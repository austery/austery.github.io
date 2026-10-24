---
author: AI Engineer
date: '2026-09-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iJVxxxHM_Oc
speaker: AI Engineer
tags:
  - reinforcement-learning
  - agentic-search
  - information-retrieval
  - context-management
title: 强化学习重构搜索范式：从脆弱流水线到自进化检索 Agent
summary: 传统基于大模型的检索虽然质量高，但成本高昂且耗时漫长，严重消耗 Agent 上下文与计算资源。SID.ai 提出通过强化学习训练专用的搜索子 Agent，利用搜索结果高可验证性的特点进行闭环训练。该方案相比直接调用前沿模型实现了 20 倍速度提升与 100 倍成本下降，同时避免上下文污染，展现了端到端机器设计对人工流水线的全面超越。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - SID
products_models:
  - SID-1
media_books: []
status: evergreen
---
### 检索瓶颈与范式转移：子 Agent 解耦主流程

在当前的智能体（Agent）工作流中，**Agent 架构**（Agent Architecture: 具备自主决策与工具调用能力的 AI 执行框架）正在成为搜索的新范式。相比传统查询，Agent 检索能够带来显著提升的结果质量，找到目标文档的概率提升了一倍。然而，这种能力的代价极其高昂：其单次查询成本是经典搜索的 **100 到 1000 倍**，且耗时从毫秒级退化至数分钟。

这种效率缺陷直接制约了整体性能。在各类复杂任务的起始阶段，Agent 通常需要消耗 **30% 至 50% 的 Token** 专门用于环境探索与上下文检索。针对该痛点，核心的架构优化思路是将搜索职责从**主智能体**（Main Agent）中剥离，交由专门训练的**搜索子智能体**（Search Sub-agent）独立执行。通过引入**强化学习**（Reinforcement Learning: 通过奖励信号自主优化策略的学习范式），目标是在兼顾高召回率与极高准确率的同时，将检索的计算开销与延迟降低数个数量级。

<details>
<summary>Original English Source</summary>

Okay, today I'm going to talk about where reinforcement learning will take search and some background on me. I'm the founder and CEO of SID. We're a stealthish AI lab for search. We're backed by some pretty amazing people. And we're hiring.

Okay. Agents are a new paradigm for search. You can now get vastly higher quality results. Twice as likely to find the right documents. But it's incredibly expensive — about a hundred to a thousand times more expensive than what you'd get out of a classical search query, and it is extremely slow. You're looking at minutes and not milliseconds.

And what this means is that agents spend 30 to 50% of their tokens on searching. And this is usually at the beginning of some task. It finds the right context to then do whatever you ask it to do. And the idea here is quite simple. First, instead of having the main agent do the searching, you pass the searching to a sub agent and you train a model to be a great sub agent.

And the question here that we'll answer today is: how much cheaper and faster can we make this with reinforcement learning? And this is really our target. So this is a benchmark across legal, finance, knowledge bases, science, email, a bunch of different tasks, some academic benchmarks, some internal benchmarks. And this is where you currently are: you see reranker and vector-only performance at the bottom, and you can see frontier models essentially go through here at the cost of spending many, you know, minutes per question. And can we get a model to be extremely accurate, have extremely high recall, but also be incredibly fast and cheap?

</details>

### 流水线溃败：端到端机器设计超越人工规则

剖析经典搜索流水线有助于理解当前系统的结构性缺陷。典型的传统架构由多个级联组件构成：输入问题后，先由大语言模型进行查询重写，再发送到底层检索后端，最后通过**重排器**（Reranker: 对候选文档进行二次精细打分的模型）输出结果。这一链路的本质是由人工在设计期固化逻辑、局部优化的模块链条，且对每个问题分配固定的计算量。

该流水线的致命弱点在于**缺乏行动闭环**：重排器即使判定当前返回的文档无法回答问题，也无法触发重新查询，只能被动返回劣质结果。这种机制导致系统在面对预期之外的长尾查询时持续累积失败案例。业界通常通过人工堆砌边缘规则（Edge Cases）进行修补，但人工规则在面对无限复杂的长尾分布时注定失效。

从技术发展史来看，**机器设计超越人工设计**是必然规律：
* **计算机视觉领域**：经历了从早期的原始边缘检测算法，到特定目标检测的小模型局部优化，最终演变为端到端的**视觉语言模型**（Vision-Language Model: 统一处理图像与文本的多模态大模型）。
* **博弈决策领域**：国际象棋从依赖人类专家规则的 **IBM Deep Blue**，演进到混合架构的 **Stockfish**，再到完全通过自我对弈学习策略的 **AlphaZero**。
* **搜索领域演进**：正经历由 **BM25** 与 **PageRank** 等传统算法，过渡到向量检索与重排小模型，最终迈向**纯强化学习**（Pure RL）驱动的新范式——彻底放弃在设计期固化规则，将全链路决策权交由模型自主掌握。

<details>
<summary>Original English Source</summary>

And let's quickly look at classical search. This is the pipeline that many of you guys will be familiar with. A question comes in, you might have an LLM that rewrites the question. You then execute that on a search backend. You might have a reranker, and you get your results at the end of the day. It is essentially a pipeline of chained locally optimized models, and all of the decisions are baked in at design time and you expend a fixed amount of compute per question.

And this one is really important: the re-ranker might know that the results are insufficient at answering the question, but the re-ranker can't take action. It can only essentially return the results even when they're bad. And what this means is that in practice a pipeline like this accrues a long tail of failure where unexpected questions come that the designer didn't have something for. And in practice this usually means people add lots of edge cases to essentially fix these. But of course you can't design infinite edge cases and you can't add infinite tweaks.

And so the strategy here is one that we've seen before: machine design outperforms human design. We saw this in computer vision where you had primitive edge detection algorithms, then you had the box-around-a-dog generation of models that were very good at this very narrow task and locally optimized for it, and then you had VLMs that were extremely good at all parts of the pipeline. You saw this again with chess with IBM Deep Blue being largely a collection of human-written rules, Stockfish bridging the two, and then AlphaZero and MuZero essentially completely putting it all inside of the model.

And we're going to see something similar happen to search, where we have our existing algorithms like BM25 and PageRank, then we had an evolution from that with small models that did some task very well like vectors and re-rankers, and now essentially this new paradigm of pure RL where we actually don't bake any design decisions into the model.

</details>

### 可验证奖励与模型专用化：RL 训练的底层支撑

在纯 RL 架构下，单一模型与底层数据库进行多轮自主交互：它可以主动执行搜索、评估阅读结果、动态追加元数据过滤条件，并根据置信度自主决定是否发起下一轮检索或终止并输出排序结果。这种架构赋予了系统针对问题难度动态分配计算资源的能力。

搜索场景之所以成为强化学习的理想标的，核心在于其具备**高可验证性**（Verifiable）与**高频可训练性**（Grindable）：
1. **明确的验证信号**：对于特定检索目标，模型是否命中准确文档可通过自动化指标精确判定，构建可靠的奖励函数。
2. **高吞吐训练环境**：在训练集群中，系统支持每秒发起数千次模拟检索迭代，为策略梯度更新提供密集反馈。

与此同时，**模型专用化**（Model Specialization）构成了另一大效率支柱。通用大语言模型的大部分参数容量在特定检索任务中并不必要。类比于硬件计算体系中 CPU、GPU 与 **ASIC**（Application-Specific Integrated Circuit: 专用集成电路）的分工差异——尽管 CPU 具备通用计算能力，但在执行大模型推理时专用硬件具备压倒性的效能优势。将模型精简并专注于检索决策，使得训练出的策略模型在保持极低延迟的同时能够自主涌现出复杂的搜索策略。

<details>
<summary>Original English Source</summary>

And what this looks like in practice is something like this: you have one model, it goes back and forth with the database. It can search, it can read results, it can iterate. It can search again until it is happy. It can set metadata filters on the fly. It can constrain its search. It can try as much as it wants. And in the end, it produces a ranked list of results.

And what you get is a model that makes all of the decisions and can adapt to any question on the fly and, for example, use much more compute if a user asks a very difficult question.

And what helps us here is that search is verifiable. Reinforcement learning needs rewards that are verifiable and grindable. Verifiable here means for a given question, did you find the correct document? And we can design this and tell this quite easily. And is there an environment where the model can attempt this question loads and loads of times? In practice for us this means thousands of times per second during a training run.

And the second part is: can we turn the models that are currently very general-purpose into something that is much more specialized? It turns out we don't actually need most of the parts of a language model to be extremely performant at search. Similarly with CPUs and GPUs and ASICs, a CPU in theory can do anything that a GPU can do, but you would never want to use a CPU to do LLM inference, because the much more specialized version is much more effective. And this really makes search an ideal target for RL. And this is what happens when you train a model on this task.

</details>

### 性能跃迁与企业级未来：解耦污染与私域数据激活

基于强化学习训练的专有检索模型 **SID-1** 在多项基准测试中展现出显著的缩放规律（Scaling Laws）：搜索质量随着训练算力投入呈现高度可预测的线性增长，且可通过在奖励函数中混合延迟（Latency）与策略多样性指标进一步调优。

在实际生产环境中，**SID-1** 与并行执行架构带来了颠覆性的性能提升与架构解耦优势：
* **极致性能表现**：平均单次检索延迟从通用前沿大模型的约 **2 分钟缩短至 5 秒**（提速约 20 倍），推理成本降低约 **100 倍**，逼近传统向量重排流水线的响应速度。
* **防止上下文污染**（Context Pollution: 无关或错误的中间检索信息占用并干扰 LLM 注意力窗口）：传统架构下主 Agent 的多轮试错会将其上下文塞满无效信息；而在子 Agent 架构下，所有检索推理与过滤试错均在沙盒内部完成，主 Agent 仅接收最终提炼的高质量候选集，直接提升了终端决策的准确率。

展望未来，强化学习在搜索领域的缩放将解锁更广泛的应用场景。超低延迟将使深度检索直接嵌入语音交互与实时电商场景。更重要的是，互联网公开数据仅占全球数据总量的一小部分，最具价值的企业内部专有知识——例如 **摩根大通**（JP Morgan）庞大复杂的内部运营与业务数据库——从未公开于公网，而具备自主深度探索能力的 RL 搜索智能体将成为激活这些高价值私域数据的关键基础设施。

<details>
<summary>Original English Source</summary>

And so again, here we added the vector and reranker-only baselines. This is of an earlier task. And what we see is that search quality increases very predictably with compute. And we can mix in other rewards like latency and different kind of retrieval strategies to make it even more performant. Importantly, we don't really tell the model what to do. Much like in AlphaZero and chess, we want it to discover its own strategies and its own tricks to essentially search well. And we don't know whether this method has no ceiling, but we're definitely not yet seeing a ceiling to this approach.

And these are the results. This is the same chart as before. And this is SID-1 and then SID-1 with some parallel execution on the left-hand side. And what this ends up meaning is you're about 20 times faster. So instead of taking around 2 minutes, you take around 5 seconds on average. And it's about a hundred times cheaper than using a frontier model for this task. The cost and speed are just completely incomparable. It's not quite at the latency of a vector and reranker pipeline, but in practice we think we can get there quite quickly.

And how does this look like in production? This is a usual agent execution trace. The agent does some searching here. It finds some good stuff. It finds some bad stuff. But all of the bad stuff that it finds is essentially polluting its own context window. And what we can instead do is use a sub agent here that does all of the searching and thinking and iterating for the main agent. And the main agent only ever sees great results. This means that the main agent sees more good stuff, which means it's more likely to be correct. And it is also extremely cost-effective, where those 30 to 50% tokens that were earlier used by the main agent to do searching can now be passed off to this 100x cheaper search sub agent.

And where will this take us? Scaling RL will give us arbitrarily good search in any domain, and RL models will become even faster which will allow them to be used in things like voice and e-commerce. They'll become even cheaper than we are currently. And better search will unlock more knowledge work tasks. The web is actually quite small in comparison to the entirety of data that is out there. And the most valuable information is not on the internet. For example, how to run JP Morgan is nowhere on the web, but it is deep inside of the databases at JP Morgan. That's it for me. Thank you.

</details>