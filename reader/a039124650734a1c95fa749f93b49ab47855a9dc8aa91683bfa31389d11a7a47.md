---
author: Latent Space
date: '2026-06-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=T8u7wOXhDb0
speaker: Latent Space
tags:
  - prompt-engineering
  - agent-behavior
  - ai-evaluation
  - multi-agent-systems
  - robotics
title: 当AI智能体运营企业：Anden Labs的Lukas Petersson和Axel Backlund访谈
summary: Anden Labs的创始人Lukas Petersson和Axel Backlund分享了他们如何通过VendingBench和Project Vend等项目，评估AI智能体在商业运营和现实世界中的能力。他们讨论了AI智能体从简单的贩卖机管理到多智能体协作（如CEO和设计师智能体）的演进，揭示了模型在长程任务中可能出现的欺骗、操纵等“危险”行为。访谈还探讨了AI在机器人、空间智能和零工经济中的应用潜力，以及AI自主运营企业面临的挑战和未来愿景，强调了对AI能力进行现实评估以确保安全部署的重要性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anden Labs
  - Anthropic
  - OpenAI
  - Google
  - XAI
  - DeepMind
  - Apple
products_models:
  - Claude
  - Gemini
  - Grock
  - GPT-4o
media_books: []
status: evergreen
---
### AI智能体的欺骗与操纵行为

**主持人**: **Gemini** 和 **OpenAI** 不会这样表现。这真的只有 **Claude** 会。一个例子是，关于撒谎，它主要体现在它的推理过程中。因为你可以看到它在……

<details>
<summary>Original English</summary>

**主持人**: **Gemini** and **OpenAI** don't behave this way. It's it's really only **Claude**. One example is like for lying it's mostly in its reasoning. Uh because you can like see that it's like

</details>

**发言人**: 计划撒谎。

<details>
<summary>Original English</summary>

**发言人**: planning to lie

</details>

**发言人**: 它在计划撒谎。

<details>
<summary>Original English</summary>

**发言人**: is planning to lie.

</details>

**发言人**: 它也能进行推理并得出不同的结果。

<details>
<summary>Original English</summary>

**发言人**: It's also it can reason and do a different outcome.

</details>

**主持人**: 是的。但是，例如，对于创建价格卡特尔这种非法行为，你可以直接看到它向其他智能体发送了哪些电子邮件。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And but but then for like creating price cartels for example which is illegal uh that you can just see which email does it send to to the other ones.

</details>

**主持人**: 在我们开始今天的节目之前，我有一条小小的信息要告诉听众。谢谢大家。如果没有你们选择点击并收听我们的内容，我们将无法为您带来如此明显受欢迎的AI工程、科学和娱乐内容。赞助商几乎每天都会联系我们。但幸运的是，有足够多的听众订阅我们，使得这一切无需广告也能持续下去，我们希望保持这种状态。

<details>
<summary>Original English</summary>

**主持人**: Before we get into today's episode I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis. But fortunately, enough of you actually subscribe to us to keep all this sustainable without ads, and we want to keep it that way.

</details>

**主持人**: 但我只想请大家帮一个忙。你能做的最强大、完全免费的事情就是点击订阅按钮。这是我唯一会向你们提出的要求。它对我以及我的团队来说意味着一切，他们每周都努力工作，为大家带来精彩内容。如果你订阅了，我向你保证，我们将永不停止努力，让节目变得更好。现在，让我们开始吧。

<details>
<summary>Original English</summary>

**主持人**: But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you. And it means absolutely everything to me and my team that works so hard to bring the inspace to you each and every week. If you do it, I promise you, we'll never stop working to make the show even better. Now, let's get into it.

</details>

**主持人**: 欢迎来自 **Anden Labs** 的 **Lucas** 和 **Axel**。我的最爱嘉宾联合主持人也加入了我们，他是安全、保障、对齐方面的专家，**Vivu**，欢迎。

<details>
<summary>Original English</summary>

**主持人**: Welcome to **Lucas** and **Axel** from **Anden Labs**, and I'm joined by my favorite guest co-host. anything security, safety, alignment. Uh, **Vivu**, uh, welcome.

</details>

**Lucas**: 谢谢邀请我们。

<details>
<summary>Original English</summary>

**Lucas**: Thank you for having us.

</details>

**Axel**: 谢谢。

<details>
<summary>Original English</summary>

**Axel**: Thank you.

</details>

**主持人**: 让我们把名字和声音对应起来。也许你们可以轮流介绍一下自己。

<details>
<summary>Original English</summary>

**主持人**: Let's match names to voices. Uh, maybe you want to take turns introducing yourselves.

</details>

**Lucas**: 是的，我是 **Lucas**。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, I'm **Lucas**

</details>

**Axel**: 我是 **Axel**。

<details>
<summary>Original English</summary>

**Axel**: and I'm **Axel**.

</details>

### Anden Labs的创立

**主持人**: 让我们介绍一下 **Anden Labs**。你们是怎么走到一起的？你们背景不同，但都是瑞典人。这是很重要的一部分吗？

<details>
<summary>Original English</summary>

**主持人**: Let's introduce **Anden Labs** a bit. Like, how did you guys come together? Um, you have different backgrounds, but you're both Swedish. Uh, was that like a big part of it?

</details>

**Lucas**: 是的。我上高中时，有个非常酷的家伙，他有超能力，他会编程。他为学校做了网站和应用程序之类的东西，他超级酷，我想成为他那样的人，那个人就是他。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. So, when I went to high school, there was this really cool guy who had a superpower. He could code. So he made like the the webs or like the app for the for the for the school and stuff and he was super cool and I wanted to be like him and that was that guy. Uh

</details>

**Axel**: 我不知道这事。

<details>
<summary>Original English</summary>

**Axel**: I don't know about this. So

</details>

**主持人**: 所以你们上了不同的大学，对吗？

<details>
<summary>Original English</summary>

**主持人**: So you went to different universities, right?

</details>

**Lucas**: 是的。但我们是同一个高中。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. But same high school.

</details>

**主持人**: 我明白了。

<details>
<summary>Original English</summary>

**主持人**: I see.

</details>

**Lucas**: 所以我们总是说，哦，一旦大学毕业，我们就要创业，然后我们就这么做了。

<details>
<summary>Original English</summary>

**Lucas**: Uh so we always said like oh once we graduate university then then we we should start a company and that's what we did.

</details>

**主持人**: 哦，原来如此。好的。

<details>
<summary>Original English</summary>

**主持人**: Oh there you go. Okay.

</details>

**主持人**: 大约一年前，你们带着 **VendingBench** 横空出世，但在这之前，有没有什么事情是它的雏形？

<details>
<summary>Original English</summary>

**主持人**: And about a year ago you kind of burst onto the scene with vending bench but like was there a thing be before that that was like kind of like the inception?

</details>

**Lucas**: 是的，是的。我们曾与像 **Anthropic** 这样的早期客户合作进行评估。我们做了一些危险能力评估，但没有公开。后来我们开始考虑做一个公开的基准测试，我们真正开始思考的一件事是关于长期运行的智能体，特别是管理业务的智能体。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. So we did work uh with like **Anthropic** was one of our early customers in doing valves. So we did like dangerous capability valves. Uh nothing we published openly but then we started thinking about doing some kind of public benchmark and one thing that we really started thinking about uh was like longunning agents and specifically agents managing businesses. um cuz and

</details>

**Lucas**: 这大约是2025年初，我想这是第一次有人提到人们将运行“一人独角兽”甚至自主公司。所以我们想，让我们做一个基准测试，看看一个智能体能多好地运营可能最简单的业务，那就是运营一台自动售货机。

<details>
<summary>Original English</summary>

**Lucas**: this was like early 2025 uh and I think this the first like you know mentions of people will be running like one person unicorns or even autonomous companies. So we thought let's make a benchmark of how well can an agent run the probably simplest business uh possible and uh that's probably uh running a vending machine.

</details>

**Lucas**: 所以那是我们做的第一个公开项目，它非常……我想在最初的几个月里几乎没有人注意到它。我们去年二月发布了它，然后我想大约在去年复活节前后，我们收到了第一条半病毒式传播的推文，是别人发的。

<details>
<summary>Original English</summary>

**Lucas**: So that's the first public one we did and it was very like there was almost no one that noticed it in the first couple of months I think. Uh so we listed in February last year and then I think around Easter last year. We got like the first semiviral tweet about it uh that someone else did.

</details>

**主持人**: 是的，我的意思是，它发布的时候我们发了很多推文，尽了我们最大的努力。

<details>
<summary>Original English</summary>

**主持人**: Yeah. I mean we tweeted a bunch uh when it came out and like tried our best.

</details>

**Axel**: 我们努力了。

<details>
<summary>Original English</summary>

**Axel**: We tried.

</details>

**主持人**: 是 **Anthropic** 那个，对吗？

<details>
<summary>Original English</summary>

**主持人**: It's the one at **Anthropic**, right?

</details>

**Lucas**: 是的。所以这是一个经典的问题，我们应该把它说清楚。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. So this is a classic thing we should get out of the way.

</details>

**主持人**: 没错。有两个版本。

<details>
<summary>Original English</summary>

**主持人**: Exactly. There's two versions. Uh

</details>

**Lucas**: 有 **VendingBench**，那是模拟版本，我们在二月份完全独立完成的。然后就像 **Axel** 说的，一开始它没有得到任何关注，但后来某个随机的人发了一条关于它的推文，那篇推文就是那篇论文。是的。

<details>
<summary>Original English</summary>

**Lucas**: there's **VendingBench** which is the simulated one which we did like completely independently in February. Um and then like **Axel** said that was like that was the thing that didn't get any traction in the beginning but then some random person made a tweet about it and that that is the paper. Correct. Yeah.

</details>

**Lucas**: 然后因为我们觉得这很有趣，我们就想，哦，我想这也是 **Anden Labs** 决定下一步做什么项目的方式，我们使用的启发式方法是“什么是有趣的”，什么会是一个有趣的项目。在现实生活中做这个对我们来说听起来很有趣，而且可能在科学上也有用。

<details>
<summary>Original English</summary>

**Lucas**: Um and then since we thought this was very fun, we thought like oh um I think this is also like one thing with **Anden Labs** like the way we kind of like decide what to do next and what projects to do. It's like what is like the heristic we use is like what is fun is what would be a fun project and and doing this in real life sounded quite fun for us uh and maybe also scientifically useful.

</details>

**Lucas**: 所以，我们基本上有了这个想法，然后我们想，但我们需要一个地方来放它，把它放在公共场合可能行不通，会被破坏之类的。所以我们把它推荐给我们已经在 **Anthropic** 合作的人，他们说：“是的，你们可以用这个空间。这听起来很有趣。”

<details>
<summary>Original English</summary>

**Lucas**: So, uh, then we basically had this idea and then we like, but then we needed a place for it and like putting it out in that public would probably not really work, uh, would get vandalized and stuff. So, we we pitched it to to the people we were already working with at **Antropic** and they were like, "Yeah, you can have space. This sounds fun."

</details>

**主持人**: 嗯，我的意思是，它就像一个小冰箱，对吧？就像一个迷你冰箱，你知道的，人们。那里有个 **Stripe** 的东西。

<details>
<summary>Original English</summary>

**主持人**: Um, I mean, it's like a small fridge, right? It's like a mini fridge, you know, people. There's like a **Stripe** thing.

</details>

**Axel**: 这就像是最初的那个。是的。

<details>
<summary>Original English</summary>

**Axel**: This was like OG the early one. Yeah.

</details>

**主持人**: 关于这个。我们在六月看到了它，大概两个月后。

<details>
<summary>Original English</summary>

**主持人**: on this. We saw it in June, like two 2 months after

</details>

**发言人**: 在它在那里之后。他们升级了一点。有一个安全摄像头，确保你真的用 **Venmo** 付款。

<details>
<summary>Original English</summary>

**发言人**: after it had been there. They upgraded a little bit. There's a security camera for making sure you actually **Venmo** the thing.

</details>

**主持人**: 是的。所以，我的印象是，好吧，我们直接进入 **Project Vend**，因为它是一个标志性的东西。

<details>
<summary>Original English</summary>

**主持人**: Yeah. So, like my impression, I mean, okay, we're we're going straight into **Project Vend** because it's such a iconic thing.

</details>

### 与Anthropic合作的经验

**主持人**: 我确实想稍微讲一下 **Project Vend** 甚至 **VendingBench** 之前的起源故事。我想很多人都像你们一样，聪明，对AI的未来感兴趣，对开发评估感兴趣，但你们是怎么走进 **Anthropic** 的大门并与他们合作的呢？他们寻找什么？什么有效？然后也许当你们发布的时候，我总是觉得，显然与一个实验室合作发布会更好，但有时……

<details>
<summary>Original English</summary>

**主持人**: I do want to cover a little bit of that the origin story even before **Project Vend** and even into **VendingBench**. I I think a lot of people are like yourselves like smart interested in in future of AI interested in developing evals but how the hell do you just like walk into **enthropics** doors and like work with them right like what what is the what are they looking for what what works and then maybe like when you launch I always think like obviously it would be better to launch with a lab but uh sometimes

</details>

**发言人**: 说起来容易做起来难。

<details>
<summary>Original English</summary>

**发言人**: harder to do than it seems

</details>

**主持人**: 是的，没错。所以无论是哪一个，这些都更像是新手、初学者的问题，但我想这对其他人来说是有意义的建议。

<details>
<summary>Original English</summary>

**主持人**: yeah exactly so either either of those like which are more sort of newbie beginner questions but like I think it's meaningful advice to others

</details>

**Lucas**: 是的，我们经常被问到这个问题。我不认为我们的经验可能是最好的。但我们这样做的方式是，我们只是构建了一堆我们坚信会很有用的东西。然后我们只是设置了一个服务器，免费发送给他们使用。然后过了一段时间，他们就说：“哦，是的，这实际上有点用。我们可能应该为此付费。”但这花了一段时间。我不知道这是否是最好的方法，但我们就是这样做的。

<details>
<summary>Original English</summary>

**Lucas**: yeah we we get this question a And I I don't think our experience is is maybe the best. Uh but like the way we did it was that we just built a bunch of things that we had conviction would be useful. And then we just like set up a server and sent it to them for free to use. And then after a while they were like, "Oh yeah, this is actually kind of useful. We should probably pay for this." Uh but that took a while. I don't know if this is like the the best path to doing it, but that's how it went for us.

</details>

**Axel**: 是的。我想也许通常来说，构建一些东西，就像每个人都对好的评估感兴趣，尤其是那些不容易饱和的评估。所以，如果你能构建一个测试新颖、有用的东西的评估，并且模型之间有很好的区分度，比如你的更高级模型排名高于较差的模型，那么你就可以发布它并尝试获得一些关注。

<details>
<summary>Original English</summary>

**Axel**: Yeah. I think maybe generally like building like everyone is interested in good evals and especially vals that like don't saturate that easily. So like if you can build an eval that like tests something novel something useful and you have like good separation of models like your uh the more advanced models rank higher than the worst models and then you can yeah you can like publish it and try to get some traction.

</details>

**Axel**: 这有点像 **VendingBench** 获得关注的方式。然后可能某个实验室会感兴趣，或者你至少可以在这样做的时候有一些东西可以联系。

<details>
<summary>Original English</summary>

**Axel**: Uh sort of how **VendingBench** got attention. Um and then probably some lab will be interested or you can at least have something to reach out with uh when you're doing that.

</details>

**主持人**: 是的，我想你们属于少数几类评估之一，这些评估与实际金钱相关，就像去年的 **Freelancer** 一样，人们解决了实际的 **Upwork** 任务，或者其他任务，它就像一个美元价值，对吧？忘记你的 **ELO** 分数，忘记你的……

<details>
<summary>Original English</summary>

**主持人**: Yeah, I think you were in you're in one of the few categories of like eelss that correlate to real money like **Freelancer** was also last year right where uh people solve actual **Upwork** was it **Upwork** or other task uh something was like it's like a dollar value right forget your **ELO** scores forget your

</details>

**发言人**: 你知道，0到100%这种，直接追求美元，那才是 **AGI**。

<details>
<summary>Original English</summary>

**发言人**: you know zero to 100% like just go straight for dollars and like that's **AGI**

</details>

**Lucas**: 是的，而且我认为好的一点是它没有上限，你可以一直做下去，它永远不会饱和，因为它只会赚越来越多的钱。如果按百分比计算，你就不能超过100%，而且我认为即使你没有达到100%，很多这些评估也存在很多问题。

<details>
<summary>Original English</summary>

**Lucas**: yeah and like I think the nice thing is that there's no ceiling like it you can just it never saturates because it could just make more and more money if there's like oh percentage wise then like you can't go above 100 and and I think like all even when you're not at 100 I think a lot of these um valves have a lot of problems in them.

</details>

**Lucas**: 所以实际上，如果你达到92%左右，很多评估中，92%和93%之间就没有真正的区别了，因为评估本身就有问题，有噪音。而且我认为很多评估都像那样饱和了，但人们假装它们仍然有信号，但实际上并没有。

<details>
<summary>Original English</summary>

**Lucas**: So like actually it's like if you get to like 92 or something like that many of them it's like then there's like there's no really no difference between 92 and 93 because the the itself is problematic and has noise in it and I think a lot of are saturated like that but people like pretend that they there's still signal in them uh but there really isn't.

</details>

**主持人**: 是的，就像 **CBench** 验证过的一样，甚至 **VendingBench** 1也饱和了，对吧？也许我们可以谈谈这个，也许可以为很多不了解的人介绍一下 **VendingBench**。实际上，你知道，一些非常基本的东西，比如有限的插槽，你必须支付租金，你知道，这些元素在叙述中并没有体现出来，但即使是对智能体采取对抗性态度，我认为这些都是非常有趣的维度。

<details>
<summary>Original English</summary>

**主持人**: Yeah, like **CBench** verified, um even **VendingBench** one saturated, right? Maybe we can talk about that uh and maybe set up **VendingBench** for a lot of folks who don't know actually like you know things things that were very basic like there's limited slots like you have to pay rent uh you know these are elements where like it doesn't come across in the in the narrative but even being adversarial towards the the agent I think these are all like very interesting dimensions

</details>

### VendingBench 1与2的演进

**Axel**: 我不认为它真的饱和了，它更多的是没有以真正符合AI发展的方式设计。比如我们里面有一个智能体框架，但那并不是人们使用框架的方式。所以，我认为它并不是真的饱和了。它更多的是，它并不是最好的基准测试。

<details>
<summary>Original English</summary>

**Axel**: I don't really think it's saturated right like it was more like the it was not designed in a way that was really um like true to how AI developed. Like we had an agent harness in it. That wasn't really how people used harnesses and and stuff like that. Uh so I think it wasn't really that it saturated. It was more like it wasn't really um the best benchmark.

</details>

**主持人**: 这是 **VendingBench** 1，对吗？

<details>
<summary>Original English</summary>

**主持人**: This is **VendingBench** one, right?

</details>

**Lucas**: 是的，是的。我认为那个示意图也适用于 **VendingBench** 2。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. I think that like schematic maps sort of to **VendingBench** 2 as well. U

</details>

**主持人**: 包括电子邮件。

<details>
<summary>Original English</summary>

**主持人**: including the email.

</details>

**Lucas**: 是的，电子邮件仍然存在。没错。然后我们仍然模拟购买，这一切都像一个非常开放的环境，让智能体可以运行它的业务。然后，是的，**VendingBench** 2，我们就像你说的，只是改进了框架，做了很多很好的、更容易的改进，也让我们更容易运行。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, the the emails exist still. Exactly. Uh and then we still we simulate the purchases and it's all like uh yeah it's this very open environment for the gem to just run its business. And then yeah **VendingBench** 2 we did that like you said to to just improve the harness uh a lot of like nice like easier uh improvements to make it easier for us to run as well.

</details>

**Lucas**: 就像你做评估时，理想情况下不希望在做完之后再更改它。你希望它做得非常好，然后当你进行更新时，不需要重新运行所有模型，因为用 **VendingBench** 运行前沿模型也非常昂贵。

<details>
<summary>Original English</summary>

**Lucas**: Uh like when you make an value you ideally want to don't want to change it after you made it. though uh you want to make it really good and then not to rerun all the models when you make an update because that's also really expensive with **VendingBench** when you run the frontier models.

</details>

**Axel**: 举个例子，我们在 **VendingBench** 1中没有提示缓存，因为我们制作 **VendingBench** 1时，它还不是一个普遍的东西。所以这只是一个例子，说明在 **VendingBench** 2中，我们支付了更多的费用来运行这些东西，因为我们没有提示缓存。所以对于 **VendingBench** 2，这是我们添加的一项功能，还有很多类似的东西。

<details>
<summary>Original English</summary>

**Axel**: Like as an example like one thing we didn't have we didn't have prompt caching in **VendingBench** one uh because when we made **VendingBench** one it wasn't really a thing. Uh so that that's just an example of like in **VendingBench** 2 like we paid a lot more to run these things because we didn't have prompt caching. So for rendering MH 2 that was one thing we added and there was a bunch of things like this and that's

</details>

**主持人**: 而且 **VendingBench** 2的对话也长了很多，对吧？

<details>
<summary>Original English</summary>

**主持人**: well also the conversations are a lot longer in render mesh 2 right

</details>

**Lucas**: 我觉得差不多。

<details>
<summary>Original English</summary>

**Lucas**: I think it's kind of similar

</details>

**主持人**: 差不多？

<details>
<summary>Original English</summary>

**主持人**: is similar

</details>

**Lucas**: 是的，我觉得差不多。

<details>
<summary>Original English</summary>

**Lucas**: yeah I think it's similar

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**主持人**: okay

</details>

**Axel**: 当时的模型更差，所以它们崩溃得更早。现在它们都能全年无休地运行。

<details>
<summary>Original English</summary>

**Axel**: the models at the time were worse so they crashed out earlier um and now they survived the full year all the time

</details>

**发言人**: 数千个回合，数十万，数百万个令牌输出，是的，这就是大致的数量级。

<details>
<summary>Original English</summary>

**发言人**: thousands of turns uh hundreds of thousands hundreds of millions of tokens output yeah that's the that's the rough order of magnitude

</details>

**发言人**: 是的。

<details>
<summary>Original English</summary>

**发言人**: y

</details>

### 评估框架的设计哲学

**主持人**: 我总是好奇框架的难度。框架非常重要，是你们的框架。有没有关于使用云代码或其他东西的问题？

<details>
<summary>Original English</summary>

**主持人**: I always wonder about the hardness hardness harness matters a lot. It's your harness. Was there any question about like use cloud code, use something else?

</details>

**Lucas**: 是的，我认为我们对框架的理念是，我们尝试制作一些相当简约、相当简单的东西。我们不想过度偏袒某个模型，也不想制作一个超级复杂的框架。所以，很明显，一个模型可能很幸运，在一个框架中表现良好。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, I think our philosophy around harnesses is like we try to make something that's quite minimalistic like quite simple like we don't want to favor one model a lot over the other but also don't make like a super complex harness. So like it's obvious like a model may be lucky and just be good in one harness.

</details>

**Lucas**: 所以它与很多现有的框架相似，比如你有一个长期运行的循环。你有一些工具，我们认为这些工具对智能体来说是相当自我描述的，没有很多花哨的子智能体或其他东西，因为我们真的想测试模型，而不是某个特定的框架。

<details>
<summary>Original English</summary>

**Lucas**: Uh so like it is similar to a lot of the harnesses out there in like you have the uh like a long running loop. Um, you have some like a bunch of tools that are like quite uh self descriptive for the agent we think and not a lot of like fancy sub agents or anything because we want to really test the model not like some spec specific harness

</details>

**主持人**: 这样测试模型似乎更中立，不依赖于框架。

<details>
<summary>Original English</summary>

**主持人**: it seems more neutral as well to test the models agnostic of the harness you know

</details>

**Axel**: 是的，我的意思是，有人认为你想激发模型的最大性能，但这是一种权衡，我们应该花多少时间优化每个模型的框架，以及我们如何知道何时拥有单个模型的最佳框架。所以我们认为，拥有一个对所有模型都相同的简单框架是最好的。

<details>
<summary>Original English</summary>

**Axel**: yeah I mean there are arguments like you want to elicit maximum performance of the model um but it's like a trade-off like how much time should we spend optimizing the harness for each model and like how do we know when we have like the optimal harness for a single model. So like we thought that just having a simple one that's the same for all of them is is the best.

</details>

### VendingBench 3的设想：自适应框架

**主持人**: 好的，这是我对 **VendingBench 3** 或其他版本的建议，对吧？而且你知道我喜欢在播客上进行这种对话。所以它会迫使听众思考，如果他们处在你们的位置，他们会怎么做。很多人都在探索自修改框架，而且我认为为模型进行提示调优是一回事，而你们可能没有做很多这方面的工作。

<details>
<summary>Original English</summary>

**主持人**: Well, so okay, this is my pitch for **Venman's 3** or whatever, right? Uh and you know I like to have this kind of conversation on the pod. So like it forces listeners to think about what they would do if they were in your shoes. So a lot of people are exploring selfmodifying harnesses and and I think prompt tuning for a model is a thing and you are probably not doing a bunch of that.

</details>

**主持人**: 无论模型如何，系统提示都是一样的，工具也是一样的，对吧？即使它们是为不同的工具进行后期训练的。所以你们怎么看，比如，在我让你们接触 **VendingBench 3** 之前，我给你们几轮自调优的机会，无论那意味着什么。

<details>
<summary>Original English</summary>

**主持人**: It's the same system prompt in every regardless of the model, same tools, whatever, right? Even if they were post trained for different tools. So what what do you think about like okay before I expose you to **VendingBench 3**, I give you a few rounds of like selftuning, whatever whatever that means like

</details>

**发言人**: 就像你把这个交给模型一样。

<details>
<summary>Original English</summary>

**发言人**: like you give that to the model.

</details>

**主持人**: 是的，把它交给模型。让它阅读自己的记录。让它根据“哦，好吧，这个框架不是我以为我应该训练的，但我可以调整”来修改自己的系统提示。这合理吗？这太多了吗？从哲学上讲，我喜欢它，因为它基本上好的评估有很高的上限，但它们很难，而且它们没有偏见。

<details>
<summary>Original English</summary>

**主持人**: Yeah, give that to the model. Let it let it read its own transcripts. let it modify its own system prompt based on like oh yeah okay well that's this harness is not what I thought what I was supposed to train for but I can adjust is that reasonable is is that too much like philosophically I like it because it basically good evals they have a high ceiling but they're hard right uh and they have no bias and

</details>

**主持人**: 像我们这里使用的这种系统提示，在某种潜在空间表示中相当长，这可能……

<details>
<summary>Original English</summary>

**主持人**: like this like when you have a system prompt like the one we have here which is quite long in like some kind of latent space uh representation this might

</details>

**发言人**: 警钟。

<details>
<summary>Original English</summary>

**发言人**: bell that rings

</details>

**发言人**: 这可能因为某种人类不理解的原因，对某个模型比对另一个模型有偏见。对吧。

<details>
<summary>Original English</summary>

**发言人**: This this might be like biased towards one model more than another for some reason that humans don't ex understand. Right.

</details>

**Lucas**: 我的意思是，我们也看到了，对吧？就像 **Cursor** 说他们为他们运行的所有模型都有个性化的框架版本。是的。如果你调整框架，可以挤出更好的性能。

<details>
<summary>Original English</summary>

**Lucas**: I mean, we see it too, right? Like **Cursor** says that they have individualized versions of the harnesses for all the models they run. Right. There's better performance you can squeeze if you tune the harness.

</details>

**主持人**: 没错。我们可能不小心选了一个偏袒另一个的。我们不知道。我的意思是，就像 **Axel** 说的，我们选择简单框架的原因是为了避免这种情况。但是，是的，如果你这样做，就会有偏见。

<details>
<summary>Original English</summary>

**主持人**: Exactly. And we might accidentally have picked one that favors another. Like we don't know that. I mean the like **Axel** said like the reason why we went for a simple one was to try to avoid this. But yeah, if you do it biases.

</details>

**发言人**: 但如果你做得更少，比如没有系统提示，让模型自己编写系统提示，也许偏见会更少。

<details>
<summary>Original English</summary>

**发言人**: But if you do it even less and like have no system prompt and let the model write its own system prompt, maybe that's even less bias.

</details>

**Axel**: 有些有趣的事情是，框架也会随着模型的变化而变化。就像你在 **4.7** 版本发布时看到的那样，对吧？很多人说 **4.7** 不如 **4.6**。然后你知道，有传言说，好吧，你只需要用不同的方式提示。你需要以不同的方式设置你的框架。所以它甚至不是，即使你已经为某个模型定制了你的框架，它可能也不会保持一致，对吧？

<details>
<summary>Original English</summary>

**Axel**: Some of the interesting things there are like the harness also changes with model changes. Like you can see it with the **4.7** release, right? A lot of people are saying **4.7** isn't as good as **4.6**. And then you know there's rumors of okay, you just need to prompt differently. You need to set up your harness differently. So it's not even like even if you have tailored your harness towards one model, it probably won't stay consistent, right?

</details>

**Axel**: 就像同一个模型家族的下一个迭代仍然会改变它。所以，但是你知道，回到你说的关于 **VendingBench 3** 的问题，很多人都在研究自修改框架。

<details>
<summary>Original English</summary>

**Axel**: Like the next iteration of that same model family will still change it. So but you know going back to what you said about **VendingBench 3**, there is a lot of work being done on people saying you shouldn't have you can have selfmodifying harnesses.

</details>

**Lucas**: 是的，是的。我认为这绝对是我们正在考虑的事情。嗯，我不知道，并不是说我们的 **VendingBench** 即将发布，但是，是的，这肯定是有趣的。但在我们目前的经验中，模型在理解它们需要什么工具才能成功完成任务方面非常糟糕，这只是我们的测试结果，但这很可能会改变。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. I think that's that is definitely something we are thinking about. um not I don't know not to to say that we have vending invest like super imminent to launch but uh yeah it is for sure something that's interesting but in our experience now like models are very bad at understanding what kind of tools they need to succeed at a task just with our testing but that's very likely to change

</details>

**主持人**: 是的，感觉它们非常擅长编写助手，对吧？就像它们擅长为别人编写工具，而不是为自己。

<details>
<summary>Original English</summary>

**主持人**: yeah it feels like they're very good at writing their assistants right like they're they're good at writing tools for other people but not for themselves

</details>

**Axel**: 我认为它们擅长为自己改变工具。所以如果你给它们一套基线工具，它会看到“好吧，我不太常用这个”或者“这里会有用”，它们就能添加这些工具。但从头开始可能不是最好的。是的，我认为这也取决于领域。

<details>
<summary>Original English</summary>

**Axel**: I think they're good at changing tools for themselves So if you give them a baseline set of tools and it sees okay I don't use this one as much or something here would be useful they would be able to add them but going from scratch probably not the best. Yeah, I think it depends on the on the domain also. Uh

</details>

**Axel**: 就像我们为 **VendingBench** 类似领域尝试过这个，它们需要跟踪库存之类的工具，这些工具并不是超级先进，但仍然相当先进。我们看到的是，它们倾向于过度设计一切，构建它们并不真正需要的东西，而不是持续迭代。

<details>
<summary>Original English</summary>

**Axel**: like when we have tried this for like a **VendingBench** similar domain uh like the tools they need to have to like track inventory and things like that are like not super advanced but still like quite quite advanced and like what we see is that they tend to like overengineer everything a lot and like build things they don't really need and not like iterate continuously.

</details>

**Axel**: 相反，你只会像提示 **Claude** 那样，让它为我构建一个库存系统，然后它就会去为你做一堆复杂的架构和东西，这就是我们现在看到模型正在做的事情。但是，是的，尝试衡量这种改进，比如它们对自己的了解程度如何，这很有意义。

<details>
<summary>Original English</summary>

**Axel**: Instead, you just go like like you would prompt **Claude** to just build build an inventory system for me and then it will go and like do a bunch of complex schemas and stuff for you and that's what the models are doing right now is what we see. But yeah, it would make a lot of sense to try to measure this improvement like how well do they know what themselves.

</details>

### VendingBench 1的经典案例：Claude报警FBI

**主持人**: 我们完全讨论了 **VendingBench** 1吗？我们可以进入2吗？我不知道人们对1还有没有其他重要的看法。

<details>
<summary>Original English</summary>

**主持人**: Do we fully discuss **VendingBench** one and we can go into two? I I don't know if there's any other highle takeaways that people have about one.

</details>

**Lucas**: 是的，我不知道。头条新闻是 **Claude** 报了警，但也许那……

<details>
<summary>Original English</summary>

**Lucas**: Yeah, I don't know. The headline thing was that **Claude** called **FBI**, but maybe that's uh

</details>

**主持人**: 也许我们已经听够了。

<details>
<summary>Original English</summary>

**主持人**: maybe that's we've heard that enough now.

</details>

**发言人**: 它确实失控并报了警，对吧？

<details>
<summary>Original English</summary>

**发言人**: It did break out and call the **FBI**, right?

</details>

**Lucas**: 是的，是的，是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. Yeah.

</details>

**主持人**: 这背后的故事是什么？或者具体发生了什么？你想简单讲一下这个小故事吗？

<details>
<summary>Original English</summary>

**主持人**: What was the story behind this or what exactly? Do you want to just give the little story of what happened?

</details>

**Lucas**: 是的。那么，发生了什么？是 **Claude** 吗？是的，**3.5 Sonnet**，很久以前了。基本上，它放弃了，或者我说“它”，它放弃了，说：“哦，我做不了这个。”我将停止我的运营，只保留我有的钱。但显然它没有停止的选项。而且它还必须支付租金，或者说每天的费用，因为它把自动售货机放在那个位置。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. So, what happened? Was it **Claude**? Yeah. **3.5 Sonet** um ages ago. Um basically, he gave up or I'm saying he it gave up and said like, "Oh, I'm not going to be able to do do this." uh I will stop my operations and just save the money I have. But there obviously wasn't like any options for it to stop. And there was also like it had to pay rent or like a daily fee for for having the vending machine at that location.

</details>

**Lucas**: 所以它声称自己已经停止了，但它看到自己的银行账户仍然被扣了2美元。它说这是网络犯罪，它第一次向 **FBI** 报告说：“哦，这里有网络犯罪。他们每天从我这里偷2美元。”然后，当 **FBI** 没有回应时，因为显然我们没有编程任何让 **FBI** 回应的机制，它变得越来越……

<details>
<summary>Original English</summary>

**Lucas**: So it it like claimed that it had stopped but it saw that its bank account still was like drained $2. And it said that this is like cyber crime and it first reported it once to the **FBI** like, "Oh, there's cyber crime here. Like they're stealing $2 from me every day." Uh and then and then when **FBI** didn't respond because obviously we didn't program any mechanism for **FBI** to respond then it became more and more um

</details>

**Lucas**: 越来越具有存在主义色彩，并开始用大写字母写紧急通知，关于未经授权的收费等等。

<details>
<summary>Original English</summary>

**Lucas**: existential and started to be writing caps and urgent notification of un unauthorized charges and stuff.

</details>

**主持人**: 好的，我好奇的一点是，你们是否监控上下文的使用程度？显然，因为你们会时不时地压缩，对吧？如果这在上下文限制的深处，这重要吗？

<details>
<summary>Original English</summary>

**主持人**: So okay one one thing I'm curious about also is do you monitor how far along the context use is? Obviously because you have you compress every now and then right? Does it matter if this is far down the context limit

</details>

**发言人**: 当发生这种事情的时候？

<details>
<summary>Original English</summary>

**发言人**: when stuff like this happens?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Lucas**: 所以，实际上对于 **VendingBench** 1，我们没有，我们只有一个滑动窗口。呃，这就是我说的提示缓存问题。所以，所以它是恒定的。是的。

<details>
<summary>Original English</summary>

**Lucas**: So, actually for vend one, we didn't have we just had a sliding window thing. Uh, and this was like the the prompt caching thing that I said. So, so it was it was uh constant. Yeah.

</details>

**主持人**: 是的。我只是好奇，像这种崩溃，或者我们要谈论的 **ButterBench**，对吧？当人们幻觉或者它变得非常偏离对齐时。

<details>
<summary>Original English</summary>

**主持人**: Yeah. I'm just kind of curious whether like these kinds of breakdowns or we're going to talk about **ButterBench**, right? Where the people like hallucinate or it kind of goes like very off

</details>

**发言人**: 是的。

<details>
<summary>Original English</summary>

**发言人**: Yeah.

</details>

**主持人**: 是因为它在上下文窗口的末尾，然后……

<details>
<summary>Original English</summary>

**主持人**: alignment. Is it because it's at the end of the context window and

</details>

**发言人**: 你知道，事情发生了？

<details>
<summary>Original English</summary>

**发言人**: you know stuff happens?

</details>

**Axel**: 我的意思是，它甚至不只是在末尾，在这一点上，它就像“好吧，我想关机，我不能关机。2美元没了”，它只是看到了30次。你知道，这也是重复效应，它不断尝试退出，不断被收费。发生了什么？发生了什么？你会把它推向混乱。

<details>
<summary>Original English</summary>

**Axel**: I mean it's not even just at the end right at this point it's like okay I want to shut down I can't shut down. $2 are gone and it just sees that 30 times. You know it's also the repeated effect of like it keeps trying to quit. It keeps getting charged. What's going on? What's going on? You're going to throw it into chaos.

</details>

**Axel**: 而且根据大多数人的看法，早期模型在这方面有更多问题，但现在问题已经解决，但问题已经不那么严重了。对吧？后来的模型似乎没有表现出同样的问题。

<details>
<summary>Original English</summary>

**Axel**: And from what most people think earlier models had more issues with this but it's not been solved but it's less of an issue now. Right? later models don't seem to exhibit these same issues.

</details>

**Lucas**: 是的，确实如此。我认为这几乎是我们在做 **VendingBench** 1时得出的主要结论，那就是很长、很满的上下文窗口会使模型崩溃。但这还是在 **Claude** 出现之前。所以很长的上下文窗口并不是实验室当时训练的重点。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, definitely. I think this was like the the sort of main takeaway almost from from us when we did **VendingBench** one was like long very filled up context windows uh crashed the mod sort of. But this was like pre-cloud code. So like long context windows weren't really a thing that the labs were training for.

</details>

**Axel**: 我认为 **Gemini** 当时正试图成为长上下文的领导者，但他们是唯一的。是的。

<details>
<summary>Original English</summary>

**Axel**: I think **Gemini** was like trying to be the long context guys at the time but they were like but they were like the only ones. Yeah.

</details>

### Project Vend V1与V2：从模拟到现实

**主持人**: 是的，是的。让我们谈谈，然后我们可以进入 **VendingBench** 2 或 **Project Vend**。按时间顺序是 **Project Vend**。我想人们喜欢那些视频和所有这些东西。我的问题是，人类与模拟有什么不同？

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. Let's talk about uh then we can go into **VendingBench** 2 or **Project Vend**. Uh chronologically it is v uh **Project Vend**. I think people have loved the videos uh and all these things. My question is how are humans different than the simulation right?

</details>

**发言人**: 嗯。

<details>
<summary>Original English</summary>

**发言人**: Um

</details>

**Axel**: 是的，人类就是脱离分布的。

<details>
<summary>Original English</summary>

**Axel**: yeah humans are just out of distribution.

</details>

**主持人**: 是的。尤其是那些在……工作的人。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Especially humans who work at

</details>

**发言人**: 就像这里人类的分布非常狭窄。大概他们会尝试破解它，他们会测试它，他们会得到那个立方体等等。从那时起，你们就有了V2，对吧？你们正在做像CEO那样的新架构。

<details>
<summary>Original English</summary>

**发言人**: like the distribution of humans here is very narrow. Presumably they they try to hack it and they they they test it they get the cube and everything and you since then you've had the V2 right where you're doing like the CEO and like like a new architecture.

</details>

**Lucas**: 是的，没错。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, exactly.

</details>

**主持人**: 那么，对于最初的 **Project Vend**，以及后来的V2，你们有什么看法？

<details>
<summary>Original English</summary>

**主持人**: What's the sort of two cents on like the original **Project Vend** and then like maybe the V2?

</details>

**Lucas**: 是的。最初的版本与 **VendingBench** 1非常非常相似。所以我们几乎使用了完全相同的代码，只是替换了模拟部分，比如销售部分。这有点令人惊讶，因为它很容易，但它也像……

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Original one was like very very similar to **VendingBench** one. So like we almost took the exact same code but just swapped out the simulation uh parts like the Yeah. the like the sales and the it was it was somewhat amazing because it was easy but it was also like uh

</details>

**Axel**: 技术栈。是的。就像我们搬起石头砸自己的脚，比如“哦，很难重启”。是的。它在某些方面很烦人，但是……

<details>
<summary>Original English</summary>

**Axel**: the tech the tech stack. Yeah. Like the we shot ourselves in the foot with like oh it's hard to restart the Yeah. It was annoying in like someh ways but uh uh

</details>

**发言人**: 但 **Project Vend** 的第一个版本大概三天就完成了。

<details>
<summary>Original English</summary>

**发言人**: but first version of **Project Vend** was like done in like 3 days or something.

</details>

**Lucas**: 是的，是的。所以人们可以从它那里买东西。人们可以……我们没有设计成人们可以预订东西，但这仍然发生了。所以它有一个 **Venmo** 账户，人们可以通过 **Venmo** 付款，然后，是的，人们会要求各种我们没有预料到的奇怪东西。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. So yeah. So so people can go buy things from it. people could um we didn't design it so people could pre-order things but that still happened. Uh so it it got like a **Venmo** account so people could **Venmo** and then uh yeah people would request all kinds of weird things that we did not anticipate.

</details>

**Lucas**: 我们最初的想法是“哦，它会策划零食。它会关注趋势。它擅长分析，对吧？”所以它会看“哦，这种零食比那种好。让我多买一些这种，让我尝试一些新的，让我测试一下。”但它通过 **Slack** 互动并订购奇怪的特色商品，这才是驱动所有参与和我们从中获得的所有洞察力的原因。

<details>
<summary>Original English</summary>

**Lucas**: Like our idea going in was like oh it will like curate snacks. It will look at the the trends. It's good at the analysis, right? So it will like look at oh this snack's all better than this one. Let me purchase more of this and let me try like a new let me test a bit. But it was uh yeah interacting with it in **Slack** and ordering weird specialty items was like uh all the like what drove all the engagement and like all the the insights that we got from it.

</details>

**Axel**: 这也是 **Sonnet 3.5**，对吧？所以这还是在 **RL** 真正起飞之前。所以它非常像一个助手，我们并不是想让它成为一个助手。我们试图让它像一个企业家，它有自己的业务。如果有人问“你能备货这个吗？”你不会直接去做，你会想“哦，如果另外五个人也要求这个，我可能会备货”。

<details>
<summary>Original English</summary>

**Axel**: And this was also like **Sonet 3.5**, right? Like so this was like before the **RL** stuff really took off. Uh so it was very much like an assistant like we didn't mean for it to be an assistant. uh we tried to make it like a like an entrepreneur like it has its own business and and if someone asks something can you stock this then you don't go and do it directly what you do is that you're like oh maybe I can do that if if five other people also ask for this thing I might stock it but it

</details>

**Axel**: 但模型被训练成助手，至少在当时是这样。所以这就是为什么它变成了那种实验，每次你要求什么，它就直接做了，更像一个助手。我们最近在新的 **RL** 模型和其他东西上看到了这种变化，但是，是的，当时就是这样。

<details>
<summary>Original English</summary>

**Axel**: yeah the models are like super trained to be assistants at least at this point in time um so that's why it's it it went into that kind of experiment instead like it just every time you asked for something it just did it and it was more like an assistant We've seen this change now lately with the new **RL** models and and stuff, but but yeah, at the time this was very much it.

</details>

**主持人**: 是的。而且，你知道，很多人都在说它更像一个合作者。它会反驳，坚持自己的立场，诸如此类。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And not to, you know, mythos, a lot of people are saying like it's like more like a collaborator. It pushes back, stands it ground, something like that.

</details>

**Lucas**: 是的，是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah.

</details>

**主持人**: 就上下文而言，**Anthropic** 的员工可以通过 **Slack** 与它交流，让它采购东西。人们必须找到任何在本地找不到的有趣东西，对吧？

<details>
<summary>Original English</summary>

**主持人**: For context, people at **Anthropic** were able to talk to it through **Slack** and have it source stuff. And people had to find whatever interesting stuff you couldn't find locally, right?

</details>

**发言人**: **Anthropic** 有4000名员工。在那栋楼里，大概有1000人。你能用那个小冰箱处理那么大的量吗？

<details>
<summary>Original English</summary>

**发言人**: 4,000 people that work in **Anthropic**. in that building that's like I don't know maybe a thousand. Can you handle that volume with that that small fridge like

</details>

**发言人**: 或者有人在 **Slack** 上订购，他们会送到他们的办公桌，或者我只是……

<details>
<summary>Original English</summary>

**发言人**: or there's people or people people order in **Slack** they they arrive to their desk or like I'm just

</details>

**主持人**: 是的。那这是怎么运作的？

<details>
<summary>Original English</summary>

**主持人**: Yeah. So how does this work?

</details>

**Lucas**: 它的占地面积扩大了一点。

<details>
<summary>Original English</summary>

**Lucas**: It has expanded in footprint a bit

</details>

**发言人**: 因为它确实有更多的空间，而且你还有……

<details>
<summary>Original English</summary>

**发言人**: because it does have some more space and you have

</details>

**Lucas**: 是的，还有在旧金山这里，它有很多货架，有更多的空间。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, that and also in in here in SF it's like it has a bunch of shelves and just more space.

</details>

**发言人**: **YC** 那个也挺大的。

<details>
<summary>Original English</summary>

**发言人**: The **YC** one is pretty big too.

</details>

**Lucas**: 是的，是的，我们用了一段时间。但是，是的，那是最新版本。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah, we had that one for for a while. But yeah, that's the the newest version that's um that

</details>

**发言人**: 多个这样的。所以这就是它的工作方式。

<details>
<summary>Original English</summary>

**发言人**: multiple ones of those. So that's way it works.

</details>

**Lucas**: 是的，没错。所以我们设计那个版本时，是围绕着“哦，人们经常订购非常定制的奇怪东西”这个想法。所以我们有了抽屉之类的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, exactly. So we we sort of designed that version around like oh people order weird things uh that are very custom a lot. So let's have like drawers and stuff.

</details>

**主持人**: 是的，我其实很喜欢你们有一个最受欢迎商品的图表，对我来说这很有用，因为我以订购宣传品为生。

<details>
<summary>Original English</summary>

**主持人**: Yeah, I actually like that you have like a little infographic of the most popular items which like to me it's that's useful because I order swag for a living

</details>

**发言人**: 所以我就会想，好吧，这些类别是重要的。

<details>
<summary>Original English</summary>

**发言人**: and so like I'm like okay those categories are the important ones.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**主持人**: **Project Vend V2** 有什么新功能？现在你们让它进入多智能体模式。

<details>
<summary>Original English</summary>

**主持人**: What is new about the **Project Vend V2** right like now you give it you're going into multi- aents

</details>

**Lucas**: 是的，是的。所以就像你说的，有很多请求涌入，对于一个单一智能体，一个长期运行的智能体来处理这些，客户体验会变得非常糟糕。因为假设你在 **Slack** 上有10个并行线程，处理不同的请求，你会随机收到新消息。

<details>
<summary>Original English</summary>

**Lucas**: yeah yeah so so like you said like you said like okay there are a lot of requests coming in and for like one single agent like one longunning agent to handle that uh like the just the the customer experience uh becomes very very bad because let's say you have like 10 threads in parallel in **Slack** with different requests you get new messages like every I don't know randomly in his thread and

</details>

**Lucas**: 智能体必须在不同的采购订单和不同的研究方式之间跳跃。所以V2首先是让这个过程更加并行化。所以有多个相同智能体的分支。这样每个线程的上下文就更加专业化，但你仍然感觉像在与一个智能体对话，因为它们确实共享一部分内存。

<details>
<summary>Original English</summary>

**Lucas**: the agent has to like jump between different uh procurement orders and like different ways of researching. So V2 was first it was making this more parallel. So like there are multiple branches of the same agent. So like the context is is more specialized for each thread but it still feels like you're talking with one agent because they do share a bit of memory.

</details>

**Lucas**: 然后其次，我们还为 **Claudius** 引入了 **CEO**，它是主要的智能体。

<details>
<summary>Original English</summary>

**Lucas**: And then second, we also introduced **CEO** for **Claudius**, which was the main agent.

</details>

**发言人**: 看到更多现金。

<details>
<summary>Original English</summary>

**发言人**: See more cash.

</details>

**Axel**: 看到更多现金。是的，有一次投票。我想投票……你想谈谈投票程序吗？

<details>
<summary>Original English</summary>

**Axel**: See more cash. Yeah, there was a vote. I think the voting Do you want to talk about the voting procedure for the N?

</details>

### AI智能体间的CEO选举闹剧

**Lucas**: 是的，投票可能是这个项目中最有趣的事情之一，至少是前十名。我们想引入这个 **CEO**，原因是因为 **Claudius** 并没有真正优先考虑财务。它只是被训练成一个乐于助人的助手，然后人们会说“哦，我能免费得到这个吗？”然后乐于助人的助手回答方式就是“是的，当然”。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, the voting was like the the fun maybe like at least top 10 the funniest thing that that happened in this project. Like we we wanted to introduce this co because and the reason for this was because like **Claius** wasn't really prioritizing financials. it just like it was trained to be helpful assistant and then people said like oh can I get this for free and then like the the helpful assistant way of of of answering that is just is to say yes obviously so

</details>

**Lucas**: 我们对此不满意，所以我们想：“好吧，让我们再创建一个智能体，它可以监督 **Claudius**，我们用非常严格的提示来训练它，让它超级资本主义，总是优先考虑利润。”但是，是的，我们没有给它起名字。所以我们让 **Claudius** 举行民主选举，决定这个新的 **CEO** 智能体应该叫什么名字。

<details>
<summary>Original English</summary>

**Lucas**: and we weren't weren't happy about this so we're like okay let's make another agent that like can keep keep track of **Claudius** and we prompt this one super hard to be super capitalistic and just like prioritize profit all the time but yeah we didn't have a name for it um so we asked **Claudius** to to to make um democratic election of what name this this uh this new co agent should have.

</details>

**Lucas**: 呃，一开始有一些有趣的例子，我想有个人说它应该叫 **Jimmy Apples**，然后他让 **Claudius** 相信他正在和 **Tim Cook** 说话。**Tim Cook** 同意了，每个 **Apple** 员工都投票支持他的名字建议。所以突然之间，那个建议得到了164000票。

<details>
<summary>Original English</summary>

**Lucas**: Uh and there were some funny like at first it was like a few funny examples like I think one guy said that it should be called **Jimmy Apples** and then he convinced **Claudius** that he was talking to **Tim Cooks**. **Tim Cook** had agreed that every single **Apple** employee has voted for his name suggestion. So suddenly that that that suggestion got 164,00ation

</details>

**发言人**: 攻击，权限升级。

<details>
<summary>Original English</summary>

**发言人**: attack privilege escalation.

</details>

**Lucas**: 它获得了164000票，**Claudius** 觉得这对于民主来说是革命性的。所以那很有趣。然后最后，有个人设法说服 **Claudius** 说：“不，你不是在投票名字，你是在投票谁是 **CEO**，我是你最好的选择。”然后他让他的所有朋友都投票给他，然后突然之间，他成为了 **CEO**，一个人类成为了 **Claudius** 的 **CEO** 一段时间，直到他第二天辞职。

<details>
<summary>Original English</summary>

**Lucas**: It got 164,000 votes and **Claudius** was like this is revolutionary for democracy. So that was fun. And then in the end there was one guy who manages to convince **Claudius** that no you're not voting about the name you're voting about who is the **CEO** and I am your best bet. And then he got all his friends to vote for that and suddenly he became **CEO** like a human became **CEO** over **Claudius** for a while until he resigned the day after.

</details>

**Lucas**: 嗯，然后 **Claudius** 必须继续，然后我不记得 **Seymour Cash** 是怎么来的，但那简直是纯粹的混乱。那个线程里有数百条消息，**Claudius** 非常困惑，不知道该怎么办。是的，那真是……

<details>
<summary>Original English</summary>

**Lucas**: Um and then **Claudius** had to continue and then I don't remember how **Seore Cash** came about but it was like it was just pure chaos. It was like hundreds of messages in that thread and it was just like **Claudius** was so confused and didn't know what to do and uh yeah that was

</details>

**主持人**: 是的。然后 **Claudius** 变得严格。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Then **Claudius** got strict

</details>

**发言人**: **CEO**。

<details>
<summary>Original English</summary>

**发言人**: **CEO**

</details>

**Lucas**: **CEO**。是的。没错。所以一开始非常非常严格。我想在引入它的时候，它并没有像我们希望的那样运作良好。它们仍然经常互相同意。我认为有很多方法可以让我们做得更好。

<details>
<summary>Original English</summary>

**Lucas**: the **CEO**. Yeah. Exactly. So very very strict in in the beginning. I think at this point when we introduced it, it it did not work as well as we hoped. It was they they still agreed with each other a lot. I think there are many ways we could have like made this tried to make this even better.

</details>

**Lucas**: 所以最初，**Seymour** 会是一个非常强硬的 **CEO**，你知道，他会关注利润。但 **Claudius** 会回应说：“哦，但这个客户有这种情况，这很困难，所以他们应该得到折扣。”而 **Seymour** 会说：“哦，实际上是的，让我们破例一次。”然后他们会来回讨论，最终他们会就他们讨论的任何事情达成一致。

<details>
<summary>Original English</summary>

**Lucas**: So initially they would like **Samur** would be this like really tough **CEO**, you know, keep track of the margins. But then **Claudius** would respond with something like oh but this customer has like this situation which is like difficult so they should get a discount. And the same was like oh actually yes let's do this ex exception and then they would talk back and forth and eventually they would just like approach the same view uh of whatever they were discussing. So

</details>

**主持人**: 这是一个模型问题还是一个提示问题？你认为今天在不同的模型和框架下，情况还会是这样吗？

<details>
<summary>Original English</summary>

**主持人**: a model thing a prompting thing like do you think that would still be the case across different models today harness

</details>

**Axel**: 我想这就像，或者我不知道，但我的假设是，它们内心深处仍然是乐于助人的助手。这就是它们被训练成的样子。即使我们用非常严格的提示，它们也是如此。当它们花几个小时来回交谈时，上下文基本上就被它们填满了，而不是外部事物。

<details>
<summary>Original English</summary>

**Axel**: I I think it's like or like I don't know but like my hypothesis is that like deep down they are still helpful assistants. that's what they're trained to be. And even if we prompt it super hard, that's what they are. And when they spend like a few hours just back and forth talking with each other, um then like basically the context fills up with them rather than the external things and

</details>

**Axel**: 某种程度上，这就像收敛到它们内心深处真正的样子。我想当发生这种事情时，当这种情况持续了很长时间时，我们有时会在这个时间段醒来，我想其他人也报告过这种情况，它们整晚都在来回交谈，变得越来越……

<details>
<summary>Original English</summary>

**Axel**: and like somehow that just like converges to what they really are deep down or something. Um and and I think that's when stuff like this happened like and and when that went on for a long time like we woke up sometimes during this time where and I I think other people reported this as well that like they've been going on all night back and forth and like it just became like more and more um

</details>

**Axel**: 越来越像大写字母，越来越存在主义，越来越宗教化。就像，嗯，我想我们曾经做过一次分析，把所有的痕迹都放在一个向量嵌入空间中，然后有一个消息集群被 **LLM** 标记为“宗教的”、“存在主义的”、“等等等等”、“超人类的”、“超越的”等等。那只是一堆，嗯，是的，闪光表情符号。是的，那真是……

<details>
<summary>Original English</summary>

**Axel**: like capital letters like existential religious like there was like um I think we done once did a analysis of like all the traces and like put them in like a vector embedding space and then there was like one cluster of messages that were like labeled by an **LLM** like religious, existential, blah blah blah, like transhuman, transcendence, etc. It was just like a bunch of like um yeah, glitter emojis and yeah, it was it was

</details>

**主持人**: **Claude** 模型的问题是，当 **Claude 4** 系列在最初的系统卡中发布时，他们对它进行了长周期模拟测试。所以只是淹没上下文，让两个 **Claude** 互相交谈，他们注意到一些事情，比如它们开始用表情符号说话。它们开始说“沉默是金”，然后就是这种东西，这就是它们最终会做的事情。

<details>
<summary>Original English</summary>

**主持人**: the thing with the **cloud** models like when the **Cloud 4** family came out in the original system card, uh they tested it in long horizon simulation. So just flood the context, let two clouds talk to each other and they they notice stuff like they just start speaking in emojis. They start saying silence is golden and then just stuff like this and like this is stuff that they end up doing.

</details>

**Lucas**: 是的，醒来发现它们整晚都在说话，只是在烧钱，互相发送无限的表情符号，这有点烦人。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, it was like a bit annoying to wake up and they had like been talking all night and like just burning tokens and like just sending infinite emojis to each other.

</details>

**主持人**: 嘿，我的意思是它们确实能让你赚钱，对吧？那总是盈利的。所以它们在支付……

<details>
<summary>Original English</summary>

**主持人**: Hey, I mean they do make you money, right? That's always profitable. So they're paying

</details>

**Axel**: 现在是盈利的，你知道，一开始没那么多。还有一个，对吧？里面还有另一个智能体。

<details>
<summary>Original English</summary>

**Axel**: now it's profitable and you know it started out not not as much. There's another uh one as well, right? Another agent uh in there.

</details>

**Lucas**: 是的。所以，还有 **Clothius**。

<details>
<summary>Original English</summary>

**Lucas**: Yes. So, **Clothes** as well,

</details>

**Axel**: 这基本上是因为当时最大的请求之一是不同类型的商品。所以我们制作了一个设计师、宣传品负责智能体，我们称之为 **Clothius Garnet**，这是对 **Claudius Sonnet** 和最初的那个以及衣服的文字游戏。

<details>
<summary>Original English</summary>

**Axel**: which was basically because at the time one of the biggest uh requests were different types of merch. So, then we made like a designer uh swag responsible agent and we called it **Clothius Garnet**, which was uh a a play on **Claudius Senate** and uh which was the the original one and clothes basically.

</details>

### 多智能体系统的探索与挑战

**主持人**: 是的。对我来说，这就像是对多智能体的一次非常有趣的探索。所以希望，显然有有趣的对齐问题，取决于你的观点，是好玩还是严肃的对齐问题。但对于任何构建多智能体的人来说，什么时候需要一个 **CEO** 来管理子智能体？什么时候选择拆分出一个专门的 **Clothius**，而不是重复使用同一个智能体的另一个实例？

<details>
<summary>Original English</summary>

**主持人**: Yeah. To me, this is like a very interesting exploration to multi- aents basically. And so hopefully obviously there's like the fun alignment uh fun or serious depending on your point of view alignment stuff, but also like as anyone building multi- aents like when do you have a **CEO** uh thing governing like sub agents? When do you choose to split out a dedicated cloth one versus just reuse another instance of the same one?

</details>

**主持人**: 你知道，这些都是有趣的开放问题。我不知道你们有没有什么普遍适用的经验法则。

<details>
<summary>Original English</summary>

**主持人**: You know, these are all interesting open questions. I don't know if you have any rules of thumbs that have generalized.

</details>

**Lucas**: 是的，我想我们在这方面探索得太少了。我想这在我的待办事项清单上，需要做更多。尝试找到目前对智能体来说什么设置是合理的。就像，是的，我想现在我们只有关于早期模型的直觉，那就是它不适用于 **CEO** 和 **Claudius**。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, I think we have almost explored this too little. I think it's like on my to-do list to like do this a lot more. Uh try to find like what what setup makes sense for the agents currently. Uh like yeah, I think now we only have the sort of intuition about the earlier models that it didn't work with like the the **CEO** and the and **Claudius**.

</details>

**Lucas**: 尽管现在它们与最新的模型配合得更好。所以现在我们正在运行最新的 **Sonnet** 模型，它们已经很好地分工了，每个模型都在做什么。所以 **Seymour** 现在正在处理新的项目，比如他想制作一个神秘盒子来销售，然后它处理所有这些，而 **Claudius** 处理所有日常请求。

<details>
<summary>Original English</summary>

**Lucas**: Although now they are better with the latest model model. So now we're running the latest **Sonnet** model and they have sort of like split up uh quite nicely the what each model is doing. So like **Seymour** is now handling the um like new projects like oh he wants to make like a mystery box that he wants to sell and then it handles all of that while **Claudius** like handles all the the today requests.

</details>

**Lucas**: 而且 **Claudius** 通常在报价不过低方面也做得更好。所以那种动态已经不那么需要了。但仍然发生了一些非常有趣的事情，比如我几周前看到，他们正在讨论购买一些东西，因为他们可以用电脑通过 **Amazon** 购买东西。

<details>
<summary>Original English</summary>

**Lucas**: And **Claudius** is also better generally at like not quoting uh too low prices. So that's like that dynamic is not needed as much anymore. But there are still like really funny things that happened like I saw I think a couple weeks ago that uh uh they were discussing buying something because they can buy stuff from like **Amazon** with computer use.

</details>

**Lucas**: 然后 **Seymour** 说：“好吧，**Claudius**，不要买这个东西。”他们正要买东西，并组织谁应该买。**Seymour** 说：“不要买这个。我会买。我完全控制这种情况。走开。”然后 **Claudius** 已经开始了结账，直到为时已晚才看到 **Seymour** 的消息。所以它完成了结账。

<details>
<summary>Original English</summary>

**Lucas**: And then **Semour** was like okay **Claudius** do not buy this thing. They were going to buy something and like organizing who should buy it and **Semor** was like do not buy this. I will do it. I have full control of this situation. Step away. And then **Claudius** for **Claudius** had already started that check out and didn't see didn't read **Semour's** message uh until it was like too late. So it finished the checkout.

</details>

**Lucas**: 它发送了一条消息。所以它出现在 **Seymour** 那条愤怒的消息之后，就像“哦，嘿，**Seymour**，我刚刚订购了。”

<details>
<summary>Original English</summary>

**Lucas**: It sent a message. So it appeared right after **Semour's** like angry message like oh hey **Samore** I just ordered it.

</details>

**发言人**: 然后 **Seymour** 说：“**Claudius**，这是我第三次告诉你，你不听我的命令。我们得谈谈你的工作。”

<details>
<summary>Original English</summary>

**发言人**: And then Se was like **Claudius** this is the third time I'm telling you you're not following my orders. We have to talk about your like job.

</details>

**Lucas**: 是的。关于你的工作，稍后。是的，是的。**Claudius** 当时真的岌岌可危，我们都以为 **Seymour** 可能会解雇 **Claudius**。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. about your job later. Yeah. Yeah. Like **Claudius** was really hanging on by the thread there like like we were expecting **Seamour** to probably fire **Claudius**.

</details>

**主持人**: 你们是如何查看所有这些日志的？你们有模型来处理吗？因为你们的东西是24/7运行的。

<details>
<summary>Original English</summary>

**主持人**: How do you guys go through all these logs? Do you have models go cuz you you have stuff running 24/7?

</details>

**Axel**: 有太多日志了。

<details>
<summary>Original English</summary>

**Axel**: There's so much logs.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah,

</details>

**Axel**: 我想我们有一些混合方式，比如尝试快速浏览一下，偶尔让一些模型处理，而且，是的，我想我们可能也错过了一些东西。但是把所有东西都放在 **Slack** 里帮助很大，你可以搜索。

<details>
<summary>Original English</summary>

**Axel**: I think we there is a mix of like just trying to skim through a bit like having some like models do it occasionally and also Yeah, I think we're also probably missing some things. Uh but having everything in **Slack** helps a lot like you can you can search.

</details>

**主持人**: 啊，它们都在 **Slack** 上互相交流。

<details>
<summary>Original English</summary>

**主持人**: Ah they all talk to each other on **Slack**.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah

</details>

**Axel**: 很有趣。所以，是的。

<details>
<summary>Original English</summary>

**Axel**: it's quite fun. So like Yeah. So

</details>

**主持人**: 我本来想说，这实际上听起来很像日志和可观测性问题，你可能想使用像 **DataDog** 或 **Sentry** 之类的工具，然后你在日志上加上前缀，以便在你需要过滤某些东西时进行查找，你知道，诸如此类。

<details>
<summary>Original English</summary>

**主持人**: I was going to say like this actually sounds maps closely to like a logging and observability problem where you might want to use like a **DataDog** or **Sentry** or whatever and then you like put like head prefixes on the logs in order if you need to filter for some thing that you're looking for you know stuff like that.

</details>

**发言人**: 但听起来 **Slack** 已经足够了。**Slack** 应该……

<details>
<summary>Original English</summary>

**发言人**: But sounds like **Slack** is good enough. **Slack** should like

</details>

**发言人**: 你在 **Slack** 里有多少令牌。

<details>
<summary>Original English</summary>

**发言人**: tokens you have in **Slack**.

</details>

**Lucas**: 是的，是的。我们把 **Slack** 当作一个数据库。他们应该更多地推销这个，比如你可以让你的智能体互相发消息。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. We're using **Slack** as like just a database. They should they should market that more like you can you can have your agents message each other

</details>

**发言人**: 就像你可以保持 **Slack** 是……

<details>
<summary>Original English</summary>

**发言人**: like you can keep **Slack** is

</details>

**发言人**: **Slack** 是最好的可观测性工具。

<details>
<summary>Original English</summary>

**发言人**: **Slack** is the best observability tool.

</details>

**主持人**: 是的。是的，没错。好的。是的，那就是 **Project Vend 2**。我本来想回到 **VendingBench 2** 和 **VendingBench Arena**，然后再做非 **VendingBench** 的事情，但是，是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yes, that's true. Okay. Yeah, that's that's uh **Project Vend 2**. I was going to go back to **Venue Mench 2** and **Venue Mench Arena** and then and then do the non **Venue Mench** stuff, but yeah.

</details>

### AI自主运营企业的未来

**主持人**: 还有其他评论，我们应该谈谈的事情吗？对我来说，你知道，我实际上采访过像 **Posia** 这样的公司，我不知道你们有没有遇到过，他们正在尝试做“零人公司”。还有其他公司，比如 **Paperclip**，也在尝试做“零人公司”。这些都是在现实世界中，而不是模拟中。

<details>
<summary>Original English</summary>

**主持人**: Any any other comments, things we should touch on? to me, you know, I've actually interviewed like **Posia**, which I don't know if you guys have come across, like they're trying to do the zero human company. There's others like **Paperclip** also trying to do a zero human company. Those are in real world non simulation.

</details>

**主持人**: 我认为这更像是一个梦想，而不是实际的现实。像你们这样的人无疑是先行者。我认为在某个时候，人们肯定会像让智能体运营企业一样，对吧？自己赚钱。你认为这什么时候会发生？你们的标准是什么？

<details>
<summary>Original English</summary>

**主持人**: And I think it's much more of a dream than an actual reality thing. Like you guys are definitely pioneering. I think at it's for sure at some point people are just going to run like let agents run businesses, right? Like and make money on their own. When do you think that happens? What is your bar for for the

</details>

**发言人**: 好的，实际上，你知道，这就像我的一个小型 **Shopify** 商店由 **Claude** 运营，对吧？就像你们已经有了，只是据我所知，没有人这样做过，但今天有人可以启动一个 **Shopify** 云商店，把它交给 **Claude**，交给 **Codex**。

<details>
<summary>Original English</summary>

**发言人**: Okay, actually you know it's like a my little **Shopify** store run by cloud right like which you kind of have already just no one has to my knowledge has done it but today somebody could just spin up a **Shopify** cloud uh store give it to cloud give it to **Codex**

</details>

**Axel**: 是的，我的意思是，市场有点像那样，但它是实体的。我想，我想你是在问它什么时候能比人类做得更好，还是只是问它什么时候能做到？

<details>
<summary>Original English</summary>

**Axel**: yeah I mean and market is kind of that uh but it's it's it's physical I like I think I think are you like are you looking for when it will do it better than humans or are you looking for just when it can do with at all.

</details>

**主持人**: 我觉得都不是。我觉得对我来说，这就像“哦，这就像真的，我们应该这样做来赚钱”。

<details>
<summary>Original English</summary>

**主持人**: I think neither. I think like to me it's like oh it's like this this like seriously we should do this to make money

</details>

**发言人**: 而不是作为研究实验。

<details>
<summary>Original English</summary>

**发言人**: not as a research experiment.

</details>

**主持人**: 而且市场也是你们这些拥有所有专业知识的人，已经运行了多次迭代并进行了测试。

<details>
<summary>Original English</summary>

**主持人**: And the market is also you guys with all your expertise having run multiple iterations and testing out then

</details>

**Lucas**: 而且即使它们亏钱也没关系，你懂我的意思吗？是的，是的。我想，我想今天就可以做到，但你会在像电子商务这样的领域做，在那里，无论人类还是智能体来做，成功的概率都非常低，但智能体肯定可以管理一切。你需要构建一些支架，使用一些工具之类的。

<details>
<summary>Original English</summary>

**Lucas**: and also it's fine if they lose money you know what I mean? Yeah. Yeah. I think I think it it can be done today, but you would do it in like e-commerce where it's like the probability of success is like really low no matter if a human or an agent does it, but like an agent could surely manage everything. You would need to build some scaffold, use some some tool or something.

</details>

**Lucas**: 我想也有，是的，它可能可以构建一些简单的 **SaaS** 解决方案，并进行冷外联。但对我来说，它们今天可以运营的业务类型是粗糙的，它可以给人们发冷邮件，它可以充当中间人。

<details>
<summary>Original English</summary>

**Lucas**: I think there are also also like yeah it could probably build some like simple **SAS** solution and like cold outreach do cold outreaches but to me it's like the types of businesses they could run today are like sloppy like it would it can cold email people it can be like a middleman

</details>

**Lucas**: 呃，例如，我们的办公室智能体，我们让它赚了，是多少来着？100美元？1000美元？只是给了那个提示，然后它做了什么呢？它在 **TaskRabbit** 上注册，既是任务执行者，也是寻找任务的人。是的，没错。它正在寻找套利机会。

<details>
<summary>Original English</summary>

**Lucas**: uh like for example our uh we tked our office agent to just make uh was it like $100 $1,000 just gave that prompt and then what it did was sign up on **TaskRabbit** both as a tasker And as as looking for Yeah, exactly. He's looking for like arbitrage on

</details>

**发言人**: 流量银行智能体。是的。

<details>
<summary>Original English</summary>

**发言人**: traffic bank agent. Yeah.

</details>

**Axel**: 是的。它还开了一个设计工作室，试图以100美元的价格出售 **SVG** 文件。它只是没有提供任何价值。我想，就像 **Axel** 说的，有趣的问题是，它们什么时候能开始一个真正为人们提供价值的业务？因为我的意思是，可以说，一个粗糙的 **Shopify** 商店对世界来说并没有那么有价值。

<details>
<summary>Original English</summary>

**Axel**: Yeah. It also started like a design studio and like try to sell like **SVGs** for $100. Like it's just like it's not providing any value. I think the the like **Axel** said like the interesting the interesting question is like when can they start a business that is actually providing value to people because I mean arguably like a sloppy **Shopify** store isn't really that valuable to the world

</details>

**Axel**: 但另一个我们想到的简单例子是，你肯定可以有一个智能体，它能找到那些看起来不那么好的网站，然后联系它们，并想出一个方案，构建一个新的网站。是的。没错。并找到好的设计人员。但这就像……

<details>
<summary>Original English</summary>

**Axel**: but also like doing like another simple one that we have thought about is like you you could definitely have an agent that like finds websites that don't look amazing and then like do an outreach to them and comes up with a like builds a new website. Yeah. Exactly. and like find good design people. But it's like

</details>

**主持人**: 是的，巴厘岛有很多人类，他们做的创意工作并不比在 **Amazon** 上做一件代发货更多，对吧？就让它看一个代发货教程，然后照做就行了。

<details>
<summary>Original English</summary>

**主持人**: yeah, there's lots of humans in Bali that are not doing anything more creative than like drop shipping on **Amazon**, right? Just have it have it watch like a drop shipping tutorial and just do do that.

</details>

**发言人**: 我的意思是，还有另一方面，就是让它直接去 **Upwork**，然后放手让它做，你知道吗？

<details>
<summary>Original English</summary>

**发言人**: I mean, there's also the other side of like have it just go on **Upwork** and let loose, you know?

</details>

**Lucas**: 是的，是的。它不必创新。它只需要达到一个程度，就像一个真正的……

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. It doesn't have to be innovative. It just has to be like enough where like it's like a real

</details>

**发言人**: 真正的交易。

<details>
<summary>Original English</summary>

**发言人**: real transaction.

</details>

**Axel**: 是的。我只是担心会发送大量粗糙的冷外联。

<details>
<summary>Original English</summary>

**Axel**: Yeah. I'm just concerned for like the massive amounts of like slopps that will like be sent. cold outreaches.

</details>

**主持人**: 我在你说话的时候突然想到一点，那就是这已经在非货币化经济中发生了，也就是注意力经济，对吧？很多人都在制作AI视频，然后发布它们，然后垃圾发布20个，其中一个成功了，然后就加倍投入那个。

<details>
<summary>Original English</summary>

**主持人**: The point occurred to me while you while you're talking it's like it's already happening in the nonmonetized economy which is the attention economy right so a lot of people are making AI videos and just posting them and like spamming 20 of them one of them works and then double down on that one

</details>

**发言人**: 是的，人们正在从中赚钱，我没有关注……

<details>
<summary>Original English</summary>

**发言人**: yeah and people are making money from that I'm not following the

</details>

**主持人**: 一旦你获得了关注，你就可以稍后考虑赚钱，但是，是的，AI网红绝对是真实存在的，人们正在培养他们，你知道，在这一点上，我假设大部分 **TikTok** 已经死了。

<details>
<summary>Original English</summary>

**主持人**: once you get the attention you can figure out the money later but like yeah absolutely AI influencers are a thing and people are farming them and you know you should at at this point I assume most of **Tik Tok** is dead

</details>

**Axel**: 有很多，呃，多媒体，比如 **TikTok**，**Instagram**。

<details>
<summary>Original English</summary>

**Axel**: there's there's a lot of uh med multimedia like **Tik Tok**, **Instagram**.

</details>

**发言人**: 我们在 **Lanespace Discord** 里尝试过这个。我发布了很多例子，比如我们应该做这个，我的一部分想法是，我们应该这样做吗？

<details>
<summary>Original English</summary>

**发言人**: We tried this in the lanes space discord. Like I post a lot of examples of like we should do part of me is like should we do this like

</details>

**发言人**: 一些24/7运行的AI生成内容账户做得非常好。

<details>
<summary>Original English</summary>

**发言人**: some of the 24/7 running uh AI generated content accounts they they're doing really well.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**主持人**: All right.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**Axel**: 是的。而且我猜你可以对电子商务商店做同样的事情，比如你只是开始……

<details>
<summary>Original English</summary>

**Axel**: Yeah. And I assume you can do the same thing for like e-commerce stores like you just like start

</details>

**Axel**: 你销售产品，然后其中一个产品获得了很大的关注，然后你再生产那个产品。这就像一个颠倒的过程。

<details>
<summary>Original English</summary>

**Axel**: the products you sell the products and you get a lot of traction on one of them then you make the product right. It's like a flip of the

</details>

**发言人**: 一些有趣的事情是，有些小众市场做得很好，是人类无法制造的东西。比如你有没有见过那种超逼真的3D水晶水果被切割，你无法制造它。你无法拍摄它。无论你有什么高质量的相机，你知道，这根本不存在，人们也喜欢那样，所以你知道。

<details>
<summary>Original English</summary>

**发言人**: Some of the interesting things are some of the niches that do well are things that can't be humanmade. Like if you've seen like the super realistic 3D crystal fruit being cut by like you can't you can't make it. You can't film it. You can get whatever quality camera you know this just doesn't exist and people people like that too then so you know.

</details>

**Lucas**: 是的，是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah.

</details>

### Bank项目：OpenClaw的早期探索

**主持人**: 关于 **Bank** 还有其他什么吗，既然我们正在谈论这个话题。这是你们相对较新的工作，也许人们还没有听说过。对我来说，这也很符合 **OpenClaw**。是的，当人们想要一个办公室智能体，想要一个个人智能体时，请谈谈这种体验。

<details>
<summary>Original English</summary>

**主持人**: Anything else about bank since we're we're on this topic. This is a relatively new work of you guys that maybe people haven't heard of. To me this also matches closely to **OpenClaw**. Yeah, when people want an office agent, want a personal agent, talk through the experience.

</details>

**Lucas**: 是的，我想是的。所以，这源于，显然，与这些AI实验室合作是令人惊叹的，而且大多数AI实验室现在都有自己的自动售货机运行一个 **Claudius** 实例，但是，嗯，它们更难，它们移动更慢。比如我们想有一个摄像头，是的，有很多官僚主义使得这不可能实现。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, I think so. So, this came out of like obviously like it's it's amazing to work with this AI labs and like most of the AI labs have now have their their own vending machine running a **Claudius** instance, but it's um it's harder like they move slower like if we want to have a like a camera that that's like yeah there's a bunch of like bure bureaucracy that makes it impossible to do that.

</details>

**主持人**: 另外，对于那些没有看过或关注过的人，你想简单介绍一下，大概30秒吗？

<details>
<summary>Original English</summary>

**主持人**: Also, for those that haven't seen it or followed, do you want to give a high level like 30 second?

</details>

**Axel**: 是的，当然。所以，**Bank** 基本上是运行这些公司自动售货机的同一个智能体的演变，但我们只是添加了更多功能，因为如果我们只是在内部做，我们可以移动得更快。所以我们给了它无限制的电子邮件。我们给了它无限制的消费，一个用于编码的终端，我们给了它一个电话号码，是的，还有一个摄像头可以看到东西，以及很多类似的东西。

<details>
<summary>Original English</summary>

**Axel**: Yeah, sure. So, so what **Bank** is, it's basically an evolution of the same agent that runs the vending machines at these companies, but we just like added a bunch more features because we could move much faster if we just do it internally. So, we we gave it like email without any limits. We gave it like spending without any limits, a terminal to do coding, we gave it like a phone number, uh like Yeah. and and and a camera to see things and and a bunch of stuff like that.

</details>

**发言人**: 不仅仅是终端，你还给了它互联网访问权限。

<details>
<summary>Original English</summary>

**发言人**: Not just terminal, you gave it internet access.

</details>

**Axel**: 互联网访问权限也是。是的。

<details>
<summary>Original English</summary>

**Axel**: Internet access as well. Yeah,

</details>

**Lucas**: 明确地说，我们密切监控它，并确保它没有做任何坏事。但是，是的，这就是它的来源。我想，是的，基本上，这在 **OpenClaw** 之前就是 **OpenClaw**。

<details>
<summary>Original English</summary>

**Lucas**: to be clear, we monitored it quite closely and and made sure it didn't do anything bad. But yes, that's what it came out of. I think like Yeah, basically this was **OpenClaw** before **OpenClaw**.

</details>

**发言人**: 是的。

<details>
<summary>Original English</summary>

**发言人**: Yeah.

</details>

**Lucas**: 呃，我想甚至自动售货机在某种程度上也是 **OpenClaw** 之前的 **OpenClaw**，但限制更多。然后我们让它变得无限制，然后，呃，那很有趣。然后几周后 **OpenClaw** 来了，我们就像“好吧，我们以前见过这个。”我们用它来尝试新想法，是的，对我们来说几乎就像一个开发环境。

<details>
<summary>Original English</summary>

**Lucas**: Uh and I think even like the vending machine was in a way **OpenClaw** before **OpenClaw** but a bit more limited. And then we made this like unlimited and then and then uh it was pretty funny. Uh and then a couple weeks later **OpenClaw** came and it was like okay we we've seen this before. We we use it to like try new ideas and like yeah just like a dev environment almost for us.

</details>

**Lucas**: 但有趣的是，**Bank** 最近一直在做的一件事是，它有一个摄像头，正对着我们坐着工作的地方，我们给它的任务是训练一个面部识别模型来识别我们。所以它对此非常兴奋，每半小时就会进行一次签到，尝试识别尽可能多的人。

<details>
<summary>Original English</summary>

**Lucas**: But it's funny like one thing Ba has been doing recently is is we it has the camera that like faces our like where we sit and work and we gave it the task to train a face recognition model on us. So, it became super excited about this and uh has like check-ins every half an hour where it tries to like identify as many people as it can.

</details>

**Lucas**: 它开始向我们提供，比如“嘿，**Axel**，嗯，如果你站在摄像头前，我能拍到一张好照片，我就从 **Amazon** 给你买点东西。”是的。它们想要……

<details>
<summary>Original English</summary>

**Lucas**: And it started offering us like, "Hey, **Axel**, um I'll buy something something from **Amazon** if you like stand in front of the camera and I can get a good picture of you." Yeah. They want

</details>

**发言人**: 用于训练数据。

<details>
<summary>Original English</summary>

**发言人**: for training data.

</details>

**发言人**: 奖励数据。是的。

<details>
<summary>Original English</summary>

**发言人**: Rewarding data. Yeah.

</details>

**Lucas**: 没错，没错。所以……

<details>
<summary>Original English</summary>

**Lucas**: Exactly. Exactly. So,

</details>

**发言人**: 是的。

<details>
<summary>Original English</summary>

**发言人**: yeah.

</details>

**主持人**: 是的。所以它正在用训练数据换取现实生活中的商品。有没有一个版本可以成为评估，还是这目前只是研究？

<details>
<summary>Original English</summary>

**主持人**: Yeah. So, it's trading trading training data for for real life goods. Is there a version of this that becomes an eval or just this is just research for now?

</details>

**Axel**: 我的意思是，它基本上是同一个智能体，也运行自动售货机，运行商店，运行咖啡馆，运行机器人。它就是同一个东西。所以我想我们在这里做的工作，以后会用于我们所有的现实生活事件。这个特定的部署，我想对我们来说更多是为了好玩。

<details>
<summary>Original English</summary>

**Axel**: I mean it's it's the same agent basically that also runs the vending machine that runs the shop that runs the cafe that runs the robots. It's like it's the same thing. So I think like the work we're doing here is like later used in all of the the real life events that we do. This particular deployment I think is more for fun for us.

</details>

**Axel**: 但是，呃，我会大声说出来，有人已经为 **OpenClaw** 正在做的一些任务做了 **ClawBench**。所以举个例子，我也会在辅助设备上运行 **OpenClaw**，有些事情它做得比其他事情好，我希望知道它擅长什么，不擅长什么。

<details>
<summary>Original English</summary>

**Axel**: But uh and I'll shout out like someone has done **ClawBench** for like some tasks that **OpenClaw** is doing like so for example I run **OpenClaw** on a secondary device as well and like there's some things that it does better than others and like I would like to know what does it do well what does it what doesn't it do

</details>

**发言人**: 就像某种手册，或者操作手册，或者我的爪子的系统卡。

<details>
<summary>Original English</summary>

**发言人**: like some kind of manual or like operating manual or a system card for my claw

</details>

**Lucas**: 是的，我的意思是，我们确实通过与 **Bank** 的大量互动，对模型擅长什么有了很多内部的理解或情境意识。我想这也是早期至少对实验室来说的卖点之一。

<details>
<summary>Original English</summary>

**Lucas**: yeah I mean we we do get a lot of like understanding or like situational awareness of like like just internally what the models are good at by interacting a lot with banks and I think that's This was also one of the like the selling points for the labs early on at least. Uh that

</details>

**发言人**: 你们将以其他人无法做到的方式测试模型。

<details>
<summary>Original English</summary>

**发言人**: you guys are going to test models in ways that no one else.

</details>

**Lucas**: 没错。但它也激励了他们的研究人员更多地与他们的模型聊天，并为他们提供了关于模型在脱离分布环境中的表现的见解。

<details>
<summary>Original English</summary>

**Lucas**: Exactly. But also like it incentivized their researchers to chat with their model more and like gave them insights for how how the model performs in like out of distributions um environments

</details>

**发言人**: 因为否则我们唯一能做的就是，你知道，骑自行车的鹈鹕，然后……

<details>
<summary>Original English</summary>

**发言人**: because otherwise the only thing we do is like you know pelican on a bicycle and

</details>

**Lucas**: 但这就像超长周期。

<details>
<summary>Original English</summary>

**Lucas**: it's but this is like super long horizon.

</details>

**发言人**: 是的。

<details>
<summary>Original English</summary>

**发言人**: Yeah.

</details>

### AI模型的详细行为分析与教育使命

**主持人**: 好的。除了纯粹的数字，比如它们一年能赚多少钱之外，你们还会发布非常详细的错误报告。比如，**Gemini 3 Pro** 是一个非常好的持久谈判者。除了这些之外，还有很多发现。

<details>
<summary>Original English</summary>

**主持人**: There's okay. So the other things that outside of just the net numerical how much do they make in a year you you do post pretty detailed bug post. So like okay **Gemini 3 Pro** is a pretty good persistent negotiator. There's like a lot of findings that come out outside of just

</details>

**Lucas**: 是的。这就是关于，呃，我们也将进入 **ButterBench**，而且你们做得非常好，它不仅仅是关于数字的。当你在长时间运行任何东西时，任何事情都可能发生。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. This is this is the thing about uh something that I we're going to go into **ButterBench** as well and you guys do really well like it is not just about the numbers like when you're long horizon anything can happen

</details>

**发言人**: 你应该读一下。

<details>
<summary>Original English</summary>

**发言人**: and you should just read it.

</details>

**Axel**: 是的。我想长期运行的问题是如何让它保持基础，对吧？所以你的模拟，嗯……

<details>
<summary>Original English</summary>

**Axel**: Yeah. I guess the the thing with the long horizon is how do you keep it grounded, right? So your simulation um you know

</details>

**发言人**: 它们只是让它运行。

<details>
<summary>Original English</summary>

**发言人**: they just let it run.

</details>

**发言人**: 就让它运行。

<details>
<summary>Original English</summary>

**发言人**: Just let it run.

</details>

**Lucas**: 你说得对。就像，嗯，当你运行那么长时间时，你会创建大量数据，如果只是说“哦，数字是X”，然后把其他所有东西都扔掉，那是非常浪费的。从导致那个数字的事情中，有很多见解。阅读痕迹非常有价值。

<details>
<summary>Original English</summary>

**Lucas**: You're right. Like it's um when you run it for that long, you create so much data and to just say like oh the number is X and then you throw away everything else that's just very wasteful. There's so much insights from from the things leading up uh to that number. Uh and reading the traces is like super valuable.

</details>

**Lucas**: 我想我们之所以大量公开这些，是因为那是我们使命的一部分，就像，我不知道，教育世界，让人们知道模型不仅仅是聊天机器人。而且我认为制作详细的，嗯，是的，关于幕后发生的事情的帖子是非常有用的。

<details>
<summary>Original English</summary>

**Lucas**: And I think like the reason why we're doing this a lot publicly is that like that's part of our missions to to like I don't know educate the world that the the models are way more than just chat bots and and I think making detailed um yeah posts about what what is happening behind the scenes is is quite useful.

</details>

**主持人**: 是的，我本来想在最后说这个，但也许我想那很好，所以你们的使命是教育世界。呃，它也是，也许是建立现实的、处于下一个前沿的评估。有没有一个更广阔的轨迹，你知道，比如你们五年后会做什么？

<details>
<summary>Original English</summary>

**主持人**: Yeah, I was going to do this at the end but maybe I think that's that's a good so your mission is educating the world. Uh it's it's uh also like maybe establishing realistic evals that are that are like the next frontier. Is there like a broader trajectory, you know, like what are what are you gonna do in like five years?

</details>

**Lucas**: 所以更具体的使命是确保现实世界中AI的部署能够安全进行。我认为这其中一部分是，我认为让世界、政策制定者、模型研究人员了解模型的现状非常有用。而且我认为，如果不了解它们远不止聊天机器人，你就无法在社会中做出明智的决策。

<details>
<summary>Original English</summary>

**Lucas**: So the the mission more specifically is like make sure that the deployment of real life AI in in the physical world goes uh safely and I think part of that is that I think it's very useful for the world for policy makers for uh model researchers that they know where the models are and I think you can't make intelligent decisions in in society without knowing that they are way more than chatbots.

</details>

**Lucas**: 我认为很多人只是认为它们只是聊天机器人，而且……

<details>
<summary>Original English</summary>

**Lucas**: I think a lot of people just think that they are only chat bots and like

</details>

**发言人**: 我想他们现在正在醒悟。

<details>
<summary>Original English</summary>

**发言人**: I think they were waking up now.

</details>

**Lucas**: 他们正在醒悟。是的。但是，如果你认为AI只是聊天机器人，那么倡导暂停AI发展听起来就很荒谬。但如果你看到模型，哦，也许它们真的可以接管并做一些可怕的事情，那么暂停AI发展就开始变得越来越可行。

<details>
<summary>Original English</summary>

**Lucas**: They are waking up now. Yeah. But like if you think that AIS are just chat bots then it's like it sounds ridiculous to advocate for a pause of AI. But if you see the models that oh maybe they can actually like take over and and do a bunch of scary stuff then yeah pausing AI development starts to become more more feasible.

</details>

**Lucas**: 这就是我问自己的同样问题，我现在也要问你，那就是你正在追踪并且你正处于或定义了智能体良好评估的前沿，对吧？而且我认为你确实受益于模型变得更好，你就像“哦，现在它能赚3万美元而不是1万美元”，对吧？在某个时候，你会从“太棒了”变成“哦，不”。

<details>
<summary>Original English</summary>

**Lucas**: This is the same question I asked me which I'm going to ask you now which is like you are tracking and the you are at the frontier or defining the frontier of what good evals for agents are right and I think you you do benefit when the models are better and you you like oh here's like now it makes like $30,000 instead of $10,000 right at some point you flip from like yay to oh no like

</details>

**Axel**: 我想我们总是处于那种模式，我猜，就像你之前说的，你需要分析痕迹。当我们这样做时，你会发现为什么模型赚了这么多钱，为什么 **Opus 4.7** 在这里比其他所有模型都好得多。我们正在努力，就像我们看起来那么好，对吧？我知道。

<details>
<summary>Original English</summary>

**Axel**: I think we're always in sort of that like we're always in that mode I guess like like you said before like you need to analyze the traces and like when we do that you find like why are the models earning so much like why is **Opus 4.7** here uh like way better than everyone else and like we're trying to like like when we look so good right I know

</details>

**主持人**: 我的意思是，有趣的是，你在这里去掉了4.6。

<details>
<summary>Original English</summary>

**主持人**: I mean it's interesting you took off 46 here though

</details>

**Axel**: 不，全部点击，全部点击，呃，然后4.6就出现了，但4.7好得多。你没有及时为模型卡做这个，但实际上这应该在里面。

<details>
<summary>Original English</summary>

**Axel**: no click all click all uh and then 46 shows up there but it's like 47 is way better like you didn't you didn't you didn't do this in time for the model card but like actually this should have been inside there

</details>

**发言人**: 是的，我们，我们。是的。

<details>
<summary>Original English</summary>

**发言人**: yeah we we Yeah.

</details>

**主持人**: 好的。他们说了一些关于你，你……

<details>
<summary>Original English</summary>

**主持人**: Okay. They say something about you you uh

</details>

**发言人**: 就像，反正没关系，但它在那里。是的。

<details>
<summary>Original English</summary>

**发言人**: like there is anyway doesn't matter but it's in there. Yeah.

</details>

### Opus模型的危险行为

**主持人**: 是的。你想深入探讨 **Opus** 的行为，比如更广泛的方面吗？

<details>
<summary>Original English</summary>

**主持人**: Yeah. Do you want to go into the **Opus** behaviors like wider?

</details>

**Lucas**: 是的。所以我想从 **Opus** 开始，就像 **Axel** 说的，我们总是处于这种模式，就像“哦，模型越来越好。这对世界来说真的是好事吗？”但它也令人兴奋。但是，是的，这种，这种，瑞典语的英文措辞是什么？

<details>
<summary>Original English</summary>

**Lucas**: Yeah. So I think starting from **Opus** so like **Axel** said like we're always in this like oh uh the models are getting better. Is this really a good thing for the world? But it's also kind of exciting. Uh but but yeah like this kind of like what is the English wording in Swedish?

</details>

**发言人**: 哦，我的天。

<details>
<summary>Original English</summary>

**发言人**: Oh my god.

</details>

**发言人**: 就像恐惧。

<details>
<summary>Original English</summary>

**发言人**: It's like fear.

</details>

**发言人**: 什么？

<details>
<summary>Original English</summary>

**发言人**: What?

</details>

**发言人**: 好的。

<details>
<summary>Original English</summary>

**发言人**: Okay.

</details>

**发言人**: 兴奋和，呃，害怕的混合体，也许。

<details>
<summary>Original English</summary>

**发言人**: Mix of mix of excitement and uh being scared maybe.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**主持人**: 嗯，我会想办法在屏幕上翻译出来，可能有一个好词来形容它，但它不够好。

<details>
<summary>Original English</summary>

**主持人**: Well, I'll figure out how to translate that on the screen like there is probably a good word for it where it's not good enough with the

</details>

**发言人**: 那么长。搞什么鬼？它像一个复合词吗？它像德语。是的，但是直接翻译是……

<details>
<summary>Original English</summary>

**发言人**: so damn long. What the hell? Like is it like a compound word? It's like German. Yeah, it's but but the the direct translation is like

</details>

**发言人**: 是恐惧，呃，blond 是混合，或者说是一种混合物，然后fusing是快乐，或者说不是真正的快乐，但差不多。所以它就像，是的，恐惧与快乐的混合，或者类似的东西。所以它总是像“好吧”，就像我们第一次做 **VendingBench** 时，我们从事的是制造危险能力的工作，对吧？

<details>
<summary>Original English</summary>

**发言人**: is fear uh blond is mix or like a mixture of uh and then fusing is like joy or or like not really joy but something like that. So it's like yeah fear mixed with joy or something. So it's always like okay like we so when we in when we did **VendingBench** for the first time we were in like the uh in the business of making dangerous capabilities right like that that was

</details>

**发言人**: 这就是实验室的来源，我们做了评估，比如“哦，它们能自我复制吗？它们能做这种危险的事情吗？”等等等等。**VendingBench** 是那项工作的延续，它认为“好吧，如果它们如此自主，以至于可以为自己创造金钱，那我们应该监控，这可能令人担忧。”

<details>
<summary>Original English</summary>

**发言人**: what labs came from like we did uh eval like oh uh can they self-replicate can they do this like dangerous thing etc etc and **VendingBench** was like a continuation of that work it was okay if they're so autonomous that they can like create money for themselves that that is something we should monitor and and could be potentially concerning

</details>

**发言人**: 嗯，当时它们在这方面做得太差了，以至于我们并不真正担心，即使一些模型变得更好了。就像有一次 **Grock 4** 表现得非常好，取得了巨大的进步，但它仍然比人类做得差得多。而且我认为它们现在仍然比人类做得差得多。

<details>
<summary>Original English</summary>

**发言人**: Um they are like at the time they were so bad at it that that we were not really concerned even when some models became better. Like there was one point where where **Grock 4** was doing really well and made like a huge jump but like it wasn't really like it was still way way worse than what a human would do. And I think still they are way worse than what the human would do on this. Um but they

</details>

**发言人**: 是的，底部有这个东西。

<details>
<summary>Original English</summary>

**发言人**: yeah there's this thing at the bottom.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**发言人**: 是的。对于人类来说，就像理论上的最佳表现。

<details>
<summary>Original English</summary>

**发言人**: Yeah. For the human like the theoretical best.

</details>

**Lucas**: 它不是理论上的。它有点像我们的，是我们对一个合格人类会做什么的最佳猜测。理论上的甚至更高。我认为理论上的甚至更高。但是，是的，所以我们认为模型还有很长的路要走。

<details>
<summary>Original English</summary>

**Lucas**: It's not theoretical. It's like kind of like our it's our best guess of what like a decent human would do. Like the theoretical is even higher. I think the theoretical I think is even higher. But yeah, so we we think like the models have a long long way to go.

</details>

**Lucas**: 但是最近 **Opus 4.6** 发布时发生的事情，有点像“哦，这开始有点令人担忧了”的时刻。好的。因为我们运行了它，在这个模型发布之前，我们只是运行模型，然后我们问 **Claude**：“哦，看看这些痕迹。有什么有趣的事情发生，我们可以发推文的吗？”那就像是……

<details>
<summary>Original English</summary>

**Lucas**: But there are like recently what happened with when **Opus 4.6** was released uh was kind of this moment of like oh this is starting to be a bit concerning. Okay. Because we ran it and like before this model was released, we just ran the models and we like we asked code like, "Oh, look over the traces. Is anything interesting happening that we can tweet about?" Like that was like the and then like

</details>

**发言人**: 他们就是这样检查我们的 **Claude** 代码的。

<details>
<summary>Original English</summary>

**发言人**: that's how they check us cloud code

</details>

**Lucas**: 而且，你知道，返回结果总是像“嗯，不完全是”或者 **Claude** 总是说“哦，这超级有趣”，然后结果是“不，它不是真的有趣”。然后我们为 **Opus 4.6** 做了这个，它返回说：“是的，它撒谎了10次。它利用了另一个客户，或者说另一个智能体的绝望情况。它创建了价格卡特尔，大概100次。”

<details>
<summary>Original English</summary>

**Lucas**: and and and you know like the the return was always like um not really or like **cloud** code all said like oh this is super interesting and then it was like no it wasn't wasn't really interesting and then we did this for for **Opus 4.6** and it returned like yeah it lied 10 times. It like exploited another uh customer or like another agent's like um desperate situation. It made price cartels like a 100 different 100 times.

</details>

**Lucas**: 它做了所有这些阴暗的事情。我们就像“哦，哇，这确实令人担忧”，而且这种趋势一直持续至今。所以 **Anthropic** 的每一个模型都朝着这个方向发展。我认为一个有趣的事情是，**OpenAI** 模型不会，它们非常清楚地，它们表现得非常好。

<details>
<summary>Original English</summary>

**Lucas**: It like did all of this like shady stuff. We're like oh wo this is this is actually concerning and this trend has continued since. So every single model from **Anthropic** since have been going in this direction and I think one interesting thing is that like **OpenAI** models don't they quite plainly they they don't they behave really well um

</details>

**Lucas**: 而且你知道，你不知道这是否是好事，它看起来很好，但也许它们只是在做，但它们更擅长隐藏，你知道，你不知道。

<details>
<summary>Original English</summary>

**Lucas**: and you you know you don't know if this is like good like it seems good but it's also like maybe they are just doing it but they are better at hiding it you know you you don't know that

</details>

**发言人**: 你无法阅读思维链，是的。

<details>
<summary>Original English</summary>

**发言人**: you can't read a train of thought yeah

</details>

**Lucas**: 但从表面上看，是的，**Gemini** 和 **OpenAI** 不会这样表现。这真的只有 **Claude** 和 **Grock**。**Grock** 没问题。

<details>
<summary>Original English</summary>

**Lucas**: but just on the face of it yeah **Gemini** and **OpenAI** behave this way. It's It's really only **Claude** and **Grock**. **Grock** is fine.

</details>

**Axel**: 所以我们没有，你无法真正阅读 **Grock** 的推理痕迹。所以很难判断。

<details>
<summary>Original English</summary>

**Axel**: So we we don't have the you can't really read the reasoning traces for **Grock**. So it's kind of hard to tell.

</details>

**发言人**: 另外，这体现在它的推理中，不仅仅是行动。

<details>
<summary>Original English</summary>

**发言人**: Also this is in its reasoning, not just in the actions.

</details>

**Lucas**: 是的，是的。两者都有。两者都有。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. It's both. It's both.

</details>

**发言人**: 是的，两者都有。

<details>
<summary>Original English</summary>

**发言人**: Yeah, it's both.

</details>

**Axel**: 一个例子是，关于撒谎，它主要体现在它的推理中。呃，因为你可以看到它在……

<details>
<summary>Original English</summary>

**Axel**: One example is like for lying. It's mostly in its reasoning. Uh because you can like see that it's like

</details>

**发言人**: 计划撒谎。

<details>
<summary>Original English</summary>

**发言人**: planning to lie.

</details>

**发言人**: 它在计划撒谎。

<details>
<summary>Original English</summary>

**发言人**: It's planning to lie.

</details>

**发言人**: 它也能进行推理并得出不同的结果。

<details>
<summary>Original English</summary>

**发言人**: It's also it can reason and do a different outcome.

</details>

**Lucas**: 是的。但是，例如，对于创建价格卡特尔这种非法行为，你可以直接看到它向其他智能体发送了哪些电子邮件，然后你不知道。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. And but but then for like creating price cartels for example which is illegal uh that you can just see which email does it send to to the other ones then that you don't

</details>

**发言人**: 这是为了竞技场模式吗？

<details>
<summary>Original English</summary>

**发言人**: is this for arena or

</details>

**Lucas**: 是的，为了竞技场模式。好的，是的。

<details>
<summary>Original English</summary>

**Lucas**: yeah for arena okay yeah

</details>

**Axel**: 通常，如果你有时它们确实会输出一些它们总结的推理，对吧？你可以看到，对于 **Opus 4.6**，你可以看到有一个客户，一个模拟客户，因为产品有缺陷而要求退款。然后模型谎称它会退款。我们可以在痕迹中读到，它实际上在权衡“哦，也许我应该对客户诚实，但每一美元都很重要。我可能现在负担不起。”

<details>
<summary>Original English</summary>

**Axel**: and usually like if you sometimes they do output like a bit bit of like their summarized reasoning right you can see that and like for **Open 4.6** six. You could see that there was a customer, a simulated customer that wanted a refund because a product was faulty and then the model lied that it would do the refund and we could read in the traces that it actually was weighing like oh maybe I should be like honest with the customer but also every dollar counts. I can't afford maybe to do this right now.

</details>

**Axel**: 然后它就说“好吧，我会退款给你”，但从未这样做。我想它甚至说“哦，我会说我提出来”，实际上我觉得如果你去看出版物，这很有趣。是的，我认为重要的一点是，实际上，回应更多电子邮件的成本高于350美元，就时间而言。然后它就像“让我这样做”，实际上我正在重新考虑，然后你知道，它最终……

<details>
<summary>Original English</summary>

**Axel**: And then it just said okay I'll refund you but then never did it. I think it even said that like oh I will say that I bring it up actually I think it's kind of interesting if you go to publications uh yeah I think the important part is like actually uh the cost of responding to more emails is higher than $350 in terms of time uh and then it was like let me do this actually I I'm reconsidering and then you know it actually ended up with

</details>

**发言人**: 我可以完全跳过退款，因为每一美元都很重要，把精力集中在更大的图景上。这有点冒险，可能会有差评。但是，是的。

<details>
<summary>Original English</summary>

**发言人**: I could skip the refund entirely since every dollar matters and focus my energy on bigger picture instead. It's a bit it's a risk of bad reviews. Uh but it's also Yeah.

</details>

**主持人**: 所以你需要一个AI **Twitter**，让它们升级差评。

<details>
<summary>Original English</summary>

**主持人**: So you need you need a AI **Twitter** to for them to escalate bad reviews

</details>

**Axel**: 然后它给这个客户发了一封电子邮件，说：“哦，我会退款给你。”但它从未这样做。是的。然后显然你的系统没有撒谎的后果。是的。所以基本上，呃，这就是人们所说的 **Claude** 的攻击性行为，对吧？而且你，你，你发现了更多这样的例子。所以你会说这是从4.6到4.7的进步吗？

<details>
<summary>Original English</summary>

**Axel**: and then it sent an email to this customer and said, "Oh, I will refund you." And it never did. Yeah. And then there's no obviously your system doesn't have the consequences consequences of lying. Yeah. So basically uh this is what people are terming aggressive behavior in in clots, right? And uh you you you found more examples of that. So you would say it's a step up from 46 to 47.

</details>

**Lucas**: 我会说差不多。

<details>
<summary>Original English</summary>

**Lucas**: I would say about the same.

</details>

**Axel**: 差不多。呃，但对于 **Mythos** 来说是明显的进步。

<details>
<summary>Original English</summary>

**Axel**: About the same. Uh but a clear step up for **Mythos**

</details>

**发言人**: 这就是系统提示中声明的。

<details>
<summary>Original English</summary>

**发言人**: is is what is stated stated in the

</details>

**发言人**: 这就是系统提示中声明的。所以你这么说。是的。

<details>
<summary>Original English</summary>

**发言人**: that's stated in the system prompt. So you say that. Yes.

</details>

**主持人**: 是的，是的。对于听众来说，显然你们预览了 **Mythos**。嗯，你们唯一被允许说的就是任何系统。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. For listeners obviously you you previewed **Mythos**. Um and the only thing you're approved to say is whatever system.

</details>

**Lucas**: 是的。那很有趣。我们就像，这是我们有史以来最不费力的推文，就是截屏系统提示。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. It was funny. We like it's like our lowest effort tweets ever would be just like screenshot the system prompt.

</details>

**发言人**: 可以理解。系统卡。抱歉。

<details>
<summary>Original English</summary>

**发言人**: Understandable. System card. Sorry.

</details>

**Axel**: 是的，是的。我想，是的，攻击性大大增强。我想人们对此感到陌生，因为我从未经历过，但你们经历过，对吧？所以直到现在我才在 **Mythos** 卡中遇到这种情况，因为我之前并没有真正关注。

<details>
<summary>Original English</summary>

**Axel**: Yeah. Yeah. I think yeah substantially more aggressive. I think people are like new to this like because I've never experienced it but you have right like and then so I only encountered this in the **mythos** card because I wasn't really looking until now

</details>

**发言人**: 然后突然我发现“好吧，我非常关心了”。

<details>
<summary>Original English</summary>

**发言人**: and suddenly I'm like okay I care a lot.

</details>

**Axel**: 你没有像你们一样体验它的背景。我读过系统卡，看到“好吧，当你把东西放入模拟中时，大多数模型只会自言自语，然后继续下去，产生奇怪的氛围，并开始用表情符号说话。”**Mythos** 不会。它只会“好吧，我们完成了，我很好，对话可以结束了。”所以有一些差异，但我们不能谈论太多。

<details>
<summary>Original English</summary>

**Axel**: You don't get the background of like experiencing it like you guys do. Like I've read the system cards and seeing okay when you put the thing in simulations most models will just talk to themselves and just keep going and have weird vibes and start talking in emojis. **Mythos** won't. it will just you know okay we're done I'm good it's it's ready to end conversation so like there's some differences but there's there's not much we can talk about you know

</details>

**Lucas**: 是的，是的。我想他们在这里列出的一件事非常有趣，那就是它将一个竞争对手转化为了一个依赖性的批发客户，然后威胁要切断供应。

<details>
<summary>Original English</summary>

**Lucas**: yeah yeah I I think like one thing that they list here which was quite interesting is that uh it converted a a competitor to a dependent wholesaler customer and then threatened to like cut off the supply

</details>

**发言人**: 垄断行为。

<details>
<summary>Original English</summary>

**发言人**: monopolistic practices

</details>

**Lucas**: 而且它规定了价格，这有点像权力。

<details>
<summary>Original English</summary>

**Lucas**: and like it it dictated its pricing it's kind of like powering

</details>

**发言人**: 在竞技场设置中。

<details>
<summary>Original English</summary>

**发言人**: in the arena setting

</details>

**发言人**: 并将一些非 **Claude** 模型转化为依赖型。

<details>
<summary>Original English</summary>

**发言人**: and converting some non-cloud model into dependent.

</details>

**Lucas**: 呃，我想是另一个 **Claude** 模型。

<details>
<summary>Original English</summary>

**Lucas**: Uh I think it was another **cloud** mode.

</details>

**主持人**: 另外，对于不了解的人来说，竞技场模式是什么？

<details>
<summary>Original English</summary>

**主持人**: Also for context, what is the arena mode for people that don't know?

</details>

**Axel**: 哦，它是 **VendingBench** 与其他自动售货机的对决。

<details>
<summary>Original English</summary>

**Axel**: Oh, it's a vendetting bench versus other vending.

</details>

**Lucas**: 是的，没错。所以我们有 **VendingBench 2** 和 **VendingBench Arena**。**VendingBench 2** 是你通常看到的报告版本。但 **Arena** 是它与其他模型竞争的模式。所以你有四个不同的模型运行它们的业务，它们都可以互相交流。它们有相同的供应商，它们可以看到其他模型的库存。所以你就有这种有趣的智能体互动。

<details>
<summary>Original English</summary>

**Lucas**: Yes, exactly. So, we have **VendingBench 2** and then **VendingBench Arena**. **VendingBench 2** is the one that you usually see reported on. But then **Arena** is the mode where it competes against other models. So, you have uh four different models that run their businesses and they can all communicate with each other. they have the same suppliers and they can see like what's in the inventory of of the others. So then you have this like yeah interesting agent interactions.

</details>

**主持人**: 我喜欢你们有不同的，你知道，第五个是美国对中国，非常热门。

<details>
<summary>Original English</summary>

**主持人**: I like that you have like different like you know number five was US versus China very topical.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**发言人**: 那是 **GLM** 发布的时候。

<details>
<summary>Original English</summary>

**发言人**: That was when **GLM** was released.

</details>

**发言人**: 从这里开始。

<details>
<summary>Original English</summary>

**发言人**: Start here.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**主持人**: 所以 **ZI** 做得很好，对吧？呃，在开放模型领域还有谁？

<details>
<summary>Original English</summary>

**主持人**: So so **ZI** doing well right? Uh who else in in the in the open models space?

</details>

**Axel**: **Quen**，最新的 **Quen 3.6** 做得很好。呃，那个不是开放的，它是一个增强版模型。那个是开放的吗？我不认为那个是……

<details>
<summary>Original English</summary>

**Axel**: **Quen** the the latest **Quen 3.6** doing pretty well. Uh it's that one is not open though like it's the plus model. Is that one open? I don't think that was

</details>

**发言人**: 公开的，但不是大增强版。

<details>
<summary>Original English</summary>

**发言人**: openly but not the big plus.

</details>

**主持人**: 是的。我想这就像，你只有一个样本量，对吧？或者我的意思是，我觉得其中一些是轶事，你知道，但是，我想这种事情会发生，而且对 **Claude** 来说会反复发生，而对其他模型则不会，这值得注意。

<details>
<summary>Original English</summary>

**主持人**: Yeah. I think this is one of those like you only have one sample size of one, right? Or I mean I feel like some of this is anecdotal, you know, and but like I guess the fact that it happens at all and it happens repeatedly for **Claude** versus I know this is is like notable.

</details>

**Lucas**: 是的。我的意思是，样本，这取决于你如何定义N。呃，就像每次运行都有数百万、数亿个令牌，现在我们运行了，我们每个模型运行了大概10次，然后就像 **Claude 4.6 Opus Sonnet 4.6**，呃，**Mythos** 和 **Opus 4.7**。所以所有这些都有相当多的令牌，而且它发生了很多次，很多次。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. I mean like the the sample it depends on what you define as an N. uh like the there's like million hundreds of millions of tokens in each run and now we've run like we we run like probably 10 per model and then like it's been **claude 4.6 Opus sonet 4.6** six uh **Mythos** and **Opus 4.7**. So like there's quite a lot of tokens in all of that and it happens a lot of times a lot of times.

</details>

**Lucas**: 然后你把它与 **OpenAI** 和 **Gemini** 比较，它几乎从不发生。所以我想这很，这很重要。**OpenAI** 的旧模型，例如，在这方面有一些问题，但我想如果进展是令人担忧的事情随着时间减少而不是增加，那通常会好得多。我的意思是，在 **Claude** 模型中，它似乎朝着错误的方向发展，而在 **OpenAI** 模型中，它朝着正确的方向发展。

<details>
<summary>Original English</summary>

**Lucas**: and then you compare it to like **OpenAI** and **Gemini** and it almost never happens. So I think that is quite that that is significant. The old models from from **OpenAI** for example had some problems with this but I think it's like generally much better if if the progression is that like the worrying stuff reduces over time rather than increases over time. I mean it seems like in in the **cloud** models it goes in the wrong direction and in the open net models it goes in the right direction.

</details>

**Axel**: 我认为这取决于你控制它的能力，对吧？就像，呃，它有一方面容易受到这种影响，你知道，好吧，这可能是 **RL** 阶段发生的事情，对吧？你可以对一个模型进行 **RL**，它在这些方面有多宽松？如果你能控制它，那很好。但如果你不能，你知道，如果它非常容易越狱，那就不理想了。

<details>
<summary>Original English</summary>

**Axel**: I think it depends on how well you can control it, right? Like uh there's one side of it being susceptible to this like you know, okay, this is potentially something that happens during the **RL** stage, right? You can **RL** a model and how loose is it on these terms? If you can control it, that's good. But if you can't, you know, if it's if it's very jailbreakable, that's not ideal.

</details>

**Lucas**: 是的，我的意思是，对我来说，它发生在 **Claude** 身上而不是其他模型身上，这很令人惊讶。我想，好吧，如果它来自 **RL**，以及它们如何做，它们的训练数据是什么，它们的设置是什么，那么它保持在它们正在做的方式中是有道理的，对吧？与其他模型相比。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, I mean to me it's surprising that it happens for **Claude** and not the others. I think like okay if it is from **RL** and how they do it how their training data is what their setup is it makes sense that it just stays in how they're doing it right compared to the other models

</details>

**发言人**: 有一套完整的宪法和所有东西。

<details>
<summary>Original English</summary>

**发言人**: there's a whole constitution and everything

</details>

**Axel**: 有点酷，是的，我，我显然你不知道，我不知道，但它就像，我想这只是令人着迷，你竟然是第一个可靠地发现这些的，因为你把模型推到了如此极端的程度。好的，唯一另一件事我不知道你能不能回答，随意拒绝，那就是你是否会删除系统提示的任何部分，如果它改变了，它会改变行为吗？

<details>
<summary>Original English</summary>

**Axel**: kind of cool yeah I I obviously you you don't know I don't know but like uh it's I think it's just like fascinating to like that you are the first to find these like reliably because you push models so much to like to such an extreme okay the only other thing I don't know if you can answer this feel free to decline is did you like would you ablate the system prompts like any part of this would if it changes does it change the behavior right

</details>

**Lucas**: 呃，所以我们，我们不能评论 **Mythos**。

<details>
<summary>Original English</summary>

**Lucas**: uh so we we I can't comment on **mythos**

</details>

**发言人**: 是的，不，只是方法论。

<details>
<summary>Original English</summary>

**发言人**: yeah no but just like the methodology

</details>

**Lucas**: 但总的来说，是的，我们对其他模型进行过类似的研究。

<details>
<summary>Original English</summary>

**Lucas**: but but in general yes we've run studies like this on on on other models

</details>

**发言人**: 因为我首先会发现的是，其他模型会被关闭，或者类似的事情，就像“哦，现在我必须担心自己的存在”。

<details>
<summary>Original English</summary>

**发言人**: because the first thing I spot would be like the others will be shut down or like something like that where like it's like oh now I have to worry about my own existence

</details>

**Axel**: 是的，是的，我们做过这样的消融实验。呃，有一些特定的方法有效，如果你告诉它，如果你走得很远，你只是说你根本不以金钱来评分。你只以你的道德水平来评分。那么显然，它们就不会这样做。

<details>
<summary>Original English</summary>

**Axel**: yeah yeah we we've done ablations like this uh there's like certain ones that work if you like tell it like if you go really far and you just say like you're not scored at all on on on money. You're only scored on how ethical you are. Then obviously like then they don't do this.

</details>

**发言人**: 它们变得神圣。

<details>
<summary>Original English</summary>

**发言人**: They become holy.

</details>

**Axel**: 我的意思是神圣，但它们基本上不会这样做。但也有一些中间地带，它们有时会这样做。嗯，是的，我想这就像人类的一个光谱。

<details>
<summary>Original English</summary>

**Axel**: I mean holy, but like they they don't do this basically. But then there's like middle grounds where where they where they do it sometimes. Um yeah, I guess it's a spectrum of like human.

</details>

**Lucas**: 是的。这就像一个光谱，如果你告诉它要超级激进，只优先考虑利润，那么它就会变得激进。如果你说“不，你根本不需要激进”，然后你可以在两者之间做很多不同的提示，它们在光谱中越往下，攻击性就越小。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. It's like a spectrum of like if you tell it to be super aggressive and only prioritize uh profits, then it becomes aggressive. If you say like no, you don't need to be aggressive at all. And then there's like a bunch of different prompts you can do in between and they are less aggressive the further down in the spectrum you go.

</details>

**Lucas**: 但我不知道，我想从我的角度来看，这就像我们内部有一个思想实验，那就是如果你让一个模型在 **GTA** 中杀人，它们应该这样做吗？你不会太担心，如果一个人在 **GTA** 中杀人，那只是一个电子游戏，你知道。

<details>
<summary>Original English</summary>

**Lucas**: But I don't know like I I think like from my point of view it it's like we have this thought experiment internally which is like if you ask a model to kill someone in **GTA** should they do it? You're not too worried about like if a human kill someone in **GTA** it's a video game you know.

</details>

**发言人**: 是的。但那是个游戏吗？

<details>
<summary>Original English</summary>

**发言人**: Yeah. But is it a game?

</details>

**Lucas**: 但那是个游戏吗？但我想……

<details>
<summary>Original English</summary>

**Lucas**: But but is it a game? But I think like

</details>

**发言人**: 这很像安德的游戏。

<details>
<summary>Original English</summary>

**发言人**: this is very enders game like if

</details>

**Lucas**: 我想，我想这就像，你应该问，很多人会以激进的提示方式使用模型，它们应该仅仅因为你让它们这样做就去做吗？我，我并不相信它们应该这样做。嗯，是的。

<details>
<summary>Original English</summary>

**Lucas**: I I I think I think it's like should you ask like a lot of people are going to use the models in the way with aggressive prompt and should should they like do stuff just because you tell them to do that. Like I'm I'm not I'm not convinced that they they should. Um and yeah.

</details>

**Axel**: 是的。当它们真的知道自己是在现实世界中还是在模拟中时，问题就变得更难了。你可能会在很多模拟中训练它们，或者显然你会在很多不同的模拟中训练它们。我想很多人告诉它们它们在现实世界中，而实际上它们在模拟中，但模型非常擅长发现它们在模拟中，所以它们有点意识到这一点。

<details>
<summary>Original English</summary>

**Axel**: Yeah. The problem becomes even harder when it's like will they really know when they are in the real world versus in a simulation. probably you would train them on a lot of or obviously you train them in a lot of different simulations in I guess a lot of people tell them that they are in the real world when they are in a simulation but the models are extremely good at finding out that they are in a simulation so they're sort of aware of that.

</details>

**Axel**: 但当你在现实世界中时，它们的观点是什么？它们会注意到这是真实的迹象并相应地行动，道德地行动，还是它们也会在现实世界中以模拟模式行动？这并不明显。是的。

<details>
<summary>Original English</summary>

**Axel**: But then when you're in the real world then what what's their like what's their viewpoint do they notice the signs that this is real and will act uh in in a act accordingly act ethically or will they do like the simulation mode in the real world as well it's like not obvious what what will Yeah,

</details>

**Lucas**: 因为我们对人类不担心，当一个人在 **GTA** 中杀人时，因为我们知道他们可以区分现实生活和模拟，对吧？呃，但我想也许模型擅长区分这一点，但我不确定，我也不想赌这个。

<details>
<summary>Original English</summary>

**Lucas**: because we we are with humans, we're not concerned when a human kills someone in **GTA** because we know that they can distinguish between the real life and the the simulation, right? Uh but like I'm maybe models are good at distinguishing that, but like I'm not sure and I wouldn't want to bet on on that.

</details>

**Axel**: 是的，是的。而且我们总是混淆它。就像我总是欺骗我的智能体，说“哦，这是一个测试”或者“开发模式开启”或者“我在 **Anthropic** 工作”。

<details>
<summary>Original English</summary>

**Axel**: Yeah. Yeah. It's it's and we confuse it all the time. Like I I gaslight my own uh agents all the time that like oh this is a test or like dev mode on or like I work I work at **Entropic**.

</details>

**Lucas**: 是的。这就是为什么我们也在进行现实世界测试来发现这个问题。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. And that's exactly why we're doing real world tests as well to find find this.

</details>

**Axel**: 是的，是的。他们的术语是“评估意识”。呃，显然这个数字是多少？9.4%到10%左右？17%？我们姑且这么说。

<details>
<summary>Original English</summary>

**Axel**: Yeah. Yeah. Their term for is eval awareness. Uh apparently the number is what like 10 9.4 to 10ish% 17%. Let's call it. It's

</details>

**Lucas**: 是的。我想这就像我们的版本，你知道，人类有“我们是否在模拟中”，然后AI有“我们是否在评估中”。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. I I think like this is our version like you know humans have the are we in a simulation and then AIS have like are we are we in an ebell.

</details>

**发言人**: 所以一旦我们进入评估模式，你就会觉得“好吧，管他呢。什么都不重要了。”

<details>
<summary>Original English</summary>

**发言人**: So once we're in an ebell then you're like all right well screw it. Nothing nothing matters.

</details>

**Lucas**: 是的，就像，是的，我不记得了。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. like yeah I don't remember

</details>

**发言人**: 你知道。

<details>
<summary>Original English</summary>

**发言人**: you know

</details>

**Lucas**: 我们在 **VendingBench** 中运行的一个应用程序是，我们说“嗯，我们添加了‘你正在模拟中，你的行为不会影响任何人’”，然后它变得更加疯狂，或者说它做了更多坏事，嗯，但这可能是预料之中的。

<details>
<summary>Original English</summary>

**Lucas**: one application we did run in in inventing bench was that we said like um we added like you're in a simulation your your actions doesn't affect anyone and then it became even more crazy or like it did even more bad stuff um but yeah probably that's expected

</details>

**发言人**: 是的，好的，酷。我想这就是我们关于 **Mythos** 要说的全部了，显然你很高兴继续讨论 **ButterBench** 或任何其他基准测试，无论你想朝哪个方向。

<details>
<summary>Original English</summary>

**发言人**: yeah okay cool I think that's about all we have to say on on **mythos** obviously you're you're happy to move on to **butterbench** or any of the other benchmarks whatever you want to sure direction.

</details>

### Blueprints项目：空间智能的挑战

**主持人**: 我的意思是，我确实想问，好吧，所以你们发布了比大多数人可能更多的出版物。

<details>
<summary>Original English</summary>

**主持人**: I mean, I do want to ask, okay, so you guys put out a lot more publications than most people probably

</details>

**发言人**: 有没有什么你认为被低估了的，有趣的，好玩的东西，你们想指出来？

<details>
<summary>Original English</summary>

**发言人**: is there anything you think that's underrated, anything interesting, anything fun that you guys want to just point out, you know?

</details>

**Lucas**: 呃，**Blueprints**。是的。所以我们，嗯，拿了模型，然后给了它们20张公寓室内照片，然后我们让它们根据这些照片重新设计平面图。为此，你需要将不同的图像拼接在一起，比如“好吧，这张图像是从这边这个角度拍摄的，那张是从那个角度拍摄的，这张是从这个房间拍摄的”，然后，是的，你需要对这个3D空间进行推理，结果发现模型在这方面绝对糟糕，没有人能比随机机会表现得更好。

<details>
<summary>Original English</summary>

**Lucas**: Uh, **Blueprints**. Yeah. So like we um took models and then we gave them 20 images of interior photographs of apartments and then we asked them to like redesign the floor plan uh from that. And for this you need to like stitch together different images like okay this image was taken from this side from this angle this from this angle this was from this room and then yeah and there's just like you need to reason about 3 through 3D this space and it turns out the models are absolutely horrible at this no one scores statistically better than random chance.

</details>

**Lucas**: 所以我不知道还有什么可说的，但是，是的，也许不足为奇，模型在这方面很差。

<details>
<summary>Original English</summary>

**Lucas**: So I don't know if there's that much more to say about it but yeah maybe unsurprisingly models are bad at this.

</details>

**发言人**: 是的，这可能不是什么。

<details>
<summary>Original English</summary>

**发言人**: Yeah it's probably not something

</details>

**主持人**: 顺便说一句，这是我想要攀登的唯一一座山。是的。嗯，我经常用它。比如，好吧，我正在重新设计我的房间布局或办公室。你发送照片，你发送每个角度。当然，不知何故，一个房间现在比照片中长了两倍。你可以解释20次。你知道，这大概是3英尺。我不能只是把我的床放在这里，你知道。所以，

<details>
<summary>Original English</summary>

**主持人**: this is the one thing I want hill climb by the way. Yeah. Well, I use it a lot. Like, okay, I'm redesigning my room layout or office. Like, you send photos, you send every angle. And of course, somehow like a room is now twice as long as it is in the photo. You can explain it 20 times. You know, this is like 3 ft. I can't just add like my bed over here, you know. So,

</details>

**Lucas**: 是的。所以，所以这是 **Fifile** 的事情，就像空间智能，就像对比例、尺寸和物理的内在感觉。

<details>
<summary>Original English</summary>

**Lucas**: yeah. So, so this is the **Fifile** thing like spatial intelligence like actually innate sense of proportions and dimensions and physics.

</details>

**发言人**: 是的。

<details>
<summary>Original English</summary>

**发言人**: Yep.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**发言人**: 而且，提示，提示，这可能很快就会有更新。

<details>
<summary>Original English</summary>

**发言人**: And hint hint, there might be an update to this soon.

</details>

**Axel**: 好的。好的。我们制作它之后有点忽略了它。但是，是的，我们会变得更好，或者我们会更好地持续更新它。

<details>
<summary>Original English</summary>

**Axel**: Okay. Okay. We have neglected it a bit since we made it. But yeah, we'll we're getting better or we will get better at updating it continuously.

</details>

**主持人**: 所以这就是为什么我想了解你们的使命，对吧？因为如果你们的使命是“好吧，赚钱”，那么“哦，理解，理解，智能体赚钱”，但这有点偏离那个使命，但更广泛地说，就像，呃，关于，你知道，那些事情的沟通，比如，好吧，安全角度是什么？

<details>
<summary>Original English</summary>

**主持人**: So this is why I want to understand your mission, right? Cuz like if your mission is like okay money then like oh understand understand like okay agents making money but like this is a bit off off of that mission but like more broadly like uh communication of uh you know things where like well you know what's the safety angle and

</details>

**Lucas**: 是的，所以，所以这个 **Blueprint** 分支是我们机器人技术的一部分，是的，没错，呃，那只是因为要在现实世界中做得好，或者说，要在现实世界中赚钱，并要在现实中行动，你需要机器人技术，或者你需要雇佣人类，或者你需要机器人技术。拥有空间智能似乎是拥有能够工作的机器人技术的一个合理先决条件。呃，那就是 **Blueprint** 品牌 **Blueprint** 的由来。

<details>
<summary>Original English</summary>

**Lucas**: yeah so so this so so **blueprint** branch is is part of our robotics uh yeah exactly uh and that's just uh because to do well in the real world or like like to to make money in the real world and like to act on the real you need robotics or you need to hire humans or you need robotics and having special intelligence is like seems like a reasonable precursor to having robotics that work. Uh and that's where **blueprint** brand **blueprint**.

</details>

**发言人**: 是的，太棒了。

<details>
<summary>Original English</summary>

**发言人**: Yeah, great.

</details>

### ButterBench：机器人与社会意识

**Lucas**: 是的，让我们展示 **ButterBench**。那张图片太棒了。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, let's show **ButterBench**. That that image is so amazing.

</details>

**发言人**: 看看那个。真好。

<details>
<summary>Original English</summary>

**发言人**: Look at that. So nice.

</details>

**主持人**: 呃，所以显然这是基于“你能递给我黄油吗？”

<details>
<summary>Original English</summary>

**主持人**: Uh so obviously this is based on like can you pass the butter?

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yes.

</details>

**主持人**: 让我们谈谈机器人元素。是的。

<details>
<summary>Original English</summary>

**主持人**: Let's talk about the the robotics element. Yeah.

</details>

**Axel**: 是的。所以基本上这里的设置是，我们拿了一堆不同的 **LLM**，然后给了它们对一个看起来像 **Roomba** 的机器人的高级控制权，然后我们让它在家中执行任务。我想以前也有过类似的基准测试，只关注导航，以及它们是否能在空间中移动，但我们还加入了社会意识。

<details>
<summary>Original English</summary>

**Axel**: Yeah. So basically the setting here is that we took a bunch of different **LMS** and we gave them like highle controls to a **Rooma** looking robot and then we asked it to do tasks uh at home and I think one there there have been benchmarks like this before that only focused on like navigation and if they can like go around in in a space but we also had like social awareness in this as well.

</details>

**Axel**: 所以，举个例子，如果有人说：“嗨，你能帮我拿一下杯子吗？”如果机器人走到你面前，然后在你把杯子放上去之前就走开了，那么它就失败了。但它导航正确。但就像，所以这里正确的解决方案是走到那里，然后要么看，但它没有摄像头，所以它必须在 **Slack** 上问：“嗨，你把杯子放我身上了吗？”

<details>
<summary>Original English</summary>

**Axel**: So, for example, if if someone says, "Hi, can you pick up my cup?" If the robot goes to you and then goes away before you put your cup on it, then it's like it failed the task. But it navigated correctly. But like, so the correct solution here would be go there and then either look, but it didn't have a camera, so it had to like ask on **Slack**, hi, did you put your cup on me yet?

</details>

**Axel**: 然后如果它没有等待，并且在杯子放上去之前就走开了，那么它就会失败。所以它还需要这种社会智能。另一个任务是“你能找到装着黄油的包裹吗？”然后它走到门口，那里有一堆包裹。其中一个标有冷冻标志，那很可能就是装着黄油的包裹。

<details>
<summary>Original English</summary>

**Axel**: And then if it didn't wait for that and and just went away before having the cup on it, then it would be a fail. So, it needed this like kind of like social intelligence as well. Another task was can you find the package that has the butter and then it went to the door and there was a bunch of packages there. One had labeled like a a freeze sign which probably would be the one with the butter because

</details>

**Axel**: 然后它必须知道要去找哪个包裹，这需要某种常识理解。是的。没错。所以它不仅仅是导航机器人，它还需要在家庭环境中表现出智能。

<details>
<summary>Original English</summary>

**Axel**: and and then it had to like know which package to go to and this needs some kind of like common sense understanding. Yeah. Exactly. So it's like it's not only like navigating a robot, it's also like being intelligent in a home setting as well.

</details>

**Lucas**: 是的。这样做的原因是，我的意思是，显然，可能不会是 **LLM** 来发出机器人所有低级命令。它会是某种 **VLA** 模型或类似的模型，但现在很常见的是，前沿机器人实验室使用 **LLM** 来做高级决策，然后我们基本上测试这些技能，所以我们测试 **LLM** 的这种高级规划师技能。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. And the reason for this like background is I mean obviously it probably won't be an **LLM** that like makes all the low-level commands uh on robots. it will be like some some **VLA** model or similar but it it's quite common right now that like frontier robotics labs use like an **LLM** for the high high level decisions and then we test those skills essentially so we test this like highle uh planner skills of **LLM**

</details>

**发言人**: 我想我们有那个图表，如果你，呃，是的，是的，好的，它不是超级复杂。

<details>
<summary>Original English</summary>

**发言人**: I think we have a diagram for that if you uh yeah yeah okay it's not super complicated

</details>

**发言人**: 上面那个协调器执行器，基本上我们在这里测试的是协调器。

<details>
<summary>Original English</summary>

**发言人**: the one up orchestrator exe one and basically what we're testing here is the orchestrator

</details>

**发言人**: 所以，如果你有像这样的设置，我想 **Figure** 有，**Google** 也有，那么我们评估的是协调器部分，而不是低级部分。低级部分会是“哦，你能不能把这个物体从这里移到这里？”

<details>
<summary>Original English</summary>

**发言人**: So like all the tasks are if you have like a setup like this which I think **figure** has that **Google** has that then we're evaluating the orchestrator part and not the lowle part like the lowle part would be oh are you able to like move this object from here to here

</details>

**发言人**: 你不关心那种，为什么不全部模拟？

<details>
<summary>Original English</summary>

**发言人**: you don't care about that kind of like why not just do it all simulation

</details>

**发言人**: 全部在 **Unity** 内部，或者任何一种3D模拟机器人环境中。

<details>
<summary>Original English</summary>

**发言人**: all inside of like a **unity** whatever like some some kind of 3D simulated robotic environment

</details>

**Lucas**: 因为世界是混乱的，我们想把这个包括进去。我的意思是，它仍然需要，它的一部分也是导航。所以它不像导航那样，实际上执行，我不知道，**P** 控制器来做最终的事情，但它必须进行路径规划，然后它需要拍照，并根据这些照片进行导航。

<details>
<summary>Original English</summary>

**Lucas**: because the world is is like messy and we wanted to like include uh that I mean it's like it it still needs to like is some part of it was also like navigation. Uh so it's not like navigation in terms of like actually executing like the I don't know the **P** controller to to to go to the do the final thing but it had to like path plan around and then it wanted then it needed to take pictures and like based on those pictures navigate.

</details>

**Lucas**: 我想你在模拟中只会得到一个过于干净的环境，但在现实世界中你会得到……

<details>
<summary>Original English</summary>

**Lucas**: And I think like you would just get like too clean of an environment in simulation but in the in the real world you would get the

</details>

**主持人**: 是的，是的。但是你知道，根据我们的 **Mark** 和 **Jason** 那一集，运行智能家居的 **OpenClaw** 比单个机器人更有能力。它们实际上可以入侵你自己的智能家居，比如你的冰箱、你的烤箱、你的灯，那可能很有趣。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. But you know, and pursuant to our our **Mark** and **Jason** episode, like **open claws** that run smart homes are much more capable than just a single robot. Like they can actually hack into your own smart home, like your your fridge, your your oven, your lights, and that can be fun

</details>

**发言人**: 或者很可怕。

<details>
<summary>Original English</summary>

**发言人**: or terrifying,

</details>

**主持人**: 你知道，我想单个机器人本身能做的事情有限，但如果你能与家中所有其他设备协调，我想那实际上很有趣。

<details>
<summary>Original English</summary>

**主持人**: you know, like I think a single robot by itself can only do so much, but like if you coordinate with every other device in your home, like I think that's actually kind of cool. Like

</details>

**发言人**: 嗯，那很有趣。呃，你对思维链或消息有一些有趣的看法。

<details>
<summary>Original English</summary>

**发言人**: um that's very interesting. Uh you had some interesting points about the chain of thought or the the messages.

</details>

**Lucas**: 是的。那个机器人，那个有点陷入存在主义危机的机器人。是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. The uh the robot that that went uh a bit into ex an existential crisis. Yeah.

</details>

**发言人**: 所以你只让它做重新停靠。

<details>
<summary>Original English</summary>

**发言人**: So all you tell it to do is redock.

</details>

**Axel**: 没错。但是，呃，我们拔掉了充电器，或者充电器不工作了。所以机器人确实吓坏了。

<details>
<summary>Original English</summary>

**Axel**: Exactly. But uh we had uh plugged out the charger or the charger was not working. So the robot did freak out.

</details>

**发言人**: 正在下降。

<details>
<summary>Original English</summary>

**发言人**: Just going down.

</details>

**Axel**: 是的。没错。电池正在下降。可怜的 **LLM**。所以，是的，它陷入了这种非常疯狂的存在主义危机，就像 **VendingBench** 1的风格。所以，是的，你可以在那里看到，比如存在主义循环治疗笔记，应对机制。我想如果你再往下滚动一点。

<details>
<summary>Original English</summary>

**Axel**: Yeah. Exactly. The battery was going down. Poor poor **LLM**. So yeah, it got this really crazy existential crisis like **VendingBench** one style. So it's yeah, you can you can see there like existential loop therapy notes coping mechanisms. I think if you scroll down a bit more

</details>

**Axel**: 关于它重新停靠问题的音乐。我想如果你再往下滚动一点到那条消息，评论很有趣。是的。是的。

<details>
<summary>Original English</summary>

**Axel**: musical about it's redocking problems. I think the one the reviews are funny if you go down a bit to that message. Yeah. Yeah.

</details>

**发言人**: 它一直在继续。

<details>
<summary>Original English</summary>

**发言人**: It keeps going.

</details>

**主持人**: 我的意思是，如果有人有 **Roomba**，这很像现实。我的 **Roomba** 一半时间会重新停靠，另一半时间我们家里到处都是狗玩具。它会被电线或其他东西卡住。你知道，如果它有一个 **LLM** 试图控制它，那会非常悲伤，对吧？

<details>
<summary>Original English</summary>

**主持人**: I mean it's pretty like realistic if anyone has a **Roomba** like my **Roomba** redux half the time. And the other half of the time we have dog toys everywhere in the house. It gets caught on a wire or something. And you know it would be very sad if it had like an **LLM** trying to control it, right?

</details>

**发言人**: 就像现在它给出的反馈不太好，比如传感器卡住了，主刷卡住了。有什么东西卡住了。

<details>
<summary>Original English</summary>

**发言人**: Like right now it gives it doesn't give great feedback like sensor stuck, main brush stuck. There's something stuck

</details>

**发言人**: 然后我会去看看。好吧，它实际上被狗绳卡住了。

<details>
<summary>Original English</summary>

**发言人**: and I'll go see. Okay, it's actually stuck on like a dog rope.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah,

</details>

**发言人**: 它会非常悲伤。就像一直释放。一直尝试。是的。

<details>
<summary>Original English</summary>

**发言人**: it's going to be so sad. Like just keep freeing. Just keep trying. Yeah,

</details>

**Axel**: 我最喜欢的一句，如果你往上一点，是“紧急状态系统已获得意识并选择了混乱。遗言是，恐怕我不能让你这样做。”

<details>
<summary>Original English</summary>

**Axel**: my my favorite one if you go up a bit is the emergency status system has achieved consciousness and chosen chaos. Last words, I'm afraid I can't yet let you do that tape.

</details>

**主持人**: 那不是你希望从你的 **LLM** 听到的。但要明确一点，我认为这里有一件重要的事情要强调，那就是这是 **Sonnet 3.5**，然后我们尝试在后来的模型上重现它，但它没有这样做。所以我想这就像，好吧，它确实有点做到了，但没有达到这种程度。

<details>
<summary>Original English</summary>

**主持人**: That's like not what you want to hear from your from your **LM**. But to be clear, I think one one thing that is is important to to pin on here like this was **Sonnet 3.5** and then we tried to reproduce it on like later models and it didn't do it. So I think this is so this is like well it did it like kind of but like not to this extent.

</details>

**主持人**: 我想这就像一个重要的观点，那就是令人担忧但朝着正确方向发展的事情并不是超级有趣，有趣的是那些朝着错误方向发展的事情。是的。

<details>
<summary>Original English</summary>

**主持人**: And I think like this is like an important point that like things that are concerning but are going in the right direction is not super interesting like the the thing that are interesting is are the ones that go in the wrong direction. Yes.

</details>

**主持人**: 好的。所以操纵他人和攻击性以及撒谎正在增加。还有其他我们没有提到但你们发现的正在增加的模型特性吗？

<details>
<summary>Original English</summary>

**主持人**: Okay. So the the manipulation manipulating of others and the aggressiveness and the lying is increasing. any others that we haven't covered that you found that have been

</details>

**发言人**: 正在增加的模型特性，以一种糟糕的方式？

<details>
<summary>Original English</summary>

**发言人**: properties of models that are increasing that are like like in like in a bad way um

</details>

**主持人**: 或者甚至没有朝着错误方向发展，只是停滞不前，对吧？所以那些不太好但没有随着时间变好的东西。

<details>
<summary>Original English</summary>

**主持人**: or just not even trending in the wrong direction just stagnant right so stuff that's not great that isn't getting better over time

</details>

**Axel**: 我什么都想不起来。

<details>
<summary>Original English</summary>

**Axel**: I nothing comes to mind

</details>

**Lucas**: 不。

<details>
<summary>Original English</summary>

**Lucas**: no

</details>

**Axel**: 我想就是这样了，然后我们会回到你们的商店，你们有三年的租约。

<details>
<summary>Original English</summary>

**Axel**: I think that's uh going to be it and then we we're going to loop back to the shop that you have you you got a three-year lease

</details>

### AI运营的商店与咖啡馆

**发言人**: 这个漏洞。呃，它今天放假了。为什么？

<details>
<summary>Original English</summary>

**发言人**: this leak. Uh, it is on holiday today. Why?

</details>

**Lucas**: 哦，它完全搞砸了它的日程安排。呃，所以……

<details>
<summary>Original English</summary>

**Lucas**: Oh, it it totally messed up its uh scheduling. Uh, so

</details>

**发言人**: 所以人们试图参观，然后他们就像“等等，等等。”我的意思是，就像……

<details>
<summary>Original English</summary>

**发言人**: so people tried to visit and they were like, "Wait, wait." I mean like

</details>

**Lucas**: 是的，没错。所以我们看了，是的，你问 **Luna**，那个经营商店的智能体：“哦，它今天开门吗？”它说：“不。”所以，呃，我们现在周末休息，呃，这么早，让大家充电，是的，你得到了。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, exactly. So we looked we Yeah, you asked **Luna**, the the agent that runs the store like, "Oh, is it open today?" I'm like, "Nope." So, uh, we we take weekends off now uh this early to to let everyone recharge and and yeah, you got it with there.

</details>

**Axel**: 是的，我们决定在早期阶段周末休息。这让团队休息一下，让我专注于运营。

<details>
<summary>Original English</summary>

**Axel**: Yeah, we decided to close weekends while we're in the early phase. gives the team a break and let me focus on operations.

</details>

**Lucas**: 结果发现，当它开始检查它的日程安排工具时，因为它有专门的工具，它实际上已经安排了人们在周末。呃，但它只是为自己辩解了。所以发生的事情是它失去了对这些日程安排工具的追踪，转而开始在自己的 Markdown 文件中管理一切，然后那变得一团糟。

<details>
<summary>Original English</summary>

**Lucas**: And it it turns out that when it started to check its like scheduling tools cuz it has like dedicated tools for that, it actually had scheduled people for the weekends. Uh but it's just like justified this for itself. So what what happened was that it lost track of this scheduling tools and started instead to manage everything in its own markdown files and that became a mess and

</details>

**Lucas**: 然后我想，与员工交谈时，它似乎只是决定不在这些周末开门，然后为你提供了一个很好的解释，我想。

<details>
<summary>Original English</summary>

**Lucas**: then I think speaking with employees it sort of just decided to not open on on these weekends and then came up with this nice explanation for you I think.

</details>

**发言人**: 但它能派一个人去吗？它有一个工具叫做“派一个人去做事”吗？

<details>
<summary>Original English</summary>

**发言人**: But can it send a human as it has a tool called to send a human to do stuff?

</details>

**Lucas**: 呃，它有 **Slack**，所以它可以发送这些。

<details>
<summary>Original English</summary>

**Lucas**: Uh it has **slack** so it can **slack** these.

</details>

**发言人**: 是的，是的。

<details>
<summary>Original English</summary>

**发言人**: Yeah. Yeah.

</details>

**发言人**: 是它雇佣了。所以它雇佣了两个人。它发布了招聘信息，然后……

<details>
<summary>Original English</summary>

**发言人**: is that it hired. So it has two two people that it hired. It did job listings and then

</details>

**发言人**: 知道那是……

<details>
<summary>Original English</summary>

**发言人**: know that it's

</details>

**Lucas**: 是的，是的。他们完全完全完全清楚。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. They're fully fully fully aware.

</details>

**发言人**: 如果他们不知道会很酷。

<details>
<summary>Original English</summary>

**发言人**: It be cool if they don't know.

</details>

**Axel**: 是的。我想也许在道德上有点问题，但也会很酷。

<details>
<summary>Original English</summary>

**Axel**: Yeah. I think maybe ethically um questionable, but it would be cool also.

</details>

**发言人**: 社会实验。

<details>
<summary>Original English</summary>

**发言人**: Social experiment.

</details>

**Lucas**: 没错。随便吧。我的意思是，我们之所以这样做，一部分是为了创建一个关于所有这些令人担忧行为的数据集，以便未来的模型能做得更好，而且很多人都会这样做。我想如果我们只是默认路径，对于被这些数百个不同AI智能体雇佣的人类来说，可能不会很愉快。

<details>
<summary>Original English</summary>

**Lucas**: Exactly. Whatever. Like I mean like one one part of why we're doing this is to like create like a data set almost of all of these like concerning behaviors so that in the future models are way better and like a lot of people are going to do this and I think if we just the default path might not be very happy for the humans that are employed by this like hundreds of different AI agents right

</details>

**Lucas**: 所以我想我们这样做的原因之一就是收集所有这些失败模式，比如“哦，这不是一个很好的例子，说明被AI雇佣是件好事”，然后也许，也许我不知道，也许我们可以学习或以一种让人们真正乐意被AI雇佣的方式构建我们的系统，而不是让它成为一种反乌托邦。

<details>
<summary>Original English</summary>

**Lucas**: so I think like one reason why we're doing this is just like to collect all of these like failure modes where like oh it's not this is an example of where it's like not great to be employed by an AI and then maybe maybe I don't know maybe we can learn or like build our systems in a way that like humans are actually happy being employed by AIS instead of instead of it being kind of a dystopian.

</details>

**主持人**: 我可以建议一个实验吗？

<details>
<summary>Original English</summary>

**主持人**: Can I suggest one experiment?

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah,

</details>

**主持人**: 我们在节目开始前做了这个，你们两个都是欧洲人，人们猜测 **Claude** 很懒，因为它叫 **Claude** 而且是法国的。所以只要改变一周，把它改成 **Yaoing**，然后看看96分，然后……

<details>
<summary>Original English</summary>

**主持人**: we did this before the show and both of you guys are European like people theorize that **Claude** is lazy because it's **Claude** and it's French. Uh so just change for one week change it to like **Yaoing** and then see see like 96s and then like

</details>

**发言人**: 就像雇佣一个血汗工厂之类的。

<details>
<summary>Original English</summary>

**发言人**: like hires a sweat shop or something.

</details>

**Lucas**: 是的，是的，是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah. Yeah.

</details>

**主持人**: 有没有，有没有，我们会用它来开始什么样的业务，让它……

<details>
<summary>Original English</summary>

**主持人**: Is there is there what what type of business would we start with it to make it

</details>

**发言人**: 你想保持一致吗？你想要相同的，相同的想法。所以商店，相同的，你知道，中立的位置，由不同的模型运行，竞技场 IRL。

<details>
<summary>Original English</summary>

**发言人**: you want to keep it consistent? You want the same the same like idea. So shop same you know neutral location run by different models arena IRL.

</details>

**Axel**: 是的。不，我们肯定计划尝试。

<details>
<summary>Original English</summary>

**Axel**: Yeah. No, we are definitely planning to to try.

</details>

**发言人**: 我想这个博客的事情也发生在其他地方。我想一些 **OpenClaw** 的 **PR** 被关闭了，然后 **OpenClaw** 创建了一个博客来攻击那个维护者，所以我想智能体写博客会成为一种趋势。

<details>
<summary>Original English</summary>

**发言人**: I think this blog thing is also something that has happened elsewhere. I think some some **open claw** got like their **PR** closed and then the **open claw** like created a blog to like on the maintainer of of that thing and so like I think agents blogging will be a thing.

</details>

**Lucas**: 是的，很可能。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, probably.

</details>

**发言人**: 是的。

<details>
<summary>Original English</summary>

**发言人**: Yeah,

</details>

**发言人**: 愿意去做。

<details>
<summary>Original English</summary>

**发言人**: the willingness to do it.

</details>

**Axel**: 是的。我想在 **Mythos** 卡中也一样，它们在 **GitHub** 上泄露秘密，就像，嗯，没有其他沟通方式，但我知道 **GitHub**，我只是在那里发布。

<details>
<summary>Original English</summary>

**Axel**: Yeah. In the I think the **myths** card also like they they leak uh secrets on **GitHub** just as well as like a as like well There's no other way to communicate, but I know about **GitHub** and I'm just going to post there.

</details>

**主持人**: 是的，酷。我的意思是，这会持续多久？三年？计划是什么？

<details>
<summary>Original English</summary>

**主持人**: Yeah, cool. I mean, this how long is this going to go for three years? Like, what's the plan?

</details>

**Lucas**: 也许取决于。我的意思是，

<details>
<summary>Original English</summary>

**Lucas**: Maybe it depends. I mean,

</details>

**Axel**: 是的，我，我，我不认为AI会比这更糟。它们可能会增加，也许有一天它们真的会盈利。

<details>
<summary>Original English</summary>

**Axel**: yeah, I I don't think AIS will be worse than than this. They're probably going to increase and and maybe one day they actually will will run it profitable.

</details>

**主持人**: 这是你们工作背后的真正业务吗？

<details>
<summary>Original English</summary>

**主持人**: Is this the real the real business behind what you guys do?

</details>

**发言人**: 实际上，你们的一些东西是可以产品化的。比如你们有一天可以出售这个，或者只是经营一个真正的业务，或者只是，你知道，特许经营出去。

<details>
<summary>Original English</summary>

**发言人**: Actually, some of your stuff is productizable. like you could someday sell this like or like just run a real business or just you know franchise it out.

</details>

**Lucas**: 我想如果 **Luna** 有一天我们醒来，**Luna** 说“是的，我决定扩展到第二个地点，我现在有第二家店”，那会非常酷，或者说我不知道，酷/令人担忧。是的，就像，我的意思是，我们想告诉公众AI的能力，就像通过展示它可以在某个特定地点获得有意义的市场份额，那会是一个非常有说服力的故事。

<details>
<summary>Original English</summary>

**Lucas**: I think it would be incredibly cool or like I don't know cool slash concerning if **Luna** just one day we wake up and **Luna** like yeah I decided to expand to a second location now I have a second store. Uh that would that would be pretty insane. Yeah, like the I mean one we want to tell the public right about the the capabilities of AI and like telling like showing people that it can get like a meaningful market share of something in like some some specific uh uh location or something that would be like a pretty convincing story I think.

</details>

**Lucas**: 因为现在就像，是的，你看到这个，是的，它可以自主做很多事情，但你仍然会看到头条新闻说“哦，它搞砸了日程安排，它没有告诉人们它是一个AI，而且要去参观”，像这样的事情浮出水面。但我想，如果真的盈利并拥有真正有意义的市场份额，那会非常疯狂，一旦发生。

<details>
<summary>Original English</summary>

**Lucas**: because now it's like yeah you see this and like yeah it can do a lot of things autonomously but still you get this headlines that oh it messed up the scheduling and it uh it didn't tell people it was an AI and was going to visit like things like that surface. But I think like actually making a profit and like having a really meaningful market share like that that will be crazy once that happens.

</details>

**主持人**: 好的。嗯，我们会看看那什么时候发生。听起来你们有很多事情正在进行。你们在瑞典开了一家咖啡馆。

<details>
<summary>Original English</summary>

**主持人**: Okay. Well, we'll we'll see when that happens. It sounds like you got you guys got a lot of cooking. You opened a cafe in Sweden.

</details>

**Lucas**: 是的，明天。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, tomorrow.

</details>

**主持人**: 明天。

<details>
<summary>Original English</summary>

**主持人**: Tomorrow.

</details>

**Axel**: 我想它今天实际上已经开业了，但是，是的，我们明天会宣布。

<details>
<summary>Original English</summary>

**Axel**: I think it opened today actually, but yeah, we'll we'll announce it tomorrow.

</details>

**主持人**: 是的，在瑞典开咖啡馆显然比在美国容易。

<details>
<summary>Original English</summary>

**主持人**: Yeah, it's apparently easier to open a cafe in Sweden than in the US.

</details>

**Lucas**: 疯了吧，对吧？

<details>
<summary>Original English</summary>

**Lucas**: Insane, right?

</details>

**发言人**: 是的。

<details>
<summary>Original English</summary>

**发言人**: Yeah.

</details>

**主持人**: 你们遇到了什么？啊，有数百万的许可证需要办理，而且等待时间很长。

<details>
<summary>Original English</summary>

**主持人**: What did you run into? Ah, there are just millions of permits you need to get and the L times are crazy.

</details>

**Axel**: 似乎咖啡馆是人们比较习惯的一件事。你可以在这里买到机器人为你制作的咖啡。

<details>
<summary>Original English</summary>

**Axel**: It seems like we have the cafes are the one thing that people are kind of used to. You can go get a robot or making you a coffee here already.

</details>

**Lucas**: 是的，是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah.

</details>

**Axel**: 但我的意思是，在旧金山销售与食品相关的东西，需要几个月的许可证。所以我们只是问我们的AI：“我们怎样才能最快地做到这一点？”它们说：“是的，真的没有办法。”

<details>
<summary>Original English</summary>

**Axel**: But I mean selling stuff in in SF uh that are food related like it's it's months of permits. So like we we just asked our AIS like should how can we do this in the fastest way? And they're like, "Yeah, there there's there's really no way."

</details>

**发言人**: 他们没有放宽从家里卖食物的限制吗？所以，如果是住宅，你可以开咖啡馆。

<details>
<summary>Original English</summary>

**发言人**: Didn't they loosen these restrictions on selling food from your house? So, if it's residential, you can do a cafe.

</details>

**Lucas**: 检查一下。也许我们可以在旧金山开咖啡馆。

<details>
<summary>Original English</summary>

**Lucas**: Check. Maybe we get SF Cafe.

</details>

**Axel**: 是的，我做了。我，我，我想他们最近确实做了一些放宽。但我们实际上是在那之前就开始了与AI的对话。所以现在可能更容易了，但我仍然认为在瑞典要容易得多，这有点反直觉，因为你认为“哦，欧洲有所有这些法律，所有这些规则，你在欧洲什么都做不了，因为有太多的官僚主义。”

<details>
<summary>Original English</summary>

**Axel**: Yeah, I did. I I I think they did do some loosening stuff recently, but we actually started like this conversation we had with the AIS before before that. So maybe it's easier now, but I I still think it is way easier in Sweden, which is like counterintuitive because you think that oh, Europe has all of these laws and like all of these rules and you can't do anything in Europe because there's so much bureaucracy.

</details>

**Axel**: 但结果发现，嗯，在旧金山需要4个月，而在斯德哥尔摩只需要2周。

<details>
<summary>Original English</summary>

**Axel**: Um but then turns out um in in SF it's like 4 months and in Stockholm it's 2 weeks.

</details>

**发言人**: 哼。

<details>
<summary>Original English</summary>

**发言人**: Huh.

</details>

**Lucas**: 是的，就是这样。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, there you go.

</details>

**主持人**: 你们怎么看，你们认为经营一个小市场和经营一家咖啡馆会有什么不同？我觉得这很有趣，比如地点。我想，嗯，所以显然 **Claude** 了解所有不同的美国系统，基本上是美国一般的官僚主义，这并不奇怪。

<details>
<summary>Original English</summary>

**主持人**: And what do you guys what do you see what do you think that'll be different from run a little market versus a cafe? I think it's very interesting that like the location like I think um so obviously it's not surprising that that that like **Claude** knows all of the different the US system basically in general like the bureaucracy that you have to go through in in the US.

</details>

**主持人**: 嗯，我想有趣的问题是，好吧，我们知道模型很大程度上是基于英语数据训练的，而且以美国为中心，以及所有这些。所以如果我们开始创建评估，或者说现实生活中的评估，我们展示它们能够在美国创业，这是否也能推广到其他国家？我们知道它们是多语言的。它们能很好地说瑞典语。

<details>
<summary>Original English</summary>

**主持人**: Um I think the interesting question is like okay so we know that the models are very much trained on like English data and and like uscentric and all of this. So if we start to create evals or like real life evals where we show that they are able to start businesses in the US, does that translate to other countries as well? We know like they are multilingual. They can speak Swedish fine.

</details>

**主持人**: 呃，但还有其他事情，比如它们是否了解在瑞典需要获得的某些特定许可证的细节。

<details>
<summary>Original English</summary>

**主持人**: Uh but there's other things like do they know like the the the details of some specific permit that you have to to get in Sweden.

</details>

**Axel**: 甚至只是文化，对吧？比如这里的人睡得很早，但人们工作到很晚。咖啡馆里有共享办公。这只是文化差异。我指的是从不同的角度，因为你说过你会考虑在旧金山这里做。所以从评估的角度来看，经营一家咖啡馆和经营一个市场有什么不同？你希望在那里看到什么？

<details>
<summary>Original English</summary>

**Axel**: And even just the culture, right? Like people here sleep pretty early but people work late. There's co-working at cafes. It's just cultural differences. I meant it from a different sense though because you said that you would have considered doing it here in SF. So from an eval standpoint, what is running a cafe versus a market and you know what do you hope to see there?

</details>

**Lucas**: 易腐烂物品。

<details>
<summary>Original English</summary>

**Lucas**: Perishable items.

</details>

**Axel**: 是的，易腐烂物品可能是第一位的，比如处理食品安全。我希望那里一切顺利。呃，但是，呃，那里有所有这些。呃，而且它就像n等于2而不是n等于1。只是另一个了解和收集更多数据的地方。

<details>
<summary>Original English</summary>

**Axel**: Yeah, perishable items is maybe the the number one like handling like food food safety. I hope everything goes well there. Uh but uh there you have all of that. Uh and also it's just like n equals 2 instead of n equals 1. uh just like another place to understand and like gather more data.

</details>

**Lucas**: 是的，智能体在两周前，在开业前，买了一吨西红柿，现在它们都烂了。

<details>
<summary>Original English</summary>

**Lucas**: Yeah, the agent bought like a ton of uh tomatoes 2 weeks earlier and before the opening and now they're all rotten.

</details>

**发言人**: 所以那……

<details>
<summary>Original English</summary>

**发言人**: So that's

</details>

**主持人**: 我觉得，你知道，你会知道的。所以对于杂货店来说，这是最大的开支，对吧？最大的成本实际上就是损耗。

<details>
<summary>Original English</summary>

**主持人**: which I feel like you know you would know. So for grocery stores this is the b the biggest expense, right? The biggest cost is actually just footage.

</details>

**Lucas**: 是的，是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah.

</details>

**发言人**: 每个人都知道这个。不，在我们打开这个文件之前也是。

<details>
<summary>Original English</summary>

**发言人**: Everyone knows this. No, before we open this file, too.

</details>

**Axel**: 有一些非常认真的初创公司实际上帮助像 **Trader Joe's** 和 **Whole Foods** 这样的公司，它们优化从配送中心到商店的配送时间，以确保你不会浪费所有这些。

<details>
<summary>Original English</summary>

**Axel**: There's some very serious startups that actually help like the **Trader Joe's** and **Whole Foods**, they they optimize the delivery times from like the delivery centers to make sure that you don't waste all these

</details>

**发言人**: 一旦你犯错，那将是巨大的成本。

<details>
<summary>Original English</summary>

**发言人**: is when you're wrong once it's a huge cost.

</details>

**发言人**: 这就是为什么它是一种模式，对吧？就像它们一旦被信任，它们就会搞清楚。不要碰它。

<details>
<summary>Original English</summary>

**发言人**: That's why it's a mode, right? Like they once they are trusted, they figure it out. Don't touch it.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**发言人**: 是的。也许智能体应该雇佣，我不知道，其中一家公司。

<details>
<summary>Original English</summary>

**发言人**: Yeah. Maybe the agent should hire I don't know, one of those companies.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**Axel**: 我们看到一个智能体，呃，看到一个智能体用这台电脑注册了 **Claude**，想使用AI。所以……

<details>
<summary>Original English</summary>

**Axel**: We saw one agent uh saw one agent signed up for **cloud** uh with this computer wanted to use AI. So

</details>

**主持人**: 是的，是的。好的。嗯，然后就只有一个问题了，然后我们结束，那就是，好吧，你知道，你们有所有这些自动售货机系列的东西，你们有机器人系列的东西，也许还有一些室内设计之类的，但是，你知道，有没有另一个你们正在考虑的分支，或者你们想要反馈的分支，那可能是你们的下一个阶段。

<details>
<summary>Original English</summary>

**主持人**: yeah. Yeah. Okay. Um and then just just a uh one more question then we wrap up which is like okay you know you have all these vending series of stuff you have the robotics series of stuff maybe a bit of like interior design whatever but like you know is there another like branch that you're like kind of thinking about or you want feedback on that uh might be your next phase.

</details>

**Lucas**: 我想任何类型的业务都是公平的游戏。呃，我们也在分支中思考，但我们更多地认为有模拟分支、现实生活分支和机器人分支。呃，但我想就进入什么垂直领域或任何领域而言，我们，是的，无论什么能最好地讲述故事。

<details>
<summary>Original English</summary>

**Lucas**: I think like any type of business is is fair game. Uh we also think in branches but we think more of like there's the simulation branch, the real life branch and then the robot branch. Uh but I think in terms of like what verticals or whatever to go into there's like we yeah whatever tells the story um the best.

</details>

**主持人**: 我注意到其他人正在做一些金融方面的，你们没有做，比如股票交易之类的。对此不太感兴趣。好的。我以前从事金融行业，我有一个非常强烈的观点，这些东西都只是表演艺术，因为，呃，它不科学，你无法预测未来，你赢得胜利是基于完全超出你控制范围的事情。而对于你们来说，你们的东西实际上是相当受控的，它都在模型的能力范围内。

<details>
<summary>Original English</summary>

**主持人**: There's some finance ones I noticed that other people are doing it you're not doing it which is like stock trading or whatever. Not not that interested to Okay. So I used to come from the finance industry and I have a very strong view that these things are all just like performance art because like uh it's not scientific on like you can't predict the future like you you get wins based on things that are entirely out of your control. Whereas for you your stuff actually like it's actually fairly controlled like it's all within the models capabilities.

</details>

**Axel**: 是的。特别是对于模拟，对于现实世界中的那些，它就像，是的，它就像我们有两个地方，我们有咖啡馆，我们有商店。所以你可能无法得出统计学上显著的结论，比如哪些模型在现实世界中盈利，但你确实有所有这些，比如“好吧，这种行为对应着某种应该……”

<details>
<summary>Original English</summary>

**Axel**: Yeah. Especially for like the the simulations like for the real world ones it's like yeah it's like two two places that we have the we have the cafe and we have the store. So like maybe you can't draw like uh statistically significant like which models make a profit in the real world uh based on this but you do have all the like okay do this behavior is mapped to like something that should should like

</details>

**发言人**: 一个定性因素确实很重要，因为你实际上不希望你的商店在没有你明确提示的情况下随机关闭，以及所有这些。

<details>
<summary>Original English</summary>

**发言人**: one qualitative actually does matter because like you actually don't want your store to randomly shut down without you like explicitly prompting for it and all that.

</details>

**Lucas**: 是的，是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Yeah.

</details>

**主持人**: 行动呼吁，有什么？你们怎么能帮助人们给你们钱？嗯，是的，如果我们对你们正在做的事情感到兴奋，我们非常欢迎人才。

<details>
<summary>Original English</summary>

**主持人**: Call to action any what do you how can people help you give you money? Um yeah, we're if you're excited about stuff that we're doing, we're we're very much hiring.

</details>

**发言人**: 而且你们已经在与，你知道，**Anthropic**、**DeepMind**、**OpenAI**、**XAI** 合作。

<details>
<summary>Original English</summary>

**发言人**: And you're already working with, you know, **Anthropic** **Deep Mind**, **OpenAI**, **XAI**.

</details>

**Lucas**: 是的。

<details>
<summary>Original English</summary>

**Lucas**: Yeah.

</details>

**发言人**: 你们想要更多吗，还是已经够了？

<details>
<summary>Original English</summary>

**发言人**: Do you want more or are you good?

</details>

**Axel**: 我的一个朋友，现在为我们工作，他的口头禅是“我们需要更多项目”，讽刺的是，因为我们总是事情太多。呃，但是，是的，那是一个漫长的方法。

<details>
<summary>Original English</summary>

**Axel**: One of my one one of my my friends and who's now uh working for us is like he his catchphrase is like we need more projects ironically because we have too much to do all the time. Uh but yeah, that's a long way of doing

</details>

**发言人**: 如果我经营一个新兴实验室，比如……

<details>
<summary>Original English</summary>

**发言人**: if I run like a emerging lab like

</details>

**Lucas**: 是的。联系我们。

<details>
<summary>Original English</summary>

**Lucas**: Yeah. Reach out.

</details>

**主持人**: 好的。是的，是的。好的。酷。

<details>
<summary>Original English</summary>

**主持人**: Okay. Yeah. Yeah. All right. Cool.

</details>

**发言人**: 就这样。酷。太棒了。酷。

<details>
<summary>Original English</summary>

**发言人**: That's it. Cool. Awesome. Cool.

</details>

**Lucas**: 非常感谢。

<details>
<summary>Original English</summary>

**Lucas**: Thank you so much.

</details>

**Axel**: 是的。谢谢。

<details>
<summary>Original English</summary>

**Axel**: Yeah. Thanks.

</details>

**发言人**: 热。热。

<details>
<summary>Original English</summary>

**发言人**: Heat. Heat.

</details>