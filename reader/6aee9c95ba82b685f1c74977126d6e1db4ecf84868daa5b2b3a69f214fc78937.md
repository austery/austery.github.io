---
author: Norges Bank Investment Management
date: '2026-06-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1jl4ZfgVH1o
speaker: Norges Bank Investment Management
tags:
  - ai-agent
  - cloud-computing
  - model-context-protocol
  - data-platform
  - software-engineering
title: 专访 Snowflake CEO：AI 智能体将如何颠覆软件工程与数据架构
summary: 本期访谈中，Norges Bank Investment Management (NBIM) 的 CEO Nicolai Tangen 对话 Snowflake 的 CEO Sridhar Ramaswamy。双方深入探讨了 Snowflake 的存算分离架构、消费级计费模式，以及人工智能（特别是 AI 编码智能体和 Model Context Protocol）对软件开发产业的颠覆性影响，并分享了 Sridhar 从 Neeva 创业失败中获得的深刻洞察与个人成长价值观。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Snowflake
  - Google
  - Norges Bank Investment Management
products_models:
  - Snowflake Cortex
  - Snowflake Intelligence
  - Neeva
media_books: []
status: evergreen
---
### 嘉宾与平台背景介绍

**尼古拉·唐根**: 大家好！我是**尼古拉·唐根**，**挪威央行投资管理渠道 (NBIM)** 的首席执行官。今天，坐在我身边的是**斯里达尔·拉马斯瓦米**，他是 **Snowflake** 的首席执行官。Snowflake 是一家极其先进的数据平台，全球许多最大的企业都在依托其运转业务。当您的银行批准一项贷款，或者某家医院整合患者数据时，其幕后通常都有 Snowflake 的支持。斯里达尔曾在 **Google** 工作了 15 年，期间他将广告业务规模从 15 亿美元提升到了 1000 亿美元以上。此后，他选择离开 Google 并创办了自己的搜索引擎公司 **Neeva**。就在 Neeva 被收购的两年后，他正式出任了 Snowflake 的 CEO。在 NBIM，我们不仅是 Snowflake 的股东，同时也是其产品的大型用户。我们在 Snowflake 上托管了大约 2PB 的数据，这相当于 200 万千兆字节（GB），而且我们每天在数据库中运行大约 300 万次查询。斯里达尔，非常欢迎你的到来！

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Hello friends, I am **Nicolai Tangen**, CEO of **Norges Bank Investment Management (NBIM)**. Today with me is **Sridhar Ramaswamy**, who is the CEO of **Snowflake**. Snowflake is a data platform on which many of the world's largest companies run their work. So when your bank approves a loan, or a hospital brings patient data together, often Snowflake is working behind the scenes. Sridhar spent 15 years at **Google**, where he grew the advertising business from $1.5 billion to over $100 billion. Then he left Google to start his own company **Neeva**, and just 2 years later he became the CEO of Snowflake. Now, here at NBIM, we are also investors in Snowflake and use its products on a large scale. Along with this, we have about 2 petabytes of data on Snowflake, which is equivalent to about 20 lakh gigabytes of data. And we do about 30 lakh queries in the database every day. So, a very warm welcome to you, Sridhar.

</details>

**斯里达尔·拉马斯瓦米**: 谢谢尼古拉。很高兴能来到这里，我对今天的交流感到非常兴奋。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Thanks Nicolai. Great to be here. I am very excited about this.

</details>

### 什么是 Snowflake

**尼古拉·唐根**: 首先，对于那些从未听过 Snowflake 的人，你会如何简单地向他们解释这家公司是做什么的？请尽量简短。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: First of all, how would you explain Snowflake to someone who has never heard of it? In short.

</details>

**斯里达尔·拉马斯瓦米**: 好的。简单来说，我们是一个数据平台，类似于**云服务计算平台**（比如 **AWS**），但我们的核心焦点完全在于数据。我们帮助客户从各种不同的系统里将数据汇集起来，然后进行深度分析，提炼出商业洞察，并最终将这些洞察导向你可以采取实际行动的业务系统。换句话说，我们是一个面向分析的数据平台。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yes, so we are a data platform. We are like a cloud computing platform, like AWS, but our special focus is on data. We help you bring data from different systems, analyze it, get insights from it, and then take it to the systems where you take action. That means we are an analytic data platform.

</details>

**尼古拉·唐根**: 你们的客户群体主要包括哪些人？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Who are your clients?

</details>

**斯里达尔·拉马斯瓦米**: 实际上，如果看具体数据的话，全球 2000 强企业中（排除中国市场以外）大约有一半可触达的企业都是我们的客户。这其中包括了数百家金融服务公司、医疗保健机构、广告巨头以及许多其他行业的代表。可以说，我们的客户名单非常长，而且我们直接在超过 25 个国家设立了运营机构，而我们的客户则分布在更广泛的国家和地区。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Oh, if you look at it, about half of the addressable Global 2000 companies, meaning companies outside of China, are our customers. This includes hundreds of customers in financial services, healthcare, advertising, and many other industries. So, we can say that the list is quite long. And we operate in more than 25 countries, while our customers are present in even more countries.

</details>

### 存算分离的核心魔力

**尼古拉·唐根**: 当 Snowflake 在 2012 年创立时，提出将**存储与计算进行分离**的概念是非常激进且颠覆性的。请为我们详细讲讲这一点。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: When the company started in 2012, the idea of separating storage from compute was quite radical. Tell us a bit about that.

</details>

**斯里达尔·拉马斯瓦米**: 确实如此。要理解这个极其关键的概念，最简单的方法是回顾一下我们在过去几十年里是如何购买或使用电脑的。我常对人说，在过去近 50 年中，每当一家企业需要计算能力时，本质上就是去购买一个“铁盒子”。在这个盒子里，存储空间、计算芯片和内存的容量都是在出厂时固定好的。一般来说，你必须用这个盒子支撑大约 5 年的业务。因此，如果你在用了一年之后需要更多内存，你是没有任何办法的，只能等待更新换代；而如果你买的 CPU 算力超出了实际需求，你也同样无能为力，因为你早已经为整台机器买单了。这就是传统架构的局限性。顺便说一句，你的手机其实也是这样一个盒子，只是体积更小罢了。在不同盒子之间迁移数据也极其困难，你需要为此做单独的系统集成项目。

因此，Snowflake 核心的一点就是利用云计算打破了这一传统思维。你可以把云看作是一个拥有近乎无限存储容量和强大计算能力的超级系统，许多客户可以共同使用和共享它。我们彻底将计算与存储进行了剥离。我们告诉客户：你需要多少存储空间就用多少存储空间，你需要多少计算算力就调用多少计算算力。如果你想运行一个深度的分析任务，比如 NBIM 内部的某位员工突然产生了一个绝佳的投资灵感，需要对历史信息的所有细节进行全面回溯，那么你可以在一个周末同时启动 1000 台电脑进行高强度分析，运行结束后立即将它们全部关闭，并基于分析结果进行业务落地。这就是 Snowflake 架构的魔力所在。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Absolutely. The easiest way to understand this very important concept is to think about how we have always bought or used computers. I tell people that for the last 50 years, whenever a company needed computing, we bought a box. That box had a fixed quantity of storage, compute, and memory, which was fixed beforehand, and usually you had to work with that same box for about 5 years. So if later you needed more memory, nothing could be done. Just wait. And if you bought more compute or CPU power than needed, even then nothing could be done because you had already bought the machine. That's the real thing. By the way, your phone is also a box. It's just a slightly smaller box. And moving data from one box to another was also quite difficult. You had to do a separate integration project for that.

So, this is where Snowflake changed this whole thinking using cloud computing. You can think of the cloud as systems with almost infinite storage and tremendous compute power that many customers can share with each other. We separated compute and storage from each other. We said take as much storage as you need, and take only as much compute power as you need. If you want to do a deep analytic job, because someone inside NBIM got a brilliant idea for investment for which you had to go through every piece of historical information, then you can start 1000 computers in a weekend, do the analysis, shut them down, and then find out how to apply it in practice. This is the magic of Snowflake's model.

</details>

### 按需付费的商业模式

**尼古拉·唐根**: 大多数软件公司通常是按账号数量收费（按席位收费），但你们却根据用户的实际使用量来收费。为什么这种方式更好呢？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Most software companies charge per seat. But you charge only as much as people use. Why is this method better?

</details>

**斯里达尔·拉马斯瓦米**: 因为这种方式让我们的收费定价直接与**客户获得的价值创造**绑定在一起。这种模式的另一个优势在于，由于我们拥有超过 13,000 家客户，我们对整体市场需求的预测非常精准。因此，我们可以自行消化和调节需求波动带来的负荷变化，从而为客户提供更加稳定且优化的技术架构。这对客户非常有利，因为你不需要提前做出僵化的承诺，规定自己必须持续使用多少存储或多少个 CPU。这意味着你只有在真正需要的时候才会调用资源。大多数分析型任务的需求并不是恒定不变的。正如你所知，即使是交易型的工作负载，白天和黑夜之间也有着巨大的差异，人们在深夜通常不会进行太多的银行转账交易。因此，这些业务量波动是有规律可循的。通过消费级计费模式，我们能够提供极具性价比的定价，因为我们可以在极大规模上统一调度和分摊这一负载。这使我们公司的利益与客户的价值创造完全保持一致。你虽然提前支付了信用额度，但只有在你和你的团队实际运行 Snowflake 时，我们才会将这部分确认为收入。我们在后文还会讨论这一点。在人工智能时代，这种按实际使用量付费的模式变得愈加重要。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Because this keeps pricing directly aligned with value creation. One benefit of this is that we are quite good at estimating demand because we have more than 13,000 customers. Therefore, we manage and amortize the fluctuations in demand ourselves, and we are able to give you a more stable and better model. This is beneficial because you do not have to make a commitment beforehand about how much storage or how many CPUs you are going to use continuously. And this means you spin up resources only when they are needed. Most analytical jobs do not have uniform demand. As you know, even in transactional workloads, there is a big difference between day and night. People do not do that many banking transactions at night. That's why there are many such patterns that are already well understood. Because of the consumption model, we are able to give you extremely affordable pricing because we can manage and amortize this entire load on a large scale. This keeps our company completely aligned with value creation. You pay first, but we recognize revenue only when you and your team use Snowflake. We will talk more about this. In the world of AI, this is a very big thing because you pay according to use.

</details>

### 编码智能体是终极威胁

**尼古拉·唐根**: 确实如此，斯里达尔。那么你为什么会把像 **Anthropic** 这样的模型公司视为你们的竞争对手？因为他们正在彻底重构整个软件世界的秩序。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Absolutely Sridhar. Now, why do you consider a company like Anthropic as your competitor? Because they are completely changing the software world.

</details>

**斯里达尔·拉马斯瓦米**: 听着，我相信对于我们这些在软件行业深耕多年的从业者来说，现在已经看得非常清楚，软件的成本经济学正在发生极为剧烈的变革。如果问我的看法，我会将这种底层的变革与人工智能模型的短期成本或临时波动剥离开来看。现实情况是，在过去的 50 年里，软件开发在很大程度上仍然是一种高度依赖人工的“手艺活”。少数顶尖的专业开发人员通过艰苦的工作去编写和维护软件。软件的开发过程非常艰难，而将它们与各种异构系统进行集成更是充满了挑战。你可以把最优秀的程序员比作音乐会上的**钢琴独奏家**。这样的人才是无法在短时间内批量培养出来的。你需要投入上万个小时去训练，并且你的大脑中必须具备那种独特的才华，才能成为一名伟大的音乐家。到目前为止，软件工程师的培养路径也大抵如此。

然而在软件开发领域，如今大语言模型所代表的，是软件开发领域前所未见的**工业化大生产**。如果深究其本质，这正是我将大模型公司及其正在开发的**编码智能体（Coding Agents）**视为我们最大竞争对手的根本原因。因此，正是看到了这个大趋势，我们也在 Snowflake 内部开发了自己的编码智能体。它们正在成为整个计算平台和信息生态系统的“前门”。这一切虽然始于软件工程师的工具升级，但它的长远影响将远远超出这个范围。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Look, I believe that for many of us working deeply in the software industry, it has now become absolutely clear that the cost economics of software is changing very rapidly. And if you ask me, I would look at it separately from near-term or temporary concerns like the cost of AI models. The reality is that for the past 50 years, making software has largely been a kind of craftsmanship. Some special people make software by working very hard. Making it is also difficult, and integrating it with different systems is also difficult. You can think of the best programmers as concert pianists. Such people cannot be prepared in large numbers suddenly. You put in 10,000 hours, and you have that special talent in your brain. Only then do you become a great musician. It has been somewhat similar with software engineers so far. But in the case of software, what these models represent is an industrialization of software development like we have never seen before. And so if you look at it, this is the biggest reason why I consider model companies and the coding agents they are building to be our biggest competition. So keeping all this in mind, we have also built our own coding agent. These are becoming the front door of computing and the entire information ecosystem. It is starting with software engineers, but its impact will go far beyond that.

</details>

**尼古拉·唐根**: 确实如此。但是对于像 **Amazon** 和 **Microsoft** 这样同样拥有竞争性产品的科技巨头，你们又如何看待呢？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Absolutely. But what about the likes of Amazon and Microsoft, who also have competing products?

</details>

**斯里达尔·拉马斯瓦米**: 是的，我的意思是，无意冒犯，但当涉及到纯粹的数据平台时，我们一直处于市场领先的地位。当然，我们绝对不能低估这些超大规模运营的云巨头，因为他们拥有极其庞大的资源来解决最具挑战性的难题。但就我个人观察来看，我认为这些自动化的编码智能体才是对整个传统软件行业的最重大威胁。在这样的行业生态下，为 Snowflake 寻找一条不仅能生存、而且能蓬勃发展的创新之路，正是我目前作为 CEO 面临的头号挑战。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yes, I mean, no offense, but when it comes to pure data platforms, we have always been top of the charts. And look, companies that operate on such a large scale should never be underestimated because they have great resources to solve the most difficult problems. But as far as I can see, I think these coding agents are the biggest threat to the entire software industry. And in such an environment, finding a path for Snowflake where it not only survives but also thrives, this is my number one challenge right now.

</details>

### 如何利用人工智能革命

**尼古拉·唐根**: 明白。那么继续围绕人工智能的话题，你能告诉我们，你们正在通过哪些具体方式来利用这场革命并从中受益吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Okay, so carrying forward the conversation about AI, tell us in what ways you are taking advantage of this revolution.

</details>

**斯里达尔·拉马斯瓦米**: 好的。如果用极度简化的视角来看待 AI 和像 Snowflake 这样的软件公司，我们在最底层其实只做两件事：第一，我们开发并运行优秀的软件，这是我的工程团队的主要任务；第二，我们把软件销售给像你们这样的客户，并协助其落地部署。因此，我们的很多精力都聚焦在如何大幅提升这些环节的效率上。

在销售端，我们的销售代表现在拥有了可以瞬间获取关键信息的智能化工具。他们的手机里配备了专属的销售助手。我们的解决方案工程师现在仅需 30 分钟，就能为尼古拉定制一套极其逼真的演示方案，其中的测试数据看起来会与你们银行的真实数据毫无二致。通过这些智能化工具，团队为客户提供高价值服务的能力得到了跨越式的提升。

如果谈到软件工程本身，编程的模式正在被彻底重塑。我刚刚参加完一个内部会议，我们当时正在讨论如何推动更多的开发人员转向**规格说明驱动开发（Spec-driven coding development）**。在这种全新模式下，你只需要用英文撰写一份清晰的功能规格说明书（Spec），随后系统就会自动生成第一版代码、编写测试用例、自动完成部署等一整套工作。因此，如今的软件工程与短短两年前相比已经面目全非了。我们面临的重大挑战在于，如何让团队中的每一位工程师快速学会以这种全新的方式工作，并充分释放这些新技术的潜能。目前，我们团队中也涌现出了一些超级明星工程师，他们的产出效率比普通的软件工程师高出了 50 到 100 倍。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Okay. So the thing is that if I look at AI and a software company like Snowflake in a very simplified way, basically at our core we do two things. We build and run excellent software, which is the job of my engineering team, and we help sell and implement our software to customers like you. So a lot of our energy is focused on how to make this fast.

On the sales side, our sellers now have tools that give them instant access to information. A sales agent is present in their phone. Our solution engineers can prepare a customized demo for Nicolai in just 30 minutes, which will have data that looks exactly like your bank's data. With the help of these tools, their ability to achieve better results for customers is truly wonderful.

And if we talk about software engineering, coding is changing completely. I am just coming from a meeting where we were talking about how we should bring even more people into spec-driven coding development, in which you just write an English language spec for what you want to produce, and then you automate the entire process, like writing the first version of the code, testing it, deploying it, and other things. Therefore, software engineering today is not at all what it was just 2 years ago. The biggest challenge before us is that every engineer on our team learns to work this way and takes full advantage of these new possibilities. But we also have superstars who are 50 to 100 times more productive than an average software engineer.

</details>

### 数据资产与智能接口

**尼古拉·唐根**: 明白。那么我的下一个问题是，伴随着 AI 时代的到来，大型企业正在以何种方式重塑其数据资产管理？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Okay. So my next question is, after the arrival of AI, how are large companies changing their data estates?

</details>

**斯里达尔·拉马斯瓦米**: 主要有两个维度。首先，人工智能让你的企业数据变得前所未有地易于访问。这正是 **Snowflake Intelligence** 的核心任务。它为你企业内部的所有数据提供了一个**智能体交互界面**。你可以直接通过自然语言询问它：“我最近最大的几笔投资表现如何？我发现某项投资的净值最近有所下滑，请帮我分析具体原因。这是由于特定行业环境导致的，还是项目本身出了问题？”过去，要想获得这些问题的答案，你需要找专门的分析师团队去跑数，而现在，答案就在你的指尖。这意味着，这种即时且可编程的数据访问方式，将在未来以极具戏剧性的方式彻底改变人们日常的工作状态。

第二种让客户广泛受益的方式是像**原生编码智能体**这样的产品。在过去，如果一个服务商跑去跟客户说“我能把你每天需要重复做的某项工作效率提升 10 倍甚至 20 倍”，这几乎是天方夜谭。然而现在，我们不仅在内部团队中大规模实践这种提效，同时也在向我们的客户输出这种核心价值。因此，无论是企业内部负责生产数据的开发人员，还是最终消费数据的使用者，都在人工智能的赋能下获得了巨大的竞争优势。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Two things. First of all, AI makes your data much more accessible. This is what Snowflake Intelligence does. It is like an agentic interface for your data, where you can directly ask: "How are my biggest investments performing? I see this investment going down a bit. Tell me its breakdown. Is this because of the sector or some other problem?" All such questions, for the answers to which analysts had to be consulted earlier, are now at your fingertips. And its direct meaning is also that due to this fast programmable access to data, the entire way of working in the future is also going to change very dramatically.

The second way our customers are benefiting is things like native coding agents. It does not often happen that I go to my customer and say, "I can make something 10 times or 20 times faster that you have to do every day." This is the work we are doing with our internal teams, and this is the value we are delivering to our customers as well. Therefore, whether it is the data creators within a company or the data consumers, both are getting tremendous benefits because of AI.

</details>

### 深入解读 MCP 协议

**尼古拉·唐根**: 现在我们有了像 **Model Context Protocol (MCP)** 这样的协议，它能够把我们与你们的产品生态无缝连接起来。你能否向我们的听众简单解释一下，MCP 到底是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Now, we have a thing called MCP that connects us to you. Can you explain in short to our audience what MCP actually is?

</details>

**斯里达尔·拉马斯瓦米**: 好的，通俗地讲可以这样理解：MCP 代表的是 **Model Context Protocol（模型上下文协议）**。它其实就是一种通信规范，让任何先进的语言模型或编码智能体能够直接与底层的数据源进行安全、顺畅的对话，并高效地从中检索和读取数据。我们希望客户在使用像 Snowflake Intelligence 这样的产品时，能以极简的方式即时调取数据。与此同时，我们非常强调系统的**互操作性**，即与客户现有的工具生态和谐共存。因此，在 Snowflake 平台中构建的每一个 AI 智能体，都可以通过 MCP 协议被用户所使用的任何外部前端界面远程安全调用。这就是 MCP 协议的关键作用，它扮演着至关重要的互操作性通道角色。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yes, roughly understand it like this. MCP stands for Model Context Protocol. It is just a way by which any language model or coding agent can talk to a data source and get information from it. And we want our customers to use products like Snowflake Intelligence, which make data available directly and easily. At the same time, our focus is also on interoperability, which means working with the tools you already have. Therefore, every agent built in Snowflake can be accessed remotely from any external front end or interface that you use. That is what MCP does. It is an interoperability layer.

</details>

### AI 智能体如何改变工作

**尼古拉·唐根**: 这些智能体未来将如何重塑我们的工作流程？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: How will these agents change your work?

</details>

**斯里达尔·拉马斯瓦米**: 这是一个非常宏大的命题。而且我认为，目前很多普通人对“智能体”这个词的理解还存在偏差。我们应该把智能体理解为**模型与特定执行代码的有机结合体**。它拥有调用各种底层工具的权限，并且能够聪明地判断出在什么时候、以何种方式去调用最合适的工具。举个例子，如果你对它说“帮我写一个小程序”，它非常清楚如何创建文件、如何在其中写入逻辑正确的代码，以及如何调用本地的系统环境或命令行去编译和运行这个程序。更进一步，当你问它“我的投资组合表现如何”时，智能体知道如何去调用资产分析工具、如何处理调取的数据，并最终以直观的图表和文字把分析结果呈现给你。

因此，智能体正在每一个层级颠覆原有的工作形态。虽然现在大家听到最多的可能是编码智能体，但这种抽象化运作的核心概念是普适且强大的。因此，即使是一个这辈子都不打算写一行代码的业务人员，也同样能在这波技术浪潮中受益匪浅。他们可以随时调用公司的所有非结构化文档，访问 Snowflake 中的海量结构化数据，并用极低的学习成本进行操作。如果我给你配备了一个可以访问你全部业务数据的 Snowflake Intelligence，你提出任何业务问题，它都能自动拆解任务、制定分析计划并协助你一步步执行。这就是为什么大家对这类工具感到如此兴奋的原因，它彻底改变了人们工作和思考问题的方式。一切都变得可编程，一切都实现了互联互通。如果你在分析完数据后需要发送一封邮件，你甚至不需要手动复制粘贴。直接对智能体说“把这份报告用邮件发给斯蒂芬”，邮件就会瞬间发出。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: That is a big question, and I feel that the word "agents" is also often not understood correctly by people. Agents should be understood as a combination of a model and some code that has access to various tools underneath, and they smartly know which tool to use when and how. For example, if you tell it, "Write a little program for me," it knows how to make a file, how to write code in it, and then how to call some local tool or system to run that code. But this also works when you ask, "How is my portfolio performing?" The agent knows how to call the portfolio tool, how to analyze that data, and then how to tell you the result. And therefore, agents are changing work at every level. Although you hear about things like coding agents most of the time, the general concept is very powerful. These coding agents are actually a kind of abstraction agents. Therefore, the person who never wants to write a single line of code will also get tremendous benefit from this. They will get access to all their documents, access to structured data in Snowflake, and they will be able to use all of this in a very easy way. For example, if I give you Snowflake Intelligence, which has access to your data, you ask any question related to data, the agent can make a plan for it and help you execute it. This is why there is so much excitement about things like Cloud Work or Snow Work, because it is changing the way people work and think about work. Everything is programmable, and everything is interconnected too. If you have to send an email based on some analysis, there is no need to copy-paste. Just tell your agent, "Send this email to Stephen," and the email will be sent.

</details>

### 脏数据与数据迁移痛点

**尼古拉·唐根**: 确实如此。但我想分享一个我们的实际痛点：为了把我们庞杂的原始数据清理干净，我们花费了数年的时间，而且说实话，那绝对是一份枯燥且痛苦的苦差事。企业的原始数据往往是碎片化、充满缺失和重复值的，而且几十年前的各种老旧遗留系统以各种奇怪的方式拼凑在一起。在实际落地的过程中，这种“脏数据”的现状在多大程度上会阻碍企业对 AI 技术的应用和对你们产品的采用呢？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Absolutely. Now let me tell you one thing: we have spent years cleaning up our data, and to be honest, it was not a fun job. Data is often scattered. There are duplicates, there are gaps, and decades-old legacy systems are somehow connected to each other. In such a situation, how big of an obstacle does this become for the use of AI and the adoption of your product?

</details>

**斯里达尔·拉马斯瓦米**: 在过去，脏数据确实是企业从数据资产中榨取商业价值的最大绊脚石。但好消息是，得益于技术的进步，这个问题现在每天都在变得更容易解决。这正是将**编码智能体引入数据治理领域**所产生的神奇化学反应。以前，如果你想在一个极其复杂的企业数据集里临时新增一个字段，你就必须去重构整条底层的**数据管道（Data Pipeline）**。这个过程可能需要一个专业的数据工程师整整折腾一个星期，因为他必须小心翼翼地去处理各种底层的技术细节。

而现在，我们推出了类似于“技能（Skills）”的概念。你可以把它们理解为用英语撰写的声明式程序，能够实现端到端的业务流程全自动化。你只需要把任务下达给智能体，去喝杯咖啡，一个小时后回来就能看到系统已经完美执行完毕。我们目前正在全力研发由**智能体驱动的自动化迁移服务（Agent-driven migrations）**。在这项技术的帮助下，你可以在短短几天或几周内，将数据从传统的本地遗留系统安全地迁移到云端的 Snowflake。而在以前，同样规模的迁移工程不仅要按季度来规划，甚至要耗费数年的时间。可以说，人工智能在推动企业数据架构现代化的征程中正释放出惊人的威力。这也是我们在这个细分技术方向上投入巨资进行研发的原因。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Earlier, this used to be a very big obstacle in getting the right value from data. But I feel that this problem is getting a bit easier every day. This is the real magic of applying coding agents to data problems. Earlier, if you had to add just one additional column to a complex dataset, you had to make changes in the data pipeline, and this work could easily take a programmer a week because they had to go into every small detail and work hard. Now we have things like "Skills", which you can understand as programs written in English language. They automate the entire process from start to finish. Someone can just start the work and come back after an hour to see that everything is completed. We are working on things like agent-driven migrations. This is a thing where you can migrate data from a legacy system to Snowflake in just a few days or a few weeks. Earlier, the same work used to take not just quarters but several years, and overall AI can prove to be extremely powerful in the entire journey of data modernization. This is the reason why we are investing at a very big level in this area.

</details>

**尼古拉·唐根**: 听起来太棒了。真希望我们 5 年前就能拥有这样的技术，但无论如何，这很令人欣慰。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: I wish we had this 5 years ago, but okay.

</details>

### GDPR 对 AI 创新的影响

**尼古拉·唐根**: 那么我们来谈谈 **GDPR**（欧盟通用数据保护条例）吧。你认为它是否限制或拖累了人工智能在欧洲的发展与应用？尤其是在个人数据保护法律如此严苛的情况下。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: So what about GDPR? Is it limiting or slowing down the use of AI? I mean, look at our personal data protection laws.

</details>

**斯里达尔·拉马斯瓦米**: 从 Snowflake 的角度来看，我们的核心竞争优势之一就在于我们能够提供极其严密且成熟的数据治理与合规管控功能。虽然对于很多企业来说，确保数据符合各项严苛的监管要求确实带来了一份额外的合规负担。作为一个土生土长的美国人，我深知很多同行对 GDPR 颇有微词，并且它在执行过程中的确产生了一些意料之外的消极后果。但不可否认的是，GDPR 里的许多条款和设计理念，在保护个人隐私方面确实展现出了极其超前的行业远见。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Look, a big part of Snowflake's benefits is that we offer excellent governance features. Companies have to make sure that rules are followed, which is an extra burden. Look, I am an American, and everyone criticizes GDPR, and there have been some unintended consequences as well. But there are many aspects of GDPR that show thinking that was really ahead of its time.

</details>

**尼古拉·唐根**: 从大方向上来看，你认为 GDPR 对于欧洲的商业环境而言，究竟是利大于弊，还是弊大于利？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Is GDPR good or bad for Europe?

</details>

**斯里达尔·拉马斯瓦米**: 我觉得这是一个非常复杂且见仁见智的问题。它确实带来了很多副作用。但它同时也给整个行业上了一课，告诉人们制定技术监管政策必须深思熟虑，而不能拍脑袋做决定，相关决策者必须对政策落实后的各个细微层面进行深度的推演。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I think it is quite mixed. It has had many unintended negative consequences. But it has also taught that regulations should be made very carefully, and people should think deeply about every aspect of it.

</details>

**尼古拉·唐根**: 在你看来，它带来最明显的负面副作用有哪些？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What are its unintended negative consequences?

</details>

**斯里达尔·拉马斯瓦米**: 在探讨负面影响之前，我先谈谈它非常积极的一面。作为普通消费者，在 GDPR 的保护下，你现在可以直接去要求任何一家互联网公司：“请永久彻底删除你们服务器上关于我的所有个人数据。”这种对个人数字权利的确认完全归功于 GDPR 的推动。这是一个重大的进步。它迫使包括我当年所在的 Google 广告团队在内的所有大厂，去建立极其精细的追踪和清理机制，搞清楚我们到底收集了关于尼古拉的哪些信息。这显然非常具有进步意义。

但从硬币的另一面来看，那些每次打开网页就会弹出的、令人厌烦的 Cookie 授权弹窗，就是典型的消极副作用。在很多时候，用户最终只是出于疲劳和无奈，在根本没有阅读条款的情况下直接点击了“同意”。我认为这违背了立法的初衷。更深层的问题在于，它大幅推高了欧洲初创企业开展业务的**合规门槛与运营成本**。最终的结果是，这种合规门槛反而成了科技巨头们的“护城河”，因为只有大公司才有足够的财力、法务资源和技术实力去完美适应这些监管要求。相比之下，任何在欧洲起步的初创公司，从成立第一天起就要在这些复杂的法条里挣扎前行。这就是我所说的“ unintended consequences（不符合初衷的副作用）”。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yes, first I'll tell you its positive points. As a consumer, you can tell a company, "Delete whatever information you have about me." This has happened because of GDPR. This is a very big positive point. It forced every company, including my Google Ads team, to track everything we knew about Nicolai. So this is a very positive thing. On the other hand, the walls of prompts that come up in front of you. At one point, you just give up and click yes. I think this is an unintended consequence. I think it has made doing business more expensive for every company in Europe, and ultimately, large companies benefited the most from it because they have enough resources to follow the rules, maintain compliance, and spend money on it. Whereas every new company starting in Europe has to struggle a lot from the beginning to follow all these rules. So by unintended consequences, I mean this kind of thing.

</details>

### 太空数据中心与量子计算

**尼古拉·唐根**: 让我们换个轻松点的话题。未来人类会在外太空部署我们的**太空数据中心**吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: A different question. Will we have our data centers in space as well?

</details>

**斯里达尔·拉马斯瓦米**: 说实话，对于这个充满科幻色彩的设想，我并不是最专业的回答人選。不过，单从物理学和数学的角度去计算，这在工程实现上的难度似乎高得超乎想象。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: To be honest, to answer this question, I am not the right person. But mathematically, it seems quite difficult.

</details>

**尼古拉·唐根**: 明白。那么**量子计算**技术在未来会为 Snowflake 释放出哪些全新的想象空间？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Okay. So what will quantum computing unlock for Snowflake?

</details>

**斯里达尔·拉马斯瓦米**: 这是一个很好的切入点。首先我们需要清醒地认识到，量子计算与当前的超大人工智能模型一样，在技术爆发初期都将带来巨大的**网络安全风险（Security Risk）**。确保我们托管的数据在量子时代依然坚不可摧，是我们的最高优先级任务。在应用层面，量子计算有望在复杂的数学规划、参数寻优和高速搜索等底层技术上，开创出完全不同于以往的高效解决方案。我们非常有信心紧跟这一前沿，并将其转化为我们平台的底层技术优势。我认为，即使在量子计算时代，专注于管理和处理海量数据的核心基础设施服务，其重要性依然不会被削弱。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: That is a good question. I feel that first of all, quantum computing, like large AI models, is a very big security risk. And making sure that your data remains secure is a high priority for us. It promises to bring completely new and different ways of looking at things like optimization and search, and we are confident that we will be able to take good advantage of these new technologies and methods. I think that even in the world of quantum computing, the importance of core infrastructure will remain.

</details>

### Neeva 创业失败的残酷教训

**尼古拉·唐根**: 我们可以聊聊你早期的工作经历吗？你现在依然非常年轻。但当你更年轻的时候，在选择离开 Google 后，你创办了 Neeva。那次创业最终以失败告终，你从中汲取到了哪些受用终身的教训？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Can we talk a bit about your early days? You are still quite young. But when you were even younger, after leaving Google, you started Neeva. What did you learn from that failure?

</details>

**斯里达尔·拉马斯瓦米**: 是的，我想我的性格里有一种理想主义甚至有些天真浪漫的成分，总是希望能亲手去塑造一个我理想中的世界。我始终觉得这是一种积极的性格特质。当年创办 Neeva 时，我真诚地相信：做一款体验更好、更尊重用户隐私的搜索引擎，不仅对人类社会大有裨益，而且在商业上也一定能证明它是一桩伟大的生意。但现实非常残酷，我们学到的最深刻的一课是：在消费级市场，如果你的创新产品无法提供比现有行业垄断者**好上 10 倍甚至 100 倍的压倒性体验**，消费者是不会轻易做出迁移决定的。虽然我在理念层面上知道搜索的体验可以被大幅改良，但我当时并没有拿出一套落地的、能实现 10 倍级体验跨越的具体商业路线图。

最终，Neeva 失败了。因为我们仅仅做出了一个体验稍好一些、隐私保护稍强一点的产品，这在强大的网络效应和用户习惯面前不堪一击。当然，这种试错过程也让我以最深刻的方式认识到：隐私保护有时就像规律健身一样，人人都知道它好，人人都喜欢挂在嘴边，但在现实生活中，真正愿意为之付出代价并付诸实践的人少之又少。虽然这些教训非常痛苦，但我们的团队聚集了极其优秀的人才。我们当时研发出的核心搜索与索引技术，最终在公司被收购后，成为了如今 Snowflake 人工智能大厦的关键基石。所以，那段看似失败的经历最终还是开花结果，衍生出了非常有价值的成果。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yes, I mean, there is a part of me that is very idealistic and very romantic about the world I want to see. I consider this a positive thing. Yes, and Neeva was started with the true belief that building a better search engine would not only be good for people but would also prove to be a wonderful business. And one of the difficult lessons you learn is that consumer products are not adopted unless they give a much better experience than the existing options. At one level, I knew search could be better. But I did not have a concrete plan on how my view of search and information could be 10 or 100 times better. Ultimately, it failed because of that. Because we built a search engine that was slightly better and had slightly better privacy. Of course, you learn the hard way that privacy is also like exercise; we like to talk about it, but in reality we don't practice it. Those were difficult lessons, but we had wonderful people in our team. We built excellent technology, and ultimately that went on to become the foundation of AI in Snowflake. So something very wonderful came out of that.

</details>

**尼古拉·唐根**: 是的，我非常赞赏这种精神。在美国，人们倾向于把失败看作是不可或缺的交学费过程或学习曲线。然而在欧洲，社会舆论对失败的态度往往就没那么宽容了，是吧？这真的很棒。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Yes, I really like the fact that in the US, this kind of thing becomes a learning experience or learning curve. In Europe, they are not seen this way, right? So, very good.

</details>

### 空降 CEO 与穿越风暴

**尼古拉·唐根**: 在 Neeva 被收购之后，你加入了 Snowflake 并在不久后被任命为 CEO。当时市场资本对这一人事变动的反应并不太积极，股价出现了大幅下挫。你能带我们回顾一下你刚出任 CEO 时那段风雨飘摇的时期吗？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: After that, you went to Snowflake and were made CEO. The share price didn't particularly like this news. Tell me about the early days of Snowflake.

</details>

**斯里达尔·拉马斯瓦米**: 是的。我确实是在一个非常艰难的时期接管了 Snowflake，当时公司在业务增长层面的确遇到了极大的瓶颈。事实上，在我正式接任 CEO 的当天，我们向市场公布的未来年度业绩指引直接比华尔街分析师的普遍预期（Consensus）调低了整整 5 个百分点。这才是导致当时股价重挫的真正导火索。当然，我也理解市场的担忧——一个在企业服务领域从未担任过 CEO 的空降兵，突然要接替行业传奇人物**弗兰克·斯鲁特曼 (Frank Slootman)**，这确实容易引发疑虑。

但在我看来，面对如此艰难的危机并带领团队穿越风暴，恰恰是证明一家公司和管理团队是否伟大的最好机会。我们当时没有去理会外界的噪音，而是选择立即全身心地投入到具体的业务中。幸运的是，在接任 CEO 之前，我已经在这家公司担任了 6 个月的研发负责人，对业务细节非常熟悉。我们把所有的焦点重新聚集在“开发伟大的软件产品”上，因为从长远来看，这才是唯一能改变公司命运的关键力量。人们可能会花很多时间去讨论 PPT 上的战略，但如果你身处软件行业，商业逻辑其实极其纯粹：你是否开发出了客户真正热爱的优秀产品？这种对“为客户创造更深层次价值”的极致追求，是推着我们不断前行的动力。正是基于这种纯粹的产品思维，我们迅速开发并推出了 **Snowflake Cortex** 这样的 AI 大利器。你只需要去市场上打听一下，就能感受到客户对这款产品的巨大热情。对于任何一个软件工程师而言，亲手做出一款真正被全球大企业广泛认可和热爱的产品，就是终极的梦想。而对于公司而言，这才是创造长期商业价值的唯一正道。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yes, I believe that I became the CEO of Snowflake at a very difficult time and in a very critical situation when the company's growth was actually starting to slow down. In fact, on the day I became CEO, we kept our guidance for the coming year a full 5 percentage points lower than the market consensus. This was the real reason for the heavy fall in the market. Of course, it also didn't help that an unknown man who had never played the role of CEO before was replacing the legendary Frank Slootman. In my opinion, facing such difficult situations and emerging from them is the mark of greatness. So we just got straight to work. I had full confidence in the company. It also helped that I had been with this company for the previous 6 months, and then we started focusing on making great products again. Ultimately, that's what makes a difference. People talk about a lot of things. But ultimately, if you are in the software business, the question is: are you building products that people really love? This sole focus on creating more value has kept driving us forward. With this thinking, we built products like Cortex. A little search will show you how much excitement and love there is for this product. It is every software engineer's dream to build a product that people love, and that is what makes real value for the company.

</details>

### AI 时代的软件工程转型

**尼古拉·唐根**: 从你的观察来看，优秀的软件工程师身上通常有哪些共同的优秀品质？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What is common among software engineers?

</details>

**斯里达尔·拉马斯瓦米**: 我觉得在人工智能时代到来之前，优秀的软件工程师必须具备两种能力：首先是在宏观架构上进行系统性抽象思考、解决复杂架构难题的宏观视野；其次是在具体代码执行层面对微小细节（甚至是一个标点符号）近乎偏执的微观严谨度。你必须同时具备这两种截然相反的品质。因为软件开发是一个对错误“零容忍”的冷酷学科。如果你在成千上万行代码里漏掉了一个逗号，编译器绝对不会温和地对你说“没关系，我帮你补上了”，它会无情地直接报错，你必须自己去一点点 debug。

而现在，人工智能正在颠覆这种人才画像。我认为在 AI 编码智能体的辅助下，现代软件工程师的角色正在变得更加“概念化”和“管理化”。他现在的工作状态更像是带领和管理着一个由多个 AI 编码智能体组成的虚拟开发团队。工程师的核心价值不再是去记忆具体的 API 调用和语法细节，而是去行使技术判断力（Judgment），去搞清楚当前的技术方案是否真正契合公司的商业目标和产品的实际应用场景。软件开发人员的核心竞争力，正在转变为快速掌握和灵活调用这些智能化开发工具来解决实际问题的能力。这个学科的知识图谱正在以日、以周为单位快速迭代，我相信一年之后的软件工程形态会与今天完全不同。

我可以分享一个身边的真实案例。我的小儿子今年 24 岁，几年前刚从一所非常著名的大学的软件工程专业毕业。当时他非常自豪于自己成长为一个硬核的系统程序员，对计算机底层技术的细节了如指掌，能够设计出延迟仅有 3 到 5 毫秒的超高性能流式计算系统，这是他的拿手好戏。而现在，他在一家前沿的人工智能实验室工作。就在前不久，他有些沮丧地对我说：“爸爸，我在大学里学到的那些扎实的底层编程技巧，在我目前的工作里几乎派不上用场。为了在现在的岗位上取得成功，我几乎必须把所有东西推倒重来，重新学习。”这个真实的案例非常生动地向我们展示了，我们这个行业的技术更迭速度是多么的惊人。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I would say that in the pre-AI era, software engineering meant the ability to think at a high level to solve a problem, and at the same time, the ability to apply things correctly by paying attention to details at an almost passionate level. You had to be capable of doing both at the same time. This is a discipline that does not forgive mistakes at all. If you left out even a comma, the compiler wouldn't say, "No problem, I'll add it." It would show an error, and you would have to fix it yourself. I feel that AI is now changing this entire picture. I feel that the modern AI-driven software engineer has become much more conceptual. Now he is managing a whole team of agents himself. They are using their judgment and understanding about which problems to solve and how solving them makes sense and is useful in the context of the company and the product being built. These are the people who are very quickly learning ways to solve problems using new and excellent tools. This entire discipline is changing every day, every week, and I feel that a year from now, its picture will be completely different. I will give you a specific example. My younger son is 24 years old. He finished studying software engineering from a very good university three or four years ago. He was very proud that he is a systems programmer who understands fine technical details very well. Designing streaming systems with 3, 4, or 5 milliseconds latency was his specialty. And now he works in an AI lab. Recently he told me, "Dad, nothing I learned in school and after that is helping me be successful in my current job. I had to learn almost everything from scratch." This gives you an idea of how much things are changing.

</details>

**尼古拉·唐根**: 听起来太震撼了。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: That's amazing.

</details>

### 每周“战时会议”的效能

**尼古拉·唐根**: 顺便问一下，我听说在 Snowflake 内部，你们运行着一种每周一次的**战时会议（War Rooms）**机制。这具体是如何运作的？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: By the way, at Snowflake, you have something like a weekly war room. What is that?

</details>

**斯里达尔·拉马斯瓦米**: 是的，这是我们在我接任 CEO 初期就迅速确立的一个管理机制。在像 Snowflake 这样规模的公司里，随着时间的推移，团队的分工会变得极其细碎和专业化。从一个产品最初立项研发，到最终完美交付到像你们这样的客户手中，中间涉及了软件工程师、产品经理、设计师、产品市场经理、技术项目经理等一系列漫长的专业协同链条。这套机制在业务稳定、只需要按部就班地扩大规模和优化现有系统时运转得非常好。

但当外部的市场环境和技术趋势正在以日新月异的速度发生剧烈变化，且我们需要快速推出全新产品时，这套漫长的串行决策链条就彻底失效了。我们必须在研发人员和一线用户之间建立起一个**极度紧密的反馈闭环（Feedback Loop）**。我们必须每天、每周与客户甚至我们自己的实施团队进行高频的沟通，甚至直接泡在 Slack 的共享频道里即时解决开发中遇到的实际问题。老实说，这就是我们运行战时会议的全部意义。我们直接打破部门墙，将负责某个全新产品线或核心技术攻关的所有关键决策人（包括我自己在内）聚在一个物理会议室里。我们在战时会议上会极其直接地去过进度：本周我们究竟取得了哪些实质性的进展？有哪些卡点？谁需要来负责解决？这是一种极度压缩沟通层级、提升决策效率的手段。在管理学上，你可以选择按扁平的水平结构去组织团队，也可以选择按垂直的条线去组织。两者各有利弊。而我们的战时会议，本质上就是为了达成特定目标，将跨部门的人员临时重组成一个“虚拟但高度垂直”的高效攻坚小组。直到今天，我依然每周在运行这样的会议。我们在周一进行高强度的规划和任务拆解，在人工智能狂飙突进的今天，我希望在周五就能直接看到研发出的测试版成果。这就是我们为了在这个竞争激烈的市场中生存，而保持的敏捷身段与战斗姿态。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yes, this is a concept we applied early on. At Snowflake, over time, work became very specialized. I mean, every step between a product being made and being used by a customer like you became a specialized discipline. You have software engineers, product managers, designers, product marketing managers, technical program managers. And this stack keeps growing. This works fine when you have a perfect product and your target is to optimize it at every scale and deliver it to people. But this doesn't work when things are changing rapidly and you have to build a new product. In such a case, you need a tight feedback loop between the product makers and users. We need to talk to your team every day, every week, continuously. We have to be present on Slack channels because we have to constantly understand and solve things. Honestly, that was the purpose of war rooms. They brought everyone responsible for a new area into one place. I also used to participate in them, and we would discuss how much progress we made this week. This was a way to speed up communication. As you know, in management, you can organize horizontally or vertically. Both have their advantages and disadvantages. Actually, this was an example of organizing people in a virtual but vertical way to get outcomes. I still run such war rooms today. In many of our war rooms, planning happens on Monday, and in the world of AI, I want to see results by Friday. This is the fast pace at which we are constantly changing and evolving today.

</details>

### CEO 角色与信息消费

**尼古拉·唐根**: 你曾自我调侃说你是一台“邮件处理机器”。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: You call yourself an email machine.

</details>

**斯里达尔·拉马斯瓦米**: [笑] 是的，我感觉我每天就是在靠处理电子邮件度日的。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: [Laughter] I process emails for a living.

</details>

**尼古拉·唐根**: [笑] 我也是这样。但说实话，这背后其实是一个**信息消费与决策上下文**的问题。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: [Laughter] And me too. But honestly, it is all about information.

</details>

**斯里达尔·拉马斯瓦米**: 确实。我也是从这个角度来看待公司管理工作的。我是一个乐于下力气干苦活累活的人。我喜欢扎进具体的业务细节里，同时我也非常有热情去提炼和向团队阐明那些根本性的商业原则，或者帮助团队在关键的十字路口做出重大抉择。为了做到这一点，我每天都需要主动消费海量的一线信息。这一切并不是为了展示勤奋，而是为了在我的大脑中建立起关于公司业务现状的**丰富背景信息（Context）**，并借此磨炼和强化我的**商业直觉（Intuition）**。只有这样，当你面对一年里最关键的那两三个足以决定公司未来数年命运的重大决策时，你才能够凭借敏锐的直觉和丰富的信息做出正确无误的判断。

因此，我把首席执行官的角色定义为一个“首席上下文构建者”。他必须对公司当下的真实技术进展、组织健康度和客户反馈有着极度客观且敏锐的感知。然后基于这个客观的认知，引导整个组织朝着正确的战略方向前进。顺便说一句，我并不认为源源不断地提供新奇点子或拍板决定所有技术细节是 CEO 的首要职责。CEO 最核心的职责是致力于构建一个足够包容和开放的职场生态，让公司里最优秀的人才和最有创意的点子能够自由涌现，而你只需要扮演好一个“Facilitator（协调促成者）”的角色。当团队经过深度辩论并论证出正确的方向时，你代表团队站出来并坚定地表示：“是的，我们必须全面往这个战略方向突围，我们必须全力推出 Cortex Code 编码智能体，因为这代表着我们的未来。”说到底，CEO 的核心价值在于源源不断地为你的团队提供战略支撑与资源保障。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Yes, I mean, no offense. But when it comes to management, I look at it from a similar perspective. I like to work hard. I like to go into details, and at the same time, understand and explain big principles, or help teams make important decisions. Therefore, I consume a lot of information. This is all about building context and strengthening my intuition so that you can make those one, two, or three big decisions in a year that have a deep and long-term impact on your company. Therefore, I see the CEO's role as having a deep and good understanding of what is going on in the company. And then based on that, helping to move in the direction of the right results. By the way, I don't think that giving new ideas, bringing new ideas, or deciding everything is the sole responsibility of the CEO. The real thing is that you prepare an environment where the best ideas can come forward, and your role is of a facilitator. You are the face of the team when you say, "Yes, we should move in this direction. We should launch a coding agent like Cortex Code because that is what will secure our future." Ultimately, it is all about supporting your team.

</details>

### 坦诚互敬的文化基石

**尼古拉·唐根**: 从你的管理实践来看，企业文化中最重要的核心部分是什么？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: What is the most important part of corporate culture?

</details>

**斯里达尔·拉马斯瓦米**: 我觉得有几个关键的方面，但我倾向于首先建立起企业文化的“基本线（Baseline）”。这包括同事之间基本的**职场礼仪与素养（Civility）**、发自内心的相互尊重，以及最终在制度层面上确保每一个员工都享有平等的职业发展机会。我认为这些底线的准则，是任何一家健康运营的公司不可妥协的基石，至少在我有幸参与管理的任何一家企业中，我都会极其强硬地去维护这些底线。在公司内部，我绝对无法容忍任何员工采取粗暴的吼叫、人身攻击或任何居高临下的侮辱性沟通方式。这种行为在任何现代职场环境中都是绝对不可接受的。我认为，由管理层以身作则去确立和维护这种充满尊重的沟通底线至关重要。

在此基础之上，我极力提倡和培育的是一种**唯贤是听、结果导向的开放争鸣文化（Merit-based open culture）**。在这种文化氛围里，下属在发现我或其他高管的决策存在明显纰漏时，他们可以毫无心理负担地站出来纠正我或反驳我，而不需要去担心会不会因为“冒犯权威”而遭到打击报复。在这里，我们可以为了真理和技术方案的优劣进行最充分、最激烈的公开辩论。辩论结束后，大家又能迅速达成共识，并以超强的执行力朝着最终的决策方向迈进。这种“公开透明、绝对坦诚”的沟通模式与协同精神，我认为是企业在快速变化的科技行业中生存的命脉。我们在这个世界上经常会看到很多悲哀的职场怪状：许多员工明明在项目执行中看到了巨大的隐患，却因为种种办公室政治而保持沉默，装作视而不见。在 Snowflake，我们必须坚决消灭这种沉默。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I think one of the most important things, but first I'll start with some baseline. Like civility for each other, mutual respect, and ultimately, equal opportunities for everyone. These are basic things that should be the most important baseline for any company, at least any company I am a part of. And I do not accept any behavior that goes against this. I do not tolerate shouting, yelling, or disrespectful behavior from anyone in the company. Such behavior is not acceptable for anyone. And I feel that setting this kind of culture is very important. And besides that, what I emphasize the most is an open culture where things are judged on their merit. Where people do not have to think twice before proving me or anyone else wrong or contradicting us. Where we debate openly on things, where we all come together, and where we reach decisions very quickly that determine where we need to go so that we can execute them together as a team. But that open and honest communication and teamwork is something that I think is extremely critical. A lot of people, and you see this everywhere in the world, are afraid to say clearly what they are seeing.

</details>

### 家庭熏陶与成长价值观

**尼古拉·唐根**: 顺便聊聊你的成长经历。你在印度的泰米尔纳德邦长大，那段童年时光是如何塑造了今天的你？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: By the way, you grew up in Tamil Nadu. So how did that shape you?

</details>

**斯里达尔·拉马斯瓦米**: 是的，我在印度的泰米尔纳德邦长大，后来在去上大学之前，我也在邻近的班加罗尔生活过一段时间。我童年成长于一个非常典型的下层中产阶级家庭。在我的记忆里，我们一家四口人在很长一段时间里，只能拥挤在一个狭小的起居室和一个卧室里生活。虽然我们的物质条件在当时有些捉襟见肘，但我非常幸运地拥有一个对“知识改变命运”有着坚定信仰的家庭。我的父母虽然只读完了高中、从未有机会踏入大学的校门，但他们对我和姐姐的教育投入有着近乎执着的重视。只要是为了能让我们接受更好的教育、为了能让我们过上更体面的生活，我的父母愿意倾其所有、做出任何自我牺牲。

因此，我的家庭赋予我最核心的精神财富就是：对知识的极度尊重、对事物保持底层的好奇心，以及坚信脚踏实地的**艰苦奋斗（Hard Work）**是改变生活轨迹和创造美好未来的唯一途径。这些朴素的品质，至今依然沉淀在我的骨子里，指引着我的一言一行。而且我也经常会向我的孩子们提起父母的这些故事，希望他们能传承这些价值观。

此外，我还想强调的一点是，我的父母在思想层面上展现出了极度难能可贵的开明度。当年我选择去一所距离家乡 300 英里之外的大学读书，虽然对于当时的父母而言，让年幼的小儿子远离家乡是一件极其痛苦且让他们充满担忧的决定，但他们最终还是选择克制内心的焦虑，坚定地站在了我身后。无论是我后来做出的重大职业选择，还是我选择我的人生伴侣，我的父母始终给予我无条件的支持。这种给予家人理解与自由的“开放（Openness）”品质，对我的一生都有着极深的影响。如果让我用几个词来概括家庭带给我的塑造，那就是：教育的无上价值、硬核奋斗的意义，以及随着世界的变化主动进化和适应的终身学习能力。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: I grew up in Tamil Nadu. I was also in Bengaluru, which is in a neighboring state, until I went to college. I grew up in a lower middle class neighborhood. For most of my childhood, our family of four had only one living room and one bedroom. But this was a family that believed deeply in education to move forward, and in which there was an intellectual curiosity about everything. None of my parents went to college. They only finished high school. But they always put a lot of emphasis on education, and there was nothing they wouldn't do to get a better life for me and my sister and to educate us. So basically, the values are that being knowledgeable, being smart, it is also important to be helpful, and the fact that hard work can make a better life and a better future for all of us. And these are qualities that I still carry with me today.

And along with this, I would also like to tell you that my parents were also extremely open-minded. I went to a college where my parents did not want to send me. It was not easy for them to send their younger son 300 miles away, and they had a lot of hesitation about it. But still, they supported me. Whether it was the decision to go to that college or to choose a life partner, they always supported me. I feel that this quality of openness is also very important. If I had to sum up all these things in a few words, I would say that it is about the importance of education, the importance of hard work, and the ability to adapt to a changing world. These are all things that I keep very close to my heart. And these are indeed the qualities that I talk to my children about.

</details>

### 给年轻一代的成长建议

**尼古拉·唐根**: 如果时光倒流，让你在今天去攻读一个全新的学位，你会选择哪个学科？你目前对哪些未知领域最充满好奇？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: If you were to get another degree today, what would it be? What are you curious about?

</details>

**斯里达尔·拉马斯瓦米**: 其实在我年轻的时候，我就对**细胞生物学（Cell Biology）**以及人体这台精密仪器的运转机制充满了浓厚的兴趣。我觉得这是一个美妙且极其有趣的学科。这个领域之所以对我有着磁石般的吸引力，是因为一方面它极度复杂，充满了无数微观精密的协同，另一方面它的未知深度似乎永无止境。我相信，如果能有机会沉下心去系统性地钻研和理解这个学科，对于我个人而言将是一次极其满足和幸福的智力体验。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: So when I was growing up, I was very interested in cell biology and how the human body works. I think it is a very interesting subject. This is a topic that attracts me because on one hand it is very complicated and on the other hand its depth is also limitless. I think studying that area and understanding it would be a very satisfying experience for me.

</details>

**尼古拉·唐根**: 最后一个问题，对于当今正在迷茫中摸索的年轻一代，你有哪些建议送给他们？

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Last question: what is your advice to today's youth?

</details>

**斯里达尔·拉马斯瓦米**: 我会重复我之前提到过的那些基本原则，并想在此基础之上着重补充几点。第一，脚踏实地的**刻苦奋斗（Hard Work）**在任何时代都绝对是有回报且极为重要的。无论你选择从事哪个行业，努力成为那个领域里的行家里手都极其关键。第二，保持灵活的开放心态，勇于推翻自己陈旧的认知。在这个技术迭代极其迅速的时代，终身学习和随遇而安的快速适应能力是生存的必备技能。第三，也是极其重要的一点，那就是**面对失败的韧性（Resilience）以及从跌倒中快速爬起来的自愈能力**。

这一点无论怎么强调都不为过。年轻时，你必须勇于去尝试各种新鲜的事物，甚至主动跨出舒适圈。但与勇敢尝试同等重要的是，你必须在心理上坦然接受一个客观事实：在你的多次尝试中，有很大一部分最终会以失败告终，而这完全是成长不可分割的一部分，没有任何可耻的地方。请记住，你作为一个人的独立价值，绝对不是由某一次世俗意义上的成功或者某一次惨痛的失败所能定义的。你的人生厚度远远超出这些单一的标签。我始终认为，建立起客观、健康且强大的自我认知与心态是重中之重。总结起来，就是我常说的三部曲：艰苦奋斗、强大的适应力以及永不言弃的韧性。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: The same things I said, and I would like to add one more thing to it, and that is that hard work really matters. Being good at whatever you do matters. Having the ability to change your thinking. It is very important to keep learning constantly and adapt to new situations. And the third thing I would say is the ability to face failure and recover from it. Very, very important. It is very necessary that you try new things. But at the same time, it also has to be accepted that in many of them you will fail, and there is nothing wrong with that. Your identity is not defined by one win or one failure. You are much more than that, no matter what you did. I feel that having the right thinking about yourself is very important. So just remember these three things: hard work, resilience, and perseverance.

</details>

**尼古拉·唐根**: 斯里达尔，我想我们找不到比这更好的地方来结束今天的精彩对话了。非常感谢你百忙之中抽空接受我们的访谈，请继续带领 Snowflake 团队创造不可思议的成就！

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Sridhar, there could be no better place to end the conversation. Thank you so much for taking the time. Keep doing great work.

</details>

**斯里达尔·拉马斯瓦米**: 谢谢你，尼古拉。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Thank you.

</details>

**尼古拉·唐根**: 谢谢。

<details>
<summary>Original English</summary>

**Nicolai Tangen**: Thank you.

</details>

**斯里达尔·拉马斯瓦米**: 非常感谢你，尼古拉。

<details>
<summary>Original English</summary>

**Sridhar Ramaswamy**: Thank you so much, Nicolai.

</details>