---
author: AI Engineer
date: '2026-10-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1_lX0m64-aI
speaker: AI Engineer
tags:
  - agentic-system
  - agent-memory
  - intelligence-plane
  - continuous-learning
title: 每个人都拥有相同的 AI 模型：智能平面如何构成 Agent 的核心差异化壁垒
summary: 演讲者探讨了从控制平面向智能平面演进的必然性，提出仅凭相同的大模型与数据无法形成差异化。智能平面贯穿 Agent 架构栈，结合记忆工程、本体与语义层以及持续学习，驱动 Agent 持续自我进化。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Bob Bemer
companies_orgs:
  - General Electric
  - Oracle
products_models:
  - Memories
media_books: []
status: evergreen
---
### 破冰与 Agent 记忆的回顾

[音乐]

>> 接下来我会过几个关键词，大家一起来互动一下。每当我念到一个关键词，如果大家听过，就请举手。首先，听过“Agent 记忆”（agent memory）的人请举手。

看到这么多人举手，我真的非常开心。因为大约一年前，我也做过一次关于 Agent 记忆的演讲，当时全场几乎没人知道我在说什么。那同样是在旧金山的 AI Engineers 大会上。想当年，大概 3 年前，当我说我们需要构建结构化记忆、需要在 Agent 中对记忆进行建模时，大家都觉得我疯了。而现在，在座的每一个人都知道 Agent 记忆，希望你们也已经在自己的 Agent 中落地实现了。

因此，我先快速回顾一下 Agent 记忆，非常简要地过一遍。Agent 记忆本质上就是 Agent 用于保留、复用、召回和提炼信息的机制。我把它称为“4R”（retain, reuse, recall, refine），这样更容易记住。

不过 Agent 记忆本身也有一套分类体系。短期记忆和长期记忆很容易理解；接着是 Agent 记忆的认知功能层面：语义记忆、情景记忆、程序性记忆和工作记忆。

随后我们会深入到具体的实现层面，这也是今天大家会频繁看到的。这些内容我在网上讲过很多次了，大家可以拍照，稍后也会拿到幻灯片。

这些就是记忆的完整分类体系，是我一直以来努力向大家科普的内容，而且过去 3 年我也一直在做这件事。

<details>
<summary>Original English</summary>
[music]

>> I'm going to go through a bunch of keywords and you guys get interactive. I'm going to ask you guys to put your hands up as I go through a bunch of keywords. So, hands up if you heard about agent memory.

That makes me unbelievably happy because I did this I did a talk on agent memory about a year ago and no one in the room knew what I was talking about. So, it was also at AI Engineers San Francisco and once upon a time, maybe around 3 years ago, people thought I was crazy when I was talking about we need to structure memory, we need to model memory in agents. And now everyone here knows about agent memory and hopefully you're implementing it within your agent. So, I'm just going to quickly go over agent memory, just very quickly. So, agent memory is basically how an agent or the memory mechanism an agent uses to retain, reuse, recall, and refine information. I call it the four Rs, it's easy to remember.

Um but there's also taxonomy of agent memory. Short-term, long-term is easy. Then you go into the cognitive function of agent memory, semantic, episodic, procedural, working memory.

Then we go into an implementation that we're going to see a lot today. And I've done this so many times online, but let's take pictures and you guys are going to get the slides as well.

So, this is all the taxonomy of memory, the what I'm trying to educate people on and I've been educating people on for the past 3 years.
</details>

### 从控制平面到软件工厂的演进

但今天的演讲中，我们要更进一步。接下来是另一个关键词：听说过“控制平面”（control plane）的请举手。

很好，举手的人少了一些。举手的人变少了，而我有一个理论：随着我们逐个过这些关键词，现场举手的人数会逐渐递减。最终，如果一切如我所料，全场可能没有人举手，或者只有一两个人举手。

对于控制平面，我们可以给它下一个定义，大多数人都知道它是什么。它本质上是一个集中化管理系统，负责治理你的 Agent，包括它们可以访问哪些工具、可以做什么、不能做什么。现在有很多软件公司都将自己定位为控制平面。毫无疑问，我们确实需要这套系统。但在今天的演讲中，我要带大家走得更远一点。

这只是控制平面的一个基本概念：为你提供 Agent 的身份管理、策略与护栏、权限编排以及全套审计能力。这些就是典型控制平面的核心组成部分。

好了，下一个关键词来了。大家准备好了吗？准备好了吗？

好的，我们继续——“软件工厂”（software factory）。

好的，举手的人更少了。快符合我的预期了，基本上和我幻灯片上预想的情况差不多。

软件工厂实际上是一个很有意思的术语。很久以前，我在通用电气（General Electric）实习过。1968 年，GE 一位名叫 Bob Bemer 的前辈在他的一篇论文中首次创造了“软件工厂”这个词，当时他讨论的是如何以一种可度量、可重复的方式来构建程序。本质上，是他提出了软件工厂这个概念。所以，这并不是 Agent 时代才出现的新词汇，而是计算机科学领域很久以前就已经使用的术语。

我等大家拍完照。

你可以将软件工厂想象成一个能够稳定可靠地批量产出软件的系统，对吧？只要给它设定一系列流程以及构建软件时必须遵循的系统化工作流，然后由 Agent 去执行——通常是多个 Agent 并行执行。同样，现在也有不少公司在这个赛道布局。

<details>
<summary>Original English</summary>
But in this talk, we're going to take it further. So, another keyword coming up. Hands up who's heard of the control plane?

Nice, less so. We're getting We're getting less hands and I have a theory. As we go through the keywords, you're going to see the number of hands in the presentation reduce. Eventually, if things go correctly, there will be no hands or maybe one or so. So, the control plane, we can define it. Most people know what it is. It's essentially a centralized management system for how your agent is governed, with the tools they have access to, what they can do, and what they cannot do. So, there's a lot of different software companies positioning themselves as a control plane. And yes, we do need these sort of systems. But in this talk, I'm going to take you a little bit further.

So, this is just an idea of what the control plane is. So, identity for your agents, the policy and guardrails, the orchestration to permission, and all the auditing. And these are the components of typical control planes.

All right, another keyword is coming. You guys ready? You guys ready?

All right, let's go. Software factory.

Okay, less hands. We're getting there. It's It's We're almost in line with what I have on the slides. So, software factory is actually an interesting term. So, I did my internship at General Electric like eons ago. And software factory is a term that someone called Bob Bemer at GE at the time in 1968, he coined the term software factory in one of his paper where he was talking about how we can create um programs in measurable and repeatable way. And essentially, he coined the term software factory. So, it's not a new term within the agentic era. It's a term that we've used in computer science a very, very long time ago.

I'll wait for people to take pictures.

So, software factory, you can just imagine it as you want to create a system that is able to churn out software reliably, right? You give it a bunch of um processes and systematic workflow it's meant to follow whenever it's building a software, and you have the agents execute this, usually multiple agents in parallel. Again, different companies position themselves in this space.
</details>

### 提出智能平面：信息不等于智能

好了，下一个关键词：“智能平面”（intelligence plane）。

有举手的吗？

好吧，我算失败了，居然有三个人举手。智能平面正是我们今天的主题。

我要像去年在旧金山谈 Agent 记忆时那样，给大家许下一个同样的承诺——当时大家也觉得我疯了。我今天同样承诺：今天我将分享给大家的所有信息、我所说的每一句话，都会让你比当前大多数人领先 6 个月。

去年聊 Agent 记忆时我许下了这个承诺；今年谈智能平面，我依然许下同样的承诺。所以等到明年我再回到这里谈智能平面时，所有人都会举起手来。当然，别拿我的话当绝对真理。

那这个词呢：“AF 代表中途岛”（AF is Midway）。有人听说过吗？

没有吗？那我们来上一堂简短的历史课。二战期间，珍珠港遭到了日本帝国海军的袭击，当时有若干小组负责截获并破译日本军方的通信。

当时一共有三个小组，我们这里只谈其中两个：一个位于华盛顿，另一个位于珍珠港。当时出现了一个代号“AF”。

这个“AF”代表某种含义，并且对整个太平洋战争的结局起到了至关重要的作用。长话短说，这两个小组都截获了大量来自日本海军部队的碎片化通信信息，并且都在尝试破译这些碎片化数据。

珍珠港的小组其实是一群待在地下室里的人，他们数月以来收集了大量的拦截信息并记录在纸上。最终，他们成功破译了代码，推断出“AF”其实就是“中途岛”（Midway）的代号。对吧，“AF”代表中途岛。

当时日军将“AF”作为中途岛的代号。中途岛是一座位于亚洲和北美洲之间的小岛。你可以去查阅这段历史，这关乎对太平洋的控制权。

但我真正想告诉大家的核心，是“控制”与“智能”之间的区别。珍珠港那个蜗居在地下室的小团队，数月来在纸张上记录一切并破译日军的通信——这在本质上就是记忆——正是这种机制让他们成功破译并使美军海军占据了战略优势。

相比之下，华盛顿的团队拥有更加中心化的架构，拥有完全相同的信息，在信息层面没有任何差异；他们甚至拥有更多的资源、拥有控制权，也拥有严密的组织，但他们却得出了对数据完全不同的解读。最终被采纳的，是 Station Hypo 小组密码破译人员的成果，正因如此他们才能提出“AF 确实代表中途岛”这一假设。

我想表达的是：在场的每一个人，使用的都是相同的大模型，拥有的也可能是相同的信息访问权限；但这并不等同于智能，也无法为你带来独一无二的差异化壁垒。因此今天，我们要深入探讨为什么必须开始关注智能平面。

<details>
<summary>Original English</summary>
All right, another keyword. Intelligence plane. Any hands up?

No, I failed. I got three hands up. Um yeah, the intelligence plane is what we're going to be talking about today. And I'm going to make a promise that I did in my previous talk last year when I was talking about agent memory when people thought I was crazy. And this promise is the same I'm going to I'm going to make, which is the information I'm going to give you today, everything I'm going to say, is going to put you 6 months ahead of where most people are today.

So, I made that promise last year talking about agent memory. I'm making that promise this year talking about the intelligence plane. So, when I come back next year and I talk about the intelligence plane, everyone's going to put their hands up. Don't don't quote me.

How about this one? AF is Midway. Who's heard about this?

No? Okay, let's uh do a bit of history lesson. So, in World War II um in World War II uh Pearl Harbor was getting um attacked by the Japanese Imperial Navy, right? And there was a bunch of groups that were meant to be intercepting communication from the Japanese army.

And there were three groups. So, we're only going to talk about two groups here. One group was based in Washington and one group was based in Pearl Harbor. And there was a code AF.

Now, AF stood for something and it was very critical to the outcome of the actual um Pacific War itself. But to cut the long story short, these two groups had a bunch of fragmented information from communication from the Japanese Navy force that they were they were that they were meant to codebreak.

So, they had a lot of fragmented information and basically the one group, which is the group based in Pearl Harbor, a bunch of folks that were basically in a basement collecting loads of information and intercepted messages on paper and storing it for over months, were able to decode this and they found out that AF is actually short for Midway.

Right? AF is Midway. Right? So, the Japanese were using AF as code word for Midway. Midway was a little island located in between Asia and North America. So, this was You can look this up, control of the Pacific.

But, a key thing I wanted to tell you is the difference between control and intelligence. Because that small group that was in Pearl Harbor, located in a basement, and they were deciphering all the um Japanese communication, and using a lot of papers to record everything for months, which is essentially memory, what was able to actually decode and position um the American Navy at an advantage. So, whereas Washington, which was more centralized, had the same information, right? There was no difference in information. They had the same information, probably more resources, and they had control, and they had organization, came up with an entirely different um uh interpretation of the data.

And the one that was chosen was the folks of our Station Hypo, um the code breakers there. And the reason they were able to also do our hypothesis on the fact that AF does mean Mid- Midway.

So, what I'm trying to say is everyone in this room has the same models, probably the same access to the same information, but that doesn't equate to intelligence, and it doesn't equate to you having that unique differentiator. So, today, I'm going to talk about why we really need to start talking about the intelligence plane.
</details>

### 智能平面的架构定义与核心要素

接下来我们来看 Agent 体系的技术栈。我已经多次讲过 Agent 技术栈，大家都清楚它由什么构成；而控制平面只横切了 Agent 技术栈的某一个特定层级。

我今天向大家提出的方案并不是凭空造出的全新事物，它只是一种审视当下软件构建的新思维方式。这就是智能平面：它贯穿了整个技术栈，为身为工程师的大家创造了一个全新的维度——在这里，你构建的 Agent 不仅仅是被编排调用，而且能够从数据和记忆中真正进行学习。

我们从理论走向更具实践意义的概念：什么是智能平面？它本质上是你的 Agent 系统或 AI 基础设施中的一部分，负责让系统去理解，或者让你的 Agent 能够随着时间的推移变得越来越聪明。

它封装了 Agent 应该“知道什么”（即知识）、应该“记住什么”（即记忆）、被“允许看到什么”（即治理与数据权限控制），以及它如何“自我提升”（即持续学习）。这里面其实没有什么全新概念，你们中的一些人已经在做其中的一部分工作，还有一些人听完今天的演讲后就会开始着手实践。这就是控制平面与智能平面之间的差异。大家能跟上吗？都点头了？很好，我们继续。

我带大家梳理一下大多数人经历过的历程以及未来的发展路径。起初，我们都在对模型进行提示词工程（Prompting），拥有提示层或管理提示词的工具；接着演进到能够呈现上下文的工具，即上下文层；如今，大多数人已经进入控制平面时代，大家在寻找或构建用于编排 Agent 的软件系统。而我们接下来的去向、或者大家应当迈向的方向，就是智能平面。

在展开所有幻灯片之前，有一点是我们都可以理解并达成共识的：**信息并不等同于智能**。把这一点牢记在心，我们就可以切入技术细节了。

这就是 Agent 技术栈。我们聊过了 Agent 平面；当我们探讨控制平面时，如果要把智能注入控制平面、或者在控制平面之上叠加智能，你会思考什么？当审视网关与连接性时，你会开始考虑端到端的用户身份如何与数据进行关联绑定。

当你考虑编排时，你会开始思考上下文组装、记忆构建以及上下文生成。再往下深入到记忆核心层——直接跳到记忆核心，因为这是我的核心专长，也就是数据库——在讨论数据库时，我们把思考推向了更深处，开始探讨本体（ontology）、语义层以及记忆。接着是至关重要的基础设施与平台层，这不仅涉及控制平面所提供的部署能力，更延伸到了推理、微调以及持续学习。

这些构成了控制平面与智能平面的全部组件。稍后会有一张参考架构图供大家拍照。

我倒是希望这是我的全新原创，但这个思路其实早已有之。如果有做过网络工程的朋友，对这个概念可能很熟悉：曾经有人提议，在用于查看各类线路路由的管理与配置平台（本质上就是一个控制平面与管理平面）之上，需要建立一个“知识平面”（knowledge plane）。而我现在针对我们正在构建的 Agent 系统所提议的，就是一个“智能平面”。

我们可以用几个公式来表示：
- **Agent = 模型 + 运行载体（harness）**
- **控制 = 治理 + 安全**
- **智能 = 知识 + 记忆 + 学习**

当你引入智能，把知识、记忆与学习融合进来时，它会为你的整个 Agent 构建方式带来乘数效应。接下来我会向大家展示这具体是什么样子。我先确认一下时间，确保能留出时间演示 Demo……大家在拍照，幻灯片稍后会分享给大家。

总结一下智能平面的高层系统组件：目前这些模块可能来自不同的供应商。首先是 Agent 实际执行所在的 Agent 运行时；Agent 运行时需要记忆与知识，上方通常有一个坐落在数据平台之上的记忆管理器；Agent 运行时将记忆轨迹（traces）写入记忆管理器，随后这些轨迹进入持续学习循环，让模型完成更新并重新输入到 Agent 运行时中。

你可以将这些全部映射到我们讨论的各个平面上：数据平面、控制平面、智能平面。关于控制平面和智能平面我们前面已经阐述得很清楚，智能平面正是目前缺失的关键拼图。

<details>
<summary>Original English</summary>
So, I'm going to go through the agent stack. I've spoken about the agent stack. We know what the agent stack is, and then the control plane cuts through a certain level of the agent stack.

Now, what I'm proposing to you is nothing new. It's just a way of thinking about the software you're building today. So, this is the intelligence plane. It cuts through the entire stack, and creates a dimension where you as engineers can start to build agents that are not only orchestrated, but they can actually learn from data and memory as well.

So, we're going to we're going to move from theory into more practical concepts. So, what is the intelligence plane? It's essentially a part of your agentic system or your AI infrastructure that allows you to understand or allows your agent to get better over time.

It encapsulate what the agent should know, which is basically knowledge, what it should remember, which is basically memory, what it's allowed to see, which is just governance, data access, and how it gets better, which is continual learning. So, there's nothing new here. Some of you are already doing some of these things already, and some of you are going to start doing it after this talk.

So, that is the difference between the control plane and the intelligence plane. Are we following? Right? Nodding? Okay, this is good. Let's go.

Um I'm going to take you through this timeline of where most of you have been and where most of you are going to get to. First, we were all prompting the models, and we all had like prompt layers or tools where we can see all our prompts. Then we moved into tools that can allow us to see the context, context layer. And most of you are now in the control plane error, when you guys are looking for softwares or building softwares that allows you to orchestrate this agent. So, where we're going to go to is intelligence plane or where you should be heading to is intelligence plane.

And just to get this out there, throughout all the slides, one thing we can understand and agree on, information does not equal intelligence.

So, take that away, and now we can start getting a bit technical. So, this is the agent stack. We spoke about the agent plane. And when we start looking about let's talk about the control plane. When we start thinking about intelligence in the control plane or intelligence added onto the control plane, we start to think about when you're looking at gateway and our connectivity, you start to think about end-to-end user identity connected to the data. Right? When you start to think about orchestration, you start to think about the context assembly, you start to think about things such as memory and contest construction. Then all the way to the memory core. I'm skipping to the memory core because that's my sweet spot, database. Um we start to talk about database, but we take things further. We start to talk about ontology and semantic layers and memory as well. Then infrastructure and platform is the important bit. Which is where we start to talk about inference, fine-tuning, and continuous learning, right? When we go beyond the deployment that the control plane gives you.

So, these are all the components of the control plane and the intelligence plane. There's going to be a reference architecture that you would be able to take a picture of.

And this idea, I wish I came up with new ideas, but this idea I'm actually proposing to you is nothing new. Um it's been proposed several times. In fact, in if you If anyone's done networking, this might be familiar to you. Um some folks have proposed that there needs to be a knowledge plane on top of management and configuration platforms that are meant to actually see um the the routes of different circuits, which is essentially a a control plane, right? So, a control plane, a management plane, then folks have um uh proposed a knowledge plane. And this is what I'm proposing for the agentic systems we're building, an intelligence plane.

We're going to have a demo. I'm looking at the time to make sure I get to the demo.

And we like equations. Agent equals model plus harness. Then you take that into control, that equals governance plus security. But when you bring intelligence, you add knowledge and memory and learning, it gives you that multiplier effect on your entire on the entire way you're building agents today. And I'm going to show you what that looks like. I'm trying to think, should I go to the demo now or later? Um we'll do a demo version. Oh, I'll go back. People were taking pictures. You are going to get the slides um in a second.

All right. So, everything I talk about within the intelligence plane, I've tried to capture as just high-level system components. So, all of these would be different providers today. Right? So, we have the agent runtime that your agent is going to be executing on. Then your agent runtime needs memory and knowledge, probably has a memory manager on top that sits on top of data platform, and then your agent runtime is able to put in traces of memory into your memory manager, and that could then go into a continual learning loop that allows you to then change models back into your agent runtime.

Right? And you can put this all on the plane that we've been talking about. So, we have the data plane, the control plane, the intelligence plane. I'm not going to go over this cuz we already know what the control plane is. We know what the intelligence plane is, and that's the key thing that is missing.
</details>

### 产业契机与端到端 Demo 对比

在智能平面中，有几个极为关键的部分，我稍后会在演示中呈现。

为什么当下整个产业已经准备好迎接智能平面了？为什么我现在要大谈智能平面？简而言之，我们拥有了前沿 AI 大模型；Scaling Law 让我们能够预测从模型中获得的收益，而开源权重模型也仅仅滞后 3 到 6 个月。但近期发生了一件大事，那就是“决策模型”（decision models）的出现。

这彻底改变了整个技术轨迹以及我们思考这类系统的方式。它促使我从非常底层的架构层面重新思考：审视我的系统，看看有哪些模块可以替换为决策模型？几年以前这是传统的架构设计方式，而今天，在整个检索流水线中都可以嵌入各类模型。

接下来我要切入演示环节。这里是演示项目的二维码，我有点讲超前了。

在这个 Demo 中（稍后大家会拿到源码），由于现场网络状况不太好，我就不进行现场运行了。这是一个简单的聊天界面，里面包含两个分析师 Agent：一个由智能平面驱动的“受监管分析师”（governed analyst），另一个是“朴素分析师”（naive analyst）。受监管分析师建立在智能平面之上，拥有本体层、语义层以及我们在参考架构中看到的所有能力。

为了快速展示拥有智能平面的效果：最直观的收益之一，就是在 Token 经济学（tokenomics）上的节省。Token 经济学涵盖成本、准确率和延迟。我们让这两个 Agent 执行相同的问题：由智能平面赋能的 Agent 明显更加智能，答对率高达 99%，并且消耗的 Token 显著减少——完成任务仅需 32,000 个 Token，而朴素 Agent 则消耗了 200,000 个 Token。此外，它还配备了全套护栏控制与缓存，以及相应的 Prompt 缓存机制。

逆向推导来看，当你开始实现我展示的这些机制时，你所落地的系统一方面针对生产环境进行了高度优化，另一方面也能随着所捕获的数据不断学习和成长。

这里我想重点强调本体层与语义层。因为时间紧张，我会在 Demo 之间做些跳转。

关于本体层和语义层，我向两个 Agent 提出了相同的问题：“什么是交易对手方（counterparty）？”本体层能够带来普通关键字搜索无法企及的准确度提升。在演示中，关键字搜索虽然找到了一些实体，朴素 Agent 没有本体层也能作答，但有了本体层之后，回答质量显著提升，Agent 能够借助本体给出正确的答案。

语义层也是同理。面对没有任何语义层的朴素 Agent，我们询问它“集中度（concentration）是什么含义？”，它回答错误了；而依托智能平面、具备语义层的智能 Agent 则回答正确。虽然这中间的错误率差距可能只有 5%，但对于金融行业或任何关键业务负载而言，这 5% 的差异至关重要。因此，构建好你的语义层与本体层变得极其关键。

大家后续都能访问到这个演示，我现在快速切回幻灯片。

<details>
<summary>Original English</summary>
So, in the intelligence plane, we have a couple things that are actually quite important. I'm going a bit too fast. We have a couple things that are quite important I'm going to show in a demo. And that is what I'm going to be showing in a second.

So, why is the industry ready for the intelligence plane? Why am I talking about the intelligence plane now? So, very quickly, we have frontier AI models. Um the scaling law allowed us to actually predict the benefits we could get from these models, and then we have the open ways are very like 6 months or 3 months behind. But we have we had something that happened recently, which was decision models. Right? And they changed the trajectory or the way that we started to think of these systems. The way I thought about the systems, right? It made me start to think systems that are very fundamental architectural level. Looking at my system and thinking, okay, what here could I replace as a decision model?

So, this was the traditional way we were seeing things a few years ago, and today you can have models all through your retrieval pipeline.

So, one thing I'm going to do is I'm going to go into a demo right here. This is the QR for the demo. A bit going ahead of myself. Here we go.

So, in this demo, which you're going to get the code to, I'm not going to run it live cuz the internet here isn't great as you guys probably know. Um this is a simple chat interface. I have a governed analyst, I have a naive analyst. My governed analyst is built on what is an intelligence plane. It gives it the ontology layer, semantic layer, gives it everything we've seen in that reference architecture.

And very quickly, just to show you the effect of having an intelligence plane. The key thing is having one, saving on tokenomics, right? Tokenomics is cost, accuracy, and latency. And we have two agents that are able to execute the same questions, but the one that is powered by an intelligence plane is a bit smarter. It gets things right 99% of the time. And it does it with less token consumption. In 32,000 token compared to the 200 thousand token with the naive agent. And then we have all of the guard controls in place and the cache as well. And we have some prompt caching mechanism as well. So, when you actually start I'm working backwards here. When you start to implement some of the things I'm going to show you to you in a second, you start to implement systems that are able to actually one, be optimized for production, and two, learn and grow with the data that you're capturing.

So, over here I just want to talk about the ontology and the semantic layer. I'm kind of skipping between demos here cuz we're short on time.

So, with the ontology and semantic layer, I asked the question uh to both agents around um what was a counterparty, right? And the ontology layer adds a level of accuracy that you can't get by just doing simple keyword search. So, in the demo, this is a keyword search where we're able to actually find some um entities, right? And the agent was able to answer without the ontology, but with the ontology, the answer actually improves and it gets the right answer using the ontology. Same with the semantic layer.

The agent the naive agent without any semantic layer, we asked it a question and it got the we asked it what does concentration mean? And it got it wrong. The naive agent got it wrong, whereas the semantic the intelligent agent built with the semantic play with the intelligence plane got it right. And now that margin of error is just five 5%. But when you're working with the finance sector in any mission critical workload, that becomes very critical. So getting your semantic layer built out, get your ontology layer built out, it becomes very important. I'm going to you're going to get access to this demo and I'm going to go back to the slides very quickly.
</details>

### Oracle 基础设施实现与五大关键支柱

我们在智能平面中集成了诸多模型，刚才的演示实际上完整落地了这套架构与模型体系。

那么，你和你的团队目前应该做什么？
1. **将记忆视作数据**。不要将其视为独立孤立的事物，明确记录你的实体与定义。
2. **将数据权限下沉至数据层**。在 Oracle，我们提供的功能支持轻松实现这一点并捕获轨迹。记忆就是你的护城河，你必须拥有属于自己的记忆资产。

在 Oracle，我们对照此前展示的参考架构，提供了与之映射的产品功能与系统组件，支持你构建属于自己的智能平面。这意味着你拥有了所需的全部工具，去构建一个能够随着 Agent 运行与开发而持续学习进化的系统。

这里我重点谈谈五个核心领域：**记忆**、**安全**、**深度数据安全**、**私有化推理**，以及**本体与语义**。

首先是 **Agent 记忆**。前面已经介绍过，在 Oracle 我们将 Agent 记忆封装成了一个 Python 包，把记忆工程打包整合，让开发者无需为 Agent 记忆的复杂实现操心。该 Python 包会自动生成上下文卡片，省去了手动构建的繁琐。同时，你必须开始捕获记忆轨迹，因为这些轨迹将成为模型微调的数据资产。这张幻灯片展示了记忆工程与上下文工程的结合点，大家拿到幻灯片后可以仔细查阅。

Agent 记忆与 Oracle AI 数据库正是我们刚刚在演示中涵盖的内容。

下一项是**深度数据安全**（deep data security）。昨天和今天我与一些同行交流，他们谈到 Agent 的身份管理以及他们采用的不同方案商。在 Oracle，我们将安全机制构建为数据库的一等公民。借助深度数据安全产品，应用上下文、数据访问权限以及用户的行级权限可以直接透传并下沉到数据层。这意味着 Agent 可以继承其所代表用户的身份，且仅能访问该用户被授权查看的数据。

演示中展示的系统正是基于这套基础设施运行的。其工作逻辑非常直接：分析师对应身份提供商，身份提供商定义了该分析师拥有的所有数据访问权限，我们将这一权限透传给 Agent，Agent 继承该权限，从而严格限制了该特定 Agent 的数据访问范围。

接下来的内容关于**私有化推理**。许多金融行业的企业希望将推理完全部署在本地私有环境中。为此我们提供了私有 AI 服务容器，其中包含了在本地托管 Embedding、LLM 推理以及重排器（Re-ranker）所需的全部基础设施。这一切都围绕着构建自主可控的智能平面展开。当然，如果选择上云，Oracle Cloud 上也托管了各类模型（例如 Grok 模型以及部分 OpenAI 模型）。无论是物理隔离环境还是云端基础设施，Oracle 内部都提供了完备的组件支持。

<details>
<summary>Original English</summary>
So there's a bunch of models that we're adding into the intelligence plane and the demo I showed you actually has all of these models and all of this architecture in place.

So what should you your team be doing now? One, you treat memory as data. Right? Don't look at it as different things. Write down your entities and definition.

You push entitlements into the data layer. Over Oracle, we have features that actually enable you to do this very easily and capture traces. So memory is is basically your moat. You need to own your own memory.

So over Oracle, we have this reference architecture we saw before. But at Oracle, we have product features that map to it. So we give you the system components to build your own intelligence plane. So that means that you have all the tools you need to build something that actually learns and grow as you continue to execute build as you continue to build and execute your agent. I'm going to touch on a few ones. Memory, security, deep data security, private inference and ontology and semantics.

So these are the key five areas I want to touch on very quickly.

So agent memory. We've spoken about it, but now what we did at Oracle is we launched agent memory as a Python package. We put memory engineering into a box, which allows you to just not worry about all of the complexities of making agents remember, we just convert it into a Python package and it generates context card for you where you don't have to actually do it yourself.

Then, one thing you have to actually have to start capturing is your memory traces because this become data for fine-tuning.

So, right here we have a slide that just shows where memory engineering and context engineering meets and this is for you to take and go through when I give you the slides. I'm just going to skip through this very quickly.

So, agent memory and the Oracle AI database is what we just covered in the demo. I skipped it. But, the next thing is deep data security. I spoke to a few folks yesterday and today and they were talking about agent identity and how they were using different solution providers for it.

In agent in Oracle, one thing we did is we made security a first-class citizen of the database. Which means with a product called deep data security, you can take all of the context of your application and the data access and row access of your user and we propagate that into the data layer. Which means your agents can take on the identity of the user it's acting on behalf and access the same data that it's only allowed for is only that the user is only allowed to access.

Fumbling my words there.

Okay. So, all of this is all great including the demo I showed you it uses all of this infrastructure I spoke about and I showed you.

And this is how deep data security works. That's right. We have the analyst, we have our identity provider. The identity provider provides all of the data access that the analyst is meant to have and we can propagate that into the agent and the agent inherits that as well. And that limits all of the data access for that particular agent.

Okay. The next couple of slides I'm going to talk about private inference. Right? A lot of you work in finance companies where you want to actually have your inference on prem. So, we have the private AI service container which contains all the infrastructure you need to host your own your own embedding, your own LLM in your own LLM inference, and re-rankers.

And this is all around owning your own intelligence plane. So, giving you the components. But, if you want to go to the cloud, we have Oracle Cloud where we host some of these models that you're hearing about. So, Grok models and some Open AI models as well. Either way, air-gapped um infrastructure or cloud infrastructure, you have the components within Oracle itself.
</details>

### 开源项目 Memories、决策模型与持续学习

在结束之前，我还有第二个演示。这是我构建的一个名为 **Memories** 的开源工具，旨在向大家展示如何真正切入智能平面领域。

正如大家所提到的，目前已经有人在研究 Agent 记忆；而在一个 Agent 记忆系统内部，可以通过引入各类特定模型来提升系统本身的性能表现。决策模型便是其中之一。本例使用了三种不同的模型：决策模型、Embedding 模型和重排器。

通常在我的 Agent 记忆系统中都会配备这些模型。在智能平面的理念下，既然明确了必须自主掌控记忆资产，我便可以着手对其中的一些开源模型进行针对性微调，这也正是我们在此处所做的。

我们重点看一看记忆路由（memory routing）：记忆路由是指接收来自上下文层或大语言模型的输出，并将其精准路由到正确的存储介质中。无论输出什么内容，系统都能将其分流至对话记忆或工作流记忆。通常大家会用硬编码来实现这一逻辑，但借助决策模型，这一过程会变得极其简单且成本低廉。

这里展示了用于记忆路由的微调模型及其训练过程：我们对 Equine 模型进行微调，使其成为一个决策模型。微调所需的数据来源于此前我与 Agent 的交互对话，我能够据此对其记忆类型进行分类标注。

这让记忆路由变得非常轻量高效。一旦有信息输入，你可以借助决策模型以极低成本将不同类型的记忆精准路由。

记忆路由、Embedding 和重排，是大家当下最容易落地的切入点。一旦理解了智能平面，捕获记忆轨迹并进行有效格式化，进而重新训练模型，你就能在质量提升的同时，在某些场景下获得更低的响应延迟。

回到幻灯片做最后的总结。在 Oracle，我们通过多种方式帮助开发者构建 Agent，其中之一就是**私有 Agent 工厂**（private agent factory）。这是一个无代码平台，通过拖拽即可构建 Agent，并且在内部完整集成了控制平面能力；同时它也内置了我们跨产品线统一构建的 Agent 记忆系统。

私有 Agent 工厂同样构建在 Oracle AI 数据库之上，因此具备我前面提到的全部记忆核心功能。此前我已经演示了具备与不具备本体层、语义层对 Agent 准确率带来的显著影响。针对同一个问题，系统可以结合语境语义给出精准答案。虽然在数据上看准确率提升幅度似乎很小，但在关键业务场景中，这微小的差距可能就决定了企业是否会因违规处理欺诈交易而面临高达 1 亿美元的巨额罚款。

最后我们简要谈谈持续学习。刚才的演示实际上就是一个持续学习的过程。持续学习可以发生在 Token 空间、权重空间，或者当采用 Prompt 缓存时发生在隐空间（latent space）。

核心的结论是：作为系统的开发者和工程师，我们必须**拥有属于自己的记忆资产**，做好记忆轨迹的捕获工程，并将其构建进一个能够实现持续学习的闭环系统中。

我的演讲到此结束。时间有些超了，这里是刚才演示项目的二维码，大家可以扫码获取；更欢迎大家到 Oracle 展台与我交流，展台同样有这个二维码以及其他技术资料。感谢大家的时间！

<details>
<summary>Original English</summary>
All right. So, I have a second demo before I go off.

So, this demo is an open-source tool that I built called Memories. And it's just to show you what how you can actually start to get into the intelligence plane domain.

So, right now there are people working on agent memory, like you guys have mentioned. And within an agent memory system, there are other ways you can start to bring in models to improve the system itself. So, decision model is one of it, and this one makes ex- uses example of three different models. A decision model, an embedding model, and a re-ranker.

And within my agent memory system, I typically have these models. But, with the intelligence plane or with an understanding that I need to own my own memory, and I own my own memory, I can actually start to fine-tune some of these open-source models. And that's what we're doing here.

So, over here in memory routing, I'm just going to focus on memory routing for a second. And what memory routing means is we get some output from the context layer, or we get some output from our LLM, and what we're able to do is route it to the right store. So, whatever comes out, I can route it into conversation memory or workflow memory. Normally, you would do this using some code, but with decision models, this becomes very easy and very cheap.

So, right here we have some fine-tuned Oh, skipped it. Let's go back.

All right. Right here we have some fine-tuned models for memory routing, and we can see how it was trained. So we fine tune the equine model and we use it and we fine tune it into a decision model. The data that we use to fine tune is all here and obtained from the conversation I was have been with the agent and I was able to classify what type of memory it was.

And this allows you to do memory routing very easily. So once you get any information coming in, the different types of memory you want to route it effectively and cheaply, you can do that with decision models.

So memory routing, embeddings, and re-ranking are some of the lowest hanging fruits you guys can actually start to work with today. Once you understand your intelligence plane, you're capturing your memory traces, you're formatting them effectively, and you're retraining the models. And you get the benefit with improvement in quality and in some cases reduction in latency as well.

Okay, so we're going to go back to the slide again. We're going back and forth a few times, which is good. Um and we're just going to wrap up. So there are different ways we're helping developers build agents in in Oracle. And one of it is private agent factory. And this is a no code platform we can just drag and drop and build your agents and have the whole control plane at least within the private agent factory. And the private agent factory also has the same agent memory system that we've we've been building across all our product surfaces.

So again, the private agent factory is built on top of the Oracle AI database, so you get all of the memory core functionalities I've been talking about. I already showed the ontology and semantic layer the effect it has on the accuracy that you get within agents that have and don't have ontology and semantic layer. But again, Oracle gives you all the infrastructure and components to build all of this.

So you can ask the same question with and without meaning, right? So we've already done the demo. Again, I skipped I'm kind of like going around the slides and the demos, but you saw what we had with ontology layers and without ontology layers and the accuracy improvements can be very minimal, but in mission-critical workload, they can mean getting a 100 million fine for handling fraudulent transactions or not.

Okay, so we touched on continual learning a bit. What we saw in the demo was continual learning. And which is there different ways you can look at continual learning in token space and in weight space and also in in latent space as well if you're going into the prompts caching. So we've just gone over this. I'm not going to rehash this again.

But one of the key thing and the key takeaway here is is developers and engineers of these systems, we need to actually own our own memory, engineer the capturing of traces, and actually build it into a system that allows for continual learning to be possible.

So I'm going to end right here. Um I think I'm going over time and I'm going to give you guys the QR code to the demo I just showed. So if you just scan this, but the best thing is you can come meet me at the Oracle booth and you will get this QR code again along with other technical assets and we can have a conversation. Thank you for your time.
</details>