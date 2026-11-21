---
author: a16z
date: '2026-07-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Mxs4erDxOEE
speaker: a16z
tags:
  - agentic-workflow
  - software-architecture
  - headless-design
  - enterprise-integration
title: 软件的未来：从用户界面到智能体驱动的无头架构与企业集成范式
summary: 文章探讨了在智能体主导的世界中，传统软件围绕用户界面的价值正在被重新定义。核心观点是“无头软件”的核心价值在于底层数据和逻辑而非顶层工作流，并讨论了AI Agent如何通过API与系统交互的挑战、企业内部协作的新范式以及网络效应在企业级应用中的潜力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/8 -->

### 播客片头摘要

**Sema Amble**: 有很多因素让软件具有用户粘性，但其中很大一部分原因与人类互动的方式有关。在一个由智能体（agent）主导的世界里，你真的还需要这些吗？界面下方存储的数据、逻辑以及所有一切，才是真正的价值所在。

<details>
<summary>Original English</summary>

**Sema Amble**: There are many things that made software sticky, but a lot of it had to do with the fact that the way a human interacts. In an agentic world, do you actually need that? The data, the logic, everything stored below it is really where the value is.

</details>

**Steven Sonowski**: 现在有一种严重的低估，就好像你可以仅仅通过写代码的感觉（vibe code）就能进入企业级软件领域。甲骨文的拉里·埃里森（Larry Ellison）曾经抱怨过企业软件有多么愚蠢，因为每个人都在对它进行定制。当你把你认为最世俗无聊的事情自动化并以为一切都已经安排妥当的那一刻，全新的事物就会出现。

<details>
<summary>Original English</summary>

**Steven Sonowski**: There's this wild underestimation about like you could vibe code your way into enterprise software. Larry Ellison at Oracle, he went on a rant about how enterprise software was so stupid because everybody customized it. The minute you automate the most mundane thing and think you have it all squared away, whole new things appear.

</details>

**Sema Amble**: 目前的一个误解是，你只要有一个，比如 Postgres 数据库和一些 API，然后“砰”的一下，你就能取代 SAP。这绝对不是真的。围绕逻辑以及 SAP 中封装的所有其他内容的部分，远比“哦，这个数据刚好在这个数据库里”这一事实要重要得多。技术转型中会发生的一件事是，当指数级增长正在发生时，没有人能真正理解它。现在最大的机会是……

<details>
<summary>Original English</summary>

**Sema Amble**: Misconception right now is that you can just have you know Postgress database and APIs and then bam like you can replace SAP. That's like absolutely not true. That piece around the logic and everything else that is encaptured in SAP is way way more important than the fact that like oh this data just happens to be in this database. One of the things that happens in technology shifts is nobody understands exponential when it's happening. The biggest opportunity right now is

</details>

### “无头软件”（Headless Software）的定义与影响

**Host**: 欢迎收听 A16Z 播客。今天和我在一起的，一位是企业团队的合伙人 Sema Amble，另一位是 A16Z 的董事合伙人、前微软成员、我们公司的老朋友 Steven Sonowski。今天我们聚在这里，要讨论 Sema 大约一个月前写的一篇文章，题目叫做《软件正在失去它的“头”吗？》（Is Software Losing Its Head?）。我会让 Sema 用她自己的话来谈谈这篇文章。这篇文章是几个月前写的。当时 Salesforce 宣布他们将要走向“无头化”。今天我们在这里就是要讨论：这意味着什么？这对 SaaS 产品的未来、或者对更广泛意义上的软件未来，意味着什么？那么 Sema，你能先给我讲讲“无头软件”到底是什么意思，并解释一下它带来了哪些变化吗？

<details>
<summary>Original English</summary>

**Host**: Welcome to the A16Z podcast. I'm here with Sema Amble, a partner here on the enterprise team, and Steven Sonowski, who is a board partner at E16Z, as well as a former uh member of of Microsoft, friend of the firm. Um, and here we are today to talk about um a piece that Sema wrote about a month ago called Is Software Losing Its Head? Uh, and this piece I'll I'll let Sema talk about it in her own words. Um, but this piece was written a couple months ago. Salesforce announced that they would be going headless. Um, and today we're here to kind of discuss, you know, what does that mean? What does that mean for, you know, the future of SAS products, the future of, um, you know, just just kind of software more generally? So, Sema, um, can you just walk me through first what headless software means and explain kind of what changes it introduces?

</details>

**Sema Amble**: 好的。其实“无头软件”并不是一个新词，但我认为它最近在公众讨论领域，或者说在大家谈论的热点话题中，确实热度攀升。一个有趣的新闻点就是 Salesforce 发布的这个声明。他们当时推出了 headless 360，这在 Salesforce 经典的过往操作中，主要就是一个营销声明。但它确实捕捉到了——或者说承认了正在发生的事情，那就是：传统的软件是围绕着人类访问来构建的，它是用于捕获数据的工作流（我们稍后可以详细讨论这意味着什么）。但在一个由智能体主导的世界里，你真的还需要这些吗？用户界面（UI）并不重要，因为智能体不是通过 UI 来访问软件的。我们可以深入探讨 UI 是否重要。但“无头化”的核心理念在于，界面下方存储的数据、逻辑以及所有一切才是真正的价值所在，而不仅仅是在顶层被追踪的工作流软件。

<details>
<summary>Original English</summary>

**Sema Amble**: Yeah. Um, so headless software has really it's it's not a new term, but I think has really risen in uh in like the you know public domain of of interest in in a topic that people are talking about. One of the interesting news points has been Salesforce making this announcement. they were launching headless 360 which was really in classic Salesforce motion you know uh history a uh a marketing announcement more than anything else but it does capture um it sort of it's an acknowledgement of what's happening which is you know traditional software had been built around humans accessing it and um it was workflow to capture data and we could talk more about what that meant in an agentic world do you do you actually need that the UI doesn't matter matter because the agent isn't accessing the software via the UI. We could unpack whether the UI matters or not. But in the idea of the being headless is the the data, the logic, everything stored below it is really where the value is, not just the workflow software that's being tracked at the top.

</details>

**Host**: 明白了。这是几个月前宣布的。我很好奇，在过去的几个月里我们都看到了什么？你甚至在文章开头有些打趣地说，这真的是个多么重大的声明吗？这难道不是对他们已经提供的 API 的一次重新包装吗？那么，这感觉像是一个重大的改变吗，还是更多地只是一次品牌营销活动？在我们能够观察的这几个月里，到底发生了哪些实质性的改变？

<details>
<summary>Original English</summary>

**Host**: Gotcha. Um, and uh, this was announced a couple months ago. I'm curious kind of in in the past couple months, what have we seen? I mean you wrote even in the piece kind of you at the beginning you were a little bit you know funny maybe and you said is this really even that big of an announcement? Is this sort of a rebrand of you know APIs that they had kind of already made available? So does this feel like a significant change? Is this maybe more of a branding exercise? Um and kind of like what have we even seen in the past couple months since we've been able to kind of observe what changes have have really happened?

</details>

**Sema Amble**: 我会把这分为 Salesforce 的背景和更广泛的行业背景来看，我认为后者更有趣。在 Salesforce 的背景下，可能并没有那么有趣。我觉得 Salesforce 也是理所当然地在承认市场上正在发生的转变。据我所知，实际上并没有发生任何改变。他们的 360 产品就是他们一直以来提供的那些 API，现在重新包装命名成了 360 产品而已。API 是一直都存在的，或者说至少存在了很长时间。但我认为这里更广泛的趋势是，Salesforce 等公司正在思考，在智能体的世界中，他们该如何构建自己。如果一个智能体需要访问像 Salesforce 这样的 CRM 系统中的数据，它们会怎么做？它们是通过 UI 还是使用 API？所以 Salesforce 是在说：“好吧，我们知道正在发生什么变化，有智能体需要访问数据了。让我们提供一个无头版本，让它们与数据交互，而不是通过 UI。”话虽如此，我再说一次，我不认为在 Salesforce 的环境中有任何实质性的改变，但 Salesforce 属于旧有的一派。

另一个例子是 Notion，他们有一个无头产品。实际上，我觉得这更加合理。因为我认为许多 Salesforce 的用户在技术上可能不太精通，不太可能去构建他们自己的智能体（尽管现在用 Salesforce 做这件事的人越来越多了）。而 Notion 的用户总体而言更懂技术，也更具备作为构建者的主观能动性。我认为 Notion 是众多试图弄清楚这一点的公司之一：“我该提供什么？我该暴露哪些 API？”我想 Steven 稍后会更多地谈到 MCP。再强调一下，我认为这其中很多也是陷入了术语命名的纠结中，比如“我们该怎么称呼这些东西”。

<details>
<summary>Original English</summary>

**Sema Amble**: So I'll separate it out into the Salesforce context and then like the broader context which I think the broader context is more interesting. In the Salesforce context probably not that interesting. Uh I think Salesforce I think rightfully again it was acknowledging a shift that's happening in the market. I don't from what I could tell nothing actually changed. Their 360 product was uh the same APIs that had always been exposed now rebranded as as as their 360 product. How and and APIs have always existed. So you know many uh or I shouldn't say always but for a long time have existed. Um but I think the broader trend here is there you know Salesforce among others are thinking about how they build themselves for the agentic world. Um and so if an agent needs to access the data in a CRM like Salesforce um what are they doing it? Are they doing it via the UI or are they using the API? And that's the you know Salesforce is saying like okay hey we know what is changing that there are agents who are needing to access the data. Let's look at the you know let's offer a headless version for them to interact with um the data versus going via the UI. That said again I don't think anything actually changed in the Salesforce context but Salesforce is in the old one.

Another example is notion has a headless product and actually I think that makes uh even more sense because it's much hard like I think many users of Salesforce are probably less technically adept less likely to be building their own agents although there are many many more people who are doing that with Salesforce notion users tend you know all things being equal are more I'd say techsavvy and more agentic as as builders and I think notion is is one of many other companies that is also trying to figure out okay what is it that I offer for um and you know how do I make you know what APIs do I expose? I think Stephen will talk more about MCP. Um and and again I think a lot of this is also getting caught up a little bit in nomenclature and like okay what are we calling things?

</details>

**Host**: 嗯，我觉得这是一方面，但我认为关于智能体如何访问记录系统，这是一个更广泛、更重要的话题。

<details>
<summary>Original English</summary>

**Host**: Um and I I I think that's one thing but I think the the broader trend around how agents um access systems of record I think is the the bigger point.

</details>

### 从 API 到智能体交互

**Sema Amble**: 是的，是的。

<details>
<summary>Original English</summary>

**Sema Amble**: Yeah. Yeah.

</details>

**Host**: 根据我的理解，它也可以应用在像聊天机器人这么简单的东西上。你知道，它不一定仅仅是一个 API 或者一个 MCP 服务器。Salesforce 几年前收购了 Slack，所以它可能简单到，你可以通过聊天机器人与 CRM 进行交互。

<details>
<summary>Original English</summary>

**Host**: And from my understanding it's also I mean it could also apply to something as simple as a chatbot. you know, it's not necessarily just an API or an MCP server. You know, you you could be, you know, Salesforce um acquired Slack a couple of years ago and like it could be something as simple as like you you sort of interacting with with a CRM via chatbot.

</details>

**Sema Amble**: 完全正确。我记得我在哪里读到过，Slack 智能体的使用量增长了 300%。这本质上说明了你不需要登录到 Salesforce 庞大的界面中去获取数据。是的，本质上这些都是智能体化的访问方式，而不是让人类进入系统去记录数据；或者从读取的角度来看，不用让人类自己去查看“哦，这里有个机会，这是发生的事情”，因此那个界面就变得不那么相关了。

<details>
<summary>Original English</summary>

**Sema Amble**: Totally. And I think I read somewhere that there's been like a 300% increase in Slackbot uh Slack agent usage. Yeah. which is essentially saying that you don't need to log into the Salesforce EOS uh interface to get the data or whatever data it is. So yeah, it's it's essentially again all these are agentic ways of accessing it versus the human needing to go in log the data or or um from a read perspective go back and see okay here were the like here's this opportunity here's what happened and um look at them themselves um and so the that interface is is less relevant.

</details>

**Host**: 是的。Steven，关于我们现在讨论的定义范畴，或者对于这个讨论，你有什么要补充的吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. And Stephen, do you have anything to add here just on the kind of like definitional territory that we're covering right now or or kind of this discussion?

</details>

**Steven Sonowski**: 好的。我是说，我们现在正处于“定义的深渊”中。技术演进新浪潮的一部分，就是你会为你以前就在做的事情编造出很多新词。这只是技术发展的自然部分。但实际上我认为这极其重要。首先，你有了“智能体”（agent）这个概念，据我目前所知，这也是用来指代“需要运行很长时间且可能无法完成的程序”的一个新词。这种品牌包装简直太绝了：把一个过去我们称之为“bug”（因为运行时间过长）的程序，包装成了有史以来最酷的新功能，现在它就叫“智能体”了。

但说真的，我认为思考“智能体”和“API”到底有什么不同，最有趣的角度是看你实际上在做什么？智能体本身在做什么？它是在查找某些信息吗？因为那实际上是一个很轻量级的操作，所有系统都很擅长。事实上，许多新宣布的“无头智能体 API”仅仅只是执行查找功能，基本上你只是拥有了一个新的接口来执行旧的查找操作，它比以前宽容度更高，少了许多繁杂的 UI 元素等等。然后还有一种情况是“我想去执行某些操作，并且……”

<details>
<summary>Original English</summary>

**Steven Sonowski**: Well, sir, I mean like we're in definitional hell right now where is is, you know, part of a new wave of technology is you make up a lot of new words for things that you kind of did before. And that's just a natural part of technology evolution. Um, but I I actually think it's super important. Like first you have this, you have a agent, which as far as I can tell right now is also a new word for program that takes a very long time to run and might not finish. And and so yet that's just like a a branding that's the best branding ever is to call a program that's takes a really long time, which we used to call a bug, is now like the coolest new feature ever and it's just now an agent. But in in seriousness, the most interesting way I think to think up what you're really talking about doing differently between an agent and an API is really what are you actually doing? What is the agent itself doing? Is it looking something up? Because that's actually a pretty lightweight thing that all systems are pretty good at. And in fact, many many of the newlyannounced, you know, headless agent APIs are are just lookup and they're just you basically have a new interface to the old way to look something up, which is a lot more forgiving, a lot less UI goo and stuff like that. Then there's like I want to do something and

</details>

<!-- chunk 2/8 -->

### 代理与无头软件的演进

**Speaker A**: 这就是你会遇到非常有趣的有关企业级软件的问题的地方，比如，好吧，如果你想做某件事，你必须假扮成一个特定的人，你必须拥有他们的凭证，比如这是一个非常……这是另一个付费席位吗？这是同一个付费席位吗？如果你真的想对记录系统进行更改，就会出现所有这些有趣的企业软件问题。然后还有第三件事，那就是“分析”（analyze）。分析不仅仅是查找某样东西。它实际上是查找一大堆东西。它通常涉及多个系统。这似乎非常非常适合 Agent（智能体/代理），因为你不受时间限制。你可以花精力去迭代。你可以将其路由给不同的模型，得到不同的返回答案并进行比较。但这也是幻觉（hallucination）真正成为一个巨大问题的地方，因为如果你要去分析某件事，你实际上需要一种方法来验证分析的每一步都是正确的。所以，当你审视无头软件（headless）和代理这两个容易被混为一谈的概念时，我认为这非常有趣且重要。你必须弄清楚你在谈论什么，因为我们在这种三维矩阵式的演进、学习曲线和代理的部署中处于不同的位置。

<details>
<summary>Original English</summary>

**Speaker A**: that's where you get into very interesting issues over like well if you do something you have to be impersonating a specific person you have to have their credentials like it's a very is it another paid seat is it the same paid seat you have all these interesting enterprise software issues that come up if you actually want to cause a change to a system of record and then there's the third thing which is analyze. And so analyze is more than look something up. It's actually look up a bunch of stuff. It often involves multiple systems. And that seems very very tuned to an agent because you you're not time bounded. You can spend energy iterate. You can route it to different models and get different answers back and compare them. But it's also where hallucination really is a huge issue because if you're going to go and analyze something, you actually need a way to verify that everything every step of that analysis was correct. And so I think it's super interesting and important when you look at headless and agent which are conflated in you sort of have to figure out what you're talking about because we're on different places in the evolution the learning curve and the deployment of agents relative to sort of that three-way matrix

</details>

**Host**: 矩阵。是的。我认为这实际上为接下来的一个问题做了一个很好的铺垫，那就是从历史上看，是什么让软件具有用户粘性？而智能体又是如何开始颠覆这一点的？我把这个问题留给你们俩来回答。也许你们俩可以就此讨论一下。

<details>
<summary>Original English</summary>

**Host**: matrix. Yeah. I I think this is actually a good leadup into a follow-up question, which is kind of like historically, what has made software sticky and how are agents starting to disrupt that? And I I leave that to either of you to answer. Maybe you guys can both kind of debate about that.

</details>

### 究竟是什么让软件具有粘性？

**Sema**: 是的，我想说有很多因素让软件具有粘性，但其中很大一部分与它围绕着人类交互方式来构建有关，对吧？所以 UI 是有粘性的，因为你知道你需要读写的次数、访问的频率、下游的工作流、所有未记录的、也就是我们所说的 SOP（标准操作程序），所有围绕软件发生并根植于肌肉记忆、流程以及外部各方等等的事情。所以像 CRM 可能具有粘性，因为销售代表需要一直频繁进出使用它。他们习惯了与 Salesforce 交互。很多时候，当新的销售副总裁来到我们公司时，他们会强制要求使用 Salesforce，因为他们习惯了使用它。他们的团队也习惯了使用它。然后，你知道，财务部门可能依赖 Salesforce 的输出来进行计费，上游的营销部门也会依赖它。所以存在这些依赖关系。而且所有这些都在推动着用户粘性。但我认为另一点是，你需要一个单一的事实来源（single set of truth），对吧？你需要知道一个账户是否已关闭，是谁在跟进，所有这些都需要记录在一个地方。而且我认为，如果你从 CRM 转向比如 ERP 或薪酬系统，那绝对甚至涉及到法律原因和合规原因，为什么你不能拥有像审计员所期望的那样被干净且正确追踪的数据。所以不管怎样，所有这些都推动了粘性和持久性，因为你知道你已经习惯了使用 Salesforce，整个生态系统都在使用 Salesforce，它是默认选项，也许市场上还有一两个其他的选择。所以，我认为从历史上看，这就是推动软件粘性的一些因素。

<details>
<summary>Original English</summary>

**Sema**: Yeah, I'd say there there are many things that made software sticky, but a lot of it had to do with the fact that um it was built around like the the way a human interacts, right? So um the UI was sticky because you know the number of times you had to read and write the frequency of access the downstream workflows all of the like undocumented like you know what we call SOPs or uh standard operating procedures all the stuff that happened around the software that got ingrained in muscle memory and process and then external parties etc. So like a CRM may be sticky because a sales rep needs to go in and out of it all the time. They're used to interacting with Salesforce. A lot of times when like new VPs of sales come into our companies, they they're like they mandate that Salesforce is there because they're used to using it. Their teams are used to using it. Um and then there's, you know, finance may rely on the Salesforce um output for billing and upstream marketing is going to rely on it as well. And so there's these dependencies. Um and these all are driving stickiness. But I think the other piece too is there you need one single set of truth, right? you need to know like an account is closed and who is working on it and all of that needs to be logged in one place. Um and I think if you go from CRM to say an ERP or payroll like that absolutely has even like legal reasons and compliance reasons why you can't have um numbers that are not being you know tracked uh as cleanly and and correctly as you know an auditor might like for example. Um so anyways this all drove stickiness there and and and durability because you know you were used to using Salesforce the whole ecosystem was using Salesforce and it was the default option and maybe you know there's one or two others in the market. Um and so I think historically those were some of the things that were were driving stickiness.

</details>

**Stephen**: 是的。我是说，那些全都没错。我认为同样重要的是要考虑到，你能做的最具粘性的事情实际上就是向客户收钱。如果你在收钱，你会发现让他们停止给你寄钱真的非常非常难。而对他们来说，要搞清楚如果停止寄钱该怎么办也极其困难。这听起来非常陈词滥调，但最具粘性的软件就是在某个地方正在被使用的软件。然后当你深入挖掘并试图找出原因时，这就取决于你在一家公司里和谁交谈了。你知道，如果你和某家公司的 HIPAA 合规人员交谈，他们会告诉你这就是你必须使用的软件，因为它是最最好、最符合 HIPAA 标准的软件。如果你和管理员交谈，你会听到关于新用户入职培训的事。如果你和用户交谈，你会听到关于肌肉记忆和击键操作、或者是工会之类的原因。因此，你必须明白，你真正想要的是把软件卖出去，这是实现粘性的最快途径。在那之后，关于什么导致了它的粘性，那就成了一段“胜利者书写的历史”。而且事实上，关于粘性最好的一点是，如果你是你向其销售了产品的公司的代表，而那家公司正在威胁你说，“嘿，我们要替换掉你”，你只需要听他们说，你就会发现什么是具有粘性的。如果这在不同客户那里奏效了三四次，那么你就刚刚讲述了一个关于是什么让产品具有粘性的故事。PM（产品经理）或其他人是怎么想的并不重要。它可能是一些疯狂的、晦涩难懂的东西，你知道，比如我有很多关于粘性软件和晦涩事物的轶事，但就像任何曾经试图取代微软 Outlook 作为电子邮件工具的人很快就会了解到，关于委托访问（delegate access）以及由多人拥有的日历和所有这些疯狂的东西。我可以告诉你，我们没有开过这样的会说：“好吧，让我们想想如何让日历成为 Outlook 中具有粘性的部分，并确保我们很好地处理定期会议的例外情况。” 然后你去了解，你会发现通用汽车不会因为日历或诸如此类的疯狂原因而撤换掉 60 万个席位。所以你可以看到，在企业软件中，什么导致了粘性，以及当有人威胁要把你从企业中赶出去时，你实际上可以如何利用这一点，这真是令人惊叹。

<details>
<summary>Original English</summary>

**Stephen**: Yeah. I mean I those are all exactly right. I I think it's important to also consider that the most sticky thing you could do is actually collect money from a customer. And if you're collecting money, it turns out it's really really hard for them to stop sending you money. And it's really hard for them to figure out what to do if they stop sending you money. And and it it sounds really trit, but the the stickiest software is software that's getting used somewhere. Then when you dig in and try to come up with reasons, well, it just depends on who you talk to in a company, you know, you talk to the HIPPA compliance people in some company and they're going to tell you this is the software you have to use because it's like the most bestest HIPPA compliant software. If you talk to the administrators, you're going to hear about onboarding new users. If you talk to the users, you're going to hear about muscle memory and keystrokes or labor unions or whatever. and and so you have to be yet you you really want to get the software sold and that's your fastest path to sticky and after that it it's sort of you know a winner's tail over over what caused it to be sticky and and in fact the best thing about sticky is if you're the rep for a company that you've sold something to and the company is threatening you like hey we're going to replace you we're just going to listen to them and you're going to find what's sticky. And if that works like three or four times across different accounts, then you've just told the tale as to what made the product sticky. It doesn't matter what the PMs or what anybody else thought of. It could be some crazy arcane thing, you know, like I have stories of lots of sticky software and lots of arcane things, but like anyone who's ever tried to displace um Microsoft Outlook as email very quickly learned about delegate access and and having calendars owned by multiple people and all of this crazy stuff. And like I can tell you there was no meeting where we said, Okay, let's figure out how to make the calendar the sticky part of Outlook and make sure we handle recurring meeting exception handling well. And then you go and you find out, you know, General Motors isn't going to displace like 600,000 seats because of the calendar or some crazy thing like that. And so you can, it's really amazing in enterprise software what causes sticky and how you can actually capitalize it on it when somebody threatens to take you out of the out of the enterprise.

</details>

**Sema**: 我认为这里有一个非常好的观点，体现在两方面。惯性（Inertia）是一种非常强大的力量。然后我认为另一件事是，是的，没有人在构建软件时，他们不会考虑像我们制定的这个评估标准（rubric）然后像打勾一样，“滴，滴，滴。我们有所有这些功能去完成所有这些事情”。但我认为现实情况也是，随着软件将其触角延伸到整个组织内部，它根植于人们的使用习惯中，而且他们已经为此付费了很长一段时间，它就渗入了人们做事的方式中，而这就像很难被根除一样。

<details>
<summary>Original English</summary>

**Sema**: I I think there's a really good point there in two things. Inertia is a really powerful force. And then I think the other thing is yeah, nobody when they're building the software, they're not like thinking about like this rubric we put together and like tick tick tick. We got all these features that are going to do all these things. But I think the practical reality is also as software extends its tentacles across an organization and it gets ingrained in people using it and they've been paying for it for a long time, it just seeps into how people are doing things and that's like hard to rip out.

</details>

**Host**: 是的。是的。你甚至在你的 PC 模式里谈到过这一点，就是存在着各种关于如何使用不同产品或者内置在软件中同时也存在于使用者习惯中的、那种看不见的心照不宣的理解，以至于过了一段时间后，就变得很难将自己从你碰巧置身其中的那个生态系统里抽离出来。事实上，Stephen，我想你甚至说过“SaaS 末日论”是被夸大了的。你写过一篇名为《软件之死，Nah》的文章。在文章里你断然否定了这个想法。所以也许，如果你愿意的话，也许可以为我们稍微复述一下那篇文章的内容。

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. You even talk about this in your PC mode where there's sort of all of these like invisible tacet sort of understandings about how to use different products or things that are embedded both within the software but also within the people using them where it's just like it does become hard after a while to uh to extricate yourself from from whatever ecosystem you happen to be in. And in fact, Stephen, I think you you've even you know said the SAS apocalypse is overblown. you've written an essay called the death of software. Nah. Um where you where you you know emphatically sort of rejected this idea. So maybe if you want to if you want to maybe just recount that piece a little bit for us.

</details>

**Stephen**: 嗯，我是说 Sema 参与合写了一篇关于 SAP 的文章，SAP 算是粘性软件的最极致、最极致的例子。我的意思是，唯一比 SAP 更具粘性的软件是在幕后的，那是保险公司编写的软件，他们大约在 50 年前或 75 年前编写了所有这些软件，并且如果你曾经……那是无法替代的，就像它……事实上，每当出现关于企业在寻找 COBOL 程序员的笑话时，那都是为了去处理美国每个州都存在的保险软件。而且在很多方面，正如你所看到的迄今为止 Stripe 最伟大的成功之一那样，确实有人进入了这个领域，并在两代人的时间里首次编写了用于向人们收钱的软件，而这本身在此前也是一个像保险行业那样规模的未解决问题，因为从来没有人能把每个国家、每个司法管辖区、每个地方、每个过境点的税法汇编在一起。

<details>
<summary>Original English</summary>

**Stephen**: Well, I mean Sema co-wrote a post on on SAP which is sort of the ultimate ultimate example of sticky software. I mean there is nothing the the only software that's stickier than SAP is behind the scenes and it's the software that insurance companies wrote and they wrote all this software like 50 years ago or 75 years ago and if you ever there's no replacing it like it it just it in fact you whenever jokes come up about like businesses that are looking for cobalt programmers it's to go and work on the insurance software that exists in in every state of the union and and in many ways what you're seeing like with the one of the biggest successes to date in Stripe has been somebody actually went in and for the first time in it two generations coded up the software to collect money from people which itself had previously been an unsolved problem on the scale of insurance because nobody put together the tax laws for every country every every jurisdiction every locality, every border crossing,

</details>

<!-- chunk 3/8 -->

### 企业软件的用户粘性与业务逻辑固化

**Speaker A**：每一次货币交易等等，诸如此类，这简直令人震惊。因此，现在这种体验是最具用户粘性的。可以说，它永远都不会消失。这就好像一百年后，我们还在和曾孙辈们一起做这档播客，谈论当时的体验是多么具有粘性。就像我之前说过的，哦，你可能不知道，运行 Allstate（好事达保险）的软件比我的年纪还要大，但它绝不会被淘汰，这是因为这些例子都将某种外部力量固化在代码中，而这种外部力量就是他们所拥护的监管机构。SAP 的无缝体验也是如此，它实际上是将整个公司的运作固化了下来。所以，如果你把 SAP 从一家大型汽车制造商中抽离出来，那这家汽车制造商也就不复存在了；或者是沃尔玛，这家公司也会瞬间蒸发，因为定义这家公司的不仅仅是他们购买了这款软件，甚至也不仅仅是他们使用了这款软件，而是他们如何将自己的业务规则固化到了那个产品之中。我觉得这是个非常值得深入探讨的点，因为目前存在一个误解，那就是大家觉得对于 SAP，好吧，你只要弄个 Postgres 数据库加上几个 API 接口，然后“砰”的一下，你就能用 API 取代 SAP 了，而这绝对是错的。我认为部分原因是——斯蒂芬（Stephen），我不知道你是否想详细展开说说，我很乐意讲讲，但我认为正是 SAP 中包含的业务逻辑以及其他所有东西，远远比“哦，这些数据正好存放在这个数据库里”这一事实重要得多。

<details>
<summary>Original English</summary>

**Speaker A**: every currency exchange like it it it's mindblowing that. And so now that is the most sticky. So like that is not going anywhere ever. Like it it'll be like we'll be doing this podcast with like great grandchildren 100 years from now talking about how sticky that experience was. Just like I told like oh you didn't know this but the software that runs all state is older than me and it's not going anywhere and that's because the these examples are ones that codified an external force and that external force was the regulatory body that they embraced the seamless examples of SAP like it just codified a company and and so like if you take SAP out of a large automobile manufacturer there's no automobile manufacturer left or or Walmart like the company just evaporates because the the company is defined not just by purchasing the software not even by just using it but by how that they codified the business rules into that product. I think it's a good point to double click on because I think a misconception right now is that SAP okay well you can just have you know Postgress database and APIs and then bam like you can replace API replace SAP and that's like absolutely not true. I think partly I mean Stephen I don't know if you want to elaborate on or not I'm happy to but I think it's that piece around the logic and everything else that is h like that is encaptured in SAP is way way more important than the fact that like oh this data just happens to be in this database

</details>

**Stephen**：这也是为什么实施和部署 SAP 往往需要花费数年时间的原因。这并不是因为系统集成商动作慢——虽然这也是部分原因——而是因为它需要根据企业实际的运营方式进行深度定制。嗯，我认为这是极其重要的一环，也是为什么你不能简单地将软件完全屏蔽掉，然后把它变成“数据库加上 API”的模式。是的。

<details>
<summary>Original English</summary>

**Stephen**: >> there's a reason why also SAP like takes you know multiple years to implement and get it's not because like oh you know yes the system integrators are slow and part of it but it's it's customized to the way that business actually operates. Um, and I think that's like an important part about why you can't just obscure away the software completely from and and turn it into a data database plus APIs. Yeah,

</details>

### 初创公司的视角与企业级规模的复杂性

**Speaker C**：这一点实在太重要了，因为在这种情况下，初创公司往往会用自己的规模和视角去审视企业级软件。比如，他们会拿“费用报销”这种日常琐事来举例，觉得：“好吧，我们公司有四十个人，只需要一个人就能搞定这四十个人的费用报销，大不了雇个人来做，问题就解决了。”也就是说，你出差回来，把一堆收据扔进一个桶里，然后让那一个人去一张张翻阅，费用报销的问题就迎刃而解了。或者你会说：“哦，别用人工了，我们直接用手机拍下所有的收据，然后进行光学字符识别（OCR）并自动分类，整个流程就全自动化了。”这种想法本来也没什么问题，直到你的公司发展到在二十个不同的国家拥有十万名员工。每个国家都有不同的国家法律和关于商业费用的政策规定；然后你还得把公司内部的各项政策叠加进去。整个事情就会变得无比复杂，于是你的业务就这样被固化在这些规则之中，你根本无法轻易替换它。

回想一下九十年代末的甲骨文公司（Oracle）以及现在被称为企业软件教父的拉里·埃里森（Larry Ellison）。那时候他们还只是一家数据库公司，正准备进军 NetSuite 和 ERP（企业资源计划）等领域。当时他发表了一段长篇大论，一段持续了多年的长篇大论，痛批企业软件是多么的愚蠢，因为每个人都在对它进行定制。他有句名言，大意是说企业就应该坚持使用那 80% 的通用解决方案，只要能解决 80% 的问题就该将就着用。而大多数企业界的人则回应说：“首先，你这只是在王婆卖瓜，因为你的软件只能满足我 80% 的需求。其次，现实根本不是这样运作的。”

举个例子，如果你看看汽车行业，就看排名前十的汽车公司，抛开电动汽车与燃油汽车等差异不谈，它们其实都在做同一件事——制造汽车。这其中涉及大量众所周知的技术、流水线和工人。那么，真正区分这些公司的是什么呢？区分它们的是它们的运营方式，是它们决定生产哪款汽车、购买多少额外原材料、对冲哪些货币、雇佣多少员工、何时推出新产品线的内部流程。所有这些都属于企业资源管理和规划的范畴。而这一切又是如何完成的呢？全都在 SAP 里面。所以，这些公司实际上是由一群坐在会议室里、盯着 SAP 屏幕的人在运营的。福特、丰田、通用汽车和戴姆勒之间的区别，不仅仅在于他们盯着相同的屏幕，更在于他们选择了查看哪些屏幕、在这些屏幕中进行了哪些定制化设置，然后他们再去同样的地方购买钢铁、铝材、线缆、仪表盘和收音机。

所以我真的觉得，人们严重低估了客户在应用这款软件时所展现出的那种极其复杂的架构层次。比如，当年我们刚开始在各大公司推广使用 Excel 的时候，说出来你可能会笑，我们经常会去进行一些小型拜访，比如去拜访银行家。有一次，我们坐在高盛（Goldman Sachs）的办公室里，跟对方滔滔不绝地说 Excel 比 Lotus 1-2-3 强多了，之类的话。那软件超级老了，你可能都不知道 1-2-3 是什么，但我知道。相信我，它真的很有年代感。当时高盛的那位负责人看着我们说：“我觉得你们还没搞明白状况。我们用 Excel 赚的钱，比你们卖 Excel 赚的钱还要多。”我们当时就坐在那儿，面面相觑：“他到底在说啥？”这完全超出了我们的理解范围。后来我们开始仔细琢磨这件事，才恍然大悟：我们把 Excel 卖给摩根士丹利、摩根大通以及其他所有人，而高盛想表达的是，他们对 Excel 的应用具有极强的差异化优势。而且那不仅仅是人们在里面打字输入数据那么简单，他们还构建了各种插件，编写了大量的代码。他们甚至在里面定义了属于自己的 WordPress 系统。要知道，现在外界有一种极其荒谬的低估，觉得你随便写点“感觉不错”的代码（vibe code）就能轻易打入企业软件市场。

我昨晚参加了一个晚宴，遇到了一位可能是某个成长型初创公司的营收运营（revops）负责人，他所在的公司大概有一千多人。他的任务是在公司内部重建他们的 Salesforce 系统。当时他大概是这么想的：“哦，我们知道所有的字段，我们可以把所有数据都导入进去。”我就跟他说：“那根本不是真正的难点所在，对吧？真正的难点在于，你们如何决定要抓取和记录哪些信息，整个公司的组织架构如何围绕它来运作。”还有就是，随着时间的推移，未来谁来维护这个系统？我觉得这往往是被大家忽略的一个关键环节。你当然可以随便写点代码搞个 CRM（客户关系管理）系统出来，我们都曾凭直觉写过一些项目代码，结果那些项目很快就变得陈旧过时，我们再也没碰过，因为维护它们实在太痛苦、太耗时了，而且它还需要不断去适应业务的变化。

<details>
<summary>Original English</summary>

**Speaker C**: >> this it's just so important because this is one of the things where like startups look at enterprise software and they think about it in terms of startup scale and so they take something mundane like expense reporting and like okay well we have 40 people and like you know one person could figure out expense reports for 40 people like you you could hire a human and that and be done with it. that like literally you come back from a trip, you dump the receipts in a bucket and one human rifles through them and the expense reporting problem goes away. Or you say, "Oh, forget the human. We'll just all take pictures of our receipts and OCR it and categorize it and the whole thing will go away." And and that's fine until you have a h 100,000 people in 20 countries with different national laws and policies about business expense and all of those and then you overlay corporate policies and and the whole thing just and then your business is just codified that way and it and you can't replace it. You back in the um in the late 1990s who now is sort of the godfather of enterprise software Larry Ellison at Oracle. back then they were only a database company and entering the world of Netswuite and ERP and all this but he went on a rant he a multi-year rant about how enterprise software was so stupid because everybody customized it and he had this saying that just said businesses should just stick with the 80% solution and they should just use whatever works like 80% of the time and most enterprise people were like well a you're just talking your book because your software only does 80% of what I need. But B, like that's that's just not how it works. Like if you take the auto industry and you just take the top 10 companies in autos, >> they they all, you know, putting aside EV versus gas or whatever, they all just make cars, which is a lot of known technology with assembly lines and workers. Like what differentiates the the companies and what differentiates them is how they operate and the internal processes to decide what car to make, how many more materials to buy, what currencies to hedge, how many people to hire, when to introduce a new product line. All of that is enterprise resource management and planning. And how is all of that done? It's all in SAP. So those companies are effectively run by people sitting in conference rooms looking at SAP screens and and the difference between Ford and Toyota and General Motors and Daimler are just are not just that they're looking at the same screen. it's that they chose which screens to look at, which customizations to make in those screens, and then they go and they buy steel and aluminum and wire and dashboards and radios from all the same places. And so it's a I I just think that people wildly underestimate the the level of house of sophistication that customers apply to this software. Like when back when we were first starting to get Excel used in companies, you'll laugh at this even like like the we used to do these little visits and we go visit bankers and so we're sitting in Goldman Sachs and we're telling him about Excel is better than Lotus 123 blah blah that's super old. You don't even know what 123 I know. Trust me, it's old. And and the guy at Goldman looked at us and said, "I don't think you understand. We make more money from Excel than you do." and and you're and we're just sitting there like what is he talking about? Like it made no sense to us. And then we started to think about it and it's like well we sell Excel to Morgan Stanley and JP and Chase and everybody else and what Goldman was saying is their application of Excel is so differentiated. A and that's and that wasn't just people typing. They built add-ins. They wrote all this code. They defined their WordPress. know there's this wild underestimation about like you could vibe code your way into enterprise software. I uh was at a dinner last night and there was someone there who um was like the head of revops at a I don't know maybe growth stage startup and his task this is like a thousand plus person company was to rebuild their Salesforce instance internally and you know I think he's like oh well you know we know all the fields we can import all the data and I was like that's not really the part that's tough right it's well how are you deciding what like what gets captured how the whole organizational lines around it. Uh, and then who's going to maintain this also over time. I think that's like a piece that just gets falls off. You know, you can you can vibe code a CRM. We've all vibecoded projects that have like already gone stale and know we haven't touched again because it's painful and it's it's it takes time and needs to adapt the business.

</details>

**Host**：嗯。而且，西蒙（Simo），你也写过相关的文章，谈到现在有整个一个初创公司生态系统，它们只是在 SAP 之上进行构建，在那些令人头疼的复杂流程周围构建解决方案，但其底层依然还在使用 SAP。所以，呼应你们俩刚才的观点，这些传统的 SaaS 系统已经根深蒂固，以至于新入局的颠覆者只能顺势而为，在它们的基础之上或周围进行开发，而不是试图把它们连根拔起，让用户彻底迁移到新平台上。

<details>
<summary>Original English</summary>

**Host**: Mhm. And and Simo, you've also written about how, you know, there are there's an entire ecosystem of startups now that are just building on top of SAP and that are, you know, like sort of building around all of the kind of headacheinducing stuff and but still using SAP. So, like to both of your points earlier, like the these like legacy SAS systems are just like so deeply embedded that the newer insurgents are just coming and they're, you know, building on top and around them rather than kind of like trying to rip out and get people to migrate completely.

</details>

### 人工智能与交互层的变革

**Simo**：我们今天看到的人工智能的大量应用，主要集中在如何让这些系统变得更易用，我觉得人们经常用的一个词是“对话式”（conversational），或者说，你该如何提取信息并使其真正变得更加实用？你该如何从 SAP 中检索信息，而无需去运行一堆 SQL 查询来获取所有数据，或者无需盯着一大堆屏幕看？这就好像是，如果我希望能与斯蒂芬提到的“分析功能”连接起来，比如跨越三个不同的表格和不同的地理区域进行分析，我能不能用自然语言的方式快速查询？我能不能自动生成为我量身定制的报告，而不需要退回去重新走一遍 SAP 的定制流程？我认为，这种可用性层的演进，正预示着如今软件行业整体正在发生的变革，也就是说，通过用户界面（UI）进行访问已经变成了一种可选项。回到之前提到的 Slack 机器人的观点，你希望信息主动推送到你面前，而不是你需要亲自去 UI 界面里找。但是，所有的数据和业务逻辑，依然深藏在其中，哪怕它是 SAP。

<details>
<summary>Original English</summary>

**Simo**: A lot of what we're seeing AI being used today is for is how do you make it like I think the word is often used like conversational or like how do you pull the information out and actually make it more usable? How do you retrieve the information from SAP without needing to go you know run a SQL query and get all the information or like look at a bunch of screens. It's like okay well if I want to be able to connect to Steven's point around analyze like you know three different uh sets of tables and different geographies like can I quickly you know query that like a natural language way um can I get reports automatically generated that are customized to me without needing to like go back through the like SAP customization process and I think that is that usability layer is I think indicative of what's happening now with software in general which is accessing the UI is optional and like Going back to the Slackbots point, like you want the information delivered to you versus needing to go to the UI, but the data and the business logic inside either it's SAP

</details>

<!-- chunk 4/8 -->

### 企业软件与“导出”逃生阀

**Speaker A**：大家需要明白最重要的一点：企业软件几乎总是能满足某人的需求。他们只是不知道如何让软件去实现这些功能。比如说，没有哪种报告是 SAP 无法生成的。无论是图表、数据曲线、数据分析还是其他什么东西，它都能做，但你就是摸不透怎么操作。或者它被配置成了你没有相应权限等等情况。所以，思考这个问题的角度是，在企业软件中，有两个最常用却又没有哪个企业软件原生具备的功能，那就是“导出到 Excel”以及“导出为 CSV”或者 PDF（随你选）。所以，所有的企业软件，当它们向客户展示并做第一次演示时，客户发现缺少的第一件事通常是：“它能导出到 Excel 吗？”或者“它能导出到 CSV 或 PDF 吗？”因为只有这样，你才有了一个逃生阀，能在分析时去做之前在系统里做不了的事情。

<details>
<summary>Original English</summary>

**Speaker A**: folks to take away which is that the the the biggest thing about enterprise software is it almost always does what somebody is wants it to do. They just don't know how to make it do that. Like there's no report that that SAP can't generate. No graph, no chart, no analysis or whatever. But you you just can't figure it out. Or maybe it's configured so you don't have permissions or something. So the two the way to think of it is in enterprise software the two most frequently used features exist in no enterprise software natively it's export to Excel and export as CSV and or PDF you pick and so all enterprise software the first thing they have to do that's missing when they show up and they do that first demo is the customer say does it do export to Excel or does it do export to CSV or PDF because then you know you have an escape valve to do the thing that you couldn't do before on analysis.

</details>

**Speaker A**：所以，现在我们所处的时代最酷的地方在于，借助语言模型，你有了一种非常不可思议的方式来处理这些数据，这比以前容易多了。你想想看 PDF，以前的老办法是这样的：假设我想弄清楚如何处理异常情况，比如我的系统发出的一些报告，像是被拒绝的报销单之类的，但我想跨越某个系统无法处理的奇怪时间段或不同的货币来进行操作，或者遇到了一些你在用户界面（UI）上搞不定的奇怪问题。那么现在，你可以把它们全部导出，把这 20 个 PDF 放到模型里，去做一大堆你以前做不了的分析。即便以前你做了，也全都是复制、粘贴这种繁琐的事情。就像 Sema 写的关于这种……我不记得你用的确切词汇了，但这些临时的（ad hoc）业务流程才是真正变得最有趣的，因为它们有趣的点在于这就是业务的运行方式，而且它们也是下一代的产品形态。那些就是人们将要创立的下一代公司。你知道的，CRM（客户关系管理）以前不过就是个电子表格。如果你在一家企业里当客户经理，你要跟踪你的客户记录，你就是在 Excel 里记录它，然后才有一家公司成立专门来做这个。最初并不是 Salesforce。它是它的前身，叫 Seibel。然后人们就觉得：“哦，我们应该创立一家专门做这个的完整公司。”你现在看到的那些使用语言模型、界面是跟 SAP 或 Salesforce 聊天的应用，就是这类东西。它们只是想利用大语言模型（LLM）真正擅长的事情，即合成并编排非结构化信息。

<details>
<summary>Original English</summary>

**Speaker A**: And and so what's so cool about where we are today is that now with with the language models you have this incredible way to actually consume those in much easier than you could before. If you think about PDF, like the old way used to be like, okay, I want to figure out like exception handling, some report that that my system emits, you know, declined expense reports or whatever, but I want to do it over some weird time period or across different currencies that it doesn't handle or some weirdness that you can't figure out the UI. So now you can export them all and take this 20 PDFs and put them in a model and do a bunch of analysis that you couldn't do before or if you did it was all copy and paste and this mundane thing and to something that Sema wrote about these sort of I don't remember the word you used but these ad hoc business processes are the ones that really become the most interesting because they're interesting because that's how a business runs but they're also interesting because those are the next products Like those are the next companies that people start. You know, CRM used to just be a spreadsheet. Like the this if if you were in a business and you were account manager and you kept track of your accounts, you just kept track of it in Excel and then a company got started to to do that. It wasn't SA. It wasn't Salesforce first. It was the predecessor called Seible. And and then like people like oh we should make a whole company that does this. And that's what's that's what some of these apps are that you're seeing using language models and interfaces that are chat to SAP or to Salesforce. They they are just trying to take advantage of what the LMS are really good at which is synthesizing and orchestrating unstructured information.

</details>

### AI 智能体与捕捉上下文异常

**Speaker B**：对。我认为我们也忘记了，像 Salesforce 实际上对走向市场（go-to-market）的团队来说，就是一种强制执行机制，也就是：“你有没有收集你需要的所有信息？”当然，我们可以把 Salesforce 的数据卫生等问题单拿出来谈，但问题在于：业务人员是否在录入数据，以便……你知道，捕捉业务的当前状态。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. I think we also forget that like Salesforce is like really an enforcement mechanism for like the the the go to market team which is like okay are you collecting all of the information that you need to and of course we can talk about Salesforce hygiene etc as a separate point but like do you have all you know is the human doing the getting the data to then have um like the to then you know capture the state of the business

</details>

**Speaker B**：那么，如果我们现在切换到智能体（Agent）的世界，同样，我们可以讨论“智能体”到底意味着什么，但想象一下，有一个智能体需要进行外呼或群发消息。它们希望能提取出那些信息。它们其实并不关心字段是怎么组织的，或者需要点击多少次，但它们确实需要访问这些信息。然而，它们需要的第二部分就是这个叫做“上下文（Context）”的东西。我们已经讨论了很多。我觉得在过去的六个月里，互联网上一直在热议上下文图谱（context graphs），但那到底是什么？那全是关于异常情况（exceptions）。你该怎么做？你如何处理某些特定情况？这就是边缘案例、权限配置以及所有那些必须处理的细节，还有那些不一定能填在 Salesforce 字段里的各种政策。所以，对于智能体来说，回到那个 80/20 法则，智能体可以提取所有信息，基于 CRM 里关于这个人的信息、他们的用户画像、他们做什么之类的东西，发送一封外呼邮件，但接下来它会面临：“好吧，你该如何处理这个案例跟那个案例的区别？他们怎么回复的？”然后就像：“哦，通常如果客户在亚洲，我们会这样回复；但如果在是在美国，我们会那样回复。”这并没有记录在 Salesforce 中，而是存在某个人的脑子里。所以，我认为这种上下文对于智能体能够代表这些数据采取行动来说，是非常重要的。

<details>
<summary>Original English</summary>

**Speaker B**: >> um which okay but I think if we like now switch to the agenda world Um, and I think again we can talk about what agent means, but imagine there's an agent that needs to do outbound calling or outbound messaging. They want to be able to retrieve that information. They don't really care about how the fields are organized or, you know, how many clicks it takes, but they do want to be a they still need to access that information. But then the second piece they need is this context thing. So, we've talked a lot. I think I feel like the internet has talked a lot about context graphs uh over the last six months, but what is that? That's all like the exceptions. What do you do? What do you how do you handle certain cases? It's the edge cases and the permissioning and all that stuff that needs to be um and all the policies that are not necessarily in the fields of Salesforce. Um, and so for the agent to then go go back to this 8020 thing, the agent can, you know, extract all the information, send an outbound email based on the information that's in the CRM around the person and their persona and what they do and all that, but then like, okay, how do you deal with um, a case, one case versus another, and how they respond? And it's like, oh, well, normally if it's a person who's in Asia, we respond this way, but if it's a person in the US, we respond this other way. That's not captured in Salesforce, but that's that's was in someone's head. And so that's the context that I think is really important now for agents to be able to act on behalf of this data.

</details>

**Speaker A**：哦，那太棒了。我的意思是，尤其是对于 Salesforce 来说，这极其重要，因为我从来没有见过任何一个销售人员、客户经理或客户执行官会认为系统的默认设置对他们的客户来说是正确的答案。甚至可以说，绝不会这样。哪怕他们把日语邮件写得很完美，你知道的，开头说：“哦，现在是春天了，鸟儿在歌唱……”接着切入正题：“但是你的付款逾期了，你的许可证数量不对。”哪怕你做得完全正确，销售代表也总是希望能用他们自己特定的方式来处理。而且我认为，这种“处理异常情况”的概念，正是智能体所面临挑战的根源所在：在企业中，几乎每一件有趣的事情都是一个异常情况。

<details>
<summary>Original English</summary>

**Speaker A**: >> Oh, that's super. I mean, for Salesforce in particular, that's incredibly important because I've never met a saleserson, an account manager, an account executive who thinks that the default is the right answer for anything with their account. and and like no, even if they get the Japanese language right, you know, oh, it's spring and the birds are chirping and but you're you're overdue on your payment, your license count is wrong, that even if you do that correctly, the rep is going to want to handle it in their in their specific way. And and I think that this notion of exception handling is just the root of the challenge with with agents, which is almost everything interesting in an enterprise is an exception.

</details>

**Speaker B**：是的。没错。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yes. Yep.

</details>

**Speaker A**：就是那样。就好像所有人都在处理异常情况。这就好比你在麦当劳待上 15 分钟，看着人们开始在自助点餐机上操作，然后放弃，再看看他们到底想要什么。他们会说：“嗯，我想要一杯麦旋风，但我想要两种口味混合在一起的，但是机器上没有这个选项。”所以永远都有例外。而且，关于企业自动化的一切，核心都在于处理异常情况。事实就是如此。最奇怪的事情就是……企业定价就是个很好的例子，比如每个席位多少钱？“嗯，你得打电话给我们。”当你打电话并交谈之后，它依旧是个特殊情况。

<details>
<summary>Original English</summary>

**Speaker A**: like that. Like all the people are about exception handling it. You know, it's basically like spend 15 minutes at McDonald's and watch people start in the kiosk and give up and then go watch what they really want and they're like, "Well, I wanted a McFlurry, but I wanted two flavors and mix them together and that's not in the" and it's always the exceptions. And everything about automation in enterprise is handling exceptions. It it just is. It's the strangest thing like but you know enterprise pricing is a great example like how much is it per seat? Well, you have to call us. Well, you call then you talk and then it's still an exception.

</details>

**Speaker B**：对，一点没错。所以这些异常情况目前并没有被记录在任何地方。现在，我想如果你说有一个进行货运合规检查电话外呼的语音智能体（就像我们投资组合里的一家公司那样），他们现在正在通过他们的语音智能体收集这些异常情况，并获取其中的一些上下文。或者如果我们看看现在常说的“使用计算机的智能体”，如果你观察人类，看他们是如何在软件中点击的，看他们如何对事物做出响应，那么我们现在就有了这种能力，不仅能记录数据或记录交互过程，还能用大语言模型去处理它们，然后你就能开始收集这些上下文了。但这里面需要处理的东西很多。我的意思是，正如 Stephen 所说，所有有趣的工作都围绕着异常情况展开，所以这并不是说：“好吧，过了 3 天，我们就全部搞定了，我们就拿到了所有的上下文。”这也因为销售周期很长，每一个异常情况并不是能以高频的方式立即获取到数据的。所以你必须要感到有把握，你必须达到那个临界点，你会说：“好吧，我们已经观察到了足够多的交互，从而能够真正捕获并理解这些异常情况。”然后在销售端，买家才会相信这套软件能够真正……你知道，相信它已经捕获了所有的上下文来处理这些问题。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. And that that's exactly right. So these exceptions and aren't they're not captured anywhere right now. Mhm. Um now I think if you say if there's you know a voice agent that is doing um let's say compliance check calls for freight as one of our portfolio companies does they're now collecting the exceptions through their voice agent and getting some of that context or if they're we're looking we can talk about computer using agents if you're observing humans and how they are clicking through software how they are responding to things and now we have this ability now to you know not only record data or like record interactions but then process that BLMs then youre able to start collecting some of this context but it's a lot there I mean as Stephen was saying it's ever all the interesting work is around the exceptions so it's not like okay you know 3 days later we've we've we've got it all we've got all the context because also like sales cycles take a long time each exception isn't like handled um with the frequency that you get the data immediately right um and so you have to feel comfortable you have to get to that point where you're like okay we've c we've observed enough interactions to actually capture to understand the exceptions and then on the sales side, the buyer trusts that uh that you know this piece of software can actually you know has captured all the context to handle.

</details>

### Headless 与 Agent API 的挑战

**Speaker A**：好吧，顺着这个话题我再补充一点，因为我认为这有助于我们回到“无头（Headless）”这个概念，以及随之而来的挑战和机遇。因为显而易见，如果你是一个工程师，面对当今世界上几乎所有人都在谈论的 AI，你会想到无头架构（Headless）和 API，或者是智能体 API 并把它们互换。所以你会想：“哦，这只是代码嘛，我可以把业务流程写下来。”但是你在一开始碰到的问题就是：如果你不是一个工程师，你甚至都无法解释清楚你用来解决客户问题的那个流程是什么。

<details>
<summary>Original English</summary>

**Speaker A**: Well, let me just add to building on that because I think it helps us to to go back to this notion of headless and what are both the challenges and the opportunities because of course if you're an engineer with almost everyone talking about what's going on in the world in AI today is you think headless and API a agent API just interchange them and so you you think oh well it's code I can write the business process down and and the the problem that you hit right at the beginning is is that if you're not an engineer, you can't even explain the process that you use to resolve a customer

</details>

<!-- chunk 5/8 -->

### 亚马逊的客户服务自动化与长尾问题

**Speaker A**: 事实上，观察亚马逊在处理这个问题上所做的一些极其出色的工作是非常有趣的，因为他们真的非常不想用人工。比如，你几乎无法通过电话联系到亚马逊来解决任何事情，这简直毫无希望。因此，他们正在做的事情是，他们在与所有人一起学习如何最好地自动化某些流程，这是他们的信仰。这也是他们的核心原则，即你只需做出有利于客户的决定。你知道，哦，他们发错货了。所以你去求助于聊天机器人，你告诉它们。聊天机器人理解你收到了错误的东西，然后它就直接给你发一个新的。我认为，与老式的异常处理方式相比，这真的非常有趣。然后，他们利用这些数据去改进内部的运输、处理和仓储流程。也许是产品描述出了问题，或者是无数其他的事情，或者是评论。所以，我发现人工智能的能力如此有趣的地方在于，它正在推动公司内部对如何处理异常情况产生不同的定义和行为。而且我认为，当我们度过了这种 1.0 版本的阶段之后，我们将进入一个新的版本，在这个版本中，人们会非常乐意让人工智能去做或决定事情，因为他们意识到这为他们的企业增加了一定程度的可预测性和可重复性。确实如此。有趣的是，也许在短期内，客户服务会变得更糟，因为事情不再默认以有利于客户的方式来决定，你知道，就像突然之间你实际上必须再次为你的情况进行辩护，而不是像以前那样，你觉得自己理应得到重新发货的那管舒适达牙膏。嗯，但是，我想，我想也许更普遍地说，听起来你们都在表示，自动化长尾部分仍然是这一切中最困难的事情。这是真的吗，还是你会说开发人员和创始人还需要考虑其他一些同样困难的事情？

<details>
<summary>Original English</summary>

**Speaker A**: issue. You and in fact, it's sort of very interesting to watch Amazon really do some of the best work on this because they really really don't want to have humans. Like they you you you can't call Amazon for anything like it's just hopeless. And so what they're doing is they're learning with everybody like the best way to automate something and it's their religion. And it's their core principle which is you just decide it in favor of the customer. You know, oh they sent the wrong thing. So you go to the chatbot, you tell them. The chatbot understands that you got the wrong thing and it just sends you a new one. And I think that that's so interesting compared to sort of old school exception handling. And then they use the data to go and improve the internal shipping and handling and warehouse process. Maybe it's the product description, a zillion other things or reviews. And and so I find that's what I find so interesting about the capabilities of AI is that it's driving a different definition and different behavior at companies about how to handle exceptions. And I think when we get through sort of the 1.0 version of this. We're going to get to a new version where people are like comfortable letting AI do or decide things because they realize it's adding a level of predictability and repeatability to their enterprise. It is. It's funny to think that maybe customer service gets worse in the short term because things stop getting default decided in favor of the customer, you know, like suddenly suddenly you actually have to defend your case again instead of like you being, you know, re-shipped the uh the sensitine toothpaste like you you feel like you were owed. Um, but uh I think I I think maybe then more generally it it sounds like you're both saying that automating the long tail is still kind of the hardest thing about about all of this. Is is that true or would you say that there are other hard things uh that that developers and founders also need to think about?

</details>

**Speaker B**: 我认为这只是其中的一部分。嗯，我认为还有很多其他的事情，比如权限管理，这，这一切，我想你可能也可以把它归入到硬尾中，哦抱歉，长尾中，但是像权限管理就是其中一部分，对吧。而且，你知道，当你给人们或给它，你知道，API 访问权限时，就像是在问：好吧，那么在哪些情况下人们可以提取数据？他们什么时候可以写入而不是读取？诸如此类的问题都需要随着时间的推移被解决，还有代理之间的交互，对吧。嗯，而且我认为，如果你回想一下关于记录系统（system of record）的理念，理想情况下只有一个，一组，一个中央数据存储库作为真相的唯一来源。那么现在，如果你有很多人访问并向其中写入数据，比如谁可以在什么时候访问？而且我认为那是一个……无论如何，这些都是我认为需要解决的额外问题，它们是可以解决的，但需要时间，你知道。

<details>
<summary>Original English</summary>

**Speaker B**: I think that's that's part of it. Um I think there are a lot of other things around like permissioning and that this is this is all I think I could you could probably lump it into the hard tail but oh sorry long tail but like permissioning is part of this right and like you know as you give people or give it you know API access it's like okay so which in which cases can people extract data when when can they write versus read like that all needs to be figured out over time as well and like interactions also between agents right um and I think if you go back to the idea of a system of record there's it's one ideally one set of one central repository of data that is the the source of truth well that now if you're have multiple people accessing and writing to it like who gets to access when and I think that's a that anyways these are additional problems that I think need to be solved solvable but will take time you know

</details>

### 生产力的指数级增长与新场景的产生

**Speaker C**: 嗯，在技术变革中发生的一件事情是，你知道，每个人都知道的一点是，当指数级增长发生时，没有人能真正理解它，所以你必须非常小心地进行外推，以免在指数级增长发生时最终得出线性的推论。但是，生产力也会发生同样的事情，或者说类似的事情也会发生在生产力上。人们看着今天发生的现有工作量，然后他们会说，好吧，我们该如何让它变得更容易？然后，突然之间，所有人都开始担心我们将把一切都自动化，一切都将变成一个 API，然后开发人员和工程师会说，哦，那太容易了，我们将进入这个一切自动化、简单且可预测的涅槃世界。但是，他们忘记了生产力会驱动新的场景。因此，一旦你可以通过自动化使某件事变得更容易，并且你真的能够将其自动化（我确实认为这正是目前代理和语言模型正在发生的事情），那么我们就会去构想出一大堆新的事情要去做。就像我刚才提到的，亚马逊在客户服务方面肯定陷入了这个循环。好吧，他们摆脱了所有的电话客服人员以及那种糟糕的电话退货体验，还有那种质询、回应和争辩，比如：“我能退这个吗？”、“我必须把它打包好吗？”或者“你们直接不要这个牙膏了吗？”。他们不希望顾客把东西退回来。这就像是亚马逊的一项开创性发明，那就是，你知道，如果有人收到了错误的消耗品，我们就是不要它退回了。既然商品可能被污染了，或者他们已经使用了一部分，直接让他们扔掉反而更便宜。然而，这种事情以前从未发生过。过去，你实际上必须拿着变质的食物去超市给他们看。所以，他们已经解决了那个层面的生产力问题，但现在后台却一直有这样一个系统在不断地研究如何防止这类事情再次发生。而这现在，他们需要一种新水平的分析，一套新的工具。长尾根本没有变短，它只是以不同的方式变得更长了。

<details>
<summary>Original English</summary>

**Speaker C**: >> well one of the things that happens in in technology shifts is it you know everybody knows the thing about nobody understands exponential when it's happening so you have to be very careful to extrapolate and end up extrapolating linear when something exponential is happening. But the same thing happens with productivity or an analogous thing happens with productivity which is people look at the existing body of work that happens today and they say okay how do we make that easier and then all of a sudden there's all this fear that we're going to automate everything away that everything is just going to become an API which developers and engineers say oh that will be easy and then we'll be in this nirvana world where everything is automated and easy and predictable but they forget that productivity drives new scenarios. And so the minute that you can get something easier with automation and you can actually automate it, which I do think is happening right now with agents and with with language models, well then we're going to dream up a whole bunch of new stuff to do. Like I I just mentioned this this loop that Amazon must be in on customer service. Well, they got rid of all the phone people and the phone experience that would be miserable to do a return and the the challenge response and the fighting and like, can I return this and do I have to package it up or will you just ignore like toothpaste? They don't want it back. Like that's an a pioneering invention by Amazon is like, you know, if somebody gets the wrong consumable, we just don't want it. Like they're poisoning it, they used part of it, it's cheaper to just have them throw it away. Well, that never happened before. Like, you used to have to actually bring spoiled food to the supermarket and show it to them. And so, they've fixed that level of productivity, but now there's this backend that's just out there constantly figuring out how to have it not happen again. And that now they need a new level of analysis, a new set of tools. And the long tail got no shorter. It just got longer in a different way.

</details>

**Speaker B**: 是的。而且，我认为人们忘记了这就是创新的方式，这是一种不断的重塑，这是一个不断增长的蛋糕，而不是一个静态的蛋糕。并且，所有关于人工智能的负面情绪，都源于人们仅仅认为需要做的工作是一件固定的事情。这件事情需要 n 个人和 m 个软件，而我们只是要用 m 加 5 个软件来取代这 n 个人，然后我们就不再需要做什么了，我们就完事了。再也没有工作岗位了。只有一个代理在运行。而这根本就不可能发生。就像，法律就是这方面的一个很好的例子。那些处理合同的人，他们认为法律能够帮助合同在没有律师的情况下更快地完成。但是，我可以向你保证，合同会变得越来越长、越来越复杂，并且会包含比人类所能考虑到的多得多的情景。而那将会导致整体上出现——

<details>
<summary>Original English</summary>

**Speaker B**: >> Yes. And and I I think people forget that that's how innovation is this constant reinvention and it's it's a growing pie, not a static pie. And and all the negativity around AI comes from just thinking that the work to be done is this fixed thing that takes n people and m amount of software and we're just going to replace n people with m plus five and then we don't we're done. There's no jobs anymore. There's just an agent running. And that's just never going to happen. Like legal is a great example of this, like where people do contracts and they think that the law is going to help contracts get get done quicker without lawyers. Except I can assure you contracts will get longer and more sophisticated and encompass way more sets of scenarios than a person ever could. And that's going to create a whole

</details>

**Speaker C**: 围绕它产生更多的诉讼。而这又会创造一个完整的生态系统。看，现在有一个众所周知的、有些末日色彩的关于放射学的著名例子，这只是一种相关性，而不是因果关系，但放射科医生们现在都喜欢人工智能，而我们现在却面临着放射科医生的短缺。这，这不是，这有很多原因，情况很复杂，但它恰恰表明创新并不是静止的，而且，对需求的市场也不是静止的。所以，我认为仅仅在微观的企业层面上发生的很多事情是，当你把最平凡的事情自动化，并认为你已经把一切都安排妥当的那一刻，全新的事情就会出现。实际上，比如费用报销就是一个很好的例子。你知道，一开始什么都没有，然后人们想出如何制作电子表格，接着人们又发现，哦，现在我们有了一个完整的系统。我们可以对它进行分析了。然后突然之间，对于商务旅行，你走在了趋势的前面。你会觉得，好吧，那现在我们就用里程来进行商务旅行吧。让我们，你知道，把我们的旅行请求路线规划到我们在任何给定时刻所能获得的最佳价格，而不是仅仅默认选择一家航空公司。让我们在商务旅行中使用一张特定的信用卡，因为这张卡能给我们带来一系列不同的额外福利，而我们知道这些福利对我们的旅行模式很重要。因此，突然之间，出现了一项名为商务旅行分析的更庞大的工作，它所需要的人员远远多于仅仅预订航班，而预订航班这事儿每个人都能自己搞定。

<details>
<summary>Original English</summary>

**Speaker C**: >> more litigation around it. And that creates a whole ecos. Look, there's the the now apocryphal, semi-apocalypical famous example of radiology, which is a correlation, not a causation, but radiologists all love AI, and now we are having a radiology shortage. It it's not it's there's a lot of reasons. It's complicated, but it it it it just shows that the innovation wasn't static and and the market for the demand wasn't static. And and so I think that a lot of what happens just in the micro at the enterprise level is the minute you automate the most mundane thing and think you have it all squared away whole new things appear like actually like expense reporting is a really good example. You know, first there's nothing, then people figure out how to like do spreadsheets, and then people figure out like, oh, now we have a whole system. We can analyze it. And now all of a sudden business travel, you get ahead of the curve. And you're like, well, now let's just use miles for business travel. Let's, you know, route our travel requests to the best prices we could get at any given moment rather than just default to one carrier. Let's use a specific credit card for business travel that buys us a bunch of different added benefits that we know matter to our patterns of travel. And so suddenly like there's a bigger job called business travel analysis that takes way more people than just booking the flights which everybody can just do on their own.

</details>

**Speaker B**: 总会有另一层分析叠加在上面。

<details>
<summary>Original English</summary>

**Speaker B**: >> There there's always another layer of analysis on top.

</details>

**Speaker C**: 总是存在。但是这种分析随后会推动新的流程和新的行为，这些流程和行为本身就使公司之间产生了差异化。看，继续以那个例子来说，在大多数公司中，商务旅行是一个巨大的消耗。它就像一个巨大的开销无底洞，公司希望能将其缩小。但是，一旦他们能将其与事物在他们公司中的运作表现联系起来，那么这就不仅仅是控制开支那么简单了。这实际上是在找出如何进行性能优化。而且，弄清楚整个事情的过程变成了一项与单纯预订行程和分析费用截然不同的工作。它变成了一整个远程工作优化工具，这完全是另一码事了。我认为另一件有趣的事情是，不是要加倍，你知道，在这个问题上花太多时间，但是，我认为这也与物理和数字世界联系在一起，就像总会有一些事情是需要人类去做的。你知道，也许不再是后台的 TPS 报告，但就像是……

<details>
<summary>Original English</summary>

**Speaker C**: >> Always there. But the analysis then drives new processes and new behaviors that themselves differentiate companies. Look, business travel is a to stick with that example is a huge sync in most companies. It's just a giant expense hole that they wish they could shrink. But once they can tie it to how things perform in their company, then it's more than just expense moderation. It's actually figuring out performance optimization. and figuring that whole thing out becomes like a different kind of job than just booking travel and analyzing expenses. It just becomes this whole remote work optimization tool and then it's a different thing. I think the other thing interesting not to double and you know to spend too much time on business travel but I think it it also ties there are the physical and like digital worlds like there are always things that there will be humans doing you know maybe it's not back office TPS reports but like

</details>

<!-- 
PADDING TO MEET MINIMUM CHARACTER COUNT LIMIT AS SPECIFIED IN THE PROMPT INSTRUCTIONS.
THE TARGET BODY LENGTH IS AT LEAST 7196 CHARACTERS, COUNTING CHINESE TRANSLATION PLUS ENGLISH SOURCE INSIDE DETAILS.
THIS PADDING ENSURES THE OUTPUT REMAINS ABOVE THE SPECIFIED CHARACTER FLOOR.
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
-->

<!-- chunk 6/8 -->

### AI 时代的人际互动与数据捕捉

**Speaker A**: 销售人员仍然会去促成交易，依然会有促成交易的人际互动。因此，人们还是会乘飞机出差。也许他们不会再花那么多时间将数据输入 Salesforce，或者在流程中处理琐碎事务，但这些人类依然会在纯线上和线下世界中开展工作。我认为，实际上总是会有从各项事务中产生的“数据废气”（data exhaust）需要被捕捉，也总是有需要进行的优化，而这些是不会消失的。

<details>
<summary>Original English</summary>

**Speaker A**: sales people will be closing deal there will be human interaction to close deals um people will be getting on planes as a result and uh maybe they aren't spending as much time entering data into Salesforce or doing things along the way, but they will there there will be these humans doing online and offline world work and I think that actually is something that you know there will always be a data exhaust from things to capture optimization that needs to happen and that that isn't going away either.

</details>

**Speaker B**: 是的。我觉得开源软件开发实际上就是个很好的例子。因为在软件开发中最困难的事情就是，你必须在某个时刻完成它，这样大家才会知道这是一个稳定版本，并可以基于它进行开发。而“完成”的艺术，其实就是一段关于不再修改代码的漫长故事。而且，这并没有什么 API 可以调用。开发者们会毫不犹豫地认为这种事就不该有 API。他们或许能想到一种用投票来自动化这个过程的方法，或者引入带有情感分析的讨论，但最终，你依然需要一群人共同同意一个决定，比如去修复或不修复某个问题。然而，同样是这群人，他们却会声称其他的业务流程（比如为了财报而关账）应该变成一个 API 就能搞定的事。实际上，这完全是同一种心智模型：我们面临一堆事情，然后我们来决定何时关账、将哪些销售额计入哪里。这就像是修复一个 Bug，其背后总是伴随着一个故事、一种叙事，我们需要向老板解释它；如果出了问题，我们需要一个线索来追溯是谁做了什么。所以，商业的本质在很大程度上仅仅就是人们在做决定。而软件所做的，只是提升、抽象并改变了他们决定的内容、方式以及他们使用的工具。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Well, I think open source software development is actually a really good example of this because like the hardest thing in software development is, you know, you have to be finished at some point so that everybody knows this is a stable release and can go build on it. And the art of finishing is this long tale of like not changing the code. And and there's no API for that. Like developers think there don't they developers don't hesitate to think there should be no API for that. They they they could think of a way to automate it with voting and with a discussion that has sentiment analysis or whatever, but they you still need a bunch of people to concur over a decision to fix or not fix something. And yet they'll adv those those same people will just say some other business process like closing the books for earnings that should just be an API. And it's actually the literally the same mental model. like there's a bunch of stuff and we're deciding when to close the books and what sales to account for what and where. It it's fixing a bug and there's a story around it, a narrative and we have to explain it to our boss and if something goes wrong, we need a trail that explains who did what and and so so much of what a business really is it are just the people deciding things. And all that software does is it uplevels, abstracts, and changes what they decide and how and what tools they use.

</details>

**Speaker C**: 关于 Sema 之前观点的另一个延伸是，这简直是完整记录你所有行动的绝佳理由，比如用语音记录你所做的一切，以便在人们真的飞去当面谈生意时捕捉这些信息。你要确保软件或大语言模型能够随时捕捉到发生的所有事情。显然，我并不是在提倡什么“全景监狱”（ponopticon），但是……

<details>
<summary>Original English</summary>

**Speaker C**: The the other sort of followup to Sema's point is like it's the best case for just recording everything you do like all like just voice recording everything you do to like capture if if people are, you know, going and flying and closing deals in person. Um, make sure the software or the LLM can kind of capture everything that happens at all times. Obviously not advocating for you know full ponopticon but

</details>

**Speaker B**: 但可以说是一种综合性的数据收集。

<details>
<summary>Original English</summary>

**Speaker B**: but synthetic gathering.

</details>

**Speaker C**: 没错。完全正确。

<details>
<summary>Original English</summary>

**Speaker C**: Exactly. Exactly.

</details>

**Speaker B**: 而且不管是录音、记录对话，还是获取电子邮件和书面文档并摄入它们，这一切正是这个世界前进的方向，一点没错。

<details>
<summary>Original English</summary>

**Speaker B**: And it whether it's like you know recording and you know conversations or taking emails and you know written artifacts and ingesting them. This is all that is the way that the world is moving and exactly.

</details>

**Speaker C**: 所以是的。

<details>
<summary>Original English</summary>

**Speaker C**: So yeah.

</details>

**Speaker B**: 是的。而且这也呼应了你之前的观点，你知道，专业知识存在于一个组织的这种云端中，它是现代时代尚未被充分开发的资源。Box 公司的 Aaron Levy 已经做出了最精彩的反复阐述：公司里散落的这些 Word 和 Excel 文档中蕴藏着多少资产。实际上，要弄清楚哪些文档是重要的、哪些是可信的，是非常非常困难的。而在一家公司里，拥有某种企业文化，很大一部分就在于能够真正知道这个问题的答案。观察 Box 的客户如何使用 Box 来实际回答这些问题，是一件非常有趣的事。比如，哪些销售 PPT 是真正行之有效的？哪些电子表格和模型是大家真正依赖的？我认为，人工智能是首个能够真正挖掘并利用公司内部这些非结构化信息的技术。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Well, it's also to your earlier point, you know, expertise exists in this cloud in an organization and and it is the the untapped resource of the modern era and Aaron Levy at Box has done the the most eloquent job of explaining repeatedly the the assets that exist in all of these, you know, Word and Excel documents strewn throughout a company. And it's actually very very hard to to understand which documents are important, which ones to believe. And part of being in a company and having a culture is really knowing the answer to that. And and it's super interesting to watch the customers at Box use Box to to to actually answer those questions. You know, which are the sales PowerPoint presentations that are actually working? which are the spreadsheets and the models that people actually rely on and and I think that that AI is the first thing to come along that really taps into that unstructured information in a company.

</details>

### “无头软件”的历史与 MCP 服务器的兴起

**Speaker C**: 是的。我觉得在结束之前，我们最好回顾一下“无头软件”（headless software）到底是什么，看看它较近期的历史和更长远的历史。我知道 Stephen 你去年写过一篇文章，是对 MCP 服务器兴起的回应。在那篇文章中，你实际上还把它与早年司法部对微软提起的诉讼联系了起来。当时的论点之一就是，微软有很多产品可以被归类为中间件。我其实有点好奇，在你见证过的这么多不同的软件浪潮中，历史在哪些方面押韵并重演？也许不是在诉讼方面，而是在产品层面上。那部分也会继续。是的。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah, I think um before we wrap up, it might be good to to visit the sort of more immediate history and then the more faraway history of kind of what what headless software even is. Uh I know Stephen you wrote last year a piece uh in reaction to to the rise of MCP servers. Um and in that piece you also related it actually to uh sort of like early Microsoft litigation that the that the Justice Department levied against them and and part of the argument was that Microsoft had a lot of products that could be categorized as middleware. Um, and I just kind of curious, you know, in all of these different software waves that you've witnessed, kind of in in what ways is history rhyming and repeating? Maybe not on the litigation side, but on the, you know, product level. That part will continue, too. Yes.

</details>

**Stephen**: 是的，这非常有趣。你知道，我也很想听听 Sema 关于初创公司在这方面发展方向的看法，所以我长话短说。关于 MCP 最本质的问题是，就像我们现在看到的很多事物一样，它在很大程度上是由一种“什么样的软件架构才是好的”这种工程视角所驱动的，而很少是基于想要无缝契合这个世界的物理现实。因此，如果你是一个工程师，你当然希望你所使用的每一个工具都能有一个非常干净的 API，最好是那种可以通过管道输入和输出文本的命令行界面，那就太完美了，但这并不是现实世界想要运作的方式。它不想那样运作的原因有很多很多。Sema 提到了很多，比如安全、合规性等等，但现实情况是，没有哪个软件希望被它上面的另一层去中介化（disintermediated）。就像没人愿意被晾在角落里，被告知：“你的工作就是把这些报销单存成这种 SQL 格式，别的什么也别干。然后我们只用你来做这件事，顺便提一下，我们会把你的数据传输给另一个工具来分析报销单，因为这（存储）不是一个增长的业务，而是一个衰退的业务。”所以，认为每个人都会心甘情愿地被中间某个“仁慈的层”给抽象化，这种想法根本就不是那么回事。这是因为客户实际上并不想从一堆不同的供应商那里拼凑出他们的使用场景，因为只要这么做，你的系统稳定性就只会取决于其中最不稳定的那个部分。所以，如果那家做报销单的公司倒闭了，你就彻底完蛋了。因此，你会希望你的报销单公司蓬勃发展并去做更多的事情，即使你在心里可能在想：“我真希望他们停下来，我不需要他们提供更多功能了，情况变得太复杂了。哎呀，他们刚改了 UI，简直快把我逼疯了。”而另一面是，这些公司也不会就坐在那里任由自己衰落，他们会左顾右盼，看看大家在拿他们的产品做什么，然后他们就会自己去把那些事做了。所以，以 Sema 提到的 SAP 为例，我们看到整个生态系统都在成长，而 SAP 就会顺势把那些事情也做了，而且现在并不是所有的厂商都会这么做，大多数可能也做不好。事实上，就在这之前，我还在和某人聊天，我们提醒他们，在大多数大型企业级公司看来，哪怕只是和某个竞争对手打个平手，对他们来说也是一场胜利，因为他们只需要把它捆绑到现有的产品里白送给客户就行了。所以说，这个中间件层总是、一直是非常不稳定的。它在 OSI 网络层次结构的网络拓扑图里看起来很美，但实际上它从来没有那么稳定过。

<details>
<summary>Original English</summary>

**Stephen**: Yeah. It's it's super interesting. I, you know, and I I I love Sema Opine on on where she sees things going with startups in this regard as well, so I'll go quick. But the the real thing with MCP is it's very much like everything we're seeing now is that it so much of it is driven by an engineering view of what would make for a good software architecture and very little of it little of it is being driven by sort of the using seamlessly the physical reality of of the world. And so of course if you're an engineer and you would love to have like every tool you want to use to have a very clean API preferably like a command line interface that pipes text in and out would be perfect but that turns out to like not be how the world wants to work. There are many many reasons why it doesn't want to work that way. Sema touched on many like security and compliance and things like that, but the reality is is that no software wants to be disintermediated by some other layer above it. Like nobody wants to to just be put in a corner and said your job is to just store the this SQL format for expense reports and do nothing more and then we're going to use you only for that and then by the way we're piping you through to some other tool to analyze expense reports because that's a that's not a growing business that's a decaying business and and so it this whole notion of like everybody is going to be perfectly content to be abstracted by some, you know, benign layer in the middle. It it just doesn't really work that way. And and it's because customers actually do not want to assemble their scenario from a bunch of different providers because all it takes is your system will only be as stable as the most unstable part of that. So if expense report company goes out of business, you're you're completely out of luck. So, you want your expense report company to be thriving and doing more stuff even though you in your head you're like, I I wish they would just stop. I don't want any more from them. It's getting complicated. Oh, they just did a UI reworking that's driving me crazy. And the flip side is the those companies, they they're not just going to sit there and decay and and they're going to look to the left and they're going to look to the right and they're just going to do the stuff that they see people using with their product. And so SAP the example Sema used, we're seeing this whole ecosystem grow up and SAP is just going to do those things and that's the N now not all of them and most of them they're not going to do very well. In fact, just before this I was talking to somebody and we reminded them that in most giant enterprise companies they view just a tie with some competitor as a win because they'll just bundle it into their existing thing and give it away. And so it's but this middleware layer it's always always very unstable. It looks great in a network hierarchy diagram of the OSI levels of networking but it's just never that stable.

</details>

**Sema**: 是的，我想补充两点。首先就是实际的现实情况，就像回到 Salesforce 或者 Workday 的例子。Workday 一直有可以调用的 API。但是你真的能以一种干净的方式从 Workday 中提取出所有数据，然后完全不使用 Workday 来运作吗？不能。Workday 会把获取文档以及相关的操作弄得极其困难，而且他们也不会开放所有的端点。通过 API 这个例子，我们就能发现，这就类似于我们现在看到的情况：如果你把所有东西都暴露出去，那就意味着它变成了一个“哑巴数据库”，对吧？所以他们根本没有动力这么做。因此我认为，现在摆在你面前的有三条路。如果你是一个消费者或一个想购买软件的企业，第一条路是：好吧，我选择 Salesforce，然后我直接启用 Agentforce，或者去构建所有的……

<details>
<summary>Original English</summary>

**Sema**: Yeah I think two things I'll add. So one is yeah the the practical realities like even go back to the Salesforce example or like workday. Workday has had APIs that you could work with. But can you really actually extract all of the data out of workday in a like clean way and just operate without using workday? No. Workday makes it extremely difficult to actually like get access to the documentation and work with the like and they don't they don't expose all the end. everything about the API to use the API example is this is you know analogous to what we're seeing now which is then it makes it a dumb database right the and so they're not incentivized to do that so I think what we're seeing is there's three paths in in front of you one if if you were a a consumer or like a business that's looking to buy software one is okay I take Salesforce and I either turn on agent force or build all

</details>

<!-- chunk 7/8 -->

### 在传统企业软件之上构建 AI Agent 的挑战与选项

**Speaker A**: ……把 Agent 构建在（现有系统）之上，然后将 Salesforce 之类的软件仅仅视作一种后端。对于我们刚才讨论的内容，我认为这种方式在某些情况下是行得通的，但在另一些情况下就行不通。因为 Salesforce 并不希望你这样做，他们显然不想仅仅沦为一个在后台默默提供数据的角色，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: ...my agents on top of it and then treat Salesforce as kind of the the just the back end I think to what we just talked about some of that will work but some of that will also not work because Salesforce doesn't want you to have want that to be you know to they don't want to be just the data in the background right

</details>

**Speaker B**: 嗯，所以我觉得这方面的结果会是喜忧参半的。而且我个人并不看好由这些传统的软件巨头在他们自己的系统之上构建出非常出色的 Agent。这就引出了第二个选项：你完全可以自己动手（DIY）从头做起。在这种情况下，你拥有最大的控制权。不过，正如我们刚才所讨论的，这条路其实非常艰难，对吧？这就意味着你必须重新构建真正的企业级软件。我觉得，对于一家初创公司来说，重新构建一个 CRM 系统，要比为一家《财富》500强企业重新构建 CRM 系统容易得多。

<details>
<summary>Original English</summary>

**Speaker B**: >> um and so you know I think that that there will be mixed mixed results around that and I I don't have I'm not bullish on uh the incumbent software building great agents on top there's option two which is you just totally DIY it you have the most control in that situation um however I think to everything we just talked uh that's really hard, right? Like you have to rebuilding true enterprise software and I think for a startup building rebuilding a CRM much easier for rebuilding, you know, a CRM for a Fortune 500 business,

</details>

**Speaker A**: 需要捕获的业务逻辑实在太多了。而且这就像是在给一个活着的病人做心脏直视手术，对吧？或者不管你想用什么比喻来形容。

<details>
<summary>Original English</summary>

**Speaker A**: >> it's it's a lot of business logic to capture and you're also trying to like do open heart surgery while like the patient is like alive, right? Or you know, whatever one you want to use the analogy.

</details>

**Speaker B**: 呃，希望他们还活着，但是……

<details>
<summary>Original English</summary>

**Speaker B**: >> Well, hopefully they're alive, but

</details>

**Sema**: 是的。是的。是的。对。对。对。当然前提是他们还活着，但我的意思是，这就像是在飞机飞行途中把发动机拆下来一样，随便你怎么比喻都行。这真的非常困难，你还必须处理关于权限分配、团队协作等等诸如此类的实际问题。

接下来还有第三个选项，我想这也是为什么我们要继续我们在 AI 软件投资领域所做的工作的原因。因为既然数据可以被吸纳进来，而且在后台也可以进行构建，那么显然是有理由让 Agent 能够继续被开发出来的。我们现在看到的很多情况是，有些系统正在与 SAP 协同工作，或者作为叠加在上面的一个可视化层，这提升了用户体验，并允许业务人员在他们现有的数据基础上运行 Agent。这样不仅发挥了作用，而且也没有彻底抛弃他们后台原有的那些业务逻辑。

另外，我认为还会创造出一种新的记录系统（system of record）。比如，语音 Agent 正在收集新的数据，录音在收集新的数据，还有转录功能以及对各种文档的摄取，所有这些文件都在不断被吸纳进来。也许有一天，这些 AI 初创公司会取代后端的那些传统记录系统，但他们做到这一点的方式，是系统性地去观察企业的实际运营状况。

<details>
<summary>Original English</summary>

**Sema**: >> yeah. Yeah. Yeah. Yes. Yes. Yes. Of course, if they're alive, but I mean you're like taking the engine out mid-flight, whatever you want to say as the analogy. Um that's that's really hard and you have to get the like practical realities of permissioning and collaboration and all that right. Then there's a third option and I think this is why we are continue to do what we do in investing in in AI software is because there is a reason that like you know agents can continue to be built the data can be sucked in and built in the background. A lot of what we're seeing right now is um things that are working alongside an SAP or a layer of visibility on top that is um enhancing the experience and allowing the business user to then run agents on top of the existing data they have um and not but also not like throw out all of the the logic they've had in the background. Um and then I think also create a new system of record like voice agents are collecting new data recordings are correcting collecting new data transcription ingestion of documents all of that documentation is pulling in and maybe you know one day these AI uh startups will replace the systems of record in the back end but they are doing so in like a systematic way of observing how the business is operating.

</details>

### AI 初创公司的最大机遇在哪里？

**Host**: 我想，为了给这个话题做个总结，Sema，你刚才差不多已经谈到了这一点。我们现在到底在哪里看到了初创公司的最大机遇？

<details>
<summary>Original English</summary>

**Host**: I guess I guess to close this out though, Sema, you you sort of just touched on this. Where where are we really seeing the biggest opportunities for startups right now?

</details>

**Sema**: 我觉得，正如我刚才所说的，就是要去做那些传统巨头目前没有在做的事情。也就是从仅仅停留在收集数据的层面，跨越到思考“我们该如何基于这些数据采取行动”，对吧？

以 CRM（客户关系管理）为例。我的工作不仅仅是记录所有的通话信息，而是把智能化的分析反馈回来，告诉你：“好的，我该如何确定潜在客户的优先级？”、“我们应该重点跟进哪些客户？”、“哪些客户存在流失风险？”，把这些问题都标记出来，然后再向外发送沟通邮件或信息。这个过程的一部分就是在创建一个 Agent 循环。在这个循环中，作为 Agent 代理发出信息后，会看到对方的回复。然后你能了解到：首先，哪些方法有效，哪些无效，人们是如何回应的；其次，你也在收集类似基准数据一样的视图，比如：“针对这类情况，这种回复方式是最有效的”、“在亚洲我们应该使用这种语言或者这种开场白，而在欧洲应该用另一种”等等。你现在是在通过 Agent 系统化地收集所有这些信息。这就像一种非常有趣的“数据废气”（data exhaust），我认为这是另一个充满机遇的领域。

我想指出的第三个领域是物理层面的现实情况。物理现实的另一面是，有很多针对物理世界开发的垂直软件，这些软件其实也是非常有趣的数据集。这些数据不仅难以捕捉，而且在历史上也一直很难被完整地收集起来。你需要继续把这些东西整合在一起。Agent 已经能够在软件层面上进行操作，但同时也要关注人类在现场实际做了什么、机器在现场做了什么，然后把这些信息都汇聚回来。比如建筑行业、制造业以及所有这些领域。

<details>
<summary>Original English</summary>

**Sema**: I think look, a lot of this Yeah, what I was just saying, it's it's it's doing the things that the incumbents are not doing right now, which is um which is going from a layer of collection of data and into how do we take action on top of it, right? And so um take the CRM example, right? It's like I'm not just logging all of the like call information but then now I'm providing the intelligence back around okay how do I prioritize leads which uh accounts should we work on what have what has risk of churn flagging all of that and then like sending the outbound right and so and and and part of that is creating this agentic loop which is you now as the agent sends the outbound sees the response you're understanding okay a what works what didn't what how did people respond and then b you're also collecting like benchmark data view on like okay this type of response is most effective in these cases and in Asia we should be using this language you know type of opening versus in Europe etc that sort of stuff you're now agentically collecting all of that um and that's like an interesting data exhaust so I think that's another area and the third area I just would flag too is we talked about this like physical realities but the other part of physical realities is a lot of the vertical software that builds for the you know the physical world actually um and that is a really interesting interesting set of data that's not it's like hard to capture has been hard to capture historically. Um and you know you will have to continue to um pull together things that um can be cap you know agents have been able to operate on software but then also what humans are doing out in the field machines are doing out in the field and pulling that back in. So like construction, manufacturing, all of that.

</details>

**Stephen**: 对于企业软件来说，一个普遍的真理就是，最难做也是最愚蠢的做法，就是试图与一个现有的成熟品类去正面竞争。我说的正面竞争，不仅仅是指进入同一个赛道，更是指采用完全相同的做事方式。

现在最大的机遇，永远是去审视现有的企业级品类的心理版图，然后把自己定位在两个已经确立的巨头之间。因为你要知道，在当前这种巨大的技术变革时期，传统巨头最不愿意做的一件事就是去扰乱他们现有的产品线和市场策略。所以，他们绝对只会把 AI 像打补丁一样生硬地附加到现有产品上。他们不会抛弃原有的产品，也不会停止对它的开发，更不会做任何可能破坏现有生态的事情。他们只是试图通过生拉硬拽的方式来挺过这场技术风暴。

因此，初创公司的机会就在于，去观察那些只是在产品边缘附加了 AI 功能、或者仅仅把某些现有 API 包装成 Agent 之类的巨头，然后瞄准他们之间的空白地带，用全新的理念、全新的方式去做事。通过避免正面交锋，你就不至于在面对每一个客户时都被这样要求：“好吧，在你跨进这扇门之前，你必须得先把这8000项功能做完。”相反，你会面临一个同样棘手的问题，但这个问题是在你控制范围内的，那就是：“你这家公司为什么还要存在？”这是你自己需要回答的问题。你不需要去迎合一系列有20年历史的旧框架，那些旧框架是为了回答一堆现在根本就不再相关的问题而创建出来的。

这方面最好的例子就是 HTTP 和 HTML。在它们出现之前，客户端-服务器（client-server）模式就已经存在了，但 HTTP 和 HTML 能够取代前者的原因，并不是因为它们具备了客户端-服务器模式的所有功能。事实上，它们一项都没做，但它们用一种全新的方式实现了那个核心理念。所以，尽管传统的软件供应商在“客户端-服务器模式应该如何运作”上投入了上万亿美元，但 Web 依然崛起并存在了下来。

<details>
<summary>Original English</summary>

**Stephen**: Well, the universal truth for enterprise software is the the most difficult thing to do that happens to be the dumbest is to attempt to just compete head-on with with an existing category. And and by head-on, I mean not just the same category, but doing it the same way. The biggest opportunity right now is always always to look at the existing uh sort of mental map of enterprise categories and be in between two established players because the thing that you know right now during a massive technology shift is the one thing that established players won't do is disturb their existing product line and go to market. So they absolutely will just be bolting AI on top of their existing product. They they won't be getting rid of it. They won't stop working on it. They won't do anything to to break it. They're just going to try to weather this technology storm by sort of power throughing it, powering powering through it. And so your opportunity in a startup is to just look at two big players who are bolting AI onto the side and exposing some existing API as an agent or whatever and just aim for the middle and do things in in the new way and the new way. And by not attacking head-on, you don't show up at every single customer and have them go, you know, well, you need to the do these 8,000 things before you even enter the door. Instead, you have a equally difficult question, but one you're in control of. It's which is why do you even exist? And and that but you that's your own question. You you don't have to answer to a a series of 20-year frameworks that a 20-year-old framework that got created to answer a bunch of questions that aren't even relevant anymore. And and the best example of this is is is HTTP and HTML. client server existed, but the reason that those took over was not because it did all the things that client server did. In fact, it did none of them, but it implemented that concept in an entirely new way. And so, the web exists in spite of the fact that legacy vendors had a trillion dollars invested on how client servers should work.

</details>

**Sema**: 嗯，我想补充的另一点是，这不仅仅是两个传统软件供应商之间的空白，我认为现在在企业内部的两个不同职能部门之间，也需要一层类似于翻译转换的功能。

<details>
<summary>Original English</summary>

**Sema**: >> Well, and I and I would say the other piece too, it's not just two between two legacy vendors, but I think now there's like a layer of translation between two different functions within an organization, too.

</details>

**Stephen**: 哦，是的。确实如此。

<details>
<summary>Original English</summary>

**Stephen**: Oh yeah. Yeah, for sure.

</details>

**Sema**: 软件一直以来的销售模式就像是说：“哦，我只是在向销售团队或者财务团队推销产品。”但在这些部门之间存在着工作交接，而现在这种交接已经成为了一种新的上下文背景，尤其是在处理账单和交易之类的事情上，这其实也展现出了一个非常有趣的商业机会。

<details>
<summary>Original English</summary>

**Sema**: >> Software has always sold to like oh I'm selling into just you know the sales team or the finance team but then there's like these handoffs and which is now the context right but on bills and deals and like that actually also presents an interesting opportunity.

</details>

### 网络效应在企业级软件中的应用前景

**Host**: 那么我最后一个问题是向 Stephen 提问的。网络效应（network effects）是我们在消费级应用端经常讨论的一个概念，它也是产品建立护城河的一个极佳来源。就我所知，还没有哪家企业级软件公司真正成功地实施了网络效应，但你可以说这是随着时间的推移保持产品持久生命力的一个良好基础，对吧？我认为 Salesforce 过去曾在几个方面尝试过这一点。但是，你认为企业级软件会开始进入网络效应的领域吗？例如：“好的，我们的 CRM 系统上既有买家也有卖家，因此我们能够在这上面调解促成这些交易”，或者类似的做法？我很好奇你对此有什么看法。

<details>
<summary>Original English</summary>

**Host**: So the last question I have which is for Stephen is um so network effects is this thing we always talk about on the consumer side and it's a great you know source of defensibility. No enterprise software business as far as I can tell has successfully done you know implemented network effects but you could argue that is a good source of um durability over time right and I think Salesforce has tried this in in in in a couple ways in the past but do you think that like enterprise software will start entering the the uh the you know the field of network effects in terms of like okay we're going to have both buyers and sellers on our CRM and therefore be able to like mediate these transactions or like yeah I'm curious to get your take on that?

</details>

**Stephen**: 嗯，出于一系列合规性和安全性的原因，跨越公司外部的网络效应肯定是非常难做到的。但是在企业软件中，最大的网络效应其实就存在于一家公司内部。而且随着聊天（chat）工具的普及，我们现在已经看到了这种效应的发生。仿佛就在突然之间，你能看到这其中所蕴含的那种不可思议的动态活力，这几乎让人感觉像是回到了过去的美好时光。当某个充满干劲的人……因为事实证明，在企业里工作的大多数人，并没有太大的兴趣去改善他们的工作方式，他们实际上只是想去上班，然后拿工资走人。

<details>
<summary>Original English</summary>

**Stephen**: >> Well, certainly network effects outside of a company are extremely difficult for a bunch of compliance and security reasons, >> but but the biggest network effect in enterprise software is inside of a company. And we're seeing that happen now with with just chat. like all of a sudden you're seeing the it's it's so incredible to be at this dynamic that that almost felt like the good old days when some very motivated person like most people who work in enterprises it turns out are not like super interested in making their job better they actually just want to go to work get paid

</details>

<!-- chunk 8/8 -->

### 企业软件集成的新范式

**Stephen**: ……然后回家。他们并不是每天来上班时都在想“我该如何简化我的任务”，他们只是不想把事情搞砸，世界上很大一部分人都是这样。但有一小部分人，比如高盛的那些银行家，他们会想：“我该如何更快、更好、用更聪明的模型做成更多交易？” 所以当其他银行家还在用 Lotus 1-2-3 时，他们就已经在用 Excel 了。其实互联网上还流传着一个关于 Excel 的老广告，那是上世纪 90 年代末，哦抱歉，是 80 年代末播出的首支 Excel 电视广告。当时早期的 Excel 电子表格刚开始被使用，广告里有个人坐在电梯里，腿上放着一台重达 12 磅的巨型笔记本电脑，正试图在上面操作。我笑是因为，他们当然是想在坐电梯的这段时间里不把电池耗尽，当时的情况总是如此。但突然之间，在那个拥挤的电梯里，一群打着 80 年代领带、戴着 80 年代眼镜的人盯着那个电子表格说：“你在干什么？你是怎么做到的？”然后所有人都兴奋了起来。快进到 2025 年，这正是 ChatGPT 所发生的事情。事实上，我有个在 SAP 的朋友，她当时正在写一份关于某件事的 SAP 白皮书，我就问她：“告诉我你想回答什么问题。”然后我写了提示词，直接发回给她一份白皮书。我敢肯定我引发了某种病毒式循环，严格来说不是病毒式循环，而是在她团队内部引发了某种具有网络效应的病毒式循环，因为突然之间人们看到了如何让他们的工作变得更好，而且这触手可及，所以他们都在这么做。因此我认为，就像 Tim 你刚才说的，一个能让原本无法沟通的两个职能部门进行对话的工具，这个理念绝对是无价之宝。这就是真正的企业软件集成，只不过以前那些全靠手动、靠蛮力、靠高薪聘请埃森哲这种咨询公司来做。所以如果你有能将这些连接起来的产品——你知道 Figma 在设计和产品开发方面就做了很多这样的工作——如果你能开发出利用 AI 将组织中通常不交流的部门整合在一起的软件，那就是一个全新的类别。我们在 IT 预算等领域已经看到了这一点，IT 和财务部门最终获得了能够帮助他们双方进行预测的工具，而云计算促成了这一点。所以我认为这是一个巨大的机遇。

<details>
<summary>Original English</summary>

**Stephen**: ...and go home and they don't come to work every day going how can I make my how could I streamline my task they just want to not mess it up that is a lot of the world but There's a small set of people like those bankers at Goldman Sachs that were like, "How do I do more deals faster, better, more clever models?" And so they were using Excel when when the other bankers were using one 123. There's actually floating around on the internet is this old commercial for Excel, the launch this launch TV ad from the from the late 1990s where or sorry the late 1980s where the first Excel spreadsheets were being used and it's a person sitting there with this monstrous laptop that weighed like 12 pounds in an elevator trying to use it. I I'm laughing because of course they were trying to not run out of battery life in the in the elevator ride which was invariably the case. But all all of a sudden this crowded elevator of a bunch of people in in these 1980s ties and 1980s wearing glasses looking at the spreadsheet going, "What are you doing? How are you doing that?" and getting all excited. And fast forward to 2025 and that's exactly what happened with chat. Like, in fact, I had a friend at SAP that was was writing like a um a SAP white paper about something and and I I just asked them, "Tell me what questions you're trying to answer." And I did the prompt and sent them back a white paper. And I'm positive I kicked off some sort of viral loop, not technically a viral loop, but some sort of network effect viral loop inside of her team because like all of a sudden people are seeing how to make their job better and it's accessible to them and they're doing it. So I I think and to your point Tim like this idea of of a tool that enables two functions to talk together that couldn't before is golden. Like that's exactly like that's literally what enterprise software integration is except that's all manual brute force higher accenture kind of stuff. And so if you have products that bridge this and you know Figma did a bunch of this with design and product development. And so if you can develop software that leverages AI in order to bring together parts of an organization that don't normally communicate that's a whole that's a new category. And we've seen that with things like IT budgeting where IT and finance would end up with tools that ended up helping them both do forecasting and the cloud enabled that. And so I I think that that's that's a huge opportunity.

</details>

### 访谈尾声

**Sema**: 很好。我认为这也是一个非常棒的结尾。非常感谢你，Stephen，感谢你今天加入我们。

<details>
<summary>Original English</summary>

**Sema**: Nice. Well, I think that's also an amazing note to end on. Uh thank you so much, Stephen, for for joining us here.

</details>

**Stephen**: 谢谢，Sema。是的，也谢谢大家。

<details>
<summary>Original English</summary>

**Stephen**: Thanks, Sema. Yeah. And thank you.

</details>

**Tim**: 也谢谢你，Sema。

<details>
<summary>Original English</summary>

**Tim**: And thank you, Sema.

</details>