---
author: AI Engineer
date: '2026-11-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=g_NgCLTibiM
speaker: AI Engineer
tags:
  - graph-engineering
  - ai-agent
  - workflow-automation
  - knowledge-graph
title: 通过图工程提升 AI Agent 的可预测性与执行效率
summary: Neo4j 探讨了如何将 Agent 工作流形式化为图结构，划分出执行图、上下文图与过程图三种类型。通过将技能或决策链路编译为确定性的图结构脚本，能够约束 Agent 路径、提供可审计的治理能力，并降低模型调用耗时与成本。
insight: ''
draft: true
series: ''
category: ai-workflow
area: PAI
project: []
people:
  - Zachary Blumenfeld
  - Peter Steinberger
  - Will Lein
companies_orgs:
  - Neo4j
  - Uber
  - Databricks
products_models:
  - LangGraph
  - Sonnet
  - Haiku
  - Neo4j Aura
media_books: []
status: evergreen
---
### 图工程概念与三种图类型

[音乐]

>> 我们今天要讨论的是**图工程（graph engineering）**。在座有多少人听说过“图工程”这个词？好的，看来现场有不少人听过。另外我也想了解一下，有多少人熟悉并且使用过 Neo4j？好的，有几位。这让我大概了解了今天听众的情况。

<details>
<summary>Original English</summary>
[music]

>> Uh we're going to talk about graph engineering today. How many people have heard about that term graph engineering? Okay, so so fair amount of the room. And then just so I understand, how many people here are familiar with Neo4j and have used Neo4j? Okay, so we got a few people. So that's good for uh just letting me know who we're talking to today.
</details>

先简单介绍一下相关用语的背景。彼得·施泰因贝格尔（Peter Steinberger）大概在今年夏天早些时候发过一条推文，里面提到了图工程，当时感觉就像是在问：这是否会成为紧跟提示词工程（prompt engineering）和上下文工程（context engineering）演进之后出现的新学科？大家对此也有很多炒作和关注。

这个名称虽然是新的，但其背后的机制其实并不新。在计算机科学中，我们很早就普遍了解状态机、工作流图、知识图谱等各种概念。真正发生变化的，是我们结合 **Agent** 来思考它们的方式。

<details>
<summary>Original English</summary>
Um so just some history on some of the verbage that's being used. Uh there was a tweet that went out uh by Peter Steinberger, I think uh earlier this year in the summer, uh that talked about graph engineering and it was almost like is this sort of a new discipline that's happening as this evolution from prompt engineering and context engineering. Uh and there's a lot of hype around this.

Um and the name for this is new, but the mechanisms are not really new. They we've always known in computer science generally about state machines and workflow graphs and knowledge graphs and all these different things. What's changing is really how we think about them in reference to agents.
</details>

我今天想和大家分享的，正是我们如何看待图工程，并为大家提供一个稍微不同的新视角。如果我们尝试去定义什么是图工程，我认为一个不错的定义是：**将 Agent 的工作设计为显式图的工程实践**。在这个图中，节点执行具体工作，边则有效地在节点之间路由状态。我通常会从三种不同类型的图来理解它：

首先是我们熟悉的通用**执行图（execution graphs）**。它们是在 Agent 运行框架（harness）内部运行的工作流图，节点就是路由器和具体的 Agent。

但我们还可以从另外两种与执行图重叠的方式来思考图工程。其一是**上下文图（context graphs）**。它们记录了决策轨迹、已发生事件的实例，以及这些事件如何连接到你业务领域内的其他数据。

还有一种我称之为**过程图（procedural graphs）**。这类似于将一项技能或过程性知识表示为一张图，其中的步骤可能并不是实际的 Agent，而是某种操作流程（即规程）中的具体步骤。比如不同的调用、决策模型步骤、针对不同 Agent 的步骤、是否升级呈批、校验步骤等等。

<details>
<summary>Original English</summary>
Um and what I'm going to talk to you about today is just how we think about graph engineering. I'm going to offer you a little bit of a new perspective on this. So if we actually try to define what graph engineering is, I think a good definition is it's just the practice of designing agent work as an explicit graph. So where nodes do work and edges effectively route state between them. And I tend to think of it in terms of three different types of graphs. We have our general execution graphs, which you're probably very familiar with. So these are the workflow graphs with routers and agents as actual nodes uh that happen within side of an agent harness. But, there's other ways that we can think about graph engineering, too, that overlap with this. So, that includes context graphs. These are decision traces, instances of what's happened, and how it connects to other data inside of your domain. And then there's also something that I'd call more procedural graphs. So, this is almost like having a skill or procedural knowledge as a graph, where the steps might not be actual agents, but they might be steps inside of uh uh a way of doing something, basically a procedure. So, different calls, maybe a step for a decision model, steps for different agents, whether to escalate, validation steps, and these sorts of things.
</details>

### 图工程的核心优势与跨运行时可移植性

我重点想聊聊后两种图，因为我认为我们对它们的探讨还不够充分。理解了这两种图之后，你实际上也能以一种非常可移植且高效的方式，实现第一种执行图所追求的目标。

图工程让 Agent 能够真正承担更大、更复杂的任务，这正是我们关注它的原因。具体拆解来看，在当前背景下，图给 Agent 带来的核心收益主要有三点：

1. **可预测性（predictability）**：能够约束 Agent 采取的路径，确保其执行任务得到的结果基本准确，并且拥有显式的图结构。
2. **治理、控制与审计能力**：能够引导 Agent 的行为并对其进行审计，从而理解它在做什么，并在下一次进行改进。
3. **可移植性（portability）**：这是我们接下来要重点讨论的有趣之处——与其将图仅仅视为运行时内部发生的事情，不如将其持久化存储并能在不同的运行时之间迁移，让其驻留在知识层中。这带来了更好的互操作性，并使技术栈保持极度简洁。

<details>
<summary>Original English</summary>
And I'm really going to focus on these last two, because I think we don't talk about them enough, and I think by understanding these, you can actually get a little bit at what the first graph is trying to do as well, but in a very portable and efficient way.

So, graph engineering lets agents really take on bigger, more complex work, and that's why we care about it. And really, if you were to split it up, I think in terms of the benefits that a graph offers agents in this uh context, it would be predictability, so being able to constrain a path that an agent takes, making sure that the the answer is basically accurate from a task that it's doing, um and having an explicit graph. The ability to govern, control, and guide what the agent does, and audit it, so you can understand what it's doing and make it better next time. And then the third one, which is going to be interesting that we'll talk about, is how do we actually make graph engineering portable, and instead of thinking about a graph as something that happens in the runtime, it could be something that you can store and actually move between different runtimes and have inside of a knowledge layer, which gives you more interoperability and allows you to have a very simple stack.
</details>

在运行时中思考图时，它本质上就像一个编排组件。在座的大多数人可能都很熟悉 LangGraph、ADK 以及各种其他 Agent 框架，甚至在某种程度上 Anthropic 的多 Agent 研究等成果也属于图工程的范畴。

而我今天要讲的，其实是当我们把这种图与数据放在一起，作为**上下文图**以及前面提到的其他形式存在时，会发生什么。

正如我刚才所说，这样做实际上增加了一个可移植层，使你能够获取所有这些知识，并使其基本上能够与任何类型的运行时协同工作。这就是我今天要探讨的内容。

<details>
<summary>Original English</summary>
Um and in the runtime, when we think about the graph, it's really like a piece of orchestration. So, we're probably all of us or a large portion of us are probably familiar with LangGraph, ADK, um and all these other agent frameworks. Um even to a certain extent Anthropic's multi-agent research and and some other stuff fits inside of graph engineering. Um and what I'm going to talk about today is actually what happens when we take that sort of graph and we put it next to our data as context graphs and some other things that I was talking about before.

Um and really when you do this, as I was saying, you add this portability layer, you add the ability to take all of this knowledge and make it work basically with any type of runtime. So, that's what I'm going to go over today.
</details>

### Neo4j 的知识层架构与技能编译研究

这正是我们在 Neo4j 所做的工作：我们正在定义这样一个**知识层（knowledge layer）**。这个知识层位于你通常检索数据的记录系统之间，比如 DataStax、BigQuery、Snowflake 这类平台，也可以是文档、Obsidian 或 Markdown 文件。我们希望在该层中构建标准协议和构件，以便将图工程流程开放给任意运行时或任意 Agent。

简单介绍一下我们在 Neo4j 的产品形态：我们拥有核心数据库以及之上的大量 AI 扩展能力。数据库和分析层在演讲中会陆续展示，但我真正聚焦的是顶层——即环绕在数据库周围的“Agent 大脑”或相关记忆工具。在接下来的演示中，我会展示加载进数据库的数据，这些构成了我们的知识层，它们来自多个不同源头。而我将展示的大量扩展工具与实验性特性，正是作为连接知识层、实现数据读写出入的 Graph AI。

>> [哼笑/吸气声]

<details>
<summary>Original English</summary>
Um and this is what we're doing at Neo4j is we're defining this knowledge layer and this knowledge layer sits between systems of record that you would ordinarily retrieve data from. So, DataStax, BigQuery, Snowflake, these types of places. It could be documentation, it could be Obsidian, these these markdown files. Um and then can we create standard protocols and artifacts that live inside of that layer that then you can take a graph engineering process and make it available to any runtime or any agent.

Um and the way our product works, just so you know at Neo4j, uh is we have our core database and then we have a ton of other AI stuff on top of it. Uh so, the database and the analytics layer, um I'm going to be showing some of this throughout my talk, uh but what I'm really going to be focusing on is this top layer where we talk about sort of this agentic brain or these other memory tools that wrap around the database. So, just know that as I go through, I'm going to be showing you data being loaded into the database. That's going to constitute our knowledge layer. It's going to come from multiple different sources. Um but a lot of the sort of extensions of that tooling and some of the experimental things that I'm going to show you exist as sort of this graph AI that hooks into that and loads data in and out of that thing.

>> [snorts]
</details>

>> 我们在 Neo4j 的做法和思考方式，首先从**上下文图**的概念切入。上下文图包含不同类型的记忆：短期记忆（如对话历史）、长期记忆（从历史或数据中提取的实体），以及位于其中的推理树或决策树。

从研究角度来看，我们探索的一个很有意思的方向起初并不是从整张图着手，而是聚焦于单个技能层面。我们在今年早些时候写了一篇论文并发表在研讨会上，当时试图回答一个核心问题：**我们能否将过程性知识——无论来自过去的决策还是现有的技能定义——编译压缩为一张图？**

最终我们摸索出了一套流程：将书面材料（通常是包含脚本、参考资料和静态资产的 `skill.md` 文件）转换并迁移至真正的图结构中，也就是大家在另一侧看到的内容。

<details>
<summary>Original English</summary>
>> Um so, what we're doing at Neo4j and kind of how we're thinking about this, we start with this concept of a context graph, which has different types of memory from short-term memory, which is going to be like your conversation history, your long-term memory being entities that are extracted from that or from your data, and then reasoning or decision trees inside of that.

And one of the interesting things that we've been looking at from a research perspective, and this really started out not so much at that graph, but actually at individual skill level. There was a paper that we wrote earlier this year that we published in a workshop, and we were really trying to ask the question, can we take procedural knowledge, whether it be from past decisions or even something like a skill like we have here, and compile it down to a graph? And what we came up with was a process of taking written material, often a skill MD file, and the scripts and the references and assets, and moving that into an actual graph structure, which is what you see on that other side.
</details>

通过这样做，并赋予 Agent 访问该图结构的权限——图中不同的节点分别代表技能内部的决策点、不同的路由分流点以及必须执行的脚本，将散文描述编译成确定性的脚本链路——当我们强制 Agent 按照该图执行时，观察到了**任务奖励（task reward）和性能表现的显著提升**。

这是前段时间的实验结果，我目前还在 [清嗓子] 推进基于最新模型的更新。不过当时我们已经能够使用更小的模型，当时用的是 Sonnet，现在我们甚至切换到了 Haiku。我们观察到，即使面对涵盖物理学、计算机科学、各类安全以及体能训练等跨多个领域的极具挑战性任务，整体的任务奖励表现也有明显提升。

随后我们转向了下一步。

<details>
<summary>Original English</summary>
And the result of doing this, and giving the agent the access to that graph structure, which has different nodes again representing inside of the skill decisions, different routing points, different scripts that have to be executed, taking pros and compiling them down to to determine the six scripts. When we do that and we force the agent to sort of run that graph, what we see is increases in uh task reward and performance. So, this was uh from a while ago. I I'm still [clears throat] working on updating it to the latest models, um but we were able to use a smaller model. In this case, I think it was Sonnet, um and now we're we're on to Haiku, as a matter of fact, but uh we were seeing even for really challenging tasks over diverse fields in physics and computer science and um various security, uh physical training, a whole a whole ton of things, um is this overall increase in task reward um performance. Then we were able to switch over to this.
</details>

### NAMS 架构与行业合规场景实践

我们 Labs 团队的产品经理威尔·莱恩（Will Lein）借鉴了这个思路并提出：“既然能对技能做到这一点，也许我们同样可以将其应用到记忆图上。”也就是说，你可以提取前面展示过的上下文图，从中提炼出技能，同时让该技能依然在同一张图中与过去的全部决策轨迹和数据保持关联。

这样一来，你不仅获得了性能提升，还保留了每个步骤完整的来源回溯链路（provenance）。它是版本化、可追踪的，并具备持续的治理能力，让你能够评估漂移（drift）、追溯特定工具调用的来源及其历史。在 **NAMS（Neo4j Agent Memory Service，Neo4j Agent 记忆服务）** 内部，人类操作者可以清楚了解其具体运作机制，并能对其进行编辑、修改和各种操作——NAMS 是我们针对该方案的参考架构。屏幕上附有二维码，演讲结束时还会再展示一次。

因此，我们现在讨论的是可以任意迁移的构件。它生成的是一个技能，任何能够接收该技能的 Agent 框架，现在都可以直接运行这些图并执行其中的全部逻辑。

<details>
<summary>Original English</summary>
And our PMs, uh, Will Lein, who works in our Labs team, actually took this idea and said, "Well, if we can do that with skills, maybe we can do it, too, with these memory graphs." So, you can actually take that context graph that I was showing you earlier and distill a skill from that and have it still be connected in the same graph over to all of your past decision traces and data. And so, then you get those performance benefits, but you also have all this provenance that goes back from every step. It's versioned, it's tracked, and you have governance over time where you can assess drift, you can understand where certain tool calls are coming from and their history. A human can go through actually inside of NAMS, Neo4j Agent Memory Service, which is our reference architecture for this. There's a QR code there, and there will be another one at the end, um, and be able to understand, like, exactly how this works, edit it, change it, do all sorts of cool stuff with it. Um, so, again, what we're talking about now are these artifacts that you can move around. I mean, this thing makes a skill, right? And so, any agent harness that can take that skill can now be running these graphs and doing all of this logic.
</details>

我们有许多客户正将我们用于图工程类型的任务。因为时间有限，我简单快速过一下。

尽管他们使用的未必完全是我们 Labs 团队的开源项目，但比如有咨询机构正在与资产管理公司合作，解决合规领域的棘手难题。例如编写审计报告，数据可能来自多个不同源头，如何自动化这一流程，同时保证其具备可治理性和可信度？你需要处理合规文档，还要对齐来自不同数据库、带有不同股票代码和名称的实体。通过为 Agent 提供能够表达业务逻辑的图并置于数据旁边，基本上能让你以可信赖的方式实现自动化。

还有像 Uber 这样的企业，将图工程应用于配置图（configuration graphs）。可以想象，对于遍布全美的网约车司机，不同地理区域的合规要求和法规差异极大，而相关数据分散在蔓生杂乱的微服务群中，你需要从中拉取数据来确定具体区域或车辆具体部件的要求。能够将业务逻辑表达成图并紧挨着数据存放，也有助于他们高效地落实这类运营流程。

<details>
<summary>Original English</summary>
Um, and we have various customers that are using us for graph engineering types of tasks. I'll go quickly because we're we're starting to run out of time. Um, and even though they're not may not be using exactly the Labs project that they that we have, uh, we have consultancies which are working with other asset managers, uh, for tough problems in compliance. Uh, so, being able to write audit reports, for example, where you have data that might come from multiple sources. How do you automate that, but do it in a way that's governed and trustworthy? So, you have compliance documentation. You might have entities with different ticker symbols and names from different databases, and those all need to be resolved. And so, giving your agent these graphs that express the logic that you need to do on besides the data basically allows you to automate those things in a trustworthy way.

Um and we have other people uh such as Uber that do this with configuration graphs. Uh so basically, if you have um you can imagine if you have drivers across the country, uh compliance and regulations for different areas geographically vary greatly, um and they come from this sprawl of microservices that you need to pull data from to figure out like, "Okay, well what is it for each area, for each component of a car, for example?" Um and so being able to express that logic and have it sit aside the data um also helps them operationalize some of these things effectively.
</details>

### 贷款审批案例演示：将记忆图编译为确定性技能

接下来进入演示环节。先提醒大家，演示包含的内容相当多，我会节奏较快地带过。但我将展示的是：如何利用我之前提到的 AIP 库来编译一个技能，将原本缺乏良好治理、耗时极长的任务，实现成本大幅降低（基本接近削减 100%），同时运行速度显著提升。当然，这只是一个 Demo，并非正式的研究报告，大家可以在项目代码库中查看全部代码，所有内容都是完全开源透明的。

本次示例针对的是贷款审批流程。在贷款审批流程中显然必须遵循大量的政策规定。我不是金融专家，但现场许多人是。因此通常会有政策文档，有一套必须严格遵守的步骤系统，并且你需要 Agent 能够清晰解释并阐述这些步骤，像人类审核员一样准确给出结论。

正如我之前所说，由于现场网络较慢且时间有限，我无法全部进行实时演示，幸运的是我已经预先加载好了数据。

系统接收到的业务问题是：“我们是否应该批准 Rosa's Bakery 这笔新贷款？”在本案例中，上传的商业计划书是一份 PDF 文档。在图谱中，橙色节点代表的就是商业计划书数据。

缩小视图可以看到，商业计划书连接到了我们从 Databricks 抽取的历史交易数据、贷款政策数据以及过往实际做出的决策记录。借助这些数据，Agent 可以遍历全部信息，快速发现该客户此前曾有过贷款或存在某种历史差错，进而生成审计追踪轨迹并迅速给出处理结果。

>> [哼笑/吸气声]

<details>
<summary>Original English</summary>
So, I'm going to jump to a demo now. It I'm going to warn you in advance, it's going to be quite a lot, and I'm going to jump through it kind of quickly, um but it's very interesting, and what I'm going to show you is how we can use that AIP library that I was talking about before uh to compile a skill and actually get a task that was not governed very well and took very long to run, basically cut its cost by like 100% and then run it a lot lot faster. Um and of course, it's a it's a demo, it's not a formal research proposal, but you can go there and look at the code, it's all it's all very transparent.

Uh so, this is going to be an example for a loan um a loan approval process. So, in a side of a loan approval process, there's lots of policies that have to be followed, obviously. I'm not a financial expert, but many of you in the room are. Um and so there's probably going to be a policy doc, there's going to be a systems of steps that have to be followed exactly, and then you need your agent to be able to explain those steps very clearly, articulate them, and really get the answer right as if it was a human reviewing. Um and the first thing you can do, like I was saying before, and I don't have time to probably run this all live, and the internet's going to be slow. So, luckily I I have this preloaded. Um and basically, the question that was asked was, "Should we approve this new loan for this Rosa's Bakery business?" And in this case, you know, we have a business plan that's in a PDF that was uploaded. Um and that is, let's see, um the business plan is the orange data. So, if I was to scroll out here, you can see it here in the graph. That connects also to data that we pulled from DataBricks from past transactions, lending policy data, and past decisions that were actually made. And with that, the agent can crawl over all that information and basically realize that this person either had a loan before or there was a mistake before, something happened before, and come up with an audit trail for that and basically post a solution uh very very quickly.

>> [snorts]
</details>

>> 从数据实体解析、遵循政策以及理解关联的角度来看，这已经是一个很好的开端。

但这么做也存在问题。我可以向大家展示图谱的样子：这是我多次运行这些政策的示例。放大后可以看到这里的对话记录，以及图谱中保存的推理轨迹。所有步骤都带有时间戳和工具调用记录。

如果观察两次运行的情况，可以查看到两条决策链。由于画面较小，我放大展示一下。大家会发现两条决策链的长度并不相同，其中一条明显更长。这是因为在那次运行中 Agent 找到了历史先例，即之前发生过的相关事件。

但重复执行所暴露的核心问题是：**没有任何机制能够强制 Agent 必须遵循确切的执行路径**。你或许提供了一个包含执行指令的技能，但依然存在分支决策问题——例如简单判定“批准还是拒绝”，或是“批准还是转交人工复核”。

这些决策步骤通常伴随置信度评分，比如提示“如果你有信心就执行，没信心就做另外的处理”，但这些置信度决策往往缺乏校准。因此，如果能将这部分逻辑交给类型安全（type-safe）的模型（例如 Jev 类型的模型）来处理，效果会好得多。

<details>
<summary>Original English</summary>
>> Um and this is a great start. Just in terms of like resolving data and being able to follow policies and understand how things connect, uh this is great. One of the issues with this is, and I can show you a graph kind of of what this looks like. This is an example of me running more of these policies. Um and if I zoom in, I have a conversation here. And then I have my my reasoning trace that exists inside of this graph. And all these steps are time-stamped and they have tool calls. Uh what can happen is if I uh look at this happening twice. I think this is the right query. Um this is this is two decision chains. It's going to be a little bit hard to see. Let me zoom in. Um they they're of different lengths, you'll notice. So, one is longer than the other. Um in this case it was cuz it found a precedent in one, um basically something else that had happened before. But the the problem with this is that if you run these over and over again, there's nothing actually like enforcing that the agent follows an exact path. You might have a skill or something that will say like do these things. Uh but then there's other problems where it's like there's these decision steps where it's approve or deny is a simple one or approve it or send to a human to review. And those decision steps as well come with confidence scores. Uh or you say like if you're confident about it, if you're not confident about something, but those decisions aren't calibrated. So, it would be great to like even take some of this and send it to something like a type safe, you know, Jev type of model as well, to be able to do some of those things.
</details>

### 从 YAML 技能到 CLI 执行：治理与性能实测

因此可以采取的做法是：抓取所有这些轨迹，并将其编译成**图结构的技能（graph-shaped skill）**，正如我们在此处所做的那样。

这个图结构技能在此处可能看不清细节，但看不清也没关系。关键在于，我们从过去多次成功的执行中提取了所有信息（即便那些执行在路径上略有差异），并将其转换为技能内部的 Graph YAML 格式。

虽然大家看不清画面，但这个技能包含了脚本、静态资产，有时还会包含参考资源（当前这个技能没有包含）。它还包含贷款相关的政策源文档。因此里面包含了大量用于链路追溯的信息，同时直接指示 Agent 如何执行该技能。最棒的一点在于，一旦技能被转化为这种 YAML 格式，由于它是一种确定性格式，我们就可以将其导入到各类不同工具中，包括导入到图结构内。

在图谱中，它的形态就像屏幕上展示的这样。让我重新运行一下这个任务。

<details>
<summary>Original English</summary>
So, what you can do is you can scrape all of this and you can compile it into a graph shaped skill, which is what we did here. And that graph shaped skill, if I go here, you're not going to be able to see it. But that's okay that you don't see a lot of the detail here. The important part is that we sort of compiled all the information down from those successful runs that we did, even though they were a little bit inconsistent, and we put them into this graph YAML shape inside of this skill. And this skill, even though you probably have trouble seeing, has scripts, it has assets here, it has sometimes other reference resources, it doesn't for this one. It also has source documentation around the policy that you're supposed to do for the loan. So, there's So, there's basically a ton of stuff in here for traceability, but then also telling the agent how to run the skill. But the great thing is, once the skill is in this YAML format, we can port it into all this different tooling, including inside of a graph, cuz it's all sort of this deterministic format. And in a graph, it looks kind of like this thing here. So, let me Actually, let me just run this Run this sucker again. Um
</details>

大致结构就是这样：所有的执行步骤都在外围展开。我所做的工作，就是在其外部封装了一个轻量级的 CLI 工具，Agent 只需发出指令：“运行此技能”。此时，路由步骤不再由 Agent 自行临场决策，而是完全**以程序化方式执行**。

我们提炼了大量业务政策，并将其封装进了这些具体的执行脚本中。

总结一下这里的核心逻辑：
1. 首先执行硬性规则校验，检查是否满足相关政策的刚性要求；
2. 如果未在此阶段直接自动批准或拒绝，则路由至决策模型（如 Jave 或 TypeSafe 模型），我可以在屏幕上展示更清晰的视图；
3. 该模型会获得风险等级选项，判断是否存在风险敞口，并给出批准或拒绝的决策倾向；
4. 随后的流程进入报告撰写：路由器判断是否需要升级呈报人工复核；若无需转交人工，则由 Agent 撰写报告，并通过内部流转进行校验与静态检查（lint）。

一旦搭建好该模式，我们拥有了能够直接运行这一流程的 CLI 工具。

<details>
<summary>Original English</summary>
This is kind of what it looks like. So, you have all of these steps out here, and then basically what I just did is I wrapped the small cli around this, so the agent can say, "Hey, run the skill." And instead of the agent deciding all the routing steps, it's just done programmatically. We took a lot of that policy down, and we put a lot of it into these execution scripts. Basically, what's happening here, if if I was just to sum it up, there's an execution that basically looks at, "Hey, do do we meet certain hard rules around policies?" After that, it's routed if it's not auto approved or denied based on that, it's routed to a decision model like Jave or TypeSafe. Um, and I can even probably show you a little bit of a clearer view here. Um, and it's given that that model is given like a risk tier choice. Um, let me make that a little bigger. Hold on. Um, whether or not there's there's some exposure material and then like an outcome of whether or not you're approving or denying. And then the rest of this um, will basically follow down into writing a report. Whether or not you need to escalate to a human review as this router. And then if not, basically the agent's going to write a report and there's a circulation here to sort of check and lint that report. Um, so once you do this and you sort of get the model going where okay, well now we have this cli that we can just run this thing in.
</details>

现在我可以在这里尝试执行，虽然可能没有时间完整跑完全程，但我还是尝试启动一下，看它能否顺利调用。整个执行通常需要约 2 分钟。

当流程运行并调用 AIP 技能时，将技能转化为这种格式不仅能让 Agent 极快地运行，还能完整追踪历次执行。例如针对单次运行，我们可以将运行记录持久化存储在图谱中。这里显示的就是该技能的一次运行实例及其执行的独立步骤。

随着时间推移，我们可以持续保存这些记录并评估其表现。在治理层面，我快速构建了一个轻量级的检查器（inspector）：你可以查看所有运行的状态，深入查看单次执行的具体情况，包括流程中哪些被批准、哪些被拒绝、具体走了哪些分支。

有了图结构之后，你甚至可以实现很多出色的可观测性能力，比如查询哪些分支被走过、哪些分支未被执行——这在合规治理层面非常有价值——以及系统是否存在失败，而所有这些信息都紧挨着原始数据存放。

需要明确的是，我们在 Agent 内部并没有构建任何死循环。我们所做的仅仅是提供一个 CLI，让它去执行由文档或记忆图编译而成的程序化技能。

<details>
<summary>Original English</summary>
Um, well now I can go in here and then maybe I can probably don't have time to run this whole thing again, but I will give it a shot. Um, I'll see if it goes and picks this up. It takes about 2 minutes to run. Uh, but the idea I guess while this is running and it should pick up the AIP scale which which it is here. Um, once you have it in this format, not only can you have the agent run this very quickly. Uh, you can track the runs. So for example, um, if I was to look at a single run, I can run this again. I can basically persist the runs inside of the graph. Um, so this is a run of that scale with like individual steps that it ran. Um, and then uh, I can just persist these over time. I can examine how well they work. So from a governance perspective, um, I have a little inspector here that I built really quickly. You can look at the status of all these. You can look at how a specific one ran, what was approved, what was denied inside of the process, what branches it took. Um, and then once you have a graph, you can even do these cool observability things where you can ask well like what branches were taken and which branches weren't taken, um, which is very interesting from a governance perspective. It failed ever, [snorts] um, all these cool different things and all of that is stored besides your data. Um, and so in none of this, we're not like creating a loop, right, inside of our agent. All we're doing here is basically giving it a cli to run this like programmatic skill that we compiled from documentation or in this case from our memory graph.
</details>

由于网络原因，这可能需要一些时间。但我们可以看看多次运行的对比数据。

我之前测试过几次。最初我使用的是 Fable（我的组织经常因为我花太多钱而批评我），光是单独在图上使用 Fable，结果几乎每次都很准确，但需要耗时 2.7 分钟。而当我们引入规程（procedure）并结合 AIP 时，耗时几乎减半。

由于流程已经规程化，我们可以切换到更轻量的模型（例如 Haiku），从而将模型运行时间进一步缩减，成本自然也出现断崖式下降。因为你把原本需要模型动态思考的所有路由负载和复杂逻辑，全部剥离并转移到了执行脚本和类型化模型中，整个系统的执行效率得到了极大幅度的提升。

现场执行确实受限于网络，耗时太长。不过从数据来看，平均耗时从最初的大约 7.5 分钟下降到了约半分钟至 2 分钟左右。

好的，时间差不多了，我就讲到这里。最后为大家提供一些参考资源：**Aura** 是我们的云服务，大家可以在上面获取我刚刚展示的数据库，并享有 100 美元的免费额度；我们即将举办 NODES 演讲者活动；此外还有初创企业扶持计划。我在演讲中提到的所有代码，以及用于对接 Agent 记忆的各个项目，链接都在屏幕下方。在被主持人请下台之前，我会将页面保留片刻。非常感谢大家！

<details>
<summary>Original English</summary>
Um, and this might take a while to run just because of the the internet. But what I will show you is I we ran this a few times. Um, and what we saw is just running, I was using Fable, so my organization already yells at me for this enough so I'm spending a bunch of money. Um, but like just using Fable alone on the graph and it was correct, you know, pretty much every time, but it took 2.7 minutes. When we had the procedure, it almost cut in half just using AIP. And then because we had the procedure, we can use a simpler model like Haiku and then we can cut the model time down even more. And then of course, you know, the cost just goes way down. So cuz you're taking all of that load, right, of having to figure out all the routing, all the stuff you're doing, you're putting into these execution scripts, these Java models and everything, um, which makes everything just much much more efficient.

Um, and this is going to take too long to run. Uh, it's mostly internet. You can see here about half a minute or 2 minutes wall clock on average down from like 7 and 1/2.

All right, so anyway, um, I'll end it here. So I want to give you some resources to check out if you're interested in this type of stuff. Aura is our cloud service offering where you can get the database that I was showing you before. You get $100 of free credits. We have nodes coming up which are is speakers event. There's a startup program. And then all the code that I was referencing in the other projects that I was using to hook up to your agent memory, all that sort of stuff is down there. So, I'll leave this up for a second until someone kicks me off, and I guess that's it for me for now.
</details>