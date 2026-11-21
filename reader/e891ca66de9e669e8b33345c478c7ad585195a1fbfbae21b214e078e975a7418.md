---
author: How I AI
date: '2026-03-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=HbWu_eYIHKQ
speaker: How I AI
tags:
  - ai-agents
  - software-development-workflow
  - prompt-engineering
  - no-code-low-code
  - product-development
title: 非技术背景的Dan Roth如何利用Claude Code和双AI代理开发iOS应用
summary: 本访谈探讨了LinkedIn编辑Dan Roth如何从非技术背景转型为iOS应用开发者，并详细介绍了他的“双AI代理”工作流。他将Claude Code配置为“Bob”（构建代理）和“Ray”（审查代理），并以“挑剔的客户”身份协调二者协作。该工作流强调规划、模块化开发，并通过代理间谨慎的交接提升学习效率。他还分享了利用AI进行日常任务管理的非编程工作流，展示了AI在非技术人员赋能开发中的巨大潜力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - LinkedIn
  - OpenAI
  - Work OS
  - Vanta
  - Apple
products_models:
  - Claude Code
  - iOS
  - Xcode
  - Commutely
  - Cursor
  - Copilot
media_books: []
status: evergreen
---
### AI代理协作与角色设定

**Claire Vo**: 你们给自己的Claude Code命名了，然后给它们指令让它们互相监听。

<details>
<summary>Original English</summary>

**Claire Vo**: So you have actually named your claws and then you give them instructions to listen to each other.

</details>

**Dan Roth**: 是的，它们必须互相交流。一个叫“**Bob**”（Bob the Builder），它有不断停止的指令，并且所有事情都必须通过**Ray**（审查代理）那里，Ray的工作是资深软件工程师，痴迷于安全。他会在里程碑处审查代码，守护安全架构。然后第三个代理是我。我是那个在Bob想做某事和Ray说“你不能做”之间经常出现分歧时，来打破僵局的人。

<details>
<summary>Original English</summary>

**Dan Roth**: Yes, they have to talk to each other. One is called the builder app is called Bob. Bob the builder and he's got instructions to stop constantly and you have to run everything by Ry who's the review agent. Ray's job is senior software engineer who is obsessed with security. He reviews code at milestones, guard security architecture, and then the third agent is me. I am the person who breaks the tie that often happens between Bob wanting to do something and racing you can't do it.

</details>

**Claire Vo**: 而你做这一切，是因为你职业生涯中并非软件工程师出身。

<details>
<summary>Original English</summary>

**Claire Vo**: And you are doing all of this as someone who has not spent their career as a software engineer.

</details>

**Dan Roth**: 有一阵子我以为我像个平庸的PM，然后我想不，也许我更像个**架构师**。现在我意识到，架构师实际是了解真正细节的。PM则非常严谨，将整个应用都牢记于心，能够很好地进行优先级排序。我是个糟糕的优先级排序者。我只是一个非常挑剔的客户。所以，我认为这就是“**vibe coder**”的角色，我深切关心的是什么？我就像在房子里走来走去，告诉架构师：“不，我想要这个房间是蓝色的。我知道你觉得这不是个好主意，但我告诉你这就是我想要的。”

<details>
<summary>Original English</summary>

**Dan Roth**: For a while I thought I'm like a mediocre PM and then I was like no maybe I'm more like an architect. And now I realize like an architect actually knows real details. A PM is like super rigid and keeps the entire app in their head and they're able to really prioritize well. I'm a bad prioritizer. All I am is a really picky customer. So, I think that is like the role of the vibe coder is what do I care about deeply? I'm like walking through this house and I'm telling the architect, "No, I want this room blue. I know you don't think it's a good idea. I'm telling you this is what I want."

</details>

### 从内容创作到应用开发者的转型

**Claire Vo**: 欢迎回到《How I AI》。我是**Claire Vo**，产品负责人和AI痴迷者，使命是帮助你用这些新工具更好地构建。今天我邀请到**LinkedIn**的编辑**Dan Roth**。他以商业作家和编辑开始职业生涯，但不知何故，他成了一名软件工程师，通过**vibe coding**将**iOS**应用一路发布到**App Store**。他将向我们展示他的“**dueling Claude Code**”设置，让**Bob**和**Ray**构建高质量的生产级软件。让我们开始吧。

<details>
<summary>Original English</summary>

**Claire Vo**: Welcome back to How I AI. I'm Claire Vo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Dan Roth who's the editor of LinkedIn and started his career as a business writer and editor, but has somehow become a software engineer vibe coding iOS apps all the way to the app store. He's going to show us his dueling cloud code setup that lets Bob and Ray build high quality production grade software. Let's get to it.

</details>

**Claire Vo**: 本集由**Work OS**赞助播出。AI已经改变了我们的工作方式。工具有助于团队编写更好的代码，分析客户数据，甚至自动处理支持工单。但有一个问题。这些工具只有在深度访问公司系统时才能良好运作。你的**副驾驶**需要查看你的整个代码库。你的聊天机器人需要搜索内部文档。对于企业买家来说，这引发了严重的安全担忧。这就是为什么这些应用从第一天起就面临严格的IT审查。为了通过审查，它们需要安全的**身份验证**、**访问控制**、**审计日志**以及整套企业级功能。从头构建所有这些，工作量巨大。这就是**Work OS**的用武之地。**Work OS**提供企业功能的**嵌入式API**，让你的应用能够快速实现企业级就绪并推向市场。把它想象成企业功能的**Stripe**。**OpenAI**、**Perplexity**和**Cursor**已在使用**Work OS**来加速发展并满足企业需求。加入他们和数百家其他行业领导者，访问**workos.com**。立即开始构建。

<details>
<summary>Original English</summary>

**Claire Vo**: This episode is brought to you by work OS. AI has already changed how we work. tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. But there's a catch. These tools only work well when they have deep access to company systems. Your co-pilot needs to see your entire codebase. Your chatbot needs to search across internal docs. And for enterprise buyers, that raises serious security concerns. That's why these apps face intense IT scrutiny from day one. To pass, they need secure authentication, access controls, audit logs, the whole suite of enterprise features. Building all that from scratch, it's a massive lift. That's where work OS comes in. Work OS gives you drop-in APIs for enterprise features so your app can become enterprise ready and scale up market faster. Think of it like Stripe for enterprise features. OpenAI, Perplexity, and Cursor are already using work OS to move faster and meet enterprise demands. Join them and hundreds of other industry leaders at workos.com. Start building today.

</details>

**Claire Vo**: **Dan**，欢迎来到《How I AI》。我喜欢像我这样，也许有几年经验的人，因为我们看到了技术随时间的变化，市场随时间的变化，以及我们自己的职业生涯随时间的变化。我喜欢你的故事之处在于，你看到了你所处行业的一次类似转变，你看到了它可能带来的颠覆和恐惧，而现在你再次看到了这一点，并且你真正投入其中。所以，告诉我们你是如何从非技术背景，到现在我们将看到一些强大的**Claude Code**技巧和**iOS**应用，通过**vibe coding**一路发布到**App Store**的。

<details>
<summary>Original English</summary>

**Claire Vo**: Dan, welcome to How I AI. What I like about having people like me maybe that have a couple years of experience under their belt is we've seen technology shift over time and we've seen market shift over time and we've seen our own career shift over time. And what I love about your story is you've seen a shift like this in an industry that you've been in and you've seen how disruptive and scary it can feel and now you're seeing this again and you're really leaning into it. So tell us how you came from your background which is non-technical into now we're going to see some power claude code tips and iOS apps kind of vive coded all the way to the app store.

</details>

**Dan Roth**: 我曾是一名长期的商业作家，在**Fortune**、**Wired**、**Forbes**工作过，我记得在**Fortune**杂志时，博客开始兴起。突然间，每个人都能接触到我曾认为是作家独有的东西。我们能够以其他任何人都无法做到的方式与世界对话。那几乎就像是这种将思想传播到世界的能力的垄断。然后**WordPress**和**Tumblr**出现了，突然每个人都可以和每个人交流，你发现思想的爆炸式增长，当时这很可怕，但后来你意识到，哦，实际上你想要拥抱它，思想越多越好。所以，作为一名作家，它改变了；作为一名编辑，它改变了我对能够追求谁以及开放什么的看法。我突然意识到有更多的人可以分享想法和进行报道，这比我几年前认为的要多得多。当**生成式AI**开始进入**编码**领域时，一切变得清晰，我们任何人都可以构建任何东西。我也有完全相同的想法，但它从一种状态变成了另一种。我曾处于它的对立面，就像“天哪，我有很多想推出的东西的想法”，过去我不得不去说服一位工程师或产品经理和我一起做，我只是试图影响构建什么。然后我突然可以开始自己构建了。所以，这成了我的痴迷，痴迷于构建，以至于现在当我与朋友和家人在一起时，他们会说：“请不要再谈论你正在构建的东西了。我们不想再听了。”我不得不收敛一些。但在周末，这正是我喜欢做的事情。所以，就像**超级碗**进行的时候，我会坐在笔记本电脑前，为我已有的应用开发新功能。

<details>
<summary>Original English</summary>

**Dan Roth**: I was a longtime business writer was at Fortune, Wired, Forbes, and I remember being at Fortune during the uh introduction of blogging. And all of the sudden, everyone had access to something that I thought was something that was unique to writers. We were able to talk to the world in a way that no one else could. And that was kind of like a monopoly almost on this ability to get ideas out into the world. And then WordPress came around and Tumblr and suddenly everyone could talk to everyone and you discovered this explosion of ideas and I have and it was scary at the time and then it was you realize oh actually you want to embrace this more ideas the better and so uh you as as a writer it changed and as an editor it changed how I thought about who I could go after and open up like suddenly I realized there were way more people that could be sharing ideas and reporting than I ever thought were possible a couple years ago when uh generative AI started making its way into coding and it became clear that any of us could build anything. I had the exact same idea but it went from being this I was on the opposite side of it. It was like oh my god I've had all these ideas of stuff I wanted to launch and in the past I would have had to go convince an engineer or a PM to go team up with me on something and I was just trying to influence what got built and then I could suddenly start building. So, it has become an obsession of mine of building to the point now where when I'm with friends and family, they're like, "Please stop talking about the stuff that you're building. You know, we don't want to hear about it anymore." And uh and I I just have to like ratchet it back. But on the weekends, it is like that is what I love spending my time doing. So, like while the Super Bowl was going on, I will be on my laptop building either like working on some new feature for the apps that I have out there.

</details>

**Claire Vo**: 很有趣的是，你并不孤单。我们刚刚邀请了**Verscell**的CEO **GMO**，他把这种优先级排序请求称为“向政府请愿”，就是每次你想构建什么东西，都得去求政府（不幸的是，政府是由**产品经理**运营的），然后说“求求你，政府，通过这项决议，把我的按钮完全发布到生产环境。”然后我们也听到所有人，无论技术背景与否，都觉得这构建起来真的很有趣，这是一种新的爱好，新的学习空间。

<details>
<summary>Original English</summary>

**Claire Vo**: Well, what's really funny is you are not alone. We just had GMO the CEO of Verscell on and he calls that request for prioritization like petitioning the government where anytime you had to have something built you had to go to the government which were unfortunately run by product managers and say please oh please government would you pass this resolution to ship my button in totally in production and then we're also hearing from everybody whether technical or not that this is just really fun to build and it's kind of new hobby new new space for learning and um unfortunately maybe or fortunately where they're spending too much time.

</details>

**Dan Roth**: 是的。

<details>
<summary>Original English</summary>

**Dan Roth**: Yeah.

</details>

**Claire Vo**: 所以，现在我们将从你的痴迷中受益，你将向我们展示，作为一个没有技术背景的人，你是如何使用**Claude Code**和其他工具来构建真正的生产级应用的。那么你是怎么做的？你的“独家秘方”是什么？

<details>
<summary>Original English</summary>

**Claire Vo**: So we'll what we're going to benefit from your obsession now and you're going to show us how you as somebody who has a nontechnical background has used cloud code and some other tools to build real production apps. So what do you do? What's what's your special sauce?

</details>

### 构建AI代理工作流

**Dan Roth**: 当然。首先我应该告诉你，我是从**Cursor**上的一门课程开始的。所以我是从如何使用**Cursor**开始的，我可以和你分享那个链接，它是一个免费课程：如何用**Cursor**构建应用。我看了那个课程，然后我开始用**Cursor**。但随着时间推移，我停止使用**Cursor**，因为我并不真正关心文件保存在哪里。我没有去编辑任何东西。我实际上不需要那个。我只需要告诉别人我在做什么。我需要告诉**Claude**我在做什么。所以**Claude Code**对我来说是一个巨大的突破。我将向你展示我是如何构建的。所以，如果你能看到我的屏幕，我将向你展示我做的一件事就是我用**Claude**，我根据我的构建阶段，在每月20美元的套餐和每月100美元的套餐之间来回切换。所以现在我用的是每月100美元的套餐。我有一个**Claude**窗口，里面有我所有的——我把所有东西都放在项目中。所以这是我的**Commutely**项目，如果你能看到的话。

<details>
<summary>Original English</summary>

**Dan Roth**: Sure. So first I should just tell you I started this with a course I took on cursor. So it started with how to use cursor and I can share that link with you on the it's a free course. how to build with cursor, how to build apps and I watched that and so I started with cursor and then over time I stopped using cursor because I didn't really care where the files were kept. I wasn't going in and editing anything. I didn't actually need that. I just needed to tell people what I was doing. I needed to tell Claude what I was doing. So Claude code was the big unlock for me. And I'll show you what how I build. Um, so if you can see my screen here, I'm going to show you one one thing I do is I keep I use Claude and I ratchet back and forth between the $20 a month plan and the $100 a month plan depending on where I am in my building. So right now I'm in the $100 a month plan. Uh, I keep a claude window up that has all of my I keep a pro I keep everything in projects. So this is my commutely project if you can see this.

</details>

**Claire Vo**: 是的。

<details>
<summary>Original English</summary>

**Claire Vo**: Yep.

</details>

**Dan Roth**: 我在这里保留了一个运行中的功能，那就是**Commutely**的功能想法和跟踪器。所以，当人们告诉我他们希望这个应用能做什么时，我就把它记下来。这是一个应用，基本上能让你永远不用再为**纽约市**的火车奔跑。你可以知道它是否——我总是错过火车。我想，我要为自己构建一个应用，它基本上就是：火车快来了吗？我是该走还是该跑？它就是为此设计的。这是一个完美的产品市场契合，因为我就是整个产品。

<details>
<summary>Original English</summary>

**Dan Roth**: And I keep one running feature here which is commutely feature idea and tracker. So, this is as people talk to me about what they wish the app did. And this is an app for being able to basically never run for the New York City train. Again, you can know if it's I keep missing the train. I'm like, I'm gonna build an app that is just for me that is basically like is the train almost here? Can I walk or do I have to run? That is what it's designed to do. It was that perfect product market fit because I was the entire product.

</details>

**Claire Vo**: 我们称之为个性化。现在是个性化软件的兴起。

<details>
<summary>Original English</summary>

**Claire Vo**: We call this personalized. So, the rise of personalized software right now.

</details>

**Dan Roth**: 太棒了。这是最好的。然后突然你发现其他人也关心这个。这就像，嗯，我有一个社群。所以这是为了我的火车通勤者社群。他们给了我很多反馈，我一直在保存——我在这里有一个**Claude**聊天窗口，里面全是功能想法，我给了它一个提示，让它根据构建所需的时间和这个功能对应用的增长影响来排名。所以我会读给你听最上面的提示，它基本上是说，让我们用这个作为**Commutely**的想法流，当我记录它们时，跟踪它们并提供指导：构建时间估算和估算来回讨论的小时数，以及在1到3的两个维度上的潜在影响分数：客户满意度和增长影响。然后我给了它一堆想法，我只是不断地给它新想法，它就有了这个表格。所以，如果你能看到，这些是按构建时间排名的**Commutely**功能。所以，我做什么呢？当我有空的时候，我进入这个聊天，找到一个我心想“我有几个小时空闲，我可以去构建一些东西”的功能，我就会去找它。所以，我列表上的事情有**Siri**集成、独立小部件。我已经构建了**SEO**友好的博客、位置感知，但我想也许这次构建一个我一直想做的东西会很有趣，那就是我构建了这个**计划自动更新**功能。我知道我每天早上7:30通常会离开家。我只希望**Commutely**告诉我火车在哪里。所以我构建了它，但没人用。所以现在我需要能够构建。现在我必须考虑**发现**。顺便说一句，这是我学到的另一部分，就是构建是一回事。**营销**是完全不同的另一部分。所以现在我从一个“准糟糕的PM”变成了“准糟糕的PMM”，因为我也在学习如何为我的应用做营销。

<details>
<summary>Original English</summary>

**Dan Roth**: It's amazing. It's the best. And then suddenly you discover other people care about this also. And it's like, well, I have a community. So, this is for my community of train runners. They give me lots of feedback and I've been keeping a um uh I keep I I keep one clawed chat available here that is just all the feature ideas and I've given it a prompt to basically rank it in terms of time it'll think to build and the growth that it will think that uh this feature should have for the for the app. And so the I'll read you the the prompt at the top which is basically uh let's use this as a running idea of ideas for commutely as I log them keep track of them and offer guidance time estimate to build and estimated back and forth hours potential impact score on two one to three scales customer happiness and growth impact and then I've given it a bunch of ideas and I just keep feeding it new ideas and it has this table here uh so these are if you can see this commutely features ranked by build time and so what I do is when I free time, I go into this chat and I find a feature that I'm like, I've got a couple hours. I can go and build something and I'll look for it. So, the things on my list to do are Siri integration, standalone widget. I've already built this SEO friendly blog, location awareness, but I thought maybe for this it would be fun to build something I've been trying to do, which I built this scheduled automatic um updates, which is I know that every day at 7:30 a.m. I usually leave my house. I just want commutely to tell me where the trains are. So, I built that, but no one's using it. And so I need to be able to build. Now I have to think about discovery. By the way, this is the other part of this I've learned is like the building is one thing. The marketing is a total other part of it. So now I've gone from being a quasi crappy PM to now being a quasi crappy PMM as I learn how to basically do marketing for my app, too.

</details>

**Dan Roth**: 这里有一件有趣的事情，我正在想，正如你所说，我是一个真正的**产品创始人**，我真的会构建列表上的所有东西，然后才能强迫自己做任何哪怕是远程被称为**营销**的事情。所以，如果你能克服你的——你知道，我们行业里说的“攀登**尴尬之山**”，然后成为一名**营销人员**，你会对你的应用的**分发**非常满意。所以，我之前已经和**Claude Code**合作制定了**保留计划**，我把所有东西都保存为**Markdown**文件。所以我的**Commutely**项目里有一个**document**文件夹，里面有**Markdown**文件列表，我每次与**Claude**合作时，我都会说“把它写入文件，记录一切，记录一切”，我这样做有两个原因。第一是**上下文窗口**。**Claude**会不断忘记它正在处理什么，然后我也会忘记我正在处理什么，因为我只在周末做这个。所以到了周六，我会拿起它，然后想“等等，我在构建什么？我记不清了，我进展到哪一步了？”所以所有东西都被记录下来。这是我试图给任何像我一样的人的建议。所以我们创建这些**MD**文件。这是保留计划，它已经提出了一个通用计划。但现在我需要去构建它。

<details>
<summary>Original English</summary>

**Dan Roth**: Here's here's a funny thing that I'm I'm thinking as you say that is I know I'm a true product founder and that I will literally build everything on this list before I can will myself to do anything that is like even remotely called marketing. And so if you can get over your uh you what we say in the industry you know if you can climb cringe mountain and just become a marketer you will be very happy with the distribution of your app. So I've already worked with uh cloud code on coming up with a retention plan and I save everything as MD file as markdown files. So I've got within my commutely project there's just there's a document folder and then there's a list of markdown files and I just every time I'm working with commut every time I'm working with claude I'm saying write it into a file log everything log everything and I do that for two reasons. One is the context window called it's constantly forgetting what it's working on and then I'm forgetting what I'm working on because I only do this on weekends. So there on Saturday I'll pick it up and I'll be like what wait what am I building? I can't remember and how far did I get? So everything gets logged. That is one tip I try to give anyone that is in my my shoes also. So we make these MD files. So this is retention plan and it's come up with a general plan. But now I need to go build it.

</details>

**Dan Roth**: 所以我保留两个标签页。我使用**终端**，并打开两个标签页。一个是用于构建，一个是用于审查。现在我给**Claude**赋予了两种个性，我可以通过使用——一个叫“**Bob**”（Builder），“**Bob the Builder**”，所以我启动**Bob**，这是我的构建应用，他有指令。

<details>
<summary>Original English</summary>

**Dan Roth**: So I keep two tabs. So I use terminal and I keep two tabs open. One is for building and one is for reviewing. Now I've given claude two personalities which I can bring up by using one is called the builder app is called Bob. Bob the builder and so I bring up Bob and this is my builder app and he's got instructions.

</details>

**Dan Roth**: 告诉我你的工作指令。这只是为了向你展示**Bob**正在尝试做什么。还有一个针对不知道如何做的人的快速问题。首先，我从未见过有人自定义他们的**Claude**主题，以让他们知道他们正在运行哪个版本的**Claude**。我见过很多人运行多个**Claude**版本。

<details>
<summary>Original English</summary>

**Dan Roth**: Tell me your instructions on how you work. So this is just to show you what Bob is trying to do. And quick question for folks that don't know how to do this. First of all, I have never seen somebody customize their Claude theme to let them know what version um flavor of Claude they have running. I've seen a lot of people that run multiple cla multiple flavors.

</details>

**Claire Vo**: 是的。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah.

</details>

**Dan Roth**: 嗯，我从未见过那种。专业提示，你可以那样做。其次是你如何构建这些别名，它们有不同的设置？你如何实际、技术性地创建**Bob**？如果你能给我们一些高层次的解释。这不会太令人满意，因为我所做的就是进入**Claude**，然后我说我不想每次都告诉你你是什么。所以这是你作为**Bob**的要求，让我，让我拉出**Bob**是什么。所以，嗯，这是我教**Bob**做的事情。这基本上就是我希望**Bob**做的事情的提示。所以这是**Bob**告诉我：

<details>
<summary>Original English</summary>

**Dan Roth**: Um so I've never seen that. Pro tip, you you can do that. Second is how do you how have you built these as aliases that have different settings? How do you build actually how do you technically make Bob? If you could just give us some high level. This is not going to be super satisfying because what I did was I go into Claude and I say I don't want to have to tell you every single time what you are. So this is your requirement as Bob and let me let me pull up what Bob is here. So uh well here this is this is what I've taught Bob to do. This is basically my prompt on what I want Bob to do. So this is Bob telling me

</details>

**Dan Roth**: **Bob**的想法。一切都必须先计划。随着时间的推移，我学会了在计划完成之前不要构建。我听过你的嘉宾说过同样的话，就是先计划，然后一切都必须以模块化方式构建。我不想有大量的**意大利面条式代码**。我在第一个项目中就学到了这一点。代码变得难以管理。所以我说你是一个精益的构建者，无论那意味着什么。然后记录一切。我们谈论过这个。这是重要部分，我告诉**Claude**，我告诉**Bob**，你必须不断停止，并且必须把所有事情都交给**Ray**（审查代理）来处理。

<details>
<summary>Original English</summary>

**Dan Roth**: Bob's idea. Everything has to plan first. I've learned over time like you don't build until it's done planning. I've heard guests of yours say the same thing like plan plan first and then everything has to be built in modules. I don't want like tons of spaghetti code. I learned that with my first project. The code gets unwieldy. So I say you're a lean builder whatever that means. And then document everything. We talked about that. This is the important part is I say to Claude the I say to Bob, you have to stop constantly and you have to run everything by Ry who's the review agent. [laughter]

</details>

**Dan Roth**: 哈哈。所以让我转到**Ray**。这是**Ray**。让我展示一下。

<details>
<summary>Original English</summary>

**Dan Roth**: So let me get over to Ray. So this is Ray. Let me bring

</details>

**Claire Vo**: 我太喜欢这个了。当你拉过来的时候。所以你真的给你的Claude Code起了名字。

<details>
<summary>Original English</summary>

**Claire Vo**: I love this so much. While you pull this over. So you have actually named your claws.

</details>

**Dan Roth**: 是的。

<details>
<summary>Original English</summary>

**Dan Roth**: Yes.

</details>

**Claire Vo**: 然后你给它们指令让它们互相监听。

<details>
<summary>Original English</summary>

**Claire Vo**: And then you give them instructions to listen to each other.

</details>

**Dan Roth**: 是的。它们必须互相交流。

<details>
<summary>Original English</summary>

**Dan Roth**: Yes. They have to talk to each other.

</details>

**Dan Roth**: 所以**Ray**的工作是**资深软件工程师**，痴迷于安全，并确保我们不会偏离我们的设计指南。所以我还有一份完整的设计文档。然后确保——这就是**Ray**所做的。**Ray**，我所做的，我会在**Bob**构建之前审查他的计划。他会在里程碑处审查代码，守护安全架构，他关心的是——这在我的提示中也有——**成员信任**、**安全**、**架构**、**完整性**和**质量**。我说，而且因为**Claude**总是**橡皮图章式**地批准一切，我确信你的观众也经常看到这种情况。一切都是天才之作。你总是完美的。我不得不告诉它：

<details>
<summary>Original English</summary>

**Dan Roth**: So Ray's job is senior software engineer who is obsessed with security and with making sure that we don't uh leave what our um uh any of our design guidance. So I've got a whole design document also. And then make sure So here's what Ray does. Right. What I do, I review Bob's plans before he builds. He reviews code at milestones, guard security, architecture, and what he cares about, and this is what it was in my prompt is member trust, security, architecture, integrity, and quality. And I say, and because Claude is always rubber stamping everything, I'm sure your viewers see this all the time. Everything's genius. You're always perfect. I have to tell it,

</details>

**Dan Roth**: 你必须对某些事情说不。然后我来打破僵局。所以第三个代理是我。我是在**Bob**想做某事而**Ray**说你不能做之间经常出现分歧时，来打破僵局的人。

<details>
<summary>Original English</summary>

**Dan Roth**: you have to say no to things like you're And then I break the tie. So, the third agent is me. I am the person who breaks the tide that often happens between Bob wanting to do something and Ray saying you can't do it.

</details>

**Claire Vo**: 嗯，我能建议另外两个代理吗？一个是**Amy**，产品经理，她会说：“抱歉，**Bob**和**Ray**，那个还没有被排入优先级。”

<details>
<summary>Original English</summary>

**Claire Vo**: Well, can I suggest two other agents? One is Amy, the PM that says, "Sorry, Bob and Ray, that hasn't been prioritized yet."

</details>

**Claire Vo**: 然后是**Joe**，销售，无论是否构建完成，他都会把它卖出去，然后你就有整个团队准备就绪。好的，那么**Ray**和**Bob**一起工作。那么**Bob**如何调用**Ray**呢？

<details>
<summary>Original English</summary>

**Claire Vo**: And then there's Joe, the AE that sells it anyway, whether or not it's been built and then you have the whole team ready to go. Okay, so Ry and Bob work together. So how does Bob invoke Ray?

</details>

**Dan Roth**: 所以**Bob**必须——我们来做这个。比如说我们要构建**保留计划**。

<details>
<summary>Original English</summary>

**Dan Roth**: So Bob has to So let's do this. say I'm going to say we were going to build uh the retention plan.

</details>

**Claire Vo**: 好的。所以我用“@”它找到了它的`retention plan.MD`，然后我只是说，因为**Bob**知道自己的角色，我说“开始吧”。

<details>
<summary>Original English</summary>

**Claire Vo**: All right. So I use the at it finds its retention plan MD uh and then I just say because Bob knows what his role is. I say get started.

</details>

**Dan Roth**: 所以他现在应该进入计划模式。**Bob**——我甚至不应该用——我不应该拟人化这些人。所以它现在进入了——

<details>
<summary>Original English</summary>

**Dan Roth**: So he should now go into plan. Bob I shouldn't even use I shouldn't personify these people. So it now goes into

</details>

**Claire Vo**: 拟人化**AI**。我觉得这很——你知道，这就是我们的工作方式。

<details>
<summary>Original English</summary>

**Claire Vo**: personify AI. I think it's very it's you know it's just the way we work

</details>

**Dan Roth**: 真的。我感觉太诡异了。我讨厌这样。我讨厌我这样做的时候。所以，它开始阅读我之前给你看的关于这个**保留计划**的**Markdown**文件。我几周前想出了这个，审查过，我觉得它很好。现在我们得开始构建它。

<details>
<summary>Original English</summary>

**Dan Roth**: really. I feel so creepy about it. I hate it. I hate I hate when I do it. So, it's starting to read this markdown file that I showed you earlier of what this retention plan is. I came up with this weeks ago. Reviewed it. I thought it was pretty good. And now we got to start building it.

</details>

**Claire Vo**: 这太棒了。我觉得这太有趣了。

<details>
<summary>Original English</summary>

**Claire Vo**: This is amazing. I think this is so fun.

</details>

**Dan Roth**: 所以，一旦它在这里完成，它就会吐出一些东西，然后我必须复制粘贴到**Ray**那里。现在，我过去所做的是，我没有构建**Ray**，我只是说“让它通过安全代理”。那样也能奏效，但我不喜欢的是我无法看到安全代理在说什么。所以构建代理通常会说“安全通过了”或者“安全希望我改变一件事”，但因为我也在努力学习，我想知道它在哪里卡住了。

<details>
<summary>Original English</summary>

**Dan Roth**: So, once it's done here, it will spit out something that I have to then copy and paste into Ray. Now, what I've done in the past is I haven't built Ray and I've just said run this past the security agent. That works, but what I don't like about it is I can't see what the security agent is saying. So what what the builder agent will often just say is security passed it or security wants me to change one thing but because I'm trying to learn this also I want to know what it's stumbling on.

</details>

### AI与学习：保留微摩擦的价值

**Claire Vo**: 我认为这是一个被低估的**工作流**。你知道，你之前说过我离开了**Cursor**，因为我不看文件，也不编辑东西，我内心的软件工程师听了就胃溃疡发作了。嗯，我是一个积极的代码阅读者，但你正在做这个，我甚至认为一些这样的**微摩擦**，不一定像——是的，你可以启动一个**Ray**子代理，做各种花哨的事情，但我确实认为在过程中增加一点摩擦，迫使你复制粘贴，放过去，阅读**Ray**说了什么。完全正确。

<details>
<summary>Original English</summary>

**Claire Vo**: I think that's an underappreciated workflow which is you know earlier when you said I got out of cursor cuz I'm not looking at files and I'm not editing things the software engineer in me just started like my ulcer starts to just flare. Um, I am an aggressive code reader, but you are taking this and I I even think some of these like micro frictions that aren't necessarily like, yeah, could you spin up a a Ray sub agent and do all sorts of fancy stuff, but I do think putting a little bit of friction in the process where you're actually forced to like copy and paste, put it over, read what Ry says. Exactly.

</details>

**Dan Roth**: 这确实有助于学习。所以我不希望人们，特别是那些从非技术领域转向更多技术任务的人，把效率做得太高，以至于你没有真正学习这个过程，因为那样你就可以建立更强大的系统。我对此完全同意。这不只是为了构建。我是为了学习。但我很早就发现，我不会学习如何编码。就像现实一点。我尝试过，但我觉得没那么有趣。我想，我完全是个新手。我想，嗯，它实际上是在构建代码。我只是想了解它为什么构建它正在做的事情。我发现作为一个人可以独特解决的问题是，比如我们是否应该优先处理这个问题？或者这看起来会非常昂贵。这值得做吗？这会超出我的预算吗？我的**Commutely**预算是零，除了我付给**Claude**的钱。所以，我必须一直告诉它，这看起来很贵。我不想做这个。好的。所以现在这里完成了。让我们来看看这个。嗯，这是一个相当长的**实施计划**。

<details>
<summary>Original English</summary>

**Dan Roth**: Does help with learning. And so I don't want people to, especially people that are moving from non-technical into more technical tasks, to make it so efficient that you're not actually learning the process because then like you, you can set up even more powerful systems. Couldn't agree with that more. That has been, and I'm not doing this just to build. I'm doing this to learn. But what I figured out early is that I'm not going to learn how to code. Like just being realistic. Like I tried to do that. I got I didn't find it that interesting. And I'm like, I'm a total beginner. And I'm like, well, it's actually building code. I just want to understand why it's building what it's doing. And the problems that I find that I can solve uniquely as a human are things of like, should we prioritize this or not? Or you're this seems like it's going to be really expensive. Like, is this worth doing? Is this going to break my budget? My budget for commutely is zero except what I'm paying for claude. And so I don't I have to tell it all the time like that seems expensive. I don't want to do this. All right. So here, this is it's now done here. Let's come up with this. Uh, it's pretty long implementation plan.

</details>

**Dan Roth**: 所以，通常我会坐在这里阅读整个东西。嗯，但我告诉它构建它。**Bob**所做的一切都必须在一个分支中完成。这是我学到的一个教训。我以前常常把所有东西都发布到主分支。我早期就学到了那样做的痛苦。

<details>
<summary>Original English</summary>

**Dan Roth**: So, normally I would sit here and read this whole thing. Uh, but I told it build it. Everything that Bob does has to be done in a in a branch. That's one lesson I've learned. I used to ship everything to Maine. And I learned the pain of that early on. Um,

</details>

**Claire Vo**: 我最近对我一个朋友大喊：“搞个分支啊，老兄！你快把我逼疯了。”

<details>
<summary>Original English</summary>

**Claire Vo**: I yelled at a friend recently. I was like, "Make a branch, dude. Like, you're stressing me out."

</details>

**Dan Roth**: 天哪。但我以前没有意识到这一点。我后来从真正的工程师那里发现，并不是说我合并分支到我的另一个应用时，我把分支合并到主分支，它没有工作。出于某种原因，它并没有完美地合并。我花了几周时间才弄清楚为什么它没有合并。所以我从未——这对我来说是一个教训，就是它并不总是无缝运作。你可能很清楚这一点。

<details>
<summary>Original English</summary>

**Dan Roth**: Oh my god. But what I I didn't realize this. I found this out from real engineers later is it's not when I merged the branch in my other app. I merged the branch into main and it didn't work. There were for some reason it didn't like merge perfectly. It took me weeks to be able to figure out why it wasn't merging. So I never I didn't this was a lesson to me is it doesn't always just work seamlessly. You probably know that well.

</details>

**Claire Vo**: 是的。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah.

</details>

**Dan Roth**: 好的。哈哈。好的。所以这里我正在复制计划。通常我会阅读整个计划，但这次我不会，因为我只是将它构建到一个分支中，然后稍后处理。所以**Ray**现在准备好了。我粘贴进去。好了。现在**Ray**要开始工作了。

<details>
<summary>Original English</summary>

**Dan Roth**: Okay. [laughter] All right. So here I've copying the plan here. Normally I would read this whole plan but I'm not going to this time because I'm just going to build this into a branch and then work on it later. So Ry is now ready for this. I paste it in. There we go. And now Ray is going to get to work.

</details>

**Claire Vo**: 那么**Ray**在这里做的是那种——嗯，这在架构上是否正确？是否安全？有没有，你知道，我们常说的“此地有恶龙”？有没有什么你可能需要担心而**Bob**忽略了的东西？我真的很喜欢这个。我们实际上从未见过有人进行**角色到角色**的交接。我们见过很多人可能会使用像**Opus45**或**Anthropic模型**来构建计划，然后他们会把它交给像**Codeex模型**来审查。**Codeex**有点像一个有点刻薄的**资深工程师**。完全正确。

<details>
<summary>Original English</summary>

**Claire Vo**: And so what Ry is doing here is the sort of um is this architecturally correct? Is it secure? Are there any, you know, as we say there be dragons? Like is there anything in there that you need to be worried about that Bob mixed? And I really like this. We we haven't actually seen somebody do a persona to persona handoff. What we have seen is a lot of people will maybe use like an Opus45 or an anthropic model to build the plan and then they'll actually hand it to like a codeex model to review it. Codeex is like a little a little mean um senior staff engineer. Totally.

</details>

**Claire Vo**: 所以，有这样的交接是件好事，你知道，我所说的“**对决代理**”，就像你在一个团队中工作一样。我认为你能理解这一点，对吗？你编写代码，或者以我的产品经验来说，你写出一个产品想法，然后你把它带给其他人，他们会说：“哦，但是你忘了我们必须有这个**合规性**的东西，或者你难道不记得我们对这个客户的数据分析结果是他们讨厌那个部分，或者设计部门说这在我们的**设计系统**中实现起来技术上真的很难。”所以，我确实认为，从你的组织流程中提取一些流程，然后弄清楚如何使它们**代理化**，对于那些特别是**经理**出身的人来说，是一种非常自然的方式。

<details>
<summary>Original English</summary>

**Claire Vo**: And so it is it is kind of nice to have that um handoff and can you know what I say is like dueling agents to just get well very similar to when you're working in a team. I think you can appreciate this, right? You write code and you're or you write up in my experience in product like you write a product idea and then you bring somebody else into it and they're like, "Oh, but you forgot we have to have this compliance thing or don't you remember that when we did the data analysis on this customers hated that piece or design says actually this is really technically hard to implement in our design system." And so I do think just taking some um taking some flows from your organizational process and then figuring out how to make them agentic is a really natural way for people who especially have been managers.

</details>

**Dan Roth**: 是的。

<details>
<summary>Original English</summary>

**Dan Roth**: Yep.

</details>

**Dan Roth**: 来构建他们自己的**AI生产力堆栈**。

<details>
<summary>Original English</summary>

**Dan Roth**: To start building out their own little AI productivity stack.

</details>

**Dan Roth**: 把经理这个概念用在这里太棒了，就是作为**AI代理**的经理。你在管理这些代理。

<details>
<summary>Original English</summary>

**Dan Roth**: It's such a great call that manager that idea of being a manager for this. You are managing these agents.

</details>

**Dan Roth**: 是的。所以，比如，我发现**Commutely**的一个问题是，它很大程度上依赖于**iOS**上的**实时活动**。当你跟踪火车时，你的手机是锁定的，你只是去看看。**实时活动**结果发现有很多限制。而**Claude**会一直忘记这些限制。所以它会提出这样的建议：“哦，你应该这样做。”我就会说：“我们知道，我们已经学过这个了。你难道不记得了吗？两周前我们试图构建它。结果是，当应用不在屏幕上时，它实际上无法**ping**到**MTA**的**API**。”所以，这就像是作为**经理**——我是在其他地方读到这句话的，不是我说的，但有人曾经说过，管理**AI**就像管理一个非常聪明但宿醉未醒的**实习生**。哈哈。我一直有这种感觉。就像“你是个天才，但你今天早上没状态。记住，我们已经讨论过这个了。”嗯，**AI**非常像我所说的**早期职业人才**的优势。是的。

<details>
<summary>Original English</summary>

**Dan Roth**: Yep. So like one of the things I find a lot with commutely is it depends on this app is really built around live activity on iOS. That is where you are tracking your train is your phone is locked. You just go and look at it. Live activity has it turns out to have all kinds of limitations. And Claude will forget those limitations all the time. And so it will suggest things like oh you should just do this. And I'm like we know we've learned this already. Don't you remember? Like two weeks ago we tried to build it. It turns out that like it can't actually ping the MTA's API when it's when when the the app is not uh in in on the screen. And so I it's like being a manager of I read this somewhere else. This is not my thing, but someone once said that managing AI is almost like managing a really smart but hung over intern. [laughter] And I feel that way all the time. It's like you're a genius but you don't have it this morning. Just remember we've gone over this already. Well, an AI is very similar to how I've positioned the benefits of what we call early career talent. Yeah.

</details>

**Claire Vo**: 也就是说，能力很强，非常兴奋，经验不足以知道他们不该做某些事。所以偶尔你会得到伟大的结果。

<details>
<summary>Original English</summary>

**Claire Vo**: Which is like very capable, very excited, too experienced to know they shouldn't do something. So, occasionally you get greatness,

</details>

**Claire Vo**: 对吗？

<details>
<summary>Original English</summary>

**Claire Vo**: right?

</details>

**Claire Vo**: 但我们应该使用**分支**和**PR**，以防万一。

<details>
<summary>Original English</summary>

**Claire Vo**: But we should use a branch in a PR just just in case.

</details>

**Dan Roth**: 完全正确。

<details>
<summary>Original English</summary>

**Dan Roth**: That's exactly it.

</details>

### 企业级AI产品与安全合规

**Claire Vo**: 作为一个**AI创始人**，你习惯于冲刺以实现**产品市场契合**、下一轮融资或第一份企业合同。但速度不足以应对**AI初创公司**。买家从第一天起就期望**安全**、**合规**和**透明度**。这就是为什么严肃的**AI初创公司**使用**Vanta**。凭借为快速发展的**AI团队**构建的深度集成和自动化工作流，**Vanta**能让你快速准备好审计，并通过持续监控确保安全，随着你的模型、基础设施和客户的演进。**Langchain**、**Ryder**和**Cursor**等**AI创新者**通过早期与**Vanta**合作确保安全，从而更快地扩展并达成更大的交易。听众可以在**vanta.com/howi**领取**Vanta**的1000美元特别优惠。

<details>
<summary>Original English</summary>

**Claire Vo**: As an AI founder, you're used to [music] sprinting towards product market fit, your next round, or that first enterprise contract. But speed isn't enough [music] for AI startups. Buyers expect security, compliance, and transparency from day one. [music] That's why serious AI startups use Vanta. With deep [music] integrations and automated workflows built for fastm moving AI teams, Vanta gets you audit [music] ready fast and keeps you secure with continuous monitoring as your models, infra, and customers evolve. AI innovators like Langchain, [music] Ryder, and Curser scaled faster and closed bigger deals by getting security right early with Vanta. [music] Listeners can claim a special offer of $1,000 off Vanta at vanta.com/howi.

</details>

**Claire Vo**: 太棒了。所以现在**Bob**提出了一些**边缘案例**的担忧，我认为是——

<details>
<summary>Original English</summary>

**Claire Vo**: Great. So now Bob has raised some edge case concerns, which I think are

</details>

**Dan Roth**: **Ray**提出了**边缘案例**的担忧。

<details>
<summary>Original English</summary>

**Dan Roth**: Ray has raised the edge case concerns.

</details>

**Claire Vo**: 是的，**Ray**提出了。然后嗯，说**Bob**的计划很稳固。所以你把它传回给**Bob**了吗？

<details>
<summary>Original English</summary>

**Claire Vo**: Yep, Ry has. And then um says Bob's plan is solid. So then do you pass this back to to Bob?

</details>

**Dan Roth**: 是的，没错。所以现在我直接复制粘贴回去。

<details>
<summary>Original English</summary>

**Dan Roth**: Yeah, exactly. So now I copy and paste this right back.

</details>

**Claire Vo**: 嗯，它得到了绿灯，然后**Bob**就要去构建了。现在下一步是我将把它导入**Xcode**，进行新的构建，然后**在模拟器中测试**，看看它是否奏效，在我的手机上测试，然后我通常会立即发布到**Apple**。所以，我一直努力每周更新**Apple**。我要说的是，构建我的两个应用最难的部分就是**App Store**。哈哈。我完全不知道。驾驭**App Store**是一个完全独立的部分。我有很多聊天记录，我都在问“**Apple**到底想要我做什么？”，仅仅让**Claude**教我如何使用**App Store**，这真是一项成就。我觉得这几乎是成为一个构建者所剩的最后一点阻力，就是驾驭**App Store**。

<details>
<summary>Original English</summary>

**Claire Vo**: Uh it's got the green light and then Bob's going to go build. Now the next step in this is that I will then take this and put it into Xcode and do a new build uh and then test it out in the simulator, see if it works, test it on my phone, and then I usually ship it to Apple right then. So I've been trying to do weekly updates to Apple. I will say the hardest part of building my two apps has been the app store. [laughter] I had no idea. Navigating the app store is a whole separate I've got I have so many chats where I'm like what does Apple want from me here and just getting Claude to teach me how to use the app store has been a real I feel like that's almost the last friction left in being a builder is navigating the app store.

</details>

### AI时代的痛点与产品机会

**Claire Vo**: 我对初创公司有几个相关的请求。我们已经拥有了所有需要的**编码代理**。它们会变得更好。我们很满意。我们选择太多了。

<details>
<summary>Original English</summary>

**Claire Vo**: I have a couple related requests for startups. We're all we have we have all the coding agents we need. They're going to get better. We're we're fine. We are spoiled for choice.

</details>

**Dan Roth**: 我们需要**AI**用于**App Store**提交。我们需要**AI**用于**SAP Aribba**提交采购需求和**POS**。

<details>
<summary>Original English</summary>

**Dan Roth**: We need AI for app source submissions. We need AI for uh SAP Aribba submitting procurement recruits and POS

</details>

**Claire Vo**: 而且我们仍然需要那个完美的**AI CRM**。所以，嗯，所有那里的构建者，如果你能为我们解决这些非常无聊但非常有价值的问题，你会有很多客户在等着。

<details>
<summary>Original English</summary>

**Claire Vo**: and we still need that perfect AI CRM. So uh all the builders out there if you could give us these very boring but very high value problem solved. You have a lot of customers waiting out there.

</details>

**Dan Roth**: 你知道，我可能会构建一个来解决这个**App Store**设计问题，再次是为了解决你自己的问题。所以现在我做的方式是，你知道，当你在**App Store**上做某事时，你必须展示你的应用是什么样子。

<details>
<summary>Original English</summary>

**Dan Roth**: You know one that I might build actually to solve again this idea of solving for your own problems is app store designs. So the right now the way that I do, you know, when you when you when you do something in the app store, you have to show what your app looks like

</details>

**Dan Roth**: 我一直在用**Canva**，但我真的不喜欢**Canva**的**AI**。我觉得我得不到我需要的东西。所以我可能会尝试构建一个应用，它能直接获取人们的截图，然后把它变成适用于**App Store**的东西。

<details>
<summary>Original English</summary>

**Dan Roth**: and I've been using Canva for it, but it's really Canvas AI I don't love. I find like I'm not getting what I need. So I might try to build an app that just takes people screenshots and turns it into something for the app store.

</details>

**Claire Vo**: 我喜欢这个。好的，所以计划，**Bob**正在提出一些设计问题。

<details>
<summary>Original English</summary>

**Claire Vo**: I love it. Okay, so right the plan, Bob is asking some design questions.

</details>

**Dan Roth**: 完全正确。所以这很棒。所以，我在过去写过关于这个的文章，但有一段时间我以为：“哦，我只是个平庸的**PM**。”然后我心想：“不，也许我更像个**架构师**。”现在我意识到，架构师实际是了解真正细节的。**PM**则非常严谨，将整个应用都牢记于心，能够很好地进行优先级排序。我是个糟糕的优先级排序者。我只是一个非常挑剔的客户。所以，我认为这就是“**vibe coder**”的角色，我深切关心的是什么？我就像在房子里走来走去，告诉**架构师**：“不，我想要这个房间是蓝色的。我知道你觉得这不是个好主意。我告诉你这就是我想要的。”所以挑剔的客户，我认为至少是我的角色。我就是这样看待我的角色的。所以在这个案例中，**Bob**在说，嗯，我必须决定一些**UX**决策。

<details>
<summary>Original English</summary>

**Dan Roth**: Exactly. So this is great. So, this is I I have I've written about this in the past, but like and for a while I thought, "Oh, I'm I'm like a a mediocre PM." And then I was like, "No, maybe I'm more like an architect." And now I realize like an architect actually knows real details. A PM is like super rigid and like has understands the keeps the entire app in their head and they're able to really prioritize well. I'm a bad prioritizer. All I am is a really picky customer. So, I think that is like the role of the vibe coder is what do I care about deeply? I'm like walking through this house and I'm telling the architect, no, I want this room blue. I know you don't think it's a good idea. I'm telling you this is what I want it. So the picky customer is I think the role that is at least my role. That's how I think about my role. So in this case, Bob is saying uh there's some UX decision I have to decide.

</details>

**Claire Vo**: 我喜欢“挑剔的客户”这个概念，因为我本来想说，我觉得这就像是**QA**，只是盯着小细节说“不，那是错的，那个按钮做得不对”。所以我喜欢把这个提升到“不，不，不，不，我不是在做质量保证。”

<details>
<summary>Original English</summary>

**Claire Vo**: I like this concept of a picky customer because I was going to say what I feel like is Q QA that's just looking at little edges and and saying no, that's wrong and that button isn't quite doing. So, I like elevating this to no, no, no, no. I'm not doing quality assurance.

</details>

**Dan Roth**: 是的。

<details>
<summary>Original English</summary>

**Dan Roth**: Yeah.

</details>

**Claire Vo**: 我正在审视并成为我最挑剔的客户。你知道，我正在像我们常说的那样，在喝**香槟**之前先闻一闻。所以，这是一种非常有趣的方式来思考你在为自己构建时的角色。

<details>
<summary>Original English</summary>

**Claire Vo**: I am going through and being my own pickiest customer. You know, I'm I'm sniffing my champagne before I drink it as as we say. And so, that's a really fun fun way to think about your role when you're building for yourself.

</details>

**Dan Roth**: 是的。而且它也像我的另一个应用，一个**播客剪辑**应用一样。视频需要一点时间才能从播客剪辑中生成，出现了一些错误。有一条消息只是说：“你的视频正在创建中。”我想：“实际上，我希望它有更好的**语气**。我希望它**有趣**。我希望它说‘天哪，你剪辑了一个很棒的播客片段。’”所以，作为一个挑剔的客户，我可以说：“这就是这个东西的语气。让它有趣。”

<details>
<summary>Original English</summary>

**Dan Roth**: Yeah. And it also does like in my other app, which is a podcast clipping app, the there was all this it took a little while for the video to be made of the podcast clip and there was some kind of error. There was a message just saying, "Your video is being created." And I'm like, "Actually, I want this to have a better voice. I want this to be funny. I want it to say like, "Oh my god, you clipped a great part of the podcast." And so, as the picky customer, I could say, "This is the voice of this thing. Make it funny

</details>

**Dan Roth**: 然后为它写了一些文案。所以，我更多地是这样看待它的，而不是**QA**，因为你想要把你的**个性**融入其中。

<details>
<summary>Original English</summary>

**Dan Roth**: and wrote some copy for that." So, that's that's how I I think about it more than QA because you want to bring your personality into it.

</details>

**Claire Vo**: 是的。

<details>
<summary>Original English</summary>

**Claire Vo**: Yep.

</details>

**Dan Roth**: 好的。所以在这个案例中，它正在问我一些选项。它给了我一些选项。我可以选择自己的选项。为了节省时间，我只想说：“好的，让我们保持**MTA蓝色**。”

<details>
<summary>Original English</summary>

**Dan Roth**: All right. So, in this case, it's asking me some options. It's giving me some options. I could pick my own option. Just for the sake of time, I'm gonna just say let's Okay, let's keep the M MTA blue.

</details>

**Dan Roth**: 好的。它要开始构建了。

<details>
<summary>Original English</summary>

**Dan Roth**: All right. And it's gonna start building.

</details>

**Claire Vo**: 太棒了。你这一切都是在周末做的。那么，你是在运行多个**Bob**和多个**Ray**吗？你是单独做还是？你的代理管理能力如何？

<details>
<summary>Original English</summary>

**Claire Vo**: Great. And you're doing this all on the weekend. So, are you doing I have to ask, are you running multiple Bobs and multiple rays? Do you single do it? What's your own what is your own capacity for agentic management?

</details>

**Dan Roth**: **Bob**被允许派生出子代理。所以，这是一件事。我的提示是：“你被允许拥有你管理的代理。你对这些代理负责。我要追究你的责任。嗯，你的子代理不能创建自己的子代理。”这就是我在这方面的规则。

<details>
<summary>Original English</summary>

**Dan Roth**: Bob is allowed to spin off subobs. So, that is the one thing. What my my prompt says you are allowed to have agents that you manage. You're responsible for these agents. I'm holding you accountable. Uh and your sub agents can't create their own sub agents. So that's my rule on how to do this.

</details>

**Claire Vo**: 明白了。所以**Bob**可以生成，但他最终是直接负责人。

<details>
<summary>Original English</summary>

**Claire Vo**: Got it. So Bob can spawn, but he's ultimately the directly responsible.

</details>

**Dan Roth**: 完全正确。**Ray**不能生成。**Ray**可以生成。只有一个**看门人**，那个看门人就是**Ray**，而且不会有更多。我喜欢——

<details>
<summary>Original English</summary>

**Dan Roth**: Exactly. Ray cannot spawn. Ray can spawn. There's only one one gatekeeper and that gatekeeper is Ray and there shall be no more. I love

</details>

**Claire Vo**: 完全正确。

<details>
<summary>Original English</summary>

**Claire Vo**: Exactly.

</details>

**Claire Vo**: 那是非常**首席工程师**的气场。就像这个人。

<details>
<summary>Original English</summary>

**Claire Vo**: That's very principal engineer energy. This like one guy.

</details>

**Dan Roth**: 是的。你去找他，然后你会说：“我们能做这个吗？”只有他能说“是”或“不”，而且他既不管理也不受管理。那就是你的**Ray**。完全正确。嗯，**Claire**，我能做到这一点，因为我已经在一家科技公司工作了15年。所以我观察了——很多都是基于我合作过的人。正如你所说，**首席工程师**。我看到我的**产品经理**合作伙伴会说：“我们真的应该让**Sanjay**过目一下。”你知道，总有那么一个人不断地出现，就像是“去搞清楚这个是否可行，或者我们会在哪里犯错。”所以**Ray**就是基于这样的原型。

<details>
<summary>Original English</summary>

**Dan Roth**: Yeah. and you go to him and you're like, can we do this? And only he can say yes or no and he neither manages nor can be managed. That is that is your Ray. Totally. Well, Claire, like one of the things that I have I'm I'm able to do this because I've now worked inside of a tech company for 15 years. And so I've watched how so a lot of this is based on people I've worked on worked with and exactly to your point the principal engineer like I've watched my PM partners be like we should really run this past Sanjay. And you know there's like one person who keeps coming up as like just find out whether this is going to work or not or where we're going to make a mistake. And so that is exactly what Ry is based on.

</details>

**Claire Vo**: 你合作过的每一个**Ray**现在都会想：“这是，这是我吗？我是**Ray**吗？”哈哈。

<details>
<summary>Original English</summary>

**Claire Vo**: Every Ray that you've ever worked with is now like is this is this am I is [laughter] this supposed to am I Ray?

</details>

**Claire Vo**: 好的。所以我们正在看**Claude Code**生成代码。然后，你知道，也许我们不会展示这部分，但你只是会把它导入**Xcode**，确保它编译通过，测试它，然后，你知道，把余生都花在把它发布到**App Store**上。

<details>
<summary>Original English</summary>

**Claire Vo**: Okay. So, we're watching Cloud Code generate code as it does. And then, you know, maybe we won't show this part, but you're just going to take this into Xcode, make sure it compiles, test it, and and you know, spend the rest of your life getting it into the app store.

</details>

**Dan Roth**: 完全正确。所以，让我快速向你展示，如果我可以的话，在**Xcode**里会是什么样子。我实际上已经开始真正喜欢在**Xcode**里工作了，但我想我可能只使用了它的5%。我尝试把**Claude**导入**Xcode**。他们刚构建了这个新的部分，嗯，你可以在**Xcode**中使用**Claude Code**。我发现这不值得。我一直内存不足，所以我干脆就不用了。嗯，但你进入**Xcode**，你——

<details>
<summary>Original English</summary>

**Dan Roth**: Exactly. So, let me just show you quickly if I can what the what this would look like is you go into Xcode. I've actually come to really like working inside Xcode, but I think I'm probably only using like 5% of it. I tried putting Claude into Xcode. They're like they just built this new part of um where you can actually use cloud code in Xcode. I have not found it to be worthwhile. I kept running out of memory so I just quit using it. Um but you go into Xcode, you

</details>

**Dan Roth**: 你做什么？你按**Command Shift K**。你清理一下。

<details>
<summary>Original English</summary>

**Dan Roth**: do what's you do? Command shift K. You do a clean of this.

</details>

**Claire Vo**: 看看你，真是个专家软件开发人员。

<details>
<summary>Original English</summary>

**Claire Vo**: Look at you expert software up here.

</details>

**Dan Roth**: 我应该说我不知道我在做什么。所以让我们把这一点说清楚。我只是学了这些东西。我基本上是个**机器人**。我就是那个**Claude**告诉我该做什么的人。

<details>
<summary>Original English</summary>

**Dan Roth**: I should say I don't know what I'm doing. So let's just make that clear. I have like learned these things. I'm basically the bot. I'm like the the claude has told me what to do.

</details>

**Claire Vo**: 你是**代理浏览器**。

<details>
<summary>Original English</summary>

**Claire Vo**: You're the agentic browser.

</details>

**Dan Roth**: 完全正确。就是这样。就像告诉我怎么做。我正在做。我只是像有人在牵着我的线一样。然后你点击**构建**，那是**Control B**吗？它会运行这个东西。完成后，它会弹出**模拟器**。我可以测试它。**模拟器**我觉得有80%接近真实。但你真的——有很多**边缘情况**，直到你把它放到手机上你才会意识到。我在我的手机上测试它，然后我快速发布到**Apple**，将其放入**TestFlight**，测试大约一个小时，然后我直接发布到**App Store**。

<details>
<summary>Original English</summary>

**Dan Roth**: Exactly. That's exactly it. Like tell me how to do this. I'm doing it. I'm just like someone's pulling my strings. And then you go to build, which is what? Control B. It's going to run this thing. When it's done, it'll pop up the uh the simulator. I can test it out. The simulator is I find like 80% close. But you really like there's so many edge cases you don't even realize until you get it onto your phone. I test it on my phone and then I quickly ship it to Apple, get it in test flight, test it for like an hour and then I just ship it to the app store

</details>

**Claire Vo**: 然后你就有所有这些额外的时间，所以你可以准时赶上你的火车。

<details>
<summary>Original English</summary>

**Claire Vo**: and then you have all this extra time so you can make it to your train on time.

</details>

**Dan Roth**: 完全正确。就是这样。

<details>
<summary>Original English</summary>

**Dan Roth**: Exactly. That's exactly it.

</details>

### AI代理工作流总结

**Claire Vo**: 这是一个很棒的流程。总结一下给大家。我们看到的是一种**对决式的Claude Code**。一个是构建者，一个是像**架构师审查者**一样的。你构建你的——你在**Claude**网页或桌面应用中有一个常设的**优先级路线图聊天**，你总是把想法放进去，然后根据一个简单的**三点框架**重新排序。周末你从中挑选一个。你制作一个**PRD**。你把**PRD**交给**Bob**。**Bob**在**Claude Code**中调用**计划模式**。它会构建一个计划。你把它复制粘贴给**Ray**。**Ray**要么批准要么给出反馈。你把它交回给**Bob**。**Bob**进行构建。我喜欢它。然后你使用了**Xcode**中你甚至不知道的键盘命令，然后你把它发布到**App Store**。

<details>
<summary>Original English</summary>

**Claire Vo**: This is an awesome flow. Just to recap for folks. So what we saw is sort of dueling clawed codes. One's a builder, one's sort of like an architect reviewer type. You build your you have a a standing prioritization roadmap chat in the clawed web or desktop app where you're always putting in ideas rep prioritizing them against like a simple threepoint framework. On the weekends you pluck one of those. You make a PRD. You give Bob the PRD. Bob invokes plan mode in Cloud Code. It builds a plan. You copy and paste that over to Ray. Ray either greenlights it or gives feedback. You give it back to Bob. Bob builds love it. And then you used um keyboard commands you don't even know in Xcode and you ship it to the app store.

</details>

**Dan Roth**: 百分之百正确。

<details>
<summary>Original English</summary>

**Dan Roth**: That is 100% right.

</details>

**Claire Vo**: 而你做这一切，作为一名从未从事软件工程师职业的人。

<details>
<summary>Original English</summary>

**Claire Vo**: And you are doing all of this as someone who has not spent their career as a software engineer.

</details>

**Dan Roth**: 我接触过很多软件工程师。我观察过他们工作，但我自己从未做过这些。

<details>
<summary>Original English</summary>

**Dan Roth**: I've been around a lot of software engineers. I've watched them work, but no, I have never done any of this myself.

</details>

**Claire Vo**: 这太棒了。这是一个我们从未真正见过的流程。我认为它是一个非常有用且可重复的流程，其他人也可以使用。嗯，我想，你知道，如果在**旧金山**有人还在使用公共交通，那我肯定会为我们请求一个地区选项。但与此同时，如果你能构建一个**Commutely**，它能告诉我什么时候我需要对我的孩子们大喊大叫，以什么程度让他们准时出门上学，那会很好。是的。显然那是我们需要的。我将要——我将要复制你的流程，然后构建下一个。

<details>
<summary>Original English</summary>

**Claire Vo**: This is amaz This is a flow we really haven't seen. And I think it's a useful really repeatable one that others can use. And um I you know if anybody in San Francisco you used uh public transport anymore then I would definitely request a regional option for us. But in the meantime if you could build a commutely that tells me like when I need to yell at my kids at what level to get out of the door to school on time that would be Yeah. Apparently that's what we need. I'm going to I'm going to replicate your flow and build that next.

</details>

**Dan Roth**: 很好。好的。所以，它在这里。**Commutely**现在正在打开。呃，哦，不。我没有打开**Metro**。我总是记不住命令。呃——

<details>
<summary>Original English</summary>

**Dan Roth**: Nice. All right. So, here it is. Commutely is now opening on this. Uh oh, nope. I don't have Metro up. I can never remember the command. Uh

</details>

**Claire Vo**: 我要建议任何总是记不住命令的人。是的。

<details>
<summary>Original English</summary>

**Claire Vo**: I'm going to have to suggest for anybody who can never remember the command. Yeah,

</details>

**Claire Vo**: 你应该观看我们与**John Linquist**的节目，他向我们展示了如何设置**终端别名**。你可以直接让**Claude**设置一个**终端别名**。嗯，它会运行这些你需要经常运行的常规东西。所以如果你想输入**Metro**，是的，并让**终端**运行它，你可以使用**Claude Code**创建一个**终端别名**来完成。

<details>
<summary>Original English</summary>

**Claire Vo**: you should watch our episode with John Linquist who shows us how to set up terminal aliases. You can just ask Claude to set up a terminal alias. Um that will then run these like regular things that you need to run. So if you wanted to type in Metro Yeah. and have the terminal run it, you could create a terminal alias using cloud code to just make

</details>

**Dan Roth**: 我把它放在一个笔记文件里，但总是找不到。所以那样方便多了。

<details>
<summary>Original English</summary>

**Dan Roth**: I have it like in a notes file somewhere which I can then never find. So that's that's much handier.

</details>

**Claire Vo**: 让我们回到**Claude Code**。我只是——我必须让你做这个。我们会直播。这可以是一个直播的《How I AI》，然后说“你能为**Metro**命令创建一个别名吗，这样以后更容易运行？”顺便说一句，我真的尽量不说“你能”或“请”。这是我确保我不拟人化这个东西的一部分。这就是我阻止机器人接管的方式。

<details>
<summary>Original English</summary>

**Claire Vo**: Let's go back to cloud code. I'm just I got to have you do this. We'll do it live. This can be a live how AI and say can you make me an alias for the metro command so it's easier to run in the future. By the way, I've really tried to not say can you or please. This is part of how I'm like making sure that I don't personify this thing. This is how I stop the robots from taking over.

</details>

**Dan Roth**: 这是两件事之一。这会引出我们的最后一个问题，那就是你如何与机器人对话？我太南方腔了。我总是说“求求你，行吗？”

<details>
<summary>Original English</summary>

**Dan Roth**: This is this is one of two things. This will go to our last question, which is how do you talk to talk to the bots? I am so southern. I'm like, would you pretty please

</details>

**Dan Roth**: 请问，先生，女士。嗯，另一件事实际上是一个快速育儿小贴士。我总是问我的孩子：“你们想把洗碗机里的东西拿出来吗？”他们会说：“不，我们不想把洗碗机里的东西拿出来。”所以这是另一件事，你不想让你的**AI**说“不”。好的，所以现在你输入**Metro**，它就会重启**bundler**。

<details>
<summary>Original English</summary>

**Dan Roth**: do this? I Please, sir. Yes, ma'am. Um the other thing is actually quick parenting tip. I always finding ask my kids like, "Would you do you want to unload the dishwasher?" And they're like, "No, I don't want to unload the dishwasher." And so that's another another thing is you don't want your AI to say no. Okay, so now anytime you type in Metro, it'll restart the bundler. I

</details>

**Claire Vo**: 这对你来说太棒了。

<details>
<summary>Original English</summary>

**Claire Vo**: amazing for you.

</details>

**Claire Vo**: 不客气。**How I AI**直播。

<details>
<summary>Original English</summary>

**Claire Vo**: You're so welcome. How AI live.

</details>

**Dan Roth**: 哇，刚刚学到了新东西。我喜欢这个。

<details>
<summary>Original English</summary>

**Dan Roth**: Wow, just learned something new. I love that.

</details>

**Claire Vo**: 好的，让我们看看它现在是否在运行。

<details>
<summary>Original English</summary>

**Claire Vo**: Okay, so let's see if it's running now.

</details>

**Dan Roth**: 让我们打开模拟器。

<details>
<summary>Original English</summary>

**Dan Roth**: So let's open the simulator.

</details>

**Dan Roth**: 看，它就在那里。所以，这正是我想要构建的。这是**Commutely**的一个隐藏功能，你可以设置它在特定时间启动。**Bob**和**Ray**刚刚合作构建了这个东西。现在，每天早上7点，工作日，我都可以得到这个。但现在，如果我去看我的早晨通勤，它会向我展示这些火车已经准备好了。我得到了这个。如果我进入锁屏，它会显示在这里。

<details>
<summary>Original English</summary>

**Dan Roth**: Look, there it is. So, this is exactly what I wanted to build. This was a hidden feature on commutely is that you could set it up to go off at certain times. Bob and Ray just worked together to build this thing. And now, every day, 7 a.m. weekdays, I can get this. But now, if I go to my morning commute, it's going to show me these trains are ready. I get this. If I go to the lock screen, it'll show up here. So,

</details>

**Claire Vo**: 如果你在第14街，你的下一班火车五分钟后就到。你得开始跑了。

<details>
<summary>Original English</summary>

**Claire Vo**: if you were at 14th Street, your next train's coming in five minutes. You got to start running.

</details>

**Dan Roth**: 我喜欢这个。好的。在**App Store**下载这个应用。给**Dan**所有的反馈，这样他就可以把它交给**Claude**、**Bob**和**Ray**。好的，**Dan**，我们来回答一些快速问题，然后我让你回去工作。

<details>
<summary>Original English</summary>

**Dan Roth**: I love it. Okay. Download this app on the app store. give Dan all the feedback so he can give it to Claude, Bob, and Ray. All right, Dan, let's hop to some lightning round questions and then I will get back get you back to your day job

</details>

### 非编程工作流与AI管理哲学

**Dan Roth**: 这样我们就可以在周末结束时，玩更多的**Claude Code**。所以我想问你的第一个问题是，你认为有没有什么非编码的工作流或技巧，是你觉得非常有用的，人们可以在五分钟内学会，并能让他们的生活变得更好？我们这整集都在谈论我周末做的事情，但我大部分时间实际上是在工作中度过的。我管理一个400人的团队。我整天都在进行**上下文切换**。我不断地依赖**Copilot**来完成这个，因为它能访问我所有的文件和我的整个团队。所以，我通常以“我遗漏了什么？”开始或结束一天。

<details>
<summary>Original English</summary>

**Dan Roth**: so we get to the end of the week and on the weekend you can start playing with some more cloud code. So the first question I have for you is are there any sort of non-coding workflows or tips or tricks that you think are really useful that people can pick up in like five minutes that you think are going to make their life better? We've talked this entire episode about something I just do on weekends, but most of my time is actually spent at work. I run a 400 person team. I've got a context switch all day long. I rely on Copilot constantly to do that because it has access to all my files and my entire uh team. So I my command that I start the day with or I end the day with usually is what did I drop the ball on?

</details>

**Dan Roth**: 我会向你展示这个。“我遗漏了什么？”然后我通常会说——为了这次节目，我将说“匿名化任何名称或项目名称，因为这将被我没有合作过的人看到”。完美。

<details>
<summary>Original English</summary>

**Dan Roth**: And I'll show you that. What did I drop the ball on? And then I usually and then for the point of this show I'm going to say anonymize any names or project names as this will be seen by people I don't work with. Perfect.

</details>

**Dan Roth**: 哈哈。好的。嗯，它会通过**Outlook**。它会通过**Teams**。它会通过任何更新的文件。它知道我的上司是谁。它知道谁向我汇报。它会跟踪我一天中不断点击的东西。所以，它会浏览我所有的电子邮件，找到我没有回复的地方，或者我没有回复的团队。最棒的是，它不仅仅是我被**@**提到的地方。它知道我真正感兴趣的东西。所以，是我一直在关注的项目。

<details>
<summary>Original English</summary>

**Dan Roth**: [laughter] Okay. Uh it's going to go through Outlook. It's going to go through Teams. It's going to go through any updated files. It knows who I report to. It knows who reports to me. and it keeps track of things that I'm constantly clicking on during the day. So, it'll find it'll go through all my emails and find places where I'm not responding or teams where I'm not responding. And what's great is it's not just places where I've been app mentioned. It's stuff that it knows that I am actually interested in. So, projects that I've been like con kind of like following over time.

</details>

**Claire Vo**: 我认为这真正有用的是，我们见过很多人做**晨间日结**，但我们从未见过有人做**晚间提醒**，那就是“嘿，你忙碌了一整天，然后你忘了X、Y和Z。”我们中有多少人，特别是**经理**，希望以一个无所事事的早晨开始，并在晚上完成所有事情。所以我认为，即使把**AI**排除在外，把这种做法从早上的前端转移到下午，当你能够实际处理白天遇到的问题时，也是一个非常棒的主意。

<details>
<summary>Original English</summary>

**Claire Vo**: What I think is really useful about this is we've seen a lot of people do their morning daily digest, but we haven't seen anybody do their evening nightly nudge, which is, hey, you got through your whole day and you forgot X, Y, and Z. And how many of us, especially managers, want to start the morning with nothing to do and having wrapped it up all in the evening. So I think just even take AI out of it. Moving that practice from upfront in your morning to in the afternoon when you can actually do something about the stuff that hit your plate during the day is a really great idea.

</details>

**Dan Roth**: 对我来说就是这样。这是我离开前的30分钟。我做这个提示，然后我就可以在这里查看。所以这里有一个来自长期创作者的**入站升级请求**。有人对我不满。呃，我没有回复。我有一个从未发送的**回复草稿**。

<details>
<summary>Original English</summary>

**Dan Roth**: That's exactly it for me. This is my 30 minutes before I leave. I ask this I do this prompt and then I can go through here. So here's an inbound escalation from a longtime creator. Someone's unhappy with me. Uh I didn't reply. I I have a draft reply that I never sent.

</details>

**Claire Vo**: 嗯，会议后续内容查找。

<details>
<summary>Original English</summary>

**Claire Vo**: Uh meeting followup content seek

</details>

**Dan Roth**: 哈哈。

<details>
<summary>Original English</summary>

**Dan Roth**: [laughter]

</details>

**Dan Roth**: 就是这样。就像你到某个阶段，你开始管理这么多不同的项目。你会想：“我知道我正在遗漏一些事情。告诉我我遗漏了什么。”所以这是我的救星。这就像我指望**AI**能够做到的，让我更好地完成工作，这样我就可以在周末构建像**Commutely**这样亏钱的应用。哈哈。

<details>
<summary>Original English</summary>

**Dan Roth**: and this is it. This is like you get at some point you start managing so many different projects. You're like I know I'm dropping the ball. Just tell me what I am dropping the ball on. So this is my savior. This is like what I count on AI to be able to do to make me better at my job so that I can spend the weekends building money losing apps like commutely. [laughter]

</details>

**Claire Vo**: 是的，你可以**vibe code**，但你不能**vibe code**毛利率。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah, you can vibe code. You cannot vibe code gross margin. So

</details>

**Dan Roth**: 那是真的。那是真的。

<details>
<summary>Original English</summary>

**Dan Roth**: that's true. That is true.

</details>

**Claire Vo**: 好的。然后我的最后一个问题，我问每个人，但当**AI**没有给你想要的东西时，你说你不想**拟人化AI**，嗯，我做了。所以我们在这方面是相反的。非常有趣。

<details>
<summary>Original English</summary>

**Claire Vo**: All right. And then my last question I ask everybody, but when AI is not giving you what you want, you've said you don't want to personify AI, um, which I I do. So, we're on opposite sides of this. Very interesting.

</details>

**Dan Roth**: 那么你的策略是什么？你喜欢消灭**Bob**和他的子嗣吗？你——你是那种用大写字母的人吗？你的**提示策略**是什么？

<details>
<summary>Original English</summary>

**Dan Roth**: What is your then what is your tactic? Do you do you like kill Bob and his spawns? Like do you Yeah. Are you an all caps person? What's your prompting strategy?

</details>

**Dan Roth**: 我是说，有时候，我通常非常直接。我只是说：“这就是你正在做的。”我尽量不说“请”或“谢谢”，因为再说一次，我只是不希望在某个时候，当我们达到**AGI**时，它们会掌管一切，我只是在斗争直到我们达到那个点。我坚守我的人性。嗯，但通常我只是花很多时间说：“我们已经讨论过这个了。你已经谈论过这个了。去搜索你的记忆，找到我们做过这个的时候。”这就像在**育儿**一样。我像你一样有三个男孩，我依赖很多事情，我会说：“我们已经谈过这个了，还记得吗？”你知道，你的孩子就像——你知道他们想做正确的事情，所以这只是很多帮助他们达到目标。我们有一个说法，我从一位前经理那里学到的，我们在**LinkedIn**经常说：“**假设善意**。”这就是——顺便说一句，这和我上一段**新闻编辑室**的工作方式有很大不同，那时你总是**假设恶意**。在科技公司，你**假设善意**。我现在把它带到了我的家人身上，也带到了与**AI**的构建中。所以我**假设AI有善意**，但需要被提醒我们的工作方式。所以我不会大喊大叫。我很清楚，我会尽量给它一点宽容。

<details>
<summary>Original English</summary>

**Dan Roth**: I mean, there are times where So, I'm usually really just straightforward. I just I'm like, this is what you're doing. I try not to say please or thank you because again I just don't want you know at some point when we get to AGI they're going to be running the show and I just I'm I'm fighting until we get to that point. I'm holding on to my humanity. Um and then but I usually just I usually spend a lot of time saying we've gone over this already. You've talked about this. Go search your memory to go find the time where we've done this. And it is it's a lot of parenting. I have like you I have three boys and I rely on a lot of the things where I'm like we've talked about this remember and you know and your kids are like you you you know that they are they want to do the right thing and so it's just a lot of like helping them get there. There's something we say that that I learned from a former manager and that we say a lot at LinkedIn which is assume best intentions and that is how that's by the way a big change from how news rooms work which was my last life which was you assume worst intentions all the time. At at tech companies you assume best intentions. I've now taken that to my family and I've taken it also to building with AI. So I assume the AI has best intentions but has to be reminded about how we work. So I don't yell. I'm pretty clear and I try to give it a little bit of grace.

</details>

**Claire Vo**: 完美。好的**Dan**，这太棒了。我认为这对技术人员、非技术人员、忙碌者、更忙碌者来说都是一个很好的概述。非常感谢你与我们和我们的观众分享你的流程。我们可以在哪里找到你，我们如何提供帮助？

<details>
<summary>Original English</summary>

**Claire Vo**: Perfect. Well Dan, this was awesome. I think it's a great overview for technical, non-technical, busy, busier alike. So thank you for sharing your flows with us and our audience. Where can we find you and how can we be helpful?

</details>

**Dan Roth**: 所以我在**LinkedIn**上，不足为奇。找到我。你可以在**LinkedIn**上关注我。嗯，我是**LinkedIn**上的**Daniel Roth**。嗯，我有一个正在运行的**时事通讯**，叫“**Forward Deployed Editor**”，它跟踪我如何学习使用**AI**，它谈论——它主要是为非技术人员设计的，让他们能够构建很酷的东西。所以我尽量谈论我正在失败的地方。大部分是我正在失败的地方。嗯，我正在学习什么，什么不起作用，如何避免犯同样的错误。所以如果你能关注那个，那会很棒。否则，我总是在**LinkedIn**上不断发布内容。世界各地的创作者都在发布很棒的内容。所以，希望你们能在那里关注我。

<details>
<summary>Original English</summary>

**Dan Roth**: So I'm on LinkedIn, not surprisingly. Find me. You can follow me on LinkedIn. Uh it's Daniel Roth at LinkedIn. Uh and I've got I keep a running newsletter called Forward Deployed Editor which tracks how I'm learning how to AI and it talks it's really designed for people who are non-technical to be able to get to be able to build cool things. And so I try to talk about what I'm failing. It's mostly what I'm failing at. Uh what I'm learning, what didn't work, how to avoid making the same mistakes I've made. And so if you can follow that, that'd be great. Otherwise, I'm always constantly posting on LinkedIn. Great content that creators are posting around the world. So, hope you'll follow me there.

</details>

**Claire Vo**: 太棒了。谢谢你参加《How I AI》。

<details>
<summary>Original English</summary>

**Claire Vo**: Great. Well, thanks for joining How I AI.

</details>

**Dan Roth**: 谢谢邀请。

<details>
<summary>Original English</summary>

**Dan Roth**: Thanks for having me.

</details>

**Claire Vo**: 非常感谢您的收看。如果您喜欢本节目，请在**YouTube**上点赞并订阅，或者更好的是，给我们留言分享您的想法。您还可以在**Apple Podcasts**、**Spotify**或您最喜欢的播客应用上找到本播客。请考虑给我们评分和评论，这将帮助其他人发现本节目。您可以在**howiipod.com**查看我们所有的节目并了解更多信息。下次再见。

<details>
<summary>Original English</summary>

**Claire Vo**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. [music] Please consider leaving us a rating and review which will help others find the show. You [music] can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>