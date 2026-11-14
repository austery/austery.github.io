---
author: AI Engineer
date: '2026-06-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=so9l_MwS2yg
speaker: AI Engineer
tags:
  - agentic-workflow
  - developer-productivity
  - remote-control
  - diffuse-thinking
  - burnout-prevention
title: 离开办公桌也能持续交付：AI智能体时代的开发者平衡术
summary: WorkOS的Zack Proser分享了在AI智能体时代保持开发者效率与身心平衡的策略。通过结合语音交互流、远程控制和智能体的夜间批处理，开发者可以将深度专注与离开办公桌的'发散思维'相结合，利用工具无限扩展产出的同时避免精力枯竭。
insight: ''
draft: true
series: ''
category: ai-workflow
area: PAI
project: []
people: []
companies_orgs:
  - WorkOS
  - Anthropic
  - OpenAI
products_models:
  - Claude Code
  - Cursor
  - Zed
  - Slack
  - Linear
  - Oura Ring
media_books: []
status: evergreen
---
### AI工具带来的上下文切换地狱

**[Zack]**: 大家好。我是Zack。我在**WorkOS**工作。感谢大家的到来。WorkOS提供即插即用的API，让你的软件能够进军高端市场，向企业客户销售更大的订单。但我现在要讲的是，面对每天涌现的各种疯狂的新工具，我正在寻找一种努力保持平衡的方法。所以，请举手示意一下，最近有没有人在和AI智能体一起编程时，感觉有点像这样，是的，尽管你完成的工作比以往任何时候都多，但到了每天结束时，你感觉自己已经彻底筋疲力尽了，对吧？就像肾上腺素在不断地飙升。

<details>
<summary>Original English</summary>

**[Zack]**: Hey everyone. Uh I'm Zack. I work at WorkOS. Thanks for coming. Uh WorkOS is um provides drop-in APIs that allow you to take your software and go upmarket and sell larger deals to enterprises. Uh but what I'm going to talk about now is um sort of the way that I'm finding to try and maintain balance with all the insane new tools that we're getting every day. So, show of hands if anyone is uh AI coding with agents lately and feels a little bit like this and yeah, despite, you know, getting more done than ever before, like you're completely fried at the end of the day, right? And like adrenaline dumping constantly.

</details>

**[Zack]**: 这就是我自己的亲身体验，我注意到其中最糟糕的一点是，上下文切换对我来说总是极其昂贵的，而现在情况比以往任何时候都要糟糕，对吧？所以，我认为我们很多人都有这种感觉。这些工具的强大程度令人发指，而我们的技能需求也比以往任何时候都要高，然而，我们才到了上午11点就已经精疲力尽了。

<details>
<summary>Original English</summary>

**[Zack]**: So, this has been my experience and I've noticed that some of the worst of it is like the context switching was always super expensive for me and now it's it's worse than ever before, right? So, I think a lot of us are feeling this way. Um like the the tools are are like insanely powerful and our skills are more in demand than ever before and yet we're like exhausted by 11:00 a.m.

</details>

### 用 Claude Code 自动修复 Bug

**[Zack]**: 我用最近发生的一个真实故事来具体说明这一点。我当时正在工作，我在WorkOS的应用AI团队（Applied AI team）。我正在构建一个**Slack**机器人，它可以让所有人都能平等地进行标准化的博客创作，这样任何一个人，即使他们以前从未写过博客文章，也可以进入Slack频道，发出一个简单的请求，然后就能得到一篇在各方面都符合标准规范的博客文章，对吧？然后我的一位同事报告了一个漏洞，说：“嘿，我们需要使用句首字母大写格式（sentence case），而目前的句首大写格式处理逻辑把我们的一些首字母缩略词（比如skim和SSO）给弄乱了。”

<details>
<summary>Original English</summary>

**[Zack]**: So, I'll I'll make this concrete with a recent story. I was working I'm on the Applied AI team at WorkOS. I was building a Slack bot that kind of democratized uniform blogging for everybody so that anybody that even if they've never written a blog post before can come into a Slack channel, make a simple request and get a uniform blog post that does everything the correct way, right? And there was a bug that one of my colleagues reported that said, "Hey, we need to use sentence case and the sentence case uh pass right now is mangling some of our acronyms like skim and SSO."

</details>

**[Zack]**: 通常情况下，我肯定会陷入我刚才向你们展示的那种窗口地狱中。但这一次，我做了一个非常微小的改变，结果却产生了极其巨大的影响。我给**Claude Code**——这是我目前最喜欢的工作窗口——赋予了读取和写入Slack的能力。而且它已经有了我的**Linear**工单系统的访问权限。所以我告诉它：“你需要修复这个问题，然后你还需要验证你自己的工作，在完成这些之前不要停下来。”大体上，这就和我左边的终端窗口显示的一样，我运行了Claude，我说：“修复这个句首大写执行器，它把缩略词弄乱了。”

<details>
<summary>Original English</summary>

**[Zack]**: So, normally I'd be living in that kind of window hell that I just showed you. And um instead this time I made a very minor change that ended up being super impactful. So, I gave Claude Code, which is my current like preferred aperture for working, the ability to read and write to Slack as well. And it already had my linear ticket access. And so, I told it, "You need to fix this and then you also need to verify your own work and don't stop until you've done that. And so roughly this is what it looked like if my terminal's on the left, you know, I ran Claude and I said fix the sentence case enforcer, it's mangling acronyms.

</details>

**[Zack]**: 于是它去执行了，而且因为它有连接到Slack的MCP（Model Context Protocol，模型上下文协议），它就把消息发到了这个博客发布的频道里。然后它正在开发的这个博客机器人，也就是坐在我本地工作目录代码库里的那个机器人，接收了消息，跑完了完整的流程，并到达了相关的步骤。接着Claude验证了访问权限和最终结果，然后说，好的，现在我已经彻底修复了这个bug。所以当我再回来看的时候，我回到的是一个已经闭环、被修复完毕的状态，我不需要再告诉它：“嘿，这部分还是坏的。”

<details>
<summary>Original English</summary>

**[Zack]**: And so it went and did that and because it had an MCP connection to Slack, it it fired it into this blog post channel. And then the blog bot that it's working on, you know, it's sitting in that code base on my in my working directory, picked it up and ran all the way through and got to the step that was relevant. And then Claude verified the access and the the outcome and then said, okay, now I have I definitively fixed this bug. So when I came back to it, I came back to a completed loop that was had been fixed and I didn't have to tell it, hey this part's still broken.

</details>

**[Zack]**: 那种感觉令人难以置信，我认为这是我们所有人将来都要、而且已经开始构建到我们工具箱里的重要组成部分。但这同时也让我感到害怕，因为我意识到这几乎没有上限，对吧？现在这些工具的威力堪比核武器，而我们的神经系统相对来说依然很古老。所以最近我在思考的是，在这个世界里，我该如何找到属于我自己的“开发者平衡”，对吧？为什么不直接叠加相同的流程，为什么不利用这套机制，每天在工作中修复150个bug呢？

<details>
<summary>Original English</summary>

**[Zack]**: So that felt incredible and I and I think that that's an important part of what we're going to all build into our toolkit and we already are. But it also scared me because I realized that there's like there's there's nothing there's no ceiling to this, right? So the tools are nuclear now and our nervous system is still relatively ancient and so the thing that I'm thinking about recently is is how do I find my own kind of developer balance in this this world, right? So why not just stack that same process, why not use that harness and just fix 150 bugs every day at work?

</details>

### 人类注意力才是真正的瓶颈

**[Zack]**: 嗯，你知道，智能体确实能够做到这一点，特别是如果你给了它们足够的上下文、正确的验证标准，以及验证自身工作所需的工具。但说到底，我无法真的驾驭所有这些东西，并确保质量达标。而且到了第二天，我还要出现再进行8个小时的工作，而不能被彻底击垮。

<details>
<summary>Original English</summary>

**[Zack]**: Well, you know, the agents can kind of do that especially if you give them enough context, if you give them the right verification criteria, if you give them the tools to verify their own work. But at the end of the day, like I can't actually sit on top of all of that and make sure that the quality is there. And also show up the next day for like another 8-hour work session and not be completely destroyed.

</details>

**[Zack]**: 所以，我认为我发现的，也是我最近交谈过的许多其他人所发现的，那就是智能体现在已经不是瓶颈了，我认为这种情况会越来越明显，但我们人类才是瓶颈。智能体可以无限扩展，特别是昨晚通过Claude API开放之后。你可以给它们提供验证标准和匹配该标准所需的工具，但我们的注意力依然停留在肉身世界（meatspace）里，如果可以这么说的话，而且它在重负载下依然会退化。它本质上依然是硬性约束。

<details>
<summary>Original English</summary>

**[Zack]**: So what I think I'm finding and I think a lot of other folks I've been talking to you recently are finding is that the agents are not the bottleneck now and I think that's going to increasingly be the case, but we are. So agents can scale infinitely especially now that they're made available as of last night via cloud API. You can give them verification criteria and the tools that they need in order to match that criteria, but our attention is still, you know, in meatspace, if you will, and it still degrades under load. It's It's still the hard constraint, essentially.

</details>

**[Zack]**: 这种感受不仅我有，不仅你有，演讲开始时举手的每个人都有。就像上周Simon Willison最近说的，他启动了四个并行的智能体，结果上午11点他就被彻底掏空了。所以，他建议我们所有人找到自己个人的平衡点以及我们个人的极限，这现在是我们所有人都需要自己去完成的事情。在应用AI团队中，我也确实看到了这一点。

<details>
<summary>Original English</summary>

**[Zack]**: Uh and this is something that's not just me and not just you, everyone that just raised their hand at the beginning of this talk feeling it. Um as Simon Willison said recently, like last week, that he fires up four parallel agents and he's wiped out by 11:00 a.m. And so, he suggests that all of us finding our own individual uh balance and and sort of our personal limits is now something that we all need to do on our own. I'm definitely seeing this also on the Applied AI team.

</details>

### 构建开发者平衡的三个策略

**[Zack]**: 所以，这里有一些提示和技巧，或者说是我最近使用并取得成功的方法，我会分享出来。其中一些我相信你们可能已经见过了。我们从根本上需要让人类开发者与这种新的工作方式取得平衡，因为现在我们有了这些超级强化的工具，如果只是线性扩展你在工作中的承担量和输出量，你将比以往任何时候都更快地把自己燃烧殆尽。所以，在我脑海中，我把它拆解成这样：智能体在无限扩展和无限循环直到达到你给定的标准方面，会做得更好。

<details>
<summary>Original English</summary>

**[Zack]**: So, uh here's a couple of tips and tricks or things that I've used like recently and found success with, and so, I'll share them. Some of them, I'm sure you've already seen. Um so, we essentially need to bring the human developer into balance with this new way of working because now that we have these like hyper-charged tools, it's faster than ever to burn yourself out, especially if you just scale linearly in terms of your what you're taking on and at work and what you're you're outputting. And so, see um the way that I'm sort of breaking it down in my mind is that agents are going to do better in terms of infinitely scaling, uh looping infinitely until they have uh reached the criteria you've given them.

</details>

**[Zack]**: 但我们仍然拥有判断力、品味，知道什么才算真正被解决，知道在人类需求和商业需求方面，这个标准是否真的得到了满足。所以，这是我目前看到的堆栈的一个初步分解。第一个我称之为“信号层（signal layers）”，找不到更好的词了，我稍后会展开讲讲。第二个是“语音优先工作流（voice-first flows）”。我现在进行语音优先编程已经大约一年半了，这改变了我的生活。

<details>
<summary>Original English</summary>

**[Zack]**: Um but we still have judgment, taste, knowing that something is actually solved, knowing that the the criterion is actually met in in uh in terms of human needs and business needs. And so, this is kind of an early breakdown of the stack that I'm seeing. So, the first I'm calling signal layers for lack of a better word, and I'll I'll develop that a little bit in a second. Uh the second is voice-first flows. I've been doing voice-first coding now for about a year and a half, and it's been life-changing.

</details>

**[Zack]**: 然后是“远程控制（remote control）”，这正变得越来越通用、越来越适用，而且我认为我们将开始在各地看到它的身影。目前，这还是某种程度上Claude Code特有的功能。最后是“系统自我改进”。所以，只需对你的工作方式和你保存消息历史的方式做一点极其微小的改变，在这个拥有能瞬间阅读大量资料并在循环中为你寻找模式的智能体时代，就能启用令人难以置信的强大功能，甚至不需要你费心去记住它。

<details>
<summary>Original English</summary>

**[Zack]**: Um and then remote control, which is becoming more and more recent uh more applicable, and I think we're going to start seeing it everywhere. Right now, it's sort of a Claude code-specific thing. And then the system improving itself. So, um changing just minimal things about the way that you work and the way that you store your own message history, even, can enable incredibly powerful passes now that you have agents that can rip through all of that um material in seconds and find patterns for you on a loop without you even needing to remember to do it.

</details>

### 第一层：建立信号过滤系统

**[Zack]**: 所以，让我们快速看看每一个代表什么意思。回顾一下我刚才给你们看过的那个我让Claude去修复的bug。我的问题是，如果我自己去Slack上梳理消息，有80%的几率我会被其他的帖子分散注意力。我会发现其他的东西，或者其他人会有新的请求找我，那会把我从当前任务中抽离出来。所以，取而代之的是，我让Claude Code拥有读取Slack的能力，并让它在一个循环中运行，这样它就能看到是否有人@我，是否有私信，是否有真正需要处理的高优先级请求。

<details>
<summary>Original English</summary>

**[Zack]**: So, let's take a quick look at what each of these uh what I mean by this. So, calling back to the the bug that I showed you that I fixed and had Claude do it. Um my problem is that if I were to go and go comb through Slack myself, uh it's like 80% guaranteed that I'm going to get distracted by some other thread. I'm going to find something else or somebody's going to have a new ask for me and that's going to kind of pull me off task. And so, instead I had Claude code um be able to read my Slack and do it on a loop so that it can see are there at mentions, are there DMs, are there actually like high priority asks that need to be actioned?

</details>

**[Zack]**: 与此同时，它一直通过MCP连接拥有我Linear系统的访问权限，因此它可以去除重复的请求并找到真正的工单。这就是一种足够好的门面掩护，让我能够继续保持专注，把我的注意力集中在作为一个人类开发者应该关注的核心事物上。而且我认为现在有很多涌现出来的工具，就像我们今天看到的那样，将为你提供你喜欢的任意定制化工作体验。但它的核心在于，你要如何管理我们现在都要面对的极其疯狂的流量、通知和噪音干扰。

<details>
<summary>Original English</summary>

**[Zack]**: Meanwhile, it's all all always had access to my linear via MCP and so it can deduplicate asks and find the real tickets. And this is just enough of a sort of facade for me to allow me to continue to focus and maintain my attention on the things that are the key for me to be able to do as the human developer. Uh and I think that there's a ton of tools that are coming out that we're all seeing here, too, that are going to make this kind of like um just a bespoke experience wherever you want to work. Um but it's sort of about managing the now extra insane levels of traffic and pings and and noise that we're all going to deal with.

</details>

### 第二层：语音优先的并行流

**[Zack]**: 第二个就是“语音优先工作流”，这也是我想分享的另一个小贴士，如果你还没有尝试过的话。我强烈推荐。我是一个非常喜欢打字的人。我从3岁开始就练习打字。我想在最好的状态下，用我不标准但独特的打字姿势和我这双巨大的香肠手，我的打字速度达到了每分钟90个词。但是现在有了语音优先工具，速度显著提升。我在普通的一天里，常常能达到每分钟184个词的速度。

<details>
<summary>Original English</summary>

**[Zack]**: The second is just voice-first flows, like another um just nudge if you haven't tried this yet. Uh highly recommend it. I'm a person that love to type. I've grown up typing since I was 3 years old. I think at my best I was hitting 90 words per minute in a weird non-standard way with my uh giant sausage fingers. But now with uh voice-first tools, um it's significantly faster. I regularly hit like 184 words per minute on a on a given day.

</details>

**[Zack]**: 它所实现的功能，不仅仅是让你能快速地向一个窗口输入语音，然后让任务更快完成；它其实解锁了并行的工作流，对吧？想象一下，如果我们在最上面，我是一个开发者，我正同时在三个不同的**Cursor**窗口说话，或者向**Codex**说话，同时也跨多个标签页向Claude说话。由于我的输入速度是每分钟184个词，所以它们通常已经开始跑起来了，而传统的开发者可能还在敲他们的第一个提示词。

<details>
<summary>Original English</summary>

**[Zack]**: And what that enables is not just speaking into one thing quickly and and having it done, you know, faster, it enables kind of parallel workflows, right? So, imagine if at the top, I'm a developer who's speaking across three different cursor windows or into codex and then also into Claude across multiple tabs. And because it's 184 words per minute, they're now often running while a traditional developer is still typing in their first prompt.

</details>

**[Zack]**: 你如果想想，你知道的，微小的优势会迅速累积，对吧？在软件领域，在一年、两年、三年的工作周期中，这会产生多大的复利？这对我来说极其关键，因为随着我对语音流越来越熟练，它也解锁了我接下来要展示的内容，那就是：你在真正的办公桌前花的时间越来越少，却依然能够完成工作。

<details>
<summary>Original English</summary>

**[Zack]**: Um and I think that if you consider, you know, that that small things grow quickly, right? In in terms of software, what how does this compound over the course of a year, two, three years of working? Um and this has been really key for me because uh as I get more and more comfortable with voice flows, it also enables what I'm going to show next, which is spending less and less time at your actual desk while still getting work done.

</details>

### 第三层：淋浴原理与远程控制

**[Zack]**: 接下来就是“远程控制”。目前，这多少算是Claude Code专属的功能，但我预计这会迅速改变。所以在深入看这在Claude生态系统中具体意味着什么之前，我们先来聊一下“淋浴原理（Shower Principle）”。我相信大家都听过这个理论。它的基本思想是，人有两种思考模式。当你全身心地专注于IDE，你敲代码、搜索符号时，你很可能是处于专注模式（focus mode）。你脑海中很可能有一个非常清晰的蓝图，知道自己想构建什么，以及打算怎么去实现。

<details>
<summary>Original English</summary>

**[Zack]**: The next is remote control. Right now, this is kind of um a Claude code specific thing, but I expect that's going to rapidly change. So, before we go look at exactly what that means in the Claude ecosystem, um we'll just talk touch on the shower principle. I'm sure everyone has heard about this before. The basic idea is that there's two modes of thinking. If you're hardcore focused in your IDE and you're typing and you're searching for symbols, you're likely in focus mode. You likely have a very clear blueprint in your mind of what you're trying to build and how you want to do it.

</details>

**[Zack]**: 那种专注力非常适合将某件事推向终点，以及精确地构建你想要的东西。但它同样也极容易让你产生盲区，忽视解决某些问题所需的创造性方案，并加剧你的思维受限。但悖论就在于，当你站起身走开，你开始和你的狗玩耍，或者带孩子去公园散步，或者洗个澡，这时就像是灵光乍现，你瞬间得到了完整的解决方案。淋浴原理的核心论点就在于，潜意识基本上总是在帮你咀嚼这些难题。

<details>
<summary>Original English</summary>

**[Zack]**: And that focus is excellent for getting something over the line and building something exactly the way you want. But it's um also ideal for having blind spots and missing what you need to uh creative solutions to things and and increasing your inhibitions. Um but paradoxically, when you get up and walk away and you start playing with your dog or or walking your kids to the park or taking a shower, you uh it's like there's a flash of insight and you get the full-form solution. And the the thesis of the the shower principle is that basically your subconscious is always churning on these hard problems.

</details>

**[Zack]**: 所以，只要你走开，打开视野，放下戒备，“发散模式（diffuse mode）”能让你更快地看到更具创造力的解决方案。我在这里要强调的关键一点是，我们其实一直都具备这种能力，而且你知道，有上百本书都在讲这个，我们也讨论了几十年，但在过去，发散模式和离开办公桌意味着停止工作。但现在情况完全不同了，尤其是有了像远程控制这样的功能。

<details>
<summary>Original English</summary>

**[Zack]**: And so, as soon as you walk away and kind of open the aperture and lower your inhibitions, diffuse mode allows you to see, you know, more creative solutions quickly. And the key thing I want to stress here is that we've always had this and there's been, you know, hundreds of books written about it and we've all talked about it for decades, but it used to mean that diffuse mode and walking away from your desk meant stopping work. And that is no longer the case, especially with things like remote control.

</details>

**[Zack]**: 那么远程控制究竟意味着什么？我们就以Claude Code生态系统为例。如果我要开启一个Claude Code会话，我会传递remote control参数，或者运行远程控制指令，或者在配置中启用它。这样我就可以在我的办公桌前开始工作。它运行在我的开发机器上，拥有例如访问文件系统等的权限。但只要我离开后，在手机上通过不同的网络（CDMA，脱离了家里的Wi-Fi）打开Claude——比如在几英里外的荒野小径上——我依然能看到那个会话。

<details>
<summary>Original English</summary>

**[Zack]**: So, what remote control means in the Let's just take the Cloud Code Ecosystem example. If I'm starting a Cloud Code session, I pass the remote control flag, or I run remote control, or I have in my config enable remote control, then I can start at my desk. It's running on my dev machine. It has access to, you know, the file system, etc. But then as soon as I uh pull up Cloud on my phone on a different network, CDMA, off the Wi-Fi from my house, like, you know, miles away in the trail, I can still see that session.

</details>

**[Zack]**: 我依然能和它对话，发消息，戳它。这极其强大，因为我总是在离开办公桌的那一刻，想出最棒的点子和所有的解决方案。因此，我现在准备提出的建议就是：将这两种模式结合。你可以以专注模式开启你的一天，把所有需要做的重要任务加载完毕，然后让你的智能体运转起来，确保工作如你所愿地推进；接着，离开办公桌，减少你的RSI（重复性劳损），减少你整天维持同一个坐姿带来的身体损伤，去散散步，但你依然保持超级高效的产出。

<details>
<summary>Original English</summary>

**[Zack]**: and I can still talk to it and send messages and poke it. And that's incredibly powerful because I get my best ideas and all the solutions as soon as I've walked away from the desk. And so, what this enables now is uh and what I'm going to propose that enables is um starting your day in focus mode, getting everything loaded up that you need to do that's super important, and then um getting your agents turning, making sure work is proceeding the way that you want, and then leaving the desk, reducing your RSI and the number of like physical injuries you're getting from sitting in the same position all day, and going and taking a walk, but still being super productive.

</details>

**[Zack]**: 针对这一点，我已经做了大量实验。去年我甚至拍了一部32分钟的视频，来证明这是可行的，证明你可以在树林里用手机进行PR（Pull Request）代码审查。所以我不仅是在吹嘘，这是切实可行的。这最棒的地方在于，当你在手机上对那个会话下指令时，在Claude Code的会话实际上还是在你的机器上运行，依然有权限做它需要做的事。如果你突然有了一个天才的点子，觉得“这个设计绝对能成”，那你直接把想法发回去就好了。你不必非得强迫自己等回到办公桌再去实现它。当你回来时，你会发现这想法已经被执行并应用了。

<details>
<summary>Original English</summary>

**[Zack]**: And I have done a ton of experiments with this, and I even filmed a 32-minute film last year like proving that you can do this and review PRs from your phone in the woods. Um so, I'm I'm not just blowing sunshine. Like, it's it's possible. Um and the really nice thing about it is that when you talk to that session through your phone, uh that's the session on Cloud Code is still running on your machine, still has access to do whatever it needs. If you have some genius idea of like this is the design that's going to nail it, then you just fire that back. You don't have to remember to do it when you get back to your desk. You're going to come back to it having already been applied.

</details>

### 安全与验证的三个阶段

**[Zack]**: 当然，要做到这一点，我经常说速度是以安全为前提的，因此执行这个流程并拥有验证机制，是分为几个层级的。随着像Chrome Use甚至为智能体准备的Computer Use等新工具的上线，这种验证将变得更加精密。第一级就像是最基础的lint代码规范检查、构建和单元测试对吧？让配备钩子（hooks）的智能体每次都在代码级别自我验证工作，以确保没有搞坏任何东西。

<details>
<summary>Original English</summary>

**[Zack]**: So, of course, in order to do this, I I often say that speed requires safety, and so there's levels of doing this and having verification. And And now with new tools coming online like not only Chrome use, but also computer use for agents, um this is going to get more sophisticated. The gate one is like the minimal lint and build and unit test, right? Let the agents with hooks um every single time verify their own work at the code level to make sure nothing's broken.

</details>

**[Zack]**: 第二级则是当你告诉Claude Code，你必须使用浏览器验证自己的工作，点进去检查，并确保你没有把登录功能搞坏，举例来说。第三级更接近于**Anthropic**所构想的那种Constitutional AI（宪法AI），在他们的设定中，会有一部“宪法”规定你必须做什么，然后另一个智能体会来验证你是否正确执行了，否则它会给出你需要修正的反馈。

<details>
<summary>Original English</summary>

**[Zack]**: You know, gate two is when you tell the Claude code that you must verify your own work with the browser, click through it, and ensure that you haven't broken login, for example. Um three is closer to like constitutional AI in the in the way that Anthropic kind of conceives of it, where they're talking about there's a constitution of what you must do, and another agent will kind of come and verify that you did that correctly, otherwise give you feedback that you need to action.

</details>

### 重塑开发者的典型一天

**[Zack]**: 那么综合以上所有，这究竟会如何改变一个在职软件开发者的日常？正如我刚才所说，我建议在每天的开始阶段安排一段深度专注的时光。你可以过一遍**GitHub**里所有的积压任务，把你需要排队的软件生命周期杂务处理好，全部丢给Codex，接着可能在IDE或者Claude Code中，开始着手你真正关注的核心功能开发。因为你可以在手机上访问它们，所以当它们沿着你今天定下的工作轨道前进时，你基本上就可以走开了。

<details>
<summary>Original English</summary>

**[Zack]**: Um and so taking all this together, how does this actually change a working software developer's day? Uh so like I said before, I propose like a deep focus session in the beginning of the day. You might go through all the backlog tasks in GitHub, the software development life cycle chores that you need to queue up, fire those all into Codex, start working on the features you really care about in an IDE, perhaps, or in Claude Code. And then essentially you walk away after getting them kind of going on their the work tracks that you've identified for that day, because you have access to them on your phone.

</details>

**[Zack]**: 这样一来，即使你是在户外漫游，连接着Edge或LTE网络，你也能把消息发回去，并且可以在你的手机上开始审查那些生成的PR。而且再次强调，由于我们目前还没碰触到大语言模型的能力边界，像在GitHub移动端自然语言地给一个PR留评，@Claude、@Cursor智能体或者@Vercelbot，说“这个需要改”，这是非常合乎常理的，并且大多数时候它都能改对。

<details>
<summary>Original English</summary>

**[Zack]**: So even when you're out wandering around on on the edge or on LTE, you can fire messages back to them, and you can start reviewing the PRs as they come through on your phone. And now, again, because agents are we haven't quite found the LLM wall, like with Opus 4.6 is quite reasonable to leave a natural language comment on a PR in GitHub mobile at Claude or at, you know, cursor agent or at Vercelbot, and say this needs to change, and most of the time it's going to get it right.

</details>

**[Zack]**: 于是这就促成了这种完整的闭环，你坐在办公桌前的时间越来越少，你拉伤手腕和双手的时间越来越少，但你在户外走动、吸收新鲜氧气时，却能获得更好的想法，同时你依然处于循环之中，依然在引导工作向前推进并取得进展。所以，我在这里快速展示一下，我在做这类实验时发现的一个关键点：如果在这一周的开始，你只是单纯地使用这些工具，周一你会觉得爽翻了，我能横扫海量工作。周二感觉也一样。

<details>
<summary>Original English</summary>

**[Zack]**: Um and so this kind of enables this complete loop, where you're actually spending less and less time away from your desk, uh less and less time at your desk, you're spending less and less time injuring yourself, your wrists, your hands, um and you're getting oxygen when you're getting better ideas when you're out walking around, but you're still in the loop, and you're still directing work forward and making progress. So, um I'll just quickly show that a key learning that I found in in doing this kind of as an experiment is that uh if you just use the tools on your own, like in the beginning of the of the week, um Mondays feels amazing. I can rip through a ton of work. Tuesday feels the same.

</details>

### 第四层：分析 JSONL 日志以实现自我改进

**[Zack]**: 然后在周中，我收到了一大堆随机的需求，有点打乱了我的节奏。到了周五，我就彻底报废了，我根本不记得我到底他妈干了什么。虽然我知道工作交付了，但一切都很混乱。正如和我一起在场的这位杰出的同事Nick提醒我的那样，所有Claude Code的对话记录都会作为JSONL文件保存在本地。这使你能够开始更聪明地工作。你可以安排一个定期流程，让你的智能体在每周结束时（如果你愿意，甚至可以在每天结束时），回溯并审查你自己与它的对话记录。

<details>
<summary>Original English</summary>

**[Zack]**: Now I got a bunch of random asks in the middle of the week that kind of threw me off course and and then by Friday I'm completely wasted and I don't remember what the hell I did and uh I know that work shipped, but it's all disorganized. Uh as my uh illustrious colleague who's with us here, Nick, reminded me, all of Claude Code's conversations are saved locally in JSON L files. And what that enables you to do um is to start working smarter and have a scheduled pass where your agent goes back and reviews your own conversations with it at the end of every week, at the end of every day if you want,

</details>

**[Zack]**: 你可以对它说：“去寻找这些模式：在哪几次任务中，你耗费了大量‘思考token’才把事情做对；或者在哪些任务里，为了弄清模棱两可的地方、把任务正确做完，你和我不得不反复沟通。找出我们缺失的那些技能。如果我们已经有了特定的工具、MCP服务器或者特定技能，情况会有什么不同？我们应该如何缩短这个反馈回路，让下周不再发生同样的事情？”通过定期审查这些由你自己使用的工具所产生的数据，你的整个系统或整个工具链就能够变得越来越聪明。

<details>
<summary>Original English</summary>

**[Zack]**: and say, "Look for the patterns where you had to do a significant amount of spending thinking tokens to get something right or you and I had to go back and forth and eliminate ambiguity in order to get a task done correctly and figure out the skills that are missing. What's the delta for if you had these tools, this MCP server, or these skills? How could we tighten that loop so that it doesn't happen next week?" And then this is a way in which just by working regularly with your own tools, your entire system or your entire harness can start to get smarter.

</details>

**[Zack]**: 目前Claude Code内置了一项技能，它不仅能构建自己的技能，还能评估技能、改进技能，并且能把自然语言提示词转化为你所需的定制化技能。所以我强烈推荐大家这么做，然后不断缩短这个回路。这样一来，你依然能够把工作完成，依然能在公司交付你必须交付的内容，但你坐在办公桌前的时间却越来越少。这带来的结果是：你在工作时，依然通过你首选的主力窗口（无论是**Zed**、Cursor还是终端里的Claude Code）来保持专注。

<details>
<summary>Original English</summary>

**[Zack]**: Um there is a built-in skill in Claude Code now to not only build its own skills, but evaluate skills, improve skills, and take natural language prompt and just create bespoke skills that you need. Um so highly recommend doing that and then tightening that loop so that you can still get your work done, still deliver what you need to at work, but spend less and less time at your desk. And so what that starts to look like is you're working, you're still paying attention through your main preferred aperture, whatever it is, maybe it's Zed, maybe it's Cursor, maybe it's Claude Code in the terminal,

</details>

**[Zack]**: 但因为你没有把工作期间积累下来的上下文轻易丢掉，你的模式库正在不断地被构建和积累。你把你所有的工作会话都当做黄金来看待，实际上它们确实是黄金。因为只要用Opus 4.6过一遍，就能发掘出海量的技能，让我们知道：“如果下周我们具备了这些能力，我就能以高效得多的方式、快得多的速度和可靠得多的手段来完成这件事。”

<details>
<summary>Original English</summary>

**[Zack]**: but the patterns are being built up because you're not trashing all of the context that you're building up while working. And so you're treating all of those sessions as gold, which they are because a single pass with Opus 4.6 can reveal a ton of skills that if we had this next week, I can do this way more efficiently, way more quickly, in a way more reliable manner.

</details>

**[Zack]**: 最后我再分享一个有趣的尝试。我非常喜欢我的**Oura Ring**智能戒指，我拿到它之后做的第一件事，就是通过MCP把它连上。有一些GitHub项目能帮你实现这一点。然后我把这些数据交给了Claude。所以，当我和Claude就某个项目发生争执时，有时候它会直接怼回来：“你昨晚根本没睡觉，所以今天我们只处理这个项目的前半部分，剩下的部分我们不做了，你留到明天再搞。”然后我会回敬它：“去你的，你只是一台机器，按我说的做。”虽然我最后还是强行继续干了，但至少，我确实思考过应该休息一下。

<details>
<summary>Original English</summary>

**[Zack]**: Uh last thing I'll just share for um for giggles. Uh I love uh my Oura Ring, and one of the first things I did was connect it via MCP. There's a couple of GitHub projects that enable you to do that. And then I gave it to Claude. And so, uh when I'm arguing with Claude about a project, there there are times he will literally come back and say, uh "You didn't sleep last night, and so we're going to tackle the first part of this, and we're not going to do the rest of it, and you're going to do it tomorrow." And then I tell him, "The hell with you, you're a machine, do what I want." And I just do it anyway, but at least I thought about taking a break.

</details>

**[Zack]**: 这是一件挺好玩的事，但我认为这也确实蕴含着某些道理：你应该开始从全局视角看待自己的工作。不仅仅是记录了你和哪些同事聊了什么对话、处理了哪些工单，或者你掌握了什么技能，它还包含了你身体的状况：你什么时间段能集中注意力最好，你睡了多久。我认为这极其重要，因为如果我们只是盲目地去用这些工具，那默认的结局必然是枯竭。有了LLM的推波助澜，如今这种枯竭会变成“涡轮增压版枯竭”，来得极其迅猛，而且比以往任何时候都更容易发生，对吧？

<details>
<summary>Original English</summary>

**[Zack]**: Um And so, uh this this is kind of a fun thing, too, but I I do think there is something to this as well, uh where you start to actually look at your work holistically, not not just in terms of the conversations you're having with which colleagues, um your tickets, and everything, the skills that you have, but then also the condition of your body, what times are you able to focus the best, how much sleep are you getting. Um and I think this is super important because if we just kind of do this mindlessly, the default path is going to be burnout, but now burnout turbo, like super fast and easier than ever before, enabled by LLMs, right?

</details>

**[Zack]**: 而具备刻意设计的成长路径则更像是：我如何在保全自我身心健康的前提下，依然产出我最卓越的工作成果？如何引导智能体去替我处理琐碎杂事，而我仍然负责把控质量、审查代码，以及推动最终产品的发布？如果你觉得这些内容很有趣，我建议你尝试去构建哪怕是最简单的“单一层级”。最简单的做法，就是把你觉得切换成本最高的工具接入到你偏爱的主力工作窗口中，比如接入Slack或Linear。给Claude Code加上一些验证网关，现在甚至简单到只要传递 `--chrome` 参数，赋予它访问自身浏览器的权限即可。

<details>
<summary>Original English</summary>

**[Zack]**: Um whereas the intentional path is a little bit more like, how do I preserve myself and still do my best work, and direct uh agents to do the minutiae for me while I'm still responsible for the quality and the review, and and actually shipping. Um so, uh if you find any of this interesting, I would recommend try uh building one single layer. It can be as simple uh as just plugging in Slack or Linear, whatever you find to be the highest um cost context switch for you into your preferred pane of glass that you're working with. Add some verification gates you don't have for Chrome for for uh uh Claude code, it's as simple as passing --chrome now and giving it access to its own browser.

</details>

**[Zack]**: 然后利用你省下来的那点闲暇和时间盈余，去一个人在公园野餐，对吧？或者去散散步，或者和你的狗玩玩，不管什么都行。所以，是的，这些工具现在拥有核爆级别的威力。而我们的神经系统依然是远古时代的版本。所以我最近满脑子思考的，就是努力在这个新世界中找到某种开发者的平衡。希望这些对你们有帮助。非常感谢大家！有什么问题吗？

<details>
<summary>Original English</summary>

**[Zack]**: And then with the margin that you get back, use that to go to either picnic in the park alone, right? Or go on a walk, or, you know, play with your dog, or whatever the case may be. So, yeah, the tool The tools are nuclear now. Um our nervous systems are still ancient. And so, what I'm thinking about these days is trying to find some developer balance. Hope that was helpful. THANK YOU SO MUCH. ANY QUESTIONS?

</details>

### Q&A环节：年轻开发者与技能培养

**[观众]**: 是的。我也想问。我可能在职业生涯中算比较早期的。这意味着技能发展也非常重要。这就需要去做很多深度工作，至少就我来说，我之前就是通过大量的深度工作来学习编程的。在这个过程中会遇到很多问题，然后去跨越这些障碍。

<details>
<summary>Original English</summary>

**[观众]**: YES. YEAH, so I guess I'm somewhat early in my career. Uh-huh. And that means skill development is also very important. >> Yep. And uh also doing deep work Well, at least like, you know, I learned to program by doing a lot of deep work. Getting into running into issues. Yep. And uh big overcoming those hurdles. Totally.

</details>

**[观众]**: 虽然我也非常支持这种新的工作流，但它某种程度上让我感觉到……它似乎会造成我的“技能赤字（skill deficit）”。就是说，它让学习本身变得更难了。所以，您有没有在这个新工作流中找到某种平衡方式呢？让我在继续提升硬技能的同时，也能享受这种方法带来的红利。

<details>
<summary>Original English</summary>

**[观众]**: Um it's sort of And and I'm also super on board with this new flow of working, but it's sort of almost felt like a uh it's been a skill deficit for me. Like, it's made made it harder to learn. So, have you found a balance for that work? Yeah, you can still push forward and at that skill level, but um while getting benefits of this approach.

</details>

**[Zack]**: 很好的问题。为了确保录音能听清，我重复一下你的问题：问题核心在于，如果我正处于职业生涯的早期，这本该是大量积累技能的阶段，但如果用了智能体，那我怎么去进行核心的硬技能开发呢？我的担忧是，这会不会反而夺走了我锻炼技能的机会？我该怎么管理并维持学习的节奏呢？我对这件事的看法是——这也是我见过关于这个问题最好的一条建议，那就是：不要使用AI去做你本就不知道该怎么做的事情。

<details>
<summary>Original English</summary>

**[Zack]**: Yeah, excellent question. So, to repeat in case it's not recorded, um the question is basically if I'm early in my career, uh this is all like skill advancement, but then how do I actually do the hard skill development? And it's my fear is almost that this could kind of take it away from me, right? And how do I manage that or maintain it? The way I think about that is the best piece of advice I saw for that was basically, don't use AI to do something that you don't know how to do already.

</details>

**[Zack]**: 因此，我平时会部署像是TypeScript系统、RAG系统，以及做AWS的线上部署，因为在过去很多年里，我是用那种“硬核”的困难方式亲手去做这些事情的。所以我身上带着那些伤疤和由于过去踩坑留下的疤痕组织。所以我能立刻揪出Claude犯的错，比方说，“不，你这做法太荒谬了。我们不这么干。”一旦它开始产生幻觉或者给出一个很糟糕的主意，我能瞬间反应过来，因为我曾经花时间真刀真枪地积累过这方面的经验。

<details>
<summary>Original English</summary>

**[Zack]**: Um so, I'm shipping like TypeScript systems and Rag systems and and doing AWS deployments because I used to do that the hard way for many many years. And so, like, I have that battle um those battle scars and like scar tissue of doing it. And I can immediately catch Claude, for example, and and say like, no, that's insane. We're not doing that, um the second it says something that's a hallucination or is not a good idea, because I've spent that time building that up.

</details>

**[Zack]**: 我认为你绝对应该继续去死磕这些底层硬技能。你应该深入研究这些东西，并且我认为借助大语言模型和AI，你完全有可能钻得更深、学得更快，甚至可以对它说：“来测试一下我吧，我是不是漏掉了什么？我在这块的心智模型还是有点模糊。”所以我极力推荐你这么做。去构建那些核心技能，依然要手写一些代码，亲自去体会其中的痛点。一旦你建立起了这些技能，并且对它们有了足够的自信，那时候你再去借助LLM和Claude更快地交付出海量的Ruby应用，这就是完全没有问题的了。

<details>
<summary>Original English</summary>

**[Zack]**: I think you should absolutely still do that. I think you should go deep on those things and I think it's even possible with LLM's and AI to go deeper, faster, and to even say like test me, where do I where am I missing this and like my mental model here is still murky. So, highly recommend doing that. Like build some of those skills, still code some stuff by hand, figure out what's painful about it. But then once you start to develop those skills you have confidence in them, then it's okay to kind of you ship a ton of Ruby apps, it might be okay to start shipping Ruby apps faster with LLM's and Claude.

</details>

**[观众]**: 您刚才也提到，只有当那是你自己本来也想亲自写的代码时，你才会把它委托出去。

<details>
<summary>Original English</summary>

**[观众]**: You also said only delegate code if you want to write your own work.

</details>

**[Zack]**: 对，我会的。如果我现阶段的重心是磨练技能，打下坚实的基础，是的，我会建议这么做。我还要说，别因此感到泄气，因为在过去我刚刚起步学习的时候，我甚至都不知道那些我没掌握的东西究竟叫什么名字，我连问都不知道该怎么问，懂吧？而现在，你可以随时提问，在这些未知领域里走得更快、钻得更深。甚至可以说，如果你对自己说出“我不懂这个”越诚实坦荡，你的进步速度反而会越快。我依然认为这里面有着无比光明的未来。所以，是的。这是一个极好的问题。

<details>
<summary>Original English</summary>

**[Zack]**: I I would. If I would if my focus is kind of like skilling up and making sure that I'm on a solid foundation, yeah, I would recommend that. Um and I would also say don't get discouraged because in the past when I was coming up and learning like I didn't know the names of the things that I didn't know, so I couldn't ask, you know? And now you can kind of ask and go faster and deeper on it. It's almost like if you're more honest with yourself about I don't know this, you can go faster. And I still I still think there's a super bright future for that. So, yeah. Great question. Yep.

</details>

### Q&A环节：处理庞大的 JSONL 日志

**[观众]**: 是的，你刚才提到让Claude去看你自己和它的聊天历史记录，也就是那些JSONL文件。我尝试过类似的方法，但我发现一个问题，那就是这些JSONL文件本身并不真的是为AI阅读而准备的。它们变得极度冗长，里面塞满了各种垃圾信息。您是直接把Claude指向原始的JSONL，还是你在中间有某种过渡步骤，用脚本把那些文件解析成了对AI更友好的格式？

<details>
<summary>Original English</summary>

**[观众]**: Yes, so you talked about getting Claude to look at your own chat history with all those JSONL files. I I I've tried stuff like that and like a problem I found is that like those JSONL files are not really meant for AI consumption. They get really long and there's a lot of junk in there. Do you just point Claude straight at it or do you have some kind of intermediary step where there's something that parses that into a more amenable format?

</details>

**[Zack]**: 这是个很棒的问题。我之前确实就是直接让它去读原始文件的。你的问题是，如果这些JSONL文件极其庞大、丑陋且并不适合AI摄取，你该如何处理并让Claude回去审查，并在这个基础上做聚合分析？我直接指给它读也取得过成功，但你也可以采用另一种做法：使用钩子。所以在每次编程对话结束时，你可以命令它：“保存我们讨论过的最关键信息，尤其要重点标记出我们卡壳的地方，或者我们耗费大量额外时间的地方，然后把这些精华放入一个独立的存储里。”所以它可以是放入Obsidian里的笔记，也可以是当周的纯文本Markdown文件，甚至可以直接就是一个简易的归档库，对吧？然后到了周末，你再对着这个精华版本运行你的分析。

<details>
<summary>Original English</summary>

**[Zack]**: Yeah, that's a great question. I mean I have just pointed at it before. Uh the question is how do you handle Claude going back and reviewing, doing aggregate kind of analysis on JSONL files if they're super gross and not meant for AI consumption? Um I have had success just pointing at it, but the other thing you could do is use hooks so that at the end of every coding session you could say save the key bits that we talked about and especially highlight where we struggled or where we spend a lot of extra time and put them in a separate uh data store. So, it could be Obsidian, could be a flat file of markdown for that week, could be just a simple archive, right? And then you run your your analysis at the end of the week on that.

</details>

**[观众]**: 这个保存过程是由AI决定，还是完全的硬编码确定性逻辑？

<details>
<summary>Original English</summary>

**[观众]**: >> AI or just deterministic?

</details>

**[Zack]**: 这个嘛，比如我会用Claude的钩子来做。它就类似于在每次会话结束时，或者当我说“这件事做完了”或者当我们合并PR时，作为触发器来执行。

<details>
<summary>Original English</summary>

**[Zack]**: Uh well, it It be it would be used like for example, I would do it with Claude Hooks and so it would be like at the end of each one of these sessions or when I say that this is done or we merge the PR, that would be the trigger.

</details>

**[观众]**: 其他的信息说明。您可以直接在提示词里告诉它。

<details>
<summary>Original English</summary>

**[观众]**: >> other bits to say Uh you could just tell it in the prompt basically.

</details>

**[Zack]**: 是的。你可以直接在提示词里告诉它说，我们要寻找那些具有特定迹象的东西……是的。这就是个给AI的提示词，比如：“你要特别留意并寻找那些在未来我们可以进一步优化的事情，或者是那些暴露了我们正在挣扎和反复折腾的线索。”对的。

<details>
<summary>Original English</summary>

**[Zack]**: You could say like look specifically for things that Yeah, yeah. It would be an AI prompt to say like you're specifically looking on the hunt for things that uh we could make more efficient in the future or or indications of struggle and churn. Yep.

</details>

### Q&A环节：夜间批处理与语音交互细节

**[观众]**: 您是否也会利用夜间的时间，比如说让您的智能体在夜班工作？

<details>
<summary>Original English</summary>

**[观众]**: Do you also make uh make use of night time like a like a night shift for your for your agent?

</details>

**[Zack]**: 我确实会。我也在实验开源的类似方案。我会用cron定时任务来执行，我会设置一些任务让它帮我处理内容生成之类的事。然后第二天早上我醒来，看一眼它生成的东西，可能会气得发飙甚至大骂它一顿，但最终总会合并其中的一小部分。我希望能达到一种境界：有了更完善的系统和验证机制，它就能自己在那不断地产出有用的成果。我觉得我最终会落地的方案，将是把所有的事务都变成Linear工单。缺陷和功能请求都会变成子任务。然后我给准备好的工单打上一个标签，叫做“智能体已就绪（agent ready）”，接着就让一个循环进程每15分钟跑一次，不管白天黑夜，不断地吞噬并消化我个人的事务，以及，此处可以打上马赛克——公司里的任务。

<details>
<summary>Original English</summary>

**[Zack]**: I do. I have ex- uh the question is do you make use of night shift for agent? I've been experimenting with open claw. Um so I do that with uh cron jobs and I have like some doing some content for me um and then I wake up in the morning kind of review it and freak out and scream at it and then eventually merge like a small percentage of them. Um I'd like to get to the point where with like better systems and verification that's like churning through. I think the thing I'm going to end up settling on is going to be linear tickets for everything, subtasks for bugs and for feature requests and then marking tickets with a tag says agent ready and then having a loop that's literally going every 15 minutes all day long and all night long churning through personal and uh earmuffs company work, too.

</details>

**[观众]**: 您会让您的智能体跟您用语音讲话吗？还是您直接阅读它的回复？如果它的回复极其冗长，您会怎么办？因为显然眼睛阅读比听语音要快得多。

<details>
<summary>Original English</summary>

**[观众]**: Do you let your agent speak back to you or do you read it? If it's very verbose, what do you do because obviously reading is faster than than speaking.

</details>

**[Zack]**: 很好的问题。问题是你在速度等方面，会不会让智能体用语音回敬你。其实这两者我都会用。大多数时候如果我在终端里用Claude Code工作，我是在对它口述说话，然后它把文字返回给我，我去阅读它。但我也非常多地直接在OpenAI的高级语音模式（advanced voice mode）里进行工作。那是我对ChatGPT最喜欢的功能之一。这也是我有时弃用Claude转而使用ChatGPT的唯一理由之一。我会在外面散步两小时，全程都在语音倒脑洞、来回交流、打磨一个想法。然后在快结束时跟它说：“好了，现在把这些提炼成一份可以直接复制粘贴的简洁摘要或者架构方案。”我认为虽然我可以通过语音和它讲话，但即便如此，它其实也聪明到足以产生一些——你懂的，我以前也和它有过那种质量存在争议的交谈。但在语音领域，技术演进非常迅猛。即使是昨晚，我就发现了一个开源的超级狠活儿，基本上是一个Whisper工作流。它只在本地运行，甚至不消耗API接口。我觉得这方面有无穷无尽的玩法。我把开源服务架在了Twilio上，所以在夜间我可以直接给它打电话。与其让它把长篇大论读给我听，我可以直接在电话里对它说：“这就是我明天要你去做的事情。”我确实觉得基于语音的操作极其高效。是的。

<details>
<summary>Original English</summary>

**[Zack]**: Yeah, great question. Uh the question is do you let your agent speak back to you in terms of voice um in terms of speed and everything? I actually do all of that. I I have if I'm working most of the time with Claude Code, I'm speaking to it and then it's writing back to me and I'm reading it. Um but I do a lot of work just in like OpenAI's advanced voice mode. It's one of my favorite things about that ChatGPT. It's one of the only reasons I would use ChatGPT over Claude. And I'll go for a walk for 2 hours and I'll like brain dump and talk back and forth and sharpen an idea and then say at the end of that, "Okay, now make this a succinct transcript or architecture that I can paste." Uh I think it's I can talk to but even that is quite, you know, intelligent enough to have like a I've had you know, conversations of arguable quality with it before. Um but I and there's also the voice space is moving so quickly that even last night I found one that that that it's an open source ghost pepper that's basically whisper flow. It's local only and doesn't use an API. I think there's like a tremendous amount of ability I I have open claw on Twilio. So at night I can ask for the call and as opposed to it reading to me and then I can talk to it and say this is what I want you to do tomorrow. Um yeah, I find I find general voice is super efficient. Yeah. Yep.

</details>

### Q&A环节：处理全栈“硬骨头”任务

**[观众]**: 是的先生。您用这种方式处理所有类型的工作吗？我也有类似的工作流，我发现当你处理小bug或者简单的UI修复这类事情时，它运转得特别完美，我甚至可以并行处理很多事情。但当我面临一个更为庞大厚重的功能时，你知道，比如有些任务需要打通后端数据库、前端，那种涉及到整个应用程序重构的级别，这种工作流就感觉像撞在了一堵墙上。这时候我就无法再把它并行化出去了，因为它极大消耗了我的注意力。碰到这种极其复杂的任务时，您是否还能应用这种工作方式，还是说就干脆自己亲自上手了？

<details>
<summary>Original English</summary>

**[观众]**: Yes, sir. Uh do you do every kind of work with that? So I I've had similar workflows and I found it works really nicely when you're doing like small bugs or UI fixes and stuff like that and I can, you know, do many things in parallel. But then when I have a more chunky feature, you know, something that needs to touch the back end database, front end, that changes like the whole application work or factor, it it feels like it grinds all of that to a point where then I'm not able to parallelize anymore cuz then it might focus. Are you able to work on that sort of like more chunky task yourself?

</details>

**[Zack]**: 是的，我认为这是一个极棒的问题，我觉得这也是目前所有人都在苦苦挣扎的地方。你的问题是，你知道，这种并行工作流用来对付独立的、小巧的任务极其完美，我同意这点。但你又该如何处理那种规模更大、更厚重，需要贯穿整个技术栈的任务呢？比方说，要为一个分布式云系统开发一项全新功能。面对这种场景，我的思路是：首先开启多个“工作树（work trees）”，这样智能体就能真正做到并行运转，而不会踩到彼此的脚后跟。然后启用多智能体团队，给它们配置极其明确的提示词分工。

<details>
<summary>Original English</summary>

**[Zack]**: Yeah, I think I think it's a great question. I think everyone's struggling with that. The question is you know, these flows work really really well for discrete bite-size tasks and I I agree with that. And then how do you do bigger chunkier ones that are like it's going to touch the entire stack. It's going to, you know, an entire new feature for like a distributed cloud system. Um where my mind goes for that is is get work trees first of all so that the agents can run in truly in parallel without stepping on each other's work. And then agent teams um with really clearly defined prompts.

</details>

**[Zack]**: 当涉及这种复杂的系统重构时，那些安全验证关卡、单元测试等等就变得比以前更加重要了。这进一步逼近了我们所说的持续集成（CI）——必须达到这样一种境界：我不断在测试整个应用程序，而智能体则是持续依据设计规范进行构建。在这个过程中，我不断地将我发现的不满甚至发脾气丢回给这套系统，然后它就能在我推进的同时一步步修正问题。不过，我认为这套模式肯定还会继续进化。我能够想象，随着模型的不断变强，未来必定会出现越来越完善的工具集成框架，使这种复杂的重构任务变得更加可靠。是的，这真是一个绝佳的问题。好的，非常感谢大家。

<details>
<summary>Original English</summary>

**[Zack]**: And then again, it makes the verification gates and the unit tests and um even more important. And then kind of, you know, continuous integration getting to the point where I'm constantly testing the application. They're constantly building against a spec. I'm flowing back my insults and rage and, you know, into the system and then it's like fixing it and as we go. Um I think that's going to keep evolving though and I I imagine that as models get better, there's going to be more and more complete harnesses to make that more reliable. Yeah, that's a great question. All right, thank you so much.

</details>