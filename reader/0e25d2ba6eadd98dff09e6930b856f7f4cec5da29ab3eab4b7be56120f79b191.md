---
layout: post.njk
source: https://yage.ai/share/deepseek-v4-agentic-workload-20260429.html
speaker: yage.ai
title: 深入浅出 DeepSeek V4：围绕 Agentic 负载的工程决策
date: '2026-04-29'
summary: 文章深入探讨了 DeepSeek V4 模型在处理 Agentic 工作负载时所做的工程决策。它回顾了 V2/V3 在成本优化和 V4 在长推理上的贡献，重点分析了 V4 如何通过混合注意力机制（HCA/CSA）、On-Policy Distillation（OPD）以及 Muon 优化器和 mHC 稳定训练等工程实践，来解决长上下文保留、多能力模型合并以及复杂系统训练的挑战。文章强调 V4 是一个务实的工程系统，展示了当前大模型竞争已转向工程整合能力。
area: tech-engineering
category: ai-ml
tags:
  - agentic-workload
  - long-context
  - attention-mechanisms
  - on-policy-distillation
  - model-engineering
people: []
companies_orgs:
  - DeepSeek
  - OpenAI
  - Thinking Machines Lab
products_models:
  - DeepSeek V4
  - DeepSeek V2
  - DeepSeek V3
  - R1
  - o1
  - Transformer
  - MoE
media_books: []
draft: true
status: evergreen
---

> 本文由 DeepSeek-4-Flash 生成

## 三代模型，三个不同的问题

要理解 DeepSeek V4
在做什么，最直接的路标是看看它之前两代模型各自解决了什么。

V2 和 V3
面对的核心问题是训练和推理的算力成本。那时大模型服务的主流方式是 dense
model，无论训练还是推理，都在消耗大量计算资源。DeepSeek 的回答是
MoE（混合专家模型，Mixture of
Experts）：通过路由机制让每次推理只激活一小部分参数，配合负载均衡和低精度计算，让同等算力服务更多用户。这个时期的矛盾是成本与吞吐。

R1 面对的是另一个问题。OpenAI 的 o1
展示了长推理路径的价值——模型在给出答案之前，先生成一段内部思考过程，反复验证和纠错。但
o1 的方法论不透明。R1
的核心贡献是证明了纯强化学习路线可以让模型自主发展出这种长链推理能力，不需要大量人工标注推理轨迹。

到了 V4，问题又变了。V4
要处理的不是一次问答，甚至不是一次长推理，而是一个持续多轮的 agent
任务：读一个代码仓库、看各种报错日志、调用工具修改文件、运行测试、根据结果再调整，反复多次直到任务完成。途中模型需要记住自己改过什么文件、工具返回了什么结果、哪些假设已经被排除。这就是
V4
technical report 的核心目标——agentic workload。

三个问题对应三代模型。V4
的位置就在从对话工具转向任务执行系统这个转折点上。

读 V4 的 technical
report，会想起《三体》里的蓝色空间号——那不是一艘在船坞里为优雅而造的飞船，而是在黑暗战役后走上真正远航时被逼出来的样子：携带了够用几百年的聚变燃料，关键部件做了八重冗余，外挂存储仓让船体看起来像个不规则的大块头。它不漂亮，但更像一个长途旅行者的真实状态。

V4
的技术选择也像这艘船：不追求理论上的最简方案。你会看到它没有选最经典的
attention
路线，也没有走最激进的效率路线，而是针对不同场景拼接了几套机制；后训练没有选最直观的端到端
mixed
RL，也没有做最方便的权重平均，而是先分开训练再蒸馏合并；训练系统混合了两种优化器、多种精度和大量工程补丁。V4
看起来并不美，也不优雅；它更像一个务实、有效的工程系统。

从 agentic workload 这个目标出发，V4
的每一个关键选择都可以推出来。Agent 任务同时把三个矛盾推到前台，V4
的技术报告本质上就是在回答这三个矛盾。

## 第一个矛盾：能装下
1M token 还不够，agent 要能用上它

对 agent 任务来说，1M token
的上下文窗口不只是”能装下多长文档”的问题。通过长上下文测试只是起点——agent
需要在十几轮工具调用中反复检索历史、持续保留任务状态，这对上下文的要求和读一段长文档完全不同。

Agent 场景和传统的 needle-in-a-haystack 测试有本质区别。针在 haystack
里的测试是：文本很长，但问题明确，答案在某一个位置，模型只需要找到它。Agent
任务不是这样。一个 coding agent
可能已经跑了十轮工具调用，每一轮的用户需求、返回结果和中间推理都在上下文里。它需要随时回看某段报错日志、某次工具返回的
JSON、某个已经放弃的方案为什么被放弃。这种场景需要的不是找一句话，而是保留一个持续演化的任务状态。

传统聊天模型可以在新一轮用户消息到来时丢弃旧 thinking
内容来节省上下文。Agent 场景不能这样做——丢弃旧 thinking
等于丢弃已经积累的任务状态。V4 report
也明确区分了这两种场景：在工具调用场景中保留完整推理历史，在普通对话中丢弃旧
thinking。这说明 1M context 的重点在于 agent
能不能在长任务中保持可用状态，而不是单纯能读多长的文档。

这个问题最终落到 attention 机制上。Transformer 每生成一个新
token，都需要决定上下文里哪些部分值得参考——attention
就是做这件事的查找机制。当上下文只有几千 token
时，这个查找成本可以忽略；但到了百万 token 级别，且 agent
需要反复回看旧日志、工具返回结果和代码片段时，attention
就成了成本和召回精度冲突的地方。

面对这个问题，设计者有几种路线可选。

一条是 full attention。它最可靠，历史里每个 token
都保留精确的访问路径。模型需要回顾哪段代码、哪个日志片段，都能精确定位。但在
1M context 下，每生成一个 token
都要扫一遍全部历史，计算代价很难接受。这相当于每次查找都把整座档案馆从头到尾翻一遍——精度最高，但每次全馆重扫的成本很难承担。

另一条是改用 linear attention 或 SSM（State Space
Model，状态空间模型）这类替代架构。这类方案基本放弃了 attention
那种按需回看历史 token
的范式，把历史压进固定大小的状态里。成本大幅降低，但 token
级别的身份信息被融合。对 agent
任务来说，精确回看某段代码、某个工具返回结果，比理解全局趋势更重要。完全放弃
attention 的按需检索能力，可能同时压掉关键能力。

两条路都有代价。V4 的做法介于之间：保留 attention
的精确查找能力，但不全馆重扫——先看地图确定区域，再抽相关柜子来查。它在
attention 框架内做压缩和分层：

第一层是 HCA（Heavily Compressed
Attention，重度压缩注意力）。它把远处历史压缩成更粗粒度的
entry，然后对所有压缩后的 entries 做全局 dense
attention。信息会有丢失，但成本低，适合提供远处历史的全局轮廓。模型至少知道远处大概有一片区域涉及之前的报错日志或工具返回结果，具体内容等需要的时候再细看。HCA
像一张超压缩地图，不保留每个细节，但能让模型知道远处有哪些区域。

第二层是 CSA（Compressed Sparse
Attention，压缩稀疏注意力）。它同样做压缩，但压缩后不再对所有 entries 做
dense attention，而是用一个 indexer 选择当前 query 最相关的 top-k
个压缩块去做 attention。V4-Pro 的 top-k 是 1024，V4-Flash 是 512。CSA
像一个可查询的索引，让模型能在远处历史中按需定位具体信息。

第三层是一个 128-token 的 sliding
window。最近发生的事情——刚返回的工具结果、刚报出的
error、刚修改的代码——需要精确保留，不能只看压缩版。这像保留桌面上刚刚发生的事情。

三层合在一起：远处粗看、相关块细看、近处全看。

这个方案的折中性质很明显。它没有选择理论上最干净的 attention
替代品（full attention 或纯 SSM），而是在 attention
框架内通过压缩、选择和局部窗口来拆分访问精度，让不同的历史距离使用不同的成本与精度配置。

这个选择的收益，看数字就清楚了：在 1M-token context 下，V4-Pro 相比
V3.2 只需要 27% 的 single-token inference FLOPs 和 10% 的 KV
cache；V4-Flash 则只需要 10% FLOPs 和 7% KV cache。

但节省不是免费的。Hybrid attention 产生多种 KV entry，违反了
PagedAttention 等推理框架的一些基本假设。V4 需要同时管理 classical KV
cache 和 state cache，还要为 on-disk KV cache 设计不同策略。Attention
层的节省把复杂度转移到了 cache layout、kernel 和 serving 系统上。

## 第二个矛盾：能力分化之后，怎么合并

长上下文解决了 agent 任务的状态保留问题。但还有另一个问题没法用
attention 解决。

用人的工作状态来类比：做数学题时需要专注推导、不能被打断；查资料时需要快速浏览、随时跳转；调试代码时需要反复验证和修改。三种活动用的不是同一种心智模式。对模型来说也类似——数学推理、agentic
coding
和普通对话各自需要不同的行为策略，对应的训练目标和奖励信号差异很大。数学希望模型想得久，聊天希望响应快；coding
agent 需要多轮工具调用，普通问答希望直接回答。

这里有一个矛盾：不同能力的训练路径在早期就开始分叉，但产品形态要求用户只调用一个模型。你不能给用户暴露十几个
specialist
模型让他们自己选。所以问题是怎么把多个专家模型的能力合并到一个可服务的模型里。

读到这里你可能会想：V4 本身就是 MoE 架构，为什么不让不同的 expert
处理不同的能力？原因是 MoE 的路由发生在单次前向推理内部，每个 expert
是架构层面的参数专业化——数学推理和 agentic coding 激活的 expert
组合可能不同，但所有 expert
在同一个预训练过程中共同优化，没有被不同的后训练奖励信号单独训练过。后训练阶段的
specialist
则不同：它们是为不同任务和不同奖励信号独立训练出来的完整行为策略，参数已经被拉向不同方向。产品部署需要的是一个统一模型行为。MoE
的架构路由不解决这个层面的行为合并问题。

V4 的 OPD（On-Policy
Distillation，在策略蒸馏）就是回答这个矛盾的。理解 OPD
的最好方式是从它背后的决策树开始。

第一层：多能力怎么合并？

最简单的做法是 mixed RL，把所有任务的数据和 reward
混在一起，训练一个模型。这相当于把所有课目放进同一个训练营——流程直接，但不同课目的训练目标和
reward 互相干扰。数学和 agent
的任务长度不同，探索路径不同，失败模式也不同。同一个 reward recipe
很难同时服务所有目标。如果 mixed RL 走不通，还有没有其他方向？

一种选择是：先训练 specialist，再合并。

第二层：先训练 specialist 的话，怎么合并？

一个直接想法是权重合并（weight merge），把多个 specialist
的参数以某种方式平均。工程上看起来简单，但不同专家在各自
RL（强化学习）训练后可能已经走到不同的参数区域，直接合并容易损失能力。不同
expert 各自保留参数，由路由机制决定调用谁。Weight merge
则把多个方向压回一个参数空间里，容易两边都做不好。

蒸馏（distillation）是另一条路。它让一个 student 模型学习多个 teacher
模型的行为分布。Weight merge 是参数空间合并（parameter-space
merging），distillation 是函数空间合并（function-space
merging）。Student 不直接平均参数，而是学 teacher
的输出分布，更接近在功能层面整合多个路线。用前面的比喻说：mixed RL
是所有课目在一个训练营里同时练，distillation 是各 specialist
各自成熟之后再做统一考核。

V4 选的是后者。

第三层：蒸馏用谁的轨迹？

Off-policy distillation 用 teacher
或旧模型事先生成好固定数据集，student 去学。成本低，但 student
实际运行时走到的状态分布和固定数据不一致。用直觉来理解：学生看老师的标准录像学习。录像很干净，但学生自己上路时会犯自己的错，走到录像里没有出现过的状态。Agent
任务里这种 mismatch 更严重，因为工具调用一步错，后面的状态就全变了。

On-policy distillation 让 student 先自己生成轨迹，teacher 在 student
实际走到的状态上指导。成本更高，但训练状态和真实使用状态更一致。V4
选的是 on-policy。这一步决定了训练信号的位置：student 不只模仿 teacher
事先准备好的数据，而是在自己实际会走到的路径上接收教师校准。

第四层：teacher 给多少信息？

成本最低的做法是 token-level KL（Kullback-Leibler
divergence）估计，只看 student 实际采样出来的那个 token，用它近似
teacher 和 student 的差距。V4 report
说这种近似会导致高方差，训练不稳定。

Full-vocabulary logit distillation 保留 teacher
在整个词表上的概率分布。成本高得多，但 teacher 对其他候选 token
的判断也保留下来，训练信号更完整。V4 选的是 full-vocabulary。

把四层决策连在一起看，V4
每一步都选了成本更高、系统更复杂的路线：Mixed RL 换成
specialist-first，weight merge 换成 function-space
distillation，off-policy 换成 on-policy student
trajectories，token-level estimate 换成 full-vocabulary logits。

OPD
是这条路线最终的名字。它的代价不只是多一次蒸馏步骤，而是需要训练十几个
domain-specific teacher，维护 teacher scheduling、rollout
service、hidden-state 缓存、logit reconstruction 和 fault-tolerant
rollout 基础设施。V4 report 专门提到不直接 materialize 超过 10 万
vocabulary 的 logits，而是缓存 last-layer hidden states，再通过
prediction head
重建。这是一个典型的例子——为了降低极高的显存和计算代价，系统反而要增加新的工程层。

OPD 的方法来自 Thinking Machines Lab 的 On-Policy Distillation
工作。DeepSeek 的贡献是把 multi-teacher、full-vocabulary、long-context
rollout、teacher scheduling 和 fault-tolerant rollout
基础设施集成到一起，在工程规模上让这套方案稳定工作。

## 第三个矛盾：混合方案的工程代价

前两章解释了 agentic workload 为什么需要更复杂的 attention
和后训练。但这些复杂方案不是搭好就能跑——它们对训练系统提出了额外要求。这些要求集中在两个方面：训练效率和训练稳定性。在
V4 里，它们分别对应 Muon 和 mHC（manifold-constrained
Hyper-Connections，流形约束超连接）。这两者解决的问题是复杂架构还能不能稳定高效训练，而不是用户直接感知的能力。

训练效率：Muon

Optimizer 决定模型参数在训练中如何更新。在万亿参数、32T 以上 token
的训练规模下，选哪种 optimizer
不只影响收敛速度，还影响分布式系统的内存和通信代价——这本身就是一个系统层面的决策。

经典路线是 AdamW，业界用得最广的默认 optimizer。V4
没有只走这一条路，而是引入了另一条来自公开研究的 optimizer
路线——Muon。这里不展开它的数学细节；形象点说，训练参数的更新方式就像工程队修路时怎么下铲——AdamW
对每小段路面分别决定修法，Muon 更关注整段路的整体走向。

V4 没有全部换成 Muon，而是对不同参数组用不同
optimizer：多数矩阵参数用 Muon，embedding 和归一化层这类参数保留
AdamW。为了让 Muon 在
MoE、分布式并行和混合精度的框架下能工作，还需要额外做工程适配。这不是一个干净的替换故事，而是一组工程上的局部折中。

Muon 来自公开的 optimizer 研究，不是 DeepSeek 从零发明的（K. Jordan
et al., 2024；Jingyuan Liu et al., 2025 验证了它在 LLM
上的可扩展性）。V4 的工作是把这条外部 optimizer 路线接进自己的大规模 MoE
训练系统，做完工程适配后公开写下了细节。Muon 和
attention、mHC、低精度训练、分布式策略共同构成 V4 的训练成本控制。

训练稳定性：mHC

Transformer 依赖 residual connection
在层与层之间传递信号——标准做法是一条直通通道，层输出加回输入。Hyper-Connections（来自
2025
年的外部工作）想把这条通道扩展成多条，让层间信息交换更丰富。但通道越多，深层堆叠后信号越容易失衡，训练就不稳定了。

Hyper-Connections 的原始概念来自 Zhu et al.（2025），V4
用的是加流形约束的变体 mHC（Xie et al.,
2026），核心思路是在多条通道之间加一个边界，防止任何一路在深层被过度放大。代价是引入
mHC 增加了显存和通信开销，必须配套 kernel 优化、重计算和 pipeline
调度调整。V4 报告给出了 overhead 约 6.7%
的数字，说明这个收益以可控代价换来了更复杂架构的可训练性。

Muon 和 mHC 共同支撑一个判断：V4
不只是在前向推理上节省成本，也在扩大模型内部的可控复杂度。CSA/HCA、MoE、长上下文
curriculum、低精度训练和 OPD 都会改变梯度路径或训练分布。Muon
从参数更新方向控制，mHC
从残差信号传播控制。它们的共同作用是让由更多混合组件组成的架构仍然可训练、可收敛。

## 复杂工程系统，不需要美化

DeepSeek V4 的 technical report
展示的是一个充满局部折中的工程系统：mixed optimizer、mixed
precision、cache tricks、teacher scheduling、rollout service、kernel
优化、通信策略、mHC
recomputation。这是一个工程团队在真实约束下做了大量系统层面决策的结果，而不是一个实验室用优雅理论完成了推演。

V4 不是靠一两个简洁漂亮的原创框架驱动起来的。读它的 technical report
更像是一个广泛阅读、仔细筛选的团队，把许多不起眼但在细节上有效的方案（OPD、Muon、Hyper-Connections，加上自家积累的
MoE、MLA 和基础设施）逐一挑出来，在 agentic workload
这个目标下重新组合，并通过扎实的执行力和大量实验让它们稳定工作。能把这么多来自不同来源的组件接在一起，本身就是一种很难复制的能力。

DeepSeek 在 optimizer 适配、cache layout、teacher scheduling 和
rollout
基础设施这些环节上投入了大量资源做工程探索，最终把这些折中和取舍全部写进了
technical
report。在大模型领域越来越倾向不公开工程细节的趋势下，这种程度的开放本身就很难得。

DeepSeek V4 的独特之处就在这里：一个 open-weight
模型通过系统的工程整合处理了 million-token 级别的 agentic
workload。它不一定在每个维度上都是最强的，但作为一份公开的工程样本，它清晰地展示了一件事：这一代大模型竞争已经从谁的理论更漂亮，推进到谁能把复杂工程系统跑通。