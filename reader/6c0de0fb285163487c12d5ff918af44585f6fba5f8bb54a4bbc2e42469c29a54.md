---
author: AI Engineer
date: '2026-11-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=O_zcc6Xl12g
speaker: AI Engineer
tags:
  - ai-agent
  - code-quality
  - verification
  - software-engineering
  - developer-productivity
title: 从代码残渣到高质量交付：构建高信任度 Agent 研发环境
summary: SpaceXSI 的 Grokbot 工程师 Potato（Lauren）分享了如何通过确定性代码约束、静态分析与全方位验证机制，将低信任度代码环境转变为高信任度体系，从而支持团队在保证代码质量与性能的前提下，实现每月向生产环境交付上万个 PR 的极速研发。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Lauren Tan
  - Brett Taylor
companies_orgs:
  - SpaceXSI
products_models:
  - Grokbot
  - Dune
  - Cursor
  - TLA Plus
  - Lean
  - Bombadil
media_books: []
status: evergreen
---
### 破除代码残渣：从个人生产力到 Agent 编码机器

>> 好的。呃，再次自我介绍一下，我的名字是 Potato。呃，我在 SpaceXSI 负责 Grokbot 项目。

大家能简单举个手吗？你们当中有多少人曾经看过别人写的代码，然后心里想：“这简直全是一堆垃圾代码（slop）”？

好吧，我以前也有过这种想法。

但是今天，我要向大家证明，你是可以把这些“残渣”变成黄金的。

呃，所以上个月我做了一件挺疯狂的事：我向生产环境推送了 3,000 个 Pull Request。
<details>
<summary>Original English</summary>
>> All right. Um so again I'm my name is Potato. Uh I work on Grokbot at SpaceXSI.

And can I just get a quick show of hands? How many of you have ever looked at code that somebody else wrote and you thought that's all slop.

Well, I have too.

But today I'm going to convince you that you can turn that slop into gold.

Uh and so I did something crazy last month and I shipped 3,000 pull requests to production.
</details>

在 Agent 出现之前，除了极少数特例之外，我们通常并不真正关心代码产出的绝对数量。在我之前的公司，我们把这种人称作“编程机器（coding machines）”。比如 Brett Taylor，众所周知，他曾在一个周末里重写了整个 Google Maps。他就是一位生产力极其惊人的工程师。

呃，如今有了 Agent，任何人都可以成为一台编程机器。而我的核心观点是：软件工程师的本质工作、或者说作为软件工程师的“元技能（meta）”，在于探索如何在大幅提升生产力的同时，维持甚至提高代码质量。

为了达到这个目标，有人喜欢将其称作“软件工厂（software factory）”。呃，但我更倾向于把它保持简单，我认为这一切的核心就在于信任。

不是盲目的信任，而是对你的 Agent 所处环境进行投资，从而让你能够确信：你的 Agent 必定会做正确的事。

要达到这种状态确实需要付出大量的努力。呃，我自己花了整整六个月的时间，才达到能在甚至睡觉时也能交付数千个 Pull Request 的水平。

但这绝对是可行的，而且你们所需要的时间肯定会比我当初花费的少得多。
<details>
<summary>Original English</summary>
Now before agents we never really cared about volume uh except for the outliers. And at my previous company we called these people coding machines. People like Brett Taylor who famously rewrote all of Google Maps uh in a weekend. Just an insanely productive engineer.

Uh and well with agents anyone can now be a coding machine. And my thesis is that the job of the software engineer, the meta of being a software engineer is figuring out how to maintain or even improve the quality of your code while massively increasing your productivity.

To get there some people like to call this a software factory. Uh but I like to keep it simple and I think of it as all about trust.

Not blind trust but investing in your agents environment so you can trust that your agents are going to do the right thing.

Now it takes quite a lot of effort to get there um and it took me six months to get to a point where I could ship thousands of pull requests, a lot of them in my sleep.

But it's certainly possible and it will take you much less time than I did.
</details>

### 构建高信任环境：确定性约束与倒金字塔模型

那么，我们先来谈谈如何从一个低信任度的环境转向高信任度的环境。

这个倒金字塔模型，就是我认为应该如何在 Agent 的环境上分配时间的思路。

最底部的两层是确定性的，也就是利用代码本身。比如良好的 API 设计、架构、重构，或者使用 Lint 规则、类型系统、编译器，以及各种不同类型的测试。

你可以将这两层结合起来使用，以约束 Agent 能够做的事情，并迫使它们在默认情况下就做正确的事。

验证层——无论是运行时验证还是形式化验证——都是非常棒的工具，可以叠加使用来发现 Bug，并检查你希望在系统中保持成立的属性和不变式（invariants），同时也能帮你检验 Agent 是否真正理解了你的目标和意图。

最后，你才需要叠加少许的自然语言文本。比如规则、Skills、`AGENTS.md`，即那些需要主观判断的事物。
<details>
<summary>Original English</summary>
So let's start by talking about how we move from a low trust to a high-trust one.

So, this inverse pyramid is how I think about where to spend time on your agent's environment.

The first two layers are deterministic, so using your code itself. So, things like good API design, architecture, refactoring, or using lint rules, type systems, compilers, or you know, different kinds of testing.

And you can use both of these layers together to constrain what agents can do and force them to do the right thing by default.

Verification, both runtime and formal, are great tools to layer on to find bugs and check properties and the invariance in your system that you want to hold true and also help you check whether or not the agent understood your goals and your intent.

And then finally, you want to layer with a little bit of prose. So, things like rules, skills, agents.md, things that require judgment.
</details>

不过，我们还是先从代码库本身说起。

Agent 是根据它们接收到的输入来生成输出的。因此，输入的质量至关重要，而恰巧你的代码库就是最大的输入源之一。

所以，每当你在纠正你的 Agent 时，请多思考如何将这种纠正转化为一项确定性的检查，而不是仅仅在规则文件或 `AGENTS.md` 里面再加一行文本。因为一旦落实到代码中，它的可复现性要高得多，也能让你对其建立更多信任。

我喜欢用的一个比喻是：你的代码库其实就像一座花园。

你知道的，过去代码通常是一次只提交几个 Pull Request。呃，我还记得在 2024 年去上班时，审查我的同事们写的那三个 Pull Request。而到了今天，这个数字更像是 300 个。

所以说，现在的每个工程师本身就相当于由数百个甚至数千个 Agent 组成的团队，代码涌入的速度如此之快，几乎像是一股连绵不断的溪流，甚至感觉是有机的，就像一个活生生的生命体。

在这个比喻中，你的代码库、你所施加的约束、你所设立的护栏，就是坚固的混凝土基石，Agent 编写的新代码都会围绕着它们生长，就如同这张图片里的建筑物一样。

因此在很多层面上，软件工程师的工作某种程度上正在变得越来越像园艺。
<details>
<summary>Original English</summary>
But let's start with your codebase.

Agents generate their outputs based on their inputs. And so the the quality of the input really matters, and it just so happens that your codebase is one of the largest inputs.

So, whenever you're correcting your agent, think about how you can make that a deterministic check instead of adding another line to your rules or your agents.md because it's far more reproducible when it's in code and it lets you trust it more.

And the analogy that I like to use is that your codebase is kind of like a garden.

You know, code used to arrive a few pull requests at a time. And uh I remember going into work in 2024 and reviewing the three pull requests that my colleagues wrote colleagues wrote. And today, that number is more like 300.

So, you know, every engineer is now a team of hundreds or even thousands of agents, and code is arriving so rapidly that it almost feels like a continuous stream, and it almost feels organic, like a living thing.

And in this analogy, your codebase, the constraints that you impose, the guardrails that you put up are the concrete foundations that the new code that your agents write grow around, just like uh the building in this picture.

And so in many ways, the job of being a software engineer is kind of becoming like gardening.
</details>

正因为代码是 Agent 最大的输入源，这意味着任何变通方案（workarounds）、呃反模式、废弃代码或技术债，现在都很容易被下一个 Agent 直接照搬，因为它看起来就像是你代码库里既有的成熟模式。

呃，这就像你的花园里长出了一些杂草或害虫，还没等你察觉，它们就已经蔓延得到处都是了。

因此，你必须尽可能让你的代码库保持纯净，以便 Agent 总是复制那些优秀的代码范式。
<details>
<summary>Original English</summary>
Because code is the biggest input for agents, it means that any workarounds, um anti-patterns, deprecated code, tech debt, it's now likely to be just copied by the next agent since it looks like the established pattern in your codebase.

And uh it's like you have some weeds or pests growing in your garden, and then they spread everywhere before you know it.

So you want to make your codebase as pristine as possible so that agents are always copying the good stuff.
</details>

### 工程实践案例：约束、目录架构与消除注释

好，我们来看几个实际的例子。

呃，Dune 是我们为 Grokbot 创建的一个客户端框架，用以落实这种有机架构的理念。在技术层面上它并没有那么神奇。呃，你大致可以把 Dune 理解为某种面向 Electron 应用的 Next.js。

但 Dune 真正有趣的地方在于，它包含了大量的约束和 Lint 规则，里面编码了我们在构建桌面应用程序过程中吸取的很多经验教训。

其中一个教训就是：任何需要精细技巧（nuance）才能用好的东西，往往都会导致劣质代码。

呃，最经典的例子就是 React 里的 `useEffect`，对吧？它确实有其应用场景，呃但经常被误用。有人开玩笑说你需要一个博士学位才能用好 `useEffect`。呃换句话说，要用好它真的需要非常多的细微权衡。而 Agent 并不擅长使用它。

呃，所以我们的解决方案是：直接在业务产品代码中禁用它，它实际上只被允许存在于 Dune API 内部的极少数地方。

这样一来，这个问题在分类上就被彻底根除了，我们在代码审查时再也不用去抓这种问题了。
<details>
<summary>Original English</summary>
All right, let's look at some real examples.

Uh so Dune is a client framework that we created for Graph Bot to implement this idea for organic architecture. It's not really that interesting technically. Uh you can kind of think of Dune as um kind of like Next.js for Electron apps.

But the interesting part of Dune is that it has a lot of constraints and lint rules that we've encoded uh a lot of the lessons that we've learned building desktop applications.

And one such lesson is that anything that requires nuance to use well often leads to slop.

Uh you know your classic example is uh you know use effect in React, right? It has its use cases, uh but it's often misused. You know some people joke that you need a PhD to use use effect. Um and in in other words, it really requires a lot of nuance to use well. And agents are not good at using it.

Um so our solution has been to just ban it in product code, and it's really only allowed in some places inside of Dune APIs.

And effectively, this problem has now been categorically eliminated, and we never need to catch that during code review again.
</details>

我们使用的另一个很有意思的模式是：通过目录结构来提供上下文。

呃，我们在 Cursor（它也是一个 Electron 应用）上看到过的一个反模式是：Agent 经常会把主线程的代码导入到渲染线程中，从而导致长任务和界面卡顿。

因此在 Grokbot 以及基于 Dune 的应用中，我们把这一点做成了极其严格的约定。呃我们设立了两个顶层目录，直截了当地命名为 `Electron renderer` 和 `Electron main`，而它们之间的导入是被我们的依赖图分析器以及部分 Lint 规则严格禁止的。

再次强调，设置这些 Lint 规则其实很简单，但它意味着在代码审查期间，我们又少了一件需要分心检查和思考的事情。
<details>
<summary>Original English</summary>
Another interesting pattern that we use is context through directory structure.

Uh so one anti-pattern that we saw with Cursor, which is an Electron app, is that agents would often import main thread code into the renderer thread, which would cause long tasks and jank.

So in uh Gulp bot and in Dunanaps, we've made this very very conventional. Uh we have these two top-level directories literally called Electron renderer and Electron main, and imports between them are forbidden or banned by our dependency graph analyzer and some lint rules.

And again, you know, these are simple lint rules to set up, but it means one less thing that we need to review and think about uh you know, during code review.
</details>

然后，我还观察到了另一件相当令人意外的事情：Agent 对 Markdown 的使用方式。比如文档、呃代码注释、规则或 Skills，它们会把这些地方当成写借口的场所，用来辩解自己为什么没有把事情做正确。或者不知道你们有没有见过这种情况：它们会针对你给出的一点微小纠正过度反应，将其视作一条绝对不能打破的硬性规则。

这里还有一个来自 Cursor 的例子。Agent 极度喜欢使用命令式定时器，比如 `setTimeout`、`requestAnimationFrame`、`requestIdleCallback`。它们把这些当作权宜之计，因为它们实际上是在掩盖 VS Code 的命令式风格与 React 的声明式风格之间的架构冲突。

因此，我们最初的架构选择实际上同时恶化了客户端性能和 Agent 的表现。

如果你曾经在 JavaScript 中做过任何性能优化工作，你就会知道，当你频繁且大量地创建和销毁定时器时，会引发频繁的主垃圾回收（major GC），进而造成严重的延迟和掉帧。

呃但最糟糕的部分在于，Agent 写了大量的代码注释（就像你们在这里看到的红色部分），来解释为什么使用这种临时修复手段是合理的。

不知不觉中，定时器在代码库中蔓延开来，应用的性能也遭受了重创。
<details>
<summary>Original English</summary>
And then one more surprising thing that I've seen is agents using Markdown. So things like documentation, uh code comments, rules or skills, and they use this as a place to write down their justifications for not doing the right thing. Or I don't know if you've ever seen this, but they'll over rotate on some small correction that you made, and they treat it like a hard rule that can never be broken ever again.

And here's another example from Cursor. So agents really loved using imperative timers, so things like set timeout, request animation frame, request idle callback. And they were using these as quick fixes because they were really patching over an architecture clash between uh VS Code's imperative style and React's declarative style.

So our choice of architecture actually made both the client and the agent performance much worse.

And if you've ever done any performance work in JavaScript, you'll know that when you have tons of timers being rapidly created and destroyed, causes a lot of uh major garbage collection, which causes a lot of lag and jank.

Uh but the worst part is that agents wrote a a of code comments, like you can see in red here, explaining why this quick fix was justified.

And before you know it, we had timers spreading everywhere and the you know the performance of the app really suffered.
</details>

在 Grokbot 中，呃我们吸取了那次的教训，决定直接禁止 99% 的注释。呃因为注释非常容易过时，呃而且人类本来也通常懒得去读那么多注释。更重要的是，这又一次给了 Agent 一个逃生通道，让它们在面对困难问题时去辩解自己为什么不按正确的方式做。

呃然而关于注释，最糟糕的一点在于它们是不可强制执行的。所以那些看似出于好意的想法——比如“我要告诉下一个 Agent 不要这么做”——最终永远无法转化为任何你能够真正信赖的东西。

因此在 Grokbot 和 Dune 中，呃我们现在配备了 Lint 规则，它们能够提供良好且极具帮助的错误信息，指导 Agent 去修复根本原因、解决真正的问题，呃而不是仅仅打补丁绕过去。

所以我们的大原则是：每一次我们纠正 Agent，都会将其转化为上述某种确定性的检查，或者去思考如何通过更好的 API 设计和架构，在代码中从根本上根除该问题。

如果你把这套流程重复得足够多次，你会发现你在代码审查时需要留意的事情越来越少。到某个阶段你甚至会意识到，已经没有什么可审查的了。你完全可以放手让 Agent 自行合并它们绝大部分的 Pull Request。
<details>
<summary>Original English</summary>
Now in Grabot, uh we learned our lesson there and we decided to just ban 99% of comments uh because they go stale easily. Uh you know humans just really don't bother reading the comment slot anyway. And again it gives an agent the an escape hatch to justify not doing the right thing because it's hard.

Um and the worst part about comments though is that they're not enforceable. So what seems well intentioned, you know like I'm going to tell the the next agent not to do something, never ends up actually being anything that you can trust.

So in Grabot and Dune and in Dune uh we now have lint rules that give uh good and very helpful error messages telling the agent to fix the root cause, the real problem uh rather than just patch around it.

And so our general principle is that every time we correct our agents, it turns into one of these deterministic checks or we think about how to categorically eliminate that problem in the code through better API design, through better architecture.

And if you do this enough times, you'll find that you have just less things to look out for in code review. And at some point you'll realize there's there's nothing left to review. And you can just let agents merge their most of their own pull requests.
</details>

### 强化验证体系：运行时、形式化与基于属性的测试

好的。呃继续往下讲，验证同样是我们提高 Agent 自主性、并增强对其产出成果的信心与信任的极其关键的一环。

我们现在的代码审查流程，实际上已经缩减为只查看验证工件（verification artifacts）。比如录屏视频、截图、图表、形式化验证报告等。

呃这其中最基础的例子就是运行时验证。呃这只是一种花哨的说法，本质上就是为你的 Agent 提供一种能够自行运行代码的方式，并让它们使用人类开发者同样会使用的调试工具，比如 Chrome DevTools 协议。

呃在我们的运行时验证 Skills 中，我们做了一个称之为“功能地图（feature map）”的东西。它基本上类似于从用户视角出发的、覆盖你应用中所有可用功能的一种站点地图。

这样一来，当你对 Agent 说“左侧边栏里的那个小东西”时，它们就不需要靠瞎猜了，这提供了一套通用的共享词汇表。

我们还在这些 Skills 内部使用了自定义 CLI，这样 Agent 每次都可以直接复用该 CLI 和驱动程序，这不仅削减了 Token 消耗，而且本身也是可测试的。
<details>
<summary>Original English</summary>
All right. Uh moving on, verification is also a really big part of how we make our agent more autonomous and also increase our confidence and trust in their work.

And our code review process has now really shrunk into looking at verification artifacts instead. So things like videos, screenshots, diagrams, formal verification.

Um and the most basic example of this is runtime verification uh which is just a fancy way of saying giving your agent a way to run the code for itself and use debugging tools that, you know, human developers use as well, like the Chrome DevTools protocol.

Um, in our runtime verification skills, we have this thing that we call a feature map. And that's basically kind of like a site map of all of the features that are available in your application from the user's point of view.

And so with this, agents don't need to guess when you say, you know, the thingy in the left sidebar, it gives you some shared vocabulary.

And we also make use of custom CLIs inside these skills so that agents can reuse the the CLI and the driver every time, which cuts down on token usage and is also testable.
</details>

呃另外，最近我们也开始关注形式化验证。

呃所以我们现在使用 TLA+ 来对主要的用户流进行模型检查（model checking），例如跨多个设备和平台的消息通知功能。

呃我们还使用 Lean 来进行特定算法的定理证明。呃举个例子，我们编写了自己的自定义虚拟化库，并使用 Lean 来验证我们不会遇到闪烁或抖动的问题。

呃总体而言，我们仍在这个方向上进行实验。它看起来非常有前景。呃通过形式化验证，我们已经找出了相当多的 Bug。呃但这当然不是什么银弹，我们只是把它视作 Agent 环境中的另一件工具、另一道防线。

呃然后这是一个播放非常快的视频，但我们最近刚开始研究的另一项技术是针对 UI 的基于属性的测试（property-based testing）。呃我们使用了一个名为 Bombadil 的库。呃这个工具也已经帮我们捕获了好几个 UI 方面的 Bug。
<details>
<summary>Original English</summary>
Um, and then recently we've also started looking at formal verification.

Uh, so we now use TLA Plus to do some model checking of major user flows such as notifications across multiple devices and platforms.

Uh, we use a lean as well for proving certain algorithms. Uh, for example, we have our own we wrote our own custom virtualization library and we use lean there to check that we don't have, you know, flickering or jittering problems.

Um, and we're still experimenting with this approach overall. It seems very promising. Uh, we've already found quite a few bugs with formal verification. Uh, but it's certainly not a silver bullet and we're treating it as another tool, another layer in our agents' environment.

Uh, and then this is a very fast video, but another thing that we just started looking at is property-based testing as well for UIs. Uh, so we use this library called Bombadil. Um, and this has also caught a few UI bugs for us already.
</details>

好了，从宏观角度来看，我看到了 Cindy 发的一条推文。在 6 个月前，她提到自己由于合并进来的隐蔽 Bug 而无法信任自己的 Agent。而当时对她而言，建立对 Agent 信任所真正缺失的环节，就是验证过程。现在 6 个月过去了，她说她每天 70% 的 Token 都消耗在了验证上。我认为这与我所观察到的情况是一致的，我自己绝大部分的 Token 消耗也同样花在了验证上。

如果你仔细审视她的工作流程，会发现这里面没有任何一项是我们以往从未有过的新型或前所未见的技术。这些都只是优秀的软件工程工具，只不过过去由于难以理解、编写或维护，导致它们的使用成本高昂到令人望而却步。

然而，Agent 大幅降低了这一成本。

事实上，我们正在迈入软件测试与验证的黄金时代，因为 Agent 让我们能够对一切进行全方位的测试，其深入程度是以往在经济效益上完全不可行的。

此外，形式化验证还能帮助你更好地推演产品应当如何运作，并验证 Agent 是否真正理解了你的意图和目标。

呃我在自己的插件 P-stack（Potato stack）中制作了一个名为 statechart 的新 Skill，呃它可以帮助你从用户的视角对状态机进行可视化。呃我发现配合我们提供的视频和截图一起查看时，这种方式的代码审查要轻松得多。呃所以它的效果非常棒。抱歉屏幕闪烁了一下。
<details>
<summary>Original English</summary>
Okay, so zooming out, I saw this tweet from Cindy and 6 months ago she she said that she was oh, she was talking about not being able to trust her agents because of subtle bugs that were getting merged. And really what was missing for her in being able to trust her agents was the verification process. And now, 6 months later, she says that 70% of her daily tokens go into verification. And I'd say that that tracks with what I see as well, that most of my token usage goes to verification.

And if you really look closely at her process, none of these things here are new or novel techniques that we've never had before. These are just good software engineering tools, but ones that might have been prohibitively expensive to use before as they were hard to understand or write or maintain.

But agents drastically cut this cost down. And really, we are entering a golden age of software testing and verification because agents let us test everything to a much greater degree than used to be economical.

And then formal verification can also help you better reason about how your product should work and whether your agents really understand your intent and goals.

Uh I made this new skill called state chart uh in my plugin P stack, potato stack, uh which helps you visualize state machines from uh from the user's point of view. Uh and it's I find this much easier to review alongside the videos and screenshots that we provide. Um and so that's been great. Sorry for the flashback.
</details>

### 成果与展望：月交付 11,000 个 PR 的自动化闭环

呃好的，现在让我们看看那片理想乐土是什么样子的。你付出这所有的呃投资，能换来什么回报？

在 Grokbot 团队中，我们的交付速度正在飞速提升。上个月，我们团队向生产环境交付了极其夸张的 11,000 个 Pull Request，这是一个非常疯狂的数字。

我们发布客户端的节奏也加快了，大约每天都会切出一个新的稳定版本。

核心团队的交付量大幅攀升，同时我们还迎来了大量临时性、轻度参与的贡献者。他们并不一定拥有很多上下文，呃但也参与了贡献。呃在 10 月份，我们大约有 227 个人贡献了至少一个 Pull Request。

面对这种加速的交付速度，你可能会心里嘀咕：这难道不会变成一场混乱吗？你知道的，这难道不会产生一堆垃圾代码吗？

但事实上，被回滚（reverted）的 PR 数量在相对比例上实际上有所下降，并且稳定维持在 0.5% 左右。

但我认为，伴随这种发布节奏和海量 Pull Request 之下，真正让人瞩目的是：Grokbot 的性能相比我们最初发布时，不仅保持了稳定，而且在多个维度上都有了提升。启动速度、打字响应、打开新对话、切换对话，所有这些操作都变得更快了。

请记住，Grokbot 目前仍然是一个 Electron 应用。所以天花板依然存在，对吧？但它已经比市面上的许多其他 Agent UI 要快得多了。

对于一个拥有如此高的交付节奏、有这么多人协同贡献的 Electron 应用来说，我认为这个表现已经相当出色了。
<details>
<summary>Original English</summary>
Uh okay, now let's look at what the promised land looks like. What do you get in return for all of this uh you know investment?

So on the Growth Bot team, our velocity is uh taking off and rapidly increasing. And last month, our team shipped a ridiculous 11,000 pull requests to production, which is a wild number.

And our pace of releasing the client has also increased. And we cut a new stable version about once a day.

And then the core team is also shipping much more. And we also have uh a lot more casual or drive-by contributors who don't always have a lot of context, uh but they're also contributing. Um and in October, we had about 227 people who contributed at least one pull request.

So So this velocity accelerating, you might be thinking to yourself like isn't this going to be chaos? You know, isn't this going to be a bunch of slop?

But actually, the number of PRs that get reverted has actually gotten lower on a relative basis and is steady at about half a percent.

But I think the really interesting thing about this shipping pace and this volume of pull requests is that the performance of Graph Bot has stayed not just stable, but has improved on multiple dimensions compared to when we launched. So startup, typing, opening new chats, switching chats, all of this has gotten faster.

And keep in mind, Graph Bot is still an Electron app for now. So there is a ceiling, right? But it's already much faster than many other agent UIs out there. And for an Electron app with this high velocity and this many people contributing, I'd say that's pretty good.
</details>

因此，在你急于去搭建软件工厂并把能自动化的一切都自动化之前：每当你纠正你的 Agent 时，请先尝试通过改进你的代码库本身来解决。

你可以从一条 Lint 规则入手，以防止反模式的新增，然后再去清理那些历史遗留模式。

接着，务必确保你的验证方案足够坚固。

很多这类工作本来就是迈向自动化的先决条件。如果你的核心编码内环产出的是低劣代码，那么自动化这个闭环只会催生出更多的低劣代码，导致你不得不把越来越多的 Token 砸进这个问题里，而我们都知道那是非常昂贵的。

一旦你在代码库、静态分析、运行时以及形式化验证上完成了这些投入，你就会开始发现，依托这些根基，很多事情都变成了可能，你能够非常轻松地在这些基石之上构建起属于你自己的软件工厂。

当你准备就绪时，Grokbot 会是构建外层循环（outer loop）的绝佳途径。我们拥有大量的连接器和常规例程，能够触发 Cursor、云端 Agent 以及各种工程项目，呃这能让你编排成百上千个 Agent。

举个简单的例子：现在每当我们切出一个新版本时，Grokbot 就会自动为我们拉起一个新的 Cursor 项目，对整个应用程序和整个构建进行模糊测试（fuzzing），通过实际运行应用并像真实用户一样使用它来寻找 Bug。

接着，它会针对找到的每个 Bug 分别提修复 PR，并且——尽管听起来有些不可思议——它还会自动合并这些 PR。这是因为我们的代码库已经足够优秀，Pull Request 在默认情况下往往就是高质量的，我们合入的大部分产品代码已不再真正需要人类进行深度审查了。

所以，当你拥有坚固的基石与优良的有机架构时，你就能化腐朽为神奇，将所谓的残渣转化为黄金；你便能在不牺牲质量的前提下，实现极高速度的高质量交付。

我是 Potato，大家也可以叫我 Lauren。再次感谢各位聆听我的演讲。

>> [掌声]
<details>
<summary>Original English</summary>
So before you jump into building out a software factory and you know, automating everything that you can, whenever you correct your agent, try and do it by improving your codebase first. You know, start with a lint rule to prevent new occurrences of anti-patterns and then clean up those old patterns as well.

And then make sure that your verification story is really strong. A lot of this work is a prerequisite to automation anyway. And if your inner coding loop produces slop, then automating that loop just produces more slop and you need to throw more and more and more tokens at the problem, which we all know is very expensive.

And once you meet these investments into, you know, code into your codebase, static analysis, runtime informal verification, you'll start to find that many things become possible with these foundations and that you can really easily build your own factory on top of these foundations.

And when you're ready, Graph Bot is a great way to build that outer loop. We have tons of connectors, routines that can kick off cursor, cloud agents, and projects uh which let you orchestrate thousands of uh hundreds or even thousands of agents.

And as a quick example, you know, whenever we cut a new release now, Grokbot will automatically spin up a new cursor project for us that will fuzz the entire application, the entire build, and it will find bugs uh by running the app and using it like a real user. And then it's going to open fixed PRs for each of those bugs that it finds and it's going to auto merge it as uh crazy as that sounds. And that's because our codebase is good enough that pull requests tend to be just be good by default and most product code that we land no longer really requires deep human review.

So when you have solid foundations and good organic architecture, you can turn slop into gold and you can ship with high quality uh high velocity without compromising on quality.

My name is Potato, also known as Lauren. Thanks to you again for listening to my talk.

>> [applause]
</details>