---
author: AI Engineer
date: '2026-10-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=laQ8wMysnkk
speaker: AI Engineer
tags:
  - compute-marketplace
  - gpu-procurement
  - forward-contract
  - term-structure
  - asset-depreciation
title: 像买股票一样买 GPU：Compute Exchange 与算力资产的金融化
summary: Compute Exchange 创始人 Carmen Li 介绍了构建中立 GPU 交易市场的实践，类比纳斯达克与大宗商品市场机制，解析预留算力、远期合约及二手硬件交易。通过分析 GPU 期限结构升水与折现现金流模型，探讨了算力资产大宗商品化与金融对冲的未来。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Compute Exchange
  - Silicon Data
  - CME
  - NVIDIA
products_models:
  - H100
  - B200
  - A100
media_books: []
status: evergreen
---
### 像买卖股票一样采购 GPU

>> 周三愉快。我叫 Carmen Li。我是 Compute Exchange 以及 Silicon Data 的 CEO。

我很喜欢上一场环节，大家深入讨论了整个生态系统、出资方、小型市场交易员以及对冲机构。

我们目前所处的领域非常酷。我的公司是 Compute Exchange，实际上是全球唯一的中立 GPU 采购市场。我们始于 2024 年，当时市面上大概只有五家新兴云厂商和三家超大规模云厂商。从本质上讲，我们相当有前瞻性地预见到了 GPU 生态系统的爆发式扩张。

想想今天的股票市场，对吧？当你想买卖股票时，你可以打电话给经纪人。显然，你也可以给几家银行打电话说：“嘿，我想买卖 X 数量的特斯拉，或者其实是 SpaceX，对吧？”你可以那么做，或者你也可以直接通过手机应用在纽交所（NYSE）或纳斯达克（NASDAQ）上进行交易。

这并不意味着你在纽交所或纳斯达克能拿到绝对最优的价格，但它更高效。你知道那里会有流动性，你知道交易会被结算、被清算。你能以非常高效的方式，按你期望的价格拿到你想要的东西，对吧？对于资本市场和资源配置来说，核心就在于效率。

<details>
<summary>Original English</summary>

>> Happy Wednesday. My name is Carmalee.

I'm the CEO for Compute Change as well as Silicon Valley.

Um I love the you know, the previous session. Um we talked the talk about a lot about the whole ecosystem, the financiers, and the small market traders, and the hedgers.

So, what we're sitting in is really cool. I've company of Compute Change. The world's actually the only neutral marketplaces for GPU procurement. We started in 2024 when there were, I don't know, five new clouds, three hyper scalers. Um essentially, we sort of will foresee, interestingly enough, the proliferation of the GPU ecosystem. So, you think about stock market today, right? When you try to buy and sell stocks, you can call brokers. Obviously, you can call a few banks to say, "Hey, I want to buy and sell X amount of Tesla or actually SpaceX, right?" And you can do that or you can transact through your app at NYSE or NASDAQ.

Doesn't mean you get the best price at NYSE or NASDAQ just because it's more efficient. And you know the liquidity is going to be there. You know the trade will be settled. It'll be cleared. You can get what you're looking for at the prices you're looking for in a very efficient manner, right? For capital markets and resource allocation, it's about efficiency.
</details>

### 中立平台与算力核验机制

所以在算力世界里，显而易见我们迎来了大爆发，这非常棒。全球范围内涌现了超过 300 家新的私有云提供商，我们有大量的 Token 工厂，有大量的 API 路由层，这些对最终客户来说都是好事。但与此同时，这也引入了一个非常有趣的变量：我们该如何让交易变得高效，对吧？你真的想给 300 个销售人员挨个打电话吗？我是说，交朋友固然很好，对吧？你想经常和他们聊聊，他们懂很多东西。但与此同时，当你需要在接下来的 48 小时内拿到预留算力合同时，最简单的办法就是去交易所，直接对接经过核验的算力资源。就像去纳斯达克和纽交所买股票一样。

对吧？所以，这是 Compute Exchange 做得极其出色的一点：我们拥有这样一个中立平台。

从设计上讲，**我们不拥有任何 GPU**。一旦我们开始持有 GPU，那这就好比纳斯达克自己下场持有股票一样，意味着我跟你之间、以及我跟算力提供商之间就会产生利益冲突。

我可能会挑拣客户，对吧？我可能会垄断客户关系。正是因为 Compute Exchange 在设计之初就不拥有任何资产，我们在全球范围内与所有算力提供商的合作都非常顺畅。

还有一个非常重要的点，我们对每一笔交易都单独对待，这意味着我们希望为你这个最终客户找到最适合的算力资源。我们专注于预留算力远期合约以及 Token 算力包。

这里给大家分享一些高层次的数据。截至今天，我们拥有超过 100 家经过核验的算力提供商，供应链中有超过 80,000 张 GPU。我们的覆盖范围涵盖除中国以外的所有地区。

<details>
<summary>Original English</summary>

So, in computer world, obviously now we have a huge proliferation, which is great. We have over 300 new cloud private provider globally. We have a lot of token factories. We have a lot of API routers, which is all good for end customers. But at the same time, introduce a very interesting variable is how do we make transaction efficient, right? Do you want to call 300 sales people? I mean, it's great to make friends, right? You want to talk to them regular basis. They know a lot of things. But same time, when you need compute in the next 48 hours on reserved contracts, is easiest way is go to exchange and then go to the verified computer resources. Just like go to Nasdaq and I see to buy stocks.

Right? So, this one of the things computing does extremely well is we have this neutral platform.

And by design, we do not own GPUs. Once we start owning GPUs, that would translate to just like Nasdaq owning stocks, translate to I have a conflict of interest with you and then with the providers.

I could cherry-pick clients, right? I could hoard relationships. Because Compute Change does not own anything by design, we work really well with all our providers globally.

Um and one very important thing is we treat every single transaction individually, meaning we want to find you as an customer the most suited computer resources. And we focus on reserved compute forward contracts as well as token packages.

So, give you some um high-level. So, today we have over 100 verified providers um and over 80,000 GPU in supply. We cover all regions, obviously ex-China.
</details>

### 从实物核验到物理交割期货

>> [吸气声]

>> 我们的承诺是 24 小时交付。我们与市面上其他所谓撮合经纪人的区别在于，我们确实会对 GPU 进行技术核验。如果它是现有的预留算力，意味着设备已经处于实际可运行状态，我们会验证 UUID、库存和性能指标。我们会运行 Nvidia DGX、Inference X、MLPerf，确保你拿到的确实是承诺给你的资源。所以我们处于中间环节，充当被信任的平台角色。

如果是远期算力，假设你需要从 2027 年 1 月 1 日开始交付的 GPU，我们实际上会审查采购订单（PO）、他们拿到的所有许可批文，确保在尽职调查层面为你把关。

而在另一端，对吧？如果你是一家新兴云厂商，你会面对无数来寻找算力的客户。你该如何判断谁有能力按约定的费率付款？这正是 Compute Exchange 发挥作用的地方。我们会对客户进行 KYB 和 KYC。显然，你必须确保你的客户确实是他们自称的那个主体。因此我们介入并提供这类核验，就像任何合规交易所做的那样。

我们在远期市场中所做的一切，实际上都是在为**实物交割的期货合约**打前站。

我也给大家介绍一下我的背景，为什么我在做这件事情。抱歉，我也许不该这么说。我的职业生涯始于芝加哥的 DRW Trading，当时担任能源期权做市商。我做那行做了四五年。作为能源期权做市商，一切都非常直观。你有 WTI 原油，你有布伦特原油（Brent），对吧？WTI 是实物交割的大宗商品合约；布伦特则是现金结算的。它们有着截然不同的应用场景：如果你追求的是金融层面的对冲，对吧，对冲你的价格波动、成本波动，你会去选布伦特；如果你是想实际采购资源，你就会用 WTI。

因此，我们正在 Compute Exchange 打造算力领域的 WTI。

<details>
<summary>Original English</summary>

>> [gasps]

>> Um our commitment is 24-hour turnaround. The difference between us and other so-called brokers is we do verify GPUs. If it's existing reserved capacity, meaning things are actually in a functional stage, we'll verify the UUIDs, the inventories, the performances. We run Nvidia DGX, Inference X, MLPerf, make sure you get resources you promised to get. Um so we're in the middle middle sort of trust the platform.

So if it's forward capacity, I'd say you need GPUs starting Jan 1st, 2027. We actually look through the purchase orders, all the permits they get, make sure, you know, we help you do the due diligence level.

And on the flip side, right? If you're a new cloud, you can send this this is a zillion clients looking for compute. How do you know who has the ability to pay at a scheduled rate? That's where Compute Exchange comes in. We do KYB KYC of the clients. Obviously, you want to make sure your clients is the clients you think they they are. So we step in and do that kind of verification just like any exchange would do.

And everything we do in the forward markets is actually a precursor to physically delivered futures.

Also give you some context why I am what I do. Sorry, I probably shouldn't say that. I start my career as energy option market maker um at DRW Trading, Chicago. So I did that for 4 5 years. So as option energy market maker, everything's very intuitive. You have WTI, you have Brent, right? WTI is a physically delivered commodity contracts. Brent is cash settled. They also have very distinct use cases. You're looking for hedging in the financial sense, right? The your price volatility, your cost volatility, you're going to Brent. You're looking physically procure resources, use WTI.

So we're creating that the WTI at Compute Exchange.
</details>

### 三类算力采购方式：预留、远期与二手市场

目前通过 Compute Exchange 采购算力的方式主要有：你可以获取预留合约，也可以获取 GPU 和 Token 的远期合约。

让我解释一下。GPU 的远期合约非常合情合理，对吧？你需要从未来某个时间点开始的算力，而目前没有任何现成资源，所以这是我们日常在做的事情。

Token 远期我认为算是一个相对较新的概念。基本上，你可以把它理解为专属部署或本地化部署，对吧？类似地，你预留了裸金属 GPU 集群。你预留了一个集群，但你在上面拥有专属的 Token 部署。因此，你能获得针对特定模型的保证 SLA。你的量化方式、精度等级，一切都在一定时期内为你固定下来。

所以，我们试图在这里解决按需 Token API 价格波动剧烈的问题。

第三点是，我们拥有一个庞大的市场——公开硬件市场。这非常有意思。二手服务器交易始于去年，当时很多人直接私信我说：“嘿 Carmen，我机房里闲置了大概 20,000 张 H100。你能帮我接手吗？”

我当时的反应是，我不知道啊，我显然不可能把它们堆在家里。于是，我们开始搭建二手服务器销售市场。在过去的差不多 12 个月里，这一直是一个极其活跃的市场。

我们再次覆盖了所有的服务器，甚至连 B200 都已经出现了二手交易。有时成交价甚至高于建议零售价（MSRP），对吧？这完全讲得通，想想疫情期间二手车交易价格超过新车价格的情况。

所以，我们覆盖了算力的三大核心层。

<details>
<summary>Original English</summary>

So the ways to buy compute through um Compute Exchange right now, you can get reserved contracts, you can get forward contracts on both GPU and token.

Let me explain. The forward contracts on GPU is very reasonable, right? You want something starting in the future, nothing available right now. So that's something we're doing on regular basis.

Token forward I think can be a newer-ish concept. Basically, you can think about as a dedicated deployment, on-premise deployment, right? Similarly, you reserve a bare metal GPU clusters. You reserve a cluster, but you have dedicated token deployment on top of that. So, you get guaranteed SLAs for that particular models. You get quantization, precision, everything's fixed for you for a period of time.

So, we try to solve the on-demand token API volatility pricing problem here.

The third is we have a huge market, open hardware market. It's really interesting. The secondary server transactions started last year when people just pinging me say, "Hey Carmen, I have like 20,000 H100 sitting at data center. Can you take away from me?"

So, I was like, I don't know. I can't store it in my home, obviously. So, we started having a marketplace for secondary server sales. This has been a very vibrant market for the past I would say 12 months.

We cover again all servers, even B200 you see secondary transaction is happening.

Sometimes trading above MSRP, right? Can make sense think about like COVID times when secondary cars trading above, right? It's a brand new car price.

So, we covered the three major layers of compute.
</details>

### 平台运作与询价机制（RFQ）

关于预留 GPU，显然前面的讲者已经把条款讲得非常透彻了。我们支持的起步门槛是单节点起租、一个月起订，然后可以一直延长到三年、四年、五年，对吧？这完全取决于供应情况和提供商，但你有机会提出自己的偏好。我们不做按需（on-demand）模式。

另一件对配置变更非常有效的事是，我们提供了相当高的灵活性。假设你在数量或租期上过度承诺了，你可以将其回售给平台，对吧？这是我们承诺会做的事情。所以如果你超额采购了，你不需要太担心。

好的，进入实时部分。我稍后会做一个快速演示。我们有很多现成的市场挂单，你可以浏览、与提供商沟通，并找出最佳的配置交付机制。

如果你没看到喜欢的资源，你也可以发起 RFQ（询价）。实际上，我们每月收到的 RFQ 需求金额已经超过 10 亿美元。听起来很大，但我们都知道对于算力来说这并不算特别夸张，对吧？但这依然能反映出活跃度。我们看到 RFQ 请求的跨度非常大，从单一节点一直到 20,000 个节点。因此我们的客户形态各异，用例千差万别，这非常棒。

是的，你设定交付时间并提交，我们会进行路由。在后台，我们有库存跟踪系统。通过全球 100 多家提供商，我们大致清楚谁在什么时间会有闲置算力。假设你提交了一个请求，说：“嘿，我需要 300 张 B200 GPU，位于美东地区，从 1 月 1 日开始交付。”我们会说：“我们认为有三家提供商符合条件。”我们会将需求路由给这三家。他们会通过平台给你回复，向你提供包含各项参数的指标明细：价格、规格、SLA；如果是现有服务器，我们还会对其进行跑分测试。接下来就由你来选择，对吧？价格不是唯一的参考指标。我们坚信应当给予你尽可能多的透明度，然后由你来做决定。

所有信息都集中在一个页面上。同样，明细返回后你能看到全部细节，然后我们为双方引荐对接。我们从不垄断客户关系，对吧？我们会确保你清楚知道自己在跟谁打交道。

用今天的价格购买明天的算力，这是一个实物采购平台。

这里展示的是二手翻新 GPU。在二手 GPU 交易板块，我们拥有一群极其令人兴奋的生态参与者。我们覆盖的型号从 4090 一直到 B200、AMD 等各类硬件。

库存是实时更新的，我们会通过各种渠道与你对接，比如邮件、即时通讯等任何你希望的方式。

我们进行端到端的跟踪。我们实际上对所有参与者都有评分机制：我们会对你（我们的客户）进行评分，也会对我们的算力提供商进行评分。目前你们还看不到这些评分，但这会非常有趣。我们打算在年底为提供商举办庆祝活动，颁发亚太区最佳提供商、欧洲最佳提供商、美国最佳提供商、最负责任提供商等奖项。敬请期待。

核验网络：所有环节都经过核验。我们充当中介角色，在某些事情不够清晰时提供协助，努力确保大家理解我们在生态系统中见过的最佳实践。

<details>
<summary>Original English</summary>

So, reserve GPU, obviously, I think the previous speaker covered extremely well with the terms. The minimum we do is one node starting at one month, and then we can go all the way to three, four, five years, right? It's all depends on the availability, the providers, but you get a chance to state your preferences. We don't do on-demand.

And another thing really works really well for config changes we do provide a flexibility. Let's say you have over committed it in terms of quantity or duration, you can sell it back to config change, right? So, that's something we committed to do. So, you don't have to worry too much if you over bought.

All right, segment life So, I will actually do a quick demo later. Um so, we have a lot listings, marketplace listings you can browse and chat with the providers and figure out the best silver mechanisms.

You can also RFQ if you don't see anything you like you liked. We actually seen over a billion RFQ'd every month. Sounds big, but we all know it's full computer it's not that huge, right? But still you see the the the the the activities, which a lot is we see a big range of RFQ requests from one node all the way to 20,000 nodes. So, our clients are you know, all different shapes and forms, different use cases, which is great.

Yeah, so you set timing submit and we route it. So, in the behind the scene, we have inventory tracking. So, with over 100 providers globally, we know who has one roughly one right before capacity. And then I say you you submit a request in that hey, I need 30 300 GPUs B200 US East starting Jan 1st. We say, you know, we have three providers we think they have those. We'll route them to the three. They will respond to you through the platforms and they'll give you um a rubrics back. Pricing, specs, SLAs, we benchmark them if it's existing servers and then it's your choice, right? Price is not only indicator. We believe give you as much transparency as we can and then you will make a decision.

So, everything is in one place. Again, the rubrics come back. You will see everything and we introduce you to each other. We never hold relationships, right? We'll make sure you know who you're dealing with.

Um so, buy tomorrow's computer today's price. So, it's a physically procured platform.

This is the used refurbished uh GPUs. So, again, we have a extremely um exciting uh ecosystem participants in this uh in this uh secondary GPU cells. We cover from 490s to B1200, AMD, everything.

Inventory is life and we do connect with you through all different channels like email, chat, however you want to do this.

Um we track end to end. We actually have scoring for everybody. We score you, our customers. We score our providers. You can't see it quite yet, but you know, it'll be really fun. Um we're going to have end of year celebration for our providers. We can We're going to give all the best provider in APAC, best provider in Europe, best provider in US, most responsible providers. So, we're going to have a lot of a provider awards coming up. Stay tuned.

Um verify network. So, everything's uh you know, verified, which is you know, negotiate state exchange. So, we help in terms of be the middleman. Sometimes things are not very clear. We try to make sure people understand what's the best practices we have seen in the ecosystem.
</details>

### 平台界面演示

我来快速给你们展示一下这个平台。我觉得这样更有趣。

在这里。这就是我们的平台。你可以看到大量可用的实时库存。顺便说一句，任何人都可以来注册，完全免费。使用我们平台没有任何弊端：你不一定要买，你可以先浏览；如果你对我们目前没有的资源感兴趣，你可以发起报价请求（RFQ）。

你可以先从选择硬件厂商类型开始。同样，我们对 GPU 品牌保持中立。你可以选择具体型号，选择部署类型。你可以选择 GPU 的数量。你可以选择计算互联偏好、CPU 平台、存储配置，以及你所需要的一切。还有一些可选配置，如系统软件栈、所在区域。当然，如果你接受的话，我们鼓励你选择多个地区。你可以添加头节点，告诉我们你的具体用例，填写任何你想要的信息，然后提交 RFQ。

这一套流程运转得极其稳健。显然，如果你有任何反馈，随时告诉我们。

<details>
<summary>Original English</summary>

I'm going to quickly show you guys the platform. I think that's more fun.

Uh here.

So, this is the platform. You can see a bunch of available inventories. By the way, anyone can come sign up. It's completely free. There's no downside using us. You don't have to buy, you can browse. You can request for quote if you, you know, interested something we don't have.

You can start with your vendor type. Again, we agnostic of GPUs. You can select your model, you can select your deployment type.

You can select number of GPUs.

You can select your compute interconnect preferences, CPU platforms, storages, everything you need. And then some optional items with system software stacks, regions. Obviously, we encourage you to select multiple regions if you open to that. You can add head nodes, tell us your use cases, anything you want, and then submit RFQ.

So, this has been extremely robust. And then we, you know, we obviously we want to make sure um if you have any feedback, let us know.
</details>

### GPU 算力的期限结构与升水（Contango）

好的，关于 Compute Exchange 的部分我就先讲到这里。

我想我还有一点时间，非常想给你们看一些我们在期限结构方面观察到的数据。补充一些背景信息：我是 Compute Exchange 的 CEO，同时也是另一家名为 Silicon Data 的公司的 CEO。

我是 Silicon Data 的创始人兼 CEO，这家公司相当于算力领域的彭博社（Bloomberg）。我们为芝加哥商业交易所（CME）提供指数，用于结算他们即将于几周后推出的期货产品。我对这一点感到非常兴奋。

即将开始在 CME 交易的品种将包括 H100 云端按需费率以及 B200 的价格。

我想给大家展示的是隐含远期曲线（implied forward curve）。正如我提到的，Compute Exchange 做了大量的远期算力交易。本质上，无论是对云厂商还是对最终用户来说，大量的长期合同都将变得至关重要。我把图表放大一下。

黄色的线代表去年，对吧？横轴 X 轴代表租期长度，纵轴 Y 轴代表美元金额。去年黄色的线呈现出彻底向下倾斜的曲线，对吧？这意味着你签署的合同期限越长，每张卡每小时的单价就越便宜。而从今年年初开始，整条曲线向上平移，并演变成了**期货升水（contango）**形态。如果你看那条红色的线，对吧？这意味着人们签署更长期的合同已经拿不到足够的折扣了。这暗示着市场预期未来价格会上涨。

现在你看到整条曲线还在继续向上平移并趋于平坦，对吧？这意味着人们签署长期合同不仅没有折扣，反而可能会承受溢价惩罚或面临不同待遇。这是我们在预留合同中观察到的现象。

如果看隐含远期费率——这里展示的是隐含远期费率，对吧？因为我们目前还没有正式的期货交易，所以这是基于我们的期限结构计算出来的。我们采用了与美国国债期货曲线类似的方法论。你可以看到，市场的共识预期是：在未来的 36 个月内，价格可能会上涨。当然，市场共识并不一定代表绝对正确。

再看 B200：去年的曲线同样呈现升水状态，而今年整条曲线整体向上平移，每一个期限都变得更贵，而且曲线变得更加扁平，对吧？隐含远期费率也是类似的，大家认为价格会继续上涨。

我之所以指出这种期限结构，是为了向大家说明：**GPU 的行为与任何传统大宗商品完全一致**，它具有非常清晰的期限结构风险，而算力数据期货正是对冲这种风险的极佳工具。

<details>
<summary>Original English</summary>

So, I'm going to pause on Compute Change side.

Um I think I have some time left, which I'd love to show you some of numbers we've seen in terms of term structure. Also, context. I'm CEO for Compute Change. I'm also CEO for another company called Silicon Data.

So, I'm a founder CEO for Silicon Data, which is the Bloomberg for compute. So, we provide indices for CME to settle their futures on, which will be happening in a few weeks. We I'm very excited about this.

So, the one that's going to be start trading at CME will be the H100 near cloud on demand rate as well as V200 um prices.

What I want to show you is implied forward curve.

So, as I said, Compute Change we do a lot of forward capacities. So, essentially a lot of longer term contracts is going to be very critical using about even in your cloud or your your consumers. Let me just make it larger.

So, the yellow line was last year, right? The the X horizontal line is the duration, and the dollar amount is the Y axis. So, last year was complete downward sloping curve for the yellow line, right? Meaning the longer term contract you signed, the cheaper you know, was per shift per hour. And this year, starting early this year, the whole curve shift up and became contango. If you see the the red line, right? So, translate to people not getting a discount enough discount for longer term contract. Implies that people assume the price going to rise down the line.

And now you see the price the whole curve keeps shifting up, got flattened, right? So, meaning people are now either get penalized or get, you know, awarded by signing long term contract.

This is reserved contract we observe.

And if you look at implied forward rates, this is not this is the implied forward rates, right? Because we don't have a future trading. So, this is calculated based on our term structure. And we use similar methodology as Treasury futures curve. So, you can see a market consensus view is the price could go up next in the the future next 36 months.

Again, market consensus doesn't mean it's right.

If you look at B200, again, last year was contango and this year the whole curve shift up. Every single term is more expensive and it's got flattened, right? Implied forward rates, similarly, people think the price going to go up.

I want to point this out the term structure how is this shows you that GPU is behaves just like any commodity, have a very clear term structure risks, which data futures are excellent at hedging.
</details>

### 大宗交易、估值模型与二手市场溢价

因此，我们看到围绕这种期限结构发生了大量的大宗交易（block trading）。想想看，对吧？如果你的资产负债表上趴着服务器，未来 5 到 6 年你都背负着融资偿付义务，而你只签下了前三年的预留租期合同，那么你在第四、第五、第六年基本上就完全处于风险敞口中，对吧？所以你希望通过进入互换（swaps）或大宗交易来对冲掉这部分风险。

又或者，即使在前三年你已经签订了转售合同，但交易依然在发生。万一转售合同违约了呢，对吧？某些参与方能提供什么样的担保？因此，我们看到围绕这些指数展开了大量的大宗交易，按浮动利率进行交易。

这张图表实际上也被 NVIDIA 团队以不同的方式使用。在 NVIDIA 最新的 9 月份投资者日演讲材料中，他们提到我们是其演讲中唯一被引用的数据提供商。这非常有趣。当几家银行将 GPU 服务器计入资产负债表时，Silicon Data 已经成为了他们的估值评估机构。

大家在这里看到的一切都是前瞻性视角的预测，对吧？也就是**现金流折现（DCF）**模型。正如我所说，我们有一套期限结构体系。假设对于 A100 而言，对吧？A100 已经面世六年了。如果今天你签了一份关于 A100 的三年期长期租赁合同，有一个约定费率，我们把这些现金流折现回当期零时刻，就能得出这笔资产到底价值几何，对吧？

显然，模型中融入了大量的参数变量：利用率是多少、运营成本是多少等等。这其中包含一系列假设，我们对此保持相当透明。我们实际上针对全球所有的 A100、H100 和 B200 服务器计算了标准化价值下的残值，然后将其与直线折旧进行对比——也就是大家普遍采用的五年期直线折旧法。

有趣的是 A100，对吧？尽管它的价值曲线是向下倾斜的，但其资产价值依然高于会计折旧中的直线曲线。而 H100 显然正如大家所见，现在已经彻底疯狂，价格实际上不跌反涨。我的类比就像疫情期间的二手车一样，价格直接飙升了，对吧？至于 B200，目前的价格显然已经远超其官方建议零售价。

这让大家对二级市场上正在发生的事情有了一些直观了解。我想我的发言时间已经到了。大家可以通过 Carmen CLI@computerhistory.com 随时联系我，或者通过 Twitter 联系我，我的 Twitter 账号是 Carmen Li。就是 Carmen Li。非常感谢。

<details>
<summary>Original English</summary>

So, we have seen a lot block trading happening around the term structure. So, you think about this, right? If you have servers on your balance sheet, you have financing obligation for next 5-6 years, and you have reserved contracts for first three, then you're exposed essentially year four, five, or six, right? So, you want to hedge that risk out by entering, you know, a swaps or block trading.

Um so, those are things Oh, or there there are trades happening even for the first three years, which you have resale contracts on. What if the resale contract defaulted, right? What's your um guarantee from some of the players? So, we saw block trading happening around the indices. Trade as a floating rate.

This chart um actually is being uh used differently by the NVIDIA team. Um in NVIDIA's latest uh um September investor day deck, they said us with only data provider that actually cited in our deck. Um this is very interesting. Silicon data becomes the appraisal for a few banks when they have GPU servers on their balance sheet.

Um this everything you see here uh forward-looking view, right? So, it's discounted cash flow. So, as I said, we have a time structure. So, assume A100s, right? A100s have been around for six years. If today you sign a three-year long lease on A100s, and you have a rate, and we discount the the cash back to time zero, you have how much the asset's worth, right? Obviously, there's a lot of things baked in, utilization rate, what is your cost. There's a bunch of assumptions which we're pretty transparent about. Um we actually calculate the residual value for normalized value, obviously, across all A100, H100, B200 servers globally. And then we'll compare that with the straight-line depreciation, which is everybody using the five-year depreciation. What's interesting is the A100, right? Even though it is downward sloping, you know, think means things are a but it's worth the accounting depreciation curve, straight line. And the H100 obviously, you know, it's going going bananas now and the price actually went up. My My analogy would be just like secondary cars during COVID time. The price went up, right?

And B200 obviously went above its MSRP by this point.

So, this is give some give you some views about what's going on in the secondary market side. I think I'm out of time, but you know, feel free to follow me at Carmen CLI at computerhistory.com, CLI@computerhistory.com. Feel free to get me on Twitter. Carmen Li is my Twitter handle. Just Carmen Li. That's it.

Thank you.
</details>