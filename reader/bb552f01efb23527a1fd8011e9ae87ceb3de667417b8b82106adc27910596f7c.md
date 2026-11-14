---
author: AI Engineer
date: '2026-05-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=XBaznoTRDFI
speaker: AI Engineer
tags:
  - agent-observability
  - technical-observability
  - llm-evaluation
  - data-processing
title: 代理观测与传统观测的区别：深度技术解析
summary: 本篇内容深度解析了‘代理观测’（Agent Observability）与传统系统观测的核心差异。Phil Hetzel 指出，传统观测聚焦于技术指标与正常运行时间，而代理观测需处理非确定性模型带来的复杂语义挑战，要求对海量非结构化文本进行实时索引，并整合技术人员与业务专家共同参与质量评估。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Braintrust
products_models: []
media_books: []
status: evergreen
---
### 代理与传统的观测差异

在进入核心议题之前，我们需要先界定当前的技术背景。**代理观测**（Agent Observability）与**传统观测**（Traditional Observability）在根本逻辑上存在巨大差异。

在传统软件工程中，观测的核心焦点在于**系统的可用性（Uptime）与技术性能**。我们利用 Datadog 或 Grafana 等成熟工具，监控请求延迟、响应时长、以及 4xx 或 5xx 错误。我们的目标是确认应用是否处于运行状态，以及从技术指标来看，用户体验是否符合预期。

然而，代理应用有着完全不同的生命周期。**大语言模型**（LLM: 基于海量文本训练的 AI 系统）天生具有**非确定性**（Non-deterministic）。传统的软件工程追求确定性的代码执行路径，以确保控制流可预测。而代理应用则是抽象的，其迷人之处在于其高多样性。因为代理可能会采取不同的路径来完成任务，所以我们需要理解它为什么选择路径 A 而不是路径 B。

因此，代理观测不能仅依赖约束性的指标。除了基础的“首次 token 时间”、“总 token 数”、“延迟”等指标外，我们更需要理解**定性的（Qualitative）指标**：
*   **上下文接地（Context Grounding）**: 系统返回的信息是否基于所收集的上下文？
*   **工具使用合理性**: 在推理过程中是否使用了预期的工具？
*   **品牌标准对齐**: 返回的响应是否符合在系统提示词中设定的品牌标准？

传统观测工具无法处理这些问题，因为回答这些问题所需的链路跟踪信息，其数据规模远超传统观测工具所能处理的量级。

<details>
<summary>Original English Source</summary>
Traditional observability is established. So, even when folks come to us, they'll say, "Well, we already have open source tools like Grafana, or as an example. Why wouldn't this be the same problem that we're solving with perhaps either an implementation or a contract that we already have?" It's very established. And we know that these applications can operate at scale. So, the case that I'll be making is that the scope of traditional observability is actually quite different from the scope of agent observability.

Scope of traditional observability: it's all about uptime and technical performance. Is the application up and is the application giving a user experience from a technical lens that we would expect? So, latency, duration of interactions, 400 and 500 level errors, these are all things that we're measuring with very established tools like Grafana, like Datadog.

Problem one for why agent observability is different: Agents are non-deterministic, whereas applications are deterministic. The reason why we love LLMs so much is because they have high variety. They can do a lot of different things. They are abstracted. Agent applications are very much non-deterministic. We're curious about why an agent might take one path versus the other. This also means that traditional observability is going to really have to focus on very constrained and known metrics, whereas agent observability needs to be a little bit broader in terms of the things that it needs to measure.

Agent observability can measure some of these more traditional metrics. Albeit with more of an AI flare: Time to first token, total tokens, duration, latency. But also, you might want to understand more qualitative things about your application. Was the information that I gave grounded in the context that I gathered with my application? Did I use the tools that I would have expected as I was reasoning towards my response? Is the response aligned to the brand standard that I set for this agent in the system prompt? These are all things that are not really able to be tested by traditional observability tools because the information in the trace that's necessary for us to compute these things is far larger than the volume that a traditional observability trace would handle.
</details>

### 复杂追踪与数据库设计挑战

代理链路的追踪数据（Agent Traces）非常“棘手”。它们具有高度的**半结构化特征**，且包含海量需要即时处理的**非结构化文本数据**。

这些数据是极其庞大的，单个代理追踪数据可能超过 1GB，甚至单个 Span 就能达到 20MB。这与传统观测数据完全不同。我们不仅需要处理摄入和处理这些海量数据的技术问题，更关键的是要在极短的时间内利用这些数据。

为了解决这个问题，我们在 Braintrust 设计了一个专门针对代理追踪的数据库。这里有两个核心技术挑战：
1.  **即时摄入与读取**: 用户希望在交互发生后即刻看到追踪结果。
2.  **复杂检索**: 代理观测往往需要像“查询所有包含‘Amazon’关键词的链路”这样的大规模全文本检索。

传统数据库难以同时高效处理这两者。我们引入了基于 Rust 编写的 **Tantivy**（一个开源的全文搜索框架，类似于 Apache Lucene 的 Rust 实现），并将其与 SQL 结合，实现了在海量半结构化数据上的快速索引与筛选。在代理观测中，处理这些文本属性的需求是压倒性的，这与传统观测场景完全不同。

<details>
<summary>Original English Source</summary>
Agent traces are really nasty. They're nasty because they're highly semi-structured. Even within those semi-structured, there's a ton of unstructured text data that we need to chew through. They're voluminous, so an agent trace could be over a gigabyte in size. We've seen that. Even with our own customers, an individual span can be 20 megabytes in size. So, it's just a far different systems problem that you have to solve in order to ingest, process, and most importantly use that type of data.

And also, it's just as fast as traditional observability data. Hopefully, your agent that you're putting in production gets product market fit, and you have a ton of users and usage associated with it. You, as the AI engineer or as the product manager for that agent, you're going to want to see that observability in real time. Tough to do when the agent traces look like this. Not only does it have a bunch of spans here, encompassing the model calls and tool calls, but even within those spans, you saw the amount of unstructured text that's in there as well.

At Braintrust, we designed a database from the ground up specifically for agent traces. We need to immediately get data into a write-ahead log so that people can instantly see these traces as soon as they expect. We need to be able to perform indexing on these data so that whenever someone is performing a filtering or analytical query, that it's fast. And we have this thing called a Tantivy index. Tantivy is how we perform text-style indexing. So if you remember when I was showing this trace, it makes so much sense for someone to want to perform the workflow of, "I just want to know every trace that had the word 'Amazon' into it." Well, it turns out it's really hard to do that unless you perform a full text-based index across your traces. That's another reason why agent observability is far different than traditional observability. You really don't have to think about the text problems in traditional observability.
</details>

### 人员角色重构与进化方向

传统观测通常面向技术人员（系统工程师或产品工程师），他们关注的是系统的稳定性。但在代理观测领域，最佳团队是由**技术人员与非技术人员（领域专家）组成的**。

非技术人员，例如医师、法律顾问、财富规划师，他们离用户更近，离问题空间更近。他们能够直接参与到代理的质量提升中，通过自然语言编写提示词，并评估代理的行为。在我们的平台上，我们看到这些专家们仔细审阅链路，并利用这些洞察来改进代理。这种工作流在只关注可用性的传统观测中是无法实现的。

展望未来，我们正在利用 AI 自身来优化这个过程：
*   **闭环优化**: 我们发现观测（Observability）与评估（Evals）其实是同一个问题。评估是在批量环境中进行，且已知输入；观测是在实时生产环境中进行。
*   **自动化洞察**: 我们最近在 SaaS 产品中引入了在追踪数据上运行轻量级 LLM 的功能，通过嵌入（Embedding）和聚类（Clustering）来实现**话题建模**（Topic Modeling）。通过这种方式，我们能自动识别用户的意图、情绪，以及潜在的问题点。

整个理念非常直接：缩短生产中发现问题到实验和修复的迭代周期，让这一过程更加快速、直观。

<details>
<summary>Original English Source</summary>
Whereas there's a very specific type of persona for traditional observability—systems engineer, product engineer—it's very technical people that align with traditional observability. That could not be further from the truth for agent observability if you're doing it well. We notice that the best teams that are building agents have both technical and non-technical people in the fold performing this work because it's the non-technical people that are either closest to the users or have knowledge that is closest to the problem space.

And what can they do now with prompts? They can write it in natural language. So, they can add real value into being able to participate in agents. We have folks that are clinicians or registered nurses or wealth advisors or lawyers. We have seen them operate in our platform looking through traces and using that information to improve their agents. That is a workflow that you simply don't see in traditional observability where you're more worried about uptime.

I think in general people don't realize that in order to perform observability and also evals well, we kind of think of observability and evals as the same problem. The only difference between evals is that you're running them in batch and you know the inputs ahead of time. Observability and evals to us, it's like we solve it with the same system.

This is something that we are starting to do. We just rolled it out I think about a month ago in our software as a service offering where we see agent observability traces come in and then we'll run like a very lightweight LLM on top of them to perform embedding and then clustering on those traces to see how we can perform like elevate topic modeling to see for example how people are using your traces, their intent, how people are feeling about interacting with your agent, the sentiment, or if they're running into issues what those issues potentially are. The whole idea there is that you can make the iteration loop between a problem that you're seeing in production and the fix that you perform experimentation on. Whole idea is to just make that faster and a little bit more direct.
</details>