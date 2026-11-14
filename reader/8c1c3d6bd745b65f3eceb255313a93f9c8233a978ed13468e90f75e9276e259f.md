---
author: Dwarkesh Patel
date: '2026-03-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mDG_Hx3BSUE
speaker: Dwarkesh Patel
tags:
  - compute-scaling
  - semiconductor-supply-chain
  - memory-bottleneck
  - euv-lithography
  - data-center-infrastructure
title: AI算力扩展的最大瓶颈：半导体供应链深度解析
summary: 本访谈深入探讨了AI算力扩展面临的核心瓶颈。Dylan Patel指出，尽管大型科技公司投入巨额资本支出用于数据中心建设，但半导体供应链，特别是EUV光刻机和内存生产，才是长期制约AI发展的关键。访谈分析了GPU折旧周期、AI模型价值提升对芯片价格的影响、内存短缺对消费电子市场的冲击，以及中国在半导体领域的追赶潜力。最后讨论了太空数据中心和人形机器人的算力需求，强调了芯片制造的复杂性和供应链的脆弱性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
  - Google
  - Amazon
  - Microsoft
  - Meta
  - Nvidia
  - TSMC
  - ASML
  - SK Hynix
  - Samsung
  - Huawei
products_models:
  - GPT-4
  - GPT-5.4
  - Claude
  - Opus
  - Sonnet
  - Gemini Pro
  - H100
  - Blackwell
  - Rubin
  - A100
  - TPU
  - Trainium
  - Dojo
  - Ascend 910C
  - Ascend 910D
  - Starlink
media_books: []
status: evergreen
---
### AI算力投入与瓶颈初探

**Dwarkesh**: 好的，这是我室友教我半导体知识的一集。这也是这套设备的告别。

<details>
<summary>Original English</summary>

**Dwarkesh**: All right, this is the episode where my roommate teaches me semiconductors. It's also the send off for this current set.

</details>

**Dylan**: 是的。你用完之后，我就会想，“我不能再用这个了。我得离开这里。” Dwarkesh可不能用别人用过的。**Dylan** 是 **SemiAnalysis** 的首席执行官。**Dylan**，我有一个迫切的问题想问你。如果你把四大巨头——**亚马逊**、**Meta**、**谷歌**、**微软**——加起来，你最近发布的他们今年合计预测的**资本支出（CapEx）**是 **6000亿美元**。考虑到租用这些算力的年度价格，这大约相当于 **50吉瓦**。显然，我们今年不会部署 **50吉瓦**，所以这笔钱大概是为了未来几年将上线的算力支付的。我们应该如何看待这些**资本支出**上线的具体时间表？对于实验室来说，也有类似的问题。**OpenAI** 刚刚宣布他们筹集了 **1100亿美元**，而 **Anthropic** 刚刚宣布他们筹集了 **300亿美元**。如果你看看他们今年将上线的算力——你应该告诉我具体是多少，但总共大约是另外 **4吉瓦**吗？**OpenAI** 和 **Anthropic** 今年维持其算力支出的租用成本是每吉瓦 **100亿到130亿美元**。仅仅这些单独的融资就足以覆盖他们今年的算力支出，这甚至还没包括他们今年将获得的收入。所以请帮我理解：首先，大型科技公司的**资本支出**实际投入使用的时间尺度是怎样的？其次，如果一个 **1吉瓦**数据中心的年租金是 **130亿美元**，那么这些实验室为什么要筹集这么多钱？

<details>
<summary>Original English</summary>

**Dylan**: It is. After you use it, I'm like, "I can't use this again. I gotta get out of here." No sloppy seconds for Dwarkesh. **Dylan** is the CEO of **SemiAnalysis**. **Dylan**, here’s the burning question I have for you. If you add up the big four—**Amazon**, **Meta**, **Google**, **Microsoft**—their combined forecasted **CapEx** this year that you published recently is **$600 billion**. Given yearly prices of renting that compute, that would be close to **50 gigawatts**. Obviously, we're not putting on **50 gigawatts** this year, so presumably that's paying for compute that is going to be coming online over the coming years. How should we think about the timeline around when that **CapEx** comes online? Similar question for the labs. **OpenAI** just announced they raised **$110 billion**, and **Anthropic** just announced they raised **$30 billion**. If you look at the compute they have coming online this year—you should tell me how much it is, but is it on the order of another **four gigawatts** total? The cost to rent the compute that **OpenAI** and **Anthropic** will have this year to sustain their compute spend is **$10 to $13 billion a gigawatt**. Those individual raises alone are enough to cover their compute spend for the year. And this is not even including the revenue that they're going to earn this year. So help me understand: first, what is the timescale at which the Big Tech **CapEx** actually comes online? And second, what are the labs raising all this money for if the yearly price of a **one-gigawatt** data center is **$13 billion**?

</details>

**Dylan**: 当你谈论这些超大规模公司的**资本支出**达到 **6000亿美元**的量级时，如果你再看看供应链的其他部分，总额会达到 **1万亿美元**的量级。其中一部分是立即用于今年上线的算力：芯片和今年支付的**资本支出**的其他部分。但也有很多是前期设置的**资本支出**。当我们谈论美国今年新增 **20吉瓦**的容量时，其中一部分并不是今年支出的。那部分**资本支出**实际上是在前一年支出的。当你看到**谷歌**有 **1800亿美元**的支出时，其中很大一部分是用于2028年和2029年的涡轮机定金。一部分用于2027年的数据中心建设。一部分用于电力采购协议、预付款以及他们为实现超快速扩展而提前进行的各种其他事情。这适用于所有超大规模公司和供应链中的其他人。所以，今年部署的约 **20吉瓦**中，很大一部分是超大规模公司，一部分不是。对于所有这些公司来说，他们最大的客户是 **Anthropic** 和 **OpenAI**。**Anthropic** 和 **OpenAI** 目前大约有 **2到2.5吉瓦**的算力，他们正试图大幅扩展。如果你看看 **Anthropic** 过去几个月的表现，新增了 **40亿或60亿美元**的收入，我们可以直接推断他们每月将再增加 **60亿美元**的收入。有人可能会说这太保守了，他们应该更快。这意味着他们将在未来十个月内增加 **600亿美元**的收入。按照**Anthropic**目前的毛利率（媒体最新报道），这意味着他们需要大约 **400亿美元**的算力支出用于推理，以支持这 **600亿美元**的收入。这 **400亿美元**的算力，按照每吉瓦约 **100亿美元**的租赁成本计算，意味着他们需要增加 **4吉瓦**的推理容量才能实现收入增长。这还是假设他们的研发训练集群保持不变。从某种意义上说，**Anthropic** 需要在今年年底前达到远超 **5吉瓦**的算力。这对他们来说会非常困难，但并非不可能。

<details>
<summary>Original English</summary>

**Dylan**: So when you talk about the **CapEx** of these hyperscalers being on the order of **$600 billion**, and you look across the rest of the supply chain, it gets you to the order of a **trillion dollars**. A portion of this is immediately for compute going online this year: the chips and the other parts of **CapEx** that get paid this year. But there's a lot of setup **CapEx** as well. When we're talking about **20 gigawatts** of incremental added capacity this year in America, a portion of this is not spent this year. A portion of that **CapEx** was actually spent the prior year. When you look at **Google** having **$180 billion**, a big chunk of that is spent on turbine deposits for '28 and '29. A chunk of that is spent on data center construction for '27. A chunk of that is spent on power purchasing agreements, down payments, and all these other things they're doing further out into the future so they can set up this super fast scaling. This applies to all the hyperscalers and other people in the supply chain. So with roughly **20 gigawatts** deployed this year, a big chunk is hyperscalers, and a chunk is not. For all of these companies, their biggest customers are **Anthropic** and **OpenAI**. **Anthropic** and **OpenAI** are at roughly **two to two-and-a-half gigawatts** right now, and they're trying to scale much larger. If you look at what **Anthropic** has done over the last few months, with **$4 billion or $6 billion** in revenue added, we can just draw a straight line and say they'll add another **$6 billion** of revenue a month. People would argue that’s bearish, and that they should go faster. What that implies is they're going to add **$60 billion** of revenue across the next ten months. At the current gross margins **Anthropic** had, as last reported by media, that would imply they have roughly **$40 billion** of compute spend for that inference, for that **$60 billion** of revenue. That **$40 billion** of compute, at roughly **$10 billion a gigawatt** in rental costs, means they need to add **four gigawatts** of inference capacity just to grow revenue. That’s assuming their research and development training fleet stays flat. In a sense, **Anthropic** needs to get to well above **five gigawatts** by the end of this year. It's going to be really tough for them to get there, but it's possible.

</details>

**Dwarkesh**: 我能问一个问题吗？如果 **Anthropic** 今年年底前无法达到 **5吉瓦**，但他们需要这些算力来满足超出预期的疯狂增长的收入——甚至可能更多——以及确保其模型明年足够好的研究和训练：这些容量将从何而来？**Dario** 在你的播客上时非常保守。他说：“我不会在算力上投入太多，因为如果我的收入以不同的速度、在不同的时间点发生变化……我不想破产。我想确保我们在扩展时负责任。”但实际上，与 **OpenAI** 相比，他搞砸了，**OpenAI** 的做法是：“我们只管签下这些疯狂的协议。”到今年年底，**OpenAI** 将拥有比 **Anthropic** 多得多的算力。**Anthropic** 必须怎么做才能获得算力？他们必须去找以前不会选择的质量较低的供应商。**Anthropic** 历史上曾拥有最好的供应商，比如**谷歌**和**亚马逊**，这些是世界上最大的公司。现在**微软**正在扩展整个供应链，他们正在转向其他新兴参与者。**OpenAI** 在与众多参与者合作方面更为积极。是的，他们从**微软**、**谷歌**和**亚马逊**获得了大量容量，但他们也与 **CoreWeave** 和 **Oracle** 合作。他们甚至找了一些看似“随机”的公司，比如**软银能源（SoftBank Energy）**，这家公司以前从未建造过数据中心，但现在正在为 **OpenAI** 建造数据中心。他们还找了许多其他公司，比如 **NScale**，以获取容量。**Anthropic** 面临着这个难题，因为他们在算力方面过于保守，不想过于激进。从某种意义上说，去年下半年很多金融恐慌是因为“**OpenAI** 签了所有这些协议，但他们没有钱支付……”所以**甲骨文（Oracle）**的股价会暴跌，**CoreWeave** 的股价会暴跌。所有这些公司的股价都暴跌了，信贷市场也陷入疯狂，因为人们认为最终买家无法支付。现在大家又说：“哦，等等，他们筹集了大量资金。好吧，他们能支付。”**Anthropic** 则保守得多。他们说：“我们会签订合同，但我们会坚持原则。我们会故意低估我们可能做到的，并保持保守，因为我们不想潜在地破产。”我想了解的是，在紧急情况下获取算力意味着什么？是不是必须选择**新云（neoclouds）**？他们的算力更差吗？差在哪里？你是否不得不向云服务提供商支付原本不必支付的毛利率，因为他们是在最后一刻才加入的？是谁建立了备用容量，以便 **Anthropic** 和 **OpenAI** 可以在最后一刻获得？如果 **OpenAI** 和 **Anthropic** 到2027年最终达到相似的算力，**OpenAI** 获得了什么具体优势？他们今年会以不同的吉瓦数结束吗？如果是这样，**Anthropic** 和 **OpenAI** 到今年年底将拥有多少吉瓦的算力？

<details>
<summary>Original English</summary>

**Dwarkesh**: Can I ask a question about that? If **Anthropic** was not on track to have **five gigawatts** by the end of this year, but it needs that to serve both the revenue that's gone crazier than expected—and maybe it's going to be even more than that—plus the research and training to make sure its models are good enough for next year: Where is that capacity going to come from? **Dario**, when he was on your podcast, was very conservative. He said, "I'm not going to go crazy on compute because if my revenue inflects at a different rate, at a different point… I don't want to go bankrupt. I want to make sure that we're being responsible with this scaling." But in reality, he's screwed the pooch compared to **OpenAI**, whose approach was, "Let's just sign these crazy fucking deals." **OpenAI** has got way more access to compute than **Anthropic** by the end of the year. What does **Anthropic** have to do to get the compute? They have to go to lower-quality providers that they would not have gone to before. **Anthropic** historically had the best quality providers, like **Google** and **Amazon**, the biggest companies in the world. Now **Microsoft** is expanding across the supply chain, and they're going to other newer players. **OpenAI** has been a bit more aggressive on going to many players. Yes, they have tons of capacity from **Microsoft**, **Google**, and **Amazon**, but they also have tons with **CoreWeave** and **Oracle**. They've gone to random companies, or companies one would think are random, like **SoftBank Energy**, who has never built a data center in their life but is building data centers now for **OpenAI**. They've gone to many others, like **NScale**, to get capacity. There's this conundrum for **Anthropic** because they were so conservative on compute, because they didn't want to go crazy. In some sense, a lot of the financial freakouts in the second half of last year were because, "**OpenAI** signed all these deals but they didn't have the money to pay for them…" Okay, **Oracle**'s stock is going to tank, **CoreWeave**'s stock is going to tank. All these companies' stocks tanked, and credit markets went crazy because people thought the end buyer couldn't pay for this. Now it's like, "Oh wait, they raised a ton of money. Okay, fine, they can pay for it." **Anthropic** was a lot more conservative. They were like, "We'll sign contracts, but we'll be principled. We'll purposely undershoot what we think we can possibly do and be conservative because we don't want to potentially go bankrupt." The thing I want to understand is, what does it mean to have to acquire compute in a pinch? Is it that you have to go with **neoclouds**? Do they have worse compute? In what way is it worse? Did you have to pay gross margins to a cloud provider that you wouldn't have otherwise had to pay because they're coming in at the last minute? Who built the spare capacity such that it's available for **Anthropic** and **OpenAI** to get last minute? What is the concrete advantage that **OpenAI** has gotten if they end up at similar compute numbers by 2027? Are they just going to end this year with different gigawatts? If so, how many gigawatts are **Anthropic** and **OpenAI** going to have by the end of this year?

</details>

**Dylan**: 要获取多余的算力，是的，超大规模公司确实有容量。并非所有算力合同都是长期五年期的。有些是2023年或2024年的算力，或者2025年的 **H100**，签订的是短期合同。**OpenAI** 的绝大部分算力都是五年期合同，但也有许多其他客户签订了一年、两年、三年或六个月的按需合同。当这些合同到期时，市场上谁最愿意支付高价？从这个意义上说，我们看到 **H100** 的价格大幅上涨。人们甚至愿意以超过 **2美元**的价格签订长期合同。我见过某些AI实验室——我在这里有点含糊其辞是有原因的——以高达 **2.40美元**的价格签订了两年到三年的 **H100** 合同。如果你考虑利润，在五年内建造 **Hopper** 的成本是 **1.40美元**。现在，两年后，你签订了两年到三年的 **2.40美元**的合同？这些利润率要高得多。现在你可以挤掉所有其他供应商，无论是**亚马逊**、**CoreWeave**、**Together AI**、**Nebius**，还是其他任何公司。这些**新云（neoclouds）**公司通常拥有更高比例的 **Hopper**，因为它们在这方面更为积极。它们也倾向于签订短期合同，**CoreWeave** 除外，其他公司都是如此。所以如果我想要 **Hopper**，市场上确实有一些容量。此外，虽然**甲骨文（Oracle）**或 **CoreWeave** 的大部分容量都以长期合同形式签订了 **Blackwell**，但本季度上线的任何产品都已售罄。在某些情况下，它们甚至没有达到承诺的销售数量，因为存在一些数据中心延迟，不仅是这两家，还包括 **Nebius**、**微软**、**亚马逊**和**谷歌**。但有很多**新云**公司，以及一些超大规模公司，它们正在建设的容量尚未售出，或者它们原本打算分配给某些不一定专注于超级**通用人工智能（AGI）**的内部用途的容量，现在可能会转而出售。或者对于 **Anthropic** 来说，他们不必直接拥有所有算力。**亚马逊**可以拥有算力并提供 **Bedrock** 服务，或者**谷歌**可以拥有算力并提供 **Vertex** 服务，或者**微软**可以拥有算力并提供 **Foundry** 服务，然后与 **Anthropic** 进行收入分成，反之亦然。本质上，你是说 **Anthropic** 不得不支付这种 **50%** 的加价，无论是通过收入分成，还是通过他们如果早点购买算力就不必支付的最后一刻现货算力。

<details>
<summary>Original English</summary>

**Dylan**: To acquire excess compute, yes, there is capacity at hyperscalers. Not all contracts for compute are long-term, five-year deals. There's compute from 2023 or 2024, or **H100s** from 2025, that were signed at shorter terms. The vast majority of **OpenAI**'s compute is signed on five-year deals, but there were many other customers that had one-year, two-year, three-year, or six-month deals, on demand. As these contracts roll off, who is the participant in the market most willing to pay price? In this sense, we've seen **H100** prices inflect a lot and go up. People are willing to sign long-term deals for above **$2** even. I've seen deals where certain AI labs—I'm being a little bit vague here for a reason—have signed at as high as **$2.40** for two to three years for **H100s**. If you think about the margin, it costs **$1.40** to build **Hopper**, across five years. Now, two years in, you're signing deals for two to three years at **$2.40**? Those margins are way higher. Now you can crowd out all of these other suppliers, whether **Amazon** had these, or **CoreWeave**, or **Together AI**, or **Nebius**, or whoever it is. These **neoclouds** are the firms that had a higher percentage of **Hopper** in general because they were more aggressive on it. They also tended to sign shorter-term deals, not **CoreWeave** but the others. So if I want **Hopper**, there is some capacity out there. Also, while most of the capacity at an **Oracle** or a **CoreWeave** is signed for a long-term deal in terms of **Blackwell**, anything that's going online this quarter is already sold. In some cases, they're not even hitting all the numbers they promised they would sell because there are some data center delays, not just those two, but **Nebius**, **Microsoft**, **Amazon**, and **Google**. But there are a lot of **neoclouds**, as well as some of the hyperscalers, who have capacity they're building that they haven't sold yet, or capacity they were going to allocate to some internal use that is not necessarily super **AGI**-focused, that they may now turn around and sell. Or in the case of **Anthropic**, they don't have to have all the compute directly. **Amazon** can have the compute and serve **Bedrock**, or **Google** can have the compute and serve **Vertex**, or **Microsoft** can have the compute and serve **Foundry**, and then do a revenue share with **Anthropic**, or vice versa. Basically, you're saying **Anthropic** is having to pay either this **50%** markup in the sense of the revenue share, or in the sense of last-minute spot compute that they wouldn't have otherwise had to pay had they bought the compute early.

</details>

**Dylan**: 是的，这里有一个权衡。但与此同时，在整整四个月里，每个人都在对 **OpenAI** 说：“我们不会和你签订协议。”这听起来很疯狂，但那是因为“你没有钱”。现在每个人都在说：“**OpenAI**，我们一直都相信你。我们可以签订任何协议，因为你已经筹集了这么多钱。”**Anthropic** 在这方面受到了限制。目前还没有那么多增量算力买家，因为 **Anthropic** 首先达到了能力层级，他们的收入正在飙升。

<details>
<summary>Original English</summary>

**Dylan**: Right, there's a trade-off there. But at the same time, for a solid four months, everyone was saying to **OpenAI**, "We're not going to sign deals with you." That sounds crazy, but it was because, "you don’t have the money." Now everyone's saying, "**OpenAI**, we believed you the whole time. We can sign any deal because you've raised all this money." **Anthropic** is constrained in that sense. There are not that many incremental buyers of compute yet, because **Anthropic** hit the capability tier first where their revenue is mooning.

</details>

**Dwarkesh**: 这很有趣。否则你可能会认为拥有最好的模型是一种极度贬值的资产，因为三个月后你就没有最好的模型了。但它之所以重要，是因为你可以提前签订这些协议，锁定算力，并获得更好的价格。这可能是一个显而易见的问题。但至少直到最近，人们还在大谈 **GPU** 的折旧周期。看空者，比如 **Michael Burry** 或其他人，都说：“看，人们说这些 **GPU** 的使用寿命是四五年。也许是因为技术进步太快了，但实际上，这些 **GPU** 的两年折旧周期是合理的。”这会增加给定年份报告的摊销**资本支出**，并使建造所有这些云在财务上不那么有利可图。但实际上你指出，折旧周期可能比五年更长。如果我们使用 **Hopper**——特别是如果AI真的腾飞，到2030年我们说，“我们必须启动 **7纳米**晶圆厂，我们必须重新启动 **A100**”——那么折旧周期实际上是令人难以置信地长。我觉得这是你所说的一个有趣的财务含义。

<details>
<summary>Original English</summary>

**Dwarkesh**: That's interesting. Otherwise you might think having the best model is an extremely depreciating asset, because three months later you don't have the best model. But the reason it's important is that you can sign these deals, lock in the compute in advance, and get better prices. Maybe this is an obvious point. But at least until recently, people had made this huge point about the depreciation cycle of a **GPU**. The bears, the **Michael Burrys** or whoever, have said, "Look, people are saying four or five years for these **GPUs**. Maybe it's because the technology is improving so fast, but it in fact makes sense to have two-year depreciation cycles for these **GPUs**," which increases the reported amortized **CapEx** in a given year and makes it financially less lucrative to build all these clouds. But in fact you’re pointing out that maybe the depreciation cycle is even longer than five years. If we're using **Hoppers**—especially if AI really takes off and in 2030 we’re saying, "We have to get the **seven-nanometer** fabs up, we have to go back and turn on the **A100s** again"—then the depreciation cycle is actually incredibly long. I feel like that's an interesting financial implication of what you're saying.

</details>

### GPU折旧与模型价值

**Dylan**: 这里有几个问题可以探讨。一个是 **GPU** 的折旧会发生什么？我猜我没有回答你之前的问题，我认为 **Anthropic** 将能够在今年年底前达到大约 **5吉瓦**，甚至可能更多，这既通过他们自己，也通过他们的产品通过 **Bedrock**、**Vertex** 或 **Foundry** 提供服务来实现。我认为他们将能够达到 **5到6吉瓦**，这远远超出了他们最初的计划。根据我们的数据，**OpenAI** 的情况大致相同，实际上会更高一点。但无论如何，**GPU** 的折旧周期。**Michael Burry** 说的是三年或更短。这大致是他的论点。看待这个问题有两个角度。从机械角度看，有一个 **GPU** 的**总拥有成本（TCO）模型**，我们预测 **GPU** 的价格并计算集群的总成本。这包括许多成本：数据中心成本、网络成本、数据中心内更换设备的智能人工成本。还有备件、实际芯片成本、服务器成本。所有这些成本都捆绑在一起。它有一些折旧周期，一些信用成本。你会得出结论：“嘿，如果你的折旧是五年，那么一个 **H100** 在五年内大规模部署的成本是每小时 **1.40美元**。”如果你以每小时 **2美元**的价格签订了这五年的合同，你的毛利率大约是 **35%**。略高于这个数字。如果你以 **1.90美元**签订，大约是 **35%**。然后你假设在第五年，**GPU** 报废了。在某些情况下，人们的论点是，如果你没有签订长期合同，因为**英伟达（Nvidia）**每两年将性能提高三到四倍，而价格只增加两倍或 **50%**……那么 **H100** 的价格……当然，也许2024年市场价值是 **2美元**，毛利率 **35%**，但到2026年，当 **Blackwell** 大规模量产，每年部署数百万颗时，你实际上只值每小时 **1美元**。当2027年 **Rubin** 大规模量产时——尽管它今年开始出货，但明年才是大规模量产——每年部署数百万颗芯片到云端，你又获得了 **3倍**的性能提升，价格又增加了 **50%** 或 **2倍**，那么 **Hopper** 只值每小时 **0.70美元**。所以 **GPU** 的价格会持续下跌。这是一个角度。另一个角度是，你从芯片中获得的效用是什么？如果你能无限量地制造 **Rubin** 或最新的芯片，那么是的，那正是会发生的情况。随着新芯片的推出和每性能价格的上涨，**Hopper** 的价格会以现货或短期合同价格下跌。但由于半导体和部署时间表受到严格限制，真正决定这些芯片价格的不是我今天可以买到的比较产品，而是我今天可以从这颗芯片中获得的价值。从这个意义上说，我们以 **GPT-5.4** 为例。**GPT-5.4** 的运行成本比 **GPT-4** 低得多，并且具有更少的活跃参数。从活跃参数的意义上说，它要小得多，因为它是一个更**稀疏的MoE**，而 **GPT-4** 是一个更粗粒度的 **MoE**。在训练、强化学习（RL）、模型架构和数据质量方面也有许多其他进步，使得 **GPT-5.4** 比 **GPT-4** 好得多。而且它的服务成本更低。当你看到 **H100** 时，它每 **GPU** 可以服务更多的 **GPT-5.4** token，而不是运行 **GPT-4**。所以它正在生产更高质量模型的更多token。**GPT-4** token 的最大**总潜在市场（TAM）**是多少？也许是几十亿美元，也许是数百亿美元。采用需要时间。对于 **GPT-5.4** 来说，这个数字可能超过 **1000亿美元**。但存在采用滞后、竞争以及其他所有公司都在不断改进的问题。如果改进到此为止，那么 **H100** 的价值现在取决于 **GPT-5.4** 能从中获得的价值，而不是 **GPT-4** 能从中获得的价值。这些实验室处于竞争环境中，所以它们的利润不能无限增长。你有一种非常有趣的动态，那就是 **H100** 今天的价值比三年前更高。这太疯狂了。从向前推进的角度来看，这也很令人感兴趣。如果我们开发出真正的**通用人工智能（AGI）**模型，如果我们在服务器上有一个真正的人类……这些关于大脑能进行多少 **FLOPS** 的数字都是非常模糊的。但从 **FLOPS** 的角度来看，**H100** 估计能达到 **1e15**，这与一些人估计人脑能达到的 **FLOPS** 数量相同。显然，在内存方面，人脑要多得多。一个 **H100** 是 **80吉字节**，而大脑可能有**拍字节**。

<details>
<summary>Original English</summary>

**Dylan**: There's a few strings to pull on there. One is, what happens to depreciation of **GPUs**? I guess I didn't answer your prior question, which is that I think **Anthropic** will be able to get to **five gigawatts**-ish, maybe a little bit more by the end of the year through themselves as well as their product being served through **Bedrock**, **Vertex**, or **Foundry**. I think they'll be able to get to **five or six gigawatts**, which is way above their initial plans. **OpenAI** will be roughly the same, actually a little bit higher based on our numbers. But anyway, the depreciation cycle of a **GPU**. **Michael Burry** was saying it's three years or less. That’s sort of his argument. There are two lenses to look at this. Mechanically, there's a **TCO model**, total cost of ownership of a **GPU**, where we project pricing out for **GPUs** and build up the total cost of a cluster. There are a number of costs: your data center cost, your networking cost, your smart hands and people in the data center swapping stuff out. There's your spare parts, your actual chip cost, your server cost. All these various costs get lumped together. There's some depreciation cycles on it, certain credit costs on it. You build up to, "Hey, an **H100** costs **$1.40/hour** to deploy at volume across five years if your depreciation is five years." If you sign a deal at **$2/hour** for those five years, your gross margin is roughly **35%**. It's a little bit above that. If you sign it for **$1.90**, it's **35%** roughly. Then you assume at that fifth year, the **GPU** falls off a bus and is dead. In some cases, the argument people are making is if you didn't sign a long-term deal, because every two years **Nvidia** is tripling or quadrupling the performance while only 2X-ing or **50%** increasing the price… Then the price of an **H100**… Sure maybe the value in the market was **$2** at **35%** gross margins in 2024, but in 2026, when **Blackwell** is in super high volume and deploying millions a year, you’re actually now worth **$1/hour**. And when **Rubin** in '27 is in super high volume—even though it starts shipping this year, it’s super high volume next year—doing millions of chips a year deployed into clouds, you've got another **3X** in performance, another **50% or 2X** in price, then the **Hopper** is only worth **$0.70/hour**. So the price of a **GPU** would continue to fall. That's one lens. The other lens is, what is the utility you get out of the chip? If you could build infinite **Rubin** or infinite of the newest chip, then yes, that's exactly what would happen. The price of a **Hopper** would fall at a spot or short-term contract rate as the new chips come out and the price per performance goes up. But because you are so limited on semiconductors and deployment timelines, what actually prices these chips is not the comparative thing I can buy today, but rather what is the value I can derive out of this chip today. In that sense, let's take **GPT-5.4**. **GPT-5.4** is both way cheaper to run than **GPT-4** and has fewer active parameters. It's much smaller, in that sense of active parameter, because it's a sparser **MoE** versus **GPT-4** being a coarser **MoE**. There's also been so many other advancements in training, RL, model architecture, and data qualities that have made **GPT-5.4** way better than **GPT-4**. And it's cheaper to serve. When you look at an **H100**, it can serve more tokens per **GPU** of **5.4** than if you had ran **GPT-4** on it. So it's producing more tokens of a model that is of higher quality. What is the maximum TAM for **GPT-4** tokens? Maybe it was a few billion dollars, maybe it was tens of billions of dollars. Adoption takes time. For **GPT-5.4**, that number is probably north of **a hundred billion**. But there's an adoption lag, there's competition, and there's the constant improvements that everyone else is having. If improvements stopped here, the value of an **H100** is now predicated on the value that **GPT-5.4** can get out of it instead of the value that **GPT-4** can get out of it. These labs are in a competitive environment, so their margins can't go to infinity. You sort of have this dynamic that is quite interesting in that an **H100** is worth more today than it was three years ago. That's crazy. It's also interesting from the perspective of just taking that forward. If we had actual **AGI** models developed, if we had a genuine human on a server… These are such hand wave-y numbers about how many **flops** the brain can do. But on a **flop** basis, an **H100** is estimated to do **1e15**, which is how much some people estimate the human brain does in **flops**. Obviously, in terms of memory, the human brain has way more. An **H100** is **80 gigabytes**, and the brain might have **petabytes**.

</details>

**Dwarkesh**: 哦，是的，你有**拍字节**？说出一个**拍字节**的二进制数，兄弟。说出一个字符串。

<details>
<summary>Original English</summary>

**Dwarkesh**: Oh, yeah, you've got **petabytes**? Name a **petabyte** of ones and zeros, bro. Name me a string.

</details>

**Dylan**: 嗯，这实际上就是重点。不，我们只是拥有有史以来最好的稀疏注意力技术。说真的。在信息压缩量方面，它可能是**拍字节**。大脑是一个极其稀疏的 **MoE**。但无论如何，想象一个人类知识工作者每年可以创造六位数的价值。如果一个 **H100** 能创造接近这个价值的东西，如果我们服务器上真有“人类”，那么 **H100** 的价值就能在几个月内收回成本。所以当我采访 **Dario** 时，我试图表达的观点并不是我认为奇点在两年内就会到来，因此 **Dario** 迫切需要购买更多算力，尽管他确实需要购买更多算力来应对收入增长。我试图表达的观点是，鉴于 **Dario** 似乎所说的——鉴于他声称我们离一个“天才数据中心”只有两年，肯定不超过五年，而且一个“天才数据中心”应该能创造数万亿的收入——他为什么一直发表关于在算力方面更保守，或者用你的话说，不如 **OpenAI** 激进的言论，这实在说不通。我猜这个观点被忽略了，因为后来人们都在嘲笑我，说：“哦，这个播客主持人试图说服这个市值数百亿美元的公司首席执行官去‘孤注一掷’，兄弟。”我只是想说，从内部来看，他的言论是不一致的。无论如何，能澄清一下很好。我认为回到之前的观点，如果模型如此强大，**GPU** 的价值会随着时间的推移而上升，目前只有 **OpenAI** 和 **Anthropic** 持这种观点。但随着时间的推移，每个人都将看到每 **GPU** 的价值飙升。从这个意义上说，你现在就应该承诺购买算力。有趣的是，以 **Anthropic** 的方式，有一个梗说他们有承诺问题，有点像多角恋。不是 **Dario**，但这有点像一个梗。

<details>
<summary>Original English</summary>

**Dylan**: Well, this is actually the point. No, we’ve just got the best sparse attention techniques ever. Genuinely though. In the amount of information that is compressed, it might be **petabytes**. The brain is an extremely sparse **MoE**. But anyways, imagine a human knowledge worker can produce six figures a year of value. If an **H100** can produce something close to that, if we had actual humans on a server, the value of an **H100** is such that it can repay itself in the course of a couple of months. So when I interviewed **Dario**, the point I was trying to make is not that I think the singularity is two years away and therefore **Dario** desperately needs to buy more compute, although the revenue is certainly there that he needs to buy more compute. The point I was trying to make is that given what **Dario** seems to be saying—given his statements that we're two years away from a data center of geniuses, and certainly not more than five years away, and a data center of geniuses should be earning trillions upon trillions of dollars of revenue—it just does not make sense why he keeps making these statements about being more conservative on compute or, to your point, being less aggressive than **OpenAI** on compute. I guess that point got lost because then people were roasting me, saying, "Oh, this podcaster is trying to convince this multi-hundred billion dollar company CEO to YOLO it, bro." I was just trying to say that internally, his statements are inconsistent. Anyway, it's good to iron it out. I think going back to the earlier view that if the models are so powerful, the value of a **GPU** goes up over time, right now only **OpenAI** and **Anthropic** have that viewpoint. But as we approach further out, everyone is going to be able to see that value skyrocket per **GPU**. So in that sense, you should commit now to compute. Interestingly, in **Anthropic** fashion, there's a bit of a meme that they have commitment issues and are sort of polyamorous. Not **Dario**, but this is a bit of a meme.

</details>

**Dwarkesh**: 这解释了一切。顺便说一句，有一种有趣的经济效应叫做**阿尔奇安-艾伦效应（Alchian-Allen Effect）**，它的观点是，如果你增加不同商品的固定成本，其中一种质量更高，另一种质量更低，那么在边际上，人们会选择质量更高的商品。举个具体的例子，假设味道更好的苹果卖 **2美元**，而味道差的苹果卖 **1美元**。现在假设你对它们征收进口关税。那么一个好苹果是 **3美元**，一个普通苹果是 **2美元**。这是因为它们都增加了 **1美元**，还是应该增加 **50%** 呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: Explains everything. By the way, there's this interesting economic effect called **Alchian-Allen**, which is the idea that if you increase the fixed cost of different goods, one of which is higher quality and one which is lower quality, that will make people choose the higher quality good, on the margin. To give a specific example, suppose the better-tasting apple costs **two dollars** and the shittier apple costs **one dollar**. Now suppose you put an import tariff on them. Now it's **$3** versus **$2** for a great apple versus a medium apple. Is that because they both increased by a dollar, or should it be a **50%** increase?

</details>

**Dylan**: 不，因为它们都增加了 **1美元**。整个效应是，如果有一个固定成本同时适用于两者。那么它们之间的价格差异，也就是比率，就会改变。以前，更贵的那种是两倍贵。现在它只是 **1.5倍**贵。所以我想知道如果应用于AI，这是否意味着，如果 **GPU** 变得更贵，算力价格的固定成本就会增加。结果是，这将促使人们愿意为稍好的模型支付更高的利润。因为计算是，反正我都要为算力支付这么多钱。我不如多付一点钱，以确保它是最好的模型，而不是一个稍差的模型。所以 **Hopper** 从 **2美元**涨到了 **3美元**。如果一个 **Hopper** 能生成一百万个 **Opus** token，能生成两百万个 **Sonnet** token，那么 **Opus** 和 **Sonnet** 之间的价格差异就减小了，因为 **GPU** 的价格从 **2美元**涨到了 **3美元**，增加了 **1美元**。

<details>
<summary>Original English</summary>

**Dylan**: No, because they both increased by **$1**. The whole effect is that if there's a fixed cost that is applied to both. Then the price difference between them, the ratio, changes. Previously, the more expensive one was **2X** more expensive. Now it's just **1.5X** more expensive. So I wonder if applied to AI that would mean that, if **GPUs** are going to get more expensive, there will be a fixed cost increase in the price of compute. As a result, that will push people to be willing to pay higher margins for slightly better models. Because the calculus is, I'm going to be paying all this money for the compute anyway. I might as well just pay slightly more to make sure it's the very best model rather than a model that's slightly worse. So the **Hopper** went from **$2** to **$3**. If a **Hopper** can make a million tokens of **Opus** and it can make two million tokens of **Sonnet**, the price differential between **Opus** and **Sonnet** has decreased because the price of the **GPU** has increased by a dollar from **$2** to **$3**.

</details>

**Dwarkesh**: 有趣。我认为这很有道理。我们看到今天所有的销量都在最好的模型上，所有的收入也都在最好的模型上。

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. I think that makes a ton of sense. We just see all of the volumes are on the best models today, all the revenue is on the best models today.

</details>

### 算力限制下的市场动态

**Dylan**: 在一个算力受限的世界里，会发生两件事。第一，没有承诺问题的公司，以及那些签订了五年期算力合同的公司，已经锁定了巨大的利润优势。他们以两三年前或五年前的价格锁定了五年的算力。而如果你在一个五年期合同的第三年，别人的两年或三年期合同到期了，他们现在正试图以现代价格购买算力，当价格根据模型的价值定价时，价格会高得多。所以早期承诺的人通常有更好的利润。长期合同在市场中的比例远大于短期合同，后者可以作为最后一刻增加的弹性容量。与此同时，利润流向何处？因为模型变得更有价值，云玩家能多大程度地调整他们的定价？如果你看看 **CoreWeave**，他们目前的平均合同期限超过三年。他们 **98%** 以上的算力合同都超过三年。他们最终陷入了一个困境，即他们无法真正调整价格。但每年他们都在以比以前快得多的速度增量增加容量。仅今年一年，**Meta** 增加的容量就相当于他们在2022年为 **WhatsApp**、**Instagram** 和 **Facebook** 提供服务以及进行AI的所有用途的整个算力集群和数据中心容量。他们今年就增加了这么多。同样地，你谈到 **Meta** 这样做，**CoreWeave**、**谷歌**和**亚马逊**，所有这些公司都在逐年增加惊人的算力。这些新增的算力以新价格进行交易。从某种意义上说，是的，只要我们处于一个腾飞期，你就已经锁定了。“哦，**OpenAI** 去年从 **600兆瓦**增长到 **2吉瓦**，今年从 **2吉瓦**增长到 **6吉瓦**以上，明年从 **6吉瓦**增长到 **12吉瓦**。”增量增加的算力才是所有成本的来源，而不是之前的长期合同。那么谁掌握着收取利润的权力呢？是基础设施提供商。现在云玩家、**新云**公司或超大规模公司可以收取利润。他们可以在一定程度上做到，但如果你追溯到谁拥有所有内存和逻辑容量的访问权，那主要是**英伟达（Nvidia）**。他们签订了许多长期合同。他们今天有 **900亿美元**的长期合同，他们正在与内存供应商谈判三年的合同。**亚马逊**和**谷歌**通过 **博通（Broadcom）**，**亚马逊**直接通过 **AMD**。这些公司掌握着所有筹码，因为他们已经获得了容量。**台积电（TSMC）**没有提高价格，但内存供应商在一定程度上大幅提高了价格。他们将再次将价格翻倍或三倍，但他们也签订了这些长期合同。谁能获得所有利润，可能是云服务商，可能是芯片供应商，以及内存供应商，直到**台积电**或 **ASML** 爆发并说：“不，我们要收取更多费用。”但与此同时，模型供应商能收取疯狂的利润吗？至少今年，我们将看到模型供应商的利润大幅上升。因为他们受到产能限制，他们必须抑制需求。**Anthropic** 无法在不抑制需求的情况下以目前的速度继续发展。

<details>
<summary>Original English</summary>

**Dylan**: In a compute-limited world, two things happen. One, companies that don't have commitment issues and have these five-year contracts for compute have locked in a humongous margin advantage. They've locked in compute for five years at the price it transacted at two, three, or five years ago. Whereas if you're three years into that five-year contract and someone else's two-year or three-year contract rolled off, and now they're trying to buy that at modern pricing, when it's priced to the value of models, the price is going to be up a lot more. So the person who committed early has better margins in general. The percentage of the market that is in long-term contracts is much larger than the percentage of the market in short-term contracts that can be this flex capacity you add at the last second. At the same time, where does the margin go? Because models get more valuable, how much can the cloud players flex their pricing? If you look at **CoreWeave**, their average term duration is over three years right now. For **ninety-eight percent plus** of their compute, it's over three years. They end up with this conundrum where they can't actually flex price. But every year they're adding incrementally way more capacity than they had previously. This year alone, **Meta**'s adding as much capacity as they had in their entire fleet of compute and data centers for all purposes for serving **WhatsApp**, **Instagram**, and **Facebook** in 2022, and doing AI. They're adding that alone this year. In the same sense, you talk about **Meta** doing that, **CoreWeave**, **Google**, and **Amazon**, all these companies are adding insane amounts of compute year on year. That new compute gets transacted at the new price. In a sense, yes, you've locked in, as long as we're in a takeoff. "Oh, **OpenAI** went from **six hundred megawatts** to **two gigawatts** last year, and from **two gigawatts** to **six plus** this year, and **six to twelve** next year." The incremental added compute is where all the cost is, not the prior long-term contracts. Then who holds the cards is the infra providers for charging margin. Now the cloud players, the **neoclouds**, or the hyperscalers can charge the margin. They can to some extent, but then as you go upstream to who has access to all the memory and logic capacity, it's **Nvidia** for the most part. They've signed a lot of long-term contracts. They've got **ninety billion dollars** of long-term contracts today, and they're negotiating three-year deals today with the memory vendors. You've got **Amazon** and **Google** through **Broadcom**, **Amazon** directly, and **AMD**. These companies hold all the cards because they've secured the capacity. **TSMC** is not raising prices, but memory vendors are, to some extent, raising a lot of price. They're going to double or triple price again, but then they're also signing these long-term deals. Who is able to accrue all the margin dollars is potentially the cloud, potentially the chip vendors, and the memory vendors, until **TSMC** or **ASML** break out and say, "No, we're going to charge a lot more." But at the same time, do the model vendors get to charge crazy margins? At least this year, we're going to see margins for the model vendors go up a lot. Because they're so capacity constrained, they have to destroy demand. There's no way **Anthropic** can continue at the current pace without destroying demand.

</details>

### 英伟达与台积电的供应链控制

**Dwarkesh**: 让我们深入探讨逻辑和内存。**英伟达**是如何具体锁定这么多这两者的？我认为根据你的数据，到2027年，**英伟达**将拥有超过 **70%** 的 **N3** 晶圆产能，或大约这个范围。我忘了**SK海力士（SK Hynix）**和**三星（Samsung）**等公司的内存数据是多少。

<details>
<summary>Original English</summary>

**Dwarkesh**: Let's get into logic and memory. How specifically has **Nvidia** been able to lock up so much of both? I think according to your numbers, by '27, **Nvidia** is going to have **+70%** of **N3** wafer capacity, or around that area. I forget what the numbers were for memory at **SK Hynix** and **Samsung** and so forth.

</details>

**Dylan**: 思考一下**新云**业务是如何运作的，以及**英伟达**如何与此合作，或者强化学习（RL）环境业务是如何运作的，以及 **Anthropic** 如何与此合作。在这两种情况下，**英伟达**都在有意地分裂互补产业，以确保他们拥有尽可能多的影响力。他们将分配给随机的**新云**公司，以确保没有一个人拥有所有的算力。同样，**Anthropic** 或 **OpenAI** 在与数据提供商合作时，他们会说：“不，我们只是要播种一个庞大的产业，这样我们就不会被任何一个数据环境供应商锁定。”我好奇为什么在 **3纳米**工艺上——那将是 **Trainium 3**，那将是 **TPU v7**，可能还有其他加速器——**台积电（TSMC）**只是把所有产能都给了**英伟达**，而不是试图分裂市场？

<details>
<summary>Original English</summary>

**Dylan**: Think about how the **neocloud** business works and how **Nvidia** works with that, or how the RL environment business works and how **Anthropic** works with that. In both those cases, **Nvidia** is purposely trying to fracture the complementary industry to make sure that they have as much leverage as possible. They're giving allocation to random **neoclouds** to make sure that there's not one person that has all the compute. Similarly, **Anthropic** or **OpenAI**, when they're working with the data providers, they say, "No, we're going to just seed a huge industry of these things so that we're not locked into any one supplier for data environments." And I wonder why on the **3 nm** process—that's going to be **Trainium 3**, that's going to be **TPU v7**, other accelerators potentially—why is **TSMC** just giving it all up to **Nvidia** rather than trying to fracture the market?

</details>

**Dylan**: 这里有几点。关于 **3纳米**，如果我们回到去年，绝大多数 **3纳米**都是**苹果（Apple）**的。**苹果**正在转向 **2纳米**。内存价格正在上涨，所以**苹果**的销量可能会下降。随着内存价格上涨，他们要么削减利润，要么继续前进。存在一些时间滞后，因为他们有长期合同，但**苹果**可能会减少需求或更快地转向 **2纳米**，而 **2纳米**目前只能用于移动芯片。未来，AI芯片将转向那里。所以**苹果**有这个。**苹果**也在与第三方供应商谈判，因为他们有点被**台积电**挤压。**台积电**在高性能计算（HPC）、AI芯片等方面的利润率高于移动领域，因为他们在 **HPC** 方面比在移动领域有更大的优势。当你看看**台积电**在这里的运行计算时，他们实际上正在为生产 **CPU** 的公司提供非常好的分配。当你想到**亚马逊**拥有 **Trainium** 和 **Graviton** 时，这两者都在 **3纳米**上，**Graviton** 是他们的 **CPU**，**Trainium** 是他们的AI芯片。**台积电**更乐意将分配给 **Graviton** 而不是 **Trainium**，因为他们认为 **CPU** 业务是更稳定、长期的增长。作为一家保守的公司，不希望过度追逐增长周期，你实际上希望首先将分配给更稳定、增长率更低的市场，然后再将所有增量产能分配给快速增长的市场。这通常是这样。**AMD** 也是如此。他们获得的 **CPU** 分配，**台积电**对这些比对 **GPU** 更感兴趣。**亚马逊**也是如此。**英伟达**有点独特，因为是的，他们有 **CPU**，他们制造交换机，他们制造网络设备，**NVLink**、**InfiniBand**、**以太网**、**NIC**。总的来说，随着 **Rubin** 的发布和该系列所有芯片的推出，其中 **GPU** 是最重要的，这些东西中的大多数将在今年年底前达到 **3纳米**。然而**英伟达**获得了大部分供应。部分原因是你看市场，**台积电**和其他公司以多种方式预测市场需求，但这也是市场信号。市场发出了信号：“嘿，我们明年需要这么多产能。我们需要这么多。我们将签订不可取消、不可退货的合同。我们甚至可能支付定金。”**英伟达**比**谷歌**或**亚马逊**早得多地做到了这一点。在某些情况下，**谷歌**和**亚马逊**遇到了障碍。其中一个芯片稍微延迟了几个季度。**Trainium** 和所有这些事情都发生了。在这种情况下，出现了一种巨大的情况：“嗯，这些人正在延迟，但**英伟达**想要更多、更多、更多。我们正在检查供应链的其他部分，是否有足够的产能？”他们会去找所有 **PCB** 供应商，问：“有足够的 **PCB** 产能吗？”**胜宏科技（Victory Giant）**是**英伟达**最大的 **PCB** 供应商之一，他们是一家中国公司。所有 **PCB** 都来自中国，或者其中很多。他们会说：“你有足够的 **PCB** 产能吗？太好了。嘿，内存供应商，谁拥有所有内存产能？好的，**英伟达**有。太好了。”当你看看谁足够“**AGI-pilled**”以至于愿意以在非“**AGI-pilled**”的人看来荒谬的长期时间表购买算力——但尽管如此，他们愿意支付相当不错的利润并现在签订合同，因为他们认为未来这个比例会失衡——半导体供应链也会发生同样的事情。

<details>
<summary>Original English</summary>

**Dylan**: There are a couple points here. On **3 nm**, if we go back to last year, the vast majority of **3 nm** was **Apple**. **Apple** is being moved to **2 nm**. Memory prices are going up, so **Apple**'s volumes may go down. As memory prices go up, either they cut margin or they move on. There's some time lag because they have long-term contracts, but **Apple** likely reduces demand or moves to **2 nm** faster, where **2 nm** is only capable of mobile chips today. In the future, AI chips will move there. So **Apple** has that. **Apple** is also talking to third-party vendors because they're getting squeezed out of **TSMC** a little bit. **TSMC**'s margins on high-performance computing—**HPC**, AI chips, et cetera—are higher than they are for mobile, because they have a bigger advantage in **HPC** than they do in mobile. When you look at **TSMC**’s running calculus here, they're actually providing really good allocations to companies that are doing **CPUs**. When you think about **Amazon** having **Trainium** and **Graviton**, both of those are on **3 nm**, **Graviton** being their **CPU**, **Trainium** being their AI chip. **TSMC** is much more excited to give allocation to **Graviton** than they are to **Trainium** because they view the **CPU** business as more stable, long-term growth. As a company that is conservative and doesn't want to ride cycles of growth too hard, you actually want to allocate to the market that is more stable with a lower growth rate first before you allocate all the incremental capacity to the fast growth rate market. That is the case generally. Same for **AMD**. The allocations they get on their **CPUs**, **TSMC** is much more excited about those than they are for **GPUs**. Likewise for **Amazon**. **Nvidia** is a bit unique because yes, they have **CPUs**, they make switches, they make networking, **NVLink**, **InfiniBand**, **Ethernet**, **NICs**. By and large, most of these things will be on **3 nm** by the end of this year with the **Rubin** launch and all the chips in that family, the **GPU** being the most important one. Yet **Nvidia** is getting the majority of supply. Part of this is because you look at the market and **TSMC** and others forecast market demand in many ways, but it's also the market signal. The market signaled, "Hey, we need this much capacity next year. We need this much. We'll sign non-cancelable, non-returnable. We may even pay deposits." **Nvidia** just did it way earlier than **Google** or **Amazon**. In some cases, **Google** and **Amazon** had stumbling blocks. One of the chips got delayed slightly by a couple quarters. **Trainium** and all these sorts of things happened. In that case, there was a huge sort of, "Well, these guys are delaying, but **Nvidia** is wanting more, more, more, more. And we are checking with the rest of the supply chain, is there enough capacity?" They're going to all the **PCB** vendors and saying, "Is there enough **PCB**?" **Victory Giant** is one of the largest suppliers of **PCBs** to **Nvidia**, and they're a Chinese company. All the **PCBs** come from China, or many of them. They're like, "Do you have enough **PCB** capacity? Great. Hey memory vendors, who has all the memory capacity? Okay, **Nvidia** does. Great." When you look at who is **AGI-pilled** enough to buy compute on long timelines at levels that seem ridiculous to people who aren't **AGI-pilled**—but nonetheless, they're willing to pay a pretty good margin and sign it now because they view in the future that ratio is screwed up—the same thing happens with the supply chain for semiconductors.

</details>

**Dwarkesh**: 我不认为**英伟达**完全是“**AGI-pilled**”的。**黄仁勋（Jensen）**不相信软件会完全自动化等等。加速计算，而不是AI芯片，对吧？

<details>
<summary>Original English</summary>

**Dwarkesh**: I don't think **Nvidia** is quite **AGI-pilled**. **Jensen** doesn't believe software is going to be fully automated and all these things. Accelerated computing, not AI chips, right?

</details>

**Dylan**: 是AI芯片。

<details>
<summary>Original English</summary>

**Dylan**: It's AI chips.

</details>

**Dwarkesh**: 但他就是这么称呼的，对吧？

<details>
<summary>Original English</summary>

**Dwarkesh**: But that's what he calls it, right?

</details>

**Dylan**: 是的。我认为这是一个更广泛的术语，AI包含在其中，但也包括物理建模和模拟。但他好像没有拥抱主要用例。

<details>
<summary>Original English</summary>

**Dylan**: Yeah. I think it's a broader term, AI is within that, but also physics modeling and simulations. But it's like he's not embracing the main use case.

</details>

**Dylan**: 我认为他正在拥抱它，但我只是不认为他像 **Dario** 或 **Sam** 那样“**AGI-pilled**”。但他仍然比去年第三季度的**谷歌**或**亚马逊**更“**AGI-pilled**”得多，而且他看到了更多的需求。原因很简单。你可以看到所有的数据中心建设。他会说：“好的，我想要这个市场份额。”我们追踪了所有的数据中心，有很多数据中心可能属于其中一种或另一种。在某种程度上，**谷歌**和**亚马逊**，尤其是**谷歌**，尽管他们的 **TPU** 对他们来说部署起来更好，但他们必须部署大量的 **GPU**，因为他们没有足够的 **TPU** 来填满他们的数据中心。他们无法获得足够的制造。

<details>
<summary>Original English</summary>

**Dylan**: I think he's embracing it, but I just don't think he's **AGI-pilled** like **Dario** or **Sam**. But he's still way, way more **AGI-pilled** than **Google** was in Q3 of last year, or **Amazon** was in Q3 of last year, and he saw way more demand. The reason is pretty simple. You can see all the data center construction. He's like, "Okay, I want to have this market share." We have all the data centers tracked, and there's a lot of data centers that could be one or the other. To some extent, **Google** and **Amazon**, **Google** especially, even though their **TPU** is just better for them to deploy, they have to deploy a crap load of **GPUs** because they don't have enough **TPUs** to fill up their data centers. They can't get them fabbed.

</details>

**Dwarkesh**: 我有一个问题。**谷歌**卖了 **100万**，是 **v7s** 吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: I have a question about that. **Google** sold a million, was it the **v7s**?

</details>

**Dylan**: 是的。

<details>
<summary>Original English</summary>

**Dylan**: Yes.

</details>

**Dwarkesh**: ——**Ironwoods** 给 **Anthropic**，你现在说最大的瓶颈，今年或明年，我想以后永远都是逻辑和内存，也就是制造这些芯片所需的材料。**谷歌**有 **DeepMind**，第三个著名的AI实验室。如果这是最大的瓶颈，他们为什么要卖掉它，而不是直接给 **DeepMind**？

<details>
<summary>Original English</summary>

**Dwarkesh**: —the **Ironwoods** to **Anthropic**, and you're saying the big bottleneck right now, this year or next year, I guess going forward forever now, is going to be the logic and memory, the stuff it takes to build these chips. **Google** has **DeepMind**, the third prominent AI lab. If this is the big bottleneck, why would they sell it rather than just giving it to **DeepMind**?

</details>

**Dylan**: 这又是一个问题……**DeepMind** 的人会说：“这太疯狂了。我们为什么要这么做？”但**谷歌云（Google Cloud）**的人和**谷歌**高管有不同的思考过程。你和我都认识 **Anthropic** 的算力团队。两位主要负责人都是从**谷歌**来的。他们看到了这种错位，谈判达成了一项协议，并在**谷歌**意识到之前获得了这些算力的使用权。至少从我们发现的数据来看，事件链是这样的：在第三季度初，在六周的时间里，我们看到 **TPU** 的容量显著增加。在这六周内，它增加了好几次。有多次请求。**谷歌**甚至不得不向**台积电**解释他们为什么需要增加产能，因为这太突然了。其中大部分产能增加是为了出售给 **Anthropic**。因为 **Anthropic** 比**谷歌**更早看到了这一点。然后**谷歌**推出了 **Nano Banana** 和 **Gemini 3**，导致他们的用户指标飙升。然后**谷歌**的领导层就说：“哦。”然后他们开始发表声明，说我们必须每六个月将算力翻倍，或者不管具体数字是多少。他们真的清醒了很多，然后他们去找**台积电**说：“我们想要更多。我们想要更多。”**台积电**回复说：“抱歉各位，我们已经售罄了。我们可能在2026年能多提供 **5-10%**，但我们真的要专注于2027年了。”在我看来，这些实验室之间存在信息不对称。我不知道具体情况。这是我根据供应链中晶圆订单的所有数据以及 **Anthropic** 和 **Fluidstack** 签订的数据中心情况，自己编织的一个叙述。对我来说，**谷歌**搞砸了是很清楚的。你可以从**谷歌**的 **Gemini** 年度经常性收入（ARR）中看出这一点。他们在第一季度到第三季度几乎没有收入——在第三季度开始有所起色。但在第四季度，他们的年度经常性收入达到了 **50亿美元**。很明显，**谷歌**最初没有看到收入飙升。从某种意义上说，**Anthropic** 在他们的年度经常性收入爆炸之前，也有一点承诺问题，尽管他们拥有更多的信息不对称，并且看到了即将发生的事情。**谷歌**会比 **Anthropic** 更保守，而且**谷歌**的年度经常性收入更少。所以他们当时不愿意这样做，然后他们意识到他们应该这样做。从那时起，**谷歌**在他们正在做的事情方面变得极其“**AGI-pilled**”。他们收购了一家能源公司。他们正在为涡轮机支付定金。他们正在购买荒谬比例的带电土地。他们正在与公用事业公司谈判长期协议。他们在数据中心和电力方面做得非常积极。我认为**谷歌**在去年年底才清醒过来，但这花了一些时间。

<details>
<summary>Original English</summary>

**Dylan**: This is again a problem of… **DeepMind** people were like, "This is insane. Why did we do this?" But **Google Cloud** people and **Google** executives saw a different thought process. You and I know the compute team at **Anthropic**. Both of the main people came from **Google**. They saw this dislocation, they negotiated a deal, and they were able to get access to this compute before **Google** realized. The chain of events, at least from our data that we found, was in early Q3, over the course of six weeks, we saw capacity on **TPUs** go up by a significant amount. It went up multiple times in those six weeks. There were multiple requests. **Google** even had to go to **TSMC** and explain to them why they needed this increase in capacity because it was so sudden. A lot of that capacity increase was for selling to **Anthropic**. Because **Anthropic** saw it before **Google**. And then **Google** had **Nano Banana** and **Gemini 3** which caused their user metrics to skyrocket. Then leadership at **Google** was like, "Oh." Then they started making the statement that we have to double compute every six months, or whatever the exact number was. They really woke up a lot more, and then they went to **TSMC** and said, "We want more. We want more." **TSMC** replied, "Sorry guys, we're sold out. We can maybe get **5-10%** more for 2026, but really we're going to work on 2027." There was this information asymmetry among the labs, in my mind. I don't know exactly. It's the narrative I've spun myself from seeing all the data in the supply chain on wafer orders and what's going on with the data centers that **Anthropic** and **Fluidstack** signed. It's pretty clear to me that **Google** screwed up. You can see this from **Google**'s **Gemini ARR**. They had next to nothing in Q1 to Q3—in Q3 a little bit once they started inflecting. But in Q4 they reached **$5 billion** in revenue on an ARR basis. It's clear **Google** didn't see revenue skyrocket initially. In a sense, **Anthropic** had a little bit of commitment issues before their ARR exploded, even though they had far more information asymmetry and saw what was coming down the pipe. **Google** is going to be more conservative than **Anthropic** and **Google** had even less ARR. So they were just not willing to do it, and then they realized they should do it. Since then, **Google** has gotten absurdly **AGI-pilled** in terms of what they're doing. They bought an energy company. They're putting deposits down for turbines. They're buying a ridiculous percentage of powered land. They're going to utilities and negotiating long-term agreements. They're doing this on the data center and power side very aggressively. I think **Google** woke up towards the end of last year, but it took them some time.

</details>

**Dwarkesh**: 你认为**谷歌**到明年年底会有多少吉瓦？

<details>
<summary>Original English</summary>

**Dwarkesh**: How many gigawatts do you think **Google** will have by the end of next year?

</details>

**Dylan**: 购买我的数据。

<details>
<summary>Original English</summary>

**Dylan**: Buy my data.

</details>

**Dwarkesh**: 你会为这类信息收费的。

<details>
<summary>Original English</summary>

**Dwarkesh**: You charge for that kind of information.

</details>

### AI算力扩展的终极瓶颈：ASML

**Dylan**: 是的，是的。我觉得每年阻碍我们扩展AI算力的瓶颈都在变化。几年前是 **CoWoS**。去年是电力。你今年会告诉我瓶颈是什么。但我想了解五年后，什么会限制我们部署奇点？最大的瓶颈是算力。为此，最长的供应链提前期不是电力或数据中心。它们实际上是半导体供应链本身。它从电力和数据中心作为主要瓶颈转回了芯片。在芯片供应链中，有许多不同的瓶颈。有内存、**台积电**的逻辑晶圆，以及晶圆厂本身。晶圆厂的建设需要两到三年，而数据中心不到一年。我们看到**亚马逊**最快在八个月内就建成了数据中心。由于建造实际制造芯片的晶圆厂的复杂性，提前期存在巨大差异。工具的提前期也非常长。随着我们规模的扩大，瓶颈已经根据供应链目前无法做到的事情而转移。以前是 **CoWoS**、电力和数据中心，但这些都是提前期较短的项目。**CoWoS** 是一种更简单的芯片封装过程。电力和数据中心最终比芯片的实际制造要简单得多。在移动或PC芯片到数据中心芯片之间，产能进行了一些转移，这在某种程度上是可互换的。而 **CoWoS**、电力和数据中心则必须作为供应链重新开始。但现在，移动和PC产业——以前是半导体产业的大部分——已经没有更多产能可以转移到AI了。**英伟达**现在是**台积电**和**SK海力士**（最大的内存制造商）最大的客户。将资源从普通人的PC和智能手机转移到AI芯片，这几乎是不可能的了。所以现在的问题是如何扩大AI芯片的生产？这是我们走向2030年最大的瓶颈。如果有一个绝对的吉瓦上限，你可以根据“我们不能生产超过这么多 **EUV工具**”来预测到2030年，那将非常有趣。为了进一步扩展算力，今年和明年有不同的瓶颈，但最终到2028年或2029年，瓶颈将落到供应链的最低端，那就是 **ASML**。**ASML** 制造世界上最复杂的机器：**EUV工具**。这些工具的售价是 **3亿到4亿美元**。目前，他们可以生产大约 **70台**。明年，他们将达到 **80台**。即使在非常积极的供应链扩张下，到本世纪末，他们也只能达到略高于 **100台**。这意味着什么？他们可以在本世纪末制造 **100台**这样的工具，而现在是 **70台**。这实际上如何转化为AI算力？我们看到 **Sam Altman** 和供应链中许多其他人都在谈论这些数字：吉瓦、吉瓦、吉瓦。我们正在增加多少吉瓦？我们看到 **Elon** 说太空中有 **100吉瓦**。

<details>
<summary>Original English</summary>

**Dylan**: Yes, yes. I feel like every year the bottleneck for what is preventing us from scaling AI compute keeps changing. A couple years ago it was **CoWoS**. Last year it was power. You'll tell me what the bottleneck is this year. But I want to understand five years out, what will be the thing that is constraining us from deploying the singularity? The biggest bottleneck is compute. For that, the longest lead time supply chains are not power or data centers. They're actually the semiconductor supply chains themselves. It switches back from power and data centers as a major bottleneck to chips. In the chip supply chain, there's a number of different bottlenecks. There's memory, logic wafers from **TSMC**, and the fabs themselves. Construction of the fabs takes two to three years, versus a data center which takes less than a year. We've seen **Amazon** build data centers in as fast as eight months. There's a big difference in lead times because of the complexity of building the fab that actually makes the chips. The tools also have really long lead times. The bottlenecks, as we've scaled, have shifted based on what the supply chain is currently not able to do. It was **CoWoS**, power, and data centers, but those were all shorter lead time items. **CoWoS** is a much simpler process of packaging chips together. Power and data centers are ultimately way simpler than the actual manufacturing of the chips. There's been some sliding of capacity across mobile or PC to data center chips, which has been somewhat fungible. Whereas **CoWoS**, power, and data centers have had to start anew as supply chains. But now there's no more capacity for the mobile and PC industries—which used to be the majority of the semiconductor industry—to shift over to AI. **Nvidia** is now the largest customer at **TSMC** and **SK Hynix**, the largest memory manufacturer. It's sort of impossible for the sliding of resources away from the common person's PCs and smartphones to shift any more towards the AI chips. So now the question is how do we scale AI chip production? That's the biggest bottleneck as we go to 2030. It would be very interesting if there's an absolute gigawatt ceiling that you can project out to 2030 based just on "We can't produce more than this many **EUV machines**." To scale compute further, there are different bottlenecks this year and next year, but ultimately by 2028 or 2029, the bottleneck falls to the lowest rung on the supply chain, which is **ASML**. **ASML** makes the world's most complicated machine: an **EUV tool**. The selling price for those is **$300-400 million**. Currently, they can make about **70**. Next year, they'll get to **80**. Even under very aggressive supply chain expansion, they only get to a little bit over **100** by the end of the decade. What does that mean? They can make a hundred of these tools by the end of the decade, and **70** right now. How does that actually translate to AI compute? We see all these numbers from **Sam Altman** and many others across the supply chain: gigawatts, gigawatts, gigawatts. How many gigawatts are we adding? We see **Elon** saying **a hundred gigawatts** in space.

</details>

**Dwarkesh**: 一年。

<details>
<summary>Original English</summary>

**Dwarkesh**: A year.

</details>

**Dylan**: 一年。这些数字的挑战，实际上不是电力或数据中心。我们可以深入探讨这一点，但它是芯片的制造。以 **英伟达** 的 **Rubin** 芯片的 **1吉瓦**为例。**Rubin** 在 **GTC** 上发布，我相信是在这个播客上线的那一周。要制造 **英伟达** 今年年底将发布的最新的芯片，达到 **1吉瓦**的数据中心容量，你需要几种不同的晶圆技术。你需要大约 **55,000片3纳米**晶圆。你需要大约 **6,000片5纳米**晶圆，然后你需要大约 **170,000片DRAM** 内存晶圆。这三个不同的类别，每个都需要不同数量的 **EUV**。当你制造一片晶圆时，有成千上万的工艺步骤，你在沉积材料和去除材料。但关键的步骤——至少在先进逻辑芯片中占芯片成本的 **30%**——实际上并没有在晶圆上放置任何东西。你拿起晶圆，沉积光刻胶，这是一种在曝光时会发生化学变化的化学物质。然后你把它放入 **EUV工具**中，它以某种方式照射光线。它进行图案化。有一个叫做掩模的东西，它实际上是设计的模板。当你看到一片领先的 **3纳米**晶圆时，它有大约 **70个**掩模，大约 **70层**光刻，但其中 **20层**是最先进的 **EUV**。如果你需要 **55,000片**晶圆才能达到 **1吉瓦**，并且每片晶圆进行 **20次EUV** 通过，你可以计算一下。那是一个 **1吉瓦**需要 **110万次EUV** 通过。这很简单。一旦你加上其他所有东西，包括 **5纳米**和所有内存，最终会达到 **200万次**。一个 **1吉瓦**大约需要 **200万次EUV** 通过。这些工具非常复杂。当你思考它在晶圆上做什么时，它会拿起晶圆，然后扫描和步进。它在整个晶圆上进行几十次。当你谈论多少次 **EUV** 通过时，那是整个晶圆以一定速率曝光。一个 **EUV工具**每小时可以处理大约 **75片**晶圆，而且该工具大约 **90%** 的时间都在运行。最终，你需要大约 **3.5台EUV工具**来完成 **1吉瓦**所需的 **200万次EUV** 晶圆通过。所以 **3.5台EUV工具**可以满足 **1吉瓦**的需求。思考这些数字很有趣。一个 **1吉瓦**的成本是多少？大约是 **500亿美元**。而 **3.5台EUV工具**的成本是多少？那是 **12亿美元**。这实际上是一个相当低的数字，这很有趣。数据中心有 **50吉瓦**的经济**资本支出**，而在此之上产生的token价值甚至更大。这可能是 **1000亿美元**的AI价值进入供应链，三年内，**台积电**已经投入了 **1000亿美元**的**资本支出**。所以是 **300亿/300亿/400亿美元**。其中一小部分被**英伟达**用于其芯片的 **3纳米**，或以前的 **4纳米**。它上个季度的收入是多少？是 **400亿美元**。所以 **400亿美元**乘以四是 **1600亿美元**。仅仅**英伟达**一家公司就将 **1000亿美元****资本支出**的一小部分（这将在多年内折旧，而不仅仅是今年）转化为一年 **1600亿美元**。当你沿着供应链往下看，到 **ASML**，它用价值 **10亿美元**的机器生产 **1吉瓦**，这甚至更令人震惊。当然，这些机器的使用寿命超过一年，所以它做得更多。

<details>
<summary>Original English</summary>

**Dylan**: A year. The problem with any of these numbers, or the challenge to these numbers, is actually not the power or the data center. We can dive into that, but it's manufacturing the chips. Take a gigawatt of **Nvidia**'s **Rubin** chips. **Rubin** is announced at **GTC**, I believe the week this podcast goes live. To make a gigawatt worth of data center capacity of **Nvidia**'s latest chip that they're releasing towards the end of this year, you need a few different wafer technologies. You need about **55,000 wafers of 3 nm**. You need about **6,000 wafers of 5 nm**, and then you need about **170,000 wafers of DRAM memory**. Across these three different buckets, each requires different amounts of **EUV**. When you manufacture a wafer, there are thousands and thousands of process steps where you're depositing material and removing them. But the key critical step—which at least in advanced logic is **30%** of the cost of the chip—is something that doesn't actually put anything on the wafer. You take the wafer, you deposit photoresist, which is a chemical that chemically changes when you expose it to light. Then you stick it into the **EUV tool**, which shines light at it in a certain way. It patterns it. There's what's called a mask, which is effectively a stencil for the design. When you look at a leading-edge **3 nm** wafer, it has **70** or so masks, **70** or so layers of lithography, but **20** of them are the most advanced **EUV**. If you need **55,000 wafers** for a gigawatt, and you do **20 EUV passes** per wafer, you can do the math. That's **1.1 million passes of EUV** for a single gigawatt. It's pretty simple. Once you add the rest of the stuff, it ends up being **2 million**, across **5 nm** and all the memory. You're at roughly **2 million EUV passes** for a single gigawatt. These tools are very complicated. When you think about what it's doing across a wafer, it's taking the wafer and scanning and stepping across. It does this dozens of times across the whole wafer. When you're talking about how many **EUV passes**, that’s the entire wafer being exposed at a certain rate. An **EUV tool** can do roughly **75 wafers per hour**, and the tool is up roughly **90%** of the time. In the end, you need about **3.5 EUV tools** to do the **2 million EUV wafer passes** for the gigawatt. So **3.5 EUV tools** satisfies a gigawatt. It's funny to think about the numbers. What does a gigawatt cost? It costs roughly **$50 billion**. Whereas what do **3.5 EUV tools** cost? That's **$1.2 billion**. It's actually quite a lower number, which is interesting to think about. **Fifty gigawatts** of economic **CapEx** in the data center, and what gets built on top of that in terms of tokens is even larger. It might be **$100 billion** worth of AI value into the supply chain, three years, **TSMC** has done **$100 billion** of **CapEx**. So it's **$30/$30/$40 billion**. A small fraction of that is being used by **Nvidia** for the **3 nm**, or previously **4 nm**, that it's using for its chips. What were its earnings last quarter? It was **$40 billion**. So **$40 billion** times four is **$160 billion**. **Nvidia** alone is turning some small fraction of **$100 billion** in **CapEx**, which is going to be depreciated over many years and not just this one year, into **$160 billion** in a single year. That gets even more intense when you go down the supply chain to **ASML**, which is taking a billion dollars' worth of machines to produce a gigawatt. Of course, those machines last for more than a year so it’s doing more than that.

</details>

**Dwarkesh**: 现在我想了解，到2030年会有多少这样的机器，如果不仅包括当年售出的，还包括前几年积累的？这意味着什么？**Sam Altman** 说他希望在2030年每周生产 **1吉瓦**。当你把这些数字加起来，这与他的目标兼容吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Now I want to understand, how many such machines will there be by 2030, if you include not just the ones that are sold that year, but have been compiling over the previous years? What does that imply? **Sam Altman** says he wants to do **a gigawatt a week** in 2030. When you add up those numbers, is it compatible with that?

</details>

**Dylan**: 如果你仔细想想，这完全是兼容的。**台积电**和整个生态系统已经拥有大约 **250到300台EUV工具**。然后今年增加 **70台**，明年增加 **80台**，到2030年增长到 **100台**。到本世纪末，你将拥有 **700台EUV工具**。**700台EUV工具**，每吉瓦需要 **3.5台**工具——假设全部用于AI，但实际并非如此——这将为你提供 **200吉瓦**的AI芯片，供数据中心部署。**Sam** 每年想要 **52吉瓦**。那么他只占了 **25%** 的份额。显然，移动和PC也占了一部分份额，假设我们仍然被允许拥有消费品，并且我们没有被价格挤出市场。但大致上，他说的是总制造芯片的 **25%** 市场份额。考虑到仅今年一年，我认为他将获得部署的 **Blackwell GPU** 的 **25%**，这非常合理。这并不那么疯狂。

<details>
<summary>Original English</summary>

**Dylan**: That's completely compatible, if you think about it. **TSMC** and the entire ecosystem have something like **250 to 300 EUV tools** already. Then you stack on **70** this year, **80** next year, growing to **100** by 2030. You're at **700 EUV tools** by the end of the decade. **700 EUV tools**, at **3.5 tools per gigawatt**—assuming it's all allocated to AI, which it's not—gets you to **200 gigawatts** worth of AI chips for the data centers to deploy. **Sam** wants **52 gigawatts** a year. He's only taking **25%** share then. Obviously, there's some share given to mobile and PC, assuming we're even allowed to have consumer goods still and we don't get priced out of them. But roughly, he's saying **25%** market share of the total chips fabbed. That's very reasonable given that this year alone, I think he's going to have access to **25%** of the **Blackwell GPUs** that are deployed. It's not that crazy.

</details>

**Dwarkesh**: **ASML** 是什么时候开始出货 **EUV工具**的？是 **7纳米**开始的时候吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: When did **ASML** start shipping **EUV tools**, when **7 nm** started?

</details>

**Dylan**: 我不知道具体是什么时候。

<details>
<summary>Original English</summary>

**Dylan**: I don't know when that was exactly.

</details>

**Dwarkesh**: 你是说2030年，他们将使用最初在2020年出货的机器。所以十年间，你都在使用这个世界上技术最先进的行业中最重要的机器？我觉得这很令人惊讶。

<details>
<summary>Original English</summary>

**Dwarkesh**: You're saying in 2030, they're going to be using machines that initially were shipped in 2020. So for ten years, you're using the same most important machine in this most technologically advanced industry in the world? I find that surprising.

</details>

**Dylan**: **ASML** 出货 **EUV工具**已经大约十年了，但它直到2020年左右才进入大规模量产。工具并非一成不变。那时，工具的吞吐量甚至更低。它们有各种规格，叫做**套刻精度（overlay）**。我刚才提到你在堆叠层。你会做一些 **EUV**，然后做一系列不同的工艺步骤——沉积材料、蚀刻材料、清洗晶圆——在做另一个 **EUV** 层之前，会有几十个这样的步骤。有一个叫做**套刻精度**的规格，就是：你做了所有这些工作，你在晶圆上画了这些线，现在我想画这些点。假设我想画这些点来连接这些金属线到孔洞，然后下一层是另一组垂直的线，这样你现在连接的是相互垂直的导线。你必须能够将它们精确地落在彼此之上。这叫做**套刻精度**。**ASML** 已经迅速改进了**套刻精度**。晶圆吞吐量也已被 **ASML** 迅速改进。工具的价格上涨了，但涨幅不如工具的能力。最初，**EUV工具**是 **1.5亿美元**。随着时间的推移，到2028年，它们现在是 **4亿美元**。但工具的能力也增加了一倍多，特别是在吞吐量和**套刻精度**方面，后者是在进行大量中间步骤后仍能精确对齐后续通过的能力。**ASML** 正在超快速改进。值得注意的是，**ASML** 可能是世界上最慷慨的公司之一。他们拥有这种关键技术。没有人拥有任何有竞争力的东西。也许中国在本世纪末会拥有一些 **EUV**，但没有人拥有任何接近 **EUV** 的东西，然而他们却没有疯狂地提高价格和利润。你去问我们经常交谈的一些其他人，比如 **Leopold**，他们会说：“让价格上涨吧。”因为他们可以。利润就在那里。你可以获取利润。**英伟达**获取利润。内存玩家正在获取利润。但 **ASML** 从未将价格提高到超出工具能力增长的程度。从某种意义上说，他们总是为客户提供净收益。并不是工具停滞不前，只是这些工具很旧。是的，你可以升级它们，新的工具正在到来。为了简化起见，我们在这个播客中忽略了每台工具的**套刻精度**或吞吐量的进步。

<details>
<summary>Original English</summary>

**Dylan**: **ASML**'s been shipping **EUV tools** now for roughly a decade, but it only entered mass volume production around 2020. The tool's not the same. Back then, the tools were even lower throughput. There are various specifications around them called **overlay**. I was mentioning you're stacking layers on top of each other. You'll do some **EUV**, you'll do a bunch of different process steps—depositing stuff, etching stuff, cleaning the wafer—dozens of those steps before you do another **EUV** layer. There's a spec called **overlay**, which is: you did all this work, you drew these lines on the wafer, now I want to draw these dots. Let's say I want to draw these dots to connect these lines of metal to holes, and then the next layer up is another set of lines going perpendicular, so now you're connecting wires going perpendicular to each other. You have to be able to land them on top of each other. It's called **overlay**. **Overlay** is a spec that's been improved rapidly by **ASML**. Wafer throughput has been improved rapidly by **ASML**. The price of the tool has gone up, but not as much as the capabilities of the tool. Initially, the **EUV tools** were **$150 million**. Over time, they're now **$400 million** as I look out to 2028. But the capabilities of the tools have more than doubled as well, especially on throughput and **overlay accuracy**, which is the ability to accurately align the subsequent passes on top of each other even though you do tons of steps between. **ASML** is improving super rapidly. It's also noteworthy to say that **ASML** is maybe one of the most generous companies in the world. They have this linchpin thing. No one has anything competitive. Maybe China will have some **EUV** by the end of the decade, but no one else has anything even close to **EUV**, and yet they haven't taken price and margins up like crazy. You go ask some other folks that we talk to all the time, like **Leopold**, and they're like, "Let's have the price go up." Because they can. The margin is there. You can take the margin. **Nvidia** takes the margin. Memory players are taking the margin. But **ASML** has never raised the price more than they've increased the capability of the tool. In a sense, they've always provided net benefit to their customers. It's not that the tool is stagnant, it's just that these tools are old. Yes, you can upgrade them some, and the new tools are coming. For simplicity's sake, we're ignoring the advances in **overlay** or throughput per tool for this podcast.

</details>

**Dwarkesh**: 你说我们今年生产 **60台**这样的机器，然后未来几年生产 **70台**、**80台**。如果 **ASML** 决定将其**资本支出**翻倍或三倍，会发生什么？是什么阻止他们在2030年生产超过 **100台**？你为什么如此自信，即使五年后，你也能相对确定他们的产量？

<details>
<summary>Original English</summary>

**Dwarkesh**: You say we're producing **60** of these machines this year and then **70**, **80** over subsequent years. What would happen if **ASML** just decided to double its **CapEx** or triple its **CapEx**? What is preventing them from producing more than **100** in 2030? Why are you so confident that even five years out, you can be relatively sure what their production will be?

</details>

**Dylan**: 我认为这里有几个因素。**ASML** 并没有决定“孤注一掷”，尽可能快地扩大产能。总的来说，半导体供应链并没有这样做。它经历了繁荣和萧条，我们可以多谈谈。基本上，一些参与者最近才清醒过来，但总的来说，没有人真正看到每年 **200吉瓦**的AI芯片需求，或者每年在半导体供应链中投入数万亿美元。他们没有“**AI-pilled**”，也没有“**AGI-pilled**”。

<details>
<summary>Original English</summary>

**Dylan**: I think there are a couple factors here. **ASML** has not decided to just go YOLO, let's expand capacity as fast as possible. In general, the semiconductor supply chain has not. It's lived through the booms and busts, and we can talk a bit more about it. Basically some players have recently woken up, but in general no one really sees demand for **200 gigawatts** a year of AI chips, or trillions of dollars of spend a year in the semiconductor supply chain. They're not **AI-pilled**. They're not **AGI-pilled**.

</details>

**Dwarkesh**: 我们今年将达到 **1万亿美元**。

<details>
<summary>Original English</summary>

**Dwarkesh**: We're going to get to a **trillion dollars** this year.

</details>

**Dylan**: 是的，我理解你，但我的意思是供应链中没有人真正理解这一点。我们不断被告知我们的数字太高了，然后当它们正确时，他们又会说：“哦，是的，但你明年的数字仍然太高了。”**ASML** 的工具主要有四个组成部分。它有光源，由圣地亚哥的 **Cymer** 制造。它有掩模台，由康涅狄格州威尔明顿制造。它有晶圆台。它有光学元件，透镜等等。最后两个在欧洲制造。当你查看这四个部分中的每一个时，它们都是极其复杂的供应链，（A）它们没有试图大规模扩张，（B）当它们试图扩张时，时间滞后相当长。再说一次，这是人类在任何规模上制造的最复杂的机器。让我们具体谈谈光源。光源是做什么的？它会滴下这些锡滴。它会用激光完美地连续击打三次。第一次击中锡滴，它会膨胀。它再次击中，使其膨胀成完美的形状，然后以超高功率轰击。锡滴被激发到足以释放 **EUV** 光，**13.5纳米**，然后它在一个收集所有光线并将其导向透镜堆栈的装置中。然后你有透镜堆栈，正如你提到的，是 **Carl Zeiss** 和其他一些公司，但 **Zeiss** 是其中最重要的部分。他们也没有试图扩大生产能力，因为他们没有看到……他们会说：“我们因为AI而增长了很多。我们从 **60台**增长到 **100台**。”这就像：“不不不。我们需要达到几百台，但没关系。随便。”这些工具中的每一个，我认为都有 **18个**这样的透镜。它们是多层反射镜，如果我没记错的话，是完美的钼和钌层，堆叠在一起形成许多层，然后光线完美地从上面反射。当我们想到透镜时，它有一个形状，并且会聚焦光线。这就像一个既是镜子又是透镜的东西，所以它非常复杂。这些超薄沉积堆栈中的任何缺陷都会搞砸。任何曲率问题都会搞砸。扩大生产存在很多挑战。从这个意义上说，它相当具有手工艺术性，因为你每年不是生产几万个，而是几百个，几千个。每年 **60台**工具，每台工具 **18个**，你仍然在数百个工具的范围内，或者说大约数千个透镜和投影光学元件。然后你再看掩模台，那也是非常疯狂的东西。这个东西以，我想说是 **9G** 的速度移动。它会以 **9G** 的速度移动，因为当你步进晶圆时，工具会……晶圆台是互补的。它是晶圆部分。你把这两个东西对齐。你通过聚焦的透镜获取所有光线，这里是掩模，这里是晶圆。掩模向一个方向移动，晶圆向另一个方向移动，因为它扫描晶圆的 **26x33毫米**部分，然后停止。它会移动到晶圆的另一个部分，然后再次执行。它在几秒钟内完成。它们每个都以相反方向的 **9G** 速度移动。这些东西中的每一个都是化学、制造、机械工程和光学工程的奇迹和杰作，因为你必须将所有这些东西对齐并确保它们完美无缺。所有这些东西都有大量的计量学，因为你必须完美地测试所有东西。如果任何东西出了问题，良率就会降到零，因为这是一个如此精密的系统。顺便说一句，它非常大，你是在荷兰埃因霍温的工厂里建造它，然后他们将其拆解，用多架飞机运到客户现场，然后你在那里重新组装并再次测试。这个过程需要很多很多个月。供应链中有许多步骤，无论是 **Zeiss** 制造他们的透镜和投影光学元件，还是 **ASML** 旗下的 **Cymer** 制造 **EUV** 光源。这些都拥有自己复杂的供应链。**ASML** 曾评论说他们的供应链中有超过一万人。

<details>
<summary>Original English</summary>

**Dylan**: Yeah, I feel you, but I'm saying no one really understands this in the supply chain. Constantly, we're told our numbers are way too high, and then when they're right, they're like, "Oh, yeah, but your next year's numbers are still too high." **ASML**'s tool has four major components. It has the source, which is made by **Cymer** in San Diego. It has the reticle stage, which is made in Wilmington, Connecticut. It has the wafer stage. It has the optics, the lenses and such. Those last two are made in Europe. When you look at each of these four, they're tremendously complex supply chains that, (A) they have not tried to expand massively, and (B) when they try to expand them, the time lag is quite long. Again, this is the most complicated machine that humans make, period, at any sort of volume. Let's talk about the source specifically. What does the source do? It drops these tin droplets. It hits it three subsequent times with a laser perfectly. The first one hits this tin droplet, it expands out. It hits it again, so it expands out to this perfect shape, and then it blasts it at super high power. The tin droplets get excited enough that they release **EUV** light, **13.5 nanometer**, and then it's in this thing that is collecting all the light and directing it into the lens stack. Then you have the lens stack, which is **Carl Zeiss**, as you mentioned, and some other folks, but **Zeiss** being the most important part of it. They also have not tried to expand production capacity because they don't see... They're like, "We're growing a lot because of AI. We're growing from **60** to **100**." It's like, "No, no, no. We need to go to a couple hundred, but it's fine. Whatever." Each of these tools has, I think, **18** of these lenses, effectively. They are multilayer mirrors, which are perfect layers of molybdenum and ruthenium, if I recall correctly, stacked on top of each other in many layers, and then the light bounces off of it perfectly. When we think about a lens, it's in a shape, and it focuses the light. This is like a mirror that's also a lens, so it's pretty complicated. Any defect in these super thinly deposited stacks will mess it up. Any curvature issues will mess it up. There are a lot of challenges with scaling the production. It's quite artisanal in this sense because you're not making tens of thousands of these a year, you're making hundreds, you're making thousands. **60 tools** a year, **18** of these per tool, you’re still in the hundreds, of tools, or you're at the thousand number roughly for these lenses and projection optics. Then you step forward to the reticle stage, which is also something really crazy. This thing moves at, I want to say, **nine Gs**. It will shift **nine Gs** because as you step across a wafer, the tool will go... The wafer stage is complementary. It's the wafer part. You line these two things up. You're taking all the light through the lenses that's focused, and here's the reticle, here's the wafer. The reticle's moving one direction, the wafer's moving the other direction as it scans a **26x33 millimeter** section of the wafer, and then it stops. It shifts over to another part of the wafer and does it again. It does that in just seconds. Each of them is moving at **nine Gs** in opposite directions. Each of these things is a wonder and marvel of chemistry, fabrication, mechanical engineering, and optical engineering, because you have to align all these things and make sure they're perfect. All of these things have crazy amounts of metrology because you have to perfectly test everything. If anything is messed up, the yield goes to zero, because this is such a finely tuned system. By the way, it's so large that you're building it in the factory in Eindhoven, Netherlands, and they're deconstructing it and shipping it on many planes to the customer site, and then you're reassembling it there and testing it again. That process takes many, many months. There are so many steps in the supply chain, whether it's **Zeiss** making their lenses and projection optics or **Cymer**, which is an **ASML**-owned company, making the **EUV** source. Each of these has its own complex supply chain. **ASML** has commented that their supply chain has over **ten thousand** people in it.

</details>

**Dwarkesh**: 比如单个供应商？

<details>
<summary>Original English</summary>

**Dwarkesh**: Like individual suppliers?

</details>

**Dylan**: 是的。可能不是直接的。可能是通过 **Zeiss** 有这么多供应商，以及 XYZ 公司有这么多供应商。如果你仔细想想，你谈论的是两个物理移动的物体，它们有晶圆那么大，而且必须精确到个位数纳米甚至更小，因为整个系统，**套刻精度**，层与层之间的**套刻精度**变化，必须在 **3纳米**的量级。如果**套刻精度**是 **3纳米**，那意味着每个单独部件的物理移动精度必须小于这个数字。在大多数情况下，它必须低于 **1纳米**，因为这些误差会累积。没有办法一蹴而就地增加产量。像电力这样简单的事情。美国从 **0%** 的电力增长到 **2%** 的电力增长，即使中国已经达到 **30%**，对美国来说也如此困难。而那是一个非常简单的供应链，其中很少有人制造困难的东西。美国可能有 **10万**名电工和电力供应链中的工作人员，或者更多？当你看看 **ASML**，他们雇佣的人很少。**Carl Zeiss** 可能雇佣不到一千人从事这项工作，而所有这些人都非常非常专业。你不能一蹴而就地培训普通人来做这个。你不能让你的整个供应链都动员起来。**英伟达**已经做了很多工作，才让整个供应链能够提供他们今年将生产的产能。当你和 **Anthropic** 谈话时，他们会说：“我们缺少 **TPU**，我们缺少训练，我们缺少 **GPU**。”当你和 **OpenAI** 谈话时，他们会说：“我们缺少这些东西。”**OpenAI** 和 **Anthropic** 知道他们需要 X。**英伟达**并没有那么“**AGI-pilled**”。他们正在建造 X-1。你沿着供应链往下看，每个人都在做 X-1。在某些情况下，他们正在做 X ÷ 2，因为他们没有“**AGI-pilled**”。你最终会遇到这种反应滞后。这种“**AI-pilledness**”和增加生产的愿望需要很长时间。一旦他们最终明白他们需要快速增加生产……他们认为他们理解了。他们认为AI意味着我们必须从 **60台**增加到 **100台**，此外工具变得更好更快，光源的功率从 **500瓦**增加到 **1000瓦**，以及供应链的所有其他方面都在技术上进步并增加生产。他们认为他们实际上正在大幅增加生产。但如果你仔细计算这些数字……**Elon** 想要什么？他希望到2028年或2029年，太空中的算力达到每年 **100吉瓦**。**Sam Altman** 希望到本世纪末每年达到 **52吉瓦**。**Anthropic** 可能也需要同样多，**谷歌**也需要。你看看整个供应链，就会发现，等等，供应链不可能为每个人提供他们想要的算力。

<details>
<summary>Original English</summary>

**Dylan**: Yes. It might not be directly. It might be through **Zeiss** having so many suppliers and XYZ company having so many suppliers. If you just think about it, you're talking about two physically moving objects that are the size of a wafer, and it has to be accurate to the level of single-digit nanometers or even smaller because the entire system, the **overlay**, the layer-to-layer **overlay** variation, has to be on the order of **3 nanometers**. If the **overlay** is **3 nms**, that means each individual part, the accuracy of its physical movement has to be even less than that. It has to be sub-**one nanometer** in most cases, because the error of these things stack up. There's no way to just snap your fingers and increase production. Things as simple as power. The US going from **zero percent** power growth to **two percent** power growth, even though China's already at **thirty**, was so hard for America to do. And that's a really simple supply chain with very few people in it who make difficult things. There are probably **100,000** electricians and people who work in the electricity supply chain, or more, in the US? When you look at **ASML**, they employ so few people. **Carl Zeiss** probably employs less than **a thousand** people working on this, and all of those people are super, super specialized. You can't just train random people up for this in the snap of a finger. You can't just get your entire supply chain to get galvanized. **Nvidia**'s had to do a lot to get the entire supply chain to even deliver the capacity they're going to make this year. When you go talk to **Anthropic**, they're like, "We're short of **TPUs**, we're short of training, and we're short of **GPUs**." When you go talk to **OpenAI**, they're like, "We're short of these things." **OpenAI** and **Anthropic** know they need X. **Nvidia** is not quite as **AGI-pilled**. They're building X - 1. You go down the supply chain, everyone's doing X - 1. In some cases, they're doing X ÷ 2, because they're not **AGI-pilled**. You end up with this time lag for the whip to react. The **AI-pilledness** and the desire to increase production takes so long. Once they finally understand that they need to increase production rapidly… They think they understand. They think AI means we have to go from **60** to **100**, in addition to the tools getting better and faster, the source getting higher power from **500 watts** to **1,000**, and all these other aspects of the supply chain advancing technically and increasing production. They think they're actually increasing production a lot. But if you flow through the numbers… What does **Elon** want? He wants **100 gigawatts** a year in space by 2028 or 2029. **Sam Altman** wants **52 gigawatts** a year by the end of the decade. **Anthropic** probably needs the same, and **Google** needs that. You go across the supply chain, and it's like, wait, no, the supply chain can't possibly build enough capacity for everyone to get what they want on the side of compute.

</details>

### 半导体供应链的替代方案

**Dwarkesh**: 我觉得在过去几年里，数据中心供应链中的人们一直在争论：“我们受到这个特定事物的瓶颈，因此AI算力不能超过X。”但正如你所写的，如果电网是瓶颈，那么我们就在现场进行**表后发电（behind the meter）**，使用燃气轮机等等。如果这不起作用，还有所有这些人们可以退而求其次的替代方案。我想问我们是否可以想象在半导体供应链中发生类似的事情。如果 **EUV** 成为瓶颈，如果我们只是回到 **7纳米**，并做中国目前正在做的事情，用 **DUV** 机器进行多重图案化生产 **7纳米**芯片，会怎么样？

<details>
<summary>Original English</summary>

**Dwarkesh**: I feel like in the data center supply chain for the last few years, people have been making arguments like, "We are bottlenecked by this specific thing, therefore AI compute can't scale more than X." But as you've written about, if the grid is a bottleneck, then we just do **behind the meter** on the site, we do gas turbines, et cetera. If that doesn't work, there are all these other alternatives that people fall back on. I want to ask whether we can imagine a similar thing happening in the semiconductor supply chain. If **EUV** becomes a bottleneck, what if we just went back to **7 nm** and did what China is doing currently, producing **7 nm** chips with multi-patterning with **DUV** machines?

</details>

**Dylan**: 如果你看看像 **A100** 这样的 **7纳米**芯片，从 **A100** 到 **B100** 或 **B200** 显然取得了很大的进步。这些进步中有多少仅仅是数值上的？如果你只是保持 **A100** 到 **B100** 的 **FP16** 不变。**B100** 略高于 **1 petaflop**，而 **A100** 大约是 **300 teraflops**。

<details>
<summary>Original English</summary>

**Dylan**: If you look at a **7 nm** chip like the **A100**, there's been a lot of progress obviously from the **A100** to the **B100** or **B200**. How much of that progress is just numerics? If you just hold **FP16** constant from **A100** to **B100**. The **B100** is a little over **one petaflop**, and the **A100** is like **300 teraflops**.

</details>

**Dwarkesh**: 是的，**312**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Yeah, **312**.

</details>

**Dylan**: 保持数值不变，从 **A100** 到 **B100** 有 **3倍**的改进。其中一部分是工艺改进，一部分只是加速器设计的改进，我们将来可以再次复制。似乎从 **7纳米**到 **4纳米**的工艺改进实际上影响很小。我手头没有具体数字，但假设每月有 **150k片3纳米**晶圆，最终 **2纳米**也有类似数量。但 **7纳米**也有类似数量。如果你有所有这些旧晶圆，并且可能因为每晶圆面积的比特数减少 **50%** 而导致性能下降 **50%**，那看起来也不算太糟，如果这能给你带来另外 **50或100吉瓦**的算力，那么直接使用 **7纳米**晶圆似乎不是那么糟糕。告诉我为什么这很天真。

<details>
<summary>Original English</summary>

**Dylan**: Holding numerics constant, you have a **3x** improvement from **A100** to **B100**. Some of that is the process improvement, some of that is just the accelerator design improving, which we could replicate again in the future. It seems there's actually a very small effect from the process improving from **7nm** to **4 nm**. I don't know the numbers offhand but let's say there's **150k wafers per month of 3 nm** and eventually similar amounts for **2 nm**. But then there's a similar amount for **7 nm**. If you have all those old wafers and there's maybe a **50%** haircut because the bits per wafer area are **50%** less or something, it doesn't seem that bad to just bring on **7 nm** wafers if that gives you another **fifty or hundred gigawatts**. Tell me why that's naive.

</details>

**Dylan**: 我们可能会足够疯狂，以至于这真的会发生，因为我们只需要增量算力，而且这些算力值得更高的芯片成本和功耗。但从很大程度上说，这也不太可能，因为其中一些不是公平的比较。例如，从 **A100**（**312 teraflops**）到 **Blackwell**（**1000或2000 FP16**），再到 **Rubin**（大约 **5000 FP16**）……这不是一个公平的比较，因为这些芯片的设计目标截然不同。对于 **A100**，**英伟达**优化了 **FP16** 和 **BF16** 数值。当你看到 **Hopper** 时，他们不太关心这些；他们关心的是 **FP8**。当你看到 **Rubin** 时，他们不太关心 **FP16** 和 **BF16**，他们主要关心的是 **FP4** 和 **FP6**。数值是他们设计芯片的目标。假设我们用 **7纳米**制造一个新的芯片设计，针对现代数值进行优化。性能差异仍然会比你提到的 **FLOPS** 差异大得多。通常很容易将事情简化为每瓦 **FLOPS** 或每美元 **FLOPS**，但这并非公平比较。让我们看看 **Kimi K2.5** 和 **DeepSeek**。当你看看这两个模型在 **Hopper** 和 **Blackwell** 上经过高度优化的软件上的表现时，你会得到截然不同的性能。这大部分不归因于 **FLOPS** 或数值，因为这些模型实际上是 **8比特**的。所以并不是说 **Blackwell** 和 **Hopper** 都针对 **8比特**进行了优化，而 **Blackwell** 在那里并没有真正利用其 **4比特**。性能差距实际上要大得多。当然，缩小工艺技术并使晶体管更小，从而使每个芯片拥有 X 数量的 **FLOPS** 是一回事，但你忽略了主要的限制因素。这些模型不是在单个芯片上运行的。它们一次在数百个芯片上运行。如果你看看 **DeepSeek** 的生产部署，它现在已经一年多了，他们运行在 **160个GPU**上。这就是他们处理生产流量的方式。他们将模型分割到 **160个GPU**上。每次你跨越从一个芯片到另一个芯片的障碍时，都会有效率损失。你必须通过高速电 SerDes 传输，这会带来延迟成本和功耗成本。所有这些动态都会造成损害。随着你不断缩小工艺节点，你增加了单个芯片中的算力。现在芯片内部的数据移动至少是每秒几十太字节，甚至数百太字节。而芯片之间，大约是每秒一太字节。然后你会有数据在物理上非常接近的芯片之间移动。你只能将这么多芯片物理上放置在一起，所以你必须将芯片放置在不同的机架中。机架之间的数据移动大约是每秒数百吉比特，**400吉**或 **800吉**每秒，所以大约是每秒 **100吉字节**。所以你有一个巨大的阶梯：芯片内通信超快，机架内慢一个数量级，机架外又慢一个数量级。当你突破芯片的界限时，你会遇到性能损失。我解释这一点的原因是，当你比较 **Hopper** 和 **Blackwell** 时，即使两者都使用一个机架的芯片，**Hopper** 也明显更慢。你在每个领域内用于任务的性能量——这些处理元件之间每秒几十太字节的通信与这些处理元件之间每秒太字节的通信——要高得多，因此性能也高得多。当你看到 **DeepSeek** 和 **Kimi K2.5** 每秒 **100个token** 的推理时，**Hopper** 和 **Blackwell** 之间的性能差异大约是 **20倍**。这不像 **FLOPS** 性能差异所表明的 **2倍**或 **3倍**，即使它们在相同的工艺节点上。只是网络技术和他们所做的工作存在差异。你可以将其中一些回溯，但当你看看他们在 **3纳米**上用 **Rubin** 所做的事情时，其中一些事情根本不可能在 **A100** 上实现，即使你为 **7纳米**制造一个新的芯片。有些架构改进你可以移植，有些则不能。性能差异不仅仅是 **FLOPS** 的差异。它在某种意义上是芯片每 **FLOPS** 差异、芯片间网络速度、芯片与系统上的 **FLOPS** 数量以及单个芯片与整个系统上的内存带宽之间的累积效应。所有这些因素都会复合。

<details>
<summary>Original English</summary>

**Dylan**: We potentially do go crazy enough that this happens because we just need incremental compute, and the compute is worth the higher cost and power of these chips. But it's also unlikely to a large extent because some of these are not fair comparisons. For example, from **A100**, which is **312 teraflops**, to **Blackwell**, which is **1,000 or 2,000 FP16**, and then **Rubin** is **5,000 or so FP16**… It's not a fair comparison because these chips have vastly different design targets. With **A100**, **Nvidia** optimized for **FP16** and **BF16** numerics. When you look at **Hopper**, they didn't care as much about that; they cared about **FP8**. When you look at **Rubin**, they don’t care about **FP16** and **BF16** so much, they care mostly about **FP4** and **FP6**. Numerics are what they've designed their chip for. Let's say we make a new chip design on **7 nm**, optimized for the numerics of the modern day. The performance difference is still going to be much larger than the **FLOPS** difference you mentioned. Often it's easy to boil things down to **FLOPS per watt** or **FLOPS per dollar**, but that's not a fair comparison. Let's look at **Kimi K2.5** and **DeepSeek**. When you look at those two models and their performance on **Hopper** versus **Blackwell** on very optimized software, you get vastly different performance. Most of this is not attributed to **FLOPS** or numerics, because those models are actually **eight-bit**. So it's not like **Blackwells** and **Hopper** are both optimized for **eight-bit**, and **Blackwell** is not really taking advantage of its **four-bit** there. The performance gulf is actually much larger. Sure it's one thing to shrink process technology and make the transistor smaller so each chip has X number of **FLOPS**, but you forget the big gating factor. These models don't run on a single chip. They run on hundreds of chips at a time. If you look at **DeepSeek**'s production deployment, which is well over a year old now, they were running on **160 GPUs**. That's what they serve production traffic on. They split the model across **160 GPUs**. Every time you cross the barrier from one chip to another, there is an efficiency loss. You have to transmit over high-speed electrical SerDes, which brings a latency cost and a power cost. There are all these dynamics that hurt. As you shrink and shrink the process node, you've increased the amount of compute in a single chip. Now in-chip movement of data is at least tens of terabytes a second, if not hundreds of terabytes a second. Whereas between chips, you're on the order of a terabyte a second. Then you have this movement of data between chips that are super close to each other physically. You can only put so many chips close to each other physically, so you have to put chips in different racks. The movement of data between racks is on the order of hundreds of gigabits a second, **400 gig** or **800 gig** a second, so roughly **100 gigabytes** a second. So you have this huge ladder: on-chip communication is super fast, within the rack is an order of magnitude slower, and outside the rack is an order of magnitude lower than that. As you break the bounds of chips, you end up with a performance loss. The reason I explain this is because when you look at **Hopper** versus **Blackwell**, even if both are using a rack's worth of chips, **Hopper** is significantly slower. The amount of performance you have leveraged to the task within each domain—tens of terabytes a second of communication between these processing elements versus terabytes a second between these processing elements—is much, much higher and therefore the performance is much higher. When you look at inference at **100 tokens a second** for **DeepSeek** and **Kimi K2.5**, the performance difference between **Hopper** and **Blackwell** is on the order of **20x**. It's not **2x or 3x** like the **FLOPS** performance difference indicates, even though those are on the same process node. There are just differences in networking technologies and what they've worked on. You can translate some of these back, but when you look at what they're doing on **3 nm** with **Rubin**, some of those things are simply not possible to do all the way back on **A100**, even if you make a new chip for **7 nm**. There are certain architectural improvements you can port and certain ones you cannot. The performance difference is not just going to be the difference in **FLOPS**. It's in some senses cumulative between the difference in **FLOPS per chip**, networking speed between chips, how many **FLOPS** are on a chip versus a system, and memory bandwidth on a single chip versus an entire system. All of these things compound.

</details>

**Dwarkesh**: 我能问一个非常天真的问题吗？**B200** 现在在一个芯片上有两个小芯片（die），所以你可以在不通过 **NVLink** 或 **InfiniBand** 的情况下获得这种带宽。明年，**Rubin Ultra** 将在一个芯片上有四个小芯片。是什么阻止我们用旧的……你可以在一个芯片上有多少个小芯片，并且仍然获得每秒几十太字节的带宽？

<details>
<summary>Original English</summary>

**Dwarkesh**: Can I ask you a very naive question? The **B200** now has two dies on a single chip, so you can get that bandwidth without having to go through **NVLink** or **InfiniBand**. Next year, **Rubin Ultra** will have four dies on one chip. What is preventing us from just doing that with an older… How many dies could you have on a single chip and still get these tens of terabytes a second?

</details>

**Dylan**: 即使在 **Blackwell** 内部，芯片内通信和跨芯片通信的性能也存在差异。这些界限显然比你离开整个芯片时要小得多。当你增加芯片数量时，会有一些性能损失。它并不完美，但比不同的整个封装要好得多。

<details>
<summary>Original English</summary>

**Dylan**: Even within **Blackwell**, there are differences in performance when you're communicating on the chip versus across the chips. Those bounds are obviously much smaller than when you're going out of the entire chip. When you scale the number of chips up, there is some performance loss. It's not perfect, but it is way better than different entire packages.

</details>

**Dwarkesh**: 先进封装能扩展到多大？

<details>
<summary>Original English</summary>

**Dwarkesh**: How large can advanced packaging scale?

</details>

**Dylan**: **英伟达**的做法是 **CoWoS**。**谷歌**、**博通（Broadcom）**、**联发科（MediaTek）**和**亚马逊**的 **Trainium** 都在使用 **CoWoS**。但实际上，你可以回顾一下**特斯拉（Tesla）**对 **Dojo** 的做法，他们取消后又重新启动了。**Dojo** 是一款芯片，大小相当于一整片晶圆。上面有 **25个**芯片。有一些权衡。他们无法在上面放置 **HBM**。但积极的一面是，上面有 **25个**芯片。迄今为止，它仍然可能是运行卷积神经网络（CNN）的最佳芯片。它只是不擅长 transformer，因为芯片的形状、内存、算术以及所有这些各种规格都不太适合 transformer。它们非常适合 **CNN**。**Dojo** 芯片就是围绕这些进行优化的，他们制造了一个更大的封装。但当你把封装做得越来越大时，你会遇到其他限制：网络速度、内存带宽和散热能力。所有这些问题都会开始显现。这并不简单。但是的，你会看到封装上芯片数量增多的趋势线，是的，你可以在 **7纳米**上做到这一点。事实上，**华为**的 **昇腾910C（Ascend 910C）**或 **D** 就是这样做的。他们最初放了一个，然后放了两个。他们专注于扩大封装，因为这是他们可以比无法缩小的工艺技术更快进步的领域。但归根结底，这也是你可以在领先芯片上做的事情。你在 **7纳米**上做的任何事情，在封装方面，你可能也可以在 **3纳米**上做。

<details>
<summary>Original English</summary>

**Dylan**: The way **Nvidia** is doing it is **CoWoS**. **Google**, **Broadcom**, **MediaTek**, and **Amazon**'s **Trainium** are all doing **CoWoS**. But actually you can go look back at what **Tesla** did with **Dojo**, which they cancelled and restarted. **Dojo** was a chip that was the size of an entire wafer. They had **25** chips on it. There were some tradeoffs. They couldn't put **HBM** on it. But the positive side was that they had **25** chips on it. To date, it is still probably the best chip for running convolutional neural networks. It's just not great at transformers because the shape of the chip, the memory, the arithmetic, and all these various specifications are just not well-suited for transformers. They're well-suited for **CNNs**. **Dojo** chips were optimized around that, and they made a bigger package. But as you make packages bigger and bigger, you have other constraints: networking speed, memory bandwidth, and cooling capabilities. All of these things start to rear their heads. It's not simple. But yes, you will see a trend line of more chips on the package, and yes, you're going to be able to do that on **7 nm**. In fact, that's what **Huawei** did with their **Ascend 910C** or **D**. They initially put one, and then they did two. They're focusing on scaling the packaging up because that is an area where they can advance faster than process technology where they can't shrink. But at the end of the day, that’s something you can do on the leading-edge chips too. Anything you do on **7 nm**, you can also probably do on **3 nm** in terms of packaging.

</details>

### 中美半导体竞争与供应链自主化

**Dwarkesh**: 如果我们最终在2030年进入这样一个世界：西方拥有最先进的工艺技术，但没有大规模提升产能，而中国……我不知道你是否认为到2030年他们会拥有 **EUV** 和 **2纳米**或其他什么。但他们是“**半导体-pilled**”的，并且正在大规模生产。基本上，我想知道哪一年会出现一个交叉点，我们的工艺技术优势已经足够减弱，而他们的规模优势已经足够增加。而且，如果他们拥有一个国家完全自主化整个供应链的优势——而不是在德国和荷兰拥有随机供应商——这意味着中国在生产大规模 **FLOPS** 的能力上会领先吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: If we end up in this world in 2030 where the West has the most advanced process technology but has not ramped it up as much, whereas China… I don't know if you think by 2030 they would have **EUV** and **2 nm** or whatever. But they are **semiconductor-pilled** and they are producing in mass quantity. Basically, I'm wondering what the year is where there's a crossover, where our advantage in process technology has faded enough, and their advantage in scale has increased enough. And also, if their advantage in having one country with the entire supply chain indigenized—rather than having random suppliers in Germany and the Netherlands—would mean that China would be ahead in its ability to produce mass **flops**?

</details>

**Dylan**: 迄今为止，中国仍然没有完全自主化的半导体供应链。但到2030年他们会拥有吗？到2030年，他们有可能做到。但迄今为止，中国所有的 **7纳米**和 **14纳米**产能都使用 **ASML DUV工具**。他们可以从 **ASML** 进口的数量很大。但 **ASML** 的绝大部分收入，尤其是所有的 **EUV** 收入，都来自中国以外。规模优势仍然有利于西方加上台湾、日本和韩国等。但他们正在尝试制造自己的 **DUV** 和 **EUV工具**，对吧？

<details>
<summary>Original English</summary>

**Dylan**: To date, China still does not have an entirely indigenized semiconductor supply chain. But would they in 2030? By 2030, it's possible that they do. But to date, all of China's **7 nm** and **14 nm** capacity uses **ASML DUV tools**. The amount that they can import from **ASML** is large. But the vast majority of **ASML**'s revenue, especially on **EUV** all of it, is outside of China. The scale advantage is still in the favor of the West plus Taiwan, Japan, and Korea, et cetera. But they're trying to make their own **DUV** and **EUV tools**, right?

</details>

**Dylan**: 他们正在尝试做所有这些事情。问题是他们能多快地在生产和质量方面取得进展和扩大规模。到目前为止，我们还没有看到这一点。现在我非常看好他们将在未来五到十年内能够做到这些事情。他们将真正扩大生产并加速发展。他们有更多的工程师致力于此，并且更愿意投入资本来解决问题。

<details>
<summary>Original English</summary>

**Dylan**: They're trying to do all these things. The question is how fast can they advance and scale up production as well as quality. To date, we haven't seen that. Now I'm quite bullish that they're going to be able to do these things over the next five to ten years. They will really scale up production and kick it into high gear. They have more engineers working on it and more desire to throw capital at the problem.

</details>

**Dwarkesh**: 那么到2030年，他们会完全自主化 **DUV** 吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: So by 2030, will they have fully indigenized **DUV**?

</details>

**Dylan**: 我认为肯定会。**DUV**，是的。

<details>
<summary>Original English</summary>

**Dylan**: I think for sure. **DUV**, yes.

</details>

**Dwarkesh**: 那么到2030年完全自主化 **EUV** 呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: And fully indigenized **EUV** by 2030?

</details>

**Dylan**: 我认为他们会有可用的工具。我不认为他们能大量生产。有“能用”和“量产地狱”的区别。**ASML** 在2010年代初就有了某种程度的 **EUV** 工作能力。这些工具不够精确。它们没有为大规模制造进行扩展，也不够可靠。他们必须提高产量，这都需要时间。“量产地狱”需要时间。这就是为什么 **EUV** 从实验室工作到在晶圆厂大规模生产又花了五到七年的时间。

<details>
<summary>Original English</summary>

**Dylan**: I think they'll have working tools. I don't think that they'll be able to manufacture a bunch yet. There's having it work, and then there's production hell. **ASML** had **EUV** working in the early 2010s at some capacity. The tools were not accurate enough. They were not scaled for high-volume manufacturing or reliable enough. They had to ramp production, and that all took time. Production hell takes time. That's why it took another five to seven years to get **EUV** into mass production at a fab rather than just working in the lab.

</details>

**Dwarkesh**: 你认为他们到2030年能生产多少台 **DUV工具**？

<details>
<summary>Original English</summary>

**Dwarkesh**: How many **DUV tools** do you think they'll be able to manufacture in 2030?

</details>

**Dylan**: **ASML**？

<details>
<summary>Original English</summary>

**Dylan**: **ASML**?

</details>

**Dwarkesh**: 不，中国。

<details>
<summary>Original English</summary>

**Dwarkesh**: No, China.

</details>

**Dylan**: 这是个很好的问题。深入研究这个供应链尤其具有挑战性。我们非常努力。在某些情况下，他们从日本供应商那里购买东西。如果他们想要一个完全自主化的供应链，他们就需要不从日本供应商那里购买这些透镜、投影光学元件或平台。他们需要内部制造。真的很难说他们能达到什么程度。我老实说，这就像是盲人摸象。但他们每年生产大约 **100台DUV工具**并非不可能，而 **ASML** 目前每年生产数百台 **DUV工具**。没有一家公司拥有每月生产 **100万片**晶圆的工艺节点。**Elon** 说他想这样做，中国显然也会这样做。**台积电**正在努力这样做。内存制造商也可能达到每月 **100万片**晶圆，但不是在单个晶圆厂。想到这种规模令人难以置信，也很难看到供应链为此而动员起来。我不想怀疑中国扩大规模的能力。我想这是一个有趣的问题。我认为在某个时候，**SemiAnalysis** 会对此进行深入研究。到什么时候，中国自主生产的规模会超过西方其他国家的总和。并将你的模型输入，预测他们何时能大规模拥有 **DUV** 机器和 **EUV** 机器？因为这里有一个问题，如果你对AI有长期的时间表——长期意味着2035年，这在宏观层面并不算太长——你是否应该预期中国将在半导体领域占据主导地位？这个问题没有被足够多地提出，因为如果你在旧金山，我们考虑的时间尺度是几周。如果你在旧金山以外，你根本不考虑 **AGI**。如果我们有 **AGI** 怎么办？如果有一个变革性的事物，它能带来数万亿甚至数十万亿美元的经济增长和token产出，但它发生在2035年怎么办？这对西方和中国意味着什么？**SemiAnalysis** 必须对此建立一个权威模型。当你把时间尺度拉得那么远时，这真的很有挑战性。我们倾向于关注追踪每一个数据中心、每一个晶圆厂和所有工具。我们追踪它们的去向，但这些事情的时间滞后相对较短。我们只能根据土地采购、许可证和涡轮机采购对数据中心容量做出相对准确的估计。我们知道所有这些东西的去向，这就是我们出售的数据。当你展望2035年时，事情会变得截然不同。你的误差范围变得如此之大，以至于很难做出估计。但归根结底，如果腾飞或时间线足够慢，我不明白中国为什么不能大幅追赶。从某种意义上说，我们有一个低谷，三到六个月前，甚至现在，中国模型比以往任何时候都更具竞争力。我认为 **Opus 4.6** 和 **GPT 5.4** 确实拉开了差距，使差距变得更大，但我相信会有新的中国模型出现。随着我们从销售提供完整推理链的token，转向销售自动化白领工作——一个自动化的软件工程师，你向他们发送请求，他们返回结果，后端有大量的思考，但他们不向你展示——从美国模型中提取学习成果到中国模型的能力将变得更加困难。其次，看看这些实验室的算力规模。**OpenAI** 去年年底大约有 **2吉瓦**。**Anthropic** 今年将达到 **2吉瓦**以上。到明年年底，他们都将拥有 **10吉瓦**的容量。中国AI实验室的算力扩展速度远不及此。在某个时候，当你无法将这些实验室的学习成果提取到中国模型中时，再加上 **OpenAI**、**Anthropic**、**谷歌**和**Meta** 都在进行的这场算力竞赛，他们最终会达到模型性能开始出现更大分歧的地步。然后看看所有这些用于数据中心的**资本支出**。**亚马逊**正在花费 **2000亿美元**，**谷歌** **1800亿美元**。所有这些公司都在花费数千亿美元的**资本支出**。今年美国大约有近 **1万亿美元**的**资本支出**投资于数据中心。这里的投资资本回报率是多少？你和我会认为数据中心**资本支出**的投资资本回报率非常高。如果我们看看 **Anthropic** 的收入，一月份他们增加了 **40亿美元**。二月份，这是一个较短的月份，他们增加了 **60亿美元**。我们将看看他们在三月和四月能做什么，因为算力限制正在阻碍他们的增长。**Claude** 的可靠性相当低，因为他们受到算力限制。但如果这种情况继续下去，那么这些数据中心的投资资本回报率将非常高。在某个时候，由于所有这些**资本支出**、这些模型产生的收入以及下游供应链，美国经济将在今年和明年开始越来越快地增长。中国还没有做到这一点。他们还没有建立起投资模型、达到能力水平，然后以如此规模部署模型的基础设施。当你看看 **Anthropic**，他们的年度经常性收入是 **200亿美元**。利润率低于 **50%**，至少根据 **The Information** 的最新报道。所以那是 **130亿或140亿美元**的算力租赁成本，这实际上是 **500亿美元**的**资本支出**，是有人为 **Anthropic** 支付的，以产生他们目前的收入。中国还没有做到这一点。如果 **Anthropic** 的收入再次增长 **10倍**——我认为我们的答案是“何时”，而不是“如果”——中国没有能力以这种规模部署算力。所以从某种意义上说，我们正处于快速腾飞期。我们不是在谈论某个日期前的**戴森球**，更像是收入以如此快的速度复合增长，以至于它确实影响了经济增长。这些实验室正在聚集的资源增长如此之快。中国还没有做到这一点，所以在这种情况下，美国和西方实际上正在分道扬镳。

<details>
<summary>Original English</summary>

**Dylan**: To date, China still does not have an entirely indigenized semiconductor supply chain. But would they in 2030? By 2030, it's possible that they do. But to date, all of China's **7 nm** and **14 nm** capacity uses **ASML DUV tools**. The amount that they can import from **ASML** is large. But the vast majority of **ASML**'s revenue, especially on **EUV** all of it, is outside of China. The scale advantage is still in the favor of the West plus Taiwan, Japan, and Korea, et cetera. But they're trying to make their own **DUV** and **EUV tools**, right? They're trying to do all these things. The question is how fast can they advance and scale up production as well as quality. To date, we haven't seen that. Now I'm quite bullish that they're going to be able to do these things over the next five to ten years. They will really scale up production and kick it into high gear. They have more engineers working on it and more desire to throw capital at the problem. So by 2030, will they have fully indigenized **DUV**? I think for sure. **DUV**, yes. And fully indigenized **EUV** by 2030? I think they'll have working tools. I don't think that they'll be able to manufacture a bunch yet. There's having it work, and then there's production hell. **ASML** had **EUV** working in the early 2010s at some capacity. The tools were not accurate enough. They were not scaled for high-volume manufacturing or reliable enough. They had to ramp production, and that all took time. Production hell takes time. That's why it took another five to seven years to get **EUV** into mass production at a fab rather than just working in the lab. How many **DUV tools** do you think they'll be able to manufacture in 2030? **ASML**? No, China. That's a great question. It's a bit of a challenge to look into this supply chain especially. We try really hard. In some instances, they're buying stuff from Japanese vendors. If they want a fully indigenized supply chain, they need to not buy these lenses, projection optics, or stages from Japanese vendors. They need to build it internally. It's really tough to say where they'll be able to get to. I honestly think it's a shot in the dark. But it's probably not unlikely that they'll be able to do on the order of **100 DUV tools** a year, whereas **ASML** is currently doing hundreds of **DUV tools** a year. No company has a process node where they make a million wafers a month. **Elon** says he wants to do it and China is obviously going to do it. **TSMC** is trying to do that. The memory makers may get to a million wafers a month as well, but not in a single fab. It's mind-boggling to think of that scale, and challenging to see the supply chain galvanized for that. I don't want to doubt China's capability to scale. I guess this is an interesting question. I think at some point **SemiAnalysis** will do the deep dive on this. By when would indigenized Chinese production be bigger than the rest of the West combined. And put in the input of your model of when they'll have **DUV** machines and **EUV** machines at scale? Because there's this question around if you have long timelines on AI—by long meaning 2035, which is not that long in the grand scheme of things—should you expect a world where China is dominating in semiconductors? It doesn't get asked enough because if you're in San Francisco, we're thinking on timescales of weeks. If you're outside of San Francisco, you're not thinking about **AGI** at all. What if we have **AGI**? What if you have this transformational thing that is commanding tens or hundreds of trillions of dollars of economic growth and token output, but it happens in 2035? What does that imply for the West versus China? **SemiAnalysis** has got to write the definitive model on this. It's really challenging when you move timescales out that far. What we tend to focus on is tracking every data center, every fab, and all the tools. We track where they're going, but the time lags for these things are relatively short. We can only make reasonably accurate estimates for data center capacity based on land purchasing, permits, and turbine purchasing. We know where all these things are going, that's the data we sell. As you go out to 2035, things are just so radically different. Your error bars get so large it's hard to make an estimate. But at the end of the day, if takeoff or timelines are slow enough, I don't see why China wouldn't be able to catch up drastically. In some sense, we've got this valley where, three to six months ago, or maybe even now, Chinese models are as competitive as they've ever been. I think **Opus 4.6** and **GPT 5.4** have really pulled away and made the gap a little bit bigger, but I'm sure some new Chinese models will come out. As we move from selling tokens where they provide the entire reasoning chain, to selling automated white-collar work—an automated software engineer, you send them the request, they give you the result back, and there's a bunch of thinking on the back end that they don't show you—the ability to distill out of American models into Chinese models will be harder. Second, look at the scale of the compute the labs have. **OpenAI** exited the year with roughly **two gigawatts** last year. **Anthropic** will get to **two-plus gigawatts** this year. By the end of next year, they'll both be at **ten gigawatts** of capacity. China is not scaling their AI lab compute nearly as fast. At some point, when you can't distill the learnings from these labs into the Chinese models, plus with this compute race that **OpenAI**, **Anthropic**, **Google**, and **Meta** are all racing on, they end up getting to a point where the model performance should start to diverge more. Then look at all this **CapEx** being spent on data centers. **Amazon** is spending **$200 billion**, **Google** **$180 billion**. All these companies are spending hundreds of billions of dollars on **CapEx**. There's nearly **a trillion dollars** of **CapEx** being invested in data centers in America this year, roughly. What's the return on invested capital here? You and I would think the return on invested capital for data center **CapEx** is very high. If we look at **Anthropic**'s revenues, in January they added **$4 billion**. In February, which was a shorter month, they added **$6 billion**. We'll see what they can do in March and April, given that compute constraints are what's bottlenecking their growth. The reliability of **Claude** is quite low because they're so compute constrained. But if this continues, then the **ROIC** on these data centers is super high. At some point, the US economy starts growing faster and faster over this year and next year because of all this **CapEx**, all the revenue these models are generating, and the downstream supply chain. China doesn't have that yet. They have not built the scale of infrastructure to invest in models, get to the capabilities, and then deploy these models at such scale. When you look at **Anthropic**, they're at **$20 billion ARR**. The margins are sub-**50 percent**, at least as last reported by **The Information**. So that's **$13 or $14 billion** of compute that it's running on rental cost-wise, which is actually **$50 billion** worth of **CapEx** that someone laid out for **Anthropic** to generate their current revenue. China has just not done this. If and when **Anthropic** **10Xs** revenue again—and I think our answer would be when, not if—China doesn't have the compute to deploy at that scale. So there is some sense that we're in a fast takeoff. It's not like we're talking about a **Dyson sphere** by X date, it's more like the revenue is compounding at such a rate that it does affect economic growth. The resources these labs are gathering are growing so fast. China hasn't done that yet, so in that case, the US and the West are actually diverging.

</details>

**Dylan**: 另一方面，这些基础设施投资的回报平平。也许它们不如预期。也许**谷歌**想把自由现金流降到零，明年花费 **3000亿美元**用于**资本支出**是错误的。也许他们就是错了，华尔街那些看空者和不理解AI的人是正确的。在这种情况下，美国正在建设所有这些产能，但却没有获得丰厚的回报。与此同时，中国能够建立一个完全垂直、自主化的供应链，而不是美国/日本/韩国/台湾/东南亚/欧洲国家共同建设这个垂直度较低的供应链。从某种意义上说，如果AI达到某些能力水平所需的时间比你的播客上绝大多数嘉宾认为的要长，那么中国在某个时候就能超越我们。时间线快，美国赢；时间线长，中国赢。

<details>
<summary>Original English</summary>

**Dylan**: The flip side is that these infrastructure investments have middling returns. Maybe they're not as good as hoped. Maybe **Google** is wrong for wanting to take free cash flow to zero and spend **$300 billion** on **CapEx** next year. Maybe they’re just wrong and people on Wall Street who are bearish and people who don't understand AI are correct. In that case, the US is building all this capacity but doesn't get great returns. Meanwhile, China is able to build a fully vertical, indigenized supply chain, instead of the US/Japan/Korea/Taiwan/SE Asia/Europe countries together building this less vertical supply chain. In a sense, at some point China is able to scale past us if AI takes longer to get to certain capability levels than the vast majority of your guests on this podcast believe. It's fast timelines, the US wins; long timelines, China wins.

</details>

**Dwarkesh**: 是的，但我不知道“快时间线”意味着什么。我认为你不必相信 **AGI** 才能拥有美国获胜的时间线。让我们回到内存。我认为华尔街和业内人士正在理解这有多么重要，但也许普通人并不理解这有多么重要。所以我们遇到了你之前谈到的内存危机。我之前问过，哦，我们能否通过回到 **7纳米**来解决 **EUV工具**短缺的问题？所以让我问一个关于内存的类似问题。**HBM** 是由 **DRAM** 制造的，但每晶圆面积的比特数比它所用的 **DRAM** 少三到四倍。未来加速器是否可能只使用商品 **DRAM** 而不是 **HBM**，这样我们就可以从现有的 **DRAM** 中获得更多的容量？我之所以认为这可能，是因为如果我们会有只负责工作的代理，而不是同步的聊天机器人应用程序，那么你不一定需要极快的延迟。也许你可以有更低的带宽，因为你将 **DRAM** 堆叠成 **HBM** 的原因是为了更高的带宽。是否有可能转向 **HBM** 加速器，并基本上拥有 **Claude Code Fast** 的反面，比如 **Claude Slow**？

<details>
<summary>Original English</summary>

**Dwarkesh**: Yeah but I don't know what fast timelines means. I don't think you have to believe in **AGI** to have the timelines where the US wins. Let's go back to memory. I think people on Wall Street and people in the industry are understanding how big this is, but maybe generally people don't understand what a big deal it is. So we've got this **memory crunch**, as you were talking about. And earlier I was asking about, oh, could we solve for the **EUV tool** shortage by going back to **seven nanometers**? So let me ask a similar question about memory. **HBM** is made of **DRAM**, but has three to four times fewer bits per wafer area than the **DRAM** it's made out of. Is it possible that accelerators in the future could just use commodity **DRAM** and not **HBM**, so we can get much more capacity out of the **DRAM** we have? The reason I think this might be possible is, if we're going to have agents that are just going off and doing work, and it's not a synchronous chatbot application, then you don't necessarily need extremely fast latency. Maybe you can have lower bandwidth, because the reason you stack **DRAM** into **HBM** is for higher bandwidth. Is it possible to go to **HBM** accelerators and basically have the opposite of **Claude Code Fast**, like have **Claude Slow**?

</details>

### 内存瓶颈与AI模型性能

**Dylan**: 归根结底，愿意为token支付最高价格的增量购买者，最终也是对价格不那么敏感的人。在资本主义社会中，算力应该分配给价值最高的商品，而私人市场通过支付意愿来决定这一点。在某种程度上，**Anthropic** 实际上可以发布一个慢速模式。他们可以发布 **Claude Slow Mode**，并显著增加每美元的token数量。他们可能会将 **Opus 4.6** 的价格降低 **4-5倍**，而速度可能只降低 **2倍**。推理吞吐量与速度的曲线在 **HBM** 上已经存在。然而他们没有这样做，因为没有人真正想使用一个慢速模型。此外，在这些代理任务中，模型可以在几小时的时间范围内运行是很棒的。但如果模型运行得更慢，这些小时就会变成一天。反之，如果模型运行得更快，这些小时就会变成一小时。没有人真正想等待一天，因为最高价值的任务也有一定的时间敏感性。我很难看到……是的，你可以使用普通的 **DRAM**。这有几个挑战。芯片的核心限制之一是芯片有一定尺寸，所有输入/输出（I/O）都从边缘引出。通常，芯片的左侧和右侧是 **HBM**——所以从芯片到 **HBM** 的I/O在侧面——然后顶部和底部是到其他芯片的I/O。如果你从 **HBM** 切换到 **DDR**，突然之间，边缘的I/O带宽会显著降低，但每个芯片的容量会显著增加。但你真正关心的指标是每晶圆的带宽，而不是每晶圆的比特数。因为限制 **FLOPS** 的是获取下一个矩阵的进出，为此你只需要更多的带宽。

<details>
<summary>Original English</summary>

**Dylan**: At the end of the day, the incremental purchaser who's willing to pay the highest price for tokens also ends up being the one that's less price-sensitive. Compute should be allocated, in a capitalistic society, towards the goods that have the highest value, and the private market determines this by willingness to pay. To some extent, **Anthropic** could actually release a slow mode. They could release **Claude Slow Mode** and increase tokens per dollar by a significant amount. They could probably reduce the price of **Opus 4.6** by **4-5x** and reduce the speed by maybe just **2x**. The curve on inference throughput versus speed is already there just on **HBM**. And yet they don't, because no one actually wants to use a slow model. Furthermore, on these agentic tasks, it's great that the model can run at a time horizon of hours. But if the model was running slower, those hours would become a day. Vice versa, if the model is running faster, those hours become an hour. No one really wants to move to a day-long wait period, because the highest-value tasks also have some time sensitivity to them. I struggle to see… Yes, you could use regular **DRAM**. There are a couple of challenges with this. One of the core constraints of chips is that a chip is a certain size, and all of the I/O escapes on the edges. Often, the left and right of the chip are **HBM**—so the I/O from the chip to the **HBM** is on the sides—and then the top and bottom are I/O to other chips. If you were to change from **HBM** to **DDR**, all of a sudden this I/O on the edge would have significantly less bandwidth, but significantly more capacity per chip. But the metric you actually care about is bandwidth per wafer, not bits per wafer. Because the thing that is constraining the **FLOPS** is just getting in and out the next matrix, and for that you just need more bandwidth.

</details>

**Dylan**: 是的，获取权重以及进出 **KV缓存**。在许多情况下，这些 **GPU** 并没有以完整的内存容量运行。这显然是一个系统设计问题：模型、硬件和软件协同设计。你必须弄清楚你需要多少 **KV缓存**，你在芯片上保留多少，你卸载到其他芯片并在需要时调用多少用于工具调用，以及你将此并行化到多少芯片上。显然，这个搜索空间非常广阔，这就是为什么我们有 **InferenceX**，一个开源模型，它为各种不同的芯片和模型搜索推理的最佳点。关键是，你并不总是受限于内存容量。你可能受限于 **FLOPS**、网络带宽、内存带宽或内存容量。如果你真的简化它，有四个限制，每个限制都可以分解成更多。如果你切换到 **DDR**，是的，你每 **DRAM** 晶圆生产的比特数是四倍，但突然之间，限制会发生很大变化，你的系统设计也会发生变化。你会变慢。市场会变小吗？也许。但同时，所有这些 **FLOPS** 都被浪费了，因为它们只是在那里等待内存。你不需要所有这些容量，因为你无法真正增加批处理大小，因为那样 **KV缓存**会需要更长的时间来读取。

<details>
<summary>Original English</summary>

**Dylan**: Yeah, getting out the weights and getting in and out the **KV cache**. In many cases, these **GPUs** are not running at full memory capacity. It's obviously a system design thing: model, hardware, and software co-design. You have to figure out how much **KV cache** you need, how much you keep on the chip, how much you offload to other chips and call when you need it for tool calling, and how many chips you parallelize this on. Obviously, the search space for this is very broad, which is why we have **InferenceX**, an open-source model that searches all the optimal points on inference for a variety of different chips and models. The point is, you're not always necessarily constrained by memory capacity. You can be constrained by **FLOPS**, network bandwidth, memory bandwidth, or memory capacity. If you really simplify it down, there are four constraints, and each of these can break out into more. If you switch to **DDR**, yes, you produce four times the bits per **DRAM** wafer, but all of a sudden the constraints shift a lot and your system design shifts. You go slower. Is the market smaller? Maybe. But also, all these **FLOPS** are wasted because they're just sitting there waiting for memory. You don't need all that capacity because you can't really increase batch size because then the **KV cache** would take even longer to read.

</details>

**Dwarkesh**: 有道理。**HBM** 和普通 **DRAM** 之间的带宽差异是多少？

<details>
<summary>Original English</summary>

**Dwarkesh**: Makes sense. What is the bandwidth difference between **HBM** and normal **DRAM**?

</details>

**Dylan**: 一个 **HBM4** 堆栈——我们来谈谈 **Rubin** 中的东西，因为我们一直在关注它——是 **2048比特**宽，连接在一个 **13毫米**宽的区域。它以大约每秒 **10吉传输**的速度传输内存。所以一个 **HBM4** 堆栈是 **2048比特**，在一个大约 **11到13毫米**宽的区域。那是你在芯片上占据的“海岸线”。在那条“海岸线”上，你有 **2048比特**以每秒 **10吉传输**的速度传输。你将它们相乘并除以八（比特转换为字节），你就得到了每个 **HBM** 堆栈大约每秒 **2.5太字节**。当你看看 **DDR**，在相同的区域，它可能是 **64或128比特**宽。那个 **DDR5** 的传输速度在每秒 **6.4到8000吉传输**之间。所以你的带宽显著降低。它是 **64** 乘以 **8000** 除以八，这让你得到每秒 **64吉字节**。即使你对 **128** 乘以 **8吉传输**进行慷慨的解释，在相同的“海岸线”上，你仍然是每秒 **128吉字节**，而 **HBM** 是每秒 **2.5太字节**。每边缘区域的带宽存在一个数量级的差异。如果你的芯片是方形的，或者 **26x33毫米**——这是单个芯片的最大尺寸——你只有这么多的边缘区域。在芯片内部，你放置了所有的算力。你可以做一些事情来尝试改变这一点，比如更多的 **SRAM** 或更多的缓存。但归根结底，你受到带宽的严格限制。

<details>
<summary>Original English</summary>

**Dylan**: An **HBM4** stack—let's talk about the stuff that's in **Rubin**, because that's what we've been indexing on—is **2048 bits** across, connected in an area that's **13 millimeters** wide. It transfers memory at around **10 giga-transfers a second**. So a stack of **HBM4** is **2048 bits** on an area that's roughly **11 to 13 millimeters** wide. That's the shoreline you're taking on the chip. In that shoreline, you have **2048 bits** transferring at **10 giga-transfers per second**. You multiply those together and divide by eight, bits to a byte, and you're at roughly **2.5 terabytes a second per HBM stack**. When you look at **DDR**, in that same area, it's maybe **64 or 128 bits** wide. That **DDR5** is transferring at anywhere from **6.4 to maybe 8,000 giga-transfers a second**. So your bandwidth is significantly lower. It's **64** times **8,000** divided by eight, which puts you at **64 gigabytes a second**. Even if you take a generous interpretation of **128** times **8 giga-transfers**, you're at **128 gigabytes a second** for the same shoreline, versus **2.5 terabytes a second**. There's an order of magnitude difference in bandwidth per edge area. If your chip is a square, or **26 by 33 millimeters**—which is the maximum size for an individual die—you only have so much edge area. On the inside of that chip, you put all your compute. There are things you can do to try and change that, like more **SRAM** or more caching. But at the end of the day, you're very constrained by bandwidth.

</details>

**Dwarkesh**: 那么问题来了，你可以在哪里抑制需求，为AI腾出足够的空间？我想情况特别糟糕，因为正如你所说，如果获得相同字节的 **HBM** 需要四倍的晶圆面积，那么你必须抑制四倍的笔记本电脑和手机消费需求，才能为AI腾出一个字节。这对未来一两年意味着什么？抱歉，这个问题有点长，你在你的时事通讯中说，到2026年，大型科技公司 **30%** 的**资本支出**将用于内存？

<details>
<summary>Original English</summary>

**Dwarkesh**: Then there's the question of where you can destroy demand to free up enough for AI. I guess the picture is especially bad because, as you're saying, if it takes four times more wafer area to get the same byte, for **HBM** you have to destroy four times as much consumer demand for laptops and phones to free up one byte for AI. What does this imply for the next year or two? Sorry for the run-on question, in your newsletter you said **30%** of Big Tech's **CapEx** in 2026 is going towards memory?

</details>

**Dylan**: 是的。

<details>
<summary>Original English</summary>

**Dylan**: Yes.

</details>

**Dwarkesh**: 这太疯狂了，对吧？在 **6000亿美元**左右的**资本支出**中，**30%** 仅仅用于内存。

<details>
<summary>Original English</summary>

**Dwarkesh**: That's insane, right? Of the **$600 billion** or whatever, **30%** is going just to memory.

</details>

**Dylan**: 是的。显然，**英伟达**在利润堆叠方面有一些操作，所以你必须将其分离出来，并将他们的利润应用于内存和逻辑。但归根结底，他们**资本支出**的三分之一将用于内存。

<details>
<summary>Original English</summary>

**Dylan**: Yes. Obviously, there's some level of margin stacking that **Nvidia** does, so you have to separate that out and apply their margin to the memory and the logic. But at the end of the day, a third of their **CapEx** is going to memory.

</details>

**Dwarkesh**: 这太疯狂了。未来一两年，随着内存危机袭来，我们应该期待什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: That's crazy. What should we expect over the next year or two as this **memory crunch** hits?

</details>

**Dylan**: 内存危机将继续加剧，价格将继续上涨。这会以不同方式影响市场的不同部分。人们会越来越讨厌AI吗？是的，因为智能手机和PC不会每年都变得更好。事实上，它们会越来越差。如果你看看 **iPhone** 的物料清单，内存占了多少比例？如果内存价格贵了两倍，**iPhone** 会贵多少？我相信 **iPhone** 有 **12吉字节**内存。以前每吉字节大约花费 **3-4美元**，所以是 **50美元**。但现在内存价格翻了三倍。假设 **DDR** 每吉字节 **12美元**。现在你谈论的是 **150美元**对比 **50美元**。这对**苹果**来说是 **100美元**的成本增加。**苹果**有一些利润，他们不会仅仅吞下这些利润。**NAND** 也有相同的市场动态，所以实际上，**iPhone** 的价格可能会增加 **150美元**。所以现在是 **100美元**的成本增加，这仅仅是 **DRAM**。**NAND** 也有相同的市场。所以实际上 **iPhone** 的价格可能会增加 **150美元**。**苹果**要么将这些成本转嫁给消费者，要么自己承担。我不认为**苹果**会大幅削减利润，也许他们会承担一点。但归根结底，这意味着最终消费者要为 **iPhone** 多支付 **250美元**。这仅仅是去年的价格与今天的价格相比。在**苹果**感受到压力之前会有一段滞后，因为他们通常有三到一年的内存长期合同。但归根结底，**苹果**会因此受到相当大的打击。他们要等到下一代 **iPhone** 发布才会真正调整。但这只是高端市场，每年只有几亿部手机。**苹果**每年销售两三亿部手机。市场主体是中低端。以前每年销售 **14亿部**智能手机。现在我们大约是 **11亿部**。我们的预测是，今年可能会降到 **8亿部**，明年降到 **5亿或6亿部**。我们查看了来自中国的一些数据点，来自我们在亚洲、新加坡、香港和台湾的分析师。他们一直在追踪这一点，他们看到**小米（Xiaomi）**和 **OPPO** 将中低端智能手机的销量削减了一半。是的，在 **1000美元**的 **iPhone** 上，物料清单只增加了 **150美元**，**苹果**的利润率更大。但对于较小的手机，物料清单中内存和存储的比例要大得多。而且利润率更低，所以吃掉利润的空间更小。而且他们通常也不倾向于签订内存长期协议。这之所以重要，是因为如果智能手机销量减半，这种下降将发生在中低端，而不是高端。所以并不是说释放的比特数减半。目前，消费设备占内存需求的一半以上。即使你将智能手机销量减半，由于减半的形态，低端削减的幅度会超过一半，而高端削减的幅度会小于一半，因为你和我都仍然会购买价格超过 **1000美元**的高端手机。即使它们贵一点，我们也会购买。而**苹果**的销量下降幅度不会像低端智能手机供应商那样大。PC也是如此。这对市场的影响是相当剧烈的。**DRAM** 被释放并流向AI芯片，AI芯片愿意签订长期合同并支付更高的利润，因为归根结底，他们从最终用户那里获得的利润要大得多。这可能会导致人们更讨厌AI。今天，你已经看到PC子版块和游戏PC推特上的所有梗图了。都是猫咪跳舞的视频，说：“这就是为什么内存价格翻倍，你买不到新的游戏 **GPU** 或台式机。”当内存价格再次翻倍时，尤其是 **DRAM**，情况会更糟。另一个有趣的动态是，不仅是 **DRAM**，还有 **NAND**。**NAND** 的价格也在上涨。这两个市场在过去几年里产能扩张非常缓慢，**NAND** 几乎为零。**NAND** 用于手机和PC的比例高于 **DRAM** 用于手机和PC的比例。当你抑制需求时，主要是为了 **DRAM**，你会释放更多的 **NAND**，这些 **NAND** 可以分配到其他市场。**DRAM** 的价格上涨幅度将大于 **NAND**，因为你从消费者那里释放了更多，事实上，你为AI生产了更多的内存。

<details>
<summary>Original English</summary>

**Dylan**: The **memory crunch** will continue to get harder, and prices will continue to go up. This affects different parts of the market differently. Are people going to hate AI more and more? Yes, because smartphones and PCs are not going to get incrementally better year on year. In fact, they're going to get incrementally worse. If you look at the bill of materials for an **iPhone**, what fraction of it is the memory? How much more expensive does an **iPhone** get if the memory is two times more expensive? I believe an **iPhone** has **12 gigabytes** of memory. Each gig used to cost roughly **$3-4**, so that's **$50**. But now the price of memory has tripled. Let's say it's **$12 per gig for DDR**. Now you're talking about **$150** versus **$50**. That's a **$100** increase in cost for **Apple**. **Apple** has some margin, they're not just going to eat the margin. **NAND** also has the same market dynamics, so in reality, it's probably a **$150** increase on the **iPhone**. So now that’s a **$100** cost increase and that’s just on the **DRAM**. The **NAND** also has the same sort of market. So in fact it’s probably a **$150** increase on the **iPhone**. **Apple** either has to pass that on to the consumer or eat it. I don't see **Apple** reducing their margin too much, maybe they eat a little bit. But at the end of the day, that means the end consumer is paying **$250** more for an **iPhone**. Now that’s just on last year’s pricing versus today’s. There is some lag before **Apple** feels the heat because they tend to have long-term contracts for memory that last three months to a year. But at the end of the day, **Apple** gets hit pretty hard by this. They won't really adjust until the next **iPhone** release. But that's the high end of the market, which is only a few hundred million phones a year. **Apple** sells **two or three hundred million** phones annually. The bulk of the market is mid-range and low-end. It used to be that **1.4 billion** smartphones were sold a year. Now we're at about **1.1 billion**. Our projections are that we might drop to **800 million** this year, and down to **500 or 600 million** next year. We look at data points out of China from some of our analysts in Asia, Singapore, Hong Kong, and Taiwan. They've been tracking this, and they see **Xiaomi** and **Oppo** cutting low-end and mid-range smartphone volumes by half. Yes, it’s only a **$150 BOM** increase on a **$1,000 iPhone** where **Apple** has some larger margin. But for smaller phones, the percentage of the **BOM** that goes to memory and storage is much larger. And the margins are lower, so there's less capacity to even eat the margins. And they have also generally tended not to do long-term agreements on memory. Why this is a big deal is that if smartphone volumes halve, that drop will happen in the low and mid-range, not the high end. So it’s not like the bits released are halving. Currently, consumer devices account for more than half of memory demand. Even if you halve smartphone volumes, because of the shape of the halving, the low end gets cut by more than half, while the high end gets cut by less than half, because you and I will still buy the high-end phones that cost north of **a thousand dollars**. We'll buy them even if they get a little bit more expensive. And **Apple**'s volumes will not go down as much as a low-end smartphone provider. The same applies to PCs. What this does to the market is quite drastic. **DRAM** gets released and goes to AI chips, who are willing to do longer-term contracts and pay higher margins, because at the end of the day the margin they extract from the end user is much larger. This probably leads to people hating AI even more. Today, you already see all the memes on PC subreddits and gaming PC Twitter. It's cat dancing videos saying, "This is why memory prices have doubled and you can't get a new gaming **GPU** or desktop." It's going to be even worse when memory prices double again, especially **DRAM**. Another interesting dynamic is that it's not just **DRAM**, it's also **NAND**. **NAND** is also going up in price. Both of these markets have expanded capacity very slowly over the last few years, **NAND** almost zero. The percentage of **NAND** that goes to phones and PCs is larger than the percentage of **DRAM** that goes to phones and PCs. As you destroy demand, mostly for **DRAM** purposes, you unlock more **NAND** that gets allocated and can go to other markets. The price increases of **DRAM** will be larger than those of **NAND** because you've released more from the consumer, and in fact, you've produced more memory for AI.

</details>

**Dwarkesh**: 抱歉，也许你刚才解释了，但我没听懂。是因为固态硬盘（SSD）在数据中心被大量使用吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, maybe you just explained it and I missed it. Is it because **SSDs** are being used in large quantities for data centers?

</details>

**Dylan**: 是的，但没有 **DRAM** 那么大量。

<details>
<summary>Original English</summary>

**Dylan**: They are, but not in as large quantities as **DRAM**.

</details>

**Dwarkesh**: 好的，所以它们也会增加，因为它们会使用一定数量，但对 **HBM** 的需求没有那么大。有道理。我之前没有意识到的一点，直到我读了你的一些时事通讯，就是未来几年阻碍逻辑扩展的限制与阻碍我们生产更多内存晶圆的限制非常相似。事实上，制造内存也需要完全相同的机器，也就是 **EUV工具**。所以我想现在有人可能会问，为什么我们不能制造更多的内存？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, so they will also increase because they'll be using some quantity, but there's not as much of a need as there is for **HBM**. Makes sense. One thing I didn't appreciate until I was reading some of your newsletters is that the same constraints preventing logic scaling over the next few years are quite similar to what's preventing us from producing more memory wafers. In fact, literally the same exact machine, this **EUV tool**, is needed for memory. So I guess the question someone could ask right now is, why can't we just make more memory?

</details>

**Dylan**: 正如我之前提到的，目前的限制不一定是今年或明年的 **EUV工具**。随着我们进入本世纪后期，它们才会成为限制。目前，限制更多的是他们物理上没有建造晶圆厂。在过去三到四年里，这些供应商没有建造新的晶圆厂，因为内存价格非常低。他们的利润很低，事实上，他们在2023年内存业务上亏损。所以他们决定不建造新的晶圆厂。市场随着时间的推移缓慢复苏，但直到去年才真正变得好起来。在2024年，我们一直在敲锣打鼓地说，推理意味着长上下文，这意味着大的 **KV缓存**，这意味着你需要大量的内存需求。我们已经谈论了一年半，两年了。理解AI的人当时在内存上投入了大量资金。所以你已经看到了这种动态，但现在它终于在定价中体现出来了。很明显的事情花了这么长时间才显现出来：长上下文意味着 **KV缓存**变大，你需要更多的内存。加速器一半的成本是内存。当然，他们会开始疯狂投入。这花了一年时间才真正反映在内存价格上。一旦内存价格反映出来，内存供应商又花了三到六个月才开始建造晶圆厂。这些晶圆厂需要两年才能建成。所以我们直到2027年底或2028年才能拥有真正有意义的晶圆厂来放置这些工具。相反，你看到了一些非常疯狂的事情来获取产能。**美光（Micron）**从一家台湾公司购买了一个制造落后芯片的晶圆厂。**海力士（Hynix）**和**三星（Samsung）**正在做一些非常疯狂的事情，试图在他们现有的晶圆厂扩大产能，这也对经济产生了巨大的连锁反应。那么为什么我们不能建造更多的产能呢？没有地方放置工具。不仅仅是 **EUV**；**DRAM** 和逻辑芯片还涉及其他工具。在逻辑芯片方面，对于 **N3**，最终晶圆成本的约 **28%** 是 **EUV**。当你看看 **DRAM**，它在十位数。它正在上升，但它占成本的比例要小得多。这些其他工具也是瓶颈，尽管它们的供应链没有 **ASML** 那么复杂。你看到**应用材料（Applied Materials）**、**泛林集团（Lam Research）**以及所有其他公司也在大幅扩大产能。但你没有地方放置工具，因为人类建造的最复杂的建筑是晶圆厂，而晶圆厂需要两年才能建成。

<details>
<summary>Original English</summary>

**Dylan**: The constraints, as I was mentioning earlier, are not necessarily **EUV tools** today or next year. They become that as we get to the latter part of the decade. Currently, the constraints are more that they physically just haven't built fabs. Over the last three to four years, these vendors have not built new fabs because memory prices were really low. Their margins were low, and in fact, they were losing money in 2023 on memory. So they decided they weren't building new fabs. The market slowly recovered over time but never really got amazing until last year. In 2024, we were banging on the drums that reasoning means long context, which means a large **KV cache**, which means you need a lot of memory demand. We've been talking about that for a year and a half, two years. People who understand AI went really long on memory then. So you’ve seen that dynamic, but now it has finally played out in pricing. It took so long for what was obvious: long context means the **KV cache** gets bigger, you need more memory. Half the cost of accelerators is memory. Of course they're going to start going crazy on it. It took a year for that to actually reflect in memory prices. Once memory prices reflected that, it took another three to six months for the memory vendors to start building fabs. Those fabs take two years to build. So we won't have really meaningful fabs to even put these tools in until late 2027 or 2028. Instead, you've seen some really crazy stuff to get capacity. **Micron** bought a fab from a company in Taiwan that makes lagging-edge chips. **Hynix** and **Samsung** are doing some pretty crazy things to try and expand capacity at their existing fabs, which also have large knock-on effects in the economy. So why can't we build more capacity? There's nowhere to put the tools. It's not just **EUV**; there are other tools involved in **DRAM** and logic. In logic, for **N3**, about **28%** of the cost of the final wafer is **EUV**. When you look at **DRAM**, it's in the teens. It's going up, but it's a much smaller percentage of the cost. These other tools are also bottlenecks, although their supply chains are not as complex as **ASML**'s. You see **Applied Materials**, **Lam Research**, and all these other companies expanding capacity a lot as well. But you don't have anywhere to put the tool, because the most complex buildings people make are fabs, and fabs take two years to build.

</details>

### Elon Musk的TeraFab愿景与半导体制造挑战

**Dwarkesh**: 我最近采访了 **Elon**，他的整个计划是他们将建造这个 **TeraFab**，他们将建造洁净室。我甚至不会问你关于“脏房间”的事情，但假设他们建造了洁净室。我有几个问题。第一，你认为 **Elon** 的公司能否比人们通常建造得更快？这不是关于建造最终工具。这只是关于建造设施本身。快速建造洁净室有多复杂？如果这是我们今年或明年面临的瓶颈，**Elon** 凭借他“快速行动”的方法，能否更快地做到这一点？第二，如果两年后，你的观点是我们不再受限于洁净室空间，而是受限于工具，那这甚至还重要吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: I interviewed **Elon** recently, and his whole plan is that they're going to build this **TeraFab** and they're going to build the clean rooms. I won't even ask you about the dirty rooms thing, but let's say they build the clean rooms. I have a couple of questions. One, do you think this is the kind of thing that **Elon** Co. could build much faster than people conventionally build it? This is not about building the end tools. This is just about building the facility itself. How complicated is it to just build the clean room extremely fast? Is this something that **Elon**, with his "move fast" approach, could do much faster if that's what we're bottlenecked on this year or next year? Two, does that even matter if, in two years, your view is that we're not bottlenecked on clean room space, but on the tooling?

</details>

**Dylan**: 就像任何复杂的供应链一样，这需要时间，而且限制会随着时间的推移而转移。即使某个东西不再是限制，也不意味着那个市场不再有利润。例如，能源在几年后不会成为一个大瓶颈，但这不意味着能源没有超快速增长，也没有利润。它只是不是关键瓶颈。在晶圆厂领域，洁净室是今年和明年的最大瓶颈。到2028年、2029年、2030年，那里仍然会有限制。**Elon** 的特点是他拥有巨大的能力来聚集物理资源和真正聪明的人来建造东西。他招募优秀人才的方式是尝试建造最疯狂的东西。在AI领域，这并没有真正奏效，因为每个人都在尝试建造 **AGI**。每个人都非常有抱负。但在去火星、制造能自行着陆的火箭、全自动电动汽车或人形机器人方面，这些都是招募那些认为这是世界上最重要问题的人来解决这个问题的方法，因为他是唯一一个真正努力的人。在半导体领域，他声称他想建造一个每月生产 **100万片**晶圆的晶圆厂。没有人有那么大的晶圆厂。他有可能招募到很多非常棒的人，让他们从事这项疯狂的任务，即每月生产 **100万片**晶圆。第一步是建造洁净室，我认为他可能可以做到。他关于删除东西、可以脏一点没关系的心态，可能是不对的。实际上我认为 **100%** 是不对的。你需要晶圆厂非常干净。晶圆厂里所有的空气每三秒钟更换一次，就是这么快。必须有极少的颗粒。但我认为他可以建造洁净室。这需要一两年时间。最初不会超快，但随着时间的推移，他会越来越快。真正复杂的部分实际上是开发工艺技术和制造晶圆。我不认为他能那么快地开发出来。这需要大量的知识积累。最复杂的昂贵工具和供应链集成是由**台积电**、**英特尔（Intel）**或**三星**完成的。这两家其他公司在这方面甚至都不太擅长，而且它们都极其复杂。

<details>
<summary>Original English</summary>

**Dylan**: As with any complex supply chain, it takes time, and constraints shift over time. Even if something is no longer a constraint, that doesn't mean that market no longer has margin. For example, energy will not be a big bottleneck a couple of years from now, but that doesn't mean energy isn't growing super fast and there's no margin there. It's just not the key bottleneck. In the space of fabs, clean rooms are the biggest bottleneck this year and next year. As we get to 2028, 2029, 2030, there will still be constraints there. The thing about **Elon** is he has a tremendous capability to garner physical resources and really smart people to build things. The way he recruits amazing people is by trying to build the craziest stuff. In the case of AI, that hasn't really worked because everyone's trying to build **AGI**. Everyone is very ambitious. But in the case of going to Mars, making rockets that land themselves, fully autonomous electric cars, or humanoid robots, these are methods of recruiting the people who think that's the most important problem in the world to work on that problem, because he's the only one trying really hard. In the case of semiconductors, he stated he wants to make a fab that's a **million wafers per month**. No one has a fab that big. It's possible that he's able to recruit a lot of really awesome people and get them on this crazy task of building a **million wafers a month**. Step one is to build the clean room, and that I think he probably can do. His mindset around deleting things, that it can be dirty, it's fine, is probably not right. Actually I think it’s **100%** not right. You need the fab to be very clean. All of the air in the fab gets replaced every three seconds, it’s that fast. There have to be so few particles. But I think he can build the clean room. It'll take a year or two. Initially, it won't be super fast, but over time, he'll get faster at it. The really complex part is actually developing a process technology and building wafers. I don't think he can develop that quickly. That has a lot of built-up knowledge. The most complicated integration of very expensive tools and supply chains is done by **TSMC**, **Intel**, or **Samsung**. These two other companies aren't even that great at it, and they're tremendously complex.

</details>

**Dwarkesh**: 如果到2030年突然出现某种彻底的颠覆，我们不再使用 **EUV**，你会感到多么惊讶？如果我们使用某种效果更好、生产更简单、产量更大的东西呢？我确信作为业内人士，这听起来像一个非常天真的问题，但你明白我的意思吗？我们应该对某种完全出乎意料的事物，使所有这些都变得无关紧要的可能性，抱有多大的信心？

<details>
<summary>Original English</summary>

**Dwarkesh**: How surprised would you be if in 2030 there just happened to be some total disruption where we're not using **EUV**? What if we're using something that has much better effects, is much simpler to produce, and can be produced in much bigger quantities? I'm sure as an industry insider that sounds like a totally naive question, but do you see what I'm asking? What probability should we put on something coming totally out of left field to make all of this irrelevant?

</details>

**Dylan**: 对于非常简单且易于扩展的东西，我给予的概率非常非常低。有一些公司正在研究粒子加速器或同步加速器，它们产生的光线要么是 **13.5纳米**，像 **EUV**，要么是更窄的波长，像 **7纳米**的X射线，然后用于光刻工具。但这些东西是巨大的粒子加速器，产生这种光线。建造它非常复杂。有几家公司，我认为这可能对 **EUV** 之外的行业造成巨大颠覆。但我不认为我们会奇迹般地建造出一种新的、直接写入且超级简单的东西，并且可以大规模生产，尽管有一些尝试这样做。

<details>
<summary>Original English</summary>

**Dylan**: Something that's very simple and easy to scale, I assign a very, very low probability. There are a number of companies working on effectively particle accelerators or synchrotrons that generate light that's either **13.5 nanometer**, like **EUV**, or an even narrower wavelength, like X-ray at **7 nanometers**, to then use in lithography tools. But those things are massive particle accelerators generating this light. It's a very complicated thing to build. There are a couple of companies and I think that could be a big disruption to the industry beyond **EUV**. But I don't think we're going to magically build something new that is direct write and super simple, and can be manufactured at huge volumes, although there are some attempts to do things like this.

</details>

**Dwarkesh**: 我之所以问，是因为如果你想想 **Elon** 过去的公司，火箭技术曾被认为是——而且确实是——极其复杂的。看，我只是一个天真的空谈者，与 **Elon** 相比。我建造了什么？所以也许这有可能。为了将来制造更多的内存，我们能否像制造 **3D NAND** 那样制造 **3D DRAM**，然后回到 **DUV**？

<details>
<summary>Original English</summary>

**Dwarkesh**: I ask because if you think about **Elon**'s companies in the past, rocketry was this thing that was thought to be—and is—incredibly complicated. Look, I'm just a naive yapper compared to **Elon**. What have I built? So maybe it's possible. In order to build more memory in the future, could we build **3D DRAM** the way we do **3D NAND** and then go back to **DUV**?

</details>

**Dylan**: 这就是目前的希望。每个人对 **3D DRAM** 的路线图都是你仍然会使用 **EUV**，因为你想要更紧密的**套刻精度**。当你进行这些后续处理步骤时，所有东西都是垂直堆叠的，并且你会有更多的层堆叠在一起。你希望间距更紧密。所以通常，人们仍然试图用 **EUV** 来做。但 **3D** 会改变单个 **EUV** 通过能制造多少比特的计算。如果你转向 **3D DRAM**，这个数字会大幅上升。这就是希望。现在，每个人的路线图都是从当前的 **6F单元**，到 **4F单元**，然后最终在本世纪末或下世纪初实现 **3D DRAM**。仍然有很多研发、制造和集成工作要做。我不会说这不可能。我认为这很可能会发生。它还需要对晶圆厂进行大规模的重新工具化。晶圆厂中工具的构成将非常不同。光刻工具实际上是唯一没有太大不同的东西。但它们相对于不同类型的化学气相沉积、原子层沉积、干法刻蚀或具有不同化学性质的不同类型刻蚀腔室的数量……你为不同的工艺节点拥有所有这些不同的工具。你不能在短时间内将逻辑晶圆厂转换为 **DRAM** 晶圆厂，反之亦然，或者将 **NAND** 晶圆厂转换为 **DRAM** 晶圆厂。同样，现有的 **DRAM** 晶圆厂需要大量的重新工具化，才能从 **1-alpha** 转向 **1-beta** 再到 **1-gamma** 工艺节点，因为它们必须添加 **DUV** 并改变使用 **EUV** 时的沉积和刻蚀化学堆栈。而且 **EUV工具**必须在那里。此外，当你转向 **3D DRAM** 时，将会有更大的转变，所以这些晶圆厂需要进行大量的重新工具化。这将是一个巨大的颠覆。这将使 **EUV** 需求普遍降低。但正如我们所看到的，随着时间的推移，光刻需求占晶圆成本的百分比呈上升趋势。在2014年左右，它占晶圆成本的 **17%**，在过去十五年中已升至 **30%**。对于 **DRAM**，它在低到中十位数，现在已趋向于高十位数。在我们达到 **3D DRAM** 之前，它可能会超过 **20%**。但如果达到 **3D DRAM**，最终晶圆成本占 **EUV** 的百分比将再次下降。

<details>
<summary>Original English</summary>

**Dylan**: That is the hope currently. Everyone's roadmap for **3D DRAM** is that you'll still use **EUV** because you want to have that tighter **overlay**. When you're doing these subsequent processing steps, everything is vertically stacked and you have more layers on top of each other. You want the pitches to be tighter. So generally, people are still trying to do it with **EUV**. But what **3D** would do is change the calculation of how many bits a single **EUV** pass can make. That number would go up drastically if you go to **3D DRAM**. That is the hope. Right now, everyone's roadmap goes from the current **6F cell**, to a **4F cell**, and then finally **3D DRAM** by the end of the decade or early next decade. There's still a lot of R&D, manufacturing, and integration to be done. I wouldn't call that out of the cards. I think it's very likely going to happen. It's also going to require a huge retooling of fabs. The breakdown of tools in a fab will be very different. The lithography tool is actually the only thing that isn't that different. But the number of them relative to different types of chemical vapor deposition, atomic layer deposition, dry etch, or different kinds of etch chambers with different chemistries… You have all these different tools for different process nodes. You can't just convert a logic fab to a **DRAM** fab, or vice versa, or a **NAND** fab to a **DRAM** fab, in a short amount of time. In the same way, existing **DRAM** fabs require a lot of retooling just to go from **1-alpha** to **1-beta** to **1-gamma** process nodes, because they have to add **DUV** and change the chemistry stacks for when you’re using **EUV** in terms of deposition and etch. And the **EUV tool** has to be there. Furthermore, when you change to **3D DRAM**, there's going to be an even larger shift, so a lot of retooling of these fabs needs to happen. That would be a big disruption. That would make **EUV** demand generally lower. But as we've seen across time, lithography demand as a percentage of wafer cost has trended up. Around the 2014 era, it was **17%** of the wafer cost, and it's gone to **30%** over the last fifteen years. For **DRAM**, it was in the low to mid-teens, and now it's trended toward the high teens. Before we get to **3D DRAM**, it'll likely cross into the **20%** range. But then, if we get to **3D DRAM**, the total end wafer cost as a percentage of **EUV** tanks again.

</details>

**Dwarkesh**: 我猜你不太关心成本百分比，而更关心它对生产的瓶颈程度。

<details>
<summary>Original English</summary>

**Dwarkesh**: I guess you care less about the percent of cost and more about how much it bottlenecks production.

</details>

**Dylan**: 是的，但成本百分比——

<details>
<summary>Original English</summary>

**Dylan**: Right, but the percentage of cost—

</details>

**Dwarkesh**: 这是一个代理，是的。如果你是 **黄仁勋（Jensen）** 或 **Sam Altman**，或者任何将从AI算力扩展中获得巨大收益的人，他们会去**台积电**说：“为什么我们不能访问Y和Z？”但我想你说的重点是，从某种意义上说，**台积电**做什么并不重要。事实上，即使**英特尔**和**三星**建造更多的晶圆厂，从长远来看，你仍然会受到 **ASML** 和其他工具和材料制造商的瓶颈。首先，这种解释正确吗？其次，硅谷的人现在应该去荷兰，试图说服 **ASML** 制造更多的工具，以便他们在2030年能拥有更多的AI算力吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: It’s a proxy, yeah. If you're **Jensen** or **Sam Altman**, or whoever stands to gain a lot from scaling up AI compute, there are these stories that they'd go to **TSMC** and say, "Why can't we access Y and Z?" But I think the point you're making is that it doesn't really matter what **TSMC** does in some sense. In fact, even if you have **Intel** and **Samsung** building more foundries, in the long run, you're going to be bottlenecked by **ASML** and other tool and material makers. First, is that a correct interpretation? Second, should Silicon Valley people be going to the Netherlands right now to try to pitch **ASML** to make more tools so that in 2030 they can have more AI compute?

</details>

**Dylan**: 这是我们在2023年、2024年和2025年看到的一个有趣的动态。那些比其他人更早看到能源瓶颈的人，不对称地去了**西门子（Siemens）**、**三菱（Mitsubishi）**，当然还有 **GE Vernova**，购买了涡轮机产能。现在他们能够收取额外的费用，因为能源原因在这些地方部署这些涡轮机。同样地，这也可以用于 **EUV**，除了 **ASML** 不会轻易信任任何随机的傻瓜来购买 **EUV工具**。这些涡轮机比 **EUV工具**便宜得多，而且生产数量也多得多。特别是当你谈到工业燃气轮机时，不仅仅是联合循环，还有更便宜、更小、效率更低的那些，人们会为这些支付定金。有人可以这样做。有人应该去荷兰说：“我给你 **10亿美元**。你给我权利在两年后购买 **10台EUV工具**，我是第一个排队的。”然后在这两年里，你等着所有人意识到：“哦，天哪，我没有足够的 **EUV工具**，”然后你试图以某种溢价出售你的期权。你实际上只是在说：“**ASML**，你太笨了。你没有从这些工具中赚取足够的利润。我要赚取利润。”问题是，**ASML** 会同意吗？我不这么认为。

<details>
<summary>Original English</summary>

**Dylan**: It's a funny dynamic we saw in 2023, 2024, and 2025. People who saw the energy bottleneck before others asymmetrically went to **Siemens**, **Mitsubishi**, and of course **GE Vernova**, and bought up turbine capacity. Now they're able to charge excess amounts for deploying these turbines in places because of energy. In the same sense, this could be done for **EUV**, except **ASML** is not just going to trust any random bozo who wants to buy **EUV tools**. These turbines are much cheaper than **EUV tools**, and there's many more of them produced. Especially once you get to industrial gas turbines, not just combined-cycle but the cheaper, smaller, less efficient ones, people put down deposits for these. Someone could do this. Someone should go to the Netherlands and be like, "I'll pay you **a billion dollars**. You give me the right to purchase **ten EUV tools** two years from now, and I'm first in line." Then over those two years, you go around and wait for everyone to realize, "Oh crap, I don't have enough **EUV tools**," and you try to sell your option at some premium. All you're effectively doing is saying, "**ASML**, you're dumb. You weren't making enough margin on these. I'm going to make a margin." The question is, will **ASML** even agree to this? I don't think so.

</details>

**Dwarkesh**: 至少他们会从中学到需求信号，从而增加产量。

<details>
<summary>Original English</summary>

**Dwarkesh**: There's a world where they at least get the demand signal from that to increase production.

</details>

**Dylan**: 有可能。我同意。

<details>
<summary>Original English</summary>

**Dylan**: Potentially. I agree.

</details>

**Dwarkesh**: 但听起来你是在说，即使他们想增加产量，考虑到供应链，他们也做不到。

<details>
<summary>Original English</summary>

**Dwarkesh**: But it sounds like you're saying they couldn't even increase production if they wanted to, given the supply chain.

</details>

**Dylan**: 是的。但这正是市场……如果他们不能增加产量，就像**台积电**不能那么快增加产量一样，然而需求却在飙升，那么显而易见的解决方案就是套利。你和我知道需求远高于他们预测的，也远高于他们的建造能力。你通过锁定产能，签订远期合同，然后在其他人意识到一切都搞砸了，我们没有足够的产能时，再试图以更高的价格出售你的期权来套利。那样你就会获得 **ASML** 和**台积电**本应收取的巨额利润。但问题是，我不知道 **ASML** 和**台积电**是否会同意这样做。

<details>
<summary>Original English</summary>

**Dylan**: Right. But that's exactly the market in which… If they can't increase production, just like **TSMC** cannot increase production that fast, and yet demand is mooning, then the obvious solution is to arbitrage this. You and I know demand is way higher than they're projecting and their capability to build. You arbitrage this by locking up the capacity, doing a forward contract, and then trying to sell it at a later date once other people realize everything is fucked and we don't have enough capacity. Then you'll have this insane margin that **ASML** and **TSMC** should have been charging. But the thing is, I don't know if **ASML** and **TSMC** will ever agree to this.

</details>

### 电力供应与数据中心建设

**Dwarkesh**: 现在让我问你关于电力的问题。听起来你认为电力可以任意扩展。

<details>
<summary>Original English</summary>

**Dwarkesh**: Let me ask you about power now. It sounds like you think power can be arbitrarily scaled.

</details>

**Dylan**: 不是任意，但可以。

<details>
<summary>Original English</summary>

**Dylan**: Not arbitrarily, but yes.

</details>

**Dwarkesh**: 但超出了这些数字。如果我没记错的话，你关于AI实验室如何增加电力的博客文章暗示，**GE Vernova**、**三菱**和**西门子**每年可以生产 **60吉瓦**的燃气轮机。然后还有其他来源，但它们不如涡轮机重要。我猜只有一小部分用于AI。如果到2030年我们有足够的逻辑和内存来每年生产 **200吉瓦**，你是否认为这些东西正在朝着每年超过 **200吉瓦**的方向发展，或者你看到了什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: But beyond these numbers. If I'm remembering correctly, your blog post on how AI labs are increasing power implied that **GE Vernova**, **Mitsubishi**, and **Siemens** could produce **60 gigawatts** a year in gas turbines. Then there are these other sources, but they're less significant than the turbines. Only a fraction of that goes to AI, I assume. If in 2030 we have enough logic and memory to do **200 gigawatts** a year, do you just think that these things are on a path to ramp up to more than **200 gigawatts** a year, or what do you see?

</details>

**Dylan**: 现在我们是 **20或30吉瓦**。顺便说一下，这是关键的IT容量，这一点很重要。当我说这些吉瓦时，我指的是关键的IT容量。服务器插电，它消耗的电量。但链条上存在损耗。传输、转换、冷却等方面都有损耗。所以你应该将今年的 **20吉瓦**或本世纪末的 **200吉瓦**乘以 **20-30%** 的系数。然后还有容量系数。涡轮机不会 **100%** 运行。如果你看看 **PJM**，我认为它是美国最大的电网——覆盖中西部和东北部部分地区——在他们的模型中，他们希望拥有大约 **20%** 的过剩容量。在这 **20%** 的过剩容量中，他们以 **90%** 的效率运行所有涡轮机，因为它们因可靠性、维护等原因而降额。实际上，能源的铭牌容量总是远高于实际的最终关键IT容量，因为所有这些因素。但不仅仅是涡轮机。如果你只是用涡轮机发电，那很简单、无聊、容易。人类和资本主义远比这更有效。那篇博客文章的重点是，是的，只有三家公司生产联合循环燃气轮机，但我们能做的还有很多。我们可以使用航空衍生产品。我们可以将飞机发动机改装成涡轮机。市场上甚至有新的进入者，比如 **Boom Supersonic** 正在尝试这样做并与 **Crusoe** 合作。还有市场上已经存在的所有其他公司。还有中速往复式发动机：像柴油发动机一样旋转的发动机。有十家公司以这种方式制造发动机。我来自佐治亚州，人们以前会说：“哦，伙计，你的 **RAM** 卡车里有 **Cummins** 发动机。”汽车制造业正在下降，所以这些公司都有产能，可以扩大规模并将其转换为数据中心电力。你可以把所有这些往复式发动机都放进去。它不如联合循环那么清洁，但如果你愿意，可以将其从柴油转换为燃气。船用发动机呢？所有这些大型货船的发动机都很棒。**Nebius** 正在新泽西州的一个**微软**数据中心这样做。他们正在运行船用发动机发电。**Bloom Energy** 正在生产燃料电池。我们一年半以来一直对它们非常看好，因为它们有能力增加产量。它们增加产量的投资回收期非常快，即使成本比联合循环（成本和效率最佳）略高。然后是太阳能加电池，随着成本曲线继续下降，它们可以上线。还有风能，你可能只期望获得 **15%** 的最大功率，因为事物会波动，但你可以添加电池。所有这些东西。另一件事是，电网的规模是为了确保在夏季最热的一天，用电高峰时不会断电。但实际上，那是一个比平均水平高 **10-20%** 的负荷峰值。如果你有足够的公用事业规模电池，或者只在一年中一小部分时间运行的调峰电厂——这些可以是燃气、工业燃气轮机、联合循环、电池或我提到的任何其他来源——那么突然之间，你为数据中心解锁了美国电网的 **20%**。大部分时间这些容量都处于闲置状态。它真的只在那个高峰期存在，一年中只有几天，每天几个小时。如果你有足够的容量来吸收那个峰值负荷，那么突然之间你就全部转移了。今天，数据中心只占美国电网电力的 **3-4%**，到2028年将达到 **10%**。但如果你能像这样解锁美国电网的 **20%**，那并不疯狂。美国电网是太瓦级的，而不是数百吉瓦级的。所以我们可以增加更多的能源。我不是说这很容易。这些事情会很困难。有很多艰苦的工程，人们必须承担风险，以及人们必须使用的新技术。但 **Elon** 是第一个进行**表后燃气发电**的人，从那时起，我们看到人们为获取电力而采取的各种不同措施呈爆炸式增长。它们并不容易，但人们能够做到。供应链比芯片简单得多。

<details>
<summary>Original English</summary>

**Dylan**: Right now we're at **20 or 30**. This is critical IT capacity, by the way, which is an important thing to mention. When I'm talking about these gigawatts, I'm talking about critical IT capacity. Server plugged in, that's how much power it pulls. But there are losses along the chain. There is loss on transmission, conversion, cooling, et cetera. So you should gross this factor up from **20 gigawatts** for this year, or **200 gigawatts** by the end of the decade, to some number **20-30%** higher. Then you have capacity factors. Turbines don't run at **100 percent**. If you look at **PJM**, which I think is the largest grid in America—covering the Midwest and some of the Northeast area—in their models they want to have roughly **20 percent** excess capacity. Within that **20 percent** excess capacity, they're running all the turbines at **90%** because they are derated some for reliability, maintenance, and so on. In reality, the nameplate capacity for energy is always way higher than the actual end critical IT capacity because of all these factors. But it's not just turbines. If you were just making power from turbines, that's simple, boring, and easy. Humans and capitalism are far more effective. The whole point of that blog was that, yes, there are only three people making combined-cycle gas turbines, but there's so much more we can do. We can do aeroderivatives. We can take airplane engines and turn them into turbines. There are even new entrants in the market, like **Boom Supersonic** trying to do that and working with **Crusoe**. Also there's all the other ones like that already exist in the market. There are also medium-speed reciprocating engines: engines that spin in circles, like a diesel engine. There are ten people who make engines that way. I'm from Georgia, and people used to be like, "Oh man, you got a **Cummins** engine in there," regarding **RAM** trucks. Automobile manufacturing is going down, so these companies all have capacity and could scale and convert that for data center power. You stick all these reciprocating engines in. It's not as clean as combined-cycle, but maybe you can convert them from diesel to gas if you want. What about ship engines? All of these engines for massive cargo ships are great. **Nebius** is doing that for a **Microsoft** data center in New Jersey. They're running ship engines to generate power. **Bloom Energy** is doing fuel cells. We've been very positive on them for a year and a half now because they have such a capability to increase their production. Their payback period for a production increase is very fast, even if the cost is a little bit higher than combined-cycle, which is the best for cost and efficiency. Then there's solar plus battery, which can come online as those cost curves continue to come down. There's wind, where you might only expect **15 percent** of the maximum power because things oscillate, but you add batteries. There are all these things. The other thing is that the grid is scaled so we don't cut off power at peak usage on the hottest day of the summer. But in reality, that's a load spike that is **10-20%** higher than the average. If you just put enough utility-scale batteries, or peaker plants that only run a small portion of the year—and those could be gas, industrial gas turbines, combined-cycle, batteries, or any of the other sources I mentioned—then all of a sudden you've unlocked **20%** of the US grid for data centers. Most of the time that capacity is sitting idle. It's really only there for that peak, which is just a few hours over a few days of the year. If you have enough capacity to absorb that peak load, then all of the sudden you’ve transferred it all. Today, data centers are only **3-4%** of the power of the US grid, and by 2028 they'll be **10%**. But if you can unlock **20%** of the US grid like this, it's not that crazy. The US grid is terawatt-level, not hundreds-of-gigawatts-level. So we can add a lot more energy. I'm not saying it's easy. These things are going to be hard. There's a lot of hard engineering, risks people have to take, and new technologies people have to use. But **Elon** was the first to do this **behind-the-meter** gas, and since then we've seen an explosion of different things people are doing to get power. They're not easy, but people are gonna be able to do them. The supply chains are just way simpler than chips.

</details>

**Dwarkesh**: 有趣。他在采访中指出，他正在寻找的特定涡轮机的特定叶片，其交货期超过2030年。你的观点是——

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. He made the point during the interview that for the specific blade for the specific turbine he was looking at, the lead times go out beyond 2030. Your point is that—

</details>

**Dylan**: 这太棒了。还有很多其他方法可以发电。只是效率低下。没关系。

<details>
<summary>Original English</summary>

**Dylan**: That's great. There are so many other ways to make energy. Just be inefficient. It's fine.

</details>

**Dwarkesh**: 目前，联合循环燃气轮机的**资本支出**是每千瓦 **1500美元**。你是说，要么使用比这贵得多的技术，要么其他东西变得足够便宜，使其具有竞争力，这才有意义吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Right now, combined-cycle gas turbines have **CapEx** of **$1,500 per kilowatt**. Are you saying it would make sense to have either technologies that are much more expensive than that, or other things are getting cheap enough to make it competitive?

</details>

**Dylan**: 完全正确。它可以高达每千瓦 **3500美元**。它可以是联合循环成本的两倍，而 **GPU** 的**总拥有成本（TCO）**只增加了每小时几美分。因为我们一直在谈论 **Hopper** 的定价，**1.40美元**，假设电价翻倍。原来 **1.40美元**的 **Hopper** 现在成本是 **1.50美元**。我不在乎，因为模型改进得太快了，它们的边际效用远超那 **10美分**的能源成本增加。

<details>
<summary>Original English</summary>

**Dylan**: Exactly. It can be as high as **$3,500 per kilowatt**. It could be twice as much as the cost of combined-cycle, and the total cost of the **GPU** on a **TCO** basis has only gone up a few cents per hour. Because we've been talking about **Hopper** pricing, **$1.40**, let's say the power price doubles. The **Hopper** that was **$1.40** is now **$1.50** in cost. I don't care, because the models are improving so fast that the marginal utility of them is worth way more than that **ten-cent** increase in energy.

</details>

**Dwarkesh**: 所以你是说电网的 **20%**——电网大约是 **1太瓦**——可以仅仅通过公用事业规模的电池上线，增加你愿意投入电网的容量。

<details>
<summary>Original English</summary>

**Dwarkesh**: So you're saying **20 percent** of the grid—the grid is about **one terawatt**—can just come online from utility-scale batteries, increasing what you'd be comfortable putting on the grid.

</details>

**Dylan**: 顺便说一句，那里的监管机制并不容易。

<details>
<summary>Original English</summary>

**Dylan**: The regulatory mechanism there is not easy, by the way.

</details>

**Dwarkesh**: 但如果这真的发生，那就是 **200吉瓦**。仅仅是你提到的不同燃气发电来源——不同种类的发动机和涡轮机——加起来，到本世纪末能解锁多少吉瓦？

<details>
<summary>Original English</summary>

**Dwarkesh**: But that's **200 gigawatts**, if that hypothetically happens. Just from the different sources of gas generation you mentioned—the different kinds of engines and turbines—combined, how many gigawatts could they unlock by the end of the decade?

</details>

**Dylan**: 我们正在追踪这些数据。仅燃气发电就有超过 **16家**不同的电力生产商。是的，联合循环涡轮机只有三家制造商，但我们正在追踪 **16家**不同的供应商，而且我们有他们所有的订单。结果发现，有数百吉瓦的订单流向了各种数据中心。到本世纪末，我们认为新增容量的大约一半将是**表后发电**。**表后发电**几乎总是比并网发电更昂贵，但并网发电有很多问题：许可证、互联队列等等。所以即使它更昂贵，人们也在进行**表后发电**。他们进行的**表后发电**范围很广。可以是往复式发动机、船用发动机或航空衍生产品。可以是联合循环，尽管联合循环不太适合**表后发电**。可以是 **Bloom Energy** 燃料电池，或者太阳能加电池。可以是任何这些东西。

<details>
<summary>Original English</summary>

**Dylan**: We're tracking this in our data. There are over **16** different manufacturers of power-generating things just from gas alone. Yes, there are only three turbine manufacturers for combined-cycle, but we're tracking **16** different vendors, and we have all of their orders. It turns out there are hundreds of gigawatts of orders to various data centers. As we get to the end of the decade, we think something like half of the capacity that's being added will be **behind the meter**. **Behind the meter** is almost always more expensive than grid-connected, but there are just a lot of problems with getting grid-connected: permits and interconnection queues and all this sort of stuff. So even though it's more expensive, people are doing **behind the meter**. What they're doing **behind the meter** ranges widely. It could be reciprocating engines, ship engines, or aeroderivatives. It could be combined-cycle, although combined-cycle is not that great for **behind the meter**. It could be **Bloom Energy** fuel cells, or solar plus battery. It could be any of these things.

</details>

**Dwarkesh**: 你是说这些单独的任何一个都能提供几十吉瓦的电力吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: And you're saying any of these individually could do tens of gigawatts?

</details>

**Dylan**: 这些单独的任何一个都能提供几十吉瓦的电力，作为一个整体，它们将提供数百吉瓦的电力。

<details>
<summary>Original English</summary>

**Dylan**: Any of these individually will do tens of gigawatts, and as a whole, they will do hundreds of gigawatts.

</details>

**Dwarkesh**: 好的。所以这本身就应该超过——

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay. So that alone should more than—

</details>

**Dylan**: 电工的工资可能会再次翻倍或三倍。将会有很多新人进入这个领域，很多人会赚钱，但我认为这并不是主要的瓶颈。现在在阿比林，**Crusoe** 为 **OpenAI** 建造的 **1.2吉瓦**数据中心，我认为有 **5000人**在那里工作，或者在高峰期是这样。如果你把它变成 **100吉瓦**——我相信随着时间的推移，效率会更高——那将需要 **40万人**来建造 **100吉瓦**。如果你想想美国的劳动力，以及有多少电工和建筑工人……我猜有 **80万**电工。我不知道他们是否都能以这种方式替代。有数百万建筑工人。但如果我们生活在一个每年增加 **200吉瓦**的世界里，我们最终会面临劳动力短缺吗，或者你认为这实际上不是一个真正的限制？

<details>
<summary>Original English</summary>

**Dylan**: Electrician wages will probably double or triple again. There are going to be a lot of new people entering that field, and a ton of people who make money, but I don't see that as the main bottleneck. Right now in Abilene, at the **1.2-gigawatt** data center that **Crusoe** is building for **OpenAI**, I think they have **5,000 people** working there, or at peak they did. If you turn that into **100 gigawatts**—and I'm sure things will get more efficient over time—that would be **400,000 people** it would take to build **100 gigawatts**. If you think about the US labor force, and how many electricians there are and how many construction workers there are… I guess there are **800,000** electricians. I don't know if they're all substitutable in this way. There are millions of construction workers. But if we're in a world where we're adding **200 gigawatts** a year, are we going to be crunched on labor eventually, or do you think that is actually not a real constraint?

</details>

**Dylan**: 劳动力是一个很大的限制。在这方面这是一个巨大的限制。人们必须接受培训。同样，我们可能会开始进口最高技能的劳动力。一个在欧洲从事拆除发电厂工作的高技能电工，现在来到美国建造数据中心的高压电力，这是有道理的。人形机器人或至少机器人技术可能会开始提供帮助，但减少人数的主要因素将是模块化和在亚洲工厂制造。不幸的是，对于美国来说，像韩国、东南亚以及在许多方面中国这样的地方，将越来越多地运送建成的数据中心部分，这些部分将被运入。今天你通常运送服务器或一个机架，然后你将其插入从不同地方运送来的不同部件。但现在你将把它运到工厂并集成整个东西。这可能是一个 **2兆瓦**的模块，这个模块将高压交流电转换为你提供给机架的直流电压，或者类似的东西。或者在冷却方面，你运送一个完全集成的单元，其中包含许多冷却子系统，因为水管工在这里也是一个很大的限制。此外，与其让人们为所有这些机架布线，你不如拿一个滑板，上面放一整排服务器，直接从工厂运来。今天，一个机架可能是 **120或140千瓦**，但随着我们进入下一代**英伟达 Kyber** 等，它几乎是 **1兆瓦**。此外，如果你做一整排，它将包含机架、网络、冷却和电源，全部集成在一起。现在当你进来时，你需要布线的就少得多了。网络光纤更少，电源连接更少，管道也更少。这可以大大减少数据中心工作人员的数量，所以我们建造它们的能力将大大提高。在此过程中，一些人会更快地转向新事物，一些人会更慢。**Crusoe** 和**谷歌**一直在谈论这种模块化，**Meta** 和许多其他公司也是如此。那些更快转向新事物的人可能会面临延迟，而那些较慢的人将面临劳动力问题。市场上总是会出现错位，因为这是一个非常复杂的供应链。归根结底，它仍然足够简单，我们能够在所需的时间尺度内通过资本主义和人类的智慧来解决它。

<details>
<summary>Original English</summary>

**Dylan**: Labor is a big constraint. It's a humongous constraint in this. People have to be trained. Likewise, we'll probably start importing the highest-skilled labor. It makes sense that a really high-skilled electrician in Europe who was working on destroying power plants now comes to America and is building high-voltage electricity moving across a data center. Humanoid robots or robotics at least might start to help, but the main factor for reducing the number of people is going to be modularizing things and making them in factories in Asia. Unfortunately for America, places like Korea, Southeast Asia, and in many ways China as well are going to ship more and more built-out sections of the data center and those will be shipped in. Today you currently ship servers or a rack in, and then you plug that into different pieces that you're shipping from different places. But now you'll ship it to a factory and integrate the entire thing. Maybe this is a **two-megawatt** block, and this block goes from high-voltage AC power to the DC voltage that you deliver to the rack, or something like this. Or with cooling, you ship a fully integrated unit that has a lot of the cooling subsystems already put together, because plumbers are also a big constraint here. Furthermore, instead of just a single rack where you have people wiring up all these racks with electricity, you take a skid and put an entire row of servers on it that is shipped directly from the factories. Today, a single rack may be **120 or 140 kilowatts**, but as we get to next-generation **Nvidia Kyber** and things like that, it's almost a **megawatt**. In addition, if you do an entire row, it'll have the rack, the networking, the cooling, and the power all integrated together. Now when you come in, you have much less to cable. There's less networking fiber, fewer power connections, and fewer plumbing things. This can drastically reduce the number of people working in data centers, so our capability to build them will be much larger. Along the way, some people will move faster to new things, and some will move slower. **Crusoe** and **Google** have been talking a lot about this modularization, as have companies like **Meta** and many others. The people who move faster to new things may face delays, while the people who are slower will face labor problems. There will always be dislocations in the market because this is a very complex supply chain. At the end of the day, it's still simple enough that we will be able to solve it through capitalism and human ingenuity on the timescales required.

</details>

### 太空数据中心与机器人算力

**Dwarkesh**: 谈到解决大问题，**Elon Musk** 对太空 **GPU** 非常看好。如果你说地球上的电力不是限制……我想他们有意义的另一个原因是，即使地球上会有足够的燃气轮机或其他什么，**Elon** 的下一个论点是，你无法获得在地球上建造数百吉瓦的许可证。你认同这个论点吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Speaking of big problems to solve, **Elon Musk** is very bullish on space **GPUs**. If you're right that power is not a constraint on Earth… I guess the other reason they would make sense is that even if there will be enough gas turbines or whatever on Earth, **Elon**'s next argument is that you can't get the permitting to build hundreds of gigawatts on Earth. Do you buy that argument?

</details>

**Dylan**: 从土地角度看，美国很大。数据中心实际上占用的空间不多，所以你可以解决这个问题。从许可证角度看，空气污染许可证是一个挑战，但**特朗普（Trump）**政府使其变得容易得多。你去德克萨斯州，可以跳过很多繁文缛节。**Elon** 在孟菲斯处理了很多复杂的事务，然后为 **Colossus 1** 和 **2** 在边境建造了一个发电厂。但归根结底，在德克萨斯州中部，你可以做更多的事情。

<details>
<summary>Original English</summary>

**Dylan**: Land-wise, America is big. Data centers don't actually take up that much space, so you can solve that. Permitting-wise, air pollution permits are a challenge, but the **Trump** administration made it much easier. You go to Texas, and you can skip a lot of this red tape. **Elon** had to deal with a lot of this complex stuff in Memphis, and then building a power plant across the border for **Colossus 1** and **2**. But at the end of the day, there's a lot more you can get away with in the middle of Texas.

</details>

**Dwarkesh**: 考虑到 **Elon** 住在德克萨斯州，他为什么不去德克萨斯州呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: Given that **Elon** lives in Texas, why didn't he just go to Texas?

</details>

**Dylan**: 我认为部分原因是他们暂时过度依赖电网电力。那只是他们认为他们需要更多的东西。

<details>
<summary>Original English</summary>

**Dylan**: I think it was partially that they over-indexed on grid power for a temporary period of time. That's just what they thought they needed more of.

</details>

**Dwarkesh**: 因为他们那里有一个连接到电网的铝精炼厂。

<details>
<summary>Original English</summary>

**Dwarkesh**: Because they had an aluminum refinery connected to the grid there.

</details>

**Dylan**: 实际上那是一个闲置的电器工厂。但我认为他们可能更侧重于电网电力、水资源和天然气资源。我认为他们购买那里时就知道天然气管道就在旁边，他们会去利用它。水资源也是如此。那是一系列不同的限制。那可能是一个更容易找到电工的地方。归根结底，我不太确定他们为什么选择那个地点。我敢打赌 **Elon** 如果能回到过去，会选择德克萨斯州的某个地方，因为他面临的监管挑战。最终，许可证是一个挑战，但美国是一个拥有 **50个**州的广阔地方，事情会办成的。有很多小司法管辖区，你可以根据承包商的需求，在三到十二个月的临时期间内，将所有需要的工人运送进去。你可以把他们安置在临时住所，并支付高额费用，因为劳动力相对于 **GPU** 和网络，以及它将产生的token的最终价值来说，非常便宜。所以有足够的空间来支付所有这些费用。此外，人们现在也在多样化。澳大利亚、马来西亚、印度尼西亚和印度都是数据中心建设速度快得多的地方。但目前，超过 **70%** 的AI数据中心仍在美国，而且这种趋势仍在继续。人们正在研究如何建造这些东西。最终，处理德克萨斯州、怀俄明州或新墨西哥州偏远地区的许可证和繁文缛节，可能比把东西送入太空容易得多。

<details>
<summary>Original English</summary>

**Dylan**: It was actually an idled appliance factory. But I think they may have indexed more to grid power, water access, and gas access. I think they bought that knowing the gas line was right there and they were going to tap it. Same with water. It was a whole host of different constraints. It was probably an area where electricians were easier to find. At the end of the day, I'm not exactly sure why they chose that site. I bet **Elon** would've chosen somewhere in Texas if he could've gone back because of the regulatory challenges he faced. Ultimately, permitting is a challenge, but America is a big place with **50** states, and things will get done. There are a lot of small jurisdictions where you can just transport in all the workers you need for a temporary period of three to twelve months, depending on the contractor. You can put them in temporary housing and pay out the butt, because labor is very cheap relative to the **GPUs** and the networking, and the end value of the tokens it's going to produce. So there is plenty of room to pay for all of these things. Also, people are also diversifying now. Australia, Malaysia, Indonesia, and India are all places where data centers are going up at a much faster pace. But currently, over **70%** of AI data centers are still in America, and that continues to be the trend. People are figuring out how to build these things. Ultimately, dealing with permitting and red tape in middle-of-nowhere Texas, Wyoming, or New Mexico is probably a hell of a lot easier than sending stuff into space.

</details>

**Dwarkesh**: 除了考虑到能源只占数据中心**总拥有成本**的一小部分后，经济论点变得不那么合理之外，你还有什么其他怀疑的原因？显然，太空中的电力基本上是免费的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Other than the economic argument making less sense once you consider that energy is a small fraction of the total cost of ownership of a data center, what are the other reasons you're skeptical? Obviously, power is basically free in space.

</details>

**Dylan**: 是的，这就是这样做的原因。

<details>
<summary>Original English</summary>

**Dylan**: That's the reason to do it.

</details>

**Dwarkesh**: 是的，这就是这样做的原因。

<details>
<summary>Original English</summary>

**Dwarkesh**: Yeah, that's the reason to do it.

</details>

**Dylan**: 但还有所有其他反驳论点。即使地球上的电力成本翻倍，它仍然只占 **GPU** **总拥有成本**的一小部分。主要挑战是……我们有 **ClusterMAX**，它对所有**新云**公司进行评级。我们测试了 **40多家**云公司，包括超大规模公司和**新云**公司。除了软件之外，这些云公司最大的区别在于它们部署和管理故障的能力。**GPU** 的可靠性极差。即使在今天，大约 **15%** 的 **Blackwell** 部署后都必须进行 **RMA**（退货授权）。你必须把它们取出来。有时你只需要重新插上，但有时你必须把它们取出来，然后运回**英伟达**或他们的合作伙伴进行 **RMA** 等。

<details>
<summary>Original English</summary>

**Dylan**: But there are all the other counterarguments. Even if power costs double on Earth, it's still a fraction of the total cost of the **GPU**. The main challenge is… We have **ClusterMAX**, which rates all the **neoclouds**. We test over **40** cloud companies, including the hyperscalers and **neoclouds**. Outside of software, what differentiates these clouds the most is their ability to deploy and manage failure. **GPUs** are horrendously unreliable. Even today, around **15%** of **Blackwells** that get deployed have to be **RMA**'d. You have to take them out. Sometimes you just have to plug them back in, but sometimes you have to take them out and ship them back to **Nvidia** or their partners who do the **RMAs** and such.

</details>

**Dwarkesh**: 你怎么看待 **Elon** 的论点，即在初始阶段之后，它们实际上不会失败那么多？

<details>
<summary>Original English</summary>

**Dwarkesh**: What do you make of **Elon**'s argument that after an initial phase, they actually don't fail that much?

</details>

**Dylan**: 当然，但现在你已经完成了这些，测试了所有，拆解了它们，把它们放在宇宙飞船上，发射到太空，然后再次上线。这需要几个月的时间。如果你的论点是 **GPU** 的有用寿命是五年，而这需要额外六个月，那就是你集群有用寿命的 **10%**。因为我们受到产能限制，所以这些算力在最初的六个月里理论上最有价值。我们现在比未来更受限制。这些算力可以在未来为更好的模型做出贡献，或者今天产生收入，你可以用它来筹集更多资金。所有这些都使得现在成为最重要的时刻，但你可能会将你的算力部署推迟六个月。这些云提供商的区别在于……我们看到一些云提供商在地球上部署 **GPU** 需要六个月。我们看到一些云提供商所需时间远少于六个月。所以问题是，太空数据中心如何融入其中？我看不出你如何在地球上测试所有这些，拆解它们，然后运到太空，而所需时间不会比仅仅把它们留在你测试它们的设施里长得多。

<details>
<summary>Original English</summary>

**Dylan**: Sure, but now you've done this, tested them all, deconstructed them, put them on a spaceship, launched them into space, and then put them online again. That takes months. If your argument is that a **GPU** has a useful life of five years, and this takes six additional months, that is **10%** of your cluster's useful life. Because we're so capacity-constrained, that compute is theoretically most valuable in the first six months you have it. We're more constrained now than we will be in the future. That compute can contribute to a better model in the future, or generate revenue today that you can use to raise more money. All these things make now the most important moment, but you've potentially delayed your compute deployment by six months. What separates these cloud providers is… We see some clouds taking six months to deploy **GPUs** right here on Earth. We see clouds that take a lot less than six months. So the question is, where does space get in there? I don't see how you could test them all on Earth, deconstruct them, and ship them to space without it taking significantly longer than just leaving them in the facility where you tested them.

</details>

**Dwarkesh**: 我想问的问题是关于太空通信的拓扑结构。现在，**星链（Starlink）**卫星以每秒 **100吉比特**的速度相互通信。你可以想象，通过为此优化的光学卫星间激光链路，这个速度会高得多。

<details>
<summary>Original English</summary>

**Dwarkesh**: The question I wanted to ask is about the topology of space communication. Right now, **Starlink** satellites talk to each other at **100 gigabits per second**. You could imagine that being much higher with optical intersatellite laser links optimized for this.

</details>

**Dylan**: 这实际上非常接近 **InfiniBand** 的带宽，即每秒 **400吉字节**。但这只是每个 **GPU** 的带宽，而不是每个机架的。所以要乘以 **72**。而且，那是 **Hopper**。当你转向 **Blackwell** 和 **Rubin** 时，这个数字会再次翻倍，再翻倍。但是每个……在推理过程中，不同的扩展单元（scale-up）是否仍然协同工作，还是推理只是在单个扩展单元内批量进行？

<details>
<summary>Original English</summary>

**Dylan**: That actually ends up being quite close to **InfiniBand** bandwidth, which is **400 gigabytes a second**. But that's per **GPU**, not per rack. So multiply that by **72**. Also, that was **Hopper**. When you go to **Blackwell** and **Rubin**, that **2x**'s and **2x**'s again. But how much compute is happening per… During inference, are the different **scale-ups** still working together, or is inference just happening as a batch within a single **scale-up**?

</details>

**Dylan**: 很多模型都适合在一个**扩展域（scale-up domain）**内，但很多时候你会将它们分割到多个**扩展域**。随着模型变得越来越稀疏，这是普遍趋势，你希望每个 **GPU** 只ping几个专家。如果今天领先的模型有数百甚至数千个专家，那么即使我们未来继续发展，你也会希望在数百或数千个芯片上运行。所以你最终会遇到需要将所有这些卫星连接起来进行通信的问题。那会很困难。如果有一个世界，你可以在单个**扩展域**上对一个批次进行推理，那么这也许更合理。但如果不是，那就是另一回事了。将这些芯片连接在一起是一个问题，你不能让卫星无限大。制造一个非常大的卫星有很多物理挑战。这就是为什么你需要卫星之间的互连。这些互连更昂贵。在一个集群中，**15-20%** 的成本是网络。突然之间，你使用的是太空激光，而不是以数百万计生产的简单激光和可插拔收发器。而且这些东西也非常不可靠，顺便说一句，比 **GPU** 更不可靠。在一个集群的生命周期中，你必须不断地拔插和清洁它们。你必须仅仅因为随机原因就拔插它们。这些东西就是没有那么可靠。所以你也有这个问题。你有一个更昂贵、更复杂的太空激光用于通信，而不是这种以超高产量生产的可插拔光收发器。

<details>
<summary>Original English</summary>

**Dylan**: A lot of models fit within one **scale-up domain**, but many times you split them across multiple **scale-up domains**. As models become more and more sparse, which is the general trend, you want to ping just a couple of experts per **GPU**. If leading models today have hundreds, if not a thousand, of experts, then you'd want to run this across hundreds or thousands of chips, even as we advance into the future. So then you end up with the problem of needing to connect all these satellites together for communications as well. That would be tough. If there's a world where you could do inference for a batch on a single **scale-up**, then maybe it's more plausible. But if not, it's a different story. Networking these chips together is a problem, and you can't just make the satellite infinitely large. There are a lot of physics challenges to making a satellite really big. That's why you need these interconnects between the satellites. Those interconnects are more expensive. In a cluster, **15-20%** of the cost is networking. All of a sudden, you're using space lasers instead of simple lasers that are manufactured in volumes of millions with pluggable transceivers. And those things are very unreliable as well, more unreliable than the **GPUs** by the way. Across the life of a cluster, you have to unplug and clean them all the time. You have to unplug and replug them just for random reasons. These things are just not as reliable. So you've got that problem as well. You've got a more expensive, complicated space laser to communicate instead of this pluggable optical transceiver that's been produced in super high volume.

</details>

**Dwarkesh**: 那么总而言之，这对太空数据中心意味着什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: So all in all, what does that imply for space data centers?

</details>

**Dylan**: 太空数据中心实际上不受其能源优势的限制。它们受限于同样的竞争资源。到本世纪末，我们每年只能制造 **200吉瓦**的芯片。我们将如何获得这些产能？这与是在陆地还是在太空无关。这真的不重要，因为你可以建造那种电力。人类的能力和容量可以达到每年在全球增加 **1太瓦**各种类型电力的时期。在某个时候，我们确实会跨越太空数据中心变得有意义的鸿沟，但这不会是这个十年。那将是更远的未来，一旦能源限制真正成为一个大瓶颈，土地许可成为一个更大的瓶颈，因为它占据了经济的更多部分。最重要的是，一旦芯片不再是瓶颈。现在，芯片是最大的瓶颈。你希望它们一制造出来就能立即部署并用于AI。人们正在做很多事情来更快地提高速度。他们正在模块化数据中心，甚至模块化机架，你把芯片放进数据中心，但只有芯片，其他所有东西都已经布线并准备就绪。人们正在做这样的事情来减少时间，而这些事情在太空中是无法做到的。归根结底，在一个芯片受限的世界里，最重要的是尽快让这些芯片产生token。也许到2035年，半导体行业、**ASML**、**Zeiss** 以及像**泛林集团（Lam Research）**和**应用材料（Applied Materials）**等供应商以及其他晶圆厂制造商会迎头赶上，一旦钟摆摆动，我们能够制造足够的芯片。那时我们将优化每一个旋钮，优化 **10-15%** 的能源成本才有意义。随着我们转向**专用集成电路（ASIC）**，如果**英伟达**的利润率不是 **+70%**，也许能源成本会占集群的 **30%**。这些是需要优化的事情。但 **Elon** 不是通过获得 **20%** 的收益来取胜的。他从不那样取胜。**Elon** 在他全力以赴，获得 **10倍**收益时才能取胜。这就是 **SpaceX** 的宗旨。这就是**特斯拉（Tesla）**的宗旨。他所有的成功都与此有关，而不是追逐 **20%** 的收益。我认为太空数据中心最终会带来 **10倍**的收益，因为地球资源变得越来越有争议，但这不会是这个十年。

<details>
<summary>Original English</summary>

**Dylan**: Space data centers effectively are not limited by their energy advantage. They are limited by the same contended resource. We can only make **two hundred gigawatts** of chips a year by the end of the decade. What are we going to do to get that capacity? It doesn't matter if it's on land or in space. It doesn’t really matter, because you can build that power. Human capabilities and capacity could get to the period where we're adding a **terawatt** a year globally of various types of power. At some point, we do cross the chasm where space data centers make sense, but it's not this decade. It is much further out, once energy constraints actually become a big bottleneck and land permitting becomes a much bigger bottleneck as it subsumes more of the economy. And crucially, once chips are no longer the bottleneck. Right now, chips are the biggest bottleneck. You want them deployed and working on AI the moment they're manufactured. There are a lot of things people are doing to increase that speed faster and faster. They’re modularizing data centers, or even modularizing racks where you put the chip in at the data center, but only the chip and everything else is already wired up and ready to go. There are things like this people are doing to decrease that time that you cannot do in space. At the end of the day, all that matters in a chip-constrained world is getting these chips producing tokens ASAP. Maybe by 2035, the semiconductor industry, **ASML**, **Zeiss**, and suppliers like **Lam Research** and **Applied Materials** and other fab manufacturers will catch up once the pendulum swings and we are able to make enough chips. Then we will be optimizing every dial and it makes sense to optimize the **10-15%** of energy costs. As we move to **ASICs** potentially, and if **Nvidia**'s margins aren't **+70%**, maybe that energy cost becomes **30%** of the cluster. These are the things to optimize. But **Elon** doesn't win by doing **20%** gains. He never wins that way. **Elon** wins when he swings for the fences and does **10X** gains. That's what **SpaceX** is about. That's what **Tesla** is about. All of his success has been about that, not chasing the **20%**. I think space data centers will eventually be a **10X** gain as Earth's resources get more and more contentious, but that's not this decade.

</details>

**Dylan**: 只是为了提供一些关于地球上土地面积的直观感受……显然，对于芯片本身，特别是如果你进入一个机架拥有兆瓦级算力的世界——

<details>
<summary>Original English</summary>

**Dylan**: Just to drive some intuition about how much land there is on Earth… Obviously, for the chips themselves, especially if you move to a world where you have racks that have megawatts—

</details>

**Dylan**: 还有一件事。如果制造是限制，现在AI芯片大约是每平方毫米 **1瓦**。一个简单的改进方法是将其提高到每平方毫米 **2瓦**。你可能无法获得 **2倍**的性能，可能只获得 **20%** 更多的性能，但这需要更奇特的冷却。它需要更复杂的冷板和复杂的液体冷却，甚至可能是浸入式冷却。在太空中，每毫米更高的瓦数非常困难，而在地球上，这些都是已解决的问题。其中一项可以让你获得更多的token，也许每片制造的晶圆多 **20%** 的token，这是一个巨大的胜利。

<details>
<summary>Original English</summary>

**Dylan**: That's the other thing. If manufacturing is the constraint, right now it's roughly **one watt per square millimeter** for AI chips. One easy way to improve that is to pump it to **two watts per square millimeter**. You may not get **2x** the performance, you may only get **20%** more performance, and that requires much more exotic cooling. It requires more complicated cold plates and complex liquid cooling, or maybe even things like immersion cooling. In space, higher watts per millimeter is very difficult, whereas on Earth, these are solved problems. One of these things enables you to get a lot more tokens, maybe **20%** more tokens per wafer that's manufactured, and that's a humongous win.

</details>

**Dwarkesh**: 每平方毫米，你是说芯片面积吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Square millimeter, you mean of die area?

</details>

**Dylan**: 是的，芯片面积。

<details>
<summary>Original English</summary>

**Dylan**: Yeah, of die area.

</details>

**Dwarkesh**: 对太空来说会更好，因为每毫米瓦数越高意味着芯片运行温度越高。我猜这是计算机芯片工程的问题，但根据**斯特藩-玻尔兹曼定律（Stefan-Boltzmann law）**，它的冷却能力与四次方成正比。如果你能运行一个非常热的芯片，它允许很多——

<details>
<summary>Original English</summary>

**Dwarkesh**: It would be better for space because more watts per millimeter means the chip runs hotter. I guess this is a question of computer chip engineering, but it cools to the fourth power by the **Stefan-Boltzmann law**. If you can run a very hot chip, it allows a lot of—

</details>

**Dylan**: 不，你不能让它运行得更热。你只能让它更密集。问题在于，将热量从那个密集区域散发出去意味着你必须从标准的空气和液体冷却转向更奇特的液体冷却形式，甚至浸入式冷却，才能达到更高的功率密度。这在太空中比在地球上更困难。

<details>
<summary>Original English</summary>

**Dylan**: No, you can't run it hotter. You can only run it denser. The problem is that getting the heat out of that dense area means you have to move away from standard air and liquid cooling to more exotic forms of liquid cooling, or even immersion, to get to higher power densities. That's more difficult in space than it is on Earth.

</details>

### 芯片互联拓扑与模型参数扩展

**Dwarkesh**: 也许现在值得解释一下**扩展单元（scale-up）**到底是什么，以及**英伟达**、**Trainium** 和 **TPU** 的情况是怎样的。我之前提到芯片内部的通信超快。同一机架内芯片之间的通信很快，但没那么快。大约是太字节的量级。非常远的通信大约是数百吉字节的量级。随着距离的增加，也许跨越整个国家，量级大约是吉字节。一个**扩展域**是这种紧密的域，其中芯片以每秒太字节的量级进行通信。对于**英伟达**来说，以前这意味着一个 **H100** 服务器有 **8个GPU**，这 **8个GPU** 可以以每秒太字节的速度相互通信。对于 **Blackwell NVL72**，他们实现了机架规模的**扩展单元**。这意味着机架中所有 **72个GPU** 都可以以每秒太字节的速度相互连接。速度代代翻倍，但最重要的创新是从 **8个