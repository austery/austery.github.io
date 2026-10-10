---
author: How I AI
date: '2026-09-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=AbZODZ_4VaM
speaker: How I AI
tags:
  - enterprise-agent
  - agentic-workflow
  - context-engine
  - tool-governance
  - sandbox-execution
title: 揭秘 Stripe 企业级智能体 Kai：打造全员使用的一体化内部大脑
summary: 本期《How I AI》邀请到 Stripe 工程经理 Sherrod，深度剖析 Stripe 内部全员使用的 AI 智能体大脑 Kai。内容涵盖组织架构上下文感知、三层数据检索与查询治理、沙盒执行环境、动态工具与技能（Skill）系统、以及基于项目的权限与安全管控策略。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Stripe
products_models:
  - Kai
media_books:
  - How I AI
status: evergreen
---
### 智能体的基础设施冲击与安全防护

**Sherrod**: **智能体（Agents）**非常擅长把你的基础设施搞垮。事实证明，智能体就像是放大了你所有的故障模式，成倍放大了可能出现的问题。曾经有智能体失控失常，甚至差点搞垮核心系统。在项目中有一件很酷且非常具体的事情，就是**工具策略（tool policies）**的概念。假设你是人力资源团队的一员，处理着大量敏感信息。你肯定不希望智能体失控并把这些敏感数据写入所有 **Stripe** 员工都能访问的公开 Google 文档中；但你同样也不想因为工作负载敏感，就对他们说“你们不能使用任何工具”。

<details>
<summary>Original English</summary>

**Sherrod**: Agents are very creative at bringing your infra down. It turns out that agents just like dial up all your failure mode. It just multiplies the amplitude of problems you can get. There were agents that went rogue. There were agents that may have almost taken down core systems. One of the cool things about projects that can be very concrete for people is the idea of tool policies. Let's say you're a person on the HR team who's dealing with a bunch of sensitive information. You really don't want the agent to sort of go rogue and put that sensitive data into some public Google document that all Stripes can access, but you also don't want to tell them, oh, you can't use any tools because your workloads are too sensitive.

</details>

**Claire**: 我非常喜欢这种数据智能体可以经历的**三层分诊机制（three layer triage）**，这真的很聪明：先查找现有的分析报告；然后使用分析语义层找到合适的查询；如果实在不行，再降级到数据目录去自己编写查询。你的数据仓库必须对海量高并发查询具备极强的弹性与容错能力，因为当智能体不确定时，它就会直接采用暴力尝试。

<details>
<summary>Original English</summary>

**Claire**: I love this idea of this like three layer triage that a data agent can go through and that's really smart. Find existing reports, then use the analytics layer to find the right query. Then if like you really have to fall down to the data catalog and write your own query. Your data warehouse has to be very resilient to high volume queries because when in doubt an agent will just brute force it.

</details>

**Sherrod**: 我们可以测试一下，它将触发一个**人机协同（human-in-the-loop）**的工作流：“帮我和 Wong 创建明天太平洋时间上午 11 点的日历邀请”。这不是最好玩的部分，最好玩的是我之前展示的。智能体能力极强、极富创造力，所以我们必须施加一些限制，防止它们失控。

<details>
<summary>Original English</summary>

**Sherrod**: We could test this out and it's going to kick off what is a human in the loop workflow. Create a calendar invite for me and Wong tomorrow at 11:00 a.m. Pacific. This isn't the fun part. The fun part is what I showed before. Agents are really good. They're very creative. So, we got to put some restrictions on them so they don't go rogue.

</details>

### 对话开场：Stripe 内部智能体 Kai 的诞生

**Claire**: 欢迎回到《**How I AI**》。我是 Claire，一名产品负责人和 AI 痴迷者，致力于帮助大家用这些新工具打造出更好的产品。今天我们邀请到了 **Sherrod**，他是 **Stripe** 的工程经理，也是打造了他们内部公司大脑与企业智能体 **Kai** 的团队成员之一。他将向我们展示为什么你会想要为自己的公司构建专属定制智能体、让 Kai 如此卓越的治理与控制机制是什么，以及如何不仅构建单个技能，而是构建一套完整的系统。

Sherrod，欢迎来到节目！在开始现场演示之前，能否先给我们介绍一下 Kai 是什么？你们为什么要构建它？在 Stripe 这种技术底蕴极其深厚的公司里，它是如何融入员工日常工作流程的？

<details>
<summary>Original English</summary>

**Claire**: Welcome back to How I AI. I'm Claire, product leader and AI obsessive here on a mission to help you build better with these new tools. Today we have Sherrod, an engineering manager at Stripe and part of the team who built Kai, their internal company brain and company agent. He's going to show us why you might want to build your own custom agent for your company. What are the governance and control mechanisms of Kai that make it super special and how to build not just a single skill, but a whole system.

Sherrod, welcome to the show. Before we get into the live demo, could you give us an overview of what Kai is, why you built it, and how it fits into daily workflows at a company as engineering-forward as Stripe?

</details>

**Sherrod**: 谢谢邀请，Claire，非常高兴来到这里。Kai 是 Stripe 的内部 AI 助手和平台，我们将其视为公司的“大脑与双手”。关于为什么要自研，主要有三个核心原因：

第一是**上下文与权限安全**。现成的商业工具无法深度理解 Stripe 内部庞大而复杂的业务上下文，比如组织架构、内部权限体系以及跨系统的数据隔离。

第二是**工具集成与执行能力**。我们希望智能体不仅仅能聊天或做简单的检索增强生成（RAG），还能代表员工执行真实业务操作——从编写和运行数据查询、部署沙盒服务，到与内部系统交互。

第三是**可治理性与定制化**。我们希望赋予每个团队和个人构建自己专属“技能（Skills）”和“项目（Projects）”的能力，同时平台层面必须具备极其严格的护栏、审计日志和成本控制。

在日常工作中，Kai 已经深度嵌入到员工的日常沟通与开发工具中。无论是非技术人员查询报表，还是工程师调试代码，Kai 都在发挥中枢大脑的作用。

<details>
<summary>Original English</summary>

**Sherrod**: Thanks for having me, Claire, super excited to be here. Kai is Stripe's internal AI assistant and platform, essentially what we consider the company's brain and hands. In terms of why we built it in-house, it really came down to three primary pillars:

First is context and permission boundary. Off-the-shelf tools simply don't have deep understanding of Stripe's internal complex landscape—our organizational charts, permission graphs, and data silos.

Second is tool integration and execution. We wanted an agent that goes beyond simple chatting or naive RAG. We needed it to take actions—running queries, spinning up sandbox environments, and driving internal workflows.

Third is governability and extensibility. We wanted every team to easily build their own custom Skills and Projects, while maintaining enterprise-grade guardrails, auditable trails, and cost efficiency.

Today, Kai is natively woven into where employees work daily. From non-technical folks pulling metric dashboards to engineers debugging services, Kai acts as that ubiquitous assistant.

</details>

### 有界上下文引擎与组织架构感知

**Claire**: 总结一下我刚才听到的内容，以及你们构建到 Kai 中的一些独特功能：首先是这种**有界上下文引擎（bounded context engine）**。你们能够感知员工在组织架构中的位置、正在处理的工作以及权限范围。

<details>
<summary>Original English</summary>

**Claire**: So just to kind of repeat back what I heard and some of the unique things that you built into Kai is one this sort of bounded context engine. So you know where people sit in the org chart, what they're working on, and their permission scope.

</details>

**Sherrod**: 我们允许员工自主选择向 Kai 开放多少访问权限。但开箱即用的是，Kai 清楚知道你是谁、你在组织架构图中的位置。此外，它还掌握一些非常有用的全局上下文，比如你所在团队的职责、你们负责的服务，以及你平时频繁协作的同事。这种上下文感知是渐进式的，既保障了隐私与安全，又让交互免去了大量的重复背景铺垫。

<details>
<summary>Original English</summary>

**Sherrod**: We allow people to select how much they give Kai access to. But out of the box Kai knows like who you are and where do you sit in the org chart, right? And it also knows some helpful global context like what your team does, what services you own, and who you collaborate with frequently. This contextual awareness is progressive, ensuring privacy while eliminating repetitive prompting.

</details>

**Claire**: 太棒了。所以你们拥有这个由最终用户在一定程度上可控的上下文引擎，员工可以自主决定让系统自动摄取多少信息。而且你们还拥有与各种底层系统的深度连接。我们非常期待看到实际操作！不如直接进入演示，看看 Kai 是如何在具体任务中发挥作用的？

<details>
<summary>Original English</summary>

**Claire**: Great. So, you have this context engine but controlled by the end user to some extent. So, you can decide as an employee how much you want to automatically ingest into the system. You have these deep connections. We'd love to see it in action! Should we jump right into the demo and see how Kai handles a concrete task?

</details>

### 现场演示：自动构建数据看板与三层数据检索

**Sherrod**: 没问题，非常乐意演示。我这里准备了几个常用的提示词。我们今天要做的，是实际创建一个数据看板，因为在 Stripe，大家都极度崇尚数据驱动。

我现在向 Kai 发送一个请求：“帮我构建一个分析 Kai 内部采用率和各部门使用情况的交互式看板”。

大家可以看到，界面上显示 Kai 正在开始工作，它在后台调用相应的**工具（Tools）**与**技能（Skills）**。

<details>
<summary>Original English</summary>

**Sherrod**: Yeah. Absolutely happy to do it. So I have a few trusty prompts here. What we're going to be doing today is we're actually going to be creating a dashboard because Stripes, we love our data. And so I'm giving Kai a prompt: "Build me an interactive dashboard analyzing Kai's adoption and usage across different orgs." As you can see on the screen, Kai is picking up the prompt and pulling for relevant tools and skills.

</details>

**Claire**: 我看到它在拉取工具和技能。这是它执行框架（harness）的一部分吗？它是否经过调优，能够自动寻找并调用解决该问题所需的工具和技能？

<details>
<summary>Original English</summary>

**Claire**: And I see it pulling for tools and skills. So is this like part of the harness which is it's kind of like tuned to go find what it can use to solve this problem?

</details>

**Sherrod**: 没错。这里有两个核心概念：工具和技能。我们都知道工具基本上是“可执行的原子操作能力”，而技能则是“完成特定复杂任务的工作流或专业流程”。

当 Kai 接收到构建数据看板的任务时，它会启动我们之前提到的三层分诊与检索逻辑：
1. **第一层（现有资产）**：它会先去检索内部现有的成熟报表和数据产品，看是否已经有现成的结果，避免重复计算。
2. **第二层（语义分析层）**：如果现成报表不满足，它会进入分析语义层（Metrics / Analytics Layer），查找标准化的指标定义和预构建的模型。
3. **第三层（数据仓库直查）**：如果依然需要定制化数据，它才会降级到数据目录去查找底层表结构，并亲自编写 SQL 查询。

<details>
<summary>Original English</summary>

**Sherrod**: Absolutely. So there are two things. We all know what tools are and we all know what skills are. Tools basically being the atomic capabilities you can execute, and skills are like essential workflows or specialized recipes.

When Kai gets a request like building a dashboard, it activates that three-layer triage:
1. First Layer: Search existing reports and assets to see if the answer already exists.
2. Second Layer: Use the analytics/semantic layer to find canonical metric definitions and pre-modeled datasets.
3. Third Layer: Fall back to data catalogs and generate custom SQL against raw tables if necessary.

</details>

**Claire**: 看起来非常准确。你之前要求它不要犯任何错误。

<details>
<summary>Original English</summary>

**Claire**: It looks right. I told it not to make any mistakes.

</details>

**Sherrod**: 哈哈，是的，这就是这些工具和技能正在执行的事情。它在受控的环境中安全地组装数据和前端组件。

<details>
<summary>Original English</summary>

**Sherrod**: So, [laughter] that's what these tools and skills are doing. It's safely assembling data and UI components in a controlled environment.

</details>

### 数据智能体的基础设施挑战：放大故障模式

**Claire**: 趁着它在后台运行，我想请教一个专门关于构建优秀**数据智能体（data agents）**的问题。因为我和很多公司交流过，几乎大家尝试构建的第一个内部智能体都是“数据问答智能体”，但往往也是最容易翻车的。在 Stripe 这样庞大的数据规模下，你们是如何解决数据准确性、表命名混乱以及幻觉问题的？

<details>
<summary>Original English</summary>

**Claire**: Yeah. I have a kind of separate question while this is running specifically about making great data agents because I talk to a lot of companies and almost universally the first internal agent they try to build is a data agent, and it often fails. At Stripe's data scale, how do you handle data veracity, messy schema discovery, and hallucination?

</details>

**Sherrod**: 我想向听众朋友们强调几点，顺便夸一下 Stripe 团队：Stripe 之所以能让数据智能体顺畅工作，很大程度上得益于我们在 AI 爆发之前多年来在**数据基础设施**和**数据治理**上的持续投入。

智能体并不是凭空产生魔法的。如果你底层的表结构混乱、没有文档、指标没有统一口径，那么智能体只会把这些混乱成倍放大。

我们在数据层面上做了几件关键事情：
1. **严格的指标定义标准（Semantic Layer）**：确保“活跃用户”或“交易量”在所有报表中只有一个唯一真实来源（Single Source of Truth）。
2. **全面的元数据与数据目录**：每一张生产表都有清晰的 Ownership、描述和常用查询模式。
3. **数据访问沙盒与配额限制**：防止智能体生成全表扫描或死循环查询搞垮数据库。

<details>
<summary>Original English</summary>

**Sherrod**: I want people that are listening to hear a couple things, and I'm going to make the Stripe team blush. One of the reasons why this works well at Stripe is our deep investment in data infrastructure and data governance pre-dating the AI era.

Agents don't magically fix broken foundations. If your schemas are messy, undocumented, and metrics lack single sources of truth, an agent will just amplify that chaos.

Key things we've invested in:
1. Canonical Metric Layer: Standardized definitions so "active users" or "volume" mean the exact same thing everywhere.
2. Rich Metadata & Catalogs: Clear ownership, descriptions, and verified query templates.
3. Sandbox Execution & Guardrails: Strict timeout, partitioning limits, and compute quotas so rogue queries never take down warehouses.

</details>

**Sherrod**: 正如前面提到的，智能体会彻底放大所有的故障模式。如果人类工程师写错一个查询，可能只是浪费一次计算；但智能体会不知疲倦地不断重试、并发执行数十次暴力破解，瞬间带来巨大的负载冲击。因此，弹性的底层基础设施和健全的限流断路器是必须具备的前提。

<details>
<summary>Original English</summary>

**Sherrod**: It turns out that agents just dial up all your failure modes; it multiplies the amplitude of problems you can get. If a human engineer writes a bad query, it fails once. An agent might aggressively retry or brute-force variants dozens of times in parallel, causing massive compute spikes. Resilient infra and circuit breakers are non-negotiable.

</details>

### 看板成果展示与轻量化团队运作

**Claire**: 太精辟了。在我们聊天的这段时间里，Kai 已经在沙盒中完成了看板的生成。让我们看看 Kai 使用这些技能和工具实际构建出了什么！

<details>
<summary>Original English</summary>

**Claire**: I love it. Okay, so we've yapped while Kai ran. Let's show what Kai actually generated using these skills and tools in Sandbox.

</details>

**Sherrod**: 好的，请看屏幕。这里是 Kai 生成的完整交互式看板。可以看到，Kai 在 Stripe 内部的采用率非常高，几乎全公司都在使用 Kai。我们看到工程团队、营销团队、支持团队的高频使用数据，还可以点击下钻查看不同维度的趋势。

<details>
<summary>Original English</summary>

**Sherrod**: Yeah, of course. So here's what you see. You see that Kai adoption is looking good and pretty much everyone at Stripe uses Kai. We can see high engagement across engineering, marketing, and support, with full interactive slicing and dicing.

</details>

**Claire**: 哈哈！我看到市场营销团队的使用率几乎是 100% 投入，对吧？

<details>
<summary>Original English</summary>

**Claire**: [laughter] I love the fact that our marketing team is like a 100% all-in, right?

</details>

**Sherrod**: 他们非常需要这个工具！我不认识任何一个不需要快速搭建应用或生成数据报表的市场营销人员。这完全体现了产品市场契合度（PMF）。

<details>
<summary>Original English</summary>

**Sherrod**: They need it, right? I don't know a single marketing person that doesn't either want some sort of app built or some sort of dashboard. So, I think you have product market fit.

</details>

**Claire**: 能够支持全公司 10,000 名员工的高频使用，支持这样一套系统的团队一定非常庞大吧？你们有 20 位工程师吗？

<details>
<summary>Original English</summary>

**Claire**: To power this for 10,000 Stripes across the company, that must require a huge dedicated team, right? Do you have like 20 engineers on this?

</details>

**Sherrod**: 绝对没有 20 位工程师！Stripe 一直保持着精简、敏捷且快速的运作风格。我们的核心团队实际上**不到 10 个人**。我们在短短两周内就推出了 V1 版本，并迅速在全公司普及。之所以能做到这一点，是因为我们站在了 Stripe 强大的底层基础设施之上，我们专注于构建智能体的调度 Harness、上下文引擎和治理体系。

<details>
<summary>Original English</summary>

**Sherrod**: Definitely not 20 engineers. Stripe runs fairly lean, very nimble, and very fast. Our core team is actually fewer than 10 people. We built the V1 in just a couple of weeks and scaled it across the company. We could do that because we leveraged Stripe's existing robust infra and focused our efforts on the agent harness, context engine, and governance.

</details>

### 赞助商插播：Hyper Agent

**Claire**: 太棒了。本期节目由 **Hyper Agent** 赞助播出。Hyper Agent 是一个用于部署全天候常驻智能体以实际运行业务的平台。通过 Hyper Agent，你可以在云端构建智能体并安全部署，支持连接各种数据源和工作流自动化。

<details>
<summary>Original English</summary>

**Claire**: I love it. This episode is brought to you by Hyper Agent, the platform for deploying always on agents that actually run your business. With Hyper Agent, you build agents in the cloud and deploy them securely with integrations into your workflows and data sources.

</details>

### 深入剖析：技能（Skills）与项目（Projects）的架构机制

**Sherrod**: 接下来我打算深入展示两件核心机制：**技能（Skills）**和**项目（Projects）**。

当大家看到生成的看板时，每个人都很喜欢，但很多时候我们不希望每次都从头输入一长串复杂的提示词。

我们构建了技能系统。熟悉类似 **Cursor** 或其他先进 AI 产品的工程师应该对此不陌生，但我们在企业级协作上做了很多升级。

更关键的是**项目（Projects）**功能。项目不仅仅是一个存放对话的文件夹，更是一个**独立的权限边界与安全策略容器**。

<details>
<summary>Original English</summary>

**Sherrod**: I'm going to do two things: I'm going to show skills and I'm going to show projects. When people see the dashboard, everyone loves it, but you don't want to re-explain complex prompt instructions every time.

So we built Skills. It should be familiar to folks who've used Cursor or modern AI tooling, but tailored for enterprise collaboration.

And even more crucially, Projects. A project is not just a folder for grouping chats; it is an isolated boundary for permissions, context, and security policies.

</details>

**Sherrod**: 举个具体的例子：如果你是人力资源（HR）团队的一员，处理着极具保密性的薪酬或员工绩效数据。你希望智能体在项目内可以使用特殊的工具来处理这些数据，但你绝对不希望智能体跨越边界把敏感数据输出到公开空间。

在 Kai 的项目体系中，我们引入了**工具策略（Tool Policies）**：
- 你可以明确定义某个项目允许调用哪些工具、禁止调用哪些工具；
- 智能体只能在项目限定的上下文和沙盒内执行操作；
- 从而让敏感业务团队既能享受 AI 的自动化红利，又不必承担数据泄露的风险。

<details>
<summary>Original English</summary>

**Sherrod**: For example, if you're on the HR team handling confidential compensation or performance data, you want the agent to use specialized tools within that project, but you must prevent sensitive data from leaking into public Google Docs.

Within Kai Projects, we built Tool Policies:
- Explicitly configure allowed vs. denied tools per project.
- Bound agent execution strictly to that project's sandbox and context.
- Enable high-sensitivity teams to leverage AI safely without security anxiety.

</details>

**Claire**: 我非常喜欢这种设计！目前很多现成工具只能在用户个人级别进行全局配置，一旦配置就会应用到所有会话中，无法根据当前具体任务和安全等级动态隔离。

<details>
<summary>Original English</summary>

**Claire**: Yeah, I love this because I think a lot of the existing tools let you maybe configure some of this at the individual level, but then it applies to every session. It's not contexted to what you're working on or the risk profile.

</details>

### 技能开发体验：低代码 IDE 与生命周期管理

**Claire**: 现场演示往往能说明一切。这里展示的不仅是一个技能创建器，还有专属的技能规范（Spec）和技能编辑器，让员工可以轻松测试、编辑、优化和管理技能。

<details>
<summary>Original English</summary>

**Claire**: This is what you see when you do it live. You have kind of a skill creator, a specific spec, and a skill editor that you can test, edit, optimize, and manage.

</details>

**Sherrod**: 虽然工程师喜欢折腾 Markdown 和 Python 代码文件，但提供一个兼具 IDE 体验的直观 UI 界面，能极大提升全员的生活质量，让非工程师也能参与到技能共建中。

<details>
<summary>Original English</summary>

**Sherrod**: While engineers love fussing around in Markdown and Python files, having a little IDE-like UI allows everyone across the company to get that quality of life improvement.

</details>

**Claire**: 另外，随着大家创建的技能越来越多，你们是如何防止技能泛滥和垃圾技能堆积的？比如当某个技能超过 30 天没人使用时，系统会有提示吗？

<details>
<summary>Original English</summary>

**Claire**: And with so many people creating skills, how do you prevent skill sprawl? For example, if a skill isn't used for 30 days, do you notify the owner and deprecate it?

</details>

**Sherrod**: 没错！在这些系统中，你无法将**质量**与**数量**割裂开来。**上下文就是一切**——你塞给大模型的无关上下文越多，模型的推理性能和准确度下降得就越快。

我们建立了一套自动化的技能生命周期管理机制：
- 持续监控技能的调用率和有效性；
- 对于长期闲置或低质量的技能，系统会自动发送通知提示归档；
- 未获响应的闲置技能会自动进入弃用（deprecation）状态，移出全局检索索引，确保模型上下文时刻保持干净高效。

<details>
<summary>Original English</summary>

**Sherrod**: 100%. You cannot separate quality and quantity when it comes to these systems because context is everything. The more unrelated context you throw into the AI, the worse it performs.

We built automated lifecycle management for skills:
- Monitor invocation frequency and quality metrics.
- Alert owners when skills go unused.
- Unmaintained skills transition to deprecated status and are removed from runtime discovery, keeping the agent's prompt context lean and focused.

</details>

### 核心亮点总结与经验提炼

**Claire**: 太精彩了！我为观众朋友们梳理总结一下关于 Kai 的几大核心亮点：
1. **个性化有界上下文**：深度融合组织架构图与员工职责，按需可控授权。
2. **三层数据检索与沙盒执行**：报表、指标语义层、数据目录逐级回退，配合安全沙盒。
3. **基于项目的工具策略**：为团队划分安全边界，精细化控制工具权限。
4. **精简高效的工程团队**：依靠不到 10 人的敏捷团队，在坚实基础设施支撑下服务 10,000 名员工。

这真的是非常惊人的成果！

<details>
<summary>Original English</summary>

**Claire**: Amazing! I just want to recap for folks the high-level takeaways about Kai:
1. Personalized Bounded Context: Org-chart awareness with progressive disclosure.
2. Three-Layer Data Triage & Sandbox: Existing reports -> semantic layer -> raw catalog, executed safely.
3. Project-Level Tool Policies: Strict security boundaries for high-risk domains.
4. Lean Team Leverage: Serving 10,000 Stripes with fewer than 10 engineers by building on solid infra foundations.

That is an incredible achievement.

</details>

**Sherrod**: 哈哈，总结得太精辟了！当然，我也必须强调，所有这一切都离不开全公司各个底层平台团队此前打下的坚实地基。

<details>
<summary>Original English</summary>

**Sherrod**: That was a fantastic summary. And of course, credit goes to all the underlying platform infrastructure teams across Stripe whose work made this possible.

</details>

### 快问快答与结尾

**Claire**: 在结束之前，我们来进入两道轻松的快问快答环节。第一个问题：抛开 Kai 和工作，在日常生活中，你最喜欢的个人 AI 工作流或用例是什么？

<details>
<summary>Original English</summary>

**Claire**: Before we get out of here, let's do two lightning round questions. First: putting Kai aside for a second, what is your favorite personal AI workflow outside of core work?

</details>

**Sherrod**: 在工作之余，我非常喜欢利用 AI 来协助我进行信息过滤和任务提醒。我构建了一套工作流，让 AI 帮我监控所有待办和重要通信，确保我不会遗漏关键事项。

<details>
<summary>Original English</summary>

**Sherrod**: Honestly, I have this whole workflow around using AI to make sure I don't miss important threads or tasks, surfacing key items so nothing slips through the cracks.

</details>

**Claire**: 很多人总是在想怎么给智能体派活，而我常说：我更希望智能体反过来给我派活——提醒我“Claire，请填写这个表单”、“Claire，去完成这件事”。

<details>
<summary>Original English</summary>

**Claire**: Exactly. We think a lot about how to put agents to work, but I often want agents to put me to work: "Claire, please fill out this form; Claire, please review this."

</details>

**Sherrod**: 确实如此！至少在智能体彻底搞清楚我们所做的一切之前，这几年我们还能这样协作。

<details>
<summary>Original English</summary>

**Sherrod**: Yes! For a few more years at least, until they figure out everything we're doing.

</details>

**Claire**: 最后一个问题：当 AI 没有按你的预期执行指令时，你会怎么做？你会对它发脾气吼叫吗？

<details>
<summary>Original English</summary>

**Claire**: Last question: when AI isn't listening or doing what you want, what do you do? Are you a yeller in prompts?

</details>

**Sherrod**: 我可能会把提示词再发一遍，或者偶尔用全大写字母强调一下，但我不太喜欢对 AI 吼叫。那样感觉怪怪的，就好像我在对训练模型的工程师吼叫一样。

<details>
<summary>Original English</summary>

**Sherrod**: I might repeat the prompt or occasionally use all-caps, but I don't like shouting at AI. It feels wrong, almost like I'm shouting at the engineers who trained it.

</details>

**Claire**: 就像我们很多嘉宾一样，你采取的是“温和育儿（gentle parenting）”式的沟通方式：“我知道你能做得更好，我相信你。”

<details>
<summary>Original English</summary>

**Claire**: Like many of our guests, you gentle-parent the AI: "I know you can do better, I believe in you." [laughter]

</details>

**Sherrod**: “我没有生气，我只是对你感到失望，Kai。”

<details>
<summary>Original English</summary>

**Sherrod**: "I'm not mad. I'm just disappointed, Kai. You should have done better."

</details>

**Claire**: 太有意思了！今天的分享非常有启发性，为我以及许多企业级 AI 探索者提供了宝贵的实践思路。大家可以在哪里关注你和你的动态？

<details>
<summary>Original English</summary>

**Claire**: I love this! This has been super insightful and gave me so many ideas for enterprise AI adoption. Where can folks follow you and your work?

</details>

**Sherrod**: 非常感谢邀请，这是一次非常愉快的交流！能够分享 Stripe 的经验是我的荣幸，感谢大家的时间。

<details>
<summary>Original English</summary>

**Sherrod**: Thank you so much for having me, this was a lot of fun. Huge thanks to the audience, and it's been an amazing time!

</details>

**Claire**: 再次感谢 Sherrod 和 Stripe 团队的慷慨分享！感谢大家的收听与观看。如果你喜欢本期节目，请在 YouTube 上点赞、订阅并留下你的评论；也可以在 Apple Podcasts、Spotify 等各大播客平台收听并给予好评。访问 howiaipod.com 可了解更多剧集。我们下期见！

<details>
<summary>Original English</summary>

**Claire**: Thank you! Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or leave us a comment. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Visit howiaipod.com for more episodes. See you next time!

</details>