---
author: AI Engineer
date: '2026-10-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-AOxpwVeIWw
speaker: AI Engineer
tags:
  - agentic-payment
  - cryptocurrency
  - micropayment
  - api-economy
title: 演讲者探讨代理支付协议的普及困境、加密货币优势与按使用量付费演进
summary: 演讲者探讨了代理支付发展现状与普及障碍，指出智能体目前主要通过固定账户和 API 密钥交互。演讲者认为加密货币因无单点控制与无退单特性适合代理支付，并介绍了 x402 协议通过批结算支持按使用量计费的实践进展。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Apify
  - Coinbase
products_models:
  - x402
media_books: []
status: evergreen
---
<!-- chunk 1/3 -->

大家好。欢迎来到我的演讲环节。今天我要谈谈代理支付（agentic payments），尤其是那个紧迫的问题——既然现在我们已经有了所有这些公开的支付协议，那么最大的疑问就是：为什么没有人使用它们？为什么智能体不进行支付？

<details><summary>Original English</summary>
[music]

Hello everyone. Uh welcome to my s session and uh today I'm going to talk about agentic payments and uh in particular the pressing question now that we have all the patent payment protocols. So the big question is like why is uh nobody is using them? Uh why don't why don't uh the agents pay and
</details>

在开始之前，先做个简短的介绍。在 Apify，我们运营着一个 AI 工具市场，我们将这些工具称为 actors。我们大约有 80,000 个这样的工具，它们覆盖的用例包括从社交媒体网站提取数据、电子商务、酒店住宿、旅游、搜索引擎以及一般的自动化等。基本上，它们帮助你自动化处理在网络上的工作。这些 actors 是由一个全球创作者社区创建的，他们构建这些工具并发布在我们的商店中，然后我们将其销售给用户和客户。就在上个月，我们向创作者支付了近 200 万美元用于他们的 actors。所以这是一个充满活力的双边市场。显而易见，我想大家现在可以理解为什么我们对代理支付抱有极大的兴趣，因为对我们来说，这只是我们将 actors、工具和创作者出售给更多人和智能体的又一种方式，对吧？因此，每当出现可以让我们的系统、平台和市场进行集成以允许智能体购买这些工具的新途径时，我们都会迅速跟进并将其添加进来。

<details><summary>Original English</summary>
before I start uh just a quick introduction uh at API we're running a marketplace of uh tools for AI uh we call these tools actors we have about 80,000 of them and they cover use cases like extraction of data from social media sites, e-commerce, hospitality, travel, search engines and general like automation. Basically they help you automate uh your uh work on the web and these actors are created by a global community of creators and uh so they they they build them publish them on our store and we sell them to the users to the customers and uh just last month we paid almost $2 million to the creators uh for their actors right so it's like a driving two-sided marketplace so obviously I think by now you can understand why we take great interest in agic payments because for us it's just another way how we can sell our actors, our tools and our creators to uh to uh more people and agents, right? And uh so obviously uh whenever there was a new new uh uh way how we can integrate our system, our platform, our marketplace uh to let agents agents buy those tools uh we we went fast and added those things.
</details>

实际上，去年在旧金山举办的 AI Engineer World's Fair 上，我是唯一一个谈论这个话题的人，也就是关于代理支付以及更广泛的智能体经济的话题。因为在当时，它确实还不是那么众所周知，谈论它的人并不多。我认为在过去的一年半里取得了巨大的进展。今年在旧金山的 AI Engineer World's Fair 上，就设立了一个专门针对代理支付的分会场。

<details><summary>Original English</summary>
So uh actually uh last year uh at AI engineer world fair in San Francisco I was the only one who was talking about this topic about the topic of Asian payments and uh agent economy in more broadly because back then it wasn't really like you know well known uh not many people talked about it and I think like over the last year and a half uh there's been a great progress right so uh this year uh on AI engineer worlds fair in San Francisco there was a dedicated uh track uh for agentic payments
</details>

现在，过去这一年中，我想几乎所有人都明白了：智能体为了完成越来越长周期的任务，实际上需要预算。因为在某个时刻，它们会请求你批准某项开支等等；如果你希望它们具备自主性并真正完成更大的任务，你可能需要给它们资金。在过去一年半里，这个领域取得了巨大进展。Gartner 预测到 2028 年这将是一个规模达 15 万亿美元的经济体，并且企业间（B2B）80% 的活动将通过智能体自主完成。我的意思是，这可能有点过高了，但我们拭目以待。不过无论如何，金融和金融科技领域的众多参与者都加入了这一潮流，因为他们看到了这个机遇的规模。因此，在过去的一年半里，我们看到了许多不同的工具和支付标准的涌现。

<details><summary>Original English</summary>
And now you know over the past year think like uh really everyone understands that uh Asians in order to complete ever longer tasks they will actually need uh budget uh because you know at some point uh they will ask you to to approve something and so on and if you want them to to be autonomous and really complete bigger task you might need need to give them money and u there's been a huge progress over the past year and a half uh in this domain so u I think like guard predicts uh that by 2028 uh this will be like a $15 trillion economy and that 80% of B2B activity between uh between uh companies will be done autonomously through agents. I mean that might be a little too much but we'll see. But anyway, a lot a lot of players in the finance uh and finance uh in fintech uh jumped on this band bedwagon because they understood they understand the size of this opportunity. So we saw a lot of different uh tools and payment standards uh appear over the past you know year and a half.
</details>

### 支付标准的演进

这一切始于 Lightning Labs 的 L402。那是在 2020 年年中，出现得非常早。去年 4 月，万事达卡推出了 Agent Pay；随后在 2025 年 5 月，Coinbase 推出了 x402，这可能是目前最流行的智能体支付标准。

<details><summary>Original English</summary>
So it started with L42 by Lightning Labs. Uh it was mid 2020 were super early and last year in April Mastercard agent pay uh then May 2025 X42 by Coinbase. It's probably the most popular agent payment standard currently.
</details>

去年 6 月，Skyfire 联合 Visa 推出了 KYA Pay；还有来自 Google 的智能体支付协议 AP2；接着在去年 9 月，由 OpenAI 和 Stripe 提出了智能体电子商务协议 ACP；10 月，Visa 提出了受信任智能体协议 TAP；今年 1 月，Google 和 Shopify 推出了通用商务协议 UCP；此外还有更多：支付宝推出的智能体电子商务信任协议 ACTP；Stripe 和 Tempo 合作的机器支付协议 MPP，这是今年早些时候推出的；到了 4 月，支付宝又推出了智能体移动协议 AMMP；最后但同样重要的是，银联推出的智能体支付开放协议 APOP。哦，还有 OKX 推出的 OKX 智能体支付协议。所以你可以看到，这里已经成为智能体电子商务未来的激烈战场，因为所有这些参与者都明白：智能体在未来的某个节点必然会进行支付，而这些公司确实希望参与到这个新未来中，并且更倾向于利用它们现有的网络和基础设施来实现这一点。

<details><summary>Original English</summary>
Uh in June last year uh KYA pay uh by Skyfire by Visa. uh we have uh Asian payments protocol AP2 by Google then agent e-commerce protocol ACP by openai and stripe in September last year uh in October trusted agents protocol tap by visa uh in January universal commerce universal commerce protocol UCP by Google and Shopify there's more agent commerce agent e-commerce trust protocol ACTP by Alipe uh machine payments protocol MPPP by Stripe and Temple. Uh that's from uh early this year. And uh from April, Asian mobile protocol, MMP, AM by Alipe. And uh last but not least, Asentic Payment Open Protocol, APOP by Union Pay. Oh, there's more. Uh OKX, agent payment protocol by OKX. So you can see this became a heated battleground uh for the future of agent e-commerce because all these like players understand okay agents are going to pay at some point and uh these companies actually want to uh you know have part of the of the of this new future and uh preferably to use their networks and existing infrastructure to do that.
</details>

哦，还有一个万事达卡的面向机器的智能体支付（Agent Pay for Machines）。有如此多的参与者，以至于现在要跟上所有不断涌现的新标准确实非常困难。我认为，整个智能体商务对加密货币行业的人来说成了巨大的利好消息，因为除了购买违禁物品和对配偶藏私房钱之外，这似乎终于成了他们长期以来一直在等待的真正应用场景。我自己并不是一个加密货币人士，我没有长期持有任何代币，也没有任何加密货币，但我确实认为加密货币在赢得这场代理支付之战中处于非常有利的地位。因为加密货币如果设计得当，就没有单一的所有者，没有单一的公司去控制整个生态系统；并且它具备的一些特性使其非常适合用于代理支付。

<details><summary>Original English</summary>
Oh one more agent pay for machines by Mastercard. So there's players a lot of these and it's really hard to keep track uh of all the new standards happening right now. Uh and I think like u this whole agent commerce became like a huge uh uh huge uh well big news for for uh crypto people because finally uh there seems to be like a real use case they waiting for for a long time you know for crypto except for uh like buying illegal substances and hiding money away from your spouse and I actually believe that like I'm not like a crypto person myself I'm not hodling anything I don't have any crypto but um I I think like crypto is actually very very well positioned uh to win in this like agentic payments wars because uh crypto like uh if done well is uh it doesn't have like single owner there's like no single company controlling the the ecosystem right and u and uh it has like properties that make it very useful for agentic payments.
</details>

例如，如果将加密货币与信用卡、PayPal 或 PayPal 小额支付、或者银行借记卡进行比较，它的成本要低得多。你根本无法将这些传统支付方式用于小额智能体交易，这在经济上是不划算的。此外，传统支付方式还存在退单（chargebacks）问题。所有在线卖家都知道，你必须考虑到有些人就是会滥用你的服务然后要求退款，这对在线业务来说就是一种家常便饭。但在智能体世界中你不能这样做，因为智能体的数量是无限的，它们实际上会卷走你所有的钱，或者免费享受你的服务。而在加密货币上是没有退单的，只有退款，但退款完全取决于商家自身意愿。因此，我真的认为加密货币非常适合智能体支付，在这方面前景光明。事实上，目前正在探索的两个最大或最流行的代理支付标准——Coinbase 和基于稳定币通道的 Stripe MPP——实际上都在使用加密货币，这并不令人意外。

<details><summary>Original English</summary>
So if you for example compare uh crypto with like credit cards, PayPal or PayPal microp payments or you know bank debit um it's much cheaper like you just can't like use uh use these traditional payment methods for small agent transaction. It just doesn't make economical sense. And also uh uh the traditional payment methods uh they also have chargebacks. Like everybody who's selling online understands that uh you have to count that like some people will just abuse your service and then ask for money back and it's just like you know sort of uh way of life for for for online businesses. But you can't do that in the in the agentic uh world because there's like infinite number of agents and uh they would just like you know steal all your money effectively or you know take your service for free. So uh on crypto uh there is no chargebacks uh only like refunds if but these are optional by by the merchants. So I think really like crypto is well suited for agent payments and uh it is like bright future u for that and actually two oh sorry two biggest players uh uh or two most popular agentic payment standards currently exploring coinbase and stripe uh mpp uh on uh stable coin pass are actually like using crypto right and uh it's not surprising
</details>

### 实际采用情况与漏斗分析

那么让我们来看看这两个系统在现实世界中的采用情况。这些数据来自 x402scan 和 MPPscan 网站，它们主要监测区块链上的交易。你可以看到在过去 30 天内，x402 上的支付交易量仅有 100 万美元左右，而 MPP 上仅有大约 1500 美元。这基本微不足道，可以说是几乎不存在。

<details><summary>Original English</summary>
so let's have a look at the adoption of uh these two systems in real world. This is from the X42 scan and MPPP scan websites u which basically monitors uh the transactions on blockchain. And you can see in the last 30 days uh in the last 30 days uh on X42 there was just only like $1 million payment volume and on MPP only like $1.5,000. I mean that's basically nothing. It's uh it's like non-existent.
</details>

那么问题来了：大家都去哪儿了？为什么没有人使用它？自智能体支付出现至今已经有一年多、将近一年半的时间了，但智能体依然没有在使用它。让我们尝试寻找这个问题的答案。首先，也许是服务供应不足？也许只是没有太多可供智能体自主购买的东西？

<details><summary>Original English</summary>
So the question is like where is everyone? Why is nobody using it? Like uh it's been more than uh like year and a half now uh when agent payments become a thing but like agents are still not using it. So let's try to u find answer to that question. So first maybe there's a low supply of services. Maybe there's just not not too many things to buy on you know for agents autonomously.
</details>

我认为情况并非如此。因为如果你查看这些代理支付目录，上面有大量的服务。而且我想说，仅仅是我们公司、Exa、Perplexity 以及 Firecrawl 都在上面，我们加在一起，每个月从智能体使用我们服务中所获得的收入远远超过 100 万美元。显而易见，智能体正在使用这些工具并为此支付了多得多的费用，但这是通过 API 密钥完成的，而不是通过自主发现和支付。所以问题一定出在需求端，对吧？很显然，智能体就是不感兴趣，它们没有在购买这些服务。因此，让我们尝试理解其中的原因。

<details><summary>Original English</summary>
Well, I don't think that's the case because if you look u at these like agentic payment directories like there's like plenty of services, you know, and I would say just like our company and Exa and Perplexity and Farcru are all there and u I would say we together make far more you know uh than million dollars per month uh from agent agents using our services right so clearly agents are using these tools pay much more for that uh but uh through API keys not uh through autonomous discovery and payment so it must be the demand right like uh so clearly the agents just are not interested they are not buying the services so let's try to understand why
</details>

好的，我认为分析这个问题的最佳方式是将代理支付视作一个漏斗。它始于需求：首先，你作为系统的构建者或智能体的创建者必须具备这种需求，比如觉得可以这样做；否则的话，你根本不会允许它发生，或者你根本不会去进行配置。接着你需要以某种方式去设置它；而一旦配置完成，智能体就需要某种途径来发现这些服务，并且……

<details><summary>Original English</summary>
okay and u I think the best way to do that is to look at the ag payments as a funnel so it starts with like need so first you as a outer of the system or creator of the agent need to have the need like okay uh because otherwise like you wouldn't allow it or you wouldn't set it up and then you need to like somehow set it up and once it's uh once it's done the agents need some way to discover the services and
</details>

<!-- chunk 2/3 -->

最终购买它们，对吧？而且我想说，在这个漏斗的每一个环节，我们都会遇到一些摩擦点，最终导致 Agent 在漏斗末端没有进行购买。

<details><summary>Original English</summary>
eventually buy them, right? And I would say at every step of this funnel, we have some friction points that ultimately like uh lead to the fact that like agents are not buying um at the end of the funnel.
</details>

那么我们来试着更详细地看一下。首先是需求。如今大多数人都在构建 Agent 系统，并且他们给它们提供访问服务的权限，但他们是通过固定的账号来实现的，或者说是那种事先注册好的账号，并且通过 API 密钥，对吧？所以就像……我不知道，比如你有一个 Agent，如果你需要让它访问网络数据，你就直接在 Apify 上注册一个账号，然后把 API 密钥放到你的云端；或者通过使用 MCP 来连接这些服务，然后你通过信用卡来支付这些服务的使用费用，对吧？这相当直接。每个人都能做到，对吧？

<details><summary>Original English</summary>
So let's try to look at it more in more detail. So first the need well most people are building agentic systems now uh and they give them access to services but they they they they do it through fixed uh accounts or like you know accounts with sign up uh they sign up before and through API keys right so you just like I don't know like you have an agent and if you need to give it access to web data uh you just uh create an account on aify and uh and then like put the API key into your cloud or you know through use use uh MCP to connect uh to the services and then so and then you pay uh for for the use of the services uh through your credit card, right? It's it's pretty straightforward. Everybody can do that, right?
</details>

所以，这真的不是说 Agent 支付在与 Visa 竞争。它们是在与 API 密钥竞争，因为那种方式就是更方便。那么，需要发生什么，才能让 Agent 或人类真正决定：好吧，我希望我的 Agent 不仅使用我之前给它预设的一套固定服务，而且我还希望我的 Agent 能在运行过程中发现新的服务，并自己去购买它们，对吧？

<details><summary>Original English</summary>
So it's it's really not like that like agentic payments are are competing with with Visa. It's uh they are competing with with API keys because it's just the more convenient way. So what needs to happen for for agents or people to really uh decide okay I want my agent not to use only fix set of services that I you know gave it before but uh uh I want my agent to also discover new services as as it goes uh and buy those on its own right
</details>

### 解锁 Agent 自主购买的前提条件

我认为这有几个先决条件。首先是更好的模型。我的意思是，随着模型变得越来越好，Agent 能够自主完成越来越长期的任务，你对它们的信任度也更高等等。所以这算是一种自然的发展演变，而且我认为随着时间的推移，这些模型——如果它们现在还没做到的话——在金钱方面也将赢得信任。我认为你可以开始比如先给它们每个任务 5 美元，然后是 50 美元，如果知道行得通，你就可以给到 500 美元。而且我想说，人们现在就已经在信任 Agent、让它们访问自己的系统了，甚至经常赋予写权限，而这有时会导致灾难或者数据泄露。我认为对于金钱来说其实更安全。我的意思是，如果你损失了 50 美元，这挺让人沮丧的，但这并不是一场灾难；除非有人泄露了你的电子邮件，那可要糟糕得多。所以这已经在逐步演进了，模型变得更好，它们也会获得人们更多的信任来做这件事情，去购买服务。

<details><summary>Original English</summary>
so I think there's uh few prerequisites to that first is better models uh I mean as the models are getting better the agents can complete every longer task autonomously you you trust them more and so on. So this is sort of a natural progression of things and I think over time uh the models like if if if they don't have it already will will deserve a trust also with money and I think like you can start like giving them I don't know $5 for job and then 50 and if you know it works like you can do 500 and I would say people already trust agents with uh access to their systems uh even right access quite often and sometimes uh it leads to disasters or you know leakage of data think with money it's it's safer I mean like if you lose $50 it's it's sad but it's not a disaster like you Unless well somebody leaks your email that's much worse. So I this is already progressing like models are getting better and they will have more trust uh from people to to to do that uh to uh purchase services.
</details>

但我认为重大的解锁契机将随着常驻（always-on）Agent 的到来而出现。现在我们看到比如 MetaMuse、OpenAI Operator 等等。我认为个人常驻 Agent 正在变成现实，而如果你想让这些 Agent 真正去执行某些任务，你最终会给它们预算。所以我认为我们也在走向这一阶段。

<details><summary>Original English</summary>
But I think big unlocker will come with always on agents now we saw with like uh metamuse you know open eye dot and so on. I think the the personal always on agents are becoming a real thing and uh if you want those agents to actually do something like you will give them budget eventually. So I think we're we're getting to this uh stage as well.
</details>

而且我认为还会带来很大帮助的是 Token 补贴时代的终结。现在在 Claude 上每月花 100 美元，如果你拉满的话，我不知道，你能买到价值相当于比如 14,000 美元的 Token。这太疯狂了，因为这样一来 Agent 就完全没有任何动力去寻找现有的服务，因为它们可以从头自己构建任何东西，反正毫无成本。但我认为在某个时刻这将会结束，也许随着 OpenAI 和 Anthropic 的 IPO，突然之间 Agent 会觉得：好吧，对我来说购买一项服务可能比从头构建它或者想办法去把它搞定更划算。所以我认为这种解锁已经在发生了。

<details><summary>Original English</summary>
And I think what will also help a lot is uh end of the era of token sub subsidies. Now on $100 per month on claude you can buy I don't know like $14,000 worth of tokens if you max it out. Uh this is crazy because then the agents have no incentives whatsoever uh to you know to look for existing services because they can build anything from from scratch because it costs nothing. But I think at some point this will end maybe with open AAI and not entropics IPO and suddenly the agents will be okay maybe it's more economical for me to buy a service rather than build it from scratch or figure out way to to get it done. So I think this is like uh the unlock is already happening
</details>

### 配置、信任与购买

然后漏斗中的第二步是配置。好的，我现在想使用它，那我该怎么做？我认为对很多人来说，加密货币仍然相当晦涩难懂。你知道的，有许多不同的行话，有各种不同的词汇和术语，而且我想说大多数人确实没有尝试过自己去设置加密钱包。也许他们会用 Coinbase 进行交易，但真正给自己的 Agent 一个加密钱包，这需要他们付出一些额外的工作，而且比起用信用卡支付服务费来说稍微更困难一些，因为每个人都已经有信用卡了。但我认为这很快也会得到解决，要么是通过更好的用户体验——我认为 Agent 支付工具每个月都在变得更好——而且我认为如果这些主流的 Agent 平台，比如 Claude、ChatGPT 或者这些个人 Agent，如果它们本身直接集成了加密支付，那将是一个巨大的突破。基本上你只需要直接使用来自 Claude 的主账户额度，然后说：嘿，你可以使用 50 美元来购买服务。我认为这会是一个重大的解锁，而且我认为这迟早会到来。

<details><summary>Original English</summary>
and then second u step in a in a in a in a funnel is setup. Okay, I want to use it now. How how do I do it? I think for a lot of people like crypto is still fairly opaque. you know there's like a lot of different like lingo there's like different words and you know uh terms and like I would say like most people uh really haven't tried to set up crypto wallet themselves uh maybe they use like Coinbase for trading but really like give their Asian crypto wallet you know it's it's you know it needs like you know some extra work from them and it's it's it's a little more difficult you know than I don't know using a credit card to pay for a service because everybody has credit cards already but I think uh this this this will also like uh soon be solved you either with better better user experience. I think the agentic payment tooling is getting better like every month really and I think big unlock would come if these major agentic payment agentic platforms you know like cloud or or JGPT or you know these uh personal agents if they actually integrate uh crypto payments directly itself right so basically you would just like use your main account credits from cloth and say like hey you can use $50 to p purchase services I think this would be like big unlock and I think it's coming sooner than later
</details>

好了，那么 Agent 拥有了一个加密钱包或者设置好了 Agent 支付系统，它可以购买服务了。那么现在最大的问题是：它在哪里可以找到它能够信任的服务？信任很重要，因为如果你要从某个地方、某个人那里购买服务，你需要确保他们会交付他们所承诺的服务，他们会按照他们所说的价格来交付，对吧？如果你没有这种信任，你就不会与任何人进行交易。

<details><summary>Original English</summary>
all right so then the agent has a crypto wallet or or you know agentic payment system set up and it can buy services. So the big question is now where where can it find the services it can trust and trust is important because if you're buying a service from something from someone you need to make sure okay that they will deliver the service they promise they will do they will deliver for the price they they they say they will right and if you don't this trust you wouldn't transact with anyone
</details>

从历史上看，人们是如何建立这种信任的呢？起初，他们开始与自己认识的人交易，对吧？他们交换服务，后来用金钱交易，但这都是与他们认识的人。所以他们知道自己可以信任，对方会卖给他们好东西；或者他们会信任某个认识并且信任的人所推荐的人，对吧？这有点像你问你的朋友：“能给我推荐一个好的理发师吗？”你的朋友就会说：“你可以去找这位。”然后你就可以信任那个人，接下来一切都很顺利。随着时间的推移，随着世界变得越来越大，人们开始利用值得信赖的中间人来告诉你谁是优质卖家、谁不是，对吧？比如各种市场或者城镇广场，如果有人在城镇广场上摆摊售卖，你或许就可以信任他们是公道的。我们也有各种评价机制，以及各种消费者保护机构等等。所以基本上，正是这些要素赋予了经济体系信任，让你能够从陌生人那里购买服务，因为有你可以参考的信号。

<details><summary>Original English</summary>
and like historically how are how are people building this trust you know like first like they did started to transact with people they they they knew right so they like you know exchange services and later with money but it was is someone they knew. So they they knew they can trust and they will sell them good thing or they will trust with someone uh someone else like they knew and trusted like recommended them right. So it's like kind of like if you ask oh um can you recommend me a good barber like uh to your friend uh you'll be like okay uh you can use this one you know and then you can trust that person and then it's all great and over time you know as the world like you know got got bigger uh people started to use like a trusted like middleman uh to to tell you who who is like good seller and who is not right so for example like different marketplaces or town squares where you know if there was some someone like selling in a town you know on the square you could probably trust okay they are you know they are fair and you know we have like different sort of like reviews and uh and you know different agencies uh for consumer protection and so on you know so basically these elements give trust to the to the to the economy that you can buy services you know from strangers because there is like signals you can use
</details>

但在 Agent 的世界里，还没有类似的东西。你怎么能知道某个随意网址上的这个 Agent 或服务——它声称“我有能提供完美天气数据的 API”——你能信任它吗？这挺难的。但我认为同样的原则也会适用：要么依靠网络信任，比如“我知道这些服务是不错的”，基本上这是一个你可以使用的资源池；要么基本上使用受信任的目录和市场。我们已经可以看到这种情况正在发生，例如 Claude 拥有一个连接器目录，对吧？这有点像是经过验证的连接器，Anthropic 实际上对其审核得相当仔细。想要进入那里很难，因此他们已经为这些工具的目录提供了这样一层信任。GPT 也是一样，他们有应用；Apify 也是一个市场。所以基本上存在一个受信任的中间人，告诉你：这是一项你可以信任的服务，你可以使用它，对吧？所以我认为这也已经在发生了。

<details><summary>Original English</summary>
but in the aging world there is nothing like that how can you know that like this agent or service on on some random URL that that's claims oh I have API for I don't know the perfect weather data can you trust it well it's kind of hard but I think the same principle will apply you know so either like network network or trust that like oh I know these services uh are good you know so basically this is a pool you can use or uh basically using trusted directories and marketplaces and we can already see is happening for example uh cloth uh has uh has a directory of connectors right it's like sort of like verified connectors that you know that actually like entropic like reviews pretty carefully. It's a it's hard to get there you know uh so they provide already this layer of trust for the directory of these tools and same forg they have apps and uh you know appi is a marketplace as well so basically there's a trusted middleman that tells you okay this is a service you can trust you know and you can you can use it right so I think this is already happening as well
</details>

再次说明，如果这些大型 Agent 提供商能够开箱即用地支持支付，那将是一个巨大的突破，整个生态我认为就会真正启动起来。最后一步就是购买，对吧？传统的这些 Agent 支付系统只支持这种超简单的用例，那就是每次 API 调用收取固定价格。但在这个世界里，这远远不够。能按固定价格购买的东西只有那么多，也许像天气预报之类的，但要完成一项真正的工作，你实际上……

<details><summary>Original English</summary>
and um uh again like a big unlock would be like if these like big agent providers uh enabled like payments out of the box you know suddenly I think the the the the whole thing would really start and last is to buy right and u traditional these agentic payments systems they only supported this uh super simple uh use case and it was like fixed price per API call but in this world this is not sufficient you know there's only so so many things you can buy for fixed price maybe like the weather forecast but to complete a real job you actually
</details>

<!-- chunk 3/3 -->

需要……比如……呃，按使用量付费（pay-per-use）。我是说，比如要启动某个计算任务，或者某个本身使用大语言模型的代理任务，对吧？所以你需要比如浮动定价。而且，幸运的是，就在今年早些时候，x402 添加了这个选项，叫做批结算（batch settlement），而 MPP 添加了会话（sessions）。这些支付方案的目标，就是让代理也能够处理这种按使用量计费的方式。

<details><summary>Original English</summary>need like uh payer use I mean like for example to to launch some comput job or some agentic job that uses LLM itself right and uh and uh so you need like variable pricing uh and uh thankfully just just uh uh earlier this year X42 added this option it's called batch settlement and u MPP added sessions uh and the goal of these uh payment schemes is to enable uh agents you know to uh handle also this like paper use billing</details>

### x402 按使用量付费的实现与流程

那么我们快速看一下 x402 是如何实现按使用量付费的，因为我认为这很好地展示了早期采用者为了让它跑通所经历的过程。先快速看一下 x402 是怎么工作的：首先，你发送 API 请求，收到一个 402 错误返回，带有一些……抱歉，带有 payment required 头信息。你创建一个签名，带着一些钱重新发送请求。然后服务器与协助方（facilitator，比如 Coinbase）进行验证。一切正常后，你再去执行工作——呃，我们稍后会看这个——接着结算交易。协助方 Coinbase 将交易提交到区块链，交易确认后，你会从协助方收到结算完成（settled）的响应。然后你就知道钱确实已经转账了，就可以去执行任务了，对吧。

<details><summary>Original English</summary>so let's have a quick look on the how how uh x4 to implements payer use because I think this is sort of a nice illustration what the early adopters have go through you know to to to uh make it work. So just a quick look how X42 works like first like you know you send API request you get like 402 error back uh with some with some payment uh signature sorry payment required header you create a signature repeat request with some money uh then the server uh verifies it with the facilitator which might be Coinbase for example it's all good and then you do work there well we'll see uh then you settle the transaction uh Coinbase the facilitator submits the transaction to to blockchain and transaction is cor confirmed you get like settled response back from the from the from the facilitator and then you know actually the money has been transferred and you can do the job right.</details>

所以这里的风险在于：如果你稍微早一点执行任务，然后钱却没有到账，你可能会赔钱。这取决于你的服务。有时你只想确保在真正提供服务之前收费，特别是如果存在不可忽视的成本，比如一些计算资源等等；然后你收到支付响应。这一切都很好，但这真的只适用于非常简单的情景。处理按使用量付费要困难得多。

<details><summary>Original English</summary>So the risk is like if you do the job a little earlier and then uh the money just doesn't arrive like you can lose money. So it depends on your service. Sometimes uh you just want to make sure that that you charge before you actually do the service if there's like non-trivial cost maybe like you know some some compute and so on and then you get payment response. So this is all good uh but this is like really just for the simple simple scenarios but handling payer use was pretty much uh like a little more challenging you know.</details>

### 支付方案的演进与双花问题

首先在 5 月，x402 推出了 exact（精确）支付方案，这是针对固定定价的第一个方案。然后他们许诺会推出 up to（最高限额）支付方案，基本上允许这种浮动成本。他们在今年早些时候发布了它，但遗憾的是，它并不能完全适用于我们的用例，我很快会讲到这一点。最后，他们在 2026 年引入了批结算（base setments）。

<details><summary>Original English</summary>So first in May uh export to launched exact payment scheme. This was the first scheme for the fix fixed pricing and then they released promise that we will release up to payment scheme basically allowing like this variable cost. They released it earlier this year but unfortunately it didn't really work exactly for our use case. I'll get to that very quickly. And then finally uh they introduced base setments uh in 2026.</details>

up to 支付方案的问题在于，尽管它允许你收取浮动费用，但没有任何机制阻止买方代理进行双重支付，因为交易是在较晚的时候才在区块链上结算。所以基本上 up to 对于按使用量付费的用例并不是真正管用，这有点令人沮丧。我们通过使用 exact 和退款来绕过这个问题：基本上我们先预收比如 10 美元，然后假设消耗了 2 美元，一旦工作完成，我们就退还剩余部分。但这又意味着代理需要信任卖家，这又回到了最初的观点：有时这很困难，而且需要两次区块链交易，这意味着更多的手续费等等，所以这并不理想。

<details><summary>Original English</summary>So the problem with up to payment scheme was that even though like it allowed you to to charge rather variable cost there was not nothing preventing the buyer the agent to spend those money twice you know because the transaction was only like settled on blockchain uh later. So basically up to wasn't really useful for for uh for pay-per- use case which was a bit of a bummer. So we work around that by using exact and refund. So basically we charge like sort of like I don't know like $10 up front and then you know let's say consumed $2 and and once u once the work was done we refunded the rest but then again that means that the agents need to trust uh the seller which again goes back to the original point that it's it's it's difficult sometimes so and it has to blockchain transaction so that means like more fees and so on. So this wasn't really ideal.</details>

### 批结算与总结展望

最终，批结算（bet settlement）支付方案解决了这个问题。我们最近才加上它，我想是在上周。我没有时间详细讲解，但它利用密码学魔法在区块链上把资金类似托管起来，然后你可以在之后针对微交易进行扣款。

最后总结：我认为代理支付漏斗现在正在真正建立起来，很快代理经济就会迎来真正的交易量和真正开启。我认为现在是个非常好的时机，去弄清楚如何在这个新世界中出售你的服务，因为实现起来可能比你想象的要困难一点；如果你等得太久，也许会赶不上这趟车。就这些，非常感谢大家。

<details><summary>Original English</summary>So finally the bet settlement payment scheme uh solved this issue. We added it just recently I think last week. Uh I do not have time to go through the detail but uh it uses cryptomagic to kind of like escrow the money on blockchain and then like you can like charge it like you know uh for microtransactions later and final remarks. Uh so I think the agent payments funnel is really being enabled right now and uh soon uh it will really like start like a real volumes on on the on the and the real start of the agent economy and I think it's really good time now to uh figure how you can sell your services uh in this new world because the implementation might be a little more difficult than you think and if you too long if you wait too long maybe uh you will miss the train and that's all. Thank you so much.</details>