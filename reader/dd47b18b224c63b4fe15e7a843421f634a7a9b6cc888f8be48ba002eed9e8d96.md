---
author: AI Engineer
date: '2026-11-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xRJMiaUoD_8
speaker: AI Engineer
tags:
  - artificial-intelligence
  - software-engineering
  - agentic-workflow
  - human-computer-interaction
title: 苦涩教训的甘美一面：从工业化走向软件文艺复兴
summary: 前 Anthropic 工程师 Tharak 反思离开后的 AI 认知变化，指出模型并非只能遵循特定模式的外来智能，而是具备能够覆盖广泛任务的平滑内部能力。他提出软件正在经历工业化与文艺复兴，并分享了在游戏开发中通过拆分引擎代码与人类可读的规格脚本来保持掌控感的实践。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Tharak
companies_orgs:
  - Anthropic
products_models:
  - Claude Code
  - React
  - Opus 4.6
  - Opus 5.5
  - Cursor
media_books: []
status: evergreen
---
### 离开 Anthropic 后的反思与认知转变
大家好，我是 Tharak，很高兴见到大家。

我想和大家聊聊自离开 Anthropic 以来一直在思考的几件事。这是跌宕起伏的一年，我有了许多反思。我的结论关乎我所谓的“苦涩教训（the bitter lesson）的甘美一面”，以及我过去看错的地方。
<details>
<summary>Original English</summary>
Hey guys,

I'm Tharak. Nice to meet you.

Yeah,

I wanted to talk to you about a couple things I've been thinking about since I left Anthropic.

It's been a wild year and there a bunch of reflections I've had.

And my conclusion is about, you know, what I'm calling the sweet side of the bitter lesson and the ways I've been wrong.
</details>

我认为今年我在很多事情上看对了。

我认为自己看对了模型能够编辑和生成视频。大概在去年六月的时候我就在谈论这个。我看对了模型能够利用 HTML 来理解自身的工作。我也看对了模型能够帮助你理解并梳理未知事物，辅助规划和学习。这些都是我看对的事情，我感到很高兴，而且我认为你们中的很多人可能也正在将这些融入到日常工作中。
<details>
<summary>Original English</summary>
So I I think I got a lot of things right this year.

I think

I was right about models being able to edit and generate videos. I was talking about this like sometime in like June last year.

I was right about models being able to use HTML to understand their work.

And I was right about models being able to help you understand and figure out your unknown to help like plan and learn about things. So these were all things I was like right about and I was happy and I I think that like a lot of you might be incorporating this sort of stuff in your work.
</details>

但我也看错了很多事情。我认为在 AI 领域经常会出现这样一种情况：大家往往会抹掉自己看错的记忆，然后说“哦，我其实一直都预料到 AI 会变得很厉害”。

但以下是我看错的一些事情。
<details>
<summary>Original English</summary>
But I've been wrong a lot too and I I think this is one of those things in AI where you sort of just like memory hole the things that you're wrong about and you're like, oh like I was just always expecting, you know, AI to be great.

But here are some of the things I've been wrong about.
</details>

### 看错的三大预测：Bash、React 与扩散模型
首先是“Bash 就能解决一切（Bash is all you need）”。当时似乎有一个阶段，智能体非常擅长使用 Bash，而 Claude Code 正是围绕 Bash 工具构建的。于是人们就觉得，好吧，我们干脆把所有东西都做成命令行界面（CLI）。感觉未来只会有 Bash 和 CLI，并且那将统治世界。

事实完全不是那样。比如我现在其实更喜欢 MCP 而不是 CLI。不仅如此，现在还有代码模式（code mode）、skills 以及渐进式披露（progressive disclosure）。智能体对外部世界采取行动的方式非常多样。它们此前使用 Bash，只是一种奇特的残留现象，反映了它们最初受训的某种方式。
<details>
<summary>Original English</summary>
So first like Bash is all you need. I I think there was this like moment where the agents were really good at using Bash and Claude Code was built around the Bash tool. And so, you know, people are like, well, we'll just turn everything into a CLI. Like, you know, like there is just going to be Bash and CLIs and that's going to like take over the world.

That's actually kind of not how it turned out. Like I actually prefer MCP to CLIs now, you know, but now there's also code mode and skills and progressive disclosure. Like there are so many other like ways that agents can, you know, act on the world, right? And the fact that they were using Bash was just like this weird remnant of, you know, like them being trained in a certain way at the start.
</details>

其次是“React 就能解决一切（React is all you need）”。我觉得曾经有一阵子，模型似乎极度擅长编写 React。于是大家认为，如果想构建一个 AI 驱动的应用，就必须想办法使用 React。比如应该用 React Native，应该把所有东西都做成网页端。

这也并非事实。我认为现在模型可以用 HTML 写，可以用 React 写，可以用 Swift 写，也可以用 Figma 的专有 JSON 格式写，它们呈现出来的效果大致相同。我之前曾担心模型都是基于 React 训练的，导致我们必须永远写 React，React 几乎会成为最后一种语言。这几乎必然是不对的，现在很多人都在编写自己的专用语言。
<details>
<summary>Original English</summary>
Then there's like React is all you need. I think for a moment it seemed like the models were really really good at writing React. And so, you know, if you wanted to create an AI enabled app you should figure out how to use React. Like you should use React Native, you should use, you know, like you should just make everything on the web.

And that also has not been true. I I think like now, you know, models can write it in HTML, they can write it in React, they can write it in Swift, they can write it in the Figma proprietary JSON format.

And they'll all look roughly the same. Right? And so

I was afraid that like you know the models have been trained on React and so we'd just be writing React forever and React would be like the last language almost, right? And that's almost certainly not true, right? I think a lot of people are writing their own languages now.
</details>

还有一件事我之前非常担忧，那就是扩散模型会“吞噬艺术”。当时觉得我们完全无法控制这些模型，或者无法控制它们创造的艺术形式，但它们就是能生成最美丽的内容。

实际情况完全不是这样。我认为现在的 LLM 能够通过代码、通过控制你的计算机、通过使用 Blender、Photoshop、Figma 或任何你喜欢的工具来创作艺术。
<details>
<summary>Original English</summary>
And I think one of the other things I was really concerned about was like diffusion models will kind of like eat art. Like it just be like, you know, we wouldn't have any control over these models and or the kind of art that these models are creating, but it would just like create the most beautiful stuff.

And that hasn't been true at all. Like I think now LLMs can make art through code, through controlling your computer and using, you know, Blender or Photoshop or yeah or Figma or whatever you'd like, right? And so
</details>

这些都是我此前对所谓的苦涩教训、外来智能（alien intelligence）或修格斯（Shoggoth）所抱有的担忧。大家常用这些词来描述某种恐惧——害怕模型拥有一套专属于它们的做事方式，而那套方式对我们而言怪异且陌生，以至于我们只能全盘接受，只能屈从于这种外来智能。

但我觉得现实并不是这样。
<details>
<summary>Original English</summary>
these were all sort of like fears I had about like I think the bitter lesson, you know, our alien intelligence, the Shoggoth, right? Like like these are all words we use I think to describe this kind of like fear that the models will just have this like way of doing things and it will be weird and alien to us and we just need to accept it. You know, like you just have to like submit to this like foreign intelligence.

But that's just like I don't think that's what happened, you know?
</details>

### AI 的双重视角：工业革命与文艺复兴
所以，我反复思考的问题是：我们如何既拥抱 AGI（AGI-piled），又保持以人为本？从这一发展进程中，或者从我看错的那些事情里，我们能学到什么？

我认为这极其重要，因为软件工程师处于 AI 应用的最前沿。在软件行业发生的一切，未来都会发生在知识工作和经济的其他领域。因此，我们如何应对和使用 AI，其他人随后也会如何应对和使用。我很喜欢这里的不同演讲，比如谈到对抗无意义粗制滥造内容（slop），我认为我们是第一道防线，又比如变得更加雄心勃勃。

我倾向于将 AI 同时视为一场**工业革命**和一场**文艺复兴**。
<details>
<summary>Original English</summary>
And so I think that like the question come back to a lot is like okay, like how can we be AGI piled and human centered and what can we learn about you know, this progression what we like you know, what can I learn about what I was wrong about, right?

So I think this is really really important because software engineers are like the leading edge of like AI adoption, right? Like any thing that is happening to software will happen to knowledge work and other parts of the economy and so I think how we deal and engage with uh with AI is um yeah, how other people will as well and you know, I really enjoyed the different talks here talking about things like yeah, fighting slop. I think you know, we're the first defense uh for that, right? Or like being more ambitious.

Um, what I like to think about it as AI is both at the same time an industrial revolution and a Renaissance, right?
</details>

我认为今年主要体现的是工业革命。我们经常使用“软件工厂”这个词。它正在把软件从一门非常不可靠、执行难度极高的手艺，转变为一种不再是瓶颈制约的事物。这种工业化进程绝对正在发生，这无疑是正在软件领域上演的变革。

但与此同有一种文艺复兴正在发生。人们渴望质量越来越高的软件，而你在其中倾注的每一分额外创造力、实用性、精神与灵魂，都是有益且具备经济价值的。

这两者同时存在，很难在脑海中同时兼顾和把握，但我认为这是千真万确的现实，我们正在同时经历这二者。
<details>
<summary>Original English</summary>
And I think this year was really about the industrial revolution, right? Like we use the word software factories very often

um

and uh like just sort of like turning software from this like craft that was very unreliable and hard to execute on into something that like is not the limiting factor, right? Um, and this sort of like industrialization is absolutely happening. This is definitely something that is happening with with software, but at the same time there's also kind of a Renaissance happening, right? Where people want and uh higher and higher quality software and every marginal bit of like creativity, utility, like spirit, like soul that you put into it is like is useful and like economically valuable, right? And so simultaneously we've got both of these things that are very hard to juggle and and sort of like hold in your head at the same time, uh but I think it is very true and uh yeah, we're doing both of them. So
</details>

### 从参差前沿到平滑内部
谈论 AI 能力时，我们经常会提到“参差前沿（jagged frontier）”。回顾两年前，你可能会让 AI 为你写一个函数；大约一年半或一年前，变成实现某个功能；接着是构建一个简单的待办事项应用；然后是克隆一个 Slack；现在则是从零开始构建《马里奥赛车》，然后再移植到 Wii 之类的平台。能力提升是显而易见的，查看评测和基准测试时，你看到的就是这样一条参差不齐的能力前沿。

但我同样喜欢谈论所谓的**平滑内部（smooth interior）**。
<details>
<summary>Original English</summary>
often times when we talk about AI capabilities, we talk about like the jagged frontier, right? And so uh you know, you maybe like you go back two years and you're like AI asking AI to like this function for you,

um or, you know, like like a year and half ago, a year ago, it's like build this feature, then you're like, okay, build this like to do app, build like a kind of simple to do app, and then clone Slack for me now, right? And And And now it's like, okay, build Mario Kart from scratch, you know, and then then like port it to like the Wii or something. There's like the capability increases are the things that you see, right? Where, you know, whenever you look at the evals and benchmarks and stuff, you see this like just

um

this jagged frontier of like capabilities. But I also like to talk about like the smooth interior
</details>

这里的运作方式是——哎呀，这个动画在播放吗？平滑内部的概念在于，随着模型变得更强，这里的动画展现了一个参差前沿，以及中间的一个圆圈。圆圈代表模型足够聪明、能够胜任的所有事情，例如编写 React 代码，或者使用 Bash。

你会发现，在前沿下方并非参差不齐。如果它能写 React，它就能写 Figma，就能写 JSON，能同时完成所有这些能力。模型在极广的任务宽度上表现都非常出色。我认为这极其重要，对我而言甚至更具冲击力，因为我不再真正关心它们是否能从零写出一个《马里奥赛车》，我真正关心的是：我们正在构建的软件质量是否够高？是否配得上称为一场文艺复兴？
<details>
<summary>Original English</summary>
where the the way Whoops. the way the models

Is there an animation playing here? Um

the smooth interior is like the idea is that the models are um as they get better, the the animation here is like this jagged frontier and this circle in between. And so uh the circle sort of represents all of the things that the models are too are smart enough to do. And so like examples being like uh writing React code, right? Or like using Bash. And what you see is that like it's not jagged below the frontier, right? Like if it can write React, it can write Figma, it can write JSON, it can do sort of like all of these capabilities all together. And there's like a breadth of tasks that the models are really really good at. And this is something that's also I think really like important and um for me even more impactful because I don't really care that they can build Mario Kart from scratch anymore, right? What I really care about is like, hey, is the software that we're building, is it high quality? Is it worthy of like a Renaissance? You know what I mean? So
</details>

你可以按照自己希望的方式来做事。如果你想做原型图，你可以要求它生成 HTML，或者 React，或者 Figma 文件，甚至可以通过计算机使用（computer use）操作你的电脑，打开 After Effects 制作视频。达到最终结果有许多不同的途径。对此我非常欣慰，我此前确实害怕过模型只钟情于某一种方式，导致我们只能那样做。

推向极致的话，正如我们经常讨论的测试脚手架、软件工厂以及模型的脚手架体系。甚至有一段时间，大家觉得工程师的工作就是给模型做质检或代码审查。现在看来显然不是这样。我认为随着模型越来越聪明，它会更多地呈现这种“平滑内部”的特性，各方面都会处理得很好。

你能想象到的完美模型，根本不需要反复验证自身工作或扫描安全漏洞，它直接把代码写好并告诉你“我完成了”。你去检查时会发现它确实做对了，完全符合约定的规格和目标。我认为这令人兴奋。
<details>
<summary>Original English</summary>
um yeah, like I think that like, you know, you can do things the way you want. So like if you're building mockup, you could be like, hey, can I get an HTML? Can I get a React? Can I get a Figma file? Can I computer use my computer and use After Effects and make a video? There are all these different ways of getting the like final result. And I've been really happy with this. I really was afraid that there would just be like one thing that the models love doing and we'd only be doing that.

Um

and you know like taken to the limit kind of like, you know, we talk about this a lot but like, you know, everything we've talked about so far about like, you know, how you build like these harnesses and software factories and um these like the scaffolding for the models.

Even things like, you know, for a while we were also like, hey um the model you'll like

your job is to QA the model, you know, or review the code. And that's clearly not the case, right? I think as the models get smarter and smarter um it will become more of this like smooth interior, right? Where they're just doing things well, right? And like the perfect model you can imagine won't need to like really verify its work or scan for security vulnerabilities. We'll just like write the code and be like, hey I'm I'm done now. Um and you will check and you'll like, oh you're right. Like, you know, according to the spec and the goals that you that we did you wrote you did it correctly. Um

and uh I think that's actually very exciting.
</details>

有一种可视化模型知识储备的方式来自一个评测，我想是 Aparthy 发布的。基本上你给模型一个经纬度坐标，这些大概是 Claude 模型，询问它这个坐标点是陆地还是水域，然后据此绘制出世界地图。

Opus 4.6 大致是在那边的水平，作为一个很优秀的软件工程模型，呈现出某种模糊的视图。现在再看 Opus 5.5，几乎是完美的，它清楚了解这些坐标，基本上了解整个世界。这说明除了基准测试所反映的参差前沿之外，模型拥有的通用知识变得越来越重要，而前沿本身的参差反而不那么核心了。

令人兴奋的是，我们可以借助智能来理解并塑造我们使用智能的方式。我认为这将是下一年的主题。今年更多是在推进软件的工业化，建立可靠的软件生产方式。但这具体会呈现出什么形态？
<details>
<summary>Original English</summary>
Um one of one of the ways I like to sort of think about visualizing how how much the model knows of this eval. I think Aparthy um posted it.

But basically you ask any I think these are

these are Claude models. You ask a model uh you give it a longitude latitude and you say like, hey is this point uh earth or water, right? Uh ground sorry land or water. And it from that you plot a map of the earth, right? And yeah this is Opus uh 4.6 uh is somewhere over there, right? With quite a good software engineering model, kind of like a blurry view. And now you look at Opus 5.5 and it's like almost perfect, right? Like it knows every piece of, you know, these like these coordinates. It knows like the entire world basically. And so this I I just gives you an idea besides like, you know, the benchmarks about like the the the jagged frontier. I feel like that's less and less important to us, and more important is just like the general knowledge that the models have.

And what's exciting, I think about this, is that we can use intelligence to understand and shape how we use intelligence, right? And I think this that will be like the theme of the next year, right? Where this year I think was really about the industrialization of software and and creating this like reliable way to make software. Um, but what does that look like?
</details>

### 游戏开发探索：从 Vibe Coding 到规格驱动
我一直在开发一款游戏。这是我一直在 Twitter 上发帖分享的一个项目，是一款 2D 等距视角的格斗游戏，灵感来自《降世神通》和《任天堂明星大乱斗》这类作品。

这很有趣，但做起来也相当令人沮丧。我此前很努力地想做一个优秀的 vibe coder。但有时我甚至不清楚每个角色到底具备什么机制。比如我说希望这个角色投掷一块石头，模型会说没问题，但在投掷石头时会发生很多复杂情况：比如这个角色同时还能召唤一堵墙，那么石头能否穿过墙体？以什么速度飞行？大小、蓄力机制又该如何设定？

我发现模型替我做了一堆决定，等我亲自试玩时，却发现自己根本搞不懂这个角色究竟拥有什么行为逻辑。
<details>
<summary>Original English</summary>
So I have been building a game.

Um, it's this like thing I've been posting on Twitter about. Um, it's a 2D like isometric game with like it's kind of like a fighting game inspired by things like Avatar and Smash Brothers. Uh, and

I have kind of like it's fun, but it's also quite frustrating to do. Like I'm really trying to like, you know, like be like a great vibe coder here. Um, I don't really know what each character does sometimes because like I will say like, hey, I want this character to throw a rock. And then it'll be like, oh yeah, great, but like there are all these like different things that can happen when you're throwing a rock. Like this character can also summon a wall. So does the rock go through the wall or not? And like how what speed or like what what about size and charge and all these questions? Um,

and I I find that like the model just makes a bunch of choices for me and then I try it out and I'm like, wow, I have no idea what this character actually does.
</details>

我很容易分心，感觉很难进入心流状态。往往是发送一个提示词，然后就转头去做别的事，过后再回来看。老实说，因为这些原因，我的进度反而变慢了。

这很令人沮丧。有段时间我觉得或许这就是与 AI 协作的注定形态，未来大概就是这个样子。但反思之后我认为这样不对。AI 完全可以按照我们期望的方式工作。我不认为这种状态是可以接受的，也不认为这样能导向文艺复兴，或是创造出非凡的软件。

回到 Dex 所说的，伟大的作品往往诞生于混乱的过程：一开始你并不确切知道自己想要什么，作品的好坏更多取决于你做出了哪些取舍、排除了什么，而不仅仅是包含了什么。

要创造出伟大的事物、创造出配得上文艺复兴的作品，你必须成为专家，必须真正精通业务。当看着自己靠 vibe coding 堆出来的东西时，我只会觉得“天哪，我完全摸不着头脑”。
<details>
<summary>Original English</summary>
I get distracted pretty easily. I don't feel in the zone very much. You know, I I sort of send off a prompt and I start doing something else and I come back. Um,

and I honestly make less progress because of these things, right? And so uh, I think this is frustrating and I think for a while I was like, man, I guess this is just like how you work with AI. This is just like what it's going to be like, you know? But I think reflecting I'm like, man, I I don't think that's right. I think that like, you know,

we have this like the AI can work in the way that we want, right? And so yeah, I don't think it's acceptable. I don't think that this is what leads to the Renaissance, right? I don't think this is what leads to like incredible software.

And part of it, you know, going back to what Dex said is like like great work is just about like this this messy process, right? Of like don't know like exactly what you want. It's more about the choices you made and what wasn't involved or wasn't what wasn't included versus like what was included.

And so

yeah, I think there's like you you like kind of just have to be an expert. You have to like just really know your stuff in order to make something great, right? In order to like make something worthy of a Renaissance, right? And I just like when I look at something I'm vibe coding, I'm like, dude, I have no idea. Like I just don't really get it, you know?
</details>

### 代码库解耦：引擎底层与人类可读脚本
那么我正在如何解决这个问题？

我目前的做法仍处于早期阶段，并不能说我已经彻底理清了所有问题，但我采取的核心方法之一是将代码库拆分为两个部分：一个是底层的引擎部分；另一个文件夹我最初可能叫它 `spec`，但现在大致称之为 `human` 之类的目录。

那个目录里的代码是专门供我阅读的。那里的代码经过了 linter 检查，对 Claude 也有很多规则来约束代码的形式。它读起来应该像自然英语一样，类似于一种规格说明，稍后我会向大家展示它的样子。它的信息密度恰到好处，只要读一读我就能明白在发生什么，并能够直接编辑和微调。更重要的是，它让我对游戏的实际样貌拥有了某种基本的事实依据（ground truth）。
<details>
<summary>Original English</summary>
And so what what am I doing? How am I fixing this?

One of the ways I'm doing it, and I'm still quite early on. I'm not saying that I've like figured it all out, but I think one of the ways I'm doing it is that I have two parts of my codebase. I've got like this like engine part of the codebase, and then I have a folder like I think I call it spec, but I think I'm just calling it human or something. And that folder is the code that I read, you know? And it's like this code that's linted and like there's all these rules for Claude about like what that code looks like. It's supposed to feel like English.

It's kind of like a spec, and I'll I'll show you what it looks like.

But it's at the density where if I just read this code, I know what's happening and I can edit it, I can tweak it. But more importantly, I just like, you know, can have a bit of a ground truth of like what the what my game looks like. And
</details>

我们来做一个快速演示。所谓演示，其实就是——哎呀，这是我的电子演讲稿。好的，开始。

这就是我的游戏。这里有一个 `game` 文件夹，里面的代码属于智能体（agent code）。这部分代码我完全搞不懂相机是如何运作的之类，里面有一堆我不会碰的代码。

但在另一份代码里，我能看到所有的角色以及他们的技能。我可以点进去，比如这是投掷石块的技能动作。在这个动作内部有很多调节参数，注释很完善，使用的是类似“米（meters）”这样的度量概念，而不是写 `X: 0.5` 之类晦涩的数值。它在实现过程中构建了一系列不同的抽象。
<details>
<summary>Original English</summary>
so let's do let's do like a quick demo here.

By demo I guess I mean I'm just going to whoops. This is my eTalk. Okay.

Here we go. Okay. So

this is my game. I've got in here this folder game, and then I've got here this code. This is the like agent code, right? Like this is the code where I'm like, dude, I I don't know how you know cameras work or whatever. I you you like there's a bunch of code here that I don't

But then in this code, I see have all my characters and I have their abilities. And so I can go in here

and I can say like, okay, this is the rock move, right? Um and inside of this move, there's a bunch of ways to tune it. Um it's well commented. It uses things like meters, you know what I mean? Instead of like X like 0.5 or whatever. Um it uh tries to like create a bunch of different abstractions along the way.
</details>

我可以看到很多实用的设计，比如这个角色投掷石块有三种方式：可以从地面抓取，也可以从墙上抓取等。我能清晰看到角色的底层真实逻辑。我并不真正清楚引擎在底层是如何运转和实现的，但我实质上为自己的游戏创建了一门专属的脚本语言。

这意味着当我玩这款游戏时，我可以微调各种细节。我仍在持续开发中，比如我想让石块变得大得多，我可以改写成 1.5，而且我使用的是真正的 IDE。切换到游戏界面，可以看到石块可以蓄力，蓄力后变得非常大，然后掷出。

非常有意思的是，我也开始更多地使用 Cursor 以及它的 Tab 补全模型。因为现在如果我想表达“如果在中途召唤了一堵墙，将其作为动作排入队列”，Cursor 就能直接在这里通过 Tab 键完成补全。这有点像规格驱动开发（spec-driven development），只不过这里的规格形式上就是这样一种脚本语言。
<details>
<summary>Original English</summary>
And so I can see that like one of the things that, you know, is useful is that like there are three ways to throw for this character to throw a rock, right? Like it can uh grab it from the ground, it can grab it from the wall or something. Um

and I can see sort of like the um the true logic of the character, right? I I don't really know how the engine works or how, you know, like this is implemented underneath. But I've essentially created this like almost a custom scripting language for my game. Um and so that means like, you know, when I'm playing this game,

um I can tweak little things. You know, I'm still I'm still like working on it. So like I can say I want the rock to be a lot bigger. So I can say like um you know, 1.5, but I'm using an actual IDE. Uh and so if I go here to my game, uh you know, I can see that like I have a rock, I can charge it, gets really big and I throw it, right? Um but I'm like kind of it it it's really interesting cuz I'm also starting to use cursor more and I'm using the tab model more, you know what I mean? Because now now I can be like, oh hey, what if I just want to say like,

you know, uh if you summon a wall in the middle, like queue it up as an action, and then cursor will sort of like, you know, do the the tab complete here. Um and this is kind of like it's kind of like spec driven development, you know, but the spec is this like this this scripting language basically.
</details>

这是否是我最终编写游戏的方式？我还不确定。在某些方面，当需要实现复杂的底层功能时，我依然需要让 Claude 来写，让 Claude 去构建基础图元（primitives）。但这让我极其容易理解系统里发生的事情，让我感觉重新掌控了一切。在 Claude 工作的同时，我也可以进行审查与协同。这令人非常振奋。
<details>
<summary>Original English</summary>
And um yeah, it's like

is this the final way I'm going to write game? I'm not sure. It's like, you know, in some ways, uh, when I need to do something complicated, I still need to ask Claude to do it, right? And I need to ask to Claude to like make the primitives, but it's actually really easy for me to understand what's happening and I feel like much more in control and while like Claude is working, I can also sort of review it and work with it.

Um, and that's been really exciting.
</details>

### 定义未来体验：迎接软件文艺复兴
对我而言，最大的心得在于：我现在必须去思考交付高质量软件的最佳方式，而不再受限于模型当下的能力、也不再受限于模型偏好使用什么代码来写。我思考的核心是：我该如何交付出卓越的软件？

如果我们能真正理解这一点，我认为接下来的一年将属于软件的文艺复兴。今天在这次大会上，许多人都探讨了如何建立更大的雄心。虽然这些并不算全新的观点，但确实有太多事情值得去做：
- **新语言**：我们显然需要像 Rust 这样高效的语言，但也需要具备模块化、支持热重载且具备高可读性的语言；
- **新图元**：可能会出现新型数据库、新型服务器以及全新的操作系统交互方式。我最近在通过 vibe coding 编写许多侵入操作系统的个人软件；
- **新交互范式**：许多过往的人机交互（HCI）研究如今非常值得重新审视；
- **新美学**：我们使用和设计软件的方式可以发生巨大的变化。

这里有太多事情可以探索。每位讲者都在探讨这些，我没有太多需要补充的。但我真正想表达的是：我们需要做的是去定义未来的工作形态，决定我们理想中的体验究竟是什么。因为模型并不是某种试图强迫我们遵循特定工作模式的外来智能。它们几乎什么都能做，而且未来也一定会做到。而我们的职责，就是去开启这场文艺复兴。

谢谢大家，这就是我的演讲。
<details>
<summary>Original English</summary>
And so I think the takeaway for me has been that like um the takeaway for me has been that like I now have to think about the way the best way for me to deliver high quality software, right? And I'm not as constrained and limited by like the model's capabilities and like what it likes to write code in or something. I'm just not thinking about like I need to think about like how can I deliver great software?

And so I think if we like really internalize that, I think then this the next year will be about a renaissance of software. And you know, I think many people have talked today and you know, this conference about how to be more ambitious and I don't think anything any of this is quite new, but I just think there's like many things to do like new languages, right? Like obviously like you know, uh, we want things like Rust that are very efficient, but we also want things to be uh potentially modular and like hot reloadable. Um, we want it to be potentially readable, right? Uh, new primitives like there are probably new types of databases, new types of servers like um new operating system interactions. I've been sort of like vibe coding a bunch of personal software, um, that sort of messes with my operating system.

Uh, there are new interaction paradigms possible, I think. Um, a lot of like old HCI research is now like very interesting to revisit. Um, new aesthetics, I think the way that we like use and design software uh can change quite a lot.

And um yeah, I I think that like there's so much to do here that I think I I don't think that any of this is everyone every speaker I think has talked about this and um I I don't have too much more to add, but I think that like what I really want us to say is that what we need to do is to decide what the future of work looks like, right? And decide what our ideal experience is because the models are not, you know, this alien intelligence that's like trying to force us into a specific way of working. Uh they can kind of do everything and and they will. Um but our job is to like bring about the Renaissance. So

thank you guys. That's my talk.
</details>