---
author: The Pragmatic Engineer
date: '2026-03-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=i1tZN41VKcE
speaker: The Pragmatic Engineer
tags:
  - agentic-workflow
  - developer-productivity
  - mcp-protocol
  - software-maintenance
  - ai-infrastructure
title: 优步的智能体转型：从配对编程到异步“同伴编程”的架构实践
summary: 本文详述了 Uber 如何通过构建 Minion、MCP 网关及 Shepherd 等内部 AI 基础设施，实现从 Generative AI 向 Agentic AI 的战略转型。Uber 分享了在自动化单元测试、大规模代码迁移、评审噪音治理以及应对 6 倍成本增长等方面的实战经验，揭示了如何将工程师从日常琐事中解放以专注于创造性工作。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Uber
  - OpenAI
  - Anthropic
  - GitHub
products_models:
  - Michelangelo
  - Minion
  - AutoCover
  - Shepherd
  - AIFX
  - Claude
  - GitHub Copilot
media_books: []
status: evergreen
---
### 范式跃迁：从配对编程到异步“同伴编程”

Uber 的 AI 战略正在经历一场深刻的**智能体转型**（Agentic Shift）。虽然 Uber 在定价和匹配平台中应用 AI 已有多年，但将 AI 整合进工程生命周期以提升生产力则是全新的尝试。Uber 首席执行官 Dara Khosrowshahi 已将 AI 列为公司的六大战略转型之一，目标是让每位员工通过生成式 AI 实现“超人化”的生产力。

在工程领域，这种转变体现为从**配对编程**（Pair Programming）向**同伴编程**（Peer Programming）的进化。在 2022 年到 2023 年的 GitHub Copilot 时代，开发者主要通过同步的“Tab 补全”和 IDE 聊天窗口获得 10% 到 15% 的效率提升。而现在的**同伴编程**范式允许开发者像**技术主管**（Tech Lead）一样，将**库迁移**、**死代码清理**、**文档编写**等**日常琐事**（Toil: 重复性且非创造性的维护工作）以异步方式交付给 AI 智能体执行。这种模式不仅提高了工程师的满意度，更让他们能专注于那些能推动业务增长的创造性工作。随着模型能力的增强，“**氛围编程**”（Vibe Coding: 开发者通过表达意图而非编写具体代码进行开发）已从笑谈变为现实。

<details>
<summary>Original English Source</summary>

AI is not new to Uber. Our fairs platform, our matching platform has been using AI methodology for years and years. It's one of the things that sets us apart from the competitors. But over the past few years, using AI as part of the engineering productivity and engineering life cycle, that's fairly new. DAR has stated that AI is one of our six strategic shifts. We move from a early AI powered company into a generative AI powered company. Nowadays it's more fashionable to be an agentic powered company but the concept still holds where AI is enabling people to become superhumans in terms of their productivity.

We want to focus on enabling our engineers to focus on creative work rather than toil. When we push some of the boring stuff to it, upgrades, migrations, bug fixes, not only does it result in much higher satisfaction from our engineers, they're able to push our product and create features in ways that we didn't even thought was possible.

We are going from pair programming to peer programming. Back in the good old days of 2022 and 2023 when GitHub copilot first came out, it was a novel way of augmenting development. You had synchronous tab completion, an ID chat window. We saw about a 10 to 15% bump in overall diff velocity. But over the past year, the paradigm has shifted to peer programming where you could hand off workloads that are running asynchronously. The models are so good, they're so accurate that all you need to do with the AI agent is to redirect it in certain ways. We imagine developers acting as their own tech leads, directing AI agents to execute asynchronously. This concept of vibe coding, which was just a joke a couple years ago, is becoming much more prominent.

</details>

### 智能体底座：MCP 网关与 AIFX 体系

Uber 的智能体架构并非闭门造车，而是“站在巨人的肩膀上”。其核心底座是历史悠久的 **Michelangelo** 机器学习平台，它提供了**模型网关**（Model Gateway）来代理主流的边缘模型（Frontier Models）或托管内部模型。为了让智能体具备**组织记忆**，系统必须能够访问源代码、工程文档、Jira 任务及 Slack 信息。

去年，Uber 迅速部署了**模型上下文协议**（Model Context Protocol: 行业标准的 AI 上下文集成协议），并组建专门团队构建了**中央 MCP 网关**。该网关统一处理外部与内部 MCP 的代理、鉴权、遥测和日志，并提供**沙箱环境**供开发者测试和发现新的 MCP。此外，Uber 开发了 **AIFX** 命令行工具，作为开发者接入智能体基础设施的前哨。**AIFX** 负责统一配置和更新各类 Agent 客户端（如 Cursor、Claude Code 等），并管理 MCP 插件的安装与提示词（Prompt）优化，确保开发者能够即插即用，连接到后台的**任务基础设施**。

<details>
<summary>Original English Source</summary>

We are building on the shoulders of giants. We have our historic Michelangelo platform which provides a model gateway so that we can proxy and talk to the main frontier models or host internal models. On top of that, we have context at Uber: source code, engineering documentation, Jira tickets, Slack information. To have an effective agent have organizational memory, it needs to get access to these.

One of the key ones is our deployment of MCPs throughout Uber. We moved very quickly to design a strategy and built a central MCP gateway. This allows us to both to proxy external and internal MCPs and expose those in a consistent way to engineers that handles authorization, telemetry, logging. We also provide a registry and a sandbox so that developers can play with these MCPs.

We built this tool called AIFX. It's a CLI and it is the forefront of what developers are using to access our agent infrastructure. It provides the central ability to provision, configure and update the agent clients themselves, install and discover MCPs from the registry, and deploy standard configuration management so that people have more effective prompts and configurations right away.

</details>

### Minion 平台：全自动后台任务执行引擎

为了解决传统 IDE 插件（如 Cursor 或 Claude Code）需在第三方基础设施运行后台智能体的局限，Uber 构建了内部原生平台 **Minion**。**Minion** 运行在 Uber 的 **CI 平台**上，可以直接访问 Monorepo 源代码及内部网络环境，实现了完全的自主运行。

**Minion** 的核心价值在于它将开发者的工作流从“持续互动”转变为“异步分发”。开发者只需输入一个提示词，甚至可以同时启动多个后台智能体，然后继续其他任务。**Minion** 提供了丰富的**提示词模板**，并内置了**提示词改进器**（Prompt Improver），能自动分析并优化低质量的输入以提高成功率。任务完成后，**Minion** 会通过 Slack 通知开发者，并自动生成包含测试计划和 Jira 链接的 **GitHub PR**。在实际应用中，开发者将 70% 的工作载荷投向了“日常琐事”任务，因为这类任务（如库升级或迁移）的起止状态明确，智能体执行的准确率远高于模糊的特性开发。

<details>
<summary>Original English Source</summary>

We wanted these background agents to be running autonomously. External vendors were running their background agents in other people's infrastructure. We built a product called Minion, our formal background agent platform. It leverages all of Uber's existing infrastructure, runs in our CI platform. This has our monorepos checked out, ready to work in quickly. It's integrated through the web interface, Slack, GitHub PRs, and CLI.

One other powerful thing is this offers good defaults. We have these existing templates that users can choose from that are well-written prompts. We built into this a prompt improver. The ability to analyze the prompt and make suggestions that the user can accept on how to have a higher chance of success.

A few minutes later, the Slack notification pings them: "the minion task is done. You can go look at the PR here." Our minion bot co-authors this with the person that kicked it off. We have a link to Jira, the test plan of how it verified. It's much easier for the developer to just dump in a prompt and get a PR out of that as opposed to all of the context switching. What we saw is 70% of the workloads that developers are pushing into the system were toil tasks. The accuracy was higher compared to more ambiguous workloads.

</details>

### 代码生命周期治理：从 Inbox 到自动迁移

随着 AI 生成代码量的爆发，**代码评审**（Code Review）成为了新的瓶颈。为此，Uber 推出了一系列配套工具：**Code Inbox** 作为一个统一的收件箱，利用**智能分配算法**，根据代码所有权、历史贡献、时区甚至日历忙闲状态，将 PR 精确分派给最合适的评审者；**U Review** 则是评审辅助平台，通过内置的**评审评分器**（Review Grader）过滤低价值的琐碎评论（Nits），确保开发者只关注高置信度的核心问题。

针对代码质量，Uber 开发了 **AutoCover** 系统。该系统基于内部的 **LangX SDK**（构建于 LangChain 之上），每月自动生成并合并超过 5000 个单元测试，其代码覆盖质量是通用智能体的三倍。对于更重头的**代码维护**工作，Uber 启动了 **AutoMigrate** 计划，其中 **Shepherd** 平台负责管理成百上千个 PR 的全生命周期。通过简单的 YAML 定义，**Shepherd** 能自动调用 **OpenRewrite** 或 **Minion** 执行大规模的库升级（如将 Java 服务迁移至 Java 21），并处理 PR 的定时刷新、通知及评审队列集成。

<details>
<summary>Original English Source</summary>

Developers are spending more and more time in planning and code review because there's so much more code being generated. We built a tool called Code Inbox, a unified inbox for PRs. It's designed to remove noise. We put a lot of work into the smart assignments, trying to find the most relevant person based on ownership, history, time zone, and calendar availability.

U Review is designed for review help itself. We have a pre-processor and a set of plugins. We have a review grader to filter low-value comments. We only want to put the high confidence changes that the developer really needs to focus on, not little nits.

We built a system called AutoCover to generate unit tests. We're seeing about 5,000 tests generated and merged per month. It has a critic engine and an independent test validator to uplevel the test quality. For code maintenance, we created a scalable version of how we handle large scale change called AutoMigrate. The key platform is Shepherd. It's a web UI where migration authors can track all of the PRs associated with a migration. Shepherd handles generating those PRs, refreshing them, and notifying the people that need to review it.

</details>

### 现实挑战：组织采纳与“贵得离谱”的成本

尽管技术取得了飞跃，但 Uber 仍面临严峻的非技术挑战。首先是**技术迭代速度**与**组织承诺**的矛盾：构建 AutoCover 等系统需要投入数十人月，但底层技术可能在几个月内就面临过时。Uber 的应对策略是建立**强抽象层**，并保持“不与特定技术结婚”的心态，随时准备用更好的行业方案替换自研工具。

其次是**人的问题**。即便演示显示 VPs 都能在 24 分钟内落地代码，基层开发者的采纳速度依然慢于预期。Uber 发现，**自上而下的行政指令**效果有限，最有效的手段是**分享成功案例**——当工程师看到同僚利用 AI 获得具体收益时，采纳率会呈爆发式增长。最后，AI 的**成本问题**（Cost）日益凸显：自 2024 年以来，Token 消耗成本增长了至少 6 倍。Uber 不得不推行**Token 责任制**，在基础设施层面自动选择模型：使用高性能模型（如 Claude Opus/Sonnet）制定计划，而使用低成本模型执行具体编码，从而在不增加开发者负担的前提下优化成本。

<details>
<summary>Original English Source</summary>

The leaders when it comes to AI tech are changing pretty frequently. We need to commit dozens of people on projects that might be running for months. So we can't just change our mind after a quarter. Making sure that we have the right abstraction layers in place. We should not be married to the tech that we're building. delivering impact for Uber is what matters.

Our adoption for this technology has been relatively slow. Part of it is because we're telling them to take a risk by operating in a very different way. The more successful technique is actually just sharing wins. Promoters pushing techniques to their peers. Engineers trust other engineers as opposed to directors like me.

The cost of AI is too damn high. Since 2024 our costs have gone up at least 6x. The GPU costs are high and memory costs are really high. So we've had to be more responsible about how we use tokens. We help developers think about the right model to form the plan and then lower cost but still effective models to do the execution. We want to have the infrastructure decide for them so that we reduce the friction but also optimize our costs.

</details>