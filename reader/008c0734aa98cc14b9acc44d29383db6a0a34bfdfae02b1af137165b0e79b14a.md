---
author: AI Engineer
date: '2026-08-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=32nrHU6zHU8
speaker: AI Engineer
tags:
  - agentic-architecture
  - context-management
  - observability
  - guardrails
  - agent-evaluation
title: 从单体到多智能体：Navan 生产级 AI Agent 架构演进与落地实践
summary: Navan 首席架构师 Roberto Milev 与架构团队成员 Uday 分享了生产级 AI Agent 的参考架构演进。内容涵盖运行时持久化、动态上下文与技能管理、基于轨迹评估与 Hooks 的可观测性体系、企业级安全护栏，以及从单 Agent 渐进式加载到 A2A 协议的编排权衡。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Navan
  - AWS
products_models:
  - Agent Core
media_books: []
status: evergreen
---
### 范式转移与单智能体基础

**Roberto Milev**: 大家好，欢迎参加我们的演讲。我叫 **Roberto Milev**，是 **Navan** 的首席架构师。我身边的是 **Uday**，他也是我们架构团队的一员。Navan 是一家差旅与费用管理（Travel and Expense Management）公司。今天我们将向大家分享一些我们在运行 AI 以及实际探索过程中的经验与心得。

如果你在这个行业的时间足够长，就会记得随着时间的推移，总会出现几次**范式转移（Paradigm Shifts）**。我们往往都会跟风涌入某个技术潮流并尝试落地，对吧？上一次是大家都蜂拥转向**微服务（Microservices）**。从中诞生了许多优秀的技术成果，比如容器编排、**Kubernetes**，后来我们又有了服务网格（Service Mesh）、熔断器（Circuit Breakers）等一系列好东西。但这并不是一蹴而就的，它经历了漫长的过程，我们花了不少时间才学会如何做好这些事情。

当时有一句名言：“如果你连一个结构良好的单体应用（Monolith）都建不好，为什么还要去尝试构建微服务呢？”这句话在今天同样适用：**如果你连一个单一的 Agent 循环（Single Agentic Loop）都构建不好，为什么还要一头扎进去构建多 Agent 编排系统呢？**

因此，随着时间的推移，就像过去一样，一套**参考架构（Reference Architecture）**正在逐步显现。我们在生产环境中通过实际操作积累了不少经验。我们运行着大量的 Agent，每天消耗海量的 Token。正如我所说，为了在生产环境中可靠地运行 Agentic 流程，已经有几个层级逐步标准化并沉淀了下来：**运行时内存（Runtime Memory）**、**上下文管理（Context Management）**、各类**运维横切关注点（Operational Cross-cutting Concerns）**以及**编排层（Orchestration）**。今天我们将逐一深入探讨所有这些层级，向大家展示当前行业的发展现状、我们的实践做法以及我们所吸取的教训。

<details>
<summary>Original English</summary>

**Roberto Milev**: Right. Hello, everybody. Welcome to our talk. My name is Roberto Milev. I am the chief architect at Navan. And I have Uday here, who's also part of the architecture team. Navan is a travel and expense management company. And we'll share with you some of our learnings around how you run an AI and what have we discovered.

So, if you've been long enough in this industry, you remember that over time there are a few paradigm shifts. And we all tend to jump on a bandwagon and try to kind of do things, all right? Last time was when we all jumped on the microservices bandwagon. And out of that, a lot of good things came out, like container orchestration, Kubernetes. Then we had service mesh, circuit breakers, all of those good things. But it didn't happen overnight. Like it took a long time. It took some time for us to learn how to do these things. So, one of the quotes from there is, "If you can't build a well-structured monolith, why even try to build microservices?" It kind of translates today because if you can't build a single agentic loop, why go in and try to build a multi-agent orchestrated system?

So, over time, just like previously, a reference architecture is emerging. So, we have learned a few things by doing in production. We have a lot of agents, a lot of tokens per day being used. And as I said, there are few layers that have standardized, that have crystallized around what do we need to run agentic flows reliably in production. Runtime memory, context management, all around operational cross-cutting concerns, and around orchestration as well. So, today we'll go over some of these layers, all of these layers actually, and we will show kind of where the industry is, what we have done, what we have learned, and so on.

</details>

### Agent 运行时与内存层架构

**Roberto Milev**: 首先从**运行时层（Runtime Layer）**开始。过去我们讨论过很多关于如何构建无状态服务以便于水平扩展的技术，并为此开发了大量服务。但现在我们进入了一个全新的世界：**Agent 天生是有状态的（Stateful）**。它们需要持久化的会话（Persistent Sessions），需要运行隔离（Isolation），而且其生命周期与传统的 API 服务截然不同。

各大云厂商纷纷入局试图填补这一空白。**AWS**、**GCP**、**Azure** 都推出了各自某种形态的 Agent 运行时。如果大家扫描本页幻灯片及后续幻灯片上的二维码，可以看到关于这些特性的横向对比，以及不同云厂商的实现路径。在 Navan，我们的所有基础设施都运行在 AWS 上。AWS 提供了 **Agent Core** 运行时，我们对其进行了深度使用，但同时也补齐了它的一些不足之处，例如**会话持久化与重新注水（Session Persistence and Rehydration）**就是由我们自行构建的。此外，我们还接入了多种用于编写 Agent 的 SDK。这些运行时的典型特征是通常对框架保持中立（Framework Agnostic），尽管它们在某种程度上都更倾向于自身原生的框架。

技术栈中的下一层是**内存（Memory）**。我们最初是从 **RAG（检索增强生成）** 开始的，RAG 曾经风靡一时，我们采用它是出于必然，因为你不可能把无限量的上下文塞进一个 Agent 里面。随着时间的推移，各大云厂商和整个行业逐渐实现了一套标准化流水线：通过**摄取（Ingestion）**、**提取（Extraction）**、**整合（Consolidation）**和**检索（Retrieval）**的工作流来自动生成内存。

RAG 的某些组成部分已经被内化到了长期记忆机制中，并天生具备一定的语义特性。但内存是在长时间运行中逐步构建起来的，涵盖了从短期的对话记忆（Conversational Memory），到需要自行管理的长期记忆（Long-term Memory），再到记录哪些交互有效、哪些无效的**情节记忆（Episodic Memory）**等等。在 Navan，由于我们全面基于 AWS 技术栈，我们利用了其 Agent Core 的内存能力，但同时也根据自身的业务场景进行了针对性的定制适配。

<details>
<summary>Original English</summary>

**Roberto Milev**: So, starting at the runtime layer, we've talked a lot and we've built a lot of services in order to scale them statelessly before. And now we're in a new world where, you know, agents are stateful by nature. They need to have persistent sessions. They need to have isolation. Their life cycle is different than the life cycle of a traditional API service, and so on. So, the cloud providers have jumped in and try to fill this gap. You know, AWS, GCP, Azure, they all have a some incarnation of a agentic runtime. If you scan the QR code for this slide and for the following slides, you will see a comparison of some of the features and how different cloud providers try to approach this. At Navan, we run everything on AWS. AWS has an agent core runtime. We heavily use that, but we have filled some gaps around that, like the session persistence and rehydration is something that we have built. And we also run a bunch of other bunch of SDKs for writing agents. And part of these runtimes is typically they are framework agnostic, although they all prefer their native framework in a way.

The next layer in the stack is around memory. We started with RAG. RAG was kind of a big thing for a while. We were kind of driven to that out of necessity because you cannot fit an unlimited amount of context into an agent. And over time all of these cloud providers and the industry has implemented a pipeline where memory is kind of automatically generated by following a workflow of ingestion, extraction, and then consolidation and retrieval. And there are parts of RAG that are built in things like a long-term memory that inherently has some semantic characteristics. But memory is built up over time from short-term conversational memory to long-term memory that you kind of manage yourself. Then episodic memories about kind of instances that worked well and didn't work well, and so on. We at Navan, again being a AWS shop, utilize their agent core memory. But we are also kind of doing it in a way that matches our use case.

</details>

### 上下文管理与技能渐进式披露

**Roberto Milev**: 接下来是**上下文管理（Context Management）**。这是一个长盛不衰的热门话题。虽然上下文窗口（Context Windows）变得越来越大，但上下文似乎永远不够用；而如果塞入太多上下文，Agent 又会因为迷失焦点等问题而表现挣扎。

我们发现行之有效的做法是：**将技能（Skills）作为上下文的基本单元**。我来解释一下这是什么意思。我们认为一个技能包含两个部分：一是**上下文**，即针对特定领域或任务的指令与配置；二是**工具执行（Tool Execution）**，也就是具体的 Agent 动作部分。

我们将技能作为可插拔、可独立测试且可复用的工作单元，从中动态组装上下文。举个例子，当我们在构建一个 Agent 时，会准备若干针对特定业务领域的技能，并在此基础上进行组合。我们高度依赖**渐进式披露（Progressive Disclosure）**机制——这是技能本身的固有特性，先从有限范围的上下文开始，后续根据流程进展再通过引入元数据来逐步扩展。接下来我把发言交给 Uday，由他带大家看接下来的内容。

<details>
<summary>Original English</summary>

**Roberto Milev**: And then the next thing is context management. You know, it's a hot topic. It was a hot topic and it's still a hot topic. Context windows are growing bigger, but there's never enough context or if there is too much context again, agents struggle with that cuz you lose focus and so on. What we found working is that focusing on skills as a unit of context. And I'll explain what I mean by that. We look at skills as both having context, meaning instructions and setup about a certain domain or a task. And there's also the the second part of the skill, which is the tool execution and you know, the agentic part. And we compose context dynamically out of skills that we use as units of work that are pluggable, that we can test independently, and that we can reuse. So, for example, when we have an agent, we have skills that are specific to a domain. And based on that, we compose them. And we rely on the progressive disclosure, which is a feature of the skills itself to start with a limited scope of context and then expand by included metadata further down the line. I'll hand it over to Uday now to kind of walk us through the rest of this.

</details>

### 可观测性：从传统日志转向推理链 Tracing

**Uday**: 谢谢 Roberto。大家能不能举手示意一下，现场有谁曾经构建过在长达 20 步或 30 步的多步骤流程中半途失败的 Agent，并且能够迅速定位原因、推断出它为什么失败的？

回顾传统微服务，我们都非常熟悉日志（Logs）。系统里到处打印日志，出问题了我们就去排查日志。但一旦切换到 Agent，一切都变了。Agent 会输出大量的思考过程（Thinking Process），信息量过大以至于无法直接阅读消化。因此，传统的日志排查方式已经不再适用了。过去的模式必须彻底转变。

以 **Claude** 为例，当我们将 Claude 作为 Agent 时，系统提供了 **Hooks（钩子机制）**，我们可以在这一层拦截 Agent 所做的任何动作。例如它调用了什么工具？它正在做出什么决策？无论是在调用工具的前后（Pre-tool / Post-tool），还是在做出决策的前后（Pre-decision / Post-decision），所有这些时间点都可以供我们进行拦截、判定，从而执行阻断操作，或者记录并上报指标（Metrics）。

这是一个非常关键的切入点，让我们能够自动生成链路追踪（Auto Traces）。在 Navan，我们使用第三方供应商来发射这些追踪链路。通过这些 Traces，我们能够清晰看清各个 Span、调用链路以及 Agent 究竟卡在了哪一个时间节点，这极大地增强了我们运维和构建 Agent 的信心。这是日常面临的真实运维挑战。如今市面上有各种各样的 Agent 开发框架，但如何在后续的实际运行中做好运维才是核心关切所在。

此外，我们在 Trace 捕获中作为关键信号上报的内容，涵盖了**推理链（Reasoning Chain）**、思维过程以及几个核心信号：**Agent 当前正在执行的目标是什么**、**其操作背后的理由**、**信念状态（Belief Status）**以及**它正在发起的工具调用**。这些为 Trace 提供了重要的研判依据。当 Agent 做出决策时，还会伴随一个**置信度评分（Confidence Score）**，表明它在做出该判断时的确定程度——比如是否存在多条路径都能推导出该选择，还是说这只是一个推测性的答案（Inferred Answer）。这些信号为我们后续的复盘审查提供了有力支撑。如果属于推测性答案，我们就可以引入 **Human-in-the-loop（人在回路）** 进行引导和微调，让 Agent 表现得更好。

<details>
<summary>Original English</summary>

**Uday**: Thanks, Roberto. All right. Can I have a quick show of hands here who had built an agent which failed halfway through multi 20-step or 30-step process and be able to figure out quickly or reason about why the agent failed. So, again, logs we've generally been traditionally with microservices, we all are familiar with logs. There's logs out there and then we go check out the logs. But this changes everything the moment we switch to agents. Agents output a lot of thinking. There's too much to consume. So, that's not the right way to do it, right? So, traditionally, that was the way, but our thought has to be changed right now.

In the way they Claude as an example, when we take Claude as an example for an agent, there is hooks and we can intercept everything that Claude as an agent does at that level. So, what kind of tool it calls, right? What kind of decision it's making? So, before pre-tool and post-tool call or a pre-decision or a post-decision, so all of that are a point in time for us to intercept and make a decision and either to do a blocking operation or to log in metric or emit a metric, right? So, this is a critical place where we can emit auto traces. At Navan, we use one of our provider to emit these auto traces and through these traces we should be able to figure out the spans, the traces and at what point in time where the agent is stuck, which gives much more confidence into how we operate and build the agent. This is day-to-day operational challenge. Building agent these days there's so many frameworks, but how do you navigate building and operating an agent later is primary concern.

And moreover, the reasoning chain, the thought process and critical signals that we emit here as part of the trace captures, we emit a few primary signals here. What is the current goal the agent is going through, the reasons behind its operations and the belief status and the tool calls that it's making. So, this kind of gives us a judgment pointers in the traces. And when the agent makes a decision, there is a confidence score, how confident it is when it makes the judgment, right? So, whether there are multiple paths that it leads to this choice or whether this is an inferred answer. So, basically these are signals that gives us confidence later to review. If this is an inferred answer, there could be a human in the loop to guide through and tweak the agent to perform a little better.

</details>

### 非确定性系统评测：轨迹评估

**Uday**: 我想再请大家举一次手：有谁对自家 Agent 的测试流水线拥有 100% 的信心？

这也是当下的另一个关键痛点。因为 **Agent 具有非确定性（Non-deterministic）**。过去我们都习惯了编写完全确定性的流程，我们清楚其运行机制。如果去问一个工程师，工程师可以把算法原理、操作时序讲得一清二楚，一切都在脑海中有既定的代码逻辑和明确预期。但现在 Agent 以非确定性的方式运行，我们该如何进行测试？这极其关键。

坦白说，我们也一直在艰难摸索。在最初构建 Agent 时，日常运维挑战重重，在很多步骤上都遭遇过失败。该如何纠偏？往往是改动了一处，其他地方又崩了。我们该怎么做？

我们采取的一种方案来自于学术界关于多步编排的研究论文：当一个 Agent 需要执行 30 个步骤或决策来达成目标时，如果那是固定程序，那是另一回事；但这并非预设程序，它以非确定性的方式在每次运行时自行规划不同的步骤。那么，我们能否在此绘制出一张确定性的图谱？不可能。但我们可以绘制出它从起点通往目标的**轨迹（Trajectory）**，进而计算它在轨迹中前进了多远、从源头到目的地的偏移程度，以此来**评估 Agent 的效率与任务完成度**。因此，我们高度依赖**轨迹评估（Trajectory Evals）**。此外还有其他一些信号，正如我上一张幻灯片提到的推测信号，如果答案来自推测，我们如何将其纳入闭环、形成信号来判定这是否属于回归（Regression），从而对 Agent 进行修复。

<details>
<summary>Original English</summary>

**Uday**: Again, can I have a raise of hands again to see how confident are you like 100% confident in testing pipelines with your agents? Right. So, this is one of the other critical aspect today. Because agents are non-deterministic. We've all been used to program and write much more deterministic flows. And we know how it works. Engineer can come and tell me how the algorithm, the sequence of operations. Everything is programmed in our mind. Everything is expectations. But now the agents come into a non-deterministic way. And how do we test them, right? So, that is very criticality here. And yeah. We are also struggling. We've started building agents, the day to operations was challenging and then we failed in a lot of steps. How do we course correct? The moment we change something, something else breaks, right? So, how do we do that?

One approach that we took, this is from research papers around in a multi-step orchestration, when an agent makes 30 steps or decisions to make to reach to a goal, if that is a program, that's a different story. But this is not a program. This is non-deterministic way of it makes up its own steps every time differently. So, how can we chart a deterministic graph here? Is it possible? No. Can we have a trajectory of its starting from an end to a goal and then see how far it went in the trajectory and how far it went from the source to the destination is what we can compute to evaluate the efficiency or the completeness of the agent evaluation. So, we heavily rely on trajectory evals. And there are few other signals as I briefly spoke around in the previous slide around the inferred signal. If the answer is from an inferred answer, how can we loop that into and make a signals around how can we classify that this is a regression and make fixes towards the agent?

</details>

### 安全护栏与委托授权治理

**Uday**: 接下来是**安全护栏（Guardrails）与授权机制**，这在企业级 AI 中扮演着至关重要的角色。海量的信息正被输送给大模型，其中很可能在不知不觉中混入了敏感信息。作为技术管理者，我们如何建立起这套治理层来加以防范，显得尤为关键。

与此同时，**身份认证（Authentication）与权限控制（Authorization）**的概念正在发生根本性的变化。传统上，我们面对的主体要么是真实用户，要么是服务账号（Service Account）。但现在 Agent 到底算什么？Agent 可以**代表用户（On Behalf of Users）**采取行动。这涉及到海量的业务场景，例如：“只要机票价格低于 200 美元，就帮我订票。”我们给出这样一句指令，Agent 就会自行研究并在后台代表我执行购买操作。那么这笔交易究竟是我买的，还是 Agent 代表我买的？Agent 既能代表用户行动，也可以使用服务账号。两者的界限变得模糊，这就要求我们必须做出**细粒度的授权决策（Fine-grained Authorization Decisions）**。这正是安全护栏与认证授权策略层大显身手的地方。在 Navan 的实践中，在每一次工具调用的前置和后置阶段（Pre-tool / Post-tool），我们都部署了这套安全护栏来进行检查、拦截并做出明智决策。

<details>
<summary>Original English</summary>

**Uday**: So, the next is the guardrails. Guardrails and authorization, this plays a critical role in enterprise AI. A lot of information is being piped to models. There could be sensitive information that goes into it without our knowledge. And we as leaders, how can we put in this governance layer to stop this is very critical here.

And the concept of authentication and authorization is taking up a different approach here. Traditionally, we've seen a user or a service account, but now what is an agent? Agent can be acting as on behalf of users. There is so much of use cases there. "Hey, book me a flight whenever it's cheaper than $200", right? So, we just tell this assertion and then agent go figures out and does this action on behalf of me. So, is it me making this purchase or is it agent making on behalf of me? So, agent acts on behalf of user or agent uses a service account as well. So, the line is being blurred here and we need to make fine-grained authorization decisions here, and the policy layer that's where the guardrails and authentication authorization plays a critical role. And in Navan what we employ here is before every tool call, pre-tool and post-tool, we have this guardrails to check and block and make a informed decisions.

</details>

### 编排选型：单 Agent 技能挂载与 A2A 协议

**Uday**: 还有关于**单 Agent 与多 Agent 之争（Single Agent vs. Multi-Agent）**，你可以把它看作一场编排架构之争——到底该构建单 Agent 还是多 Agent？正如 Roberto 此前简要指出的，如果你连单个 Agent 都无法做到尽善尽美，为什么要去盲目追求多 Agent 呢？我们应当吸取失败教训和实践经验，循序渐进地构建。

在 Navan，我们采取的方案是：**单一主控 Agent（Single Master），并在其内部采用子技能（Sub-skills）机制**。虽然内部有子 Agent 的概念，但整体表现为一个单一的 Agent，能够**渐进式加载各项技能**，精准判断需要将哪些内容载入上下文，从而在具体的业务场景中完成推理与导航。

不过，业界也正在涌现出其他架构模式，对应着不同类别的业务场景。其中之一就是 **Agent 间通信（Agent-to-Agent Communication，A2A）**。在一个大型企业组织内部，往往存在许多团队边界，团队之间可能缺乏直接沟通。此时两侧各有一个 Agent，它们该如何协作？我们可以借助 **A2A 协议**在技能层面建立契约（Contracts），将 A2A 协议作为跨团队边界的标准通信手段。好的，接下来交回给 Roberto。

<details>
<summary>Original English</summary>

**Uday**: And this single agent versus multi-agent, again, this is kind of a orchestration wars you can think of whether to build a single agent or a multi-agent. Again, as Roberto briefly hinted, if you can't perfect and build a single agent, why go towards multi-agent, right? So, learn from our failures, experiences, and build towards that.

At Navan, the approach that we have taken is single master, and then we adopted sub-skills. There are sub-agents within it. So, it's a single agent that can progressively load the skills and understand decisively what needs to be loaded into the context, and then make this navigation through the use case.

But there are other patterns that are also emerging. There are different class of use cases here. One is agent-to-agent communication. If you take a large scale organization, and there are so many of these teams that are that are acting as the boundaries, and they don't talk to each other, let's say. How do we communicate? There are two agents on either of the side, right? How do we do it? So, there is A2A protocol which can help us establish the contracts in terms of skills. And we can use A2A as a protocol there, which kind of is a boundary between the teams. Yeah, over to you, Roberto.

</details>

### 技术栈成熟度总结与未来挑战

**Roberto Milev**: 好的。当我们梳理完整套技术栈后，很明显会发现：**技术栈中的某些组件已经进入了较为成熟的阶段，我们已经拥有了良好的应对方案**。

正如 Uday 所说，**运行时（Runtime）层面基本已经得到解决**。我们在编排以及运行大语言模型方面已经非常成熟，甚至可以用相对大力出奇迹的方式来运行，因此水平扩展并不是难题。

**内存（Memory）**方面，随着前沿基座大模型能力的不断增强以及工程实践的积累，我们能够覆盖绝大多数业务场景，而且主流云厂商也提供了相当成熟的支持。

**MCP（Model Context Protocol）** 已经成为事实上的标准协议，工具调用（Tool Calling）如今已成为各大模型普遍支持的基础能力。我们正看到整个行业在此方向上的收敛，MCP 规范本身也在持续演进并走向无状态化。我们已经达到了一个能够清晰掌握如何让 Agent 调用外部服务与工具的技术阶段。

然而在另一些领域，虽然有所进展，但仍存在大量未解之谜：
1. **可观测性（Observability）**：业界目前正大力推行 **OpenTelemetry（OTEL）**，但 OTEL 是否真的完美契合 Agent 的调用链路？正如 Uday 所说，通过定制改造确实可以跑通，但依然面临诸多挑战。
2. **测试模式（Testing Patterns）**：Agent 系统的测试极为困难，但我们已经摸索出方法，即便在 Agentic 系统本身存在非确定性的前提下，也能为客户提供高质量的稳定体验，这套方法论正在逐步完善。
3. **编排模式（Orchestration）**：我们拥有各种模式，既可以构建大体量 Agent，也可以构建小体量 Agent。但正如前文所言，正确的原则大概是**切忌过度设计（Not Over-engineer）**。我们正在实践中摸索，一套主流的设计思潮也正在逐步形成。
4. **成本控制与可预测性（Cost Management）**：这是大家都深感头痛的难题。刚才的演讲从辅助开发工具的角度探讨了这个问题，但在生产环境的 Agent 中我们也同样面临这些挑战：**成本极难预测，也极难进行精细化管理和设置安全红线**。如何设计可靠的降级策略（Fallback），或者针对特定子任务路由到更轻量、更便宜的模型？当前大模型厂商的商业利益诉求显然是希望大家消耗更多的 Token。
5. **重放与调试（Replay and Debugging）**：正如 Uday 所提到的，这同样是一个巨大的痛点。排查 Agent 的决策逻辑非常晦涩，但我相信这最终也能得到解决，因为我们现在甚至可以利用 Agent 自身来分担和消化调试分析时的认知过载。
6. **行业标准（Standards）**：开源社区正在推动各种标准的建立。正如提到的 OTEL，以及目前还很早期、由特定厂商主推的 **Agent-to-Agent（A2A）** 协议。我相信随着时间的推移，我们终将达成成熟的标准。

总而言之，我们已经清楚地知道自己需要什么，接下来就看我们如何亲手将其设计并实现出来。谢谢大家！

<details>
<summary>Original English</summary>

**Roberto Milev**: All right. So, as we went through the stack, it's obvious that some components of the stack are in a more mature state and we already have good answers for them. As Uday said, the runtime, I think it's pretty much solved. We are so advanced in orchestration and we are running LLMs in kind of a very brute-force way. So, scaling is not a problem.

Also, memory, I think as the frontier LLMs get better and as our practices get better, we will find a way to cover the majority of the use cases and there is good maturity around the cloud providers.

MCP has emerged as the de facto protocol and tool calling is now a feature that everybody supports. So, we are seeing some industry convergence around that as well and MCP as a standard is also evolving. Now, it's becoming stateless. We are reaching a point where kind of we know how to invoke services and tools with agents.

In some areas, things are happening, but you know, there's still a lot of unknown. Around observability, there is a push towards OTEL, but does OTEL really work for agentic calls? Yeah, you can make it work as Uday was saying. Also, we are getting more comfortable around the testing patterns. It's very hard to test, but we have found a way to give customers quality experiences even with the unreliability of agentic system and I think that's kind of getting in a state that is better defined.

Orchestration is another one where, you know, we have patterns, we can build bigger agents, smaller agents. As we said previously, probably the right answer is to not over-engineer. So we're learning there and a pattern of school thought is also emerging.

Where we're all struggling with and the previous talk was about this for the developer, AI assistant development perspective, but also we're seeing these issues from our production agents. It's very hard to predict cost and it's very hard to manage cost, and put guardrails and solve this in a way where there is reliable, maybe fallback or have agents be using cheaper models for certain tasks. This is all driven by kind of the big AI vendors who, I think, their interest is for us all to spend more tokens.

Replay and debugging, Woody talked about that, that's also a big big issue. It's very hard to understand, but I think this is also something that is going to be solved because we can now use agents to get over the cognitive overload of trying to debug what they do.

And then standards, standards are emerging by, you know, the community. OTEL, as I mentioned, agent to agent is young, it's kind of pushed by certain vendors, but I think over time we will get there. With all of this said, you know, we know what we need and it's up to us to write and build it. Thank you, everybody.

</details>