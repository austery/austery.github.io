---
author: Stanford Online
date: '2025-11-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=k1njvbBmfsw
speaker: Stanford Online
tags:
  - prompt-engineering
  - retrieval-augmented-generation
  - agentic-workflow
  - multi-agent-system
  - model-context-protocol
title: 斯坦福 CS230 | 2025秋季 | 第8课：超越 LLM——Agent、提示工程与 RAG
summary: 本讲座深入探讨了如何超越基础大语言模型（LLM）构建实际的 AI 系统。内容涵盖了从提示工程（Prompt Engineering）、微调（Fine-tuning）到检索增强生成（RAG）的优化路径。重点讲解了吴恩达（Andrew Ng）定义的 Agentic AI 工作流、Agent 的核心组件（内存、工具、规划）以及多 Agent 系统。通过客服 Agent 案例演示了评估框架，并展望了多模态和架构搜索等未来趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Andrew Ng
  - Ilya Sutskever
companies_orgs:
  - Stanford University
  - OpenAI
  - Anthropic
  - Microsoft
products_models:
  - GPT-4o
  - Model Context Protocol
  - GPT-3.5 Turbo
media_books: []
status: evergreen
---
### 超越 LLM：讲座概览

**[讲师]**: 大家好，欢迎来到 CS230 深度学习的另一场讲座。今天我们要讨论增强大语言模型的应用，我把这节课称为 **“超越 LLM（Beyond LLM）”**。它包含很多较新的内容。这节课的思路是，我们从学习神经元开始，然后是层、深度神经网络，接着在 C3 中学习了一些如何构建项目的知识，现在我们要更进一步，看看如果你在初创公司或企业中构建 **Agentic AI（智能体 AI）系统**，会是什么样子。这可能是最实用的讲座之一。

<details>
<summary>Original English</summary>

**[Instructor]**: Hi everyone, welcome to another lecture for CS230 Deep Learning. Today we're going to talk about enhancing large language model applications, and I call this lecture Beyond LLM. It has a lot of newer content, and the idea behind this lecture is we started to learn about neurons, and then we learned about layers, and then we learned about deep neural networks, and then we learned a little bit about how to structure projects in C3, and now we're going one level beyond into what would it look like if you were building agentic AI systems at work, in a startup, in a company, and it's probably one of the more practical lectures. 

</details>

**[讲师]**: 再次强调，我们的目标不是在接下来的一个小时左右构建出一个端到端的产物，而是告诉你 AI 工程师已经破解、发现或正在探索的所有技术。这样在课后，你就拥有了关于不同 **Prompting（提示）技术**、**Agentic 工作流**、**多 Agent 系统**、**Evals（评估）** 的广阔视野。当你想要深入研究时，你就有足够的背景知识去钻研并更快地学习。

<details>
<summary>Original English</summary>

**[Instructor]**: Again, the goal is not to build a product end-to-end in the next hour or so, but rather to tell you all the techniques that AI engineers have cracked, figured out, or exploring, so that after the class you have sort of the breadth of view of different prompting techniques, different agentic workflows, multi-agent systems, EVAs, and then when you want to dive deeper, you have the baggage to dive deeper and learn faster about it. 

</details>

### 基础模型的局限性

**[讲师]**: 让我们像往常一样，尽可能地保持互动。大家都很熟悉 **GPT-3.5 Turbo** 或 **GPT-4o** 这样的预训练模型。仅使用基础模型有什么局限性？使用原生预训练模型时通常会出现什么问题？

<details>
<summary>Original English</summary>

**[Instructor]**: Okay, let's try to make it as interactive as possible, as usual. You are all familiar with pre-trained models like GPT 3.5 Turbo or GPT 4.0. What's the limitation of using just a base model? What are the typical issues that might arise as you're using a vanilla pre-trained model? 

</details>

**[学生]**: 缺乏某些领域知识。

<details>
<summary>Original English</summary>

**[Student]**: Lacks some domain knowledge. 

</details>

**[讲师]**: 你完全正确。几年前我们有一组学生——虽然与 LLM 无关——他们正在构建一种自动耕作设备，通过底部的摄像头拍摄农作物图片，以确定农作物是否生病。这种数据集在外面是找不到的，基础模型或预训练的 **计算机视觉模型** 肯定会缺乏这种知识。还有吗？

<details>
<summary>Original English</summary>

**[Instructor]**: You're perfectly right. You know, you we we had a group of students a few years ago was not LLM related, but you know they were building a an autonomous farming device or vehicle that had a camera underneath taking pictures of crops to determine if the crop is sick or not, if it should be thrown away, like if it should be if it should be used or not, and and that data set is not a data set you find out there, and the base model or a pre-trained computer vision model would lack that knowledge, of course. What else? 

</details>

**[学生]**: 模型是在高质量照片上训练的，但在现实中，摄像头拍出的照片可能非常暗。

<details>
<summary>Original English</summary>

**[Student]**: Trained on high quality pictures, but in reality, the pictures are very dark on the camera. 

</details>

**[讲师]**: 没错。正如我们在 **GAN（生成对抗网络）** 中看到的，现实世界的分布可能与训练集不同。此外，LLM 缺乏最新信息，模型不是实时更新的。几年前有一个搞笑的故事，特朗普在第一次任期内发了一条推文叫 **“covfefe”**。这个词并不存在。当时推特运行的 LLM 无法识别这个词，推荐系统也乱套了。在社交媒体上，新趋势层出不穷，很难通过重新训练 LLM 来理解这些新词（比如 Gen Z 的流行语）。

<details>
<summary>Original English</summary>

**[Instructor]**: In fact, yes, the distribution of the real world might differ as we've seen with GANs from the training set, and that might create an issue with pre-trained models. Lacks current information. The LLM is not up to date. One story that I found funny, it's from probably three years ago or maybe more, five years ago, where during his first presidency, President Trump one day tweeted "covefeve." Just "covefeve," and it was probably a typo. That word did not exist. The LLMs, in fact, that Twitter was running at the time could not recognize that word. This is an example of nowadays, especially on social media, there's so many new trends, and it's very hard to retrain an LLM to match the new trend. 

</details>

### 提示工程：从零样本到链式调用

**[讲师]**: 提升 LLM 表现的第一道防线是 **提示方法（Prompting Methods）**。我们可以从简单的“总结这份文档”改进为带有角色设定、具体受众和结构化步骤的提示。比如：**“作为可再生能源专家，为政策制定者总结这份 10 页的科学论文，提供 5 个要点。”**

<details>
<summary>Original English</summary>

**[Instructor]**: The first line of optimization, which is prompting methods. I'm giving you a very simple prompt here. Summarize this document. You can actually improve these prompts by doing something like summarize this 10 page scientific paper on renewable energy in five bullet points focusing on key findings and implications for policymakers. 

</details>

**[讲师]**: 还有 **Chain of Thought（思维链，CoT）**，鼓励模型“分步思考（Think step by step）”。这在初创公司中非常流行。以及 **Few-shot Prompting（少样本提示）**，通过提供几个例子来校准模型的输出。例如在判断评论语气时，给它几个“积极、消极、中性”的例子，这比 **Zero-shot（零样本）** 效果好得多。

<details>
<summary>Original English</summary>

**[Instructor]**: Then there's chain of thoughts. This is actually a popular method that's been shown in in research that it improves. Approach the task step by step and do not skip any step. Few shot prompts are very popular. Zero shot refers to the fact that it's not being given any example, into a few shot prompts where the model is given in the prompt a set of examples. 

</details>

**[讲师]**: **Chaining（链式调用）** 是目前提示工程中最流行的技术。它不是 CoT。它是将复杂的任务分解为独立的 Prompt 链。例如：第一步提取关键问题，第二步根据问题拟定回复大纲，第三步写出完整的回复邮件。这样你可以独立测试和调试每一个 Prompt，而不需要把所有指令塞进一个巨大的 Prompt 里。

<details>
<summary>Original English</summary>

**[Instructor]**: Chaining is the most popular technique out of everything we've seen so far in in prompt engineering. It's not chain of thought. This is different. This is chaining complex prompt to improve performance. One advantage of chaining is you would separate the prompts so that you can debug them separately. A first prompt is extract the key issues. Second prompt, draft an outline. Prompt number three, write the full response. 

</details>

### 检索增强生成：RAG 的原理

**[讲师]**: 让我们谈谈 **RAG（检索增强生成）**。这是面试中的常考题。预训练 LLM 有幻觉、知识断层和缺乏来源的问题。RAG 允许模型接入外部知识库。

<details>
<summary>Original English</summary>

**[Instructor]**: Let's talk about RAGs. RAGs is important. It's a very common interview question. Standalone LLMs have challenges including hallucinations, cutoff dates, and lack of sources. RAG integrates with external knowledge sources. 

</details>

**[讲师]**: 工作流程是：首先将文档通过 **Embedding（嵌入）** 算法转化为低维向量，存储在 **Vector Database（向量数据库）** 中。当用户提问时，也将查询转化为向量，通过计算距离检索出最相关的文档片段，然后将这些片段作为背景信息放入 Prompt 中，让 LLM 根据这些事实来回答。这样回答就有了依据（Grounded），而且你可以让它标注出具体的页码和行号。

<details>
<summary>Original English</summary>

**[Instructor]**: The way it works is you have your knowledge base of a bunch of documents. You use an embedding to embed those documents into lower dimensional representations. You will store those representation into a database called a vector database. You run a retrieval process, find the relevant documents. Then you add them to the user query with a system prompt. The prompt template can be answer user query based on list of documents. 

</details>

### Agentic 工作流：吴恩达的定义

**[讲师]**: **吴恩达（Andrew Ng）** 提出了 **“Agentic AI 工作流”** 这个词。因为现在很多公司把什么都叫 Agent，甚至一个 Prompt 也叫 Agent。吴恩达认为，Agentic 工作流是关于完成任务的多步骤过程，它包含工具调用、API 调用和资源整合。

<details>
<summary>Original English</summary>

**[Instructor]**: Andrew actually coined the term agentic AI workflows. Calling everything an agent doesn't do it justice. So Andrew says let's call these agentic workflows because in practice it's a bunch of prompts with tools with additional resources, API calls that ultimately are put in a workflow. 

</details>

**[讲师]**: 这是一个范式转移：从 **确定性编程（Deterministic）** 转向 **模糊工程（Fuzzy Engineering）**。传统软件处理结构化数据，过程是确定的；而 Agent 软件处理自由文本和图像，它是模糊的，非常难以控制。你需要像经理一样思考：如果我把工作交给一组人类，他们的角色是什么？是平面设计师、营销经理还是数据科学家？

<details>
<summary>Original English</summary>

**[Instructor]**: I want to talk about the pirating shift. Traditional software deals with structured data. Now more and more companies are handling freeform text. The software itself used to be deterministic. Now you have a lot of software that is fuzzy, and fuzzy software creates so many issues. You sort of want to think about your software as like your manager. If I was to delegate my product to be done by a group of humans, what would be those roles? 

</details>

### Agent 的核心组件

**[讲师]**: 一个 Agent 的核心组件包括：**Prompts（提示词）**、**Context Management（上下文管理/内存）** 和 **Tools（工具）**。
1. **内存**：分为工作内存（快）和存档内存（慢）。
2. **工具**：包括 API（如航班搜索、酒店预订）。
3. **资源**：Agent 可以读取的数据（如 CRM 系统）。

<details>
<summary>Original English</summary>

**[Instructor]**: What are the core core components of an agent. The prompts. That travel agent also has a context management system, which is essentially the memory. That context management system might include a core memory or working memory and an archival memory. And then you have the tools. The tools can include APIs. Anthropic also talks about resources. Resources is data that is sitting somewhere. 

</details>

**[讲师]**: 这里要提到 **MCP（Model Context Protocol，模型上下文协议）**。这是 Anthropic 提出的。相比于传统的一次性 API 集成，MCP 提供了一种更通用的方式，让 Agent 能够与数据源高效通信，它类似于 Agent 之间的通信协议。

<details>
<summary>Original English</summary>

**[Instructor]**: You probably have heard the term MCP or model context protocol that was coined by Anthropic. MCP, it's really about putting a system in the middle that would make it simpler for your LLM to communicate with that endpoint. It's agent to agent communication, which allows more scalability. 

</details>

### 案例研究：评估客服 Agent

**[讲师]**: 假设你的经理让你构建一个修改收货地址的客服 Agent。你该如何评估它是否有效？
1. **端到端指标**：用户满意度评分。
2. **组件评估**：单独测试每一个步骤（提取信息是否准确、数据库更新是否成功）。
3. **LLM Traces（追踪）**：这是 AI 堆栈的基础，没有追踪你就无法调试。

<details>
<summary>Original English</summary>

**[Instructor]**: Let's do a case study with evals. Let's say your product manager's manager asks you to build an AI agent for customer support. How would you know if your system works? One is an end-to-end metric. You look at the user satisfaction at the end. You can also do a component-based approach. LLM traces are very important. If they don't have LLM traces, it is pretty hard to debug an LLM system. 

</details>

**[讲师]**: 还要区分 **客观指标（Objective）** 和 **主观指标（Subjective）**。订单号提错是客观错误，可以通过 Python 代码校验；而语气是否友好是主观的，这时你需要 **LLM as Judge（以模型为评委）**，给它一个打分量表（Rubric）来进行自动化评分。

<details>
<summary>Original English</summary>

**[Instructor]**: Another way to look at it is what is objective versus what is subjective. An objective example would be the LLM extracted the wrong order ID. You also have subjective stuff. You probably want to do either human rating or LLM as judges. 

</details>

### 多 Agent 系统与未来趋势

**[讲师]**: 为什么需要 **多 Agent 系统（Multi-Agent Systems）**？主要优势在于 **Parallelism（并行化）** 和 **可复用性**。在一个智能家居的例子中，你可以有一个安全 Agent、一个气候控制 Agent，以及一个与用户沟通的 **Orchestrator（编排者）** Agent。这通常是一种层级结构（Hierarchical）。

<details>
<summary>Original English</summary>

**[Instructor]**: Why do we need a multi-agent workflow? The main advantage of a multi-agent system is going to be parallelism. The other advantage is an agent can be reused. You might have a hierarchical setup here. 

</details>

**[讲师]**: 最后，关于 AI 的未来趋势：
1. **性能高原（Plateau）**：虽然基础模型提升放缓，但通过 **架构搜索** 可能会发现下一个“Transformer”。
2. **多模态（Multimodality）**：理解图像、音频和视频会反过来让模型的文本能力更强。
3. **技能半衰期**：技术变化太快，这些具体的 RAG 优化方法可能两年后就过时了。我希望大家掌握的是视野的宽度，并在需要时具备快速切入（Sprint）和深度学习的能力。

<details>
<summary>Original English</summary>

**[Instructor]**: What's next in AI. I wanted to call out a couple of trends. Ilias Sutskever raises that question about are we plateauing or not? It's probably architecture search. Whoever discovered transformers had a tremendous impact. The other set of gains is from multimodality. Being good at images makes you better at text. Finally, the velocity at which things are moving. The half life of skill is so low. You want to come out of the class with a good breath and then have the ability to go deep whenever you need. 

</details>