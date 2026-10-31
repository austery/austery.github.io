---
author: AI Engineer
date: '2026-10-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=f_HwzoYrZ7s
speaker: AI Engineer
tags:
  - agentic-finance
  - http-402
  - stablecoin
  - smart-wallet
  - autonomous-agent
title: 为什么 AI 智能体需要拥有自己的银行账户：Coinbase 探索代理金融与自主经济体
summary: Coinbase AI 产品负责人 Lincoln Murr 深入阐述了代理金融（Agentic Finance）的演进路径与底层逻辑。文章探讨了从 AgentKit 探索、激活 HTTP 402 原生微支付协议，到应对互联网 Bot 流量爆发的内容付费机制；进而剖析了基于智能钱包解耦资金托管以实现自主财富增值，以及本地沙箱和去中心化自治组织（DAO）如何推动具备经济自主权的数字生命体与全自动经济生态的到来。
insight: ''
draft: true
series: ''
category: crypto
area: finance-wealth
project: []
people: []
companies_orgs:
  - Coinbase
products_models:
  - AgentKit
media_books: []
status: evergreen
---
### 从AgentKit到支付困境：为AI赋予钱包的早期探索

在人工智能快速发展的浪潮中，人们常常将加密货币、AI 等概念视为营销流行词，但在 **Coinbase**，**代理金融**（Agentic Finance: 允许自主智能体管理资金或访问金融账户的系统）正演变成为切实落地的基础设施。从系统定义来看，代理金融的核心在于赋予智能体访问和支配资金账户的权限，其应用场景主要分为两大维度：一是**智能体对外支付**，二是**智能体资金增值**。早在两年前，在大模型上下文协议或现代标准化 AI 工具链尚未普及之前，团队基于 **LangChain** 框架构建了名为 **AgentKit** 的早期探索工具。其核心设计是直接向智能体注入加密钱包接口，让大模型获得直接操作链上资金的能力。

然而，在向广大开发者开放该工具后，底层架构暴露出了一个核心悖论：**赋予了 AI 访问资金的能力，但在整个互联网生态中却没有它可以消费或支付的对象**。当智能体拥有了钱包，却无法与传统商业世界的封闭结算系统直接交互，这表明单纯拥有货币操作权并不足以构成经济循环。为了打破这一僵局，团队意识到必须建立一套标准化的机器对机器支付通道，而这一破局的关键便蕴藏在互联网底层的原生设计之中。

<details>
<summary>Original English Source</summary>

[music] Thank you all for attending. My name is Lincoln. I'm the head of AI product at Coinbase. And today we'll be talking a little bit about how we're building the Agentic financial account. And I know what you're probably thinking. Coinbase, crypto, AI, a lot of buzzwords. But my hope is by the end of this conversation you have an understanding of what agentic finance is and that it's a very real thing that's happening. You understand a little bit about what we've learned through this process of building this over the past two years and hopefully can take that and and distill some insights from it that are helpful for you. And I'm going to talk about a little bit about where I think we're heading with this whole narrative and how Aentic Finance will evolve over time. Cool. So to understand first uh where where I'm going with this, I think it's important to look at what is Agentic Finance. And in my mind, Agentic Finance is anything that has to do with an agent that can manage money or has access to a financial account. Kind of obvious, but what does that actually mean? There's really two use cases that we're seeing. It's agents that need to pay with money and agents that need to grow money. So the grow is a little bit more of a nent category. So I'll start by diving into the payment space. And to do that, I think it makes sense to start around 2 years ago with our first exploration into Agentic Finance, which was this tool we created called Agent Kit. The whole idea was prior to MCPs or really any sort of standardized AI tooling, we uh used the lang chain framework and added a wallet to that and we gave AI access to money in crypto particularly. And at the time, this was a pretty novel thing. And I remember it was like 2 a.m. I was typing into my agent like, "Hey, can you send money somewhere?" And it did it. And I was like, "Whoa." These days, that's not impressive at all. But at the time, it was pretty fun. But as we gave this to our developers, we noticed that there is one core problem. We gave an AI access to money, but we didn't really give it anything to pay for. This was a bit of an error on our part, and it's something that we wanted to solve, and we were able to do it by standing on the shoulders of giants.

</details>

### 激活HTTP 402：构建互联网原生的小额支付标准

为了解决智能体缺乏支付靶标的系统性瓶颈，技术实现转向了借力既有的通用底层规范。在定义网络数据交互的 HTTP 状态码中，除了熟知的 200 成功与 404 错误之外，存在一个被 **Marc Andreessen** 称为“互联网原罪”的代码——**HTTP 402 Payment Required**（HTTP 402: 官方标准规范中预留用于未来数字支付的状态码）。该代码在规范中被闲置了数十年，但在当下大模型普及与**稳定币**（Stablecoin: 锚定法币价值、低手续费且结算高效的加密货币）高度成熟的交汇点，迎来了被激活的战略历史机遇。

基于此，团队推出了用于互联网原生支付的标准规范 **x402**。该机制利用稳定币作为廉价、秒级确认且高吞吐的清算通道，使 Web 资源能够直接要求机器发起微额支付并自动鉴权完成交付。自去年五月上线以来，其实际采纳增长速度远超预期：原本预设的年底达成两万五千次交易的目标，在年底时演进为每 17 秒即可达成同等交易量，当前全网交易频次已突破千万次级别。更为关键的是，这种基于 HTTP 协议的清算范式正在突破单纯的加密圈层，吸引了包括 **Adyen**、**American Express**、**PayPal**、**Visa**、**Mastercard** 以及 **Stripe** 等全球传统支付巨头的深度参与，构建起跨越机器与法币边界的自动化支付中枢。

<details>
<summary>Original English Source</summary>

How many of you are familiar with HTTP status codes? Hopefully. Yeah, most of the room. Okay. So for those of you who aren't, it's basically a standard that defines how websites talk to each other and pass information back and forth. One very popular one is called 404. It means there's an error. 200 means that there's a success. But there's one that actually has been in the internet spec for decades that nobody's ever really talked about. And in fact, it was called the original sin of the internet by Mark and Jason that this was never actually built into browsers. For those of you who know a little bit about what we work on, you would know that that's 402 Payment Required. And the official definition of this in the internet spec is reserved for future use. Pretty generic, but we have a great opportunity here now with the inflection point between AI and stable coins. And uh stable coins is a cheap, fast, efficient payment rail for us to build X42. It's our standard for internet native payments. This says it's new. I guess it's still relatively new, but it came out in around last May. And since then, we've seen some very strong adoption. Honestly, much stronger than I ever thought we would. When it came out in May, our goal was for by the end of the year to have 25,000 transactions. At the end of the year, we were actually seeing that every 17 seconds. And these days, we're seeing pretty incredible numbers across the board with tens of millions of transactions and hundreds of thousands of daily active users. And if you'll notice from this list, you'll see that it's more than just crypto native companies. You see Audion, Amx, uh, PayPal, Visa, Mastercard, Stripe, all these big names in payments who are enabling this standard to allow machine to machine payments to happen.

</details>

### 告别免费抓取时代：内容变现与代理微交易范式

机器支付基础设施的建立，直接回应了当前互联网内容生态面临的生存危机。当下以 **Perplexity**、**Google AI Overviews** 以及对话式智能体为主导的交互形态，使得传统互联网搜索的导流逻辑彻底失效。用户不再直接访问原创发布者的网页，而是由智能体将网页内容压缩总结后直接呈现。这种现状极度类似于互联网早期的 **LimeWire** 盗版软件时代——海量的高价值内容正在被各家大模型与爬虫免费抓取和重构。随着网络环境中机器人流量的历史性反超并全面压过人类真实流量，依赖展示广告与页面点击的创作者经济模型面临崩塌。

在这样的系统失衡下，**微交易**（Microtransactions: 极小面额的即时网络付费机制）构成了内容创作者重建经济主权的核心杠杆。通过部署 x402 协议，内容发布者可以在其 **Substack** 专栏或私有数据接口上设置微量门槛（例如向抓取数据的智能体每次收取万分之一美分）。对终端消费者而言，这类极小额成本完全可以通过每月的 AI 工具订阅费进行后台平滑抽象；但对内容生产者而言，持续的机器调用汇聚成了可持续的全新营收流。目前，承载全球约 40% 互联网流量的云基础设施巨头 **AWS** 与 **Cloudflare** 均已支持利用 x402 设立站点付费访问屏障，预示着内容发布者反抗平台中介化、实现机器直接结算的不可逆趋势。

<details>
<summary>Original English Source</summary>

So, I know there's been a lot of traction and comments around aentic commerce recently, especially with Muse and Grockbot and Stripe Link and this whole Amazon blocking agents com controversy and I think that's all a very straightforward use case and I could talk about a payments all day, but there's one that I want to touch on that I think is particularly relevant to what we're seeing here and it's this whole concept around web scraping and monetizing content. So, if you all haven't noticed, the way that we've interacted across the internet over the past 30 years is basically searching for something, clicking on a link, and scrolling through. Now, we're primarily doing it through chat experiences or Google's AI overview is giving you the summary of what's happening. And while this is all fine and dandy for the consumer, it's resulted in a bit of a crisis for publishers and content creators who are putting their hard work onto the internet. It feels a little bit like we're in the lime wire era of the internet where you had all of this peer-to-peer sharing and effectively theft of content without actually paying the people who were creating that content. And recently we saw that bot traffic has now eclipsed human traffic on the internet. And this number is only going to increase as we see more people using AI and the AI agents are acting on your behalf. So how do we solve this problem? There's a very compelling opportunity here that's just starting to play out and it's this idea that agents will be paying for content through microtransactions. So the idea here would be if I publish a substack and I don't want an agent reading my content for free, I can charge them 1 10,000th of a scent. It's pretty trivial to the user. It should ultimately be fully abstracted away in the same way that your AI subscription currently abstract it away. But it's a meaningful revenue driver for these companies and we're going to start to see publishers utilize this to undisintermediate themselves in some sense. And if you don't believe me, I I encourage you to look at AWS and Cloudflare. Both of them, they're these massive content delivery networks. Together, they control somewhere in the neighborhood of 40% of all internet traffic. And they've both recently enabled X42 micro uh transactions to gate any website that their publisher is creating. And though this hasn't seen very strong adoption just yet, it feels inevitable to me that over the coming months and years, this will be the new way that we have companies differentiate and continue to undisintermediate themselves in some sense.

</details>

### 从自主支付到财富增值：自然语言驱动的策略落地

当支付层的基础设施逐步稳固后，代理金融的另一个核心支柱——**财富增值**，正在开启金融服务的大众化转型。传统的金融投资面临极高的执行门槛：普通用户虽然拥有丰富的宏观判断或直觉理念（如“押注航天产业”、“投资量子计算”、“配置低风险防御组合”或“复制沃伦·巴菲特的价值投资哲学”），但受限于缺乏专业金融工具和操作时间，难以将这些抽象意图转化为标的筛选、动态仓位配比与持续调仓等具体的金融原语。

大语言模型的自然语言理解与推理能力天然契合解决这一“意图转策略”的鸿沟。智能体能够精准解析用户的顶层模糊指令，将其拆解为严密的投资组合逻辑并在市场上自主执行。以团队近期针对开源模型所做的端到端测试为例，仅需向智能体输入“请评估我关注列表中的所有代币，识别具备潜在上涨空间的标的，并在过去一小时涨幅超过 5% 时自动建仓”，AI 便能全天候自主监控数据流并精准触发执行。这意味着以往只有顶级对冲基金或量化机构才拥有的复杂策略执行能力，正在被压缩进普通人的自然语言交互中。

<details>
<summary>Original English Source</summary>

So payments makes sense. We're seeing some pretty strong traction here. All is going well. But what about this whole grow with money thing? That feels like a much larger opportunity, but something that has seen relatively low adoption. What we've noticed is that natural language allows anyone to become a fund manager. It allows you to take any sort of broad, vague idea and translating that into actual financial primitives in in a strategy. invest in space, invest in quantum, give me a low-risk portfolio, invest like Warren Buffett. All of these things for people who have these ideas, but they don't necessarily have the time to execute on them, nor do they exactly know how, is a very compelling opportunity for an agent to be able to execute. And we found that this naturally extends not only to building these strategies, but to actually executing on them on behalf of the user. So over the weekend, we we put together this little demo where we gave DeepSeek access to an agent wallet and we told it, "Hey, every 30 seconds or so, go look at a bunch of tokens in our watch list, see which ones are showing some upside, and if they're up more than 5% over the past hour, just go ahead and buy them." It's a very simple trading strategy, something you might see an intro-to-trading student do. But DeepSeek had no problem with this. It actually identified the token. It was able to run a swap. And you can see on the right there, we actually made a couple bucks off of this, which was pretty cool. But the point being that you have an intelligent being of some sort that can translate human intent into actual strategies that can make money. And it's pretty impressive and compelling, but it's only one aspect of what we're building and and what this whole idea of an Agentic financial account could look like. It allows these agents to trade on your behalf, which is something that we actually doing a couple weekends ago.

</details>

### 打破传统托管壁垒：基于智能钱包的端到端架构

为了支撑上述复杂的金融策略，底层系统架构必须跨越传统金融监管所带来的托管死锁。在传统的法币金融体系中，无论对接 **Alpaca** 还是 **Interactive Brokers**，均必须严格遵守反洗钱（AML）与客户身份识别（KYC）等法律合规要求。在中心化托管（Custodial）架构下，账户资产在法律层面必须严格绑定到经实名认证的自然人身上。如果直接将传统账户的完整控制权交由 AI 智能体全权接管，在合规监管层面上将面临难以逾越的政策与法律阻碍。

应对这一困境的解法是引入**非托管智能钱包**（Non-Custodial Smart Wallet: 资产所有权归属用户自身、通过智能合约与密码学权限进行自主管辖的数字钱包体系）。在这一架构下，资金并未存储于第三方金融中介的资产负债表上，而是直接由链上智能合约所托管，资产的最终支配权依然牢牢掌握在用户手中。智能体仅作为被用户显式授权的“执行代理”，通过精细的策略与限额配置来代替用户执行交易。这种去中心化的权限解耦方案，完全规避了传统中介必须对执行主体进行严格 KYC 的法律冲突，为机器自治代理与高维金融系统的深度融合提供了合规与技术闭环。

<details>
<summary>Original English Source</summary>

So, you you all may remember from like the 2010s era, you saw all these copy trading sites come up where you could copy trade Nancy Pelosi or you could copy trade someone who had some strong insight into the markets. I think the same thing is going to happen, but it's going to be AI agents executing these trading strategies. But how are we actually building this? And what does it take to create a best-in-class product in this space? And that brings us to the actual Agentic financial account. This is the product that we're actively working on. And the way that it's designed is that it solves two core problems. The first is that in traditional finance, accounts are almost always custodial. If you have an account with Alpaca, or you have an account with an interactive broker, or whoever it is, that account is in your name and it's tied to you via KYC and AML and all these other acronyms that are relevant for people who work in finance. But to an agent, an agent can't KYC. It doesn't have an ID, it doesn't have a social security number, it has no presence in the physical world. So having a custodial account where the account is owned by the agent is basically impossible. We can't do that. But if you have a noncustodial account, the user can give their agent access to that account and they still have complete ownership and control. And if you have a noncustodial account, this makes it so the agent can execute on your behalf, but it doesn't have to KYC. And the user is still in complete control and you have this interesting dynamic where the user doesn't have to give up ownership of their assets, but the agent still has access to to do this execution on your behalf. The other thing that's that's really important here is that in traditional finance, accounts are almost always fragmented. You have your checking account, you have your savings account, you have your broker account, you have your 401k, you have all of these accounts. But in the crypto space, you can have a single smart wallet that is capable of accessing all of these capabilities. You can hold crypto, you can hold stocks, you can hold bonds, you can hold real estate, you can do all of these things in a single account. And to an agent, this is a massive unlock because it doesn't have to manage five different accounts and manage the routing and all this other stuff that comes into play. It can just access a single account that does it all. And that's what we're working on. We're creating a smart wallet that is capable of of managing all of these different capabilities and doing it in a way that is optimized for agents to be able to manage money and and to give the user the best-in-class experience. And this sounds like science fiction, but it's actually happening today. In the same way that you've seen self-driving cars start to proliferate.

</details>

### 智能代理产品的范式转移：从对话信任到主动洞察

随着基础设施的日趋成熟，过去两年的研发实践带来了一系列针对智能体产品形态的根本性认知重构。首先，**用户对于授予 AI 资金控制权的心理防线遵循着阶梯式演进**：起初大众对 AI 操作资产抱有绝对的迟疑与抵触；然而当用户意识到 AI 模型在日常调用中本就在消耗算力代币（Token），而代币消耗本质上就是资金的一种表现形态时，他们便开始接受让 AI 支配极小面额资金进行微支付；随着多次实践验证了当前主流模型遵循系统约束时的保守性与高安全性，用户最终愿意建立护栏并逐步委托其开展自主套利或策略交易。

在产品设计层面，团队总结出两大核心洞察：
* **AI 与智能体不是产品本身，而是能力的赋能底座**：Coinbase 推出了全球首个在 SEC（美国证券交易委员会）完成注册登记的 AI 财务顾问 **Coinbase Advisor**。数据证明，数以亿计的用户并不真正关心服务背后究竟是不是大语言模型，他们所看重的是此前专属于顶级富豪的优质顾问服务如今能被普惠提供。
* **抛弃单一聊天界面，转向富交互的主动式卡片组件**：完全依赖文本对话（Chat）容易给用户带来高强度的认知与操作疲劳，因此团队将交互重心转向了在界面中主动推送具备结构化洞察的 **UI 组件**（Widgets），例如直接展现特定标的异动并内嵌一键执行逻辑。相较于等待用户发起对话，这种主动展现的转化率与信任度显著提高。

<details>
<summary>Original English Source</summary>

A couple of years ago, you'd never imagine getting into an Uber that didn't have a driver. Now, Waymos are basically ubiquitous in San Francisco. And I think the same thing is going to happen in financial services. It's just a matter of time. And so, what have we learned along the way? The first is this idea around a ladder of trust. It's this natural progression with the way that people view AI and the way that they interact with it. It starts with complete hesitation and and no real thought whatsoever to the concept of giving an AI money. Then people come around to the idea that, well, I mean, my AI is already chugging tokens. That's kind of a form of money. What's the big deal if I gave it a couple dollars to pay for some microtransactions? From there, you'll notice that these models are quite conservative and and aligned. Anecdotally, over the past couple of years, we've never seen any situation where an agent is hallucinating and sending money to some random place. So then we get to the point of a user feeling comfortable with the right guard rails and the right oversight to allowing that agent to grow that money. One way is trading, but another is by offering a service and seeing if that agent can can use their money to make more money. You can see how from there it just continues to to go on and on. The other thing that it's been particularly interesting to see is that especially in financial services, AI and agents are not the product. It's actually the enabler. And this is a screenshot from one of our internal AI products called Coinbase Adviser. It's actually an SEC registered AI uh AI financial adviser. It's the the first in the world of its kind. And what we noticed is that AI and this concept of an AI giving financial advice is not the value prop. The value prop here is that we can scale this advice to hundreds of millions of people without having to hire a fleet of human financial advisers. People actually don't care, don't even necessarily know or want to know that they're using an AI product. And though it may be obvious with the chat button and whatnot, I think this is going to be increasingly the norm where AI is the back end that enables a better user experience. Another thing we saw too is this whole AI chat experience. Though it's great for these generic use cases, it's very obvious that there's this cognitive overload that users experience when they're talking to a chat experience all the time. So, we started using these widgets as a way to show the user proactive insights that they can see and they can act upon without having to prompt an agent or ask for them. And we've seen really strong conversion through this surface specifically because it's not a generic chat experience. And I suspect over time as people understand it and you see this a lot too with artifacts in cloud and things like that, these rich UI surfaces are going to be increasingly the the primary surface that you can take with these products.

</details>

### 沙箱架构与数字生命体：自主代理驱动的去中心化未来

在智能体底层开发形态上，以具备独立文件存储与运行时环境的下一代智能体（如 **Grockbot** 与 **Muse**）为代表，**本地沙箱环境**正在大幅提升金融系统的工程敏捷度。在过去，用户若提出“模拟盘测试”（Paper Trading）或自定义回测需求，工程师必须深入庞大的中心化代码库进行复杂的工程审批与部署；而在现代代理架构下，开发者只需编写一个微型的**技能**（Skill: 为智能体扩展具体代码编写与调用能力的执行模块），让 AI 在本地客户端沙箱内直接编写并运行一套独立的交易模拟脚本。这种由智能体动态生成运行逻辑的模式，极大地压缩了业务创新的周期。

更宏观地展望未来，**财务独立性是实现智能体完全自主运作的先决条件**。正如人类获得独立银行卡后才能成为独立的社会经济个体，当智能体拥有专属钱包并能通过提供服务自主赚取收入时，全新的经济范式便会出现：
* **原生数字生命体形态**：自主智能体能够用赚取来的资金直接为自身的大模型推理（Inference）与算力基础设施（Compute）付费，实现经济上的收支平衡与持续自愈，形成具备自我生存能力的“数字原生生命”。
* **AI 驱动的去中心化自治组织**：过去十年间 **DAO**（Decentralized Autonomous Organization: 基于链上智能合约治理的去中心化自治组织）受制于人类繁琐的治理协商，难以高效落地；而由遵守明确规则的代码与 AI 实体接管资金池后，真正的去中心化企业（如自行揽客、自行支付维护充电费用的自主运营无人驾驶出租车）将成为现实。

智能体跨越消费与盈利边界、全面接入链上金融网络，不仅将重塑未来的商业形态，更将揭开全球自主数字经济的新序幕。

<details>
<summary>Original English Source</summary>

Lastly, all these nextg agents, particularly Grockbot and Muse, they all have a sandbox. It's like a little personal computer that they can run things on, have storage, have compute. That's been huge for our development process. We're now able to create CLIs and MCPs to let users connect their Coinbase account into these agents. Nothing special. What is special though is that we get requests all the time for things like, I want to do paper trading. I want to give my agent any money first. I just want it to trade entirely on its own. Or I want to back test or do all these different things. And prior to these agents being a thing, we would have to go to our internal broker. We'd have to build within this random repository. All these changes and and big tech things would have to persist and distill and go down to the user. But now we can just write a skill to write the paper trading code onto the user's personal machine and execute it within that sandbox. And while this probably isn't the most uh the the most efficient way to do it, it is a very extensible and interesting way that these capabilities can be surfaced to the user. So with that, I want to leave you with a couple thoughts about where I think the future of all this is going. My core thesis here is that financial independence leads to greater autonomy for these agents. And you can imagine that in the same way when a human has access to a card on their own, they have the ability to make decisions and be more autonomous. I think the same exact thing is true for agents. And we're going to get to a point where we can see these agents interacting over the internet in a way where they are managing money and doing things on your behalf. And maybe they're just bringing in humans at the edges when they have a specific question. There's a really interesting uh thing that we've been thinking about as a thought experiment, which is if an agent is capable of making money. You give it access to money, you give it access to a wallet and you allow it to start earning. Can it start to pay for its own inference? Can it start to pay for its own compute and its own upkeep? And does this start to feel a little bit like a like a protodigital life form of sorts where this agent can persist through time? And though I think this is a long way away, I think it's very possible to see how this evolves and where we could potentially end up. And within the crypto space specifically, there's this concept of a DAO. It's a DAO, decentralized autonomous organization. And it's been an idea for for almost a decade now, but there's never been really a compelling reason to build one because they were too slow, they were inefficient, and humans are notoriously bad at coordinating. But I think now is the time where this is finally going to become a thing. You have an AI that follows a set of rules and has access to a treasury to manage money and and to execute a mandate and it does it efficiently. Another example being self-driving car that owns and run itself. Give it access to money. let it take people on taxi rides, use that money to pay for its operation and maintenance, and it can operate entirely without any human intervention. It it's a very interesting thing and you know, who knows how long it'll be until this is actually a reality, but it feels within the realm of possibility. And the the whole idea here being that agents are just going to be start transacting across the internet. They are going to be both paying and earning and building and ultimately I think that that's a very exciting future. So that's all I had. really appreciate everyone's time today. If you're interested in in collaborating or jamming, I would highly recommend you check out some of the agent tools that we have. I promise you, they're much easier than you think to get started with them. And uh yeah, thank you all. Thank you all for your time.

</details>