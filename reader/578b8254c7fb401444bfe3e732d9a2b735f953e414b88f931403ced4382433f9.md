---
author: AI Engineer
date: '2026-06-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=6bmM45jkMDY
speaker: AI Engineer
tags:
  - story-mapping
  - requirement-elicitation
  - value-architecture-design
  - software-development-lifecycle
title: 无法向会议室输入提示词：AI时代软件交付的真正制约因素
summary: 随着人工智能极大地降低了编码门槛，软件交付的瓶颈已从“编写代码”转变为“确定正确的构建目标”。通过引入用户故事地图与VAD模型，团队能够精确锚定核心业务价值，避免“交付速度高但采用率低”的反模式，实现从平庸均值到数量级跃迁的价值跃升。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Visual Labs
products_models: []
media_books: []
status: evergreen
---
### 无法向会议室输入提示词：AI时代软件交付的真正制约因素

在人工智能迅速发展的背景下，**软件开发生命周期**（Software Development Life Cycle: 软件产品从可行性研究到设计、编码、测试和维护的完整过程）的传统瓶颈正在发生根本性转移。过去，编写代码和实现功能是交付软件的主要制约因素，而如今，随着生成式 AI 极大地降低了编码的门槛，真正的瓶颈已演变为**确定正确的构建目标**（Figuring out what to build）。正如 **Visual Labs**（提供数字化转型与咨询服务的技术公司）创始人 **Balázs Horváth** 所言：“你可以向 AI 输入提示词，但你无法向会议室里的人输入提示词。” 这意味着，理解利益相关者的真实意图、引导团队达成共识并挖掘核心价值，依然是机器无法取代的人类专属技能。

为了说明这一点，Horváth 分享了他们公司在今年年初举办的一场**内部黑客松**（Internal Hackathon）。在这次活动中，团队共提出了 21 个 AI 智能体（Agent）的创意，但最终有 17 个想法在评估阶段被直接放弃，原因在于它们无法创造实际的商业价值，或是受限于数据访问权限。最终只有 4 个智能体项目得以落地，并对公司如今的日常工作流产生了深远影响。这一案例表明，在开发效率呈指数级提升的时代，如果不能在源头上甄别价值，盲目追求开发速度只会加速无用软件的堆积。因此，弥合业务需求与技术实现之间的鸿沟，已成为当前最紧迫的课题。

<details>
<summary>Original English Source</summary>

Hi everyone. I am Balázs Horváth and today I will talk to you about what is the last thing that AI will take away from us as people in the software business. So, at a point where writing code is no longer the bottleneck, the real thing is figuring out what it is that you should be building. And that comes down to people skills and being able to work the room because you can't prompt the room. You can prompt your AI.

So, at the beginning of the year, we held an internal hackathon where we had about 21 agent ideas and 17 of those were abandoned because they actually created no business value. We either didn't have data access or it just didn't make sense to build it. And those four were the ones that actually had a very big impact on how we work today. And it's a very good example of just making sure that we are building what is worth building.

</details>

### 摆脱平庸：从“更快马匹”到“汽车”的认知跃迁

回顾过去十三年连接业务与 IT 部门的职业生涯，Horváth 经历了从编写功能设计书、技术规约，到指导团队进行需求提炼的完整演变。在这个过程中，虽然人机交互的介质不断改变，但通过**需求启发**（Requirement Elicitation）获取核心业务诉求的本质从未改变。如果仅依赖 AI 去直接生成解决方案，我们极易陷入“均值平庸”的陷阱。因为从底层逻辑来看，**大语言模型**（Large Language Model）的训练机制决定了其倾向于输出最常见、概率最高的平均答案。

这与汽车先驱**亨利·福特**（Henry Ford）经典的“更快马匹”类比异曲同工：如果福特在当年只去询问用户的需求，他们只会索要一匹更快的马，而不会想象出汽车。同理，如果我们只是向 AI 索取答案，它也只能在已有经验的基础上复制马匹，无法实现维度的跨越。作为软件从业者，我们的核心职责是利用洞察力将 AI 引导出平庸的均值区间，实现从“更快的马”到“汽车”的**数量级跃迁**（Magnitude Shift），从而创造出真正具有颠覆性的产品。为了实现这种高水平的洞察，开发者的技能栈必须从单一的编码转向更深层次的分析工具箱。

<details>
<summary>Original English Source</summary>

And throughout my career in the past 13 years, I've always been the bridge between business and IT and the developers. I started writing, well, initially testings, functional designs, specifications, and then I wrote them. And as a functional consultant, I worked with large ERP and CRM programs in the US and the UK. And then I founded Visual Labs. And essentially, I trained my team on how to elicit those requirements in a way that we can turn them into good specifications for developers to build, for consultants to configure, and most recently now for AI to build. And what's not really changed over the years is how we interact with our customers, how we interact with systems, how we interact with AI is very much changing. But if you can read the room, if you can elicit the right requirements, then you will be able to build more valuable software.

And that essentially the big shift over the past 2 3 years was that getting access to code and being able to build is no longer the bottleneck to the software development life cycle. Now the real bottleneck is getting your people, your stakeholders, your decision-makers into the room and being able to access them and elicit the requirement and being able to spend the time with them. So that's the real bottleneck, figuring out what it is that should be built. Cuz you can prompt your code, you can prompt your AI, you can prompt your whole specification, but you can't prompt your room.

And what a model can't do is very similar to how Henry Ford's analogy of what he said about asking his users or his customers, if he'd asked them what it is that they needed, they would have said they needed more horses. But in reality, he built a car and he made a perfect success of them. So if you're just using AI to make things, build things better, the chances are that you are replicating what already exists because AI by definition is coded to give you the most common answers. So for us, the real job is to make sure that AI moves away from that average into what is better for us. So, we can just got to not a faster horse, but actually produce a car that's a magnitude shift better than what we had. So, it's really an interesting world where being able to write good code is no longer the most important skill to have.

</details>

### 故事地图：重塑人机协作的分析工具箱

随着编码技能的退潮，卓越软件开发的差异化优势已转移到由**用户故事地图**（User Story Mapping）、**商业模式画布**（Business Model Canvas）及设计思维组成的“分析工具箱”上。在这些工具中，**用户故事地图**是梳理系统骨架最为有效的手段。它不仅能让团队清晰地审视用户在系统中的完整旅程，还能帮助团队科学地界定开发优先级。例如，在一个客户支持系统中，主干流程被划分为：
* **联系客户** (Contacting)
* **案件分流** (Triaging)
* **问题解决** (Resolving)
* **结案归档** (Closing)

在这条主干之下，我们可以规划出**最小可行性产品**（Minimum Viable Product）的核心路径：捕获用户意图、自动判定紧急程度、起草基于知识库的回复并将其记录到系统后台。而诸如情感分析、团队协作通知、下一步行动建议以及用户满意度回访等功能，则可以作为第二阶段的**待办清单**（Backlog）逐步迭代。

此外，将这些需求编写为经典的“作为...，我想要...，以便于...”标准用户故事模板，不仅有助于与业务部门沟通，更是向 AI 提供高保真上下文的桥梁。因为大语言模型在训练中学习了海量结构化需求模板，具备极强的模式识别能力，给它提供符合规范的**用户故事**，能显著提升其生成代码的质量与准确度。

<details>
<summary>Original English Source</summary>

Actually, the real skill now is becoming the analysis toolkit, which is things like story mapping, business model canvas, value canvas, and those those good old things that we are so used to using as functional consultants, business analysts, or in the world of design thinking. So, I'd like to zoom in on story mapping because that's the the skill set that I found as the most valuable. So, once you have the story map with the backbones and understand at each step what your customers, your users are doing, that would give them the ability to move forward in their processes. So, here's a support systems user story map: contacting, triaging, resolving, and then essentially closing a case. With this, you can understand different stages of the process, and then capture the user stories beneath them. It is intended to stay at a fairly high level so you can get a big picture, and then you can decide what it is that you want to build and release one like capturing intent, classifying urgency, drafting a grounded answer, and then logging it to a system of record. That's essentially your MVP. Those are the first things that you'd want to build, and those are your first four user stories. And beneath those, you've got the second set of user stories, like reading a sentiment, writing to a team, suggesting next action, chatting checking satisfactions, so on and so forth. Those will be part of your backlog.

So, what it would allow you to get really good results is by honing in on these user stories and making sure that you use these user stories as a means to elicit discussions with your stakeholders, with your business, and then work out what that user story should really be about. So, the first user story second user story would be as a support lead, I need to open cases ranked by urgency so that none of the escalations should slip. So, just make sure that every user story covers these is ideally written in this setup because AI is really good at pattern recognition and it was actually trained on the user story structure because it's a very well-known and well-used setup. So, if you go back to something that's familiar to AI, it will get you better results. And every user story is actually made up of these, you know, well-known structures, the persona, the what, the actual need, and the why. So, by packaging these up and giving it to AI, obviously with the acceptance criteria based on which you can derive the test cases, you will be able to create very good setup and very good results. And then if you just connect these user stories, daisy chain them up, then that will allow you to create a coherent system based on which you can create your specification and then essentially your code.

</details>

### VAD模型：价值驱动的系统设计方法

尽管 AI 重塑了代码生成的路径，但**软件交付生命周期**的底层逻辑依然稳固。在评估和构建任何系统前，我们必须通过以下四个核心问题来审视价值定位：
* **目标客群**：这究竟是谁的问题？（精确量化到具体的用户角色）。
* **成功标准**：对他们而言，怎样的结果才算“赢”？（提供更快捷、更顺畅或更安全的体验）。
* **排斥因素**：什么原因会导致他们拒绝使用该系统？（例如：平台不兼容、操作繁琐或数据安全漏洞）。
* **决策影响**：该系统是否能改变用户的决策？（能否引导他们做出更好的选择）。

为了避免“为了技术而技术”的盲目开发，Horváth 提出了 **VAD模型**（Value-Architecture-Design: 价值-架构-设计模型）。该模型倡导从业务价值（Value）出发，理清支撑该价值的核心业务流程，然后分析底层的技术架构（Architecture）支持，最后才进入具体的系统设计（Design）。这是一种典型的“旧技能，新经济”的体现——尽管方法论是经典的，但在 AI 消除编码阻力的新经济格局下，它的商业回报被无限放大。只有将最聪明的人才和资源从下游的“代码编写”向游的“决策与设计”迁移，才能在这个技术泛滥的时代精准交付真正的业务成效。

<details>
<summary>Original English Source</summary>

So, the software development life cycle doesn't change as much as a result of AI. It's actually the toolkit that we are using is changing. Right. So, when we work with systems and when we think about what we want to build, I always like to ask these four questions as whose problem is this? Whose problem are we actually solving? So, we can name it to a direct person, direct persona, and it's very much quantified. What does winning look like for them? So, when are they actually successful? Are they achieving the right outcome? Can we help them achieve that right outcome in a quick way or a smooth way or a safe way? And what would that make them refuse to use it? It's not available on their platform, it's cumbersome to use, it's the data security aspect applies, so they wouldn't actually use it. And would it change a decision? Ideally, we want to be impacting how a person makes a decision and we'd want to, you know, tilt them to making better decisions. So, does it change a decision and what is the decision that it changes?

So, once you can answer these four questions, then you'll be able to elicit better responses from your AI and just make sure that you track all of these in a good old markdown file in your repository so that AI can access it. It will just get way more context out of it. And you know, if you just did something as generic as build us an agent that handles support, you will not get the answer you want. So, what we always do is go from value, so understand how value is created, what constitutes value, how the process currently flows, what is the underlying architecture beneath it that supports that process, and then you can start the actual design where you can start designing. So, we like to call this thinking process VAD, value architecture design, and this is what we want to always go through. So, always have, you know, value in mind, how we're creating value, what is the value we are creating, what is the value that your customer is looking for, what is the underlying process that supports this, and how you can design a system around it so it best supports the value and the process, and what process changes are needed along the way.

</details>

### 避免反模式：从交付速度转向真实的采用率指标

在 AI 赋予开发团队极高**特征吞吐量**（Feature Velocity）的当下，构建错误产品的代价被成倍放大。典型的**反模式**（Anti-pattern）是“交付率高，采用率低”——团队源源不断地发布新功能，却极少有用户持续使用。为了规避这一陷阱，企业需要改变 KPI，将重点从“上季度交付了多少功能”转向“交付的功能中，有多少被用户深度使用（如使用两次以上）”。同时，必须坚决摒弃“以演示为交付物”（Demo as Deliverable）和“缺乏真实用户测试的 PRD”等自嗨式开发习惯。

要实现这一转变，关键在于在研发链条上进行“逆流而上”（Upstream Shift）的资源重新配置。以往，企业将最聪明的人才放在下游编写代码；如今，编写代码已变得极为廉价，真正昂贵的是“决定构建什么”。因此，应当将最懂业务的领域专家（SME）推向客户一线，参与到“什么值得构建”的决策中。正如 Horváth 的建议，在周一早上开始新项目前，团队应当通过故事地图或商业画布明确价值流向，确保团队在动手前就看清价值所在。这种“先谋后动”的策略，是确保我们在 AI 时代交付真正有价值产品的关键保障。

<details>
<summary>Original English Source</summary>

So, you might ask, isn't this just good old product management? And to certain extent, yes, it is an old skill, it is an old trade that is worth picking up and learning, because this is now becoming the mode, if you will, of how you can elicit the right requirements, how you can build better software, because we all have access to the same tools, so the difference will be who can understand the business need better, because then we can all just have the latest and greatest model write the code for us. So, it's old skill, but new economics, and it's a real shift towards analyst toolkit.

So, what building the wrong thing looks like, if you've got velocity of your shifting shipping new features like crazy, but the adoption is not good. If people are barely using it, that's actually a very very poor pattern, that's what you want to address. If people are trying out new features, they're logging into the new system, we just wiped Google it out, craziest newest thing, but they are not actually reusing it. So, don't look at time of usage and time spent on site. Much rather you got look at the frequency of a certain activity.

Um, if another miss pattern and anti-pattern is if the demo is the deliverable. We want to make sure that people can put things into production. It's really fast to do a demo and it will look nice, but people aren't actually using it. So, the demo system is not a live system. And if your PRD has no real user testers, so if you if you don't gather proper feedback from a real user, then it's chances are it will not make it into a live environment and people will not use it.

So, the big thing here is actually putting your you know your everything is needs to be moving upstream here. So, earlier on before the AI boom, we had our smartest people writing our code, but what now we need to be shifting our smartest people towards our customers, towards the business problems, and we need to be spending more time on deciding what to build because that's the expensive part. Building it has actually become very cheap.

So, couple of things that you can start doing from Monday morning or from the next day is audit the wrong thing, right? Just start figuring out what are the wrong things that you're currently tracking. And just make sure that you are realigning your measurements, your time, what it is that you're looking for. So, the number of features shipped last quarter, that should be eliminated and you should just start looking at the number of features that we shipped that is actually used more than twice. So, that would be a good a good shift in your KPIs and your metrics. And just make sure that you're moving those real subject matter experts to a more customer-facing, client-facing role or position where they have an actual impact on what gets built. And I'm not suggesting that everybody should become a functional consultant or a product manager, product owner. I'm just saying involve them in the decision-making because they have the most experience of what worked in the past and what didn't. And just making sure that gets included in the decision-making of what should be built is a super important aspect. And I still do this I recommend it to everyone to actually start doing a mapping session before you build. Just make sure that you either create a user story map or business model canvas or any old mapping that highlights where the value lives and just make sure that you understand how you create value. So, I hope you found this valuable. It's a lots of lots of old things stitched together that will really make a difference. Just give it on shot if you have a good use case that you want to wipe code. Try building it with user stories first or without user stories and just compare the difference in the results. When I did this for myself, that was the big big shift that I started doing is holy cow, I still need to incorporate user stories in my development. So this way we can build the right thing and not just the next thing. You can scan a QR code to connect with me on LinkedIn. I would be happy to chat further. Thank you so much.

</details>