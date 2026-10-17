---
author: All-In Podcast
date: '2026-07-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Y7p4rUCdqi0
speaker: All-In Podcast
tags:
  - inference-chip
  - data-center-scale
  - compute-demand
  - generative-ai
title: 超级智能竞赛中的推理芯片崛起与数据中心建设的规模化挑战
summary: 文章探讨了在追求通用人工智能（AGI）的过程中，超大规模计算基础设施的惊人建设规模。核心内容包括对推理芯片领域的先驱公司及其商业模式的讨论，以及当前算力需求已远远超出硬件建设能力的矛盾，并展望了生成式AI与粉丝共创等前沿应用带来的价值创造和未来发展方向。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cerebras
  - AppLovin
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/8 -->

### 超级智能竞赛与 Cerebras 的崛起

**Host**: 我们正处于超级智能的竞赛之中。安德鲁·费尔德曼（Andrew Feldman）又回到了我们的节目。他显然是 Cerebras 的首席执行官兼创始人，该公司致力于制造推理芯片，并且是该领域的先驱，之前已经成功上市（IPO）。我们之前已经讨论过几次了。今年一月在达沃斯我们见过面。IPO 之后，我和伙计们最近又和你坐下来聊了聊。

<details>
<summary>Original English</summary>

**Host**: We are in the race for superintelligence and uh Andrew Feldman is back uh and obviously CEO and founder of uh Cerebras doing inference chips pioneered the space had a successful IPO. We've talked about this a couple of times. We got to see each other in January at Davos. IPO happens. Uh the boys and I got to sit with you recently.

</details>

**Andrew Feldman**: 那次真的很有趣。

<details>
<summary>Original English</summary>

**Andrew Feldman**: That was fun

</details>

**Host**: 在流动性活动上。

<details>
<summary>Original English</summary>

**Host**: at liquidity.

</details>

**Andrew Feldman**: 那真的非常有趣。

<details>
<summary>Original English</summary>

**Andrew Feldman**: That was really that was really fun.

</details>

**Host**: 和伙计们进行了非常棒的讨论。我想和你深入探讨几个话题。第一个就是 AI 的建设规模。我们以前从未见过这样的建设规模，我想，可能自从建造万里长城以来就没见过吧。

<details>
<summary>Original English</summary>

**Host**: Had a great discussion with the boys. I wanted to deep dive with you about a couple of topics. The first one is the buildout of AI. We've never seen a build out like this since, you know, the Great Wall of China,

</details>

**Andrew Feldman**: 是的吧？谁知道呢？

<details>
<summary>Original English</summary>

**Andrew Feldman**: right? Who knows?

</details>

**Host**: 或者是金字塔。我的意思是，感觉就像是地球上大量的资本、时间以及聪明人，都在全心投入到某项建设中。我能想到的我们有生之年内，或者我们出生之前能与之相比的，可能只有战争时期的全民动员了。

<details>
<summary>Original English</summary>

**Host**: The pyramids. I mean, it feels like the amount of capital, time, and intelligent people on the planet dedicating themselves to the buildout of something. Um I I can't think of anything in our lifetimes with per perhaps uh you know before our lifetimes the war effort

</details>

**Andrew Feldman**: 对。

<details>
<summary>Original English</summary>

**Andrew Feldman**: right

</details>

**Host**: 这是一种我们在书上读到过、听说过的动员和规模，但你们实际上正在参与其中。你们的客户正在建设数据中心，而你们是其中的关键一环。

<details>
<summary>Original English</summary>

**Host**: this is a mobilization and a scale that we read about we hear about but you're actually doing it you have customers who are building data centers and you're a key piece of that

</details>

### AppLovin 广告赞助插播

**Host**: AppLovin 最初只是一个 8 美元的域名，没有风险投资，后来成为了世界上最大的广告平台之一。现在同样的引擎也在为 AppLovin 的电商广告提供动力。你的广告可以在手机游戏内运行，在没有干扰的全屏注意力下，触达超过十亿人。该平台会自动寻找买家并优化利润。你只需设定目标，剩下的交给它。有一个厨具品牌在 AppLovin 上的收入从 400 万美元增长到了 1600 万美元，实现了扭亏为盈，而且今年的收入有望达到 8000 万美元。现在就访问 applovin.com/allin 来启动你的第一个广告系列吧。

<details>
<summary>Original English</summary>

**Host**: allapp started with an $8 domain and no VC funding and became one of the largest ad platforms in the world now that same engine powers Appleven ads for e-commerce. Your ads run inside mobile games, reaching over a billion people with full screen, distraction-free attention. The platform finds buyers and optimizes for profit. You set the target, it does the rest. One cookware brand went from 4 million to $16 million, turned profitable, and is on pace for 80 million this year. Visit apploven.com/allin to launch your first campaign today.

</details>

### 数据中心建设的惊人规模

**Host**: 也许你可以给我们讲讲 2026 年的情况。Cerebras 现在在做什么？德克萨斯州的这些建设进展如何？这些都是极其庞大的工程。正在建设的项目在物理尺寸和规模上都非常惊人。通常当我们谈论软件或者硬件时，我们谈论的是芯片或者机箱，它们并没有这种物理上的巨大规模。对吧。

<details>
<summary>Original English</summary>

**Host**: Maybe you could just enlighten us in 2026. What is Cerebras doing and what is happening with this buildout out in Texas? These are some gigantic gigantic efforts. The the size and scope of what is being built, the physical size and scope. Usually when we talk about software or we talk about hardware, we're talking about chips or boxes and and they don't have the same sort of physical enormity. Right.

</details>

**Andrew Feldman**: 没错。我们现在谈论的数据中心，在未来几年内使用的电力将比地球上过去 50 年的总耗电量还要多。哇。是的。我们谈论的是那些单个建筑就有足球场那么大，而且输入的电力比中型城市还要多。并且它们正在全美各地建设。在加拿大在建，在整个北欧也在建。甚至在巴黎和整个法国，在欧洲，在中东——那些以前根本不在人们视线中心的国家，比如哈萨克斯坦、塔吉克斯坦，也都在建设。格鲁吉亚在建设大型数据中心。亚美尼亚，几乎每个人都聚焦于此。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Right. And what we're talking about now are data centers that are in the next several years going to use more power than the previous 50 years on Earth took. Wow. Right. We're talking about individual buildings the size of football fields that have more power coming into them than midsize cities. And they're being built they're being built across the US. They're being built in Canada. They're being built throughout the Nordics. are being built here in Paris and throughout France, in Europe, in the Middle East in nations that sort of weren't front and center in anybody's mind previously. You know, Kazakhstan, Tajjikstan are building out Georgia building out data centers of size. Armenia, everybody's sort of focused.

</details>

**Host**: 每个国家都是。

<details>
<summary>Original English</summary>

**Host**: Every country

</details>

**Andrew Feldman**: 显然，美国的每个州都觉得自己需要参与其中。

<details>
<summary>Original English</summary>

**Andrew Feldman**: um and every state obviously in America feels they need to participate in this

</details>

**Host**: 而且那些购买算力容量的人，比如 OpenAI、Anthropic、SpaceX、SpaceX AI、Google 们，他们现在的需求是无法满足的。

<details>
<summary>Original English</summary>

**Host**: and the people who are buying the capacity, the open AI, anthropics, SpaceX, SpaceX AI, uh the Googles, they are insatiable right now.

</details>

**Andrew Feldman**: 是的，当你和他们交谈时，你会发现他们正规划着未来好几年的建设。早在你们芯片还没完工之前，他们就已经向 Cerebras 订购了。他们都在提前下订单。讽刺的是，这与科技界过去许多令人兴奋的时期不同。他们现在是在努力满足“昨天”的需求，对吧？需求远远超过了我们建设数据中心以及用硬件填满它们的能力。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah. and they're building how many years out when you talk to them? They were ordering chips from Cerebras before you were finished with the chips. They're putting orders in ahead of time. The irony is unlike many sort of exciting times in technology. They're trying to capture yesterday's demand, right? The demand is way outstripping our ability to build data centers and to fill them with hardware.

</details>

**Host**: 对吧？所以，你要知道，我们现在有 250 亿美元的订单积压。

<details>
<summary>Original English</summary>

**Host**: All right? And so, you know, we have a $25 billion backlog,

</details>

**Andrew Feldman**: 250 亿美元的积压。

<details>
<summary>Original English</summary>

**Andrew Feldman**: $25 billion backlog

</details>

**Host**: 而且不仅是我们，OpenAI、Anthropic，你可以看看这个名单，Google 想要更多数据中心，微软想要更多数据中心，AWS 想要更多数据中心，对吧？所有这些参与者都不是在追求“如果你建好了，他们就会来”（即被动等待需求）。他们是在追求已经被预订的需求。

<details>
<summary>Original English</summary>

**Host**: and we we are not alone in that that that OpenAI uh Anthropic, you go through this list of of uh Google wants more data centers, Microsoft wants more data centers, AWS wants more data centers, right? All of these players are not chasing sort of if you build it, they will come. They're chasing the demand is booked,

</details>

**Andrew Feldman**: 对吧？我们该如何留住他们？是的。这是非常不寻常的情况。

<details>
<summary>Original English</summary>

**Andrew Feldman**: right? How do we keep them from leaving? Right. And and that that's extremely unusual.

</details>

### AI 价值创造与实验性探索

**Host**: 这是非常不寻常的。现在我们有这样一群人，我们有个词叫“Token 最大化”（token maxing）。

<details>
<summary>Original English</summary>

**Host**: It's very unusual. And now we have people who are, you know, we have a term for a token maxing.

</details>

**Andrew Feldman**: 是的。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah.

</details>

**Host**: 现在存在一个巨大的争论：这真的在创造价值吗？我很好奇你的立场。你知道，如果没有价值存在，真的可能产生这么大的需求吗？显然这里正在产生巨大的价值。

<details>
<summary>Original English</summary>

**Host**: And there's a great debate. Is this actually creating value? I'm curious where you stand. You know, is it even possible that this much demand could be created if value did not exist? There is clearly massive value happening.

</details>

**Andrew Feldman**: 是的，但也存在大量的实验性尝试。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah. But there's also massive experimentation.

</details>

**Host**: 哦，那是肯定的。你知道，我把这比作我们刚开始使用 AWS 的时候，绕开你公司内部的 IT 部门感觉太好了，对吧？

<details>
<summary>Original English</summary>

**Host**: Oh, for sure. You know, I you know what I I I liken this to when we first started with uh AWS and it was so good to get around your own IT organization, right?

</details>

**Andrew Feldman**: 是的。

<details>
<summary>Original English</summary>

**Andrew Feldman**: That you told every engineer, yeah, go ahead, put on your credit card kite and sign up.

</details>

**Host**: 然后你告诉每一个工程师，去吧，用你们的信用卡注册就行。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Andrew Feldman**: 没错。其中很多确实非常有用，但也有一些让人觉得：“天哪，真希望我们没这么做。”

<details>
<summary>Original English</summary>

**Andrew Feldman**: Right. And a lot of it was really useful and some of it was like, God, I wish we didn't do that.

</details>

**Host**: 是的。所以肯定存在实验阶段，但这并不意味着净价值不是巨大的。这只是意味着其中一些尝试最终会无疾而终。

<details>
<summary>Original English</summary>

**Host**: Yeah. And so for sure there's experimentation, but it doesn't mean that the net value isn't enormous. It it means some of it is going to go nowhere.

</details>

**Andrew Feldman**: 你知道，这道理是一样的。我记得 1988 年好市多（Costco）在帕洛阿尔托地区开业时，人们像逛 Safeway 超市一样逛好市多，他们会走过每一条过道。

<details>
<summary>Original English</summary>

**Andrew Feldman**: And you know, it was the same. I remember when Costco opened up in in in in the Palo Alto area in 1988. And people used to shop Costco like they shop Safeway. They go down every aisle.

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Andrew Feldman**: 那种逛好市多的方式是很糟糕的，因为最后你买回了四件你根本不需要的东西，而且每件都要 22 美元。

<details>
<summary>Original English</summary>

**Andrew Feldman**: And that's a horrible way to shop Costco because you end up with four things you didn't need and each was $22.

</details>

**Host**: 没错。后来随着人们变得越来越习惯，你直接走到后面，拿上烤鸡。

<details>
<summary>Original English</summary>

**Host**: Right. And as people got more sort of accustomed to it, you go to the back, you get the chicken,

</details>

**Andrew Feldman**: 为孩子生日派对准备 18 个纸杯蛋糕，搞定，这就是很有策略性的购物。这（使用 AI）也是完全一样的。

<details>
<summary>Original English</summary>

**Andrew Feldman**: 18 cupcakes for the kids' birthday party, bang, you are strategic. And it's exactly the same.

</details>

**Host**: 我认为一开始人们放开了限制，说每个人想要多少 token 都可以。

<details>
<summary>Original English</summary>

**Host**: I think at first people opened up and said everybody as much tokens as you want.

</details>

**Andrew Feldman**: 在企业中，是不存在开环系统的。我们不会不受限制地把任何资源交给员工。现在我们开始介入并说：“哇，好吧。这些家伙应该得到他们需要的量，他们在这方面效率极高。而在这边，我们也许可以使用开源模型，也许可以使用更便宜的模型。” 现在我们正在像经营企业一样运作。我们真的看到了一种特定类型的人的崛起，他们知道如何部署这项技术。系统性思维。

<details>
<summary>Original English</summary>

**Andrew Feldman**: And the in enterprises, there's no open loop. We don't give sort of any resource unconstrained to people. And now we're jumping on saying, "Whoa, all right. These guys should have as much as they need. They're enormously productive over here. We can use maybe an open- source model, maybe a cheaper model over here. And now we're sort of running like a business and we're really seeing a certain type of person emerge who knows how to deploy this technology. Systems thinking,

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: yeah,

</details>

**Andrew Feldman**: 开发者通常天生具备这种思维。CEO 往往是伟大的战略家，理解系统。但是现在的智能程度在每一步都变得如此之好。我在观察一些个人，通常是初创公司的创始人，也包括我们风险投资公司的合伙人和风投家们。他们开始使用这些工具，然后工具反过来开始引导他们。他们开始意识到：“哦，我还没明确定义我的目标是什么。我不明白什么是系统。我甚至从没听说过要编写需求文档。” 而软件会问：“你有需求文档吗？你的目标是什么？” AI 开始告诉人们：“你只是在疯狂消耗 token，你需要稍微聚焦一下。”

<details>
<summary>Original English</summary>

**Andrew Feldman**: which developers kind of have innately CEOs tend to be great strategists and understand systems. Uh but this the intelligence is getting so much better every step along the way that I'm watching individuals typically startup founders but also venture capitalists and associates who work at my venture firm. They start playing with the tool and then the tool starts playing with them. They start to go, "Oh, I haven't clearly defined what my goal is. I don't understand what a system is. I don't under I've never heard about making a requirements document." And the software's like, "Do you have a requirements document? What's your goal?" The AI starts telling people, "You're token maxing and you need to get a little more focused here."

</details>

### AI 意图理解的飞跃

**Host**: 20 年前我的一位同事，一位非常非常聪明的计算机科学家说过：“计算机其实很笨。它们只会完全照你说的去做。”

<details>
<summary>Original English</summary>

**Host**: One of one of my colleagues 20 years ago, a really smart smart computer scientist said, "Computers really dumb. They do exactly what you tell them."

</details>

**Andrew Feldman**: 是的。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah.

</details>

**Host**: 一开始，提示词（prompting）也是那样的，对吧？你稍微修改一点点提示词，答案就会发生戏剧性的变化。

<details>
<summary>Original English</summary>

**Host**: And at first, prompting was like that, right? You modified your prompt a little bit and it changed the answer

</details>

**Andrew Feldman**: 戏剧性的。

<details>
<summary>Original English</summary>

**Andrew Feldman**: dramatically.

</details>

**Host**: 戏剧性地改变。而现在，它越来越能理解你的意图了。

<details>
<summary>Original English</summary>

**Host**: Dramatically. And increasingly it's understanding what your intent was.

</details>

**Andrew Feldman**: 对。没错。如果你有机会玩一下 Fable 或者 OpenAI 的 56 模型，你会发现，越来越不需要把提示词写得天衣无缝了。你不需要成为一个“提示词巫师”（prompt whisperer）。相反，你去问它，它会说：“好吧，这里有一些东西，顺便说一下，也许你想要图表有两种展示形式，既要有折线图也要有柱状图。” 你就会觉得：“哇，那正是我想要的。我虽然没开口要，但这样更好。” 所以，这就是对意图的理解，这是一个巨大的飞跃。如果我们两年前坐在这里谈论这个想法……

<details>
<summary>Original English</summary>

**Andrew Feldman**: Right. Right. And if you if you have a chance to to to play with Fable or or 56 from from OpenAI, increasingly what you don't have to get the prompt just right. You don't have to be a prompt whisperer. Instead, you ask it and it says, "Well, here are some things and and by the way, maybe you wanted the chart to to to go two ways. You wanted a line and a bar." And it's like, "Well, that's exactly what I wanted. I didn't ask for it, but that is better. And and so it's it's understanding intent and that's a huge leap which if we were sitting here two years ago, the idea

</details>

**Host**: 我们绝对无法预测到，在短短 24 个月内，它能从一个出色的网络结果总结器和研究员……

<details>
<summary>Original English</summary>

**Host**: we would never have been able to predict in a short 24 months that it would go from being a great summarizer researcher of web results,

</details>

**Andrew Feldman**: 对。

<details>
<summary>Original English</summary>

**Andrew Feldman**: right,

</details>

**Host**: 进化到能够真正理解你的意图，然后提供解决方案，并且把所有的复杂性对你进行抽象化封装。

<details>
<summary>Original English</summary>

**Host**: to actually understanding your intent and then providing a solution and abstracting it all from you.

</details>

**Andrew Feldman**: 说得对。完全正确。

<details>
<summary>Original English</summary>

**Andrew Feldman**: That's right. That's right.

</details>

**Host**: 这是一件非常不可思议的事情。不知道你有没有玩过 Hermes 智能体？

<details>
<summary>Original English</summary>

**Host**: Which is a very weird thing. I don't know if you've played with the Hermes agent yet.

</details>

**Andrew Feldman**: 是的玩过。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah.

</details>

**Host**: 你试用过了吗？

<details>
<summary>Original English</summary>

**Host**: Have you played with it yet?

</details>

**Andrew Feldman**: 我是说，我今天早上才刚问过它。我获得了一个秘密的 Bittensor 项目的权限，它包含了新的 ZAI 的模型 52……

<details>
<summary>Original English</summary>

**Andrew Feldman**: I mean, I asked it just this morning. Uh, and I I was given a secret bittensor project that has the new um ZAI's uh model 52

</details>

**Host**: 他们给了你……

<details>
<summary>Original English</summary>

**Host**: and they gave me

</details>

**Andrew Feldman**: GLM 52。是的。

<details>
<summary>Original English</summary>

**Andrew Feldman**: GLM 52. Yeah.

</details>

**Host**: GLM 52。所以，在那个 Bittensor 里的某个人，我想你应该了解 Bittensor，你听说过它，那个分布式的……

<details>
<summary>Original English</summary>

**Host**: GLM 52. So, somebody in that Bit Tensor, I think you understand Bit Tensor, you've heard of it, the distributed

</details>

**Andrew Feldman**: 嗯，加密项目。而且……

<details>
<summary>Original English</summary>

**Andrew Feldman**: um crypto project. And

</details>

<!-- chunk 2/8 -->

### 发现模型的推理能力

**Speaker A**: 所以他们拥有所有这些额外的算力。有人私下告诉我，可能在中国有一些拥有免费能源的算力。好吧，那没问题。所以他们给了我无限的算力。于是我开始让它做一些非常疯狂的任务，我说：“我希望你每小时都告诉我世界上有哪些还没有人发现的趋势。为了做到这一点，你想怎么做都行。但我的目标是成为世界上最聪明的趋势猎手。”然后我观察它在后台的运作，发现它开始自己进行辩论，讨论应该去哪里寻找这些东西。它说：“嗯，我们可能应该去 Hacker News 和 Reddit。” 然后我就说：“对，但还有社交媒体，而且趋势往往会在 Instagram 上显现出来。”

<details>
<summary>Original English</summary>

**Speaker A**: so they have all this extra capacity. I was a whisperer told me probably some capacity in China that has free energy. Okay, fine. So they gave me unlimited capacity. So I started having to do some really crazy jobs where I was saying like every hour I want you to tell me what the trends in the world are that nobody else has identified yet. And you can do whatever you want to do that. But my goal is to be the smartest trend hunter in the world. And I watched what it was doing in the background and it started debating itself on where it should find the things. He said, "Well, we should probably go to Hacker News and Reddit." And then I was like, "Yeah, but there's also social media and trends tend to manifest on Instagram."

</details>

**Speaker B**: 那是一个推理模型。你当时是在观察一个推理模型进行演算。

<details>
<summary>Original English</summary>

**Speaker B**: That's a reasoning model. You were watching a reasoning model work out.

</details>

**Speaker A**: 是的。那不是很引人入胜吗？我是说，那太惊人了。而且那是一个折叠的过程。所以，作为一个普通人，如果你没有触及那个未折叠的时刻，如果你用的是 ChatGPT 3.5 或者 4.8（不管是什么版本），而且你还没有体验过这种新层次的推理、推断以及本质上无限的计算……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Isn't that interesting? I mean, that's amazing. And and it was collapsed. So, as a civilian, right, who doesn't hit the uncolapsed moment, and if you were using chatbt 3.5 or you were using 4.8, whatever it was and you haven't used this new level of reasoning and inference and unlimited compute essentially,

</details>

**Speaker B**: 对吧？

<details>
<summary>Original English</summary>

**Speaker B**: right?

</details>

**Speaker A**: 就在今天早上，这让我大开眼界，让我看到了一个拥有无限 token 的世界可能会是什么样子，对吧？因为我相信，无限的 token 意味着无限的推理。确实如此。这意味着什么呢？是的，我的意思是，如果你让这些模型运行 25 或 48 小时，你现在就能得到惊人的结果。那如果使用 Cerebras 我们能快 15 倍，然后你让它运行 24 小时呢？

<details>
<summary>Original English</summary>

**Speaker A**: It opened my eyes just this morning of what a world of unlimited tokens might look like, right? Cuz unlimited tokens, I believe, means unlimited reasoning. It does. What does that mean? Yeah, it's uh I mean if you run these for 25 or 48 hours, you get amazing things now and what what if by using Cerebrus we were 15 times faster and then you ran it for 24 hours,

</details>

**Speaker B**: 对吧？那你就能获得相当于几周或几个月的思考量。

<details>
<summary>Original English</summary>

**Speaker B**: right? A and you got weeks or months worth of thinking.

</details>

**Speaker A**: 是的。我的意思是，那真的是非同寻常。而且我认为其中一件事是，像 Ilia 和 Sam 这样的人在早期就说过这一切会到来。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And I mean it it is uh it is extraordinary. And I I think one of the things is people like Ilia and Sam in the early days were saying this was coming.

</details>

**Speaker B**: 对。对。我觉得当你回首过去，你会对自己说：“我的天啊。那些家伙早就预见到了。”

<details>
<summary>Original English</summary>

**Speaker B**: Right. Right. And I think when you look back you say to yourself, "Holy crap." Those guys saw it.

</details>

**Speaker A**: 是的。他们能够预见未来的趋势。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. They were They could see around the corner.

</details>

**Speaker B**: 没错。而我们其余的人当时能看到什么呢？我不确定。有一次我们请 Sam 上《All In》播客，当时他说，“哦，你知道，我很乐意找个时间来参加。”我说，“没问题，来吧。”然后他就谈到了这个话题。他说，你知道，我问：“下一步是什么？”他说：“推理。”我说：“详细解释一下。那是什么意思？”嗯，那就是能够理解你刚才说的意图，然后想出一个策略，接着可能还会和其他代理以及其他线程交流，讨论像“这样做对吗？”之类的问题，互相审查对方的工作。我当时就想，哇，我们从“猜测下一个词”已经走得很远了。

<details>
<summary>Original English</summary>

**Speaker B**: That's right. And the rest of us could see like what? I'm not sure. It's when we had Sam on Allin uh at one point he uh and he said, "Oh, you know, I'd love to come on at some point." I said, "Sure, come on." And he he was talking about it. He said, you know, I said, "What's next?" He said, "Reasoning." I said, "Unpack that. What does it mean?" Well, understanding what your intent was just as you're saying and then figuring out a strategy and then maybe talking to other agents and other threads about like is this the right thing to do and vetting each other's work and I'm like wow we have come a long way from guess the next word

</details>

**Speaker A**: 对，对，填补句子，你知道的，或者总结这份 PDF。

<details>
<summary>Original English</summary>

**Speaker A**: right right fill the sentence in you know summarize this PDF

</details>

### Cerebras 与无限推理

**Speaker B**: 现在 Cerebras 处于这一切的核心，因为这种推理就是推断。这种推理就是推断，而且它是计算密集型的。

<details>
<summary>Original English</summary>

**Speaker B**: now Cerebrus is at the center of this because this reasoning is inference this reasoning is inference and it's computationally intensive

</details>

**Speaker A**: 对。

<details>
<summary>Original English</summary>

**Speaker A**: right

</details>

**Speaker B**: 对。因此，快速的计算使得这类工作能够快速进行，变得易于处理。它不需要花费大量的时间来得出一个好答案。正是因为这种推理在内部消耗了大量的 token……这就让像我们这样速度快得惊人的机器得以存在。我带了一块过来，因为我出门总得带着它。你知道，当制造一块这样的东西要花五亿美元的时候，你到哪儿都会带着它。呃，我们在达沃斯论坛的时候还把这东西抛来抛去的。

<details>
<summary>Original English</summary>

**Speaker B**: right and So fast compute makes this sort of work fast and sort of tractable. It doesn't it by taking a huge amount of time to get a good answer. And so it's exactly the fact that that that this reasoning consumes a huge amount of tokens internally that allows a blisteringly fast machine like ours. And I I brought one because I I'm never far without you know when one costs half a billion to make you you bring it everywhere with you. Uh we we were um we were tossing this back and forth at Davos.

</details>

**Speaker A**: 呃，这个的型号是多少？

<details>
<summary>Original English</summary>

**Speaker A**: Uh what's the model number of this one? Th

</details>

**Speaker B**: 这是前八个或前十个制造出来的之一。

<details>
<summary>Original English</summary>

**Speaker B**: this was in the first eight or 10. Um

</details>

**Speaker A**: 所以这个有着特殊的地位。

<details>
<summary>Original English</summary>

**Speaker A**: so this has a special place.

</details>

**Speaker B**: 它有着特殊的地位。我是说，我妻子说我就像个八岁生日时拿到一辆越野摩托车的孩子一样。到了晚上它就在他的卧室里。我走到哪儿都带着它。

<details>
<summary>Original English</summary>

**Speaker B**: This has a special place. I mean my wife says it's like I'm a kid with a a dirt bike for his 8th birthday. It was in his bedroom at night. I I carry him with me.

</details>

**Speaker A**: 我的意思是，当你在家里举办下一次派对时，我强烈建议只要一点点或者什么的……我觉得这会非常合适。如果你有一些的话，这将是个很棒的亮点。

<details>
<summary>Original English</summary>

**Speaker A**: I I mean when you have um you know your your next party at the house, I highly recommend just a little or something or I I think it would be like a great fit. It would be a great bit if you had some.

</details>

**Speaker B**: 是这样的。但是，我们在这里关注的是能够大规模进行这种推理的能力。

<details>
<summary>Original English</summary>

**Speaker B**: That's right. Um, but what we're looking at here is the ability to do that reasoning at scale.

</details>

**Speaker A**: 那么推理和 Cerebras 的摩尔定律是什么呢？你们内部是否有过讨论，比如我们在每个 X 时间段内要把这个提升一倍？

<details>
<summary>Original English</summary>

**Speaker A**: And what is Moore's law for inference and for cerebrus? Do you have something internally you discuss as we're going to double this every x time period?

</details>

**Speaker B**: 在我们之前在处理器世界中的所有芯片都遵循摩尔定律。

<details>
<summary>Original English</summary>

**Speaker B**: So all chips prior to us in the processor world followed Moore's law.

</details>

**Speaker A**: 明白了。

<details>
<summary>Original English</summary>

**Speaker A**: Got it.

</details>

**Speaker B**: 然后我们打破了……

<details>
<summary>Original English</summary>

**Speaker B**: And we broke

</details>

**Speaker A**: 每 18 个月翻一番。

<details>
<summary>Original English</summary>

**Speaker A**: doubling every 18 months.

</details>

**Speaker B**: 大约每 18 个月翻一番。

<details>
<summary>Original English</summary>

**Speaker B**: Doubling about every 18 months.

</details>

**Speaker A**: 明白了。

<details>
<summary>Original English</summary>

**Speaker A**: Got it.

</details>

**Speaker B**: 嗯，我们用这款芯片彻底颠覆了它，而且我们开辟了一条全新的轨迹。呃，我的观点是，在接下来的 18 个月里，我们将会远远超过两倍的提升。

<details>
<summary>Original English</summary>

**Speaker B**: Um and we crushed it with this chip and we've carved out a whole new trajectory. And uh my view is in the next 18 months we'll be way over 2x

</details>

**Speaker A**: 有意思。

<details>
<summary>Original English</summary>

**Speaker A**: interesting.

</details>

**Speaker B**: 所以，呃，我认为，呃，在一个架构的早期，你还有很大的空间可以做得比传统的摩尔定律好得多。现在，如果你拥有像 GPU 这样有 20 年历史的架构，那就困难得多了，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: And so, uh, I I think that, uh, early in an architecture, you have room to to do much better than what was traditionally Morris law. Now, if you've got a 20-year-old architecture like the GPU, it's much harder, right?

</details>

**Speaker A**: 你就必须依赖更小的制程节点等因素，对吧？进入下一个晶圆厂节点。

<details>
<summary>Original English</summary>

**Speaker A**: You you have to rely on things like smaller geometry, right? Going to the next fab node.

</details>

**Speaker B**: 但在一个较新的架构中，你还有巨大的空间去学习正在被呈现的工作负载，并进行能给你带来巨大收益的优化。

<details>
<summary>Original English</summary>

**Speaker B**: But in a newer architecture, you have a huge amount of room still to to to learn about the the work that that is being presented and make optimizations that that give you huge gains.

</details>

### 管理人工智能时代的狂飙公司

**Speaker A**: 你是如何管理这家公司的？就像现在在人工智能时代做一名 CEO，嗯，你们有价值 250 亿美元的需求。你必须以极其惊人、令人眼花缭乱的速度进行部署。你必须招人。你必须制定路线图。我并不是想在这里让你感到恐慌。

<details>
<summary>Original English</summary>

**Speaker A**: H how do you run the company? Like just being the CEO now in the age of AI, um you have $25 billion in demand. You have to you have to deploy at an just an incredible blistering pace. You have to hire people. You have to create a roadmap. I don't mean to give you a panic attack here.

</details>

**Speaker B**: 你必须跟上像 OpenAI 这样发展速度快得令人难以置信的公司的步伐。是的。

<details>
<summary>Original English</summary>

**Speaker B**: You have to keep up with somebody like OpenAI who's moving so unbelievably quickly. Yes.

</details>

**Speaker A**: 对。而且他们充满竞争力。你得跟上。

<details>
<summary>Original English</summary>

**Speaker A**: Right. And they're they're competitive. You got to keep up.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Right.

</details>

**Speaker A**: 对。你的硬件、软件、部署必须跟上历史上发展最快的一些组织的步伐。他们是要求很高的客户。

<details>
<summary>Original English</summary>

**Speaker A**: Right. Your hardware, your software, your deployments have to keep up with some of the fastest moving organizations in history. They're demanding customers.

</details>

**Speaker B**: 他们绝对不是，绝对不是好对付的。

<details>
<summary>Original English</summary>

**Speaker B**: They are not they're not pushovers for sure.

</details>

**Speaker A**: 是的。而且未来他们也可能是潜在的竞争对手。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. A and also potentially competitors down the road.

</details>

**Speaker B**: 我觉得，我，我，我认为现在的需求太庞大了，以至于没有任何一块硅片会被闲置，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: I look I I I think there is so much demand right now that that that there is no silicon that will go unused, right?

</details>

**Speaker A**: 但是为什么 OpenAI 不发布 Jalapeno？为什么亚马逊要制造自己的芯片？你看到这种反复出现的趋势了吗？这是一种让你们知道、让黄仁勋和英伟达知道的方式吗？就好像在说，“嘿，我们也能做这个。所以我们需要好的定价。”这是否有点像是在秀肌肉，还是说那就是未来，他们将会进入你们所在的行业？

<details>
<summary>Original English</summary>

**Speaker A**: But why isn't OpenAI releasing Jalapeno? Why is Amazon making their own chips? You see this reoccurring trend? Is it a way to let you know to let Jensen and Nvidia know, hey, we can do this, too. So we we need good pricing. Is it is it a little bit of a flex that way or is that the future that they're going to be in your business?

</details>

**Speaker B**: 不，我，我，我认为没有人喜欢受制于人。并且，我认为 x86 世界里那些超大规模云服务商吸取的一些教训是，他们曾经受制于英特尔。而 GPU 制造商吸取的一些教训是，他们曾经受制于少数几家超大规模云服务商。

<details>
<summary>Original English</summary>

**Speaker B**: No, I I I think nobody likes being dependent and I I think some of the lessons learned by the the hyperscalers of the x86 world is they were dependent on Intel. And uh some of the lessons learned by uh the GPU makers was they were dependent on a small number of hyperscalers.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 然后他们想要更多的客户，所以他们开始着手帮助资助这些新型的云服务（neoclouds）。所以，我，我认为，这主要关乎一个掌控你命运中至少重要一部分的机会。

<details>
<summary>Original English</summary>

**Speaker B**: And they wanted more customers and so they set about to to help fund these neoclouds. And so I I think mostly it's about uh an opportunity to control at least an important part of your destiny.

</details>

**Speaker A**: 明白了。

<details>
<summary>Original English</summary>

**Speaker A**: Got it.

</details>

**Speaker B**: 而且，我认为这是一件非常合理的事情。我觉得你不必非得制造出最快的芯片。你只是不能完全依赖别人的芯片。

<details>
<summary>Original English</summary>

**Speaker B**: And I I think that's a very reasonable thing. I think you don't have to sort of make the fastest chip. You you just can't be entirely dependent on other people's chips.

</details>

### 开源模型与前沿模型之争

**Speaker A**: 这种依赖已经成为一个热门话题。不知道你有没有看过去两周的节目，但我们在过去一年里一直在讨论开源。我非常支持开源，仅仅是因为我很早就开始使用 Open Claude，并很快开始使用 Kimmy（Kimi），然后我就想：“等一下。我正在耗尽我的 Claude tokens，但是这个 Kimmy，我分辨不出它们的区别。然后我们开始对它进行智能路由，突然之间，这些开源大模型开始理解推理，而这种差距……”

<details>
<summary>Original English</summary>

**Speaker A**: And that dependency has become a hot topic. Not sure if you caught the episodes over the last two weeks, but we've been talking over the last year about open source. I've been championing that a lot just because I was early into Open Claw and quickly started using Kimmy and was like, "Wait a second. I'm blowing out my claw tokens, but this Kimmy, I can't tell the difference. And then we started smart routing it and suddenly this open source started to figure out reasoning and the gap has

</details>

**Speaker B**: 在今年突然缩小了。

<details>
<summary>Original English</summary>

**Speaker B**: suddenly closed this year.

</details>

**Speaker A**: 嗯，我，我，你知道，你不想开着你的法拉利去杂货店，对吧？你总有想开你那些有趣的车的时候。

<details>
<summary>Original English</summary>

**Speaker A**: Well, I I you know, you you don't want to take your your Ferrari to the grocery store, right? You you you there there are times you want to drive your fun car.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 对。还有一些时候你想把孩子们塞进车里，并且不用担心他们把麦片条弄得满地都是。

<details>
<summary>Original English</summary>

**Speaker A**: Right. And there are times you want to throw the kids in and and don't worry if they're Cheerios on the floor.

</details>

**Speaker B**: “微型面包车”（Minivan）时间，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Minivan time, right?

</details>

**Speaker A**: 没错，这是“微型面包车”时间。而且，我认为随着用户成熟度的提升，对吧，你将会遇到困难的问题，而那些将是前沿模型（frontier model）要解决的问题。它们将是 OpenAI 要解决的问题。它们将是 Anthropic 要解决的问题。也会是 Gemini 要解决的问题。而在那之后，会有很多普通的问题。对吧？我的意思是，如果你想想一家公司，你知道有多少时间是花在从 Workday 里把东西剪切出来，然后放到另一个单元格里的？是的。

<details>
<summary>Original English</summary>

**Speaker A**: There's minivan time. And and and I think that as the sort of sophistication of the user grows, right, you're going to have hard problems and those are going to be frontier model problems. They're going to be open AI problems. They're going to be anthropic problems. Going to be Gemini problems. And behind that, they're going to be a lot of ordinary problems. Right? I mean, if you think about a company, you know how much time is spent cutting things out of workday and getting it in a different cell for Yeah.

</details>

**Speaker B**: 对。想想看……这种剪切粘贴的经济是真实存在的。

<details>
<summary>Original English</summary>

**Speaker B**: Right. Think about the cutting and pasting economy is real.

</details>

**Speaker A**: 没错。而且这不需要，对吧，这不需要拿金牌的数学水平。不需要。

<details>
<summary>Original English</summary>

**Speaker A**: That's right. And and this doesn't need, right, gold medal math. No.

</details>

**Speaker B**: 这需要的是……

<details>
<summary>Original English</summary>

**Speaker B**: What what this needs

</details>

<!-- chunk 3/8 -->

### 开源模型与主权AI的兴起

**Speaker A**: ……是那种坚如磐石的开源能力。是的。如果你明白我的意思，好吧，我们在 DNA 方面考虑了很多，但大量的 DNA，你要知道，其实并非发明创造，

<details>
<summary>Original English</summary>

**Speaker A**: is sort of rock solid open-source capabilities. Yeah. And if you think about what I mean, well, we've been thinking a lot about it in DNA, but a huge amount of DNA, all right, is not invention,

</details>

**Speaker B**: 对吧？你可能不需要最复杂的智能体来做这件事。最近翻开的另一张牌是，有些人可能对前沿模型的野心有所担忧，也可能担心共享数据会导致数据泄露，以及智能主权的问题。他们会说：“嘿，我们公司要做出选择，也许我们处于一个受监管的行业，比如金融、医疗保健、HIPAA（健康保险便携与责任法案）、你要知道的 FINRA（美国金融业监管局），或者是各种不同的法规——”

<details>
<summary>Original English</summary>

**Speaker B**: right? And you you may not need sort of the most sophisticated agents for this. And another card that's turned over recently is some folks uh maybe have concerns with the ambition of the frontier models and maybe sharing their data data leakage and sovereignty of intelligence and they're saying hey our company is going to choose maybe we're in a regulated industry finance healthcare HIPPA you know FINRA all kinds of different regulations

</details>

**Speaker A**: 我们需要将这些部署在本地。

<details>
<summary>Original English</summary>

**Speaker A**: we need to have this on

</details>

**Speaker B**: 部署在国内。我们需要一个开源版本，以便拥有更多的控制权。是的。而且我认为……

<details>
<summary>Original English</summary>

**Speaker B**: prem domestically and we'd liken an open-source version where we have uh a little bit more control. Yeah. And I I think

</details>

**Speaker A**: 你现在看到这种趋势了吗？

<details>
<summary>Original English</summary>

**Speaker A**: are you seeing that now?

</details>

**Speaker B**: 我们确实看到了。而且我认为 OpenAI 几个月前发布 OSS 12B 是一个明智的决定。那是一个很棒的开源模型。但我认为在美国我们需要更多国产的开源模型。我们需要给世界一个选择，

<details>
<summary>Original English</summary>

**Speaker B**: We are seeing that for sure. And I I think OpenAI made a good call releasing OSS 12B some months back. That was a good open-source model. Um but I think in the US we need more domestic open source models. We need to give the world a choice,

</details>

**Speaker A**: 对吧？对。如果他们现在想运行开源模型，只能选 OSS 12B 或者中国模型。

<details>
<summary>Original English</summary>

**Speaker A**: right? Right. If they want to run open source right now, it's OSS 12B or Chinese models.

</details>

**Speaker B**: Nvidia 有一些……

<details>
<summary>Original English</summary>

**Speaker B**: Nvidia has some in

</details>

**Speaker A**: Nvidia 也看到了同样的机遇来推动开源模型。我认为赋予他们更多的权力可能会是某种……

<details>
<summary>Original English</summary>

**Speaker A**: Nvidia has seen the same opportunity to push open- source models. I I I think giving them more power might might be sort of

</details>

**Speaker B**: 好了，我刚想说，那是你之前打断我的地方，我的理解是黄仁勋（Jensen）的态度就像是：“嘿，我们甚至都不想谈论我们拥有的这些开源模型，因为我们的客户会怎么想，

<details>
<summary>Original English</summary>

**Speaker B**: Well, I was about to that was you cut me off at the past like my understanding was Jensen was like, "Hey, we we don't even want to talk about these open source models we have because our customers,

</details>

**Speaker A**: 对吧？”

<details>
<summary>Original English</summary>

**Speaker A**: right?

</details>

**Speaker B**: “我们现在就要和 Sam、Dario、Elon 竞争了，”

<details>
<summary>Original English</summary>

**Speaker B**: We're now going to be competing with Sam, Daario, Elon,

</details>

**Speaker A**: “还有 Sergey，比如，我们想处于那种境地吗，

<details>
<summary>Original English</summary>

**Speaker A**: uh Sergey, like do we want to be in that position,

</details>

**Speaker B**: 对吧？”

<details>
<summary>Original English</summary>

**Speaker B**: right?

</details>

**Speaker A**: “所以，但我们确实需要这里有更多的冠军企业，而且它是开源的，大家可以分叉（fork）它。” 不过，这会让你处于一个更中立的位置。

<details>
<summary>Original English</summary>

**Speaker A**: So, but we do need some more champions here and it's open source so people can fork it." Um, but that puts you in a more neutral position.

</details>

**Speaker B**: 没错。我们今天运行的，我们运行 GLM，运行 Kimi，运行 Qwen 系列模型，我们也运行 OpenAI 的模型，也就是闭源的那些。我们为葛兰素史克（Galaxos Smith Klein）运行模型，这些模型是他们编写和开发的。我们也为我们在阿联酋的合作伙伴 G42 和 MBZUAI 运行模型。是的。那是他们自己设计的模型。所以，我们拥有非常广泛的多样性。

<details>
<summary>Original English</summary>

**Speaker B**: That's right. We we we run today, we run GLM, we run Kimmy, we run the Quen set of models and we run OpenAI's models, the closed source ones. We run models for say Galaxos Smith Klein, which they wrote and developed. Um, we run models for uh our partner uh in the UAE uh G42 and MBZ UAI. Yeah. Um that are are are their models that they designed. So we we have a a a wide variety.

</details>

**Speaker A**: 所以主权确实是一个趋势。

<details>
<summary>Original English</summary>

**Speaker A**: So sovereignty is a trend.

</details>

**Speaker B**: 主权是一个趋势。而且我认为，政府在 Fable 和 56 方面的行动中，他们说：“哦，哇，让我们先思考一下，然后再行动。”

<details>
<summary>Original English</summary>

**Speaker B**: Sovereignty is a trend. And I think uh the the government's actions with regard to fable and uh uh 56 um where they said, "Oh, whoa, let's think and then we can act."

</details>

### AI 监管、政治极化与安全风险

**Speaker A**: 我认为这在欧洲尤其算是一个警钟。当你看到这些情况发生时，我们国家现在也存在一层党派之争。而且相当激烈。Dario 已经非常明确地表示，你知道的，他不属于这届政府。他们之间的对抗性很强。双方都承认他们现在开始试图解决这个问题了。所以，我认为对于不在这些党派房间里的人来说，很难理解哪些是党派偏见，哪些是政治游戏。但是，你是否相信他们发布的东西对网络战、对网络攻击来说真的是危险的？如果你要评价一下 Dario 的“不沟通”策略——因为他通常是个非常热情洋溢的沟通者，我认为这是一种外交辞令——但要有一个按计划推出的发布方案，

<details>
<summary>Original English</summary>

**Speaker A**: Um I I think sort of particularly here in Europe was a bit of a wakeup call. And when you saw this going down, there's a layer of partisanship in our country right now. It's pretty fervent. Daario is pretty explicitly, you know, not part of this administration. They they've been very adversarial. Both sides have been have admitted that they're starting to work it out now. So, it's hard, I think, for us not being in the room with these parties to understand what's partisanship, what's games here. But do you believe that what they released was truly dangerous for cyber warfare, for cyber attacks, and that if you were to rate Daario's not communication, because he's a very effrovescent communicator, um I think is a diplomatic way to say it, um but to have a scheduled rolled out release,

</details>

**Speaker B**: 对吧？我们先把政府的控制权放在一边，但你认为在现阶段这对我们来说是明智之举吗？你认为那里真的存在重大威胁吗？

<details>
<summary>Original English</summary>

**Speaker B**: right? We'll put aside the government's control of it, but do you think that is is a wise thing for us to do at this point? And do you think it's there was actually a major threat there?

</details>

**Speaker A**: 真正有趣的是，我以前从未见过这种情况，

<details>
<summary>Original English</summary>

**Speaker A**: So what's interesting is I hadn't seen it before,

</details>

**Speaker B**: 对吧？而且我认为，你知道，如果我们退后一步问，这是否合理？我不知道这是否是合适的时机，但是在某个时期

<details>
<summary>Original English</summary>

**Speaker B**: right? And I I think you know if we just step back and say is it reasonable I don't know whe whether this was the right time but at a time

</details>

**Speaker A**: 当某个模型在思维上具有足够的创造力，以至于它构成了有意义的威胁时，政府要求分阶段推出模型。

<details>
<summary>Original English</summary>

**Speaker A**: that that that a model is sufficiently uh creative in its thinking that it poses a meaningful threat for the government to say we'd like you to roll it out in steps.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 在我看来，这似乎并非不合理。

<details>
<summary>Original English</summary>

**Speaker A**: Now this doesn't seem unreasonable to me.

</details>

**Speaker B**: 完全没有。

<details>
<summary>Original English</summary>

**Speaker B**: Not at all.

</details>

**Speaker A**: 对吧。我的意思是，我们在对待强效药物时也是这样做的。

<details>
<summary>Original English</summary>

**Speaker A**: Right. I mean we we do this with powerful pharmaceuticals.

</details>

**Speaker B**: 对。我的意思是，我们当然不鼓励搞什么七年的临床试验，或者弄出大量文书工作，还有那些堆积在 FDA（美国食品药品监督管理局）身上的繁文缛节，

<details>
<summary>Original English</summary>

**Speaker B**: Right. We we we'd like I mean we're certainly not encouraging seven years of trial and the amount of paperwork and all the garbage that has acred to the FDA,

</details>

**Speaker A**: 但是对于一项强大的新技术，说一句：“嘿，伙计们，至少让我们在政府内部进行一些红队测试（red teaming），这样我们就能知道我们的防御系统是否能拦截它”，这似乎并不不合理。

<details>
<summary>Original English</summary>

**Speaker A**: but with a powerful new technology, it certainly doesn't seem unreasonable to say, "Hey guys, um let's at least do some red teaming at the government so we know our defenses can block this."

</details>

**Speaker B**: 是的。我们检查过，我们检查过

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Have we checked Have we checked

</details>

**Speaker A**: 国家的基础设施了吗，比如

<details>
<summary>Original English</summary>

**Speaker A**: the infrastructure of the country like

</details>

**Speaker B**: NSA（国家安全局）的？我们检查过基础设施的状况了吗？对。你能不能给我们两到三周的时间来修补发现的任何明显漏洞？这似乎

<details>
<summary>Original English</summary>

**Speaker B**: of the NSA? Have we checked the infrastructure up? Right. And can you give us two or 3 weeks to patch any obvious holes that are found? This doesn't seem to be

</details>

**Speaker A**: 对于政府来说并不是一个不合理的要求。

<details>
<summary>Original English</summary>

**Speaker A**: an unreasonable thing for the government to ask.

</details>

**Speaker B**: 对。但是在这个极其两极分化的时代，

<details>
<summary>Original English</summary>

**Speaker B**: Right. We But we in this very polarized time

</details>

**Speaker A**: 我们还在此之上附加了一层看法：“哎呀我的天，这是特朗普总统在做这件事。” 然后你不得不去想，如果换成 AOC（亚历山德里娅·奥卡西奥-科尔特斯）总统，或者处于这两个极端之间的任何一位总统呢？

<details>
<summary>Original English</summary>

**Speaker A**: put on top of it, well, oh my god, it's President Trump doing it. And then you have to think, well, what if it was President OA AOC or President anybody in between the the two extremes?

</details>

**Speaker B**: 我觉得极化造成了极大的伤害。它伤害了清晰的思考，

<details>
<summary>Original English</summary>

**Speaker B**: I I think the polarization hurts a great deal. It hurts clear thinking,

</details>

**Speaker A**: 对吧？它阻碍了清晰的思考，双方都会做一些蠢事，也会做一些真正聪明的事。

<details>
<summary>Original English</summary>

**Speaker A**: right? It hurts clear thinking and and and both sides are going to do some dumb things and some really smart things.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Right.

</details>

**Speaker A**: 对。而且实际上，我发现政府里的人都在非常努力地工作。

<details>
<summary>Original English</summary>

**Speaker A**: Right. And in fact, what I found is that the people in the government are are trying really hard.

</details>

**Speaker B**: 嗯。

<details>
<summary>Original English</summary>

**Speaker B**: Um

</details>

**Speaker A**: 普通的基层员工，

<details>
<summary>Original English</summary>

**Speaker A**: the rank and file,

</details>

**Speaker B**: 普通的基层员工都在非常努力地工作，而且事情进展很快。而且我认为，能够把一些政治极化放在一边，然后说“我们如何以一种合理的方式来做这件事？”是很重要的。我的意思是，我们希望 Dario 和 Sam 像疯了一样竞争。这太棒了，对吧？这对技术有好处。这对于企业家们看到即使有着数千人的规模，你依然能够不断取得成就，是有好处的。对。

<details>
<summary>Original English</summary>

**Speaker B**: the rank and file are trying really hard and this is moving fast. And I I think that that an ability to to set aside some some of the the polarization and say h how do we do this in a reasonable manner? I mean we we want Dario and Sam competing like crazy. It's awesome, right? It's good for the technology. It's good for it's good for entrepreneurs to see even with thousands of people this is what what you can continue to achieve. Right.

</details>

**Speaker A**: 对。这就是谷歌在后面踢他们的屁股，让他们变得更敏锐。因为这样，亚马逊进步了，所有人都变得更好了。我们希望如此，我们肯定不想成为一个首先想到就是去监管的地区。

<details>
<summary>Original English</summary>

**Speaker A**: Right. This is Google in the ass made them get sharper. Amazon got everybody got better because of that. We want that and we certainly don't want to become sort of a region where the first thing we want to do is regulate it.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Right.

</details>

**Speaker A**: 对。但随着它变得越来越强大，行业本身确实应该在自我监管方面做得更好。而且看起来他们似乎正在开始这个过程，但当时的沟通可能不够。

<details>
<summary>Original English</summary>

**Speaker A**: Right. But as it gets more powerful and the industry really should do a better job of regulating itself perhaps and and it did seem like they were starting that process but then the communication was lacking maybe.

</details>

**Speaker B**: 是的。你知道，我认为他们不仅是在激烈地竞速，而且他们也是边走边发明的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Uh, you know, I I think not only are they racing hard, but they're inventing this as they go too.

</details>

**Speaker A**: 是的。对。并没有现成的剧本。没有。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Right. There's not a playbook. No.

</details>

### AI 模型的护栏设计与安全漏洞的教训

**Speaker B**: 对。他们正在发明……我们说：“哦，加上护栏（guardrails）就行了。”好吧，他们必须自己去设计那些护栏。

<details>
<summary>Original English</summary>

**Speaker B**: Right. They're inventing the we we say, "Oh, just put on guardrails." Well, they have to design the guard rails.

</details>

**Speaker A**: 当然。

<details>
<summary>Original English</summary>

**Speaker A**: Sure.

</details>

**Speaker B**: 对。护栏是会产生影响的。嗯，你知道，速度快带来的一个好处是它让护栏变得不那么痛苦。我们在过去六周里发现了这一点。是的。那就是护栏本身可能会增加时间，让人感觉更慢，因此像我们这样快速的芯片（chips）确实可以提供帮助。所以，他们是在与竞争对手赛跑。他们也是在与自己追求伟大的感觉赛跑。

<details>
<summary>Original English</summary>

**Speaker B**: Right. They the guardrails have an impact. Um, you know, one of the things that fast does is it makes the guard rails less painful. And so that that we we discovered that in the last six weeks. Yeah. is that the very guard rails can add time and make it feel slower and so fast ships like ours can really help that. But so theyre racing against competition. They're racing against their own sense of greatness.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 对。这甚至可能是这里最大的驱动力。而且我认为他们确实在认真思考如何做正确的事情。所有这些因素都混合在这个大熔炉里。而且有时候你处于这一边而不是那一边。而且……

<details>
<summary>Original English</summary>

**Speaker B**: Right. Which is maybe even the biggest driver here. A and I think that they're in earnest trying to think about how I do the right thing. A and all of those are are are mixed in this bucket. and and sometimes you're on one side rather than the other. And

</details>

**Speaker A**: 是的，正如你所说，这是第一次，对吧？当 3.5 出来的时候，它不像我们在使用 ChatGPT 2.5、3.5 的时候，它并没有让网络崩溃，但在和 Palo Alto Networks 的 Nikesh 交谈时，我问他：“嘿，你会如何评价这个？” 他说：“我们把它拿来对付我们的软件，结果我们发现了以前没意识到的漏洞，

<details>
<summary>Original English</summary>

**Speaker A**: yeah, and as you're saying, this is a first time, right? When we when 3.5 came out, it wasn't like when we're using chatbt 2.5, 3.5, it was taking down networks, but in talking to Nicash uh from PaloAlto Networks, I asked him like, "Hey, well, how would you grade this?" And he said, "We put it against our software and we found bugs we were not aware of and

</details>

**Speaker B**: 它把它们秒杀了。”

<details>
<summary>Original English</summary>

**Speaker B**: it killed them."

</details>

**Speaker A**: 是的。他说我们不得不停下手头的所有工作，花了六周时间打补丁，

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. He said we had to stop everything we're doing and do patches for 6 weeks,

</details>

**Speaker B**: 对吧？那时候你就明白了，对吧？我的意思是，Nikesh 领导着，也许可以说是领先的安全软件公司，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: right? And and that's when you know, right? I mean, Nick leads, you know, maybe the leading security software firm, right?

</details>

**Speaker A**: 当它在一个小时内发现了数十个关键的安全漏洞时，你会觉得，哇，这是一个非常强大的工具

<details>
<summary>Original English</summary>

**Speaker A**: And when it finds in an hour, right, tens of critical opens, you're like, whoa, this is a powerful tool

</details>

**Speaker B**: 我们需要思考，也许你先向一个群体展示它，对吧？也许你……我不知道正确的方法是什么，但是……

<details>
<summary>Original English</summary>

**Speaker B**: and we need to think and and maybe you you show it to a a group first, right? May maybe you I I don't know what the right thing is but

</details>

**Speaker A**: 是的，我是说红队测试（red teaming）……而且我们一直都有这种机制，就像当你发布新版本的操作系统时，你知道当你用 iPhone 时，你可以说我想参与测试版（beta）。

<details>
<summary>Original English</summary>

**Speaker A**: yeah I mean red teaming and uh we've always had just when you were releasing the new version of um an operating system you know when you have your iPhone you can say I want to be part of the beta.

</details>

**Speaker B**: 没错。你也知道的，对吧？而且还有两层其他的测试版参与者，作为普通消费者你甚至都没有机会选择加入。那些是用于安全测试的。那些是为了确保你不会丢失数据或者造成数据损坏。

<details>
<summary>Original English</summary>

**Speaker B**: That's right. you know, right? And there's like two other baiters that you don't even get the chance to opt into as consumers. And those ones are for security. Those ones are for, you know, making sure you don't lose your data or data.

</details>

**Speaker A**: 就是那样。

<details>
<summary>Original English</summary>

**Speaker A**: That's

</details>

<!-- chunk 4/8 -->

### 应对未知的风险与黑天鹅事件

**Interviewer**: 对，可能消失、泄露或者损坏，诸如此类各种各样的情况。

<details>
<summary>Original English</summary>

**Interviewer**: right. Disappear or leak or corruption. Any number of these things.

</details>

**Andrew**: 我觉得我们也可以预见到，将会发生大规模的数据泄露。

<details>
<summary>Original English</summary>

**Andrew**: I think we can also know that that there will be a massive data leak.

</details>

**Interviewer**: 当然，我们很清楚这一点。是啊。

<details>
<summary>Original English</summary>

**Interviewer**: Of course, we know this. Yeah.

</details>

**Andrew**: 没错。这就好像沃伦·巴菲特在谈到再保险行业时说的，你知道会有糟糕的事情发生，只是不知道在什么时候。

<details>
<summary>Original English</summary>

**Andrew**: Right. And it's like uh Warren Buffett talked about the reinsurance industry that you know something bad's going to happen. You don't know when.

</details>

**Interviewer**: 是的，所以你必须为此攒钱，对吧？你把钱存起来买再保险。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. But you got to save up for it, right? You put money away for reinsurance,

</details>

**Andrew**: 但终究会有龙卷风，会有大地震的。我的意思是，我们知道这些，并且可以尽最大努力去计划，但终究会有大规模的系统漏洞，我们必须提前做好心理准备。我们必须去思考它，思考在那个时刻应该采取怎样的正确回应，某种程度上也是为具体情况未知但必定会发生的未来做好准备。总的来说，我们非常确定有些事情是会发生的。

<details>
<summary>Original English</summary>

**Andrew**: but there will be a tornado. There will be a massive earthquake. I mean, we we know this and we can do our best to plan, but there'll be a massive breach and they there'll be and we we have to steal ourselves in advance and we have to think about it and think about the right response at the time and sort of prepare ourselves for a future that is in specific unknown. But in general, we're pretty sure it's something's going to happen.

</details>

**Interviewer**: 肯定会发生点什么，并且通常来说它会是一只黑天鹅，对吧？根据定义，它将是我们没有考虑到的事情，或者是我们根本不知道该去问的问题。但即便是知道存在一些“未知的未知”，也是一个很好的起点。

<details>
<summary>Original English</summary>

**Interviewer**: Something will happen and yeah, it's typically a black swan, right? By definition, it's going to be something we didn't consider or a question we didn't know to ask, right? But but even knowing that there's some unknown unknowns is a useful place to start.

</details>

### 用人工智能弥补思维盲区

**Andrew**: 是的。有什么是我们没有问自己的？

<details>
<summary>Original English</summary>

**Andrew**: Yeah. What are we not asking ourselves?

</details>

**Interviewer**: 没错。凭借推理能力，人工智能将能告诉我们：“嘿，愚蠢的人类。”

<details>
<summary>Original English</summary>

**Interviewer**: That's right. With reasoning, the AI is going to be able to tell us, "Hey, schmuck humans."

</details>

**Andrew**: 没错。顺便告诉你，以下是你没有考虑到的部分。现在这成了我写提示词（prompt）时的结束语。我会告诉它：我需要你给我写一个能帮我做这个趋势预测的提示词，举个例子。然后我总会在结尾说，“请检查你的工作结果”。

<details>
<summary>Original English</summary>

**Andrew**: That's right. By the way, here's what you're not thinking about. This is now my closing sentence when I do my prompting is I need you to make me a prompt that will help me do this trend scouting for an example. And then I always say at the end um please check your work

</details>

**Interviewer**: 对，然后告诉我，在实现我的目标方面，有什么是我没有考虑到的。并且在你每次运行这个任务时，都向我提出几个问题。这就改变了一切，因为这就好比它在说：“顺便提一句，我检查了我的工作，这部分是不对的。” 对吧？“所以我在想，你要不要我也把这个做了？”像 Perplexity 这样的一些工具会自动做这件事，它们会给你提供接下来的三个提示词。但是如果你给它非常明确的指示，天哪，它在这方面做得非常好。

<details>
<summary>Original English</summary>

**Interviewer**: right and uh then tell me what I haven't considered in terms of my goals and uh give me ask me some questions every time you run the job and that has changed everything because it's like I checked my work by the way this was incorrect right and uh I'm wondering hey uh would you like me to also do this and some of the tools like perplexity do that automatically they give you your next three prompts but if you give it explicit instructions My lord is it um good at that.

</details>

**Andrew**: 所以，你知道的，在过去的十年里，当我在筹集资金的时候，在对话接近尾声时，我认为我遇到过的最聪明的一个问题是，有人问我：“你听过的、而我刚才没有问到的最聪明的问题是什么？”

<details>
<summary>Original English</summary>

**Andrew**: So, you know, over the course of the last 10 years as I was raising money, I I thought one of the smarter questions I got at the end of a conversation where someone asked, "What was the smartest question you heard that that wasn't covered by what I asked?"

</details>

**Interviewer**: 这简直太棒了。现在，这是一个充满好奇心、勤于思考、谦逊，并且试图利用这一点来全面了解这个领域的人。而且，如果你能在某种程度上这样去问人工智能……

<details>
<summary>Original English</summary>

**Interviewer**: It's incredible. right now. Now, that's somebody who's curious and thinking and humble and and trying to sort of use this to get a picture of of the space and and to the extent that you can ask the AI that

</details>

**Andrew**: 而且它能够在某种程度上拓宽你的视野，告诉你“也许你应该问这个问题才能成为这方面的专家？” 或者说，“一个博士级别的提问者会问什么样的问题？”又或者是“一块数学金牌？” 我的意思是，我认为这些都是那种你甚至不知道该怎么去问的问题。

<details>
<summary>Original English</summary>

**Andrew**: and and and that it can sort of broaden your your view, you know, maybe what question should I have asked to to be an expert in this? What what what would a a PhD level uh uh questioner ask of this or a gold medal math? I mean I I think those are the sort of questions that you you you know you don't even know how to ask

</details>

### 通用人工智能（AGI）已经到来

**Interviewer**: 你知道的，如果你开始思考通用人工智能（AGI）和超级智能……你知道，它们虽然只是定义，但我认为记住它们很重要，因为它们就像是一个个航路点。

<details>
<summary>Original English</summary>

**Interviewer**: which you know if you start thinking about AGI and super intelligence um you know they're just definitions but they're important definitions I think to kind of keep in mind because they're way points.

</details>

**Andrew**: 没错。至于 AGI，我想，我也猜想你会同意我的观点——我们已经实现了它，只是我们还没有将它完全部署而已。我们现在就已经拥有通用人工智能了。当我们谈论这些关于推理的时刻，以及它有能力变得和任何人一样聪明时，这种感觉就很明显。

<details>
<summary>Original English</summary>

**Andrew**: That's right. And AGI I think I suspect you'll agree with me that we've hit it. we just haven't exactly deployed it fully. We we we have artificial general intelligence now. It feels like when we're talking about these reasoning moments and you know the the the ability for it to be as smart as any human but

</details>

**Interviewer**: 让我们来谈谈这个。按照我们在 20 年前对它的任何一种定义，我们现在都已经达到了。

<details>
<summary>Original English</summary>

**Interviewer**: let's talk about by any definition we had 20 years ago we've hit it.

</details>

**Andrew**: 是的。

<details>
<summary>Original English</summary>

**Andrew**: Yes.

</details>

**Interviewer**: 没错。我的意思是，你想想看，图灵测试已经被彻底打破了。是的。

<details>
<summary>Original English</summary>

**Interviewer**: Right. I mean if you think about oh there's a touring test blew it away. Yes.

</details>

**Andrew**: 我的意思是，你去回想一下，在过去任何一个时期——无论是 10年、15年、20年、30年、40年，还是 50年前，不管我们之前提出的是怎样的定义，对吧？

<details>
<summary>Original English</summary>

**Andrew**: I mean, you think about that that any period of time sort of 10, 15, 20, 30, 40, 50 years ago, we we we any definition we would have previously put forward, right?

</details>

**Interviewer**: 我们都已经远远超越它了。所以，这就回到了我们之前提到的观点：在 20 年前，我们知道该问什么问题吗？科幻小说家们，你知道的，他们发表了他们的看法，而我们则回答了他们所有的问题。

<details>
<summary>Original English</summary>

**Interviewer**: We've blown past it. And so, which goes back to our previous point of like, do we know the questions to ask 20 years ago, science fiction authors, you know, had their say and we answered all their questions, right?

</details>

**Andrew**: 如果他们今天看到这些，他们会说：“好吧，我没问题可问了。我提不出问题了，抱歉。”这就是为什么某种程度上我们需要倾听那些有时候听起来很边缘化的人的声音。

<details>
<summary>Original English</summary>

**Andrew**: If they were to look at this today, they'd be like, "Well, I'm out of I'm out of questions. I'm out of questions. Sorry." And that's where sort of the the sort of listening to people who we who sound sometimes like they're on the fringe, right?

</details>

**Interviewer**: 对吧？八年或者十年前，当 Ilya 谈到安全性的必要性时，你可能会想：“什么情况？” 但他完全是对的。

<details>
<summary>Original English</summary>

**Interviewer**: When when when Ilia was talking eight or 10 years ago about the need for safety and then and you're like, "What?" And dead right.

</details>

**Andrew**: 是的。

<details>
<summary>Original English</summary>

**Andrew**: Yeah.

</details>

**Interviewer**: 对。当埃隆·马斯克（Elon Musk）谈论制造火箭并将运载火箭的成本降至接近于零时，你会说：“什么？” 然后它就成了现实。现在你能看到这些成果了，我认为这也是为什么现在作为一个技术从业者是一件非常有趣的事情。

<details>
<summary>Original English</summary>

**Interviewer**: Right. When when when Elon was talking about building rockets and driving the cost to to to near zero of of of a launch vehicle, you're like, "What?" And there it is. And now you can see and that's I think that's why it's really fun to be a technologist now.

</details>

### 递归学习与超级智能的崛起

**Andrew**: 没错，而且具体到这些工具上，你知道，我们正在谈论如何构建所有这些工具，然后这些工具正在这种递归循环中开始自我构建。

<details>
<summary>Original English</summary>

**Andrew**: Well, and with these tools specifically, you know, we're talking about building all these tools and then the tools are starting to build themselves in this recursive loop.

</details>

**Interviewer**: 没错。

<details>
<summary>Original English</summary>

**Interviewer**: That's right.

</details>

**Andrew**: 我们才刚刚开始看到人们在应用这种循环机制。事实上，“loop maxing（循环最大化）” 这个词，当初我在做趋势预测的时候，它就不断提取到“loop looping（循环往复）”，也不断提取到“maxing（最大化）”相关的内容，于是它为我创造了一个流行词：“loop maxing”，对吧？然后很神奇地……

<details>
<summary>Original English</summary>

**Andrew**: We're kind of just starting to see people apply loops. Uh, in fact, loop maxing became when I was doing my trend, when I did my trend thing, it kept picking up loop looping and it kept picking up the maxing stuff and it created a buzz word for me, loop maxing, right? And then it magically

</details>

**Interviewer**: 人们也开始谈论起“loop maxing”了，我当时就觉得：“哇，这太不可思议了。”它预见到了其他人类会想出这个词。不过，请您稍微谈谈“递归（recursive）”，以及通向超级智能之路吧。Andrew，关于超级智能、它对人类意味着什么、我们将如何定义它以及我们将如何体验它，你有什么样的看法吗？

<details>
<summary>Original English</summary>

**Interviewer**: people started talking about loop maxing and I was like, "Wow, this is really weird." It anticipated that this would other humans would come up with this word. But talk a little bit about recursive and then the road to super intelligence. And do you have a way Andrew that you think about super intelligence and what it will mean for humanity and how we will define it and how we'll experience it? Yeah.

</details>

**Andrew**: 我认为让我们从“loop maxing”或者说递归学习开始说起吧。我想……Sam 和 Ilya，以及后来的 Dario 和 Dennis，他们在五年或六年前所看到的是，强大的递归收益呈现指数级增长，对吧？你做得更好，然后你再做一次。如果你继续获得收益，那条曲线的斜率是非常陡峭的。

<details>
<summary>Original English</summary>

**Andrew**: I I I think let's begin on on on loop maxing or sort of recursive learning. I I I think um I think what what what Sam and Ilia and then later Daario and and and Dana Dennis saw um six years ago or five years ago was that um powerful recursive gains are are exponential, right? you get better, you do it again. And if you continue to get gain, the the the the slope of that curve is so steep.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Andrew**: 而且我们现在才刚刚开始看到这一点。

<details>
<summary>Original English</summary>

**Andrew**: And that um we're just beginning to see that now.

</details>

**Interviewer**: 你问它一个问题，你从结果中学习，你要求它再做一次，结果会变得更好，并且会添加更多的信息。你的答案变好了。你再要求它做一次，它涵盖了更多的材料。而这种循环产生的，不是好一点点的答案，而是好得多的答案。

<details>
<summary>Original English</summary>

**Interviewer**: You ask it a question, you learn from the results, you ask it to do it again, it the results get better and more information is added. Your answer gets better. You ask it to do again, it covers more material. And the these sort of loops are producing sort of not a little bit better answers but vastly better answers.

</details>

**Andrew**: 是的。而且那将拥有极其巨大的力量，因为我们完全不知道它的终点在哪里，对吧？

<details>
<summary>Original English</summary>

**Andrew**: Yeah. A and that is enormously powerful because we don't quite know where it ends, right?

</details>

**Interviewer**: 你不断地向它投入计算资源。我的意思是，它的答案能好到什么程度？

<details>
<summary>Original English</summary>

**Interviewer**: You keep throwing compute at it. I mean, how much better does the answer get?

</details>

**Andrew**: 你知道的，可能会遇到我们用光了所有的 Token，或者超出了我们的预算等情况，但天哪，我想说，指数级增长什么时候才会停止？或者答案会一直向上、一直变得更好吗？

<details>
<summary>Original English</summary>

**Andrew**: You know, we we run out of tokens or our budget or or or but but holy cow. I mean, when does the exponential stop or does the answer keep going up and up and up to the right?

</details>

**Interviewer**: 是啊。而且这在当下是一个非常有趣的心智上的问题。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. And that's sort of an enormously interesting intellectual question right now.

</details>

**Andrew**: 是的。就像，什么时候我们会没有问题可解决？并且……

<details>
<summary>Original English</summary>

**Andrew**: Yeah. Like when do we run out of problems to solve and

</details>

**Interviewer**: 嗯，没错。而且，到什么时候，这些问题不再是简单的智力或者学术上的问题，而变成了关于人的问题？

<details>
<summary>Original English</summary>

**Interviewer**: Well, that's right. And and when are are the the problems no longer sort of intellectual problems and they're now people problems?

</details>

**Andrew**: 是啊。

<details>
<summary>Original English</summary>

**Andrew**: Yeah.

</details>

**Interviewer**: 对吧。比如如何组织人员去完成人工智能要求做的事情。

<details>
<summary>Original English</summary>

**Interviewer**: Right. How to organize people to to get done what the AI asked for.

</details>

**Andrew**: 没错，对的。我的意思是，正如你所知，在经营你的公司时，你的很多问题并不是什么困难的学术或智力问题。它们是人们如何一起合作的问题。

<details>
<summary>Original English</summary>

**Andrew**: Right. Right. I mean, as you know, in running your company, a lot of your problems aren't hard intellectual problems. They're people working together problems.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Andrew**: 对。还有你说的……动力。

<details>
<summary>Original English</summary>

**Andrew**: Right. And you motivation.

</details>

**Interviewer**: 动力。作为一名领导者，你要花很多时间在团队身上喷洒“WD40润滑剂”。

<details>
<summary>Original English</summary>

**Interviewer**: Motivation. You spend a lot of time as a leader spraying WD40 on your team.

</details>

**Andrew**: 对。

<details>
<summary>Original English</summary>

**Andrew**: Right.

</details>

**Interviewer**: 没错。就是为了这样减少摩擦，并且……我们如何从人工智能那里学习这些？我们如何从人工智能那里获得对人类行为的洞察？而且我认为，当世界模型开始观察人类行为时，这就是它们将给我们带来的一些东西。

<details>
<summary>Original English</summary>

**Interviewer**: Right. It just so so friction is reduced and um how do we learn about those from AI? How do we get behavioral insight from from AI? And and I think that's some of the things the world models are going to bring us as they begin to watch human behavior.

</details>

**Andrew**: 是的。我们甚至还没聊到那一点。这将是下一次采访的话题了。但是，当这些东西跳出屏幕，对吧？当它们处于真实世界中，并且递归过程开始时，它们不仅是尝试解决数学问题，并且，你知道，人类最困难的问题……而是说，“嘿，你知道吗，外面有一个不可思议的世界，比如这里是凡尔赛宫”，对吧？你就会像是：“现在我们在说，给我建造一个新版本的 Salesforce，” 然后我们可能会说：“嘿，你知道吗，我想要一个凡尔赛宫。我在得克萨斯或者内华达州某处有一百英亩地，我只需要派一千个 Optimus（特斯拉人形机器人）去那里，给我建一座凡尔赛宫出来。”对吧？这听起来像是在天方夜谭，但那就是凡尔赛宫。

<details>
<summary>Original English</summary>

**Andrew**: Yeah. We didn't even get to that. This is going to be for another interview. But um when these things jump off the screens, right, and they're in the real world and the recursiveness starts, not trying to solve math problems and right, you know, humanity's most difficult ones, but hey, you know, there's an incredible world out here and here's the palace of Versailles, right? You're just like now we're like make me a new version of Salesforce and we're like hey you know what I'd like a palace of Versailles I've got a hundred acres somewhere out Texas or Nevada I'll just send a thousand optimistes out there make me the Palace of Versailles right sounds fantastical but the Palace of Versailles

</details>

<!-- chunk 5/8 -->

### AI与跨代际学习的加速

**Jason**: 对于那些早于它一千年生活的人来说，这似乎是天方夜谭。

<details>
<summary>Original English</summary>

**Jason**: would seem fantastical to people who lived a thousand years before it

</details>

**Andrew**: 我想，对于那些建造它的人来说，它同样是天方夜谭。

<details>
<summary>Original English</summary>

**Andrew**: and it was fantastical I think to the people who built it.

</details>

**Jason**: 是的。没错。即使对建造者而言，我想他们在建造的过程中自己都会对此感到敬畏。

<details>
<summary>Original English</summary>

**Jason**: Yeah. Right. Even to the builders, I I think they were awed at it as they built it.

</details>

**Andrew**: 是的，这是一种复利效应。他们在不断积累着递归式的学习经验。

<details>
<summary>Original English</summary>

**Andrew**: Yeah. They're compounding. They're compounding recursive learning.

</details>

**Jason**: 没错，并且跨越了几个世代。我们之前聊过，你提出了一个极其深刻的见解：在建造这座建筑的过程中，你们经历了世世代代的石匠传承。

<details>
<summary>Original English</summary>

**Jason**: That's right. A and generations. We talked about you had a really such a great insight of in building this place, you had generations of masons.

</details>

**Andrew**: 是的，我想在所有这些大型工程项目中，通常会有一些专家家族，你在你的父亲或叔父手下当学徒，当你们接手一个需要耗时 50 年、70 年甚至 100 年的工程时，你们可能要经历同一个家族的三代或四代人，对吧？同一个石匠家族在同一个建筑结构上代代相传地工作，并在这个过程中传递着知识和新的创新，对吧？这正是我们在此次新模型及你们正在构建的基础设施中所模拟的模式。当你仔细思考这一点时，真的觉得不可思议。

<details>
<summary>Original English</summary>

**Andrew**: Yeah. I I think in in in all these large projects um often there were families uh who were specialists who you and uh you you apprenticed under your father, your uncle and when you had a project that took 50 or 70 or 100 years, you might have three or four generations of the same family, right? The same stonemason family working on the same structure and passing on passing on the learnings, new innovations, right? which is what we've modeled with this new models and and what you're building in the infrastructure. It's pretty incredible when you think about it.

</details>

**Jason**: 尤其是当我们坐在这里探讨时。我的意思是，我认为人类学习的瓶颈在于，它通常只能以一个“世代”的步伐来推进。像大象以及其他大型哺乳动物一样，我们的一代人不是几天，而是每 15 到 20 年才更迭一次。而如果你想跨越世代以极快的速度推进，你就会希望它们像果蝇（Drosophila）一样发生。你恨不得一天就能更迭两代。

<details>
<summary>Original English</summary>

**Jason**: That's right. Especially when we're sitting here and the and that's what I mean I I think the the problem with human learning is um it often moves it at the pace of a generation. uh and like uh elephants and other large mammals, we don't have generations but every 15 or 20 years. And if you want to move really quickly across generations, you want them happening more like Drosophili, like fruitfly. You want two a day.

</details>

**Andrew**: 是的。

<details>
<summary>Original English</summary>

**Andrew**: Yeah.

</details>

**Jason**: 没错。你在遗传学中就能看到这一点，这就是为什么我们在遗传学中研究它们，因为编码在 DNA 中的学习进化过程，你可以通过它们在数千个世代中进行研究。

<details>
<summary>Original English</summary>

**Jason**: Right. Then and you see that in genetics, that's why we study them in genetics because learning encoded in the DNA, you can study over thousands of generations.

</details>

**Andrew**: 我认为我们在人工智能领域正在获得与之等效的体验。我们在如此短的时间内，正在获得相当于数千代人的快速学习迭代。

<details>
<summary>Original English</summary>

**Andrew**: And I I think that what we're getting is that equivalent in AI. We're getting sort of learning so quickly over the equivalent of thousands of generations.

</details>

**Jason**: 是的。达尔文如果看到了，绝对会为这种进化的速度感到敬畏。

<details>
<summary>Original English</summary>

**Jason**: Yeah. Darwin would be in awe of this uh pace evolution.

</details>

**Andrew**: 完全正确。

<details>
<summary>Original English</summary>

**Andrew**: That's exactly right.

</details>

**Jason**: 你可以这样想，我还记得当我在攻读心理学学位时，他们教我们关于“范式（paradigms）”的概念，我当时一直试图理解范式是如何发生转变的，然后我的教授对我说：“Jason，你必须明白，范式本身是不会消亡的。”

<details>
<summary>Original English</summary>

**Jason**: You think about it as there was I remember when I was getting my psychology degree and they were teaching us about paradigms and I was like trying to understand how the paradigms shifted and the professor said to me uh Jason uh what you have to understand is paradigms don't die.

</details>

**Andrew**: 它们不会消亡。

<details>
<summary>Original English</summary>

**Andrew**: They don't.

</details>

**Jason**: 消亡的是人。

<details>
<summary>Original English</summary>

**Jason**: People do.

</details>

**Andrew**: 没错。

<details>
<summary>Original English</summary>

**Andrew**: That's right.

</details>

**Jason**: 这就是弗洛伊德、斯金纳和荣格这些人的情况，只有等到他们离世，范式才得以更替。

<details>
<summary>Original English</summary>

**Jason**: And that's how Freud he and Thomas Freud and Skinner and Young like it took them dying.

</details>

**Andrew**: 没错。需要一代人去质疑它，而那通常是 20 年，有时是 40 年的时间，因为他们的学生在很长一段时间里依然把持着领导地位，直到有人站出来说，“也许我们可以换种方式做”。我认为你现在看到的这种迭代，实际上是代际鸿沟的一种缩短，学习的速度变得如此之快。和你交流总是非常愉快，因为首先，你的探讨在学术上非常严谨，但在面对这个世界时，你又充满了无与伦比的乐观与活力。看到你对这项技术抱有如此乐观的态度，并且你能以如此深思熟虑的方式去构建它，我感觉棒极了。我认为，对于那些不断听到关于人工智能、失业以及各种恐怖故事的人来说，他们需要明白，有像你这样的人在以一种极其深思熟虑的方式构建这项技术，这将会为人类带来难以想象的净收益。是的，我们有望借助这项技术，让我们的孩子，或者他们认识的任何人，都不再死于癌症。

<details>
<summary>Original English</summary>

**Andrew**: That's right. It took generation question it and that was 20 years sometimes 40 years as their students maintained positions of leadership until someone said maybe we could do it differently and I I think what you're seeing is this iteration is a shortening of the the the intergeneration gap and the learning is so fast. It's uh always so great to talk to you because uh one it's just intellectually um uh so your your approach to it is so intellectually rigorous but also um with so much poom in the world. I I feel so good that you're such an optimist about this technology and you're building it with such thoughtfulness and it I think for people who are hearing these horror stories about AI and job loss and everything, they need to understand there are people like yourself who are building this in an incredibly thoughtful way and this is going to be a net benefit for humanity that just is unimaginable. Yeah, we have a shot with this technology. So not our children nor anyone they know dies of cancer.

</details>

**Jason**: 好的，可以这么说。当然，经济中不可避免地会出现一些结构性失调。这是肯定的。就像汽车刚问世时，同样出现了结构性失调，如果你是一个给马钉马蹄铁的人，或者是一个造马车的人，那绝对是一笔糟糕的买卖，对吧？

<details>
<summary>Original English</summary>

**Jason**: All right. I mean say it like that. There will be some dislocation in the economy. Sure. There will be there was dislocation when cars came and and and it was a bad deal to to to be a guy who shed horses, right? Or built carriages.

</details>

**Andrew**: 但与此相对，你也必须理清其中的利与弊，权衡优劣。

<details>
<summary>Original English</summary>

**Andrew**: But you got to also against that, you know, make your tea of the cons and the pros.

</details>

**Jason**: 是的。

<details>
<summary>Original English</summary>

**Jason**: Yeah.

</details>

**Andrew**: 对吧。我们有机会让我们的孩子，让他们以及他们所爱的人都不会死于癌症。这是我们可以通过这项技术去致力于解决的问题之一，并且我们将在这方面获得巨大的掌控力。我认为，当你开始列出这些好处时，这就会变成一场更加经过深思熟虑的讨论。

<details>
<summary>Original English</summary>

**Andrew**: Right. There's a shot that our children, none of them nor their people they love will die cancer. And that that's one thing that we can work on wi with this technology and we will have great purchase on and and I think you begin listing those and then it's a more thoughtful discussion.

</details>

**Jason**: 是的。无限的能源，无限的卡路里，无限的知识，无限的教育资源，无限的住房保障。

<details>
<summary>Original English</summary>

**Jason**: Yeah. Unlimited energy, unlimited calories, unlimited knowledge, unlimited education, unlimited housing

</details>

**Andrew**: 以及我们实现这一切的方式。想象一下，就像我们其实知道应该如何教导孩子，但我们一直没有采用正确的方法。亚里士多德是亚历山大大帝的导师。苏格拉底也是他所在时代的导师。我们知道，如果你给一个孩子配备一位私人导师，并且这位导师能根据孩子的特点量身定制教学方式，他们就能学得更好。

<details>
<summary>Original English</summary>

**Andrew**: and how we do it. We imagine imagine sort of we know how to teach children and we don't do it right. Aristotle was a tutor to Alexander the Great. Socrates was his tutor. We know that if you give a child a tutor and the tutor modifies the teaching for the child, they learn better.

</details>

**Jason**: 然而我们现在的课堂教学根本不是这样运作的。完全是“工厂化养殖”式的教育。

<details>
<summary>Original English</summary>

**Jason**: That's not how we do teaching classes. Factory farming.

</details>

**Andrew**: 没错。我们只是试图迎合某种中等水平进行教学。想象一下，如果我们能构建出能够适应孩子们自身学习方式的 AI 智能体来教导他们。

<details>
<summary>Original English</summary>

**Andrew**: That's right. We we teach to some sort of mid-level. Imagine if we beat built agents that that taught children for their way of learning.

</details>

**Jason**: 是的。

<details>
<summary>Original English</summary>

**Jason**: Right.

</details>

**Andrew**: 没错。你看，一种做法是，我们在一千年的时间里一直沿用同一种方式做事。并且在整个这段时间里，我们明明知道有更好的方法，但我们却选择不去改变。而现在，有了这种技术，我们就能做到。把这个放入“利”的那一栏吧。所以，只要我们能够足够深思熟虑且公正地记录下好的一面和坏的一面，我认为最终的结果会是好的。

<details>
<summary>Original English</summary>

**Andrew**: Right. And here's a way we we've been doing it the same way for a thousand years. And during that entire time, we knew how to do it better and we chose not to. And and here's a way we can do it. Put that on the pro side. And so as long as we're sort of thoughtfully and fairly writing the good and the bad, I I think it'll come out.

</details>

**Jason**: 你必须走出去，Andrew，继续向世界传达你眼中的世界版本，因为有些人看到了未来的冰山一角，他们变得有些紧张和不安。

<details>
<summary>Original English</summary>

**Jason**: You got to get out there, Andrew, and keep communicating your version of the world because some people see around the corner and they get a little nervous and

</details>

**Andrew**: 好吧，这很合理。但我认为，正如你所描述的那样，这份账单上的“利”已经严重偏向于“丰饶”与“富足”的那一面。

<details>
<summary>Original English</summary>

**Andrew**: Okay, fair enough. But I think the ledger, as you describe it, is heavily weighted towards abundance.

</details>

**Jason**: 我认为它肯定会创造极大的丰饶。

<details>
<summary>Original English</summary>

**Jason**: I think it'll create abundance for sure.

</details>

**Andrew**: 是的，绝对的大丰收与资源富足。

<details>
<summary>Original English</summary>

**Andrew**: Massive abundance.

</details>

**Jason**: Andrew，这是我的荣幸。每次见到你都是一件乐事。我们六个月后的“复查”再见。那一定会非常棒。

<details>
<summary>Original English</summary>

**Jason**: Andrew, pleasure. Always a pleasure to see you. I'll see you in six months for our checkup. That'll be great.

</details>

### 赞助商插播：纳斯达克

**Narrator**: 工业、资本和智能正逐渐融合为一个单一且相互关联的系统，而其背后的基础设施也需要以同样的速度进行演进。纳斯达克（NASDAQ）正是为这一历史性时刻而生，为全球超过 135 个市场和监管机构提供强大动力，并将资本与塑造未来的创新型公司紧密连接在一起。随着创新经济的不断加速，互联互通性正成为最为关键的资产。纳斯达克是领先的技术平台，正是它让这一切变得可能且具备可扩展性。如需了解更多信息，请访问 nasdaq.com。

<details>
<summary>Original English</summary>

**Narrator**: Industries, capital, and intelligence are converging into a single interconnected system, and the infrastructure behind it needs to evolve just as quickly. NASDAQ was built for this moment, powering more than 135 marketplaces and regulators globally and connecting capital to companies shaping the future. As the innovation economy accelerates, connectivity becomes the critical asset. NASDAQ is the leading technology platform that makes it possible and scalable. Learn more at nasdaq.com.

</details>

### 黑森林实验室 (Black Forest Labs) 与生成式 AI 的未来

**Host**: Robin Rombach，你是 Black Forest Labs (黑森林实验室) 的联合创始人兼首席执行官。你目前的工作基地位于德国黑森林，这是一个城市——

<details>
<summary>Original English</summary>

**Host**: Robin Rombach is uh the co-founder and CEO of Black Forest Labs. You are uh based in Germany in Black Forest which is a city

</details>

**Robin Rombach**: 在德国。其实那是一片山脉。

<details>
<summary>Original English</summary>

**Robin Rombach**: in Germany. A mountain range actually.

</details>

**Host**: 是山脉。

<details>
<summary>Original English</summary>

**Host**: A mountain range.

</details>

**Robin Rombach**: 是的。

<details>
<summary>Original English</summary>

**Robin Rombach**: Yes.

</details>

**Host**: 那里是你长大的地方。

<details>
<summary>Original English</summary>

**Host**: Where you grew up.

</details>

**Robin Rombach**: 是我长大的地方。没错。

<details>
<summary>Original English</summary>

**Robin Rombach**: Where I grew up. Yes.

</details>

**Host**: 你目前正在研发开源的图像和视频模型。你曾在 Stable Diffusion 工作过一段时间。

<details>
<summary>Original English</summary>

**Host**: And uh you are working on open-source image and video models. You worked at stable diffusion for a little bit.

</details>

**Robin Rombach**: 没错。

<details>
<summary>Original English</summary>

**Robin Rombach**: That's correct.

</details>

**Host**: 你在那里积累了丰富的经验。如今，你因为开源模型 Flux 广为人知，或许也因为一些闭源模型而受人瞩目。请和我们谈谈 Black Forest Labs 的业务吧。这家公司的主要业务是什么？你们的目标又是什么？

<details>
<summary>Original English</summary>

**Host**: Cut your teeth on that. and uh you're known for the open source model flux and maybe also for some closed source models. Tell us about the business of Black Forest Labs. What is the business and what is the goal?

</details>

**Robin Rombach**: 绝对没问题。首先稍微快速补充一点，我们的总部位于黑森林地区。这是一个叫做弗赖堡（Freiburg）的小镇，另外我们在旧金山也有据点。我们在那里有——

<details>
<summary>Original English</summary>

**Robin Rombach**: 100%. Uh one uh quick addition, we are based in uh the Black Forest. It's a town called Frybook and in San Francisco. We have like

</details>

**Host**: 当然，在旧金山也有。是的。

<details>
<summary>Original English</summary>

**Host**: in San Francisco of course. Yeah.

</details>

**Robin Rombach**: 呃，我们...

<details>
<summary>Original English</summary>

**Robin Rombach**: Um we

</details>

**Host**: 所以你平时是在两地奔波分配时间吗？

<details>
<summary>Original English</summary>

**Host**: you're splitting your time or

</details>

**Robin Rombach**: 呃，在某种程度上我确实是两边分配时间的。我们...是的，我们在两年前创办了这家公司。正如你所说，我和我的合伙人过去曾在 Stable Diffusion 工作过。在那之前，我们发明了一种名为“潜在扩散（latent diffusion）”的算法，这基本上是如今所有被部署用于图像生成、视频生成，甚至包括现在的实体人工智能（physical AI）等各类生成式模型背后的基础核心算法。

<details>
<summary>Original English</summary>

**Robin Rombach**: uh I'm splitting my time to a certain degree. Um we um yeah started a company 2 years ago. Um me and my co-owners as you said like we've worked on stable diffusion in the past. Before that we invented like an algorithm called latent diffusion which is basically like the fundamental algorithm behind all of like generative models that are being deployed for image generation, video generation, even like physical AI now.

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Robin Rombach**: 它基本上利用了这样一个原理：你可以将像图像、视频、音频这样的自然数据，压缩成一种更为高效的表征形式，然后在这个基础上训练一个 Transformer 模型。我的意思是，这也是为什么你所熟知的 JPEG、MP3 诸如此类的技术能够奏效的原因。就在几年前，当我们还只是慕尼黑的博士生时，我们实际上就将这一原理转化成了某种神经算法。随后，我们在那项研究的基础上构建了 Stable Diffusion，接着在那之上...是的，就是我们今天正在研发的各种生成式模型。当然，技术本身也取得了长足的进步。但我认为，我们目前正在攻克的，是那些真正旨在理解我们周围整个世界的多模态视觉模型，它们在图像和音频数据上进行了同步预训练。我们现在正在进入一种全新的范式，那就是将其与所谓的“动作预测（action prediction）”结合起来，这样你实际上就能使用同一个模型来生成图像、生成视频、生成音频，并且能够预测动作。这意味着，你最终能够将它部署到真实世界的机器人上。

<details>
<summary>Original English</summary>

**Robin Rombach**: Um it basically makes use of this principle that uh you can compress natural data such as images, such as video, such as audio into a much more like efficient representation and then train a transformer model on that. And um I mean this is the stuff why like you know like JPEG uh MP3 and all of that works. And we basically translated that into like a neural uh algorithm uh a few years ago when we were still like PhD students in uh in Munich actually. And uh then build on like on top of that we build stable diffusion and then um on top of that uh yeah uh the generative models that we are developing today and of course like the technology has advanced um but we are now tackling I would say models that are really made for understanding like the whole world around us multimodal visual models uh pre-trained on images audio data at the same time and we are now like entering a new paradigm which is combining that with uh something that's called action prediction such that you can actually use the same model to make images to make videos to make audio and to predict actions which means you can ultimately deploy it on a robot in the real world.

</details>

**Host**: 哇。所以不仅是从图像到视频、音频，接着最终还会延伸到真实世界本身。

<details>
<summary>Original English</summary>

**Host**: Wow. So from the image to the video, the audio and then eventually the real world

</details>

<!-- chunk 6/8 -->

### 走向多模态与现实物理的理解

**Speaker B**: ……以及机器人技术和现实世界模型，因为如果你能生成图像，并且你能训练出这个模型，那意味着在默认情况下你理解了现实世界。为了制作出关于现实世界的视频，你必须理解现实世界。是的。

<details>
<summary>Original English</summary>

**Speaker B**: ...with robotics and a real world model because if you can make the image you and you can train the model that means by default you understand the world. In order to make a video of the world you have to understand the world. Yeah.

</details>

**Speaker A**: 还有物体在……

<details>
<summary>Original English</summary>

**Speaker A**: And the objects in...

</details>

**Speaker B**: 我觉得这是一个非常好的思考角度。是的，这就像是一种与世界互动的直观方式，对吧？我想说，最终存在着这些互补的智能形式。有直观的智能，然后还有一个深层的推理层。要实现一种完整的形式，你最终需要这两者，并且需要它们相互作用。我认为我们之前更多是从直观的一面来切入。图像是涉足这整个领域的一种非常自然的方式，因为它不像视频那样具有计算密集性，对吧？但现在，我认为我们正在将它们结合起来，它正融合成为一个多模态模型。而且是的，我们确切地看到，比如在视频上进行预训练能赋予模型对真实世界交互物理的内隐理解，然后你就可以从同一个模型中获得诸如动作预测、机器人技术等能力。

<details>
<summary>Original English</summary>

**Speaker B**: I think that's like a really good way to think about it. Yeah, it's like an intuitive way to interact with the world, right? Like I would say there's these complimentary forms of intelligence ultimately. There's intuitive intelligence and then there's a deep reasoning layer. Now ultimately you need for a complete form you need both and you need them to interact and I think we've been approaching it more from the intuitive side. Images is a very natural way to approach this whole field because it's not as computationally intensive as let's say video, right, but now yeah I think we're combining it, it's converging into a multimodal model and yeah we see exactly like pre-training on videos gives implicit understanding of the physics of interactions with the real world and then you can get stuff like action prediction, like robotics, out of the same model.

</details>

### 从“老虎机”到操控层

**Speaker A**: 随着这些模型和训练的推进，在创建视频和图像时某种程度上存在一个局限，生成式 AI 受到的批评是它有点像老虎机。我给出一个提示词，它就给我返回一些东西。但它是如何从训练数据中得出那个结果的？但你看，也许我想要一种不同的风格？也许我想要一种不同的颜色。也许我想要一种不同的美感。

<details>
<summary>Original English</summary>

**Speaker A**: And with these models and the training there's kind of been a limitation in creating videos and creating images where the criticism of generative AI is it's a bit of a slot machine. I give a prompt, it gives me something back. But how did it come up with that? The training data, but you know, maybe I want a different style? Maybe I want a different color. Maybe I want a different aesthetic.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Yep.

</details>

**Speaker A**: 这个问题怎么解决？在底层生成图像时，你真的理解发生了什么吗？

<details>
<summary>Original English</summary>

**Speaker A**: How does that problem get solved? And do you actually understand what's happening when the image is being made under the hood?

</details>

**Speaker B**: 是的，我想最终这关乎向那些在这个模型之上进行构建的用户或开发者暴露尽可能多的操控层，对吧？而且我认为我们过去已经看到了这一点。在过去的图像模型中，它们基本上是从简单的文本到图像的系统起步的，对吧？然后它们扩展为文本加图像到图像的系统，这意味着你突然可以拿一张图像（比如真实图像或生成的图像），然后基于文本提示在此基础上进行迭代，比如编辑它、修改它，对吧？接着这又扩展到接收多张图像和一个文本提示，并以一种语义化的方式将它们结合起来生成新内容。现在同样的原理也适用于视频。而且我认为，当所有这些模态实际上合并为同一个模型的输入和输出时，这就变得更加有趣了。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I think ultimately it's about exposing as many manipulation layers as possible to a user or developer that builds on top of this model, right? And I think we've seen that in the past. In the past image models basically started from simple text-to-image systems, right? Then they've expanded into text-plus-image-to-image systems, which means you could suddenly take an image, like a real image or generated image, and iterate on that based on a text prompt. Like edit it, modify it, right? And then this expanded into taking multiple images and a text prompt and combining them in a semantic way and producing new content. And the same principle now applies to video. And I think now it becomes actually even more interesting when all of these modalities are actually combined inputs and outputs of the same model.

</details>

### 与马丁·斯科塞斯的合作

**Speaker A**: 那我们来谈谈视频。有公告说你正在与有史以来最伟大的导演，或者是还在世的伟大导演马丁·斯科塞斯（Martin Scorsese）合作。我们稍后再聊这个。

<details>
<summary>Original English</summary>

**Speaker A**: So let's talk about video. There's an announcement that you're working with the greatest director of all time or living director Martin Scorsese. We'll talk about that in a second.

</details>

**Speaker B**: 太棒了。

<details>
<summary>Original English</summary>

**Speaker B**: Fantastic.

</details>

**Speaker A**: 但在电影制作方面，有这样一种承诺：能够制作出像《好家伙》（Goodfellas）这样的真正电影，或者是《好家伙》里的某个场景，而相比之下，今天的情况是，你可以制作出有趣的 5 到 10 秒片段，然后人们也许要费力地做出 10 个这样的片段，接着用一些后期编辑软件把它们拼接在一起。但你立刻就会明白这不是那回事。这不是电影。它是 AI 垃圾。它很笨拙。它通不过恐怖谷测试。

<details>
<summary>Original English</summary>

**Speaker A**: But in a movie, this promise of being able to make an actual movie like Goodfellas or a scene from Goodfellas, versus where it is today where you can make interesting five or 10 second clips and then maybe people struggle making 10 of them and then they use some post-editing software to put them together, but you immediately understand this is not that. It's not a movie. It's AI slop. It's kludgy. It doesn't pass the uncanny valley.

</details>

**Speaker B**: 嗯，我认为有一点很重要，而且这至少是我们的观点，那就是这些 AI 模型，它们是一种媒介，对吧？我们不想设定任何关于它们应该如何使用的规则。我们不想告诉任何人，尤其是像马丁·斯科塞斯这样的人，他该怎么使用这些模型？他可是有史以来最伟大的电影制作人之一。能和他多次坐在同一个房间里，实际上看着他探索我们的模型，而我作为背后的核心研究员之一，那简直是一种疯狂的感觉。对吧。而与此同时我也是他的超级粉丝。

<details>
<summary>Original English</summary>

**Speaker B**: Well, I think it's important and that's at least the view that we have, is that these AI models, they are a medium, right? We don't want to set any way of how they are supposed to be used. We don't want to tell anyone, especially not someone like Martin Scorsese, how is he supposed to use these models? Like he is one of the greatest filmmakers ever. It was insane sitting in the same room with him multiple times and actually him seeing, exploring our models as one of the core researchers behind it, was just an insane feeling. Right. And at the same time I'm also a big fan.

</details>

**Speaker A**: 所以你和马蒂·斯科塞斯坐在一个房间里，向他展示了你们的工具。

<details>
<summary>Original English</summary>

**Speaker A**: So you sat in a room with Marty Scorsese and showed him your tools.

</details>

**Speaker B**: 没错。是的。

<details>
<summary>Original English</summary>

**Speaker B**: Exactly. Yeah.

</details>

**Speaker A**: 他的反应是什么？他关注的重点是什么？他觉得最受启发或最有趣的事情是什么？

<details>
<summary>Original English</summary>

**Speaker A**: And what was his reaction? What did he key off of? What was the thing that he found most inspiring or interesting?

</details>

**Speaker B**: 好的。我觉得真的是这样一种理念：他的脑海中显然有一幅画面，关于某个场景或风景，也许一部新电影将在那里拍摄，他试图探索这个想法。我们基本上看了一个可能位于东欧某处的村庄风景，他描述了它。我们看到了一些输出，我们在这些输出上进行了迭代。而且最终，我认为，这也是他最后所说的，就是把脑海里的这种心理图像提取出来，通过制作这些图像或者系列图像，以一种视觉化的方式交流出来。这确实让传达和表达你脑中真实的构想变得更加容易。我认为这是使用这项技术非常有趣和强大的方式之一，而且我认为最终……

<details>
<summary>Original English</summary>

**Speaker B**: Okay. I think it was really this idea of, he has clearly a vision in his head of a scene or a scenery where maybe a new movie will be shot and he's trying to explore that and we basically looked at the scenery of a village in Eastern Europe somewhere and he was describing it. We saw some outputs, we iterated on the outputs. And ultimately I think, and that's what he said in the end, is getting the mental picture of something out of your head and communicating it in a visual way by making these images or the series of images, is something that just makes it easier to communicate and convey an idea of what is actually in your head. And I think that's one of the very interesting and powerful ways to use this technology and I think ultimately...

</details>

**Speaker A**: ……就是为了获得灵感，把他脑海里的愿景转化为图像。

<details>
<summary>Original English</summary>

**Speaker A**: ...is to get the inspiration, to get the vision out of his head onto an image.

</details>

**Speaker B**: 是的。我的意思是，语言最终有点像是一种有损的交流媒介，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I mean language ultimately is a little bit of a lossy communication medium, right?

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 它也会被用不同的方式来解读，但是视觉信息是如此丰富。非常丰富。像一张图片或者一段视频，里面蕴含着那么多的信号，这简直是另一种交流方式。我认为那是这项技术最终能够赋能的美妙之处之一。而且对于你提出的关于是否能用一个视频生成模型来制作完整电影的问题，我不确定这是否就是最终目标。也许把这个接入到某种智能体工作流（agentic workflow）中去制作一段很长的视频会很有意思。而且我觉得这很酷，值得探索。但我认为最终真正有趣的应用场景是在“人在环路”（human-in-the-loop）时出现的，人类在其中迭代并把它当作一种媒介来使用。我认为至少从我个人的视角来看，这才是让它变得有趣的地方，而且最有趣的输出往往就是在这种时候诞生或者被实际创造出来的。

<details>
<summary>Original English</summary>

**Speaker B**: It's also interpreted in different ways, but then visual information is so rich. So rich. Like an image or video, there's so much signal in it and it's just another way of communicating. And I think that's one of the beautiful things that this technology ultimately enables. And I think to your question of making full movies with a video generation model for example, I'm not sure if that is the ultimate goal. Maybe it's interesting to plug this into some kind of agentic workflow and make a very long video. And I think that's really cool to explore, but I think ultimately the real interesting use cases they come when you have a human in the loop who iterates and uses it as a medium. And I think this is at least a perspective that I take that makes it interesting and that this is most often when the most interesting outputs arrive or are actually being made.

</details>

### AI 并行化头脑风暴与商业应用

**Speaker A**: 这种头脑风暴层面的生产力显然是一个巨大的胜利……你基本上可以并行化（parallelize）你的头脑风暴了。

<details>
<summary>Original English</summary>

**Speaker A**: The brainstorming production level is so obviously a huge win for... you can parallelize your brainstorming basically.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 对，我很喜欢这个说法。并行化你的头脑风暴，他们在这方面也有个类比。他们画分镜头脚本（storyboards），一些伟大的导演，比如执导过《异形》（Alien）和《角斗士》（Gladiator）的雷德利·斯科特（Ridley Scott），就以亲自画分镜头脚本而闻名。我还相信斯皮尔伯格（Spielberg）也喜欢为《夺宝奇兵》（Raiders of the Lost Ark）等作品画草图。乔治·卢卡斯（George Lucas）则以与许多出色的艺术家合作而闻名。他们甚至为《星球大战》（Star Wars）系列制作微缩模型和分镜头脚本。他有全职的人员来帮他做这些。所以这是很明显的切入点。但如果我们看看初创公司，初创公司总是想弄清楚如何以低成本做事。以前人们为了给自己的初创公司做一个发布视频，你知道，要花 10 万美元、25 万美元。所以他们拿 1000 万美元的风投资金，花 25 万美元做个发布视频。我在我现在投资的很多初创公司中看到，他们现在只会花一两周时间和一位导演合作来制作发布视频。你大概也看到了这个趋势。是的。而且我确信人们在用 Flux 和你们的一些模型来做这件事。你看到这个现象了吗？

<details>
<summary>Original English</summary>

**Speaker A**: And yeah, I like that. Parallelize your brainstorming, and they have an analogy for this. They do storyboards, and some of the great directors, Ridley Scott of Alien and Gladiator was known for making his own. I also believe Spielberg also liked to sketch Raiders of the Lost Ark and some of these. George Lucas was known for collaborating with many amazing artists. Even making miniatures and making storyboards for the Star Wars franchise. He had those people on full-time helping him with that. So that's the obvious place to start. But if we look at startups, startups always want to try to figure out how to do something cheaply. And people used to make a launch video for their startup for, you know, $100,000, $250,000. So they take their $10 million venture raise and spend $250,000 on a launch video. I've seen with a lot of the startups I'm investing in now, they'll just spend a week or two working with a director to make a launch video. You've probably seen this trend. Yeah. And I'm sure people use Flux and some of your models for this. Have you seen this?

</details>

**Speaker B**: 是的，当然。是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, of course. Yeah.

</details>

**Speaker A**: 对。你怎么看这事？因为感觉这像是讲故事（storytelling）的早期阶段。你正试图以一种有趣、吸引人、有冲击力的 30 秒或 90 秒的方式来传达一种产品或服务。是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. What's your take on that? Because that feels like the early stage of storytelling. You're trying to communicate a product or service in a fun, engaging, punchy 30-second, 90-second way. Yeah.

</details>

**Speaker B**: 我的意思是，再次说明，我认为我们支持基于这些工具的这种探索，对吧？并且我认为最终很高兴能看到各种各样……我不知道，比如产品发布视频之类的，被构建在同一个基础模型或者同一种技术之上。而且我认为正是这些让它变得……

<details>
<summary>Original English</summary>

**Speaker B**: I mean, again, I think we support this exploration based on these tools, right? And I think ultimately it's great to see all different kind of... I don't know, launch videos, products being built on top of the same base model or the same technology. And I think that's what's making it...

</details>

<!-- chunk 7/8 -->

### 电影制作中的生成式AI应用

**Speaker A**: 这非常有趣，而且也非常强大。

<details>
<summary>Original English</summary>

**Speaker A**: so interesting and also so powerful.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah.

</details>

**Speaker A**: 人们还在用这项技术做些什么呢？我听说有一部关于比特币的电影即将上映，而这部电影中并没有使用传统的绿幕。嗯，我和盖尔·加朵（Gal Gadot）聊过，你知道的，就是那位扮演神奇女侠的女演员。

<details>
<summary>Original English</summary>

**Speaker A**: And what else are people using the technology for? I understand there's a Bitcoin movie coming out. instead of using a green screen in this Bitcoin movie. Um, I was talking to Galado, you know, the woman who played the actress who played Wonder Woman.

</details>

**Speaker B**: 哦，盖尔·加朵，当然。

<details>
<summary>Original English</summary>

**Speaker B**: >> Oh, Galado, of course.

</details>

**Speaker A**: 我是在一个活动上和她交谈的，她告诉我——嗯，那是突破奖（Breakthrough Prize），尤里·米尔纳（Yuri Milner）举办的活动——她告诉我，她刚拍完一部比特币电影，他们是在一个没有绿幕的摄影棚里拍摄的。所有的演员只是在一个像摄影棚一样的地方工作，然后他们身后的所有布景都是由生成式AI完成的。那可是一部真正的电影，是一部预算高达3000万美元的电影。她说，如果他们必须去搭建实景，成本可能会高达1.5亿美元，那这部电影可能永远都不会被批准拍摄。你现在是否开始看到人们在实际的制作中使用这项技术了？不仅仅是在后端的构思阶段，而是在实际制作中已经开始使用你们的工具了吗？

<details>
<summary>Original English</summary>

**Speaker A**: She I was talking to her at an event and she was telling me um it was the Breakthrough Prize uh Yuri Milner's event and she was telling me she just did a Bitcoin movie and they did it on a sound stage without green screens
>> but all the actors just worked in like a sound stage
>> and then all of the scenery behind them was being done by Generative AI. That's a real movie. That's a $30 million budget movie. She said it would have cost $150 million if they had to build sets and the film would have never been green lit. Are you starting to see people use that in production? Not just in the back end and the ideation phase, but actually in production yet with your tools.

</details>

**Speaker B**: 是的。嗯，是的，我们确实看到了一些在实际制作中的此类用例。我认为像高端的电影制作可能算是要求最高的使用场景之一了。我很高兴看到它正在被探索，但我也真的想说——嗯，我认为很重要的一点是，要看到这项技术正处于一个发展轨迹上，而且它在不断进步，进步的速度非常快。我不知道，如果我回想一下几年前我们刚开始的时候，当我在这个领域攻读博士学位时，你唯一能做的就是生成64x64像素的图像。现在你已经可以生成多输入的视频了，对吧，而且是高分辨率的，但这不会就此止步。它会继续改善，我认为接下来它将会解锁更多这种高端的使用场景。但我认为最主要的是……

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah.
>> Um, yeah, we see some use cases like that in production. I think like high-end film production is kind of like the one of the like most demanding use cases. And I I think I'm glad that it's being explored, but I also
>> really want to um like it's I think it's important to see that this technology is like on a trajectory and it's improving. It's improving rapidly. I don't know if I look back at like where we started like a few years ago when I was doing my PhD in this field like the only thing that you could do was like images of 64x 64 pixels. Now you can do like multi-inut videos, right, at like a high resolution, but it's like it's not going to stop there. It's going to it's continue to improve and I think like then it's going to unlock like even more of these like high-end use cases. But I think the main thing

</details>

**Speaker A**: 在我们讨论那个之前，是的，很难预测。

<details>
<summary>Original English</summary>

**Speaker A**: >> before we get to that, yeah,
>> hard to predict.

</details>

**Speaker B**: 我觉得很难预测，我认为最终……

<details>
<summary>Original English</summary>

**Speaker B**: I think hard to predict and I think ultimately

</details>

**Speaker A**: 几年之后。

<details>
<summary>Original English</summary>

**Speaker A**: >> couple of years

</details>

**Speaker B**: 最终我认为你仍然希望拥有那种能够实现“人在回路（human in the loop）”的工具……

<details>
<summary>Original English</summary>

**Speaker B**: >> ultimately I think you still want to have like the tool that enables like this human in the loop kind of

</details>

**Speaker A**: 当然。是的。

<details>
<summary>Original English</summary>

**Speaker A**: >> of course. Yeah.

</details>

### 从视频生成到机器人控制

**Speaker B**: 这种生产工作流，对吧？但我认为当我从整体上看待多模态生成模型时，真正让我感到兴奋的是，你可以使用同一种AI模型来制作电影，并将其作为一个“大脑”部署在机器人上。啊，我认为这真的是太有趣了。嗯，我不知道，好像有一些想法是尝试在数字世界中进行这种操作，对吧？这可能是，比如说，计算机的使用。这是否真的可行还有待观察，但我认为这项技术是如此强大，如此多才多艺，它只是刚刚开始进入那个领域。所有关于世界模型（world models）、世界动作模型（world action models）等所有的讨论，从根本上来说都是同一回事。我认为正是这一点让它变得如此有趣，也是我觉得最令人兴奋的地方。

<details>
<summary>Original English</summary>

**Speaker B**: >> Um production workflow, right? But I think when I look at multimodal generative models um as a whole, I think what really excites me is you can use the same kind of um AI model to make a movie and deploy that as a brain on a robot. Ah, and I think this is like this is so interesting. Um and I don't know like there's like some thoughts around trying that in the digital world, right? which would be for example computer use remains to be seen if that is actually something that works or not but I think like the technology is so powerful and so versatile and it's just just moving into that and all the all the talk around like world models world action models all of that it's basically all the same and I think that's what's making it so interesting and what I find like most exciting

</details>

**Speaker A**: 那么你是否相信，这项技术将被用来分析，或者说主要用来分析真实世界？比如这有一段某人做三明治的视频，现在我们让机器人去学习它，然后做出三明治。或者你认为会生成大量的合成数据，然后机器人只需学习这些合成数据？还是说，它们会基于这些海量的训练数据，以某种方式天生就知道该怎么做？

<details>
<summary>Original English</summary>

**Speaker A**: >> so do you believe that the technology will be used to analyze or primarily to analyze is real world like here's a video of somebody you know making a sandwich. Now we have the robot study it and make the sandwich or do you think there'll be a lot of synthetic data made that then the robots will just study the synthetic or they're going to just in some way innately know based on all this massive amounts of training data.

</details>

**Speaker B**: 嗯，我认为这是预测的结合，对吧？这是一种预测，你可以把它看作是模拟，或者是生成。它是在预测动作，也就是说你必须理解输入，即视觉输入，才能真正预测出下一个合理的动作。所以这关乎感知。只有当你理解并感知了内容，你才能——我不知道，比如——把它转化为一段新的内容，或者预测一个动作，或者描述你在那个场景中实际看到了什么。我认为所有这些结合在一起……是的，我认为这就是推动它发展的动力。这不仅仅是其中单一的一项，而是这些想法的结合。

<details>
<summary>Original English</summary>

**Speaker B**: Um I think it's a combination of prediction right and p prediction and is a way of you can think about it as simulation as generation it's um predicting actions which is you have to understand the input the visual inputs in order to actually predict a reasonable next action um and it's about perception it's like you can only do that if you understand if you perceive the content you then you can only I don't know like transform it into a new piece of content or predict an action or describe what you actually see in that um scene. And the and the combination of all of that is I think um yeah is I think what's what's driving it. There's not a single one of them. It's a combination of these thoughts.

</details>

### 获取训练数据与上下文提示

**Speaker A**: 那么获取这些训练数据的最佳方式是什么？你是否需要让人戴上眼镜，获得第一人称视角，让他们戴上手套，这样你就能拥有，你知道的，那种高保真度的理解：“嘿，这个杯子在移动。我正在倒这个杯子。我正在往里面放冰块”，你知道的，“而且这就是它的工作原理，还有水花飞溅和冷凝水，所以我可以拿起来而且不会因为外面是湿的而把它掉在地上。”还是说仅仅是，“嘿，拿YouTube视频的语料库，机器人就能确切地知道该怎么做，因为它们能找到一千个关于人们倒饮料的视频。”？

<details>
<summary>Original English</summary>

**Speaker A**: >> And what's the best way to get that training data? Do you need to have people put on glasses, get a firsterson perspective, have them put on gloves so you have that,
>> you know, fidelity of understanding, hey, this glass is moving. I'm pouring this glass. I'm putting ice into it, you know, and and here's how that's works and the splashing and the condensation water so I can pick it up and not drop it because it's wet on the outside. Or is it going to be just, hey, take the corpus of YouTube videos and the robots know exactly what to do because they'll find a thousand videos of people pouring drinks.

</details>

**Speaker B**: 我的意思是，最终，我认为你会希望达到这样一个境界：你可以像使用语言模型一样，在上下文中对机器人进行提示，对吧？基本上就是直接告诉它：“嘿，去，我不知道，拿起这杯……我不知道，橙汁或者是别的什么。”

<details>
<summary>Original English</summary>

**Speaker B**: >> I mean, ultimately, I think you would want to go to a place where you could like prompt a robot in context, right? as you can do with like a language model basically just tell it hey go and I don't know pick up this glass with the I don't know orange juice or whatever it is

</details>

**Speaker A**: 是的，没错。

<details>
<summary>Original English</summary>

**Speaker A**: yeah exactly

</details>

**Speaker B**: 我们还没到那一步。嗯，但我认为这这就是目标之一。而且我认为这些模型目前的部署方式是，有很多像不同的硬件、在工厂运行的不同的机器人，嗯，它们都有某种不同的动作表示，你需要针对性地调整模型，对吧？所以在实践中，嗯，你的做法是，你在模型中已经具备了所有这些视觉理解能力，嗯，然后你只需要非常少的一点点，比如几个小时的微调数据，来针对那个特定任务调整模型。我认为我们的目标应该是尽可能摆脱这种方式，朝着尽可能多的“在上下文中（in context）”的方向发展，但这还是有点像是一个研究难题。呃，我我是这样认为的。

<details>
<summary>Original English</summary>

**Speaker B**: >> we're not there yet um but I think this this is like one of the goals and I think like how these models are deployed currently is there's like a lot of like different hardware different robots that are running in factories um that all have like some different kind of action representation that you need to kind of tune the models towards right So in practice um what you do is you have like all this like visual understanding in the models um and then you need only a very little bit of like a few hours of um fine-tuning data to adjust the model on that specific task and I think the goal would be to kind of move away from that uh towards like as much in context as possible but it is a little bit of a research problem. Uh, I I think that

</details>

### 开源模型与知识产权（IP）保护

**Speaker A**: 开源现在正迎来一个高光时刻。我们最近在播客上讨论了很多关于这方面的内容，人们也在谈论主权。有些公司拥有令人难以置信的知识产权（IP）库。我之前提到过《星球大战》。迪士尼拥有一个非常庞大的IP库。你的建议会是什么，你会给像迪士尼这样的公司什么建议？他们应该拿你们的开源软件去训练自己的模型，还是和你们合作来训练他们自己的模型以便控制它，然后宣称“嘿，这是我们的IP”？他们已经特意选择和ChatGPT合作，并声明“嘿，你可以或不可以使用某些角色”。事实上，OpenAI曾为了Sora和他们有过合作关系，虽然现在已经停止了，但他们在输出上获得了某些角色的官方授权。那么你如何看待那些主要的IP持有者？你对他们有什么建议？你是否在和他们进行讨论？我们知道关于马丁·斯科塞斯（Martin Scorsese）或这类大导演的交易，但你如何看待内容库呢？

<details>
<summary>Original English</summary>

**Speaker A**: >> open source is kind of having a moment right now. We've been discussing it on the podcast a whole bunch recently and people are also talking about sovereignty. You have companies that own incredible IP libraries. I mentioned Star Wars before. Disney owns an incredible library. What should your advice, what would your advice be to a company like Disney? Should they take your open source software, train their own models or work with you to train their own models to control it and then hey this is our IP? They've already made a point of working with chat GBT and saying hey you you can and cannot use certain characters. In fact, OpenAI had a relationship with them that's for Sora that's no longer happening but they officially licensed on the output some characters. So how do you think about those major IP holders? What's your advice to them? Are you in discussions with them? We know about the Martin Scorsesei or tour deal, but how do you think about content libraries?

</details>

**Speaker B**: 我觉得这是……看，我认为这项技术最有趣的应用场景，如果你考虑内容创作的话，就是在生成一些以前从未存在过的东西，创造一些前所未见的事物，对吧？比如，那是这项技术一个非常根本、非常有趣的方面。然后我认为，是的，当涉及到IP时，例如在我们的面向公众的工具上，我们实施的策略是你不能用这些模型生成特定的IP，对吧？我认为那是一种明智的做法。然后，是的，我们确实和一些特定的IP持有者合作，与他们共同开发模型。嗯，其中一些是基于我们的开源模型，还有一些是基于我们更强大的专有模型，但我认为那是非常具有吸引力的。

<details>
<summary>Original English</summary>

**Speaker B**: >> I think it is um look, I think like the most interesting use cases of this like if you think about like content creation um is in generating something making something that hasn't been there before, right? Like that that's a fundamental like interesting aspect of this technology. And then I think like yeah when it comes to IP what we implement for example on like our public facing tools is you cannot generate certain IP with these models right and I think that's something that is a a sensible approach and then yes we do work with certain IP uh holders to develop models together with them um some of them based on our open source models some of them based on like our more powerful proprietary models but I think that is like a very like attractive

</details>

**Speaker A**: 其中的价值所在。你认为在未来的几年里，这对消费者来说会是什么样子？当你打开Disney+时，可能会发生什么？

<details>
<summary>Original English</summary>

**Speaker A**: >> value there what do you think that will look like for consumers in another couple of years? What would potentially happen when you open up Disney Plus?

</details>

**Speaker B**: 我觉得，这是个好问题。我不是……我不在迪士尼工作，对吧？所以，这取决于他们自己来决定。但是，我认为我们想要赋能他们去构建各种他们所设想的东西。而且我认为我们能支持他们。我们能支持该领域的其他公司去，我不知道，以最佳的方式整合这项技术。我认为这其中一个非常有趣的角度是，它正变得越来越快。它变得更具互动性了。我可以想象出一大批非常有趣的交互式内容创建工具，你可以将它们托管在Disney+或其他任何地方。

<details>
<summary>Original English</summary>

**Speaker B**: >> I mean, that's a good question. I'm not I'm I'm not in Disney, right? So, it's up up to them to decide that. But, I think we want to enable them to build all kinds of stuff that they that they that they envision. And I think we can support them. We can support like other companies in that space to
>> I don't know integrate the technology in the best possible way. I think like one of the very interesting angles of it is that it is like it's becoming much faster. It's becoming more interactive. I can imagine like a whole bunch of like very interesting interactive content creation tools that you could host on Disney Plus Plus or elsewhere.

</details>

**Speaker A**: 我认为最……

<details>
<summary>Original English</summary>

**Speaker A**: >> I think the most

</details>

<!-- chunk 8/8 -->

### 生成式 AI 与粉丝共创

**Speaker A**: 我在这方面看到的一个有趣现象是粉丝自制电影，对吧？在生成式 AI 出现之前，就有一个粉丝同人小说（fanfiction）的类别。人们会写他们自己的《星球大战》（Star Wars）故事。后来出现了粉丝自制电影，人们会装扮成绝地武士（Jedi Knights）并录制自己的电影。乔治·卢卡斯（George Lucas）曾说：“只要你们不将其用于商业目的，不拿去卖钱，我就允许你们去拍绝地武士的电影。”他们甚至还发布了操作指南，你知道的，关于如何制作光剑（lightsaber）的教程，或者是，你知道，像如何制作光剑声音的音频文件。现在，人们正在将《星球大战》宇宙中未曾讲述的故事拿出来，并使用 AI 重新创作它们。对于粉丝们来说，这些视频在 YouTube 上正变得相当受欢迎。呃，《不为人知的星战故事》（Star Wars Stories Untold）我想是其中最大的一个。它每条视频都已经获得了数百万的播放量。我认为这才是真正的未来，即让客户群支付许可费或支付一笔费用，呃，也许是租用软件，或者是基于输出的付费模式，让他们可以在角色上发挥创造力，让他们创作自己的故事，而你可以处于一个独特的地位来赋能这一切。

<details>
<summary>Original English</summary>

**Speaker A**: interesting thing I've seen in this regard is uh fan films, right? So there's a category before generative AI fanfiction. People would write their own Star Wars story. Then there came fan films where people would dress up as Jedi Knights and record their own films. And George Lucas said, "As long as you're not doing it commercially, you're not selling it, I give you permission to go make Jedi movies." And they even released how to, you know, how-tos on how to make a lightsaber or, you know, sound files of like how to make the lightsaber sound. Now, people are taking the stories that haven't been told from the Star Wars universe and they're recreating them using AI. And for the fans, they're becoming quite popular on YouTube. Uh Star Wars Stories Untold is, I think, the biggest one. It's getting millions of views per video already. And I think that's really the future is letting the customer base pay a licensing fee or pay a fee, uh maybe rent software or maybe based on the output and let them be creative with the characters, let them make their own stories, and you could be in a unique position to empower that.

</details>

**Speaker B**: 不，100% 同意。我觉得就像，如果你找到一种对，像 IP 所有者有效的模式，呃，但同时也能促成这些超级具有创意的定制化用例，我认为那就太棒了。是的。我的意思是像，像我自己的话，就像当我读一本书或什么的，比如看一部电影时，我会有那么多像这样的想法：它本来可以怎么被不同地演绎，或者本来可以发生这样的事，对吧。这就像，你能够真正让人们把这些想法可视化，这真的太好了。

<details>
<summary>Original English</summary>

**Speaker B**: No, 100%. I think like if you find like a model that works for like the um IP owners uh but then also can enable like these super like creative customization use cases I think that's great. Yeah. I mean like like I mean like for myself like I when I read a book or whatever like watched the movie I had like so many like ideas how it could be done differently or this could have happened right this is like so nice that you can actually enable people to visualize these ideas.

</details>

### 公司扩张与招聘

**Speaker A**: 是的，呃，它将会获得难以置信的持续成功。你们在旧金山（San Francisco）有个办公室。你们在招人吗？是的，

<details>
<summary>Original English</summary>

**Speaker A**: Yeah it's uh going to be incredible continued success with it. You have an office in San Francisco. You're hiring people? Yeah,

</details>

**Speaker B**: 我们在招。是的，我们刚刚，我们筹集了一大笔钱。我们筹集了一大笔钱。呃，我们刚刚突破了 100 人。我们正在德国（Germany）和旧金山招聘。

<details>
<summary>Original English</summary>

**Speaker B**: we do. Yeah, we just we raised a bunch of money. We raised a bunch of money. Uh we just crossed 100 people. We're hiring in Germany and in San Francisco.

</details>

**Speaker A**: 太棒了。你们在寻找什么样的人？什么样的人、什么样的规模才是合适的？

<details>
<summary>Original English</summary>

**Speaker A**: Fantastic. Who are you looking for? What's the right type of person, the right type of scale?

</details>

**Speaker B**: 是的。呃，一方面，我们一直在寻找那些在超大规模模型训练方面有经验的研究人员。呃，在扩散模型（diffusion model）训练、流匹配（flow matching）训练方面的经验。我们在寻找那些希望与客户合作，你知道，开发这些像定制化的，呃，物理 AI 解决方案的工程师，或者例如与像 IP 所有者合作，和他们共同开发这些模型。呃，我们正在寻找那些，就是像在管理大规模计算基础设施方面有经验的工程师，呃，并确保训练运行顺畅，以最大化我们的 MFU 等等所有这些指标，呃，并且我们也在寻找那些对，你知道像，呃，把这项技术推广出去有兴趣的人

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Um on the one hand, we're always looking for researchers who have experience in large scale model training. Um experience in diffusion model training, flow matching training. We're looking for engineers who want to be working with the customers to you know develop these like customized um physical AI solutions or for example with like a IP owner like develop these models jointly with them. Um we are looking for engineers who have experience in just like large scale compute infra managing that um and making sure that the training runs runs smoothly that we maximize our MFU and all that um and we're looking for people who have interest in you know like uh getting the technology out there

</details>

### 部署与未来展望

**Speaker A**: 交到人们手中。关于这个的部署，有很多很棒的想法，而且我觉得具体在开源领域你们会有很多很棒的合作伙伴。你知道，似乎企业真的很想拥有某种额外级别的控制权，但他们也需要前沿模型或你们的专有模型来实现一些那些精细的功能。所以，我认为你们有一个非常光明的未来。好的。祝你们继续取得成功。非常感谢你来参加这个节目。

<details>
<summary>Original English</summary>

**Speaker A**: in the hands of people the the the for deployment of this there's just so many great ideas and so many great partners for you I think you're going to with the open source specifically. You know, it seems like the corporates really want to have some additional level of control, but they also need the frontier models or your proprietary ones for some of those refined features. So, I think you have a very bright future. All right. Continued success. Thank you so much for doing the show.

</details>

**Speaker B**: 我的荣幸。

<details>
<summary>Original English</summary>

**Speaker B**: Pleasure.

</details>

**Speaker A**: 我要全押进去了。我要全押进去了。

<details>
<summary>Original English</summary>

**Speaker A**: I'm going all in. I'm going all in.

</details>