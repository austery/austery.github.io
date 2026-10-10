---
author: AI Engineer
date: '2026-04-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=MhHEGMFCEB0
speaker: AI Engineer
tags:
  - openai-codex
  - software-engineering-agent
  - sub-agents
  - mcp-server
  - ai-automation
title: OpenAI Codex 深度解析：从软件工程智能体到亚代理架构
summary: 本篇内容源自 OpenAI 开发体验团队的深度大师课。详细介绍了软件工程智能体 Codex 的演进历程，重点解析了其底层的 GPT-5.4 模型系列、统一智能体框架（Unified Agent Harness）、插件系统以及能够并行处理复杂任务的亚代理（Sub-agents）架构。此外，还通过实战演示展示了 Codex 在自动化工作流、视觉化游戏开发及大规模代码审查中的卓越能力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models:
  - Codex
  - GPT-5.4
  - GPT-5.4 Mini
  - GPT-5.4 Nano
media_books: []
status: evergreen
---
### 软件工程智能体：Codex 的定义与底层模型演进

**Codex** 并非单纯的“代码助手”，而是一个定位为 **软件工程智能体**（Software Engineering Agent: 能够理解工程语境并执行端到端研发任务的 AI 系统）的综合平台。它不仅能编写代码，更能运行指令、执行测试、探索复杂的代码库，具备软件工程师在日常工作中所承担的各种能力。

在底层架构上，Codex 建立在 OpenAI 最前沿的模型基础之上。目前的旗舰级模型是 **GPT-5.4**，同时也提供了专为超高速响应设计的 **Spark** 版本。针对不同的任务场景，Codex 还会调用 **GPT-5.4 Mini** 和 **Nano** 模型，用于处理短时任务或作为 **亚代理**（Sub-agents: 在主智能体控制下执行特定子任务的独立智能体线程）运行。

为了确保这些模型在工程环境中的稳定性与安全性，OpenAI 构建了一个名为 **统一智能体框架**（Unified Agent Harness: 管理智能体行为、工具执行、环境设置及安全防御的封装层）。这一层作为模型之上的包装器，负责评估智能体行为，管理环境初始化，并嵌入了关键的安全防御机制，确保智能体在执行特权指令时始终处于受控状态。

<details>
<summary>Original English Source</summary>

Hi everyone. Thank you for being here. So today we're going to talk about Codex. My name is Katya Gilusman and I'm with VB. We are both working in the developer experience team at OpenAI based in London. And so our role is really to help developers build and get the most out out of our products including Codex.

To start, just for those who don't know Codex or even if you know it, maybe you don't know it that well, Codex is our software engineering agent. So it's not just a coding agent. It's not just an agent that writes code. It can do much more than that. It can run commands. It can run tests. It can explore code bases. It can really do everything that a software engineer would do. And so it's based on our models as a foundation. For example, GPT 5.3 Codex was our previous ones. We also have the Spark version which is like the super fast model that we have. The state-of-the-art model right now is GPD 5.4. And we also have a mini version that came out last week.

And you know, every time we make improvements, every time we have better models, Codex benefits from it. But it's not just the models. On top of that foundation, we have what we call a unified agent harness that will manage evaluates the agents' behavior and that is a wrapper for tool execution for environment setup for everything that can let the agent do its work and run smoothly. There's also safety, the safety embedded in that harness. So all of that is Codex.

We also released GPD 5.4 mini and GPD 5.4 Nano which you can use for short-running tasks and sub-agents which we'll talk about in a bit. One thing that as we pushed on making these models better, we also worked quite a bit on making sure that these models can be served to you as fast as possible. What that means in principle is we introduced something called websockets which allow us to create a connection between your device as well as where the API resides to be able to give you roughly about 1.75x faster tokens without really paying the cost over to you. At the same time we also released a fast mode which allows you to on top of the 1.75x get 2x more faster tokens.
</details>

### 生态与交互：多端覆盖与插件化工作流

用户可以通过多种界面（Surfaces）与 Codex 交互，包括独立的 **Codex App**、IDE 扩展插件、命令行工具（CLI），甚至是 Slack 和 GitHub。在 OpenAI 内部，工程师们习惯于在 Slack 中直接 @Codex 来修复 Bug 或在 GitHub PR 中寻求建议。

为了让 Codex 完美融入现有的开发堆栈，它支持与 **Figma**、**Linear**、**Notion** 等主流工具集成。这种集成能力主要通过 **插件**（Plugins）实现。一个插件本质上是 **技能**（Skills: 针对特定流程打包的、可重用的指令集与脚本）、应用连接和 **模型控制协议服务器**（MCP Servers: 暴露外部系统工具以扩展智能体能力的标准化协议）的集合。通过插件，开发者无需手动安装多个技能或配置复杂的连接，即可实现如“同步 Google Drive 电子表格与代码库数据”或“使用 Playwright 进行视觉调试”等高级功能。

<details>
<summary>Original English Source</summary>

And then you can interact with it through different surfaces. So you have the Codex app that we're going to talk about in a few minutes. You can also interact with it through your IDEs with the extension. You can interact with it through the CLI and also through other services like Slack for example. At OpenAI we all the time just like ping Codex in Slack and ask it to fix things or in GitHub as well. And on top of all of that, you can also integrate it with your preferred tools so that it can really work with everything that you're already using. So, you know, you can integrated with Figma, with linear, with notion, all of that combined can let Codex do everything that a software engineer colleague would do.

Plugins bundle a bunch of things together, like skills, apps, integrations, MCP servers, and they bundle that into reusable workflows. Skills are essentially reusable instructions packaged for specific processes. If you have something that you're doing quite a bit, you can actually create a skill for it so that Codex knows about it. You can give it instructions, you can give it scripts as well, resources and all of that. Apps are connections to other services. The tools that you use every day like Notion, Linear, all of that, you can let Codex connect to it. And MCP servers basically expose tools for Codex to just extend its capabilities further and it's tools from external systems.
</details>

### 深度自动化：从日常工作流到视觉化游戏开发

Codex 的 **自动化**（Automations）功能是其核心亮点之一。它允许用户设置类似 **定时任务**（Cron Jobs: 在特定时间或触发条件下自动执行的任务）的后台进程。例如，你可以设定每天早上 9 点让 Codex 自动梳理 Slack 消息，识别具有时效性或需要紧急回复的任务，并按话题进行归类。

在更高级的开发场景中，Codex 能够通过 **视觉化反馈循环** 构建应用和游戏。利用 **Playwright Interactive**（Playwright Interactive: 允许智能体在无头浏览器中进行点击、截图及视觉分析的技术）技能，Codex 可以在沙盒浏览器中运行并调试正在开发的应用。配合 **图像生成**（Image Gen）技能，它可以自主生成游戏所需的 **精灵图**（Sprites: 游戏开发中用于角色的 2D 图像资源）。在现场演示中，Codex 仅凭简单的提示词就构建了一个完整的平台跳跃游戏，包括自主生成的关卡资产和经过视觉调试的物理交互。

<details>
<summary>Original English Source</summary>

Automations is one of my favorite things to do with Codex. You can set up automations that run in the background, like a cron job. For example, you can set an automation to run every day at a certain time. I connected Codex to Slack and I'm asking, "Hey, Codex, can you check every day at 9:00 a.m. the messages that I should reply to and flag if it's time sensitive or waiting for an urgent response? Can you also do a summary of all the things that have happened since yesterday on Slack, bucketed per topic?" Another one is connecting Gmail to check if there are emails that I should actually reply to. This is saving me hours per day.

There's two skills that I want to highlight that are super useful and honestly that are a game changer when you're developing something visual. It's Playwright Interactive and Image Gen. Playwright is essentially like a headless browser, a sandbox browser that Codex can just run and use that to see what it's doing. With the interactive version you can actually click things and navigate your app and take screenshots and analyze those screenshots. Image Gen is a great way to just generate visual assets for your apps and games. I was just like "do a platformer game with platforms made of bricks." That's it. And yeah, it generated everything... literally all the sprites, and I didn't have to do any of that.
</details>

### 工程质控：大规模代码审查与内部实践

OpenAI 极其重视交付代码的质量，而 Codex 的 **代码审查**（Code Review）能力被公认为行业标杆。通过与 GitHub 集成，开发者可以设置让 Codex 自动审查每一个拉取请求（Pull Request）。它不仅仅是扫描代码差异（Diff），更会结合整个代码库的上下文进行深度分析。

这种深度审查能够识别出具有 **二阶效应**（Second-order Effects: 修改一处代码导致其他看似无关模块产生连锁反应的后果）的变更。目前，OpenAI 内部 100% 的代码库，包括 Greg Brockman 等核心成员提交的 PR，默认都会经过 Codex 代码审查的首轮过滤。它会将问题标注为 P0、P1、P2 等不同优先级，显著降低了人工审查的负担。

<details>
<summary>Original English Source</summary>

One thing that you want to be sure of is whatever it is that your agent produces is of the utmost quality. Codex code review is one of the best in the industry right now. You are able to use Codex code review on GitHub. For each and every pull request that you create, you can set it up such that Codex can automatically review each and every pull request. It would contextualize it with everything that is there on the repo itself. A lot of the times Codex code review will find out changes which would have second-order effects which is not limited to just the diff but also to some other modules which you haven't even touched in the pull request itself. This is so effective that 100% of pull requests across all OpenAI repos made by all employees, including Greg, are reviewed by Codex code review by default.
</details>

### 并行智能：亚代理（Sub-agents）架构与分布式任务处理

为了处理极其复杂的工程任务，Codex 引入了 **亚代理**（Sub-agents）机制。这是一种将主任务拆解为可分解、可并行且相互独立的子任务，并分发给多个专业智能体的策略。用户可以针对特定任务定义 **自定义亚代理角色**（Custom Personas: 为亚代理预设的模型偏好、沙盒模式及指令集配置文件）。

例如，在审计一个拥有 50 多个角色的复杂代码库时，主 Codex 智能体会自动切换到 **计划模式**（Plan Mode），将任务切片并派生出 20 个专注于不同维度的“评审智能体”。这些亚代理会在独立的沙盒环境中运行，并在任务完成后自动撤销，最后由主智能体汇整所有反馈。通过 **模型控制协议**（MCP）的权限分配，你可以给不同的亚代理授权：例如给文档智能体授权访问 Notion，给安全智能体授权访问 Sentry。这种分布式架构极大地提升了 Codex 处理大规模工程项目的效率。

<details>
<summary>Original English Source</summary>

Sub-agents is essentially the ability wherein you can spin off a master task into decomposable, parallel and independent tasks which you can hand off to agents which can allow these agents to sort of work independently and then at the end of their run get back to you and give you a response. You can define your own custom sub-agents. For each of these you can define what model you want to use, what reasoning effort, what sandbox mode (read-only or write-access). For a review agent or security assignment, you would almost always 100% want to use it in read-only mode.

In this case, it essentially created review slices... they would spin up a new Codex environment. They would review those and then at the end Codex will collate all of these and give me back a response. Codex automatically decided that this is potentially a complex task, so it automatically kickstarted the plan mode. It's partitioning all of these persona files and then it's going to spawn 20 sub-agents. You can give these sub-agents more capabilities by giving them MCP access. You can give a sub-agent MCP access to Sentry or one to your Linear backlog so that it can read through all the issues and triage them.
</details>

### 核心安全与前沿探索：Guardian、钩子函数与云端执行

在迈向更高自主性的过程中，安全与管控至关重要。Codex 推出了 **Guardian 审批机制**（Guardian Approvals: 一种通过派生专门的安全子智能体来评估并自动批准或拦截特权操作的防御机制）。当 Codex 需要执行删除目录、运行服务器或暴露敏感文件等特权任务时，Guardian 子智能体会根据预设的安全提示词判断是否需要人工干预。这显著减少了因频繁的人工确认而导致的“审批疲劳”。

此外，Codex 还支持 **钩子函数**（Hooks: 在会话启动、工具使用前后或会话结束时触发自定义逻辑的机制），允许开发者通过 Python 脚本实现“自动拉取最新代码”或“任务未完成时持续重试”等高级逻辑。对于长时运行的大规模任务，用户可以通过 **云端执行**（Cloud Execution）将负载卸载到 OpenAI 的高性能云端沙盒，并利用 **Best of N** 采样技术在多个并行运行的结果中选择最佳方案。

<details>
<summary>Original English Source</summary>

Guardian approvals is an experimental feature. All of us were guilty of using "yolo mode," giving unfettered access to your coding agent. Hence we came up with guardian approval. Whenever Codex needs to run a privileged task—remove a directory, run a server, expose a file—Codex will spin up a new sub-agent which will verify whether or not this needs human interruption. This way we hope to reduce the human fatigue.

Hooks allow you to programmatically ask Codex to do a thing based on a particular event (after tool use, start of session, stop session). For long-running tasks, I created a hook for "stop" which runs a Python script "keep going UI"—it asks Codex to do one more pass, run one more validating command, and then stop.

Is there a way to hand off a task to a cloud agent? Yes, definitely. You can select "cloud" directly from the Codex app. You can parallelize—we call that "best of N"—so you can run it four times in the cloud and then just pick the best output. We do want to give you the ability to have your own trusted MCP servers run there or the ability to just have SSH agents that you can spawn off a particular task on a VM.
</details>