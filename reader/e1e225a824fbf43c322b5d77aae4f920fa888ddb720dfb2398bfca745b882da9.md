---
author: AI Engineer
date: '2026-06-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KLSuFPj2ld0
speaker: AI Engineer
tags:
  - autonomous-economy
  - payment-infrastructure
  - machine-payments
  - api-design
  - risk-management
title: 为自主经济构建护城河：将发现的非决定论与支付的决定论分离
summary: 探讨了AI代理作为经济参与者时面临的不可靠点击与交易风险，提出在发现阶段拥抱非决定论，在结账阶段必须转向结构化的API交互。通过共享支付代币和机器支付协议建立安全可验证的代理支付基础设施。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Steve Kaliski
companies_orgs:
  - Stripe
  - OpenAI
  - Tempo
products_models:
  - Stripe Press
media_books: []
status: evergreen
---
### 发现与交易的二元法则：非决定论与决定论的分野

**自主经济**（Autonomous Economy: 由 AI 代理主导或深度参与的自动化经济活动）的崛起，意味着 AI 代理已经成为了实质上的经济参与者。在日常调用模型或编写代码时，其实质就是消耗计算代币或引发真实的财务开销。但要将这种模式扩展到更广泛的法币体系和商业互动中，我们需要解决核心的风险架构问题。

这里有一个至关重要的底层认知：**发现与探索受益于非决定论，而凭证、支付和结账必须要求绝对的决定论。** **大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）能够通过分析世界海量信息来为你灵活推荐代码、产品或服务，这得益于其概率性和非决定论本质。然而，在执行真实的资金转移时，必须要求精确的确定性。将“我应该寻找什么”的模糊性与“我该如何交易”的严谨性彻底隔离开来，是构建下一代支付系统的核心。

如果沿用旧思路，让代理像人类一样通过模拟点击去操作浏览器页面，将会面临灾难性的风险，这主要体现在四个层面：
* **错误的地点**：代理极易被钓鱼网站欺骗，难以在复杂的 DOM 树中验证当前域名的真实性。
* **错误的商品**：在非结构化的网页中游荡时，代理不仅可能买错颜色，甚至可能因为元素识别错误而买下价格高出十倍的同名商品。
* **错误的金额**：受汇率、税费漂移等因素影响，或者仅仅是文本解析错误，代理提取出的“价格”往往并非购物车最终计算出的实际扣款金额。
* **错误的凭证**：将原始信用卡直接硬编码或粘贴给代理，一旦代理出错，将会带来无底线的损失；同时，对于代理而言，跨越不同支付方式（如加密货币或区域性支付工具）的阻力也极大。

<details>
<summary>Original English Source</summary>
Just want to thank everyone for being here. Um, I'm from Stripe and today I'm going to talk about building safe payment infrastructure for the autonomous economy or how we can let robots spend money and how businesses can receive money from robots. So just about me, I'm a principal software engineer at Stripe. Spent my first four years leading our issuing team, so that's our product that lets developers create physical and virtual credit cards that historically would be for humans and increasingly for robots. In the last two years, I've been exploring how to let robots spend money and how Stripe businesses can adapt to that new kind of buyer.

And if I just want to take away, if you stop listening for the rest of the presentation, discovery and exploration benefit from non-determinism, right? So the amazing thing about LLMs is huge corporate of information, the world's information can predict and recommend code or products or businesses for you. But credentials, payments, and checkout require determinism. So not just benefit from it, but require it. So that's sort of isolation of how do I find things or what should I do from how am I going to transact is sort of the critical separation.

So we're going to talk about agents as economic actors, all the bad things that can happen, the solutions that that Stripe and our partners have worked together on to fix those, and then a little bit of what's next. So again, maybe another takeaway, agents are already economic actors, right? They have their own currency and tokens. So as you are in cloud code or codex or any other kind of application, you were in effect spending money, right? It might be proxied through the subscription you have or converted from the tokens that are being inputted or outputted turning into dollars, but in effect we're already letting them spend, right? Just not with any business but the LM uh provider that they're working with. So, how do we enable other currencies and other spend patterns and other payment methods and other business interactions is our is our main question. So, um we probably we're going to zoom through this cuz all we talked about today is agents, I imagine. So, uh agents produce text. Sometimes they need to read or write data or interact with third parties. They do so using tools, and sometimes those tools require money.

So, how do we safely enable this? Um again, we all know this, but uh crudely, an agent is just calling LM and calling tools. They're spending both of them. Um and the tools in particular we're going to talk about are search, credential management, and payment. It's the magic, but it's also the risk. So, uh what are the main problems? Um I can buy from the wrong place. I can buy the wrong thing. I can spend the wrong amount. I can use the wrong credential.

So, the base approach uh in sort of the open class style, let's just let the robot operate a human operate Well, hopefully not operate a human, but uh concerning slip, uh hopefully it doesn't come true. Let the robot just operate the browser like a human. Um So, wrong place. Well, first, how does an agent certify it's in the right place or domain? Um how do I know that, you know, maybe the the website looks a lot like, you know, amazon.com, but is, you know, amazon. whatever and and is a fake one. Um the wrong thing. Uh you could stumble through a site looking for a purple T-shirt, and you could maybe, less concerningly, buy an orange T-shirt, but you could also, you know, uh buy something that's 10 times more expensive. The wrong amount. Um you know, as we know, at least for me, I've seen totally different prices here than back at home. Prices can drift. There's miscalculations, different currencies, taxes, and so on. Like, the number you your robot may extract from the page may not actually be the amount of money that you want to spend. And of course, wrong credential. Um you could paste your credit card, it could go the wrong place. Um, but, you know, as as here, there are other different payment methods that are hard or if not impossible for an agent to relay. So, we want to be able to solve all four of those things. And again, the basic approach of taking a card number, bad. Browsing a site can be finicky, filling forms, clicking pay, it's all slow, um, hard to observe outcomes. And, you know, this isn't unique to payments, right? It's the same as operating any web app or anything that has a monetary risk. And that's why MSPs and uh, APIs exist.
</details>

### 从表层模拟到 API 驱动：构建受限的信用边界

要消除这种致命的“非决定论摩擦”，我们需要全面拥抱 **API驱动（API-driven）** 架构。人类使用仪表盘，而机器人应当使用代码与可验证的结构化身份进行交互。

我们提供的第一个基石是 **共享支付代币**（Shared Payment Tokens: 一种通过 API 生成，携带智能合约限制逻辑的次级支付凭证）。传统的做法是传递一张信用卡的完整卡号，这意味着你只能祈祷代理不会出错，因为你无法跨平台、跨账户地去限制它。而共享支付代币允许你先授权一个高额度主卡，然后为代理派生出一把“受限的虚拟钥匙”。

这把钥匙内部编码了极其严格的强制性规则：你可以指定它只能在特定的商家（例如某个内部测试环境）进行结算，并严格限制它在 30 天内只能消费最多 25 美元。在执行层面，即便是代理被钓鱼网站诱骗，或者传递了 50 美元的错误结算请求，**Stripe** 作为底层网关也会直接拦截并阻断这笔超额扣款。此外，系统不会对商户完全隐藏支付背景，商户依然能收到卡片品牌、卡片尾号等特征信息，以此保持他们现存的风控和反欺诈模型的正常运转，在降低爆炸半径的同时兼顾了商业信任。

<details>
<summary>Original English Source</summary>
So, in Stripe parlance, the the left-hand side dashboard is for a human, and the right-hand side, robots prefer code. So, the ideal approach is you know, something where we can bind to a merchant. We can enforce spend policies. It can be API-driven and thus programmatic. And you can have verifiable identities.

So, I'm going to talk about three different things that Stripe and our partners have built together around credentials, payment flows, and checkout to illustrate how we're trying to solve all of those problems.

So, first I want to talk about shared payment tokens. And the idea here is that, um, you know, first, not all payment methods are, you know, universal like credit cards. Um, some are expressed in different ways. Um, but there's also no way to enforce spend limits or controls when you just hand a card number to someone else, right? You're going to trust them that they charge the amount that you parsed out of the page or whatnot. And what we built with shared payment tokens is this idea that an agent collect a payment credential and it can share it with the seller, you know, across hundreds of different payment method types. And it can encode sort of like a mandate or smart contract, the limitations of that credential to be used by a particular seller.

So, you know, we'll do a demo in a second, but I can apply usage limits to specific currencies, to amounts, for time, and a particular seller. So, even if I've been, you know, duped by a domain or you know, haven't parsed the amount correctly, I can still apply what I think is right in terms of the amount and the particular seller that I'm targeting. So again, scope to seller, it's enforced by Stripe, works across payment methods, and it's auditable. So, I'm going to jump into a quick demo just to show you how that works.

So, let's look at um kind of a common Stripe integration. So, I have my seller Stripe account and I want to charge uh $50. So, I normally I would create a payment intent and on line 39 I'd collect that payment method myself and it would run and that's all great. Um but now instead of collecting the payment method on my website, an agent is collecting a payment method that it may have already received from its human operator or through the subscription that backs the harness or whatever it may be. So, we're going to introduce a second Stripe account. And this is the agent Stripe account. And it's going to provision a shared payment token. Let's say it collect had collected a Visa card. And it's going to say that this Visa card, which has a much higher credit limit, is only going to work for $25 and it's only going to work for the next 30 days and it's scoped to this particular seller, illustratively, my internal test account.

So, we're going to go ahead and we're going to create that credential. And instead of the seller using a payment method that they've collected, they're going to receive a token that's been granted to them and try to run the payment.

Cool. So, the first thing we see is that we created that new shared payment token, which applies to that Visa card, it's active, it has that $25 limit, and it's going to expire in 30 days. Now, what's important as part of this also is we don't want the seller to be fully hidden from what's happening. So, in the same way that they would have otherwise collected a card and knew the brand and knew the last four and so on, um we still send that information over. So, the the brand and the last four, the credit type, they can use all these inputs in their existing risk analysis. So, an important part here, too, is that we're not trying to do something secret from the seller. We still want to provide the relevant information to the seller so that they can still apply their exact their previous uh risk systems um so that, you know, they they can accept payment. Um, but what we'll see is we actually had a failure here. So, the request amount, which was $50, is greater than the amount that was uh mandated. So, again, we like collected a credential, we shared it, we applied a limit, we trusted the seller, the seller tried to do more, and now Stripe enforced a limitation. So, uh again, like this would work across any payment method type, and, you know, now that we you know, can lower the cost, we'll see that uh this actually goes through. Yep, that payment went through. So, now we're able to securely send a credential, apply limits, make sure there's a minimized blast radius, um and still allow the seller to process payments as they normally would.
</details>

### 机器间微观协议：重构动态结账流

确立了凭证边界后，更大的挑战在于机器之间该如何协商并执行动态复杂的交易。在这一体系中，代理与服务器的互动被归纳为两套核心协议。

首先，针对调用第三方工具时产生的即时性开销，我们与 **Tempo** 网络合作推出了 **机器支付协议**（Machine Payments Protocol: 一种通过HTTP状态响应来通知并处理机器间资金结算的标准化方案）。当代理发起 HTTP 请求触碰到收费端点时，服务器无需展示报错页面，而是直接返回标准的 `402 Payment Required` 状态码，并附带经过编码的负载信息，精准说明“交易对象、所需支付的金额以及底层结算网络（例如 Tempo 区块链上的 USDC）”。代理获取该负载后，出示被授权的凭证即可完成这种细颗粒度（哪怕只有一美分）的无感微交易。

在应对更厚重的传统电商结账场景时，单纯的微支付依然不够。商品由于税金计算、物流费用以及数量调整，存在巨大的动态变量。为了阻止代理去抓取复杂的 HTML DOM 获取信息，我们与 **OpenAI** 联合发布了 **Agent to Commerce Protocol (ACP)**。这是一个通过标准化的 API 对象定义全网购物车工作流的协议。以 **Stripe Press** 书店为例，商品目录和属性完全被映射为 JSON 格式。每次代理修改商品数量或切换收货地址时，商户服务器都会回传经过重算后的确定性状态（The Latest State），从而将一场充满迷雾的页面操作转化为严格的结构化数据博弈。

通过这种“非决定论发现 + 决定论校验”的设计，我们为代理和商业实体之间建立了一条极度安全的双向高速公路。如果企业依旧只提供为人眼视觉优化的 Web 界面，必然会被挡在自主经济爆发的门外；而转向对代理友好的确定性架构，才是企业捕获这一波新流量红利的终极解法。

<details>
<summary>Original English Source</summary>
Now, um that covers credential sharing, but there's two more parts to this. This how do we actually associate payment to a product, and then how do we do checkout? So, uh the second thing we built uh we worked with our friends at Tempo was what we call the machine payments protocol. So, back to that original point around tool calls, um well, tool calls are just sort of HP requests that agents can make. Um, and HP requests um should be able to be paid for, right? So, one way is you pass in an API key, but sometimes those interactions with tools can be ephemeral. So, we want to be able to communicate the need to pay um in those HP requests by returning a 402 status code, and then supply that credential that we showed earlier um so that we can actually get a good back.

So, um we've covered uh Uh, how do we get credentials, how do we know to pay for them and associate with the actual product we're buying? So, again, um closing that window of of improved determinism. Um So, maximize determinism. Let's do demo. So, now if we jump over here, I'm going to start a server. This server's a regular sort of uh web server. It has protected endpoints that now require payment. So, let's say my robot is calling one of these endpoints to try to execute a tool. Make a curl request to it. It fails. Tells us that we need to pay. It gives us some uh encoded payload that explains what we're buying and who we're paying for and the what we're paying for and the mechanism to pay for it. Um and I can go ahead and uh pay for it now. So, now we get some extra information back because we're speaking that protocol. We can see that it's going to cost a penny um this to this particular recipient. Um it'll be path USD on the tempo blockchain. And I can go ahead and approve it. So, now that goes through, get our success, and then we can see a transaction landed on the blockchain. So, uh we're, you know, able to create credentials that have limited use. Now we can be uh told by a seller how they want money and have it be associated with the actual re- resource I'm requesting. And now I can send them funds.

Um but the last part is um let's just jump back in. It's like we're not always buying API calls, right? And sometimes the details uh of the purchase matter quite a bit, right? The tax amount, maybe there's that, there's uh restrictions about the amount of things I could buy. All the things that a typical e-commerce site is trying to convey. And to that earlier point around, you know, the the robot, you know, stumbling around a checkout page, there are a lot of details that we want to be able to relay back to the agent and ultimately back to the human buyer to make sure that the thing we're buying is is the thing we think we're buying, right? We want to minimize disputes and chargebacks and so on. And if we have this proxy layer of the agent in between, we run the risk of incorrectly relaying those details. So, what we built with Open AI being the agent to commerce protocol is a standard set of APIs and objects that can explain how checkouts work across the web.

So, similar to the last thing we showed where the seller kind of conveys the need to pay, we establish a back and forth between agent, a seller, and their PSP, where every single time the agent wants to create a checkout or update the quantity or pick a shipping amount, the seller can relay sort of like a tool called relay back the latest state, respond to that request, and ultimately result in payment. So, we can sort of illustrate how this works with a real business. Let's spin up a server here. So, Stripe operates something called Stripe Press. It's our store of books. This is obviously a very cool, human-friendly way to look at it, but our equivalency um is the robot-friendly way of looking at it. So, um the ACP protocol or ACP covers a few things. How do we express a product catalog, right? So, instead of the robot stumbling around and having to click on links and figure out what to buy, we can express our products just in JSON with images and descriptions and pricing. And then the robot can pick one of those and initiate a checkout.

So, uh Uh, we can pull up a familiar UI, maybe I'm asking for recommendations about AI books. And on the right-hand side we'll see the requests that the agent makes. So, it tells a little bit about the buyer, the line items and quantity it wants. And then the seller can relay back basically the state of the cart. So, instead of the robot trying to, you know, pull information, you know, out of a UI like this, it has structured data that I can refer to. So, uh, the line items, the base price of each, applicable tax, the different fulfillment options, and so on. So, nothing surprising here, but, you know, our goal is to sort of establish that determinism, right? Where like we've segued from discovery, where maybe we were doing some web crawling, now we've transitioned to just purely programmatic back and forth. So, you know, as I change payment methods or I change shipping, and ultimately pay, those back and forth happen. Payments goes through using something like a shared payment token or otherwise to relay those credentials. Let me check again. Yep.

So, you know, at the end we we have API-driven commerce flows that are flexible to different payment methods, whether they're crypto or cards or any of the other hundreds of payments that exist. And critically, the seller remains in control. They continue to have the relationship that they expected to have with customer, but also receive the signals um and risk data that they need to safely interact with agents. And sort of the, you know, goes without saying most of us have already done this with with our products, but, you know, we want to make our products agent-friendly. Um, and if we only expose you web UIs or or or applications like that, um we increase the likelihood of non, you know, the non-determinism interacting with our businesses. Instead, we should make them age friend agent-friendly um to maximize the deterministic flows that agents have with our businesses. So, leveraging things like shared payment tokens or wallets or other technologies to then manage those credentials safely um is then important for agents so that they're able to uh yeah, not accidentally spend a gazillion dollars on a card.

Um so TLDR, discovery we should keep with non-determinism that's perfect. Payments and checkout and credentials we want to shift towards exclusively deterministic. Um so non-deterministic planner and constraints with verifiable parties and structured negotiation results in a small radius of risk and hopefully safe uh payments between agents and businesses. So that's all I got. Thank you.

I have 2 minutes and 9 seconds if people have questions.

>> You mentioned blockchain.
>> Yeah.
>> What is this hosted by Temple or is it Stripe or do they own their own separate data?
>> Yeah, so um you know, Stripe supports a number of different uh protocols and and a uh variety of networks including Base and Tempo. The transaction data uh innately lives on those chains and then Stripe replicates the sort of product view of that data in our own system.
>> Yep. But why factor
>> This guy.
>> Um the shared payment tokens are really cool. Uh in terms of say like recurring budgets and payments, like I'm thinking of you know, I want to give Open Claw $25 a week to use with like a particular model. How how does that uh kind of factor in?
>> Yeah, so you touched on two points the sort of the subscription thing and then sort of more enduring policies. Um on the subscription side um in the same way you give a credit card to a business and you permit it to spend $25 or whatever on a on a periodic basis but it still uses the same credential. Uh we have a similar idea there as well. Sort of similar to in OAuth access and refresh flow where you can sort of like request uh subsequent usage. Um and then on the another part about like uh uh sort of more balanced budgets the sort of equivalency can work here where you just pick a higher number. We still scope it to individual sellers, but you could just create infinite of them.
>> Um so I'm wondering is Stripe projects just effectively a wrapper of these primitives that you've discussed during the session?
>> Uh yes. Thank you for that plug. I did not have time to include that, but yes, Stripe projects is built on shared payment tokens. And then the mannerism in which seller or SAS business can express their products as And then the point touched on the recurring part is how the monthly part would work.
>> Thank you.
>> You mentioned that you have started this 2 years ago. I'm wondering about the the number of such payments done and the volume If you can share something
>> We don't have public stats on any of that, but I think in general we're very encouraged by it and we're really excited about trying to support more businesses in accepting that type of payment. Well, I'm at zero now, so thank you everyone. Appreciate it.
</details>