---
author: Bloomberg Podcasts
date: '2026-06-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=BrpadR5KuMo
speaker: Bloomberg Podcasts
tags:
  - ai-inference
  - data-center
  - compute-infrastructure
  - cloud-computing
title: OddLots播客探讨AI推理成本激增与CoreWeave算力基础设施瓶颈
summary: OddLots探讨企业AI推理与算力支出激增现象，Uber等公司面临预算压力。CoreWeave联合创始人指出，当前算力扩张瓶颈在于带电毛坯房数据中心、电力、变压器及熟练电工等物理供应链交付，而非芯片获取或融资。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Joe Weisenthal
  - Tracy Alloway
  - Brandon McBee
companies_orgs:
  - CoreWeave
  - Nvidia
  - Bloomberg
products_models: []
media_books:
  - OddLots
status: evergreen
---
<!-- chunk 1/6 -->

彭博音频工作室出品：播客、电台与新闻。

<details><summary>Original English</summary>
Bloomberg Audio Studios podcasts, radio, news.
</details>

>> 大家好，欢迎收听新一期 OddLots 播客。我是 Joe Weisenthal。

<details><summary>Original English</summary>
>> Hello and welcome to another episode of the OddLots podcast. I'm Joe Weisenthal
</details>

>> 我是 Tracy Alloway。Tracy，我正在设想这样一个未来：

<details><summary>Original English</summary>
>> and I'm Tracy Aloway. Tracy, I'm envisioning this future
</details>

>> 比如我们可能得一个月做一次类似于 AI 推理市场现状的节目，你知道吧，就像事情变化得太快了，无论是模型在用什么，还是它们被用来做什么等等，都有极大的变化。就像我们偶尔会定期做一期股票市场节目之类的，我们就会来做一期“好吧，我们现在在 AI 推理趋势中看到了什么”，因为感觉只要我们刚做完一期节目，几周后可能就过时了。

<details><summary>Original English</summary>
>> where like we have to do a uh a state of the sort of AI inference market episode like once a month, you know, like where it's like things are moving so rapidly and there's so much change either in terms of what models are using or what they're being used for, etc. that in the same way we would do like you know the occasional regular stock market episode or whatever we would just do okay what are we seeing right now in AI inference trends because it just feels like the moment we do an episode a few weeks later it may be out of date
</details>

>> 我们干脆硬着头皮每周做一期算了，把 Lots 更多地转变成关于算力的市场动态更新。

<details><summary>Original English</summary>
>> we should just bite the bullet and do a weekly episode transform lots more into a market update on compute
</details>

>> 我们可以做推理……推……额，我不知道，我们得再切磋推敲一下。

<details><summary>Original English</summary>
>> we could do inference inf uh I don't know we'll have to workshop this
</details>

>> 推理，不行。

<details><summary>Original English</summary>
>> inference no
</details>

>> 不行，我们得……嗯，不过无论如何，这期是关于大量推理。

<details><summary>Original English</summary>
>> no we'd have to um but anyway this is lots inference.
</details>

### AI 算力与推理成本的激增

>> 大量的推理。这可谓是当下的焦点话题，而且我们知道，一两年前每个人都还在四处浅尝辄止，进行各种尝试，用 AI 比如“哦，帮我写一首关于这个的诗”之类的。AI 的那个阶段早已过去，我们清楚企业尤其在算力上投入了巨资。以至于全球各地的首席财务官（CFO）都对他们的算力预算感到震惊。甚至有头条新闻报道，比如 Uber 规定“每位员工每月在 token 上的花费最多 1500 美元，不要超额”。所以，这是一个变化极其迅速的领域。

<details><summary>Original English</summary>
>> Lots of inference. This is like the story of the moment and we know that you know a couple years ago everyone was sort of dabbling around with various things and experimenting and using AI like oh like write a poem for me about this etc. That phase of AI is long over and we know that companies specifically are spending a ton on compute. So much so that CFOs around the world are getting sticker shock about their compute budgets. And there was even a headline of like Uber saying like, okay, like $1,500 of max per employee, like don't spend more than that in a month on tokens. So like this is a very fastmoving area.
</details>

>> 是的。随着更多人去尝试并在上面花钱，你开始看到关于企业在 AI 上面临清算的头条新闻。你提到的那个关于 Uber 的头条，Uber 显然在四个月内基本上就烧光了其整个 2026 年的 AI 预算。而且更重要的是，首席运营官（COO）实际上在质问这到底值不值得，比如他们是否因此获得了生产力提升等等。我看到的另一条非常搞笑的头条新闻，援引了一位未具名消息人士，来自 Axios，所以你懂的。

<details><summary>Original English</summary>
>> Yeah. You're starting to get headlines about, I guess, a corporate corporate reckoning with AI as more people experiment and spend money on it. The Uber headline that you mentioned, apparently Uber burned through its entire 2026 AI budget in four months basically. And like what's more important is the COO was actually asking whether or not that was worth it, like whether they saw productivity gains or whatever as a result of that. The other very amusing headline that I saw and it was citing an unnamed source. It's from Axio, so you know.
</details>

>> 哦，是的。

<details><summary>Original English</summary>
>> Oh, yeah.
</details>

>> 不能完全确定是真的，但据报道是个很棒的头条。

<details><summary>Original English</summary>
>> Not entirely sure it's true, but reportedly a great headline.
</details>

>> 确实是个很棒的头条。一位 AI 顾问告诉 Axios，他们的一位客户在未设置使用限制的情况下，最近在单个月内就花费了 5 亿美元。

<details><summary>Original English</summary>
>> It was a great headline. An AI consultant told Axios that one of their clients recently spent half a billion dollars in a single month after failing to put usage limits on.
</details>

>> 没错，因为所有人都在用。就像是，“哦，我只是有个简单的问题。我想查一下我们嘉宾的头衔，我就要用最先进的模型来查”等等。我有一个理论——我们稍后会和嘉宾深入探讨这一点，而且我们之前也和高盛的 Marco Argenti 讨论过——我预测的事情之一是，显然企业会继续越来越多地使用它，这是我的推测，但可能会有大量投资流向类似最优化模型路由的领域，因为有些模型每次查询的成本只有前沿模型的百分之一，很多人可能不知道什么才是有效率的前沿模型使用方式，所以将查询实际路由到最高效的模型上。我有种感觉，我们会在这个特定领域看到大量投资。

<details><summary>Original English</summary>
>> Yeah, it's because it's everyone. It's like, oh, I just have a simple question. I want to look up our guest's title. I'm gonna use the most advanced model to do that etc. I have a theory and we will get into this with our guests that one of the things that will and we've talked about this with Goldman's Marco Argenti but one of the things I predict is that companies are like clearly you know they're going to keep using it more and more would be my guess but there will probably be a lot of investment made in sort of like optimal model routing because some models are like a hundth per query of what a frontier model is probably a lot of people don't know like what is the sort of like efficient frontier model usage and So actually routing the query to the sort of most uh efficient model. I have a feeling we're going to see a lot of investment in that area specifically.
</details>

>> 嗯，而且随着模型向前发展，它们整体上是否会变得更便宜本身也是个问题，对吧？我们已经看到一些，我想英伟达推出了新的系统或芯片之类的，据说是为了减少 token 使用量。我们也可以聊聊那个。而且你知道，我们最近和 Hudson River Trading 的 Ian Dunning 做过那期现场节目，他在节目里讲了很多有意思的事情，但他说的一点是：

<details><summary>Original English</summary>
>> Well, there's also just the question of whether or not the models get cheaper overall as they advance, right? And we have seen some I think Nvidia has a new system or chip out or something that is supposed to reduce token usage. We can get into that as well. And you know, we did that live episode recently with Ian Dunning of Hudson River Trading, and he said a lot of interesting things in that, but one of the things he said is that
</details>

>> 稀缺性越来越偏向纯粹的地产要素。找到合适的地方插上 GPU，至少从他的角度来看，现在的挑战就算不比获取 GPU 本身更大，也至少是不相上下了。所以说……

<details><summary>Original English</summary>
>> the scarcity is increasingly like just the real estate component. Finding a suitable place to plug in your GPUs, at least from his perspective, right now is as much if not more so of a challenge than securing GPUs themselves. So like,
</details>

>> 这与三年前的情况截然不同。是的。

<details><summary>Original English</summary>
>> which is different to what it was like 3 years ago. Yeah.
</details>

>> 是的。所以，光是把它插在哪里就是个问题，我们知道外界还存在着各种反对数据中心的政治阻力。所以，是的，我们必须对这个市场做个摸底把脉。

<details><summary>Original English</summary>
>> Yeah. So, just like where you plug it in, we know there's all the like the anti-data center politics out there. So, it's like, yeah, we got to take the pulse of this market.
</details>

>> 好的。就把这期当作我们的推理更新节目吧。

<details><summary>Original English</summary>
>> All right. Consider this our inference update.
</details>

### 对话嘉宾：CoreWeave 的发展与算力需求

>> 是的。我很兴奋地告诉大家，我们确实请到了完美的嘉宾。我们上一次跟他交流真的感觉像是很久以前了。我想我们第一次联系这家公司时，他们手头一直有大量芯片，但我想我们第一次联系他们时，还在大家热衷于将英伟达芯片用于加密货币挖矿之类的时代。但我们现在进入了一个非常不同的时代，而这真正是当下的焦点公司之一，那就是 CoreWeave，所谓的“新一代云服务商”（Neoclouds）之一，为各种不同的 AI 工作负载提供训练和推理服务。我非常高兴地宣布，重返我们节目的嘉宾是 CoreWeave 的联合创始人兼首席开发官 Brandon McB[ee]。Brandon，非常感谢你来到 OddLots。

<details><summary>Original English</summary>
>> Yeah. Well, I'm really excited to say we really do have the perfect guest. Someone we spoke to like truly feels like eons ago. I think the first time we ever connected with this company, they've always had a lot of chips, but I think the first time we ever linked up with this company was still in the era where people were excited about Nvidia chips being used for like crypto mining and stuff like that. But we are now in this very different era and this is truly like one of the companies of the moment and that is of course Cororeweave, one of the so-called Neoclouds offering both training and inference services for all sorts of different AI workloads. I'm very excited to say back on the show we have Brandon McB Corweave's co-founder and chief development officer. So Brandon, thank you so much for uh coming on OddLots.
</details>

>> 感谢二位再次邀请我。嗯……刚才的介绍太棒了。我们期待今天深入探讨这些话题。

<details><summary>Original English</summary>
>> Appreciate being invited back guys. Um and that was a fantastic intro. We look forward to hitting these topics today.
</details>

>> 好的，这是我的问题。我们知道，在去年年底以及今年第一季度，大家都开始使用 Claude Code 之类的工具，显然整个 AI 需求迎来了一个关键的拐点，然后我们进入了第二季度，突然之间首席财务官们开始惊呼：“天哪，我们在推理上花了这么多钱，我们得把事情搞搞清楚。”坦白说，就在过去一个月左右的时间里，你有没有看到这种情况开始出现的迹象？这些依然渴望采纳 AI 的公司，是否正在试图加强控制，并可能放缓增长速度？这种情况已经发生了吗？

<details><summary>Original English</summary>
>> All right, here's my question. So we know that like at the tail end of last year and then in the first quarter of this year everyone started using cloud code and just there's clearly a key inflection moment for sort of like overall AI demand and then we get into Q2 and suddenly the CFO is oh my gosh we're spending this much on inference we got to like figure things out just straight up like in the last month whatever do Do you see any signs of that happening yet? Of these companies which are all like none still AI eager AI adopters trying to get a little bit of a handle and maybe slowing the grow the rate of the rate of growth. Is that happening yet?
</details>

>> 是的，我认为你会看到那些关于支出超预期的头条新闻等等。我认为我们的解读完全是立足于市场上存在的真实且根本的需求，对吧？其实我们真正在谈论的，是 AI 的消耗量有多大、用途有多广。而且我认为在 12、18、24 个月前，市场上确实存在一个疑问：AI 到底会有需求吗？大家一直在谈论的这些推理需求究竟在哪里？而且我认为你说得完全正确。大约在一月份，随着这批即将推出的下一代模型问世，所有人突然且异口同声地表示：“这就是我们需要的，这才是真正的产品突破。”但我觉得值得记住的是，归根结底，这一产品突破当时是针对有限的一群人，对吧？我们说的是编程专业人员、部分金融专业人员，但以如此庞大规模使用基础设施的其实是一个相对较小的群体。因此，我们认为接下来的发展走向是更广泛的企业端应用，可能不会出现那种把 token 用到极致（token maxing）的做法。我认为那种做法是不可持续的。

<details><summary>Original English</summary>
>> Yeah, I think you see headlines there that there are surprises of spend etc. I'd say our interpretation of it is entirely look at the like authentic and foundational demand that is out there, right? Like all we're really doing is talking about how much consumption there is of AI and use for it. And I think that that was a real question in the market 12, 18, 24 months ago is will there be demand for AI? Where is this inference demand that everyone's been talking about? And I think you're absolutely correct. January or so with this kind of like next group of models that were coming out, everyone all of a sudden and all at once said, "This is what we've needed like this is the real product breakthrough." But I think it's worth keeping in mind that product breakthrough was like for a limited set of people at the end of the day, right? We're we're talking like coding professionals, some finance professionals, but it's a relatively small group of people that are using infrastructure at this enormous scale. And so where we see this moving towards next is broader enterprise use likely not seeing this whole that token maxing approach. And I think that that is unsustainable.
</details>

>> 但我们是否看到了其他行业的采纳，以及这种情况如何继续扩散开来？那是绝对的。我的意思是，在我们的业务端，我认为目前我们有 10 家金额超过 10 亿美元的客户，我们在金融服务领域的客户储备订单目前也达到了数百亿美元的规模。

<details><summary>Original English</summary>
But do we see adoption in other sectors and how this can continue to spread out? Absolutely. I mean, you know, on our end, I think we have 10 over1 billion dollar clients at this point and our financial services client backlog is in the tens of billions of dollars
</details>

>> 所以，我们现在谈论的是 AI 实验室之外、超大规模云厂商（hyperscalers）之外的领域。而且……

<details><summary>Original English</summary>
>> at this point. And so, we're now talking about things outside of AI labs, outside of hyperscalers. And
</details>

>> 听着，正如二位所知，我们为全球排名前十的 AI 实验室中的九家提供支持——如果你把中国以及那边发生的一切排除在外的话。我们对人们在做什么有非常清晰的洞察，而且我们目前没有看到他们在推理方面的投入有任何收缩。如果说有什么变化的话，那就是对获取市场上运行人工智能的最佳技术方案的需求依然强劲不减，而这正是 CoreWeave 在市场上提供的解决方案。

<details><summary>Original English</summary>
>> look, as you guys know, we support nine of the top 10 uh AI labs on the planet. if you you know exclude China and everything that's going on over there like we have a lot of visibility into what people are doing and we're not seeing any pullback on on what they're doing on on inference today. If anything, it just remains this unrelenting demand for access to the best technology solution in the market for running artificial intelligence and that's coreweave solution in the market.
</details>

>> 等等，多讲讲现在的客户构成与三年前的对比吧。你们有超大规模云厂商，有初创公司，还有各种各样的企业。这种构成随着时间的推移发生了怎样的变化？是的，它极大地转向了一个更加多元化的客户群体，对吧？我们在 IPO 时曾因此受到很多抨击，对吧？人们指责说……

<details><summary>Original English</summary>
>> Wait, say more about the customer mix now versus say three years ago. So you have hyperscalers, you've got startups, you've got various businesses. How has that I guess um composition shifted over time? Yeah, it it's it's shifted enormously towards a more diverse customer base, right? We got a lot of flack for this in our IPO, right? Like people were uh noting that
</details>

<!-- chunk 2/6 -->

### 客户多元化与模型路由

我们曾经只有少数几个大客户，那时候我们的客户基本就只是超大规模云厂商（hyperscalers）外加一两家 AI 实验室。而我认为，我们在推动多元化方面取得了巨大的进展。所以我想说，目前主要分为三大类，对吧？我们拥有持续与我们共同成长的超大规模云厂商客户；我们有 AI 实验室客户——正如我所说，全球前十大 AI 实验室中有九家选择 Core Reef；然后我们还有这批企业客户群体。而企业群体正如你所料，并不会占据那么多新闻头条，对吧？并没有签下那些数十亿美元的巨额合同。但我认为单在第四季度，我们客户群新增的标志性客户（logos）数量就比以往任何一个季度翻了一倍，

<details><summary>Original English</summary>
we only had a handful of large clients um that our clients were like just the hyperscalers and AI lab or two and I think that we have made tremendous progress in driving diversification. So I'd say it sits probably across three buckets today, right? We we have hyperscaler clients who continue to grow with us. We have AI lab clients. Um as I said, nine of the top 10 AI labs on the planet choose Core Reef. And then we have this enterprise base. And the enterprise base just doesn't grab as many headlines as you would expect, right? There's not these massive multi-billion dollar contracts that are being signed. But I think in Q4 alone, we added twice as many logos to our client base as we had ever done versus any previous court,
</details>

>> 对吧？而正是那个企业客户群体正在如此大幅地增长。你们在开场介绍中触及了一个我认为非常值得重视的观点，那就是模型路由（model routing）的概念，以及并非每个人都只需要最新模型这一想法，也就是存在不同类型的模型。我可以针对不同的使用场景，这也是我们讨论了一段时间的事情，对吧？在涉及基础设施方面也是如此，对吧？因为并非所有任务都需要最新的模型。相应地，你也不需要用最新的一批基础设施去支持市面上的每一次推理或训练查询。

<details><summary>Original English</summary>
>> right? And that that enterprise base is the one that's growing so much. And there was a point you guys hit on in the intro that I think is really worth acknowledging and it was this concept of model routing and the idea that like not everyone needs just the latest model that it's different types of models. I can hit different use cases and this is something we've been talking about for a while, right? As it relates to the infrastructure side of things as well, right? Because you don't need that latest model for everything. And accordingly, you don't need the latest piece of infrastructure to support every single inference or training query that's out there.
</details>

>> 你完全可以把这构想成一个不同规模工作负载对应不同规格 GPU 的矩阵。突然之间，这就告诉你，天哪，比如 H100 可以使用六年、七年、八年。A100 的使用寿命还会更长。这彻底改变了围绕基础设施折旧年限的整个讨论，

<details><summary>Original English</summary>
>> You can kind of conceptualize this matrix of different sizes of workloads relative to different sizes of GPUs. And all of a sudden that tells you my god like H100s could last six, seven, eight years. A100s are going to last longer. And it totally changes the entire conversation around depreciable life of infrastructure
</details>

>> 因为那是 2025 年期间非常热门的话题。人们当时常说：“哦，这批设备只能用两年。之后价值就归零了。”而像那样的苗头我们从没见过，因为正如你们准确指出的观点，用户将需要找到针对其提示词使用合适模型的方法，正如你所指出的，那将通过模型路由来解决。这正好进一步支撑了基础设施将被使用更久这一概念，而且我们在自己的资产组合中每天都能看到这种情况，一直延伸回溯到 A100。我只是想针对客户群体的拓展提一个具体的问题，比如你提到了金融服务客户。当你把比如一家金融服务客户说成是一家有别于某家主流 AI 实验室的独立客户时，那是否意味着——好吧，按照你的说法——打个比方，我只是随口举例，我不知道是否存在这些合作关系，假设花旗集团（Citigroup）与 Anthropic 签有企业授权协议，这算是将 Anthropic 视为客户，还是将花旗视为客户？而当你谈到这种拓展时，本质上是不是有更多类型的实体正在构建某种模型——不一定严格是 LLM，而是某种他们希望从中运行推理的特定内部自研模型？

<details><summary>Original English</summary>
>> as that was a really popular topic during 2025. People were saying like, "Oh, this stuff will last two years. It's worth zero afterwards." And like we've never seen any semblance of that because of the point you guys are accurately making which is users are going to need to find the way to use the appropriate model for their props and that'll be solved by model rabbit to your point. that just further enables this concept that infrastructure is going to be used longer and we see that every day in our portfolio extending all the way back to A100s. I just want to ask a specific question about the broadening out of the customer base and you mentioned for example financial services clients when you talk about say a financial services client as being distinct client from one of the major AI labs does that mean well you're saying so it's like I'm just making it up let's just say I don't know if these relationships exist let's say a city group has an enterprise license with an anthropic does that count as anthropic as a customer or city as a customer. And when you talk about this broadening out, are there essentially more types of entities who are building some type of model, not necessarily an LLM per se, but some type of internal house specific model from which they want to run inference.
</details>

>> 问得非常好。在你提出的情境下，Anthropic 会是我们的客户。好，明白。所以我想强调的是——我想更正一下我之前说的数字——我们的金融服务客户（这是直接面向这些金融机构的），他们的在手未完成订单（backlog）正逼近 100 亿。好，

<details><summary>Original English</summary>
>> It's a great question. The scenario you presented anthropic would be our client. Okay, there. Got it. So what I'm highlighting I want to correct the number I said earlier our financial service clients and this is direct to those financial services they're approaching 10 billion in backlog okay
</details>

>> 所以这将是——你知道，这里的一个很好的例子，也是我们最近建立合作的一个例子，就是和简街（Jane Street）。好，

<details><summary>Original English</summary>
>> so this would be you know a good example of this and that's something we made recently is with Jane Street okay
</details>

>> 对，那不是简街通过 OpenAI 或 Anthropic 间接找到我们，

<details><summary>Original English</summary>
>> right that's not Jane Street coming through open AI or anthropic to get to us
</details>

>> 而是简街直接找我们，并使用我们的平台，而且那是——

<details><summary>Original English</summary>
>> that is Jane Street coming directly to us and using our platform and that is
</details>

>> 为了他们正在构建的模型，所以是简街自己的——

<details><summary>Original English</summary>
>> for a model that they're building so it's a Jane street
</details>

>> 或者是推理，对吧？是训练推理。我并不是说抛开训练不谈，但这会是针对属于简街自己某种模型的推理，而不是简街与某家主要实验室签订合同并建立的企业合作关系。

<details><summary>Original English</summary>
>> or entrance right it's training entrance I'm not saying setting aside training but it would be inference of a model that it's Jane Street's model of something rather than Jane Street's contract and enterprise relationship with one of the major labs.
</details>

### 企业工作负载与 AI 实验室合同演变

>> 归根结底，我们不知道这些实体具体在运行什么工作负载。好。特别是对于像简街这样的实体。我想象那是高度机密的。是的。嗯，但我想说的重点更多在于，这不是他们通过 AI 实验室找上我们。他们是在我们平台上直接对接并管理基础设施。在我们拓展这个多元化客户群体的过程中，这是非常重要的区别。嗯，我再次认为，在过去一年里我们在落实这一点上做得非常出色。

<details><summary>Original English</summary>
>> At the end of the day we don't know what exact workloads okay these entities are running. Um especially for entities like Jane Street. I would imagine that's highly secretive. Yeah. Um but the point I would say is more that this is not them coming through an AI lab to us. They are interfacing with and managing the infrastructure directly on our platform. And that's a really important distinction as we grow this diversified client base. Um and I again I think that we've just done a wonderful job of um executing on that over the past year.
</details>

正如你所谈到的，包括在财报发布中所提到的，并且正如你仅从这些庞大的 Token 预算就能看出的那样，推理需求正在蓬勃增长，但模型训练依然很重要。不过除了模型训练之外——所以假设，如果有一个饼图，推理所占的部分正在变大，但我推测训练也在增长。但我很好奇，从比如 AI 实验室的角度来看，当他们考虑增长时，相比于投资比如更好的测试基准框架（harnesses），从大力投入推动纯模型前沿、拥有绝对顶尖的 SOTA 模型之间，是否存在某种微妙的转变？因为我们目前对 AI 感到兴奋并且全都在热议的一个重要原因，实际上是 2025 年最后一个季度围绕 Cloud Code 引发的轰动，大家觉得“哇，这个 harness 确实解锁了一大堆能力”。在投资上是否发生了一种转变：不再仅仅针对最纯粹、最先进的模型，而是去更多地投资于工具能力以及其他能让公司和客户从先进模型中挖掘更多潜能的东西？

<details><summary>Original English</summary>
as you've talked about including in earnings releases and as you can just tell from these huge token budgets inference demand is booming but model training is still important but in addition to model training so you say okay rel if the if you have a pie chart the what the part that's inference is getting bigger but I assume the training is also growing as well but I'm curious from the perspective of like say the AI labs when they think about growth has there been a subtle shift from investing to push the pure model frontier having the absolute best state-of-the-art model verse investing in say better harnesses because a big reason we're excited and all talking about AI right now is really the excitement that happened over with cloud code in the final quarter of 2025 and it's like oh this harness has really unlocked a bunch of capabilities. Has there been a shift in investment from rather than just the purest most advanced model to let's invest more in tooling capacity and other things that allow companies and clients to get more juice from an advanced model.
</details>

我认为我们并没有接触到那种决策制定。

<details><summary>Original English</summary>
I don't think that we're exposed to that decision making.
</details>

>> 好。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 在 AI 实验室作为我们的交易对手方这方面。我能观察到的 AI 实验室的行为变化是，他们希望在更长的期限内获得更多的基础设施。对吧？而且——我会稍微作进一步说明，那就是一年前、两年前，我们签的是三年承诺合同。我们签订的合同类型基本上就像照付不议（take-or-pay）合同，这是为我们为客户构建的基础设施进行融资的最佳方式。去年是四年期合同，对吧？他们当时说，我们希望明确获得 Hopper 四年的使用权，或者 Blackwell 四年的使用权。

<details><summary>Original English</summary>
>> With the AI labs as counterparties to us. The observation I would make in a behavior change for the AI labs is they want access to more infrastructure for longer duration. Right? And and I'll qualify that a little bit which is a year two years ago we were signing three-year committed contracts. The type of contracts we sign are basically like take or pay contracts which is the best way to finance the infrastructure that we are building uh for our clients. Last year it was four-year contracts, right? They were saying we want explicit access to Hopper for four years or Blackwell for four years.
</details>

>> 现在他们找上门来说，其实我们想要五年，而且我们不希望在使用上有任何中断。我们承诺在合同的完整期限内维持完全相同的经济条款。在合同期内你不能升级或更换基础设施。你不能取消合同。我们想要五年。而且他们希望在更大的规模上进行，对吧？部署规模正变得越来越大。所以，这大概是我们针对 AI 实验室目前正在经历的决策制定所能给出的最佳定性描述。从基础设施的角度来看是这样吗？工具显然非常重要，但缩放定律（scaling laws）依然有效。是的。

<details><summary>Original English</summary>
>> Now they're coming and saying well actually we want it for five years and we don't want any interruption of use. We'll commit to the exact same economics throughout the full duration of the contract. You can't upgrade or change the infrastructure within it. You cannot cancel the contract. We want it for 5 years. And they want it at more scale, right? The deployments are getting larger and larger. So that's probably the best characterization we can offer on decision-m that AI labs are going through right now. Does it look from an infrastructure perspective? It it absolutely seems like tooling is important but scaling laws are still holding. Yeah.
</details>

>> 对。比如你通过规模化获取更多基础设施来推进前沿模型的能力依然成立，而且我们预计这种情况将一直持续到 Vera Rubin，并且目前看来短期内绝不会停止。

<details><summary>Original English</summary>
>> Right. Like your your ability to advance your frontier model through accessing more infrastructure at scale holds and that will hold through Vera Rubin we expect and seemingly it's not stopping anytime soon.
</details>

### 新架构演进：从 Hopper、Blackwell 到 Vera Rubin

>> 噢，对。关于 Vera Rubin 是怎么回事？你能跟我们解释一下吗？

<details><summary>Original English</summary>
>> Oh yeah. What's the deal with Vera Rubin? Can you explain that to us?
</details>

>> 呃，哪方面的？

<details><summary>Original English</summary>
>> Uh wh which aspect of it?
</details>

>> 它是什么？噢，对对对，基本情况。

<details><summary>Original English</summary>
>> What is it? Oh yeah yeah yeah basically.
</details>

>> 好。所以这只是英伟达即将推出的下一代架构，对吧，就像我们今天部署的主流架构是 Blackwell 一样。Blackwell 来了，我们主要采用 NVL72 配置进行部署，这在部署形式上是一次彻底的架构变革，对吧。如果你还记得的话，Hopper 是在 Blackwell 之前。Hopper 你可以部署这些 42U 机架，通常就是一个服务器机箱里装大概八张 GPU。你把它拿过来，插上电，也基本都是风冷的，对吧？我们当时运行了一些液冷，只是为了了解液冷的要求，因为对于我们的部署来说，Blackwell 在其部署配置中绝大多数都是液冷的。而且不同于 42U 配置中的八张 GPU，它放在这个更大的 72 GPU 机架中。运进来的就像是一整个机箱。呃，而且在数据中心里它看起来完全不一样。就像你在 X 上流传的图片里看到的那种巨大的塔状巨物。因此，Vera Rubin 将会是下一个推出的架构，并且我们已经开始接收用于 Vera Rubin 的测试机架。基本理念就是，这种新配置使整个系统更加

<details><summary>Original English</summary>
>> Yeah. So it's it's just Nvidia's next architecture that's coming out right like the current architecture that we're deploying today is Blackwell. Blackwell comes we deployed predominantly in a MBL72 configuration which was an entire architecture change from deployment right if you recall hopper came before Blackwell. Hopper you could deploy these 42U racks which was typically like eight GPUs in a server case. You would take it, plug it in, largely air cooled as well, right? We ran some liquid cooling just so that we understood the requirements of liquid cooling because Blackwell for our deployments um is overwhelmingly liquid cooled in its deployment configuration. And instead of eight GPUs in a 42U configuration, it's in this larger 72 GPU rack. It's like an entire chassis that's being brought in. uh and it it just looks entirely different in the data center. It's like this giant tower thing that you've seen in pictures floating around on X. So Vera Rubin uh will be the next architecture that comes out and we've started receiving testing racks uh for Ver Rubin. The basic idea is like the new configuration makes the whole system more
</details>

<!-- chunk 3/6 -->

高效，比如单位能耗产生更多 token 之类的。

<details><summary>Original English</summary>
efficient, like more tokens per energy use and that sort of thing.
</details>

>> 是的。对，我觉得你差不多说到点子上了。但这并不一定意味着——回到刚才那一点——每个人都只想要最新一代的 GPU，对吧？我们对 Ampere、Hopper、Blackwell 等架构都有巨大的需求。嗯，这只是因用例、模型以及客户类型而异。比如我会说，AI 实验室呃可能是最先排队去锁定最新一代 GPU 获取渠道的，

<details><summary>Original English</summary>
>> Yes. Yeah. I I think that's kind of where you're getting to with it. But that doesn't necessarily mean, going back to the point earlier, that everyone only wants the latest generation of GPU, right? We have massive demand for Ampear, Hopper, Blackwell, etc. Um, and it just varies by use case, model, and type of client as well. Like I would qualify that AI labs uh are probably the ones who are lining up first to secure access to the latest generation GPUs,
</details>

>> 而企业客户可能倾向于呃非常聚焦在当前一代，对吧？比如眼下的 Hopper 和 Blackwell。

<details><summary>Original English</summary>
>> whereas enterprise clients might be pro uh very focused on current generation, right? Like Hopper and Blackwell right now.
</details>

### 自研定制芯片与市场需求

>> 我坦白说一句。你看，我试图跟上很多与 AI 相关的事情。我确实尽力了。而且我每一天……

<details><summary>Original English</summary>
>> I'm going to be honest for a second. You know, I try to keep up on a lot of things AI related. I really do. And I every single day
</details>

>> 有一件事我就是记不住，如果你问我的话。比如，我很喜欢过去那种方式，以前是 186、286、386、486、奔腾，然后是奔腾 2 等等。那时它就是一个我能在脑子里记住的数字序列。所以如果有人问我：“Joe，比如 Ver、Ruben、Hopper、Blackwell，具体是什么顺序？”我比如，我得跟你说实话。我真的不太记得了。我会在某个时候把这个优先级提高。但说到芯片，就在昨天，微软发布了一个大消息——他们真的很想也参与到这场竞赛中来。他们不想仅仅局限于和实验室关联。他们自己也想拥有前沿模型。而且显然那是一个很好的模型，他们宣布了 MAI-1 思考模型，但他们表示该模型在 Maia 100 芯片上进行了优化，那是他们自己的芯片。这也是一件——再次回到我们最近的那次谈话——甚至连像 Hudson River Trading 这样的机构都在考虑涉足定制硬件领域。从你的视角来看，将模型与定制芯片对齐，这其中的性价比或投入产出比到底有多大？

<details><summary>Original English</summary>
>> the one thing I do not keep like in my mind if you asked me like I liked it in the old days when it was like 186 286 386 486 pennium and then like pennium 2 etc. then it was just this numerical sequence that I could keep track of in my head. And so if someone asked me like Joe like Ver Ruben Hopper Blackwell what was the sequence? I like I gotta be honest with you. I like don't exactly remember. And I will prioritize that at some point. But speaking of silicon, so yesterday Microsoft came out with a big they're really they want to be in the game too. They don't want to just be connected to labs. They they want to have advanced models too. And apparently it's a good model and they announced the MAI thinking one model but they said it's optimized on the Maya 200 chip which is their own chip and this is a thing which is even again going back to our recent conversation we had even a place like Hudson River trading is thinking about getting into the customized hardware game. How much juice for the squeeze is there of aligning the model with custom silicon from your vantage point?
</details>

>> 我们所能提供的，是我们从客户那里听到的反馈。

<details><summary>Original English</summary>
>> What what we could offer is what we hear from our clients.
</details>

>> 明白。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 关于那一点，而且有一点很重要，需要牢记——

<details><summary>Original English</summary>
>> On that and and it's important to keep in mind
</details>

>> 我们的平台上可以运行任何类型的芯片。好的。

<details><summary>Original English</summary>
>> we can run any type of silicon on our platform. Okay.
</details>

>> 对。我们在构建什么上是完全由客户主导的。比如，我们不会直接去承诺资本支出，然后投机性地期望大家来使用这些基础设施，对吧？比如，我们会等到有客户说：“我们希望你们去进行这项具体的建设。这是我们希望它呈现的样子。”然后我们再去承诺那笔资本支出，对吧？它更像是一种基于成果的资本支出模式。而客户要的全部都是英伟达的基础设施。

<details><summary>Original English</summary>
>> Right. We are entirely customer-led in what we build. Like we don't go commit to capex and speculatively hope people come and use infrastructure, right? like we wait until a client says, "We want you to go do this specific build. Here's what it we want it to look like." And then we go commit to that capex, right? It's more like a success-based capex approach. And the client isn't asking for anything but Nvidia infrastructure.
</details>

>> 我认为这在很大程度上归功于，我是说，他们围绕自己的芯片组构建了这个令人难以置信的生态系统。嗯，我认为到目前为止，他们通过 CUDA 架构在这方面深耕了超过 15 年，而且英伟达从我们从客户那里听到的情况来看，该平台仍然是市场上最高效、最具可扩展性、最可靠的一套基础设施，对吧？所以我我觉得其他家……

<details><summary>Original English</summary>
>> And I think a large contributor to that is I mean they built this incredible ecosystem around their chipset. um they have been dedicating to that for I think over 15 years at this point through the CUDA architecture and Nvidia from what we hear from our clients that platform just remains the most efficient the most scalable the most reliable uh set of infrastructure that is in the market right so I I I think others
</details>

>> 一直都有，我是说，回顾过去的几年，对吧，总有人在讨论比如这个怎么样，其他芯片和这些合作关系怎么样，而在这一天结束时，大家仍然在使用英伟达的基础设施。他们正在针对英伟达基础设施签下五年以上的长期合同，以及这些数以亿计、数十亿美元的投入承诺，因为他们知道那将是他们拓展业务规模的关键组成部分。在实质层面上，我们真的没有看到除了英伟达算力之外的任何需求，而这正是我们今天正在建设的。

<details><summary>Original English</summary>
>> there's always been I mean you think over the past few years right there's always been talk of like what did it what about this other silicon and these dealerships and at the end of the day like people are still using Nvidia infrastructure. They're committing to Nvidia infrastructure for five plus year contracts and these billion multi-billion dollar commitments because they know that that is going to be a critical part of how they scale their business. we really don't see demand uh on a material basis for anything but that Nvidia compute and that's what we are building today.
</details>

### 训练与推理中的芯片选择

>> 显然，我只是针对这一点稍微提出一些异议，而且我也并没有真正处于能够反驳的立场。我只能转述以往嘉宾说过的观点和我自己的阅读所见。我们的一位嘉宾说过，英伟达在模型训练上绝对拥有绝对优势；如果你想要训练一个模型，那么确实，英伟达芯片是唯一的选择。但是在推理方面，他的看法——这又是 Ian Dunning 的观点——他的看法是确实存在选择。然后当然，我们还有一位带有更强立场的嘉宾，我们采访了 Cerebras 的 CEO，呃，就是那家制造那块巨大板子的公司，或者抱歉，那个巨大的……

<details><summary>Original English</summary>
>> Obviously just to push back on this a little bit and I'm not really in any position to push back. I can only relay what past guests have said and my own reading. So what one of our guests said is that absolutely Nvidia has the lock on model training that if you want to train a model that yes Nvidia chips are the only game in town but that for inference there really his view this is Ian Dunning again his view is there really were options and then of course we had someone who was much more biased we interviewed the CEO of Sarah Bros uh the company that makes the gigantic plate and or sorry the the gigantic
</details>

>> 巨大的板子。

<details><summary>Original English</summary>
>> gigantic plate
</details>

>> 当然他也——但我意思是，他当然会说：“是的，CUDA 护城河在推理方面被严重高估了，它几乎不存在。”当然，他当然会那么说。所以，你知道，他是一家竞争对手，但我们也从一位推理用户那里听到了这种说法。从直觉上看这也说得通，比如训练非常复杂等等。但你的意思是，从客户的角度来看，你们看到对英伟达的需求在训练和推理两方面都很稳定，而且你们认为那种优势在两个维度上都是一致的。

<details><summary>Original English</summary>
>> and of course he But I mean, of course, he was going to say, "Yeah, the the the CUDA moat is vastly overrated for inference that barely exists." Now, of course, of course, he's going to say that. So, like, you know, he's in a competitor, but we've also heard it from a user of inference and intuitively it makes sense like training is very complicated and all that stuff. But what you're saying is that from the customer standpoint, you see the demand for Nvidia on both the training and the inference as being steady and that you perceive that advantage to be consistent through both aspects.
</details>

>> 所以我想在我们上一季度的财报中，我们的 CEO Mike 明确指出，在我们的平台上，推理工作负载占基础设施利用率的 50% 以上。

<details><summary>Original English</summary>
>> So I believe in our last quarterly report our CEO Mike qualified that inference workloads represent well in excess of 50% of infrastructure utilization on our platform.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 他们用于训练的基础设施完全是一模一样的。对的。回到我之前的评论，即在这些不同类型的工作负载之间，它是非常可替代流通的。

<details><summary>Original English</summary>
>> the exact same infrastructure they use for training as well. Right. Going back to my comment of like it's very funible between those different types of workloads.
</details>

>> 那些客户在推理方面依然选择与英伟达合作。我认为你将会看到的是，人们会希望小规模尝试其他类型的芯片，但从我们的角度来看，目前最可靠、经过验证且仍然最高效的基础设施依然是英伟达。这种情况随着时间推移会改变吗？谁谁真的知道呢？但我认为我们已经看到英伟达与这种论调抗争多年了，每年他们都会站出来，并且他们依然是 AI 基础设施的既定之选。我想我们将会是市场上最早察觉到这一点的群体之一。嗯，因为那将是来自我们客户的基调转变，要求我们去运行别的东西。

<details><summary>Original English</summary>
>> Those customers are choosing Nvidia to work with on imprints. I I think what you're going to see is people will want to try at small scale other types of silicon but the reliable proven and remains from our perspective most efficient infrastructure to use is Nvidia today. Does that change over time? Who who really knows? But I think we've seen Nvidia battling this concept for years and every year they show up and like they remain the de facto choice for AI infrastructure. I I I think we're going to be one of the first people in the market to see it. Um because that will be a tone shift change from our clients asking us to run something else.
</details>

>> 那还没有发生。

<details><summary>Original English</summary>
>> That hasn't happened.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

### 数据中心的核心瓶颈：通电毛坯

>> 那么对你们业务的制约因素有发生任何变化吗？好吧，三年前我们在谈论 GPU 以及实际获取它们有多难。我设想获取 GPU 至少依然竞争激烈，但你们是否看到其他制约因素浮现，就像 Joe 在开场中提到的？比如单纯的土地使用，单纯的实际建设数据中心的地方。

<details><summary>Original English</summary>
>> So have the constraints on your business changed at all? Well, so three years ago we were talking about GPUs and how hard they were to actually get. I imagine GPU securing GPUs is still competitive to say the least, but are you seeing other constraints emerge like Joe mentioned in the intro? Just land usage, just places to actually build data centers.
</details>

>> 土地使用本身，我不会说它算是一个很大的顾虑。拥有带电毛坯房（powered shell）才是瓶颈。好的。在今天，让我界定一下带电毛坯房。带电毛坯房是——

<details><summary>Original English</summary>
>> Landed usage specifically, I wouldn't say is as much of a concern. Having a powered shell is the bottleneck. Okay. today and let me qualify PowerShell. PowerShell is
</details>

>> 实际上就是一个已经通了电的空置数据中心，

<details><summary>Original English</summary>
>> effectively an empty data center that is energized,
</details>

>> 对吧？它具备所有电力以及相关组件。我可以走进去把

<details><summary>Original English</summary>
>> right? It has all the power and associated components. I can come into it and deliver
</details>

>> 电力输送到机架上。内部建有冷却系统。比如它它具备完整的一切，对吧？带电毛坯房是行业内的称呼。那就是瓶颈所在，因为所有相关的供应链都汇聚于此，对吧？比如不仅是你是否拥有电力、是否拥有土地等等，而且你还要有备用电池供应、你还要有变压器、嗯你还要有人力，对吧？比如想想看这些场地的电工，以及让电工方面获得认证从而能够参与这些建设。我是说，我认为要能够完成那个培养项目，需要 5 年以上的学徒期，对吧？我们不可能利用一条供应链就直接凭空制造出新的电工，对吧？比如那是你无法真正高效扩充规模的一个工种。所以这对于我们以及我认为目前市场上存在的同业群体来说，绝对就是瓶颈所在。芯片的获取渠道，嗯，我认为我们与英伟达有着非凡的关系，我们已经证明了自己是这个星球上这套基础设施的最佳运营商。你知道，以往存在于我们面前的一个瓶颈，我认为是获取融资的渠道。

<details><summary>Original English</summary>
>> electrons into a rack. Has the cooling system built within it. Like it it has the whole thing, right? It powered shell is is the industry term for it. That is the bottleneck because of all of the supply chains that that come into that, right? Like not only you have electricity, do you have the land etc. But you have the backup battery supplies, you have the transformers, um you have personnel, right? Like think about the electricians for these sites and getting the accreditation on electrician side to be able to participate in these builds. I mean, I think it's a 5year plus apprenticeship to be able to go through that program, right? We can't just make new electricians leveraging a supply chain, right? like that that's a trade that you can't really scale efficiently. So that is absolutely the bottleneck for us and I think our peer set that's out there right now. Access to chips. Um I think we have a phenomenal relationship with Nvidia where we've just proven to be the best operator of this infrastructure on the planet. You know a bottleneck that existed for us previously I think was access to financing.
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 对。众所周知——

<details><summary>Original English</summary>
>> Right. as we all know
</details>

>> 现在似乎不再是个问题了。

<details><summary>Original English</summary>
>> doesn't seem to be an issue anymore.
</details>

>> 我大体上同意嗯那种说法，但那是多年的辛勤工作和执行力为我们带来了这种能力。我是说，今年迄今为止，我们已经为我们的业务筹集了超过 210 亿美元的融资。比如，你不可能平白无故就做到这一点，然后比如直接从零冲到 20。而且而且我认为这很大程度上是由我们的执行记录所推动的，对吧？我们的投资者、我们的债权人可以看到多年来在持续交付这些工程项目上积累的深厚经验。我是说，在当前时点，我们在运行中的呃呃电力容量已经超过了一吉瓦（gigawatt），对吧？比如在一吉瓦的规模下，比如在数据中心层面配合 GPU，你知道，输送进……

<details><summary>Original English</summary>
>> I I I would agree um with that broadly, but that's years of work and execution that has delivered that ability for us. I mean, year to date, we've raised over $21 billion of financing for our business. Like, you don't get to do that and just go from, you know, zero to 20 right out of nowhere. And and I think that's largely driven by our track record of execution, right? Our investors, our creditors can see this deep set of experience over the years of consistently delivering on these builds. I mean, we have over a gigawatt in active uh uh power at at this point, right? Like a gigawatt like at the data center level with GPUs, you know, delivering into
</details>

<!-- chunk 4/6 -->

clients。而且我认为市场上一直存在某种误解，人们把“纸面上敲定了某件事”与“物理上建成并交付”这两个概念混为一谈了。我只能说，签下2030年交付的电力合同，与实际把这些转化为可计费的GPU机时之间，存在着巨大的鸿沟。

<details><summary>Original English</summary>
clients.

 And

 I

 I

 think





that

 there's

 been

 kind

 of

 a





misunderstanding

 in

 the

 market

 where





where

 people

 are

 conflating

 the

 concept





that

 like

 you

 know

 something

 on

 paper

 is





the

 equivalent

 to

 being

 physically

 done





and

 delivered.

 And

 all

 I

 can

 say

 is





there's

 an

 enormous

 gap

 between

 you

 know





signing

 for

 power

 for

 delivery

 in

 2030
</details>

>> 与实际将其交付转化为可计费的GPU机时相比。而这种执行力上的差距，正是极为激进地拉低我们资本成本的关键所在。这个差距就是我们业务的立足点，也是它如此成功的原因。我的意思是，秘诀就在于我们有能力承接这些数据中心部署以及这些客户关系，并将其转化为可计费的GPU机时。说到融资，我只想说，去年比如大约六个月前，可能差不多是受Michael Burry启发的“这些芯片只能用两年”论调的高峰期。你在Twitter上能看到的疯传图表之一，就是CoreWeave的CDS图表。那些利差已经大幅收窄了。所以，这……这……

<details><summary>Original English</summary>
>> versus

 actually

 delivering

 that

 into





billable

 GPU

 hours.

 And

 that

 gap

 of





execution

 is

 what

 has

 driven

 down

 our





cost

 of

 capital

 so

 aggressively.

 That





gap

 is

 where

 our

 business

 sits

 and

 why





it

 has

 been

 so

 successful.

 I

 mean

 that





that's

 the

 secret

 sauce

 is

 our

 ability





to

 take

 these

 data

 center

 deployments





and

 these

 customer

 relationships

 and





deliver

 billable

 GPU

 hours

 into

 them.





You

 know,

 speaking

 of

 financing,

 I

 just





want

 to

 say,

 you

 know,

 during

 last

 year,





like

 maybe

 six

 months

 ago,

 that

 might





have

 been

 the

 sort

 of

 near

 peak

 of

 the





Michael

 Bur

 inspired

 these

 chips

 are





going

 to

 last

 two

 years

 stuff.

 And

 one





of

 the

 viral

 charts

 that

 you

 would

 see





on

 Twitter

 was

 the

 Cororeweave

 CDS





chart.

 Those

 have

 come

 way

 in.

 So,

 it

 is





uh

 it

 is,

 you

 know,
</details>

>> 我已经好久没看到那些图表了。我……

<details><summary>Original English</summary>
>> I

 haven't

 seen

 those

 charts

 in

 a

 while.





I
</details>

>> 没错。这就是CDS的特点。当信用违约互换利差收窄时，从来没人发图表；当它们急剧走阔时，大家都热衷于发出来。它们确实大幅收窄了。所以，这确实说明自年初以来，这些担忧至少在某种程度上得到了缓解。在讨论信用违约互换和融资时，我突然想到——我正准备写一篇大文章，可能目前只是在脑海里打草稿——数据中心业务与银行业务之间确实存在很多相似之处。我们在银行业中学到的教训之一（比如从SVB学到的），就是行业和储户集中度风险：如果你的储户要么全在……或者某个储户规模过大，要么所有储户都在同一个行业，那你就会面临这种类似关联性挤兑的风险。这显然是搞垮SVB的原因。当你们考虑规划、考虑“好吧，这是投资等等”时，这种考虑……我想大概是租户……

<details><summary>Original English</summary>
>> That's

 right.

 That's

 the

 thing

 about





CDS.

 No

 one

 ever

 posts

 charts

 of

 credit





default

 swaps

 when

 they're

 coming.

 They





people

 love

 to

 post

 when

 they're

 blowing





out.

 They

 have

 um

 come

 in.

 So,

 you

 know,





that

 does

 speak

 to

 some

 of

 this

 point





about

 these

 anxieties

 uh

 having

 been





alieved

 at least

 uh

 somewhat

 since

 the





start

 of

 the

 year.

 You

 know,

 it

 occurred





to

 me

 like

 we're

 talking

 about

 credit





default

 swaps.

 We're

 talking

 about





financing.

 I'm

 g

 I'm

 sort

 of

 gearing

 up





to

 write

 a

 big

 thing

 maybe

 but

 I'm





writing

 it

 in

 my

 head

 currently

 that





there

 really

 are

 a

 lot

 of

 analogies





between

 the

 business

 of

 data

 centers

 and





the

 business

 of

 banking

 and

 one

 of

 the





things

 in

 banking

 as

 we

 all

 learned

 from





SVB





was

 the

 risk

 of

 industry

 and

 depositor





concentration

 that

 you

 if

 you

 have

 all





your

 depositors

 are

 either

 in

 like

 one





depositor

 gets

 too

 big

 or

 all

 your





depositors

 are

 in

 the

 same

 industry

 then





you

 have

 this

 risk

 of

 like

 correlated





withdrawal.

 calls

 and

 that's

 what





obviously

 did

 in

 SVB

 when

 you

 think





about

 planning

 and

 you

 think

 about

 okay





here's

 investment

 etc

 how

 much

 does

 this





come

 up

 sort

 of

 like

 thinking

 about

 I





guess

 uh

 tenant

 uh
</details>

>> 多样化。

<details><summary>Original English</summary>
>> diversification
</details>

>> 对，租户多样化，这是你们在多年期规划中会考虑的事情吗？

<details><summary>Original English</summary>
>> yeah

 tenant

 diversification

 as

 something





that

 you

 think

 about

 in

 your

 multi-year





planning
</details>

### 客户集中度与融资架构

>> 这是一个至关重要的方面，对吧？就像我之前说过的，这也是去年我们进行IPO筹备时面临的一个关键批评，对吧？当时我们在收入上存在那种客户集中度。我们在这方面取得了巨大进展，我认为最好的理解方式是：我们可以把所有未分配的容量——我用这个词非常具体，它不是“未售出”容量（那意味着没有需求），而是“未分配”，市场需求非常旺盛，我们正在规划它的去向——就客户这部分而言，老实说，我认为我们可以把所有这些容量分配给单一名义客户，对吧？有相当数量的单一名义客户是我们可以去把容量分配给他们的。但我不认为这是我们在这里应该建立的业务。我认为我们应该建立的业务是一个多元化的云平台，为全球领先的AI消费者和生产者提供支持。我不认为我们应该只支持一两家公司。

<details><summary>Original English</summary>
>> it's

 a

 critical

 aspect

 of

 it

 right

 as

 I





said

 earlier

 too

 like

 this

 was

 a

 key





criticism

 of

 us

 coming

 into

 our

 IPL

 last





year

 right

 where

 we

 had

 that

 customer





concentration





in

 our

 revenue

 and

 we

 have

 made

 enormous





progress

 there

 and

 I

 think

 the

 best

 way





to

 think

 about

 it

 is

 we

 could

 take

 all





of

 our

 unallocated

 capacity

 and

 I

 say





that

 very

 specifically

 it's

 not

 unsold





capacity

 implying

 that

 there's

 no

 demand





for

 it

 it's

 unallocated

 there's

 intense





demand

 for

 it

 we're

 figuring

 out

 where





it

 should

 go

 and

 that

 customer

 piece

 of





it

 I

 think

 honestly

 like

 we

 could





allocate

 all

 that

 capacity

 to

 like





single

 name

 clients,

 right?

 Like

 there





is

 a

 pretty

 significant

 number

 of

 single





name

 clients

 we

 can

 go

 allocated

 out





into.

 But

 I

 I

 I

 don't

 think

 that

 is

 the





business

 we

 are

 supposed

 to

 be

 building





here.

 I

 think

 the

 business

 we

 are





supposed

 to

 be

 building

 is

 a

 diversified





cloud

 that

 is

 supporting

 the

 uh

 uh





leading

 AI

 consumers

 and

 producers

 on

 on





the

 planet.

 I

 don't

 think

 we're

 supposed





to

 be

 supporting

 just

 one

 or

 two





companies.
</details>

关于融资，你能否多谈谈究竟发生了什么变化，让市场对此更加放心？因为这正是市场上的重头戏：现在有如此多的AI融资正在通过公司债市场发行。正如我们所知，股票市场目前基本全是大科技公司。在投资者方面发生了什么变化？仅仅是因为纯粹的回报和业绩表现，还是说有了更强有力的举措让合同更具约束力，或是提高了对需求的可见度诸如此类？看到推理层面的发展，确实极大地鼓舞了投资者。但这其实也就是1月份的事，对吧？或者可能是第四季度末，你开始看到这种完全由推理驱动的爆发式需求拐点。

<details><summary>Original English</summary>
when

 it

 comes

 to

 financing.

 Can

 you

 say





a

 little

 bit

 more

 about

 what

 changed

 to





make

 the

 market

 more

 comfortable

 with





this?

 Because

 like

 this

 is

 the

 big

 story





in

 markets

 just

 how

 much

 AI

 is

 now

 being





issued

 through

 the

 corporate

 bond





market.

 The

 equity

 market

 as

 we

 know

 is





basically

 all

 big

 tech

 at

 the

 moment.





Like

 what

 changed

 on

 the

 part

 of





investors?

 Was

 was

 it

 just

 pure

 return





and

 performance

 or

 were

 there

 I

 guess





efforts

 to

 like

 make

 the

 contracts

 more





robust

 or

 increase

 visibility

 into





demand

 and

 that

 sort

 of

 thing?

 seeing





the

 inference

 aspect

 of

 it

 really





emboldened

 in

 investors.

 But

 like

 that





that

 was

 really

 just

 you

 know

 January





right

 or

 maybe

 late

 Q4

 where

 you

 started





seeing

 this

 just

 massive

 inflection

 of





demand

 driven

 by

 inference
</details>

>> 对我们而言，对吧？我很难去评述其他公司，但对我们来说，为什么我们能获得如此大规模的承销，而且资本成本还在不断下降？我认为这要归结于那种执行记录，对吧？就是市场看着我们去执行，看着我们在这些合同上完成交付。关于我们为业务融资的方式——如果我讲得太细你就告诉我——你大体可以把它分成两大类，对吧？母公司融资和资产公司融资。资产公司融资是所有GPU获得融资的地方，对吧？所有客户合同都放在那里，我们可以把这些融资放入SPV中，或者打个比方，我们就叫它一个箱子……

<details><summary>Original English</summary>
>> for

 us

 right

 and

 it's

 tough

 for

 me

 to





speak

 about

 you

 know

 other

 companies

 but





for

 us

 like

 why

 why

 have

 we

 been





underwritten

 at

 such

 scale

 and

 at

 a





decreasing

 cost

 of

 capital

 I

 think

 it





goes

 back

 to

 that

 track

 record

 of





execution

 right

 it's

 just

 the

 market

 has





watched

 us

 execute

 and

 watched

 us





deliver

 on

 these

 contracts

 and

 the

 way





and

 tell

 me

 if

 I'm

 going

 into

 too

 much





detail

 here,

 but

 but

 the

 way

 that

 we





finance

 our

 business,

 you

 kind

 of

 break





it

 into

 two

 broad

 buckets,

 right?

 You





have

 parent

 co-

 financing

 and

 asset

 co





financing.

 And

 asset

 co

 financing

 is





where

 all

 of

 the

 GPUs

 get

 financed,





right?

 It's

 where

 all

 of

 our

 client





contracts

 sit

 and

 we

 could

 take

 these





financings

 and

 put

 them

 into

 STDs

 or





we'll

 just

 call

 it

 a

 box

 so

 to

 say

 and
</details>

>> 你……抱歉，请继续。

<details><summary>Original English</summary>
>> you





sorry

 keep

 going
</details>

>> 箱子、箱子有很多含义，不过请继续，请继续。

<details><summary>Original English</summary>
>> boxes

 boxes

 on

 lots

 of

 connotations

 but





keep

 going

 keep

 going
</details>

>> 我们把它们放入SPV中，这些SPV内部拥有基础设施、承担数据中心成本，并且包含债务协议。因此，你能够将这种为期五年的“照付不议”合同与债务的摊销计划相匹配；收入进入这个箱子，偿付债务摊销计划，支付数据中心的运营成本，而且它仍然向母公司贡献利润，拥有25%的边际贡献率，对吧？在SPV结构底层，这些都是利润极高的协议。于是你把那个SPV拿到信贷市场去，说：“看看这个工具，这是一套由交易对手组成的独立合同组合，比如想要使用GPU算力的实体；内部包含数据中心等等。”而且，我们最近做的一笔是——我们称之为DDTL4——这是一笔获得投资级评级、开同类先河的交易。此前从未有人在GPU融资、无追索权的高性能计算基础设施融资中做到这一点，它的定价是SOFR加225个基点。对我们来说，这是一个极具优势的资本成本。更重要的是，我们成功引入了保险资金层级，那是市场上规模庞大的一笔资金，正寻求在该领域进行配置。因此，我们在这些不同的资本层级中不断取得进展，解锁接触越来越多类型投资者的渠道。这就是为什么你会看到我们进军可转换票据市场、无担保债券市场，同时也接受直接的战略股权投资。但对我们来说，让整个投资界理解这项业务非常重要，因为这项业务以前基本不存在，对吧？人们以前不会向超大规模算力企业放贷来支持这些建设，对吧？老实说，开辟这条“如何有效为AI超大规模企业提供融资”路径的责任落在了CoreWeave身上，而且我认为过去几年里我们在这方面做得非常出色。

<details><summary>Original English</summary>
>> we

 put

 them

 into

 SPDs

 uh

 and

 these

 these





SPVS

 they

 have

 the

 infrastructure

 they





have

 the

 data

 center

 costs

 and

 they

 have





the

 uh

 the

 the

 debt

 agreements

 within





them.

 And

 so

 you're

 able

 to

 pair

 this





like

 five-year

 take

 or

 pay

 contract

 to





an

 amortization

 schedule

 on

 the

 debt

 and





you

 have

 the

 revenue

 come

 into

 the

 box,





pay

 down

 the

 amortization

 schedule,

 pay





down

 the

 operating

 costs

 of

 the

 data





center,

 and

 it

 still

 contributes

 a

 it





has

 a

 25%

 contribution

 margin

 of

 profit





up

 to

 the

 parent

 code,

 right?

 like

 these





are

 highly

 profitable

 agreements

 down

 in





the

 SPV

 stack.

 And

 so

 you

 take

 that

 SPV





out

 to

 the

 credit

 market

 and

 say

 look

 at





this

 instrument

 that's

 a

 discrete

 set

 of





contracts

 with

 counterparties

 like





entities

 who

 want

 to

 consume

 GPU





compute.

 Um

 you

 have

 the

 data

 centers





within

 it

 etc.

 And

 you

 know

 one

 of the





latest

 ones

 we

 did

 was

 uh

 as

 we

 call





DDTL4





this

 was

 a

 investment

 grade

 rated

 first





of

 its

 class.

 No

 one

 had

 done

 this





before

 for

 GPU

 financing,

 nonreourse

 HPC





infrastructure

 financing

 and

 got

 done

 at





sofur

 plus

 225





like

 that

 that

 is

 a

 phenomenal

 cost

 of





capital

 for

 us

 and

 importantly

 we

 were





able

 to

 bring

 in

 uh

 the

 insurance

 trunch





of

 capital

 which

 is

 a

 massive

 trunch

 of





capital

 out

 there

 that

 is

 looking

 to

 do





allocations

 into

 the

 space.

 So,

 we're





kind

 of

 continuously

 making

 progress





through

 these

 different

 stacks

 of





capital

 and

 locking

 access

 to

 more

 and





more

 types

 of

 investors.

 It's

 why

 you've





seen

 us

 move

 into

 the

 convertible

 note





market

 into

 the

 unsecured

 market

 um

 as





well

 uh

 along

 with

 taking

 you

 know





direct

 uh

 strategic

 equity

 investments.





But

 for

 us,

 it's

 really

 important

 for





the

 entire

 investor

 space

 to

 understand





this

 business

 because

 this

 business





largely

 didn't

 exist

 before,

 right?

 Like





people

 weren't

 making

 loans

 into

 the





hypers

 scales

 to

 go

 credit

 these





buildouts,

 right?

 It's

 it's

 on

 coreweave





honestly

 to

 be

 building

 this

 path

 into





how

 do

 you

 finance

 the

 AI

 hyperscaler





effectively

 and

 I

 think

 um

 we've

 just





done

 a

 terrific

 job

 of

 it

 over

 the

 past





few

 years.
</details>

### 可交易算力与大宗商品属性

>> 你前世曾经做过交易员，对吧？

<details><summary>Original English</summary>
>> You

 used

 to

 be

 in

 a

 prior

 lifetime

 a





trader,

 right?
</details>

>> 是的，我曾是一名大宗商品交易员。

<details><summary>Original English</summary>
>> Yes,

 I

 was

 a

 commodity

 trader.
</details>

>> 所以我很好奇，大家对GPU算力交易抱有很大兴趣——我不知道这最终能否落实——而且即将推出新的合约。我们最近采访了Compute Exchange的CEO，他们非常接近在CME挂牌上市相关产品。从你的角度来看——因为我对这一点还没有定论——一方面，你看到大型AI公司签下五年期合同，正如你所说合同期限正在拉长，“我们要锁定这个”。我不知道在那种环境下对可交易算力的需求会是什么等等。你的推测是什么？你是否预计会有足够由套期保值者和投机者构成的生态，从而形成一个可交易算力的流动性市场？

<details><summary>Original English</summary>
So,

 I'm





curious

 like,

 you

 know,

 there's

 a

 lot

 of





interest

 in

 and

 I

 don't know

 if

 it's





going

 to

 materialize

 in

 uh

 GPU

 capacity





trading

 and

 there's

 going

 to

 be

 a

 new





contract.

 We

 recently

 uh

 interviewed

 um





the

 CEO

 of

 Compute

 Exchange

 and

 they're





very

 close

 to

 having

 something

 listed

 on





the

 CME

 from

 your

 perspective

 because

 I





I

 don't

 have

 a

 view

 on

 this

 yet.

 On

 the





one

 like

 you

 see

 like

 okay,

 a

 big

 AI





company

 does

 a

 five-year

 contract

 as

 you





say

 the

 duration

 is

 lengthening.

 we're





going

 to

 lock

 this

 in.

 I

 don't

 know

 like





what

 the

 need

 is

 for

 tradable

 compute

 in





that

 environment

 etc.

 What's

 your

 guess





like

 do

 you

 anticipate

 that

 there

 will





be

 a

 sufficient

 ecology

 of

 hedggers

 and





speculators

 such

 that

 there

 will

 be

 a





liquid

 market

 for

 tradable

 compute.
</details>

>> 我认为这是一个摆在面前的非常明确的时间表问题。短期来看，不会。让我来谈谈为什么短期不会，然后再说为什么长期或许可以……

<details><summary>Original English</summary>
>> I

 I

 think

 it's

 a

 it's

 a

 very

 much

 a





timeline

 question

 that's

 out

 there.





Shortterm,

 no.

 Let

 me

 offer

 why

 no





short-term

 and

 then

 I'd

 say

 maybe

 in

 the





long

 term
</details>

>> 这完全归结于可替代性，对吧？如果你想想黄金，黄金是由其化学成分定义的，对吧？不存在……

<details><summary>Original English</summary>
>> and

 it

 all

 comes

 back

 to

 fungeibility





right

 if

 you

 think

 about

 gold

 gold

 is





defined

 by

 its

 chemical

 composition





right

 and

 there's

 no
</details>

>> 什么是黄金、什么不是黄金的问题等等……

<details><summary>Original English</summary>
>> uh

 uh

 question

 of

 of

 what

 is

 gold

 and





not

 gold

 etc
</details>

>> 算力真不是这样，对吧？尤其是GPU算力。

<details><summary>Original English</summary>
>> compute

 really

 isn't

 right

 especially





GPU

 compute
</details>

>> 如今的GPU算力是……

<details><summary>Original English</summary>
>> GPU

 compute

 today

 is
</details>

<!-- chunk 5/6 -->

### GPU 的不可替代性与软件栈差异

不可替代，而且我认为这一点已经被我们的客户群、我们的供应商、以及像 SemiAnalysis 这样的第三方咨询机构所充分理解了。核心观点在于：部署在一个云上的 H100，并不能达到与部署在另一个云上的 H100 相同的性能。人们使用的指标包括有效吞吐量（goodput）或模型浮点运算利用率（MFU）等。通过这些测量方式可以发现，同一款 GPU——顺便提一句，完全相同的 GPU——部署在一个数据中心与部署在另一个数据中心相比，性能究竟能高出多少。因此，某种东西要变成大宗商品化，它就必须具备可替代性，对吧？否则就会存在太多模糊不清的地方，缺乏一个确切的数据基准。

<details><summary>Original English</summary>
not fungeable and I think that this is well understood by our client base, by our suppliers, by you know third party consultants like Cine Analysis and it's it's this idea that an H100 deployed in one cloud doesn't have the same performance of an H100 deployed in another cloud and the the metrics that people use are things like good put or model flop utilization MFUs and there are these measurements of like how much more performant is one G the exact same GPU by the way versus another GPU deployed in another facility. And so in order for something to be commoditized, it it has to be fungeible, right? Otherwise, there's just too much, you know, murkiness and there isn't like uh an exact data point in there.
</details>

>> 我能针对这点再深入追问一下吗？我是说，我觉得这听起来是个合乎情理的观点。这种不可替代性是与配置相关吗——比如具体是指 GPU 内部物理上的配置方式？究竟是什么原因造成的？是因为电力吗？我的意思是，很多地方都会说“我们能达到 9 个 9”或者你们行业所需的任何几个 9 的可靠性等等。在你看来，究竟是什么原因会导致同一款 H100 在一个云和另一个云之间的性能出现显著差异？在某种程度上可能是配置原因，对吧？我们所有的东西都是按照 DGX 参考规范来构建的，这是英伟达所制定的标准。这是构建、运行和交付……

<details><summary>Original English</summary>
>> Can I push on that a little bit further? So, I mean, I think that seems like a reasonable view. Is the nonf fungeability related to configuration of like how they literally like the configuration of the GPUs within physically like what is it is it about power I mean I think they all like you know there are plenty of places that will say you know we have nine 9ines or however many nines you need in your industry or whatever. What is it in your view that would cause significant changes in the performance of an H100 in one cloud versus another? It could be in some part configuration, right? We build everything to DGX reference spec u which is the most outlined by Nvidia. It's the most performant way to build, operate and deliver
</details>

>> ……GPU 最高性能的方式。但老实说，其余部分纯粹就在于你如何运维这些 GPU，而这正是 CoreWeave 的软件栈所在。那就是你如何保持这些 GPU 处于在线状态，对吧？比如，如果某个 GPU 发生故障会怎样？你是否能预测 GPU 即将发生故障并置换入其他基础设施，从而让客户在该组件上不产生停机时间？为了在行业中达到最佳的有效吞吐量、最佳的 MFU，我们构建了一整套庞大的软件解决方案和基础设施管理解决方案。这些都不是现成可买到的，对吧？所以我觉得这不能归结为单纯的硬件组件。那只是一个最低限度的起步门槛，对吧？就像你必须从 DGX 参考规范起步一样。但差异化正是从这里产生的，我是说，这正是你刚才所描述的核心产品。

<details><summary>Original English</summary>
>> GPUs. But but the rest of it honestly is just how you operate the the GPUs and that is the coreweave software stack that is how do you keep these GPUs online, right? Like what happens if a GPU fails? Can you predict if a GPU is about to fail and swap in other infrastructure so that the client doesn't have downtime on that component? And there's there's an immense suite of software solutions that and and infrastructure management solutions that we have built to have the best goodput to have the best MFUS in the industry. And that's none of that is is off the shelf, right? And so I I wouldn't say it comes down to the strict components. That's kind of like a bare minimum starting point, right? Like you have to start in DJX reference spec. But where's differentiation come from there? I mean that's that's the core product you're describing right there.
</details>

### 专业术语与大宗商品化路径

>> 顺便提一下，特蕾西（Tracy），我刚才查了一下专业术语。根据谷歌的解释，有效吞吐量（goodput）衡量的是训练任务所能发挥出的峰值硬件性能的比例；而 MFU（模型浮点运算利用率）则是用于评估大语言模型训练实际效率的硬件指标。所以这是两个新词汇。在此之前我其实没听过 MFU 或 goodput。今天正好学到了两个新术语。

<details><summary>Original English</summary>
>> By the way, Tracy, I'm just looking up terms of art. Goodput measures the fraction of peak hardware performance that the training job can extract. This is according to Google. And MFU's model flops utilization hardware metric for evaluating real world efficiency of LLM's training. So, two new terms. I actually hadn't heard of MFUS or goodput before this. So, I just learned two new terms today.
</details>

>> 我们得建一个 AI 词汇表了。

<details><summary>Original English</summary>
>> We got to create a uh an AI glossery.
</details>

>> 是的，确实得建一个。布兰登（Brandon），早些时候乔（Joe）问你关于算力市场的问题时，你说这是一个时间线问题，在我看来这意味着它是必然发生的，只是一个耗时多久的问题。但当你后来描述这种不可替代性问题时，这似乎又是一个极其难以解决的实际难题。

<details><summary>Original English</summary>
>> Yeah, we do. Brandon, when Joe asked you that question about um compute markets earlier, you said it was a timeline question, which in my mind implies that it's inevitable. Like it's just a question of how long it takes. But then when you describe the funggeability problem, it seems like this is an actual issue that will be very difficult to solve.
</details>

>> 是的，我认为这种描述完全准确。如果你单看通用的大宗商品理论——我做过十年以上的天然气、电力和农产品交易——理论表明它在某个时刻应当变成那样。但当下的现实是什么？现实是这些东西的运维并没有变得更容易，对吧？我们已经从相对简单的 Hopper 42U 风冷机架，发展到极其复杂的 Blackwell 部署，随后还将迈向 Vera Rubin。在构建、运维、配置和交付这些 GPU 方面，事情并没有变得更容易，而是变得更加困难。我认为在它开始变简单之前，算力真正走向大宗商品化是没有明确路径的。你必须继续优先与世界一流、全球领先的基础设施运营商合作。这正是我们的定位所在。

<details><summary>Original English</summary>
>> Yes, I I think that characterization is absolutely correct, right? Like if you just take general commodity theory and I traded natural gas, electricity, agriculture products for over a decade like it suggests that it should become that at some point. But what is the reality today? The reality is this stuff isn't getting easier to operate, >> right? We've moved from these kind of relatively simple 42U aircooled racks of hopper to these immensely complex blackwell deployments moving into Vera Rubin following that like it's not getting easier to to build operate provision deliver these GPUs it's getting more difficult and I I I think until it starts becoming easier you don't really have a path to commoditization you will have to continue to prioritize working with the world class and worldleading operators of infrastructure. That's where we sit.
</details>

### 小规模与超大规模算力需求的反差

>> 首先，这很有帮助，而且我很高兴我们能听到多种不同视角的观点，因为我确实认为这将是金融市场面临的大问题之一。因为假设如果这些算力市场真能兴起，你可以设想它甚至可能改善融资条件，因为贷款方就可以进行对冲……是的，所以如果能做起来，可能确实会对行业带来一些好处。因此很感谢能听听你对此的看法。为什么——顺便说一下，我自己也是个推理用户，我在自己的一个业余项目中做了一个小型机器学习模型，我在 havlock.ai 提供推理服务，或者说我是个推理使用者，我有这么个模型什么的。为什么……

<details><summary>Original English</summary>
>> First of all, this is helpful and I like that we're getting multiple perspectives because I do think this is going to be like one of the big questions for financial markets because let's say if they took off then you could imagine that might even improve financing conditions because then the lender can hedge against Yeah. So like there would probably be some good things for the industry if this took off. So I appreciate it's good to have your um perspective on this. Why is it you know I'm a I'm an inference prov I I I I'm an inference user by the way so I I made a little machine learning model in one of my hobby projects and I provide inference over at havlock.ai or I'm a user of inference or whatever I have a model whatever. Why is it that
</details>

>> 如果你是在提供推理服务，那挺令人佩服的。

<details><summary>Original English</summary>
>> impressive if you were providing inference?
</details>

>> 我其实算是个推理消费者。我用了一个……总之，为什么对于我这样的人来说，其实很容易就能拿到算力配额——虽然不是很大的配额。我使用过 GPU 算力，当时我想着如何训练这个模型。这是一个谷歌在 2018 年或 2019 年发布的名为 BERT 的模型，我针对自己的用途对其进行了微调，然后基本上直接通过 cloud code，在 10 分钟内就完成注册，开始使用一家名为 Modal 的公司的服务，并且能够着手训练模型了。我很惊讶这根本没花我多少钱，而且我的用量极小，但尽管如此，显然市面上还是有一些零散的 GPU 算力可供我获取，整个过程大概也就花了我 5 美元左右。然而大家平时听到的却总是像“利用率已被打爆”这样的说法。为什么对于像我这样的人来说，找到 GPU 算力实际上并没那么难？

<details><summary>Original English</summary>
>> I'm trying to I I guess I'm a consumer of inference. I use a um anyway why is it that I'm actually very easily able to get now not a huge allocation I've used like GPU access so I was like how do I train this model it's a model called BERT that Google released in 2018 or 2019 I fine-tuned it for my purposes and then literally using cloud code I was able to in 10 minutes sign up I started using this company called modal and I was able to start training a uh model. I was surprised that there was like and it didn't cost me very much and I have like no volume, but nonetheless, evidently there was a little GPU capacity out there that I could get and it cost me like $5 or something for the whole thing given what you always hear about like a utilization is slammed. Why is it actually not that hard to find GPU capacity for someone like myself?
</details>

>> 我觉得核心就在于规模上的差异。找几块或者几十块 GPU，在市面上获取的门槛要低得多。

<details><summary>Original English</summary>
>> You know, I I I think it's uh the scale difference right there. finding ones or tens of GPUs. I think that's way more accessible out there.
</details>

>> 明白。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 我们的客户关注的则是成千上万块、数十万块 GPU。

<details><summary>Original English</summary>
>> Our clients are focused on the hundreds of thousands of of GPUs.
</details>

>> 我还没达到那个规模，不过还没达到而已。

<details><summary>Original English</summary>
>> I'm not there yet, but I'm not there yet.
</details>

>> 还没达到。我相信以后会达到的，是的。而这正是算力随着规模扩大而逐渐失去大宗商品属性的地方，对吧？当你的需求达到数十万这个级别时，根本就没有那么多可以交付的集群，对吧？这种规模的部署屈指可数。但是要获取单块级别的 GPU 算力，我认为在市场上获取这种规格资源的能力要强得多。

<details><summary>Original English</summary>
>> Not yet. I'm sure it'll get there. Yes. And and that's where it kind of decommoditizes itself with scale as well, right? Like as you're in the hundreds of thousands component, there's just not that many deployments, right? It's handfuls of deployments at that size. Um, but getting access to ones of GPUs, I I think that there is a lot more ability to to go secure that that sizing in the market.
</details>

### 中国市场与数据中心选址阻力

>> 乔和我很快就要去香港了，我预计中国的人工智能会是一个热门话题。尽管你们没有直接参与中国市场，但你肯定对此有所思考，你会如何描述目前美国和中国市场之间的差异？

<details><summary>Original English</summary>
>> So Joe and I are heading to Hong Kong very soon and I expect that AI in China is going to be a big topic of conversation. How would you characterize I guess the difference between the US and the Chinese market at the moment? I'm sure this is something you think about even though you don't participate in the Chinese market directly.
</details>

>> 是的，这基本上是在向你征集我们去那边时可以向别人提出的问题。

<details><summary>Original English</summary>
>> Yeah, that that's asking for questions that we basically like questions that we can ask people when we're over there.
</details>

>> 是的，特蕾西，我大概率还是那句话：我们确实没有参与那个市场。我认为我们存在扩张的机会。正如大家所知，我们在加拿大和欧洲都有业务。我认为进一步向东扩展对我们来说很有意义，但我们在扩张方式上力求非常稳健。所以很遗憾，在那个特定市场的问题上我恐怕无法为你提供具体建议，但我想你们会遇到很多与在美国看到的相同情况，那就是对 AI 无法满足、永无休止的需求。就像我们总是一再回到的这个论点：在满足需求方面目前看不到任何解决办法，对吧？供应链方面存在太多阻碍，根本没有满足需求的路径，坦白讲，在短期甚至中期内都是如此。

<details><summary>Original English</summary>
>> Yeah, that that's likely going to be my response, Tracy, is like we just do not participate in that market. Um I think that there's opportunity for us to be expanding. As you guys know, we we operate in Canada, Europe. Um I think moving uh further east makes a lot of sense for us, but we're trying to be very methodical in the way that we expand. So I unfortunately I'm not going to be able to help you with specific questions in that market but I would imagine you're going to encounter a lot of the same things that you're seeing in the US which is just insatiable unrelenting demand for AI like you know we just kind of keep coming back to this is like there is no solution in sight for being able to satiate demand right there's just too many supply chain there's no path to solving demand. And in the near term or even the medium term frankly
</details>

>> 你提到——特蕾西刚才问了你关于土地使用的问题，你说这确实不是什么问题，但比如我们在 2023 年或者什么时候第一次跟你交谈时，全美并没有出现一场声势日益壮大的反对数据中心的运动。也许当时有一些边缘群体，但这绝不是政治家和活动人士等会关注的事情。而现在你确实能看到一些头条新闻，提到某些项目确实被搁置了。比如有一个大项目——北弗吉尼亚州是这方面的一个巨大热点地区——由于未能与当地政府达成协议，一个大项目直接被叫停了。那……

<details><summary>Original English</summary>
>> you mentioned so Tracy asked you about land use you said you weren't that really was an issue but like the first time we talked to you in 2023 or whenever that was there was not a major growing movement of people who were just like anti-data centers in America. Maybe there were a few fringe people but it was not something that was on the minds of politicians and activists and so forth. And you do see these headlines, you know, about some projects really having been shelved. There was like a big one, Northern Virginia is a huge hot spot for it, and there was a big project that was they pulled the plug on due to some they couldn't get an agreement with the local government. That
</details>

<!-- chunk 6/6 -->

一定对你们产生了影响。就你们的建设能力而言，你们看到了什么？具体来说，鉴于这种情况发生了怎样的变化，或者说你们看到变化了吗？如果这从未成为一个政治热点问题，你们在这样一个世界里能否建设得更快？

<details><summary>Original English</summary>
must have affect you. What are you seeing in terms of like your capacity to build? How has it changed specifically in light of or have you seen a change? Would you be able to build faster in a world where this had never become a political hot button issue?
</details>

>> 我认为它确实已经变成了那样一个热点问题。这是我们在市场上相当积极应对的事情。嗯，而且我认为你就是得走一遍尽职调查流程的核查，以确保你执行得当。我、我认为外界存在一些误解，比如用水量。

<details><summary>Original English</summary>
>> I believe it has become that hot button issue. It's something that we're quite proactive about in market. Um, and I I think you just kind of go through the checks on the diligence process to make sure you're going through it correctly. I I think that there's misconceptions out there like water usage.
</details>

>> 是的。先抛开误解——先抛开，我知道，先抛开整个关于……的争论，但仅就运营层面而言，就……而言，这对你们改变了什么？

<details><summary>Original English</summary>
>> Yeah. Setting aside the misconcept like setting aside I know setting aside the whole debate about but just in terms of like operationally what's it changed for you in terms of
</details>

>> 不，我、我会说我们最大的挑战仍然只是交付我们的，比如施工建设和所有这些东西，把一切运送就位——比如那真正更是当今市场上的瓶颈所在。

<details><summary>Original English</summary>
>> No I I would say our greatest challenge is still just getting that delivery of our like the construction and all the things and getting everything in there like that is truly more of the bottleneck that's in the market today.
</details>

### 尾声与算力商品化讨论

>> 布兰登（Brandon），非常感谢你重返 Odd Lots。我们下个月会请你再来谈另一个市场。不，或者至少，也许三年后再来。

<details><summary>Original English</summary>
>> Brandon, thank you so much for uh coming back on OddLogds. We'll uh we'll have you back uh next month for another uh market. No. Or at least or maybe in three years.
</details>

>> 可别三年。

<details><summary>Original English</summary>
>> Not three years.
</details>

>> 一年。是的。可别三年。不过真的——

<details><summary>Original English</summary>
>> One. Yeah. Not three years. But uh really
</details>

>> 那可太漫长了。

<details><summary>Original English</summary>
>> that's an eternity.
</details>

>> 是啊，我知道。

<details><summary>Original English</summary>
>> Yeah, I know.
</details>

>> 非常感谢。

<details><summary>Original English</summary>
>> Thank you so much.
</details>

>> 谢谢大家。非常感谢。

<details><summary>Original English</summary>
>> Thanks, guys. Appreciate it.
</details>

我对于算力期货是否会兴起感到非常兴奋。我觉得这是一个令人兴奋的故事。你知道，它不是世界上最重大的事件，但它确实是一个非常令人兴奋的故事。

<details><summary>Original English</summary>
I'm very excited about whether compute futures will take off. I think this is an exciting like story. You know, it's not the biggest story in the world, but it is actually a very exciting story.
</details>

>> 我之前就说过这一点，即使你对人工智能没那么感兴趣，这也是一个非常有趣的市场结构故事，对吧？它基本上是一个全新市场的诞生，并提出了关于你如何做到这一点的所有这些有趣的哲学问题。而且我认为——

<details><summary>Original English</summary>
>> I've said this before, even if you're not that interested in AI, this is a really interesting market structure story, right? It's basically the creation of a brand new market and poses all these interesting philosophical questions about how you do that. And I thought
</details>

>> 布兰登关于可替代性的观点。我是说，那是一个真正的——

<details><summary>Original English</summary>
>> Brandon's point about fungeibility. I mean, that is a real
</details>

>> 问题。而且目前看来这确实是一个很难解决的难题。我不知道它在未来是否不可避免，但谁知道呢？

<details><summary>Original English</summary>
>> issue. And it does seem like it's a challenging one to fix at the moment. I don't know if it's inevitable in the future, but who knows?
</details>

>> 不，不。我是说，这非常有道理。这也是路易斯·哈特（Lewis Hart）的观点，嗯，这就好比……你知道，就在大宗商品（commodity）这个词本身里面，对吧？如果它、如果它不是一种大宗商品，你就无法为它形成大宗商品市场。当然，许多机构都在押注它将被商品化。但如果事实确实如此——比如你知道，它们正变得越来越难以操作，对推理提供商、对数据中心的技术要求希望能变得越来越高，以便压榨出最大化的……你知道，潜能，那么也许它就不会被商品化。但我认为那确实是一个非常吸引人的问题。

<details><summary>Original English</summary>
>> No, no. I mean, it makes a lot of sense. This was also Lewis Hart's point um that it's like the f you know it's in the word commodity right if it's if it's not a commodity you're not going to get a commodity market for it and of course a number of entities are betting that it will be commoditized but if the if it's true that like you know they're getting more difficult to work that the technical demands on the inference provider on the data center hopefully are getting greater in order to get the maximum, you know, juice, then maybe it doesn't become commoditized. But I think that's like a fascinating question.
</details>

>> 比如如果你确实看到了那些效率提升和新设计之类的事情，你就可以想象，对标准化 GPU 的需求也是存在的。所以我不知道，我真的很纠结。感觉它两种走向都有可能。嗯，甚至在他的回答中，他也谈到了他们是如何按照很大程度上由英伟达（Nvidia）自己提出的规格来配置他们自己的 GPU 的。

<details><summary>Original English</summary>
>> Like if you do see those efficiency improvements and new designs and things like that, you could imagine that like the demand is there for a standardized GPU as well. So I don't know like I'm really torn. It feels like it could go either way. Well, and even in his answer, he talked about how they configure their own GPUs to a spec largely that Nvidia itself has come up with.
</details>

>> 所以在理论上，比如存在每个人都能对齐匹配的规格。所以那真是一个非常有趣的、那真是一个非常有趣的问题。我还非常想深入探究所有这些芯片。谷歌有 TPU，亚马逊有 Trainium，微软有自己的硬件。也许连简街（Jane Street）和哈德逊河交易（Hudson River Trading）这类机构也会拥有它们自己的硬件。如果它们没有——比如我很想更好地理解为什么，对吧？因为它们大概是有某种理由的，而且它们——至少比如微软会说，好吧，这在我们的定制硬件上会运行得更好。我想理解为什么会这样。在性能上有多大差距？然后用户对非英伟达芯片的需求在多大程度上能够具现化，确实是一个非常重大的问题。

<details><summary>Original English</summary>
>> So in theory like there is spec that everyone can match to. So that's like a really interesting that's really an interesting question. I also really want to do more on all of these. So Google has TPUs, Amazon has Tranium, Microsoft has its own hardware. Maybe even Jane Streets and the Hudson River Tradings will have their own hardware. If they're not like I want to understand better why, right? Because like they presumably have some reason and they at least like the Microsoft will say, well, this will run better on our customized hardware. I want to understand why that would be. How much difference in performance is there? And then the degree to which demand materializes from users for non- Nvidia silicon is like a really big question.
</details>

>> 是的。为什么要做定制芯片？

<details><summary>Original English</summary>
>> Yeah. Why custom chips?
</details>

>> 是的。如果你将模型和芯片进行调优以实现协同最佳运行，你能从中获得什么？我完全不知道，但我感觉这是我想要做的一期节目。

<details><summary>Original English</summary>
>> Yeah. And what can you get out of that if you align model and chip to optimally work together? I have no idea, but I feel like it's an episode I would like to do.
</details>

>> 是的，我们应该做。好了。在此期间我们先聊到这里好吗？

<details><summary>Original English</summary>
>> Yeah, we should. All right. Shall we leave it there in the meantime?
</details>

>> 先聊到这里吧。

<details><summary>Original English</summary>
>> Let's leave it there.
</details>

>> 好的。这又是《Odd Lots》播客的一期节目。我是特蕾西·阿洛威（Tracy Alloway）。你可以在 @TracyAlloway 关注我。

<details><summary>Original English</summary>
>> All right. This has been another episode of the All Thoughts Podcast. I'm Tracy Aloway. You can follow me at Tracy Aloway.
</details>

>> 我是乔·韦森塔尔（Joe Weisenthal）。你可以在 @TheStalwart 关注我。关注我们的嘉宾布兰登·麦克比（Brandon McBee），账号是 @BrandonMcB。关注我们的制作人卡门·罗德里格斯（Carmen Rodriguez），账号是 @CarmenArman；达谢尔·贝内特（Dashel Bennett），账号是 @Dashbot；凯莱布·布鲁克斯（Caleb Brooks），账号是 @Kalebrooks；以及凯文·洛萨诺（Kevin Lozano），账号是 @KevinLloydLozano。若想获取更多 Odd Lots 内容，请访问 bloomberg.com/odd题目 查阅每日简报并收听我们所有的节目。你还可以在我们的 Discord 上全天候 24/7 畅聊所有这些话题，地址是 discord.gg/odd题目。如果你喜欢 Odd Lots，如果你希望我们做一期关于定制芯片的节目，请在您最喜爱的播客平台上给我们留下好评。请记住，如果您是彭博订阅用户，您可以完全免广告收听我们所有的节目。您只需在 Apple Podcasts 上找到彭博频道，并按照那里的指引操作即可。感谢收听。

<details><summary>Original English</summary>
>> And I'm Joe Weisenthal. You can follow me at the stalwork. Follow our guest Brandon McB at Brandon McB. Follow our producers Carmen Rodriguez at Carmen Arman Dashel Bennett at Dashbot Kalebrooks at Kalebrooks and Kevin Lozano at Kevin Lloyd Lozano. And for more OddLots content, go to bloomberg.com/odlots for the daily newsletter and all of our episodes. And you can chat about all these topics 24/7 in our Discord, discord.gg/odlotss. And if you enjoy OddLotss, if you want us to do an episode on custom chips, then please leave us a positive review on your favorite podcast platform. And remember, if you are a Bloomberg subscriber, you can listen to all of our episodes absolutely adree. All you need to do is find the Bloomberg channel on Apple Podcasts and follow the instructions there. Thanks for listening.
</details>