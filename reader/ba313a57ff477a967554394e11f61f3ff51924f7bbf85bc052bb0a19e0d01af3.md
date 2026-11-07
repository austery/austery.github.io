---
author: 硅谷101
date: '2026-11-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xzc99JOBMlY
speaker: 硅谷101
tags:
  - data-center
  - power-generation
  - debt-financing
  - compute-capacity
  - infrastructure
title: 硅谷101圆桌：AI数据中心融资、电力瓶颈与算力短缺
summary: 嘉宾探讨了AI数据中心的电力供给瓶颈，指出电网输电受阻正促使30%至50%的新规划转向表后发电，并分析了建设延期风险、租期错配与高杠杆融资趋势，预测算力短缺或持续至2030年。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - GMI Cloud
  - Bloom Energy
  - SpaceX
  - Anthropic
  - General Electric
products_models: []
media_books: []
status: evergreen
---
### 开场与嘉宾介绍

**>>**: 哇，我们这里几乎座无虚席了。所以，如果你在周日早上大概9点40分来到这里，我想你要么是真的热爱数据中心，要么就是嗅到了金钱的味道。不管怎样，你都来对房间了。而且我们在这方面有着很好的记录。伊森（Ethan）和我去年在同一个小组讨论中探讨了数据中心，我们得出的结论归结为一句话——不知道大家是否还记得——那就是“数据中心是新时代的石油”，对吧？如果你们在过去一年里相信了这一点，并看好数据中心和新型云服务，你们在股市上的投资可能已经翻倍了。不用谢。所以今年，我们会确保这个小组讨论像去年一样富有见地，甚至按照陈（Chen）的要求，更加犀利。好的，那我们先做一下自我介绍吧。
<details><summary>Original English</summary>
**>>**: Foreign. Wow. We almost got a full house. Uh so if you are here um at like like 9:40 on a Sunday morning I guess you are either really love data center or you just smell money and either way you're in the right room and we had great track record for that Ethan and I we were on the same panel last year talking about data center and our conclusion uh came down to one line is um I don't know if you still remember was that data centers are the new oil, right? And if you guys were um believed in that and bullish about data center and new cloud for the past year, you probably have already doubled your money on stock markets. Um you're welcome. So this year uh we'll make sure the panel is as insightful as last year and even spicier as Chen required. So okay, so let's start with some introductions.
</details>

**>>**: 好的，当然。大家好，我叫伊森（Ishing/Ethan），目前在谷歌工作，负责谷歌的数据中心规划和能源战略。此前我在微软、字节跳动工作，也是负责类似的能源战略，以支持全球数据中心的超高速增长。在此之前，我曾在突破能源（Breakthrough Energy）工作，专注于清洁能源转型等领域。我在数据中心和能源方面有些经验，一直支持这些科技公司实现超高速扩张，建设全球吉瓦级规模的数据中心。很高兴见到大家。
<details><summary>Original English</summary>
**>>**: Uh sure. Uh hi everyone my name is uh Ishing and uh I'm currently working at Google and in charge of Google's data center planning and energy strategy and previously I work at Microsoft by dance also in charge of a similar energy strategy to support the uh very fast growth of data centers uh globally and uh before that I worked at breakthrough energy focusing on the clean energy transition etc. had uh some experience in data center and energy and have been supporting these tech companies to grow fa very fast. They are uh gigger uh what scale of uh data centers worldwide. Uh nice to meet everyone.
</details>

**>>**: 谢谢。谢谢邀请我们，也谢谢大家起得这么早。希望在这场讨论结束时能让大家觉得不虚此行。我们会讨论很多有趣的内容，祝大家听得愉快。接下来请亚历克斯（Alex）做自我介绍，我对你有很多问题想问。
<details><summary>Original English</summary>
**>>**: Uh thank you. Thank you for having us here and thank you for getting up so early. Hopefully it pays off at the end of this panel. Uh we're going to discuss a lot of like interesting stuff and uh just enjoy. and Alex. Uh, let's start with some introductions and I have lots of questions for you.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Sure.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 大家好，我叫亚历克斯（Alex），是GMI Cloud的创始人兼CEO。GMI代表通用机器智能云（General Machine Intelligence Cloud）。我认为我们正在迈向通用机器智能时代，这不可避免。所以我的使命，也是公司的使命，就是加速每个人的采用步伐，不仅是前沿实验室或超大规模企业，而是任何想使用AI的人。因此，我们在全球范围内构建了从亚洲到美国的基础GPU基础设施，以及面向不想管理裸金属设备的用户的Kubernetes管理层，还有我们的Token工厂，目前每天处理超过一万亿个Token。
<details><summary>Original English</summary>
**>>**: Yeah. So, my name is Alex. Uh, founder and CEO of GMI cloud. GMI stands for general machine intelligence cloud. I believe that we're moving into the general machine intelligence age. I think this is in inevitable. And so my my mission also the company's mission is to accelerate adoption for everyone not just frontier labs or hyperscalers but for everyone that wants to utilize AI. So we built foundational GPU infrastructure across the world from Asia to US uh as well as our Kubernetes management layer uh for people who doesn't want to manage bare metals as well as a uh token factory which right now uh we're processing about a trillion plus token per day.
</details>

### 电力瓶颈与表后发电转向

**>>**: 好的，那我就先从你开始问。记得去年你提到了数据中心的瓶颈在于能源，对吧？尤其是输电，然后是发电。那么对于过去这一年，你觉得情况还是那样吗？发生了什么变化？
<details><summary>Original English</summary>
**>>**: Okay. Uh yes and I'll start with you. Um because remember last year you mentioned the bottleneck uh of data centers energy right and especially the transmission and then generation uh what do you think about like for the past the past year right um is it still the same what changed
</details>

**>>**: 是的，这是个很好的问题。我认为去年我们讨论了美国缺乏足够的电力来支持超大规模数据中心的快速增长。主要的瓶颈是输电系统，也就是大家在公路沿线看到的高压输电线路，用来把电从发电端一路输送到数据中心。我认为在过去一年里，很多人意识到一个非常残酷的事实，那就是美国几乎不可能建设大规模的输电系统。所以几乎所有人都放弃了解决这个问题。于是他们转向解决另一个问题：如果我们不能建设相当于公路的输电线路，那么直接在数据中心园区就地发电怎么样？所以我认为这就是为什么在过去的12个月里，很多所谓的现场自备发电（on-site generation）或所谓的表后发电（behind the meter）被选作解决数据中心电力问题的方案。我看到的一些数据表明，今年规划的数据中心里，大概有30%到50%——意思是也许在一两年内会投入运营的规划数据中心——大约30%到50%采用的是表后发电方案。这意味着需要大量的天然气轮机，包括大、中、小型轮机，尤其是小型轮机，因为像通用电气（General Electric）的大型天然气轮机已经提前售罄多年了，所以小型轮机成了市场上的热门产品。此外，如果你关注股市的话，有一家叫Bloom Energy的公司今年非常火爆，主要是……
<details><summary>Original English</summary>
**>>**: yeah that's a great question I think uh last year we talk about for United States we don't have sufficient uh electric power to support the very fast and large scale data center growth uh the The main bottleneck is transmission system uh which is the you can think of it as the high voltage transmission lines you see along the highways to deliver electricity from the generation all the way to the data center. I think in the past year a lot of people realized a very cruel kind of fact which is United States is almost impossible to build a large scale transmission system. So almost everyone gave up on that on solving that problem. So they pivoted to solve another problem which is if we cannot build transmission which is kind of a similar like the highway right uh if we cannot build highway how about just build the the generations directly at your data center campus so I think this is why the past 12 months a lot of uh the so-called on-site generation or so-called behind the meter uh generations uh is picked as the solution to solve the data center uh electricity problem. I think some of the data I saw is that uh roughly maybe 30 to 50% of the uh this year's planned data set data centers meaning that maybe in in one or two years they will become alive but plan data centers roughly 30 to 50% of them are behind the meter uh generation uh solution uh meaning that uh a lot of natural gas turbines large medium and small turbines especially small turbines because we want to like General Electrics large gener gas turbines has already been sold out for many years and so the small ones becomes the the the kind of a hot products in the market and also uh if you uh uh kind of uh follow the stock markets there's one company called the bloom energy uh becomes very hot this year uh mainly
</details>

**>>**: 大家记得做好笔记。
<details><summary>Original English</summary>
**>>**: make sure you take notes
</details>

**>>**: 是的，主要是因为他们提供快速通电（speed to power），意味着他们能切实帮助你在几个月内——比如3到6个月内，有时他们甚至声称能在60天内——让现场发电上线。这成为了非常热门的表后方案。但当然，他们也有其他挑战，比如供应链挑战，以及他们的技术对于所有数据中心而言是否足够成熟。目前它们仍处于小规模阶段，所以仍然存在相关风险。然而，有些公司正在认真考虑这个方案，其中一些人认为这可能是数据中心的一大解决方案。不过还是要保持谨慎，这仍是新技术。但这正是人们正在思考的如何解决数据中心能源问题的途径之一。所以我想说，今年一个巨大的转变就是大家放弃了解决输电问题，转而专注于解决现场或表后发电问题。
<details><summary>Original English</summary>
**>>**: yeah mainly because they are providing uh speed to power meaning that they can really help you get the on-site generation online within several months like within 3 to 6 months and sometimes they claim they can do it within 60 days. uh and that becomes a very hot solution which is behind the meter. But of course they do have other challenges right like supply chain challenging and also whether their technology is mature enough for all the data centers right now they are still small scale so there are still risk associated with that. However they are companies who is seriously thinking about this solution and some of them think this could be one of the big solution for data centers. uh but again remain cautious this is still new new technology but this is one of the uh things people are thinking about like how to solve the energy problem for uh data centers so I would say this year a big shift is that the people gave up on solving the transmission problem but focusing on solving the onsign or behind the meter generation problem now
</details>

**>>**: 好的，关于Bloom Energy，我知道很多新型云服务商使用这项技术，超大规模企业也是这样吗？
<details><summary>Original English</summary>
**>>**: okay on the bloom energy I know lots of new cloud use this technology is it also same with the hyperscalers that okay
</details>

**>>**: 是的，确实如此。
<details><summary>Original English</summary>
**>>**: yeah that's true
</details>

### 供应链短缺与物理建设瓶颈

**>>**: 好的。布鲁斯（Bruce），我相信你在AI数据中心和能源的不同环节都有投资。那么你认为瓶颈在哪里，最令人担忧的是哪个部分？
<details><summary>Original English</summary>
**>>**: okay so Bruce I'm sure you invest uh in different parts of the AI data center and energy. So where do you think is the bottleneck and which part worries the most? Um yeah
</details>

**>>**: 事实上，整个AI供应链——包括能源在内——都严重短缺。为数据中心供电是一个大问题，而且这不仅关乎设备。因为在美国，我同意伊森的看法，在这次AI建设潮之前，美国的基础设施原本就没那么完善。但它也有自己的优势，天然气就是其中之一。所以实际上我完全同意表后发电是解决方案，只是建设起来需要时间，而且你需要像通用电气（GE）、西门子能源（Siemens Energy）这类大厂的设备。此外你还需要物理实体资源，比如施工、劳动力、许可证，所有这些都是我们在接下来的中期阶段必须面对和解决的瓶颈，对吧？像得克萨斯州、弗吉尼亚州、俄亥俄州，它们都面临着所有这些挑战。我们是否有许可证，是否有当地社区的支持来建设所有这些宏伟的数据中心？这些都是我们未来必须注意的事情。我依然非常乐观，因为归根结底这关乎权衡。当你建造新事物时，必然会对当地社区产生积极和消极的影响。因此，所有的超大规模企业和新型云服务商都必须证明自己能实现双赢，而不仅仅是把所有资源占尽。我认为大趋势的发展方向是正确的。总而言之，所有这些都是我们必须面对的切实挑战，但人们正在寻找解决方案。这就是我们的现状，所以我们保持投资。
<details><summary>Original English</summary>
**>>**: well uh as a matter of fact actually the whole AI supply chain energy included is all we we are in shortage uh significantly and uh uh data center uh you know power to data center is a big one and it's not only about the equipments because in the US I agree with Ethan and uh uh uh just US infrastructure was not that good before this boom of AI built out uh but it also has its own like uh you know advantage natural gas is the one. So actually I fully agree you know behind the meter is the solution and it just takes time to build it out and you need equipments like from like the names like GE Simmons energy stuff like that you also need physical stuff you know constructions labor permits all those things those are all the bottlenecks we have to deal with and and solve this coming midterms right and uh uh uh uh states like Texas, Virginia, Ohio they all facing all the challenges right and do we have do we have the permits do we have the local community support to build out all those ambitious like data centers those are the things we have to pay attention going forward and uh I remain like very optimistic because in the end it's all about like it's a trade-off of course you know the uh when you build something new it's going to have like a pos both positive and negative you know uh impact on the local communities so the all the hyperscalers neural cloud they have to prove they can make it as win-win rather than just you know oh I take everything up I I I say the you know the the direction of travel uh it's it's it's to the right directions so uh all those things again to summary it up all those are the challenges real challenges we have to face but and the people have solutions yeah so that's where we are so we stay invested yeah
</details>

**>>**: 好的，我能看出来大家都非常看好AI，持积极乐观的态度。做一个快速的直觉判断：如果必须选出一个目前最紧缺的环节，是GPU、网络、内存还是电力？你会选什么？
<details><summary>Original English</summary>
**>>**: okay um I can tell that we are all very AI peeled kind of positive and bullish. Um, just one quick gut check. If you have to pick like uh one thing that really most short of right now, it's a GPU, it's like a networking, a memory, power, um, what would you pick?
</details>

**>>**: 好的。正如我所说的，所有东西都极其短缺，只是程度不同。GPU、内存，甚至是底层设备、基板等等所有东西，包括MLCC（片式多层陶瓷电容器），台湾公司从这些短缺中受益良多。所有这些物理实体层面的东西，就是需要时间去建设出来。如果非要选一个方向，随着智能体（agency）的兴起，大家现在关注的不仅是CPU算力，过去GPU与CPU的比例通常只是一比一，现在已经低于四比一，有些人甚至乐观地看好八比一左右，所以你能看到巨大的潜力。但我想表达的一点是，我们需要保持一点创造力和开放的心态，现在处于非常早期的阶段，这是一个做大蛋糕的故事，而不是谁赢谁输。整个蛋糕都在变大，这是我希望大家关注的一个方面。其次，这也关乎技术优势。你们是这方面的专家，你们为超大规模企业所做的所有半导体项目，与过去所做的有着根本的不同。这也会创造出赢家和输家。比如功率半导体过去是非常无聊、强周期性的东西，但现在鉴于GPU和CPU消耗更多电力、使用更高电压，它变成了一个非常令人兴奋的领域，我们正在关注它。所以这是个激动人心的时刻，这就是我想说的。有时候你不需要非得去选到底是看好GPU还是CPU、内存还是光模块。我深信，从宏观格局来看，这是一个不断扩大的蛋糕。
<details><summary>Original English</summary>
**>>**: Okay. Well, uh, like what I said, you know, everything is in huge shortage. It's just to different extent uh GPUs uh memories and even like a below uh equipments and uh uh substrates and all those things even MLCC you know uh Taiwanese companies are benefit a lot from those you know the shortages uh it just take all those physical stuff it just takes time uh to build them out and if we have to pick something uh one direction you know it's giving the agencies pick up you like people are not right now very like you know CPU compute right the GPU to CPU that's ratio uh used to be just one to one now it's below 4:1 some people even are like a bullish like 8 to1 something like that so that's where you see the you know a huge potentials but I the point I want to make you know uh here we need to be a little bit creative and uh open-minded this is very early stage this is very early stage and this is pi growing story. It's not like who is going to win, who is going to lose. It's a whole pie is growing. So that's one aspect I want people pay attention to. Second, it's also about like a technology advantage. So you know you guys are the experts in this aspect, right? So all the like semi projects you have been doing for the hyperscalers, there are so fundamentally different from the stuff you are you used to be working on. So that's going to also create a winners and losers. Like for example like power semis used to be very very boring cyclical stuff but now given the GPU and CPU are using like more power high voltages and that becomes a very something very exciting we are looking into it. So, so this this is the exciting time. That's what I want to say. Uh sometimes you don't need to pick okay, I have to like GPU versus CPU, memory versus optics. I I truly believe, you know, in the grand scheme of things, this is a growing pie.
</details>

### 新型云与算力商业化模式

**>>**: 好的，太棒了。不知道大家有没有听说，GMI Cloud刚刚融资了6.68亿美元，对吧？首先恭喜你们。
<details><summary>Original English</summary>
**>>**: Yeah, that's great. Yeah. Okay, great. U so I don't know if you guys heard the news that the GMI cloud just raised $668 million, right? And well, congratulations first. Um, yeah,
</details>

**>>**: 谢谢大家。
<details><summary>Original English</summary>
**>>**: thank you guys.
</details>

**>>**: 我看到你们签约的ARR（年度经常性收入）在一年内增长了近10倍。是什么让GMI如此与众不同？
<details><summary>Original English</summary>
**>>**: And I saw that your uh contracted R also almost grow like 10 times in a year. So what makes like GMI like so different?
</details>

**>>**: 我想说有三点。第一，我认为可靠且按时的算力交付是最重要的事情。虽然我们在上层构建了很多软件层，但排在第一位的依然是提供按时交付和可靠的算力，这是非常关键的。这意味着在亚洲掌握非常强大的供应链关系并向全球扩张，所以第一点是供应链。第二点是东西方的布局。由于我们在美国面临很多政治阻力，无论是在兆瓦级甚至更小容量的项目上，我们在美国、东亚到南亚、东南亚都有数据中心布局，这为想要快速扩张的公司提供了不同的区位选择，这是第二点。第三点当然是——我想这也是今天的一个主题——很大程度上关乎融资。我们能够利用亚洲资本，过去是日元套利交易，我们有新台币交易，与美国同行相比，我们能够以低得多的借贷成本进行杠杆操作，而美国的同行不得不承受接近10%或更高的借贷成本。
<details><summary>Original English</summary>
**>>**: I would say uh three things, right? Uh number one, I think uh reliable and on time compute is the most important thing, right? uh we can we have a lot of uh software layer that's built on top but number one is providing uh on time delivery and reliable compute uh I think this is uh uh a very important thing so that means a commending a very strong supply chain relationship from Asia and expand globally so that's number one supply chain uh number two is the east and west so as we face a lot of political headwind in the US right um on mega megabs uh even smaller smaller capacities uh we have data center uh footprints across US from East Asia to South Asia Southeast Asia right so it provides different uh locations um for companies that want to expand rapidly so that's number two and number three of course uh this is I guess a topic today right is a lot about the financing um we're able to tap into kind of the Asia capital um it used to be yen trade We have a NTD trade which is Taiwanese dollar trade and we're able to uh uh leverage at a much lower borrowing cost comparing to our peers in the US which have to borrow about close to 10% or more.
</details>

**>>**: 太棒了。募集了这么多资金之后，今年初最难买到的东西是什么？你提到了像光纤互连（link），对吧？那现在呢？
<details><summary>Original English</summary>
**>>**: Well, that's great. And with all the capital raised, what is still the hardest thing to buy early this year? You mentioned like link, right? And what about right now?
</details>

**>>**: 是的，现在依然是电力。电力是最最关键的问题。如果你关注黄仁勋的讲话、第二季度财报以及华尔街的讨论，全都在谈电力外壳（PowerShell / 具备电力接入的数据中心外壳）。所以这是一个全球性现象，不仅在美国，全球各地都在发生。今天甚至到2027年能准备就绪的具备电力接入的算力设施是极其罕见的。
<details><summary>Original English</summary>
**>>**: Yeah. Uh right now it's still power. Ping power is the most uh most most critical issue. Um if you follow Jensen's kind of talk you know Q2 earnings and all the uh Wall Street uh you know chat it's all about PowerShell. Uh so this is a global phenomenon not just in the US but also happening globally. Uh compute that is uh PowerShell that is ready today or even 27 is extremely rare.
</details>

### 数据中心交付周期与延期风险

**>>**: 好的，针对这个问题，让我们再深入探讨一下。如果一家公司今天签约签约了一兆瓦的电力——这个问题可能是问伊森和亚历克斯的——需要多长时间才能转化为可用的算力？给大家一个大致的概念。
<details><summary>Original English</summary>
**>>**: Okay great. So to this question, let's dive a little bit deeper like um so if a company signs up for a megawatt today, this is might be for you Ethan and Alex. Um and how long until that turn into um usable compute? Just give us a sense.
</details>

**>>**: 好的。我认为在美国，超大规模数据中心的时间线通常大概是两年，也许两年半。我们谈论的是500兆瓦以上，有时甚至是吉瓦级的大型数据中心。对于较小的规模可能会更快，大概一年半，但对于大型数据中心大约是两年。另外我想和听众分享的一点是，根据我过去半年的观察，我认为目前整个数据中心和AI行业存在潜在的巨大风险，那就是……
<details><summary>Original English</summary>
**>>**: Yeah, I think uh United States normally the timeline is about two years maybe two and a half years for the very large scale data centers. we're talking about like a 500 megawatt above like sometimes a gigawatt level uh large data center I think for for the smaller ones it could be faster maybe one half year but for large ones that's roughly two years and I do think uh maybe one thing I want to kind of share with the the audience is that what I observe in the past half year I think there is a potential huge risk to the whole data center and AI industry right now and I think
</details>

**>>**: 你是指延期吗？
<details><summary>Original English</summary>
**>>**: you mean a delay
</details>

**>>**: 是的，我认为是数据中心的交付延期。目前很多数据中心是去年规划的，意味着它们并不是今年交付，而是预期在2027年或2028年交付。所以很多问题还没有浮出水面，我们也没有察觉到。不过像《华尔街日报》或其他投资银行的报告也提到，他们观察到了全美普遍出现延期的迹象。所以我确实认为这可能是一个巨大的风险。导致这种延期风险的原因有很多，其中之一就是我们讨论过的电力问题；各种电力设备可能是另一个原因；此外还有各种各样的新法规限制了数据中心建设的进度。举个例子，比如FAA（美国联邦航空管理局），这是美国的航空监管机构，跟数据中心毫无关系，但不知何故也出台了新规定，限制在机场附近建设数据中心，他们认为可能存在某些安全问题。另一个因素正如布鲁斯所提到的，当地社区的反对正在成为美国的一个大趋势。如果你阅读美国的主流媒体，比如《华尔街日报》等，你会发现很多关于数据中心的故事，所有这些报道都围绕着同一个叙事，那就是将整件事描绘成美国的当地社区反对AI行业或AI数据中心。不幸的是所有的报道都是这样的叙事，因为我个人并不认为这是一种客观的视角。然而，这种故事能吸引人们点击和阅读，对吧？它并不一定是事实。但是现在发生的情况是，在11月的中期选举之前，美国几乎所有政客都在表达反对数据中心的观点，以便在中期选举前获得更多选票成功当选，这如今成了一种趋势。甚至在得克萨斯州，今年早些时候得州州长还在全力支持数据中心，但几个月前他的观点发生了180度的大转弯，完全反对数据中心。这是由于当地对这些政客施加的压力，这可能会成为导致数据中心延期的另一股巨大力量。我确实认为这可能是一个巨大的风险。用公开数据举个例子，比如SpaceX向Anthropic出租了一些数据中心，数字大约是300兆瓦的数据中心，价格接近每月10亿美元，对吧？
<details><summary>Original English</summary>
**>>**: yes I think that is a delay of the data center so right now a lot of data center they are planned maybe last year meaning that they are not delivered this year but they will they are expected to be delivered in 2027 or 28. So a lot of problems are not surfaced yet and we do not notice that like like Wall Street Journal or other kind of investment bank reports they also mentioned they observed like signs that there are delays across the broad United States. So I do think this could be a huge risk and there are a lot of reasons uh leading to this delay risk. One of them is what we discussed like electric power could be one issue and all types of electric equipments could be another and also there are all types of regulations like new regulations like limiting the progress of data center constructions. Uh one one example is uh FAA like uh that's a kind of aviation regulation entity United States. It has nothing to do with data center but somehow it is also having new regulations limiting data centers uh which are built near airports and they think there could be some uh safety issues and uh other another thing is what uh Bruce mentioned like local community oppositions is becoming a huge trend United States uh if you are reading the mainstream medias United States like Wall Street Journal etc you will notice that there are a lot of stories about data centers and all those stories are around the same narrative which is uh they kind of make this whole thing kind of like the the the local community of United States is against uh the AI industry or AI data center. Uh I I it's unfortunate like all these stories are narrative like this because I I personally do not believe that is a objective view. However, that's a that's a story like people click and view, right? uh and it's not necessarily the the truth but however what's happening now is that before uh November's midterm election uh almost all the politicians United States they are kind of a uh kind of they're expressing their views against data centers so they can get more votes uh to be elected uh before the during this m midterm election and that becomes a trend now even in Texas right in early this year the Texas governor is was fully supporting data center but a few months ago uh his view changed 180% 180 degrees right completely against uh data centers and that's because of the local company's pressure on those politicians and that's could be another huge force like uh causing the delay of the data centers and I do think this could be a huge risk because maybe using one kind of a public data as example like uh uh SpaceX, right? The the SpaceX uh rented out some of the data centers to Anthropic and I think the number is around like 300 megawatt of data centers uh and for uh almost $1 billion a month, right?
</details>

**>>**: 没错，价格比去年翻了三倍。
<details><summary>Original English</summary>
**>>**: Right. Triple the price compared to last year.
</details>

**>>**: 是的，价格非常高。但你可以把这个数字作为一个参考，这意味着如果300兆瓦的数据中心每个月价值10亿美元，那么如果有数吉瓦的数据中心延期一年，整个行业会因为数据中心建设的延期而损失或推迟多少收入？这个数字对整个行业来说可能达到1000亿美元的级别。我们在这次讨论中也谈到了融资，这意味着投入到数据中心建设中的所有资金，可能要推迟一年才能产生收入，从而导致推迟获得1000亿美元的收入。这对行业将是一个巨大的打击。我认为如果管理不当，这可能会是一个巨大的风险。
<details><summary>Original English</summary>
**>>**: Yeah, that's a huge price. But uh but you can use this number as a reference meaning that okay, so if for 300 megawatt of data center it's worth uh $1 billion per month. What if there is a several gigawatt of data center which are delayed for one year like how how much revenue is going to be lost or delayed because of the the the delay of the data center construction and if that number could be in terms of $100 billion for the whole industry and we were also talking about financing this panel. So that means all the money is put into data center constructions, you won't get it the revenue until maybe one year later and causing you a delayed 100 billion dollars of revenue. That's a huge blow to the industry. I think so I think this could be a huge risk if it's not managed well.
</details>

**>>**: 好的。亚历克斯，刚才谈到了从签约电力到获得算力需要大约两年的时间。新型云服务商也是这样吗？还是说这实际上是你们的机会？
<details><summary>Original English</summary>
**>>**: Okay. So Alex um um you mentioned about like two years from your sign uh the power to get the computer. Is it the same to new clouds or that's actually your opportunity?
</details>

**>>**: 我认为这取决于所讨论的规模。吉瓦级的算力显然面临巨大问题，电网几乎不可能支持吉瓦级的规模，因此通常采用混合电网或表后方案。正如前面提到的表后发电，基本上是使用Bloom、某种内燃发电机（recip）或某种燃气轮机，这意味着你需要燃烧天然气。因此，最关键的问题实际上是环保局（EPA）关于碳和二氧化碳排放的空气许可证。所以基本上，任何目前没有获得许可证、还没有开工建设的项目，我认为即便对于较小规模的模块化橇装（skids）建设，也需要T+14个月，可能再加两个月左右；然后从机房就绪（whitespace ready）到Token产出就绪（token ready），我认为还要再加两到三个月。所以如果你还没有开工建设，总共需要16到17个月。因此我认为情况非常严峻。在过去，我们的客户（包括超大规模企业）甚至不想讨论任何低于100兆瓦的项目，而现在我看到有人甚至要求20兆瓦、30兆瓦，只要你能在2027年之前交付就行，他们全都愿意接手。情况大概就是这样。不过这是在美国方面。我认为在亚洲方面可以更快实现，那里的能源更加充足；而且我认为政府（取决于具体地点）支持力度更大，是一种自上而下的方式，因此你可以以相对迅速的方式建设数百兆瓦的园区，但你仍然需要寻找不同的区位缝隙。
<details><summary>Original English</summary>
**>>**: Uh I think it depends on the scale that you're talking about. A gigawatt compute obviously very very uh is a huge issue and almost there's no way that grid can support a gigawatt scale right so it's typically a mixed grid or behind a meter and uh like what you kind of mentioning uh behind a meter uh basically you're using bloom or some sort of reip or some sort of uh turbines right and that means you're burning natural gas and therefore the most critical issue is actually air permit with ESA on like carbon and carbon dioxide uh emission. Uh and so basically anything that is not permitted right now that you haven't started construction it's t plus 14 months I would say even for smaller scale uh modular build right uh skits is probably at another two months uh more or less uh and then you add another I would say two to three months on token so whitespace ready to token ready so you're talking about six 16 17 months if you haven't started any any construction right and so uh I think it's the very dire situations uh in the past our customers including hyperscalers um didn't want to talk about anything below say 100 megawws and now I've seen people asking for even 20 megawws 30 megawws anything if you can deliver before 27 that's awesome like they'll take everything um and uh yeah that's kind of the situation right now um but this is in the US side uh I think Asia side you can have have it sooner, right? I think there's just more abundance uh uh energy uh and also uh I think the government depends on which locations are more supportive uh and it's kind of top down approach uh and so uh you can have these kind of uh hundreds of megawatts of campuses that are being built in a relatively sweet fashion but you still have to find uh different pockets. Yeah.
</details>

**>>**: 是的，这可能是一个很好的策略。考虑到像Nebius这些公司也在走向全球。我想就这一点跟进一下，你提到了延期，我们预期会有多大程度的延期？
<details><summary>Original English</summary>
**>>**: Yeah, that could be a great strategy. think about like um Nubius and those companies also go global right um and I want to can follow up on this point you mentioned uh about the delayed how much delay are we expecting
</details>

**>>**: 这是个好问题。
<details><summary>Original English</summary>
**>>**: uh that's a good question
</details>

**>>**: 对于普遍的超大规模企业而言。是的，我认为已经有一些报告和数据公布了，可能来自SemiAnalysis，也可能来自不同主流媒体。我认为目前的趋势是，没有人真正知道延期的确切规模，但根据所有这些数据，我们可以大致推测，大约有10%到20%的数据中心可能会延期一年以上。
<details><summary>Original English</summary>
**>>**: for the general like hyperscal yes I think uh there are some reports and numbers already out there right from from maybe semi analysis maybe from different mainstream mediums I think right now the trends is that no one really knows what's the scale uh of the delay uh but the based on all those data we can roughly guess like I think maybe 10 to 20% of the data center could be delayed more than a year
</details>

**>>**: 我能补充一个问题吗？这是延期的问题，还是取消的问题？这正是我困惑的地方。如果是延期，也许还好，因为整个供应链都非常紧张；但如果是取消，那可能是一个更大的问题。所以我想从你们那里了解一下情况。
<details><summary>Original English</summary>
**>>**: can I add one question so it's a matter of delay or it's a matter of cancellation that's where I have troubles to really understand you know if it's delayed maybe it's fine because the whole supply chain is so like you know toughen up and but it's canled so like that may be a bigger problem so I just want to get some sense from you guys
</details>

**>>**: 是的。你需要明白，云和数据中心是一个区域化的业务。阿伯特（Abbott）州长在得州站点按下了暂停键，我们位于丹佛和亚特兰大的站点突然变成了炙手可热的资产。这就像是一个区域性事件：西南地区按下了暂停键，东北地区就变得抢手，然后每个人都开始争抢。它真的是按季度在变动。因此，我们机构的观点基本上是在全球范围内开展投机性建设，包括东亚、东南亚，以及美国其他数据中心集中度较低的地方。这样你就能找到机会的缝隙；等到时机来临、事件发生时，你就能抓住机会。因为我们都与超大规模企业和前沿实验室保持着联系，当项目暂停或取消时，机会就来了，但你必须做好准备。
<details><summary>Original English</summary>
**>>**: yeah uh So I think it's you got to understand uh clouds and data centers it's a regionalized business right so governor Abbot uh right kind of have a pause on the on the Texas site and suddenly our sites in Denver and Atlanta become really hot hot hot seat assets right so it's kind of like oh it's a regional event all right this hit pause on the on the on the you know southwest side and the northeast becomes popular right and then everyone kind of start scram scrambling Right. Uh and so it's like it literally moves quarter by quarter,
</details>

**>>**: 对吧？
<details><summary>Original English</summary>
**>>**: right?
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: And so so our house view is basically uh basically start speculative builds around the world in East Asia and Southeast Asia as well as US elsewhere that has less of a data center concentration, right? Then you can find pockets of opportunities and when time hits when something happens then you can pick up because we all have the contacts with kind of like hyperscalers and uh and frontier labs right and so when the projects get paused or canceled then you know opportunities comes but you got to be ready.
</details>

**>>**: 也许可以顺着布鲁斯的问题跟进一下，我认为绝大多数是延期，而不是取消。一小部分可能会被取消，但大部分只是延期。
<details><summary>Original English</summary>
**>>**: Yeah maybe just a follow up of Bruce's question I I think mostly it's delayed not canceled. Yeah, I think a small percentage of them could be cancelled, but most of it's just delayed.
</details>

**>>**: 好的，谢谢两位。
<details><summary>Original English</summary>
**>>**: Okay, thank you guys.
</details>

**>>**: 是的，目前没有人想取消。
<details><summary>Original English</summary>
**>>**: Yeah. Um, nobody wants to cancel right now.
</details>

### 数据中心融资机制与错配

**>>**: 我其实还有另一个问题。接着亚历克斯的回答，从你们的角度来看，融资是不是主要问题？显然供应链短缺等问题是存在的。
<details><summary>Original English</summary>
**>>**: Well, I actually have another question. So, like just you know uh following uh Alex's like answers uh from your perspective and uh financing is the major problem or not? It's obviously actually the supply chain the shortage and you know those stuff.
</details>

**>>**: 我认为这绝对是一个巨大的问题。这就是为什么你会看到博通（Broadcom）、英伟达（Nvidia）、谷歌都在加大融资参与力度。融资领域存在巨大的错配，所以谁能解决这个问题，谁就能获得巨大的机会。数据中心通常需要12到15年的租约，但算力通常只有4到6年，因此在合同期限上存在明显的错配。数据中心方面非常希望确保租约的确定性，因此英伟达、博通或谷歌这些最大的投资级主体（IG）会通过不同方式介入。所以当我们接触数据中心运营商或具备电力接入的设施方时，最常见的问题是：“谁是你们的投资级担保方？是否有投资级主体的信用包装（IG-wrapped）？”这就形成了一种错配。解决办法是存在的，比如设立保险箱（lockbox）机制，将五到六年的现金流放入特殊目的实体（SPV），优先支付给数据中心运营商。已经有开创这一先河的先例，或者在数据中心端提供某种残值担保。但现在每个人都在尝试创新方式。
<details><summary>Original English</summary>
**>>**: I think it's definitely a huge issue. That's why you see uh you know Broadcom or uh Nvidia, Google all stepping up on on the financing. Um and so there's a huge mismatch in in the financing and so whoever can solve this I think will uh you know can can make a lot uh I guess there's a lot of opportunities call that way. So data center is typically uh they require 12 to 15 years uh of lease right. Um but compute is typically you know four to six years right and so there's clearly a mismatch in terms of the uh contract durations uh and so data center folks they really want certainty right of the lease and therefore there's different ways that Nvidia and Brocom or or Google the largest IG's to come in and so like the the I guess most common question when we go to data center operator or uh or uh PowerShell they're like Okay, who's your IG? Uh, as it's being IG wrapped, right? And so that's becomes there's a basically a mismatch. Um, and here's a solution, right? There's some solutions basically a lock box, right? You're you're you're putting kind of the cash flow of five six years into a SPV and then that will get paid to the data center operator first. And there's some presidents that started that, right? or some sort of residual value guarantee on the data center side, but everyone's trying to be creative right now. Um and uh yeah
</details>

**>>**: 我们刚才谈到了AI数据中心的建设与融资，我相信很多数据中心现在开始利用公共信贷市场，那也是一个万亿美元级的市场，而AI数据中心目前仅占其中的5%，从传统软件信贷转向数据中心信贷还有很大的空间。作为投资人，在万亿信贷的这一端，什么让你感到担忧？
<details><summary>Original English</summary>
**>>**: and we had that video talking about the AI did a center build out and uh uh that and I'm sure lots of data since now started tapping into uh public credit that's also like trillion dollar market and uh AI data center is only 5% of that and there will be lots of room switching from the traditional software uh credit to now data center and as you're an investor what worries you on this side of you know the trillion credit card in that.
</details>

### 宏观债务周期与私营部门加杠杆

**>>**: 好的，我来给听众提供一些关于这个问题的视角。我们需要往后退一步，因为我们必须清楚自己在整个大格局中所处的位置。像雷·达利欧（Ray Dalio）总是在谈论，我们正处于全球公共部门杠杆率的顶峰，这确实非常真实。我们必须处理这个问题，整个发达国家世界的杠杆率都非常高，所以他们必须去杠杆。历史上只有几种行之有效的方法来应对这种情况。今天我们只聚焦于其中一种，那就是增长。斯科特·贝森特（Scott Bessent）多次提到过这一点，这是他的核心主张之一：我们需要通过增长来摆脱债务问题。回顾历史，这确实是非常真实的，这是我们摆脱债务的主要方式。在宏观大局中，这是AI的历史使命。当然，如果不是AI，也会是别的东西。但很幸运，这个重任落在了AI的肩上。这是一个巨大的使命，全世界都需要AI来实现真正的增长。从这个角度来看，所有的资金都会涌入进来，这是大家需要记住的一点。第二，这个周期截然不同。为什么？因为想想2008年之后发生了什么。公共部门一直在加杠杆，各国政府发行债务、印钞，不断加杠杆直到今天难以为继。但私营部门在2008年之后一直在去杠杆。因此无论是企业还是家庭（尤其是在美国），资产负债表都相对非常干净、非常健康。所以在新的周期中，情况将会反转，私营部门将会加杠杆。锚点就是AI，AI给了他们加杠杆的机会和理由，而公共部门则必须去杠杆。这就是我们必须置身其中的整体宏观大背景。多年来我们习惯了轻资产商业模式，习惯了自由现金流，不喜欢公司加杠杆，但那个时代已经过去了，我们必须适应这一点。有时候当你听到人们说甲骨文（Oracle）的信用利差走阔了，坦白说目前确实有点夸张，但那不是崩溃，而应该称之为重新定价（repricing）。甲骨文从信贷角度看过去一直是一头现金奶牛，非常安全，信用利差非常紧窄；但现在他们必须改变商业模式以保持竞争力，这就是必须付出的代价，所以信用利差走阔很正常，这就是我想表达的。我们正处于这个过程中，这是私营部门第一年认真加杠杆，在可预见的未来都会是这样，我们必须习惯这一点。明年像亚马逊甚至Meta都会耗尽自由现金流，所以他们必须借贷，但他们的资产负债表非常健康，属于投资级类别。今年表现非常出色，如果我没记错的话，年初至今的新发行规模大约接近5000亿美元，但我们仍有很大空间，这仅占整个投资级市场的约7%。我们甚至还没真正使用高收益债市场，更不用说所有的私募股权和私募信贷了。金融过去曾是一个“脏词”，但在这一轮周期中，你必须研究银行业，必须观察资金流向，看银行体系是否足够健康、是否有能力支持这种杠杆。由于今天时间有限，这是一个非常令人兴奋的话题，简短的回答是：是的，绝对健康。美国银行体系非常健康，完全有能力加杠杆。关键在于你们是否有能力或愿意借款。只要你们敢借，他们就敢贷。事情就是这么简单。
<details><summary>Original English</summary>
**>>**: All right. Uh I'll give audience some perspective on that. We step back a little bit because we need to know where we are in the you know the whole big picture and uh uh everybody like Redo Redalio always talk about we're at the end of you know the peak of the leverage uh for the public sectors globally right which is true uh which is very very true. we have to deal with with the this problem and the whole entire developer world is so leveraged up. So they have to deverage you know there are only like a proven ways to deal with this. Today we are going to just focus on one uh that one is uh growth. So this is the Scott Basson like mentioned this many times that's one of his pitches right so we need to grow out of our that problems and uh which is actually very true looking at history you know that's the only way the other way not not only way but the major way we have to grow out of this. So this is in the grand scheme of things. This is a historical mission for AI. Of course, if it's not AI, it's going to be something else. But you know, AI is so fortunate like it's fall onto AI's shoulder. So this is a huge the whole world needs AI to really grow. So from that perspective, all the monies are going to coming in are going to coming in. So that's you know something you need to keep in mind. Second uh this cycle is so different. This cycle is so different. Why? Because after 08 think about what happened. So public sector has been leveraging up right all the governments issue like a debts and you know printing money. So they leverage up until today they couldn't do it anymore. But private sector private sector has been deleveraging after 08. So their balance sheet both corporate especially in the US go both corporations and households their balance sheet are relatively very very clean and healthy. So in the new cycle it's going to re it's going to reverse it's going to reverse private sector is going to leverage up. The anchor is AI AI give them an opportunity an excuse to leverage up. The public sector has to be leveraged. So that's the thing that's the whole scenario the big picture we have to put ourselves in right so because just like for so many years you know we are so used to asset light business models we are so used to free cash flows we do not like companies to you know leverage up but you know that time has gone we have to get used to this because sometimes when you hear people like ah uh uh uh uh like Oracle Oracle's credit spread at uh widen up and right now it's that a little bit crazy to be honest with you but that's not a collapse that's call it a repricing Oracle used to be a cash cow right from the credit perspective it's so safe of course the credit spread is really really tight but now they have to change their business business models to become relevant so that's the cost that you have to pay so that's why the credit spreads just widen up it's normal that's what all I'm trying to say so we are in this process this is the first year actually private sector seriously lever up it's going to it's going to be like this for the foreseeable future so we have to get used to this right so next year like Amazon and even Meta is going to use all their free cash flow so they have to borrow but their balance sheet is so healthy their balance sheet is so healthy and uh no they're all in the investment grid you know categories and it's still like it's been a fantastic year. The new issuance if I remember it correctly year to date is around almost half trillion but still we have a lot of room. It's only like 7% something like that of the whole IG market. We haven't really used the you know high yield market yet and not to mention all the like private equities and private credits. You know financials used to be such like a dirty word but for this cycle you have to do research on on the banking sectors. You really need to see how those you know flows are is the banking system is healthy enough has the capacity to support this kind of like leverage you know because we have limited time today because it's really really exciting you know topic to talk about uh the short answer is yes it's really yes the US banking system is so healthy and has the capacity to leverage up what is well it really depends on you guys are able or are willing to borrow. If you dare to borrow, they dare to lend. So as simple as that. Exactly. Yeah.
</details>

**>>**: 亚历克斯，我相信听到这个你一定很高兴。
<details><summary>Original English</summary>
**>>**: Alex, I'm sure that's great for you to hear.
</details>

**>>**: 我并不是说这里面没有任何问题。即便在今天，超大规模企业和半导体企业是健康的，但新型云以及部分电力建设项目并不健康，它们的信用利差非常夸张。因此它们可能会出现问题，但现在还处于极早期阶段。这完全取决于AI如何增长。如果收入增长好于预期，你就不需要这种杠杆；杠杆的作用相当于缓冲垫。因为在理想的世界里，如果你能立即产生收入覆盖资本支出，自然不需要杠杆，但现实并非如此，这就是资本主义运作的方式。在整个事物的早期阶段，你需要这个缓冲垫，而缓冲垫就是杠杆。这就是我想说的全部内容。
<details><summary>Original English</summary>
**>>**: I'm not trying to say like there is no problems there there will be even today like you know hyperscalers are healthy, semis are healthy but like you know newer cloud and some like power build up they're not their credit spreads are crazy. So they might be the problem but this is still so early. It's it really depends on how AI is growing. You know if if if if the revenue is coming up like a better than people expected you do not need this you know leverage leverage works as a a buffer right because in a perfect world if you know you generate revenue right away it covers your capex but which is not the case and that's how capitalism works. during the early stage of the whole thing, you need this buffer. Buffer is leverage. That's all. Yeah, that's all I'm trying to say.
</details>

### 估值、长约与Token化商业策略

**>>**: 听到这些太棒了。我们仍处于AI时代的初期，所以不存在泡沫。
<details><summary>Original English</summary>
**>>**: That's so great to hear. We're still very early in this AI time, so there's no bubble.
</details>

**>>**: 我答应过要讲得犀利一点，所以抱歉了。
<details><summary>Original English</summary>
**>>**: Well, I I promise to make it spicy. So, sorry.
</details>

**>>**: 这其实是个好问题，因为面临很多挑战。至少在股票市场整体来看，你知道目前QQQ的市盈率估值倍数是多少吗？不知道大家有没有注意到，现在大约是下一年度远期收益的20到21倍。相对于金融环境而言，即便在实际收益率上涨之后，它依然是便宜的。为什么便宜？因为QQQ目前是一个绝佳的代理指标。我们做过研究，实际上可以计算出长期成长溢价（secular growth premium），即扣除周期性风险溢价后剩下的长期成长溢价。QQQ的这一溢价大概是26%，标普大约是14%，小型股的问题在于它们没有从中受益多少，只有5%。所以大家必须相信市场是非常高效的，市场一点也不傻，市场的定价是非常理性的。这就是我想说的。
<details><summary>Original English</summary>
**>>**: It's actually good question because a lot like challenges. Uh well uh at least in the equity space overall do you know like how much like what's the multiple for QQQ these days? Do you like I don't know you pay attention now it's uh uh 21 20 time 21 times like forward earnings next next year it's cheap relative to the financial conditions even after this running up of real yield it's just cheap why it's cheap because QQQ right now it's really a proxy we did that research actually you know you can literally calculate secular growth premium which is you all the premium risk premium excluding the excluding the cyclical you know uh premium what's left is your secular growth premium QQ carries like what 26%. SMPP car car carries what 14%. Small cap that's the trouble they do not benefit this a lot it's only 5%. So you know actually people you got to trust market is very efficient you know market is not dumb at all. So they price everything you know very rationally. That's what I want to say. Yeah.
</details>

**>>**: 好的，太棒了。让我们转换一下话题，回到亚历克斯这里。我相信你很高兴听到还有大量的债务可以借贷。在这种情况下，你会尽量多借款并尽快扩张吗？
<details><summary>Original English</summary>
**>>**: Okay. Great. Okay. Let's switch gear a little bit and back to Alex. I'm sure you're happy to hear about like um there are still lots of debt to borrow and uh in that case uh would do you just try to uh like get as much as possible and expand as soon as possible?
</details>

**>>**: 是的。你看市场上主要有两家公司，Nebius和CoreWeave。CoreWeave在历史上一直强调五到六年的长期合同，他们做得很好。你看Nebius，大概50%（我不清楚具体比例）是长期算力，另外50%是现货（spot），属于投机性建设。你会发现，当供应非常紧张时，CoreWeave基本上无法利用所有算力的价格上涨获利，而Nebius能够利用这种情况，收取高得多的溢价，我认为达到每瓦25到30美元甚至50美元，而CoreWeave大约是15美元。我们也采取了同样的方法。我们既进行投机性建设，也进行长期建设，以保持业务健康。对于长期建设项目，我们能够从美国和亚洲以低得多的资金成本借贷，显然这并不是全面拉满杠杆，而是必须保持健康。我们通过设立各自独立的SPV对所有借款进行风险隔离（ring fence），从而使公司能够以健康的步伐增长。
<details><summary>Original English</summary>
**>>**: Well, yeah. Um so you see in the market there's two two companies, right? It's Nebas and Core Weef. And Coravee has historically been emphasizing long-term contracts, five years, six years, right? And they've done well. Um, and you see Nebius, right? It's which is like 50% is or I don't know that exact ratio is long-term compute and then 50% is uh is spots, right? Kind of speculative builds. And you see that um when the the supply is very constrained and coreweave is unable to basically uh take advantage of the price increase of all the compute and Nebius is able to kind of take advantage of that situation and charge a much higher premium to you know uh I think $25 to $30 or even $50 per watt right where core we is roughly 15 Um and so we're taking the same approach as well. So we're we're building speculative builds uh as well as uh uh long-term long-term builds so that we uh remain healthy, right? And so on the long-term builds, we're able to borrow at a much lower cost of capital from US uh and Asia, right? Obviously, it's not leveraged uh all the way up, but it has to be uh healthy. Um and so we kind of ring fence uh all the borrowing within each uh each and uh every uh SPVS uh and so so the company can grow uh on a healthy healthy pace.
</details>

**>>**: 我注意到你们也开始销售Token了，对吧？所以仅仅卖GPU机时是不够的。这纯粹是为了经济收益，还是有战略层面的考量？
<details><summary>Original English</summary>
**>>**: Uh I noticed you also start to uh do the sell token, right? So the GPU hour is not enough. Is it just more for the economics or there's a strategic?
</details>

**>>**: 是的，你看，你必须从整体上看待云业务的本质是什么。云业务的核心完全在于利用率。把云想象成一台巨大的笔记本电脑：如果我把它租给你，你用了12个小时，不再多用了，还剩下12个小时，那么我会在你睡觉的时候把它倒出来租给另一个人，这就是为了利用率。如果我只租给一个人，利用率可能只有50%。所以云业务的核心就是提高利用率。拿一个空杯子来说，五到六年的长期算力合同就是鹅卵石，你把它放进玻璃杯里填满50%，非常好，你的现金流变正了，但利润率并不高；然后你开始往里倒沙子，什么是沙子？就是6个月、1年、2年、3年的短期合同，用来填补空隙；接着你做什么？你往里面倒水，把利用率彻底填满。因为你必须满足服务等级协议（SLA），会有热备（hot swap）节点，比如有5个或10个备用节点。那我们要怎么处理这些节点？没人会单独租下这几个节点。我们把它们放到市场上，但市场上也没有多少人能消化这种单一节点、两个节点或三个节点。顺便提一下，我们有这个平台，但你也可以把它们转化为Token，因为Token是以更小的颗粒度和区块形式存在的。所以我认为新型云服务商和推理平台不可避免地会整合为一个垂直栈，因为这是云厂商提高利润率的唯一途径——将GPU时间切成越来越小的碎片，这就是Token业务的本质。因此Token业务对我们来说非常核心。由于我们所有的算力已经全部预售到了2027年底，但我们有这些备用的热备节点，以及我们从外部采购的算力，我们将它们转化为Token，对我们来说这纯粹是极高的利润率。
<details><summary>Original English</summary>
**>>**: Yeah, look. Okay. So you got to look at cloud business in general like what is the fun fun like what is the business of a cloud cloud business it's all about utilization rate okay it's like think of a cloud is just like a massive laptop if I lend it to you right and you use it 12 hours of time right you're not use more and you have 12 hours left so I'm going to rinse that and then and then lend to another person when you're asleep right that's for utilization so if I lend to only one % that utilization is maybe 50%. Right? Uh and so the cloud business is all about increasing that utilization. So take an empty cup, the long-term compute, five years, six years contract, that's the pebbles and you put it in a glass, right? You fill that to 50%. Great. You're casual positive, right? But you're not making too much margin. And then you just start throwing in sand. And what is sand? That's short-term contract. 6 months, one year, two year, three years to fill that gap. And what do you do? you pour water in to fill that utilization up because you're going to have hot swap, right? Because we had to fulfill our SLAs's. So you have like say five spare nodes or 10 spare nodes. What are we going to do? No one's going to rent that. So we throw that onto a marketplace and marketplace not many people will absorb all these one node, two node or three nodes. We have that platform by the way, but you also turn that into tokens because that's in in a smaller increments and chunks. So I do think that it's inevitable for NeoClouds and also inference platform to consolidate into a vertical stack because that is the only way uh for cloud to increase the the margin is by cutting the GPU time into smaller and smaller chunks and that's what token business is about. Uh and so token business for us is very essential, right? Because all our compute is already sold out all the way to 27 and end. But we have these spare hot swaps and and uh compute that we buy externally and we turn that into token and to us that just pure margin.
</details>

### 未来预测与总结

**>>**: 好的，太棒了。我们剩下的时间不多了，但我想让每位嘉宾对明年做一个预测。必须给出一个预测并给出一个时间点。谁先开始？
<details><summary>Original English</summary>
**>>**: Okay, great. Yeah. Um so we don't have much time left but I want uh let each panelist make some predictions for next year. You have to give a prediction and give a time. Who wants to start first?
</details>

**>>**: 我可以先来，因为我是做市场的。
<details><summary>Original English</summary>
**>>**: I can start because I'm market guy.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Okay.
</details>

**>>**: 好的，美股市场的情况大致是这样：由于金融环境一直在收紧，我们目前处于估值的底部。这跟云和AI无关，纯粹是美国国债市场出现了一些剧烈波动。这是件好事，因为你需要通过这种波动来应对通胀问题；但希望展望未来，我们能真正解决通胀问题，从而释放空间。所以我想说的是，金融环境基本上已经在这里见顶了。如果这一假设成立，它不足以真正破坏我们目前的增长。想象一下QQQ目前的年化增长率是50%，即使增速放缓一点，也有40%左右。从成长周期的角度来看，我们确实正处于中途。同时我鼓励大家保持开放心态，其持续的时间可能会比想象的更长。所以我实际上非常非常乐观，但我不会去押注估值本身的扩张，而是去寻找具有扎实韧性增长的领域。目前看很不幸只有AI，因为所有其他周期性行业——房屋建筑商、零售商甚至传统工业企业——由于更高的利率都遇到了困难，它们对利率非常敏感。鉴于这种背景，在今年年底甚至下半年，就像去年上半年一样，那是我会下注的地方。
<details><summary>Original English</summary>
**>>**: Well, uh, so here is the US equity market like a situation. Uh, we are kind of like at the bottom of the valuation. Uh, for a reason because of the financial condition has been tightening, you know, like it has nothing to do with cloud AI. It's just, you know, the the US treasury market is, you know, uh, having some like a dramatic moves. uh which is a good thing because you need that to deal with all the inflation stuff but hopefully going forward and we can really deal with the inflation things and that gives room. So all I'm saying like you know uh financial conditions has kind of like peaked here. If that works out if that works out it's not enough to really damage the growth we have right now. Just imagine QQ year over year right now it's a 50% growth and uh even this is slowing down a little bit. let's do 40% something you know from the growth perspective growth cycles so we are really in the middle of something and also I encourage everybody to be open-minded they think can last longer than you imagine so I'm actually very very positive but I do not bet on the you know valuation stuff it's really you find places which has a solid res resilient growth unfortunately it's AI so far because all other cyclical stuff house you know home builders retailers even like you know traditional industrials you know they have troubles because of higher you know their interest rate very sensitive so given this you know background uh uh towards the end of this year even the second half like last year first half last year uh that's where I'm going to place my bet yeah
</details>

**>>**: 能说得更具体一点吗？
<details><summary>Original English</summary>
**>>**: uh to make it more concrete
</details>

**>>**: 很短的一句话。
<details><summary>Original English</summary>
**>>**: well very short one sentence
</details>

**>>**: 做多AI基础设施。
<details><summary>Original English</summary>
**>>**: well the long AI infrastructure by the way yeah
</details>

**>>**: 我不想去挑选具体的赢家或输家，只要广泛配置，我认为就是正确的策略。
<details><summary>Original English</summary>
**>>**: oh AI I don't want to pick winners or losers that given this is already but you just have the broader exposure I think that's the right play
</details>

**>>**: 好的，最起码就是做多QQQ。
<details><summary>Original English</summary>
**>>**: okay very minimum just long queue
</details>

**>>**: 我之后可能还会回来找你。
<details><summary>Original English</summary>
**>>**: I might come back to you
</details>

**>>**: 好的，伊森。
<details><summary>Original English</summary>
**>>**: okay Ethan
</details>

**>>**: 好的。我认为……
<details><summary>Original English</summary>
**>>**: great yeah I think uh yeah during
</details>

**>>**: 不一定是股票，任何预测都可以。
<details><summary>Original English</summary>
**>>**: it doesn't have to be like a stock like anything yeah a prediction
</details>

**>>**: 是的，早餐时我和布鲁斯聊过，我认为我们的看法高度一致。正如我提到的延期等风险，我确实认为整个过程中肯定会经历阵痛，这意味着会有一些起伏波动。但从中长期来看，我对AI基础设施非常积极和乐观。着眼于算力的需求和……
<details><summary>Original English</summary>
**>>**: yeah during breakfast I talked with Bruce and I think we're pretty much in line I think I do think some risks as I mentioned like delays etc so I do think there there is going to be kind of a kind of a pains in the process for sure. Uh meaning that there will be some up and downs. Uh but I in in mid to long term I'm very uh uh positive and optimistic about AI infra. And looking at the demand for compute and the
</details>

**>>**: 供给。更具体一点呢？
<details><summary>Original English</summary>
**>>**: supply specific
</details>

**>>**: 是的，看着供需错配或差距，我认为到明年底，AI基础设施的电力板块——尽管会有起伏——我认为它会表现得非常好。
<details><summary>Original English</summary>
**>>**: yes looking at the demand and the supply mismatch or the gap I do think the power sector for uh AI infra uh by the end of next year even there will be some up and down I think it's going to do really well
</details>

**>>**: 更具体一点，正如你所提到的，可能是表后发电相关的电力？
<details><summary>Original English</summary>
**>>**: and even more specific as you mentioned that might be behind the meter related power
</details>

**>>**: 我会说是的，表后发电技术；实际上与布鲁斯所说的类似，我认为很多电气设备公司将从中受益。
<details><summary>Original English</summary>
**>>**: I would say yeah behind the meter generation technologies and actually similar to what Bruce said, "I think a lot of electrical equipments are going to benefit from it."
</details>

**>>**: 好的，亚历克斯。
<details><summary>Original English</summary>
**>>**: Okay, Alex.
</details>

**>>**: 好的，一句话对吧？我认为至少在2030年之前，我们将面临永久性的算力短缺。我来解释一下为什么。现在市场上如果看的话，有预训练和后训练，但实际消耗算力的是什么？是推理，对吧？目前大部分消耗在代码领域，从Codex到Claude Code，我认为这已经被计入预期了；你还有多模态，也就是图像生成和视频生成，大家可能在Reels或TikTok等平台上都看到了，这些人们已经见识到了。但大家必须明白，与研究人员交流会发现，RSI（递归自我改进）很快就会到来，这意味着算力或AI将在没有人类参与的情况下进行自我训练和改进，因此算力需求将呈爆炸式增长。与许多知名研究人员交流，他们的预测是短则6个月，长则两年就会实现。第二件事是具身智能机器人。这是我们第一次看到Astra能够以惊人的方式使用机器人。在传统认知中，我们甚至不知道机器人的泛化能力是否有效，必须针对特定任务进行训练，比如拿起我的麦克风；但Astra展示的是它在移动物体之前会先伸展、摆动。现在你看到了隧道尽头的曙光：通过暴力穷举，持续叠加算力与自我中心视角数据（egocentric data），我们就能通过机器人实现真正的AGI。而目前的市场基本上只计入了代码领域。
<details><summary>Original English</summary>
**>>**: Yeah. Uh so one sentence, right? I think we will have a permanent uh compute shortage at least. So I can see that until 2030. Now explain why. Okay. Right now the market if you look at there's like pre-training and post-trainining, right? But what is actually using compute? That's inference, right? Um it's mostly on the coding coding uh coding coding uh stuff from uh codecs to to clock code right I think that's priced in you also have multimodal which is the image gen and video gen you probably see that on reals on Tik Tok whatnot so that's those people already see but you got to understand uh talking to researcher RSI is coming very very soon and that means that compute or or AI is going to self-train and improve move on itself without human in the loop. So compute is demand is going to skyrock skyrocket and talking to a lot of prominent researchers their prediction is about from 6 months as short as 6 months uh to two years to have that completed. Second thing is the robotics right it's the first time we see that Astra is able to utilize robots in a phenomenal way. Traditionally we actually didn't even know whether uh ro generalization of robots works. You have to train on a specific task like picking up my mic for example. But Astra has shown is it stretches first. It wiggles before moving things. So now you see the light at the end of the tunnel which is okay brute force right continue to layer on compute uh egocentric data and we can get to true AGI with robotics right and what is the market now market is only on coding basically
</details>

**>>**: 没错，更不用说消费级需求了。
<details><summary>Original English</summary>
**>>**: right and and not to mention like muse and instinct which is consumer uh demand that hasn't picked up right so we only priced in on the business side we didn't talk about robotics we didn't talk a consumer, right? Uh and then also RSI. Incredible. We are just the beginning.
</details>

**>>**: 好的。各位，请记住所有的这些预测，明年再回来看看到底谁预测准了。
<details><summary>Original English</summary>
**>>**: Okay. All right, everyone. So, memorize all those predictions and come back next year and see who was right.
</details>

**>>**: 谢谢大家。
<details><summary>Original English</summary>
**>>**: Thank you. Thank you.
</details>