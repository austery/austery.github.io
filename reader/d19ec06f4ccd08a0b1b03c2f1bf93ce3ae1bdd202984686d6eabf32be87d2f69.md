---
layout: post.njk
source: https://yage.ai/share/prefix-cache-agent-cost-lever-20260625.html
speaker: yage.ai
title: KV cache 命中率：Agent 推理的第一成本杠杆
date: '2026-06-25'
summary: 文章深入剖析了大型语言模型（LLM）推理过程中，Prefill 阶段对计算成本和延迟的巨大影响。核心观点指出，KV cache 的命中率是决定推理成本的关键杠杆。通过分析 ReAct agent 工作负载，研究表明优化 KV cache 命中率可以显著降低 GPU 账单，并大幅提升推理效率。文章提出了从压缩层、路由层到 API 层缓存等三层工程实践，以及 'context engineering' 作为新的学科，来系统性地管理输入成本与质量的平衡。
area: tech-engineering
category: ai-application
tags:
  - kv-cache-hit-rate
  - prefill
  - prefix-caching
  - context-engineering
people: []
companies_orgs: []
products_models: []
media_books: []
draft: true
status: evergreen
---

## 一个 ReAct agent 的账单解剖

一个 ReAct agent 执行 10 次工具调用，总共只产出 500 个 output
token，却吃掉了 80 万 input token。模型做那 500 个 token
的生成只需毫秒，但在每轮工具调用开始前，它必须先把几万甚至几十万个 input
token 全部处理一遍才能理解当前状态。这个过程叫
prefill，耗时数秒，而且每轮都要重新计费。

这不是某个极端用例，是 agent 工作负载的普遍特征。Spheron
在生产环境测出 agent 推理任务里 prefill 占比高达 85-95%，input 到 output
的原始比率达到 267:1，每生成一个 token 就要重读 267
个。在这个负载特征下，决定推理成本和延迟的第一变量不是模型选型，是 KV
cache 命中率。同一个 agent 工作负载，cache 命中率从 0% 提升到 90%，月度
GPU 账单可以从 2 万美元降到 2 千美元。arXiv 2605.26297
的推理成本分析独立验证了这一点：有效缓存介入后，append ratio 从 53.9 到
559.8 倍的原始区间骤降至 1.5 到 7.3 倍，decode 阶段重新占据 91% 到 98.6%
的时间占比。

KV cache hit rate vs TTFT

## Prefill 才是 agent
账单的主要成分

要理解上面这个判断，得先碰一下 LLM 推理的内部机制。LLM 接收 input
token 时，需要为每个 token 计算一组 key-value 矩阵（K 矩阵和 V
矩阵），存到 GPU 显存里供后续生成时查询，这个计算过程就是 prefill。KV
矩阵的大小和 input token 数量成正比：input 越长，prefill
越重，占用的显存越多。生成新 token 很快，把旧东西重新读一遍很慢。Cockroach
Labs 对规模化 agent
推理的成本拆解印证了这一点，重读开销在总账单中的占比远高于直觉预期。

prefix caching 正是针对这笔重读开销的优化。如果下一轮请求的 input
前面一大段和上一轮完全一致，这一段的 KV
矩阵就不需要重新计算，直接从显存里复用。这部分共享前缀每轮自动变长，缓存命中次数越高，实际需要新算的
token 越少。命中了叫 hit，没命中叫 miss，hit rate
是衡量这个机制好坏的直接指标。

agent 场景恰好把重读问题推到了极致。每轮工具调用的 prompt 由 system
prompt、tool schema、对话历史三部分组成。system prompt 和 tool schema
在所有轮次里完全不变，对话历史越长，不变前缀的占比反而越大。Stanford
的统计显示 re-sent context 占 agent 推理账单的
62%，绝大部分开销花在了让模型反复咀嚼它已经知道的信息上。Manus 团队把 KV
cache hit rate 称为 production agent 的第一指标。

各 API 供应商的定价结构也给出了侧面证据：cached input
的价格普遍是非缓存输入的 0.1 到 0.5 倍。供应商在前缀复用时几乎不产生额外
GPU 开销，自然有能力把折扣传递出去。这本身就是一个结构性信号，说明
prefill 才是账单的主要成分。

当然，这个判断成立的前提是 agent
工作负载有稳定的前缀复用。如果每个请求的输入完全不重复、没有可复用的前缀结构，prefix
caching 的收益趋近于零。同样地，当并发请求的总 KV cache 占用超出 GPU
显存容量时，缓存会被不断挤出再重新加载，prefill
重新成为主导，进入缓存颠簸（thrashing）的状态。

## 三层工程栈：压缩、路由和 API
缓存

知道了 cache hit rate 是成本杠杆之后，问题转移到怎么让它更高。2026 年
6
月，有三层工程实践分别从不同方向回答了这个问题，各自面向不同的控制者。压缩层改的是
vLLM、SGLang 这类 inference engine 的内部算法和内存管理，只有 engine
维护者或自托管大模型的 infra
团队能动。路由层改的是多副本部署的负载均衡，只有自己部署 GPU
集群的团队有控制权。API 层的 prompt caching 是用 Claude、OpenAI API 的
agent
开发者唯一直接能碰的部分。三层互相叠加、各自独立演进，合在一起构成了一条完整的命中率提升栈。你可以根据自己的角色对号入座。

压缩层解决单次推理的内存效率。KV 矩阵本身就挺大，一个 100K token
的上下文产生的 KV cache 可以轻松占用几十 GB 显存。如果把 KV
矩阵压小还不丢太多信息，缓存能存下更多上下文，命中率自然上升。

CompressKV 在 2026 年
6 月发表于 arXiv 的工作打开了一条新路径。论文作者发现 transformer 的不同
attention head 分工并不均等：有一小部分 head 专门负责语义检索，称为
Semantic Retrieval Heads，它们的 attention score
能够精准定位上下文中哪些 token 对当前生成任务有价值。用这几组 head 的
score 来决定保留哪些 token，只需要保留 3% 的 KV cache 就能在 LongBench
QA 上守住 97% 的性能。在更极端的 Needle-in-a-Haystack 测试里，仅用 0.7%
的容量也拿到了 90% 的准确率。同期 STAR-KV 和 R-KV 从不同路径探索了 KV
cache 压缩的上界，CacheBlend
则在压缩后的缓存语义保真度上做了补充。

压缩算法本身已经足够好。眼下的瓶颈转移到了怎么让算法在生产 serving
栈里跑起来。NVIDIA
的博客点出了两堵工程墙：FlashAttention 内核不暴露 attention score，依赖
score 做 eviction 决策的方法拿不到数据；paged attention
管理内存的最小单位是 block，只有整个 block 都空了才释放，eviction 后幸存
token 散布在不同 block 里，碎片化导致内存实际上释放不掉。Tangram
的解法是把非均匀压缩需要的动态开销通过离线校准全部静态化，throughput
拉高 2.6 倍。UltraQuant
走硬件侧，用 4-bit
量化直接适配矩阵核心的原生指令。三条路径各自从不同方向推进，并行演进。

路由层解决的则是多副本部署下的缓存亲和性问题。假设有 8 个 vLLM
副本挂在一个标准 Kubernetes service 后面，负载均衡器默认用 round-robin
轮转分发请求。第一个请求带着某些前缀进来，KV cache 写进了副本
1。第二个请求带着完全相同的 system prompt 进来，round-robin
把它送到了副本 2。副本 2 的显存里没有这个前缀的 KV
矩阵，只能从头算，全部
miss。集群越大，同一个前缀第二次被送到相同副本的概率越趋近 1/N，prefix
caching 的收益被路由层完全抵消。TrueFoundry
的测试给出了量化证据：相同前缀的请求被反复送到不同 GPU 副本时，KV cache
命中率归零，延迟和成本立即回到全部 prefill 的水平。

路由问题在 2026
年上半年从隐性假设变成了显式工程目标，三个主要生态已经分化成型。llm-d 来自 Red
Hat 社区，走 Kubernetes 原生路线做 precise prefix-cache scheduling，在 8
个 Pod、16 块 H100 的环境下测出了决定性差距：TTFT p90 从随机调度的 92.5
秒降到 0.54 秒。SGLang SMG
的 cache-aware routing 在吞吐量上拿到 1.9 倍提升，命中率增加到 3.8
倍。GKE
Inference Gateway 把 TTFT 压低了 92.8%。Snap 的生产环境稳定跑在
75-80% 的命中率上。Together
CPD 的 cache-aware disaggregated inference 和 DigitalOcean
的生产实践也在往同一个方向收敛。vLLM
Router 的 consistent hashing
路线给出了另一种选项。几个方案已经分化，意味着 prefix boundary
的调参仍需人工介入，但路由这件事从现在起不再是隐形的。

API 层的 prompt caching 是大部分 agent
开发者能直接用的最快路径。Anthropic 的 Claude
prompt caching 把 cached input 按 0.1 倍计费，相当于 90%
折扣。它允许在 prompt 里设置 4 个缓存断点，天然对应 agent prompt
的四个静态区域：system prompt 打一个、tool schema 打一个、few-shot
示例打一个、长文档打一个。每轮推理只在 prompt
里变化的部分付全价，不变的区域全部享受折扣。

这个方案在 2026 年 3 月 6
日出了一次事故，暴露了整套机制的单点脆弱性。Anthropic
在那天静默地把缓存默认 TTL 从 1 小时降到了 5 分钟，agent 用户的账单瞬间暴涨
100 倍，连锁反应在社区里迅速扩开，最终定位到需要显式声明
"ttl": 3600 字段才能恢复之前的缓存时长。

API 层 prompt caching
已经从可选优化变成了默认基础设施，但坑还不少。Requesty
在 2026 年 4 月统计了同一模型在不同平台上的 cache hit rate：Claude
直连的命中率是 77.5%，同样通过 Google Vertex AI 走的 Claude 命中率只有
23.5%，同一模型、不同网关、命中率差了三倍。Morph 的 5
杠杆叠加模型显示，系统性地组合缓存断点位置、TTL、prompt
结构（静态部分前置、变量部分后置）、厂商选择和命中率监控，可以达到 90%
以上的成本节省。在存储侧，KVFlow 和 Lablup
与 VAST Data 的 KV cache offload benchmark 拓宽了缓存的容量边界，LMCache
的新架构 在 MoE 模型上把推理性能提升了 10 倍。

## context engineering
正在凝成一个新工程学科

这三层栈不是三个独立的方向，而是同一个问题在不同基础层的投影：怎样让模型重读已知信息的成本趋近于零，同时不损失推理质量。实现这个目标需要同时管理
cache hit rate（成本）、context rot（内容陈旧导致质量下降）和 error
propagation（缓存错误向前传播），任何一个单点优化都覆盖不全这三个维度。

prompt engineering 关心怎么问，优化的是 output 质量，典型成本节省在
5% 到 8%。RAG 关心检索什么，优化的是检索内容的相关性和覆盖度。context
engineering 关心的是信息进入上下文的顺序、缓存策略和压缩方式，优化的是
input 成本加延迟加质量三个指标，典型节省可以达到 55% 到
60%。它补上了前两种实践不碰的层面。

arXiv 2605.27744
提出的 agent runtime layer 架构从另一个角度交叉验证了这件事。论文里列了
9 个跨模块的 policy，包括缓存、重试、聚合、身份管理等，每个 policy
都需要 agent identity 作为共享坐标才能协调，单纯在 framework 层或者
engine 层都处理不了。Preprints 上的
survey 从 sufficient state approximation
的理论角度对这条线做了综述，给它装上了系统的学术骨架。Cognition AI 把
context engineering 称为构建 agent 的第一号工作。Gartner 把 2026 标成
Year of Context。

context engineering 这个词有被营销稀释的风险，Gartner
对它的一部分描述里掺杂了 data engineering 和 corporate anthropology
这类远离工程实质的范畴。但工程的实底是稳的：可量化的
ROI、接近完整的工具链、从 attention head 到路由策略到 API 断点的理论
grounding，这些不是 buzzword 能撑起来的东西。Nexus Sampling 和 IntentKV
等新工作持续在压缩效率和语义保真两个方向给出新上界，说明这个学科正在从经验直觉走向系统化设计。

## 从成本账到行动项

跑多轮 agent 的团队，先开 prompt caching 再谈模型选型。这是 ROI
最高、集成成本最低的一步：不改代码架构、不影响模型行为、直接作用于账单。Claude
的 4 断点加 1 小时 TTL 是当前最可控的方案，把 system prompt、tool
schema、few-shot
和长文档各自打上缓存断点，每轮只对变化部分付全价。同步把 cache hit rate
设成看板上的第一个指标，它和成本的相关性比任何模型版本号都直接。

自托管多副本的团队，路由策略比换模型重要。最低门槛是把 round-robin
切换成 prefix-hash
routing，让相同前缀的请求落到同一个副本上，立刻恢复前缀缓存收益。fleet
稍大的团队可以上 llm-d 的 precise scheduling，把 TTFT p90
从分钟级压到秒级，或者走 vLLM Router 的 consistent hashing 路线。NVIDIA
Dynamo 的低延迟分布式框架给出了另一种整合方案。

context engineering 作为一个方向，处理的正是 prompt engineering 和
RAG
都不碰的层面：信息进入上下文的顺序怎么排才能让缓存断点落在重复段上、压缩算法在削
KV cache
时怎样保证检索质量不掉、路由策略在多个副本间怎样让相同前缀聚到一起。它不是营销词，是
agent 推理成本逐渐明朗化之后自然浮现的结构性新维度。