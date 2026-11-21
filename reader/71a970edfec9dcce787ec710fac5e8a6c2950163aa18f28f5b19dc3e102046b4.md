---
author: AI Engineer
date: '2026-10-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=AnsXWH2_EBU
speaker: AI Engineer
tags:
  - software-factory
  - code-review
  - automated-testing
  - ai-agent
title: 谁来验证软件工厂：Anthropic 与 Sonar 谈 AI 代码规模化验证
summary: Sonar 的 Manish Kapoor 与 Anthropic 的 Addy Osmani 探讨了 AI 编码智能体普及背景下的软件工厂模式与代码验证挑战。双方讨论了从有人员参与的亮灯工厂向黑灯工厂的演进路径，并强调需通过多层自动化验证、端到端测试以及将品味规范化来建立代码合并的信心与责任机制。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Manish Kapoor
  - Addy Osmani
companies_orgs:
  - Sonar
  - Anthropic
  - CircleCI
products_models:
  - Claude Code
  - Claude.ai
  - Opus
media_books: []
status: evergreen
---
### 现场互动与开场介绍

**>>**: 我非常高兴来到这里，探讨谁来验证软件工厂这个话题。在开始之前，大家能快速举个手吗？如果你的编码智能体（coding agent）在过去一周内提过任何 Pull Request，请举手。

几乎所有人都举了，谢谢。如果你合并了这些 Pull Request，并且审查了合并的每一行代码，请继续举着手。

噢，我确实看到有几个人。太棒了。

因此，我今天想谈的是两个阵营之间的鸿沟：一边是不做手动审查就合并请求，另一边则是做了一些审查后再合并。

我是 Manish Kapoor，在 Sonar 负责产品与解决方案开发者关系团队。我非常激动能与特邀演讲嘉宾——来自 Anthropic 的 Addy Osmani 一起站在这里。Addy 曾在 Google 工作了大约 14 年，你们大多数人可能都知道他。他撰写了大量的文章和内容。我从 Addy 身上学到了很多，所以今天能邀请到他站在我身旁，与大家分享他的真知灼见，我感到十分荣幸。

他最近加入了 Anthropic。Addy，恭喜你在 Anthropic 的新角色。你愿意跟团队聊聊你在 Anthropic 的具体工作和角色职责吗？
<details><summary>Original English</summary>
**>>**: I'm pretty excited to be here and talk about who verifies the software factory. Uh before we get started, uh can you give me a quick show of hands? Uh raise your hand if your coding agent has pulled uh opened any pull request in the last 1 week.

Almost everyone, thanks. And keep your hands raised up if you have merged pull requests and reviewed every line of code that was merged.

Oh, I do see a few people. That's excellent.

So, what I'm going to talk about is the gap between the uh two uh camps, uh merging requests without reviewing manually, and uh you know, merging requests uh after doing some reviews.

So, my name is Manish Kapoor, and I lead the product and solution uh developer relations uh team at Sonar, and I'm excited to be here uh with my guest speaker, Addy Osmani from Anthropic. Uh Addy has been uh had been at Google for about 14 years. Most of you probably know him. And he's written lots and lots of content and articles. Uh I learn a lot from Addy, so I'm uh really fortunate to have him here, stand next to me, and uh share his wisdom with all of us here today.

Uh he recently joined Anthropic, and Addy, so congratulations on your uh role at uh Anthropic. Would you like to tell the team what you're working on at Anthropic, what your role is?
</details>

**>>**: 好的，没问题。我的职责是确保大家在使用 Claude Code 进行构建时能获得极佳的开发者体验。每当我们发现有让体验更顺畅的机会，就会立即将其带回到产品中。我们每天都会发布几次，所以我们非常希望尽可能频繁地确保大家获得尽可能好的体验。
<details><summary>Original English</summary>
**>>**: Yeah, sure. So, I'm responsible for making sure that you all have a really great developer experience building with Cloud Code, and anytime that we discover there are opportunities to make it even smoother, we bring that right back into the product. We ship a couple of times every single day, and so we're very interested in trying to make sure that you have the best possible experience as often as possible.
</details>

### 软件工厂的概念：亮灯与黑灯

**>>**: 太棒了，谢谢你。

好的，我们先来看一张展示问题和背景设定的幻灯片。幻灯片上有两个数据：CircleCI 今年分析了 2800 万个 CI 工作流，他们注意到吞吐量激增了大约 59%，但与此同时，将这些代码合并到生产环境的尝试中，每十次就有三次以失败告终。这是来自 CircleCI 的一项独立统计数据。而且我认为，在我每天接触的大多数客户中也看到了相同的趋势。

这里引用了 Addy 的一句话：“软件工厂就是对循环（loops）的规模化驾驭。”这让我产生了强烈的共鸣。如果你还没读过那篇文章，可以去查阅一下。这是一篇非常有启发性的文章，探讨了软件工厂在未来的发展图景。

Addy，你愿意就撰写那篇关于软件循环以及规模化驾驭循环的文章时的想法，做进一步的阐述吗？
<details><summary>Original English</summary>
**>>**: Cool. Thank you.

All right. Uh so, let's start with some problem and context setting slide. There are two numbers on the slide. CircleCI analyzed 28 million CI workflows this year. And they noticed that the throughput jumped by about 59%. But yet three in 10 attempts to merge that code into production are failing. And this is a stat from one independent stat from CircleCI. Uh And I think I'm seeing the same trend from most of our customers that I speak to every day.

Uh this is a quote from Adi. A software factory is harnessing loops at scale. This resonated quite a bit for me. And if you have not read that article, you can look it up. It's pretty educational article and talking about future how the future will look like in terms of soft software factories. Uh so, Adi, would you like to expand on what you were thinking when you wrote this article about soft loops and harnessing the loops at scale?
</details>

**>>**: 当然可以。在座的许多人可能都听说过“软件工厂”这个词，至少有两种类型的工厂值得关注。既然软件工厂是规模化驾驭循环，那么所谓的“亮灯工厂”（lights-on factory），就是由智能体协助你周而复始地进行规划、构建、检查和发布代码，但人类自身仍需在整个环节中运用判断力和品味。而“黑灯软件工厂”（dark software factory），则更接近于带有机器人自动化作业的汽车制造厂，它始终处于运转状态：自主进行需求界定、构建、检查，而人类的角色则进一步退至意图层面，只在出现极个别的例外情况时才被介入。

这大概就是我当时的思考。我认为很多团队目前都处于这个光谱的某个位置上，并正处于探索如何以一种值得信赖的方式逐步加深自动化的历程中。
<details><summary>Original English</summary>
**>>**: Yeah, absolutely. So, a lot of folks here probably heard this term software factories, and there's two types of factories that are at least worth keeping in mind. Well, you know, software factory is harnessing loops at scale. A lights-on factory is one where you have agents that are helping you with planning, building, checking, and shipping code again and again, but you as a person still apply your judgment and taste inside the picture. And then we have a dark software factory, which is a little bit closer to how, you know, a car factory with robotics might be working where it's constantly doing the work. So, it's scoping, building, checking, and you as the person move down further to thinking about intent, and you're pulled in when they're really the greatest of exceptions to the case.

But, that's sort of what I was thinking. I think a lot of teams are somewhere on this spectrum and are on this journey to figure out like how how do I get further and further into automation in a way that I can trust it.
</details>

### 验证瓶颈与代码信心的建立

**>>**: 很好。

AI 编码现在基本上已经是一个被解决的问题了。我们都知道智能体已经存在。85% 的组织已经在使用编码智能体，这一比例很快会上升到 95%，甚至很快达到 100%。

生成 AI 代码的开发者中有 76% 表示，代码产出的速度快到让他们无法进行验证。因此，他们把越来越多的时间花在审查代码上。那么，你认为目前工程团队管理者面临的最紧迫问题是什么？
<details><summary>Original English</summary>
**>>**: Cool.

So, uh AI coding is now basically a solved problem. We all know agents are there. 85% of the organizations are already using coding agents. It will go to 95% and very soon to 100%. Uh 75% of the uh 76% of the developers that generate AI code, uh they are saying that it it's being code is being produced at a speed that is impossible for them to verify it. So, they are spending more and more time reviewing the code. So, what do you think is the most pressing question that engineering leaders have right now?
</details>

**>>**: 我认为，过去一年里各团队与智能体协作的能力已经有所提升，模型和测试载具（harnesses）也变得更好。我看到很多管理者关心的是：我们如何能让大家在具备信心（confidence）的前提下更快地发布代码？而“信心”这块至关重要。

现在的智能体能够以远低于以往的成本，为你生成检验代码的方式。如果你回顾一下过去让我们能把优质代码定义为“高质量”的要素，那就是出色的测试、基准测试、技术规范——任何能给我们带来信心的东西。如今，智能体能帮我们更轻松、更迅速地生成这些内容。我们当然可以对它们进行完善，但我认为这些检查正是我们当下最应该投入时间的地方之一。

如果你希望从智能体那里获得最高质量的输出，你就必须为它们提供一种验证工作是否正确的方法。如果你具备了这一套机制，能确保代码既正确又完备，你的产出质量就能轻易提升两到三倍。
<details><summary>Original English</summary>
**>>**: So, I think that teams have gotten better working with agents over the last year. Um models, harnesses have also gotten better. And what I see a lot of leaders being interested in is how do we enable you to ship code faster um with confidence. And that confidence piece is very important. Agents can now generate ways for you to check your code much more cheaply than ever before. And if you think about the things that enabled us to call good code, you know, high quality, uh those were things like good tests, benchmarks, uh specs, anything that gives us confidence. So, agents are able to help us generate that a little bit more easily these days, a little bit more quickly. We can of course refine those things, but I think that those checks are one of the most important things we should be spending our time on these days.

Like if you are hoping to get the best quality output from your agents, you need to give your agents a way to verify that the work is correct. If you've got that in place and it you can make sure that the code is both correct and complete, that can easily two to three by like the quality of your outcomes.
</details>

### Anthropic 内部实践：规模化合并与代码审查

**>>**: 没错，完全正确，一针见血。我认为“代码信心”——我们之前一直打的一句广告是“代码信心是稀缺的”。既然编码问题已经被解决，你确实需要把这种信心建立起来。

昨晚我读到了 Anthropic 发出的一篇文章，这可能对你来说是个突击提问。我鼓励大家去读一读，里面谈到了 Anthropic 目前运转的规模：他们现在每天合并大约 30,000 次代码变更。就在几个月前，他们每天大约处理 3,000 或 2,500 次代码变更。他们已经从每天 2,500 次扩展到了每天 30,000 次，这简直令人难以置信。那么，在 Anthropic，在与你合作的 Claude Code 团队中，代码审查究竟是怎样的流程？
<details><summary>Original English</summary>
**>>**: Yep. Yep. Absolutely right. Spot on. I think code confidence uh we have been running an ad code confidence is scarce. And you really need to build it up now that the coding problem is solved. So, I actually I yesterday night, so this might be a surprise question for you. Uh yesterday night I read a post uh from Anthropic, and I encourage all of you to read it. It talks about the scale at which Anthropic is operating. Uh they are merging about 30,000 code changes every single day. They used to do about 3,000 or so, 2,500 or so code changes just a few months back. They have scaled from 2,500 code changes to 3,000 uh 30,000 code changes per day. That is mind-boggling. So, I didn't What does code review look like at uh Claude Code at Anthropic and with the Claude Code team that you're working with?
</details>

**>>**: 是的，这些都是极好的问题。我们早在五月份的时候，每天就合并大约 2,500 次变更了。即便是最近对 Claude.ai 的重构，我们发布了一篇案例研究，提到我们让其性能提升了大约三倍。这是通过在极短的时间内合并了大约 3,000 个 Pull Request 实现的，期间有工程师、产品设计师等多个不同职能的人员参与其中。

为了落实验证和代码审查，我们的工作流首先是让 Claude 进行首轮初审。这里面非常关键的一点是，确保它具备像真实用户一样实际体验产品的方式。这意味着可以进行端到端测试、打开页面体验、在浏览器中检查、运行各种工具、执行代码静态检查（linting），以及进行其他任何建立信心所必需的检查。

大家通常会问：“如果发现漏洞或功能缺失，会发生什么？”我们配备了钩子（hooks），它们会在任何修改发生时运行，研究差异（diffs），并促成一个闭环机制，让我们尽快修复 PR。

因此，我们有 Claude Code 进行审查。我们还有一个代码审查产品，大家也可以去看看，效果很好。那里的核心思路是我们试图尽可能实现代码审查自动化。这是我们自己也在使用的工具。

此外，越来越重要的是让你的团队去思考：如何把我们最近经常谈论的“品味与判断力”沉淀下来？将你认同的最佳实践和品味，规范化（codify）写入团队共享的文档中，比如 `Claude.md`、`agents.md`，或是任何智能体在代码审查期间能够查阅的载体。然后，人类负责审查智能体给出的证据。

我们该如何确证呢？例如，如果我正在构建一个将在浏览器中供用户使用的 UI 组件，我希望能确保它在浏览器中经过了测试，甚至让它为我生成一段该交互体验的视频，展示它在里面到处点击的过程，以此给我提供信心：“好吧，这确实能正常工作。”如果我关心移动端或桌面端的体验，也许它可以为我生成截图或录屏。但归根结底，你希望达到这样一种状态：由智能体为你提供尽可能详尽的验证证据。
<details><summary>Original English</summary>
**>>**: Yeah, these are great questions. So, we were we were merging about 2,500 changes all the way back in May.

Um and even for our recent refresh of Claude.ai, we put out a case study saying that we kind of three-by'd the performance of it. That was accomplished by merging about 3,000 pull requests in a very short space of time with engineers, product designers, a number of different functions contributing to it. So, our workflow for being able to get verification and code review in place is that we first of all have Claude do a first-pass review. What's very important in there is making sure that it has a way to actually try the experience out similar to a real user. So, that can mean end-to-end tasks, you know, opening up the experience, checking it in a browser, running any tools, doing any linting, doing any other checks that are necessary to build up that confidence. Um people usually ask, "Is it okay, well, what happens if, you know, you discover a bug or a gap in functionality?" Well, we have hooks that will then go and run on any edits. They will study the diffs and allow us to get this loop in place where we're correcting the PR as quickly as possible. So, we have uh Claude Code doing the review. We have a um code review product uh that you can also check out. It's pretty good. And the idea there is we're trying to automate code review um as much as possible. This is something that we use ourselves. Um and increasingly what's important is for your teams to be thinking about how can you cut We talk about taste and judgment so much these days, right? It's important for you to be trying to codify what you consider best practice and taste in your team's shared like Claude.md, agents.md, anywhere where the agent can then consult during code review. And then people are responsible for checking on the agent's evidence.

So, how do we know? Some If I'm building out um a piece of UI that's going to be, you know, used by a user in the browser, I want to make sure that it's tested in the browser, maybe generated me a video of that experience where it's been clicking around and gives me confidence. Well, okay, well, this works. If I care about the mobile or desktop experience, maybe it generates me screenshots or videos of that. But basically, you want to get to a place where the agent's giving you as much verification evidence as possible.
</details>

### 调研数据与测试类型演进

**>>**: 很好。是的，验证是核心。我认为你需要验证软件工厂产出的一切，这也是我们今天要探讨的主题。

顺便提一下，这些统计数据来自 Sonar 即将发布的《代码状态调查报告》。我们调研了 1000 多名开发者，发现了一些有趣的数据，能让我们洞悉行业现状以及未来的发展趋势。

84% 的人表示 AI 特性让新功能和漏洞修复能更快地上线生产环境。Pull Request 变得更大、更复杂。然而，未经验证就进入生产环境的代码却增加了 31%。

这是一个有点令人担忧的事实，特别是在监管严格的行业或关键任务应用中，你绝对必须确保对代码进行了验证，并对发布的代码充满信心。

那么，Addy，下一阶段的效益提升将来自何处？
<details><summary>Original English</summary>
**>>**: Cool. Yeah, verification is key. I think you need to verify everything that the software factories will produce and that's what we are going to talk about today. Uh so Uh another these stats by the way are from uh the state of code survey report that will be coming out very soon from Sonar.

Uh we surveyed about a thousand more than a thousand developers and we found some interesting data which will give us insights as to what's happening in the industry today and where we are headed.

So, 84% say AI features uh uh gets gets features and fixes put to production faster.

The pull requests are getting larger and more complex. Uh and you know, yet uh only uh 31% more code is reaching reaching the production without review.

So, that's a little little bit of a scary fact particularly for uh production uh applications in the regulated industries in the mission-critical applications where you absolutely make need to make sure uh that you know, uh you have to verify that code and you're confident in the code that is being shipped. So, uh what are the where are the next gains going to come from, Addy?
</details>

**>>**: 我认为下一阶段的提升将结合两个方面：我们真正落实好验证机制，以及模型质量的提升。但就模型而言，比如你看看 Opus 55，模型质量其实已经达到了相当出色的水准。我认为，我们能够就验证环节分享最佳实践，将会变得越来越重要。因为如果你只是告诉人们“去验证工作”，他们接下来的问题就会是：“这到底意味着什么？”
<details><summary>Original English</summary>
**>>**: I think the next gains are going to come from a combination of us really nailing verification, right? As well as model quality. But models are already like if you you take a look at Opus 55, model quality has already gotten to a place where it's pretty good. Um and I would say that us being able to share best practices about that verification step is going to become increasingly more important because if you tell people, yeah, just like verify the work, you know, their next question is, what does that even mean?
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 因此，我认为讨论必须深入到具体哪些类型的测试是真正有用的。我们非常倚重端到端测试、基于属性的测试（property tests）、各类视觉验证测试，这些手段能够帮助我们建立信心，从而自动合并这些变更。
<details><summary>Original English</summary>
**>>**: And so, I think that the conversation needs to evolve into specifically what kinds of tests are useful. We lean a lot on end-to-end tests, property tests, any visual verification tests, things that can help us just get that confidence to merge those changes in automatically.
</details>

### 软件工厂普及率与多层验证体系

**>>**: 很好。你提到了亮灯工厂，这正是我们前进的方向。我们的调研结果显示，目前有 5% 的公司在使用软件工厂，未来这一比例将达到 34%，在金融服务领域更是高达惊人的 39%。

现场有多少人今天已经在使用软件工厂了？单纯好奇一下。只有少数几位。那有多少人计划在明年之前使用软件工厂？

是的，这是个好问题。你如何定义软件工厂？你愿意解答一下这个问题吗？
<details><summary>Original English</summary>
**>>**: Cool. You mentioned light factories. Want to go down that and that's the way uh direction we are headed. Uh our survey results show that, you know, today 5% of the companies are using uh software factories. It will get to 34% and surprisingly 39% in the financial services. How many of you are using software factories today? Just curious. A handful of you. And how many are planning to use software factories by next year?

Yeah, that's a good question. How do you define a software factory? Would you like to take that question?
</details>

**>>**: 好的，没问题。我们刚才已经稍微谈到了软件工厂的定义。软件工厂基本上就是规模化运行的循环。当我们思考这个问题时，核心在于人类在流程中的参与程度处于光谱的哪一端。

智能体越能够生成验证手段并赋予你信心，你就越能接近实现黑灯的状态。我认为大多数人目前仍然处于该光谱的中间某个阶段，正如数据显示的那样，尚未完全达到黑灯的状态。
<details><summary>Original English</summary>
**>>**: Yeah, yeah, sure. So, we we talked about definition of software factories just a little bit earlier. A software factory is basically loops at scale. And when we think about this, it's all about like what end of the spectrum are you at in terms of how much people are still involved in the process.

The more that the agents are able to generate verification and give you confidence, the more that you can get to that place where you go dark. And I think that yeah, most people are still somewhere in that spectrum and are not quite as this data shows at that dark point just yet.
</details>

**>>**: 是的。补充一下 Addy 所说的：我认为可以把软件工厂想象成一条生产线，你从定义意图和规格说明开始，然后开始编写代码。这是一条流水线，软件开发生命周期的每一个步骤都在这里发生。

在黑灯工厂中，通过规模化自动化，基本上无需开灯，它能够完全自主运行。而在亮灯工厂中，人在每一步或大多数步骤中仍会参与其中；黑灯工厂的目标则是关上灯，让工厂全天候独立运转。

好的，你刚才谈到了验证。我想谈谈 Sonar 对验证的看法。如果你今天早些时候听过我们 CEO 的主题演讲，他提到验证应该是多层次的。我们百分之百确信，每家公司都应该采纳零信任的多层验证方法，并且验证应该贯穿每一个循环。无论你是在智能体循环内部操作，还是在 CI 验证循环内工作，亦或是在进行代码维护，在每一个循环中，验证工厂或智能体产出的代码都至关重要。

我们从层次的角度来看待它。可以把它想象成：第一层是确定性层（deterministic layer），它负责捕获漏洞、安全问题，比如 SQL 注入、缓冲区溢出等缺陷。

然后是第二层，即智能体审查层。正如 Addy 所说，这里利用智能体来审查代码，在智能体审查中，它们能捕获确定性层不擅长发现的逻辑与意图层面的问题。因此，我们让每一层专门针对特定类型的问题。

第三层可以是软件供应链安全层，你在其中检查所有的 CVE，进行恶意软件检测，以及恶意代码包的检测。因此，这是一种分层方法，每一层都针对捕获特定类型的问题进行了调优和优化。所以，我们坚决推荐进行多层验证。
<details><summary>Original English</summary>
**>>**: Yep. Just to add to what Addy said, I think software factory, think of it like a production line where you start defining the intent and your specifications. Then you start writing the code. So, it's an assembly line where each of these software development life cycle steps happen.

And automating them at scale where there's pretty much in a dark factory, there would be no lights on. It's autonomously working, fully autonomously working. A light factory has uh is where people are involved in the process at every step or most steps. Uh whereas a dark factory, the goal would be to turn off the lights and let the factory run independently 24/7. Uh all right. So, you talked about verification.

Uh I'll talk a little bit about what we think at Sonar about verification. If you saw our keynote earlier today from our CEO, he talked about verification should be multi-layered. Uh we absolutely 100% believe that each company should adopt a zero trust multi-layered verification approach. And verification should be done in every loop. Whether you're operating inside the agentic loop or whether you're working inside the CI verification loop or whether you're doing code maintenance. In each and every loop, it is important to verify the output of the factories or the agents that code that the agents are producing.

So, we look at it in terms of layers and think of it like, you know, the there's first layer which is a deterministic layer which catches uh bugs, security issues, things like SQL injection, buffer overflow bugs, and all of those are caught. And then there's a second layer where agentic review happens where agents are used to like Adi was talking about, agents review review that code. And in that agentic review, they catch logic and intent issues which the deterministic layer is not well suited to catch. So, we we use each layer is targeted at catching a specific types of issues. And then the third layer could be a software supply chain security layer where you look at all the CVEs, all your malware detection happens, all your malicious package detection happens. All of that happens in the third layer. So, it's a layered approach where each layer is tuned and optimized to catch a certain type of issue.

So, we absolutely recommend doing a multi-layered verification. Oops.
</details>

### 控制、沙箱与引导轨道

**>>**: 这里还有一项统计数据：28% 的公司拥有批准的智能体和共享控制措施，而只有极少数具备共享控制机制，且只有 5% 的公司在自主运行软件工厂。Addy，你对此有什么看法？
<details><summary>Original English</summary>
**>>**: So, there's another stat here. 28% you know, companies have approved agents and shared controls and very few shared controls.

And 5% are operating software factories autonomously. What are your thoughts there, Adi? Uh in terms of
</details>

**>>**: 我与很多公司交流过，几个月前他们最大的担忧之一是：他们放任工程团队去随意尝试智能体，结果导致公司内部在某些情况下出现了成百上千个智能体，而他们根本不知道这些智能体在干什么。这些智能体究竟在执行什么操作？它们触碰着公司所有的系统，访问各种数据，甚至可能正在部署到生产环境。

因此，许多企业都在考虑诸如智能体身份标识、遥测技术以及追踪实际运行情况等问题。
<details><summary>Original English</summary>
**>>**: So, I've talked to so many companies where a couple of months ago one of their biggest worries was they were allowing their engineering teams to go off and play around with agents and they got to a place where there were hundreds, thousands of agents in some cases and they just didn't know what they were doing. Like, what are these agents actually doing? They're touching all of our systems, accessing all kinds of data, maybe they're deploying to production. And so, a lot of enterprises think about concerns like, you know, agent identity and telemetry and being able to track what's actually happening.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 我认为对许多公司而言，最大的三个考量是：我们如何看待控制？我们如何看待权限？以及我们如何看待沙箱？我们该如何确保智能体不会跳出沙箱去执行不该做的事情？
<details><summary>Original English</summary>
**>>**: And I'd say that the three biggest things for a lot of companies are how do we think about control, how do we think about permissions, and how do we think about the sandbox? Like, how are we making sure that the agent isn't jumping out of the sandbox and doing things that it shouldn't be doing?
</details>

**>>**: 没错。在 Sonar，我们称之为“引导轨”（guide rails）。与防护栏（guard rails）不同，我们倾向于称其为引导轨，也就是引导智能体沿着正确的轨道行驶，遵循特定路径，防止它们逾矩，或者像 Addy 所说的那样跳出沙箱。因此，为智能体设置引导轨并对协同工作的智能体实施治理是非常非常重要的。
<details><summary>Original English</summary>
**>>**: Yeah. Yeah, we we at sonar we call it guide rails. So, instead of guard rails, we're thinking of calling it as guide rails, where we guide the agents to follow the real tracks, right? A specific path to take and prevent them from going out of bounds or so to say going out of the sandbox like Addie was saying. So, it's very very important to have guide rails for the agent and govern the agents that you're working with.
</details>

### 闪电问答与总结展望

**>>**: 计时器显示我们只剩几分钟了，我们马上进入尾声。我们来做一个快问快答环节，每个问题用一句话回答。幻灯片上已经展示了这些问题，所以……
<details><summary>Original English</summary>
**>>**: Uh So, let's uh we're coming to a close now as my timer is telling me we just have a few minutes left. Let's go get into a lightning round. Uh one sentence response for each of these questions. And you've seen the questions already on the slide, so
</details>

**>>**: 可以是长句吗？
<details><summary>Original English</summary>
**>>**: Can these be long sentences?
</details>

**>>**: 时间允许的话，多长都行。
<details><summary>Original English</summary>
**>>**: They They can be as long as the time permits.
</details>

**>>**: 完美。
<details><summary>Original English</summary>
**>>**: Perfect.
</details>

**>>**: 到 2027 年底，对大多数团队而言会是亮灯工厂还是黑灯工厂？请回答是或否。
<details><summary>Original English</summary>
**>>**: Uh light or dark factory for most teams by end of 2027, yes or no?
</details>

**>>**: 我认为我们将看到带有某些黑灯角落的亮灯工厂。我不认为这个房间里的所有人都能完全用上黑灯工厂，但会非常接近那种状态。
<details><summary>Original English</summary>
**>>**: I think we're going to see uh light factories with some dark corners. I don't think we're going to get to everybody in this room using dark factories entirely, but it's going to be something close to that.
</details>

**>>**: 我猜 Anthropic 今年或明年就会实现。
<details><summary>Original English</summary>
**>>**: I I would guess Anthropic would do it this year or next year.
</details>

**>>**: [笑声]
<details><summary>Original English</summary>
**>>**: [laughter]
</details>

**>>**: 好的。第二个问题：智能体编写的代码应该在 PR 中被标记出来吗？
<details><summary>Original English</summary>
**>>**: All right. Second question. Should agent-written code be labeled in the PR?
</details>

**>>**: 我个人认为应该标记。从历史上看，我们对自己的代码抱有强烈的归属感和自豪感：“这是我写的，我署上自己的名字。”但在 Anthropic，我们对此的思考稍有不同。我们已经演化到不太介意是否标记出“这是 Claude 写的”，因为我们更关注结果，确保代码、功能以及交付给用户的产物是正确的。所以我个人觉得标记出代码来自智能体完全没问题。这还能帮助我们明确：“既然是智能体写的，我们需要落实哪些约束和额外的检查机制？”
<details><summary>Original English</summary>
**>>**: I personally think it should. Historically, we have felt a great deal of ownership around our code, pride around the fact that, "Hey, I wrote this thing. I'm putting my name on it." And at Anthropic, like we we think about this a little bit differently. We've evolved to the point where we don't really mind so much if Claude is like labeled as, "Hey, I'm I'm the one that wrote this thing." because we're a little bit more focused on the outcomes and making sure that the code, the features, like what we're shipping to users is the right thing. And so, I personally think it's fine for the code to be written labeled as being coming from an agent. And that can also help us with things like figuring out, "Okay, well, if the agent wrote it, what are some of the constraints and extra checks that we need to keep in place?"
</details>

**>>**: 我和你的观点一致，Addy。我认为在短期内，至少在可预见的 6 到 9 个月内，我们应该标记 PR，直到我们对自己的工厂具备足够的信心。我们确实希望知晓并追踪这一点，而且这对这里的金融行业客户来说在可审计性方面也很重要。如果做了标记，就能知道是谁写的代码，因为归根结底我们仍然要承担责任……
<details><summary>Original English</summary>
**>>**: I I have the same point of view, Addie. I think in the short run, at least in the foreseeable you know, 6 to 9 months, we should label the PRs till we are confident enough in our factories. We do want to know and track it, and it's also important for the financial customers here in terms of auditability. If you if you know, if you label it, you know who's writing the code because we are at the end of the day still accountable for
</details>

**>>**: 是的，没错，问责制（accountability）是这里最重要的部分。我们依然会标注谁是这次变更的责任人。我也许启动了一次云端运行来完成某项工作，但我依然是要担责的人。如果出了问题，我必须去修复它。
<details><summary>Original English</summary>
**>>**: Yeah, absolutely. Accountability is the most important part here. Like we still label like who is the owner for this change. I might have kicked off a cloud cloud run to complete a piece of work, but I'm I'm still on the hook. If something goes wrong, I have to go and fix it.
</details>

**>>**: 对，这是核心要点。下一个问题，因为这是一个领导力专题分会场，我现场稍作调整：初级开发者或技术管理者今年应该重点培养哪项技能？
<details><summary>Original English</summary>
**>>**: Yep, yep. Key point. Yep. Uh the next question, actually I'll improvise it here because this is a leadership session. What one skill a junior developer or leader should build on this year?
</details>

**>>**: 如果你是一名管理者，我认为你应该推动你的团队认真深入地思考“验证”到底意味着什么。你们目前是如何进行测试等工作的？现状与“让你们能非常放心地让智能体自行批准并合并代码”之间还存在怎样的差距？搞清楚这个问题。而如果你是一名初级开发者，则是硬币的另一面：切实去积累更多不同类型测试的经验，无论它是端到端测试、属性测试等。
<details><summary>Original English</summary>
**>>**: I think that you should push your teams, if you're a leader, you should push your teams to really think hard about what verification means. Um how are you already approaching things like testing? What is the gap between that and you getting to a place where you're very comfortable with the agents being able to sign off on the code being good enough to merge on their own. And so figuring that out, if you're a junior, it's the other side of that. Like actually getting more experience in the different flavors of tests, whether it's like end-to-end tests, property tests, etc.
</details>

**>>**: 好的。其实你没按规则来，超过了一句话，但没关系。最后一个问题……
<details><summary>Original English</summary>
**>>**: Yep. And the last uh you you actually not following the rules, you're going beyond one sentence, but that's cool. Uh The last one
</details>

**>>**: 还剩 30 秒，我赶得上。
<details><summary>Original English</summary>
**>>**: 30 seconds left. I'm fine.
</details>

**>>**: 超时一分钟也没关系。智能体提了 PR，在什么时候可以安全合并？
<details><summary>Original English</summary>
**>>**: We can go a minute over, I'm sure. Uh the agent opened the PR. It is safe to merge when?
</details>

**>>**: 当你完全确信不会出任何差错，或者你已经尽可能把风险缓解到极致的时候。
<details><summary>Original English</summary>
**>>**: You have full confidence nothing's going to go wrong or that you have mitigated that as much as possible.
</details>

**>>**: 太棒了。

好的，这是我的最后一张幻灯片，随后我们就收尾。那么，是什么把那些“发布快但绝非盲目发布”的团队区分开来的？我认为有三个核心要点供大家参考：

首先，编写代码是最快的部分，而且这个问题已经被解决了。对团队而言，强大的审查与验证才是帮助你保持这种速度的关键。写得快并不等于发布得快。你必须对合并的内容进行统计，审视即将合并的内容，并确保它在进入生产环境之前不会跳出沙箱等等。

验证一切。而且自主权是赢来的。即便不是明年，我们也很快会迈入软件工厂时代。你需要在工厂的每一个循环内部，都引入独立的自动化验证，确保你能信赖工厂生产出的产物。

那么，今天的演讲就到此结束。感谢大家今天来参加我们的演讲，以及与 Addy 的这场对话。再次感谢 Addy 抽时间与我们交流。如果大家还有任何疑问，或者想进一步探讨，欢迎前往展厅中 Sonar 的红色大展台找我们。再次感谢大家。
<details><summary>Original English</summary>
**>>**: Love it.

All right. Uh here's my last slide and then we'll wrap it up. Uh so what separates uh teams that are shipping uh fast but not shipping blind? I think that three key takeaways for you. Uh writing code is the fastest part and that is solved. Strong review and verification for our teams is what will will help you maintain that speed. Fast to write is not fast to ship. Uh you have to basically count what is getting merged, looked at what is getting merged, and make sure it doesn't escape the sandbox and the things like that before it gets into the production.

Verify everything. And autonomy is earned. Uh you We will get to software factories very soon if not next year. Uh you need to put in independent automated verification inside each loop of your factory. Make sure that you can trust the output that the factory is producing.

Uh, with that, I'll wrap it up. Thanks for attending our talk today, uh, a conversation with Adi. Uh, again, Adi, I appreciate you taking the time and joining us here in this conversation. Uh, visit us at the big red booth, uh, the sonar booth in the expo hall if you have any further questions or would like to, uh, talk about it. Thank you again.
</details>