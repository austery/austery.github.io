---
author: a16z
date: '2026-10-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=q8cb1XL9sXA
speaker: a16z
tags:
  - agentic-commerce
  - payment-credential
  - tokenization
  - digital-wallet
  - pci-compliance
title: Agentic Commerce爆发：当AI代理获得支付凭据与钱包武器
summary: a16z合伙人Alex Rampel与VGS首席执行官Terry Angelos深入探讨了AI代理商业的崛起。随着AI从旁观者演变为掌握支付凭据的行动者，围绕数字凭据托管、网络令牌化、多处理器路由与钱包战争展开了全新行业博弈。对话深度剖析了代理商业中的授权委托、欺诈责任划分、商家阻断及凭据基础设施的演进。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Very Good Security
  - Andreessen Horowitz
  - Visa
  - Mastercard
  - Stripe
products_models: []
media_books: []
status: evergreen
---
### 开篇前瞻：AI代理迈向行动者时代

**特里·安杰洛斯 (Terry Angelos)**: 在过去的三个月里，我们见证了一次巨大的飞跃——**AI代理 (AI Agents)** 从我所谓的“旁观者”跃升为真正的“行动者”。它们之所以能成为行动者，是因为它们实际上拥有了手和脚，而这双手和脚正是**支付凭据 (Payment Credentials)**。

亚马逊最近屏蔽了 **Muse**，这背后的原因有很多。面对**代理商业 (Agentic Commerce)**，你既可以采取敌对排斥的态度，也可以选择高度接纳。随着 Muse 和 Instinct 等产品的兴起，一旦它们获得了支付凭据的访问权限，其实用价值便呈指数级攀升。因此，我们实际上开启了一场我称之为**钱包战争 (Wallet Wars)** 的角逐，每一个数字钱包现在都在争先恐后地与 AI 代理进行对接。对于正在收听本期播客的每一位听众，我几乎可以保证，你们都有一张凭据存储在 **VGS (Very Good Security)** 的金库中。

<details>
<summary>Original English</summary>

**Terry Angelos**: In the last 3 months, we've had this huge leap from agents being what I would call spectators to agents being actors because they effectively have arms and legs, which are payment credentials. Amazon recently blocked Muse and there are many reasons for this. You can either be antagonistic to agent commerce or you can be highly receptive. What's happened with the rise of, you know, Muse and Instinct is once they have access to payment credentials, their utility increases. So, we sort of have kicked off what I kind of call the wallet wars where every wallet is now rushing to connect to the agents. Everybody who's listening to this podcast, I almost guarantee you have a credential that's stored at VGS.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 全球最大的在线商户、顶尖的新型数字银行，以及最领先的前沿 AI 实验室，都在使用 VGS 来保障其支付凭据的安全。这确实是一个令人瞩目的护城河与领先地位。那么，你认为 VGS 未来将走向何方？

<details>
<summary>Original English</summary>

**Alex Rampel**: The largest online merchants, the largest neo banks, and the largest frontier labs all use VGS to secure payment credentials. It's a really formidable position to be in. Where do you think VGS is going to go?

</details>

### 从 TrialPay 到 VGS：安全与隐私的溯源

**亚历克斯·兰佩尔 (Alex Rampel)**: 大家好，我是 a16z（**Andreessen Horowitz**）的合伙人 Alex Rampel。今天非常高兴能邀请到 Terry Angelos 与我坐在一起。之所以如此激动，是因为 Terry 和我在 2006 年共同创立了一家名为 **TrialPay** 的公司。那已经是整整 20 年前的事了。

<details>
<summary>Original English</summary>

**Alex Rampel**: Hi everyone. I'm Alex Rampel, partner at Andreessen Horowitz and I'm here joined by Terry Angelos and I'm very excited about being joined by Terry because Terry and I started a company called TrialPay in 2006. Um long long time ago, 20 years ago.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 20 年前，Alex 看起来和现在可大不相同。

<details>
<summary>Original English</summary>

**Terry Angelos**: 20 years ago. Alex looked very different.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 是啊，而你看起来倒是一点没变。所以我想你是在贬损我，而我却在夸奖你，希望大家可别理解反了。

不过今天真正酷的事情在于，我在 a16z 最早主导投资的项目之一就是一家名为 VGS 的公司，全称代表 **Very Good Security**。有些人可能没意识到这其实是一个双关语或行业幽默，因为密码学历史上最著名的公司/协议之一叫作 **PGP (Pretty Good Privacy)**，意为“相当好的隐私”。显然，它不仅仅是“相当好”，而是一种令人惊叹的、无法破解的隐私安全保障，因为在大数质因数分解极其困难的数学原理支撑下，“相当好”其实就是坚不可摧。所以 Very Good Security 这个名字正是致敬并呼应了这个渊源。我主导了对这家公司的早期投资，并在董事会任职多年。当 VGS 的创始团队准备交出日常运营接力棒、寻找下一任首席执行官时，我想到的第一个人就是 Terry。于是我联系了 Terry，并成功说服他接任 CEO。

<details>
<summary>Original English</summary>

**Alex Rampel**: Yes. Uh you look the same. So I think you're insulting me and I'm complimenting you and hopefully not the other way around. But today, this is the really cool part. One of my first investments here was a company called VGS, which stands for Very Good Security. And some people might not get that that's actually a pun or a joke because one of the most famous cryptography companies was called PGP, which is Pretty Good Privacy. And obviously, it's very good privacy. It's not just pretty good privacy. It's incredible privacy. It's unbreakable privacy because that's how you know it's very hard to factor very large composite numbers into their primes. And Pretty Good Privacy is actually very good. So that was kind of the original name for Very Good Security. So I led that investment and served on the board for a long time. When the founders were ready to transition to the next phase, the first person I thought of was Terry. I reached out and convinced him to take the helm.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 没错，这是一段极其有趣且令人难忘的历程。回看我们 20 年前在 TrialPay 的经历，当时我们必须自己建立凭据金库。那是一段漫长而复杂的摸索过程，我们必须在本地自建基础设施来保管信用卡数据。后来，我去掌管了 **Visa** 的全球金融科技业务，见证了现代金融科技与支付基础设施在过去十年中的彻底爆发。因此，接手 VGS 并思考它的未来，感觉就像是职业生涯的一次完美闭环。

<details>
<summary>Original English</summary>

**Terry Angelos**: Yeah. It's been a very fun and incredible journey. If you look back to our experience 20 years ago at TrialPay, we had to build our own credential vault. That was a long, complex slog where we had to store credit card data on-premise. Later, I went on to run Visa's global fintech business and saw the explosion of modern fintech and payment infrastructure over the last decade. So taking the helm at VGS and thinking about what comes next feels like a complete full circle.

</details>

### 解构凭据：主账号、网络令牌与解耦路由

**亚历克斯·兰佩尔 (Alex Rampel)**: 或许我们应该深入剖析一下究竟什么是“支付凭据”。在支付行业内部，“凭据”听起来很高级，但究竟代表着什么？在 TrialPay 那个时代，我们主要处理的就是 **PAN (Primary Account Number)**。

<details>
<summary>Original English</summary>

**Alex Rampel**: But maybe we should dig into what a credential is. I mean, credential is a fancy way of saying... in our world, back at TrialPay, we were dealing with PANs.

</details>

**特里·安杰洛斯 (Terry Angelos)**: PAN 即主账号（Primary Account Number），也就是我们日常所说的信用卡卡号。

<details>
<summary>Original English</summary>

**Terry Angelos**: A PAN is a primary account number. A PAN is a primary account number, credit card number.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 那就是印在卡片上的 16 位数字。过去，我们会将这 16 位卡号加密存入金库；每当需要向用户收费扣款时，我们就在内部解密，并将其传递给当年的收单处理机构，比如 Chase Paymentech。

但今天，情况完全改变了。现代支付流程不再直接存储并传递这 16 位物理卡号，而是向发卡卡组织——Visa、Mastercard、American Express 或 Discover——发起请求：“请为我签发一个该卡片的全新版本，且该版本在域级别与我的商户域名严格绑定 (**Domain-Bound**）。”这种方式安全性极高，因为即使系统发生泄露，黑客拿到的这一串数字也只能在当前特定的商户域名下生效，在其他任何地方毫无价值。随后商户再将这个**网络令牌 (Network Token)** 发送给支付处理机构。

VGS 作为一家专业的基础设施公司，代表商户集中托管所有这些底层凭据，并负责从卡组织处批量获取网络令牌。这是当前凭据流转的核心机制，也是我们每天处理的核心业务。由于与各大卡网络进行深度交互极其复杂，而且大型商户往往对接多个不同的支付处理机构，这就带来了巨大的工程挑战。Alex，我这里正好有一个问题想考考你：对于一家年交易总额（GMV）超过 10 亿美元的大型商户，其后端通常会同时接入多少家支付处理机构？

<details>
<summary>Original English</summary>

**Terry Angelos**: It's the 16-digit number that you have on your card. We would encrypt it and vault it and then when it came time to charge someone, we might unencrypt it and give it to I think Chase Paymentech back in those days. Today, that doesn't happen. Today, instead, what happens is rather than store that 16-digit card number and use that, you actually go to the network that issued it—Visa, Mastercard, Amex, Discover—and you say, "I would like another version of this card that's actually domain-bound just to my merchant domain," which is safer because if there's ever a problem, the only number that I have only works on my merchant domain and I am going to use this when I send it to Chase Paymentech. So VGS as a company vaults all these credentials on behalf of the merchant, also gets all of the network tokens which is the primary way that these credentials are passed to the payment processor and to the network, and that's what we do today. And so because of that complexity of interacting with the card networks and doing this across multiple processors... actually here's a question for you Alex. If you're a merchant with over a billion dollars in GMV, how many payment processors do you have on the back end?

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 这得看情况。业内确实有少数巨头只用一家，但绝大多数成熟的大型企业都不会这么做。这就切中了 VGS 的核心应用场景：与其被死死绑定在单一的支付处理机构（如单一捆绑的 **Stripe**、**Adyen** 或 **Braintree**），你更希望将底层凭据存储与支付收单处理进行彻底解耦，从而能够自由挑选和动态路由最优的支付处理通道。

此外，当你有统一的基础设施来存储凭据时，还能解决凭据失效的问题。以我自己最近遇到的真实案例为例：Capital One 收购了 Discover 网络，随后我手头原本享受 1.5% 返现的 Capital One Visa 卡，就被银行自动升级置换成了 Discover 卡。

<details>
<summary>Original English</summary>

**Alex Rampel**: Well, it depends. There are plenty that just have one, but you are better... I mean, this goes to the use case of VGS, which is rather than being locked into one payment processor, you'd rather unbundle that and you'd rather be able to pick and choose which payment processor you use. But also if you have a kind of a shared infrastructure that is storing credentials, what if one credential goes bad? Like what if my... I just had a Capital One card. Great example. Capital One bought Discover card or Discover Network, and then my fancy Capital One cashback rewards 1.5% Visa card, it became a Discover card.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 结果，每周我都会收到来自各个商户悲伤的邮件通知：“很抱歉，我们无法处理您的信用卡扣款。”为什么他们无法扣款？因为原先旧的卡号已经注销作废了。尽管我与 Capital One 之间的信用关系依然正常存续，但我拿到了一组完全不同的新卡号。

<details>
<summary>Original English</summary>

**Alex Rampel**: And every week I get notifications from very sad merchants: "We are unable to process your card." Why are they unable to process my card? Because that old card number doesn't exist anymore even though I still have a relationship with Capital One. I just got a new card number from them.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 确实如此。跨网络迁移更为复杂，单个商户不可能凭空知晓“旧 Visa 卡号已经自动变成了新 Discover 卡号”。

<details>
<summary>Original English</summary>

**Terry Angelos**: Yeah, granted it's a little bit complicated. It's on a new network. Merchants can't just say, "Oh, we know that this card became that card." One merchant cannot do that.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 但一个大型的集中式凭据金库却能够做到。各大卡组织（如 Visa、Mastercard 以及 Discover）本身都提供了**账户更新器 (Account Updater)** 机制。商户面对海量卡号时，每年会有相当高比例的卡片自然过期，这个数字大概是多少，每年 10%？

<details>
<summary>Original English</summary>

**Alex Rampel**: But a large vault can do that. And then as you know, the actual networks themselves like Visa and Mastercard and Discover, they have these account updating tools. So you could say, "Hey, I'm a merchant. I have all of these card numbers." And I think what is it every year, like 10% of cards expire?

</details>

**特里·安杰洛斯 (Terry Angelos)**: 远不止于此，每年实际上有将近三分之一（约 33%）的卡片发生变更。从纯数学计算来看，因为大多数信用卡的有效期是四年，每年自然到期的卡片就有 25%；再加上 5% 到 8% 因欺诈补发、银行并购（比如 Capital One 收购 Discover）、卡损换卡等原因更替。

顺便回答刚才那个问题：年交易额超过 10 亿美元的商户，后端平均会接入 3 到 5 家支付处理机构。

<details>
<summary>Original English</summary>

**Terry Angelos**: Yeah. So about a third of all cards get turned over every single year. Mathematically, it's about 25% because it's a four-year expiration, and another 5% due to Capital One buying Discover, or fraud, or something else. Back to that question, by the way: for a merchant of about a billion dollars, it's about three to five processors that that merchant will have.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 商户并非强制要接多家，但接入多家是行业最佳实践。因为不同的收单通道拥有不同的手续费率、不同的批准率（Approval Rates），并在不同国家与地区拥有不同的本地结算优势。用计算机科学的术语来说，你需要对支付流量进行分片（Sharding）。如果把全部流量押注在单一通道上，容灾和商业议价能力都会大打折扣。但要想做到多通道路由，前提是你必须能够安全合规地将真实的支付凭据分发给你挑选的指定通道。

<details>
<summary>Original English</summary>

**Alex Rampel**: They don't have to, but they should. That is the average that we see. There's a reason for them to do that: different costs, different approval rates, different regions—you want to shard. In computer science terms, if you just say "I use the same processor every single time," that's just not as good of an idea as having multiple processors. But in order to do that, you have to be able to securely send the card number to the processor you've chosen.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 没错。一旦引入多家处理机构，凭据保管与卡号更新的工作量就会随处理商数量成倍增加。如果你作为商户持有 1 亿张用户卡片，难道要在 Chase 存 1 亿张、在 Stripe 存 1 亿张、在 Braintree 再存 1 亿张，并且让每个孤立的金库分别去卡组织跑更新吗？

VGS 的本质定位就是充当中立且独立的第三方凭据金库基础设施。我们代表商户统一进行安全托管与动态更新；当需要扣款时，商户可以随时从 VGS 生成一个网络令牌，安全地经由 Stripe 或 Chase 完成结算。对于你刚才吐槽的 Capital One 换卡困扰，如果该商户接入了 VGS，凭借全自动的生命周期更新协议，这种扣款失败完全可以被底层静默修复。

<details>
<summary>Original English</summary>

**Terry Angelos**: That's right. And in fact, once you have multiple processors, then the job of vaulting and getting updates is multiplied by the number of processors. So maybe I have 100 million cards as a merchant, but I have to store 100 million with Chase and 100 million with Stripe and 100 million with Braintree. And each of those vaults have to be updated at their networks. What VGS does is serve as an independent vault-neutral infrastructure on behalf of the merchants for the vaulting and the updates, such that the merchant can then send a Visa token via Stripe. Back to your annoying Capital One issue: if you're a VGS merchant, that should not happen. There are mechanisms when Capital One switches from Visa to Discover to get those updates, and certainly when there's fraud. That's the role VGS is playing.

</details>

### 从 PCI 合规重担到 Agentic Commerce 爆发

**亚历克斯·兰佩尔 (Alex Rampel)**: 这非常清晰地阐述了 VGS 的底层业务逻辑。不仅如此，支付行业还有一套严苛的 **PCI-DSS (Payment Card Industry Data Security Standard)** 标准。在座的听众如果有人研读过该规范，应该知道那是一本超过 100 页的繁文缛节，列满了商户在接触和存储银行卡数据时必须强制遵守的技术与流程规范。任何银行和卡组织都强制要求 PCI 合规，违反合规的企业根本无法处理支付业务。

而 VGS 的巨大价值在于它能将 PCI 合规性直接完全剥离出商户的责任范围（**Out of Scope**）。商户只需专注做自己的业务，由 VGS 的隔离环境代为承担所有安全审查。

多年来这一直是一门极其稳健的商业模式。然而就在过去几个月里，**Agentic Commerce（AI代理商业）** 突然爆发，整个世界骤然生变。大批顶尖前沿的 AI 公司紛紛选择接入 VGS。其核心逻辑在于：如果我在聊天工具里对 AI 说：“母亲节到了，帮我给妻子买一束花”，我并不愿意直接将我的物理信用卡号交给某个初创的聊天应用；而 AI 公司本身也极其抗拒亲自存储这些敏感数据，更缺乏与遍布全球的各类独立商户直接传递支付凭据的能力。

<details>
<summary>Original English</summary>

**Alex Rampel**: Exactly. Hopefully everybody now has a good understanding of what VGS does. Out of nowhere, while this was already a great business, this whole thing called Agentic Commerce showed up. How does the world change? A lot of AI companies have decided to work with VGS. The reason is: if I go into my chat tool and say, "Hey, I'd like to buy flowers for my wife for Mother's Day. She'll be mad if I don't and happy if I do. Please buy them." I don't want to give my credit card number to a chat app, and they certainly don't want to store it. Even if they did store it, how do they communicate it to the merchant? The better option is a third party that already knows how to do this.

You take it out of scope. I don't know if most of our audience knows what PCI DSS is—the Payment Card Industry Data Security Standard. It's over 100 pages of rules you have to maintain to be PCI compliant, demanded by every bank. You cannot process or issue cards without it. VGS takes PCI compliance completely out of scope. You run your business, VGS handles the compliance. Which goes back to buying flowers via a chat app: VGS is uniquely positioned here as the trusted backend infrastructure.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 没错。正如我刚才所讲，最近三个月见证了 AI 代理从“旁观者”向“行动者”的突变。它们究竟如何替我采取行动？答案是：只要以安全受控的方式赋予它们支付凭据，代理就能从“给你推荐该买哪种花”，直接闭环跨越到“替你下单买下那束花”。

举个身边的亲身经历：就在昨天晚上，我和妻子一直在商量为我们 7 岁的儿子找一位钢琴老师。这非常繁琐，因为老师必须符合我们全家的作息时间，我儿子每周还有三天足球训练，而且我们要求老师能上门授课，这需要双方日程极其严密的匹配。之前我曾向传统的 ChatGPT 咨询过，它只是泛泛地列出了几点建议和搜索链接；但在昨晚，我吩咐了一个 AI 代理，它替我跑完了整个端到端的任务——它物色了多位人选，向我核对了几个关键偏好，自动校验了空闲日程，并直接完成了第一堂试听课的在线预订。

这种体验相比于把一堆琐事扔回给我自己处理，有着天壤之别。AI 代理之所以能在瞬间变得极具生产力，是因为支付凭据赋予了它们行动的“手和脚”。随着 **Muse**、**Instinct**、**Town** 等 AI 代理的崛起，一旦接通支付凭据，其实用性便呈指数级攀升。

这也彻底点燃了我所说的“钱包战争”——各大钱包系统都在争相将自己连入 AI 代理。作为 AI 代理，在选择接入的钱包时主要考量两个维度：第一，该钱包在消费端已经沉淀了多少绑卡用户；第二，该钱包覆盖了多少下游可消费的商户网络。

当前这一赛道上有几个核心巨头：
1. **Stripe Link**：约 3 亿消费者注册，覆盖约 100 万商户；
2. **Shopify Shop Pay**：消费者体量相仿，商户基数达 170 万家左右；
3. **PayPal**：坐拥超过 4 亿活跃账户，并覆盖了多达 3000 万家商户。

这些数字钱包正在加速与 AI 代理深度对接，以释放出惊人的实用生产力。

<details>
<summary>Original English</summary>

**Terry Angelos**: In the last 3 months we've had this huge leap from agents being spectators to agents being actors. How do they act on my behalf? Well, if you give them a payment credential in a safe way, I can go from recommending the flowers for your wife to buying the flowers for your wife.

I'll give you an example: just last night, my wife and I were talking about getting a piano teacher for our seven-year-old son. It's complicated because you have to know our schedule, he has soccer three days a week, and we want someone who can come to the house. We have to coordinate with the teacher's schedule. I asked ChatGPT about this a while ago and got some recommendations, but just last night I asked an agent, and it did the entire transaction task for me. It found a bunch of candidates, asked me a few questions, checked the schedules, and booked someone for the very first lesson. That is infinitely more useful than dumping yet another task on my doorstep.

Agents have become significantly more helpful because they effectively have arms and legs, which are payment credentials. With the rise of Muse, Instinct, Town, and other AI agents, once they have access to payment credentials, their utility increases. We sort of have kicked off what I call the wallet wars, where every wallet is now rushing to connect to the agents. As an agent, I want a wallet that has two things: the maximum number of consumers who already have stored credentials, and broad merchant reach. Right now, Stripe Link has about 300 million consumers and 1 million merchants; Shopify Shop Pay has a similar consumer scale with ~1.7 million merchants; and PayPal has over 400 million accounts and around 30 million merchants. These wallets are connecting to agents and providing massive utility.

</details>

### 钱包战争 2.0：从消费者收银台到代理分发枢纽

**亚历克斯·兰佩尔 (Alex Rampel)**: 这非常耐人寻味。“钱包战争”的概念在支付领域早已存在。你还记得我们当年的老东家 Visa 推出的产品吗？

<details>
<summary>Original English</summary>

**Alex Rampel**: So it's interesting though because wallet wars have been around for a while. Remember—not to speak ill of our old employer—remember V.me?

</details>

**特里·安杰洛斯 (Terry Angelos)**: 哈哈，没错，**V.me**，后来更名为 **Visa Checkout**。

<details>
<summary>Original English</summary>

**Terry Angelos**: Right, V.me. They changed the name to Visa Checkout. That's correct.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 当时在 TrialPay，我们研究过一个核心课题：如何将 Visa 卡推向“钱包首选位置（**Top of Wallet**）”。例如在 Uber 应用中，你可以绑定八张不同的信用卡，发卡行和卡组织为了争夺第一扣款顺位打破了头。

但在早期的数字钱包时代，当用户在电商网站看到“PayPal 支付”、“Google Checkout 支付”或“Masterpass 支付”等一系列并排按钮时，本质上是一场在消费者收银台前端争夺视觉点击的战争。对于大多数钱包而言，那是一场痛苦的零和博弈。

<details>
<summary>Original English</summary>

**Alex Rampel**: One of the things that we worked on at TrialPay was how does a Visa card become top of wallet. You can store eight different cards within Uber, and being top of wallet is everything. When digital wallets emerged, you had buttons like "Pay with PayPal," "Pay with Google Checkout"—remember Google Checkout launched back then?—and Masterpass. It was a battle for consumer checkout real estate.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 确实如此。回顾历史，钱包其实分为两大阵营：其一是**消费者钱包 (Consumer Wallets)**，比如你手机上的 Apple Pay、PayPal 或各家银行的应用；其二是**商户端凭据存储 (Merchant Vaults)**，比如 Uber、Amazon 或大型电商将卡号记录在自己系统内。

在上一代“钱包战争”中，发卡行和卡组织的核心追求是在消费者端占据主导地位（Top of Wallet）。然而在 AI 代理的全新语境下，“钱包”一词的内涵已经被深刻重构。许多人正在混淆“用户交互前端”与“底层凭据分发网络”的边界。当你在凌晨两点想要下单买花时，你根本不在乎屏幕上显示的是哪个花哨的钱包品牌，你只在乎代理是否能顺畅、安全、准确地将交易履约完成。

<details>
<summary>Original English</summary>

**Terry Angelos**: There are consumer wallets and then there are merchant-stored credentials. In the previous wallet wars, it was all about top of wallet for consumers. But in the context of agents, the word "wallet" is getting a bit overused and conflated. When it's 2 AM and you need flowers ordered, you don't care about a consumer button; you care about whether the agent can seamlessly execute the transaction with a secure credential.

</details>

### 从单人到多人：凭据托管、中间人与三方信任机制

**特里·安杰洛斯 (Terry Angelos)**: 仔细推敲代理商业的流转流程，你会发现其复杂性远超表象。传统电商的信任模型建立在买家与卖家之间的双边契约上。例如，你在沃尔玛买东西，如果商品出现问题，你联系信用卡银行：“我有一笔沃尔玛的消费存在争议。”

但如果中间引入了代理和第三方中介，情况就变了：银行看到的可能并不是沃尔玛的商户代码，而是一笔来自底层聚合器（例如 Stripe）的交易流水。持卡人、AI 代理服务商、结算通道与最终履约商户之间，形成了一条复杂的链条。

<details>
<summary>Original English</summary>

**Terry Angelos**: The word wallet is a bit overused. There's distinct architectures. In traditional commerce, if something goes wrong, you call your bank and dispute the Walmart charge. But if you introduce intermediaries and synthetic accounts, the bank might say, "We don't see a Walmart charge, we see a Stripe charge." This breaks the dispute and attribution model.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 这正是 Visa 和 Mastercard 这类卡组织之所以能够构筑千亿美元市值的核心护城河所在——**信任与拒付调解机制 (Dispute Adjudication)**。支付并不仅仅是转移资金，更关键的是当交易发生欺诈、未收到货、货物破损时，由一套中心化的规则引擎来判定最终损失由谁承担。

如果在一个交易闭环中引入了层层代理，而没有明确的凭据传递标准，整个追责链条就会彻底断裂。

<details>
<summary>Original English</summary>

**Alex Rampel**: That is the main reason why Visa and Mastercard have succeeded and become trillion-dollar networks. It's a trust mechanism. I pay you, you give me goods. What if you don't send the goods? What if they are broken? There is a central intermediary that helps adjudicate those complaints and enforce liability rules. That trust mechanism is vital.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 正是如此！因此正确的演进路径并非让代理变成一个虚拟发卡行或洗钱通道，而是建立**中立透明的凭据流动网络**。

想象一下理想的工作流：
1. 消费者将其银行卡安全地保存在一个受信任的金库中；
2. 消费者授权 AI 代理：“去沃尔玛帮我下单这款吸尘器”；
3. 金库为该代理生成一个受限的域绑定令牌（或直接将安全令牌递交给沃尔玛后端）；
4. 沃尔玛作为最终商户，使用自己的商户收单资格向卡组织发起清算扣款。

这样一来，账单上清晰地标明“沃尔玛消费”，沃尔玛承担发货履约责任，银行和卡组织的拒付体系完好无损，AI 代理没有触碰明文凭据，也不承担过桥的坏账风险。

更进一步，我们正在从**单人模式 (Single Player)** 走向**多人博弈 (Multiplayer)**。过去，你的信用卡可能最多只在几台个人设备上使用，或者偶尔借给配偶；而现在，你有五个不同的自主 AI 代理在后台并发运转——有的在监测低价机票，有的在帮你自动续订日用品，有的在处理公司费用报销。凭据的授权、并发扣款、额度管控与撤销，已从单人控制彻底转变为复杂的多代理协作系统。VGS 平台目前已经安全托管了超过 **100 亿个凭据**，正是为了支撑这种高并发、跨实体、跨代理的基础设施演进。

<details>
<summary>Original English</summary>

**Terry Angelos**: That is the right direction of travel: we hold the credential safely in the vault. We give a domain-bound credential safely to the agent; the agent passes it to Walmart, and then Walmart runs the transaction on their existing merchant ID. Walmart gets paid, the consumer gets the loyalty points, the fraud rules work, and the statement says "Walmart."

Furthermore, commerce is going from single-player to multiplayer. Today, you might share your card with your spouse for a few things. In an agentic world, you might have five different agents running concurrently—one booking travel, one restocking groceries, one managing SaaS subscriptions. A credential vault has to handle delegated, scoped permissions for multiple autonomous actors. VGS manages over 10 billion credentials today, positioning us to be the infrastructure that powers this transition from single-player to multiplayer commerce.

</details>

### 授权委托、欺诈与责任归属：谁来为幻觉买单？

**亚历克斯·兰佩尔 (Alex Rampel)**: 深入到规则与司法层面，这引发了一系列极难界定的法律与合规拷问。传统的支付欺诈判定建立在一个核心假设上：“持卡人是否亲自授权了这笔交易？”

但在代理商业中，情况变得扑朔迷离。我们可以将其拆解为三个致命问题：
1. **凭据合法性**：卡号和网络令牌在技术上绝对合法有效；
2. **委托范围认定**：用户确实授权了 AI 代理去采购某项商品，但如果 AI 代理理解偏了呢？
3. **心智与幻觉责任**：如果代理“喝醉了”（**产生幻觉**），原本让你买 100 美元的降噪耳机，它却下单了 10000 美元的发烧友音响，这究竟算不算欺诈？如果算欺诈，责任究竟由用户、AI 平台、商户还是发卡行承担？

<details>
<summary>Original English</summary>

**Alex Rampel**: This gets really complicated when you look at the operating rules. Traditionally, fraud questions boil down to: "Was this authorized by the cardholder?" But with agents, you have three distinct questions:
1. Is the card valid? Yes, the card is technically valid.
2. Did the person tell the agent to do it? Yes, there was delegated authority.
3. Was the agent of sound mind—did it hallucinate? What if it was "drunk" and bought the wrong thing or hallucinated an order? Who is liable when an autonomous agent makes a catastrophic mistake?

</details>

**特里·安杰洛斯 (Terry Angelos)**: 这触及了问题的核心——**委托授权 (Delegated Authority)** 的边界与归责。

回想一下移动应用内购（In-App Purchase）早期：小孩子拿着父母已绑卡的 iPad 玩游戏，在不知情的情况下疯狂点击，充值了 10,000 美元的虚拟钻石。当家长看到账单崩溃时，他们打电话给银行声称这是欺诈。

早期苹果和银行之间产生过激烈的拉扯与争端。最终各大机构达成了某种妥协：在一定金额门槛内，平台和银行设立争议处理流程；但同时在系统底层强制引入了更严格的二次生物识别确认（如 Face ID / 指纹验证）。

在 Agent 商业中，我们必然会看到类似的规则演进：卡组织和监管机构将要求建立明确的“授权凭证（Proof of Intent）”链条。例如，对于 50 美元以下的日用品复购，允许代理全自动静默扣款；但当单笔金额突破特定阈值，或者风险引擎检测到异常品类时，必须挂起事务，强制要求人类介入签署（Human-in-the-Loop）。如果 AI 平台无法提供结构化的用户意图授权证明，一旦发生拒付（Chargeback），责任与损失大概率将被直接穿透判定给 AI 平台本身。

<details>
<summary>Original English</summary>

**Terry Angelos**: It's this exact idea of delegated authority. Think back to early in-app purchases: a kid takes an iPad and buys $10,000 worth of virtual gems in a game. The parents see the bill and claim it's fraud. Merchants and banks had to deal with this constantly. Eventually, platforms introduced stricter biometrics and established clear liability thresholds.

With agents, we will see a similar evolution. Card networks and regulatory bodies will establish clear liability frameworks based on "proof of intent." For transactions under $50, you might grant autonomous execution; for larger transactions or unusual purchases, the protocol will require human-in-the-loop cryptographic confirmation. If an agent platform fails to demonstrate verifiable user intent, chargeback liability will inevitably fall back onto that platform.

</details>

### 高估与低估：Agent 商业的攻防博弈与阻断壁垒

**亚历克斯·兰佩尔 (Alex Rampel)**: 从投资人和战略家的视角来看，面对 Agentic Commerce 的浪潮，你认为目前行业中哪些趋势被过度高估（Overhyped）了，哪些反而被严重低估（Underhyped）了？

<details>
<summary>Original English</summary>

**Alex Rampel**: Well, on that note, what do you think is overhyped versus underhyped in agentic commerce right now?

</details>

**特里·安杰洛斯 (Terry Angelos)**: 我先谈谈被**过度高估**的方面：
我认为在未来两三年内，那种“人类什么都不管、彻底放飞由完全自主通用代理打理一切财务生活”的幻想被过度夸大了。人们不会轻易把不受限制的无限额度黑卡交给一个黑盒智能体。那种宣称“消费者交互界面（UI）将在 12 个月内彻底消失、所有人都只和一个终极 Agent 对话”的论调，严重脱离了商业现实。

而被**严重低估**的，则是：
AI 代理将以极其务实的方式为消费者省下真金白银。代理能够 7x24 小时不间断地进行跨全网比价、跟踪最优运费规则、自动套用优惠券折扣、并利用智能路由绕过各种隐形加价。

但与此同时，这必然会引爆一场剧烈的商业博弈。也就是我们在开篇提到的：商户究竟是拥抱代理，还是敌视并阻断代理？

举个经典例子：高端热门餐厅的订座。过去普通人很难抢到热门席位；当少数极客用机器人脚本自动预订时，他们获得了超额收益。但如果人人都配备了一个全天候不断轮询刷新 API 和前端的 AI 代理，整个餐厅的预订服务器会被海量并发瞬间打崩。

亚马逊最近封禁 Muse 等购物代理，也是完全相同的逻辑。许多平台不希望外部代理轻易抓取其排他性的价格数据，不希望代理剥离掉自己精心设计的站内广告推荐流，更不希望代理抢走其直面消费者的第一入口关系。

<details>
<summary>Original English</summary>

**Terry Angelos**: I'll start with what's overhyped: I don't think we're going to see completely unconstrained, fully autonomous agents handling every aspect of human financial life overnight. The narrative that consumer UI will vanish in 12 months and everyone will exclusively talk to one unified agent is massively overhyped.

What is underhyped is that agents are going to save consumers substantial amounts of money. Agents can monitor prices 24/7, optimize shipping, auto-apply coupons, and route transactions through the most economical paths.

However, this triggers an intense conflict: merchant receptivity versus antagonism. Take restaurant reservations: when a few people have bots, they get all the tables. But if everyone has an agent hitting the reservation system simultaneously, it collapses the merchant's infrastructure. Amazon recently blocking shopping agents like Muse is a prime example: platforms do not want automated agents scraping their proprietary inventory, stripping away their high-margin ad impressions, or disintermediating their direct relationship with the shopper.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 没错。有些商户或运营商会封禁已知的代理 IP 地址。这就好比电信巨头 Comcast 试图封禁网络爬虫，却发现最前沿的多模态模型（如 GPT-4o 等语音与视觉代理）其调用特征已经与真实人类行为高度趋同。当代理的行为完全模拟人类在网页上的点击、甚至通过语音直接致电人工客服时，单纯的技术封锁就变成了堂吉诃德式的防御。

更深层次的冲突在于**服务条款 (Terms of Service)** 的灰色地带。当一家自动化代理替你与商户客服周旋两小时退费时，如果商户要求“持卡人本人在场”，这种法律层面的摩擦该如何收场？

<details>
<summary>Original English</summary>

**Alex Rampel**: Right. Merchants recognize IP addresses and block automated agents. But as multimodal models like GPT-4o and autonomous browser agents behave indistinguishably from humans, blocking them becomes nearly impossible. The real battleground moves to the legal edge cases in the Terms of Service: what happens when an agent reads the fine print and negotiates with customer service on your behalf? When the merchant says, "Only the account holder can do this," how will that tension resolve?

</details>

**特里·安杰洛斯 (Terry Angelos)**: 这正是一个前沿的探索领域。商业最终会达成新的利益平衡点——如同当年的搜索引擎爬虫催生了 `robots.txt` 与开放的 SEO 协议一样，面对 AI 代理商业，未来的商户必然也会从被动防御走向制定标准化的机器可读商业协议（**Agent-Readable APIs**）。

<details>
<summary>Original English</summary>

**Terry Angelos**: That is an open frontier that the industry has yet to fully reconcile. Eventually, just like the early web created robots.txt and SEO protocols to negotiate with web crawlers, commerce platforms will transition from crude blocking to standardized, machine-readable APIs and programmatic commercial agreements for agents.

</details>

### VGS 的三代演进：网络时代与 Agentic 未来

**亚历克斯·兰佩尔 (Alex Rampel)**: 面对这些激荡的技术与商业变革，作为 CEO，你如何规划 VGS 在这一新范式下的定位与长期蓝图？

<details>
<summary>Original English</summary>

**Alex Rampel**: With all of these massive themes unfolding, where do you think VGS is headed in this new world?

</details>

**特里·安杰洛斯 (Terry Angelos)**: 我认为 VGS 的发展历程可以划分为彼此交叠的**三大纪元**：

1. **第一纪元：金库纪元 (The Vault Era)**
这是 VGS 的立足之本。我们为那些不想触碰明文凭据和 PCI 合规重担的公司提供极致安全的隔离金库。无论是大型独角兽还是金融科技初创，通过使用 VGS 的零数据泄漏架构，都可以零合规负担地上线核心业务。

2. **第二纪元：编排纪元 (The Orchestration Era)**
随着客户业务体量激增，他们开始接入 3 到 5 家不同的支付收单机构。VGS 演进成为跨卡网络与收单机构的智能调度与令牌化中枢，支持智能路由、自动化账户生命周期更新与网络令牌生成。

3. **第三纪元：网络纪元 (The Network Era)**
这正是我们当前全力投入的最高形态——充当连结消费者、金融钱包、自主 AI 代理与底层商户的**可信基础设施网络**。在这个时代，VGS 不仅是被动的金库，更是跨实体的可信凭据交换枢纽。无论是 OpenAI、Anthropic 驱动的前沿代理，还是 Stripe、Shopify、PayPal 驱动的钱包，亦或是全球最大的品牌商户，都可以通过 VGS 这套中立标准，安全、无缝、零摩擦地实现代理商业的价值互联。

<details>
<summary>Original English</summary>

**Terry Angelos**: I think there are three distinct, overlapping eras of VGS:

1. **The Vault Era**: This was the foundation. We provided an unbreakable, zero-data vault for companies that didn't want the liability and regulatory burden of PCI compliance. They could launch products without ever touching raw credit card numbers.
2. **The Orchestration Era**: As our customers grew and adopted multi-processor architectures, VGS evolved into an orchestration layer—managing network tokens, account updaters, and routing credentials across multiple payment processors.
3. **The Network Era**: This is where we are today. VGS is becoming the neutral credential network connecting consumers, digital wallets, autonomous AI agents, and merchants. In this era, VGS serves as the underlying trusted interchange that enables AI agents to transact safely and frictionlessly with any merchant, using any wallet, while preserving security, attribution, and trust.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: Terry，今天这番回顾与畅想真是让人心潮澎湃，仿佛又回到了我们 20 年前一起钻研支付底层架构的激情岁月。改天我们一定要把老朋友们都聚齐，重温当年的回忆。

<details>
<summary>Original English</summary>

**Alex Rampel**: Well Terry, this has been fun down memory lane. One of these days we should get the band back together and do a full retro.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 绝对赞成！我非常期待。

<details>
<summary>Original English</summary>

**Terry Angelos**: Yeah, I think we should redo it. That would be fantastic.

</details>

**亚历克斯·兰佩尔 (Alex Rampel)**: 好的，非常感谢大家收听本期对话，也非常感谢 Terry 的深度分享！

<details>
<summary>Original English</summary>

**Alex Rampel**: Yes, that's a great idea. All right, thank you very much everyone, and thank you Terry.

</details>

**特里·安杰洛斯 (Terry Angelos)**: 非常感谢邀请我，大家下次见！

<details>
<summary>Original English</summary>

**Terry Angelos**: Thank you for having me.

</details>