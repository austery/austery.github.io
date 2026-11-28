---
author: AI Engineer
date: '2026-10-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rAUyRDOFyHU
speaker: AI Engineer
tags:
  - agentic-workflow
  - deterministic-execution
  - enterprise-governance
  - runtime-isolation
  - structured-output
title: 工作流而非自动驾驶：Flywire 的企业级智能体架构实践
summary: Flywire 工程师分享了其内部 AI 平台 Orbit 的架构与落地经验。在强监管的跨国支付业务背景下，团队放弃开放式全自动黑盒，采用确定性代码与大模型推理结合的 YAML 工作流机制，依托 AWS Fargate/MicroVM 实现环境隔离与安全治理，并结合结构化输出、独立评估与人机协同，支撑起月均过万次的高成功率自动化工程交付。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Flywire
  - AWS
products_models:
  - Orbit
  - Claude Code
  - Victoria
media_books: []
status: evergreen
---
### 序言与金融合规背景

**Eduardo**: 大家好，欢迎各位！我是 Eduardo，坐在我旁边的是 Javier，我们代表的是 Flywire 的 AI 平台体验团队（AI Platform Experience Team）。我们团队的核心使命是构建实用的智能体基础设施（practical agentic infrastructure），在赋能自主软件工程师的同时，严格遵守既定的工程规范与研发实践标准。今天，我们将向大家分享结构化工作流自动化（structured workflow automation）是如何为企业带来切实价值的，并展示我们如何在整个软件开发全生命周期中确保系统控制力、安全边界与运行可靠性。在深入探讨 AI 平台的技术细节之前，先为大家介绍一下 Flywire 的核心业务背景。

<details>
<summary>Original English</summary>

**Eduardo**: Hello, everyone, and welcome. My name is Eduardo, and Javier here will represent the AI Platform Experience Team at Flywire. Our core mission is to build practical agentic infrastructure that empowers our sovereign engineers, while following our established engineering standards and practices. Today, we'll share how structured workflow automations deliver real enterprise value, ensuring control, safety, and reliability across our development process. Before we dive into the deep technical details of our AI platform, let us give you some essential context about Flywire.

</details>

**Eduardo**: Flywire 旨在处理全球各行业最为复杂的支付结算业务，客户覆盖教育、医疗、跨境商贸及专业商业服务等多个领域。目前，我们服务于全球超过 204 个国家和地区的 5000 多家客户。由于平台每日需要处理大容量的跨国支付交易，因此**监管合规**、数据隐私以及系统安全性从来不是可有可无的附加项，而是支撑我们业务运转的生命线和核心前提。

<details>
<summary>Original English</summary>

**Eduardo**: Flywire is built to process the world's most complex payments across global industries like education, healthcare, commerce, and business services. Today, we serve over 5,000 clients across more than 204 countries around the world. Because we process high-volume international transactions, regulatory compliance, privacy, and security are not optional items. They are core requirements of our business.

</details>

**Eduardo**: 我们在非常严苛的合规标准下运行，包括 **PCI DSS**（支付卡行业数据安全标准）以及 **SOC 2** 认证要求。这意味着客户数据、个人身份标识信息（PII）以及具体的支付敏感细节必须受到全方位的安全保护。在没有建立严格的数据治理框架与清晰架构边界的情况下，我们绝不能简单地把敏感上下文直接输送给任何第三方服务商。

<details>
<summary>Original English</summary>

**Eduardo**: We operate under strict compliance frameworks like PCI DSS and SOC 2. This means that customer data, personal identification, and payment details must remain completely safe. We cannot simply take sensitive context and pass it to third-party services without strict governance and architectural boundaries.

</details>

**Eduardo**: 为了让大家了解我们的研发组织概貌：我们拥有分布在全球各个团队的数百名工程师。我们维护着非常多元的技术栈，包括 Java、Ruby、Go、Python、.NET 以及 PHP 等语言体系。我们构建和运行的几乎所有业务服务，都统一部署在名为 **Victoria** 的内部 PaaS 平台上。Victoria 基于 GitLab 与 AWS 基础设施构建，提供标准化的构建流水线以及全局一致的部署交付实践。

<details>
<summary>Original English</summary>

**Eduardo**: To give you an idea of our engineering organization: we have around hundreds of engineers distributed globally across our teams. We maintain diverse technology stacks, including Java, Ruby, Go, Python, .NET, and PHP. Almost everything we build and run is deployed on Victoria, our internal Platform-as-a-Service that operates on top of GitLab and AWS infrastructure. Victoria provides standardized build pipelines and consistent deployment practices.

</details>

**Eduardo**: 那么，我们的企业级 AI 探索之旅是如何启程的呢？大约在六个月前的四月份，我们正式组建了专属的 AI 平台体验团队。而在此之前，整个 Flywire 内部就有很多满怀热情的工程师在自发尝试各种 AI 工具：自己编写自定义技能（Skills）、搭建模型上下文协议服务（**MCP Server**），甚至协同搭建出了早期的代码审查机器人原型。这种自下而上的自发创新证明了我们的工程师极度渴望 AI 自动化；但同时也清晰地表明，我们需要一支专属的平台团队，来提供坚实底层基础设施，确保智能体方案安全、受控且具备企业级可靠性。

<details>
<summary>Original English</summary>

**Eduardo**: So how did our AI journey begin? About six months ago, back in April, we formally established a dedicated AI Platform Experience Team. Even before that, passionate engineers across Flywire were already experimenting with AI tools, creating skills, building MCP servers, and assembling an early code review bot. That organic activity proved that our engineers wanted AI automation. It also showed that we needed a dedicated team to provide infrastructure for safe and reliable agentic solutions.

</details>

**Eduardo**: 自团队成立以来，我们保持了极高的迭代节奏，向内部工具提交了近千次代码 Commit。然而外部的 AI 工业界在同样过去的六个月里更是一刻不停：仅 **Claude Code** 一款工具就发布了超过 160 个版本，几乎达到每天更新一次的频率；各大 AI 实验室累计发布了二十多个全新基础模型。每周都会诞生新的模型架构、新的开发工具或崭新的工程范式。摆在我们面前的挑战，不仅在于自身能否跑得够快，更在于如何紧跟时代且在企业内稳健落地。

<details>
<summary>Original English</summary>

**Eduardo**: Since then, we have moved fast with close to a thousand commits to our internal tool. But the industry does not stop. In the same six months, Claude Code alone published more than 160 releases, almost one per day, and the major AI labs released more than twenty new models. Every week brings a new model, a new tool, or a new way of working. Our challenge is not only to build fast, but to keep up.

</details>

---

### Orbit 架构哲学：工作流而非自动驾驶

**Javier**: 这就引出了我们的内部核心平台——**Orbit**。Orbit 作为一个内部平台，致力于消除日常工程协作中的重复死循环。其核心设计哲学在于：将大语言模型严密嵌入到结构化工作流（Structured Workflows）之中，而不是任由自主 AI 智能体去漫无边际地自由发散与执行。我们将大部分程序逻辑固化为**确定性代码**（deterministic code），仅仅在确实需要高阶理解与推理能力的关键环节才去调用大语言模型。在评估选择自研还是采购市面方案时，自研内部平台对我们所处的严苛环境而言具有绝对的合理性。现成的前沿模型能力大幅加快了功能研发速度，从根本上降低了自建定制化平台的开发成本。

<details>
<summary>Original English</summary>

**Javier**: This brings us to Orbit. Orbit is an internal platform that eliminates daily engineering repetition loops by including LLMs strictly into a structured workflow. Instead of letting AI agents freely open-end, our approach wraps procedural logic into deterministic code, and we call the LLM only where reasoning is actually needed. When we evaluated whether to build or buy, building in-house made complete sense for our environment. Frontier models made feature development really fast, which drastically lowers the cost of a custom platform.

</details>

**Javier**: 更关键的是，作为一家需要处理 PCI、PAI 以及各类敏感个人健康与财务信息的金融科技企业，将所有智能体执行环节完整封闭在我们现有的 Victoria 基础设施之内，能够从根本上保证敏感业务数据绝不脱离我们的受控内网环境。这使我们免去了漫长复杂的第三方供应商安全审查，也省去了繁琐的多余合规认证流程。

<details>
<summary>Original English</summary>

**Javier**: More importantly, as a financial enterprise handling PCI, PII, and PHI data, keeping execution inside our existing Victoria infrastructure ensures that sensitive data never leaves our controlled environment. We also skip long vendor security reviews and extra compliance work.

</details>

**Javier**: 那么，一个具体的 Orbit 工作流实际上长什么样呢？在 Orbit 中，每一个智能体工作流都完整定义在一个独立的 **YAML** 文件里。该文件保存在代码仓库中，与任何其他常规业务代码一样，必须严格走相同的合并请求（Merge Request）代码审查流程。以我们的**自动化代码审查智能体**为例，它的整体流转是这样的：首先由一个 Webhook 触发器发起——比如当研发人员在某个 GitLab MR 评论中主动提及 `@review-bot` 时触发。

<details>
<summary>Original English</summary>

**Javier**: So what does a workflow actually look like? Every agent in Orbit is defined in a single YAML file that lives in a repository that goes through the same Merge Request review as any other code. Take our code review agent as an example. It starts with a trigger, like a webhook that fires when an engineer mentions that review bot on a Merge Request.

</details>

**Javier**: 接下来，系统会启动一系列确定性的前置步骤（deterministic activities）：抓取该 Merge Request 的元数据，对其进行风险分级（risk tier classification），加载该工程既往的审查记录与规则，然后完整拉取代码仓库上下文。随后，流程进入大语言模型调用步骤：此环节模型被授予代码只读权限，严禁对文件进行修改，并且模型返回的分析结果必须严格遵从我们定义的强类型 JSON Schema 输出格式。最后，由另一个确定性的系统步骤将整理好的审查建议回写并发布到 Merge Request 评论中。

<details>
<summary>Original English</summary>

**Javier**: From there, a sequence of deterministic activities fetches the Merge Request metadata, classifies its risk tier, loads prior findings, and clones the repository. Finally, we call the model in an LLM step that can read code, but has no permission to modify, and that must answer under a strict output schema. Finally, another deterministic step posts the findings back to the Merge Request.

</details>

**Javier**: 这就是我们所强调的“**工作流而非自动驾驶**”（workflows, not autopilot）。确定性代码牢固掌控所有可预测的逻辑分支与环境操作，而昂贵的大模型则仅在真正需要推理分析的缝隙处被精准唤起。

<details>
<summary>Original English</summary>

**Javier**: This is what we mean by workflows, not autopilot: code handles the predictable parts, and the model is called only where reasoning is actually needed.

</details>

---

### 配置、触发机制与高频落地场景

**Javier**: 我们之所以特意选择 YAML 文件作为配置载体，并绑定 MR 审查机制，是有深思熟虑的考量的。首先，YAML 是每一位工程师日常极其熟悉的文件格式，而且 MR 审查流完美契合了开发团队现有的每日工作节奏。其次，这种方式让代码库对 AI 更加友好（AI-friendly）：编程智能体同样可以像人类一样自如地阅读、修改和评审工作流的 YAML 定义。然而，并非所有的业务场景都来自于工程产研团队。针对非技术类协同场景，我们目前正在规划 Orbit UI 的可视化编排画布，让业务人员可以通过拖拽预制活动节点（predefined activities）的方式组装工作流，完全无需手写 YAML 文本。

<details>
<summary>Original English</summary>

**Javier**: We chose to start with YAML files and an MR request review process on purpose. YAML is a format our engineers already know, and the review works the way they already work every day. It also keeps the codebase AI-friendly: coding agents can read, write, and review workflow definitions as easily as people can. However, not every use case comes from an engineering team. For corporate use cases, we are considering an authoring tool in the Orbit UI, where people can build a workflow by dragging and dropping from a set of predefined activities without writing any YAML.

</details>

**Javier**: 在 Orbit 中，工作流的触发支持三种标准化路径。第一种是由工程师或者上游系统直接调用 Orbit 内部 API，或者是通过我们的内部命令行工具（CLI）发起调用；第二种是依托事件驱动 Webhook，监听来自 GitLab、Jira、Sentry 或 AWS 的状态变动事件，在特定系统事件发生的第一瞬间实时启动工作流，例如研发发起 MR 或线上出现新的生产告警；第三种是计划定时任务（scheduled jobs），按照固定的时间节拍运行常规运维流程，比如我们每日的国际化多语言翻译同步、Feature Flag 清理规范检查以及内部知识库刷新。

<details>
<summary>Original English</summary>

**Javier**: A workflow can start in three ways. Engineers or another system can call Orbit's internal API directly, or use our internal CLI. Webhooks from GitLab, Jira, Sentry, and AWS start that workflow from the moment something happens, such as a Merge Request or a new production error. Scheduled jobs run workflows on a fixed cadence, like our daily translation syncs, feature flag cleanups, and knowledge base refreshes.

</details>

**Javier**: 除了上述常规入口外，我们目前正在紧锣密鼓地为 Orbit 打造专属的 **MCP Server**，以便部署在 Flywire 各个角落的其他 AI 服务能够通过声明式协议动态触发对应工作流。举例来说，后续工程师在 Slack 交流时，只需呼叫 `@claudecode` 即可无缝调起 Orbit 内部工作流完成特定分析与变更，全程不需要切换工作窗口。

<details>
<summary>Original English</summary>

**Javier**: Beyond these entrypoints, we are currently building an MCP server for Orbit so that other AI services and tools we use at Flywire can start workflows dynamically. For example, an engineer will be able to ask Claude in Slack through Claude Code to run an Orbit workflow without ever leaving their conversation.

</details>

**Javier**: 在落地路径上，我们坚持小步快跑，优先攻克影响大、高频次的确定性业务场景：
1. **日常研发协同**：针对 Victoria 平台升级的自动化 MR 审查机器人，自动识别 Victoria 版本契约并给出审查见解；
2. **多语言全球化翻译**：单一条工作流完整串联整个长周期链路——自动抓取新提交的文本词条、利用大模型批量翻译、更新本地语言包文件，并向对应项目组发送翻译变更通报；
3. **线上生产故障自愈**：接入 Sentry Webhook 触发故障排查智能体，它会第一时间研判错误日志链路、在 Slack 对应告警频道发布排查诊断分析，并附带附上修复代码的 MR 链接；
4. **技术支持与派单**：Ticket 分类智能体自动研判用户提交的技术工单，精准路由分派至对应的研发小组；
5. **AI 友好度雷达**：AI Readiness 评分卡量化评估代码库对 AI 辅助研发的就绪程度，并由修复智能体根据发现的规范问题自动修正；
6. **通用需求自动实现**：Jira Implementer 智能体直接读取 Jira 需求工单，解析细节并自动编写代码转化为可运行的 MR。它运作起来就像一座微型软件制造工坊。

<details>
<summary>Original English</summary>

**Javier**: We started small with clear, high-impact use cases. First, daily engineering work: automated reviews of Merge Requests on our Victoria upgrades agent, which verifies Victoria compliance in the findings. Second, translations: one workflow now handles the full cycle—it fetches new strings, translates them, updates the files, and notifies the teams with updated docs. Third, production errors: a Sentry webhook starts the Sentry investigator; it assesses the issue, posts the assessment in Slack, and shares a Merge Request with a fix in the same place. On the support side, ticket triaging classifies new tickets and routes them to the right engineering area. AI readiness scorecards measure how ready a repository is for AI-assisted development, and a fixer acts on the findings. Finally, the Jira Implementer takes a ticket and turns it into a Merge Request. It works like a small software factory.

</details>

**Javier**: 经过实践，我们发现该体系带来的最大收益之一，是能够安全地进行**跨海量仓库的大规模批量工程治理**（software engineering at scale）。这使得我们在执行底层核心依赖库升级、框架迁移和废弃接口治理时变得极其从容高效。我们还利用它来批量运行 Code Doctor 体检工具，并部署自动化 AI 就绪协作者。值得强调的是，在所有这些高强度自动化中，**合并请求（MR）始终是我们不变的最小工作单元**，也是人类保留在控制回路中（Human-in-the-Loop）的关键关卡。鉴于我们处于严苛的金融监管体系之下，最终的变更合并必须经由研发工程师进行审查与明确批准。

<details>
<summary>Original English</summary>

**Javier**: One of the biggest benefits that we found is that we can make changes in bulk across many repositories, which lets us do software engineering at scale. It is very convenient for migrations, library updates, and deprecations, and we also use it to run Code Doctor and to launch our own AI readiness coworkers. Even with all this automation, the Merge Request is still our unit of work, and it is where a human stays in the loop. We operate in a regulated environment, so people still review and approve those Merge Requests.

</details>

---

### 技术架构深潜：隔离、运行时与护栏机制

**Eduardo**: 接下来，让我们深入剖析一下 Orbit 的底层技术架构演进。最初，我们采用的是一套极简的容器化部署架构，基于 **AWS ECS Fargate** 构建。在早期版本中，工作流的编排协调层（orchestration layer）、智能体执行环境与任务运行时完全打包存活在同一个容器内部。

<details>
<summary>Original English</summary>

**Eduardo**: Let's take a deeper look at the technical architecture of Orbit. Originally, we began with a simple container setup on AWS ECS Fargate, where the orchestration layer, harness, and the runtime environment lived inside the same container.

</details>

**Eduardo**: 随着应用场景的爆发式扩展，我们将系统重构分拆为三个完全独立的组件：**流程编排层**（orchestration layer）、**智能体运行时环境**（agent runtime environment）以及**会话状态持久化层**（session state）。这一解耦带来了更高的安全隔离性、可维护性与计算资源利用率。系统的整体韧性也得到了质的提升——当智能体内部执行发生崩溃报错时，编排主进程完全不受影响；而且我们能够根据负载特征独立弹性伸缩各个层级，灵活适配快速迭代的需求。

<details>
<summary>Original English</summary>

**Eduardo**: As our needs grew, we evolved toward separating the orchestration layer, the agent runtime environment, and the session state into distinct components. This improves isolation, maintainability, and resource allocation. It also makes the system more resilient because an error in the agent does not kill the sandbox, and it lets us scale each piece independently and adapt to changing requirements.

</details>

**Eduardo**: 基于 AWS Fargate 的无服务器机制，我们能够高度弹性地调度底层容器任务，支撑海量智能体同时并发运转。此外，部署 Orbit 也极其顺畅，因为 Victoria PaaS 原生具备成熟的应用平滑扩缩容能力。然而，高并发与大规模调用若缺乏控制则极其危险，我们必须为平台建立坚固的安全护栏（guardrails）：
1. **执行超时熔断机制（Timeouts）**：每一个智能体容器都有可配置的最大执行时间窗口，超时即强制退出，防止陷入无限死循环；
2. **激进的调用频次限制（Rate Limits）**：在系统默认层面对 API 调用实施严格的限流策略。一旦某个第三方集成出现异常 Bug，容易在瞬间衍生出成千上万个并发调用，引发不可控的天价账单，限流机制确保成本与调用压力始终收敛在安全区间；
3. **并发排重锁（Concurrency Control）**：控制平面内置分布式互斥锁（Locks），坚决防止同一个业务触发事件被多次消费或重复拉起相同的执行任务。

<details>
<summary>Original English</summary>

**Eduardo**: Fargate lets us scale tasks elastically, so we can run a very large number of agents in parallel. It was also really easy to deploy Orbit because we already have Victoria, our PaaS that scales applications without any effort. But that scale needs guardrails so the platform is not abused. First, timeouts: every agent stops after a configurable amount of time. Second, rate limits, which are aggressive by default: a broken API integration could start spawning thousands of agents and make our bill much bigger; rate limits keep that under control. Third, concurrency control: the control plane uses locks to prevent duplicated executions of the same task. For example, our control plane uses locks to prevent duplicate requests from running agents twice.

</details>

**Eduardo**: 在容器沙箱配置上，Victoria 平台天然集成了容器规格边界限制。Victoria 使用标准的 Fargate Task 定义，因此这些轻量级容器受到了极高强度的权限收口与资源限制。我们的智能体基础容器镜像内置了常见的通用编程语言运行时，但**有意移除了 Bundler、Maven、Composer 等包管理工具**。这样做是为了确保像 Jira Implementer 这样功能复杂的重型智能体，无法在基础容器内肆意执行未受管制的本地编译构建或单元测试。

<details>
<summary>Original English</summary>

**Eduardo**: Victoria comes with container limits. Victoria uses standard Fargate task definitions, so the containers are lightweight and entirely restricted. Our baseline agent container includes common language runtimes, but it intentionally leaves out package managers like Bundler, Maven, and Composer. So heavy agents like our Jira Implementer cannot easily run native builds or unit tests inside the container.

</details>

**Eduardo**: 当我们在今年四月份启动 Orbit 项目时，AWS Lambda MicroVM（微虚机）环境尚未发布（AWS 直到六月份才正式推出）。因此我们的首个版本纯粹运行在 Fargate 之上。而这类新兴的托管型微虚拟机的工作方式非常类似于无服务器 Lambda，但具备进程暂停（Pause）与原地断点恢复（Resume）的原生特性。这种即用即走的按需伸缩与上下文恢复机制，天然契合智能体长链路任务的执行特点。因此，我们现在正针对不同项目技术栈采用这类专属运行时环境，让每套技术栈都能在独立的微沙箱中毫秒级拉起。

<details>
<summary>Original English</summary>

**Eduardo**: When we started Orbit in April, AWS managed microVMs did not exist yet; AWS released them in June. So our first version ran only on Fargate. These managed microVMs work like Lambda functions with resumable processes, so they can pause and continue where they stopped. That fits the nature of agentic execution really well, so we now use them with a runtime chosen by project type. Each tech stack gets its own container quickly in an isolated environment.

</details>

**Eduardo**: 当然，这距离绝对完善的容器安全沙箱仍有距离，团队正全力向深层隔离演进。我们的远期目标是提供类似 Docker-in-Docker 或多层 MicroVM 架构，让智能体在安全的隔离空间内，可以针对任何代码仓库全自动化地运行自动化测试、启动集成环境和执行端到端构建验证。

<details>
<summary>Original English</summary>

**Eduardo**: These are not full sandboxing yet, and we are actively moving there. The goal is to support setups like Docker-in-Docker or multiple microVMs, so agents can run tests or more complex verifications on any repository inside.

</details>

---

### SDK 复用、权限控制与中央技能市场

**Eduardo**: 在大模型底座交互与执行套件（harness）方面，我们并没有从零重复造轮子。相反，我们直接复用了 **Claude Agent SDK**——这与驱动 Claude Code 的是完全同一套成熟的执行套件底座。这让我们开箱即用地获得了经过充分实战检验的工具调用规范、子智能体协作（sub-agents）调度以及技能注入机制，从而能够将精力完全聚焦于企业工作流本身的编排，而非耗费在底层框架与通信管道的打磨上。

<details>
<summary>Original English</summary>

**Eduardo**: For each LLM step, we did not build our own harness. Instead, we reused the Claude Agent SDK, the same harness that powers Claude Code. This gives us a much more well-tested harness with tool usage, sub-agents, and skills out of the box, so we can focus on the workflow rather than the plumbing.

</details>

**Eduardo**: 我们在此基础之上叠加的核心能力是**精细化治理控制**。针对工作流中的每一个步骤，我们都设置了细粒度的权限边界：
- 智能体允许访问的出口网络白名单；
- 允许调用的具体工具集合；
- 允许动态加载的 Skill 技能集；
- 允许连接的 MCP 服务，甚至精确限定到该服务暴露的特定只读接口。

所有上述边界规则，全部透明地声明在工作流自身的 YAML 文件中。例如，一个代码检索排查步骤可以读取和搜索代码，但绝对没有写文件或 Push 代码的分支权限；我们的 Sentry 故障分析智能体虽然能够通过 MCP 协议拉取链路追踪（trace），但权限被严格限制在精选的几个只读工具接口上。实际生产中，每一个步骤都遵循最小权限原则（PoLP），配置对全员透明可见，并与普通代码一样接受 PR 审计。

<details>
<summary>Original English</summary>

**Eduardo**: What we add on top is control. We restrict different things for every step: the network the agent can access, the tools it can call, the skills it can load, and the MCP servers it can use, down to the specific tools allowed from each server. All of this is declared in the YAML file itself. A search step, for example, can read and search the code, but cannot edit files or push changes. And our Sentry investigator can query traces through our MCP server, but only with a short list of read-only tools. In practice, each LLM step runs with only the access it needs, fully visible and reviewable like any other code.

</details>

**Eduardo**: 在技能（Skills）的组织上，Flywire 建立了统一的中心化管理机制。我们维护着一个技能中央仓库，并在内网公开发布为专属的 Claude 插件市场（plugin marketplace），Orbit 在系统镜像构建时会自动同步接入该市场。这意味着同一套能力沉淀可以在两端无缝共享：开发者既可以在自己本地电脑的 Claude Code 终端中直接调用该 Skill，Orbit 也能够在服务端的自动化云端工作流中无缝装载它。

<details>
<summary>Original English</summary>

**Eduardo**: Skills themselves come from a single place at Flywire. We maintain a central repository of skills that is published internally as a Claude plugin marketplace, and Orbit connects to that marketplace at build time. This means the same skill works in two places: an engineer can run it in Claude Code on their laptop, and Orbit can run it inside an automated workflow.

</details>

**Eduardo**: 这种底层共享设计从根本上塑造了我们推荐给各个研发团队的最佳落地范式：**一切从编写一个简单的 Skill 起步**。因为写一个 Skill 的试错成本极低，工程师可以快速本地调试验证，而且从写出来的第一天起就能在本地日常开发中产生收益。一旦某个任务场景被团队反复验证具有高度通用性、值得自动化时，我们再将其平滑迁移到 Orbit 平台并固化为标准工作流。此时，任务中所有可预测的步骤被转化为确定性代码，大语言模型仅在能提供高价值判断的切面介入。比起放任大模型在开放式会话中自主盲目摸索，工作流模式不仅显著提升了执行稳定性，也大幅降低了 Token 消耗成本。

<details>
<summary>Original English</summary>

**Eduardo**: That shared foundation also shapes our recommendation to teams: start with a skill. A skill is cheap to write, easy to iterate on, and useful from day one. Once a team is sure that a task is worth automating, we move it into Orbit and turn it into a workflow. The predictable parts become deterministic code, the model is called only where it adds value, and each run becomes more reliable and less expensive than an open-ended session.

</details>

**Eduardo**: 此外，Orbit 工作流在后台异步离线运行，工程师不需要守在电脑屏幕前维持长会话并不停提供每一步引导指令。这意味着大幅减少了工程师的上下文切换（context switching）消耗，让他们能够抽身将宝贵的时间投入到真正需要人类深思熟虑的核心业务挑战中。

<details>
<summary>Original English</summary>

**Eduardo**: Workflows also run in the background, so engineers do not have to sit with an open session and guide it step by step. That means less context switching and more time for the work that needs them.

</details>

---

### 结构化输出、组件化评测与可观测性闭环

**Eduardo**: 除了运行时的环境物理隔离，我们在系统确定性与可靠性上重度依赖于**结构化输出**（structured output）。在 Orbit 工作流中，每一个大语言模型交互节点都会强制配置严格的 **JSON Schema** 进行响应约束。通过在输出层对数据格式进行强校验，我们确保了后续的业务逻辑分支跳转、异常分支处理以及状态流转全部由确定性代码的控制流驱动，而不是依赖不可控、充满隐患的自然语言字符串正则解析。一旦大模型的响应内容未能通过预设 JSON Schema 的契约校验，Orbit 就会自动拦截并触发定向重试策略或执行优雅降级分支，绝不会让脏数据流向下游。

<details>
<summary>Original English</summary>

**Eduardo**: Beyond runtime isolation, we also rely heavily on structured output to guarantee systemic reliability. Every LLM step in an Orbit workflow enforces strict JSON schemas for model responses. By constraining output formats, we ensure that subsequent execution branches, error handling, and state transitions are driven by deterministic control flow rather than unpredictable string parsing. If an LLM response fails validation against the expected JSON schema, Orbit automatically triggers a targeted retry or fallback path before proceeding.

</details>

**Eduardo**: 我们依赖的另一项关键工程实践是**组件隔离评测**（isolated component evaluation）。如果试图在合成基准测试环境下对复杂的端到端长链路智能体进行评测，通常会伴随极大的噪声干扰、高昂的 API 调用开销，且非常难以在回归测试中实现稳定复现。因此，我们的评测套件放弃了从头到尾整体黑盒评测的做法，转而对单个 LLM 节点实施完全隔离的切片评测。我们通过将真实的生产历史状态与上下文数据精准注入到工作流的特定节点中，能够单独衡量该步骤下模型的输出质量、精细校准 Prompt 提示词工程，并以极低的试错成本快速捕获模型能力退化或回归缺陷。

<details>
<summary>Original English</summary>

**Eduardo**: Another crucial pattern we rely on is isolated component evaluation. Evaluating complex end-to-end agentic workflows in synthetic benchmark environments is often noisy, expensive, and difficult to reproduce consistently. Instead of trying to evaluate entire workflows from start to finish, our evaluation harness isolates individual LLM steps. By injecting exact historical state and context directly into specific workflow nodes, we can evaluate model output quality, measure prompt adjustments, and catch performance regressions quickly and cost-effectively.

</details>

**Eduardo**: 那么，我们如何判定一个新构建的智能体达到了投产标准呢？目前，一个新智能体在初次上线前通常需要经历团队内部的实战效果走查（vibe check）——即由开发团队挑选数个具有代表性的真实业务 Case 进行验证，确保其行为表现完全符合预期。一旦通过走查正式投产，系统就会基于 **OpenTelemetry** 对每一次生产执行展开全链路追踪（end-to-end trace），记录每一次节点活动、模型调用入参与工具执行详情。

<details>
<summary>Original English</summary>

**Eduardo**: So how do we know when an agent is good enough? Today, a new agent usually reaches production after a vibe check: the team tries it on a few real cases and confirms that it behaves as expected. Once it runs in production, we trace every execution end-to-end with OpenTelemetry, including each activity, model call, and tool call.

</details>

**Eduardo**: 随后，我们会从真实的线上 Trace 数据中抽取典型样例，持续扩充并打磨出该场景的**黄金评测数据集**（golden dataset）。目前，各个场景的黄金数据集与业务代码一并保存在代码仓库中接受版本管理，并支持按需触发评测。研发团队可以基于评测数据反馈持续优化 Prompt 或者调整候选模型，并在同一套黄金基准上反复运行比对效果差异。尽管当前我们尚未完全实现全自动的在线持续评测，但这套体系的打通已经在紧密推进中。我们的终极目标是在 Orbit 平台内部直接打通“智能体发布 -> 线上观测与生产评测 -> 逆向反哺优化 Prompt 与模型 -> 零部署热更新生效”的端到端数据飞轮闭环。

<details>
<summary>Original English</summary>

**Eduardo**: We then extract traces from real executions to add to a golden dataset. For now, each golden dataset is versioned in the repository next to the code, and we run evaluations on demand. Based on those results, we improve the prompt or change the model, and we run the dataset again to compare. We do not have fully automated continuous evaluations yet, but we are working on them internally. Our goal is to run the whole evaluation loop inside Orbit from the UI or through the MCP server: first, you deploy your agent, then you monitor and evaluate its execution in production, and finally, you improve the agent based on those evaluations without the need to deploy it again. That is our roadmap for evaluation: to trace, measure, and improve every workflow.

</details>

---

### 规模化业务收益、治理经验与演进路线

**Eduardo**: 这种架构设计在整个 Flywire 研发团队中产生了极其显著的实际业务推动力。单在过去的 30 天内：
- 我们的**代码审查智能体**累计完成了超过 **9,700 次**自动化审查运行，单个 Merge Request 平均审查耗时缩短至仅 **3 分钟**以内；
- 我们的依赖审计修复智能体（Audit Fixer）自动开启了 **159 个**合并请求，批量修复存在漏洞的三方依赖组件；
- AI 就绪修复智能体自动化改良了约 **80 个**代码仓库；
- Victoria 规范检查修复智能体（Linter Fixer）完成了对 **430 个**工程项目的代码规范与最佳实践自动修正；
- 合并冲突解决助手（Merge Conflict Bot）累计调用执行达 **921 次**。

在涵盖上述多类高频场景的综合工作流中，平台累计承载了超过 **11,000 次**生产执行，全流程任务成功率高达惊人的 **99%**。

<details>
<summary>Original English</summary>

**Eduardo**: The operational impact of this approach has been significant across our engineering organization. In the past 30 days alone, our automated code review agent completed over 9,700 runs, averaging under 3 minutes per Merge Request. Beyond code review, our Audit Fixer opened 159 Merge Requests to fix vulnerable dependencies, and the AI readiness fixer improved around 80 repositories. The Victoria linter fixer fixed 430 projects, and the merge conflict bot was run over 921 times. Across these workflows, we ran over 11,000 executions with a 99% success rate.

</details>

**Javier**: 回顾我们的架构演进与平台化历程，推行**自助服务模型**（self-service model）无疑是团队做出的最明智决策之一。基于标准化的脚手架与组件库，来自 SRE 稳定性工程、安全团队、IT 以及技术支持部门的工程师均可根据自身诉求，极为快捷且安全地拼装自定义工作流步骤。

<details>
<summary>Original English</summary>

**Javier**: Reflecting on our journey, adopting a self-service model was one of the best decisions we've made. Standardized scaffolding allows engineers across SRE, Security, IT, and Support to build custom workflow steps easily and safely.

</details>

**Javier**: 我们收获的另一条深刻经验是：**工程成本控制始于模型选型**。在复杂的长链路工作流中，并非每一个步骤都需要消耗顶配的超高智商基础大模型。在 Orbit 中，工作流的每一个 LLM 节点都支持独立声明绑定具体的模型规格。例如，前期的方案规划步骤可以使用推理能力强大的大模型，而后续具体的代码格式化或简单重构步骤则完全可以使用轻量化的小模型来执行。这种将模型能力与具体任务颗粒度高度匹配的做法，使整体 API 调用开销得到了极其严格的控制。目前，基于成本感知的模型路由器（cost-aware model router）已经被列入我们的核心迭代路线图中。

<details>
<summary>Original English</summary>

**Javier**: We also learned that cost control starts with model selection: not every step needs the most capable model. So each LLM step in a workflow declares its own model. For example, a planning step and an implementation step can use different models. Matching the model to the task keeps cost under control, and that is why a cost-aware model router is on our roadmap.

</details>

**Javier**: 另一方面，**严格的数据边界隔离**始终是平台必须坚守的底线。我们在底层架构中严格划分并物理隔离了三类核心数据域：研发体系的 SDLC 代码与元数据、企业日常运营协作数据、以及最为机密核心的线上生产支付业务数据，三者之间设置有明确的数据访问防火墙。此外，由于全公司对于智能体自动化的业务需求呈现井喷态势，平台团队必须时刻保持战略定力，学会合理过滤需求，优先聚焦于具备最高业务影响力的核心场景。

<details>
<summary>Original English</summary>

**Javier**: On the other hand, managing data separation remains an ongoing responsibility. We maintain a strict isolation between engineering SDLC data, corporate operational data, and sensitive payment production data. Additionally, because demand for automation is high, maintaining focus and prioritizing high-impact work is essential.

</details>

**Javier**: 展望未来，我们的技术演进路线图重点聚焦于平台功能边界拓展与底层架构灵活性的提升：
1. **全隔离安全沙箱演进**：全力构建完备的运行时沙箱环境，使智能体能够平稳处理复杂的多模块编译构建、启动本地虚拟环境，并跨异构技术栈并发无缝跑通集成测试套件；
2. **可恢复持久化会话（Resumable Sessions）**：引入原生支持断点恢复的持久化会话机制，以便更从容地协调高复杂度、长周期的多阶段智能体任务；
3. **平台原生评测控制台**：在 Orbit 内部深度集成原生的评测与对比工具集，让各个业务团队在平台内就能对自身工作流的交付质量与模型迭代效果一目了然；
4. **模型无关的编排抽象与成本动态路由**：重构底层编排接入层使其彻底模型中立（model-agnostic），支持跨不同模型供应商无缝调度，并上线智能化自动路由引擎，动态为每个任务分发性价比最高的最优模型，在业务平台持续规模化扩张的同时牢牢锁死算力开销；
5. **执行套件解耦（Harness-agnostic）**：推进底层与特定 Agent SDK 解耦，确保平台未来不与单一开源框架强绑定，始终保持技术先进性与架构灵活性。

<details>
<summary>Original English</summary>

**Javier**: Looking ahead, our roadmap focuses on expanding our platform features and increasing overall architecture flexibility. We are actively moving toward complete sandboxing, so agents can handle complex builds, local environments, and test suites seamlessly across all project stacks. Moving forward, we are also introducing resumable sessions to handle complex multi-step tasks. We are also building model evaluation tools directly into Orbit, so teams can measure the quality of their workflows on the platform itself. In parallel, we have refactored our orchestration layer to be model-agnostic, enabling flexible routing across different model vendors, including an automated model router that selects the most cost-effective model for each task to help us control cost as we keep scaling the platform. We also want to make the platform harness-agnostic, so that we are not tied to a single harness.

</details>

**Javier**: 最后，在结束今天的分享之前，我们想为大家提炼三条最关键的落地建议：
- **第一，小处着手，验证后再规模化**：挑选那些流程重复、规则清晰、定义明确的任务作为切入点。在动手大范围推广之前，务必先在小范围内彻底跑通并验证实际商业价值；
- **第二，仅在真正创造增量价值的环节使用大模型**：把所有能够被确定性代码解决的环节毫不犹豫地留给传统程序代码。让确定性代码充当系统的坚固骨架，这是让复杂工作流稳定长效运转的秘密武器；
- **第三，筑牢护栏，坚持人类介入闭环（Human-in-the-Loop）**：通过超时熔断、严格限流以及不可逾越的 MR 人工代码复核流程构筑防线。只有建立起坚定的工程安全边界，我们才能真正实现从零散脆弱的 AI 玩具实验，跨越到全公司成百上千名工程师每天都高度依赖且信任的坚固工作流基础设施。

<details>
<summary>Original English</summary>

**Javier**: To wrap up, three takeaways: First, start small. Pick a repetitive, well-defined task, and prove it works before you scale. Second, use the model only where it adds value. Everything predictable is solid as code, and that is what keeps the workflows reliable. Third, keep guardrails and humans in the loop: timeouts, rate limits, and Merge Request reviews. That is how we move from fragile AI experiments to dependable workflows our engineers use every single day.

</details>

**Eduardo**: 非常感谢大家今天的时间与关注！如果各位对 Orbit 的架构设计或实践有任何疑问或见解，欢迎随时与我们沟通交流。谢谢！

<details>
<summary>Original English</summary>

**Eduardo**: Thank you so much for your time and attention today. Feel free to reach out to us if you have further questions or comments.

</details>