---
author: AI Engineer
date: '2026-08-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=dQ-_i1tZiws
speaker: AI Engineer
tags:
  - ai-agent
  - enterprise-architecture
  - llm-ops
  - software-engineering
title: 全球航运的部落迷宫：规模化 AI Agent 落地生产的系统工程
summary: 本文基于马士基（Maersk）一线工程师的实战复盘，深度剖析了 AI Agent 在全球航运复杂业务场景下的落地难点。文章指出，构建生产级 Agent 系统的核心不在于基础模型或单一 Agent 循环，而在于将隐性业务知识（SOP）转化为 Agent 可安全执行的代码资产，并建立包含确定性护栏、全链路追踪评测与反馈迭代闭环的自适应工程体系。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Maersk
products_models: []
media_books: []
status: evergreen
---
### 走出演示陷阱：生产级 Agent 面临的长尾与复杂系统挑战

在真实世界的企业级生产环境中，**AI Agent**（人工智能智能体）面临的核心挑战远非演示文稿中的基础循环逻辑所能概括。以**全球航运业务**（Global Shipping Operations）为例，表面上标准化的单一条目工作流，实质上是多套高度耦合且并行运行的**状态机**（State Machine: 描述系统在不同状态间转换及行为的数学与工程模型）编排。当各系统状态吻合时，理想路径能够顺利流转；然而一旦某个子系统发生状态漂移，就会引发海量的异常处理需求。

目前多数企业已经自动化了占绝大多数的简单标准流程，剩下的难点全部集中在极具破坏性的**长尾异常**（Long-tail Exceptions）中。真实世界的业务逻辑高度依赖多个异构且不完备的遗留系统同时保持一致性。当某个步骤受阻导致理想路径断裂时，传统模式必须依赖资深业务专家跨多个遗留系统进行人工协同与补偿操作。这种跨系统的长尾异常不仅处理成本极高，也正是硅谷 AI 理想模型脱离现实业务场景时遭遇的最大壁垒。

<details>
<summary>Original English Source</summary>

Hello everyone. This is a practitioner report from real production work. So, let's get into it. I'll skip the generic yet another loop agent intro. This is about the hard part most agent demos skip, and about turning messy operational knowledge into something an agent can execute safely.

This comes from real work in my company I'm working for supporting global shipping operations and grounded in production. On paper it's one workflow usually, but in reality every shipment is an orchestration of many parallel state machines. While they agree the happy paths work; the moment one drifts, you get exception work.

The easy majority is already automated in many companies. What's left is the long tail and more exceptions than systems built to handle them. That tail is the expensive part. And then there's my favorite category. And it comes with a special plate here. See for AI builder dreams and their laptops, this what you can find outside of AI bubble in San Francisco. The signal process depends on many systems being coherent at once. If any step can't complete, the happy path breaks and then it takes expert orchestration across multiple incomplete systems.
</details>

### 解构部落迷宫：从人类截屏 SOP 到 Agent 可执行资产

在受监管的复杂传统行业中，应对业务变异的标准工具是**标准作业程序**（Standard Operating Procedure: 企业规范作业流程的操作指南，简称 **SOP**）。然而，现存的业务知识大多被深锁在**隐性知识孤岛**（Tribal Dungeons: 散落在组织老员工经验中、未被形式化建模的业务逻辑与经验）中。传统的 SOP 本质上是为人类员工编写的“截屏与点击序列”，仅描述了用户在界面上看到什么、点击哪里的表面交互，根本无法被智能体直接且安全地运行。

要让 Agent 安全接管业务流程，必须将传统 SOP 彻底重构为**Agent 可执行 SOP**（Agent Executable SOP）。这类 SOP 需要涵盖明确的前置条件、决策逻辑、业务唯一标识符、后端接口调用契约、校验机制、容错与恢复路径，以及执行成功的留存凭证。在这一范式下，**业务专家拥有“定义目标（What）”的主权，而 Agent 与工程师则负责“实现路径（How）”的工程化**，并将各类业务异常转化为强约束的系统护栏。

<details>
<summary>Original English Source</summary>

All these variations pathways should be captured in SOPs. SOP is a standard operating procedure common in regulated industries. So an expert and the model read them the same way. That gap is the hard part: stable intent detection, tool calls you can guarantee are safe, integrating with legacy backends, and results evaluated with experts.

I call this tribal dungeons: the knowledge exists, but not in a form an agent can execute and you can safely run a process. The organization cannot represent standard legacy SOPs—a bunch of screenshots organized in sequence, but screenshots are not a process. Legacy SOPs explain what a person sees and clicks. And an agent SOP needs a more complex setup: preconditions, decisions, identifiers, backend calls, validation, recovery, and evidence of successful execution.

Experts own the what, agents own the how. And exception becomes a guardrail. Most of the effort is the translation and negotiation between them to align on common sense.
</details>

### 系统重心转移：围绕 Agent 的自适应精炼闭环

生产级 Agent 系统的工程核心绝非 Agent 本身的调用循环，而是围绕它建立的外部**自适应精炼系统**（Refining Loop Architecture）。在生产架构中，系统主要由三大支柱构成：以 **SOP 语料库**（SOP Corpus）形式组织的企业流程记忆库、**执行运行时**（Execution Runtime），以及**分诊与反馈捕获机制**（Triage & Feedback Capture）。

由于不同国家和地区的监管与业务惯例存在巨大差异，相同的业务术语在不同语境下含义迥异。SOP 语料库作为沉淀企业跨国流程记忆的核心资产，其体量与复杂度远超运行时本身（二者工程量比例可达 20:1）。在当前并发运行超过 200 个生产实例的规模下，系统响应延迟在数分钟到十分钟不等，其核心瓶颈往往在于下游众多老旧遗留系统的响应能力，而非大模型推理本身。

为了缓解业务专家审查时间的稀缺瓶颈，评测系统（Theme Bench）必须负责自动完成**故障聚类分诊**（Failure Clustering & Triage），输出可直接采取行动的具体变更。**执行追踪日志**（Trace）构成了专家与工程师共同审查真实案例、对故障原因达成共识的事实依据。在严谨的工程标准下，任何审查意见只有被转化为可执行的代码或规则变更时才算有效修复；系统的可靠性绝非来自模型参数规模的盲目提升，而是来自基于真实生产回放（关闭写权限以保护生产系统）的持续回归验证。

<details>
<summary>Original English Source</summary>

Three parts here in this architecture: it's SOP memory organized as SOP corpus, execution runtime, and theme feedback capture. The agent loop is not the system. The refining loop around the agent is the system, and it's the most complex part.

It's a good illustration why the same thing means different and describing differently in different countries, and it's creating a lot of variations between each country. And that corpus is an asset—the company's process memory modified and aligned with every country's conditions, and far bigger than runtime; you could see the proportion 20 to 1.

And this is concurrently operating system, and this is the scale we run in production today: over 200 instances, and spikes and latencies deviates from few minutes up to 10 minutes. Mainly the main reason for it that we depending on many legacy systems which cannot be faster than agent loop itself.

Expert time is the bottleneck. So the theme bench does the triage for us. It clusters the failures and hands back something you can act on, not just look at it. The trace is the shared evidence that lets an expert and an engineer review the same case and agree on what happened. A correction only counts when it becomes an executable change. And that's the line between an opinion and a production fix.

And this is where quality comes from: not from vibes, not from a bigger model; from replaying real examples with disabled writes to protect the production systems and checking whether behavior improved.
</details>

### 确定性工程护栏：从数万次修正中沉淀复合能力

高可靠性的生产级 Agent 系统无法通过前期的单张架构蓝图一蹴而就，必须依赖在超大规模场景下通过微小修正逐步累积。在长达 9 个月的开发周期中，系统经历了超过 100,000 次精准修正。通过将海量追踪转化为**故障热力图**（Failure Heat Maps），工程团队能够精准定位优先级，协同专家攻坚最具业务价值的高频卡点。

在工程哲学上，探索发现阶段需要给予 Agent 足够的自主权，但**进入生产环境则必须施加确定性的严格束缚**。外部脚手架（Harness）的核心目的不是为了扩展 Agent 的自由度，而是为了**在物理上杜绝愚蠢错误的发生**。在工业级规模下，单纯依靠“Prompt 提示词叮嘱”（如要求模型“小心处理”）毫无防护意义。必须建立分层防御机制：
* 针对工作流分类错误，配置专门的**分类评测器**（Classifier Eval）；
* 针对非法数据写入，部署强约束的**写入网关**（Write Gate）；
* 针对关键路径上的不可逆操作，保留人工审查与审批闭环（Human-in-the-loop）。

真正的核心产出并非某个单一 Agent，而是一套严谨的 Agent 落地方法论体系，其核心行动原则包含五大支柱：
1. **工作形式化**（Make work representable）：将业务流程转化为机器与人类可共同理解的模型；
2. **执行边界化**（Make execution bounded）：限定执行范围，消除无约束行为；
3. **行为可观测**（Make behavior observable）：对每个 Agent 的状态转移与工具调用建立全链路追踪；
4. **修正低成本**（Make correction cheap）：降低从发现缺陷到完成修复的工程代价；
5. **改进可复利**（Make improvement compound）：确保每一次局部修复都能持续累积为全局资产。

在工具设计层面，团队避免直接引入庞大而未经提炼的通用标准（如 MCP），而是采用精简蒸馏的**函数调用**（Function Calling: 结构化调用外部 API 的接口机制），将经过验证的成功操作序列沉淀并合成为更健壮的**复合工具**（Composite Tools）。这种自适应架构使经过单国验证的自动化能力能够迅速、安全地横向推广至上百个国家和地区的业务网络中。

<details>
<summary>Original English Source</summary>

You can see here on the cognitive proportion or this effort ratio between each activity in our project. Usually pipe coding ends here; here ends spec-driven development because it cannot improve accuracy more than this stage on this scale. And this is where the real work starts. Nothing exotic: it's engineering common sense applied at scale.

So if you don't know all this terminology which developed over last 30 years in software development, an argument to check because this is what every AI coding agent should know to help you develop reliable production systems. And accuracy wasn't designed in one diagram up front; it was earned one small correction at a time at the scale you see here. So we have over 100,000 corrections over last 9 months in the system when we developing it.

And this heat maps turned thousands of traces into priorities. This is how we keep experts and engineers looking at the same problems and prioritize where the most beneficial work for them. Every cell is a group of tracked scenarios we have, and usually to turn one block in red it's around 1-2 months of efforts for the whole team of engineers and also AI agents.

The agent failed is where the investigation starts, not where it ends. Each failure maps to a specific fix. Discovery needs agent freedom, and production needs a cage. The harness isn't there to give the agent more room; it's there to make the dumb mistakes impossible.

So on this scale, "please be careful" is not a guardrail. If we have wrong workflow, then classifier eval; if it's wrong write, then write gate; if it's wrong assumption, then it's a review. A preventive measure eliminates the unsafe path on critical paths. Review and approval stay in the loop. The engineering focus is to build safe handoffs and a trail you can trust.

The real outcome wasn't the agent in the system. It was the methodology we built around it. If you want the blueprint, then it's these five moves:
1. Make work representable.
2. Make execution bounded.
3. Make behavior observable for every agent.
4. Make correction cheap.
5. Make improvement compound.

AI-native operation is more than agents in workflow. It's a system that learns from what works and folds it back into code as new composite tools, adapting to the applications and the people around it. The adaptive architecture we built is the final asset. We aggregating all repeatable sequences of steps and successful scenarios and merging them into bigger tools which combine these proven scenarios into reusable snippets by other agents. And then it's possible to roll them out not only for one country, but for hundreds of countries in one go.

And the final reminder: if you are AI builder, if you are emotionally attached to tools, not MCPs—we're not using MCPs because for us it's always not the best choice, because all systems usually really bloated and we have to distill responses and tune the tools through function calling to our agents. Then we can control quality of our software and ensure that it's correctly processing assigned tasks.
</details>