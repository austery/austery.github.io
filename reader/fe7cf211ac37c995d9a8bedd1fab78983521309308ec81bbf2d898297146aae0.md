---
author: AI Engineer
date: '2026-05-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_QAVExf_1uw
speaker: AI Engineer
tags:
  - ai-agents
  - knowledge-management
  - institutional-knowledge
  - demand-driven-context
  - knowledge-gap-discovery
title: Agent驱动的知识管理：需求导向上下文方法论
summary: 本次演讲介绍了一种名为“需求导向上下文”的企业知识管理方法论，旨在解决AI Agent在企业环境中面临的知识库（尤其是机构知识）碎片化、过时和未文档化的问题。该方法通过利用Agent在执行任务时的“失败”来主动发现知识空白，从而逐步建立和完善结构化的上下文知识块。演讲者还提倡将GitHub作为协作管理知识库的平台，并将其与测试驱动开发（TDD）理念进行类比，强调自动化在扩展此方法中的关键作用，最终目标是让Agent从知识消费者转变为知识管理者。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - GitHub
  - Confluence
products_models:
  - Copilot
  - Jira
  - MCP servers
media_books: []
status: evergreen
---
### 欢迎与开场

**发言人**: 谢谢大家。我们开始吧。首先，非常感谢大家来参加这个工作坊，特别是那些没有座位的朋友们。我向你们保证，我会尽力让这次活动充满乐趣，特别是对你们这些正在学习的人来说。非常感谢。

<details>
<summary>Original English</summary>

**发言人**: uh thank you. Maybe we can get started. Uh first of all, thank you so much for uh coming for the workshop especially ones who didn't get the seat. Uh I I promise you I'll do my best to make it entertaining especially for you who are studying. Uh thank you so much.

</details>

**观众**: 是的。呃，这确实有道理。所以现在我知道了为什么票会售罄，对吧？呃，到底是哪个工作坊的票卖完了？

<details>
<summary>Original English</summary> **观众**: Yeah. Uh actually it it makes sense. So now I know like why the tickets got sold out, right? Uh which workshop actually sold out the tickets. </details>

**发言人**: 那么，呃，我们从我的自我介绍开始。我是**Raj**。我在**IKEA**担任**高级软件工程师**。我负责一个叫做“配送服务”的领域。我们基本上有超过一百名工程师和六个pedex团队。它就像公司内部的一个迷你公司。我对架构、神经科学、语言学以及现在的**AI**都非常感兴趣。所以，如果有人有很酷的项目——因为现在大家都在做很酷的项目——请在会后找我。现在，对观众进行一个快速的脉搏检查，呃，有多少人是第一次来伦敦？

<details>
<summary>Original English</summary>

**发言人**: So uh let's start with uh my introduction. So I'm Raj. Uh I work as a staff software engineer uh at IKEA. uh I work for a domain called deliverance services. Uh basically we are like almost more than 100 engineers and six pedex teams altogether. It's like a mini company within the company itself. Uh I'm very interested with architecture, neuroscience and linguistics and now AI. So if anyone has some cool projects because everybody is building cool projects these days, please find me after this meeting. So quick pulse check uh with the uh audience. Uh who is visiting London for the first time?

</details>

**发言人**: 好的，很棒。欢迎来到伦敦。呃，这里有多少人有工程背景，也包括白盒编码和原型设计？

<details>
<summary>Original English</summary>

**发言人**: Okay, cool. Welcome to London. Uh who is here uh from the engineering background also with white coding and prototyping?

</details>

**观众**: 不，所有...

<details>
<summary>Original English</summary>

**观众**: No, all of okay.

</details>

**发言人**: 好的，呃，那么谁在积极使用**Copilot**这样的**Agent**？好的，那对我来说会有点难了。

<details>
<summary>Original English</summary>

**发言人**: So uh who actively uses agents like co-pilot? Okay, this is going to be tough for me then.

</details>

**发言人**: 那么扩展呢？好的，看来大家都是专家。好吧。

<details>
<summary>Original English</summary>

**发言人**: So extensions. Okay. So everybody's pro. Okay. Fine.

</details>

**观众**: 没有我想要的那么多。

<details>
<summary>Original English</summary>

**观众**: Not so much as I want.

</details>

**发言人**: 好的。现在压力很大。呃，你们要坐在这个炎热的房间里一个多小时。所以首先，我将呃，简单介绍一下我今天要展示的内容。呃，主要关于**Agent**和**上下文管理**。我把它分成了三个部分。第一部分是你们都知道的“现状”，所以我会把它讲得简洁明了，大概五分钟。呃，然后我会谈论“问题”。这部分我会在幻灯片上多花些时间，因为我认为呃，没有人真正认真地关注这个问题。呃，我想把它提出来。然后是较少的幻灯片，更多地转向某种**实践**环节，呃，了解实际的**需求导向上下文**是如何运作的。一切顺利。

<details>
<summary>Original English</summary>

**发言人**: Okay. So much tension now. Uh so you're going to sit here in this hot room for more than an hour. So first I will uh give a bit of introduction of what I'm going to present today. Uh it's basically on agent and the context management. Uh I I divided into three parts. One is the situation which all of you already know. So I'll keep it tight and short like five minutes. Uh then I'll talk about the problem. This is where I'll spend a bit more time on the slides because I think like uh nobody is actually seriously looking into the problem. Uh and I want to bring it up then less slides and more into some kind of a hands-on uh how the uh actual demand driven context actually works. All good.

</details>

### AI Agents的记忆困境：电影《记忆碎片》的启示

**发言人**: 好的。那么，我们从第一个开始。有多少人看过这部电影？《**记忆碎片**》。

<details>
<summary>Original English</summary>

**发言人**: Okay. So, let's start with the first one. How many have seen this movie? Memento.

</details>

**观众**: 好的。好的。好的。酷。

<details>
<summary>Original English</summary>

**观众**: Okay. Okay. Okay. Cool.

</details>

**发言人**: 那么，我来概括一下这部电影。这个人非常熟练，呃，非常有才华。他唯一的问题是，呃，他的记忆保持时间不超过15分钟。所以每隔15分钟，他必须拿出笔记本，呃，看他身上的纹身，找出“15分钟前我在做什么”，然后他一遍又一遍地重复这个过程。如果你把它和**AI**、**AI Agent**等事物联系起来，它实际上正好符合这部电影的描述，也符合现在的**Agent**。如果你去看这部电影，你不需要看**YouTube**或博客就能理解**Agent**和**MCP**。这部电影实际上 literalmente 告诉你所有的一切。呃，就像这个人有记忆问题一样，呃，我们几年前引入的**AI**，呃，在推理、计算、呃，代码生成方面非常出色，它的基准表现就像是，呃，超出了预期。唯一的问题是**机构知识**，对吧？你拥有的**领域知识**，那是我们必须稍微有点问题的地方。

<details>
<summary>Original English</summary>

**发言人**: So, I I'll give the gist of the movie. So, this guy is very skilled uh very talented. The only problem he has is uh he can't hold memory more than 15 minutes. So every 15 minutes he has to take his notebook uh watch his tattoos that he put it on his one and figure out okay what I was doing before the 15 minutes and he does it again and again. If you relate to the AI and AA agents things and all it actually fits exactly how the movie is and how the agents are right now. If you go and watch this movie you don't need to watch YouTube or blogs to understand agents and MCP. This movie actually tells you about everything literally. uh and as this guy has a memory problem uh in the same way the AI uh that we got introduced couple of years ago uh is very good with reasoning computation uh code generation it's it's benchmark as like uh above the par the only problem is the institutional knowledge right the domain knowledge that you have that's that's the only thing we have to be uh a bit problematic

</details>

### AI到Agent的演进

**发言人**: 所以从**AI**到**Agent**，如果你看它的呃，演变，呃，它爆炸式增长。所以它首先从**提示工程**开始，呃，然后是**RAGs**，呃，现在是**MCPs**，然后是**多Agent**，现在是**深度Agent**。呃，我最近发现，呃，使用**Replit**实际上可以在10分钟内构建一个**全栈应用程序**。这意味着当你泡方便面的时候，你已经有一个价值百万美元的应用程序在你的笔记本电脑上运行了。所以我们，我们已经达到了这个地步，它非常出色。

<details>
<summary>Original English</summary>

**发言人**: so from AI to agent if you look at the uh evolution uh it exploded So it started from prompt engineering first of all uh then there was rags uh now MCPS then multi- aent now it is deep agents uh I recently found out like uh using replet actually you can build a full stack app in 10 minutes that means the by the time you make the instant noodles you already have a million dollar app already working on your laptop so we we got it to this point like it's extraordinarily good

</details>

### 企业AI的交付困境

**发言人**: 现在那是**AI**和**Agent**。那么我们来谈谈**企业AI**。好的。呃，我不知道你们中有多少人有这个问题，但我看到大多数企业的问题是：好的，**AI**非常智能。它在做呃，**代码生成**、**全栈应用**、**代码审查（PRs）**、**事件管理**所有这些事情。呃，对吧。所以如果**AI**做了这么多，为什么**Jira**工单或Apex没有在仪表盘上移动呢？对吧？为什么我没有看到实际的**交付**？所以大家都在说“看，三分钟内一切都准备好了。”是的。好吧。那为什么我的Jira工单没有移动呢？因为那定义了**业务交付**，那定义了**投资回报**，对吧？呃，正如你所看到的，呃，今年**McKenzie**的报告显示，88%的公司使用**AI**，但它们只看到了，呃，6%的**价值创造**。

<details>
<summary>Original English</summary>

**发言人**: now That's AI and agents. So let's talk about enterprise AI. Okay. Uh I don't know how how many of you have this question but most of the enterprises I see the question is okay. A is pretty smart. It's doing uh code generation fullstack apps reviewing your PRs uh doing incident management all those things. Uh right. So if I is doing that much why is the Jira tickets or Apex are not moving on the dashboard right? Why do I don't see the delivery actually? So everybody is speaking about look at like 3 minutes everything is ready. Yeah. Okay fine. Why are my J pics are not moving? Because that defines the business delivery and that defines the return of investment, right? Uh and as you see like uh it's it's from the Mckenzie this year like 80 8% of all companies use AI but they only see like uh 6% of value creation.

</details>

### 机构知识的挑战

**发言人**: 好的。所以我认为这就是我们面临的问题。呃，我有四个不同的**Jira工单**，是示例工单。你可以看到我标记为绿色的部分，基本上是**LLM**已经训练过的内容，比如**API标准**，或者呃，它们已经知道的事情，那是**通用知识**，对吧？那没问题。那些工单里的任务，**LLM**可以完成。现在有第二部分，橙色的部分，我们需要实际教导它们。所以你要告诉它：“你知道这个，但要这样做。”所以所有这些橙色的东西都会适合你的**Agent扩展**，比如**技能**，或者呃...但是红色的部分，那就是**机构知识**，它存在于公司内部和员工之间。所以除非它接手一个任务，呃，如果它接手一个工单，它必须完成所有部分。它在处理绿色和橙色部分方面做得非常好，但它在处理红色部分，即**机构知识**方面遇到了困难。而且我相信，呃，现在**编码Agent**变得越来越好。我觉得如果**AGI**出现，第一个**AGI**肯定会是一个**编码Agent**。

<details>
<summary>Original English</summary>

**发言人**: Okay. So I think this is the problem uh that we have. Uh I have four Jira tickets different ones uh sample ones and you can see the green ones that I have uh marked is basically which LLM is or already trained on like API standards or like uh things very they already know it's a general knowledge right that's fine those tasks from the ticket it can pick up and it can do it now there are second part orange ones which we have to teach them actually so you have you know this but do this in this way so all this kind of an orange ular things will fit into you know your agent extension like skills or like uh but the red ones that's what the institutional knowledge is which sits within the company and within the people. So unless if it picks a task uh if it picks a ticket it has to fulfill all of them. It is so good with uh green ones and orange ones but it struggles with the red one with the institutional knowledge and what I believe is uh right now the coding agents are getting so so better. I feel like if there is an AGI coming the first AGI will be a coding agent for sure. uh

</details>

**发言人**: 呃，所以为了解决向**Agent**提供**机构知识**的问题，我们已经有了一个行业解决方案。所以这基本上就是你的**AI投资回报**管道看起来的样子，对吧？所以你有**LLM模型质量**，呃，你有**Agent**，你有**Agent框架**，你的**机构知识**则存在于**Confluence**、**Jira**、**SharePoint**、**GitHub**所有这些地方。基本上，**检索层**就是行业告诉我们能解决这个问题的方案。所以你构建那个**检索层**，然后它会获取所有这些东西并提供给**Agent**，**Agent**应该能够完成，对吧？所以基本上，呃，通过**RAG**或**知识图谱**，实际上可以达到40%的事实准确性，呃，但前提是有一个**已文档化的知识库**。

<details>
<summary>Original English</summary>

**发言人**: so to fix the uh giving the institutional knowledge to uh the agents so we have an industry solution already so this is basically your return of investment on AI pipeline will look like right so you have LLM model quality uh you have agents and you have agent harness and your institutional knowledge sits under conflence jira sharepoint gith GitHub all those things and basically retrieval layer is what industry is telling us will fix that issue. So you build that retrieval layer and then it will fetch all those things and give it to an agent and agent should be able to do it right. So basically uh so 40% uh actu factual accuracy can be achieved through rag or like knowledge graphs actually uh but with a documented uh knowledge base.

</details>

**发言人**: 现在基本上，如果你构建一个**检索层**，它就必须工作。现在我问你一个问题：你们有多少人构建过**检索层**，比如**RAGs**和**MCPs**？好的，太棒了。所有人都构建过。好的，现在问题是，你构建了多少个？你构建了多少个**MCP服务器**？你们有多少人构建过超过20个**MCP服务器**？

<details>
<summary>Original English</summary>

**发言人**: Now basically if you build a retrieval layer it has to work right now let me ask you a question. How many have you built uh retrieval layer things like rags and mcps? Okay, cool. All of them. Okay, now the question is how many did you build? How many MCPS did you build? How many have you built more than 20 MCP servers?

</details>

**发言人**: 好的。好的。看来没有人能打破我的记录。呃，所以，我看到的是，呃，在大多数企业组织中，人们正在构建10到15个，或者20个**MCP服务器**或**RAGs**，呃，在他们的**机构知识**之上，以供**Agent**使用。对吧？所以假设是，如果我能构建所有这些**MCP服务器**并提供给那个**Agent**，我就不需要做任何工作，它会自己完成。但问题是，当你插入这些**MCP服务器**时，基本上所有这些数据输出大多是**不确定性的**，**不可靠的**，而且是**未经测试的**，对吧？所以尤其在工程领域，没有人真正做**评估**。实际上，这更像是一个数据机器学习概念，但我们不做评估。所以对我来说，如果你，抱歉，呃，呃，如果你插入一个**MCP**或**RAG**等，我们只看输出是否产生，而不是它是否真的有价值，是否真的解决了问题。呃，这是我看到的主要问题。我不是在指责别人，因为我就是那个人。我当时想，好吧，让我构建所有**MCP服务器**，插入我的**机构知识**。我要证明**Agent**可以半自主地持续处理**Jira工单**并完成它们。对吧？但每次我构建这些**MCP服务器**时，10%、20%、30%的时间是准确的，但其余的时间我都在为它们做**数据录入**工作。所以实际上我是在填补空白，提出问题。所以基本上，我做的工作比减少的工作更多。呃，所以我认为这是主要问题，我，我实际上处于这个第四阶段，我真的开始手写**领域上下文**。所以我想，好吧，让我写下所有东西来证明这一点，但我真的对做这件事感到筋疲力尽了。

<details>
<summary>Original English</summary>

**发言人**: Okay. Okay. So, nobody beats my record then. Uh so what I see is uh mostly in the enterprise organizations and all people are building like 10 to 15 or like 20 MCP servers or like rags uh knowledge graphs on top of their institutional knowledge and to the agent right so the assumption is if we if I can build all those MCP servers and give that agent I don't need to work anything like it will do but the thing is when you plugging this MCP servers basically all this data coming out is mostly undeterministic it's unreliable and it's untested right so especially in engineering nobody does evals actually it's it's more like a data machine learning concept but we don't do eval so for me if you sorry uh uh if you plug uh an MCP or like a rag and all we see whether the output is coming or not rather than is it really valuable actually is it really solving the problem or not. Uh that's the main problem that I see. I'm not saying pointing other people because I was that person. I was like okay let me build all MCP servers plug in my institutional knowledge. I'm going to prove that point that agents can semi-autonomously can continue and fill those zero tickets and finish it. Right? But every time when I build those MCP servers 10% 20% 30% of time it was accurate but rest of the time I was doing the data enter job for them actually. So I was filling the gaps asking the questions. So basically I'm doing more work than actually doing less work. Uh so I think this is the main problem and I I actually was in this fourth stage where I literally started to write the domain context with handwritten actually. So okay let me write everything and prove the point but I got really exhausted of doing it.

</details>

**发言人**: 好的，所以我不知道有多少人能与这个**饼图**产生共鸣，呃，但大多数企业的**机构知识**大致是这样的。所以如果你看，20%是**过时的**，20%是**不可靠的**。呃，20%到10%总是**在不同地方重复**。而主要问题是，40%的知识始终是**部落知识**，这意味着人们知道事情如何运作，所以它**从未被文档化**。所以，在这种企业环境中，你构建了大约100个**MCP服务器**并插入那个**单体**中，无论你构建多少，它都不会工作，因为你的整个**机构知识**基本上是一个**单体**。呃，我认为，呃，因为你们都来自工程背景，所以你们已经了解**单体遗留系统**向**微服务**的转变，对吧？所以同样地，除非我们将那个**单体知识库**分解成某种**上下文块**，这些**上下文块**对**Agent**有用，只有这样，我们才能真正让它对**Agent**有用，并真正让它们半自主地完成任务。

<details>
<summary>Original English</summary>

**发言人**: Okay so how I don't know how many can you relate uh with this pie chart uh but most of the enterprise uh the institutional knowledge is kind of something like this. So 20% if you see it's outdated, 20% it's unreliable. Uh 20% 10% is always duplicated with different places. And the major problem is 40% of the knowledge is always uh tribal knowledge which means people know how things work. So it's it's never documented actually. So in this situation of an enterprise and you build like 100 MCP servers and plug into that monolith, it doesn't matter how many you build, it won't work because basically your whole institutional knowledge is a is a monolith. Uh I think like because you're all from the engineering background so you already know uh the transformation of monolith legacy system to microservices, right? So in the same way unless we break down that monolith knowledge base into some kind of of a context blocks which are useful for agents then only we can actually make it useful for them uh for the agents and actually make them semi-autonomously can actually do the tasks.

</details>

### 突破知识单体：需求导向上下文

**发言人**: 那么，呃，我们将在这次工作坊中主要讨论那个**单体**，如何打破它，呃，打破它的方法是什么，以及打破之后它如何有用。这是我们需要做的工作，因为呃，呃，**LLM提供商**将专注于**LLM模型质量**，**Agent**将专注于**框架**，而且有一个价值90亿美元的巨大**检索市场**正在专注于**检索**，但没有人会来你的公司修复你的**知识库**。你必须自己修复它，对吧？那么，我们该如何做呢？呃，好的。所以，**需求导向上下文**，呃，这就是我试图提出的解决方案，对吧？所以，基本上，如果我要抽象地概括它是什么，就像我们有呃，**单体服务**，我们有将其分解成**微服务**的过程。我们有**瀑布模型**，我们将其转变为**敏捷**。同样地，当你有一个**机构知识的单体**时，你如何使用一种方法将其转换为**上下文块**。所以这是一种我们可以做到这一点的方法。

<details>
<summary>Original English</summary>

**发言人**: So that said uh we are going to talk in this workshop mostly on that monolith how to break it uh what is the approach to break it and how it is useful uh when once we break it and this is a job we need to do because uh uh the LLM providers will focus on the uh LLM model quality the agents will focus on the harness things and there is a big uh uh retrieval market of 9 billion they're focusing on retrieval but nobody is going to come to your company and fix your knowledge base. You have to fix it yourself, right? So, how can we do it? Uh, okay. So, the demand-driven context uh is what the as a solution I was trying to propose, right? So, basically if I have to give an abstract of it what it is like we have my uh monolith uh services and we have this process of breaking them into microservices. We have waterfall model which we transformed into agile. In the same way when you have a monolith of institutional knowledge how do you transform into a context blocks using an approach. So this is an approach of how we can do it.

</details>

**发言人**: 呃，在开始之前，呃，这只是一个想法。所以，呃，我们已经用一些数据集进行了尝试，并试图证明这种方法是有效的。而且，呃，在三月份，我们已经在**RXV**上发表了一篇**预印本**。所以，如果有人对阅读学术论文感兴趣，呃，你可以通过“**需求导向上下文**”找到它，或者我也可以在工作坊结束后给你链接。

<details>
<summary>Original English</summary>

**发言人**: Uh before starting uh just not an idea. So uh we already tried with some data sets and try to prove this approach works and uh in the March we have published a preprint uh uh in RXV. So if anyone interested in reading academic papers uh you can find it with the demanddriven context or I can I can also give you a link after the uh workshop.

</details>

### 需求导向上下文的工作原理：拉动式策略

**发言人**: 好的。那么它实际是如何工作的呢？呃，当我们向**Agent**提供**机构知识**时，我们基本上是在尝试做一种**推送策略**，对吧？所以我们构建所有东西，然后推给它。所以，在这种方法中，它更像是一种**拉动式策略**。这意味着，例如，假设一个新员工加入了你的公司，对吧？你如何**入职**一个人？你会让他们入职一两天，给他们一些初始的**岗前培训**，然后告诉他们：“好的，这些是**Confluence**链接，这些是**GitHub**，这是一些**文档**你需要遵循的，等等。”然后你只是给那个人分配一个任务。所以你不会说：“好的，去完成所有这些知识的学习，然后回来，我再给你工作。”对吧？所以你只会分配工作项，当你分配工作项时，那个人会开始提问，填补空白。如果那个人非常喜欢文档化，他也会为你**完善文档**。呃，他会逐渐掌握**机构知识**，对吧？同样地，我们不会将所有知识推给**Agent**，而是开始给**Agent**分配问题，就像工作项一样，让它们实际从我们这里**拉取信息**。一旦，呃，拉取了信息，也要求它们以更好的方式，而不是以**单体结构**来**文档化**。所以，如果你看到，这就是四个层面。所以你有一个**单体**，呃，一个框架，它实际上会拉取并创建更好的**上下文块**。如果你了解，你可以把它更多地与**遗留单体**到**微服务**直接联系起来。所以这就是它的工作方式。

<details>
<summary>Original English</summary>

**发言人**: Okay. So how does it work actually uh when we are giving institutional knowledge to agents basically what we are trying to do is we're trying to do a push strategy right so we build everything and we push it to uh to it. So in in this approach it's more pull approach which means for example let's say a new joiny has joined your company right how do you onboard a person so you onboard them for a one two days you give some initial orientation and then you tell them like okay these are the confluence links these are the github this is the some some kind of a documentation you have to follow things and all then you just assign a task to that person so but you're not going to tell okay go and get graduated on on this knowledge and come back then I will give you work right so you'll just assign the work item and when you assign the work item the person will start asking questions fill the gaps if the person is very much into documentation he will also fill the documentation for you uh he gradually uh get his knowledge of of the institutional knowledge right in the same way we don't push all the knowledge to the agent rather than we start giving problems to agents like work items and let them actually pull the information from us and once uh pull the information also ask them to document it uh in in a in a better way rather than in a monolithic structure. So if you so that's the four layers. So you have a monolith uh a framework and it actually pulls and actually creates a good better context uh blocks you can actually relate it to more into a legacy monolith to microservices directly if you have to have an knowledge of it. So this is how it works.

</details>

### 类比测试驱动开发（TDD）

**发言人**: 所以这是一个循环，呃，问题如何传给**Agent**，在第一次尝试中，**Agent**会失败。所以它会说：“你知道吗，你给了我一个问题，但大多数呃，文档我找不到任何东西，我无法完成。然后这些是我需要做的事情来完成这个任务。”它会给出一个**清单**，所以我们完成这个**清单**，就像我们完成这个**清单**一样。所以一旦，呃，问题解决了，它会获取那些知识，并且还会更新，这意味着它会**整理**这些知识到一个特定的地方，这样它可以重复使用，或者其他**Agent**也可以重复使用。这是一个循环。所以想法是，如果我们能通过多个呃，会话，解决多个问题。所以它会逐渐，呃，**整理**你的**知识单体知识库**，呃，并且为你**文档化**。

<details>
<summary>Original English</summary>

**发言人**: So this is one cycle of uh how a problem to an agent and the in the first attempt the agent will fail to do it. So it will say you know what you gave me a problem but most of the uh documentation I couldn't able to find anything I couldn't able to do it then these are the things I need to do to finish this task and it gives a checklist of things so we fulfill the checklist like we fulfill this checklist so once it is uh given the problem is solved it will take that knowledge and also it will update that means curate the knowledge in a particular place so that it can reuse or like other agents can also reuse. This is one cycle. So the idea is if we can do it in multiple uh sessions with multiple problems. So it will gradually uh curate your knowledge monolithic knowledge base uh and also document it for you.

</details>

**发言人**: 呃，你也可以把它与**TDD**联系起来。所以，有多少人呃，做**TDD**，或者说，没有人讨厌**TDD**，对吧？在我呃，是的。

<details>
<summary>Original English</summary>

**发言人**: Uh you can also relate it to TDD. So how many are uh do TDD or like nobody hates TDD right before I uh Yeah.

</details>

**观众**: 好的。好的。

<details>
<summary>Original English</summary>

**观众**: Okay. Okay.

</details>

**发言人**: 所以，呃，同样地，对吧？在**TDD方法**中，我们做什么？我们只编写**失败的测试用例**。我们不首先构建产品。我们只编写**失败的测试用例**。呃，我们看看为了让**失败的测试用例**通过，缺少什么代码，然后我们只提供代码，并逐渐根据**失败的测试用例**构建产品。同样地，我们给**Agent**分配它肯定会失败的问题，然后我们逐渐填补这些空白，在某个时候，它就会变得**半自主**，拥有良好的**机构知识**。

<details>
<summary>Original English</summary>

**发言人**: So, uh in in the same way, right, in in a TDD approach, what we do, we just write the failed test cases. We don't build the product first of all. We just write the failed test cases. Uh we see what is the code that is missing uh for the failed test case to pass and we just give the code and we gradually build the product based on the failed test cases. In the same way we give problems that agent will definitely fail and we gradually uh fill those gaps and at a certain point it becomes semi-autonomous with a good uh institutional knowledge already.

</details>

### 演示：Agent驱动的根因分析

**发言人**: 好的。所以我认为我已经可以跳到，呃，某种**演示**了。呃，所以我将使用**终端**。所以别恨我。呃，我认为你们都来自工程背景，所以我想你们会喜欢**终端**。呃，让我切换到**终端**。好的。好的。所以，在最左边，呃，你看到的是它在底层是如何运作的。所以当你收到一个问题时，呃，**Agent**会如何失败？它如何要求解决问题所需的知识？然后像**领域专家**这样的人，呃，填补这些空白，然后它会为你**整理**一个新的**知识库**，这个**知识库**会好得多，然后**Agent**成功，你再重复处理下一个问题。所以这就是一个循环。所以它如何实现？它可以使用任何**Agent**来实现。呃，它可以在**Cloud Code**或**Copilot**上实现，因为它是一种方法，你可以呃，以任何你想要的方式进行。在工作中我使用**Copilot**。呃，所以我用**Copilot**实现了这个。呃，但因为我相信每个人都更喜欢**Cloud Code**。所以，呃，我用**Cloud Code**创建了这个演示。呃，你可以看到它只是**技能**、**规则**、**Agent**和**钩子**的组合，以及一些存储**知识库**的地方。

<details>
<summary>Original English</summary>

**发言人**: Okay. So I think I can jump into uh some kind of a demo already. Uh so I will use terminal. So don't hate me. Uh I think like all of you from engineering background so I think like you'll like terminal. Uh let me switch to terminal. Okay. Okay. So on the on the far left what uh right what you see is how uh under the hood it works actually. So when you have given a problem uh how does the agent will fail? How does it demand for the knowledge uh that the problem has to be solved and a human like a domain expert and all uh fills those gaps and then it will curate uh a new knowledge base for you which is which is much better and then the agent succeeds and you repeat on the next problems. So that is how one cycle uh things. So how I it can be implemented? It can be implemented using any agent. There is no uh it can be implemented on cloud or copilot because it's an approach you can uh do uh in any way you want. At work I use copilot. Uh so I implemented this using copilot. Uh but because everybody I I believe loves more cloud code. So uh I created this demo with cloud code. Uh and you can see it's just a combination of skills, rules, uh agents and hooks and some kind of a place to save the knowledge base.

</details>

**发言人**: 在中间的面板，你看到顶部是你的**单体**。呃，这代表了你的**Confluence**、**Slack**、**GitHub**等等。但为了演示的目的，我只是放了一些看起来像它们的**平面文件**。呃，所以你的**单体知识库**就会是这个样子。在下面，你看到的是实时情况。所以当它解决一个问题时，它是如何实际地添加新的知识的。呃，所以这就是它的样子。那么，让我…那么，我将要做的是，我将去一个**Agent**那里。

<details>
<summary>Original English</summary>

**发言人**: On the middle pane, what you're seeing on the top is your monolith basically. Uh this is a representation of your conflence, Slack, GitHub and all. But just for a sake of demo, I just put some flat files that look like them. Uh so that is how your monolith uh knowledge base will look like. On the down, what you're seeing is on a live. So when it's solving a problem how it is actually adding the new knowledge uh to it. So this is how uh it is. So, let me So, what I'm going to do is I'm going to go to an agent.

</details>

**发言人**: 好的，我将基本上给一个**事件问题**让它进行**根因分析**，对吧？所以，好的，我所做的是，你还记得在上一张幻灯片中，我展示了**GT样本**，对吧？它是**已文档化**和**未文档化**知识的组合。所以，这个事件也代表了这种组合。所以，有些知识已经记录在你的**单体**中。有些不存在，或者过时，或者类似的情况。而大部分知识它找不到，因为它从未被写下来。所以当我给出这个问题时，它使用我用这种方法开发的**技能**，它会尝试实际地首先去你的**单体**，实际地在**知识库**中寻找已有的信息。所以你可以这样想：

<details>
<summary>Original English</summary>

**发言人**: Okay, I'm going to basically give an incident problem to do the root cause analysis, right? So, okay, what I did is you remember in the previous slide there is a GT samples that I showed, right? It's a combination of uh knowledge that is documented, not documented things at all. So, this incident also represent the same kind of combination. So, there is some knowledge that is documented already on your monolith. some it is not there or outdated or things like that and most of it it doesn't couldn't wouldn't able to find because it's never written down actually so when I gave this problem so it uses those skills that I have developed using this approach and it will try to actually first go to your uh monolith actually on the knowledge base and try to find information on what is uh there so think about it like this so

</details>

**发言人**: 第一部分是**检索**。这意味着它已经在做**RAG**和**MCP**的第一部分工作。但它还在做什么呢？在获取数据之后，它会如何处理数据呢？那是一个缺失的部分。例如，当你给一个新员工新的**Confluence**链接时，员工会去那里，查看，但找不到信息。但他并没有就此止步。他会继续提问。所以，要解决这个问题，就不仅仅是添加更多的知识等等。对吧？这些是目前缺失的下一步骤。我们只是停留在**检索**。所以这是它实际执行的接下来三个步骤。所以你可以看到置信度几乎是1到5，因为它说：这些是它不理解的特定**术语**。实际上这些**术语**和这些**业务逻辑**是不需要的。所以你需要注意的一点是，它所说的这些都是**未文档化的信息**，这意味着它们从未被写下来。所以除非你这样做，否则你永远不会知道哪些东西没有被文档化。例如，如果有人说：“好的，缺少文档，我们需要编写。”好吧，你希望我写什么呢？人们头脑里有那么多东西，我写不了那么多，对吧？它必须以某种方式浮现出来。所以当你给一个问题时，它实际上会浮现出哪些东西没有被文档化，它会告诉我：“好的，缺少这个，我需要在这里有新的信息。”呃，所以我将要做的是，它完成了所有三个步骤。所以，然后我将要做的是，我已经有了一个预先准备好的答案，一个非常高层次的答案。我把它给了它，呃，关于缺少什么信息。所以，好的，这是你要求我解决这个问题所缺少的信息。你现在能解决这个问题吗？呃，我没想到会这样。

<details>
<summary>Original English</summary>

**发言人**: First part is retrieval. That means it's already doing what RA and MCP is doing first part. But what else it is doing is after it fetches the data, what it will do with the data actually. So that is a missing part. For example, when you give a new conference links to a new employee, the employee goes there, looks into it, but doesn't find information. But it he doesn't stop there actually. He continue asking questions. So to solve the problem, then then just adding more knowledge and things and all. Right? Those are the next steps missing right now. It's we just stop at retrieval. So this is the next three steps it does actually. So you can see the confidence score is almost 1 to five because it says these are the particular terminologies. I don't understand actually these terminologies and these business logics uh is not needed. So one thing you need to look at here is whatever it has said this is the undocumented information that means it was never written down. So unless you don't do this way you will never know what is not documented. For example if somebody says like okay there is documentation missing we need to write okay what do you want me to write actually so there is so much in the people's head I can't write so much right somehow it has to surface. So when you give a problem it actually surfaces what is not documented and it tells me okay this is missing I need to have a new information there. Uh so what I will do is so it does all the three steps. So then what I will do is I already have a pre-prepared answer very high level prepare uh answer I gave it to it uh of like what is the missing information so okay this is the missing information you asked me uh to solve this problem can you solve this problem now uh I didn't expected this one

</details>

### 知识库的实时更新与管理

**发言人**: 呃，通知是，是的。我只会说“是”。

<details>
<summary>Original English</summary>

**发言人**: Uh notifications is yes. I'll just say yes.

</details>

**观众**: 它还问我应该用什么虚构的名字。

<details>
<summary>Original English</summary>

**观众**: It asks also what fictional name should I use.

</details>

**发言人**: 好的。我没看到。看，当我进行测试运行时，它没有问我这些问题。

<details>
<summary>Original English</summary>

**发言人**: Okay. I didn't see it. See when I did the test run, it didn't ask me the questions.

</details>

**观众**: 让我们看看。它知道这是一个演示。

<details>
<summary>Original English</summary>

**观众**: Let's see. It knows it is a demo.

</details>

**发言人**: 我训练它去…好的。不，它正在做的事情就是。所以你可以看到，在实时界面上，它已经在添加新的**知识库**中出现的**实体**。

<details>
<summary>Original English</summary>

**发言人**: I trained it to Okay. No, it is already what it is doing is already. So you can see on the live it is already adding the entities that uh the new knowledge base has been come into the place.

</details>

**观众**: 那么**知识库**呃，是作为**文件系统**管理的，对吧？作为**文件系统**。

<details>
<summary>Original English</summary>

**观众**: So the knowledge base uh manage as a file system right as a system of files.

</details>

**发言人**: 为了演示，我只是把它展示为**文件系统**，但它基本上是你的**MCP服务器**。呃，数据会存储在**Confluence**、**Slack**或其他地方。呃，你可以直接插入并使用相同的**MCP服务器**或**RAG**等。所以它不需要是**平面文件**。

<details>
<summary>Original English</summary>

**发言人**: For the demo, I'm just showing it as a file system, but it's basically your MCP servers. Uh the data will stay in conflence, slack or things. Uh you can just plug in and use the same MCP servers or rag and all. So it no need to be a flat file.

</details>

**观众**: 你把它当作你的**持久层**来处理，对吗？

<details>
<summary>Original English</summary>

**观众**: You treat this as your persistence layer for for this,

</details>

**发言人**: 对吧？

<details>
<summary>Original English</summary>

**发言人**: right?

</details>

**观众**: 它就像一个...你用了什么**记忆工具**吗？是的，我会在下一次展示如何看到，呃...

<details>
<summary>Original English</summary>

**观众**: It's like a me do you use any like a memory tool for for this? Yeah, I will show you on the next look like how I'm going to see uh

</details>

**发言人**: 好的，所以它从56个**实体**左右开始，呃，这个，对吧？现在一个问题实际浮现了六个从未被文档化的**实体**。当我把这些信息给它时，它能够实际发现和整理另外五六个从未被文档化的新**实体**。所以它能**发现空白**。它也能从我这里获取信息，并存储信息，新的信息等等。呃，这是其中一个。好的。接下来让我们看看这个繁忙的窗口。我尝试实际做一些事情，但是呃，它没有成功。好的。所以你现在在窗口上看到的是14个**事件**。你已经看到我用一个**Agent**解决了一个问题，对吧？**沟通**。如果我处理14个**事件**，呃，然后我进行14个这样的循环，它是如何运作的呢？所以如果你看左边，那是第一个**事件**，对吧？所以现在它的置信度是1.5，所有东西都很**关键**，所有…所以基本上没有文档化，所以所有东西都是**关键**的，数据严重缺失。所以我开始在第一个**事件**上给出答案，然后我在第二个和第三个以及连续14个**事件**上重复这个过程。但在第14个**事件**上，它基本上实际能够达到4.4的置信度，因为它首先在每个**事件**上都得到了给我的答案列表，而且它也为我文档化了所有东西。所以它逐渐从1.4提高到接近5的知识范围。呃，所以如果你看传统方式，在传统方式中我们做的是解决所有**上下文问题**，对吧？我们必须先处理它，然后我才能把它交给**Agent**。在这个方法中，我们把**Agent**从**消费者**变成了**知识管理者**。所以你不仅仅从我这里获取，我还要告诉你，整个**知识管理**也是你的工作，你必须为之努力。

<details>
<summary>Original English</summary>

**发言人**: okay so it started from 56 entities or something with the uh this one right now one problem actually surfaced six entities that are never been documented and when I gave that information to it it is able to actually discover curate another five or six uh new entities that were never documented. So it does discovery of the gaps. It also gets information from me and also stores information, new information and all. Uh this is one. Okay. Next let's see this is a busy window. I tried to actually do things but uh it didn't worked out. Okay. So what you are seeing on the on the window is like 14 incidents. You have seen one problem that I solved with an agent, right? The communication. What if I took like 14 incidents uh and I just go and have 14 cycles of this thing and how it does? So if you see on the left side it was the first incident right. So right now it has 1.5 confidence and everything is critical every so basically nothing is documented so everything is critical high the data is missing. So I started giving answers to on the first incident then I repeated for the same second and third and continuously for like 14 incidents but on the 14 incidents it basically actually able to go to a confidence level of 4.4 because first it disco on every incident it got the list of answers for me and also it documented everything for me. So it gradually from 1.4 four to almost like five range of knowledge uh it improved. uh so if you look at the traditional way in traditional way what we do is we solve all the context problem right we have to deal with it first then I have to give it to agent in this one we are moving agent from a consumer to a knowledge manager so you just don't consume from me I'm going to tell you but the whole knowledge management is also your job and you have to do it for

</details>

### 知识管理自动化：上下文差距扫描器

**发言人**: 好的，我想我们可以稍微回到幻灯片了。好的，所以我们看到的是，呃，我运行了一个循环，也展示了当我运行15或16个不同循环时的样子，对吧？但是如果你想手动完成，那会非常痛苦，因为我尝试了15个循环之后，没有人会想实际地坐下来和**Agent**一起，你知道，你有一个事件，但你不会和你的**Agent**一起坐着，一直提问，告诉它你的问题，对吧？所以那非常痛苦。呃，但是问题是，我们可以**自动化**这个过程。所以这就是它真正好的地方，也变得有趣的地方。所以这就是重点。

<details>
<summary>Original English</summary>

**发言人**: Okay, I think we can get back to the slides a bit. Okay, so what we have seen is uh we have I have run one cycle and also I have shown how it look like when I run in like 15 or 16 different cycles, right? But if you have want to do it manually, it would be really painful because I tried it after 15 cycles like nobody would like to actually sit with an agent and you know you have an incident but you won't be sitt with your agent and keep actually asking questions and telling you about your problems right so that is super painful. Uh so but the thing is we can automate this process. So this is where actually it's it's really good and gets interesting. So here is the thing

</details>

**发言人**: 你们所有人，我们已经有了所有**工作项**，对吧？我们有**Jira**，我们有**事件**，呃，我们有**客户支持工单**，所有这些类型的**工作项**都已经存在，对吧，存储在档案中。所以为什么我们不能拿它们，实际使用这个框架，呃，并验证你的**单体数据库**，运行**自动化**，实际查看你的现状呢？对吧？

<details>
<summary>Original English</summary>

**发言人**: you all we already have all the work items right we have Jira we have incidents uh we have uh customer support tickets like that all those kind of a work items already there right sitting in the archive so why can't we take uh them and actually use the framework uh and uh validate across your monolith database run an automation and see actually what is the state of your actually right

</details>

**发言人**: 好的，让我看看，让我向你展示它是什么样子的。所以，与其手动操作，如果我们以**规模化**的方式进行这种方法，它会是什么样子？所以你看到的这个演示，几乎所有东西都是预设好的。呃，例如，我有这个演示。我有一个**平台操作Agent**，而且呃，我说：“好的，这些是最近的**事件**。”比如说，我有20个最近过去的**事件**。我有一个**Markdown文件**或一个**JSON文件**，对吧？它有所有详细的描述，等等，呃，评论和所有东西。其余的文件是你的**知识库**。所以它是一个**文件系统**，但你也可以实际连接到**Confluence**等等，仅仅为了演示目的，我把它展示为**平面文件**。现在我尝试做的是，我将获取所有这些**事件**，并验证每个**事件**在我的**知识库**中，然后问**Agent**：“好的，告诉我，呃，有多少文档是好的？有多少文档是我不能信任的，或者说老旧或过时的？以及有多少是实际缺失的，根据这个**事件**没有被文档化的？”所以让我运行它。

<details>
<summary>Original English</summary>

**发言人**: Okay, let me see let me show you how it looks like. So rather than actually doing it manually at a scale if we do this approach. So how does it look like? So the demo that you're seeing is almost like everything is preset. Uh for example, I have the demo. I have like a platform operations agent and uh I'm saying okay these are the recent incidents let's say I have 20 recent past incidents I have uh like an MD file or a JSON file right it has all the details of description of it things and all uh comments and everything and the rest of the files are your knowledge base so it's it's a file system but you can also actually connect with the same way the conflence and things and all just for a demo purpose and just showing it as a flat files now what I'm trying to do is I'm going take all those incidents and validate each incident across my knowledge base and ask the agent okay tell me uh how much of the document is good how much of the documentation is I can't trust it or like old or outdated and how much is actually missing not documented as per this incident so let me run it

</details>

**发言人**: 好的，这会花点时间，所以它会经历三个步骤。所以，第一个是，呃，它生成**探测器**，这意味着它会编写一个**基本测试**来实际测试你的知识。然后它会运行这些测试，然后实际**分析差距**。好的。房间里有点热。

<details>
<summary>Original English</summary>

**发言人**: okay it will take some time so it will take three steps actually so one is uh it generates probes which means a basic test it will write to actually test your knowledge. Then it will run those tests and then analyze the gaps actually. Okay. It's a little bit hot in the room

</details>

**发言人**: 呃，我的意思是，这些应用就像一个巧妙的问题，我想。呃，好的，举个例子，假设你有一个即时调用，**通知服务**没有向客户发送呃，**短信服务**，对吧？所以**通知服务**，然后你提到**Agent**看到的是，是否有关于**通知服务**的文档？

<details>
<summary>Original English</summary>

**发言人**: actually. I mean the apps it's just like a clever problem I imagine. Uh okay for example let's let's say you have an instant call the notification service is not sending uh customer uh messages to uh SMS service right so the notification service then you mentioned that the agent sees is there a documentation related to notification service

</details>

**观众**: 所以它找不到，这意味着你从未编写过**通知服务**的文档。我确实理解什么是**客户短信**等等。当你提到**客户通知服务**时，它是一个**空白**，因为它从未被文档化。或者它获取一个**客户通知服务**，去**Confluence**查看文档有多旧。如果它说，呃，已经一年了，它会告诉你：“看，我查过了。它已经一年了。我不知道是否需要信任这份文档。”或者说是**不完整的文档**。所以如果你看到，它对每个**事件**进行了评分，获取它，并查看你连接的所有**知识库**，然后得到一个整合列表，比如：“好的，**Agent**可以部分处理你给出的**事件**的基本**边缘情况**，因为你的**知识库不完整**。”它会告诉你缺少了多少**部落知识**、**系统信息**、**业务流程**，以及你的**机构知识**中缺少了多少**未文档化的内容**。呃，这些是**探测器**，它还会识别，呃，哪些是**关键的**，哪些是**高优先级的**。这非常重要，因为比如说，有一个**通知服务**的例子，我提到了，对吧？它重复地，呃，出现了大约20次，而你没有…这是你首先需要根据你的文档修复的问题。所以它也会帮助我们实际理解，当你，呃，**分解你的知识库**时，你需要理解什么才是**关键**的，我首先需要关注什么，什么能给我带来价值。所以，它会组织成**关键**、**高**、**中**。所以这就是，呃，我展示的是**平面文件**，但你也可以将它连接到我们使用的各种**数据源**。

<details>
<summary>Original English</summary>

**观众**: so it doesn't find that means you never wrote a documentation and notification service I do understand what is a customer SMSS and all the customer notification service when you mention it's a gap because it's never documented or it takes a customer notification service goes to conflence and sees like the documentation how old it is. If it is says like uh it's like one year old, it will tell you look I looked into it. It's like one year old. I don't know whether I need to trust this documentation or not or like incomplete uh documentation. So if you see it scored each incident it took it and it looked at all the knowledge uh base that you have connected and have a consolidated list of like scoring of like okay partially the agents can handle uh the basic edge cases of the incidents that you give uh because your knowledge base is not complete and it will show you how much of the tribal knowledge is missing system information business process what are actually are missing from your uh uh institutional knowledge when whatever is not documented. Uh these are the probes and it will also identify uh what is critical and what is high. This is really important because let's say there is some kind of an example of notification service which I mentioned right it is repeatedly uh appearing in like 20 occasions and you don't have this is the first that you need to fix as per your documentation. So it will also help us actually understand when you're uh breaking down your uh knowledge base you need to understand what is critical actually what I need to focus on first what makes value for me so organized into critical high medium so this is what like uh I showed the flat files but you can also connect it to the various data sources that we

</details>

**发言人**: 所以第一步基本上是它做了什么，**需求提取**。这意味着每个**事件**，它都会提取一份**信息清单**，列出缺少什么。第二步是它将整合所有缺少的东西。所以它会创建像**系统**和**API**等等，以及有多少是**干净的**，有多少是**陈旧的**，哪些是**不完整的**，哪些是**完全缺失的**。呃，有些是**部落知识**。呃，它还会做这些**分类**，并为你创建一个**看板**。所以会发生什么呢？如果你想修复你的**机构知识库**，基本上就像我们完成**Jira工单**一样，我们必须**文档化**这些缺失的部分等等。当你开始…它也存储在**上下文湖**中，所以它也必须构建自己的，呃，呃，**知识库**。你可以看到性能。所以一旦你修复了**看板**上的东西，呃，知识。所以，这就是我们所看到的，一个是方法，首先，这意味着不是**推式方法**，而是**拉式方法**，如何做它。一个循环或多个循环是什么样子，但是如果你把它放在**自动化规模**上，它会有多大价值？

<details>
<summary>Original English</summary>

**发言人**: So the step one is basically what it does demand extraction. That means every incident it will extract uh the checklist of information what is missing. On the second step is what it will consolidate everything what is missing. So it will create like systems and APS and all and how many are clean, how many are stale, which is incomplete, what is entirely missing. Uh something is tribal. uh those kind of a classification it will also do and it will create a kban board for you. So what happens is so if you want to fix your institutional knowledge base basically you just just like Jira tickets we finish it we actually has to document these missing pieces and all and the the moment you started to so it also saves in the context lake so it also has to build its own uh uh knowledge base and you can see the performance so once you're fixing the sticks on the can uh the knowledge. So that's how so what we've seen is one is the approach first of all which means not the pull push approach but the pull approach how to do it one cycle or multiple cycle how it look like but if you put it in a scale of automation then how much valuable it uh would

</details>

### 知识存储：GitHub与元模型

**发言人**: 好的。现在，呃，呃，重要的问题是…

<details>
<summary>Original English</summary>

**发言人**: Okay. Now, uh uh the important question is

</details>

**观众**: 抱歉。双麦克风。是的，声音有点断断续续。所以，我也会把那个打开。

<details>
<summary>Original English</summary>

**观众**: sorry about this. Double mic. Yeah, it's cutting out a bit. So, I'm just going to put that one on as well.

</details>

**发言人**: 我应该稍后做画外音吗？实际上，

<details>
<summary>Original English</summary>

**发言人**: Should I do a voice over later? Actually,

</details>

**观众**: 我觉得你需要重复一下。我有耐心，谁有耐心等一下。

<details>
<summary>Original English</summary>

**观众**: I think you need to repeat. I have the patience who has the patience for a second.

</details>

**发言人**: 所以问题是，我一直在说“它接收上下文，所以我们提供信息，它会存储”，但问题是它实际存储在哪里？所以我有一个非常**主观的观点**。呃，请听我说。呃，我更倾向于它应该存放在**GitHub仓库**中。呃，因为最终会有人提出一个，你知道，获得2000万美元**种子资金**的**SaaS解决方案**给你。呃，但在那之前，我更倾向于实际把它放在**GitHub**作为**仓库**。为什么？因为如果你从**规模**上看，如果你想这样做，会有多个**Agent**，多个**团队**实际贡献到同一个**知识库**，而且会有**冲突**和**解决方案**，对吧？所以，呃，最简单的方法是使用**GitHub**，因为它实际上内置了，呃，呃，**PR流程**，**审查流程**等等。所以如果多个**领域专家**正在上传文件，或者**Agent**正在贡献，最有效的管理方式是在**GitHub**中，就像这样的结构。另一个好处是，如果你把它放在**GitHub**上，你也可以稍后发布到**Confluence**或**Slack**，或者你想要发布到的任何其他解决方案。呃，所以我更倾向于把它放在**GitHub**上，但如果你想直接集成到**Confluence**等等，你也可以插入并进行。

<details>
<summary>Original English</summary>

**发言人**: So the question is so I was all all the time I was talking about okay it receives the context so we give the information it will store it but the question is where does it actually store it? So I have a very opinionated opinion. Uh hear me out. Uh I prefer uh it has to go to a GitHub repository. Uh because eventually somebody will actually come up with a you know 20 million seedfunded uh SAS solution for you. Uh but before that I prefer uh to actually put it in GitHub as a repository. Why? Because if you look at at a scale, if you want to do this, there will be multiple agents, multiple teams actually contributing to the same knowledge base and there will be conflicts and resolutions, right? So the uh the easiest way to do is using GitHub because it actually comes with inbuilt uh uh PR processes uh review processes things and all. So if multiple domain expert are sitting and uploading the files or like agents are contributing to it the most efficient way to manage is in a GitHub something like a structure like this and the other advantage is also if you put it on GitHub you can also publish it to conference later or like slack wherever you want to publish it to another uh uh solution that you want to use. uh so I prefer to have it on GitHub but if you want to directly integrate it to conflence and all you can also insert do it.

</details>

**发言人**: 接下来是，呃，**元模型**。呃，有多少人知道**元模型**这个词？嗯，也许我可以快速向你展示它是什么样子。所以**元模型**基本上是这样的，对吧？所以，呃，你的**领域**是如何构建的，比如，呃，它是一个**业务流程**吗，或者，呃，它如何与**系统**相关联，**系统**如何与**API**相关联，以及这些呃，**业务术语**或**技术术语**实际链接到哪一个。所以这些类型的关系，**元模型**非常重要。对于我提出的方法来说，它不是必需的，但它是一个附加功能。为什么你需要拥有它呢？现在，把它想象成一张**地图**，对吧？现在你的**Agent**没有任何**地图**来导航你的**知识库**。基本上你所做的是，你倾倒了这么多文件，它需要弄清楚我需要哪个文件，对吧？但你的**文件结构**实际上是你的**元模型**的表示，它实际上知道如何导航。例如，假设你可以修复这个**系统**吗？它会理解如果我进行更改，哪些**业务流程**会受到影响，以及我需要更改或接触哪些**API**。所以，拥有一个**元模型**也很重要。如果你有它，呃，那么它会产生更大的价值。所以，我强烈建议在此方法中加入一个**元模型**。

<details>
<summary>Original English</summary>

**发言人**: Next is uh a meta model. Uh how many are aware of the word meta model in the okay maybe I can quickly show you how does it look like. So meta model is basically something like this right. So and uh how does your uh domain actually structured around like uh is a business process or uh how it is related to a systems how systems are related to uh APIs and how is this uh business jargon or like tech jarens are actually linked to which one. So these kind of a relationship uh meta model is really important. It's not necessary uh for the approach that I have proposed but it's an add-on and why uh you need to have this one is right now think of it as like a map right now your agents doesn't have any map actually to navigate with your uh knowledge base basically what you're doing is you're dumping like uh these many number of files and it need to figure out which file I need to need right but your file structure is actually a representation of your meta model it actually knows how to navigate For example, let's say can you fix this system? It will understand if I make changes, which business processes will be affected and which APIs I need to change or like touch these kind of a things. So, it's also important to have a meta model. If you have it, uh then it will produce more value. So, I strongly prefer to have a meta model along with this approach.

</details>

### 价值与局限性

**发言人**: 好的。所以最后一部分，呃，是它创造了什么价值。所以你已经看过很多幻灯片，看过很多演示。所以就我个人而言，我也需要分享一下，呃，当我使用它时，或者，呃，其他我分享过的人使用它之后给我的反馈是，呃，首先最有价值的是**知道未知**。所以**从未被文档化**的东西，只能通过这种方法才能浮现出来。呃，否则你只会陷入一个无休止的**白板**，写着“这个缺失，那个缺失，我需要添加，我需要添加”，然后一直这样做。所以这是发现，呃，你以前的**工作项**中，所有从未被文档化的东西的最快最好的方法。呃，其次是，呃，基本上我现在可以把工作交给**Agent**，而不是我来做所有这些事情，比如，呃，与其我来做，不如我把所有这些信息交给**Agent**，让它来管理我的**知识管理**。我不想成为它的**知识管理者**。所以让它来做吧。所以这是我看到的两个巨大价值。如果你想使用它，我想你会看到这两个是最有价值的。呃，但这些是我现在看到的其他事情。好的。所以，我也需要告诉你，使用它有什么缺点，对吧？首先，如果你来自一个小团队，或者如果你说：“不不不，我的文档，我的**知识库**真的很好。”我为你感到非常高兴。呃，你就是现在这个世界上，在使用**Agent**方面最幸运的人。呃，对你来说，它可能不是非常相关，除非你有一个非常，呃，非常复杂的**文档**。呃，其次是我已经提过的，手动操作是非常痛苦的，我不建议任何人这样做。如果你只是想为了测试目的尝试一下，你也可以这样做，但是**自动化**是实际使用这种方法的最佳方式。

<details>
<summary>Original English</summary>

**发言人**: Okay. So the last part uh is what is the value it created. So there's a lot of slides that you have seen lot of demos that you've seen. So personally I need to also share like what is the value that I see when we uh I was using it or like uh the other people who I shared with already were using it came back with the feed feedback and told me uh first the most valuable thing is knowing the unknown. So what is never documented is something can be surfaced only by this approach actually. Uh otherwise you'll just end up in u an endless mroboard of like putting tickets on okay this is missing this is missing I need to add it I need to add it and uh keep on doing it. So this is the fastest and better way to discover uh with your previous work items and all what is never documented uh things and all. uh second is uh basically I can now give work to agents rather than I do all those things like uh rather than I become I give the agents all this information let it manage my knowledge management I don't want to be the knowledge manager of it so let let it do it so those are the two big values that I have seen if you want to use it I think like you will also see the those two as the most valuable uh but these are the other things what I seen now. Okay. So, I also need to tell you like what is the drawbacks of also using it, right? First of all, if you are coming from a small team or like if you say like no no no my documentation, my knowledge base is really good. I'm like super happy for you. Uh you're the lucky ones in this world right now with agents. uh for you it might not be really relevant unless you have a very uh very complicated uh uh documentation that you have uh second is I already mentioned the manual manually doing is it's very painful I don't prefer anyone to do it if you want to just try it for testing purposes you can also do it but u automation is the most best way to actually use this one

</details>

**发言人**: 呃，这种方法非常早期，所以到明天，**YouTube**上可能已经有人发布了不同的、呃，比我更好的东西。所以，呃，在**AI**时代，没有人知道，呃，一个**理论**或一种**方法**或一个**应用程序产品**能存活多久。所以目前，我认为这是最好的方法。好的。所以整个工作坊，我们从一个**管道**开始，对吧？关于**投资回报率**。所以**需求导向上下文**实际位于**单体**和**检索层**之间。它所做的是，呃，它实际帮助你构建**整理好的上下文块**。你也可以把它想象成一个**缓存数据库**。所以每次你的**Agent**不需要去“煮海”（boil the ocean）来解决问题，而是如果你有一个良好的**信息上下文块**，大多数时候，80%的时间都是可用的，因为我也相信，它总是遵循**80/20法则**。所以你20%的文档是最有用的，80%是一些**边缘情况**，你需要去查看。所以与其给出100%的东西，你需要找出我的20%是什么，呃，那对**Agent**超级有帮助，并把它当作一个**缓存数据库**，呃，它的**上下文块**。其余的你可以把它当作链接，所以当**Agent**觉得我需要更多信息时，它才会去检查，呃，整个**单体机构知识**。

<details>
<summary>Original English</summary>

**发言人**: uh this is very early this approach so by tomorrow warning on YouTube somebody would have already posted something differently uh better than me. So uh in the in the uh era of AI nobody knows like uh how long a thesis or an approach or an app product going to survive. So for now I see this is the best approach. Okay. So the whole workshop so we started with uh one pipeline right on the ROI and so the demanddriven context actually sits between this monolith and also the retrieval layer actually and what it does is uh it actually helps you build curated context blocks for you. You can also think of it like a cache database that you have. So every time you agent doesn't need to go and know boil the ocean for fixing an issue rather than if you have a good context block of information most of the time 80% of the time that can be usable because what I also believe is it's always the 80/20% rule so 20% of your documentation is most useful 80% is some corner cases you have to look into it so rather than giving 100% of things you need to figure out what is my 20% of that uh that is super helpful for agent and have it like a cache database uh the context block of it using it and rest of it you can leave it like a links so whenever agent feels I need more information then only it can go and check uh the whole monolithical uh institution knowledge

</details>

### 工作坊总结与实践

**发言人**: 好的，所以从这次工作坊中你可以带走三样东西。第一，呃，我希望我能让你们理解这种方法。所以，呃，有一个**GitHub仓库**，我详细介绍了它，还有一个**入门指南**。如果你想回家尝试，你可以尝试。呃，你已经知道这个框架是如何工作的。所以如果你想回家并**重新混合整个方法**，你可以这样做，也请让我知道，呃，我会留下这个，我会与你一起贡献。呃，你有一个我展示过的**上下文差距扫描器**，它已经**实时预设**。呃，我想大概加了20美元。所以也尽可能多地使用它。200，对吧？好的。好的。

<details>
<summary>Original English</summary>

**发言人**: okay so from here what you can take from this workshop is three things one uh I hope uh I makes I made sense of this approach So uh there is a GitHub repo uh which I detailed it out and also a starter guide on it one if you want to go home and try with it you can you can try it. Uh you already have know how the framework works. So you want to go home and just remix the whole approach you can do it and let me also know uh I'll leave this one and I'll join with you for contribution. Uh you have a context gap scanner that I showed you which is live already with presets. Uh I think like added like $20 on it. So hit it as much as possible as well. 200 right? Okay. Okay.

</details>

**观众**: 所以在20美元之后，先到先得。

<details>
<summary>Original English</summary>

**观众**: So after $20 so first serve.

</details>

**发言人**: 呃，所以这三样东西你可以使用，呃，你可以从这次工作坊中带走。好的。所以因为这是一个工作坊，所以我也想让你尝试一些东西。呃，你可以尝试三件事。第一个是，如果你说：“你知道吗，我已经太累了，快四点了，快要去派对了，我不想做。”所以你可以直接去**上下文差距扫描器**，呃，这里所有东西都是预设的，你可以直接尝试一下，运行它，看看它是如何工作的。如果你认为可以做得更好，请告诉我，这样我们可以一起工作。

<details>
<summary>Original English</summary>

**发言人**: Uh so all these three you can use uh you can take away from this workshop. Okay. So because this is a workshop so I also would like to want you to try something. Uh what you can try is three things. One is either uh if if you say like you know what I'm so so tired already it's almost like 4 uh it's almost about to go for a party I don't want to do it so you can just go to the context gap scanner uh everything is a preset here you can just try it out hit it and see how it works if you think it can be done better let me know so that we can work together

</details>

**发言人**: 呃，或者，呃，假设我现在非常技术化，我想知道它在底层是如何工作的。呃，这是一个**GitHub仓库**。呃，它在，呃，也许我把它拿出来。呃，这是一个**GitHub仓库**，它有所有信息。呃，另外还有一个**入门指南**，如果你想尝试的话。但是，呃，如果你仍然觉得不，我想要更简单的。你也可以尝试这个。所以你不需要做任何事情。基本上，拿这个**提示**，呃，拿你现在的一个**Jira工单**或**事件**。如果你已经构建了**MCP服务器**，呃，或者其他类型的东西，你只需要使用那个**提示**，把它提供给你的**Agent**，呃，带着**事件**或**Jira工单**，然后问它，呃，根据这个**事件**或**Jira工单**，给我你的**知识库**的质量，看看有多少是红色的，也就是从未被文档化的。所以你也可以尝试这个简单的方法。我就把它留在这里。也许你可以拍张照片。也许如果有人想的话，我可以切换到幻灯片。酷。

<details>
<summary>Original English</summary>

**发言人**: uh or otherwise uh let's say now I I'm very technical. I want to know how it works under the hood. Uh this is a GitHub repository. Uh it's it's under uh maybe I'll just take this out. Uh this is a GitHub repository and it has all the information. Uh plus there's a starter guide also if you want to if you want to try it out. But uh if you still feel like no, I want much more simpler You can also try this one. So you don't need to do anything. Basically take this prompt uh take one of your Jira ticket or incident that you have right now. If you already built MCP servers uh or like uh any other kind of a things, you just use that uh prompt, give it to your agent uh with the incident or a Jira ticket and ask it uh give me the quality of the knowledge base that I have as per this incident or uh Jira ticket in this way and see how many how much of it comes in red which is never documented. So you can you can try also the simple one. I'll just leave it like this. Maybe you can take a picture. Maybe I can switch to the slide if any anyone want to. Cool.

</details>

### 问答：方法论的实践与挑战

**观众**: 这是你的...

<details>
<summary>Original English</summary>

**观众**: This is your

</details>

**发言人**: 所以这种方法我觉得非常有趣。所以第一个问题是，你是否已经在**规模化**上使用了这种工作方式，或者因为我们看到的大多是**玩具示例**，对吗？

<details>
<summary>Original English</summary>

**发言人**: So this approach find it very interesting. So first question is have you already used this way of working at scale or because we've seen most of the toy examples right

</details>

**观众**: 是的。

<details>
<summary>Original English</summary>

**观众**: y

</details>

**发言人**: 呃，我使用过，呃，但**不是规模化**的。呃，我从更简单的开始，因为你也需要看它的**范围**是什么。比如说，我有一个企业，我在**企业层面**尝试，但我做不到，因为涉及多个**领域**等等。即使我在**领域层面**做，我需要理解，我在**领域层面**尝试了，但即使在**领域层面**，也有太多的**领域专业知识**我需要填补，呃，填补那些空白。所以，我再次缩小到，也许我拥有的最小的**团队**是什么，以及最小**团队的Jira工单**，最小**团队的实例**，以及**团队的Confluence页面**，呃，稍微限定一下范围。然后如果我**缩小范围**，我觉得它会更，呃，更快，更有用。但如果我在更大的范围上做，会发生什么呢？不是一个人拥有整个，呃，**领域专业知识**，所以基本上又变成了，呃，需要五六个人坐下来开始做这些事情。

<details>
<summary>Original English</summary>

**发言人**: uh I used it uh not at a scale uh I started with simpler because you also need to see what is the scope of it let's say I have an enterprise and I try an enterprise level I can't do it because it's multiple domains things and all even if I do it at domain level I need to understand I tried it at a domain level then even at a domain level there is so much of a domain expertise I need to fill it up and uh fill those gaps. So again I cut down into maybe what is the smallest team that I have and the smallest teams Jira tickets the smallest teams instance and the team's confluence page uh with a bit of a scope then if I drill down the scope then I feel like it's more uh fast more useful but if I do it at a bigger scope what happens is not one person has the whole uh domain expertise so basically it again becomes like uh somebody has to come and uh you know five or six people has to sit down and start doing this things.

</details>

**观众**: 是的，我有点担心这可能会在某种程度上对你的团队成员造成**拒绝服务攻击**，因为我们的**LLM**经过**微调**，会不断**获取信息**，不断**获取更多信息**，不断**追问**。所以我认为这对必须进行**问题回答**的工程师来说会很困难。其次，**扫描器**很好，但它仍然建立在这样的假设之上：你的所有团队成员和企业其他部门仍然在使用你的企业，

<details>
<summary>Original English</summary>

**观众**: Yeah, I'm a bit concerned that this might denial of service attack your team members in a certain way because our LLMs are fine tuned to keep eliciting information to keep getting more information to ask follow so I think it will be hard on the engineers that have to do the question answering and secondly the scanner is nice but still built on the assumption that all of your team members and the rest of the enterprise are still using your enterprise it

</details>

**观众**: 嗯，按照计划，他们实际上会填写他们的**工单**，包括所有细节等等。而我从实践中知道，大多数时候情况并非如此。

<details>
<summary>Original English</summary>

**观众**: well as planned that they're actually filling in their tickets with all the details etc and I know from practice that is most of the time not the case

</details>

**发言人**: 那是真的，那是真的，我同意你的看法。即使我去，我的假设也是，即使我去找领导，让他们接受：“嘿，你能给我一些**带宽**吗？或者，呃，你知道，我需要这些人实际坐下来修复**上下文**。”我认为现在没有人会这样做，但我认为这会发生，因为慢慢地，我认为我们正在慢慢地转向**Agent管理者**，**Agent**变得**半自主**或**自主**，我们来管理它们。但在某个时候，必须有人修复这些知识，因为它不会凭空出现。你必须……所以企业的关注点将转向**差距**。这就是我开始说的，我认为没有人关注这个问题。然而，呃，每个人都非常关注**Agent**有多好，**检索**有多好，但**上下文**有多好，呃，你并没有解决它。我想在未来一年左右的时间里，人们会意识到它的重要性，呃，**看板**很快就会成为现实。

<details>
<summary>Original English</summary>

**发言人**: that is true that is true I agree with you even if I go my my assumption is also even if I go to a leadership to buy in like hey can you give me a bandwidth or like uh you know I need these people to actually sit and fix the context. I don't think right at this point of time nobody will do but I think it will happen because slowly I think we are slowly moving towards an agent managers where agents are becoming semi-autonomous or autonomous and we manage them but at the certain point of time somebody has to fix that knowledge because it's not going to come from anywhere you have to so then the enterprise focus will shift towards the gap that's what I started saying I don't think nobody is looking into the problem Yet uh everybody is very focused with agent how good the agent is, how good the retrieval is but how good the context is uh you're not solving it. I think like in down the line in a year or so I think people will realize importance of it and uh the KBAN board will definitely come into reality actually very soon.

</details>

**观众**: 是的。谢谢。

<details>
<summary>Original English</summary>

**观众**: Yeah. Thanks.

</details>

**发言人**: 我觉得实际上是同样一点。我觉得当我们看大型搜索时，实际上是**文档**，实际上是**代码**。只是想知道你是否将其应用于**代码库**？

<details>
<summary>Original English</summary>

**发言人**: I think actually the same point I think when we look at large search actually documentation actually code. Just wondering have you applied it to the code base?

</details>

**发言人**: 呃，我做过，呃，我也将其应用于**代码库**。呃，但我得到了**混合结果**。当我，呃，所以，事情是这样的。当我只使用**代码库**时，它特别好，或者当我只使用**Confluence**或**文本数据**时，呃，它会给出好的结果。但当我将它们结合起来时，不知何故，呃，它会产生**冲突**，因为它会从**GitHub仓库**中创建出一个**理论**，但同一个**GitHub仓库**的文档也存在于**Confluence**上。所以那里就产生了**冲突**：“好的，**真相来源**是什么？代码说应该这样做，我应该按照文档来实现吗？”所以那时候我又需要创建额外的**技能**或**规则**，比如：“好的，如果你在**GitHub**上看到它，你需要给它什么**排名**？这意味着那是**真相来源**。或者如果你没有看到它，那么你必须，呃，在**Confluence**中查找信息等等。”但这些都是我仍在努力解决的问题。所以看到这些空白并修复它们，但我确实看到了，呃，结合这两者的问题。

<details>
<summary>Original English</summary>

**发言人**: Uh I did uh I also applied the code base. Uh but I got a mixed result when I uh so so here is the thing. What happened is when I only use codebase uh it is particularly good or when I only use conflence or like textual data uh like uh uh it gives a good results. But when I combine it somehow actually uh it conflicts because it it creates a theory out of the GitHub repository but the same GitHub repository documentation is also on confluence. So there it gets a conflict of okay what is the source of truth to it code says this should I implement it this way as per the documentation. So then again I need to create an additional skill or rules like okay what is the ranking that you need to give if you see it in GitHub that means that is the source of truth or if you see it if you don't see it then you have to uh look the information in confluence things and all but those are still I'm trying to fix those things actually so seeing the gaps and fix those but I definitely see uh that issue combining those two

</details>

**观众**: 第二个问题是，嗯，有趣的是，实际上是**技能**。因为我们发现，实际上就像你有你的那种，嗯，像这样的过程：运行一个**上下文**并识别正确的，

<details>
<summary>Original English</summary>

**观众**: and the second question is um interestingly actually skills because what we find out is actually like you have your kind of like your um like the process that's like run a context and identify the right

</details>

**观众**: 然后你执行任务，识别，你回去，然后你正在修复**知识库**。

<details>
<summary>Original English</summary>

**观众**: then you do the task identify you go back and then you're fixing the knowledge back

</details>

**发言人**: 好的。

<details>
<summary>Original English</summary>

**发言人**: Okay.

</details>

**发言人**: 呃，我认为我目前构建的**技能**是**静态的**，但如果你没有理解错的话，你更倾向于**演进式技能**，对吧？如果**技能**失败了，它就必须演进，对吧？我同意你的看法，我从未尝试过，但我觉得它必须是那样，因为我也更专注于如何**规模化**地实现它。呃，原因也是，呃，我希望**上下文**在**检索本身之前**就被修复，而不是在**操作过程中**。所以当我第一次开始使用它时，我开始在**操作中**进行，这意味着：哦，我有一个**工作项**，我把它分配给它，它会失败，然后我开始提供**上下文**等等，但这需要很多时间，也需要我很多耐心。所以与其这样做，你知道吗，我打算在**检索之前**就修复**上下文**。所以如果我能，呃，在我回答她的问题时，如果你选择一个团队，你需要修复的**上下文**非常小，所以你可以使用**上下文差距扫描器**这样的东西，也许如果你有一个好的演示专家，我想大概几周内你就可以实际修复你的**文档**，不是100%，但至少60%、70%、80%的良好质量你可以构建出来。所以我的建议永远是，不要在**操作层面**、呃，**实时层面**进行，而是在**检索本身之前**进行，这在这种方法中会好得多。

<details>
<summary>Original English</summary>

**发言人**: Uh I think right now the skill that I have built is static but what you are more proposing if I'm not wrong it's like evolving skill right if the skill fails it has to evolve right I agree with you I never tried it but I think like it has to be uh like that because I'm also more concentrating on how to do it at scale. uh the reason is also uh I I want I want the context to be fixed before retrieval itself not during operational. So first when I started with it I I started doing with when operational which means oh I have a work item I will assign to it it will fail then I'll start giving context and all but it takes a lot of time it takes a lot of patience for me so rather than doing it you know what I'm going to fix the context but before retrieving so if I can uh while I was answering her question if you take a team the context that you need to fix is very small so you can use a uh context gap scanner uh kind of a thing and maybe if you're good have a good demoing expert I think like couple of weeks you can actually fix your documentation not like 100% at least like 60 70 80% of a good quality that you can already build it so my proposal would always be don't do it at an operational level uh at an real-time level but do it before retrieval uh itself that is much better in this approach

</details>

**观众**: 是的，尤其是在你问的问题可能需要五六个不同方面的情况下。

<details>
<summary>Original English</summary>

**观众**: y especially sitting in situations where you ask questions that may need I don't know like five or six different there

</details>

**发言人**: 现在，**Cloud Code**宣布**上下文窗口**达到100万个**Token**之后。我知道我没有任何问题。所以我计算了一下，呃，平均大概是96k个**Token**，因为我尝试了不同的**领域**。实际上每个**领域**我看到大约是96k个**Token**。呃，如果我整合所有东西，比如**Confluence**等等，呃，它很容易就适合**上下文窗口**。实际上，呃，我尝试做了一些实验，你知道，把**图谱RAG**放在那里，而不是仅仅获取所有文件，使用**图谱RAG**来理解意图。但对我来说，现在只是把整个**上下文**放在窗口中，能给你带来比实际进行，呃，**RAG**更多的结果，除非你有一个非常大的，呃，接近一百万个**Token**的**上下文**想要放入，也许那时候你才需要使用更多，呃，**检索机制**来处理，但除此之外，我想，呃，应该没问题。

<details>
<summary>Original English</summary>

**发言人**: right now after cloud code announced 1 million of tokens in the context window. I know I don't have any problem. So I calculated it uh at an average it's like uh 96k tokens because I tried with different domains actually per domain I see like around 96k tokens. uh if I consolidate everything like confluence things and all uh so easily fits in the context window actually uh I tried to do some experimentation around you know a graph rag put them there rather than just take all the files use a graph rag understand the intent but for me just putting the whole context right now in the window gives you more results than actually doing uh uh rack unless you have a very big uh almost around a million tokens of a context that you want to fit in maybe then you have to use a bit more uh retrieval mechanisms between it but otherwise I think like uh it should be fine.

</details>

**观众**: 我有一个问题，呃，我打开了你的**论文**，你能解释一下这个图表吗？比如不同**技术**之间的比较，比如**领域知识**、**战略知识**、**知识获取**，呃…

<details>
<summary>Original English</summary>

**观众**: I have a question uh I opened your paper and could you explain this graph like comparison between different techniques like domain knowledge strategy knowledge access uh

</details>

**发言人**: 呃，哪个？好的。当然。好的。所以，呃，我也引用了其他**论文**。好的。呃，所以，不是直接相关，但你有一篇**ACE**的**论文**，呃，呃，它也做了类似的事情。所以，呃，但**ACE**并不完全是关于，呃，呃，怎么说，**发现和整理**的。呃，如果我没记错的话。也许我需要刷新一下我的记忆。

<details>
<summary>Original English</summary>

**发言人**: uh which one? Yep. Sure. Okay. So, uh I also did the citations from other papers. Okay. Uh so, not directly related but u you have the paper of ACE uh uh which is also does a similar thing. So, uh but ACE is not exactly into uh uh how do you say uh discovery and curation actually uh if I remember it correctly. Maybe I need to refresh my memory.

</details>

**观众**: 你是说，呃，**领域知识**和**战略知识**之间的区别是什么？

<details>
<summary>Original English</summary>

**观众**: What do you mean between uh the difference between domain knowledge and strategic knowledge here.

</details>

**发言人**: 好的。所以**战略知识**。好的。所以，当你在尝试与**AI**进行对话时，就像**Cloud Code**等等，它会更新它的，呃，**记忆**，或者，比如它与你的事物的**关系**等等，对吧？而且，它还会从**聊天历史**中理解我需要记住的最重要的**上下文**是什么。所以当你与它进行**沟通**时，那些**AI改进**中提出的**操作性对话**。所以我的提议不是基于你与**AI**的对话，而是基于你的**领域知识**，那是**已文档化**的。

<details>
<summary>Original English</summary>

**发言人**: Okay. So strategic knowledge. Okay. So what as and all uh are doing is when you are trying to have a conversation with uh AI uh you can see in the cloud code and all it updates its uh memory or like the relationship with your things like that right. So and also from the chat history it understands what is the most important context I need to remember those kind of a things. So when you are in communication with it that operational conversations with AI improvement they propose. So what I my proposal is not based upon your conversation with an AI but rather than your domain knowledge which is documented actually.

</details>

**观众**: 呃，其他人有问题吗？抱歉。何时才能远程**知识**？所以事情是确定的。你如何确保你的**Agent**只指向你本地的相关**文档**，你喜欢？

<details>
<summary>Original English</summary>

**观众**: Uh somebody else has a question. Sorry. When to remote knowledge so things are confident how do you ensure that your agent only points to the relevant documentation in your local you have liked

</details>

**发言人**: 好的，所以当我编写一个从**Confluence**提取的**管道**时，它也实际允许你提供**日期**，以及**上次更新**者，**创建者**等**分析**信息。所以你可以使用它，呃，来实际设置一个**阈值**，比如：“好的，在这个特定日期，所有旧的都视为**过时的**，并告诉我。”不要直接将其视为**过时的**，你要告诉我，因为有时文档可能会**陈旧**很长时间，但它可能是一个**重要文档**。所以它会让你知道，但现在不会做出决定。所以你决定，呃，哪个是**陈旧的**，哪个不是。你没有像**中间层**那样，在**仓库**中存储这个仍然是…

<details>
<summary>Original English</summary>

**发言人**: okay so when I wrote a pipeline for extracting from conflence it also allows actually to give you a date and also last updated who created kind of an analytics on on the space. So you can use it uh to actually put a threshold of like okay on this particular date whatever is is old consider it as an outdated one and let me know. Don't just consider it as an outdated one you let me know because sometimes the document can be stale for so long but it could be an important document actually. So it lets you know but not like take decisions actually right now on this one. So you decide uh which one is stale and which one is not. you don't have like an intermediate layer where in the repo you store this is still

</details>

**发言人**: 好的，所以，呃，当它在**上下文**中被**整理**时，呃，它也会更新一个，呃，**日期**，以及**文档的状态**，比如**陈旧**、**活跃**和**干净**。所以它也会查看：“好的，这是**陈旧的**，我不会碰它，我只会寻找是否有其他新的**文档**。”

<details>
<summary>Original English</summary>

**发言人**: okay so uh when it is curated in the context uh also it updates with a uh date and also the state of the document like stale active and clean so it also looks into okay this is st I don't I'm not going to touch it and I'll just go to look for any other new other documents are there uh in this one

</details>

**观众**: 你认为如何管理**可访问性**？

<details>
<summary>Original English</summary>

**观众**: you think about how to manage access accessible.

</details>

**发言人**: 好的。所以，因为它不是一个**产品**或**SaaS解决方案**，对我来说它基本上就是**GitHub**，所以现在**权限**等并不难实现，因为**GitHub**开箱即用地提供了我可以给谁**权限**，谁可以拥有**读写权限**等等，谁可以**合并**等等。但如果它演变成一个**产品**，例如**上下文差距扫描器**作为一个**产品**，我希望你测试它，因为我为这次工作坊使用**预设**而不是实际要求你上传文件的原因是我不想获取你的**IP数据**。对吧？所以除非它成为一个**产品**，否则你没有任何问题，呃，**GitHub**等等。但如果你有一个针对此的**SaaS解决方案**，呃，那么就看**SaaS解决方案**如何管理它了，对吧？但现在，这种方法与**访问权限**等无关，你如何在你**知识库**上实现这些**访问权限**取决于你。

<details>
<summary>Original English</summary>

**发言人**: Okay. So, because it's not a product or a SAS solution, it's just basically GitHub for me right now permissions and things are not difficult to implement because GitHub out of the box gives me who I can give the permission to is GitHub. who can have write read access things and all who can merge those things and all but in case if it evolves into a product and for example context gap scanner as a product and I want you to test it because the the reason why I was using presets for this uh workshop not actually asking you to upload the files is because I don't want to take your IP data on this one right so unless it becomes a product you don't have any problem uh GitHub and all but if you have a SAS solution for this uh then it's between how the SAS solution will manage it right right now but the approach has nothing to do with the access things and all how you implement those access on on the knowledge is up to you

</details>

**观众**: 你有，所以这当然是关于**文档**的，但你有没有考虑过将其用于一些，比如公司会使用的**中央工具**？比如说，你有一个**平台团队**，你有一个**CLI**，不同的团队正在使用它，所以现在它被不同的**Agent**使用，对吧？

<details>
<summary>Original English</summary>

**观众**: you have so this is of course about documentation but did you give any consideration about using it on some like central tooling that a company would use like let's say that you have a platform team and you have a CLI that the different teams are using and so now it's used by different agents right

</details>

**发言人**: 好的。

<details>
<summary>Original English</summary>

**发言人**: okay

</details>

**观众**: 所以**Agent**也可能会说：“好吧，这个**操作**对于一个**资源**是可用的，但我不想因为有500个**资源列表**就进行500次调用。”

<details>
<summary>Original English</summary>

**观众**: and so the agents can also be like well this action is available for a resource but I don't want to do 500 calls just because I have a list of 500 resource

</details>

**发言人**: 好的。

<details>
<summary>Original English</summary>

**发言人**: okay

</details>

**观众**: 如果工具能做到就好了。我不知道你是否考虑过这一点。

<details>
<summary>Original English</summary>

**观众**: it would be nice if the tool could do that I don't know if if you've given any consideration to this

</details>

**发言人**: 我认为它在组织中就应该这样运作，你必须有一个**中央解决方案**。但你希望如何实现这个解决方案，取决于组织。例如，我们正在做**敏捷**，对吧？所以**敏捷**可以通过**Scrum**、**看板**或**精益**等方式来做，你也可以使用不同的应用程序来做。过程是相同的，但你如何做，你选择哪种方法，以及你在组织中选择哪个应用程序，是不同的。同样地，我们讨论的是**方法**。如果你想在组织中实施它，你可以使用这种方法，你可以以任何你想要的方式来做。我的观点更像是，通过这个，你可以识别出你的**差距**。

<details>
<summary>Original English</summary>

**发言人**: I think that is how it has to work uh in an organization you need to have a central solution for it but how you want to do the solution is up to the organization for example we are doing agile right So agile can do by scrum kban or like lean or something and also you can do different apps to do it. The the process is the same but how you do it which method you will choose and which app will you choose in your organization is different. In the same way what we have discussed is the approach. If you want to put it in the organization you can use the approach and you do you can do it in whichever way you want. My point is more like so with this you can identify gaps in your

</details>

**观众**: 对，你能用它来识别你**工具**上的**差距**吗？

<details>
<summary>Original English</summary>

**观众**: right could you use it to identify gaps on your tooling for

</details>

**发言人**: 好的，呃，当你说**工具**时，是**Agent**的…

<details>
<summary>Original English</summary>

**发言人**: okay uh when you say tooling it's the agentic

</details>

**观众**: 内部工具，我不知道，也许一个团队正在为公司的其他部门构建。

<details>
<summary>Original English</summary>

**观众**: internal tools that I don't know maybe a team is building for the rest of the company

</details>

**发言人**: 基础设施总的来说，对吗？

<details>
<summary>Original English</summary>

**发言人**: infrastructure in general right

</details>

**观众**: 也许吧。

<details>
<summary>Original English</summary>

**观众**: maybe yeah

</details>

**发言人**: 呃，你能给我一个例子，呃，比如？

<details>
<summary>Original English</summary>

**发言人**: uh can you give me an example of uh like uh how

</details>

**观众**: 比如说，呃，我不知道你构建了某种**Kubernetes**之上的**抽象层**。

<details>
<summary>Original English</summary>

**观众**: let's say that uh I don't know you build some sort of abstraction on top of kubernetes

</details>

**发言人**: 好的。

<details>
<summary>Original English</summary>

**发言人**: okay

</details>

**观众**: 你不希望你的开发者一定知道如何处理它。好的。

<details>
<summary>Original English</summary>

**观众**: you don't want your developers to necessarily know what to do with that. Okay.

</details>

**发言人**: 那么你有一个不同的**CLI**或者你有一些东西，对吧？

<details>
<summary>Original English</summary>

**发言人**: Then you have a different CLI or you have something right.

</details>

**观众**: 嗯，但后来就像我说，我不知道，也许你认为他们会一个接一个地发布你的**自定义应用程序**或**企业应用程序**。

<details>
<summary>Original English</summary>

**观众**: Um but then like I say I don't know maybe you thought that they would release one of your custom applications or corporate applications one by one

</details>

**观众**: 但一个团队已经发展到更多地使用它，突然他们有很多，而且他们不想进行那么多调用，或者甚至**Agent**会觉得这效率低下，我希望这个**内部工具**以不同的方式工作。

<details>
<summary>Original English</summary>

**观众**: but a team has grown into using more of that and suddenly they have a lot and they don't want to do that many calls or perhaps even the agent is like well this is inefficient. I would like this internal tool to work in a different way.

</details>

**发言人**: 好的。那样你就能识别出**工具**中的**差距**，或者**性能改进**，就像这个方法对**文档**所做的那样。

<details>
<summary>Original English</summary>

**发言人**: Okay. And in that way you would identify like gap in the tool or a performance improvement kind of like this does for documentation

</details>

**观众**: 实际上可以扩展。

<details>
<summary>Original English</summary>

**观众**: could be extended actually.

</details>

**发言人**: 所以，呃，因为我们已经看到了**业务流程**，对吧？所以它也可以**文档化业务流程**。**业务流程**无非就是应用程序中的过程如何实际运行和执行任务，对吧？所以你可以扩展它，也可以发现**业务流程**中的**差距**，或者它是如何运作的。它可能是它的一个扩展。

<details>
<summary>Original English</summary>

**发言人**: So uh because uh we have seen the business processes also right. So it can also document business process. The business process is nothing but how uh the process in the application it actually runs and does things right. So you can extend it to also find out the gaps in the business process or like how it works. It could be an extinction to it.

</details>

**观众**: 抱歉。你如何确保你知道**更改**？

<details>
<summary>Original English</summary>

**观众**: Sorry. How would you ensure that you know changes?

</details>

**发言人**: 是的。问题的答案是明天，周五，以识别**B1**和**B**，以及**文本**，那是问题。

<details>
<summary>Original English</summary>

**发言人**: Yeah. The answer for question is tomorrow on Friday to identify B1 and B and over text that's problem.

</details>

**发言人**: 好的。所以，呃，当我展示**上下文差距扫描器**时，你也看到了**重复**的指示器，对吧？所以如果今天你有一个文档，明天你有一个**2.0版本**，以及其他东西，它实际上会发现相同的信息在三个不同地方存在，它也会发现。如果你只有一个，它被更改了，它会选择**最新更新**的那个，因为作为人类，你更改了它，所以它会将其作为**真相来源**，对吧？但如果你有三个相同文档的版本，那就是**重复**，它会将其标记为**重复**。

<details>
<summary>Original English</summary>

**发言人**: Okay. So uh when I showed the context gap scanner you also saw like an indicator of duplication right? So if today you have a document tomorrow you have version 2.0 zero and something else actually it will find out the same information is having in three different it it will also will find it. If you have only one it is changed it will take the latest updated one because as a human you changed it so it will take it as a source of truth right but if you have three versions of the same document that's a duplication and it will flag it as a duplicate

</details>

**观众**: 对，但这是一个…你如何确保**性能**？假设一个10万字的文档，你只是更改了一个单词，比如说，其中的一个示例变了，

<details>
<summary>Original English</summary>

**观众**: right but it's a s how do you ensure the performance Let's say document of 100,000 words just change a word like let's say there for example right has changed

</details>

**发言人**: 好的。

<details>
<summary>Original English</summary>

**发言人**: okay

</details>

**观众**: 所以你必须找到，比较那三个**文档**，你使用什么**工具**来确保？

<details>
<summary>Original English</summary>

**观众**: so you have to find compare those three documents tools you use to ensure

</details>

**发言人**: 呃，嗯，我没有完全理解你的问题。实际上。呃，你是担心**Token使用量**吗？比如，我们使用了那么多**Token**，成本节约是多少？是的，正是，**更改**，维护整个**数据库**，对吗？

<details>
<summary>Original English</summary>

**发言人**: uh Um I didn't quite get your question actually. Uh is it like the token usage you're worried about like uh the that many tokens that we used how how is what is the costsaving? Yeah, precisely changes maintain maintain that whole database right

</details>

**发言人**: 我不知道，无论什么，对吗？我的问题是，你所展示的是一种**理想情况**，你有一个**复制品**，然后你重复使用它。但很快你就会有一个**复制品**，你假装它有那个**差距**，但实际上它没有包含**最新信息**，包含**错误信息**。所以你想保留那个。

<details>
<summary>Original English</summary>

**发言人**: I don't know whatever right my question is well because what you presented is sort of a happy path where you have a cup it and then you reuse it but in a while you will have a where you pretend to have that gap but actually it doesn't contain up to date information contains wrong information. So you want to preserve that.

</details>

**发言人**: 啊，好的。好的。呃，所以它可以根据创建时间或上次更新时间进行**标记**。你可以设置这样的**过滤器**。但假设你有一个包含**错误信息**的最新文档。

<details>
<summary>Original English</summary>

**发言人**: Ah okay. Okay. Uh so it can flag as per when it is created or last updated. You can set such kind of a filters. But let's say you have a latest document which has a wrong information.

</details>

**观众**: 对，知道这一点，对吗？

<details>
<summary>Original English</summary>

**观众**: Right. know that right?

</details>

**发言人**: 不，这是真的。呃，但是，例如，作为人类，对吧？你会去看**文档**，你让某人去看**文档**，那个人看了**文档**，并根据**文档**，这应该这样实现。那个人就会这样做，对吧？这并不是**Agent**或人类的问题。

<details>
<summary>Original English</summary>

**发言人**: No that's true. uh but as for example as a human being right so you go and look into documentation you told somebody to look into documentation and the person looked into the documentation and as per the documentation this is be implemented in this way the person will do it right it's not an agent or a human issue

</details>

**观众**: 太晚了。我的意思是，你解决了一个。**Agent**试图假设，所以它正在解决，但**解决方案**是错误的。

<details>
<summary>Original English</summary>

**观众**: too late I mean you solved one and the agent is trying to assume so it's solving it but the solution is wrong

</details>

**发言人**: 好的。

<details>
<summary>Original English</summary>

**发言人**: Okay.

</details>

**观众**: 所以你说有一个**扫描器**，很好。你每天运行它吗？成本会是多少？

<details>
<summary>Original English</summary>

**观众**: So you say there is a scanner fine. Do you run it daily? How much will it cost?

</details>

**发言人**: 你可以有另一个**进程点**，它会尝试查看**上次更新时间**。

<details>
<summary>Original English</summary>

**发言人**: You you can have another process spot that would try to see like last updated

</details>

**观众**: 呃，尝试以某种频率运行一个**进程**，它会**更新知识**。

<details>
<summary>Original English</summary>

**观众**: uh try to see on some cadence try to run a process that will update the knowledge.

</details>

**发言人**: 太棒了。成本会是多少？

<details>
<summary>Original English</summary>

**发言人**: Fantastic. How much will it cost?

</details>

**发言人**: 呃，例如，呃，抱歉，你是在说…

<details>
<summary>Original English</summary>

**发言人**: Uh for for example uh sorry you're saying

</details>

**观众**: 比每天开更多的会议来**入职**某人或…那是一个强有力的说法，但我不认为它会花费那么多，就像**AI**的前提一样。

<details>
<summary>Original English</summary>

**观众**: less than than doing more meetings uh every day to onboard someone or That's a strong claim but I don't think it will cost that much as premise of AI.

</details>

**发言人**: 是的。就像我说的，呃，当我测试它时，没有一个**领域**超过100k个**Token**。实际上。所以我认为我们不会。例如**上下文差距扫描器**，对吧？我不认为你需要每天运行它或任何东西。即使你每天运行，比如说100个**Token**，进行一次扫描。例如，对吧？如果你尝试开始使用所有这些，呃，所有这些**上下文差距扫描器**，我想你甚至烧不掉1美元。我想，如果我没记错的话，它已经有了，哦，你已经准备好了，好的，呃，好的，我现在就取消订阅。但我，我要回去捍卫两件事。一个是**组合系统文档**，所以我同意你的看法。所以**规模**，你必须解决这个问题。

<details>
<summary>Original English</summary>

**发言人**: Yep. As I said like uh when I tested it there is none of the domains which cross more than 100k tokens actually. So I don't think we will for example contact gap scanner right you I don't think like you have to do it like on a daily basis or anything even if you run daily basis like 100 tokens and do one scan for example right if you try to start hitting all of them uh all of you the context cap scanner I think you can't even burn like one $1 I think so if I'm not wrong it already had like oh you're ready okay uh okay I'll I'll cancel the subscription now But I go back and defend two things. One is a compository system documentation for so I agree with you. So scale you would have to solve this question.

</details>

**发言人**: 好的。这也将取决于，**数据变化**的速度有多快。我想不会那么快。你达到了80%左右。

<details>
<summary>Original English</summary>

**发言人**: Okay. which is going to be depend also how fast the how fast the the data change I think not that much you get to like 80%

</details>

**观众**: 是的，**用例** by **用例**，是的。还有其他问题吗？

<details>
<summary>Original English</summary>

**观众**: yeah use case by use case yeah any other questions

</details>

**发言人**: 好的。

<details>
<summary>Original English</summary>

**发言人**: okay

</details>

**观众**: 我怎么知道那是什么？呃…

<details>
<summary>Original English</summary>

**观众**: how do I know that's uh

</details>

**发言人**: 它，它实际会尽可能详细地列出。现在我还没有完全展示它做了什么，只是为了**UI目的**。呃，但每个**工单**，它实际发现了什么，比如，呃，它会写大约100到150行的**Markdown文件**并保存起来。这样你就能获得更多细节，以防你实际想了解。所以为了演示，我只是放了一些，你知道，漂亮的**用户体验**内容在上面，但你也有**详细信息**进行测试。

<details>
<summary>Original English</summary>

**发言人**: it it it actually tries to detail out as much as possible. Right now I haven't actually exposed everything what it did just for the UI purpose. Uh but the all the per ticket what it actually found like uh it writes like a 100 or like 150 lines of uh markdown files and save it somewhere. So that gives you more details in case if you want to know actually. So for for the demo I just put the you know nice UX stuff on on top of it but you also have a detailed information at uh test.

</details>

**观众**: 还有其他人有问题吗？

<details>
<summary>Original English</summary>

**观众**: Anyone else has any questions?

</details>

**观众**: 我可以问一个吗？

<details>
<summary>Original English</summary>

**观众**: Can I have one?

</details>

**发言人**: 是的，当然。请。对。

<details>
<summary>Original English</summary>

**发言人**: Yeah, sure. Go on. Right.

</details>

**观众**: 简单的问题。哈？我毁了它。如果我理解没错，你的主张是：不是填补空白，而是发现空白。但如果把范围缩小到一个团队，几周内就能做到。我的意思是，如果你不感觉到它并继续问这些问题，那就有道理，对吧？所以在某个时候，你有了另一个价值。

<details>
<summary>Original English</summary>

**观众**: Easy one. Huh? I destroy if I translation right your claim is not not fill the gaps uh but discover but if you scope down to a team within weeks you can do I mean if you wouldn't feel it and keep asking those questions then make sense right so at some point you have another value

</details>

**发言人**: 是的，所以你首先做一次，或者在第一次做多次，首先看到整个图景，你的**知识库**的现状是什么。首先在这个层面修复它，然后你再进入**操作**，对吧？你仍然可以实际，呃，你仍然可以继续用**Agent**和**技能**来做。

<details>
<summary>Original English</summary>

**发言人**: yeah so you do it one time first of all or like multiple times at first see the whole picture first of all what is the state of your knowledge base first fix it uh at that level then you go into operations right you still can actually uh also you you can still continue doing it with the agent with skills.

</details>

**观众**: 是的。

<details>
<summary>Original English</summary>

**观众**: Yep.

</details>

**发言人**: 我认为这种提供**知识**的过程，当有新成员加入组织时，会频繁发生。所以，难道不能用**Zoom通话**来替代吗？把它们转换过来，并将其作为**来源**。假设所有的通话或所有的**知识转移**或**介绍**都发生了。或者团队，或者任何新成员加入，提问，你有权访问这些。

<details>
<summary>Original English</summary>

**发言人**: And I think the same process of kind of providing that knowledge is happens pretty frequently when a new member joins the organization. So wouldn't a replacement that be just Zoom calls, transfer them and use them as source. Assuming all the calls or all the knowledge transfers or maybe introductions happen or team or whatever the new member join asking questions and you have access to that.

</details>

**发言人**: 好的。所以你的意思是，你也可以提供所有的**会议记录**，而不是，呃，呃，进行循环，你的意思是，呃，那也可以做到，呃，如果你所有的讨论都是**文档化**的，所有的会议记录本身都是**文档化**的，但我不认为每个人的情况都一样。至少，呃…

<details>
<summary>Original English</summary>

**发言人**: Okay. So you mean like you can also give all the transcripts rather than uh uh doing the cycle you mean uh that can also be done uh if you're only have the all the time you have discussions in everything is documented meetings transcript itself but I don't think like that's the same case for everyone at least uh

</details>

**观众**: 但更容易，我不知道，我不确定。我认为人们在团队中花费的时间，如果你使用**会议记录**，实际上那些是拥有更多**Token**的人，实际上有很多无用的会议，呃，那些**会议记录**实际上…

<details>
<summary>Original English</summary>

**观众**: but easier that I don't know I'm unsure I think the amount of time people spending in teams if you do use the transcripts actually those are the ones actually who which uh have more tokens actually there are so many useless meetings uh the transcripts actually

</details>

**发言人**: 完全同意，但**压缩**只是一部分，然后是**数据库**的一部分。

<details>
<summary>Original English</summary>

**发言人**: totally agree but compression only one and then part of the database

</details>

**发言人**: 可能是，这 again 取决于**机构**与**机构**之间的差异，对吧？所以你是那种更喜欢开会，通过**对话**解决问题，那些**对话**中包含数据，还是你的**Confluence**或类似东西中包含数据。如果你有数据，就使用那些**会议记录**作为你的**知识库**。同时，就像**压缩**一样，它实际是有效的，那更有用。是的。还有其他人吗？还有问题吗？没有。都很好。呃，那么，呃，非常感谢大家参加这次会议。

<details>
<summary>Original English</summary>

**发言人**: could be again it depends upon institution to institution right so are you like more into meetings, have solving problems within the conversations and those conversations has the data or like your conflence or things has the data. If you have it, use that those transcripts as your knowledge base and at the same time like the compression actually that works actually that that is more useful. Yeah. Anyone else? Any questions? No. All good. Uh then uh thank you so much uh for attending this session.

</details>