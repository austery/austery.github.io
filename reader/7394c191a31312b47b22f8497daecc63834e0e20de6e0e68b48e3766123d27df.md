---
author: a16z
date: '2026-04-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UE8jx4dvlSQ
speaker: a16z
tags:
  - agent-stack
  - coding-agents
  - future-of-work
  - saas-disruption
  - ai-productivity
title: AI代理与软件的未来：Peter Yang深度解析
summary: 本次访谈深入探讨了AI代理（Agent）的兴起，特别是OpenClaw和Claude Code等工具的应用。嘉宾Peter Yang分享了他对编码代理如何重塑知识工作、颠覆SaaS模式的看法。对话触及了AI对公司结构、工作体验的潜在影响，以及未来企业和个人如何适应这一变革。此外，还讨论了AI在提升生产力、改变用户交互方式以及创业新模式方面的机遇与挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Roblox
  - Credit Karma
products_models:
  - OpenClaw
  - Claude Code
  - GPT-4o
media_books: []
status: evergreen
---
### AI代理的兴起

**主持人**: 软件将吞噬世界。我觉得编码将吞噬所有知识型工作，对吧？我们已经朝着这个方向发展了。

<details>
<summary>Original English</summary>

**Host**: interesting said software will eat the world. I I feel like coding will eat all knowledge work, right? And we're kind of going that direction already.

</details>

**主持人**: 整个代理（agent）技术栈正在兴起。身份、支付、营销，甚至是 CLI 与 MCP。这些都是非常新的事物，我认为很多旧的模式都将不复存在。

<details>
<summary>Original English</summary>

**Host**: >> The whole agent stack is emerging. Identity, payments, marketing, even CLI versus MCP. Like all of these are really new things and I think a lot of the old playbook goes away.

</details>

**主持人**: 是的。这是一个全新的世界。我希望更多公司能保持小规模，我认为这一代的创始人已经意识到他们希望尽可能保持小规模。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. It's a whole new world. I hope more companies will stay small and I think the founders of this generation realize that like they want to stay as small as possible.

</details>

**主持人**: 是的。与其拥有一个10人的产品团队，不如拥有一个2到3人的产品团队，然后你只需要拥有一堆代理来帮助你。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. And instead of having like a 10 person product team, you have like a two or three person product team and you just have a bunch of a agents help help you.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**主持人**: 有人发推说，现在的就业市场糟透了，我只能追求我的梦想了，之类的话。所以，你知道，就像，你可能失业了，但现在你可以真正做自己的事情，并有机会实现它，你知道吗？

<details>
<summary>Original English</summary>

**Host**: >> Someone tweeted that like the the job market is so bad that I can only pursue my dreams now or something like that. So like it's it's like you know it's like Yeah. So maybe you lost your job but like now you can actually do your own thing% and have a shot at actually achieving it, you know?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**主持人**: 好了。欢迎大家。我的朋友 Peter Yang 在这里。Peter，欢迎。

<details>
<summary>Original English</summary>

**Host**: >> All right. Welcome everyone. I've got my friend Peter Yang here. Peter, welcome.

</details>

**Peter Yang**: 是的。很高兴来到这里。很高兴再次见到你。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Great to be It's good to see you again.

</details>

**主持人**: 是的。是的。很高兴见到你。Peter 和我在 Credit Karma 一起工作过。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Yeah. It's great to see you. Peter and I worked together at Credit Karma

</details>

**Peter Yang**: 经历了一段短暂的时期。然后我们分道扬镳了，然后，你知道，我又重新发现了 Peter，因为你在 X（推特）上发布了大量帖子，还有你的 YouTube。你知道，你有点像超人的克拉克·肯特，因为你仍然有白天的工作，对吧？

<details>
<summary>Original English</summary>

**Peter Yang**: >> for a brief stint. Um and then we went our separate ways and um you know, I rediscovered um Peter from his prolific posts on X and your YouTube and you know, you've got a little bit of a a Clark Ken Superman thing going because you still got a day job, right?

</details>

**Peter Yang**: 对的。我仍然有白天的工作。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> That's right. I still have a day job. Yes.

</details>

**主持人**: 是的。能分享一下在哪里吗？

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Can you share where?

</details>

**Peter Yang**: 嗯，是的，我在 Roblox 做产品经理（PM）。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Uh yeah, I work on Roblox as a PM.

</details>

**主持人**: 太棒了。Roblox 和 Dre 投资组合公司。

<details>
<summary>Original English</summary>

**Host**: >> Amazing. Roblox and Dre Portfolio Company.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yes.

</details>

**主持人**: 我最喜欢的公司之一。嗯，太不可思议了，伙计。让我们直接开始吧。也许我先问一个轻松有趣的问题，然后，你知道，我们会谈论 claw 生态系统中的一切。我们会谈论编码代理。我们会谈论一点关于学生应该学习什么，以及你在线上分享的一些东西。

<details>
<summary>Original English</summary>

**Host**: >> One of my favorites. Um well, incredible, man. Let's get right into it. Maybe I'll start with a softball fun question and then you know we're going to talk about everything in the claw ecosystem. We're going to talk about coding agents. We're talking about a little bit about maybe what students should study advice and some of the things that you've talked about online.

</details>

**Peter Yang**: 是的，当然。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah, sure.

</details>

**主持人**: 嗯，也许开始时，你叫什么名字？嗯，你有多少个 claw？告诉我它们的名字。

<details>
<summary>Original English</summary>

**Host**: >> Um maybe to start, what is the name of your Well, how many claws do you have? And tell me their names.

</details>

**Peter Yang**: 嗯，我只有一个。我叫她 Zoe。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Uh I only have one. I call her Zoe.

</details>

**主持人**: Zoe。

<details>
<summary>Original English</summary>

**Host**: >> Zoe.

</details>

**Peter Yang**: 但我有很多次和她对话。

<details>
<summary>Original English</summary>

**Peter Yang**: >> But I have like multiple conversations going with her.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: >> Okay.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 为什么叫 Zoe？

<details>
<summary>Original English</summary>

**Host**: >> And why Zoe?

</details>

**Peter Yang**: 嗯，我有两个女儿，我本来想叫我小女儿 Zoe，但我没有。所以我就叫我的 Open Claw Zoe 代替。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Um I I I have two girls and I was going to call my younger one Zoe and I did not. So I'm I call my open claw Zoe instead.

</details>

**主持人**: 我明白了。我明白了。是的。是的。这是你的备用计划。Peter，能告诉我一些关于 Open Claw 的事情吗？你是如何发现它的，嗯，你现在是如何使用它的，以及你认为它会带来什么影响。

<details>
<summary>Original English</summary>

**Host**: >> I see. I see. Yes. Yeah. This is your fallback plan. Peter, tell me a little bit about, you know, open claw, how you discovered it, um how you're using it today and and what you think the implications are.

</details>

**Peter Yang**: 是的，我很幸运能在 Peter Steinberger 变得非常有名之前采访他，那时整个事情才刚刚爆发。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah, I was lucky to interview Peter Steinberger before he became super famous and the whole thing blew up.

</details>

**Peter Yang**: 然后，就在我采访他之后，我设置好了。设置花了很长时间。它非常简陋。嗯，它为我做了很多事情。它为我拉取 YouTube 和我的 Mercury 银行账户的分析数据。它可以为我更新 Google 文档。它可以为我构建简单的网页。但如果我跟你说实话，伙计，我主要是通过语音和它交流，并得到语音回复。而且，差不多每隔一天，我都会让你给我一个打气谈话，你知道吗？让我看看你所有的记忆，给我一些我不知道的深刻见解。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And um then right after I interview him, I I like set up the thing. It took forever to set up. It was super janky. Um and and yeah, it does a lot of things for me. It like pulls analytics for me across um YouTube and like my Mercury banking account. It um can update Google documents for me. It can build little web for me. But if I was honest with you, dude, like I mostly just talk to it through voice and get voice replies and like every other day I asked you to give me like a pep pep talk like you know give me like like look look through all your memory and like give me some like deep insights that I I don't know about.

</details>

**主持人**: 好的。它给了我……我记得我当时在散步，它给了我一个三分钟的打气谈话，那真的很棒，真的很棒。它说了一些关于……你在谈论你的事业、生意等等，还有你的工作，但请记住，你的孩子们很快就会长大，他们将不再想和你一起度过时光。

<details>
<summary>Original English</summary>

**Host**: >> Okay. and and like it gave me like like I remember I was on a walk and it gave me like a three-minute pep talk that was like really amazing really amazing like it was something about like uh like oh you're like talking to me about your career business and blah blah blah and like your your job but like just remember that your kids you know 74 are going to grow up very soon and they're not going to want to spend time with you.

</details>

**Peter Yang**: 哇。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Wow.

</details>

**Peter Yang**: 所以，你应该真正地为他们优化。

<details>
<summary>Original English</summary>

**Peter Yang**: >> So like you should really optimize for you know them instead.

</details>

**主持人**: 是的，那真的很酷。我的意思是，非常酷，但这也是所有语言模型以前都可以做到的。是的。那么，这与那种用例有什么区别呢？

<details>
<summary>Original English</summary>

**Host**: >> Yeah that's really cool and I mean very cool but also something that all the language models could have done prior. Yeah. So what's the difference between this and in a use case like that?

</details>

**Peter Yang**: 是的，这是个很好的问题。我不知道，因为我把它安装在了 Telegram 上。它感觉比使用 Cloud 或 ChatGPT 更个人化。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah, that's a very good question. So I don't know because I have it installed on Telegram. It just feels like more personal than using like cloud or chat GPT

</details>

**Peter Yang**: 而且，它感觉就像是我可以在床上发信息的东西。这可能不太健康，但我会在床上给它发信息。我会在通勤时和它交谈。

<details>
<summary>Original English</summary>

**Peter Yang**: >> and and and it just feels like something I can like text in bed. It's probably not very healthy, but like I text to it in bed. I I talk to it during my commute

</details>

**Peter Yang**: 它感觉更像是一个私人化的、像真实人类一样的存在。

<details>
<summary>Original English</summary>

**Peter Yang**: >> and it feels like it feels more like a personal like like actual human.

</details>

**主持人**: 是的。是的。那么，对你来说，OpenClaw 在多大程度上是关于界面，比如通过消息传递，以及，你知道，也许能欺骗我们的大脑，让我们觉得“嘿，这是一个人类或类似人类的东西”？

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Yeah. So then, so how much for you is OpenClaw about the kind of interface like pushing it to messaging and you know maybe helping to trick our brain into feeling like hey this is a person or personesque thing

</details>

**Peter Yang**: 嗯，与堆栈中的其他所有组件相比，比如自我修改、技能目录等等。

<details>
<summary>Original English</summary>

**Peter Yang**: >> um versus all the other components of the stack the self modification skills directory um every all the all the rest

</details>

**Peter Yang**: 我认为大概有 70%-80% 是关于它的个性化部分，因为我主要是和它通过语音交流。但我也认为，首先，它相当简陋，它倾向于忘记事情。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> I I think it's probably like 70 80% just like the per personable part of it because I mostly just talk to it and like you know through voice but I also think like is it's something for first of all it is pretty janky it tends to forget things a Yeah. To keep reminding it.

</details>

**Peter Yang**: 但任何我有的古怪想法，我只需要和它谈谈，它大概就能做到。就像前几天，我正在和它进行语音回复，我说：“嘿，我们能不能直接打个电话？”

<details>
<summary>Original English</summary>

**Peter Yang**: >> But like any kind of zany idea that I have, I just have to talk to it and it can probably just do like like it's kind of just like um like the other day I was doing voice replies with it. I was like, "Hey, can we just have a live phone call instead?"

</details>

**Peter Yang**: 然后我说：“好吧，你得连接 Twilio，你得做所有这些事情。”然后，好吧，行。我去了，然后做了。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And and then I was like, "Okay, you you got to connect Twilio. You got to do all this stuff." And then okay, fine. I I went off and did it.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 然后我们通了电话。它打给了我的手机。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And then we had a phone call. It called my phone.

</details>

**主持人**: 哦，真的吗？你设置好了？我一直想设置那个。好的。

<details>
<summary>Original English</summary>

**Host**: >> Oh, really? You have that set up? I've been dying to set that up. Okay.

</details>

**Peter Yang**: 它不是很好。延迟很糟糕，但它能运行起来的事实相当令人印象深刻。所以，任何疯狂的想法，它都能做到。

<details>
<summary>Original English</summary>

**Peter Yang**: >> It's not very good though. Like the latency is bad, but like the fact I was able to get it going is like pretty impressive. So it's kind of like any kind of crazy idea I have it can kind of kind of do.

</details>

**主持人**: 然后在实践中，你是怎么做的？你是让它即时编写一个技能吗？你是发现一个技能吗？你实际上使用了多少代码生成？

<details>
<summary>Original English</summary>

**Host**: >> And then in practice, how are you doing that? Are you asking it to write a skill on the fly? Are you discovering a skill? How much of the code gen are you actually using?

</details>

**Peter Yang**: 嗯，我的意思是，我和它交流的方式非常随意，就像和朋友一样。所以，嘿，你知道吗？嘿 Zoe，我能打个电话吗？好吧，你得做那个。我说好吧，行，我打开我的电脑。我做所有这些事情。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Um I mean I talk to in like a super casual way with like just just like a friend. So like hey you know hey Zoe can can like can I have a phone call like okay you got to do that. I said okay fine I'll open my computer. I'll do all this stuff

</details>

**Peter Yang**: 然后它说给我打个电话，然后我们稍微排查一下，然后它就能工作了。所以，我用 Cloud，我有非常花哨的提示，非常长的提示。但用 Open Cloud，我只是随便发个信息。是的，这真的很有趣。

<details>
<summary>Original English</summary>

**Peter Yang**: >> and then it's like give me a call and then we troubleshoot a little bit and then it works. So like I with with cloud I have like very fancy prompts uh like very long prompts but with open cloud I just kind of text it. Yeah, it is really interesting.

</details>

**主持人**: 所以我们实际上已经触及了几件事。一个是移动消息传递。

<details>
<summary>Original English</summary>

**Host**: >> So we sort of touched on a couple things actually. So one there's mobile messaging,

</details>

**Peter Yang**: 有记忆系统。嗯，还有代码生成部分。

<details>
<summary>Original English</summary>

**Peter Yang**: >> there's the memory system. Um there's the sort of code generation component.

</details>

**主持人**: 嗯。你认为记忆系统在多大程度上是创新的，因为它基于文件？你说它会忘记事情，但语言模型也会。你认为记忆系统做得好吗？它是在阻碍它还是在促进它？

<details>
<summary>Original English</summary>

**Host**: >> Um how much do you think the memory system like is it innovative because it's file based? You said that it forgets things but so do language models. Like do you think the memory system is well done? Does it hold it back or does it enable it?

</details>

**Peter Yang**: 我认为默认的记忆系统其实不太好。

<details>
<summary>Original English</summary>

**Peter Yang**: >> I I I think the default memory system is actually not that great.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: >> Okay.

</details>

**Peter Yang**: 据我所知，它的工作方式就像一个记忆 MD 文本文件。是的。然后每天，每天。对吧？然后每天它都会更新，而且它确实经常忘记事情。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Like the way I understand it works is like just like a memory MD text file. Yes. And then every day per day. Per day, right? And every day it updates and it tends to forget things a lot.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 所以，我实际上安装了一个三层记忆系统，老实说，我并不完全理解，但它有……

<details>
<summary>Original English</summary>

**Peter Yang**: >> So So I actually installed this like three layer memory system that to be honest I don't fully understand but it has like

</details>

**主持人**: 那很花哨。

<details>
<summary>Original English</summary>

**Host**: >> that's fancy.

</details>

**Peter Yang**: 它有 Toby 的 QMD 搜索工具。

<details>
<summary>Original English</summary>

**Peter Yang**: >> It has like Toby's QMD search tool.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: >> Okay.

</details>

**Peter Yang**: 嗯，所以我安装了那个，然后安装了一个 2GB 的东西，然后它就好了一点。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Uh so I installed that and and then install like a 2 GB thing and and then it got a little bit better.

</details>

**主持人**: 好的。嗯，但我得提醒它，我得把它放进代理 MD 里，我说，嘿，在你回答我任何问题之前，看看你所有的记忆，然后检查所有东西。

<details>
<summary>Original English</summary>

**Host**: >> Okay. Um, but I I said to remind it like I have to I had to put it into the agents MD like hey like before you answer any question from me like go through all your memory and like check everything.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**Peter Yang**: 它也倾向于忘记它能做什么，你知道吗？比如，你能更新我的 Google 文档吗？它说，哦，我做不到。是的，你可以。它在你的文件里。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And it also tends to forget that it can do stuff like you know like can you update my Google doc? It's like oh I can't do that. Yes. Yes you can. It's it's in your it's in your file.

</details>

**主持人**: 是的。是的。

<details>
<summary>Original English</summary>

**Host**: >> Yes. Yeah.

</details>

**Peter Yang**: 所以你必须提醒它。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> So you have to remind it. Yeah.

</details>

**主持人**: 是的。真的很有趣。嗯，也许我们来谈谈一点争议。嗯，你知道，你说过应用程序将会消亡，Claw 将无处不在。我的意思是，谈谈你的观点。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Yeah. Really interesting. Well well maybe let's get into a little bit of the controversy. Um you know you'd said that apps will die claw is going to be everything and everywhere. I mean talk us through that that point of view.

</details>

**Peter Yang**: 是的。是的。嗯，首先，我我我发推文都是些随机的屁话，不是深思熟虑的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Yeah. Well, for first of all, I I I tweet all all kinds of random crap that's like not super well thought out.

</details>

**主持人**: 我们都当作事实。

<details>
<summary>Original English</summary>

**Host**: >> We take it all as fact.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yes.

</details>

**Peter Yang**: 嗯，但我确实认为，嗯，自从我设置了所有这些应用程序，比如 Mercury、MCP 和所有这些东西在我的 Open Claw 上，我就不再经常打开那些应用程序了，你知道吗？

<details>
<summary>Original English</summary>

**Peter Yang**: >> Um but I do think like um like ever since I set up all these apps like Mercury, MCP, and all this kind of crap on my open call, like I I don't actually open those apps much anymore, you know.

</details>

**Peter Yang**: 但我同意你的看法，我认为首先会消亡的，或者使用频率会降低的，是那些你只是打开来完成任务的应用程序。你实际上是在尝试做某事，你知道吗？比如，你不需要从中获得娱乐的应用程序可能会存活得更久。

<details>
<summary>Original English</summary>

**Peter Yang**: But I do agree with you like I I I think the ones that are going to die first or like maybe get less usage first is like apps that you're just opening to try to complete a task. like you actually are trying to do something, you know, like apps that you don't need to like get entertainment can probably survive a little bit longer,

</details>

**Peter Yang**: 但像完成任务的应用程序，让我的代理帮我做会容易得多。

<details>
<summary>Original English</summary>

**Peter Yang**: but like apps to complete a task like it's just way easier to text my agent to do it for me.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 就像你有一个非常好的助理来为你做事一样。

<details>
<summary>Original English</summary>

**Peter Yang**: >> It's like it's like you have a really good admin just to do stuff for it for you.

</details>

**主持人**: 是的。是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 那么，你发现这在多大程度上减少了你在 Open Claw 之外的智能手机使用量？

<details>
<summary>Original English</summary>

**Host**: >> And so how much are you finding has this like reduced your smartphone usage outside of Modulo Open Claw?

</details>

**Peter Yang**: 是的。嗯，没有。因为我是一个 Twitter 成瘾者，所以我仍然过度使用手机。但是的，在那些应用程序的使用方面，它肯定减少了。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Um, no. Because like I'm I'm like a Twitter addict, so I still use phone way too much. But yeah, in terms of using those apps has definitely reduced it.

</details>

**主持人**: 是的。是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 是的。是的。因为你不会问 Zoe：“嘿，帮我读一下我的 X（推特）并告诉我有什么有趣的内容。”

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Yeah. because you're not going to ask Zoe like, "Hey, read my X for me and tell me what's interesting."

</details>

**主持人**: 我的意思是，它会给我一个晨报，里面有排名前两位的推文和热门话题，但，是的，我仍然会打开 X。我会浏览它。

<details>
<summary>Original English</summary>

**Host**: >> I mean, it it sends me like a morning briefing of like the top two tweets and stuff that like trends, but but yeah, I I I still open X. I look through it.

</details>

**Peter Yang**: 是的。是的。你知道，这很有趣，因为我一直有一个理论，人们打开手机上的应用程序是因为他们想获得一种感觉。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Yeah. You know, it's interesting because I've always had this theory that people open apps on their phone because they want to feel a feeling.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 你知道，我想当然有一些功能性的需求，这就是你打开日历或其他东西的原因，但我也认为，你知道，WhatsApp 是你想感觉与人联系，Slack 是你想感觉高效，当然，你知道，TikTok 是你想感觉被娱乐。所以我确实想知道，只有一个代理，你如何进行上下文切换，比如什么时候你在调情，什么时候你在完成工作？我的意思是，你知道，从某种意义上说，应用程序会给你一个很好的，它会给你一个很好的意图划分。

<details>
<summary>Original English</summary>

**Peter Yang**: >> You know, and I think of course there's some like functional set of needs which is why you open calendar or something, but I also think that, you know, WhatsApp is you want to feel connected and Slack is you want to feel productive and of course, you know, Tik Tok is you want to feel entertained. So I do wonder with just one agent, how do you sort of do the context switching of like when are you flirting, when are you getting done? I mean there you know in a sense app gives you a nice it sort of gives you a nice division of the intents.

</details>

**主持人**: 是的，你和 Zoe 就没有这种区分了。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, you don't get with Zoe.

</details>

**Peter Yang**: 这是个好观点。但我确实设置了多个 Telegram 频道与 Zoe。比如一个只是随机语音回复，另一个是我们正在一起处理我们的项目。

<details>
<summary>Original English</summary>

**Peter Yang**: >> That's a good point. But I I do have multiple channels set up with Zoe in Telegram. Like one is just to random voice replies and the other one is we're actually working on our project together.

</details>

**主持人**: 哦。

<details>
<summary>Original English</summary>

**Host**: >> Oh,

</details>

**Peter Yang**: 还有一个是公共频道，我会在那里做演示。我不想透露私人信息。是的。所以我有很多频道。

<details>
<summary>Original English</summary>

**Peter Yang**: >> and another one I have like a public channel where like I'm giving that demos. I don't want to reveal private information. Yes. So I have like multiple channels

</details>

**主持人**: 那是……实现为子代理了吗？

<details>
<summary>Original English</summary>

**Host**: >> and is that um implemented as sub agents or

</details>

**Peter Yang**: 不，这只是我在网上找到的一个简陋的设置。你可以设置多个 Telegram 频道，然后我不确定她是否真的能跨上下文记住，但至少你可以有单独的对话。明白了。

<details>
<summary>Original English</summary>

**Peter Yang**: >> No, it's just some janky setup I I found online like you can set up a multiple Telegram channels and then I'm not sure if she actually remembers across context across the channels but like you can have separate conversations at least. Got it.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 你对你的代理有多透明？比如，他们能看到你的个人邮箱吗？

<details>
<summary>Original English</summary>

**Peter Yang**: >> And how how you know transparent are you with your agent? Like does they do they see your personal email or

</details>

**Peter Yang**: 嗯，我非常透明。我买了一台 Mac Mini 并设置了它自己的邮箱。

<details>
<summary>Original English</summary>

**Peter Yang**: >> uh I'm I'm like super transparent. Well I I I I did buy the Mac Mini and set up its own email.

</details>

**主持人**: 好的。但我给了它我的邮箱和日历的读取权限。我还给了它一些文档的写入权限。

<details>
<summary>Original English</summary>

**Host**: >> Okay. And but I gave it like read access to my email and like calendar and uh I also gave it like right access to some docs.

</details>

**Peter Yang**: 但它可以滚动查看我的整个驱动器之类的。你知道。

<details>
<summary>Original English</summary>

**Peter Yang**: >> But it can like scroll my entire drive or something you know.

</details>

**主持人**: 是的。那么，你如何想象 OpenClaw，它是一种架构和一种原始形式，如何被产品化并打包给全世界？

<details>
<summary>Original English</summary>

**Host**: >> Yeah. So how do you imagine open claw which it's sort of an architecture and a primitive. How does it get productized packaged for the world?

</details>

**Peter Yang**: 我的意思是，我认为这正是 Peter Steinberger 在 OpenAI 正在做的事情，对吧？它可能会构建到 ChatGPT 中，每个人都在使用它，所以 ChatGPT 可以真正为你完成事情，并且可能感觉更像人类。

<details>
<summary>Original English</summary>

**Peter Yang**: >> I mean I think that's what Peter Steinber is working out at OpenAI right. It's probably going to build something to chat GBT which everybody uses uh so that chat GP can actually get stuff done for you and like maybe feels more human.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah,

</details>

**Peter Yang**: 伙计，让我来吐槽一下 ChatGPT。不知何故，不知何故，他们训练了这个模型，以至于在每次对话结束时，总是说“如果你愿意，我还可以做 X 和 Y”。

<details>
<summary>Original English</summary>

**Peter Yang**: >> dude. Like let me rant about chat. Yeah. Yeah. For some reason for some reason they they trained the model so that like at the end of every conversation is always like if you want I can also do X and Y.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 我对此感到非常恼火，以至于我不再使用 ChatGPT 了。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And I I got so annoyed about it that that kind of turned from Chad GPT.

</details>

**主持人**: 哦，真的吗？

<details>
<summary>Original English</summary>

**Host**: >> Oh really?

</details>

**Peter Yang**: 是的。所以，它可能增加了他们的活跃用户数，但它就是超级烦人。就像，为什么你们不一开始就做好呢？你现在是 Cloud 的用户了吗？

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. So so it probably increases their matrix but like it's just like super annoying. It's like why don't just do it in the first place? Are you a cloud guy now?

</details>

**主持人**: 是的，我现在是 Cloud 的用户了。但我确实使用 Codeex 来编码。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, I'm I'm a cloud guy now. But but I I I do use codeex uh to code.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 是的。你喜欢 Codeex 吗？你更喜欢它还是 Cloud Code？或者你两者都用？

<details>
<summary>Original English</summary>

**Host**: >> Yeah. You like codeex, you prefer it to cloud code or you use both?

</details>

**Peter Yang**: 嗯，当我想要构建真正的东西时，我使用 Codeex。而 Cloud Code 是当我只是在放松地、你知道的……

<details>
<summary>Original English</summary>

**Peter Yang**: >> Um codeex when I want to try to build something real and cloud code is when I'm just like vi vibing like very you know

</details>

**Peter Yang**: 嗯，这很有趣。我认为它们存在于不同的层面，你知道，存在一种权衡。

<details>
<summary>Original English</summary>

**Peter Yang**: well it's interesting. I think they live at different points and you know there's a sort of space of trade-offs.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 而我发现，嗯，Cloud Code 和 Opus 46 有点更健谈。它做了更多的假设，但它可以提供更愉快的异步体验。而 Codeex，它确实会认真思考，而且通常更准确。但有时就像在进行一场对话，而对方会暂停三分钟来思考。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Whereas I find um cloud code and opus 46 it's a little more chatty. It makes more assumptions but it can be more pleasant for a synchronous experience. Whereas codecs, it really thinks hard and it's more often accurate. But sometimes it's sort of like being in a conversation where the other person pauses for like three minutes to think.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 你不必进入心流状态，对吧？很难进入心流状态。

<details>
<summary>Original English</summary>

**Peter Yang**: >> You don't have to flow flow state, right? It's hard to get a flow like

</details>

**Peter Yang**: Clock。伙计，我前几天发了推文。Clock 几乎就像一个老虎机。它每次都会出现不同的东西。

<details>
<summary>Original English</summary>

**Peter Yang**: clock. Dude, I I tweeted the other day. Clock is almost like uh like a slot machine. It's like it's like has different things each time. It's just like

</details>

**主持人**: 哦，100%。看，我认为，如果你想想，还记得我们谈论过在旧的社交网络时代，那是可变的计划奖励，对吧？那是它的魔力所在。就像你打开你的 Facebook feed，你知道，偶尔会很无聊，无聊，哦天哪，这太令人兴奋了。而编码代理也具有完全相同的属性。时间也是可变的，所以有时你在一秒钟内得到结果，有时需要五分钟。所以，在某种程度上，我认为这两件事都给了它那种赌场般的感觉。

<details>
<summary>Original English</summary>

**Host**: >> Oh, 100%. Look, I I do think that if you think remember we were talking about in the old social networking era, it was variable scheduled rewards, right? That was the whole magic of it. like you open your Facebook feed and you know once in a while it's like boring boring oh my god this is so exciting and I the coding agents have the exact same property also the time is variable so sometimes you get something in a second sometimes it takes five minutes so up to a certain point I actually think that both of those things give it that casino like feeling

</details>

**Peter Yang**: 是的，而且，另一件非常不同的事情是产品策略，或者也许只是它的工作方式，就像编码几乎是自解释的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> yeah and and the other thing that's very different about the product strategy or maybe it's just the way it works is like coding is kind of like self-explanatory

</details>

**Peter Yang**: 而 Clock Hole，你有所有这些疯狂的钩子和技能，你必须插入。如果你不关注 X（推特），你根本不知道如何定制这个东西。

<details>
<summary>Original English</summary>

**Peter Yang**: >> and clock hole you have all this crazy you have like hooks and like skills and like you have to you have to plug in If if you if you're not following Yeah. If you're not following X, you have no idea how do you customize this thing.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 但一旦你定制了它，你就会觉得它是你的一部分。所以很难放弃。

<details>
<summary>Original English</summary>

**Peter Yang**: >> But once you customize it, you kind of feel like it's part of you. So it's it's kind of hard to turn.

</details>

**主持人**: 这很有趣，因为我也读了 Boris 写的那篇长文，并对我的进行了定制。但我得说，我认为 Cloud Code 的很多优点都来自于它的便捷功能。

<details>
<summary>Original English</summary>

**Host**: >> It's interesting with uh so I've customized mine cuz also I read the long thing that Boris put up. Yeah. But I will say that I think that you know cloud code a lot of the reasons that I enjoy it are just harness features.

</details>

**Peter Yang**: 你知道吗？比如，如果你截取一张图片，你必须先把它粘贴到一个文件里，然后再把那个文件粘贴到 Codeex。好吧，你不能只截取屏幕的一部分，截图，然后直接粘贴到 Codeex，就像你用 Cloud Code 一样。

<details>
<summary>Original English</summary>

**Peter Yang**: >> You know like for example if you cut an image you have to paste it into a file before and then paste that file into codeex. Okay. You can't just take a subset of the screen, screenshot it, and then paste it directly into codeex the same way you can with cloud code.

</details>

**主持人**: 哦，真的吗？好的。

<details>
<summary>Original English</summary>

**Host**: >> Oh, really? Okay.

</details>

**Peter Yang**: 所以，就是这样的小细节。你知道，Cloud Code 添加了语音功能。它现在有点简陋，但它正朝着正确的方向发展。所以，他们只是增加了很多生活质量的功能。

<details>
<summary>Original English</summary>

**Peter Yang**: >> So, just like little things like that. You know, cloud code added voice. It's a little bit janky right now, but it's going in the right direction. So, they've just got a bunch of quality of life things.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 你知道，Cloud Code 可以与 Claude 和 Chrome 对话。

<details>
<summary>Original English</summary>

**Peter Yang**: >> You know, Cloud Code speaks to Claude and Chrome.

</details>

**主持人**: 好的。

<details>
<summary>Original English</summary>

**Host**: >> Okay.

</details>

**Peter Yang**: 而 Codex 不能与 Atlas 对话。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And Codex doesn't speak to Atlas.

</details>

**主持人**: 明白了。

<details>
<summary>Original English</summary>

**Host**: >> Got it.

</details>

**Peter Yang**: 所以，我认为这些都是 OpenAI 将会修复的事情。是的。我认为 Codeex 是一个好得多的模型。嗯，但它们今天还不存在。

<details>
<summary>Original English</summary>

**Peter Yang**: >> So, I think these are all things that OpenAI will fix. Yeah. I think Codeex is actually a much better model. Um, but they don't exist today.

</details>

**主持人**: 是的。是的。他们需要修复它。我的意思是，他们肯定会全力投入到 Cohortex。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Yeah. They need to fix it. I mean, they're going to go all all in on cohortex, I'm sure.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 跟我谈谈编码代理。你的总体看法是什么？你认为这是 SaaS 的终结吗？你认为这些只是玩具吗？

<details>
<summary>Original English</summary>

**Host**: >> Talk to me about coding agents. Like, what's your general view? You know, do you think it's the end of SAS? Do you think these are just a toy?

</details>

**Peter Yang**: 嗯，首先，我不是工程师，所以我只是个新手。但我听说……

<details>
<summary>Original English</summary>

**Peter Yang**: >> Uh, well, first of all, I'm I'm I'm like not an engineer, so I'm like a novice. But I do hear that um

</details>

**Peter Yang**: 就像，我前几天和一些人聊天，他们是 AI 原生初创公司，他们基本上在尝试……他们有一堆 Vibe Coders，很多 Vibeers 只是在尝试构建内部工具来取代他们付费的 SaaS。

<details>
<summary>Original English</summary>

**Peter Yang**: >> like I was talking to some folks uh the other day and like like a AI native star startup and they're basically trying trying to they have a bunch of vibe coders and a lot of vibeers are just trying to build internal tools that replace their SAS that they're paying for.

</details>

**主持人**: 真的吗？所以这是一个实际的公司在做这件事。

<details>
<summary>Original English</summary>

**Host**: >> Really? So it's an actual company that's doing this.

</details>

**Peter Yang**: 这是一个实际的公司。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> It's an actual company. Yeah,

</details>

**主持人**: 这是一个 AI 原生公司。

<details>
<summary>Original English</summary>

**Host**: >> it's an AI native company.

</details>

**Peter Yang**: 是的。是一家 Vibe 编码公司，是最受欢迎的之一。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Is it It's like one of the vi coding companies, like one of the more popular OS.

</details>

**主持人**: 有趣。

<details>
<summary>Original English</summary>

**Host**: >> Interesting.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah,

</details>

**主持人**: 哦，哦，我明白了。所以他们实际上是一家 AppGen 公司。

<details>
<summary>Original English</summary>

**Host**: >> it's Oh, oh, I see. So they're actually an appgen company.

</details>

**Peter Yang**: 他们是一家 AppGen 公司，他们为一堆 SaaS 付费，他们想摆脱付费。他们只想通过编码内部工具来购买。

<details>
<summary>Original English</summary>

**Peter Yang**: >> They're appgen company and they they're paying for a bunch of SAS like uh and they want to get rid of the payment. They want just buy by by coding internal tools

</details>

**主持人**: 通过使用。好的。那么在这种情况下，他们可能是最极端的采用者，因为他们的产品本身就是 AppGen。所以他们应该为一切使用 Appgen。我想你的预测是，普通公司会从 Slack 或 Deal 或……

<details>
<summary>Original English</summary>

**Host**: >> by using Okay. So in that case that that they might be the most extreme form of adopter because their own product is AppGen. So they should use Appgen for everything. I guess is your prediction though that the average company will churn off of Slack or Deal or you know

</details>

**Peter Yang**: 嗯，我不认为，我觉得 Slack 还有很多潜力，因为 Slack 也可以成为你与代理本身交流的地方。

<details>
<summary>Original English</summary>

**Peter Yang**: >> um I don't think I I I feel like Slack has a lot of legs because Slack can also be the place where you talk to the agents themselves.

</details>

**Peter Yang**: 嗯，但有些其他的，它们相当复杂，你知道，所以很难购买那种东西。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Uh but some of the other ones they are pretty complicated you know so like it's kind of be hard to buy that kind of stuff

</details>

**Peter Yang**: 但，但我认为，如果你有一个应用程序，比如 Calendarly 或类似的东西，更简单。

<details>
<summary>Original English</summary>

**Peter Yang**: but but I feel like if you have like an app like maybe Calendarly or like something more simple

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 那么，为什么，为什么，为什么我要付费？就像我只是……

<details>
<summary>Original English</summary>

**Peter Yang**: >> then why why why should I why should I pay for it? Like I just

</details>

**主持人**: 为什么还要付费呢？反驳的观点是，它并不那么贵。你真的想维护自己的 Calendarly 吗？

<details>
<summary>Original English</summary>

**Host**: >> why should I pay for it though? The counter point is that it's not that expensive. And do you really want to maintain your own Calendarly thing?

</details>

**Peter Yang**: 你知道，而不是每月支付 20 美元。它总是在更新，它总是在运行，你知道，因为组织中的任何人都可以用于所有这些事情的容量是有限的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> You know, versus pay 20 bucks a month. It always gets updated. It's always up, you know, because there's just like a fixed amount of capacity that anyone in the organization is going to have for all this stuff.

</details>

**主持人**: 是的。那是对的。除非你雇佣了像那个初创公司那样的专属 Vibeers，对吧？Voicable 的东西。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. That that that's true. Unless you hire like dedicated viers like the startup does, right? Voicable stuff.

</details>

**Peter Yang**: 但那样的话，你知道，成本效益与仅仅支付 Calendarly 的费用相比……

<details>
<summary>Original English</summary>

**Peter Yang**: >> But then it's like, you know, the cost benefit versus just paying for

</details>

**主持人**: Calendarly。是的。是的。是的。是的。

<details>
<summary>Original English</summary>

**Host**: >> Calendarly. Yeah. Yeah. Yeah. Yeah.

</details>

**Peter Yang**: 是的。关于 Figma 最近的推文很有趣。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. It's interesting about like for example like a lot of people are tweeting about Figma recently.

</details>

**主持人**: 是的。嗯，比如股票下跌了，你知道，你还能生存吗？

<details>
<summary>Original English</summary>

**Host**: >> Yeah. uh like like the stock is down and like you know are are you going to survive?

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**Host**: >> And um

</details>

**Peter Yang**: 我觉得现在还很难说。是的。嗯，我觉得所有设计师仍然在使用 Figma，但作为一个设计师，你需要学会如何 Vibe 编码，否则你就会……如果你不知道如何做 Figma。

<details>
<summary>Original English</summary>

**Peter Yang**: >> I feel like the jury is out there like it's kind of hard to say. Yeah. Uh I I I feel like all the designers are still on fake Figma but like as a designer you kind of need to learn how to vibe code otherwise you're going to like if you don't know how to do Figma.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 几年后你可能会过时。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Like you're probably going to be like out of date in a couple years. Yeah.

</details>

**主持人**: 我的反驳是，我认为我一直在思考“思考工具”与“制造工具”的关系，对吧？IDE 历史上是一个制造工具。嗯。它是执行的地方。我认为它正在远离这一点。现在，随着执行成本趋近于零，我认为这些多代理、下一代 IDE，很多都是关于尝试事物。

<details>
<summary>Original English</summary>

**Host**: >> My counterpoint to that is that I think that I've thought a lot about the sort of thinking tools versus making tools, right? The IDE was historically a making tool. Mhm. It's a place for execution. I think it's migrating away from that. And now with execution going to zero, I think these sort of like multi- agent, you know, nextg ides, a lot of them are about trying things

</details>

**Peter Yang**: 并使用试错作为一种信息来源来指导你的思考。比如很多时候，我只是以一种非常天真的方式构建一个功能，然后我会一遍又一遍地用编码代理来尝试，直到它工作为止。然后我会说，“嘿，写下所有你本可以做得不同的事情，然后我回到最初的点，重新做。”

<details>
<summary>Original English</summary>

**Peter Yang**: >> and using the trial and error as a way to inform your thinking. Like a lot of times I'll just build a feature in a really naive way and I'll hammer the coding agent until it works. Then I'll say, "Hey, write all the things that you would have done differently and I'll go back to the initial point and redo it."

</details>

**Peter Yang**: 所以我想知道，而且我认为 Figma 实际上两者兼具。我认为它是一个设计执行的地方，但它也是一个重要的设计思考场所。我认为这就是他们保持高度相关性的机会。

<details>
<summary>Original English</summary>

**Peter Yang**: >> So I wonder if and I think Figma actually does both. I think it's a place for design execution, but it's also an important place for design thinking. And I think that's their opportunity to be highly relevant in the new stack.

</details>

**主持人**: 是的，我完全同意。我完全同意。嗯，我认为 A6Z 投资了 Pencil，或者类似的东西。Pencil.dev。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, I totally agree. I totally agree. Um, but I I I think A6Z has like uh you guys investing pencil or something. Pencil.dev.

</details>

**Peter Yang**: Speedrun 做到了。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Speedrun did. Yeah.

</details>

**主持人**: 是的。Speedrun。嗯。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Speedrun. And like um

</details>

**Peter Yang**: 是的，Figma 需要升级其 AI 工具，因为你知道，看着这些代理与你协作并完成事情是很有趣的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> yeah, Figma needs to like uh level up his AI tooling because you know like watching these agents collaborate with you and like do stuff is like very very interesting.

</details>

**主持人**: 我知道这对他们来说是头等大事。嗯，你认为编码代理最被低估的能力是什么？你知道，什么被低估了，也许什么被高估了？

<details>
<summary>Original English</summary>

**Host**: >> I know it's top of mind for them. Um yeah, what do you think are the most under discussed capabilities of coding agents? You know, what's what's underhyped and maybe what's overhyped as well?

</details>

**Peter Yang**: 这可能不是被低估的，但你知道，你知道，我认为软件将吞噬世界。我认为编码将吞噬所有知识型工作，对吧？我们已经朝着这个方向发展了。我认为 Lovable 最近推出了……今天。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> This is probably not underhyped, but like but you know, like you know, I I I feel like ent software will eat the world. I I feel like coding will eat all knowledge work, right? And we're kind of going that direction already. Like I I think lovable recently launched like today. Yeah.

</details>

**主持人**: 他们可以支持一切和复制。

<details>
<summary>Original English</summary>

**Host**: >> That they can support everything and replic.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 所以，是的。所以我认为每个人都在追逐这个，而且可能处于领先地位。

<details>
<summary>Original English</summary>

**Host**: >> So, so yeah. So I and I feel like everyone's cha chasing this like and is probably in the lead.

</details>

**Peter Yang**: 是的。但你知道，我不想再用 PowerPoint 了。我不想写 Google 文档了，伙计，我讨厌写 Google 文档，我一生都在写。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. But like, you know, like I I don't want to use PowerPoint anymore. I don't want to like write a Google like I hate writing Google Docs, dude. Like my entire life.

</details>

**主持人**: 是的。是的。所以，所以，但是前几天我在写我的博客文章，而不是直接打字，我说：“嘿，让我用 Clock Code 吧，你知道，给我一些反馈，你来写。”

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Yeah. So, so like but but but the other day I was writing my blog post and instead of just like typing it out, I was like, "Hey, let's let me just use clock code and like you know, let me give you a bunch of feedback and you you write it for me."

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**Peter Yang**: 然后你继续……它完成了最初的 80%。最后的 20% 我不得不手动进去调整。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And then you just keep the um it it did the first 80%. The last 20% I had to manually like go in there like tweak tweak tweak stuff.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 但这就是我现在的工作方式。我从不从零开始。我总是从 AI 那里获得最初的 80%。

<details>
<summary>Original English</summary>

**Peter Yang**: >> But like that that's the way I work now. I I never start from zero. like I always get the first 80% from AI,

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> right?

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 你知道，这很有趣，如果你看看，也有历史上的类比。我认为 Satya 曾说过，Excel 是世界上最强大或最受欢迎的编程语言。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. It's interesting, you know, if you look at there there are also like historical analoges of this. I think Satya said this um which is that Excel is the most powerful or most popular programming language in the world.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 而且它是一种编程语言，有数百万、数千万，我指的是超过一亿人会，也许更多。但我们不那样认为。它是一种描述和解决问题的方式。

<details>
<summary>Original English</summary>

**Host**: >> And that it's sort of a programming language that millions and millions I mean 100 million plus people must know maybe even more. Um and yet we don't think of it that way. It's a way to sort of describe and solve problems.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 我认为编码代理将是 Excel 的一千倍。

<details>
<summary>Original English</summary>

**Host**: >> And I think coding agents are going to be that of course times a thousand.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 即使是像写 Google 文档这样感觉主观的事情，也可以在编码领域以一种更令人满意、更高效的方式表示，使用代理来完成。

<details>
<summary>Original English</summary>

**Host**: >> Where even things that feel subjective like writing Google docs can be represented in the coding domain in such a way that it's more satisfying productive more to use agents to do it.

</details>

**Peter Yang**: 因为 Excel 很受欢迎，因为它非常容易上手，对吧？是的。而编码代理，代码几乎消失了，就像你只是在和一个代理交谈，让它做事情。所以……

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Because Excel was like popular because it's super appro approachable, right? Yes. And like coding agents the code is basically gone like it's like appra just talking to some some agent and getting to do do stuff. So

</details>

**主持人**: 是的。是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Yeah.

</details>

**Peter Yang**: 是的。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Exactly.

</details>

**主持人**: 这将是巨大的。是的。

<details>
<summary>Original English</summary>

**Host**: >> It's going to be hu huge. Yeah.

</details>

**Peter Yang**: 你认为未来的公司是什么样的？它只是一堆代理和一个 CEO 吗？CEO 是一个代理吗？我的意思是，未来公司里人的角色是什么？

<details>
<summary>Original English</summary>

**Peter Yang**: >> What do you think the future company looks like? Is it just a bunch of agents with a CEO? Is the CEO an agent? I mean, what is the role for people in a company in the future?

</details>

**Peter Yang**: 好的。嗯，我有一些激进的观点。所以，我们都曾在一些公司一起工作过，然后……

<details>
<summary>Original English</summary>

**Peter Yang**: >> Okay. Well, I have some hot takes. So, we we both worked at uh some companies together and um

</details>

**主持人**: 嗯哼。

<details>
<summary>Original English</summary>

**Host**: >> Uhhuh.

</details>

**Peter Yang**: 嗯，让我给你一个激进的观点，伙计。也许我们删掉这个，但我觉得公司越大，它就越倾向于变成一个糟糕的工作场所，伙计。是的。因为人太多了，你需要协调。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Uh let let me give you a hot take, man. Maybe we cut this out, but like I feel like as a company gets bigger, it tends to get it tends to become like a shitty shittier place to work, dude. Yeah. Like like because there's like a lot of people you have to align.

</details>

**主持人**: 我认为这是不言而喻的。是的。

<details>
<summary>Original English</summary>

**Host**: >> I think that's axiomatic. Yeah.

</details>

**Peter Yang**: 对。我记得，你知道，也许我应该提一下这家公司，但我记得我们公司以前有过所有这些 OKR 会议，我记得在房间里坐了三个小时讨论 OKR。我只是觉得，伙计，这简直是在浪费我的生命。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Right. And and I remember, you know, maybe I should mention this company, but I remember our company used to have all these like OKR meetings and like I remember sitting in a room for like three hours talking about OKRs. I'm just like, dude, this is like wasting my life.

</details>

**主持人**: 是的。所以我的意思是，我希望更多公司能保持小规模，我认为这一代的创始人已经意识到他们希望尽可能保持小规模。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. So what where I'm going with this is I hope more companies will stay small and and I think the founders of this generation realize that like they want to stay as small as possible.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**Peter Yang**: 嗯，与其拥有一个 10 人的产品团队，不如拥有一个 2 到 3 人的产品团队，然后你只需要拥有一堆代理来帮助你。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Um and instead of having like a 10 person product team, you have like a two or three person product team and you just have a bunch of agents help help you.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 你知道，因为我认为与人类合作相比，与代理合作更容易跨越界限。

<details>
<summary>Original English</summary>

**Peter Yang**: >> You know, because I I I think it's way easier to cross launch a line with a agents than with with humans.

</details>

**主持人**: 是的。是的。嗯，实际上，在某种意义上，代理实际上……因为它也消除了情感。比如，你可以想象我派我的代理，你派你的代理去谈判某事。他们得出了一个结论。对我们任何一方来说，这都不是情感化的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Yeah. Well, actually in a in a sense the agents actually because it takes the emotion out of it too. Like you can imagine if I sent my agent, you sent your agent to go negotiate something. Yeah. And they came out with some conclusion. It's not emotional.

</details>

**Peter Yang**: 它不是……

<details>
<summary>Original English</summary>

**Peter Yang**: >> It's not

</details>

**主持人**: 对我们任何一方来说。你知道，这是非常客观的。是的。

<details>
<summary>Original English</summary>

**Host**: >> for either of us. You know,

</details>

**Peter Yang**: 是的。是的。没错。是的。很有趣。你知道，我们一直在讨论的一个问题是，工作中的 AI 用例是什么？就员工体验而言。我认为这就是你所描述的，对吧？比如，你如何提高工作的 NPS？是的。所以，如果我们回顾一下，或者更广泛地说，人类体验的 NPS，对吧？想想公元前 10000 年的日常人类的 NPS，当时只是不要被狮子吃掉，那就算好的一天，对吧？或者，你知道，一百年前，也许是“好吧，不要在工厂里被杀”。

<details>
<summary>Original English</summary>

**Peter Yang**: >> it's very objective. Yeah. Yeah. Yeah. Exactly. Yeah. It's funny. You know, one of the things that we've been talking a bunch about is like what is the procase for AI at work in terms of employee experience? And I think it's what you're describing, right? Like how do you increase the NPS of work? Yeah. So, if we like go all the way back or even broadly the NPS of the human experience, right? Like think of the NPS of the day-to-day human in 10,000 BC when it's like just don't get eaten by the lion and that's like a good day, right? Or you know maybe a 100 years ago it's like okay don't get killed at the factory

</details>

**主持人**: 嗯，被蒸汽压路机压死，或者别的什么。嗯，现在很多事情是，就像，不要陷入某种高情绪的谈判，你知道，与另一位副总裁的下属。嗯。

<details>
<summary>Original English</summary>

**Host**: >> um crushed by the the steam press or whatever else. And um and now a lot of it is like h like just don't get sucked into some high emotion you know sort of negotiation with another VP's subordinate. Um

</details>

**Peter Yang**: 是的，就像一个 50 人的堆栈线程来回争论。

<details>
<summary>Original English</summary>

**Peter Yang**: >> yeah like a 50 me stack thread going back and forth.

</details>

**主持人**: 是的。没错。然后最终每个人都说，“我不想告诉 CEO。”最终它会传达上去，这太糟糕了。所以，也许未来的模式是，很多情感化、主观性的工作都得到了处理。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Exactly. And then eventually everyone's like, I don't want to tell the CEO. And eventually it goes there and it's just terrible. Um, so maybe the future of this is that a lot of that emotional subjective work gets handled.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**Peter Yang**: 我们只是在指导过程，而不是身处其中，以一种不适合我们作为人类的方式。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And we're sort of guiding the process but not in the middle of it in a way that just doesn't suit us as humans.

</details>

**主持人**: 是的。你知道，我过着双重生活，既是 PM 又是创作者，我觉得所有 PM 其实都只想创造产品。他们想创造产品，然后……

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Like you know, I I I lead a double life as a PM creator and like I feel like all the PMs actually just want to create products. They want to create products and and

</details>

**Peter Yang**: 嗯，这就是我们都开始做这个的原因。你知道，这太有趣了。我的意思是，Nicole 总是谈论这个，但每个 PM 的理想 PM 形象都是创新者，你知道吗？我提出了新东西，然后我有了大的见解，它解锁了产品。

<details>
<summary>Original English</summary>

**Peter Yang**: >> well that's why we all got into it. You know, it's it's so interesting. I mean, Nicole talks about this all the time, but like every PM's sort of view view of the ideal PM is the innovator, you know, like I came up with the new thing and it's like I sort of like had the big insight and it unlocked the product.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 我认为“黑丸”理论是，我认为大多数 PM 都不知道如何做到这一点。事实上，许多公司没有任何职能部门的人知道如何做到这一点。

<details>
<summary>Original English</summary>

**Peter Yang**: >> I think the black pill is I don't think most PMs know how to do that. In fact, many companies have zero people that know how to do that at all in any function.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 尽管如此，我认为 PM 们渴望能够做到这一点，他们应该要么做到，要么成功，要么可能不成功并转到不同的职能部门。我也觉得我的激进观点是，我认识的所有 PM 晚上和周末都在尝试编码。

<details>
<summary>Original English</summary>

**Peter Yang**: So, nonetheless, I think PMs aspire to be able to do that and they should either do it and either be successful or maybe not successful and move to a different function. I I also feel like my hot take is like uh like basically all the PMs I know are trying to vibe code at night on weekends.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 我觉得我的激进观点是，如果你真的失业了，你可能就有更多的时间成为一个建设者，成为一个创新者，因为你可以真正地玩所有这些东西，学习所有这些东西。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And I feel like my hot take is that like I feel like if you're actually unemployed like you probably have more time to be a builder and like to be innovative because you can actually like play all this stuff and like learn all this stuff.

</details>

**主持人**: 很多 PM 都在尝试……

<details>
<summary>Original English</summary>

**Host**: >> A lot of PMs are trying to

</details>

**Peter Yang**: 或者也许成为团队里的工程师，你知道吗？我以前是工程师，我不知道我是否是被迫成为 PM。也许我也认为 PM 是一个地位更高的职位，当我加入 Google 时。但后来，你知道，这太糟糕了，你从来没有真正获得实际交付的满足感，除了每个季度一次的交付。

<details>
<summary>Original English</summary>

**Peter Yang**: >> or maybe be an engineer in the team, you know? I used to be an engineer and I got sort of I don't know if I got forced to be a PM. Maybe I also perceived PM as like being a little more high status when I joined Google. But then eventually you like this is terrible, you know, like you never really get the satisfaction of actually shipping other than like you know once a quarter when you ship.

</details>

**主持人**: 我的意思是，PM 的技能，比如与用户交谈，弄清楚要解决什么问题，这些仍然非常重要。

<details>
<summary>Original English</summary>

**Host**: >> I mean the PM skills of like talking to users and like trying to figure out what to do like what problem to solve like those are very important still.

</details>

**Peter Yang**: 是的。是的。但你必须扮演多重角色，伙计。你必须自己去构建一个东西，去原型化它，然后获得一些反馈，然后也许带上工程师。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. And and like but yeah, you got to wear multiple hats, dude. You got you got to like go go go build a thing yourself, go prototype it and get some feedback and then maybe bring engineer along.

</details>

**主持人**: 你认为每个人都必须像你一样快吗？我的意思是，Gary 谈到了“stemmies”和跳过睡眠，GStack。我的意思是，这是我们都需要工作的默认方式吗？还是你认为有权衡思考的空间？

<details>
<summary>Original English</summary>

**Host**: >> How much do you think that everyone has to go as fast as you know I mean like Gary was talking about stemmies and skipping sleep and 10 like you know GStack I mean is hey I mean is that like the default way that we all need to work or do you think there's a trade-off for thoughtfulness?

</details>

**Peter Yang**: 我认为现在很容易，有了所有这些 AI 工具，就朝着十个不同的方向同时前进。

<details>
<summary>Original English</summary>

**Peter Yang**: >> I I I think it's very easy now with all these AI tools just going like 10 different directions at once.

</details>

**主持人**: 是的。所以有时你确实需要放慢脚步，试着弄清楚你想去哪里。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. So sometimes you do have to slow down and try to figure out where you want to go.

</details>

**Peter Yang**: 是的。但我同样认为，传统的年度规划流程，以及所有这些……我只是觉得那不再奏效了，你知道吗？

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. But I also believe that like u the traditional process where you like do annual planning and like do all this like I just feel like that doesn't really work anymore, you know?

</details>

**主持人**: 是的。是的。并且为了记录在案，我爱 Gary，我非常欣赏他。所以这是我的看法，因为我对此想了很多。你知道，谁昨天问我这个？Hithan。嗯，他印象深刻。是的。Ch。是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. Yeah. And for the record, I love Gary and I like think the world of him. So here's my view on that because I thought a bunch about that. You know who asked me this the other day? Hithan um who's really really impressed. Yeah. Ch. Yeah.

</details>

**Peter Yang**: 所以我们在谈论这种生产力“色情”内容，每个人都在运行 20 个代理，20 个显示器，等等。我认为，当涉及到……

<details>
<summary>Original English</summary>

**Peter Yang**: >> So we're talking about this like sort of productivity porn and everybody's got 20 agents running and 20 monitors and blah blah blah. And like I do think when it comes to

</details>

**Peter Yang**: 完全实现局部最大值，你应该非常快地行动，对吧？所以，假设你爬山，你到达了一个新的局部最大值的底部。我认为有了代理，你应该能够非常快地爬到山顶，对吧？你有一个新的见解，围绕这个见解构建一切，使其完全表达出来。但然后，我认为要达到下一个，你知道，下一个山峰，你可能需要放慢脚步，几乎停下来，去接触大自然，做任何事情。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> um fully realizing a local a sort of local maxima, you should go very fast, right? So let's say you kind of hill climb, you get to the bottom of a new local maxima. I think with agents, you should be able to get to the top of that hill extremely fast, right? You have a new insight, build everything around the insight so it's fully expressed. But then I think to get to the next, you know, the next sort of hill,

</details>

**主持人**: 你需要放慢脚步，几乎停下来，去接触大自然，做任何事情。是的。

<details>
<summary>Original English</summary>

**Host**: >> you've got to probably slow down and almost stop and go touch grass and do whatever. Yeah.

</details>

**Peter Yang**: 所以我认为这是一种快与慢的结合。这可能是未来的方式。

<details>
<summary>Original English</summary>

**Peter Yang**: >> So I think there's this combination of like fast and slow. That's probably the future way.

</details>

**主持人**: 是的，我认为是这样。而且，你必须进行随机的探索，寻找市场契合点，这需要我们一段时间，对吧？所以不是……

<details>
<summary>Original English</summary>

**Host**: >> Yeah, I think so. And and like you got to go on that random walk trying to find hard market fit which take takes us a while, right? So it's not like

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 所以我们在录音开始前谈论了一些“一站式”商业平台。你研究过它们吗？你有什么看法？

<details>
<summary>Original English</summary>

**Host**: >> So we were talking before we started recording about some of the business in a box platforms. Have you looked at them? Do you have a view?

</details>

**Peter Yang**: 我看过 Post Yet，我们谈过的那个。我不知道那个家伙是故意让它与 AI Slab 相反，还是……

<details>
<summary>Original English</summary>

**Peter Yang**: >> I've looked at post yet that we talked about like I don't know if the guy like intentionally made it the opposite of AI slab or or is it kind of you

</details>

**主持人**: 我认为是的。是的。

<details>
<summary>Original English</summary>

**Host**: >> I think so. Yes. Yes.

</details>

**Peter Yang**: 这很有趣。嗯，我有很大的公众影响力，对吧？所以我把我的所有东西都连接起来了。然后，嗯，它确实能让你很好地了解可能发生的事情，但目前它可能还处于早期阶段。它告诉我运行 Facebook 广告。我为什么要运行 Facebook 广告？

<details>
<summary>Original English</summary>

**Peter Yang**: >> That's funny. Well, I mean, I have a pretty big public presence, right? So, I connect all my to to it. And then, um, I mean, it's it's definitely gives a good peak into what's possible, but like right now it's probably still pretty like early stage. Like, it's telling me to run like fa Facebook ads. Like, why am I running Facebook ads?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 你知道，所以……

<details>
<summary>Original English</summary>

**Peter Yang**: >> You know, so

</details>

**主持人**: 我不知道。是的。是的。是的。我的意思是，我对它感到非常兴奋，因为它确实为更多人构建公司提供了一条途径。是的。即使它们是单人公司，你知道，如果你想想建立一家价值十亿美元的企业有多么竞争激烈，支持它的市场，尝试的人数，与一亿美元，与一千万，与 10 万美元 TAM 相比。

<details>
<summary>Original English</summary>

**Host**: >> I don't know. Yeah. Yeah. Yeah. I I mean, I'm very excited about it because it does feel like it's a path for more people to build companies. Yeah. Even if they're single oneperson companies, you know, like if you think about how competitive it is to build a billion dollar business, like the markets that support it, the number of people trying versus hundred million versus 10 million versus $100,000 TAM.

</details>

**Peter Yang**: 是的。也许全国各地，世界各地都有这些领域，存在 10 万美元 TAM 产品的机会。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Like maybe there are these pockets all over the country, all over the world where there are opportunities for $100,000 TAM products. Yeah.

</details>

**主持人**: 那将改变某人的生活。现在，这不是一家企业风险投资公司，但没关系。是的。所以我希望整个理论都能奏效，因为我认为这是让更多人参与进来的方式。

<details>
<summary>Original English</summary>

**Host**: >> And that would change somebody's life. Now, that's not an enterprise ventureback company, but that's okay. Yeah. So, I hope that whole thesis works because I do think it's a way to get more people to participate, you know.

</details>

**Peter Yang**: 是的。这是我对我孩子的计划，伙计。我想让他们在高中时就建立自给自足的企业。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. That that that's my plan for my kids, dude. Like I want them to just build like um bootstrap businesses in high school.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 他们可以跳过大学和……嗯，核心的职业生涯。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And they can skip the whole college and like uh core corporate life.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 嗯，伙计，我认为这是……你知道，十年来，一直有一种道德恐慌，说孩子们想成为 YouTuber。是的。你知道，你是个 YouTuber。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Well, dude, I think this is like, you know, for 10 years there's this moral panic about the kids want to be YouTubers. Yeah. You know, you're a YouTuber.

</details>

**主持人**: 嗯，你知道，你知道，以 Mr. 的名义。我认为，对于那些不是程序员的人来说，唯一的渠道就是在线上创建 YouTube 视频。

<details>
<summary>Original English</summary>

**Host**: >> Um you know, you know, in the in the vein of Mr. And and I think the like pro case for that actually is that the kids wanted to be entrepreneurs or have agency. And the only channel for people if they weren't programmers was creating YouTube videos at least online.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 所以，如果你是一个在线原生代，你想创造一些东西，你不是程序员，你就制作一个 YouTube 节目。现在你可以做更多的事情了。

<details>
<summary>Original English</summary>

**Host**: >> So if you're like an online native generation, you want to create something you're not a programmer, you make a YouTube show. Now you can make a lot more than that.

</details>

**Peter Yang**: 是的。你可以建造任何你想建造的东西。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. You you can build whatever you want. Yeah.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: >> Exactly.

</details>

**Peter Yang**: 所以。没错。

<details>
<summary>Original English</summary>

**Peter Yang**: >> So Exactly.

</details>

**主持人**: 这将非常令人兴奋。是的。

<details>
<summary>Original English</summary>

**Host**: >> It'd be very exciting. Yeah.

</details>

**Peter Yang**: 是的。还有什么激进的观点吗？

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Any other hot takes for us?

</details>

**主持人**: 我对你的想法很好奇。我的意思是，很多人说代理将首先与你的产品互动，对吧？然后你看到了所有这些伟大的公司，比如，构建 API 和 MCP。

<details>
<summary>Original English</summary>

**Host**: >> I'm curious about your thoughts about this actually. Like so I feel like uh a lot of people are saying like agents will interact with your product first, right? And and then you see all these great companies like uh building like APIs and MCPS.

</details>

**Peter Yang**: 嗯。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Mh.

</details>

**主持人**: 但，你如何看待……你知道，你一直是消费者一段时间了。所以，消费者就是，你得让用户回来使用你的产品，对吧？但现在，用户就是，“嘿，去发送代理来使用。”所以，你如何看待留存率以及所有这些基本的东西？你知道，或者甚至品牌资产，因为代理只是指向某个 API，你知道，你怎么……

<details>
<summary>Original English</summary>

**Host**: >> But like how do how do you think about like you know you've been consumer for a while. So like consumer is like you got to get the user to come back and use your product, right? But but now like the user is like hey go send the agent to use So, so how do you think about retention and all this like basic stuff like how do you you know or even like brand equity because the agent just like point some API like you know how do you

</details>

**Peter Yang**: 是的，我不知道。所以，我认为其中一个……我不知道真相是什么，但……

<details>
<summary>Original English</summary>

**Peter Yang**: >> yeah I don't okay so I think one of I don't know is the is the truth but um

</details>

**Peter Yang**: 我有一些想法。一是，我认为消费者领域的许多复杂性之所以发生，是因为我们必须进行间接货币化。

<details>
<summary>Original English</summary>

**Peter Yang**: there's I have a few thoughts so one I think that a lot of the sophistication sophistication that happened in consumer happened because we had to have indirect monetization

</details>

**主持人**: 好的。就像我们从不直接向消费者收费一样。

<details>
<summary>Original English</summary>

**Host**: >> okay like we just were never charging consumers directly for these products

</details>

**Peter Yang**: 这就是为什么我们有了广告和……

<details>
<summary>Original English</summary>

**Peter Yang**: which is why you got

</details>

**主持人**: 广告和大规模网络，我们都痴迷于留存率、参与度和鲸鱼用户，所有这些东西都非常非常重要，因为我们没有直接向人们收费。

<details>
<summary>Original English</summary>

**Host**: >> got ads and stuff ads and large scale networks and we all obsessed with retention and engagement and whales and all of these things really really mattered because we didn't simply charge people for products.

</details>

**Peter Yang**: 所以我认为 AI 时代真正有帮助的一件事是，消费者现在很兴奋尝试新事物。他们愿意支付，他们愿意支付非常高的价格。

<details>
<summary>Original English</summary>

**Peter Yang**: So I think one big thing that's actually really helped in the AI era with that is that consumers are now excited to try new things. They're willing to pay they're willing to pay a really high price point.

</details>

**Peter Yang**: 嗯，消费者领域也有消费收入，这是第一次。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Um there's also consumption revenue in consumer for the first time

</details>

**主持人**: 比如代币之类的。

<details>
<summary>Original English</summary>

**Host**: >> like token and stuff.

</details>

**Peter Yang**: 是的。是的。比如代币。你有订阅加上你的代币。所以，然后实际的……一种伪装的祝福是，也有实际的成本。你有这些推理成本。所以你会想，“哇，我们必须从第一天就开始向客户收费。”

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Yeah. For like tokens. You have your subscription plus your token. So and then the actual like the sort of blessing in disguise is that there are real costs as well. you have these inference costs. So you're like, "Wow, we have to charge our customer on day one."

</details>

**Peter Yang**: 所以我认为一件事是，业务模式的简化将真正有助于你描述的许多方面。

<details>
<summary>Original English</summary>

**Peter Yang**: So I think one thing is that like the business model simplification I think will really help with a lot of what you're describing.

</details>

**Peter Yang**: 第二，我认为很多产品将拥有某种……它将有一个 API 接口供你的代理进行交互，或者用于……你知道，用于事务性的……事情。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Two, I think that a lot of the products will have a sort of, you know, it'll have an API interface for your agents to interact with or for, you know, for transactional sort of wrote things.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 然后它还将有一个基于消费的接口。所以你也可以想象一个……一个移动应用程序，里面有一个 feed，然后你可以把它翻转过来，看看幕后。

<details>
<summary>Original English</summary>

**Peter Yang**: >> And then it'll have like a consumption based interface as well. So you can also imagine a like a mobile app where there's like the feed, but then you can kind of turn it over to where the wires are.

</details>

**主持人**: 嗯哼。你也可以要求事情完成，或者你也可以看到完成的事情的日志。

<details>
<summary>Original English</summary>

**Host**: >> Mhm. And you can just ask for things to get done or you can just see the log of the things that got done.

</details>

**Peter Yang**: 是的，也许人们会两者都做，对吧？

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah, maybe people would do both, right?

</details>

**主持人**: 我的意思是，你可以想象 Credit Karma，我们曾经在那里工作，你知道，偶尔你想看看你的分数历史和一些其他的信用卡优惠。我不知道。我的意思是……

<details>
<summary>Original English</summary>

**Host**: >> I mean, you can imagine Credit Karma where we worked, you know, like once in a while you want to just take a look at your score history and a few other maybe credit card offers. I don't know. I mean,

</details>

**Peter Yang**: 是的。是的。如果我能得到我的分数和各种信用卡优惠，我肯定会做的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> yeah. Yeah. If I get my score with all kind of credit card offers, I'll definitely do that.

</details>

**主持人**: 是的，100%。没错。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, 100%. Exactly.

</details>

**Peter Yang**: 另一方面，有时候你想说，“嘿，你能帮我修好所有东西吗？或者你这个星期修好了什么？我省了多少钱？”你知道。

<details>
<summary>Original English</summary>

**Peter Yang**: >> On the other hand, like sometimes you want to just be like, yo, like can you just fix all my stuff or like what stuff did you fix this week? How much money did I save? You know,

</details>

**主持人**: 明白了。明白了。

<details>
<summary>Original English</summary>

**Host**: >> got it. Got it.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**主持人**: 这绝对很有趣。是的。

<details>
<summary>Original English</summary>

**Host**: >> It's definitely interesting. Yeah.

</details>

**Peter Yang**: 但你看，我也只是觉得整个代理技术栈正在兴起。身份、支付、营销，我们甚至……CLI 与 MCP。所有这些都是真正的新事物，我认为很多旧的模式都将不复存在。

<details>
<summary>Original English</summary>

**Peter Yang**: >> But look, I also just think the whole agent stack is emerging. identity, payments, marketing, we don't even even CLI versus MCP. Like all of these are really new things and I think a lot of the old playbook goes away.

</details>

**主持人**: 是的，这是一个全新的世界。而且，我认为在 2025 年，我认为代理被高估了，但现在我认为它真的来了。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, it's a whole new world and like in 2025 I thought agents was overhyped but now I think it's really coming like

</details>

**Peter Yang**: 我也是。我知道这个词很令人沮丧，因为它被过度使用了。

<details>
<summary>Original English</summary>

**Peter Yang**: >> me too. I know it's just the word is frustrating because it gets so overloaded.

</details>

**主持人**: 是的，有工作流之类的。所有这些。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, there's like workflows like all this kind of

</details>

**Peter Yang**: 完全同意。我一直在尝试说，我们能不能只说“模型循环”？

<details>
<summary>Original English</summary>

**Peter Yang**: >> Totally. I've been trying to just say like can we just say like model in a loop?

</details>

**主持人**: 是的，确切地说。在循环中使用工具的模型。这是最好的定义。是的。是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, exactly. Model that use tools in a loop. That's the best definition. Yeah. Yeah.

</details>

**Peter Yang**: 但没人想听。代理更闪亮，你知道。

<details>
<summary>Original English</summary>

**Peter Yang**: >> But nobody likes to hear that. It's Asians is much flashier, you know.

</details>

**主持人**: 是的，它更闪亮。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, it's flashier.

</details>

**Peter Yang**: 是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah.

</details>

**Peter Yang**: 我的希望是，嗯，所有这些东西，很多人认为我们会失去工作，这可能在某个时候会发生，但我希望所有这些东西能让人类工作更有趣，让我们的工作更有趣，你知道吗？

<details>
<summary>Original English</summary>

**Peter Yang**: >> My my hope is that um all all this stuff's like a lot of people think like we're going to lose our jobs, which probably what will happen at some point, but like I hope all this stuff makes just makes like uh human work more fun like our jobs more fun, you know?

</details>

**主持人**: 伙计，我不认为我们会都失业。我真的认为，我们看到很多公司，你知道。所以我们看了很多公司，我们看到了两个不同的类别。

<details>
<summary>Original English</summary>

**Host**: >> Dude, I don't think we're all going to lose our jobs. Like I really think the and we see this a lot of companies, you know. So we look at a ton of companies and we've seen two different buckets. So

</details>

**Peter Yang**: 一类是，“嘿，我们极大地提高了一个人或一个团队的生产力。”我们在招聘中看到了这一点，但我们无法完成 100% 的工作。所以，我们可以做电话筛选，但显然，你知道，不能带候选人参观办公室。或者我们可以做电话筛选，回答所有关于公司的问题，甚至可以做薪酬谈判，但我们无法完成入职。

<details>
<summary>Original English</summary>

**Peter Yang**: >> one bucket is hey, we dramatically increase productivity for a person or a team. We see this in like recruiting, but we couldn't do 100% of the job. So, we could do the phone screen, but we couldn't obviously, you know, show the candidate around the office or we could do the phone screen and we could like answer all the questions about the company and we could even do the like comp negotiation, but we couldn't do the onboarding.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Peter Yang**: 另一种公司风格，我们看到的是，也许是 Decagon，或者 Happy Robot，是，“嘿，我们完成了 100% 的工作”，比如客户支持。

<details>
<summary>Original English</summary>

**Peter Yang**: >> The other style of company which we see which is maybe a decagon, right, or a happy robot is, hey, we did 100% of a job like customer support.

</details>

**主持人**: 你知道，客户打来电话，他们有问题，我们希望解决了他们的疑问，然后就这样。这是 100% 自动化的。

<details>
<summary>Original English</summary>

**Host**: >> You know, the the customer called in, they had a question, we hopefully resolved their query and then that's it. M and that is 100% automated.

</details>

**Peter Yang**: 我认为第二类，即 100% 自动化工作职能的类别，非常罕见。几乎每一个 AI 产品、AI 原生 X 或 Y，我们看到的都能提供巨大的提升，但无法做到 100%。

<details>
<summary>Original English</summary>

**Peter Yang**: I'd say that that second group where you have 100% automation of a job function is really rare. Almost every AI product AI native X or Y we see is able to provide dramatic lift but it's not able to do 100%.

</details>

**主持人**: 所以最后 10% 是人类做的。

<details>
<summary>Original English</summary>

**Host**: >> So last 10% use humans.

</details>

**Peter Yang**: 是的，至少今天仍然是人类在做这些事情。而且这很有趣，因为买家将其视为软件，昂贵的软件，而在 Happy Robot Docking Sierra 之类的情况下，他们将其视为廉价劳动力。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah, it's still it's today anyway it's still humans that do that stuff and it's interesting too because the buyer looks at that as software as expensive software whereas in the case of something like a happy robot docking Sierra they look at it as like cheap labor. M

</details>

**主持人**: 所以我认为买家的心态不同，但由于实现 100% 自动化存在困难，我认为很多效率提升会以不同的方式体现出来。可能不是工作岗位减少，也许我们会实现欧洲式的四天工作周，也许公司会提高两倍的生产力。我不知道。

<details>
<summary>Original English</summary>

**Host**: >> so I do think there's a different buyer mindset but because there's been this difficulty of getting to 100% automation I think a lot of the efficiency gain shows up in just a different way probably not less jobs maybe we get like the European style 4 day work week maybe companies get like twice as productive I have no idea

</details>

**Peter Yang**: 是的，但你不认为……我觉得会有一个从……这些拥有 10000 多名员工的公司裁员，到希望……更多的小公司，比如 Solarreneurs 之类的人。

<details>
<summary>Original English</summary>

**Peter Yang**: >> yeah but but you don't think that like uh I I I feel like there's going to be a transition from like these like 10,000 plus people companies laying a lot of people off to hopefully like more smaller companies like solarreneurs and stuff like that

</details>

**主持人**: 我认为是的。我认为经济的形态会改变，比如集中程度。但我只是不认为工作岗位会减少。我认为人类的雄心没有上限。

<details>
<summary>Original English</summary>

**Host**: >> I I think yes I think that they'll the the sort of shape of the economy is going to change like the amount of concentration but I just don't think there's going to be less jobs. I think human ambition has no ceiling.

</details>

**Peter Yang**: 你知道，人类的欲望没有上限。读任何一本稍微有趣一点的科幻小说。

<details>
<summary>Original English</summary>

**Peter Yang**: >> You know, human desire has no ceiling and just read any mildly interesting science fiction book

</details>

**Peter Yang**: 就像，没有办法，这就是我们想要的和需要的所有的顶峰表达。我们将说服自己，你知道，每天读到的所有新东西，比如奢侈品、肽，你知道，每个人都会拥有所有这些东西，并且想要更多。你知道。

<details>
<summary>Original English</summary>

**Peter Yang**: >> like there's no way this is the peak expression of all the stuff that we want and we need and we're going to convince ourselves and you know all the new things that you read about every day is these luxuries peptides and you know everybody is going to have all of that stuff and want even more. You know,

</details>

**Peter Yang**: 伙计，我看到一条很好的推文。有人发推说，就业市场太糟糕了，我现在只能追求我的梦想了，之类的。所以，你知道，就像，你可能失业了，但现在你可以真正做自己的事情。

<details>
<summary>Original English</summary>

**Peter Yang**: dude, I I saw a really good tweet about this. Like someone tweeted that like um the the job market is so bad that I can only pursue my dreams now or something like that. So like it's it's like you know, it's like Yeah. So maybe you lost your job, but like now you can actually do your own thing.

</details>

**主持人**: 并有机会实现它，你知道吗？

<details>
<summary>Original English</summary>

**Host**: >> And have a shot at actually achieving it, you know?

</details>

**Peter Yang**: 是的。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah. Yeah.

</details>

**主持人**: 酷。嗯，太棒了，伙计。也许这是一个很好的积极的结束点。

<details>
<summary>Original English</summary>

**Host**: >> Cool. Well, awesome, man. Maybe that's a good uh positive note to end on.

</details>

**Peter Yang**: 是的，很高兴知道。是的。酷。你做得很好。是的。

<details>
<summary>Original English</summary>

**Peter Yang**: >> Yeah, that's good to know. Yeah. Cool. Good thing you do. Yeah.

</details>

**主持人**: 谢谢你，Peter。是的。谢谢。

<details>
<summary>Original English</summary>

**Host**: >> Thanks, Peter. Yeah. Thank

</details>