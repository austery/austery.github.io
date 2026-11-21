---
author: a16z
date: '2026-11-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LI3lxzHfRrU
speaker: a16z
tags:
  - ai-infrastructure
  - data-center
  - mergers-and-acquisitions
  - semiconductor
  - networking
title: 对话 Mike Volpi：AI 算力基建是否会重演互联网泡沫？
summary: 前思科高管 Mike Volpi 结合 90 年代互联网浪潮与并购经验，对比了当前 AI 算力基建周期。他认为底层算力资产具备长期价值且会被充分利用，但行业可能面临经济层面的调整与重组；同时就芯片供需、光电网络演进、系统级架构以及并购整合策略展开了深入分析。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Mike Volpi
companies_orgs:
  - Cisco
  - Nvidia
  - Google
products_models: []
media_books: []
status: evergreen
---
### 引言与背景对比：互联网浪潮与 AI 基础设施建设

>> 我们生活在一个对 AI 算力 token 的需求近乎无限、而供给极其受限的世界。换句话说，我们都生活在黄仁勋（Jensen）的世界里。当年你曾在这个星球上最有价值的公司负责并购业务。
<details><summary>Original English</summary>
>> we live in a world where demand for AI capacity tokens is near infinite and supply is incredibly constrained. So, another way to put it is we all just live in Jensen's [music] world. You were doing back then M and A for the most valuable company on the planet.
</details>

>> 回顾思科当时行之有效的并购流程，我认为关键在于我们不怕失败，而且我们的并购频率足够高，以至于能够捕获几个离群的高回报案例。你花 5 亿美元买下某家公司，两年后它就能带来 10 亿美元的收益。
<details><summary>Original English</summary>
>> The retro on the M and A process that I think worked well for Cisco was we were not afraid to fail and we did it with high enough frequency that we got a few outliers. You bought this thing for 500 million and like it's doing a billion in earnings two years later.
</details>

>> 当你看到如今的 AI 建设时，你如何回顾以往的经历？
<details><summary>Original English</summary>
>> When you see the AI build out, how do you look back on your previous experiences?
</details>

>> 如果你看 Anthropic 和 OpenAI 的营收爬坡曲线，它们经历的增长率确实远优于我们当时所见的情况。我认为现在正在进行的建设是有用的、并且会被充分利用乃至超额利用吗？100% 确定。但它将来还会属于今天拥有它的这批人吗？
<details><summary>Original English</summary>
>> If you look at the revenue ramp of Anthropic, OpenAI are definitely experiencing growth rates that were far superior to what we saw at the time. Do I think the build out that's happening now is useful and will be fully utilized if not more? 100%. Will it be owned by the same people that own it today?
</details>

>> 很高兴邀请你来到播客，Mike。这是一个非常非常及时的时刻，因为当年你在思科时是宏大互联网建设的架构师之一，而如今当然又迎来了巨大的 AI 建设浪潮。所以，Viro、我和听众们都很想听听你对当年与现在在各个维度上的看法，从实际建设、资本运作到技术差异等等。那么，为了让那些不了解或不记得的人有所了解，我们先介绍一下：Mike 曾在 90 年代末担任思科高级主管，负责思科的大量并购与战略举措，而那正是互联网蓬勃发展的时期。Mike 身处这一切的中心。因此，我们显然从这里开始。当时你见证了互联网的腾飞，然后大家争先恐后投入很多事情，行业竞相建设大量带宽等等，这些在一段时间内没有发挥作用，但后来证明其实是建得太少了，对吧？这与现在发生的事情有一些松散的相似之处。所以当你看到现在的 AI 建设时，你如何回顾你以前的经历？
<details><summary>Original English</summary>
>> Great to have you here on the podcast, Mike, and it is a very very opportune time to have you because you were one of the architects of the great internet build out when you were at Cisco and now of course you've got the great AI build out happening. So, Viro and I and the audience would love to get your thoughts on then and now from all different dimensions from the actual build out, the capitalization of it, the technology differences, etcetera, etcetera. So, so let's start for those that don't know or remember. Mike was a senior exec at Cisco overseeing a lot of the M and A and strategic moves that Cisco made in the late '90s [snorts] and of course that was the time the internet got built out. So, Mike was in the middle of all of it. So, clearly that let's start from there. So, you were there when the internet started taking off and then you guys rushed into to a lot of things and the industry rushed to build a lot of bandwidth, etc. etc. which for some time was not useful and then it turned out it was actually too little, right? And there are some loose similarities to what's going on now. So when you see the AI build out, how do you look back on your previous experiences?
</details>

>> 首先，能和在座的两位传奇人物坐在一起绝对是我的荣幸，无论是你 Ragu，还是 Guido——Guido 和我至少共事过一次。所以能来这里太棒了。正如你所说，这是一个有趣的时刻，因为你知道，历史不会重演，但往往押着相同的韵脚。
<details><summary>Original English</summary>
>> Well, first of all, it's an absolute privilege to be here with two legends here, both you Ragu and and in the case of Guido and I we got the chance to work together at least once. So so it's fantastic to be here and as you said, an interesting time because you know, history doesn't repeat itself, but it definitely rhymes.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

### 90 年代网络基建与当今 AI 算力的核心差异

>> 所以，是的，确实有一些相似之处。回顾 90 年代末建设期的一些观察，并对比哪些可能适用于当今世界、哪些不适用，也许会很有参考价值。当时类似的主题之一是，我们正在构建被称为互联网和 Web 的技术，以及运行在互联网上的一切。我们预期这将给世界带来巨大的变革，并且构想了各种各样最终将从这种建设中极度受益的应用。这些应用涵盖了不同的媒体类型，对吧？最初我们只有图片和文本，然后有了音频，再有了视频，接着有了高清视频；还有像电子商务、社交网络这样的应用，所有这些都在 90 年代被构想出来，但当时并不存在。与此并行的是，需求出现了非常大的激增。至少，对连通性的需求激增，
<details><summary>Original English</summary>
>> So so so yeah, there are some similarities. Maybe useful to give some context on some of the observations of the late '90s build out and what some of those things might apply in today's world versus not. Some of the kind of similar themes was that we we were building out this technology called the internet and the web and all the things that wrote on the internet. We had expectations that this would be massively transformative to the world and we imagined a wide range of applications that would ultimately massively benefit from this build out. Applications were different media types, right? So first we just had pictures and text and then we had audio and we had video and then we had high quality video, applications like commerce, applications like social networking, all of these things were imagined in the '90s but didn't exist. In parallel with that, there was a very big surge in demand. At a minimum, there was a surge in demand for connectivity
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 在此之上，对带宽的需求也出现了相当大的激增。与此同时，大量资本以股权和债务两种形式涌入。如果你回顾当时发生的事情，首先，在带宽领域，特别是在光纤带宽领域，带宽容量增长的单元和递增方式与算力有很大不同。这是因为我们发明了波分复用（WDM）技术，本质上就是取一根光纤，过去你可能只能在上面跑 1 Gbps 或 10 Gbps，但通过在同一根光纤中输入更多颜色的光，你现在可以拥有 40 倍或 80 倍的容量。因此，随着技术变革的到来，容量急剧增加。这与算力实际不同，因为算力最终受类似于摩尔定律的规律约束。所以算力提升的步伐……更平缓一些。虽然难以置信，但算力增长的步伐实际上比当年的带宽增长更为克制。另一个我认为不同的因素是，我认为当今 AI 的实际适用性高于当时网络带宽的实际适用性。
<details><summary>Original English</summary>
>> and on top of that a reasonable surge in demand for for bandwidth. And in parallel with that, there was a great influx of capital of two shapes and forms, equity and debt. So uh if you back at sort of what happened, first of all, in in the bandwidth world, uh in particular in fiber optic bandwidth, the elements, the increments of increase of the amount of bandwidth are quite different than compute. That's because, you know, we invented this technology called WDM that essentially takes a piece of fiber and said if you used to put, you know, 1 gigabit on there or 10 gigabits on there by putting in more colors of light in in that same piece of fiber, you can now have 40 times or 80 times that capacity. So essentially capacity increased quite dramatically with the advent of technological change. That's actually different cuz compute ultimately is bound by something that resembles Moore's Law. So the pace of improvement uh uh is is more more moderated. Hard to believe, but it is actually more moderated in compute than it was at the time. Uh and the other component that is I think different is that the practical applicability of AI, I believe today is higher than the practical applicability at the time of network bandwidth.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yep.
</details>

>> 这体现在了各家提供商的营收爬坡曲线上。如果你看 Anthropic、OpenAI 的营收增长——我不知道 Google 内部的具体数据是多少——甚至像 Fireworks、Together、Model 等开源模型提供商，绝对都在经历极高的增长率，也许利润率不尽相同，但增长率肯定远超我们当时所见。
<details><summary>Original English</summary>
>> Uh and that represents itself by the revenue ramp of the providers. So if you look at the revenue ramp of uh Anthropic, OpenAI, I don't know what the numbers look like within within Google, uh even the providers of the open source models like Fireworks, Together, Model, etc. etc. are uh definitely experiencing growth rates, maybe not quite at the same margins, but certainly growth rates that were far superior to what we saw at the time.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yep.
</details>

### 底层资产的长期价值与所有权更迭

>> 那么接下来会发生什么呢？在某个时刻，市场会受到冲击，发现一些基于互联网建立的商业模式不够好，接着这种冲击波及整个行业，最终那些负债最重的参与者破产了。现在值得注意的是，那些债务购买的资产是光纤电缆。事实证明，这些资产在未来是非常有用的，
<details><summary>Original English</summary>
>> Now uh then what happens? Uh uh at some point there's a shock that some of these businesses that are built on the internet are not good enough uh and then that ripples through the industry and ultimately the players that were most saddled with debt went bankrupt. Um now it's interesting to note that that debt was buying assets, was fiber optic cables. And those assets actually turned out to be quite useful in the future,
</details>

>> 确实如此。
<details><summary>Original English</summary>
>> Exactly.
</details>

>> 只不过它们由其他人来运营了，因为破产的那批人已经无法再拥有它们。
<details><summary>Original English</summary>
>> except they were operated by somebody else because the guys that went bankrupt didn't have them anymore.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以，首先要认识到的是，当时作为带宽建造的底层资产——我推测这次的算力也是如此——
<details><summary>Original English</summary>
>> So, uh, the first thing to recognize is the underlying assets that were built at the time as bandwidth and I suspect this, you know, compute this time,
</details>

>> 算力周期，是的。
<details><summary>Original English</summary>
>> cycles, yeah.
</details>

>> 它们将是有用的。毫无疑问它们会有用。但它们是否仍由同一批公司所有，是一个有趣的经济学问题。所以，说了这么长的一段回答，回到核心：我认为目前正在进行的建设是有用的、并且会被充分利用甚至超额利用吗？100% 确定。它将来还会属于今天拥有它的这批人吗？这里面存在很多有趣的依赖关系，而且有很多因素实际上不在控制范围之内，因为它们涉及宏观经济、地缘政治等等，确实超出了建设者本身的控制。尤其是当我谈到建设者时，有些参与者的资产负债表相当健康；但上次我与英伟达的人交流时，统计显示有 200 家新云厂商（Neo Clouds），而这些公司的资产负债表可并不好看。
<details><summary>Original English</summary>
>> it'll be useful. There's no question that it'll be useful. Whether it will be owned by the same companies or not is an interesting economic question. So, you know, that's a long-winded answer to say, do I think the build out that's happening now is useful and will be fully utilized if not more? 100%. Will it be owned by the same people that own it today? A lot of interesting dependencies and a lot of things that in fact are outside of the control because they're they're macroeconomic and geopolitical and so forth. It's really outside of the control of the builders themselves. And in particular, when I talk about the builders, uh, you know, some of the balance sheets are pretty healthy, right? Last count when I was talking to folks at NVIDIA, there are 200 Neo Clouds and those balance sheets are not good.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 所以我推测，我预测市场会出现某种程度的经济修正，有些表现会好于另一些，但总体而言我预期市场会出现经济调整，而底层资产在很长一段时期内都将是非常有用的。
<details><summary>Original English</summary>
>> So, so, I'm going to guess that there's, uh, I I'll predict that there'll be some Yeah, yeah. Some of them better than others, but broadly I expect that there will be an economic correction uh, in the market, uh, but the underlying assets will be quite useful for a long period of time.
</details>

>> 与当年的另一个巨大区别，难道不是现在的规模要庞大得多吗？我的意思是，当年我们在互联网基础设施上的投资只占微不足道的百分之零点几。而今天，我们在 AI 基础设施上的投资大约占到了 GDP 的 2%，对吧？
<details><summary>Original English</summary>
>> Isn't that one other big difference from how it was back then, which is that everything is now much much larger? I mean, back then we were investing a small fraction of a percent in in infrastructure for for the internet. Today we're investing 2% or so of our GDP, right, in in AI infrastructure?
</details>

>> 是的。确实庞大得多，但这是一个很有意思的概念，对吧？因为从十万英尺的高空抽象来看，正在建设的到底是什么？当年建设的是通信；今天我们建设的是智能。而智能的经济价值可能高于通信的经济价值。
<details><summary>Original English</summary>
>> Yeah. Uh, well, it is much bigger, but it's an interesting concept, right? Because in the 100,000 ft abstraction, what is it that is being built, right? Back then, it was communication that was being built. Today, we're building intelligence. And the economic value of intelligence is probably higher than the economic value of communication.
</details>

>> 很有可能，是的。
<details><summary>Original English</summary>
>> Probably, yeah.
</details>

>> 对吧？所以我觉得这并不令人意外。另外我认为，信不信由你，距当年已经过去了近 30 年，现在的市场效率更高了，对吧？这就是为什么有如此多的风险资本愿意进入 AI 领域，而当年这些资本甚至无法进入。所以总结下来，我对这一轮周期实际上更乐观，但我也相信会出现一些调整，行业结构也会发生一些清理整合。
<details><summary>Original English</summary>
>> Yep, right? Um so uh so so I think it's it's unsurprising. I also think that that believe it or not, I mean it's been nearly 30 years, the markets are more efficient now, right? Which is why so much more risk capital is willing to make its way uh into AI which, you know, uh even back then uh was not able to. So net is I'm actually more optimistic about this cycle, but I also believe that there will be some correction and some cleaning up of the industry structure.
</details>

>> IT 的地位也极大地提升了，对吧？当年在 90 年代末，PC 虽然算常见但并非无处不在。今天，可以说是软件吞噬了世界，对于任何一家企业来说，IT 都是其业务极其核心的组成部分，而——
<details><summary>Original English</summary>
>> The role of IT has also massively increased, right? Back then, I mean in the late '90s PCs were were somewhat common but but not ubiquitous. Today, Yeah. so to speak, software has eaten the world and it's sort of for any company out there, so it's a very central part of what they do when
</details>

>> 智能分发的成本以及——
<details><summary>Original English</summary>
>> Cost of distribution of intelligence and
</details>

>> 哦，那是肯定的。而且不仅是任何公司，就像 70 亿人的口袋里都揣着一台超级计算机。
<details><summary>Original English</summary>
>> Oh, for sure. And not just any company, but like, you know, 7 billion people have a super computer in their pocket.
</details>

>> 是的，确实如此。
<details><summary>Original English</summary>
>> Yeah, exactly.
</details>

>> 所以对于所产生的底层效益，其消费分布要广泛得多。
<details><summary>Original English</summary>
>> So so you know, there's there's you know, there's much more evenly spread uh consumption of of the the underlying benefit that's being produced.
</details>

>> 是的。我记不太清 90 年代和 2000 年代初的所有财务权衡了。在金融方面，这里最近对系统造成冲击的显然之一是利率上升，以及资本规模让人们惊呼：“这会挤占其他一切投资，我们甚至可能没有足够的资本。”在当年的带宽和互联网建设期间，情况并非如此，对吧？当时并没有利率的骤然上升，是这样吗？
<details><summary>Original English</summary>
>> Yeah. Uh don't fully recall all the puts and takes in the '90s and the early 2000s. [sighs and gasps] On the financial side, here obviously one of the recent shocks to the system was the rising interest rates Mm. and the scale of capital causing people to say, hey, this is going to crowd out everything else and we may not even have enough capital. During the bandwidth build out and the internet build out, that was not the case, correct? There was no sudden increase in interest rates, was it?
</details>

### 资本结构、设备使用寿命与稀缺性动态

>> 不，当时并没有利率的大幅上涨。存在几个重大差异：其一，按比例来看，我认为当时更多的资本来自设备供应商的资产负债表，而不是像今天这样。如今的建设更多是由资本市场驱动的，包含私募债权、公开市场股权等等。虽然有英伟达的供应商融资——我不确定这种称呼合不合适，但它看起来确实很像［笑声］——有一点那样的成分，也存在一些企业融资，但主要是股权融资。
<details><summary>Original English</summary>
>> No, there wasn't a massive increase in interest rate. There was a couple of big differences, right? One one is that more, I would say on a proportional basis, I believe more of the capital came from the balance sheet of the equipment vendors than today. Today it's a more uh capital markets driven uh build out. So it you know it's private debt, it's public equities, etc etc. There is NVIDIA vendor I don't think you're supposed to call it vendor financing, but it looks a lot like it. [laughter] Uh so there's a there's a little of that but uh and there's some corporate financing, but it's largely equity.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而且它不与具体的设备采购等强行绑定。所以我认为现在的资本结构稍微干净一些。不过有一点我认为有趣的是，90 年代的情况在于，大量资金以光纤的形式埋入地下，而当你把光纤埋入地下后，它能保持很长很长的时间，可以使用 20 到 30 年。而我认为当下的决定性因素之一是：你投入部署的算力，它的实际使用寿命到底有多长？我认为这是一个引人入胜的现象，因为这种算力的主导部分是芯片，也就是 GPU。那是——
<details><summary>Original English</summary>
>> Uh and it's not tied to specific equipment purchases and so forth. So I'd say the capital structures are a little cleaner now. Um the the one thing that I think interestingly though favors the 90s is a lot of the money went into the ground in the form of fiber optic and when you put a fiber optic in the ground, it's good for a long long time. It's like it's a usable asset for 20 30 years. The I I think one of the deterministic factors is the compute you put in the ground, what is its actual life? And I I this is a fascinating phenomenon, right? Because the dominant part of that compute is is is chips. It's it's it's GPUs. That's the
</details>

>> 占比达到相当高的比例，是的。
<details><summary>Original English</summary>
>> plus percent, yeah.
</details>

>> 是的，那是其中很大一部分，对吧？我还记得以前人们对 Hopper、H100 感到兴奋的时候，当时他们认为，好吧，它也许有五年的使用寿命，按每 GPU 小时 1.82 美元左右出租。那是四年前的事了。按理说这款芯片现在应该停用了，或者说接近报废。但实际上完全没有淘汰。
<details><summary>Original English</summary>
>> Yeah, it's the big chunk of it, all right? So I remember back when people were excited about Hopper, H100s, right? You were you're they were like, okay, well maybe it has a five year useful life and you're renting it out at a you know buck 82 per GPU hour, okay? And that was four years ago. So the chip should be defunct now, like near defunct. Not at all defunct.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 没有淘汰。
<details><summary>Original English</summary>
>> No.
</details>

>> 不仅没有淘汰，它还能以更高的费率出租，租金达到了 2.5 或 3 美元。因此有趣的地方在于，我们原以为只有五年寿命的资产，部分由于 AI 自身的发展，其可用寿命延长了相当多。在那种背景下，如果你从事资产融资业务，而该资产最终拥有更长的使用寿命，你就是受益者，因为商业模式此前是基于特定年限构建的。所以从某种意义上说，我认为 AI 擅长编写软件带来了一个意想不到的后果，那就是底层资产的使用寿命正在变长，从而有助于其更易于获得融资。这是我在这一切起步时未曾预料到的有趣现象。
<details><summary>Original English</summary>
>> Not only that, it rents at a higher rate. It's a it's a 250 or three. So the the the kind of the interesting part is we thought this asset that have a five year life partly because of AI itself is a useful asset for quite a bit longer. And in that context I mean if you're in the business of financing an asset and that asset ends up having a much more longer useful life, then you're the beneficiary of that because your business models were constructed on a certain So, in some sense I I actually think this the the fact an unintended consequence of AI being good at software is that the underlying asset life is getting longer thereby helping it to be more financeable. And that's an interesting phenomenon that I didn't quite expect when this thing got underway.
</details>

>> 债权投资者尚未普遍接受 GPU 寿命延长的观点，但新云厂商显然深信不疑。
<details><summary>Original English</summary>
>> the investors are not the dead investors have not broadly accepted the extended life of a GPU, but the neo clouds clearly believe that.
</details>

>> 我不确定自己是否也接受了这一观点。我的意思是，目前看来主要发生的情况是我们面临着资产的极度稀缺。因此，即使是上一代产品依然价值很高，对吧？如果我们未来某天达到了 GPU 充裕的状态，情况可能会彻底改变，价格可能会回到过去的测算水平。
<details><summary>Original English</summary>
>> I'm not sure I'm not sure I have either. I mean like right now it seems what's mostly happening is that we have a massive scarcity of an asset. So, even previous generations are still worth a lot, right? If we ever get to a point where we have uh you know an abundance of of GPUs that might completely change. You might go You might go back to those numbers.
</details>

>> 是的。所以我认为关键指标是每瓦特能获取多少 token 收入，对吧？
<details><summary>Original English</summary>
>> Yeah. So, I think the key metric is is uh uh how much token revenue can you extract per watt, right?
</details>

>> 也许多半如此，是的。
<details><summary>Original English</summary>
>> Maybe, yes.
</details>

>> 所以 Hopper 会比 Blackwell 差很多，而 Blackwell 又会比 Vera Rubin 差很多，对吧？它们在将每瓦特转化为美元方面的效率都在提高。因此理论上，在某个时刻当你拥有足够的 Vera Rubin 时，继续运行 H100 就毫无意义了，因为把电力转化为美元的效率实在太差。
<details><summary>Original English</summary>
>> So, the the hopper is going to be a lot worse than Blackwell is going to be a lot worse than Vera Rubin, right? They're all just more efficient at getting dollars out of a watt. So, in theory at some point when you have sufficient Vera Rubins it doesn't really make sense to run H100s anymore because like it's just a worse way of converting electricity into dollars.
</details>

>> 确实如此。
<details><summary>Original English</summary>
>> Correct.
</details>

>> 对吧？但目前的问题在于需求太旺盛，即使瓦特到美元的转换率很低，你依然会使用该资产。眼下这种稀缺性非常显著，而且归根结底——也许我们稍后会在对话中讨论到这点——这种稀缺性终究存在于半导体本身的制造环节。而这一点短期内看起来不会改变。
<details><summary>Original English</summary>
>> Right? But the problem is right now that the demand is so high that even if the watt to dollar conversion is low, you're going to still use the asset. So, uh and right now the scarcity is so significant and ultimately you know at some point in the conversation maybe we get there, but ultimately the scarcity is in the manufacturing of the semiconductor itself. And that doesn't look like it's changing anytime soon.
</details>

>> 没错，确实。
<details><summary>Original English</summary>
>> Correct, yeah.
</details>

>> 只要稀缺性持续存在，资产的使用寿命就会继续保持较长。
<details><summary>Original English</summary>
>> And so then scarcity persists, then the life of the asset continues to be long.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我想这是对的。
<details><summary>Original English</summary>
>> I think it's correct.
</details>

>> 是的。另一个重大区别是，曾经有一段时间存在闲置未用的带宽。而今天，根本不存在闲置的 GPU，对吧？
<details><summary>Original English</summary>
>> Yeah. And the other big difference there was a period of time where there was unused bandwidth. Today there is no such thing as an unused GPU, right?
</details>

>> 确实存在一点未充分利用的能源；另外，我不知道我们稍后是否会聊到网络，但通过更好的网络，你可以从给定的 GPU 中榨取更多的算力（FLOPS）。
<details><summary>Original English</summary>
>> There's a There's a bit of unused energy and like you could probably you know I don't know if we're going to talk about networking, but with better networking you could get more flops out of a given GPU.
</details>

>> 是的，我刚才正想说，在某些特定用例和特定构建方式下可能存在微小的闲置因素，但总体上肯定是不存在的。
<details><summary>Original English</summary>
>> Yeah I was just going to say there are a few small factor in certain use cases and how the people have built it but but certainly generally not.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

### 思科高频并购复盘与对英伟达的启示

>> 回到你在思科的时期，当思科成为全球市值最高的公司时，你还在那里吗？
<details><summary>Original English</summary>
>> Back when you were at Cisco were you still there when Cisco was the most valuable company on the planet?
</details>

>> 是的，确实，我当时在。
<details><summary>Original English</summary>
>> I yes indeed I was there.
</details>

>> 所以你当时在为全球市值最高的公司操盘并购，而且回想起来效果非常不错，应该说——
<details><summary>Original English</summary>
>> So you were doing back then M and A for the most valuable company on the planet and it worked pretty well I want to say looking back right that's
</details>

>> 对此挺满意的，是的。
<details><summary>Original English</summary>
>> happy with it yeah.
</details>

>> 你对 2026 年的英伟达有什么建议？比如掌管英伟达并购业务的人，现在的处境与当年的你完全一样。
<details><summary>Original English</summary>
>> Um what would be your words of advice to Nvidia in in 2026 like that whoever runs M and A there isn't exactly the same spot as you are correct as you were.
</details>

>> Vishal 如今的处境和我当年一样。复盘我认为在思科行之有效的并购流程，其核心在于：我们愿意进行足够数量的收购，从而在这些收购中获得具有统计显著性的结果。这意味着有些案例表现极佳，有些表现平平，有些则完全失败。如果把它们划分为三个板块，大约三分之一非常成功，三分之一表现平庸，三分之一彻底失败。我们具备的优势在于不害怕失败，而且我们的收购频率足够高，从而捕捉到了一些极具爆发力的特例，比如 Mario Mazzola 的公司等一系列标的，对我们来说带来了类似风险投资般的超额回报。你花 5 亿美元买下它，两年后它就能产生 10 亿美元的利润。
<details><summary>Original English</summary>
>> Vishal Vishal's in the same spot I am. Um look the the retro on the M and A process that I I think worked well for Cisco was that fundamentally uh we were okay with making enough acquisitions that we got a statistically significant outcome on those acquisitions meaning some worked really well some worked so so some didn't work at all. And you know if you kind of drew it out one in one in each of those three sectors a third of them worked really well a third of them were whatever and a third of them failed. Um the benefit that we did is we were not afraid to fail and we did it with high enough frequency that we got a few outliers uh and time's company uh Mario Mazzola's company uh a bunch of these things that were sort of you know even for us were venture like returns. So you bought this thing for 500 million and like it's doing a a billion in earnings two years later.
</details>

>> ［笑声］太惊人了。
<details><summary>Original English</summary>
>> [laughter] That's amazing.
</details>

>> 最终的结果是，在我任职期间——我是 1994 年加入的，大概是唯一的业务拓展（biz dev）雇员——到了 2000 年，思科大约 50% 的收入来自并购整合的技术和资产。所以这极其有效。而且我们在单次收购上花费的资金实际上从未超过我们市值的 4% 或 5%。
<details><summary>Original English</summary>
>> And so it ended up that during the period that I was there by I joined in 94 and I was like the one biz dev hire in 2000 in 2000 roughly 50% of Cisco's revenue came from acquired sources. So that was incredibly useful and we actually never really spent much more on a given acquisition than four or 5% of our market cap.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 按照我们市值的标准来衡量，绝大多数收购实际上都算得上“便宜”。
<details><summary>Original English</summary>
>> Most of the acquisitions were actually quote cheap relative to our market cap standards.
</details>

>> 这对英伟达意味着什么？我甚至都不敢想象。
<details><summary>Original English</summary>
>> would that mean for NVIDIA? I don't even want to think about that.
</details>

>> 是的。我当时的基本逻辑是：如果你的股票在一天之内的交易额超过了你收购所支付的价格，那么你想做多少起收购都可以，没有任何人会在意。［笑声］
<details><summary>Original English</summary>
>> Yeah. Well my my rationale at the time was like if your stock trades more than the price you paid for the acquisition in one day, then you can do the acquisitions as many as you want. Nobody [laughter] nobody will care.
</details>

>> 那些交易全是用股票完成的吗，还是……？
<details><summary>Original English</summary>
>> And were all of them done with equity or was
</details>

>> 全部都是股票。几乎所有交易都是全股票支付，只有少数小额交易用了现金，但绝大多数全都是股票。
<details><summary>Original English</summary>
>> All all equity. Almost everything was equity. A handful of the small ones were cash, but it was all
</details>

>> 我的意思是，它们后来都成长为了主要产品线。所以这绝非仅仅是补充某个功能的小型嵌入式收购，而是演变成了全新的产品线，在某些情况下甚至成为了行业领先的产品线。
<details><summary>Original English</summary>
>> I mean they became major product lines. So it was not like this was a little tuck in that added a feature somewhere, but this was of a new product line that in some cases became leading product line in the industry.
</details>

>> 你们是搞网络出身的，所以会理解这一点：网络领域的收购与其他领域相比有一个不同之处，那就是网络运行在开放协议之上。这意味着我可以收购一家别人制造的交换机公司，由于所有协议都是开放的，它能立刻与我的交换机或路由器自由通信。虽然在思科我们拥有一些专有协议，但大体上像 OSPF、BGP、IS-IS、以太网交换、802 系列协议等都能通用。因此你可以立即把收购来的产品整合进销售团队，销售团队基本上只需要换个品牌标牌就能直接开卖。这让我们能够保持极高的推进速度。那么，这与当今黄仁勋的世界有何对比？首先，他们进行了一些非常高明的收购，比如 Mellanox，它如今是全球最大的网络公司。
<details><summary>Original English</summary>
>> Now you're networking guys, so you'll appreciate this. The one thing that's a little different about a networking acquisition versus other ones is that networking operates on open protocols, which means that I could buy a switch company made by somebody else and it immediately talks to my switches or routers whatever freely because all the protocols are open. So you know at Cisco we had a couple of proprietary protocols that we enjoyed, but by and large all the OSPF, BGP, ISIS, Ethernet switching, 802. whatever, they all worked. So you could immediately integrate the product into your sales team and have your sales team like literally you just change the badge on the thing. And so that allowed us to be like super high velocity. Okay, how does that contrast to to Jensen's world today? One, they've made some really clever acquisitions. You know like Mellanox is the world's largest networking company.
</details>

>> 是的，确实如此。
<details><summary>Original English</summary>
>> yes. Yeah, it was.
</details>

>> 对吧？这堪称神来之笔。现在他们也在进行其他收购，有时会让我挠头不解。例如，我并不完全明白收购 Hugging Face 是为了什么。也许背后有其逻辑，但我很难看透。不过我认为这无伤大雅，他们进行这些尝试并承担风险完全没问题。其中有些会起效，如果能达到像 Mellanox 那样的效果，那就太惊艳了；当然也有些不会奏效。我认为市场赋予了他们难以置信的期权价值（optionality），基本上他们想做什么就能做什么，而这正是他们承担这些风险的最佳时机。所以我认为他们做得很聪明，任何单笔收购你都可以去批评挑刺。相信我，当年在思科我也被无休止地批评过，比如我收购了 Stratacom，收购了 Cascade，还从 Velo 买了一家毫无下文的光网络公司等等。但归根到底，在我任职期间，我们团队大约完成了 70 起收购，这些收购转化为了公司一半的营收；当时我们的年营收达到了 300 亿美元，其中 150 亿美元来自并购业务。这项战略奏效了。我认为英伟达团队目前也正在践行这一策略。我觉得这很有意思，也很明智。至于他们在多大程度上对整个行业进行资本资助，我们拭目以待。
<details><summary>Original English</summary>
>> Right? It's like genius. Now they're making other acquisitions that sometimes I scratch my head. I'm not entirely sure what Hugging Face is all about, for example. Like, maybe there's a rationale. Hard to me to see it. I don't think it matters. I think it's fine for them to do some of these and take risk. And some of them will work. And if they work as well as Mellanox, holy cow. And some of them are not going to work. And I think the market has granted them a moment of incredible optionality. Right? Basically, they get to do whatever they want, which is the optimal moment for them to take these risks. So I think they're being very clever, and you can always critique any given acquisition. Trust me, I got critiqued endlessly at Cisco cuz I bought Stratacom and now Cascade, and I, you know, bought an optical networking company from Velo that went nowhere and whatever. But in the end, and you're like, all right, well, I did I did 70 I think our team did 70 acquisitions while I was there, and those turned into half the company's revenue, and we were doing 30 billion in revenue, so it was 15 billion in revenue. Uh the strategy worked. And I I think that I think that um uh the team Nvidia is is is is doing that. Um I think that's interesting and wise. The degree to which they are financing the industry, we'll see.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 因为那是不同的事情，对吧？从这个意义上说，英伟达基本上是在试图塑造行业的形态。
<details><summary>Original English</summary>
>> Cuz that's different, right? That that in that sense, Nvidia is basically I think they're basically trying to shape what an industry looks like.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 但我认为行业本身具有强大的内生力量，会演变出自身的格局，外界很难去强行重塑它。
<details><summary>Original English</summary>
>> And I think industries are powerful and they find their own shape. It's hard to reshape them.
</details>

### 生态塑造、并购整合与投后治理

>> 让我稍微为英伟达辩护一下。曾在英特尔待过，并亲眼目睹了大型超大规模云厂商（hyperscalers）如何基本上切断了英特尔与终端客户的直接联系，对吧？最终，他们能够造出比英特尔更好的芯片，仅仅是因为英特尔已经完全不知道客户在用这些芯片做什么了，对吧？我非常理解英伟达希望拥有超过三四个客户的心情。
<details><summary>Original English</summary>
>> Let me Let me Let me defend Nvidia a little bit. Having been at Intel and and having seen how the big hyperscalers essentially disintermediated Intel from the end customers, right? And at the end, they could build better chips than Intel just because Intel had no idea anymore what the customer was doing with the chips, right? I I I I have some sympathy for wanting to have more than three customers to sell to or four maybe, huh?
</details>

>> 我也深表理解。
<details><summary>Original English</summary>
>> As do I.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以你可以讨论什么是有效的资本配置策略：是把资本全部退还给投资者，还是在这个极具历史意义、可能绝无仅有的时刻，将其全额投入到未来的创新中，对吧？
<details><summary>Original English</summary>
>> So and you could argue what is an efficient allocation strategies and given it ball [gasps] back to investors or could it be at this time, which is probably once in a time in history put it all to work on future innovation, right? So
</details>

>> 我觉得你们两位说的都非常有道理。Guido，我想指出的是，一个行业之所以会形成特定的形态，是因为当它达到这种形态时，能创造出最大的效用和最大的经济价值。为什么只存在三家超大规模云厂商？因为这是一个规模效应至关重要的业务。
<details><summary>Original English</summary>
>> Well, I think both of you make very valid points. Um the thing I would say Guido is that an industry wants to look a certain way because when it does it creates maximum utility, maximum economic value. Why are there three hyperscalers? Because it's a business where scale matters.
</details>

>> 软件，是的。
<details><summary>Original English</summary>
>> Software, yeah.
</details>

>> 对吧？这是一个规模决定一切的行业，因此行业本身倾向于高度集中。无论你给小玩家提供多少资金支持，弱小者始终处于劣势。显然，如果你是英伟达，你不会喜欢这种局面；你不想只有三个客户，你想要 50 个客户。所以你资助他们，但到某个阶段他们还是难逃消亡。这只是因为只要是规模化行业，就必然走向整合。我们在美国可以资助 100 家航空公司，但最终你依然只会剩下三家。所以我的观点并不是说这是个坏主意，而是说这种努力终归是徒劳的。
<details><summary>Original English</summary>
>> Right? It's a business where like scale matters and therefore the industry wants to concentrate. The the no matter how much you finance them, the little ones are always weaklings. So and obviously if you're Nvidia, you don't like that. You don't want three customers. You want 50 customers. So you fund them, but at some point they're going to die. It's just that because the industry, whenever it's a scale business, wants to consolidate. You know, we could fund 100 airlines in America, but in the end you're going to have three. So my point is not that the not that it's a bad idea, it's just that it's futile.
</details>

>> 是的。［笑声］初衷是崇高的，但是……
<details><summary>Original English</summary>
>> Yeah. [laughter] So so noble intentions, but but
</details>

>> 针对你刚才提到的点，这可能带来非常好的回报。我不知道他们是否真正在意资本回报率，也许在意，如果他们能在合适的时间点退出的话——
<details><summary>Original English</summary>
>> Now to your point like it could be a very good return on I don't know if they I don't know if they actually care about the return on capital. They they they they they might and if they get out at the right time
</details>

>> 是的，这甚至无关资本回报。我同意这在某种程度上是在塑造行业形态。但另一方面，它确实推动了大量的创新，因为我们的初创公司和许多其他初创企业现在确实因此获得了宝贵的算力资源。
<details><summary>Original English</summary>
>> Yeah, it's not even about the return on capital. It's I agree it is it is to some degree shaping industries, I mean shaping the deciding the shape of the industry. But on the other hand it is enabling a lot of innovation as well because our startups and lots of other startups do get access to that capacity now.
</details>

>> 是的，确实如此。
<details><summary>Original English</summary>
>> Yeah, yeah, yeah.
</details>

>> 总体来说我理解他们为什么这么做，而且我们的许多公司也都是受益者。所以感谢你，Jensen。
<details><summary>Original English</summary>
>> No, no, look we're overall I get why they're doing it and and and you know many of our companies are beneficiaries of it. So you, Jensen.
</details>

>> 确实。［笑声］
<details><summary>Original English</summary>
>> Exactly. [laughter]
</details>

>> 在 VMware，我们完成的并购可能没有你那么多，但在公司的整个生命周期中大概也进行了 50 多次收购。当时的观察是：无论收购的是一家 20 人的公司，还是一家 2000 人的公司，在整合、文化、商业模式、销售团队等方面的投后整合工作量始终极其庞大。你们当时在思科是如何搞定这一切的？
<details><summary>Original English</summary>
>> So, um mean, at VMware, we did probably not as many as you did, but uh maybe 50 plus acquisitions over the full lifetime of the company. And the observation was whether it didn't matter whether you were acquiring a 20% company or a 2,000 person company, the amount of post-acquisition work in terms of integration, culture, business model, sales team, etc., etc., was all always a lot of work. How did you guys pull it off at that time at Cisco?
</details>

>> 好的。从架构上看，我们的做法是：我们有一支非常小的交易团队，人数少于 10 人，职责就是负责并购执行。同时我们有一支规模稍大的整合项目管理团队，他们拥有一套关于如何执行整合的规章和准则。这批负责项目管理的人员，与思科内部各个业务部门、事业部以及职能部门的同事协同配合。所以，关键是要认识到：企业擅长处理标准化流程，但非常不擅长处理一次性突发事件。因此，如果我们要进行大量的收购，就必须建立可重复的流程，能够一遍又一遍地执行，并且由一个中心化的团队来管理和推行这些流程。很多时候——思科早起也经常这么做——并没有正式指定负责人，往往就像这样：“Ragu，这是你的任务了，你去负责搞定那起整合，做完了告诉我一声。”对吧？然后你就会发懵：“我到底该从哪儿下手？”这曾是过去的常态，我们意识到这样不行。于是我们建立了这套流程，并且运转得非常出色。挑战出现的地方在于，我们习惯于收购小型标的，而随着整体业务规模变得极其庞大，小标的变得微不足道，对整体业务不再产生实质影响。后来当他们试图去收购更大的公司时——那是在我离开之后的事情了，因为我在 2000 年不再负责并购事务，转去掌管一个业务部门——他们开始收购体量更大的标的。然后就会陷入你刚才提到的困境：大型公司极难整合，它们存在了很长时间，有着根深蒂固的文化。比如我们收购了 Scientific Atlanta，那是一场灾难；还买了一堆其他东西，效果都不好。我们也陷入了“哦，我们不全面整合，只进行部分整合”的模式。
<details><summary>Original English</summary>
>> Um okay, structurally the way we did it was that we had a very small When I say small, less than 10 people uh deal team that was job was to acquire. And we had a somewhat larger uh integration project management team that had sort of rules and guidelines about how we did integrations. And uh they they had colleagues, those people that project managed it, had colleagues in the various business units and divisions and functional units within Cisco that collaborated with them. So the important thing to recognize there is that uh businesses, companies are good at processes. Uh they're very bad at one-time events. And so essentially, if we were going to do a large number of acquisitions, we needed to have repeatable processes that were uh performed over and over again. And we had a centralized group that was the administrator of those processes. Um more often than not, and in the beginning at Cisco we did this a lot, there was nobody that was formally assigned to this, so it'd be like, Ragu, it's it's it's your job, you you go have fun with that integration and let me know when it's done. Right? And you're like, where do I even start? You know? That was like the modality and we're like, okay, this is bad. So, we we created this process and it and it worked pretty well. Um, where it got challenging is we liked to buy small things and small things became too small to become significant to the overall business because the business got so big that like, you know, it just didn't make a difference anymore. And then when they tried to this was a little bit after my time because I I I stopped doing the M&A stuff in 2000 and switched over to running a business unit. But uh after my time they started buying bigger things. And then you get into the problem that you're talking about. Big things are very very hard to integrate. They have their they've been around a long time, they have a long culture, they like you know, we bought like Scientific Atlanta which was a disaster, we bought like a bunch of things that didn't work very well. We also got into the mode of like oh we're not fully integrating them, we're like partially integrating them.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这种模式往往效果不佳。所以换句话说，应对手段是建立制度流程；但当你不再遵守流程时，就会遭遇你提到的那些大麻烦。
<details><summary>Original English</summary>
>> Um, yeah it it doesn't work very well. So, um so you so in other words the mitigation is to have a process, but then when you stop respecting the process you do have big problems like you talked about.
</details>

>> 那么从被投企业的角度来看呢？我是说，你们有被投企业，我们也有被投企业，至少在最近的记忆中，我们经历过一些被其他大公司收购退出的案例。这里有两个问题：第一，如果你是被投企业的 CEO，你应该注意什么？第二，作为这些公司的董事会成员，你如今如何就退出问题向你的被投企业提供建议？
<details><summary>Original English</summary>
>> And what about from the portfolio company side? I mean you got portfolio companies, we got portfolio companies that at least in recent memory we have had some exits into being other large companies buying them. Two questions there. One is if you're a portfolio company CEO what would you watch out for, right? And then sitting on the boards of these companies, how do you advise your portfolio companies these days? About exits, about exits in general.
</details>

>> 当你在我们这个行业担任董事会成员，面临可能出售公司的机会时，通常有三种结果：第一种，公司发展极其顺利，此时尝试卖掉公司是个非常糟糕的主意，所以你要努力劝阻 CEO 千万不要卖。第二种，公司举步维艰，资金所剩无几，出售是一个体面的退出途径，所有人都能满意，那你就推动交易完成，组织并管理好出售流程。第三种，介于两者之间的中间状态。我们无法完全确定。我认为此时有几个重要的指标能帮助你决定该怎么做：首先是创始人、创始团队是否依然充满激情？他们是否还渴望继续拼搏？他们是否坚信自己能够跨越这个过渡期并迎来下一阶段的爆发？他们内心是否还渴望它？因为如果你的 CEO 或领军人物表现出：“哎，我也许该考虑退出了，我有点累了，这段路走得太漫长。”
<details><summary>Original English</summary>
>> Um, look you when you're when you're in our business of being on boards and you're facing a situation where you need to sell a you know, there was an opportunity to sell a business, it's one of three outcomes. One, your company's doing great and it's a really bad idea to try to sell it. So, then you try to convince the CEO no, don't do it. Two, the company's struggling, we don't have a lot of finances. It's a nice way to get out, everybody's happy, then you just help the deal happen. You sort of manage a process and do. The Then you have the tweeners. Uh we're not totally sure. And uh I think that there are a couple of important indicators that help you determine what to do in that moment. The first is does CEO, the founder, the founding team have the fire? Like do they want to do this? Do do they do they believe they can get through this sort of intermediary period and uh uh bust open into the next phase? Do they Do they want it? Because if you have a CEO or a leader that's kind of like, man, you know, maybe I should consider this. I'm a little tired. It's been a long haul.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 那就把公司卖掉，继续往前走。第二个因素是，你必须保持客观冷静地判断：这未来会成为一个足够有吸引力的业务吗？不是看它能否在现有基础上翻倍——因为归根到底，如果只是翻倍，我宁愿今天就套现拿钱——而是它能否实现 10 倍增长？我认为这往往是一个非常艰难的决定，因为对你个人而言也夹杂着情感因素。你虽然不是创始人，但你陪伴这家公司走过了四五六年，倾注了心血，还曾推荐好友去那里工作。然而你必须抽离出来，客观审视：“从目前来看，它无法实现 10 倍增长了。”然后你去协助掌舵。但我认为最重要的考量参数始终是：创始人的内心状态如何？
<details><summary>Original English</summary>
>> Then let's just sell this thing and and kind of move on. Um and then the second factor is you have to be pretty cold and objective about like is this going to be a interesting enough business? Not like will it double from here? Because at the end of the day, if it's double, I'll take the money today. But will it 10x from here? And that I would say gets to be a really hard decision because it's a little bit emotional also for you. Like you're you know, you're not a founder, but you know, you've been working with this company for four, five, six years. Your heart's in it. You you've told your good friends to go work there. And and yet you have to step step away from it and go like objectively, this is not 10x from here. And then you help steer the ship. But I think the most important parameter is where's the founder's head at?
</details>

>> 是的。对许多被投公司的创始人来说，这些交易究竟是如何发生的，存在着某种神秘感或未知数，对吧？人们往往以为是某天有人突然给另一家公司打电话说“我想买下你们”；与此相对的另一种情况是大家长期建立起的深厚联系。当年在思科你是如何处理的？即使被投公司有望实现 10 倍增长，你会如何向他们提建议？是直接打电话说“嗨，我想收购你们”，就这么简单吗？
<details><summary>Original English</summary>
>> Yeah. Yeah. And most So there is a certain element of mystery or unknown for a lot of the portfolio company founders on how do these things actually happen? Right? People think one day somebody calls another company and say, hey, I want to buy Versus and then there's other thing where people have built relationships for a long time. How did you approach it at Cisco and how would you advise your portfolio companies even if they are expecting a 10 X?
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 就这样直接打电话吗？
<details><summary>Original English</summary>
>> Do you just call them up and say, hi, I want to buy you? Is that it?
</details>

>> 不。显然，你要尽可能地拓展人脉网络并随时洞察行业动向。过去我们常把这称为“梳理库存清单”。市场上的每家公司都是潜在的收购标的，因此你要把它们编目建档，了解它们的增长率如何、拥有什么样的创始人、背后的支持者是谁、抱负是什么、客户有哪些，随时保持消息灵通。企业拓展团队必须做这项工作，但我认为公司里的每个人都应该时刻了解周围发生的一切。在思科，我们会尝试将这些标的库存与现有的战略定位结合起来。例如：我们是一家路由器公司，但未来的交换机数量将超过路由器，因此我们必须拥有交换机产品，市面上有哪些可收购的交换机公司？或者由于带宽需求爆发，光网络变得至关重要，市面上有哪些可供收购的标的？反过来，也经常会有公司主动找上门来说：“你好，我们希望被收购。”我认为这种一般都是坏主意，对吧？因为这要么意味着正在进行一场竞价拍卖，要么说明如果你们原本对它感兴趣，早就应该提前考虑了。基本上我们几乎从不关注主动找上门来的标的。反过来看，如果你现在是一家小公司或初创企业，该如何思考这个问题？我始终鼓励我们被投公司的创始人多与大公司交流，与竞争对手交流，始终保持对话。有人会说：“这样不是在四处兜售自己吗？”不，这是一种逆向的情报收集机制。我甚至鼓励我的 CEO 们去和直接竞争对手喝咖啡。如果你稀里糊涂，可能会泄露信息；但希望你不是懵懂无知的，他们可能会透露一些有价值的信息，或者帮助你重塑对行业的认知。因此我鼓励大家走出去，不断交流，观察市场的动向。通常情况下，如果你的公司遇到了一点困难，你动了出售的念头，你往往已经比较了解对方了，因为平时一直保持着沟通。所以初创公司的 CEO 没必要把整天的时间都花在聊天上，但每周去喝一两次咖啡，同英伟达、亚马逊或 OpenAI 的高层交流，当合适的人愿意对话时，去聊就是了。这种信息交换并不会让你失去太多东西，对方其实早已在思考这些问题了；但通过维系这种联系，你能获得巨大的收益。
<details><summary>Original English</summary>
>> No. Well, obviously you do as as a good a job as you can building a network and knowing what's going on. I I basically cataloging the inventory is the way we used to think about it. But every company in the market is a potential acquisition, so you catalog them and you know, where are they and their growth rate, what kind of founders they have, who are the backers, what are their aspirations, who are their customers, just like be informed. So and the and you know, the business the corporate development group had to do that, but I kind of considered it everybody's job at the company to be constantly informed about what's happening around them. So and then essentially we at the company we would try to weave at Cisco, we would try to weave in the inventory against a strategy statement that was there. For example, we're a router company, but there are going to be more switches than routers. Therefore, we need to have a switch. What are the switching companies that are available, right? Or optical networking is becoming important because of bandwidth, blah blah blah. What are the companies that are available? You often have the the other way where companies come to you and says, hi, I'd like to get bought. I think they're broadly a bad idea. Right? Because there's either an auction going on or you should have thought about it earlier if you were interested in it. But basically you almost never pay attention. We never try to pay attention to inbound. Flip side, you're you're now a small company or startup and how do you think about that? I always encourage always the founders of our companies to talk to big companies, to talk to competitors and to always be in dialogue. Some people will say like, well, you're shopping yourself. Uh, no, it's an inverse intelligence gathering mechanism. I even encouraged my CEOs to talk to their direct competitors. Go to coffee. All right? Like, yeah, you if if you're clueless, you might leak some information towards them. [laughter] Hopefully you're not clueless, and they might tell something to you that's interesting or they might shape your view on an industry or something. So I encourage people to be out there always talking and seeing what's happening in the market. And um usually you kind of have a pretty good idea of like, okay, my company is struggling a little bit. I think I'd like to sell. I kind of already know them because I've been in conversations with who's where. So I would say uh you know, don't a CEO of a startup shouldn't spend their entire day talking, but going on one or two coffees a week with you know, the powers that be at NVIDIA, the powers that be at Amazon and OpenAI, etc. etc. When the right people are talking, do it. It's fine. The information exchange, you don't lose that much in that. They're already thinking about it. Uh but you gain a lot by having that relationship.
</details>

>> 我认为这是极好的建议。我一直向我的被投企业 CEO 强调同样的事情：如果你手机里没有每一个竞争对手 CEO 的电话号码，那就是个问题，总有一天你会需要它的。这是一个你必须建立的网络。
<details><summary>Original English</summary>
>> I think this is really good advice. I I keep telling my portfolio CEOs the same thing. If if you don't have the cell phone number of the CEOs of each of your competitors, that's a problem. There will be a day when you need it. All right? Uh Absolutely. So you that's it's a network you need to build.
</details>

>> 绝对如此。
<details><summary>Original English</summary>
>> Absolutely.
</details>

>> 是的，是的。
<details><summary>Original English</summary>
>> Yeah, yeah.
</details>

### AI 基础设施全景：系统级架构、芯片与内存瓶颈

>> 关于并购的内容聊得差不多了，让我们回到具体的技术上来。你在基础设施领域深耕了 30 多年，很少有人比你更了解基础设施的现状与历史。请为我们概括一下当前的基础设施格局：你看到了哪些机遇与技术差距，以及创业者究竟应该关注什么？
<details><summary>Original English</summary>
>> Now enough of this M&A stuff. Let's get back to actual technology. You are spent 30 plus years in infrastructure. Very few people know more about infrastructure than what you do, what you've done in the past. Summarize the landscape for us right now when you think about infrastructure, opportunities versus where is the technology gaps that you see and um what founders be really looking at.
</details>

>> 这是一个非常引人入胜的话题。我认为可以从两个维度来思考当前行业的格局：一是垂直技术栈，从最底层的 EUV 光刻设备一直延伸到最上层的应用 AI 与终端应用，以及夹在中间的一切；另一个维度则是专门从基础设施侧去思考其价值链。首先，正如前面所说的，我们当前身处一个对 AI 算力与 token 的需求近乎无限、而供给极其短缺的世界。换句话说，我们都生活在黄仁勋的世界里。
<details><summary>Original English</summary>
>> Well, super interesting topic. You know, I would say you you want to think about I think the current in the shape of this industry in two dimensions, right? One is the vertical stack that starts with, you know, EUV equipment and goes all the way up to AI, applied AI and applications and everything that sits in between that sandwich. And then you want to think about particularly the infrastructure side. What's that what sort of the the the value chain of it? Um the first thing you would say is right now we live in a world where demand for AI capacity tokens, whatever, is near infinite. And supply is incredibly constrained. So another way to put it is we all just live in Jensen's world.
</details>

>> ［笑声］
<details><summary>Original English</summary>
>> [laughter]
</details>

>> 他是无可争议的王者。毫无疑问。我认为当需求特征发生变化，或者供给特征发生变化时，行业格局将开始改变。我的观点是，目前在供给侧，虽然确实存在一定的电力瓶颈，但最主要的限制依然在芯片制造。除非拥有更多的晶圆代工产能，否则这种情况不会改变；这意味着在未来两三年内很难发生根本转变，可能要看五年后。你可以设想未来拥有更多晶圆厂产能，让同一台设备跑更多晶圆，或者制造更多的 ASML 光刻机等等。但这很可能是我们行业的决定性制约因素，意味着我们将长期处于一个相对稀缺的世界中。而那些掌握晶圆制造产能的人，实际上扮演了基础设施领域的造王者角色。在需求侧，我认为全世界在使用 token 的类型上会变得越来越聪明。过去几年我们处于一个大家都只想要超高端前沿 token 的时期。而如今大家讨论的焦点是模型路由（model routers）：例如顶配的 Anthropic token 与顶配的 Kimi token 之间的经济成本差异可能达到 5 比 1 或 7 比 1，这是一个巨大的经济差距。因此人们在 token 消费上会变得更加精明，我认为这至少会让需求端开始产生价格敏感性。这在短期内更有可能发生。所以这些是主导我们行业的基本动态，夹在中间的无论是新云、推理云还是模型构建商，都生存在供需这两极之间。至于基础设施本身，我认为目前大家依然需要将整个基础设施视为单一系统来看待。这与过去的网络时代大不相同——过去你会假定流量具有高度波动性，流量类型和时间段各不相同，存在大量不确定性，因而更容易进行统计复用。而今天，大量 GPU 始终全天候高负荷运行，保持互联，数据流更为恒定；而且由于各组件之间的交互在很大程度上仍是专有的（比如 NVLink 等），你很难把其中一个组件随意替换掉。事实上，今天我会认为最好的架构可能是谷歌的 TPU 架构，因为它完全是作为单一系统来设计的。
<details><summary>Original English</summary>
>> He's he's king of the hill. There's no question. Um um I I I think uh the shape of the industry will begin to change when either the the characteristics of demand change or the characteristics of supply change. And I think that my my view is right now the the supply side because so much of the limitation Well, there's there's there are some power limitations for sure, but the dominant limitation is silicon. And um I would say that unless there's more fab capacity, that doesn't change, which is means it's not likely to really change in the next two or three years, maybe five years out. You could imagine that there would be more fab capacity. You could put more wafers through the same machines or you can make more ASML machines and so forth. But that's probably a governing factor of our industry, which means we live in a reasonably scarce world. And those who have fab capacity are are actually kind of kingmakers of of the infrastructure uh universe. Uh on the demand side, I do think that the world is going to get smarter about the type of tokens they consume. I think we've been in the kind of an era of the last couple of years that everybody just wanted the super high-end frontier token. And I think the topic of conversation today is model routers and how do I move stuff to you know the economic difference between a top end Anthropic token and a top end Kimi token is like 5 to 1 or 7 to 1 or whatever. It's a massive economic difference. So people are going to get start smarter about consuming what uh and and I I do think that that will begin to at least put some price dependency on demand. And that's a lot more likely to happen in the in the in the near term. So uh those are first of all I think the dynamics that are going to govern our industry and everybody that sits in between you know if you're a Neo cloud or you're an inference cloud or you're a model builder you live between those two poles of supply and demand. Now for the infra itself um I I think right now we still live in a world where you need to think of the entire piece of infra as a single system right? So uh it's quite different I think than the networking days for example of old where you would assume a very variable amount of traffic going from one to be types of traffic times of day lots and lots of variability much easier to statistically multiplex that workload. Um today basically you have uh lots of GPUs that are all working all the time always connected with much more constant flows and you you uh because the interrelationship between the various components are largely still proprietary you know you're on NVLink or whatever it's very hard to like swap one thing out for the other. And and the in fact today I would argue that probably the best architecture is the Google TPU architecture because it is literally thought of as a single system.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 我认为英伟达风格的架构正在朝 TPU 架构的方向演进，但目前它仍有一些可以拆换的部件。
<details><summary>Original English</summary>
>> And I I think an NVIDIA style architecture is migrating in the direction of where the TP- TPU architecture is, but it still has uh a few pieces that you can kind of swap out.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 剩下的其他人则像是：“我拿一颗 Cerebras 芯片，上面搭一台 Arista 交换机”，拼凑各种现成组件。至少在当今世界，这些系统存在低效性，因为它们不是作为一个整套系统构建的，更像是一种拼凑修补。我认为行业会演进，但如今那些能够将整体视作单一系统并据此优化架构的人，具备显著的竞争优势。
<details><summary>Original English</summary>
>> Um and then you have everybody else who's like, you know, I'm going to take a Cerebras chip and throw an Arista switch on top of it and like all that good stuff. And at least in today's world, those systems have inefficiencies uh because they're not constructed as a system. They're more of a patchwork. Um I I think that industry will evolve, but today people that can think of the whole thing as a single system and optimize the architecture of it through that have a competitive advantage.
</details>

>> 是的。看起来我们正在从以加速卡为最小单元，走向以机柜为最小单元，甚至在某些情况下演变为几个机柜。
<details><summary>Original English</summary>
>> Yeah. I mean, it it seems we're moving from from a from a card as the the minimum unit to a rack as the minimum unit or even even a few racks in some cases now.
</details>

>> 机柜级。确实如此。
<details><summary>Original English</summary>
>> racks. Yeah. I would that that's true.
</details>

>> 他们最近发布的部件可能构成了最小单元。
<details><summary>Original English</summary>
>> part that they announced recently that is the minimum unit possibly.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 如果你看谷歌是如何利用环形直通光纤 MEMS 交换机等技术构建系统的，那简直相当于把整个数据中心作为最小单元。
<details><summary>Original English</summary>
>> Well, but if you look at how Google does its thing with these like toroidal pass-through optical MEMS switches and everything like it's literally like the whole data center
</details>

>> 是的。整排机柜（row）成为了最小单元。
<details><summary>Original English</summary>
>> Yeah. is is the minimum unit. the row is the minimum unit.
</details>

>> 没错，确实如此。［笑声］
<details><summary>Original English</summary>
>> Yeah, exactly. [laughter]
</details>

>> 是的。但我感觉英伟达也希望朝那个方向走。
<details><summary>Original English</summary>
>> Yeah. Yeah. But I I my sense is that's where NVIDIA wants to go also.
</details>

>> 是的，显而易见。
<details><summary>Original English</summary>
>> Yeah, clearly.
</details>

>> 所以两家主流提供商都在走向这种系统级路径，而不是——
<details><summary>Original English</summary>
>> so the two dom- two dominant providers are all going to that systems approach versus
</details>

>> 甚至连小型初创公司也在朝这个方向迈进。请谈谈你对 AI 芯片演进的看法。目前黄仁勋居于顶峰，占据绝对优势；谷歌 TPU 也非常成功，但目前主要是谷歌自用。预计未来会有所改变。
<details><summary>Original English</summary>
>> I mean, even even the smaller startups are are heading that direction. Tell tell me on that. How how do you see how do you see AI chips evolving? And and right now Jensen, king of the hill, incredibly dominant, right? Google TPU very successful. Um currently mostly sold by Google. It's expected to change.
</details>

>> TPU 数量不够用。
<details><summary>Original English</summary>
>> Not enough TPUs.
</details>

>> 确实 TPU 不够用。未来的格局会怎样？我们会看到更具竞争力的芯片出现吗？
<details><summary>Original English</summary>
>> Uh but not enough TPUs, exactly. Uh how how will the how is the future looking like? Will we see more more competitive silicon?
</details>

>> 我认为肯定会。我们都渴望看到，也希望投资于此。但我首先觉得有趣的是，模型架构正变得相当多元化。有些人使用 FP4，有些人用 FP8；有些人采用包含大量专家的混合专家模型（MoE），有些人的专家数量较少；有些人不断推高参数量，有些人则不那么追求参数规模。我认为在芯片设计与围绕它进行优化的模型之间，存在着紧密的相互关联。
<details><summary>Original English</summary>
>> I think for sure. Um We all want that. Yeah. We all we all want it. Um and we all want to invest in it. But I would I would say I would say first of all, what I find interesting is that model architecture is becoming reasonably diverse. Mhm. Right? So you have uh people some people using FP4, FP8, uh some people are using mixture of experts with lots of lots of experts. Uh some have fewer experts. Some are jamming up the parameter counts, some not so much. And I actually think that there is a interrelationship between your chip design and the model that's optimized surrounded. Right? So
</details>

>> 软硬件协同设计。
<details><summary>Original English</summary>
>> Hardware software co-design.
</details>

>> 从某种意义上说，芯片会出现更多多样性吗？我认为会的，因为模型设计会出现更多的多样性。取决于你想运行什么样的模型、希望模型实现什么样的功能，你完全可以选择不同的芯片架构。迄今为止，推理强度（reasoning intensity）一直主导着芯片架构的设计走向，因为推理强度意味着大参数量和庞大的 KV 缓存（KV cache）。这就要求芯片与内存之间进行海量的数据通信。如果芯片之间只能通过边缘进行互连通信，其连接数远少于利用芯片顶部和底部进行连接的方式。因此，我是 3D DRAM 架构的忠实支持者；而结合混合铜键合（hybrid copper bonding）的新技术更加令人兴奋，因为能够实现更高的互连密度。只要我们继续看到对 KV 缓存高度密集的使用场景，我认为这种架构就具有巨大的前景。目前看来最具附加值的劳动或 AI 工作，都是由推理驱动的，因此这自然会青睐那些具备优异内存带宽的架构。我们投资了 Cerebras。Cerebras 在追求极致速度方面做得很出色。但如果模型无法完全放入片上 SRAM 中，
<details><summary>Original English</summary>
>> In some sense to your point like is there going to be more diversity in chips? And I think yes, because there is going to be more diversity in model designs. And depending on what kind of model you want to do uh what kind of things you want that model to do, you can certainly select a different chip architecture for that. Now uh reasoning intensity has dominated to date what chip architecture should be because uh reasoning intensity equals big parameter counts and big KV cache. Yep. Uh and that means that you need to talk a lot between memory and chip. Yep. Uh and you know when the only way you can talk between chips are the edges of it, it's just less connections than if you can use the top and bottom of the chip. So uh I'm a big fan of uh 3D DRAM architectures um and uh some of the new stuff that's coming up with hybrid copper bonding is even more interesting cuz you can have even higher density. Uh so uh I think that architecture has huge promise so long as we continue to see these KV cache in particular KV cache intensive use cases. And it seems like the most value added labor that occurs, labor or AI that occurs is reasoning driven labor. Right? So and and therefore that should favor architectures that have very good memory bandwidth.
</details>

>> 就需要很多芯片。
<details><summary>Original English</summary>
>> Yep. Um I we're investors in Cerebras. Cerebras did very well to go fast. Um but if the model doesn't fit in the SRAM, you know, a lot of them.
</details>

>> 是的，因为一旦离开 Cerebras 芯片的板上环境，速度就无法保持极快；而且由于晶圆级芯片尺寸巨大，一旦走出片外，在内存带宽上实际上处于显著劣势。现在他们在 Cerebras 芯片上运行 Sol 模型，那是一个大模型，说明他们找到了容纳它的方法；但我推测 OpenAI 必须做大量的艰苦工程才能把模型塞进芯片中。
<details><summary>Original English</summary>
>> Yeah. Well, yeah, you need a lot of Well, because once you get off off board of Cerebras chip, it's not going to go super fast, right? And they And also because the chip the wafer is so large, the actual you're actually at a significant disadvantage in terms of the memory bandwidth once you go off chip. Yep. So um now they they run Sol on on the Cerebras chip. Uh so that's a big model. So they've figured out how to fit it in. But my guess is OpenAI had to do some hard work to get that model to to fit in the chip.
</details>

>> 是的。我们同样看好 3D 架构，但在制造工艺上面临严重的热效应等问题，复杂度要高得多。
<details><summary>Original English</summary>
>> Yeah. No, we are fans of 3D architectures as well, but the manufacturability of it is a lot more complex with all the thermal effects and Yeah. Yeah. so on and so forth.
</details>

>> 没错。我本身是学热力学的机械工程师出身，所以热量是我的朋友。［笑声］
<details><summary>Original English</summary>
>> Yeah. No, I'm a big fan I'm a mechanical engineer that studied thermodynamics. So um heat is my friend. [laughter]
</details>

>> 这让你成为了极少数会这么说的人。台积电和其他厂商的封装部门估计正在给你打电话。［笑声］
<details><summary>Original English</summary>
>> That makes you one of the very few people who would say that. Yeah. So I'll So the we'll see how that pack divisions of TSMC and everybody else are calling you right now. [laughter]
</details>

>> 我赞同，这些芯片的封装将极其复杂，尤其是热学特性。当我们走向逻辑芯片和存储芯片置于同一封装内的形态时，虽然它们可能具有相同的热膨胀系数，但逻辑芯片的发热量要高得多。因此将它们封装在一起的能力可以说是非常棘手的挑战。
<details><summary>Original English</summary>
>> Uh yeah. Yeah. No, I agree. The packaging of those chips are going to be complex especially obviously the thermal attributes of it. And then when we get to a world where you have both a logic chip and a memory chip in the same package, the different um uh coefficients of Well, they they have the same coefficient thermal expansion, but logic chips get a lot hotter. So, you know, the ability to put that all into the same package will be non-trivial, shall we say?
</details>

>> 芯片重新变得火热，而且温度越来越高。另一种可能性当然是让它们继续保持物理分离，但在彼此之间采用光学互联。你相信这种路线吗？
<details><summary>Original English</summary>
>> Chips are hot again and they're getting hotter. The other possibility of course is to keep them still separate but have optical interconnectivity between them. Are you a believer in that?
</details>

>> 是的，我想是的。不过光学器件非常敏感脆弱，需要大量的实验探索。当你对光学部件加热时，它们并不适应高温，光子并不喜欢变热。理论上你希望拥有包含波导的基板，但一旦逻辑芯片开始升温、超出舒适的工作温度范围，就会引发各种连接故障等问题。所以我认为光学互连很有前景，但我的看法是：如果能用铜缆解决，我一定会首选铜缆。
<details><summary>Original English</summary>
>> Yeah. Um I think yes. Uh optics though are very finicky things um that need to be uh experimented with a lot. So you you when you heat up optics, they they don't they don't like it. They don't you know, photons don't like getting hot. And um, I mean, in theory, you would like have a substrate that have wave guides in it or something, but the minute the logic chip starts getting hotter and you get sort of outside the comfortable temperature range, you're going to have a variety of connectivity issues and so forth. So I I think optics are uh interesting. Um, if you can do it with copper, I'd do it with copper is is my view. But if you if you if you yeah.
</details>

>> 甚至在 Scale-Up 机柜内部也是如此，而不仅是跨机柜互连，甚至对于——
<details><summary>Original English</summary>
>> Even for scale up racks, not just interconnect now, but even for
</details>

>> 不，对于机柜扩展来说，那当然是另一回事了。那只是简化了布线等等。我指的是在模块级别内部。
<details><summary>Original English</summary>
>> No, no, I mean, obviously for scale up racks, that's a different story. That just simplifies the cabling and so forth. I'm talking about it at the at the module.
</details>

>> 在服务器内部。
<details><summary>Original English</summary>
>> Inside the server.
</details>

>> 是的，在机柜顶（Top of Rack）及以上层次，毫无疑问必须采用光学方案，因为铜缆根本没有足够的带宽。
<details><summary>Original English</summary>
>> Yeah, yeah, yeah. Yeah, yeah. No, for for when you start going top of rack and all that, definitely no no question. You just can't you don't have enough bandwidth. Um,
</details>

### 数据中心网络：电路交换复兴与架构范式转变

>> 当年思科作为全球市值最高的公司，是驱动整个互联网建设的早期网络硬件领导者。但在某个时刻它不再是市值第一了。当时是什么触发了这一转变？我们能从中吸取什么教训？
<details><summary>Original English</summary>
>> So so Cisco back then, most valuable company on the planet, early early hardware leader in networking which powered powered all of the internet. At some point wasn't most valuable company on the planet anymore. What what what triggered that? What can we learn from that?
</details>

>> 当在感知需求上出现泡沫时，往往会发生一种情况：客户会超额下单，因为他们知道订单会被削减。当时我们各条产品线的产能全部告罄，交换机制造供不应求，订单层层累积。由于需求感知非常强劲，我们便向整个供应链下单，并承担了这些订单的财务风险。我们相当于对供应链说：“钱给你们，请尽快把货交出来。”
<details><summary>Original English</summary>
>> What tends to happen when you have a bubble in demand, in perceived demand, is that uh customers over order because they know they're going to get cut back. Yep. And so every part of our product line was out of capacity. We were we couldn't we didn't have enough we couldn't make enough switches. We couldn't make we had orders on top of orders on top of orders on top of orders. And then what we were of course putting orders on all of our supply chain and because the demand felt so robust, we were taking the financial risk on those orders. In other words, we were like, here's the money, keep the money and just give the give us this stuff as soon as possible. So
</details>

>> 这能出什么差错呢？对吧。
<details><summary>Original English</summary>
>> could go wrong with that? Yeah.
</details>

>> 是的。接着当需求枯竭时，客户并不是放慢采购，而是直接取消所有订单。他们会说：“我本来就订了实际需求的两倍，现在我只需要原来的一半的一半。”于是订单一下子锐减到原先的四分之一左右。这就导致：第一，你承担了供应链的积压风险；第二，你的终端需求遭遇断崖式下跌。我记得这发生在 12 月那个季度，格外令人难忘。我们的财季错开了一个月，即 11 月、12 月和 1 月。通常对于错开月份的企业来说，12 月表现疲软，然后在 1 月第一周开始回暖，到 1 月底就能追平补齐。我们熬过了疲软的 12 月，当时觉得没什么大不了，12 月向来疲软；结果到了 1 月第一周毫无动静，第二周依然没有起色，第三周依然毫无起色，这时你意识到大势不妙。［笑声］那个季度的业绩缺口可能直接暴跌了 35% 到 40%。
<details><summary>Original English</summary>
>> Yeah. So then when demand dries up, it's not like people stop buying. They cancel all their orders. They're like, yeah, I never I ordered twice as much as I wanted to anyway. So I I I need half an half of half of that. So the orders went to like one quarter of what they what they were. And then you you A you've taken the risk on the supply chain and B your demand falls through the roof. And so I think we ended up in the December quarter and it particularly this is kind of memorable because it happened in December quarter. So we are one month off. So November, December, January. And usually what tends to happen with businesses that are month off you you know this right like December soft and then the first week of January you start seeing coming back and then by the end of January you've made it up. So we go through December it's soft and it's like no big deal December is always soft and then week one January nothing happens week two January nothing happens week three January nothing happens you're like oh [laughter] So the quarter came in I don't know maybe we missed by 35 40% right there.
</details>

>> 哇。
<details><summary>Original English</summary>
>> Wow.
</details>

>> 是的。对于一家上市十年从未错过任何季度预期的公司来说，这是巨大的打击。回调就这样发生了。那是一段艰难的时期，股价在六个月内从 80 多美元一路跌到大约 9 美元，市值蒸发了整整十分之九。非常残酷。
<details><summary>Original English</summary>
>> Yeah. Massive for a company by the way that publicly traded for a decade never missed a quarter. Yeah. And yeah and then that's how it all corrected. And it was a it was difficult stock went from 80 some dollars a share to nine dollars a share I want to say. So it was like literally one tenth the value over a period of six months. Very tough.
</details>

>> 每当顶层的工作负载发生足够大的改变时，底层的软硬件基础设施必须随之改变。在 AI 领域我们已经看到了这点。我们讨论了计算，那么网络方面会发生什么呢？我们在网络领域看到了巨大变化：我们不再只有一张网络，突然出现了第二张后端网络，这是从何而来的？
<details><summary>Original English</summary>
>> Yeah. So so look every time when the workload changes enough at the top layer the the underlying infrastructure software and hardware needs to change with it right with AI we've seen this. We talked about compute right. What what's going to happen in networking? I mean we've we've seen big changes in networking. We no longer have one network we don't have suddenly the second back end network where did this come from?
</details>

>> 你刚才难道是想予以太网死刑吗？
<details><summary>Original English</summary>
>> Did you just say Ethernet is dead?
</details>

>> 来了，以太网已死。以太网是一种成帧机制……
<details><summary>Original English</summary>
>> There we go Ethernet is dead. Ethernet is a framing mechanism for
</details>

>> 不，它正在卷土重来，之前确实死过一次。［笑声］
<details><summary>Original English</summary>
>> No it is it's coming back it was dead right the [laughter]
</details>

>> 电信世界的核心教条始于电路交换，比如电话：起点 A 到终点 B 之间建立恒定带宽，接通线路便可传输。后来我们发现这相当不可靠，因为线路一旦切断就中断了；而且面对不均匀的流量模式时无法良好扩展。于是我们决定转向分组交换（包交换）。数据包非常便利，因为它们允许统计复用（stat muxing），
<details><summary>Original English</summary>
>> Here here I think I think the the core tenants the world of telecom started with circuit switching right like we made the phone and the idea with the phone is that you had starting point A starting point B constant bandwidth between the two you connect the line and off it goes. And then we found out well this is like uh reasonably unreliable because one line cut and you lose it. Uh and obviously it doesn't scale very well in a world where you have uneven traffic patterns. So then we decided let's go to packets. And packets are very convenient because they allow stat muxing.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yep.
</details>

>> 这是它最核心的优势。当年 David 和 Andy 等人一直在为此摇旗呐喊。变长数据包以及所有的 IP 数据包由此普及。因此整个世界在构建网络设备时，都预设流入设备的流量具有不均匀性，设备可以通过统计复用来分散工作负载；同时进行欠配，因为并非所有人都会同时通过该设备进行通信，流入后的输出高度可变。这就是互联网，是我们长期习惯的工作负载模式。
<details><summary>Original English</summary>
>> Uh which is the big big benefit of it. David and Andy back then, right? They were cheerleading it, yeah. Yep. So so uh that and uh you know variable length packets and all of these you know IP packets essentially. So essentially the world grew up building networking equipment assuming that you had uneven arrivals and departures into a device that spread out the workload and you would under provision the device to connect more bandwidth because not everybody all communicates at the same time through the thing and the outputs of that inbound are highly variable. Okay that that was that's the internet, that's the workloads that we live with.
</details>

>> 这在很长一段时间内几乎成为了教条，对吧？
<details><summary>Original English</summary>
>> That was almost dogma, right? For for a long time.
</details>

>> 快进到今天，AI 数据中心是什么样子的？完全不是那样。这里没有随机的数据到达；链路持续处于完全打满的状态，GPU 始终渴望满负荷运转。流量模式实际上比以往任何时候都更具可预测性，尤其在模型训练阶段极具确定性；在推理阶段虽略逊一筹，但通过良好的批处理，流量模式依然清晰可辨。
<details><summary>Original English</summary>
>> Okay. So fast forward today, what does an AI data center look like? It does not look like that. You don't have random arrival. Um you links are consistently fully utilized. GPUs want to be fully utilized. Traffic patterns are actually much more predictable than they ever were before, particularly in training. They're incredibly predictable. They're less predictable in inference, but you can see the traffic pattern especially if you do like good batching.
</details>

>> 很大一部分依然高度可预测，对吧？尤其是做大批次处理时。
<details><summary>Original English</summary>
>> of it is still very predictable, right? especially if you do like big batching. Like you you can definitely make it more predictable.
</details>

>> 工作负载的基本属性已经改变了。然而如果你看当今主流的网络架构——比如博通收购 Dune 获得的 Tomahawk 交换芯片——它仍然是基于统计复用的包交换架构。因此我认为在未来的某个时间点，数据中心网络将迎来一种具备高度可预测性与满载利用率的架构，而不是不可预测的、随机的统计复用方式。
<details><summary>Original English</summary>
>> So the fundamental tenant of the the the workload has changed. Yet if you look at the dominant networking architecture today, which is the Broadcom uh uh what's it not Trident? Tomahawk. Uh which is the Dune acquisition that they did is a stat muxed packet switching architecture. Yes. So I think that at some point for data center networking we're going to have a uh a a kind of architecture that a high degree of predictability and a full utilization as opposed to an unpredictable, a stochastic, statmuxed approach. Um
</details>

>> 所以你说的本质上是回归电路交换。最终采用光路交换机（OCS）。
<details><summary>Original English</summary>
>> So essentially back to circuits is what you're saying. Yeah. Ends up optical circuit switches.
</details>

>> 或者时分复用（TDM）也同样奏效，对吧？
<details><summary>Original English</summary>
>> Yeah. So in an Or or I mean time division multiplexing works as well, right?
</details>

>> 或者是它们的结合体。你可以采用多种复用方式，但它们不是随机的，而是具有严格恒定时序的，比如 TDM 等等。当前的问题在于：你今天购买的交换机虽然拥有足够的带宽，但在架构上却是不匹配的，或者说是适应性较差的架构。我认为未来的数据中心交换机在某个时刻会更接近这种模式，甚至可能通过 MEMS 等技术实现。
<details><summary>Original English</summary>
>> Or combinations of those. You know you can have you can have many modalities of multiplexing, but they're they're not stochastic, right? They're they're constantly timed somehow. Like you can do TDM, you can do whatever else you want, but basically. So and I think these architectures the the the issue is the switches you buy today have the correct amount of bandwidth and the incorrect architecture. Not incorrect, but less adapted architecture. Uh and I think the data center switches of the future at some point will look more like that. Will look more uh like you know potentially you could do it with MAMS.
</details>

>> 那就是把 ATM 带回数据中心。
<details><summary>Original English</summary>
>> So bring ATM back into the data center.
</details>

>> 但即便是 ATM 也存在统计复用的随机信元，它并不是纯粹的物理电路。对网络设备商（包括我的老东家）来说，这是个坏消息。因为当技术不发生迭代变革时，你就无法维系高昂的定价，对吧？制造交换机的溢价点就在于：处理统计复用的流量是一头复杂的怪兽——一个数据包进来，必须存入内存，进行查表匹配，再从对应端口转发出去，这极难实现，因此设备非常昂贵。但在相对静态确定的世界里，你不需要那么多的智能，直接直通转发即可。因此我认为存在重塑网络架构的机会，使网络变得便宜得多。这是经典的“创新者的窘境”：无论你今天是哪家老牌网络大厂，这都不是一个有利的趋势，你不会想这么做；但对于破局的新入局者而言，抛弃那些统计复用包袱，完全有可能打造出极具颠覆性的产品。它可能是全光的，可能是电学的，也可能是光电结合的。但我认为这种范式必将出现，从谷歌构建其网络的方式中你已经能捕捉到端倪。
<details><summary>Original English</summary>
>> But even ATM had statmuxed stochastic cells, right? It was straight up circuits. Yeah. Um so now networking vendors including my former employer, this is bad news. Because when things don't change, you can't charge a lot of money for them. Right? Like the whole point of a switch is that it's a complicated animal to have a statistically, statistically multiplexed traffic flow. It's a hard thing to have oh my one packet came in here I have to throw it into memory, I have to do a lookup, do the lookup, I got to send it out of this gate. That's like hard to do. So you make the thing expensive. But in a world where it's relatively static, you don't need that much intelligence. Bam, send it right through, right? So I think that there's an opportunity for somebody to to sort of rethink network architecture given this workload and make it way cheaper. It's like classic innovator's dilemma. Because no matter what vendor you are today, this is not a good trend. You're not going to want to do that. But if a newcomer and you say you know what, forget all that statmuxing Like the world's different. I'm going to go with my thing. Actually, you might be able to build something interesting. Um, now it could be optical, it could be electrical, it could be a combination of the two. Um, but I think we're going to what will emerge and I think you can see clues of that from how Google does its network.
</details>

>> 是的，确实。我认为 Amin 是光路交换领域当之无愧的先驱，他们是最早落地的。
<details><summary>Original English</summary>
>> Yeah. Yep. Yep. I mean I think Amin has has been the pioneer of specifically optical circuit switching, right? As they were the first ones. And
</details>

>> 这就是那种环形结构的来源。另外顺便提一句，我不明白它为什么切换得那么慢，切换一次大概需要一分钟，这点我不太能理解。
<details><summary>Original English</summary>
>> That's where like the toroidal thing Yeah, yeah, yeah. I don't understand why it's so slow, by the way. It takes like a minute to switch. So that one I don't totally understand.
</details>

>> 我想在某种程度上是因为目前的用例是将其配置为相对静态的拓扑。如果是静态的，你又何必在乎切换时间呢？
<details><summary>Original English</summary>
>> I think to some degree it's because of the use case that right now you use it to set up fairly static. don't know that it is static. What do you care? Fair. I mean for availability
</details>

>> 就算为了可用性，也请给我毫秒级的切换，而不是一整秒。［笑声］
<details><summary>Original English</summary>
>> Still, I know but give me a few milliseconds, not a second. [laughter]
</details>

>> 但说实话，技术其实是具备这个潜力的，只是目前的应用场景还没有强烈需求。我也一直在考察其中的许多技术，无论是 MEMS 还是马赫-曾德尔干涉仪（MZI）等器件，看看里面是否有突破点。但关键是要有人能拿出一套完整的系统架构。接下来的核心难题在于谁会采用它，因为你无法脱离整个系统的协同而单独制造一台孤立的交换机。
<details><summary>Original English</summary>
>> Yeah, but you probably could, honestly, right? I mean the technology I think is there. It's just the use case is not there. Yeah. Yeah. Yeah. So yeah, no, I've been looking at a bunch of these, whether it's MEMS or uh his Max Ender thingies, the MZIs and what not, to see if there's something in there. But you know, somebody has to emerge with an architecture. And then the issue is going to be who embraces it because you can't just build a switch without the rest of the system coming together.
</details>

>> 这还要面对用户的路径依赖和转换惯性。
<details><summary>Original English</summary>
>> The I mean that's the other thing that exchange to the user's inertia as well.
</details>

>> 确实如此。回到今天基础设施“整排交付”的理念，网络已经成为整套架构不可分割的核心组件。因此这种创新在某种程度上几乎必须来自 GPU 芯片厂商本身。
<details><summary>Original English</summary>
>> Exactly. Right. Well, and this way the network to some degree coming back to the, you know, ship me a role concept of infrastructure today. The network has become an integral component of of your architecture. So this innovation to some degree almost has to come out of the the GPU vendors.
</details>

>> 是的。但有意思的地方在于，目前只有英伟达（未来 AMD 也许能达到）以及谷歌具备交付整机柜系统的能力。因此当下必须由他们来主导采纳。未来随着更多芯片厂商的崛起，是否会出现一个大家都能达成共识的替代性网络架构标准？就像我们当年所做的那样。
<details><summary>Original English</summary>
>> Yeah. Yeah, but it's interesting, right? Because there's on only Nvidia, maybe AMD will get there at some point, but only Nvidia and Google right now have the ability to ship you uh uh an a rack system. That's right, yeah. So today they would have to adopt it. Uh, it would be interesting to see like, you know, as more chip vendors evolve, is there uh, you know, is there an alternative architecture that they can all agree on? Um, sort of the that, you know, we did.
</details>

>> 就像当年的情形，IETF 2.0。［笑声］
<details><summary>Original English</summary>
>> Back in the days. Back in the day, right? So like if the thing is like you have two dominant vendors. The ITF 2.0. [laughter]
</details>

>> 当存在两家拥有自身技术路径的占主导地位厂商时，他们不太可能轻易做出改变。那么其他所有的参与者能否联合起来，建立一套大家共同认可并全力打造的标准化网络架构？
<details><summary>Original English</summary>
>> Well, they they they they have two vendors, they're dominant. Uh, they they have their own approach of doing things. They're not likely to shift off of that. And can you have uh uh a collection of everybody else that says, no, actually, this is a standardized network architecture that we're all going to agree upon and that's what we're going to build.
</details>

>> 叛军联盟，我喜欢这个比喻。关键在于采购方必须达成一致。
<details><summary>Original English</summary>
>> The rebel alliance. I like it. buyers have to agree. That's the key.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

### 周期纵览与结语

>> Mike，你见证了这么多轮技术周期，也亲历过上一次真正的超级大周期。相比之下，你如何看待当下的时代？
<details><summary>Original English</summary>
>> So Mike, you've seen a lot of these cycles now, some bigger, some larger. You've seen the last really big one. How how does this compare?
</details>

>> 如你所知，我创办了一家名为 Anabi Capital 的新风险投资基金。从严格意义上讲，我原本在 2023 年就退休了，本该买艘游艇打打高尔夫。这并没有如愿，对吧？因为我深信当下是从事我们这个行业、身处这一领域最令人心驰神往的时刻。这不仅是因为变革极其剧烈——我们都知道变革有多具颠覆性——更是因为理解未来的演进需要付出极其高密度的智力劳动。我们没有预测未来的水晶球，下一步棋该怎么走并不直观明显。你必须不断思考，而且必须以系统级思维进行跨维度的思考。我想以往没有任何一个时代，需要我去研究蔡司镜片上光线如何聚焦汇聚，来推断我的聊天机器人能否顺畅运转。这构成了令人惊叹的万物互联：这里存在瓶颈，引发连锁变化；那里的变动又牵动另一处。我由衷地觉得这是在智识层面最激动人心的时期。由于终极的回报如此丰厚，只要你能想清楚如何解锁这些不同的环节，就能在这里诞生一家万亿美元级企业，在那里创造出 5000 亿美元的公司等等。坦白讲，我未曾预料到自己的职业生涯中还能再次遇到这样的时代。到目前为止，我认为这是从事我们当下事业最富动态、最引人入胜的时刻，我们所有人都应当感到无比幸运。
<details><summary>Original English</summary>
>> As you probably know, I I've started a new venture fund called Anabi Capital. Technically speaking, I retired in 2023 and I was supposed to get a yacht and and play golf. work out very well, did it? Why? I I actually think this is the most fascinating time to be doing our job and to be in our industry. Not just because the change is big and we all know that, you know, how transformative the change is, but because it requires more uh intellectual exertion to understand how what next. It's like you don't have a crystal ball. It's not obvious what the next move is. Yeah, it's hard. And so you have to keep thinking and you have to think at a systems level. Like I don't think I've ever been in industry before that I had to think about how light gets concentrated on a Zeiss mirror to figure out whether my chatbot works well. And like that it's all it's this amazing interconnection of things where there's bottlenecks and this changes and this change that change. So I find it just the most intellectually fascinating time. And because the end prize is so significant by figuring out how these different parts unlock, you can create a company here and a company there, and this one can become worth a trillion dollars, and this one can become 500 billion, and so on and so forth. And I honestly I did not expect to encounter another time like this in my career, and by far I find I find this the most dynamic and interesting time to be doing what we're doing, and I think we should all feel quite fortunate about it.
</details>

>> 这完全超越了 1999 年。
<details><summary>Original English</summary>
>> This This tops 99
</details>

>> 噢，是的。
<details><summary>Original English</summary>
>> Oh, yeah.
</details>

>> 轻易超越。
<details><summary>Original English</summary>
>> Easily.
</details>

>> 完全赞同，我们大家之所以投身于同一项事业，都是出于非常相似的原因。这真是令人着迷的一个小时。非常感谢你，Mike。我们本来可以无休止地聊下去，不过也许我们下次再续。
<details><summary>Original English</summary>
>> Totally Totally agree, and we are all on the same business for very much the same reason. This has been a fascinating hour. Thank you so much, and we could be continuing this conversation endlessly, but perhaps we'll do it another time.
</details>

>> 聊得非常愉快，谢谢大家。
<details><summary>Original English</summary>
>> This was super fun. Thank you guys.
</details>

>> 感谢你的到来，Mike。非常感谢。
<details><summary>Original English</summary>
>> Thanks for coming, Mike. We appreciate it.
</details>