---
author: AI Engineer
date: '2026-05-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=B9h9ovW5H9U
speaker: AI Engineer
tags:
  - context-graph
  - decision-traces
  - graph-embeddings
  - agentic-workflow
  - graph-database
title: 超越文档检索：为什么 AI Agent 需要上下文图谱沉淀决策逻辑？
summary: 本文探讨了 Neo4j 提出的“上下文图谱”（Context Graph）概念，分析了其如何通过记录决策痕迹（Decision Traces）、因果链和先例，弥补传统 RAG 知识库在 Agent 决策场景下的不足。作者详细介绍了图嵌入技术在结构化匹配中的应用，并展示了如何利用自动化工具快速构建具备长期记忆与推理能力的 Agent 应用架构。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Neo4j
  - Foundation Capital
products_models:
  - Neo4j Graph Database
  - Graph Data Science
  - Pydantic AI
  - create-context-graph
  - Claude
media_books: []
status: evergreen
---
### 从 RAG 到上下文图谱：重构 AI Agent 的决策维度

在当前的 AI 生态中，**检索增强生成**（Retrieval-Augmented Generation: 通过外部知识库增强模型回答准确性的技术）已成为标配，但仅靠知识库（Knowledge Base）不足以让 AI Agent 做出高质量的决策。传统的 RAG 系统更像是“记录系统”，侧重于事实、实体和当前状态的查询。然而，真正的 **Agent 决策** 需要的是一种**推理系统**（System of Reasoning: 记录决策前因、因果链和预期结果的动态系统）。

Neo4j 提出的 **上下文图谱**（Context Graph）正是这一演进的核心。它不仅包含传统知识库中的信息，还记录了**决策痕迹**（Decision Traces）和历史先例。以金融分析 Agent 为例，传统的系统可能只能提供客户信息和风险评分；而上下文图谱则能告诉 Agent：在过去类似的情况下，为什么某个请求被拒绝了，当时的政策依据是什么，以及之前的决策者（无论是人类还是 AI）是如何推理的。这种图谱模型由三个关键维度构成：**实体**（关于存在的事物）、**事件**（决策、交易、审批）以及**上下文**（引导推理的政策与历史记忆）。

<details>
<summary>Original English Source</summary>

So, my name is Zach. Uh I work for Neo4j. We're a graph intelligence company. You can think of us like a knowledge layer graph database at the core. We help connect and resolve information so AI systems can be a little bit more accurate and explainable.
So, I'm going to talk to you today about context graphs. ... Basically we saw a lot of noise around this idea of creating decision traces and reasoning um to help agents make better decisions.
And so, to kind of think actually about what a context graph is, we need to ask ourselves, "Would you agents really be accurate?" Right? And so, um for one thing, doing a lot of retrieval, you're going to need a knowledge base, obviously. Um so, a knowledge base for something like rag or graph retrieval basically helps an agent or a chatbot answer questions correctly. What a context graph does in the evolution of this is really the information required to not only answer questions correctly, but make better decisions.
Um systems of record, really about facts, entities, current state, [Context graphs are] about precedents, causal chains, expected outcomes, and enabling the agent to act with subject matter expertise, um and telling the agent really [how to reason]. Um the entities, about things that exist, there'll be uh events, so decisions, transactions, approvals, things like that. And then context, policies that are um in different reasoning by AI that records memory, but um by employees and and past humans that have made decisions.

</details>

### 决策痕迹与结构化匹配：图嵌入技术在因果链中的应用

上下文图谱的强大之处在于它能实现**混合搜索**（Hybrid Search: 结合语义相似度与结构相似度的检索方式）。传统的向量检索主要依赖于文本语义的相似性，但在处理复杂的业务逻辑时，结构上的相似性往往更为重要。为了实现这一点，系统引入了 **图嵌入**（Graph Embedding: 将图中的节点及其连接结构映射为多维向量的技术）。

通过 **图数据科学**（Graph Data Science: 利用算法分析图结构特征的学科）工具，我们可以将决策痕迹及其关联的因果链转化为向量。这意味着当 Agent 处理一个新任务时，它不仅能搜索语义上相似的文档，还能在向量空间中寻找“结构相似”的历史决策路径。这种技术能够敏锐地捕捉到跨系统的关联信息，例如从 CRM 到支持系统的跨维度数据。通过这种方式，Agent 能够找到**先例**（Precedents），并基于历史的成功或失败经验给出最终的建议，从而显著提升决策的可解释性与专业深度。

<details>
<summary>Original English Source</summary>

Then it does this thing called find precedents, which is going to be more in a second, but it's going to look at structural information in the graph to pull a bunch of [data]. ... connect to each other in these causal chains. So, you build off of each other.
Then we did a special of hybrid search, especially around those precedents, both on semantic similarity and structural similarity inside of the graph that actually looked at how the decision traces were made um from previous decisions, and it tried to match that, and I'll talk a little bit about how that works with graph embeddings in the next slide to ultimately come up with the recommendation.
And so, we have a we have a vector index, so we're able to search like fraud rejection, for example, sort of on the semantics. But then we have this concept called graph embedding. ... A graph embedding is the same concept except those green nodes that I was showing you before everything was connected. We actually embedded those into a vector. And so, what that means is similar decision traces are now going to be able to be looked up by vector similarity.
Um GDS is called graph data science. That's what we use for the uh for the graph embeddings themselves.

</details>

### 自动化工程实践：一键构建具备推理能力的 Agent 架构

为了降低开发者构建上下文图谱的门槛，Neo4j 推出了 `create-context-graph` 工具。这类似于前端开发的 `create-react-app`，开发者只需在终端执行一行 **UVX** 命令，即可快速初始化包含前后端、图数据库骨架及 Agent 框架（如 **Pydantic AI** 或 **LangGraph**）的完整堆栈。该工具支持 22 个内置领域（如金融服务、医疗保健等），并能根据用户定义的**本体论**（Ontology: 定义实体类型及其相互关系的图谱模式）自动生成图谱 Schema。

在底层架构上，这套系统依赖于 `Neo4j agent memory` 软件包，它为 Agent 提供了完整的记忆 API。这个 API 涵盖了三个关键层面：
1. **短期记忆**：记录对话历史和会话上下文。
2. **长期记忆**：从对话中提取并随时间沉淀的实体信息。
3. **推理能力**：在上下文图谱中形成的决策痕迹。
此外，系统内置了精细的**文本转图谱**（Text-to-Graph）流水线，通过 spaCy、gliner 等工具进行**命名实体识别**（Named Entity Recognition: 识别文本中人名、地名、组织机构等实体的技术），并配合 LLM 降级方案和合并去重策略，确保短期的零散信息能平滑转化为高质量的长期知识沉淀。

<details>
<summary>Original English Source</summary>

But what I really wanted to show you today um was another tool that was just recently created a little month ago, um which allows you to create a full um stack application to start with with just a one-line command in the terminal to actually create the context graph and the front end and the back end. ... Basically you can think about this like um create React app or create Next app, like you basically get this boilerplate.
There's just a UVX command, UVX create context graph, um specify the name of the app, the domain, um the framework I want to use. ... It'll give you um you know data inside of a graph and then um you know, you can go ahead and ask questions um and it will go and and you know, basically do this type of retrieval with Cypher and and everything else. Cypher's a graph query language um to pull data back.
Underpinning this, one of the big dependencies is our Neo4j agent memory package. Um so, this is a complete memory API. Uh it includes and context graphs really need all three of these things. Um a short-term memory, a long-term memory and reasoning. ... So, here uh we actually implemented this inside of the package. Um where it goes through a few different stages on raw text. ... stages where you go from spaCy to gliner and and more advanced to an LLM fallback. Um and then there's a separate merging, deduplication, and enrichment strategy.

</details>