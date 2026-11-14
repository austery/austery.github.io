---
author: Latent Space
date: '2026-03-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TvmxWWfiYWI
speaker: Latent Space
tags:
  - ai-agents
  - agentic-apps
  - ai-platform
  - ecosystem-development
  - privacy-security
title: Dreamer：面向所有人的智能代理操作系统
summary: 本访谈深入探讨了 Dreamer 平台，一个由前 Stripe CTO David Singleton 创立的 AI 代理生态系统。Dreamer 旨在让非技术用户也能发现、构建和使用 AI 代理与智能应用，通过核心 Sidekick 代理简化操作。平台强调隐私安全、开放工具构建，并提供独特的 Builders-in-Residence 计划，鼓励开发者贡献和货币化工具。访谈还讨论了 AI 在团队协作、记忆处理和未来商业模式中的潜力，以及在 AI 时代对工程师技能的新要求。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - David Singleton
  - Swix
  - Hugo Bar
  - Nicholas Czechov
  - Sam Altman
  - Andrew
  - Greg Brockman
  - Sarah
companies_orgs:
  - Stripe
  - Google
  - OpenAI
  - Xbox
  - Anthropic
products_models:
  - Dreamer
  - Sidekick
  - Android
  - Play Store
  - Calendar Hero
  - Granola
  - Attain Finance
  - Instacart
  - Haiku 45
  - Sunno
  - nano banana
media_books: []
status: evergreen
---
### Dreamer 的核心理念与操作系统级架构

**David Singleton**: 显然，拥有能为你工作的软件非常酷，但它只有在你信任它时才有用，对吗？所以，隐私和安全对我们来说非常重要。当我们开始思考这个问题时，我们意识到我们实际上必须构建一个有点像操作系统的东西。**Sidekick** 就像内核，代理和应用程序就像用户。不同的环。没错。因为如果你试图只挑选其中一部分，你实际上无法让它在大规模人群中工作。你可以构建一些小型的五代码应用程序，但它们会随意抓取你的所有数据。它们无法协同工作。你必须投入到基础核心中，才能让它为人们良好地工作。这就是我们一直在做的，并且一直很有趣。

<details>
<summary>Original English</summary>

**David Singleton**: Obviously, it's really cool to have software that will work on your behalf, but it's only useful if you can trust it, right? So, privacy and security is very important to us. As we started to think about this problem, we realized that we actually had to build something that's a bit like an operating system. The sidekick's like the kernel, the agents and apps are like users. Different rings. Exactly. Because if you try to pick off just one piece of this, you can't actually make it work for people at scale. You could build little five-coded apps, but they're going to grab all your data willy-nilly. They won't be able to work together. You actually have to invest in the fundamental core in order to make it work well for people. That's what we've been doing. And it's been a lot of fun.

</details>

### 访谈开场与 Dreamer 介绍

**Swix**: 好的，我们在演播室里和 **David Singleton** 在一起。欢迎你。

<details>
<summary>Original English</summary>

**Swix**: Okay, we're here in the studio with David Singleton. Welcome.

</details>

**David Singleton**: **Acewix**，很高兴来到这里。

<details>
<summary>Original English</summary>

**David Singleton**: Acewix, it's great to be here.

</details>

**Swix**: 很高兴能邀请你。我们很有共鸣，你们公司的颜色和 **Lyn Spac** 的颜色一样。

<details>
<summary>Original English</summary>

**Swix**: It's great to have you. We have very sympatico that your company color is the same as Lyn Spac's color.

</details>

**David Singleton**: 没错。绿色或紫色。

<details>
<summary>Original English</summary>

**David Singleton**: That's right. Green or purple.

</details>

**Swix**: 以前是 **dev agents**，我觉得很酷。这就像是对 **dev payments** 的回顾。

<details>
<summary>Original English</summary>

**Swix**: It used to be dev agents, which I thought was very cool. It's like a call back to dev payments.

</details>

**David Singleton**: 是的。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah.

</details>

**Swix**: 你显然是 **Stripe** 的 **CTO**。跟我谈谈 **Dreamer** 背后的起源或思考过程。也许可以从 **Dreamer** 是什么开始。

<details>
<summary>Original English</summary>

**Swix**: You were obviously CTO of Stripe. Talk to me about the origin or thinking process behind Dreamer. Maybe start with what Dreamer is.

</details>

### Dreamer：为大众设计的智能代理应用商店

**David Singleton**: 是的，**Dreamer** 是一个新产品，每个人今天都可以来玩。这是一个让所有人，确实是所有人，都能发现、构建、享受和使用 **AI 代理**和**智能应用**的地方。我们确实是为消费者设计的，为那些不一定有任何技术背景的人设计的。它真的是面向所有人的。我经常想到我的姐姐。她很聪明，但一点也不懂技术。她的生活中有很多问题，她希望能有很棒的软件和智能软件来解决，但即使像 **cloud code** 这样的工具兴起，她也无从下手。而 **Dreamer** 就是一个她可以进来，获取社区中其他人构建的智能应用，立即开始使用，并解决她生活中实际问题的地方。核心部分我们有一个名为 **Sidekick** 的个人代理。你可以给你的 Sidekick 起名字，赋予它自己的个性，它会在你的一整天、你的生活中真正帮助你。它帮助你使用平台上的所有代理，也帮助你构建任何你想要的东西。我们已经为此努力了一段时间。我们最近推出了 **beta** 版本，所以任何人都可以访问 **dreamer.com**，加入等待名单。现在社区中有许多人在为自己构建真正有趣、强大且有用的代理和智能应用。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. So, **Dreamer** is a new product which everyone can come and play with today. It's a place where everyone, literally everyone, can discover, build and enjoy and use **AI agents** and **agentic apps**. And we really did design it for consumers, for folks who do not necessarily have any kind of technical background. It's really aimed at everyone. I think often of my sister. She's very smart. She's not in the slightest bit technical. She has lots of problems in her life that she would like to be able to have great software and intelligent software to solve, but even with the rise of tools like **cloud code** and so forth, she's got no way to get started. And Dreamer is a place where she can come in, grab some intelligent apps that other people in the community have built, start using them right away, and solve real problems in her life. And at the core, we have a personal agent called the **sidekick**. You can give your sidekick a name, you can give it its own personality, and it really helps you across your entire day, your life. It helps you use all of the agents on the platform, and it also helps you build anything you want. We've been working on this for a little while. We recently launched in **beta**, so anyone can go to **dreamer.com**, join the wait list. And we have many, many, many people in the community now who are building really fun, really powerful, really useful agents and agentic apps for themselves.

</details>

### 从 Stripe CTO 到 Dreamer 联合创始人：移动应用生态的经验迁移

**Swix**: 我想我们接下来会直接进入演示环节。我只是想提一个观察，你把发现放在构建之前，但实际上，至少对于我们这些工程师听众来说——因为我们主要是工程师，而你主要瞄准的是消费者，对吗？

<details>
<summary>Original English</summary>

**Swix**: I think we're going to go right into a demo. I just want to make an observation that you put discover first before build, but actually at least for the engineers in the audience, because we are primarily engineers and you're primarily targeting consumers, right?

</details>

**David Singleton**: 是的。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah.

</details>

**Swix**: 对于工程师来说，有大量完整的技术栈内容，我们将深入探讨。没错。这太令人印象深刻了。我心想，‘天哪！’ ‘这正是我一直想要的。’ 所以我认为这非常好。从某种角度来看，考虑到你的背景，考虑到 **Hugo** 的，是 Hugo 吗？

<details>
<summary>Original English</summary>

**Swix**: For engineers, there's a huge full stack of stuff which we're going to dive into. That's right. It's so impressive. I'm like, "Holy shit." "This is what I always wanted." I think that's really good. In some ways, given your background, given **Hugo**'s, is it Hugo?

</details>

**David Singleton**: **Hugo Bar**。是的，**Hugo**。你基本上是为代理构建了一个应用商店，这并不令人惊讶。

<details>
<summary>Original English</summary>

**David Singleton**: **Hugo Bar**. Yeah, **Hugo**. It's not surprising that you basically kind of build an app store for agents.

</details>

**David Singleton**: 是的，**Hugo** 是我的联合创始人。我和 Hugo 在 **Google** 的 **Android** 早期阶段认识了我们的另一位联合创始人 **Nicholas Czechov**，当时我们正在构建 Google 的第一批移动应用。然后我们为 Android 本身的核心部分做出了贡献。你说得对，我们对构建两件事非常兴奋。第一，解决移动这项突破性技术需要解决的许多问题，以便让它能够在大规模人群中真正发挥作用。第二，利用 **Play Store** 构建一个第三方开发者生态系统，能够在平台上提供比我们自己能提供的多得多的价值。我们对 **Dreamer** 的看法也完全相同。正如你所提到的，我当时在 **Stripe** 工作，我们有机会将世界上第一批 **AI 代理系统**投入生产。从我们完成第一个系统的那一刻起，我就强烈地相信，这是一项突破性技术，它将改变我们所有人与计算机、手机以及我们生活中所有技术互动的方式。但要让这项技术对普通人来说易于接近，还有很多问题需要解决。它与我们当年在 Google 和 Android 上解决移动应用早期问题的问题如出一辙。所以，能把它变为现实很有趣。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. So **Hugo** is my co-founder. Hugo and I met with our other co-founder, **Nicholas Czechov**, in the very early days of **Android** at **Google** where we were building Google's first mobile apps. We then contributed to very core pieces of Android itself. And you're right, we were really excited about building two things. One, solving a bunch of problems that this breakthrough technology here I'm talking about mobile, needed to have solved in order to make it work for real people at scale. And then secondly, building this ecosystem of third-party developers using the **Play Store** and able to deliver way more value on the platform than we could have delivered on our own. And we think about **Dreamer** in exactly the same way. I was working at **Stripe** as you mentioned and we had the opportunity to put some of the very first **AI agent systems** in the world into production. And from the moment we did the first of those I was just struck with a strong sense of conviction that this is breakthrough technology that's going to change how all of us work with computers and phones and so forth, all of the technology in our lives. But there's a lot of problems to be solved for real people to be able to make this approachable. And it really is kind of a direct analog for what we were solving back in the early days of mobile apps at Google and on Android. So, it's been fun to bring that to life.

</details>

### Dreamer 平台演示与个性化代理应用

**Swix**: 好的。我们来看看。

<details>
<summary>Original English</summary>

**Swix**: Yeah. Let's look at it.

</details>

**David Singleton**: 好的，我们来看看。这是 **dreamer.com**，我们的主页。你可以在这里观看一些关于它是什么的视频，并注册等待名单。一旦你……

<details>
<summary>Original English</summary>

**David Singleton**: Yeah, let's take a look. So, **dreamer.com**. This is our homepage. This is where you can come and watch some videos about what is here and sign up for the wait list. Once you...

</details>

**Swix**: 我只是想对那些听众说，请切换到 **YouTube**，看看那些动画。

<details>
<summary>Original English</summary>

**Swix**: I just want to say for those listening, switch to **YouTube**, look at the animations.

</details>

**David Singleton**: 我们非常用心。我们非常关心这款产品要有趣且使用起来引人入胜。显然，很多人用它来做真正重要的事情。你可以在这里完成实际工作。但你也可以构建一些有趣的东西。一旦你脱离等待名单，你就会进入产品。第一件事就是你会和你的 **Sidekick** 进行对话，它就是这个友好的小角色。Sidekick 会试图了解你，理解你。你关心什么？我们会帮助你发现并构建你的第一个 **AI 代理**或智能应用。之后，你就会有一个仪表盘。这是我的仪表盘。每个人的都不同。你可以看到我这里有一些东西。我有一个信息流。所以我们很多代理在你没注意的时候在后台做事情。信息流就是它们让你知道它们最近在忙什么的方式。我有一些我自己构建的应用的小部件。这个叫做 **Calendar Hero**。这是我从应用商店安装的。它是由我们社区中的某个人构建的。这是一个非常强大的日历应用，因为对于我的每一次会议，如果会议对象是我不熟悉的，它实际上会去研究，然后给我提供我与这些人互动过的历史，以及一堆公开的有用信息，让我可以开始。我喜欢这个应用的一点是，它每天会生成一个播客，一个每日简报。我们对平台做的一件事是，我们让代理做的事情能够出现在你关心的所有地方。所以如果你看这边，这是我手机的屏幕。如果我打开 **Apple Podcasts**，你可以看到这里，你的每日简报播客已经准备好了。这是由运行在我 **Dreamer** 账户中的一个代理生成的。通过扫描二维码将其连接到我的 Apple Podcasts 非常简单。现在我每天早上上班路上都会听这个。它为我的一天做好了准备。

<details>
<summary>Original English</summary>

**David Singleton**: There's so much care. We really care about this product being fun and interesting to use. Obviously, a lot of people are using it to do real important stuff. You can do real work here. But also you can build fun things too. Once you get off of our wait list, you'll come into the product. The first thing that happens is you'll have a conversation with your **sidekick**, which is this little friendly character here. And sidekick will seek to get to know you and understand you. What do you care about? And we'll help you discover and build your first **AI agents** or **Aentic apps**. After that, you're going to have a dashboard. This is my dashboard. Everyone's is different. You can see I have a few things here. I have a feed. So, a lot of our agents do things in the background when you're not looking. And the feed is how they let you know what they've been up to. I have some widgets from apps that I have built. This one is called **Calendar Hero**. This is something that I installed from the gallery. This was built by someone in our community. It's a really powerful calendar app because for each of my meetings, if it's with someone I don't already know well, it'll actually go off and research it and give me both a history of my interactions with those people and also a bunch of public useful information to get started. One of the things I love about this particular app is that every day it generates a podcast, a daily briefing. And one of the things that we've done with the platform is we've made it possible for all the things that agents do to show up in places that you care about. So if you look over here, this is the screen at my phone. And if I go ahead and open my **Apple Podcasts**, you can see right here, your daily briefing podcast is ready. This was produced by an agent running in my **Dreamer** account. And it was very easy by scanning a **QR code** to connect it to my Apple Podcasts. That's what I listen to in the car now every morning. On my way to work, it preps me for my day.

</details>

### 代理的移动集成与工具库

**Swix**: 我看到这个之后，立即问了你一个额外的问题，比如“我怎么能和我的代理对话呢？”你说你实际上最初是从语音开始的，后来才转到播客，因为预先下载好会很方便。

<details>
<summary>Original English</summary>

**Swix**: So, one additional bit of context I asked you immediately after seeing this was like, "What what about I want to talk back to my agent?" And you said you actually started with voice and then you went to podcast because it's nice to have it pre-downed.

</details>

**David Singleton**: 没错。

<details>
<summary>Original English</summary>

**David Singleton**: That's right.

</details>

**Swix**: 是的，你可以和你的 **Sidekick** 对话。所以，在移动端我们有 **Dreamer** 应用，你可以在这里直接和 Sidekick 对话。但是我们发现，让内容出现在你日常生活中已经使用的其他应用中，这种方式非常强大。所以，我们来看看这里面有什么秘密。我之前提过我们有一个应用商店。所以，你会在那里找到我们社区中的许多代理。目前已经有数百个，它们正在解决各种用例。我想说，最主要的用例是个人生产力，但也有很多信息管理。这可以包括个人信息，比如文档等等，管理你的电子邮件。它也延伸到你可能感兴趣的公共信息，但你需要一些东西来帮助你管理涌向你的海量信息。例如，我有一个代理，它一直在查看所有 **AI** 新闻。信息量很大，它会找到我真正感兴趣的东西。我发现它非常有用。所以，这些是你可以安装的其他开发者构建的代理。你在 **Dreamer** 上安装的任何东西，你都可以说，我想开始做一些修改。我们稍后会看看。但是通过自然语言，在 **Sidekick** 的帮助下，你可以修改任何这些体验，让它们以你想要的方式工作。系统基础层是工具。所以你和 **Swix** 都知道，任何 AI 系统的好坏，都取决于它能获取的数据质量和它能采取的行动质量。所以在我们推出 **beta** 版之前，我们非常努力地确保我们的工具集成了许多高质量和强大的集成。所以，例如，这是真正的 **Google 搜索**。这是真正的 **Gmail**。你可以用它们做非常有用的事情。但这也是一个面向所有人的平台。当我们开始和我们的 **alpha** 社区的人交流时，出现了一大堆体育用例，我们意识到如果你想用 AI 为体育构建一些酷炫的东西，你需要真正高质量的实时数据。所以看看这些 **Formula 1**、**MLB**、**NFL**。这些都是我们构建的工具。我们做的这些不是从网上抓取的数据。这是一个直接的数据流集成。正因为它是实时的和高质量的，你可以构建真正强大的东西。但工具并不是我们自己要控制的东西。平台对工具开发者开放，让他们贡献可以在 **Dreamer** 上供任何人使用的工具。所以，这实际上是平台中，我认为软件工程师……首先，我们很乐意你来玩。但软件工程师真的会为系统构建许多强大的东西。我们今天在播客上首次分享一件事，那就是 **Dreamer** 上的工具开发者可以获得报酬。所以，如果你向平台发布一个工具，并且很多代理使用它，你实际上会根据使用量获得报酬。我们希望大家来尝试一下。我们有很好的文档可以帮助你入门，你可以构建一些解决你自己需求的东西。例如，有人构建了这个 **Ski Bum** 工具，它提供了许多滑雪胜地的实时雪况。我稍后会向你展示我是如何使用它的。我们也有一些工具合作伙伴，他们的工具是按使用付费的。例如，**Parallel Web Systems** 是一个高级工具。你可以用它做一些非常酷的事情。它是一个智能化的网络研究工具。因为它的运营成本很高，所以它是按使用付费的。但如果你是来平台上构建代理的，即使是高级工具，你也可以获得免费试用。所以你可以在决定注册之前，有机会实际试用它们，确保这个用例适合你。这就是工具。所以，我们有应用商店，我们有工具，然后 **Sidekick** 帮助我们把所有这些整合起来，构建代理。我们在代理工作室中进行这些操作。你也可以在手机上进行，但如果我在这里在桌面打开代理工作室，Sidekick 就会开始与你对话，讨论你想一起构建什么。我很乐意向你展示我最近做的一个。我们来做吧。

<details>
<summary>Original English</summary>

**Swix**: Um yeah, we you you can talk to your **sidekick**. So, you know, on mobile we have a **dreamer app** and you can talk to the sidekick right here. But we've actually find that making things show up in the other apps that you already use in your life is incredibly powerful. So, let's take a look at what's kind of under the hood here. So, I already mentioned that we have a gallery. So, this is where you'll find a lot of agents from our community. There's many at this point, hundreds, and they are solving all kinds of use cases. I'd say the top use cases are around personal productivity, but also a lot of information management. That can range from personal information like docs and so forth, managing your emails. It also ranges out to public information that you might be interested in, but you need something to help manage the kind of fire hose of stuff that's coming at you. For instance, I have an agent which looks at all the **AI news** all the time. There's a lot of it and it finds the stuff that I would actually be interested in. And I've found it incredibly useful. So, these are agents that you can install that other people have built. Anything that you install on **Dreamer**, you can actually just say, I want to start making some changes. And we'll look at that in a second. But in natural language, with the **Sidekick**'s help, you can change any of these experiences to work just the way you want them. At the base layer of the system are tools. So you know as well as anyone **Swix** that any **AI system** is only as good as the quality of data that it can pull in and the quality of action it can take. So before we launched our **beta** we worked very hard to make sure that we seated our tools with a bunch of very highquality and powerful integrations. So you know for instance this is real **Google search**. This is actual **Gmail**. And you can do very useful things with those. But also this is a platform for everyone. And as we got started talking to people in our **alpha community**, a whole bunch of sports use cases popped out and we realized if you want to build something cool for sports with AI, you need really high quality live data. So look at these **Formula 1**, **MLB**, **NFL**. These are tools that we've built. We've done a these are not data scraped off the web. This is a direct data feed integration. And because it's live and because it's high quality, you can build really powerful stuff. But tools is not something that we're just going to kind of control ourselves. The platform is open for tool builders to contribute tools that anyone on dreamer can use. So this is actually the place in the platform where I think software engineers, well number one we'd love for you to come and play with it. But software engineers are really going to build a lot of powerful stuff into the system. And we're actually sharing something for the first time on this podcast which is tool builders on **dreamer** get paid. So if you publish a tool to the platform and a lot of agents use it, you'll actually get paid in proportion to their usage. And we'd love for folks to come and give this a try. We've got good docs that help you get started and you can build things that you know scratch your own itch. For instance, someone built this **Ski Bum** tool which provides live snow conditions for a bunch of ski resorts. I'd love to show you how I've used that in a second. And also we have some tools partners where the tools themselves are paper use. So for instance, **Parallel Web Systems** is a premium tool. You can do really cool stuff with it. It's an agentic web research tool. And that one because it's expensive to operate is paid on a per usage basis. But if you're coming in to build agents on the platform, even the premium tools, you get a free trial. So you get a chance to actually try them out, make sure that the use case is good for you before you decide to sign up. So that's tools. So, we have the gallery, we have tools, and then the **sidekick** helps us put all of this together to build agents. We do that in the agent studio. You can also do this on your phone, but if I open up agent studio here on desktop, Sidekick is just going to start a conversation about what you want to build together. I'd love to show you one that I made recently. Let's do it.

</details>

### 会议应用困境与 Dreamer 的解决方案

**Swix**: 嗯，我们来看看一些你可能很关心的事情。

<details>
<summary>Original English</summary>

**Swix**: Um, let's look at something that hopefully is kind of near and dear to your heart. So,

</details>

**David Singleton**: **Dreamer** 平台最让我喜欢的一点，以及现在这个技术时代的特点是，如果你仔细想想，生活中有很多这样的事情：你有没有去过会议？我知道你肯定去过，对吗？大型会议都有自己的应用。这些应用通常是由代理机构构建的，而且它们通常非常昂贵。我也曾参与过一些此类应用的运营。你参加过多少次会议，发现它们的应用程序很好用？

<details>
<summary>Original English</summary>

**David Singleton**: One of the things I love about **Dreamer** and this kind of moment in technology is that if you think about it, there are all these things in your life where have you ever gone to a conference? I know you have, right? And big conferences have apps. And these apps are usually built by agencies and they're usually actually quite expensive to build. I've been involved in running some of these myself. And how many conferences have you been to where the app was good?

</details>

**Swix**: 说实话，

<details>
<summary>Original English</summary>

**Swix**: Honestly,

</details>

**David Singleton**: 没错。零个。

<details>
<summary>Original English</summary>

**David Singleton**: Exactly. Zero.

</details>

**Swix**: 是的，可能有一个吧。我参加过一个会议，它的应用还不错。我们 **Stripe**...

<details>
<summary>Original English</summary>

**Swix**: Yeah, maybe one. I've been to one conference that was pretty good. We we **strip**

</details>

**David Singleton**: 但重点是它们很少是优秀的软件，对吧？而且构建成本也很高。但它们很有趣，因为它们是情景性的。它们只用于一次活动，然后就不再相关了。

<details>
<summary>Original English</summary>

**David Singleton**: But the point is that they're rarely great pieces of software, right? And they're also expensive to build, but they're interesting because they're episodic. They last for this one thing. And then they're not they're not relevant anymore.

</details>

**Swix**: 这是一种糟糕的投资感觉，因为你知道它有时间限制。

<details>
<summary>Original English</summary>

**Swix**: It's so it's the worst feeling to invest in them because you know it's like it's got a limited date.

</details>

**David Singleton**: 绝对是。所以我决定在 **Dreamer** 上为你们的 **AI 工程师大会**构建一个会议应用。**Swix** 做了一件非常有远见的事情，那就是将大量会议数据以 **LLM** 可读的方式放在了网页上。有一个 **LLM.txt** 文件，还有一个 **JSON** 格式的所有会话的数据流。所以我使用了你去年会议的数据，通过在 **Dreamer** 中与我们的 **Sidekick** 对话，构建了这个智能应用。简单带你浏览一下，这就是我梦想中的会议应用。我一直希望在会议中能够搜索演讲者。我通常去参加会议是因为有我关心的演讲者。所以，你知道，**Swix**，你是那个我关心的演讲者。我可以在这里看到你和谁一起上台。比如 **OpenAI** 的 **Greg Brockman** 就在这里。这是他的会话。你看，Greg 和 Swix 是演讲者。那么，我们把它添加到我的日程中。很好。然后也许还有其他一些我可能会看到的。比如第二天，我记得有一些主题演讲。所以，“构建开放式代理网络”听起来很有趣。所以我把它添加到我的日程中。

<details>
<summary>Original English</summary>

**David Singleton**: Absolutely. So I decided to build a conference app for your **AI engineer conference** on **Dreamer**. One of the things that **Swix** has done, which I thought was very forwardlooking, is actually put a whole bunch of data about the conference on the web page in an **LLM** readable way. There's an **LLM.txt** file. There's a feed of all of the sessions in **JSON**. So, I used the data from your conference last year and built this intelligent app just by talking to our **sidekick** in **Dreamer**. So, just to give you a quick tour, this is my dream conference app. What I always want to do for conferences is I want to be able to search for speakers. I'm usually there because there is a speaker I care about. So, you know, Swix, you're the speaker I care about. I can actually see here who you're on stage with. So, here's here's **Greg Brockman** from **OpenAI**. And this is his session. And look, Greg and Swix are the speakers. So, let's add that to my schedule. Great. And then maybe there's a couple others I might see here. Like on day two, I remember there were some keynotes. So, "Building the open agentic web." That sounds fun. So, I add that to my schedule.

</details>

**Swix**: 她现在是 **Xbox** 的 **CEO** 了。

<details>
<summary>Original English</summary>

**Swix**: She's now **CEO** of **Xbox**.

</details>

**David Singleton**: 太棒了。

<details>
<summary>Original English</summary>

**David Singleton**: Awesome.

</details>

**Swix**: 这很有趣。

<details>
<summary>Original English</summary>

**Swix**: Which is interesting.

</details>

**David Singleton**: 太酷了。所以，我已经选出了一些我关心的会话。这通常是我参加任何会议应用能做到的极限了，但当然，你还有会议的其他部分需要弄清楚。所以这里就是你在 **Dreamer** 中构建的这些东西的固有智能发挥作用的地方。所以我将点击“引导我”。**Dreamer** 的 **Sidekick** 实际上解析了整个日程，并找出了其中一些主题，我可以在这里选择我感兴趣的。我绝对对代理感兴趣。我绝对对代码生成以及推理和 **RL** 感兴趣。所以现在我将说“构建我的日程”。它会遍历会议的每个时间段，并在我可以参加的活动中，根据我的兴趣选择它认为最适合我的。它还会利用它对我自己的记忆，这是 **Dreamer** 的一部分，来理解我可能最喜欢什么。你知道，每个时间段都有一个 **LLM** 提示在运行。所以这不会超级快，但大约 30 到 40 秒就能完成。我就会有一个特别定制的会议日程。就像我说过的，这是我梦想中的会议应用。这正是我一直想要的，我昨天早上就把它构建出来了。我在会议间隙完成的。我想我总共花了 25 分钟的实际时间。我在几个小时内完成了它。这是我的会议日程。我可以在日历视图中看到它。这是我周二应该做的。这是我周三应该做的。没有冲突，但你知道，它可能不会涵盖所有事情。这就是了。在 **Dreamer** 中构建。所以我们来看看实际的构建体验是怎样的。这就是我构建它的实际账户。哦，当然我应该说，你在 **Dreamer** 上构建的任何东西都可以在你的手机上运行。所以，这是我手机上的 **AI 工程师大会**应用。它拥有所有相同的功能，当然，这是查看我的日程的最佳地点。

<details>
<summary>Original English</summary>

**David Singleton**: So cool. So, so I've gone through and picked out a couple of sessions that I cared about. That's as far as I usually get with any conference at, but of course, you've got the whole of the rest of the conference to figure out what to do. So here is where the native intelligence of of these things you build in **Dreamer** can come in. So I'm going to click "guide me". So **Dreamer**'s **sidekick** actually parsed out the whole schedule and figured out what some of the themes are and I can choose what I'm interested in here. I'm definitely interested in agents. I'm definitely interested in **code generation** and also reasoning and **RL**. So now I'm going to say "build my schedule". So what this is doing is it's going across every time slot for the conference and it's choosing among the things I could go to which one it thinks is best for me based on my interests. It also uses its own memory of me that's part of **Dreamer** to understand what I might like best. And you know there's an **LLM** prompt running for each one of these time slots. So this is it's not super fast but it'll be done in about 30 or 40 seconds. And I'm going to have a special custom schedule for the conference. This, like I said, is my dream conference app. is exactly what I've always wanted and I was able to build this yesterday morning. I did it between some meetings. I think I spent a total of 25 minutes of wall clock time on it. I did it over the course of a couple of hours. And here is my schedule for the conference. I can see it in a calendar view. This is what I should do on Tuesday. This is what I should do on Wednesday. No conflicts but you know it may not go to every single thing. And there you have it. Built in you know **Dreamer**. So let's take a look at what the building experience actually looks like. So this is the the actual account that I made it on. Oh, of course I should say anything you build on **dreamer** also works on your phone. So here is my **AI engineer conference** app right here on my phone. Got all the same functionality and of course this is the best place to jump into my schedule.

</details>

**Swix**: 是的。

<details>
<summary>Original English</summary>

**Swix**: Yeah. Um so

</details>

**David Singleton**: 你甚至可以生成一个关于它的播客，完全是多模态的。

<details>
<summary>Original English</summary>

**David Singleton**: You could generate a podcast about it just completely multimodal.

</details>

**Swix**: 绝对是。没错。对我来说，这就是我外包的原因。我的意思是，我为什么要发布 **LMTXT**，**JSON**，因为你不能在 2025 年举办一个工程师会议，却不让工程师做他们想做的事情。

<details>
<summary>Original English</summary>

**Swix**: Absolutely. Right. To me. I mean, this is why I outsource. I mean, why I I posted the **LMTXT**, the **JSON**, because you cannot run an engineer conference in 2025 and not let engineers do whatever they want.

</details>

**David Singleton**: 是的。而且既然所有会议应用都很糟糕，我只想放一个最小可行应用，让人们随心所欲。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. And since all conference apps suck, I'm just going to put up a B minimum viable app and just let people do whatever they want.

</details>

**Swix**: 完全正确。而且在 **Dreamer** 上最酷的是，我把这个发布到了应用商店，你可以使用它。所以，你有一个符合我对会议应用品味的。我觉得它很酷，但你可能想要一些不同的。在这种情况下，你只需要告诉 **Sidekick** 如何改变它。所以我们很快来看看……

<details>
<summary>Original English</summary>

**Swix**: Totally. And the cool thing about this on **Dreamer** is I published this to the gallery and you can use it. So, you've got one that's built to my taste of conference apps. I think it's pretty cool, but you might want something different. In which case you just start telling the **sidekick** how to change it. So let's just very quickly look at

</details>

**David Singleton**: 很棒的是你也可以分叉它，对吗？比如我可以发布你的那个，然后说这是基础的启动器。它有很好的默认设置，但你可以自定义任何东西。

<details>
<summary>Original English</summary>

**David Singleton**: what's great is also you can fork it, right? Like I can publish I can publish your one and go this is the base starter. It's it's got good defaults but go customize whatever.

</details>

**Swix**: 没错。没错。所以我们来看看我实际是如何构建的。这是真实的。所以我将说“进行更改”。我们现在看到的这个体验是我们的代理开发工作室。就像我说过的，你也可以在手机上进行。事实上，我这个是从桌面开始的。我们来看看我的实际提示。我说“让我们创建一个名为 AI 工程师日程规划器的代理”。它应该是一个为 **AI 工程师大会**定制的日程规划器。我不会把这些都读出来，但你明白我的意思，它会告诉它从哪里获取数据。所以这是第一个提示，实际上在我给出这个提示后，我的 **Sidekick** 只运行了一次，这个应用的简单版本就已经运行起来了。所以 **Sidekick** 就像一个专业的软件工程师，我们非常努力地让它能够为那些可能没有任何工程经验的人构建功能性应用。所以你看，下面我们有技术性的构建日志，但你可以把它们隐藏起来。Sidekick 在构建时，实际上会将所有从框架中产生的东西翻译成你能读懂的英文。顺便说一下，这种英文是根据你 **Sidekick** 的个性来定的，这很有趣。我们构建代理和智能应用的方式，与你在其他平台上看到的可能有些不同，原因有几个。首先是构建过程。Sidekick 做的第一件事，是理解你设置的所有代理。它理解所有工具，然后会制定一个计划，如何实现你的目标，如何确保它实际拥有完成目标所需的数据和能力。它偶尔会拒绝。如果它无法完成你要求的事情，它会告诉你，我做不到。它需要另一个工具。这对所有工具构建者来说，都是一个很好的起点，可以构建一个新工具。所以，它首先会弄清楚如何做。然后它会构建它。然后它会实际测试它。所以它会实际确保它生成的东西正在实现你的目标。你可能比任何人都清楚，任何时候，只要你能让任何现代最先进的编码模型进入一个循环，让它能够进行更改并感知自己的输出，然后修复 bug，奇迹就会发生。所以这些构建，在 **Dreamer** 上第一次构建通常需要 10 到 15 分钟，这比你可能在其他平台上看到的要长一些，但它创建的第一件东西在大多数时候都能工作。当然，当你开始进行较小的更改时，你可以让它以你喜欢的任何方式调整用户界面。那些会快得多。只是给你一个概念，对于这个，我要求它“放一个标志”。我给了它一个位于静态文件中的标志文件。使用它作为标题。所以对于那些真正想深入了解更多细节的人，我们在这里提供了一个强大的 **IDE**。所以我可以在这里看到生成的代码。代码的一些部分比其他部分更容易访问，比如提示。所以这是由一个强大的 **LLM** 用来选择日程的提示。我可以直接在这里阅读它。如果我想，我可以不通过 **Sidekick** 而直接编辑它。所以这非常好。

<details>
<summary>Original English</summary>

**Swix**: That's right. That's right. So let's take a look at how I actually built this. This is real. So going to say make changes. This experience we're looking at now is our agent development studio. Like I said you can do this on your phone as well. And in fact this one I started out on desktop. Let's look at my actual prompts. I said let's make an agent called **AI engineer schedule planner**. should be a custom schedule planner for the **AI engineer conference**. I'm not going to read this all out, but you get you get the point and it told it where to get the data from. So that was the first prompt and actually after I gave it that prompt, I actually had a simple version of this app working after the **sidekick** took one turn. So the sidekick is a like a professional software engineer and we've worked very hard to make this work and build functional apps for folks that might not have any engineering experience whatsoever. So you know down here we have build logs that are technical but you can hide those away and sidekick as it is building will actually translate everything that is coming out of the harness into English that you can actually read. And by the way this English is in the personality of your **sidekick** which is fun. And the way that we build agents and **agentic apps** it's a little different to what you might have seen in some other platforms for a couple of reasons. One just the build process. The very first thing that **Sidekick** does, it understands all the agents you've got set up. It understands all the tools and it will come up with a plan for how to realize your goal, how to make sure it actually has the data and the capabilities to complete it. It will occasionally refuse. If it can't do what you're asking, it will tell you, I can't do that. It needs another tool. And that's a good jumping off point for any of the tool builders out there to build a new tool. So, it'll first figure out how. Then it will build it. And then it will actually test it. So it will actually make sure that the thing that it has generated is realizing your goal. And you probably know as well as anybody that anytime you can get any modern state-of-the-art coding model into a loop where it can make changes and perceive its own output and then fix bugs, magic happens. So these builds, the first build will often take 10 to 15 minutes on **Dreamer**, which is a little bit longer than you might have seen on some other platforms, but the first thing that it creates will work most of the time. And then of course as you start making smaller changes you can like ask it to tweak the UI in any way that you like. Those are much faster. And just to give you a sense for this one here's something I asked put a logo. I gave it a logo file in static files. Use that as a title. So for folks that actually really want to dig into a bit more detail. We've provided a powerful **IDE** here. So I can actually see here's the code that was generated. And some pieces of the code are more accessible than others like the prompts. So this is the prompt that's used by a powerful **LLM** in order to do that schedule picking. And I can actually read it here directly. I can edit it without having to ask the **sidekick** if I want to do that. So this is very nice.

</details>

**David Singleton**: 这是为更复杂的用户准备的。

<details>
<summary>Original English</summary>

**David Singleton**: This is for the more the more sophisticated users.

</details>

### Dreamer 的托管服务、社区分享与自动化 To-Do List

**Swix**: 这是真的。其他与 **Dreamer** 不同之处在于，一旦你在这里构建了东西，它就可以立即使用了。我们提供托管。所以你不用担心从数据库提供商那里获取数据库、注册、获取 **API 密钥**。你也不用担心你的 **LLM** 提供商令牌。所有这些都在平台托管，你可以自己使用。你可以分享到应用商店，供其他人在此基础上发挥。你也可以与你的朋友和同事分享，让他们使用你的代理或智能应用实例。我们看到这在我们的社区中发生了很多。我们看到很多人为自己的个人生活构建了一些小应用，并与他们的伴侣分享。我们看到人们为他们的团队在工作中构建了一些生产力应用，并在他们之间分享。我们实际上在公司内部也经常这样做。所以，目前，我们基本上是通过 **Dreamer** 代理来运营公司，处理各种重要的事情。一个很好的例子就是我们的等待名单。人们正在注册。每当有人注册我们的等待名单时，一个 **Dreamer** 代理就会实际研究那个人。我们正在寻找那些能够构建代理而非技术性很强的人，让他们进来并给我们提供大量反馈，我们优先让这些人从等待名单中脱离。

<details>
<summary>Original English</summary>

**Swix**: This is true. The other thing that is different about **Dreamer** is once you've built something here, it's ready to go. We host it. So you don't have to worry about getting a database from a database provider, signing up, getting **API keys**. You don't have to worry about your **LLM provider tokens**. All of that is hosted on the platform and you can use it yourself. You can share it to the gallery for other people to riff on it. You can also share it with your friends and co-workers to use your instance of the agent or **Agentic app**. And we're seeing that happen a lot in our community. We've seen a whole bunch of folks who built little applications for their personal life and shared them with their significant other. We've seen people who are building little productivity apps for their team at work and sharing it among them. And we actually do this a lot inside of the company. So, at this point, we pretty much run the company on **dreamer agents** for all kinds of important things. Maybe a good example of that is our wait list. People are signing up. Every time someone signs up for our wait list, a **dreamer agent** will actually research that person and we're looking for folks who are builders, not super technical to build agents and come in and give us a lot of feedback and we prioritize bringing those people off of the wait list first.

</details>

**David Singleton**: 我有一个快速问题，就那个，它可能不会再提了。你觉得像 **ZoomInfo** 这样的丰富 **API** 有用吗？我清理了一下。

<details>
<summary>Original English</summary>

**David Singleton**: Just a quick question on that one just there's it may not come up again. Do you find enrichment **APIs** to be useful like the **zoom info**? I clear a bit.

</details>

**Swix**: 丰富化是一个非常常见的用例，嗯，在 **Dreamer** 上。**Dreamer** 上的任何应用程序都可以启动一个子代理来执行特定任务。所以这实际上是一个强大的代理平台，它在自己的 **VM** 内部运行。我们称它们为 **Sidekick** 任务，因为它们实际上是在 **Sidekick** 的上下文中运行的。我稍后会更多地谈论 Sidekick。而丰富化是一个非常常见的用例。Sidekick 任务的酷之处在于，它可以使用平台中的所有工具，也可以使用公共数据。所以，我们的平台上的丰富化功能经常通过网络上可以找到的公共数据来实现。有一些工具可以从各种定制系统中获取人员数据，所以这运行得很好。但实际上你会惊讶。我的意思是，如果有人想构建一个 **ZoomInfo** 工具，我们今天还没有。我们很乐意在平台上看到它，我确信它会非常强大。但我们也看到这个强大的代理平台可以获取大量数据。在工具方面，这使得体验更好。我们不断添加更多工具，因为社区中的人们正在构建并发布它们。我们仔细审查这些工具，然后它们就会对所有人开放。昨天我们添加了 **Granola**，那非常酷。所以，我当时在和……实际上，我团队的 **Sarah** 今天早上在和一位在平台上构建的人交流，他们实际上有一个他们构建的智能应用，它是一种神奇的 To-Do List。所以，他们把事情放在他们的 To-Do List 上，每件事都会启动一个 **Sidekick** 任务，以找出如何推进事情。有时它会完全完成，通常是通过调用平台上的另一个代理来完成，有时它只是研究并帮助他们迈出第一步。

<details>
<summary>Original English</summary>

**Swix**: Enrichment is a very common use case on **Dreamer**. Any application on **Dreamer** can kick off a sub agent to do a particular task. So this actually is a powerful agentic harness that runs inside of its own **VM**. We call them **sidekick tasks** because they actually run in the context of the sidekick. I'll talk more about sidekick in a second. And enrichment is a very common use case. And the cool thing about a **sidekick task** is that it has access to all the tools in the platform but also public data as well. And so very frequently enrichment on our platform happens using public data that it can be found in the web. There are some tools for getting people data from various bespoke systems and so that works pretty well. But actually you'd be surprised. I mean we would love if someone out there would like to build a **ZoomInfo** tool, we don't have one today. We'd love to see that on the platform and I'm sure it will be very powerful. But we're also seeing that this powerful agentic harness can pull a lot of data in. You on that note of tools that make experiences better. We're constantly adding more tools because people in the community are building them and publishing them. We review the tools carefully and then they go live for everybody. Yesterday we added **Granola** and that was pretty cool. So, I was talking to well actually **Sarah** on my team was talking to someone building on the platform this morning and they actually they have an **agentic app** that they build which is a kind of magic to-do list. So, they put stuff on their to-do list and for each thing it kicks off one of these **sidekick tasks** to figure out how to move the ball forward thing. Sometimes it will complete it entirely often by calling another agent on the platform and sometimes it just kind of researches it and helps them take the first step.

</details>

**David Singleton**: 你知道这是 **Sam Altman** 对 **AI** 应用的第一要求吗？就是那种自动完成的 To-Do List。是的，自动完成的 To-Do List 是很多人在 **Dreamer** 上构建并从中受益匪浅的东西，他们发现它确实非常……

<details>
<summary>Original English</summary>

**David Singleton**: Do you know this is **Sam Altman**'s number one ask for an **AI app**? It's the self-completing to-do list. Yeah, the self-completing to-do list is something that a lot of people have built on **Dreamer** and are getting a lot of use out of and finding it actually genuinely.

</details>

**Swix**: 我应该试试那个。

<details>
<summary>Original English</summary>

**Swix**: I should I should try that.

</details>

**David Singleton**: 嗯，请务必尝试。你甚至可以在应用商店找到一些可以混搭的。所以，他今天早上说他已经在 **Dreamer** 上构建了这个自动完成的 To-Do List，但他昨天连接了 **Granola** 工具，现在发生了一些真正神奇的事情，那就是当他在会议中说他要做某事时，它就会神奇地出现在他的 To-Do List 上，然后它就可以神奇地完成。正如我提到的，**Dreamer** 上的所有代理、所有应用实际上都可以协同工作。所以我们的编码代理在构建它们时做了一些非常特别的事情，它将每个体验的内部结构暴露给系统，然后 **Sidekick** 可以操作这些内部结构来完成任务。所以他构建了另一个代理，他用它来招聘。它会跟踪候选人，还有一个迷你 **CRM** 功能，所以他可以介绍候选人互相认识。他今天早上告诉我们，他昨天在会议上承诺要做的事情，在 **Granola** 上被记录下来，出现在他的神奇 To-Do List 上，而他的神奇 To-Do List，就像是“介绍一个人进行招聘”，然后它就使用了他的招聘代理来完成这项任务。

<details>
<summary>Original English</summary>

**David Singleton**: Mhm. Please do. And you'll even find some in the gallery that you can remix. So, he was saying this morning that he's he built this self-completing to-do list on **dreamer** already, but he connected the **granola tool** yesterday and now something really magical happens, which is when he says in meetings that he's going to do a thing, it magically shows up on his to-do list and then it can magically get completed and then as I mentioned all the agents, all the apps on **dreamer** can actually work together. So our coding agent as it builds them does something very special where it exposes the internals of each of the experiences to the system and then **sidekick** can manipulate those to get stuff done. So he has built another agent which he uses for recruiting. It kind of keeps track of candidates and also it's got a kind of mini **CRM** function so he's able to introduce candidates to each other. He told us this morning that something he committed to do in a meeting that was recorded on **Granola** yesterday showed up on his magic to-do list and his magic to-do list, it was like introduce a person for recruiting, used his recruiting agent to get it done.

</details>

### 隐私、安全与平台生态的愿景

**David Singleton**: 嗯，这就是梦想。这就是我们创办公司的原因。你确实可以构建和使用这些非常强大的定制体验，它们通过协同工作来自动化你的生活。我很乐意稍微谈谈它们如何协同工作。所以显然，拥有能为你工作的软件非常酷，但它只有在你信任它时才有用，对吗？所以，隐私和安全对我们来说非常重要。让这些东西易于访问且有用，同时又值得信任，这是很难的。所以我们拥有的这个模型运作得非常好，那就是 **Sidekick** 是这里所有一切的核心。所以它既是你的伴侣，又是你的帮手，但它也是系统中的交通警察。所以当一个代理想在 **Dreamer** 中与另一个代理协作时，它不会直接进行。它会通过 **Sidekick**。让 Sidekick 去做这件事，Sidekick 理解所有与我作为用户设定的期望，关于代理能做什么，我授权它们使用哪些工具。它会确保正在发生的一切都与我的利益保持一致。你知道，这是我为解决这个领域问题带来的背景知识的一部分。我多年来一直在努力保护非常重要的信息安全。所以当我们开始思考这个问题时，我们意识到我们实际上必须构建一个有点像操作系统的东西。你知道，**Sidekick** 就像内核，代理和应用就像用户，不同的环。

<details>
<summary>Original English</summary>

**David Singleton**: Um, and this is this is the dream. This is why we started the company. It really is the case that you can build and use these very powerful bespoke experiences that can automate your life by working together. And I'd love to talk a little bit about how they work together. So obviously it's really cool to have software that will work on your behalf, but it's only useful if you can trust it, right? So privacy and security is very important to us. Making these things accessible and useful while also being trustworthy is hard. So the model that we have which is working very well is that the **sidekick** is at the core of everything here. So it is both your companion your helper but it's also the traffic cop in the system. So when when one agent wants to work with another agent in **dreamer**, it doesn't do it directly. It does it via the sidekick. Ask the sidekick to do the thing and the sidekick understands both everything all the expectations that have been set with me as a user about what agents can do, which tools I've given them permission to use. And it will make sure that whatever is is going on is actually aligned with my own interests. And you know that's part of the background that I bring to this problem domain. I've worked for years keeping very important information safe and secure. And so as we started to think about this problem, we realized that we actually had to build something that's a bit like an operating system. You know, the **sidekick**'s like the kernel, the agents and apps are like user different rings.

</details>

**Swix**: 没错。因为如果你试图只挑选其中一部分，你实际上无法让它在大规模人群中工作。你可以构建一些小型的五代码应用，但它们会随意抓取你的所有数据。它们无法协同工作。你必须投入到基础核心中，才能让它为人们良好地工作。这就是我们一直在做的，并且一直很有趣。我想提的另一件事是，嗯，我显然谈到了两件事：工具和智能应用。我们真正将 **Dreamer** 设计成一个生态系统和一个平台。我最喜欢的一句关于平台的引言，我认为是来自 **Bill Gates** 的，那就是你只有为参与和使用平台的人创造比平台本身创造的更多价值时，你才能成为一个平台。这就是我们的目标。所以我们每一步都在思考，如何确保其他人从 **Dreamer** 中获得的价值甚至比我们更多。所以在这个方面，我之前提到工具开发者可以获得报酬，人们可以构建满足他们需求的代理并与他人分享。我们已经在思考他们如何也能将这些货币化。在此背景下，我们今天正在推出 **Builders-in-Residence** 计划。所以，已经有很多人正在构建非常酷的东西并贡献到应用商店中，但我们受到了其他公司项目的启发，那些项目有驻场艺术家，那些非常有创意的人可能会有公司内部或生态系统中的人没有的想法。所以我们正在寻找有有趣想法的创意人士，他们希望真正弄清楚如何将他们的创造力应用到当今最前沿的技术中，来与我们合作。所以，如果你访问 **dreamer.com/lenpace**，你会发现——我们喜欢 **Latent Space**——你会找到一个链接，既有我们的工具构建者信息，也有我们的驻场构建者计划。对于驻场构建者，我们会让你快速脱离等待名单，构建一个代理，然后对于少数最有创意的人，我们会付费让你构建代理。你可以直接与我们的团队合作。你知道，这就像玩乐高。所以，你知道，我们已经有一些基本积木了，但如果你需要一个圆形的方向盘而我们还没有，我们会为你构建。我们真的希望被这些构建者和驻场者启发。这个乐高比喻很常见，还有一个我称之为“大师构建者”的东西。实际的 **乐高公司** 有他们雇佣的大师构建者，用来激励人们并在社交媒体上发布。

<details>
<summary>Original English</summary>

**Swix**: Exactly. Because if you try to pick off just one piece of this, you can't actually make it work for people at scale. You could build little vibecoded apps, but they're going to grab all your data willy-nilly. They won't be able to work together. You actually have to invest in the fundamental core in order to make it work well for people. That's what we've been doing. And it's been a lot of fun. One other thing I wanted to mention is I've obviously talked about two things tools and **aentic apps**. We really designed **Dreamer** to be an ecosystem and a platform. And one of my favorite quotes about platforms. I think it's from **Bill Gates** is that you can only be a platform if you create more value for the folks participating and using the platform than than the platform itself creates. And that's our goal here. So we at every step have been thinking about how do we make sure that other people are deriving even more value from **dreamer** than we are. So in that vein, I already mentioned tool builders get paid and people can build agents that solve their needs and share them with others. And we are already thinking about ways that they can actually monetize those as well. Against that backdrop, one of the things that we are launching today is our **builders in residence program**. So, there are tons of people building really cool stuff and contributing it to the gallery already, but we've been really inspired by programs we've seen at other companies where artists might be in residence, people that are very creative and might have ideas outside of what the folks at the company or in the ecosystem already have. And so we're looking for creative people who have fun ideas and you know want to really figure out how to apply their creativity at the cutting edge of technology today to come and work with us. So if you go to **dreamer.com/lenpace** you'll find well we love **Latent Space** you'll find a link both to our tool builder information and our builder and residence program. And for builders and residents, we'll let you in off the wait list quickly, build an agent, and then for a small number of of the most creative folks, we're going to pay you to build agents. You can work directly with our team. You know, this is like building Legos. So, you know, we've got some of the basic blocks together already, but if you need a round steering wheel and we don't have one already, like we'll build it for you. We really want to be inspired by by these these builders and residents. This Legos thing is pretty common as an analogy and there's a there's a thing I call the **master builder**. Which the actual **Lego company** has master builders that they employ to inspire people and post on socials.

</details>

**David Singleton**: 那正是启发我们的地方。说实话，我们讨论过 **乐高大师构建者计划**。所以这就是我们的驻场构建者计划。

<details>
<summary>Original English</summary>

**David Singleton**: That is exactly what inspired us as well. Honestly, we talked about the **Lego master builder program**. So that's our builder and resonance program.

</details>

**Swix**: 是的。

<details>
<summary>Original English</summary>

**Swix**: Yeah.

</details>

**David Singleton**: 嗯，最后再回到工具。就像我说的，今天任何人都可以来构建工具，如果你点击 **Latent Space** 链接。

<details>
<summary>Original English</summary>

**David Singleton**: Um and then finally back on on tools. Like I said, anyone can come in and build tools today if you follow the **latent space** link.

</details>

**Swix**: **dreamer.com/latenspace** 再次强调，将让你直接脱离等待名单。所以你可以立即开始构建。你可以通过发布到平台来盈利。这适用于所有人。到四月中旬，最好的工具将被添加到平台。我们有一个 **10,000 美元**的奖金，我们想颁发，真正的原因只是我们想激发所有人的创造力。所以我们很高兴这样做。

<details>
<summary>Original English</summary>

**Swix**: **Dreamer.com/latenspace** again will get you off directly off the wait list. So you can build right away. You can monetize by publishing onto the platform. That's for everyone. The very best tool that gets added to the platform by midappril. We have a **$10,000 prize** that we want to give out really because we just want to seed the creativity of everyone out there. So we're excited to do that.

</details>

### AI 商业模式与微支付的未来

**David Singleton**: 是的。你知道这是一个完整的飞轮，对吧？更多的工具，更多的构建者，更多的第三类东西，代理，你知道，它们相互促进。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. And you know this is completely a flywheel, right? Like the more tools, the more builders, the more the third thing, agents, you know, it just feeds into each other.

</details>

**Swix**: 没错。

<details>
<summary>Original English</summary>

**Swix**: That's right.

</details>

**David Singleton**: 是的。关于支付的事情，我可能不会再提了，但我必须问前 **Stripe CTO** 关于支付的问题，因为你大概正在使用 **Stripe Connect**。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. Just on the payments thing because I probably won't touch on that again, but I have to ask the former **CTO** **Strip** on payments as presumably you're using **Stripe Connect**.

</details>

**Swix**: 是的。

<details>
<summary>Original English</summary>

**Swix**: Yeah.

</details>

**David Singleton**: 有没有什么痛点，因为人们对智能商务和微支付等事物非常感兴趣。稳定币可能在某个时候也会进入对话，但也许不是现在。

<details>
<summary>Original English</summary>

**David Singleton**: Um any pain points that you're because people are very interested in **agentic commerce** and **micro payment** and all these things. Presumably **stable coins** get into conversation at some point, but maybe not now.

</details>

**Swix**: 是的，我们对**智能商务**非常非常兴奋。我们采取的第一步是帮助世界上从未能够构建这类体验和软件的人，去构建符合他们热情的东西，并与世界分享并获得报酬。所以这就是我们平台上发生的所有商业活动。因此，我们不需要任何新东西来促进这一点。**Stripe Connect** 已经存在很长一段时间了，它是解决这类问题的完美方案。所以，嗯，我们首先对这一点感到兴奋。然而，很多人已经在 **Dreamer** 上做的事情，我们刚刚谈到了一个自动完成的 To-Do List。你想要完成 To-Do List 的很多方式，都是通过在现实世界中闭环来完成的，这会涉及到价值的交换。所以，我们有一些人已经在构建工具，这些工具确实涉及到资金流动，以完成那个闭环。到目前为止，我们只是想对所有协议保持开放和不可知。我真心认为现在这个时刻有点像早期的网络。我个人小时候就开始编程，我想我大约在 1995 年或 1996 年接触到互联网，那时候网络已经存在了，你知道 **HTTP** 是一种协议，但我也一直在使用其他协议，比如 **gopher** 和 **UUCP**，以及各种其他协议。所以重点是，网络、HTTP 和 **HTML** 只是众多协议中的一种，当然它成为了赢家，它很棒，但其他协议在当时也很有趣且可行。我认为智能商务的世界现在就是这样。

<details>
<summary>Original English</summary>

**Swix**: Yeah, we're really really excited about **Agentic Commerce**. The first step we're taking is help people in the world who have never been able to build these kind of experiences and software before to build stuff that meets their passions, share it with the world and get paid. So that's all commerce that happens on our platform. And so we don't need anything new to facilitate that. **Stripe Connect** has existed for quite a while and is the perfect solution for this kind of stuff. So we're excited about that first and foremost. However, a lot of the things that people are already doing on **Dreamer**, we just talked about a self-completing to-do list. A lot of the ways that you want to complete to-dos is by actually closing the loop in the real world, and that's going to involve the exchange of value. So, we have some folks that are building tools already that actually do have money move in order to to complete that that loop. So far, we just want to be open and agnostic to all the protocols out there. I honestly think this moment in time is a little bit like the early web. So I personally started coding as a kid and I think I got access to the internet in about 1995 1996 and back then the web existed you know **HTTP** was a protocol but there were also other protocols I was using all the time like **gopher** and **UUCP** and various others so the point is like the web **HTTP** and **HTML** was just one among many protocols and of course it became the winner and it's awesome but the others were also kind of interesting and viable at the time as well. And I think the world of **agentic commerce** is like this right now.

</details>

**David Singleton**: **ACP**。

<details>
<summary>Original English</summary>

**David Singleton**: **ACP**.

</details>

**Swix**: 没错。所有 **CPS**，你知道，在 **Dreamer** 上，我们希望人们能够构建利用所有这些东西的工具。但我确信在某个时候，一两个会脱颖而出成为赢家，然后我们将能够提供非常深入的支持。

<details>
<summary>Original English</summary>

**Swix**: Exactly. All the all the **CPS**, you know, on **Dreamer**, we hope that folks will build tools that kind of make use of all of these things. But I'm sure that at a certain point one or two will emerge as the winners and then we'll be able to build like really deep support in

</details>

**David Singleton**: 是的，这可能有点离题，但我确实在思考很多 **AI 公司**，尤其是那些 **AI 公司**，必须从基于席位（seat-based）切换到基于使用量（usage-based）的模式，因为当然，然后他们最终不得不稍微模糊利润，然后他们最终发明出他们自己的 **Robux** 等价物。

<details>
<summary>Original English</summary>

**David Singleton**: yeah this is like maybe a complete tangent but I do think about how a lot of these companies in **AI companies** in particular have to switch from seat based to usage based because of course but then then they end up having to sort of obscure the margins a little bit and then they inventing end up inventing their equivalent of **Robux**

</details>

**Swix**: 嗯，他们会说，“好吧，好吧，每个公司都应该有自己的货币。”然后它就很快变成了一个代币，或者……

<details>
<summary>Original English</summary>

**Swix**: uh where they're like well okay well every company should have their own currency And it's like very shortly to a token or

</details>

**David Singleton**: 我想，“好吧，这到底会如何收场？”我真的无法预见下一步，比如这会是混乱吗？这会是……

<details>
<summary>Original English</summary>

**David Singleton**: and I'm like, okay, well, where does this end? I can't really play out the next step as to like, is this chaos? Is this

</details>

**Swix**: 是的。好的。

<details>
<summary>Original English</summary>

**Swix**: Yeah. Okay.

</details>

**David Singleton**: 嗯，我认为它有点像狂野西部。我不是说它完全无序，但未来可能发生的事情太多了。现在，关于它将如何落地，**奥弗顿之窗**非常宽广。我非常高兴能够构建一个能够利用所有这些机会的平台。我们将继续为用户服务，确保最终出现的东西能够良好运作。

<details>
<summary>Original English</summary>

**David Singleton**: Well, I think it is kind of like the **wild west**. I don't mean that in a completely disorganized way, but there's just so many things that could happen from here. The **Overton window** is very wide right now for how this might land. And I'm just very excited to be building a platform that can take advantage of all of those opportunities. and we're just going to be there working for our users to make sure that the things that emerge work.

</details>

### Dreamer：智能代理的操作系统

**Swix**: 你将拥有消费者，你将成为应用商店的操作系统，拥有一切。

<details>
<summary>Original English</summary>

**Swix**: You're going to own the consumers, you're going to be the **OS** for the app store for everything.

</details>

**David Singleton**: 所以，思考这个问题的一种方式是，**Dreamer** 实际上使用了所有最先进的模型。作为用户，你无需考虑是应该使用 **Opusport 6** 还是 **OpenAI** 的 **54 模型**。我们正在持续进行评估等工作，以确保最好的东西在那里供你使用。你只需在平台上构建，并且知道随着世界的变化，你会得到适合你的正确东西。嗯，我认为这是让人们能够大规模利用这项技术所需要的。我很乐意向你展示我构建的另一个例子。我们来做吧。这是另一个只在特定时刻有效的软件例子。所以最近我和一群朋友去滑雪旅行了。

<details>
<summary>Original English</summary>

**David Singleton**: So, one of the ways to think about this is **Dreamer** actually uses all of the state-of-the-art models. As a user, you don't have to think about should I be using, you know, **Opusport 6** or should I be using the **54 model** from **OpenAI**. we are continually doing evals and so forth to make sure that the best things are there for you. You can just build on the platform and know that as the world ships around, you're going to get the right stuff for you. Um, and I think that's something that is needed to actually have folks take advantage of this technology at scale. I'd love to show you another example of something I built. Let's do it. This is another example of software that just lasts for a certain moment in time. So recently I went on a ski trip with a bunch of friends.

</details>

**Swix**: **Ski Bum**。嗯，所以它使用了 **Ski Bum**。是的。

<details>
<summary>Original English</summary>

**Swix**: **Ski bum**. Uh so it uses **ski bum**. Yes.

</details>

**David Singleton**: 我去 **Big Sky** 滑雪旅行了，我以前从未去过那里，我为我们做了这个智能小应用。你可以看到它显示“正在加载 **Big Sky** 条件”。所以它实际上正在调用我刚刚向你展示的 **Ski Bum** 工具，该工具已发布在我们的应用商店中。所以这是什么呢？这是一个只为我们周末旅行而开发的小应用。它使用生态系统中的那个工具显示 **Big Sky** 所有缆车的当前状态。它显示即将到来的周末的天气预报。它显示了我们的住宿地点。这就像我的团队住的地方。这只是为我们准备的，还有很多餐饮信息，其中一个朋友，他对 Big Sky 很了解，他把这些信息整理在一起。所以，我能够使用这个应用，将链接分享给我的朋友们。他们当时还没有用 **Dreamer**。我只是通过 **iMessage** 发送给他们，他们就可以在手机上使用一个版本。当然，最厉害的是这个。我以前和朋友们去过滑雪旅行和其他周末冒险。人们会为不同的事情付费，到周末结束时，总是很难弄清楚谁该付钱给谁来结账。所以我们在这个周末使用了它。我们把所有的开销都加进去了。嗯，别看太仔细，这是真实数据。别看太仔细。然后在旅行结束时，我们按下“分摊”，我们结清了账，完成了。所以这是另一个例子，因为我们在现实世界中为东西付费了。就像，“好吧，这个人需要付给那个人 20 块钱。这个人已经付够了，”对吧？所以，它只是帮助我们结清了账。我们没有在 **Dreamer** 上进行资金流动。你可以这样做。事实上，如果你是一个工具构建者，正在思考这个并感到兴奋，那就来构建一个工具来做这些事情吧。我们真的把我们的工具构建者视为设计伙伴。

<details>
<summary>Original English</summary>

**David Singleton**: I went on a ski trip to **Big Sky**. I'd never been there before and I made this little intelligent app for us. And you can see it says "it's loading **Big Sky** conditions". So it's actually calling the **Ski Bum** tool that I just showed you which is published in our in our gallery. So what is this? This is a little app that was just for our weekend trip. It shows the current status of all the lifts of **Big Sky** using that tool from the ecosystem. It shows the forecast for the upcoming weekend. It shows our accommodation. This is just like where my group was staying. This is just for us and also a bunch of dining information that one of our friends put together who's an expert on **Big Sky**. So, I was able to take this app, share the link with my friends. They weren't on **Dreamer** yet. Just send it to them on **iMessage** and they get a version they can use on their phone. And of course, here's the real kicker. So, I've been on ski trips before and other weekend adventures with my friends. People pay for different things and at the end of the weekend it's always a pain to figure out who needs to pay who to settle up. So we used this during the weekend. We added all of our expenses in here. Too closely it's a real data. Don't look too closely. And then at the end of the trip we press split and we're we settled up and we're done. So there's another examp because because we paid for stuff in the real world. It was like, okay, this person needs to pay that person 20 bucks. This person already paid enough, right? So, it just helped us all settle up. We didn't move the money on **Dreamer**. You could do that. And in fact, if you're a tool builder thinking about this and getting excited like come build a tool to do that stuff. We really think of our tool builders as design partners.

</details>

### 金融代理应用与银行整合

**Swix**: 是的，我有这个工具。我讨厌……我用 **Bank of America**。我讨厌银行，我讨厌那个应用。我讨厌银行网站，简直糟透了。所以，就给我构建一个，在 **Plaid** 之上构建一个东西，对吧？然后就……

<details>
<summary>Original English</summary>

**Swix**: Yeah, I got I got the tool. I hate I use **Bank of America**. I hate bank I hate the app. I hate the banking websites just horrible. So, just build me like build a thing on top of **Plaid**, right? And then just

</details>

**David Singleton**: 所以由银行应用代码。

<details>
<summary>Original English</summary>

**David Singleton**: so code by banking app

</details>

**Swix**: 已经有一个工具可以做到这一点了。所以 **Attain Finance** 是我们社区中的一个构建者开发的工具，它使用像 **Plaid** 这样的安全系统来访问你的财务数据，你今天就可以在 **Dreamer** 上使用这个工具构建强大的个人财务代理。就像我说的，我们仔细审查工具。所以在将 **Attain Finance** 引入平台时，我们确实与那家公司进行了相当详细的安全审查，以确保如果人们用它构建东西，它会运行良好。所以是的，去看看吧。我想我相当确定它连接到 **Bank of America**，所以你将能够构建你一直想要的应用。

<details>
<summary>Original English</summary>

**Swix**: there's already a tool for that. So **Attain Finance** is a tool a builder in our community built and it uses a secure system like **plaid** to access your financial data and you can build powerful personal finance agents on **dreamer** today using this tool. And like I said we review tools carefully. So when bringing **Attain Finance** onto the platform, we did actually quite a detailed security review with that company to make sure that if folks build stuff with it, it's it's going to work well. So yeah, check that out. I think I'm I'm pretty certain it connects to **Bank of America**, so you'll be able to build the the app that you wanted already.

</details>

### Dreamer 的模型选择、工具库与合作伙伴策略

**David Singleton**: 是的，我想就几点深入探讨，也许可以向大家强调，因为我花更多时间在 **Dreamer** 上。所以我们正在努力，你代表你的用户做出选择，因为他们是消费者。所以可能不那么技术性，对吧？但显然，我们的高级用户可以根据需要覆盖。但它不仅仅是 **LMS**。它也是转录。它就像所有这些都是第一方策展的一套“这是关于事物的内部意见”，对吗？这个列表是什么？有没有这样的……

<details>
<summary>Original English</summary>

**David Singleton**: Yeah, there's a couple of points I wanted to sort of dive in on, maybe highlight to folks because obviously I spent more time with **Dreamer**. So we're making a point where you choose on behalf of your users because they are meant to be consumers. So maybe less technical, right? But obviously people can power our users can override if they need. But it's not just **LMS**. It is also the the transcription. It is all like there's there's a first party curated set of here's the house opinion on what the thing is, right? Is what's the list? Is there like

</details>

**Swix**: 是的。所以实际上，如果你查看工具库，第一方策展的工具都是那些带有灰色图标的。所以，我们有一个内置的图像理解工具、图像生成工具、**RSS** 探索工具、文本转语音工具等等。

<details>
<summary>Original English</summary>

**Swix**: Yeah. So actually if you look in the tool gallery, the first party kind of curated set are all the ones that have these grayscale icons. So, we have a built-in tool for **image understanding**, for **image generation**, for **RSS exploration**, **text to speech**, and so forth.

</details>

**David Singleton**: 食谱。

<details>
<summary>Original English</summary>

**David Singleton**: Recipes.

</details>

**Swix**: 嗯，我们确实有一个内置的食谱工具。结果发现，我们的 **alpha** 用户中很多人想做关于烹饪的事情。嗯，你可以从网上抓取好的食谱，但我们很快就能找到一个好的食谱库。

<details>
<summary>Original English</summary>

**Swix**: Uh, we actually do have a built-in recipes tool. It turns out that a lot of people in our **alpha** wanted to do stuff for cooking. Um, and you know, you can scrape the web to get good recipes, but we were able to quite quickly find a good repository of recipes

</details>

**David Singleton**: 这在这里运作得很好。所以，这些背后的意义是，我们将保持接口稳定，所以它们永远都能工作。但你知道，最好的翻译模型……你知道，有人使用这个翻译工具将中文播客翻译成英文。它非常强大。它可以处理非常长的文本。但今天的最佳翻译工具可能与明年某个时候的最佳翻译工具不同。我们只是要确保那个翻译工具始终非常接近最先进水平。所以你可以构建一些东西，并且知道它会持续良好地工作。当然，我们有些工具是有品牌的。你可能确实有偏好的购物方式。比如你可能喜欢 **Instacart**，这很好。你可以专门使用 **Instacart** 工具。

<details>
<summary>Original English</summary>

**David Singleton**: that works great here. So, the point behind these though is that we'll keep the interfaces stable, so they'll always work. But you know the best translation model and you know there are people using this translation tool to translate Chinese podcasts into English. It's it's pretty powerful. It can deal with very long text. But the best translation tool today might be different from the best translation tool sometime next year. And we're just going to make sure that that translation tool is always pretty close to state-of-the-art. So you can build something and you know it's going to continue to work well. Of course, some of our tools are branded. You may actually have a preferred way of buying groceries. Like maybe you prefer **Instacart** and that's great. You can use the **Instacart** tool specifically.

</details>

**Swix**: 是的，你的合作伙伴关系。我的意思是，我不知道你是否负责合作伙伴关系，但这对于任何想做交易的人来说都将是一笔横财。

<details>
<summary>Original English</summary>

**Swix**: Yeah, your partnerships. I mean, I don't know if you're ahead of partnerships, but this is going to be a bonanza for anyone want to do deals.

</details>

**David Singleton**: 我们有一个很棒的人负责我们所有的合作伙伴关系。嗯，这是你构建这样一个平台所必须做的一部分，才能让它为人们工作。我们已经完成了这项艰巨的工作。很多人与许多不同的公司交流，以确保你拥有核心的优秀工具。是的。当然，因为我们对工具构建者向平台贡献开放，所以这只会变得越来越好。

<details>
<summary>Original English</summary>

**David Singleton**: We have an amazing person who works on all of our partnerships. Um, and it's part of what you have to do to build a platform like this that's going to work for people. Like we've gone and done that schle. This is a lot of work. Everyone talks to lots of different companies. Um in order to make sure that you've got good tools at the core. Yeah. And then of course because we're open to tool builders contributing to the platform, this is only going to get better and better and better.

</details>

### 代理实验室与模型路由

**Swix**: 是的。我有一个观察，这与我一直追求的一个论点相符，我称之为“代理实验室”。

<details>
<summary>Original English</summary>

**Swix**: Yeah. One observation I have this this sort of maps to a thesis I've been pursuing which is what I've been calling an **agent lab**.

</details>

**David Singleton**: 嗯。

<details>
<summary>Original English</summary>

**David Singleton**: Mhm.

</details>

**Swix**: 你与模型实验室有所不同，因为你从不训练自己的模型，但你是路由评估层，是选择模型的主题领域专家。是的。

<details>
<summary>Original English</summary>

**Swix**: Where you're sort of different than a model lab in in in the sense that you never train your own models, but you are the router evaluation layer ex subject domain expert for choosing between models. Yeah.

</details>

**David Singleton**: 而且你明确地在做这些事情。所以，根据我的理解，每个代理实验室都会做一些类似的事情，比如“这是图像理解的端点，我们会为你路由，你不用担心。”

<details>
<summary>Original English</summary>

**David Singleton**: And you're explicitly doing these things. Then so like in my construction every agent lab does some version of this where like here's the **image understanding endpoint** and we will route for you and don't worry about it.

</details>

**Swix**: 谢谢，我觉得这很酷。

<details>
<summary>Original English</summary>

**Swix**: Thanks I think it's kind of cool.

</details>

**David Singleton**: 我觉得这完全合理。嗯，再说一遍，为了让那些不每天关注 **AI** 新闻的人也能使用，这确实是一件非常重要的事情。嗯，这真是一种乐趣。我的意思是，我个人对这些东西完全痴迷。我热爱它。能够深入研究所有这些细节，以便让它为其他人良好地工作，这真是一种享受。我现在无法想象从事其他任何工作，这太有趣了。

<details>
<summary>Original English</summary>

**David Singleton**: I I think it makes total sense. Um and again to make this work for folks that don't follow the **AI news** every day. It's an actually it's a it's a really important thing to do. Um and it it's been it's been a real pleasure. I mean I'm I'm personally a total geek for this stuff. I love it. And being able to go and dive into all those details in order to make it work well for other people, it's a true pleasure. I cannot imagine working on anything else right now is just so much fun.

</details>

**Swix**: 棘手的部分是多模态，当其中一些东西确实融合在一起时……

<details>
<summary>Original English</summary>

**Swix**: The tricky part is multimodality when some of these things do merge

</details>

**David Singleton**: 而你正在对那些根本不想被结构化的事物施加结构，所以有时这可能会对你不利。但对于 99% 的情况，这没问题。

<details>
<summary>Original English</summary>

**David Singleton**: and you're you're sort of this is you're imposing structure on things that fundamentally don't want to be structured and so sometimes that might work against you. But for 99% of these cases, this is fine.

</details>

**Swix**: 是的。我的意思是，我认为看看这个世界如何成熟会非常有趣，因为 **Dreamer** 的大部分力量在于能够启动这些子代理。所以，这些强大的代理平台可以根据数据实际改变它们的工作方式。我实际上认为我们将能够跟上并保持在工具和系统如何协同工作这一不断变化的领域的前沿。而这是新的。你知道，软件以前不是这样工作的，现在是了。嗯，所以即使只是弄清楚如何设计正确的原语来使其成为可能，本身也很有趣。这是一个可能包含两部分的问题：为什么 **Dreamer** 不能自己创建工具，以及为什么你不让构建者自己建立路由组？我称之为路由组，对吧？就像一个集合，是的，有些东西。在某种程度上，**Dreamer** 确实会创建自己的工具，因为代理在系统中表现为工具，所以它们可以被用来完成任务。所以你可以构建一个本质上是工具的代理，嗯，对我来说，这非常有用，可以重复利用。没错。没错。因为我喜欢这样。现在我的接下来的五个应用，我不想再重复整个来回过程了。

<details>
<summary>Original English</summary>

**Swix**: Yeah. I mean, I think it's going to be very interesting to see how the the the world matures because a lot of the power of **dreamer** is the ability to kick off these sub agents. So, these powerful agentic harnesses which can actually change how they work based on the data. I actually think that we will be able to kind of keep up with and stay at the forefront of the changing landscape of how tools and systems work together. And that's that's new. You know, software didn't used to work like this and now it does. Um, so even even just figuring out how to design the right primitives to make that possible has itself been a lot of fun. This this is a sort of maybe two-part question that why can't streamer make its own tools and then why don't you let you builders maybe stand up their own routing group I call this a routing group right like where it's like a collection yeah things so two things to some extent **dreamer** does make its own tools in that agents appear to the system as tools so they can be they can be used to accomplish things so you can build an agent that is essentially a tool um and it to me very useful reuse.

</details>

**David Singleton**: 没错。

<details>
<summary>Original English</summary>

**David Singleton**: Right.

</details>

**Swix**: 是的。

<details>
<summary>Original English</summary>

**Swix**: Yeah.

</details>

**David Singleton**: 嗯，然后，在系统的工具层，它是对任何人开放的。所以它实际上非常强大和灵活。所以如果你想添加一个工具，比如你正在训练你自己的基础模型 **Swixs**，那可能会很有趣。想象一下你想让人们玩，我不知道，也许你制作了像 **nano chat** 或其他什么东西，你想让人们玩你自己的 **nano chat**，看看感觉如何。

<details>
<summary>Original English</summary>

**David Singleton**: Um then at the tool layer of the system, it's open to anyone. So it's actually quite powerful and flexible. So if you wanted to add a tool which was uh imagine that you were training your own foundation model **Swixs**, that might be fun. And imagine you wanted people to be able to play with I don't know, maybe you make like, you know, **nano chat** or whatever and you want to let people play with your own **nano chat** and see how

</details>

**Swix**: 它感觉如何。现在，

<details>
<summary>Original English</summary>

**Swix**: it feels. Now,

</details>

**David Singleton**: 你可以发布一个就是 **nanohat** 的工具，它在你工具背后进行 **nano 图像生成**，如果你愿意，它也可以是你自己的路由器。

<details>
<summary>Original English</summary>

**David Singleton**: you could you could publish a tool that is **nanohat** and it **nano image generation** behind your tool and it could be your own router if you wanted to.

</details>

**Swix**: 我明白了。

<details>
<summary>Original English</summary>

**Swix**: I see.

</details>

**David Singleton**: 说实话，如果这种事情让你作为构建者感到兴奋，请来做吧。我们真的相信这个理念，那就是我们不会自己弄清楚每一个细节。我们会确保这是一个安全有趣的地方来构建这些东西，但我们真的对来自其他人的这些想法持开放态度。嗯，所以没有什么比你进来构建一个能做你心中那些很酷事情的工具更让我高兴的了。

<details>
<summary>Original English</summary>

**David Singleton**: And honestly, if that's the kind of thing that gets you excited as a builder, please come and do it. Like we we really are believers in this idea that we aren't going to figure out every single detail ourselves. We're going to make sure it's a safe and fun place to build this stuff, but we're really open to these ideas coming from other people. Um, and so I'd like nothing more than you come in and build a tool that does some of that cool stuff that you that you have in mind.

</details>

**Swix**: 是的。太棒了。

<details>
<summary>Original English</summary>

**Swix**: Yeah. Awesome.

</details>

### Dreamer CLI 与 Type-Safety 的优势

**David Singleton**: 提醒一下，如果你想这样做，找到链接的方式是 **dreamer.com/latenspace**。嗯，在此页面上，限时开放，所有收听此播客的人都将直接脱离我们的等待名单。嗯，现在等待名单很长。我们正在努力引入 **SQL**，所以请跳过等待名单。

<details>
<summary>Original English</summary>

**David Singleton**: And just as a reminder, if you'd like to do that, the way to find the links is **dreamer.com/latensspace**. Um, and for a limited time on that page, um, anyone who's listening to this podcast will also get directly off of our wait list. Uh, it's quite long right now. We are working hard to bring **SQL** in so skip the wait list.

</details>

**Swix**: 是的。你知道我认为这太棒了。我认为这确实是一种面向构建者的方式。我想回到那个酒吧。是的。你知道我对此很兴奋。

<details>
<summary>Original English</summary>

**Swix**: Yeah. Know I think I think that's fantastic. I I think it's it's really sort of probuilder way to do it. I wanted to jump back to the the bar. Yeah. You know you know I get excited about this.

</details>

**David Singleton**: 是的。好的。我们回到那里。

<details>
<summary>Original English</summary>

**David Singleton**: Yes. Okay. Let's jump back in there.

</details>

**Swix**: 就像，你知道，这是工程师播客。让我们尽可能技术化。

<details>
<summary>Original English</summary>

**Swix**: Like let's you know this is the engineer podcast. Let's get as technical as you can.

</details>

**David Singleton**: 是的。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah.

</details>

**Swix**: 关于你构建的一切，就像展示一下。

<details>
<summary>Original English</summary>

**Swix**: On everything you've built like have a show off.

</details>

**David Singleton**: 是的。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah.

</details>

**Swix**: 好的。那么我们就在 **AI Studio** 里尽情发挥吧。所以，你可以看到左边这里是与 **Sidekick** 的对话，你告诉它做什么，它会用任何人都能理解的英语解释正在发生的事情。但是，嗯，如果你想揭开盖子，看看内部，嗯，如果你像我一样是工程师，那么我们有这个，嗯，这个底部的调试抽屉。所以你可以在这里看到完整的构建日志，但你也可以深入查看已生成的文件和提示。嗯，你可以在静态文件中上传你电脑里的文件。嗯，非常重要。

<details>
<summary>Original English</summary>

**Swix**: Okay. So let's go wild in the aisles in the **Asian studio**. So, as you can see over on the left here is a conversation with the **sidekick** where you ask it what to do and it will explain in English that anyone can understand what's going on. But, um, if you want to pull back the covers and look under the hood, um, if you're an engineer like me, then we have this, uh, this kind of debug drawer at the bottom. So, you can see the full build logs here, but you can actually also dig in and see the files and prompts that have been generated. Uh, you can upload files from your computer in static files. Um, very important.

</details>

**David Singleton**: 嗯，确实，你可以实际阅读为你生成的提示。我们特意在这里放了一个例子，只是为了让你能看到格式是怎样的。然后，你知道，我们已经看过了为这个特定的应用生成的那个。但是如果你真的想把代码从 **Dreamer** 中提取出来，在自己的本地机器上工作，你可以这样做。所以，这里所有一切的核心是一个带有强大命令行界面的 **SDK**。我们首先构建了它。实际上，你可以在 **Dreamer** 上构建代理，而无需与 **Sidekick** 对话。如果你想，你可以用手指在键盘上写代码。我知道这现在听起来很过时，但实际上这会很有趣。所以，如果你想把它拉到你的笔记本电脑上，你可以使用我们的 **CLI**，你可以在 **Cursor** 或 **Cloud Code** 中编辑它。你知道，你不需要使用我们的 **Sidekick**。而且 **CLI** 实际上可以完全访问平台的其余部分，你作为用户可以进行操作。所以，你知道，显然它是安全且注重隐私的。这是我们一些最技术性的构建者在平台上构建东西的方式。真正酷的是，**Sidekick** 在编码模式下，它使用的正是相同的 **CLI**。所以它在 **Dreamer** 上构建东西的方式，使用的是你作为工程师可能会使用的相同工具。嗯，这实际上是一个非常强大的抽象，因为它表明，向代理提供大量上下文以使用 **CLI** 的正确方法是编写出色的文档。确保所有你能做的事情都是实际可能的。你猜怎么着？这也会为真实人类带来愉快的开发者体验。

<details>
<summary>Original English</summary>

**David Singleton**: Uh, indeed, you can actually read the prompts that have been generated for you. We intentionally put an example in here just so that you can see what the format looks like. And then, you know, we already looked at this one that was generated for this particular um, app. But if you actually want to bring the code out of **Dreamer** and work on your own local machine, you can. So, at the core of everything here is an **SDK** with a powerful command line interface. And we built that first. It's actually possible to build agents on **Dreamer** without talking to the **sidekick**. You can write code with your fingers on a keyboard if you want to. I know that sounds very antiquated now, but actually this can be a lot of fun. So, if you want to pull it out onto your laptop, you can use our our **CLI** and uh you can edit it in **Cursor** or in **cloud code**. You know, you don't have to use our **sidekick**. And the **CLI** actually has full access to the rest of the platform with you as the user. So, you know, obviously it is uh secure and privacy sensitive. And this is a way that um some of our most technical builders do build stuff on the platform. The really cool thing is the **sidekick** when it's in coding mode, it uses exactly the same **CLI**. So the way it builds stuff on **dreamer** is using the same tools that you might as an engineer. Um and that's actually a very powerful abstraction because it turns out that the right way to give a lot of context to agents to use **CLIs** is to write great documentation. make sure that all of the things that you could do are actually possible. And guess what? That makes it a delightful developer experience for real humans as well.

</details>

**Swix**: 是的。

<details>
<summary>Original English</summary>

**Swix**: Yeah.

</details>

**David Singleton**: 所以，这很酷。

<details>
<summary>Original English</summary>

**David Singleton**: So, that's pretty cool.

</details>

**Swix**: 我们一直在告诉开发者这样做，但他们一直不听，直到现在他们不得不这样做。

<details>
<summary>Original English</summary>

**Swix**: We've been telling developers to do this and they ignored us until now they have to.

</details>

**David Singleton**: 我说这很久了。

<details>
<summary>Original English</summary>

**David Singleton**: I I've been saying this for a long time. Um,

</details>

**Swix**: 嗯，实际上，**Stripe** 的文档。我的意思是，拜托。

<details>
<summary>Original English</summary>

**Swix**: well, actually, **Stripe** docs. I mean, come on.

</details>

**David Singleton**: 绝对是。

<details>
<summary>Original English</summary>

**David Singleton**: Absolutely.

</details>

**Swix**: 拜托。

<details>
<summary>Original English</summary>

**Swix**: Come on.

</details>

**David Singleton**: 绝对是。但实际上，我上周在和 **Stripe** 的人聊天，我说：“嘿，你们必须让 **Stripe CLI** 真正告诉代理它们可以在 Stripe 上做什么，因为这样它们才会更多地使用 Stripe 上的东西。”我认为这对于整个行业来说是一个真正的趋势。

<details>
<summary>Original English</summary>

**David Singleton**: Absolutely. But actually, I was chatting with folks at **Stripe** last week and saying, "Hey, you got to make the **Stripe CLI** actually tell agents what they can do on **Stripe** because that way they're going to use more stuff on Stripe." I think this is a real trend for the entire industry.

</details>

**Swix**: 所以我们一直在这样做。

<details>
<summary>Original English</summary>

**Swix**: So we we've been doing that.

</details>

**David Singleton**: 对我来说，这种下载和 **git push** 等一切都完全是出于信任，因为你没有在修改它，对吗？因为还有其他一些，我们称之为 **AI** 构建平台，它们将它们的堆栈强加给你，如果你……所以因此它们不允许你这样做，因为它们不能，因为它们施加了一些自由度的限制，这样它们才能让它工作。你的则是一个完全通用的，像 **VM** 一样运行完整代码。没错。你想做什么就做什么。任何你想要的语言。

<details>
<summary>Original English</summary>

**David Singleton**: To me, this this download and **git push** and everything is complete confidence in that you're not hacking it, right? Because there's other let's call them **AI builder platforms** that impose their stack on you and if you if you and so therefore they don't allow you to do this because they cannot because they they impose some degrees of freedom restrictions so that they can get it to work. Yours is a fully general like **VM** running the full code. Correct. Do whatever you want. Any language you want.

</details>

**Swix**: 没错。是的。没错。

<details>
<summary>Original English</summary>

**Swix**: Correct. Yeah. Correct.

</details>

**David Singleton**: 嗯，就语言而言，如果你使用 **SDK**，你可以在其他语言中构建东西。我们发现 **TypeScript** 是构建这些体验的最佳语言。

<details>
<summary>Original English</summary>

**David Singleton**: Well, in terms of language, if you use the **SDK**, you could build stuff in other languages. We've actually found that **TypeScript** is the best language for building these experiences.

</details>

**Swix**: 是的。

<details>
<summary>Original English</summary>

**Swix**: Yes.

</details>

**David Singleton**: 因为它是强类型的。所以你可以在编译时发现错误。没有什么比让一个编码代理进入一个循环，让它能看到自己的错误并修复它们更好的了。所以 **TypeScript** 是这里所有一切默认构建的语言。你有没有看到 **TypeScript** 转向 **Python** 在 **GitHub** 上？

<details>
<summary>Original English</summary>

**David Singleton**: Because it's strongly typed. So, you find out at compile time if you've made mistakes. And there's nothing better than getting an a coding agent in a loop where it can see its mistakes and fix them. So, **TypeScript** is the language that everything gets built in by default here. Did you did you see that **TypeScript** over to **Python** in the **GitHub**?

</details>

**Swix**: 我看到了。就我的经验而言，当我们创办公司时，我们开始用 **Python** 编写东西，我喜欢 **Python**。嗯，如果我参加 **Advent of Code**，我总是用 Python 写。作为一名开发者，用我的双手敲键盘时，它是我的最爱。嗯，但是 **TypeScript** 对于 **AI** 来说是一种很棒的语言，因为模型中有大量的训练数据。嗯，它是强类型的。实际上在公司里，我们用 **TypeScript** 构建了大部分技术栈。我们拥有这个惊人的特性，那就是我们从数据库到前端都具有类型安全。对于与编码代理协作来说，没有什么比能够让它们在编译时检查正确性更好的了。所以构建公司代码库背后的相同理念，我们也应用到了这里的代理 **SDK** 中。

<details>
<summary>Original English</summary>

**Swix**: I did. And for what it's worth, when we started the company, we started writing stuff in **Python** and I love **Python**. Um, if I do **advent of code**, I always write it in Python. It's my favorite language as a developer with my fingers in the keyboard. Um, but **TypeScript** is an amazing language for **AI** because there's tons of training data in the models. Um, and it's strongly typed. And actually at the company, we built most of the stack in **Typescript**. And we have this amazing property which is we have type safety all the way from the database to the front end. And there's nothing better for working with coding agents than being able to have them check their correctness at compile time. So the same ideas behind building the company's codebase we've put into the agent **SDK** here as well.

</details>

**David Singleton**: 是的。你知道你是否会使用 **Prisma** 或其他工具，还是对你来说太低级了？

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. Do you know if you'd use one of those tools like **Prisma** or whatever or is it to level for you?

</details>

**Swix**: 我们实际上大部分工具都是自己制作的。嗯，例如，在 **Anthropic** 本周发布的东西之前，我们就有 **LLM** 驱动的代码审查。你知道，我们一直在自己做这些事情。

<details>
<summary>Original English</summary>

**Swix**: We we actually have crafted most of our own tools. Um, for instance, we had **LLM driven code review** before the thing that got published from **Anthropic** this week. You know, we we've been doing this stuff on our own back.

</details>

**David Singleton**: 你知道，我们都为每次审查支付 25 美元。

<details>
<summary>Original English</summary>

**David Singleton**: You know, we all pay $25 per review.

</details>

**Swix**: 我们支付的少得多。不过，我听说那些审查很棒，可能值 25 美元。

<details>
<summary>Original English</summary>

**Swix**: We we pay a lot less than that. However, I hear that those reviews are excellent and possibly worth $25.

</details>

**David Singleton**: 你知道，这是一个选择，对吧？这很好。有它很好。

<details>
<summary>Original English</summary>

**David Singleton**: You know, it's an option, right? It's good. It's good good to have it.

</details>

### Dreamer 的版本控制、工作流、数据库与函数暴露

**Swix**: 只是带你看看这里的一些其他东西。所以，嗯，我也可以看到所有版本。嗯……

<details>
<summary>Original English</summary>

**Swix**: Just to give you a tour of some other stuff here. So, um I can also see all the versions. Um

</details>

**David Singleton**: 这不是 **Git**。

<details>
<summary>Original English</summary>

**David Singleton**: This is not **Git**.

</details>

**Swix**: 这不是 **Git**。这是内置在 **Dreamer** 中的。我可以看到所有以前推送的版本。为什么不是 Git？不是 Git 是因为我们可以让它比 Git 更高效地工作，我们实际上在幕后做了一些工作，以理解每个版本中包含什么。嗯，所以我正在追求的一个想法，我有很多论文，就是 Git 会消失吗？GitHub 会消失吗？原生的版本控制会是什么？

<details>
<summary>Original English</summary>

**Swix**: This is not **Git**. This is built into **Dreamer**. I can see all the versions that have been pushed before. Why is it not Git? It's not **git** because we can make it work more efficiently than git and we actually we do some work behind the scenes to kind of understand what's in each of these versions. Um so one of the things I'm pursuing and I have a lot of thesis right one of the thesis is like does **git** go away? Does **GitHub** go away and like what what is the native revision?

</details>

**David Singleton**: 就其价值而言，你在任何构建的东西中都有很多路径依赖。如果我们可以重新开始，我们可能会把它做成 **Git**。你知道在公司内部，我们为我们的平台源代码使用 **Git**，我们喜欢它，它与编码代理也配合得很好。这个项目的最初版本，我们希望能够让 **Sidekick** 轻松操作它。嗯，这是一种便捷的方式。

<details>
<summary>Original English</summary>

**David Singleton**: For for what it's worth to some extent in anything you build there's a lot of path dependency. If we started over we might make this **git**. There's you know within the company we use **git** for our you know platform source code and we like it and it works well with coding agents as well. The very first versions of this we wanted to be able to make it possible for the **sidekick** to manipulate it easily. Um and this this was an expedient way to do it.

</details>

**Swix**: 是的。嗯，你也可以看到你构建的工作流中发生的所有活动。你在 **Dreamer** 上构建的许多代理都在后台做事情。所以它们根据触发器运行。这些是来自外部的刺激来启动它们。这是一种很好的方式来查看所有可能启动你的代理的事情。你知道，你可以让一个代理通过 **webhook** 启动。所以你可以把它连接到外部系统。你可以让一个代理在你收到符合过滤器（包括 **LLM** 过滤器）的特定电子邮件时运行。所以，在这里你可以看到，哦，它什么时候运行的？它做了什么？你知道，如果我打开这些引导我提示或引导我事件中的一个。好吧，我告诉你它为每个时间段都调用了一个 **LLM**。这里是所有 LLM 调用。这里是实际的提示。

<details>
<summary>Original English</summary>

**Swix**: Yeah. Um, you can also see all the activity that has happened in the workflows that you build. A lot of agents you'll build on **Dreamer** do things in the background. So, they run on triggers. These are stimuli from the outside to kick them off. And this is a nice way to see all of the things that might have kicked off your agent. You know, you can have an agent that kicks off on a **web hook**. So, you can plug it into external systems. You can have an agent that runs when you receive certain emails that match filters, including **LLM filters**. And so, here you can see, oh, when did it run? What did it do? You know, if I open up one of these guide me prompts or guide me events. Well, I told you it was calling an **LLM** for every one of those time slots. Here's all of the LLM calls. Here's the actual prompts.

</details>

**David Singleton**: 而且你不介意暴露所有这些，对吗？

<details>
<summary>Original English</summary>

**David Singleton**: And you don't mind exposing all of this, right?

</details>

**Swix**: 不，我们希望构建者能看到内部发生了什么。好的。是的。

<details>
<summary>Original English</summary>

**Swix**: No, we want builders to see what's going on under the hood. Okay. Yeah.

</details>

**David Singleton**: 所以，好的。现在，那个是 **Haiku**。就像我说的，我们使用所有模型，**Sidekick** 会选择最适合这份工作的那个。你看到它质量很高，速度也很快。所以，**Haiku 45** 是它为那份工作选择的模型。嗯，我们也有日志，正如我提到的，每个代理都会按需启动一个数据库。你不用去弄清楚如何自己托管。这是一个 **SQLite**。

<details>
<summary>Original English</summary>

**David Singleton**: So, okay. Right now, that one was **Haiku**. Like I said, we work with all the models and **Sidekick** will actually pick the best one for the job. And you saw that was pretty high quality and pretty fast. So, **Haiku 45** is the one that it picked for that job. Uh we also have logs as I mentioned there's a database spun up on demand for every agent. You don't have to go and figure out how to do your own hosting. This is a **SQLite**.

</details>

**Swix**: 这是一个 **SQLite** 数据库。嗯，它是一个多用户 **SQLite** 数据库。然后，嗯，但是每个你都会得到一个这个代理独有的数据库。但是如果你与多人共享代理，我们会处理好谁是每行的所有者，所有这些东西都开箱即用。嗯……

<details>
<summary>Original English</summary>

**Swix**: This is a **SQLite** database. Um it's a multi-user **SQLite** database. And then uh but but each one is you get a database that is unique to this agent. But then if you share the agent with multiple people, we take care of like who are the owners in each row and all of that stuff is just there out of the box. Um,

</details>

**David Singleton**: 再次是内部的。

<details>
<summary>Original English</summary>

**David Singleton**: and again in-house.

</details>

**Swix**: 我的天啊。

<details>
<summary>Original English</summary>

**Swix**: Oh my god.

</details>

**David Singleton**: 是的。嗯，我们确实与许多基础设施提供商合作，但操作这项技术的技术是内部的。有趣的是，我们实际上在公司早期做了很多自己的基础设施开发，后来意识到我们需要将精力投入到我们独一无二的事情上。所以我们非常高兴能与许多优秀的设计师合作来做这些。最后，嗯，我提到了智能应用和代理会将其所有内部结构暴露给系统。所以 **Sidekick** 可以像用户一样操作和使用它们。所以你可以看到它如何决定将这个问题分解成函数。其中一些函数，带小 **I** 的那些，是导出的。这意味着它们可以从外部公开访问。没错。而其他的是内部的。如果你愿意，你可以直接在这里深入并调用单个函数，看看会发生什么。但大多数情况下，你完全不需要考虑这些。嗯，你可以把那个小抽屉关上，你可以和你的 **Sidekick** 对话，构建真正强大而迷人的体验。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. Um, well, we do work with a bunch of infrastructure providers, but the technology for how to manipulate this is in-house. Fun fact, we actually did a lot of our own infrastructure development early on at the company and realized we need to spend our energy in the stuff that we're uniquely doing in the world. So, we're very delighted to partner with a bunch of great designers on some of this stuff. And then finally, um, I mentioned that **aentic apps agents** expose all of their internals to the system. So the **sidekick** can manipulate them and use them just like a user can. So you can see how it's decided to break this problem up into functions. Some of the functions, the ones with the little **I** here are exported. That means that there's publicly from outside. Exactly. And others are internal. And if you want to, you can dig right in here and call individual functions and see what happens. But mostly you don't need to think about that at all. Uh you can keep that little drawer closed and you can talk to your **sidekick** and build really powerful and enchanting experiences.

</details>

### 多用户应用与编码代理的互操作性

**Swix**: 是的。我的意思是，对我来说，展示这些可以让工程师对你所做的事情以及你可以用它做什么有一个完整的心理模型。

<details>
<summary>Original English</summary>

**Swix**: Yeah. I mean to me like showing this gives the engineer a complete mental model of what you've done and what you can do with it.

</details>

**David Singleton**: 例如，我首先会寻找一个心理检查清单上的东西，比如数据库是否关闭，看起来没有对吧？所以这是一个单独的层，这可能意味着在同一个应用上做多用户应用很难，对吧？

<details>
<summary>Original English</summary>

**David Singleton**: For example, the first thing I look for a mental checklist of things right like is off in the database off looks like it's not right. So that's a separate layer that's probably means it's hard to do multi-user apps on the same app, right?

</details>

**Swix**: 所以你实际上我们已经解决了这个问题。所以，嗯，是的，平台内置了 **O**，所以你作为用户登录平台。如果你使用的是其他人发布的代理，那么你的身份将由系统处理，当你查询数据库时，你会得到属于你的数据，除非构建者明确表示这是公共数据，每个人都应该看到。所以他们实际上有机会思考这个问题，**Sidekick** 也可以引导你构建以这种方式工作的代理和应用。所以，你说得对。这是人们在尝试弄清楚如何构建软件体验时必须考虑的另一件事。在 **Dreamer** 上，它是内置的。你像和人类一样与 **Sidekick** 对话，告诉它你想要什么，然后你就能得到什么。所以，你知道，我的 **Big Sky** 应用，我刚才展示给你的那个，就是为多人使用的。当然，我们输入的开销应该对所有人可见。我只是告诉 **Sidekick** 我想要那样。但默认情况下，如果我构建一个这样的应用，每个用户的数据是不会对其他人可见的。

<details>
<summary>Original English</summary>

**Swix**: So you actually we've solved that. So um yes the platform builds in **O** so you as a user sign into the platform. If you're using an agent that was published by someone else then your identity is is kind of taken care of by the system and when you query the database you're going to get the stuff that is for you unless the builder specifically said this is public data that everyone should see. So they they actually get a chance to think about that and again **Sidekick** can guide you through building agents and apps that work that way. So, you're right. That's another thing that people have to think about when they're trying to figure out how to build software experiences. On **Dreamer**, you it's built in. You talk to the **sidekick** as if it were a human being about what you want, and that's what you get. So, you know, my **Big Sky** app that I just showed you, that was designed for multiple people to use it. And of course, the things that we were putting in as expenses were supposed to be visible to everybody. And I just told the **sidekick** that's the way I wanted it. But by default if I built an app like that the data from each user would not have been visible to the others.

</details>

**David Singleton**: 是的。是的。嗯，我猜这是一个情绪问题，但基本上你不得不构建自己的编码代理，对吧？也就是 **Psychic** / **Sidekick** 内部的任何东西。显然，很多人非常渴望 **Cloud Code** 和 **CodeEx**，并对其有依赖。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. Yeah. Uh this is I presume this is a mood question but basically you've had to build your own coding agent right which is **psychic**/ whatever is in inside **psychic**. Obviously there's a lot of people with a lot of desire for **cloud code** and **codeex** and attachment to it.

</details>

**Swix**: 我知道从底层来看，它们基本上都归结为一个循环，但你会让人们使用 **Cloud Coding CodeEx** 吗？或者框架是否太专业化了？是的。如果你想使用 **Cloud Code** 和 **CodeEx**，那你就去这里，获取 **SDK**，我们甚至在这里就说了，尽情编辑吧。Z 光标云代码。

<details>
<summary>Original English</summary>

**Swix**: I know under the hood they basically reduce to a loop but like would you let people use **cloud coding codeex** or is the harness too specialized? Yeah. If you if you want to use um **cloud code** and **codeex** then you go down here get the **SDK** and we even say this right here edit to your heart's content. Z cursor cloud code

</details>

**David Singleton**: 但人们想在 **Psychic** 内部使用它，对吧？他们想切换编码引擎。

<details>
<summary>Original English</summary>

**David Singleton**: but like people want to use it inside of **psychic** right they want to switch the engine that's the coding engine.

</details>

**Swix**: 是的，我们现在没有这样做。嗯，你知道，目标确实是抽象复杂性，因为构建智能应用的真正目标是那些今天还无法做到这一点的人。我无法告诉你我们社区中有多少用户跟我说：“**Dreamer** 改变了我的生活，因为我以前有很多想法。如果我能找到一个工程师来帮助我实现它们，我就能完成它们。现在我可以和我的 **Sidekick** 对话，并把它构建出来。”我认为这才是我们思考那些应该从平台中获得巨大价值和乐趣的人的方式。所以他们并没有要求能够插入他们自己的编码代理。对于这些人来说，机会是巨大的。如果你以前从未能够用代码做事情，现在你可以为自己、为你的朋友、为你的家人、为你的同事构建东西。而且，对于那些确实用代码构建东西的人来说，也有巨大的机会来为这个生态系统做贡献。所以这就是我们的思考方式。

<details>
<summary>Original English</summary>

**Swix**: Yeah we are not doing that right now. Um you know again the goal really is abstract the complexity um because the real target for building **agentic apps** is folks who can't do this already today. I can't tell you how many users in our community I've spoken to who are like, "**Dreamer** has changed my life because I used to have all these ideas. If only I could find an engineer to help me implement them, I'd be able to get them done. And now I can talk to my **sidekick** and and get it built." I think that's like really how we think about the people that should get a ton of value and fun um out of the platform. And so they're not asking to be able to plug in their their own, you know, coding agent. And for those folks, the opportunity is massive. If you've never been able to do stuff in code, now you can build stuff for you, for your friends, for your family, for your co-workers. And also, there's a huge opportunity for folks who do build stuff in code to actually contribute to this ecosystem. So that's how we think about it.

</details>

### 记忆、个性化与 Dreamer 的未来发展

**David Singleton**: 是的。太棒了。这就是我大部分想涵盖的关于 **Dreamer** 的内容。我认为个性化和记忆可能是操作系统最重要的工作。也许我们可以谈谈这个，然后我想谈谈公司的构建。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. Amazing. That's most of what I wanted to cover **dreamer** wise. I think personalization and memory is probably like the single most important job of of the **OS**. Maybe we could talk about that and then I wanted to zoom out on the company building stuff.

</details>

**Swix**: 是的。是的。听起来不错。

<details>
<summary>Original English</summary>

**Swix**: Yeah. Yeah. Sounds good.

</details>

**David Singleton**: 是的。那么，你们如何处理记忆？你们发现了什么？尝试了什么，又失败了什么？

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. So, how do you handle memory? What what have you found? What have you tried and failed?

</details>

**Swix**: 是的。好的。所以，嗯，首先，**Dreamer** 的核心是 **Sidekick**。**Sidekick** 会了解你，并随着时间的推移建立起关于你的记忆，这被证明非常重要。所以，**Dreamer**……

<details>
<summary>Original English</summary>

**Swix**: Yeah. Okay. So, uh first of all, at the core of **dreamer** is the **sidekick**. The **sidekick** gets to know you and it builds up a memory about you over time and that turns out to be very important. So, **dreamer**...

</details>

**David Singleton**: **Dreamer** 用得越多越好。例如，平台上的许多代理在你开始使用时，首先会向你展示：“这是我认为与你相关的，针对这个特定用例。”**Dreamer** 上非常流行的一种代理是周末活动规划器。所以，嗯……

<details>
<summary>Original English</summary>

**David Singleton**: **Dreamer** gets better the more you use it. For instance, a lot of agents in the platform when you start using them, the first thing they do is show you, "here's what I think is relevant to you for this particular use case," uh, a very popular kind of agent on **Dreamer** is a weekend activity planner. So, um,

</details>

**Swix**: 就告诉我该做什么。

<details>
<summary>Original English</summary>

**Swix**: just tell me what to do.

</details>

**David Singleton**: 嗯，告诉我该做什么。特别是如果我有孩子，对吧？所以，我有两个孩子，一条狗，我和我妻子经常花很多时间来弄清楚这个周末我们一家人要做什么，你知道，我们的兴趣非常一致。实际上，弄清楚这些可能需要一周的时间。所以，**Dreamer** 上有一个名为**周末活动规划器**的代理，它帮助我找到周末和家人一起做的事情。事实上，今天早上我收到了我的周末活动规划器的消息，告诉我周六在市中心有圣帕特里克节游行。我是爱尔兰人。我的孩子从技术上讲也是爱尔兰人。我的意思是，他们有多重国籍，但你知道，他们是爱尔兰人。嗯，有什么比带他们去圣帕特里克节游行更好的呢？为什么会推荐给我这个？因为在周末活动规划器了解我的档案中，它知道我是爱尔兰人，对吧？所以所有这些都来自 **Sidekick** 随着时间推移建立的关于我的记忆。我们为此投入了大量资金。我们将继续投入更多。我们实际上尝试了许多不同的技术。如你所知，嗯，智能记忆的前沿一直在变化。你知道，很早以前我们把大量事实放入向量数据库，然后进行嵌入，然后通过，你知道，嵌入的反向查找，即 **RAG**，将其提取出来，那确实有效，但结果发现比实际所需的复杂得多。所以，你知道，今天我们已经用一个不同的系统取代了它。嗯，我认为我们使用的系统与你在许多其他产品中会发现的非常相似，但这是一个我们正在积极投入的领域。公司里有不止一个人专门从事记忆研究。所以，期待我们继续改进它。

<details>
<summary>Original English</summary>

**David Singleton**: Well, tell me what to do. Especially if I've got kids, right? So, I have two kids and a dog and my wife and I often spend a lot of time trying to figure out what are we going to do with the crew this weekend and, you know, we have interests that are very consistent. It actually can take a ton of work during the week to figure this out. So, there is an agent on **Dreamer** called **Weekend Activity Planner** and it helps me find things to do with with the family at the weekend. In fact, this morning I got a message from my weekend activity planner telling me about the **St. Patrick's Day parade** on Saturday at **Civic Center**. I'm Irish. My kids are technically Irish as well. I mean, they they have multiple citizenships, but you know, they're they're Irish. Um, what a better thing to do than take them to the **St. Patrick's Day parade**. Why did that get recommended to me? Because in the profile that weekend activity planner knows about me, it knows that I'm Irish, right? So all of that comes from the memory that **sidekick** builds up about me over time. We have invested in this a bunch. We will continue to invest in this more. We've tried actually many different techniques. As you know, the the kind of um cutting edge of **aentic memory** has changed over time. you know, very early on we were putting lots of facts into a **vector database** and uh and doing **embeddings** and pulling them back out um using, you know, **reverse lookup of embeddings rag** that actually worked but turned out to be much more complexity than was actually required. So, you know, today we've replaced it with a different system. I think we use a system that's pretty similar to what you'll find in lots of other products, but it's an area that we're actively investing in. Like there's there's more than one person at the company specifically working on memory. And so expect us to just continue to make it better.

</details>

**Swix**: 你尝试过知识图谱吗？

<details>
<summary>Original English</summary>

**Swix**: Did you try knowledge graphs?

</details>

**David Singleton**: 我们尝试过知识图谱。我们现在的系统不是知识图谱。嗯，但我们可能已经实现了你见过的大多数关于智能记忆的论文，而且当前的系统运行得很好。

<details>
<summary>Original English</summary>

**David Singleton**: We've tried **knowledge graphs**. The system that we have now is not a **knowledge graph**. Um but we've probably implemented most of the papers you've seen out there on **agentic memory** and the current system is working pretty well.

</details>

### CEO 角色转换、小团队运作与 AI 时代的招聘

**Swix**: 是的。太棒了。就公司方面而言。嗯，这是你第一次担任 **CEO** 吗？

<details>
<summary>Original English</summary>

**Swix**: Yeah. Excellent. Zooming out just on the company stuff. Um uh this is your first time in the **CEO** seat,

</details>

**David Singleton**: 没错？

<details>
<summary>Original English</summary>

**David Singleton**: correct?

</details>

**Swix**: 你之前是 **CTO**，对吗？有什么不同？

<details>
<summary>Original English</summary>

**Swix**: You were **CTO** before, correct? What's different?

</details>

**David Singleton**: 是的，**CEO** 和 **CTO** 之间的区别在于，CEO 真的只是确保你关注所有方面。所以，嗯，我以前也管理过产品。例如，**Android Wear**。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah, the difference between being a **CEO** and a **CTO** really is just like making sure you're looking across everything. So, um I have run products before. So, for instance, **Android Wear**,

</details>

**Swix**: 你基本上是那个产品的 **CEO**。

<details>
<summary>Original English</summary>

**Swix**: you're basically a **CEO** of that product.

</details>

**David Singleton**: 我当时是作为一名总经理管理它的。

<details>
<summary>Original English</summary>

**David Singleton**: I I was running that as a **general manager**.

</details>

**Swix**: 是的。

<details>
<summary>Original English</summary>

**Swix**: Yeah.

</details>

**David Singleton**: 然而，当你为自己的公司做这件事，而且责任完全落在你肩上时，它确实会有点升温。嗯，但对我来说，思考很多市场推广方面的问题一直很有趣。嗯，我现在大部分时间都在与用户见面，嗯，与人们讨论他们可以在平台上做什么，在 **X** 和 **LinkedIn** 上非常活跃。嗯，顺便说一下，这是一种巨大的乐趣。能够直接与用户和潜在用户互动，并了解他们想做什么，这非常有趣。嗯，这就是这个角色与担任一家公司 **CTO** 的最大区别。同时，我是一个总是喜欢寻找“我们为什么要这样做？谁会从中受益？”的人。所以，你知道，即使作为 **CTO**，我也会一直非常关注公司各个方面的话题。所以，我对以前的角色中学到的一切感到非常感激，这些都让我准备好以这种规模来做这件事。

<details>
<summary>Original English</summary>

**David Singleton**: However, when you do it for your own company and the buck truly stops with you, it definitely kind of raises the temperature a little bit. Um but it's been a lot of fun for me to think about a lot of go to market topics. Um, I spend a lot of my time these days meeting users, uh, talking to folks about what they could do on the platform, being very active on **X** and **LinkedIn**. Uh, which by the way is a huge pleasure. It is so much fun to be able to engage with users and potential users directly and understand what they would like to do. Um, and that's the biggest difference between this role and being the **CTO** um, of a company. At the same time, I am someone who always likes to look for why are we doing this? Who are the people that benefit from it. So, you know, even as a CTO, I was always paying a lot of attention to topics across the company. So, I feel very grateful for all I learned in my previous roles that kind of got me ready to to do this at this kind of scale.

</details>

**Swix**: 是的。对我来说，这就像我走进你办公室时的自然引导。是的。出乎意料的小。

<details>
<summary>Original English</summary>

**Swix**: Yeah. To me, this is like the natural lead to when I went into your office. Yeah. Surprisingly small.

</details>

**David Singleton**: 是的。所以，我正在为 **L Space** 追求另一个论点，那就是小团队的出现，你知道，经典的形象是，团队的收入比员工多几百万，对吧？所以这是收入效率的定义，但我确实认为作为 **CEO**，你将管理一个比你过去更小的团队。

<details>
<summary>Original English</summary>

**David Singleton**: Yes. So and I have another thesis I'm pursuing for **L Space** which is the emergence of tiny teams where uh you know the classic sort of image is that teams with more millions in revenue than employees right so that's revenue efficiency definition but I do think as a **CEO** you are going to run a smaller team than you used to

</details>

**Swix**: 是的，我非常坚信小团队的力量。所以你给一个团队增加的人越多，沟通开销就越大，而且它甚至不会线性增长，如果你想想，你增加的人越多。每个人都关心了解其他人，并与其他人分享他们正在做的事情。这很好。我不是说他们不应该这样做，对吧？我希望在一个有趣的团队中工作，人们可以互相交流，分享想法等等。但是，你知道，更大的团队会带来一种引力。所以，从本质上讲，大型组织不如小型组织灵活。如果你管理一个大型组织，你必须不断思考如何精简，使其能够像一个小团队一样运作。所以在 **Dreamer**，构建我刚才展示的一切的核心团队，说实话，大约有六个人。嗯，我们现在规模更大了。公司现在大约有 17 个人，因为……

<details>
<summary>Original English</summary>

**Swix**: yeah so I believe very strongly in the power of small teams so the more people you add to a team the more communication overhead there is and it doesn't even grow linearly if you think about it the more people you add. Everyone cares about getting to know everybody else and sharing what they're doing with everybody else. And that's great. I'm not saying they shouldn't, right? The very like I want to work in teams that are fun where people are talking to each other and and sharing ideas and so forth. But, you know, there's just a kind of gravitational weight that comes from larger and larger teams. So, just inherently large organizations are less nimble than small ones. And if you run a large organization, you have to keep thinking about how do I kind of like prune things so that it can act like a small team. So at **Dreamer**, the the core team that built everything I just showed you was was honestly about six people. Uh we're larger now. We're about 17 people at the company now because

</details>

**David Singleton**: 就你展示的所有内容而言，这仍然是一个小团队。

<details>
<summary>Original English</summary>

**David Singleton**: it's still for everything you just showed,

</details>

**Swix**: 这仍然是一个小团队，这很棒。这是一个人才密度非常高的团队。我们在发展过程中非常非常小心，甚至痴迷，以确保每个加入公司的人都加入一个他们能够学到很多东西的团队，同时他们也能帮助其他人很多。这也有一点非常特别。你知道，我们公司里的每一个人，我都乐意在任何时候与他们一起做任何项目，因为他们都很棒。你知道，团队规模越小，就越容易确保这种人才密度也存在。当然，创立一家公司是一种真正的奢侈。我们是在 2024 年底创办这家公司的，但今天创立一家公司是一种真正的奢侈，因为我们可以利用代理来构建。所以我们正在使用编码代理。我们正在使用 **Dreamer** 营销代理。我们正在研究如何利用我们自己的工具来实际加速我们的所有运营。嗯，你有没有想特别提到的任何不是你构建的代理？

<details>
<summary>Original English</summary>

**Swix**: it's it's still a small team, which is great. A very very high talent density team. We've been very very careful and kind of obsessed as we grew to make sure that everyone that's joining the company is joining a team that they're going to get a lot of learning out of, but also they're actually going to kind of help everyone else a lot as well. There's something very special about that too. You know, every single person at our company I would be delighted to do any project with at any time because uh they're just all great. And you know the smaller you keep the team the easier it is to make sure that that that talent density is there as well. Of course it's a real luxury to be building a company. We started this company in late 24 but it's a real luxury to be building a company today because we can build with agents. So we're using **coding agents**. We're using **dreamer marketing agents**. All of our operations we're looking at how we can can actually accelerate what we're doing uh using our own tools. Um any actually any agents that you don't build that you want to shout out just that that you love?

</details>

**David Singleton**: 是吗？

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. Is it

</details>

**Swix**: 其他人构建的代理，我们为公司构建的？

<details>
<summary>Original English</summary>

**Swix**: other people's agents that we built for the company?

</details>

**David Singleton**: 不，不。其他人构建的东西，比如你提到的 **Granola**。

<details>
<summary>Original English</summary>

**David Singleton**: No. No. Other people's uh stuff like you shouted out **Granola**.

</details>

**Swix**: 是的。我向你展示了 **Attain Finance**。嗯，**Attain Finance** 也有一个代理，它就像帮助你管理你的钱。我发现这真的很棒。所以，嗯，我总是有这种挥之不去的感觉，觉得我有很多订阅，如果我能花点时间逐一查看，我就可以弄清楚如何整合它们。而构建 **Attain Finance** 的人不是我们公司的员工。他们是早期 **alpha** 小组的一员。所以他们很早就对这些东西的运作方式有所了解。他们构建了这个真正很棒的体验，它实际上帮助你省了很多钱，因为它会帮助你分析你的消费。它几乎就像一个财务健身教练。他叫 **Andrew**，是他构建的。他来向我们展示时，第一件事就是建议他应该少买卷饼。嗯，他说：“是真的。那样我才能省最多的钱。”所以，嗯，这是一个很酷的例子。

<details>
<summary>Original English</summary>

**Swix**: Yeah. So I showed you **Attain Finance**. Uh **Attain Finance** has an agent as well which like helps you manage your money. I find this really amazing. So um I always have this like lingering feeling that I've got a whole bunch of subscriptions that if I just had a bit of time to go across them, I could, you know, figure out how to consolidate them. And the person who built **Attain Finance** doesn't work at our company. They were part of the early **alpha** group. So they got a kind of look at how all this stuff works pretty early on. And they built this really amazing experience that actually helps you like save a lot of money because it will kind of help you analyze your purchases. It's almost like a kind of financial fitness coach. He's called **Andrew** who who built it. He came and showed it to us and the first thing it did was it recommended that he should buy fewer burritos. And he was like it's true. Like that is actually hard. I could save the most money. So, uh that's a that's a pretty cool example.

</details>

**David Singleton**: 嗯，我注意到他是第一个，因为他是按字母顺序排列的。所以，我想知道为什么没有像 **Artvark** 这样的。嗯，是的。嗯，如果你是一个构建者，并且你在想如何在 **Dreamer** 平台上进行 **SEO**，**Swick** 建议你把你的工具命名为 **Artvark**。不过说真的，这些是我已经连接的工具。所以它们是按字母顺序排列的。如果你还没有连接它们，我们实际上会把它们放在正确的顺序。所以 **Sidekick** 理解你，并把它们放在正确的顺序，但我想 **Arvar** 会排在所有其他东西前面，对吧？

<details>
<summary>Original English</summary>

**David Singleton**: Uh I noticed he was first cuz he's in order alphabetical order. So, I'm I'm wondering how come there are no like **Artvark**. Uh yeah. Well, if you're a builder out there and you're wondering how do I **SEO** myself on the **dreamer platform**, **Swick** suggest you name your tool **Artvark**. In all seriousness though, those are the tools I have connected. So, they're in alphabetical order. If you haven't yet connected them, we actually kind of put them in the right order for you. So **sidekick** understands you and puts in the right order, but I'd say **Arvar** is going to come before anything else, right?

</details>

**Swix**: 是的，没错。嗯，然后我想，招聘有什么变化？你一生中招聘过很多软件工程师。我假设有些事情变了。

<details>
<summary>Original English</summary>

**Swix**: Yeah, exactly. Um, and then I I think how's hiring changed? You've hired plenty of software engineers in your life. I assume something's changed.

</details>

**David Singleton**: 是的，绝对是。所以，我现在招聘工程师时主要看的一点是，你与编码代理合作得如何？我们的团队实际上经验很丰富。很多人，**Dreamer** 的每个人，嗯，我想我也写了很多代码。每个人都是 **IC**，一个个人贡献者。团队中的许多人以前都担任过经理。事实证明，担任工程经理，只要你非常接近代码并能够继续自己制作代码，实际上是一种很棒的技能组合，可以让你在这个时代让代理为你和你的团队工作。所以这绝对是我们招聘工程师时非常关注的一点。嗯，我们仍然会让人们用手写一些代码。只是知道核心技能在那里很重要。但我们大部分时间都在与编码代理一起，在一个有趣、协作的环境中，共同构建相当重要和复杂的作品，对吧？

<details>
<summary>Original English</summary>

**David Singleton**: Yeah, absolutely. So, one of the main things that I look for now when hiring engineers is how well do you work with **coding agents**? Our team actually is quite experienced. A good number, everyone at **Dreamer**, other than well, I guess I write a lot of code too. Everyone's an **IC**, an individual contributor. Many of the folks that work on the team have previously been managers. And it turns out being an **engineering manager** as long as you stay very close to the code and are able to continue to craft it yourself is actually a great skill profile for being able to make agents work for you and for your team in this uh in this age. And so that's definitely something that we look for quite intently when hiring engineers. And um we still have folks write some code like with their fingers. It's just important to know that the kind of core of the craft is there. But the vast majority of what we spend time doing is building quite significant and elaborate stuff together in a fun collaborative environment with **coding agents**, right?

</details>

**Swix**: 嗯，

<details>
<summary>Original English</summary>

**Swix**: Um,

</details>

**David Singleton**: 那么面试流程是怎样的？坐在那里用 **CodeEx** 做些什么。是的，我的意思是，我们的面试流程是：首先进行一次编程筛选，以确保基础能力到位，然后我们实际上会与团队中的一名工程师以及考虑加入的候选人一起进行几个短期项目。我们会一起讨论一个非常完善的产品想法。我们会一起集思广益，确保我们测试一点产品意识。然后我们实际上会尝试用 **CodeEx** 或 **Cloud Code** 或候选人最熟悉的任何工具来构建整个东西。嗯，观察一个人如何思考代理的提示，当代理工作时他们会做什么，因为，你知道，实际上这在行业中是一个有趣的动态。这些天我每当编写代码时，总是同时运行多个代理，因为当一个代理运行时，我正在审查下一个代理的输出。如果你能让它们很好地轮流工作，你会非常非常高效。你也可以将代理链式连接起来。你可以让一个代理生成代码，另一个代理审查代码，实际看到人们如何适应他们的工作流程，这是我们面试过程中非常重要的一部分。

<details>
<summary>Original English</summary>

**David Singleton**: So what is the interview loop like? Sit there with **codeex** do something. Yeah, I mean our interview lip is one a coding screen to make sure that the base is there and then we actually do a couple of short projects with an engineer on our team and whoever is thinking about joining where we'll actually put out a very fully formed product idea. We'll riff on it together, make sure that we kind of test product sense a little bit. Then we'll actually try to build the whole thing with **CodeEx** or **Cloud Code** or whatever the person is most familiar with. Um, and watching how someone thinks about prompting the agents, what they do while the agent is working cuz, you know, you can actually, this is a kind of interesting uh, dynamic in the industry. Anytime I'm working on code these days, I always have more than one agent going at the same time because while one agent is going, I'm reviewing the output of the next one. And if you get them in a nice round robin, you can be very, very productive. You can also chain agents together. you could have one agent producing code, another agent reviewing it, and actually just seeing how folks have adapted their workflow um is a big part of what we're we're looking for in our interview process.

</details>

### LLM 的未来与人类创造力

**Swix**: 太棒了。我想最后一个问题，但也欢迎你提出我没有触及的任何话题。你希望 **LLM** 能够做到的，但它们今天仍然做不到的事情是什么？

<details>
<summary>Original English</summary>

**Swix**: Amazing. I guess last question, but also open to you to bring up any topics that I haven't touched on. Have you wanted **LLMs** to do that they still cannot do today?

</details>

**David Singleton**: 这是一个很好的问题。嗯，这很神奇，因为 **LLM** 的能力发展得如此之快。你知道，如果你一年前问我，我可能会说：“嗯，你知道，音乐生成，我喜欢音乐。”嗯，顺便说一句，**Sunno** 很棒。但以前的版本，我可以说，那是 **AI** 生成的。今天，我听 **Sunu** 制作的最新曲目，我心想，这非常令人印象深刻。如果我们回到六个月前，我可能会要求更好的图像生成。最新的 **nano banana**，顺便说一句，是 **Dreamer** 平台上你可以使用的工具，它正在生成壮观的信息图表，当我要求时也能生成壮观的绘画图像。所以这非常令人印象深刻。我仍然认为，我认为随着我们走向未来，人类创造力仍然有很大的空间，所以这也许也是我会说 **LLM** 最缺乏的地方。所以，我认为当你思考构建软件时，真正重要且我们都需要带来的是品味，对吧？你必须真正理解人，他们的动机。我如何构建一个真正令人愉悦的东西？所以，你知道，我们在 **Dreamer** 上做了很多工作，才有可能让我们的体验看起来不像 **AI** 制造的通用敷衍品。对吧？我们做到了。我们通过将我们自己的很多品味融入到模板、提示和框架中来实现这一点。嗯，所以我希望你玩得开心。我认为今天的 **Dreamer** 生成的体验不会让人觉得非常通用，但这需要大量工作，对吧？**LMS** 默认不会这样做。事实上，如果我看到一个，如果你要求一个简单的 To-Do List 应用或其他什么，由模型构建的，我可以通过它的外观来判断是哪个模型构建的。所以，嗯，品味、创造力、个性感仍然是我认为 **LLM** 无法开箱即用的东西，我认为这将是一个有趣的领域。你觉得呢？

<details>
<summary>Original English</summary>

**David Singleton**: That's a great question. Um and it's amazing because the capabilities of **LLM** just advanced so quickly. You know, if you'd asked me a year ago, I would have said, "Well, you know, music generation, I I like music." Um, and **Sunno** is amazing, by the way. And but previous generations, I'd Yeah, I can kind of tell that that's **AI generated**. Today, I listen to the latest tracks made by **Sunu**. I'm like, that's that's pretty impressive. If we went back 6 months, I'd be asking for better image generation. The latest **nano banana** which by the way is a tool on the platform that you can use on **dreamer** is producing spectacular infographics spectacular painterly images when I ask for those as well. So so that's quite impressive. I still think I so I think as we go forward into the future there is still a lot of room for human creativity and so that's also maybe where I'm going to have to say the **LLMs** are most lacking. So I think that when you think about building software, the thing that's really important and that we all need to bring is taste, right? You have to like actually truly understand people, their motivations. How do I build something that's really delightful? So, you know, we had to do a lot of work on **dreamer** to make it possible for the experiences that we build to not look like **AI generic slop**. Right? We go. Um, and we've done that by putting a lot of our own taste into the templates and the prompts and the the harness. Um, so I hope you have fun playing with it. I I think **Dreamer** today generates experiences that don't feel super generic, but that's a ton of work, right? The **LMS** do not do that by default. And in fact, I if I see a if you ask for a simple like to-do list app or something built by the models, I can tell which model built it just by kind of how it looks. So um taste, creativity, sense of individuality is still something that I think the **LLM** are not producing out of the box and I think that's going to be an interesting frontier. What do you think?

</details>

**Swix**: 通常那是，这是我从构建者到研究者的问题，因为我们确实有研究者在听，我只是想说，那是什么，但像对我来说，“软品味”是一个非常宽泛的话题。嗯，我怎么想？我的意思是，我同意。我只是觉得这是一个太大的话题，无法分解，特别是对于研究者来说，有很多“我看到了就会知道”类型的问题是无法验证的。

<details>
<summary>Original English</summary>

**Swix**: Usually that's this is my uh from builder to researcher question because we do have researchers listening and I'm just like well that's but like soft taste for me please is it's like a very broad topic. Uh what do I think? I mean I agree. I just think that it's too big of a topic to break down particularly because there's a lot of I'll know it when I see it type uh email which is unverifiable for for researchers to do.

</details>

**David Singleton**: 所以……

<details>
<summary>Original English</summary>

**David Singleton**: So

</details>

**Swix**: 是的，我的意思是，我确实经常和研究者交流，嗯，我们讨论这个话题，我认为大多数人同意……

<details>
<summary>Original English</summary>

**Swix**: yeah, I mean I I do talk to researchers quite often and uh we talk about this topic and I think most people agree

</details>

**David Singleton**: 你知道，构建模型来生成代码的好处之一就是它是可验证的。所以，嗯，你知道，它非常容易处理，他们同意下一个问题是如何提升需求层次，进入这些品味问题，量化品味很难。但我实际上有点兴奋，因为有些人将开始这样做。你知道，那时我认为世界上一些真正标志性的公司将开始成为人们真正尝试调试和理解创意过程的地方。我对此感到非常兴奋。

<details>
<summary>Original English</summary>

**Swix**: that you know one of the great things about building models to generate code was just you know it's so verifiable. So, um, you know, it's very tractable and they agree that the next problem is how do you kind of step up that hierarchy of needs and get into these taste questions and quantifying taste is hard. But I'm actually kind of excited that some people are going to start doing this. And, you know, that's when I think that some of the really iconic companies in the world will start to become places where, you know, folks really try to like debug and understand the creative process. And I get pretty excited about that.

</details>

**David Singleton**: 是的。嗯，我认为我们正在慢慢揭示智能的真正含义，而我们采纳然后放弃的基准，因为它们已被解决，基本上就是我们正在以一种不同于我们进化方式的方式进化机器智能，但我们正在慢慢理解智能的含义，对吧？嗯，这很有趣，我想知道它们未来如何压制我们，但我们甚至还没有达到那个阶段，我们只是想让它达到一个我们喜欢机器智能给我们带来什么的地方，有时……

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. Uh I I think we are slowly uncovering what intelligence really means and and the the benchmarks that we adopt and then abandon because they're solved is is basically us evolving the machine intelligence in the way that we a different way than we evolved but we are slowly understanding what it means to be intelligent right and uh and it's it's interesting I wonder how they suppress us in the future but like we're not even there yet we're just like get get it to a place where we like what we get from the machinist sometimes

</details>

**Swix**: 以前是 30%，现在是 95%，但仍然有 5%。

<details>
<summary>Original English</summary>

**Swix**: you It used to be 30%, now it's like 95%, but still there's that 5%.

</details>

**David Singleton**: 没错。

<details>
<summary>Original English</summary>

**David Singleton**: That's right.

</details>

**Swix**: 是的。我们还有其他需要讨论的话题吗？

<details>
<summary>Original English</summary>

**Swix**: Yeah. Any other topics we should have touched on?

</details>

**David Singleton**: 不，我想我们已经涵盖了所有内容，但我想提醒大家。

<details>
<summary>Original English</summary>

**David Singleton**: No, I think we've covered everything, but I want to remind everyone.

</details>

**Swix**: **CTA** **dreamer.com/lenpace**。

<details>
<summary>Original English</summary>

**Swix**: **CTA streamer.com/lenpace**.

</details>

**David Singleton**: 是的。不，这很划算。我的意思是，来吧。是的。所以，谢谢你提供这个。

<details>
<summary>Original English</summary>

**David Singleton**: Yes. No, it's a it's a very good deal. I mean, like, come on. Like, yeah. So, thank you for offering that.

</details>

**Swix**: 酷。好的，**Swix**，非常感谢。这很有趣。

<details>
<summary>Original English</summary>

**Swix**: Cool. Well, **Swix**, thank you so much. This was fun.

</details>

**David Singleton**: 是的。谢谢你。嗯，我们会让 **Alejandro** 在 **YouTube** 上放上闪烁的霓虹灯牌。

<details>
<summary>Original English</summary>

**David Singleton**: Yeah. Thank you. Uh, but we'll get **Alejandro** to put like flashing neon signs on the on the **YouTube**.

</details>

**Swix**: 酷。太棒了。

<details>
<summary>Original English</summary>

**Swix**: Cool. Wonderful.

</details>

**David Singleton**: 嗯，好的。非常感谢。

<details>
<summary>Original English</summary>

**David Singleton**: Um, all right. Thanks so much.

</details>

**Swix**: 酷。太棒了。谢谢你。

<details>
<summary>Original English</summary>

**Swix**: Cool. Awesome. Thank you.

</details>