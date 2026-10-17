---
author: AI Engineer
date: '2026-04-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=cCRO3ChaYhM
speaker: AI Engineer
tags:
  - platform-engineering
  - ai-agent
  - api-first
  - self-service
  - developer-experience
title: 机器视角下的平台工程：为 AI Agent 时代重构基础设施
summary: 本文探讨了在 AI Agent 崛起背景下，传统平台工程如何转型以适应机器用户的需求。作者通过分析开发者在手动流程中的困境，提出了“自助服务、API 优先、本地化优先”的三大核心原则，并强调了结构化文档与可编程观测性在构建闭环自动化中的决定性作用，旨在利用 AI 浪潮推动工程最佳实践的落地。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Juan Herreros Elorza
companies_orgs:
  - Banking Circle
products_models:
  - Kubernetes
media_books: []
status: evergreen
---
### 叙事起点：跨国金融背景下的“Atlas”平台愿景

大家好。我是 Juan，在 Banking Circle 担任云原生技术团队负责人。我们是一家全球跨境支付提供商，每年处理超过 1 万亿欧元的资金，并为 700 多家监管金融机构提供银行服务。作为一家典型的金融科技（Fintech）公司，我们拥有超过 250 人的工程团队，负责构建包括 API、核心银行系统、内部工具、数据工程以及与结算方案集成在内的复杂技术体系。

为了应对底层基础设施和云端的复杂性，我们建立了一个名为 **Atlas** 的**平台工程**（Platform Engineering: 旨在通过工具、服务和流程降低开发者认知负担的工程领域）团队。Atlas 涵盖了基于 Kubernetes 的计算平台、用于配置存储和数据库的基础设施平台、消息传递平台以及**观测性**（Observability: 衡量系统内部状态的编程化能力）平台。虽然我们已经走了很远，但这个过程并非一帆风顺。让我们从一个基于真实经验的虚构故事开始：一位新入职的开发者在构建完支付系统后，试图部署它。他询问同事，同事让他去复制一个旧的 Pipeline；Pipeline 运行失败了，他却看不懂错误信息，因为那与他的代码无关。接着他被推向基础设施团队，对方虽然愿意帮忙，却说：“我要处理的事太多了，下周再说。”这种破碎的体验让开发者极度沮丧，他们不仅要写代码，还要在文档、同事和跨团队沟通的迷宫中艰难前行。

<details>
<summary>Original English Source</summary>

My name is Juan and I work as the team lead for the cloudnative technology team in a company called banking circle. Mainly we are a global crossborder payments provider on top of accounts and liquidity management. We process over €1 trillion euro per year and we provide banking services to over 700 regulated financial institutions. More than 250 people in banking circle are building some type of technical systems and this includes the APIs that our clients are using. Because of that, we have decided to establish a platform that all of these teams can use so that we abstract away the complexity in some of the underlying infrastructure and cloud concerns. We call that platform Atlas.

Now we have come a long way in this platform engineering journey, but it wasn't always easy. Let's say that we have a new developer and they have joined the company. They build their first application but eventually they hit a wall. They have the code but they need to deploy that application somewhere. Then the developer will naturally ask someone in the team, hey, what should I do with this application? And then the person in the team might say, well, you know what? Actually, I did that, but it's already set in this pipeline. Why don't you copy it from there? The developer might go copy the pipeline. Maybe the pipeline will fail. And ultimately the developer doesn't know why it's failing because the error has nothing to do with the application that they coded. Maybe the teammate might say you should talk to this person that is working in the infrastructure team. Now this developer will go maybe they will talk with this person and eventually realize they also needed a database or maybe some blob storage. Back to square one. Maybe the person in the infrastructure team will say, I actually have a lot of other things that I'm working on. I will help you, but that's going to be next week. Obviously the developer will get frustrated because they kind of had done their part but then they struggled a lot in this process to then deploy the application and to get it running with all of the dependencies that it needs.

</details>

### 机器极限：为何 AI Agent 无法在破碎流程中生存

在日常工作中，我们开始广泛使用大语言模型（LLM）和 AI Agent。如果上述破碎的流程对人类开发者来说只是“棘手”，那么对于机器来说则是“完全不可能”。机器无法理解模糊的口头指令，更不可能走到二楼去和基础设施团队的人聊天。虽然 Agent 可以通过工具调用或语音模型拨打电话，但通常意义上的编码 Agent（Coding Agent）无法在缺乏清晰定义、依赖人工协调的环境中发挥作用。

**开发者痛点**（Pain Points: 开发者在工具使用或流程中遇到的阻碍）在 Agent 面前被无限放大。Agent 的生产力瓶颈往往不在于其模型能力，而在于它所处的工程环境。这也揭示了一个核心观点：**最佳实践依然是最佳实践**。过去我们知道依赖同事口述、跨团队等待、盲目尝试 Pipeline 是糟糕的模式，但在 AI Agent 时代，这些缺陷变得更加致命且不容忽视。我们必须构建一套既能服务人类，也能服务机器的平台。

<details>
<summary>Original English Source</summary>

Now this is a bad situation that again I think all of us have been at some point. It's a bad situation for a person, but today all of us are using LLMs, we're using AI agents to help us in our daily job. And if this situation was tricky for a developer, this situation is essentially impossible for a machine because the machine is not going to, you know, go and try the pipeline and then go up to the second floor and talk to the person in that other team. A coding agent is not going to be able to do all of these things. So these pain points that the developers were facing suddenly become much more obvious when an agent is facing them and they are a limiting factor in how productive this coding agent can be or how productive the developer can be when using the coding agent.

The gist of it is that best practices are still best practices. We have known for a while that some of these things like relying on a teammate to tell us how to deploy an application or having to reach out to a person in a different team or having to wait for a pipeline only to realize that it wasn't exactly what we needed. They were never good. They are just much more obvious and perhaps much more painful now that we have these coding agents working next to us.

</details>

### 三大支柱：重构面向机器的基础设施原则

要让平台真正适配 AI Agent，必须遵循三个核心维度：**自助服务**（Self-service）、**API 优先**（API-based）以及**本地化优先**（Local-first）。首先，如果 Agent 需要任何资源，它必须能够独立完成，不存在任何需要等待特定人员干预的环节。真正的自助服务必须是直观且自动化的。如果技术上自称是自助服务，但需要 Agent 从五个不同地方提取组件并拼凑触发，那在机器看来这依然是不可用的。

其次，平台必须基于 API 构建。Agent 极其擅长调用定义良好的 API、CLI 或 **MCP 服务**（Model Context Protocol: 一种允许 AI 模型与外部数据及工具交互的协议）。API 提供了可发现性、架构验证（Schema Validation）以及内置的身份验证机制，这使得 Agent 可以安全、确定地进行尝试，并在失败时通过 API 返回的结构化错误信息进行快速迭代，形成闭环。最后是“左移”策略，即本地化优先。如果某项任务注定失败，它应该在 Agent 的本地环境中立即报错，而不是等到推送代码几分钟后的 CI/CD 流程中才暴露。通过在本地提供 API 封装或验证工具，我们允许 Agent 在本地循环中不断精进，直到任务达成。

<details>
<summary>Original English Source</summary>

So what can we do about it? Well, the first thing to me it has to be self-service. If I need any resources from this platform, I should be able to do it on my own. Similarly, if my agent needs to be able to do anything on the platform, it should be able to do it on its own. There should be no process that requires talking to a specific person or waiting for a specific person to do something. Make it automatic, remove people from the process and make it easy to the greatest extent possible.

The second point is make it API based. Agents are good at calling well-defined APIs. It could also be a CLI on top of the API or something like an MCP server. Generally under all of that, you should have a well-defined API. This is discoverable, it has scheme validation, it also has authentication and authorization in place. With this the agent can go back and forth in a loop until it gets what it needs.

Which brings me to my next point: make it local first. Shift left as much as possible. If something is going to fail, it should fail as soon as possible. So don't make the agent push something to your version control system only to then fail on some workflow after a few minutes. If you can validate things up front, if you can run them just locally, do that. It is important that you give it precise instructions and tell the agent this is how you know you have succeeded at the task. Agents are not going to be looking at graphical interfaces. So make those logs, metrics, traces available via an API or CLI. By doing that, you're letting the agent close the loop.

</details>

### 知识聚合：构建机器可理解的文档与技能系统

文档的结构化是 AI Agent 协同的核心。传统的文档往往在需要时难以寻找，我们提倡两种策略：小型项目建议将文档直接存放在代码库的相关目录下，让 Agent 随时随地获取上下文；大型平台则应建立中心化的发现机制。关键依然是 **API 优先**，Agent 通过 API 消费文档比处理庞大的 HTML 页面要高效得多。

此外，我们应当引入**针对 Agent 的文档规范**，例如使用 `agent.md` 或针对特定 Agent 的指令文件（如 `clipp.md`）。这些文件定义了特定的构建、测试、部署及验证路径。更进一步，我们可以将复杂的平台交互模式固化为 **AI 技能**（Skills: 以 Markdown 描述的、针对特定任务的操作指南），通过描述性的指引告诉 Agent：“当你执行此类任务时，应遵循以下步骤”。这种做法显著降低了开发者（尤其是利用 AI 的开发者）贡献平台的门槛，同时也需要配套的**护栏策略**（Guardrails: 用于确保安全性、合规性及标准化的限制性策略），通过策略引擎（Policy-as-Code）来防止不当操作。

<details>
<summary>Original English Source</summary>

Something that is crucially important is documentation. When we need to expose this documentation to agents, we need to be structured around it. One strategy is keep your documentation next to the code it's documenting. If you're working on something bigger, put it in a centralized place so that the agent can go there and start discovering. Think API first because the agent is going to be much better at consuming the specific bits of documentation that it needs over API.

Of course, when we talk documentation, we can also think about agent-specific documentation like the agent.md files or instructions.mmd depending on your agent of choice. You can tell it: well, you should always build in this way, test in this way, deploy in this way. On top of that, you can also use skills. If you have some conventions, you can codify those in a skill, which is again just a markdown document. By doing that, you're telling the agent when you do this type of task, you should do it like that. I would encourage a combination of guardrails thinking about security or compliance and then on top of that, use these markdown files to help the agents work in the way that you want them to.

</details>

### 闭环验证：利用 AI 契机推动工程治理

最后，任何变革都必须通过数据来衡量成效。我们可以关注 **DORA 指标**（Dora Metrics: 包含部署频率、变更交付周期、平均修复时间及变更失败率的效能衡量体系），观察 AI 的介入是否提升了发布频率或降低了平均故障恢复时间。在金融科技领域，**可靠性指标**（Reliability Metrics）尤为关键，我们需要通过 API 实时监控流量表现和错误率。此外，平台团队还应关注支持请求（Support Requests）的数量：如果自助服务真正起效，人工支持请求应当下降。

一个额外的建议是：如果你的组织过去一直阻挠 API 优先、本地化开发或文档完善等最佳实践的落地，现在就是最佳契机。**“为了 AI”**（AI Excuse）是一个绝佳的借口。从高管到普通员工，每个人都在关注 AI 这个热点。你可以借此机会实现那些本就该存在、却因种种优先级借口被搁置的工程标准。总结来说，打造一个面向 AI Agent 的平台需要：自助服务、API 优先、本地化优先，配合优秀的结构化文档与观测性，并积极拥抱内源贡献与度量驱动的治理。

<details>
<summary>Original English Source</summary>

The way of knowing if it works is by measuring. You can focus on Dora metrics: change frequency, mean time till recovery, lead time. Those metrics are measuring how often your developers are able to release and how good those releases typically go. You can also measure reliability. Or you might want to look at more platform specific metrics such as how many support requests have I got? If people and their agents can do everything on their own, am I then not needed to support them?

Maybe your organization has been resisting some of these best practices like API first platforms or to make them more local friendly or to have the time to write proper documentation. But then you have gotten some resistance because people were focused on other priorities. Take advantage. Everyone from the executive level to the individual contributors are looking at AI now. It is a very hot topic. So you can use AI as the excuse to implement some best practices that again were always best practices if you didn't have the chance to do it until now.

</details>