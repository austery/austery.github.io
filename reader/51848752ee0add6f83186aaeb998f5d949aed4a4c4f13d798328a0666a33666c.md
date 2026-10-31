---
author: AI Engineer
date: '2026-10-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DrfyORO8RqA
speaker: AI Engineer
tags:
  - context-engineering
  - agentic-architecture
  - memory-management
  - llm-reasoning
title: 为什么更大的上下文窗口拯救不了你的 Agent：上下文工程与记忆架构实战
summary: 随着 Agent 频繁调用工具产生海量数据，单纯依赖大上下文窗口会导致迷失在中间、推理退化与成本失控。来自 AWS 的 Elizabeth 结合开源框架 Strands，系统性阐述了对话管理、多级记忆架构、内存指针与异步解耦等核心上下文工程策略。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Elizabeth Fuentes Leone
companies_orgs:
  - Amazon Web Services
products_models:
  - Amazon Bedrock
  - Strands
  - Neo4j
media_books: []
status: evergreen
---
### 认知重塑：无限上下文窗口的工程幻象

在大模型 Agent 系统的实际落地中，“无限上下文窗口能够解决一切记忆与推理问题”是一个广泛存在的误解。大约一年前，在 Agent 架构尚未全面爆发的早期阶段，行业普遍认为只要模型原生支持的上下文窗口（Context Window）足够大、Token 容量足够多，所有长期交互问题都将迎刃而解。然而现实表明，当 Agent 系统频繁调用工具（Tools）时，外部数据源往往会返回极其庞大的数据载荷；一旦上下文窗口被这些未经提炼的信息直接填满甚至溢出，Agent 就会迅速出现幻觉，其逻辑推理能力也会呈断崖式下滑。

导致这一退化的底层机理在于大语言模型的**注意力曲线缺陷**（Attention Curve: 模型在处理超长文本时呈现出的两端关注、中间丢失的“迷失在中间”现象）。当上下文窗口中注入的数据量过大时，底层推理引擎往往只能较好地回忆起输入起始端（System Prompt 及初始设定）和末尾端（最新的交互输入）的信息，而位于上下文窗口中间位置的大量实质性细节则会被模型忽略。此外，过度臃肿的上下文还会增加 Prompt 注入攻击的风险，并带来高昂的计算成本与推理延迟。因此，构建现代 Agent 系统的核心在于**上下文工程**（Context Engineering: 在正确的时机为模型精准提供其执行当前任务所必需的最小充足信息），通过主动的数据分流与窗口优化，在保障推理精度的同时最大化节约系统成本。

<details>
<summary>Original English Source</summary>

Greetings. First, I must say, I am Elizabeth, not Morgan, but on the agenda they never changed it. So we are almost the same, only hair color is different, okay? So everything will be similar. Today I will tell you about why infinite context window is a misconception. Yes, this is because right now agent systems break when tools return large amounts of data. The context window overflows, the agent starts hallucinating, and its reasoning capabilities get worse and worse.

So now context engineering helps us build a better future for these agentic architectures. We have some methods that allow improving the context in the window for these agent applications. Imagine you have an agent monitoring a program, and this agent must extract logs from that project. Every time the agent receives those logs, it adds that data into the context window. Each time, this context window is growing and growing continuously, because in a session every request pulls in the previous ones since the agent has to remember everything.

Earlier, about a year ago before the agent era, we thought more tokens would fix everything. They said a bigger context window would solve the problem. But today we know that is not true because of the model's attention curve. What is this? We have a large amount of data, but if there is too much, the engine forgets the middle position of this curve. It only remembers the beginning and the end of what we sent in the context window.

Context engineering is about providing a model with the necessary information exactly when it needs it. Sometimes it is unnecessary for the model to have all information included in the context window. Sometimes an overflowing context window hurts the model because it can accept prompt injections. Context engineering helps optimize the window for best background results and saves costs.

</details>

### 上下文管理策略：基于 Strands 框架的轻量化循环

为了系统性治理上下文膨胀，工程上通常需要将治理手段收敛为三大核心抓手：**外部存储与指针化**（将海量原始数据持久化至上下文之外，仅在提示词中保留引用指针）、**相关性选择与压缩**（仅提取当前决策最关键的上下文切片，对冗余内容进行摘要）、以及**上下文隔离**（避免多步骤或多 Agent 间无序共享脏上下文）。在具体工程落地中，我们可以首先从对话管理器（Conversation Manager）的会话控制策略切入。

在具体实践中，以开源且模型无关的 Agent 框架 **Strands**（Strands: 一种仅需极简代码即可自动构建 Agent 内部工作流循环与工具调用的开源框架）为例，该框架内置了针对上下文窗口的三种标准对话收缩策略：
* **滑动窗口策略**（Sliding Window）：仅截取并保留会话序列中最新鲜的几轮消息，直接丢弃超出的历史上下文。
* **增量摘要策略**（Summarization）：在框架内部对早期陈旧的历史交互进行语义归纳与摘要提炼，仅全量保留最近的少数交互轮次。
* **混合压缩策略**（Hybrid Retention & Summarization）：设定特定的总结比例系数（例如 50% 压缩率），动态保留最近的 4 条原始对话，同时将前序累积的上下文压缩合并为结构化摘要。

开发者在代码层面通常只需编写一行声明代码，框架即可在底层自动驱动 Agent 循环、系统提示词拼接与工具绑定，并无缝适配 **Amazon Bedrock**、OpenAI、Gemini 或本地 Ollama 等多种后端模型。

<details>
<summary>Original English Source</summary>

Today I will show you several methods that will help improve the use of context windows. I merged these methods into strategies: First, we use external storage to move big data to permanent storage, and you can create memory pointers to store this data. Second is selection: you pull out only what is relevant, squeeze and reduce tokens by summarizing, and return that info. And the last is isolation: you can separate context between agents.

Let us start with the conversation manager strategy. We have many strategies, but let us start simple inside a framework. Here we will use the agent framework Strands. It is an open-source framework we support, free and completely model-agnostic.

Inside Strands, you can use three different strategies:
1. Sliding window, which allows storing only the latest information.
2. Summarization inside the framework, allowing you to generalize older information while keeping the last few messages.
3. A combination of the previous two, merging the summary of older things with the last few messages.

With Strands, you only need one line of code to create a working agent loop. That line creates the entire workflow behind the scenes. You do not need to create nodes or count tokens manually, because Strands does that for you with system prompts and tools. It uses Amazon Bedrock under the hood, but if you want to use Ollama, Gemini, or OpenAI, you just add one line to import and switch the model.

Returning to our conversation manager strategy: you can specify a summarization ratio, such as 50%, and specify that you want to preserve the last four messages. Every time you invoke this agent in the session, it will maintain your context window this way: preserving the latest four messages and summarizing the remaining 50%.

</details>

### 多层级记忆工程：短期、长期与图关系的系统闭环

当 Agent 面临更加复杂的工作流时，简单的对话窗口截断会带来信息丢失的隐患。为了兼顾上下文的精简与系统记忆的完整性，必须构建分层的记忆体系。记忆架构在工程上主要解构为三个互补维度：
* **短期记忆**（Short-term Memory）：专属于当前会话生命周期，精准保存最近对话上下文和局部工作状态，通常结合上述滑动窗口与摘要机制进行在窗维护。
* **长期记忆**（Long-term Memory）：当用户开启新会话或需要跨周期检索时，短期记忆被持久化写入**向量数据库**（Vector Database）。系统利用特定的嵌入与提示词结构，在后续对话中根据语义相似度按需召回所需知识。
* **关系图谱记忆**（Graph Memory: 实体间复杂拓扑与跨维度依赖的网络化表达）：针对多实体关联、复杂业务依赖或跨流程实体脉络，引入图数据库（如 **Neo4j**），通过图遍历（Graph Traversal）精准追踪实体间的关联与引用。

在健壮的生产级 Agent 架构中，推荐采用这三者的融合模式：利用短期记忆处理当前交互上下文，利用长期向量数据库调取跨会话经验，并通过关系图谱快速厘清复杂依赖关系，从而彻底摆脱“将所有历史记忆一股脑塞入上下文窗口”的粗放模式。

<details>
<summary>Original English Source</summary>

What should you do when you have a lot of memory and you do not want to lose everything in the context window?
You can use short-term memory, because it preserves recent conversational history in the current session. You can use the summarization and sliding functions I just mentioned for short-term memory.

But what happens when you start a new session with the agent and do not have that short-term memory? You can have long-term memory and create a vector database for it. You can have different types of vector databases and retrieval prompts that understand your conversation and save everything you need.

And the third type is relational memory. You can use graph entities—you can look into Neo4j manuals for more details. You can perform graph traversals and link connections.

As you can see, you can use a combination of all three:
- Use short-term memory for the current session.
- Access long-term memory for past historical records.
- Add graph memory if you have entity connections you want to preserve.

</details>

### 数据解耦与内存指针：治理重载工具返回

在系统监控、代码审查或运维排障场景中，Agent 调用的诊断工具往往会返回动辄数万行的应用系统日志。如果 Agent 直接将这些裸日志写入上下文窗口，窗口会被瞬时击穿。解决此类高负载数据交互的标准模式是**内存指针机制**（Memory Pointer: 在外部持久化沉淀重载载荷，仅向上下文窗口传递唯一轻量标识符的设计模式）。

其核心交互闭环由以下组件协同实现：
1. **数据捕获与落地**：当下游工具检索出海量日志时，工具内部将完整数据转存至外部独立存储系统（如 S3 或专用状态存储），并仅返回一个轻量级的记录唯一标识符（Identifier）。
2. **上下文隔离**：Agent 的上下文窗口中仅记录状态标记与轻量指针（Pointer），极大地降低 Token 开销并保护模型注意力。
3. **按需代理查询**：当 Agent 确实需要理解或比对部分日志时，它无需读取全文，而是通过专门构建的下游辅助工具传递该标识符，并提出具体问题（例如：“针对该任务标识符对应的日志，请检查第 42 行附近的错误码”），由下游模块负责切片并返回高度精炼的结论。

当业务复杂度进一步上升、单个 Agent 难以兼顾多重职责时，应推进**多智能体蜂群架构**（Multi-Agent Swarm）。各子 Agent 拥有完全独立的上下文窗口，避免因“上下文公用”而导致无关业务垃圾互相污染；子 Agent 之间仅通过共享调用状态指针（Call State Point）与数据标识符实现协作协同，保持个体上下文的高纯度。

<details>
<summary>Original English Source</summary>

What should you do if your project generates huge volumes of logs? You don't want to put all these raw logs into the context window every time you call the agent. You can save this using indexed memory and memory pointers.

How does it work? You have a tool that returns a bunch of logs. You use that tool to fetch logs, save them into external storage, and return an identifier for that entry. Using the agent's state condition, you store that identifier as a memory pointer in the context window. Then you can use another tool that can understand those logs by passing messages like: "Hey, what happened in the logs for this identifier?" You don't need the agent to see all raw records to understand the situation.

If inspecting everything is strictly necessary, you pass the identifier: "Here is my identifier, please inspect these logs because I need to understand them." In code, inside the agent, you build this architecture using tool decorators. You receive program logs, capture the info, save it, and create an identifier memory pointer stored in the context window.

If your application is too complex and one tool is not enough, you can use a multi-agent swarm architecture. You create multiple agent instances and split their context windows. You isolate contexts so one agent's garbage doesn't pollute another, because agents don't need all shared information between them. You share state via call state pointers and identifiers across the agent swarm.

</details>

### 鲁棒性与异步调用：突破死循环与网关超时

除了数据载荷本身的体积管理，Agent 调用的行为链路同样对上下文窗口的稳定性具有决定性影响。在生产实践中，最常出现的两个工程痛点是**工具无限递归死循环**与**外部 API 网关超时阻断**。

针对死循环问题，当工具返回的响应模糊或未直接命中终止条件时，Agent 极易陷入无休止的重复工具调用循环，短时间内即可耗尽上下文 Token 与调用配额。有效的防御策略包括：
* **显式返回契约**：工具的输出必须具有确定性与结构化结论，避免输出引起 Agent 歧义的发散文本。
* **严格调用频次熔断**：为每项工具（例如航班查询或订单检索）设置硬性单任务最大调用上限（Max Invocation Limits，如最多允许调用 3 次）。一旦达到上限立即强制熔断，防止上下文被死循环日志塞满。

针对外部 API 延迟，当 Agent 接入 **MCP**（Model Context Protocol: 开放模型上下文协议）工具或高耗时第三方服务时，由于 AWS API Gateway 等云端网关通常存在严格的连接超时限制（例如 29 秒超时），若采用同步等待模式，长任务极易导致整个执行链路异常中断并丢失会话。应对方案在于全面采用**异步轮询解耦架构**（Asynchronous Task Pattern）：
* **任务发起**：通过 FastAPI 等框架定义异步任务触发工具，Agent 发起长耗时任务后立即获得任务标识并退出当前等待状态。
* **状态轮询**：提供独立的状态检查工具，Agent 可以在后续轮次或异步回调中根据任务 ID 检查执行状态并取回处理结果，从而彻底解耦等待延迟并保护会话上下文的完整性。

<details>
<summary>Original English Source</summary>

Next: what happens when an agent does not want to stop? Sometimes an agent gets trapped in an infinite loop, invoking the same tool again and again, never ending. You can prevent this by placing hard limits on loop calls. When a tool doesn't provide a clear answer, the agent keeps calling. You avoid this by providing explicit answers from tools and limiting the maximum number of tool calls—for instance, allowing a flight search tool to be called at most three times. Once limited, it will never execute that inner infinite loop.

Lastly, how to handle external integrations: sometimes we call MCP tools or external APIs with long response times. In AWS API Gateway, there is a maximum timeout waiting for a response. If your program doesn't respond within that time, it halts with latency errors. You can avoid this using asynchronous methods.

In synchronous calls, your runtime waits forever for the MCP response. With asynchronous handlers, you call your external API/MCP, save the task status, and retrieve the result during a subsequent call. For example, using FastAPI you create two tools: one to start the long-running task, and another to verify task status. This asynchronous pattern makes a huge difference; otherwise, while waiting, the agent stops responding and cannot fetch information.

</details>

### 上下文工程的生产级设计法则

总结构建企业级高可靠 Agent 系统的最佳实践，工程团队应严格践行以下核心守则，在架构设计阶段即遏制上下文溢出：

1. **坚持最小充足原则（Min-Context Rule）**：绝对不要盲目将全量数据塞入上下文窗口。严格过滤与当前推理无关的冗余字段，仅向 Agent 喂入生成下一步决策所需的最小必要信息。
2. **警惕过度泛化与摘要丢失（Selective Summarization）**：内置自动摘要机制在缩减上下文的同时，可能会抹去关键的技术参数与事实细节。必须在架构层面区分状态性元数据与临时性闲聊，避免关键指令在无差别摘要中丢失。
3. **推行外部指针化与数据解耦（External Pointerization）**：面对数据库查询、报表或海量日志等重载数据源，坚决推行“外置存储 + 内存指针”模式，仅在 Prompt 中传递引用句柄，由专用分析工具按需解析。
4. **实施工具执行约束与异步解耦（Execution Guardrails）**：为所有工具配置严格的并发限流与单会话最大调用阈值；对耗时超过 5 秒的长任务全面采用异步任务提交与状态轮询机制，确保 Agent 会话主循环免受网关超时与同步阻塞的冲击。

<details>
<summary>Original English Source</summary>

So, what should you avoid?
- Avoid context overflow. Do not include everything there. It is not worth adding everything to the context window because the agent does not need all that information. Only provide what the agent needs to create the response.
- Be careful with built-in summarization: sometimes when summarizing, the agent might forget necessary details. If you summarize blindly, you might lose things required for the agent's answer.
- Avoid passing raw, uncurated data to the agent in full sequence.

What are the best practices?
- When a tool returns heavy data volumes (large database records, extensive logs), offload it externally and use memory pointers.
- For multiple agents requiring shared heavy data, coordinate state across steps using identifiers.
- Keep agent cycles and tools explicit: ensure tools return distinct, clear answers, enforce tool call limits, and implement asynchronous descriptors.

Thank you. If you want to know more about agents, we have a booth with specialists and AWS Lego mini-blocks. And remember, I am Elizabeth, not Morgan. Thank you very much!

</details>