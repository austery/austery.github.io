---
author: AI Engineer
date: '2026-07-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=z0sh8HyTrDo
speaker: AI Engineer
tags:
  - agentic-workflow
  - developer-productivity
  - autonomous-agents
  - human-in-the-loop
title: 重构开发流程：打破人机协作的吞吐量瓶颈
summary: Auditoria AI 的数据科学家 Ramana Siddanth Emani 指出，生产级 AI Agent 在实际落地中的最大瓶颈是开发者的研发循环速度。通过引入并行工作树的子智能体、组织专属的技能秘方、微型化交互界面以及自主闭环目标，开发者可以将自身从繁琐的任务编排中释放出来，仅作为验证者而非生产力的天花板。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Auditoria AI
products_models: []
media_books: []
status: evergreen
---
### 生产力悖论：为什么精美的 Demo 落地即失效

在如今的 AI 时代，编写代码和展示精美的 Demo 变得极其简单。然而，当这些 Demo 被推向试点阶段并开始接入真实客户的未来数据时，生产环境中的 Bug 就会呈指数级增加。很多团队试图通过更换更好的模型、使用更快的 GPU 或频繁更换应用框架来解决这一问题。但事实上，市面上的模型和芯片都在以极快的速度更新迭代，硬件与框架的置换无法从根本上解决即时修复生产 Bug 的效率问题。

真正决定生产效率的是**开发循环速度**（Developer Loop Velocity）。尽管模型能力呈指数级增长，开发者每天却仍需花费大量时间来手动运行和编排开发循环。因此，如何通过自动化开发套件将开发者效率提升 10 倍，成为解决生产环境问题的关键。

<details>
<summary>Original English</summary>
Hello everyone. Welcome to this session about your finance agent's bottleneck is you. So, sorry for the rude title. I don't mean to call the audience here the bottlenecks, but I'm here to talk about the harnesses that you guys are developing and using these internal harnesses to build your production agents. So, my name is Siddhant Imani and I'm a data scientist at Auditoria AI and we build production agents for finance. So, if you're a CFO in the audience, I would love to speak to you after the session. This talk is in between the harness engineering track and AI for finance. So, this talk is mostly about identifying the bottlenecks within your developer and if you're a developer yourself, how do you be 10x productive with the agent harnesses that you're using. So, all of us have seen, you know, beautiful demos in this AI engineer's world fair. But, once these demos are promoted to pilots and you start onboarding new customers, the agent has never seen these future data. So, all of us know production bugs are very high and production guards built by the hour. So, that's a hard fact. And writing code is very easy. So, shipping beautiful demos and showing it to a lot of people is very easy right nowadays. So, what is the problem? And why do you these demos fail in production? Is it the model? Do you need a better model? Fable 5, perhaps? Or do you need faster GPUs? Or do you need a better framework? Maybe. Or your RALF loops are not working properly. So, what is the answer? If you wait 3 and 1/2 months, we are awarded with a new model in the market. So, we can easily swap models. If you wait perhaps 1 year, we have new chips. We have faster GPUs. And again, writing code is easy. So, we have new frameworks every day. So, you can swap your framework every now and then. So, how do we in real time fix these production bugs? The answer is your dev loop velocity. The model capability increases very exponentially. And the developers have to spend a lot of time every day to automate your developer loop.
</details>

### 构建高效自治的四大开发基石

为了大幅度提升生产代码的迭代效率，开发套件需要引入四个核心的构建基石：

* **并行子智能体**（Sub-agents）与 **Git 工作树**（Git Worktrees: 相互隔离的物理文件夹）。借助 MacBook 充足的内存，开发者可以并行启动数十个子智能体，在相互独立的物理路径中编写并调试代码，避免在同一个分支或文件上发生冲突。
* **技能系统**（Skills）。这代表了企业或团队内部的**“秘方”**（Secret Recipes）。一旦将这些封装了正确研发流程的技能赋予 Agent，它们就能严格遵循标准化流程来定位和修复特定的生产 Bug。
* **模型上下文协议工具**（Model Context Protocol Tools: 连接外部系统的开放接口）。这使得 Agent 能够顺畅地连接到任何第三方服务器或企业内部数据系统。
* **极简用户体验**（Minimal UX）。由于多任务并行需要繁琐的协调工作，将所有服务的监控、系统日志、Jira 工单和 GitHub 提交信息浓缩在单一的**“玻璃面板”**（One Pane of Glass）中，能极大地减少开发者频繁切换窗口和屏幕的认知负担。

<details>
<summary>Original English</summary>
So, I'm talking about four primitives here. All of you need to think about loops. And at the end of the session, I hope you can 10x your production code. So, first we have sub agents. Nowadays, whatever harness you're using, you can spawn new sub agents. You can have an army of them. And get work trees are your best friend. So, think of work trees as isolated folders. And inside these folders, the agent writes whatever code it's generating. So, you want these work trees to be in parallel. So, the sub agents are doing independent tasks and are not fighting over the same thing. Second, we have skills. These are your organization secret recipes. So, make sure you have a lot of skills because these skills, once you start say giving it to your agents, the agents will always make sure to use the correct and proper workflows to solve whatever production bug you're facing. And of course, all of us have seen a lot of MCP tools being shipped into the market right now. Everybody says we can, yeah, the agent can connect to whatever MCP tool and whatever third-party server there is. And your client data can live in any system you want. And at the end of the day, if you have a lot of sub-agents, you have a lot of work to orchestrate. So, minimal UX is the key here. Let's look at the sub-agents. With you as the orchestrator, you can have, let's say, with 48 GB of RAM on your MacBook, you can have 50 active work trees. That is 50 active sub-agents working independently on different tasks.
</details>

### 从工单到部署：AI 闭环研发的实操链路

在传统的软件生命周期中，当质量保证团队报告 Bug 时，开发者需要经历从需求分析、根本原因分析、提取日志、编写测试、本地测试再到提交拉取请求（PR）的繁琐过程。在合并代码后，还需要构建 Docker 镜像、部署到开发环境测试、再发布至预发环境验证，最后才通知测试团队。

在这个包含九个步骤的完整研发链路中，**人类仅在起点（解析需求并分配任务）和终点（验证已部署至预发环境的产品）是必须参与的**。中间所有枯燥的排查、编码、测试和部署步骤，均可由 Agent 在本地的工作树中以更高质量、更快的速度自动执行。开发者无需再为了监控智能体的行为而频繁转动脖子看多个显示器，仅通过一个精简的 macOS 桌面微件，就能在一个界面内统揽全局。

<details>
<summary>Original English</summary>
So, where do these tasks come from? So, let's say the production software you're going to ship has a lot of bugs that your QA is reporting. So, all the Jira tickets can be thought of in a separate different work tree. So, different work trees are handled by a separate agent, and these agents can spawn multiple sub-agents to solve that particular task. You don't want to queue up your tasks because the agent is will do that a lot better than you. Let's look at, you know, um, an example harness. What if the QA reports a lot of bug tickets, and somehow magically there is an agent which parses the requirements, does a root cause analysis, pulls all the traces, pulls all the logs, puts all this in a separate work tree, does the TDD, does the, implements the fix. Because it's in your local system, you have to do test scripts, local end-to-end testing. You create a PR. You submit the PR to your team for review. And after review, you merge it into your master branch, let's say. After merging it, obviously, you have to build a Docker image, deploy it into your development environment, test it, again ship build an image to your stage environment, test it, deploy it to stage. And then you go back to the QA saying, "Here you go. You can test it now." So, I would like to ask a question in the audience, um at what points do you think the human contact is required in this, um steps 1 to 9? So, I would say the human is only required at steps 1 and 9 because the in-between steps, the agent can do a lot better work. There needs to be a human to see what work the agent is doing. And then needs to be a human at the end to validate after the work is being shipped to stage. And obviously, we need minimal UX because humans love minimal UX. So, in the image, if um you can if you squint your eyes and see, the image shows um the production agent software that you're building, the project dashboards which shows all your Kubernetes services, pods, examples, all the logs, system logs, all your Jira tickets, all your GitHub PRs, and maybe a cloud code session at the bottom. So, this is basically a macOS widget, and you don't need to open multiple windows to do all of this work. A developer does like variety of things in their software development life cycle. So, you can use just this one widget to do a lot of things. So, you can see from the graph also, the number of neck rotations to ship one change like reduces a lot drastically. And I imagine all of you have like two to three monitors on your table and you just keep rotating your neck orchestrating these agents.
</details>

### 自我迭代的闭环：将人类从吞吐量天花板中解脱

特别是在规则极其严格、合规性要求极高的金融领域，传统的风险控制通常依赖人类审计员和控制员来签署法案合规证明。如果直接让 Agent 相互审查，往往会面临责任归属的难题。但在日常的 Bug 修复和研发迭代中，随着新一代大模型具备更强大的逻辑推理能力，我们可以实现**递归自我改进**（Recursive Self-improvement）。

开发者可以将每日的生产环境失败案例作为输入，让 Agent 在后台运行并分析研发流程本身的瓶颈，自动生成优化方案并升级其内部研发套件。长此以往，开发者只需要输入一行简单的指令，Agent 即可自动连接数据库、抓取链路追踪、修改代码并提交发布。通过将“目标”与“循环”有机结合，并在后台进行类似人类睡眠时的数据整理与模式沉淀（即“梦境”过程），智能体得以不断自我升级。人类应当坚守**“验证者”**的角色，而不是扮演限制系统吞吐量的天花板。

<details>
<summary>Original English</summary>
So, Auditoria works in finance. So, there's a lot of regulation and policies happening in finance right now. So, what does it look like for orchestrating a team of sub agents in the finance sector? If we take AI out of the picture, usually what happens is you have a human auditor which reviews the code and you have a controller which signs off under your socks compliance. And reviewing agent to agent, it doesn't Where do you keep the accountability? If something goes wrong in production, you can't say Cloud is doing this. Something is wrong. So, but let's say you have all these sub agents and you're using this harnesses to fix bugs in real time. What is the bottleneck? It becomes a human attention because you yourself have to orchestrate all these different tasks. And moving fast and breaking things in sector in the finance sector is a lot different. So, let's look at part two, which is removing yourself from the loop. Till now I've been saying a human is required to see what the agent is doing and at the end also to validate what the agent has done. But with the self-improvement of the agent and model capabilities these days, we get Fable 5 and Mythos 5 and GPT 5.6 also. So, what does it look like when you have this recursive self-improvement in your internal developer developer harnesses? So, all your production failures become input. So, let's say you automate keep automating these cell developer harnesses every day and you ask the agent to upgrade itself essentially. So, you do a task. You let the loop run. Let's say one or two days. You solve five to six bug tickets. And you just tell the agent to analyze all the bottlenecks in this process. Make a list of them. And somehow slowly keep removing these bottlenecks every day. At the end of one month, let's say, you have a really nice self-automated loop where you just type in one sentence and just say fix this bug for me. And the agent goes off, connects to all your database systems, fetches all the logs, traces, tickets, and ships it and migrates it migrates it to the Jira to QA pipeline. And you can just book a vacation maybe or work from home. And what does it look like internally and what happens when you stare less and ship more? Nowadays, how many of you know you can give goals to your agents? You can just set a goal and forget about it. Anybody? Nice. Um so, what if you combine goals and loops? You can just set a goal saying there is some data discrepancy in this report. And in the production bug like the source data is not matching with what the agent has generated. So, you can just set a goal to fix this, look into this, set a loop. You can even close like close your laptop because you can do it from your phone nowadays. And if you look at the last but one point, which is dreaming, um let's say a lot of are using your production software and they are doing the same type of patterns and they're facing the same type of problems. So, you let the agent dream like humans dream in the background so that it collects all the sessions that your customers are using and compacts it into a set of data points which your system can use and basically upgrade yourself. So, with a combination of all these features, basically you can essentially remove yourself out of the loop. But, as I said before, the developers do a lot of variety things in their software development life cycle and sitting behind a desk from 9:00 to 5:00 and just writing code is not valid anymore. So, just an overview of what I've covered till now in the session. You can have a team of sub agents working in parallel work trees. You can have skills, your organizational secret recipes, your customers recipes. You can give all of these to an agent. Your agent can connect to whatever third-party server there is. It can be a logging system, it can be an authentication gateway. And you just compress all of this into one pane of glass because minimal UX is the key. And you can set goals and loops for autonomy. If you think this particular work can be done by the agent a lot better, you can just ship it to the agent. Always have the human as a verifier, but not the throughput ceiling because human attention is very limited. So, thank you for your time and thank you for your Thank you for I hope you learned something from the session. Thank you.
</details>