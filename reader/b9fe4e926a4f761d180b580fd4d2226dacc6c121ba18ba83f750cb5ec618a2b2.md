---
author: The Pragmatic Engineer
date: '2026-08-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=8xBJPa_480Q
speaker: The Pragmatic Engineer
tags:
  - performance-optimization
  - assembly-language
  - premature-optimization
  - software-architecture
  - knowledge-acquisition
title: 关于软件优化误区、性能关注与工程实践的深度探讨
summary: 文章探讨了软件优化中的常见误区，指出过度优化可能成为逃避性能思考的借口。核心观点包括对性能的关注、学习底层语言（如汇编）的重要性，以及在游戏开发模式与传统软件工程模式上的对比。同时，文章也讨论了在职业发展中，如何看待AI工具的使用，并推荐通过阅读学术论文来获取知识的有效方法。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/16 -->

### 关于优化的误区与开场介绍

**Casey Muratori**：关于如何进行优化，人们存在一个误区。你运行性能分析，找出开销大的部分，做一些修改，然后测量统计数据。我和许多非常优秀的优化专家共事过，但他们并不是这么做的。

<details>
<summary>Original English</summary>

**Casey Muratori**: There's a misconception about the way you approach optimization. You run a profile, you identify the big parts, you make some changes, you measure statistics. I've worked with many extremely good optimization people and that is not how it is done.

</details>

**Host**：汇编语言并没有那么复杂，对吧？

<details>
<summary>Original English</summary>

**Host**: Assembly language is not all that complicated, right?

</details>

**Casey Muratori**：所有的 JavaScript 库、DOM、CSS、React、汇编语言，你总共可能只需要学习 20 到 30 条指令。如果你能在 HTML 中垂直居中一个 div，那么我敢说你大概也能学会汇编语言。

<details>
<summary>Original English</summary>

**Casey Muratori**: All of the JavaScript libraries, the DOM, CSS, React, assembly language, maybe there's 20, 30 instructions you might have to learn total. If you can vertically center a div in HTML, then you can probably learn assembly language, I would say.

</details>

**Host**：如果你有在使用 AI 工具的话，你是如何使用它们的？

<details>
<summary>Original English</summary>

**Host**: How are you using AI tools, if you're using them at all?

</details>

**Casey Muratori**：我们完全没有在使用。我想在游戏中亲自编程的原因，就是因为我想编程。如果我只是想让 AI 来写代码，我干脆去用 Unreal（虚幻）引擎好了 [笑]。

<details>
<summary>Original English</summary>

**Casey Muratori**: We are not using them at all. The reason that I want to program things in a game is because I want to program them. If I just wanted an AI to program them, I'd just go get the Unreal [laughter] Engine.

</details>

**Host**：你认为要成为一名伟大的软件工程师，有哪些是不可妥协的特质？

<details>
<summary>Original English</summary>

**Host**: What are things that you think are non-negotiable for someone to be a great software engineer?

</details>

**Casey Muratori**：我发现有很多公认的编程经验完全是无稽之谈。很明显，从来没有人去验证过它。所以，要想让它成为公认的智慧，你应该……

<details>
<summary>Original English</summary>

**Casey Muratori**: So, I find there's a lot of received programming wisdom that's just nonsense. Clearly, no one's ever tested it. And so in order for it to be received wisdom, you should

</details>

### 播客引言与赞助商信息

**Host**：为什么大多数开发者不关心编写高性能软件？我们应该关心吗？今天的嘉宾 Casey Muratori 在过去十年里一直在主张我们应该关心。他还说，现有的大多数软件的运行速度比它应该达到的速度慢了数十倍到上百倍。[音乐] 今天我们将讨论为什么在整个行业中，对性能的关注退居次要地位，以及为什么 Casey 认为这种趋势终于在发生转变。如果你对编写高性能代码是认真的，为什么你会想要学习阅读汇编语言，以及为什么它听起来并没有那么可怕。“过早的优化是万恶之源”这句话，为什么 Casey 认为大多数人只是用它来逃避在真正应该考虑性能时去思考性能，此外还有很多其他话题。如果你想提升自己，编写出更快的软件 [音乐]，并在此过程中成为一名更好的工程师，那么这一集就是为你准备的。如果你是给 Ryan 的那篇帖子点赞、要求这一集多聊编程少聊 AI 的人之一，那么这一集也是为你准备的。

<details>
<summary>Original English</summary>

**Host**: Why do most devs not care about writing performance software and should we? Today's guest Casey Moratory spent the last decade arguing that we should. He also says that most software out there runs tens to 100 times slower than it needs to. [music] Today we discuss why the focus on performance took a backseat across the industry and why Casey thinks the tide is finally turning. why you'll want to learn reading assembly if you're serious about high performance code and why it's less scary than it sounds. The saying premature optimization is the root of all evil, why Casey says that the majority of people use it to avoid thinking about performance when they really should and many more. If you want to get better at writing faster software [music] and become a better engineer while doing so, then this episode is for you. And if you're one of the people who hit a like on this post by Ryan asking for this episode to be more about programming than about AI, this episode is also for you.

</details>

**Host**：本集由 Antithesis 赞助播出。如果你从事与智能体（agents）相关的工作，你的工作就不再仅仅是编写代码。还包括对其进行规范和测试。[音乐] Antithesis 是当今验证智能体代码最有效的方法。

<details>
<summary>Original English</summary>

**Host**: This episode is presented by antithesis. If you work with agents, your job is no longer just writing code. It's also specifying and testing it. [music] Antithesis is the most effective method of verifying agentic code today.

</details>

**Host**：本集也由 Sentry 为您带来。你大概已经知道 Sentry 是什么了，因为你是一名开发者。如果不知道，随便问个开发者，他们会告诉你的。我用 Cry 来监控 Pragmatic 引擎后端的所有事件和错误。当然，Sentry 不仅处理错误。他们还提供日志、回放、跨度（spans）、性能分析、指标等等，因为它们都连接到同一个追踪链路。Sentry 有个我非常喜欢的新功能，那就是它修复错误的能力。让我给你展示一下。这是我的管理后台上的一组错误列表。有一个最近发生在 O 上的错误，我想检查一下。让我们让 Seir 为我们运行自动修复。Seir 是 Sentry 的 AI 调试工具。首先，它会生成根本原因分析。它发现了一些 HTTP 和 HTTPS URL 的问题。很好。现在我们知道出了什么问题，Seir 可以创建一个关于如何着手修复它的计划。我可以去编辑这个计划，但我对它很满意。所以，让我们创建实际的代码修复。这是 Seir 生成的代码修复方案。假设它看起来不错，而在我的例子中，确实不错。让我们起草一个合并请求（PR）。砰的一下，PR 就创建好了，准备合并。我喜欢 Autofix 的一点是，Senu 如何从在我的应用程序中显示一个错误列表，到为我提供一个快速的方法来修复它并形成闭环，而我在此期间始终掌控着这个错误修复的过程。调试变得快得多，也容易得多。访问 centry.io/pragmatic io/pragmatic 了解 Sentry，今天就开始检测错误、诊断根本原因，并修复问题和退化（regressions）吧。

<details>
<summary>Original English</summary>

**Host**: This episode is brought to you by Sentry. You probably already know what Sentry is because you're a developer. If not, just ask a dev and they'll tell you. I use Cry to monitor the back end of the pragmatic engine for any and all events and errors. Of course, Sentry doesn't only do errors. They also have logs, replays, spans, profiles, metrics, and more because they're all connected to the same trace. One new capability Sentry has I'm really liking is its ability to fix errors. Let me show you. Here's a list of errors on my admin back end. There's a recent error on O that I want to check out. Let's have Seir run an autofix for us. Seir is Century's AI debugging tool. First, it generates a root cause analysis. It's finding some problem with HTTP versus HTTPS URLs. Cool. Now that we know what's going wrong, Seir can create a plan on how to go about fixing it. I could go and edit this plan, but I'm happy with it. So, let's create the actual code fix. Here's a code fix that Seir generated. Assuming it looks good, and in my case, it does. Let's draft the pull request. And boom, the PR is created, ready to merge. What I love about Autofix is how Senu went from showing a list of errors inside my application to offering me a fast way to fix it and close the loop while I stay in charge of this bug fix the whole time. Debugging got a whole lot faster and a whole lot easier. Check out Sentry at centry.io/pragmatic io/pragmatic and start detecting errors, diagnosing your root causes, and fixing issues and regressions today.

</details>

### Casey 的早期编程经历

**Host**：好了，Casey，欢迎来到播客。很高兴你能来这里。

<details>
<summary>Original English</summary>

**Host**: All right, Casey, welcome to the podcast. It's so nice to have you here.

</details>

**Casey Muratori**：非常感谢。很高兴来到这里。感谢你们的邀请。

<details>
<summary>Original English</summary>

**Casey Muratori**: Thank you so much. It's great to be here. Thank you for the invitation.

</details>

**Host**：现在，我想回到最初的时候。你是如何进入科技、编程、计算机领域的？

<details>
<summary>Original English</summary>

**Host**: Now, I want to go back when we start to the beginning. How did you get into tech programming, computers?

</details>

**Casey Muratori**：嗯，我想接触计算机的话，是在非常非常早的时候。我的父亲曾是数字设备公司（Digital Equipment Corporation）的一名程序员，如果你研究过计算机历史，肯定知道这家公司，但如果只看当今的科技格局，你可能就不太了解了。他们已经完全消失了，对吧？呃，他们后来被吸收了，我想一部分被英特尔（Intel）吸收，另一部分被康柏（Compaq）吸收了。当时，你知道，他们算是被分拆了。在那个时代，这是一家非常大的计算机制造商。你知道，像 PDP11 这样的计算机，那就是数字设备公司的计算机。还有 VAX 之类的，你可能在计算机历史里听说过这些东西。

<details>
<summary>Original English</summary>

**Casey Muratori**: Well, I guess computers, it's like very very early on. Um, my dad was a programmer at Digital Equipment Corporation, which is a company that people will know if they studied computer history, but would not know if you just looked at the landscape today. They're they're completely gone, right? Uh, they got absorbed partly by Intel, partly by Compact, I think. Uh, there was, you know, they kind of got uh, broken up. At that time, it was kind of a really big computer manufacturer. You know, computers like the PDP11, that's a digital equipment corporation computer. uh the vax like things that you may have heard of in computers.

</details>

**Host**：哦，这些都是那种巨型的大型机。

<details>
<summary>Original English</summary>

**Host**: Oh, these were these ma massive main frames.

</details>

**Casey Muratori**：是的。还有小型机。所以有时也像比大型机更小的那种，算是下一级的产品，对吧？总的来说在那个时代，我父亲在那里做程序员。后来他去了英特尔，因为，你知道，就像我说的，有些部门被收购了。他实际上从未离开过他的工作岗位。他只是由于 Digital 最终的倒闭而到了英特尔。但也正因为如此，我们家里总是有计算机，尽管在那个年代，你知道，这可能有些不同寻常。嗯，你知道，我在七岁时就学会了编程，那大概是在，你知道，1982 年左右吧。所以那时候，或许你家里会有一台 Apple 或 Commodore 之类的早期计算机。我不记得那些电脑具体的发布日期了，但大多数人是没有的。直到晚一点的时候才普及，而且更重要的是，你家里大概率不会有一个能教你编程的程序员，对吧？所以，呃，所以我很早就学会了编程，也就是在那时我接触了计算机。至于我是怎么进入游戏行业的，是因为我后来偶然去了微软实习，在那里结识了一些人，然后通过他们，我就有点算是进入了游戏行业。如果这听得懂的话，事情就是这样发生的。

<details>
<summary>Original English</summary>

**Casey Muratori**: Yeah. Uh mini computers as well. So like smaller also sometimes than main frames like the kind of next step down, right? And so in general that that era, my dad was a programmer there. He would later end up at Intel because, you know, like I said, parts got acquired. He never actually left his job. He just ended up at Intel through kind of uh digital's eventual demise. But as a result, we always had computers at home, even though at that time, you know, that might have been a little bit odd. Um, you know, I I learned to program when I was seven, which would have been in like, you know, 1982 or something like that. And so at that time, you know, maybe you might have an Apple or Commodore kind of computer at home, like some kind of early computer. I don't remember the exact line dates of those computers, but most people didn't. And it was only until a little bit later that you would and you probably wouldn't have had a programmer in your household to teach you more importantly, right? So, uh, so I learned really early on and that's when I got into computers. How I got into games was, uh, I ended up randomly interning at Microsoft and I met people there and like I went and, you know, sort of went off into games through them. That was that was how that happened if that makes sense.

</details>

### Windows 游戏生态的起步

**Host**：等等，微软和游戏之间的关系是怎样的？这并不是理所当然的，对吧？微软并不是……他们 [笑] 就只有一款游戏，对吧？就是《飞行模拟器》（Flight Simulator）。

<details>
<summary>Original English</summary>

**Host**: But wait, how is the Microsoft/game relationship? That's not kind of a given, right? Microsoft is not They [laughter] have one game, right? It's Flight Simulator.

</details>

**Casey Muratori**：呃，是的，在那个时候，这会非常奇怪。呃，这件事之所以发生，是因为一个叫 Chris Hecker 的人。呃，很多人并不太了解他的历史，因为将游戏引入 Microsoft Windows 有两次浪潮。嗯，因为，我的意思是现在想起来觉得很好笑，因为现在人们会想：如果你有一台 PC，你会用什么平台玩游戏？你知道，Windows 就像是默认选项。Linux 现在算是这一领域的挑战者。但 Windows 仍是默认。所以你就会想，这是怎么变成这样的？因为，你知道，呃，在早年间情况并非如此。呃，Microsoft Windows 并不是一个游戏平台。上面几乎什么都没有。就只有像纸牌和扫雷之类的少数几款游戏。

<details>
<summary>Original English</summary>

**Casey Muratori**: Uh yes, at that time it would it would have been very weird. Uh the reason that happened was a guy called Chris Hecker who uh a lot of people don't really know his history because there was sort of two waves of bringing games to Microsoft Windows. Um cuz I mean now it's it's funny to think about now because people think of like what platform are you going to play games on if you have a PC? You know, Windows is like the default. Linux is now an insurgent to that. But Windows is the default. And so you think about how did that happen? Be you know uh because that wasn't the case if you were back in the early days. Uh Microsoft Windows not a gaming platform. It's almost nothing on it. It's like solitire and mind sweeper and a few other uh sort of games.

</details>

**Host**：那是怎么发生的呢？

<details>
<summary>Original English</summary>

**Host**: How did it happen?

</details>

**Casey Muratori**：所以，呃，发生这件事的原因……这有点涉及到一个技术层面的原因。原因在于，当时要想快速生成可以显示在屏幕上的图像非常困难。要理解为什么会这样，这本身就像是一个独立的话题，但总体来说，你可以想象你正在运行着这个操作系统，也就是 Microsoft Windows。它控制着显卡。它通常以相当高的分辨率运行，呃，与游戏想要运行的分辨率相比。你必须跟它协商，以便以某种方式显示你的位图（bitmap），而不会破坏它试图显示的所有其他东西。诸如此类。早期版本的 Windows，呃，直到像 Windows，呃，3 系列，呃，比如我们说的 Windows for Workgroups，如果还有人记得这个名字的话。

<details>
<summary>Original English</summary>

**Casey Muratori**: So uh what happened the reason for this this kind of gets into a technological reason. The reason for this is that it was very hard to actually produce images that could be displayed on the screen quickly. And to understand why this is is like its own kind of topic, but in general, you can just imagine you have these this operating system running, which is Microsoft Windows. It's controlling the graphics card. It's often running at a fairly high resolution uh compared to what a game might want to run at. You have to negotiate with it in order to display your bit map in some way that won't destroy all the things that it's trying to display. So on so forth. early versions of Windows uh up through like Windows uh three uh Windows for workg groupoups let's say if anyone remembers that name.

</details>

**Host**：那是 3.1 之后吗？

<details>
<summary>Original English</summary>

**Host**: Was it after 3.1?

</details>

**Casey Muratori**：我觉得应该叫 3.51，或者也可能只是 31。对，有 NT 3.51。不，所以我觉得你说得对。31、3.1，我不知道，差不多是这个。是的，Windows for Workgroups 呃，你知道大概就是那个时期的。那个版本的 Windows，也就是在 3 系列中，并没有一种方法可以真正利用 CPU 快速填充像素，而这恰好是游戏需要做的事，对吧？当时真的没有任何 GPU 加速。

<details>
<summary>Original English</summary>

**Casey Muratori**: It was 3.51 I think is what it's called or maybe just 31. Yeah, there's NT351. No, so it's like I think you're right. 31 3.1 I don't know something like this. Yeah, Windows for workg groupoups was uh you know around that time. that version of Windows, which is in the 3 series, didn't really have a way to quickly use the CPU to fill pixels, which is what games need to do, right? There's there's no GPU acceleration really at

</details>

<!-- chunk 2/16 -->

### Windows上游戏的起源与早期经历

**Speaker A**: 在这一点上，我们可以稍微谈谈，但这并非主流，也不在消费级领域。所以，他们需要能够做到这类事情。他们需要以双缓冲的方式进行，这样他们就可以在一个后备缓冲区（back buffer）进行绘制，然后再显示到屏幕上。这个过程必须非常快地发生。但是在Windows系统中，当时根本没有办法做到这一点。在Windows下，你不得不通过某个API，这个API会生成一种位图，而这种位图格式未必适合你正在使用的显示器，然后在显示时它还必须将这种位图转换为另一种格式。全都是这类繁琐的操作。所以像《毁灭战士》（Doom）这样的Windows游戏，当时根本不会登陆Windows平台，对吧？那种未来图景在当时的Windows计划中并不存在。而微软内部的一些人正是想改变这种状况。推动这一改变的人之一，是一个名叫Chris Hecker的家伙。他当时的逻辑是：“好吧，我们其实可以直接开发一个库，能够快速地将数据块传送到屏幕上（fast blit），这样我们就有一种方法，让人们可以执行这些绘制操作并足够快地将其显示在屏幕上，从而让在Windows上玩游戏成为可能。它能做到像在DOS系统中百分之百那么快吗？”可能不行。但是，你到底能不能运行一些当时的新游戏呢？要知道，我想《德军总部3D》（Wolfenstein 3D）在那个时候应该已经面世了。《毁灭战士》也快要问世了，诸如此类，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: this point. We there's a little bit we could talk about, but it's not mainstream. It's not in consumer. So, they they need to be able to to do this sort of thing. They need to be do it in a double buffered way so they can draw to a back buffer and then show it to the screen. And that has to happen very quickly. And there just wasn't a way to do this in Windows. In Windows, you had to kind of go through uh this API where you would produce sort of a bit map that wasn't necessarily in the right format for the display you were using and then it had to do a translation from that bit map to the other one when it displayed it. All this sort of stuff. So games on Windows like things like Doom, they're not coming to Windows, right? Uh that kind of future was not in the works uh for Windows. And that was kind of what some people in Microsoft wanted to change. And one of the people who brought this change about was a guy named Chris Hecker. and he was like, "Okay, we could actually just make a library that did the fast blitz to the screen so that we could have a way that people could do these draws and get them on the screen quick enough to make gaming viable. Would it be 100% as fast as DOSs?" Probably not. But could you actually run uh you know, some of these new games? You know, Wolfenstein 3D I think would have been out at this time. Doom was kind of on the horizon and that sort of thing, right?

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 所以，他开启了这个本不该由他负责的项目。他并没有获得授权去做这个名为WinG的项目，我猜这个名字至少代表着“Windows Graphics”或者类似的意思。这完全是一个臭鼬工厂项目（即秘密研发项目）。他得到了他经理的掩护。我想我现在应该可以把这些事情全说出来了，因为这已经是陈年旧史了。他有他经理的掩护，那个人的名字叫Michael Edwards。Michael Edwards基本上就是在为这件事打掩护，因为这事儿很可能根本行不通，原因是他们当时所在的部门大致相当于今天的微软研究院。当时叫作高级技术部门（Advanced Technology），是微软研究院的前身。在那个部门，你们根本不应该去为Windows发布核心库，这完全不搭界。长话短说，最终的结果是，那个产品确实发布了。WinG，我想你可能不该叫它产品。它是Windows的一个附加组件。它发布了，并且这是迈向DirectX的第一步。人们常常忘记WinG才是实现这一目标的最初方式，然后最终我们才有了DirectX、DIB sections、Windows 95，以及所有那些东西。有趣的是，当我去微软实习时，我本应向其汇报的人正是Michael Edwards。在我第一天去报到的时候，和另外几个实习生一起——其中一个叫Rudy，另一个叫Rajie——我们原本都要向他汇报工作，对吧？因为通常一个经理手下会带几个实习生。我们到了那儿，在参加了那种你们懂得、一如既往无聊的愚蠢的人力资源入职培训之后，我们就被人拉到了一边。我记不清当时他们原话怎么说的了，大概就是：“听着，稍微出了一点状况。面试你们并且你们原本要向他汇报的那个人，呃，他们不在这里。”我记不清他们具体怎么措辞的了。“所以呢，你们去跟另外那个人谈谈，他们会给你们安排点事情做的。”结果发现，WinG那件事情在前一周搞砸爆发了，Mike Edwards气冲冲地离开了大楼，从那以后就再也没人见过他。这可是真事。[笑声] 所以，这就是我初到微软时的遭遇，那个我本应跟着他实习的人，他直接爆发然后走人了。没人知道他什么时候会回来。在我到了大概一周后，他确实回来了。呃，但他被调到了另一个部门。就像，你要知道那里当时进行了大量类似“故障分诊”的善后工作，试图弄清楚到底发生了什么。所以，那就是我的亲身经历，不过可以说，这意味着我恰好处于Windows游戏发展的某种“归零地”或者说最核心的起点。因此，我遇见了Chris Hecker。我有机会与那里的许多人交谈。他甚至带我去见了我童年时代的英雄之一Ron Gilbert，也就是开发了SCUMM引擎的那个人。是的。他认识所有这些家伙，因为在开发WinG的过程中，他出去拜访了一堆游戏开发者，并与他们合作诸如此类的事情。所以，我得以去了Humongous Entertainment，那是Ron新成立的公司。他给了我一个《猴岛小英雄》（The Secret of Monkey Island）的鼠标垫，我还记得。呃，总之，那真的非常酷。而我最终也是通过Chris Hecker进入了游戏行业的。他在让游戏登陆Windows的过程中，算得上是一位无名英雄，因为，你知道，他并没有四处宣扬自己的故事，但是，我想现在由我来说出这些了。

<details>
<summary>Original English</summary>

**Speaker A**: And so he started this project that he was not supposed to do. He did not have the authority to do this called wing, which I believe at least stand for like win graphics or something like that. Total skunk works project. He had cover from his manager. I'm I'm assuming I can say all this stuff now because it's ancient history. He had cover from his manager. His name guy's name was Michael Edwards. And Michael Edwards basically just kind of ran cover for this, which is a thing that probably wasn't going to fly because they were in a division at that time which would have been Microsoft Research today kind of. It was called at Advanced Technology was the early version of Microsoft Research. You were not supposed to be shipping core libraries for Windows like it had nothing to do with that. Long story long, what ended up happening is that product did ship. Win, I guess you wouldn't call it a product. It's an add-on for Windows. did ship and it was the first step towards DirectX. Uh people forget that Wing was the first way you did this and then eventually we had DirectX and DIB sections and Win 95 and all that sort of stuff. When I went to Microsoft, amusingly the person I was supposed to be reporting to as an intern was Michael Edwards. When I showed up first day along with the other interns, uh guy named Rudy, a guy named Rajie, uh we were all supposed to report to him, right? because you get a couple interns in under one, you know, sort of manager. We show up and we're just taken aside, you know, after some kind of, you know, stupid HR orientation thing that was, you know, lame as it always is. And and we get taken aside by somebody. I don't remember the lyrics. They're like, "Look, bit of bit of a problem. Uh the person you interviewed with and were supposed to like report to, uh they they aren't here. Like I don't remember exactly how they put it. So, uh, you're going to go talk to this other guy and they'll find something for you to do." Turns out the wind thing had blown up the previous week and Mike Edwards had stormed out of the building and had not been seen since. That is what actually happened. [laughter] So, that's I arrive at Microsoft, the person I'm supposed to intern with, he just he just flamed out and left. No one knows when he'll be back. He did end up coming back like a week after I got there. Uh, but he was kind of moved over to a different division. like they you know there was a bunch of like triage work done there to figure out what's going on. So that that was my experience but suffice to say it meant that I was right in sort of like ground zero of games on Windows. So I met Chris Hecker. I got to talk to a bunch of people there. He actually took me out to see one of my childhood heroes Ron Gilbert who is the guy who did the scum engine. Yeah. He knew all these guys because working on WG he had gone out to see a bunch of game developers and like work with them and this sort of thing. So, I got to go to Humongous Entertainment, which was Ron's new company. He gave me a a secret of Monkey Island, uh, mouse mouse pad, I remember. Uh, so anyway, it was it was really cool. And that's how I ended up getting into the game industry was was was through Chris Hecker. And he's kind of of an unsung hero of getting games on Windows because, you know, he he just he wasn't out there making his story known, but but, you know, I am now, I guess.

</details>

### DirectX的推动与后续的职业发展

**Speaker B**: 但能听到这些故事真的是太有趣了。显然，我现在确信你可以分享这些了。你知道，有一段时间这可能只限于核心圈子内知晓，但事实是，你知道，当然了，DirectX取得了巨大的成功，并且正如大家所知，从我的视角来看，它是游戏在Windows上繁荣的一个巨大原因。但现在居然有这么一个人，他不在乎别人的看法，没问过任何人，只是凭着自己的想法去干，卷入了冲突和争吵，就这样强行推动了一个想法。

<details>
<summary>Original English</summary>

**Speaker B**: But it's it's so interesting to hear these stories. Obviously, now you can share it, I'm sure. you know, like for a while this would have been like only with within the inner circle, but the fact that you know, of course, DirectX was a huge success and and it it did like as far as you know, from my vantage point, huge reason why games are big on Windows, but now here's someone who just ignored wasn't asked anything, just was doing something, got into conflict, fights, and just like pushed an idea.

</details>

**Speaker A**: 情况比你想象的还要复杂，因为真正推动DirectX的核心人物其实有三位，我指的是在体制和机构层面去推动它。当然有成千上百的像Todd Laney这样的程序员做了极其重要的核心开发工作。如果没有像他这样的人，它永远都不可能发布。所以，我指的不是编程开发这一块，我说的是在体制架构层面。这些人是Angstrom和Alex St. John。我不记得他们谁是谁了，或者Angstrom当时是WinG项目的测试员。所以他也是从那个团队出来的。也就是说，DirectX起步时，其中一个核心成员就曾在WinG团队待过。所以这是一脉相承的。这甚至不是一次毫无关联的推动。因此，WinG确实是它的开端。然后，DirectX算是在获得了微软官方批准后，真正在一个组织架构中全面开花结果了，你知道，在那个时候，它在内部才真正变得有权势了。

<details>
<summary>Original English</summary>

**Speaker A**: It's more than you think because there were three people who really were the core people who pushed DirectX, meaning institutionally pushed it. There are tons of programmers like Todd Laney who did, you know, really important core work. It never would have shipped without people like him. So, not on the program side, I'm talking about institutional side. It's Angstrom and Alex St. John. I don't remember which one is either or Angstrom was the tester on Win. So he came from that team. So the start of DirectX, one of the core members of DirectX was on the Windy team. So it's a direct lineage. It's not even like an unrelated push. So WGI really was the start of it. And then DirectX was kind of the actual full blossoming into an org with Microsoft's blessing at that point, you know, that that actually became powerful internally.

</details>

**Speaker B**: 那么在结束了这次微软实习，并接触了所有这些人之后，你实际上去开发了游戏工具，然后你还创办了自己的工作室，对吧？那么，这一切是怎么一步步发生的呢？

<details>
<summary>Original English</summary>

**Speaker B**: And then after after this Microsoft internship and getting exposed to all these folks, you actually went and and built games tooling, you then started your own studio as well, right? So like how how did that sequence?

</details>

**Speaker A**: 我想这中间有几个阶段。我和Chris Hecker在一家初创公司工作过，但那家公司最后并没有做出什么有趣的东西。之后我去了Gas Powered Games，那实际上可以说是微软的——我想他们不算微软的第一方工作室，但他们的发行协议是跟微软签的。呃，他们开发了一款名为《地牢围攻》（Dungeon Siege）的游戏，这款游戏，你知道，我不知道它算不算特别有名。从那里离开后，我去了Rad Game Tools，在那儿我待了相当长的一段时间。呃，我开发了他们的角色动画系统，那是一个非常受欢迎的产品，最终被用在了许许多多的游戏里。甚至到今天它还在被使用，这让我非常惊讶。因为那个产品非常、非常……其实从2004年起我就没再碰过它了，[笑声] 但我想其他人维护了它，而且一些工作室刚好将其集成到了他们的系统里——因为你是可以获得源代码授权的。所以我猜有些工作室把它集成进了他们的管线后，就再也没有移除它。而且他们可能只是在不断地更新它，为了让它能继续按照他们想要的方式运行。总之，呃，那就是我在那里的工作。那之后我就一直保持独立开发者的身份了。我只是拥有一家叫Molly Rocket的公司，我们做各种各样的事情。我通过那家公司为别人做过一些外包工作。我们现在也在那里做像Substack一样的平台，在那上面提供教育材料。所以从那以后我就一直在做一些比较杂的事情。尽管我也做过一些和游戏相关的工作。

<details>
<summary>Original English</summary>

**Speaker A**: I guess there's a couple of steps in there. I worked at a startup with Chris Hecker that didn't end up doing anything interesting. Then I went to a company called Gaspowered Games, which was actually a Microsoft guess they're not a Microsoft studio, but their publishing deal with was Microsoft. and uh they did a game called Dungeon Siege which is kind of a you know I don't know it's not a particularly well-known title. From there I went to Rad Game Tools and that's where I stayed for quite some time. Uh I did their character animation system that was a very popular product that ended up getting used in in lots lots of games. It's still used to this day, much to my surprise. Uh because that's a very very I haven't worked on it since 2004, [laughter] but I guess other people had maintained it and some studios just kind of integrated into their you could get source licenses. So I guess some studios just integrated it into their pipelines and have never removed it. Uh and they just maybe keep updating it um to to keep it working the way that they want. So anyway, uh that's what I did there. And then afterwards I' I've been independent since then. I just have a company called Malle Rocket uh where we do various stuff. I've done you know contract work for for people through that. We now do like the Substack through that where we do educational materials. So I've kind of just done random stuff uh since then. Although I have done some work on games.

</details>

**Speaker B**: 我注意到你的工作清单上提到了《见证者》（The Witness）。

<details>
<summary>Original English</summary>

**Speaker B**: I noticed your checklist you were talking about the witness.

</details>

**Speaker A**: 呃，显然那是一款我实际参与过的具体的游戏作品，但这主要仅仅是因为那是一个非常大的项目，而且你也知道，我和John是朋友，所以我只是想在旁边帮点忙，写一些辅助性的代码。我做了一些有关移动机制的东西……

<details>
<summary>Original English</summary>

**Speaker A**: Uh obviously that one was an actual specific title that I worked on but that was that was mostly just because it was a very big project and I was you know I'm friends with John so I was just trying to do some helpful programming on the side. I did some stuff on how the movement

</details>

<!-- chunk 3/16 -->

### 关于未公布的游戏项目

**Speaker A**: ……起作用了。我觉得在游戏领域有一些我们可以解决的有趣问题。所以，那是一个做起来非常有趣的项目。

<details>
<summary>Original English</summary>

**Speaker A**: worked. I thought there were some interesting problems that we could solve there for games. And so that was a that was a really fun project to work on.

</details>

**Gerge**: 是的。然后如今你在你的 Substack 上做一些关于编程性能的教育内容。除了这个你还在忙些什么呢？

<details>
<summary>Original English</summary>

**Gerge**: Yeah. And then today you're you're doing educational stuff on a bunch of subprogramming performance on your substack. And what else are you busy with?

</details>

**Speaker A**: 我们其实有一个尚未公布的项目，它占据了我剩下的大部分时间[笑]，如果这说得通的话，毕竟剩下的时间并不总是那么多。嗯，我们希望不久后能公布它。但现在它还没有完全准备好。相信我，一旦我们有正式的公告，我会立刻给你发邮件。不过，鉴于这对我们来说像是在挤时间做的事情，因为我们主要精力还是放在确保 Substack 的质量之类的事情上，在我们确信基本完成之前，我们打算尽量保持缄默。因为我们也不知道自己总共能投入多少时间，你能理解吧。

<details>
<summary>Original English</summary>

**Speaker A**: So we do actually have a an unannounced project that we've been working on uses up sort of the rest of the time [laughter] that that I have if that makes sense which is not always so much. um and that we will we're hoping to announce it sometime soon. Um but it it it's not quite out yet. Believe me, I will I will you will hereby I will send you an email as soon as we have an actual announcement. But uh given the fact that it is kind of like a split time sort of thing for us because we're pretty focused on making sure the substack is good and all that sort of stuff. We're we're trying to keep it fairly tight lipped until we actually know we're mostly done because we don't know how much time we can always devote to it if that makes sense.

</details>

**Gerge**: 是的。这也是游戏相关领域非常典型的做法，对吧？因为一些充分的理由，在有拿得出手的成果之前保持缄默。

<details>
<summary>Original English</summary>

**Gerge**: Yeah. No, it's it's it's it's pretty typical games related things, right? Like tight lipped until you have something for good reasons.

</details>

**Speaker A**: 嗯，有时候人们会采取另一种策略。他们会说：“听着，我们要从第一天起就大张旗鼓地宣传这件事，并试图围绕游戏的开发建立一个社区，诸如此类。”那也很好。这也是你可以选择的另一条路。但如果这不是你的全职工作，如果你还有其他责任，这种做法似乎就不太好了，对吧？因为你根本不知道自己实际上能投入多少时间，不是吗？

<details>
<summary>Original English</summary>

**Speaker A**: Well, sometimes people play the other game. They go like, "Look, we're going to day one we're going to be very loud about this and try to build a community around the development of the game and all that sort of stuff." And that's great. Uh so, you know, that's another route you can go. But if it's not your full-time thing, if you have, you know, other responsibilities, that doesn't seem great, right? because you you don't have any insight into how much time you will actually be able to devote to it, right?

</details>

### 为什么软件行业不重视性能？

**Gerge**: 是的。在 Substack 上，你的专栏叫 Computer Enhance，一开始你就是写性能相关的话题。我想这正是我们大概三年前开始交谈的契机，那时你已经有了这个 Substack，我们在私信里聊了起来。我记得你发信息问我：“嘿，Gerge，你觉得为什么在这个行业里，软件开发者们就是不太关注性能？”我记得你当时专门写了……

<details>
<summary>Original English</summary>

**Gerge**: Yeah. And on on Substack, it's called computer enhance and you started it with performance related topics and that's how we started to talk I think about three years ago when when you already had a Substack and we we had a direct message conversation. I remember you messaged me saying, "Hey, Gerge, why do you think in the industry people software developers just don't really focus on performance?" I I think you specifically wrote

</details>

**Speaker A**: 我确实写了。

<details>
<summary>Original English</summary>

**Speaker A**: I did

</details>

**Gerge**: 呃，你当时在说人们对性能缺乏重视。即使似乎有压倒性的证据表明，性能对大多数软件的商业底线（bottom line）至关重要。我想问你，我们在这个问题上曾有过很好的交流，实际上我想我一开始对你说的是，哦，这就是为什么你在构建——我不知道——分布式系统之类的时候不需要关心性能，但从那以后你学到了什么？为什么大多数开发者不关心，甚至大多数公司、团队、工程团队都不那么关心性能？

<details>
<summary>Original English</summary>

**Gerge**: uh you were saying how there's there's little emphasis on performance. There's even though there seems to be overwhelming evidence that performance is critical to the bottom line of of most software and I wanted to ask you we we've had a good back and forth on this and actually I think initially I told you like oh here's why you don't need to care about performance when you're building I don't know distributed systems or like but since then what have you learned? Why do most developers don't care or even most companies, teams, engineering teams not care about performance all that much?

</details>

**Speaker A**: 这是一个非常好的问题。而且我认为，如果我没记错的话，你当时的回答对于某些特定的行业领域来说确实是准确的，你大概是这么说的：“你看，你看到的很多这类软件，它的用户并不是购买者，对吧？”你当时的意思是，这就像是某种高管会去看的东西，他们会说我们需要管理 HR 的软件，他们会看这款软件的成本，会看软件的合规条款、法律责任等等，对吧？然后他们就会基于那张表格做出购买决定。他们才不会进去看看这软件是不是，你知道，是不是每次你想尝试访问某人的记录时都会卡顿 30 秒，对吧？我觉得这非常真实。不幸的是，许多企业级软件的现状可能就是这样。所以，也许某个普通用户确实会因为那款软件的性能而感到沮丧。我也确实经常听到人们抱怨他们使用的软件。但他们可能没有任何权力去改变它。我认为这是第一点。

第二点是，在很多情况下，你面临的仅仅是垄断效应。呃，你知道，人们目前不太可能去挑战现有的那些社交网络。举个例子，人们尝试过。但这非常困难。你知道的，Blue Sky 和 Threads 曾试图挑战 X，而且你知道，你还有 Facebook、Instagram 和 TikTok，它们基本上就占据了那些空间，对吧？因为这些网络效应，很难挤进那些领域。也许性能可以作为你试图挑战那些巨头时所提供方案的一部分。比如，“嘿，看看我们的产品响应速度比他们的快多少。”这可能是一个不错的加分项，但这不足以成事。如果你就这么出现，对于如何获得用户采纳没有计划，对于如何把大网红拉拢过来没有计划，诸如此类，单凭性能本身是无法在垄断领域卖出产品的，对吧？如果你谈论的仅仅是用户可以选择下载的独立应用，也许你还有机会。但这些应用在软件中的占比正在变得越来越小，对吧？而越来越大的一部分是那些你必须上去使用的垄断平台。所以我会说这是另一个原因。

第三点是，我认为现在人们开始更多地关注性能了。我认为在过去的十年里，包括我自己在内的许多人都在呼吁这是一个问题，而且这实际上产生了一些影响——我不认为那是在浪费时间。我看到了很多对性能的重新重视，人们在谈论性能，人们在发布各种东西的基准测试（benchmarks）。所以我实际上认为，第三点是，指出这个问题并呼吁这是我们应该做得更好的地方，似乎并没有完全白费力气。我确实看到情况开始有些好转。我也看到现在有人用基于性能的卖点来冲击主要的软件产品类别。比如 File Pilot 或者 Blick 视频编辑器，最近推出的这些产品都在传达：“哦，这是一款性能极高的软件，试图挑战该领域的现有巨头”，而且它们已经获得了一些吸引力。所以，我认为这也是一个非常好的迹象。

<details>
<summary>Original English</summary>

**Speaker A**: It's a really good question and I think I do think your answer at the time if I remember it correctly is certainly an accurate one for some subset of of industries uh which you know you said something along the lines of look a lot of these pieces of software that you're seeing the user isn't the purchaser right like you were you were like this is some kind of thing where you know somebody very high up is going to look and say we need software for managing HR they're going to look at the cost of the software they're going to look at the compliance terms terms of the software, the legal liability, whatever, right? And then they're just going to make a purchase decision on that sheet. They're not in there looking to see whether it takes like, you know, whether there's a 30-cond pause every time you want to try and access somebody's record, right? And I think that's very true. Like unfortunately, the situation for a lot of enterprise software probably is that way. So maybe an individual might well be upset about the performance of that software. And I certainly hear from people all the time who are upset about the software that they use. They might not be in any position to change it. I think that's one thing. 

There's thing two which is that in a lot of cases you simply have monopoly effects. Uh you know people aren't right now realistically going to challenge the social networks that currently exist. For example, people have tried. It's very hard. you know, Blue Sky and Threads have tried to assail X and you know, you've got Facebook and Instagram and Tik Tok and they kind of just own those spaces, right? And it's very hard to push into those because of these like network effects and maybe performance could be part of a package where you try to take on one of those players. like, hey, look at how much more responsive our thing is than theirs. Might be a nice plus, but that's not going to be sufficient. If you just show up with no plan for how you get adoption, no plan how you get big influences over there, all that sort of stuff, it can't sell a product on its own into a monopoly space, right? If you're just talking about apps that someone can choose to download, maybe you've got a shot there. But those are just they're forming a smaller and smaller subset of what software is, right? and this bigger and bigger subset is like these monopoly platforms you go on uh to to sort of work with. So I'd say that's another thing. 

Thing number three is I think now people sort of are caring about performance more. I think over the past decade uh the people uh including myself but many many other people who have been saying that this is a problem uh have actually had some effect like I don't think that it was a waste of time. I'm seeing a lot of new emphasis on performance, people talking about performance, people posting benchmarks on things. And so I actually think that the third thing is well actually it kind of does seem that pointing at this issue and saying this is something we should be doing better has not been completely uh a waste of time. I I do see things as sort of starting to turn around a little bit. I also see people attacking major product categories now with performance-based pitches. Things like File Pilot or the Blick video editor, like things like this that have been coming out lately where it's like, oh, really performant software to try to take on uh incumbents in a space and they've been getting traction. So, I think that's also a really good sign.

</details>

### 性能作为破局优势与性能基准

**Gerge**: 是的。我想在刚才说的最后一个类别中，开发者社区里一个非常好的例子就是 Bun 对比 npm。Bun 只是说：“好吧，我们比你快 10 倍、20 倍或 50 倍”，然后开发者们就会觉得：“什么？这可能吗？”然后事实确实如此。他们提出了这个看起来很夸张的声明。我甚至在想，你是不是必须得有这些听起来很离谱的声明，开发者才会开始关注？因为它在很多你能想到的类别里快了 10 倍。你知道的，Linear 对比 Jira 也是个好例子。Linear 有这样一个基准：好吧，他们对任何操作的响应时间限制在 300 毫秒以内；而 Jira 我们当然知道，它就是慢，因为他们有一堆复杂的……你可以解释为什么，但它就是慢。他们一开始就不是为了这个性能而构建的。

<details>
<summary>Original English</summary>

**Gerge**: Yeah. And I guess on on this last category, a really good example in the developer community is bun versus npm where bun just said like okay we're like 10x or 20x or 50x faster and devs are like what this possible and then it was so they there was this outrageous claim. I almost I I wonder if like you need to have these outrageous claims cuz devs started to pay attention cuz it was 10x faster in many you know categories. You know, linear versus was gyra is also a good example where linear have this benchmark of okay, they have 300 milliseconds for any action and gyra of course we know is is just slow because they have a bunch of complex you can explain why but it's slow. They it was never built for that.

</details>

**Speaker A**: 是的。而且你知道，如果你思考一下类似某个操作的 300 毫秒预算这种事，300 毫秒在计算机科学中就像是一个永恒的时间，对吧？所以，当你们说你们的卖点是耗时不超过 300 毫秒，这恰恰向你展示了过去对某些东西的标准已经偏离它本该在的位置有多远了。你到处都能看到这种情况。你知道的，你打开一些程序，有时一个操作你要等上好几秒。我认为人们没有意识到，一秒钟在现代计算中到底有多漫长。特别是当你连接的网络具有，你知道，不到 10 毫秒的 ping 延迟时。有时你讨论的这种情况是，实际的以太网数据包必须跨越物理距离到达这个数据中心，而这发生的速度远比你未能在合理时间内完成的这个非常简单的操作要快得多。这就好像是我们现在的性能大规模地不合格，当你告诉人们可以快 10 倍、100 倍时，人们根本不相信，但这确实是真的，而且正如你指出的那样，我们已经看到了很多证据。我确实在想，人们不太关注性能的原因之一，是不是因为很多开发者不知道基本的基准是什么。而且我，我想起了 Turbuffer 的创始人 Simon Ericson 曾有过的……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And you know if you think about something like a 300 millisecond budget for an operation 300 milliseconds is like an eternity in computing, right? And so if you're talking about like our pitch is that we're not more than 300 milliseconds, that just shows you how the bar was so far past where it probably should have been for something. And you see it everywhere. You know, I you go on to programs and you're waiting sometimes seconds for an operation. And I don't think people realize just what an eternity a second is in modern computing. Uh especially when you're sitting on networking like that has, you know, sub 10 millisecond ping times. Sometimes you're talking about this, you know, the actual packets had to travel physical distance to get to this data center and that was being done far faster than this very simple operation that you were failing to do in a reasonable amount of time. It's just like we are massively underperforming and people don't believe it when you say 10x 100x but it's actually true and we've seen a lot of proof of it as you point out. I do wonder if one part of the not really much focus on performance is that a lot of developers don't know the the baseline thing. And I I'm reminded by Simon Ericson, the founder of Turbuffer, have

</details>

<!-- chunk 4/16 -->

### Napkin Math 与性能评估的误区

**Speaker A**：他有个项目叫 Napkin Math，在里面他列出了很多操作的耗时，主要是网络相关的操作。比如在两个 AWS 数据中心之间传输一个字节需要多长时间？传输一 GB 需要多长时间？传输一 TB 呢？把数据从 SSD 写入 NVMe 需要多长时间等等。他拿到了这些数据。他说他发现，每当 Shopify 内部决定是选择供应商 A 还是供应商 B 作为数据库时，他们只会运行一个自己写的基准测试，然后得出类似这样的结论：比如存储这个东西在这个数据库上需要 2 秒，在那个数据库上需要 10 秒，我们就选那个 2 秒的。他看了之后觉得这根本说不通，像是在文件系统里存储的这个操作，这里明明有一个理论极限，比如大概是 100 毫秒。那它绝对不可能需要 10 秒。结果往往证明，他发现那个基准测试本身就是错的。他们测试了错误的东西，并以此做出了决定。所以我很好奇，是不是很多工程师和开发者根本意识不到，与你拥有的资源相比，这东西实际上慢得有多么令人抓狂。

<details>
<summary>Original English</summary>

**Speaker A**: This has this project called Napkin Math where he did a list of mostly networking operations. How long does it take to transfer one byte between like two AWS data centers? How much does a gigabyte take? How much does a terabyte take? How much does it take uh to to write an SSD to an NVME and so on. And so he had these numbers and he said that what he found is whenever inside Shopify they were deciding do we choose vendor A or vendor B as a database they would just run uh a benchmark that they would write themselves and they would get like okay like I don't know storing this and this it takes 2 seconds on this one 10 seconds on that one we will choose a two second one and he looked at it and said like hey like this doesn't make sense like the amount to to store in a file system like here's a theoretical limit which is I don't know 100 milliseconds. Like there's no way that's going to be 10 seconds. And it often turns out that he found that the benchmark was just wrong. They were benchmarking the wrong thing and they were making decisions. So I wonder if there's a thing where many engineers, developers are maybe just not aware of how truly devastatingly slow this thing is versus the resources you have.

</details>

**Speaker B**：这正是我在 Substack 上想表达的全部核心，对吧？你刚才说的完全正确，这也是我在 Substack 上、在那些课程的所有部分中反复强调的一点：总的来说，人们对于在计算机科学，或者随便说在软件工程中进行优化的方式存在一种误解。这种误解就是：你会认为你应该先运行一下性能分析（profile），找出性能分析中耗时较大的部分，然后对它们做些修改，接着去测量统计数据；统计数据越好，你能获取的统计数据越多越好，然后你看看这些统计数据是否有所改善。如果改善了，那就是一个好的修改，你就会继续这么做。但这完全是不对的，从来没有人是这么做的。我和许多极其优秀的优化专家合作过，他们并不是这么做的。做优化的正确方法非常像你刚才说的：你首先要知道，这个系统必须执行哪些操作？底层硬件在理论峰值下能做到什么程度？然后你去测量这个理论最大值和你实际达到值之间的差值。接下来你在优化过程中的目标，就是把这个差距缩小到一个你认为可以合理解释的范围，并希望能找到原因，解释你为什么没有达到理论极限。因为很多时候你是达不到理论极限的，所以我们才叫它理论值，对吧？做到这一点至关重要，因为否则的话，你用之前那种方法所做的无非就是，找一个你觉得可能算得上优化的修改，然后看看统计数据有没有提升。你那么做其实只是在寻找一个局部最优解（local minima）。

<details>
<summary>Original English</summary>

**Speaker B**: Uh that is the entire point of like my substack, right? So what you just said is exactly true and it is the thing that I hammer home on the substack through all the parts of like the courses on there which is that in general there's a misconception about the way that you approach optimization in uh like in computer science or in whatever software engineering let's say and that misconception is that what you do is you run a profile you identify where the like you know big parts of the profile are you make some changes to those and you you measure like statistics the better the statistics you know the the the more uh statistics you can get the better and you look to see if those statistics improved if they have that was a good change and you proceed as such and this is completely not correct that is not how anyone has ever you know I I've worked with many extremely good optimization people and that is not how it is done the correct way to do optimization is very much like what you just said you first go what are the operations that this system has to perform form. What is the underlying hardware capable of doing at its theoretical peak? And then you measure the delta between that theoretical maximum and what you have achieved. And then your goal during optimization is to shrink that gap to something that you think could be plausibly explained and hopefully come up with explanations of why you aren't at theoretical. Because often times you can't hit theoretical. That's why we call it theoretical, right? And it's crucial that you do this because otherwise all you're doing with that other method is finding a you know with with the with the I'm just going to you know make something I think might be an optimization and look if my statistics improved. All you're doing there is finding a local minima.

</details>

### 理解理论极限的重要性

**Speaker B**：你做的仅仅就是这些。你只知道你的性能表现大概是这么个形状，然后你找到了一个小坑，就这么安于现状了。这不叫优化，这叫改进。但优化的意思是让其达到最优，对吧？意味着我们要找出我们实际上应该能让这台机器做到什么程度。所以，这就是为什么我强调那种方法，因为那是我见过的优秀优化者始终采取的方法。他们就是通过了解最大值能达到多少来获得良好性能的。除此之外，这也是能让你在优化方面变得更强的原因。因为不管你是谁，也不管你已经懂了多少，当你要去解决一个优化问题时，系统采用的新布局方式里很可能存在一些你不知道的东西：一些人们还没有弄清楚的关于现代 CPU 的新机制，网络背板（network backplane）有何不同的新设计，或者 GPU 驱动程序有何不同的新特性，谁知道呢，对吧？如果你没有一个理论最大值可供参考，没有一个基准来测量你的差距，你就不会知道那里是否存在某些严重的异常。而且你绝对想不到，我们有多经常发现这类异常：像 CPU 里的一些谁都不知道的机制。你知道，我甚至在做 Substack 的过程中就真切地遇到过。我会想：“这是个什么东西？”然后我去研究它，发现：“哦，原来 Intel 芯片好像能做这种新的重命名（renaming），这种新的 RAT 表机制。我们以前都不知道。”而这就成了一个我们在讨论如何做性能优化时必须去建模的新机制。所以，我猜这也就是你刚才所说的 Napkin Math（餐巾纸估算）的另一个关键部分。我也把它叫做“信封背面的计算”（back of the envelope），我听过别人用这个词。很多时候它们基本是可以互换的，对吧？知道理论值是多少，也是你学习的一种方式。你就是这样学习新硬件和新性能选项的。

<details>
<summary>Original English</summary>

**Speaker B**: That's all you're doing. You're just you're just you know you've got this this shape of your performance and you're finding some little spot and you're sitting in it. That's not optimization. That's improvement. But optimization means to make optimal, right? means we're going to find what we actually should be able to get this machine to do. And so, uh, you know, that's why I emphasize that approach because it's the one that I I've always seen great optimizers take. That is how they get good performance is by knowing what the maximum could be. In addition to that, it also is what lets you become better at optimization. Because no matter who you are and no matter how much you already know, when you go to tackle an optimization problem, there may well be some things in the new like way that the system is laid out that you don't know about, new uh things that people have not figured out about modern CPUs, new things that are different about the network backplane, new things that are different about the GPU drivers, who knows, right? And if you don't have some theoretical maximum to look at and to measure your delta from, you don't know if there's some serious anomaly there. And we you would be surprised at how many times we find anomalies like this things in CPUs that no one knew about. And we, you know, like I've literally had them in the course of making the Substack. I've been like, "What is this thing?" And I look into it's like, "Oh, there's this new renaming this this new rat table thing that Intel chips seem to be able to do. We didn't know about that." And that's like a new thing we have to model when we talk about how to do performance. And so the that's the other crucial part of I guess what you were calling napkin math. I also call it back of the envelope. That's the term I've heard used for it. Often times they're kind of interchangeable, right? Knowing what the theoretical is is how you learn as well. Uh how you learn about new hardware and new performance op options.

</details>

**Speaker A**：很有意思。而且通过做这些，你本身就是在学习。你在成为一名更专业的从业者。你更了解特定的硬件，或者你的电脑、软件栈、内核的内部运作原理，你知道的，我猜所有这些东西已经远远超出了最基础的编程语言的范畴。因为你可以说我是一名工程师，我是一名软件工程师，因为我知道怎么使用这门编程语言；但我认为，只有当你能深入技术栈的底层，并且具备这种能力，而且至少对其中一部分有很好的理解时，你才可能算得上是一名真正的工程师，对吧？然后你还可以再去学习其余的部分。

<details>
<summary>Original English</summary>

**Speaker A**: Interesting. Plus by doing this you're just learning. You're becoming better professional. you understand more about given hardware or or the inner workings of of your computer or or software stack or kernel, you know, all the stuff that I guess goes way beyond the the the b the vanilla programming language like cuz you can say I'm an I'm an engineer. I'm a software engineer because I know how to use this programming language, but I'd argue you're probably an engineer if you can go down the stack and you have that ability and you have like a good good understanding of some of it at least, right? And you can learn the rest.

</details>

### 为什么要学习汇编语言

**Speaker B**：我还要说，我们在课程中做的另一件事就是教如何阅读汇编语言。人们经常会问，为什么？你知道，汇编语言，我什么时候会需要用到它？其实有一个非常好的理由。那就是，你可能会使用的所有其他东西，都不会告诉你 CPU 到底接收到了什么指令。你知道，如果我看一个 Java 程序，如果我看一个 C 程序，如果我看 Haskell、OCaml 或者是 Rust，我看到的都只是编译器的输入。我根本不知道 CPU 实际上会被要求去做什么。而如果我看那个编译器输出的汇编语言，我就能确切地知道 CPU 被要求去做什么。并且，学会阅读汇编语言并没有那么难，你可以很快看出来：CPU 被要求去做的事情，和我认为它应该被要求去做的事情是一致的吗？这样一来，对吧，你几乎永远不需要去写汇编。你极少需要亲自写汇编语言来做任何事情，除有时候为了测试目的，这么做会更容易一些，这样你就不用费劲去说服编译器输出某个特定的东西了。所以如果你只是在测试某个东西，有时能写点汇编语言会很有帮助。但如果你谈论的是在优化中可能要做的绝大多数任务，去写它？没必要；去读它？至关重要。它还会为你打开一个充满无限可能的巨大世界，因为一旦你懂了汇编语言，你现在就可以做诸如看懂那些 CPU 架构图之类的事情。比如，当他们发布一款新处理器时，他们会放出一张小图表。那张图表会告诉你诸如这东西做乘法最快能有多快之类的信息。这意味着，如果你懂汇编语言，你直接看那张图表就能看懂，对吧？如果你不懂汇编语言，你看着那张图表只会觉得：我完全不知道我在看什么，对吧？这就好像只是一张奇怪的流程图，并没有真正告诉我任何信息，对吧？所以汇编语言真正伟大的一点在于，它为你解锁了所有这些知识，因为它是机器实际的输入语言，它能让你弄清楚机器到底是如何运作的。

<details>
<summary>Original English</summary>

**Speaker B**: And I would also say that one of the other things that uh we do in the class is teach how to read assembly language. And people often ask what like why like you know assembly language what would I ever need that for? Uh there's a very good reason for it. And that is that everything else that you might use doesn't tell you anything about what the CPU is actually receiving. You know if I look at a Java program if I look at a C program if I look at Haskell OAML whatever right uh Rust all I'm seeing is input to a compiler. I have no idea what the CPU is actually going to be asked to do. If I look at the assembly language output from that compiler, I know exactly what the CPU is being asked to do. And it's not that hard to be able to learn to read assembly language so that you can see very quickly is the CPU being asked to do the things that I think it should be asked to do them. And in that way, right, you don't have to write it hardly ever. Uh it's very rare that you have to write assembly language to do anything. um other than sometimes for test purposes it's easier to do that so you don't have to try and convince a compiler to output something. So if you're just testing something, sometimes it helps to be able to write some assembly language. But if you're just talking about the uh vast majority of tasks you might do in optimization, writing it, no reading it essential. And it also unlocks this sort of uh huge world of possibilities to you because once you know assembly language, you can now do things like read those CPU diagrams like you know when they announce a new processor, they put up a little diagram. That diagram tells you stuff like the fastest this thing could do multiplication and stuff like that. It tells you that if you know a semi language, you can read it right off the chart, right? If you don't know a semi language, you look at that chart and like I have no idea do what I'm looking at, right? Like it's just this weird flowchart that doesn't really tell me anything, right? And so one of the really great things about s unlocks all of this knowledge for you because it's the it's the it's the actual uh input language to the machine and it allows you to figure out how it's operating.

</details>

**Speaker A**：另外，我想我们还应该补充一点，汇编语言并没有那么复杂，对吧？就其本质而言，它是一门要简单得多的语言。好吧，如果你以前从未见过它，读起来是会难一些，但从数量上来说……

<details>
<summary>Original English</summary>

**Speaker A**: Plus, I guess we should add that assembly language is not all that complicated, right? Just just by by by nature, it's a far simpler language. Okay, it's harder to read if you've never seen it, but it's in terms of the number of

</details>

<!-- chunk 5/16 -->

### 汇编语言的简洁性与学习门槛

**Guest**: 那些操作。汇编语言之所以如此精简，是因为你知道汇编的本质就是这样。相比之下，每一门高级语言都有比汇编多得多的关键字、控制结构等等，不管你怎么称呼它们，对吧？

<details>
<summary>Original English</summary>

**Guest**: operations. It's so barebones because you know that's what assembly is. Like every single higher level language will have way more keywords, structure, whatever you name it, right? Than assembly,

</details>

**Guest**: 要多得多。特别是当你考虑到实际使用的那部分子集时更是如此。如果你看看理解今天的一个网站所需要掌握的语言结构子集——所有的 JavaScript 库，所有的 JavaScript 语法，所有的 DOM，以及所有将要发生的交互行为，还有 CSS（笑）。

<details>
<summary>Original English</summary>

**Guest**: massively more uh and especially when you consider the subset that are actually used. If you look at the subset of constructs that you would need to understand to be able to understand um say just a website from today, all of the JavaScript libraries, all of the JavaScript syntax, all of the DOM, you know, all of the behavior that's going to go on there, CSS, [laughter]

</details>

**Host**: React，CSS，对吧？所有这些。

<details>
<summary>Original English</summary>

**Host**: React, CSS, right? all of that

</details>

**Guest**: 至于汇编语言，你总共可能只需要学习 20 到 30 条指令。因为大多数传统的汇编指令，比如 x64 中的大部分指令，编译器几乎从不输出。所以你只需要学习一个非常小的子集。那就是你在 90% 的情况下会实际看到的那些指令。这要简单得多。而且，当你关注性能时，你通常也只关注其中非常小的一部分，对吧？你已经大致了解了代码的运行情况，也看到了程序的基本布局。你明确了应该发生什么，只是想看看，比如：“等等，为什么我原本认为不该跑得这么慢的这部分，现在却这么慢？”你通常最终不得不去查看的也只是非常小的一段代码。所以，就像人们说的那样，如果你能理解如何在 HTML 中让一个 div 居中，如果你能让 div 垂直居中，那么我敢说你大概率也能学会汇编语言。

<details>
<summary>Original English</summary>

**Guest**: assembly language, you know, maybe there's 20 30 instructions you might have to learn total because most assembly most things in legacy assembly like x64, most of them are hardly ever output by the compiler. So you only need to learn a very small subsets. That's the ones that's actually going to be that you're going to be seeing in 90% of the cases. It's so much simpler. And also when you're looking at performance, you're typically only looking at a very small part, right? You've kind of understood roughly what's going on. and you've you've seen the basics layouts of your program. you've identified what's supposed to be happening and you're just looking to see like wait why is this part which I don't think should be running this slowly why is it running this slowly it's just a very small piece you typically end up having to look at as well so it's really much easier if you can understand how to center a div as they say if you can vertically center a div in HTML then you can probably learn assembly language I would say

</details>

### 过早优化是万恶之源？

**Host**: 好的，你对性能优化充满热情。你也有很好的教育材料，包括免费的视频、你的付费 Substack 以及其中的免费内容等等。但让我来唱个反调。有句老话说“过早优化是万恶之源”。我们在很多时候，或者说我个人在很多时候都会用到这句话。我们会想：“哦，我们应该让这个具有高性能吗？我们需要优化这个东西吗？”然后我们会说：“算了吧，先别那么做。我们先把它构建出来。先看看它对我们的客户或者对我们自己来说是不是足够好，如果真的有必要，我们随时可以再去优化它。”我的意思是，你也知道，这并不是世界上最难的事情。好吧，可能我举的例子不如你说的那么好，因为我可能不懂汇编，但这确实是一种构建软件的思维方式，比如在大型科技公司构建 SaaS 软件时。你对这种说法有什么回应？因为我感觉我刚刚提出了一个非常有力的论点。

<details>
<summary>Original English</summary>

**Host**: okay you're super passionate about performance optimization you also have really good educational materials both both free videos your paid substack the free parts of it, etc. But let me just play devil's advocate. There's this saying that premature optimization is the root of all evil. And we typically use it or I typically use it so many times. We're like, oh, should we make this performance? Should we optimize the thing? And like, nah, let's not do that. Let's first build it. Let's see if it's good enough for our customers, for ourselves, and if we need to, we can always optimize it. I mean, you know, like it's it's not the hardest thing in the world. Okay, maybe not as good as how you mentioned cuz maybe I don't read assembly but and that's that's kind of a thinking of building you know like I guess SAS software building software at big tech. What is your reply to that cuz I I'm I feel really good that I made a really good argument here.

</details>

**Guest**: 那么，我想说的是，关于那句话最重要的一点——我想我得把这句话本身稍微剥离开来谈。顺便说一句，我有一整场关于那句名言的讲座。长达两个小时，是我今年在“更好的软件”（Better Software）大会上讲的。我相信我们会在下面的节目简介里放上视频链接。

<details>
<summary>Original English</summary>

**Guest**: So I guess what I would say is the important part about that and I guess I'll divorce it a little bit from the saying. I have an entire lecture on that saying by the way. It's it's like two hours long and I I gave it at better software conference this year and I believe the VOD we're linking that in the show notes below.

</details>

**Host**: 好的。我想大概还需要一两周视频才会上线。所以它可能会和这期播客差不多同时发布。

<details>
<summary>Original English</summary>

**Host**: Okay. It'll it'll be like a week or two I think till it's up. So it may be right at the same time as this.

</details>

**Guest**: 但是，如果你想了解那句话的历史渊源，你可以去看看那个讲座。不过我想谈谈它背后的理念，因为我认为……我不想完全否定它，因为它并不完全是错的。这个理念是说：“好吧，我打算推迟优化工作。我现在不去考虑性能问题，我只管把我需要做的功能先做出来。然后，你要么指望我自己，要么指望我以后雇个性能专家来收拾烂摊子。”对吧？

首先，我们来看看这种做法积极的一面。它积极的一面在于，对于某些类型的代码，这是行得通的。如果你碰巧把某个操作写得很糟糕，而那个操作的优化版本仅仅是把一个循环从你那种非常天真的实现方式改成一个高度优化的版本。

<details>
<summary>Original English</summary>

**Guest**: Uh but so if you want to find out the history of that phrase you can go look at that. But I wanted to talk about the idea behind it because I think there's uh I don't want to dismiss it entirely because it's not entirely false. And the idea is that well I'm just going to delay optimization work. I'm not going to think about that and then I'm just going to make whatever I'm going to make and then you know either myself or maybe I'll just hire some performance person to come in and clean up the mess later. Right? So here's the positive side of that first. The positive side of that first is for some types of code that will work. If you happen to have written some operation poorly where the optimized version of that operation just looks like someone taking a loop and changing the loop from your really like you know naive version to a really well optimized version.

</details>

**Host**: 典型的例子就是：“我写了一个冒泡排序，我们以后再去优化它。”

<details>
<summary>Original English</summary>

**Host**: The the the typical of like I wrote a bubble sort we can later optimize that.

</details>

**Guest**: 谁知道呢，对吧？任何类似形式的东西。好吧，也许我们可以那样做。所以在某些时候，你的确应该在脑子里采取这种策略，你会告诉自己：“好的，我本可以花一个星期去研究这里最快的哈希表实现，但软件工程的一部分就是足够聪明，知道现在做还是以后做其实都无所谓。”因为我非常了解这个问题，所以我很确定围绕这个部分的架构不需要改变。没关系，我可以把它推迟到以后再做。也许即使放个朴素版本进去，它也永远不会显得太慢，那我们就根本不需要做任何优化工作。也许以后它真的太慢了。那也没关系，我只需要针对这一个哈希表实现去优化，我们就能达到所需的速度，对吧？

如果你这样做，如果你将这种真正的工程思维应用其中，你就不会遇到问题。问题在于，你不知道你正在做出的选择是否会产生那种容易优化的热点（hotspot）。我可以给你举一个人们通常都经历过的非常简单的例子。

<details>
<summary>Original English</summary>

**Guest**: Who knows right? Anything of that form. Okay maybe we can just do that. So there are certain times where you do in your head want to be doing this where you want to say okay I could go spend a week researching the fastest hasht implementation here but part of software engineering is being smart enough to know it won't matter if I do that now or later the architecture around this piece won't have to change I'm quite certain because I understand the problem well enough so it's okay I can defer that to later maybe it's never too slow with the naive when put in there and then we don't have to do any work. Maybe it's too slow later. That's okay. I just target this one hasht implementation and we'll get as fast as we need. Right? If you're doing that, if you're applying that true engineering mentality to it, you don't have a problem. The problem comes when you don't know if the choice that you're making produces that kind of optimizable hotspot. And I'll give you a very simple example that usually people have had experience with.

</details>

### 串行依赖链带来的性能灾难

**Guest**: 这个非常简单的例子就是：我们编写整个软件项目时，不管我们设想做的是个多庞大的东西，我们在编写时完全忽略优化。我们坐下来开始写，我们使用了一种向服务器请求数据的模式。我们有某个 API，你知道，就是我们构建的用于向服务器请求数据的 API。我们向服务器发送请求，它返回给我们服务器的响应。这就是我们构建这个东西的架构方式。

所以，每个人写出了成百上千万行的代码，而且这些代码看起来全都是：向服务器请求某个东西，做一些计算，再向服务器请求下一个东西，再做一些计算，对吧？然后在最后，你发现这实在太慢了。但这没关系。因为你本来就不担心这个，你想着到最后可以请一些性能专家来看看。他们看了一眼，然后说：“抱歉，我们无能为力。”

为什么呢？原因是你创建了一个串行依赖链（serial dependency chain）。你所有的代码看起来都是：等待网络请求返回，做点事情；等待网络请求返回，做点事情，等待……而那种串行依赖链如果不重写的话，是根本无法缩短的。

<details>
<summary>Original English</summary>

**Guest**: A very simple example would be we write our entire software thing like we just whatever this massive thing that we're imagining doing where we're going to ignore optimization. We sit down and we write it and we use a paradigm where we ask the server for something. We have like some API, you know, that we've built for asking servers for things. We ask the server and it returns to us what the server's response was. And we that's like kind of how we architect this thing. So everyone writes, you know, hundreds of thousands or millions of lines of code and they all look like ask the server something, do some calculations, ask the server for the next thing, do some calculations, right? Then at the end you find this is way too slow. But that's okay. You weren't worried about that cuz you're like when the end you call in some performance experts. They look at and they go, there's nothing we can do for you. Sorry.

Why? Well, the reason is because you created a serial dependency chain. All of your code looks like wait for a network request to come back, do something. wait for a network request to come back, do something, wait for and that serial dependency chain can't really be shortened without just rewriting it.

</details>

**Guest**: 相反，如果你当初采用了另一种模式，并告诉你的程序员：“听着，你们需要这样做。在每个操作的开头，你们需要弄清楚可能需要向服务器请求的所有数据，然后你们一次性去请求所有这些数据，对吧？接下来再统一进行所有的数据处理。”只有当你绝对无法提前确定你需要向服务器请求什么时，你才去创建依赖链。

现在，你陷入了这种困境，仅仅是因为你没有告诉他们那样做。你不得不重写你所有的代码。每个人现在都要去重写所有代码，如果他们还能重写的话。如果这在实际上甚至可能的话——而且是以一种不会比完全重写整个项目还要慢的方式来进行，对吧？

那么，那里发生了什么呢？重申一次，我们在 Substack 上经常讨论这个话题，这涉及到串行依赖链的概念。就是当你按顺序把事情堆叠起来的时候，对吧？你的软件性能通常是由最长的串行依赖链决定的，因为它是不能被并行的东西。如果我有任务 A，然后任务 B 依赖 A，接着任务 C 又依赖 B，我们没法缩短这个过程，因为它必须按顺序进行。所有的东西都在等待它。因为存在依赖关系，我们不能用多线程处理；我们也不能让它横向扩展；我们无法摊销网络请求的开销等等。

这种模式可能会在编程中普遍存在，我们无法低成本地把它消除掉，因为它不是一个局部热点。这就是你做事的方式。这正是那种“先不管性能”思维失效的地方。如果每一个软件工程师都知道要提防虚假的串行依赖链，提防那些他们正在创建的一系列无法被优化掉的依赖操作，或者其他诸如此类无法轻易修复的架构问题，那么这个世界就真的会更像是“先等着，最后再优化热点”，对吧？

<details>
<summary>Original English</summary>

**Guest**: If instead you had made the paradigm and told your programmers, look, here's what you need to do. At the top of every operation, you need to figure out all the things you might want to ask the server for, you ask them for all of those things, right? And then you do all of your processing there. And you only create a chain of dependencies if you absolutely couldn't have determined what it was you needed to ask a server for. Now you're just in this situation because you didn't tell them to do that. You have to rewrite all your code. Everyone is now going out rewriting all the code if they even can. If it's even possible to really do that in a way that's not slower than just rewriting the thing, right? So what happened there? Well, again, we talk about this a lot on on the Substack, but there's this idea of a serial dependency chain. It's when you stack things in order, right? And the performance of your software is generally determined by the longest serial dependency chain because it's something that cannot be parallelized. If I have thing A that then B depends on that then C depends on that we cannot shorten that because it has to go in order. Everything waits for it. We can't multi-thread it because it's dependent. We can't uh you know make it run wide. We can't you know uh amortize the network request whatever. that kind of thing can be pervasive in the programming and we can't cheaply remove it cuz it's not a hot spot. It's a way that you did things. That's the part where that kind of thinking breaks down. If every uh software engineer knew to watch out for false serial dependency chains, things where they were creating series of dependent operations that could not be optimized away or other sorts of architectural problems like that that cannot be easily fixed, then the world would look more like just wait and optimize the hotspot, right?

</details>

**Host**: 是的。所以这就是架构，就是规划，对吧？就像如果在那个阶段你会想：“好吧，随着这个东西不断增长，会有什么……”

<details>
<summary>Original English</summary>

**Host**: Yeah. So this this is the architecture, the planning, right? Like if if in that phase you're like okay like as this thing grows like what will get

</details>

<!-- chunk 6/16 -->

### 性能优化的误区与架构决策

**Host**: 在性能方面，什么会拖慢它的速度？或者你可以问所有这些问题，或者像这些问题的不同变体，你懂的，或者从另一个角度来看等等。

<details>
<summary>Original English</summary>

**Host**: in the way of performance what will slow it down or you can ask all these questions or like different flavors of the questions you know or from the other side and so on.

</details>

**Casey**: 是的。另一种思考方式是，因为人们通常会谈论“热点（hotspots）”，比如：“哦，这将会是热点优化。我们只是遇到了一些尖峰。会有人来清理那些尖峰，然后我们就完事了。”对吧？但正确的思考方式是，在大多数情况下，你的代码库不再会因为偶然就变成那种（容易优化的）状态了。你必须在前期就通过工程设计，构建出一个包含热点的代码库，这样人们之后才能对其进行优化，对吧？因此，关键的结论是：你团队中每一个做架构决策的人，都必须了解性能，并且他们必须做出能够让下游的其他人使用一种可以在后续进行优化的架构的决策。如果你不这么做，那你完全就是在碰运气（掷骰子）。

<details>
<summary>Original English</summary>

**Casey**: Yeah. Another way to think of it is cuz hotspots is the way that people talk about that like oh it's it's going to be hotspot optimization. We just got a few spikes. Someone will come in and clean up those spikes and we're done. Right. The way to think about it is your codebase will not end up that way by accident in most cases anymore. you have to engineer upfront for a hotspot codebase that people can then optimize, right? And so that's the crucial takeaway is everybody on your team who is making architectural decisions, those people must know performance and they must make decisions that will allow the other people downstream of them to use an architecture which can be optimized later. If you don't do that, you're just rolling the dice.

</details>

### 赞助商插播：Turbopuffer 与 Antithesis

**Host**: Casey 刚才谈到了做出架构决策的工程师们应该如何了解性能。在选择你的依赖项（比如使用哪个数据库）时，这一点同样适用。在这里，我想提一下我们本季的赞助商 Turbopuffer。你已经知道 Turbopuffer 是一个向量和全文搜索引擎。但这里有一个来自 Linear 的有趣故事，讲述了当你不再把 Turbopuffer 仅仅当作一个搜索引擎，而是开始把它作为一种用来降低延迟的基础组件（primitive）时，会发生什么。作为背景，Linear 是一个本地优先（local-first）的应用程序。因此，每个客户端都保留一个本地数据库，当该客户端重新上线时，它需要追赶上期间发生的事情，并且要快速完成。他们最大的工作区每天会产生大约一百万次同步操作。对于大规模的读取，通过从 Postgres 读取数据来进行追赶变得非常缓慢。因此，尾部延迟变得过大，而增加更多的副本也没有任何帮助。Linear 巧妙地解决了这个问题。他们开始将 Turbopuffer 用作每个客户端的服务索引。这是因为 Turbopuffer 本身是建立在倒排索引之上的。因此，对于每个索引值，它都会存储可以找到该值的文档。这种索引的查找成本是恒定的。所以 Linear 利用了这种结构，让每个客户端的索引指向他们需要同步的变更。结果是，他们不仅降低了延迟，而且无论同步到客户端的变更列表有多长，他们都将其保持在持续的低水平。Linear 发布了一篇关于这次重构的博客文章，标题为“重构 Linear 的增量同步读取路径（rebuilding linear's delta sync read path）”。去看看吧。我喜欢这个故事，因为它展示了选择正确的基础组件有多么重要，以及优秀的基础组件可以如何改进你的系统。如果你正在构建需要存储大量数据或服务大量数据的系统，Turbopuffer 很可能会加快你的系统速度，或者为你节省成本。前往 turbopuffer.com/pragmatic 了解更多。

<details>
<summary>Original English</summary>

**Host**: Casey just talked about how engineers making architectural decisions should know about performance. This is also true when choosing your dependencies like which database to use. And this is where I want to mention our season sponsor Turbopuffer. You already know how Turboper is a vector and full text search engine. But here's an interesting story from Linear on what happens when you stop thinking of Turbopuffer as a search engine and start using it as a primitive to reduce latency. As context, Linear is a local first app. So each client keeps a local database and when that client goes back online, it needs to catch up with what happened and do it fast. Their biggest workspaces generate around a million sync actions per day. Doing catch-ups by reading from post was getting slow for large reads. So the tail latency got too large and adding more replicas did not help either. Linear solved the problem cleverly. They started using Turbopuffer as a serving index for each client. This is because Turbopuffer itself is built on top of inverted indexes. So for every index value, it stores the documents that that value can be found in. The lookup cost for such an index is constant. So linear took this structure and had each client's index point to the changes that they needed to sync. As a result, not only did they reduce latency, but they kept it constantly low matter how long the change list is synced to the client is. Linear published a blog post about this refactors titled rebuilding linear's delta sync read path. Check it out. I love this story because it shows how important it is to choose the right primitives and how good primitives can improve your system. If you're building systems where you store a lot of data or serve a lot of data, Turbopuffer can probably speed things up or save on your costs. Learn more at turbopuffer.com/pragmatic.

</details>

**Host**: 我还想谈谈我们的首席赞助商，虽然 Casey 刻意在工作中不使用 AI 编程助手（agents），但我们大多数人都在用。而当你使用编程助手工作时，你的工作就不再是编写代码了，而是详细说明并测试它。Antithesis 是当今验证 AI 助手生成代码的最有效方法。让我解释一下它是如何工作的。Antithesis 在一个充满敌意的模拟环境中运行你的整个系统。通过这样做，它能在你的用户之前发现每一个 Bug。因为这种模拟是完全确定性的，它不仅能发现 Bug，还能为你提供每个问题的完美复现。为了创造这样一个工具，Antithesis 团队还需要发明全新类型的调试工具。例如，这里有一个叫做“Bug 概率图”的东西。X 轴是虚拟时间，Y 轴是概率。当 Antithesis 运行敌意模拟时，它会绘制出 Bug 概率上升的时间段，这极大地帮助了寻找 Bug 的根本原因。同时，Antithesis 还有一个日志可视化工具。向下的垂直线代表从相同状态分支出来的事件。而紫色的圆点则是 Bug 发生的位置。在能够交付 AI 助手编写的代码方面，Antithesis 是目前最棒的工具。Jane Street、Fly.io 的团队以及 CD 社区都在使用它来充满信心地交付代码。前往 antithesis.com/primmatic 了解更多。

<details>
<summary>Original English</summary>

**Host**: I'd also like to talk about a presenting sponsor and this is while Casey deliberately does not use AI coding agents for his work. Most of us do. And when you work with coding agents, your job is no longer writing code. It's specifying and testing it. Antithesis is the most effective method for verifying agentic code today. Let me explain how it works. Antithesis runs your whole system in a hostile simulation. By doing so, it finds every bug before your users do. And because the simulation is fully deterministic, and this doesn't only find bugs, it gives you a perfect reproduction of every issue. To create such a tool, the anticys needed to invent new kinds of debugging tools as well. For example, here's what's called a bug probability graph. The xaxis is virtual time and the yaxis is probability. As anticis runs a hostile simulations. It plots time frames when the bug probably increases which greatly helps with finding the root cause of the bugs and antithesis also has a log visualizer. Vertical lines going down represent events branching off from the same state. And the purple dots are where the bug happens. Antithesis is as good as it gets in being able to ship agent written code. It's what teams at Jane Streetfly.io and the CD community used to ship with full confidence. Head to antithesis.com/primmatic to learn more.

</details>

### 工程博客背后的真实原因

**Host**: 讲完了这个，让我们回到 Casey 的话题：如果你不设计一个可以在日后进行性能优化的架构，那你完全就是在碰运气。

<details>
<summary>Original English</summary>

**Host**: And with this, let's get back to Casey and how if you don't design an architecture that can be performance optimized later, you're just rolling the dice.

</details>

**Casey**: 而且我们已经看到了太多这样的项目。我做过一整期视频，在里面我逐一分析了人们写的这些博客文章，他们会说，你知道的，包括 Facebook、Uber，所有这些公司。他们的博客文章里写着：“我们不得不重写这整个东西，因为性能太差了。”如果是局部热点导致你的性能很差，你永远不需要重写整个系统。所以，我们知道那一套（指望事后清理热点）已经行不通了。为什么呢？就是因为我刚才说的那些原因。

<details>
<summary>Original English</summary>

**Casey**: And we've seen so many projects. I have an entire video where I go through like look at all these blog posts of people who like say we, you know, it's Facebook, it's Uber, it's everybody. They've got blog posts of we had to rewrite this whole thing because the performance was bad. If it was always hotspots that made your performance bad, you'd never have to rewrite the whole thing. So, we know that that doesn't work anymore. Uh why? Because of the things I just said.

</details>

**Host**: 我曾经在 Uber 工作，当时我不是做决策的人，但我旁边的团队是，我看到或者说我多多少少理解了他们为什么做那些决策。但通常情况下，而且现在这也正在 AI 公司身上发生，很多时候就像是：“我们选择了这种技术，也就是 Python，它是单线程的，当时在 Web 服务器上这么做是有道理的，但现在我们规模变大了。”这在 Uber 就发生过，当时是 Python 和 NodeJS，然后他们在后端转向了 Go 和 Java。现在在 AI 公司里则是 Python，OpenAI 和 Anthropic 现在都在经历这个过程。他们要么已经公开了，要么——我之前写过关于 Anthropic 的文章，他们私下跟我分享过，但我把它公开出来了。他们使用 Python 是因为数据科学家、AI 或者机器学习工程师懂 Python。他们部署了一堆 Web 服务器，把 API 运行在上面。最初，他们只是，你知道，横向扩展，但现在他们会说：“好吧，如果我们迁移到 Rust”——他们现在正在选择 Rust 或者 Go，但我认为是 Rust——“那么我们实际上就可以实现多线程，而且同一台机器实际上可以处理更多的连接。那太酷了。”我遇到了很多这种情况，因为我认为这是一种简单且安全的沟通方式，因为它不会让你显得很糟糕。但你说得对，很多时候，我不认为你能在工程博客文章中得到这些公司公开宣称的真正原因。比如，当它是一种非常……很容易承认的错误，或者不算错误，只是当时看来合理的决定时，他们会告诉你。但如果那是个由于疏忽造成的失误，你真的不会在一篇面向公众的工程博客文章里看到它，除非是一些真的很坦诚的初创公司。而且别忘了，很多这类博客文章的作用是帮助某人升职或获得认可，所以它们的基调总是会更加积极，尤其是当他们有一个内容创作团队的时候——大公司确实有。所以，这不完全是公关（PR），但介于两者之间。

<details>
<summary>Original English</summary>

**Host**: I was at Uber where I I was not making the decision but the teams next to me were and I saw or I I kind of understood why they were making but typically and right now it's happening with AI companies oftent times it's like we chose this technology which is Python and it's single threaded and it made sense at the time on the web server but now we're big and this happened at Uber it was it was Python and NodeJS and then they went to go and Java on the back end and now with AI companies it was Python open AI and Tropic are both going through this right now uh They're both either public about it or I I've written with Antropic. They they they share with me with with me, but I I put it out there. They used Python because data scientists or AI or machine learning engineers knew Python. They put on a bunch of web servers. They had their API run on it. Initially, they just, you know, scales horizontally, but now they're like, well, if we move move over to Rust, they right now they're choosing Rust or or Go, but I think it's Rust. Well, we can actually have multi-threaded and the same machine can actually handle more connections. So, cool. I came across a lot of that because I think that's easy and safe to communicate because it doesn't look bad on you. But you're right, a lot of times I don't think on engineering blog post you'll get the real reason that these companies put out there like when it's kind of a very kind of you know easy to own mistake or not mistake but just the decision which made sense. they'll tell you. But if it's something that was an oversight, you're not really going to get that on a public facing engineering blog post, except for maybe some startups who are really there. But don't forget like a lot of those blog posts are going to help someone get promoted or get recognized and they will always be way more positive in especially when there's a content writer team which large companies do have. So it's it's not quite PR but it's somewhere midway in between.

</details>

**Casey**: 我的意思是，是的。而且，我只想指出一点：这些事情正在发生，这个事实本身就是我们唯一需要知道的信号，对吧？因为一般来说，这种事是不应该发生的。如果那些关于（语言）激活的想法是真的，你永远不需要用一种不同的语言去重写一些东西，除非你单纯就是偏爱那种语言。那样的话，背后的故事只会是：“我们用这种语言重写了它，因为我们想使用这种新语言。”绝对不会是因为……或者对于 Rust 来说，可能仅仅是为了内存安全。我们看到过那些博客文章，对吧？就像是在说：“为什么我们要用 Rust 重写？不是为了性能。只是因为我们想要内存安全性”或者类似的原因。

<details>
<summary>Original English</summary>

**Casey**: And I mean, yes. And also, I would just point out the fact that like the fact that these things are happening though is all we really need to know for the signal, right? Because in general, this should not be happening. If the the ideas about activation were true, you'd never have to rewrite something in a language in a different language unless you just preferred that language. It would just the story would just be we rewrote it in this language because we wanted to use this new language. would never be um or for Rust it might be just memory safety. We see those blog posts, right? It's like why did we write into Rust? It wasn't performance. It was just we wanted the memory safety or something like that.

</details>

### 如何学习编写高性能代码

**Host**: 如果我是一名软件工程师、程序员，而且我只想提高编写高性能代码的能力，我很感兴趣，你知道，也许是在这期播客之后，或者去研究一下你做过的某些事情。在你的 Substack 之外（你在那里涵盖了很多这些内容），你会遵循什么样的学习路径？你认为为了更好地编写高性能代码，有哪些领域是你必须去理解的？

<details>
<summary>Original English</summary>

**Host**: If I'm a software engineer, programmer and I'd like to just get better at writing performance code, I'm interested, you know, maybe after this podcast or or looking into some of the things that you did. What is a learning path you would follow outside of your substack where you cover a lot of these things, but what are areas that you think are kind of like you need to understand these things to like get better at writing performant code?

</details>

**Casey**: 我认为这实际上非常简单，也许还有一点反直觉。所以，我先说一个关于学习编写高性能软件的非常好的消息。好消息是，我们刚才讨论的那种优化，就是那种“热点”类型的优化，比如某人要深入到这里面去，也许他们甚至会用手工编码的方式重写这个例程……

<details>
<summary>Original English</summary>

**Casey**: I think it's actually very simple and perhaps a little bit counterintuitive. So, I'll start with the uh the very good news about learning to write uh performance software. The good news is that optimization of the kind that we sort of talked about, the like hotspot kind where it's like somebody's going to go in here, maybe they're going to even rewrite this routine in handcoded

</details>

<!-- chunk 7/16 -->

### 汇编语言与底层架构对开发者的意义

**Speaker A**: 像直接写汇编语言或者类似这种疯狂的事情，对吧？现在其实已经很少有必要这样做了。你之所以不会再看到“热点优化（hotspot optimization）”被当作一件特别重要的事情，以及我为什么会建议软件架构和避免做出糟糕的决定要重要得多，其中一个原因就是，你可能会用到的很多库其实都已经为你做好了优化。如今的 CPU 极其擅长把糟糕的代码跑得飞快。因此，通常当我们谈论性能问题，或者说带来负面性能的原因时，我们并不是在讨论如何把硬件的最后一丝性能都榨干，而仅仅是确保这个程序不会比它理应达到的速度慢上 100 倍。通常这更多的是需要你重新建立一种意识，去了解计算机应该能做到什么，并确保你做出的软件架构选择能让它发挥出这种能力。如果你做到了这些事情，一般性能差异就会控制在两倍左右，而这比那些慢了 100 倍的人要好上 50 倍，对吧？所以好消息是，为了写出比你今天用到的大多数软件都要好得多的代码，你并不需要掌握极其深奥的知识。那么你需要知道些什么呢？我在 Substack 上主张并关注的是，我认为你只需要完整体验一次学习阅读汇编语言的过程，去看看 CPU 是如何工作的，去感受其中的差异，去理解为什么 Python 运行得很慢——我们在 Substack 上展示了这一点。我最初向大家展示的事情之一就是，我带你仔细看一遍在 Python 中执行“A+B”所需的汇编语言，它庞大到我不得不跳过其中的大部分内容。那段汇编指令简直多得惊人，非常庞大。而如果你在 C 语言中执行同样功能的函数，那只需要一条“add”指令，对吧？所以你需要了解诸如此类的基础知识。如果你去学习阅读汇编语言，去试着看一些底层代码，去测算一些 CPU 时钟周期，只要你有过这种体验——比如花上一两个月的晚上闲暇时间，去理解一些性能相关的东西，自己亲手把玩几个例子，你就能明白其中的差距。

<details>
<summary>Original English</summary>

**Speaker A**: assembly or something crazy like this, right? That's very rarely necessary these days. One of the reasons that you don't see hotspot optimization as a thing that really matters that much anymore and one of the reasons I advise that architecture and and not making bad decisions is much more important is because a lot of libraries already have been optimized for you that you might use. CPUs are incredibly good at taking bad code and running it quickly and so on. So, typically when we're talking about the causes of performance, uh, negative performance that aren't squeezing every last little thing out of the hardware, but rather just making sure this thing isn't running like a hundred times slower than it should be, usually it's more just about having an awareness again of what the computer should be able to do and making sure you're making uh software architecture choices that allow it to do that. And if you do those things, you will generally be within, you know, 2x or something, which is 50x better than the people who are 100x [laughter] away, right? So the good news is in order to write software that's much better than a lot of the software you use today, you don't have to know that much. So what do you have to know? What I argue and what we focus on the substack is I think you just have to go through the experience once of learning reading the assembly language seeing how the CPU works seeing the difference seeing why Python is slow which we show on the sub. So one of the first things I show is uh I walk you through the assembly language necessary to execute uh A plus B in Python and it's so vast that you know I have to skip most of it. It's it's massive right it's like this huge and whereas you know if you have the equivalent function in C it's one instruction add right so you know uh understanding basic things like that if you go through learn to read assembly language learn to look at some code learn to do some CPU timings and you just have that experience just spend you know uh a month or two of nights or whatever you want just understanding some performance stuff and going through a few examples where you play with it and you see the difference

</details>

**Speaker B**: 为了确保我理解准确，你的意思是说，去学习这些并不是因为——比方说你在做 iOS 开发或者是 Web 开发，比如你在写 React——你肯定不会去查看 React 编译出来的汇编代码。但如果你在一个项目中掌握了这些知识，你就能在脑海中构想出底层大概在发生什么，整个架构的分层是怎样的。这样你或许就能做出决定，比如“我到底需不需要这一层抽象？”或者“我要不要直接去用 WebGL ？”如果你只是一名普通的 React 工程师，你可能根本碰不到这些底层逻辑。但同样地，即使你可以跳过这其中的一大堆东西，当面临可维护性等方面的取舍时，现在的你就能明确知道，保留或者去掉这一层到底意味着什么。我是不是可以这样理解？

<details>
<summary>Original English</summary>

**Speaker B**: and and just so I understand you're you're saying do this not because let's say you're doing iOS development or or web development read what React like you you will not look at the assembly that the React does but if you do this on a project you will be able to conceptualize what is likely happening what the layers are and you you might be able to decide like do I want this layer or do I want to use let's say WebGL If you're a React engineer, you probably haven't touched it. But again, you can skip a bunch of those things and it comes to trade-offs with maintainability, yada yada, but that now you you you will know like kind of what you say by keeping this layer or not keeping it and so on. Is it do I get that right?

</details>

**Speaker B**: 本质上是的。最简单的例子就是我们刚刚说到的 Python 的例子。绝大多数人从来没有真正意识到一个事实：同样是执行简单的“A+B”，Python 所消耗的 CPU 指令数量可能比像 C 这样对等的编译型语言要多出上百条。哪怕你仅仅是理解了这一点，就足以让你顿悟：“哦，我懂了。我终于明白为什么在写 Python 的时候，我几乎必须依赖各种库来干活了。”而那些库恰恰是用 C 语言写的。因为只要我打算对海量的数据进行任何操作，我就绝不能纯用 Python 去写，因为每次操作的开销被放大得太离谱了，它会瞬间把性能彻底拖垮。相比之下，那些底层语言就不会有这个问题，对吧？所以，当你理解了这种数量级的差距以及计算机底层真正在发生什么，程序员就能做到心中有数：“如果我权衡一下眼前要做的功能，我能承受这种巨大的性能损耗吗？”通常情况下，你并不需要成为什么性能优化专家才能做出这个决定。你一般都能自行判断：这部分代码究竟能不能容忍比它理想状态慢上 100 倍？对吧？绝大部分人其实都能顺理成章地做出这种判断。如果答案是不能，那么现在的你就知道该怎么做了：“好吧，既然我用的是 Python，我要么得去调一个能干这事儿的库，然后围绕这个库的机制来组织我的代码逻辑；我要么就得引入像 Cython 这类东西，让我在 Python 里能跑一些编译过的代码，通过调用这些底层模块来完成任务。”你看，你现在在写代码之前，就已经具备了做决策所需的认知工具。你能确保在编写程序时，只在那些执行频率极低、或者隔很久才跑一次的环节去承受那 100 倍的性能惩罚。我认为最核心的收获就是这种认知。一旦你懂了，你就能在任何语言中做出好得多的架构决策。因为当你遇到问题时，你只需稍微搜索一下，或者去问问 AI，只要你确切地知道你在寻找什么、该问什么问题，你很快就能得到答案。关键在于，你必须先具备这种“我应该去考虑底层性能”的意识。

<details>
<summary>Original English</summary>

**Speaker A**: Essentially, yes. And like uh you know the simplest example is the Python example. Most people have never internalized the fact that it takes, you know, maybe on the order of a hundred more uh CPU instructions to do an ad in Python than it does to do it uh in an equivalent language like C for the same piece of text, just A plus B compiled in two different, you know, in two different languages, right? And so just understanding even just that is enough for you to kind of go like, "Oh, okay. A, now I kind of understand why if I'm using Python, I kind of have to use libraries to do things." And those libraries were written in C. Because it's like if I'm ever going to do any operations on a on a large number of things, I can't do it in this language because the amplification factor is so high on each operation that it just, you know, kills the performance immediately. whereas these other languages don't have that, right? And so understanding those orders of magnitude and what's actually going on, I think that allows the programmer to know, okay, if I think through what I'm doing right now, can I afford the super slowdown that I'm going to take? And usually I don't think you have to be a performance expert to make that decision. You could usually know like, okay, is this a part of the code that can afford to be 100 times slower than it should be or not? Right? And uh you know most people can I think make that decision fairly logically. And if it's not then now you know like oh okay if I'm in Python then what I got to do is either I got to go find a library call that will do these sorts of things and structure around how that library works or I should maybe get something like Syon or something where I can do compiled stuff inside my Python and make my uh code work around calls out to that kind of code. You know, you now have the tools you need upfront to make sure that when you write the program, you've put the parts that needed this and you've structured the code in such a way that you are only paying the 100x on things that you know are very infrequent or happen like only uh you know once per every so often things like that right that's I think the biggest thing is just the knowledge and once you know you can start to make much better decisions in any language because it doesn't take you very long you know a simple le search or you know asking an AI or whatever is the common practice that you're going to do. A simple bit of that once you know what you're asking for will get you this information back very quickly. Right? You just have to know that you should have been thinking about it.

</details>

### 理解 CPU 架构的实际价值

**Speaker B**: 那么，作为一名软件工程师，你刚才提到去理解 CPU 的工作原理大有裨益。但如果我不是做游戏开发的，我也从不碰底层开发，那这对我来说到底有什么用？因为在大多数情况下，甚至是在学术界或是计算机科学的课程里，大家虽然都会教一点最基础的 CPU 理论，但通常我们也就到写代码为止了。或许你会稍微看看汇编语言，但极少有人会钻研得更深。那些你教过的、真正学了这些底层知识的开发者们，你觉得他们从中获得了什么常人难以获得的收益？

<details>
<summary>Original English</summary>

**Speaker B**: Now, as a software, you mentioned it's good to understand how the CPU works. As a software engineer who is not a games developer, I'm not doing low-level stuff. What does that give me? because for the most part even in academia or or in computer science you know there is some level of of some basic CPU theory taught but usually we just kind of we stop at the code okay maybe you look at the assembly but you rarely go further than that the folks who you know you've you've taught and they they learn these things what do you see them get out of this that they wouldn't otherwise

</details>

**Speaker A**: 所以你现在具体问的是“了解 CPU”这一块的作用对吧？

<details>
<summary>Original English</summary>

**Speaker A**: so you're talking about specifically the knowing the CPU part

</details>

**Speaker B**: 没错，就是了解 CPU，或者说了解 CPU 的运作细节。因为你刚才提到这也是其中不可或缺的一环，也就是说我们不应该仅仅停留在学会看汇编语言上。

<details>
<summary>Original English</summary>

**Speaker B**: knowing about the CPU, knowing about the details about a CP because because you mentioned that that's also part of it, right? It's not necessarily just stopping at assembly.

</details>

**Speaker A**: 其实这里的逻辑是反过来的——我们去学习汇编语言的原因，正是为了看懂 CPU 到底在干什么。所以真正重要的其实是 CPU 这个层面。理解 CPU 之所以重要，是因为你可以把 CPU 想象成一台精密的微型机器，而对于我们所关心的那些主流 CPU，其内部的详细齿轮运转对我们来说通常是保密的。比如 Mac 里的 M 系列芯片，服务器或笔记本里的 AMD Zen 架构核心，或者是英特尔的酷睿系列芯片。这些 CPU 并没有公开详细到能让你搞清楚每一个微小部件具体怎么工作的文档。而且退一步说，就算文档公开了，你大概也没时间去逐一研究，因为我们要讨论的这些机器实在是过于庞大且极其复杂。但是，如果从一个宏观的、更倾向于黑盒的视角来看，一旦我们了解了它们倾向于执行的核心指令大概有哪些，它们在我们眼中就能被抽象成非常易于理解的机器。我们可以把它的运作拆解成几个不同的类别。比如，数据是如何流进和流出处理器核心的？这基本上涉及到加载/存储单元（load/store units）是如何工作的，以及各个层级的缓存（L1、L2、L3，甚至现在有时还有 L0 缓存）是如何运作的。这些机制到底是怎么运转的，为什么要这样设计？其缓存的颗粒度是怎样的？调度策略又是什么？CPU 究竟是如何实际去处理这些数据的？理解机器的这一层逻辑至关重要，因为当你在处理海量数据时，你采用这种方式来组织数据架构与采用另一种方式相比，最终带来的性能差异是巨大的，对吧？再次强调，这些软件架构上的决策与所谓的“热点优化”毫无关系，它们关乎的是所有数据到底是如何在内存中布局的，以及代码访问这些数据的模式是什么，对吧？而这些东西一旦定型，有时是极难去重构的。所以，这是你想去了解这台机器的一个层面。

<details>
<summary>Original English</summary>

**Speaker A**: So the reason for that is more the other way around the the reason to learn the assembly language is so that you know what the CPU is doing. So it's the CPU part that's actually important and the part that's important about it is that the CPU is basically you can think of it as a little machine whose internal gearings we are not privy to because for the CPUs that we care about. So you know an M series CPU in a Mac a Zen core CPU in a server uh or in a laptop or an Intel you know core series those sorts of things. These CPUs are not documented at the level where you're going to be thinking about how each little individual part works. And to that end, it's unclear that you would have time to do so anyway because these are massive, very complicated machines that we're talking about, right? But from a high level, from a more blackbox perspective, they are machines that we can think of in relatively straightforward ways once we know kind of what their core instructions are that they tend to execute. And they break down into a couple different categories. There's how does data move into and out of a core. And this is basically how like load store units work, how the cache levels work, L1, L2, L3. Some we have like we have L0 now sometimes things like this. How does that work and why? What is the granularity of it? What is the policy? How does the CPU go about actually working with those things? Understanding that part of the machine is crucial because when you're working with a lot of data, the the difference can be massive if you structure it in one way versus structuring another way, right? Again, architectural decisions that have nothing to do with hotspots, they're how all the data is laid out and what the access pattern is, right? Things that are very hard to change sometimes. So, that's one part of the machine you want

</details>

<!-- chunk 8/16 -->

### 理解底层架构与性能优化的本质

**Speaker A**：……去理解。关于这台机器，你还需要了解的另一个部分是指令是如何在其中流转的。你知道，很多人都听说过类似“分支预测错误”（branch misprediction）或者“指令缓存未命中”（i-cache misses）这样的词汇。你可能会经常听到这些专业术语，但你并不真正确定它们的实际含义。实际上，它们在概念上都很容易理解。有时候，你很难确切地界定它们到底是如何工作的，因为分支预测器（branch predictors）现在变得越来越复杂等等，但是你仍然可以对它们的行为进行分类，并理解代码是如何通过它们流转的，以及你什么时候该去关心这些问题，什么时候不需要去管。最后，还有执行单元调度（execution unit scheduling）这部分，它是关于了解任何特定类型操作的原始吞吐量（throughput）是多少。比如浮点乘法（floating-point multiplies）、整数加法（integer additions）、除法，或者任何你可能想要了解的操作。对吧？一旦你稍微学习了一点汇编语言，你就会明白它读取的是什么，你会理解它是如何将那些汇编语言指令转化为微操作（micro-operations）的——这正是它实际在做的事情，以及这些微操作是如何在机器中被分配执行的。当你看着他们为了发布新的 Zen 核心架构而展示的那种基本流程图时，你可以看着它然后说：“我大概能知道这台机器的性能了，对吧？”当然不是完全精确，因为就像我说的，会有所有这些小小的边缘情况。如果你真的想成为一个疯狂的性能优化者（crazy optimizer）的话，你确实得去抠这些细节，但我其实并不提倡人们这么做。我认为他们没必要成为那种极其疯狂的优化狂人。如果你喜欢这样做，那很好，这会带来很多乐趣，但这不是最重要的部分。只要看着 C 语言代码，然后想：“好吧，我明白针对这种大小的数据加载，CPU 应该能达到怎样的性能。如果我打算在这个数据上做一堆数学运算，我大概能从中获得多少性能。”你知道的。而且，我认为这应该是软件工程领域的某种基础常识，就像家常便饭一样。你去学校上了四年学来学习这些知识。没有理由你不能在几个月内掌握这些。这并没有那么难。

<details>
<summary>Original English</summary>

**Speaker A**: understand. Another part of the machine you want to understand is how the instructions flow through it. And you, you know, a lot of people have heard about like branch misprediction or things like this. eye cache misses. There's words that you might hear, but you're not really sure what they mean. They're all actually pretty simple to conceptualize. Sometimes they're they're harder to pin down exactly how they work because branch predictors are, you know, getting more and more complicated and so on, but you can still categorize the behavior of them and understand how code flows through it and when you might care and when you won't. And then finally, there's the execution unit scheduling part, which is about knowing what's the raw sort of throughput for any particular type of operation. floatingoint multiplies, integer additions, division, whatever it is that you might want to know. Right? Once you learn a little bit of assembly language, you understand what it's reading, you understand how it turns those assembly language instructions into micro opterations, which it actually does, and how they get distributed through that machine. That flowchart that they put like basically up on the we've announced the new Zen core, that flowchart, you can look at it and go, I know the performance of this machine roughly, right? Not exactly because like I said there's all these little edge cases that if you really want to be a crazy optimizer which again I don't really advocate people do. I don't think it's important that they be like crazy hyper optimizers. If you like to do it great it's a lot of fun but it's not the important part. Just look at the C like okay I see what the CPU should be getting in terms of like what I could do with this size data load that size data load. This is what I could probably get out of it for if I was doing a bunch of like how to do a bunch of like math ops on it you know. And and I think that's that's just something that should be kind of par for the cars to software engineering. You go to school for four years to learn this. There's no reason you can't learn this in a few months. It's not that hard.

</details>

**Speaker B**：是的。另外，我想这仅仅从一种工匠精神（craftsmanship）的角度来看，我们也应该了解我们的工具。我们应该了解我们正在为其编程的机器。显然，我们知道我们的代码，如果你在做 Web 开发，它将会运行在所有这些不同的设备上，或者如果是移动端开发，它会运行在所有这些不同的手机上。但是从概念的角度来看，我们应该能够知道底层正在发生什么。所以我感觉这里面也有一种自豪感。就像退一万步说，你至少也能学到一堆新东西。像我也了解其中的一些知识，但我现在有了更多的动力去深入学习它。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Plus, I guess just from a craftsmanship perspective, like we should know our tools. We should know the machines that we're programming. Obviously, we know that our code will be if you're doing web, it'll be running on all these different things or if it's a if it's mobile on all these different phones, but from a conceptual point of view, like we should be able to know what's going on. So I I feel there's a bit of a pride as well. Like if if nothing else, you would learn a bunch of stuff. Like I I know some of it, but I'm now getting motivation to learn more about it.

</details>

**Speaker A**：我确实认为这里有一个工匠精神的角度。我认为有很多人可能在编程时没有感到满足——我确实从很多人那里听到过这种声音。当他们写一些东西，而那仅仅是某种无定形的、高度抽象的东西时，他们并没有从中获得那么多的满足感。然后，当他们学会如何更深入地观察底层发生的事情时，他们会感到满足得多。即使他们并没有改变自己编程的抽象层级，但现在他们知道自己在做什么了，这让他们感到更加充实，对吧？就好像：“哦，我看到了，而且我明白了为什么这件事情会以这种方式发生，那件事情会以那种方式发生。”这是非常令人满足的，对吧？所以这里面确实有这方面的因素。我同时也想强调另外一点，那就是这是一个关于“百分比”的游戏（percentages game）。如果我们能说服足够多的库维护者（library maintainers）认识到这些底层细节是重要的，并且让所有的库都变得快很多，那么突然之间，所有使用这些库的人的代码也会变得快很多，依此类推。如果 API 开始发生变化，使得库更容易被优化，仅仅是因为人们现在把这些问题想透了，对吧？这就像是具有传染性一样。有越多的人在做性能优化，就需要越少的人去专门做性能优化，[笑声]——尽管这听起来可能有点自相矛盾，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: I do think there's a craftsmanship angle. I think there's a a large number of people who maybe don't feel fulfilled when they I' I've certainly heard from lots of people who when they write something and it's just kind of this amorphous highle thing, they they don't get as much satisfaction out of it. And then when they learn how they can look more deeply at what's going on, they feel much more satisfied. even if they didn't change what level they were programming at, they feel much more satisfied that now they know what they're doing, right? And it's like, oh, I see and I understand why this thing was happening this way and this thing was happening that way, that's very satisfying, right? So there there's an aspect of that. I also want to emphasize another part which is that it's a percentages game. If we convinced enough library maintainers that this stuff was important and the libraries all get a lot faster, all of a sudden all the people using the libraries code gets a lot faster and so on and so forth. If the APIs start changing to make it easier to optimize the libraries because people now thought that through, right? Like it's infectious. The more people are doing performance, the less people need to do performance, [laughter] if that makes it kind of paradoxical, right?

</details>

**Speaker B**：嗯，不仅如此，我确实认为现在仅仅是做到“高性能”仍然是一个很大的优势，你之前也提到了，有些类别的软件纯粹就是通过跑得更快来赢得市场的。为了做到这一点，你需要做这些底层优化；而且如果你知道怎么做这些，也许你就能作为一名软件工程师发现新的机会。也许你现在在自己的职位上并不那么开心，但你可以开启一些新的尝试，或者做一个副业项目，最终它可能变成了一份全职工作，诸如此类。所以我感觉这是个很好的契机。最坏的情况也不过是，你学到了全新的知识。考虑到 AI 的发展（我们稍后会讨论这个），这些底层的知识可能并不会那么容易过时。但是这些东西，它感觉上，就是非常有趣，对吧？感觉它能让你的大脑运转起来。

<details>
<summary>Original English</summary>

**Speaker B**: Well, plus plus I I I I do think that right now there's still an edge in in just being performant again and you mentioned but there are categories of software that is just winning by being much faster and to do that you need to do this and if you know how to do this maybe you're going to spot opportunities as a software engineer maybe right now you're not as happy in your position but maybe start something or do a side project that turned into a full-time thing and so on and so forth. So like I feel there's like and worst case you just learn like net new knowledge which will probably not be as outdated with AI which we we'll get into later but this stuff it it feels it just feels very interesting right like kind of it moves your brain.

</details>

**Speaker A**：确实如此。而且值得庆幸的是，更新这方面的知识其实也没有那么难，因为同样的，你可以去看 CPU 公司提供的那些演示报告，他们会说：“这是我们做出的架构改变。”所以你大概也能在每次有新东西出现时保持了解。你知道的，肯定会有一些小细节悄悄出现，而你可能并不知情；但还是那句话，外面有很多人在运行大量的微基准测试（microbenchmarks），你总会了解到这些信息的，而且他们通常也会帮你把这些细节挖掘出来，对吧？嗯，所以……

<details>
<summary>Original English</summary>

**Speaker A**: It does and thankfully like uh it's also not that hard to update your knowledge because again you get these presentations that that the CPU companies give and they're like here's the changes we made. So you kind of are aware every time a new thing gets you know there's little tiny things that creep in that you don't that you know but again there's people out there who are running lots of microbenchmarks that you will find out about and they often uncover these for you as well right uh so

</details>

### 游戏开发模式与传统软件工程的对比

**Speaker B**：所以……我想谈谈游戏的话题。你在游戏行业里开发游戏可能已经有几十年了。对于我们这些不在游戏行业里的人，你能不能给大家做一个概述？就你所了解的、观察到的或者亲自参与过的游戏而言，一款游戏通常是如何开发出来的？我特别想试着对比一下，你知道的，比如在典型的 SaaS（软件即服务）或者分布式系统里，或者当我们正在构建一个网站或服务时，我们的流程通常是先做规划，我们做一个预估，花几个月或几周的时间去构建它。然后我们将其部署上线，进行监控，接着不断地对它进行调整。然后你知道，时光快进到 5 年后，它现在变成了一个庞然大物，拥有各种微服务，但它始终在不断演进，对吧？感觉我们一直在做大量的这种原型式的迭代。而对于游戏来说，似乎从一开始讨论就很明显会有一个“发布日”（launch）。但是，当你在行业内部，或者当你加入一个游戏工作室时，你能观察到什么？就开发流程是什么样的而言，它与我刚才描述的这种传统的 SaaS 软件或随便什么开发模式相比，有什么不同，或者感觉哪里比较奇怪？

<details>
<summary>Original English</summary>

**Speaker B**: so I I wanted to talk about games you've been you've built games for like decades at at this point can you give an overview for those of us who are not in the games industry how is a game typically built from the games that you know of that you've observed or or you worked on especially trying to compare for you know like in typical SAS or distributed system or or something we're building a a website or service is kind of you plan this stuff you you know we'll we'll do an estimate we'll build it in a few months or a few weeks we deploy it and then we monitor it and then we keep tweaking it and then you know fast forward 5 years later it's now this like gigantic thing with microservices but but it keeps evolving right like it's we do this like a lot of prototyping thing for games It's pretty obvious right from the get-go as we're talking like there there will be a launch but can you when you're inside or when you when you join a game studio like what would you observe there in terms of what the process is like and how it's different or or how it feels weird compared to like this I guess I don't know traditional software SAS software whatever development that is.

</details>

**Speaker A**：好的，我想我可能会这么说，不幸的是我可能并不是回答这个问题的合适人选。因为到了今天，我的知识其实已经有点过时了。近年来发生在游戏身上的一件事情是，我感觉它们在不断地向另一种模式靠拢。我不想绝对地说它们在开发实践上完全转变了，但至少从产品性质的角度来看，游戏已经发生了相当戏剧性的变化，变得更像 SaaS 这样的东西了。你知道，如果你看看当下最受欢迎的那些产品——按收入来算吧，我想“受欢迎”可能很难去精确定义，但我们就说能产生大量收入的那些。如果我们去衡量整个游戏行业的总收入，并看看其中最大的份额是什么，你会看到像《堡垒之夜》（Fortnite）、《Roblox》、《侠盗猎车手 5》在线版（Grand Theft Auto 5 online）等等，还有《我的世界》（Minecraft）。这些东西开始看起来越来越像一种始终在线的“实时服务”（live service），就是那种“我们不断向客户交付增量功能”的模式。所以，我实际上会说，你知道，我并不是那个适合告诉你从内部看现在的开发流程到底长什么样的人，因为我并没有真正去过那些公司里工作。我在那里有朋友，所以我能听到一些事情，但我不是那个能给你提供一幅精确图景的人。但我只是想从我的角度指出，今天的游戏行业实践看起来，与我更密切地亲身参与构建游戏的时候相比，已经大不相同了。

<details>
<summary>Original English</summary>

**Speaker A**: So, I guess what what I would say is unfortunately I'm probably the wrong one to ask because my knowledge is outdated at this point because one of the things that has happened to games recently is I feel like they've moved closer. I don't want to necessarily say entirely in development practices but at least in terms of the nature of the product has changed somewhat dramatically to be more like something like SAS where you know if you take some of the most popular things that are being in terms of dollars let's say so I guess maybe popular is kind of nec might be hard to say specifically but let's just say revenue generating so if we were to measure the total games industry revenue and you look at what are the largest slices of that, you're seeing things like Fortnite, like Roblox, like Grand Theft Auto 5 online, etc., etc., Minecraft. These things are starting to look a lot more like an always on live service kind of we ship incremental features to our customers uh kinds of things. And so I would actually say that, you know, I I'm I'm the wrong one to ask about what that actually looks like from the inside because I haven't actually gone and worked at one of those companies. I have friends there, so I hear things, but I'm not the right one to like give it an accurate picture of it. But I just would point out from my perspective, the game industry practices look different today than they did when I have a more intimate sort of experience with what we were actually building.

</details>

**Speaker B**：但是……我们能谈谈你当初制作游戏时的情景吗？大概是 10 多年前吧。就我的理解，那时的游戏一旦被制作出来、正式发布，可能也就后续打个一两个补丁，然后就某种程度上……你知道的，团队就转移目标了，他们就被解散了。那时候是……

<details>
<summary>Original English</summary>

**Speaker B**: But c can can we talk about it when you were building games which was you know 10 plus years ago when I understand these were the games where they were built they were launched you know maybe they got a patch or two and then they were kind of you know the team moved on they were disbanded. It was

</details>

<!-- chunk 9/16 -->

### 早期游戏开发的限制与挑战 (Constraints and Risks in Early Game Development)

**Speaker A**: 这种有时间限制的开发模式，包含大量的开发工作和一次盛大的发布，结果要么是获得巨大的成功、成为爆款，要么就是彻底的失败，对吧？然后工作室可能就破产了。那么，这种模式到底是如何运作的呢？因为我觉得，虽然今天的许多游戏已经不再面临那种限制，但在那个年代，游戏开发确实受制于各种各样的条件。我非常感兴趣的是，在那些限制之下，究竟是什么样的方法奏效了。

<details>
<summary>Original English</summary>

**Speaker A**: This time box thing that was a lot of development, a big launch, and either it went big, huge hit, or you know, a huge failure right? And then the studio goes bankrupt. So how did that work? Because I feel that's a world where, okay, today a bunch of games don't have those constraints, but it has a bunch of constraints and I'm interested in what worked in those constraints.

</details>

**Speaker B**: 在早期阶段，你并没有那些可以授权使用的商业游戏引擎。所以在那个时期之前……这也是为什么我会说现在的环境与过去有很大不同。你知道的，现在如果你要进行 Web 开发，你可能会想：“我要去弄一个像 React 这样的框架，然后用它来开发产品。”或者，“我要去用一个现成的数据库，比如 Postgres 或者 Oracle，或者随便什么你首选的数据库”，对吧？但是——

<details>
<summary>Original English</summary>

**Speaker B**: So in the early days you didn't have licensable engines. So up until sort of the point like nowadays like this is why I say it's a lot different now than it used to be. You know nowadays you think of web development like I'm going to go grab like a thing like React and I'm going to make this thing or whatever. I'm going to go grab an off-the-shelf database thing, Postgres or Oracle or I don't know like what would be the thing of choice, right? But

</details>

**Speaker A**: 顺便说一句，对大多数人来说，绝对是选 Postgres 而不是 Oracle。

<details>
<summary>Original English</summary>

**Speaker A**: By the way, just definitely Postgres and not Oracle for most people.

</details>

**Speaker B**: 好的，抱歉，抱歉。[笑声] 就当是 Postgres 吧，我并不想在这里冒犯任何人，所以我道歉。所以，好吧，绝对是 Postgres，对不住了，Oracle。是的。

<details>
<summary>Original English</summary>

**Speaker B**: Okay, sorry. Sorry. [laughter] Postgres, uh I didn't want to slight anybody there, so I apologize. So, okay, definitely Postgres, sorry, Oracle. Yeah.

</details>

**Speaker B**: 也就是说，你会去使用某种现成的数据库系统的变体等等。就像我说的，这也更像是现在的人们在做的事情。比如，他们会直接使用虚幻引擎（Unreal Engine），他们不会再去从头开发一个自己的引擎了。他们会从别人那里获取后端服务器的相关组件，里面甚至可能就包含了 Postgres，对吧？谁知道呢？但是在早期，游戏行业根本不存在这些现成的东西。就像我提到的，我当时实际上是在做中间件（middleware）的工作。所以，我算是当时致力于改变这种状况的人之一，比如编写能够被多款游戏复用的代码，而这种复用在当时其实是非常罕见的。

<details>
<summary>Original English</summary>

**Speaker B**: Um, so you're going to go use some kind of a variant of one of these off-the-shelf databases and so on. That's more, like I said, what people might be doing nowadays, too. Like they'll grab the Unreal Engine. They're not going to develop an engine on their own. They'll grab backend server stuff from people. It might even be some Postgres in there, right? Like, who knows? In the earlier days, none of this stuff existed for games. I actually worked, like I said, in middleware at the time. So, I was actually sort of one of the people who was working at the time on maybe changing that a little, like producing code that would get reused throughout games, which was actually fairly rare.

</details>

**Speaker A**: 所以，在过去那个年代，每一款游戏都是自己构建自己的渲染引擎，举例来说是这样吗？

<details>
<summary>Original English</summary>

**Speaker A**: And so back in the day, every game built their own rendering engine, for example.

</details>

**Speaker B**: 没错。确实是这样。如果你把时间往前推得足够远，那么人们在开发游戏时，比如在渲染引擎方面复用代码的程度，充其量也就是：“我从 Dave 还是谁那里拿了一些代码，因为我们当时都在雅达利（Atari）工作，而且有人写了一段很棒的程序，所以我们就拿来用了”，对吧？当时只有这种程度的复用，但并没有那种所谓的现成“引擎”。这种共享技术开始变得稍微普遍一些的时间点，可以说是从 id Software 的做法开始的。当时人们开始有这种概念：“哦，你要用 Doom（毁灭战士）引擎来开发游戏了”，或者“有人要用 Quake（雷神之锤）引擎来开发游戏了”。当时还有 Ken Silverman 制作的 Build 引擎，以及类似的一些东西。

<details>
<summary>Original English</summary>

**Speaker B**: Correct. And so, yeah. Yeah. Yeah. Uh and so really early on, right, if you rewind the clock far enough, uh then yeah, the degree to which people were reusing code for their thing for like their rendering engine, it'd be like cuz I got some code from like Dave or whatever who was or we were both at Atari and somebody wrote this good routine so we used it, right? There was that kind of thing, but there wasn't like this sort of set uh engine. And the time when that sort of maybe you could say first started happening a little more widespread was with things like what ID Software did where they sort of started having like oh you know like someone's going to build something with the Doom engine or someone's going to build something with the Quake engine. There was also the uh the build engine at the time uh made by Ken Silverman and some things like that.

</details>

**Speaker B**: 所以，早期确实有一些少数人制作游戏的案例，但他们的制作方式非常受限。比如，如果我们使用了 Doom 引擎，我们做出来的游戏就会非常像 Doom。所以在大多数情况下，情况依然是人们都在从头开始重新构建几乎所有的东西，至少对他们自己的工作室来说是这样。而且，工作室现有的代码库通常也是该工作室价值的一部分。打个比方，如果你是暴雪（Blizzard），并且刚刚开发了《魔兽争霸1》（Warcraft 1）。那么，把所有的知识和代码积累投入到《魔兽争霸2》的开发中，对你们来说就是一个巨大的优势。因为任何想要制作《魔兽争霸1》竞品的人，都必须从零开始做起。他们必须编写寻路系统，必须制作关卡编辑工具，必须开发渲染技术，他们必须做所有的这一切。所以，这就是传统游戏开发的方式。

<details>
<summary>Original English</summary>

**Speaker B**: So there were some early cases where a few people would make a game, but they were making a game very much like that. Like if we did the Doom engine, we're going to make a game very much like Doom. So it really was the case that for most games, people were rebuilding most of the things from scratch, at least for their studio. And studios often their existing code base was kind of part of the value of the studio, too. Like if you are uh think Blizzard and we just built Warcraft 1. Well, rolling all of that knowledge and code into Warcraft 2 is a huge advantage for us because everybody else who wants to build a competitor to Warcraft 1 has to do all of that from scratch. They have to make the path. They have to make the level editing tools. They have to make the rendering. They have to make whatever. And so, you know, that was how things were traditionally done.

</details>

**Speaker A**: 难怪与软件工程的其他领域相比，游戏行业会如此保密。说真的，简直太封闭了。

<details>
<summary>Original English</summary>

**Speaker A**: No wonder the games industry is so secretive compared to the rest of the software engineering industry. Like seriously,

</details>

**Speaker B**: 过去确实如此。

<details>
<summary>Original English</summary>

**Speaker B**: Used to be.

</details>

**Speaker A**: 至少过去是这样。是的，也许现在情况正在发生改变。

<details>
<summary>Original English</summary>

**Speaker A**: Used to be at least. Yeah, maybe now it's changing.

</details>

### 早期游戏开发的双重风险 (The Twin Risks of Early Game Development)

**Speaker B**: 所以，在那个年代，当你启动一个游戏项目时，通常会面临两个非常巨大的风险。第一个是“引擎风险”：我们是否有能力在技术上制作出满足这款游戏需求的东西？这个风险又可以细分为很多层面：第一，我们到底能不能把它做出来？第二，我们做出来的速度够不够快，以至于我们能够真正可靠地在它上面构建出这款游戏？

<details>
<summary>Original English</summary>

**Speaker B**: And so there were two really big risks typically uh when you started a game project in those days. One was the engine risk: would we be able to make something that would be technically able to do what we need to do for this game? And that risk comes in a lot of flavors: one, will it happen at all? Two, will it happen fast enough for us to actually reliably build the game on it, right?

</details>

**Speaker B**: 我不知道你希望我对这个问题回答得有多详细，如果我偏题太远，你可以随时打断我。但你需要记住的另一件事是，在那个时候——虽然这在今天某种程度上依然成立，但在当时尤为关键——你根本无法花钱买到比你现有设备快得多的硬件。当时并不存在那种分层极其丰富的、你可以随意购买的个人电脑。所以对于渲染引擎来说，你的关卡设计师根本无法在比普通消费者拥有的设备更快的机器上进行游玩和测试。你只能使用你现有的机器，如果这款游戏要在一年后发布，那么你现在的配置大概也就是消费者一年后可能拥有、或者稍微好一点的配置。当然，也有人开始去购买 SGI 工作站之类的高级设备，因为那些机器确实足够快，这就是你当时为了解决性能问题不得不做的事情。

<details>
<summary>Original English</summary>

**Speaker B**: One of the things I mean I don't know how detailed an answer you're looking for for this question. So stop me if I'm going down too many tangents, but one of the things you also have to remember is that at that time, and this is sort of still true today, but at that time it was very important, there was no way to really buy something all that much faster than what you had. There was not a huge strata of PCs that you could, you know, buy or anything like that. So the rendering engine, there wasn't like a way your level designers could like be playing on a faster thing than the consumer would have really. You can only have the machine that you have now and if this game comes out in a year that's sort of roughly what the consumers might have or a little bit, but you know, so there are people who started doing things like buying SGI workstations because those were actually faster enough, right? And things like that is what you know you kind of had to do uh and so on.

</details>

**Speaker B**: 总而言之，当时存在着巨大的引擎风险。有些游戏之所以直接失败，就是因为他们无法在技术上制作出满足自身需求的产品。你可以看到，那些存活下来的公司都是依靠纯粹的技术实力。比如 id Software，他们在制作第一人称引擎方面几乎是无可匹敌的。还有牛蛙工作室（Bullfrog），他们开发了那个伪 3D 引擎，并用于《魔毯》（Magic Carpet）、《地下城守护者》（Dungeon Keeper）等各种类型的游戏。他们的所有游戏都是基于这一个核心技术打造的。引擎风险是一个极其巨大的挑战。那你要如何去规避它呢？你无法规避。你只能咬牙硬抗，对吧？因为你没法从市场上直接买一个现成的引擎，所以你只能咬紧牙关坚持下去。

<details>
<summary>Original English</summary>

**Speaker B**: So anyway, so there was a huge engine risk and some games just failed because they couldn't produce a thing that could technologically do what they needed. You saw houses who survived on technological prowess. You had ID Software that was kind of unrivaled at making those kind of first-person engines. You had Bullfrog who had this engine that the pseudo-3D engine that they did for like the racing games, Magic Carpet, Dungeon Keeper, like they were all based on this, you know, one core tech and all the sorts of things. There's that engine risk that was huge. And how do you mitigate it? You didn't. You were just grit, right? Because there wasn't a way to buy one off the shelf. So, you were just kind of uh gritting your teeth.

</details>

**Speaker B**: 另一个巨大的风险——这个风险在今天依然在一定程度上存在，只是远没有过去那么严重了，因为现在你可以尽早地进行原型设计——这个风险就是：这款游戏到底好玩吗？我们到底在做什么？它有趣吗？好玩吗？当你思考这个问题时，你会发现，我们甚至无法真正运行游戏未来的样子，因为我们还在构建这个该死的引擎，而且我们连一个很好的测试游戏的方法都没有。我们也没法构建出什么像样的最终关卡，因为我们甚至还没有关卡编辑工具，那些工具才刚刚开始开发。

<details>
<summary>Original English</summary>

**Speaker B**: The other big risk, and this one is still somewhat true today, but it's just much less because you can start, you could do prototyping early. The risk is, is the game any good? Like, what are we building? Is it interesting? Is it fun? And when you think about this problem of we can't even really run the game as it will be cuz we're just building this engine and we don't even really have a way to test the game super well. And we can't really build much of a final level because we don't have level editing tools yet. Those are just coming online.

</details>

**Speaker B**: 在那种情况下，想要预测你最终交付的玩法会是什么样子，是极其困难的。有很多著名的游戏，比如 Looking Glass 工作室开发的《神偷：暗黑计划》（Thief: The Dark Project）——这是一款非常著名的游戏，它是潜行类游戏的奠基之作，并开启了《神偷》这个系列。我听那个团队里的人说过，游戏最终的核心玩法几乎是在最后关头才真正成型的，对吧？所以，这款游戏本来可以做得更丰富，或者打磨得更好，但要把这些所有的元素在时机上配合在一起，实在是太难了。它真的是一件极其困难的事情，而且没人有好的解决办法。

<details>
<summary>Original English</summary>

**Speaker B**: Trying to guess what you are actually going to be shipping in terms of gameplay is incredibly hard. And there are games, famous games, um I want to say like Thief the Dark Project, a very famous game, Looking Glass game, uh it was formative in the stealth genre, launched a franchise which was Thief. You know, I want to say uh everything I heard from people on that team was that like the final core gameplay only sort of came together like right at the end, right? And so the game just could have been a lot more, could have been polished a lot more, but it just the timing of these things coming together was so hard. And so it really was an incredibly different thing and nobody really had a way um around it.

</details>

**Speaker B**: 最终，行业内出现了一种推动力。简单来说，就是早期的“垂直切片原型设计”（vertical slice prototyping）。随着游戏的规模越来越大，人们开始觉得：“我们不能再这样下去了，尤其是当我们要在游戏上投入数百万美元的时候，这样盲目开发绝对不行”，对吧？于是他们开始转向这种模式：“听着，我们接下来的做法是，把整个工作室的精力都集中在以最快的速度、构建出一个垂直的玩法切片上。哪怕代码写得再糟糕、再粗糙也无所谓，只要能做出来就行。我们要首先证明这个玩法是吸引人的、是有趣的，然后才开始着手开发其他所有的东西。因为我们根本承担不起不知道这款游戏到底是什么的风险。只要证明了这一点，我们就可以开始制作电子表格，来规划我们需要哪些资产，因为我们现在已经对这款游戏有了信心，我们能看到它在运行，然后这再去填补所有的细节。”对吧。我不是一位游戏历史学家，所以我刚才说的话你最好持保留态度，但我相信那对于整个游戏行业来说，绝对是一个相当巨大的范式转变，当他们开始说“好吧，我们懂了……”的时候。

<details>
<summary>Original English</summary>

**Speaker B**: Eventually, there was sort of this push towards something. Well, it was basically early vertical slice prototyping where as games started getting bigger and people were like, we can't keep doing this, especially if we're going to be putting millions of dollars on like this is not like an option, right? They started to move toward this thing about look what we're going to do is we're going to focus the entire studio on building one vertical gameplay slice as fast as we can, as hacky as we can. Whatever we have to do, do that. Prove that that is engaging to play and then start building out everything else because we simply can't afford to not know what that thing is. And then we can start building like spreadsheets that'll schedule what are the assets we need cuz now we actually believe in the thing, we can see it running, and it fills in all those details right? And that I believe, you know, I'm not a game historian so take what I'm saying with a huge grain of salt, that I believe was a pretty big paradigm shift for the industry when they started going okay we got

</details>

<!-- chunk 10/16 -->

### 游戏引擎普及的后果

**Guest**: 才能真正了解，从那之后，可以说这种“凭感觉”的做法就少多了。

<details>
<summary>Original English</summary>

**Guest**: to actually know and it became much less seat of the pants after that if you will.

</details>

**Host**: 现在我对你的观察很感兴趣。我知道你不是游戏历史学家，但你曾在游戏行业工作，并且现在依然与它保持着联系。当游戏引擎变得普及时，发生了什么？它们不仅变得可以授权——就像我们谈论的针对大型工作室的虚幻引擎（Unreal Engine）——还出现了像 Unity 或 Godot 这样的引擎，现在连业余爱好者也负担得起了。我的意思是，所谓业余爱好者，是指如果你是一个大学生，或者你在做一些业余项目，你已经能负担得起授权费用，并且可以构建出东西来，因为现在这种风险已经不存在了。显然，对于工作室来说，那种风险被消除了。而且我想，现在这也为更多的人打开了大门，让他们有机会去创作一款游戏，因为你不再需要筹集巨额资金来获得极其昂贵的游戏引擎授权。你不再有那种风险。唯一的风险就是，它好玩吗？就整个行业以及开发节奏等方面而言，你观察到发生了什么？我之所以问这个问题，是因为我在想，这是否会与 AI 产生某种相似之处？在过去，情况可能是，好吧，你知道，你需要一位能够……的工程师。

<details>
<summary>Original English</summary>

**Host**: Now I'm interested in your observation. I know you're not a game historian but you were in the industry and you still remain connected to it. What happened when game engines became widespread. they became not only licensable like you we're talking about like Unreal Engine for for larger studios but ones like Unity or or God do which now amateurs could also afford or I mean amateurs in the sense that you're a college kid or or you do some side project you can already afford the license and you can build stuff because now that risk is gone for clearly the studio so that risk is eliminated and it also I guess it now opened up so much more people who who can now have a shot at creating a game because you no longer have to either have this massive amount to license this super expensive game engine. You no longer have that risk. The only risk is is it fun. What have you observed happen in terms of both for the industry for for for development pace those kind of things. And the reason I'm asking because I I I wonder if there's going to be a parallel with AI where okay, you know, like you needed you needed to have an engineer who was

</details>

**Guest**: 对。我感觉游戏行业可能会给我们一些暗示，让我们知道在更广泛的行业中可能会发生什么。

<details>
<summary>Original English</summary>

**Guest**: right. I I I feel games might give us a bit of a a hint of what we might expect at the broader industry.

</details>

**Guest**: 我得说，对于一个没有亲身经历过那段游戏行业历史的人来说，能注意到这一点，这确实是对当时情况非常精彩的分析。这让人印象深刻，我首先得说这一点。而且我完全同意你的看法。过去当有人问我关于 AI 对游戏的影响时，我也差不多是这么说的，我说过，很不幸，可授权引擎的出现基本上就已经算作是我们经历过的“AI 转型”了，而且我很遗憾地告诉你们，这个消息可能没那么积极。当然，早期确实发生了一些积极的事情，因为正如你所说，它让那些原本无法召集必要的技术人员来开发出有竞争力的引擎的人，也有了制作游戏的能力。赋予他们制作游戏的能力是一件非常重要的事情，这也让许多人能够实现某种艺术表达，而这在早期是他们根本无法做到的。这通常是一个净收益，因为这只是意味着有更多的游戏问世。也许其中有些游戏没那么好，但是，你知道，一些现有的游戏本来也没那么好，所以这没什么区别；但随后，你会从那些本来根本无法制作游戏的来源那里，得到一些非常酷的游戏。这值得点赞。问题在于，它迅速加速演变成了一种相当糟糕的局面，你面临的是海量的游戏发布。我认为到了目前这个阶段，我想说，Steam 上每年发布的游戏数量大约有数万甚至十万款左右。数量如此庞大，以至于你的游戏基本上根本不可能再被自然地注意到了，就这么简单。所以从本质上讲，这是一个非常令人头疼的问题，市场上充斥着各种产品。你知道，以前的情况是，如果你做了一款高质量的游戏，如果它很好玩，人们就会发现它，因为当时的游戏太少了，只要有人玩到了这款好玩的游戏，就会告诉其他人，然后它就会被购买。对吧？口碑传播，或者仅仅是放在店面上展示，这就差不多足以让你，你知道，把游戏的名气打出去了。你不需要庞大的营销预算之类的东西。快进到今天，我们面临着这种海量的游戏涌入。重申一遍，这还是在 AI 出现之前，仅仅是因为现在的准入门槛非常低。而且，你真的需要一种策略来确保你的游戏被别人发现。有时候，有没有可能一款没有任何营销计划的小型独立游戏被人们发现并成为超级爆款？当然，这种事偶尔还是会发生，但你成为那款游戏的几率几乎为零。所以，你现在需要一个营销策略，一个真正的营销策略；如果没有营销策略就进入游戏市场，还指望着能卖出可观的销量（可能最多也就几千份以上吧），那真的非常不明智。如果你想让游戏达到合理的销量，你必须对人们将如何发现这款游戏心里有数。

<details>
<summary>Original English</summary>

**Guest**: So that is actually I would say that's a brilliant analysis of the situation for for not having lived through games and for noticing that. Uh that's that's impressive. I'll say that first. Uh and I totally agree with that. I've I've said to people in the past who have asked about sort of AI impact on games in that sense and I've sort of said as much I've said like the licensable engine thing kind of was our AI transition already unfortunately and uh I regret to inform you that the news is not probably that positive. So there are some uh definite positive things that happen early on because as you say uh it opens up the ability to make games to people who could not have uh marshaled the technical sort of uh the sort of the technical staff necessary to produce a competitive engine. And so giving them the ability to make games is a pretty important thing. and it allows a bunch of people to make sort of some artistic expressions that made they just wouldn't have been able to do early on. That tends to be a net positive because you just have some more games coming out. Maybe some of them aren't that good, but ex, you know, some of the existing games aren't that good. That's not that different, but then you get some really cool games coming from some sources that just simply wouldn't have been able to do it. Thumbs up. problem is it rapidly kind of accelerates into this kind of a nasty scenario where you just have massive numbers of releases. And I think at this point we're at the point where I want to say Steam games are in the like tens of thousands or hundred thousand per year or something like that. It's it's so massive that there is no way that your game will be organically noticed anymore pretty much period. So essentially it's this really nasty problem where you just have the market flooded with products and there you know it used to be that if you made a quality game if it was fun people would find it because there were so few games that someone would play the fun one and tell people about it and it would get purchased. Right? Like word of mouth or just exposure on a storefront would be all you really needed to get, you know, sort of the word out about a game. You didn't need a huge marketing budget or anything like that. Fast forward to today where we have this sort of massive influx of games. Again, pre-AI, it's just because now the barrier to entry is very low. Uh, and you really need a strategy to make sure your game gets found. Is it possible that sometimes, you know, a small indie game with no marketing plan or nothing will get discovered uh and become a huge hit? Absolutely. It does still happen once in a while. the chances that you will be that game are like zero. So, you kind of now need a marketing strategy, a real marketing strategy, uh, and going into the market for games without one and expecting to sell any significant number of copies, uh, above, you know, maybe a few thousand at best is really unwise. If you want to hit reasonable numbers of sales of a game, you have to have an idea of how people will find out about this about this game.

</details>

**Host**: 所以，如果我没理解错的话，听起来游戏本身质量好只是基本门槛（table stakes），但这本身还不够，对吧？分发、营销、让人们听到这款游戏，才是更为重要的差异化因素，因为现在市面上的好游戏实在太多了，而且现在的开发也变得更容易了。

<details>
<summary>Original English</summary>

**Host**: So, if I'm getting this right, it sounds like the game itself being good as table stakes, but not enough on its own, right? That distribution, marketing, getting people to hear about the game is much more of the differentiator because there's just too many good games out there and now they're easier to create.

</details>

**Guest**: 我认为完全正确。这就是现在令人遗憾的现实。这是一笔划算的交易吗？我不知道。但事情就是这样发生了，这就是我们目前在行业中所处的阶段。

<details>
<summary>Original English</summary>

**Guest**: I think that's exactly right. And uh and that's just the unfortunate reality of it now. Was that a good trade? I don't know. Um but that's what happened. And so that's where we are in the industry.

</details>

### 新游戏与老游戏的竞争

**Host**: 另外，我还听说了另一件事，那就是新游戏不仅要和其他新游戏竞争，还要和老游戏竞争，对吧？比如前几天，我花了好几个小时玩《死亡拉力赛》（Death Rally），这是一款 90 年代的游戏。每年都有越来越多好玩的游戏可供选择。它们都在挤占留给新游戏的时间。

<details>
<summary>Original English</summary>

**Host**: Now, there's this other thing that I heard about which is how new games not only compete with other new games, but with old games as well, right? Like the other day, I spent a few hours playing Death Rally, which is a game from the '9s. And every year, there's more and more good games to play. They all take away from the time that the new games have.

</details>

**Guest**: 是的。而且这个问题只会变得更糟，因为过去游戏行业可以依赖、而现在很难再依赖的一点是，老游戏在消费者关注的技术方面会显得过时。现在，我们确实也跨过了一个门槛，在这个门槛上，仍有一部分市场受众非常在意最新的技术，比如光线追踪照明之类的东西，以及更加逼真的照片级渲染等。但从收入来看，很大一部分游戏市场其实并不那么在乎游戏看起来怎么样——在某种意义上，我们今天所做的任何画面都已经足够好了。因此，如果 10 年后的游戏因为某些原因看起来更好了，实际上也没有人会认为这是销售上的巨大差异化因素。回到 1995 年，技术进步在销量上是一个巨大的差异化优势。如果你推出了一款看起来很棒、充分利用了当时硬件性能的游戏，哇，跟早期的游戏相比，它看起来更酷，操作响应更灵敏，还有其他种种优势，对吧？因此，这也会加剧你所说的那种情况的发生。我可以去玩一款老游戏，因为它在视听方面并没有明显的过时感。我不需要是一个复古游戏爱好者，才会去玩一款 2017 年出的游戏。它看起来依然很不错，对吧？所以这是一点。我想提的另一点，我们刚才其实也提到了，这也直接印证了你的观点，那就是实时服务型游戏（live service）现在非常突出。人们只需要登录游戏，然后玩上好几个小时的《堡垒之夜》（Fortnite）之类的。这也夺走了原本可能会花在购买某款独立游戏、甚至新款 3A 大作上的潜在收入。所以你面临着这些既得利益者，人们把时间花在玩《我的世界》（Minecraft）上，或者花在玩《英雄联盟》（League of Legends）或《Dota》上，这占据了他们大量的时间。这是零和博弈，对吧？人们的时间是有限的，就像网飞（Netflix）或其他任何平台一样，只能把时间花在某些特定的地方。他们必须开始考虑，你知道的，他们是在和其他所有人竞争用户的娱乐时间。

<details>
<summary>Original English</summary>

**Guest**: Yes. And that uh problem will only get worse because one of the things that the game industry could rely on in the past that is much harder to rely on now is that older games would look dated technologically in ways that consumers cared about. And we have now kind of also crossed the threshold where there is a segment of the market where people really do care about the latest like ray trace lighting and all these sorts of things. and you know more photorealistic rendering or whatever it is. But a large portion of the gaming market by revenue doesn't really care what the game looked like all that much uh in a sense that whatever we're doing today is good enough. So 10 years from now if the games look much better for some reason no one will really think of that as a huge differentiation differentiator in terms of sales. You go back to 1995 and technological advances were a huge differentiator in terms of sales. You come out with something that you know looks good that takes advantage of the hardware of that day and boy did it look cooler and feel more responsive and all these other things as compared to earlier titles, right? And so that's also going to increase the degree to which the thing that you're talking about will happen. I can go play an older game because it doesn't feel obviously dated in an audiovisisual way. I don't have to be an appreciator of retro gaming to go play something from 2017. It just looks fine probably, right? So, there's that. The other thing that I'll just mention, which we kind of already touched on, but that ties directly into your point, is that also live service is such a prominent thing now. People are just logging on and playing Fortnite for several hours or something. that's also taking away from the possible revenue that might be spent on buying some indie game or some new AAA game even. So you have these sort of incumbents, people playing Minecraft, spending their time playing Minecraft, spending their time playing um League of Legends or Dota and that's taking up a huge amount of their time that's it's it's zero sum, right? They can only they can only spend their hours in certain places just like Netflix or anywhere else. They have to start thinking about, you know, they're competing with everyone else for entertainment hours.

</details>

### 3A 大作的开发周期

**Host**: 好的，那我得问问你这个问题。《侠盗猎车手 6》（GTA 6），在 2026 年，这是一个我们拥有比以往任何时候都更好的工具、而且我们可以比以前更快地构建软件和游戏的时代，它是怎么一回事？比如，为什么游戏的开发需要 10 年甚至更长的时间？这是某种特例，还是说 3A 游戏的开发需要耗费很多很多年，这一点根本就没有改变过？你认为这到底是怎么回事？

<details>
<summary>Original English</summary>

**Host**: Okay, so I need to ask you this. GTA 6, how is that in 2026 at a time when we have better tools than we have ever before and we can build software and games faster than before? Like how do games take 10 plus years to develop? Is this some kind of outlier or has AAA game development taking many many years just not changed at all? What do you think is going on here?

</details>

**Guest**: 从玩家的角度来看，我可以理解为什么有人在看到这种情况时会说：“哇，《侠盗猎车手 6》（Grand Theft Auto 6）已经开发了这么长时间了。这怎么说得通？”或者，你知道的，诸如此类的话。但从商业的角度来看，你必须……

<details>
<summary>Original English</summary>

**Guest**: So from a player's perspective, I can understand why someone would look at it and go, "Wow, Grand Theft Auto 6 has been in development a long time. How does that make sense?" Or, you know, something like this. From a business perspective, you have to

</details>

<!-- chunk 11/16 -->

### 《侠盗猎车手 6》的商业定位

**Speaker A**: 我明白《侠盗猎车手 6》（Grand Theft Auto 6）并不是一款他们打算卖给那些仅仅为了玩游戏而玩游戏的玩家的作品。从产品定位的角度来看，它的意义并非如此，对吧？从产品角度而言，《侠盗猎车手 6》是为了取代《侠盗猎车手 5》（Grand Theft Auto 5）而存在的。如果我没记错的话，《侠盗猎车手 5》在当时绝对是世界上创造收入最多的娱乐产品，遥遥领先于其他所有产品。那款游戏的在线部分创造了大概数十亿美元的收入。就像我说过的，我不是游戏行业的历史学家，所以你们听听就好，不要完全当真，但《侠盗猎车手 5》可以说是《堡垒之夜》（Fortnite）出现之前的“堡垒之夜”，如果你愿意这么比喻的话。它们都是那种能够创造巨额收入的大型实时服务型产品。因此，从 Rockstar 或 Take-Two 的角度来看，《侠盗猎车手 6》不仅仅是“让我们尽快把下一部《侠盗猎车手》做出来，因为卖这款游戏能赚钱”那么简单。它的意义在于“我们要用一个全新的产品，来取代我们有史以来打造过的最赚钱的产品，而且这个旧产品目前依然在为我们创造巨额利润”。你大可以相信，他们绝对想要确保自己能把这件事做对，因为你最不希望看到的情况就是：你发布了一款新产品，它不仅蚕食了旧产品的市场份额，而且创造的收入还比以前少了。对吧？所以我敢肯定，他们围绕《侠盗猎车手 6》所做的规划，绝不仅仅是试图制作出一款粉丝会喜欢、会作为原汁原味的单机游戏体验去购买的《侠盗猎车手》游戏。我确信他们非常看重这一点。单从声誉和艺术层面来说，我肯定那些团队里有很多人非常在乎单机体验。但从商业角度来看，我也确信他们在如何设计游戏的在线服务部分上投入了大量的思考和工作。那是一项巨大的工程，你知道的，我敢肯定他们也为此规划了相当长的一段时间。

<details>
<summary>Original English</summary>

**Speaker A**: I understand that Grand Theft Auto 6 is not a game that they are selling to players who are going to play the game. That's not what it is from a product standpoint, right? What Grand Theft Auto 6 is from a product standpoint is a replacement of Grand Theft Auto 5. Grand Theft Auto 5 at the time was, if I'm not mistaken, by far the most revenue generating entertainment product in existence. The online part of that game was generating like billions of dollars. And like I said, not a game industry historian, so you know, take what I have to say with a huge grain of salt, but Grand Theft Auto 5 was kind of like Fortnite before Fortnite, if you will. They were a huge huge live service revenue generating product. So from Rockstar or Take 2's perspective, right, Grand Theft Auto 6 is not just let's try to get out the next Grand Theft Auto as soon as we can cuz we'll make money selling that title. It's a we are going to replace the most profitable thing we have ever built, which is still generating a ton of money for us, with a new thing. And you can better believe that they want to make sure that they are going to do that right because the last thing you want to do is ship a new product that cannibalizes something from your old product and then is less revenue generating. Right? So I'm sure that their planning around Grand Theft Auto 6 is not just about trying to produce a Grand Theft Auto that their fans will love and will buy as the original singleplayer gaming experience that it was. I'm sure they care very deeply about that. Just from a reputational and from an artistic standpoint, I'm sure there's a lot of people on those teams who care about that. But from a business standpoint, I am sure there's also been a tremendous amount of thought and work put into what does the live part look like? And that's a huge undertaking, you know, that I'm sure that they've been planning for quite some time as well.

</details>

**Speaker A**: 所以，他们现在正在做的是一件规模极其庞大、极其宏伟的事情。它能取得多大的成功？我完全不知道。但它绝不仅仅是一部简单的《侠盗猎车手》新作，至少我不会这么看。我认为《侠盗猎车手 5》对他们来说多少是个意外之喜。我不觉得他们事先知道它能在网络上创造那样惊人的收入。我的意思是，也许他们有过期望，但我不认为他们知道它会成为那样一个超级印钞机。因此，这真的是第一款他们确切知道自己将拥有如此庞大受众基础的产品。在《荒野大镖客：救赎》（Red Dead Redemption）上，他们有点像是试过水，做出了《荒野大镖客：救赎 2》。他们做了类似的事情，试图加入在线模式。但我认为它并没有取得像《侠盗猎车手》那样巨大的成功。《侠盗猎车手 6》是他们第一次为自己的旗舰产品推出真正意义上的换代更新。所以，你知道，这相当于谷歌搜索之类的产品进行一次全面的重新发布，这就是他们现在正在做的事情。呃，所以如果我是那个项目的负责人，我肯定会紧张得直冒冷汗。因此，我确信他们在这个项目上投入了大量的精力与思考。而且我敢肯定，这是一项非常巨大的工程。

<details>
<summary>Original English</summary>

**Speaker A**: So, it's a massive massive thing that they're doing here. How well will it succeed? I have no idea. But it is not just a new Grand Theft Auto is I guess the way that I would look at it. Grand Theft Auto 5, I think, was somewhat of a surprise to them. I don't think they knew it was going to generate that kind of online revenue. I mean, maybe they had hopes, but I don't think they knew that it would be that kind of a massive money maker that it was. And so, this is the first product really where they know they will have the audience. For Red Dead Redemption, they kind of tried to do Red Dead Redemption 2. They did a similar thing where they tried to have the online thing. It didn't I don't think it hit nearly as big as Grand Theft Auto. Grand Theft Auto 6 is the first time they're shipping a true update to what is their flagship. And so, you know, it's equivalent to like a relaunch of Google search or something like that is what they are doing here. Uh and so I I you know, I'm sure if I was in charge of that project, I would be sweating bullets. So, I'm sure that they are putting a lot of thought into it. Uh, and it's a very massive undertaking, I'm sure.

</details>

### 关于“整洁代码”与性能的争议

**Speaker B**: 我想把话题转向 SoftwareCraft。你制作了一个名为《整洁代码，糟糕性能》（Clean Code Horrible Performance）的视频/文章，在里面展示了鲍勃大叔（Uncle Bob Martin）基于多态的重构模式，其运行速度比普通的表开关（table switch）版本慢了大约 1.5 到 15 倍。我们能聊聊大家对这个作品的反应吗？

<details>
<summary>Original English</summary>

**Speaker B**: >> I'd like to switch gears to SoftwareCraft. You made this video titled Clean Code Horrible Performance, an essay/v video showing how Uncle Bob Martin's polymorphism based refactoring pattern runs about 1.5 to 15 times slower than a plain table switch version. Can we talk about the responses to this piece?

</details>

**Speaker A**: 嗯，我想我可以介绍一下背景。那个内容差不多是我在 Substack 上开设的课程的一部分。所以，它是与 Substack 上的一系列其他视频相配套的。我想我要说的第一点是，我觉得大家对它的反响非常积极。我其实有点惊讶。当然也有很多人不喜欢它，别误会我的意思。毫无疑问，这是有争议的，但我也很惊讶居然有那么多人对它充满热情。但我想说的是，我真的不认为这应该引起这么大的争议，因为有一种情况是，人们只是想用“整洁代码”（clean code）这个词来指代他们喜欢或者认为写得规范的代码，这是你无法反驳的，对吧？因为那只是，你知道的，我可能也有我自己心目中认为的整洁代码的标准，而且显然我不认为那是坏事，对吧？这就像是，这是我对好代码长什么样的理解。所以，如果你的“整洁代码”概念仅仅是指你想要的任何东西，你知道，任何你碰巧认为是不错的编程实践，我可能也会同意那些编程实践，我不知道。所以在这个特定的视频里，我专门讨论的是那些被倡导的非常具体的规则，比如，有人说不要让函数的长度超过特定的行数，或者是诸如此类的东西，对吧？还有，代码不应该在运行时知道类型，或者别的什么要求，对吧？关于这个有很多类似的规则。比如总是优先使用多态，对吧？如果你去审视这些东西，它们其实就是糟糕的编程实践。我真的不知道还能用什么别的方式来形容它们。当你把它们放在一起时，它们并不能很好地融合。单独来看，其中一些可能没问题。所以，举个例子，如果你真的偏好大量的小函数，如果编译器能够看到所有这些函数，并知道它可以安全地将它们内联，在必要时将它们折叠起来，那其实是没问题的。

<details>
<summary>Original English</summary>

**Speaker A**: >> Well, I guess I can put that in context. So, that is sort of from that course on the Substack. So, it kind of goes with a bunch of other videos that are part of like the Substack thing. I guess the first thing I'd say is I feel like the response to it was very positive. I was kind of surprised. There are plenty of people who didn't like it. Don't get me wrong. It's controversial to be sure, but I was surprised at just how many people were enthusiastic about it as well. But what I would say is it's really I I don't really think it's should be so controversial because there's one thing where people want to just use the term clean code to mean code that they like or think think is written properly and that's not something you can argue against, right? Because that's just, you know, I probably have a version of what I think is clean code and obviously I don't think that's bad, right? Like it's it's my idea of what good code looks like. So if your idea of clean code is just whatever you want it, you know, whatever you happen to think are good programming practices, I might agree with those programming practice, I don't know. So in this particular video, I was talking specifically about the things that were advocated that are like very specific things that are said like don't have functions over a particular length or these sorts of things, right? Uh things should not know the type at runtime or whatever, right? There's all these like kind of rules about it. Preferring polymorphism always, right? If you look at those things, they're kind of just bad programming practices. I I don't really know how else to say them. They don't mesh well when you put them together. In isolation, some of them might be fine. So, for example, if you really prefer lots of small functions, that's actually fine if the compiler can see all those functions and know that it can safely inline them and collapse them as necessary.

</details>

**Speaker A**: 我想很多人在这个视频里忽略了这一点，因为这个视频很短，所以我没有详细解释任何东西。但当你有大量这种微小、极小的小函数时，就会产生大量冗余的代码。在 C++ 里，如果它们全都是虚函数（virtual functions），比如说，编译器就无法确定到底哪些函数会被调用，诸如此类。即使你在里面加上像 `final` 这样的关键字，人们对于代码是如何工作的依然有很多奇怪的认知。你可以自己去进行测试。当你有大量这样的小函数时，如果它们都是静态定义的（statically defined），而且不是虚函数调用，如果它们只是已知的调用，或者仅仅是成员函数。当我说静态时，我的意思差不多是指仅仅在当前翻译单元（translation unit）内是已知的，而不是外部可见的。编译器可以把这些东西放在一起，折叠掉所有的冗余代码，实际上它能生成出一种运行速度非常快的合理的代码。它还可以做一些事情，比如在需要向量化，以便在 SIMD 之类的环境下运行时，拓宽代码路径。编译器有各种各样的选项，可以把那些在运行时表现不佳、从根本上来说写得并不怎么好的代码，转化为高效的代码，因为它可能做得到，毕竟现在的优化编译器、优化编译器能做出的事情其实是非常伟大的（heroic），它们能做到各种各样的事情。然而，相反地，如果你使用了所有那些被推荐的东西，你就彻底阻断了编译器去执行那些优化的能力。因为如果它无法判断在运行时会发生什么，如果它必须保留你在这里替换了一个不同类的可能性，或者类似的情况，那你就会陷入这样一种境地：编译器无法进行任何优化工作。

<details>
<summary>Original English</summary>

**Speaker A**: This is a this is a part a lot of people missed about the video I guess because it's a pretty short video so I didn't explain anything in detail but a lot of redundant code happens when you have lots of tiny you know little these little tiny functions and if they're all virtual functions in C++ let's say the compiler can't know for sure which ones of them are being called and so on even if you put things like final in them there's all people have a lot of weird beliefs about how the code works you can just go do this testing when you have lots of these little functions if they're all like statically defined and aren't virtual calls if they're just known calls like or just member functions. When I say static, I kind of mean just known to the to the translation unit, not external. The compiler can put those together, collapse all of the redundant code and actually produce something reasonable that will run pretty fast out of that. It can also do things like widen the code path if it needs to vectorize to like run in SIMD and stuff. The compiler has all these options to take what is fundamentally not particularly great code in terms of how you would want it to run at runtime, but it might be able to turn it into that because you know compiler optimizing uh optimizing compilers are pretty heroic these days and the sorts of things they can do. If instead you use all of these, you know, things that were recommended, you completely block out the compiler from a being able to do those things. Because if it can't tell what it's doing at runtime, if it has to leave open the possibility that you substituted in a different class here or something like that, then you end up in a situation where the compiler can't do any of that work.

</details>

**Speaker A**: 人们错误地以为这仅仅是因为虚函数调用的代价太高了，或者是类似的原因。根本不是那么回事。代价不在于虚函数调用本身。我们可以把它当成一个单独的话题来讨论。因为你也可以去分析那个代价。它其实与它是否是虚函数没有太大关系。它与很多其他事情有关，比如分支预测（branch prediction），以及有多少东西被压入堆栈（stack），还有其他等等，对吧？但真正的代价是编译器无法进行任何优化。那才是真正的代价所在。而且这种代价可能会非常严重。我认为，我在视频里展示的性能下降，与如果你在实际生产环境中真的有海量代码这样做所导致的性能下降相比，其实是相当温和的了。我觉得这个视频的反响还不错。你知道，这个视频的播放量非常大，而且有很多人似乎真的非常喜欢它。我本来以为它可能会引发比现在更大的争议。所以我对这个结果感到满意。但是，是的，我的意思是，我想我要说的是，直到今天，所有那些东西依然是正确的。我觉得让人们听到这些观点是件好事，因为……

<details>
<summary>Original English</summary>

**Speaker A**: And people mistakenly think that this is just because like virtual function calls cost too much or something like that. That's not what it is. It's not the cost of the virtual function call. We could talk about that as a separate thing. Um because you you can analyze that cost as well. It doesn't have much to do with specifically whether it's virtual or not. has to do with a lot of things like branch prediction and how much stuff is getting pushed on the stack and whatever else, right? But it's the cost of the compiler not being able to do any optimizations. That's the actual cost. And that cost can be severe. I showed only I think a pretty mild degra degradation compared to what you would actually see in production if you really had a huge number of things doing this. And I think it landed pretty well. It, you know, it's a very widely viewed video and a lot of people seem to really like it. I thought it would be, you know, probably even more controversial than it was. So, I was pleased with that. Um, but yeah, I mean, all that stuff remains true today, I guess, is what I'd say. And I think it's good for people to hear because

</details>

<!-- chunk 12/16 -->

### 关于测试驱动开发 (TDD) 的看法

**Speaker A**: 他们需要听到相反的观点。我认为你可以写出易于维护和阅读的代码，即使它不以那种方式遵循那些原则，也不会产生那些问题。我不认为你必须做那些事情。因此，我认为值得探索其他选项，它们仍然易于维护，是好代码，但允许编译器做正确的事情。

<details>
<summary>Original English</summary>

**Speaker A**: ...they need to hear opposing viewpoints. I think you can write code that is maintainable and easy to read that doesn't follow those principles in that way and that doesn't have those problems. I don't think you have to do those things. So I think it's worth exploring other options that are still maintainable, that are good code, but that allow the compiler to do the right thing.

</details>

**Speaker B**: 你对测试驱动开发 (TDD) 有什么看法？你知道的，就是先写测试，然后再写业务逻辑。你之前也稍微谈到过这个，因为这曾经是一个非常流行的实践，尤其是在 2000 年代构建服务的时候。但后来有些做法变得有些过时了，现在也不清楚随着 AI 智能体的发展，它是否会回归。

<details>
<summary>Original English</summary>

**Speaker B**: What is your take on test-driven development? You know, when you write the test first, then you write the business logic. You've talked a little bit about this as well because it's a practice that used to be super popular, especially when you're building services. Some of those things, especially in the 2000s, kind of got a little bit out of fashion, and now it's unclear if it'll come back or not with agents.

</details>

**Speaker A**: 我对此并没有什么特别激进的看法。我的观点非常务实，那就是：如果你能确认测试总体上能节省时间，那通常就是我会去强调的。换句话说，如果创建和维护测试所花费的时间，实际上能为我们节省总的开发时间——因为它们能发现那些我们在生产环境中很难找到，或者一旦发布出去修复成本极高的 Bug——那这就太好了。我以前也用过它，就像我提到在 RAD Game Tools 工作时，我有一个回归测试工具，专门跑在那些我编写的核心库上。那虽然不能真正称为“库”，而是一些核心例程，为了确保任何我能为客户测试的东西我都尽量测试了。所以我觉得有些时候是适合进行测试的。

我想说，关于测试驱动开发，我不喜欢的部分是“测试驱动”这一部分。我不认为开发应该由测试来驱动。我认为测试是一件你应该意识到的事情。你应该知道你的测试选项有哪些，并且你应该针对测试做出明智的工程决策。那么，这个决策有可能是“对于这个特定的项目，我们将主要由测试来驱动”吗？是的，你可能会做出这样的决定。但你真的不应该默认将开发视为主要由测试驱动的事情，因为对于某些其他项目来说，这可能是一个非常糟糕的决定，最终会导致你按照这种方式做付出更多的成本。

所以，就像对待大多数事情一样，我提倡对测试采取务实的态度。你应该了解测试的成本、开发和维护测试的成本，以及如果测试使得修改代码库变得更加困难（因为测试也必须重写，从而导致你不去进行那些本该进行的修改）时，对你的代码库造成的成本。所有这些因素都应该在你的脑海中，你应该针对你的测试策略做出明智的决定。如果经过明智思考后做出的决定是，我们要在这个项目上进行大量测试，那这可能就是一个好决定。我不认为你可以对应该有多少测试给出一个绝对的说法。有些项目可能不需要太多测试，也许有些项目应该有很多测试。我认为，知道自己正在做哪一种情况，是一个优秀软件工程师应具备的素质。

<details>
<summary>Original English</summary>

**Speaker A**: I don't have that much of a spicy take on that one. My take is very pragmatic, which is that if you can identify tests that will save time in total, that's usually what I try to emphasize. In other words, if the amount of time it takes to create and maintain the tests will actually save us total development time because they will identify bugs that would be hard for us to find in production or would be very costly to get to if they got out, then great. And I've used them before. Like I talked about working at RAD Game Tools, I had a regression tester that I ran on the core libraries there that I had written. You know, they're not really called libraries, but the core routines to make sure that anything that I could be testing for our customers, I sort of was. And so I think there's good times for testing.

I would say the part that I don't like about test-driven development is the "test-driven" part. I don't think development should ever be driven by tests. I think tests are a thing that you should be aware of. You should know what your options are for testing and you should make intelligent engineering decisions about tests. Now could that decision be that for this particular project we are going to drive it primarily from the tests? Yes, that could be a decision that you make. But you shouldn't really think of development as something that is primarily test-driven like by default, cuz that might be a very bad decision for some other project where it just ends up costing you more to have done it that way.

So like with most things, I would advocate for a pragmatic approach to testing. You should understand the cost of testing, the cost of developing and maintaining the test, and the cost to your codebase if it makes it harder to change your codebase because tests have to be rewritten and you therefore don't make changes you should make. All of that stuff should be in your brain and you should make an intelligent decision about what your testing strategy is. If that decision intelligently made turns out to be we are going to have a lot of testing on this project, that may well be a good decision. I don't think there's an absolute thing you can say about how many tests there should be. Some projects probably shouldn't have very much. Maybe some projects should have a lot. And I think knowing which of those you are doing is part of being a good software engineer, is I guess what I would say.

</details>

### 好代码与优秀软件工程师的标准

**Speaker B**: 你提到了成为一名优秀的软件工程师。但在我们深入探讨什么是优秀的软件工程师之前，对你个人而言，到底什么是“好代码”？

<details>
<summary>Original English</summary>

**Speaker B**: You mentioned being a good software engineer. But before we get into what is a good software engineer, what does good code mean to you specifically?

</details>

**Speaker A**: 对我来说，好代码通常意味着你写出的东西，尽可能直接地表达了机器为了解决问题实际需要做的事情。同时，希望你已经恰当地找到了将其分解成易于理解的片段的方法，并以容易让人（特别是你自己）理解的方式对这些片段进行了命名，因为你很可能就是那个要去修改它的人。

这就是我倾向于编程的方式。我试图弄清楚：我到底需要计算机做什么？我尽量用最简单的方式写出能做到这一点的东西。然后，我试着把它表达为，我想说，最不冗余的形式。所以，比如我不想看到计算欧几里得距离的公式散布在我的代码各处。我想有一个类似 `compute_distance` 的函数，然后正确地使用它。我希望它能很好地被拆解成它所代表的各个片段，并且我希望这些片段能够被编译器以一种能产生极高运行效率的代码的方式，正确地重新组装起来。

这就是我平时编程时试图做的事情。对我来说，我从来没有真正理解过那种认为“基于某些原则架构良好的代码”和“运行速度快的代码”之间存在区别的心态。因为在我的经验中，通常架构良好的代码也是运行速度快的代码。是的，确实有一种情况，如果我们决定某件东西必须尽可能地接近理论上的最大性能，是的，我们会开始让那段代码变得更难阅读和修改，因为我们现在是为了这块特定的硬件或其他什么东西，对它进行了真正的过度特化。这是事实。但那种情况处于曲线的最末端，它不是常见的情况。大多数时候，假设你只是想要在大多数硬件上运行得相当不错的代码，那么简单、可读版本的代码实际上就非常快。只有当你认为你需要有 27 个工厂类、8000 个微服务以及所有这些东西在运行时，它才开始变成那种所谓的“架构良好”，但同时又难以修改、难以阅读、运行缓慢的东西，对吧？

所以我倾向于认为，在好代码中存在这样一个完美的交汇点：运行得相当不错、易于阅读、易于维护、虽然没有达到理论上的最大性能，但也足够接近了，而且通往理论最大性能的路径并没有被堵死。我们在编写它的时候留了一扇门，这样如果真的有人需要过来提升它的性能，它是具备这种条件的。

<details>
<summary>Original English</summary>

**Speaker A**: So good code to me usually means that you have written something that is as straightforward to what the machine actually needs to do to solve the problem as it can be. And also hopefully that you have, I guess I'll say, properly identified ways of breaking it into easily digestible pieces and named those pieces in ways that are easy for someone to understand, especially yourself because you are very likely to be someone who's going to have to modify it.

So that's the way I tend to code. I try to identify what do I actually need the computer to do. I try to write as simple as possible the thing that will do that. And then I try to put that in terms that are, you know, I would say least redundant. So you know, I don't want to see the equation for Euclidean distance scattered throughout my code. I want to have a function that's like compute that distance and I want to use it right. I want it to then be nicely broken into the pieces that it represents and I want those pieces to be reassemblable properly by the compiler in a way that will produce code that runs very efficiently. Right? And so that's what I'm usually trying to do when I'm trying to program.

And for me, I have never really understood the sort of mentality of there's a difference between code that is like well architected by some principles and code that runs quickly because in my experience usually the code that is architected properly is also the code that runs quickly. And yes, there is a point where if we decide that something absolutely has to get as close to theoretical maximum as it possibly can, yes, we will start to make that code harder to read and modify because we are now like really over-specializing it for this piece of hardware or whatever. That's true. But that point is like, you know, way out on the curve. It's not the common case. Most of the time, assuming you just want code that runs pretty darn well on most hardware, the simple readable version of the code is actually very fast. It's only once you think you need to have 27 factories and 8,000 microservices and all these things running that it starts to be this thing that's like good architecture, but also like hard to modify, hard to read, run slowly, right? All these things.

So I tend to think of like good code there's like this nice nexus of runs pretty darn well, easy to read, easy to maintain, isn't as close to theoretical maximum as it could be but it's close enough, and the paths towards theoretical maximum have not been foreclosed. We left the door open with the way that we wrote it so that if someone really needs to come along and boost its performance it's set up to do that. Right.

</details>

**Speaker B**: 与此相关的是，对你来说，什么是优秀的软件工程师？仅仅是能写出好代码的人，还是远远不止于此？

<details>
<summary>Original English</summary>

**Speaker B**: And related to this, what is a good software engineer to you? Is it just someone who writes good code or it goes beyond that?

</details>

**Speaker A**: 我想说，这真的在很大程度上取决于环境，因为我觉得我见过许多不同类型的优秀软件工程师。所以我更愿意把它比作，打个体育方面的比方，你可以把它想象成更像是一支棒球队：怎样才算是一个好的棒球运动员？嗯，这要看我们讨论的是投手还是指定打击手，对吧？评判标准会有相当大的差异。

所以，可能会有一些通用的标准，比如，如果一个人很好相处，并且你知道的，不总是摸鱼，能把自己的工作完成。这些显然是我们对任何软件工程师都会有的期望，也有一些普遍的性格特征可能是正面的。

但是当你谈论那些更专门针对软件工程，而不仅仅是作为一个好员工之类的事情时，我想说我见过几种不同的类型。我见过那种像“多面手”一样的人。有些人就是能够发现问题、着手去尝试修复并取得成功。即使代码库有点古怪、一团糟，他们也能非常迅速地摸清情况，发现正在发生的事情。而且他们不怕深入其中，他们的态度就像：“好吧，这里的代码库确实有点丑陋。没关系。我会打上补丁。我会做我需要做的事情把事情搞定。” 这种工程师在团队里是非常棒的。

我也见过跟这种截然相反的优秀工程师。他们的做法就像：“我接手了我们现在有的这个特定问题，八个月后，我已经把关于这个问题的每一个细节都彻底搞清楚了。” 有时甚至到了能够产生出以前从来没人知道的新算法的地步，对吧？就像那些突破性的东西。如果碰巧有这样的需求，那这也是一位非常适合留在项目中的优秀软件工程师，如果你将会……

<details>
<summary>Original English</summary>

**Speaker A**: I would say it really depends on the environment a little bit because I think I've seen a lot of different kinds of good software engineers. And so I would liken it more to a—you know, if you want a sports analogy, you'd imagine something more like a baseball team where it's like what's a good baseball player? Well, it's like are we talking about a pitcher or a designated hitter, right? And it changes quite dramatically.

So, there might be some things like, hey, if someone's pleasant to work with and, you know, doesn't goof off all the time and actually gets their work done. Those are obviously things that we would say are true of any software engineer, you know, there are some general personality traits that might be positive.

But when you're talking about things that are more specific to just software engineering and not just being a good employee or something like that, I would say I've seen a couple different kinds. I've seen people who are like the utility infielder. There are people who just like they can identify and go and try to fix a problem and succeed. Even if the codebase is kind of wacky and out there, they're good at getting the lay of the land very quickly of identifying something that's going on. And they're not afraid to go in and like, "Okay, this is kind of this code base is kind of ugly here. It's okay. I'm going to patch around. I'm going to do what I need to do and get things done." That's a great engineer to have around.

I've also seen great engineers who are the exact opposite of that. They are just like, "I take this one particular problem that we have and eight months later, I have ground out every last thing there is to know about this." And sometimes to the point of like producing new algorithms that no one's even known before, right? That are like these, you know, breakthrough things, right? And that's a great software engineer to have on a project if you happen, if you're going to be...

</details>

<!-- chunk 13/16 -->

### 什么是优秀的软件工程师

**Speaker A**: ……拥有那种特质。因此，我见过很多不同的、我认为是优秀软件工程师的人，他们并不都是同一种类型的，对吧？所以，我认为如果你从这样的角度来问这个问题会比较重要：比如，“嘿，你需要组建一个团队去构建这个项目，那什么才是优秀的软件工程师呢？”我会说，在这种情况下，你能给出的最好的建议就是：考虑角色。想想在这里会需要什么样的角色，不要总想着“优秀的软件工程师”，而是要想着“在这个角色上表现优秀”，对吧？谁能成为一个优秀的投手？谁能成为一个优秀的一垒手？谁能成为一个优秀的外野手？谁能成为擅长这个、那个或其它事情的优秀人才？或者是优秀的跑垒指导员，不管是啥，对吧？对我来说，如果你要组建一个团队，这才是你需要去拼凑的东西。

<details>
<summary>Original English</summary>

**Speaker A**: ...having that kind of thing. And so I've seen a lot of different people that I would consider great software engineers and they aren't all the same person, right? So I think that it's kind of important if you're asking it from the standpoint of like, hey, you need to put together a team to go build this project. What's a great software engineer? I would say the best advice you could give someone in that position is think about the roles. Think about what kinds [snorts] of roles there are going to be here and don't think great software engineer. Think great that role, right? Who is going to be a great pitcher? Who's going to be a great first baseman? Who's going to be a great outfielder? Who's going to be a great this that the other thing? Great third base coach, whatever it is, right? And that's what you're trying to put together if you're trying to build a team to me.

</details>

**Speaker B**: 是的，所以它并不是一刀切的。但我还是想稍微逼问一下：对于成为一名优秀的软件工程师，你认为哪些特质是不可妥协的底线？你知道，我们讨论过很多相关的事情，你经常反复提到的一个主题就是不断深入，去理解下一层、再下一层，比如，如果你在做 Web 开发，你要理解 React；一旦你理解了 React，就要去理解 DOM 里发生了什么；一直深挖到底层的汇编；到了那一步，再去理解 CPU 是如何进行运算和分支预测的，等等。对我来说，这是一种受好奇心驱动去钻研更深层工艺的技能，不管你怎么称呼它，而且我们有很多不同的方式可以做到这点。但顺着这个思路，你认为无论我们谈论的是哪种角色，只要你回想一下与你合作过的不同类型的角色，你是否看到他们都在某方面有这种共通点？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, like it's just not one size fits-all. But I I still want to push you a little bit like what are things that are you think are non-negotiable for someone to be a great software engineer? I you know we we talked about the things that we talked about which is a recurring theme with you is just going deeper and deeper and understanding the next and next layer you know like understand if if you're doing web development understand react once you understand react understand what's going on in the DOM go all the way to assembly once you've done there understand how the CPU is doing operations and branch predictions and some of those things like to me that's a skill of like curiosity driving deeper crafts whatever you call you know, there are different ways we could do it. But along these lines, what are those traits that you think no matter, you know, what kind of role we're talking about, but if you think back of of some of the different types of roles that you work with, like do you see some overlap that that they all had something?

</details>

**Speaker A**: 我想说，这相当不寻常，我的意思是，如果一个人不知道怎么读汇编代码之类的，我很难将其视为一名优秀的软件工程师。这确实是实话。可能是因为，对事物运作方式抱有好奇心，并在一定程度上知道底层发生了什么，这可能是优秀软件工程师非常普遍的一个共性。但我想强调一点：他们运用这些知识的程度可能会有很大差异。对其中一些人来说，这可能是他们赖以生存的本钱，他们整天都在做这些。而对另一些人来说，仅仅是因为他们了解计算机是如何工作的，从而不会做出那些后来会反咬我们一口的愚蠢的架构决策，对吧？这很好，但实际上他们在那个底层的层面上并没有做那么多事情，或者说很少在那个层面上进行思考。他们只是觉得，“是啊，我知道我们得推进一下，好吧，这些东西必须批处理（in batch），因为我就知道机器只能这么处理它。所以，你知道，我会确保我把代码写成那样，或者诸如此类的。”是的，所以确实有一点这种因素。

我可能会说的另一件事，大概就是：对他们自己没有实际验证过的事情，不要教条主义。这可能是非常关键的一点。我发现有很多所谓的“公认的编程智慧”纯粹是胡说八道。很显然从来没有人去测试过它，如果他们测试了，就会发现那根本没有实际依据。这不一定意味着它是错的，只是你找不到实际的有形方式去证明它。有时候，你甚至可以证明这种“公认的智慧”在实际中确实存在具体的缺点，对吧？因此，要让它成为“公认的智慧”，你至少应该能够证明它有具体的好处，但很多时候根本做不到。所以我认为，真正专注于实践中行之有效的方法的人，具备着一个巨大的优势，你可以把这个原则应用到任何地方、任何事情上，对吧？而不是仅仅说，“哦，最近的流行趋势是我们什么都用类（classes）、虚函数和层级结构来写，或者别的什么。”这就好比，你到底有没有确认过那会减少代码量，或者那代码实际上是否更可维护（mermaid，注：此处原转录音近错词，实为 maintainable）？比如，我们有没有做过任何测试，来搞清楚这到底是帮了我们还是害了我们？很多时候答案是否定的，或者就算做了，也做得极其敷衍，你根本无法将那些结果视为任何形式的定论。所以，对编程实践保持更多的怀疑态度，真正去关注实践中有效的东西，关注我们可以用某种可重复的方式去证明和衡量的事情，我认为这对于一名软件工程师来说也是一个非常棒的品质。所以，那些不容易盲从的人——比如，我看了一些演讲，然后某个在 Google 的人说“永远调用 `memset`”或者“永远不要使用 `if` 语句”之类的，如果你是在这个层面上思考，那我可能就不会把你归类为真正优秀的软件工程师了，因为事情不是这么运作的。

<details>
<summary>Original English</summary>

**Speaker A**: I would say that it's pretty unusual, I guess, that I can't think of someone I would think of as a great software engineer who like didn't know how to like read assembly or something. That is true. It might be that having that curiosity about how things work and and knowing at some level what's going on is kind of maybe something that's going to be very common to a great software engineer. But I would just underscore the point. The degree to which they are employing that knowledge may vary quite a bit. For some of them that may be their bread and butter and they're doing that all day. For others it's just really a thing where because they know how a computer works, they're not making those stupid architectural decisions that come back to bite us later. Right? And that's great, but they may not really be doing all that much actually at that kind of level or or thinking about at that level. They're just going like, "Yeah, I know we got to kind of push, okay, this stuff's going to have to be done in batch because I just kind of know that that's, you know, how the machine's going to have to handle it. So, we'll, you know, I'll make sure I I write the code that way or whatever." Yes. But, so there's a little bit of that. The other thing that I would uh say maybe is actually like not being dogmatic about things that they haven't actually themselves proved out is probably a huge one. I find there's a lot of like received programming wisdom that's just nonsense. Like clearly no one's ever tested it and if they did they would have found out that it's that there's no actual basis for it. Doesn't necessarily mean it's false. It's just there's no like there's no actual tangible way you can demonstrate. And sometimes it is like you could demonstrate that there are actual concrete downsides to this received wisdom, right? And so in order for it to be received wisdom, you should have to be able to at least demonstrate concrete upsides, which often times cannot be done. So I would say people who actually focus on what works in practice is a huge plus and you could apply that anywhere into anything, right? Not just saying, "Oh, the flavor of the month is that we're writing everything with classes and virtual functions and hierarchies or whatever." It's like, did you actually determine that that results in less code or that the code actually is mermaid? Like, did we do any testing to figure out if this is helping us rather than hurting us? And the answer oftentimes is no or if if it was at all. It was extremely shoddily done and you would not take those uh results as conclusive in any way. And so it's like being more skeptical about coding practices and actually trying to focus on what is working in practice and what we can demonstrate and measure in some kind of a uh repeatable way is I think a really great thing for a software engineer to have as well. So people who don't tend to fall prey to that just like I watch some presentation and someone at Google says always call me MEMS set or never use if statements or whatever it is like if that's the level that you're thinking at then I probably am not going to put you in that category of of really good software engineer because that's not how it works.

</details>

### 人工智能与编程的初衷

**Speaker B**: 另外，自己去尝试这些事情，或者在内部建立环境运行一下实验，也并不是那么难。那么，我想谈的最后一个话题（我故意把它留到了现在），是 AI 以及它正在如何改变你的工作。我想先从这点开始问：在你们 Molly Rocket 做的这个尚未发布的新项目中，你们是如何使用 AI 工具的？或者说，你们究竟有没有在使用它？

<details>
<summary>Original English</summary>

**Speaker B**: Plus it's not that hard to try these things out or in or set up or or do run an experiment. Now, the the final topic I wanted to touch on, which I deliberately didn't get into until now, is AI and how it's changing your work. And I'd like to start with that, like in in the work that you're doing at Molly Rocket with this this project that is un yet unreleased, how are you using AI tools, if you're using them at all?

</details>

**Speaker A**: 我们完全没有使用它们。

<details>
<summary>Original English</summary>

**Speaker A**: We are not using them at all.

</details>

**Speaker B**: 所以，你们就像以前一样？纯手写代码。是什么让你决定走这条路的？

<details>
<summary>Original English</summary>

**Speaker B**: So, you're you're you're doing it just like before. You're writing your your code. What made you decide to to take this path?

</details>

**Speaker A**: 嗯，很明显我们有点不太一样，原因有两个。其一，就像我说的，我们在这里算是有两个项目并行，Substack 是我们的主要关注点，而另一个项目是我们因为“想做”所以才做的。当你从这个视角来思考时，就会问：“好吧，你为什么要去做它？”嗯，我想亲自去给游戏里写东西的原因就在于，我本身就想去编程。

如果我只是想让 AI 来编代码，那我可能……你知道，首先，我们大概会直接去使用一个商业授权的引擎，对吧？我甚至都不会费神去叫 AI 做，我直接拿个虚幻引擎（Unreal Engine）就好了，[笑声] 对吧？或者诸如此类的工具。

所以，我认为这个决定的那部分因素，对你的听众来说可能没那么有参考价值，因为这更多是关于“你想做什么？”的问题。比如，你为什么要花这些时间？对吧？这是一个哲学问题，而不是一个生产力问题。因此，我并不是对 AI 进行了评估然后说：“我不觉得这能给我们省时间”，或者“我对它的版权问题或者伦理道德有疑问”，或者是那些你本来可以正当去评估 AI 的所有维度。不一定是因为这些。更主要的原因在于，使用它并不能推进这个项目的真正目标。所以，在那一点上这就完全是个伪命题了。对。

再往外跳出一点，把关于 AI 的讨论放到一个更广阔的哲学框架里。我想补充说的是，不管你认为 AI 未来会发展成什么样（因为显然我们都没法真正预测它 10 年后会是什么样子，这真的全靠猜），我认为在未来的某个时间点，很可能也会出现一种对“传统手工制作”的推崇。因为我们在实现其他自动化的时候大多也看到了这种现象。比如，如果你实现了家具制造的自动化，于是有了宜家之类的品牌，但这并不意味着在你所在城市的工业区里，就没有某个奇怪的家伙，还在用铁和焊接之类的材料在那儿疯狂地手工打造木桌。这仍然是人们在做的一件事情，而有些人就是想要那张桌子。我未必能给出一个解释，我也不打算去争论它是否有更多或更少的价值，但它就是会发生的一件事，对吧？所以如果我想象我想要什么，我喜欢计算机的什么，以及我想用计算机做什么……

<details>
<summary>Original English</summary>

**Speaker A**: Well, we're a little bit different obviously uh in the sense for two reasons. One um is that we you like I said we are kind of we have like sort of two projects here and the substack is our primary focus and this other one is a thing that we're doing because we want to do it. And when you think about that perspective it's like well why did you want to do it? Well, the reason that I want to program like things in a game is because I want to program them.

If I just wanted an AI to program them, I probably, you know, first of all, we'd probably just go use a licensed engine, right? Like I wouldn't I wouldn't even bother asking AI to do it. I'd just go get the Unreal [laughter] Engine, right? Or something like that and so on.

So, uh I think a little bit of that decision is probably not that relevant to your audience because it's more about what do you want to do? Like what why are you spending this time, right? It's a philosophical question, not a productivity question. So, it's not like I evaluated it and said, I don't think this will save us time or I or you know, or I have questions about the copyrightability of it or the ethics of it or all the sorts of things that you could rightfully evaluate AI on. It wasn't necessarily that. It's more just like this does not further the goals of the project to use it. So, it kind of was a non-issue at that point. Right.

stepping out a little bit more uh to a broader philosophical framework about AI. I guess what I would also say is I think that if you regardless of what you think will happen with AI in the future because obviously we don't really have any way to predict what it will look like 10 years from now. It's anyone's guess really. I think there will probably also be at some point point a notion of like traditional handcrafting that will come into play because we've seen this in most other times when you automate something. So, if you automate making furniture and you have like IKEA or whatever, that doesn't mean that there isn't some weird guy down in the industrial district of your city making crazy wood tables with iron and welding and something. And that that's just a thing that people are still doing and some people want that table. I don't necessarily have an explanation for it and I'm not trying to argue that it has more or less value, but it's just something that happens, right? And so if I imagine what I want, what I love about computers and what I want to do with computers,

</details>

<!-- chunk 14/16 -->

### AI 与手工编程的意义

**Speaker A**：如果你问我，把它放到其他背景下看，我会是哪种人？我的答案始终是，我会是那个搞有机农业的人。我会是那个在工业区里亲手制作奇特桌子的人。我对在宜家管理一个部门毫无兴趣。我真的一点都不在乎那个，对吧？所以，我认为我不太有兴趣追求 AI 的另一个原因在于，我希望成为那些让这种传统手艺继续存活下去的一份子，仅仅因为这是人类会做的事情。而不是说我们要证明这是正确的商业模式，对吧？不知道这是否说得通。

<details>
<summary>Original English</summary>

**Speaker A**: and you asked me, move that into some other context, which of these people would you be? My answer is always, I'd be the organic farming guy. I'd be the guy who's making the weird table in the industrial district. I have no interest in managing a division at IKEA. I literally couldn't care less about that, right? And so I think for me another reason why I'm not that interested in pursuing AI is because I would like to be part of whatever the set of people are who are going to keep this traditional craft alive just cuz that's something humans do. Not because we're trying to say that that's the right business case, right? If that makes sense.

</details>

**Speaker B**：是的。而且从某种程度上说，这已经形成了一种传统，即便我们假设这些机器能做得和人类一样好甚至更好，但毕竟在过去 60 多年的时间里，我们都完全只靠手工编写软件，因为事情本来就是这样完成的，对吧？比如我们当中的很多人，任何在 2023 年、或者 2022 年底，说实话可能是 2024 年这些工具变得相当不错之前开始编程的人，很多代码就是手工敲出来的，或者按 Tab 键自动补全也算在内。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And and at this point there's a bit of a tradition if you will even if we assume that these machines will do as good or better than cumizit for like what 60 plus years we've we've only exclusively handwritten software because that's how it got done right like a a lot of us anyone who started coding before 2023 or the end of 2022 or probably honestly 2024 when these things have gotten like decently good you just wrote it by hand a lot of it or tap complete still counts.

</details>

**Speaker A**：是啊。我想说的是，同样地，这只是……你知道，问题在于为什么要那么做，对吧？就像我不知道为什么人类要那样做，人类这样做是因为这就是人类会做的事，对吧？人类有时就是喜欢亲力亲为。你知道，人们可以买一顶帽子，他们可以轻而易举地买一顶羊毛帽子，或者随便买个什么。然后现在可能就有某个人正在那里自己织帽子，对吧？这只是人类会做的事情。他们有时就是喜欢手工制作东西，而且手工的程度各不相同。你知道，有些人只是买来羊毛或者买现成的纱线。有些人会自己养羊然后剪羊毛，对吧？你可以无限地追溯下去。你可以找到那种全程包揽的人，对吧？甚至比我从事那个行业所能达到的程度还要深。所以，你知道，你可以想象现在有人在自己制造硬件，对吧？呃，我是不会这么做的。所以这差不多就是我的看法。嗯，所以关于 AI 编程或者你想用它做什么，我可能是最不适合问的人了。我真的没有任何有价值的意见可以补充。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I and and I guess I would say like again it's just you know why why do that right is the question it's like I don't know why humans do that humans do that because it's something humans do right humans like to do things themselves sometimes you know people can buy a hat they can buy a a wool hat trivially or they can buy a whatever and then someone's out there knitting a hat right now that's just it's just something humans do they like to make things by hand sometimes and at varying levels of handmadeness You know, there's some people just buy the the wool or whatever or buy the pre-made yard. Some people raise the the sheep or whatever and shear it, right? Like you can go arbitrarily far down. You could find somebody who's going all the way, right? Even further than probably I would ever go if I was in that thing. So, you know, you could imagine someone making their own hardware these days, right? Uh I'm not doing that. And so that's kind of my my take on it. Um, so I'm kind of the last one to ask about, you know, AI coding or what you might want to do with it. I I really have no nothing of value to add.

</details>

### AI 编程对行业的影响评估

**Speaker B**：是的。但我还是想通过游戏行业的视角来问问你，我们之前也提到过游戏引擎的出现，现在更多的人可以制作游戏了。虽然不是每个人，但门槛确实降低了很多。你观察到的大多数人（除了那些因为热爱而坚持手工写代码的人之外）使用这些 AI 编程代理，无外乎两个原因。要么是因为这么做很合理，他们意识到现在这东西生成的代码和他们写的一样好了，在今年 1 月份出现了一个转折点，我自己也确实经历了那个转折点；要么是因为公司的硬性要求，比如“你们必须使用这些工具”，最终他们也就顺从了，不管是不是自愿的。但既然有这么多人让 AI 替他们写代码，他们虽然在写提示词，但实质上代码是 AI 写的。从你的角度来看，你观察到这产生了什么影响？可能是在质量、工艺上，或者单纯在产出、速度等方面。你都看到了什么？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. But I am interested in asking you through the lens of the games industry and and we touched on on games engines arriving and and now so many more people can make games. Not everyone, but it's it's a lot easier to enter. What are you observing in terms of most people outside of who are still handcrafting code because they want to are are using these AI coding agents for for two reasons. Either it's either it's it just makes sense and they realize well this thing can now generate code as good as I did which was a turning point in January. I I I had that turning point actually myself or some are actually just pushed with corporate mandates of like you need to use these tools and and eventually they kind of get on board whether willingly or or unwillingly. But so many folks are are having AI write the code for them. They're, you know, they're prompting it, but they're doing it. What do you observe of the effect having, you know, from your vantage point? May that be on on quality, craftsmanship, on just output, speed, etc. What are you seeing?

</details>

**Speaker A**：老实说，我认为现在评估还为时过早。因为正如你所指出的，显然有一些人——我们可能会贬义地称之为“AI 托儿”——这两年左右一直在说它生成的代码和人类一样好，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: I think it's a little too early to assess to be honest because kind of as you pointed out obviously there's been people who maybe uh you know we might derogatorily call AI shills who have been saying that it was producing as good a code as humans for you know two years now or something like that right

</details>

**Speaker B**：但在现实中，那些我更信任其观点的人，没有一个认为它真的那么可用，直到最近才大有改观。

<details>
<summary>Original English</summary>

**Speaker B**: but in reality the people who opinion I would trust more none of them thought it was really all that usable until more much more recently Right.

</details>

**Speaker A**：所以，实际上我们并没有——他们并没有太多的时间去真正搞清楚该如何使用这个东西，或者去确定他们能在多大程度上使用它，以及它最擅长什么，怎样的工作流程能让它产生最好的结果。目前看来，我觉得可能至少还需要给它六个月甚至一年的时间，让每个人都能摸索出使用这东西的最佳方式。我知道游戏行业里有无数的人都在使用它。所以我知道他们确实在用它做各种各样的事情。无论他们现在做的这些事情，是否是他们最终认为最好的方式——你知道，可能他们现在做的这些事情以后看来会有点傻，比如“你不应该那样用它，你应该用它做这件别的事，那样效率会高得多”之类的。所以我感觉现在评估可能为时过早。我们还没有看到任何真正明显的变化，比如那种“哇，你知道吗，《堡垒之夜》现在每周发布一次而且完全没有 Bug”。在输出方面并没有发生什么特别有趣的事情，但这又回到了一个问题，这才过去了多久，大概 5 个月左右吧。所以，要看出它实际上是如何被整合到一个可靠的流程中去，现在真的真的还太早了。

<details>
<summary>Original English</summary>

**Speaker A**: And so we really haven't they haven't had very many months to actually be figuring out how to use this thing or to determine to what extent they can use it and how what it's best at, what the workflow looks like that makes it produce the best results. It seems like at the moment I would say probably need to give it at least another six months if not another year or something to let everyone kind of shake out like what what are actually the best ways to use this thing. I know tons of people in the game industry are using it. So I know that they are um doing various things with it. Whether those things are the same sorts of things they will eventually think are the are the way they like you know like the the things that they're doing right now may be like oh that was kind of dumb like you shouldn't have used it that way you should do this other thing with it and it's way more productive or something. So I feel like it's probably too early to assess. Uh we haven't seen any real like obvious like oh wow like you know the the you know Fortnite ships once a week now and it's bug free like nothing particularly interesting has happened in terms of output there but again it's been what like 5 months or something. So it's just it's way it's way too too early to see how it actually gets integrated into a reliable process. Right.

</details>

**Speaker B**：是的。而且我知道有一些公司现在正在安排代理去修复 Bug，但这也仅仅是几个月前的事。目前被广泛使用的、几乎 100% 由代理编写的软件，最老的一批也就来自实验室，比如 OpenAI 的 Codex 和 Anthropic 的 Claude 代码，但即便如此，那也是从 11 月或者部分从 12 月才开始的，大概也就六个月的时间。而且这也不一样，对吧，那是他们在销售的产品，所以其中是否存在营销的成分……或者确实存在自我偏见。所以我会先把这些放在一边不谈它们的可靠性。你说得对，至于其余的，我们确实真的没有足够的信息。我相信肯定有很多实验正在进行，但正如你所说，它需要时间来酝酿，才能看到影响。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. and and there I I know there are some companies who are now tying up let's say agents fixing bugs but that's only a few months old the oldest software that's widespread that is written close to 100% by agents is from the labs open AI's codeex and entropics cloth code but even there it's been since November or or some parts of it December so like maybe six months and it's a it's different right that is a product they're selling so there's uh I'm not sure we'll we'll we'll know for sure like is it truly 100% how much you know there there's a marketing angle or not but there's a there's a self bias there so like I would put those aside in terms of trustworthiness and you're right that the rest we just we just don't really have the information it'll be I'm sure there's so much experimentation so but to to your point it takes time to bake right to see the the impact

</details>

**Speaker A**：目前这些东西大部分还是作为工具呈现的，也就是说至少在某种程度上必须有人类来操作它们，比如至少得设置好让它去做什么。因此，你必须给它一些时间。你知道，目前还没有人销售这样一种产品，就是“只要打开这个东西，它就会自动一直开发发布《堡垒之夜》，你可以把所有的工程师都解雇了”。还没有人真正在卖那样的产品，对吧。如果真有，我们就可以去评估那个产品，因为我们会问：“有人这么做了吗？它开始自动开发发布《堡垒之夜》了吗？”对吧。所以，如果它仍然是一个需要人类去弄清楚如何将它融入现有工作的东西，那么外部观察者没有看到生产力出现明显大幅提升的原因，完全可能是人们需要花一段时间来摸索和适应，或者也许 AI 还需要变得更好一点。也许我们还要经历一些更新阶段，或者别的什么。我不确定。这些都是可能的。然后还有另一种可能性，那就是它实际上已经起作用了，只是生产力的提升幅度并没有那么明显。如果人们的生产力提高了 10%，那依然是非常令人印象深刻的，因为想要实现全面 10% 的提升是很难的。我以前在播客里也说过。我说如果你有一个工具能让每个人的工作效率提高 10%，那很棒。但这几乎不会有人察觉，对吧？如果这就是你所获得的，它在外部其实并不那么容易被观察到，但它可能已经发生了，对吧？所以，由于这些种种原因，真的很难判断。在未来的某个时刻，如果 AI 真的非常出色，而且人们也弄清楚了如何非常好地使用它们，那应该会变得很明显。比如应该是 5 个人现在就能开发并发布《堡垒之夜》，而不是 5000 个人，诸如此类，对吧？但是，在那一刻到来之前，真的很难知道，因为特别是如果提升幅度很小，我们是很难看出来的。

<details>
<summary>Original English</summary>

**Speaker A**: most of these things are currently presented as tools meaning a human has to operate them at least in some way like at least setting it up to do what it's going to do and therefore uh you have to give it some time you know you know nobody currently is selling a product where it's just like oh just turn this thing on and it will just ship Fortnite by itself forever and you can just get rid of all your engineers like no one's actually selling that product yet right we could evaluate that product because we'd be like did anyone do it did it start shipping Fortnite on its own right so if it's still something where humans have to kind of figure out how they want to like slotted into what they're doing, then it's entirely possible that the reason that we haven't seen some big uptick in productivity uh that would be obvious to an external observer is because it's going to take a while for people to like shake that out or maybe the AIs need to get a little bit better. Maybe like we've got to go through some more update steps or you know whatever. I'm not sure. So there's all that's on the table. Then there's another possibility which is that it actually already has worked but just the productivity boost isn't as big as would be obvious if people got 10% more productive. That would still be pretty impressive because it's hard to get a 10% across the board uplift. I've said this before on podcasts. I'm like if you have a tool that can give everyone 10% off of that's great. Almost no one would know, right? It's like you can't it's not really externally observable that clearly if that's what you got, but it may have happened, right? So, it's really hard for all of those reasons. At some point, if the AIS are really fantastic and people figure out how to use them really well, it should be obvious. It should be like five people are now shipping Fortnite instead of 5,000 or whatever, right? But, but until that point, it's really hard to know because it's just like especially if it was small, it'd be hard for us to see.

</details>

**Speaker B**：好吧，这可能只是轶事，但我正在从软件工程师和经理那里收到大量的数据和信息。它产生的一个影响是，有这样一种 AI……

<details>
<summary>Original English</summary>

**Speaker B**: Well, this is anecdotal, but I'm getting a lot of data points and messages from software engineers and managers. One impact it's having is there's this kind of like AI

</details>

<!-- chunk 15/16 -->

### AI 带来的职业倦怠与自主性缺失

**Host**: 软件开发人员中出现了一种疲劳或职业倦怠感，他们会觉得：“听着，我很擅长写代码。我一直都很擅长这个。在不同程度上，我以前很享受这份工作。但是自从年底或今年年初 AI 这股浪潮兴起以来，情况变了。现在我实际上是在写提示词（prompting），我所有的代码都是生成的，不管是因为公司的强制要求还是仅仅因为这样做的确更快。我开始失去动力了，感觉就像是‘我在这里的意义是什么？’好像任何人都能做这些事，而且我觉得自己大材小用，发挥出的能力远不如从前。” 现在上面施加了各种压力，要求你用 AI 变得更高效。而且我觉得，我们应该……我看到了越来越多这样的迹象，我们可以称之为职业倦怠、AI 疲劳等等，也就是动力的丧失。我还没见过哪种技术，或者说我不记得有哪种技术能产生如此广泛的影响，几乎无处不在。我从一些领先公司的同行那里听到了这种声音，他们可能本身不算是纯粹的 AI 公司，但是足够庞大，比如那些现在大规模涉足 AI 领域的数据库提供商，他们正在为各行各业不管是传统企业还是现代企业赋能。你有没有观察到这些现象？对于现在有这种感觉的人，你有什么建议或指导吗？

<details>
<summary>Original English</summary>

**Host**: fatigue/burnout for from software developers who are like look I am good at coding. I've always been good at it. I I enjoyed the the work to various extents. But since this AI thing happened since the end of the year, beginning of the year since it's actually I'm now prompting and now all my code is generated whether that's corporate mandates or it's just faster. I'm starting to lose my drive like why am I here? like anyone could do this and I think there's a sense of like I'm using a lot less of what I'm capable of. There's all this pressure from above to be more productive with it and it's I think we should like I I'm seeing more and more signs that it's it's what do we call it burnout, AI fatigue, etc. loss of motivation. I haven't seen a technology or I don't remember technology having this widespread impact like everywhere. I'm hearing from folks at some of the leading like kind of not AI companies per se but like you know big enough like database providers who are now hugely into AI and they're powering a lot of the things traditional companies modern everywhere. Have you observed some of this thing and would you have any any advice or any uh pointers to folks who are feeling like this right now?

</details>

**Guest**: 我觉得我只能说，我并没有亲眼“观察”到。但是否“听说”过呢？是的。我想我大概会这么说。比如，我和一些人聊过，他们会说某某人在这方面遇到了很大的困难，或者某某人情况如何，我确实听到过这些。但我有没有直接和经历过这些的人交流过呢？目前还没有，没有。而且，这其中很大一部分原因可能在于，和我交流的大多数人在工作内容和工作方式上都有相当大的自由度。我每天交谈的很多人都能自己决定他们想怎么使用 AI 等等。因此，我不太会从那些被经理直接命令“你必须这么做”的人那里听到太多抱怨。

<details>
<summary>Original English</summary>

**Guest**: I guess I would say observed. No. Uh heard about. Yes. Uh I guess is what I would say. Like I have talked to people who have been like such and such has been having a really hard time with this or such and such has been having like there's there I've definitely heard that interacted directly with someone. Not currently. No. Uh, and part of that is is probably largely because most of the people I talk to have a fair amount of latitude with what they do and how they do it. A lot of the people that I talk to on a daily basis are able to make their own decisions about what they want to do with AI and so on. And so I don't necessarily hear from as many people who are going to be in a position where some manager told them this is just what you have to do.

</details>

**Host**: 这非常有趣，因为有一件事被反复提及，Armen Ronacher 在播客上跟我说的也是同样的事情，他观察到工作中的自主性——你在工作中有多大的自主权，比如在你要做什么工作、怎么做这些工作上你能做多少决定——那些拥有很高自主权的人通常会觉得：“哦，太棒了，我可以用它来做这个，我可以使用这个工具。” 但是那些被硬性告知怎么做的人，你知道的，比如你事先被分配了一个工单（ticket），或者产品经理（PM）直接给你下达指令，他们没有太多回旋余地。现在，这些人更多地将其视为一种威胁，因为不管是在潜意识里还是意识里，他们肯定在想：“这东西可能会让我的工作自动化。就是现在了，”或者是“它甚至把原本需要我付出的那一点点努力也剥夺了。”所以我在想这中间是不是有什么联系。

<details>
<summary>Original English</summary>

**Host**: This is very interesting because one thing that keeps coming back and Armen Ronacher was telling me the same thing on the podcast is he's he's observed that autonomy like at your work how how autonomous you are at your work like how many decisions you can make on how what you work on how you do your work the people who have a lot of that are typically like oh great I can use this for this like I can use this tool but the people who are told you know like in beforehand you're given a ticket or the PM tells you this they don't have much wiggle room and Now those folks are seeing it way more as a threat because of course subconsciously or consciously they're thinking well this thing could automate my my job. It's now or or it made it made from that little effort I had to do that it took it away as well. So I wonder if there's a connection here.

</details>

**Guest**: 我的意思是，这听起来完全合乎逻辑，对吧？如果你是一个拥有高度自主权的人，那你什么时候会去求助于 AI 呢？显然是当你遇到自己不想做的事情的时候，对吧？所以从某种定义上来说，我觉得在那种情况下你对它会有非常积极的体验，因为最坏的情况也就是它不起作用。那样的话，我猜感觉是不太好。你可能会想：“啊，这玩意有点糟糕。” 但是，假设它确实能加快这部分工作的进度，那就太棒了。这就好像在说：“嘿，我本来就不想做这件事。我让 AI 帮我做了，现在我拿到了想要的结果。” 这对他们来说绝对是一种积极的体验，对吧？然而，没错，如果你只是被告知，你有一件自己想做的事情，但上面告诉你不能自己做。你必须用 AI 来做。并且你懂的，顺便提一句，我们公司刚刚还裁员了，或者发生了其他什么事情。你知道，很多这些因素显然会彻底改变你的心理反应，因为现在不是你因为不想做某件事而决定让 AI 替你做。现在是你被直接要求必须使用这个 AI 来自动化你以前的工作。你可以很明显地看出，为什么这会对人们产生完全不同的心理影响，对吧？

<details>
<summary>Original English</summary>

**Guest**: I mean that sounds totally logical, right? Uh if you're somebody with a high degree of autonomy then when are you going to reach for an AI? Well, whenever there's something that you didn't want to do, right? So kind of by definition, I think at that point you're going to have a much more positive experience with it because worst case just doesn't work. In which case, I guess that's not great. You're going to be like, "Ah, this thing was kind of crappy." But assuming that it's able to accelerate some part of that, that was great. It's like, "Hey, I didn't want to do this thing already. I had this AI do it for me and now I have the thing." That's just a positive experience for them, right? Whereas, yeah, if you're just told like you had this thing that you wanted to do, and you were told you can't just do it yourself. You have to do it with the AI. Uh, you know, and by the way, we just had layoffs or whatever. You know, a lot of that stuff obviously could totally change your mental reaction thing because now it's not you deciding to use an AI because there's something you didn't want to do that you thought the AI could do for you. Now it's you just being told that you're supposed to be using this AI to automate whatever your job used to be. You can see pretty obviously why that would have different psychological effects on people, right?

</details>

**Host**: 所以，我想这对于处于这种情况的人来说可能只是一个建议：现在你可能需要评估一下你目前的职位，或者如果你在面试下一个职位，你可以基于你将拥有多少自主权来评估。因为你的自主权越高，你就越有可能控制自己如何使用这些技术，你能做多少实验；而不是被下达一道命令，比如“我不管，我们期望你的产出能增加或者发生改变”，不管是怎样。我很好奇这是否会重新评估一些……你知道，比如什么才算是一个有吸引力的职位？因为举个例子，以前大型科技公司被认为是绝佳的工作场所，因为薪酬高、期望明确，职业晋升路径也很清晰易懂；但现在正是他们在开始衡量你的 AI 使用情况，这就像是给他们对你的期望戴上了一种手铐，或者在那儿你可能会面临大规模裁员，这又是你完全无法控制的，对吧？就像又一次……或者是用比喻来说的内部岗位重新分配，比如“你接下来的几个月去打数据标签吧。”

<details>
<summary>Original English</summary>

**Host**: So, so I guess it it might be just an idea for folks in this situation that now it you might want to evaluate your current position or if you're interviewing your next position based on how much autonomy will you have because the more autonomy you'll have, the more likely you're going to have control over how you're using this stuff, how much you can experiment versus being given a mandate that I don't know, we're expecting you to have this output increase or output change, whatever that is. I I I wonder if this will re-evaluate some of you know like what is considered an attractive position because like for example big tech was considered a great place to work because high compensation pretty clear expectations like easy to understand career advancement but now they're the ones who are starting to measure uh your AI usage which is going to like giving a kind of a bit of a handcuff of what we're expecting you to do or there's where you might have there might be mass layoffs which again you have no control over right like again one more or or inside of metaphors reassignments of like you will now do labeling for x months.

</details>

**Guest**: 我的意思是，你甚至可以这样想，你知道的，我们能不能创造个短语——“是你正在使用 AI 来做你的工作，还是 AI 正在利用你来做工作？” 对吧？因为在某个时刻，这种感觉非常明显。以 Meta 为例，从你对这件事的报道来看，而且我也看到其他人说过同样的话，所以这听起来不像是单一消息来源的说法。听起来这似乎已经成为一种公认的事实：他们只是在利用你进行 AI 训练，对吧？就像你在那里的意义就是，你知道，你只是在那里训练这个 AI 去做这件事，这样我们以后就不需要你了，对吧？因此，从选择工作的角度来思考这个问题，如果你真的有任何选择余地，这确实是说得通的，对吧？不过，是的，

<details>
<summary>Original English</summary>

**Guest**: I mean you could sort of think of you know could we coin the phrase are you using an AI to do your job or is an AI using you to do to do your job right like because at some point it definitely it definitely felt like meta for example uh from from your reports on it and I have seen the same thing said by other people so it does not sound like a a one source kind of a thing. It sounds like this was kind of just accepted as fact that they kind of just were using you as AI training, right? Like that's what you were kind of, you know, you're just there to train the eye to do it so that we don't need you anymore, right? And so thinking about that from a from a perspective of choosing your job. Uh it does make some sense if you do if you have any latitude, right? Uh but yeah,

</details>

### 推荐资源：比起读书，更推荐读论文

**Host**: 作为结束，有哪些对你产生过影响的书籍，你能推荐一两本吗？

<details>
<summary>Original English</summary>

**Host**: as closing, what are one or two books that you would recommend that had an impact on you?

</details>

**Guest**: 如果可以的话，我想在这里发表一个比较有争议的观点（hot take），因为这算是我最近一直试图推动的事情。我认为人们不一定非要听我推荐书。我想推荐大家去读论文（paper）。我正在努力让更多的人去阅读学术论文，因为我意识到我自己就读了大量的论文。我经常阅读关于我感兴趣事物的论文。比如，如果我要去一个我以前从未涉足的领域进行编程，我就会阅读大量的论文。我会去顺藤摸瓜查找论文中的参考文献。我会阅读一篇综述，然后收集所有相关的参考文献，去阅读这些参考文献，再接着往回追溯。我发现我通过这种方式学到了非常多东西。我觉得很多程序员根本就不这么做。所以我的建议是，你不需要去读某一篇特定的论文。我不会给你指定说“去读这一篇”。你只需要想想你正在编程的那个领域。在谷歌学术（Google Scholar）上搜索一下你感兴趣的那个领域的某个部分。试着读一篇论文，顺着它的参考文献继续读，看看你有什么想法。我认为这是一件很棒的事情。我不仅从这种学习过程中获得了巨大的乐趣，而且还获取了更多关于我正在做的事情的知识。几乎每次我这么做，哪怕只是为了多了解一点事物是如何被发现的历史记录，但在很多时候，就像是我学到了我以前根本不知道的全新技术。因为外面的知识实在太多了，任何一个人都不可能完全掌握。而且我也不知道在什么程度上能用到 AI……同样，既然我目前在工作流中不使用 AI，我也不好说。但我的猜测是，如果你有兴趣，AI 也会非常擅长帮你寻找一些论文来阅读，因为你知道，咀嚼大量的技术记录正是它们擅长的事情。所以也许你甚至可以让你最喜欢的 AI 去去

<details>
<summary>Original English</summary>

**Guest**: I'm gonna uh have a hot take here if I if I might because it's sort of a it's sort of a a push I've been on recently. I don't think people should uh necessarily take a book recommendation from me. I want to recommend that people read a paper. I'm trying to get more people to just to just read papers because I realized I read a ton of papers. Like I am constantly reading papers on things that I am interested in. Like if I'm going to go do some programming in a in an area that I haven't done before, I will read a ton of papers. I'll crawl the references on papers. I'll read a survey and go gather all those references and read those references and crawl them back. And I find that I learn a ton that way. And I feel like a lot of programmers just don't do that. And so my recommendation would you don't have to read a specific paper. I'm not going to give you a specific paper. Read this one. Just think about the domain you're programming in. Do a search on Google Scholar for some part of that that you're interested in. Try reading a paper, following the references, see what you think. I think it's a great thing to do. And I get a tremendous amount of not just enjoyment from the education of it, but also just like more knowledge about what I'm doing. pretty much every time I do this, even if it's just to learn a little bit more about the historical record of how things got discovered, but a lot of times it's just like I learn about whole new techniques I just was not aware of. Uh because there's way too much out there for any one person to know. Uh and and I don't know to what I again since I don't currently use AI in my workflow, I couldn't say. But my assumption would be that AIS would also be very good at helping you find some papers to read if you were interested as well because that's you know chewing through a lot of uh the technical record is something that they do. Uh and so maybe you could even ask your favorite AI uh to to

</details>

<!-- chunk 16/16 -->

**Casey**: 根据你告诉它的一些信息，为你推荐一篇你可能会喜欢的论文。我不知道它们在这方面是否擅长，但我猜这是它们能做到的事情。

<details>
<summary>Original English</summary>

**Casey**: suggest a paper that you might like based on some things that you tell it. I don't know if they're good at that, but I'm guessing that's something they could do.

</details>

**Host**: Casey，非常感谢你参与这次对话。太棒了。

<details>
<summary>Original English</summary>

**Host**: Casey, thanks a bunch for this conversation. This was great.

</details>

**Casey**: 非常感谢邀请我。这是我的荣幸。

<details>
<summary>Original English</summary>

**Casey**: Thanks so much for having me. It's been a pleasure.

</details>

### 播客总结与反思

**Host**: 我很久以来一直想和 Casey 讨论性能问题，很高兴我们终于实现了。我有些希望行业里能有更多像 Casey 一样对高性能代码充满热情和兴趣的人。如果你坚持听到了本期节目的最后，你可能就是其中之一。我很欣赏 Casey 说话直言不讳。如果你关心性能，你会希望能够阅读汇编代码，并花些时间去读它。阅读汇编语言比编写它要容易好几倍。如果你能读懂汇编，你就能看到在机器底层发生了什么。而且，当你看到简单操作的汇编代码时，就很容易理解，比如说，为什么像 Python 这样的编程语言比 Rust 或 C 要慢得多。当 Casey 谈论那些宣称“用新语言重写服务获得 10 倍性能提升”的博客文章时，我忍不住笑了，因为这些重写通常与新语言本身无关，而是修复了最初导致性能问题的架构。虽然我们没有过多谈论 AI，但我发现 Casey 说的一点很有趣：游戏行业在几年前就迎来了它的“AI 时刻”，当时游戏引擎变得对几乎任何想开发游戏的人都触手可及。以前需要庞大的团队来同时构建游戏引擎和游戏，而现在一两个人的团队就能创造出完整的游戏。在大量优秀的新游戏发布带来短暂的繁荣之后，游戏开始大量涌入市场，数量之多以至于现在新游戏几乎不可能再自然而然地成为爆款了。因此，营销和发行变得不可或缺，即使是对于出色的游戏也是如此。有关游戏开发和性能软件的更多深入探讨，请查看 Pragmatic Engineer 关于这些主题的深度文章链接。如果你喜欢这个播客，请务必在你最喜欢的播客平台和 YouTube 上订阅。如果你还能给节目打个分，那真是万分感谢。非常感激，我们下期见。

<details>
<summary>Original English</summary>

**Host**: I've been wanting to talk about performance with Casey for such a long time, and I'm glad that we finally made it happen. I kind of wish the industry had more people as excited and interested in high performant code as Casey is. If you made it to the end of this episode, you might just be one of them. I appreciate that Casey did not beat around the bush. If you care about performance, you want to be able to read assembly and spend some time reading it. Reading assembly is several times easier than writing it. If you can read assembly, you can see what's happening at the machine level. And it's a lot easier to understand, for example, why a programming language like Python is much slower than something like Rust or C when you see the assembly code for simple operations. I was chuckling when Casey talked about these blog posts about how we rewrote our services in a new language and got 10x performance improvement and how those rewrites are usually not about the new language with fixing the architecture that caused the performance issues to start with. And although we did not talk much about AI, I found it amusing for Casey to say that the games industry had its AI moment years ago when game engines became accessible to pretty much anyone wanting to build a game. Before large teams were needed to build both a game engine and a game, and now teams of one or two can create full-blown games. After a brief spike of positive effects with lots of new good games released, games have flooded the market in such great number that it's now impossible for a new game to become a hit organically. So marketing and distribution becomes mandatory even for great games. For more deep dives related to game development and performance software, check out the link that Pragmatic Engineer deep dives on these topics. If you've enjoyed this podcast, please do subscribe on your favorite podcast platform and on YouTube. And a big thank you if you also leave a rating on the show. Appreciate it and see you in the next one.

</details>