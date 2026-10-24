---
author: 'House of El: AI'
date: '2026-09-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=sOv1odPw_pc
speaker: 'House of El: AI'
tags:
  - compute-futures
  - financial-derivatives
  - circular-financing
  - market-bubble
  - gpu-infrastructure
title: 算力期货与循环融资：华尔街如何将AI泡沫推向衍生品时代
summary: 英伟达亮眼财报背后，华尔街正通过芝商所与洲际交易所推出GPU算力期货。本文深度解析算力衍生品的利弊、英伟达循环融资与高客户集中度风险，并结合互联网泡沫历史，推演AI基建债务与真实需求博弈下的市场出清路径。
insight: ''
draft: true
series: ''
category: investment-assets
area: finance-wealth
project: []
people: []
companies_orgs:
  - Nvidia
  - CME Group
  - Intercontinental Exchange
  - OpenAI
  - Anthropic
products_models:
  - H100
media_books: []
status: evergreen
---
### 算力金融化：华尔街重构AI底层工具

**英伟达**（Nvidia: 全球领先的加速计算与 GPU 芯片制造商）单季度斩获 962 亿美元营收，同比激增 106%，首席执行官黄仁勋在演讲台上直言“算力即收入”（Compute is revenue）。然而，在看似无可匹敌的繁荣表象之下，资本市场正在围绕 AI 算力构建一套隐秘而激进的金融架构。华尔街的金融工程团队正在将**图形处理器**（Graphics Processing Unit / GPU: 用于并行计算和模型训练的核心硬件）的租赁与使用权转化为标准化的衍生品。

**金融衍生品**（Derivative: 价值派生自基础资产价格变动的金融合约）的核心逻辑在于转移风险与价格博弈。在**期货合约**（Futures Contract: 买卖双方约定在未来特定时间以锁定价格交割资产的标准化协议）的框架下，市场参与者可以在不实际持有或交割底层实物的情况下对未来价格进行押注。传统商品市场中，农场主通过预售下一季度的收成来锁定价格以规避现货波动，这种套期保值机制为实体产业提供了平稳运营的确定性。但当类似机制被直接嫁接到算力这一新兴资产类别时，它既可能是过去十年中最精密的风险平抑工具，也可能演变成继**信用违约互换**（Credit Default Swap / CDS: 为债务违约提供保险的衍生工具）之后最具投机性的泡沫催化剂。

<details>
<summary>Original English Source</summary>

Nvidia just posted $96.2 billion in revenue in a single quarter, up 106% from a year ago. Jensen Huang stood on stage and said, "Compute is revenue." Congratulations. Generally, that is an extraordinary amount of money. Can I have some? The situation around that money, however, is complicated in ways that most coverage either ignores or oversimplifies.

I've already covered Nvidia's circular financing structure in a previous video, so I won't relitigate all of that today. What I want to walk you through instead is something quieter. Wall Street has been building entirely new financial instruments around AI compute. I promise the next video will have plenty of quips about Jensen Huang's jacket collection, but today we need to talk about what's being built behind the scenes. And I'm going to need you to stay with me on this one because what I'm about to show you is either the most sensible piece of financial engineering in a decade or the most elaborate attempt to keep a bubble inflated since someone invented the credit default swap. Possibly both.

There was a time in my life when I didn't know what a derivative was. What a blissful, innocent time that was. I had my PhD. I was doing perfectly fine. Well, as fine as a newly minted PhD can be. And then one day I made the catastrophic mistake of asking somebody to explain how futures contracts work. And the more I learned, the more I kept thinking, what? People bet on this. You can place a wager on the future price of something you never intend to actually buy. And that's considered a functioning financial market rather than say a casino with better lighting. Except of course in a real casino. The house eventually has to let somebody win a hand. In derivative markets, Wall Street just invents a new deck of cards every time the current deck stops paying out.

Now, you can make the argument that futures and options serve a legitimate purpose. Of course, they let businesses hedge risk, lock in prices, and plan ahead. A farmer can sell next season's harvest at today's price, and sleep at night. That price is reasonable, but of course we live on this planet with these specific people. And so the question becomes what happens when you take that machinery and point it at artificial intelligence?

Because that is what's happening right now. Both the Chicago Mercantile Exchange, CME, and the Intercontinental Exchange, ICE, the two largest derivatives exchanges in the world, are launching compute futures. Contracts that let you trade the future price of renting AI chips. The CME is rolling out contracts tied to the hourly rental price of Nvidia's H100 GPUs, while ICE is launching a broader index of AI compute capacity.

To understand why this is happening, you have to look at the problem AI companies are currently facing. Right now, buying and selling compute is basically like buying a used car in the 1970s. You negotiate a private contract with a cloud provider, AWS, Azure, Google Cloud, or one of the newer neoclouds like CoreWeave or Lambda Labs. The pricing is opaque, the terms are bespoke, and if you need thousands of GPUs next quarter for a training run, you have no way to lock in that price without signing a massive multi-year lease that could bankrupt you if your next model doesn't work out. It's like trying to run a restaurant where meat suppliers charge wildly different amounts for the same cut of meat and there is no public market where you can see what the going rate actually is.

</details>

---

### 价格发现与垄断套牢：当算力被对标为“新石油”

当前 AI 算力采购市场极度不透明，云服务商（如 AWS、Azure 以及 **CoreWeave** 等新兴新算力云）提供的往往是非标准化的私下协议。企业若想在下个季度锁定数千张 GPU 进行模型训练，必须承担高昂的多年期租约风险。**芝加哥商业交易所**（CME Group: 全球最大的衍生品交易所）与**洲际交易所**（Intercontinental Exchange / ICE: 跨国金融与大宗商品交易所运营商）相继推出算力期货，正是试图建立公开可交易的**基准价格**与**远期曲线**（Forward Curve: 反映市场对某项资产在未来各时间节点预期价格的曲线图）。

根据**波士顿咨询公司**（BCG: 全球顶尖管理咨询机构）的测算，一套成熟可靠的算力远期曲线有望在 2030 年前为全球 AI 基建投资削减约 1160 亿美元的融资借贷成本。芝商所能源产品负责人甚至公开将算力比作 20 世纪的原油。然而，大宗商品的历史规律证明，每一轮严重的实物资产泡沫都会被围绕其构建的衍生品杠杆数倍放大。更为关键的结构性风险在于：石油是无差异的同质化商品（Fungible Commodity），而当前 CME 与 ICE 的期货合约均直接绑定英伟达的 **H100** 芯片。在英伟达占据 AI GPU 市场约 80% 份额的背景下，黄仁勋不仅是一家芯片公司的管理层，更成为了手握底层基准资产定价权的“超级商品寡头”。

<details>
<summary>Original English Source</summary>

You would have no way of knowing whether you were getting a fair deal. You couldn't plan your menu prices 3 months out. You're essentially flying blind. A futures market fixes that. It creates a public tradable reference price. Everyone can see what GPU time is expected to cost next month, next quarter, next year. Companies can lock in their compute cost today instead of hoping prices don't spike before their next training run. Lenders can look at the forward curve to assess whether a data center's revenue projections are realistic before extending a loan.

For the beautiful non-nerds in the audience, a forward curve is just a chart of what the market expects a commodity to cost at each point in the future. If GPU rental prices are expected to drop, a lender can see that before agreeing to finance a data center whose business plan assumes they won't. The CME's head of energy products said it directly. I'm quoting here. "Just as oil fueled the 20th century's economy and evolved from spot trading into a global derivatives market, our futures contracts will now turn compute into a standardized tradable commodity."

So that quote is interesting. They are not comparing compute to software or to cloud services or to any other technology product. They're comparing it to oil, a physical resource that powered the global economy for a century. And they're building the financial infrastructure to treat it accordingly.

Now, there is a version of this story that is entirely positive. Transparency and price discovery are good for any market and hedging is of course good for any business planning more than a quarter ahead. BCG estimates that a reliable forward curve of compute prices could reduce borrowing costs across AI infrastructure investment by about $116 billion through 2030. That is real money saved by real companies making real planning decisions. If you're building a data center and you can hedge your GPU cost the way a mining company hedges metal prices, that's genuinely useful financial engineering, of course.

But here is where my personal history with derivatives makes me twitch a little bit. Every major commodity bubble in modern history was amplified by the financial instruments built around it. The 2008 financial crisis wasn't caused by people buying houses. It was caused by the derivatives, the collateralized debt obligations, the credit default swaps that let Wall Street make leverage bets on housing prices disconnected from whether anyone was actually living in the houses. The futures market for oil is used for hedging, yes, but it's also used for speculation by traders who will never take delivery of a single barrel.

The AI giveth and the AI taketh away. When you create a liquid futures market for something, you don't just enable prudent risk management. You also enable people to pour money into bets on price movements, which can drive prices in directions that have nothing to do with actual supply and demand.

And compute futures have one additional feature that oil futures don't. Both the CME and ICE contracts are tied specifically to Nvidia chip rental prices. Not AMD, not Intel, not Google TPU, Nvidia. In the oil market, a barrel from Chevron is chemically identical to a barrel from ExxonMobil. The commodity is fungible. No single producer controls the benchmark. But Nvidia holds an estimated 80% market share in AI GPUs. An hour on an H100 is specifically Nvidia's product. If compute truly becomes the new crude oil, Jensen Huang isn't just the CEO of a chip company. He is the commodity baron of a type that has never existed in the history of energy markets because the commodity itself is his. At this rate, by 2028, Jensen won't just sell the hardware. He'll probably charge you a monthly subscription fee for the ambient heat radiated by his leather jackets.

Which brings us to the question underneath all of this. Is the demand real? But before I answer that, and trust me, the numbers are worth the wait, let me tell you about today's video sponsor. Morph from modelcode.ai is built for one of the least glamorous problems in software: the enormous legacy codebase that everyone knows needs modernizing, but nobody particularly wants to touch. Mainstream LLMs can be useful for rewriting a function or explaining a strange piece of code. But modernizing an entire system is a very different problem. Morph from modelcode.ai is the world's leading generative AI platform built specifically for legacy code modernization. It analyzes and maps the codebase, creates a modernization plan, executes and tests the work, and lets you approve every step before anything reaches production. So whether you're moving from .NET 4.5 to .NET 10, web forms to React, or breaking apart an ancient monolith, it is designed to handle the wider modernization process rather than just individual snippets. Modelcode.ai customers report reducing projects that might once have taken years down to months, weeks, or even less. You can sign up and analyze your codebase completely free with no credit card required. Morph gives you a realtime cost estimate before any work begins and you only pay if you decide to proceed. Visit modelcode.ai/m and use code house of l. You'll get 60,000 free credits every month for your first year, unlocking nearly $10,000 of real world value completely free just for using my link.

</details>

---

### 循环融资与闲置算力：万亿生态背后的真实需求成色

衍生工具的有效性完全取决于底层资产的真实供需。如果算力需求是广泛而坚实的，期货将大幅提升资本配置效率；反之，若需求高度集中且依赖人为制造，衍生品只会加速系统性风险的累积。仔细审视英伟达的收入结构可以发现：其高达 70% 的应收账款仅来自五家大客户，更有 60% 的总营收直接依赖于单一未公开客户。这种极端的客户集中度使得整个生态呈现出类似“封闭会员俱乐部”的特征。

**循环融资**（Circular Financing: 核心企业通过投资参股下游客户，客户以此信用借债并回购核心企业产品的资本闭环）进一步扭曲了真实需求信号。以澳大利亚云服务商 **Sharon AI** 为例，其 2026 年第二季度营收仅为 190 万美元，却与大股东英伟达签署了高达 49 亿美元的订单协议；按其现有营收体量，需持续运营近 650 年才能偿付该合同。与此同时，英伟达将部分客户的账期从 90 天延长至一年。而在算力消耗端，**xAI** 部署的 50 万张 GPU 集群在今年 4 月的实际利用率仅为 11%，相当于建造了一座超级发电厂却让 89% 的发电设备处于空转闲置状态。

<details>
<summary>Original English Source</summary>

Right, the demand, because futures help or hurt depending entirely on what's underneath them. If the underlying demand for compute is genuine, broad-based, and durable the way global demand for oil is genuine, broad-based, and durable, then futures are exactly the right infrastructure to build. Great. They'll make the market more efficient, more transparent, and more resilient. But if the demand is concentrated, fragile, and particularly manufactured, then futures are a derivatives layer on top of a bubble. And that's how you turn a correction into an actual crisis.

So, let's look at what's underneath here. Nvidia's $96 billion quarter is real money, but 70% of their accounts receivable come from five customers. 60% of total revenue came from a single customer they won't name. If you ran a restaurant and 70% of your tabs were from five regulars, you wouldn't call that a thriving business. You'd call it maybe a private dining club with a very expensive lease.

I've covered the circular financing structure in detail before, so I'm going to keep this part brief. Nvidia invests in companies. Those companies use the investment to raise debt. They spend that debt buying Nvidia GPUs. Nvidia books the revenue. Just look at Sharon AI as an example. That's an Australian cloud company. Their quarterly revenue in Q2 2026 was $1.9 million. Nvidia signed a $4.9 billion deal with them. Sharon AI's own SEC filing states that the company has limited experience in delivering, implementing, and managing such contracts at scale. A company making less than $2 million a quarter just signed a deal worth nearly $5 billion with its largest investor. I mean, at their current revenue, it would take Sharon AI roughly 650 years to earn the value of that contract. For context, 650 years ago was 1376. Nobody had discovered the Americas yet. To believe this deal pays for itself in current numbers, you'd need Jesus to personally return, take a seat on the board, and just start closing enterprise sales. And even then, he would probably spend the first two quarters just trying to figure out how to put water into wine down as recurrent SaaS revenue.

Nvidia has also extended payment terms from 90 days to up to a year for certain investment grade customers. That sounds reassuring until you realize that investment grade in this context does not necessarily mean Microsoft. It could include CoreWeave which has had to raise billions in fresh debt every single year just to stay operational.

Meanwhile, Elon Musk's xAI built a 500,000 GPU cluster that was running at only 11% utilization as of April this year. That is the computing equivalent of building the world's largest power station and then leaving 9/10 of it sitting in the dark. Or to reframe it in terms Elon might appreciate in case he's watching this video: it's a bit like buying a fleet of Cybertrucks, parking 89% of them in a field, and claiming you've revolutionized logistics. All of this, the circular financing, the futures contracts, the extended payment terms, all of it is a bet, a very large, very expensive bet that the demand for AI compute will grow fast enough and lasts long enough to justify the debt.

</details>

---

### 生产力验证与社会阻力：AI扩张面临的现实断层

判断算力债务是否可持续，关键在于生成式 AI 是否具备能够支撑万亿资本开支的实用价值。学术实证研究并不支持对生成式 AI 的全盘否定：哈佛大学与波士顿咨询针对 758 名咨询顾问的同行评议研究表明，合理使用 AI 工具可使任务完成速度提升 25%、产出质量提高 40%；另一项针对 5000 余名客服代表的独立研究也测得 15% 的平均生产率提升。这表明技术本身并非毫无用处，当前的核心矛盾在于其实用价值的变现速度无法匹配硬件军备竞赛的消耗速度。

在技术效用之外，社会舆论与法律合规层面的阻力正在迅速收紧算力扩张的空间：
* **社区抵制加剧**: 全美有近 70% 的受访民众反对在居住区附近兴建数据中心，目前已有至少 48 个数据中心项目、涉及 1560 亿美元的投资因地方阻力而搁置；**OpenAI** 首席执行官山姆·奥特曼（Sam Altman）公开承认公众对数据中心基础设施存在强烈的负面情绪。
* **资本与劳工撕裂**: 亚马逊在宣布 2026 年投入 2000 亿美元 AI 资本开支的同时，其依赖美国食品券补助的基层员工比例自 2020 年以来激增了近两倍。
* **版权诉讼风暴**: 索尼与华纳音乐正式对 **Anthropic** 提起大规模知识产权诉讼，而 Anthropic 此前已就历史版权纠纷支付了高达 15 亿美元的和解金。

<details>
<summary>Original English Source</summary>

And demand only grows if the technology is actually useful. So, before I go any further, I want to address something I see in every single comment section on every single video that I've made so far. I know a lot of people in the comments are adamant that generative AI is useless, and I understand the frustration driving that, but the research doesn't support this blanket dismissal.

A peer-reviewed Harvard and BCG study of 758 consultants found that those using AI completed tasks 25% faster with 40% higher quality output, though the gains depended heavily on the human knowing when and how to use the tool. A separate study of over 5,000 customer support agents found a 15% average productivity increase with the biggest gains going to less experienced workers. The picture is genuinely mixed and I want to do a proper deep dive on this one in a separate video because it deserves one and I don't want to derail this one. But the claim that nobody benefits from generative AI is simply inaccurate. These companies are not attracting hundreds of billions in investment because the technology does nothing. The question is not whether AI is useful. It's whether it's useful enough to justify what's being spent on it.

But despite generative AI being useful, for demand to grow, something else has to change: the way people feel about AI. And right now that sentiment is moving in the negative direction. 7 in 10 Americans oppose building a data center near them. At least 48 data center projects representing $156 billion in investment have been blocked or stalled by local resistance. Sam Altman himself admitted recently clearly people hate data centers right now at least. That's the CEO of OpenAI conceding that the public does not want the infrastructure his business model requires.

Meanwhile, the number of Amazon workers relying on food stamps has nearly tripled since 2020, while the company announced $200 billion in AI spending for 2026. I'm not going to editorialize any of that. I'm just going to leave it there. We all know what it means.

On top of all of this, Sony and Warner just sued Anthropic, alleging one of the largest and most blatant ongoing thefts of intellectual property in history, a year after Anthropic already paid $1.5 billion in the largest copyright settlement in US history. So, to summarize the demand situation, the public hates your buildings, your workers cannot afford groceries, and the music industry thinks you're a pirate. Other than that, the vibes are immaculate.

</details>

---

### 债务买时间：互联网泡沫的重演与漫长出清

债务本身并非负面工具，从铁路网络、电网到电信光缆，人类历史上所有重大基础设施建设无一不是由债务驱动。债务的本质是“购买时间”——为硬件降本、需求培育与技术落地争取窗口期。然而，当前 AI 产业链正遭遇双重夹击：一方面，GPU 采购与借贷成本持续攀升，版权诉讼负债不断累积；另一方面，消费级杀手级应用尚未出现，Token 调用增长逐步步入平台期，基础设施在社区和政策层面频频受阻。

即将于 10 月运行的算力期货市场将提供客观的价格发现信号：若远期曲线呈现**期货升水**（Contango: 远期价格高于即期价格，反映市场预期需求持续扩张），则证明增量资本仍在流入；若呈现**现货升水**（Backwardation: 远期价格低于即期价格，反映市场预期未来需求见顶回落），则表明算力资产正在面临估值修正。历史最具参考意义的样本是 2000 年前后的**互联网泡沫**（Dot-com Bubble: 20世纪末由互联网概念过度投机引发的资产泡沫）。彼时互联网技术本身真实有效，亚马逊与谷歌也最终脱颖而出，但纳斯达克指数依然经历了 78% 的深幅回调且耗时 15 年才修复失地。当前的 AI 产业大概率不会走向灾难性的崩盘，而是经历一场漫长、乏味的资产通缩与估值出清。英伟达仍将保持卓越的盈利与芯片制造能力，但其市值将从 30 万亿美元的狂热预期回归至客观现实。

<details>
<summary>Original English Source</summary>

Here's where I land, and I want to be careful because I really don't think that it's simple. Debt is not inherently a bad thing. Debt buys time. Time for cost to decrease, time for demand to grow, time for the technology to find its footing, time for further research and innovation, beautiful things. Every major infrastructure buildout in human history was financed by debt. Railways, electricity grids, telecoms networks. The question with debt is always the same: is there a viable path to the revenue that services it?

Right now, both paths are being a bit obstructed. Costs are not decreasing. GPU prices are up. Debt is getting more expensive. Copyright liabilities are accumulating. And demand isn't scaling the way the financial structure requires. Public hostility is blocking infrastructure. The killer app still doesn't exist. And token spend is beginning to plateau.

The compute futures market launching in October will give us something we've never had before: a real-time market price signal of where this is heading. If the forward curve goes into contango, meaning future prices are higher than current prices, the market believes demand is growing. If it goes into backwardation, meaning future prices are lower, the market believes demand has peaked. That's the most honest signal available because it's people putting actual money behind their predictions rather than posting on X.

My prediction, and I'm being completely honest, predictions are hard, and I could definitely be wrong, is that this doesn't end in a dramatic crash, but rather it ends in a slow, boring deflation. The technology is definitely real. The productivity gains are often measurable and definitely real, but the financial structure around it is priced for a revolution that hasn't happened yet and may not happen on the timeline the debt requires.

The most useful historical parallel here is the dot-com era. The internet is of course a real thing. Amazon is around. Google as well. Email is a real thing. But the NASDAQ back then still lost 78% of its value and took 15 years to recover because the market had priced in a future that was directionally correct but wildly premature. Most of the companies riding the wave didn't survive. The ones that did became the most valuable businesses on Earth. The technology was not the problem, but the financial structure around it definitely was.

I think big tech AI companies follow the same pattern. The useful applications will likely survive. The infrastructure likely rationalizes. Several of the Neocloud companies and possibly one or two AI labs either fold or get acquired at a fraction of their peak valuations. Nvidia will likely remain a large profitable company. They make genuinely excellent chips, but at a significantly lower market cap because the market will eventually price in realistic demand rather than $30 trillion fantasies. Or of course, people could just become pro-AI as well and everything's going to be okay. Who knows? Only Oracle, actually.

The responsible position here isn't hoping that generative AI fails. Hoping a technology fails because its corporate stewards are reckless is a bit like hoping medicine fails because pharmaceutical companies overcharge. The responsible position is demanding that the financial structure be stress tested before it gets bigger. That the people building this show their working, that someone counts the chairs before the music stops.

But if you're wondering how the AI industry ended up with a public that hates it this much, I made a separate video about how the word slop broke the internet's brain and what it actually means for anyone using AI responsibly. Thank you so much for watching. I'll see you in the next one.

</details>