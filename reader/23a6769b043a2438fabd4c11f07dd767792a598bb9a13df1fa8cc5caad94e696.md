---
author: AI Engineer
date: '2026-08-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2aS7aKoXn64
speaker: AI Engineer
tags:
  - reinforcement-learning
  - long-horizon-tasks
  - agent-evaluation
  - environment-design
  - llm-judges
title: 重构长视界任务的强化学习环境：Theta Software 的探索与实践
summary: 本访谈由 Theta Software 联合创始人团队分享，深入探讨了人工智能代理在长视界（Long-Horizon）任务中的评估与训练环境重构。讨论涵盖了 METR 等基准的局限性、模型与人类评估尺度的差异，并系统性地提出了利用评判代理（Judge Agents）、可查询轨迹（Queryable Trajectories）和高密度评估红线（Rubrics）来提升模型在复杂软件及金融领域学习能力的核心设计原则。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Rayan Garg
companies_orgs:
  - Theta Software
  - METR
products_models:
  - Claude
  - GPT-4
media_books: []
status: evergreen
---
### 团队介绍与背景

**CTO**: 很高兴今天能在这里见到大家。我们非常兴奋能在这里分享我们在 Theta Software 最喜欢的话题之一。在正式开始之前，我们想先简单介绍一下自己。大家好，我是 Theta Software 的联合创始人兼首席技术官（CTO）。

<details>
<summary>Original English</summary>

**CTO**: It is great to see all of you here today. We are super excited to talk about one of our favorite topics here at Theta. Before we get started, we just want to introduce ourselves. So, hi, I am a co-founder and CTO at Theta Software.

</details>

**Rayan Garg**: 大家好，我是 Rayan。我是 Theta Software 的联合创始人兼首席执行官（CEO）。在此之前，我是 Deep Silken 的创始工程师，在那里我们主要从事三值模型（Ternary Models）的研究工作。

<details>
<summary>Original English</summary>

**Rayan Garg**: Hi, I am Ryan. I am a co-founder and CEO at Theta Software. Prior to this, I was previously a founding engineer at Deep Silken where we did research into ternary models.

</details>

### 定义长视界任务与趋势

**CTO**: 太棒了。那么我先来开启今天的主题。我们今天将要探讨在**长视界任务（Long-Horizon Tasks）**背景下的**强化学习环境（RL Environments）**。我认为在最开始，我们最重要的事情是先讨论一下当前的趋势，以及“长视界”到底意味着什么。

众所周知，AI 代理（AI Agents）能够自主工作的视界正在以极快的速度向外延伸。我们可以通过很多指标来观察这一领域的加速进展。但我认为，给这里的“时间视界（Time Horizon）”下一个清晰的定义是非常关键的。我们从目前最常用于衡量时间视界的基准测试之一获取了相关数据，大家在 Twitter 的推送中可能也经常看到它，那就是来自 **METR**（模型评估与威胁研究组织，前身为 ARC Evals）的数据。

METR 针对“我们如何界定长视界”这一核心问题给出了他们自己的回答。理解这一点非常重要，因为在一年前我们认为属于长视界的内容，放在今天的定义下可能已经不算什么了。而今天我们所认为的长视界任务，在一年或两年后，大概率也会被重新定义。

这就引出了我们的第一个观点：“长视界”实际上是一个标量度量，而非二元分类。它更适合用来测量任务之间的相对难度——例如某个任务比另一个任务的步骤更长、难度更大；但我们很难直接给出一个非黑即白的二元划分，说这个任务是长视界的，而那个任务不是。随着技术的不断演进，其界定的范围也在持续发生变化。

<details>
<summary>Original English</summary>

**CTO**: Awesome. So, I can get us started with the topic today. We are going to be talking about RL environments within the context of long horizon tasks. And I think the most important thing for us to start with at the beginning is just talk about the trends and what long horizon actually means. So, we all know that the horizon at which AI agents can work autonomously is accelerating really fast. This is just some of the metrics that you can look at to see how this progress is really accelerating. But I think it is really important to actually define what the time horizon here actually means. We have gotten this data from one of the most common benchmarks out there that you have probably heard of for time horizons, which comes from METR. And METR has one response or answer to this really important question about how we actually define long horizon. It is really important to understand because what we considered long horizon a year ago probably is not really long horizon in our definition today. And what is long horizon today probably won't be long horizon in a year or two. And I think that gets to our first point, which is that long horizon is really a scalar metric. It is useful for measuring relative tasks, like one task might be more long than another, but it is really hard to define into a binary category of "this task is long and this task is not," especially as the scope changes over time.

</details>

### 人类基准与模型指标的局限性

**CTO**: 另一种我们可以用来界定长视界的方法是参考人类的表现，也就是说，我们是否能够将人类作为基准？如果一个任务需要人类花费特定时长来完成，而 AI 代理也能够自主达成，那么它们就达到了某种关键的时间视界水平。

METR 在这方面做的是为他们所关注的任务设定阈值。比如他们设立了一个 50% 的成功率阈值。这意味着，如果某款模型在基准测试中达到了 16 小时的阈值，代表它在解决那些需要人类花费 16 小时才能完成的任务时，能够达到 50% 的成功率。尽管这背后有一套非常严谨的方法来测量人类是如何耗费这 16 小时的，但我们在此先略过这些技术细节。

除了参考人类之外，我们通常思考长视界含义的另一种方式是参考模型本身的指标。在这方面，我们主要关注的指标包括** Token 消耗量（Tokens Consumed）**、**执行步数（Steps）**以及**工具调用次数（Tool Calls）**。

必须承认，这些模型侧的评估指标可能会非常不稳定且伴有大量噪音。我相信大家在使用不同模型时应该深有体会。例如，在很多场景中，**Codex** 系列模型在 Token 的使用效率上会被认为显著高于 **Claude** 等模型。之所以说这种估算有很多噪音，原因有两点：第一是模型本身的架构差异，第二是不同的测试套件对于 Token 实际消耗量有着极大的影响。

因此，在没有控制好所有变量的情况下，去解读这些数据是相当困难的。比如，如果一个任务需要消耗 GPT 模型 50 万个 Token，在没有实际运行 Claude 之前，它并不能直接告诉你 Claude 运行该任务会消耗多少 Token。

但尽管存在这些噪音，理解这一指标对我们来说仍然极为有用且关键。因为 Token 的消耗量能很大程度上反映出一个任务对 AI 代理自主解决而言究竟有多难。我们必须在长视界中应对诸如“上下文压缩（Compaction）”之类的问题。模型通常无法在足够长的步骤或轨迹（Trajectory）中保持连贯性。因此，即使这是一个有噪指标，当我们对比当前的模型与下一代更强的模型时，如果它们能在相同的任务轨迹上依靠更大的上下文窗口或更好的压缩方案来实现百万级别的 Token 吞吐，这仍然能向我们传递出极具价值的信号，体现出 AI 代理在自主性上的跨越。

它为我们界定了当前模型所面临的技术前沿。这或许与人类的行为方式并不完全一致，因为人类显然不用 Token 来进行思考，但这对于衡量模型能力来说依然具有极高的参考价值。

因此，这是我们可以采用的两种不同的评估维度。但究竟哪一种才是正确的思考方式呢？答案是，我们可能需要将它们结合起来考虑。如果我们孤立地只看其中任何一个指标，往往无法得出准确的评估。

<details>
<summary>Original English</summary>

**CTO**: The first way we can talk about defining this is how METR looks at it, which is human horizon, meaning can we use humans as a benchmark. If a task takes humans a certain amount of time, so if AI agents can do that, then they have reached this certain critical level of a time horizon. And the way METR does it is they have thresholds for the tasks they care about. So, they have a 50% threshold, meaning if a certain model reaches a 16-hour threshold on this benchmark, that means it can achieve tasks with a 50% success rate that take a human 16 hours. And there is a really rigorous methodology of how they actually measure how it took a human 16 hours, but we will avoid some of those details. The other way we usually think about what long horizon actually means is not with the reference of humans, but instead the reference of models. Some of the relevant model units we usually care about are things like tokens: how many tokens are consumed in a trajectory, how many steps it took, how many tool calls it takes. And these can be really noisy, right? Because I am sure you guys have used different models. A lot of the Codex models are seen as more token efficient than some of the Claude models. And it is a pretty noisy estimate for a couple of reasons. One is that which model you are using, like I just said, and different harnesses you care about have a pretty big impact on how many tokens are actually consumed on a task. So, this can be pretty hard to interpret when you are not holding variables constant. If a task takes a GPT model 500,000 tokens, that doesn't really tell you a lot about what that task would look like for Claude models until you actually run on those Claude models. But despite it being a pretty noisy metric, it is actually really useful and important for us to understand because the amount of tokens that are consumed tells us a lot about how difficult a task actually is for an AI agent to tackle autonomously. We have to deal with things like compaction over long horizons. They don't really stay coherent over enough steps or trajectory length that you achieve. So even though it is a noisy metric, it can be really useful when we look at what a next-generation model can do now, and then you use the same model generation and see if it can achieve a million-token trajectory based on an increased context window or improved compaction. That tells us a lot about how autonomous AI agents can actually go for long periods of time in that sense. And it really defines for us what the technical frontier actually means for models right now. Maybe not really human-adjacent. It is really hard to say how many tokens a task takes for a human because we don't really think in tokens, but it is still very useful in that sense. These are two different approaches we can think about. But what is actually the right way to think about this? The answer is that we probably want to think about all of these. And if we just look at one of these metrics in isolation, it is probably not a great way of measuring things.

</details>

### 多维度的模型能力评估

**CTO**: 正如我刚才提到的，无论是单纯依赖模型特有的指标（如 Token 和步数），还是完全依赖人类表现的对照，都有其各自的局限性。对于人类来说属于长视界的事情，由于任务性质的不同，对于模型来说并不一定同样困难。

世界上有许多极其繁琐且耗时的任务。例如，一位金融分析师可能需要打开一个 Excel 文件，去逐一修复整个文件中的一系列格式问题，或者调整里面所有的配色主题。如果文件非常庞大，这对于人类来说将是极其枯燥且会消耗数天时间的工程；但对于模型而言，它或许只需要写一个简单的 Python 脚本，或者利用其它巧妙的自动化手段，在极短的时间内就能一次性搞定。这在计算上对它并不构成真正的挑战。然而，我们绝不能指望一位金融专家去通过编写 Python 脚本来做这件事情，因为绝大多数人并不具备编程技能。这是一个需要注意的差别。

另一个需要高度重视的变量是**测量方法学（Methodology）**的差异。当有人宣称“我们开发的环境平均需要人类运行 16 小时”，而另一个人宣称是“20 小时”时，如果这两个实验在测试专家群体、基础设施和评估标准上不一致，那么这些数字在不同的研究者之间是完全无法进行直接横向对比的。

专家的熟练度差异会对完成特定金融或编程任务的效率产生巨大的影响。随着我们开始触及人类能力的极限，也就是说，去评估那些只有前 10%、前 1% 甚至前 0.1% 的顶尖人类专家才能解决的专业任务时，人类的耗时估算会变得具有极大的噪声和不确定性。

与此同时，AI 代理的工作方式正在沿着其独特的演进路线独立发展。在很多任务维度上，AI 代理表现出了与人类完全不同的瓶颈，也展现出了超越人类传统工作方式的独特优势。

正是因为人类与代理在能力边界和瓶颈上的分化，我们在评估中必须将两套指标同时纳入考量。它们从不同的角度为我们勾勒了技术发展的全貌，只看单一方面都会导致对技术现状的以偏概全。

那么，我们到底该如何客观地衡量模型的能力？这是一个至关重要的问题。因为从根本上说，长视界任务本身并不是我们唯一关注的维度，我们需要在一个更宏大的框架下去思考如何为模型设计训练和评估任务。

我们首先需要考虑的是**环境复杂度（Environment Complexity）**，尤其是与**工具协同（Tool Coordination）**相关的复杂度。这指的是代理在执行任务时，需要协同多少种不同的工具或外部依赖项？它需要在多少个不同的工具和依赖之间进行信息和数据的流转？

在长视界任务出现之前，世界要简单得多。代理可能只需要在代码库中读取单个文件或一组特定文件，这就是任务的全部范围。但现在，随着任务视界的不断延伸，为了精确评估模型能力，代理必须被要求能够熟练协同各种各样的工具：例如使用 **Grafana** 来进行日志观测和解析，操作 **GitHub** 触发 CI/CD 流程，查阅 **AWS CloudWatch** 监控指标，以及直接对数据库进行读写。

随着环境复杂度的提升，我们必须开始审视伴随而来的**状态变更度（State Changes）**，即在整个任务生命周期中，外部环境发生变化的剧烈程度。

<details>
<summary>Original English</summary>

**CTO**: I went through some of the weaknesses with measuring with model-specific metrics like tokens and steps, but there is also a lot of weaknesses in the other approach of relying on humans. What is long horizon for a human isn't necessarily that difficult for a model depending on what the actual task you care about is. There is a lot of tasks that are really tedious and time-intensive. Maybe some financial analyst has to go into an Excel file and fix a bunch of formatting issues throughout the task, maybe changing the theme colors in the file. That might be really tedious for a human to take; it might take them days to do that if it is a really big Excel file. But for a model, it can write a Python script or find some other cool trick to do that really quickly. And that is not really hard for it to do, but you never really expect a financial expert to do that because most of them don't really know how to write these Python scripts. So I think that is one thing to note. And the other that I briefly touched upon before is that the methodology of how we actually measure this has a really big impact. And if someone is out there saying, "Hey, we have some tasks or environments that are 16 hours long on average, someone else is 20 hours," that is really hard to compare across people because there are so many different things in the methodology that really impact what that actually means. It can mean the quality of the experts you are using. Some more experienced experts might actually be way more efficient at doing a certain type of financial or coding task. And this becomes really important as we start shifting towards the frontier of even human capabilities. As you shift towards more long-horizon tasks and tasks that only the top 10%, top 1%, or top 0.1% of humans can really do, these estimates start to get really noisy. And it is something that we really have to consider. The way agents work is developing in its own separate path, and there are a lot of different bottlenecks and different things that AI agents are better at than even the way humans work. And with that in mind, as these paths diverge of how humans do work and what their limitations are and what agents do and what their limitations are, it is really important to keep both these metrics in mind because they paint different pictures of what is actually relevant, and you don't really get the whole picture by just looking at one. So now the question becomes, how do you measure model capabilities? And this is a really important question because fundamentally, long horizon tasks aren't the only thing we care about. This is the larger question that we want to think about every time we are trying to create tasks, create environments to train our models. And the first way we can think about this is environment complexity, and specifically environment complexity related to tool coordination, right? How many tools or external dependencies does the agent have to coordinate? How many tools or external dependencies does the agent have to move information across? Before a long-horizon task world, we will notice that there was a low complexity world where the agent maybe had to read one file or one set of files in a codebase, and that is what a task entailed. But now we can see increasingly as these tasks become more long horizon, what is important to define for measuring model capabilities is that the agent should be using a ton of different tools like Grafana for observability to parse logs, or GitHub for CI/CD, or AWS CloudWatch, or reading and writing to a database. And we are going to notice that as we have these agents use many tools, we also start to think about environment complexity in regards to state changes, which is effectively the degree to which the environment changes throughout the task.

</details>

### 状态变更与任务的串并行复杂度

**CTO**: 必须明确，并非所有长视界任务都是平等的。例如，我们可以通过把一堆完全不相关、相互独立的子任务强行串联在一起，从而人工制造出一个所谓的“长视界任务”。然而，这种做法并没有真正测量到模型的核心能力。

真正有价值的能力在于：**代理在任务早期阶段做出的决策，应当能够对环境的后续状态产生深远的影响，进而制约或启发后面的决策**。这就直接触及了代理与工具交互的本质，以及工具如何改变环境状态的动态过程。

我们可以看一个具体的对比案例。

一种是**可并行复杂度（Parallelizable Complexity）**，这种任务在运行中不涉及深度的状态依赖与变更。比如，代理的任务是分析一个极为庞大的代码库，它可以通过派生出多个子代理去并行读取和分析不同的文件模块，然后将结果汇总返回给主代理，最后由主代理统一进行包装输出。这一过程可以非常轻易地通过并行化来提高效率。

而另一种则是**串行复杂度（Sequential Complexity）**。在这种情况下，比如代理需要利用仪表盘或日志进行分析，那么它在最开始执行的一个错误查询，或者对某条关键日志的误读，就会像滚雪球一样级联级放大，对下游的所有执行步骤产生破坏性的多米诺骨牌效应，最终导致彻底的失败。这完全取决于代理如何操纵这些工具，以及环境状态随之发生了怎样的演变。

我们在评估模型能力时需要考虑的第三个关键维度是**歧义性（Ambiguity）**。这指的是我们在任务开始时提供给代理的初始上下文和环境信息的完整度，包括任务说明、参考产物等。

为了让 AI 代理的工作更贴近人类的真实工作状态，我们必须在初始状态中引入歧义性。因为人类在真实工作中面临的环境永远充满不确定性，信息从来不是百分之百完备的，我们需要在探索中去逐步厘清问题。

因此，我们坚信，要衡量模型的能力，必须测试模型在面对信息不全的环境和文档时，是否具备像人类一样进行主动探索和求证的能力。

然而，引入歧义性在工程上会带来一个显著的权衡：当初始信息存在歧义时，代理可能会探索并衍生出许多条完全不同的执行路径，这也意味着可能会产生多种不同但同样正确的最终方案。这导致标准化的自动评估（Evaluation）变得异常困难。

<details>
<summary>Original English</summary>

**CTO**: Fundamentally, all long horizon tasks aren't equal. For example, one task can be made artificially long horizon by chaining together unrelated, independent tasks. However, that doesn't actually meaningfully measure the model capabilities. Instead, a key component of this is actually being able to have the earlier decisions in the environment influence the later decisions. And this comes back to how the agents are asked to interact with the tools, how these tools change the state of the environment, etc. So, we can look at a concrete example. One example where you will see parallelizable complexity, which is effectively not involving a lot of state changes, is when you have an agent analyzing a large codebase and then the agent needs to spawn off multiple sub-agents. It can very easily parallelize this; it can look at a lot of the different files in parallel, come back to the master agent, and wrap this all up. But meanwhile, if we look at sequential complexity, we will see if you have to use a dashboard or logs, a bad early query or a misread can cascade into these downstream steps that really start to have major consequences later on. It is all dependent on how you use those tools and how the state of the environment changed. So the third area that we also need to consider for measuring model capabilities is ambiguity. And ambiguity is defined as the information you give the agent and the environment when starting the task. So this could be the instructions, this could be the artifacts, etc. And increasingly, as these agents work with more artifacts at the start, we want to have them mirror the work that humans really do. And the work that humans really do has a lot to deal with ambiguity. They don't have the most complete information, and they want to let exploration happen. And so we believe that to measure model capabilities, we need to test the model's ability to explore throughout the environment as well and explore these artifacts similar to how a human would. Now the trade-off with this is that if you are going to have ambiguity in the materials you give, there is a lot more possible paths that the agent could take. There is a lot more ways the agent could be right. And that means that standardized evaluation gets much, much harder.

</details>

### 验证器的设计瓶颈与“评判模型”的引入

**Rayan Garg**: 没错。接下来我将探讨在构建评估环境时最困难的挑战之一，也是包含最多微妙细节的环节——**验证器（Verifier）**的设计。我们到底该如何判定代理产出的工作确实是正确的，并在训练过程中给它提供高水平的奖励信号（Reward Signal）？

在这里，我们面临着一系列工程挑战。随着任务变得愈发复杂，环境随之复杂化，执行轨迹也在不断变长。回顾过去，早期强化学习（RL）主要集中在那些极易自动验证的硬性领域，这也是为什么我们在数学、算法竞赛和数据结构编程等领域能迅速取得巨大突破的原因，因为这些领域的正确性判定非黑即白。

然而，随着时间的推移，我们现在真正关注的是那些在软件和商业领域具备极高经济价值的真实工作。在这些领域中，我们不能仅仅依靠运行一个简单的 Python 脚本、跑几个单元测试，或者写一段数学证明来判断模型的最终输出是否正确，也无法轻易判定系统环境状态的变更是否合规。

我们必须引入全新的技术手段。目前最主要的解决方案是引入**评判模型（Judge Model）**或**批判模型（Critic Model）**。这种方式在评判过程中引入了极具弹性和深度的逻辑，能从根本上重塑我们对正确性的定义和奖励分配方式。

评判模型通常会从两个核心维度来开展评估：第一是审视环境的**最终状态（Final State）**，看它是否符合预期；第二是审查代理的**执行轨迹（Trajectory）**，即评估模型在运行过程中对环境做出的每一步修改是否合理。

那么，我们为什么非要使用基于“评判模型”和“详细红线规则（Rubrics）”的评估技术呢？在深入探讨如何正确使用它们之前，我们必须先理清以下几点核心原因。

首先，正如我刚才所说，在真实的复杂软件工程中，存在着一大类极为关键的任务，我们根本无法为它们编写确定性的验证器。因为这种尝试如果不是由于条件过于繁琐而极易脆弱崩溃，就是受限于问题本身的多样性而根本无法实现。

其次，对于复杂的开放式问题，解决方案不是唯一的，通往解法的路径也各不相同。如果采用最简单的评判方式，比如在早期给评判模型提供一个标准的参考答案，或者一份样例执行轨迹，然后直接拿代理的执行过程去和样例做硬性比对，这在面对高度歧义和开放的任务时是完全行不通的。因为正确的解法有成千上万种，机器不可能在事先穷尽所有的可能性。因此，我们必须探索出更加鲁棒的评估方法，允许并能够正确识别各种不同路径下的正确解。

最后，一个更令人头疼且必须通过轨迹审查来解决的问题是**奖励黑客行为（Reward Hacking）**。在不同的任务设置和规则下，代理会衍生出各种各样的作弊手段。例如，代理可能会试图突破沙箱（Sandbox）的隔离限制，去窥探它本不该接触到的敏感系统信息；或者在执行编码任务时，直接在后台寻找并读取隐藏的测试用例文件来应付检查。

这显然不是我们想要的真正解决方案。为了彻底杜绝此类投机取巧的行为，我们必须通过加强验证器和隔离环境来防范，而评判代理在审查和捕捉这些异常执行轨迹时，起到了至关重要的哨兵作用。这也是为什么我们不能只看最终结果，而必须将代理的完整行为轨迹纳入审计的原因。

<details>
<summary>Original English</summary>

**Rayan Garg**: Awesome. So I am going to talk about one of the hardest things there are to build in environments and one of the most complex things to really think about where there is a lot of nuance, which is the verifier in the environment. How do we actually know that the work the agent did was correct and give it some reward signal during the training process? So I think there is a few challenges here. Just to give a high-level overview, tasks are getting more complex, the environments are getting more complex, the trajectories are getting longer, and we have shifted a lot. A lot of the early RL that we were doing in recent times was really in hard verifiable domains, and that is why we saw these gains in math and data structure style coding problems. But what has happened over time is now we really care about a bunch of economically valuable work in software domains where we can't just run a Python script or run test cases or write a proof to really see whether or not the output was correct or whether or not the environment was changed correctly. We have to start using other techniques, and the main way we are really going to use that is introduce a judge model or critic model, as some people put it, and they can add a lot of nuance to how we actually determine correctness and assign reward. They will look at two things mainly. One is the final state of the environment and how it was impacted. And the other is looking at the trajectory of how the model that you are training made changes to the state of the environment and what correctness looks like there. Why do we actually use judges and rubrics as a technique? I think it is really important to understand before we can even understand how to use them properly, which there is a few reasons. One is that for these software domains, there is like an entire class of problems that are really important, and a lot of the problems we care about, that you can't really write a deterministic verifier for; they would be really impractical, brittle, or just downright impossible depending on what the problem setup really is. And the other thing also is that not all solutions are really created equal, and not all paths of those solutions are equal either. The worst case of a bad solution we can get is some reward hacking that happens. Lots of different types of reward hacking can happen depending on the setup or the task you care about. An agent can escape a sandbox, maybe see privileged information it shouldn't be seeing about a hidden test suite for a coding task. This is all behavior that we want to prevent, obviously, because those are not actually really valid solutions we care about. And mitigating this is going to require strengthening your verifier and your environment setup, but the judge is really, really important in actually catching this behavior. And that is an important reason why we actually look at the trajectory that the agent actually took to get there.

</details>

### 设计高水平评判代理的黄金法则

**Rayan Garg**: 在设计评判模型时，我们需要遵循一系列精细的准则。其中最重要的首要考量是：**评判模型自身也必须被视作一个代理（Judges are agents too）**。

随着测试环境的复杂度呈指数级上升，我们的评估系统必须能够随之横向扩展。为了支撑起对高维度环境的评判，我们需要为评判代理装备一系列工具，并确保整个评估框架能够完美支撑这些工具的调用。评判模型必须对环境中发生的变化拥有极高且清晰的**可观测性（Observability）**。

正如我们前面所讨论的，评判代理要判断任务的正确性，它经常需要直接读取和分析环境的状态。因此，我们为被评估代理所设计的底层交互基础设施，很多时候也需要原封不动地复用给评判代理。

我们可以通过一个具体的场景来解释：假设我们设计了一个软件工程任务，背景是某个服务在部署时发生了故障。被评估代理的任务是去GitHub上翻阅CI/CD日志，去AWS CloudWatch中检索错误信息，定位根本原因，在代码库中修改Bug，然后提交PR并在合并后触发重新部署。

对于这样复杂的链路，如果评判系统只去检查代理做出的工具调用记录，这是极不可靠且极易被欺骗的。为了得出确定性的评估，评判代理必须亲自接入GitHub和AWS系统，去读取部署完成后的实时系统日志，以确保服务确实在正常运行。

这就要求评判代理必须具备进入环境并调用工具的权限。但在此过程中，我们必须设计极其严格的安全防护屏障（Safeguards）：我们必须绝对防止评判代理在进入环境后，意外地对已经运行结束的环境状态产生任何写操作或二次破坏。通常，我们必须对评判代理强制实施**只读权限（Read-Only Permissions）**，限制它不能触发任何部署或修改代码的操作。

另外一个不容忽视的痛点是，随着任务视界的拉长，代理的轨迹变得极其漫长和冗杂。我们绝对不能采取那种粗暴的办法——直接把成千上万步的完整轨迹一次性塞进评判模型的上下文窗口（Context Window），然后指望它通过单次模型调用就给出准确的分数。这种做法会带来极大的注意力和推理精度损耗。

我们必须对轨迹数据进行精细的前置处理。我们需要将轨迹存储在专门的数据库中，并引入子代理去提取和丰富关键的轨迹特征。比如，我们将长轨迹切分为不同的逻辑阶段：第一阶段是代理在检索日志，第二阶段是代理在编写和修改代码，第三阶段是代理在进行自检和运行测试。

我们需要让**执行轨迹变得可索引和可查询（Queryable Trajectories）**。只有这样，评判代理才能够在海量的执行步骤中迅速检索定位到最核心的逻辑节点和失败风险点，并对这些点进行针对性的正确性判定。

<details>
<summary>Original English</summary>

**Rayan Garg**: Yeah, and I think there is a lot of careful things you want to be doing here. One is that there is nuance in how much guidance or explicit rigidness you want to add to the trajectories that the model can actually take. If we enforce this too tightly, we collapse the state space of how many paths the agent actually explores. And that can be really bad, especially because some of the more simple approaches we have seen with judges early on is, hey, we will just give it a reference answer or solution or maybe a sample trajectory of what a good solution looks like and then just compare against what the model did and say, hey, does it match up with that? And that really does not work for these more ambiguous or open-ended tasks because there is so many possible correct solutions. It is basically impossible to account for every single one. And we want to check for more robust methods that allow for these different solutions. So now that we have established why we use judges, we want to go through some of the general heuristics and principles we think about when we are designing good judges. Some of the things that we think about at Theta. So you know, I think the first important consideration to make is that judges are agents too. So as environments get really complex, often times a consideration we have is like, hey, we have to make sure the harness can scale and match up with whatever environment you have. Maybe that means introducing a bunch of new tools and making sure your harness can support those tools really well. The agent has clear observability over what is happening in the environment. But I think like we said, the way the judge determines correctness is that it often times has to look at the state of the environment itself as well. So a lot of the harness that you have designed for the agent might also be reused for the judge as well. I think the best way to illustrate this is the example we have here. Let's say you have defined a task where there is some deployment failure with the software engineering task of some platform you are deploying, and the agent's task is to sift through the CI/CD logs on GitHub, look through the CloudWatch logs, figure out whatever happened, apply the changes to the codebase, open a PR, and kick off a redeploy once the PR is merged. For a lot of that, if the judge actually wants to verify whether or not this is correct, besides just looking at the tool calls the agent made—which are usually not very reliable—it actually has to also check the GitHub logs, AWS logs, or the GitHub logs after the deployment happened to make sure, oh, are things actually working properly. So it is really important that the judge has access to the environment in the same way, with some important safeguards of course. One is that we don't want the judge to make an accidental mutation in some way to the environment after the agent is done. So you want to be very careful about that. Maybe that means enforcing read-only permissions for a lot of this information; it can't actually kick off a deployment or anything like that. So those are things to be careful about. But I think this is really important, especially where there is a lot of open-ended approaches and the only way we can really verify correctness is to actually look at the state itself. The answer isn't obvious of whether or not the agent completed the task just from looking at the trajectory. So I think that is one example where this approach is really important. I think the other thing to be notable of is as these environments get more complex, the agent trajectories get longer and longer, and part of the reason we also need the judge to be an agent is that you can't just use this really basic approach of taking the trajectory and stuffing it in the context window of the judge and have it be a basic LLM call. These trajectories can get really long and complex. So we need to do a lot more thoughtful processing of the trajectory in some meaningful way. That might mean we put it into some database. We use sub-agents to actually enrich certain information. Maybe we parse out specific phases that the agent was actually in. Maybe the beginning part was it going through logs. The second part was actually writing code. The third part was actually it checking what happened after that. These are all different things we want to do. And in that sense, we need to make the trajectory itself queryable. So that might mean enriching information like I just said or looking at some other metadata at certain steps. This is really important so the agent can find critical steps like failure points and verify whether or not those are actually failures. Making that usable for the agent is really important.

</details>

### 环境的可学习性与评估红线的质量保证

**Rayan Garg**: 我们需要考虑的另一个极具挑战的课题是环境的**可学习性（Learnability）**。这直接取决于评估系统中**奖励信号的密度（Density of the Reward Signal）**，而这主要由评判模型所依据的红线规则（Rubrics）来定义。

我们需要特别警惕在红线设计中塞入过度密集的考核点。在面对那些超出模型当前能力极限的前沿挑战时，如果考核红线设计得过于琐碎和严苛，评判模型在实际运行中将极难保持评分的**一致性（Consistency）**。因此，我们必须进行大量的 QA（质量保证）测试，以确保评判代理能够稳定、不偏不倚地执行这些评估标准。

除了奖励密度外，影响环境可学习性的关键因素还包括任务分布的合理性以及底层数据的质量。如果忽视了可学习性的优化，大量的算力资源将会被白白浪费在那些模型根本无法有效吸收和进化的任务场景中。

在当前的行业实践中，一些前沿的评判模式正在悄然兴起。我在这里快速提两个关键的趋势。

首先，确定性验证器并没有完全退出历史舞台。我们目前经常将确定性验证器与大模型评判代理结合起来使用。例如，让确定性程序首先自动生成一份系统状态分析报告，然后再由大模型评判代理去审阅这份报告并给出综合裁决。

其次是引入**动态评估红线（Dynamic Evaluation-Time Rubrics）**，这极大解决了级联失败中的评分公平性问题。在长链条任务中，我们允许系统给代理以“部分分（Partial Credit）”。如果在任务的最开始，代理做出了一个错误假设并在此基础上继续往下执行，只要它后续的推导和操作在逻辑上能自圆其说且完全正确，动态验证器就会倾向于承认它后续步骤的正确性并给予相应的分数。这就像在批改数学试卷时，如果第一步算错，但后面的推导完全符合逻辑，老师依然会给后面的步骤分一样。这对于模型获得平滑的梯度信号、进行高效学习是极为有利的。

<details>
<summary>Original English</summary>

**Rayan Garg**: I think another important thing to consider is learnability of our environments. The most important thing here is just the density of the reward signal, and a lot of that comes from your rubric and how the judge is defining that. So, I think you have to be very careful with just overloading with density in your rubric. A lot of times, especially for frontier problems that models aren't really capable of yet, judges will really struggle to apply that rubric consistently. So, there is a lot of QA we need to do to make sure judges are able to apply that information correctly. There is other learnability factors that we care about and we measure in environments like the distribution of tasks and the actual underlying data there. And these are all things we think about for learnability, and it is really important, otherwise you are just wasting a bunch of compute on problems where the model can't actually effectively learn. These are some emerging rubric judge patterns we have seen. I'll quickly skim over this. Often times, deterministic verifiers aren't completely dead. Oftentimes we use them in tandem with judges. Maybe generating an artifact for the judge to look over, where you are collecting metrics. Or another interesting thing we could use is dynamic evaluation-time rubrics, where we are giving partial credit where we have baked in some assumptions that the model made and assume they are correct. It is like grading a test assuming if you got the first part wrong, let's just assume it is correct, did they get the rest of the part right? That can be really important for assigning credit there. I will skip over this part. I will let Ryan just close things off with some things about QA for rubrics.

</details>

**Rayan Garg**: 没错。对于我们制定出的每一套红线规则，我们都会在后台运行多层测试程序。我们今天不会拆解所有的测试细节，其中有些是非常基础的，比如黄金标准对照测试、无操作变异（No-Op Variance）测试等。在设计任何验证器时，这些都是应该默认考虑的常规测试。

但正如我们所看到的，随着我们越来越多地让 AI 参与到规则的制定和校验流程中，甚至协助人类专家进行规则迭代，加之任务的视界拉得越来越长，我们必须引入更为复杂的测试机制。这其中最核心的就是**覆盖度测试（Coverage）**以及**专家一致性（Expert Agreement）**的校验。

在今天演讲的最后，我想和大家分享一下为什么我们所做的这些研究至关重要。我们在今天前半段花了大量时间去严谨地定义什么是长视界，核心原因在于：我们发现目前行业中产出的许多用于训练和评估模型的数据集与文献，实际上存在着严重的质量缺陷。

以目前金融领域最著名的三大基准测试——**GDP-val**、**Toolbench** 和 **Apex Agents** 为例，它们在以下几个维度上暴露出严重的不足：

第一，如果根据 METR 所给出的长视界标准来审视这些基准，我们会发现这几个测试集中每个任务所耗费的平均人类时间远远低于长视界任务的门槛。因此，它们本质上并不能算作长视界评估。

第二，这些基准目前已经出现了高度的**能力饱和（Saturation）**，我们认为这是由于其任务设计耗时过短导致的必然结果。如果看 Apex Agents 在投资银行（IB）板块的测试表现，其 Pass@1 指标已经达到了惊人的 57%。这非常直观地告诉我们，当前的模型已经能非常轻松地解决其中大半的任务，这些测试已经无法对前沿模型构成真正的压迫感。

第三，这些测试的**覆盖宽度（Breadth）**极其狭窄。例如，GDP-val 几乎把所有的金融测试任务都局限在极小范围的 Excel 操作上；而 Apex Agents 则过度聚焦在投行（IB）领域。这就导致金融体系中极其重要且亟需可学习性数据支撑的核心板块——如信用评估（Credit）、债务结构（Debt）以及风险控制（Risk），在现有的评估体系中出现了严重的空白。

第四，正如联合创始人刚才所强调的，它们所能提供的奖励信号粒度（Granularity of Reward Signal）极其粗糙，根本无法支撑起模型强化学习训练所需的梯度密度。在 Theta，为了确保训练效率，我们针对每个评估维度都会设计多达 20 个子维度规则，并且每个子维度规则下还会再细分 10 个层级的评判标准。相比之下，现有基准的简陋程度显而易见。

最后，我想用 Theta 制作的金融测试集的一些核心统计数据来作为今天分享的收尾。在我们的测试集中，通过对 50 个典型任务样本进行多轮评测，人类专家的平均完成时间达到了 15 小时。而在面对这个测试集时，即使是目前最优秀的前沿模型，在处理这些分布在金融各核心板块的复杂任务时，依然面临着极高的失败率，表现出明显的挣扎。这才是我们认为真正能够代表前沿、并能为下一代自主代理提供演进动力的强化学习环境。

非常感谢大家今天抽时间与我们交流。谢谢！

<details>
<summary>Original English</summary>

**Rayan Garg**: Yep. So for each rubric we produce, we run a couple of different tests. We won't go into all of them. Some of them are pretty basic, right? Gold, no-op variance. These are tests you want to be considering regardless for your verifiers. But I think increasingly, as you involve AI in the process of even creating rubrics or verifying rubrics or aiding experts, you need to have more and more tests, especially as the tasks become more long horizon. And so that really touches on the coverage and the expert agreement. But I think what we wanted to close off with today is why a lot of this stuff matters, right? We spent a lot of time earlier in this presentation defining what long horizon means. And a huge reason we did that is because we feel like a lot of the literature and data being produced right now and being used to train and evaluate models is actually flawed. So we present three major benchmarks in the area of finance predominantly. And so this is GDP-val, Toolbench, and Apex Agents. There's a couple of notable issues here. First, if you look at the average human hours per task, based on what METR has defined for a lot of the leading frontier models, a lot of these different average human hours per task fall far below that, and so they wouldn't actually be considered long horizon tasks. The second notable issue here is that we see that these benchmarks are already reasonably saturated, and we think this is a downstream effect of the average human hours per task. So, it is really important to look at the metrics that are being used here. If you look at the Apex Agents IB section of this benchmark that they put out, pass at 1 effectively means that for 57% of cases, the tasks are 100% solved. That is effectively telling us that there is a large part of these tasks that models are solving similar to what we have seen already. But I think a third key important part here is the breadth. For each of these different benchmarks, particularly GDP-val, they have a very narrow set of Excel tasks that they consider for finance. And for Apex Agents, they're largely focused on IB. What this means is that a lot of these more important areas for learnability like credit, debt, risk in the domain of finance don't really get covered. And then I think lastly, I'll note the reward signal as Gver mentioned is really important. And in regards to the reward signal here, we'll notice that there's like really, you know, if you look at what you need for a rubric, you need a very granular, detailed reward signal. You need, we have 20 different subcriteria and 10 different subcriteria per criteria. So, I think there is a lot of room that is left when you read these benchmarks into how granular reward signal they're giving, which is really important for being able to go ahead and train your models. With that, I think I wanted to round off with a couple of stats about the data we produced. Here you can look at some statistics for our finance data. We can see that the human time to complete one task on average is 15 hours over a 50 task sample set. Furthermore, it takes models a pretty long time to work through these tasks. And after all of that, across all the domains we care about within finance, for example, they still struggle significantly. And so here we provide mean five notably different than all of these previous scores we see here. So, thanks for taking the time to talk with us today. Thank you.

</details>