---
author: AI Engineer
date: '2026-09-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KcVkq5L-0f0
speaker: AI Engineer
tags:
  - context-engineering
  - ai-agent
  - context-engine
  - software-engineering
  - model-context-protocol
title: AI Agent 上下文工程：如何终结「你说的完全正确」并解决企业级上下文缺失
summary: Unblocked 联合创始人 Brandon Waselnuk 深入探讨了 AI Agent 在企业工程落地中的核心瓶颈——上下文缺失。他分析了 Agent 频繁出现「你说得对」并陷入无休止错误循环的底层原因，对比了人工维护 Markdown 上下文与 MCP 工具调用的局限性，并提出了融合全域工程数据、权限控制、确定性分析与语义检索的企业级上下文引擎解决方案。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Unblocked
products_models: []
media_books: []
status: evergreen
---
### 上下文断层危机：Agent 为何总在盲目附和「你说得对」

在当前软件工程向 AI 与 Agent 深度集成的演进过程中，开发者普遍经历着从简单的代码补全（Tab 键自动补全）向全自主 Agent 编码的范式转移。早期的代码补全工具以开发者的大脑为核心上下文载体，开发者凭借多年对业务逻辑、团队架构、历史 PR、甚至夜间事故排查记忆的积累，可以极低成本判断补全代码的合理性。然而，当工程师启动一个全新会话的终端 Agent 时，这套由人类数年工程实践沉淀下来的“隐性知识”与“组织上下文”是完全缺失的。

这种上下文真空直接导致了代价高昂的恶性循环。当 Agent 在对企业业务流程和代码规范一无所知的情况下开始编写代码，往往在第一步就引入了错误假设。随后，开发者被迫在审查环节介入并指出错误，而 Agent 则会立刻附和「**你说得完全正确！**（You're absolutely right!）」，继而在相同的错误假设上不断打补丁、消耗大量的推理 Token 和排查时间。对于拥有庞大遗留代码库、需要持续交付实际业务价值的成熟团队而言，无法在编码初期向左移动（Shift Left）并注入精准上下文，Agent 的并发执行就会退化为一场吞噬 Token 预算和工程师精力的灾难。

<details>
<summary>Original English Source</summary>

Good afternoon. I hope everyone is having a great time. It's warm out there, but we have amazing weather. The UV index was around 10, so hopefully you are all practicing safe sun hygiene. I'm here to talk about context engineering. I was fortunate to follow Jay from LinkedIn, because he talked a lot about the actual system design and the decision-making process. I'm going to lean into the tooling and the open-source code that is coming out at the end of the week. So, if you looked at the preceding presentation, you're going to get a lot of tooling that you can try, and today I'm going to teach you a few techniques.

The goal is to fix the "you're absolutely right" problem. I think they've already updated the prompt to say "you're right" or something else, but I'm sure you've all hit this. I'm Brandon. I work at Unblocked. Yes, I have the coconuts. We're giving those out for the new context—fresh coconuts.

What I really want to talk about is those models, especially the frontier models, looking like they're going to solve all our problems today. That's what they tell us. You can make an app in five seconds. That's true for a landing page and an MVP. But what I want to think about is: with these tools, the code that the AI produces looks like it was written by someone who has been on your team for years.

To set the stage properly, you have to remember that you were the context engine for many years. How did you do that? You built the context by walking through the workspace, asking questions, reviewing PRs, rejecting PRs, attending meetings—all these tiny things that formed your mental model. You know how things work here, you know what happens when a release goes out, you were on call that night when the outage happened, and you know why it happened.

The problem is that these agents have the exact same challenge. You start a fresh session with a terminal agent: it's very smart, but it has zero context about how your company works. It has to figure it out from scratch. The issue is that when you scale these agents, the cost compounds if you do something wrong right at the beginning.

Using context properly is essential. When we look at the evolution over the last few years, code autocomplete was great because all that happened was a ghost text popup: "Hey, do you want this completed by hitting Tab?" Your brain, the internal context engine, quickly evaluated: "No, that's bad," or "Oh, that's good," and pressed Tab.

As we move toward agent execution, we enter scenarios where agents work without human intervention, or at least you want them to. To achieve that without failure, they need a way to ask questions, solve tasks, or resolve problems, and eventually generate code that can be merged into the main codebase—especially for legacy codebases that have been around for years and generate real revenue, not just greenfield projects.

The cost of incorrect context at the beginning is severe. If you think about "shifting left," you want to catch bugs as early as possible. That applies directly to context. Because in a multi-turn conversation, you get caught in failure loops: you ask the agent to do something, it says "Hey, I did it," you reply "No, that's wrong," and then it gives rule after rule after rule. That's a waste of search tokens and a waste of iteration time. It doesn't scale with tokenomics.

When you run parallel agents, you start paying a heavy tax for verification. That's why we try to use AI code reviewers; but again, context is required for those reviewers to understand business processes, business logic, and operational realities. Ultimately, if you want to take humans out of the final loop where agents make mistakes, you need an enterprise context engine so agents can formulate precise queries and get the answers required to deliver successful outcomes.
</details>

### 主流方案的局限：静态规则库与 MCP 的检索盲区

在构建 Agent 上下文体系时，业界常见的两种过渡方案均存在显著的结构性缺陷：

1. **静态上下文（Curated Context）**：开发者通常会在仓库中建立虚拟文件系统或维护专用的 Markdown 规则文件（如 `AGENTS.md` 或项目架构说明），试图将所有业务流程和架构全貌预先灌输给 Agent。这种做法在短期内能提供一定帮助，但很快会陷入**维护老化**的困境。如同任何传统的软件文档一样，静态规则库极易过时；同时，集中维护海量上下文严重依赖特定工程师的个人记忆与精力投入，难以实现规模化自更新。
2. **模型上下文协议（Model Context Protocol / MCP）**：作为标准化的工具集成接口，MCP 赋予了 Agent 读取第三方系统（如 JIRA、Slack、Confluence、Git 等）的能力。然而，MCP 仅仅解决了“数据可达性”，并未解决“信息理解与检索效率”。在实际运行中，Agent 极易陷入**确认偏差**（Confirmation Bias）——盲目抓取检索到的第一条线索便误以为获得了完整真理，缺乏系统性交叉验证能力。

当面临信息冲突时（例如过时的 Confluence 架构图与 Tech Lead 昨天在 Slack 中的实时讨论相悖），缺乏全局上下文的 Agent 无法判断哪方代表最新真相。更严重的是，随着系统规模扩大，Agent 若无法穿透代码库的隐藏依赖，即便代码完全通过语法与单元测试，也可能在部署上线时引发严重的 P0 线上事故。此外，直接开放底层数据查询还会带来权限越权（Access Control）和 Token 消耗爆炸的隐患。

<details>
<summary>Original English Source</summary>

There are some common approaches that only work partially. They represent local maximums. Two of the most frequent patterns we see among hundreds of enterprise and mid-market customers are:

First, **Curated Context**. You create a virtual filesystem or local directory, fill it with markdown files, and say: "Here is all the project context, here is how everything works." Then you allow the agent to search through it. It gets lots of useful information and starts working better. But the problem is that this repository goes stale, just like any other documentation. Who is the omniscient curator in the company responsible for maintaining that file or repository for everyone? You quickly run into maintenance bottlenecks.

Next comes the **Model Context Protocol (MCP)**. We have MCPs, and they are great. You can provide them to an agent so it can pull information from other systems. The problem, however, is that based on the server response or tool descriptions, the agent might never read what it actually needs to read. Or it suffers from confirmation bias: the agent finds the first piece of information, assumes it is correct, says "Oh, I have everything I need," and moves on.

In most organizations, yesterday's Slack conversation might state that we should do A instead of B. But if the agent can't find that, it relies on the original written architecture. Therefore, it does not have a holistic understanding of the context. The issue isn't just access to information—it's having no real operational understanding.

To supervise models effectively, you need other methods. If your agent cannot see what lies beneath the surface, it might produce code that passes 100% of the build, but that code breaks in production at 1:00 AM, causing a P0 incident because it missed a deployment procedure or a required feature flag.

Your team needs a contextual provider that understands who you are, what role you play in the organization, and what code you touch. It should understand: where do I work, what Git commits did I make, who reviewed them, who are my contacts—and use that as a starting point to discover relevant information. It should resolve conflicts between outdated architecture diagrams and yesterday's Slack message from the tech lead. Which one is correct? You need an approach that understands this nuance.

Of course, this must be paired with respecting permissions and access policies. While MCP allows OAuth and SSO integrations, if someone asks a question about confidential Project A, the system must ensure unauthorized details are not leaked in the response.

Finally, delivering context to the model at the right time without inflating the context window is critical for token optimization.
</details>

### 上下文引擎架构：多维全域数据与权限隔离

为了从根本上解决上述瓶颈，企业级上下文工程必须构建一套由多维数据流驱动的**上下文引擎**（Context Engine）。该引擎在架构上横跨六大核心支柱，实现了对组织内部全量研发活动与元数据的全自动感知与对齐：

* **组织图谱与人员拓扑（People & Teams）**：精准掌握团队成员的职能分工、协作关系及代码所有权（Code Ownership）。
* **代码库与版本演进（Codebases & Git History）**：分析代码依赖拓扑、提交历史以及代码审查（PR Review）记录。
* **业务流程与通讯动态（Slack & Collaboration）**：捕获工程师在日常沟通、技术决策与工单讨论中的动态信息流。
* **确定性检索与深度探索（Deep Research vs. Targeted Fetching）**：针对高层设计支持多跳推理深度调研，针对具体接口支持确定性即时抓取，避免无效遍历。
* **冲突仲裁与时效判定（Conflict Resolution）**：自动比对静态规范与最新即时沟通，赋予时效性更高的权威来源以更高权重。
* **细粒度权限管控（Fine-Grained Permissions）**：原生继承企业 SSO 与 OAuth 授权边界，确保跨项目检索时的数据合规与安全性。

通过在这六大维度上对上下文进行结构化预处理与智能裁剪，上下文引擎能够在**不撑爆模型上下文窗口**的前提下，将精准的信息切片以极低的延迟注入 Agent。在实际基准测试中，相较于直接将原始全量数据或宽泛搜索结果塞入上下文（Token 消耗常突破千万级），经过上下文引擎优化后的方案可将 Token 开销降低 **50% 以上**，同时彻底消除因上下文混乱导致的逻辑死循环，大幅提升代码生成与调试的首次命中率。

<details>
<summary>Original English Source</summary>

Here is how the mechanism works in practice:
On the left side, you observe all the incoming data sources. We look at engineering teams, the tools they use, and technical writing tasks—support tickets, sales notes, and more. You gather all this data, receiving real-time event updates from tools across the workflow.

These events feed into the engine, which powers six key pillars:
1. **Organizational Context**: Understanding the entire engineering organization and who works on what.
2. **Deep Research & Targeted Fetching**: Balancing in-depth technical exploration with low-latency, immediate retrieval to prevent token waste.
3. **Conflict Resolution**: Resolving discrepancies between conflicting data sources (e.g., stale documentation vs. active engineering discussions).
4. **Temporal Relevance**: Recognizing current operational state, user identity, and active project focus.
5. **Token Optimization**: Formatting and pruning context to maximize response quality without overflowing the context window.
6. **Access Control & Permissions**: Enforcing OAuth and identity boundaries so private project information is never leaked.

For large enterprises like LinkedIn, Workday, or General Motors, having this unified contextual layer is mandatory. They need full visibility across complex engineering activities.

In our experiments comparing models running with and without this contextual engine:
Without optimized context, a heavy task consumed roughly 10.8 million tokens due to repetitive exploratory loops and redundant searches. With the contextual provider, token consumption dropped by over 50%, while accuracy and execution speed improved significantly because the model operated with full awareness of the internal business environment.
</details>

### 开源工具与落地实践：从代码静态分析到企业知识落地

为推动上下文工程在广大开发团队中的落地，Brandon 分享了由 Unblocked 推出的开源工具与实践路线：

1. **开源静态工程分析工具**：该工具通过确定性程序分析技术深度解析 GitHub 仓库，自动构建出团队的专家分布图谱（Expertise Mapping）、代码依赖拓扑与贡献热区，帮助 Agent 明确每项业务逻辑的归属者与技术背景。
2. **Agent 规则库健康度检查（Rules Health Check）**：针对各团队在仓库中累积的提示词文件与规则配置，系统能自动扫描所有规则定义，检测规则间的相互冲突、重复定义及冗余项，并输出规则清晰度评分，帮助团队重构 Agent 交互界面。
3. **超越传统 RAG 的关系型上下文架构**：传统的向量检索（RAG）在处理诸如「上周关于认证模块有哪些打开的 PR」等结构化关系查询时往往无能为力。通过将代码模式与关系型元数据结合，开发者无需编写脆弱的自然语言提示词即可让 Agent 直接提取高可信度的确定性结果。
4. **跨职能业务赋能**：上下文工程的价值并不局限于研发团队内部的代码编写。当客服支持、售前解决方案与销售团队接入这套经过权限过滤的企业上下文引擎后，业务人员可以直接查询复杂的工程实现细节与技术排期，将工单流转与客户响应时间缩短达四倍之多。

最终，构建高效 AI 系统的核心矛盾已经从“模型基础推理能力不足”转移至“**上下文工程的精准供给**”。只有通过系统化的上下文管理与确定性工程支持，才能真正让 AI Agent 在复杂的企业代码库中释放生产力。

<details>
<summary>Original English Source</summary>

I want to share three tools and open-source resources:

First, a deterministic GitHub analysis tool that automatically maps team structures, identifies code ownership, and builds an expertise matrix across your repositories. When integrated with OpenAI or Anthropic models, it allows agents to intelligently route questions to the right engineering domain.

Second, an agent rules analyzer. It inspects all prompt and rule files across your repositories, detecting duplicated rules, conflicting constraints, and outdated instructions, while providing a clear health score to keep your agent prompts clean.

Third, our workshop on building relational contextual providers from scratch, moving beyond basic RAG. Traditional RAG fails on queries like "What PRs were opened last week regarding authentication?" because vector similarity cannot effectively process temporal and relational queries. Combining relational data schemas with deterministic extraction enables agents to retrieve accurate structural facts without hallucination.

The impact of this context engine extends beyond code generation. When customer support and sales teams use the context engine, ticket resolution times drop significantly, and sales cycles close up to four times faster because team members can instantly query technical truths directly from the codebase.

The barrier today is no longer raw intelligence—frontier models from Anthropic, OpenAI, and others already possess extraordinary capabilities. The real challenge is context: how to feed them the exact, verified context they need, within appropriate token economics and strict permission boundaries. Thank you for your time.
</details>