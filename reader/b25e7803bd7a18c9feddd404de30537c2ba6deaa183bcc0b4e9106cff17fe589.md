---
author: AI Engineer
date: '2026-05-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5ID22ACI7IM
speaker: AI Engineer
tags:
  - context-engine
  - agentic-workflow
  - developer-productivity
  - rag-optimization
  - software-architecture
title: 重构上下文引擎：超越 RAG 与长文本的 AI 研发新范式
summary: Peter Werry 在本次演讲中深入探讨了在 AI 代理时代构建“上下文引擎”的必要性。他指出，单纯增加上下文窗口或使用基础 RAG 无法解决“理解”问题。通过整合社交工程图谱、识别历史决策意图并解决数据冲突，上下文引擎能显著提升 AI 代理的执行精度，在实际案例中将复杂任务的 Token 消耗降低 50% 以上，并大幅缩短交付时间。核心在于将组织中的专家经验“瓶装化”，让 AI 编写的代码如同资深员工手笔。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Peter Werry
companies_orgs:
  - Unblocked
  - Anthropic
  - OpenAI
  - Google
products_models:
  - Claude
  - Gemini
  - Mythos
media_books: []
status: evergreen
---
### 场景重构：从“零点”代理到高效执行的上下文艺术

在 AI 代理（AI Agents）的世界里，当你开始编写代码时，代理最初往往处于“零点”状态——它们对你的代码库、组织架构、工程规范一无所知。通常情况下，代理的第一步是疯狂扫描代码库以获取背景理解。**上下文引擎**（Context Engine）的核心艺术在于：以高度优化的方式，精准提供执行任务所需的全部上下文，同时**剔除所有无关信息**。这样，当代理开始运行时，它能以流水线式的方式执行任务，并确保产出完全符合组织的最佳实践、预期和规范。

<details>
<summary>Original English Source</summary>

In the world of AI agents, you have agents that, when you start off and you start coding, they are basically at ground zero. They have no context about your code, your organization, nothing. Okay. So typically what happens is the first thing they do is they start to rip around your codebase based on the task that you give them to try to gain some understanding, sort of background understanding, before they start to do their task. So context engineering is kind of the art of supplying all the context that you need and, most importantly, none of the context that you don't need in a highly optimized way, so that when the agent starts to run, it executes the task in a streamlined way that's in line with your organization's best practices and expectations and so on.

</details>

### 上下文演进：从人类“战斗伤疤”到背景代理

回顾在 AI 出现之前，一个人是如何在组织中建立上下文的：你通过经验积累、代码探索、跟随导师，并最终经历真实的线上事故和停机。这些“痛苦”构成了**组织上下文**（Organizational Context）——即“我们为什么以这种方式做事”的背后逻辑。

从技术路径来看，我们经历了从 2022 年 8k 长度的“高级自动补全”到集成语言服务器的转变。现在，大多数人处于使用 MCP（Model Context Protocol）和技能连接并行代理的阶段。然而，**人类正在成为瓶颈**。在管理多个并行任务时，频繁的上下文切换会导致严重的认知断层。要迈向全自动的背景代理模式，必须依赖一个理解代码运行逻辑、组织运作方式以及历史变更动机的上下文引擎。

<details>
<summary>Original English Source</summary>

Not long ago, as in like four years ago or less, you were the context engine. When your agent needed something, you would prompt it, you'd grab the issue ticket, you'd hand it all of the information that it needed to start its task. Over time, you would accumulate this kind of context through experience, right? You'd start a job, maybe start code splunking a little bit... eventually you'd experience real things like incidents and outages... Those are the battle scars, right? And that is what constitutes organizational context. It's the learnings along the way, the "why did we do things the way we did it."

We're becoming the bottleneck as humans. I'm not sure if people have tried managing parallel agents and working on several tasks at once, but everyone's starting to feel this cognitive disconnect because you're context switching all the time and it's just really, really painful. It is very difficult to move from that mode where you're the human managing context into the background agents mode unless you have some kind of context engine that knows how your code operates, how your organization works and understands the motivations for historical changes.

</details>

### 破除三大迷思：为什么 RAG 和长文本不是终极答案

在构建上下文引擎的过程中，业界存在三个常见的迷思：

1.  **“基础 RAG 等于上下文引擎”**：单纯对文档做向量搜索会导致“搜索饱和”（Satisfaction of Search）问题。代理会疯狂搜索并消耗 Token，但在缺乏**个性化**（Personalization）和任务对齐的情况下，往往会拉入无关代码，制造混乱。
2.  **“连接一堆 MCP 服务器就够了”**：访问不等于理解。即便连接了 Slack 和 GitHub，系统若不理解数据间的关联逻辑，依然无法复现专家的判断。
3.  **“更大的上下文窗口能解决一切”**：Gemini 虽然率先实现了百万级 Token 窗口并擅长“大海捞针”，但其**跨数据源推理**和理解深层问题含义的能力仍然有限。而且，绝大多数组织的上下文远超千万级，试图将一切塞进窗口既不可行也不经济。

<details>
<summary>Original English Source</summary>

Myth one, naive RAG over my docs is a context engine. If you implement say vector search, you're going to run into a few issues. One is this satisfaction of search problem where the agent will search like crazy, consume your tokens and then in the worst case you'll reach compaction. You need to have personalization... if you just RAG all your data, it's just going to create a huge mess.

And finally, a bigger context window will solve this. Gemini first model to try this and it was really good at finding needle in the haystack. But it wasn't good at all at reasoning across different data sources, understanding the real meaning behind a problem and then recommending the appropriate solutions. Most organizations have more than a million tokens worth of context. Trying to fit all that into the context window isn't going to work anyways.

</details>

### 搜索饱和与冰山模型：挖掘隐藏的“决策意图”

彼得借用放射医学中的**搜索饱和**（Satisfaction of Search: 放射科医生发现一个能解释症状的异常点后便停止搜索，从而遗漏更严重的病灶）来类比 AI 代理。代理在 Notion 或 Confluence 中找到一个看似匹配的信息后往往会停止，但真正的“黄金信息”可能隐藏在过去的 Slack 讨论、事故报告或由于某种原因被删除的代码中。

工程领域的**冰山模型**显示：能编译的代码只是水面上的基准，而水面下真正重要的是**用户原始意图**、团队曾拒绝过的方案、失败的尝试以及决策的历史背景。一个真正的上下文引擎必须能够感知“谁是专家”、“曾经发生过什么冲突”以及“这些冲突是如何解决的”。

<details>
<summary>Original English Source</summary>

Satisfaction of search is a term that actually comes out of the medical field in radiology. Techs might find something on the x-ray that explains those symptoms and then they stop. This is what happens with agents... they'll stumble across what looks like the thing they're looking for and they'll stop. But the real golden nuggets of information might be in a different place... like in a past Slack conversation or in an incident report.

Here's the classic iceberg meme. Code that compiles - that's like the baseline. But everything that is actually important happens underneath here: understanding the user's original intent, what was rejected in the past by the team and tried before but failed. You need history as well leading up to decisions.

</details>

### 核心能力：统一上下文与社交图谱的协同

一个功能完备的上下文引擎需要具备六大核心需求，其中最关键的是**统一系统上下文**。它不仅要发现数据间的显性链接（如 Slack 中的 PR 链接），更要深度挖掘潜性规律。

通过蒸馏历史 PR 评论，系统可以识别出组织的**最佳实践模式**并将其存储为“记忆”。例如，当新员工修改代码时，引擎能自动加载相关记忆：“本组织在这种场景下通常采用 X 模式而非 Y”。

此外，**权限控制流**（Access Controls Flow）在企业级应用中至关重要。例如，Unblocked 集成了 Slack 私有频道信息，但它**仅在提问者拥有权限时**才会使用这些敏感信息生成答案，且答案对其他人不可见。

<details>
<summary>Original English Source</summary>

Unified system contexts... it's more than just recognizing when one piece of data is related to another. You have to go a little deeper... distill historical pull request comments on PRs and try to distill those down to their core essence... store them as "memories" so that when someone is working on a similar piece of code you can load those memories and then the agent can see that.

It's really important that you flow the access controls up. Our context engine integrates with Slack or Microsoft Teams. When you have private channels that are highly sensitive... it will only use that information if the person that's asking the question has access to it. And then those answers are not public.

</details>

### 性能飞跃：2100 万 vs 1000 万 Token 的效率之战

在 Unblocked 进行的一项大型任务实验中，未使用上下文引擎（仅连接 MCP 服务器）的代理因不理解遗留系统的兼容性需求，反复做出错误尝试，耗时 2.5 小时，消耗了 2100 万 Token。而在开启**上下文引擎**后，代理准确识别了历史变更动机并实现了向后兼容，仅耗时 **25 分钟**，消耗 **1000 万 Token**。

彼得总结了三个惨痛的教训：
1.  **优化“理解”而非“访问”**：单纯提供工具是不够的。
2.  **暴露冲突而非掩盖冲突**：当引擎无法确信事实真相时，应将其作为信号反馈给人类，而非草率处理。
3.  **严禁缓存答案**：由于代码和文档随时在变，缓存的答案会导致模型产生“均值回归”（Regress towards a mean），持续引入过时或错误的背景，污染上下文。

<details>
<summary>Original English Source</summary>

Without the context engine, it took two and a half hours to finish this task with 21 million tokens. But with the context engine it took only 25 minutes and 10 million tokens. It's a pretty dramatic difference.

Hard lessons: One, initially we optimized for access not understanding. Second one, we hid conflicts instead of surfacing them. A context engine... can't always tell what the truth elements are and when it can't, you should surface that and learn from it. And finally, do not cache the answer... everything changes constantly. If you continuously bring previous answers into context, you're obviously going to pollute the context.

</details>

### 社交工程图谱：如何“装瓶”专家经验

在随后的 WorkShop 环节，彼得展示了如何构建**社交工程图谱**（Social Engineering Graph）。这不仅仅是为了看谁贡献了更多代码，更是为了识别**谁才是特定领域的专家**。

通过分析 PR 的评审关系和贡献路径，引擎可以自动划分团队集群并定位核心专家。在 Unblocked 内部，这些专家图谱被用作上下文检索的**跳转点**（Pivot Points）。系统会执行“瓶装化专家”（Bottling the Expert）的操作：蒸馏该专家过去的工作内容、层级地位以及在 Slack 中的决策逻辑。当新员工进入该代码领域时，引擎会自动“开瓶”这些专家的认知，作为种子数据（Seed Context）引导代理。

<details>
<summary>Original English Source</summary>

Social graph is not just about conveying information about who the experts are. It's used within the context engine as a pivot point into more important context. Another part of a context engine is "bottling the expert" - distilling what that individual has worked on in the past, where they sit in the hierarchy, the decisions they've made based on Slack conversations... Getting that expert's learnings into context is a really powerful mechanism. It helps drive the rest of the retrieval in an agentic loop and it helps the agent directionally where to go next.

</details>

### 专家 Q&A：隐私、评价指标与未来愿景

*   **关于隐私**：对于极度敏感的政府或银行客户，Unblocked 提供私有化部署（On-prem），但推荐使用云端以获取更快的更新。数据隔离是基于 Repository 和 Group ID 实现的。
*   **评价指标**：除了 Token 和时间，最重要的是**氛围值（Vibes）**，即用户满意度。目前 Unblocked 在 -100 到 100 的量表上得分约为 60（归一化约 0.75-0.8）。
*   **执行与检索的比例**：在复杂的 Agentic 流程中，**90% 的时间花在上下文搜集上**，代码编写本身极快。优化输出 Token 的效率远比输入 Token 更关键，因为输出是拖慢性能的主因。
*   **愿景**：AI 生成的代码不应看起来像个新手，而应感觉像是**在该团队工作了 20 年的资深员工**所写。

<details>
<summary>Original English Source</summary>

Agent context collection is probably close to that number. It's like 90%. The actual code writing part is really, really fast. The thing that really impacts performance is output tokens.

AI generated code should just feel like it was written by someone that's been in your team for like 20 years. If it doesn't yet, that's fine. It will.

</details>