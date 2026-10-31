---
author: Latent Space
date: '2026-10-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=EAtLq9_vrE0
speaker: Latent Space
tags:
  - compute-market
  - futures-trading
  - physical-settlement
  - programmable-datacenter
  - gpu-clustering
title: 可编程数据中心与算力期货：专访 SF Compute 创始人 Evan Conrad
summary: SF Compute 创始人 Evan Conrad 深度解析如何通过“物理交割”构建真正流动的算力金融市场。访谈探讨了英伟达与云厂商在算力期货中的利益冲突、算力集群的性能折价与物理交割工程难点，以及如何将数据中心虚拟化与可编程化，降低 AI 基础设施的融资成本与资产残值风险。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Evan Conrad
companies_orgs:
  - SF Compute
  - Nvidia
products_models:
  - B200
  - H100
media_books: []
status: evergreen
---
### 巨头与算力市场

**主持人**: **英伟达**（Nvidia）显然是这个领域里不可忽视的庞然大物。为什么他们自己没有去打造一个超级计算机交易市场呢？

<details>
<summary>Original English</summary>

**Host**: Nvidia's obviously like the 800-pound gorilla in the room. Why don't they Why didn't they make a supercomputer?

</details>

**Evan Conrad**: 我们的理解是，英伟达自己做不了这个市场，但这个市场的存在却能让他们获得巨大的利益。他们做不了的原因在于，一旦他们下场做交易平台，其独立性就无法满足各方在上面进行公正交易的要求。

<details>
<summary>Original English</summary>

**Evan Conrad**: So our impression is that Nvidia can't make it, but benefits tremendously from it existing. The reason why they can't make it is because they would then not be independent enough for people to trade on it.

</details>

### 欢迎来到峰会

**主持人**: 不管怎样，Evan，欢迎回到 AI 领域，欢迎来到 **AI Engineer** 峰会！这其实是你第一次参加 AIE 吧？

<details>
<summary>Original English</summary>

**Host**: Anyway, Evan, welcome back to A I space. Welcome back to A I E. Actually, first time at A I E?

</details>

**Evan Conrad**: 我想是的，没错。

<details>
<summary>Original English</summary>

**Evan Conrad**: I think so, yeah.

</details>

**主持人**: 这次非常特别，因为我觉得你一直在算力交易和算力市场上耕耘，而现在这个时刻的感觉已经完全到来了。

<details>
<summary>Original English</summary>

**Host**: This is very special one because I feel like you have been working on computer trading computer markets for a while. Now it's like feeling of the moment.

</details>

**Evan Conrad**: 确实是这样。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah.

</details>

**主持人**: Jump 基本上已经宣布他们正在进军算力市场，这也是为什么我很兴奋能把相关的人聚集起来。你见到了来自 **SemiAnalysis** 的 Oliver，他基本上已经开始对算力市场展开研究覆盖了。这是我的观察。所以大家都会去关注你的演讲。

<details>
<summary>Original English</summary>

**Host**: Jump basically announced that they are getting into computer markets, which is why I'm excited to sort of cluster people. You met Oliver from Semi Analysis, who is basically initiating coverage on computer computer markets. This is This is my read on this. So people are going to watch your

</details>

**Evan Conrad**: 演讲。

<details>
<summary>Original English</summary>

**Evan Conrad**: talk.

</details>

**主持人**: 我觉得那篇演讲非常出色地解释了你的创业起源、你们为什么必须存在，以及你们正在解决的硬核问题。

<details>
<summary>Original English</summary>

**Host**: I think it's very good explanation of like both your origin story and why you need to exist and what the hard problems you work on.

</details>

**Evan Conrad**: 是的。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah.

</details>

**主持人**: 表达方式极其简单明了、引人入胜。我非常嫉妒你的写作能力，因为你展示了在 NeurIPS 上分发的那张传单。真的很直截了当、清晰有力。

<details>
<summary>Original English</summary>

**Host**: Done in a very simple engaging manner. I'm very jealous of your writing skills cuz you showed the flyer for that you showed at NeurIPS. Yeah. It was like it's pretty straightforward and like simple and like it's it's good.

</details>

**Evan Conrad**: 哈哈，是的。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah.

</details>

**主持人**: 总之，恭喜你！

<details>
<summary>Original English</summary>

**Host**: So anyway, congrats.

</details>

**Evan Conrad**: 非常感谢，我很感激。同时也要祝贺你们举办 AIE，看起来你们的发展势头极其迅猛。

<details>
<summary>Original English</summary>

**Evan Conrad**: Thank you. I appreciate that. And also congrats on A I E. It's It seems to Y'all are rolling.

</details>

**主持人**: 我们确实势头正猛。我刚从明年的 AIE 场地考察回来。

<details>
<summary>Original English</summary>

**Host**: We're rolling. I just came back from the site tour for next year's A I E. And then for

</details>

**Evan Conrad**: 能提前给我透露一点提示吗？

<details>
<summary>Original English</summary>

**Evan Conrad**: Give me like a hint.

</details>

**主持人**: 在贾维茨会议中心（Javits Center），就是举办纽约漫展的地方。

<details>
<summary>Original English</summary>

**Host**: At Javits Center. It's the same place they do Comic-Con.

</details>

**Evan Conrad**: 哇，厉害了！

<details>
<summary>Original English</summary>

**Evan Conrad**: Okay, wow.

</details>

**主持人**: 那里非常宏大。

<details>
<summary>Original English</summary>

**Host**: Which

</details>

**Evan Conrad**: 哇，太震撼了，真棒！

<details>
<summary>Original English</summary>

**Evan Conrad**: Wow. Wow. Damn.

</details>

**主持人**: 但我认为金融这个聚焦点确实击中了很多人。

<details>
<summary>Original English</summary>

**Host**: But I think the finance focus is really hitting for folks.

</details>

**Evan Conrad**: 没错。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah.

</details>

**主持人**: 所以我们正在尝试细分。在这里，我们把所有东西都笼统地归入金融范畴。比如你的金融、他们的金融，连保险也算金融。但其实它们截然不同。

<details>
<summary>Original English</summary>

**Host**: So we're going to try to split up like this is Here we just lump everything in finance. Like your finance, their finance, like insurance is finance. But like they're all super different.

</details>

**Evan Conrad**: 是的。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah.

</details>

**主持人**: 所以未来我们可能会划分得更细致，因为有人想深入探讨对冲基金相关的内容，有人想深究银行或者个人财富管理，或者其他领域。

<details>
<summary>Original English</summary>

**Host**: So we'll probably break out things more minutely in in future because people want to go deep on hedge fund stuff or banking or personal wealth or

</details>

**Evan Conrad**: 确实，特别是在纽约这里。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah, especially in in New York.

</details>

**主持人**: 没错，比如 **Anthropic** 就说他们现在全心扑在 RIA（注册投资顾问）上。

<details>
<summary>Original English</summary>

**Host**: Yeah, like Entropic was like, yeah, we're we're all about RIAs right now. RIAs like registered investment

</details>

**Evan Conrad**: 是的。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes.

</details>

**主持人**: 这跟你们做的事情大相径庭。

<details>
<summary>Original English</summary>

**Host**: Like so different from you.

</details>

**Evan Conrad**: [笑]

<details>
<summary>Original English</summary>

**Evan Conrad**: [laughter]

</details>

**主持人**: 是的，我很清楚这种差异。

<details>
<summary>Original English</summary>

**Host**: Yeah, no, no, I'm uh I'm aware of this.

</details>

**Evan Conrad**: 对，对于不了解情况的听众，我们在两年前做过一期播客，当时你谈到了 **SF Compute** 处于什么阶段。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah, yeah, yeah. Um okay, so for listeners who don't know, uh we did a podcast 2 years ago where you talked about your your uh you know, where where SF Compute was.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**Host**: Mhm.

</details>

**主持人**: 而今天，你们在做**物理交割**（Physical Settlement）方面深入得多了。你谈到了你们的背板（Backplane）或者底层互联架构。

<details>
<summary>Original English</summary>

**Host**: Um today you're you're much more in this sort of physical settlements. You're talk you talk about your your back fabric or what do you call it?

</details>

**Evan Conrad**: 是底层背板（Backplane）。

<details>
<summary>Original English</summary>

**Evan Conrad**: Uh the backplane.

</details>

**主持人**: 没错，背板，这显然需要大量硬核的工程技术。针对两年前在播客中听过你们介绍的听众，你能介绍一下现在的 SF Compute 发展到什么阶段了吗？

<details>
<summary>Original English</summary>

**Host**: Backplane, which uh obviously like like takes a lot of hardcore engineering stuff. Um can you give a status update on like where is SF Compute versus listeners who last heard you on a podcast 2 years ago?

</details>

### 物理交割的演进

**Evan Conrad**: 当我们刚起步时，公司叫 Junnar，当时我们只是试图转租自己的 GPU 集群。我们是从技术栈切入的。打个比方，这就好比你在经营一家酒店，你试图把酒店房间卖出去。然后有人问你：“嘿，你能帮我打扫房间吗？”于是你说：“好吧，看来我除了房间，还需要保洁壁橱的权限。”于是你拿到了保洁壁橱。接着他们想要客房送餐服务，你就得拿到厨房的权限。然后他们需要安保，你就得拿到安保系统的权限，等等。

在某个时刻，你发现自己实际上是在经营整家酒店。当你真正掌控整家酒店的运营时，你才会意识到：“等等，我这个市场上的供应商，其实更像是一家基金，或者拥有数据中心资源的云厂商，而我们要提升层次。”

因此，我们在过去几年所做的，就是构建起一家云厂商完整的底层运营能力，以便真正能够以高可靠的水准交付算力。我们将其称为**物理交割**（Physical Settlement）。这个词借鉴自期货市场。

<details>
<summary>Original English</summary>

**Evan Conrad**: So when we started, we were this company called Junnar, and then we were just trying to sublease our cluster. Um and we started there in the technical stack. Um and a way to think about it is it's like you're in a hotel and you're trying to sell that hotel room. And then somebody asks you, "Hey, like are you going to clean my room?" And then you say, "Oh, I guess I probably also need the hotel room as well or like I need the um the cleaning closet." And so you go get access to the cleaning closet. And then they want room service, and so you get access to the kitchen. And then, you know, they want um security, and so you get access to the security closet, and you get this, and you do that, and you do this. And at a certain point, you're just running the whole hotel. Um and the moment you're running the whole hotel, you say, "Oh, wait a second. Um instead, my supplier on this market um is somebody that looks closer to a fund um or a cloud that has access in our case, a cloud that has access to the data center, and we're going to level up. And so what we spent the last several years doing is building the entire operating capacity of a cloud um in order to offer in order to actually deliver um the compute at a reliable level. Um we call that physical settlement. We're taking a term from

</details>

**Evan Conrad**: 比如在大宗商品期货市场中，无论是石油、大豆还是其他品种，物理交割意味着你必须真正收到那一桶桶原油或大豆。

<details>
<summary>Original English</summary>

**Evan Conrad**: the futures market futures markets, from other markets. Um where in, you know, oil or soybeans or something, physical settlement means you get delivered the oil and the soybeans.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Evan Conrad**: 但在某些市场中，比如石油以及电力市场，存在着一个具体的交付网络。在石油市场中，你必须拥有输油管道。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um but um in some markets, um like in oil and also in power, um there's like a delivery network. In oil, you have to have pipes.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Evan Conrad**: 对。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um

</details>

**主持人**: 对金融历史感兴趣的人都知道，在新冠疫情期间，国际原油价格一度跌至负数，因为储油空间耗尽，卖家宁愿倒贴钱求别人把原油运走。

<details>
<summary>Original English</summary>

**Host**: And and and for people interested in financial history, during COVID, oil went negative because uh so like I will pay you to take my oil.

</details>

**Evan Conrad**: 是的。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes.

</details>

**主持人**: 卖家会说：“我倒贴你钱，请你把我的油拉走。”

<details>
<summary>Original English</summary>

**Host**: And so I will pay you to take my oil.

</details>

**Evan Conrad**: 确实如此。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes. Um

</details>

**主持人**: 这就是物理交割带来的独特性质与奇特现象。

<details>
<summary>Original English</summary>

**Host**: That that is like the weirdness of physical settlement.

</details>

**Evan Conrad**: 没错，其他市场中也充斥着类似的特殊现象。比如在电力市场和电网中，存在输电线路容量受限和电网节点拥堵问题。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes. There's a bunch of weirdnesses like this in other markets as well. So in the power markets and the grid, um there's

</details>

**主持人**: 好的。听众可以去看你的演讲，你之前也录过几次播客。所以我今天想把对话拉到 201 甚至更深的技术与金融层面，而不是泛泛的 101 入门介绍；而且因为我曾经做过衍生品交易员，所以我能从大家通常不涉及的角度来展开探讨。

<details>
<summary>Original English</summary>

**Host**: Yeah. So uh people can refer to your talk and you've done a couple other podcasts already. Um so I want to be like the sort of 201 level instead of the 101 level short uh and also because I I am I have been a derivatives trader so I can give people a bit more detail that you normally don't get into.

</details>

**Evan Conrad**: 好的，没问题。

<details>
<summary>Original English</summary>

**Evan Conrad**: Okay.

</details>

### 算力流动性与标准化

**主持人**: 比如，今天的算力市场成熟度、深度和流动性究竟如何？

<details>
<summary>Original English</summary>

**Host**: Um so for example, well, how how mature or deep or liquid is the compute market today?

</details>

**Evan Conrad**: 坦白讲，还非常不成熟，缺乏深度，流动性也很弱。因此，我们一直在做的就是建立一个多维订单簿系统。

<details>
<summary>Original English</summary>

**Evan Conrad**: Uh not very mature or deep or liquid. Um so, what we've been doing is

</details>

**主持人**: 理解。我们上次交谈时，谈到了关于合同标准化的很多争议。

<details>
<summary>Original English</summary>

**Host**: Yeah, got it. And so, uh last time we talked as well, there was a lot of debate on standardization of contracts.

</details>

**Evan Conrad**: 对，我认为整体上对合同进行标准化依然是非常困难的。因为集群在性能上存在各种各样的衰减。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um so, I think standardizing the contracts in general is still pretty hard. There's all kinds of like performance degradation that clusters have.

</details>

**主持人**: 当你提到性能衰减时，是指类似 **MFU**（模型算力利用率，Model Flops Utilization）这类的指标吗？

<details>
<summary>Original English</summary>

**Host**: When you say performance degradation, are you talking like MFU type thing?

</details>

**Evan Conrad**: 它会直接影响 MFU。在这种具体情况下，我说的是 GPU 内核执行效率和网络传输瓶颈。

<details>
<summary>Original English</summary>

**Evan Conrad**: It will affect So, in this particular case, I'm talking about GPU kernel execution.

</details>

**主持人**: 明白了。

<details>
<summary>Original English</summary>

**Host**: Okay.

</details>

**Evan Conrad**: 最终的结果就是你拿到手的有效 MFU 变差了。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um the um uh that will basically the end result is that you get a worse MFU, but um like

</details>

**主持人**: 这属于中间层的损耗吗？

<details>
<summary>Original English</summary>

**Host**: Is the intermediate level

</details>

**Evan Conrad**: 基本上就是中间层产生的损耗。

<details>
<summary>Original English</summary>

**Evan Conrad**: intermediate level, basically.

</details>

**主持人**: 明白了。对于交易过大宗商品的人来说，比如原油有西得克萨斯轻质原油（**WTI**），它作为基准品，其他含硫油或者重质油会有相应的升贴水。大家都在寻找算力领域的基准等价物。

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah. So, so what I'm trying to So, for anyone who's traded commodities, like light sweet crude is the is the is the is the benchmark and then other types of crude degrade against it and then you just kind of adjust for that.

</details>

**Evan Conrad**: 没错，人们一直在试图建立这些等价折算标准。

<details>
<summary>Original English</summary>

**Evan Conrad**: Uh and so like people are trying to Well, you have to establish the equivalents

</details>

**主持人**: 建立这些维度的等价物。

<details>
<summary>Original English</summary>

**Host**: equivalents of those things.

</details>

**主持人**: 是的，我想知道目前这些标准是否已经确立了？

<details>
<summary>Original English</summary>

**Host**: Right, yes. And I'm wondering if they they have been established.

</details>

**Evan Conrad**: 我们采取的做法与众不同：我们构建了一个具备多维度属性匹配的订单簿系统。

<details>
<summary>Original English</summary>

**Evan Conrad**: So, what we did instead um was we created an order book that had multiple dimensions.

</details>

**主持人**: 明白。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Evan Conrad**: 对。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um

</details>

**主持人**: 这确实很麻烦，也很痛苦。

<details>
<summary>Original English</summary>

**Host**: It It sucks. Yeah.

</details>

**Evan Conrad**: 但从另一方面来看，这意味着存在大量的套利空间。

<details>
<summary>Original English</summary>

**Evan Conrad**: But, on the other hand, it means there's lots of arbitrage to make um

</details>

### 集群网络与硬件缺陷

**主持人**: 在这个多维矩阵中，最重要的维度有哪些？

<details>
<summary>Original English</summary>

**Host**: Okay. What dimensions matter in this grid of things?

</details>

**Evan Conrad**: 涉及很多不同的维度。其中一个核心维度是网络连接属性。很多算力集群之间并没有配置广域网（**WAN**）。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um so a bunch of different things. Um one is dimensions categories that is implemented with a WAN but

</details>

**主持人**: 大多数集群内部并没有跨区域的连接。

<details>
<summary>Original English</summary>

**Host**: most of these clusters don't necessarily have

</details>

**Evan Conrad**: 嗯。

<details>
<summary>Original English</summary>

**Evan Conrad**: um

</details>

**主持人**: 广域网连接。

<details>
<summary>Original English</summary>

**Host**: a wide area network.

</details>

**Evan Conrad**: 没错，广域网连接。也就是真正连接各个集群物理站点的长途光缆。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah a wide area network. So um basically cables that connect the clusters together.

</details>

**主持人**: 原来如此，所以这还取决于它们是属于哪一批次生产下线的硬件？

<details>
<summary>Original English</summary>

**Host**: Oh, so it's it's about like what cohort they were they were produced and and they pay more um, because for that

</details>

**Evan Conrad**: 比如首批下线的机架硬件可能会有一些缺陷或设计故障。

<details>
<summary>Original English</summary>

**Evan Conrad**: So, like uh, the first ones off the rack maybe had some faults or something.

</details>

**主持人**: 我猜这属于正常的工业制造规律：每一批次总有瑕疵品。

<details>
<summary>Original English</summary>

**Host**: I assume that sort of process is like, look, there's the defects every cohort.

</details>

**Evan Conrad**: 完全没错。

<details>
<summary>Original English</summary>

**Evan Conrad**: Totally.

</details>

**主持人**: 所以从台积电刚出厂运过来的新批次硬件总会出现一些状况。

<details>
<summary>Original English</summary>

**Host**: And so, like, you get it you get a new shipment off of from TSMC whatever, and you kind of pay for that.

</details>

**Evan Conrad**: [笑] 我来举个具体的例子。你描述的正是我们常说的集群“烤机预热”（Burn-in）过程。在集群点亮运行的早期阶段，某些节点会发生故障，你必须进行维修和 RMA（退货返修），替换新的硬件。经过这个阶段后，客户在实际使用中就不会再遭遇突发的硬件崩溃。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah, so [laughter] um, I'll I'll give an example. Um, you're describing burn-in. So, clusters will have like burn-in failures. Um and that's like you pay for that, but whatever, you'll get

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Evan Conrad**: 你会更换一批备件，随后客户就再也感受不到底层的硬件动荡了。

<details>
<summary>Original English</summary>

**Evan Conrad**: you'll get some back. Um and then the customer never has to experience that.

</details>

**主持人**: 没错。或者像 Cornelis 之前拿到那一批 **B200** 时遇到的情况一样。

<details>
<summary>Original English</summary>

**Host**: Yeah. Or Cornelis had this for like the the B200s that that that we got.

</details>

**Evan Conrad**: [笑]

<details>
<summary>Original English</summary>

**Evan Conrad**: [laughter]

</details>

**Evan Conrad**: 确实如此。各种各样的硬件问题都会在此期间暴露出来。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes, correct. So like different types of problems like this can happen.

</details>

**主持人**: 很有意思。不过相比于整个算力大盘，这些硬件磨合似乎还算局部问题。那么合同期限一般是多久呢？

<details>
<summary>Original English</summary>

**Host**: Interesting. Okay. So I'm okay, that seems small compared to the overall. What are the lengths of the contracts?

</details>

### 算力融资周期与现金流

**Evan Conrad**: 回答你的第一个问题，算力集群的主流租赁周期通常是 3 到 5 年。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um to answer your first question, um 3 to 5 years. Um

</details>

**主持人**: 哇，这么长。

<details>
<summary>Original English</summary>

**Host**: Wow.

</details>

**Evan Conrad**: 我们现在开始看到一些变化。

<details>
<summary>Original English</summary>

**Evan Conrad**: We're starting to see

</details>

**主持人**: 付款方式是按月、按季度还是怎样的形式？

<details>
<summary>Original English</summary>

**Host**: month by month or quarter by quarter or how's this?

</details>

**Evan Conrad**: 你是在问现金流的实际结算方式吗？

<details>
<summary>Original English</summary>

**Evan Conrad**: Are you asking what how the cash flow works?

</details>

**主持人**: 对，合同层面的现金流，比如远期期货合约是如何设定的？

<details>
<summary>Original English</summary>

**Host**: The the the the contracts. Like the few the futures contracts, right?

</details>

**Evan Conrad**: 在当前的大市场环境下。

<details>
<summary>Original English</summary>

**Evan Conrad**: In the in the market itself

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Evan Conrad**: 在更广泛的整个算力行业中。

<details>
<summary>Original English</summary>

**Evan Conrad**: um like is in the broader market.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Evan Conrad**: 整个集群的债务融资周期一般是 3 到 5 年。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um clusters are financed 3 to 5 years.

</details>

**主持人**: 明白了。

<details>
<summary>Original English</summary>

**Host**: Okay.

</details>

**Evan Conrad**: 所以相关的还款和支付。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um so the the

</details>

**主持人**: 付款也是在。

<details>
<summary>Original English</summary>

**Host**: The payments

</details>

**Evan Conrad**: 付款正是分布在这段漫长的时间周期内的。

<details>
<summary>Original English</summary>

**Evan Conrad**: are over that period of time.

</details>

**主持人**: 明白了。那么现在的指标价格是多少？比如 **H100** 的价格。

<details>
<summary>Original English</summary>

**Host**: Got it. And and what is the what is the index price? What is like the H100?

</details>

**Evan Conrad**: 目前没有单一的挂牌基准价格。它完全取决于租赁合同的期限长度。

<details>
<summary>Original English</summary>

**Evan Conrad**: There isn't one. It really depends on how long the contract is for.

</details>

**主持人**: 如果是按小时计算呢？比如大家常说的每小时几美元？

<details>
<summary>Original English</summary>

**Host**: Per hour. Like everyone talks about like dollar dollars per hour.

</details>

**Evan Conrad**: 即使按小时折算，也高度取决于你承诺锁定的总时长。

<details>
<summary>Original English</summary>

**Evan Conrad**: It really depends on the length of the contract.

</details>

**主持人**: 假设分别是一年期和三年期的合约呢？

<details>
<summary>Original English</summary>

**Host**: Let's say one year and three year.

</details>

**Evan Conrad**: 一年期和三年期的价格大约在每 GPU 小时 2 美元到 3 美元之间，目前的价格更倾向于接近 2 美元区间。

<details>
<summary>Original English</summary>

**Evan Conrad**: A one-year and a three-year are around between $2 and $3, probably closer to the $2 side right now.

</details>

**主持人**: 好的。如果是在现货（Spot）市场上呢？

<details>
<summary>Original English</summary>

**Host**: Okay. And on the spot market?

</details>

**Evan Conrad**: 你是想要实时现货还是带锁定期限的？

<details>
<summary>Original English</summary>

**Evan Conrad**: Uh, do you want real-time or do you want like

</details>

**主持人**: 比如按周或按月购买的灵活短租。

<details>
<summary>Original English</summary>

**Host**: Like a week or a month.

</details>

**Evan Conrad**: 那种价格会在每小时 2 美元出头，大致在 2 美元到 2.5 美元左右。

<details>
<summary>Original English</summary>

**Evan Conrad**: Like low 2s, like $2 to $2.50.

</details>

### 二级市场与转租机制

**主持人**: 那么现在存在违约或转租市场吗？比如某些公司融不到钱了或者算力闲置了。

<details>
<summary>Original English</summary>

**Host**: And is there a secondary market for bankruptcies or distressed leases?

</details>

**Evan Conrad**: 是的，现在市场上存在着转租需求，主要是针对违约提前解约的租赁合约。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes. There are secondary markets for breaking leases, basically.

</details>

**主持人**: 天呐。

<details>
<summary>Original English</summary>

**Host**: god.

</details>

**Evan Conrad**: 很多公司签了长期租约，但业务变化导致他们不得不转手。

<details>
<summary>Original English</summary>

**Evan Conrad**: or like for leases that are um

</details>

**主持人**: 我原本以为这些集群可以直接放在公开市场上竞价拍卖。

<details>
<summary>Original English</summary>

**Host**: Oh, I thought this was like a spot instance auction thing.

</details>

**Evan Conrad**: 这其实是两个不同的层面。

<details>
<summary>Original English</summary>

**Evan Conrad**: Oh, this is an ex- Both at different

</details>

**主持人**: 我觉得这太不可思议了。

<details>
<summary>Original English</summary>

**Host**: I I I It's I find it fascinating

</details>

**主持人**: 现在的算力究竟是以什么作为最小计价单位售卖的？很多人把算力比作电力，但电力的单位是度（千瓦时）。算力的计量单位到底是一个 GPU 运行一小时，还是生成的 Token 数量？

<details>
<summary>Original English</summary>

**Host**: how compute is sold right now. Everyone draws an analogy to electricity, but electricity is sold in kilowatt hours. The unit of compute today, uh, may be token hours or it may be GPU hours.

</details>

**Evan Conrad**: 事实上这两种形态同时存在。

<details>
<summary>Original English</summary>

**Evan Conrad**: Both exist.

</details>

**主持人**: 两种都在被广泛使用？

<details>
<summary>Original English</summary>

**Host**: Both exist, yeah.

</details>

### Token 与 GPU 小时定价

**Evan Conrad**: 好的，让我为你拆解一下这其中的逻辑。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um, okay, so

</details>

**主持人**: 请展开讲讲。

<details>
<summary>Original English</summary>

**Host**: Explain.

</details>

**Evan Conrad**: 当你在使用大语言模型进行推理时，底层依然是一台物理服务器在运转，它可能配置了 8 张卡，每张卡每小时成本比如是 2 美元。这意味着整台服务器每小时的运行成本大约是 16 美元。

<details>
<summary>Original English</summary>

**Evan Conrad**: If you're running inference, you have a box, that box has 8 cards in it, and it costs maybe $2 an hour per card, so the box costs $16 an hour.

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Evan Conrad**: 如果你在这台机器上跑 **Llama-3-70B**，它一秒钟大概能生成几百个 Token。如果这台服务器的利用率达到 100%，你可以算出一小时内它总共产出了多少个百万 Token（Mtok）。

<details>
<summary>Original English</summary>

**Evan Conrad**: If you're running Llama-3-70B, it generates maybe a few hundred tokens a second. If you utilize that box at 100%, you can calculate how many million tokens you produced in an hour.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Evan Conrad**: 将 16 美元除以生成的总 Token 数量，你就能精确得出每个 Token 的理论底准成本。但在现实中，几乎没有任何推理服务的 GPU 利用率能持续保持在 100%。

<details>
<summary>Original English</summary>

**Evan Conrad**: Divide that $16 by the number of tokens, and you get the baseline cost per token. But in reality, almost nobody runs at 100% utilization.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Evan Conrad**: 如果利用率只有 20%，那么每个 Token 摊销的实际硬件成本就会直接飙升 5 倍。

<details>
<summary>Original English</summary>

**Evan Conrad**: If your utilization is only 20%, your effective cost per token is 5x higher.

</details>

**主持人**: 确实如此。

<details>
<summary>Original English</summary>

**Host**: Totally.

</details>

**Evan Conrad**: 这就是为什么**按 Token 付费**（API 模式）和**按 GPU 租用**之间存在天然的转换套利关系。对外售卖 API 的推理厂商承担了利用率波动风险，因此他们必须在单位 Token 价格里计入风险溢价。

<details>
<summary>Original English</summary>

**Evan Conrad**: That's why there's a spread between paying per token versus renting the dedicated GPU. Inference providers take on utilization risk, so they price that risk into the tokens.

</details>

**主持人**: 任何模型都适用这种套利吗？

<details>
<summary>Original English</summary>

**Host**: Any model?

</details>

**Evan Conrad**: 基本上任何主流开源或私有模型都是这个逻辑。

<details>
<summary>Original English</summary>

**Evan Conrad**: Any model, basically. Um

</details>

**主持人**: [笑]

<details>
<summary>Original English</summary>

**Host**: [laughter]

</details>

**Evan Conrad**: 所以如果你能够将集群打满，自建集群跑推理会极其便宜；但一旦利用率跌落，成本就会反噬。

<details>
<summary>Original English</summary>

**Evan Conrad**: and so that's if you use it at full capacity, self-hosting is very cheap, but if utilization drops, it bites you.

</details>

### 芯片迭代与推理经济学

**主持人**: 那么芯片的世代更迭会带来什么影响？比如大家不仅关心算力（FLOPs），也非常关心显存带宽和容量。

<details>
<summary>Original English</summary>

**Host**: How do generational shifts impact this? People don't just care about raw compute, they care about memory bandwidth and memory capacity.

</details>

**Evan Conrad**: 没错，不同世代的芯片在架构上有质的飞跃。

<details>
<summary>Original English</summary>

**Evan Conrad**: Totally. Different generations of chips have different architectures.

</details>

**主持人**: 你指的是比如从 **B200** 到 **B300** 这一代？

<details>
<summary>Original English</summary>

**Host**: So, like B300 generation. Yeah.

</details>

**Evan Conrad**: 是的，比如 B300 拥有更高的显存容量，这允许你在单节点上加载更大参数规模的模型或容纳更长的上下文窗口。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah, like B300 has much more memory capacity, which allows you to fit larger models or much larger context windows per node.

</details>

**主持人**: 但你刚才提到有些客户只在乎成本。

<details>
<summary>Original English</summary>

**Host**: But you just said you care about memory and other stuff.

</details>

**Evan Conrad**: 确实如此，并不是所有客户的需求都相同。有些客户只跑特定任务，他们的优化瓶颈在于单卡吞吐量，只要每小时价格足够便宜，他们就愿意租用上一代芯片。

<details>
<summary>Original English</summary>

**Evan Conrad**: Totally, but not every customer does. So some customers like just care about throughput for a specific workload, and as long as the price is cheap enough, older chips work fine.

</details>

**主持人**: 明白了。

<details>
<summary>Original English</summary>

**Host**: Okay.

</details>

**Evan Conrad**: 这正是我们平台的价值所在。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um and that's what we do.

</details>

### 对冲与物理交割的必要性

**主持人**: 所以用户可以通过你们的 API，以可编程的方式定义自己所需的集群规格？

<details>
<summary>Original English</summary>

**Host**: So and so people use your APIs to programmatically define what they want?

</details>

**Evan Conrad**: 是的，目前我们正在推出结构化命名查询功能，让用户可以通过声明式配置来获取算力。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes. Um with the caveat that having a named query is a new thing we're rolling out.

</details>

**主持人**: 非常有趣。那么在金融机制上，为什么你们坚持要做物理交割，而不是像其他金融机构那样纯粹做**现金结算**（Cash Settlement）？

<details>
<summary>Original English</summary>

**Host**: Okay. Interesting. Um all right. So why the insistence on physical settlement versus pure cash settlement?

</details>

**Evan Conrad**: 核心在于：如果没有物理交割作为基础锚点，金融市场的价格发现就会完全脱离实际。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um mainly just the requirement for physical settlement. Um we think that without physical delivery, prices detach from reality.

</details>

**主持人**: [笑]

<details>
<summary>Original English</summary>

**Host**: [laughter]

</details>

**Evan Conrad**: 我们今天整个对话的核心其实就是：算力资产必须能够被真实交付并投入生产。

<details>
<summary>Original English</summary>

**Evan Conrad**: And um our entire conversation today is um that these things have to be real capacity you can actually take delivery of.

</details>

**主持人**: 能够真实地买到并调用底层算力容量。

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. You can actually buy the capacity for.

</details>

**主持人**: 这就像电影《大空头》（The Big Short）里展现的合成资产，如果纯粹做现金结算，脱离了真实抵押品，风险就会被无限放大。

<details>
<summary>Original English</summary>

**Host**: Yeah. So for listeners, this is like synthetic CDOs in The Big Short, where cash settlements are just side bets on an index.

</details>

**Evan Conrad**: 没错，纯现金结算就像是在场外对指数进行赌博，它可能跟底层物理硬件毫无关联。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah. And basically cash settlements can be side bets that may or may not have anything to do with actual hardware.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**Host**: Mhm.

</details>

**Evan Conrad**: 澄清一下，我们并不是认为现金结算未来没有价值，而是认为在没有确立稳固的物理交割机制之前，纯现金结算市场根本立不住脚。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes. Yeah. So, to be clear, we think cash settlement as a future derivative has a place, but trying to do cash settlement before you can physically deliver is backwards.

</details>

**主持人**: 就像人们炒作初创公司的影子股权一样，很多人在未上市公司上市前就去炒作各种衍生赌注。

<details>
<summary>Original English</summary>

**Host**: People do that for all sorts of things, including startup stock.

</details>

**Evan Conrad**: 是的。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes.

</details>

**主持人**: 你可以买卖虚构的股权份额，但背后并没有真正的股票交割。

<details>
<summary>Original English</summary>

**Host**: Right? Like you can buy and sell a made-up share, but you don't actually own the underlying asset.

</details>

**Evan Conrad**: 没错，很多这种交易最后的结局都非常惨烈。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes. And lots of those go very poorly. It would be bad if compute markets ended up like that.

</details>

### 基准利率与操纵风险

**主持人**: 我以前是做外汇和利率衍生品交易的，这让我想到了曾经轰动一时的 **LIBOR**（伦敦银行间拆借利率）操纵丑闻。如果算力指数依赖于几家大厂自报的数据，三年后这个指数是否还会失去公信力？

<details>
<summary>Original English</summary>

**Host**: Well, so, I used to be a currency trader. Think about the LIBOR scandal. Is a self-reported compute index even meaningful, or will it be manipulated?

</details>

**Evan Conrad**: 关键就在于：LIBOR 之所以被操纵，是因为它不是基于真实撮合的交易，而是几家银行每天提交的估算报价。

<details>
<summary>Original English</summary>

**Evan Conrad**: So, critically, LIBOR was manipulated because it was based on quotes, not actual trades.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Evan Conrad**: 我们的担忧正在于此。如果仅仅收集各家云厂商的公开报价来生成算力指数，就会重蹈覆辙，造成严重的市场操纵。

<details>
<summary>Original English</summary>

**Evan Conrad**: Well, our concern is there's a very similar problem where you can just fabricate numbers if there is no physical trade clearing behind it.

</details>

**主持人**: 12 家银行坐在一起商量数字。

<details>
<summary>Original English</summary>

**Host**: 12 banks. Yeah.

</details>

**Evan Conrad**: 没错，那正是问题的根源。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yes.

</details>

### 市场生态与竞争格局

**主持人**: 市场上现在还有其他玩家，比如 Silicon Data、Compute Exchange，以及高频量化巨头 Jump Trading。你能区分一下你们与这些玩家的路线差异吗？

<details>
<summary>Original English</summary>

**Host**: Ooh. So, we're big fans of Silicon Data and Compute Exchange. And SemiAnalysis mentioned Jump. Can you distinguish your different paths?

</details>

**Evan Conrad**: 总体来说，他们主要聚焦于做金融现金结算，而我们专注于构建**物理交割网络**。

<details>
<summary>Original English</summary>

**Evan Conrad**: So, the general gist is they're doing cash settlement, we're doing physical settlement.

</details>

**主持人**: 在一个健康的生态系统里，既需要买方和卖方，也需要承保**资产残值险**（Residual Value Insurance）的金融机构。

<details>
<summary>Original English</summary>

**Host**: I think effectively what you want in this ecosystem is buyers and sellers, and then residual value insurance.

</details>

**Evan Conrad**: 对，资产残值保险是极其关键的一环。

<details>
<summary>Original English</summary>

**Evan Conrad**: Uh residual value insurance.

</details>

**主持人**: 拥有一个完善的生态系统至关重要。而你们显然在死磕物理交割这一硬骨头工程。

<details>
<summary>Original English</summary>

**Host**: And we want this healthy ecosystem out there. But you guys are owning the problem of physical settlement.

</details>

**Evan Conrad**: 是的。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah.

</details>

### 极致工程与技术架构

**主持人**: 你们为了解决物理交割，招募了一群极其顶尖的技术大牛。能描述一下你们的技术架构（Stack）吗？

<details>
<summary>Original English</summary>

**Host**: And you are also hiring extremely cracked engineers. Describe your stack.

</details>

**Evan Conrad**: 我们做了传统云厂商所做的一切重资产运营与自动化调度工作，但我们自身并不将自己定位为传统意义上的云。我们与各大服务器 OEM 厂商直接对接，确保硬件准时交付并快速上架点亮。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um, we do all the things the cloud does without being the cloud. We work directly with OEMs to ensure that things get delivered on time, and handle all the provisioning.

</details>

**主持人**: 这些全部是由你们 SF Compute 的全职员工亲自完成的吗？

<details>
<summary>Original English</summary>

**Host**: you as an SF Compute employees?

</details>

**Evan Conrad**: 是的，全部由我们的团队主导。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah.

</details>

**主持人**: 哇，太厉害了。

<details>
<summary>Original English</summary>

**Host**: Wow.

</details>

**Evan Conrad**: 当你从传统云厂商购买裸机节点时，很多底层的硬件调优和网络拓扑管理实际上是黑盒。而我们在数据中心内部署了完整的控制面，管理光纤互联、监控网络抖动，并实时自动化隔离故障节点。

<details>
<summary>Original English</summary>

**Evan Conrad**: All right. When you buy a node from a cloud, there's a lot hidden. We manage the physical topology, the optics, the fabric configuration, and automatic health remediation.

</details>

**主持人**: 传统数据中心的作用主要是提供电力和散热风道，而你们则是在这个基础上把所有计算硬件和网络基础设施完全软件化、自动化。

<details>
<summary>Original English</summary>

**Host**: Because traditionally the job of the data center is to extend power and cooling. You guys do everything above that.

</details>

**Evan Conrad**: 没错，我们就是负责打通从数据中心物理空间到可用算力之间所有层面的团队。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah. We're the ones that do that.

</details>

**主持人**: 明白。所以你们并不是在做买地建楼的数据中心重资产物业投资？

<details>
<summary>Original English</summary>

**Host**: Okay, all right. But you're not in the real estate data center business per se.

</details>

**Evan Conrad**: 我们不搞土建地产。我们提供的是**超级计算即服务**（Supercomputing as a Service）。无论底层硬件放置在哪个合作数据中心，我们都能为客户提供统一标准的超级计算交付能力。

<details>
<summary>Original English</summary>

**Evan Conrad**: We're not in the concrete data center business. What we do is offer supercomputing as a service. We turn raw infrastructure into high-performance compute clusters.

</details>

**主持人**: 有人把你们的模式比作是算力基础设施领域的 Palantir。

<details>
<summary>Original English</summary>

**Host**: Yeah, someone once described us as like Palantir for compute.

</details>

**Evan Conrad**: 是的，有人确实这么形容过。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah, someone once described us as like um uh like Palantir for compute.

</details>

**主持人**: 你们的部署主要是在美国境内吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh and primarily the US?

</details>

**Evan Conrad**: 目前主要集中在美国，但我们已经在全球范围内交付和运营集群。

<details>
<summary>Original English</summary>

**Evan Conrad**: Primarily the US, but we operate around the world.

</details>

**主持人**: 未来的某一天，SF Compute（旧金山算力）这个名字会不会变得名不副实？因为你们早已走向全球。

<details>
<summary>Original English</summary>

**Host**: Yeah. At some point does SF Compute become a misnomer?

</details>

**Evan Conrad**: [笑] 实际上，当我们在全球各地部署集群时，SF（旧金山）所代表的顶级 AI 技术品牌依然具有极高的市场号召力。我们正在让全球的算力资产变得具备金融流动性，让它们能够被安全融资。

<details>
<summary>Original English</summary>

**Evan Conrad**: [laughter] So, we're deploying clusters all around the world, and when we do that, we make that compute financeable.

</details>

### 利益博弈：巨头为何无法下场？

**主持人**: 回到我们开头的核心问题：英伟达毫无疑问是行业主宰，还有 CoreWeave、Lambda、Crusoe 以及几大巨头云厂商，为什么这些行业巨擘无法自己建立这样的算力期货市场？

<details>
<summary>Original English</summary>

**Host**: Nvidia is obviously like the 800-lb gorilla in the room. Why don't they Why didn't they make SF Compute? And again, let's get into the incentives of multiple players.

</details>

**Evan Conrad**: 关键在于各方的**利益激励结构**（Incentives）。

英伟达虽然能从这个市场的存在中获取巨大的宏观红利——因为市场流动性越强，金融机构越敢贷款给客户买 GPU——但英伟达自己绝对不能坐庄做交易所。因为一旦英伟达成为裁判，各家买方和卖方就不会信任这个平台的中立性。如果缺乏公信力与中立性，就不会有真实活跃的交易，贷款银行也就不会认可该市场的远期定价作为抵押融资依据。

同理，**CoreWeave**、**Lambda**、**Crusoe** 乃至各大超大规模云厂商（Hyperscalers）也做不了这个平台；做推理层的 **Modal**、**Fireworks**、**Base10** 也做不了。因为他们本身就处于供需博弈的一端，身上背负着沉重的直接销售压力和算力采购需求。要想做一个中立的算力交割与交易市场，你必须主动放弃直接向终端大客户转售算力获取暴利的机会。要构建这个平台，你必须先杀死自己做传统云转售的业务模式。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah, so our impression is that Nvidia can't make it but benefits tremendously from it existing. The reason why they can't make it is because they would then not be independent enough for people to trade on it. If you don't trade on it, then you don't have enough liquidity for lenders to finance against the forwards market. This is also why Crusoe and Coreweave and Lambda why the hyperscalers can't make it, why Base10 and Fireworks and Modal can't make it cuz they have too much demand on that side. Um this is the thing that benefits the entire industry because it makes the financing costs go down. But nobody can make it unless they give up the ability to do all the big inference money and all the big cloud deals. You have to kill your business in order to make this.

</details>

**主持人**: 没错。他们在结构上天然存在利益冲突，不可能成为中立的交易基础设施。而你们所做的是消除摩擦，促成交易流动。你们最近公布了一些重要的里程碑数据，能跟我们分享一下吗？

<details>
<summary>Original English</summary>

**Host**: Mhm. That's why nobody does it. It's like structurally they're not set up to do that. And you're basically reducing friction and that's all your revenue. You've announced some milestones. Can you repeat what they are?

</details>

### 可编程数据中心

**Evan Conrad**: 我们已经达成了数亿美元的交易撮合规模，并且有大量全新集群正在密集交付中。

但更让我兴奋的是我们在底层工程上推出的重磅功能。例如，我们现在允许客户在不向我们提交工单申请的情况下，**动态重新切分与划分子网内的 InfiniBand 架构**（Dynamic Subdividing）。

在绝大多数传统云厂商那里，你购买一个集群后，他们只会给你分配一个固定的 InfiniBand Fabric。如果你希望重新划定网络边界，你必须发邮件提工单，等待工程师手动调整。而在 SF Compute，我们的客户可以通过代码按需实时、动态地重划 Fabric 拓扑。这完美契合了算力交易市场的本质需求：当你要在市场上快速扩容或缩容集群规模时，物理底层必须能够瞬间软件定义并随之调整。

<details>
<summary>Original English</summary>

**Evan Conrad**: Uh, we closed several hundred million dollars of volume. Um, we have a significant number of new clusters on the way. Um, and then the things that I think I'm most excited about um, is we've um, shipped a whole bunch of new features um, that make SF Compute very viable for platform as a service companies. Um, an example is um, we allow customers to subdivide their InfiniBand fabric um, without having to ask us. So, many clouds when you go to buy them, they will give you one InfiniBand fabric. Um, and then if you want to re redraw the lines of that InfiniBand fabric, uh, you need to contact them and they will then do something for you. Um, we now can do that on the fly for customers um, which I think is really great um, because it interfaces with the market really well um, where you want to be able to redraw things in order to scale up and down your clusters.

</details>

**主持人**: 这听起来就像是你们把整个物理数据中心虚拟化并让它完全**代码可编程化**（Programmable Data Center）了。

<details>
<summary>Original English</summary>

**Host**: Um, would you describe this as like you're virtualizing the data center and making it programmable?

</details>

**Evan Conrad**: 没错，我们正是把数据中心完全虚拟化，并使其成为一个可编程的基础设施。过去你只有在完全拥有物理硬件时才能获得的高级底层控制权，我们现在全部将其软件化、抽象化交付给用户。

<details>
<summary>Original English</summary>

**Evan Conrad**: Yeah, we're virtualizing data center and making it programmable. So, all the stuff that you would have gotten if you had owned the hardware, we're trying to virtualize that um, which I think is um, exciting to us.

</details>

**主持人**: 上一次行业发生这种变革还是云计算诞生初期，当时是将虚拟机（VM）全面可编程化。这太酷了！最后，给想要拥有集群的用户做个一句话推介吧。

<details>
<summary>Original English</summary>

**Host**: It's funny like the last time this happened was like the cloud. Which is really cool. Finally, what's your pitch to the ecosystem?

</details>

**Evan Conrad**: 如果你想购置并拥有一组 GPU 集群，但又担心未来资产残值暴跌的风险；或者当你中途发现训练计划变更、必须提前退出集群合同时，我们可以立即在市场上帮你把多余的算力集群转售给第三方，从而让你的资产负债表免受减值冲击。

<details>
<summary>Original English</summary>

**Evan Conrad**: Um, if you would like to own a GPU cluster and you want the residual value from that cluster hedged, or if you found out that that was a bad idea, that you need out of that cluster, we can immediately sell that cluster to someone else so it doesn't hit your balance sheet.

</details>

**主持人**: 非常简洁有力的商业诉求！Evan，非常感谢你抽出宝贵的时间。你正在为整个 AI 行业构建一项至关重要的基础设施，作为你的朋友，我感到非常荣幸。

<details>
<summary>Original English</summary>

**Host**: Very simple pitch. Well, thank you so much for your time. You're doing a great service to the industry and I just am happy to be your friend.

</details>

**Evan Conrad**: 非常感谢你的认可！

<details>
<summary>Original English</summary>

**Evan Conrad**: I appreciate it.

</details>

**主持人**: 好的，今天的播客到此结束！

<details>
<summary>Original English</summary>

**Host**: All right. That's it.

</details>

**Evan Conrad**: [片尾音乐]

<details>
<summary>Original English</summary>

**Evan Conrad**: [music]

</details>