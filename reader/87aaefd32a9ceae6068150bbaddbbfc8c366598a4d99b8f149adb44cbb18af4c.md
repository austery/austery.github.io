---
author: The MAD Podcast with Matt Turck
date: '2026-06-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0NttU4CbyVs
speaker: The MAD Podcast with Matt Turck
tags:
  - neocloud
  - gpu-compute
  - scaling-laws
  - data-center-financing
  - ai-infrastructure
title: Neocloud 崛起：AI 计算基础设施的深度解析
summary: Lambda 联合创始人兼 CTO Stephen Balaban 深入探讨了 Neocloud 市场的现状与未来。他解释了为什么 GPU 计算从未真正成为商品，分析了从土地、电力到软件编排的垂直整合优势，并讨论了 AI 工厂的融资模式、规模定律的持续有效性，以及“一人一 GPU”的长期愿景。他还分享了 Lambda 从面部识别初创公司到价值数十亿美元云服务商的传奇发展历程。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Lambda
  - Nvidia
  - Amazon
  - Microsoft
  - Google
  - Oracle
  - Apple
  - SK Telecom
products_models:
  - H100
  - H200
  - B200
  - GB200
  - B300
  - V100
  - A100
  - GH200
  - VR200
  - GB300 NVL72
  - CUDA
  - CUDNN
  - NCCL
  - Opus 4.5
  - AlexNet
  - Dream Scope
  - Lambda Hat
media_books: []
status: evergreen
---
### 开场：Neocloud 的误解

**[Matt]**: 几年前在硅谷，如果你问大多数人，他们会说 Neocloud 将会成为一种商品，特别是因为 GPU 计算会被商品化。但快进到今天，情况似乎完全相反。Lambda 和你的几个竞争对手似乎都表现极佳。那么，当时的怀疑论者错在哪里，并且至今仍在错什么？

<details>
<summary>Original English</summary>

**[Matt]**: There was a moment in time in Silicon Valley a few years ago. If you had asked most people, they would have said that Neoclouds were going to be a commodity in particular because GPU compute was going to get commoditized. And if you fast forward to today, it seems to be exactly the opposite. Both Lambda but several of your competitors seems to be absolutely ripping. So what is it that naysayers got wrong then and continue to get wrong today?

</details>

**[Stephen Balaban]**: 最大的问题是，云服务不是一种商品服务。它是一种非常复杂、高度垂直整合的服务类型，涵盖了从土地许可、建设、高性能计算设计、软件、虚拟化到上层云服务的方方面面。世界上最大的公司，这些市值数万亿美元的企业，无论是亚马逊、微软、谷歌还是甲骨文，都从事云计算业务，原因就在于这是一门好生意。所以我认为，最根本的误解在于，人们以为这跟普通的云服务有点不同，但实际上，它是一种为 AI 时代设计的云服务。当然，也存在一些商品化的元素，GPU 的租赁价格确实在下降，但正如你所说，在某种程度上这并不重要，因为它只是蛋糕中的一层。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: The big thing is that cloud compute is not a commodity service. It is a very complicated, highly vertically integrated type of service that spans everything from land entitlement, construction, HPC, high performance computing, design, software, virtualization, cloud services on top. And there's a reason why the biggest companies in the world, these multi-trillion dollar market cap businesses, whether it's Amazon, Microsoft, Google, Oracle, are all in the cloud computing business is because it's a great business. And so I think that's like probably the fundamental thing that was misunderstood is that, oh, this is somehow a little bit different than a normal cloud service. But really what it was was it's a cloud service designed for the age of AI. But there is some element of commoditization right the price of rental of a GPU is going down but what you're saying is that to some extent it doesn't matter because it's only one layer of the cake.

</details>

**[Matt]**: 是的。所以，当我们看比如彭博社的 H100 租赁价格指数时，我认为值得深入探讨一下其方法论。我们在市场上实际看到的是，首先有两种不同的价格：一种是公有云按需价格，另一种是长期租赁价格。我认为一些指数没有正确考虑到这一点，因为我们实际看到的是非常稳定甚至还在上涨的长期租赁价格，以及非常稳定且上涨的按需租赁价格。所以，如果指数的编制方法偏向于长期合同（因为长期合同在交易量中占比更大），那么指数看起来就会下降，而实际上，这只是指数所覆盖的交易组合发生了变化。

<details>
<summary>Original English</summary>

**[Matt]**: Yeah. So when you look at for example I think it's like actually worth doing is to try to kind of dig into some of the methodology on for example an index like there's the index that's on Bloomberg for H100 rental prices. And what we're actually seeing in the market is that first of all there's two different rates. There's a public cloud on demand rate and then there's a long-term rental rate. And I think that some of these in indices don't properly take that into account because what we're actually seeing is a very consistent if not increasing long-term rental rate and very consistent and increasing on-demand rental rates. And so what happens is if the index mix for example if the methodology in the index biases towards long-term contracts being a bigger part of the volume that will look like a decline in the index when the reality is it's just a decline in the mix that the index is covering.

</details>

### 竞争优势：技术 vs. 融资

**[Matt]**: 太精彩了。我很好奇，作为 Neocloud 生态系统中的关键领导者，你如何看待市场演变？你们和其他参与者建立的竞争优势，有多少是基于技术，又有多少是基于融资竞赛？

<details>
<summary>Original English</summary>

**[Matt]**: Fascinating. So I'm curious about your thoughts as a key leading player in the Neo cloud ecosystem about how you see the market evolve. How much of the competitive advantage that you guys are building and other players are building is based on technology versus financing race.

</details>

**[Stephen Balaban]**: 这有几个不同的层面。首先，在云软件编排层有很多差异化和工作，这使我们能够将非常大的 GPU 集群分割开来提供给客户。例如，我们有一键集群产品，可以做到这一点。这在 Neocloud 领域是相当独特的。大多数其他 Neocloud 要么没有从网站启动集群的能力，要么最多只能提供 32 个 GPU。而 Lambda 设计的软件，可以通过网页界面提供从 16 到 4000 个 GPU 的集群。其次，在数据中心建设和设计方面也有创新，这同样非常重要，因为那是高性能计算设备之下的物理层。我们正在研究许多不同的方法来大幅缩短建设和启用新兆瓦级设施的时间。最后，正如你提到的，在金融方面也有创新，我们正在寻找新的、独特的方式来为这些大型资本项目融资、承销和打包。所以，我认为创新发生在堆栈的每一层，这是一个非常复杂的协调型业务。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: There's a few different layers on it which is there's a lot of differentiation and work that's being put into for example the cloud software orchestration layer which allows us to for example take a very large scale GPU cluster and partition it up for our customers. So we've got, for example, our one-click cluster product that allows us to do that. And that's something that's like quite unique in the Neocloud space. Most of the other Neoclouds either don't have the ability to launch a cluster from their website or max it out at say 32 GPUs. Whereas Lambda's designed a piece of software that allows us to give you anywhere from 16 up to, you know, 4,000 GPUs in a web interface. And then there's innovation on the data center construction and design side of things which is also really important right because that's like the physical layer underneath the high performance computing equipment and you know we're working on a lot of different ways to dramatically reduce the time it takes to construct and stand up new megawatts. And then there's as you mentioned innovation on the finance side of things where you know we're coming up with new and unique ways to finance underwrite package these large-scale capital projects really and so I think it's like innovation's happening on every layer of the stack and it's a very complex coordination style business.

</details>

**[Matt]**: 是的。你认为 Neocloud 生态系统最终会变成赢家通吃，还是可以容纳多个大型参与者？

<details>
<summary>Original English</summary>

**[Matt]**: Yeah. And do you think that ultimately the NeoCloud ecosystem becomes a winner take all or is there room for multiple very large players?

</details>

**[Stephen Balaban]**: 我认为绝对有空间容纳多个大型参与者。就像传统的云业务已经证明的那样，有空间容纳多个赢家和多个大型参与者。我认为根本原因在于市场结构。一般来说，当一个行业具有技术模式、资本形成模式和经济模式时，其市场结构往往趋向于寡头垄断。而具有更多网络效应模式的市场，则往往更倾向于单一赢家通吃。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I think it's absolutely room for multiple very large players just like the traditional cloud business has shown that there's room for multiple large winners and multiple large players. And I think that the fundamental reason for that kind of going back to well what drives I guess market structure and I'd say generally speaking when you have an industry that has like technology modes and capital formation modes and economic modes that tends to be oligopolistic in its market structure. When you have markets that have more sort of network effect modes, those tend to be a little bit more, you know, single winner take all.

</details>

### 建设不足与规模定律

**[Matt]**: 在你思考未来时，脑海中有什么样的情景？我们是在过度建设还是建设不足？没人知道。你怎么看？

<details>
<summary>Original English</summary>

**[Matt]**: What are the various scenarios in your head as you think about the future about how it all play out? Are we overbuilding? Are we underbuilding? Nobody knows. How do you think about it?

</details>

**[Stephen Balaban]**: 我认为我们总体上仍然建设不足。Neocloud 或市场中的大多数领导层人士都已经认识到，对大型语言模型的需求是贪得无厌的，它们可以做从担任助手到代码生成的一切事情。你可以回顾一下我过去的一些演讲，我当时就预言，在几个月到几年内，我们将达到一个可以投入资金、另一端产出软件的阶段。现在，当我们到达那个时间点时，我认为随着 Opus 4.5 的发布，情况已经非常清楚：我们拥有一个惊人的系统，可以吸收资金并产出软件。让我对未来需求如此有信心的一点是，我们仍然看不到规模定律的尽头。其核心理念是，投入更多计算，就能从模型中获得更高的智能水平。随着模型容量的增加，用更多的计算和数据进行训练，你就能获得更多的智能。只要这一点持续成立，我认为我们还有很长的路要走。很难预测规模定律何时会开始进入边际收益递减的曲线部分。但就目前而言，很明显我们将继续看到越来越强大的模型，这正在不断扩大可寻址市场的范围。最初，可寻址市场只是说，这对客户支持有帮助，是谷歌搜索的替代品。而现在，它已经成为许多软件工程岗位的替代品或巨大增强。随着这个范围的扩大，总市场和计算需求也在扩大，我认为我们仍在低估它。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Well, I think that we continue to be generally underbuilding. And the most people that are sort of in leadership positions at NeoClouds or within the market have been recognizing this, you know, sort of insatiable amount of demand for large language models to do everything from, you know, being an assistant to code generation. You know, you can kind of look back to some of the talks that I've given in the past around I kind of called, hey, in a couple of, you know, months to years, we're going to be at a point in time where you can put money in and get software out the other end. And now at that point in time when you were predicting when I was predicting that, it was maybe not as widely held of a belief. But now with you know let's say the release of Opus 4.5 I think it's pretty clear that we have an amazing system that can take in money and output software and the I think the part which makes me feel so confident that there's going to continue to be demand is that we continue to see no end to the scaling laws which are like the underlying idea that you put more compute in and you get better intelligence levels out of your models. You know, as you increase the capacity of the model and train it with more compute, train it with more data, you get more intelligence out. And as long as that continues to hold, I think that we still have in store for us, it's hard to predict exactly when scaling laws might start to reach sort of a diminishing marginal return type of part of the curve. But right now it's very clear that we're going to continue to see more and more and more capable models that is kind of expanding the cone of the addressable market, right? Like originally the cone of the addressable market was all right, this is going to be helpful for customer support. It's a sort of substitute good for Google search and for other search online. And then now it's like well this is a substitute for a lot of software engineering roles or a huge augment to software engineering roles. And so as that cone expands the total market and the demand for compute expands and I think that we're continuing to underestimate it.

</details>

**[Matt]**: 你是否担心模型训练和推理的计算效率会提高 10 倍，以及这对建设规模意味着什么？

<details>
<summary>Original English</summary>

**[Matt]**: Do you worry about model training and model inference becoming I don't know 10x more compute efficient and what that would mean in terms of the buildup.

</details>

**[Stephen Balaban]**: 我认为，一般来说，如果你真的变得高效 10 倍，那仅仅意味着每个人都能处理 10 倍的 token，而在任何给定时间点，世界上的计算总量仍然是固定的。有趣的是，早在 2017 年，我们就经常讨论这个问题。人们担心可能会出现一种新的模型类型，比如更像随机森林的模型，你可以在 MacBook 上训练。人们一直担心模型方面会出现颠覆。但到目前为止，我们还没有看到这种情况。我们所做的一切都是基于规模定律，即扩展这种架构。所以，我不认为会出现巨大的模型颠覆导致计算需求下降的情况。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I think that generally speaking what you're seeing is that if let's say you do become 10 times more efficient, I think that that just means that everybody is able to process 10 times more tokens and there's still the same fixed amount of compute in the world at any given point in time. And so in the early days, it's funny, we used to talk a lot about this back in let's say 2017. Oh, well, maybe there's going to be some new type of model, let's say, that will look more like a random forest model, which the audience might some members of the audience might know. You can kind of train a random forest model on a MacBook, right? And there was this concern that was kind of persistently raised around like, well, okay, what happens if you have this sort of adjacent disruption on the model side of things? And so far, we haven't seen that. And again, everything that we're building towards is sort of based on these scaling laws, which is really about scaling up this architecture. So, I don't really foresee a very likely outcome where we have this huge model disruption that would cause a decline in the demand for compute.

</details>

### 瓶颈与社区关系

**[Matt]**: 目前你在建设 Lambda 时遇到的主要瓶颈是什么？是 GPU、电力还是电力供应？

<details>
<summary>Original English</summary>

**[Matt]**: Where's the main bottleneck these days that you're experiencing building lambda labs? Is that GPU, power, electricity?

</details>

**[Stephen Balaban]**: 我总是说，瓶颈在成为全球性问题之前，总是局部性的。一个开发项目可能受限于发电机或 UPS 系统，这取决于站点的具体情况。但纵观整个行业，主要的瓶颈基本上是“带电力设施的土地”，也就是那些已经获得许可、可以从公用事业公司获得一定兆瓦电力承诺的土地。然后当然是数据中心本身，以及其中的机电管道设备。这就是目前整个行业面临的主要瓶颈。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: So I always say that bottlenecks are always like kind of local before they're global in terms of you know one development might be bottlenecked on let's say generators or on UPS systems as a function of like the sort of idiosyncrasies of the site but broadly in the industry the thing that is the main bottleneck is basically land powered shell which is basically land that is entitled to have a certain amount of megawatt commitment from a utility and then of course the data center and the mechanical, electrical and plumbing equipment, the MEP equipment that goes into that data center. And so that's the main bottleneck that we're seeing in the industry right now I'd say across the board.

</details>

**[Matt]**: 全球社区反对数据中心的运动有多真实？你认为应该如何回应？

<details>
<summary>Original English</summary>

**[Matt]**: How real is the movement against data centers from the global community and how do you think about how to respond to it?

</details>

**[Stephen Balaban]**: 这在新闻中确实很热门，而且非常真实。我认为，任何大型资本项目所在的社区，无论是发电厂、太阳能农场、数据中心还是配送中心，都希望有发言权。总的来说，我花了很多时间阅读社区的评论，人们想要工作，想要税收收入。任何大型资本开发都会带来大量的税收、就业和投资。我认为他们真正想要的是在项目开发过程中拥有发言权。让他们的声音被听到，让开发商真正了解社区，这很重要。另一件需要记住的事情是，存在大量错误信息。例如，每一个现代部署的 Blackwell 或 Rubin 级 GPU，通常都采用封闭的、直接到芯片的液冷系统，连接到干冷器，这意味着几乎没有蒸发。它不使用蒸发冷却，而是使用不消耗大量水的干冷器系统。除此之外，大多数数据中心开发项目还为电网带来了大量电力。它们要么建设表后电力，要么建设电池储能系统。它们带来了所有这些辅助效益，可以加强和巩固电网，并最终在长期内维持社区所承担的成本。所以，我认为有一条非常清晰的路径来传播更多关于数据中心带来什么的事实，因为错误信息太多了。你会看到人们谈论数据中心消耗大量水。蒸发冷却塔可能会蒸发大量水，但实际上，美国的新建项目几乎都不再使用蒸发冷却来为这些闭环直接到芯片的液冷系统降温了。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Well, it's certainly it's like very popular in the news right now. I'd say that it's definitely very real. I mean, I think that rightfully communities that host any type of large capital project, whether it's a power plant or a solar farm or a data center or a distribution center, right? Those communities want to have a seat at the table. I'd say in general though, I spend a lot of time reading through a lot of the comments from communities and people want jobs. They want tax revenue. Any major capital development is going to bring a lot of tax revenue and it's going to bring a lot of jobs and it's going to bring investment into their community. And what they really are voicing I think is one is having a seat at the table while this stuff is being developed. I think that's an important thing just to have their voices heard and that the developers coming in and actually understanding the community. The other thing to kind of keep in mind is that there's a lot of misinformation out there. So for example, every single modern deployment of let's say a Blackwell class or a Rubin class GPU, you know, the VR GBN VR GPUs, these are often times in a closed direct-to-chip liquid cooling system that's connected to a dry cooler, which means that there's almost zero evaporation. It's not using evaporative cooling. It's using a dry cooler system that does not consume a lot of water. And on top of that, most of these data center developments are bringing a ton of power to the grid. They're either standing up behind the meter power. They're standing up and bringing battery electric storage systems to the grid. And they're bringing all these sort of ancillary benefits that strengthen and fortify the grid and also, you know, eventually in the long term will maintain the costs that are being experienced by the community. And so I actually think that there's a very clear path towards maybe spreading more of that fact around what does a data center bring because there's just a lot of misinformation. You'll see people talking about how data centers consume a lot of water. Well, an evaporative cooling tower might evaporate a lot of water, but practically no new builds in the United States are using evaporative cooling for doing these closed loop direct to chip liquid cooling systems.

</details>

**[Matt]**: 你认为我们整个行业在向外界解释这一点方面做得很糟糕吗？因为这些问题反复出现，而且似乎在加速，但从技术角度来看，很多讨论都基于过时的信息。

<details>
<summary>Original English</summary>

**[Matt]**: Do you think we do a terrible job as an industry explaining this to the broader world because like those things keep coming back and they seem to be accelerating but then when you have the discussion there from a technical standpoint a lot of this is just simply based on museum information as you just said.

</details>

**[Stephen Balaban]**: 我认为每个人都在努力改善这种沟通。这只需要清晰的思考，写下好处和成本，然后清晰、直白地呈现给社区，让他们就能在自己的社区想要什么样的工作和开发做出好的决定。

<details>
<summary>English</summary>

**[Stephen Balaban]**: I think that everybody's trying to get better at that kind of communication. And it just takes some clear thinking, writing down what are the benefits, writing down what are the costs and presenting that clearly and plainly to a community so they can make a good decision about, you know, what kind of jobs and what kind of development they want in their communities.

</details>

### 计算单元与芯片价值最大化

**[Matt]**: 我们来深入探讨一下。人们谈论 FLOPS、GPU 小时、Token 和 MFU。思考计算单位的最佳方式是什么？

<details>
<summary>Original English</summary>

**[Matt]**: Let's open the hood for a minute. People talk about things like flops and GPU hours and tokens and MFU. what is the best way to think about a compute unit?

</details>

**[Stephen Balaban]**: 这很有趣。我喜欢从物理学的角度，用国际单位制来分解。左边是所有能源生产，右边是某人消耗的 Token，最右边可能还有使用 Token 的应用层。左边是每秒进入的光子或天然气分子，然后通过发电厂或太阳能农场转换成焦耳/秒，也就是电功率的度量。然后焦耳/秒在引擎中有一个效率水平，那就是引擎效率。有趣的是，MFU 百分比就像是这个链条高端的一个效率指标。发电厂或太阳能电站将其转换成焦耳/秒，也就是瓦特，由整个数据中心消耗。数据中心本身需要冷却，这就是 PUE，它是衡量数据中心效率的指标。然后你放入服务器、网络和存储设备，它们产生每秒浮点运算次数，即 FLOPS。这就是被消耗的东西。FLOPS 容量被模型构建者用于训练或推理模型，然后从 FLOPS 转换为每秒 Token。在此之上，最终客户可能还有一定的效率，将这些 Token 转化为真正的智能。这就是我认为的整个端到端管道。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Yeah, it's interesting. You know, you said a few different terms and I always like to kind of break it down from like a physics perspective into like the SI terms. So okay on the left hand side is all of the energy production and then on the you know my right hand side is sort of tokens being consumed by somebody and you know maybe you can even have the application layer on the far right of that that's using the token. So on the left hand side you've got either photons coming in per second or molecules of natural gas coming in per second and then that through a power plant or a solar farm gets converted into joules per second which is a measure of electrical power production and then the joules per second obviously in engines there's a level of efficiency and that's a engine efficiency. It's interesting because like the MFU percentage is kind of like an efficiency up on the higher end of that chain. The power plant or the solar plant then converts that into joules per second which is watts which is consumed by the entire data center. the data center itself needs to cool itself and that's the PUE and that's actually the efficiency metric that you can use to measure a data center on and then you put the servers and all the different networking and storage gear in and that's producing floating-point operations per second or flops per second. Okay, that is what gets consumed. The flops per second capacity is what gets consumed by let's say a model builder when they're training a model or when they're inferencing a model and that gets turned from flops per second into the tokens per second. Then on top of that tokens per second you might have some level of efficiency that the end customer is actually turning those tokens into real actual intelligence. That's like the entire pipeline I would say from end to end.

</details>

**[Matt]**: 非常有帮助。如果两家公司从根本上使用相同的芯片，它们如何从中提取更多价值？需要做什么来最大化芯片的效用？

<details>
<summary>Original English</summary>

**[Matt]**: If two companies have the same chip fundamentally, how do they extract more value from it? What needs to happen to maximize the usefulness of that chip?

</details>

**[Stephen Balaban]**: 如果你看一下一个 GPU 小时的成本结构，以 H100 为例，其中最大的部分是折旧。你可以把利用率指标看作是一个乘数因子，即 1/利用率。所以，如果你的资本资产只有 50% 的时间被使用，那么每小时的折旧费用就会翻倍。因此，我认为公司获得独特优势的首要方法是，如何构建一个受人喜爱的云产品，从而驱动高利用率。除此之外，正如我们之前提到的，按需计算市场的零售价格显然远高于批发价格。零售就是按需使用，像正常的云服务一样启动和关闭 GPU。批发则是例如一次性购买 10,000 个 GPU 使用 5 年。因此，我们在 Lambda 做的一件事就是，弄清楚如何从我们的资本部署中获得最高的美元利用率和百分比利用率。这通过构建出色的云软件来实现，让人们可以轻松地启动和关闭。例如，如果没有那个云软件，你就无法按小时出租，无法获得零售价格。实际上，很多 Neocloud 都处于这种状态，他们甚至没有运行真正云服务的基础设施。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: If you look at the cost structure of let's say one GPU hour of time, you know, we're talking about H100s. The largest part of that cost structure is the depreciation that is associated with that GPU hour. And basically you can think of a utilization metric as being like kind of a multiplicative factor on that. So one over the utilization. So if you use your capital asset 50% of the time, you will have on a per hour basis twice the amount of depreciation expense associated with that. And so I think that the number one way that companies are gaining a unique advantage is, well, how can I build a cloud product that is beloved by people that is going to drive a high utilization. And in addition to that the market as we mentioned earlier for on-demand compute basically the retail pricing is obviously much higher than the wholesale pricing. So the retail is like on demand, spin up a GPU, spin down a GPU, normal cloud service. The wholesale is sort of buying 10,000 GPUs for 5 years for example. And so one of the things that we do at Lambda is really try to figure out, hey, how can we get the most dollar utilization and percentage utilization out of the capital deployments that we do and that's by making great cloud software that makes it easy for somebody to spin it up and down. So for example, if you don't have that cloud software, you can't rent you can't extract a retail pricing, right? you know, you cannot rent it out to somebody for an hour because you just simply don't have the means to be able to do that. And actually, a lot of NeoClouds are in that position where they don't even have the infrastructure to be able to run a real cloud service.

</details>

### GPU 网络与前沿推理

**[Matt]**: 所以，你有 GPU，但这些数据中心工作的很大一部分是将 GPU 转化为 GPU 网络。你能在高层解释一下这是如何工作的吗？

<details>
<summary>Original English</summary>

**[Matt]**: So, you have GPUs, but like a big part of how those data centers work is transforming GPUs into networks of GPUs. Do you want to explain at a high level how that works?

</details>

**[Stephen Balaban]**: 总体思路是，你有一个大规模的高性能计算集群，里面有一堆，比如 Nvidia GB300 NVL72 机架，每个机架有 72 个 GPU，通过 NVLink 连接在一起。然后机架之间通过 InfiniBand 或高速以太网连接。这本质上就是所谓的“脊叶拓扑”，基本上意味着这是一个完全无阻塞的网络，每个 GPU 上的每个端口都可以与网络中的任何其他 GPU 通信，它是全连接的，能够在每个单独的 GPU 之间提供最大带宽。这个集群对于训练大型模型很有用，也适用于推理。我们在 Lambda 有时称之为“前沿推理”，它基本上是一个分布式推理问题，模型会被分片，采用某种分片策略，使其能够在多个 GPU 上运行，并利用高速 InfiniBand 或以太网互连进行通信。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: The general idea is that you've got a large scale high performance computing cluster of a bunch of you know let's say Nvidia GB300 NVL72 racks that's 72 GPUs all worked together via Nvlink and then there's a connection between the racks that's either infiniband or high-speed Ethernet and that is essentially what's called the spine leaf topology which is basically a way to say hey this is a completely non-blocking every port on every GPU can talk with every other GPU in the network it's fully connected and it's able to provide maximum bandwidth between every individual GPU and that cluster is useful for training large models it's also useful for inferencing so frontier inference as we sometimes refer to it at lambda is basically very much a distributed inferencing problem where they actually will fragment or shard the model there'll be some sort of sharding strategy for the model where it can be essentially run on multiple GPUs and it uses that high-speed infiniband or Ethernet interconnect to do that communication.

</details>

**[Matt]**: 那么，前沿推理是针对最先进的推理模型，比如要求更高的那种吗？

<details>
<summary>Original English</summary>

**[Matt]**: And so what is a frontier inference is that in France for the most advanced reasoning models like the more demanding.

</details>

**[Stephen Balaban]**: 是的。但它不一定与推理模型相关，更多的是指一个非常大的前沿模型，这通常是世界上三到四家公司在进行推理时的领域。这是一件非常复杂的事情，它充分利用了所有可用的互连。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Yes. Well, you know, it's not necessarily associated with reasoning models so much as like just a very large frontier model that is, you know, kind of the domain of let's say three companies in the world or four companies in the world when they're doing their inference. It's a very complicated thing that is fully utilizing all of the interconnection that's available.

</details>

**[Matt]**: 你描述的前沿推理，在概念上与训练时发生的事情是一样的吗？都是将任务大规模分布到大量 GPU 上。从计算角度来看，训练运行期间会发生什么？

<details>
<summary>Original English</summary>

**[Matt]**: And what you describe for Frontier in France is that conceptually the same thing as what happens for training. This concept of just distributing a task massively across a bunch of GPUs. What happens during a training run from a compute standpoint?

</details>

**[Stephen Balaban]**: 一般来说，在进行训练运行时，模型的反向传播和前向传播之间会有分工。反向传播可能占计算量的三分之二或更多。前向传播，基本上和推理一样，是剩余部分。过去一段时间的一个认识是，你为大规模训练运行所希望拥有的基础设施类型，可以复用于该模型的推理。我所说的前沿推理以及推理以分布式方式进行，意味着你会有一个混合专家模型，会有不同的分片策略，将那些专家放到不同的服务器和 GPU 上。模型可能非常大，无法装在一个机架甚至一台服务器上。它们可能需要分布到不同的服务器上，仅仅是为了进行前向推理。这就是分布式前沿推理发挥作用的地方。因为如果你运行的是一个小模型，比如 Llama，或者一些量化后的小模型，它们可以装在一个 GPU 上。但像 Opus 和 Chad JBD 5.5 这样的模型就无法装在一个 GPU 上。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Generally speaking, when you're doing a training run, you might think there might be some sort of split between the backwards pass and the forward pass on the model. And the backwards pass might be, let's say, 2/3 or more of the compute. And the forward pass, which is basically the same thing as inferencing, is the remainder. And one of the realizations that I think has been made over the last bit of time is that the type of infrastructure that you'd want for doing a large scale training run can be reused to do the inferencing of that model and what I mean by the sort of frontier inference and the fact that the inferencing is being done in a distributed way you know you'll have like a mixture of experts model and there'll different basically sharding strategies for how you put those experts onto different servers and to different GPUs. And you know the models can be very large. They may not fit on one single rack or you know they may not fit on one single server. They might need to be distributed across different servers to even just do the forward inference pass. And so that's where sort of distributed frontier inference kind of comes into the picture, right? Because like if you're doing a small model, let's say llama that the users might be familiar with or some of the quantized small models can fit on a single GPU. Okay. Well, let's just say that like Opus and Chad JBD 5.5 can't fit on a single GPU.

</details>

### 计算成本与芯片堆栈

**[Matt]**: 当我们考虑计算成本时，什么最花钱？是模型大小、内存带宽、延迟，还是非常大的上下文窗口会改变计算成本？

<details>
<summary>Original English</summary>

**[Matt]**: And when we think about compute costs, what costs the most money? Is that model size? Is that memory bandwidth? Is that latency? Does context window and like those very very large context window do they change anything to the compute cost?

</details>

**[Stephen Balaban]**: 正如我提到的，像这样的云服务的单位成本中最大的部分是折旧费用。其中，主要是数据中心内服务器的物料清单，这远远是成本的最大部分。如果谈论资本堆栈，可以追溯到发电，每兆瓦 2 到 3 百万美元，每吉瓦 20 到 30 亿美元用于发电厂。建设数据中心的成本是每吉瓦 100 到 150 亿美元。而计算服务器每吉瓦的成本在 350 到 450 亿美元之间。所以你可以看到，服务器部分显然远远是最大的，这是折旧费用的一大部分。其中，服务器和集群的物料清单主要是 GPU。如果你分解 Nvidia 的物料清单，就能更好地了解这些成本的来源。但在最近一段时间，内存费用上涨了很多，而且供应商很少，比如 HBM 内存只有三星和 SK 海力士。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: As I mentioned, like the biggest component of the unit cost for a cloud service like this is the depreciation expense. And within that, is basically some sort of bill of materials for the servers that are in the data center, which is by far and away the biggest portion of the cost. If you talk about the capital stack, let's say you can go back down to power generation, 2 to 3 million a megawatt. 2 to 3 billion a gigawatt for a power plant. The data center is between 10 and 15 billion a gigawatt for building the data center. And then the compute the servers can be anywhere from 35 to 45 billion a gigawatt. So you can see the server portion is obviously by far and away the largest and that's like a big part of the depreciation expense and then within that obviously you have the server and cluster bill of materials which is primarily the GPUs. If you were to kind of break down Nvidia's bill of materials, then you can kind of get better allocation towards where those costs are coming from. But certainly in the most recent period of time, memory expenses, you know, memory has gone up a lot in price and there's very few vendors, right? You know, for HBM memory, but Samsung, Hynix.

</details>

**[Matt]**: 所以，你们是 Nvidia 的大客户。具体来说，你们主要使用哪些芯片？你们的芯片堆栈是什么样的？

<details>
<summary>Original English</summary>

**[Matt]**: So, you guys are a big Nvidia shop at a precise level. You mentioned some of the names, but like which chips do you use mostly? What's your kind of chip stack?

</details>

**[Stephen Balaban]**: Lambda 非常喜欢 Nvidia 的产品。它们是唯一一个在每个主要云平台都可用的服务器和芯片供应商，这是一个巨大的平台优势。我们一直坚持使用 Nvidia 生态系统来部署所有芯片。我们拥有从 V100、A100、H100、H200、B200、GH200 或 GB200、B300 到即将推出的 VR200 的所有产品。我们使用生态系统中的一切。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Yeah, so Lambda really loves Nvidia's products. I mean, they're the only server provider, the only chip provider that is available in every single major cloud platform, which is a huge platform advantage. And we've stuck with the Nvidia sort of ecosystem for all the chips we've deployed. And we've got everything from V100s, A100s, H100s, H200s, B200's, GH200s or GB200, B300s, and VR200's coming soon. And so we use everything in the ecosystem.

</details>

**[Matt]**: 你认为现在或不久的将来，我们会进入一个多芯片的世界吗？除了 Nvidia，还有其他玩家的空间吗？

<details>
<summary>Original English</summary>

**[Matt]**: Do you think that today or in the near future we're going to be in a multi-silicon kind of world? Is there like room for different players beyond Nvidia?

</details>

**[Stephen Balaban]**: 我认为我们已经处于一个存在大量竞争的世界，来自那些市值数万亿美元的巨头公司，它们都在争夺同一件事：成为世界上运行和训练神经网络最好的芯片。Nvidia 构建了一个伟大的产品，获得了广泛的发行，并拥有一个热爱他们产品的庞大开发者平台。你必须考虑的不仅仅是芯片的成本，还有整个软件生态系统和已经开发出来的东西。人们谈论 Nvidia 的护城河，其中一个巨大的护城河就是 CUDNN 堆栈。不仅仅是 CUDA，CUDA 是我们都在其中游泳的水，但 CUDNN 内置了如此多的矩阵乘法例程优化。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Well, I mean, I think that we're already in a world where there's a huge amount of competition from massive massive multi-trillion dollar companies and they're all trying to fight for the same thing, which is to be the best chip in the world for running and training neural networks. Essentially, Nvidia's built a great product that has gotten a lot of distribution and has a great platform of developers who love what they do. And you have to take into account not just the cost of the chip, right? The price of the chip is one aspect, but you know, you have to take into account the entire software ecosystem and what's been developed. So, one of the big people talk about like what's Nvidia's moat? One of the big moats they've got is just the CUDNN stack. It's not just CUDA. You know, CUDA is sure that's like the water we all swim in, but like CUDNN has got so many matrix multiplication routine optimizations baked into it.

</details>

**[Matt]**: 为了让大家都理解，什么是 CUDNN？

<details>
<summary>Original English</summary>

**[Matt]**: What is CUDNN for everyone to understand?

</details>

**[Stephen Balaban]**: CUDNN 是 CUDA 深度神经网络库。你可以把它想象成一个高度调优的矩阵乘法引擎。如果你只是简单地实现矩阵乘法算法，你可能会达到一定的 FLOPS 水平。但 Nvidia 已经调优了它的每一个方面，使用了 Winograd 滤波等各种算法来加速矩阵乘法。CUDNN 意味着你不需要自己去做这些优化。这是其中一个方面。另一个是 NCCL，他们的网络优化库。它会感知你的网络拓扑和连接性质，无论是 InfiniBand 还是以太网，并会建议一个优化的例程来执行 all-reduce 和 broadcast 等操作，这些是用于我们之前讨论的训练和推理分片的 Open MPI 原语。所以，我认为这种软件堆栈对于许多芯片领域的新进入者来说是很难克服的。但就像我说的，我们已经处于一个存在多种芯片选择的世界。世界上最大的实验室正在使用多种不同类型的芯片进行推理和训练。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: So, CUDNN is the CUDA deep neural network library and it's basically Nvidia's you can think of it like a highly tuned engine for matrix multiplication. And basically, if you were to just sort of naively implement the matrix multiplication algorithm, you would maybe get a certain level of floating point operations per second. But they've gone and tuned every single aspect of it and come in and do Winograd filtering or a bunch of different algorithms that you would apply to speed up matrix multiplication and CUDNN means that you don't have to go and do the optimization yourself and so that's one aspect the other one is NCCL which is their networking optimization library where it will sense the topology and the connected nature of your network, your Infiniband or your Ethernet network and it will suggest an optimized routine for doing reduce all and broadcast the different what are called open MPI primitives which are used for that sharding that we were talking about for both training and for inference. And so that's the kind of software stack that I think really is hard for a lot of the new entrants in the chip space to overcome. I think we're already, like I said, we're already in a world where there are multiple options for silicon. You know, the biggest labs in the world are using multiple different types of chips to do their inferencing and training on.

</details>

### 存储、网络与数据中心内部

**[Matt]**: 用通俗的语言解释一下，我们谈到了芯片，但堆栈的其他部分，比如网络和存储。请带我们了解一下它是如何工作的。

<details>
<summary>Original English</summary>

**[Matt]**: What would be a plain English definition? We talked about the chips, but like the rest of the stack, the networking and the storage. Just walk us through how it works.

</details>

**[Stephen Balaban]**: 当你运行一个云服务时，你会训练模型或上传训练好的模型，然后准备开始大规模推理。你需要一个地方来存放你的数据，无论是用于训练的数据，还是来自终端客户的流式数据。因此，拥有高速存储是非常重要的。Lambda 提供了一种 AI 优化的文件系统服务，它比标准的云文件系统（比如传统的 NFS）要快得多。这是一个高度优化的并行文件系统，专为高性能读写而设计，主要是高性能读取，这是大部分工作负载。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: When you're running a cloud service, you'll train your model or you'll upload your trained model and you're ready to start doing large scale inferencing. Well, you're going to need a place to put your data whether it's the data that you're using to train with or whether it's the data that's coming in and streaming in from your end customers. And so having high-speed storage is like a really important part of it. So, Lambda offers the basically AI optimized file system service that is significantly faster than like your standard let's say cloud file system which is maybe more of a traditional NFS type of thing. This is like a highly optimized parallel file system that's designed for high performant read and writes and mostly high performance reads. That's like the kind of most of the workload.

</details>

**[Matt]**: 那是你们完全自建的吗？

<details>
<summary>Original English</summary>

**[Matt]**: And that's something you build in-house completely.

</details>

**[Stephen Balaban]**: 嗯，完全自建的定义是什么？我们从未在这家公司自己制造过 PCB，也没有编写过例如我们用于虚拟化的 KBM。我们既有使用现成硬件的商品，也有在上面安装软件的，还有一些存储合作伙伴。但总的来说，我们在云上所做的一切，我认为都是我们借助更广泛的生态系统自己动手做的，因为除非你是在开采超纯硅并制造自己的 ASML 光刻机，否则没有真正的“自己动手”这回事。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: We have I mean well in-house completely right it's like you have to ask the question like what is the definition of in-house completely right you know like we've never spun a PCB at this company we have not authored for example you know we use KBM for our virtualization for example right and so you know what we have both commodity off-the-shelf hardware that has software installed on top of it for our some of our storage we have some storage partners that we work with as well. But you know generally speaking everything that we do on the cloud I would generally say is something that is like we rolled it ourselves with the help of the broader ecosystem because again there's no such thing as rolling it yourself unless you're like mining ultra pure silicon and then coming up with your own ASML.

</details>

**[Matt]**: 是的，那是高度优化的存储。还有什么？网络部分和其他部分呢？

<details>
<summary>Original English</summary>

**[Matt]**: Yeah, that's the highly optimized storage. What else? The networking part and what other pieces?

</details>

**[Stephen Balaban]**: 我之前谈到过我们的云集群产品。你可以这样理解：你有一堆 GPU，比如一个 10,000 个 GPU 的集群。我想把这个集群分区。它由一堆 GPU、一些 CPU 服务器（用于编排集群）和一些存储组成。所有的 CPU 服务器、存储服务器和 GPU 服务器都通过存储互连，以便快速读写。这种通信发生在所谓的带内网络上。然后是计算结构，我之前提到过，所有的权重和特征激活都在这个计算结构中共享。还有一个带外监控网络，用于访问 BMC 或 DPU。当你试图创建一个 10,000 GPU 集群的子分区时，你需要同时分区带内、带外和计算结构。所以，这种复杂的协调，从一堆裸金属系统到一个虚拟化系统，拥有 RDMA（远程直接内存访问），允许它们不仅从磁盘，而且从彼此的内存（GPU 的 HBM 内存）快速读写，允许数据直接从一块 GPU 传输到另一块 GPU，而无需经过 CPU。让这一切工作是一个巨大的软件工程。这又回到了最初的问题：人们对 Neocloud 有什么误解？首先，答案是大多数 Neocloud 没有这种技术。大多数 Neocloud 没有投入数千万到数亿美元的软件投资来构建一个真正的云系统，来分区这样的高性能计算环境。然后还要让这一切与存储协同工作。总之，这大致概括了所需的步骤。你可以思考一下现代 AI 数据中心的所有不同活动部件。人们谈论 AI 数据中心，但你真的需要深入一层。因为如果你去问一个传统的数据中心房东里面发生了什么，他们会说，“我们是搞房地产的，我们把这事外包给总承包商了，但总承包商当然也不知道里面发生了什么。” 实际上是他们的租户才知道。这就是 AI 数据中心内部实际发生的事情。这也回到了社区问题。如果人们更多地知道，这个 AI 数据中心实际上只是在处理我发出的 ChatGPT 请求，他们甚至没有意识到这就是 AI 数据中心的作用。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: So, I was talking about this one cloud cluster product that we've got and the way just for everybody to think about this is like okay well look you've got a bunch of GPUs. Let's say you've got a cluster of 10,000 GPUs. Well, I want to partition that cluster up. And so what it is is it's a bunch of GPUs. some CPU servers as well because you need to have an orchestration fleet as well and then you've got some storage and all of the CPU servers and the storage servers and the GPU servers are interconnected with the storage so they can quickly read and write from it and that communication happens over what's called the inband network and then there's the compute fabric which is where I was talking about where all of the sort of weights and feature activations are being shared throughout that compute fabric and then there's an out-of-band monitoring network where you've got access to whether it's BMC or some of your DPUs and when you are trying to create a subpartition of a 10,000 GPU cluster you need to simultaneously partition the inband the out of band and the compute fabric okay so like that complex coordination between we've got a bunch of bare metal systems to hey we've got a virtualized system that has what's called RDMA, remote direct memory access that allows them to read and write quickly not just from the disks but from each other's memory the GPU's HBM memory and allow them to do that sort of direct memory access allowing it to go directly from a GPU to another GPU without getting copied to the CPU for example. Having that all work is an immense software undertaking and this is going back to the original question like well what are people not getting about Neoclouds? Well, first of all the answer is that most Neoclouds don't have this kind of technology. Most Neoclouds have not made the really it's like kind of high tens to hundreds of millions of dollars of software investment that you need to make to build a real cloud system that can partition a high performance computing environment like this and then to have it all work with the storage. Anyways, I guess that sort of summarizes the steps that you need and kind of you can think about all the different moving parts of a modern like how does an AI data center work? People talk like AI data center, but really you have to kind of go down that one next level down, which is because if you were to, by the way, if you were to ask an AI data center landlord, a traditional one, what's going on inside of the data center, they'd be like, well, look, we're real estate people, and we really outsource this to the GC, but the GC doesn't know, of course, anything that's going inside. And this is then it's their tenants who know. So this is what's actually happening inside of an AI data center and then it serves the result like also going back to the community stuff. If people knew a lot more about like well this AI data center is actually just serving the chat GPT request that I'm giving it, right? Like sometimes they don't even realize that that's actually what an AI data center does.

</details>

### 垂直整合与国际化

**[Matt]**: 你提到了租户。你们是租用数据中心，还是也自己拥有一些建筑？这在整体战略中处于什么位置？

<details>
<summary>Original English</summary>

**[Matt]**: So you mentioned tenants. Do you rent them? Do you also own some building some? and where does that fit in the overall strategy?

</details>

**[Stephen Balaban]**: 最初，我们主要是租户。但后来我们开始涉足为其中一些数据中心融资和建设。现在我们正在走向完全垂直整合，我们自己识别土地，带着设计方案（即建设数据中心的所有工程图纸）参与进来，融资并建设数据中心，放入服务器，然后将其与世界上主要计算消费者之一的长期承购协议关联起来，并为其提供全部融资。所以，Lambda 正在走向完全垂直整合，这很棒，因为我们能够再次将工程思维带到这个历史上主要由房地产人士处理的问题上。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Yeah. So, initially we started off as being primarily a renter and we've actually started to get into the business of financing some of them the construction of them ourselves as well as you know we're going now into full vertical integration where we are identifying land coming to the table with a basis of design which is basically all the engineering diagrams to construct the data center financing and constructing that data center, putting the servers in, and then associating that with a long-term offtake agreement with one of the major compute consumers in the world and financing it all. So, like we're getting into full vertical integration at Lambda and it's been great because we've been able to kind of again bring that engineering mindset to this problem which was historically mostly run by people in real estate.

</details>

**[Matt]**: 在你们自己的数据中心里，你们是唯一的租户吗？还是说部分想法是也可以租给其他人？

<details>
<summary>Original English</summary>

**[Matt]**: In your own data centers, are you the sole tenant or is part of the idea that you can also rent some to others?

</details>

**[Stephen Balaban]**: 在我们的许多数据中心，我们是唯一的租户。对于计划建设的数据中心，我们目前还没有将空间租给其他人的计划。所以，我们并不试图进入数据中心租赁业务。也许未来可以想象，我不会完全排除这种可能，但现在，我们必须专注于为 Lambda 提供服务市场所需的计算能力。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: In a lot of our data centers, we are the sole tenant. In terms of the data centers that we're planning on constructing, we don't yet have any plans to lease that space to others. So, we're not trying to get into the leasing data center business. Maybe that's something that you can imagine down the road. I wouldn't write it out completely, but for now, we have to focus on providing Lambda with the compute that we need to service the market.

</details>

**[Matt]**: 顺便问一下，你们的国际化程度如何？

<details>
<summary>Original English</summary>

**[Matt]**: How international are you, by the way?

</details>

**[Stephen Balaban]**: 我们非常专注于北美。我们在加拿大、美国和墨西哥都有数据中心。我们主要专注于北美，尤其是美国。我们内部没有强烈的愿望去扩展到欧洲或亚洲太远的地方。我们与一些优秀的投资者如 SK Telecom 建立了合作关系，并在韩国首尔运营过一个数据中心，所以有一些国际经验。但现在，我们专注于美国市场，机会就在这里。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: You know, I'd say that we're very much focused on North America. And so we have data centers in Canada, United States, and Mexico. We're very much, like I say, primarily focused on North America, but really within, you know, that the United States obviously. And we haven't had this desire internally to try to go and expand into Europe or too far into Asia. We've done some partnerships with some of our great investors like SK Telecom and we have a data center that we've operated in Korea in Seoul. And so we have some experience with international but right now we're just like look let's focus on the US market. It's where the opportunity is.

</details>

**[Matt]**: 出于性能原因，是否需要像传统云那样靠近客户，建立多个区域？

<details>
<summary>Original English</summary>

**[Matt]**: Do you need for performance reasons to be close to the customer the way you need to have regions in cloud?

</details>

**[Stephen Balaban]**: 这非常有趣。很多人问我延迟是否重要。我可以告诉你什么重要，什么不重要。你可以看看你自己使用 ChatGPT、Claude、Grok 或 Gemini 的情况，你会发现很多任务，我发出指令，过一会儿回来拿研究报告，或者是一个长时间运行的 Agent 工作流，在这些情况下，延迟根本不重要，唯一重要的是每个 Token 的成本。这是一个非常有趣的变化。我认为传统的云业务非常注重延迟，因为某些应用的需求，但这批新的 AI 应用对延迟的敏感度要低得多。但有一个警告，那就是数据治理正变得越来越重要。很多国家希望其公民使用的 AI 计算能在本国境内运行，这样他们至少能有自己认为的控制权。这是一个因素，但从延迟角度来看，没有技术上的理由。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: You know, it's super interesting. A lot I get this question a lot and people they're like well does latency matter does so I'll tell you what matters and what doesn't matter. You can look at your own utilization of whether it's chatgpt or claude or grok or gemini and you can see hey a lot of the things that I'm doing I kind of shoot it off I come back later and there's a research report for me maybe it's a long-running agent workflow in those cases latency doesn't matter at all the only thing that matters is your cost per token that's all that matters. So that's been a really interesting change. I think that the old school traditional legacy cloud business was so latency focused because of some of the applications but this new fleet of AI applications are far less latency sensitive. So that's one. But there is the caveat which is this governance and data governance is becoming an important thing and a lot of countries are wanting to have the AI compute that their citizens are using be run out of their own country so that they can at least have their own perception of control or whatever and that is another element to it but I'd say that from the latency there's no technical reasons.

</details>

### 融资堆栈

**[Matt]**: 我们来谈谈融资堆栈。它大概是股权和债务的组合。这一切是如何运作的？

<details>
<summary>Original English</summary>

**[Matt]**: Let's talk about the financing stack. So presumably it's a commission of equity and and debt. How does it all work?

</details>

**[Stephen Balaban]**: 你可以把它分成两部分：为你的按需云融资，以及为承购协议（一种长期承诺）融资。对于按需云，看的是 Lambda 的信用质量。对于承购协议，看的是最终客户的信用质量。做法是，你把承购协议、你正在部署的那批 GPU、租赁或物业，打包成一个实体，然后可以去私人信贷市场，获得基于资产的贷款。有多种不同的方法。大多数情况下，是通过某种特殊目的实体来为这个特定部署融资，其风险很容易评估。有一个活跃的私人信贷市场。在按需云方面，它不像有投资级承购协议那样成熟，但它正变得越来越成熟。总的来说，债权人和贷款人开始真正理解 Nvidia 芯片的价值。因为你看，我们在 2023 年部署的 H100，现在出租的价格比 2023 年最初的时候还要高。所以，债权人开始关注这些资产，说：“哇，这是一个非常有价值的资产，而且很容易评估风险。” 当然，虽然他们是根据协议产生的实际现金流来承销，但作为一个资产类别，人们意识到这是一个非常好的机会。因此，债权人开始涌入这些交易。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Yeah. So the way that it works is that you could really fragment it into these two parts which is like financing your on demand cloud versus financing an offtake agreement which is like a longer term commitment. And on the on-demand cloud you're kind of looking at Lambda's credit quality. on the offtake agreement you're kind of looking at the credit quality of the end customer who's paying the bill and so what you do is you just take your offtake agreement you take this chunk of GPUs that you're deploying you take a lease or the property and you kind of put it into a box and you can go to the private credit markets and you can come up with an asset-based loan you can get a variety There's a variety of different methodologies for financing it. Most of it is just some sort of special purpose vehicle that's designed to finance this particular deployment with a very known and easy to underwrite which is basically just a fancy way of saying the finance term for just assessing the risks and the downsides of a particular credit investment. And there's a vibrant private credit market for that. On the on demand cloud side of things, it's not quite as mature as when there's a for example an investment grade offtaker agreement. But it's becoming more and more mature and in general creditors and lenders are really starting to understand the value of an Nvidia chip because, you know, you actually look at the chips that we deployed in 2023, H100s, we're now leasing those out at a higher rate now than we were originally in 2023. So, these creditors are starting to look at these assets and say, "Wow, this is an asset that is very valuable and also easy for us to underwrite." And of course, while they are underwriting towards the actual cash flows that are coming out of that agreement, just as an asset class overall, people are realizing that this is a really great opportunity. And so, creditors are starting to flock to these deals.

</details>

**[Matt]**: 你现在以更高的价格出租 H100，原因是什么？是因为计算需求如此旺盛，以至于人们会接受任何东西，还是产品的技术折旧比人们想象的要慢？是什么驱动了这一点？

<details>
<summary>Original English</summary>

**[Matt]**: You're renting an H100 at a higher rate because why? because the demand for compute is so rapid that people will take any or the technical depreciation of the product is slower than people thought. What drives that?

</details>

**[Stephen Balaban]**: 当然，高需求推高了市场价格，这是毫无疑问的基本规律。回到人们对这个市场的误解，有人说这些 GPU 有五年或三年的使用寿命，我甚至听人说过三年。这完全是错误的。我们有一些已经投入使用的 GPU，我们是最早的 Neocloud 之一。事实上，我们可能是唯一一个在其机队中拥有从会计角度已经完全折旧的 GPU 的 Neocloud。大多数人采用大约六年的会计折旧计划。但这不是可用寿命。可用寿命比会计折旧计划要长。真正重要的是经济可用寿命。我们开始看到，那些说“你会在 5 年内扔掉这些 GPU”的怀疑论者完全错了。他们完全错了，而且他们一直都错了。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Well, what's driving it? I mean certainly it's the demand being high increases the price that you're able to get in the market. There's no question about that fundamental law. Again, going back to what people didn't understand about this market, there was people who were saying, "Oh, well, there's a five-year lifetime or three-year lifetime." I even heard some people say three year lifetime for these GPUs. This completely false. You know, we have GPUs that we've commissioned and we're one of the earliest Neoclouds. In fact, we're probably the only Neocloud that actually has GPUs in our fleet that are fully depreciated from an accounting perspective, right? which is most people are adopting around a six-year accounting depreciation schedule. But that's not the usable life. The usable life is longer than the accounting depreciation schedule. And what really matters is the economic usable life. And so what we're starting to see is that the people who are the naysayers, oh this is going to be you're going to throw these GPUs out in 5 years are completely wrong. They're completely wrong and they've been wrong the entire time.

</details>

**[Matt]**: 你认为是否会出现，或者你已经看到某种计算单位的金融市场，有交易和衍生品？这正在发生吗？

<details>
<summary>Original English</summary>

**[Matt]**: Do you think there is going to be or do you already see happening some kind of financial market for compute units you know with trading and derivatives is that happening

</details>

**[Stephen Balaban]**: 我开始看到一些人开始研究一个活跃的现货市场。首先，你需要有一个现货市场，然后才能建立期货或其他更复杂的衍生品。我开始看到这一点。但根本上，我认为这个资产类别才刚刚开始成熟，债权人开始对投资于购买 Nvidia GPU 并将其部署到数据中心的信贷方面感到非常舒适。我们不需要搞得太复杂。我的部分观点是，这个市场正在成熟，未来可能会出现围绕 GPU 的更复杂证券。但我认为，现在人们开始意识到这是一个很好的信贷投资，这就是过去一年发生的变化，人们开始真正把它当作一个更成熟的资产类别来对待。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I'm starting to see some people start to examine what a maybe vibrant spot market you know first you need to have a spot market for something before then you can establish a derivative like a future or other more exotic things. I'm starting to see that. But fundamentally, I think that the asset class is just starting to mature and creditors are starting to become very comfortable with investing in the credit side of buying Nvidia GPUs and deploying them into data centers and we don't need to get too fancy with it. That's kind of like my part of my opinion is that I think that the market is starting to mature that may be an eventuality is having more complex securities that surround GPUs. But I think for right now people are starting to realize that it's a great credit investment and that's what's changed I'd say over the last year is that people have started to really treat it like a more mature asset class.

</details>

### Lambda 的起源故事

**[Matt]**: 也许快速回顾一下起源，因为我认为你实际上一直处于 AI 世界，但来自一个非常不同的角度，经历了多次转型。你们最初是做什么的，是什么时候开始的？

<details>
<summary>Original English</summary>

**[Matt]**: Maybe quickly just go back to the very origin because I think you've been in the effectively in the AI world the whole time but are coming from a very different angle with multiple pivots. What did you start with and when?

</details>

**[Stephen Balaban]**: 考虑到业务的复杂性、资本密集度以及它不符合传统模式，你可以理解为什么 Lambda 通常没有很多传统风险投资者。我们的所有投资者都做得非常好，但他们往往来自硅谷主流风投之外。回到起源故事，我于 2012 年创立了 Lambda，当时是一家面部识别软件公司。我训练卷积神经网络进行人脸和图像识别，并最终将其托管在 API 上。我当时在一个 4 块 Nvidia GTX 580 的工作站上训练这些卷积网络，那是我从一个朋友那里买的。这在当时是非常前沿的东西，大多数人并不相信当时被称为“深度学习”的领域。这受到了 2012 年 ImageNet 时刻的启发，甚至在那之前。我从 Google Code 上拉下了 CUDA convnet 仓库。Lambda 有多老，从 Google Code 还在的时候就能看出来。我拉下了 CUDA convnet 代码库并开始摆弄它。我很幸运，AlexNet 论文在 Lambda 成立的同一年发表。这绝非巧合。我们推出了一个空间识别 API，获得了数千用户，但并没有产生大量现金。作为初创公司复杂故事的一部分，我同时发现了 Zach 和 Nico，他们刚博士毕业，说“我们要创办一家公司”。我说，“让我帮你们，我跟你们一起工作一年，多学点神经网络。” 我帮助他们创办了一家名为 Percepio 的公司，我是那里的第一个员工，同时还在运营 Lambda。我们在 iPhone 上本地运行这些卷积网络，那是 2013 年。我们使用 GPU 图像库和直接的 OpenGL ES 着色器来运行它们。后来我离开去全职做 Lambda，大约一年后，他们被苹果收购了。所以，如果你知道 iPhone 上向上滑动图片就能识别人脸并搜索图库的功能，那可能就是通过那次收购最终整合到 iOS 中的一部分。之后，Lambda 继续发展。我们有过各种各样的产品，从 Lambda Hat 开始，那是一顶棒球帽，帽檐尖端嵌入摄像头，每 10 秒拍一张照片，用于收集图像和人脸识别数据集。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Well, you know, with the complexity of the business, you can now, you know, the complexity, the capital intensivity, just the sort of not fitting into a box and you can see why we've oftentimes not had a lot of traditional venture investors in Lambda. and all of our investors have done exceptionally well but they've kind of come from more often than not outside of traditional let's say mainline Silicon Valley VCs. So just going back to the origin story I started Lambda in 2012 and we were a facial recognition software company so I was training convolutional neural networks to do face and image recognition And we eventually hosted that on an API. I was training those convnets on a 4X Nvidia GTX 580 workstation that I had bought from a friend who had built it actually. And this was, you know, really pretty avant-garde stuff at the time. Most people didn't really believe in what was called the field called deep learning at the time. And that was inspired by the imagenet 2012 moment or that was even before that the Imagenet moment. You know I pulled the CUDA convnet repo off of Google code. That's how you know how old Lambda is is that Google code was still around and I pulled the CUDA convnet codebase and was like playing around with it. I got very lucky that the AlexNet paper had been published the same year that Lambda was founded. It's not a coincidence at all. We launched this space recognition API, got a couple thousand users, but it wasn't really generating a ton of cash. And sort of as part of that the complex story of startups, you know, in parallel, I was sort of I found these guys who had just graduated from their PhD programs the gentlemen Zach and Nico and they had said, "Hey, we're going to start a company." I said, "Hey, you know, let me help you guys out. I'm going to work with you for a year. I'm going to learn a little bit more about neural networks." And I helped him out on this company, helped them get a company called Percepio started. And I was the first employee there while I was running Lambda. And we were running these convnets locally on the iPhone. And again, this is 2013. So we were using the GPU image library and just straight open GLES shaders like the shaders that are used for rendering. We were using those to run the convnets on the iPhone and eventually I kind of left to go continue to work on Lambda full-time and probably about a year or so later they got acquired by Apple. And so if you know the feature on your iPhone where you swipe up on an image and you can recognize faces and search through your library, that's maybe some of the stuff that eventually got integrated into iOS through that acquisition. And then Lambda, we continued on. I had we had a variety of different products. Everything from Lambda hat, which was a baseball cap that took a camera every 10 sec took a picture every 10 seconds with a camera embedded in the tip of the brim for gathering data sets for image and face recognition.

</details>

**[Matt]**: 这很吸引人，因为快进到今天，这已经成为一个完整的领域，比如捕捉日常生活来训练 AI。

<details>
<summary>Original English</summary>

**[Matt]**: which is fascinating because fast forward to today and that's a whole segment, right? Like capturing everyday life to train the AI.

</details>

**[Stephen Balaban]**: 这说明，能够看到未来很重要，但把握时机也同样重要。现在一切都成功了。尽管 Lambda Hat 产品可能不怎么样，但它教会了我很多关于如何构建硬件的知识。我在深圳住过一段时间，做 PCB 设计和硬件产品。它教会了我如何制造消费电子产品，这实际上是一项巨大的技能，因为它完全打开了我对新的商业方式的思路，而不仅仅是做应用程序。后来我们有了一个叫 Dream Scope 的产品，在 2015 和 2016 年变得非常流行。它基本上是使用 Google DeepDream 的方法，用卷积网络生成图像，类似于早期版本的 Midjourney。DeepDream 和 Leon Gate 风格迁移算法可以让你把照片变成画作。我们获得了大约 100 万用户，处理了数千万张图像，大概 1500 万张。这导致我们有一笔巨大的 AWS 账单，每月大约 4 万美元。为了替代它，我们用工作站搭建了一个小集群。那是一个 6 万美元的资本支出，我们当时非常害怕，担心这会让我们破产。我们之所以用工作站搭建，是因为想，最坏的情况是我们可以把它们卖掉。结果，我们把它上线后，账单降到了零。所以它在一个半月内就回本了。我们想，哇，我们省的钱比赚的还多。也许我们应该从事为其他 AI 研究人员提供计算服务的业务。于是，我们开始销售工作站和服务器，并开始开发我们的云平台。2017 年，第一年销售工作站，可能做了 300 万美元的收入，2018 年 1000 万，2019 年 3000 万。在接下来的几年里，我们将硬件业务增长到大约 2 亿美元的运营率。而云业务，我们真正开始是在 2019 年，之前一直在开发，但真正开始营销后，老实说增长很慢，因为在 2018、19、20 年，没有多少人需要大量的 AI 计算，这是一个非常小众的市场。但最终，我们的云业务持续增长，现在运营收入略低于 10 亿美元。我们已经完全退出了硬件业务。所以，Lambda 的创立故事绝对疯狂。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: It goes to show you have to, you know, it's one, it's important to be able to see the future. It's also important to get your timing right as well. Right. And now it all worked out, right? Despite maybe that Lambda hat product not being great, but it taught me a lot about how to build hardware. I lived in Shenzhen for a little bit, working on the PCB and spinning the PCB and designing the actual hardware product. And, you know, it taught me how to make consumer electronics. And that was actually a huge huge skill because it totally opened my mind to new ways of doing business that aren't just making apps, right? And eventually we had this product called Dream Scope which became really popular in 2015 and 16 and it was basically using the Google Deep Dream methodology of using a convnet to generate images. It's like an early version of midjourney or whatever. and DeepDream and the Leon Gate style transfer algorithm allowed you to turn a photo into a painting basically. And we got like a million users on that, processed tens of millions of images, maybe 15 million images or something like this. And that caused us to have a huge AWS bill. It was like $40,000 a month or something. And so to replace that, we'd ended up building a little cluster out of workstations. And then that was a $60,000 capex that we were terrified to make, by the way. We were so scared that doing this capex was going to put us out of business. We made it out of workstations because we thought, oh well, worst case scenario, we can just sell them. And so lo and behold, we did end up turning it online and it brought the bill down to zero. So it paid itself back in a month and a half. And we thought, wow, this is like we're saving more money than we're making. Maybe we should be in the business of providing compute to other AI researchers. And thus, we started selling workstations and servers and started developing our cloud platform. Maybe did $3 million of revenue in 2017. That first year, selling workstations, then 10 million in 2018, then $30 million in 2019. We grew the hardware business over the next couple years to probably about $200 million run rate. And then the cloud business we really started in 2019 and we started development before then but we started really marketing it and it kind of was slow to grow to be honest because not a lot of people in 2018 and 19 and 2020 wanted a bunch of AI compute. There was a pretty niche market for it. But eventually our cloud business continued to grow and now it's at a little bit under a billion dollar revenue run rate. we've fully exited the hardware business and so yeah, Lambda's got a absolutely wild founding story to summarize.

</details>

**[Matt]**: 最初的一些人还在吗？我记得你是和你哥哥一起创办公司的，对吗？你哥哥还在公司吗？

<details>
<summary>Original English</summary>

**[Matt]**: Are some of the people that were there at the beginning still around? I think you started the company with your brother. Is that right? And your brother is still at the company.

</details>

**[Stephen Balaban]**: 是的。早期的人，基本上，制作 Dream Scope 的四个人：我、我的联合创始人和异卵双胞胎兄弟 Michael Balaban、我们的首席科学官 Tran Lee，以及工程负责人 Steve Clarkson，他们都还在公司。下一个招聘的人，团队中的 Mateesh Agaral，他在公司待了大约 8 年，后来离开并与另一位前 Lambda 成员 Thomas Summers 共同创立了 Positron，这是一家加速器公司，现在估值超过 10 亿美元。所以，不仅原始团队留下来了，而且我们已经开始看到 Lambda 校友网络在世界上是什么样的。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Yeah. And so in terms of like the early people basically it's not I mean not even basically of the four people who are making Dream Scope me, Michael Balaban, my co-founder and fraternal twin brother, Tran Lee who's our chief scientific officer and then Steve Clarkson who's an engineering leader at the company and has a bunch of folks reporting into him. Now they're all still at the company. The next hire, one of those gentlemen named Mateesh Agaral who's one of the next hires in that team. He was with the company for maybe eight years or something like this. and then he eventually left and joined another former Lambda team member Thomas Summers to start Positron which is an accelerator company and they're like now valued at over a billion dollars. So not only has the original team stuck around but we've already started to kind of see what a lambda alumni a lambda mafia network looks like in the world.

</details>

**[Matt]**: 在困难时期，你是如何让团队保持凝聚力的？

<details>
<details>
<summary>Original English</summary>

**[Matt]**: how did you keep the band together during the difficult times

</details>

**[Stephen Balaban]**: 当你经营一家如此资本密集、营运资金密集的初创公司时，随着你的成长，系统会受到很多冲击。例如，在 2020 年 4 月，软件公司感觉很好，因为他们可以交付软件，需求更大。而硬件公司，码头关闭了，你在 3 月和 4 月无法确认收入。我清楚地记得所有这些事情。我记得站在团队面前说，“嘿，听着，现在非常艰难。我们不确定是否能挺过去，但唯一能做的就是咬紧牙关，享受痛苦，冲过去，为眼前的问题找到解决方案，所有这一切都是为了取悦客户。” 因为从根本上说，最重要的是让大家团结在同一个目标上：我们在这里的唯一原因就是构建人们想要、喜爱并会告诉朋友、愿意付钱的东西。其他一切都源于这种取悦客户的体验。例如，在做入职培训时，我过去常常在 Lambda 101 中展示一张 Linux 企鹅的图片，它坐在 Lambda 工作站上，正在阅读 GPT-2 论文，训练有一个损失曲线。我说，“把自己想象成那只正在使用这个工作站或云服务训练神经网络的企鹅，想想什么能取悦它。” 无论是我们发货团队的人说，“嘿，我们在盒子里放一些 T 恤吧。” 所以每个工作站都附带一件 Lambda T 恤。或者数据中心运营团队的成员说，“嘿，我们应该用白色机架，因为那会让我们与众不同，让一切看起来很棒，我们会很自豪地展示它。” 这些就是你向公司灌输“客户至上”理念的方式，我认为这能帮助你度过难关。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: just when you're running a startup company that's this capital intensive working capital intensive as well like it's just you get a lot of shocks to the system as you're growing and then co what co I mean in April of co software companies were feeling great because they could ship software and there was so much more demand. Hardware companies the docks were closed. You couldn't ship revenue in April and March. So I mean I remember all these things really distinctly. I think I remember just getting in front of the team like, "Hey, look, it's really tough right now." And there's certainly a feeling that like we're not sure if we're going to make it through this, but the only thing to do is just to like suck it up and enjoy the pain, run through it, and come up with the solutions to the problems that you're presented with all in the service of delighting customers. Because fundamentally, the big thing is just aligning people towards the only reason we're all here is to build something that people want and they love so much that they tell their friends about it and they give you money. And then everything else, it just follows from that customer experience of delighting customers with what you do. When we do onboarding, for example, I used to do this thing in what called Lambda 101 and we would show a picture of like a Linux penguin and he was like on a Lambda workstation and he was reading the GPT 2 paper and training had a loss curve which is like what you see and you look at as you're if you're doing machine learning research. I was like, look, just put yourselves in the shoes of the penguin who's training using this workstation or cloud service to train a neural network and just think about what's going to delight them. You know, whether it's, people on our shipping team who said, "Hey, let's put some t-shirts inside of the boxes." And so every workstation came with a Lambda t-shirt, or members of the data center operations team said, "Hey, you know what? we should do a white rack because that'll kind of like set us apart and make everything look good and we'll be really proud to showcase that." And those are the types of things that as you kind of imbue your company with the kind of delight the customer first mentality that I think helps you get through the hard times.

</details>

### 新任 CEO 与未来愿景

**[Matt]**: 最近的一个演变是，你们请来了一位新 CEO，我的法国同胞 Michel K，来管理公司。请谈谈你们的想法，是什么促使你做出这个决定，以及这将如何为公司下一阶段做好准备？

<details>
<summary>Original English</summary>

**[Matt]**: recent evolution in that journey is that you just brought on a new CEO and my fellow French countryman Michelle K to run the business. Walk us through the thinking and what led you to make the decision and how that equips the company for the next chapter.

</details>

**[Stephen Balaban]**: 作为一个创始人，能够走到公司有能力引进像 Michel 这样优秀的人才担任这个职位，是一种巨大的荣誉。因为很多公司，创始人 CEO 可能出于 ego 而必须担任 CEO。我个人从未有过这种感觉。我在乎技术，在乎打造一家伟大的世代公司，而且我认为有很多不同的职位可以实现这个目标。所以，当我们成熟到能够负担得起像 Michel 这样的 CEO 时，他之前是软银国际 CEO、Sprint CEO、阿尔卡特朗讯 CEO，还在一些非常棒的公司董事会任职，包括迈凯伦。我过去做融资、资本形成和日常业务管理是出于必要，而不是因为我真的喜欢做这些。我认为有很多创始人 CEO 热爱他们工作的每一个方面，但私下里，当我与创始人 CEO 交谈时，我总是问，“你有多讨厌它？”

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: It's a huge honor as a founder to get to the point where the company can afford to bring on amazing talent like Michelle, in that seat, right? is because if you think about it, I'd say most companies it's not uncommon for somebody to say, "Hey, look, a lot of people sometimes maybe there's a component of ego involved where they have to be the founder CEO." I've never really personally had that. I care about the technology, as you can tell. I care about building a great generational company and I think there's so many different seats to do that from. And so, getting to the point of maturity where we could afford to bring on a CEO like Michelle who has experience like he, previously Soft Bank International CEO, Sprint CEO, Alcatel, he's on the board of some really amazing companies, including McLaren, which is a kind of a fun one. I always did the sort of like fundraising and capital formation and day-to-day business management as a necessity and not like because that's what I really love doing for example right and I think there's plenty of founder CEOs who absolutely love every aspect of their CEO job I think that privately and it will be very hard for you to get this out of any founder CEO often times but like secretly When I talk with founders CEOs, I'm always like, "Yeah, so like how much do you hate?"

</details>

**[Matt]**: 我觉得人们不觉得整天和 VC 交谈很兴奋，这很令人震惊，但我相信你的话。

<details>
<summary>Original English</summary>

**[Matt]**: I find it shocking that people don't find speaking to VCs all day exciting, but I will take your word for it.

</details>

**[Stephen Balaban]**: 对我来说，能够围绕公司组建一个团队，看到每个人都在他们喜欢专注的事情上蓬勃发展，这是一次很棒的经历。例如，现在我作为 CTO，主要关注的事情之一是公司的高速数据中心部署是什么样的。我希望 Lambda 成为这样一个垂直整合、高速度的强大力量。当你放眼世界，你会发现世界上只有两家公司能够进行高速部署：SpaceX 和 Lambda。我们极度专注于如何削减流程中的每一个小环节，以更快地部署计算。这就是我作为 CTO 一直在深入研究并真正享受的事情。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: It's been like an amazing experience for me that I to be able to form a team around the company and to just see everybody flourishing in the things that they love to focus on. So for example, now that I'm the CTO, one of the main things I'm focused on is what does rapid data center deployment look like at the company and kind of working to say like hey I want Lambda to be this sort of vertically integrated high velocity powerhouse that so when you look at the world you say all right there's two people in the world that can and two companies in the world that can do high velocity deployments SpaceX AI and Lambda where we're just extremely focused on how do you cut every little piece out of the process to stand up compute faster. And that's something I've just been diving into and really enjoying with my new time as CTO.

</details>

**[Matt]**: xAI 在启动时的记录是怎样的？

<details>
<summary>Original English</summary>

**[Matt]**: What was XAI's record like when they launched?

</details>

**[Stephen Balaban]**: 我想大概是 200 多天。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I think it was like 200 and something days.

</details>

**[Matt]**: 是的。你认为这个记录可以以可重复的速度被匹配或超越吗？

<details>
<summary>Original English</summary>

**[Matt]**: Yes. And you think that can be matched or exceeded at a repeatable pace?

</details>

**[Stephen Balaban]**: 我认为可以匹配或超越。是的。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I think it can be matched or beat. Yeah.

</details>

**[Matt]**: 这主要是流程问题。

<details>
<summary>Original English</summary>

**[Matt]**: And that's process mostly.

</details>

**[Stephen Balaban]**: 我认为这涉及到方方面面，从选址过程、选址时使用的约束条件、MEP 管道、数据中心建设方式，到如何让最终客户消费这些计算，以及如何从流程中削减很多东西。因为很多时候，设计这些数据中心的人，就像我提到的，是房地产人士，他们被超大规模云厂商揪着脖子说，“去建这个设计，去找个总承包商干活。” 他们对里面是什么一无所知。另一方面，超大规模云厂商一直在为传统的云服务建设。如果你看看任何云厂商的现代区域，它们有数百种服务，从卫星基站到磁带存储、旋转磁盘、人脸识别 API。每一种服务都需要不同的配置和参数。你可能有人在上面运行 ATM 后端，这与 AI 数据中心的设计空间和约束条件截然不同，AI 数据中心可能对可用性和正常运行时间要求较低。所以，我认为这正是 Lambda 能够通过这种有针对性的 AI 优先方法建立大量独特价值的地方。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I think it's everything from like the site selection process, the set of constraints that you use in a site selection process, the MEP pipeline, the way that you construct the data center, how do you make it so that the end customer will consume that compute, and how do you cut out a lot of stuff out of the process? Because often times, the people who've been designing these data centers have really kind of been real estate people, as I've mentioned, who've been kind of grabbed by the scruff of their neck by a hyperscaler. They're like, "Go and build this design. Here, go get a GC run off." And they don't know anything about what goes inside of it. And the hyperscalers on the other hand have been really building towards traditional cloud services. I mean if you look at a modern region in any of the clouds they have hundreds of services. I mean everything from satellite base stations to tape storage to spinning disc to face recognition APIs. I mean these are all the services and each of those services requires a different skew and has different parameters about what you're kind of servicing and in fact you might have somebody who's trying to run an ATM backend on one of these things that's a pretty different design space and design constraint than an AI data center that could maybe have a lower availability and uptime right and so that's kind of where I think Lambda is able to build a lot of really unique value through this kind of targeted AI first approach.

</details>

### 神经软件与自组装软件

**[Matt]**: 你曾说过一句话：AI 不会编写软件，它将成为软件本身。你这是什么意思？

<details>
<summary>Original English</summary>

**[Matt]**: you had a quote where you said that AI won't write software it will become the software what do you mean by that

</details>

**[Stephen Balaban]**: 这是我关于所谓“神经软件”或“神经操作系统”的想法。最好的体验方式是去你的 ChatGPT 或 Claude，说，“嘿，给我渲染一个 ASI 艺术桌面界面。” 你完全在文本领域工作，我希望你假装成一个操作系统。我会说点击这个，打开那个，你就像一台计算机一样运行。给它那个提示。我认为你会看到，大型语言模型成为软件本身，而不是生成软件的未来。这导致了一种极其灵活和可塑的与计算机交互的方式，其中不可能有 bug，只有对提示和你所要求的内容的误解。我认为，对于你电脑上的许多软件，你可能会看到这种情况开始接管。你可以通过 ASI 艺术一窥未来，最终它还会有一个多模态网络，生成屏幕上的每一个像素以及扬声器发出的每一个音频波形。这样做的好处是，你可以真正地构想出软件。只有你正在体验的部分才被实际实现。它可以拥有你要求的任何功能。我认为这是一种非常强大的与计算机交互的方式。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: So that's in my sort of like idea around what I call neural software and or you know a neural computer neural operating systems and the best way to kind of get this experience is to go to your Chad GPT or your Claude and say, "Hey, just render for me an ASI art desktop interface." Okay, so you're working in purely in the domain of text and I want you to just pretend to be an operating system for me. I'm going to say click on this, open up this and I want you to just behave like a computer. So give it that prompt. Okay? And what you're going to see I think is that you're going to see that sort of future of the large language model becoming the software and not generating the software. And this results in an extremely sort of squishy and flexible way of interfacing with a computer where it's not possible to have a bug, only a misunderstanding about the prompt and what you've asked for. And I think that for a lot of the pieces of software on your computer, you might see that taking over where you can get the glimpse of the future with this ASI art and then eventually it'll also have a multimodal network that's generating every pixel on your screen as well as every audio waveform that comes out of your speakers. The advantage to this is that you can really sort of dream up software. the only the part that is being experienced by you is actually implemented right if that makes sense it could have whatever feature it is if you ask it and that's like a really powerful way to interact with a computer I think.

</details>

**[Matt]**: 所以，不是你给 LLM 简单的指令，而是 LLM 本身就是软件。

<details>
<summary>Original English</summary>

**[Matt]**: so it's not like you give simple instructions to the LLM so the LLM is the software

</details>

**[Stephen Balaban]**: 打个比方，Vibe Coding 接收一个提示，然后输出人类可读、可写、可编译的代码，这些代码运行在正常的人类软件编程语言基础上。它输出 C 代码，通过编译器；输出 Python 代码，通过解释器。那个软件是静态的，一旦生成就不能改变。你可以再次进行 Vibe Coding，或者即时 Vibe Coding。在传统人类编写软件和 Vibe Coding 软件之间有一个渐变过程。然后你进入即时 Vibe Coding 软件，它是软件应用的实时创建。但这仍然是软件。再下一步，你直接与 LLM 交互，它模拟软件可能的行为方式。这就是 Vibe Coding 和神经操作系统或神经软件之间的区别。神经软件没有运行的代码，它只是神经网络思维中特征激活空间和上下文的修改。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I guess make the analogy like you know vibe coding takes in a prompt and then outputs It's human readable, writable, compilable code that runs on normal human software programming language substrate, right? You know, it outputs C code which gets put through a compiler. It outputs Python code which gets put through a Python interpreter. That software is static. Once it's been generated, it can't change, right? You can vibe code it again and maybe, you know, vibe code on the fly. There's like a couple different stages of the gradient between traditional human written software and then you go to like maybe vibecoded software. But then you go to just in time vibecoded software where like it's a live creation of the software application but still software but then you go to the next step which is just you're interacting with the LLM and it is emulating kind of how software might behave and that's the difference between vibe coding and a neural operating system or neural software. Neural software there is no code that's running. It's just modifications of the feature activation space and the context in the mind of the neural network.

</details>

**[Matt]**: 你认为我们离那还有多远？那是……

<details>
<summary>Original English</summary>

**[Matt]**: And how far do you think we are from that? Is that something

</details>

**[Stephen Balaban]**: 我们今天已经有原型了。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I mean we have prototypes of it today. So we have prototypes of it today.

</details>

**[Matt]**: 当你说“我们”时，是指 Lambda 吗？

<details>
<summary>Original English</summary>

**[Matt]**: And when you say you is that lambda or is that

</details>

**[Stephen Balaban]**: 是的，Lambda 开发了一个原型。还有其他多家公司也开发了原型。也有学术研究概述了这可能是什么样子。至于大规模采用，一般来说，当我对某件事过早下判断时，我往往会早十年到十五年。所以，我认为神经软件将在十年到十五年内开始或实现大规模采用。实际上，你已经有了一个例子：特斯拉的自动驾驶汽车，或者任何类型的端到端神经网络和大型模型进行自主驾驶，都是神经软件的一种形式。人们理解那个方面，它看到视频，做出关于输出什么的决定，用户体验就是驾驶体验。我认为这是一个神经软件的例子。我们今天已经看到了。现在的问题是，每个人的电脑何时会采用它？我猜是十年。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: yeah lambda's developed a prototype. There are multiple other companies have developed prototypes of this. There's academic research that has outlined what this might look like and how far are we from mass adoption. I would say that generally speaking when I'm early on something I tend to be about a decade to a decade and a half early. So I would say that between a decade and 15 years we will see mass adoption beginning or otherwise happening for neural software. I mean you already have it. So here's another example by the way you already have so you can think of a Tesla self-driving car or any type of end-to-end neural network and then large model that's doing autonomy as a form of neural software right people understand that aspect right which is it's seen video it's making decisions about what to output now the user experience is the driving experience that said that is an example of neural software I would argue and so we already see that today now the question is when is your everyone's computers going to adopt that I'd say a decade.

</details>

### Agent 的影响与内部使用

**[Matt]**: 从你作为计算提供商的角度来看，Agent 会改变什么吗？如果会，以什么方式？

<details>
<summary>Original English</summary>

**[Matt]**: do agents change anything from your perspective as a compute provider and if so in what way

</details>

**[Stephen Balaban]**: 要理解计算层需要改变什么，我们需要理解用户正在改变什么。当你使用 Agent 进行 Vibe Coding 时，你会注意到，你的挂钟时间大部分花在运行测试、收集数据、搜索代码库上。很多时间实际上不是花在推理神经网络上，而是花在做其他事情上。这很像软件工程师如何分配他们的时间。还记得 XKCD 那个关于编译的漫画吗？他们在办公椅上剑斗，有人问“你们在干嘛？”“编译。” 所以现在有很多时间花在编译上，很多时间花在运行测试上，因为 Agent 24/7 循环工作得好的方式，是你不断地用一套很好的自动化测试来验证你写的代码是否正确。那么这意味着什么？这意味着每一个云服务都需要开始做更多的传统 CPU 工作负载。它们需要专注于提供一个伟大的、安全的环境来托管你的编码实例。然后你需要从安全角度思考，如何保护这些大量涌入的新应用。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: to understand what needs to change on the compute layer we need to understand what's changing with the user so when you're doing vibe coding with agents one of the things you'll notice is that your wall clock time in the world is mostly spent on running tests, gathering data, searching through a codebase. A lot of the time is spent not just inferencing a neural network, but it's actually spent doing other things. And it's actually very much similar to how software engineers spend some of their time, right? You know the old XKCD cartoon of compiling where they're sword fighting on the office chairs and someone says, "What are you guys doing?" Well, compiling. And so, now there's a bunch of time spent compiling. There's a bunch of time spent running tests because the part of the way that the agent 24/7 loops really work well is when you are constantly banging against a nice suite of automated tests to make sure the code you're writing is good. And so, well, what does that mean? It means that every single cloud service needs to start doing a lot more traditional CPU workloads. They need to focus on a great environment, a secure environment to host your cloud code instance on. And then you need to think about security from the perspective of you need to think about how this massive influx of new applications are going to be secured.

</details>

**[Matt]**: 你们内部是如何使用 AI Agent 的？

<details>
<summary>Original English</summary>

**[Matt]**: How do you use AI agents internally?

</details>

**[Stephen Balaban]**: Lambda 的很多工程师已经在使用完全由 Agent 驱动的工作流了。你只需去 Cloud Code，说使用高级工作流或启动 Agent，就可以做到。这是第一步。我在内部演示过，一些人已经采用了所谓的“自组装软件”。自组装软件的想法是，你将产品需求和来自系统的持续用户反馈，连接到一个 24/7 运行的 Agent 集群。这样就形成了一个非常清晰和紧密的循环：提交一个 bug 或功能请求，就有一群 Agent 为你实时实现它。我把这种循环称为自组装软件，因为你定义了软件的用途，但大部分开发工作是在软件发布后，用户开始与之交互并集体为其定制时才发生的。我认为这可能是未来很多 Agent 驱动开发的发展方向。另一方面，一旦模型变得更智能，虽然还没完全到那一步，但 Agent 会说，“嘿，我需要人类帮助我。我需要你为我插上一千块 GPU，或者给我一个特定服务的 API 密钥，或者去帮我注册个东西，你能去谈判一下吗？” 我认为这就是你将开始看到的情况：产品用户反馈由 Agent 实现，然后 Agent 也会要求公司里的人为它们做事，所有这一切都是为了取悦客户和赚钱。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Well, I mean a lot of the engineers at Lambda are already doing a fully agent-driven workflow. I mean if you just go to cloud code and say hey use advanced workflows or spin up agents you can do that. So that's like step one. I've demoed internally and some folks have adopted what I kind of call self assembling software. And so self assembling software is this idea where you kind of tie in to a 24/7 running agent fleet product requirements and constant user feedback that's coming off of the system. So you have a very clear and tight loop to go from submitting, hey, this is a bug or this is a feature request and there's a fleet of agents who are implementing that live for you. Okay. And that sort of cycle I call self assembling software is because you kind of say hey this is what this software is for but most of the development for it is going to happen after the software is launched and the users start to interact with it and customize it for themselves collectively. And I think that that is kind of maybe the future paradigm of where a lot of the agent driven development is going to go towards. the other side of that eventually once the models get smarter, I think that they're quite not quite there yet. But, you know, tying that back into, hey, I need help. And I'm not talking about the human. I'm saying the agent's going, "Hey, I need a human to help me. Like, I need you to plug in a thousand GPUs for me, or I need you to give me an API key to a particular service. I need you to go sign up for something for me. can you go please negotiate this?" And I think that's actually how you're going to start to see it happen, which is product user feedback gets implemented by the agents. The agents then also ask the people at the company to go and do things for them all in the service of delighting customers and making money.

</details>

### 吉瓦级工厂与一人一 GPU

**[Matt]**: 你之前谈到过吉瓦级工厂。这是你之前描述的，比如非常擅长快速创建数据中心，但也让它们变得更大。这个概念是什么？它是一个 AI 工厂，基本上是土地、数据中心、里面的服务器，生成 Token。吉瓦级意味着它消耗一千兆瓦或十亿瓦特的电力，这很大。作为参考，纽约市大约是 5 吉瓦。你还谈到了“一人一 GPU”。这是你对未来的愿景吗？请为我们解读一下。

<details>
<summary>Original English</summary>

**[Matt]**: You've talked about gigawatt scale factories. Is that what you were describing earlier around like setting up beginning super good at creating data centers very quickly but it's also making them bigger. What is that concept? It's a an AI factory which is a basically land data center servers inside that is generating tokens and a gigawatt scale means that it's consuming a thousand megawatts or a billion watts which is a lot of power sort of like maybe you can think of it for context New York City is something like five gigawatt. You also talked about one person, one GPU. Is that your vision for the future? Unpack that for us.

</details>

**[Stephen Balaban]**: 在人们真正相信 AI 理论之前，我在 B 轮和 C 轮融资时，经常谈论计算机行业和 AI 行业之间的相似之处。我真的觉得 AI 正在形成一批世代公司，随着 AI 带来的变化，将会诞生一批世代公司。那是在 2020、2021 年。如果你读一下苹果公司的历史，早期的座右铭和信条是“一人一电脑”。在“一人一 GPU”中蕴含着一种谦逊，它源自“一人一电脑”。想想史蒂夫·乔布斯是多么有远见。苹果公司成立于 1976 年，Macintosh 在 1984 年推出。那是成立 8 年后。那时实现“一人一电脑”了吗？不，差得远。1984 到 1994 年，互联网刚刚开始繁荣，还没到。2004 年，我们终于有了宽带互联网接入，在美国，可能第一次接近“一人一电脑”，但更像是“一家一电脑”。直到 2014 年，40 年后，才可能真正实现“一人一电脑”，甚至超越了它，因为人们有笔记本电脑和手机。最终，直到 2024 年，苹果公司成立大约 50 年后，电子商务才开始真正渗透。我之所以选择“一人一 GPU”，是因为我相信，在未来，美国的每个人都需要一块或更多 GPU 的计算能力来完成日常工作、享受生活，无论是获取信息、娱乐、提高生产力还是发挥创造力。同时，我也认识到，史蒂夫·乔布斯和苹果，作为资本主义历史上最优秀的公司之一，花了半个世纪才实现他们的目标。所以，我认为这不是一个可以一夜之间快速实现的目标。这就是它对我的意义。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: So, before people really believed in the AI thesis, when I was pitching our series B and C, I would kind of talk a lot about the similarities between, let's say, the computer industry and the AI industry. I really felt like AI was forming a set of generational companies. And there was going to be a set of generational companies that got minted with the changes that were coming with AI. And this is like in 2020, 2021. And if you read about the history of Apple, for example, in the early days, the motto and the credo at Apple was one person, one computer. One person, one computer. And there's a sense of humility that's embedded in this one person, one GPU, which is the one person, one computer. You think about how visionary Steve Jobs was. That was, Apple was founded in 1976 or something like this. The Macintosh came out in 1985 or 1984, excuse me. 1984, 8 years or so after founding. Is that one person, one computer yet? No, not even close. All right. So, 1984 to 1994. All right. Well, is it one person one computer? Well, we're just starting to have the internet boom. So, we're not quite there yet. 2004, we finally have broadband internet access. And maybe for the first time in the United States, there's not quite one person, one computer, but there's certainly like one person, one family, one computer, or something like this. It's like getting close to it. You don't have until 2014. So 74, 84, 94, 2004, 2014, 40 years after one person one computer do you have probably truly one person one computer and you get actually beyond one person one computer because people have laptops and cell phones and I would consider a cell phone a computer so and then finally you didn't even have e-commerce penetration until 2024, 50 years after the founding or so of Apple computer when e-commerce starts to actually penetrate. I think that the reason I really wanted to choose that one person one GPU is because one I believe that in the future everybody in the United States will need the computational power of one GPU or more to just do their daily work enjoy life whether it's getting access whether it's getting entertained whether it's being productive whether it's being creative And I also recognize that it took Steve Jobs and Apple, one of the best companies in the history of capitalism, half a century to accomplish their goal. And so I think this is not just like an overnight let's quickly get to one person, one GPU. So that's what that means to me.

</details>

### 快速问答：过热与低估

**[Matt]**: 最后，准备好回答几个快速的热点问题了吗？

<details>
<summary>Original English</summary>

**[Matt]**: To close, are you ready for a couple of quick hot takes?

</details>

**[Stephen Balaban]**: 当然。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Sure.

</details>

**[Matt]**: AI 中哪个想法被过度炒作了？

<details>
<summary>Original English</summary>

**[Matt]**: What is one idea in AI that is overhyped?

</details>

**[Stephen Balaban]**: 我认为很多针对非软件工程领域的 Agent 工作流被过度炒作了。原因是，让 Agent 工作流运行良好的一个方法是，它需要有非常具体的反馈机制，这在自动化测试中效果很好。但对于像“去买个网站”这样的任务，效果就不好，因为没有牵引力让模型在长时间内迭代。所以，我认为对于不易验证的事情，Agent 工作流被过度炒作了。但我也不是说所有非软件工程领域都这样，因为有很多容易验证的领域，比如 CAD、计算机辅助制造、有限元分析、计算流体动力学，在这些领域你可以很好地运行 Agent 工作流，进行模拟和迭代。但对于“Claude，给我赚十亿美元，别犯错”这样的任务，情况就不同了。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: I think a lot of the sort of agentic workflows for things that are not software engineering I think tend to be overhyped and I'll tell you that the reason for that is because one of the ways that you get an agentic workflow working really well is that it needs to have very concrete feedback mechanisms which are done brilliantly through automated testing. It's not at all done brilliantly for like go and buy a site. there's no traction to give a model to go and iterate over a long period of time on. So I think agentic workflows for things that aren't readily verifiable. Now I wouldn't say as far as everything that's not software engineering because there's plenty of readily verifiable fields CAD, computer aided manufacturing, finite element analysis, computation fluid dynamics there's a bunch of fields where you can really do a great agentic workflow and simulate it and then go and iterate it's not the case for hey Claude make me a billion dollars make no mistakes.

</details>

**[Matt]**: 通货膨胀会怎样？

<details>
<summary>Original English</summary>

**[Matt]**: sadly or maybe not okay fascinate inflation

</details>

**[Stephen Balaban]**: 那不会是通货膨胀，实际上只是经济中的价值创造，甚至是通缩的。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: would be well it wouldn't be inflation it would actually be just value creation in the economy deflationary even

</details>

**[Matt]**: AI 中哪个想法被低估了？

<details>
<summary>Original English</summary>

**[Matt]**: what is one idea in AI that is underrated

</details>

**[Stephen Balaban]**: 我确实认为神经操作系统和自组装软件的一些方面被低估了。有趣的是，我会给出同样的答案：用于软件开发的基于 Agent 的工作流。我认为大多数人并不理解，他们真的不理解，因为他们从未尝试过。他们从未去过 Cloud Code，说“最大努力”，使用最新的模型，然后去构建任何他们想构建的东西，并启动 10 个 Agent 去做。我认为很多人仍然没有这样做过。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: yeah I really think that the neural OS thing and also some of the aspects of self assembling software like I still do think people you know the funny thing is I'll give the same answer agent-based workflows for software development I think that most people don't understand they literally don't understand because they've never tried it. They've never gone to cloud. Go to cloud to go say maximum effort. Use the latest model and then go and build whatever you wanted to build and say, spin up 10 agents to go and do it. I think a lot of people still haven't done it yet.

</details>

**[Matt]**: 好了，Stephen，这真是太棒了。非常感谢你抽出时间与我们交流。

<details>
<summary>Original English</summary>

**[Matt]**: Well, Stephen, it's been wonderful. Thank you so much for spending time with us.

</details>

**[Stephen Balaban]**: Matt，非常感谢你的邀请。

<details>
<summary>Original English</summary>

**[Stephen Balaban]**: Matt, thank you so much for having me.

</details>

**[Matt]**: 很荣幸。

<details>
<summary>Original English</summary>

**[Matt]**: Appreciate it.

</details>

**[Matt]**: 嗨，我是 Matt Turk。感谢收听本期 Mad Podcast。如果你喜欢，如果你还没有订阅，我们非常感激你能考虑订阅，或者在你观看或收听本期节目的任何平台上留下好评或评论。这真的有助于我们建设播客并邀请到优秀的嘉宾。谢谢，下期节目再见。

<details>
<summary>Original English</summary>

**[Matt]**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already, or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks, and see you at the next episode.

</details>