---
author: AI Engineer
date: '2026-07-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Btk8wDUVs74
speaker: AI Engineer
tags:
  - context-understanding
  - world-model
  - lambda-architecture
  - ai-agent
title: 从记录系统到上下文系统：构建 monday.com 的智能工作世界模型
summary: 本文探讨了 monday.com 如何通过构建“世界模型（World Model）”将协同系统从单纯的数据记录（System of Record）转变为具备上下文理解能力的系统（System of Context）。重点介绍了双引擎架构（慢引擎与快引擎）的设计，并结合神经科学与 Lambda 架构，阐述了如何解决 AI 助手在任务优先级和关联理解上的局限性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - monday.com
products_models:
  - Monday Sidekick
media_books: []
status: evergreen
---
### 破局：从“记录”到“理解”的转变

**Tomer**: 大家好，非常高兴能来到这里，感谢大家的邀请。今天我们将探讨如何将 **monday.com** 从一个“数据记录系统（System of Record）”转变为“上下文系统（System of Context）”。说实话，这个标题本身在一行字里就讲完了整个故事。

几十年来，我们构建的软件一直在记录发生的事情——每一个任务、每一份文档、每一条消息、每一次状态更新，都只是被塞进记录里。我们今天想讨论的是更进一步：我们希望软件能够真正理解它们之间的连接。

我想从一个我们每个人每天早晨都会问自己的简单问题开始：“我现在应该专注于什么？”

这听起来似乎微不足道，但坦诚地面对自己，如果你问你的 AI 助手——无论是 **Gemini**、**GPT** 还是 **Claude**——如果你曾经输入过这个问题，你得到的可能只是一堆互不相关的要点列表，或者是包装得像一段自信段落的条目。但它并没有真正与你的工作内容联系起来。

事实上，我上周测试了一下，**Claude** 居然建议我去健身房。我不知道这算不算是一种赞美，但这就是它给出的建议。

真正让人沮丧的是，你的助手其实拥有所有这些数据。它拥有所有的看板、任务、电子邮件、**Slack** 消息，只要你连接了它，你接触过的任何数据它都有。但它依然无法真正回答这个问题。它拥有所有的数据，但理解力为零。

所以这是我们面临的真正挑战，也是整个演讲的核心。问题从来不在于数据的缺失或检索（Retrieval），问题在于缺乏“理解”。这是完全不同的两件事，几乎所有人都会把它们混为一谈。理解（Understanding）是我们在整个演讲中要重点关注的词。不是上下文（Context），不是内存/记忆（Memory），不是检索（Retrieval），而是理解。

下面简单介绍一下我们自己。我叫 **Tomer**。

<details>
<summary>Original English</summary>

**Tomer**: Um, hey everyone. Uh, we are super excited to be here. Thanks for having us. Uh, today we're going to talk about how we shift monday.com from a system of record, uh, into a system of context. And honestly, the title tells the whole story, uh, in just a single line.

Uh, for decades, we built, uh, software that records what's happened, um, every task, every document, every message, um, every status update, um, just put into the record. What we want to talk today is like take it a step further. Uh, we want software that actually understands the connection between them.

So I want to start from a simple question that each one of us asks himself every morning: um, what should I focus on right now? Um, it sounds almost trivial, but, uh, to be honest with yourself, if you ask your agent, whether Gemini, GPT, or even Claude, um, if you ever typed this question, you probably got a list of bullets, um, not related to each other, um, list of like items dressed up like a, a confident paragraph. Um, but, but it's not really, um, um, connected to what you're working on. Actually, I tested last week and, uh, Claude asked me to go to the gym. I don't know if it's a compliment or not, but, uh, this is what he suggested.

Um, and, and what really makes it so frustrating is like your assistant, um, has all this data. It has all the boards, the tasks, the emails, the Slack messages, everything that you ever touched if you connect it. Um, but it still can't really answer it. Um, it has all the data. Um, but it has zero understanding.

Um, so this is the real challenge we are facing. Um, this is the heart of the entire talk. The problem was never the missing of data, the retrieval. The problem is like the missing understanding. Uh, those are two totally different things, and almost everyone mixes between them. Understanding is the word that we're going to focus the entire, the entire talk. Not context, not memory, not retrieval, understanding.

So um, quick about ourselves. My name is Tomer.

</details>

### AI 助手面临的核心挑战

**Omri**: 我的名字是 **Omri**。这位是 **Tomer**。我们都是 **monday.com** 的工程经理，致力于解决我们接下来要讨论的这个问题。

介绍一下我们所处背景的信息。**monday.com** 是一家全球软件公司。我们构建了一个工作平台，被成百上千个团队所使用。对于本次演讲来说真正关键的部分是，**Monday** 是工作发生和存在的地方。我们帮助公司完成工作，而不仅仅是保存数据记录。每个项目、每个任务、每个决定、每次会议、笔记、待办事项，一切都会记录到系统中。

我们的使命一直是帮助团队实现他们的业务成果。无论你是销售人员——我们希望能帮助你创建一个 **SDR 代理**来呼叫你的潜在客户并帮助你销售产品；如果你是财务团队或市场营销团队，我们希望帮助你进行研究。对于每个学科，我们都想帮助你完成工作。在平台上，我们有四个重大的赌注（Bets）：我们有 **Monday Sidekick**（今天主要讨论它）、如果你想构建自己的软件可以使用 **Monday Vibe**、如果你想在平台中创建自己的代理可以使用 **Monday Agent**，而如果你想要更确定性的工作流，我们有 **Monday Workflows**。

但今天我们将专注于 **Sidekick**。**Sidekick** 是你的智能 AI 个人助手，它理解你的工作，思考并与你一起执行，就像落在你肩膀上的一只鸟。它了解你，了解你的业务，在方方面面帮助你的工作，以你习惯的方式和语调与你协同。它让你保持完全的控制。

但是，把所有这些要点落地并兑现这些承诺是非常困难的。让我们来谈谈为什么它这么难，这里有三个原因。

首先，想象一下一个助手坐在绝对所有事情的顶端。你有你的 **Slack** 消息，有你所有会议的记录，有绝对的一切。这很美好，但同时也很压倒性，因为就现状而言，到处都堆满了记录之墙。那为什么要在它们之间建立连接会这么难呢？

有三个原因。

第一，我们称之为“**代理差距（Agent Gap）**”。当代理知道要做什么时，每一个代理在执行任务时都非常敏锐。但是，当需要去主动发现问题时，它有时就会迷失。如果我要求我的代理：“请帮我起草并回复客户的升级申诉邮件”，它能做得非常出色。它知道怎么做，它会获取上下文，完成工作。但如果问它：“我应该先专注于什么？”它只能靠猜，因为它不理解我的优先级是什么，我是谁。即使你拥有记忆之类的东西，它依然不知道问题所在。

第二，我们虽然拥有记录，但我们没有“**含义（Meaning）**”。记录从来不会说明它自身的含义。让我们从我们的开发流程中打个比方。

假设你在 **GitHub** 中有一行代码。你看着代码，也许它上方有一个注释，这很好。但你并没有真正理解为什么有人会写下这行代码。今天，我们都不再亲自动手写每一行代码了。但在过去的某个时刻，有人写下了这行代码。如果你真的想知道原因，你可以查看 Git Blame，通过提交日志（Commit Log）来理解为什么有人这样做。但如果你想了解得更深，你可以去查看 **PR（拉取请求）** 并阅读其描述。如果你真的想追根溯源，你可以去你的 **Monday** 看板，看看哪个 PR 连接到了这个条目，从而明白这行代码是因为某个客户投诉了某些问题而产生的。这就是我们试图构建的“含义连接”。

第三，在运行时（Runtime）实时构建含义是非常具有挑战性的。当有人提出问题的那一刻再去做这件事，实在太迟了，你根本做不到。因此，对上下文的理解必须提前完成，你需要在别人提问之前很久就将其构建好。

这就是为什么我们构建了我们正在构建的东西——我们正在构建 **Monday 世界模型（World Model）**。这就是我们所说的 **Monday 世界模型**。它帮助你理解为什么这很重要、如何帮助你、你是谁，以及什么不该做。它是跟随你工作的上下文，它理解你是谁，而它绝不仅仅是一个更大的 Prompt 或更长的上下文窗口，它与我们目前所知的东西完全不同。

在 **Tomer** 讲解我们如何构建它之前，我想先说明它不是什么：它不是一个检索问题。问题从来不是获取数据，我们拥有所有的数据，拥有与所有我们想要的提供商的连接，拥有所有的 **MCP**。问题在于真正去理解它是如何运作的，理解每一个实体如何相互连接。

那么，请 **Tomer** 继续。

<details>
<summary>Original English</summary>

**Omri**: My name is Omri. This is Tor. Um uh we both engineering managers at monday.com working on exactly uh the problem that we going to talk about a little a little bit context about where we coming from. Uh monday.com is a global software company. Uh we build a work platform uh used by hundreds of thousands of teams. Um and the part that really mattered for the talk is that Monday is where the work um lives. uh we help companies to doing the work not just like saving records. Every project, every task, every decision, every meeting, the notes, the action items, everything logs logged into the system.

And our mission has always been to help the teams to achieve their business outcomes. Whether you are a salesperson, so we want to help you like create an SDR agent that calls to your prospects and help you sell the product. And if you are like a finance team or marketing we want to help you uh with the research. So each one of the disciplines we want to help you to doing the job and together we have like four big bets on the platform. We have like Monday Sidekick we're going to talk about it mostly today. Uh Monday Vibe if you want to build your own software. Monday Agent if you want to create your own agent into the platform and like if you want some more deterministic flows we have like Monday Workflows but today we're gonna focus on Sidekick.

Um Sidekick is your intelligence AI personal assistant that understands your work, thinks and executes with you like a bird on your shoulder. Uh he knows you, he knows your business, um it helps you with your work on every aspect. Uh he works the way you do uh with your tone. Um um it keeps you totally in control but like putting all these bullets and uh building all these promises is really hard. Um so let's talk about why it's hard and there are three points for that.

Um first like picture one assistant sitting on top of absolutely everything. You have your, your Slack messages. You have all the notes for your meetings. Um absolutely everything and it's beautiful and overwhelming at the same time because as it stands like there's a wall of records everywhere. Um so what why it's making so hard to connect between them. There are three reasons for that.

One is something that we call the agent gap. Your agent, every agent is really sharp at doing tasks um when you, when he knows what to do. Um but he sometimes is lost to find them, find the problem. Um if I ask my agent like please help me draft and reply to like the escalation from a customer, he nailed it. He knows how to do it. He takes the context. I like doing the work but asking him what should I focus on first, he guesses because he doesn't understand what is my priority, who am I. It doesn't matter if you have a memory or something, he still doesn't know what is the problem.

The second problem is like um we have the records but we don't have the meaning. Um a log never says what it means. Let's take an analogy from our development flow. Let's say that you have one line of code in your GitHub. You look at a code, maybe there is a comment on top of it. Nice. But you don't really understand why someone wrote this line of code. Today, no none of us is writing code. But somewhere in the past, someone wrote this code, line of code. And if you really want to know, you can go to Git Blame and understand uh from the commit log what why why someone did it. But if you want to go further, you can go to the PR and maybe read the description. And if you really want to go hard, you can go to your Monday board and see which PR connected to this item and understand that this line of code came because some customer complained about something. So this is what we're trying to build.

And the third point that is a bit challenging as well is like um it's really hard to build ahead of time um at runtime um the meaning of things. Um it's really too late. Um you simply can't do something like that the moment someone asks the question. So understanding, understanding of the context has to be ahead of time. Um you need to build it much before someone asks the question.

Um and this is why we have built what we are building. We are building, uh, the Monday world model. This is what we call the Monday world model. Help you um understand why this matters, um how to help you, who you are, when and, and what's not to do. Um it's the context that follows your work. Um he understands who you are and it's simply not a bigger prompt. Uh it's not a longer, uh, context window. It's a totally different um from from what we know until now.

First before like Tor going to talk about how we build it. What it's not: it's not a retrieval problem. The problem has never been getting the data, we have all the data, we have all the connections to all the providers that we want to get, all the MCPs. The problem is really to understand how it works, understand how each one of these entities connects to each other. So go ahead.

</details>

### 慢引擎与快引擎：世界模型的技术实现

**Tomer**: 谢谢大家。大家好。那么，什么是数据模型？我们收集用户成千上万的数据点，包括每一次看板条目的状态变更、他们的活动日志、消息以及会议，并构建出三个可供代理进行推理的要素。

第一，**用户工作的结构化方式**：他们的关键实体、关系以及它们之间的连接。什么依赖于什么，Slack 中的一条消息如何连接到一个任务，谁在阻塞谁。

第二，**当前状态的即时快照**：这些实体之上的实时信号。什么是逾期的，当前什么具有关键的紧迫性，你一直在与哪些同事积极合作，以及原因是什么。

第三，**我们在时间跨度上学到的用户画像**：这些是长期的决定和结果、工作模式和节奏，它们被蒸馏成一个持久的配置文件（Profile）。

那么，我们如何构建这个数据模型呢？我们使用两个运行在不同时间窗口和调度计划上的引擎。

一个是运行在长长的时间窗口上、用于学习用户及其工作的**慢引擎（Slow Engine）**；另一个是读取当前发生的事情并分析其如何影响用户工作的**快引擎（Fast Engine）**。一个了解你，另一个了解你的一天。

首先是慢引擎。它以用户数周的活动作为上下文，挖掘其中的模式：用户属于哪种角色画像（Persona）、他们的日常惯例（Routines）、工作节奏、他们与谁协作、他们的主要目标和当前项目。这些模式被提炼成一个持久的配置文件，每次配置文件起作用时，它都会得到强化。这个引擎试图随着时间的推移，精准学习用户到底是谁以及他们是如何工作的。

快引擎则相反。它以短期且近期的窗口作为上下文，重新计算用户当前状态的一组实时信号：服务器在做什么，什么事情突然变得紧急，你被卷入了与哪些同事的协同中。这个引擎试图理解你的一天，并且更新得非常频繁。

这种“快慢引擎”的双重划分并不是我们发明的，它同时存在于两个完全不同的领域。

在神经科学中，这种划分被称为“**互补学习系统（Complementary Learning Systems）**”。而在数据处理架构中，它被称为“**Lambda 架构（Lambda Architecture）**”。我们将相同的概念应用到了我们构建代理数据模型的方式上。

我们的大脑使用相同的机制。每一个重要的经历都会被**海马体（Hippocampus）**瞬间捕捉，而随着时间的推移，**新皮质（Neocortex）**将这些经历蒸馏为持久的教训和认知。

在数据基础设施中也是如此。一个针对近期实时窗口的快速“速度层（Speed Layer）”，以及一个针对完整历史进行重构的慢速“批处理层（Batch Layer）”，两者最终合并为一个统一的“服务视图（Served View）”。两个不同领域的人不约而同地得出了相同的想法，这就是我们尝试应用到我们数据模型中的东西。

那么，这一切是如何整合在一起的呢？

我们从用户工作的任何地方收集数据：**Monday**、**Slack**、电子邮件、日历，并将其转化为数据结构、信号和模式。两个引擎在后台离线且提前（Ahead of Time）在这些数据之上进行预计算。当用户与 **Sidekick** 交互时，系统会针对近期活动重新计算一小部分薄薄的逻辑，然后将整个上下文提供给代理。**Sidekick** 随后可以决定何时以及如何遍历并从数据模型中检索上下文，并准备好在这些数据之上进行推理。

以这种方式构建为我们开箱即用（Out of the box）地带来了两种行为：

第一，**数据模型具有极强的韧性（Resilient）**。数据源是相互隔离的，因此一个坏掉的数据源不会破坏其余的部分。而且在服务运行阶段（Serve Time）运行的轻量逻辑层会根据实时数据验证一部分上下文，而其余部分则回退到上一次验证过的上下文。所以它会优雅地降级，但不会彻底崩溃。

第二，它能真正理解**信息的紧急程度（Urgency of Facts）**。它能够理解何时以及如何主动通知用户，何时又该保持沉默。

而最关键的部分在于，这种机制是**具叠加效应的（Compounding）**。每天的数据被捕获，数据层被填补，画像也变得更加敏锐。添加一个新的数据源被刻意设计得很廉价，并且只会带来正向贡献。因此，认知边界只会不断扩大。它看过的越多，理解得就越多；理解得越多，你就越能依靠它。

当然，这个数据模型是独特的，它因你独特的工作方式而定制。

我们并不假装这能解决所有问题。这个模型本身相对于真实的现实世界总是存在滞后的。新用户还没有可靠的数据来供系统推理，而且信号中也带有我们自己内置的偏见。因此，最难的部分其实是从噪音中分辨出重要的部分。但这是一个我们可以随着时间的推移不断丰富、测试和改进的架构设计。谢谢大家。

<details>
<summary>Original English</summary>

**Tomer**: Thank you. Hi everybody. Um so what's the data model? We collect thousands of data points on the user—every item status change, their activity log, messages, and meetings—and construct three things the agent can reason over.

The first is how the user's work is structured, their key entities and relationships and connections between them. What depends on what, how a message in Slack connects to a task, who's blocking whom. The second is a current snapshot, live signals over those entities, what's overdue, what's critically urgent right now, which co-workers you've been actively working with, and why. The third is what we can learn about the user over time. There are decisions and outcomes, work patterns and cadences distilled into a durable profile.

So how do we build that data model? Um we use two engines running on different time windows and schedules. A slow engine that runs on a long time window and learns the user and their work, and a fast engine that reads what's happening right now and how it affects the user's work. One knows you and the other one knows your day.

First, the slow engine. It takes as context users' activity over weeks and mines it for patterns and the type of persona the user is, their routines, their work rhythm, who they collaborate with, their main goals, and current projects. Those patterns get distilled into a durable profile and every time a profile holds, it's reinforced. This engine tries over time to learn who exactly the user is and how they work.

The fast engine is the opposite. It takes as context a short recent window and recomputes a set of live signals over the user's current state. What server do, what's suddenly urgent, which co-workers you've been pulled in with. This engine tries to understand your day and updates frequently.

Uh this split isn't something we invented. It's present in two totally different fields. In neuroscience, this split is referred to as complementary learning systems. And in data processing architecture, it's referred to as a lambda architecture. We apply the same concepts to how we construct the agent's data model.

Our brain uses the same split. Uh every important experience gets captured instantly by the hippocampus and over time the neocortex distills those into durable lessons. In data infrastructure, the same—there's the same split. A fast speed layer over a recent real-time window and a slow batch layer over the full history that gets recomputed and the two are merged into a single served view. Two different fields landed on the same idea and that's what we're trying to apply to our data model.

So how does it all come together? We collect data from everywhere our users work—uh Monday, Slack, emails, calendar—and we turn it into data structures, signals, and patterns. Both engines precompute on top of that offline and ahead of time. And when a user engages with Sidekick, a thin slice of logic is recomputed for recent activity, and the entire context is served to the agent. Sidekick can then decide when and how to traverse and retrieve context from the data model itself, and it's primed to reason on top of it.

And building it this way gives us two behaviors out of the box. The data model, it's resilient. Sources are isolated so a bad feed can't break the rest. And the thin layer of logic that runs at serve time verifies part of the context against live data while the rest falls back to the last verified context. So it degrades gracefully, but it doesn't fail.

Second, it actually understands the urgency of facts. It's able to understand when and how it should be proactive and notify the user and when it should stay silent.

And the crucial part is that it compounds. Every day the data is captured, the layers fill in and the profile sharpens. And adding a new data source is deliberately cheap and only contributes. So the surface only grows. The more it sees, the more it understands. And the more it understands, the more you can lean on it. And the data model is unique. It's unique to how you work.

We're not pretending this solves everything. Uh the model itself is always trailing the actual live world. New users have no reliable data to reason from yet, and signals have our own biases built in. So the hardest part is actually telling the important parts from the noise. But this is an architectural design that we can enrich and test and improve over time. Thank you.

</details>

### 从面包屑中重构个人工作画像

**Omri**: 那么，回到我们最初的问题：“我现在应该专注于什么？” 

现在 **Sidekick** 能够真正回答这个问题了。让我们来看看它是怎么做到的。

首先，正如 Tomer 所说，我们收集所有的数据点，我们称之为“面包屑（Breadcrumbs）”。例如我目前正在处理的看板、过去一个月的电子邮件、会议的转录文本、我从这些会议中得到的所有待办事项，然后我们在后台离线处理它们。

我们能够看到你日历的完整全貌，这有助于我们理解模式。因此，如果你和你的 VP 们有每两周一次的例会，我能知道你明天有另一个会。我们甚至能结合过去几天的 Slack 消息，来分析你是否在 Slack 里说了一些你在与团队的每日站会（Daily Standup）中没有提到的相关内容。

我们获取所有这些数据，并通过快引擎或慢引擎来处理它们。

慢引擎为你构建某种画像。所以你可以在界面顶部看到，比如判定 Omri 是一个工程经理。我们知道我正在负责两个项目：**Sidekick** 和 **Notetaker**。我来自特拉维夫，以及我每天工作多少小时、每天如何工作。

而快引擎则能够帮助我理解当前的行动项。比如我有三个对其他人的承诺（Commitments）。我必须要给一位发送了邮件但被我漏掉的 VP 进行回复。这只来自于过去一天或几天的窗口，它与今天的内容更为相关。这就是 **Sidekick** 如何回答这些问题的方式。

总结一下，瓶颈从来都不是从哪里获取数据的能力，而是理解你如何将每一个点彼此连接起来。世界上最强大的代理，无论是 **Claude** 还是 **Gemini**，它们默认都不理解你。它需要提前进行处理。这就是我们在 **Sidekick** 中尝试解决的问题。这就是 **Monday 世界模型**。这就是我们正在构建的东西。

如果大家有什么问题的话……我们时间到了。我们就在舞台旁边。非常感谢大家的时间。大家可以在 **LinkedIn** 上关注我们，我们会在该领域发布一些内容。非常感谢大家！

<details>
<summary>Original English</summary>

**Omri**: So back uh back back to the original uh question that we had. What should I focus on right now? Remember the, the question. So now Sidekick can really answer that. Uh let's see how.

So first like Tomer said we collect all the data points, we call it breadcrumbs—for example the board that I'm working on right now, um all the emails from the past uh month, um the transcript for the meeting, all the action items that I got from those meetings—and we processing them offline. Um we see a full picture of your calendar, this is what helps us to understand the pattern. So if you have like bi-weekly with your VPs, I understand that tomorrow you have another meeting, and even Slack messages from the last few days to understand if you say something in the Slack that's relevant that you didn't say in your daily uh standup with the team. We took all this data and we uh process them either fast or slow.

Um the slow builds some kind of like profile on you. So you can see it on the top like Omri is an engineering manager. We, I'm working on two projects: Sidekick and Notetaker. I'm from Tel Aviv. And this is how many hours I have per day and like how I work every day.

And the fast is something that's helped me to understand what is the action item. I have like three commitments that I promised to other people. I have to, to reply to a VP that sending email and I didn't. Um so this is only from the past uh uh day or few days window. This is something that's relevant more for today and this is how Sidekick can answer those questions.

So to summarize it, the bottleneck was never uh the capability where you can, where you take all the data from. It was the understanding how you connect each one of the dots to each other. Um the most capable agent in the world, whether it's like a Claude and Gemini, it doesn't understand you. He needs to process it beforehand. This is what we're trying to solve at Sidekick. Um this is the Monday world model. Uh this is what we're building. Um if you have any question, uh we out of time. We are here uh uh near the stage. Thank you very much for the time. Uh you can follow us on LinkedIn. We post things on, on the area. Thank you very much.

</details>