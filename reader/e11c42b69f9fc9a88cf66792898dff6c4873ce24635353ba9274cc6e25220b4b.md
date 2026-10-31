---
author: a16z
date: '2026-04-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0_NGsljlo3o
speaker: a16z
tags:
  - proof-of-human
  - identity-verification
  - biometrics
  - digital-privacy
  - bot-detection
title: AI时代如何证明你是人类？Worldcoin的数字身份验证之路
summary: 本期访谈深入探讨了在AI时代下，如何有效证明人类身份的复杂性与重要性。Alex Blania介绍了Worldcoin的“人类证明”机制，包括基于虹膜生物识别技术的唯一性验证，以及为确保用户隐私而采用的多方计算和零知识证明。他指出，随着AI内容和机器人活动的爆炸式增长，在线社交媒体、视频会议、游戏乃至政府服务和民主投票等多个领域，对人类身份验证的需求日益迫切，这不仅关乎平台诚信，也直接影响经济政策与社会运行。Worldcoin正致力于通过大规模Orb设备部署和技术整合，在美国市场全面推广其解决方案，以应对日益严峻的AI挑战。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Worldcoin
  - Twitter
  - X
  - Tinder
  - YouTube
  - OpenAI
products_models:
  - Orb
  - Face ID
  - ChatGPT
  - Gemini
  - ClaudeBots
  - Moldbook
media_books: []
status: evergreen
---
### 引言：人类证明的紧迫性

**主持人**: 如何证明某人是人类？

<details>
<summary>Original English</summary>

**主持人**: How do you prove somebody is human?

</details>

**Alex**: 这是一个异常困难的问题。我认为人们会开始被指责是机器人。

<details>
<summary>Original English</summary>

**Alex**: It is a surprisingly hard problem. I think that people are going to start getting accused of being bots.

</details>

**主持人**: 我们现在看到的还不到未来一两年内可能出现的1%。AGI（通用人工智能）将带来一些非常根本性的转变，这似乎是显而易见的。

<details>
<summary>Original English</summary>

**主持人**: What we currently see is less than 1% of what it will look like in probably a year or two. The idea that AGI will lead to some very fundamental shift. Seems obvious. Like

</details>

**主持人**: 人工智能确实很擅长编程人类，远胜于人类编程人工智能。

<details>
<summary>Original English</summary>

**主持人**: the AIs are really good at programming humans. Much better than humans are at programming AIs.

</details>

**Alex**: 绝对如此。一个人工智能将能够拥有一个GitHub账户，能够发帖，并能证明其他五个AI是人类，即使它们不是。说实话，如果你现在不认真对待，

<details>
<summary>Original English</summary>

**Alex**: Absolutely. An AI will be able to have a GitHub account and will be able to post and also attest to five other AIs that these are in fact humans and even though they're not. Honestly, if you don't take it seriously now,

</details>

**主持人**: Alex，欢迎来到播客。很高兴邀请到您。

<details>
<summary>Original English</summary>

**主持人**: Alex, welcome to the podcast. Great to have you.

</details>

**Alex**: 谢谢邀请。目前，“**人类证明**”（Proof of Human）正当其时。您能否先为不熟悉的人介绍一下？现在发生了什么，我们是如何走到这一步的？

<details>
<summary>Original English</summary>

**Alex**: Thanks for having me. So, Proof of Human is having a moment right now. Why don't you first give a background for people who are unfamiliar? What is the moment that's happening and how did we get here?

</details>

**主持人**: 是的。什么是人类证明？

<details>
<summary>Original English</summary>

**主持人**: Yeah. And what is proof? Proof of human.

</details>

**Alex**: 人类证明，顾名思义，是关于您是否知道在互联网上与您互动的是人类还是其他某种东西。我实际上认为，我们现在提出的问题是：您是与一个人互动，还是与代表一个人行事的代理（Agent）互动，或者仅仅是一个代理？我认为这大致是我们想要区分的三个领域。那么，您如何看待“仅仅是一个代理”和“代表人类行事的代理”之间的区别呢？

<details>
<summary>Original English</summary>

**Alex**: Proof of human as the name suggests is, you know, do you know if you interact with a human or like something else on the internet? And I actually think the kinds of questions that we're now asking is are you interacting with a human, an agent on behalf of a human or just an agent? Like I think these are like roughly the three areas that we want to split apart. Well, and and describe a little bit the difference between just an agent and an agent acting on behalf of a human. How do you see that distinction?

</details>

### 人类证明的定义与挑战

**Alex**: 是的。所以，我先快速解释一下**人类证明**这个术语，以及它困难之处，然后我将解释它如何适用于“代表人类行事的代理”。所以，人类证明真正的含义是，在某个平台上互动的每个个体，理想情况下只有一个账户，或者有限数量的账户。

<details>
<summary>Original English</summary>

**Alex**: Yeah. So, quickly explaining just the term proof of human and I think what is hard about it and then I will I will explain how that fits into into an agent on behalf of a human. So what proof of human really means is that, you know, every individual that interacts on a platform has only one ideally one account or, you know, a limited number of accounts

</details>

**主持人**: 并且保持该账户的所有权，这就是您正在寻找的属性。您正在寻找一个初始验证，理想情况下应该是匿名或极度保护隐私的，然后是持续的身份验证，以确保同一个人始终控制着该账户。

<details>
<summary>Original English</summary>

**主持人**: and stays the owner of that account like that that's that's kind of the property that you're looking for. Like you're looking for a initial verification that ideally should be, you know, something like anonymous or very extremely privacy preserving and then on ongoing authentication that the same person remains in control of the account.

</details>

**Alex**: 嗯，然后还有一些我认为是很好的次要属性。但这实际上告诉您，真正困难的事情是**唯一性**。就像现在在**Twitter**这样的平台上发生的情况是，有所有这些账户，所有这些机器人都在回复中，可能有一个人类坐在某个地方，发送数万或数十万个AI。

<details>
<summary>Original English</summary>

**Alex**: Um, and then there's like some secondary properties that I think are good to have. But that actually tells you that the really hard thing is is uniqueness like like what what is happening on a platform like Twitter right now is that there's all these accounts, you know, all these all these bots that are in the replies that you know there's probably one human sitting somewhere and and sending out 10 thousands or like hundred thousands of AIs

</details>

**主持人**: 而且这是一个追赶游戏，**Twitter**和**X**正试图发现并阻止它们，每天可能数百万个，这大概只是机器人总数的百分之一。

<details>
<summary>Original English</summary>

**主持人**: and there's this catchup game where like, you know, Twitter and X are trying to just find them and block probably millions a day of these which is what like, oh, a 100th of the of the bots

</details>

**Alex**: 是的，感觉就是这样。然后，“代表人类的代理”，我认为未来的情况会是，我们所有人都会有代理，但尚不清楚会是什么样子。会是一个，还是多个，可能带有不同的任务，甚至不同类型的角色。

<details>
<summary>Original English</summary>

**Alex**: That that's right. That's how it feels like. Um, and then agent on behalf of human I think like how it will look like is, uh, you know, I as a like I think all of us will have agents. It's unclear how it will look like, is this going to be one or there multiple ones, maybe with different tasks and different even even types of characters.

</details>

**Alex**: 嗯，我认为它最终会归结为我批准我的代理的某个特定行动。我赋予它某些权利，比如代表我行事。

<details>
<summary>Original English</summary>

**Alex**: Um, and I think it will then come down to I, you know, I approve a certain action of my agent. I give him certain rights. So like act on my behalf.

</details>

**主持人**: 好的。发布到我的**X**账户，发布到我的**Instagram**。

<details>
<summary>Original English</summary>

**主持人**: Okay. Post post to my X account, post to my Instagram,

</details>

**Alex**: 例如。

<details>
<summary>Original English</summary>

**Alex**: for example.

</details>

**主持人**: 但那是我的**Instagram**，我是一个拥有它的独特人类。

<details>
<summary>Original English</summary>

**主持人**: But it's my Instagram and I'm a unique human that owns it.

</details>

**Alex**: 没错。然后，**X**或**Instagram**可以决定这是否是他们作为平台想要的东西。

<details>
<summary>Original English</summary>

**Alex**: That's right. You know, then X or Instagram could could decide if that if that's actually something they want as a platform,

</details>

**主持人**: 对吗？

<details>
<summary>Original English</summary>

**主持人**: right?

</details>

**Alex**: 嗯，但这就是您能做到的方式。

<details>
<summary>Original English</summary>

**Alex**: Uh, but that's how you could do it.

</details>

**主持人**: 这很有道理。嗯，那么您如何证明某人是人类呢？这是一个出人意料的难题。

<details>
<summary>Original English</summary>

**主持人**: That makes sense. Um, and so how do you how do you prove somebody is human? It is it is a surprisingly hard problem.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**主持人**: 您知道，那些代理非常非常聪明。

<details>
<summary>Original English</summary>

**主持人**: So, you know, you know, those agents are very very clever.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

### 人类证明解决方案的演变

**Alex**: 嗯，这很有趣。我们几年前成立了这家公司，在**ChatGPT**和所有这些出现之前，但我们当时就预设，最终会有人工智能，它们既通过了图灵测试，因此可以声称自己是人类。您将无法再在互联网上分辨出它们。而且它们将是高度自主的，会自己运行，做自己的事情。所以这使得问题变得非常非常困难，因为当时我们刚成立公司时，人们感兴趣的大约有三个主要想法。嗯，其中一个是关于**信任网络**（web of trust）或相关想法。这个想法是，您会查看某人在互联网上的行为，或过去的行为。通常是结合了您拥有一定数量的账户，您拥有这些账户已经几年了，然后您定期发帖或定期评论**GitHub**，这些是人们使用的方式。然后假设我们三个人都有这些，然后我也证明，我在现实世界中认识您，我向您证明我在现实世界中认识您，这就是您建立某种图谱的方式，这在当时是一个非常热门的想法。嗯，但我们基本上立即就否定了它，因为我们认为，您知道，最终所有只是数字化的东西，人工智能也能够做到。

<details>
<summary>Original English</summary>

**Alex**: It's uh, you know, it's funny. We started this company now a couple of years ago before Chad JPD and before all of that, but we we kind of took that as an assumption that eventually we will have AIs that, you know, both passed the touring test, so they can just claim to be a human. You will not be able to tell them anymore on the internet. And also that they would be, you know, a highly agentic and just like run around, do their own thing. And so that makes it really, really hard because uh back then when we started the company, there were like roughly three big ideas that people were interested in. Um one was this idea of uh web of trust or like related ideas. So this idea that you you look how someone behaves on the internet or did behave in the past. So like usually a combination of you have these certain number of accounts uh that you you know you own since a couple years and then you post regularly or you comment regularly to GitHub like these were the kind the kinds of things that people are using and then let's say all three of us have them and then I attest also that you know I know you in the real world and I attest to you that I know you in the real world and that's how you would build a certain graph and that was like a very hot idea back then for this Um but we disregarded it basically immediately because we assumed that you know eventually everything that is just digital an AI will be able to do it as well like

</details>

**Alex**: 我们已经到了那个地步。

<details>
<summary>Original English</summary>

**Alex**: we're there.

</details>

**主持人**: 是的。没错。所以，一个AI将能够拥有一个**GitHub**账户，能够发帖并拥有一个账户，并且能够证明其他五个AI是人类，即使它们不是。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Exactly. So an AI will be able to have a GitHub account and we'll be able to post and own an account and like also attest to five other AIs that these are in fact humans and even though they're not.

</details>

**Alex**: 所以，嗯，您知道，那是第一个领域。第二个领域是仅仅使用**政府ID**。

<details>
<summary>Original English</summary>

**Alex**: So uh so you know that was that was area number one. Area number two was to just, you know, uh use government IDs

</details>

**主持人**: 对于所有事情，我们都立即否决了，原因有几个。一个原因是，我认为，如果政府不控制这种基础设施，在言论自由方面会更好，并且实际上要打破这种控制。

<details>
<summary>Original English</summary>

**主持人**: for everything which uh we just all immediately disregarded for a couple reasons. one is the, you know, uh I think, you know, it's strictly better if the government would not control such an infrastructure in terms of free speech and actually breaking that apart but then also

</details>

**主持人**: 对，您会立刻失去匿名性。

<details>
<summary>Original English</summary>

**主持人**: right you lose anonymity

</details>

**Alex**: 您理论上可以建立一个可能保留它的系统，但这很难做到。然后第二件事是，政府身份系统根本不是为此而设计的。

<details>
<summary>Original English</summary>

**Alex**: instantly right you could hypothetically set up a system that maybe preserves it but it's very hard to do and then the second thing is also um, you know, the government identity system is just not built for that

</details>

**Alex**: 嗯，这个问题的困难之处在于，它将是一个全球性问题。所以，即使某个政府可能拥有完美的国家基础设施，例如**新加坡**就是一个拥有完美基础设施的政府，但这几乎无关紧要，因为，例如，**Meta**是一个拥有三十亿用户、遍及许多其他国家的全球产品。

<details>
<summary>Original English</summary>

**Alex**: and uh and and what is so hard about this problem is it's going to be a global problem and so it doesn't really matter if you know one government maybe has the perfect infrastructure for example Singapore is like an example of a of a of a of a of a government that has, you know, perfect infrastructure all around but that barely doesn't doesn't matter because you know for example I don't know Meta is a global product with three billion users with a lot of other countries

</details>

**主持人**: 是的，新加坡大概有两百万人或一百万人。

<details>
<summary>Original English</summary>

**主持人**: yeah Singapore is what like uh 2 million people or million people

</details>

**Alex**: 没错，所以您想把其他人全部排除在外吗？所以，嗯，是的，然后还有一长串其他原因，我们基本上立即就否定了这种方法。然后最后一个是**生物识别技术**，这实际上立即引起了我们最初的反应，它就像……

<details>
<summary>Original English</summary>

**Alex**: exactly so do you want to lock everyone everyone else out so uh so yeah and then there's a long list of other things um why we disregarded that basically immediately and and then the last one is biometrics which actually, you know, immediately gives us this IG reaction it's it's like

</details>

**Alex**: 嗯，它甚至更进一步，因为，正如我一开始提到的，这个问题的难点在于**唯一性**。

<details>
<summary>Original English</summary>

**Alex**: um and it even went further because uh what is so hard about this problem as I mentioned in the beginning is uniqueness

</details>

**Alex**: 所以，简单来说，如何描述这个问题是：首先，例如，**Face ID**做了什么？**Face ID**检查我是否是再次使用手机的同一个人。

<details>
<summary>Original English</summary>

**Alex**: and so just like in very simple words how you can describe the problem is um well first of all for example what does face ID do face ID checks that I'm the same person again using my phone.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**主持人**: Mhm.

</details>

**Alex**: 所以，它是一种一对一的身份验证。我的手机上存储了一个嵌入式数据。它拍下我的脸，创建一个新的图片，与之前的图片进行比较，如果足够接近，我就可以使用我的手机。

<details>
<summary>Original English</summary>

**Alex**: And uh so it's a onetoone authentication. So there's an embedding stored on my phone. It takes a picture of my face, creates a new picture, compares to the previous one, and if that is close enough, I can use my I can use my phone.

</details>

**Alex**: 但是，嗯，那是一个一对一的，您知道，一个嵌入式数据到一个新的嵌入式数据。

<details>
<summary>Original English</summary>

**Alex**: But uh so that's a one to one, you know, one embedding to one new embedding.

</details>

**Alex**: 要解决人类证明问题，您需要区分一个新个体与所有之前的个体。

<details>
<summary>Original English</summary>

**Alex**: To solve the proof of human problem, you will need to distinguish one new individual from all previous individuals. H

</details>

**Alex**: 您需要确保**Ben**正在注册，而且**Ben**之前没有注册过。

<details>
<summary>Original English</summary>

**Alex**: you need to make sure that you know Ben is trying to sign up and Ben did not sign up before.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Alex**: 嗯，然后它突然从一对一变成了**一对N**，而**N**本质上是您试图证明的网络的规模。

<details>
<summary>Original English</summary>

**Alex**: Um and then suddenly it goes from one to one to one to n and n is the n is the size of your network essentially that you're trying to prove that to

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right

</details>

**Alex**: 然后您就可以进行数学计算，计算出从信息论的角度来看，您需要多少**数学熵**，需要多少信息来证明这一点。结果是这个数字相当高，因为它是一个指数级的问题，对吗？

<details>
<summary>Original English</summary>

**Alex**: and then you can just do the math and you can calculate how much mathematical entropy like how much information just information theoretically do you need to um to prove that. And it turns out that's a pretty high number because it's it's an exponential problem,

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right?

</details>

**Alex**: 那么您就可以进行数学计算，然后发现，像面部或指纹之类的东西是行不通的。那样的话，您会在数千万用户之后基本上碰到一堵墙。

<details>
<summary>Original English</summary>

**Alex**: And so then you can do the math and you find out that you know things like a face or or you know even fingerprints or something doesn't work. Uh like that then you would basically hit a wall after tens of millions of users.

</details>

**主持人**: 是的。所以您最终会得到像**虹膜**（iris）这样的东西，它是您眼睛的肌肉，它实际上拥有足够的熵。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And so then you end up with uh, you know, something like iris which is the muscle of your of your eye that actually has enough entropy

</details>

**主持人**: 它是唯一的。

<details>
<summary>Original English</summary>

**主持人**: that it's unique

</details>

**Alex**: 它是唯一的，足够唯一。

<details>
<summary>Original English</summary>

**Alex**: that is unique that is unique enough

</details>

**主持人**: 那么您如何解决生物识别技术历史上一直面临的**重放攻击**问题呢？

<details>
<summary>Original English</summary>

**主持人**: and how do you also then solve the uh, you know, one thing that biometrics have been subject to historically is just replay attacks

</details>

**主持人**: 即使我没有您的眼球，但我有足够的信息可以对您进行重放攻击。

<details>
<summary>Original English</summary>

**主持人**: where okay I may I may not have your eyeball but I've got enough information that I can run a replay attack on you.

</details>

**Alex**: 嗯，所以现在实际上有……再次强调，我认为将问题拆分为**验证**（verification）和**认证**（authentication）很重要。验证本质上是，用旧的术语来说，就像您拿到护照一样。

<details>
<summary>Original English</summary>

**Alex**: Um so like there's there's now actually, you know, again it is important I think to split up the problem and verification which is essentially in, you know, old terms it's like you getting your passport

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right

</details>

**Alex**: 然后认证是您为某些事情不断出示护照。

<details>
<summary>Original English</summary>

**Alex**: and then authentication which is you showing your passport constantly for certain kinds of things

</details>

**Alex**: 嗯，在验证方面，我们，如果您了解**Worldcoin**，您就会知道我们已经构建了这个被称为**Orb**（奥秘）的东西。它做了很多事情来防止这类攻击。例如，它在电磁光谱中有多个传感器，以确保您不能向它显示一个屏幕，它会识别出来。嗯，所以我认为在那方面我们已经处理好了。在消费者端，您知道，那应该会重新认证。结果证明这要困难得多，因为您在某种程度上需要信任手机。

<details>
<summary>Original English</summary>

**Alex**: and on the, you know, on the verification piece um that's, you know, we we've went down if you know world, you know, that we've built this thing called an you know, it's it's doing a lot of things to prevent these kinds of attacks. So it's for example it has multiple sensors in the, you know, electromagnetic spectrum to just make sure that you cannot show a display to it and it and it would recognize that. Um so I think on that side we've, you know, we we've got it handled on the on the consumer side like, you know, that should then reauthenticate. It turns out to be much harder because uh you would need to trust the phone in some sense

</details>

**Alex**: 嗯，因为我们实际上在那个时刻所做的，是当您用**Orb**进行验证时，我们不仅以完全匿名和保护隐私的方式检查您的唯一性（我们应该谈谈这一点），而且我们还会向您的手机发送一张签名的面部图像，您以后可以用它来重新认证。

<details>
<summary>Original English</summary>

**Alex**: uh because what we actually do in that moment is when you verify with an orb we not only do we check uh your uniqueness in a fully anonymous and privacy preserving way and we should talk about that but also we send to your phone a signed face image that you then can later use to reauthenticate against it

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right

</details>

**Alex**: 嗯，您知道，用一台新的**iPhone**，您可以对其抱有相当程度的信任，但用旧的**安卓**手机，基本上……

<details>
<summary>Original English</summary>

**Alex**: um and you know with a new iPhone you can have meaningful amount of trust against that but with old Android phones basically

</details>

**Alex**: 所以，是的，您知道，因为您可以只显示一个**深度伪造**（deepfake），无论是通过屏幕还是直接注入摄像头流。所以，嗯，这是一个问题。因此，它将是两者的结合：如果您有一台足够新的**iPhone**或普通手机，那么您就可以用您在验证时拍摄的那张图片进行重新认证。否则，您可能不得不定期回到**Orb**那里。嗯，比如说一年几次，如果您只是……

<details>
<summary>Original English</summary>

**Alex**: And so yeah, you know, because like you can just uh, you can just show a deep fake essentially either through a display or just directly injected in the camera stream. So, um that's a problem and so it's going to be a mix of uh, you know, if you have a new enough let's say iPhone or or general phone um then you can just reauthenticate against that uh picture that you took on verification. Otherwise, you would probably have to even go back to an orb somewhat frequently. Um, like let's say a couple times a year if you just I see you

</details>

**主持人**: 对，重新认证它。

<details>
<summary>Original English</summary>

**主持人**: right to reauthenticate it.

</details>

**Alex**: 是的，没错。

<details>
<summary>Original English</summary>

**Alex**: Yeah, that's right.

</details>

**主持人**: 有趣。

<details>
<summary>Original English</summary>

**主持人**: Interesting.

</details>

### Orb与隐私保护

**Alex**: 然后，您知道，早期的这种方法受到的一种不正确的批评是，“天哪，他们拿走了我的眼球。”嗯，您知道，现在他们，他们以某种方式获得了我的隐私，他们将对我做所有这些事情，那是我的访问权限，然后他们**Worldcoin**可以冒充我，所有这些事情，但情况并非如此。

<details>
<summary>Original English</summary>

**Alex**: And then, you know, one of the things one of the kind of incorrect criticisms of the approach early was, "Oh my god, they've got my eyeball." Um, you know, now they're, you know, they they somehow have uh access to my privacy and they're going to, you know, do all these things to me and and that's my access and then they can they uh Worldcoin can um impersonate me and all these kinds of things, but that's not the case. And um

</details>

**主持人**: 那是一个非常非平凡的工程问题。

<details>
<summary>Original English</summary>

**主持人**: There was that was very much non-trivial.

</details>

**Alex**: 嗯，所以实际上，我认为人们对**虹膜**的一个不太重视的点，是我们当时下注的，但它本质上是，虹膜作为一种识别方式将变得非常普遍，只是因为我认为我们都会佩戴做这种事的**AR**和**VR**系统。您知道，**苹果**已经做到了，**Vision Pro**已经有了**RSI ID**。所以，我认为这可能是一个普遍的观点。我认为它将成为我们在许多不同设备上使用的东西，并且会在此意义上常态化。但我想在隐私方面，嗯，这花费了我们很多时间，因为，当我们当时决定，根据我们的假设（那是在六年前），我们需要一个定制的生物识别硬件设备时，实际上是相当可怕的。

<details>
<summary>Original English</summary>

**Alex**: Um, so actually I think one point on Iris that I think people don't appreciate enough and that's a bet we took back then but it was essentially that Iris will turn out to be supern normal as a as a modality just because I think we will all wear um AR and VR systems that do that. You know Apple already does it uh already has RSI ID and the vision pro. So I think it's so maybe that's a general point. I think it's going it's going to be become something that we will use across many different devices and uh we'll normalize in that sense. But I think on the on the privacy piece um that took us a lot of time because like when when we when we decided back then that you know with our assumptions you know which was 6 years ago that we will need a custom hardware device for biometrics it was actually quite scary um, you know, to to come to the conclusion because like

</details>

**主持人**: 是的，那是一个昂贵的结论。

<details>
<summary>Original English</summary>

**主持人**: yeah that's an expensive conclusion.

</details>

**Alex**: 这非常昂贵。然后仅仅是拥有这个想法，您需要将它们分发到世界各地，这仅仅意味着您将能够以某种方式筹集数十亿美元。

<details>
<summary>Original English</summary>

**Alex**: It's like it's like very expensive and then just having this idea that you would need to distribute them all over the world like that that just assumes that you would be able to like somehow bring up billions of dollars and

</details>

**Alex**: 像这样大规模地努力将其分发到世界各地。嗯，但同时，隐私挑战在于如何构建一个满足我们所有要求的系统。解决这个问题的两个主要高级想法是**多方计算**（multi-party computation）和**零知识证明**（zero knowledge proofs）。

<details>
<summary>Original English</summary>

**Alex**: do like a massive effort to to distribute all over the world. Um but then also the privacy challenge of like how could you build such a system that has all the all the requirements that we care about and the the two main highlevel, you know, ideas on how to solve it where uh multi-party computation and zero knowledge proofs.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**主持人**: Mhm.

</details>

**Alex**: 所以，嗯，再次强调，**Face ID**有何不同？因为**Face ID**实际上可以非常私密，仅仅因为嵌入式数据存储在手机上。它不必离开手机，因为它只是您自己与过去的您进行比对。

<details>
<summary>Original English</summary>

**Alex**: And so um to again what is different to face ID because Face ID actually is it you know can be very private just because the embedding is stored on the phone. It doesn't have to leave the phone ever just because it's just you against you in the past.

</details>

**Alex**: 但是要检查**唯一性**，您需要与所有之前的人进行检查。所以，某种东西需要离开。

<details>
<summary>Original English</summary>

**Alex**: But to check uniqueness uh you need to check against all previous people. So so something needs to leave.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Alex**: 您知道，某种东西需要离开某个地方，并与其他人进行比较。嗯，那是一个更困难的挑战。然后，嗯，我们解决这个问题的方法是**多方计算**。所以这本质上意味着，在我们的例子中，当您用**Orb**进行验证时，我们会拍摄所有这些图片，它们在设备上进行计算，然后它们实际上被分割成多个部分。所以我们，例如，拍下虹膜的图片，计算出一个**虹膜码**（iris code），然后我们将该虹膜码分割成多个部分，并将其发送到多台计算机。

<details>
<summary>Original English</summary>

**Alex**: You know something needs to leave something and be compared to someone else. Uh and that's and that's a much harder uh challenge. And um how we approach that is we have multi-party computation. And so that essentially means that so in our case when you uh verify with an orb, you know, we take all these pictures uh they get computed on the device and uh then they actually get split up in multiple pieces. So we for example we take a picture of the iris we calculate an iris code um then we break that iris code in multiple pieces and sell send it to multiple computers

</details>

**Alex**: 这样，嗯，就不会有某种形式的中央数据库。所以没有人真正拥有关于您的信息。

<details>
<summary>Original English</summary>

**Alex**: such that um there is no central database in some sort. So no one actually has the information about you.

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: Right.

</details>

**Alex**: 然后您会做一些巧妙的技巧，让这些不同的参与方需要聚集在一起进行计算，但同时仍保持这些部分分离。

<details>
<summary>Original English</summary>

**Alex**: And then you do some clever tricks of how these different parties need to come together to do a computation that still leaves the pieces apart.

</details>

**主持人**: 对。对。对。

<details>
<summary>Original English</summary>

**主持人**: Right. Right. Right.

</details>

**Alex**: 以这样一种方式，没有人拥有完整的信息。是的。所以没有人拥有完整的信息，而且在计算过程中也没有人拥有完整的信息。

<details>
<summary>Original English</summary>

**Alex**: In such a way that nobody has the whole thing. Yeah. So no one has the whole thing and also during the computation no one has the whole thing

</details>

**Alex**: 但他们确实会做一些，您知道，一些巧妙的互动来得出结论。

<details>
<summary>Original English</summary>

**Alex**: but they do some, you know, some clever interactions to come to the conclusion

</details>

**主持人**: 有点像**零知识证明**那种技术。

<details>
<summary>Original English</summary>

**主持人**: a little like a zero knowledge proof kind of technique.

</details>

**Alex**: 嗯，我的意思是它非常不同，但我觉得在它实现的属性方面有点相似，您知道，没有人知道您的任何信息，但您实际上可以一起做出关于您的声明。

<details>
<summary>Original English</summary>

**Alex**: Uh it's it I mean it it's very different but I think in terms of the properties it achieves it's somewhat similar where like you no one knows anything about you but you can actually together make a statement about you

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right

</details>

**Alex**: 所以，您知道，您将其发送到这个**多方计算**中，返回的结果是：是的，这个个体是唯一的。然后我们做的第二件事是，我们用**零知识证明**将所有这些与您分开。这意味着您的手机上有那个秘密，但其他人没有。没有服务器有它。我们也没有。嗯，然后您以后可以回到这个多方计算中，说：“嘿，我有一个属于那个计算的秘密，我确实是唯一的。”嗯，您可以向平台证明这一点。您可以去社交网络，向社交平台证明您是唯一的身份，而我们不知道您的任何信息，社交网络也不知道您的任何信息。所以它具有这种非常**反直觉**的属性，即使它使用生物识别技术，您仍然保留了**匿名性**和极高的隐私水平，我认为这非常酷。

<details>
<summary>Original English</summary>

**Alex**: and so, you know, you send it to this multi-party computation and what comes back is yes that individual is unique and then the second thing we do is we we separate all of this um from you with a zero knowledge proof. So meaning you have that secret on your phone but no one else has it. No server has it. We don't have it. Um and then you can later go back to this multi-party uh computation and say like hey I have a secret that is part of that computation and I am in fact unique. Uh and you can prove that to a platform. You could go to the social network and prove that you're a unique user to the social platform without us knowing anything about you or the social network knowing anything about you. And so it's this like very counterintuitive property that you there is like even though it uses biometrics you you know you preserve anonymity and and extreme levels of privacy which I think is super cool.

</details>

### AI时代机器人泛滥的挑战

**主持人**: 您知道，社交媒体是**机器人**活动的一个载体，以前是令人烦恼的，现在正变得势不可挡，尤其是**SCAM**宣传等等。如果我们将来无法实现**人类证明**，还有哪些**机器人**的使用会让人无法忍受？

<details>
<summary>Original English</summary>

**主持人**: You know social media is one kind of vector of, you know, things that were annoying and are now becoming overwhelming in terms of just bots, you know, particularly with SCOPS propaganda all these kinds of things. What are some of the other um, you know, uses of bots that are going to be kind of impossible to live with if we don't get to proof of human in the future?

</details>

**Alex**: 是的。实际上，我认为我对此的简单模型是，互联网上每一个主要关于人类相互交流的时刻，或者即使是间接相互交流的时刻。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Actually, I think the the simple model I have for it is every moment on the internet uh that is primarily about humans interacting with each other,

</details>

**Alex**: 您知道，您可以从简单的开始，比如约会，您知道，那真的很重要。

<details>
<summary>Original English</summary>

**Alex**: you know, or or even indirectly interacting with each other. So uh, you know, you can you can start with simple ones like dating you know that really matters.

</details>

**Alex**: 另一方确实是那个人。

<details>
<summary>Original English</summary>

**Alex**: What is the other side is in fact the person.

</details>

**主持人**: 是的。好吧，听众们，有个坏消息。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Well the got bad news for listeners.

</details>

**主持人**: 嗯，还有您所期望的那个人。

<details>
<summary>Original English</summary>

**主持人**: Well and the person who you expect it to be.

</details>

**Alex**: 是的。是的。是的。没错。我们甚至在**钓鱼**（catfish）事件之前就遇到过问题。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. Yeah. Exactly. We had the problems even before catfish thing.

</details>

**主持人**: 是的。没错。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Exactly.

</details>

**Alex**: 是的。是的。所以，那是一个显而易见的问题。嗯，例如，**Tinder**已经为此使用了它。嗯，我认为……

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. So that that that's that's an obvious one. Um and and so for example Tinder is already using it for that reason. Um I I think

</details>

**主持人**: **Tinder**的用例是什么？

<details>
<summary>Original English</summary>

**主持人**: and what what's the uh the Tinder use case? So

</details>

**Alex**: 所以我们从**日本**开始，作为测试市场，它本质上就是我们刚刚讨论的。如果您通过**Orb**验证，您会得到一个**小徽章**，它向其他人表明您确实是人类。所以它具有高水平的验证。嗯，然后，我认为那还没有上线，但接下来会发生的是，您实际上就是您声称的那个人。所以，这意味着您有一个**World ID**，它与您使用的个人资料图片相关联。

<details>
<summary>Original English</summary>

**Alex**: so we started we we started in Japan uh and like as as a test as a test market and it's essentially exactly what we just discussed. It is um if you verify it with an orb, you get a little badge that you know signals to other people that you are in fact a human. So it has a high level of verification. Um, and then also, um, I don't think that's live yet, but what will come next is that you're actually the person you claim to be. So, meaning you have a world ID that is associated to the kind of profile pictures that you use.

</details>

**Alex**: 嗯，所以您只需快速检查一下，确保这一切都是正确的。

<details>
<summary>Original English</summary>

**Alex**: Um, so you just run a quick check that, uh, this is all correct.

</details>

**Alex**: 嗯，所以，您知道，您就知道您不是在与机器人互动，而且您是在与一个完全真实的个人资料互动。

<details>
<summary>Original English</summary>

**Alex**: Um, and so, you know, you then know you're not interacting with bot, but also you, you know, you interact with a fully authentic profile.

</details>

**Alex**: 是的。另一个有趣的，因为我认为它有点反直觉，但我认为它会是**视频会议**。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Another fun one because I think it's somewhat counterintuitive but I think it will be video conferencing.

</details>

**Alex**: 嗯，因为您知道，您已经有了**深度伪造**（deepfakes）。

<details>
<summary>Original English</summary>

**Alex**: Uh because you know you already have deep fakes.

</details>

**主持人**: 是的。我只是不想参加这个视频会议。直接把我的**深度伪造**放上去。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Just I don't feel like going to this video conference. Just put my deep fake up.

</details>

**Alex**: 是的。实际上，您是第一个向我提出这个问题的，这就是为什么我们开始为此构建产品，因为您知道，它实际上将从非常**高价值用户**开始。您知道，例如，像您这样管理基金的人，有时电话会议的价值可能非常高，如果涉及借钱的话。

<details>
<summary>Original English</summary>

**Alex**: Yeah. And actually you um you raised it to me first and that's why we started building a product for it because you know it will actually start with very high value users you know like for example people you know like yourself that maybe manage a fund and you know sometimes calls actually could be very high value if it's about borrowing money or

</details>

**主持人**: 哦，是的，是的，是的。所以某人可以冒充我，然后说：“**Eric**，您能把这四亿美元电汇给这位尼日利亚王子吗？”

<details>
<summary>Original English</summary>

**主持人**: Oh yeah yeah yeah well so so somebody can uh be me and say Eric can you please wire this Nigerian prince $400 million

</details>

**Alex**: 没错，完全正确。嗯，很高兴知道。是的。

<details>
<summary>Original English</summary>

**Alex**: right exactly um Good to know. Yeah.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**Alex**: 是的。您知道，那仍然有点假想，因为这些事情还不是完全实时的，而且您在某种程度上可以……

<details>
<summary>Original English</summary>

**Alex**: Yeah. Like, you know, that's still slightly hypothetical because these these things are not fully real time and you can somewhat

</details>

**主持人**: 我们非常接近了。

<details>
<summary>Original English</summary>

**主持人**: we're very close

</details>

**Alex**: 但我们非常接近了，所以我认为，您知道，一年之内它就会成为一种完全的商品，它将是**超级照片级真实**的，并且绝对实时。您将不再在这些媒介上知道任何事情。

<details>
<summary>Original English</summary>

**Alex**: but we're very close and so I think, you know, in a year from now it's just going to be a full commodity and it's going to be super photorealistic and absolutely real time and you will just not know anything anymore on these vehicles and and so

</details>

**Alex**: 我认为那是另一个。嗯，我认为另一个会很有趣，但会是**游戏**。嗯，您知道，因为……

<details>
<summary>Original English</summary>

**Alex**: I think that's another one. Uh I think another one then will be which I think is fun but it's it's going to be gaming. Uh, you know, because

</details>

**主持人**: 哦，是的。是的。

<details>
<summary>Original English</summary>

**主持人**: Oh, yeah. Yeah.

</details>

**Alex**: 因为玩家真的很在意。

<details>
<summary>Original English</summary>

**Alex**: Because like gamers really care.

</details>

**主持人**: 哦，是的。他们没有和AI玩游戏。

<details>
<summary>Original English</summary>

**主持人**: Oh, yeah. That they're not playing a an AI.

</details>

**主持人**: 这令人沮丧。

<details>
<summary>Original English</summary>

**主持人**: That's frustrating.

</details>

**主持人**: 特别是如果我们赌钱的话。

<details>
<summary>Original English</summary>

**主持人**: Especially if we bet money.

</details>

**Alex**: 没错。而且您会输钱。您每天训练好几个小时才能在这方面变得非常出色，然后突然您就被一个在各个方面都**超人类**的AI摧毁了。

<details>
<summary>Original English</summary>

**Alex**: Exactly. And you you you lose money. You train multiple hours a day to get like really good at this thing and then suddenly you get, you know, you you get destroyed by an AI that is just super human in every dimension.

</details>

**Alex**: 嗯，有趣的是，我当时想，您对这一点有何看法，因为我对此没有一个好的心智模型，但即使是**视频平台**的整个模型，我认为也即将崩溃，因为这个问题有几个维度，但其中一个维度是，如果内容的创作变得**超级可扩展**。例如，我听说有个人……

<details>
<summary>Original English</summary>

**Alex**: Um, funny enough, I was like, I wonder what you think about this bit because I don't have a good mental model about it, but even the the whole model for video platforms, I think, is about to break because there's a couple dimensions to the problem, but one, if if if the if the creation of content is is becoming super scalable. Like for example, I heard about this one guy that

</details>

**Alex**: 嗯，他每天在**YouTube**上创建了大约一百个视频，每月赚取数万美元。所有这些视频都是完全**AI生成**的。

<details>
<summary>Original English</summary>

**Alex**: uh created I think like it was like on the order of a hundred videos a day on YouTube and made tens of thousands of dollars a month. All of them were fully AI generated.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Alex**: 嗯，人们只是上当了。所以现在的问题是，**YouTube**真的想以这种方式盈利吗？是的。那真的是……

<details>
<summary>Original English</summary>

**Alex**: Um and people just fell for it. So now the question is is that actually something that YouTube wants to monetize that way? Yeah. Like is that

</details>

**主持人**: 是的。嗯，这很有趣，对吧？他们上当了。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Well, it's it's interesting, right? They fell for it. Um

</details>

**Alex**: 但也许他们喜欢它。是的。可能是这样，但如果能知道这是**人类视频**还是**AI视频**，那肯定会很好。

<details>
<summary>Original English</summary>

**Alex**: but maybe they liked it. Yeah. like that could be, but it would sure be nice to know like, okay, this is a human video or this is an AI video. Um,

</details>

**Alex**: 实际上，我对这个问题的看法是这样的。

<details>
<summary>Original English</summary>

**Alex**: actually, my thesis about this is like something something along the lines of

</details>

**Alex**: 我认为有一些内容类别明显只是**虚构**的。

<details>
<summary>Original English</summary>

**Alex**: I think there's categories of content that are clearly just fictional.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Alex**: 比如电影就是这样。您知道，您不在乎它是否与现实有任何联系。它只是一个完全虚构的故事。但现在如果您想到像**TikTok**或所有这类东西，人们实际上非常关心它们，主要是因为它们与现实有一些联系，您知道。

<details>
<summary>Original English</summary>

**Alex**: Like movies are that, you know, it's like you you don't care that there's any connection to reality. It's just a fully fictional story. But now if you think about something like Tik Tok or, you know, all all these kind of things like people actually really care about them mostly because there is some connection to reality you know.

</details>

**主持人**: 是的。嗯，有现实，也有与人类的联系，对吧？所以，您可以创造一个相当好的……您可以拿一篇科学论文，然后交给**Gemini**，让它把它变成播客，您知道，它会是一个相当有趣的播客，而且它是真实的，因为它来自于某个真实的东西，但您会想知道这一点。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Well there's reality and there's connection to human right. So right you can create a pretty good p like you can take a scientific paper and give it to Gemini and say make this into a podcast and you know it'll be like a pretty entertaining podcast and it will be reality and that it came from you know some real thing but you would like to know that.

</details>

**Alex**: 您会想知道这一点。

<details>
<summary>Original English</summary>

**Alex**: You would like to know that.

</details>

**主持人**: 是的，我会想知道。

<details>
<summary>Original English</summary>

**主持人**: Yeah I would like to know that.

</details>

**Alex**: 然后它会继续发展，作为广告商，您会想知道是人类观看了它吗？

<details>
<summary>Original English</summary>

**Alex**: And then it continues as an advertiser you would like to know did a human watch it?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah

</details>

**Alex**: 还是AI观看了它？是的。没错。没错。嗯，没错。那是另一件事，我创建了一百个AI视频。我有一百万个AI观看了它。

<details>
<summary>Original English</summary>

**Alex**: or did an AI watch it? Yes. Right. Right. Well, right. That that's the other thing is I created a 100 AI videos. I had a million AIs watch it.

</details>

**主持人**: 是的。然后我从**YouTube**上赚了很多钱。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And then I made a lot of money off of YouTube.

</details>

**Alex**: 没错。我今天确实看到了一个**YouTube农场**的视频。

<details>
<summary>Original English</summary>

**Alex**: Exactly. And I actually saw that video today of a YouTube farm.

</details>

**Alex**: 就像他们有数千部手机，出于某种原因整天观看视频。

<details>
<summary>Original English</summary>

**Alex**: Like they had these like thousands of phones that just watch videos all day for a reason.

</details>

**主持人**: 是的。是的。然后，这对**YouTube广告商**来说毫无价值。所以，这对他们来说实际上是一个真正的问题，对吧？

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. And then like that's got zero value to the YouTube advertisers. And so that's that's actually a real problem for them,

</details>

**主持人**: 嗯，过去十年的整个**创作者经济平台**，您知道，**Substack**、**Spotify**，您知道，所有支持艺术家或**Patreon**的人，创作者、YouTube博主，他们与这些人之间存在个人关系。不仅仅是他们喜欢艺术，所以如果他们突然发现他们是机器人，您知道，他们可能就不想以同样的方式支持他们了。

<details>
<summary>Original English</summary>

**主持人**: right? Well, the whole sort of the creator economy platforms of the last decade, you know, Substack, Spotify, you know, and all the people who support artists or, you know, Patreon is that creators, YouTubers, they have a personal relationship with with with these people. It's not just they like the the art and so if they all of a sudden found out that they were, you know, bots that might, you know, they might not want to support them in the same way.

</details>

**Alex**: 是的。您可能不想给他们一个大的**YouTube**小费或……

<details>
<summary>Original English</summary>

**Alex**: Yeah. You might want not want to give them a a big YouTube tip or

</details>

**主持人**: 是的。我认为有一定比例的人支持，您知道，他们想支持真实的人，并感觉他们正在建立真实的关系。

<details>
<summary>Original English</summary>

**主持人**: Yeah. I think there's a certain subset of people who support um, you know, want to support actual people and feel like they're having a real relationship.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**Alex**: 而且我认为人们真正没有理解的是，您知道，这应该很明显，但我认为人们并没有真正理解其后果。我认为有两件事。一是我们目前所经历的，只是即将发生的事情的**超级微小**一部分。

<details>
<summary>Original English</summary>

**Alex**: And and the thing that I think like people don't really get is that you know it should be obvious but I don't think people really understand the the consequence of that. I think two things. One is that what we currently experience is like a super super tiny thing of what is about to happen you know just because like

</details>

**主持人**: 对，这只是一个**瞥见**。它只是一个瞥见，就像，您知道，**智能成本**几乎呈指数级下降，**代理能力**以某种超线性形式增长。

<details>
<summary>Original English</summary>

**主持人**: right it's a glimpse. It's a glimpse like, you know, cost of intelligence is dropping almost exponentially agent capabilities are increasing, you know, in like some super linear form like

</details>

**Alex**: 是的，我们现在看到的还不到未来一两年内可能出现情况的**百分之一**。所以……

<details>
<summary>Original English</summary>

**Alex**: yeah what we currently see is less than 1% of what it will look like in probably a year or two and so

</details>

**Alex**: 然后第二点是，这些东西实际上在许多方面将是**超人类**的。它们将能够完美地理解您，并以正确的方式与您交流。例如，有这样一篇论文，我认为它后来被删除了，但它是在**“改变我的想法”（change my mind）subreddit**上。

<details>
<summary>Original English</summary>

**Alex**: and then second these things will be actually they will be super human in many ways they will be like perfectly able to understand you and like talk in the right way to you for example there's this like one paper that I that I think it got deleted after but it was Um it was uh the change my mind subreddit.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**主持人**: Mhm.

</details>

**Alex**: 嗯，**苏黎世大学**在那里做了一件事，他们让人工智能与“改变我的想法”进行互动。

<details>
<summary>Original English</summary>

**Alex**: Um where the University of Zurich did this thing where they had AIs actually interact with change my mind.

</details>

**主持人**: 是的。而且他们在改变他人想法的能力上是**超人类**的，因为他们会回顾发帖人的个人资料。他们会理解他们的政治动机，他们的谈话方式，并且以完美的方式互动。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And they were like super human in their ability to change it because they they were going back to their profile of the people posting it. They were like understanding their political motivation, the way they talk and like and they're just interacting in perfect in the perfect way,

</details>

**主持人**: 您知道，就像击中所有按钮一样。

<details>
<summary>Original English</summary>

**主持人**: you know, and just like hit all the buttons and uh like

</details>

**主持人**: 人工智能非常擅长编程人类。远胜于人类编程人工智能。

<details>
<summary>Original English</summary>

**主持人**: AIS are really good at programming humans. That that's much better than humans are at programming AIs.

</details>

**Alex**: 绝对如此。毫无疑问。所以，我认为那也会变得相当可怕。但是，我认为至少如果您知道自己是**SCAM**的受害者，那么，如果它是一个由AI完成的非常先进的SCAM，这将非常有助于理解。

<details>
<summary>Original English</summary>

**Alex**: Absolutely. There's no question. And so I think that's going to get quite scary also. But uh I I think at least if you know you're being a victim of a scop then or or or it's a very advanced one done by an AI that would be extremely useful to understand.

</details>

**主持人**: 完全同意。

<details>
<summary>Original English</summary>

**主持人**: Totally.

</details>

### Worldcoin的发展与美国市场策略

**主持人**: 更多地谈谈**Worldcoin**产品和业务的现状吧，目前有多少ID？您能否提供一些更新，也许也谈谈其演变？

<details>
<summary>Original English</summary>

**主持人**: Talk a bit more about the state of the product in the business today like how many IDs are are out there why don't you give a little bit of an update maybe talk about the evolution as well.

</details>

**Alex**: 首先，这是一个多方面的问题，我认为您必须考虑大约三点。第一，嗯，您需要平台来使用这项技术，您知道，比如**Reddit**、**X**之类的。嗯，其次，您需要这些设备的**分发**。我认为正确的思维模型是，一个人平均需要多少分钟才能接触到这样的设备？您知道，目前如果取全球平均值，那将是一个糟糕的数字，可能是几天之类的，因为很多人需要坐飞机。但是，您知道，我们如何才能将这个数字在美国境内降到15分钟以下？这意味着您需要部署大约**五万台设备**。这并不是疯狂的数字，但也绝非小事。这，您知道，很难做到。然后最后一个是，所有这些如何结合在一起，成为许多人真正想要使用的东西。这结合了所有**子平台**的效用，但所有这些都层叠在其上，比如您也许可以在您的**Reddit**账户上使用它，也许您会免费获得一定数量的**TBD**订阅。所以，我认为这将是多种因素的结合，但您需要在某个时候同时实现所有这三点，这很难做到。我们现在有**1800万**经过验证的用户，**应用程序**总共有4000万。嗯，但最大的问题是，由于过去的政策，因为我们使用**加密货币**，我们长期以来没有真正在美国投资。

<details>
<summary>Original English</summary>

**Alex**: Well first of all it's a multi-sided problem and I think there's like roughly three that you have to consider. One is uh well, you need platforms to use the technology uh then you know like things like Reddit or, you know, X or, you know, things like that. Um secondly you need uh distribution of these devices and I think the right mental model to to have for it is how many minutes does it take a person to reach such a device on average and you know currently it's if you would take the global average it would be terrible number it would be like, you know, days or something because many people would need to fly but but, you know, how do we get that down to below 15 minutes across the US and so that's probably roughly around 50,000 devices that you need to deploy. That's like it's not crazy, but it's also not nothing. It's it's, you know, it's hard to do. And then the last one is how does all of that come together to something that a lot of people really want to use it. And that's a combination of you know the utility of all the subplatforms essentially but but all that layers on top like maybe you can use on your Reddit account maybe you get like, you know, certain amount of TBD subscription for free like so I think it's going to be a combination of things but you need to you need to land all three at some point at the same time which is uh which is hard to do. We are now at 18 million users that are verified 40 million in total in the app. Uh but the biggest thing is because of the past administration because we use, you know, we use crypto we we did not really invest in the US for a long time and um that's not the main shift that we're going through like

</details>

**Alex**: 对于所有这些，最重要的是**美国**。

<details>
<summary>Original English</summary>

**Alex**: for all of this the main thing that matters is the US

</details>

**主持人**: 希望我们能尽快通过《**清晰法案**》（Clarity Act），那将……

<details>
<summary>Original English</summary>

**主持人**: and hopefully uh we get the clarity act passed shortly that

</details>

**Alex**: 是的，没错，那会很棒的，所以，嗯，为了明确这一点。

<details>
<summary>Original English</summary>

**Alex**: yeah exactly that would be really great so um to get clarity on that

</details>

**Alex**: 是的，所以我们现在正在经历的重点是全面进军**美国**。所以，我认为在明年，公司90%的精力都将集中在**美国**。您如何提高设备分发量？您如何最终让**Orb**出现在每一家**星巴克**？嗯，所以它变得非常普遍，人们每天都在使用它。所以这就是那种……

<details>
<summary>Original English</summary>

**Alex**: yeah so so the big focus that we that we now are going through right now is to kind of go all in on the US. So I think over the next year 90% of the of the, you know, effort of the company is just going to go about the US and how do you get for example device distribution up? How how do you eventually have this in every Starbucks? Um so it becomes just, you know, super normal and people just just use it every day. So that's kind of the

</details>

**Alex**: 然后在平台方面，我们实际上经历了一个……嗯，那是一次非常有趣的个人经历，因为我认为，嗯，就像几年前，人们普遍都在嘲笑我们。

<details>
<summary>Original English</summary>

**Alex**: and then on the platform side actually we went through a it's um it was a very interesting experience to go through personally because I think um like a couple of years ago universally people just made fun of us, you know, like just it was like the universal reaction uh well minus and recre and a couple other people who believed in it but um

</details>

**主持人**: 是的，就像媒体一样，那种嘲笑的程度，它只是表明人们是多么**短视**。

<details>
<summary>Original English</summary>

**主持人**: yeah like and the press like like the amount of fun making of something that it just shows short-sighted people are.

</details>

**Alex**: 没错。

<details>
<summary>Original English</summary>

**Alex**: That's right.

</details>

**Alex**: 就像，您不认为**机器人**会来吗？

<details>
<summary>Original English</summary>

**Alex**: It's like, do you don't think the bots are coming?

</details>

**主持人**: 当我们第一次推销时您怎么想的，因为即使您也一定认为这很疯狂。

<details>
<summary>Original English</summary>

**主持人**: What did you think when when we first pitched actually because even you must have thought this is crazy.

</details>

**Alex**: 嗯，因为您有**Orb**，**Orb**是如此……

<details>
<summary>Original English</summary>

**Alex**: Well, because you had the orb like the orb was so

</details>

**Alex**: 狂野。嗯，您知道，好吧，我们要扫描人们的视网膜，这就是我们知道他们是人类的方式等等。这，我的意思是，您向我们推销时是……

<details>
<summary>Original English</summary>

**Alex**: wild. Um, you know, okay, we're going to scan people's retinas and that's how we're going to know they're human and so forth. And this was, I mean, you pitched us

</details>

**主持人**: 六年前。六年前。

<details>
<summary>Original English</summary>

**主持人**: six years ago. Six years ago.

</details>

**Alex**: 是的。那是在疫情之前，因为您带着**Orb**在那里，对吗？嗯，您知道，**AI**当时还没有发生。

<details>
<summary>Original English</summary>

**Alex**: Yeah. It was before COVID because you were there with the orb, right? Um, and you know, AI just hadn't happened yet.

</details>

**Alex**: 而且，您知道，您能看到一些，但那时有机器人。嗯，但它们当时非常粗糙，您知道，与现在相比。嗯，但它似乎是不可避免的。嗯，至少在当时，您知道，问题在于它太**超前**了，它太来自未来了，以至于我们总是担心，好吧，这方面的时间安排是什么等等。嗯，但您知道，您足够令人印象深刻，而且它最终会发生，这是一个足够令人兴奋的想法，我认为所有这些都让我们觉得，好吧，我们……但它并不明显，并不是说它会在那个时间框架内奏效。

<details>
<summary>Original English</summary>

**Alex**: And and you know, you could kind of see, but there you know, there there's bots. Um, but they were kind of very crude and, you know, compared to what there are now. Um, but it uh it seemed inevitable. Um, at least at the time, you know, the thing was it was so out of it was so from the future that uh, you know, we always worry about, okay, like what's the timing of this and this and that and the other and and so forth. Um, but you know, you were impressive enough and it was going to happen eventually and it was an exciting enough idea that I think all those things kind of got us to go, okay, we're um but but it was not it was one of it wasn't obvious that like it was going to work in that time frame.

</details>

**主持人**: 很长一段时间它看起来都非常不明显。那个推销与最终的结果有什么不同？或者多说一点。

<details>
<summary>Original English</summary>

**主持人**: It seemed very inobvious for a long time. And how different was that pitch from what it ended up being or talk a little bit.

</details>

**Alex**: 实际上，那几乎是完全相同的推销。

<details>
<summary>Original English</summary>

**Alex**: It was actually pretty much exactly the same pitch.

</details>

**Alex**: 我认为这是同一件事。设备变了。您知道，他们让它变得更经济、更方便，但是……

<details>
<summary>Original English</summary>

**Alex**: I think it's the same thing. the device changed. You you know they've they've made it much more economical and convenient, but

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**主持人**: that's right.

</details>

**Alex**: 它……

<details>
<summary>Original English</summary>

**Alex**: It's uh

</details>

**主持人**: 但最初的直觉是正确的，它就在那里。

<details>
<summary>Original English</summary>

**主持人**: but the initial instinct was right was there.

</details>

**Alex**: 它基本上是：每个人都必须证明他们是……您要么必须有一些证明您在**网络空间**是人类的证据，否则……

<details>
<summary>Original English</summary>

**Alex**: It was basically everybody's going to have to prove they're you're either going to have to have some proof that you're human on in cyerspace or like

</details>

**Alex**: 那将是一个非常糟糕的世界。我的意思是，机器人会抓住我们。我们完了。

<details>
<summary>Original English</summary>

**Alex**: it's going to be a very bad world. I mean the robots are gonna get us. We're done,

</details>

**主持人**: 对吧？然后实际上第二部分是，第一点是它本身将是一个大问题，然后第二点是，当它成为一个大问题时，我们将能够因此建立最有价值的网络之一，因为在一个AI的世界里，拥有一个**人类网络**将是一件极其重要的事情。嗯，所以实际上有两件事：第一，您需要证明您是人类，然后第二，它将具有非常强的**网络效应**。

<details>
<summary>Original English</summary>

**主持人**: right? And then actually the second piece of it was like this was the first thing is like it's going to be that itself is going to be a big deal but then second of all that you know when it's going to become a big deal we will be able to build one of the most valuable networks as a result of that because in a world of AI having a human network is going to be this incredibly important thing and uh and so actually yeah two things like one you will need to prove human but then second it will have very strong network effects

</details>

**主持人**: 而且即使是平台，当您进入平台时，即使平台最大的问题一直是**机器人**。我的意思是，您还记得**Elon**，以及他退出购买**Twitter**的原因，就是因为所有的数据都基于机器人。

<details>
<summary>Original English</summary>

**主持人**: and even as the platforms as you get into the platforms even as the platform's largest problem has been bots. I mean you remember Elon and the, you know, he backed out of buying Twitter because all the stats were based on bots.

</details>

**主持人**: 他们仍然，即使知道这一点，也很难完全展望未来并说：“是的，我们需要**人类证明**。”

<details>
<summary>Original English</summary>

**主持人**: They still even knowing that it was hard for them to get all the way to the future in their thinking and go yeah we need proof of human.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**主持人**: 就像这很明显一样。

<details>
<summary>Original English</summary>

**主持人**: Like it's kind of obvious.

</details>

**Alex**: 是的。因为人们当时想：“这到底是什么意思？**人类证明**到底是什么意思？我们不能就这样……”

<details>
<summary>Original English</summary>

**Alex**: Yeah. Because people were like what does it even mean? You know like what does proof of human even mean? We can just we can just, you know,

</details>

**主持人**: 那您有链接吗？

<details>
<summary>Original English</summary>

**主持人**: and did you have the link

</details>

**主持人**: **检测工具**？您什么时候想出“**人类证明**”这个说法的？

<details>
<summary>Original English</summary>

**主持人**: detection tools? When did you come up with the language proof of human?

</details>

**Alex**: 我们实际上长期以来都有“**人格证明**”（Proof of Personhood）。在这个简报中也有提到。

<details>
<summary>Original English</summary>

**Alex**: We had actually we we had proof of personhood for the longest time. It's even here in this on this brief.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Alex**: 但后来，嗯，在某个时候我们想：“好吧，在某个时候，AI也会拥有**人格**的。”所以……

<details>
<summary>Original English</summary>

**Alex**: But then uh at some point we're like, "Well, at some point AIs will have personal too. So

</details>

**Alex**: 嗯，所以那行不通了。

<details>
<summary>Original English</summary>

**Alex**: uh so like that's not going to fly. So

</details>

**主持人**: 是的，但他们很长一段时间都不会有视网膜。

<details>
<summary>Original English</summary>

**主持人**: yeah, but they're not going to have retinas for a long time.

</details>

**Alex**: 那最终会到来。

<details>
<summary>Original English</summary>

**Alex**: That's coming eventually.

</details>

**Alex**: 实际上非常有趣。当时**OpenAI**的一些人，我遇到的一些人，他们说：“伙计，Alex，这会很黑暗。人们会因为您不给予**个人AI**而恨您。”我当时想：“天哪，好吧，那我们叫它**人类证明**吧。”

<details>
<summary>Original English</summary>

**Alex**: It was actually really funny. It was like some of the some of the OpenAI people uh that I met were like, "Man, Alex, this is going to this is going to be so dark. Like people will hate you for like not giving personal AI." And I was like, "Jesus, all right, let's let's call it proof of human then." Um

</details>

**主持人**: 这很有趣。

<details>
<summary>Original English</summary>

**主持人**: that's funny.

</details>

**Alex**: 所以这就是它改变的原因。嗯，但那实际上是……所以我会说，去年，也就是在那之后，在**ChatGPT**之后有一个巨大的转变，人们觉得AI突然变得真实了。然后实际上我认为，从那时起人们开始与我们交谈，但仍然不是那种：“您知道，这是一个未来的问题，可能还有几年时间，我们并不真正关心它，让我们保持联系吧。”那是常见的回复。然后……

<details>
<summary>Original English</summary>

**Alex**: So that that's how it changed. Um but that actually so then I would say like last year so post then there was like a big shift post post chat GBT like people were like that was like the AI suddenly got real to people and then actually I think and so that's when people started talking to us but still were not like, you know, like it's a future problem it's probably couple years out like we don't really care about it let's stay in touch like that was like the common response and then

</details>

**Alex**: 嗯，您知道，好吧，但您也有一些真正相信它的**CEO**，他们愿意进行长期押注，嗯，这要归功于他们。但我认为第二次重大转变实际上是最近的**ClaudeBots**和**Moldbook**。

<details>
<summary>Original English</summary>

**Alex**: uh, you know, and well but you also you had couple CEOs that really believed it and were like willing to take the long-term bet um to to give them credit. But I think the second big shift was actually Claudebots and Moldbook recently.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Alex**: 仅仅因为……

<details>
<summary>Original English</summary>

**Alex**: Just because

</details>

**主持人**: 是的。那意味着牛已经跑出谷仓了。

<details>
<summary>Original English</summary>

**主持人**: Yeah. That that kind of means like the the cow is way out of the barn.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**Alex**: 是的。所以，说实话，如果您现在不认真对待，

<details>
<summary>Original English</summary>

**Alex**: Yeah. And so like honestly if you don't take it serious now

</details>

**Alex**: 那么我认为您就应该换个工作什么的。

<details>
<summary>Original English</summary>

**Alex**: then I think you just you should get a different job or something.

</details>

**Alex**: 是的，他们只是没有以正确的方式思考**ROM**。就像，那是一个许多人开始与我们联系的时刻，现在感觉更多是一个执行问题，不再是**市场风险**。

<details>
<summary>Original English</summary>

**Alex**: Yeah, they're just not not thinking about ROMs in the right way. Like it's and so that's that was like the moment when many many people started reaching out and now now it feels like much more of an executional problem. Not not anymore

</details>

**主持人**: 市场风险。

<details>
<summary>Original English</summary>

**主持人**: market risk

</details>

**Alex**: 像市场风险，或像论文问题，或像……这仍然是一个大问题。您如何将**五万台设备**分发出去？您如何使其足够便宜？您如何使其经济？您知道，您如何同时做到这三件事仍然是一个非常困难的问题。您如何使这种行为正常化等等？这样人们就不会在**星巴克**之类的场合感到奇怪。

<details>
<summary>Original English</summary>

**Alex**: like a market risk or like a thesis problem or like like just a and which is still a big problem. Like how do you how do you how do you get 50,000 devices out there? How how do you make it cheap enough? How do you make it economic? Like, you know, how how do you make all these three things at the same time is still a very hard problem. How do you normalize the behavior, etc. So people aren't weirded out in a Starbucks or something?

</details>

**主持人**: 尽管我认为现在会是……

<details>
<summary>Original English</summary>

**主持人**: Although I I think that's now going to be

</details>

**Alex**: 您会习惯的。

<details>
<summary>Original English</summary>

**Alex**: what you get used to.

</details>

**Alex**: 我只是因为我认为人们会非常讨厌替代方案。

<details>
<summary>Original English</summary>

**Alex**: I just because I think people will hate the alternative so much.

</details>

**主持人**: 而且我认为人们会，顺便说一下，会在线上更加为自己是人类而感到自豪，尤其是在线上，因为我认为人们会开始被指责是机器人。我的意思是，这会变得非常奇怪。嗯，如果没有明确的界定，那将是一团糟。我不知道有人怎么会认为他们可以拥有一个不区分人类和机器人的社交媒体平台。这对我来说似乎很荒谬。

<details>
<summary>Original English</summary>

**主持人**: And I think people are going to by the way take a lot more pride in being human. Uh particularly online because I I think that people are going to start getting accused of being bots. I mean like it's it's going to get really weird. Um, and without like clear delineation, it's it's going to be a mess. Like I don't I don't understand how somebody can think they're going to have a social media platform that doesn't distinguish between humans and bots. Like that seems absurd to me.

</details>

**Alex**: 似乎很荒谬。我猜测在接下来的几个月里，我们会看到这些平台尝试使用手机上的**面部生物识别技术**之类的东西，您知道，我知道它会失效，所以没关系，但我认为我们现在会经历这个周期。嗯，是的，所以我们只需要足够快地扩大规模，以满足市场对后续产品的需求。我认为像**Orb**这样的东西是唯一的解决方案。我认为目前没有真正的竞争对手。我认为我们也会看到这一点。

<details>
<summary>Original English</summary>

**Alex**: Seems absurd. I think we will my guess is over the next couple months we will see we will see things like these platforms trying to use things like face biometrics on the phone which, you know, I know it will break so it's fine but I think we'll go through that cycle now uh and yeah so we just need to get to scale fast enough to to meet uh the market to what comes after which I think something like the orb is the only solution I think currently there's no real competition I think we'll also to see that.

</details>

**主持人**: 我还没有看到竞争对手，因为……

<details>
<summary>Original English</summary>

**主持人**: I have not seen a competitor yet because

</details>

**Alex**: 因为它太荒谬了。

<details>
<summary>Original English</summary>

**Alex**: because it's so ridiculous.

</details>

**Alex**: 它太荒谬了，而且在构建方面如此困难，然后又有一个巨大的**网络效应**。

<details>
<summary>Original English</summary>

**Alex**: It's so ridiculous and it it was so hard to get to in terms of building it and then there's a massive network effect. Um,

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right,

</details>

**主持人**: 这就像人们落后了六年。但是……

<details>
<summary>Original English</summary>

**主持人**: which like people are starting six years behind you on that. But

</details>

**Alex**: 是的，我确信那会到来，因为它现在只是一个如此明显的问题。

<details>
<summary>Original English</summary>

**Alex**: yeah, I'm sure that'll come because it's it's just such an obvious problem now.

</details>

### AI与经济政策及民主

**主持人**: 您实际上认为**AI**会带来什么？在您看来，我们需要实施或指导哪些**经济政策**？

<details>
<summary>Original English</summary>

**主持人**: What actually do you think about like AI continues? What in your mind are the economic policies that we will need to implement or directionally?

</details>

**主持人**: 我认为政府必须找出如何向公民发钱的方式。他们擅长从公民那里收钱，而不是相反。我的意思是，如果回到**疫情**刺激计划……

<details>
<summary>Original English</summary>

**主持人**: I think governments do have to figure out how to send citizens money they're good at taking money from citizens but not the reverse. I mean well just if you go back to co the stimulus program

</details>

**主持人**: 我认为**四千亿美元**被盗了。

<details>
<summary>Original English</summary>

**主持人**: like I think $400 billion was stolen

</details>

**主持人**: 就像，您会想知道您正在把钱发给独特的人类。我的意思是，即使不是公民，只要他们是独特的人类，那也会很好。

<details>
<summary>Original English</summary>

**主持人**: like that that that's pretty you would have liked to know that you were sending the money to unique humans. I mean, if even if not citizens, as long as they were unique humans, that would have been good.

</details>

**Alex**: 是的。我的意思是，例如，**美国**的**社会保障系统**一团糟。它……

<details>
<summary>Original English</summary>

**Alex**: Yeah. I mean, the social security system, for example, is a mess in the US. It's

</details>

**主持人**: 疯狂。完全是一场灾难。所以，我们必须找到某种方法，以**加密强度**的方式识别谁是哪个国家的公民。就像，那将是一个非常糟糕的问题。嗯，否则，我认为……

<details>
<summary>Original English</summary>

**主持人**: insane. Is a total disaster. So, we're going to have to get to some kind of way to cryptographically strong way to identify who's the citizen of what country. Like, like like that's going to be a really bad problem. Um I think otherwise

</details>

**主持人**: 甚至无法拥有**民主**。我的意思是，您知道，他们试图通过《**安全投票法案**》（SAVE Act）做的事情相当粗糙，但这并非完全疯狂，即……

<details>
<summary>Original English</summary>

**主持人**: there's no way to even have a democracy. I mean, you know, like the it's pretty crude what they're trying to do with the save act but it's not completely insane which is

</details>

**主持人**: 您甚至如何知道投票的人是真实的人还是活着的人？我们现在真的不知道。嗯，我们真的不知道。然后如果您看，我的意思是，整个**邮寄选票**的事情，是为整个非常不同的世界而建立的，对吗？

<details>
<summary>Original English</summary>

**主持人**: how do you even know like the people are voting are actual people or living people or anything and we really don't know now. Um like we genuinely don't know and then if you go to I mean the the whole mailin ballot thing like is built for a whole very different world right

</details>

**Alex**: 没错。

<details>
<summary>Original English</summary>

**Alex**: that's right

</details>

**主持人**: 嗯，所以，我认为在一个**AI世界**中，您可能会有**大规模的冒充**，然后再加上一个**破碎的社会保障系统**，您就不会再拥有**人民的意愿**了。我认为那会很快消失。所以，我认为我们需要某种，您知道，在“谁是谁”方面的**加密基础设施**。嗯，然后，您知道，类似地，我认为我们将不得不能够比通过我们拥有的这种疯狂的**社会计划**机构更有效地向人们提供资金。嗯，仅仅因为像**社会保障**或**医疗保险**或任何这些东西的损失和欺诈程度有多高？我的意思是，像**医疗保险**对人们来说是如此令人沮丧，以至于他们枪杀了**联合健康集团**的**CEO**，人们对此很高兴，真的很高兴。所以想想那是一个多么糟糕的系统。嗯，当您知道，政府花了很多钱为您的医疗保健提供资金，但他们以一种超级低效的方式进行。嗯，但我们现在拥有技术可以做到这一点。所以，我认为**AI**将使这个问题变得如此糟糕。嗯，因为提交欺诈性索赔和创建虚假信息的能力，您知道，购买社会……我的意思是，您可以在黑市上购买**社会保障号码**，对于那些不知道的人来说，这是一件容易的事情，这是真实的事情，就像每个人的**社会保障号码**都在出售一样。嗯，所以，您知道，**AI**只是一种使那种松散的**黑市地下欺诈**活动变得大规模和极度可扩展的方式。

<details>
<summary>Original English</summary>

**主持人**: uh so like I don't think in an AI world where you can have like very high scale impersonation that and then with a broken social security system that like you're going to have the will of the people anymore like I I think that's going to be gone pretty fast so I think we're going to need some kind of, you know, cryptographically strong infrastructure on like who's who. Um, and then, you know, similarly, I think we're going to have to be able to get people money much more efficiently than through these uh this crazy apparatus of social programs that we have. Uh, just cuz like how lossy is and fraudulent is social security or Medicare or any of these things? I mean like the Medicare is so frustrating for people that they shot the CEO of United Healthcare like and people are happy about that like really happy. So like think about how bad a system that is. Um when you know and the government spends a lot of money sending you money for your health care but they do it in a like super inefficient way. Um but we have the technology to do that now. So I think that AI is going to make that problem so bad. Uh because the ability to file fraudulent claims and create fake, you know, buy social I mean you can buy social security numbers on the black market like for those of you who don't know that's an easy thing that's a real thing like that is like everybody's social security number is for sale uh and so um, you know, like AI is just a way of making that kind of loose black market underground fraud thing just massive and extremely scalable.

</details>

**Alex**: 我同意。

<details>
<summary>Original English</summary>

**Alex**: I agree s.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Alex**: 所以我，我，我，我认为，您知道，**人类证明**是一个非常重要难题的一部分，我们需要升级整个基础设施，否则我们将不再是**民主国家**。我的意思是，那只是我的猜测。我同意。

<details>
<summary>Original English</summary>

**Alex**: So I I I I think, you know, proof of human is a piece of a very important puzzle where we have to upgrade the entire infrastructure or we're not going to be a democracy anymore. I mean that that just be my guess. I agree. Tom

</details>

### Worldcoin的未来展望与市场策略

**主持人**: 再多分享一些。您说，明年市场将重点关注**美国**。多谈谈您是如何考虑这个问题的？人们参与的动机是因为他们可以使用一套服务吗？还有其他经济激励吗？或者您是如何构想的？

<details>
<summary>Original English</summary>

**主持人**: Share more. You said okay next year go to market is focused on on the US. Say more about how how you're thinking about that is the incentive for people to do it because they get to use a set of services. Is there some other economic incentive or how do you envision it?

</details>

**Alex**: 基本上，一个月前，我们作为项目进入了一个非常不同的阶段，我相信我们现在正在整合的许多平台，您知道，它们将为我们的平台带来大量用户，这完全改变了您的看法。就像如果您有一个拥有十亿用户的平台。

<details>
<summary>Original English</summary>

**Alex**: Basically, a month ago, we entered a very different phase as a project where I do believe many of the platforms that we're now integrating with will, you know, bring a lot of users to our platform and that changes, you know, how you think about it entirely. Like if you have a you have a platform of a billion users

</details>

**Alex**: 嗯，将用户发送给您，那么这实际上就是关于您如何满足这种需求。就像，您知道，这正是我们现在正在进入的阶段。所以……

<details>
<summary>Original English</summary>

**Alex**: um sending users to you then it's really just all about like how do you meet that demand? It's like, you know, and that's that's that's what we're now entering and and so

</details>

**Alex**: 嗯，是的，所以我认为第一个回应是，嗯，我认为您会看到，而且我们已经在为此努力了，但您会看到很多非常大的平台，它们将在近期整合。

<details>
<summary>Original English</summary>

**Alex**: um yeah so I think the response is first um I think you will see and we're already working on it but you will see a lot of really large platforms that you know integrate uh in the in the near term future.

</details>

**Alex**: 我认为那最初会很慢，只是为了设定预期，因为它也应该只是，您知道，为了了解产品。它将专注于某些地理区域，就像我们在**日本**的**Tinder**商店所做的那样，只是为了，您知道，测试产品，并使这个概念正常化。嗯，但这会发生。然后……

<details>
<summary>Original English</summary>

**Alex**: I think that will just to set expectations. I think that will be slow initially because it also should be just, you know, to to get understand the product. It will be focused on certain geographies like what we did with Tinder store in Japan just to, you know, to uh to test the product and also to just normalize the concept. Uh but that will happen. And then

</details>

**Alex**: 其次，现在这对我来说是主要优先事项之一，就是如何提高**Orb**的分发量。这，您知道，广义上讲有几个不同的维度，但其中一个首先是产品需要在没有监督的情况下大规模运行，这比您想象的要困难得多。您知道，每个大规模的工程问题都比您想象的要复杂得多，因为，您知道，为了1%的质量提升而奋斗，涉及所有这些依赖关系聚集在一起。所以，我认为这是现在最大的工程重点之一。然后其次……

<details>
<summary>Original English</summary>

**Alex**: secondly, which is now becoming like one of the main priorities for me is just how do you get this orb distribution up which is which is, you know, broadly speaking there's a couple different dimensions to that but one is first of all the product needs to work at scale uh, you know, without supervision which is turns out to be much harder than you would think. You know, every engineering problem at scale turns out to be much more complicated than you would think because, you know, fighting for 1% of improvement in quality is this cluster of, you know, all these dependencies to come together. So that's I think that's like one of the biggest engineering focuses right now. Then second

</details>

**Alex**: 嗯，您需要找到部署它们的地方。考虑这个问题的方式是，有一些大规模的分发合作伙伴关系，比如**沃尔玛**，您知道，或者如果您非常有抱负，它可能是**星巴克**。

<details>
<summary>Original English</summary>

**Alex**: um you need to find places to deploy them at and and the way to think about it is there are large scale distribution partnerships that could be something like Walmart, you know, or if you if you're very ambitious it could be something like Starbucks

</details>

**Alex**: 嗯，或者它可以只是您去一家时尚咖啡馆，然后把它放在那里，或者您知道，然后您最终甚至可以去**DMV**（机动车辆管理局）并把它放在那里。

<details>
<summary>Original English</summary>

**Alex**: um or it it can just be you go to one of, you know, hip coffee shops and you just you just put it there or you know, and then it you could go you could eventually even go to the DMV and just put it right

</details>

**Alex**: 所以这就是我们目前正在努力解决的问题。嗯，您知道，这将是所有这些的结合。我认为将会有一些大规模的分发合作伙伴关系，以及许多独立的咖啡馆。哦，实际上有一件事我们很快就会推出，团队会讨厌我现在说这个，但，嗯，那将是**按需Orb**（Orb on demand）。是的。所以，在**湾区**，仅仅因为这实际上是一个如此棘手的问题，您知道，要让**Orb**真正到达每个人，您知道，这就像，资本支出是巨大的。

<details>
<summary>Original English</summary>

**Alex**: So that's the problem we're currently trying to trying to puzzle together. Um, and you know, it's going to be some some of all of that. I think there's going to be some large scale distribution partnerships, many one-off coffee shops. Oh, actually one thing that we will uh we will launch soon and the team is going to hate that I'm saying this now, but uh it's going to be orb on demand. Yeah. So, so in the Bay just because actually it's such it's such a gnarly problem to, you know, to get an orb to truly everyone, you know, it's like to to get that the capex is insane.

</details>

**主持人**: 所以实际上，将**Orb**放在摩托车上，然后开到您身边，实际上更便宜、更容易。

<details>
<summary>Original English</summary>

**主持人**: So it's actually it's actually much cheaper and easier to just put an orb on a motorbike and drive it to you as as crazy

</details>

**Alex**: 听起来多么疯狂。所以，在像**湾区**或**纽约**这样的地方，您将能够说：“是的，我现在想验证。”

<details>
<summary>Original English</summary>

**Alex**: as as crazy as it sounds. So like in in places like the Bay Area or New York, you will just be able to say like, "Yeah, I want to verify now

</details>

**Alex**: 15分钟后，**Orb**就会来到您身边，您可以进行验证。而且，嗯……

<details>
<summary>Original English</summary>

**Alex**: and 15 minutes later there's an orb comes to to your can you can verify." And uh

</details>

**主持人**: 您有没有想过，嗯，我不知道，这可能是一个糟糕的主意，但，嗯，有不同级别的验证，比如我们知道您是一个独特的人类，或者这个人可能是一个独特的人类，因为他是在他的**iPhone**上完成的，这不太一样。但是……

<details>
<summary>Original English</summary>

**主持人**: did you ever think about uh I don't know, this is probably a terrible idea, but um having kind of different levels like we know you're a unique human or like this guy may be unique human because he's done it on his iPhone and it's not quite the the same. But

</details>

**Alex**: 是的。是的。我们有这个。所以实际上，嗯，您知道，一般来说，我们只是秉持一个原则，即任何对这个问题有用的东西，我们都会去构建它。

<details>
<summary>Original English</summary>

**Alex**: yeah. Yeah. we we have that. So actually we um, you know, generally we just have the you know, we have the principle of, you know, what whatever could be useful for this problem we just build it

</details>

**Alex**: 而且，嗯，所以我们有一个叫做**面部检查**（face check）的东西，它就是做这个的。所以它使用……

<details>
<summary>Original English</summary>

**Alex**: and and uh and so we we have something called face check that that does that. So it uses

</details>

**Alex**: 它使用来自摄像头的面部识别。它仍然使用我们为整个系统构建的**多方计算**。所以您仍然是匿名的。

<details>
<summary>Original English</summary>

**Alex**: it uses face uh from the camera. It still uses multi-party computation what we've built for the entire system. So you're still anonymous.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**主持人**: Mhm.

</details>

**Alex**: 嗯，您知道，它的准确性当然要低得多。所以，嗯，您知道，作为一个系统，您会知道一些类似这样的信息：嗯，这至少可以防止一个人创建一百个账户，也许只能创建十个或二十个。所以，它至少提供了一些**速率限制**措施。

<details>
<summary>Original English</summary>

**Alex**: Um and, you know, it of course reaches way less accuracy. So, uh, you know, as a system you will know something along the lines of, well, this is, you know, at least one person cannot create 100 accounts, maybe it's just 10 or 20. So like it's like a at least it's some measure of rate limiting.

</details>

**Alex**: 嗯，我确实认为，为了声明，我认为随着**深度伪造**和所有这些东西的出现，我认为这会从根本上失效。所以它是一个……

<details>
<summary>Original English</summary>

**Alex**: Um and I do think just to set a disclaimer I think with deep fakes and, you know, all this stuff I think that will fundamentally break. So it's a

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**主持人**: Mhm.

</details>

**Alex**: 它是一个临时的解决方案，我认为可以帮助我们实现规模化。我就是这样看待它的。

<details>
<summary>Original English</summary>

**Alex**: it's it's a temporary solution that I think can get us to scale. That's kind of how I think about it.

</details>

**Alex**: 嗯，我们实际上也使用**政府ID**，类似地，我们只使用带有**NFC ID芯片**的ID。

<details>
<summary>Original English</summary>

**Alex**: Uh we also actually use government IDs uh similarly where like we we use just the ones that have an NFC ID chip.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**主持人**: Mhm.

</details>

**Alex**: 嗯，我们使用**多方计算**，所以您保持匿名，平台也可以选择使用它，但没有人真正这样做。它只是不知何故带有一种非常负面的耻辱，我认为这很合理。

<details>
<summary>Original English</summary>

**Alex**: Um and we use multi-party computation so you remain anonymous and platforms can choose to use that as well but no one really did. It's just somehow they have this like very negative stigma which I think makes sense.

</details>

**Alex**: 是的。嗯，但是的，基本上任何能做到的。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Um but yeah, basically whatever could do it.

</details>

**主持人**: 是的，不惜一切代价。

<details>
<summary>Original English</summary>

**主持人**: Yeah, by any means necessary.

</details>

**Alex**: 没错。

<details>
<summary>Original English</summary>

**Alex**: That's right.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**主持人**: 嗯，非常感谢您来参加播客。太棒了。

<details>
<summary>Original English</summary>

**主持人**: Well, thanks so much for coming on the podcast. It's been great.

</details>

**Alex**: 是的。谢谢您。谢谢您。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Thank you. Thank you.

</details>

**Alex**: 谢谢邀请。

<details>
<summary>Original English</summary>

**Alex**: Thanks for having me.

</details>