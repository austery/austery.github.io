---
author: Latent Space
date: '2026-07-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=gKhW6vL4V9A
speaker: Latent Space
tags:
  - idea-generation
  - user-feedback
  - generalist-talent
  - work-related
title: 创意与品味：在自下而上的雄心时代中寻找瓶颈
summary: 文章探讨了当前技术发展背景下，构建新事物面临的瓶颈在于创意和品味。核心观点指出，想法并非凭空产生，而是源于用户交流、反馈或摩擦的反应。同时，讨论了从开发者到通用知识工作者的演进路径，以及在企业应用中如何通过适应用户需求来定制展示方式的重要性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/11 -->

### 瓶颈在于创意与品味

**Speaker A**: 我觉得瓶颈变成了创意和品味，我猜。因为现在任何人都能构建东西，我认为这真的是一个自下而上的雄心时代。因为有太多东西可以构建，你总是会被你在任何特定时间拥有的创意数量和正在做的事情所限制。

<details>
<summary>Original English</summary>

**Speaker A**: I think the bottleneck becomes like sort of like ideas and taste, I guess. Um I think because anyone can can build now, I think um it's really is the era of like bottoms-up ambition. And because there's so much to be built, like you're always going to be bottlenecked by the amount of ideas and amount of things that you're doing at any given time.

</details>

**Speaker B**: 关于创意，有趣的一点是它们并非凭空产生。它们通常来自某个地方，比如，在产品开发中，它们来自于与用户交流，或者对你看到的摩擦或反馈做出反应。我们谈到的这些通才型人才总是有价值的，比如，你知道的，闭环思考，并根据反馈或与用户交流等提出切合实际的创意。

<details>
<summary>Original English</summary>

**Speaker B**: One interesting part about ideas is like they're not like in a vacuum. It's like not They usually come from somewhere and like, you know, in product development like they're coming from talking to users or reacting to, you know, friction that you're seeing or feedback. There'll always be value in in these like generalists that we talked about, like, you know, closing that loop and and and coming up with these ideas that are grounded in in that feedback or talking to users, whatever it is.

</details>

### 主持人开场与嘉宾介绍

**Speaker A**: 在我们进入今天的正题之前，我有个小消息要告诉听众们。谢谢你们。如果不是你们选择点击并收听我们的内容，我们就不可能为你们带来你们如此渴望的AI工程、科学和娱乐内容。几乎每天都有人找我们谈赞助，但幸运的是，有足够多的你们订阅了我们，让我们能够在没有广告的情况下维持这一切，我们想保持这种状态。但我只想请大家帮一个忙。你们能做的最有力、完全免费的事情，就是点击那个订阅按钮。这是我对你们唯一的要求，而这对我和我的团队来说意义重大，他们每周都如此努力地为大家带来《In Space》节目。如果你们订阅了，我保证我们会永不停止地努力，让节目变得更好。现在，让我们开始吧。

<details>
<summary>Original English</summary>

**Speaker A**: Before we get into today's episode, I just have this small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis, but fortunately enough of you actually subscribe to us to keep all this sustainable without ads, and we want to keep it that way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you, and it means absolutely everything to me and my team that works so hard to bring the In Space to you each and every week. If you do it, I promise you we'll never stop working to make the show even better. Now, let's get into it.

</details>

**Speaker A**: 好的，今天我们请到了来自OpenAI的Akshay。欢迎你。

<details>
<summary>Original English</summary>

**Speaker A**: Okay, we're here in the studio with Akshay from OpenAI. Welcome.

</details>

**Akshay**: 谢谢。

<details>
<summary>Original English</summary>

**Akshay**: Thank you.

</details>

**Speaker A**: 还有我们值得信赖的联合主持人Vibhu。你最近推出了ChatGPT Work。你领导核心产品工程。你知道，这是一段很长的旅程。我觉得很有意思的是，你从Walrus和Airtable的无代码或低代码起步。在某种程度上，ChatGPT Work有点像超级应用中的超级应用，因为这里是终极的无代码，你只需写一个提示。

<details>
<summary>Original English</summary>

**Speaker A**: And with our trusty co-host Vibhu. We So, you recently launched ChatGPT Work. You lead core product engineering. You know, it's been a long journey into into all this. I find it very interesting that you started with no-code or low-code with Walrus and Airtable. And to some extent, ChatGPT Work is kind of like the super app of super apps of well here is the ultimate no code you just write a prompt.

</details>

**Akshay**: 是啊。是啊，事情真是循环往复，很有趣。我的意思是，在我的职业生涯中很长一段时间，我是在消费金融科技领域起步的，但之后，有一个假设是，我们工程师能用代码做到的事情，如果能以更易获取的方式带给更多人，那将是真正的魔法。我们当时在做一个创业项目，实际上是在LLM和视觉LLM出现之前，研究如何用AI做自动化测试，那时候效果有点糟糕，但我们尽力而为。后来我在Airtable工作了一段时间，秉持着同样的理念：如果我们能把数据库或其背后的参数带给人们，那对他们会非常有用。但是，一旦LLM出现，很明显，这就是缺失的那一块，是让每个人都能体验到代码的魔力，而无需了解底层原理所必需的关键技术。所以，我认为这次发布以及我们所做的所有事情，都是那个理念的体现。

<details>
<summary>Original English</summary>

**Akshay**: Yeah. Yeah, it's it's it's funny how things come like full circle. I mean, I think for a long time my career I mean I started my career working consumer fintech but then after that like there's this hypothesis that you know the things that we were able to do with code like as engineers like if we could bring that to many more people in a more accessible way then that would be truly magical. We were working on a startup so I actually found it like before LLMs before vision LLMs on how to do automated testing with AI and it was it was kind of jank back then but you know doing what we can and then and then worked at Airtable for a while on you know the same thesis that like if we can bring a database or the parameters behind a database to people that'd be really useful to them. Um but once I think LLMs came onto the scene it became clear that like this was like the missing piece like the missing technology required to like bring the magic of code to everyone without them having to know what's going on underneath the hood. And so like I think this launch and you know all of the stuff that we've been up to is like um the manifestation of that.

</details>

### 加入OpenAI后的变化与不变

**Speaker A**: 你加入的时候情况怎么样？你是2023年加入OpenAI的。现在我们有了这么多东西：ChatGPT、Codex应用、ChatGPT for Work。事情发生了怎样的变化？

<details>
<summary>Original English</summary>

**Speaker A**: How was stuff when you joined? So you joined OpenAI in 2023. Now we've got you know so much more stuff. So ChatGPT, Codex app, ChatGPT for work. How have things changed?

</details>

**Akshay**: 实际上，我觉得更有趣的是那些没有改变的事情。我猜，我加入的时候，我记得当时公司大概有500人。我担心的一点是，我在寻找更早期阶段的东西，想知道它是否足够“创业”。我加入后心想，天哪，这感觉比我所能想象的还要有创业氛围。这一点直到现在也真的没有改变。我的意思是，我认为那种自下而上的雄心壮志，以及任何人都有能力做任何事情、提出想法并将其发布出去，这真的很酷。但在使命方面，我认为真正吸引我的是这个使命：将前沿智能带给每个人，构建AGI，然后将其带给每个人。而且，即使在当时，我也认识到，这个愿景不会是线性发展的。我们可能会尝试不同的产品，会有成功也有失败。但愿景和使命始终如一，我们现在开始看到各个部分拼凑在一起，这真的很酷。

<details>
<summary>Original English</summary>

**Akshay**: I actually think the more interesting thing is how things haven't changed. Like I guess like one I I joined I remember when I joined it was like 500 people. One thing I was worried about was like I was looking for something you know more early stage and like was it going to start up enough and I joined I was like dude this feels even more start-upy than I could ever imagine. And like that that really hasn't changed even till now. I mean I think the like level of like bottoms-up ambition and like the ability of anyone to like you know do anything or have an idea and and and ship it is is really cool. But on the like sort of mission side I think what was really compelling to me is this mission of you know bringing frontier intelligence to everyone like building AGI and then bringing it to everyone and um I think acknowledging even then that like that vision is going to, you know, not be a linear progression. Like we're probably going to like try different products and and have different things that that succeed and don't. Um, but the vision has stayed the same and the mission has stayed the same and we're starting to see the pieces um, fall together and and that that's really cool.

</details>

### 企业级市场的经验教训

**Speaker A**: 呃，你之前负责企业业务。很多人从未接触过ChatGPT for Enterprise。嗯，你从那里学到了什么，并应用到了现在的工作中？

<details>
<summary>Original English</summary>

**Speaker A**: Uh, you worked on enterprise. What a lot of people never touched chat chat chat chat GPT for enterprise, God. Um, what is something that you learned from there that you're bringing into your work now?

</details>

**Akshay**: 我认为在企业领域，没有一刀切的解决方案。嗯，我记得在ChatGPT Enterprise早期，我们会和客户交谈。当时ChatGPT发布已经一年了，每个人都兴奋地想把AI引入他们的企业。我以为会有很多团队被组建起来，作为AI部署团队，拥有巨额预算。如果你问任何人他们兴奋的是什么？他们想解决什么问题？起初，你会得到一些基础答案，比如“是的，我们有所有这些联系人和数据等等”。但如果你再问他们，比如，他们希望AI在工作场所实现的具体用例是什么，你会得到各种各样、差异巨大的答案。这很有趣，你知道，使用这些模型和产品，你有一个盒子，你可以对它说任何话，这就是魔法所在。但另一方面，这也意味着你不知道该用它做什么。在企业领域，我认为很大一部分工作实际上是去适应用户，了解他们试图解决什么用例，然后教会他们如何使用AI来获得优势。

<details>
<summary>Original English</summary>

**Akshay**: I think how there's no like one-size-fits-all solution in enterprise. Um, I remember in the early days of chat GPT enterprise like we would talk to customers and like everyone that was like when I think it was a year after chat GPT was released and everyone was so excited to bring um, you know, AI into their enterprise and like I thought there was all these teams that that were being set up as like you know, the AI deployment team with like these enormous budgets and if you asked anyone like what were they excited about? Like what were they excited about solving? Like at first you'd get like you know, kind of like the the baseline answers of like yeah, we have all these contacts and data and all this stuff. But then if you ask them like you know, what was like a discrete use case of like they want AI to enable in their in their workplace, you get such a different like variance like explosion of different types of answers and it's interesting like you know, you using like these models and these products, you you have this box and you can say anything to it, which is the magic. But it's on the flip side, it also means that like you don't know what to do with it. And in enterprise, I think a big part of that is like actually meeting the users where they are like what use cases were they trying to solve and then actually teaching them how they can use AI to like gain leverage there.

</details>

**Speaker A**: 你是否有意识地将这与前向部署工程区分开来？

<details>
<summary>Original English</summary>

**Speaker A**: Do you meaningfully differentiate that from forward deployed engineering? Or

</details>

**Akshay**: 我认为这里面有市场推广的一面，也有产品的一面。

<details>
<summary>Original English</summary>

**Akshay**: I I think there's like the the like go-to-market side of it and then there's like the product side of it.

</details>

**Speaker A**: 我认为你需要更多地站在产品这边，是的。嗯，而且我认为，无论我们在FDE（前向部署工程）方面做得有多好，归根结底，如果用户正看着他们的电脑或手机，我们的工作就是在产品中赋能他们，并告诉他们该怎么做。嗯，所以我们对此感到非常兴奋。

<details>
<summary>Original English</summary>

**Speaker A**: I think you need to be more on the product side, yeah. Um, and I think like however good we get at FDE motion, like I think at the end of the day if we have a user who's like looking at their computer or looking at their phone, like it's our job in the product to like be enabling them and showing them where to go. Um, so we're really excited about that.

</details>

### AI采用的现状与未来机遇

**Speaker A**: 你认为在过去3年的采用过程中有变化吗？你知道，有一些阶跃性的变化，比如推理模型等等。企业仍然面临同样的问题，即不知道用它做什么的黑箱问题，还是情况已经改变了？

<details>
<summary>Original English</summary>

**Speaker A**: Do you think there's been changes, you know, over the past 3 years of adoption? So, there've been, you know, step function changes, you have reasoning models and whatnot. There's still the same problems of enterprise has black box to know what to do with it or have things changed?

</details>

**Akshay**: 我的意思是，我们现在看到使用量大幅增长，对吧？每个人都对此感到非常兴奋。感觉就像，你知道，数以百万计、数以亿计的人在使用ChatGPT。他们大致了解如何与AI协作。但是，每当一项新能力被解锁时，比如现在我们看到智能体（agents）的出现，可能仍然有一批早期采用者，他们真正理解它。他们知道，你可以做任何事情。你只需要确保有正确的上下文，连接到正确的工具，然后进行监督，但一切皆有可能。但还有十倍、百倍更大的市场，他们还没有理解这一点，或者还没有看到这一点。嗯，所以我认为这就是下一阶段。嗯，所以我想回答你的问题，我认为采用已经存在并且正在快速增长，但我认为机会要大得多，大得多。

<details>
<summary>Original English</summary>

**Akshay**: I mean, we're seeing now that like there's this huge uptick, right? Everyone's like extremely excited about it. It feels like, you know, many people like millions, hundreds of millions of people are using ChatGPT. They understand like how generally to work with AI. But then like every time like a new capability gets unlocked. So, now like we're seeing with agents, like there is probably a contingent of like early adopters still who, you know, truly get it. We're like, you know, we you can do anything. You just have to make sure the right context is there. It's connected to the right tools and then that you're supervising it, but like anything is is is possible. But then there's like this like 10x or 100x bigger market or like they don't yet get that or they don't yet see that. Um, and so I think that's the next stage here. Um, so I guess to answer your question, like I think the adoption is there and and growing fast, but I think the opportunity is like far, far bigger

</details>

<!-- chunk 2/11 -->

### 从 Codex 到 ChatGPT Work：产品合并的决策过程

**主持人**: 对。嗯，那我们直接跳到 ChatGPT Work 吧。大概一个月前才宣布的。是什么决策过程导致了它的诞生？你知道，就是那个超级应用的整体合并。我们是正式这么叫它吗？你也废弃了浏览器。我想请你总结一下过去几个月你在这个项目上的工作。

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh, well, let's let's uh skip ahead to ChatGPT work. Only like a month ago or so announced. What was the sort of decision process that led into it? You know, there was this overall merging of the super app. Is Is that what we're officially calling it? You deprecated the browser as well. Just I guess summarize your last like couple of months of working on this thing.

</details>

**嘉宾**: 是啊，现在感觉好像过了很久，但其实也就几个月。我想最突出的一个推动力，是我们发布 Codex 的时候，甚至是在内部使用 Codex 的时候。它真的让我们很惊讶。我们最近发布了一些相关数据，但 OpenAI 内部非开发人员的采用率出现了一个真正的拐点。在产品开发过程中，我们会进行用户研究访谈，与内部人员交流。让我印象最深的是，比如你去和战略财务、市场部的人聊，他们都在用 Codex 处理他们的用例，这部分很酷。但真正让我触动的是，他们为自己在使用 Codex 而感到多么自豪。

<details>
<summary>Original English</summary>

**Guest**: Yeah, it feels like forever now, but I guess it's only been a few months. I think maybe the one one like impetus that like is most salient is when we released Codex or even internally had Codex. Like it was really surprising to us. I think we recently put out some stats on this, but there was this like real inflection of like adoption among non-developers at OpenAI. And I, you know through this product development process like we go to like these UX our sessions to talk to people internally and the thing that stuck out to me is like one like you know you go talk to like strategic finance or marketing or whatever and they're all using Codex for you know their use cases that that that part's cool but the thing that really stuck out to me is how proud people were that they were using Codex like how like

</details>

**主持人**: 就好像“我不该用这个，但我用了”。

<details>
<summary>Original English</summary>

**Host**: It's like I'm not supposed to be using it but I am.

</details>

**嘉宾**: 对，就是那种感觉，他们觉得自己是早期接触这个新事物的人，但同时也有一种拥有了超能力的感觉。我们当时认识到，Codex 的力量、智能体的力量，我们已经有了庞大的用户基础，他们了解并喜爱 ChatGPT。我们如何向他们展示这些能力？如何把它带给他们？这是一个很难的产品问题，也很棘手，有很多方法可以解决。所以，我们称之为“合并”和“超级应用”，并最终在 ChatGPT Work 中发布了它。我们的核心问题是：如何做到这一点？但这一切都源于最初的那个认识：这种力量不仅仅是为开发者准备的，它可能比我们想象的更早地惠及每一个人。

<details>
<summary>Original English</summary>

**Guest**: was that it was like that they were you know early to this like new thing but it was also this thing of like they felt like they had a superpower right and what we recognized then is that like the the power of Codex power of agents like we already had this massive distribution base of people who have you know come to know and love ChatGPT like how do we show that to them like how do we bring it to them which is like a hard product problem and it's like a tricky thing right there's many ways you can go about it and so that's what we called the merge and the super app over time and and and ultimately launched it in ChatGPT work is how do we do that but it came from that initial realization that like the the power was not only for developers like much much earlier than probably even we thought like it could be extended to to everyone.

</details>

### 产品定位：为“工作型”任务服务

**主持人**: 你怎么看待这些产品的不同定位？比如，它们是为谁服务的？Codex 最初是从命令行开始的，然后是应用，现在有了 ChatGPT、Codex 和 ChatGPT Work 的合并。这是面向普通用户、企业用户还是工作场景？你如何定位它？

<details>
<summary>Original English</summary>

**Host**: How do you see the products differently so like who is it for right so Codex started out even CLI then app now there's a merge of ChatGPT Codex and ChatGPT work so is it the opening for the average user for enterprise for work how how do you position it?

</details>

**嘉宾**: 我认为我们希望将其定位为：如果你在做与“工作”相关的事情。暂时找不到更好的词了。我认为“生产力”实际上是我所支持的支柱，这也是我们团队的名字。我们叫它“生产力”而不是“企业”或“工作”之类的原因，是因为还有个人生产力。我看到人们在个人生活中用 ChatGPT Work 做一些技术上不能归类为“工作”的事情，但这些智能体非常强大。最近的一个例子是，有人在我们的 Slack 上发帖说，有人没收到包裹，然后他们收到了亚马逊或快递公司发的照片，他们让 ChatGPT Work 去查找包裹在哪里。这个智能体非常执着，它拿了图片，查看了社区周围的大量房源信息，最终精确地找到了包裹所在的公寓大楼，并把信息给了他们。所以，我认为所有这些都是与“工作”或“生产力”相关的事情。这就是我们希望产品成为的样子。你问到了 Codex。我们认为 Codex 是一个持久的品牌，但我们有一个原则：我们不希望用户被困在一个标签页或体验中，而无法获得产品的全部力量。所以，基本上你在桌面版 Codex 产品中能做的一切，在 ChatGPT Work 中也能做，反之亦然。但我们在产品决策上做出了一些有主见的选择，比如：如果你要获取一个仓库，我们想向最终用户暴露多少初始状态？或者，我们想让用户看到智能体思考过程的体验有多大程度是“差异前置”的，这样你就能在按钮旁边看到差异。在安全方面，我们如何考虑沙箱化，并确保我们在一种状态与另一种状态下有正确的默认设置。所以，这背后有一些考量，但我们确实不希望用户需要去选择他们处于哪种体验中。

<details>
<summary>Original English</summary>

**Guest**: I think we want to get to position it for if you're doing worky related things lack of a better word right? [laughter] I think productivity is like a is is actually what like the pillar that I I support like that's the name of the team and the reason for that the reason we call it productivity and not like you know enterprise or or like work or something like that is because there's also personal productivity right and like I think ChatGPT work is I've seen people do things in their personal lives that you wouldn't classify as like work technically but like these agents are you know super capable for like one one recent example that someone posted about on our slack is like someone had like a missed package, like they didn't receive it and then they got like the picture of it you know from Amazon or whatever the courier was and they like asked ChatGPT work to like find out where that package is and like the agent you know is extremely tenacious and like they like took the image and like looked at a bunch of like listings around their neighborhood and figured out exactly the apartment complex in which the package was like gave them this information. And so like I think there's all these things that like you you know worky or productivity related things. I think that's what we want the product to be. You asked about Codex. I think we think Codex is you know a durable brand but we have a principle that like the user you know we don't want a user to get stuck in a tab or an experience where they don't get the power of the product. And so like basically everything that you can do you know in the Codex version of the product on on desktop you can do in ChatGPT work and vice versa but we made some opinionated product decisions on like you know how much of the get state if you're going to get repo do we want to expose to the end user or how much do we want to make the the experience of seeing the agents thinking like diff forward so that you're getting you're getting exposed to the diff side of the button. And then like on the safety side like how do we want to think about like sandboxing and making sure that we have the right defaults in one one state versus the other. So um there's like these some opinions that go behind that but we do we do want we don't want the user to need to choose which experience they're in.

</details>

**主持人**: 这对 AGI 来说是个好目标，对吧？人们不想去选择他们想要哪个版本的 AGI，他们只想让 AGI 为他们做决定。嗯，我想问一下，Codex 的底层框架和 ChatGPT Work 的底层框架是一样的吗？只是 UI 上的差异，还是在提示词层面甚至更深层次有不同？

<details>
<summary>Original English</summary>

**Host**: That is a good goal for AGI right like people don't want like to hide to choose what version of AGI they want they just want the AGI to decide for them. Um can I get a answer or like it's not super clear to me is the Codex harness and the ChatGPT work harness the same? Is it just UI affordances or are there actually prompt level or even even deeper differences?

</details>

**嘉宾**: 底层框架是一样的，是共享的。嗯，在这两个产品中，我们都对框架进行了改进，使其更适合知识工作，尤其是在插件、计算机使用或工件方面。无论你处于哪种体验中，都能获得这种能力。在用户体验方面，我们有自己的一些看法。当你处于 Codex 模式时，用户体验应该是什么样，应该如何表现。还有一些我提到的关于沙箱的东西。但底层的能力框架应该是一样的。实际上，我有点好奇，也许我们可以运行一个查询，看看它在两种模式下会有什么不同？

<details>
<summary>Original English</summary>

**Guest**: So the harness is the same the harness is shared. Um on in both of the products we made improvements to the harness to make it good for knowledge work especially as it relates to plugins or computer use or artifacts. You get that power regardless of which your experience you're in. On the UX side, there's opinionated takes that we have. When you're in Codex mode, what the UX should be how the UX should behave. And some stuff around the sandbox that I mentioned, but the underlying harness of capabilities should be the same. Actually, I'm just kind of curious, maybe we can uh is there a query that we can run that would look different in the the two modes?

</details>

**主持人**: 是的，我试过让它创建一个退休计算器电子表格之类的东西。嗯，在两种模式下都试了。在 Codex 模式下，你可能需要在一个仓库里，但你会看到我正在创建的表格的差异以及文件编辑之类的东西。嗯，但在 Work 里，你就看不到这些。我觉得这非常清楚。另外，我还想深入了解一下你的生产力团队。呃，首先，除了生产力团队，还有哪些顶层团队？生产力不就是一切吗？

<details>
<summary>Original English</summary>

**Host**: Yeah, I tried to create like ask it to create like a retirement calculator spreadsheet or something um and in both in both modes and then in Codex mode um you might have to be in a in a repo for this, but you'll see like the diffs of like the the sheet that I was creating and stuff like that um and the file edits. Um but in work, you won't be able to see that. I think this that's super clear. And then also the other thing I wanted to dive into was your uh the productivity team. Uh what else is there First of all, you know, what are the top-level teams other than productivity? Isn't productivity everything?

</details>

**嘉宾**: 所以，我们有一个专注于 ChatGPT 核心聊天体验的团队，面向消费者。这并不全是生产力，因为人们每天都在用 ChatGPT 进行搜索、给亲人写消息、思考如何学习新主题等等。里面还有更多功能，比如创建图像。聊天里还有更多东西，数亿用户正在使用，这显然需要一个非常专注的努力。嗯，还有专注于企业、基础设施、API 等方面的团队。

<details>
<summary>Original English</summary>

**Guest**: So, you know, we have a team focused on uh on ChatGPT like the the core chat experience um for consumer, which is like, you know, not I think all productivity like there's people are using ChatGPT every day for search to, you know, figure out how to write messages to loved ones, to think about um how to like learn a new topic, etc. And so, there's so much more inside to create images. And there's so much more in chat that you know, the hundreds of millions of users are using that um you know, obviously that that warrants like a a very dedicated effort. Um and there's teams focused on enterprise and infrastructure and API and stuff like that as well.

</details>

### 现场演示与设计取舍

**主持人**: 我把它调出来。是的，我让它们两个都运行着。

<details>
<summary>Original English</summary>

**Host**: I will bring it up. Yeah, so I have them both running.

</details>

**嘉宾**: 好的。

<details>
<summary>Original English</summary>

**Guest**: Yeah.

</details>

**主持人**: 这是 Work。这里有一个 Codex 版本。我选了 5.6 个灵魂，所以这需要一些时间。我想我们就让它后台运行，等它们完成后，我们来看看一些差异。

<details>
<summary>Original English</summary>

**Host**: This is work. There's a Codex version here. I picked 5.6 souls, so this will take a while. I think I think we'll just keep it in the background and you know, as as they finish, we'll look into some of the differences.

</details>

**嘉宾**: 是的，但如果你立刻切回 Codex 版本，你会看到……嗯，看起来不错。是的，没错。它们看起来是动态的，表明你正在一个 Git 仓库里。嗯，你可能会错过一些东西，因为其中一些信息是在实际的思考链中，伴随着那些更改以及我们如何展示它们。

<details>
<summary>Original English</summary>

**Guest**: Yeah, but immediately I think if you flip back to the Codex version, you'll see that uh that it seems it seems good. Yeah, exactly. They're like dynamic on it seems that you're in a Git repo. Um and you might miss some stuff because some of it is like in the actual chain of thought with with those changes and how we display that, but

</details>

**主持人**: 有没有什么不直观的，比如你本来想发布某个功能，但收到反馈后说“不，我们不这么做了”？背后的思考是什么？

<details>
<summary>Original English</summary>

**Host**: Is is there an unintuitive like is there a thing that you wanted to ship and then you got feedback and you're like no let's not do it. Like what's the thinking behind that?

</details>

**嘉宾**: 在 ChatGPT Work 里吗？

<details>
<summary>Original English</summary>

**Guest**: In uh ChatGPT work?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**嘉宾**: 我认为我们本可以走的一个方向是，让这些体验完全分离。就像，为什么要把它们做成完全不同的应用，或者即使在同一个应用里也做成完全不同的体验？为什么要全部合并呢？

<details>
<summary>Original English</summary>

**Guest**: I think one direction we could have gone with this is like keeping the experiences like completely separate. So it's like why why exactly like different apps or even in the same app like different completely different experiences. Like why merge it all?

</details>

<!-- chunk 3/11 -->

### 产品融合背后的理念

**主持人**: 比如，你知道，Codex 显然很受欢迎。为什么要把这些产品整合在一起？

<details>
<summary>Original English</summary>

**Host**: Like what is, you know, Codex obviously people love. Like why, why bring these products together?

</details>

**OpenAI 产品负责人**: 我认为这里的直觉是，我们所有的工作都在随着 AI 发生巨大变化，坦白说，每隔几个月就变一次。我感觉我每天早上醒来，做的事情和几个月前就完全不同了。我这里的假设——或者说，我们的假设是——我们正在构建的这项技术，有一部分是在给人们提供杠杆。你知道，也许是你工作中更平凡的部分，或者那些如果你能自动化，就能更快地分享更多想法的部分，就像你现在能做到的那样。正因为如此，这实际上可能会模糊那些只写代码、只写策略文档、或者策划活动、做营销、做播客等等的人之间的界限，对吧？所以随着时间的推移，这些事情会变得模糊。试图根据你是谁来划出一条硬性边界会越来越难，我们应该让用户去选择，而不是把他们框死。因此，这里投入的大量工作，比如保持原语的一致性——例如，插件在这个产品、ChatGPT 和云端都是统一的——就是出于这个理念。这个理念就是，最终所有东西都会融合在一起，我们不想——我们希望对何时使用哪种体验给出指导性建议，但我们不想把任何人框死。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: And I think the intuition here is that like all of our jobs are like changing dramatically with AI, like frankly every few months. Like I feel like I wake up and then I'm like doing a completely different thing that I was doing a few months ago and my my hypothesis here is that or I should say our hypothesis is that like part of what we're we're building in this this technology is giving people leverage. Like you know the things maybe it's the more mundane parts of your job or or parts of it that like if you were able to automate you'd be able to share more ideas faster or whatever like you're able to do now. And because of that like that might actually blur the lines between someone who's like only writing code or creating strategy docs or you know planning events or um helping with marketing or doing podcasts or whatever, right? And so like these things are going to get blurred over time. And so like trying to draw a hard boundary based on like the who you are is is is going to be is going to be tough and like we should enable users to choose, but we shouldn't box them in. And so a lot of the work that went in here like you know keeping the primitives the same like for example plugins are like unified across um this product and ChatGPT and the cloud was because of that. It's this this thesis that like eventually things are going to come together and and we don't want to be like we want to be prescriptive about when to be in either experience, but we don't want to box anyone in.

</details>

### 新旧交互界面的对比

**主持人**: 我想知道是否有用户非常习惯于旧的 ChatGPT 交互界面，而现在它实际上被 Codex 的交互界面取代了。我无法想象那是什么样子，但也许他们更偏向对话式的那一面。你能比较一下这两个界面吗？毕竟只有你见过。

<details>
<summary>Original English</summary>

**Host**: I wonder if there's users who are very tuned to the old ChatGPT harness that is effectively now replaced by the the Codex harness. I can't imagine what that was, but maybe they're more the more conversational side. Can you compare and contrast the the two harnesses cuz only you've seen it?

</details>

**OpenAI 产品负责人**: [笑]

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: [laughter]

</details>

**主持人**: 是啊，我的意思是，我认为 ChatGPT 现有的交互界面今天仍然存在。它存在于这个应用里。

<details>
<summary>Original English</summary>

**Host**: Yeah, I I mean, I think ChatGPT the the existing harness like still exists today. It like exists in this app.

</details>

**主持人**: 经典的那个，对吧？

<details>
<summary>Original English</summary>

**Host**: The classic, right?

</details>

**OpenAI 产品负责人**: 你只要开始一个新对话，不进入“工作”模式就行。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: You just start a new chat and you don't go under work, right?

</details>

**主持人**: 对，如果你开始一个新对话并进入聊天模式，那你就是在和现有的 ChatGPT 实例对话。

<details>
<summary>Original English</summary>

**Host**: Yeah, if you start a new chat and go to chat, then you're you're talking to ChatGPT with the existing instance.

</details>

**OpenAI 产品负责人**: 对，所以这个不会去写代码。或者说它是在行内进行的，不是在沙盒环境里。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: Yeah, so this one's not going to code. Or it's going to be in line. It's not in a in a line of sandbox.

</details>

**主持人**: 对，实际上，如果你在创建电子表格，我们会尝试引导你进入“工作”模式。

<details>
<summary>Original English</summary>

**Host**: Yeah, actually we do try to push you to to go to work if you're creating a spreadsheet.

</details>

**OpenAI 产品负责人**: 这是一个路由决策。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: And this is a router decision.

</details>

**主持人**: 抱歉，这是一个路由决策吗？

<details>
<summary>Original English</summary>

**Host**: Is it a router decision? Sorry.

</details>

**OpenAI 产品负责人**: 这是模型做出的决策，然后，你知道，它发现你能够或者正在尝试做一些在“工作”模式下能更好完成的事情。但我认为你的问题是，ChatGPT 聊天界面有什么优势？

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: This is the decision that, you know, the model is making and then like, you know, it sees that you're able to or you're trying to do something that would be better served in work mode. But I I think your question was like, what what are the advantages of like the the chat like ChatGPT chat harness?

</details>

**主持人**: 更广泛地说，我基本上是想做一次关于交互界面工程的口述历史。

<details>
<summary>Original English</summary>

**Host**: It's more broadly like I wanted basically do an oral history of harness engineering.

</details>

**OpenAI 产品负责人**: 嗯。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: Mhm.

</details>

**主持人**: 对吧？你知道，ChatGPT 的交互界面从我们称之为 01 时代一直用到现在。而现在它实际上正在被 Codex 的交互界面取代。它们有些重叠，但我很好奇，如果有什么变化的话，到底改变了什么。

<details>
<summary>Original English</summary>

**Host**: Right? You know, the ChatGPT harness lasted us from let's call it the 01 era until now. And now it's being replaced by the Codex harness effectively. And they're they're overlapping somewhat, but I'm curious what changed if, you know, if there is.

</details>

**OpenAI 产品负责人**: [笑] 我对此的看法是，这有点像是一个不断分化、融合、再分化、再融合的过程。而聊天模式，就像我之前谈到的许多用例一样，比如搜索或学习，我认为我们真正在优化的是延迟、个性以及其他不同的东西。随着时间的推移，人们喜爱 ChatGPT 的原因，正是因为我们长期以来一直在优化这些东西并为此努力。而 Codex 让我们学到的是，如果你给智能体一个像计算机一样无限灵活的环境，你就能做出非常非常强大的事情。所以当我们思考，好吧，对于知识工作，我们应该选择哪种模式？对我们来说，更自然的做法是把它带到这个计算机环境中，并且，你知道，也许为那些不习惯的用户抽象掉这个计算机的一些细节，但给予他们同样的能力。但最终，我认为我们希望所有地方都拥有这种能力，对吧？我们希望在任何地方都能满足用户的需求。所以，我确信未来还会有工作要做，以便让所有场景都具备同等的功能。但这只是一个问题，即我们历史上在产品上关注了什么，以及我们现在关注什么。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: [laughter] My perspective on this is like there's there's there's sort of like a a constant process of like divergence, convergence, divergence, convergence. And and chat, like many of the use cases I was talking about before like, you know, search or learning, I think we're we're really optimizing for latency and optimizing for personality and like different things that over time like the product The reason people love ChatGPT is because we've been optimizing for those things and working on them for so long. Codex, what we learned was that like if you give the agent access to this infinitely flexible environment as a computer, you can do really, really powerful things. And so when we think about like, okay, well, for for knowledge work, like what is which mode should we choose? It was like it felt more natural to us to bring that to this like computer environment, and you know, maybe abstract some of the details of this computer away from users who might not be used to that, but like give them that same power. Um but ultimately, I think that we want the power in in all places, right? We want to meet people where they are. So, I'm sure there'll be work down the road in order to to get things to be um equally only capable in in all scenarios. Um but it's just a question of like what we've been focusing on the product on historically, and what we're focusing on now.

</details>

### 新模型的使用建议

**主持人**: 我想除此之外，除了交互界面以及何时在工作场景使用 Codex 和 GPT 之外，你们还发布了新模型，对吧？在这方面有什么指导建议吗？人们喜欢精打细算，比如“只在需要高推理能力时用 o3”，“这种情况用 Sonnet”，等等。

<details>
<summary>Original English</summary>

**Host**: I think alongside that, outside of just Harness and when to use Codex and GPT at work, there's also the new models you've released, right? Um any guidance there? So, people love to min-max what to use, like only use Terra on high reasoning versus uh for this, you know, you want to use Soul here, ignore

</details>

**OpenAI 产品负责人**: 有 32 个选项。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: There's 32 options.

</details>

**主持人**: 是啊，是啊，是啊。

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, yeah. Um

</details>

**OpenAI 产品负责人**: [笑]

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: [laughter]

</details>

**主持人**: 但话虽如此，你知道，对于那些正在扩展、尝试提高工作效率、尝试新东西，但又不清楚所有这些模型区别的人来说，有什么建议吗？

<details>
<summary>Original English</summary>

**Host**: but um that being said, you know, for people that are expanding, so uh productivity trying stuff for work that don't have the breakdown of what all this is, um what's what's the advice, right?

</details>

**OpenAI 产品负责人**: 嗯，我的意思是，在给建议之前，首先要说的是，没有这些模型，这一切都不可能实现。我认为你之前问过，比如，工作的灵感是什么，早些时候我提到了我们从 Codex 上看到的东西，但那也是因为模型的能力变得无限强大。现在这种情况再次发生。我认为这又是一次阶跃性的提升。回到建议的问题上，我们希望默认设置是最好的。我们希望对于默认设置是有明确主张的，所以我们选择了一个我们认为对所有人都最好的默认设置。而且，你知道，对于高级用户，我们在底层提供了选项。现在可能有人会争论说选项太多了，我们也在努力简化。但是，你可以调整推理级别，如果需要，也可以在不同的模型类别之间切换，但默认设置应该对大多数用例来说是最好的。所以我给大多数人的建议是坚持使用默认设置。然后，如果你遇到一种情况，你认为可以尝试不同的配置，如果你在成本效率或智能质量方面不满意，那么你可以更改默认设置，看看是否能得到更好的结果。但我们认为默认设置应该足够好了。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: Well, I mean, I think before the advice, like the first thing is like none of this would be possible without these models. Like I think you asked earlier like, you know, what was like the inspiration for work, and like, you know, earlier on, like I I mentioned like what we were seeing with Codex, but that was also because of the the models were getting infinitely more capable. That's happening again. I think it's like another step function jump now. And to answer the question on advice, like we want the default to be the best possible. Like we want to be opinionated about the default, and so we've we've chosen a default that we think is going to be the best for everyone. And you know, we have for power users options under the hood. We could one could argue that there might be too many right now, and we're you know, working on simplifying it. Um but you can extend, you know, the reasoning level, and you can change between the different model classes if you need to, but the default should be the best for for most most use cases. So my advice to most people would be to stick to that. And then, you know, if you reach a situation in which you think that you could you want to try um a different configuration, if you're not seeing either the the efficiency on the on the cost side or or the the quality on the intelligence side, then you can change the defaults and see if you can get something better. But but we think that the default should be good enough.

</details>

**主持人**: 我有个想法想跟你探讨一下，因为你经验比我丰富得多。我最近一直在用 Sonnet，但搭配了“目标”功能。我的想法是，“目标”基本上增强了推理的努力程度，但伴随着更多的终止点和交互轮次。这样想对吗？相比于用 Sonnet Ultra 或者 Sonnet 超高推理模式。

<details>
<summary>Original English</summary>

**Host**: I have uh I I'm just going to run something by you since you you have way more experience than me. I've recently been doing Soul light but on with goal. With the idea that the goal basically augments the reasoning effort but with more terminations and turns.

</details>

**OpenAI 产品负责人**: 嗯。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: Mhm.

</details>

**主持人**: 这样想对吗？相比于用 Sonnet Ultra 或者 Sonnet 超高推理模式。

<details>
<summary>Original English</summary>

**Host**: Is that a good way to think about it? As opposed to Soul ultra or Soul, you know, extra high.

</details>

**OpenAI 产品负责人**: 是啊，这很难说，因为这是一种交互效应。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: Yeah. It's hard to say because it's like an interaction effect.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Exactly.

</details>

**OpenAI 产品负责人**: 这涉及到个人偏好，比如，作为个体，你喜欢如何与模型协作？你想要多少次你所说的那种“终止点”，以便你可以引导或确保它做正确的事情？我认为一般来说，人们应该尝试对他们有效的方法。我认为使用 Ultra 或多智能体设置最适合那些要么极其复杂（比如开放式探索），要么非常容易并行化的任务。我认为即使是使用“目标”功能，我认为它最适合那些你知道能够以可验证的方式持续取得进展的任务。但我认为大多数任务实际上并不属于这两类，至少在他们刚开始的时候是这样。所以这就是为什么我认为最好的第一步是用默认配置尝试，然后看看你想从那里往哪个方向走。

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: Exactly. It's like there's a preference on, you know, for you as an individual, like how do you like to collaborate with the models? Like how many of those like terminations, as you call them, do you want where, you know, you can uh steer or make sure that it's doing the right thing. I think generally people should try whatever works for them. Um I think that like using ultra or the like multi-agent setups are best for like when you have like tasks that are either incredibly complicated like open open explorations or very parallelizable. I think even for tasks, using goal I think is best for for tasks that you know that you'll be able to make consistent progress in a way that's verifiable over time. But I think for most tasks, they actually don't fall into either of those buckets. Um and so like at least when they're starting. And so that's why I think the best first step is like trying it with the the default configuration and then seeing like where you want to go from there.

</details>

**主持人**: 对。你们做了一个滑块，这实际上对减少恐慌非常有帮助。

<details>
<summary>Original English</summary>

**Host**: Right. You guys worked on a slider which is actually super helpful for reducing the amount of panic.

</details>

**OpenAI 产品负责人**: 是啊，是啊。[笑]

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: Yeah, yeah. [laughter]

</details>

**主持人**: 至少在移动端上很好用。这里有一个很好的阶梯式设计。

<details>
<summary>Original English</summary>

**Host**: It's nice on mobile at least. There's a nice ladder here.

</details>

**OpenAI 产品负责人**: 我……

<details>
<summary>Original English</summary>

**OpenAI Product Lead**: I

</details>

<!-- chunk 4/11 -->

### 高级视图与一维投影

**Speaker A**: 你还没试过。

<details>
<summary>Original English</summary>

**Speaker A**: haven't tried it.

</details>

**Speaker B**: 所以，你这里有高级视图，但如果你点击高级视图……对。

<details>
<summary>Original English</summary>

**Speaker B**: So, you you have you have the advanced view there, but if you click advanced view Yeah. Yeah.

</details>

**Speaker A**: 就是一个简单的阶梯，对。

<details>
<summary>Original English</summary>

**Speaker A**: Just a simple ladder, yeah.

</details>

**Speaker B**: 非常非常漂亮，非常多彩。

<details>
<summary>Original English</summary>

**Speaker B**: Very very pretty, very colorful.

</details>

**Speaker A**: 对，这里的想法是，虽然有多维度，但把它简化成一维，对吧？尝试为用户投射到单一维度上。对。就像，你知道，某样东西代表了一边的速度和效率，对。然后另一边代表了质量和全面性。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, the idea was here here was like reduced to like one dimension, even though there's multiple dimensions, right? Try to project it onto a single dimension for the user. Yeah. Like, you know, something from that represents like, you know, speed and efficiency on one side Yeah. And then like sort of like quality and thoroughness on the other side.

</details>

**Speaker B**: 我只是很困惑它用了这么多Soul。比如，低级的青铜……

<details>
<summary>Original English</summary>

**Speaker B**: I am just puzzled that it uses Soul so much. Like, the lower bronze

</details>

**Speaker A**: 我想是Spider，如果我没记错的话……哦，是的。

<details>
<summary>Original English</summary>

**Speaker A**: I think it's Spider, if I'm not mistaken, is Oh, it is.

</details>

**Speaker B**: 对，你看我们这边。所以他们预设Terra只是浅色的那个。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, you see our side. So, they they preset Terra to only be the light one.

</details>

**Speaker A**: 我明白了。

<details>
<summary>Original English</summary>

**Speaker A**: I see.

</details>

**Speaker B**: 但是，我觉得很多人实际上应该……更多人应该用Terra。第一，因为Soul一直在耗尽容量。

<details>
<summary>Original English</summary>

**Speaker B**: But like, I think a lot of people actually would More people should use Terra. One, because Soul keeps running out of capacity.

</details>

**Speaker A**: [笑声]

<details>
<summary>Original English</summary>

**Speaker A**: [laughter]

</details>

**Speaker B**: 我就是原因，你知道。这里有我们10分钟的……

<details>
<summary>Original English</summary>

**Speaker B**: I'm the reason, you know. Here's 10 minutes of our

</details>

**Speaker A**: 给你。

<details>
<summary>Original English</summary>

**Speaker A**: There you go.

</details>

**Speaker B**: ……退休计算器。

<details>
<summary>Original English</summary>

**Speaker B**: retirement calculator.

</details>

**Speaker A**: 哦，这就是那个Excel的东西。哦，天哪，看看那个。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, that's the Excel thing we're Oh my god, look at that.

</details>

**Speaker B**: 是工作，然后Codex还在运行，所以我们待会再回来看。我觉得看看思考过程、推理过程会很有趣。而且，你知道，我猜这是8分钟的工作。Codex还在运行。

<details>
<summary>Original English</summary>

**Speaker B**: is work, and then Codex is still cooking, so we'll get back into it. I think it'll be interesting to actually see the thought process, the reasoning. And also, you know, I guess this is 8 minutes on work. Codex is still cooking.

</details>

**Speaker A**: 对，顺便说一下，我……你知道Gabriel Chua吗？他是OpenAI安全团队的。他给我看了这个，我当时很震惊，这看起来像Excel。对。它编辑Excel文件。你从来没付过Excel许可证费，对吧？但不知何故，这居然能用，而且这是智能化的Excel。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, and by the way, I So, I Do you know Gabriel Chua? He's part of the Open AI safety team. He showed me this, and I was like pretty shocked that this looks like Excel. Yeah. It It edits Excel files. You never paid an Excel license. Right? Like, but somehow this is This is like kind of workable, and it's agentic Excel.

</details>

**Speaker B**: 对，我的意思是，我们这次发布的一个重大推动就是制品，对吧？在模型方面，我觉得如果你把这个和5.5以及之前的5.4比较，你会看到这些制品的质量有了显著的提升。然后在产品方面也是。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I mean, one of the big like pushes that we made for this launch was like artifacts, right? Like, both on the on the model side, like I think if you compare this with with 5.5 and and and 5.4 before that, you'll see that there's been pretty dramatic improvements in the quality of these artifacts. And then also on the product side.

</details>

**Speaker A**: 用户体验方面也很疯狂。比如，托管网站之类的，不再需要自己托管一个小网页了。

<details>
<summary>Original English</summary>

**Speaker A**: The UX side is also crazy. Like, hosted sites and whatnot, no no longer needing to host your own little webpage. Like,

</details>

**Speaker B**: 哦，我有个关于那个的故事。我可以单独做一件事。我需要在这里截取画面，但我们稍后会切到那里。我猜，你们进行了代码训练，因为你们做出了这么大的动作，并且在同一天发布了5/6和ChatGPT工作？模型训练团队和工程团队之间是否有相互影响，还是说发布日恰好是同一天？

<details>
<summary>Original English</summary>

**Speaker B**: Oh, I have a story about that. I can I can do a separate thing. I'll I'll need to take the the the visuals here, but we'll we'll cut to that later. Was there code training, I guess, because you were moving making this big move and you launched 5/6 on the same day as ChatGPT work? Was there influence between the model training teams and the harness teams or did they launch days just happen to line up the same day?

</details>

**Speaker A**: 我认为，你知道，我们与研究团队紧密合作，我的意思是，我认为这是工作中最神奇的部分之一，也是最有趣的部分之一。但是，对，我的意思是，仅以制品为例，你知道，你看到的很多幕后工作，都投入了大量精力来确保我们有正确的基础设施来训练模型，使其在这方面做得更好，然后在产品方面，为用户提供正确的体验，使他们能够与模型在这样的制品上进行协作。事实上，就像整个查看器，这里的直觉是，你知道，这不一定意味着你不再需要Excel许可证。这是第一阶段，对吧？这可能不是你制作退休计算器时的本意。你想要迭代，当你看到它时，如果这个东西与你实际看到的，或者如果你把这个发给Sean，你的同事会看到的，具有高度保真度。我认为这会让迭代变得容易得多，并且让你在产品迭代方面信任它。

<details>
<summary>Original English</summary>

**Speaker A**: I think the you know, we collaborate heavily with the research teams and I mean I think that's like one of the most magical parts of the job, like the most fun parts of the job. But yeah, I mean just just using artifacts as an example like you know, a lot of what you're seeing like underneath the hood, there's a lot of work that went into making sure that like you know, we had the right infra to be able to train the models to get better at this and then on the product side like had the right experience for users to be able to collaborate with the model on artifact like this. In fact like this whole viewer like the intuition here is that like you know, it's it's not necessarily that you wouldn't need an Excel license. This is stage one, right? Like this is probably not what you meant when you're like making a retirement calculator. You want to iterate and like when you're when you're seeing it and if this thing is high fidelity to like what you'd actually see and and or what your your co-workers would see if you were to send this to Sean. Like that that I think makes it so easier and makes you trust the the the product in in terms of iteration.

</details>

**Speaker B**: 当你说同事会看到时，你看到了一个多人多团队与制品的协作吗？你们有什么想法吗？

<details>
<summary>Original English</summary>

**Speaker B**: When you say co-workers would see, do you see a multiplayer multi-team collaboration with artifacts? Any any things you guys think about?

</details>

**Speaker A**: 分享它，对吧？对。

<details>
<summary>Original English</summary>

**Speaker A**: share it, right? Yeah.

</details>

**Speaker B**: 对，这是我们正在积极思考的事情。有一件事，你知道，我们在内部注意到，在不透露太多路线图的情况下，很多时候有人会ping我一些事情，我会问ChatGPT工作这个问题，然后把答案ping回去。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, it's something that you know, we're actively thinking about. One thing that you know, we've noticed internally without talking too much about the road map is that like I there's many times when someone will ping me about something and I'll ask ChatGPT work the question and then I'll ping them back the answer.

</details>

**Speaker A**: 最简单的就是，你知道，我们三个人都在一个托管页面上。

<details>
<summary>Original English</summary>

**Speaker A**: Like the simplest would be you know, the three of us are just all on one hosted.

</details>

**Speaker B**: 完全正确。我会想，你知道，我是否是这个循环中必需的一环？或者也许是我重新表述了他们的问题，或者从某些上下文中提取了信息等等。但是，你知道，当我把答案回复给他们时，这个过程也是有损耗的，对吧？我只是给了他们我对ChatGPT工作生成内容的解读。但在幕后，现实世界中有很多上下文信息，这些信息可能会很有趣。所以答案就是预先响应每一个传入的请求。

<details>
<summary>Original English</summary>

**Speaker B**: Exactly. And I'll think about like you know, like was I required in this loop or maybe it was you know, rephrase like what they were asking or pulled from some context or whatever. But like you know, when I gave them back the answer, that process was also lossy, right? Like I gave them just like my interpretation of what ChatGPT work cooked up. But like underneath the hood, there's so much context like in the real world and stuff that that could be interesting. So like the answer was preemptively respond to every inbound request.

</details>

**Speaker A**: 不，这就像我有时做的工作一样。

<details>
<summary>Original English</summary>

**Speaker A**: No, it's just like literally like this is what I do sometimes as my job.

</details>

**Speaker B**: 你复制粘贴，然后你知道，你只是一个从AI到AI的消息转发服务。

<details>
<summary>Original English</summary>

**Speaker B**: you copy paste and then you you know, you're just a message forwarding service from AI to AI.

</details>

**Speaker A**: 我觉得这很有趣，对吧？它帮助人们理解他们可以询问和委托的能力范围，很多时候人们直到尝试或有人展示给他们时才会意识到，然后你就会说，哦，好吧，好吧。

<details>
<details>
<summary>Original English</summary>

**Speaker A**: I think it's interesting, right? It helps people understand the capability of what you can ask and delegate that often times people don't realize until they try or someone shows you and then you're like, oh okay, okay.

</details>

**Speaker B**: 我明白了。对。我认为这也有一个轻微的安全问题，基本上你就是权限层。就像，是的，我可以查询你查询的所有内容，我可以得到自动回复，但也许我不应该看到它。对。然后，对，我没办法知道，因为我不应该知道我不知道的事情。

<details>
<summary>Original English</summary>

**Speaker B**: I see. Yeah. I think it's also there's also like a light security issue where like basically you're the permissions layer. Like yes, I could query everything that you query and I could get an automated response, but maybe I'm not supposed to see it. Yeah. And then yeah, there's no way I would know because I'm not supposed to know what I don't know.

</details>

**Speaker A**: 尤其是，你知道，当工作应用要求你连接插件时，它会从你的本地文件中提取信息等等。智能体能够访问的上下文信息量是非常个人化的，这是我们需要保护的东西。所以这绝对是一个挑战。

<details>
<summary>Original English</summary>

**Speaker A**: Especially as like, you know, with try to be work for for asking you to connect your plugins and you know, it's pulling from your local files and stuff like that. Like the the amount of context that the agent has access to is like deeply personal and like that's something that like we need to preserve. So that'll be definitely a challenge.

</details>

### 工作格式的未来：从Excel到Sites

**Speaker B**: 有Excel，有PowerPoint，有Docs，你知道，工作三件套。你们还考虑哪些其他工作格式？你知道，显然你做过Airtable。未来会不会有OpenAI Airtable？你知道，如果你们最终做了，那会是什么样子？

<details>
<summary>Original English</summary>

**Speaker B**: There's Excel, there's PowerPoint, there's Docs, you know, the grand trio of work. What other formats of work do you do you think about? You know, like obviously you worked on Airtable. Is there a future where there's like OpenAI Airtable? Like, you know, like what what what does that look like if if you ever ended up doing it?

</details>

**Speaker A**: 这是一个非常好的问题。我想，嗯，我的意思是，你没提到的一个是Sites，我认为这是这次发布的一个重要部分。Sites有一个方面，我认为人们在Twitter或X上经常谈论，就是你知道，这种原型设计工具。实际上，我们看到这次发布就发生了这种情况，你们之前提到的模型滑块，几乎完全是在一个Site里开发的。你知道，设计、工程和产品之间的协作就是在Site上进行的，我们可以在上面玩，你知道，调整交互设计，弄清楚它的感觉等等。嗯，但我认为另一个较少被提及的方面是，Sites作为知识工作的一个制品。我前几天实际上和我们公司财务团队的一个人聊天，我们提到，现在当他们团队每月制作报告时，历史上这些东西都在幻灯片和电子表格里，而现在它们就在Sites里。Sites是他们跨团队协作的机制。原因是它的带宽更高。你知道，像PowerPoint和Excel这些工具是无限灵活的，但在某个时候，要么作为人类你可能不知道如何使用某个功能，要么产品本身不支持它。但在Site的情况下，你可以做任何事，你可以要求任何东西，你就能得到它。我的意思是，一旦人们看到了这种魔力，我认为它真的很有价值。

<details>
<summary>Original English</summary>

**Speaker A**: It's a really good question. I think um I mean, one that you didn't bring up was Sites and I think that was a big part of this launch. There's one one side of Sites that I think people commonly talk about especially on Twitter and stuff or X of like, you know, this sort of like prototyping tool. Actually like we saw that happen with this launch even the the model slider that you guys were referencing earlier, like that was developed almost fully in a site. Like, you know, the the collaboration between design and engineering and product on that was like on a site where we could play with, you know, the the the affordance and and and figure out how it feels and and all of that. Um but the other aspect that that I think is a little bit less talked about is like Sites has like an an artifact for for knowledge work. I was actually talking to someone the other day who was on like our our corporate finance team and like we were mentioning how like now when they have these reports that they're they're working on as a team month-to-month, historically those things were in in slide decks and in spreadsheets and now they're just in sites. Like sites is the mechanism that they collaborate across the team. And the reason is cuz it's like it's like somewhat higher bandwidth. Like, you know, at some these tools like PowerPoint and Excel are like infinitely flexible, but at some point you reach the boundary of like either as a human you may not know how to use some feature or something or the product itself doesn't support it. But in the case of a site you can do anything you ask for anything and you can get that. I mean, once people see that magic I think it's been really valuable.

</details>

**Speaker B**: 对，让我给你看看我的案例研究。这涉及所有热门话题，包括ChatGPT工作，还有5.6、Token亿万富翁和Token最大化，以及Sites和自动研究。我是一个叫Strata的游戏的粉丝。它基本上是一个小棋盘游戏，你用一些物理积木在上面玩……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, let me show you my my case study. This involves all the hot topics including ChatGPT work but also 5.6, token billionaires and token maxing, and sites and auto research. I'm a fan of this game called Strata. It's a basically it's like a little board game that you that you play with a physical blocks that come on top of it

</details>

<!-- chunk 5/11 -->

### 从研究到可交互原型

**Speaker A**: 就像那样。所以周末我拍了大概30张照片，直接扔进ChatGPT。消耗了17亿个token之后，输出了这个网站，带有完整的可玩功能，包括3D方块放置等等。因为它需要实体方块，我需要朋友在上面训练，这样他们才能进步，我才能和他们对战。但与此同时，我也可以做其他事情，比如在上面训练AI。这就是自动搜索，进而进入自动研究。所以你想训练你自己的AI，然后让它们互相自我对弈。我需要设置好两个AI。所以这是AI对AI，它们会自我对弈。显然，AI一开始很糟糕，然后你需要定义一个损失函数，让它变好。我不打算全程监督这些。我当时在圣马特奥参加一个会议。我最终做的是自动研究这个，并创建基准测试。参数实在太多了，我读不过来。所以我开始让它生成一个网站，它创建了这个……这个实验室面板。有没有快捷方式可以访问它创建的网站？

<details>
<summary>Original English</summary>

**Speaker A**: like that. So over the weekend I took like 30 photos and just threw it into ChatGPT. 1.7 billion tokens later outcomes this site with a fully playable thing with 3D block placement and everything. Because it requires physical blocks and I needed friends to train on it so they can get better so I can play against them. But also I could also do things like train an AI on it. And that's your auto search. That gets into auto research. So you want to train your own AIs and then make sure they self play against each other. I need to set both the AIs. So this is AI versus AI and they're going to self play. Obviously that the AI start out bad and then you want to define a loss function and get good. I wasn't going to supervise all this. I was down in San Mateo attending a conference. What I ended up doing was auto researching on this and creating benchmarks. And there was just way too many parameters for me to read. So I started asking it for a site and it's created this lab panel. Where is there a shortcut for a site that it's created?

</details>

**Speaker B**: 呃，你应该能在侧边栏里找到“网站”，在侧边栏顶部。呃，左侧边栏。

<details>
<summary>Original English</summary>

**Speaker B**: Uh you should be able to go in the sidebar to sites, top of the sidebar. Uh left sidebar.

</details>

**Speaker A**: 这个？哦，左边？

<details>
<summary>Original English</summary>

**Speaker A**: This one? Oh, left?

</details>

**Speaker B**: 对，一直滚动到最上面。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, just scroll all the way to the top.

</details>

**Speaker A**: 哦，哦，写着“网站”。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, oh, it says sites.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 哦，找到了。对。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, there you go. Yeah.

</details>

**Speaker B**: 哦。

<details>
<summary>Original English</summary>

**Speaker B**: Ooh.

</details>

**Speaker A**: 所以，它创建了这些网站。嗯，我不认为这完全是我想要的。嗯，但让我给你看看它生成了什么，好吗？我认为作为一个研究产物，嗯，准确沟通正在做的事情非常重要。它输出了这个东西，我后来开始发布它。所以，我把它从“网站”移走了，因为我想要比“网站”提供的更多的数据库和基础设施。嗯，但这就像是一个研究输出，你可以开始摆弄它，试着思考你在训练AI时调整了哪些超参数。嗯，我当时试图找出缩放定律，做各种游戏优化之类的事情。嗯，事实上你可以直接把它作为研究产物抛出来，就像，我不再需要阅读ChatGPT的输出了。我阅读网站的输出。但这也带来了巨大的信息蔓延。看看这个东西有多长。数字太多了。嗯，这相当令人不知所措。所以，从那里开始，我又得着手处理。但从markdown过渡到这个，是一个有趣的转变。

<details>
<summary>Original English</summary>

**Speaker A**: So, it create it creates the sites. Um I don't think this is a it is exactly what I wanted. Um but let me show you what it popped up, right? Like I think as a research artifact, um it is very important to communicate exactly what is being done. Outputs this thing which I eventually started publishing. So, I moved it off of sites because I wanted more database and infrastructure than sites afforded me. Uh but this is like research output that you can start to mess with and like try to think about like what hyper-parameters are you tuning for training your AIs. Uh and like I was trying to make like scaling laws and everything and doing all sorts of like game optimization stuff. Uh and the fact that you can just kind of throw this up as a research artifact, like I no longer need to read ChatGPT output. I read site output. But then there's also huge sprawl. Like look at how long this thing is. There's so many numbers. Uh it is pretty overwhelming. So, then I have to start putting in from there. But it's an interesting transition from markdown

</details>

**Speaker B**: 对，实际上你发布的不再是文档，而是一个完整的功能性网站。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, actually that you're putting out to you're you're putting a whole functional site.

</details>

**Speaker A**: 我认为markdown对人们来说并不是最优的阅读格式，对吧？还不如直接写HTML网站。我不知道。我觉得你可以在这方面做很多定制，对吧？你有技能文件来解释你想要什么。就像我注意到它们相当冗长。我不需要这么多信息。

<details>
<summary>Original English</summary>

**Speaker A**: I think markdown just isn't that optimal for people to read, right? Might as well just write HTML website and I don't know. I think you can do a lot with customizing this, right? You have your skills that explain what you want. Like I noticed they're quite verbose. I don't need a lot of this information.

</details>

**Speaker B**: 冗长。

<details>
<summary>Original English</summary>

**Speaker B**: verbose.

</details>

**Speaker A**: 所以，拥有一个并排的网站的好处是，你可以迭代你想要的和不想要的，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: So, and then the nice thing of having a site side by side is, you know, you just iterate on what you want and what you don't, right?

</details>

**Speaker B**: 对，我不知道这是否让你联想到它在内部是如何运行的。我这样做对吗？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I don't know if that any that triggers any stories for you of how it's run internally. Am I doing this right?

</details>

**Speaker A**: 对，我的意思是，我认为这是我们看到各种团队都在使用的一种工作流程，以前的标准产物是DAC或其他东西，现在变成了一个网站。而且因为网站只是HTML，你可以无限灵活地调整。所以，如果你想让某个东西更突出，在幻灯片里可能会显得格格不入，但在这里你可以让它成为主视觉图，对吧？所以我认为，人们开始意识到，显然还有很多工作要做，才能让这些东西更容易协作。你提到它们很长、很冗长，可以拆分，我相信我们可以对此做些什么。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I mean, I think that this is like a workflow that we're seeing like all different types of teams use where like the canonical artifact that was previously a DAC or something is now becoming a site and like with a site you because it's just HTML you can like it's infinitely flexible and so you know if you want to give more prominence to a certain thing that like in a slide deck would you know feel like it was braid like you can do that you can have it be like the hero image right and so I think that like um people are starting to see that um there's obviously more work to be done to make these things like much more easier easy to collaborate on um you mentioned that they're very they're long and verbose could be broken up I'm sure there's something we can do about that.

</details>

**Speaker B**: 长。

<details>
<summary>Original English</summary>

**Speaker B**: long.

</details>

**Speaker A**: 对，对，但我认为我们开始看到，这是一个非常有趣的格式，嗯，供人们使用，嗯，它比以前拥有的东西灵活得多。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah yeah but I think we're starting to see that like there there is this aspect of this is a really interesting format um for for people to use um that's like much more flexible than than what they were had before.

</details>

### 设计元产品的挑战

**Speaker B**: 我认为你的工作也变得有点“元”了，你不是在设计产品，而是在设计一个用来制造产品的产品。我很好奇你是如何管理这一点的。

<details>
<summary>Original English</summary>

**Speaker B**: I think your job also comes becomes kind of meta you're not designing the products you're designing a product to make products and I'm curious how you manage that.

</details>

**Speaker A**: 我，我认为我们一直在思考的一件事是，当我们审视用户体验时，我们如何平衡简单性和能力。就像你说的，如果我们设计一个产品，它旨在构建各种东西，你可以构建非常多不同的东西，但我们不能把所有这些都摆在你面前，因为你会不知所措。

<details>
<summary>Original English</summary>

**Speaker A**: I I think one thing that we've been like when we look at the UX like that we've that we've been thinking a lot about is how can we balance like simplicity with capability like if we if we're designing a product like you said that like is is made to make a build out of the things right you can build so many different things but we can't put that all in front of you because you'll get overwhelmed.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 所以我们在ChatGPT上也遇到过类似的问题或挑战，但现在尤其如此，因为能做的事情太多了。我认为我们一直在努力寻求的平衡是，如何给用户足够的UI界面，让他们能够表达自己，告诉AI他们需要什么，验证它是否使用了正确的工具、从正确的来源获取信息等等，然后它就能让开。然后，我们如何构建正确的系统，以便我们可以向他们展示，而不是告诉他们能做什么？因为很大程度上，这将取决于他们如何发现下一个用例，以及再下一个用例，如果他们真的想被AI超级赋能的话。

<details>
<summary>Original English</summary>

**Speaker A**: And so we had similar problem or similar challenges even with ChatGPT but especially now like when there's so much that can be done I think the balance that we're constantly trying to strike is like how can we give the user enough of a UI surface where you know they can be expressive they can tell the the agent what they need they can verify that it's using the right tools it's pulling from the right sources etc. but then it gets out of the way and then how can we build the right system such that we can show them instead of telling them what can be done? Because so much of this is going to be like how do they discover the next use case and the next one after that if they really want to you know to to be super powered by the AI.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

### 不同的测试方式，相同的结论

**Speaker A**: 这很有趣。我觉得每个人做事的方式也不同，对吧？我做了这个的类似版本，同一个游戏。我没有拍任何棋盘或规则的照片。我把它扔进去，18分钟53秒后，消耗了大量token，我得到了一个类似的版本。显然没有自动研究那些功能，但你知道，嗯。

<details>
<summary>Original English</summary>

**Speaker A**: It's interesting. I feel like everyone also just has a different way to do it, right? I made a similar version of this, same game. I didn't take any pictures of board or rule game. I threw in at goal, 18 minutes 53 seconds later, a lot of tokens later I've got a similar version. Obviously not with all the auto research and whatnot, but you know um

</details>

**Speaker B**: 你得跟上所有最新趋势。

<details>
<summary>Original English</summary>

**Speaker B**: You got to do all the latest trends.

</details>

**Speaker A**: 对，我用的是Codex，不是Workspace，但这很有趣，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: And yeah, I I did it with uh did it with codex not work, but it's interesting, right?

</details>

**Speaker B**: 对。这显然是GPT图像生成的化身。对游戏设计非常好。很多游戏设计师都非常喜欢GPT图像。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And this is obviously GPT image generating the avatars. Very good for game design. Like a lot of game designers were like really into GPT image.

</details>

**Speaker A**: 我会说，更广泛的结论可能是，我们这样做的主要原因只是为了测试工具，对吧？嗯，这也是在5.6版本发布前的一个测试。我之前在5.5版本上做过这个游戏，对吧？我不再需要……我必须把规则喂给它。这是一个相当小众的游戏。它自己找不到怎么玩。

<details>
<summary>Original English</summary>

**Speaker A**: I I will say like the broader takeaway probably is the reason that we do this is more so just to test the tools, right? Like um this was also a test before 5.6 came out. I had done the game on 5.5, right? The ability for me to no longer need it to I had to feed it the rules. It's a pretty niche game. It couldn't find how to do this on its own.

</details>

**Speaker B**: 哦，对。

<details>
<summary>Original English</summary>

**Speaker B**: Oh, yeah.

</details>

**Speaker A**: 呃，5.6的自动分发。这就是为什么我也非常热衷于测试5.6的能力。

<details>
<summary>Original English</summary>

**Speaker A**: Uh 5.6 auto distribution. That's is why I was also very keen on testing the 5.6 capability.

</details>

**Speaker B**: 但你知道，随着新工作的发布和新事物的出现，这些只是我们测试事物的侧面方式，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: But you know, this is just as as work comes out as new things come out. These are just our sideways to test things, right?

</details>

**Speaker A**: 对。这有点像私人邮件，我猜。虽然它没那么私密。但也很有价值，因为现在你可以把这个发给你的朋友，我的意思是，我就是通过看到这个才了解到这个游戏的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I It's some kind of private email, I guess. Which that is not all that private. But also valuable cuz now you can send this to your friends and I mean I learned about this game through seeing this.

</details>

**Speaker B**: 很难的游戏。他非常厉害。

<details>
<summary>Original English</summary>

**Speaker B**: Hard game. He's very good.

</details>

**Speaker A**: [笑声] 呃，呃，没人和你竞争的时候赢是挺好的。呃，但没错，这是一个经典的强化学习问题，比如自我对弈来引导你的游戏AI。嗯，对，你看工作和个人生活变得多么容易相互渗透，因为我在个人时间做的事情，实际上直接启发了我共事的人，因为我给他们看了。他们就说，“哦，GPT还能做这个？” 我想这就是增长策略。

<details>
<summary>Original English</summary>

**Speaker A**: [laughter] Uh uh it's good to win when no one is competing with you. Uh but yes, it's a classic RL problem of like self play bootstrapping your game AI. Um yeah, you see how easily work becomes personal and personal becomes work because the thing I do for personal, it actually directly informs people I work with cuz I showed it to them. They were like, "Oh, you can do that with GPT?" Which like I I imagine is the growth strategy.

</details>

**Speaker B**: 对。“展示而非告知”是一个重要的部分，你知道，我认为我们还没有完全解决这个问题，比如，向人们展示他们可以用产品做所有事情，而不是试图通过文章、新手引导或其他方式来教导他们。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. The show not tell is a big piece that, you know, I think we've not still not fully cracked of like, you know, showing people all the things that they can do with the product versus like trying to teach that to them through like, you know, articles or onboarding or whatever.

</details>

**Speaker A**: 对，在他们需要的时候出现。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So, meeting them in the moment.

</details>

**Speaker B**: 这对我来说是个职业风险，呃，因为我以前是做开发者关系的，对吧？你的工作就是展示。然后你会想，“你什么意思，你不需要……实际上你的工作是告知。” 嗯哼。然后产品人员会说，“嗯，如果我们的产品足够直观，我们就不需要你了。” 所以。

<details>
<summary>Original English</summary>

**Speaker B**: It's a career risk for me uh because I used to be in developer relations, right? Where your job is to show. And then, you're like, "What do you mean it you you don't you don't need uh it actually your job is to tell." Mhm. And then and then but the product people are like, "Well, we don't need you if our product is intuitive enough." So.

</details>

<!-- chunk 6/11 -->

### 从开发者到知识工作者，再到每一个人

**主持人**: 是啊，这就是模型的魔力所在。你可以根据用户的具体需求来定制“展示”或“告知”的方式，比如他们关心什么、过去做过什么、在采用旅程中处于哪个阶段。所以我认为这将是一个巨大的机会。

<details>
<summary>Original English</summary>

**Host**: Yeah, I mean, that's the magic of the models. So, you can tailor the telling or the showing to like specifically what the user needs, like what what they care about, what they've done in the past, exactly where they are on the adoption journey. So, I think that's like going to be a super big opportunity.

</details>

**主持人**: 现在定制化展示似乎越来越容易了，对吧？人们有不同的使用场景。尽管你说你不想把不同的人分到不同的类别里，但对于不同类别的人来说，这其实也不难做到。但我想问的是，你说你的团队更广泛地关注……你用的词是什么？生产力？

<details>
<summary>Original English</summary>

**Host**: Seems easier and easier now to tailor custom showing, right? People have different use cases. As much as you said you don't want to segment different people into different buckets, right? It's also not that hard to for people that are in different categories. But, the question I guess is you said your team is more broadly on What What was the term you used? Productivity?

</details>

**Reid**: 生产力。

<details>
<summary>Original English</summary>

**Reid**: Productivity.

</details>

**主持人**: 生产力，现在基本上就是工作。是工作吗？还有没有其他我们没覆盖到的用户群体？有没有一群人会用到不同于 ChatGPT、Codex 或工作的东西？大众市场是否还有未触及的领域？

<details>
<summary>Original English</summary>

**Host**: Productivity, which is now work, basically. Is it work? Is there another distribution that we're not hitting? Is there a group of people that will have something different than ChatGPT, Codex, or work? Is there Is there more that the mass isn't targeting?

</details>

**Reid**: 我把它看作一个序列。你知道，愿景是为每个人带来有用的智能体。我们从开发者开始。开发者历来是早期采用者，他们愿意忍受更多的摩擦，去设置环境等等。Codex 就是这样起步的。我认为下一个机会是我们称之为“通用知识工作”的领域，也就是开发者之外的所有其他职能。我认为当你从开发者转向这个群体时，显然会面临固有的挑战，比如我们刚才谈到的“展示而非告知”的问题，让产品更容易理解，引入对这个群体更重要的新能力——这些能力对开发者也很重要，比如 artifacts、computer use 等等。然后，就像我们把从开发者身上学到的东西应用到通用知识工作上一样，下一阶段将是把从通用知识工作中学到的东西带给每一个人，无论他们在生活中做什么。我们已经看到了一些苗头，比如你提到的那个游戏例子，它就处于娱乐、个人生活和职业生活的边界上。我在工作中全职使用 ChatGPT，在家里也用它做所有事情。前几天我还用它来制定膳食计划，然后保存在它的电脑环境里，这样我就可以随时回去查看。现在每个人都这么做了吗？可能还没有，因为我们在努力改进，但最终，我们希望让人们达到那个状态。

<details>
<summary>Original English</summary>

**Reid**: I see it as like a sequencing, like, you know, the the vision is like bring useful agents to everyone. We started with like developers. Like developers historically are like early adopters. They're willing to put up with more friction, set things up, etc. Like that's where, you know, Codex started. I think the next opportunity is like sort of we call it general knowledge work, you know, all the other functions around developers. I think when when you go from developers to this segment, like there's inherent challenges, obviously, with like, you know, this this show not tell thing that we're talking about, um making the product more understandable, um bringing in new capabilities that matter more for for this cohort, the matter for developers, things like artifacts, things like computer use, etc. And then I think like the the same learning is like similarly how we took the learnings from developers and brought it to, you know, general knowledge work, the next stage will be like taking the learnings from general knowledge work and bringing it to everyone, no matter what they're doing in their lives. Um and we're already seeing that a little bit, like this this game example that you have is, you know, something that's it's like on the border of like fun and personal life to to, you know, your your professional life. I use ChatGPT at work full-time at home for everything, like for for whatever I'm doing. I used it the other day to come up with a meal plan and like, you know, save that on um on the like computer environment that it has and something that I can continue going back to. Like, is everyone doing that yet? Probably not because of things that we work on it, but eventually, you know, we want to get people there.

</details>

**主持人**: ChatGPT 生活。

<details>
<summary>Original English</summary>

**Host**: ChatGPT life.

</details>

**Reid**: 对，没错。ChatGPT 烹饪。但我认为那里有很大的机会。我把它看作是我们先在软件工程领域打下了基础，然后我们将把从软件工程中学到的东西应用到知识工作，再从知识工作应用到每一个人。

<details>
<summary>Original English</summary>

**Reid**: Yeah, exactly. ChatGPT cooking. Um but I think there's a lot of uh there's a lot of opportunity there, but I see it as like, you know, we're we're built we built the foundation in in in in software engineering and we're going to take this same learnings that we take from software engineering to knowledge work to knowledge work to to everyone.

</details>

### 高级用户建议：拓宽想象，投入更多上下文

**主持人**: 你有什么给高级用户的建议吗？我觉得有一群人整天都在用，用它做所有事，7x24小时在线。然后在这群人和另一群人之间有点差距，后者只是偶尔用用，或者只是问几个问题。你有什么建议、心得或者推荐吗？或者你发现有什么方法可以帮助弥合这个差距？

<details>
<summary>Original English</summary>

**Host**: Do you have any power user advice? I feel like um there's a group of people that will live it, use it for everything, stay on it 24/7. Yeah. Um and then there's a bit of a gap between that crew and people that, you know, okay, I use it for work, I use it occasionally, sometimes I pipe questions. Uh any advice, any learnings, anything you recommend or just, you know, takeaways that you found that help bridge that gap?

</details>

**Reid**: 我认为有几件事。第一，拓宽你对可能性的想象力真的很有帮助。这对我来说也是一个学习过程。技术发展得太快了，三个月前你还觉得“不可能，模型绝对做不到这个”，现在你就会想“哇，它居然真的能做到了”。比如我们内部正在进行的绩效评估周期。人们总说这是个老生常谈的话题：“我不想写评估，我们用AI来做吧。”但然后评估结果也需要被评价。说真的，以前AI生成的东西基本上就是垃圾，有点用，但效率不高。现在我发现，模型做得比我好得多，尤其是在这个环境下，它可以提取上下文，了解人们在做什么，他们做了哪些事情带来了改变，突出他们取得的成就——这些成就我可能都没注意到。它可以访问所有东西，代码、他们发现的错误、代码审查、Slack消息，所有的一切。所以在这个领域它变得异常强大。而就在六个月前，我们上次做评估周期的时候，我试过用它，但一点用都没有。这次却变得非常有帮助。所以我认为，即使你之前尝试过某件事，也要不断拓展你对可能性的想象边界，这也许是我最大的建议。另一件事是，你投入得越多，尤其是在这个环境下，模型可以访问你电脑或ChatGPT工作区里的所有东西，你可以随着时间的推移创建 artifacts 并保存在你的库中，模型可以持续访问这些内容。你给它的信息越多，无论关于你的生活还是工作，它就会变得越有价值。而且这种价值会以你可能意想不到的方式体现出来，比如它可能会主动从上下文中提取信息，以你从未想过的方式。但它首先需要能够访问这些工具或上下文。

<details>
<summary>Original English</summary>

**Reid**: I think a couple things that I've seen is like one that it really helps to broaden your imagination of what's possible. And this has been a learning even for me, like, you know, the technology has progressed so fast that, you know, there's something that like even 3 months ago like, no way, no way the models can do this. Like, now it's like, wow, it's like it actually can. Like, um We're going through right now that are like review cycle internally and you know people always talked about this as like kind of a a thing that the the models are good at like you know there's a cliche of like okay like I don't want to be writing reviews and like we just use AI to do it but I mean and then it needs to be evaluated as well. Yeah exactly. In all seriousness before it was like just like slop basically and like I I think it was helpful but you know not super productive. Now I found that like the model can do a much much better job than me especially in this environment of like pulling contacts on like what people are up to how they've like the things that they've done to make a difference highlighting like you know wins that they've had that like I might may not even have seen you know it has access to like everything right like the code like you know things that they've caught reviews slack everything and so it's like incredibly powerful in that domain and like just like six months ago the last time we did this cycle like I didn't even I tried using it but it was not at all helpful and this time it's been like incredibly helpful and like so I think continuing to push the the frontier of imagination what's possible even if you tried something before I think is maybe that my biggest piece of advice. The other I guess thing is like the more the more you put in especially in this environment where like you know the model has access to to everything on your on your computer or in chat GPT work like you can create you know artifacts over time and save them in your library and like the model continue having access to those like the more information you give it about whatever domain you're in whether it's your life or your work the more valuable it becomes and it'll become more valuable in like ways that might surprise you like it might pull from contacts in a way that you know maybe proactive in that you might not even have thought about but it needs to have access to those so that those tools or that context first.

</details>

### 关于AI生成绩效评估的礼仪

**主持人**: 我正想谈谈评估这件事，因为那是一个非常敏感的话题。你们是创始人，管理着你们雇佣的人。作为管理者，我非常不愿意发布任何由大语言模型生成的东西，尤其是涉及到对人的评价时，因为这会让人觉得你不在乎。大概在 OpenAI，人们显然更开放地接受被 GPT 评价。但关于这个有没有什么不成文的规定？比如，礼仪是什么？

<details>
<summary>Original English</summary>

**Host**: One thing I was just wanted to talk about the review stuff because I still that's a very sensitive thing and you're you're founders manage people you've hired people as manager myself I'm very reticent to put out any LLM generated things especially when it comes to people cuz it feels like you don't care. Presumably at Open AI people are obviously more open to being basically rated by GBT. Uh but are there any unofficial rules around this? Like what's the etiquette?

</details>

**Reid**: 哦，我的意思是，我认为礼仪是，我绝不会只通过AI写点东西，然后就把它当作对某人的评估呈现出来。我刚才说的更像是收集上下文。

<details>
<summary>Original English</summary>

**Reid**: Oh, I mean I think the etiquette is that like I would never write something via like only via AI and like present it as like a review for someone. What I was talking about is more like gathering context.

</details>

**主持人**: 对，那才是它真正发挥作用的地方。

<details>
<summary>Original English</summary>

**Host**: Yeah. That's the place where it's

</details>

**Reid**: 所以它只是搜索。它是一种智能体搜索。

<details>
<summary>Original English</summary>

**Reid**: So it's just search. It's agentic search.

</details>

**主持人**: 就像智能体搜索，但你知道，你可以比以前更灵活地定制和引导它。因为这里有一个飞轮效应在发生，对吧？因为有了 Codex，人们能够做到这些；因为有了 ChatGPT，更多的人现在能够比以往任何时候都做得更多。如果你能做得更多，也更容易遗漏一些东西。所以我认为我们需要使用同样的工具来跟上人们产生的影响，并了解我们可以在哪里提供帮助。

<details>
<summary>Original English</summary>

**Host**: It's like agentic search, but you know, that you can tailor and steer much more capably than you could before. And cuz like the the thing is it's all there's sort of a flywheel happening, right? Because of Codex people are able to do them because of ChatGPT more people are able to do so much more now than ever before. And if you're able to do so much more, it's easy to miss things as well. Um and so like I think we need to use these same tools to keep up with all the impact that people are having. And and and understand, you know, where where we can be helpful.

</details>

**主持人**: 我认为，显然我经营一家小公司，所以搜索很容易。但在 OpenAI 这样的规模下，有你们在 Slack 里发的那么多消息，你觉得它会遗漏东西吗？

<details>
<summary>Original English</summary>

**Host**: I think that the the thing like obviously I I run a small company, so easy to search. But at the scale of OpenAI, with the mono messages you guys put in Slack, do you think that it misses things?

</details>

**Reid**: 可能会，但我觉得我自己也会遗漏东西。

<details>
<summary>Original English</summary>

**Reid**: Probably, but I think that I also miss things.

</details>

**主持人**: 所以这没关系，对吧？它只需要达到人类水平就可以了。

<details>
<summary>Original English</summary>

**Host**: Like it doesn't matter, right? Like it's it's as it needs to be human level.

</details>

**Reid**: 是相对的，对吧？有时候它能找到你找不到的东西，这很好，对吧？比如现在，我的 Codex 系统提示词设置方式是，我的每个项目都有一个秘密的独立笔记文件（notes.md）。它会自动把学到的东西写进去。然后全局的那个可以从所有这些笔记中提取信息。所以有时候它会说：“哦，你四个月前做过这个项目，这是我们当时的一条笔记。”然后它随机地把这个信息拉回到当前的上下文中，这是我永远不会做、也从未想到过的。我就会想：“好吧，这有点超人类了，对吧？”就像那些我本不会想到的东西，它却帮我记住了。

<details>
<summary>Original English</summary>

**Reid**: relative, right? Yeah. Sometimes it's nice when it finds things you wouldn't, right? Like right now my Codex system prompts they're set up in such a way that every project I have has a secret separate notes MD. And it just writes learnings to there. And then the the global one can pull from all these. So sometimes it'll be like, "Oh, there's this project you did like 4 months ago. Here's a note that we had." And it it randomly pulls it back in the context that I would never do I haven't thought about. And I'm like, "Okay, this is quite superhuman, right? Like stuff that would And you know, it'll save

</details>

<!-- chunk 7/11 -->

### 从代码补全到工作助手：ChatGPT Work 的诞生

**Speaker A**: 就像，花好几个小时去分块处理东西，或者找一些已经有人做过的东西。我觉得，虽然它可能会漏掉一些东西，但它在找到东西的时候非常有用。而且我有一个非常，你知道的，不是超级工程化的解决方案。就是一些 Markdown 文件，随时可以被拉取使用。

<details>
<summary>Original English</summary>

**Speaker A**: like hours on chunking of stuff or find something that's already been done. I'm like, as much as it might miss stuff I would do, but it's very useful when it finds stuff. And I have like a very, you know, non-super engineered solution to this. It's just markdown files that get pulled whenever they want.

</details>

**Speaker B**: 是的，我其实有个关于这个的有趣轶事。就像最近为了准备这次发布，你知道的，团队已经，你知道的，真的全力以赴了好几个月。在那段时间里，Slack、文档和其他地方有大量的对话和讨论。然后，呃，团队里的一位成员设置了一个，呃，定时任务，就像一个自动化程序，去查看所有正在发生的事情，然后生成最好的梗图，并发布到我们一个共享频道里。这件事有两个很酷的地方。第一是，我觉得这些模型，你知道的，随着时间的推移，实际上开始变得有趣了。而你知道的，一年前，情况完全不是这样。第二点是，就像你刚才说的，它们能以令人惊讶的方式找到你可能没想到的东西，并建立起你可能没想到的联系。这真的有助于梗图的生成，因为你可以看到一些真正让你感到惊讶的东西，然后，呃，以那种方式变得有趣。所以，是的，我的意思是，这显然不是这项技术最高产的应用，但它确实体现了正在涌现的一种能力，那就是发现你原本不知道的信息。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I actually have a funny anecdote about this. Like recently gearing up to this launch, you know, the team has been, you know, really cooking on it for for for a couple months and over that time like there's so much conversation and chatter going on in Slack and Docs and elsewhere. And uh one one of the members of the team set up this um scheduled task like automation to like look at everything that's going on and like come up with the best memes and then post in one of our shared channels. And like there are two cool things about this. Like the first is like I think the models are you know, over time like actually starting to become like funny. Whereas like you know, a year ago like that was not at all the case. The second is that it was what you were saying like they find things that in surprising ways that you may not have not have thought of and like create connections that you may not have thought of and that really helps with like the meme generation because then you can see something that you know, genuinely surprises you and then and um is funny in that way. So yeah, I mean obviously that's like not like the most productive uh use of this of this technology, but it does it doesn't cover this like this capability that's emerging which is just like defining information that you otherwise would not know.

</details>

**Speaker B**: 说到这次发布，我，我觉得，呃，我已经说过这是很长一段时间以来最成功的一次发布。我个人认为甚至比 5.0 还要成功。你现在宣布有 1000 万用户。感觉有什么不同吗？你经历过很多次发布了。我觉得这像是一个 culmination（集大成之作）。

<details>
<summary>Original English</summary>

**Speaker B**: Talking about the the launch, I I think uh I have pretty much said this is the most successful launch in a long time. I think even more successful personally than 5.0. And you're announcing 10 million users. Does it feel different? You've been through a lot of launches. I think it feels like a culmination.

</details>

**Speaker A**: 嗯，我觉得有两件事。第一，这感觉像是一个 culmination，就像我之前提到的，这是我们长期以来的愿景。就像我说的，我们在内部看到了 Codex 的魔力，然后我们非常兴奋能把它带给更多人，看到它发挥作用，看到我们达到，你知道的，你提到的那个数字所代表的覆盖目标，我觉得这非常了不起，而且，而且超级令人兴奋。另一面是，我们还有很多事情要做。那也同样令人兴奋。就像，你知道的，整个 ChatGPT，这个产品，你知道的，几乎每个人都把它等同于 AI，并且喜爱它，你知道的，拥有数亿用户。所以，1000 万用户真的很酷，但是，我们需要让所有人都能用上它。我们需要每个人都感受到这种魔力。嗯，所以这是接下来的步骤，但是，是的，我对目前的进展以及未来的机会感到无比兴奋。

<details>
<summary>Original English</summary>

**Speaker A**: Well, I think two things. One it feels like a culmination like I was mentioning earlier like this like vision vision that we've been on for a long time. Like I said, we saw the magic of Codex internally and then we're like extremely excited to bring this to many more people and to see it working to like see us reach you know, the distribution goal in um numbers that you mentioned like I think that's like huge and and and super exciting. The flip side of that is like there's so much more to do too. Like that's also really exciting. Like you know, ChatGPT as a whole like this product that you know, everyone almost equates to AI and like loves you know, has hundreds of millions of users. And so like 10 million is really cool, but like we we need to get this to everyone. Like we need everyone to feel this magic. Um and so that's the next step from here, but yeah, I think extremely pumped about how it how it's going so far and then the opportunities.

</details>

**Speaker B**: 呃，太棒了。呃，我还想问一下，因为我一直在密切关注这个数字，它在某个时候从单纯的 Codex 用户转变成了 Codex 加上 ChatGPT Work 的用户。显然，因为用的是同一个框架，重点就在于你不能单独评论。你们大概有十亿，呃，ChatGPT 用户吗？是不是一下子就跳到 10 亿了？就像，这难道不是 ChatGPT 上的默认设置吗？还是说不是？

<details>
<summary>Original English</summary>

**Speaker B**: Uh awesome. Uh I did want to also, because I have I've I've been tracking the the number closely, it transitioned at some point from just Codex users to Codex plus ChatGPT work. Obviously, because the same harness, the whole point is that you don't you you can't uh comment separately. Do you have roughly a billion um ChatGPT users? When did it just jump to 1 billion right away? Like, isn't that the default on ChatGPT or no?

</details>

**Speaker A**: 我们不会默认让你使用 ChatGPT Work，如果你用的是 ChatGPT 免费版的话。是的。它目前也只对付费用户开放，而且我认为这有一个过程，比如，你知道的，教育用户这个产品的价值是什么，让他们尝试，从他们的反馈中学习，并随着时间的推移让它变得更好。但是，我的意思是，目标是，你知道的，让尽可能多今天喜爱 ChatGPT 的人，去感受，感受 ChatGPT Work 的力量，但我认为这将是一个过程。

<details>
<summary>Original English</summary>

**Speaker A**: We don't default you into ChatGPT work if you're on ChatGPT or free. Yeah. It's also only available to it to paid users right now and I think there's like a process if you know educating users of what is the value of this product, having them try it, learning from their feedback, and making it better over time. But, I mean, the goal is to, you know, get as many of people who who love ChatGPT today to like feel the feel the power of ChatGPT work, but I think it'll be a a journey.

</details>

**Speaker B**: 是的。而且 Codex 在可预见的未来仍将作为一个品牌存在。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And Codex will will still be alive as a brand for the foreseeable future.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 嗯，我们只需要在 UI 方面根据需要在这两者之间切换。

<details>
<summary>Original English</summary>

**Speaker B**: Um and we'll just toggle between them as as as needed for UI stuff.

</details>

**Speaker A**: 是的，我认为这一点甚至比那更有力。就像，我认为我们完全打算，你知道的，像对待开发者一样，你知道的，他们长期以来一直是我们核心市场，而且我们还可以做更多的事情来让 Codex 专门为，呃，软件开发变得更好，我们将继续这样做。这完全不会削弱这一点。如果有的话，它应该会增加像 Codex 这样的工具的实用性，因为现在，你知道的，你可以在编写一个函数、创建一个 artifact（工件）或者，你知道的，在你的代码库中进行搜索之间无缝切换。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think it's even even stronger point than that. Like, I think we fully intend to like, you know, treat developer like developers have been, you know, core market for us for so long and like there's there's so much more that we can do to make Codex great specifically for um software development and we'll continue to do that. This doesn't take away from that at all. If anything, it should increase the utility of something like Codex because now like you can move seamlessly between writing a def to creating an artifact or, you know, doing a search over your code.

</details>

**Speaker B**: 我确实想知道这些术语在多大程度上会渗透给非技术用户。比如，他们是否必须学会说“artifacts”才能得到 artifacts，或者，你知道的，

<details>
<summary>Original English</summary>

**Speaker B**: I do wonder how much this terminology leaks to the non-technical user. Like, do they have to learn to say artifacts if I want artifacts or, you know,

</details>

**Speaker A**: 这很有趣，我们在内部称之为 artifacts，因为团队就是这么叫的，但在外部，没人这么说。没人管它叫 artifact。但是，我认为人们通常，你知道的，会用他们习惯的方式来描述事物，对吧？所以，如果，你知道的，ChatGPT Work 擅长创建幻灯片，他们就会说 ChatGPT Work 擅长创建幻灯片，而这实际上正是我们想要的。

<details>
<summary>Original English</summary>

**Speaker A**: It's funny like we call artifacts internally cuz that's what the teams call them, but like externally like no one says that. No one calls it an artifact. I But, I think that people like often like describe things whatever they're used to, right? So, if, you know, ChatGPT work is good at creating slides, they'll say ChatGPT work is good at creating slides, and that's actually what we want.

</details>

### 从 Open Claw 到 ChatGPT Work：个人代理的演进

**Speaker B**: 另一个大事，我的意思是，现在是 2026 年 7 月。另一件大事发生在 OpenAI，那就是 Open Claw，我认为这是很多人第一次真正将代理用于个人事务，同时也以同样的方式跨界到工作领域。据我所知，Open Claw 仍然是独立的，但你是否经历过你自己的“Open Claw 时刻”？你有没有从 Open Claw 那里学到什么经验，应用到 Codex 上，或者反过来？

<details>
<summary>Original English</summary>

**Speaker B**: One big another, I mean, it's July of 2026. One big thing that also happens in for opening AI was open claw, and that's I think a lot of people's first time really maxing agent for personal stuff, but also crossing over to work in in that sense same way. As far as as far as I understand, open claw is still independent, but did you go through your own open claw moments? Were there any lessons you took from open claw to Codex or back, whatever?

</details>

**Speaker A**: 我认为有很多灵感。我确实经历过我自己的“Open Claw 时刻”。我，呃——

<details>
<summary>Original English</summary>

**Speaker A**: I think there's a lot of inspiration. I did go through my own open claw moment. I um

</details>

**Speaker B**: 是的，讲讲这个故事。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, tell the story.

</details>

**Speaker A**: 我和我的，呃，我的妻子设置了一个 Open Claw，试图管理我们房子里的一切。虽然东西不多，但它实际上非常有用。它给了我们一个日历，开始，你知道的，为我们创建事件之类的。后来，运行它的笔记本电脑坏了，然后我们就再也没有机会重新用起来了，但那里有很多灵感。就像，呃，你知道的，在 ChatGPT Work 的网页和移动端，你可以访问一个持久的计算机环境，在那里，你知道的，你可以存储文件，这些文件会在会话之间保留。其理念就是能够实现这样的用例。呃，我们团队的一位成员实际上就用 ChatGPT Work 来做他们以前用 Open Claw 做的事情，我觉得这已经完全过渡了，这就像是，呃，工作计划和饮食追踪，呃，这再次说明，这有点像“工作”性质的事情，对吧？它不一定是工作，但它属于个人生产力这个领域。但它拥有所有相同的基本功能。比如，它有定时任务。它有能力在文件系统上存储文件。它有能力随着时间的推移引用这些东西。呃，所以你开始看到相同类型的用例出现，这真的很酷。

<details>
<summary>Original English</summary>

**Speaker A**: Me and my um my my wife like set up an open claw to like try to manage everything in our house. Not that there's like a ton, but it was like actually quite useful. It gave it a calendar, started, you know, creating events for us and stuff. At some point the the laptop they were running on it died, and then they never got a chance to to pick it back up, but there's a lot of inspiration there. Like, um you know, in ChatGPT work in web and mobile, like you you get access to this like persistent computer environment where, you know, you can store files, and those files stay around between sessions. And the idea is to be able to enable use cases like this. Um one of the members of our team actually uses ChatGPT work for what they used open claw for them before, and I feel like it has like completely transitioned, which is like uh work out planning and like meal tracking, um which again, it's like a worky thing, right? It's like not work necessarily, but it's like in this personal productivity space. But it has all the same primitives. Like it has scheduled tasks. It has the ability to store files on a file system. It has the ability to like reference those things over time. Um and so you start to see the same types of use cases emerge, which has been really cool.

</details>

**Speaker B**: 有没有一个点，ChatGPT Work 会完全取代 Open Claw？显然，它们是独立的，所以——

<details>
<summary>Original English</summary>

**Speaker B**: Is there a point that ChatGPT work completely replaces open claw? Obviously, they're independent, so

</details>

**Speaker A**: 是的，我的意思是，我，我，我对此并不了解，所以我不能谈论 Open Claw 的路线图，但我，我不这么认为。我认为，你知道的，总会需要像那个团队构建的这样令人难以置信的开源技术，而且我认为我们可以从产品中汲取灵感，并且，你知道的，ChatGPT，我认为听说过和使用过 ChatGPT 的人比使用过 Open Claw 的人多得多，如果我们能汲取 Open Claw 的魔力并将其带给这些人，我认为那将是一个成功。我认为，在 ChatGPT Work 方面，我们强烈认为的一点是，核心体验是，你来到这个产品，与这个代理进行对话，开始一个会话，随便你怎么称呼它，而这个产品的魔力在于，你可以在那一刻做任何事情，我们希望创建一个产品，让你无需点击按钮或去其他地方，就能在一个地方获得你，你知道的，你的财务应用或任何其他产品中存在的任何功能。这就是目标。就像，它会是——

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I mean, I'm I'm I'm not close to it, so I can't speak to the the open claw road map, but I I don't think so. I think that there's going to be, you know, there's always a need for like this like incredible like open source technology that that team has built and I think that we can draw inspiration in the product and you know, chat GPT I think many more people have like heard about and used chat GPT than have you have used open claw and if we can take the magic from open claw and bring it to them, I think that'll be a success. I think that like one thing on the chat GPT work side that we feel strongly about is that like the core experience is that you come to this product and you have a conversation, start a session, whatever you want to call it with this agent and the magic of the product is that you can do anything in that moment and we would like to create a product where you don't have to click a button or to go to a different place, whatever and you can get whatever functionality exists in you know, your your finances app or or any other product like in this in this one place and so that's the goal. It's like it'd

</details>

<!-- chunk 8/11 -->

### 可扩展系统与插件生态

**Speaker A**: 我们想要一个可扩展的系统，带有插件，让你能连接到你需要的工具，从而完成某项财务任务。比如，如果你在做科学类工作，我们有一种能力可以扩展系统，让你编写技术代码，并且它性能良好。我们支持的产品中，总会有一些在那些方面是同类最佳的，但我们希望尽可能多的魔力都集中在核心体验中。

<details>
<summary>Original English</summary>

**Speaker A**: We want an extensible system with plugins where you can connect to the tools that you need in order to be able to accomplish like a financial task where you can, you know, if you're doing like science work like we have an ability to like extend the system in such that you can like write the tech and and it performs well. There'll always be like products that we support that are best in class at those things, but we want as much of the magic as possible in that core experience, you know.

</details>

**Speaker B**: 你觉得你现在能用ChatGPT Finance做以前用Wolfram做的一切事情吗？

<details>
<summary>Original English</summary>

**Speaker B**: Do you think that you can do everything you used to do with Wolfram's in chat GPT finance?

</details>

**Speaker A**: 我其实试过。我的意思是，ChatGPT目前还不能替你托管现金和资产，所以那部分还不行，还没到那一步。但我的意思是，像退休规划、财务规划、预算这类事情，我在那边的时候我们就在研究，现在有了Finance插件，这些在ChatGPT上都能实现，所以至少对我来说，那部分已经被替代了。

<details>
<summary>Original English</summary>

**Speaker A**: I actually tried it. I mean, like chat GPT doesn't yet custody cash and and assets for you, so so that part no, not yet, but I I mean, there's like a whole component of like retirement planning and um sort of like financial planning and budgeting and stuff that that um we were looking into when I was there and like with the finances plugin like that's all possible with chat [laughter] GPT today, so um I feel like at least that component's replaced for me.

</details>

**Speaker B**: 我还没真正接入过。我有点害怕看到答案。

<details>
<summary>Original English</summary>

**Speaker B**: I haven't really plugged it in yet. Um I'm somewhat scared to look at the answer.

</details>

**Speaker A**: [笑声]

<details>
<summary>Original English</summary>

**Speaker A**: [laughter]

</details>

**Speaker B**: 说实话，健康和财务也是同样的原因。我就觉得，我不知道，我不知道。

<details>
<summary>Original English</summary>

**Speaker B**: Like that's honestly like the same reason for health and finances. Like, I'm like, I don't know. I don't know.

</details>

**Speaker A**: [笑声]

<details>
<summary>Original English</summary>

**Speaker A**: [laughter]

</details>

**Speaker A**: 它真的很好。我的意思是，真的很酷。我们之前聊过一点关于智能体搜索的方面，但真的很酷的是，在传统的用户体验里，你想给用户更多权力，就需要添加更多的旋钮、按钮和花哨功能。比如那些财务和预算应用，总有一堆不同的过滤器和搜索栏之类的。但现在，只要正确连接了正确的数据，你想要什么都可以。你可以问任何问题，输入那个框里，然后得到答案。我觉得这非常强大。

<details>
<summary>Original English</summary>

**Speaker A**: It's really good. I mean, it's it's really cool how I mean, we were talking about like the agentic search aspect a little bit earlier, but like it's really cool how like, you know, in in conventional UX, like if the more power you want to give to a user, the more like knobs and bells and whistles you need to add. Like, you know, for like these finance and budgeting apps, like there's always like a bunch of the different filters and like search bars and stuff like that. But like now like with the right connect connectivity to the right data, you can have whatever you want. You can ask any question you want and and into that box and and get the answer and I think that's super powerful.

</details>

**Speaker B**: 我觉得能集中在一个空间里也很好，对吧？你有不同的健康应用。我有一个智能秤的、一个手表的，所有这些不同的东西。能集中放在一个地方就很方便。

<details>
<summary>Original English</summary>

**Speaker B**: I think it's also nice to just have it centralized in one space, right? You have different health apps. I have one for a smart scale, a watch, all these different things. It's just nice to centrally collocate it.

</details>

### 数据架构与智能体

**Speaker A**: 这其实就是Open Claw整个理念的一部分，对吧？你会有一个个人操作系统，而ChatGPT显然想成为那个系统。我确实认为，仅仅依赖即时拉取数据——比如通过MCP、CLI、API，无论你怎么做——仍然不够。我有一点数据工程的背景。你仍然需要一个数据仓库，或者某种缓存层或语义层。你有这种感觉吗，还是你们已经有了？

<details>
<summary>Original English</summary>

**Speaker A**: Which is, you know, part of the whole thing of Open Claw, right? Like that that you would have a personal OS, which presumably ChatGPT wants to become. I do think that just relying on like just-in-time pulling of data for, let's say, through via MCP, CLI, API, whatever you whatever you do, still not enough. Like I I like I come from a bit bit of a data engineering background. Like you still want like a data warehouse or some kind of caching or semantic layer. Um, do you [snorts] feel that or do you already have that?

</details>

**Speaker B**: 我不能透露所有细节，但我觉得这取决于访问模式，对吧？比如，如果你想立即得到答案，那么如果要从所有这些来源拉取数据，确实很难做到。但是，我们想在ChatGPT上实现的很多用例，并不一定需要你立刻得到结果。它更像是一个你希望智能体去完成的任务，这需要一定的时间。而且，现在有了程序化工具调用之类的功能，其中一些时间，以及子智能体之类的，有些部分是可以并行处理的。所以，我认为MCP和调用这些第三方服务的可能性上限已经被大幅提高了。我们对此非常兴奋。

<details>
<summary>Original English</summary>

**Speaker B**: I can't speak to like all the details on how everything works, but I think it depends on the access pattern, right? Like, if you want to answer immediately, then yes, it's very difficult to do that if you need to pull from all of these sources. But, a lot of the like use cases that we want to enable on ChatGPT work aren't necessarily something that you need immediately. It's more like a task that you want the agent to go and do. And that that's going to take a certain amount of time. And, you know, with things like programmatic tool calling and stuff now, like some of that time and sub agents and stuff like some of that is also parallelizable. And so, it's possible I I I think it's very possible that there's a the ceiling on what can be done, you know, with MCPs and like calling out to these third party services has been raised substantially. So, we're really excited about that.

</details>

**Speaker A**: 你提到了子智能体。我得深入问一下。Ultra是一个新模式。ChatGPT本身有一些特殊的交互方式来展示这些智能体。说实话，你不能对它们做太多操作，只能看着。

<details>
<summary>Original English</summary>

**Speaker A**: You mentioned sub agents. I I I got to double click on that. Ultra is a new mode. Um you have special affordances in ChatGPT itself to show off the the agents. Can't really do much with them to be honest. I just just just watch.

</details>

**Speaker B**: [笑声]

<details>
<summary>Original English</summary>

**Speaker B**: [laughter]

</details>

**Speaker A**: 你的经验是什么？有没有什么设计问题是你想提醒其他使用子智能体的开发者的？

<details>
<summary>Original English</summary>

**Speaker A**: Um what have been your what have been your experiences? Any design issues that you would call out to other builders building with sub agents?

</details>

**Speaker B**: 我觉得这又回到了我之前提到的平衡问题。既要向开发者展示工具的强大，又要创建足够的抽象层以免让他们不知所措。我认为对于子智能体，我们想展示的是，你可以把一个有很多并行路径或者很复杂的任务交给子智能体处理，这个产品就是为你准备的。模型可以完成这些目标，或者尝试完成这些目标。所以这就是我们在产品中展示它们的目的，也是我们设计的方向。还有另一个迭代版本，你可以看到它们具体在做什么之类的，但我觉得那可能会因为信息过载而让人不知所措。所以这是我们目前做出的一个双刃剑式的权衡。

<details>
<summary>Original English</summary>

**Speaker B**: I think it's sort of goes back to the balance that I was raising earlier. Felt like, you know, showing builders the power of the tool, but also creating enough of an abstraction to not overwhelm them. I think with sub agents the thing that we wanted to show is that you can take a task that, you know, has many parallel tracks or um is is complicated in a way that, you know, sub agents can handle and this product is for you. Like the model can can accomplish those goals or try to accomplish those goals. Um and so like that's the point of like showing them in the product and and that's where we we've gone with the design. There's another, you know, iteration of this where like you can see exactly what they're doing and and things like that, which I think is like, you know, could could verge on like overwhelming um with information. And so this is like the double edged trade off that we made for now.

</details>

**Speaker A**: 你们确实显示了相当多的转录内容。

<details>
<summary>Original English</summary>

**Speaker A**: you you you do display quite a lot of transcripts.

</details>

**Speaker B**: 对，对。

<details>
<summary>Original English</summary>

**Speaker B**: Right. Right.

</details>

**Speaker A**: 你觉得你想显示得比那更多吗？

<details>
<summary>Original English</summary>

**Speaker A**: I think it's you want to display more than that?

</details>

**Speaker B**: 不，不，这样挺好。

<details>
<summary>Original English</summary>

**Speaker B**: No, no, it's fine.

</details>

**Speaker A**: 有些人可能想要更多。我就是那种会把很多东西扔给目标的人，而且几乎每个目标我都会告诉它使用子智能体。听起来有点多余，对吧？但每次我都会说，“好的，尽可能使用子智能体。”我有很多朋友也推荐并这样做。而有时候我和另一些人聊天，他们会说，“好的，我希望你在这个子任务中使用子智能体。”我敢肯定他们会希望看到它们是如何被使用的。对我来说，主要是两件事：第一是净时间效率，分散到子智能体上；第二可能是成本，对吧？不用又大又贵的模型，把任务卸载给很多更小、更便宜的模型。有些人想要那种控制级别。所以，如果你做的事情有重复性，比如我想构建一个每天都能持续做这件事的东西，我可能想进去微调这里的子智能体、那里的子智能体。你可以看到两者，但我想我没记错的话，默认是隐藏的。有一个下拉菜单，我经常是，“好的，我就一直开着它。”

<details>
<summary>Original English</summary>

**Speaker A**: Some some people could want more. So, I'm one of those people that will basically throw a lot of stuff at goal and pretty much every goal I'll tell it to use sub agents. Seems redundant, right? But every time I'm like, "Okay, use sub agents where possible." And I have a lot of people a lot of friends that recommend and do the same. Whereas I'll sometimes talk to people that are like, "Okay, this is where I want you to use sub agents for this sub task." And I'm sure they would appreciate seeing into how they're being used. For me it's primarily like two things, right? One is net time efficiency. So, span out across sub agents. Two is probably cost, right? Uh don't use big expensive model, offload to a lot of smaller, cheaper models, and some people want that level of control. So, if you have repetition in what you're doing, right? Say I want something built where I want it to consistently do this every day, I might want to go in and fine-tune subagents here, subagents there, so you can see both, but I think if I'm not mistaken, it's hidden by default. There's a drop-down that goes a lot where I'm like, "Okay, I'm just going to keep it on."

</details>

**Speaker B**: 你可以改变它们使用的模型吗？

<details>
<summary>Original English</summary>

**Speaker B**: You can You can change the model that they use?

</details>

**Speaker A**: 我知道我可以引导它们。我会说，我知道Anthropic在Claude Code里提供了这个功能。你可以告诉Fable使用Sonnet或Opus，让Sonnet作为子智能体，所以这是很简单的事情。你告诉它用Sonnet来扩展子智能体，它更便宜、更快。我猜如果现在没有这个功能，以后也可以加上，但我认为有一方面是……

<details>
<summary>Original English</summary>

**Speaker A**: I know I tell them to be steered. I'll say my I know Anthropic offers this in Claude code. You can tell Fable to use Sonnet or Opus to use Sonnet as a subagent, so pretty trivial thing, you know, you tell it to span out subagents with Sonnet, you know, it's cheaper, faster. I would assume if it's not there, it could be built there, but I think there's a side of

</details>

**Speaker B**: 太多开关了。

<details>
<summary>Original English</summary>

**Speaker B**: Too many toggles.

</details>

**Speaker A**: 嗯。其实不是开关。你只是在聊天里告诉它。我用的方式就是通过提示词，对吧？我认为除非你是为重复性任务构建的，否则这会被抽象掉。所以，如果我在构建一个东西，比如播客准备工作，对吧？研究人物，做非常深入、广泛的研究，我可能想把它配置成用更便宜、更快的模型专门做网络搜索。我可以看到一个世界，你两者都想要。我认为目前的默认设置其实相当不错，它是隐藏的，但你可以下拉获取更多已完成任务的信息。我知道人们在5.6发布时讨论了很多。这个东西喜欢用很多子智能体，导致ChatGPT应用直接崩溃，因为它太耗处理器了，但是……

<details>
<summary>Original English</summary>

**Speaker A**: Mhm. It's not a toggle, actually. It's just a You tell it in chat. The way I do it is prompt it, right? And I think this is something that gets abstracted unless it's something you built for repetition, right? So, if I'm building something, say that's a podcast prep, right? Research into people, do a very, very deep, extensive research, um that I might want to configure to cheaper, faster model just for web search, right? I can see a world in which you want both. I think the default is actually pretty good right now, where it's hidden, but you can drop down and get some more info into what's done. I know people talked a lot about it on 5.6's launch. Uh this thing loves to use a lot of subagents and causes the ChatGPT app to just crash because it's so processor heavy, but um

</details>

**Speaker B**: 那么，你个人的体验是什么？是啊，我的意思是，我还没遇到过因为子智能体而崩溃的情况。

<details>
<summary>Original English</summary>

**Speaker B**: So, what is your personal experience? Yeah, I mean, yeah, you know, I haven't had it crash from subagents.

</details>

**Speaker A**: 我也没有。我们都有大笔记本电脑，但我知道有人提过。这是一个讨论话题，我们没有遇到同样的问题，但这也是另一种氛围评估，对吧？人们会说，“天哪，运行这么多子智能体太疯狂了。”而我会说，“我觉得这没问题。我觉得这很好。”但只是人们提出来的一些事情。

<details>
<summary>Original English</summary>

**Speaker A**: I I haven't either. I have We both have big laptops, but I know I know people brought it up. There was a topic of discussion that we didn't see the same, but it is another vibe eval, right? People are like, "Okay, the amount of subagents all this running is crazy." And I'm like, "I think this is okay. I think it's good, but just stuff people bring up.

</details>

**Speaker B**: 我认为当我们发布产品时，我们也没有对Ultra 4是谁以及他们应该在什么时候使用它给出明确的意见。从那以后，我们做了一些改变，比如要求你手动开启它，并在高级设置里找到它，因为那才是它该在的地方。

<details>
<summary>Original English</summary>

**Speaker B**: I think when we launched the product too, we we weren't as opinionated about like who is Ultra 4 and like when when should they be using it and since then we made some changes to like, you know, require you to turn it on and and and find it in the advanced setting cuz that's who it is

</details>

<!-- chunk 9/11 -->

### 关于记忆系统的讨论

**Speaker A**: 这是为高级用户准备的，他们明白会发生什么，因为根据你的使用场景，它也可能消耗更多你的额度。

<details>
<summary>Original English</summary>

**Speaker A**: for. It's for like power users who understand what's going to happen because it also, you know, depending on your use case can can use more of your your limits as well.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

**Speaker A**: 所以我认为这就是我们收到很多反馈的原因。

<details>
<summary>Original English</summary>

**Speaker A**: So that's where I think a lot of the the feedback was coming for us.

</details>

**Speaker B**: 好的，重置额度。

<details>
<summary>Original English</summary>

**Speaker B**: Okay, reset the limits.

</details>

**Speaker A**: [笑声]

<details>
<summary>Original English</summary>

**Speaker A**: [laughter]

</details>

**Speaker B**: 总是重置额度。

<details>
<summary>Original English</summary>

**Speaker B**: Always reset the limits.

</details>

**Speaker A**: 嗯，你知道，今天我们重置是因为我想换个话题，聊聊框架的最后一个部分：记忆。最近很多人都在评论记忆功能。ChatGPT 的新记忆系统以前很糟糕，不太好用。然后这位老兄也说了基本相同的话。还有 Samir，你应该和他一起工作过，也在谈论记忆。这方面你能说些什么？

<details>
<summary>Original English</summary>

**Speaker A**: Well, it's you know, today we're resetting because it is I want to change topics to one last piece of the harness, memory. A lot of people are commenting on memory recently. ChatGPT's new memory system used to suck is not very good. And then this guy also basically the same thing. And Samir who you presumably work with talking about memory. What can you say there?

</details>

**Speaker B**: 我认为，你知道，Samir 和团队，以及研究团队，随着时间的推移做了大量的更新和改进。我觉得当我和朋友、家人聊起他们喜欢 ChatGPT 的什么时，他们觉得 ChatGPT 了解他们，感觉他们的 ChatGPT 就是他们自己的 ChatGPT，这大概是最重要的一点。

<details>
<summary>Original English</summary>

**Speaker B**: I think that, you know, Samir and the team have made a ton of and and and the research teams have made a ton of updates and and improvements over time. I think when I talk to friends, family members about what they love about ChatGPT, like the fact that it knows them, that they feel like their ChatGPT is is their ChatGPT, I think comes up probably

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 排名第一。而且 ChatGPT 工作版默认在云端运行，所有对话都继承自 ChatGPT 的记忆，所以它会了解你的上下文。它还能将信息写回这个记忆。

<details>
<summary>Original English</summary>

**Speaker B**: number one. And ChatGPT work in the in the cloud like by default all conversations like inherent from ChatGPT memory so you'll know they'll know context about you. They'll also be able to write back to this memory.

</details>

**Speaker A**: 就像一小段文本，对吧？比如你写东西的时候会告诉我，对吗？

<details>
<summary>Original English</summary>

**Speaker A**: With the like a like a like a small text right. Like you tell me when you're writing, right? Is it

</details>

**Speaker B**: 不，它是我们推出的同一个记忆 V3 系统的一部分。

<details>
<summary>Original English</summary>

**Speaker B**: No, it's part of the same like memory V3 system that that we we launched.

</details>

**Speaker A**: 你说 V3 是什么意思？是的。

<details>
<summary>Original English</summary>

**Speaker A**: What do you mean V3? Yeah.

</details>

**Speaker B**: 所以我认为这非常强大，因为，你知道，从 ChatGPT 到 ChatGPT 工作版，感觉就像是我已经使用这个产品多年所做事情的延伸。嗯，这太棒了，看到人们认可这里的改进也很棒。

<details>
<summary>Original English</summary>

**Speaker B**: So I think that's been really powerful because, you know, going from ChatGPT to ChatGPT work feels like an extension of what I've already been doing with the product for sometimes many years. Um so that's been awesome and it's awesome to see that like people are recognizing um the the improvements here.

</details>

**Speaker A**: 那么，这基本上是一个检索问题，对吧？比如你是否检索到了正确的东西？你是否过度关注了错误的东西？是误报更多还是漏报更多，你明白我的意思吗？更大的问题是什么？

<details>
<summary>Original English</summary>

**Speaker A**: Is there So it's it's basically a retrieval problem, right? Like are you retrieving the right things? Are you over focusing on the wrong things? Is there like uh more false positive or false negative, you know, if if that makes sense? Like what's the bigger problem?

</details>

**Speaker B**: 嗯，我不直接负责记忆功能，所以很难确切地说哪个问题更大，但我认为你说得对。我觉得，你知道，这有两个方面。一方面是确保它了解关于你的事情，另一方面是拥有足够的情商，在合适的时机主动或以一种积极而非消极的方式让你惊喜地提起这些事情。嗯，所以我认为这是一个非常有挑战性的问题，但也是我们觉得有巨大机会去解决的事情，这也是我们大力投资的原因。

<details>
<summary>Original English</summary>

**Speaker B**: So, I don't work on memory directly, so it's hard to say what the bigger problem is with like certainty, but I I think you're right. I think that like, you know, the there's two sides of it. It's like, you know, making sure it knows things about you, but then also having the EQ to like bring those things up at the right moments, proactively or surprising you in ways that are positive, not negative. Um so, I think it's a very challenging problem, but something that I I think we feel very is a huge opportunity get right, which is like why we made like big investments in it.

</details>

**Speaker A**: 你怎么看待另一方面，比如，当你构建 ChatGPT 工作版时，它与普通的聊天应用不同，与 Codex 也不同，需要管理不同项目、协作等方面的记忆。你怎么看待这个与框架分离的方面？所以，如果我在一个项目上有四个线程，嗯，在如何构建那里的记忆系统方面有什么经验教训吗？

<details>
<summary>Original English</summary>

**Speaker A**: How do you see the side of, okay, when you're building ChatGPT for work different than the regular chat app, different than Codex, managing memory across different projects, um collaboration and whatnot? How do you see the the side of what's separate from the harness, right? So, if I have four threads on one project, um any learnings on how to build memory systems there, you know?

</details>

**Speaker B**: 为了提供一些背景，稍微引导一下，我想说，在聊天类应用中，你会有很多一次性对话，对吧？当你转向工作场景时，它可能是你要做一个月的事情，或者你经常做的事情，对吧？现在，当我增加更多会话时，情况就远不止单线程了，对吧？而且那里可能也有记忆。

<details>
<summary>Original English</summary>

**Speaker B**: For background as well, I guess, to steer it a bit is when you do chat style applications, I'd say you have a lot of one-offs, right? When you switch to work, it might be something you're doing for a month, something you do a lot, right? Now, as I add more sessions, there's a lot more than just single-threaded, right? And there there might be memory there.

</details>

**Speaker B**: 我的意思是，首先我想挑战一下这个观点，即记忆的深度或价值在聊天和工作场景中是根本不同的。确实，聊天中有很多较短的会话，但我认为，你知道，ChatGPT 这个产品已经存在了很长时间，嗯，而且你知道，只要这项技术存在，人们今天就已经在用它做与工作相关、提高生产力的事情了。所以，我认为我们发现其中有很多价值。我的意思是，即使在我个人的使用中我也发现了这一点，所有这些一次性对话随着时间的推移会累积成相当持久的东西，并且很好地代表了我这个人。我知道时不时会有人在 X 上发帖说，ChatGPT 告诉你它了解你的一切，人们总是惊讶于它了解得有多深。

<details>
<summary>Original English</summary>

**Speaker B**: I mean, I think first I'd challenge that like the depth of the memory or the like value of it is like fundamentally different across chat and work. Like, it it is true that like, you know, there are a lot of like shorter sessions on chat, but I think, you know, the ChatGPT the product has had like a ton of longevity, um and you know, as long as this this technology has been around, and and people use it for worky like productivity-related things already today. And so, I think we've found that there's a lot of value. I mean, I found this even in my personal usage, like all of these one-offs add up over time into something like quite durable and like like quite a good representation of who I am. I know like from time to time something will go viral on on X about like, you know, ChatGPT telling you everything it knows about you, and people are always surprised like how how deep that is.

</details>

**Speaker A**: 就是那个好玩的“吐槽我”，你知道的。

<details>
<summary>Original English</summary>

**Speaker A**: The fun roast me, you know.

</details>

**Speaker B**: 完全正确。所以，我想说的是，我认为现有的 ChatGPT 产品在这方面已经很有深度了，这就是为什么我们认为将其带入工作产品是有价值的。但我提出这个问题的另一个原因是，我认为，希望我们也能使用一些相同的基础原语和系统来扩展这里的记忆。而且我知道这是专注于这方面的团队目前正在努力解决的问题。

<details>
<summary>Original English</summary>

**Speaker B**: Exactly. So, like I think like the That's all to say that like I think there's a lot of depth there in the existing, you know, ChatGPT product, and so that's why I think we think it's valuable to bring into the work product. But, the other reason I brought that up is because I think, like, hopefully we can use some of the same fundamental primitives and systems to extend memory here as well. And I know this is something that the the team that focuses on this is like working working through right now.

</details>

**Speaker A**: 我想提一下记忆的一个元素，老实说我不太常用，我很好奇你是否在用，就是 Chronicle，现在屏幕上显示的就是它。呃，它有点像超级记忆，或者它到底是什么？

<details>
<summary>Original English</summary>

**Speaker A**: I wanted to bring up one element of memory, which I honestly don't really use much, and I'm curious if you do, Chronicle, which was is up on screen right now. Uh it's kind of a super memory, or like what what is it?

</details>

**Speaker B**: [笑声]

<details>
<summary>Original English</summary>

**Speaker B**: [laughter]

</details>

**Speaker B**: 我的意思是，它的理念是，它可以学习你如何使用电脑，就像它是记忆的另一个输入源。嗯，我认为它现在还是实验性的，默认是关闭的，但我建议你试试。我觉得它很有趣，因为它回到了我们之前讨论的一个话题，比如，你问过，ChatGPT 会遗漏东西吗？比如，在 Slack 上搜索时，它会遗漏东西吗？因为信息量太大了，对吧？同样的问题也适用于你在电脑上做的一切事情。比如，它会知道你做的所有事情吗？它能捕捉到意图之类的东西吗？可能不会，但它很可能会发现一些你自己可能都不知道的事情。然后，如果它能在你执行任务时，以主动的方式在合适的时机将这些信息呈现给你，那么至少我发现它会非常有帮助。所以，值得一试。

<details>
<summary>Original English</summary>

**Speaker B**: I mean, the idea is that, like, it can learn from, you know, how you're using your computer, and like it's an another input source um into memory. And um I think it's, you know, experimental right now, and something that, like, isn't default off, but I'd recommend that you try. I think that it's like quite interesting how it goes back to a conversation we were having earlier on, like, you know, you were asking, like, does it Can ChatGPT miss things? Like, does it, you know, on Slack, when it's searching, does it miss things? Cuz there's such a volume of stuff, right? And like it's I You can ask the same question about, like, everything that you're doing on your computer. Like, is it going to know everything that you're doing? Is going to capture the intent and stuff like that? Probably not, but like it probably will find things that you might not know about. And then, if it can surface those to you in relevant times in proactive ways, like when you're doing tasks, then I found, at least, that it can be quite helpful. So, it's worth trying.

</details>

**Speaker A**: 所以，主要用于洞察和长期记忆？

<details>
<summary>Original English</summary>

**Speaker A**: So, mostly for insights and longer term?

</details>

**Speaker B**: 是的，没错。比如，洞察力，它能构建上下文，让你在某些任务上更高效，但如果不亲自体验，很难描述。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, exactly. Like, insights and it builds context that that makes that can make you more productive on certain tasks, but it's it's it's hard to describe without feeling it. Um

</details>

**Speaker A**: [笑声]

<details>
<summary>Original English</summary>

**Speaker A**: [laughter]

</details>

**Speaker A**: 我得说，你能很好地感受到它。就像他们在这里说的那样，对吧？就是“检查我的记忆”或“检查我的日志，并添加技能”。

<details>
<summary>Original English</summary>

**Speaker A**: I will say you can feel it pretty well. Like, the idea of what they're saying here, right? Just check through my memories, or check through my logs, and add skills.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 相当被低估了，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: Pretty underrated, right?

</details>

**Speaker B**: 但是，那是自动化。你可以用 cron 任务重复做。

<details>
<summary>Original English</summary>

**Speaker B**: But, that's that's automations. You you can repeat that using a cron job.

</details>

**Speaker A**: 检查你的记忆并创建技能。

<details>
<summary>Original English</summary>

**Speaker A**: Checking through your memories and creating skills.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 但我认为，从 Chronicle 本身创建记忆才是不同之处。就像你因为开启了 Chronicle 而拥有了更深的记忆。

<details>
<summary>Original English</summary>

**Speaker A**: But I think the creation of the memories from Chronicle itself is like what's different. It's like you have much deeper memories because you have Chronicle on.

</details>

**Speaker B**: 它就在那里。我不怎么用它，但也许我只是需要更多例子。我想你们内部肯定用了很多，所以我一直在找用例。

<details>
<summary>Original English</summary>

**Speaker B**: It's there. I don't use it much, but maybe I just I need more examples. I I imagine you guys use a lot of it internally, so I'm always fishing for use cases.

</details>

**Speaker A**: 是的，我会建议你直接打开它，然后它就会自动运行。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I would just try turning it on and then like it just auto works. Like it

</details>

**Speaker B**: 是的，然后看看它可能在哪些方面开始帮助你。我想你会感到惊讶的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, and seeing like where where it might start helping you. I think you'll be surprised.

</details>

**Speaker A**: 是的，太棒了。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, amazing.

</details>

### 关于 AI 时代前后构建产品的反思

**Speaker A**: 我想关于 ChatGPT 工作版的整体覆盖就这些了。我认为在构建和所有这些方面已经取得了很大进展，也有很多讨论。社区里和 OpenAI 内部也有很多前创始人。你认为事情发生了很大变化吗？我猜就像是你对 AI 时代前后构建产品的整体反思。

<details>
<summary>Original English</summary>

**Speaker A**: I think that was the about it in terms of like the the overall coverage of ChatGPT work. I think there's been a lot of like good progress and discussion on building and all these things. There's a lot of like ex-founders in the in the community and in OpenAI as well. Do you think that things have changed a lot? I I guess like your overall reflection of building pre-AI and post-AI.

</details>

**Speaker B**: 我的意思是，我认为事情发生了巨大的变化。我觉得看到今天从想法到实现真实产品能有多快，这非常令人兴奋。是的。嗯，而即使在之前，比如我认为，你知道，5年、10年前，如果你很拼，并且愿意构建最小可行产品，那也算快了，但现在你能构建的东西的范围要广泛得多。而且我认为我们在内部构建时也看到，这让你有机会更快地验证，与用户交流，与内部医生等交流，并确保你走在正确的轨道上。

<details>
<summary>Original English</summary>

**Speaker B**: I mean, I think things have changed a ton. I think it's it's like super exciting to see how quickly you can go to from idea to something real today. Yeah. Um whereas like even before like I think you know, 5 10 years ago like it it was fast if you were scrappy and you know, like willing to build the the minimal viable thing, but like now the extent of what you can build is like much much broader. And I think that also like what we've seen internally building is like that gives you an opportunity to validate much more quickly, to talk to users, to talk to to internal doctors, etc. and like make sure you're on the right track.

</details>

<!-- chunk 10/11 -->

### 反馈循环与产品开发

**Speaker A**: 这个循环，我认为，比以往任何时候都更加封闭了。这对产品开发来说是一个胜利。我认为这对消费者和用户来说也是一个胜利，因为理想情况下，这意味着他们从一开始就能得到好得多的产品。

<details>
<summary>Original English</summary>

**Speaker A**: And like that loop I think has been has become more closed than ever before and that's like a win for product development. I think it's a win for for consumers and users too cuz ideally that means they're getting much more better much better products out the gate.

</details>

**Speaker B**: 这是否意味着你的团队规模变小了？

<details>
<summary>Original English</summary>

**Speaker B**: Does it mean your team's a smaller?

</details>

**Speaker A**: 我认为现在有更多的事情要做。嗯，所以我认为人们现在可以单独或在小团队中完成更多以前需要更多人才能完成的事情，但同时也有更多的事情要做。所以我认为团队的雄心壮志更大了。

<details>
<summary>Original English</summary>

**Speaker A**: I think there's much more to do now. Um so I think people can accomplish more individually or in a small team than they were that would require more people within before, but there's at the same time there's also more to do. So I think the teams are much more ambitious.

</details>

**Speaker B**: 你看到角色范围、团队组建方式有什么变化吗？比如，几年前我们组建团队的方式，与现在理想的团队构成相比，有什么不同？

<details>
<summary>Original English</summary>

**Speaker B**: You seen any changes in scopes of roles and building teams and how we used to have teams say a few years ago versus what ideal teams look like now?

</details>

**Speaker A**: 我认为我们看到典型的产品开发职能之间的界限变得模糊了，比如，你知道，工程经理、产品经理、工程师，嗯，设计师等等。

<details>
<summary>Original English</summary>

**Speaker A**: I think we've seen a blurring in the lines between like the typical product development functions like between like you know, EM, PM, engineer, um designer, etc. like

</details>

**Speaker B**: 是啊，当我提起这句话时，科技行业将只剩下四种工作。有AI“垃圾大炮”，那些只会……嗯，他们会消耗大量token的人；然后还有SRE，那些更负责任的人；还有负责销售的“成年人”；最后就是“红人”。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, when I bring up this quote, there will be uh only four jobs left in tech. There's AI uh slop cannon, the people who just like uh they'll burn a bunch of tokens uh and then there is there is SRE uh who people who are more responsible. There's grown-ups who sell things and then there's hot people.

</details>

**Speaker A**: [笑声] 这是一个有趣的观点。我的猜测是，每个人都会在某种程度上成为T型人才，而不是说AI会让每个人都成为通才。比如，我以前永远无法提出一个设计方案，即使现在，我可能也没有所需的视觉品味，但我可以在AI的帮助下迭代一些东西。但人们会有一个专长，那就是T字的那一竖，或者T字向上的那条线。嗯，所以，你有一个你感兴趣的专长，在AI的帮助下，你可以随着时间的推移变得更深入、更擅长，但同时你也是一个通才。有了这个基础，你能完成的事情几乎是无限的。

<details>
<summary>Original English</summary>

**Speaker A**: [laughter] It's an interesting take. I think my my suspicion is that there's everything everyone will be like T-shaped in a way and not like AI will enable everyone to become a generalist like you know things that like I I never would be able to like come up with a design before and like even now I don't have maybe like the visual taste required but I can iterate on something with the help of AI. But then people will have a specialty and that's like the the like it's a straight line in the T or the the upward line in the T. Um and so like you have a specialty that you're interested in with the help of AI you can go deeper and become better at over time but then you'll also be a generalist and so with that foundation the what you can accomplish is like almost limitless.

</details>

**Speaker B**: 在专业领域方面，你被什么卡住了？比如，你需要更多的设计师吗？你需要更多的“垃圾大炮”吗？你需要更多的“红人”吗？

<details>
<summary>Original English</summary>

**Speaker B**: What are you bottlenecked by in terms of specialties? Like do you need more designers? Do you need more slop cannons? Do you need more hot people?

</details>

**Speaker A**: 我认为瓶颈变成了某种……想法和品味，我猜。嗯，因为现在任何人都可以构建，我认为这真的是一个自下而上的雄心时代。因为有太多东西需要构建，所以你在任何时候都总是会被你拥有的想法数量和你正在做的事情的数量所限制。

<details>
<summary>Original English</summary>

**Speaker A**: I think the bottleneck some becomes like sort of like ideas and taste I guess. Um I think because anyone can can build now, I think um it really is the era of like bottoms-up ambition and because there's so much to be built, like you're always going to be bottlenecked by you know the amount of ideas and amount of things that you're doing at any given time.

</details>

**Speaker B**: 你认为模型有助于解决这个问题吗？

<details>
<summary>Original English</summary>

**Speaker B**: Do you think models help solve that?

</details>

**Speaker A**: 模型？

<details>
<summary>Original English</summary>

**Speaker A**: Models?

</details>

**Speaker B**: 是的。我的意思是，我有个例子，比如我有一项前端设计技能，它们会给我四个截然不同的示例，展示这个东西可能的样子。当然，这会消耗大量token，但你知道，然后我通常会把它们整合起来。好吧，我喜欢这部分，我喜欢那部分。我们把它们结合起来，就像……是的，我有一个愿景，但我不知道。我想说，我希望实现但行不通的一个自动化是“给我新想法”，对吧？嗯，不知何故，LLM就是做不到。关于想法，有趣的一点是，它们不是凭空产生的。它们通常来自某个地方，你知道，在产品开发中，它们来自与用户交谈，或对你看到的摩擦或反馈做出反应，或在你之前已经规划好的基础上进行构建等等。嗯，所以我认为，这就是我们谈到的那些通才的价值所在，你知道，他们能闭合那个循环，并根据反馈、与用户交谈或其他什么，提出那些立足于现实的想法。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I mean I have the example of like I have a front end design skill that's like they give me four drastically different examples of what this looks like. You sure it burns a lot of tokens, but you know and then I'll mostly just condense down. Okay, I like this part, I like this part. Let's draw these together and it's like yeah, I had a vision, but like I don't know. I would say that the one automation that I would love to work and it doesn't work is bring me new ideas, right? Uh somehow LLMs are just not it. One interesting part about ideas is like they're not like in a vacuum. It's like not they they usually come from somewhere and like you know in in product development like they're coming from talking to users or reacting to you know friction that you're seeing or feedback building on some foundation that you already had planned out before whatever. Um and so I think that's where like I think there there always be value in in these like generalists that we talked about like you know closing that loop and and and and having coming up with those ideas that are grounded in in that feedback or talking to users or whatever it is.

</details>

### 定义生产力

**Speaker B**: 酷。嗯，你领导生产力团队。你如何定义生产力？

<details>
<summary>Original English</summary>

**Speaker B**: Cool. Uh you were going to you lead the productivity team. How do you define productivity?

</details>

**Speaker A**: 我认为我们的使命是让人们能够做到以前做不到的事情。而现在，我们主要从知识工作的角度来思考这个问题。在看待知识工作时，我认为人们不再被他们的角色所束缚，也不再被他们的背景或所受的训练所束缚。就像，无论你处于什么职能，你都可以突然开始构建东西，突然可以访问你以前可能无法解读的数据等等。嗯，然后我认为这可以延伸到你的个人生活，我们希望最终能为你提供杠杆。我们希望产品中的模型能够为你提供杠杆，这样你就可以为自己创造时间，去做你热爱的事情。

<details>
<summary>Original English</summary>

**Speaker A**: I think our mission is to make it possible for people to do things that they weren't able to do before. And right now we're thinking about it from the the perspective of knowledge work. And so when looking at knowledge work I think about people are no longer siloed by their roles, they're no longer siloed by maybe the the um background or training that they have. Like no matter what function you're in you can suddenly build things and suddenly get access to data that you otherwise might not be able to interpret etc. Um and then I think that extends to your personal life where we want to give you leverage at the end of the day. Like we want the models in the product to be able to give you leverage so that you can you know create time for yourself to do the things that you love.

</details>

**Speaker B**: 这是否也转化为衡量生产力的方法？比如，你如何衡量杠杆？

<details>
<summary>Original English</summary>

**Speaker B**: Does that also translate to a way to measure productivity? Like what is how do you measure leverage?

</details>

**Speaker A**: 我认为我们还没有弄清楚这一点。部分原因是它太多样化了。每个人都有不同的目标，真正衡量标准是他们实现那个目标的能力。我们帮到你了还是没有？是的。而且，如果事先不知道那个目标是什么，并且不为每个人量身定制，这是非常困难的。

<details>
<summary>Original English</summary>

**Speaker A**: I think we haven't figured this out yet. Part of the reason is it's so diverse. Everyone has different goals and really the true measurement is like their ability to achieve that goal. Did we help you or did we not? Yeah. And it's very difficult without knowing what that goal is up front and also tailoring it for every individual.

</details>

**Speaker B**: 而ChatGPT的“赞”和“踩”并不能给你任何信息，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: And the thumbs up and thumbs down from ChatGPT doesn't give you anything, right?

</details>

**Speaker A**: 对。我的意思是，你不知道他们是在给答案的内容、它的“感觉”点踩，还是它是否帮助他们实现了目标。我认为这很困难。嗯，但这是我认为我们需要解决的问题，整个行业也需要解决，因为，你知道，如果这是我们的目标，这就是我们衡量成功的方式。

<details>
<summary>Original English</summary>

**Speaker A**: Right. I mean, you don't know if they're thumbs downing the the content of the answer, the vibe of it, whether or not it helped them with their goal. I think that's difficult. Um but it's something that I think we will need to figure out and the industry at large will need to figure out because, you know, that's how we we measure success if this is what we're for.

</details>

**Speaker B**: 你认为它改变了生产力以及你衡量它的方式吗？基本上，你说现在可以做更多的工作，范围也大得多。嗯，它改变了吗？

<details>
<summary>Original English</summary>

**Speaker B**: Do you think it's changed productivity and how you measure it? Basically, you said there's a lot more work that can be done, a lot more scope. Um has it changed?

</details>

**Speaker A**: 我认为一直以来，你真正想衡量的是，你知道，你的团队、个人、你自己是否能够达成目标，或者你是否更接近达成你的任何目标，对吧？但我认为以前我们使用代理指标。比如，你知道，代码提交次数或代码行数之类的。嗯……

<details>
<summary>Original English</summary>

**Speaker A**: I think it was always true that what you really wanted to measure is like you know, was your team, was the individual, were you personally able to hit the goal or are you closer to hitting that whatever your goal is, right? But I think previously we used proxies for this. So like, you know, code commits or lines of code or whatever. Um

</details>

**Speaker B**: 故事点。

<details>
<summary>Original English</summary>

**Speaker B**: Story points.

</details>

**Speaker A**: 是的，没错。故事点。而且……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, exactly. Story points. And like

</details>

**Speaker B**: 顺便说一句，它又回来了。

<details>
<summary>Original English</summary>

**Speaker B**: Coming back, by the way.

</details>

**Speaker A**: [笑声] 也许吧。我的意思是，但这是变化的一部分，我认为随着AI的出现，这些代理指标开始失效了。比如，你知道，你使用的token数量，或者你发起的拉取请求数量，等等，可能不再与你的团队能否达成目标或是否在达成目标的轨道上高度相关。所以我认为我们需要想出新的衡量标准。

<details>
<summary>Original English</summary>

**Speaker A**: [laughter] May maybe. I mean, but but that is for part of the change and like I think with with AI now, those proxies starting to fall apart. Like you you know, the number of tokens you use or the number of pull requests you make or like no longer like maybe as hyper correlated with the that is your team able to hit the goal or are they on track to hit their goals. So I think we'll need to come up with with new um measurements.

</details>

### 给管理者的建议

**Speaker B**: 对于正在听的管理者们，嗯，给他们一个可以尝试的方法。

<details>
<summary>Original English</summary>

**Speaker B**: For the managers listening, uh give them one thing to try.

</details>

**Speaker A**: 我认为对我来说，重要的是“上场击球次数”。我们作为一个团队，是否在培养一种能力，不仅要有击球的数量，还要有质量？比如，我们能否完整地走完一个流程：从产生一个想法，到把它构建出来，获得反馈，对反馈做出反应，实际验证或推翻假设，然后继续下一个想法？我们能否非常高效地做到这一点？这涉及到，你知道，实际编写的代码、做出的设计、编写的规格说明等等，但也涉及到团队的文化。比如，我们是否有谦逊的态度，并且能够一次又一次地经历这个过程，并在此过程中保持动力和兴奋？嗯，所以这就是我认为现在很重要的事情，尤其是当我们处于这项技术的前沿，有这么多东西要构建，有这么多事情要做的时候。这可能是我们最看重的事情。

<details>
<summary>Original English</summary>

**Speaker A**: I think for me, what's important is like at-bats. Are we as a team building the muscle to have not just quantity of at-bats, but quality? Like, are we able to go all the way from like generating an idea, building it out, getting the feedback, reacting to that feedback, actually validating or invalidating the hypothesis, going on to the next idea? Are we able to do that really efficiently? Like that goes to like, you know, the actual like code that's being written or the designs that are being made or the specs that are being written whatever, but also the culture of the team. Like do we have the humility and and and and um are able to like go through that process many many times and stay motivated and excited throughout that. Um so that's the thing that like I think is important now, especially when we're on the frontier of this technology and like there's so much to build, there's so much to do. That's probably the most most important thing that we look at.

</details>

**Speaker B**: 人们在衡量你和团队工作的生产力时，有没有什么常见的陷阱？我感觉有很多这样的情况：好吧，我们加了很多LLM，我们有这个那个的仪表盘，但实际变化不大，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Any traps people fall into around measuring productivity with your team work on? I feel like there's a lot of okay, we added a lot of LLMs, we have dashboards for this and that, but not much has changed, right?

</details>

**Speaker A**: [笑声] 这就是陷阱，是的。

<details>
<summary>Original English</summary>

**Speaker A**: [laughter] That is the trap, yes.

</details>

**Speaker B**: 你知道，这个问题的更广泛来源是，对于正在构建产品的管理者和团队，你知道，他们应该如何处理这个问题？

<details>
<summary>Original English</summary>

**Speaker B**: And you know, the broader source of the question is for for the managers and teams building, you know, how how should they approach this?

</details>

**Speaker A**: 我认为陷阱可能是混淆了“动作”和“进展”。我认为，由于我们拥有的工具，现在产生“动作”比以往任何时候都容易得多。但“进展”要求你非常有条理和刻意地对待你正在做的事情。

<details>
<summary>Original English</summary>

**Speaker A**: I think maybe the trap is like conflating motion and progress. I think motion is much easier now than ever before because of the tooling that we have. But progress requires you to be like very prescriptive and deliberate about like what you're

</details>

<!-- chunk 11/11 -->

### 运动与进步的区别

**主持人**: 实际上，这正是我们试图实现的目标。这又回到了我们关于衡量标准的问题，对吧？就像我们之前讨论的，OpenAI 能否找出衡量用户生产力的方法？这是一个非常困难的问题，因为存在多样性，但作为一个团队，你应该对你和你的团队来说进步是什么样子，有一个非常规范且深思熟虑的看法。如果你没有这个看法，那么很容易将这两件事混为一谈。我认为“忙碌”是一件非常好的事情。我真的很高兴……我喜欢运动与进步之间的讨论。我认为这是我们将在总结中引用的一个金句。你非常慷慨地分享了你的时间。非常感谢你，并祝贺你达到1000万用户。

<details>
<summary>Original English</summary>

**Host**: Actually, that's what we're trying to achieve. And it goes back to our question of measurement, right? Like you were we were talking about like can we OpenAI like figure out how to measure productivity for our users? That's that's a very hard problem because of the diversity, but like as a team like you should have a really prescriptive and deliberate view on like what progress looks like for you and for your team. And if you don't have that, then it's very easy to conflate these two things. I think that batch is a really great thing. I'm I'm really glad I I like the discussion between motion and progress. I think that's a quote that we're going to feature in the write-up. You've been very generous with your time. Thank you so much and congrats on 10 million.

</details>

**嘉宾**: 是的，谢谢你邀请我。

<details>
<summary>Original English</summary>

**Guest**: Yeah, thank you for having me.

</details>

**主持人**: 下一个目标，100。两个月内。

<details>
<summary>Original English</summary>

**Host**: The next to a next one at 100. In two months.

</details>

**嘉宾**: [笑声]

<details>
<summary>Original English</summary>

**Guest**: [laughter]

</details>

**主持人**: 谢谢。

<details>
<summary>Original English</summary>

**Host**: Thank you.

</details>