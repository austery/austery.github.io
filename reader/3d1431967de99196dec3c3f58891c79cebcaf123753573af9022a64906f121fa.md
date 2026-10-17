---
author: AI Engineer
date: '2025-12-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rT2Del5pwg4
speaker: AI Engineer
tags:
  - developer-experience
  - ai-agents
  - software-engineering-best-practices
  - code-review-optimization
  - testability
title: AI 代理时代的开发者体验：为何“利于人类”即“利于 AI”？
summary: 来自 Capital One 的 Max Kanat Alexander 深入探讨了 AI 编程代理对软件工程的颠覆。他指出，在预测未来极其困难的当下，企业应聚焦于标准化环境、强化 CLI/API 接口、提升验证精度及代码审查效率等“无悔投资”。其核心哲学是：凡是能提升人类开发效率的基础工程，也正是让 AI 代理释放最大潜力的关键。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Max Kanat Alexander
companies_orgs:
  - Capital One
  - GitHub
products_models: []
media_books: []
status: evergreen
---
### 范式转移：预测失灵时代的开发者投资策略

在过去的 12 个月里，**开发者体验**（Developer Experience: 开发者在工作流中的主观感受与效率总和）经历了前所未有的剧变。软件工程师们几乎每两三周就会被层出不穷的新技术冲击。对于 CTO 或 DevEx 负责人而言，最核心的焦虑在于：现在的技术投资在 2026 年回头看时，是否会沦为无用的浪费？

许多人寄希望于 **AI 编程代理**（AI Coding Agents: 能够自主执行编程任务的 AI 系统），认为它们能自动修复公司的一切问题。然而，AI 代理虽具有变革性，却非万能灵药。要释放 AI 的最大价值，企业必须跳出代理本身，去修复那些限制人类与代理协作的底层障碍。这不仅仅是一个小的工程问题，而是决定软件业务未来成败的关键。我们需要寻找那些无论未来如何变化都具备高价值的“无悔投资”。

<details>
<summary>Original English Source</summary>

I have been doing developer experience for a very long time and I have never in my life seen anything like the last 12 months. The you know about every 2 to 3 weeks software engineers been making this face on the screen. Okay. And if you work in developer experience the problem is even worse. You're like this guy on the screen every few weeks. You're like, "Oh yeah, yeah, yeah, yeah, yeah. Here's the new hotness." And then somebody else comes up and they're like, "Well, can I use the the new new hotness?"

And what this leads to overall is the future is super hard to predict right now. So, a lot of people, a lot of CTO's, a lot of people who work in developer experience to people who care about helping developers are asking themselves this question, are all of my investments going to go to waste? Like, what could I invest in now that if I look back at the end of 2026, I'll be like, I sure am glad that I invested in that for my developers. And I think a lot of people have just decided, well, I don't know. I guess it's just coding agents and I guess they'll fix every single thing about my entire company by themselves which look they're amazing they're transformative but it's not the only thing that you need to invest in as a software engineering organization.

</details>

### 环境标准化：停止与“预训练集”对抗

AI 代理效能的一个关键输入是**开发环境**（Development Environment）。企业应该坚持使用**行业标准工具**（Industry Standard Tools），并以行业通用的方式使用它们。原因很简单：这些工具正是模型训练集的核心内容。

如果你在公司内部发明了奇特的包管理器，或者对现有工具进行了“反人类”的魔改，你实际上是在逼迫 AI 代理与它的**预训练集**（Training Set: AI 模型学习的基础数据）对抗。这种对抗往往会导致不可预知的错误。同样的逻辑也适用于编程语言：虽然作为爱好者可以探索各种小众语言，但在进行**代理化软件开发**（Agentic Software Development）时，应优先选择主流语言，因为它们在模型中的知识储备最深厚。不要试图通过复杂的指令文件去纠正模型根深蒂固的训练惯性，回归主流才是最高效的路径。

<details>
<summary>Original English Source</summary>

One of the biggest ones is the development environment. What are the tools that you use to build your code? What package manager do you use? What llinters do you run? Those sorts of things. You want to use the industry standard tools in the same way the industry uses them and ideally in the same way the outside world uses them because that's what's in the training set. And look, yes, you can write instruction files and you can try your best to try to fight the training set and make it do something unnatural and unholy with some crazy amalgamation that or modification that you've made of those developer tools. Like you might you invented your own package manager. You probably should not do that. you probably should undo that and try to go back to the way the outside world does software development because then you are not fighting the training set.

And also it means it means things like you can't use obscure programming languages anymore. Look, I'm a programming language nerd. I love those things. I do not use them anymore in my day-to-day agentic software development work.

</details>

### 确定性接口与精准验证：AI 代理的感官系统

为了让代理能够采取行动，必须为它们提供 **CLI**（Command Line Interface: 命令行界面）或 **API**（Application Programming Interface: 应用程序接口）。虽然现在有所谓的“计算机使用”（Computer Use）功能让 AI 模拟鼠标操作浏览器，但在追求极致准确性的工程领域，文本交互的原生接口才是最可靠的。

更重要的是**验证机制**。任何客观、确定性的验证工具都能直接增强代理的能力。高质量的验证必须产生极度清晰的错误信息。人类也许能猜出“500 Internal Error”背后的含义，但 AI 代理无法“通灵”。它们需要明确知道哪里出了错以及如何修正。许多企业在面对遗留代码库时，由于代码缺乏**可测试性**（Testability），AI 代理写出的测试往往会变成毫无意义的“按钮按下了，测试通过”式的无效逻辑。因此，投资于底层验证架构，是提升代理循环效率的基础。

<details>
<summary>Original English Source</summary>

In order to take action today, agents need either a CLI or an API to take that action. Yes, there's computer use. You can make them write playright and orchestrate a browser. But why? Like if you could have a CLI that the agent can just execute natively in its normal format that it understands the most natively, which is text interaction, why why would you choose to do something else, especially in an area where accuracy matters dramatically and where that accuracy dramatically influences the effectiveness of the agent?

One of the most important things that you can invest in is validation. So any kind of objective deterministic validation that you give an agent will increase its capabilities. You just need to think about how do I have high quality validation that produces very clear error messages. This is the same thing you always wanted by the way in your tests and your llinters, right? But it's even more important for the agents because the agents cannot divine what you mean by 500 internal error with no other message, right? Like they need a way to actually understand what the problem was and what they should do about it.

</details>

### 结构化代码与意图文档：补全 AI 的逻辑版图

**代码库结构**（Codebase Structure）的优化对 AI 的推理能力至关重要。在许多大型企业中，存在着人类都无法理解的遗留代码，因为推理所需的信息根本不在代码本身。如果代码结构混乱，AI 代理只能像人类一样不断尝试并报错，这会极大地降低其效能。代码必须做到“可被推理”，这意味着逻辑流向应该是清晰且符合直觉的。

此外，**文档**的价值在 AI 时代被重新定义。AI 虽然能读懂代码，但它无法读懂你的心。它没参加过你那场没有记录的口头会议，因此无法理解系统背后的原始需求和权衡。虽然有些代码解析类文档可以交给 AI 自动生成，但那些**代码之外的信息**——例如“为什么要写这段代码”、“外部传入数据的真实形状是什么”——必须被书面记录。任何无法从代码中推导出来的意图（Intent），都必须存在于 AI 能够访问到的地方。

<details>
<summary>Original English Source</summary>

Agents work better on better structured code bases. For those who have worked in large enterprise, you know that there are code bases that no human being could reason about in any kind of successful way because the information necessary to reason about that codebase isn't in the codebase and the structure of the codebase makes the codebase impossible to reason about looking at it. Yes, the agents can do the same thing human beings do in that case, which is sort of go through an iterative process of trying to run the thing and see what breaks, but that decreases the capability of the agent so much compared to just it having the ability to just look at the code and reason about it.

The agent cannot read your mind. It did not attend your verbal meeting that had no transcript. Now there are many companies in the world that depend on that sort of tribal knowledge to understand what the requirements are for the system. Why the code is being written? Basically anything that can't be in the code or isn't in the code needs to somehow be written somewhere that the agent can access.

</details>

### 代码审查革命：从“打字员”向“评审员”转型

在软件工程中，阅读代码的时间向来多于编写代码。但在 AI 代理普及的今天，“编写代码”本身已经变成了“阅读代码”。每位软件工程师都在转变为**代码评审员**（Code Reviewer）。随着 AI 生成 PR（Pull Request）的速度大幅提升，代码审查已成为整个流水线的瓶颈。

提高**审查速度**（Review Velocity）并非要缩短总时长，而是要加快每一次交互的反馈速度。许多团队习惯在 Slack 频道喊一句“谁能帮我审一下”，结果导致压力集中在极少数响应极快的成员身上。解决之道是建立自动化的分配系统，并设定明确的 **SLO**（Service Level Objective: 服务水平目标）。更危险的倾向是“橡皮图章”式的盲目通过——如果代码审查的质量门槛降低，随着 AI 生成的代码不断堆积，系统会变得越来越难以维护，最终导致生产力的持续下滑。我们需要通过**学徒制**（Apprenticeship）让资深工程师将评审技巧传授给新人，因为这是目前培养优秀评审员的唯一路径。

<details>
<summary>Original English Source</summary>

The difference today is that writing code has become reading code. So even now when we are writing code we spend more time reading it than actually typing things into the terminal. And what that means is every software engineer becomes a code reviewer as basically their primary job. In addition, we generate far more PRs than ever before, which has led to code review itself, the like the big scale code review being a bottleneck.

So one of the things that we need to do is we need to figure out how to improve code review velocity. What you care about the most is making each individual response fast. You don't actually want to shorten the whole timeline of code review generally because code review is a quality process. If you don't have a process that is capable of rejecting things that shouldn't go in, you will very likely actually see decreasing productivity gains from your agentic coders over time as the system becomes harder and harder for both the agent and the human to work with.

</details>

### 总结：迈向加速发展的“正向循环”

如果你不投资于标准化的环境、不优化过慢的 CI（持续集成）流程（如果代理跑一次测试要 20 分钟，开发效率就会崩溃）、不提升代码的可测性，那么你将陷入一个**恶性循环**：AI 产生平庸的代码，疲惫的评审员给出“橡皮图章”式的通过，代码库质量持续恶化，AI 的效率也随之下降。

相反，如果我们现在就进行这些基础投资，我们将进入一个**正向循环**（Virtuous Cycle）：代理能力被放大，人类生产力被解放，业务竞争力由此产生差异化。所有的这些投资都有一个共同的底色：**凡是利于人类的，均利于 AI。** 即便我们在 AI 代理的某些预测上失手了，这些针对基础工程能力的投资也绝对能让开发人员获益。

<details>
<summary>Original English Source</summary>

If you have low quality code reviews or code reviewers who are overwhelmed, you just have lots and lots and lots of bad rubber stamp PRs that keep going in and you get into a vicious cycle where what I expect to occur is your agent productivity will decrease consistently through the year. On the other hand, we live in an amazing time where if we increase the ability of the agents to help us be productive, then they can actually help us be more productive and we actually get into a virtuous cycle instead where we actually accelerate more and more.

So to summarize, standardize your development environments. Make CLIs or APIs for anything. Improve validation. Refactor for testability and reasoning. Make sure the 'why' is written down. Speed up code review responses and raise the bar on quality. What's good for humans is good for AI.

</details>