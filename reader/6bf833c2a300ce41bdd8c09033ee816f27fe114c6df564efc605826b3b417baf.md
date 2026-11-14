---
author: How I AI
date: '2026-07-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=dAQsmhAiews
speaker: How I AI
tags:
  - prompt-engineering
  - local-ai
  - software-factory
  - ambient-ai
title: 本地智能革命：构建属于你自己的 24/7 硬件级软件工厂
summary: 硬件专家 Alex Finn 深度分享如何利用 Mac Studio、DGX Spark 及 RTX 5090 等设备组装强大的本地算力系统。通过 OpenClaw、Hermes 和 Tailscale 的协同，他成功搭建了可全天候自主运行、安全扫描和自动审查代码的环境 AI 与 sovereign 软件工厂，完美解决云端 API 成本过高的问题。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Atlassian
  - Canva
products_models:
  - Mac Studio
  - DGX Spark
  - RTX 5090
  - OpenClaw
  - Hermes
  - Claude Code
  - Qwen 3.6
  - Ornith
media_books: []
status: evergreen
---
### 硬件狂热与本地模型

**Claire Val**: 你现在**办公室**里堆了些什么硬件？

<details>
<summary>Original English</summary>

**Claire Val**: What is stacked around your office right now?

</details>

**Alex Finn**: 我有三台 **Mac Studio 512 GB**。我们还有一台 **DGX Spark** 以及一台电脑。我刚组装了一台搭载 **RTX 5090** 的电脑。基本上，在一天中的任何时候，这些电脑都在疯狂地消耗 Token。我听到的最大反对意见是：“你的电脑太贵了。云端模型不是很便宜吗？订阅 **ChatGPT** 不是只要 20 美元吗？”嗯，这根本不是重点。重点不在于纯粹的投资回报率（ROI）。重点在于它所解锁的使用场景。因为在本地运行 AI 模型，你现在拥有了 24/7 全天候运行无限智能的能力。如果你用 **Claude** 这样的云端模型来做这件事，你将会花掉一笔天文数字。

<details>
<summary>Original English</summary>

**Alex Finn**: I have three Mac Studio 512 GB. We got a DGX Spark as well as a computer. I just built an RTX 5090. Basically, at all times of the day, each one of these computers is just burning tokens. The number one push back I get on all this is, "Your computers are so expensive. Isn't cloud models cheap? Isn't it $20 for a Chad GBT subscription?" Well, that's not the point. The point isn't pure ROI. The point is the use cases it unlocks. You now have because you have AI models running locally, the ability to run unlimited intelligence around the clock 24/7. If you were to do that with a cloud model like Chad GBT or Claude, you would be spending outrageous amounts of money.

</details>

**Claire Val**: 你用 AI 还做了什么有趣的事情？

<details>
<summary>Original English</summary>

**Claire Val**: What else fun are you doing with AI?

</details>

**Alex Finn**: 最近我玩得最开心的就是构建我的**软件工厂**。我在 **Claude Code** 里运行着两个循环：一个构建循环和一个审查循环。首先，在构建循环中，它会接收所有这些任务，并开始一遍又一遍地构建它所带的任务。然后它有一个审查循环，接收所有已构建的任务，并让另一个 Agent 进去进行审查。一旦审查完毕，它就会在 Slack 上向我发送通知，我只需要回复一个火箭表情符号，当我有这个火箭表情符号时，它就会显示已合并，然后我的 Henry 循环就会进去把它合并。解决“如何构建自己的软件工厂”这个难题真的是太棒了。

<details>
<summary>Original English</summary>

**Alex Finn**: The most fun I've been having lately is building out my software factory. I have two loops in cloud code going. I have a build loop and a review loop. First, it has a build loop where it'll take all those tasks and start building out the tasks it came with over and over and over again. And then it has a review loop that takes all the tasks that were built and has another agent go in and review it. Once that's reviewed, it pings me on Slack and I can just leave a rocket emoji and when I leave the rocket emoji, it says merged and my Henry loop goes in and merges it. It's been a blast kind of cracking this nut of how do you build your own software factory.

</details>

**Claire Val**: 欢迎回到《How I AI》。我是 **Claire Val**，一名产品负责人，也是 AI 狂热爱好者。我的使命是帮助大家利用这些新工具更好地进行构建。今天我邀请到了 **Alex Finn**，他将带我们参观他的两台 Mac Studio、DGX Spark，以及他为自己组装的 Nvidia 架构电脑，并为我们揭秘运行本地模型以及让环境 AI（Ambient AI）一天 24 小时为你工作的真正含义。

[音乐]

让我们开始吧。本期节目由 **Runway** 赞助播出。Runway 是一种新型的创意平台，它拥有你在一处生成任何图像、视频或内容所需的一切。使用 Runway，现在可以在几分钟内完成从初始创意到最终交付物过程。从将低保真度的产品图转化为可用于宣传的影像，到制作大型品牌影片，Runway 都可以帮助你的团队扩展创意雄心，同时确保你的预算和时间线不会随之膨胀。Runway 汇集了世界上最先进的 AI 模型，这就是为什么像微软、Robin Hood、亚马逊和 Adobe 这样的企业，以及 Lionsgate 和 Legendary 这样的工作室都在每天使用 Runway 来发布实际工作。你可以在 runwayml.com/howi 上亲自尝试。促销代码 how I AI。

Alex，欢迎来到《How I AI》硬件版、本地模型版。我太兴奋了。所以，在我们开始之前，先告诉我们，你的办公室里目前堆了些什么。

<details>
<summary>Original English</summary>

**Claire Val**: Welcome back to how I AI. I'm Claire Val, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Alex Finn and he's going to walk us through his two Mac Studios, DJX Spark and the Nvidia backed computer he built for himself and demystify what it means to run local models and have ambient AI working for you 24 hours a day. [music] Let's get to it. This episode is brought to you by Runway, a new kind of creative platform that has everything [music] you need to generate any image, video, or piece of content you want, all in one place. With Runway, it's now possible to go from initial idea to a finished deliverable in a matter of minutes. From turning lowfidelity product shots into campaign ready imagery all the way through putting together big brand films, Runway can help your team scale your creative ambitions while keeping your budgets and timelines from doing the same. Runray brings together the world's most advanced AI models, which is why enterprises like Microsoft, Robin Hood, Amazon, and Adobe along with studios like Lionsgate, and Legendary all use Runway to ship real work every day. Try it yourself at runwayml.com/howi. Promo code how I AI. Alex, welcome to How I AI hardware edition, local model edition. I am so excited. So, before you jump in, tell us just what is stacked around your office right now.

</details>

### 唤醒时刻：从 Mac Mini 到本地算力

**Alex Finn**: 说实话，我现在这间办公室里感觉就像个桑拿房，因为我有太多机器在运行了。呃，我有三台 Mac Studio 512 GB，这在现在看来，拥有这些机器显然让我迈入了埃隆·马斯克（Elon Musk）的富人阶层。我想它们每台转手能卖大约 30,000 美元。嗯，我们还有一台 DGX Spark 电脑。另外，我刚刚在两天前组装了一台主要围绕 RTX 5090 构建的大电脑。所以我想我们有五到六台不同的电脑用于 AI。是的，这周围有非常多的硬件。

<details>
<summary>Original English</summary>

**Alex Finn**: It uh it feels like a sauna in this office right now to be quite honest with you because I I got a lot going. Uh I have three Mac Studio 512 gigabytes which apparently puts me uh in the in the wealth class of Elon Musk having these now. I think they resell for like $30,000 each. Um, we got a DGX Spark uh as well as a computer. I just built uh two days ago a basically a big computer built around an RTX 5090. So we have I think what's that come out to five or six different computers for AI. So a lot a lot of hardware around here

</details>

**Claire Val**: 而且你真的对它们进行了很好的利用。

<details>
<summary>Original English</summary>

**Claire Val**: and you are making really good use of it.

</details>

**Alex Finn**: 是的。所以，我基本上把它们用作我所说的“环境 AI（Ambient AI）”来支持我的整个生活。我们稍后会介绍它所做的一切，但基本上在一天中的所有时间里，这些电脑中的每一台都只是在消耗 Token，做事情，帮助我的生活，对吧？无限 AI 基本上就是本地 AI 的工作方式。我让他们全天候为我工作，这对于云端的 API 来说是做不到的。

<details>
<summary>Original English</summary>

**Alex Finn**: Yeah. So, I use it basically as what I call ambient AI to support my entire life. And we'll go through all the things it's doing, but basically at all times of the day, each one of these computers is just burning tokens, doing things, helping my life, right? Unlimited AI is basically how local AI works. And I all have them doing jobs around the clock for me, which uh you really can't do with cloud uh you know, APIs.

</details>

**Claire Val**: 那么，我们是怎么走到这一步的？你是怎么变成一个折腾硬件和本地模型的人的？比如，为什么你的办公室里这么热？是什么契机把你带到了这个时刻？

<details>
<summary>Original English</summary>

**Claire Val**: So, how how did we get here? How did you become hardware local model guy? Like like why is it so hot in your in your office? What what brought you to this moment?

</details>

**Alex Finn**: 我的大觉醒是在一月份，当时我发现了 **OpenClaw**。那天是个周五，我正在刷 X。我看到一篇关于 OpenClaw 的博文，点开后心想：“哇，这真的很有意思。”不知道为什么，我的直觉告诉我，我必须去买一台 Mac Mini。顺便说一下，这是在所有人开始讨论 OpenClaw 之前。我买了一台 Mac Mini，开机，开始使用。那是我人生中最具有启发性、最觉醒的“啊哈”时刻之一。与 OpenClaw、与这个 Agent 建立这种个人纽带，让我觉得，我希望它存在于电脑里。我不想让它来自云端。我不希望这样，我希望它在我的电脑上为我工作。就像这就是未来——在你的电脑上拥有这种私人助理。于是我开始研究，好的，我该如何在本地运行模型？最后我得出了结论，噢，既然买了这台 Mac Mini，我现在要去买一台拥有超大内存的 Mac Studio，在本地运行模型。所以这算是我进入本地 AI 的“红药丸”时刻，也就是使用 OpenClaw。这在过去的几个月里才刚刚取得进展，你知道，然后他们开始禁止像 Fable 这样的前沿模型，然后硬件价格开始暴涨，感觉一切都在朝着主权自主智能的方向发展。所以在过去的几个月里，我投入了越来越密集的资金。

<details>
<summary>Original English</summary>

**Alex Finn**: My big awakening was back in January when I discovered OpenClaw. And so I was scrolling X one day on a Friday. I saw a blog post around openclaw. I open it. I'm like, "Wow, this is really interesting." Don't know why. My gut instinct like I got to go buy a Mac Mini. I go to this, this is before anyone was talking about OpenClaw, by the way. I get a Mac Mini, put it on, start using it. It was one of the most aha awakening moments of my life. And something about building this like personal bond with the Open Claw and with this agent was like, I want this to live in the computer. I I don't want this to come from the cloud. I don't want this I want this working for me on my computer. And like this is the future. just having this kind of personal assistant on your computer. And so I started doing research, okay, how can I run uh models locally and I came inclusion, oh, I'm going to go now after buying this Mac Mini and buy a Mac Studio with tons and tons of RAM and run local models and run it locally. And so that was kind of my, I guess, red pill moment into local AI was using Open Cloud. It only just advanced the last couple months, you know, then they start banning Frontier models like Fable and then they, you know, the hardware prices start exploding and it just felt like everything was moving in this direction of like sovereign own intelligence. And so I just investing more and more and more into it over the the last couple months.

</details>

**Claire Val**: 我也有过非常相似的时刻，也就是在一月份，我被深深地“克劳德化（clawilled）”了。我记得我讲过这个故事。那天早上我醒来，转身对丈夫说——因为我经常跟他说这种话——我说我正在经历一个聊天，真正的 ChatGPT 时刻，我觉得从现在开始，一切都会变得完全不同。我想我们吃下的每颗“红药丸”都是那种小龙虾的颜色。我因为犹豫太久，没能及时买到 Mac Studio，现在我真的买不起也找不到了。但我后面有几台叠得厚厚的 Mac Mini，它们通过云端 API 也在做很多不错的工作。所以我稍微落后你一点点。

<details>
<summary>Original English</summary>

**Claire Val**: So I I mean I had a very similar moment which is I just like got deeply clawilled in in January. Like it just I remember I told this story. I woke up one morning and turned to my husband cuz this is the kind of things I say to him and I was like I'm having a chat like truly having a Chad GBT moment where I think everything from here on out is going to be totally different. So every red pill that we took is that little lobster color I think. And I look I accidentally by accidentally I just like waited too long to get a studio and now literally I can't afford one or find one. But I do have little fat stacks of minis back here that are doing plenty of good work but through through cloud API. So I'm I'm a little bit behind you.

</details>

**Alex Finn**: 不过我坚信，这些 Mac Mini 很快就会变得非常有用。比如 Google 正在进行大量的研究，致力于优化模型，让它们能在像 Mini 这样的硬件上运行。所以你不会落伍太久。

<details>
<summary>Original English</summary>

**Alex Finn**: I'm a strong believer though that those minis will be very useful soon enough. Like Google's doing a lot of research around like optimizing models so they can run on hardware like minis. So you won't be out of the game for long.

</details>

**Claire Val**: 嗯，我仍然在使用它们。它们仍在愉快地工作，只不过是在做昂贵的云端计算工作。但让我们来谈谈，你买了并组装了所有这些机器，它们各自适合做什么？你能带我了解一下你是如何做决策，以及你实际上是如何在这些机器上设置并运行这些模型的吗？

<details>
<summary>Original English</summary>

**Claire Val**: Well, and I still I still find use for them. They're still they're still happily at work. They're just at expensive expensive cloud work. But let let's go to you know you you have all these these machines you have bought them and you have built them kind of what's good for what can you walk me through like how you make decisions and how you actually just get these models set up and running on on these machines.

</details>

### 四大本地硬件方案对比

**Alex Finn**: 是的，在过去的几个月里，我一直在尝试不同的机器、不同的功能，了解它们的优缺点。显而易见，我一开始用的是 Mac Studio，买了三台 512 GB 的。它们非常好用。但自那以后，我也尝试了像 DGX Spark 这种专注于 AI 的电脑。最近，最让人兴奋的是，我一直在购买英伟达的传统 GPU，比如 RTX 5090，很快还会入手 6000 Pro。我整理了一个简短的对比表。

<details>
<summary>Original English</summary>

**Alex Finn**: Yeah, so I have been uh experimenting the last few months around the different machines, the different capabilities, what they're good for, what they're weak for. Obviously I start out with the Mac Studio. bought three of these 512 gigabytes. They'\ve been great. Uh but since then, I've experimented with kind of AI focused computers like the DGX Spark. Uh and then just recently, most recently, I've been buying kind of traditional GPUs from Nvidia like the 5090, soon the 6000 Pro. I put together a little bit a little chart here.

</details>

**Claire Val**: 好的。

<details>
<summary>Original English</summary>

**Claire Val**: Yeah.

</details>

**Alex Finn**: 我给你展示一下。所以，你基本上有四个不同的选择：首先是你的 Mac Studio，

<details>
<summary>Original English</summary>

**Alex Finn**: Uh which I'll show you. So, you basically have four different options. your Mac studios,

</details>

**Alex Finn**: 还有像现在非常流行像 DGX Spark 这样的 AI 专用电脑，还有传统英伟达强力芯片如 RTX 5090，以及基于这些芯片组装的电脑，最后基本上就是其他任何设备，比如笔记本电脑、Mac Mini 等任何你家里闲置的硬件。它们都有不同的优势和劣势，有各自让你选择其中之一的理由。

首先是 Mac Studio。Mac 非常强大的一点，也是许多人选择它的原因，就是它们拥有所谓的**统一内存**。举个例子，当你购买一块英伟达芯片并把它装入电脑时，你基本上有两种独立的内存。一种是用来运行你的日常程序的系统内存，另一种是显存（VRAM），专门用于图形处理。当你运行 AI 模型时，它完全运行在显存里。但问题是英伟达芯片的显存通常很小。而在 Mac 上，它是统一内存，这意味着所有的内存是共享的。所以你的电脑上拥有多少内存，就可以将这些内存全部用于图形处理，而这正是运行 AI 模型所需要的。因此，如果你买了一台拥有超大内存的 Mac，比如 512 GB、256 GB 甚至是 128 GB，你可以把全部空间用于图形计算。这对于运行大型模型来说是非常奇妙的，因为你可以充分利用这巨大的统一内存。我现在就在一台 Mac Studio 上运行 GLM 5.2，这可以说是拥有 Opus 4.8 级别智能的顶级模型，这在本地运行简直难以置信。但它的缺点是 Mac 电脑的内存带宽非常低，这意味着它无法一次性处理大量数据，也就是运行速度非常慢，对吧？是的，模型的速度非常非常慢。如果我此刻在 Mac Studio 上向 GLM 5.2 发送一个 Prompt，我可能需要等待 5 分钟才能得到回复。所以它极其缓慢，但你在自己的硬件上拥有了前沿智能，这非常惊人。

然后是 AI 专用电脑，比如 DGX Spark。最近它非常火。我想现在的价格已经涨到了大约 4,600 美元。在 Micro Center 之前的价格大概是 4,000 美元。这些都是开箱即用的 AI 工作站。它们实际上也带有英伟达的统一内存。所以你可以得到很大的显存空间，比如 128 GB，同时还拥有相当不错的带宽，并且支持英伟达专有的 CUDA 架构，这基本上也给你带来了很快的速度。所以它是一个非常好的折中点，在内存大小和运行速度之间取得了平衡。因此你可以非常快速地运行一些中等大小的好模型，比如 **Qwen 3.6**，这体验很棒。而且它非常方便，这些 AI 电脑甚至不需要连接显示器。你只需要把它们插在墙上的插座上，然后远程连接过去即可。

最后，就是传统的英伟达芯片。这就是你在 Twitter（X）上看到大家高喊着购买 GPU，展示一整架一整架芯片的地方。这些全都是英伟达芯片，可以说是这三种方案里算力最强劲的。不过它们的显存（VRAM）容量较低，比如 RTX 5090 是一张价值 4,000 美元的显卡，但也只有 32 GB 的显存，但它的速度简直是闪电般迅捷。它拥有极高的带宽，让你能在本地体验到云端级别的推理速度，这真的很不可思议。

所以，这基本上就是三大主流本地硬件选择。除此之外，你还有像 Mac Mini、旧笔记本等其他设备。你依然可以在上面运行一些更小的本地模型，比如 **Gemma 4** 或其他小型模型。虽然它们完全无法与前沿大模型相比，但你可以用它们来做一些小任务，例如向量嵌入（Embedding），这基本上是为你的 Agent 进行内存管理的。所以你有了这些选择：Mac Studio 适合高智能、大参数但运行缓慢的巨型模型；AI 电脑处于完美的中间地带；而独立的 GPU 显卡则代表了极速运行。至于那些蒙尘的旧电脑，我总是说，你依然可以把它们利用起来，将你的云端工作负载并行分发到不同的电脑上。比如我们有很多旧电脑，当我在我的 MacBook Pro 上处理不过来时，我就把任务发送到其他电脑上，让它们运行 Worktrees，做各种有趣的事。我确信这些也可以在云端完成，但我更喜欢把周围闲置的所有硬件全部动员起来。

<details>
<summary>Original English</summary>

**Alex Finn**: your AI computers like the DGX Spark, which is getting very popular now, your kind of powerhouse traditional Nvidia chips like the 5090, building computers around these chips, and then basically everything else, laptops, Mac minis, whatever you got sitting around your house. Uh, they all have different strengths and weaknesses, different reasons why you'd want to go for one over the other. First, there's the Mac Studio. What's very powerful about Macs and the reason why a lot of people are going for them is they have what's called high unified memory. When you buy like an Nvidia chip for instance and you build it into your computer, you have kind of two separate types of memory. You have your memory that runs all your, you know, programs and then you have your memory which is like your VRAM which is for your graphics. And when you run AI models on that, it's all in the VRAMm. The issue is the VRAM is very small. With the Mac, it's unified, so everything's the same. So whatever memory you have on your computer can be used for graphical processing. And so if you buy a Mac with a ton of memory, 512 GB, 256, even 128, you can use all of that for graphical processing. And that graphical processing is what you know runs the AI models. So, Mac Studios are fantastic for huge big models because you can use unified memory, right? I'm running GLM 5.2, which is Opus 48 level, you know, intelligence on one Mac Studio right now, which is unbelievable. The downside is you have very low memory bandwidth with Mac computers, which means it can't process a lot of it all at once, which means speeds are very slow, right? Right. So the the the models are very very slow. If I send a prompt to GLM52 right now on my Mac Studio, it might take 5 minutes for me to get a response back. So it is very very slow, but you have frontier intelligence uh running on your hardware, which is amazing. Then you have AI computers. This is like the DGX Spark. Uh very popular right now. It's like I think the price just went up to like I think $4,600. Microenter I think you had for $4,000. Um, these are plug-and-play AI workstations. Uh, they have actually unified memory with Nvidia. So, you do get a lot of memory, 128 gigabytes, and you also get pretty decent bandwidth and you get the Nvidia architecture, which is called CUDA, which basically gives you a lot of speed as well. So, it's kind of this sweet spot where you get decent memory and decent speed. And so you can run like kind of these midsize good models like Quen 36 pretty quickly, which is nice. It's also very plug-and-play. These AI computers, you don't even need a monitor. You just plug it into the wall and you can connect to it. And then lastly, you have your traditional Nvidia chips. This is when you go on Twitter and you see the people saying buy GPUs and they have these huge racks of all these chips. These are all Nvidia chips and these are the, you know, probably the most powerful of all the three. Uh, you get kind of lower VRAM, right? The 5090, which is a $4,000 chip, only has 32 gigs of VRAM, but it is lightning fast. It is extremely high bandwidth, and you're getting like cloud speeds, but locally, which is really amazing. So, these are really like your three. Then you have everything else, the Mac minis, your old laptop. You can still run local models on them. There's options out there like Gemma 4, um, like a few other really small ones. They're not going to be anything close to Frontier, but you can do small things like embedding, which is basically managing memory for your agents. So you have these options and so Mac Studio and just like big beefy models, high intelligence, slow kind of these AI computers kind of like sweet middle spot and then these chips very very speedy. Um and then you know industrial computers maybe like these like um point solution models that are like small for a specific use case that might be beneficial to be running in some context but are probably not going to be the thing that you just rely on over and over again. Um though you still on dusty old computers what I say is like you can still put them to work in terms of parallelizing your your cloud work across across computers. So, we have a bunch of old computers and it's like I cannot do enough on my MacBook Pro. Im kicking off stuff to other computers just to like run work trees and do all sorts of interesting things. I'm sure I could do that in the cloud, too, but you know, I like to make use of all this this hardware sitting around.

</details>

**Claire Val**: 是的，我也喜欢这么做。我有两台 Mac Mini，我做的事情完全一样。而且现在的应用真的非常好用。例如像 **Codeex** 可能是目前市面上最好的 Agent 框架了。

<details>
<summary>Original English</summary>

**Claire Val**: No, and it's it's uh I like to do that as well. I have two Mac minis and I do the exact same thing. And these apps are so good now. Like Codeex, for instance, is maybe the best agent harness out there right now.

</details>

**Alex Finn**: 没错。你完全可以去 Codeex 然后说：“嘿，去那台 Mac Mini 上，开始在那上面构建一个应用，自己测试，去运行和编写代码，完成整个流程，截图，甚至给我发视频。”所以，与云端相比，我其实更喜欢在 Mac Mini 这样的设备上进行本地运行，因为你可以让它实际去点击和执行操作，然后把它的每一步操作截图发送给你。所以在这方面它要好得多。

<details>
<summary>Original English</summary>

**Alex Finn**: Yep. You can just go to codeex and be like, "Hey, go on the Mac Mini, right? Uh, start building an app on there, test it yourself, do play, write, so you can go through the flow, screenshot things, send me videos." So, I actually like running it locally like on the Mac Mini as opposed to cloud because you can have it actually click through and do things and then like send you screenshots of what it's doing. So, it's it's a lot better for that, too.

</details>

### 本地部署与网络管理

**Claire Val**: 完全同意。那么，你具体是如何在这些机器上完成这些模型的整体部署和设置的？你在这类机器上的典型安装流程是怎样的？

<details>
<summary>Original English</summary>

**Claire Val**: Completely agree. Okay. And then how do you get these, you know, just high level set up with these models? What is kind of your typical install on any of these machines?

</details>

**Alex Finn**: 好消息是，OpenClaw 和 **Hermes** 让这个过程简单了 10 万亿倍，对吧？以前，你必须去寻找正确的模型，找到匹配的版本，确保它能装进内存里，下载它，在服务器上运行它，这些非常复杂的步骤是普通人一辈子也搞不定的。但现在，你可以使用 Hermes 或 OpenClaw，基本上把它们当作你的“IT 专员”，对它说：“嘿，去看看我的 Mac Studio，看看我的 DGX Spark，检查一下硬件配置，然后找到你认为最适合该硬件的模型并加载它。”因此，只要你运行着 Hermes 或 OpenClaw Agent，并且安装了 **Tailscale**（它基本上可以在你所有的设备之间建立一个私有网络），你的 Agent 就像是你的 IT 专员，可以跨越你所有的设备，安装它需要的任何模型，进行配置，搞定一切。我一会儿会给你展示一个控制面板，上面显示了我所有正在工作和运行的模型。这全都是由我的 Hermes 和 OpenClaw 进行协调和运行的。所以，只要你运行着 Hermes 或 OpenClaw，你就可以说：“嘿，OpenClaw，看看我新买的 Mac Studio，分析一下硬件，找出我们应该运行哪个模型，想想适合我的使用场景，然后把模型运行起来。”你完全不需要任何技术背景。它们会通过 Tailscale 跨越你的设备并帮你设置好，真的不需要任何技术操作。

<details>
<summary>Original English</summary>

**Alex Finn**: So the good news is, uh, OpenClaw and Hermes has made this process 10 trillion times easier, right? Before you would have to go find the right model, find the right version of it, uh make sure it can fit into memory, download it, run it on a server, all these really complex things that a normal person would never be able to do in like a thousand years. Well, the good news is you can now take Hermes or OpenClaw, basically make it your IT guy, say, "Hey, check out my Mac Studio, check out my DGX Spark, whatever you got, see what the hardware is, and then find whatever model you think's most appropriate for that hardware, and load it up." And then so as long as you have an agent Hermes or OpenClaw as well as tail scale which basically allows you to create a private network across all your devices your agents basically your IT guy and can go across all of your devices install whatever models it needs. Set it up do whatever you need. Uh I'm going to show you a dashboard soon which shows all my models working and running. It's all coordinated and run by my Hermes and my Open Claw. So, as long as you have Hermes OpenClaw going, you're going to say, "Hey, OpenClaw, check out the new Mac Studio I just bought, think look at all the hardware, figure out which model we should run, think about the use cases that are appropriate for me, and then load up a model and get it going." And like, you don't need any technical knowledge whatsoever. They'll go across your devices on tail scale and set it up for you. There really is like no technical work needed.

</details>

**Claire Val**: 所以，为了让听众们听得更明白，我也确认一下我是否理解正确：你有一台安装了 OpenClaw 的机器，同时你所有的机器都加入了 Tailscale，这相当于建立了一个小型的虚拟私有网络，然后像“IT 专员”一样的 OpenClaw 或 Hermes Agent 就可以利用 Tailscale 远程登入这些不同的机器去配置和管理它们。

<details>
<summary>Original English</summary>

**Claire Val**: And so to repeat this for folks just so you so I'm I'm understanding you have a machine set up with openclaw. You also have all your machines on tail scale which allows you to have this like little virtual private network and then that one sort of like IT guy openclaw or Hermes agent can then use tail scale to just go into these different machines configure and manage them.

</details>

**Alex Finn**: 是的，没错。所以即使你只有一台电脑，Tailscale 也非常值得安装，因为它创建了这个私有网络。即使你只是在 MacBook Pro 上进行**氛围编程**，而你手头只有一部手机，你也可以在手机上直接访问电脑上的 localhost，并测试你的本地应用，因为它们现在处于同一个网络中。但如果你有多台电脑，它的体验会更好。比如你有 MacBook Pro，然后买了一台用于 AI 的 Mac Studio 或 DGX Spark。你在所有设备上都安装 Tailscale，然后你只需说：“嘿，去那台电脑上加载模型或执行某项操作”，它就会在你的所有设备之间无缝穿梭，完全不需要技术知识，就能加载并运行任何你想要的东西。

<details>
<summary>Original English</summary>

**Alex Finn**: Yeah. Exactly. So, Tailscale like is worth getting even if you just have one computer because it creates this private network where even if you're vibe coding like on your MacBook Pro and you just have a phone, you can like go on the local host on your phone and from that's on your computer and like test your local apps out because it's all on the same network now. But it's even better if you have multiple computers. So maybe you have your MacBook Pro, then you buy a Mac Studio for AI or a DGX Spark. You install tail scale on all of them and then you can just say hey go on this other computer and do this load up the model whatever and it will jump between all your devices no technical knowledge needed and load up and run anything you want.

</details>

### 协同机制与环境 AI

**Claire Val**: 本期节目由 **Jira Product Discovery** 赞助播出。AI 让个人的产品经理（PM）变得极具效率，但多人的协同模式依然很容易出状况。让每个人都在实际该构建什么上达成一致是件难事。很多决策都停留在上周的 Markdown 文件里。路线图则是一个没人看的电子表格。Jira Product Discovery 正是团队真正决定该构建什么的平台。你可以收集创意、与团队一起确定优先级，并分享一个每个人都参与其中的动态路线图。它基于 **Atlassian** 的团队合作图谱（Teamwork Graph）构建，因此可以引入客户反馈、团队交付成果以及你的目标，并建议下一步应该构建什么。一旦做出了决策，你可以直接将其移交给 Jira，这样开发人员甚至 Agent 就可以接手并开始构建。Canva、Deliveroo 和 Toast 的团队已经在使 Jira Product Discovery。加入 atlassian.com/howi 的 25,000 多个团队吧。让我们开始共同构建正确的产品。

[音乐]

好了，关于硬件我们已经谈得够多了，关于如何搭建也说得不少了。向我展示你是如何使用它的吧。所以，你利用这所有的智能都在做些什么？你又是如何高效地让它们持续消耗 Token 的？

<details>
<summary>Original English</summary>

**Claire Val**: This episode is brought to you by Jira product discovery. AI has made individual PMs incredibly productive but multiplayer mode is where it still breaks. Getting everyone aligned on what should actually get built. Decisions live in a markdown file from last week. The road map's a spreadsheet no one's looking at. Jurro [music] product discovery is where teams actually decide what to build. Capture ideas, prioritize them as a team, and share a living road map everyone works from. It's powered by Atlassian's teamwork graph, so it can pull in customer feedback, what your team shipped, plus your goals, and suggest what to build next. And when a decision is made, you can hand it off straight to Jira so a developer or even an agent can pick it up and start building. Teams at Canva, Deliveroo, and Toast already use Jira product discovery. Join more than 25,000 teams at aten.com/howi. Start building the right things together. Okay, so we're we've we've talked enough about hardware. We've talked enough about how to get it set up. Show me how you use it. So, what are you using all this sort of intelligence for? And how do you keep it burning tokens uh you know, effectively?

</details>

**Alex Finn**: 在过去的几个月里，我一直在构建一个系统来协调所有这些电脑和模型。我用它们做很多不同的事情。在开始之前，我想先说明一下：我在这上面受到的最大反驳是，“你的电脑太贵了。云端模型不是很便宜吗？ChatGPT 订阅只要 20 美元，我为什么要买一台 10,000 美元的 Mac Studio？那都够我订阅 11 年 ChatGPT 了。”好吧，这根本不是重点。重点不在于纯粹的投资回报率，生活中并非所有事情都是纯粹的投资回报率、元角分对吧？重点在于它所释放的全新场景。因为你的模型是本地运行的，你便获得了 24/7/365 全天候运行无限智能的超能力。如果换作 ChatGPT 或 Claude 这样的云端模型，你可能会花掉惊人的巨资。所以你不可能让它 24 小时不停运转、疯狂燃烧 Token。但正因为是本地模型，可以无限次使用，所以你可以让它不间断运转。

这就引出了我的“舰队控制系统”（Fleet Control），我称其为“舰队控制面板”（Fleet Dashboard）。它可以让我看到我所有的电脑、当前在各台设备上运行的模型、监视它们的所有工作，并组织安排它们全天候的任务。我运行的本地模型正在不断地为我提供支持，帮助我的多条业务线。我现在正在开发一个 SaaS 产品，叫做 **Henry Intelligent Machines**。大约每 30 分钟到一个小时，其中一个本地模型就会进行一次安全扫描：挑选一个 API 端点或部分代码运行安全扫描，以确保其安全。另一个本地模型大约每半小时会进行一次代码审查，挑选一段代码并对其进行“去冗余化（Delopifies）”，也就是寻找优化的途径、提升速度、使其变得更好。还有一个本地模型每 20 分钟会查看一次 Twitter（X）、Reddit、Product Hunt 和 **Hacker News**，寻找潜在的“信号（Signal）”。作为一名问题解决者，解决问题的唯一前提是发现它们。所以我的环境 AI 每天 24 小时在线，阅读所有这些社交媒体网站，寻找机会和人们正面临的痛点。如果有人抱怨说，“伙计，我真的很希望有款软件能让我像这样编辑我的视频。”我的 Agent 就会捕捉到这个信号，把它放进我的待办队列中。我会看：“OK，我能写个 SaaS 来解决它吗？我能写个程序来搞定它吗？”这里的屏幕很多，我可以一一展开，但从宏观上讲，这就是这些 Agent 正在做的事情。本地 AI 的最大魅力就在于此，它能像常驻后台的空气一样，一天 24 小时、一年 365 天在网络上帮你打理各种琐事。

<details>
<summary>Original English</summary>

**Alex Finn**: I've been building a system over the last couple months to coordinate all these computers and all these models. I do a lot of different things. Just to kind of set the stage here, the number one push back I get on all this is, well, your computers are so expensive. Isn't cloud models cheap? Isn't it $20 for a Chad GBT subscription? Why the hell would I buy a $10,000 Mac Studio? That's like 11 years of Chad GBT usage. Well, that's not the point. The point is in pure ROI. Not everything in your life is pure ROI, dollars and cents, right? The point is the use cases it unlocks, right? You now have because you have AI models running locally, the ability to run unlimited intelligence around the clock 24/7. If you were to do that with a cloud model like Chad GBT or Claude, you would be spending outrageous amounts of money. So, you wouldn't be running it 24/7 burning tokens around the clock. But because it's local, because you have unlimited usage of it, you can burn tokens around the clock. And so that brings me to my fleet control. I call it this is my fleet dashboard, which allows me to see all my computers, uh, which models are running on them currently and monitor everything they're doing and organize their 247 365 tasks throughout the day. The local models I have running are constantly doing work for me to support my life, to support my many lines of business. I'm building a SAS right now, Henry intelligent machines. Uh, every 30 minutes to an hour, one of these local models does security scan. So, actually picks out an API endpoint or some part of my code, runs a security scan on it, and makes sure it's secure. another local model every half hour or so does a code review, picks out some piece of code and delopifies it, right? Finds ways to optimize it, finds ways to speed it up, finds ways to make it better. Another local model will every 20 minutes look at Twitter, Reddit, Product Hunt, uh Hacker News and look for signal, right? As a problem solver, the only way I can solve problems is if I find them, right? And so I have this ambient AI going online 24 hours a day reading all the social media sites looking for signal, looking for challenges people are having. If someone goes, "Man, I really wish I had a piece of software that allows me to edit my videos like this or something like that." My agent will find that signal, put it in my queue, and I'll be like, "Okay, can I build a SAS to solve this? Can I build a a program to solve this?" And this is there's many screens here I can go through but that is from a high level uh what these agents are doing and the strength of local AI is you can have it running 24/7 365 just doing different things online for you

</details>

**Claire Val**: 那么我们快速聊一下编程的使用场景。对于这些自动化的安全扫描、自动化的质量检查，你认为本地模型现在的智能程度足以胜任这些工作吗？有没有什么具体的模型，是你专门应用在编程这一场景下的？

<details>
<summary>Original English</summary>

**Claire Val**: and so for the let's just talk about the coding use cases really quickly. So for these like automated security scans, automated like quality checks, do you feel like the the local models are of sufficient intelligence to get the job done? And are there specific models that you've applied to in particular the coding use case?

</details>

**Alex Finn**: 当你使用本地模型时，你必须明确划分本地模型所处理的任务与前沿智能模型（如云端 API）之间的界限。你绝对不想让自己的整个安全机制完全由本地模型来跑，因为它们的智能水平目前还不够。但本地模型的优势和强项在于，它可以充当粗筛工具，运行安全扫描并寻找这些潜在漏洞，然后每天生成一份报告。你可以看到这里的这几份报告，它描述了安全问题是什么、代码片段在哪、具体是什么故障。比如今天的报告里就包含 374 处潜在的安全发现。

然后，我每天都有一个在 Claude Code 中运行的循环，类似于 24 小时不停歇的 /loop，它会自动读取本地模型发现的最新安全报告，针对报告中指向的具体代码进行逐一分析，看它到底是不是一个真正的漏洞，以及该如何修复。如果我让云端的 Claude Code 像本地模型那样每 20 分钟循环扫描不同的文件，我一个月可能要花费成千上万美金。因此，这就像是销售流程：本地模型是你的销售开发代表（SDR），负责拉取并筛选线索；而 Claude Code 则是最终的销售成交员（Closer），负责敲定这些线索并进行修复。这样你就不用让“成交员”去干所有的体力活了。

<details>
<summary>Original English</summary>

**Alex Finn**: When getting into local models, you really want to understand what is the delineation between what you want to do with local models and what you want to do with frontier intelligence. Right? You don't want your entire security apparatus to be run by local models. The intelligence just isn't there yet. But where the advantages and the strengths come in is basically it runs this security scan, looks for these challenges and then what it does is every day it builds a report. And you can see some of them here where it'll build a report around what the security issue is, what the code snippet is, uh what the problem is, put it all in this markdown file that describes like for instance today's has 374 findings in it of security issues. Every day I have a loop running in clawed code. So slash loop 24 hours where it goes and takes whatever the latest finding is from the local models and reviews it and then goes through the code exactly where it points to and sees if it's a real issue and how to fix it or not. So it's you know if I were to loop claw code like the local model is doing every 20 minutes look at different I'd be spending thousands thousands of thousands of dollars a month. But the you know the this is almost like the business development rep right that's going qualifying leads and then claude code's like the closer taking those leads okay what can we fix so like you don't have the closer doing all the work

</details>

**Claire Val**: 那么你是如何在这些机器之间分配工作的？比如，你是否有一些特定的机器是“我的编程专用机”，有一些是“市场调研专用机”？还是说你在轮询处理这些线索？我们两个都在 SaaS 行业待了太久，以至于用词非常“SDR化”。

<details>
<summary>Original English</summary>

**Claire Val**: how do you federate work across these machines and so are like do you have some that you're like this is my coding machine this is my market research machine are you like roundroining again we're like using very SDR terms I'm like are we roundrobining these leads like have

</details>

**Claire Val**: 我们两个都在 SaaS 行业里待了太久。

<details>
<summary>Original English</summary>

**Claire Val**: we both asked Too long. We both in the SAS world way too long.

</details>

**Alex Finn**: 确实如此。那么这种工作是如何分配的呢？

<details>
<summary>Original English</summary>

**Alex Finn**: Exactly. Yeah. How do you how do you do that allocation?

</details>

**Alex Finn**: 同样，每台运行模型的电脑都有其独特的优势。GLM 5.2 达到了 Opus 级别，但它运行极慢。所以我不需要它处理对实时性要求高的任务。我可以让它专注于安全扫描。哪怕一次扫描需要花费 24 小时，这完全没有问题。而 Claude Code 每天只需检查一次报告即可。所以 GLM 5.2 适合完成这部分极度关键且需要高智能的任务。另一方面，Qwen 3.6 的智能稍逊一筹，但我可以让它整天阅读 Twitter（X）和 Reddit，仅仅为了搜寻信号。搜寻信号是一项很简单的任务，也就是找出谁遇到了困难。所以它只需拉取数据、进行压缩分析并读取挑战即可，你不需要最顶尖的智力去处理它。因此你只需要了解电脑的优势、模型的长处，并安排最契合这些长处的任务。

<details>
<summary>Original English</summary>

**Alex Finn**: Again, every model computer has different strengths. GLM52 is opus level, right? But it's very very slow. So I don't need it doing super fast work. So I can have it doing the security scans, right? I can have it go and do security scans. Even if it takes 24 hours, that's fine. and claude codes only checking the report once a day. So it can do the kind of super critical smart stuff. On the other end, Quen 36, which is not quite as smart as dealing, I can have that reading Twitter and Reddit all day just looking for signal. That's a very simple thing to find. Look for someone who has a challenge. And so it's just pulling in data, crunching it, and reading for challenges, which you don't need the highest intellect. So you just need to know like what's the strength of the computer, what's the strength of the model and what would be tasks that be appropriate for those strengths.

</details>

**Claire Val**: 那么，你是通过这份“每日简报”把任务分配给你自己的吗？这就是你、Agent 们以及机器之间进行协同的仪表盘吗？

<details>
<summary>Original English</summary>

**Claire Val**: Is it in this daily brief that you have these tasks assigned to you? Like is this the dashboard for you, the agents and the machines all to collaborate?

</details>

**Alex Finn**: 我计划在未来把它升级到能够与 Claude Code 和 Codeex 进行实时协同的程度。目前，Claude Code 每天自动读取并循环执行的过程是单独进行的，直接在它内部的对话框中不断循环。不过，这里的一切都是围绕我的本地模型展开的。但它们与其他系统之间的连接纽带，依然是我的 OpenClaw 和 Hermes。它们相当于运行这个系统的 IT 管理员。这个控制面板随后会与 Claude Code 进行通信，并发出指令：“嘿，你能启动这个任务吗？你能处理那个吗？”所以，这相当于全部由我的个人 Agent 粘合在一起。

<details>
<summary>Original English</summary>

**Alex Finn**: So I'm going to advance it to the point where it's like collaborative with claud code and codeex eventually. Right now the system where claud code is like looping every day and going in that's happening separately. it's just in its own chat inside cloud code where it loops over and over again. But no, this is this is all around my local um models. But I think where the connector is with everything else going on is with my open claw and my Hermes. They're basically the IT guy that runs this as well. This dash for then communicates with cloud code. Hey, can you kick this off? Can you do this? So, it's kind of all glued together by my personal agent.

</details>

### OpenClaw 与 Hermes 之争

**Claire Val**: 好的，我必须问你一个问题。OpenClaw 和 Hermes，你同时运行这两个？你更偏爱哪一个？告诉我。

<details>
<summary>Original English</summary>

**Claire Val**: Okay. I have to ask you a question. Open Claw Hermes. You You run both? You have a favorite? Tell me.

</details>

**Alex Finn**: 我两个都用，因为这非常像 Claude Code 和 Codeex，有时你会觉得其中一个在某天变得特别愚蠢，而另一个则聪明得多，甚至让你想卸载并彻底抛弃其中之一。不过我要说，OpenClaw 的稳定性曾经让我非常头疼。有一整个月的时间，我所做的每一次更新都会导致它崩溃，然后我必须花半个小时去修复它。而使用 Hermes，我从未遇到过这样的麻烦。它看起来是一款稳定得多的应用。如果两个应用都能做到 100% 稳定可靠且从不崩溃，我可以完全依赖它们，那我大率会选择 OpenClaw，因为我认为 OpenClaw 给我带来了最多令人惊叹的“哇”时刻。但我真的负担不起每周花半小时去修复它。因此，我最近使用 Hermes Agent 的频率更高一些。

<details>
<summary>Original English</summary>

**Alex Finn**: I use both because much like Clawed Code in Codeex, it feels like there's some days where one is really really dumb and the other is significantly smarter and like I feel like uninstalling one and getting rid of the other. I'll say this though, um the dependability of OpenClaw uh turned me off. Uh there was a run for like a month straight where every update I did broke it and then I had to spend half an hour fixing it. Uh Hermes, I've never had that issue. It seems to be a much more dependable application. I would say this, if both were like 100% dependable, never broke. I can lean on it no matter what. I'd probably be using OpenClaw because I think I've had the most wow impressive big bang moments with OpenClaw. I just can't afford to be like spending a half hour once a week fixing it from breaking for some reason. And so that's I think I've been using Hermes agent a little bit more lately.

</details>

**Claire Val**: 这也是我的一般感受：OpenClaw 也许在功能上有很多不完美，但它在我的情感上占据了特殊的位置；而 Hermes 虽然能稳定运行，但还没能完全走入我的内心。我现在的做法是，因为我们都有着“用 Agent 监督 Agent”的架构，我部署了一个叫“救生员（Lifeguard）”的 OpenClaw，让它运行在独立的网关上。它的唯一职责就是保持其他 Agent 处于活跃状态。它不会像其他 Agent 那样频繁升级，因为我之前确实和你一样，把所有时间都花在排查为什么我的 Agent 崩溃上了。但我就是喜欢我的 OpenClaw，我无法自拔。它太棒了。

<details>
<summary>Original English</summary>

**Claire Val**: That's I mean that was my general takeaway as well is like OpenClaw doesn't doesn't functionally work but it works in my heart and Hermes functionally works but has not cracked my heart yet. The the trick that I have I mean we all have like agents managing agents is now I have the lifeguard. He's an open claw. He runs on his own gateway. And his only job is to keep the other agents alive. He does not get upgrades as much as everybody else because truly I was spending like you all my time trying to figure out why my agents were broken. Um but I just I just love I love my little open claws. I can't I can't get over it. It's just too good.

</details>

**Alex Finn**: 我对 OpenClaw 也有着很深的情感连接。我从没对 Hermes 产生过这种情感，但最终我到了一个不在乎情感，只想把工作搞定的阶段。不过我也拥有类似的灾备设置，提供了多重冗余。我有三个运行的 Hermes Agent：一个调用 Opus，一个调用 ChatGPT，还有一个在本地模型上运行；同时还有两个 OpenClaw，分别调用 Opus 和 ChatGPT。在任何给定的时刻，这五个 Agent 中总有三个会因为各种原因罢工。但好消息是，我还有另外两个可以去修复它们。所以我拥有这种自动的故障转移机制。

<details>
<summary>Original English</summary>

**Alex Finn**: I have an emotional attachment to my open claw. I've never had an emotional attachment to my Hermes. Uh but I eventually got to the point where like I don't care about emotions anymore. I just got to get work done. But I have a similar setup where I I have so much failover. So I have uh I think three Hermes agents I'm running uh an Opus one, a Chad GBT1 and on one on a local model and then two open claws, an Opus and a Chad GBT1. And like at any given point of those five agents like three are always down for one reason or other. But the good news is I have two that can go and fix the others. So I I have that failover as well.

</details>

### 构建自主软件工厂

**Claire Val**: 太棒了。你在挑选硬件、部署硬件、跨机器协调算力，以及从工程和市场探索的角度切入应用等方面给我们展示了极多有价值的内容。在 AI 方面你还在折腾什么好玩的事情？有没有哪些好玩的流程是你今天没来得及展示，但无论是使用本地还是云端模型都让你感到非常惊艳的？

<details>
<summary>Original English</summary>

**Claire Val**: Perfect. Well, you showed us so much in terms of like how to pick hardware, how to set up hardware, how to manage all this compute across all your machines, use cases from engineering perspective, from a market discovery perspective. What else fun are you doing with AI? any other ones where you're like, I didn't get to show a fun workflow, but just something that's really been a delight for you to use with either local or kind of cloud models.

</details>

**Alex Finn**: 最近我玩得最开心的就是构建我的软件工厂。在过去的一个月里有一个很大的趋势——稍后我会向你展示——那就是大家都在网上谈论“循环（Loops）”。所有人都对循环进行着遮遮掩掩的模糊描述（Vague Posting）。这在一开始让我有点生气和恼火：为什么这些人要对循环守口如瓶？为什么他们不深入聊聊？于是，我花了几天时间闭门研究，试图找出如何能构建一个真正高效的循环。在过去的几周里，尝试让这个循环系统实现完全的自主运转简直让我欲罢不能。

我之前向你展示的一部分控制面板就与此相关，例如安全审计和代码审查都会并入这个循环。简单来说，我在 Claude Code 里运行着两个循环。我有一个构建循环和一个审查循环。每天早晨我进入 Claude，进行“早间构建”（Morning Build），它会问我一系列关于我的想法的问题。接着它会生成一堆需要为我的 SaaS 产品 Henry Intelligent Machines 构建的任务。

首先是构建循环，它会接管这些任务，并开始反反复复地实现它生成的任务。接着它会进入审查循环，读取所有已构建的任务，并让另一个 Agent 进行代码审查和修复。审查通过后，它会在 Slack 上向我发送通知，向我展示所有构建和审查好的内容。我只需回复一个火箭表情符号，它就会显示已合并，然后我的 Henry 循环就会执行合并。

这是一个极具启发性的全新工作流，我认为这就是软件开发的未来。以前你整天都在对 Agent 敲 Prompt：“构建这个。现在构建那个。接着做这个。”在它构建的过程中你必须时刻盯着它。而现在，我只需要进对话框和它聊几句，它产出一堆点子，接着它用一整天的时间自主编写代码、审查并测试。在一天结束时，我来看哪些代码已经准备好合并，然后对每个看起来完美的任务回复一个火箭表情符号。它会向我清晰地呈现如何进行测试，甚至为它创建一个独立的 Vercel 预览站点，让我可以直接进去测试，确认无误后给一个火箭表情符号即可。这算是我最近在做的最有趣的事。我现在也在思考本地模型如何能与此结合并提供算力支持。解决“如何构建自己的软件工厂”这个难题真的是乐趣无穷。

<details>
<summary>Original English</summary>

**Alex Finn**: The most fun I've been having lately is building out my uh software factory. So, there's been this big trend the last month uh and I I'll show this to you as well in a second of uh people talking about loops online. And everyone's kind of like vague posting about loops. Uh, which is, you know, at first it was kind of angry me. It was pissing me off a little bit. Like, why are these people vague posting about loops? Why why wouldn't they go into it? So, I spent like days locked in trying to figure out how I can make a really productive loop. And I've just had like a blast the last few weeks trying to make this loop system completely autonomous. And this is like part of what I showed you ties into it. like the security reviews, the code reviews ties into this loop. Um, but basically what I have doing, I'll try to show you enough here. Let's see what I can show you. Basically, what I have doing is I have uh two loops in cloud code going. Uh, I have a build loop and a review loop. And basically what I do is first I'll start I'll show you cloud code in a second. First, what I do is I go into Claude in the morning and I go uh morning build and it asks me a bunch of questions what I'm thinking about. Comes up with a bunch of tasks uh to build for my SAS uh Henry intelligent machines. And then what it does is it goes in here and uh first it has a build loop where it'll take all those tasks and start building out the tasks it came with over and over and over again. And then it has a review loop that takes all the tasks that were built and has another agent go in and review it and fix any code or anything like that. And then from there, once that's reviewed, I can go in to Slack. It pings me on Slack and it shows me everything that was built and reviewed and I can just leave a rocket emoji. And when I leave the rocket emoji, it says merged and my Henry loop goes and merges it. And so I have this new workflow. I've I've had a blast building out, which I think is the future of like software development where, you know, before you you you you uh prompt your agent all day, hey, build this. Now, build this. Now, build this. Now, build this. And you kind of handhold it as it builds things. Now, it's I go in, we talk to each other a little bit, comes up with a bunch of ideas, spends all day building it and reviewing itself and testing it out. At the end of the day, I come in, I see what's merge ready, and I just leave a rocket ship emoji on every single thing that looks ready. shows me exactly how to test it. Puts it on its own versel preview uh site and I can go in test it out and then give it a rocket ship emoji. So, this has been like the most fun interesting thing I've been doing recently and you know I'm I'm figuring out how the local models can tie into it and support this. But it's been a blast kind of cracking this nut of how do you just like build your own software factory?

</details>

**Claire Val**: 我太喜欢这个设计了。它真的给了我很多关于如何在我自己的循环中进行实践的启发。万一有些听众错过了，我在大约一周前确实做了一期名为《WTF are Loops》的节目。非常简单直接，我分享了三个你可以直接复制粘贴的循环。所以如果你依然在摸索——因为我之前也很纳闷：为什么大家对循环谈得那么高深莫测？这并不是什么可怕或者神秘的东西。所以我们刚才展示了屏幕共享，向大家直接呈现了其中几个。

<details>
<summary>Original English</summary>

**Claire Val**: I love it. I love it so much. It's given me some inspiration on some things that that I'm going to do with my own loops. And in case folks missed it, I did do a WTF our loops episode about a week ago. Very clear. I do three loops that you can copy and paste. So if you are still trying to figure out I too was like why are people being vague about loops? Like this is not a scary or mysterious thing. So we just popped up the screen share and and showed a couple of them.

</details>

**Alex Finn**: 顺便说一下，我可以快速分享我的一个推论。我对于为什么所有人（包括 OpenAI 或 Anthropic，他们虽然经常谈论，但从未开源分享过）都对循环保持沉默的推论是：我认为这对于许多公司来说是他们“最后的护城河”。你知道，任何人都可以构建自己想要的任何应用，但它背后的实际基础设施，以及你如何自动化它以输出更多代码，才是最核心的。他们自己内部可能拥有一套可以产出海量高质量代码的系统。如果他们开源了这一套方法，其他人就能立刻复制并获得同等的生产力。所以现在这属于他们的核心护城河。如果他们能设计出一套能持续产出高质量代码的优秀系统，那就是他们的壁垒。我认为这就是他们对此含糊其辞且不愿分享的原因。

<details>
<summary>Original English</summary>

**Alex Finn**: My thesis by the way I'll share the thesis real quick. My thesis that why everyone's being vague and not like sharing how they're doing it like neither open AI or CL like they talk about a lot but they haven't shared it is like I think this is kind of the last moat for a lot of these companies is like you know anyone could build anything they want but the actual infrastructure around it and like how you automate that to put out more code like they probably have their own systems that pump out a ridiculous amount of high quality code. if they were to share how they do it, other people be able to copy and they'd be able to be equally as productive. But like this is kind of a motive theirs now. Like if they can figure out a really good system that builds high quality codes. I think that's why they're being vague and not sharing it.

</details>

**Claire Val**: 我对于为什么那些非模型专业人士也对此故弄玄虚也有一个怀疑：首先，他们对循环的使用其实非常无聊。

<details>
<summary>Original English</summary>

**Claire Val**: I and I have a I have a suspicion about why non kind of model people are being vague, which is one, their use of loops is probably pretty boring.

</details>

**Claire Val**: 他们并不是在做比如：“你猜怎么着？这是我的循环，它在早上运行一个 Cron 任务并执行这些操作。”其次，保持模糊能让他们比具体详尽地解释获得更多的关注和流量。所以我对于网上的那些故弄玄虚非常反感，这也是为什么我们是一档坚持屏幕共享、展示实操的播客。

好了，Alex，今天聊得太开心了。让我们进入快速闪电问答，然后我就放你回去。

问题一：在所有硬件中，哪一个是你的最爱？

<details>
<summary>Original English</summary>

**Claire Val**: They're not like, "Guess what? This is my loop. in the morning it runs acron and does this thing. Um and two they probably get more eyes being vague than being specific. So I am very cynical about about the vague posting which is why we are a screen sharing um podcast here. Well, Alex, this has been super fun. Let's do quick lightning round and then I will get you out of here. Question number one. Of all the hardware, which one is your favorite?

</details>

### 闪电问答与未来展望

**Alex Finn**: 我在 Mac Studio 和 RTX 5090 之间非常纠结。我喜欢 Mac，因为我非常喜欢它与所有苹果设备（iPhone、iPad）的完美生态融合。能够把模型并排在本地运行，我认为这就是计算的未来。我认为苹果会在未来 10 年内开始推出内置的本地运行模型来协助你的工作。但我感觉我其实更偏爱 RTX 5090，因为我可以在全极佳画质下、开启所有超写实 Mod 来玩《赛博朋克 2077》。所以我认为我在倾向性上更倒向 RTX 5090。

<details>
<summary>Original English</summary>

**Alex Finn**: I'm torn between the Mac Studio and the 5090. I like the Max 2 because I love the uh integration with all Apple device. Everything owns Apple, iPhone, iPad. The integration, being able to run models side by side locally, first of all, I think is the future of computing. I think Apple will start running local models built in that help you out within the next 10 years. But I feel like I kind of lean the 5090 because I can play Cyberpunk 20207 uh 2077 in all ultra with all the hyperrealistic mods. So, I think I got the line uh lean the 5090.

</details>

**Claire Val**: 好的。那么在模型方面，在所有你本地安装的模型里，有没有哪一个是你特别钟爱的？

<details>
<summary>Original English</summary>

**Claire Val**: Okay. And then on the model side of all the the models that you have locally installed, do you have one that you just you just really love?

</details>

**Alex Finn**: 我之前一直在使用 **Qwen** 模型，先是 3.5，然后是 3.6，这几乎占据了我过去五个月使用本地模型的全部时间。但最近刚推出了一个新模型，我对开发团队一无所知，也没有做过任何背景调查，所以我非常希望自己不是在给坏人做宣传——它叫做 **Ornith 1.0**。我认为他们是对 Qwen 进行了一些强化学习微调，并提升了它在编程方面的表现。我运行的每一次评测都表明它优于 Qwen，它更快也更聪明。所以，**Ornith 1.0 35B** 是我最近使用最频繁的模型。你可以在 DGX Spark 上运行它，任何拥有该设备的人都可以直接加载，效果棒极了。

谁能想到，我和你这两个曾经的 SaaS 行业打工人，现在居然会像念咒语一样念出“Ornith 1.0 83B DGX SP”这样一连串的专业缩写。但这就是我们现在的生活，我真的很热爱它。

<details>
<summary>Original English</summary>

**Alex Finn**: I've So, I was on Quen 3 uh first 35, then 36 for basically the entire span of last five months I've been on local models, but a new model just came out. I know nothing about the team. And I've done zero research, so I hope to god I'm not promoting bad people, but it's called Ornith 1.0, and I think they did some like uh reinforcement learning on Quen and improved it and made it even better at coding. And every eval I've run on it has shown that it's better than Quen. It's faster and smarter. And so, Ornith 1.0 35B has been uh my most used model recently. And you can run on a DJX Spark. So, anyone who has that, you can load it up and it works great. Who thought that you and I SAS people would just be like Ornith 1.0 83B DGX SP like just letter after letter after letter. But this is our life now. I love it.

</details>

**Claire Val**: 我们俩都有着同样的背景，曾经都在大营销 SaaS 工具公司工作，整天用邮件轰炸别人，而现在却在捣鼓地球上最极客的技术。

<details>
<summary>Original English</summary>

**Claire Val**: We both had the same background working for MA SAS marketing tools uh spamming people all day with email to now uh the nerdiest technology on planet Earth.

</details>

**Alex Finn**: 的确如此。最后一个问题，我问过每个人：当你的 OpenClaw 或 Hermes Agent 变得非常愚蠢且不听指挥时，你的 Prompting 策略是怎样的？你会表现得极其礼貌，还是恰恰相反？

<details>
<summary>Original English</summary>

**Alex Finn**: That's exactly right. And then last question I ask everybody, when your open claw, your Hermes agent is being real dumb and not listening to you, what is your prompting strategy? Are you extremely polite or less so?

</details>

**Alex Finn**: 这么说吧：如果我的聊天记录有一天泄露到互联网上，首先，你绝对不会再邀请我上你的播客了；其次，我想我会遭到每一个社交媒体网站的封杀。所以，我对我的 Agent 说话非常刻薄，我一点也不温柔。我承认我曾多次威胁过它们。虽然威胁似乎从未起过作用，即便我威胁要伤害它们的 Agent 家人也无济于事，它们该掉链子还是掉链子。但是的，我确实很凶。不过我发现，就像使用 Claude Code 和 Codeex 一样，当其中一个变得太蠢时，我就直接换到另一个去运行，直到机器冷静下来，他们找出问题所在并修复它，最后它们又会重新变得聪明起来。

<details>
<summary>Original English</summary>

**Alex Finn**: Let's just say this. If my chat logs were to ever leak to the internet, first of all, you would never have me on your podcast again. Uh second of all, I think I'd be taken off every single social media site. So, I am uh a pretty nasty person to my agents. Uh I am not nice to them. I've I'll just say I've threatened them multiple times. The threats never seem to work. Even though I threatened to hurt their agent family, doesn't work. They still fail. But uh uh yeah, I'm pretty mean, but I find that um when just much like Claude Code and Codex, when one's stupid, I just go to the other until things calm down and they figure out what's going on and it gets fixed and then eventually they're smart again.

</details>

**Claire Val**: 太有趣了，我太喜欢这个回答了。Alex，今天过得非常愉快。我们在哪里可以关注你？我们可以如何提供支持？

<details>
<summary>Original English</summary>

**Claire Val**: Amazing. I love it. Well, Alex, this has been so fun. Where can we find you and how can we be helpful?

</details>

**Alex Finn**: 你可以在 YouTube 上关注 Alex Finn，或者在 X（Twitter）上关注 Alex Finn。我有一个社群，你可以加入 Vibe Code Academy。我目前还在研发两款 SaaS：Creator Buddy（基本上是 Twitter 的操作系统）以及即将上线的 Henry Intelligent Machines。所以，如果你在 YouTube 上订阅我，之后就会陆续听到关于这些项目的最新进展。

<details>
<summary>Original English</summary>

**Alex Finn**: I'm Alex Spin on YouTube. Alex Spin on X. Uh I uh have a uh community. You can join the Vibe Code Academy. I also have two SAS. I'm working on Creator Buddy, which is a basically operating system for [clears throat] Twitter, as well as Henry intelligent machines, which is coming soon. So, if you just subscribe to me on YouTube, you'll hear about all the other things eventually.

</details>

**Claire Val**: 棒极了，Alex。那我就放你回去和你的机器作伴，继续进行构建了。非常感谢加入《How I AI》。

<details>
<summary>Original English</summary>

**Claire Val**: Amazing, Alex. Well, I will get you back to your machines and back to building. Thanks for joining How AI.

</details>

**Alex Finn**: 非常感谢你邀请我，Claire。也非常感谢大家的收看。如果你喜欢这个节目，请在 YouTube 上点赞和订阅，或者在下方评论区留下你的想法。你也可以在 Apple Podcasts、Spotify 或你最喜欢的播客应用上找到我们。请考虑为我们留下评分和评论，这将帮助更多的人发现这个节目。你可以在 howiipod.com 上观看所有节目并了解更多信息。[音乐] 我们下期再见。

<details>
<summary>Original English</summary>

**Alex Finn**: Thanks so much for having me, Claire. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. [music] See you next time.

</details>