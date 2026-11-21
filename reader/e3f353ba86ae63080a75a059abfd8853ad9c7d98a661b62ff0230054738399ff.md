---
author: AI Engineer
date: '2026-10-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=XPj3mIKEtI4
speaker: AI Engineer
tags:
  - agent-memory
  - knowledge-graph
  - skill-distillation
  - context-graph
  - reasoning-trace
title: 将智能体记忆转化为可执行技能：基于 Neo4j 上下文图谱的架构演进
summary: Neo4j 产品经理 Will Lyon 剖析了传统 AI 智能体“失忆循环”与纯向量检索的局限，提出由短期、长期与推理记忆构成的上下文图谱体系。进一步结合 APE 协议与 NAMS 服务，展示如何将沉淀的交互轨迹确定性地蒸馏为类型化、可调试、版本可控的 Agent Skills。
insight: ''
draft: true
series: ''
category: ai-memory
area: PAI
project: []
people: []
companies_orgs:
  - Neo4j
  - Anthropic
products_models:
  - NAMS
media_books: []
status: evergreen
---
### 走出失忆循环：从向量检索到上下文图谱

在当前智能体架构的讨论中，**ReAct 循环**（Reasoning and Acting Loop: 智能体结合推理与行动的迭代循环）是高频出现的概念，但智能体系统在现实中往往陷入一种“失忆循环”：智能体历经推理与工具调用并成功完成任务，事后却无法积累和复用经验。当前的智能体记忆系统多聚焦于**文本嵌入向量**（Text Embeddings）与相似度匹配，仅仅从语料库中检索相关片段塞入上下文窗口，寄希望于模型自行理解。然而，单纯的文本检索并不等同于**可执行知识**（Actionable Knowledge）。

当缺乏统一实体规范时，系统极易出现指代混乱，例如在不同语境下对“Nguyen 医生”存在“Robert N.”、“心脏病专家”等多种表述。智能体真正需要的是具备**一致性**（Coherent）、**类型化**（Typed）且**可追溯**（Traceable）的知识体系。基于图数据库的**上下文图谱**（Context Graph: 以图结构整合异构交互与实体关系的语义网络）正是为此设计的架构底座。构建过程首先完成非结构化文本向知识图谱的转换，将用户与助手对话通过**实体提取与消歧**（Entity Extraction & Disambiguation）转化为强类型节点与关系；借助统一的**共享本体**（Shared Ontology: 领域概念与关系的规范化数据模型定义），确保现实对象具备唯一的规范化表达。

<details>
<summary>Original English Source</summary>

Let's get started. I see that some people want to join, so please come in. This session will be dedicated to actionable knowledge and context graphs. So, my name is Will. I am a product manager at Neo4j. Em. There's been a lot of talk about cycles at this conference, hasn't there? React loops, ReAct loops. Sometimes I feel like we're in some kind of amnesia cycle, right? When our agents go through the reasoning phase, they act, successfully complete the task, but then they seem to forget what they learned. Today's memory systems are mostly focused on embedding text, and during retrieval, on finding the most relevant data to insert into context, right? Um, something like this. We find similar pieces of data in our corpus, insert them into a context window, and hope that the agent can do something useful with it, right? The problem is that remembering is not exactly actionable knowledge. One of the challenges we face is, for example, the lack of a canonical representation of an object. If we have three different ways to address Dr. Nguyen: Robert N., cardiologist, correct? Depending on the context of the discussion, we need to have some canonical representation of the object. In fact, agents need knowledge that is coherent, typed, and traceable. Not just ones that can be obtained. Search is only part of the problem when we talk about agent memory. So, in Neo4j, we see agent memory like this. We view it as a connected graph consisting of short-term, long-term, and logical memory. We'll look at this in a little more detail. But be patient with this idea of context graphs for agent memory, okay? What are the main components here? Well, first, it's a transition from unstructured data to a knowledge graph. Moving from the process... agent messages, right? Both user and assistant messages go through an entity extraction process where we determine what these entities are and how they are related. Doing this in a graph where we have clear types, right? We have a relationship that describes how these entities interact with each other. The entity recognition phase is one of the most important parts of building this knowledge graph, right? Understanding and ensuring that you have a canonical representation of an object. So when we talk about Dr. Nguyen, we know who the provider is, his name, his role, etc. And a shared ontology is an important part of that, right? That is, having a certain description of your data model, the domain you are working with. This is one of the key elements that ensures a successful transition from unstructured text data to a knowledge graph. So for those who have worked with agent memory before, this should look a little familiar.

</details>

### 推理图谱与跨智能体共享决策沉淀

在明确了实体层面的图谱建模之后，智能体记忆的核心更在于捕获动态的**推理记忆**（Reasoning Memory: 记录决策逻辑、执行轨迹与策略依据的记忆分支）。系统的全局记忆由短期记忆、长期记忆以及推理记忆三部分紧密交织而成。常规的短期与长期记忆仅负责保存消息与抽取实体，而智能体执行动作的过程与思考链路本身才是高价值资产。图谱不仅要保存数据事实，更必须记录**决策追踪轨迹**（Decision-Making Trail: 智能体选择特定路径的证据链与工具执行流）。

在实际建模中，智能体的每一次决策都对应着**证据推理**（Evidence-Based Reasoning）。系统显式定义策略约束，记录执行计划全貌，涵盖调用的工具类型、入参及返回结果，并关联记录消耗的 Token 数、执行耗时等元数据。当组织内存在成百上千个共享工具集的智能体时，将决策轨迹沉淀到统一的图谱中，就能构建出跨智能体的协同记忆底座。一个智能体的成功探索经验能够直接被其他智能体读取与借鉴，使知识沉淀突破单会话局限。

<details>
<summary>Original English Source</summary>

One thing that I think is really important when we talk about agent memory and real knowledge is the idea of a reasoning graph, right? If we've seen our three components of agent memory, reasoning memory is the primary one here, right? We talked about short-term and long-term memory. These are the messages, the entities extracted, but what about the actual actions the agent performs? What about the reasoning process itself? We want to make sure we capture that because it's an important part as well. So, we want to make sure we're preserving the thinking and the facts, not just the data itself, right? That is, how exactly the agent made the decision. And that's usually represented as a decision-making trail, right? So every decision our agent makes involves evidence-based reasoning, right? We have policies that we model explicitly, and we understand the execution plan: the tools that the agent called, and the results of those calls. We also want to record things like the number of tokens spent, execution time, etc. This is all part of fixing the memory of reasoning. And this is important not only so that one agent can perform better the next time they do the same task, but also for systems where you have hundreds or thousands of agents sharing a common set of tools, right? So we can store these agent runs, these decision traces in a graph, and then share them with other agents in our organization, right? Thus, we have one shared context graph that allows our agents to learn from each other through this shared memory element. Okay, that's the thing about memory. This is, in fact, the system we built in Neo4j. A template that many follow for working with agent memory.

</details>

### APE 协议：将非结构化技能重塑为类型化执行图

拥有完整的记忆轨迹后，更关键的跃迁在于将反思记录转化为**可执行技能**（Agent Skills）。当前业界通常采用类似 **Anthropic** 推出的开源标准（如 agentskills.io），通过元数据与 Markdown 文件实现**信息渐进式披露**（Progressive Disclosure: 根据执行阶段按需检索并加载详细指南以节省上下文窗口）。然而，传统的纯文本或 Markdown 技能面临着与传统记忆相同的缺陷：非结构化散文描述难以验证实体规范性，执行步骤黑盒化且缺乏可调试性。

为了让技能具备确定性与可控性，**Neo4j** 研究团队提出了 **APE 协议**（Agent Process Execution: 将智能体技能建模为带严格模式的类型化有向图表示法）。APE 扩展了原有的技能规范，将每个操作步骤建模为图节点，并由严格的 Schema 规范步骤间的状态流转与约束。在基准评测 **Skills Bench** 中，采用 APE 结构化表示的技能在任务完成率上相较传统形式取得了显著提升。这使得技能不仅具备可解释性与确定性，还能够依据图结构进行断点调试与自动化校验。

<details>
<summary>Original English Source</summary>

But what about the idea of practical knowledge, huh? How do we allow our agents to act? Memory, one way of thinking about memory is that it's a beautiful reflection of what happened, right? We know the people we were talking about and how they are connected. We have these traces of decisions. The next step is usually skill building, right? How many people use skills with their agents today? Most of them are cool. How many people wrote these skills themselves? Cool, most of them. How many people have asked an agent to write a skill for them? Steeply. So, that's what we're talking about here: how to move from this memory graph, this context graph, to how to use it to create grounded and actionable skills. So, if you're not familiar with the concept of a skill, it's an open standard. Anthropic released it. Agentskills.io seems to be where this open standard is hosted. The main idea here is that we have some metadata, right? Some description of what this skill is about. And then it's a gradual disclosure of information, right? That is, I have a lot more detailed information. These are often files in markdown format, links that we can gradually select, if we go through the process of performing part of the skill, we can retrieve and load this data into the context. So this gives us common units that we can take, package the skill, and reuse across different agents. But skills have a similar problem to what we saw earlier when we talked about memory. Namely, that we usually work with prose. And so we're still limited in understanding whether this is a canonical object and in providing debuggable steps and results. So, to solve these skills problems, some of the Neo4j research team did some interesting research and published a paper on APE—a graphical representation for training and managing agent skills. This is a screenshot from the article. Zach is here somewhere. If it's not here, it's at the Neo4j booth today, so be sure to chat with Zach if you're interested, but you can think of APE as an extension of the agent skills protocol with additional metadata, which now treats your skills as typed execution graphs, right? So we have steps modeled as nodes, and we have a very strict scheme that governs the description of how these steps become actionable. Yes? So, think of it as a way of representing a skill as a graph, broken down into steps that are performed using a schema that governs the description. This is the APE protocol, and according to the benchmark used in the article, it really makes a difference: when applied to Skills Bench, we saw a significant increase in the number of tasks completed when using the APE protocol for human-selected skills.

</details>

### 从图谱蒸馏技能与生命周期动态治理

基于上述理论支撑，系统能够直接从工作区或项目的上下文图谱中提炼出经过现实检验的高可靠技能。这一过程称为**技能蒸馏**（Skill Distillation: 从累积的交互子图与决策轨迹中提炼出可复用程序性技能的确定性流水线）。蒸馏产物并非主观臆断的文本，而是以真实发生的执行数据为**依据支撑**（Grounded Justification），具备完全确定性的流程步骤。在技能治理层面，系统通过图算法持续监控两项关键指标：
- **覆盖度**（Coverage）：验证蒸馏出的步骤与约束定义是否在整个技能执行链路上完全自洽且闭环。
- **内聚度**（Coherence）：利用图上的**社区发现算法**（Community Detection: 识别子图中紧密相连的聚类结构）分析输入子图。若检测到混合了多个异构主题社区，系统将自动建议进行解耦拆分，将其拆解为多个专注单一职责的微技能。

更为重要的是技能的**生命周期管理**（Skill Lifecycle Management）。由于技能节点直接锚定在底层的记忆图谱实体上，一旦现实业务数据、底层依赖关系发生变更或删除，后台监控进程能精确感知依赖失效，标记技能进入陈旧过期状态，从而通过动态加载机制确保智能体技能库始终保真可用。

<details>
<summary>Original English Source</summary>

So, this looks interesting. How can we use some of these ideas and research to distill skills? Essentially, we want to take this memory graph, this context graph, which may be limited to a workspace or a project in an organization, and distill it into a skill, but not just as a markdown file. We want it to be based on real data that we have observed. We want it to be deterministic, right? We want to have well-understood procedural steps in our graph and we want to be able to manage it over time, right? If the underlying data that shapes our skill changes in memory, we want to be able to understand it and know about it. Justification is the important part here, right? Making sure that the data that makes up our skill is based on our memory system, but that's not enough for it to be useful, right? There are other heuristics that we should pay attention to. For example, coverage: do we make sure that the steps and descriptions throughout our skill are valid within the entire skill. Coherence. Coherence is interesting. This is a way we can detect whether the information or subgraph coming into the skill distillation is divided into multiple topics, and we can suggest: maybe you should create multiple skills here, and so on. So, these are some of the elements that lead to skill generation. Skill management is an important aspect that I mentioned, making sure that we can understand: as the skill changes, as the data changes, are we able to update that skill? And thanks to dynamic loading, you can think of it as a managed skills inventory, which allows us to get the most relevant skills for any agent and understand whether they are outdated or have lost their relevance, right? Steeply.

</details>

### NAMS 架构落地：七阶段流水线与临床场景实践

为了将上述模式工程化落地，Neo4j Labs 推出了 **NAMS**（Neural Agent Memory Service: 面向智能体的图记忆与技能治理服务平台）。该服务对外提供 REST API 与 **MCP 工具**（Model Context Protocol: 用于连接智能体与外部工具及上下文的标准化协议），支持智能体写入与检索引擎中的短期、长期与推理记忆。服务内部运行着一套严格的七阶段确定性流水线，大语言模型仅在必要阶段负责描述语句的提炼与合成，其余拓扑构建与验证皆保持确定性。

流水线的第一步是**作用域界定**（Scoping: 指定蒸馏输入边界），用户既可以针对整个工作空间进行蒸馏，也可以精准圈定特定实体、特定会话，或是领域本体中的特定类别。以医疗门诊场景为例，智能体加载医疗领域本体处理医患就诊对话。系统首先完成实体消歧与关系入图，随后蒸馏引擎捕获门诊过程中的全部工具调用（如挂号接诊、体格检查记录、病历归档），将每个环节锚定在真实发生的调用日志与实体之上，自动打包生成遵循渐进式披露规范的标准 `SKILL.md` 及其引用资源包。整套体系展示了如何利用图谱消除幻觉、保留认知资产，从而赋能具备持续学习能力的智能体网络。

<details>
<summary>Original English Source</summary>

So, we implemented this in the Neo4j Agent Memory Service, or as we call it, NAMS. This is a memory service for agents that is part of our development at Neo4j Labs. We also have open source tools that implement these patterns. Essentially, it works like this: we have a context graph within the workspace, right? It contains three types of agent memory: short-term, long-term, and reasoning memory. We have background processes capable of performing this distillation process. We'll see what that looks like in a minute. We also have a background creation process that provides control to detect when our skills become obsolete based on the data contained in the memory system. This is the pipeline we use to create them. I won't go into detail on this. The only thing we want to point out here is that most of these steps are deterministic. We're really only using LLM here to synthesize some statements and generate some of the text that we use to describe skills. And one more thing I want to point out: the first stage is scoping. That is, where do you start distilling one of these skills? Is it related to a specific entity, or to the subgraph around it? Is this a specific conversation? Well, that's another thing. So we can decompose the way the skill is represented and make sure that each of these components is again based on the original data. This is exactly the point where we check if the skill becomes obsolete if any of this source data changes, is removed, or becomes inconsistent. Steeply. And then we can also, as I mentioned before, combine skills, right? This is where the principle of consistency comes in handy. We use graph algorithms like community detection, right? So if we are mixing topics from multiple communities, it could be a sign that we need to decompose our skill, and we will find this within skill management. Steeply. So, I have a few minutes left. Let's see what it looks like. So this is NAMS, the Neural Agent Memory Service. It is currently free. Anyone can log in and try it out. This is what the dashboard looks like. The basic idea is that we have a REST API and MCP tools that we can provide to our agents to write, retrieve, and work with long-term, short-term, and logical memory. We go through the process of entity extraction and recognition, so I can view a graphical representation of my agent's memory. I can navigate it, etc. We can see the entities that have been marked. An important part here is the concept of ontology. In this case, we use a medical ontology. We will work with data on visits, medical professionals, etc. I also uploaded a few conversations here. We can see the conversations that were uploaded regarding the medical agent, right? Now we are ready to highlight the skill. As we said, the first step is to determine the scope of this skill. We can do this for the entire workspace. Although this is not always what we need. We can do this for a specific entity, specific conversations, or a class in an ontology. Let's do this for our last conversation. We will see how the process begins in the distillation queue: the system will receive data, go through a seven-stage pipeline, form a skill in the form of a graph, and package it for us. While it works, here is one example. Let's just take a look at him. Here is the example we ran earlier. It was launched based on a conversation during a patient's appointment. As you can see, we have essentially highlighted the steps that make up a skill: from receiving a patient to filling out their medical record. We see that each of these steps is based on the actual tool calls and entities that form the core components of the skill, and we package this together with the skill file. MD. If we were to upload this, it would be packaged with other reference materials in accordance with the progressive disclosure standard we use for agent skills. Class. So, this was a quick overview of how we look at agent memory within this context graph with Neo4j, and I'll leave you with some useful links. The slides can be downloaded here. Here is a link to the slides and a QR code. The Neo4j agent memory service I mentioned is also listed here, along with a bunch of documentation and resources for our open source tools. So, that's all. I'm out of time, but we have a Neo4j booth. So I will be there, as will many others from the Neo4j team. See you there. Thank you all.

</details>