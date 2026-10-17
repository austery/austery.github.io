---
author: AI Engineer
date: '2026-06-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pSto5YaNGUo
speaker: AI Engineer
tags:
  - agentic-loop
  - automated-evaluation
  - root-cause-analysis
  - ai-agent
  - software-engineering
title: AI 智能体工程的未来：构建自主优化的智能体开发循环
summary: 本访谈由 Mutagent 联合创始人 Bene 与 CTO Burak 深入探讨 Agentic AI Engineer（智能体 AI 工程师）的架构与落地。详细解析了从 Spec 设计、构建、评估、上线监控到故障诊断及自动优化循环的完整生命周期，并演示了 Mutagent 如何通过评估智能体和诊断智能体实现流程的自动化与闭环优化。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Mutagent
products_models:
  - LangFuse
  - Whisper
media_books: []
status: evergreen
---
### 双循环机制介绍

**Bene**: 大家好，欢迎来到我们的演讲，今天的主题是**智能体 AI 工程师**（The Agentic AI engineer）。我是 **Bene**，**Mutagent** 公司的联合创始人兼首席执行官，今天我和我的同事一起在这里与大家分享。

<details>
<summary>Original English</summary>

**Bene**: Hi everybody. Welcome to our talk the Agentic AI engineer. I'm Bene. CEO and co-founder of Mutagent and I'm here with my colleague.

</details>

**Burak**: 嗨，大家好，我是 **Burak**，我是 Mutagent 的首席技术官。今天我们基本上要讨论的是**循环**（Loops）以及智能体 AI 工程师是如何工作的。

<details>
<summary>Original English</summary>

**Burak**: Hi, I'm Burak. I'm the CTO of Mutagent and today we're basically going to talk about loops and how the Agentic AI engineer works.

</details>

**Bene**: 正如大家现在所意识到的，循环是目前如何构建智能体循环软件的热门话题。我们也将同样的循环概念应用到构建 **AI 智能体**（AI agents）上。如大家所知，这里有两个核心概念：一个是**离线循环**（Offline loop），即在构建阶段，你对智能体进行迭代、测试、评估和改进，如此循环往复；然后是第二个循环，我们称之为**在线循环**（Online loop），一旦智能体部署到生产环境，你就需要监控其运行轨迹（traces），进行诊断，然后将诊断结果反馈到优化循环中，通过不断迭代来产生智能体的多个版本。

在此之前，我们所做的一切工作基本上都是通过**手动方式**来运行这个循环的。这显然非常缓慢。其生命周期基本上是：当发现问题或想要对智能体做出某种改变时，你必须手动去实现这种变更——如果是使用编码智能体，或许可以通过它们来完成这一步。然后，你可能会生成一些测试样本来验证这个新功能或解决的问题。接着，你需要查看运行结果，仔细分析其轨迹，看看最终输出的实际效果如何。之后可能还会发布它，进行 **A/B 测试**，但所有的反馈基本上都是手动收集的，这需要耗费极长的时间。最终，**人工审查**（human review）以及**人工构建时间**（human building time）就成了整个流程中最大的瓶颈。特别是如果你的组织并不打算规模化部署数以百计的智能体，人工方式就完全无法扩展。这也正是为什么我们认为智能体 AI 工程师是构建智能体的必然发展趋势。接下来我将让 Burak 深入探讨我们如何通过智能体 AI 工程师来缩短开发耗时，并提高生产环境中的可靠性。

<details>
<summary>Original English</summary>

**Bene**: So, as you all are aware of now, loops is the hot topic how you build software in an Agentic loop. And we apply the same loop to the building of AI agents. And as you all aware, there is uh two concepts here. One is the offline loop where while you build, you iterate um on your agent, you test it, you evaluate it, you improve it, and you go on. And then you have a second loop which is we call the online loop where once the agent is deployed to production, you monitor its traces, you diagnose it, and then you feed it back into your optimization loop uh yeah, to iterate and have multiple versions of your agents. Yeah, up to until now um what we did was uh just doing this loop manually. It's quite slow. Um the life cycle is basically um you have an issue, um you want to change something to your agent. Um yeah, you implement the change. Um [snorts] you maybe vibe implement the change if you use coding agents for it. Um yeah, you generate some samples for this new feature or issue to test it. Um yeah, then you look at the result, you look through the traces, how does the outcome look like. Then you maybe ship it, you do AB testing, and all your feedback is kind of manually, it takes very long. Um yeah, and the the bottleneck basically becomes the human review and the human yeah, building time. And yeah, that you can't scale especially if in your organization you're not planning to roll out hundreds of agents etc. Yeah, and uh yeah, this is why we think the Agentic AI engineer is the natural next step to build agents. And I'll have Burak deep dive into how we improve timing and the road to production reliability with the Agentic AI engineer.

</details>

### 提升开发吞吐量

**Burak**: 好的。这里的核心关键在于，一旦你的智能体数量或者基于 AI 的功能模块达到一定规模，由人类来执行这一闭环过程在时间上是完全无法扩充和应对的。因此，**通过智能体来实现这个循环的自动化**是提高整体吞吐量的关键，因为这样你就可以在相同的时间窗口内塞进多得多的迭代周期。

这个循环的工作方式基本上包括以下几个阶段。首先，当你从零开始构建时，这与当前的软件开发实践非常相似：你需要先为你的智能体（在这种情况下，指的就是它的某项技能）创建一个**规格说明书**（Spec）。在这里，你需要清晰地定义该智能体需要处理的所有职责和功能，以及它在特定条件和状态下必须做出的决策。需要强调的是，这仅仅是定义阶段。

一旦你定义好了智能体的需求，接下来就可以进入**构建阶段**（Build）。在构建阶段，你会在特定的测试套件、智能体框架中去实现该 Spec 的要求。在当前的技术背景下，你甚至可以直接将其构建为**云端代码**（cloud code）或是 **Codex 智能体**（Codex agent）。

紧接着是下一步，即定义清晰的**评估体系**（Evaluations），以评估智能体的性能。因为这些是核心关键指标，能够明确告诉你“我的智能体是否功能正常”。这在本质上相当于写代码时的**单元测试**（unit tests），是你验证智能体是否正常工作的手段。

评估之后，如果一切看起来都很好，就进入**发布阶段**（Ship），基本上就是将该智能体部署到生产环境中。这同样可以是一个代码更新过程，或者是在任何智能体平台甚至本地测试环境中的直接更新。

随后进入在线部分。在生产环境中，智能体将被持续监控以发现问题，并在满足特定触发条件时自动启动**诊断程序**（Diagnostics）。触发条件可以基于智能体生成的运行轨迹数据量，也可以是每周或每日的定时任务。

然后我们进入**诊断阶段**（Diagnosis）。在这一步中，你会收集智能体的所有失败案例，进行结构化的**根因分析**（Root cause analysis），从而了解失败到底源自何处。

一旦你理解并对这些失败进行了分类，就可以最终进入**优化阶段**（Optimization）。在这里，你会针对智能体生成非常具体的修改或**突变**（mutations），以应对发现的失败模式（failure modes）。

随后，整个循环再次重复：重新评估，如果一切顺利，就可以再次部署。现在，我们接下来将对每个阶段进行更深层次的拆解，看看具体包含了什么。

<details>
<summary>Original English</summary>

**Burak**: Uh so, yeah, the key thing here is basically once you reach a certain number of agents or AI-based features, the human performing this loop again cannot really scale in enough time. So, this is why doing this agentically is the key to increasing the throughput because then you can fit many more cycles into the same time window. And now how that loop works is basically we have a few stages. So, this is when you are starting from scratch like the current software development practices, you first create a spec for your agent or your skill in this case. And here you need to define all the responsibilities and the functions that agents needs to handle, the decisions that it has to make on certain conditions. And here again, this is only the definition stage. Once you defined your agent's requirements, then you can finally go on to the build. And build is where you then realize that spec in a specific harness or uh agent framework or in these days you could even build it as a cloud code or a codex agent. Then comes the next step. This is where you define clear evaluations to evaluate your agent's performance because these are the key metrics then where you can say, \"Hey, my agent is functional or not.\" Uh can think of essentially the equivalent to unit tests for coding. This is how you verify your agent works. Then after evaluation, if everything looks fine, you usually have the ship basically where you deploy this agent to production. Uh again, this can be a code update. This can be a direct update on a any agent platform or again your local harness agents. Then comes the online part. This is where then the agent is continuously monitored for issues and based on certain trigger conditions, then you can start automatic diagnostics. Again, this can be based on the volume of traces that your agent generates or, you know, weekly or daily jobs. Uh then we go into diagnosis stage. This is where you collect all the failures for your agents and do structured root cause analysis to then understand where the failures are coming from. Once you understand and categorize the failures, then you can finally go on to the optimization stage. This is where then you create, let's say, very specific changes or mutations for your agents and to deal with the found failure modes. And then the whole cycle repeats again. You evaluate and if everything looks good, then you can deploy again. Now, we will maybe do a deep dive on each stage, what that entails. Then

</details>

### 新旧功能开发路径对比

**Bene**: 在我们继续之前，Burak，我们这里有两条路径。一条是**冷启动路径**（cold start path），另一条基本上是针对**已有功能**（existing features）的迭代。我们能花半分钟左右的时间深入探讨一下这两者有什么区别，为什么这一点很重要吗？

<details>
<summary>Original English</summary>

**Bene**: So, before we continue, Burak, um we have two passes here. Like one is the cold start path, and one is basically existing features. Um should we dive deeper for like a half a minute on what differences here, what we see, and why this is important. Yeah.

</details>

**Burak**: 好的。如果今天你坐下来构建一个智能体，显然有两种选择。要么你已经拥有了一个现成的智能体，它已经被构建并在某处运行，且具备一定的准确率；要么就是你正在从零开始全新创建。所以，当你从零创建时，显然必须从 Spec 设计和概念化阶段开始。而如果你面对的是一个已有功能，智能体已经存在了，你所做的就是在一个已有的基础之上进行优化。

<details>
<summary>Original English</summary>

**Burak**: Yeah, so today, if you again sit down to build an agent, there are, you know, two options. Either you already have an agent, it's built, it's already running somewhere with um, you know, certain accuracy. However, the other option is again you are creating from scratch. So, when you create from scratch, obviously you design with the spec and the conceptualization stage. If you have an existing feature, the most likely again the agent is there, but then you are optimizing over something that already exists.

</details>

**Bene**: 好的，明白了。那我们接下来就深入讨论每个阶段。你刚才提到了新智能体的 Spec 制定，这似乎是一个非常重要的产物，让我们深入剖析一下。

<details>
<summary>Original English</summary>

**Bene**: Okay, cool. And [snorts] Yeah, let's dive deeper into each phase. I mean, you just mentioned the specking of new building agents, so this seems to be an important artifact, so let's dive into it.

</details>

### Spec驱动与目标平台隔离

**Burak**: 好的。在**规格说明书驱动的开发**（Spec-driven development）中（这在如今构建软件产物或运行任何编码智能体工作流时也非常普遍），其核心目标是捕获对智能体的需求，尤其是**成功标准**（success criteria）。其原因在于，除了通用的编码智能体之外，其他领域的智能体通常需要处理非常具体的业务流程，而这在不同的公司之间是各不相同的。因此，它对于智能体所处的具体环境来说是非常特异和定制化的。这里的关键点在于要清晰地定义智能体拥有哪些上下文需求、需要接入哪些集成模块和工具、它的职责或必须完成的任务是什么，以及它不应该处理哪些事情。最后，还要明确智能体的约束条件和整体边界。

<details>
<summary>Original English</summary>

**Burak**: Right. So, with the spec-driven development, also prevalent for building software artifacts these days, or any kind of coding agent workflows, basically the goal is to capture the requirements for the agent, and especially the success criteria. The reason being, apart from coding agents, the agents in other domains they handle specific processes and this differs from company to company, so it's very specialized to the environment where the agent is in. And then the key point here is to clearly define which context requirements that the agent has, again which integrations and tools it then needs to have. What are the jobs to be done or the responsibilities that the agent will handle and what it will not. And then finally again the constraints and in general the boundaries for the agent.

</details>

**Bene**: 明白了。

<details>
<summary>Original English</summary>

**Bene**: Okay.

</details>

**Burak**: 一旦我们定义了清晰的 Spec，它就会成为未来任何开发的**蓝图**（blueprint），后续的实际实现方案都需要对照它来进行衡量和验证。

<details>
<summary>Original English</summary>

**Burak**: Now once we can define a clear spec as I said it becomes like a blueprint for any future development which then the implementation is held against.

</details>

**Bene**: 明白。那我们接下来如何根据这个 Spec 来构建智能体呢？

<details>
<summary>Original English</summary>

**Bene**: Okay. And let's dive into how we would then build an agent from the spec, right?

</details>

**Burak**: 基本上，这个 Spec 会告诉你的编码智能体应该去构建什么，在此过程中，**目标平台**（target platform）的选择完全取决于你。因为正如我提到的，智能体领域目前变化极其迅速，你今天使用的框架，可能在一年左右之后就想替换掉。基于这个原因，Spec 的定义与具体的实现细节是相互隔离的。一旦你决定好了，你可以挑选任何目标。此时你所选择的编码智能体就会拿着这份 Spec，为你提供该智能体的初始版本，然后你就可以根据需要对其进行自定义，使其运行在任何你认为合适的平台上。

<details>
<summary>Original English</summary>

**Burak**: Right. So basically then the spec tells your coding agent what to build and then here the target platform choice is entirely yours. Cuz as I mentioned agent space is very changing very rapidly these days. So the framework you are using today, you might want to change, you know, in a year or so. So essentially because of that spec is isolated from the implementation details. So once you decide to you can pick any target. Here then your coding agent of your choice will take that spec and give you a, you know, initial version of that agent, which is then basically customized to run on any platform that you see fit.

</details>

**Bene**: 为什么我们会在一年后想要更换平台？从过往的经验中我们学到了什么？

<details>
<summary>Original English</summary>

**Bene**: Why would I want to change the platform in a year down the line? So, what what what did we learn out of experience here? Um

</details>

**Burak**: 根据我们过去三年构建智能体的经验，有时候特定的智能体框架或开发套件并不总是具备所需的能力。偶尔你会遇到瓶颈或障碍，此时你不得不依赖底层框架来试图消除这些障碍，这往往需要花费不少时间。因此，关键在于保持**灵活性**（flexibility），你需要选择最能满足你业务需求的框架或开发套件。

<details>
<summary>Original English</summary>

**Burak**: Uh again building agents for the last 3 years, sometimes the agent framework or the harness does not always have the capabilities. So, occasionally you hit um like a bottleneck or a roadblock, and then you have to rely on the underlying framework to kind of get rid of that, and this can sometimes take a while. The key here is to be flexible because yeah, essentially again, it you want to pick the best harness or the framework that can, you know, fulfill your requirements.

</details>

**Bene**: 确实如此。我们在过去的几个月里都目睹了这一点，许多新的开发套件相继发布。智能体构建代码的方式，正在向着定义明确的智能体循环运行时的方向演进。我们看到了 **Hermes**、Deep Agents 等各种框架的兴起。

<details>
<summary>Original English</summary>

**Bene**: Mhm. I mean, we've all seen it in the in the last months, we how new harnesses shipped and yeah, how everything went from like a agents building code towards yeah, defined as like a agent loop run time. I mean, we've seen Hermes coming up, deep agents, and all of these frameworks, right?

</details>

**Burak**: 是的。

<details>
<summary>Original English</summary>

**Burak**: Yeah.

</details>

**Bene**: 好的，那我们继续。构建完成之后会发生什么？

<details>
<summary>Original English</summary>

**Bene**: Okay, let's continue. What happens after build?

</details>

### 评估驱动的发现过程

**Burak**: 在完成构建之后，对于智能体开发而言，你基本上会进入我称之为**评估驱动的开发**（Eval-driven development）循环。这在本质上相当于传统软件开发中的**测试驱动开发**（Test-driven development, TDD），因为智能体需要一个终止条件。一个 AI 功能或者一个智能体在什么阶段才算是“足够好”了？

这里同样有两种方式来构建你的**评估套件**（Eval suite），它由评估指标、评估标准以及数据集本身组成。数据集通常包含了智能体必须要满足的所有测试用例。

在最开始，传统的选择是你和你的**领域专家**（domain experts）坐在一块，尝试写下能够覆盖你想要构建的功能或智能体的评估指标和标准。但大多数做过这件事的团队都会知道这非常困难，因为你**无法在最开始就预判出完整的评估套件**。

其次，你可以始终从历史数据或者已知的数据样本中合成数据，来对智能体进行测试。但本质上，一个真正且完整的评估套件是一个**探索和发现的过程**（product of discovery）。这意味着随着时间的推移，通过用户反馈和生产环境的失败案例，你不断收集指标、评估标准以及额外的数据集案例。这些案例往往代表了智能体需要处理的**边缘案例**（edge cases）或极具挑战性的困难案例。通过这样的方式，你最终拥有了一个完备的评估套件，能够运行智能体并精确指出它在哪些地方失败了。

<details>
<summary>Original English</summary>

**Burak**: Now, after you build for agents, you essentially go into the eval-driven development loop, which I would call. And this is kind of equivalent to test-driven development for building software with agents because then the agents needs uh termination condition, right? So, when is an AI feature or an agent is good enough? So, here again there are two ways to kind of create your eval suite, which is composed of the evals like the metrics and the criteria you evaluate. And the data sets themselves, which usually contain the cases you have to satisfy. Now, in the beginning, the original option is that you can sit with your domain experts and then try to write down eval metrics and criteria that would cover the feature or the agent you want to build, but most teams working on that will already know that this is a bit difficult as in you cannot pre-guess the entire evaluation suite from the beginning. And secondly, you can always start with historical data or synthesized data from a known you know, sample of the data that you would like agent to be tested on. But essentially, the real and the complete eval suite is a product of discovery. What that means is over time, from user feedback, from production failures, you collect the metrics and criteria plus the additional data set cases, uh which is often representative for edge cases or you know, hard cases that the agent needs to deal with. And with that, then you finally have an evaluation suit where you can run the agent against an exactly know where it fails.

</details>

**Bene**: 在我们继续之前，为什么智能体 AI 工程师在这里能给我们带来这么大的帮助？我们这里显然在讨论**评估智能体**（evaluator agent），在开发中引入这种概念或思维方式有什么好处？

<details>
<summary>Original English</summary>

**Bene**: Okay, before we continue, why does the Agentic AI engineer help us here so much? So, um obviously we're talking about the evaluator agent. So, why is it so why is it so why is it so good to use this kind of concept or thought process in the building?

</details>

**Burak**: 假设你的数据集包含 200 个样本。在没有自动评估的情况下，运行这些样本并纯靠人工肉眼去逐个评估会耗费极长的时间。你必须不停地滚动查看观测仪表盘和日志，这反过来会极大拉长每个评估阶段的循环耗时。因此，一旦你需要评估和实验的功能模块变多，想要快速或并行地完成这一工作就变得完全不可能了。此时，**人就成了最主要的瓶颈**。

<details>
<summary>Original English</summary>

**Burak**: Well, I mean one issue is again, imagine you have a data set item of 200. Here, without automated evals, running this and evaluating by like human eyes takes quite a while. Um you would have to again scroll through an observability dashboard and logs and this in turn increases your loop time per eval state. So, as soon as you have a lot of features that you need to evaluate and experiment on, then it suddenly becomes impossible to, you know, do this quickly or in parallel. Then the human essentially becomes the bottleneck.

</details>

**Bene**: 明白。所以我们其实就是让一个智能体来承担筛查运行轨迹的繁重工作。

<details>
<summary>Original English</summary>

**Bene**: Okay. So, we just have an agent do this work in sifting through traces.

</details>

**Burak**: 是的。正如当前时代所提倡的，你为你的智能体设计闭环，以便它们能够在后台自动处理这其中的大部分事务。而你的工作就转变成了去设计这些带有清晰评估指标或终止条件的循环。

<details>
<summary>Original English</summary>

**Burak**: Yes, as the current era says a bit, you know, um you design loops for your agent so then they can autonomously work as many of these things in the background. Uh and then your job becomes designing these loops with a clear eval or termination gate.

</details>

**Bene**: 明白。那我们来看一下一个好的评估套件应该如何构建，它究竟评估了哪些东西？

<details>
<summary>Original English</summary>

**Bene**: Okay. Understood. So, let's look at the how good eval uh supposed to be constructed and what it kind of evaluates.

</details>

### 轨迹评估与指标标定

**Burak**: 好的。对于智能体而言，其**运行轨迹**（trajectory）非常重要，因为智能体接收输入、意图或任务，并在特定的系统提示词或决策树之上运行。在进行智能体评估时，我们首先要检查的是：“上下文是否完整？”也就是说，智能体是否拥有执行端到端任务所需的全部上下文信息？这也包括检查运行轨迹中的每一次工具输出，因为会话中任何错误的工具输出，最终都可能导致错误的最终输出。

除了这些，还有不同的维度可以用来进行评估。在当下，智能体运行的底层开发套件或框架，对智能体的行为有着巨大的影响。这也是另一个需要优化的维度。但归根结底，当你评估一个智能体时，你需要通盘考虑所有的这些因素，而不是把它们割裂开来进行孤立评估。

<details>
<summary>Original English</summary>

**Burak**: Right. So, in the context of agents in general, the mainly the trajectory is important because agents receive input or let's say intent or tasks and then they have a specific system prompt or like a decision tree that they kind of operate over. And when doing agent evaluations, again in general, we check, \"Hey, was the context complete?\" As in, did the agent have all the required context to perform the task end to end? Then this includes also chain checking every, you know, tool output in the trajectory because every wrong tool output in session can in the end lead to our wrong output as the final output. And apart from that, again, there are different things you can evaluate on. So, these days also the harness that the agent is operating on has quite drastic effects on the agent behavior. And this is again another vector of optimization. But in the end, when you evaluate an agent, you would like to evaluate all of these things and not something in just isolation.

</details>

**Bene**: 的确。

<details>
<summary>Original English</summary>

**Bene**: Mhm.

</details>

**Burak**: 好的。一般来说，是什么让评估指标真正发挥作用？你固然可以采用 **LLM作为裁判**（LLM as a judge）的方式，让它给你打一个分数。但是为了让评估真正有用，它必须能够**提供可落地的反馈**（actionable feedback）。

如果你使用的是基于评分的评估，除非你的评分细则定义得极其精确，否则它无法明确告诉你到底需要修复什么。在这样的情况下，采用**二分类评估**（binary evals）或标准是更推荐的做法，因为这种方式能直接带来明确的待办事项。如果某项标准未通过，你能够准确知道发生了什么以及该如何解决这个问题。

此外，你的“LLM作为裁判”方案必须经过**标定与校准**（calibrated），以消除不同裁判之间的打分噪音。由于大语言模型本身是不确定性的，你最常遇到的问题是同一个裁判在不同的运行周期中，对同一个问题的评估结果大相径庭。你必须确保你的“LLM作为裁判”方案能够妥善处理这种打分波动问题。否则，你就很难开展实验并给出确凿的结论，无法判定你的改进版本是否真的优于智能体的初始版本。

<details>
<summary>Original English</summary>

**Burak**: Right. And in general, here, what makes an eval useful? So, you can always have you know, metrics or evals that are working in a LLM as a judge fashion and give you some score, but here, in order to make an eval, you know, useful, it has to provide actionable feedback. Uh, as in when you use score-based evals, unless your rubric is very well defined, then this does not exactly tell you what to fix. Uh, in such cases, using uh, binary type of evals or criteria, is preferred because there you have a kind of a call to action. If an eval or a criteria fails, then you know exactly what happened and how to kind of deal with that problem. Then, uh, another point is your LLM as a judge solution should be calibrated so that you don't have the, uh, scoring noise between judges because since LLM LLMs are undeterministic, what you will mostly encounter is the same judge can, uh, evaluate a problem different ways on each run. And then here, you have to make sure your LLM as a judge solution deals with this variance problem. Otherwise, it's hard to run experiments and conclusively say, \"Hey, my initial or my improved version is better than my initial version of my agent.\"

</details>

**Bene**: 明白。

<details>
<summary>Original English</summary>

**Bene**: Mhm.

</details>

### 在线诊断与失败模式聚类

**Burak**: 是的。在评估之后，我们基本上就会上线。在生产环境中，我们会收集学到的失败案例、失败模式，并从执行过程中获取主要的信号。

这里的核心思想是，当一个智能体随着时间推移遇到问题时，这些问题很可能会重复发生。因此，第一步是识别智能体遇到了哪种失败模式，然后**按根因以及它们的源头进行聚类**。这可能源自智能体提示词的某个部分、缺失的工具，或者是运行异常的工具。

在对诊断结果进行分类之后，你就可以生成新的评估用例。首先，用来检测这些问题；其次，基于这些问题来生成改进方案和补救措施。随着时间的推移，你就积累起了这些学到的失败模式库。因此，每个智能体都能逐渐积累起可供随时校验的历史数据。

在开始进行诊断时，前期可能会有一定的成本，因为你通常需要深度阅读 LLM 运行轨迹来查明发生了什么。但久而久之，你可以为每种失败模式收集**可通过代码直接校验的指标**（code-checkable indicators）。这意味着，通过特定的内容片段或特定的工具调用序列，你就能知道智能体会在哪里遇到问题。这在后续能够帮助你直接从轨迹中诊断问题，而不需要实际去人工阅读所有的轨迹。

为什么直接阅读所有轨迹是个问题？因为如果你拥有数以百万计的智能体运行轨迹，人工去阅读这所有的内容，其花费实际上可能比执行本身的成本还要高。因此，这绝对不是诊断问题最有效率的方式。你的目标应该是通过**智能细分策略**（intelligent segmentation strategies）并结合已有的特征指标，从海量轨迹中筛选出最具代表性的样本来进行诊断。

<details>
<summary>Original English</summary>

**Burak**: Right. Uh, after then evaluation, basically, we go live and this is where then, uh, collecting, let's say, learned failures, failure or primary signals from the execution takes place. Um here the idea is again when an agent encounters a problem over time, there will most likely be multiple occurrences of these. So, it starts by identifying what failure mode uh that the agent has encountered and then grouping essentially these failure modes by the root causes and where they originate from. Again, this could be a section in the agent prompt. This could be missing tools or, let's say, malfunctioning tools. But, after your diagnostics results are categorized, then you can finally generate new evaluations. First, to detect these problems. And then, second, you can generate improvements and remedies based on these problems. And yeah, with that, over time, you have um build-up of these learned failure modes. So, then every agent over time uh gathers these historical data that it can always check against. When you uh start diagnosing, there's a bit of a upfront cost in the beginning because you often need to deep read the LLM traces to find out what's going on. Over time, you can collect code-checkable indicators per failure mode. What that means is there are maybe specific pieces of content or there's a specific tool called sequence where you know that the agent will encounter an issue and then this later on helps you to diagnose problems in your traces without actually having to read through all your traces. Now, why is that a problem? Because if you have let's say millions of agent traces and to read all of these uh it actually costs more than the execution itself. So, it's not the most efficient way of diagnosing the problems. Uh what you want to aim for is again try to uh pick a representative sample from your um whole traces by you know intelligent segmentation strategies and using again as I said the learned indicators.

</details>

**Bene**: 好的，非常好。

<details>
<summary>Original English</summary>

**Bene**: Okay, cool.

</details>

**Burak**: 基于这些诊断，你就可以最终开始构建**自主优化循环**（autonomous optimization loop）。因为既然你已经拥有了评估套件，你就可以调整你的功能模块，甚至运行自动化的探索式实验，来看看是否能够达到评估套件所设定的目标分数。只要能够达到这个目标分数，它就可以自动部署到生产环境中。

之后，从生产环境中你又得到了你的外循环。同样地，在诊断过程中发现的每一个问题都会为你提供一个改进方案或补救措施。只要评估套件的测试全部通过（变绿），它就会被再次部署到生产环境中。

<details>
<summary>Original English</summary>

**Burak**: And then with that you can finally start building the autonomous optimization loop because here then given that you have a eval suit, you can you know vary your feature again update certain or even run auto research style experiments to see that whether you can reach the desired or the target scores for your evals. As long as you can reach that then it's automatically shipped to production. Then from production you have your outer loop. Again, every issue that's found then on diagnostics gives you a improvement or a remedy which then you can optimize on and then as long as the eval suite is green then this again gets deployed to production.

</details>

### 端到端智能体闭环生命周期

**Bene**: 好的，我们现在来梳理一下整个生命周期。正如我们所学到的，一切都始于 Spec。你定义并设计它，然后构建你的智能体，所有这些显然都可以通过智能体化的方式来自动完成。你可以定义专门负责处理这些工作的智能体，它们结合起来就构成了智能体 AI 工程师。

然后，你通过离线循环，基于构建好的评估系统，在你的测试数据集上评估、优化、测试并提升你的准确率。一旦准备就绪，你就将其部署到生产环境中。

这便是在线循环的起点。在这里，你会获得来自用户的真实反馈。你复盘测试用例，持续监控它们，查看实时运行轨迹，并正如我们之前学到的，使用诊断智能体来进行诊断、执行根因分析、对你的失败模式进行聚类。接着，你将从中推导出新的评估指标，它们将成为 Spec 以及智能体的一部分。这意味着，当你在生产环境中使用智能体时，它会伴随你一起持续成长。

随着你收集的用例越来越多，看到的生产环境数据越来越丰富，你的智能体就会变得越强大，其评估得分也会越来越高。所有这些流程结合在一起，就构成了一个你可以智能体化运行的端到端闭环。你可以将这些概念应用到 AI 工程和构建 AI 智能体中。

接下来，我们在 Mutagent 正在推进这项工作，我们将向大家展示这套系统在实际产品中是如何呈现的。

目前，整个系统都是运行在你的本地环境中的。我们支持云端和本地部署，并且未来将提供托管服务。这实际上是一套智能体系统，目前我们有两款智能体处于研究预览阶段。我们在本次演讲中也重点讨论了它们。

第一个是**评估智能体**（evaluator agent），它帮助你构建评估集和高质量的数据集，因为这是整个优化和评估驱动开发循环的核心。

第二个是**诊断智能体**（diagnostics agent），它帮助你诊断生产环境中已有的运行轨迹。因为我们从用户那里了解到，阅读和分析这些轨迹要耗费他们大量的时间，如果能够直接在他们的代码开发环境中启动智能体来分析轨迹，对他们来说是非常有帮助的。

如你所见，这两个智能体都是通过一个运行在你的编码环境中的**编排器**（orchestrator）进行连接的。你所需要的只是连接到你存放所有轨迹和记录事件的数据源。这可以是像 **LangFuse** 这样的观测平台，也可以是你本地的云端日志，或者是从其他平台导出的 JSONL 格式文件。这基本上就是我们平台的工作原理，我们启动不同的智能体，它们连接到同一个编排器。Burak，让我们向观众展示一下我们在研究预览版中的第一个智能体吧。

<details>
<summary>Original English</summary>

**Bene**: Let's continue now with the whole life cycle. Um yeah, as we learned now the details of each everything starts with a spec. Um you define and design it. Uh you build your agent and all of this can be done obviously agentic. So you define agents that do this work. And then they all together become uh the agentic AI engineer. Um you go through the offline loop where once you build your evaluation system uh yeah, you evaluate, you optimize, you test, you improve your accuracy on your test data set. Once you feel ready, you deploy it to production. And that's when the online loop starts. Here you get real feedback from users. Um yeah, uh you review the test cases, you continuously monitor them, you look at your live traces, you diagnose them as we learned before with the diagnose agent you can do root cause analysis, you can cluster your failure modes. Uh you'll derive new eval criteria from it. They become part of the spec. Uh they become part of the agent. So they they continuously grow with you while you use your agent in production. And uh yeah, this becomes the online loop. And the more use cases you collect, the more is production data you see, the better your agent becomes and the better scoring your agent becomes. And this all together now um becomes one end-to-end loop that you can run agentic. And uh yeah, from here on uh yeah, you can now see the combination to software-driven development with coding agents. You can transport this concepts also for AI engineering and building AI agents. And uh now, as we at Mutagen work on this, we're going to show you now how this looks like as a product. Um This is kind of how it looks like. Um for now, everything runs in your environment. And we it as cloud and local, um we'll offer a managed service down the line. Um so, it's a set of agents. We have two in research preview. The ones we talked deep about this in our talk. First one is the evaluator agent that helps you build an eval set, a good data set, because this is the core of the optimization, the eval driven development loop. The second one we have is the diagnose the diagnostics agent. It does you It helps you diagnose your traces you already have in productions, because we learned from our users that reading through these traces took them a lot of time, and having kind of they can just spin off from their coding environment to analyze the traces is very helpful to them. And as you can see here, um both of these agents um are connected through an orchestrator, which runs in your coding environment. And what you need basically is connectors to sources where you basically have all your traces, where you get your incidents from. This could also be like your

</details>

### 产品演示与任务生成

**Burak**: 在实际操作中，如我所说，你拥有一个编排器来处理所有其他子智能体或阶段的分发和调度。你可以在任何你想要的开发环境或智能体中使用它。在这个演示中，我使用的是命令行终端（code code）。

在系统启动时，它会向你展示一个控制面板，呈现你当前拥有的开发阶段，以及代码库中已有的智能体和先前的配置情况。

在这里，我有一些启动命令，它们是特定工作流或阶段的触发命令。如果我在这里输入 `diagnose`，这就会启动用于根因分析的诊断阶段。同样地，你可以将诊断指向一个特定的范围，可以是一个智能体，也可以是一个技能。所以你基本上可以诊断某个特定技能的所有调用情况。

当你启动诊断时，它会从你配置的源平台中检索运行轨迹。在这个演示中，这个平台可以是 LangFuse，也可以是你的本地日志，或者从其他可观测性平台导出的 JSONL 格式文件。

由于诊断运行本身需要耗费较长的时间才能完成，所以我将直接向大家展示一个预先生成的版本，看看它最终是如何工作以及输出什么结果的。

好的，我们在这里看到了什么？基本上，一旦你在智能体上运行了诊断智能体，你就会得到一个生成的 HTML 产物，它会显示你的智能体细节以及你拥有的工具。

如果拥有代码访问权限，它还会告诉你智能体正在使用的是哪个测试套件或框架。

接着，它会通盘分析你的运行轨迹，并根据它们在样本中出现的频次来筛选主要的失败模式。正如我之前所说，大多数时候你并不想去人工阅读所有的轨迹，因为这非常昂贵且不划算。因此，诊断智能体使用多级过滤或细分来挑选最具代表性的样本。

一开始，LLM 会读取轨迹中的一小部分内容，看看是否存在任何明显的、可检测的问题。基于此，诊断系统可以决定接下来重点关注某个特定的失败模式或信号。

另一种选择是，在触发诊断时，你也可以手动指定你自己发现的或者正在寻找的特定问题。这可以是用户直接上报的问题。在当前情况下，这更像是一种引导式搜索。也就是说，如果你告诉诊断智能体你对某个特定问题感兴趣，它就会尝试去寻找所有与该问题相关的故障实例。

<details>
<summary>Original English</summary>

**Burak**: ticketing system, um Slack where people report failures of your agents. Then you connect them. And then, obviously, as we mentioned before, there's different target platforms. Um this could come a PR that automatically gets raised in GitHub. Um this could be just the adjustment of your agents in uh in MD files. Uh yeah, different frameworks we target. And or being deployed to managed services. Um yeah, kind of this is how our platform works. We spin up different agents. They are connected to an orchestra and I guess Burak, let's show uh our first agent in research preview to the audience. Uh in practice, as I said, you have um orchestrator which kind of handles the dispatch for all the other sub agents or stages we have. And then you can use it in any coding harness or agent you want. In this case, I'm using code code. But then what it will do is when you first boot up, it will show you kind of like a dashboard of which stages you have and also kind of the existing things in uh let's say your code base, your agents, and the prior configurations. Now here I have some start commands. These are basically, let's say, trigger commands for the workflows or specific stages. And if I type diagnose here, this will basically start the diagnostic stage for the root cause analysis. And here again, you can point the diagnostics into a specific scope. This can be an agent. This can be a skill as well. So you could basically diagnose all invocations of a particular skill. Here uh when you start the diagnostics, it will retrieve traces from your configured source platform. In this case, again, it can be something like LangFuse. It can be your local cloud transcripts or another you know, like a JSON L format that's like exported from one of the observability platforms. Now, the diagnostics run itself takes quite a while to finish, so I will show you instead a pre-generated kind of version of what it does and how that looks like in the end. Okay, so what do we see here now? So, basically, once you run the diagnostics agent, as I said, on your agents, you will get a um, generated HTML artifact, which basically shows you, you know, the details of your agent, which tools you have. Uh, then in general, if you if you have code access, it will also tell you which harness or the framework that the agent is using. And then here, in general, it will basically go through your traces and then select primary signals, or let's say failure modes, depending on how frequent they occur in the trace samples. Now, as I said, most of the time you don't want to read all of your traces because this is not cost-efficient. So, there the diagnostics use like a a multi-tier filtering or segmentation to kind of pick a representative sample, so uh, originally, a few, you know, pieces of the traces, or let's say, portion will be read by the LLM to see that if there any detectable obvious problems. And based on that, then diagnostics can decide or to focus on a particular failure mode or a signal. Uh the other option is then trigger the diagnostics, you can also specify an issue that you have seen yourself or issue that you're looking for. This could be something that the users reported. Uh in this case, it's again more of a guided search, meaning hey, if you tell the diagnostics agent you have a particular problem you're interested in, then it will try to find all incidents or occurrences regarding the same problem.

</details>

**Bene**: 好的，那我们在这个完整的页面上还能看到些什么呢？

<details>
<summary>Original English</summary>

**Bene**: Okay. And what do we see here in uh in yeah, in full here?

</details>

**Burak**: 这里是诊断的整体概览，它会告诉你检测到了哪些问题，并展示在给定时间段内这些问题发生的频率。在每个标签页下，都有对应的失败模式以及对该问题的解释。

在这里，你可以看到这个问题是从哪里来的，以及它为什么会发生。智能体会提供一个类似于**递归的“为什么”分析链**（recursive why chain），来明确告诉你：“这就是问题最初产生的地方。”

此外，它还会为你提供补救措施或修复建议来解决该问题。在页面中，你还会看到一个**假设模块**（assumptions block）。这非常重要，因为在分析轨迹时，你并不总是能直接访问源代码，所以这能帮助我们检测智能体或诊断智能体是否做出了一些不正确的假设，我们可以在这里直接进行纠正。

在最后，你会看到一系列纠正措施或补救方案，它们能够修复你的问题。你可以选择推荐的方案，或者根据需要多选。

当你处理完所有的问题后，最终会进入一个**决策页面**（decisions page）。针对那些习惯使用语音输入（如 **Whisper** 工作流）的用户，我们提供了一个通用的反馈输入框，你可以直接对着麦克风说话。

当你对所有的决策都感到满意时，系统会生成一份 Markdown 格式的**任务定义书**，直接提供给你的编码智能体。因此，所有的修复或补救措施都可以在你回到终端后，由编码智能体直接自动应用并实施。

<details>
<summary>Original English</summary>

**Burak**: Uh so, this is in general the overview, which tells you again which issues kind of were detected and kind of shows you like the frequency giving the given time frame. Then for each tab, you will have a failure mode and kind of like an explanation of the problem. And then here, you can kind of see where that problem comes from or why it happens. The agent will provide kind of like um uh recursive why chain, let's say, to then tell you, \"Hey, this is where the issue is originating from.\" Now, in addition, it will offer you kind of remedies or fixes to deal with that. And then here, you will see an assumptions block. Uh here, this is important because uh when you are reading traces, sometimes you don't always have access to the code, so this helps us detect uh, LLM or let's say the diagnostics agent makes certain assumptions that are also not correct and we can see and correct them here. Uh, but in the end you will be presented by certain corrections or remedies, which then kind of can fix your problem. You can, you know, pick either the recommended or, you know, as many as you need as it's multi-choice. And once you basically go through all your problems, uh, at the end you kind of get to a decisions page and here again for those using, you know, text-to-speech or speech-to-text AI features like Whisper flow, there's always a general feedback box so that you can always talk into your mic. And finally, when you are happy with all the decisions, you get a markdown, let's say, um, task definition for your coding agent. So, all the fixes or the remedies can then be directly applied to once you go back to your terminal and to your coding agent.

</details>

**Bene**: 感谢你的演示，Burak。最后，关于我们的产品，我们还有什么想说的吗？

感谢大家收听我们的演讲。希望我们能够为大家带来一些关于如何通过智能体 AI 工程师来构建智能体的未来构想。让我们停止无休止的人工调试，让智能体去承担那些繁重单调的工作。如果有任何问题，欢迎随时联系我们。祝大家在大会上玩得开心！

<details>
<summary>Original English</summary>

**Bene**: Thanks for the demo, Burak. So, last words on our product. Yeah, so, uh, thanks for listening into our talk. Um, yeah, I hope we could show you some, uh, good insights on how we envision the future of agent building with the Agent AI engineer. Um yeah, stop uh, the debugging. Um have agents do the tedious work and reach out to us if you have further questions. And yeah, have a great conference.

</details>