---
author: Norges Bank Investment Management
date: '2026-06-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=lbSeyzlAGLc
speaker: Norges Bank Investment Management
tags:
  - data-platform
  - ai-agent
  - software-engineering
  - cloud-computing
title: 专访 Snowflake CEO：AI 代理将重塑软件工程与企业数据架构
summary: 本期节目由挪威主权财富基金 CEO Nicolai Tangen 专访 Snowflake CEO Sridhar Ramaswamy。对话深入探讨了 Snowflake 的存储与计算分离架构、消费计费模式优势，以及 AI 代码代理如何革命性地改变软件开发。Sridhar 详细阐述了智能代理对企业运作的深远影响，同时分享了他对数据合规、早年创业经历及其个人成长路径的深刻反思。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Snowflake
products_models:
  - Snowflake Intelligence
  - Cortex Code
media_books: []
status: evergreen
---
### 简介与背景

**Nicolai Tangen**: 大家好，我是 **Nicolai Tangen**，挪威主权财富基金的首席执行官。今天和我在一起的是 **Snowflake** 的首席执行官 **Sridhar Ramaswamy**。Snowflake 基本上是世界上许多最大公司所依赖的数据平台。所以当你的银行批准贷款或者医院汇总病人数据时，Snowflake 通常是底层的引擎。Sridhar 在 **Google** 工作了 15 年，将广告业务从 15 亿美元建设到了超过 1000 亿美元。然后他离开并创办了自己的公司，两年后他成为了 Snowflake 的首席执行官。现在在 **MBIM**（挪威投资管理公司），我们是 Snowflake 的投资者，同时我们也是该产品的大客户。我们在 Snowflake 中拥有 2 PB 的数据，相当于 200 万千兆字节，我们每天对数据库大约进行 300 万次查询。所以热烈欢迎 Sridhar。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Hi everyone, I'm Nicolola Tangan, the CEO of the Norwegian Sovereign Wealth Fund and today I'm joined by Shria Ramaswami, the CEO of Snowflake. Snowflake is basically the data platform that many of the world's biggest companies run on. So when your bank approves a loan or when a hospital pulls together patient data, Snowflake is often the engine underneath. Shrida spent 15 years at Google where he built the advertising business from one and a half billion to over hundred billion dollars. Then he walked away to start his own company and two years later he became the CEO of Snowflake. Now here at MBIM we are investors in Snowflake and we are also big users of the product. We have two pabytes of data in Snowflake which is the equivalent of 2 million gigabytes and we have roughly 3 million queries into the database every day. So big welcome Shrar.

</details>

**Sridhar Ramaswamy**: 谢谢你，Nicolai。很高兴来到这里，对这次对话充满期待。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Thank you Nikolai. Happy to be here. excited for the conversation.

</details>

### 定义 Snowflake：云时代的分析型数据平台

**Nicolai Tangen**: 首先，简而言之，你会如何向从未听说过 Snowflake 的人描述它？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: First of all, um, how would you describe Snowflake to somebody who's never heard of it in brief?

</details>

**Sridhar Ramaswamy**: 是的，我们是一个数据平台。我们就像一个云计算平台，比如 **AWS**，但我们强烈专注于数据。我们帮助你完成一切，从不同系统中引入数据，分析它，从中获取洞察，然后将其带到你采取行动的系统中。所以，我们是一个分析型数据平台。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yeah, we are we are a data platform. We are like a cloud computing platform like an AWS, but with a strong focus on data. We help you do everything from bring in data from various different systems, analyze it, get insights from it, um, and then, uh, take it to the systems where you take action. So, we are an analytic data platform.

</details>

**Nicolai Tangen**: 谁是你们的客户？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Who are your clients?

</details>

**Sridhar Ramaswamy**: 天哪。全球 2000 强公司中一半我们可触达的企业——也就是非中国公司——都是我们的客户。在金融服务、医疗保健、广告等行业有成百上千的客户，这个名单还可以一直列下去。我们在超过 25 个国家运营，拥有客户的国家远不止这些。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Gosh. Uh half the uh global 2000 companies that are addressable uh that is non-China companies are our customers u hundreds and hundreds of uh customers in financial services uh healthcare advertising uh industries the list goes on and on and uh we are uh we operate out of more than 25 countries and have customers in way more than those.

</details>

### 计算与存储分离的激进架构

**Nicolai Tangen**: 当公司在 2012 年成立时，将存储从计算中分离出来是相当激进的，对吧？跟我们说说这个。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: when when the company was founded in uh 2012 uh to separate storage from compute was was pretty radical, right? Just tell us about it.

</details>

**Sridhar Ramaswamy**: 理解这个非常重要概念的最简单方法，就是想想你和我以前是如何购买或使用电脑的。我告诉人们，在过去的 50 年里，每当你我或者我们的公司需要计算能力时，我们都会去买一个“盒子”。那个盒子里有固定容量的存储，固定数量的计算能力，和固定大小的内存。而且你通常要和这个盒子绑定——我不知道，大约 5 年吧。所以，如果你决定你需要更多的内存，很遗憾，你只能等。如果你决定你买的计算能力太多，CPU 算力过剩，那也没办法。你已经买了这台机器了。这就是它的本质。顺便说一句，你的手机也是另一个盒子，只是一个更小的盒子而已。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: The simplest way to internalize that really important concept is to think about how you and I have always bought or used computers. I tell people for the past 50 years um whenever you and I wanted computing or our company we would go buy a box and that box would have a fixed amount of storage a fixed amount of compute and a fixed amount of memory and you're generally stuck with that box for I don't know 5 years. So if you decided that you wanted more memory uh well too bad you wait. If you decided that you bought too much compute, too much CPU power, well that's too bad. You already bought the machine. And so that's at the essence of it. By the way, your phone is another box, just a littleer box. 

</details>

**Sridhar Ramaswamy**: 因此，将数据从一个盒子转移到另一个盒子也非常困难。那曾经是一个集成项目。Snowflake 将一切彻底变革，它建立在云计算之上，这些云计算平台实际上是无限大的数据库，拥有惊人的计算量，可以在那里运营的不同客户之间共享。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: And so, and it was also really hard to move data from one box to another. That was an integration project. Snowflake radicalized things uh by sitting on top of cloud computing, which effectively are infinitely large databases with amazing amounts of compute that can be shared um between different customers that operate there. 

</details>

**Sridhar Ramaswamy**: 我们将计算和存储分离了出来。所以我们说，你可以精确使用你想要的存储量，以及你想要的计算量。如果你想进行像深度分析这样的工作——因为你们 MBIM 内部有人提出了一个非常棒的投资想法，需要你翻阅每一条历史信息——你可以在一个周末启动 1000 台电脑进行分析，然后将它们关闭，接着弄清楚如何在实践中实施。这就是 Snowflake 模式的魔力。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: And we separated out compute and storage. So we said you can use exactly the amount of storage that you want and the compute that you want if you want to do like a deep analytic job because one of the people within uh um NBIM came up with like this brilliant idea for investing that required you to go through every piece of historical information. You can spin up a thousand computers over one weekend do the analysis shut them down and then figure out how to implement that in practice. That's the magic of Snowflake's model.

</details>

### 消费计费模式：对齐价值创造

**Nicolai Tangen**: 大多数软件公司按座位（按人头）收费，但你们根据人们实际消耗的资源来收费。为什么？为什么这更好？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Most software companies charge per seat but you charge for what people actually consume. Why? Why is that better?

</details>

**Sridhar Ramaswamy**: 因为这与价值创造是对齐的。我们拥有的部分优势在于，我们非常善于预测需求，因为我们有超过 13000 个客户。所以我们能够自行摊销激增的需求，并为你提供一个更稳定的模式，不要求你承诺必须持续使用一定数量的存储或一定数量的 CPU。这反过来意味着，你只在需要时才启动资源。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Because it is aligned value creation. Part of the benefit that uh we have is um we are very good at predicting demand because we have over 13,000 customers and uh so we are able to amatize spiky demand ourselves uh and offer you a more stable model that does not require you to make a commitment that you're going to use a certain amount of storage or a certain number of CPUs on an ongoing basis. And uh this in turn means that you spin up things as you need them. 

</details>

**Sridhar Ramaswamy**: 大多数分析任务往往是突发性的。如你所知，即使是事务性工作中的日夜变化也是非常大的。人们在夜间做的银行业务交易就是没那么多，所以存在所有这些众所周知的模式。我们能通过消费模式提供极其划算的价格，因为我们能够将其摊销。这也使得公司在价值上高度一致。你为你所用的买单——我们只在你们团队使用 Snowflake 时才确认收入。而且，当我们谈到 AI 时代时，这会是一件大事，因为你只需为你所用的内容买单。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Most analytic jobs tend to be bursty and as you know the dayight variations even in transactional jobs is very high. People just are not doing as many banking transactions in the night and so there are all of these well-known patterns. Uh what we are able to do with a consumption model is offer an incredibly effective price because we are able to amortize that and it also makes the company super value aligned. You pay for we recognize revenue when you and your team use Snowflake and uh we'll come to this in the world of AI that's a big deal because you only pay for what you use.

</details>

### AI 代理与软件工程的革命

**Nicolai Tangen**: 绝对的。Sridhar，你现在为什么把像 **Anthropic** 这样的公司视为你们的竞争对手？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Absolutely. Trina, why do you now consider uh the likes of Entropic and so on your competitors?

</details>

**Sridhar Ramaswamy**: 因为他们正在改变我们所知的软件。我认为，对于我们许多在软件行业深耕的人来说，非常非常清楚的一点是：软件的成本经济学正在发生戏剧性的变化。我会将此与近期关于 AI 模型成本等担忧明确区分开来。现实是，在过去的 50 年里，软件一直有点像一门手艺。有特殊技能的人们做着惊人的工作量来生产软件。它很难构建，很难集成。你应该这样想：最好的程序员就像音乐会钢琴家。你没办法批量生产他们。这是因为你在那个领域花了一万个小时，你脑子里有那种特殊的天才，这就是你成为一名出色音乐家的方式。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Because they're changing software as we know it. I think what is uh very very clear uh to many of us working deeply in the software industry is that the cost economics of software are dramatically changing. And uh I would separate that out clearly from near-term concerns about costs of AI models and things like that. The reality is that software has always been a little bit of a craft for the past 50 years. Special people that are doing incredible amounts of work in order to produce software. Hard to build, hard to integrate. Um you should think of these like the best programmers are like concert pianists. There's no way to mint them. It's you spend the 10,000 hours and you have that special genius in your head and that's how you become an amazing musician. 

</details>

**Sridhar Ramaswamy**: 软件工程师以前就是那样的。但这些模型在软件领域所代表的，是以我们从未见过的规模实现的软件工业化。那是我将提供模型的公司、它们创造的代码代理视为我们最大竞争对手的主要原因。这也是为什么我们有自己的代码代理。它们越来越多地代表了所有人通往计算系统的前门，通往所有信息的前门。它从软件工程师开始，但还会延伸到更多人群。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Software engineers have been like that. But what these models represent with software is the industrialization of software at a scale that we have not seen before. And u that is the primary reason why I consider um the model companies things like the coding agents that they are creating um to be our uh biggest competition. This is the reason why we have a coding agent. They represent the front door to computing, the front door to all information more and more for everybody. Starts with software engineers, but it goes to more.

</details>

**Nicolai Tangen**: 完全同意。那像 **亚马逊** 和 **微软** 呢？他们也有竞争产品。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Absolutely. What about the likes of Amazon and Microsoft who also have competing products?

</details>

**Sridhar Ramaswamy**: 是的，对他们保持充分尊重的前提下，当涉及到纯粹的数据平台时，我们一直在排行榜上名列前茅。那些在这个规模运营的公司绝不应该被低估，因为它们能够调动难以置信的资源来解决问题。但从我观察到的来看，我认为代码代理才是所有软件面临的最大威胁。弄清楚 Snowflake 如何在这个世界上生存并蓬勃发展，是我面临的第一大挑战。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yeah. You know, with all due respect to them um when it comes to pure data platforms, we have always been top of the charts when it comes to that. uh companies that operate at that scale should never be underestimated because they are able to bring on just incredible resources to solve problems. Uh but from what I see, I think of uh coding agents as the biggest threat to all software and uh figuring out a path for snowflake that is going to survive and thrive in this world is my number one challenge. 

</details>

### Snowflake 如何从 AI 革命中受益

**Nicolai Tangen**: 嗯……继续谈谈 AI，你们是从这场革命中如何获益的？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: M m um continuing on on AI um in what ways are you benefiting from um from this revolution?

</details>

**Sridhar Ramaswamy**: 在涉及 AI 和像 Snowflake 这样的软件公司时，我采取了一种还原论（reductive）的方法。你知道，在我们的核心，我们做两件事。我们创建并运行伟大的软件。这是我的工程团队所做的。然后，我们销售并帮助像你们这样的客户实施我们的软件。所以，我们的大部分精力都集中在：我们如何让这一切变得更快。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I take a reductive uh approach when it comes to AI and uh a software company like Snowflake. You know, at our core, we do two things. We create and run great software. This is what my engineering team does. We sell and help customers um like you implement our software. So, a lot of our energy is focused very much on how do we make this go faster.

</details>

**Sridhar Ramaswamy**: 在销售端，我们的销售人员现在拥有的工具能让他们即时获取信息。这就像是一个坐在他们手机里的销售代理。我们的解决方案工程师可以在 30 分钟内为 Nicolai 制作一个定制的演示，里面的数据看起来就像是来自你的银行一样。他们使用这些工具、为你带来结果的能力是令人难以置信的。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: On the sales side, our uh sellers now have tools that give them instant access to information. It's a sales agent that sits in their phone. Our solution engineers can do a custom demo for Nicola in 30 minutes that has data that will look like it came from your bank. Their ability to use these tools, drive outcomes for you is incredible. 

</details>

**Sridhar Ramaswamy**: 然后在软件工程端，编程正在被彻底革命化。我刚从一个会议出来，我们正在讨论如何让更多的人进入“基于规范驱动的代码开发（specdriven coding development）”。也就是说，你用英语写下一份规范，说明你想要生产什么，然后你将编写第一版代码、测试它、部署它等等的整个剩余过程自动化。所以软件工程已经完全不同于两年前的样子了。如何让团队里的每个工程师都像那样行事，去内化这些巨大的可能性，是我们面临的最大挑战。但我们也有超级明星，这些人的生产力比普通软件工程师高出 50 到 100 倍。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: And then on the software engineering side, coding is being revolutionized. Um I just came from a meeting where we are talking about how we need to get more people into specdriven coding development. Um which is you write an English language spec for what it is that you want to produce and then you automate the entire rest of the process of writing the first version of the code and testing it and deploying it and uh and so on. And so software engineer is software engineering is nothing like what it was two years ago. How to get every engineer in your team to act like that to internalize these great possibilities is the biggest challenge that we have. But we have the superstars, people that are 50, 100 times more productive than the average software institute.

</details>

### AI 时代的智能代理接口与 MCP 协议

**Nicolai Tangen**: 大型企业现在如何借助 AI 来改变他们的数据状态？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: How do large enterprises now change uh the data states on the back of AI?

</details>

**Sridhar Ramaswamy**: 两件事。首先，AI 让你们拥有的数据变得更加容易访问。这就是像 **Snowflake Intelligence** 这样的产品所做的。它大致上是一个连接你数据的代理式接口（agentic interface）。在里面你可以问：“我最大的几笔投资目前表现如何？这笔投资似乎下跌了一点。帮我拆解分析一下。是因为板块原因？还是其他问题？”所有那些过去需要分析师代你执行的问题，现在触手可及。这也意味着，未来工作应该如何完成，将会因为这种对数据几乎“即时的可编程访问”而发生戏剧性的改变。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: So two things first of all AI makes the data that you have a lot more accessible. This is what products like snowflake intelligence do. It is roughly an agentic interface to your data where you can say how are my biggest investments doing? This investment seems to have gone down a little bit. Break it down for me. Um is it because of the sector? Is it some other problem? All of those questions that required analysts to perform on your behalf right now at your fingertips. And what this also means that how work should be done in the future is also going to get dramatically changed because of this fast programmable access almost to the data. M

</details>

**Sridhar Ramaswamy**: 我们许多客户受益的第二个方面是因为像原生代码代理这样的东西。我很少有机会去找我的客户，告诉他们：“我可以让你每天必做的一件事提速 10 倍或 20 倍。”那是我们在内部团队正在做的事，并且那是我们带给他们的价值。所以对于一家公司内数据的建设者和消费者来说，都从 AI 中获得了巨大的好处。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: the second way in which a lot of our customers are benefiting is because of things like native coding agents. Uh it's not often that I go to my customer and say I can make something that you have to do every day go 10 times or 20 times faster. That's where you what we are doing with internal teams and that's the value that we take to them. So both the builders and the consumers of data within a company have massive benefits thanks to AI. 

</details>

**Nicolai Tangen**: 现在我们有一种叫做 **MCP** 的东西，将我们与你们连接起来。你能不能向听众简短解释一下，什么是 MCP？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Now we have something called an MCP which connects us to you guys. Could you just explain in short to the listeners what an what an MCP is?

</details>

**Sridhar Ramaswamy**: 是的，你应该大致将其理解为“模型控制协议（model control protocol）”。它仅仅是一种让语言模型或代码代理能够与数据源对话的方式。我们希望我们的客户使用的是，像 Snowflake Intelligence 这样原生暴露数据的产品，但我们也同样致力于可互操作性，去适配你们已有的东西。因此，在 Snowflake 中创建的每一个代理，都可以被你们拥有的某个前端远程调用。那就是 MCP，它是一个互操作性层。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yeah, you should roughly think of that as uh it stands for model control protocol. It is just a way for uh a language model or a coding agent to be able to talk to a data source. And um what we like our customers to do is use our products like Snowflake intelligence that natively expose the data but we're also all about being interoperable working with the things that uh you folks have. So every agent that is created in Snowflake can be called remotely from some front door that um you know that you have and that's what MCP is. It is an interoperability layer.

</details>

### 重新定义工作：抽象层面的计算

**Nicolai Tangen**: 代理将如何改变人们工作的方式？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: How will agents uh change the way you work? 

</details>

**Sridhar Ramaswamy**: 这是一个很大的问题，而且“代理”这个词本身就有一点点被误解了。你应该这样理解代理：它是一个模型和一段代码，它可以访问底层各种不同类型的工具，而且它知道如何智能地调用它们。比如，如果你问它一个问题并说：“给我写个小程序”，它知道如何创建一个文件，往里面写些代码，然后在本地调用某些东西来执行那段代码。但完全相同的事情也可以被使用，如果你说：“我想知道我的投资组合表现如何。”它知道如何调用投资组合工具，分析它，并把结果反馈给你。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: This is a big question and the word agents themselves itself is a little bit uh misunderstood. Uh the way you should think about agents is um it is a model and a piece of code that has access to different kinds of uh tools underneath and um it knows how to call them smartly. So for example, if you ask it a question and say write a little program for me, um it knows how to create a file, write some code into it and then call something locally to execute that piece of code. But exactly the same thing can be used if you say I want to know how my portfolio is doing. It knows how to call the portfolio tool, analyze it and give you back the result.

</details>

**Sridhar Ramaswamy**: 所以代理正在改变每一个层级的工作。尽管你往往听到最多的可能是诸如代码代理这类事物，但这个总概念是非常强大的。这些代码代理实际上就是“抽象代理（abstraction agents）”。因此，即使是一个永远都不想写一行代码的人，也将从它们身上获得巨大的收益。其核心功能是可以访问你的所有文档、访问存储在 Snowflake 里的结构化数据。比如，如果我赋予 Snowflake Intelligence 访问所有数据的权限，那么你几乎可以对数据提出任何问题，代理解会制定一个计划并帮助你执行。这就是为什么人们对如工作理念、云共事（cloud co-work）或 Snow-work 这类东西如此兴奋，因为它们改变了人们对工作的思考方式。一切都是可编程的，而且一切也是相互连接的。如果你想基于你做的一项分析发送一封电子邮件，你不需要去复制粘贴。你只需告诉你的代理：“请将这封邮件发给 Stefan。”，邮件就发出去了。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: And so agents are changing work at every level. Even though you tend to hear most about things like coding agents, but the general concept is very powerful. These coding agents are effectively abstraction agents. So even somebody that never wants to write a line of code is going to benefit enormously from having their basic functionality, access to all of your documents, access to the structured data that is in Snowflake. If I give you for example Snowflake Intelligence access to all of it, practically any question that you would want to ask of the data, the agent can come up with a plan and help you execute. That's why there's so much excitement about things like the work concept, cloud co-work, or snowwork because they're changing how people think about work. Everything is programmable and also everything is interconnected. If you want to send an email based on an analysis you did, you don't have to cut and paste. You can just tell your agent, please send this email to Stefan and out goes the email.

</details>

### 数据迁移与现代化：突破历史债务

**Nicolai Tangen**: 说得太对了。现在，我告诉你一件事。我们花了好几年时间来清理我们的数据，那不是一份……那不是一份好玩的差事。现在当你审视数据时，它杂乱无章，充满重复，存在缺漏，是几十年的旧系统拼凑在一起的。这就构成了对 AI 采纳以及你们产品使用的巨大障碍，对吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Absolutely. Now, uh I'll tell you one thing. We spent years cleaning up our data and it's not uh it's not a fun job. Um now when you look at data, it's messy, duplicates, gaps, decades of legacy systems stitched together. Just what kind of barrier is that to the usage of AI and to the usage of your product?

</details>

**Sridhar Ramaswamy**: 过去，这曾经是从数据中获取价值的巨大障碍。我认为现在这正日益变得简单。这就是将代码代理应用于数据问题本身的魔力所在。过去，如果你只是想为了给一个复杂数据集添加额外一列信息而修改一个数据管道系统，那对于某个可怜的程序员来说，轻轻松松就是一个星期的工作，他必须得在所有繁琐的细节里苦干。我们现在有了“技能（skills）”这样的东西，你可以把它们看作是英语语言程序，它们自动化了从头到尾的整个流程，所以他们可以启动它，然后一小时后回来，确认一切都已经被处理妥当了。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Used to be a huge barrier to getting value from data. I think it is getting simpler by the day. That's the magic of uh coding agents applied to the data problem itself. Used to be that changing a pipeline um for just adding one additional column of information in a complex data set that would easily be a week-long job for some poor programmer that had to toile through all of the details. We now have uh things like skills which you can think of as English language programs that automate that entire process from start to finish so that they can start it and they can come back in an hour and just ensure that everything has been taken care of. 

</details>

**Sridhar Ramaswamy**: 我们正在开发诸如“由代理驱动的迁移（agent-driven migrations）”功能，让你能在几天和极少数几周内，将数据从旧系统迁移到 Snowflake 上，而过去这需要好几个季度甚至好几年的时间。AI 在整体的数据现代化旅程中可以变得非常非常强大，而这是我们投入巨资的一个领域。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: We are working on things like agent-driven migrations where you can move data from legacy systems onto snowflake in a matter of days and small number of weeks as opposed to the multiple quarters in the multiple years that it used to take and u AI can be very very powerful in the data modernization uh journey overall and it's an area that we are very heavily invested into. 

</details>

### 数据合规：GDPR 的意想不到的后果

**Nicolai Tangen**: 真希望我们五年前就有它，不过……嘿，那关于 **GDPR** 呢？它是如何阻碍这种使用的？也就是说，个人数据保护法。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: I wish we had it five years ago, but uh hey um what about uh what about GDPR? How is that uh holding back usage i.e. the personal data protection laws?

</details>

**Sridhar Ramaswamy**: 嗯，Snowflake 的部分优势正是我们提供了出色的治理功能。对于公司而言，确保他们合规是一种负担。你知道，我是美国人，每个人都在批评 GDPR，并且它确实带来了一些意外的后果。但 GDPR 的许多方面实际上也非常具有前瞻性。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Well, part of Snowflake's benefit is that we offer excellent governance features. It is a burden for uh companies to make sure that uh they comply. You know, I'm American and uh everyone criticizes GDPR um and it has had some unintended consequences. Uh but there are also many aspects of GDPR that were genuinely forward-looking.

</details>

**Nicolai Tangen**: GDPR 对欧洲来说是好是坏？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Is GDPR good or bad for Europe?

</details>

**Sridhar Ramaswamy**: 我认为它是喜忧参半的。我认为它带来了许多意外的后果，它也告诉你，在监管层面，它需要非常精准地实施。人们真的需要仔细思考：那些意想不到的负面后果是什么？

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I think it's a very mixed bag. I think it had a lot of unintended consequences and it al it also tells you how regulation needs to be very surgical about uh what it does and people really need to think very hard. What are the unintended negative consequences?

</details>

**Sridhar Ramaswamy**: 是的，我先跟你说积极的方面。你作为一名消费者，可以找到一家公司并说：“你们需要删除你们所掌握的关于我的一切信息。”——这是作为 GDPR 结果出现的。这是一个巨大的积极点。它迫使每家公司采取行动。它迫使我的 Google Ads 团队确保我们实际上能够追查到我们所知道的关于 Nicolai 的所有信息。我认为这是一个巨大的积极意义。但另一方面，在这个节骨眼上，面对那漫天弹窗的提示墙，你干脆放弃了，然后点了“同意”。我认为那是一个意外后果。我认为它提高了每家欧洲公司做生意的成本，而最终从 GDPR 中受益的人是那些巨头，他们有能力花钱，遵守所有的规则并做到合规。然而，每一个在欧洲涌现的新公司，从一开始就必须努力挣扎以遵守所有这些规则。这就是我所说的意料之外的后果。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yeah, I I'll I'll tell you the positive things first. The fact that you as a consumer can go to a company and say you need to delete everything that you know about me >> that came as a result of GDPR. That is a huge positive. It forced every company. It forced my Google Ads team to make sure that we were actually able to track down everything that we knew about Nicola. I think that's a huge positive. On the other hand, those walls of uh prompts that you have to at this point you just give up and say yes. I think that's an unintended consequence. I think it has raised the cost of doing business for every European company and the people that ultimately benefited from GDPR were the giants who are able to spend the money, follow all the all the rules and be compliant while every new company that comes up in Europe has to struggle to follow all of these rules right out of the gate. That's what I mean by unintended consequences.

</details>

**Nicolai Tangen**: 一个不相关的问题，我们会在太空中建立数据中心吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Unrelated question, will we have data centers in space?

</details>

**Sridhar Ramaswamy**: 嗯，我完全没有资格回答这个问题。这笔账算起来……你看，这笔账算起来真的非常、非常令人生畏。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Um, I'm simply not qualified to answer that. uh uh the maths look the math looks really really formidable. So

</details>

**Nicolai Tangen**: 那么量子计算能为 Snowflake 解锁什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: what will uh quantum computing uh unlock for snowflake?

</details>

**Sridhar Ramaswamy**: 这是一个很棒的问题。我认为，首先，类似于伟大的 AI 模型，量子计算是一个巨大的安全风险，确保你们的数据安全是我们的首要任务。它承诺在如何思考优化和搜索等问题上带来非常新颖且截然不同的方法，我们对能够利用这些东西充满信心。我认为核心的基础设施在量子计算的世界里，仍将继续具有极大的相关性。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: This is a great question. I think uh being things like uh first of all quantum computing computing similar to great AI models is a great security risk and making sure that your data is safe is a high priority for us. It uh promises to bring very new and different approaches about how you think about things like optimization and searching and uh we are confident about being able to use those things. I think core infrastructure will still continue to be super relevant in the world of quantum computing.

</details>

### 从 Google 到创业失败的反思

**Nicolai Tangen**: 我们能花点时间聊聊你的早年经历吗？你知道的，你仍然是个非常年轻的男人，但当你更年轻的时候，在离开 Google 之后，你创办了 Neeva。你从那次失败中学到了什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Can we spend a bit of time on your uh earlier years? You know, uh you're still a very young man, but when you were even younger, you after Google started up uh NEA, what did you learn uh from that failure? 

</details>

**Sridhar Ramaswamy**: 我的内心深处有一部分人是极度理想主义的，对我希望能看到的世界充满了浪漫的幻想。我认为那是一种积极的特质，Neeva 正是出于“创造一个更好的搜索引擎将会是一项伟大事业”这种真诚的信念而创办的。在众多你学到的艰难教训中，其中一条就是：特别是消费者级产品，如果没有大幅超越过去的体验，就得不到大规模的普及。在某一层面上，我知道搜索可以做得更好，但我并没有一个具体的计划，来说明我对搜索和信息的愿景到底怎样才能好上 10 倍甚至 100 倍。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I mean there's a there is a part of me that is uh deeply idealistic and deeply romantic about the world that I would like to see. I consider that a positive >> and uh Neva was uh started out of this sincere belief that creating a better search engine was going to be a great business. Among the tough lessons that uh you learn is um consumer products especially do not get adopted without a without an experience that is dramatically better. At one level I knew that search could be better but I did not have a concrete plan for how my view of search and information could be 10 times 100 times better. 

</details>

**Sridhar Ramaswamy**: 最终，那导致了它的失败，因为我们做出了一个仅仅是“稍微好一点”、拥有更好隐私保护的搜索引擎。当然，你经历了惨痛的教训才明白：隐私就像锻炼一样，是一种我们喜欢口头支持其理念，却不愿付诸实践的品质。那些都是严酷的教训，但我们在团队里拥有了惊艳的人才。我们开发了令人惊叹的技术，并且它最终成为了 AI 在 Snowflake 得以生根发芽的技术基础。所以其中确实结出了伟大的果实。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Ultimately, that's what led to its failure because we came up with a search engine that was marginally better, that had better privacy. Of course, you learned the hard way that uh privacy like exercise is a quality that we like subscribing to rather than actually practicing >> and u you know those were tough lessons but we had amazing folks in the team. We built amazing technology and it eventually ended up being the underpinnings of what AI became at Snowflake. So something great came out of it.

</details>

**Nicolai Tangen**: 是的。我非常喜欢这些经历最终转化为学习过程的方式。在美国、在欧洲，那种情况并没有被视为学习，你知道的。所以那很好。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Yeah. I love the way that these type of things are learning learning experiences in the US in Europe. Uh that's not the way they are considered, you know. So uh uh so good. 

</details>

### 接任 CEO：应对逆境与组织扁平化

**Nicolai Tangen**: 之后你加入了 Snowflake。你被任命为首席执行官。股价当时可不太喜欢那个决定。刚开始的时候是怎样的？跟我说说在 Snowflake 初期的那段日子。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Now then you went into Snowflake. Uh you were named uh CEO. Um the share price didn't particularly like it. Just how did you tell me about the first the first period in Snowflake?

</details>

**Sridhar Ramaswamy**: 是的，我想我是在一个对 Snowflake 来说非常关键的转折点成为 CEO 的——那时增长实际上正在放缓。事实上，我担任 CEO 的第一天，我们对接下来一年的预期指引，就比市场共识低了整整五个百分点。那才是股价暴跌的真正原因。当然，一个从未担任过 CEO 的无名之辈，从传奇人物 Frank Slootman 手中接过接力棒，这也于事无补。应对逆境在我看来，正是成就伟大的真正标志，我们就直接投入了工作。我相信这家公司。我在公司里已经待了 6 个月也有帮助，我们重新把焦点放回了打造伟大的产品上。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yeah, I think um there I became CEO at uh a pretty critical juncture for uh Snowflake when growth was actually slowing down. The day I became CEO, in fact, we guided five full percentage points below consensus for the year uh for the upcoming year. That was the u real reason for the dramatic drop. Of course, it does not help that an unknown person that has never been CEO before was taking over from the legendary Frank Slutman. These uh dealing with adversity in my mind is the true mark of uh greatness and uh we just set about going to work. I believed in the company. It helped that I had been in the company for 6 months and uh we focused back on creating great products. 

</details>

**Sridhar Ramaswamy**: 那最终才是造成差异的原因。每个人都在谈论其他一切，但归根结底，如果你身处软件行业，生活根本上就是：你是否在创造人们喜爱的产品？这种对创造价值的纯粹专注推动了我们，这也是我们如何开发出像 Cortex Code 这样产品的方式。你可以稍微搜索一下，就会看到大家对这个产品有多么兴奋和喜爱。这就是所有软件工程师为之生存和梦想的东西，这才是为公司创造价值的源泉。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: That ultimately is what makes the difference. Everybody talks about everything else but at the end of the day if you are in software life is fundamentally about are you creating products that people love >> and that singular focus on creating value is what has propelled us and uh this is how we have created products like cortex code. Um you can do a little bit of a search and you will see how much excitement and love there is about the product. This is what all software engineers live and dream for and that's what creates value for the company.

</details>

**Nicolai Tangen**: 软件工程师有哪些共同点？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What do software engineers have in common? 

</details>

**Sridhar Ramaswamy**: 我会说，以前在“前 AI 时代（pre-AI era）”，软件工程结合了两种能力：一种是在高层架构上思考你想如何解决问题，再结合一种几乎是狂热的打磨细节的能力。你需要能同时兼顾两者。这是一门非常无情的学科。你在某个地方漏掉了一个逗号，编译器可不会跟你说：“嘿，这只是个逗号，我帮你补上”。它是这样反馈的：“这是一个你必须解决的错误”。我认为 AI 正在让事情变得非常不同。我认为现代由 AI 驱动的软件工程师在概念层面上会更加抽象。他们实际上是在管理一个代理团队（team of agents）。他们在判断应该解决什么问题，以及评估“解决这些问题对于公司和正在构建的产品的语境中是否有意义”的过程中，锻炼自己的品位和判断力。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I would say previously in the pre-I era, software engineering combines the ability to think at a high level about how you want to solve a problem combined with almost this fanatical ability to drive the details. You need to be able to do both at the same time. It is a remarkably unforgiving discipline. You miss one comma somewhere, the compiler would not tell you, hey, that's just a comma, I'll add it for you. It's like that's an error that you had to deal with. I think AI is making things very different. I think the modern AIdriven software engineer is much more conceptual. They are actually managing a team of agents. They are exercising taste and judgment about what problems to solve and how solving these problems makes cont you know makes sense in the context of the company and the product that you're creating. 

</details>

**Sridhar Ramaswamy**: 这些人正在迅速弄清楚，如何使用最新、最好的工具来解决问题。这种学科要求每天、每周都在发生戏剧性的变化，它将在一年后变成完全不同的样子。我给你举个具体的例子。我的小儿子 24 岁。他三四年前从一所很好的大学毕业，获得了软件工程师学位。他曾非常自豪于自己是一名真正的系统程序员，深谙系统底层设计，能设计出三、四、五毫秒延迟的流媒体系统。那是他的专长。而现在，他在一家 AI 实验室工作。他最近对我说：“爸，为了在我现在的工作里取得成功，我在学校以及之后学到的所有东西都彻底没用了。我基本上不得不再学一套全新的东西。”这就告诉你事物变化的幅度有多大。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: These are the people that are quickly figuring out how to use the latest and greatest tools in order to solve a problem. That discipline is dramatically changing um by the day, by the week, and it's going to be completely different a year from now. I'll give you a specific example. My younger son is uh 24 years old. He graduated 3 four years ago as a software engineer from a really good university. And he was very proud of being a systems programmer that really knew the details designing uh streaming systems with three, four, five millisecond latencies. That was his specialty. And now he works for one of the AI labs. And uh he told me recently, "Dad, everything I learned in school and after that is completely useless to succeed in my current job. I've had to learn basically new things." That tells you how much things are changing.

</details>

**Nicolai Tangen**: 那真是不可思议。太不可思议了。在 Snowflake，你们有一个被称为“每周作战室（weekly war room）”的东西。那是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: That's incredible. That's incredible. Um at Snowflake, you have something called the weekly war room. What is that?

</details>

**Sridhar Ramaswamy**: 是的，这是我们在早期就实施的一个概念。Snowflake 以前专业化分工很严重。我的意思是，在产品被创造出来，一直到你们这些客户能实际使用它之间的每一个环节，都已经演变成它自己专精的学科了。所以你有软件工程师、有产品经理、有设计师、有产品营销经理、还有技术项目经理。这个垂直的堆栈越来越高。当你拥有一个完美的产品，而且你只是想在将软件交付给你的每一个层面上优化规模时，这一切运转得很好。但当事物正发生剧烈变化时，这就行不通了。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yeah, this is a concept that we put into place early on. Snowflake um you know, had specialized a lot. What I mean by that is um every function in between when a product is created to when you the customer can actually use it had evolved into its own specialized discipline. Um so you have software engineers, you have product managers, you have designers, uh you have product marketing managers, you have technical program managers. This stack keeps going up and up and up. All of this works fine when you have a perfect product and all you're trying is optimizing scale at every level of delivering that software to you. It does not work when things are changing dramatically. 

</details>

**Sridhar Ramaswamy**: 当你想要创造一个新产品时，你基本上需要在创造者和使用者之间拥有一个更紧密的反馈循环。我们需要每天、每周跟你们的团队交流。我们需要在 Slack 频道上，因为我们需要弄清楚事情。老实说，这就是“作战室”的作用。它们把所有为一个新领域负责的人召集在一个地方。我会参与其中，我们会讨论我们是怎么取得进展的。正如你在管理中所了解的那样，这是一种缩短沟通回路的方法。你要么选择横向组织，要么选择纵向组织，而且这每种方式都有优缺点。这其实是一个将虚拟团队重新在纵向上整合（vertically）以推动产出的例子。直到今天我还在这么做，我有很多这样的作战室，我们在周一做计划，而在 AI 这个领域，我希望在周五就看到结果。那就是我们自身也在演进和变化的高速节奏。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: When you want to create a new product, you basically want to have a much tighter feedback loop between who is creating and who is using. We need to talk to your team every day, every week. We need to be on Slack channels because we need to figure things out. Honestly, that's what the war rooms did. They brought everybody that was responsible for a new area together into one place. I would participate in them and we would talk about how we made progress. This week is a way to short circuit communication. As you know in management um you can either organize horizontally or you can organize vertically and there are pros and cons of each of these things. This was an example of reorganizing virtually but vertically to drive outcomes. I do these even today I have a number of war rooms where we plan on Monday and in the world of AI I want to see results on Friday and that's the rapid speed at which we ourselves are evolving and changing even today

</details>

**Nicolai Tangen**: 你称自己为一台“电子邮件机器”。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: you call yourself an email machine

</details>

**Sridhar Ramaswamy**: 我靠处理电子邮件谋生。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I process email for a living

</details>

**Nicolai Tangen**: 我也是。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: so do I

</details>

**Sridhar Ramaswamy**: 但这全是关于信息的获取。我把管理看作是……通常像生活一样，我喜欢努力工作。我喜欢既能深入细节，也能阐明更高层面的原则，或是帮助团队达成关键决定。所以我消化大量的信息。所有这一切都是为了建立语境（context），建立直觉（intuition），好让你能够做出一年一两次或三次，会对公司产生深远影响的决定。所以我把 CEO 的角色看作是，对于正在发生的事情获取广度和深度上的认知，并帮助推动这些产出落地。顺便说一下，我不认为我应该是那个必须提出新想法，想出点子或者做决定的人。这是关于确保你搭建了一个能让最好想法涌现的环境，而你只是协助者（facilitator）。当你对团队说：“是的，我们应该朝着那个方向走，我们真该发布 Cortex Code 这个代码代理，因为那将确保我们的未来。”时，你代表着团队做出了判断。这一切都是关于支持这个团队。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: but it's all about information you know I look at uh I look at management as um I like generally life I like working hard. I like uh both being in the detail but also being able to articulate the higher principles or uh help uh teams reach critical decisions. So I consume a lot of information. Um all of this is towards building context is about building intuition so that you can make the one or two or three decisions per year that are going to have a profound influence on your company. And so I think of a CEO's role as getting that breadth and depth in what is going on and helping drive like those outcomes. By the way, I don't think I'm the one that needs to be um driving the new ideas or coming up with new ideas or deciding. It is about making sure that you set up an environment in which the best ideas come up and you are the facilitator. You're the face of the team when you say yes, we should go in that direction. we should actually launch cortex code a coding agent because that is going to ensure our future um it's all about supporting the team.

</details>

### 公司文化与个人准则

**Nicolai Tangen**: 公司文化最核心的部分是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What are the most important part of the copa culture? 

</details>

**Sridhar Ramaswamy**: 我认为在最重要的事情里，你需要……我是说，首先让我从基准线说起。像讲究文明礼貌，像互相尊重，像机会平等这样的东西。这些是任何一家公司的基准线。至少对于任何我参与其中的公司而言，我绝对不接受任何不符合这些要求、发生在我公司内部任何一个人身上的行为。绝对没有对我来说可以容忍的咆哮。我认为树立那种文化非常重要。但除此之外，我强调的是一种基于绩效进行评估的开放文化，人们不必担心反驳我或是反驳其他人。我们公开辩论问题，我们走到一起，而且我们也果断地达成……你知道……决定了我们想往哪里走的决策，而且我们能够作为一个团队去共同执行。但是，那种公开诚实的沟通以及团队合作，是我认为非常非常关键的东西。太多人了，而且你在世界各地都能看到，他们害怕说出他们看到的真相。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I think among the most important things that you need is I mean first of all let me start with baselines. Things like civility, things like respect for each other, things like equality of opportunity. Those are things that are a baseline in any company. Um definitely any company that I am a part of I do not accept uh like any behavior whatsoever that does not conform to these uh there's never any yelling um in you know that I will tolerate from literally anyone within uh uh within the company and I think setting that culture is uh is very important but beyond that the thing that I stress is an open culture in which things are evaluated ated on their merit, where people do not have to worry about contradicting me or contradicting anyone else, where we debate things openly, where we come together, where we also decisively reach um you know decisions that uh that dictate where we want to go and we're able to execute together as a team. Um but that open honest communication um and teamwork is something that I think is very very critical. Too many people And you see this all over in the world are afraid to say what they see.

</details>

**Nicolai Tangen**: 你在泰米尔纳德邦长大。那段经历是如何塑造你的？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: You grew up in uh Tamil Nadu. How did that shape you?

</details>

**Sridhar Ramaswamy**: 我在泰米尔纳德邦长大，上大学之前我也在附近邦的班加罗尔待过。我在一个中低收入社区长大。当我长大的那段时间，大部分时间里，你知道，四口之家只有一个客厅和一个卧室。但这是一个深深相信教育是前进道路的家庭，一个对事物充满求知欲的家庭。我的父母都没有上过大学。他们只读完了高中。但他们强调教育，为了帮助我和我姐姐追求更好的生活、让我们接受教育，他们什么都愿意做。所以这里的那些美德非常像，就是去变得知识渊博，变得聪明是重要的，这是有益的，以及努力工作可以为我们所有人创造一个更美好的未来。而且，这些都是我至今都保留的品质。我也想告诉你，我的父母有着出色的“适应性（malleability）”。我去了一所他们不希望我去的大学，因为要把一个小儿子送到离家 300 英里远的大学，是他们非常犹豫的事情，但他们在做这件事上，或在我选择谁作为终身伴侣这件事上，还是支持了我。我认为那种可塑的适应性同样重要。如果我必须把所有这些重新提炼出来，我会说这全是关于教育的价值、努力工作的价值，以及对于不断变化的世界保持适应性的价值。这些都是我深深铭记在心的事情，也是我经常跟我孩子们谈论的品质。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I grew up in Tamil Nadu. I was also in Bengaluru which is uh in a nearby state um until I went to college. I grew up in a lower middle-ass neighborhood. Most of the time when I was growing up, you know, there was one living room and one bedroom for a family of four. But this was a family that profoundly believed in education as a way forward, that was intellectually curious about things. Neither of my parents went to college. They only finished high school. Um, but uh they stressed education and there was nothing that they would not do to help me and my sister uh reach for a better life and uh educate ourselves. Uh so the virtues are very much that of uh being being knowledgeable being smart um is uh is important that it is helpful and that working hard can create a better future for all of us and uh these are qualities that I keep to this day. Uh and uh I'll also tell you that um you know my uh parents were also remarkably malleable. I went to a college that they did not want me to go to um because the idea of sending a young son to a college that was 300 miles away was something that they were very hesitant about but they supported me in uh in doing that or in who I choose as my life partner. I think that kind of malleability is also important. If I had to crystallize all of these back, I would say it's all about the value of education, the value of hard work and the value of being malleable to a changing world. Um, these are all things that uh I take very much to my heart and these are very much the qualities um that I talk to my children about.

</details>

**Nicolai Tangen**: 如果你现在再读一个学位，那会是什么？你对什么感到好奇？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: If you were to do another degree now, what would it be? What are you curious about?

</details>

**Sridhar Ramaswamy**: 你知道，当我长大时，我对像细胞生物学以及身体是如何运作的之类的事情非常感兴趣。我认为它就是……它就是那种让我感兴趣的话题，因为它无限复杂，但同时也无限深奥。我想那将会令人无比满足。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: You know when I was growing up I was really interested in things like uh cell biology and how um the body worked. Uh I think it is just um it's the kind of topic that interests me because it is infinitely complicated but also infinitely profound. Um I I think that would uh be enormously satisfying.

</details>

**Nicolai Tangen**: 最后一个问题。你对年轻人的建议是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Last question. What is your advice to young people?

</details>

**Sridhar Ramaswamy**: 就是我刚刚说的那些事。我还会再补充一条，那就是……我的意思是，我会从我刚刚说的“努力工作很重要”开始。擅长你所做的事情很重要。有能力改变你的想法，去学习和适应是重要的。我还要说的第三件事是：对失败保持韧性非常非常重要。你去尝试新事物非常重要，但你必须接受在许多尝试中你都会失败，而那是完全没问题的。比起你在做的事情里的任何一次具体的胜利，或任何一次具体的失败，你要大得多。对自己有那种脚踏实地的认知，我认为是非常重要的。所以，三件事：努力工作、适应性，以及对失败保持韧性。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: It's the things that I said. Um, and I would add on one more which is I mean I'll start with as I said hard work matters. Being good at what you do matters. Having the ability to change your mind and learning and adapting and you know is is important. The third thing that I would say is being resilient to failure is really really important. It's really important that you try new things, but you have to accept that you're going to fail in many of them and that is okay. You're a lot more than any particular victory or any particular failure in what you do. Having that grounded sense of self I think is very important. So three things hard work, malleability, and resilience to failure.

</details>