---
author: All-In Podcast
date: '2026-07-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wcV0SRPFK9s
speaker: All-In Podcast
tags:
  - model-performance
  - open-source-debate
  - regulatory-action
  - copyright-law
title: 开源模型性能突破引发的国际监管辩论与版权诉讼
summary: 文章讨论了中国开源模型在性能上逼近顶级商业模型的现状，引发美国关于禁止此类模型的激烈辩论。同时，还提到了白宫内部对这一问题的复杂立场、政府激励顶尖实验室开发开源模型的倾向，以及围绕AI训练数据的版权和法律诉讼的最新进展。
insight: ''
draft: true
series: ''
category: tech-trends
area: geopolitics
project: []
people: []
companies_orgs:
  - moonshot ai
  - anthropic
products_models:
  - kimmy k3
  - opus 4.8
  - gpt 5.6
media_books: []
status: evergreen
---
<!-- chunk 1/12 -->

### 金米 K3 引发的辩论

**Host**: 大家好，欢迎回来。这是世界上最棒的播客的第 282 集。这是你们的播客创作者最喜欢的播客。也是你们妈妈最喜欢的播客。这就是 All-In 播客。今天和我在一起的还是大卫·萨克斯（David Sacks）以及大卫·弗里德伯格（David Friedberg）。这周发生了很多大事。非常重要的一周。呃，目前世界上持续位居第一的新闻就是金米（Kimmy）K3。它引发了一场关于是否应该在美国禁止中国开源模型的辩论，并且在上周五，这件事甚至惊动了白宫。我们在这里讨论过这件事。中国的人工智能公司月之暗面（Moonshot AI）发布了金米 K3 开源模型。很显然，它的性能已经赶上来了——不是落后 6 个月，也不是落后 12 个月，而是现在已经与 Opus 4.8 和 GPT 5.6 这样的模型平起平坐了。这本身就令人惊叹，但它还要便宜大概 50%。这引发了一定程度的恐慌，类似于我们在 2025 年初经历的 DeepSeek 时刻。

<details>
<summary>Original English</summary>

**Host**: All right, everybody. Welcome back. Episode 282 of the world's greatest podcast. It's your podcasters's favorite podcast. It's your mom's favorite podcast. It's the All-In podcast. With me again, David Sax up to you, David Freeberg. It was a big week. It was a big week. Uh the continuing number one story in the world is Kimmy K3. It's sparked a debate about banning Chinese open-source models here in the United States and it's gone all the way to the White House last Friday. We talked about it here. China's Moonshot AI released Kimmy K3 open source model. Obviously performance on par on par not 6 months behind not 12 months behind but now on par with models like Opus 4.8 and GPT 5.6 six, which in and of itself is extraordinary, but about 50% cheaper and uh this has created a bit of a panic similar to the Deep Seek moment that we had here back in early 2025.

</details>

**Host**: 白宫和大卫·萨克斯已经卷入其中。我们节目的老朋友迈克尔·卡齐奥（Michael Katzio）引述道：“我们掌握的情报表明，月之暗面 AI 通过提取 Anthropic 模型的内容来开发他们的 K3 模型。” 以下是特朗普政府目前的反应。周一，Axios 报道称白宫正在考虑禁止中国开源模型。大卫，几个星期前，我想大概是三周前，我曾把它作为一个假设情况向你提出来，结果我们现在就走到了这一步。周三，Wired 报道说节目的老朋友霍华德·莱提克（Howard Letic）并不想禁止中国模型。所以显然这其中有宫廷内斗，特朗普的白宫内部可能存在不同的意见。相反，他们想要激励更多美国的顶尖前沿实验室去开发更好的开源模型。Polymarket 平台显示，美国政府在 2026 年禁止一款开源模型的概率为 45%。这是一个全新的预测市场，几天前它才只有 22%。萨克斯，你两个月前就预见到了这一点。这是我们这一集的第一个胜利时刻。当时你说：“我认为所有这些最终都会导向试图禁止开源模型。有很多线索指向这一点。如果你看看大量关于模型需要设置护栏（guard rails）的言论，以及声称由于开源模型可能会被移除护栏从而变得危险的说法，你就能在 Anthropic 的博客文章中看到这种说辞了。他们描述的任何威胁，他们似乎都会特意借题发挥去攻击开源模型。我认为他们再次试图制造概念或在公共记录中设定先决事实，以证明以后的行动是正当的。我认为他们觉得时机成熟，或许可以直接推动那种禁令只是时间问题。”

<details>
<summary>Original English</summary>

**Host**: The White House, David Saxs, has gotten involved. Michael Katzio, friend of the show, said, quote, "We have information that Moonshot AI distilled anthropics fable for the development of its K3 model. Here's how the Trump administration has reacted so far. Monday, Axios reported the White House was considering banning Chinese open source models. A couple of weeks ago, David, I I think it was three weeks ago, I I gave that to you as a hypothetical, and here we are. On Wednesday, Wired reported that Howard Letic, friend of the show, does not want to ban Chinese models. So apparently palace intrigue there might be different opinions inside Trump's white house and instead they want to incentivize more US frontier labs to develop better open source models. Poly market says 45% chance US government bans an open source model in 2026. Uh that was a brand new market started just it was at 22% a couple days ago. Saxs um you called it two months ago. Our first victory fap of the episode. I think where it's all leading to is an effort to ban open source models. There's a lot of breadcrumbs leading here. If you look at a lot of the rhetoric around how models need to have guard rails and that with open source models, the guardrails can be removed and therefore they're dangerous. You see this rhetoric already in Anthropics blog posts. Any threat that they describe, they kind of go out of their way to take that shot at open source models. I think again they're trying to create ideas or put predicate facts in the public record to justify an action later on. I think it's just a matter of time before they feel like they're at a position where maybe they can push for that type of ban directly.

</details>

**Host**: 好了，事情就是这样。萨克斯，白宫那边到底是怎么回事？政府在这个问题上是什么立场？为什么我们会听到多种不同的说法？是白宫在试探和摸底，试图弄清楚他们自己应该在这个问题上采取什么立场，还是说这仅仅是一个超级动态的局势？到底发生了什么？

<details>
<summary>Original English</summary>

**Host**: All right, there it is. Sachs, what's going on at the White House? What is the administration's position here? Why are we getting multiple? Is the White House testing and and probing to figure out what their position is here or is it just this is a super dynamic situation? What's going on?

</details>

**David Sacks**: 嗯，听着，我的意思是，有可靠的消息来源告诉我，白宫并没有做出禁止开源模型的决定，而且我认为他们希望外界知道这一点。我认为目前围绕如何处理中国模型蒸馏（distillation）的问题正在进行持续的对话，我们也应该讨论一下这个话题。但是目前还没有做出任何决定，总统倾听多方的声音。他希望从尽可能多的人那里获得建议。而且我深信，如果大家都发表了意见，总统会做出正确的决定，就像他在这些科技问题上一贯做的那样。我认为他在这一领域的直觉绝对是无懈可击的，而且他总是支持一种，比方说，监管更宽松、更加开放的方法，这也是我认为（清嗓子）美国正在赢得人工智能竞赛的原因。所以我认为事情目前的状况就是这样。嗯……

<details>
<summary>Original English</summary>

**David Sacks**: Well, look, I mean, I have it on good authority that there is no decision by the White House to ban open- source models and I think they want that known. I think there's an ongoing conversation happening around what to do about Chinese distillation and we should talk about that. But no decision has been made and the president listens to a course of voices. He wants to get advice from as many people as possible. And I'm confident that if everybody weighs in that the president will make the right decision as he always has with these tech issues. I think his instincts have been absolutely impeccable on this and he's always supported a let's say lighter regulation more open approach and that's why I think the [clears throat] US is winning the AI race. So I think that's kind of where where things stand. Um

</details>

### 开源生态与模型蒸馏争议

**Host**: 那你的立场是什么？你的立场是什么，萨克斯？这是大家都想知道的。

<details>
<summary>Original English</summary>

**Host**: where do you stand? Where do you stand Sax? That's what everybody wants to know.

</details>

**David Sacks**: 是的，我认为让我表达自己的观点很重要，本着再次贡献自己声音的精神，这样总统就能听到所有观点，然后做出最好的决定。听着，我认为如果政府对开源生态系统采取行动，那将是一个悲剧性的错误。那样做除了会损害美国在这场人工智能竞赛中的地位之外，毫无益处。这会严重地适得其反。而且我认为这里的关键点在于，无论你怎么看待模型蒸馏（distillation），你都不能因此去惩罚美国的开发者。所以，你知道，你不能说美国公司和美国开发者不能使用中国向公共领域贡献的东西。那纯粹是损人不利己。我的意思是，很显然，

<details>
<summary>Original English</summary>

**David Sacks**: Yeah, I think it's important for me to make my opinion known in the spirit of again contributing my voice so the president hears all perspectives and then can make the best decision. Look, I think it would be a tragic mistake if the government were to take action against the open source ecosystem. That would do nothing but hurt America's position in this AI race. It would backfire badly. And I think that the key point here is that regardless of what you think about distillation, you cannot punish American developers for it. So, you know, you can't say that American companies and American developers can't use Chinese contributions to the public domain. That's just cutting off our nose to spite our face. I mean, obviously,

</details>

**David Sacks**: 美国公司必须能够使用公共领域里的所有内容，因为世界上的其他地方都会使用这些东西。我想说，我一直都在指出 Anthropic 犯有监管捕获（regulatory capture）的罪行，也就是试图寻求政府的保护。这家公司是历史上在达到一定规模后增长最快的科技公司。他们年初的年度经常性收入（ARR）是 100 亿美元。现在他们的 ARR 已经超过了 700 亿美元。这并不是一家需要政府保护的公司。这也不是一家受到竞争对手（无论他们是中国人还是其他国家的人）威胁的公司。然而他们却非常成功地试图让大家感到恐慌，让人误以为他们需要某种形式的政府保护。而且在这个问题上，能让你看穿整个“蒸馏”说法是虚假的证据就在于，如果阻止蒸馏是他们的首要目标，那么 Anthropic 会推动禁止中国访问美国的模型，而不是禁止美国访问中国的模型。

<details>
<summary>Original English</summary>

**David Sacks**: American companies have to be able to use everything that's in the public domain because the rest of the world will be using those things. And let me just say, I've said for a while that Anthropic is guilty of regulatory capture, of attempts to seek government protection. This is a company that is the fastest growing tech company at scale in history. They started the year at 10 billion of ARR. They're now over 70 billion of ARR. This is not a company that needs government protection. This is not a company that is under threat from competitors or or whether they're Chinese or otherwise. And yet they have been very successful at trying to panic everybody into thinking that they need some sort of government protection. And the tell on this, the way that you know that this whole distillation thing is fake is because if stopping distillation was their primary objective, Anthropic would push to ban Chinese access to American models, not American access to Chinese models.

</details>

**Host**: 是的，他们可以这么做。而且那是可以实现的。他们可以阻断访问。所以——

<details>
<summary>Original English</summary>

**Host**: Yes, they could. And that is that is achievable. They could block it. So

</details>

**David Sacks**: 他们是处于最有利位置去阻断它的人。如果说蒸馏——如果工业规模的蒸馏是对国家安全的威胁，那他们才是需要去阻止它的人，因为那里才是发生蒸馏的源头。你必须从源头上阻止它。一旦你允许中国公司进行蒸馏，那就覆水难收了。

<details>
<summary>Original English</summary>

**David Sacks**: they're the ones in the best position to block it. If distillation, if industrial scale distillation is a national security threat, they're the ones who need to stop it because that is the place where distillation occurs. You have to stop it at the source. Once you allow Chinese companies to distill, the horse is out of the barn.

</details>

**Host**: 对。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**David Sacks**: 而现实情况是，我认为目前这里发生的事情是，在对增长的极度渴望中，Anthropic 在阻止蒸馏方面做得非常糟糕。我的意思是，他们说蒸馏正在以工业规模发生。好吧，如果是工业规模，那肯定很容易被发现。所以是通过学生创建的一波又一波的账号，被打包在暗网上出售吗，你知道，就是通过那种渠道。所以你让在马尼拉、在菲律宾（据我了解）以及印度的人注册所有这些账号，然后他们把这些账号发到暗网上，并使用来自美国的 IP 地址出售它们。是的。这就是它发生的方式。但是规模越是工业化，它就越明显，越容易被发现。而查马斯（Chamath）已经说了一段时间了，你们为什么不对你们的客户进行 KYC（了解你的客户，实名认证）呢？嗯，他们知道如果他们对客户进行 KYC，就会减缓他们的增长速度。所以相反，他们现在说的是，嘿，封禁我们的竞争对手吧。嗯——

<details>
<summary>Original English</summary>

**David Sacks**: And the reality is that I think that what's happening here is that in their lust for growth, Anthropic has done a very poor job at stopping distillation. I mean they're saying that distillation is occurring at industrial scale. Okay, if it's industrial scale, it must be pretty obvious to see. So is waves of accounts being created by students rolled up and sold on the dark web, you know, in those kind of channels. So you got people in Manila, in the Philippines, I understand, and India signing up for all those accounts and then sending them to the dark web and selling them using IP addresses from America. Yeah. So that that's how it occurs. But the more the more industrial scale it is, the more obvious it is to see. And Tamatha has been saying for a while, why don't you KYC your customers? Well, they know that if they KYC their customers, it'll slow their growth. So instead, what they're saying is, hey, ban our competitors. Well,

</details>

**David Sacks**: 这太荒谬了。我的意思是，他们是阻止模型蒸馏的最佳人选。我认为他们在这方面失职了。或者说，如果他们真的认为这是一个如此巨大的威胁，他们就应该拿出他们 90% 毛利率中的几个百分点来解决这个问题。你不该做的是转过头去说美国的开发者不能使用在公共领域里的一切东西。因此在我看来，这场辩论完全是本末倒置，问题应该抛给 Anthropic，让他们解释为什么自己做得这么差，而不是为了 Anthropic 的失败去惩罚整个美国开源生态系统。

<details>
<summary>Original English</summary>

**David Sacks**: that's ridiculous. I mean, they're in the best position to stop the distillation. I think that they're negligent about doing that. or I mean if they really think it's that big a threat, they should use a few points of their 90% gross margins to do that. What you don't do is then say that American developers cannot use everything that's in the public domain. So it seems it seems to me that this debate is all backwards that the question should be on Anthropic to explain why it's doing such a bad job, not on the whole American open source ecosystem to be punished for Anthropic's failure.

</details>

### 企业市场动态

**Host**: 好了，弗里德伯格（Freeberg），我有一个很好的问题要问你，但在那之前，查马斯（Shimath），你能不能稍微跟我说说你在打 8090 的销售电话时都听到了些什么？你正在和各个企业对话。他们听到了所有这些报道，无论是从你、达里奥（Dario）、这个播客，还是在其他地方听到的，都在谈论说，嘿，开源已经准备好了。就是现在。夺回控制权，实现 AI 主权等等。他们肯定会打电话给你说，嘿，好的，我们准备好了。比如，我们怎样才能把这些东西部署在本地（on prem）？我们该怎么做？那么，在你和企业的那些通话中都发生了些什么？然后你能不能大概给人们介绍一下到底什么是模型蒸馏，以及为什么它在这里如此重要。

<details>
<summary>Original English</summary>

**Host**: All right, Freberg, I have a really good question for you, but before we do that, Shimath, can you give me maybe a little bit of what you're hearing on your sales calls for 8090? You're talking to enterprises. They're hearing all these reports, whether it's you, Daario, this pod, other places talking about, hey, open source is ready. This is the moment. Get control, AI sovereignty, etc. They must be calling you up and saying, hey, okay, we're ready. Like, how do we get these things on prem? How do we do it? So what's the what's happening on those calls you're doing with the enterprise and then can you maybe give people an idea of what distillation is just and and why it's so important here.

</details>

**Shimath**: 让我们从第二件事开始说起。蒸馏（Distillation）就是当你启动一个模型，你向它提出一个问题，你观察它，然后你获取它的输出结果，并将其用于训练你自己的——

<details>
<summary>Original English</summary>

**Shimath**: Let's start with the second thing. Distillation is when you fire up a model and you ask it a question and you observe it and you take its output and you use that in training of your own

</details>

<!-- chunk 2/12 -->

### AI模型的同质化与估值保卫战

**Speaker A**: 现在把那种行为放大几千万倍，你所提取的本质上就是数以万亿计的问答。萨克斯（Sax）说得对。如果你真的在乎模型蒸馏（distillation），你就应该实施KYC（了解你的客户）。你得强制人们不仅用用户名和密码注册账号，还要提供某种形式的身份证明，或者绑定信用额度有限的信用卡。[轻嗤] 其实你们可以采取各种措施，老实说这些措施虽然会拖慢营收的增长速度，但从根本上能解决模型蒸馏的问题。所以，蒸馏问题其实并不是什么大不了的事。这有点像是在转移视线（red herring）。关于模型蒸馏的另一点是，每个人在某种程度上都进行过蒸馏。问题是谁在从谁那里蒸馏？这看起来就像那个搞笑的梗图，九个蜘蛛侠互相指着对方。这就是现在的状况，因为Anthropic从所有这些出版商那里蒸馏了数据。他们只需支付15亿美元的罚款。显然，OpenAI也从《纽约时报》那里蒸馏了数据。现在还有一场正在进行的诉讼。而中国的人工智能实验室则从Anthropic那里进行了蒸馏。

<details>
<summary>Original English</summary>

**Speaker A**: model. Now multiply that behavior by tens of millions and what you exfiltrate is essentially trillions of questions and answers. And Sax is right. If you really care about distillation, you implement KYC. You force people to make an account, not just with a username and a password, but with some form of identification, maybe with a bounded credit card. [snorts] There's all kinds of steps that you can take that would frankly slow things down in terms of revenue traction, but would solve the distillation problem on its face. So, that isn't really a thing. It's a bit of a red herring. The other thing on distillation is everybody has at some point distilled. The question is who is distilling from whom? And it looks like that funny meme where there's like nine Spider-Man all pointing at each other. That's what this is because Anthropic has distilled from all of these publishers. They just pay a $1.5 billion fine. Apparently, Open AI distilled from the New York Times. There's still an ongoing lawsuit. the Chinese labs have distilled from anthropic.

</details>

**Speaker B**: 到处都是大规模的剽窃。是的。

<details>
<summary>Original English</summary>

**Speaker B**: It's wholesale stealing everywhere. Yeah.

</details>

**Speaker A**: 呃，我不想称之为剽窃，因为一开始就不清楚到底谁拥有版权。但这里有一个重要的观察：这些模型商品化的速度比任何人想象的都要快得多。我们是怎么知道这一点的呢？因为一旦一个模型公布了它的性能指标，就没有任何有意义的、持久的优势了。你看到的是，字面意义上在几周之内，其他模型——有些是开源的，有些是闭源的，有些是开放权重的——就能赶上，甚至在某些情况下超过其性能。所以我认为这里正在发生的事情是，少数几家美国公司已经意识到：“哇，我们今天看到的这种价值，在5年或10年内可能无法持续。”当你去向华尔街展示一个商业模式时，你需要有这种确定性，否则它会影响你的估值。所以我认为现在发生的大很多事情，杰森（Jason），其实是闭源前沿实验室的一场“估值保卫战”。因为如果你真的明白这些东西商品化的程度，以及它发生的速度，你就会看到真正的商业模式已经不再是基础模型本身了。它存在于上面的应用层，也存在于下面的基础设施层，无论是云端还是芯片。因此，我认为，在没有监管干预的情况下，在美国政府没有介入并施加影响的情况下，将会发生的是，随着人们了解到价值正在如何发生转移，他们会将更多的价值放在应用层，将更多的价值放在基础设施层。这对闭源前沿实验室来说是不利的，特别是当它们的定价是开源替代品的25到50倍，存在严重错误定价时。所以，这是一种试图阻止与它们质量相同但便宜得多的竞争对手的手段。现在这里还有另一件重要的事情，那就是如果美国政府介入，那将会使股市崩盘。

<details>
<summary>Original English</summary>

**Speaker A**: Well, I don't want to call it stealing because it's not clear who actually owns the copyright in the first place. But here should be the important observation. These models are getting commoditized much faster than anybody thought. And how do we know this? Because there is no meaningful sustained advantage once a model publishes their performance criteria. What you see is literally within weeks other models some open some closed some open weight who are able to match and in some cases exceed the performance. So I think what's happening here is a handful of American companies have realized whoa this value that we are seeing today may not be sustainable in a 5 and 10 year period and when you go and present a business model to Wall Street you need to have that certainty otherwise it impacts your valuation and so I think a lot of what's happening right now Jason is a valuation preservation game by the closed frontier labs because if you actually understood how commoditized these things are becoming and the velocity at which it's happening. You see that the real business model is not in the foundational model anymore. It's at the application layer above and it's in the infrastructure below whether that's the cloud or whether that's chips. And so I think in the absence of regulatory intervention and in the absence of the United States government stepping in to put their thumb on the scale, what will happen is that as people learn about how value is changing, they're going to put more value in the application layer and more value in the infrastructure layer. That is bad for closed frontier labs, especially when they're mispriced 25 to 50x the open alternative. And so this is an attempt to stop a competitor that is of the same quality but just much cheaper. Now there's another important thing here which is if the United States government intervenes it will tank the stock market.

</details>

**Speaker B**: 真的吗？

<details>
<summary>Original English</summary>

**Speaker B**: Okay?

</details>

**Speaker A**: 绝对的。毫无争议。当然，你可以争论哪些公司的股票会暴跌，我们也可以推演一下那个场景。但举个例子，如果他们说不能再有开源模型了，美国公司不能使用开源模型。好吧，让我们纯粹从股票市场的角度来看。我们以一家普通的标准公司为例，比如可口可乐（Coca-Cola）。嘿，可口可乐，你正试图利用人工智能来改善你的业务。你知道吗？你只能使用这两个选项。而且这些东西的成本，比你本来可能会使用的其他最佳替代方案要高出50到100倍。这最终会体现在你的成本中，因为人工智能本应是这种不可思议的东西，它似乎能解决所有问题，为你做一切事情。所以，这个在你的成本模型中极其重要的输入项，现在却比你美国之外的竞争对手高出几个数量级的倍数，仅仅因为你在美国。那么资本市场会怎么做？他们会说，“哇，你的成本结构太疯狂了。这说不通。你被迫承担了既不合理、也不是由市场驱动的成本。”因此，可口可乐的估值将被重新评定。但接下来你再看看那些销售这些代币的人，这就是Anthropic和OpenAI需要明白的地方。如果政府介入，并真的告诉你没有开源模型了，他们的估值将会暴跌。为什么？因为他们所有的收入都是被人工支撑起来的。

<details>
<summary>Original English</summary>

**Speaker A**: Period. Not debatable. Now you can debate which companies get tanked and we can probably play that scenario out. But for example, if they said no more open source, American companies cannot use open source. Okay, let's just take at it from a stock perspective. Let's take an average normal company, Coca-Cola. Hey, Coca-Cola, you're trying to use AI to improve your business. You know what? You can only use these two options. And those things cost 50 to 100 times more than your other best alternative that you may use otherwise. that will eventually show up in your costs because AI is supposed to be this incredible thing that just kind of solves every problem and does everything for you. And so this incredibly important input into your cost model is now orders of magnitude multiples greater than your competitors that are outside the United States simply because you're in the United States. So what would the capital markets do? They're going to say, "Wow, you have a crazy cost structure. This doesn't make sense. you're forced to absorb costs that aren't rational nor market driven. So then Coca-Cola has to get rerated. But then you look at the people who are selling those tokens and this is where anthropic and open AAI need to understand. If the government comes in and actually tells you that there's no open source, their valuation will crater. Why? Because all of that revenue is artificially being propped up.

</details>

**Speaker C**: 它不是由你被迫竞争的市场需求所驱动的。这是因为监管俘获（regulatory capture），你现在得到了一个人工设定的约束，但这只在一个市场起作用。所以不管怎样，条条大路通向市场混乱。

<details>
<summary>Original English</summary>

**Speaker C**: It's not being driven by market demand where you're being forced to compete. It's because of regulatory capture where you now get an artificial constraint, but it only works in one market. And so anyways, all roads lead to market chaos.

</details>

**Speaker B**: 说得好。是的。

<details>
<summary>Original English</summary>

**Speaker B**: Love it. Yeah.

</details>

**Jason**: 如果有人介入，那我们就干脆别介入。听起来你的意思是，如果政府给了Anthropic和OpenAI一个政府强制的双头垄断，美国企业将支付一笔“代币税”——

<details>
<summary>Original English</summary>

**Jason**: If anybody gets involved, so we should just not get involved. What it sounds like is you're saying that American enterprises will pay a token tax if the government gives anthropic and open AI a government enforced duopoly

</details>

**Speaker C**: ——而且企业将不再像世界其他地方一样，可以自由使用开源软件。是的。

<details>
<summary>Original English</summary>

**Speaker C**: and enterprises are no longer free to use open source like the rest of the world. Yes.

</details>

**Jason**: 是的。有上限的市场。

<details>
<summary>Original English</summary>

**Jason**: Yeah. The markets with the cap.

</details>

**Speaker C**: 我们将把自己置身于孤岛之上。是的。

<details>
<summary>Original English</summary>

**Speaker C**: We will put ourselves on an island. Yeah.

</details>

**Jason**: 我们将处在一个充斥着极其昂贵的AI的孤岛上。

<details>
<summary>Original English</summary>

**Jason**: We'll be on an island of overly expensive AI.

</details>

**Speaker A**: 你可以选择可口可乐，或者百事可乐，或者是可口可乐，或者是百事可乐。

<details>
<summary>Original English</summary>

**Speaker A**: You can have CocaCola or Pepsi or Coca-Cola or Pepsi.

</details>

**Jason**: 是的。嗯，这不像你选饮料那样。你有两种饮料可以选择，但它们的价格是美国以外可乐的50倍。这就是关键所在。我们明明到处都已经有可乐了。所以，

<details>
<summary>Original English</summary>

**Jason**: Yeah. Well, it's not your beverage choices. You have two beverage choices, but they cost 50 times more than Coke outside of America. This is the point. We already have Coke everywhere. So,

</details>

**Speaker C**: 你可以买50美分的可乐，也可以买50美元的可乐。当你能买到50美分的可乐时，你为什么要买50美元的可乐呢？

<details>
<summary>Original English</summary>

**Speaker C**: you can buy 50 cent coke or $50 Coke. Why would you buy $50 Coke when you can buy 50 cent coke?

</details>

**Jason**: 是啊。

<details>
<summary>Original English</summary>

**Jason**: Yeah.

</details>

**Speaker D**: 好了。让我们……让我也插一句。是的。

<details>
<summary>Original English</summary>

**Speaker D**: All right. Let's get Let me get free here. Yeah.

</details>

**Speaker A**: 好的。我只想就这事说一点。这回到了我的观点，即这些来自Anthropic的禁止开源的提议。它们解决不了模型蒸馏的问题。如果蒸馏是个问题，你必须从源头上阻止它。换句话说，如果你想在美国禁止开源，世界其他地方仍然会使用中国的开源模型。我们想要解决那个问题。

<details>
<summary>Original English</summary>

**Speaker A**: Okay. I was going to say just just just one thing on this. This goes back to my point of these proposals to ban open source that are coming from anthropic. They don't solve the distillation problem. If dissolation is a problem, you have to stop it at the source. In other words, if you want to ban open source in America, the rest of the world will still be using Chinese open models. We want to solve that problem.

</details>

**Jason**: 是的。那意味着他们将获得数据，他们将获得强化学习成果，然后我们保证会在人工智能竞赛中落败。弗里德伯格（Freedberg），让我们借用格雷厄姆·艾利森（Graham Allison）的视角，把这里的讨论提升一个层次。禁止中国模型将是非常具有挑衅性的。习近平对此会作何反应？中共对此会作何反应？这是一个疯狂的棋盘。这似乎是相当容易引发升级的举动，我们将步步升级。说说看，弗里德伯格（Freeberg）。

<details>
<summary>Original English</summary>

**Jason**: Yes. And that means they'll get the data and they'll get the reinforcement learning and then we lose the AI race guaranteed. Freedberg, let's take it from a Graham Allison and level up the discussion here. Would be quite provocative to ban the Chinese models. How does Xi Jinping respond to that? How does the CCP respond to that? This is a crazy chessboard. It would seem like a pretty escalatory and we'll be going up the ladder. Yeah, Freeberg.

</details>

### AI模型蒸馏与技术借鉴

**Freedberg**: 是的，听着，我认为……我认为开源模型尚未由中国发布这一点并不那么相关，这可能存在安全风险，但这些风险是可以评估和解决的。我认为在这个问题上，有三件事值得强调，我非常同意萨克斯（Sax）和查姆（Chim）的观点，我认为这三件事都围绕着模型蒸馏展开。而且我不认为蒸馏仅仅是人工智能领域才有的。你知道，蒸馏是一个过程，通过这个过程，你观察别人生产的最终产品，在思考和学习如何去设计你自己的产品。这是各行各业每个产品类别中都在使用的常用技术。一家汽车制造商会研究另一家汽车制造商生产的汽车是如何运作的，他们将利用这些信息来帮助自己设计出一款更好的汽车。你知道，在谷歌的早期，我们会向雅虎和微软的搜索引擎提交数百万个搜索查询，看看结果集是什么样的，然后我们会将自己的结果与他们的结果进行比较，作为一种改善我们搜索引擎排名和算法的方法。这是一种非常普遍的技术。这并不意味着我们窃取了他们的算法。我们没有侵入他们的服务器去偷他们的软件。我们观察的是他们软件的输出，并利用它来改进我们的软件。

<details>
<summary>Original English</summary>

**Freedberg**: Yeah, I look I don't I don't think it's as relevant that the open source model is published by China yet that there may be security risks, but those can be estimated and addressed. I think on the three things that are worth highlighting on this this issue, I'm I'm very much aligned with Sax and Chim and I think the three things are really around distillation. And I don't think distillation is just about AI. You know, distillation is a process whereby you look at the end product that someone else has produced in thinking about and learning about how to engineer your product. It is a common technique that is used across every product category in every industry. One car maker will look at how the other car maker's car operates and they will use that to help them design a better car. You know, at Google in the early days, we would submit millions of search queries to Yahoo and Microsoft search engines to see what the result sets were and we would compare our results against their results as a way of improving our search engine rankings and our algorithm. It was a very common technique. It doesn't mean we were stealing their algorithm. We didn't go into their servers and steal their software. We looked at the output of their software and use that to improve our software.

</details>

**Speaker C**: 这叫做基准测试（benchmarking），对吧？这是基准测试。你可以叫它……有很多个词来形容。完全正确。所以我不认为这有那么重要。我认为关于版权侵权或知识产权侵权的问题——

<details>
<summary>Original English</summary>

**Speaker C**: It was called benchmarking, right? It was benchmark. You can call it there's been a million terms. Exactly. Right. And so I don't think that this matters as much. I think the question around copyright infringement or IP infringement

</details>

**Speaker A**: 萨克斯说得对。这里有一个服务条款的问题，但那取决于服务提供商去修改服务条款，如果他们愿意，可以阻止人们这样做。

<details>
<summary>Original English</summary>

**Speaker A**: Sax is right. There's a terms of service question here, but that's on the service providers to fix the terms of service blocking people from doing this if they so chose.

</details>

**Speaker C**: 但关于版权的争论、知识产权的争论，真正的核心在于：他们是否窃取了软件？他们并没有窃取软件，他们只是看了输出。

<details>
<summary>Original English</summary>

**Speaker C**: But the copyright argument, the IP argument is really about did they steal the software? They didn't steal the software and they just looked at the output.

</details>

**Speaker A**: 那不构成侵犯知识产权。那也不构成侵犯版权，在——

<details>
<summary>Original English</summary>

**Speaker A**: That's not IP infringement. That's not copyright infringement in the

</details>

<!-- chunk 3/12 -->

### 知识产权、模型蒸馏与开源之争

**Speaker A**: 古典意义上的。因此，我确实认为从模型蒸馏（distillation）的知识产权争论角度来看，真正重要的是输出结果，而不是过程。所以问题在于，他们是在复制受版权保护的软件并使用它，还是仅仅在观察它的输出？因此，我认为你在这里真正需要评估的是输出结果，而不是工程过程。

<details>
<summary>Original English</summary>

**Speaker A**: classical sense. And so I do think from a distillation IP argument perspective, it's the output, not the process that matters. So the question is, are they taking copies of copyrighted software and using it or are they looking at the output? And so I think output not process of engineering is what you really need to assess here.

</details>

**Speaker B**: 我能插句话吗？关于这一点，我认为很多在所谓政策圈里的人并不理解这种区别，但我认为科技界的每个人都懂。我觉得这也正是为什么在这个问题上会出现巨大认知脱节的重要原因：模型权重（weights）和输出（outputs）之间有着天壤之别，对吧？权重就是那些数字文件，它是软件代码中的数值参数，它就是代码本身。

<details>
<summary>Original English</summary>

**Speaker B**: Can I insert something free? comment on it is I think a lot of people in the let's say policym community don't understand this distinction but I think everybody in tech does and I think it's a big part of why there's a disconnect on this is there's a huge difference between model weights and outputs right so the weights are the it's the file of numbers it's the numerical parameters in the software code that's the code

</details>

**Speaker C**: 没错，那就是软件，那就是代码。如果中国公司窃取了——

<details>
<summary>Original English</summary>

**Speaker C**: that's the software that's the code and if Chinese companies were to steal

</details>

**Speaker B**: 窃取了像 Anthropic 或 OpenAI 那些专有的模型权重，那确实是盗窃。好的，但这并不是我们在这里讨论的情况，因为没有人指控他们这么做。我们现在讨论的是，获取模型的输出结果，然后试图从中进行学习，并且——

<details>
<summary>Original English</summary>

**Speaker B**: weights proprietary weights from anthrop ropic or open AI that would be theft. Okay, but that's not what we're talking about here because no one's accused that. What we're talking about here is taking model outputs and then trying to learn from them and

</details>

**Speaker C**: 利用其他人的软件来进行学习。

<details>
<summary>Original English</summary>

**Speaker C**: using other people's software to learn.

</details>

**Speaker B**: 是的。这就完全像你刚才提到的 Google 搜索之类的例子。而这件事最虚伪的地方在于，OpenAI 和 Anthropic 都曾争辩说，他们有权利用世界上所有的输出内容来进行模型训练，无论创作者是否愿意。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. And it's exactly the situation you said with like the the Google searches or whatever. And here's the thing that's so hypocritical is that OpenAI and Anthropic have both argued that they are free to train on all the world's output regardless of whether the creator wants them to or not.

</details>

**Speaker C**: 没错。

<details>
<summary>Original English</summary>

**Speaker C**: That's right.

</details>

**Speaker B**: 那就是他们目前的立场。就像 Chamath 提到的《纽约时报》的诉讼。《纽约时报》现在正在起诉 OpenAI——

<details>
<summary>Original English</summary>

**Speaker B**: That is their current position. That's like Chimath mentioned the New York Times lawsuit. The New York Times is suing OpenAI right now

</details>

**Speaker C**: 起诉他们进入《纽约时报》的网站，违反《纽约时报》的服务条款，抓取了所有的信息并用这些数据进行训练。

<details>
<summary>Original English</summary>

**Speaker C**: for going onto the New York Times website in violation of the New York Times terms of service, scraping all the information and training on it.

</details>

**Speaker B**: 而 OpenAI 的辩词是：“听着，我们没有偷任何东西。我们只是获取了《纽约时报》的输出内容，然后我们正在推导得出我们自己的模型权重。” 这恰恰就是那些中国模型正在做的事情，也就是他们获取了美国模型的输出结果，然后推导出他们自己的权重。他们正在从中学习。

<details>
<summary>Original English</summary>

**Speaker B**: And Open AI's argument is look, we're not stealing anything. We're taking the output of the New York Times and we are deriving our own model weights. And that is exactly what these Chinese models are doing is is they are taking the output of American models and then they're deriving their own weights. They're learning from it.

</details>

**Speaker A**: 是的。所以尽管如此，为了让我们在这里把话说清楚，现在的指控是——

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And so the accusation though, just so we're clear here, is that

</details>

**Speaker B**: 指控是，这种工业规模的、秘密违反服务条款的行为存在伦理问题。这也是白宫关于服务条款的看法。所以我想让大家明白，人们对这一点还是有一定共识的。

<details>
<summary>Original English</summary>

**Speaker B**: there's ethical issues around the industrial scale covert breaking of terms of service. That's what the White House has been terms of service as well. So just so people understand like there is a bit of recognition of that.

</details>

**Speaker A**: 听着，让我明确一点，我绝不是在为中国辩护。事实上，你们可以看看我的资历背景。我是第一个甚至提到“模型蒸馏”这个概念的政府官员。我在 2025 年 1 月 DeepSeek 刚出来的时候就谈到了这一点。我上了 Laura Ingraham 的节目，而且我想我可能是政府里第一个向公众公开解释这个概念的人。此外，你们也知道，我是那份《赢得人工智能竞赛报告》（Winning the AI Race Report）的合著者，那份报告的整个前提就是我们想要赢。我们想要击败中国。所以，我绝对不是那种不希望美国赢的人。我希望美国赢。问题在于如何去赢。如果我们为了禁止开源而搬起石头砸自己的脚——也就是说，当世界上其他国家都能利用开源的时候，却不让我们所有的美国公司利用它——那将是一个巨大的问题。当然，我完全支持 Anthropic 和 OpenAI 强制执行他们的服务条款。他们需要做得更好，从一开始就阻止模型蒸馏的发生。如果政府有什么可以做的去帮助他们，那没问题，但我不确定政府具体能做什么。真正需要发生的是，那些公司自己需要更好地执行他们的服务条款。

<details>
<summary>Original English</summary>

**Speaker A**: Look, let me let me be clear that I'm not defending China in this. In fact, you know, look at my my bonafides. I was the first administration official to even talk about distillation. I did it in January of 2025 when deep sea came out. I went on Laura Ingram and I think I was probably the first person in the government to even explain this concept publicly to people and moreover, you know, I was a co-author of the winning the AI race report in which the whole premise of it was that we want to win. We want to beat China. So, you know, I'm definitely not someone in this camp that doesn't want the US to win. I want the US to win. The question is how. And if we shoot ourselves in the foot by banning open source, which is to say not letting all of our American companies take advantage of open source when the rest of the world is able to, then that is a huge problem. Now, I'm fine with Anthropic and Open AI enforcing their terms of service. They need to do a better job, stop the distillation from occurring in the first place. If there are things that the government can do to help them, okay, but I'm not sure what those things are. What needs to happen is those companies need to do a better job enforcing their terms of service.

</details>

**Moderator**: 是的。

<details>
<summary>Original English</summary>

**Moderator**: Yes.

</details>

**Moderator**: 好的。那么，Freeberg，我记得你刚才说过你有三点要讲。我想你已经讲了第一点。我想听听你剩下的那两点。

<details>
<summary>Original English</summary>

**Moderator**: Okay. Now, Freeberg, you had you I think you said you had three points to make. I think you made one. I want to get the other two out of you.

</details>

### 开源软件与言论自由及经济普惠

**Freeberg**: 对的。我的另外一点是关于言论自由的争论，也就是说，听着，什么是开源模型？如果你不是软件行业的人，我觉得听众需要理解这一点。开源就是一个可下载的软件包。你可以把它想象成下载了一段文本、一本书。你直接获取了所有的代码。一旦你拿到了这些代码，它就保存在你的电脑上了。你甚至不需要连接互联网。你直接就可以运行它、使用它。我认为这里即将面临的挑战之一在于，如果有任何企图去限制开源，那将会打开一个潘多拉魔盒，那就是你究竟该如何对开源实施限制？因为你基本上是在告诉人们，一旦他们下载并获得了一份这个免费、公开可用的软件拷贝，他们却不被允许使用它。这就成了一个真正的难题。我不认为在这方面我们有什么很好的先例可循。试图阻止开源将会变得非常难看。我确实认为，可能会有关于版权诉讼之类的问题，但如果要走这条路，那就得通过法定的正当程序去证明案件成立，并阻止那个开源软件的传播。

至于我的第三点，那就是开源对这个世界来说更好。就如 Chamath 刚才所说，它的成本要便宜 100 倍。这对整个行业有利，对企业有利。最终的受益者将是整体经济和广大消费者。从根本上说，如果你回顾互联网的早期时代，Netscape（网景）开发了一款专有闭源浏览器以及专有的服务器软件，也就是 Netscape 软件，然后他们上市了，他们是第一个这么做的，而且当时这个软件非常有价值且利润丰厚。但那家公司最终却被开源彻底击垮了。Mozilla 基金会成立，打造了一款名为 Firefox（火狐）的开源网页浏览器，然后 Google 把那边的人都挖了过去，做出了 Chrome 浏览器，但它依然是建立在开源之上的。Apache 基金会创建了第一个作为开源产品的 HTTP 服务器。这样一来，任何拥有一台电脑的人都可以下载 Apache 软件，搭建一个 Web 服务器，连上互联网并创建一个网站，而不需要向 Netscape、微软或甲骨文支付服务器软件的费用。最终发生的结果是，价值汇聚到了整个互联网之中，而不是流向那少数几个控制着互联网大门和入口的软件供应商手中。基本上，所有的东西都开源了，Google 起飞了，eBay 起飞了，Etsy 和亚马逊起飞了，数以百万计的小型网站和数以百万计的小企业，以及所有人都从一个开放获取的、开源的互联网中获益了。如果互联网是封闭的，如果在整个互联网中遍布着只有付费才能通过的专有软件大门和入口，那么互联网就不会起飞，经济也不会如此增长，而所有这些我们现在看到的工作岗位，当年可能就会统统被称为 AOL 和 CompuServe 类似的东西。

所以现在，当我们看到这种类比，这里的类比就是，如果开源 AI 腾飞了，那么 Bernie Sanders、Elizabeth Warren 以及所有那些社会主义者们一直喋喋不休、大声疾呼的种种担忧，就不再成立了。因为你不会看到 AI 的所有价值仅仅流向两三家或四家公司，以及他们那一小撮亿万富翁股东手里。将会发生的是，AI 得到普及，全世界数以百万计集成了 AI 的企业都将从中获益。每个人都会获益。经济将会增长，就业机会将会被创造出来，AI 会成为一股向善的力量，创造一个开放的经济体。所以，我知道一些在政府里听这段节目的人，以及那些站在对立面的人，肯定会说：“但是、但是、但是中国开源对比美国开源，你这可是让它们全面扩散啊。” 坦白说，如果中国人正在侵犯版权、窃取软件，那就去追究他们这方面的责任。实施贸易制裁。尽你们所能去阻止这种事情发生。但从根本上来说，开源 AI 将彻底改变全球经济，它将确保 AI 的经济价值扩散给每一个人，而不是被少数人垄断。为什么？因为如果那 1% 控制开源的人掌握了它，寡头们的如意算盘就要被打乱了，而我们甚至都不需要再去征收什么财富税了。Chamath，我想我们要在这点上补充一下。

<details>
<summary>Original English</summary>

**Freeberg**: Yeah. So, the other one was just on the free speech argument, which is look, what is an open-source model? And I think the audience needs to understand this if you're not from the software industry, but open source is a downloadable package of software. You can think about it as downloading a a text, a book. You just got all the code. Once you get the code, you've got it on your computer. You don't have to be connected to the internet. You can just run it and use it. And I think part of the challenge that's going to be faced here, if there is any attempt at restricting open source, it's going to open a can of worms on how do you actually enforce restrictions on open source because you're basically telling people once they've downloaded and gotten a copy of this free publicly available software, they're not allowed to use it. And that becomes a real challenge. I don't think we have a lot of great precedent for that. It's going to be very ugly to try and stop open source. I do think there's a question on like copyright action but if there is there's a legal due process to go through to make that case and stop that open source from being available and then my third point is just open source is better for the world to Chimath's point this is 100 times cheaper that is better for the industry for enterprise the beneficiaries are going to be the economy the consumer fundamentally if you look back on the internet in the early days Netscape made a proprietary browser and a proprietary server software, the Netscape software, and that they went public, and they were the first to do this, and it was super it was super valuable and profitable. That company ended up getting crushed because of open-source. The Mozilla Foundation was formed to create an open-source web browser called Firefox, and then Google ended up hiring everyone and made it Chrome, but it was still open source. The Apache Foundation set up the first HTTP server as an open-source product. Rather than having to pay Netscape or Microsoft or Oracle for their server software, anyone with a computer could download the Apache software and make a web server and be on the internet and create a website. And what ended up happening is the value acrewed to the internet. It didn't acrue to the small number of software providers that controlled the gate and the portal of the internet. Basically, everything got open sourced and Google took off and eBay took off and Etsy and Amazon and all the millions of small websites and all the millions of small businesses and everyone that benefited from an openly accessible open-sourced internet. If the internet was closed and there was proprietary software gates and portals throughout the internet that everyone had to pay to get through, the internet would not have taken off and the economy wouldn't have grown and all these jobs would have been called AOL and Coffee Serve like and now now when we look at this analogy, the analogy here is if open-source AI takes off, then all the worries that Bernie Sanders and Elizabeth Warren and all the socialists are harping and larking about are not going to be the case anymore because you're not going to see all the value of AI acrue to two or three or four companies and their small group of billionaire shareholders. What will happen is AI proliferates and a million AI integrated enterprises all over the world will benefit. Everyone will benefit. The economy will grow, jobs will be created and AI becomes a power for good for creating an open economy. So the I know that some people that are listening to this in the government and that are on the other side are going to say but but but Chinese open source versus American open source let it all proliferate. And frankly if the Chinese are violating copyrights, stealing software, go after them for that. Put in place trade sanctions. Do all the you can do to stop that from happening. But fundamentally open-source AI will transform the global economy and it will ensure that the economic value of AI will diffuse to everyone and not be held captive by a small number. Why the 1% that controls open source if they have it the oligarchs are going to get their clocks rung and we don't need to have a wealth tax. Chamathy we're going to add to this.

</details>

**Chamath**: 我们必须承认，令人难以置信的是，在这个细分市场中，价值捕获（value capture）蒸发的速度有多快。在我在硅谷的 25 年里，我从未见过经济的某个特定领域能够在吸收了成百上千亿美元之后出现这样的情况。

<details>
<summary>Original English</summary>

**Chamath**: We have to acknowledge that it's incredible how fast the value capture at this segment of the market has basically evaporated. I've never seen it in my 25 years in Silicon Valley where a sector of the economy can absorb hundreds and hundreds of billions of dollars

</details>

<!-- chunk 4/12 -->

### AI 模型的定价权与大宗商品化

**Speaker A**: ……你认为这种经济定价权能够延续到未来几十年，但实际上它在几个月内就蒸发了。短短几个月。

<details>
<summary>Original English</summary>

**Speaker A**: ... and then you think that there's going to be economic pricing power many decades into the future and it effectively evaporates in months. Months.

</details>

**Speaker B**: 它也是在几个月内起飞的。要知道，它在几个月内起飞，又在几个月内蒸发了。

<details>
<summary>Original English</summary>

**Speaker B**: It took off in months. Remember remember and it's evaporated in months.

</details>

**Speaker C**: 不，在这个问题上我不同意你们的看法。

<details>
<summary>Original English</summary>

**Speaker C**: No, I got this is an area where I disagree with you guys.

</details>

**Speaker A**: “蒸发”这个词太重了。看起来它可能会放缓，或者可能会，或者它可能会进入平稳期。

<details>
<summary>Original English</summary>

**Speaker A**: Evaporate is strong term. It it does look like it could slow down or it could or or it could plateau.

</details>

**Speaker B**: 说吧，Sacks。提出你的论点，然后我会给出我的论点。

<details>
<summary>Original English</summary>

**Speaker B**: Go ahead, Sax. Make your argument and I'll give you my argument.

</details>

**Jason**: 是的，但在你开始之前，Sacks，让我调出 Anthropic 的营收图表，因为这能帮我们在这里缓解一下情绪，并给观众提供一些背景信息。正如你们在这里看到的，在过去的几个月里，Anthropic 的营收出现了一点停滞。而且这似乎是——这是第三方追踪的数据。所以这不是完美的数据，但我们确实看到这是一个明显的阻力。然后，你有没有我准备的第二张图表？嗯，我上周或前一周在播客上谈到过，当时我们在讨论开源，我想是 Altimeter 的 Brad Gerstner 谈到了“嘿，代币（tokens）还在增长”。好吧，有些路由器会追踪 OpenRouter，一个开源模型做得越好，在你自己服务器上部署它、将其引入内部等就越容易。这些都是“暗代币（dark tokens）”。它们没有被记录下来，你也不会在任何地方的营收图表上看到它们，因为它们本质上是免费的。你只需要有服务器和能源就能运行它们。在这里你会看到，现在已经远超 50%，而且其中很多来自中国。

<details>
<summary>Original English</summary>

**Jason**: Yeah, but let me pull up the anthropic revenue chart before you go there, Saxs, because we can this will help mitigate it here and educate the audience. So, as you can see here, we got a little bit of a stall in anthropics revenue uh in the last couple of months. And it seems and and this is third party tracking. So it's it's not perfect data, but we do see that this is a a clear headwind. And then do you have the second chart I had? Um I talked on the pod just uh it was last week or the week before when we're having the discussion about open source and like I think it was um Brad Gersonner uh from alimter was talking about hey tokens are still growing. Well there are routers that track open router. the better an open source model does and the easier it is to implement on your own servers and take it in-house etc. Those are dark tokens. They're not recorded and you're not going to see them show up on a revenue chart anywhere because they're free essentially. You just need to have servers and energy to to do them. And here you see that now well over 50% and um a lot of these are coming from Chinese.

</details>

**Speaker B**: 顺便说一下，Sacks，我想在你给出反驳之前澄清一下。我不是说这些公司赚不到钱。这不是我的意思。我所说的是，市场在透过当前的盈利状况，提出一个非常具体的问题方面非常精明，这个问题就是：10年后这项营收会是什么样？它会上升吗？会下降吗？竞争会变大还是变小？它实际上是垄断的，还是更像是一种大宗商品（commodity）？如果它是一种大宗商品，有多少人能为这种商品定价？10年后那种商品的市场出清价格会是多少？我只是想说，通常这些变量会被暴露出来。这些底牌被翻开的速度相对较慢。因此，你会有 5 到 10 年的周期，从某项商品的独家供应商转变为该商品的实质性大宗商品供应商。我所观察到的是，这太独特了，只有科技才能创造这样一个市场：这个周期可能被压缩到短短几年内。因为，如果你是一个资金配置者，坐在那里看着这些数据，你很难不去想：为什么它在 5 到 7 到 10 年内不会变成一种大宗商品？当他们得出这个结论时——每一个资本配置者都会得出这个结论，因为如果不这么做将是相当失职的——你很难再去赋予它巨大的未来溢价。顺便说一下，真正的资金正在流向哪里？我们在 Google 的财报中看到了，我确信我们也会讨论这一点，资金正流向云端。它正在流向基础设施。所以，顺便说一下，还有另一群人，他们不希望看到开源的终结，因为他们希望提供尽可能便宜的模型，因为他们知道所有的利润空间都在那里。

<details>
<summary>Original English</summary>

**Speaker B**: By the way, Sax, I want to be clear before you give the counter. I'm not saying that these companies won't make money. That's not what I'm saying. But what I am saying is that markets are very savvy in looking through current earnings and asking a very specific question which is what does this revenue look like 10 years from now? Does it go up? Does it go down? Is there more competition or is there less competition? Is it effectively monopolistic or is it more of a commodity? If it's a commodity, how many people can price this good? At what price is the market clearing price of that good in 10 years? And all I'm saying is normally those variables get exposed. Those cards get turned over relatively slowly. And so you have 5 10 year cycles to transition from being an exclusive provider of a good to effectively a commodity provider of a good. And all I'm observing is it's so unique that only technology could create a market where that cycle could get compressed into a few years because it is very hard if you're an allocator of money to sit there and look at this data and not wonder to yourself why it's not a commodity in 5 to 7 to 10 years. And when when they get to that conclusion, which every capital allocator will because it'll be pretty negligent to not, it's very hard to assign huge future premiums. And where the real money is going, by the way, and we saw it in Google's earnings, which I'm sure we'll talk about, it's going to the cloud. It's going to the infrastructure. So, by the way, there's another cohort of people that don't want to see the end of open source because they want to serve the cheapest models possible because they know that's where all the margin capture is.

</details>

**Speaker A**: 这将走向何方，Sacks？两者都会开源吗？我们将会看到一种激增。我的意思是，就我而言，对按需智能（on-demand intelligence）的需求是无限的，而且我认为，你可以获取的智能没有上限，只要它继续变得更好。那么这里的论点将是，没错，它是一种大宗商品，价格在不断下降，但消耗量却在不断上升。你的想法是什么？你必须假设，这正是你们用过的例子。它就像是一个网络浏览器，而在网络浏览器中，它是一种到达某个地方的机制，所以那些真正作为目的地的应用程序才是捕获价值的地方。我认为，如果你假设一瞬间，智能变得完全无处不在。它被广泛获取。它的边际成本实际上是零。生成它所需的能量实际上是零，我认为这是一个准确的假设。你很难说明为什么它不会像浏览器那样……

<details>
<summary>Original English</summary>

**Speaker A**: What's your Where's this going, Sax? Is it both open? We're going to just see a proliferation. I mean as far as I'm concerned there is an unlimited appetite for ondemand intelligence and there's going to be I don't think there's an upper bound for how much intelligence you can tap as long as it's continues to get be better which then the thesis would be yeah it's a commodity and the prices keep going down but consumption keeps going up. What's your thoughts on you have to assume that this is exactly the example that you guys used. It's a web browser and in a web browser it's a mechanism to get to a place and so the apps that are actually the places are where the value is captured and I think if you assume for a second that intelligence becomes completely ubiquitous. It's widely available. The marginal cost of it is effectively zero. The energy to generate it is effectively zero which I think is an accurate assumption. It's very hard to make the case of why this isn't like the browser

</details>

**Speaker C**: ……而且它最终会融入亚马逊 AWS 云业务、埃隆（Elon）的网络服务等。Sacks，你认为这会向什么方向发展？然后我们将进入我们的第二个故事，也就是知识产权（IP）的故事。第三个故事将是市场、具体到 Google，以及特斯拉（Tesla）和 SpaceX。

<details>
<summary>Original English</summary>

**Speaker C**: and it becomes just gets subsumed into the Amazon web services cloud businesses, Elon's web service, etc. Sax where do you think this is going? Then we're going to go to our second story which is the IP story. Third story is going to be the markets and Google specifically and Tesla and SpaceX.

</details>

### 开源与闭源的未来

**Sacks**: 听着，到目前为止在这个节目上大家都有很多非常一致的意见。所以，让我来提出一个反面观点。我认为开源和闭源都将是这场竞争中的大赢家。我认为市场很庞大，它们各司其职。发生的事情是，随着 Kimi K3 的推出，出现了一点小恐慌，大家都说：“天哪，所有的中国模型都赶上来了，而且他们免费提供这些模型，他们将摧毁我们领先的美国前沿实验室。而 Anthropic 和 OpenAI 都在四处游说，‘听着，如果中国公司能直接窃取我们的权重，我们就不能继续投资数十亿美元了。’”对吧？所以这就是他们所提出的、政府官员正在回应的论点。事实的真相是，听着，当 Kimi K3 刚发布时，我也有些担忧，因为我想：“哦，中国赶上来了吗？他们现在能够生产出一个便宜得多的前沿模型了吗？”然后细节开始浮出水面。所以 Ben Thompson 在他的博客中分析了一些成本数据，结果证明 Kimi K3 运行起来并没有便宜多少。它并没有明显的成本优势。所以这是第一点。第二点是，中国并没有赶上。确实，Kimi K3 在前端编码、Web 开发的竞技场测试中得分很高，但那只是一个测试。那只是一个维度。在某些领域它得分很高，但在许多其他领域它得分并不高。所以，它并没有明显领先或明显赶上领先的美国模型。此外，Anthropic 和 OpenAI 的实验室里还有远远领先于此的东西，据报道，Sam 下周将前往华盛顿讨论 GPT 6.0，这绝对是惊天动地的。所以，我不相信中国真的赶上了。我认为这里有……

<details>
<summary>Original English</summary>

**Sacks**: Look, there's been a lot of violent agreement on this show so far. So, let me just make the counterargument. I think that both open source and closed source will be big winners in this. I think the market is huge and they each serve their purpose. What happened is with the introduction of committee K3, there was a little bit of a panic in which everybody said, "Oh my god, all the Chinese models have caught up and they're giving them away for free and they're going to destroy our leading American frontier labs and Anthropic and Open AI are running around saying, listen, we can't continue to invest billions of dollars if Chinese companies can just steal our weights." Right? So that's the argument that they're making that government officials are responding to. The truth of the matter is that look when Kimmy K3 first launched I was concerned about it because I was like oh has China caught up are they now able to produce a much cheaper Frontier model. Then the details started coming out. So Ben Thompson on his blog went through some of the cost numbers and it turns out that Kimmy K3 is not that much cheaper to run. There's not a significant cost advantage to it. So that was that's point number one. Point number two is that China has not caught up. It's true that Kimmy K3 scored really well on the arena battleground for front-end coding for web development, but that's just one test. That's just one dimension. There are areas where it scores really well, but there's lots of other areas where it doesn't score that well. So, it is not a clear advance or a clear catch-up to the leading American models. Moreover, you still have stuff in the labs by Anthropic and Open AAI that is way ahead of this and the reports are that Sam is going to Washington over the next week to go talk about GPT 6.0 which is blowing the doors off. So, I don't believe that China has really caught up. I think there's

</details>

**Speaker B**: Sam 要去见“爸爸”了，他会要些什么呢？我认为有一批不可思议的未发布模型正在酝酿中，我们需要让我们的马儿在这里奔跑，而不是用一堆不必要的繁文缛节来拖慢它们的脚步。如果我们做到这一点，我认为我们会没事的。我不相信中国已经赶上了。我仍然认为我们领先了 6 个月。然后关于这一点的最后一部分是，如果你看看营收，这是现实世界中实际使用情况的检验，Anthropic 和 OpenAI 的表现绝对是惊人的。他们绝对是我们见过的有规模的、增长最快的科技公司。Jason，你展示的这张图表据说显示了 Anthropic 的一个小挫折。听着，他们的内部预测是今年增长 10 倍，从 1000 万到 1 亿。我们现在处于年中，他们的年度经常性收入（ARR）已经超过了 7000 万。他们轻松就能达到 1 亿。我们并不真正知道这里出现的小波动是什么。我认为可能的一个原因是 OpenAI。如果你把 OpenAI 的图表叠加上去，他们在过去一个月里重新加速了。所以我认为，如果你把 OpenAI 加进来，

<details>
<summary>Original English</summary>

**Speaker B**: Sam's going to go see daddy and what is he going to ask for? I think there's incredible unreleased models in the pipeline and we need to let our horses run here and not slow them down with a bunch of unnecessary hoops and if we do that I think we're going to be just fine. I don't believe that China has caught up. I still think we are 6 months ahead. And then just the final point on this if you look at revenue which is the test of real usage in the real world anthropic and open AI are blowing the doors off. They are by far the fastest growing tech companies at scale that we've ever seen. Jason, you showed this chart that supposedly shows a hiccup in anthropic. Listen, their internal forecast was to 10x this year from 10 to 100. We're in the middle of the year. They're already over 70 billion of ARR. They're easily going to get to 100 billion. And we don't really know what this little blip is here. I think one thing it might be is that open AAI, if you superimpose the OpenAI chart on this, they have reacelerated over the past month. So I think that if you were to add Open AI,

</details>

**Speaker C**: Codex 非常棒。Codex 是……

<details>
<summary>Original English</summary>

**Speaker C**: Codex is excellent. Codex is

</details>

**Sacks**: Codex 确实非常棒，我认为他们正在抢占一点市场份额，而 Sam 正在外面发推说我们找回了魔力，并且他们上调了预测。我想他们原先预计年底的 ARR 会达到 6000 万，但我认为他们现在的预测更接近 7500 万。所以我的猜测是，如果你把 OpenAI 和 Anthropic 叠加在一起看，并基本可以说，姑且称之为美国的前沿模型双头垄断，你不会看到任何放缓。你没有看到任何波动。他们都在上调预测。而现实是，如果模型蒸馏……

<details>
<summary>Original English</summary>

**Sacks**: Codex is excellent and I think they're taking a little bit of share and Sam is out there tweeting that we've got our mojo back and they're taking their forecast up. I think they were expecting to end the year at 60 billion of ARR and I think they're forecasting more like 75 billion of exit ARR. So my guess is that if you were to superimpose open AI and anthropic and looked at them together and you were basically just to say that you know let's call it the frontier model duopoly in the US you do not see any slowdown you don't see any blip they're taking their forecasts up and the reality is that if distillation

</details>

<!-- chunk 5/12 -->

### AI巨头寻求政府保护的争议

**Speaker A**: 这种情况一直在发生，你知道的。我早在2025年1月就指出过DeepSeat的问题，所以这一整个时期以来它们都在呈指数级增长，因此我根本不相信这些家伙实际上受到了什么损害。我不认为它们需要政府的保护。我认为它们依然在指数级地增长。这就有点像——你知道在篮球里这叫什么吗？——当一个球员假摔，你知道的，你犯规了或者假摔之类的。

<details>
<summary>Original English</summary>

**Speaker A**: is going on it's been a thing for you know again I pointed it out back in January of 2025 with deep seat so it's been a thing this entire time that they've been growing exponentially so I just don't believe that these guys are actually suffering in any way. I don't think they need government protection. I think they're growing exponentially still. This is a little bit of a case of um you know what do you call it uh in basketball when a player flops you know that you did a foul flop or whatever.

</details>

**Speaker B**: 是的，这就是假摔。没错。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. It's a flop. Yeah.

</details>

**Speaker C**: 对，或者说你为了造进攻犯规，在接触后表现得极其夸张。你这就是在碰瓷，试图骗取犯规，然后你假摔，就是做那种像勒布朗（詹姆斯）一样的夸张动作。

<details>
<summary>Original English</summary>

**Speaker C**: Well, or you you basically act super dramatic after a foul in order to draw the charge. You're foul baiting when you're trying to get a foul and then you're flopping which is just making like an exaggerated thing like LeBron does

</details>

**Speaker D**: 没错，完全就是这样。这就是勒布朗式的动作。

<details>
<summary>Original English</summary>

**Speaker D**: and that's exa Yes. It's a LeBron

</details>

**Speaker A**: 这就是极其夸张的假摔，你知道的，这些家伙正试图造犯规。他们试图让政府介入。那么，他们为什么要这么做呢？因为他们现在正处于路演（招股推介）的中间阶段。而且 Chamath，关于你的观点，我确实认为他们面临着一个合理的问题：为什么你们随着时间推移不会被开源模型商品化？而对这个问题最好的回答，莫过于如果他们能诱使政府赋予他们一个受政府保护的双头垄断地位，那将是不可思议的。

<details>
<summary>Original English</summary>

**Speaker A**: it's a flare flop, you know, where these guys are trying to they're trying to draw the foul. They're trying to get the government to intervene. Now, why are they doing this? Because they're in the middle of road shows right now. And Chamas, to your point, I do think they get the legitimate question about why won't you be commoditized over time by open source? And by far the best response to that would be that if they can lure the government into giving them a government protected duopoly, then that would be incredible.

</details>

**Chamath**: 最好的回答就是你刚刚给出的那个。Anthropic 和 OpenAI 应该主导这一切，因为他们擅长这个，也就是说他们将要在技术栈上向上移动，进入应用层。

<details>
<summary>Original English</summary>

**Chamath**: The best answer is what you gave and anthropic and open AAI should own this because they're good at it, which is they're going to go up the stack to the application layer.

</details>

**Speaker A**: 嗯，他们其实已经这样做了。

<details>
<summary>Original English</summary>

**Speaker A**: Well, they already done

</details>

**Chamath**: 我知道，但他们现在的做法在某些情况下显得有点笨拙。

<details>
<summary>Original English</summary>

**Chamath**: I know, but they've done it in this way which is a little ham-handed in some cases,

</details>

**Speaker A**: 但他们在这方面非常出色。这些面向终端用户的应用程序做得非常好，他们就应该主导这块市场。而那应该成为他们给华尔街的答案，那就是：“伙计们，我们拥有最好的模型。我们最终会向上拓展技术栈。而且如果我是他们，我实际上会练习以下这套说辞：可能会有某个版本的模型我选择不发布，只留给我自己，而且我只会把它用在我自己的应用程序中。这样如何？”

<details>
<summary>Original English</summary>

**Speaker A**: but they're excellent at it. these enduser apps are really good and they should just own that. And that should be their answer to Wall Street, which is guys, we have the best model. We will eventually go up the stack. And if I were them, I'd actually practice the following answer. There may be a version of a model that I don't release and just keep for myself and I'll just use in my own applications. How about that?

</details>

**Speaker B**: 是啊。嗯，那将会是……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Well, that would be

</details>

**Speaker C**: 那才是真正的答案。但那是反竞争的。

<details>
<summary>Original English</summary>

**Speaker C**: that's the real answer. That's anti-competitive.

</details>

**Speaker A**: 不，这并不是。他们有权构建一个模型，选择不发布它，并将其留作己用。

<details>
<summary>Original English</summary>

**Speaker A**: This No, it's not. They're allowed to build a model and not release it and use it for themselves.

</details>

### 开源模型的崛起与企业困境

**Speaker E**: 等等。等一下。让我来回应这一点。在他们的客户看来，这将会是反竞争的。在政府眼中可能并非如此，但如果你作为客户正在使用他们——而且你是 Lovable（我跟他们聊过），然后他们付了大量的钱；或者你是 ElevenLabs，付给他们一大笔钱——然后他们说：“嘿，我们有了最新最好的模型。你们不能用，因为我们要和你们公司竞争。”那么他们就会停止使用，转而投入开源阵营。我来告诉你为什么，因为我认为在这个问题上你错了。我认为开源正迎来属于它的时刻。我和初创公司一起工作。它们全都在脱离这些闭源模型，转而使用开源模型，而且使用成本要低得多，因为许多任务根本不需要最顶尖的模型。它们可以使用上一代的模型，并且人们正把它们转移到本地。他们在自己托管这些模型。我认为有不为零的可能性，这将会破坏 Anthropic 和 OpenAI 的 IPO 计划。

<details>
<summary>Original English</summary>

**Speaker E**: Hold on. Hold on. Let me answer that. it it would be anti-competitive in the eyes of their customers. It might not be in the governments, but if you are using them as a customer and you're lovable, which I talked to, and they're paying a ton of money or you're 11 Labs and you're paying them a ton of money and they say, "Hey, we got our latest and greatest. You can't use it cuz we're going to compete with your company." They would stop using it and they go to open source. I'll tell you why so I think you're wrong on this issue. I think open source is having its moment. I work with startups. They are all moving off of these and they're using open source and they're using it at much cheaper rates because a lot of the jobs don't need the latest models. They can use these uh the last generations models and people are moving them local. They're hosting them themselves. This is I think a nonzero chance that this is going to derail anthropic and open eyes uh IPOs and

</details>

**Speaker F**: 他们会没事的。只要……他们就会没事的。

<details>
<summary>Original English</summary>

**Speaker F**: they're going to they're going to they're going to be fine. They're going to be fine as long as

</details>

**Speaker E**: 不，等一下。伙计们，让我说完。我正在阐述我的观点。给我闭嘴三十秒。我相信这会破坏他们的 IPO。我从头说起。这会破坏他们的 IPO，这会成为阻碍他们的逆风，因为我认为他们将面临巨大的利润空间压缩。我相信他们烧了那么多钱，以至于我认为他们会陷入陷阱。我认为这可能对他们来说是个陷阱。他们过度支出，他们没有同等的盈利能力，在账面上这是算不平的。而初创公司才是未来。初创公司最终是大型企业会去效仿的对象。我觉得你错了，Sacks。你接着说。[大喊] [笑声]

<details>
<summary>Original English</summary>

**Speaker E**: No, hold on. Let me finish guys. I'm making my point. Shut the [ __ ] up for 30 seconds. I believe that this is going to derail their IPOs. I'm taking it from the top. It's going to derail their IPOs. It's going to be headwinds against it because I think that they're going to have massive margin compression. I believe they're spending so much money that I think they're going to get caught in a trap. I think this could be a trap for them. They overspend. They don't have the same profitability and it doesn't pencil out. And startups are the future. The startups are what eventually the enterprise copies. I think you're wrong, Sax. Go ahead. [screaming] [laughter]

</details>

**Sacks**: 好的，我会回应的，不过先让你的嘴巴回应吧。请举手。

<details>
<summary>Original English</summary>

**Sacks**: Well, I'll come back, but let your mouth respond. Raise your hand.

</details>

**Speaker G**: 你错了。你完全错了。

<details>
<summary>Original English</summary>

**Speaker G**: You're wrong. You're totally wrong.

</details>

**Speaker H**: 我认为你错了。我认为他们（开源）已经赶上并能够处理 95% 的任务。这是一种疯狂的逆风。我并不是说 IPO 就此泡汤，但我认为他们的市值和面临的阻力即将到来。有不为零的可能性他们会被拖慢脚步。

<details>
<summary>Original English</summary>

**Speaker H**: I think you're wrong. I think they have caught up for 95% of the jobs. This is a crazy head. I'm not saying that the IPOs are off, but I think that their market caps and the headwinds are coming. There's a non-zero chance that they're going to get slowed down.

</details>

**Speaker I**: 我认为答案略有不同。并不是说 95% 最前沿尖端的任务每个人都能做，而是说 95% 的常规任务可以由许多不同的模型来完成。这才是真实的答案。而且这也没问题。顺便说一句……

<details>
<summary>Original English</summary>

**Speaker I**: I think the answer is slightly different. It's not that 95% of the bleeding edge tasks can be done by everybody. It's that 95% of the tasks can be done by many different models. That's the actual answer. And that's okay. And by the way,

</details>

**Speaker J**: Chamath 说的完全正确。我同意。

<details>
<summary>Original English</summary>

**Speaker J**: that's exactly right, Chimath. I agree.

</details>

### AI 公司的估值与竞争格局

**Chamath**: 对于 Anthropic 来说，这么说也是没问题的：“你知道吗，我拥有这种下一代级别的模型。我要去建立，比如说，一个生命科学项目，或者一个网络安全业务。”正如 Sacks 之前所言，随着时间的推移，那才是他们能够获取数万亿、数万亿美元企业价值的地方。因为我确实认为他们拥有出色的模型，他们有顶尖的工程师，并且他们保持着发展势头。但如果你要建立一种商业模式，试图将这个层面归结为拥有巨大的终极价值，我认为在数学逻辑上这是一个错误。就是这样。你无法做到这一点。开源必然会成为这些公司面临的阻力，特别是因为——因为他们所有最好的客户（我和他们谈过，不管是 Lovable 还是 11 Labs，或者是那些就在六个月前每季度还向他们支付数十万美元的初创公司），他们已经大举转向像 GLM-52 这样的模型，去打造他们自己的模型了。木已成舟（猫已经放出了袋子）。他们将会开始把大量客户流失给开源，而谷歌、AWS 和埃隆的云服务（Elon Web Services）将会托管这些模型。我怎么知道的？我每次做一项任务，我都在用 Plexity Computer。这不是付费合作什么的。这仅仅是因为它碰巧是我发现的最好的平台工具。我从 Grok、Neotron、GLM-52 开始，我也把它放入 Claude 中，结果是一样好甚至更好。换句话说，我甚至看不出这些模型之间有什么区别。

<details>
<summary>Original English</summary>

**Chamath**: It's also okay for Anthropic to say, you know what, I have this next generation class of model. I'm going to instantiate, I don't know, a life sciences program, a cyber security business. That's where they can capture as Saxs was saying before over time trillions and trillions of enterprise value because I do think they have excellent models and they have excellent engineers and they have momentum. But if you're going to build a business model that tries to ascribe this layer as having a lot of terminal value, I think that that is a mathematical mistake. That's it. You can't do it. Open source is going to be a spec a headwind to these companies specifically because because all of their best customers and I talked to them whether it's lovable or 11 labs or the startups that were spending hundreds of thousands of dollars with them every quarter just last you know six months ago they have all moved on mass GLM52 making their own models the cat's out of the bag they are going to start losing a lot of customers to open source and Google and AWS and Elon Web Services are going to host them. And how do I know this? Every time I do a job, I'm using Plexity Computer. Not not a paid partnership or anything. It just happens to be the best harness that I found. And I start with Grock, Neotron, GLM52, and I also put it into Claude and the results are as good or better. I in other words, I can't even tell the difference between these.

</details>

**Speaker K**: 让我们把 OpenAI 的数据叠加到 Anthropic 的数据之上，因为我认为这支撑了我试图阐明的观点。

<details>
<summary>Original English</summary>

**Speaker K**: Let's superimpose the the OpenAI numbers on top of the anthropic numbers because I think it supports the the point I'm trying to make.

</details>

**Speaker L**: 顺便说一下，这些都是估算值。这并不是完全来自这些公司的官方数据。只是想确保大家清楚这一点。

<details>
<summary>Original English</summary>

**Speaker L**: These are estimates, by the way. This is not like literally from the companies. Just want to make sure people know.

</details>

**Speaker K**: 所以根据这家公司的数据——我的意思是，谁知道他们是怎么得出这些数字的呢。我们不确定这些数据是否完全真实。他们基本上展示出 OpenAI 的运营数据，也就是年度经常性收入（ARR），从 5 月份的 330 亿美元上升到了 7 月份的 413 亿美元。所以他们正在经历加速增长。就像我说的，我的意思是，山姆（Sam Altman）在外面放话说他们找回了状态。他们即将迎来前所未有的最好的 12 个月预期。而且你看，Anthropic 依然在极速增长。我们在之前的一期节目中讨论过这个问题。年复一年永远保持 10 倍的增长在物理上是不可能的。你会耗尽算力。你会耗尽能源。你会耗尽一切。这根本没有——是的，这种事情根本没有办法做到。

<details>
<summary>Original English</summary>

**Speaker K**: So according to this company that I mean look, who knows how they derive this. We don't know that they're totally true. They're basically showing that OpenAI's run rate, which is ARR. It rose from 33 billion in May to 41.3 billion in July. So they're seeing acceleration. Like I said, I mean Sam is out there saying they got their mojo back. They're going to have their best 12 months forward looking ever. And look, Anthropic is still growing really fast. We've talked about this on a previous show. It's not physically possible to grow 10x year over year forever. You'll run out of compute. You'll run out of energy. You'll run out of everything. There's just no Yeah. There's just no way to do things.

</details>

**Speaker M**: 但是 Anthropic，我的意思是，听着，如果有人——如果在今年 1 月份有人说 Anthropic 到年中时收入将超过 700 亿美元，而他们目前是 100 亿美元，根本没人会说出这种话。你一定会说这是有史以来增长最快的科技公司。认为他们正面临失去整个商业帝国的风险的想法，这种迹象还未在数据中显现，这就是我试图表达的意思。此外，Chamath，回到你的观点，这不仅仅关乎模型。这也关乎平台（harness）。关乎连接器。关乎企业协议。你需要很多因素才能把这样的业务做大。而这种认为他们需要因为未来可能面临的竞争风险，而竞相寻求政府保护的观点，我认为简直就是不体面且令人作呕的。我是说，这可是有史以来最成功的科技公司啊，他们却跑去对政府说：“你们需要保护我们免受竞争对手的威胁。”真是好一个借口。

<details>
<summary>Original English</summary>

**Speaker M**: But anthropic, I mean, look, if any if anybody had if anybody had said Anthropic would be at over 70 billion in the midpoint of the year back in January and they're at 10 billion, nobody would have said it. You would have said this is the fastest growing tech company of all time. The idea that they're at risk of getting their entire franchise destroyed, it's not in the data yet is what I'm trying to say. And moreover, Jamas, to your point, it's not only about the model. It's also about the harness. It's about the connectors. It's about the enterprise agreements. There's a lot of things here that you need in order to grow a business like this. And you know, this idea that they need to race to get government protection because of a competitive risk that might happen in the future, I think is just kind of unseammly and gross. I mean, this is literally the most successful tech company of all time and they're racing to the government to basically say, "You need to protect us against our competitors." Great argument.

</details>

**Speaker N**: 不仅仅是防备我们的中国竞争对手，还有我们的美国竞争对手，以及我们潜在的未来竞争对手。

<details>
<summary>Original English</summary>

**Speaker N**: Not just our Chinese competitors, our American competitors, our potential future competitors.

</details>

**Speaker M**: 他们应该去雇佣莉娜·汗（Lina Khan）。好吧。坦白说，这真的很恶心。请让我举几个例子，因为我知道……

<details>
<summary>Original English</summary>

**Speaker M**: They should hire Lena Khan. Okay. And frankly, it's gross. And just let me give a couple of examples cuz I know

</details>

<!-- chunk 6/12 -->

### 开源模型与知识经济的商品化

**Sacks**: 人们对中国公司并没有太多同情心。这没关系。我不是在为中国公司辩护。我是在为那些需要能够使用公共领域内所有东西的美国开发者辩护。我来给你们举个例子。Ma Maratti（注：可能是某位高管或研究员），她的新模型，Thinking Machines（会思考的机器）。Thinking Machines。他们目前拥有美国最好的开源模型。你们知道它是怎么训练出来的吗？它是自举（bootstrapped）训练的。它是基于一个中国模型（Kimik 2.5 / Qwen 2.5）进行知识蒸馏而来的。现在，如果你们说那个中国模型是基于知识产权盗窃的，那么这个 Thinking Machines 算什么？它是一个衍生作品，而它所基于的模型正是 Anthropic 试图污名化为侵犯知识产权的模型。顺便说一句，目前没有任何证据证明这一点。没有经过任何取证程序。他们只是试图在这里一竿子打翻一船人，说现在那个模型已经被污染了。我再给你们举个例子。Cursor 推出了他们的新产品 Composer 2。他们能够使用 Kimik 2.5 和他们自己专有的代码数据对那个模型进行后训练。好吧，所以仔细想想这件事。他们从一个中国的开源模型开始，然后使用他们自己的数据，最终得出了一个新的衍生产品。这就是开源的运作方式。你拿走公共领域中的东西，你对其进行分叉（fork），然后把它变成你自己的东西。顺便说一下，一旦它进入了公共领域，它就不再是一个中国模型了。它是开放权重的，任何人都可以自由获取。它就是一个文件，好吗？你拿走那个文件，分叉它，然后将它运行在你自己的硬件上，在一家美国的数据中心里。没有数据包会被传回中国。没有任何数据会被传回中国。什么都没有传回中国。一家美国公司采用了公共领域中的开源贡献，将其转化为自己的东西，然后开发出了自己的模型。如果你说美国公司不能这么做，或者说这在某种程度上被知识产权盗窃污染了，你基本上就是在用一把匕首刺穿整个美国开源生态系统的心脏。而这正是 Anthropic 想要的结果，因为他们根本不希望有竞争对手存在。

<details>
<summary>Original English</summary>

**Sacks**: people don't have a lot of sympathy for Chinese companies. That's fine. I'm not defending Chinese companies. I'm defending American developers who need to be able to use everything in the public domain. And let me give you an example. Ma Maratti, her new model, thinking machines. Thinking machines. They currently have the best American open-source model. You know how it was trained? It was bootstrapped. It was distilled off a Chinese model, Kim K 2.5. Now, if you say that Chinese model is based on IP theft, what is thinky? It's a derivative work off a model that anthropic is trying to taint as being IP. By the way, there's been no evidence of this. There's no evidentiary process. They are simply trying to paint with a very broad brush here and say that now that model is tainted. Let me give you another example. So cursor rolled out its new product composer 2. They were able to post-train that model using Kimik 2.5 on their own proprietary coding data. Okay, so think about this. They started with a Chinese open- source model and then they used their own data and they came up with a new derivative product. This is the way that open source works. You take things that are in the public domain, you fork them, you make them your own. And by the way, once it's in the public domain, it's not a Chinese model anymore. It is open weights that are freely available to anyone. It's a file, okay? And you take that, you fork it, you run it on your own hardware in an American data center. No packets are going back to China. No data is going back to China. Nothing's going back to China. An American company has taken open- source contributions in the public domain, made it their own, and then developed their own model. And if you say that American companies can't do that or that somehow it's tainted with IP theft, you are basically going to put a dagger through the heart of the entire American open source ecosystem. And that is exactly what Anthropic wants because they do not want to have the competition.

</details>

**Jason**: Freeberg，也许你可以总结一下这里，然后我会表达我的观点。

<details>
<summary>Original English</summary>

**Jason**: Freeberg, maybe you can uh close this out here and then I'll put my

</details>

**Freeberg**: 我把视角拉远一点来说这件事。思考一下中国方面的战略。如果你回顾过去 50 年的全球经济，美国通过处于知识经济和事实上服务经济的核心，积累了如此多的价值。从这个意义上说，通过知识产权（IP）的发展，知识的发展，然后将一个比特转换为另一个比特，我们已经能够从中获取数万亿美元的 GDP。与此同时，我们将制造业外包，并在中国创造了一个沉睡的巨人，他们在那里拥有这种令人难以置信的制造能力。说到底，如果你思考人类技术演进和人类繁荣的进程，它在很大程度上是由我们将分子从一种形式转化为另一种形式，并尽可能使用最少的能量来完成这一过程的能力所驱动的。这就是所有技术最终都会导向的简单方程式。分子转换。用尽可能低的成本制造出你身后的那张漂亮的沙发。制造材料，制造半导体，制造所有这些东西。我们世界里的一切都是由分子转换驱动的。所以说到底，如果知识经济和服务经济受到压缩，就像 AI（特别是开源 AI）实际上把这种价值拉平了一样，因为所有那些价值现在都是开源的了。它是免费的，只需打开开关运行即可。那么，美国和西方经济的价值就在很大程度上被削弱了。剩下的就是分子经济的价值。也就是转换分子并使用能量来做到这一点的能力。当你把今天中国和美国的并置情况来看，我们在美国有 1 太瓦的电力生产能力，而他们正朝着拥有 8 太瓦的方向发展。我们有大约 100 亿平方英尺的制造产能。他们有 2000 亿平方英尺的制造产能。所以他们拥有 20 倍的制造产能，8 倍的电力生产，外加他们所有的其他能源来源。我认为这就是中国在未来一二十年甚至三十年进程中的长期游戏，通过压缩知识经济和服务经济，使其完全商品化，他们将握有全球经济中的所有价值，因为他们可以制造东西，而且因为拥有最多的电力生产，他们能比任何人都制造得更便宜。这是一个非常简单的准则，大体说明了我如何看待他们在这里试图布局的长期游戏。

<details>
<summary>Original English</summary>

**Freeberg**: I'll just zoom out for a second and I'll say it. Think about the strategy as well for China. If you think about the global economy of the last 50 years, the US has acrewed so much value by being at the core of the knowledge economy and effectively a services economy. And in that sense through the development of intellectual property of IP of knowledge and then the conversion of one bit to another bit we've been able to derive trillions of dollars in GDP. Meanwhile we outsourced manufacturing and created a sleeping giant in China where they have this incredible manufacturing capacity. And at the end of the day, if you think about the course of like human technology evolution and human prosperity, it's largely driven by our capacity to convert molecules from one form to another and use the least amount of energy possible to do that. That's that all of technology ultimately leads to that simple equation. Molecule conversion. Making that beautiful couch behind you at the lowest cost possible. Making materials, making semiconductors, making all this stuff. Everything in our world is driven by molecule conversion. So at the end of the day, if the knowledge economy and the services economy gets compressed, much like AI and open source AI in particular, effectively flattens that value because all of that value is now open source. It's free and it's simply a function of turning on a switch and running it. The value of the US and the western economy has been largely degraded. And what's left is the value of the molecule economy. the ability to convert molecules and use energy to do that. When you look at the juxtaposition of China versus the United States today, we have one terowatt of electricity production capacity in the US and they're on their way to having eight. We have about 10 billion square ft of manufacturing capacity. They have 200 billion square ft of manufacturing capacity. So they have 20x the manufacturing capacity, 8x the electricity production plus all of their other sources of energy. And I think that's the the long game for China over a decade, two, three decade process is by compressing the knowledge economy and the services economy, commoditizing it completely, they are left holding all the value in the global economy because they can make stuff and they can make it cheaper than anyone because they have the most electricity production. That's a very simple rubric for kind of how I look at the the long game that they're trying to play here.

</details>

**Jason**: 你认为他们是想把这个非常重要的领域商品化，就像他们对...所做的那样。

<details>
<summary>Original English</summary>

**Jason**: You believe they're trying to commoditize this very important space just like they did for

</details>

**Speaker A**: 全球汽车行业。

<details>
<summary>Original English</summary>

**Speaker A**: global cars,

</details>

**Freeberg**: 全球知识和全球服务。比特的创造和移动被商品化，剩下的就是电力的创造和分子的创造，在这两方面他们都拥有这种极难逾越的优势，这将使他们成为世界的核心依赖。我认为这才是这盘长远大棋的关键。

<details>
<summary>Original English</summary>

**Freeberg**: global knowledge and global services. The creation and movement of bits gets commoditized and what's left over is the creation of electricity and the creation of molecules both of which they have this very difficult to surmount advantage that's going to make them the core dependency for the world. That's what I think is kind of the long game here.

</details>

**Jason**: 顺便说一句，你要知道，这些数据来自《The Information》等地方的报道或者其他来源，或是泄露的数字，他们只是尝试据此制作图表。

<details>
<summary>Original English</summary>

**Jason**: And just so you know, this data comes from reports in places like the information or other sources or leak numbers and they try to just make charts based on it.

</details>

**Sachs**: 是的。另外顺便提一下，我自己也有信息来源。我跟这些公司的投资者交流过，我只是想告诉你，无论是 Anthropic 还是 OpenAI，他们目前都在上调他们的预期，上调他们的预测。所以我的意思是，听着，我认为在未来，开源抢占市场份额的情况可能会发生，这没问题。这是因为市场太大了，而开源总是会有市场的。因为开源更可控，更可定制，你可以拥有它，你获得了数据主权，你获得了控制权。但同时它也需要更多的工作量。所以这里有不同的使用场景，市场也有不同的细分部分。

<details>
<summary>Original English</summary>

**Sachs**: Yeah. And by the way, I you know, I have my own sources too. I've talked to investors in these companies and I'm just telling you that both Anthropic and Open AI are taking their estimates up right now, their forecasts up. So I mean look I think in the future it may be the case that open source takes share fine it's because the market's so big and there is always a market for open because open is more controllable it's more customizable you can own it you get the data sovereignty you get the sovereignty but it's also more work so there are different use cases there's different parts of the market

</details>

**Jason**: 这实际上非常有趣。Sachs 提到的“需要更多的工作量”那一点超级有意思。大概 3 到 6 个月前，要搭建这些系统还需要巨大的工作量。而现在，有如此多的中间商在构建框架体系，默认支持它，这个问题正在得到解决。但这绝对一直是开源项目面临的问题，那就是实施它需要耗费巨大的工作量。呃，如果你确实想在你的组织内部实施这个，请拨打 8090 试试软件工厂。使用促销代码 JCAL（笑声）在 8090 获取免费咨询。好吧。他们能得到免费咨询吗？

<details>
<summary>Original English</summary>

**Jason**: that's actually very interesting the the more work part there Sachs is super interesting like 3 to 6 months ago it was so much work to stand these up and Now there's so many intermediaries building the harnesses that default to it that that is getting worked out. But that has always been the issue with open source for sure is the amount of work it takes to implement. Uh if you do want to implement this inside of your organization, please make a call to 8090 and try the software factory. Use the promo code JAL [laughter] to get a free consultation at 8090. All right. Can they get a free consultation?

</details>

**Chamath**: 每个人都在为自己的利益说话。实际上大家都在自卖自夸，我想说这也包括 Anthropic 和 OpenAI 的投资者。很神奇的是，这些（投资者中）有多少人...

<details>
<summary>Original English</summary>

**Chamath**: Everyone's talking their books. Everyone's talking their books actually including I'd say the anthropic and uh open AAI investors. It's amazing how many of these

</details>

**Jason**: 两周前 Brad 参加了我们的节目，当时你也在那期节目里，Brad 就说，“让我来告诉你为什么事情会变成这样。” 他实际上紧紧抓着这个观点不放。

<details>
<summary>Original English</summary>

**Jason**: Brad was on the show two weeks ago when you on the episode Brad was LIKE LET ME TELL YOU WHY this is going to he's holding on he's holding on to this actually

</details>

**Chamath**: 他的态度就是...

<details>
<summary>Original English</summary>

**Chamath**: he's like

</details>

**Sachs**: 我实际上非常赞赏 Brad，因为我确实认为他在公共政策方面是客观的，或者说，考虑到他确实拥有所有这些公司，他已经做到了尽可能客观。但是，听着，我只想告诉你们，我看到很多人突然变成了对华鹰派，嚷嚷着我们需要阻止中国。我们阻止个什么呀，搞得好像他们真的是对华鹰派似的，明明每个人都想卖芯片赚钱。

<details>
<summary>Original English</summary>

**Sachs**: I actually give Brad a lot of credit because I do think that he's objective about public policy or as objective as you can be given that he does own all these companies. But look, let me just tell you that you know I see a lot of folks who are suddenly China hawks and saying we need to stop China. WE STOP LIKE THEY'RE CHINA HOGS. EVERYBODY WANTED TO SELL THEIR CHIPS.

</details>

**Jason**: 那么是不是应该先披露一下你是否在 Anthropic 的股东名单里？好吧。

<details>
<summary>Original English</summary>

**Jason**: How about disclosing first whether you're on the cap table of anthropic? Okay.

</details>

**Speaker B**: 绝对的。你们几个在这任何一家公司的股东名单上吗？

<details>
<summary>Original English</summary>

**Speaker B**: Absolutely. Are you guys on any of these cap tables?

</details>

**Jason**: 不，我不在。

<details>
<summary>Original English</summary>

**Jason**: No, I'm not.

</details>

**Speaker B**: 没有直接持股。

<details>
<summary>Original English</summary>

**Speaker B**: Not directly.

</details>

**Jason**: 对，没有直接持股。没错，是间接持有。也许获得了一点份额。你知道那是种什么感觉吗，Chamath？这就好比，你拿到了一手很棒的同花或顺子，然后你在心里默念：“千万不要发出成对的公牌。” Brad 就好像在喊：“别发成对的公牌！求你了，千万别发成对的公牌。”（笑声）好的。我们继续。

<details>
<summary>Original English</summary>

**Jason**: No, not directly. Yeah, that's indirectly. Maybe got a little access. You know what it's like, Chimat? It's like when you you got that great flush or straight and you're like, "Please don't pair the board." Brad's like, "DON'T PAIR THE BOARD. PLEASE don't pair the board." [laughter] All right. Here we go.

</details>

**Chamath**: 我热爱开源。我喜欢开源的 AI 技术。

<details>
<summary>Original English</summary>

**Chamath**: I love open source. I love I love this open source AI stuff.

</details>

**Speaker B**: 我觉得这太棒了。

<details>
<summary>Original English</summary>

**Speaker B**: I think it's so awesome.

</details>

**Chamath**: 它具有那种朋克摇滚般的价值。

<details>
<summary>Original English</summary>

**Chamath**: The value punk rock.

</details>

**Jason**: 就是这样，有了它可以做很多很多事情。这非常令人兴奋，而且太棒了。是的，Chamath 说得完全正确。大多数模型都能完成 95% 的任务。如果是这样的话，那大家就不必争相恐后地非要去抢最好的开源模型了。你只需要开源模型来完成你想要用 AI 完成的 95% 的事情就可以了。至于另外那 5%，你可以选择专业化、高价值的方案，或者你为此支付溢价。顺便说一句，如果你是一家大型企业，你需要为你的员工提供封装、支持以及所有这些额外的工具，那就买吧。

<details>
<summary>Original English</summary>

**Jason**: It's it's just like there's so much to be done with it. It's just exciting and awesome and yeah, Chimoff's point is exactly right. Most of the models can do 95% of the tasks. And if that's the case, then it's not like everyone needs to scramble to get the best open source model. You just need open source to do 95% of what you want to do with AI. And then the other 5% you get specialized or high value or you pay a premium. And by the way, if you're a big enterprise and you need to have rappers and support and all these other tools for your employees, buy

</details>

<!-- chunk 7/12 -->

### 播客闲聊与优惠码调侃

**Speaker A**: 无论是 Anthropic、OpenAI、Grok 还是 Gemini，只要确保你有一个好的合作伙伴就行，

<details>
<summary>Original English</summary>

**Speaker A**: Anthropic or OpenAI or Gro tools or Gemini, like just make sure you have a good partner,

</details>

**Speaker B**: 使用优惠码 Jal。你就能和你妈妈打个 Zoom 视频电话。好吧。[笑声] 在 Zoom 上和他来张自拍。

<details>
<summary>Original English</summary>

**Speaker B**: use the promo code Jal. You get a Zoom call with your mom. Okay. [laughter] A Zoom call with A ZOOM CALL WITH YOUR take a selfie with him on Zoom.

</details>

**Speaker C**: 我很抱歉。

<details>
<summary>Original English</summary>

**Speaker C**: I'm sorry.

</details>

**Speaker D**: 只要有人准备和 8090 签一份 1000 万美元的合同，你就能 [笑声] 让咱们四个人里的三个陪你打个 5 分钟的 Zoom 视频电话。

<details>
<summary>Original English</summary>

**Speaker D**: Anyone's going to sign a $10 million contract with 8090, you get [laughter] to have uh three of the four of us for a fiveminute Zoom call.

</details>

**Speaker E**: 绝对没问题。你能打 1000 万的电话。你可以猜猜播客上都有谁。

<details>
<summary>Original English</summary>

**Speaker E**: Absolutely. You get to call 10 million. You get to GUESS WHO'S ON THE POD.

</details>

**Speaker F**: 如果有人准备预购一百万美元的马铃薯种子，你也能获得 [笑声]

<details>
<summary>Original English</summary>

**Speaker F**: And anyone ready to make a pre-purchase on a million dollars of potato seed, you also get to have [laughter]

</details>

### Anthropic 达成 15 亿美元版权诉讼和解

**J Cal**: 使用优惠码 Sax Poo。没错。如果你想做客座主持，第一个给 Launch Fund 5 开出 2500 万美元支票的人，就能和你兄弟 J Cal 一起客串主持一期节目。好吧。本周简直是优惠促销之城。好了。来说说 Anthropic 的版权问题。开始了。Anthropic 在周一以 15 亿美元了结了他们的 AI 版权诉讼。Freedberg，这是美利坚合众国历史上最大的一笔版权和解案。这是第一起达成和解的重大 AI 训练诉讼案。后续还有很多类似的案子正在审理中。Anthropic 从盗版网站下载了 700 万本书来训练 Claude。单凭这一点，它可能构成犯罪，也可能不构成犯罪。法院对此做过一些裁决。他们之前曾裁定，针对受版权保护的书籍进行 AI 训练，在合理使用的范畴内是合法的，但未来还会有一些新的案例。所以，这次是和解。他们没有坚持打到底。律师拿走了 1.01 亿美元。作者每本书能拿到 3000 美元。和解协议覆盖了 50 万本书。到目前为止，91% 受影响的作者已经领取了他们的份额。还有大量其他作者正在赶来领钱的路上。这是你本期节目的第二次胜利狂欢。内容提供商作为一个群体，需要团结起来，一致争取他们的权利。《纽约时报》就是为了这个权利而战。

<details>
<summary>Original English</summary>

**J Cal**: use the promo code Sax Poo. Yes. And if you'd like to guest host, the first person to put a $25 million check into Launch Fund 5 gets to guest moderate an episode with your boy J Cal. All right. Uh Promo City this week. All right. Anthropic Copyrights. Here we go. Anthropic has settled their AI copyright lawsuit for 1.5 billion billy on Monday. Largest copyright settlement Freedberg in the history of the United States of America. First major AI training lawsuit to settle. There are many more in the pipeline. Anthropic downloaded 7 million books from pirated websites to train Claude. And that alone it may or may not be a crime. This has been adjudicated a little bit in the courts. They had ruled previously that AI on copyrighted books is legal under fair use, but there's going to be some future cases. So, this is a settlement. They didn't go to the bat. Lawyers getting 101 million. Authors get 3,000 a book. 500,000 books were covered in it. Thus far, 91% of the covered authors have claimed their share. Tons of other ones are on the way. And here's your second victory p fap of the episode. Content providers as a group need to get together and fight for their rights in unison. New York Times Met for the right to party.

</details>

**Speaker B**: 不。是为了获得报酬和生存的权利而战。[笑声] 退一步说，作为一个群体，要么给我们这些条件，要么就别索引我们的内容。他们正在干扰这些机构利用自身内容的能力。这极其不公平，那些杂志和报纸需要……那是什么？

<details>
<summary>Original English</summary>

**Speaker B**: No. Fight for the right to get paid and to survive. [laughter] TBT and say as a group either give us these terms or don't index us. They are interfering with their ability to leverage their own content. is profoundly unfair and those magazines and newspapers need to what's that?

</details>

**Speaker C**: 你会被碾压的。

<details>
<summary>Original English</summary>

**Speaker C**: You're going to get steamrolled.

</details>

**Speaker B**: 有这个可能。YouTube 就是一个很好的例子。这就是接下来会发生的事情。会达成一项和解，他们将能够索要他们的……Jal，我愿意下任何赌注来反驳你的预感。这就像是……

<details>
<summary>Original English</summary>

**Speaker B**: It's possible. YouTube is a great example. That's what's going to happen here. There'll be a settlement where they are going to be able to claim their I will bet any amount against your your your premonition here Jal. This is like

</details>

**Jal**: 我觉得我最大的赢家会是……

<details>
<summary>Original English</summary>

**Jal**: I am going to go with for my biggest winner for

</details>

**Jal**: 训练数据的所有者，比如《纽约时报》、Reddit、X（Twitter）、YouTube 等等。我认为我们在 2023 年学到的是，语言模型很快就开始走向同质化，而真正的价值将存在于……甚至它可能会变成大宗商品，开源可能会赢得最终的胜利。所以那时候，我认为赢家是那些拥有训练数据的人。

<details>
<summary>Original English</summary>

**Jal**: training data owners like the New York Times, Reddit X, Twitter, YouTube etc. I think what we learned in 2023 was that the language models are starting to hit parody very quickly and that the real value is going to be in and it may even become commodities and open source may win the day. So then I think the winner is folks who have the training data.

</details>

**Speaker B**: 你知道吗，这件事最有趣的地方就是看 Jason 对 Jason 自己言论的反应。你有没有做个我的画中画，就好像在说，“上啊 Jac，我们在这上面打过赌吗？我们打赌了吗？” 我不知道。他已经走了。

<details>
<summary>Original English</summary>

**Speaker B**: You know the best thing about this is watching Jason's reaction to Jason. Did you do a picture and picture of me just be like go Jac did we make a bet here? Did we make a bet? I don't know. He's gone.

</details>

### AI 公司的伪善与双标

**Speaker C**: 嗯，实际上，这个……我不认为这次和解能完全证明你想让它证明的东西。Jal，

<details>
<summary>Original English</summary>

**Speaker C**: Well, actually, this I'm this settlement I don't think quite proves exactly what you want it to prove. Jal,

</details>

**Jal**: 你说吧。

<details>
<summary>Original English</summary>

**Jal**: go ahead.

</details>

**Speaker C**: 解释一下。我能、我能在这里说点细微的差别吗？

<details>
<summary>Original English</summary>

**Speaker C**: Explain. Can I can I make a nuance here?

</details>

**Jal**: 当然。当然。

<details>
<summary>Original English</summary>

**Jal**: Of course. Of course.

</details>

**Speaker C**: 所以，好吧。听着，你要知道，显然我不是 Anthropic 的狂热粉丝。我认为他们为了自己的监管俘获目的，可能会摧毁整个生态系统。但是，让我们对这起判决究竟是什么、不是什么保持非常清晰的认识。[笑声] 我们就明确一点，随时可以展示，Daria。

<details>
<summary>Original English</summary>

**Speaker C**: So, okay. Look, and you know, obviously I'm not a huge fan of anthropics. I think they're potentially destroying the whole ecosystem for their own purposes of regulatory capture. But let's just be very clear about [laughter] what Let's just be very clear about show anytime, Daria.

</details>

**Speaker A**: 是的，让我们对这个判决到底是怎么回事保持清醒。所以，好吧，Anthropic 做的是，他们从 LibGen 盗版了所有这些书，并在上面训练了模型。他们惹上麻烦的原因，是因为他们基本上拿了偷来的书。他们甚至连一本正版书都没买过。但是，如果他们哪怕只是为每本书支付了一份正版费用，他们就不可能被钉在盗版的耻辱柱上。他们原本有可能被纳入合理使用的范畴。据我了解，Jal，目前法院还在对合理使用进行诉讼，但这本来会是他们的辩护理由。所以，他们被判处这 15 亿美元的罚款，原因在于他们连买一本正版的钱都不愿意出。Anthropic 的立场，同样也是 OpenAI 的立场，仍然是：只要他们买了一份正版，他们就应该能够以合理使用为由，在所有这些书上进行训练。而这个问题目前还没有定论。现在你应该能看出，他们在这一观点上的彻底虚伪，尤其是相对于前一个问题而言——也就是，他们认为自己有权在世界上每一个创作者的作品上进行训练。你要知道，我想只要他们买了一份副本，无论那些创作者的意愿如何，不管创作者喜不喜欢。他们认为，基于合理使用原则来训练模型并推导出自己的权重，这就是合理使用。然而，他们又说，有一种内容是你绝对不能用来训练的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Let's just be very clear about what this judgment was and was not. So, okay, what Anthropic did is they pirated all these books from LibGen and they trained on them. And the reason why they got in trouble is cuz they basically took stolen books. They didn't even pay for one copy of them. But if they had paid for just one copy of each book, they could not have been nailed for piracy. they would have been potentially under fair use, which I understand Jal is still being litigated in the courts, but that would have been their defense. So, the reason why they got nailed with this $ 1.5 billion judgment is they wouldn't even buy one copy. It is still Anthropic's position and it's OpenAI's position that they should be able to train on all these books under fair use if they buy one copy. And that issue has not been resolved yet. Now you should be able to see the total hypocrisy of their point of view relative to the previous issue which is they believe they should be able to train on every creator's output in the world. You know as long as I guess they bought one copy of it against the will of those creators whether those creators like it or not. They believe it is fair use to train their models and derive their own weights based on fair use. However, they say that the one type of content that you should never be able to train on is 

</details>

**Speaker C**: 那就是他们自己的输出结果。这正是他们目前的立场。这完全是伪善。实际上，如果你回头看看 Anthropic 二月份发表的那篇博客文章，他们在那里第一次定义了“工业级蒸馏攻击”（industrial scale distillation attacks）这个概念，这个词是他们生造出来的。这就很让人担心，政府政策制定者并不明白，这一切都是 Anthropic 运营策略的一部分。在 Anthropic 写那篇博客之前，没有人把“蒸馏”和“攻击”这两个词连在一起用过。“模型蒸馏”本来只是一个行业标准做法。但后来 Anthropic 发明了“工业级蒸馏攻击”这个概念。不管怎么说，如果你去读读那篇博客，搜索一下“知识产权盗窃”（IP theft）这个词，里面根本没有。Anthropic 没有声称……尽管他们试图创造这个新概念，并把这种工业级蒸馏攻击的想法打造成一个品牌，但他们没有胆量去声称这就是知识产权盗窃。

<details>
<summary>Original English</summary>

**Speaker C**: their output. That is currently their position. It's completely hypocritical. And actually, if you go back to anthropics blog post in February where they defined this concept of industrial scale dissolation attacks for the first time, they coined that expression. And this is, you know, I worry that people in the government policy makers don't understand that this is all part of a anthropic op. No one used the terms distillation and attack together until Anthropic wrote that blog post. Distillation was simply an industry standard practice. But then Anthropic coined this idea of industrial scale dissolation attacks. In any event, if you go to that blog post, search for the words IP theft. It's not in there. Anthropic did not claim even though they were trying to coin this new concept and brand this idea of industrial scale dissolation attacks. They did not have the hutzbah to claim that it was IP theft.

</details>

**Speaker B**: 他们的胆量、伪善、那种肆无忌惮的态度，居然声称这就是知识产权盗窃。为什么？因为他们坚持认为，在全世界的所有输出上训练他们的模型是他们的权利，即使创作者不愿意。知识产权只保护“我们”，不保护“你们”。

<details>
<summary>Original English</summary>

**Speaker B**: The coahjones the hypocrisy the kutzbah to claim that it was IP theft. Why? Because they maintain that it is their right to train their models on all the world's output even if the creators don't want them to. IP for we but not for thee.

</details>

**Speaker C**: 完全正确。所以，Jal，我甚至不想讨论你在合理使用问题上是对还是错。也许你是对的，我不知道。好吧。但我想说的是这种伪善。他们自己也从未声称中国公司的做法是知识产权盗窃。他们试图主张的是，这是一个国家安全威胁，因为可能发生的情况是，这些中国公司会利用他们进行模型蒸馏，创建自己的模型，而这些模型将没有安全护栏。所以他们提出的是一种不同性质的论点。那个论点从未……不过那个论点从未在政策制定者那里获得认可，因为我认为他们能看出来，是的，护栏很重要，但是，你知道，它一直没有真正获得认可，直到 Anthropic 开始声称，“哦，这是知识产权盗窃”。但他们不愿意在公开场合提出这个论点，因为他们知道这会毁掉他们目前正在进行的所有关于合理使用的诉讼。正如 Jimoth 你提到的，《纽约时报》目前正在起诉 OpenAI，理由基本上就是发生了工业级的蒸馏攻击。我是说，OpenAI 跑到《纽约时报》的网站上，使用爬虫，以人类无法企及的规模抓取了他们所有的信息，然后他们将其用作训练数据，实际上就是逆向工程了模型的权重。所以我的观点是，连 Anthropic 和 OpenAI 都不愿意公开承认中国正在做的事情是知识产权盗窃，因为他们自己也在做同样的事情。这完全是伪善的，我认为政策制定者不应该提出这些公司自己都不愿意提出的论点，因为他们清楚自己会输掉所有这些法庭官司。

<details>
<summary>Original English</summary>

**Speaker C**: Exactly. So, so Jal, I don't even want to get into whether you're right or not on the fair use question. Maybe you are right. I don't know. Okay. But my point is about the hypocrisy and they themselves never claimed that this was IP theft by the Chinese companies. What they tried to claim was that it was a national security threat because what would happen is these Chinese companies would distill off them, create their own models, and those models would not have guard rails. So they were making a different kind of of argument. That argument never that argument though never found purchase with policy makers because I think that they could see that yeah look guardrails are important but you know it never really found purchase until anthropic started claiming oh this is IP theft but they have not been willing to make that argument publicly because they know that it would poison all of their fur use lawsuits that are happening. And Jimoth, like you mentioned, the New York Times is currently suing Open AI for basically a industrial scale distillation attack. I mean, Open AAI went on the New York Times website, used scrapers, slurped up all of their information at a scale that no human could achieve, and then they used that as training data and reverse engineered the model weights effectively. So my point is that even Anthropic and Open AAI won't publicly admit that what China is doing is IP theft because they are doing it themselves. It's totally hypocritical and I don't think policy makers should be making arguments that these companies themselves won't make because they know that they will lose all these court cases.

</details>

**Jal**: Freedberg，对于目前仍在审理的这件事，正如我们讨论过的那样，你有什么想法吗？这里有 150 起重大案件。《纽约时报》起诉音乐产业就是其中之一。

<details>
<summary>Original English</summary>

**Jal**: Freeberg, any thoughts here on um and obviously this is still being litigated as we've discussed. It's 150 major cases. New York Times is one of the music industry.

</details>

### AI 时代的内容壁垒与商业模式

**Freedberg**: 假设你写了这本书。好吧。

<details>
<summary>Original English</summary>

**Freedberg**: So you write this book. Okay.

</details>

**Speaker B**: 比如在哈珀柯林斯出版。

<details>
<summary>Original English</summary>

**Speaker B**: Harper Collins

</details>

**Freedberg**: 然后你选择不把它提交给 AI 训练，因为有限制条款。你把它封闭起来。没人能读到你的书。

<details>
<summary>Original English</summary>

**Freedberg**: and you opt to not submit it to AI because there's a restrict. You keep it closed. No one can read your book.

</details>

**Speaker B**: 我们在 Google 搜索时代就是这么做的。你不让它出现在 Google 上。

<details>
<summary>Original English</summary>

**Speaker B**: We did for Google search. You can't be on Google.

</details>

**Freedberg**: 没人能读到你的书。你不让任何人读你的书。如果你想读书，你就得为你的书买单。

<details>
<summary>Original English</summary>

**Freedberg**: No one can read your book. You're not letting anyone read your book. you want to pay for your book if you want to read it

</details>

**Speaker B**: 10 块钱。

<details>
<summary>Original English</summary>

**Speaker B**: 10 bucks

</details>

**Freedberg**: 然后某人花了 30 美元买了这本伟大的美国小说，他们读完了它，接着他们写了一篇书评 [笑声]，并且他们把书评发表在……

<details>
<summary>Original English</summary>

**Freedberg**: and someone pays $30 for Genule the great American novel and they read it and then they write a review [laughter] and they publish their review on the

</details>

<!-- chunk 8/12 -->

### AI 训练数据与版权问题

**Speaker A**: 现在互联网上，如果评论家讨论并描述了你的书，然后这篇评论被 AI 引擎的网络爬虫抓取，AI 引擎从中学习了关于你的书的内容。那么，当有人在 AI 引擎中询问关于你的书的问题时，AI 引擎生成了一些评论，你是否觉得你的版权在某种意义上受到了侵犯？嗯……

<details>
<summary>Original English</summary>

**Speaker A**: now on the internet the reviewer talks about your book and describes your book gets webcrolled by an AI engine and the AI engine learns from that learns about your book and now there's some commentary made about your book when someone asks a question about your book in the AI engine do you feel like your copyright was violated in that sense Um,

</details>

**Friedberg**: AI 其实并没有摄取你的书，它摄取的是关于你书的元数据。它摄取的是关于你书的评论，以及第三方对你书的分析。而所有这些内容都是公开在互联网上的。它不仅仅是复制了这些内容，而是用它们来学习关于你的书的信息。

<details>
<summary>Original English</summary>

**Friedberg**: so the book the AI never ingested your book. It ingested metadata about your book. It ingested reviews about your book. It ingested third party analysis about your book. All of which was on the open internet. And it didn't just copy that stuff, but it used it to learn about your book.

</details>

**Jason**: 所以你的意思是，这 1500 条关于《天使投资人：如何投资科技明星，一位将 10 万变 1 亿的天使投资人的永恒建议》（笑声）的评论，然后会成为 AI 的基础。所以我想我必须得接受这个事实。但像这种，你知道的，这本“雄辩而张扬的天使投资蓝图”，那条经过认证的评论……是的，我会觉得这没问题。

<details>
<summary>Original English</summary>

**Jason**: So you're saying these 1500 reviews for Angel, how to invest in technology stars, timeless advice from an angel investor turned 100,000 into 100 million. [laughter] These reviews would then be the basis of the AI. So I guess I would have to be okay. But this like, you know, this eloquently brash blueprint for angel investing, that verified uh review. Yes, I would be fine with that

</details>

**Speaker B**: 里面有五星好评。

<details>
<summary>Original English</summary>

**Speaker B**: fivestar review being in there.

</details>

**Jason**: 真的吗？

<details>
<summary>Original English</summary>

**Jason**: Really?

</details>

**Speaker B**: 你现在对上面这些一无所知了。（笑声）有 1498 条评论不是你写的吧？还有 3 条。呃，其实，我会告诉你一个秘密。当你们真的被要求写一本书，或者你们中有人有能力完成一本书时……是的，因为我已经 97 岁了，住在……

<details>
<summary>Original English</summary>

**Speaker B**: You now have no knowledge. You now have no knowledge of the above [laughter] 1498 reviews did you not write? Three. Uh, actually, I'll tell you the secret. When you guys actually get asked to write a book or any of you have the capability of completing a book. Yeah, because I because I'm 97 years old living in the

</details>

**Speaker C**: 你在 2017 年用了什么 AI 智能体，或者用了什么机器人？（笑声）

<details>
<summary>Original English</summary>

**Speaker C**: What AI agent did have [laughter] you used to what bot what bot did you use in 2017?

</details>

**Speaker D**: 现在我们知道他把那个他自己建的愚蠢的开源 AI 垃圾炮口对准哪里了。（笑声）

<details>
<summary>Original English</summary>

**Speaker D**: Now we know where he pointed that stupid open source AI slop cannon that he's built. [laughter]

</details>

**Friedberg**: 我也验证了购买记录。

<details>
<summary>Original English</summary>

**Friedberg**: I verified the purchase too.

</details>

**Jason**: Friedberg，（笑声）你说的很有道理。你提出了一个……哦，在那里。Jennifer，伟大的美国小说。关于掌控野心、建立韧性以及在工作与创新等人生方面取得胜利的实用智慧。

<details>
<summary>Original English</summary>

**Jason**: Freeberg, [laughter] you make a great point. You make a Oh, there it is. Jennifer, great American novel. Practical wisdom for mastering ambition, building resilience and winning at life work and innovation.

</details>

**Speaker B**: 掌握美德信号，掌握美德（笑声）信号。

<details>
<summary>Original English</summary>

**Speaker B**: Master virtue signaling master virtue [laughter] signaling.

</details>

**Speaker C**: 难以置信。难以置信。

<details>
<summary>Original English</summary>

**Speaker C**: Incredible. Incredible.

</details>

**Friedberg**: 那很美。那真的很美。但是 JL（Jason），我的观点是：知识是无法被封锁的，它是扩散的。所以版权的形式是非常清晰的。判例法和版权法非常明确：我不能从你的书里提取文字，重新印刷，然后声称这是我自己的作品。那是侵犯版权。但是，我对你书的阅读，我对关于你书的评论的阅读，以及由你的书引发的知识的扩散，最终会导致将知识抽象转化为某人可能会阅读的新输出。而且我认为，我们不太可能发现自己处于这样一个境地：即数字化传输、数字化处理并转化为其他内容的知识，最终会构成侵犯版权。

<details>
<summary>Original English</summary>

**Friedberg**: That's beautiful. That is beautiful. But JL, I mean, this is my point. Knowledge can't be contained. It's diffuse. And so the form of copyright is very clear. The case law and copyright's very clear. I cannot lift text out of your book, reprint it, and claim it as my own. That is a violation of copyright. But my reading of your book, my reading of the reviews of your book, the diffusion of the knowledge that arises from your book, that is ultimately going to lead to some abstract transformation of knowledge into a new output that someone might read. And I think it is very unlikely that we will find ourselves in a place where the idea that knowledge transferred digitally, processed digitally, and turned into other content is going to end up violating copyright in

</details>

**Jason**: 我理解你的立场。总有变通的办法。显然，我们一直都有缩写本（Cliff Notes），对吧？所以，如果一本书足够好，有人就可以写出它的缩写本。你无法阻止这种事发生。这里有一个分四部分的测试。我们在播客里讨论这事已经三年了。我想说的是，美国公司如果正在构建这些模型，应该拿出他们 10% 的收入，高调地进行现金赔偿并达成和解。而这正是正在发生的事情。如果你是一个版权所有者，你应该研究一下音乐产业是怎么做的。他们就像疯狗一样，会拼死抗争，把你拖在法庭上，直到你屈服并达成和解，同意进行授权；然后这会给他们提供判例法和和解协议，以便去找下一个人、再下一个人，这也就是为什么他们能够成功捍卫版权的原因。然后，如果你在和我竞争，那就会成为问题。所以，如果你只是问“他的书是关于什么的”、“大家对它有什么看法”、“最精彩的部分是什么”，而这些信息来自评论，那好，很合理。问题在于，而且我会和你们分享，现在还有一些其他的诉讼正在法院审理。正如 Chamath（Shimoth）所说，当他们进入应用层面并使用这些内容时，应用层将会成为问题。这里有一个重大的法庭案件。显然你知道其中的一些，但现在有了其他的案件。有音乐版权案件，还有《纽约时报》的案件。其中比较有趣的一个是 Thomson Reuters 诉 Ross 案。这是一起关于 AI 训练侵犯版权的最终判决案件。有一家名为 Westlaw 的公司，他们类似于 LexisNexis，人们一直试图声称他们可以利用像 Westlaw 这样的输出进行模型训练。如果你和我处于同一行业，这在版权法中是有特殊地位的，因为你侵犯了我使用我自己版权的能力。而你的论点，我认为 Friedberg（Fraber）是站得住脚的，那就是这不会阻止人们去买书。但是，一旦你实际上与我构成了直接竞争，这些事情就会出问题。这也是为什么我认为音乐行业会赢，以及其他一些领域也会赢的原因。但听着，这是……

<details>
<summary>Original English</summary>

**Jason**: I understand your position. There are workarounds. Obviously, we've always had cliff notes, right? So, if a book became good enough, somebody could write the cliff notes of it. You can't stop that. There's a four-part test for this. We we've talked about this for three years here on the pod. What I'd say is American companies should take 10% of their revenue, if they're building these models, and do splashy cashy and do settlements. And that's exactly what's happening. If you're a copyright owner, you should study what the music industry does. They are raid dogs and they will fight tooth and nail and keep you in the courts until you submit and make a settlement and agree that you're licensing it and then that gives them that case law and that settlement to go to the next person and the next person and the next person and that's why they've been able to successfully defend it and then if you're competing with me that becomes the issue. So if you said hey what's his book about and what do people think about it what are the best parts of it and that comes from the reviews okay fine fair enough. The problem is and I and I'll I'll share with you there's been some other lawsuits here that are making the way through courts. What's going to be the problem is the application level layer that you talked about Shimoth as they go into the application layer and they use this. There's a there's a big court case here. Obviously you know about some of these but there are now other cases. There are music cases. There's a New York Times case. The one that's kind of interesting is Thompson Reuters versus Ross. This is a uh final judgment on AI uh training copyright. There's a company called Weslaw. They're like Lexus Nexus and people have been trying to claim that they can train on the outputs of something like uh Westlaw. And when you're in the same business as me that has a special place in copyright law because I have you're you're infringing on my ability to use my copyright. And your argument I think Fraber holds up that it wouldn't be it wouldn't stop somebody from buying the book. But the second you are actually competing with me like directly that's when these things have problems. And that's why I think the music industry is going to win and and some other places are going to win. But listen, this is

</details>

**Chamath**: 这是一个全新的领域。这些诉讼属于全新领域，而知识产权法实际上还没有相应的细微界定。

<details>
<summary>Original English</summary>

**Chamath**: brand new territory. These lawsuits are brand new territory and IP law does not actually have the nuance yet.

</details>

**Jason**: 所以作为一个社会，我们将不得不在“什么是公平的”这个问题上做出决定。我建议，就像我们上周讨论过的自律组织一样，所有的 AI 公司应该联合起来，拿出你们 10% 的收入放进一个资金池里，持续支付给相关人员并获得他们的许可，这样你就可以获得内容的更新，从而获取下一本书，获取下一篇《纽约时报》的报道、下一篇路透社的报道。

<details>
<summary>Original English</summary>

**Jason**: So we're going to as a society have to make a decision here on what is fair. I suggest just like the self-regulatory group that we talked about last week, all the AI companies should get together, take 10% of your revenue, put it in a pool, and keep paying the people and getting permission from them so you can get updates on the content so you get the next book so you get the next New York Times story, the next Reuters story.

</details>

### 合理使用与商业欺诈之争

**Chamath**: 我告诉你，10% 是无法满足那些“疯狗”的。他们会要求 100%。现在，JK（Jason），让我问你一个问题。是的。考虑到“合理使用（fair use）”原则尚未成为定论，考虑到 Anthropic 和 OpenAI 卷入了针对资金雄厚的内容创作者和这些社区的巨额诉讼，且结果未卜，事关数十亿美元，甚至可能危及他们的整个产品。你是否认为，他们主张“违背创作者意愿提取内容属于知识产权盗窃”，可能犯了一个致命的错误？你明白我的意思吗？

<details>
<summary>Original English</summary>

**Chamath**: 10% is not going to satisfy the rabbit dogs, let me tell you. They're going to go for 100%. Now, JK, let me here's a question I want to ask you. Yes. Given that the fair use doctrine is not a decided matter yet, given that anthropic and open AI are embroiled in huge lawsuits against very well financed content creators and those communities and the outcome is indeterminate and there's billions of dollars at stake, maybe even their entire product at stake. Do you think that they have potentially made a fatal mistake by arguing that distilling content against the wishes of its creator is IP theft? Do you see what I'm saying?

</details>

**Jason**: 是的。

<details>
<summary>Original English</summary>

**Jason**: Yes.

</details>

**Chamath**: 就像，这是否可能是一个致命的错误？看，他们本来可以这么做。

<details>
<summary>Original English</summary>

**Chamath**: Like, is this potentially a fatal mistake? See, here's what they could have done.

</details>

**Jason**: 嗯，你可以把这个问题提交给最高法院，然后你说，“嘿，听着。”

<details>
<summary>Original English</summary>

**Jason**: Well, you would bring that to the Supreme Court and you say, "Hey, listen."

</details>

**Chamath**: 但他们本来可以这么做的。Anthropic 本可以这样说：“听着，我们发现有中国公司正在创建虚假账户，并使用代理基本上在违反我们服务条款的情况下使用我们的产品。”现在，使用这些模型输出并不是知识产权盗窃，因为这是合理使用。然而，这些人大量建立账户并在身份上撒谎，这是一种欺骗性的商业行为。因此，他们从事的是欺骗性商业行为。我们将尽一切可能去阻止，但我们也希望政府能协助制止这种行为。不过，我们没有说任何关于知识产权盗窃的事。

<details>
<summary>Original English</summary>

**Chamath**: But here's what they could have done. What Anthropic could have done is they could have said, "Listen, we have these Chinese companies are creating fake accounts and they're using proxies to basically use our product in violation of our terms of service." Now, using those model outputs is not IP theft because it's fair use. However, it's a deceptive business practice for these guys to lie about who they are when they set up accounts at scale. And so, they're engaged in a deceptive business practice. and we're going to do everything we can to stop that, but we'd like the government's help in stopping that, too. However, we not we're not saying anything about IP theft.

</details>

**Jason**: 对。

<details>
<summary>Original English</summary>

**Jason**: Yeah.

</details>

**Chamath**: 这难道不是一个更加细致入微的策略吗？当然，因为我认为他们在这里正处于搬起石头砸自己脚的边缘。

<details>
<summary>Original English</summary>

**Chamath**: Wouldn't that be the more nuanced approach? Of course, because I think that they're on the verge of being hoisted on their own petard here.

</details>

**Jason**: 是的。我的意思是，这是一个“自我打脸”（self-own），我想孩子们管这叫自我打脸，对吧？就像你实际上……这简直是经典的自我打脸。你也知道，在大多数这类案件中，最终都会达成和解。所以再说一次，如果你看看音乐行业、报纸、杂志，以及一些作家，他们往往非常软弱。现在出现了一种新趋势，Friedberg，很多内容提供商对 Google 说，把我们从索引中移除，因为 Google 有一个机器人，它不仅进行 Google 爬虫抓取，还进行 AI 爬虫抓取。行业现在的诉求是，嘿，把这两者分开。我想出现在 Google 搜索中，但我不想被收录到 AI 里。所以人们现在会说，嘿，我们会把你从索引中移除。这一点 Rupert Murdoch 做对了。如果所有的报纸集体表示：“不要索引我们，Google。我们拒绝被索引”，那就会迫使 Google 坐到谈判桌前，付给他们版税，并为能够索引他们支付一些钱。

<details>
<summary>Original English</summary>

**Jason**: Yeah. I mean, it's a cell I think that kids call it a cell phone, right? Like you basically it's just a classic cell phone. And you know, in most of these cases, settlements happen. So again, if you just look at the music industry, the newspapers, the magazines, and some of those folks and book authors, they've tend to be very meek. There's a new trend happening now, Friedberg, they're a lot of content providers are saying to Google, take us out of the index because Google has one bot and that bot does the Google crawl and that bot also does the AI crawl. And what the industry is saying is, hey, split that up. I want to be in Google, but I don't want to be indexed in AI. So people are now saying, hey, we'll take you out of the index. which Rupert Murdo got right. If all the newspapers said collectively, "Do not index us, Google. We're no indexed, that would have made Google come to the table and give them a royalty and give them some money for being indexed."

</details>

**Speaker B**: 我那么做过，老兄。发生过一笔交易，但并没有像你描述的那样发展。

<details>
<summary>Original English</summary>

**Speaker B**: I did that, dude. There was a there was a deal that happened, but it didn't it didn't go the way you're describing.

</details>

**Jason**: 好吧，因为他们没有……

<details>
<summary>Original English</summary>

**Jason**: Well, cuz they didn't

</details>

<!-- chunk 9/12 -->

### 关于内容版权与监管的和解讨论

**Speaker A**: （我们）需要结成统一战线。现在，我认为……

<details>
<summary>Original English</summary>

**Speaker A**: have a united front. Now, I think

</details>

**Speaker B**: 这些家伙想要、他们想要谷歌的用户群。所以，他们最终达成了一项协议，在这个协议中，他们设置了类似付费墙这种排他性规则，而另一方面，你可以展示一定数量的免费文章。这其中有一个完整的协商和解过程。不过，我说的甚至是在更早之前，也就是第一次建立索引发生的时候。但这里是，你知道，我、我、我认为我们正处于在这里达成某种类型和解的边缘。呃，并且我认为这对于美国在这一领域发挥领导作用是一件好事，因为你确实希望继续获得这些。但是所有这些内容公司，他们都应该互相会面，比如音乐产业、纽约时报，他们所有人都应该联合起来，阻止他们的内容在未经允许的情况下被使用，并且防止（AI公司）与他们竞争。这就是我的观点。你知道，只有当双方都能达成一致时，你才能达成和解。而且在我看来，如果你是这些内容创作者游说团体中的一员，并且你看到 Anthropic 刚刚告诉政府，未经创作者同意对其产出进行模型训练就是知识产权盗窃。

<details>
<summary>Original English</summary>

**Speaker B**: these guys wanted they wanted Google's user base. So, they ended up doing a deal where they had this like payw wall like exclusion rule whereas like you could show a certain number of free articles. There was a whole negotiated settlement. Well, I'm talking even long before that when the first index happened. But here's I you know I I I think we are on the cusp of a some type of a settlement getting done here. Uh and I think that would be good for America to take a leadership position in that because you do want to keep getting that. But all of these content companies, they should be meeting with each other, the music industry, the New York Times, all of them to stop their content from getting used without their permission and from competing with them. That's my point. You know, you you only get a settlement when both sides can agree. And it seems to me that if you're one of these content creator lobbies and you see that Anthropic has just told the government that training on a creator's output without their consent is IP theft.

</details>

**Speaker C**: 是的。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah.

</details>

**Speaker B**: 他们现在基本上已经承认了他们的整个产品都是偷来的。而在我看来，为什么内容创作者现在不主张他们有权拥有 Anthropic 100% 的收入呢？在我看来，这可能做得有点太过火了，你知道，他们非常擅长监管俘获（regulatory capture）。他们非常擅长提出这些论点并让政府介入以制定新的法规来保护他们。但我怀疑这是否有点聪明反被聪明误了。再说一次，如果他们只是换一种略微不同的方式来定位它，如果他们说：“看，这些中国公司正在创建虚假账户。这是一种欺骗性的商业行为。我们不是说这是知识产权盗窃，对吧？”但相反，他们说了“知识产权盗窃”，现在整个创业社区都被激活了。你看到了，你知道，Gary Tan 和 200 家初创公司写了那封信。为什么？因为他们知道，如果这个知识产权盗窃的罪名成立，那么所有基于中国模型衍生出来的作品现在也都被玷污了。所以这意味着整个创业生态系统现在都处于危险之中。

<details>
<summary>Original English</summary>

**Speaker B**: They have now basically confessed to their entire product being stolen. And it seems to me that why wouldn't the content creators now assert that they're entitled to own 100% of anthropics revenue? It seems to me that this could be a bridge too far that you know that that they're so good at regulatory capture. They're so good at making these arguments and getting the government involved to create new regulations to protect them. But I wonder if this was just a little bit too cute. And again, if they just positioned it slightly differently, if they said, "Look, these Chinese companies are creating fake accounts. That's a deceptive business practice. We're not saying this is IP theft, right? But instead they said IP theft and now the whole startup community is activated. You saw that you know Gary Tan and 200 startups wrote that letter. Why? Because they know that if this IP theft thing sticks that all derivative works of Chinese models are tainted now too. So that means the whole startup ecosystem is now at risk.

</details>

**Speaker C**: 是的。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah.

</details>

**Speaker B**: 所以我只是在想，这些家伙是不是做得太过分了。我的意思是，如果你去华盛顿，

<details>
<summary>Original English</summary>

**Speaker B**: So I just wonder if these guys have just gone it's just all a bridge too far. I mean, if you go to Washington,

</details>

**Speaker C**: 是的。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah.

</details>

**Speaker B**: 然后你和狗躺在一起，如果你醒来时身上有跳蚤，不要感到惊讶。就像，你、他们决定参与其中，你知道的。所以，他们、他们可能惹怒了老虎。嗯，我认为、我认为这相当准确。

<details>
<summary>Original English</summary>

**Speaker B**: and you lay down with the dogs, don't be surprised if you wake up with the fleas. Like, you they decided to engage in this, you know. So, they they may have poked the tiger. Um I think I think it's pretty accurate. 

</details>

### All-In 播客新书出版计划的玩笑

**Jason**: 哦，顺便说一下，呃，2027 年的出版计划已经发布了。我们会有一些新书出版。你已经听说了我的，《反射》，现在向你走来。手腕上的法拉利。如何在生活中取胜并买得起一块 [笑声] 来自 David Sacks 的 25 万美元的手表。

<details>
<summary>Original English</summary>

**Jason**: Oh, by the way, uh the publishing schedule for uh 2027 was released. We have some new books coming. You heard mine, Jen, you flecting coming to you now. Ferrari on my wrist. How to win at life and afford a [laughter] $250,000 watch from David Sax.

</details>

**Speaker D**: 哦，我的上帝。

<details>
<summary>Original English</summary>

**Speaker D**: Oh my god.

</details>

**Jason**: 这是 Pompic Sachs。[笑声]

<details>
<summary>Original English</summary>

**Jason**: This is Pompic Sachs. [laughter]

</details>

**Speaker E**: 我们需要把那件事搞定。在这里。大卫（David）著的《拯救美国的战斗：摧毁社会主义、缩减债务并赢得 AI》。

<details>
<summary>Original English</summary>

**Speaker E**: We're going to get need to get that done. Here it is. The fight to save America: Destroying Socialism, Shrinking the Debt, and Winning AI by David.

</details>

**Jason**: 是的，那是一本相当不错的书。我想这是我们新的 All-In，呃，它在这里。Chamath Palihapitiya，[笑声]一个性感的意大利夏日。这是一本爱情小说。这是唯一一个 [清嗓子] 决定写虚构小说的人。这是虚构的。

<details>
<summary>Original English</summary>

**Jason**: Yeah, it's a pretty good one. I think this is our new all-in uh here it is. Chama polyatina, [laughter] a sexual Italian summer. It's a romance novel. This is the only person who [clears throat] decided to do fiction. This is fiction.

</details>

**Speaker E**: 这是虚构的。这是虚构的。Chamath，[笑声]

<details>
<summary>Original English</summary>

**Speaker E**: It's fiction. It's fictional. Chimat, [laughter]

</details>

**Speaker D**: 我也拿到了 Chamath 的、呃、非虚构小说。

<details>
<summary>Original English</summary>

**Speaker D**: I got Traumat's uh non-fiction novel also.

</details>

**Jason**: 哦，你连他的非虚构小说也有。它在这里。它在这里。[清嗓子]《企业销售。Chamath 的反乌托邦。我的软件创业公司 [笑声] 如何影响我的意大利夏日》。

<details>
<summary>Original English</summary>

**Jason**: Oh, you have his non-fiction as well. Here it is. Here it is. [clears throat] Enterprise sales. Chimat dystopia. How my software startup [laughter] affects my Italian summer.

</details>

**Speaker D**: 给你。

<details>
<summary>Original English</summary>

**Speaker D**: There you go.

</details>

**Jason**: 太棒了。这太棒了。哦，我的上帝。哇。那是来自 All-In 的……

<details>
<summary>Original English</summary>

**Jason**: It's great. This is great. Oh my god. Wow. That's coming from the allin

</details>

**Speaker D**: 在米兰的 IT 人员。

<details>
<summary>Original English</summary>

**Speaker D**: the IT guy in Milan.

</details>

**Jason**: 绝对是。这、这是来自 All-In 呃 图书部门。这是我们即将在 2027 年推出的新出版品牌。我们还会有 Brad Gerstner、Bill Gurley、埃隆·马斯克（Elon Musk），以及其他书名即将推出。所以，我们会在未来的节目中讨论那些内容。更多、更多的书名即将到来。

<details>
<summary>Original English</summary>

**Jason**: Absolutely. This is This is coming from Allin uh books. It's our new publishing label coming in 2027. We'll also have the Brad Gersonner, Bill Gurley, Elon Musk, and other titles coming. So, we'll have those on future episodes. More more titles coming. 

</details>

### 科技巨头的资本支出与财报分析

**Jason**: 这里的突发新闻主题。谷歌（Google）和特斯拉（Tesla）今天分享了他们的业绩。有很多关于资本支出（capex）的讨论。谷歌的表现极其惊人，他们的，嗯……

<details>
<summary>Original English</summary>

**Jason**: Breaking topic here. Google and Tesla shared their results today. Had a lot of talk about capital expenditures. Google blew the doors off of their um

</details>

**Speaker E**: 极其惊人。我的意思是，

<details>
<summary>Original English</summary>

**Speaker E**: blew the doors off. I mean,

</details>

**Jason**: 那简直太疯狂且离谱了。而他们（的股价）下跌了大概 7% 到 10%。谷歌云（Google Cloud）正在增长……

<details>
<summary>Original English</summary>

**Jason**: it was insane and outrageous. And they were down like 7 to 10%. Google Cloud growing

</details>

**Speaker E**: 因为他们的现金流百分比……

<details>
<summary>Original English</summary>

**Speaker E**: because of their cash%

</details>

**Jason**: 同比增长。

<details>
<summary>Original English</summary>

**Jason**: year-over-year.

</details>

**Speaker E**: 是的，因为那些现金流数据。现在已经达到了千亿美元的年化收益率。而这仅仅是一个业务板块。特斯拉的资本支出同比飙升了 140%，他们预计将有 250 亿美元的资本支出。谷歌今年的资本支出预测是从 195 亿到 205 亿美元。所以明年的数字还会更高。特斯拉下跌了 14%，谷歌在录制时下跌了 7%。谁知道呢？嗯，但两家都报告了负的自由现金流。换句话说，银行里的现金金额不但没有增加反而减少了。而对于谷歌来说，这在历史上还是第一次。

<details>
<summary>Original English</summary>

**Speaker E**: Yeah, because of the cash flow numbers. And now is on a hundred billion dollar run rate. That's but one business. Tesla's capex surged 140% year-over-year and they expect 25 billion in capex. Google's capex forecast from 195 to 205 billion this year. So next year will be even higher. Tesla down 14, Google down 7% of taping. Who knows? Um but both reported negative free cash flow. In other words, the amount of cash in the bank went down instead of up. And for Google, that was the first time ever. 

</details>

**Jason**: IPO 最新消息，呃，SpaceX 相比其上市首日收盘价下跌了 30%，目前交易估值在 1.5 万亿。这只股票面临着很大的压力。我们也会谈论这个话题。显然，他们是以 2 万亿的估值上市的。获得了巨大的涨幅，呃，那种“埃隆效应”的涨幅，并且，嗯，可能会有、呃、更多的下行压力，或者它可能已经触底了。你知道的，对于这些事情你永远无法确定。这是史无前例的领域。我们从未经历过规模如此之大的 IPO，但伴随着一些锁定期。这是图表。一系列的股票解禁正在、正在不同的阶段性时间点发生。

所以，让我们、嗯，让 Chamath 来稍微谈谈。这是你关于 SpaceX 的部分。我想资本支出的投入很明显是为了 AI 进行构建，还有 OpenAI 为了提供他们的服务而在资本支出上投入的情况，但同时也有谷歌，他们进行这些资本支出投资，一部分是为了将其作为谷歌云（一款极好的产品）的一部分进行转售，而另一方面，他们显然也在将其用于自己的基础设施，并且他们的业务正处于疯狂增长中，无论是 YouTube、谷歌云，甚至搜索业务也仍在增长。所以我看了看这个，然后我说：“嗯，这看起来像是一个非常好的资金用途，而不是仅仅去发放股息。对我来说，建设这样的基础设施听起来像是对未来的投资。”这对我来说似乎是一个买入信号，但市场显然对此感到失望。为什么市场会失望？对你来说，这是一个买入信号吗？这是否让你对管理层以及桑达尔（Sundar）和谢尔盖（Sergey）在那里所做的事情感到更加、呃、兴奋？还是说这让你感到担忧？对吧，

<details>
<summary>Original English</summary>

**Jason**: IPO update, uh SpaceX down 30% from its day one closing price, now trading 1.5 trillion. A lot of pressure on the stock. We'll talk about that as well. Obviously, they went public at 2 trillion. Got a big pop, uh the Elon pop, and um there could be uh more downward pressure or it could have found a bottom. You know, you never know with these things. This is unprecedented territory. We've never had an IPO this big, but some lockups. Here's the chart. Bunch of lockups are are happening at different staged intervals. So, let's um Chimath talk a little bit. Here's your SpaceX. I guess capex chimoff is being built out obviously for AI and there is the case of open AI spending on capex in order to provide their service but then there's also Google which is making these capex investments to resell it as part of Google cloud incredible product and then on the other side they're using it for their own obviously infrastructure and their business is just growing like crazy whether it's YouTube or Google cloud or even search is still growing So I looked at this and I said, "Well, this seems like a really good use of capital instead of just giving dividends like building out this infrastructure to me sounds like an investment in the future." Seems like a buy signal to me, but the market is obviously disappointed. Why is the market disappointed? Is it a buy signal for you? Is it make you more uh excited about management and what Sundar and Sergey are doing over there? Or does it make you concerned? Yeah,

</details>

**Chamath**: 我更看涨。你们知道谷歌自上市以来其 25 年的平均投资资本回报率是多少吗？

<details>
<summary>Original English</summary>

**Chamath**: I'm more bullish. Do you know what Google's 25y year average return on invested capital has been since going public?

</details>

**Jason**: 猜一下。

<details>
<summary>Original English</summary>

**Jason**: Take a guess.

</details>

**Speaker E**: 17%。

<details>
<summary>Original English</summary>

**Speaker E**: 17%.

</details>

**Chamath**: 不对。

<details>
<summary>Original English</summary>

**Chamath**: No.

</details>

**Speaker E**: 21%。

<details>
<summary>Original English</summary>

**Speaker E**: 21%.

</details>

**Chamath**: 不对。

<details>
<summary>Original English</summary>

**Chamath**: No.

</details>

**Speaker E**: 23%。

<details>
<summary>Original English</summary>

**Speaker E**: 23%.

</details>

**Chamath**: 不对。

<details>
<summary>Original English</summary>

**Chamath**: No.

</details>

**Speaker E**: 29%。

<details>
<summary>Original English</summary>

**Speaker E**: 29%.

</details>

**Chamath**: 是竞猜价格的游戏，对吧？

<details>
<summary>Original English</summary>

**Chamath**: Prices, right?

</details>

**Speaker E**: 35%。

<details>
<summary>Original English</summary>

**Speaker E**: 35%.

</details>

**Speaker F**: 32%。

<details>
<summary>Original English</summary>

**Speaker F**: 32%.

</details>

**Speaker E**: 耶稣啊。

<details>
<summary>Original English</summary>

**Speaker E**: Jesus.

</details>

**Chamath**: 好吧。这就是当你是一台机器、一群人以及一个能够在 20 年平均水平上以 32% 的复利实现资金增长的商业模式时的情况。你会给予这些人无罪推定的信任。这些人绝不是那种行事轻率鲁莽的人。他们正在有条不紊地对自己的竞争优势进行投资。而这正如、我回到我们最初的对话。他们将会获得极其丰厚的回报。你知道的，在 Twitter 或者 X 上有很多关于 Gemini 使用情况的讨论，讨论它是真实的还是不真实的，以及他们的收入增长是否真的来自于人工智能赋能的工作流？那些全是一派胡言。谷歌拥有令人难以置信的搜索体验。他们似乎正在非常出色地驾驭这种向使用 AI 的过渡。这做得非常好。他们拥有令人难以置信的云业务，并且他们拥有令人难以置信的芯片（silicon）业务。对他们来说，可能发生的最好的事情就是 500 种不同的模型激增，而他们支持所有这些模型，因为他们会在芯片层面赚取极多的钱。他们作为云服务提供商会赚取巨额利润，并且他们会找到一堆应用程序，包括 YouTube 和其他东西来从中赚钱，因为你使用 AI 能够更好地进行广告定向，或者帮助制作出更好的内容，等等。

<details>
<summary>Original English</summary>

**Chamath**: Okay. This is when you are a machine and a group of people and a business model that compounds money at 32% over 20 year average. You give these guys the benefit of the doubt. These are not people that are flying fast and loose. They are methodically investing in their edge. And this is I go back to the first conversation. They are going to get massively rewarded. You know, there was a lot of Twitter chatter or ex chatter about Gemini usage and was it real or was it not real and is their revenue growth really coming from AI enabled workflows? It's all malarkey. Google has an incredible search experience. They've seem to be navigating this transition to use AI. It's been done very well. They have an incredible cloud business and they have an incredible silicon business. The best thing that can happen to them is 500 different models proliferate and they support all of them because they will make so much money at the silicon layer. They'll make so much money as the cloud provider and they'll find a bunch of apps including YouTube and other things to make money from because you use the AI to target ads better or to help make better content etc etc.

</details>

**Speaker E**: 碎片化对他们是有好处的。

<details>
<summary>Original English</summary>

**Speaker E**: Fragmentation's good for them.

</details>

**Chamath**: 哦，这对他们来说太棒了。这是一台复利机器。顺便说一下，我认为市场之所以有这样的反应，Jason，是因为我看到了 Ryan Peterson 的一条推文。我不知道这是否属实，但他表示谷歌今年在资本支出上的花费将达到军事预算的 20%。所以也许人们之所以做出这样的反应，仅仅是因为他们以前从未见过如此庞大投资规模。这是他们自上市以来首次出现自由现金流为负的情况。因此，这显然让人们感到意外，但他们目前正处于一个巨大的投资期。而且我认为这会带来丰厚的回报，即使他们——正如 Friedberg 最初猜测的那样，只投入了那个数字的一半。所以即使他们只投入了一半的金额，他们仍然会超额完成目标。是的。我的意思是，Friedberg，如果你看看苹果（Apple），我想他们回购了一半的……

<details>
<summary>Original English</summary>

**Chamath**: Oh, it's great for them. It's a compounding machine. I think the reaction, by the way, is because Jason, I saw a tweet from Ryan Peterson. I don't know if it's true, but he said Google will be spending 20% of this year's military budget in capex. So maybe what people are reacting to is just the scale of the investment they haven't seen. They're free cash flow negative for the first time since going public. So that obviously takes people by surprise, but they're in a huge investment period. And I think it'll pay off dividends even if they, as Freeberg's first guess was half the number. So even if they did half the number, they'd still be overachieving. Yeah. I mean, Freeberg, if you look at Apple, I think they bought back half

</details>

<!-- chunk 10/12 -->

### 科技公司的资本配置：谷歌的基础设施优势 (Tech Capital Allocation: Google's Infrastructure Advantage)

**Speaker A**: 他们的股票。他们已经将数千亿美元的资金以利润的形式返还了。天哪，在我看来，把所有这些钱返还回去，以回购你们股票的形式进行购买，你知道，或者发放大量的股息。我认为，如今科技公司能够说“等等，我们有值得去投资的东西”是极好的。下一个划时代的大事件就是按需智能（on-demand intelligence），而且智能的发展是没有上限的。我不认为任何人，我当然也无法预见在未来十年的任何时候，会有人说：“我已经获得了足够的智能，我懂了，我已经解决了世界上所有的问题。” 我认为他们会一直持续不断地需要它。所以，你们怎么看这种令人难以置信的巨大转变，你知道，各家公司基本上都将一千亿美元到两千亿美元——你知道，这取决于具体的公司——直接投入到资本支出（capex）之中。呃，这看起来是一个非常明智的举动，对吧？我们所有人都认为这是一件好事。我的意思是，如果你想要押注做空谷歌在基础设施方面的资本部署，仅仅是因为你宁愿今天让他们为你的股票支付现金，那么你就不应该持有这只股票，其他人自然会去买它。我认为谷歌会在很多不同的方面取得最终的胜利。谷歌有太多值得称道的地方了。它有庞大的消费者业务，那里面包含了非常多且复杂的东西。还有YouTube。还有谷歌云平台（GCP）。还有这个包含其他众多押注和投资的投资组合，顺便说一下，这里面甚至包括了SpaceX公司 10% 的股份，以及他们所持有的 Anthropic 的很大一部分股份等等。Waymo的估值，在这个季度对 Anthropic 的投资上就获得了高达一千亿美元的账面上调。所以，仅仅在一个季度之内，他们对 Anthropic 的按市值计价（mark-to-market）就达到了一千亿美元，并且他们在所有这些非常有潜力的业务中都占有相当大的份额。所以关于谷歌有很多令人喜欢的地方，但仅仅就 GCP（谷歌云平台）而言，我认为，在利用人工智能在企业环境中捕获并创造价值方面，可能没有比 GCP 更适合、更具优势的企业级服务层了。我认为——

<details>
<summary>Original English</summary>

**Speaker A**: their stock. They've given hundreds of billions of dollars back in profits. And gosh, it seems to me giving all this money back, buying back in the form of buying back your shares, you know, or or giving tons of dividends. I think it's great that tech companies are now saying, wait, we have something to invest in. The next big thing is ondemand intelligence and there is no upper bound for intelligence or I don't think anybody I certainly don't see you know anytime in the next 10 years people saying I got enough intelligence I've got it I've solved all the problems in the world I think they're going to keep wanting it so what do you think about this incredible change and you know basically a hundred billion $200 billion you know depending on the company just going into capex uh this seems like a savvy move right this is all of us think this is a good I mean, if you want to bet against Google's deployment of capital into infrastructure because you'd rather have them give you cash for your shares today, you shouldn't own the stock and someone else will buy it. I think Google wins in a lot of different ways. There's just so much to Google. There's the consumer business, which is a lot of stuff. There's also YouTube. There's also GCP. There's also this portfolio of other bets, which by the way includes 10% of SpaceX. and a good chunk of Anthropic that they own and so on. Whimo worth took a hundred billion dollar write up on Anthropic in the quarter. So they had a hundred billion dollar mark to market on Anthropic just in one quarter and they own a piece of all these businesses. So there's a lot to like about Google, but just on GCP, I think that there's probably no better suited enterprise layer than GCP to take advantage of capturing value with AI for that enterprise setting. I think

</details>

**Speaker B**: 我认为你只是具有远远大得多的优势，因为你拥有如此海量的企业数据，所有的电子邮件、你的云端硬盘（Drive），以及大量你肯定希望人工智能能够掌握其知识并且能够直接访问的各类信息，从而极大地提高工作场所的生产力水平。而且，他们是模型不可知论者（model agnostic）。我的意思是，你可以运行任何你想要运行的模型，你可以执行任何你想要执行的工作流，你完全不需要被死死地绑定在某一个生态里。很多其他的云服务提供商、云端软件即服务（SaaS）公司，它们都在某种程度上依赖于特定的模型。它们只能以某种非常特定的方式运行。而在谷歌这里，你可以根据你自己的意愿，更好、更自由地调整你的系统。那么最坏、最坏、最坏的情况究竟是什么呢？最坏最坏的情况就是，他们依然拥有世界上成本最低的基础设施，可以作为一种服务来运行其他人的模型，就像埃隆（Elon）和他的 Grok 在 Colossus 计算集群上所做的那样。

<details>
<summary>Original English</summary>

**Speaker B**: I think you're just so much better because you have so much of your enterprise data, all your email, your drive, a lot of information that you would want to have AI have knowledge of and have AI have access to to improve workplace productivity. And then they're model agnostic. I mean, you can run any model you want and you can run any workflow you want and you don't have to be tied in. A lot of other cloud service providers, cloud SAS, they're kind of model dependent. It's run in a certain way. With Google, you can better tune your system how you want to tune it. And what's the worst worst worst case scenario? The worst worst worst case scenario is they have the lowest cost infrastructure in the world to run other people's models as a service like Elon did with Grock with the Colossus

</details>

**Speaker C**: 埃隆的“网络服务”（Elon Web Services）看起来似乎做得相当出色。

<details>
<summary>Original English</summary>

**Speaker C**: Elon Web Services seems to be doing pretty great.

</details>

**Speaker B**: 看看埃隆在 Colossus 基础设施安装上所获得的惊人回报吧。因此我认为，即使是在谷歌面临最坏情况的场景下，即使他们的应用层产品全都不起作用，他们的网络效应全都不奏效，而且他们也没有任何出色的好模型，他们仍然会拥有世界上最强大、最优秀的基础设施。如果你相信人工智能的未来，他们就可以凭借这些基础设施在未来数年里像印钞机一样疯狂赚钱。所以，如果你想要押注人工智能赛道，我认为目前最值得持有的公开市场股票绝对是谷歌。而且顺便说一句，买入它你还会同时获得 YouTube，还会获得庞大的消费者业务，你还会获得其他所有极具价值的一切。目前的估值倍数确实有点荒谬了。

<details>
<summary>Original English</summary>

**Speaker B**: And look at the return Elon's making on the Colossus install. So I think if Google in the worst case scenario, none of their application layer stuff works, none of their network effects work and they don't have any good models, they're still going to have the world's best infrastructure they can print cash on for years if you believe in AI. So if you want to bet AI, I think the best public market stock to own is Google. And by the way, you also get YouTube, you also get the consumer, you also get everything else. The multiple is kind of ridiculous right now.

</details>

### 苹果云服务的设想与基础设施的壁垒 (The Apple Web Services Hypothesis & Infrastructure Moats)

**Speaker A**: 我们在之前的一期节目中深入讨论过这个问题。我想，查马斯（Chamath）、你和我当时在热烈地讨论苹果接下来究竟应该做什么，而且我认为我们最终都得出了这样一个一致的结论：这就好比，为什么不打造“苹果网络服务（Apple Web Services）”呢？他们与成千上万的开发者有着如此良好的紧密关系，他们拥有App Store生态，他们有着如此深厚且庞大的开发者基础群体。但这并没有那么容易，因为你必须要从头开始建立一个庞大的云服务提供商体系，你必须建立一些极其关键的底层基础设施。这花了亚马逊——

<details>
<summary>Original English</summary>

**Speaker A**: We talked about this on a previous issue. I I think Chimath and you and I were talking about like what Apple should do next and I I think we both came to the conclusion it's like why not have Apple web services they have such great relationships with developers they have the app store they have this deep developer it's not so easy because you have to build a cloud service provider you have to build some critical infrastructure it's taken Amazon

</details>

**Chamath**: 差不多整整17年的时间才将其打磨完善。

<details>
<summary>Original English</summary>

**Chamath**: call it 17 years to perfect it

</details>

**Speaker A**: 花了谷歌大概12或13年的时间才在很大程度上勉强赶上。但是，杰森（Jason），从你签约决定成为一个网络服务提供商、一个云计算服务提供商的那一刻起，你真正要向客户承诺和承担的，是五个九（99.999%）的绝对可靠性和系统正常运行时间。而这绝对是极其昂贵的。要达到前两个九，也就是99%的正常运行时间，你知道的。如果你是为一家制药公司或者一家国防公司托管某些服务，你也许可以以相对较低的成本勉强做到这一点。但是要达到第三个九，也就是99.9%，这可能就要花费你数十亿美元。达到第四个九的成本将高达数百亿美元，而要达到那至关重要的第五个九，更是要花费数千亿美元的巨资。这需要真金白银的大规模投资和实打实的顶尖技术能力，而目前在这个市面上只有三个真正的实力玩家能够做到。

<details>
<summary>Original English</summary>

**Speaker A**: it's taken Google call it 12 or 13 years to mostly catch up. But the minute that you sign up to be a web provider, Jason, and a cloud service provider, what you're really signing up for is 59s of reliability and uptime. And that is just extremely expensive. Getting to the first two nines, you know, 99% uptime. If you're hosting something for a pharma company or a defense company, you can probably do it for relatively cheaply. Getting to the third nine, 99.9 probably cost you in the billions. Getting to the fourth nine costs the tens of billions, but getting to that fifth nine costs hundreds of billions. And that takes a real investment and real technical skill, and there's only three games in town.

</details>

**Jason**: 是的，我认为蒂姆·库克（Tim Cook）绝不是做这件大事的那个人，但这位新任的CEO也许可能会，呃，因为他本身就是一名工程师出身，但他们在过去整整十年的时间里，已经把海量的资金都回馈给了股东。

<details>
<summary>Original English</summary>

**Jason**: Yeah, I think Tim Cook's not the guy to do it, but this new CEO might be uh since he's an engineer, but they've returned in the last decade.

</details>

**Speaker A**: 他们可以用这些钱购买9000亿美元，其中7550亿美元用于大规模的股票回购，1400亿美元——萨克斯（Sacks）——用于分红。好好让这组数字沉淀并消化一下吧。9000亿美元！如果他们把这笔巨款投资到 Anthropic 和 SpaceX 以及其他一些极具前瞻性的项目上呢？他们本来是完全可以为这笔巨额资金找到一些非常好的用处的。但是，萨克斯，关于发生的事情你有什么想法或见解吗？

<details>
<summary>Original English</summary>

**Speaker A**: They could buy 900 billion, 755 in buybacks and 140 billion sachs in dividends. Just let that sink in. 900 billion if they had invested that in Anthropic and SpaceX and other things. They just could have found some good uses for that money. But Sax, any thoughts here on what's happen?

</details>

**Sacks**: 谁能断言呢？抱歉，但谁能说获得那些钱的投资者们，没有为这笔钱找到一个好的用处呢？

<details>
<summary>Original English</summary>

**Sacks**: Who's to say? Sorry, but who's to say that the investors that got that money didn't find a good use for it?

</details>

**Speaker A**: 哦，是的。所以，从整个社会的宏观层面上说是这样的，但我只是固执地认为，如果苹果没有把这笔巨款花在回购和分红上，而是仅仅拿出这笔钱的一半，用来创造全新的颠覆性产品，并且真正地去发布他们的苹果汽车，也许再收购一些非常有趣的创新型公司，他们本来是可以变得更具野心和侵略性的。我认为他们——

<details>
<summary>Original English</summary>

**Speaker A**: Oh, yeah. So, on society level, but I just think Apple could have been more ambitious if they just spent half that money instead of on buybacks and dividends on creating new products and actually releasing their car, maybe buying some interesting companies. I think they

</details>

**Sacks**: 我认为这在很大程度上是一种“绝对不造成伤害（do no harm）”的保守资本配置策略，并且这种策略对维持和推高股票价格确实非常有效。

<details>
<summary>Original English</summary>

**Sacks**: I think it was very much a do no harm capital allocation strategy which worked for the stock.

</details>

**Jason**: 看看约翰·特纳斯（John Ternus）未来是否会彻底扭转这种局面、改变剧本，将会是一件非常有趣的事情。

<details>
<summary>Original English</summary>

**Jason**: It's going to be really interesting to see if John Turners flips the script.

</details>

**Speaker A**: 我认为他会的。我认为他将会展现出一种典型的工程师那样的务实和创新风格，是的。好了，关于金融市场我们就谈到这里吧。市场总是会我行我素地做市场该做的事。等有更多值得风险投资家们深入评论的新闻时，我们再来详细讨论伊朗以及其他类似的地缘政治事件。现在就仅仅是关于，我知道大家一直在急切地问。我不认为在这件事上我们有太多实质性的话可说。但我确实认为在我们全新的、定期重现的常驻板块“社会主义角（Socialism Corner）”里，我们有很多话可以说是的。弗里德伯格（Freeberg），每周都有更多令人震惊的新闻从“社会主义角”冒出来。呃，制片人——

<details>
<summary>Original English</summary>

**Speaker A**: I think he does. I think he's going to be like engineer guy and yeah. All right, enough on the markets. The markets are going to do what markets do. We will talk about Iran and other stuff like that when there's more news for venture capitalists to comment on. Right now, it's just on on I know everybody keeps asking. I I don't think there's much for us to say on it. I do think there's a lot for us to say uh in socialism corner our new reoccurring uh theme here Freedberg every week there's more news coming out of socialism corner uh producer

</details>

**Friedberg**: 你们可以展示一下我过去六年来一直都在谈论关于社会主义的那些视频了。

<details>
<summary>Original English</summary>

**Friedberg**: you can show my uh my videos on socialism going back six years

</details>

### 纽约市的租赁政策争议 (Controversy over NYC Rent Policies)

**Speaker A**: 让我们把本月早些时候弗里德伯格对社会主义的慷慨陈词和痛批补充进来。城市独裁者市长祖汉·曼尼（Zohan Mani）——

<details>
<summary>Original English</summary>

**Speaker A**: let's add to the Freeberg socialism rants earlier this month city dictator mayor Zohan Mani

</details>

**Friedberg**: 别，千万别，请不要滥用那个极其严重的词，拜托，别这样。

<details>
<summary>Original English</summary>

**Friedberg**: don't don't misuse that term please come on

</details>

**Speaker A**: 在纽约市廉租公寓博物馆（Tenement Museum）举行了一场名为“租房敲诈（rental ripoff）”的专门听证会。听证会结束后，他直接提交了一份《租房敲诈报告》。如果该报告获得正式通过，将严厉禁止房东对信用检查收取任何形式的申请费。它将允许房东要求租客提供信用检查，或者要求提供符合40倍租金收入标准的严格证明，但绝对不能两者同时都要求。并且在法律上正式承认租客工会的合法地位，还有更多其他的规定。很显然，他已经强行把租金冻结了整整一年。在听证会的现场，一位激进的活动人士呃戴着防护级别很高的 COVID 口罩，并耸人听闻地将驱逐行为称为“驱逐的暴力（violence of evictions）”。这是给你们准备的 22 秒短片。“曼达尼（Mandani）政府正在大力鼓励和支持我们，以便我们绝不再像对待往常那些冰冷的商业行为一样，去默默容忍驱逐的暴力。”[全场笑声]

<details>
<summary>Original English</summary>

**Speaker A**: a rental ripoff hearing at New York City's Tenement Museum. After the hearing, he introduced a rental ripoff report. If passed, bars landlords from charging applications for credit checks. It's going to let landlords require a credit check or the 40x rent income standard, but not both. Legally recognizes tenant unions and more. He's obviously frozen the rent for a year. At the hearing, an activist uh wore a COVID mask and referred to evictions as the violence of evictions. Here's your 22nd clip. The Mandani administration is emboldening us so that we no longer tolerate the violence of evictions as a matter of business as usual. [laughter]

</details>

**Speaker D**: 搞什么鬼，我们刚才看的到底是什么诡异的东西？画面里那个是萨克斯（Sacks）吗？你们还记得经典动画《胖子阿伯特》（Fat Albert）里那个戴着那种夸张帽子的家伙吗？[笑声] 我们能把那个家伙的画面调出来对比一下吗？你们还记得《胖子阿伯特》里那个戴着那顶帽子的家伙吗？他叫什么名字来着？哦，我的天哪。

<details>
<summary>Original English</summary>

**Speaker D**: What the What were we just watching? Is that the sax? Do you remember the guy from Fat Albert who had the hat like that? [laughter] Can we pull that guy up FROM YOU REMEMBER THE GUY FROM FAT ALBERT who had the hat? What's his name? Oh my god.

</details>

**Speaker E**: 新冠疫情（COVID）到现在还在肆虐吗？我一直以为新冠早就彻底结束了。不，不，她刚才只是拿到了一个——

<details>
<summary>Original English</summary>

**Speaker E**: Is CO still happening? I thought CO was over. No, no, she just got a

</details>

**Speaker D**: 那绝对是一个超级无敌的强力防护口罩。那真的是一个超级无敌的防护口罩。那不仅仅是一个普通的、单薄的小布口罩。那是这种——

<details>
<summary>Original English</summary>

**Speaker D**: That was like a super duper mask. That was a super duper mask. That just wasn't like a little cloth one. That was one of these

</details>

**Speaker E**: 那种非常大号的口罩。

<details>
<summary>Original English</summary>

**Speaker E**: those big ones.

</details>

**Speaker D**: 我的意思是，配合上那顶奇怪的帽子，那真是……那画面真的是绝了。[笑声] 就是这个。我清楚地记得那家伙，他来自于……呃这到底是在搞什么鬼？

<details>
<summary>Original English</summary>

**Speaker D**: I mean, combined with the hat, it was uh that was pretty [laughter] There it is. I remember that guy from uh What is going on?

</details>

**Jason**: 等等，让我们，我们要特意给弗里德伯格（Freeberg）留出一个尽情发表长篇大论的机会，因为，我的意思是，我自己完全可以，我也可以立刻针对这事儿来一段长篇大论的痛批。

<details>
<summary>Original English</summary>

**Jason**: Wait, let's we're going to give Freeberg a chance to do a rant because I mean I could do I could do a rant on this.

</details>

**Speaker A**: 不，不要。让我们把舞台交给弗里德伯格发挥。这可是弗里德伯格的最爱（rare meat）。1787年版本的弗里德伯格。在1787年，约翰·昆西·亚当斯（John Quincy Adams），

<details>
<summary>Original English</summary>

**Speaker A**: No, no. Let's give Freeberg his This is Freeberg rare meat. Freeberg in 1787. In 1787, John Quincy Adams,

</details>

**Friedberg**: 看吧，他又要开始了，

<details>
<summary>Original English</summary>

**Friedberg**: there he goes,

</details>

**Speaker A**: 出版了一部具有深远影响的著作，名为《美利坚合众国政府宪法辩护》。在那部重要的著作中，他发表了一番极其深刻的评论。一旦社会中承认了这样一种危险的观念：私有财产不如上帝的律法那般神圣不可侵犯，并且社会不再有法律的力量和公共正义来坚定地保护它，那么无政府状态和暴政的深渊就会立刻开始降临。然后在随后的1791年，他在一系列文章中更加斩钉截铁地公开声明：“财产必须得到绝对的保障，否则自由就根本无法存在。”

<details>
<summary>Original English</summary>

**Speaker A**: published a work called a defense of the constitutions of governments of the United States of America. And in that work, he had a comment. The moment the idea is admitted into society, that property is not as sacred as the laws of God, and that there is not a force of law and public justice to protect it, anarchy and tyranny commence. And then in 1791 he made the statement publicly, "Property must be secured or liberty cannot exist in an essay series."

</details>

**Jason**: 你能不能为我们详细地拆解一下，并解释为什么他当时会那样断言？你认为——

<details>
<summary>Original English</summary>

**Jason**: Can you unpack it and explain why he said that? Do you think

</details>

**Friedberg**: （这）是支撑美利坚合众国赖以建立和存续的最根本的基础。

<details>
<summary>Original English</summary>

**Friedberg**: fundamental to the foundation of the United States of America

</details>

<!-- chunk 11/12 -->

### 私有财产权与反向演化：从无政府到暴政

**Friedberg**: ……是私有财产权的理念吗？因为如果你想一想所有来到美国的人当初是来自哪里，你会发现那里存在着各种暴虐的政府、君主制或类似的东西。在那里，某个领主或某个政治集团可以随时决定拿走你所拥有的东西。作为个人，你完全没有任何私有财产权可言。他们可以随便闯进来，然后说：“那个农场是我的农场。你实际上只是一个农奴，而我是领主。那个东西是我的东西。你之所以有权使用它，是因为我赋予了你使用的权利。我是全能的，我是这片土地上专制的监管者。”正是这种停滞不前的状态，驱使着那么多人来到美国，并表示我们想要一个地方，在这个地方，个人，哪怕是一个普通人也可以说：“我拥有某样东西，而且任何人都不能从我这里夺走它。”私有财产权是美国自由的基石。这种认为你可以借由暴力行为，或者你可以声称存在着极其悬殊的、极度奢华的财富状况，然后对那个个人说：“我现在有权，政府现在有权拿走你的私有财产”的观念，最终必然导致这种暴政形式。而且这一切在开始时表现为一种无政府状态，因为，请记住，无政府状态只是一个过渡性的临时状态。它总是介于一种状态和另一种状态之间。所有的无政府状态最终都会走向暴政。一群群的人互相斗争，他们都在互相抢夺和偷窃彼此的东西。每个人都只顾着去拿、去夺取他们想要的东西。最终，人们开始联合起来，他们形成了各种团体。然后，那些团体变成了更强大的团体。接着，强大的团体最终获胜，他们便成为了凌驾于大众之上的暴政。这就是为什么所有无政府状态最终都会演变成暴政的原因。所以，无政府状态和暴政本质上是同一回事。从根本上说，这些所谓的社会主义原则正在做的事情是，我们正在拿走你的私有财产，而你对你的私有财产不再拥有权利。无论你是一个房东，还是一个被我们认定为拥有过多财富的富人，我们现在都将有权闯入、拿走你的财产、控制它，并彻底把它从你手中夺走。这往往总是以一种充满道德意味的框架作为开端：我们是好人，你们是坏人，原因如下。你对居住在你大楼里的人犯下了暴力行为。你攫取了太多的财富，而我们这些人都没有财富。所以我们有权去拿走你的财富。它总是从这样一个观点出发，即你是坏人。所以，第一种设定框架就是：私有财产所有者是邪恶的，私有财产所有者对那些没有私有财产的人犯下了不公正的行为，而这就是剥夺他们私有财产权的所谓正当理由。而这也是向专制暴政系统过渡的开端，这最终将导致我所说的这种美国式的大型政治局，或者任何由这些社会主义者的核心集团所建立的社会主义框架，以及他们试图拼凑起来的任何东西。因此，所有这些看似荒谬、疯狂和极其不恰当的小举动，总体上来说其实都是同一回事。它们都在促成一种对私有财产权的背离，而私有财产权正是美利坚合众国的立国根基。这就是为什么我认为我们所有人都应该感到如此震惊的原因。正如约翰·昆西·亚当斯（John Quincy Adams）所说的那样，我们需要强烈地捍卫这些权利。一旦这些权利开始流失，哪怕是以最微小的方式流失，这也会产生一种级联效应，一切都会变得专制暴虐，而在美利坚合众国，事情将会变得非常难看。Sacks，呃，你对，嗯，Mandami 同志在这里有什么看法？

<details>
<summary>Original English</summary>

**Friedberg**: ... was this idea of private property rights? Because if you think about where everyone that came to America was coming from, there were these tyrannical governments, monarchies or whatever, where some overlord or some cabal could decide at any point to take the things that you have. You had no private property rights as an individual. They could come in, they're like, "That farm is my farm. You're actually a surf. I'm the lord. That thing is my thing. You have a right to use it because I vest you that right to use it. I am the all powerful. I am the tyrannical overseer of these lands. And it was that stasis that drove so many to come to the United States and say we want a place where individuals, one person can say, I own something and no one can take it from me. Private property rights are the foundations of liberty in America. this idea that you can then claim acts of violence, that you can then claim circumstances of of extraordinary, extravagant wealth and say to that individual, I now have a right, the government now has a right to take your private property ultimately leads to this tyrannical form. And it starts out as being an anarchctic because, and remember, anarchy is a temporary state. It's always in between one state and another. All anarchies end up in tyranny. Groups of people fight each other. They're all stealing [ __ ] from each other. Everyone just goes and takes and gets what they want. And eventually people coales. They form groups. And those groups become the more powerful groups. And the powerful groups end up winning and they become the tyranny over the mass. And that is why all anarchies eventually evolve into tyranny. So anarchy and tyranny are one and the same. And fundamentally what's going on with these socialist principles is that we are taking your private property and you no longer have rights on your private property. Whether you are a landlord or whether you are a wealthy person that we've deemed to have too much wealth, we now will have the rights to come in and take your property and control it and take it from you. And it always starts with this framing of moralistic intent. We are good. You are bad for the following reasons. You have committed violence against the people that live in your building. You have taken too much wealth and none of us have wealth. We have a right to go and take your wealth from you. It has always started from this point of view that you are bad. So the first framing is that the private property owner is evil and that the private property owner has committed an act of injustice against those who don't have the private property and that is the justification for taking away their private property rights and it is the beginning of this transition towards a tyrannical system which will ultimately be what I call this kind of great American polit or whatever socialist framework gets set up by the the cabal of the socialists and and what they're trying to put together. So all of these little acts while seeming ridiculous and insane and inappropriate in aggregate are the same thing. They're a transition away from private property rights which is the foundation of the United States of America. That's why I think we should all be so shocked. And to John Quincy Adams point we need to vehemently defend those rights. As soon as those rights start to slip away even in the tiniest way it is a cascading effect and everything will become tyrannical and it will be very ugly in the United States of America. Saxs, uh, what are your thoughts here on um, Comrade Mandami?

</details>

### 租金控制、驱逐禁令与社区衰败

**Sacks**: 是的，我只是想在这个观点上再补充一个层面。你知道，这些美国民主社会主义者（DSA）类型的社会主义者声称驱逐就是暴力，所以他们基本上想要停止驱逐行为。我认为 Friedberg 刚才提出了一个很好的观点，那就是这种做法剥夺了房东的财产，这确实是事实，但我认为我们还必须停下来思考一下，这对这些公寓大楼里的其他居民究竟意味着什么。我的意思是，首先，如果房东因为大楼里有一大堆拖欠租金的无赖租客而赚不到收入，那么他们现在就无法支付日常的维护和保养费用。所以，这些建筑会变得越来越破旧不堪，而这不可避免地会影响到这里的其他租户。但同时，我有一个负责管理这些公寓大楼的朋友，他指出，那些最糟糕的邻居，往往正是这些占据着房子的“租霸”，也就是这些早就应该被驱逐却无法被驱逐的拖欠租金的租客。因此，当你思考一个公寓综合体里出现的问题时——那里可能有人在半夜制造极大的噪音，也许他们在放着震耳欲聋的音乐；或者你遇到有人在疯狂地砸墙；或者从某些公寓里散发出令人作呕的恶臭气味；或者他们在使用公共区域时滥用设施；又或者你遇到一些醉酒和扰乱公共秩序的行为。我的意思是，所有这类乌七八糟的事情，正是发生在这些受到租金控制的公寓大楼里的典型现象。而且你必须记住，这里还有许多长期居住的老居民，很多是负担不起去别处寻找新住处的上了年纪的人。他们完全依赖于这种租金控制。当你无法驱逐那个不守规矩的恶劣租客时，是的，这肯定会影响到房东，但它对邻居的影响甚至更大、更深远，因为现在他们被迫陷入了一个不断恶化的恶性循环之中。我认为这就是贯穿整个进步派思维模式中的一个普遍问题，那就是这些 DSA 类型的人总是那些受过高等教育、而且往往生活非常富裕的阶层，他们完全有资本去拥有关于公共空间的各种所谓“奢侈信念”，因为他们自己从来都不去使用这些空间，对吧？他们根本不坐公共汽车，不坐地铁，也不去那些普通的公园。所以，当这些公共设施被无家可归的吸毒者占领时，他们总是倾向于为那些吸毒者辩护，而不是站在中产阶级的立场上。

<details>
<summary>Original English</summary>

**Sacks**: Yeah, I just want to add a layer to this this idea. You know, the these DSA socialists say that evictions are are violence and they basically want to stop them. I think Freeberg's making the point that this deprivives the landlord of their property, and that's true, but I think we also have to stop and consider what this means for the other residents in these buildings. I mean, first of all, if the landlords aren't making income because they got a bunch of delinquent tenants in the building, they can't now pay for upkeep and maintenance. And so, these buildings become more dilapidated, and that affects the the other tenants. But also, I have a friend who manages these apartment buildings, and he makes the point that it's often these squatters, these delinquent tenants who should be evicted but can't, who make the worst neighbors. So, when you think about the problems in a in an apartment complex where you've got people creating noise at night, maybe they're playing loud music or you have people punching walls or there's disgusting smells coming from apartments or they're misusing common areas or you have drunken and disorderly behavior. I mean, this is all the kind of stuff that happens in these rent controlled apartment buildings. And you have to remember that there's long-standing residents, a lot of old people who can't afford to find a new place. They depend on the rent control. And when you can't evict that unruly tenant, yes, it it affects the landlord, but it affects the neighbors even more because now they're stuck in a downward spiral. And I think this is a problem with the progressive mindset across the board is that these DSA types are always these like highly educated and often affluent types and they can afford to have luxury beliefs about public spaces because they never use them, right? They don't use the bus or the subway or parks. And so when they get taken over by homeless drug addicts, they always defend the addicts as opposed to the middle class.

</details>

**Speaker C**: 如果你不住在田德隆区（Tenderloin，旧金山市中心犯罪率高的街区），那说这种话当然是一件很容易的事。

<details>
<summary>Original English</summary>

**Speaker C**: An easy thing to do if you don't live in the tenderloin.

</details>

**Sacks**: 对，一点没错。而且这种情况对工薪阶层的打击是最沉重的，因为他们实际上是真正需要这些生活设施的人。他们需要去公园遛孩子，或者他们需要乘坐地铁通勤，对吧？当你在地铁里遇到有人注射毒品，或者吸毒，或者，你知道的，随地大小便时，这真的是一个非常严重的问题。

<details>
<summary>Original English</summary>

**Sacks**: Right. Exactly. And it falls the hardest on the working class because they actually need these amenities. They need the parks for their kids or they need to use a subway, right? And it's really a problem when you get people shooting up or doing drugs or, you know, defecating in a subway.

</details>

**Speaker D**: 比如住在马林县（Marin County，旧金山湾区富人区）或者在纽约上东区拥有这种奢侈信念的人，当他们送孩子去上学时，他们根本就不……他们完全是与这种现实脱节的。他们完全不需要去应对这种破事，对吧？

<details>
<summary>Original English</summary>

**Speaker D**: You're walking your kids to school like the person in Maring County who has these luxury beliefs or on the upper east side, they just don't they're they're abstracted from this. They don't need to deal with it, right?

</details>

**Speaker C**: 我们以前讨论过这个问题。

<details>
<summary>Original English</summary>

**Speaker C**: We talked about this.

</details>

**Sacks**: 在这些实行租金控制的公寓部门，情况也没有任何不同。我认为这里的关键点在于，如果在长达几年的时间里，无论某些租客的行为多么恶劣、制造了多大的麻烦，你都无法驱逐任何人，那么你实际上就把这些公寓大楼变成了类似于廉租房（housing projects）的地方。而且你知道，这确实严重影响了那些收入微薄却奉公守法的体面人，他们根本没有其他地方可去，他们的生活质量因此大幅下降。听着，你知道的，那些住在封闭式高档社区里的私募股权投资人的妻子们可能仍然会对自己的行为感觉良好，因为，在她们看来，她们成功阻止了这些驱逐事件，但是，真正要为这一切承受最大痛苦的，是大楼里那些无辜的普通居民。

<details>
<summary>Original English</summary>

**Sacks**: And it's it's no different with these rent control departments. I think that's the important point here is that if over a period of several years you can't evict anyone no matter how problematic they are, you effectively turn these apartment buildings into the equivalent of housing projects. And you know that really affects decent people of modest income who have nowhere else to go and their quality of life suffers. And look, you know, the private equity wives in their gated communities will still feel good about themselves because, you know, they prevented these evictions, but it's the people in the building who are going to suffer the most.

</details>

### 解决住房危机的基本经济学原则

**Speaker C**: 还有就是，Chamath（Shimat），这些人不仅仅是没有从第一性原理出发去思考问题。如果你真的想解决住房问题，任何一个只要对经济学有一点点基础了解的人都会直接说，那好，增加供应量，价格自然就会降下来。而且实际上，你增加的是哪种供应都无所谓。不管你建的是豪华公寓单元，还是多户型住宅，或者是单户家庭住宅，这都不重要。只要能有更多的，呃，住房供应，并且有相应的交通网络能够到达这些地方，能够把人们运进运出，那问题就能迎刃而解。就像我们……就像我现在坐在东京一样，比如这里的人们很久以前就已经弄明白了这个问题。只要往高处建，多增加一些住房单元就行了。他们在德克萨斯州、在佛罗里达州、在内华达州也都弄明白了这个问题。似乎唯独无法弄明白这个道理的，你知道的，就是像纽约、洛杉矶和旧金山这样的地方，而这些地方碰巧全是自由派精英的聚居地。从概念基础上来说，这真的不难。只要允许人们去建造更多数量的住房单元，以及建造不同类型的住房单元，然后房价自然就会随之下降。Chamath，在这里你有什么……有什么想法吗？

<details>
<summary>Original English</summary>

**Speaker C**: And well, these and they're Shimat, these people are not just thinking from first principles. If you want to solve the housing problem, anybody with any basic understanding of economics would just say, well, increase the supply and the price will go down. And it actually doesn't matter which supply you add. It doesn't matter if it's luxury units or multif family or single family. As long as there's more uh housing and there's transportation to get to it and to move people in and out, it'll be fine. As we've as I like I'm sitting here in Tokyo, like they figured this out a long time ago. Just build up and put more units in. They figured it out in Texas, Florida, Nevada. The only people who can't seem to figure this out, you know, is like New York, LA, and San Francisco just happens to be liberal elite enclaves. And it's not hard on a conceptual basis. Just allow people to build some more units and different types of units and then the price will go down. Chimath, any any thoughts here?

</details>

**Chamath**: 来自奥斯汀（Austin）的数据表明，一旦你放宽了审批许可的限制条件，你就能建起更多的住房单元。而且每有一个新增的住房单元投入使用，它就会真真切切地拉低整体的租金水平。所以，如果你想要低廉的租金，你就需要有更多的住房单元。如果你想要更多的住房单元，你就需要更积极主动地去发放建筑许可。就这么简单。所以，这仅仅是一个决定而已。如果 Mandani 有足够的政治意愿去通过这项（反驱逐）法律，那么他只要运用同样的政治意愿，实际上就可以去通过一些审批许可方面的改革，而这将会带来大得多的好处。关于私有财产的那件事，我之所以问……

<details>
<summary>Original English</summary>

**Chamath**: The data from Austin says once you relax the permitting constraint, you'll get more units built. And for every unit that comes online, it literally drives down the rent. So if you want low rent, you need to have more units. If you want more units, you need to permit more aggressively. That's it. So, it's just a decision. The same political will that it would take Mandani to pass this law, he could actually pass some permitting reform and it would do a lot more good. The thing on private property, the reason I asked

</details>

<!-- chunk 12/12 -->

### 财产所有权与租赁法规 (Property Ownership and Rent Regulations)

**Freebrook**: 解释一下，我真的认为他所说的非常重要。对我来说，这种想法很可笑。在极端情况下，我们假设你正在开着自己的车，突然有人跳进车里，然后他们说：“嗯，你知道，现在我在这里了。你不能把我赶出去。”或者，你知道，你走到外面，开着门去取一个联邦快递（FedEx）包裹或亚马逊（Amazon）的箱子，然后有人跑进你的房子，坐在你的沙发上，现在突然之间他们就……你就不能把他们赶出去了。这听起来真是荒谬至极、愚蠢透顶。如果你强迫实物财产的持有者无法对租客进行信用检查，并且无法区分他们将公寓出租给谁，那么将会发生的情况是，租金会变得更高。因此，我怀疑他们应该做的是通过这项法律，然后他们应该观察结果会是什么，接着你可以对纽约市（New York City）和奥斯汀（Austin）进行一个相当科学的 A/B 测试对比，这样你就会知道什么方法行得通，什么方法行不通了。

<details>
<summary>Original English</summary>

**Freebrook**: to explain it is I really believe what he's saying is really important. It's like funny to me this idea that at the limit, let's just say you're driving your car and all of a sudden somebody jumps in it and they're like, "Well, you know, now I'm here. You can't kick me out." or you know, you go outside, you leave your door open to go get a FedEx package or Amazon box and somebody runs in and sits on your couch and now all of a sudden they can't you can't kick them out. And it sounds so ludicrously dumb. If you force the owners of physical property to not be able to credit check and differentiate who they rent their apartments to, what's going to happen is rents will go up even more. So, I suspect that what they should do is they should pass this law and they should observe what the outcome is and then you can do a pretty scientific AB comparison between New York City and Austin and you'll know what works and what doesn't work.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 我的意思是，这里的问题是社会主义者永远不会吸取教训。我的意思是，我们已经有……

<details>
<summary>Original English</summary>

**Speaker B**: I mean, here's the problem is is the socialists never learn. I mean, we already have

</details>

**Speaker C**: 阿根廷取消了租金管制。结果租金下降了。

<details>
<summary>Original English</summary>

**Speaker C**: got rid of rent control in Argentina. Rents went down.

</details>

**Speaker B**: 是的。是的，我的意思是，Jimoth 提到的问题就在于，你看，如果社会主义者曾经从他们失败的实验中吸取过教训，你就不会看到芝加哥现在的情况。你知道的，这就像是，我们不需要等到纽约市彻底崩溃，才意识到这根本行不通，因为这种事情已经在太多其他地方发生过了。但不知何故，这种趋势似乎永远不会停止。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Yeah, I mean this is the problem with Jimoth is that look, if the socialists ever learned from their failed experiments, you wouldn't have Chicago, you know, it's just you like we don't need New York to go down the tubes to know this isn't going to work cuz it's happened in so many other places already. But somehow it just never seems to stop.

</details>

**Speaker D**: 他们似乎永远学不会。所以他们应该进行这项实验并从中学习。我的意思是，疯狂的是，你将在最宏大的舞台上学习，而这注定将是一场失败。你谈论的是最大、最复杂的城市——纽约市。天哪。

<details>
<summary>Original English</summary>

**Speaker D**: They never seem to learn. So they should run the experiment and learn. I mean what's crazy is you'll be learning and it'll be a failure on the grandest stage possible. You're talking about the biggest, most complicated New York City. My gosh.

</details>

### 租金管制与幽灵公寓 (Rent Control and Ghost Apartments)

**Speaker E**: 我的意思是，还有……Sachs，如果一个房东无法合理地提高租金，会发生什么？

<details>
<summary>Original English</summary>

**Speaker E**: I mean, and and Sachs, what happens if a landlord

</details>

**Sachs**: 无法合理地提高租金？那么，他们就没有动力去投资新建公寓。他们也没有动力去升级现有的公寓。而在纽约市，特别是存在这样一个陷阱。他们制定了公寓法规，规定如果你进行翻新，就必须符合特定的建筑规范。而这些规范多如牛毛。好吧。所以这意味着翻新会变得极其昂贵。于是现在他们有……你就会看到“幽灵公寓”的出现。

<details>
<summary>Original English</summary>

**Sachs**: cannot raise the rent reasonably? Well, they have no incentive to invest in new units. They have no incentive to upgrade new units. And there's this trap in New York City specifically. They have made this regulations for apartments such that if you do a renovation, it has to hit certain codes. And there are a ton of codes. Okay. So that means it's incredibly expensive. So now they have you have ghost apartments.

</details>

**Speaker F**: 是的。所以现在的房屋存量变得破旧不堪。而且你看，他们现在还在做更糟糕的事情，我认为，那就是他们禁止房东对潜在租客进行信用和背景调查。他们声称你不能查看租客的收入，所以你无法审查他们是否真的有能力支付租金。所以他们正在禁止……

<details>
<summary>Original English</summary>

**Speaker F**: Yes. So now the housing stock becomes dilapidated. And look, they're doing something even worse now, I think, which is they are banning landlords from doing credit and background checks on potential tenants. And they they say that you can't look at their income, so you can't vet whether they can actually pay the rent. So they're banning

</details>

**Speaker G**: 房东。再也没有房东了。

<details>
<summary>Original English</summary>

**Speaker G**: landlord. No more landlord.

</details>

**Speaker F**: 他们正在禁止驱逐。然后他们还阻止你进行尽职调查，以确定这个人是否是一个会交房租的租客。

<details>
<summary>Original English</summary>

**Speaker F**: They're they're banning eviction. And then they're and then they're preventing you from doing the diligence to see if this is even a tenant who will pay the rent.

</details>

**Speaker G**: 我们已经完全脱离常轨了。

<details>
<summary>Original English</summary>

**Speaker G**: We've lost the script.

</details>

**Speaker F**: 那你该怎么办呢？

<details>
<summary>Original English</summary>

**Speaker F**: So what are you supposed to do?

</details>

**Jimoth**: 有趣的问题是，如果你作为一个房东，被迫在这些规则下生存，你会怎么做？显而易见的答案是，你一开始就会把租金定高三到四倍，并且你会强迫人们签署多月预付租金的协议，然后你会慢慢放宽这些条件，直到你找到一个市场出清价格。那是唯一可行的办法。所以租金不会下降，租金会上升。那么就运行这个实验，我们看看会发生什么吧。

<details>
<summary>Original English</summary>

**Jimoth**: The interesting question is if you were forced to live under these rules, the landlord, what would you do? And the obvious answer is you'd start rent three or four times higher and you force people to sign up to a multi-month prepayment and you'd slowly ease those conditions until you find a market clearing price. That's the only way to do it. So rents will not go down. Rents will go up. So run the experiment and let's just observe what happens.

</details>

**Speaker H**: 这是个非常好的观点，Jimoth。比如，假设你知道有 X% 的租客会变得拖欠房租，对吧？因为顺便问一下，当他们知道自己不会被驱逐时，他们付房租的动力是什么？

<details>
<summary>Original English</summary>

**Speaker H**: That's a really good point, Jimoth. Like let's say that you know X percent of tenants are going to become delinquent, right? Because and by the way, what's their incentive to pay when they know they can't be evicted?

</details>

**Speaker I**: 零。完全没有动力。

<details>
<summary>Original English</summary>

**Speaker I**: Zero. Zero.

</details>

**Speaker H**: 所以实际上，相当大比例的人可能会直接决定：“我要把付房租变成一个可选项。”

<details>
<summary>Original English</summary>

**Speaker H**: So like actually a pretty significant percentage of people could just decide I'm going to make rent optional.

</details>

**Speaker I**: 因此现在房东必须吸收这些损失。

<details>
<summary>Original English</summary>

**Speaker I**: And so now the landlord has to absorb those losses.

</details>

**Speaker H**: 完全正确。而这意味着他们必须将更高的租金转嫁给其他所有人。你要把租金定高 3 倍，然后你会慢慢将其下调。就像我说的，你将不得不要求他们在第一年全额预付一整年的租金。

<details>
<summary>Original English</summary>

**Speaker H**: Exactly. And that means they have to pass on a higher rent to everybody else. You're going to set the rent 3x higher and you're going to slowly meander it down. And like I said, you're going to have to wire in the first full year of rent.

</details>

**Speaker I**: 好吧，祝你好运。这怎么能让人负担得起呢？

<details>
<summary>Original English</summary>

**Speaker I**: Well, good luck. How is that affordable?

</details>

**Speaker J**: 情况甚至更糟，Sachs。房东不仅在某些情况下保留了破旧的公寓，对他们来说，有时更好的做法干脆是让公寓和房屋存量空着。所以，有人搬走了，房东被迫进行翻修，而这花费更高，你知道，翻修要花几十万。于是，他们说：“你知道吗？我现在就让它空着算了。”因此，根据纽约市的报道，那里有 5 万套幽灵公寓。

<details>
<summary>Original English</summary>

**Speaker J**: It's even worse, Sax. Not only do the landlords keep the dilapitated apartments in some cases, it's better for them to just leave apartments, housing stock, empty. So, somebody leaves, they are forced to renovate it and it costs more, you know, hundreds of thousands in uh renovations. So, they say, "You know what? I'll just leave it empty for now." And so, you have 50,000 ghost apartments according to reports in New York City.

</details>

**Sachs**: 嗯，那是个 Airbnb 的问题。那就像是……

<details>
<summary>Original English</summary>

**Sachs**: Well, that's an Airbnb problem. That's like a

</details>

**Speaker J**: 不，他们在纽约禁止了 Airbnb。你无法租到 Airbnb。

<details>
<summary>Original English</summary>

**Speaker J**: No, they banned Airbnb in New York. You cannot get an Airbnb.

</details>

**Sachs**: 哦，真的吗？

<details>
<summary>Original English</summary>

**Sachs**: Oh, really?

</details>

**Speaker J**: 是的。所以现在情况就像是……

<details>
<summary>Original English</summary>

**Speaker J**: Yes. So, now it's like

</details>

**Sachs**: 那真的很有趣。是的。你看，如果你是一个房东，好吧，我的意思是，我猜你会做的一件事就是直接卖掉房产，去另一个司法管辖区。你可以做的另一件事就是干脆等下去，因为经营一栋公寓楼已经无利可图了。你不能提高租金，不能驱逐租客，也不能对租客进行尽职调查。所以，也许你就让整栋楼空着，慢慢熬过去。我的意思是，前提是你没有背负太多的债务，对吧？

<details>
<summary>Original English</summary>

**Sachs**: That's really interesting. Yeah. Look, if you're if you're a landlord, okay, I mean, I guess one thing you would do is just sell and go to another jurisdiction. Another thing you could do is just wait this out because it's not profitable to run an apartment building. You can't raise your rents. You can't evict people. You can't diligence the tenants. So, maybe you just leave the building empty and you wait this out. I mean, that's assuming you don't have too much debt on it, right?

</details>

**Speaker K**: 或者是幽灵公寓。是的。

<details>
<summary>Original English</summary>

**Speaker K**: Or ghost apartments. Yeah.

</details>

**Sachs**: 然后你就拥有了幽灵公寓。

<details>
<summary>Original English</summary>

**Sachs**: And then you have ghost apartments.

</details>

### All-In 峰会宣传 (All-In Summit Promotion)

**Host**: 是的。好了，听着，你们一直都在考虑来参加 All-In 峰会（All-In Summit）。今年是属于你的一年。演讲嘉宾都是世界级的。活动、派对、社交网络环节，在那里 80% 的人都是创始人、投资者或高级别的运营者。今年的重点更加侧重于人际网络……

<details>
<summary>Original English</summary>

**Host**: Yeah. All right. Listen, you've been thinking about coming to the All-In Summit. This is your year. speakers are world class. The events, the parties, the networking, 80% of the people there, founders, investors or high level operators this year. Greater focus on network,

</details>

**Speaker L**: 还有音乐表演。

<details>
<summary>Original English</summary>

**Speaker L**: the musical performances.

</details>

**Host**: 噢，是的。我的意思是，在过去，我们有过……

<details>
<summary>Original English</summary>

**Host**: Oh yes. I mean, in the past, we've had

</details>

**Speaker L**: 美食、美酒……

<details>
<summary>Original English</summary>

**Speaker L**: the food, the drink,

</details>

**Host**: 歌手 Grimes……

<details>
<summary>Original English</summary>

**Host**: Grimes,

</details>

**Speaker L**: 制作人 Diplo……

<details>
<summary>Original English</summary>

**Speaker L**: Diplo,

</details>

**Host**: Diplo。我们请到过这么多不可思议的人。去访问 all-inssummit.com 吧。好了，各位。这又是一集令人惊叹、空前传奇的 All-In 播客。爱你们，伙计们。再见。拜拜。

<details>
<summary>Original English</summary>

**Host**: Diplo. We've had so many incredible people. Go to the all-inssummit.com. All right, everybody. It's another amazing alltime legendary episode of the All-In podcast. Love you boys. Bye. Byebye.

</details>

**Announcer**: [音乐] 让你的赢家继续奔跑。[音乐]

<details>
<summary>Original English</summary>

**Announcer**: [music] Let your winners ride. [music]

</details>

**Speaker M**: 然后它说，我们向粉丝们开源了它，他们对它简直是痴迷疯狂了。[音乐] 爱你。

<details>
<summary>Original English</summary>

**Speaker M**: And it said we open sourced it to the fans and they've just gone crazy with [music] it. Love you.

</details>

**Speaker N**: [音乐] 闺蜜们（Besties）走了。那是我家狗在车道上拉屎。[音乐]

<details>
<summary>Original English</summary>

**Speaker N**: [music] Besties are gone. That is my dog taking an [music] driveway.

</details>

**Speaker O**: 噢，天哪，我的男装裁缝（haberdasher）会来接我。[音乐]

<details>
<summary>Original English</summary>

**Speaker O**: Oh man, my habitasher will meet me up. [music]

</details>

**Speaker P**: 我们都应该开个房间，然后直接举办一场巨大的狂欢派对，因为他们都只是……这就像是这种性张力，[音乐] 我们只需要以某种方式释放出来。[笑声]

<details>
<summary>Original English</summary>

**Speaker P**: We should all just get a room and just have one big huge orgy cuz they're all just It's like this like sexual tension [music] that we just need to release somehow. [laughter]

</details>

**Speaker Q**: 我们需要获得宽恕。[音乐]

<details>
<summary>Original English</summary>

**Speaker Q**: We need to get mercy. [music]

</details>

**Speaker R**: [音乐] 我要“All in”（全押）。

<details>
<summary>Original English</summary>

**Speaker R**: [music] I'm going all in.

</details>