---
author: AI Engineer
date: '2026-07-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=RGSFUqzqErE
speaker: AI Engineer
tags:
  - agentic-retrieval
  - retrieval-augmented-generation
  - agent-optimization
  - knowledge-grounding
  - hybrid-search
title: 重构 AI 与知识的联结：微软 CVP 阐述智能体的三维知识演进与工程实践
summary: 微软杰出工程师兼 CVP Pablo Castro 探讨了智能体时代知识的三大维度：内源知识、外源知识和学得知识。他详细介绍了微软 Foundry、Microsoft IQ 以及 Agent Optimizer 等工具，展示了如何通过混合检索与自主优化构建高效的企业级 AI 学习闭环。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Microsoft
products_models:
  - Microsoft Foundry
  - Microsoft IQ
  - Agent Optimizer
  - GitHub Copilot
  - Claude
media_books: []
status: evergreen
---
### 内源跃迁：参数化记忆驱动开发革命

Pablo Castro 提到，要理解智能体与知识的关系，首先需要审视“何为知道”以及我们如何基于所知去执行任务。他将知识分为三大类：**内源知识**（Intrinsic Knowledge）、**外源知识**（Extrinsic Knowledge）与**学得知识**（Learned Knowledge）。

**内源知识**（Intrinsic Knowledge: 固化在模型参数中的先验记忆）是模型与生俱来的知识，它来源于预训练数据集。正是这种参数化记忆与推理能力的结合，将我们推向了技术指数级增长的时代。以编程为例，从 1996 年微软引入 **IntelliSense**，到 22 年后机器学习对其进行候选项排序优化，再到仅 3 年后 **GitHub Copilot** 的推出，技术演进经历了巨大的拐点。如今，随着 Cursor、GitHub Copilot X、Claude 等模型的快速迭代，我们甚至见证了完全无需手写代码即可构建复杂软件系统的奇迹。为了方便开发者将这些模型无缝集成到智能体中，微软在 **GitHub** 上构建了智能体平台，并在 **Microsoft Foundry**（Microsoft Foundry: 微软统一的智能体托管、观测与模型管理平台）中提供了丰富的模型目录，最近还正式宣布 **Claude** 在 Microsoft Foundry 中全面可用（Generally Available），实现了参数推理能力与工程托管的强强联手。

在建立这种内源模型推理基础后，具体的企业级落地技巧与多源知识融合架构如下。

<details>
<summary>Original English</summary>

>> Now taking the stage is CVP and distinguished engineer at Microsoft, Pablo Castro.

>> Hello everyone. Hello everyone. Good morning. It's great to be back here at the AI Engineer World's Fair. Now, my job at Microsoft is to connect the dots between AI and knowledge. As an information retrieval nerd, like that's great for me. Like I spend a lot of time on looking at knowledge representation, extraction, search, and whatnot. And thinking about agents and knowledge really invites to reflect on, you know, what it means to know something. And uh, you know, the the the nature of how do we get things done based on what we know.

There. So, this morning what I thought we would do is spend a little bit of time talking about the nature of knowledge and split it into these three categories of intrinsic, extrinsic, and learned.
Intrinsic knowledge is just the knowledge that comes with the models. You know, it's what we uh train the models on, the training data, and what uh stored in the models' kind of parametric memory. And while it's kind of the obvious thing, I would argue this is the knowledge that actually threw us into the exponential we are in today. It's what started many of the scenarios that then grew on all the things we're doing with agents today.
Let me give you an example with code. So, I wrote these two pieces of code about 25 years apart. And yet, the process to put this thing together was surprisingly similar. Like I had to sit down with what I knew or what I had to go look up and then just write it up. And while, you know, I'm illustrating this with knowledge, you could say the same thing about, you know, writing an email or creating a summary of a document.
Now, you can see this exponential at play in tasks like these where, you know, I'm sure you can go further back. But an interesting point in time to start looking at this would be when Microsoft introduced IntelliSense. That was in '96. And, you know, it was great. You didn't have to remember function signatures anymore and whatnot. It takes 22 years from there to go for the next step where machine learning helps us actually rank the options we give you in IntelliSense, so it's quicker to pick the right choice. Just 3 years after that, GitHub Copilot launches. And that was one key inflection point. This was even before ChatGPT was announced. And, you know, I would argue that GitHub Copilot, ChatGPT, that sort of experiences were heavily grounded on this intrinsic memory, what the models already knew.
From there, of course, things shifted. You know, a couple of years later, Cursor launches, GitHub Copilot X launches, and how we do things kind of evolved really quick, which takes us to kind of late last year. Opus 4.5 ships. And then rapid succession, you know, GPT, Opus, and other models keep getting better and better at coding. Which takes us to early this year, where incredibly successful software like like Open Claw comes out to existence with not a single line of code written by hand. So, this is the shape of the exponential we're in. And a lot of this was powered by the by the intrinsic knowledge in models and of course their ability to reason.
Now, in the context of Microsoft, we want to make available all these models and make it easy for you to integrate them into the agents you're building. We do this from our agent platform that starts in GitHub where we all go and build. It has a contextualization system so you can ground your agents. And when it comes to agent hosting, observability, and management, we all do all of these in Foundry. Microsoft Foundry is also where we offer thousands of models in our model catalog so you can pick whatever is the right model for the right task. And we keep adding more every day. In fact, just yesterday we announced that Claude in Microsoft Foundry is generally available so you can use all the capabilities of Claude in the context of the unified experience in Foundry. So you get best of both worlds.
Now, an interesting model got us here, but it only gets you so far if you're building a system that or an agent that needs to participate in what's happening in an organization or a company.

</details>

### 外源演进：多源混合与智能体检索

智能体通常需要接入**外源知识**（Extrinsic Knowledge: 外部数据库或企业数据源中的环境信息）以处理企业内部的业务流。早期的检索增强生成 **RAG**（Retrieval-Augmented Generation: 通过外部检索为模型提供实时上下文的技术）是一种较为低技术的手段，但已快速演进为高度复杂的上下文工程系统。这一演进在两个维度上尤为明显：

* **从隔离数据走向全公司全局接入**: 智能体不仅需要特定任务的数据，还需要企业中的环境数据。为此，微软开发了 **Microsoft IQ**，作为统一企业这些数据的单一入口。其包含：
  - **Work IQ**: 联结 SharePoint 文档、邮件、日程和团队聊天。
  - **Fabric IQ**: 提供对数据湖、数据仓库及 Power BI 报表的分析资产接入。
  - **Foundry IQ**: 托管自定义的智能体专属数据。
  - **Web IQ**: 允许智能体检索外部公开的网页信息。
* **从简单向量搜索走向混合分层检索**: 仅靠余弦相似度计算已无法满足复杂的实际检索需求。评估表明，多种检索方式的融合（Lexical 与 Vector 混合检索）效果显著优于单一方式。**Foundry IQ** 采用分层架构设计，既支持开箱即用的自动化管道（处理文档分块、向量化、重排），也允许专家级开发者在底层自定义向量索引的量化算法和词汇检索权重。

此外，微软引入了**智能体检索**（Agentic Retrieval: 智能体自主评估并反思检索结果质量的检索模式）。它在召回证据的完备性与答案准确度上明显优于单次检索。在管理这些海量企业级外源知识时，系统还将知识库以 **MCP 服务**（Model Context Protocol: 开放式大模型上下文交互协议）的形式直接暴露，确保无需繁琐的胶水代码即可即插即用。同时，系统还通过严格的评估优化**标记效率**（Token Efficiency: 尽量使用最少的 Token 传达最高密度信息的能力），确保外源知识库的查询兼具高性价比与高质量。

<details>
<summary>Original English</summary>

And you know, as an industry we realized this early and we, you know, we saw the the RAG pattern emerge. That started as a pretty low-tech technique, but quickly evolved and what we do today with context engineering and you know, it became a pretty sophisticated system for connecting agents and the knowledge they need to get their job done. Of the many dimensions of of which this got kind of complicated, I'm going to pick on two. One is kind of the evolution from simple and isolated data sets to whole company-wide grounding. And the other one is how we started with simple vector search and whatnot and we really saw this evolve into fairly complicated retrieval systems.
So let's start with company grounding. Like at Microsoft, you know, spending time with customers, one of the things we saw early was that whenever you build an agent, you you always have the knowledge you care about for that agent and you'll manage that yourself, but you also need to ground the agent often on the kind of the ambient data of your organization, you know, whenever the agent leaves. This includes maybe your documents, your emails, your chat threads, or the information in your data warehouse and whatnot. So, we built Microsoft IQ as a way to give you a single entry point into all these kind of ambient data that agents need to get the job done in addition to the specific information that you build into the agent. Microsoft IQ is not one feature, it's more like a set of capabilities that goes from work IQ that connects your agents to all the documents in say SharePoint, all the emails, calendar, your chats, and the connections between people to fabric IQ that gives you access to all the all your analytics assets, you know, from data warehouses and data lakes to Power BI reports, and foundry IQ, which is what you use for your all agents where you can push your own data and then use it for grounding. And of course, sometimes you have your agents need to go out to the web to ground on data maybe not yours, it's public information, but but you need to use it to complete the picture of what the agent world's view is, and for that we have web IQ.
Now, this first part allows agents to ground on the kind of these ambient data. Now, the second dimension I mentioned before is the evolution of the actual retrieval systems. You know, when drive first emerged, I think, you know, what we saw is like an initial adoption for vector databases that really unblocked us from getting a lot of these systems off the ground, and that was great. Um, I think, you know, for a hot second as an industry, we thought that if we could get really, really good at computing cosine similarity between vectors, we were all set for retrieval. It turns out, you know, things never are are never that easy. Uh, so, you know, what evaluations show over and over again is how, you know, if you combine methods, you just get better results. Like in this case, this is an evaluation from actually I search, the search technology behind Foundry IQ. And you can see how individual methods don't do as well as combined methods, particularly when you apply them to real-world customer scenarios.
Now, the trick is how you build a platform that allows you to combine all these building blocks without putting the complexity right in front of you. You like let you opt into it when you need control, but when you have a scenario that is clear, then you can have an easy system. So, in Foundry IQ, that was one of our core design goals. And the way we do this is we actually layer the system. So, you can start at the top, you can go to Foundry and say, "Hey, I have a bunch of, I don't know, PDFs or pictures over there. Just deal with them." And then we'll do everything under the covers, do like, I don't know, chunking, vectorization, deal with relevance and ranking, deal with agentic retrieval and whatnot. Now, if you're an expert and you want control, you can also do that. You can go to the bottom of the stack, you want to build vector indexes and tell us how to quantize the vectors or control lexical retrieval and whatnot. You can do all of that and you can do it in the same stack, which means you can go up and down as you as your needs change.
Now, on on top of the core retrieval system, we also introduced an agentic retrieval stack because we see that for easy cases, like, you know, quick single-shot retrieval is great, but for more sophisticated cases, you do want a system that can reflect on on what's in the data set and decide whether or not we've satisfied the information need as stated in the input before we come back with results. Of course, we see a lot of patterns like this emerge and they always the question is, is this actually useful? Like, are the results better? Our experience in our own evaluations is for for difficult cases, agentic retrieval can a difference. You across the many metrics that we we track, you know, things like um the actual actual evidence recall or answer completeness, we see like the agentic retrieval approach continuously does better than than simple that's uh individual simple parts.
Now, let me show you some of these in action if you can go to laptop. Can we switch to the laptop? There you go. So, here I'm in I'm in Foundry, and uh Foundry is where you you manage your agents, manage models, but also the place where you can manage all the knowledge that you give your agents in order to uh do their jobs. Um when here, you can you can create knowledge bases as the kind of the entry point of energy agents into the knowledge you care about. In this case, I'll create a knowledge base. I have a data set about movies. These are agentic retrieval systems, so I'll give it a model to power the retrieval workflow. And I can say how much effort you want the model to uh to make or the system to make. And this is effectively a trade-off between latency and quality. I can configure a number of other things, but critically, I want to say where the data I want to ground is coming from. And uh I can start from scratch, or in this case, I have a bunch of unstructured data like PDFs and whatnot in in blob storage. I have structured, you know, parquet tables with statistics, and I also want to ground on the web. So, if I take these three steps, and then I save this knowledge base, now I have this asset, this knowledge base that I can connect to an uh Foundry agent right here, and it'll take a second. Uh but also it's a standalone asset that if I have already a harness that I'm using in other in other places, every knowledge base is an MCP server, so you can just connect to it uh without having to write any glue code in the middle. Now, a knowledge base like this has uh you know, has a bunch of parts. Some of them, like uh for example, this uh storage uh content, you usually build indexes uh and you you know, vectorize these things and whatnot. Uh and if you want control over that, like if I if you don't, you can just use it here. But, if you do, let me just switch to Azure and show you the service behind that particular instance. Where if I go to knowledge bases, this is the knowledge base we just created a second ago. And I can go peek inside. For example, I can go fish out the indexes that back this particular uh piece of content. And in that index, I can see what is the structure of the index. Uh if I'm opinionated about, I don't know, maybe the quantization uh approach I want to use or which indexing algorithm I want for my vectors, I can say all of that. And of course, I can actually go and explore the data. And you know, see what's inside, how chunks were organized, and and whatnot. So, the goal of this is to again give you high product a highly productive environment when you need uh when you don't need uh the sophistication, and when you need it to make sure you have it to get your job done. We go back to slides. And of course, the other aspect of this is, you know, top of mind these days for all of us is token uh is token efficiency. And uh so, uh we carefully evaluate this system to make sure that we give you the most information dense answer that has the fewest tokens uh so that you you know, the the your consumption of tokens has a high value when it comes to all retrieval tasks.

</details>

### 学得闭环：智能体自主优化机制

除了静态的内源和外源知识，智能体系统最重要的演进在于引入**学得知识**（Learned Knowledge: 智能体通过观察运行轨迹和用户反馈，不断自我调整与优化的动态知识库）。微软 CEO **Satya Nadella** 曾指出，人类与智能体可以通过长期的协作形成一个不断沉淀独特组织能力的学习闭环。为了将这种机制落地，微软在 Foundry 中构建了**智能体优化器**（Agent Optimizer: 通过跟踪运行轨迹并不断调整智能体配置的自动化优化工具）。

在具体的工程实践中，开发者可将智能体中的指令、工具定义和技能配置外部化，通过以下两个核心步骤实现自优化：

1. **生成自动化评估集**: 使用 `eval generate` 工具。系统能够提取智能体运行的历史追踪（Traces）与原始指令，自动生成一套针对任务遵循度的指标评估数据集。
2. **执行山峰攀爬优化**: 运行 `optimize`。优化器启动一个类似 **JPower 风格**（JPower-style: 微软内部的一种基于探索的启发式调优搜索模式）的演进式搜索循环，通过评估基线并不断变异生成候选配置。系统在经历约 45 分钟的微调后，会通过“山峰攀爬”算法使配置不断逼近评估指标的最优解。

优化完成后，开发者只需运行 `optimize apply` 即可实现热替换。从输出的 Diff 来看，智能体的系统指令已不再是纯手工撰写，而是包含了大量由优化器通过 hill-climbing 迭代自动生成的、针对边缘案例特别优化的指令。这种将运行 trace 转化为智能体新技能的闭环，正是“学得知识”在现代 AI 工程中的最佳体现。

<details>
<summary>Original English</summary>

The last category of knowledge I wanted to talk about is learned knowledge. Now, learned knowledge is the result of us doing the work we do as individuals and as organizations every day. And the the idea that we can actually observe the processes and get better at them by reflecting and improving every step of it is something that is really uh changed now that we have agents doing the work and we can go tune the agents automatically. Satya wrote about this recently and reflected on the fact that people and agents can really compound in in how they do the work and how they can create this learning loop that effectively captures what's unique about the company or or the organization you're working on and inputs that to work to differentiate the work that you do.
Now in Foundry we wanted to offer like a material a materialized version of this that you can use today. So we built a component called the agent optimizer that effectively goes through this process and allows you to evaluate a baseline, generate candidates, and then you know, evaluate the new candidates and we have a strong result, then deploy that to production. Let me give you a kind of a quick flavor of what this looks like if we can switch back to the laptop. All right. So here I'm I mean VS Code, I have the Foundry toolkit installed. And I have a simple agent, it doesn't matter how you write your agent as long as you externalize configuration like you know, your instructions, tool definitions, skills, and whatnot. So once you have one of those, it takes two key steps to do this. So first oops. Um I can actually so usually you have an evaluation already, but if you don't, you can actually say eval generate and what we'll do is we'll look at what we know about the agent like traces and instructions and whatnot and we'll produce a task adherence focused evaluation for you. In this case I run this a little bit earlier. So just to give you a flavor of what this looks like, you you have a bunch of tasks and then you know, the questions and the criteria and whatnot. Once you have a dataset you can evaluate then next step is you can say uh optimize. And uh I could just run optimize on its own and that will run In this case, this run for maybe 45 minutes or so and you get an optimized version by effectively hill climbing the metric that's established from by evaluation. Um so I run this earlier and so let me show you the output for this particular one. Where you can see that, you know, we established the baseline first and then we kept iterating on candidates uh using different combinations using a J power style kind of loop uh and uh looking for options that perform better given uh the rubric that we have. And uh the interesting thing is that once you found one that is that is better, then you can simply just say optimize apply and what this does is since you externalize the configuration, it allows you to swap one configuration for the other. Um if I if if we look here, you can see that for example, I have baseline and the one we just applied. And just to pick on instructions, these are just the uh trivial instructions for this example agent. But if I look at the optimized one, then you can see like a bunch of instructions that are not handwritten but that that they emerged out of the hill climbing process to get to make this particular um agent better given what we have in terms of instructions and skills and tools, but also based on reflecting on the actual uh traces from the agent as users are using it. So this is a real learning loop materialized in practice. You can go back to slides. So this was like a very quick overview about how do we think about knowledge in the context of AI and how do how we think we can enable these learning loops that will capture, you know, these differentiated capability that lives in each one of the companies and organizations we work on. If you want to try anything of what I talked about or showed today, you can head to ai.azure.com and get going. And with that, thank you all for listening this morning. I hope you have a great rest of the event. Thanks.

</details>