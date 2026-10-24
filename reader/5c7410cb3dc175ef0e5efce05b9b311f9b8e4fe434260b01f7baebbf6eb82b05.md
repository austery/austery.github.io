---
author: a16z
date: '2026-09-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=J3pegsM5drk
speaker: a16z
tags:
  - fintech-innovation
  - payment-infrastructure
  - buy-now-pay-later
  - fraud-detection
  - agentic-payments
title: 对话 Affirm 联合创始人：支付 UI 的演进、创业早期的至暗时刻与 Agentic 支付未来
summary: Affirm 联合创始人 Max Levchin（PayPal 联合创始人）与 Alex Rampell（a16z 合伙人）深度复盘支付领域的演进历程。对话涵盖信用卡交互设计的不可替代性、生物识别支付的兴衰、Affirm 从虚拟商品到床垫 DTC 与职业培训的分期拓展经历、PayPal 早期的欺诈攻防战，以及对 AI 时代 Agentic 购物与支付机制的前瞻洞察。
insight: ''
draft: true
series: ''
category: business-entrepreneurship
area: finance-wealth
project: []
people: []
companies_orgs:
  - Affirm
  - PayPal
products_models: []
media_books: []
status: evergreen
---
### 支付 UI 的极致与巨额长尾市场

**Alex Rampell**: 银行卡支付界面堪称人类有史以来创造的最极致的用户界面。从任何角度来看，它都是全球最大的市场，在支付领域中，几乎没有任何一个细分赛道的规模会低于上千亿美元。

<details>
<summary>Original English</summary>

**Alex Rampell**: The card payment interface is the singular best user interface ever created. It is the world's largest market by any stretch of imagination. And there are no niches in payments that are smaller than $100 billion.

</details>

**Max Levchin**: 当交易规模变得极其庞大时，费率数字往往会变得非常微小，这种反差很奇妙。虽然交易体量巨大，但支付领域中真正高利润率的收入机会往往集中在较小金额的交易场景中。

<details>
<summary>Original English</summary>

**Max Levchin**: Once you go really big, the numbers get small, which is strange. There's a lot of volume, but the large volume revenue opportunities in payments tend to be the smaller dollar amounts.

</details>

**Alex Rampell**: 永远存在利用另一种支付载体来满足基本需求的机会。但随着你要发送的总金额降低，便捷性便占据了绝对上风。有史以来最好的用户界面就是信用卡。不过，随着人工智能的到来，这一地位或许终于迎来了重新谈判的时刻。AI 已经就绪，只是目前你尚未完全信任让你的 Agent 去代办这些事务能达到你亲自操作的水平。

<details>
<summary>Original English</summary>

**Alex Rampell**: There's always an opportunity to use another form of payment delivery device to satisfy a basic need. Convenience just trumps as the total amount you're trying to send goes down. The best user interface ever created is the credit card. This may actually be finally up for renegotiation because AI is already there. It's just that you haven't yet trusted your agent to do as good a job as you would.

</details>

### EMV 芯片迁移与生物识别支付的现实

**Host**: 还有什么事情是让你们感到惊讶至今仍未发生的？

<details>
<summary>Original English</summary>

**Host**: There is something else that you're surprised has not happened yet.

</details>

**Max Levchin**: 我曾经参加过一个密码学相关的学术会议，在会上展示了一种全新的数字支付方案，结果几乎被嘘下台，因为那套方案显然不具备匿名性。而 **PayPal** 当时最大的创新恰恰在于：如果我们根本不在乎匿名性会怎样？

<details>
<summary>Original English</summary>

**Max Levchin**: I went to some cryptography related conference and presented a new idea in digital payments and was literally booed off stage because it was certainly not anonymous. And the big innovation of PayPal was what if we don't care about anonymity at all?

</details>

**Host**: 你们两位相识已久，不仅共同创立了公司，而且在更早之前就认识了。作为金融科技领域的先驱，你们思考这个赛道、审视当下并推演未来已经超过 20 年甚至 25 年以上了。我很想知道，从你们最早进入这个领域算起，经过了这么多年，在发生或未发生的事情中，最让你们感到意外的是什么？你们在 2000 年代初期曾预想这个行业会如何演变？Alex，不如你先开始？

<details>
<summary>Original English</summary>

**Host**: So you guys go way back having co-founded a firm and met well before then. You guys are pioneers in fintech. You've been thinking about the space, trying to make sense of the present, thinking about where the future is going for 20 plus years, 25 years, maybe even more. And I'm curious, given so much time has passed since you first got into the space, what has most surprised you about what has happened, what hasn't happened, what did you expect to happen in the early 2000s of how this space would play out? Maybe Alex, why don't you start?

</details>

**Alex Rampell**: 我认为是 **Apple Pay** 和 **Google Pay** 的崛起，以及它们渗透的深远程度。一般来说，改变消费者的习惯是非常困难的。这其实源于一系列奇特的偶然历史事件：当时发生了一场商户欺诈责任转移（Merchant Liability Shift），因为磁条卡太容易被伪造了，于是 Visa 和万事达卡等卡组织规定，如果商户不升级为支持芯片插卡的 EMV POS 终端，一旦发生伪造欺诈，责任将由商户自行承担。

<details>
<summary>Original English</summary>

**Alex Rampell**: I think the rise of Apple Pay and Google Pay and the extent to which they've really penetrated. Because it's very hard to change consumer behavior in general, and it was a bizarre set of accidents if you will. Where there is this merchant liability shift because magstripes were so easily cloned. Visa and Mastercard and the networks said if you don't get an EMV POS terminal that you can dip the card into, you the merchant are on the hook if somebody steals a bunch of card numbers and makes a fake card.

</details>

**Host**: Europay？

<details>
<summary>Original English</summary>

**Host**: Europe card?

</details>

**Alex Rampell**: Eurocard。

<details>
<summary>Original English</summary>

**Alex Rampell**: Euro card.

</details>

**Max Levchin**: 欧洲人总能在标准制定上有话语权，因为他们一贯如此。他们硬是把非接触芯片前置的插卡标准塞了进来。

<details>
<summary>Original English</summary>

**Max Levchin**: I don't know. The Europeans somehow got their say because they always do. They insert their not electronic...

</details>

**Alex Rampell**: 对，是 Europay、Mastercard 和 Visa 联合制定的 **EMV 标准**。所以对于全美所有的终端机来说，如果你不想承担盗刷欺诈责任——比如有人跑去 Best Buy 买电视然后拒付——商户就必须购买全新的终端设备。而碰巧的是，当时所有的全新终端硬件都默认内置了 NFC 芯片。如果单单为了支持 Apple Pay 去让全美数百万家商户更换硬件，这原本可能需要花费 20 年的时间，但因为那次责任转移，全美商户几乎在两到三年内全部换装了新机器。

当人们买到支持 Apple Pay 的 iPhone 时，走到哪里的收银台都能直接感应刷手机。这种硬件层面的巧合让移动支付得以迅速普及，但我依然感到惊讶的是，除了手机以外，几乎没有其他支付载体能够成功立足。

<details>
<summary>Original English</summary>

**Alex Rampell**: Yeah, it's Eurocard, Mastercard, Visa. So it was called the EMV switch. So all of these machines, if you did not want to be liable—like I could go to Best Buy, buy a TV and charge back—you had to buy a new machine. And it just so happened that all of the new hardware included NFC chips. If you had had to convince all these merchants to buy a new machine just for Apple Pay, it would have taken 20 years. But everybody got these machines over a 2 to 3-year period. When people had Apple Pay on their phones, they could just tap it. But I'm surprised that other form factors haven't really taken off.

</details>

**Host**: Max，你呢？你在很多年以前就畅想过货币与支付的未来形态。发生或没发生的哪些事情让你感到意外？

<details>
<summary>Original English</summary>

**Host**: How about you Max? You were dreaming about what the future of money would look like a long time ago. What has surprised you about what has happened or what hasn't happened?

</details>

**Max Levchin**: 的确。

<details>
<summary>Original English</summary>

**Max Levchin**: Yeah.

</details>

**Alex Rampell**: 有意思的是，当交易体量真正做到极大时，单笔的数字会变小。比如我在两家银行之间转账 1 亿美元，这笔交易在技术上可能只需花费几美分甚至几美元的固定成本，对支付处理机构来说利润并不高。真正丰厚的商业机会反而深藏在那些高频、小额的长尾交易中。

<details>
<summary>Original English</summary>

**Alex Rampell**: Although it's interesting like once you go really big, the numbers get small, which is strange, right? Like if I send a $100 million wire from Bank of America to JPMorgan Chase, it costs like $25. But the large volume revenue opportunities in payments tend to be the smaller dollar amounts.

</details>

**Max Levchin**: 我前阵子还在翻找我们两人最早的一封往来邮件，那是我们最初萌生出后来演变为 **Affirm** 的点子的时候。

<details>
<summary>Original English</summary>

**Max Levchin**: I was trying to find the original email between the two of us where we start mentioning what becomes Affirm eventually...

</details>

**Alex Rampell**: 哈哈，很有趣，我记得当时我还买下了 `paymesooner.com` 这个域名。

<details>
<summary>Original English</summary>

**Alex Rampell**: Well, and that's actually funny you mentioned, I bought the domain paymesooner.com.

</details>

**Max Levchin**: 当时大家觉得 Bill Me Later 是个好主意，但对商家来说 Pay Me Sooner（早点给我结款）或许是更好的诉求。

<details>
<summary>Original English</summary>

**Max Levchin**: As a result so it's like, "Ah, Bill Me Later was a good idea, Pay Me Sooner would be an even better idea."

</details>

**Alex Rampell**: 如今应付账款融资（AP Financing）和应收账款融资（AR Financing）领域都涌现出了一些非常健康稳健的企业。但在消费级大宗支付上，纯粹通道处理方很难赚到大钱。

<details>
<summary>Original English</summary>

**Alex Rampell**: There are some healthy businesses these days in both accounts payable financing and accounts receivable financing. But it's not a very profitable business for whoever processes raw volume.

</details>

**Max Levchin**: 是的。

<details>
<summary>Original English</summary>

**Max Levchin**: Yes.

</details>

**Host**: 还有什么是你们曾经设想过、但至今惊讶于它竟然没有普及的创新想法？

<details>
<summary>Original English</summary>

**Host**: What's another idea that you're surprised does not exist yet that you were thinking at some point?

</details>

**Max Levchin**: 亚马逊最近在 Whole Foods 停掉了刷手掌支付（Amazon One）。

<details>
<summary>Original English</summary>

**Max Levchin**: Amazon actually just discontinued the whole thumb payment at Whole Foods.

</details>

**Alex Rampell**: 那不是大拇指，是掌纹，刷整个手掌。

<details>
<summary>Original English</summary>

**Alex Rampell**: They actually... It's not a thumb payment, it's the palm. The palm, yeah.

</details>

**Max Levchin**: 我其实非常喜欢那个功能。每次出差住在酒店，我都会特地去旁边的 Whole Foods 买东西体验刷掌。

<details>
<summary>Original English</summary>

**Max Levchin**: I loved it. I would literally go to Whole Foods next to whatever hotel I'd be staying in.

</details>

**Alex Rampell**: 听到他们下线这个功能我也很遗憾。我以前也经常用。

<details>
<summary>Original English</summary>

**Alex Rampell**: I was sad that they got rid of it. I used to use it, too.

</details>

**Max Levchin**: 它实际上并没有比掏出手机更快，但确实很有未来感、很好玩。

<details>
<summary>Original English</summary>

**Max Levchin**: It's actually not even faster. It's just fun.

</details>

**Alex Rampell**: 确实，甚至可能比掏卡还慢一些。

<details>
<summary>Original English</summary>

**Alex Rampell**: I know. It's probably slower.

</details>

**Max Levchin**: 确实慢，把手悬在扫描仪上方，感觉就像是在让机器看手相算命，顺便买两串葡萄。

<details>
<summary>Original English</summary>

**Max Levchin**: It is slower. It's like tell me my fortune and these grapes.

</details>

**Alex Rampell**: 机器给你的算命结果永远只有一句话：“你欠我们钱”。

<details>
<summary>Original English</summary>

**Alex Rampell**: The fortune is: you owe me money. That is the only fortune that you ever get.

</details>

**Max Levchin**: 没错！这让我想起当年加密货币兴起的时候，许多项目宣称“密码学货币是未来，它解决了在街头买咖啡需要匿名结算的场景”。

<details>
<summary>Original English</summary>

**Max Levchin**: That's right. When sort of the crypto industry was becoming popular, or when some of the major projects launched...

</details>

**Alex Rampell**: 我通常对很多狂热潮流持观望态度，我不是大多数消费级新潮流的最早尝鲜者。

<details>
<summary>Original English</summary>

**Alex Rampell**: So I'm frequently late to trends. I'm not the world's earliest adopter of the majority of things.

</details>

**Host**: 我觉得你创建 PayPal 已经算非常早的先锋了。

<details>
<summary>Original English</summary>

**Host**: I feel like PayPal is pretty early, right?

</details>

**Max Levchin**: 某种程度上算吧。但为了让大家理解背景：当年很多人坚信“买咖啡的匿名支付是核心刚需”。可现实是，买咖啡恰恰是最不可能需要匿名支付的场景。当你早晨睡眼惺忪地去买咖啡时，你最在乎的是能否以最快的速度拿到咖啡，而不是隐匿自己的身份。

<details>
<summary>Original English</summary>

**Max Levchin**: Well, sort of. To give you full context for PayPal: buying coffee is not the most important metric because there's no reason to hide your identity when getting coffee in the morning. You just want maximum convenience and speed.

</details>

**Alex Rampell**: 只要金额足够小，便捷性就会完全压倒一切其他诉求。

<details>
<summary>Original English</summary>

**Alex Rampell**: There's always an opportunity to use another form of payment delivery device to satisfy a basic need. Convenience just trumps as the total amount you're trying to send goes down.

</details>

### Affirm 的诞生：从虚拟商品到“免费送花”的滑稽试验

**Host**: 能带我们重温一下 Affirm 最初创立时的故事吗？这个点子究竟是如何从你们的讨论中孵化出来的？

<details>
<summary>Original English</summary>

**Host**: I want you to take us both back down memory lane. What was the beginning of Affirm and how did that evolve?

</details>

**Alex Rampell**: 希望我们两人的回忆版本能对得上！

<details>
<summary>Original English</summary>

**Alex Rampell**: Well, hopefully our stories match.

</details>

**Max Levchin**: 哈哈，应该把我们分置在不同的房间里分别拷问。

<details>
<summary>Original English</summary>

**Max Levchin**: Yeah, we should put us in separate rooms for questions.

</details>

**Alex Rampell**: 谁会做这种事呢？但当时大家都在 **FarmVille** 里买虚拟金币，或者在社交游戏里买虚拟扑克筹码。

<details>
<summary>Original English</summary>

**Alex Rampell**: Who would do such a thing? But you know, you're buying coins in FarmVille or virtual poker chips.

</details>

**Max Levchin**: 当时我还在经营 HVF（Hard, Valuable, Fun）孵化器。放在今天，大家可能会用 ChatGPT 或 Gemini 来辅助编写业务计划，但那时全靠纯手工推演。

<details>
<summary>Original English</summary>

**Max Levchin**: Yes. And this wouldn't have worked today because now obviously I would have used Gemini or ChatGPT to write this.

</details>

**Alex Rampell**: 你把我的商业秘密都抖出来了！

<details>
<summary>Original English</summary>

**Alex Rampell**: You're revealing all my secrets.

</details>

**Max Levchin**: 哈哈，我们在旧金山的 Vic's 咖啡馆碰面，一边喝咖啡一边聊。我们当时观察到，在移动端和网页端，用户在结账页面输入 16 位信用卡卡号、过期时间和 CVV 码的摩擦力极高。在虚拟商品交易中，放弃率高达 70% 到 80%。

Alex 当时在做 TrialPay，他们的逻辑是让用户通过完成第三方任务（比如注册试用 Netflix）来免费获得游戏道具。而我们的想法更进一步：为什么不在结账时直接给用户提供基于身份信用的分期贷款？用户只需输入姓名、手机号等极少的信息，后台在几秒钟内完成风控授信，立刻放款，商户即时结款。

<details>
<summary>Original English</summary>

**Max Levchin**: Yes, exactly. Because I know how much you love Vic's. We had coffee there and that's where we discussed it. We were talking about checkout friction on mobile and web—entering 16-digit card numbers, expiration dates, and security codes was terrible. Drop-off rates were 70-80% for digital goods. Alex was running TrialPay, where users did alternate actions to get digital goods. Our thesis was: why not underwrite consumers on the fly with minimal identity inputs (name, phone, DOB), provide an instant installment loan in seconds, and pay the merchant immediately?

</details>

**Alex Rampell**: 当时 TrialPay 正处于准备出售给 PayPal 的谈判阶段，但 PayPal 在最后一刻退出了交易。我们手里有大量的商户关系和场景认知，于是我们决定直接验证分期支付（BNPL）模式。

<details>
<summary>Original English</summary>

**Alex Rampell**: The motivation was similar: TrialPay was in the throes of selling to PayPal, but then they left me at the altar. We had all these merchant relationships and insights, so we decided to test this installment lending model directly.

</details>

**Max Levchin**: 那段经历其实挺有意思的。

<details>
<summary>Original English</summary>

**Max Levchin**: Oh yeah, I don't find it a negative thing.

</details>

**Alex Rampell**: 我们开始找商户路演。我们找的第一批客户之一就是 **1-800-Flowers**。我们去和他们的高管吃早餐，当面推介我们的系统。

<details>
<summary>Original English</summary>

**Alex Rampell**: No, it was funny. We had this meeting with 1-800-Flowers. We went through the pitch over breakfast with their senior executives.

</details>

**Max Levchin**: 那次早餐会上发生了一件特别搞笑的事。那位主管听完我们的构想后，突然说：“等等，我们以前做过一模一样的事情！”

<details>
<summary>Original English</summary>

**Max Levchin**: Two colorful points from that breakfast: In the middle of it, the guy goes, "Oh yeah, we used to do exactly this!"

</details>

**Alex Rampell**: 后来我们被转交给了他们的具体业务负责人 Amit Shah（他现在也创办了一家很成功的创业公司）。

<details>
<summary>Original English</summary>

**Alex Rampell**: Then we got handed to Amit Shah, who actually now runs a successful startup.

</details>

**Max Levchin**: 对，Amit。

<details>
<summary>Original English</summary>

**Max Levchin**: Yes.

</details>

**Alex Rampell**: Amit 非常聪明但也非常务实毒舌。我用 Word 做了一个非常简陋的原型流程展示给他看，告诉他用户只需要点两下就能完成先买后付。

<details>
<summary>Original English</summary>

**Alex Rampell**: Amit took over. He was very excited, but I remember I came up with a mock flow in Microsoft Word showing how a customer could check out with two clicks.

</details>

**Max Levchin**: 那时你身边终于有了一个真正的财务金融背景员工。

<details>
<summary>Original English</summary>

**Max Levchin**: You had like a real finance employee.

</details>

**Alex Rampell**: Amit 听完后直接挑眉对我们说：“这不就是免费送花吗？因为消费者根本就不需要还钱给你们啊！”

<details>
<summary>Original English</summary>

**Alex Rampell**: I showed him this, and he was like, "Free flowers, right? Because they just don't have to pay you back."

</details>

**Max Levchin**: 真是极致的冷嘲热讽。

<details>
<summary>Original English</summary>

**Max Levchin**: So cynical.

</details>

**Alex Rampell**: 他原话就是：“对于买花的人来说这简直太划算了，相当于 100% 白嫖鲜花。”

<details>
<summary>Original English</summary>

**Alex Rampell**: He literally said, "Free flowers. This is a great deal, free flowers."

</details>

**Max Levchin**: 他虽然说话犀利，但极其敏锐。我们并没有被他的怀疑打退堂鼓，反而更加确信：只要风控算法能够准确识别欺诈与违约概率，这种极低摩擦的信贷体验能给商户带来难以置信的销售转化提升。

<details>
<summary>Original English</summary>

**Max Levchin**: This is generally a very smart but cynical guy. We were not going to be perturbed by some cynicism.

</details>

**Alex Rampell**: 当时公司最初注册的名字还叫 **Expedite Software Inc.**。

<details>
<summary>Original English</summary>

**Alex Rampell**: At the time, I think it was still called Expedite.

</details>

**Max Levchin**: 是的，我们在 Expedite 这个名字下运营了一小段时间，后来才正式更名为 Affirm。

<details>
<summary>Original English</summary>

**Max Levchin**: Yeah, it briefly bumped around as Expedite, and then we finally renamed it.

</details>

**Alex Rampell**: 注册主体全称叫 Expedite Software Inc.。

<details>
<summary>Original English</summary>

**Alex Rampell**: It was incorporated as Expedite Software Inc.

</details>

**Max Levchin**: 没记错的话正是这样。

<details>
<summary>Original English</summary>

**Max Levchin**: Yeah, I think that's right.

</details>

### 穿越沙漠：从睡衣、床垫狂潮到职业培训的真实洗礼

**Host**: 那么这个模式是如何演进的？Affirm 是在什么时候真正找到了 Product-Market Fit（产品市场契合点）？随后的商业模式又是如何扩展的？

<details>
<summary>Original English</summary>

**Host**: And so how did the idea evolve as you went from there? When did it start to really get product-market fit or how did the space play out?

</details>

**Max Levchin**: 每一家值得在事后大书特书的伟大创业公司，都经历过‘在沙漠中漫游 40 年’的至暗迷茫期。许多团队在这个阶段就因为绝望而放弃了。

我们最初主打游戏虚拟商品和低客单价电商，但发现小额虚拟商品的坏账率和利润率根本无法支撑借贷模型。直到我们遇到了一个关键转折点——高客单价垂直 DTC 电商。

其中一个最早的忠实客户是一家专门销售高档睡衣与生活方式产品的女性创业者。

<details>
<summary>Original English</summary>

**Max Levchin**: Every startup has the '40 years in the desert'—it's just a given if it's worth talking about ex-post. Some people just quit. We started with virtual goods and low AOV, but unit economics didn't make sense. Until we pivoted to high-AOV direct-to-consumer (DTC) merchants. One of our earliest champions was an entrepreneur selling luxury pajamas and apparel.

</details>

**Alex Rampell**: 对，我前不久还见过她。她当时是我们最强有力的拥护者。

<details>
<summary>Original English</summary>

**Alex Rampell**: Oh yeah, I just saw her. She's wonderful. And she was an early advocate for us.

</details>

**Max Levchin**: 因为接入 Affirm 后，她的业务发生了立竿见影的质变。

<details>
<summary>Original English</summary>

**Max Levchin**: Because her business literally transformed.

</details>

**Alex Rampell**: 我差点把她给忘了。

<details>
<summary>Original English</summary>

**Alex Rampell**: I forgot about her.

</details>

**Max Levchin**: 她经常会直接把后台销售数据截图发给我，兴奋地说：“这就是 Affirm 效应！接入你们的分期结账后，我的客单价和整体销售额暴增了 35%，请你们千万继续做下去！”

<details>
<summary>Original English</summary>

**Max Levchin**: She would email me screenshots of her dashboards and say, "This is the Affirm effect. Here's a 35% pop you guys caused for me. Please do more."

</details>

**Alex Rampell**: 解决完睡衣类目的转化问题之后，我们迎来了真正爆发式增长的风口——**盒装床垫 DTC 浪潮**（Purple、Casper、Tuft & Needle 等）。

<details>
<summary>Original English</summary>

**Alex Rampell**: There was a solution to the pajama problem, and then it was also all the mattress companies.

</details>

**Max Levchin**: 没错，那是真正的大风口。

<details>
<summary>Original English</summary>

**Max Levchin**: Oh yes, that was the big one.

</details>

**Alex Rampell**: 当时市场上突然冒出了无数家床垫公司，比如 Purple、Casper、Nectar 等等。

<details>
<summary>Original English</summary>

**Alex Rampell**: That was another... that was the big one. I remember it's like, wait, there's a company called Purple, a company called Casper...

</details>

**Max Levchin**: 那是一场极其疯狂的行业狂潮。一张记忆海绵床垫售价 1000 到 2000 美元，客单价极高。消费者极度渴望分期付款，而床垫品牌之间竞争极其惨烈，获客成本高昂，因此床垫品牌非常愿意向 Affirm 支付高额的商户费率（MDR），甚至愿意补贴 0% APR 免息分期来换取更高的订单转化率。

随后，我们又看到了另一个类似的狂热赛道：**营利性在线编程训练营与职业教育机构**（如 General Assembly、Bloc 等）。

<details>
<summary>Original English</summary>

**Max Levchin**: It was an incredible wave. A memory foam mattress cost $1,000 to $2,000. High ticket size. Consumers loved paying over 12 months, and mattress companies had huge margins and fierce CAC competition, so they were eager to pay high Merchant Discount Rates (MDR) and subsidize 0% APR financing to boost checkout conversions. Then the next boom was for-profit vocational training and coding bootcamps.

</details>

**Alex Rampell**: 比如类似凤凰城大学（University of Phoenix）或阿波罗集团旗下的各种培训机构。

<details>
<summary>Original English</summary>

**Alex Rampell**: Some of them like Apollo Group, University of Phoenix, coding academies.

</details>

**Max Levchin**: 当时各种编程训练营雨后春笋般冒出来，学费高达 1.5 万到 2 万美元。这些机构非常渴望接入 Affirm，因为学员根本拿不出整笔现金。

但我们在深入运营后，选择**主动且坚决地逃离了这个行业**。

为什么？因为我们深入分析后发现，这些高客单价教育机构之所以愿意向我们支付极其高昂的通道费率，是因为其教学质量普遍参差不齐，很多学员毕业后根本找不到工作。这些机构本质上是把学员找不到工作、无力偿还学费的违约风险甩给了贷款机构。如果 Affirm 坚持以消费者利益为中心，我们就绝不能靠给低就业率的高价课程放贷来赚取不良资产收益。我们选择果断砍掉这部分业务。

<details>
<summary>Original English</summary>

**Max Levchin**: Coding academies were charging $15k–$20k. They were willing to pay enormous MDRs. But we ran out of that space kicking and screaming because the reason they were willing to pay high fees was that the educational quality was often dubious, and students couldn't get jobs to repay the loans. It transferred default risk onto the lender. Since Affirm's mission was to be aligned with consumers, we refused to underwrite predatory education loans and exited the space entirely.

</details>

**Alex Rampell**: 回到床垫行业，床垫的生产供应链其实高度集中。

<details>
<summary>Original English</summary>

**Alex Rampell**: The mattress manufacturing was actually all consolidated. They paid very little for the foam, but spent everything on marketing.

</details>

**Max Levchin**: 床垫品牌的核心价值方程式非常耐人寻味：他们以极低的成本采购记忆海绵，真空压缩后塞进盒子里寄给用户。他们的核心壁垒不是制造，而是数字营销与品牌心智。因此，与 Affirm 合作提供透明、无隐形收费的月付方案，成为了他们打赢 DTC 营销战的核心武器。

<details>
<summary>Original English</summary>

**Max Levchin**: Their value equation was fascinating. The cost of goods was low, shipping compressed foam in a box was cheap, so their entire battle was CAC and conversion. Offering Affirm's transparent, no-late-fee monthly installments became their primary conversion lever.

</details>

### PayPal 早期的欺诈防御战与风控哲学

**Host**: 我们回顾了 Affirm 的创业史。既然这是一期历史复盘特辑，我也想借机探讨一下 PayPal 早期的历史。Jimmy Soni 写的《Founders》一书近期引发了大家对 PayPal 创业岁月的广泛讨论。在经历了如此激烈的市场竞争与体系演变后，你们如何看待当年的成功要素？

<details>
<summary>Original English</summary>

**Host**: While we're doing a historical episode, I also want to ask a question about PayPal history. The book 'The Founders' came out recently and there's been a lot of revisiting of PayPal. What were the defining factors that allowed you to survive and win?

</details>

**Max Levchin**: 关于这个问题，有一个经典答案，也有一个全新的回顾视角。

经典答案在于：**风控能力是支付企业的生死线**。在 2000 年前后，网络欺诈呈现爆发式增长，俄罗斯和东欧的黑客盗取数以万计的信用卡号并进行洗钱套现。传统银行由于结算周期长达数天甚至数周，根本无法应对互联网级别的实时欺诈。

PayPal 之所以能在几乎所有竞争对手都因坏账爆仓倒闭时存活下来，是因为我们从第一天起就将风控算法（如著名的 **Igor 欺诈分析系统**）置于公司最高优先级。我们用机器学习与行为模式分析，在毫秒级别实时识别并拦截恶意交易。

而从全新视角来看：大多数初创公司都面临极高的获客成本，而我们借助 eBay 平台搭建了野蛮生长的病毒式增长飞轮。但如果没有底层的风控盾牌，增长越快死得越快。

<details>
<summary>Original English</summary>

**Max Levchin**: There's an old answer and a new answer. The canonical answer is risk management and fraud detection. Around 2000, internet fraud exploded. Syndicates were using stolen cards to drain funds. Traditional banks with multi-day batch processing couldn't handle real-time internet-speed fraud. PayPal survived because we engineered proprietary real-time fraud models (like the Gausebeck-Levchin test and Project Igor) to stop bad actors in milliseconds. Without fraud defense, viral growth on eBay would have just accelerated bankruptcy.

</details>

**Alex Rampell**: 支付业务的本质在于：产品本身具有沉重的客服与风险履约负担。如果系统被黑客和恶意刷单者击穿，不仅资金受损，还会被卡组织和监管机构直接封杀。

<details>
<summary>Original English</summary>

**Alex Rampell**: You already have the burden of supporting your product and dealing with chargebacks. A payments company that fails at fraud prevention will get completely destroyed by network penalties and chargeback losses.

</details>

### AI 时代的前瞻：Agentic 购物 vs Agentic 支付

**Host**: 在今天的访谈结束之前，还有什么重要话题是你们希望深入探讨的？

<details>
<summary>Original English</summary>

**Host**: Is there anything we didn't get to that you want to make sure that we get to while we're here?

</details>

**Max Levchin**: **我对“Agentic 购物”（AI 代替人类挑选商品）相对悲观，但对“Agentic 支付”（AI 代替人类优化支付路径与资金流）极其乐观。**

<details>
<summary>Original English</summary>

**Max Levchin**: I'm probably less optimistic about agentic shopping, and I'm very optimistic about agentic payments.

</details>

**Max Levchin**: 所谓“AI 机器人会自动帮我们选购周五晚宴要穿的衣服”这种概念，在很大程度上是对人性的误判。购物不仅是获取物品，更是审美表达、情感投射与多巴胺分泌的过程。在穿上衣服之前，我们人类自己必须亲自看到、挑选并确认“我穿上它好不好看”。人类不会愿意把这种自我表达的乐趣完全让渡给机器。

但在结账与支付环节，情况则完全相反。

<details>
<summary>Original English</summary>

**Max Levchin**: The notion that robots will buy our Friday night outfits is misguided. We want to know what we look like long before the robot delivers it. Shopping is emotional, aesthetic, and self-expressive. But payments are completely the opposite.

</details>

**Alex Rampell**: 我基本同意你的看法。但我认为在购物过程中需要区分两类行为：一类是寻找并调研商品信息，在这个阶段 AI 只是你手头强大的搜索与对比工具，就像你向骑行圈的朋友咨询哪个自行车飞轮配件好用一样；

而真正的痛点在于：当我决定购买时，我手里有 9 张不同的信用卡，我根本记不住大通银行（Chase）联名卡在非餐厅场景下对于 500 美元以下消费的具体返现条款和积分倍率，我也记不清哪张卡目前正处于 0% APR 优惠期。

<details>
<summary>Original English</summary>

**Alex Rampell**: I mostly agree, but research vs payment are different. For research, AI is a great tool, like asking a friend about bike parts. But for payments: I have nine different credit cards. I don't remember the Chase Amazon card terms for a non-restaurant purchase under $500 versus another card's cashback promotion or 0% APR teaser rate.

</details>

**Max Levchin**: 没错！这就是 **Agentic Payments** 的巨大价值所在。

消费者在付款那一秒面临着极其复杂的最优解决策：
1. 哪张卡当前返现积分最高？
2. 哪种支付方式附带更优的退货保障或延保保险？
3. 是直接划扣活期资金，还是使用 Affirm 的 0% 免息分期把资金留在高收益理财账户中赚取利息？

人类的大脑不擅长在结账的 3 秒钟内完成这种多变量金融优化，但 AI Agent 却能在毫秒级瞬间为用户计算并执行最优支付组合。

<details>
<summary>Original English</summary>

**Max Levchin**: Exactly. That's the immense opportunity for Agentic Payments. At the point of sale, optimizing between: Which card gives maximum points? Which payment method has purchase protection? Should I pay now or use a 0% APR installment with Affirm while keeping cash in high-yield savings? Humans cannot calculate that multi-variable optimization in 3 seconds, but an AI Agent can do it instantly.

</details>

**Host**: 这是一个极具启发性的总结。未来的支付不仅是资金的搬运，更是智能决策的实时协同。Max，Alex，非常感谢你们今天带来如此精彩的深度分享！

<details>
<summary>Original English</summary>

**Host**: That's a great note to end on. We'll definitely have to do a part two to talk more about the future. Max, Alex, thanks so much for joining us!

</details>