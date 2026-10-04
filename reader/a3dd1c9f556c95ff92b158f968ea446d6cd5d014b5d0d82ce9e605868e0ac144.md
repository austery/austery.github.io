---
author: AI Engineer
date: '2026-07-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=EUsPvBeIx70
speaker: AI Engineer
tags:
  - semantic-blindness
  - ai-agent
  - query-resolution
  - context-window
  - system-scaling
title: 解决 LLM 语义盲区：如何为 50 万个传感器的 AI 工厂构建可扩展的 AI 智能体
summary: 本文探讨了 Phaidra 在为 1GW 级 AI 工厂（数据中心）构建 AI 智能体时面临的“语义盲区”挑战。在面对 50 万个命名规则混乱的设备传感器时，传统 RAG、向量检索和分片 LLM 方案均告失效。Phaidra 团队通过将层次化拓扑结构（Software 1.0）与 LLM 查询规划能力（Software 3.0）结合，实现了 100% 的查询准确率，并使 Token 消耗降低了 300 倍，探索出 AI 原生软件从 3.0 向 1.0 反向演进的成熟路径。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Phaidra
products_models: []
media_books: []
status: evergreen
---
### 语义盲区与背景介绍

**Rahul Singh**: 欢迎大家。我叫 **Rahul Singh**，是 **Phaidra** 的主任人工智能研究工程师（Staff AI Research Engineer）。

<details>
<summary>Original English</summary>

**Rahul Singh**: Welcome everyone. My name is Rahul Singh. I'm a staff AI research engineer at Phaidra.

</details>

**Vance Levstik**: 我是 **Vance Levstik**，是 Phaidra 的高级工程经理。

<details>
<summary>Original English</summary>

**Vance Levstik**: And I'm Vance Kulistik. I'm a senior engineering manager, also at Phaidra.

</details>

**Rahul Singh**: 今天我们想聊聊曾经发生的一件事：我们给大语言模型（LLM）输入了 **500,000 个传感器名称**，结果它彻底搞糊涂了。我们将这个问题称为**语义盲区（semantic blindness）**。

在 Phaidra，我们致力于为 **AI 工厂**构建 **AI 智能体**（AI agents）。这包括开发能够让我们的客户与他们的数据中心进行“对话”、向自己解释并理解数据中心如何运转，以及他们在日常运营中面临哪些问题的智能体。用户的查询可以是各式各样的，从“哪个冷水机组（chiller）温度过高”到“分析我所有数据大厅的温度分布”，再到“我的 GPU 有遇到什么问题吗？”。

从这些千奇百怪的查询中可以看出，它们既包括针对特定设备（比如“6号冷水机组状态正常吗”）的提问，也包括针对设备群组（比如“1号数据大厅里的 GPU”）的询问。然而，整个行业目前还没有形成统一的命名规范，每个客户都有自己的一套命名方式：有的很简单，比如直接包含 GPU 所在机架和数据大厅，让你能一目了然地知道各个设备在哪里；但有的则极其晦涩难懂，比如像 `CH3-xxxx-6` 这样的代号。在行业中，我们见过各种各样千奇百怪的命名方式。

在构建演示系统（demo）时，这套机制运行得很好，因为你只在很小的规模上工作。一个简单的大语言模型就能浏览你所有的设备名称，并理清用户在谈论什么。但是，随着系统规模的扩大，这个问题会迅速变得无法解决。例如，在一个 **1吉瓦（1 GW）规模的工厂**中，你会看到超过 **400,000 个 GPU**，为了支持这些 GPU 运转，你还需要配备电表、冷水机组以及其他各种配套设备。大语言模型的上下文窗口是有限的，你会非常快地将其填满，这就会变成一个巨大的瓶颈。就像我们常说的，一个真正的产品是必须能够应对所有场景且不会发生隐式失败（fail silently）的系统，而演示 demo 只需要保证在一种特定情况下跑通即可。

<details>
<summary>Original English</summary>

**Rahul Singh**: And today we want to talk about the time when we gave an LM 500,000 sensor names and it got confused. We call this problem semantic blindness. At Phaidra we build AI agents for AI factories. This includes agents which allow our customers to talk about their data centers and explain to themselves and understand how the data centers are working and what problems they are facing on a day-to-day basis. User queries can be anything from what chiller is running hot to analyze the distribution of temperatures across my data halls to is any of my GPUs facing any problems? Now from this variety of queries you can see that these include talking what specific equipments is chiller six all right to talking about a groups of equipments GPUs in data hall one. The industry has not really figured out a common naming pattern yet and every single customer can have their own things from simple names like racks with GPUs with data halls which give you an exact idea of where different things are to something that is more difficult to comprehend like CH3 something something six. We've seen all kind of names in the industry going forward. Now when you're building a demo system this works because you're working at a small scale. A simple LM can look at all the names of your equipment and figure out what user is talking about. But this problem really becomes intractable as you go to for scale. For example at 1 gigawatt scale factories you will see 400,000 plus GPUs and to support those GPUs you have power meters, you have chillers, you have other equipments. LM context windows are finite and you will very quickly saturate and it just becomes a problem. Like we say, a product is something that works for all scenarios and does not fail silently. A demo just has to work for one.

</details>

### 传统方案在规模化下的失效

**Vance Levstik**: 除了让大语言模型自己去理解这些名称之外，我们其实也可以将它们嵌入到机架数据库中，也就是采用**向量嵌入（vector embedding）**或**语义检索**的方法。但问题在于，很多时候这些名字实在是太相似了，导致语义搜索直接失效。

如果一个长达 20 个字符的字符串名称与另一个名字只差一个字符，它们之间的向量差异是极其微小的。例如，“Chiller 6” 和 “Chiller 7” 的区别，或者某些 CDO 命名代号的区别。由于相似度过高，你很难获得准确的召回率（recall）。

此外，大语言模型还存在所谓的**频率惩罚（frequency penalty）**机制。如果你让模型反复输出非常相似的名称，或者更准确地说是反复输出非常相似的 Token，大语言模型内部的惩罚机制就会被触发，从而直接强行关闭输出。比如，如果用户问：“你能列出 i7 区域所有 GPU 的名字吗？”假设那里有 100 个 GPU，仅仅是通过逐个列出它们的名字，LLM 的安全护栏或频率惩罚就会认为模型陷入了死循环（spiraling），进而直接终止系统运行。

因此，这两种传统路径都是行不通的。普通的 **RAG**（检索增强生成）无法工作，单纯依赖幼稚的 LLM 也无法解决问题。随着我们转向生产系统，我们需要一种能够随着系统规模扩大而同样进行扩展的解决方案。接下来我们将讨论一些比较天真的尝试。

一个天真的解决方案就是“分而治之”。把不同的设备划分到不同的分片（shards）中，然后将它们分别传给多个大语言模型。我们本以为这种**并行 LLM 调用**能够奏效。但实际上面临的问题是，你会得到极其糟糕的召回率，并且伴随着严重的**幻觉（hallucinations）**。大语言模型会凭空捏造根本不存在的幽灵设备（phantom equipment），同时也会默默丢掉实际存在的设备。对于任务关键型系统（mission-critical systems）来说，这是一个致命问题，因为用户必须确切地知道他们的系统发生了什么，任何失误都会迅速侵蚀用户的信任。同时，这也会导致遗漏特定的问题，进而级联恶化成更大的灾难。

总之，我们意识到：随着物理基础设施规模的增长，基于纯大语言模型的解决方案无法简单地随着组件、实例或节点数量的增长而同步线性扩展。我们必须寻找一种随着设备数量增加而呈**亚线性增长（sub-linearly）**的方案。这就是我们的核心突破点。我们不能让系统复杂度随着实例数量增长，而是应该让它随着**树的深度（tree depth）**增长。

<details>
<summary>Original English</summary>

**Vance Levstik**: In addition to having the LLM figure out these names, we could also have embedded them in a rack database, a vector embedding approach. But, the problem is often times the names are so similar that semantic search just fails. There's very little difference between a vector of Sorry, a string name of 20 characters long which just differs by, let's say, one character. Chiller 6 instead of Chiller 7. Or CDO something versus, well, something else. It's very small. So, you get a lot of problems with getting accurate recall. Also, LLMs suffer from what we call a frequency penalty. If you keep on outputting very similar names over and over again, or very similar tokens, more accurately, over and over again, there are internal penalties in the LLM which just shut off their output. So, if the user says, "Can list all the names of let's say GPUs in i7?" There are, let's say, 100. Just by listing through them, the LLM's guardrails would see think that well, it's spiraling, and it would just shut the system up. So, we can't really have these two approaches. RAG would not work. Just naive LLMs would not work. As we move into production systems, we need something that can scale as the system scales. Now, there are naive solutions which we shall discuss going forward. A naive approach to solve this problem would be just to well, divide and conquer. Take your different equipments, branch them in different shards, and pass them through LLMs. Parallel calls should work, right? Well, that's what we thought. The problem is you get horrible recall and hallucinations. You will see LLMs invent phantom equipment that do not exist, and also silently drop things that do exist. Now, this creates a problem for mission-critical systems where the users need to know exactly what is happening with their systems. Any problems there will quickly erode user trust. At the same time, you will miss on specific problems which can cascade into bigger, bigger problems going forward. Anyhow, something that we realized here is that as the size of these physical infrastructure grows, LLMs can not the LLM-based solutions can not grow with the size of individual components or instances or nodes. We have to find something that grows sub-linearly with increasing equipment count. And this is what we figured out. So, we should not grow with instances, we should grow with tree depth.

</details>

### 四大核心洞察

**Rahul Singh**: 所谓的“随着树的深度增长”，是指我们意识到 AI 工厂是以一种**层次化结构（hierarchical structure）**来组织的。你会拥有数据中心（data centers），然后每个数据中心有不同的数据大厅（data halls），每个数据大厅有不同的通道（aisles），通道里有不同的排（rows），然后是机架（racks），最后才是 GPU。同样地，冷水机组系统也有安置冷水机组的机房，然后有水泵，还有独立的冷却塔单元。这就像一棵树。

这棵树的深度增长得非常缓慢，而宽度增长得极其迅速。换句话说，你的层次结构很少会增加新的设备层级，但当它增加时，会在既有层级下增加大量的实例。你会拥有成千上万个 GPU，但在没有这些 GPU 之前，你并不需要那么多复杂的层级。

我们意识到可以利用这一特性来解决我们的问题。这带来了四个核心洞察：

第一个是**线性化器（linearizer）**。我的意思是，LLM 必须弄清楚这些设备是如何排布的，以及如何将模糊的用户查询映射到特定的设备或设备群组。在这里，我们系统图（graph）的简化表示（summarized representation）就变得非常有用。例如，一个 1吉瓦规模的工厂可能有超过一百万个节点，每个节点代表一个独特的设备。但是，因为你只想从根节点（root）寻路到叶子节点（leaf），你所要做的就是描述所有的路径，而这只是一个非常小且有限的列表。要定位到某一个 GPU，你只需要经过四个不同的层级；同样地，要定位到一个冷水机组或交换机，也只需要四个层级。有了这个机制，一个拥有 64 个 GPU 的系统和一个拥有 460,000 个 GPU 的系统所产生的结构摘要大小大致相同。这种整合的上下文向大语言模型提供了它所需的一切信息，使其能够理解工厂的布局以及不同设备在厂区内的分布情况。

第二个洞察是：**LLM 擅长规划，但不擅长检索（searching）**。这是我们在看到分片方案中极差的召回率时意识到的。因此，我们没有让 LLM 去过滤用户可能输入的各种模糊名字，而是要求 LLM 告诉我们**具体应该如何去寻找它们**。

举个例子，用户查询是：“帮我找出 11 号数据大厅里所有运行温度过高的 GPU。”大语言模型不需要去逐个查看我们所有 GPU 的名字来分辨哪些在 11 号大厅，也不需要自己去计算哪些正在过热。它只需要产生一个**结构化的输出**，告诉我们：首先，我们需要收集 GPU；其次，我们需要收集的范围是 11 号数据大厅这个子树（subtree）；最后，我们需要应用的过滤器（filter）是“运行温度过高”。根据不同的上下文，你可以实现不同的过滤器。我们唯一需要知道的，就是如何构建我们想要获取的这个目标集合。

第三个发现是，一旦你通过结构化输出来明确你需要什么，在后端为其构建执行逻辑就变得相对简单和直接了。现在，我们所要做的就是根据设备的位置以及它们与周围其他设备的交互方式，创建不同的设备子集——我们称之为**预索引树（pre-index trees）**。比如，从前页幻灯片中我们知道要查找 11 号数据大厅中的 GPU，我们可以直接在一个预索引子树中获取该大厅下的所有 GPU。接着，为了得到最终结果，我们只需运行一个查询来找出所有正在过热的 GPU，并求它们的**交集（intersection）**。**集合操作（set operations）**确保了无论用户在查询中如何进行过滤，或者他们的提问有多么模糊，我们都能获得完美的召回率和准确性。

第四个洞察是，如果用户的提问非常非常模糊，我们该怎么办？在这种情况下，我们必须让大语言模型参与检索，但不是直接在名称上进行模糊搜索，而是让大语言模型**为我们生成检索模式（patterns）**。这些模式可以是数据中的规律，但如果能在名称中发现命名规律，对于理清用户在谈论什么会大有帮助。通过这种方式，我们避免了将整个名字列表传递给 LLM。LLM 永远不需要处理海量的 Token，它只需要识别命名规范中的某些模式，理解用户的真实意图，创建一个检索模式，然后交由我们在后端执行。这确保了大语言模型在运行过程中的开销（Token 成本）是恒定的，或者说是相对平坦的。相反，如果我们必须让它读完所有内容，成本就会随着设备数量的增加而呈线性增长，而在系统规模扩大时，设备数量本身是呈指数级增长的。

总结一下端到端的处理流程：我们从用户的查询出发（查询可以针对单个设备或设备群），将其输入给规划器大语言模型（Planner LLM），规划器理解用户意图并给出一个检索规划（search plan）。基于该检索规划，我们通过**确定性解析器（deterministic resolver）**进行索引和集合操作，精确计算出我们需要的设备，生成最终映射用户查询的集合，这就是我们所说的结果集。整个过程是一个两到三步的流程，而不是一个可能会不断循环往复的多步智能体循环（agentic loop）。这也让我们的总成本保持在相对平坦和恒定的水平。

<details>
<summary>Original English</summary>

**Rahul Singh**: Now, what do we mean by tree depth is we realized that there's a hierarchical structure in which an AI factory is arranged. You will have data centers, then each data centers will have different data halls, you have each of them will have different aisles, and you will have different rows and then racks and then GPUs. Similarly, a chiller plant will have rooms where chillers are arranged, then you will have pumps. There will be a separate cooling tower unit. It's kind of like a tree. The depth of the tree grows very slowly, the width grows extremely fast. In other words, you will have a hierarchy that only adds new equipments very rarely, but it adds a lot of them when it does. You will have a lot of GPUs, but without GPUs, you won't have a lot of things. Now, we realized that this could be used to solve our problems. And there are four insights that really come into the picture for this. One is a linearizer. What I mean by the linearizer is the LLM has to figure out where each of these things are arranged and how to map from a vague user query to specific equipment or groups of equipments. Here a summarized representation of our system's graph can be really, really useful. For example, uh if you're a 1 gigawatt scale factory can have over a million nodes and each node represents a unique equipment. But, because you want to go from the root to the leaf, all you have to do is describe all the paths and that's a very small finite list. For example, here you can see that to get to a GPU, you can just you just need four different layers to get to it. To get to a chiller, similarly four layers to get to switches, similarly four layers. With this, 64 GPU system and a 460,000 GPU system produce roughly the same size of summaries. This consolidated context gives your LLM all it needs to know to figure out how the distribute how a plant is arranged and how different equipment are distributed in that plant. The second insight that we had was LLMs are good for planning but not good for searching. This is what we realized when we saw very poor recall with our sharded solutions. So, instead of making the LLM sift through all the different fuzzy names that we can get from our users, we asked the LLM to give us exactly how to look for them. So, for example, here the query says, "Give me all the GPUs that are running hot in data hall 11." The LLM does not need to go through all these names of all our GPUs to figure out which one of those are in data hall 11 and then figure out how they are running hot. All it needs to do is structured outputs which tells us that well, we need to collect GPUs. The scope under which we need to collect is a subtree which is just data hall 11 and the filter that we need to apply to finally figure out what exactly we need is GPUs that are running hot. Now, this can be different things depending on the context and you can implement different filters. All we need to know is how do we create the set that we want to know get to. The third thing that we realized is that once you have a structured output to figure out what exactly you need, building the back end for it is relatively simple and straightforward. Now, all we need to do is create different subsets of our equipment or pre-index trees as we like to call them based on their location and based on how they interact with other equipment around to get an idea of what you need to look at. So, for example, from the previous slide we saw that we wanted to look at GPUs in data hall 11. We could just get all the GPUs in data hall 11 in one pre-index subtree or other data halls, for example, or other racks, for example. And then to get to the final result, all we need to do is run a query to find all GPUs that are running hot and take their intersection. Set operations ensure that we have perfect recall and accuracy irrespective of how we want to filter the queries and what you know, fuzziness the user may have in their query. Next slide, please. Yes. And finally, what if you have something that is very, very vague? In which case, you have to get the LLMs to searching, but instead of searching directly over names, we figured out that getting the LLMs to give us patterns to look for. This could be patterns in the data but in the names can be much more useful to figure out what the user is talking about instead of just passing the entire name list to the LLM. The LLM never has to see very large number of tokens. All it needs to do is see some patterns in the naming convention, figure out what exactly the user is talking about, create a pattern, and then we can execute it on the back end on our side. This makes sure that the LLMs has a constant or relatively constant cost of operation. Whereas if we had to read through everything, we would have been scaling linearly with increasing equipment count, which itself grows exponentially as the size of the system increases. Finally, to process a user query end-to-end, we go from the user's query, which could be anything from one equipment or a group of equipment, to a planner LLM, which figures out user's intent and gives us a search pattern. Based on that search plan, we have a deterministic resolver, which indexes, does set operations, figures out exactly what we need to do, and creates the final set that maps to the user's query, and this is what we call the result set. All of this is a two or three-step process instead of a multi-step agentic loop, which can keep on running over and over again. And this keeps our total cost also relatively flat and constant.

</details>

### 评估结果与数据指标

**Vance Levstik**: 太棒了。如果说 Rahul 的工作是设计系统架构，那么我的职责就是确保它达到**生产就绪（production readiness）**状态。

我们需要确保无论设计多么优雅，这套解决方案在面对真实负载、真实客户数据以及只有在生产环境中才会遇到的各种混乱边界情况时，依然能够稳稳立得住。因此，在将这套系统交付给客户之前，我们对其进行了大量的测试和评估（evals）。我们让新旧系统在相同的 LLM 模型、相同的数据下进行了头对头的对比测试，并且每个测试用例运行了三次，以确保结果的可靠性。

我们的目标很简单：证明 Rahul 的设计已经为投入生产做好了准备。结果确实令人振奋。

如果我们来看一下具体的数据：
旧方案在规模扩大时性能下降得非常快。在只有 64 个 GPU 的规模下，它的正确率只有 80%；当 GPU 数量增长到 460,000 个时，正确率直接暴跌到了 30% 左右。相比之下，我们的新方案在所有测试中均保持了 **100% 的准确率**。

这不仅仅是在合成数据上的测试，在真实数据上也是如此。我们在 6 个真实的生产系统上测试了 66 个案例，同样录得了 **0 次失败**。

除了正确率的提升，新架构在资源消耗上也**显著更加轻量**。在 1吉瓦规模的数据中心进行单次验证运行时，旧方案消耗了高达 **1.16 亿个 Token**，而且依然伴随着很多错误。而新方案仅消耗了 **390,000 个 Token**，Token 消耗量减少了将近 **300倍**。

最关键的部分在于，Token 成本变得非常平坦。正如 Rahul 之前所言，尽管系统规模在不断扩大，但在 64 个 GPU 的系统和 460,000 个 GPU 的系统上，单次查询的成本都稳定在 **9,000 个 Token** 左右。这意味着当客户扩展他们的系统时，我们的运营成本不会呈指数级飙升，而是保持恒定。这就是这项改进带来的巨大影响力。

<details>
<summary>Original English</summary>

**Vance Levstik**: Cool. Yeah, if Rahul's job is to design the architecture, my job is production readiness. So, we need to make sure that whatever we designed, the elegant solutions we came up, actually hold up under real load, real customer data, and all the messy edge cases you only ever see production. So, before any of this went near a customer, we put it through some extensive tests and evals. We measured the new system head-to-head against the old ones with same LLM model, same data, and we did three runs per case just to make sure. Our goal was simple, prove that Rahul's solutions are ready for production. And they definitely are. If you look at some stats here, the old approach degraded pretty fast at scale. So, we got 80% correctness at 64 GPUs, and that dropped to about 30% when the GPU grew to 400 460,000. On the other hand, the our new approach has maintained correctness with 100% accuracy across all of those um tests that we give it. And this is not just synthetic test. Uh this is also a real data. So, we we had 66 cases on six real production systems and they product they produce zero failures as well. And not just correctness, it's also dramatically lighter. So, when we talk about 1 GW scale data center, the old approach burned 116 million tokens for just a single validation pass while still having a lot of errors. If you look at the new one, it's a 390,000 tokens, which comes to around 300 less tokens fewer tokens. But the part that matters the most, the cost is flat. As as Rahul was talking about before, the the system grows in size, but we the cost of the query was 9,000 tokens a query where the system was 64 GPUs or 460,000. So, instead of getting the cost grow exponentially w- when the customers grow their systems, it stays the same. That's the impact.

</details>

### 从 3.0 向 1.0 的反向演进

**Vance Levstik**: 接下来我想谈谈我们得到的启示，以及我希望大家能带回到自己工作中的核心思考。

这要从 **Andre Karpathy** 提出的一个视角说起。你们大多数人可能看过他的演讲，或者熟悉他关于软件分类的框架。

他提出了不同时代的软件定义。**Software 1.0** 是你编写的确定性代码。它是可预测的、精确的，但灵活性较差。另一方面，我们有 **Software 3.0**，它基本上是你通过向 LLM 发送 Prompt 从而引导出来的行为。在我们的案例中，这可能是“帮我找出 11 号数据大厅里所有运行温度过高的 GPU”。这非常灵活、智能，但略显模糊和不确定。

Karpathy 之前的观察是，在传统软件中，3.0 正在稳步吃掉 1.0。过去属于确定性代码的很多工作，现在正逐渐变成由 Prompt 来驱动。

请记住这个画面，因为对于全新构建的 AI 原生系统（AI native systems）来说，演进的方向可能恰恰相反。真正的技巧在于，**你需要知道哪些工作是 LLM 不擅长的**。

你应当始终将 LLM 用于它最擅长的事情。LLM 非常擅长解析模糊的请求、判断去哪里寻找数据、应该寻找什么、处理我们从未见过的用户新奇提问，以及在最后一步将结果合成并撰写成人类可读的回答。

但是，**任何你可以进行数据建模（data model）的部分，都应该移交给代码（Software 1.0）**。这在大型系统中尤为关键。如果你的数据本身具有结构——无论是层级结构（hierarchy）、图（graph）还是模式（schema）——让大语言模型去逐个 Token 地扫描它，绝对是错误的工具。

无论是精确检索、确定性的集合逻辑、计数、在几乎完全相同的名称之间进行去重（这在数据中心领域非常常见），还是任何必须保证 100% 可复现（reproducible）的任务，都应当由确定性的代码来处理。

一个简单的启发式规则是：**如果你能写下它的结构或规则，它就属于 Software 1.0 的工作。**

而纯大语言模型最脆弱的时刻，恰恰是系统规模巨大且结构良好的时候——这正好是我们和我们的客户所处的业务场景。

因此，从某种意义上说，我们把 Karpathy 描述的趋势反过来运行了。我们最开始几乎是纯粹的 3.0 方案。我们把所有内容都塞进上下文窗口里，因为这是搞清楚什么东西值得构建的最快方式。正如我们所说，这在最初的简单 demo 上跑得很好。然而，当系统必须真正扩大规模时，我们将那些可以作为已知工程问题处理的部分，全部移回到了 1.0 中。我们仍然在 LLM 中保留了核心的理解与规划决策。

这就是我们所说的“反转（inversion）”。传统软件从 1.0 漂移向 3.0，而全新的 AI 原生软件则从 3.0 开始，并随着用例的成熟，向着 1.0 的方向逐步完善。

我们不是要取代模型的主观判断。我们希望为模型提供我们所称的 **1.0 工具**。你添加的每一个 1.0 函数，都是让大语言模型立足的更为可靠的基石。

总结一下：让 LLM 保留困难的规划与意图决策。而对于它不应该靠“猜测”来完成的每一项工作，请将其作为代码（Software 1.0）加入，并将这套确定性的结构交还给大语言模型来协同工作。通过 Software 3.0 快速开发，并通过引入 Software 1.0 实现生产化。

感谢大家的观看。如果有任何后续问题，可以通过电子邮件联系我们：Rahul 的邮箱是 `rahul@phaidra.ai`，Vance 的邮箱是 `vance@phaidra.ai`，或者也可以在视频下方的评论区留言。

<details>
<summary>Original English</summary>

**Vance Levstik**: Now, there's something about uh what we learned and the part I want you to take back to your own work. It starts with a lens from Karpathy. Most of you have probably seen his presentation or his framing talk about this before. He talks about different kinds of software. Software 1.0 is a deterministic code you write. It's predictable, exact, but a lot less flexible. On the other hand, we have software 3.0, which is basically a behavior you prompt out of an LLM. In our case, that might be show me the GPUs in data hall 11 that are running hot. This is very flexible, smart, but it's a bit fuzzy. Now, his observation was that in legacy software, the 3.0 is steadily eating 1.0. More of what used to be deterministic code becomes a prompt. Just hold that picture because the lesson for new built AI native systems runs a little bit the other way. But the real skill is knowing which work is the LM not best for. And you always want to keep the thing the LM should be used for the things that it does well. It's great at parsing ambiguous requests, judging where to look for data and what to look for, handling phrasing we've never seen from a new user that has a different query, and at the end also synthesizing and writing the final human-readable answer. But everything you you can data model, you should move into code. This is the key one especially for large systems. If your data has structure, call it a hierarchy, graph, or a schema, a language model scanning it token by token is definitely the wrong tool. Both retrieval, exact set logic, counting, dedup across near identical names, which happens a lot in the data center land, anything that must be 100% reproducible, it should be a deterministic code. The simple heuristic that usually works, if you can write down the structure or the rules, it's a 1.0 job. And pure LM is weakest exactly when the system is large and well structured, which is precisely where we operate and our customers. So, in a sense, we ran Carpathia's trend backwards. We started almost pure 3.0. We threw everything in the context window because that is the fastest way to find out what's even worth building. And as we said, it worked pretty well on a simple demo to start. Then, as it had to really scale, we moved the parts that can be treated as known engineering problems into 1.0. And we still kept the hard judgment in the LM. So, that's the inversion. Legacy software drifts from 1.0 towards 3.0 and new AI native software starts at 3.0 and matures towards 1.0 for the use cases that earn it, of course. We are not here to replace model judgment. We want to feed it with the 1.1.0 tools, as we call it. So every 1.0 function you add is more reliable ground for the LLM to stand on. So to finish up, let the LLM keep the hard decisions. Everything it shouldn't be guessing on, add add it in as code and hand that structure back to the model to work with. So develop with software 3.0, productionize by adding in software 1.0. Thanks for watching everyone. Uh any follow-up questions at all, you can reach us by email Rahul Russell Google at fidra.ai, Lanza at least to get fidra.ai, or you can drop them in the video comments below.

</details>

**Rahul Singh**: 谢谢大家的观看。

<details>
<summary>Original English</summary>

**Rahul Singh**: Thank you for watching.

</details>

**Vance Levstik**: 谢谢。

<details>
<summary>Original English</summary>

**Vance Levstik**: Thanks.

</details>