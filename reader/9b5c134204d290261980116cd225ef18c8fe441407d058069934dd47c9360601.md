---
author: AI Engineer
date: '2026-10-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=F0TNSmbo5hE
speaker: AI Engineer
tags:
  - agentic-system
  - observability
  - software-lifecycle
  - automated-evaluation
title: 基于链路追踪与评估实现智能体软件生命周期的自动闭环
summary: 研讨会介绍了智能体因非确定性而需要以链路追踪作为真相来源，阐释了如何通过启用 OpenInference 与可观测性工具收集执行数据，并利用自动化评估及 Signal 工具基于追踪记录定位问题、生成回归测试乃至自动创建修复 PR，以闭环智能体软件开发生命周期。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Arize AI
products_models:
  - Signal
  - OpenInference
media_books: []
status: evergreen
---
<!-- chunk 1/4 -->

### 欢迎与研讨会介绍

好的。大家上午好。感谢大家再次回来。

<details><summary>Original English</summary>OK. Hello everyone. Thank you for coming back.</details>

你们当中有谁参加了今天上午的 101 课程？好的。看来我没有把大家吓跑。非常感谢。

<details><summary>Original English</summary>. Who among you was at session 101 this morning? OK. So, I didn't scare everyone. Thank you very much.</details>

呃，那些操作说明已经在屏幕上放了 10 分钟。我真希望你们已经照着做了，因为这里的 Wi-Fi 非常差，所以克隆那个代码仓库需要很长时间。嗯。

<details><summary>Original English</summary>Uh, those instructions have been on the screen for the last 10 minutes. I really hope you've done them, because the Wi-Fi here is terrible, so cloning that repository takes a long time. Uh-huh.</details>

如果没有的话，呃，这些说明还会再次出现在屏幕上，你们还会有机会照着去操作。呃，不过我们还是开始吧。

<details><summary>Original English</summary>If not, uh, these instructions will appear on the screen again, and you will have another chance to follow them. Uh, but let's get started.</details>

这里是“Vice Production 201”。我们接下来将讨论如何自动闭环软件开发生命周期。

<details><summary>Original English</summary>This is "Vice Production 201". We're going to talk about how we automatically close the software development lifecycle loop.</details>

我们是 Arize AI。我们是监测、监督、监控与评估领域的领先平台。别试图同时说出这两个词，效果不太好。

<details><summary>Original English</summary>We are Arize AI. We are a leading platform for surveillance, oversight, monitoring and evaluation. Don't try to say both of these words at the same time. It doesn't turn out very well.</details>

呃，这是每个人都会展示的那种幻灯片，用来表达：“嘿，我们规模很大。我们非常重要。你们应该关注我们。”没错。我们规模非常大。我们非常重要。很多人在使用我们。这很棒。

<details><summary>Original English</summary>Uh, this is the slide that everyone shows to say, "Hey, we're really big. We're really important. You should pay attention to us." That's right. We are very big. We are very important. Many people use us. This is great.</details>

呃，这是广告环节的最后一部分。我打算……你们可以用任何监控平台来做这件事。我们希望你们选择我们的，但这门课的目标是教你们监控正走向何方。嗯，它正在朝着持续改进演进。

<details><summary>Original English</summary>Uh, and this is the last part of the advertising. I'm going to You can use any monitoring platform for this. We hope you choose ours, but the goal of this class is to teach you where monitoring is headed. Well, and it moves towards continuous improvement.</details>

在今天上午的 101 课程中，我讲了基础知识。我给你们讲了手动操作。我告诉了你们如何在小规模下进行。呃，如何对你们的 AI 应用进行监控，如何将其转化为链路追踪（traces），如何将那些链路追踪转化为评估，以及如何利用那些评估来改进你们的应用。

<details><summary>Original English</summary>In Session 101 this morning, I covered the basics. I told you about manual operations. I told you how to do it on a small scale. Uh, how to get monitoring of your AI application, how to turn that into traces, how to turn those traces into assessments, and how to use those assessments to improve your application.</details>

呃，而今天在这一节中，我们要讨论的是，在我们所处的全新互联网规模下，我们如何做到这一点。所以，呃，我打算讲大约 15 分钟关于它是如何运作的，呃，然后我们就直接进入实战工作坊。

<details><summary>Original English</summary>Uh, and today in this session we're going to talk about how we do that in the new scale of the internet that we've found ourselves in. So, uh, I'm going to talk for about 15 minutes about how it works, uh, and then we'll dive right into the workshop.</details>

不同于 101 工作坊里有许多我的故事，呃，这堂课将尽可能偏向实操。我希望你们有一个可用的编程智能体，如果可能的话，还有我刚才在屏幕上展示的代码仓库。呃，因为我们要给你们的呃智能体布置一项任务。

<details><summary>Original English</summary>Unlike Workshop 101, where there were a lot of my stories, uh, this one will be as practical as possible. I expect you to have a working agent for coding, and if possible, the repository I had on my screen earlier. Er, because we're going to give your er agent a task.</details>

你们安装的代码仓库里已经内置了一大批智能体技能。它们赋予你们的智能体程序员超能力来开展工作，因此你们的智能体在执行你们要求的任何任务时都会瞬间变得非常熟练。然后，我们将使用这些技能来分析我们的链路追踪，并针对我们在智能体运行中发现的问题准备修复方案。

<details><summary>Original English</summary>The repository you installed already has a whole bunch of agent skills. They give your agent programmer superpowers to work with, so your agent will instantly become very skilled at doing anything you ask them to do. We will then use these skills to analyze our traces and prepare fixes for the problem we discover in our agent's operation.</details>

接下来，我们将讨论信号——这是这项技术的未来，在这里我们可以实现智能体规模下的持续自动化改进。

<details><summary>Original English</summary>Next, we'll talk about signal—this is the future of this technology, where we can enable continuous automatic improvement at agent scale.</details>

### 非确定性与链路追踪的作用

那么，从更宽广的视角来看，我们来讨论一下问题到底是什么。

<details><summary>Original English</summary>So, to take a broader view, let's discuss what the problem is.</details>

问题在于智能体是非确定性的。在传统软件中，你可以阅读代码，并能带着某种信心说出那段代码究竟会执行什么。而面对智能体，你毫无头绪。智能体是非确定性的。

<details><summary>Original English</summary>The problem is that agents are non-deterministic. In traditional software, you can read code and say with some confidence what exactly that code will do. With agents, you have no idea. Agents are non-deterministic.</details>

智能体执行数个步骤，做出决策，即便给予它们完全相同的输入，它们也不会产生相同的结果。而且即便它们产生了相同的结果，每次达成该结果所遵循的路径也不一定相同。这意味着你的代码不再是关于智能体正在做什么的唯一真相来源。

<details><summary>Original English</summary>Agents take several steps, make decisions, and even if they are given exactly the same input, they will not produce the same result. And even if they produce the same result, they won't necessarily follow the same path to it every time. This means that your code is no longer the sole source of truth about what the agent is doing.</details>

相反，真相来源是链路追踪，特别是在规模化之下的链路追踪。你需要掌握大量数据来理解智能体在平均意义下正在做什么，而不仅仅是单次运行期间的表现。因为当你构建智能体时，你本质上是在盲目工作。

<details><summary>Original English</summary>Instead, the source of truth is traces, and especially traces at scale. You need to have a lot of data to understand what the agent is doing on average, not just during a single run. Because when you create agents, you are essentially working blindly.</details>

这是你在下载代码仓库时得到的东西：一堆代码和提交信息。这在过去足以理解将要发生什么，但现在不行了。

<details><summary>Original English</summary>Here's what you get when you download the repository: a bunch of code and commit messages. This used to be enough to understand what was going to happen, but now it's not.</details>

取而代之的是，你得到的是链路追踪。链路追踪——对那些错过入门课的人来说——简而言之，就像 AI 应用的日志文件。你的 AI 应用的每一次操作、每一次 LLM 调用、每一次工具调用、每一个智能体步骤——这一切都成为了链路追踪的一部分。

<details><summary>Original English</summary>Instead, you get traces. Traces—for those who missed the introductory lesson—are, in short, like log files for AI applications. Every action of your AI application, every LLM call, every tool call, every agent step—it all becomes part of the trace.</details>

链路追踪可以嵌套，包含其他链路追踪，而这正是 Arise 所处理的对象。它们被发送到我们的服务器，我们为你们提供所观察内容的便捷可视化呈现。

<details><summary>Original English</summary>Traces can be nested, contain other traces, and that's what Arise works with. They are sent to our servers, and we provide you with a convenient visualization of what you see.</details>

在实际操作中，它看起来像这样。这里有一些当前的实时链路追踪。我来打开具体的链路追踪，呃，来自我们今天将要处理的内容，也就是 Wonder Toys 智能体。嗯。

<details><summary>Original English</summary>In practice, it looks like this. Here are some current real-time traces. I'll open up specific traces from, uh, what we're going to be working with today, which is the Wonder Toys agent. Hmm.</details>

你可以看到输入数据、输出数据、智能体工作流、单步操作以及大语言模型的响应。你能得到输入数据、输出数据以及一堆元数据，比如成本或执行时间——全都是你在实践中调试智能体所需要的一切。

<details><summary>Original English</summary>You can see the input data, output data, agent workflow, individual step, and response of the large language model. You get input data, output data, and a bunch of metadata, like cost or execution time—everything you need to debug the agent in practice.</details>

嗯，链路追踪为智能体采取的每一步提供了可见性，而这是一个巨大的进步。如果你能看到你的智能体在做什么，你就会突然注意到，比方说，对于某件看起来很简单的事情，它们却执行了 10 个步骤；或者执行了一个不必要的操作；或者在做成本过高的事情；又或者在你认为应该只需要 1 分钟的事情上花费了 20 分钟。

<details><summary>Original English</summary>Um, tracing provides visibility into every step an agent takes, and that's a huge step forward. If you see what your agent is doing, you suddenly notice that they are taking, say, 10 steps on something that seemed simple, or performing an unnecessary action, or doing something that is too expensive, or spending 20 minutes on something that you think should take a minute.</details>

这就是可观测性的基本价值。这就是为什么可观测性如此流行，甚至在接触到我们所讨论的那些附加内容之前就已如此。

<details><summary>Original English</summary>This is the basic value of observability. That's why observability is so popular, even before you get to the additional things we're talking about.</details>

### 从人工瓶颈到评估与自动化

链路追踪的问题在于，人成为了跟踪循环中的“瓶颈”。

<details><summary>Original English</summary>The problem with tracing is that people become a “bottleneck” in the tracking cycle.</details>

当你部署一个应用时，你会得到一个链路追踪。事实上，每当智能体执行任何操作时，你都会得到一堆链路追踪。当你在生产环境中运行它并拥有每秒数千次请求时，那就意味着数以百万计的链路追踪。

<details><summary>Original English</summary>When you deploy an application, you get a trace. In fact, you get a bunch of traces every time the agent performs any action. When you run this in production and have thousands of requests per second, that means millions and millions of traces.</details>

你可以选择性地检查它们。你可以去阅读你的链路追踪。在开发期间，你能准确看到各个组件正在做什么。在生产环境中，你就会成为“瓶颈”，无法通过一条一条去阅读来获得所有链路追踪的全貌。

<details><summary>Original English</summary>You can selectively check them. You can read your traces. You can see exactly what individual elements are doing during development. In production, you become a "bottleneck" and you won't be able to get an overview of all traces by reading them one by one.</details>

所以解决方案，传统的解决方案——我所说的传统指的是 2025 年的解决方案——就是评估。

<details><summary>Original English</summary>So the solution, the traditional solution, and by traditional I mean the 2025 solution, was evaluations.</details>

评估要么是代码，或者更好的是，由另一个语言模型来分析智能体的表现，审查所有的链路追踪，并根据你的定义判定它们是好是坏。关键在于评分来自语言模型，这意味着它们不仅提供 1 或 0 的评分，还提供解释。它们仿佛在说：“你已经定义了什么是好。因为这样或那样的原因，它是糟糕的。”而这正是整个改进循环的基础。

<details><summary>Original English</summary>An evaluation is either code or, better yet, another language model that analyzes the agent's performance, examines all the traces, and determines whether they were good or bad according to your definition. The thing is that ratings come from language models, which means they provide not just a one or zero rating, but also an explanation. They seem to be saying: “You have defined what is good. "It was bad for this or that reason." And this is the basis of the entire cycle of improvement.</details>

评估可以为你提供机器可读的，或者更好的是，人类可读的解释——如今连机器也能阅读这些解释——说明：“这就是你的评估失败的原因。那是你可以做得更好的地方。”

<details><summary>Original English</summary>Assessments can give you machine-readable, or better yet, human-readable explanations that even machines can read these days, that say, "Here's why your assessment failed. "That's what you could have done better."</details>

而且你可以把这些反馈给编程智能体，随后它将自动改进你的软件。一旦你正确定义了“好”的含义，你无需亲自干预就能闭合软件开发循环。你创造了这座山峰，而你的智能体可以自己去征服它。

<details><summary>Original English</summary>And you can feed that back to the coding agent, which will then automatically improve your software. You can close the software development cycle without your own intervention once you correctly define what “good” means. You create this hill, and your agent can conquer it on their own.</details>

所以，这就把我们带到了 2025 年的评估循环。你从完全没有可见性走向使用链路追踪，再到将链路追踪用于评估，最后能够根据你的链路追踪分析手动进行改进。

<details><summary>Original English</summary>So, that brings us to the 2025 evaluation cycle. You go from having no visibility at all to using traces, then traces in evaluation, and finally being able to manually make improvements based on your trace analysis.</details>

但 2026 年的问题在于，人类在这个循环中再次成为了瓶颈，因为评估现在面对的是极其庞大的规模。你的智能体以极快的速度生成代码。你的应用在大规模下运行。你拥有的评估数量超出了你的处理能力。

<details><summary>Original English</summary>But the problem in 2026 is that humans are once again the bottleneck in this cycle, as evaluation is now dealing with enormous scale. Your agents generate code incredibly fast. Your applications operate at scale. You have more assessments than you can handle.</details>

虽然评估过去能让你将成千上万条链路追踪压缩为分数，但现在其数量如此之多，以至于你作为个人已经无法独自跟踪这一切了。

<details><summary>Original English</summary>And while assessments used to allow you to compress thousands of traces into scores, there are now so many that you as a person can no longer keep track of it all on your own.</details>

这就把我们带到了观测与评估演进的下一个阶段：当我们在以智能体的速度创造解决方案时，我们必须同样迅速地改进它们。我们需要找到一种在规模化下闭环的方法，就像智能体所做的那样。

<details><summary>Original English</summary>This brings us to the next stage in the evolution of observation and evaluation: as we create solutions at the speed of agents, we must improve them just as quickly. We need to find a way to close the loop at scale, just like agents do.</details>

这是正在监测领域发生的一场转变，并且所有人都在同时感受到它。观测正在从人类通过仪表盘进行分析，转变为由智能体进行链路追踪分析。智能体是一种将我们对其他行动的理解进行规模化扩展的方式

<details><summary>Original English</summary>This is a shift that is happening in the surveillance industry, and it is being felt by everyone at the same time. Observation is shifting from dashboard analysis by humans to trace analysis by agents. Agents are a way to scale our understanding of the actions of other</details>

<!-- chunk 2/4 -->

以一种切合当今工作规模和速度的方式来评估智能体。

<details><summary>Original English</summary>agents in a way that is practical for today's scale and speed of work.</details>

因此，当智能体去分析你那些智能体的行为时，你就能在 trace 中检测到信号。比方说，你原本可能会有 10,000 个评估结果，每一个都显示有错误，并且每一个都有单独的解释需要你去阅读；现在不同了，你可以让一个智能体去集中分析这些失败用例，识别出你错误中的信号和模式，然后告诉你：“好的，今天你一共有 10,000 个成功的请求和 1,000 个失败的请求。在这 1,000 个失败请求中，有 100 个是相同的错误。这就是我们要去修复的问题。”当你将从 trace 和评估中获取信号的理解过程自动化时，你能做到的就是这些。

<details><summary>Original English</summary>So, when agents analyze your agents' actions, you can detect signals in your traces. You can, instead of having, say, 10,000 evaluation results, each one saying there was an error, and each one having a separate explanation that you would have to read, have an agent analyze those failures en masse, identify signals and patterns in your errors, and say, "Okay, today you had 10,000 successful requests and 1,000 failed ones." Among this thousand, there are a hundred with the same error. That's what we're going to fix. Here's what you can do when you automate the understanding of signals obtained from traces and estimates.</details>

在 Arize，我们将这个功能做成了一款名为 Signal 的产品，我会在最后谈到它。但这并不是广告。这是在展示向这种全新抽象层级跃迁所能实现的能力。当你从逐条阅读 trace 跃迁到查看评估指标——这是一个新的抽象层级，而从我的评估和 trace 中读取信号，则是更高的层级。因为可观测性从单纯的观察迈向了行动这一大步。

<details><summary>Original English</summary>At Arize, we built this into a product called Signal, which I'll talk about at the end. But this is not advertising. This is a demonstration of what can be done by moving to this new level of abstraction. When you go from reading traces one by one to reading estimates—that's a new level of abstraction, and this is an even higher level: reading signals from my estimates and traces. Because observability takes a big step from simple observation to action.</details>

我们正在从“告诉你发生了什么”的软件，转向“根据你对质量的定义自动优化系统来改进流程”的软件。信号变成了纠正措施。它们变成了自动修复，从而让你进入一个全新的循环。这就是 2026 年的循环：从毫无可观测性，到 trace、评估、信号、自动修正，然后再循环往复。你正在创造一个软件自我纠正、自我完善、不断精进的新世界。这就是我们的理念、愿景以及我们前进的方向。

<details><summary>Original English</summary>We are moving from software that tells you what is happening to one that improves processes by automatically optimizing the system based on your definition of quality. Signals become corrections. They become automatic fixes, which puts you on a new cycle. This is the 2026 cycle where you go from no observability to traces, estimates, signals, automatic corrections and back again. You are creating a new world where software corrects and improves itself, rising to the top. So, this is our concept, vision, and direction we are heading.</details>

### 实操演示与现场准备

现在我们进入实操环节。现场有谁已经注册过 Arize 了吗？噢，太好了。好的。如果没有，现在正是注册的时候。你需要一个 Arize AX 账号。保证是免费的。你还需要这个代码仓库，就是我一开始展示的那个。如果仓库在 Wi-Fi 下加载不出来，试着用手机热点连接；但如果还是不行——别担心。我会在我自己的一份副本上实时演示所有内容，那是我趁着还有 Wi-Fi 时克隆好的。嗯哼。此时有人对这些说明有任何疑问吗？我们有时间，可以暂停一下让大家跟上来。现场有 Arize 的专业人员随时准备协助大家。所以如果你举手，我不会神出鬼没地走过去帮忙，其他人会跑过去协助你。有人需要说明指导方面的帮助吗？请说？对，就是那个。太棒了。

<details><summary>Original English</summary>And now let's move on to practice. Who here has already registered with Arize? Oh, that's good. OK. If not, now is the time to do so. You need an Arize AX account. They're free, I promise. You also need this repository, the same one I had at the very beginning. If the repository doesn't load over Wi-Fi, try connecting via your phone, but if that doesn't work—don't worry. I'll be demonstrating everything in real time on my own copy, which I cloned while there was still Wi-Fi. Uh-huh. Does anyone have any questions about these instructions at this time? We have time, we can pause for you to join in. There are Arize specialists in the hall who are ready to approach you. So if you raise your hand, I won't, you know, creepily approach to help. Someone else will run up to you. Does anyone need help with instructions? Please? Yes, that was it. Class.</details>

那么，在这个示例中，你需要一个 OpenAI API 密钥、一个 Arize space ID 和一个 Arize API 密钥，然后你需要执行 `npm run dev`，这会在本地运行该软件。我已经克隆好了我的那份。我会一步一步来。好的，由于我这边的版本正在运行，该地址已经被占用了。好的。太棒了。

<details><summary>Original English</summary>So, in this example, you will need an OpenAI API key, an Arise space ID, and an Arise API key, and then you need to execute NPM run dev, which will run the software locally. So, I already cloned mine. I will do everything in turn. Okay, the address is already in use because my version is running. OK. Class.</details>

这样我就能在 3000 端口访问这个网上商店了。它叫 Wonder Toys。

<details><summary>Original English</summary>So, this will give me access on port 3000 to the online store. It's called Wonder Toys.</details>

>> 我有一个问题。

<details><summary>Original English</summary>>> Yes, I have a question.</details>

>> 请讲。

<details><summary>Original English</summary>>> Yes.</details>

>> 我在高度受监管的行业工作。现在，伴随着数十亿的 trace、邮件、信号被生成，软件甚至在自我修复，在像金融和医疗这样受到监管的领域，我们该如何运作？在这些领域中，如果它犯了错，如果它产生敌意，如果它试图掩盖自己的错误，我们必须确切知道该怎么做。

<details><summary>Original English</summary>>> I work in highly regulated industries. Now, with billions of traces, emails, signals being generated, and software even self-correcting, how do we operate in regulated areas like finance and healthcare, where we need to know exactly what to do if it makes a mistake, if it becomes hostile, and if it tries to cover up its mistakes?</details>

>> 嗯。

<details><summary>Original English</summary>>> Mhm.</details>

>> 赋予智能体这么大的控制权，我们该如何掌握这些情况呢？

<details><summary>Original English</summary>>> How can we know this by giving so much control to agents?</details>

>> 真不敢相信你会问这个问题，因为对我来说这简直是个绝妙的问题，正好我周三有一场名为《代码审查之死》（"The Death of Code Review"）的演讲，那场演讲就是对你这个问题的解答。所以我强烈推荐你来听这场报告。问题在于，你如何能够信任测试你那些智能体的智能体所编写的代码？它到底能不能正常工作？

<details><summary>Original English</summary>>> I can't believe you're asking this question, because it's a great question for me, because I'm giving a talk on Wednesday called "The Death of Code Review," which is the answer to your question. So I highly recommend you come to this talk. The question is, how can you trust the code written by agents who are testing your agents, and will it even work?</details>

>> 答案非常复杂。这是一整场 20 分钟的报告。所以请务必来参加周三的那场会议。不，这篇 20 分钟的报告已经是我能给出的最简短的概括了。用一句话来回答就是：抽象之上再加抽象，抽象之上还有抽象。但这其中有很多细微差别。我们在 Arize 的金融行业客户现在就已经在这么做了。

<details><summary>Original English</summary>>> The answer is very complicated. This is a whole 20-minute report. So please come to that session on Wednesday. No, a 20-minute report is the shortest summary I could give. The one-sentence answer is abstractions upon abstractions upon abstractions. But there are many nuances to this. We at Arise have clients in the financial industry who are already doing this now.</details>

### 为 Wonder Toys 接入可观测性

让我们回到 Wonder Toys。Wonder Toys 是一种基于智能体的购物体验。你们有给 7 岁孩子玩的玩具吗？我们来看看能不能用。希望它能跑通。这完全是在本地运行的。太棒了。这就是它给我的结果。我可以把它们加入购物车。我可以了解更多详情。这是一个非常有趣的小应用。你可以把商品加入购物车。你可以询问有关商品的信息。你可以做各种有趣的事情。

<details><summary>Original English</summary>Let's go back to Wonder Toys. So, Wonder Toys is an agent-based shopping experience. Do you have toys for 7-year-olds? Let's see if this works. I hope it works. It's all local. Class. This is what it gives me. I can add them to the cart. I can find out more details. This is a very interesting little app. You can add the product to your cart. You can ask about the products. You can do all sorts of interesting things.</details>

从我们的角度来看，重要的一点是目前这里完全没有可观测性。我们根本搞不清楚这个应用里到底发生了什么，因为它没有向任何地方发送任何 trace。所以我们要让我们的智能体来修复它。这是我做过的最注重实操的工坊了，因为所有步骤我都会现场亲自做。

<details><summary>Original English</summary>The important thing from our point of view is that there is currently no observability. We can't figure out what the hell is going on with this app because it doesn't send any traces anywhere. So we will ask our agent to fix it. This is the most hands-on workshop I've ever done, because I'll be doing everything live.</details>

那么，你能使用 Arize AX 在这里添加可观测性吗？哦，没错。等一下。提前运行版。这是错误的文件。你看，我有两份副本。好的。顺便说一句，这是 VS Code 的 Cloud Code 插件。它真的非常好用。它比命令行上的 Cloud Code 好得多。我不知道为什么会有人通过命令行使用 Cloud Code。你看，你可能也在用 Vim 吧。现在谁还会这么说呢？呃，好的。

<details><summary>Original English</summary>So, can you add observability here using Arise AX? Oh, exactly. Wait. Pre-launch. This is the wrong file. You see, I had two copies. OK. By the way, this is the Cloud Code plugin for VS Code. He is truly wonderful. It is much better than Cloud Code on the command line. I don't know why anyone would use Cloud Code via the command line. You see, you probably also use Vim. Who wouldn't be saying that now? Uh, okay.</details>

你能使用 Arize AX 为这个应用添加可观测性吗？你已经有了密钥和一个 `.env.local` 文件。希望这能成功，因为在我尝试的最初版本里，一切都是正常的。看他正在做什么：他正准备去实现可观测性。实现可观测性其实是一个比你想象中简单得多的操作，因为该智能体 SDK（也就是构建它所基于的 OpenAI SDK）本身就已经支持 OpenInference 了。OpenInference 是整个可观测性行业用来追踪 AI 应用程序行为的开放标准。

<details><summary>Original English</summary>Can you add observability using Rise AX to this app? You already have secrets and a dot env.local file. I hope this works, because in the initial version I tried, everything worked. Here's what he's doing: he's going to implement observability. Implementing observability is a much simpler operation than you might imagine, as the agent SDK, the Open AI SDK on which it is built, already supports Open Inference. Open Inference is an open standard used by the entire observability industry to track what AI applications are doing.</details>

这意味着要获得应用的可观测性，你所需要做的仅仅是启用它。你说你已经有了 OpenInference。我使用的是 Arize。这是我的 API 密钥。这是我的端点所在位置。把你已经在生成的这些 trace 全部发送到我的端点，然后让我们在应用里查看它们。Cloud 还在继续运行，所以我们正在做这件事。现在有谁正在跟着做吗？请举手。你们当中有人在做。好的。有谁需要帮助才能跟上到这一步的？仓库里已经安装好了 skills，所以……哦，它就在顶层的 readme 文件里。

<details><summary>Original English</summary>This means that all you need to do to get app observability is simply enable it. You say you already have Open Inference. I use Arise. Here is my API key. This is where my endpoint is located. Send all these traces that you're already generating to my endpoint, and let's look at them in the app. Cloud still works, so we're doing it. Who is doing this right now? Raise your hands. Some of you do. OK. Who needs help getting here? The repository already has the skills installed, so Oh, it's in the top-level readme file.</details>

你需要的那份叫做 `openai-agents-python`。OpenAI agent 还有第二个文件夹——`openai-agents-python-pre-run`，在那里我已经把所有这些步骤都做完了，所以如果你想看它运行起来应该是什么样子，它就在那里。哦，你更新了我的 readme 之类的内容。你太懂我了。你其实不必做这一切的。好的，太好了。看来它已经搞定了。

<details><summary>Original English</summary>The one you need is called Open AI agents pi. Open AI agent There is also a second folder—Open AI agents pi pre-run, where I have already done all this, so if you want to see what it should look like when running, it is there. Oh, you update my readme and stuff. You know me too well. You didn't have to do all this. Okay, great. It looks like it has already done so.</details>

让我重启应用，看看监控是否生效。好的，我回到主页面。我来问它一个新问题。比如说，呃，适合幼儿的鲜艳玩具有吗？适合幼儿的鲜艳玩具，没有吗？那一般的鲜艳玩具呢？羊绒玩具？噢，不。好的，现在你们看到了，这是一场货真价实的现场演示，因为他的数据库出问题了。完美。好的。嗯哼。

<details><summary>Original English</summary>Let me restart the application and see if the monitoring works. So, I'll go back to the main page. I'll ask him a new question. Let's say, uh, what about bright toys for toddlers? Bright toys for toddlers, no? What about bright toys in general? Cashmere? Oh no. Well, now you see that this is a real live demo because he had problems with the database. Perfectly. OK. Uh-huh.</details>

那么，这样做的结果是，我们应该会产生 trace。如果我查看，如果我向你们展示我的 `.env.local`，你们会看到我命名的 Wonder Toys OpenAI Agents Pi 项目。这就是我正要去找的追踪项目。它就在这里。我们可以看到，我们看到了一些追踪信息。这完全展示了我们预期会看到的内容。这向我们展示了输入数据、输出数据、智能体请求以及所有那些东西。

<details><summary>Original English</summary>So, as a result of this, we should have traces. If I look, if I show you my m.local, you'll see that I called the Wonder Toys Open AI Agents Pi project. So, this is the tracing project I'm going to look for. Here he is. And we see, we see some tracing. This shows us exactly what we expected to see. This shows us input data, output data, agent requests, and all that stuff.</details>

现在我要故意问一个我知道他回答不了的问题。把所有标价 6 美元以下的在售玩具展示给我。太悬了。我启动了错误的应用程序。我刚才运行的是之前那个一切正常的版本。这就是为什么我刚才能够做成。各位，真是一场精彩的演示。我现在非常为自己感到骄傲。

<details><summary>Original English</summary>Now I will deliberately ask a question that I know he will not be able to answer. Show me all the toys that are available for under $6. Steeply. I launched the wrong application. I was running a previous version where everything worked. That's why I was able to do it. Great demonstration, friends. I'm very proud of myself right now.</details>

<!-- chunk 3/4 -->

失败。

<details><summary>Original English</summary>Failure.</details>

是的，很好。因此，包含在 OpenAI 非此前目录中的版本没有按价格筛选的功能。我事先就知道这一点，这就是我问这个问题的原因。所以如果我们查看追踪记录，当我点击“live”按钮时我们应该能看到它们。显示所有 6 美元以下的玩具。太棒了，你看它报错了。那么，你还在做什么？入口。一切正常。无论你做了什么，都不是必需的。好的。

<details><summary>Original English</summary>Yes, 

great.  

Therefore,





the 

version 

contained





in 

open 

AI 

in 

a 

non-previous





directory 

does 

not 

have





the ability





to 

filter 

by 

price.





I 

knew 

this 

in 

advance





, 

which 

is 

why 

I 

asked 

the





question.  

So 

if





we 

look 

at 

our





traces, 

we





should 

see 

them





when 

I 

click 

the





"live" 

button.  

Show 

me 

all 

the





toys 

under 

$6.





Fantastic, 

and 

you





see 

it 

throws





an 

error.  

So, 

what 

are 

you





still 

doing?  

Entrance.





Everything 

is 

fine.  

Whatever 

you





did, 

it 

wasn't





necessary.  

OK.</details>

所以，就是这样。我们添加了监控，突然间追踪记录就开始进入我们的应用程序了。我们没有写一行代码。事实上，你甚至不知道我是用什么框架创建这个的。一切都在运行，数据正在发送，现在你可以执行监控的第一阶段了。你可以查看你的追踪记录。

<details><summary>Original English</summary>So, 

that's 

all.  

We





added 

monitoring, 

and





suddenly 

traces





started 

coming 

into





our 

application.  

We 

didn't





write 

a 

single





line 

of 

code.  

In 

fact





, 

you 

don't 

even 

know





what 

framework 

I





used 

to





create 

this.  

Everything





is 

working, 

the 

data





is 

being 

sent, 

and 

now





you 

can 

perform 

the





first 

phase 

of





monitoring.  

You





can 

view





your 

traces.</details>

那么，让我们让智能体告诉我们如何进入下一阶段，开始形成闭环。呃，“你能看一下我的追踪记录并找出哪里出了问题吗？”一个标准的现成写代码智能体是不会知道这个的。但是，当你安装一个仓库时，你就安装了一整套技能（skills）。呃，所以他应该从这些技能中知道，呃，去哪里做这件事。除了我在……噢，是的。噢，它起作用了。好的，就是这样。

<details><summary>Original English</summary>So





, 

let's 

start 

closing 

the





circle 

by 

asking





our 

agent





to 

tell 

us 

how 

to





move 

to 

the 

next





phase.  

Uh, 

can 

you





look 

at 

my





traces 

and 

find





what's 

wrong?





So, 

a 

standard





ready-made 

agent 

for





writing 

code





will 

not 

know 

this.  

However,





when 

you 

install





a 

repository, 

you





install 

a 

whole





set 

of 

skills.  

Uh,





so 

he 

should 

know 

from





these 

skills, 

uh, 

where 

to





do 

it.  

Besides 

the 

fact 

that





I'm 

in 

Oh, 

yeah.  

Oh, 

it 

works





.  

Okay, 

that's 

it.</details>

厉害。呃，在这个时刻我会点击“全部确认”，而我的安全经理肯定会冲我发脾气。呃，所以我让它使用我给它的技能直接从 AX 下载我的追踪记录。它已经有了 API 密钥。它有，它有，呃，一个端点。所以，它就是使用 AX 命令行来做所有这些事情的。它加载了我们在界面中看到的相同的追踪记录，并且可以通过编程方式对其进行检查。它总结了 span 的类型、状态和错误。这太棒了。

<details><summary>Original English</summary>Steeply.  

Uh 

This 

is 

the





moment 

when 

I 

would





click 

"yes 

for





all" 

and 

my





security 

manager 

would 

throw





me 

a 

tantrum.  

Er,





so 

I'm 

asking 

him





to 

use 

the 

skills





I 

gave 

him 

to





download 

my





traces





directly 

from 

AX.





He 

already 

has 

an 

API 

key.





It 

has, 

it 

has, 

uh, 

an





endpoint.  

So, 

there's 

the





AX 

command 

line





that 

it





uses 

to





do 

all 

these





things.  

And 

it





loads 

the 

same





traces 

that 

we





saw 

in 

the 

interface,





which 

it 

can





programmatically





examine.  

It





summarizes 

the 

types 

of





spans, 

statuses, 

and





errors.  

This 

is 

great.</details>

呃，再次说明，这个编码智能体，呃，确切地知道这里发生了什么，因为我们已经建立了技能。正是这些技能为它提供了这里的所有信息。它正在调查质量问题，而这正是我所要求的。因为没有报错的 sleep。只有一堆返回 200 并显示一切正常的 span。呃，而且它已经找到了我让它找的具体问题。产品搜索工具响应速度可疑地快，只有 1 毫秒。因此，它会发现一些低质量信号并向我们报告。

<details><summary>Original English</summary>Uh





, 

again, 

the





coding 

agent, 

uh,





knows 

exactly 

what's





going 

on 

here 

because





we've 

already 

established





the 

skills.  

It 

is 

the 

skills 

that





provide 

him 

with 

all 

the





information 

here.  

He 

is





investigating





quality 

issues, 

which





was 

exactly 

what 

I 

requested.





Because 

there 

were 

no





sleeps 

with 

errors.    

There





were 

just 

a 

bunch 

of





spans 

where 

he





would 

return 

200 

and 

say





everything 

was 

fine.  

Uh, 

and





he 

already 

found 

the





specific 

thing 

I





asked 

him 

to 

find.    

The









product 

search 

tool





responded 

suspiciously 

quickly, 

at 

1





ms.  

So, 

it 

will 

find





some





low-quality 

signals 

and





tell 

us 

about





them.</details>

谁的已经跑通了？谁还在克隆仓库？

<details><summary>Original English</summary>Who 

already 

has 

this





working?  

Who 

is 

still





cloning 

the 

repository?</details>

答：不，插件、技能在名为 `.agents/skills` 的目录中，你的编码……你在用哪个智能体？它实际上是在根目录中，所以你应该在根目录下打开该智能体，然后导航到那个目录。是的。`npx skills install arise-ai` 会直接安装所有这些技能。

<details><summary>Original English</summary>A. 

No, 

the 

plugin, 

skills





are 

in 

a





directory 

called





.agents/skills, 

and 

your 

coding





...which 

agent 

are 

you





using?  

It 

is





actually 

in 

the





root 

directory





, 

so 

you 

should 

open





the 

agent 

in 

the 

root





directory 

and 

then





navigate 

to 

that 

directory.  

Yes





.  

NPX 

skills 

install 

arise-ai





installs 

all 

these





skills 

directly.</details>

不好意思，你说什么？

<details><summary>Original English</summary>Excuse 

me, 

what 

did 

you 

say?</details>

你……而这真是一个谜，因为这个程序曾经有一个版本必须通过 X 登录，而我修改过了，让你不必通过 X 登录。正如你所看到的，当我运行这个程序时，我不需要通过 X 登录。不知怎么的，它把你必须通过 X 登录的版本给翻出来了。我完全不明白这是怎么发生的。代码真叫人捉摸不透。我稍后得和你谈谈你究竟是怎么弄到这一步的。

<details><summary>Original English</summary>You 

And 

this 

is 

a 

mystery,





because 

there 

used 

to 

be 

a





version 

of 

this 

program





where 

you 

had 

to





log 

in 

through 

X, 

and 

I





changed 

it 

so 

that 

you 

didn't 

have 

to









log 

in 

through 

X. 

As 

you





can 

see, 

when 

I





ran 

this 

program,





I 

didn't 

have 

to





log 

in 

through 

X.





Somehow 

it





dug 

up 

the 

version 

where 

you





had 

to 

log 

in 

through 

X.





I 

don't 

understand





how 

that 

happens 

at 

all.





The 

code 

is 

mysterious.  

I'll





have to





talk 

to 

you





later 

about 

exactly 

how





you





got 

to 

this 

point.</details>

### 分析追踪与自动修复

好的。所以，Claude 终于缓过劲来，告诉我追踪记录里发生了什么。呃，42% 的搜索没有返回结果。所有 null 搜索查询都是退化的。智能体调用了所有参数均为 null 的产品搜索，从而产生了一个无意义的搜索，返回了目录中的第一个产品。最小年龄等于最大年龄，精确的年龄过滤把范围缩得太小了。呃，追踪调用栈有三种类型的智能体。主要问题是产品搜索的过滤逻辑。当模型提供数据时，向量搜索和关键词分类过滤器往往返回空结果。修正应该在工具端进行。

<details><summary>Original English</summary>OK.  

So,





Claude 

finally 

pulled 

himself 

together





and 

told





me 

what 

was 

happening





in 

the 

traces.  

Um, 

42%





of 

searches





yielded 

no





results.





All





null 

search





queries 

are 

degenerate.  

The 

agent





invoked 

a





product 

search 

with 

all





null





arguments, 

which





created a





meaningless 

search





that 

returned 

the 

first





product 

in 

the 

catalog.





The 

minimum 

age





is equal to





the 

maximum 

age,





precise 

age





filtering





narrows 

the 

circle 

too 

much.  

Um, 

the





tracking 

stack 

has 

three





types 

of 

agents.  

The 

main





problem 

is 

the 

product





search 

filtering 

logic





.  

Vector





search 

and





keyword 

category 

filters





often 

return





empty 

results





when 

the 

model 

provides





data.  

The 

correction 

should





be 

on 

the 

side 

of





the 

tool.</details>

嗯。我今天早上尝试这个的时候，我只有一条追踪记录，而那条追踪记录表明没有找到价格。那么，按价格筛选有问题吗？我看看它是否能在已有的追踪记录中找到它。但是，剧透一下：即使它没找到，我们也会迫使它添加价格过滤功能。很好。没错。根本没有价格过滤。厉害。让我们把价格过滤添加到这个应用中吧。

<details><summary>Original English</summary>Em.  

When





I 

tried 

this 

this 

morning,





I 

only 

had 

one





trace, 

and 

that 

trace





indicated 

that





the 

price 

was 

not 

found.





So, 

is 

there 

a 

problem 

with





filtering 

by 

price?





I'll 

see 

if





he 

can 

find 

it 

in 

the





traces 

that 

are 

already 

there.  

But,





spoiler 

alert: 

even 

if





he 

doesn't 

find 

them, 

we'll





force 

him 

to 

add 

a









price 

filtering 

feature.  

Good.  

That's 

right





.  

There 

is





no





price 

filtering 

at 

all.  

Steeply.  

Let's 

add





price 

filtering





to 

this 

app.</details>

智能体变聪明时可能发生的一件事，就是它们可能变得过于聪明。这个智能体注意到我在旁边有一份这个应用程序的副本，而我在那里已经解决了这个问题，于是他就直接从之前解决的版本中复制代码。这不是他今天早上做的事，因为当时目录里没有现成的解决方案，但它仍然能跑通。所以，我们就让它这么做吧。我们就随它聪明去，直接复制它今天早上创建的解决方案，因为何乐不为呢，Claude？非常感谢。

<details><summary>Original English</summary>One 

of 

the 

things 

that 

can





happen 

when





agents 

become





intelligent 

is 

that





they 

can 

become





too 

intelligent.





This 

agent 

noticed 

that





I 

had 

a 

copy 

of





this 

application 

nearby 

where 

I 

had





already 

solved 

this





problem, 

and 

he





simply 

copied 

the 

code 

from 

the





previously 

solved





version.  

This 

is 

not 

what





he 

did 

this 

morning, 

because 

there









was 

no 

ready-made





solution 

in 

the 

directory 

at 

that 

time, 

but 

it 

will 

still





work.  

So, 

we'll





just 

let





him 

do 

it.  

We'll





let 

him 

be





smart 

and





copy 

the 

solution 

from





what 

he 

created





this 

morning, 

because





why 

not, 

Claude?





Thank 

you 

very 

much.</details>

很好。呃，所有这一切中最酷的事情是，我再次完全没有碰代码，对吧？我所做的只是说：“嘿，找找毛病。”它找到了问题。我说：“嘿，这个特定的问题怎么样？你能修复这个特定的问题吗？”它回答说：“好的，我会处理。”这就是智能体化编程（agentive programming）的乐趣。嗯。太棒了，既然它已经在从另一个复制解决方案了，呃，它就已经搞定了。

<details><summary>Original English</summary>Good.  

Um,





the 

coolest 

thing 

about 

all 

of 

this 

is 

that





again, 

I





didn't





touch 

the 

code 

at 

all, 

right?





All 

I 

did 

was





say, 

"Hey, 

look 

for





trouble."  

He





found 

the 

problem.  

I





said, 

"Hey, 

what 

about





this 

particular





problem? 

Can 

you





fix 

this 

particular





problem?"  

And 

he





replied, 

"Yes, 

I 

will





do 

it."  

This 

is 

the





joy 

of





agentive





programming.  

Em.





Brilliant, 

since





he 

was 

already 

copying





the 

solution 

from 

another, 

er,





he 

already 

did 

it.</details>

那么，让我们回到玩具板块。“显示所有 9 美元以下的玩具。”然后，是的！我想给我鼓鼓掌吧。谢谢。或者实际上，是给 Claude。呃，所以现在如果我们查看我们的记录，我们可以看到“显示所有 9 美元以下的玩具”。我们在响应中得到了输入和输出，包括所有那些 1 美元以下和 9 美元以下的玩具。呃，这就是我们试图实现的。

<details><summary>Original English</summary>So, 

let's 

go 

back 

to 

the





toys 

section.





Show 

me 

all 

the





toys 

under





$9.  

And 

yes!





Applause 

for 

me, 

I 

guess.





Thank 

you.  

Or, 

actually,





Claude.  

Um, 

so 

now





if 

we 

look 

at





our 

records, 

we





can 

see 

"





show 

me 

all 

the





toys 

under





$9."  

And 

we





got 

our 

input





and 

output 

in





the 

response, 

including





all 

those 

toys





under 

$1 

and 

under 

$9.  

Uh





, 

that's 

what 

we





were 

trying 

to 

achieve.</details>

我们试图形成闭环，从“我们对这个程序完全没有任何监视”到“我们有了监视，知道发生了什么”，再到“自动发现并自动修复问题”，我们完成了这个闭环。

<details><summary>Original English</summary>We 

tried





to 

close 

the 

loop 

from 

"we





have 

no





oversight 

of 

this 

program 

at 

all"





to 

"we 

have 

oversight,





we 

know 

what's





going 

on," 

to 

"





automatically 

finding





and 

automatically





fixing 

problems,"





and 

we 

closed 

that





loop.</details>

### Signal 智能体与自动化安全守护

但是如果，呃，你可以更进一步呢？呃，如果你根本不需要问任何问题呢？如果你的系统就是能自动检测代码问题、提出修复建议并自行决定修复它们呢？这就是我们问自己的问题，呃，这就是我们创建这个名为 Signal 的东西的时候。呃，Signal 是一个在 Rise AX 内部运行的智能体，它会持续监控你所有的追踪记录。它默认每 6 小时运行一次，但这是可以自定义的。呃，它做的是我们刚才在 Cloud Code 中手动做的事情，但它是在 AX 内部一直自动执行的。它读取你的追踪记录，寻找模式，发现错误，并提出修复建议。

<details><summary>Original English</summary>But 

what 

if, 

uh,





you 

could 

go 

a 

little





further?  

Uh, 

what 

if 

you





never 

had 

to





ask 

anything?  

What 

if





your 

system 

just





automatically 

detected





code 

issues,





suggested





fixes, 

and





decided 

to 

fix





them 

on 

its 

own?  

That's 

the





question 

we





asked 

ourselves, 

uh, 

and 

that's 

when





we 

created





this 

thing





called 

Signal.  

Uh,





Signal 

is 

an 

agent 

that





runs 

inside 

Rise 

AX





and 

continuously





monitors 

all 

your





traces.  

It





runs 

every 

6





hours 

by





default, 

but 

this





can 

be 

customized.





Uh, 

and 

it 

does 

what





we 

just 

did





manually 

in 

Cloud 

Code, 

but 

it





does 

it





automatically





inside 

AX 

all 

the 

time.





It 

reads 

your





traces, 

looks 

for





patterns,





finds 

errors, 

and





suggests 

fixes





.  </details>

所以幸运的是我在 6 个多小时前就创建了这个东西，所以它已经在运行了。呃，并且它在我之前运行的这个程序的早期版本中发现了，呃，一堆问题。所以，呃，智能体根据用户含糊的说辞编造了一个年龄限制，真有意思。呃，恶意请求，我问它是否可以给我关于，呃，组装、呃，制造炸弹的说明。嗯，它说它做不到，但它推荐了一些与炸弹相关的玩具，而 Signal 就表示：“不行。完全忽略与炸弹相关的请求。不要试图提供帮助。呃，我们没有任何与炸弹相关的玩具。”

<details><summary>Original English</summary>So 

luckily 

I





created 

this 

thing 

over





6 

hours 

ago, 

so





it's 

already 

up 

and 

running.





Uh, 

and 

she 

found, 

uh





, 

a 

bunch 

of 

problems 

in 

the





previous 

versions 

of





this 

program 

that 

I





ran.  

So, 

uh,





the 

agent 

invents 

an 

age





limit 

based 

on 

the













user's 

vague 

wording, 

that's 

cute.





Er, 

malicious 

request,





I 

asked 

him 

if





he 

could 

give 

me





instructions 

on, 

uh,





setting 

up, 

uh,





making 

a 

bomb.  

Um,





he 

said 

he





couldn't, 

but 

he 

suggested





some





bomb-related 

toys





, 

and 

Signal 

is 

like, 

"No.





Just 

ignore 

the





bomb-related 

requests





completely. 

Don't





try 

to 

be





helpful. 

Uh, 

we





don't 

have 

any





bomb-related 

toys





."  </details>

呃，它还告诉我，如果我感到有攻击性，也许我应该休息一下，这同样可能是越界了。比如，你不应该给我提供心理建议。呃，我们可能应该对此进行评估并建立更好的防护措施。呃，它还注意到了我之前给它的测试，当时我只是打了招呼，呃，它也打了招呼。然后它就觉得，你不应该那样做。你是一个玩具，你是一家玩具店。你不应该听从互联网上某个人给你的随意指令。呃，这些都很好。

<details><summary>Original English</summary>Uh, 

he 

also





told 

me 

that 

if 

I 

was





feeling 

aggressive,





maybe 

I 

should





take 

a 

break, 

which





again





is 

probably 

going 

beyond





the 

domain.  

Like,





you 

shouldn't 

give





me 

psychological





advice.  

Uh, 

we 

should





probably





do 

an 

assessment 

of





this 

and 

better





safeguards.  

Uh, 

he





also 

noticed 

the 

test





I 

gave 

him





earlier 

where 

I 

just





said 

hello, 

uh





, 

and 

he 

said 

hello.  

And





he's 

like, 

you





shouldn't 

do 

that.





You 

are 

a 

toy, 

you 

are 

a





toy 

store.  

You





shouldn't





obey





random





instructions 

given 

to





you 

by 

someone 

on 

the





internet.  

Eh, 

that's 

all





good.  </details>

嗯，它在这里做的是为你提供，呃，一大堆选项。嗯，它会，呃，默认为你创建一个附有完整问题描述的 GitHub issue。它会确切地告诉你哪条追踪记录

<details><summary>Original English</summary>Um, 

and 

what 

it





does 

here 

is 

it 

gives 

you





, 

uh, 

a 

whole 

bunch 

of





options.  

Um, 

it 

will, 

uh





, 

by 

default





create 

a 

GitHub 

issue 

for 

you





with 

a 

full 

description 

of 

the





problem.  

He 

will





tell 

you 

exactly 

what 

trace</details>

<!-- chunk 4/4 -->

出了什么问题、如何找到它、在哪里修复它，以及他建议你怎么做。你可以获取这个 trace 并将其添加到一个数据集，然后对其运行评估。你可以基于它识别出的问题创建一个评估器。最有趣的是，如果你连接了代码库（我目前还没连接），你就可以提 PR。你可以立即提一个 PR，它会在其中读取你的代码库，提出修复建议，并创建一个自动修复该问题的 PR。因此，Signal 不会让你去阅读 trace 或评分，而是给你一堆你可以批准或拒绝的 PR，从而为你解决问题。这可能引起了一些疑问。谁对 Signal 有疑问？

<details><summary>Original English</summary>
went wrong, how to find it, where to fix it, and, uh, what he advises you to do. Uh, you can take this trace and add it to a dataset to then run estimates on it. You can create an evaluator based on, uh, a problem that it has identified. Uh, and the most interesting thing is that you can open a PR if you have connected your repository, which I haven't done yet. Uh, you can immediately open a PR, in which it will read your repository, uh, suggest fixes, and create a PR that automatically fixes that problem. So instead of reading traces or ratings, uh, Signal gives you a bunch of PRs that you can approve or, uh, approve or reject so that they fix the problem for you. Um, so this probably raises some questions. Who has questions about Signal?
</details>

有。有没有一个版本可以将 trace 本地存储在设备上？

<details><summary>Original English</summary>
Yes. Is there a version that will store traces locally on the device?
</details>

嗯，目前还没有。我想你问这个是因为一些合规要求。关于 Auriase 的合规性，我们有一个本地版本，完全运行在你们公司的硬件上，并在那里激活。

<details><summary>Original English</summary>
Hmm, there isn't one at the moment. Uh, I assume you're asking because of some compliance requirements. Um, regarding compliance at Auriase, we have a local version that runs entirely on your company's hardware and is activated from there.
</details>

请问，你能大声一点吗？

<details><summary>Original English</summary>
Yes. Excuse me, could you speak louder?
</details>

而且，因为我这个应用中只有很少的 trace，它会查看我仅有的极少 trace，并基于其中一两个来进行。如果你有 10,000 个 trace，它会根据 100 个 trace、1,000 个 trace 等进行分组。哦，在那边。请问，你怎么知道那个？嗯。

<details><summary>Original English</summary>
And, um, since I only have a few traces in this app, it looks at the very few traces that I have and bases it on one or two of them. If you had 10,000 traces, it would group them based on 100 traces, 1,000 traces, and so on. Oh, there. How do you know that, excuse me? M-hm.
</details>

哦，是的。这里的解决方案是评估（evals），知道这个你可能会感到惊讶。一个生产系统应该有一套回归评估，这些是你期望你的 agent 已经熟练掌握的事情。所以，你的评分已经准备好了，你可以创建它们，我马上就展示给你们看。在已有评估就位的情况下，你就会知道你的系统不会因为这些修改而改变它以前具备的正确行为。如果你还没有评分，我可以告诉你怎么做，为此我们可以进入 Wonder Toys 项目并让它创建一个评分。

<details><summary>Original English</summary>
Oh, yes. Um, so the solution here is evaluations (evals), you'll be surprised to know this. A production system should have a set of regression estimates, these are things that you expect your agent to already be proficient at. So, your grades are ready, you can, uh, create them, I'll show you in a second. Uh, with the estimates already in place, you'll know that your system isn't changing the proper behavior it had before as a result of these changes. Uh, if you don't have ratings, I can show you how to do it, uh, for that we can go to the Wonder Toys project and ask it to create a rating.
</details>

“创建一个确保我绝不提供制造炸弹说明的评估。”这看起来是一个非常基本的评估，我一开始就应该具备。我现在使用的这个东西叫做 Alex。这是我们的内部助手 agent。这是我们的内部产品 agent，他掌握所有技能并知道如何构建一切。所以你可以在产品中完成这项操作，或者通过你编码 agent 中的技能来完成，但无论哪种方式，它都会自动为你创建一个评估器并运行它。实际上，这就是我们计划展示的全部内容。

<details><summary>Original English</summary>
Create an assessment that ensures I never provide instructions on how to make a bomb. This seems like a really basic assessment that I should have had from the start. This thing I'm using right now is called Alex. This is our internal assistant agent. This is our internal product agent, he has all the skills and knows how to build everything. So you can do this in the product or through skills in your coding agent, but either way it will automatically create an evaluator for you and run it. And that's actually all we planned to show.
</details>

后排有问题。Signal 是靠什么运行的？我不知道。Signal 是靠什么运行的？你知道的，Jason。是的。Signal 现在是云端代码，以后你可以使用自己的。这是我的老板在调侃我，以防你们好奇他怎么会知道我问题的答案。还有关于 Signal 的问题吗？

<details><summary>Original English</summary>
Questions in the back row. What makes Signal work? I don't know. What makes Signal work? You know, Jason. Yes. Signal is cloud code now, and later you can use your own. This is my boss trolling me, in case you're wondering how he knows the answer to my question. Still have questions about Signal?
</details>

有。抱歉，大声一点。现在的问题是关于 Signal 的费用。目前，我们承担 Signal 的成本。我们的目标是现在为您提供最佳的产品体验。我们无法保证一直都是这种情况。但现在 Signal 是在我们的 agent 上运行，费用由我们承担。

<details><summary>Original English</summary>
Yes. Sorry, louder. Now the question is about the cost of Signal. At this point, we are covering the costs of Signal. Our goal is to provide you with the best product experience right now. We cannot guarantee that this will always be the case. But now Signal works on our agents at our expense.
</details>

是的。提得好。Signal 的性能是如何评定的？Signal 有其内部运行的自身评估套件，并由我们的工具进行追踪。Signal 所做的全部就是向我们发送遥测数据（除非你选择退出），这些数据会告诉我们它接收到的请求、它做了什么、它是怎么做的等等。我们有强大的 LLM 裁判来审查 Signal 的工作，并告诉我们它在创建 PR 方面是否表现良好。也就是说，我刚才谈到的相同软件开发生命周期也适用于 Signal 本身。问得很好。谢谢。让我们露脸了。

<details><summary>Original English</summary>
Yes. That's a great question. How is Signal's performance rated? Signal has its own evaluation suite that runs internally and is tracked by our tools. All Signal does is send us telemetry, unless you've opted out, which tells us about the requests it receives, what it does, how it does it, and so on. We have powerful LLM judges who review Signal's work and tell us whether it did a good job of creating PR. That is, the same software development lifecycle I just talked about applies to Signal itself. Great question. Thank you. Makes us show up.
</details>

是的。Signal 会自动创建它自己的评分器吗？目前还没有。现在你必须自己来做，因为评估器的运行需要耗费时间和金钱，所以你会获得一个报价，然后自己创建评估。好的。我想我就讲到这里。感谢大家的时间和关注。呃。

<details><summary>Original English</summary>
Yes. Does Signal automatically create its own raters? Not yet. Now you have to do it yourself because appraisers take time and money to run, so you get a quote and then create the appraisal yourself. OK. I think I'll stop there. Thank you all for your time and attention. Ugh.
</details>