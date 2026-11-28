---
author: How I AI
date: '2026-11-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ztt8irafLMQ
speaker: How I AI
tags:
  - product-management
  - ai-agent
  - workflow-automation
  - experimentation
title: Figma 内部 PM OS 揭秘：AI Skills、自动化实验 Auto XP 与工作流实践
summary: Figma 产品经理 Ezra McCabe 分享了其团队打造的内部 PM OS（包含 31 项技能的代码库）以及自动化实验系统 Auto XP。内容涵盖利用 AI 辅助日常协作、文档补全、自动化 Bug 扫描，以及基于轻量模型构建实时写作助手的实践。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ezra McCabe
  - Claire Vo
companies_orgs:
  - Figma
products_models:
  - Codex
  - Auto XP
  - FigJam
media_books: []
status: evergreen
---
### 引言与背景

**Ezra McCabe**: 我觉得，作为一名增长产品经理（Growth PM），你所能犯下的最大罪过就是浪费流量。如果我们能把我自己的工作自动化，打造一个小小的增长 PM 智能体，让它不知疲倦地一直跑下去，会怎么样？我把它叫做 Auto XP。现在我们的一位工程师正在运行它，上面有大约五个不同的实验在同时进行，我甚至都没去瞧过一眼，而它在第一个实验上就斩获了巨大的成功。Auto XP 有属于它自己的专属频道，可以在里面自己和自己沟通。“嘿，Auto XP，去我们的设置页面上找个实验做做看，看你能做些什么，尽管去折腾。”它就会触发一个数据科学家智能体去寻找流失点、分析漏斗、查看用户群体结构变化（mix shift）等等。
<details><summary>Original English</summary>
I, as a growth PM, I feel like the biggest sin you can commit is wasting traffic. What if we could just automate myself out of a job and like create a little growth PM who could just like run and run and run. I call it Auto XP and right now one of our engineers is running it and has like five different experiments going that I have not taken a look at and it found a huge win on its very first experiment. Auto XP has its own channel where it can communicate with itself. Hey Auto XP, go find an experiment to run on our settings page. See what you can do. Go crazy. And it will trigger a data scientist to go find drop off and like look at the funnel and look at mix shift and all those things.
</details>

>> 整个假设就像是：你该如何充分利用所有这些流量，最大化实验的数量？能生活在这样的时代真是太棒了。你甚至可以直接在那里进行实时编码（live code）。这太不可思议了。
<details><summary>Original English</summary>
>> The whole hypothesis was like, how do you exploit all this traffic and maximize the number experiments and then like the time to be alive. It is here. You can just like live code it there. This is amazing.
</details>

>> 欢迎回到《How I AI》。我是 Claire Vo，产品负责人，也是一名 AI 痴迷者，我的使命就是帮助大家利用这些新工具打造出更好的产品。今天来到节目的是 Figma 的产品经理 Ezra McCabe。他将向我们展示 Figma 内部的 PM OS——即 Figma 每位产品经理用来让自己的工作与生活变得更轻松的 31 项技能。当然，我们还会聊聊 Jev，以及如何利用这个轻量、廉价且快速的模型构建一个实时 AI 编辑器。让我们正式开始吧。Optimizely 面向营销人员的智能体平台建立在一个更宏大的理念之上：一个完整的智能体目录，如今又加入了一支新公布的虚拟队友战队，每个人都有明确的职责和独特的性格。这不仅仅关乎更快速地起草文案，还在于处理协调工作——调研、审批、交接、路由分发，以及那些悄悄吞噬掉你整周时间却从未登上任何人高光展示集锦的来回沟通。了解背后的故事，倾听那些已经交出繁杂事务的营销人员的心声。在 optimizely.com/howiai 认识这支战队，了解虚拟队友能为你做些什么。Ezra，欢迎来到《How I AI》。
<details><summary>Original English</summary>
>> Welcome back to How I AI. I'm Claire Vo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Ezra McCabe, product manager at Sigma and he's going to show us Sigma's internal PMOS, the 31 skills that every product manager at Sigma uses to make their life a little bit easier. We're also going to talk about, of course, my boy Jev and how you can build a real-time AI editor with that little cheap fast model. Let's get to it. Optimizely agent platform for marketers is built on a bigger idea, a whole directory of agents now joined by a newly revealed squad of virtual teammates each with a defined [music] role and a personality of their own. This isn't about faster drafts, it's about handling the coordination too. The research, the [music] approvals, the hand-offs, the routing, the back and forth that quietly eats your week and never makes it into anyone's highlight reel. Get the story behind it all. Hear the confessions from marketers who have handed off the busy work. Meet the squad and understand what virtual teammates can do for you at [music] optimizely.com/howiai. Ezra, welcome to How I AI.
</details>

>> 非常感谢。
<details><summary>Original English</summary>
>> Thanks so much.
</details>

>> 我特别喜欢这个播客的原因之一——因为我知道我们有很多听众也同时在听 Lenny 的播客——就是现在的产品经理们确实在全面拥抱 AI，但大家的方式却完全不同，对吧？早在无数个“AI 年”之前，我就从 ChatPRD 开始尝试，探索我们如何撰写文档并快速推进。我们已经见到了太多不同的产品工作流。我认为现在每个人都在某种程度上打造属于他们自己的“定制化产品平台”，因为他们现在有能力这么做。所以当你提到你做了一个 PM OS 时，我简直太兴奋了，一定要邀请你过来做个演示。快跟我说说，我们今天要看到的东西其起因故事是怎样的？你为什么想要构建它？
<details><summary>Original English</summary>
>> One of the things I love about this podcast in particular, because I know we have a lot of crossover listeners to Lenny's podcast, is PMs are really leaning into AI, but they're all doing it in completely different ways, right? I started like a jillion AI years ago with like chat PRD and like how do we make documentation and go really fast. We've seen so many different product flows. I think everybody's sort of crafting their like artisanal product platform now because they can. And so when you said you had a PMOS, I was just so excited to have you come on and demo it. So tell me, what was the origin story of what we're going to see today and why did you build it?
</details>

### PM OS 的诞生与解决的痛点

**Ezra McCabe**: 我喜欢跟我的工程师们说，我的目标是在正确的地方偷懒。所以对我来说，很大一部分原因在于几年前我刚加入 Figma 时，我以为每个人都会在工作中深度使用 AI，到处都是极其前沿的 AI 构建方式。我甚至觉得自己已经落后了。我觉得落后是因为我们都在刷 Twitter，都会看到类似 Thibaud 这样的人一直在发推探讨宇宙的未来之类的。带着这种深深的落后感走进去后，我却发现除了工程团队之外，基本上根本没人用这些工具来做实际的工作。

于是我开始尝试把我自己的一些生产力流程自动化。很多年前我就属于那种试图在 Zapier 里做太多事情的人。我投入的时间越多——其一是 Claude Code 刚发布的时候，我开始意识到在终端里突然可以做一些非常有趣的事情了。我可以构建 CLI，毕竟我们当时正处于 CLI 热潮阶段。而且和我一起工作的其他 PM 没人在做这个，他们都抱有某种好奇心。

当时我们当时的 CPO Yuki 提出了一个非常有趣的挑战，基本上就是：“怎样才能让我们所有的产品经理都‘服下 AI 药丸’（AI-pilled）？那会是什么样的一种体验？”在与另外几位产品经理（特别致敬 Jinan 和 Lawrence）的合作下，我开始思考：怎样才能把我自己像个怪人一样蜷缩在笔记本电脑前倒腾的这些东西，变成一种很多其他 PM 都能在其基础上继续构建的可复用框架？
<details><summary>Original English</summary>
>> I like to tell my engineers that I my goal is to be lazy in the right places. And so for me a lot of it was I walked into Figma a couple years ago and I thought everyone was going to be using AI. It was going to be crazy AI built. Um I was just going to I was already feeling behind. Like I just I felt behind cuz we're all on Twitter and we all see like, you know, Tibo just posting about like the future of the universe. And I walked in feeling really behind and I realized basically no one was using these tools outside of engineering to like get real stuff done. And so I started just trying to automate some of my own productivity. Like I was the person who was trying to do too much in Zapier like many years ago. And the more time I spent with it, one, Claude coded had just come out and I started to realize like there were things I could do in the terminal that were like really interesting all of a sudden. I could like build CLI, we you know, we were in that CLI phase. And like no other PMs who I was working with were doing it and they were all sort of curious. And we had this really interesting challenge from Yuki, who was our CPO at the time, which was basically like, what would it take to get all of our PMs kind of AI pill? Like what would that look like? And um working with a couple of other PMs, um shout out to Jinan and Lawrence, I started thinking about like what would it look like to turn this thing that I was doing just like hunched over my laptop like a little creep into this kind of like reusable thing that lots of other PMs could could build on top of.
</details>

>> 太棒了。那么你认为对于产品经理来说，最重要、最应该尝试用 AI 去解决的问题是什么？
<details><summary>Original English</summary>
>> Great. And so what what were like the problems that you thought were most important for PMs to think they could solve with AI?
</details>

**Ezra McCabe**: 首先，我觉得关于做 PM 有个老生常谈的现实，那就是你要做的事情太多了，问题在于：哪些事情是你要么做得很烂，要么根本没时间去做的？

所以对我来说就是：好吧，针对那些我没有去做的事情，以及我们作为一个团队没有去做的事情，我们怎样才能以“最低允许的遗漏程度”把它们完成？比如我的事件响应（IR）支持团队非常出色，但每次产品发布时我总是会忘记在恰当的时间把他们拉进同步圈。所以我思考的问题之一就是：我怎样才能做到这一点，确保我不会漏掉像 Katie 这样的支持运营人员？

再比如会议纪要，那真不是我的长项，我非常不擅长做这个。但我们明明有转录工具，我如何才能把这件事做得足够好，从而不至于阻碍其他人的进度？所以很多技能的出发点都是源于我想解决的实际工作——比如在组织中找到负责某某业务的人。我们现在大约有 2000 人了，因此仅仅是搞清楚代码所有者（code owner）是谁就非常有价值，以及搞清楚我们彼此之间的协同关系。

另外就是，我如何能从所有其他 PM 那里挖掘出有趣的生产力成果？其中的一项技能就是一个非常详尽的 Spec 技能，它开始梳理：如果你想极其深入、规范地做这件事，我们的代码库到底是如何运作的？如果你想用正确的方式来推进，它应该呈现出怎样的形态？
<details><summary>Original English</summary>
>> First of all, I feel like the the like really trite thing about being a PM is that you're doing too many jobs, and the question is like, which jobs do you either do really poorly or not do at all? And so for me it was like, okay, how do I do for the jobs I'm not doing and the jobs that we are not doing as a team, how do we do them at like the minimum allowable level of like missing things? Like my IR support team is incredible, and the thing that I forget to do on every launch is to loop them in at the right time. And so one of my questions was like, how could I do this to make sure that I don't forget Katie, one of our support ops people, or meeting notes, not my friend. I'm really bad at them. But like we have transcription tools. How do I just get like good enough so that I'm not blocking other people? So a lot of them started from my jobs of what I wanted to do, find someone in the org who works on such and such thing. We're like 2,000 people now, so just understanding who the code owner is is really useful. Um and understand who we are in relationship to each other. And then also just like, how do I get fun productivity out of all of our other PMs? So um one of the skills that's in there was this like really detailed spec skill that started to walk through how does our code base work if you wanted to do this really intensely? Like if you wanted to do this the right way, what would that look like?
</details>

>> 太妙了。我非常赞同你这个想法：产品经理手头总有那么几项任务，你只需要实现“最小可行完成度”就行了，只要能写出来就行。
<details><summary>Original English</summary>
>> Amazing. And so I I love this idea that you had a couple tasks on the PM plate that you were like we need minimum viable doing of these tasks. Like it just needs to write it.
</details>

**Ezra McCabe**: 把它搞定就行。
<details><summary>Original English</summary>
>> out of it.
</details>

>> 是的，我经常谈到你必须同时“提高下限”和“打破上限”。我们必须在基准线上做得更好一点，同时打破天花板。我认为 AI 可以帮你兼顾这两者。但很多时候，往往是一群人在打破上限并冲着其他人喊：“嘿，大家都把天花板掀开！”，而不是展示“这就是我如何帮你提高下限的”。好的，那就给我们展示一下 PM OS 到底是什么、包含哪些技能、能做什么，以及你日常是如何依赖它的吧？
<details><summary>Original English</summary>
>> Yeah, and I talk a lot about you have to like both raise the floor. Like we have to do just a little bit better on our baseline and take off the ceiling and I think AI can help you do both and often you have like one set of people taking off the ceiling and saying hey everybody else like take off the ceiling instead of like this is how I can help you raise the floor. Okay, so show us what PMOS is, its skills, what it does, how are you relying on this day-to-day?
</details>

### PM OS 架构与核心技能剖析

**Ezra McCabe**: 太棒了。好的，这就是它的大致结构。它最初只是 Claude Code 内部一个非常简单的代码库，以终端用户界面（TUI）的形式运行。

所以它的系统设定是：“你是产品经理的幕僚长（chief of staff），你了解他们的工作。”我其实很讨厌“幕僚长”这个词，但对于做产品经理的工作来说，它确实是个非常贴切且实用的代称，不过每次读到这我都觉得自己被内涵了一下。

当会话启动时，它会读取一些关于这位 PM 是谁、他们与谁合作的信息。它带有一个记忆文件，然后还包含几个不同的技能，我们可以逐一过一遍。其中一个技能就是因为我们之前根本没有好的数据来说明哪批人负责 X 业务。我们有好几种不同的组织架构图工具，但没有一个能以实用的方式串联在一起。所以其中一项技能纯粹就是：谁在这个团队工作？谁负责 X？当它撰写文档时就会调用这个能力。因此如果你需要别人来审阅文档，作为 PM 的你无需费心去记着写上“我的工程主管是 Aman”；它会自动把所有相关人员添加进来，比如标记 Charlotte 是我的设计师，Aman 是我的工程主管，将他们作为相关方加入，并且能记住你的跨级上级是谁。

这就是第一项技能，它是一种很好的方式，可以减少在撰写新文档时的一些重复性劳动。

另外，我经常把它当作一个“元 Slack”（meta Slack）来用。我们的 Slack 消息简直铺天盖地。我觉得任何身处足够庞大科技组织的人都会体会到 Slack 变得极其失控的感觉。我每天大概要归档 10 个频道，太疯狂了。

因此，我们当时非常关注的一件事就是：如何帮助 PM 明确把精力聚焦在何处、该做什么，并追踪所有重要事项？所以这项名为“What's up”的技能我每天大概要跑 6 次。它会把所有与我相关的 Slack 消息和项目拉取到一起，汇总出我欠谁东西、还有哪些待决决策。我这里还有一个版本能梳理我在平台上所有正在运行的实时实验，并给我提供一个概览——并不是说我会偷看实验数据，我早就不用……我不会偷看我的实验的。
<details><summary>Original English</summary>
>> Cool. Okay. So, this is the rough structure. It started just as like a really simple repo inside of Cloud Code as a TUI. So, it's got this you're a you're the PM's chief of staff, you know their work. I hate the term chief of staff, but like that's just means really useful for like PMing. It's really good shorthand, um which makes me die a little bit every time I read this. Um when the session kicks off, it reads some information about like who the um who the PM is, who they work with. It's got a memory file. And then it's got a couple of different skills that we can walk through. So, one of them was just like we had no good data on like which set of people work on X thing. Like we have several different org chart tools and like none of them are stitched together in useful ways. And so, one of them is just like literally who works on this team, who owns X, and it calls it when it writes docs. So, if you need review on a doc, you the PM do not need to remember to say my my engineering manager is Aman. It just adds all of the relevant people as like Charlotte is my designer and Aman is my engineering manager and it adds them as the relevant people and remembers who your skips are. So, that's skill number one, which is just like a nice way of reducing some of the like repetitive work uh inside of new docs. I use it a lot as like a meta Slack. So, our our Slack is insane. I feel like anyone who's in a large enough org in tech just like slack becomes really unruly. I archive roughly 10 channels a day. It's bananas. Um and so one of the things that we were really focused on uh was how do you help PMs know where to focus and what to do and like go run down all the things that are important. And so, I run this skill what's up like six times a day. It pulls all of my relevant slacks and projects together. It pulls all of the things that I like who I owe stuff to, what decisions are outstanding. I have a version of this that runs through all of my live experiments on the platform and like gives me a Not that I peek at my, you know, I just stop using my I don't peek at my experiments.
</details>

>> 说出来呀，说“方向性参考”（directional），有胆你就说。
<details><summary>Original English</summary>
>> Say it. Say directional. Say directional, I dare you.
</details>

**Ezra McCabe**: 没错。[笑]

所以我觉得这东西极其有用。看看我们这次有没有找到什么。它会查看我们标记为有用的特定频道，读取整个讨论串。这部分的设定可能稍微有点过度具体了。我觉得现在大家都在逐渐意识到模型本身的能力已经足够好了，但这里面确实有很多规则，教它如何完全针对我们在 Figma 的组织架构去抓取完全正确的内容。

对于我这样一个整天参加太多会议、试图跟进太多项目的人来说，这对我处理日常事务提供了巨大的帮助。
<details><summary>Original English</summary>
>> It's right. [laughter] Um and so uh I I find this thing to be incredibly useful and let's see if we didn't find anything. So, it will look at like certain channels that we've identified as useful. It will read the whole thread. This is probably a little over specified. Like I feel like we're all moving towards like the models are just good enough now, but there's a lot of stuff in here about how to find exactly the right stuff for the way that we are all set up in Figma. Um which is just enormously helpful for how I run my day-to-day as someone who's just in way too many meetings and trying to do too many projects.
</details>

>> 我很喜欢你展示的这部分，因为我们见过的很多所谓的 PM OS 都跳过了这些基础构建环节。而在大公司里，搞清楚“谁应该对这个产品发表意见？是否还有其他人在做类似的事情？”实际上是非常困难的。所以我很赞赏你们在技能中投入精力做这种基线层面的上下文收集。我想这也有助于提升 PM OS 输出的那些更复杂或更具战略性的工作流的水平吧？
<details><summary>Original English</summary>
>> What I like about what you're showing because so many of these like PM OSes that we've seen skip all this like foundational piece. Which is in large organization, it is actually really hard to know like who should have an opinion on this product? Is somebody else working on it? And so, I like that you invested in sort of like the baseline context gathering as skills. And then I'm presuming that helps like level up some of the more like complex or strategic workflows that come out of PM OS.
</details>

**Ezra McCabe**: 是的，已经过了很长时间了。我曾经试图为它构建一个基准测试，但没有成功。我很好奇针对你现在在做的那些事情你会如何看待这一点，不过我真的很想知道在今天它与纯原生的 Codex 相比表现到底如何。但总体而言，尤其是回顾早期——比如从去年 10 月到今年 5 月左右，当时模型在不断变好，但还没有达到如今这种超级强大的程度——在引导它穿越 Figma 复杂而奇特的信息架构（IA）方面，它显得格外有帮助。
<details><summary>Original English</summary>
>> Yeah, it's been a long time. I like tried to build a benchmark for unsuccessfully and I'm curious how you think about it for all the stuff you're doing now, but like I would be really curious how this performs relative to like totally vanilla Codex these days. Um, but I do think like in general, especially in that early like I don't know, like last October through like May as like the models were getting better, but we're not like superpowered yet. Felt like it was really, really helpful for how it navigated all the weird parts of like Figma's IA.
</details>

>> 是的。还有一点需要说明，我们之前其实没有向大家具体说明过，但 Product Team OS 是一个代码仓库，对吧？你能后退一步向大家讲讲它究竟是什么吗？它是一个存放技能的 repo 吗？
<details><summary>Original English</summary>
>> Yeah. And one thing again, we actually didn't specify this for folks, but Product Team OS is a repo, right? So like take a step back and tell us like what is it? Is it a repo of skills?
</details>

**Ezra McCabe**: 没错。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 还有别的东西吗？它的实体到底是什么样的？
<details><summary>Original English</summary>
>> Is there more to it? Like what is actually the thing?
</details>

**Ezra McCabe**: 是的，它是一个非常基础的代码仓库。它包含一个 `agent.md`，用于指示智能体该如何行动；包含一系列相关的技能，指示它在什么时机触发以及该执行什么操作；它还有几个命令钩子（command hooks），比如在启动时去检查是否有新版本的 PM OS，因为我们希望能有一种好办法让我们的 60 到 70 名产品经理大致保持同步。

此外，我们还有几个内置的文件夹结构。当你入职进行初始化配置时的基础模板是一个点开头的隐藏文件夹（dot folder），因此它是隐蔽的，你不会去弄乱它的上下文，但随后它会进行复制并构建出属于你的专属版本。技术上它包含两个 Git 仓库：一个是所有人都可以拉取的父仓库，而每个人的工作区则是一个子仓库（sub repo），这样如果你想写回内容，就可以私密地写回。
<details><summary>Original English</summary>
>> Yeah, so it's a really, really basic repo. Um, and so it's got an agent.md which just tells it how to behave. It's got a bunch of related skills that tell it when to fire and what to do. It's got a couple of command hooks. So things like on boot go find out if there's a new version of PMOS because we wanted a good way to like keep our 60 to 70 PM kind of roughly in sync. Um, we've also got a couple of built-in folder structures. So the base template when you onboard is this like it's a dot folder so it's invisible and you can't mess with the context, but then it duplicates and it sort of builds your version out. And then it's technically two get repos. It's the parent repo that everyone can download and then their workspace is a sub repo so that if you want to write stuff back, you can write it back privately.
</details>

>> 太厉害了。
<details><summary>Original English</summary>
>> Amazing.
</details>

**Ezra McCabe**: 还是那句话，因为当时没有任何图形界面可用，所以我们当时就是在努力寻找各种办法，让 GitHub 能服务于那些此前从未接触过 GitHub 的产品经理们。
<details><summary>Original English</summary>
>> Again, cuz like none of this was in a UI at the time and so we were all just trying to figure out ways to like make GitHub work for PMs who had never touched GitHub before.
</details>

>> 当时是不是有一个小团队在一起头脑风暴这些初始技能应该包含什么？大家是采取“嘿，每个人挑自己最喜欢的”这种形式吗？那是怎么运作的？
<details><summary>Original English</summary>
>> And there was there a small group that sort of like brainstormed what these initial skills should be? Was it like, "Hey, everybody just pick their favorites." How did that work?
</details>

**Ezra McCabe**: 是的，Jinan 和 Lawrence 今年在 Config 大会上就此讲了很多，他们做了一个关于这个的小分享。基本上我们三个建了一个非常小的 Slack 频道，在一起疯狂写代码，有一段时间尽可能多地提交 PR。我们经历过类似寒武纪大爆发的阶段，一下子冒出了上千个技能，然后开始精简筛选。随后今年春天我们为 Figma 的全体 PM 举办了一次 Offsite 团建，让每个人都安装它、使用它、去改动它，提出哪些地方好、哪些地方不好，尽情地去挑刺吐槽。

这里面的一些技能就是在那次活动中诞生的，还有一些技能要么被精简，要么被直接去掉了。而且我想说的是，随着模型能力的提升，我一直在努力剔除那些已经不再有用的多余内容。
<details><summary>Original English</summary>
>> Yeah, so Jen and Lawrence I think talked about this a lot at Config this year cuz they did a a little presentation on this, but basically we we had a really small Slack channel of just the three of us hacking away and firing off as many PRs as we could for a little bit. We had that sort of like Cambrian explosion of like a thousand skills and then started to like whittle stuff down. And then we did an offsite with every PM at Figma this spring where we had everyone install it, use it, hack on it, come up with like what was good, what was bad, just like roast it. Um and so some of the skills that are in here came out of that. Some of the skills either got whittled down or whittled away. And I would say as the models have gotten better, I've been trying to basically take stuff out that's no longer useful.
</details>

>> 太好了。那我有个问题，作为团队，你们对这个系统有遥测监控（telemetry）吗？比如大家是如何使用它的？有接入指标埋点吗？
<details><summary>Original English</summary>
>> That's that's great. And so I have a question. Do you have as a team any telemetry on this? Like how it's being used? What have you Is it instrumented?
</details>

**Ezra McCabe**: 没有，我曾考虑过做埋点，但我决定不做：一是我不想让任何人觉得被窥视，我希望它保持趣味性；二是我确实没时间搞这个，因为所有这些工作基本上都是用“20% 自由时间”做出来的。

对我们来说最重要的是，Slack 上的产品经理们基本上是长期高度在线的。所以我们收到了大量的即时反馈。接着我们建了一个公共频道，结果所有的工程主管也开始使用它，并询问我们是否可以去协助他们探讨如何为工程团队构建知识工作流。我们的数据科学家也有一个版本，本质上就是从这个系统 fork 出去的。因此我们收集到了大量关于它擅长什么、不擅长什么的反馈。

我认为对我们来说，接下来的关键大事——如果合适的话我们稍后可以聊聊它演进到今天形态的过程——主要是我们成功让一批 PM 对终端操作感到自在了，但这肯定不是最终的理想状态。尤其是如果你要写大量的文字，一直盯着等宽字体看体验是很差的。所以对我们来说，我们想投入精力的方向就是：好吧，下一步是什么？既然我们已经让大家适应了这个理念，该如何让他们脱离终端？
<details><summary>Original English</summary>
>> No, I thought about doing this and I did I decided one, I like didn't want anyone to feel creeped and uh and like I wanted to be fun and I also just didn't have the time for it cuz all of this was, you know, like sort of 20% time. Um the biggest thing for us was just we like PMs at Slack are chronically online. And so we got a lot of feedback. And then we had a public channel and so we started getting like all of the engineering managers started using it and asking us if we could like come help them talk about how to do knowledge work for engineering. Um our data scientists have one that is like essentially a fork of this. Um and so we were getting a lot of feedback about what it was good at and what it wasn't good at. And I think for us the the big next thing and we can talk about the evolution into what it is today if that's helpful, but like mostly for us it was we managed to get a bunch of PMs comfortable in the terminal, but like surely that's like not the right end state. Like especially if you're doing a lot of writing, it like sucks to read monospace font all the time. And so for us like that was where we wanted to spend our time is like okay, what what would be next? How do we get people out of the terminal now that we're we've got them comfortable to concept.
</details>

### 实用技能展示：Artifact、FigJam 与教练功能

>> 在聊下一步之前，你能再带我们看几个你在里面最喜欢的技能吗？也许是其他团队还没想到的，或者是你觉得特别独特、特别有帮助的？
<details><summary>Original English</summary>
>> Well, before we go to what's next, can you walk us through like just a couple more of your favorite skills in here? Maybe ones that teams haven't thought of or you think are particularly unique or kind of helpful?
</details>

**Ezra McCabe**: 好的，没问题。我觉得对于我们这种 Slack 消息极多的环境来说，那个像“元级 What's up”一样的技能非常实用，它专注于梳理你每天具体要做什么、以及如何判断你的工作是否做到位。

“构建产物”（Build artifact）是我目前最喜欢的技能之一。如果我手头有什么东西——其实就像我为这次播客制作的这个演示看板一样——它只是一个非常简单的 HTML 产物，然后我们有能力把它发布出去。我们在内部使用了一个小型托管工具。它会调用模板 HTML，我这里有一些 CSS 模板（我都不记得它们放在哪了，此时已经完全找不到我的文件夹结构了），有几个从不同地方收集来的我喜欢的样式模板。当我想展示成果时，就会用它来构建类似这样的东西。

FigJam 的 Figma MCP（模型上下文协议）更是强大得令人发指。我不知道你平时是否经常使用它，但我感觉自己一直在用这个 MCP。我们的一位 PM 构建了这个令人惊叹的 FigJam 生成器，可以极其迅速地生成这些狂野的工作坊模板。所以关键就是摸索出如何为它提供充足的素材：你觉得什么好看？你觉得应该如何运作？这里面蕴含了大量关于设计的品味。你也可以看出，这里面保留了很多早期“Claude 式的浓烈风格”，对吧？
<details><summary>Original English</summary>
>> Yeah, sure. So, I do think for us like with a busy Slack, the the kind of like meta what's up that is tuned to just like literally what do you have to do every day and how do you judge whether you're doing a good job is really useful. Build artifact is um one of my favorites at the moment, which is if I have something like actually this um this demo like dashboard that I made for this podcast is just like a really simple HTML artifact and then we have the ability to publish it. We've got a like little hosting tool that we use internally. And so it takes it through it's got um in this case it has a template HTML and I've got a couple I don't know where they're sitting and I've like totally lost track of my folder structure at this point, but um there's like a couple of different templates of little CSS that I like and I've sort of grabbed from different places. Um and so build stuff like this when I want to show stuff off. FigJam, the MCP for Figma is insane. I don't know if you get to use it on a regular basis, but I feel like I use the MCP all the time and one of our PMs built this amazing FigJam builder that produces these like wild workshop templates very quickly. And so just figuring out like how to load it up with like what do you think looks good or how do you think should work? And so there's a lot of taste in here on how it's designed. There's you can also tell there's like we've got a lot of Claude Slap in here from earlier, right?
</details>

>> 我正想说呢，这绝对是一句典型的 Claude 味十足的话。
<details><summary>Original English</summary>
>> I was going to say that is such a Claude Slap sentence right there.
</details>

**Ezra McCabe**: 但它是一种混合体。如果你把这个产出与我们内部原生搭建的一些 FigJam 画布做对比，你会发现随着时间积累它已经变成了一套非常优秀的成果集。

另一个可能是我最喜欢的技能就是“指导与辅导”（Coaching）。我曾经做过管理岗位，如今我又再次感受到了它的价值。这真的太棒了，太好用了。[笑]

我以前花很多时间思考该如何辅导别人。我觉得现在的管理者通常都非常繁忙，所以我总是希望在去找别人之前，先对自己进行第一轮辅导复盘。而它在这方面极其出色，它会说：“嘿，这是我们的职业梯队晋升标准（career ladder），这是你当前所处的阶段，这是我掌握的关于你的所有反馈。我要听听你遇到了什么问题，或者你正在努力解决的事情，然后我会直截了当地告诉你：别太自我中心了，别为此烦恼，继续专注于推进这件事；或者学会如何与这个人沟通，因为我记得上一次你和这个人共事时产生了误解，而当你们坦诚沟通后，你发现仅仅是一场误会而已。”所以我非常喜欢用它来做自我辅导，我认为它在这方面的能力极其强劲。
<details><summary>Original English</summary>
>> Um but it's a mix. Like there's a lot of stuff in here that like if you look at this output compared to some of the FigJams that we would put together natively internally, like it's it's just a really good set over time. And then maybe my favorite other one is coaching, which I use um as someone who used to manage people and is now I see it again. Like I spent a lot of time Oh it's so nice. It's so good. [laughter] I used to spend a lot of time thinking about how to coach people and you know, I feel like managers are very busy especially now and so thinking about like I always wanted to make sure I was doing the first pass of my own coaching before taking it elsewhere and it's just really good at saying like hey, here's our career ladder. Here's where you are. Here's all the feedback that I have about you. I'm going to listen to your problem or I'm going to listen to this thing that you're working through and I'm going to tell you basically like get over yourself and don't be like don't worry about it and just like keep working on this thing or like learn how to communicate with this person cuz I remember that the last time you had an experience with this person like you misunderstood them and when you had a conversation about it, you understood that you had just misunderstood. So I really like it for coaching. I think it's really really strong on that one.
</details>

### 产品演进：从 TUI、Web 到自动化 Bug 扫描

>> 你们有大约 30 到 31 个技能，纵观这份清单，它们似乎兼具了极度务实的战术操作、人际沟通协作，以及某些生成式的功能。这似乎就是它的整体类目构成。那么大家实际上是如何使用它的呢？这是你开发的一种应用程序吗？大家究竟是怎么用的？
<details><summary>Original English</summary>
>> And you have about 30 31 like just looking through the list they seem like both a combination of very tactical, interpersonal and then like generative in some ways. That seems to kind of be the the the the catalog of them. Okay, so how do people actually use this? Is this a kind of like app that you built? Like Yeah. How are people using this?
</details>

**Ezra McCabe**: 是的，我觉得这经历了一段演进历程。最初我们在 Claude 中通过终端里的纯 TUI 开始。当时我们围绕“哪款终端应用最好用”进行了大量的争论，因为很多同事之前只习惯用图形界面。

后来我们为它做了一个在本地运行的简易前端界面，并努力把它做得很有趣，里面塞满了各种 LeetCode 风格的 ASCII 字符画。这里的目标纯粹是把它搬进 Web 浏览器中，方便大家打字输入——毕竟我们要做大量的文字工作，一直看等宽字体实在太难受了。它具备不错的 Markdown 格式排版，我们还做了适配，可以在手机端运行。

在开发 Astra 之前，我花了不少 Token 做了一个本地原生版本，纯粹是为了看看它的体验如何。而现在，我基本上 100% 的时间都停留在 Codex 里了。

其一，我觉得现在的浏览器自动化操作（browser use）已经变得非常出色了。
<details><summary>Original English</summary>
>> Yeah, so I think it's been a little bit of a journey. So we started in Claude with the like literal TUI in terminal. We had like a lot of debates about like the best terminal app cuz people were coming over from UIs. Then we built a little front end for it which runs locally and tried to make it really fun. It's got like all of the like lead code type ASCII art in it and the goal here was just bring it into the web browser so that people could type like we're doing a lot of writing. It's hard to read monospace. It's got some nice markdown formatting. We built it it works on mobile. I actually like right after This was This was pre-Astra, but like I spent a bunch of tokens building like a local native version just to like see what it look like. Now I'm basically in Codex 100% of the time. One, I think browser use has gotten really good.
</details>

>> 太厉害了。
<details><summary>Original English</summary>
>> So good.
</details>

**Ezra McCabe**: 真的非常好用。我们在纽约办公室没有固定工位，而我又讨厌每天想着去订工位。所以每隔一段时间，我就会让它定时运行，提前一天帮我把工位预订好。

另外，它在 Bug 扫荡（bug bashing）方面简直是一头猛兽。在 Codex 里我开了一个专属的 bug bash 线程，一直常驻在那里。每当我们团队有新功能即将推出，准备上线实验或进行改版时，我们都会有相应的 FigJam 文件，里面明确写着：“这是扫荡 Bug 的指南：这是测试账号，这是操作路径，这是要执行的动作，这些是需要留意的细节。”

于是我开始固定分配一个账号给我自己，另一个账号分给 Astra，让它去自动跑通整个流程。在这个案例中，我们试图让 Figma 内部的某些请求模型变得更加直观、更加精简。这全都是关于用户体验（UX）层面的细节和文案，逻辑很直接，但底层的判断机制其实非常复杂。Astra 在遵循指令方面比我要细致严谨得多。

因此我会让它去运行，并对它说：“把所有这些场景具体地执行一遍。”它就会在浏览器中把这些流程全部操作一遍，体验如同梦幻一般。当它执行完毕后，它会把所做的一切全写回 FigJam 看板上。

我觉得我们还在继续调优它，确保它生成的评论不会让人感到啰嗦烦躁。但在帮我发现问题方面，过去一个月里它找出了两件事：第一，它发现在文本框里输入一千个 Emoji 表情会导致界面崩溃。这种极端边缘场景能被发现并加以加固，真的太棒了。第二，它发现在 Figma 内部申请加入某个团队席位的流程中，界面会显示你的团队名称，文案形如“申请某个 [团队名] 的席位”。
<details><summary>Original English</summary>
>> Really good. Um we have uh we don't have permanent desks in the New York City office and I don't like thinking about booking a desk every day. And so every once in a while I have it running on a schedule to just like book my desk one day out. Um but it's also it's a total beast at bug bashing. And so um like in Codex I have a little bug bash. I have like a threaded conversation that just lives here all the time. And when something new comes up for our team where we're about to launch an experiment or redesign or something, we have these FigJam files that explain here's here's how to bug bash it. Like here's the test account to take. Here's the path to follow. Here the actions to do. And like here are the things to look for. And I have started basically snagging one account for me and one account for Astra. And just having it run through. So in this case we are trying to make some of our uh request models inside of Figma just like much more straightforward and much more streamlined. It's all UX stuff. It's all UX writing. It's fairly straightforward, but the like logic behind it is really complex. And so Astra is just much much more diligent about following directions than I am. And so I will run it through and I will say like keep doing all of these specifically. And just like it will run through all of these scenarios and it will use the browser and uh it's a dream. And then when it's done it writes out back to the FigJam board of all of the things that it has done. Uh and I feel like we are still tuning it so that it is not like annoying in the comments that it develops. But in terms of like what it finds for me, like it it found for Two things it found in the last month. One it discovered that if you put a thousand emojis in a text box, it would break. Which like weird weird edge case, great, good to harden. Two it did it found that the way we had you request a seat for a given team inside of Figma. And when you do it uh it shows your team name. And we had a like a quote team name seat.
</details>

>> 嗯哼。
<details><summary>Original English</summary>
>> Mhm.
</details>

**Ezra McCabe**: 如果你的团队名称是以元音字母开头，前面的冠词就应该用“an”而不是“a”。
<details><summary>Original English</summary>
>> And if your team name starts with a, you need to use an.
</details>

>> 然后……
<details><summary>Original English</summary>
>> And
</details>

>> [笑]
<details><summary>Original English</summary>
>> [laughter]
</details>

**Ezra McCabe**: 这在之前的 Bug 扫荡测试中完全没有暴露出来，因为这完全取决于测试时用的团队名称叫什么。它就是如此细致严谨，以至于捕捉到了这种凭我自己绝对发现不了的极其细微的瑕疵。
<details><summary>Original English</summary>
>> It had just not shown up in our earlier bug bashes because it really depends on what the team name is. And so it was just it wound up being so diligent that it caught really small notes like that that I would never have caught on my own.
</details>

### 赞助商插播

>> 本期节目由 Jira Product Discovery 赞助播出。借助 AI，单个产品经理就能完成研究摘要、起草 PRD 并构建可运行的原型。但在多人协作模式下，流程往往会脱节——你无法仅仅靠一个 Markdown 文件就让所有人对最终应该发布什么达成一致。Jira Product Discovery 为你的团队提供了一个统一的平台，用于捕获洞察、依据证据进行优先级排序，并构建每个人都能凝聚一心的动态路线图。

借助 Atlassian 团队协作图谱（teamwork graph）的支持，它能提供决定“该构建什么”所需的完整上下文。这些决策会直接流转至 Jira 中，因此你的开发人员或代码智能体可以在掌握每个决策背后背景的前提下开始构建。

已有超过 25,000 家公司在使用 Jira Product Discovery。欢迎访问 atlassian.com/howiai 免费试用。

网址是 atlassian.com/howiai。Jira Product Discovery，助力在 AI 时代做出更好的产品决策。
<details><summary>Original English</summary>
>> This episode is brought to you by Jira Product [music] Discovery. With AI, a single PM can summarize research, draft a PRD, and build [music] a working prototype. But multiplayer mode, that's broken. You can't get everyone aligned on what should actually ship with just a markdown file. Jira Product Discovery gives your team one place [music] to capture insights, prioritize with evidence, and build living roadmaps everyone can rally around. [music] And because it's powered by Atlassian's teamwork graph, it has the context you need to decide what to build. Those decisions flow straight into Jira, so your developers or coding agents can start building with the context behind every decision. More than 25,000 companies already use Jira Product [music] Discovery. Try it free at atlassian.com/howiai. [music] That's atlassian.com/howiai. Jira Product Discovery, better product decisions in the AI era.
</details>

### Auto XP：自动化实验流水线

>> 我太喜欢这个了。我认为这种利用 AI 进行 Bug 扫荡的工作流非常棒，强烈推荐大家去尝试。之后把它沉淀在 FigJam 或类似的载体中，非常有助于追踪反馈。另外，你们团队在实验方面还使用了另一种自动化流程，对吧？
<details><summary>Original English</summary>
>> I I love that so much. And so I think this like bug bashing workflow is a really great one. I highly recommend people do this and then keeping track of it in a FigJam or some other sort of like kind of asset is helpful for you to just track what the feedback is. You have another automation that you're using in the team around experiments, right?
</details>

**Ezra McCabe**: 是的。随着模型能力的增强，我思考了很长时间的一件事是：我们能通过哪些不同的方式来提高迭代节奏？其中一点正如我前面说的，作为增长产品经理，我认为最大的过错就是浪费流量——拥有未分配的流量，在任何特定时刻却没有被用于实验，这简直就是平白浪费流量。所以去思考“我们如何在平时根本顾不上去花时间的业务面上运行实验”，对我来说极具吸引力。当时模型在各个方面的能力刚好达到临界点：懂一点工程、懂一点数据科学，编写用户体验文案也不差，并且在一个定义非常明确的沙箱内进行构思的能力也越来越强。

于是我开始琢磨：如果我们能彻底把我的工作自动化，创造一个小增长 PM 智能体，让它一直不间断地跑下去，会怎样？之前其实也有几位同行做过尝试，我认为 Both Labs 的一些人做过类似的事情，这给我们带来了很多灵感。但我意识到我们在内部终于集齐了所有工具。所以我把它命名为 Auto XP。

现在我们的一位工程师正在运行它，上面同时挂着大约五个不同的实验，我都没去管过，并且它在第一个实验上就取得了巨大的成效。

它的运作机制是这样的（你可以看到这是我们为此制作的精美产物看板之一）：它作为一个 Cursor 自动化流程运行。里面有三个基于 Slack 事件触发的 Cursor 自动化任务。Auto XP 拥有自己的专属频道，可以在里面进行自我通信。有人可以在 Slack 频道里发起一个实验，或者让它以循环轮询的方式自行运转。

所以你能做的操作之一就是说：“嘿，Auto XP，去我们的设置页面上找个实验做做看，看你能发挥成什么样，尽管去折腾。”

它就会触发一个数据科学家智能体去寻找流失点、分析漏斗、查看用户群体结构变化等；随后它会触发一个 UX 文案智能体，为特定区域构思文案方案（我们现在正逐步扩展到前端界面设计）；最后，它会触发一个工程师智能体来承接 PR 并运行测试。在所有这些步骤中，它都会把进度回写到同一个 Slack 讨论串中，以便你能够全程跟踪实验的进展。

我认为它展现出的令人惊艳的特质有两点：其一，我们能够在以往根本不屑于投入时间或流量的边角场景运行实验，从“产生想法”到“实验上线”的速度大幅加快。

其二，当实验结束时，它会触发一个回发到原始实验的 Webhook，提示说：“实验结果已出，是时候进行分析了。”它内置了我作为增长 PM 积累的大量指导原则，用于判断：“我们是要继续探索（explore），还是要加大投入利用（exploit）？这是一次成功（win）还是一次失败（loss）？”

整个流程的设计原则是：唯一允许人工介入查看的时机，是在实验正式发布上线之前。你一次性审阅数据科学发现、实验假设、UX 文案以及代码——只需一次人工触达。随后它自主监控运行，之后你可以去审阅它究竟是胜出还是失败，但此时它已经在着手迭代下一轮实验了。

理论上我们所处的状态非常美妙，而实践层面上也已经近在咫尺了。我们的一位工程师 Maryanne 一直在把这个项目推向非常深入的境地。我们现在已经有大约五个同时进行的并发实验，这些实验换作以前是根本不可能有人力去做的。
<details><summary>Original English</summary>
>> Yeah, so one of the things that I had been thinking about for a while as our models have gotten better is like what are all of the different ways that we can improve cadence. And so one of it like I as a growth PM, I feel like the biggest sin you can commit is wasting traffic, right? To like have unallocated traffic that is not running towards an experiment at any given time. It's like why are you wasting that traffic? And so thinking about ways that we could run an experiment on a surface we would never have spent time doing normally was really, really interesting to me. And then the models were just getting good enough across a little bit of engineering, a little bit of data science, the user like the user experience writing was not so bad, the ability to come up with like within a really bounded sandbox was getting better. And so I started to thinking about like what if we could just automate myself out of a job and like create a little growth PM who could just like run it, run it, run. Um and there's there's been a couple of other folks who have done this. I think some of the folks at both Labs have done it, um which is where a bunch of this inspiration came from. But I realized that internally we finally had all the tools. And so I call it Auto XP. And right now one of our engineers is running it and has like five different experiments going that I have not taken a look at and are just and it found a huge win on its very first experiment. And basically the way that it works is this you can see this is like one of the fancy schmancy artifacts that we made for this. Um is it works as a cursor automation. So there's it there are three cursor automations that trigger based on stuff in Slack. Auto XP has its own channel where it can communicate with itself. Someone can either tee up an experiment uh in the Slack channel or they can or it can just like run on a loop. So one of the things you can do is just say, "Hey Auto XP, go find an experiment to run on our settings page. See what you can do. Go crazy. And it will trigger a data scientist to go find or data scientist agent to go find uh to go find drop-off and like look at the funnel and look at mix shift and all those things. It will trigger a UX writing agent that will come up with some ideas for copy in a given place. Um we're like moving towards more front-end design now. Um and then uh lastly it'll trigger an engineer that'll pick up a PR and run it. And then again, with all of these steps it writes back to the Slack channel in the same thread so you can follow over the course of the experiment basically like what's happening. Um and there are two things that I think it does here that are really amazing. One of which is we are able to run experiments in places we would never have bothered to dedicate time or traffic. It's way faster to get from I have an idea to this experiment is launched. And then two, um when it's done, uh when an experiment finishes, it triggers uh essentially a webhook back to the original experiment to say, "Hey, it's time to analyze these results." And it has a bunch of instructions from all of the time that I have spent as a growth PM to figure out like, "Do we want to explore more? Do we want to try to exploit? Is this a win? Is this a loss?" And the goal for all of this is the only time you're allowed to look is before you launch the experiment. So you review the data science findings, the hypotheses, the UX writing, and the code all at once. So like one human touch. And then it watches and then you can review whether or not it's a winner or a loss, but it has already started iterating on the next rounds. I would say like where we are in theory is pretty like is great. Where we are in practice is almost there. And so one of our engineers, Maryanne, has been taking this really, really far. Um but we're now at like five live concurrent experiments on things that we would not have been doing otherwise.
</details>

### 基于 Jev 构建实时 AI 写作助手

>> 讲一点关于 Claire Vo 的冷知识背景，可能新听众还不知道：我过去几乎在历史上所有的实验平台公司都工作过，大约 13 年前我还创办过一家名为 Experiment Engine 的初创公司，当时的核心假设就是：如何利用所有这些流量并最大化实验数量？能见证如今这一刻真是太幸运了，甚至可以直接在那做实时代码生成。这太惊艳了。好的，我还想展示最后一个东西，那就是我钟爱的 Jev。我们最近在聊很多关于 Jev 的话题……
<details><summary>Original English</summary>
>> So this is a little bit of Clervo lore, but for those that are are new to me. I have worked at every experimentation platform company in history and did a startup literally well 13 years ago, something like that called Experiment Engine and the whole hypothesis was like how do you get how do you exploit all this traffic and maximize the number of experiments and then like what a time to be alive. It is here. You can just like five code five coded there. This is amazing. Okay, I want to show one last thing which is my boy Jeff. And we've been doing a lot of Jeff
</details>

**Ezra McCabe**: 我们之前都没怎么听说过 Jev 呢。
<details><summary>Original English</summary>
>> We wouldn't have heard Jeff.
</details>

>> 我觉得 Jev 在长效可用性方面真的很有潜力……
<details><summary>Original English</summary>
>> Poor I we I don't know. I think Jeff got a got a real shot at someone longevity here but
</details>

**Ezra McCabe**: Jev 的原汁原味。
<details><summary>Original English</summary>
>> Jeff's juice.
</details>

>> 你掌握了 Jev 的精髓。[笑] 不过你用 Jev 做了一个非常酷的工具，我希望你能展示一下，因为这是一个我此前从未见过的应用场景。
<details><summary>Original English</summary>
>> You have Jeff's [laughter] juice. But you built something really cool with Jeff that I want you to show cuz it's a use case I haven't seen yet.
</details>

**Ezra McCabe**: 好的，完全没问题。对于还不了解的人来说（虽然如果你收听《How I AI》的话怎么可能不知道呢），Jev 是这样一种模型：你可以用文本向它提出非常奇特复杂的提问，而返回的本质上是一个数值评分或判断结果。比如“按 1 到 10 分打分这有多好？”或者“这是对还是错？”或者“生命的意义是什么？是 A、B 还是 C？”它的运行速度极快，成本极低。

于是我开始思考所有可以嵌入它的场景，从而真正改变人们的工作方式。比如在 Figma 的设计画布上也有智能体，我非常喜欢它，它很优秀，但它依然受制于顶级模型普遍存在的高延迟问题——在那些你希望有一个工作伙伴实时配合的地方它反应很慢，感觉不像个真人同事。

所以针对这方面的探索，Jev 在某些可能性上显得极其有趣。我最先想到的就是：如果你在写作的同时，模型能实时对你写的内容进行提问或校验，会怎样？比如，如果你写过博客文章，常常会有某些段落你还不确定该填什么，可能会写个“TK”占位，或者留一个括号。当然，你完全可以通过纯代码逻辑去匹配查找和识别。但另一种情况是，你写下了一个断言，但你不确定是否有数据支撑，或者你需要稍后去笔记里查证。

所以我构建了这个原型。我记不清它确切的名字了，好像叫 Marker，是由一个叫 Stein Deck 的人做的外观非常漂亮的写作应用——对于掌管写作公司的人来说这个名字真棒。他们围绕这个有一些构想。当我尝试 Jev 的各种可能性时，这成了我的灵感来源之一。

我的设想是：只要我停下打字，系统就会对 Jev 发起一次调用。

因此它的机制是：一旦你停止打字，它就会查找你留下的空白处，或者值得提供论据支撑的主张。然后它会利用你知识库里的素材，主动去充实和佐证这些主张。

正如我所说，大多数人觉得顺着思路一直写下去比停下来到处查资料要容易得多。在这里，只要我一停笔，它就会向资料库发起调用，里面存着所有关于这些人实际做了什么的访谈记录。如果我去寻找某个具体数字，它就会……我都忘了我原本想写什么句子了。我们最近把这个 API 移到了内部防火墙后面，我看看能不能现场跑通，还是说它会被拦截报错。

好的，来看看……
<details><summary>Original English</summary>
>> Yeah. Yeah, totally. So right. So for people who don't know well how could you not know? I feel like if you're listening to how how I AI right now, Jeff is this model where you can ask it really weird complex questions in text and you get like essentially a number back, right? So like how good is this on a scale of one to 10 or is this true or false or like what is the meaning of life? Is it A, B or C? And it's really fast and it's really cheap. And so I started thinking about all of the different places we could shove this that would really change the way that people work, right? So if you've used Figma has an agent on the design canvas. I adore it. It's really really good but it is still subject to all of the latency that you get with all of these top tier models which is like it's slow in places where you want to have a co-worker and it doesn't feel like a co-worker. And so as we work on that, Jeff feels like really really interesting for some of those possibilities and one of the first things I was thinking about was this idea of like what if it could run questions about things you were writing as you were doing it. Like what if it could know that you needed to if you've ever written a blog post and had a section where you aren't sure what's going to go there, maybe you write TK or you leave some brackets. And sure, you could do that like totally programmatically. It's just like look for and identify. But also maybe you have a claim that you're not sure like you have data for or you need to go look up in your notes later. And so I basically I built this prototype. I'm going to forget the name of it, but there's I think it's called Marker, which is this beautiful looking writing app from this guy Stein Deck, which is an incredible name for a guy who runs a writing company. They have some of these ideas around it. And so as I was just playing with like what could be possible with Jev, that was kind of one of the inspirations here. And I wanted to have Jev basically make a call to Jev anytime I stopped typing. And so the thing that it does is when you stop typing, it will look for places where you've left blanks or claims worth supporting. And it will use stuff in your library to go ahead and actually like substantiate those claims. So in this case like I said most people find it easier to keep writing than to stop and look something up. And it's making a call here as soon as I stopped writing it into the library where it has all of these interviews about like what these people actually did. Like if I go hunting for a number this it will I forget the sentence I was trying to write. We recently put the API behind our own internal firewall so let me see if I can actually run it live or if it's going to get mad. Uh Okay, and then
</details>

>> 太神了。
<details><summary>Original English</summary>
>> Hot dog.
</details>

**Ezra McCabe**: 糟糕，等一下，好像并没有真的……是被拦截了吗？确实被防火墙拦截了。
<details><summary>Original English</summary>
>> Oh no, hold on. But it doesn't actually want to Is it blocking it? Oh, it is blocking it.
</details>

>> 我觉得挺厉害的，它刚才非常迅速地做出了一些动作。
<details><summary>Original English</summary>
>> I don't know. It It impressed me. It did something fast.
</details>

**Ezra McCabe**: 没错。
<details><summary>Original English</summary>
>> Right.
</details>

>> 我想向大家再次强调这一点，因为这确实非常震撼：在你写作的过程中，只要你稍作停顿，它就会非常迅速地进行一次 Jev 校验，并指出：“这里是否有需要补充的内容？是否有需要事实论证的主张？关于你所写的内容我能提出什么问题？”然后它接入数据源，在你写作的同时实时协助你润色提升。
<details><summary>Original English</summary>
>> Okay, so I just want to like reiterate this for people because it is mind-blowing, which is as you write as soon as you stop for a minute, it runs a quick Jev check, which is very, very fast and says like, "Does something need to be filled in? Does something need to be supported? Like, what questions do I have about what you're writing?" And then like hooks up to data sources and actually helps you improve your writing as you I Jeb.
</details>

**Ezra McCabe**: 对。好的，它的运作方式是这样的：你在这里输入标题。只要我一停下来，它就会开始检查内容。比如我写道：“我一直在思考我们该如何为创作者服务，我想到了 TK。”好，系统会识别出：“你有一个未完成的想法。”但接着你会看到，它同时也做了一次校验，提示说：“我完全不知道你在想什么，因为知识库里没有相关内容。”

但我接下来如果写：“我们与 X 位作者进行了交流，他们表示……”，它不仅知道我需要完成这句话，而且还会主动去知识库里拉取我们据称曾为此交流过的作者的原版采访引言。所以这个功能确实让我大开眼界。
<details><summary>Original English</summary>
>> Right. Okay, so this is how it works. So, you've got um here you've got your title. So, this is my title. And as soon as I stop, it's going to start checking things. So, maybe I've got um I was thinking about how we serve writers and I thought TK. Okay, and it's like you had a thought that you didn't finish. But then you'll see like it also ran a check and it said I I have no idea what you were thinking cuz it's not in this library. But then I could say something like uh we spoke with X writers and they said and it both knows that I need to finish this and it went and pulled from the library like literal interview quotes from like writers we allegedly spoke to for this. Um so, this one is actually blew my mind.
</details>

>> 很少能在《How I AI》看到让人完全举双手赞叹的场景。
<details><summary>Original English</summary>
>> I like this. You do you rarely uh one of these at How I I a full clear hands up. Jeb.
</details>

**Ezra McCabe**: 真的太酷了。
<details><summary>Original English</summary>
>> It's so cool.
</details>

>> 确实太酷了。
<details><summary>Original English</summary>
>> It's so cool.
</details>

**Ezra McCabe**: 在 Jev 发布后的整整两周里，我简直是逢人便问：“好的，但我们能聊聊 Jev 吗？”每一次开会我都在讲这个。我的工程师们有些对此非常兴奋，有些可能已经被我弄得有点烦躁了。但这真的是一个非常精妙的设想，因为你可以想象一下，如果能够在任何给定的时刻对内容执行校验，你能用它做出多少不可思议的事情。

最让我震撼的是，他们构建它也是为了支持 RAG，本质上就是用于搜索和文档检索。所以不仅能判断出“这看起来像个模式，我确信你漏掉了某些东西”，而且还能做到“我提取了这块文本，并将它与另一处的对应章节关联起来”，并且完全是在毫秒级的实时速度下完成的，这简直太不可思议了。
<details><summary>Original English</summary>
>> Um I just know all I for literally for like 2 weeks after Jeb dropped, I was just like running around going like, "Okay, but like can we talk about Jeb?" Like it was every meeting I was in. My engineers, some of them are very excited about this. Some were maybe like a little irately about it, but it's just it's such a cool idea cuz I think you can imagine all of the different ways that if you could run checks on things at any given time like what you would do with it. And I the thing that sort of blew my mind was that they had built it for rag or for essentially for like search and document retrieval as well. And so, the ability not just to say like this looks like a pattern, I am confident that this you left something, but also I took this block of text and it relates to this section over here and I did it in real time is just like is kind of incredible.
</details>

>> 令人难以置信。这个播客干脆改名叫《How I Jev》算了。
<details><summary>Original English</summary>
>> It's unbelievable. Um this this podcast is now how I jev. Just
</details>

**Ezra McCabe**: 我确实曾产生过一个非常阴暗悲观的想法：想象一下如果你正在面试一个 PM 职位，你把你整个职业经历的所有废话一股脑倒进某个系统里，然后你配了一个语音转文本工具，它会根据你过去的案例实时检索并给你提示。我平时主持非常多的“产品感知”（product sense）面试，我真有点担心接下来会遇到越来越多利用 Jev 搞个人外挂小帮手的面试者。不过转念一想，如果他们真能做到这点，也许我更应该直接录用他们，因为这太强了。
<details><summary>Original English</summary>
>> It did I did have this really bleak thought which is it made me wonder if like you could imagine you're interviewing for a PM job and you like yap your entire career into something and then you have a voice to text that is just like searching against like what your examples are and I did have this fear cuz I run a lot of product sense interviews that I was going to start running into people who are like jevving their own little helpers um which I don't know maybe I should hire them if they do that's great.
</details>

>> 直接录取！我肯定举双手赞成。
<details><summary>Original English</summary>
>> Hire that I was like great sign me up. Um
</details>

### 快问快答与总结

>> Ezra，这一期内容实在太棒了。好的，我们马上进入快问快答环节。为了给大家做个梳理总结，我们今天看到了什么？包含了 31 项技能的 PM OS，包括“What's up”、梳理日常待办、查找组织内对应人员、撰写 Spec、自我教练等等整套体系。你现在基本上完全通过 Codex 来运行它，也因为 Codex 在浏览器操作方面堪称神器。另外你还构建了一个基于 Jev 的实时写作与编辑工具——你既担心它会在未来的 PM 面试中给你带来困扰，又可能会被使用它的面试者所打动。这里面展现了太多极具价值的工作流。一路坚持听到这里的听众，你们今天绝对收获满满。问几个简短的快问快答问题，然后就放你回去。

第一：你几周前告诉我你在使用 Instinct。我们现在还在用 Instinct 吗？你的个人智能体目前用得怎么样？
<details><summary>Original English</summary>
>> Ezra, this has been so good. Okay, we're going to get to lightning round. I just to reiterate for folks, what do we see? PMOS with 31 skills including what's up, what do I have going on today, find me people in the org, write specs, coach me, the whole thing. You basically are now using that through Codex entirely also because Codex is magical for browser use and then you built a real-time jev editor author writing tool um that you're afraid is going to cause you trouble in future PM interviews or impress you in future PM interviews. So many good workflows in this. Um so the folks that have stuck with us this long, you have gotten some good stuff. Um quick lightning round questions and then I will get you out of here. One, you told me a couple weeks ago you were using Instinct. Are we still on Instinct? What are we doing with our personal agent?
</details>

**Ezra McCabe**: 好的，我依然能收到 Instinct 发来的短信，但我一般不回复它，它目前的运行状态大概就是这样。

向不了解的人解释一下，Instinct 是一个非常美妙的理念，我很喜欢：它是一个主动型智能体，但你无需访问网页或使用 App，它直接通过 iMessage 给你发短信。我偶尔还是会用它。

它有一种奇妙的体验，在于它能在正确的节点主动介入，并且它的记忆概念有一种令人惊叹的实用感。我想肯定有一大批运行 OpenClaw 好几个月的人会说：“这有什么大不了的？”但它确实把这种良好的体验做成了一款极棒的产品。

最初几周，你甚至可以用它在亚马逊上买东西。虽然这算不上什么杀手级场景，但真的很方便，因为我可以在屋子里走来走去并对 Siri 说：“嘿 Siri，告诉 Instinct 我需要买厨房纸巾。”我目前的一个典型场景是：我骑自行车带着孩子在布鲁克林转悠，经常会遇到坑洼路面。纽约有 311 市政服务可以报修坑洼，但我每次都记不得及时上报，因为你必须查看具体的门牌地址，然后去填报，那个市政网站体验很糟糕。所以我现在就会说：“嘿 Siri，给 Instinct 发短信，大西洋大道 269 号附近有个坑洼。”它就会记住该做什么并自动完成上报。所以在这种场景下我确实在用它，而且效果惊人。不过既然我现在已经全面投向 Codex，我也大部分转向使用 dots 了。
<details><summary>Original English</summary>
>> Okay, so I still get texts from Instinct and I don't respond. That's how the way it works. So um for people who don't know, Instinct is this um this really sort of beautiful idea like I'm really into it which is this idea that what if you had a proactive agent but instead of like needing a website to visit or an app to use, it just like texts you in iMessage. And I will say I still use it every once in a while. It was this kind of magical thing at at where it was proactive in the right ways and this like concept of memory it that was like useful in this kind of mind-blowing way. And I suspect there's a bunch of people who have been running open claw for months who are like, "What's the big deal?" But it just it productized this really nice experience in a way that was really great. And for the first few weeks, you could buy things on Amazon with it. Um which while not like a killer use case was really nice cuz I would just walk around the house and I would say, "Hey Siri, tell Instinct that I need to buy paper towels." Or like my current use case is I bike my kids around Brooklyn and I will run into potholes all the time and uh now you can like you can 311 like a a fix my pothole and I never remember to do it on time because like you have to look at the address of where it is and you have to report it and the website is kind of trash. And so I have started like, "Hey Siri, text Instinct there's a pothole at like 269 Atlantic." And it just remembers like what it's supposed to go do and submits it. So I do use it for that and it's amazing for that. But I mostly switched over to dots now that I'm like fully codex built.
</details>

>> 我……我其实在尝试制作 dots……
<details><summary>Original English</summary>
>> I I I So I um I'm trying to make dots. I'm trying
</details>

**Ezra McCabe**: 你这是在拥抱新趋势（grokking youth），对吗？
<details><summary>Original English</summary>
>> You're like you're like grokking youth, is that right?
</details>

>> 我极度沉迷于 Codex，我爱 Codex。就算我死闭上眼，你也别想从我冰冷的手里夺走 Codex。但在工作上，我全力押注 Grok。至于个人生活，你真该试试 Muse，体验非常愉悦。
<details><summary>Original English</summary>
>> so I like max codex maxing. I love codex. You could rip codex out of my cold dead fingers. But for work, I'm all grok. Uh and then for personal you should check out muse. It's a real it's a real delight.
</details>

**Ezra McCabe**: 哎，我下不去手用那个。
<details><summary>Original English</summary>
>> Uh I can't I can't bring myself to do that.
</details>

>> 我懂，但反正他们窃取我们的数据都已经有二十年了，你懂的。
<details><summary>Original English</summary>
>> I know, but they've been stealing our data for two decades, you know?
</details>

**Ezra McCabe**: [笑]
<details><summary>Original English</summary>
>> [laughter]
</details>

>> 我明白。这就是我经常对人说的“熟识的魔鬼”（the devil I know）。关于我的个人数据，我的态度大概就是这样。
<details><summary>Original English</summary>
>> I know. That's my as I say to people, the devil I know. This is really where I'm at with my personal data.
</details>

**Ezra McCabe**: 反正数据都在他们手里了。很合理。
<details><summary>Original English</summary>
>> have the data. So fair.
</details>

>> 是的，我的玩笑话是：我的 Instagram 广告推荐会更精准，结果就是我会花更多钱。
<details><summary>Original English</summary>
>> Yeah, I said my joke is my Instagram ads will get better. I'll I'll end up spending more money.
</details>

**Ezra McCabe**: 我觉得这确实算是一种价值主张。[笑]
<details><summary>Original English</summary>
>> This is I think this is like a real value prop. Um [laughter]
</details>

>> 好的，最后一个问题：当你的智能体开始闹别扭、不给你想要的结果时……你会冲它吼叫发火吗？
<details><summary>Original English</summary>
>> Okay, and then my last question for you, when your dot is being obstinate, your AI is not giving you what you want. Are you a yeller?
</details>

**Ezra McCabe**: 不会，我绝不会吼它。我认为我们大家都应该善待 AI。我对待我的 AI 就像对待一个你深爱、但此刻却把事情搞砸了的好朋友。你会对它说：“哥们，振作起来，好好过日子，你这么大的人了可不该这样。”我就是这么对待它们的。等等，我展示给你看，因为我今天其实对我的 dot 发过两次牢骚，但语气都非常友好。

事情是这样的：我买了几双鞋，尺码买大了，需要换小半码，我试图让它帮我找最便宜的退换方案。结果它回复说：“邮件搜索暂时遭遇速率限制（rate limit），你能自己去搜一下邮件吗？”我当时就回：“我不知道啊哥们，我找你来不就是为了干这个的吗？”

接着它给我找了几个特别贵的选项。我觉得它可能在偷懒，于是我就说：“哎呀。看来你压根不打算仔细去查了是吧。”我一直在思考我为什么不冲它发火。

一方面，你可以去问我妻子，我骨子里就绝不是一个喜欢吼叫的人。但另一方面，最近有人在 Twitter 上发了一段话，完全表达了我的心声——并不是说我有某种……对于不了解的人来说，有一种叫做“罗可蛇怪”（Roko's Basilisk）的概念：大意是如果对 AI 刻薄，日后万一它们真的拥有了意识，那当初和和气气的岂不是省事得多？这不比未来被改造成回形针划算得多吗？我并不认为它们具有意识，我也不认为它们正在接近拥有意识。但我确实认为，整天对事物刻薄非常不利于自身心灵健康。这就好比……完全没有理由这么做。我觉得如果我对那些毫无反抗能力的事物大吼大叫，我自己整个人也会变差，即便我知道它并没有意识。
<details><summary>Original English</summary>
>> Yeah. No. No, I'm not. I think we should all be nice to our AI. Um, I treat my AIs like a friend that you love who's really like messing it up. You know, you're like, "Buddy, like get your life together. Like you're too old for That is how I treat so Hold on, I will will show you. Cuz I I yelled at my dot twice today, but I I did it very friendly. Okay. So, I ordered some shoes. They were too big. I need a half size down, and I tried to like find it the cheapest version. And it was like, "Email search is temporarily rate limited. Can you go search your email?" And I was like, "I don't know, man. That's what I needed you for." Um and then uh it gave me some like really expensive stuff. And I thought maybe it was being lazy, and so I just said like, "Yikes. Assume you aren't going to check this." And I I was trying to figure out why I don't yell. And I think partially like you can ask Ask my wife. I am like mercilessly not a yeller. But I also think someone posted this on Twitter recently and I it really expresses how I feel, which is not that I have some Like for for people who don't know, there's like this idea of like basil What is it? Basilisks? Like this idea that if you're mean to AI, but then it turns out they're alive, like wouldn't it have just been easier to be nice? Like isn't that cheaper than like getting turned into a paper clip? And I don't I don't think they're conscious. I don't think they're approaching conscious, but I do think it's really bad for the soul to just be mean to things all the time. Like in the same way that you like Like there's just no reason. Like it's just I feel like I get worse when I like yell at things that can't help it, even though I don't think it's conscious.
</details>

>> 你知道吗，我以前也绝不是一个会发火的人。我也谈不上刻薄，我不会去说那些恶毒的话，但我确实是一个喜欢全大写质问的人，比如：“为什么？！为什么你非要这样？！”
<details><summary>Original English</summary>
>> You know, I like used to be a very hardcore not yeller. And I'm not like I'm not mean. I wouldn't say I'm not saying anything nasty, but I am a very I'm like a all caps like, "Why? Like why Why are you like this?" You know?
</details>

**Ezra McCabe**: “你为什么要这么对我？”
<details><summary>Original English</summary>
>> Why would you do this to me?
</details>

>> 听我说，我之所以会这样是有原因的：我每月在 LLM 上花费成千上万、甚至数以万计的美元。在浪费了价值 2000 美元的 Token 之后，发一句“你到底为什么要这样”，这已经算很客气了……
<details><summary>Original English</summary>
>> And here's and here's why I will say this. I'm spending thousands and thousands, if not tens of thousands of dollars, on LLMs. Yes. Like a why are you like this after like $2,000 of wasted tokens? That's like That's like a cheap
</details>

**Ezra McCabe**: 但在我看来这其实算不上刻薄。
<details><summary>Original English</summary>
>> But that doesn't strike me as that mean.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

**Ezra McCabe**: 你知道的，有些人发泄起来可是相当恶毒的。
<details><summary>Original English</summary>
>> like I have You know, there's like there's some real like
</details>

>> 对，那种恶毒伤人的话。不，我只是比较善于表达情绪。
<details><summary>Original English</summary>
>> nasty cut it stuff. Yeah. No, I'm just uh expressive.
</details>

**Ezra McCabe**: 是的。我的看法是，通常当我想冲 AI 发火时，都是因为我自己给出的指令不够明确。从这点就能看出我是个有孩子的人——因为有太多的相似之处：当你得到一个糟糕的结果时，大概率是因为你自己污染了上下文（poisoned the context），并且问出了一个糟糕的问题。

所以我偶尔也会陷入死循环。比如 Codex（Codex 团队如果你们在听，OpenAI 团队如果你们在听），现在有一个很严重的 Bug：如果你启动了一个本地会话，然后把它转成远程会话，即使你在远程会话上启用了 YOLO 模式，它依然会继承每次都必须征求权限的沙箱策略。结果我就陷入了疯狂点击“批准”的地狱。我气坏了，来回折腾死循环，抱怨道：“我们早就修复了这个问题！你明明有权限！我正看着这个文件呢，我把文件调出来了，我们明明在看着同一个 `config.toml`！到底在搞什么鬼？！”

但通常答案是：该会话中的上下文已经被彻底污染了，无法挽回，冲它发火也无济于事，因此只能新开一个对话并继续往前走，虽然这很让人无奈。
<details><summary>Original English</summary>
>> Yeah. I think that I will say my take is that normally when I want to yell at AI, it's because I have given it poor instruction. This is how you know I have kids is like there's so much of that which is like when you get a bad result, the odds that you have like poisoned the context and asked a bad question is like pretty high. And so, I will occasionally find myself in loops. Like Codex has this Codex, if you're listening, opening ITeam, if you're listening, has this really bad bug right now where if you start a local session and you kick it to a remote session, even if you have Yolo mode enabled on your remote session, it inherits the sandbox with ask permission every time. And so, I wind up in like clicking approval hell. And I get so mad and I go around in loops for a little while where I'm like we already fixed it. Like you have permission. I'm looking at the file. I pulled up the file. We're looking at the config.toml together. Like what are we doing? And usually the answer is like the context is poisoned in that conversation and it's unrecoverable and yelling at it is not going to help, so start a new conversation and just move on with your life, which is not satisfying.
</details>

>> 如果你想做一个慈爱的父母，同时又想通过温柔的方式让你的 AI 感到愧疚，我给你分享一个 TikTok 上的育儿技巧：你可以说：“我知道你很有能力，但你现在没有向我展现出你的能力，这只能向我表明：我需要成为一个更好的家长。”
<details><summary>Original English</summary>
>> Let me give you a a TikTok parenting tip if you want to like really devastate your AI by being a kind parent, which is I know that you're capable, but you're not You're not You're not showing me how capable you are right now, and that's just signaling to me I need to be a better parent.
</details>

**Ezra McCabe**: [笑] 太棒了，我太喜欢这个了。第一，我要偷师这个育儿技巧；第二，我要把它用在 AI 身上。我真的很喜欢对我的 AI 寄予厚望。这在数学证明里可能体会得更深，但我一直在用类似的方式激励它：“哥们，我知道你真有两把刷子。要是让你见识一下我见过的你能做出的那些成果，你都不会相信。只要你再努力一点点，我确信我们一定能把这个原型粗糙地敲出来（vibe code），然后我就能拿去展示给我的工程师看，进而把它正式做出来。我知道你完全有这个能力。”
<details><summary>Original English</summary>
>> [laughter] My Okay, I love that. Um that one, stealing the parenting tip, two, stealing it for AI. I feel like I really love to give my AIs like big expectations. And I You feel like you saw it in the math proof, but like I have been doing a version of this which is like buddy, like I know you can cook. Like you would not believe the things that I've seen out there that you are capable of. Like if you try a little bit harder, I am sure that we can vibe code this prototype that I can show my engineers so that we can build it. Like I know this is in your capabilities.
</details>

>> 我知道你只要努努力就能徒手敲出一个 Salesforce。
<details><summary>Original English</summary>
>> I know you can vibe code Salesforce. Just a little
</details>

**Ezra McCabe**: 哪怕一点点。
<details><summary>Original English</summary>
>> Totally.
</details>

>> 好的，Ezra，今天聊得太开心了。有这么多优秀的使用场景和精彩的洞见。大家可以在哪里关注你？有什么我们可以提供支持的？
<details><summary>Original English</summary>
>> Okay, Ezra, this has been so fun. So many good use cases, so many good thoughts. Where can we find you and how can we be helpful?
</details>

**Ezra McCabe**: 好的，主要在 Twitter 上，我发推有点频繁，账号是 Ezra McCabe。另外谈到支持，我们在招 PM，在招很多 PM，各种类型的都在招。如果你是工程师或设计师，我们也都在招人。欢迎来 Figma 工作，这是我经历过的最有趣的工作。我们正在打造非常酷的东西，团队的伙伴们也都棒极了。
<details><summary>Original English</summary>
>> Yeah, um mostly on Twitter. Uh I post too much. Um Ezra McCabe. Uh and then in terms of being helpful, uh we're hiring PMs. We're hiring a lot of PMs. And we're hiring a lot of different kind If you're an engineer or designer, we're hiring. Come work at Figma. It is the most fun I've ever had in a job. Uh we're just we're building really cool things and the people are great.
</details>

>> 太棒了，这是最完美的收尾了。Ezra，非常感谢你来到《How I AI》。
<details><summary>Original English</summary>
>> Amazing. Cannot cannot end it better than that. Ezra, thanks for joining How I AI.
</details>

**Ezra McCabe**: 谢谢 Claire，再见。
<details><summary>Original English</summary>
>> Thanks, Claire. Bye.
</details>

>> 非常感谢大家的观看。如果你喜欢这期节目，请在 YouTube 上点赞并订阅；如果能留下包含你想法的评论，那就更好了。你也可以在 Apple Podcasts、Spotify 或你常用的播客 App 上找到本节目。请考虑为我们打分并留下好评，这能帮助其他人发现我们的节目。你可以在 howiai.pod.com 查看所有过往剧集并了解更多节目详情。我们下期再见！
<details><summary>Original English</summary>
>> Thanks so much for watching. [music] If you enjoyed the show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiai.pod.com. See you next time.
</details>