---
author: AI Engineer
date: '2026-07-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZpK5PWX2YRM
speaker: AI Engineer
tags:
  - developer-productivity
  - code-review
  - ai-agent
  - software-architecture
  - system-reliability
title: 2026年AI时代我们还需要读代码吗？解析Z/L象限与人机协同的评判标准
summary: 本文基于ThursdAI主持人Alex Volkov在AI Engineer Europe上的演讲，深入探讨了在AI自动生成代码量爆发的2026年，工程师是否仍需阅读代码的行业焦虑。文章通过分析OpenAI的Ryan LeFebvre（“代码免费论”）与Pi创造者Mario Zechner（“代码严审论”）的观点冲突，提出了基于任务特性的“Z/L连续体”决策框架，指出人类工程直觉和系统级架构评审在自动驾驶编码时代的不可替代性。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
  - GitHub
  - Weights & Biases
  - CoreWeave
  - Google
  - METR
  - Faros AI
products_models:
  - Claude
  - Codex
  - Grok
  - GPT-4
  - Mythos
  - Fable 5
media_books: []
status: evergreen
---
### 行业大辩论的起点

**亚历克斯·沃尔科夫 (Alex Volkov)**: 在欧洲 AI 工程师大会（AI Engineer Europe）上，有两场令人瞩目的演讲针锋相对。

一位演讲者宣称：“**代码现在是免费的**”，并且他甚至注销了自己的 GitHub 账号。

而另一位演讲者则警告大家：“**必须阅读你写下的该死的每一行代码**”。

那么，AI 工程师在今天，也就是 2026 年，是否仍然需要去阅读他们的 AI Agent 所生成的代码呢？

我将这个现象命名为“**阿波罗消亡连续体**”（The Desolation of Apollo Continuum），或者更简单地称之为 **Z/L 连续体**（Zechner-LeFebvre Continuum）。你们大概率已经在 Slack 频道里为这个问题争论得面红耳赤，或者在会场的走廊里热烈讨论过。

今天，我们就在这里开诚布公地探讨这个问题。因为虽然代码变得极其廉价，但我们的精力和注意力并没有随之贬值。

<details>
<summary>Original English</summary>

**Alex Volkov**: Two talks at the AI Engineer Europe. One guy is saying, "Code is free." and deleted his ID. And the other one is saying, "Read every effing line of code." So, should AI engineers still read code their agents output? I named this the Desolation of Apollo Continuum. And you guys probably have argued about this in Slack. You probably talked about this in the hallway track. So, let's talk about this here. Because code got cheap, attention didn't.

</details>

### 2025年之后的游戏规则突变

**亚历克斯·沃尔科夫 (Alex Volkov)**: 大家都知道，早在 2025 年 12 月，一些非常根本性的事情发生了。**AI 工程**的范式被彻底改变，并打破了其原本的发展趋势线。

事实上，AI 工程师大会的组织者 Swyx 正在一个名为 **wtfhappened2025.com** 的网站上收集这门技术在特定历史时刻发生剧变的证据。我强烈建议你们去浏览一下，真的非常有趣。

例如，来自**机器智能评估中心**（METR, Machine Evaluation Center）的一项数据显示，AI 模型首次开始能够独立完成原本需要人类工程师花费 16 个小时以上才能搞定的复杂任务。

而且事实上，在这之后我们沿着这条增长曲线一路狂飙，远远超出了原有的趋势线。这就是当前所有 AI 工程师所面临的生存背景：因为我们绝大多数人都不再亲手编写代码了，至少不再手写大部分代码。

我想做个现场调查。如果你们当中还有人坚持手写、人工打磨自己大部分代码的，可以举手示意我一下吗？有谁是大部分代码都靠手打的？

太不可思议了，毕竟这里是 Token Maxing（最大化生成效率）的主会场。我想那些依然坚持手写代码的人可能只是害羞，不太好意思举手。这很正常。因为我们已经不再是纯粹的“代码手艺人”了。我们的主要职责变成了监督——我更喜欢称之为“给 AI Agent 当保姆”。

<details>
<summary>Original English</summary>

**Alex Volkov**: As you may know, back in December 2025, something big changed. AI engineering has changed forever, and it broke its own trendline. Actually, Swyx, the organizer of AI Engineer, is collecting evidence to that single moment in time at the website called wtfhappened2025.com. I recommend you go and check it out. It's really, really funny. This is just one example from METR, the machine evaluation center. And it shows that models, for the first time, started completing tasks that would take engineers over 16 hours to do. And in fact, we've gone way up the curve, way up the trendline after that. This is the backdrop to everything that AI engineering is experiencing. Because we don't write code anymore. Most of us, at least. I want to see one—can you guys give me a raise of hands if you still handcraft and write code, most of your code? Anybody here? Most of your code is written by hand? Amazing. This is the Token Maxing track, after all. I think the one person here who still writes code is maybe a little shy of raising their hand. That's okay. Cuz we don't type code anymore. We're not handcrafters. We supervise. I like to say we babysit agents.

</details>

### 代言人与他们的极限实践

**亚历克斯·沃尔科夫 (Alex Volkov)**: 这种新模式最典型的例子显然是 **Boris Cherny** 的探索之路。你们应该都知道 Boris，他是 Anthropic 内部著名的 **Claude Code** 开发工具的创造者。目前，他所提交的全部代码中，100% 都是由 Claude Code 自动生成和编写的。

但是，这并没有让他失去作为一名工程师的价值，他只是把自己的工作升华到了更高的维度。他依然能保持每个季度交付 20 到 30 个甚至更多的 Pull Request（PR）。

最近，他还分享说自己注销了自己的 GitHub ID，这简直太幽默了，这意味着不再有任何手写代码的理由了。事实上，早在几个月前的数据就已经表明，**Anthropic** 内部 80% 的代码库都是由 AI 编写的，现在这个比例只会更高。

而且他绝非个例。你们很多人可能都看过 GitHub 发布的这张趋势图，或者在 GitHub 服务崩溃时无奈地想起了它。

导致 GitHub 经常不堪重负的原因是，GitHub 今年正朝着**年提交量达 140 亿次**的目标一路飙升。而在 2025 年之前，全年的总提交量仅仅是 10 亿次左右。这意味着提交量暴增了 14 倍，这简直是疯了，而这其中绝大多数都是在 AI 辅助下生成的代码。

因此，AI 工程的形态已经彻底改变了。我想和大家聊聊 AI 工程师的世界博览会。我参加了每一届，稍后我会细说。AI 工程师大会是一个能够精准捕捉我们职业未来走向和行业风向标的绝佳场所。

比如今年，大会的规模比去年整整扩大了三倍。这只是其中一个分会场，这里有很多类似的房间，登记参会的多达 7,000 人，共设置了 36 个技术专题。如果你想知道 AI 工程界正在发生什么，你必须身处现场。

让我们回到刚才的“形而上”探讨。在 AI 工程师欧洲大会上，一位嘉宾将代码视为可丢弃的耗材，而另一位嘉宾则强调我们必须逐行阅读代码。现在，让我们来重温一下他们当时的声音。

首先是来自 **OpenAI** 的 **Ryan LeFebvre**。

<details>
<summary>Original English</summary>

**Alex Volkov**: And the greatest example for this obviously is Boris's journey. You guys know Boris, the creator of Cloud Code, at Anthropic. 100% of his code is written and authored by Cloud Code at this point. And he didn't stop being engineer, he moved up the layer. He still ships 20 to 30 PRs, maybe more. And recently he talked about he deleted his ID. I found it really funny. Just no reason to just hand type code anymore. In fact, 80% of Anthropic's code is now AI written and this stat is at least a few months old. It's likely more right now. And he's not the only one. Some of you have seen this chart from GitHub. Some of you have maybe remembered this chart while GitHub was down for you. The reason is GitHub is on track to get 14 billion commits this year. All of 2025 was 1 billion. They're 14x the number of commits. They're seeing 14x the number of commits, which is insane and most of this is AI assisted. And it's a lot of code. And so the AI engineering has changed forever and I want to tell you about AI Engineer World's Fair. I been to every single one and I'll tell you about this later. And AI Engineer is a great place to get the zeitgeist of where our career is going and how is it changing, okay? This one obviously is 3x bigger than last year. This is just one of the rooms. There's like a bunch of rooms. 7,000 people I think we clocked in. 36 tracks. And if you want to know what happens in AI engineering, you kind of have to be here. So this would be a little bit of meta talk. So one of the guys at AI Engineer EU talked about code as ship. The other one talked about we should read every line of code. Let's listen to them for just a second, okay? This is Ryan LeFebvre from OpenAI.

</details>

### “代码免费论”与“代码严审论”的交锋

**莱恩·勒菲弗 (Ryan LeFebvre)**: 目前的模型能力已经强大到了一种几乎等效于人类的程度，它们完全有能力自主编写代码。

这些 AI 工具的质量非常高，能够在真实的生产代码库中解决用户的实际问题。**代码已经变得完全免费**了。

不管是生成代码、重构代码，它的成本都已经低到微不足道，这不再是一个值得人类工程师去纠结和死磕的环节了。

人类不需要再将自己局限于具体的底层实现细节。最核心的不再是代码本身，而是你输入给模型的 **Prompt（提示词）** 以及你为模型建立的 **Guardrails（安全护栏与逻辑边界）**。

你可以非常直接地对模型下达指令：“不要产生劣质代码（slop）。”只要你不接受劣质产出，你的代码库里就不会充斥着垃圾。但是，要做到这一点，需要我们在短期内牺牲一些速度，必须深入任务内部去仔细剖析和发现 AI Agent 目前在哪些方面遇到了瓶颈。

<details>
<summary>Original English</summary>

**Ryan LeFebvre**: The models at this point are good enough where they're isomorphic, they can write code. These tools are high quality that solve real user problems in real code bases. Code is free. It's free for you to produce, free to refactor, and it is not a thing to get hung up on anymore. Humans no longer need to concern themselves with implementation. The important thing is not the code, but the prompt and the guardrails that got you there. You can just simply say, "Do not produce slop." Don't accept slop. You won't get slop in your code base. But, to do that requires taking short-term velocity hits in order to back up or double-click into a task to figure out what it is the agents are struggling with.

</details>

**亚历克斯·沃尔科夫 (Alex Volkov)**: 这就是 Ryan LeFebvre，他在台上作了开场发言。他幽默地调侃说：“我是个能让大家发财的人，我也希望在座的各位都能如此。”

而与此同时，在同一个大会的另一侧，Pi 的创造者 **Mario Zechner** 给出了完全相反的警告。

<details>
<summary>Original English</summary>

**Alex Volkov**: So, this is Ryan LeFebvre, okay? He came up on stage at the engineer, and he opened with like, "Hey, I'm a talking billionaire, and I want you to be as well." In fact, the talking billionaire lounge that's in front of the leadership track that you guys see, that's because of him. He came up with this concept. And he got the golden card and everything. On the other side, the same conference, the other side, Mario Zechner, creator of Pi.

</details>

**马里奥·策希纳 (Mario Zechner)**: 大家都慢下来，别头脑发热了。现在所有的东西其实都是千疮百孔的。

现在总有人得意洋洋地说：“看啊，我们的产品 100% 都是由 AI Agent 亲手构建出来的。”

是的，我们大家都心知肚明，这样的产品目前体验极其糟糕。祝贺你们啊。

这些 AI Agent 实际上只是在不断地**堆砌和累积错误（booboos）**——这是我对那些低级失误的称呼。它们毫无学习能力，没有自我纠偏的瓶颈，只会让痛苦不断延后。

而这个**延迟到来的痛苦**，最终将由在座的各位人类工程师来全盘买单。

我很同情那些宣称自己“连一行代码都不再读”的同行，我只能对你们表示祝贺。一旦系统崩溃，用户开始疯狂投诉的时候，你打算指望谁来排查？你根本指望不上你自己，因为你压根连一行代码都没读过。

对于那些非核心的次要代码，好吧，你们爱怎么写垃圾就怎么写。但对于**核心的关键业务代码，你们必须逐行审查**。

<details>
<summary>Original English</summary>

**Mario Zechner**: Slow the down. Everything's broken. And then there's people that say, "Our product's been 100% built by agents." Yes, we know it sucks now. Congratulations. Agents are actually compounding booboos, which is my word for errors, with zero learning and no bottlenecks and delayed pain. The delayed pain is for you. Those are my most beloved people. I don't even read the code anymore. Congratulations. Something is broken, and your users are screaming, so who you going to call? Not yourself, because you haven't read the code. Non-critical code, sure, write slop ahead. Critical code, read every line.

</details>

### 数据揭示的残酷现状：交付暴增与系统不稳定性

**亚历克斯·沃尔科夫 (Alex Volkov)**: 两位行业大咖，在同一个大会上，在相邻的日程中，表达了我们所有人都在共同面对的深切焦虑：在 2026 年，我们是否依然需要阅读代码？

顺便提一句，这两位嘉宾的演讲视频是整个 AI 工程师频道有史以来播放量排在第六和第七位的热门视频。这显然表明他们切中了大家最敏感的神经。在这个关于技术管理的议题中，你手下的团队成员也必然在讨论这个话题。我们到底该不该读代码？我们的代码质量防线究竟在哪里？

从两端的视角来看，他们指向了同一种焦虑。

在继续分析之前，我希望大家对自己坦诚一些。即使你现在已经不怎么亲自写代码了，但如果你手下的工程师每天都在帮你们监督 AI Agent 的产出，那么在回答这个问题时，请代入他们的视角。

在 Z/L 连续体上，你究竟站在哪一端？

让我们现场举手投票表决一下：
有谁曾经把一段**自己完全没有看过的 AI 生成代码直接合并并提交到生产环境中**？

太棒了，非常感谢大家的诚实。
那么，又有谁依然坚持**阅读每一行代码**，或者至少是仔细阅读每一行核心业务逻辑代码？

我看到那边有一位“孤勇者”。我非常欣赏你的坚持，伙计。会议结束后我一定要找你聊聊，我想听听你是如何在每天海量的代码生成中坚持下来的。

那么，究竟谁才是对的？让我们用客观的数据来说话。

首先，支持 Ryan 这种乐观派的观点其实是有数据支撑的，至少在**产出效率**上是如此。

根据 **Faros AI** 在 2026 年 4 月发布的一项最新行业调查报告，这是我们目前能够引用的关于行业走向的最佳证据之一。他们对多达 22,000 名开发者进行了深度调研，并给这种现象起了一个很有表现力的名字——“**效率鞭梢效应**”（Acceleration Whiplash）。

在这份报告中，我个人最钟爱的一个数据是：**PR 中的代码删除率惊人地增长了 861%**。这表明，我们和 AI Agent 配合时，最喜欢干的事情其实是疯狂地重构和删除废弃代码。

同时，Anthropic 官方也表示，他们目前每个季度交付的代码量是 2025 年的 8 倍之多。

然而，这些被海量合并的代码，真的都是高质量的优秀代码吗？

<details>
<summary>Original English</summary>

**Alex Volkov**: So, two folks, same conference, day after day, talking about the one anxiety that we all feel. Should we all still be reading code in 2026? By the way, these two folks are the number six and number seven most watched YouTube videos from AI engineer from all time. So, they're obviously representing something that we're feeling we're talking about. And this is being the leadership track, something that you folks that report to you are talking about, okay? Should they still be reading code? And what's the level quality? So, they name the same anxiety from both ends. Uh at this point, I probably should introduce Uh hey, I'm Alex Volkov. I'm the host of Thursday AI podcast. It's a podcast and a newsletter. We go live every week to talk about AI. For the past 3 and 1/2 years, we've been tracking every change in the AI engineering, every release from every lab, every model. And I'm also an AI evangelist with Weights & Biases and Core Weave. Um what also should I tell you about myself? That I've been covering AI engineers specifically since the first one in 2023. And oh boy, has it changed. And so, you can treat this as a dispatch from the front line because all of these people now are my friends. And we constantly talk about this in the speakers' room in the hallway track. I couldn't stop thinking about that tension. I couldn't stop thinking about that kind of disparity between the two folks, okay? And I put them both on a line, Zeshner from one end, Lapopolo on the other end. I called it a continuum. And I basically started asking people, "Hey, where are you on this line? Where are you a Zeshner? Do you still read every line of code? Are you a Lapopolo? Do you just YOLO and don't even look at code and think agents are good enough, etc.?" And I got the framing wrong. But, I'll tell you about this in just a second, okay? So, before this, I want you to be kind of honest with yourself. And again, if you don't write code, or let me say this, if you don't babysit your own agents, but you have reports that babysit agents for you, uh think about them when you answer this, okay? And be honest. On the ZL continuum, where are you? And let's take um let's take by vote of hands, who here has committed code that they've never looked at before? Amazing, love that. Who here still reads every line of code or at least critical code? I see one cowboy over there. I love that, man. I'm going to talk to you afterwards, okay? I want to understand exactly why you do this. Um, and so who's right? Let's talk about who's right. Let's talk about where we are right now, and we start with Ryan Lepopolo. If you get to meet Ryan over here, he's very AGI built. I think even within OpenAI, the AGI organization, Ryan is kind of like the more AGI built person. If you have a chance to go downstairs and grab the AGI pills that 2X prescribed, I think Ryan had all of them. He works at OpenAI, where he sits code is literally free. So are tokens. It's really We renamed Ryan, do you guys know the dash dash YOLO in Codex? It's kind of like the skip dangerous permissions in cloud code. So we renamed the Ryan Lepopolo YOLO Popolo. He's okay with it, by the way, I asked him. So if we check his kind of side, the folks like him against the data, they're actually right. The optimists are right, at least about output. This is from Faros AI, I think I'm not the only speaker at this conference who sites this essay. It's sorry, this survey. It's new from April 2026. I think it's one of the best kind of evidence of where we're going that we can now site, okay? 22,000 engineers were surveyed about code. They call this the acceleration whiplash. And they're talking about my favorite stat on here, and you can read this yourself, 861% increase in code deletion per PR. So us together with AI agents, we love deleting code. Anthropic also said that they're shipping eight times more code per quarter than in 2025. But is it all good code?

</details>

**亚历克斯·沃尔科夫 (Alex Volkov)**: 让我们来做个猜谜游戏。

如果你们知道答案，请留给我在台上的高光时刻。如果不知道，我们一起来猜猜：

**这是哪家公司的服务状态监控页面？**

我听到台下有一些零星的回答，看来大多数人都猜对了。没错，这就是 **Claude** 的监控页面。

非常滑稽的是，在我截这张图的时候，他们的服务刚好又处于宕机状态。作为目前在代码库中被 AI 自动生成代码比例最高的公司，Anthropic 的系统健康监控状态页看起来却像一棵**五颜六色的圣诞树**，频繁出现各种警报。

当然，我今天并不是专门来嘲讽 Anthropic 的。他们在台上展现了极其出色的技术，Claude 的功能是毋庸置疑的。

这种高频的故障也许是由于用户规模呈指数级增长导致的，也许还有其他复杂的技术因素。我不是为了指责他们，但这个现状说明了，**单纯的高产出并不等同于系统的稳定性**。

同时，GitHub 也频繁面临类似的服务抖动问题。

在这份 Faros AI 的报告中，还有一个数据非常值得警惕：**在没有任何人类或 AI 审查的情况下，直接合并的 PR 数量增加了 31%**。

我真心请求大家：千万不要在实际生产中这么干。这非常危险。

当你的交付速度如此之快、交付数量如此之大时，总会有所牺牲，而这牺牲的往往就是软件的质量。

所以，也许 Mario 的保守观点才是对的。在生产环境中，我们最终是要为这些隐藏的质量债买单的。

同样的调研指出：**平均每个 PR 引入的线上事故（incident）率飙升了 242%**。这是一个极其惊人的数字。

而另一份行业调研同样令人担忧：平均每个开发者引入的 **Bug 数量是 2025 年的整整 6 倍**。

<details>
<summary>Original English</summary>

**Alex Volkov**: Okay, let's play a game. If you know the answer, you let me have my moment on here on stage, okay? But if you don't know the answer, let's guess. Whose status page is this? I think I hear a few answers. I think most of us guessed it. This is Claude. Uh in fact, as you can see on the on the right, it was down when I took the screenshot. It was really funny. Uh this Anthropic is the company that probably uses the most AI-generated code, and their status page looks like a Christmas tree. Now, I'm not here to dunk on Anthropic. Uh they did an incredible job back on stage uh talking about Claude and etc. Um this may be due to scale, this may be due to other factors. Uh I'm not here to dunk on them, but [snorts] it just goes to show that they're not the only ones like this. Obviously, GitHub is famously also suffers from a little bit of golf. Output does not mean stability, okay? So, maybe this is a good example of what? Same essay, 31% increase in PRs merged with no review at all, human or agentic. Don't do this. I beg of you. Don't It's it's We'll talk about how to fix this in a second. So, when you ship this fast and this much, something gives, and usually it's quality. So, maybe Mario's right, yeah? Maybe the bill does come due in production. Same study, 242% increase in incident per PR. This kind of scary. The second study is also scary. Bugs per developer is up six times than 2025.

</details>

### Amdahl定律在人类审查上的失效与“Z/L连续体”的重构

**亚历克斯·沃尔科夫 (Alex Volkov)**: 甚至连 Anthropic 官方对此也心知肚明。

不知道大家是否读过他们之前发表的一篇关于**递归自我提升**（RSI, Recursive Self-Improvement）的深度论文。在这篇论文中，他们描绘了未来可能出现的两种主要场景。

第一种场景是：AI 技术的迭代速度开始放缓，行业逐渐适应现有的生产力水平。但他们明确指出，这种情况发生的概率极低，之所以写在纸上仅仅是为了逻辑的严密性。

他们认为更有可能发生的是：工程师和科技企业将面临**产出和生产力 10 倍、100 倍甚至 1000 倍的爆发式增长**。

紧接着，他们指出了一个关键的痛点：“随着我们在组织内部疯狂推行更多的自动化代码编写，**人类代码审查（Human Code Review）已经成为了全新的系统瓶颈。**”

这正是 **Amdahl 定律**（阿姆达尔定律）在软件工程中的具象化体现：当你大幅度优化了代码生成的效率时，系统整体的吞吐量将会被卡在那个最无法被优化的环节上——也就是人类的精力和注意力。

而且在目前这些顶尖的科技巨头中，并没有人打算把“人类”从这个闭环中完全剥离。无论是 Anthropic 还是 OpenAI，他们依然在大量招聘优秀的人类工程师。这意味着，人机协同和代码审查依然是全行业不可动摇的核心关切。

在这里，我必须做一次自我纠偏（mea culpa）。我之前在划分这个连续体的时候，逻辑上出现了一个偏差。

**Z/L 连续体是真实存在的，但它的划分依据不应该是不同的“人”，而应该是不同的“任务（Tasks）”。**

<details>
<summary>Original English</summary>

**Alex Volkov**: So, even Anthropic can see this. I don't know if you guys read the RSI essay they posted, the recursive self-improvement, where they talk about, "Hey, what does the future hold?" They outline two scenarios. One of them says, "Maybe the acceleration will stop, and we're going to get used to this." They all They say, "That's actually not likely to happen. We just added this uh eventuality for clarity. We don't think that's likely to happen. What we think is going to happen is uh engineers and companies 10Xing to 100x-ing to 1,000x-ing their output and productivity, and then they say this, "We, as we began to push more code around the organization, human code review has become a new bottleneck." They're citing Amdahl's law that shows that if you have an explosion of productivity in one area, another area going to going to get blocked. And nobody removes the human in these organizations. In fact, careers in Anthropic and careers in OpenAI, they're still hiring humans. So, nobody's removing the human, and they're both saying that human code review is still a concern. And here's my mea culpa. I promise you I'll tell you where I got it wrong the framing. My mea culpa is the continuum is real. The Zeal continuum is real, but it's not about the people. It's about the tasks. The continuum is real. It's not about the people. It's about the task.

</details>

### 面向任务属性的代码分流决策表

**亚历克斯·沃尔科夫 (Alex Volkov)**: 同一名优秀的工程师，在面对某些代码片段时，应该扮演 Ryan 这样敢于放手的决策者；而面对另一些关键的核心逻辑时，则必须化身为 Mario，化作人肉防线逐行死磕代码。

**不同的任务属性，决定了它们需要何种程度的置信度论证。**

如果我们仔细审视 Ryan 和 Mario 的核心论点，就会发现他们之间的分歧其实并没有想象中那么大。

Ryan 的逻辑是：我们要把人类的宝贵精力提升到更高的系统设计层面上。他指出，人类在试图捕获相同类型的重复性低级错误时，其表现是非常不可靠的。

因此，当你通过 PR 审查捕获到某种类型的 Bug 时，你不应该仅仅修复它，而是应该立刻编写文档、配置静态扫描工具（Linter），让系统的自动拦截机制记住这个教训。这样，未来的同类 Bug 就会被自动化体系拦截，而无需人类反复用肉眼去识别。

他并不是在宣称我们可以完全对代码放任不管，他是在强调**我们应当审查机制和系统本身，而不是疲于奔命地审查每一行具体的代码**。

而 Mario 的逻辑则是：**根据任务的物理属性来进行分流。**

如果是非核心业务、即使挂掉也不会造成重大损失的代码，那就让它自由合并。而一旦涉及到核心链路，人类工程师就必须死守防线，逐行阅读。

但是你该如何判断哪些是核心逻辑？Mario 给出的答案非常简单粗暴：阅读你那该死的代码。

而我的补充建议则是：**去询问你的“代码扫描模型（clankers）”**。这些底层的 LLM 扫描工具非常擅长在超大型的工程仓库中为你进行静态依赖分析，并精确地警告你：“注意，这段代码涉及到核心原语，是系统中最脆弱的枢纽，你必须重点审查这个区域。”

这表明，他们两个人的核心理念，在本质上是高度互补的。

因此，我们不应该去追问“在 2026 年我们还要不要读代码”。

我们真正应该追问的是：**“这一次具体的代码变更，究竟需要何种级别和维度的质量论证（Proof）？”**

为了帮助大家更好地落地这个理念，我将许多行业内一线 AI 工程师朋友的真知灼见，浓缩成了一张面向任务的**路由决策表（Routing Table）**。Swyx 之前在 Twitter 上对我说，我应该给出一张能够直接让大家截图保存的 PPT 页面，那就是下面这一张：

| 任务敏感度 / 业务场景 | 论证机制与防线 (Proof Needed) | 审查策略建议 |
| :--- | :--- | :--- |
| **高敏感 / 核心链路**<br>· 身份鉴权与核心安全机制<br>· 资金流转与计费系统<br>· 核心数据库Schema及不可逆操作 | **人类专家逐行严审 (Mario 模式)**<br>· 必须 100% 掌握每一行底层实现<br>· 人类工程直觉是最终安全边界 | **极致的确定性优先**<br>· 禁止 AI 自动合并<br>· 辅以静态编译校验与形式化验证 |
| **中等敏感 / 业务主逻辑**<br>· 界面交互与核心业务流变更<br>· 数据统计与分析上报 | **系统级防护与自动化测试 (Ryan 模式)**<br>· 编写针对性的集成测试与单元测试<br>· 确保边缘 Case 覆盖 | **效率与质量的平衡**<br>· 依靠 Linter 和 CI 自动拦截常规错误<br>· 人类仅做架构与关键边界审查 |
| **低敏感 / 辅助工具与展示**<br>· 内部监控后台仪表盘<br>· 静态文案与小工具脚本 | **完全托管与影子模式测试 (YOLO 模式)**<br>· 线上影子模式运行捕获异常<br>· 自动生成测试覆盖 | **效率第一，小步快跑**<br>· 允许 AI 自动合并与快速回滚 |

<details>
<summary>Original English</summary>

**Alex Volkov**: Same engineer could be a Ryan LeCompte on Apollo on one piece of code, and has to be Mario Zechner and read every line of other pieces of code. Different task just need different proof. If we look at them closely, I obviously character—characterized them. I practiced this word multiple times and I still got it wrong. Characterized them. Their character on both ends for the Zeal continuum. But, if you look at them closely and what they're saying closely, they're actually not that different. Ryan's mechanism is moving attention up the layer. He's saying humans are unreliable at catching repeated mistakes of the same type. Repeatedly catching the mistakes of the same type. So, when they you do catch a mistake during the PR review, write the documentation, the linter, and the reviewer needs to remember this once, so the system will catch this type of bugs. He's not saying don't inspect your code. He's saying inspect the system, not every line. Mario from the other end is saying route by task. If it's not critical, let it rip. He said it. And if it's critical, you read every line. How do you know what's critical? Well, his answer is easy. You read the effing code. Uh my answer to add to this is also you ask your clankers. They're great at looking at a large repository and saying you and telling you, "Hey, this line is actually critical. You should look at this area. This primitives over here are critical." So, you ask your clanker. So, they agree more than I can have given credit for. And so, I think at the beginning of this, the wrong question is should I still be reading code in 2026? I think the better question right now for all of us is what proof does this specific change need? What proof does this specific change need? And so, I took Mario on the left, obviously. I took Ryan on the right. And then I took a bunch of other uh great AI engineers, friends, some friends, uh many of them speakers at this conference. I kind of distilled their advice down to a routing table. And uh they told me, I think Swyx told me on Twitter, "Just give me one slide that I will that people need to take a screenshot of. It's going to be this slide. You don't have to read it with me, but in the end, you're welcome to take a picture of this." This is the your Monday artifact. Routing the change where the proof needs it. Routing the change to the proof that it needs. You read every line of authentication, money movement, permissions, and irreversible data. You inspect the critical path yourself, and then obviously, you keep going.

</details>

### 解耦、可观测性与来自卡帕西的行业警示

**亚历克斯·沃尔科夫 (Alex Volkov)**: 在具体的研发实践中，**对代码变更进行原子级别的拆分和解耦**变得比以往任何时候都更加关键。

随着 AI 自动生成的代码量迎来海啸般的增长，人类审查者的视觉极其容易在那些动辄上千行、密密麻麻的巨大 PR 中产生审美疲劳，漏掉关键缺陷。

因此，你必须将复杂的大型变动拆解为原子化的、易于审查的超小 PR。在这方面，AI Agent 其实是天然的好帮手，你可以直接指示它们去进行代码的解耦与拆分。

另外，那些在传统软件工程中起支柱作用的体系在 AI 工程时代不仅没有被削弱，反而变得更加核心：**调用链路追踪（Traces）、实时评估体系（Evals）以及线上“影子模式”（Shadow Mode）运行**。

由于演讲时间有限，我无法在这里展开长篇大论，但影子模式绝对是一个非常迷人且实用的架构设计，这是我在准备这次演讲时感触最深的一个收获。

最后，千万不要让编写代码的同一个 AI Agent 去充当测试和代码质量的审查者。

**测试与生成的角色必须彻底分离。**

如果让同一个智能体既当运动员又当裁判员，就像我自己出一份考卷，自己作答，最后自己给自己打满分一样，这在软件工程安全上没有任何实际意义，也是极其低效的。

正如 Ryan 所推崇的那样：我们要构建一个能够源源不断产生高质量代码的“系统级系统”。用你的精力去优化规则，让系统具备持久的记忆力和拦截能力。

那么，面对未来的新纪元，当前的这些方法论依然有效吗？

毕竟，我提出 Z/L 连续体概念仅仅过去了 82 天，而 Anthropic 就已经正式发布了备受瞩目的 **Mythos** 与 **Fable 5** 模型。

在如此恐怖的技术迭代速度下，当模型具备了全新的推理与规划能力，这一切还会是当下的格局吗？

在 Anthropic 工作的 **Jared S. Chipar** 在大会上分享了他们使用新模型的感受，他的话让我印象极为深刻：

“在过去，我们使用工具是为了检查 **Claude 是否在正确地完成工作（doing the work right）**；而在配备了全新的 Fable 5 推理能力之后，我们的主要工作变成了检查 **Claude 是否在做正确的工作（doing the right work）**。”

这段话让我的后颈直发凉。它向我们昭示了下一代模型在系统理解和业务对齐层面的恐怖潜力。

我们非常敬仰的行业先驱 **Andrej Karpathy** 最近加入 Anthropic 后，也在 Twitter 上直言不讳地表达了相同的观点：

“**现在不去看任何底层代码的诱惑力已经达到了前所未有的高度。但在实际生产环境中，请千万不要这么做。**”

卡帕西用这句极度凝练的话，完美概括了我们当前的集体焦虑。

这就像我们经常开玩笑说：“这个本可以开一小时的会，其实发封邮件就能解决。”那么，我今天一整场演讲的核心主旨，其实也可以缩写为卡帕西的这一句话。

技术能力的进化和漂移，只会不断改变我们需要去进行质量论证的层级和锚点，但它**永远无法消灭对于“质量论证”和“最终直觉裁判”的绝对刚需**。

<details>
<summary>Original English</summary>

**Alex Volkov**: Uh decomposing, I think is very important. The more code is getting written, the more it's hard. Your eyes are starting to glaze over a a very long pull request. So, split it into atomic reviewable PRs. You know who's good at it? Agents. They're great at decomposing code. Ask them to do it. You verify that doesn't go away. This has been with us in the in engineering software engineering and the AI engineering doesn't go away. Traces, evals, shadow mode. Come talk to me after after this talk. I don't have enough time, but shadow mode is a really cool one that I learned about preparing this talk. And then, I think the most important one is separating. Many people have the same agent that writes the code, also inspects the outputs and writes the tests. Separating is very important. If you don't separate, it's kind of like if I came up with an exam and then I took an exam and I scored myself on the exam. It's not not really productive, right? And then last one is engineer. Rails observability rollback. This is what Ryan Le Popo talks about. Build the system that builds the system because read spends your attention once, engineer makes the system remember. Right? And you might sit in might be sitting there and saying, "Hey, did you hear the news, Alex? Fable is back. What about Fable? What about Mythos? Is this still relevant at this next scale of capability?" Because when I coined the Zeal Continuum, it was only 82 days ago. Mythos has just been announced. We weren't sure like what was going on. Only the people in Anthropic got access to it. And Jared S. Chipar, that was on stage from Anthropic, he said about Mythos and and and Fable, "We used to check if Claude is doing the work right? And with Fable 5, I instead check if Claude is doing the right work." Let it land for a second. I don't know if you read the statement. When I read the statement, I felt like little chills at the back of my neck about the next like level of capability, okay? We used to check if Claude is doing the work right. With Fable, we check if Claude is doing the right work. And our favorite senpai who recently joined Anthropic and is getting unnecessary heat on Twitter said this. Andrej Karpathy has said, "It's never felt so tempting to stop looking at code at all. But don't do this in production." Senpai is great for the sole reason. Do you guys know the sentence, "This meeting could have been an email?" So, this presentation could have been Andrej Karpathy's one sentence, okay? He's naming the anxiety from both ends. It's never been so tempting to stop looking at code. Don't do this in production, even with Fable. And so, if you guys noticed, I have a little thing here. This. Uh it's so wide you can see my little laser pointer. Do you guys see the arrow, the capability drift arrow? This thing? When I wrote the continuum, I realized that it it's only a temporary place in time. Capability increases move us towards the popular. So, we're going to talk about capability increases as well because the review layer moves. If yesterday we inspected the outputs and we read the code, and today we inspect the task direction and kind of like directed to the right proof, maybe tomorrow we're inspecting the loops. Capability drift changes where proof belongs. It doesn't remove the requirement of proof.

</details>

### Agent自动化循环的隐忧与未来展望

**亚历克斯·沃尔科夫 (Alex Volkov)**: 既然谈到了自动化循环（Loops），这会是下一个工程原语吗？

在这个会场上，在当前的行业风向中，大家都在谈论 **AI 工厂**（factories）和人机协同工厂（co-factories）的落地。而循环运行的 Agent（Loops）确实正在成为一种全新的研发常态。

现场可以再举手示意一下吗：有谁听说过 Loops 这个概念？

请大家保持举手。如果你还没有在实际的研发工作流中部署和运行这种循环 Agent，请把手放下。

可以看到，场下依然有相当一部分同仁依然举着手。

这也印证了 Peter Steinberger（Open Claw 创造者）以及 Boris Cherny 最近的分享。在短短几天的时间里，他们不约而同地把讨论的焦点引向了 Loops，这正在演变成行业的新共识。

自动化循环正在引导我们告别以往一问一答的交互式 Prompts 编写，转去**设计一个能够自动生成 Prompts 的自动化架构系统**。

顺便提一句，这些行业大佬和我们最大的区别是什么？那就是他们的 Token 额度几乎是完全免费且无限使用的。

所以，当他们向你描绘这些复杂的自循环架构时，他们可能不会太在意底层的 Token 消耗成本。但是，我们依然可以把这些头部实验室的研究视为航标灯塔，从中窥见整个软件开发行业的未来演进路线。就像冰球大帝格雷茨基那句经典的名言：“**滑向冰球将要到达的位置，而不是它现在的位置。**”

如果非要给自动化循环（Loops）做一个高度概括的总结：

它们本质上是一系列**在后台按特定调度策略运行的高级定时任务（Fancy Cron Jobs）**。

但不同的是，它们能够自主发现待办任务，基于整体规划自动编写子提示词并予以执行。而最关键的一点在于，**它们具备自查验证机制，一旦运行失败，能够自我迭代并重新尝试。**

这意味着，一个具备循环迭代能力的 Agent 能够以极少的人类干预度，根据既定的终极目标，不断对自己的产出质量进行自我评测和修正。

然而，正如我们前面所警告过的：**如果构建者自己充当考官来给自己打分，你并没有真正消除代码审查这一关卡，你仅仅是将它掩盖和隐藏了起来。**

这完美地印证了我们前面路由决策表的逻辑。

来自 **Google** 的杰出工程师 **Adi Olasman** 最近在大会上也坦言道：

“如果我们完全放弃人工审查，百分之百依赖 AI 内部的自我修正循环去解决所有的代码缺陷，那么当 Jira 上分配过来一个线上 Bug 并且自动化循环试图去修复它时，我们的软件质量将遭遇无法挽回的滑坡。

我们极其容易陷入一种不断自我退化的泥潭，非但没有修复问题，反而把系统漏洞撕扯得越来越大。”

因此，**自动化循环系统并没有免除人类判断（Judgment）的必要性，反而由于其惊人的产出效率，极大地抬高了人类工程直觉的决策门槛。**

<details>
<summary>Original English</summary>

**Alex Volkov**: Talking about loops. Is that the next primitive? I think most of this conference, I think the zeitgeist for this one is going to be is talking factories and co-factories are real, and is loops is a real thing that I need to be doing at this point. By raising of hands, who here heard of loops? Keep your hands up, please, and take them down if you are not running loops right now and you haven't anything about they are. There's a good perception There's good number of people here who heard about loops, and they started with both these folks, Peter Steinberger, creator of Open Cloud Open Claw, and now is Open AI, and Boris Cherny. And pretty much within the span of 2 days, both of them start talking about loops that became kind of the zeitgeist. And loops are moving us from prompting each turn to designing the system that writes the actual prompts. By the way, do you guys know what's common between these guys and what's different between me and these guys? Their tokens are free. So, when they talk about loops and their tokens are free, they're not telling you, "Hey, you should be doing this right now specifically." But because they work at bigger labs, you can can treat them as kind of a lighthouse that's pointing where we're all going. Kind of like Gretzky skate where the puck is going to to They're going to tell us what all of our enterprises are going to get get up on. And if it's if it's loops, then let me at least give you a TLDR, okay? Loops are basically fancy cron jobs that run on a schedule. But what they do is they discover a task and kind of start writing a prompt for this task from the plan. They write the plan, they execute, and most importantly for my talk here, they verify themselves, and if it doesn't work, they try again. So, an agent that loops grades its own work against the goal with less human intervention. But if the builder grades itself, you didn't remove the review, you hid it. Okay, this this connects to my routing table. This comes from Adi Olsmanyu recently at Google. He's also at this conference, a great engineer. Uh he said if I if I if I wasn't reviewing the code myself, or relied entirely on automated loops to fix my code, let's say a bug comes up in Jira and my loop picks it up and starts fixing this, my product quality would suffer. I'd likely end up in a downward spiral, digging myself into a deeper hole. So again, loops don't remove judgment, but they do raise the stakes on where you put it.

</details>

### 总结与工程师的未来身位

**亚历克斯·沃尔科夫 (Alex Volkov)**: 展望未来的软件工程图景，没有人能给出百分之百确定的答案。

即使是 Anthropic 官方，在此之前也没能预料到 Claude Code 的热度会以如此恐怖的速度彻底爆发，并迅速演变成一个产值数十亿美元的庞大产品线。

几年前，也没有人能断言基于泛化智能体的代码编排和工程保障框架会成为今天全行业争相竞逐的核心高地。

从 OpenAI 的 Codex，到搭载 Grok 的 xAI 体系，再到 Google 备受瞩目的 **Antigravity SDK** 生态，底层模型的推理与工程能力正在以令人屏息的速度狂飙突进。

而我唯一能给在座各位工程师的至理名言就是：**保持极高强度的灵活性与架构敏锐度**。

你需要时刻跟紧底层技术趋势的漂移，这正是我们依然将自己定义为“软件工程师”的最核心价值所在。

如果大家希望继续跟进这一条不断演进的人机防线究竟在向何处漂移，欢迎扫描屏幕上的二维码，加入我们的 ThursdAI 社区与邮件订阅列表。

最后，我想以这句话作为今天演讲的收尾：

在 2026 年的今天，**并不是每一行机器生成的代码，都需要你花费眼力去肉眼审查。**

但整个软件系统的最终命运与设计走向，**依然时时刻刻需要你贡献那无可替代的人类直觉与工程评判。**

谢谢大家！

<details>
<summary>Original English</summary>

**Alex Volkov**: So what about the future, folks? Nobody knows. Anthropic did not know that Claude code is going to explode on them and this is going to be a billion-dollar product. Uh nobody knew that coding agents and Harness are going to be the generalized agent, and now everybody's pursuing them. Folks at OpenAI with Codex, Elon with with Grok code, uh Google with with anti-gravity. Model capability is jumping at an insane pace, and what I implore and to tell you here is that flexibility is required. You need to keep being able to keep up with with the trends. This is why you stay engineer. And by the way, I told some folks here about my podcast Thursday and news. If you want to keep tracking where that line moves, feel free to scan this QR code, join our uh our, you know, newsletter, etc. Um and I'll leave you with this. Because it's my time, I'll leave you with this. Not every line in 2026 needs your eyes. Every system still needs your judgment. Thank you.

</details>