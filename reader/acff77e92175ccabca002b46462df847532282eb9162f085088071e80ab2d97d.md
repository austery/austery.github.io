---
author: AI Engineer
date: '2026-10-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ImnZ7s68jw8
speaker: AI Engineer
tags:
  - ai-engineer
  - agent
  - evaluation
  - observability
  - telemetry
title: AI 工程师当下在做什么：构建自动化闭环与常驻智能体
summary: 演讲探讨了 AI 工程师职责的演变。随着前沿实验室向运行成千上万个常驻智能体迈进，AI 工程师的角色已从编写单一功能转向构建涵盖构建、评测、监控与改进的完整闭环，通过追踪全链路遥测数据驱动智能体自我修复与系统优化。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Andrej Karpathy
companies_orgs:
  - Arize AI
  - Anthropic
products_models:
  - Signal
  - Claude Code
  - Cursor
  - Codex
media_books: []
status: evergreen
---
### AI 工程师的定义与前沿差距

[music]

>> 太棒了。欢迎来到 AI Engineer。

考虑到我们在纽约的 AI Engineer 大会上，我想我们可以重新审视一下这个问题：AI 工程师到底是做什么的？感觉每年我们对 AI 工程师职责的理解都在发生变化。

在准备这次演讲时，时间点非常巧，因为 Karpathy 刚在这个周末发了一条推文，谈到了目前日益扩大的差距——基本上是前沿领域那些运行着成千上万个智能体和常驻（always-on）智能体集群的人群，与普通人群之间的差距。他列出了这样一个漏斗：超过 60 亿用户可能接触过或使用过大语言模型；10 亿到 20 亿可能是偶尔使用的免费层用户；2000 万是专业人士，可能已经开始用它将原本需要数周的工作缩短到几天；但真正身处前沿实验室的人群比例极小，大约只有 5000 名用户，他们能够同时运行成千上万个智能体。
<details>
<summary>Original English</summary>
[music]

>> Awesome. Well, welcome to AI engineer.

Um uh thought given where at AI engineers New York, we'd kind of revisit the question of what does an AI engineer do? Feel like every year we have an idea of what an AI engineer does and that definition kind of changes. Um And as I was putting this talk together, it was super timely because Karpathy actually just tweeted something this weekend where he kind of he kind of talks about this growing gap between basically folks at the frontier who are running thousands of agents and swarms of always-on agents and he really kind of drops this funnel where 6 billion plus users have maybe touched or interfaced with an LLM. 1 to 2 billion or maybe like casual free tier users. 20 million are professionals who have maybe started using it for more taking some piece of work that would have taken weeks down to to days. But really those at the frontier labs are which is a super small percentage. It's like 5,000 users. Uh are the ones who are running thousands and thousands of agents at once.
</details>

看着这个现状，我的意思是，他勾勒出了这个漏斗的一部分。任何人看到这个漏斗的第一反应都是：我处在哪个位置？而且他也勾勒出了一条路线图，即未来几年大家如何能成为那 5000 名运行着数千个智能体的用户之一。

可以说这种情况已经持续了几十年，抽象层级变得越来越高。过去几年这种演进无疑更加迅速，但我们已经经历了从工程师编写更高抽象层级的语言，到直接复制粘贴代码，再到使用本地智能体、使用云端智能体；现在真正的期望已经演变为：我们所有人如何在内部开始运行一个智能体团队或智能体工厂，并朝着这个方向构建。
<details>
<summary>Original English</summary>
And as I look at this, it really is I mean he's kind of dropped a bit of the funnel. I mean the first question anyone looks at this is that where am I on this? And you know, he's kind of drawn out a bit of a road map of how does everyone get to in the next couple of years one of those 5,000 users who are running thousands of agents.

And this has been happening I'd say for for a couple of decades now where the abstraction layer has gotten higher and higher. I mean definitely faster in the last couple of years, but we've gone from engineers writing higher level abstraction languages to I mean just copy-pasting code, using local agents to using cloud agents to really the expectation now is how how do all of us start running a team of agents or factories of agents internally and build toward that.
</details>

>> [嗤笑]
<details>
<summary>Original English</summary>
>> [snorts]
</details>

### 从编写功能到构建闭环

>> 这实际上带来了 AI 工程师“过去与现在”的转变。对某些人来说这可能算是一条路线图，但我认为在我们团队内部，我们已经开始朝这个方向推进了。

作为一名 AI 工程师，你的工作不再仅仅是编写功能、编写一个 AI 功能，而是如何**构建出能够编写该功能的闭环（loop）**。不再仅仅是阅读 diff 差异并亲自进行代码审查，而是实际上如何搭建系统和智能体来完成代码审查，以及如何编写评测（evals）来真正审查那些非确定性的任务。

甚至也不再仅仅是设置指标和软件遥测，而是实际上如何让智能体去梳理并读取可观测性数据，让智能体真正消费这些遥测数据来发现模式。
<details>
<summary>Original English</summary>
>> And what this has led to is essentially what is a then and now of what an AI engineer is. And this is is this is a bit uh I I think of a of a roadmap for some, but I think internally this is what we've already started to kind of push towards. As an AI engineer, your job's no longer to just write the feature, write an AI feature, it's about how do you build the loop to write that feature. It's no longer about you know, just reading the diff and actually doing code review, it's actually how do you set up systems and agents to do the code reviews, and how do you write evals to actually do the non-deterministic um to review those non-deterministic tasks.

It's actually no longer even about just setting up metrics and and software kind of telemetry, but it's actually how do you have agents go through and read the observability data and have agents actually consume that telemetry to find patterns.
</details>

所以，[嗤笑] 我们一直谈论的这个闭环——构建、评测、上线、监控、改进——现在的 AI 工程师实际上不仅要负责执行其中的每一个步骤，更要负责**如何构建出能实际执行这些步骤的闭环**。
<details>
<summary>Original English</summary>
And so, [snorts] this loop that we've kind of been talking about, which is the build, the eval, ship, you monitor, you improve it, well, the AI engineer is now actually responsible not just for doing each of those steps, but how do you build the loop that does the that that actually does each of those steps.
</details>

### Arize 的 Signal 实践与架构

在 Arize，我们在产品中推出了一项功能，今天我也想分享一些在构建它过程中的经验，那就是我们构建了 **Signal** 来为 AI 工程师实际运行这个闭环。Signal 所做的是：它检查所有的追踪（traces），读取遥测数据，在遥测数据中识别模式，并且如果它拥有代码仓库的访问权限，它实际上可以提交修复方案或 PR。

Signal 是一个常驻智能体。这是 Signal 如何启动的一个示例，但它最初只是通过读取 traces 开始。这是一个非常简单的例子，但它会逐一读取——这一切都是可配置的——读取在某种频率下进来的特定数量的 traces。它读取这些数据，目标是真正从遥测数据中识别出问题。

它必须记录之前已经发现过的问题。因此，我们必须考虑它的记忆：它之前是否看到过某些它认为是问题的内容？某件事当时看起来像是个问题，但并没有被实际捕获，而现在随着它收集了更多数据，它是否认为这实际上是一个严重得多的关键问题？因此，Signal 实际上是通过读取 traces 来开始识别问题的。
<details>
<summary>Original English</summary>
And at Arize, one of the things we've rolled out in our product, and I'm going to talk about a bit of what we've learned in building this, is we built signal to actually run this loop for AI engineers. What signal does is that signal actually looks at all of the traces, it reads the telemetry, it identifies patterns in that telemetry, and it can actually put up a fix or a PR if it has access to the repo.

And signal signal's an always-on agent. So, this is an example of how signal starts, but it actually starts off by just reading the traces. Super simple example, but it goes through, reads um and all of this configurable, but and certain volume of traces that came in in some cadence. It reads it and then the goal is to actually identify issues from that telemetry data.

It has to keep track of issues that it's previously seen. So, we have to consider the memory of did see something before that it thought was an issue? Did something seem like an issue, but it wasn't actually captured and now as it collects more data, it actually thinks it's much more of a critical critical issue. And so, signal actually starts off by reading the traces to identify problems.
</details>

### 将智能体作为遥测数据的主要消费者

我们最先意识到的事情之一是，真正消费遥测数据的主体在未来已经发生了很大变化。这不再是关于人类消费遥测数据。甚至不仅是关于人类去消费它、然后智能体接手任务，而是真正变成**如何配置你的遥测数据，使智能体成为该数据的主要消费者**。

这样带来的效果是，可观测性数据可以成为实际运行并触发这些常驻智能体的触发器。因此，如果你正在构建一个由常驻智能体组成的团队或工厂，首要考虑的事情就是：**什么能触发这些智能体唤醒或启动？**

触发器可以有很多种。对 Signal 而言，它是可配置的，可以按持续的固定节奏运行。比如每 3 小时、6 小时去拉取最近的某 X 数量的 traces，进行读取并发现问题。它也可以由事件触发，比如 Slack 消息、某个用户对某事提出了抱怨；它也可以是基于指标的触发器。这些本质上都是用来唤醒智能体实际启动的触发器。
<details>
<summary>Original English</summary>
And so, one of the first things that we realized was that the future of who's actually consuming telemetry data has really changed. It's no longer about humans consuming telemetry data. It's not even about humans consuming it and agents kind of taking on the task, but it really is how do you set up your telemetry data so that agents are the primary consumers of that data.

And what that does is that that observability data can become the trigger for actually running and triggering these always-on agents. And so, the first thing that if you're building a team of of you know, a factory of really always-on agents is what triggers these agents to wake up or start. And there can be a variety of triggers. For signal, for us it's you know, it's configurable to run on an ongoing cadence. So, every 3 hours, 6 hours, go pull the last, you know, X amount of traces, read them, identify problems. It can also be triggered by events. So, Slack messages, um if some user complains about something, it can be a metric-based trigger, but these are essentially triggers to kick up the agent actually starting.
</details>

一旦智能体实际启动，我们必须花时间弄清楚：一个智能体运行（agent run）究竟是什么样的？

对我们来说，我们会拉入 traces 的所有上下文，以及任何额外的第三方数据——我们允许连接到 APM 日志、APM 指标，拉入所有我们想接入的第三方遥测数据，还有代码仓库的访问权限，以及实际运行该智能体所需的任何密钥访问权限。但所有这些信息都被放入一个沙盒（sandbox）内部，这就是每次智能体唤醒时启动的环境。

智能体被触发后，我们构建沙盒，将我们需要的一切放入沙盒中。那里有一个代理（proxy），信息进出沙盒的唯一途径就是通过这个单一代理。沙盒内部发生的所有事情实际上已经在被追踪（traced），每一个产出——生成的和创建的问题——都会被保存到某种形式的记忆中。智能体的每一次实际运行都会发生这个过程。
<details>
<summary>Original English</summary>
Once the agent actually starts, we have to spend some time figuring out, well, what is what is an agent run actually look like? For us, we actually pull in all of the context of the traces, um any additional third-party data, so we allow collecting to APM logs, APM metrics, um but all of the third-party telemetry data that we want to pull in, um access to the repo, um access to the actual um the the access to any keys that are needed to actually run run this agent, but all of this information is um put inside of a sandbox, and this is actually what's started up every time the agent wakes up. And so, the agent's triggered, we build a sandbox, we put everything that we need inside of that sandbox, there's a proxy, the only way to get information in and out of the sandbox is by this single proxy, and everything that happens inside of that sandbox is actually already getting traced, and every output, so the issues that are generated and created are all getting saved to some kind of memory.
</details>

智能体每次运行结束时——它扫过了所有的 traces，无论有没有发现问题——都会涉及**哪些东西实际被保留，哪些东西被实际丢弃**。

保留下来的内容包括：如果发现了任何问题，所有输出都会保存到某种记忆中，这样下一次启动智能体时，它不必从零开始，而是拥有它实际发现过的历史记录；智能体本身是被追踪的，所以智能体调用了什么的所有遥测数据、它是否实际提交了 PR，所有这些都会被追踪；以及它在实际运行中可能学到的任何技能，也可以保存到代码仓库中。

而销毁的内容则是：沙盒会被拆除，任何凭据显然都会被移除，代码仓库的访问权限会被移除。所有不需要保存的东西在 Signal 运行完毕后都会被销毁拆除。
<details>
<summary>Original English</summary>
And so, this happens every single time the agent actually runs. Every time the agent finishes running, so it swept through all of the traces, um it either found something or it didn't, there's what actually stays and what actually gets thrown away. What stays is that if it found any issues, all of the output is actually saved off in some kind of memory, so that the next time an agent gets spun up, it doesn't have to start from ground zero. It has a history of what are the issues that it actually found. Um the agents are traced, so all of the telemetry data of what the agent called, um you know, if it actually put up a PR, all of those things are actually traced. And any skills that it may have learned while actually doing a run can also get saved to the actual repo.

But, the things that go away is the sandbox gets torn down, any credentials, um you know, obviously get get removed, um the repo access is removed, and so all of the stuff that doesn't need to be saved kind of gets torn down after the run of signal.
</details>

我们设计 Signal 的方式是要让这个智能体保持持久性（durable）。这意味着，如果沙盒失败，或者 harness 运行框架失败，它在运行途中不应该从头开始重来，而是应该能够直接从失败的那个步骤继续恢复，所有所谓的状态都会保存在沙盒外部的记忆中。所以我们将其设计为一个非常耐用可靠的智能体，即使失败了也可以重新拉起，你可以启动一个新的沙盒、启动一个新的 harness，从它原本开始的地方重新接续。

所有这些本质上构成了我们构建 Signal 每次运行的基础机制：智能体被触发，智能体启动并加载所有的上下文和证据，扫描遥测数据，无论是否发现问题，所有内容都会保存到记忆中；如果中途发生失败，智能体可以被重新设置恢复。
<details>
<summary>Original English</summary>
And we've designed signal in a way to actually keep this agent configure durable. So, that means that either if the if the sandbox fails, or if the harness fails, then it shouldn't have to start everything from scratch in the middle of the run. It should actually just be able to pick up from the step that it failed, and all of the state, so-called, is kind of saved off in kind of a a memory outside of the sandbox. And so, we've designed this to actually be a very durable agent, so that if it fails, it can spin it back up. Um you can launch a new sandbox, launch a new harness to kind of pick back up where it started.

So, all of this is essentially the underpinnings of how we built signal to run every single run. Agent gets triggered, agent gets started, loaded with all the contexts, the evidence, uh it sweeps through the telemetry data, it either finds something or it doesn't, all of that gets saved to memory. If something fails in the middle, the agent can get reset up.
</details>

### 模型与框架解耦，以及评测的核心地位

而且我们构建 Signal 时使其对模型或 harness 保持不可知（agnostic）。所以今天 Signal 不仅支持 Cloud Code（这是我们最初起步支持的），还支持 Cursor 和 Codex。我们的目标是实际支持市面上所有主流的、甚至是开源的 harness。

并且 Signal 还支持多种模型。即使你使用的是 Claude Code，你也可以选择 Anthropic 家族内部的任意模型。这对我们来说非常重要，原因之一是这是我们在每次拉起智能体时评估其质量的极佳方式；它还帮助我们控制成本，因此我们可以观察到，随着使用更强大的模型，PR 的质量可能会更好，但我们能否在降低成本的同时仍然保持严谨性，并保持 Signal 实际检测问题的质量？这是我们在设计 Signal 时从第一性原理出发进行过深入思考的问题。
<details>
<summary>Original English</summary>
And we built signal to also be you know, agnostic of the model or the harness. So, today signal supports not just Cloud Code, which is what we started with, but it also supports Cursor and Codex. And the goal is to actually support all of the the major, even the open source harnesses out there.

Um and signal actually also supports um multiple uh it will support kind of multiple models. So, even if you're using Claude code, uh you can pick any of the models inside the Anthropic family. Um and this is really important to us because one, it's an awesome way for us to evaluate the quality of the agent um every time we spin it up. It helps us control costs, so we can see, you know, as we use more powerful models, the better quality maybe the PRs are, but can we reduce the quality of the the you know, can we reduce the cost and actually still maintain the rigor um and maintain the quality of issues that are actually detected by Signal. So, this is something we deeply thought about from from first principles when we were designing Signal.
</details>

这其实非常自然地引申到了“AI 工程师需要做什么”。AI 工程师确实需要学习如何编写评测（evals）。每次 Signal 运行时，如果发现了问题并提出了 PR，就会在智能体之上运行评测来测试该 PR。评测可以非常简单，例如作为开发工作流的一部分进行测试：你有一个数据集，或者一个带有输出的简单 prompt，用来测试并确保没有回归。

但这些评测还需要与人类的判断保持对齐。我认为在构建系统来运行闭环的过程中，这或许正是 AI 工程师应该投入大量时间的地方。他们应该花时间与他们的智能体一起查看 traces，识别常见的错误。

有许多技能，比如我昨天听到 Lance 谈论用来构建评测的 Claude skill；我们也有结合 Arize 评测器的 skill，帮助你构建和编写评测，并将这些评测与人类判断对齐。但对于 AI 工程师来说，转向去定义“什么是好的标准”变得至关重要。对于很多与我们沟通和合作的团队来说，他们的问题变成了：“我该如何信任评测器？”以及“我是否真的相信这个评测能够捕捉到……我该如何相信它能达到与我的判断一样好的水平？”我可以说，我们在自己的产品上投入大量时间所做的事情，就是真正地**对评测器本身进行评测（evaluate the evaluators）**。
<details>
<summary>Original English</summary>
And this is actually a pretty good segue into what does an AI engineer need to do? Well, an AI engineer really needs to kind of learn how to write evals. And so, we actually every time Signal runs, Signal finds an issue, it puts up a PR. Well, there's evals that are run on top of the agent to test that PR. Um and an eval can be as simple as um you know, testing something as part of your development workflow. You have a dataset, you can be a simple prompt um it with with outputs that you're testing to make sure that there's no regressions.

Um but these evals can also they need to be kind of aligned with human judgment. And I'd argue that this is actually probably where an AI engineer should be spending a lot of their time as they're building the system to actually run the loop. They should be actually spending time looking at the traces with their agents, identifying what the common errors are. Um and there's a lot of skills I think I was hearing Lance yesterday talk about the Claude skill to build evals. We have a skill with the arise um evaluator to actually help you build and write evals as well as align those evals with the human judgment. But, this is probably where the shift to defining what is good becomes really, really important for an AI engineer to actually do. And for a lot of teams I I think we speak with and we work with, their question becomes, "Well, how do I trust the evaluator?" And do I do I really trust that the eval is um you know, is going to capture you know, how how do I trust that it's as good as my judgment? And I'd say what we spend a lot of our own time doing for our own products is that we actually evaluate the evaluators.
</details>

我们花相当多的时间来实际构建这些数据集——黄金标准真相（golden truth）数据集。我们运行评测，对照人类的产出进行验证，然后努力对齐，以确保在实际交付新的评测器之前，裁判模型的判定确实与人类的判断达成一致。

然后这些评测既可以用于离线测试，也可以用于在线测试。我认为这正越来越多地成为 AI 工程师的工作内容。
<details>
<summary>Original English</summary>
Um we spend a decent amount of time on actually building these data sets, golden truth data sets. We run e-vals, verify them against the human output, and then try to align to make sure that the judge actually agrees with the human um and and they're in agreement before we actually ship out uh a new evaluator.

And these e-vals can then be used both in an offline testing as well as in an online testing manner. Um and this this is probably what I would say as an AI engineer is more and more of what the job is becoming.
</details>

### 全链路追踪与自我完善系统

最后我想留给大家的思考是：作为一名 AI 工程师，你构建了这个智能体，让它常驻运行，在正式发布到生产环境之前运行评测。发布上线之后，目标则是对一切进行追踪（trace everything）。

现在，“追踪一切”不仅意味着追踪智能体本身，还意味着追踪构建出这些智能体的背后的编程智能体（coding agents）。你可以追踪 Cloud Code，可以追踪 Cursor，可以追踪 Codex，所有这些编程智能体都可以被追踪，从而让你能够理解在大家正在构建的智能体工厂中究竟发生了什么。

然后，所有这些 traces 也可以在线进行评测。因此，不仅在你实际测试新变更时存在离线评估；当它进入生产环境后，这些评估会变成你在遥测数据之上运行的在线评测。对我们来说，这最终变成了新的数据，再被拉回到智能体中，去读取遥测数据、读取评测结果，并揭示 traces 内部存在的问题。所以整个系统真正变成了：你如何从**收集数据、评测数据、在此基础上运行智能体以发现问题，并找出差距所在，从而真正改进你的系统**。
<details>
<summary>Original English</summary>
Um and so, what I'm going to leave you guys with is as an AI engineer, you've built this agent, you've built this agent to actually run, be always on, you run e-vals before you actually ship it into production.

You can ship it, and then once it goes into production, the goal is to actually trace everything.

And tracing everything now means not just tracing the agents, but also tracing the coding agents behind the agents that built this. So, you can trace um cloud code, you can trace cursor, you can trace codex, but all these coding agents can be traced so you can understand what happened um in the factory of agents that you all are building.

And then these agents that all the traces can then also be evaluated online. So, there's an offline evaluation when you're actually testing what you're what a new change is, but as it goes into production, these become your online evals that you're running on top of the telemetry data. This for us ends up becoming the new data that then gets pulled back into the agents to read the telemetry data, the evals, and surface up kind of problems inside of the traces. So, the the system really becomes how do you go from collect data, eval that data, run agents on top of it so that you can find problems and figure out where the gaps are to actually improve improve your systems.
</details>

回到我们最初提出的问题：AI 工程师到底是做什么的？

如今前沿实验室里的做法与许多企业内部的现状之间存在着相当大的差距。部分原因可能仅仅是企业内部的数据比起实验室中非常受控且可测试的数据要混乱得多。但 AI 工程师正是弥合这一差距的角色。

我认为这真正始于**追踪一切**：追踪你实际构建的智能体；运行评测以学会如何测试我们正在构建的产品；然后构建一个系统，使智能体能够从实际收集的遥测数据中不断改进。这样你就不再只是构建单独的功能，而是在实际构建能够改进产品的系统。

如果你想了解更多，欢迎来看看我们的展位。你可以了解 Signal，获取更多信息。非常感谢大家的聆听。

>> [掌声]

[music]

>> 嗨。
<details>
<summary>Original English</summary>
So, if I go back to kind of the question that we started this whole thing with, it's what does an AI engineer do?

I mean, the gap between I think there's a pretty big gap between what's happening in the labs today and what's happening with a lot of businesses. And some of it could just be the data inside of businesses are a lot more messy than what is very constrained and testable inside of a lab. But, AI engineers are kind of the the role to close that gap, and I would think it really starts with tracing everything, tracing the agents you're actually building, running evals, so being able to learn how to test these test these products that we're really building, and then how do you build a system so that agents can actually improve from the telemetry that's actually being collected so that you're no longer just building individual features, but you're actually building the system to improve to improve your products.

If you want to learn more, come check out we have a booth. You can check out Signal, learn more, but thank you so much for listening to us.

>> [applause]

[music]

>> Hey.
</details>