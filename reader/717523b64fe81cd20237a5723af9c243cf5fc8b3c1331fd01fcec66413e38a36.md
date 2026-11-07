---
author: AI Engineer
date: '2026-10-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=SHMCGrNJJGc
speaker: AI Engineer
tags: []
title: ''
summary: ''
insight: ''
draft: true
series: ''
category: ''
area: ''
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/13 -->

### 工作坊介绍与环境准备

**Lauri Voss**: 我叫 Lauri Voss，是 Arize AI 的开发者关系负责人。早些年我曾在 npm, Inc. 从事 JavaScript 相关的工作，所以大家可能从那个时候就认识我。不过这些日子里，我主要在思考 AI 应用，思考如何运行它们，以及如何让它们真正发挥作用。在开始前的 15 分钟里，我一直在屏幕上放着这张幻灯片，希望大家之前已经看过了。如果还没看，现在就可以开始配置了。

<details>
<summary>Original English</summary>

**Lauri Voss**: My name is Lauri Voss. I'm head of developer relations at Arize AI. I used to do JavaScript at npm, Inc. way back in the day, so you may remember me from then. But these days I think about AI applications and how to make them run and how to make them actually work. I had this slide up for the 15 minutes before. I hope you've seen it already. If not, now is the time to get started.

</details>

**Lauri Voss**: 这是一个有一定实操性质的工作坊。我已经为大家预先构建好了一个 Agent，它就放在那个代码仓库里。大家将有机会去修改 prompt 并运行实际的 eval 评估。不过整个过程都设置了检查点（checkpoint），所以如果你中途跟不上了，随时可以切换到对应的 checkpoint，直接跳到已经跑通的阶段。

<details>
<summary>Original English</summary>

**Lauri Voss**: This is a moderately hands-on workshop. I've already built an agent for you. It's sitting there in that repo. You will get to play with the prompts and run actual evals. But it's got checkpoints all the way through. So if you get lost, you can just switch to the right checkpoint and jump to the part where it's already working.

</details>

**Lauri Voss**: 运行环境需要 Node 22 或更高版本。所有的示例都会使用 TypeScript 来写，毕竟你们懂我的风格，只要能用 JavaScript 我就一定会用。另外，大家需要在自己的笔记本电脑上安装并运行 Phoenix。在会场的 Wi-Fi 环境下这可能会有点挑战，但我今天早上试过，下载速度相当快。不得不说，`uvx` 确实非常神奇。整个过程中大家完全不需要自己运行任何 Python 代码，所有的 Python 都会由 JavaScript 代表你在后台运行，体验非常不错。

<details>
<summary>Original English</summary>

**Lauri Voss**: You're going to need Node 22 or later. All of these examples are going to be in TypeScript. Because you know it's me, I'm going to use JavaScript if I can. And you're going to be installing and running Phoenix on your own laptop. On conference Wi-Fi that can be a challenge, but I tried it this morning and it came through pretty quickly. So, uvx is magic. You're not going to need to run any Python in this thing. All of the Python is going to be run for you on your behalf by JavaScript, which is nice.

</details>

**Lauri Voss**: 我想环境准备方面大概就是这些。关于今天要做的事情……哦对了，抱歉，还有一个准备工作。当 Phoenix 安装好之后，大家应该在浏览器中打开 `localhost:6006`，看看它的界面长什么样。现在里面应该是空的，但稍后我们会运行命令，把数据灌进去。此外，大家还需要一个 Anthropic 的 API Key。我所有的示例使用的都是 Claude。虽然你可以使用世界上任何一家 LLM 提供商来完成这些事，但我总得选一个示例，所以我选了自己每天都在用的那一个，因此今天用的是 Claude。谁在环境配置上需要帮助？举手示意一下，直接喊我就行，没关系的。好了，那前 10 分钟……怎么了？

<details>
<summary>Original English</summary>

**Lauri Voss**: I think that's it for the setup. So, what we're going to do today is... oh yeah, sorry, one more bit of setup. Once Phoenix is installed, you should open up your browser on localhost 6006 so that you can see what it looks like. It's going to be empty right now, but we are going to run the commands that will fill it with data. You will also need an Anthropic key. All of my examples are using Claude. You can do all of this stuff using any LLM provider in the world, but I had to pick an example, so I picked the one that I use every day. So, this one is using Claude. Who needs help with the setup? Show of hands. Just shout at me. It's fine. All right. So, the first 10. What's up?

</details>

**Audience**: 刚刚开始配置。

<details>
<summary>Original English</summary>

**Audience**: Just getting started.

</details>

**Lauri Voss**: 好的，没问题。

<details>
<summary>Original English</summary>

**Lauri Voss**: Okay, great.

</details>

**Audience**: 好的。

<details>
<summary>Original English</summary>

**Audience**: Yeah.

</details>

### 为什么需要 Evals：告别“看起来不错”的盲目迭代

**Lauri Voss**: 那么，前 10 分钟我们会先讲理论，这样大家可以在我讲解的同时抓紧完成环境配置。我们先从理论开始。

我猜在座的大多数人都遇到过这种情况：你已经构建了一个集成了 LLM 的应用，可能是一个聊天机器人，或者是一个 Agent。你自己试跑了几次，感觉效果相当不错。接着你把它发布上线了，结果有人以一种你完全没料到的方式使用了它，程序就崩了。或者，你改动了 prompt 来修复某一个问题，心里却总有一种挥之不去的担忧：我是不是改坏了别的东西？而且你根本无从知晓。这就是今天我们要探讨的问题，也是 eval（评估）要解决的问题。你怎么知道你的 Agent 到底行不行？你怎么知道自己的改动到底让它变好了还是变差了？当你在修改代码或 prompt 时，如何避免它变差，而又不必人工去逐条阅读每一条输出？

<details>
<summary>Original English</summary>

**Lauri Voss**: So, the first 10 minutes are theory, which will give you some time to catch up on the setup while I'm talking. So, let's get started with the theory. Here's the situation I'm assuming most of you are in. You have already built an application that has an LLM in it. Maybe a chatbot, maybe an agent. You tried it a bunch of times and it looks pretty good. Then you shipped it and somebody used it in a way that you weren't expecting and it broke. Or you changed the prompt to fix one thing, and you have this nagging feeling that you broke something else. And there's no way of knowing. That is the problem that today is about. That is the problem that evals are here to solve. How do you know if your agent is any good? How do you know if your change made things better or worse? And how do you stop it getting worse when you make changes without having to read every output yourself?

</details>

**Lauri Voss**: 我今天向大家保证：到今天活动结束时，你将拥有一套能端到端追踪（trace）的完整 Agent，配有代码评估（code evals）、LLM Judge 评估，以及你自己手写的一个自定义 eval。你还会验证你的 Judge 是否值得信任，运行实验证明你的改动确实生效了，并且把这一切作为测试套件跑在 `npm test` 里，以便能直接放入 `npm ci`。那一部分是我最兴奋的，所以会放在我们今天的最后一步来做。

我看到有几位朋友刚刚进来，让我快速退回到配置页幻灯片，免得他们完全跟不上节奏。好的，请记下这个仓库地址，稍后你们都会用到它。大家那边的 Wi-Fi 怎么样？顺利连上了吗？都能下载了吗？

<details>
<summary>Original English</summary>

**Lauri Voss**: My promise by the end of today is that you're going to have a working agent traced end to end with code evals, with LLM judge evals, and with a custom eval that you wrote yourself. And you'll have checked whether your judge can be trusted. You'll have run an experiment to prove that your changes worked. And you'll have all of it running as a test suite with npm test so you can put it into npm ci. That is the bit that I'm most excited about. So, it's going to be the last thing that we do. I see some people have walked in late. So, let me just go back to the setup slide very quickly so that they're not completely lost. Right. Remember this repo because you're going to want this repo. How is the Wi-Fi working for people? Is it Are you getting places?

</details>

**Audience**: 顺畅得很。

<details>
<summary>Original English</summary>

**Audience**: Excellent.

</details>

**Lauri Voss**: 很好。我之前在 World's Fair 上做过这场分享，当时仓库里不小心塞满了产品图片，在演示里看着确实漂亮，但整整有 400MB 的图片文件，结果彻底翻车，现场甚至没人能把代码库拉下来。所以这次我吸取了教训，今天绝对没有图片了。

<details>
<summary>Original English</summary>

**Lauri Voss**: Okay. I did this at World's Fair and I accidentally had a repo that was full of product images that looked really great in the demo, but it was 400 megabytes of product images and it just complete failure. Nobody was able to get even the repo down. So, I've learned my lesson and today has no images.

</details>

### 核心心智模型：Traces 与 Evals

**Lauri Voss**: 接下来我们梳理一下基础概念。到底什么是 eval？最简短的解释，也是我每次跟资深工程师交流时用的说法：系统中有一套东西叫 trace（追踪），本质上就是日志（log）；还有一套东西叫 eval（评估），本质上就是测试（test），而 eval 就是在你的 trace 上面运行测试。eval 和传统单元测试的区别在于：eval 针对的是永远不会两次完全相同的输出，也就是 LLM 产生的非确定性输出（non-deterministic outputs）。

<details>
<summary>Original English</summary>

**Lauri Voss**: So, let's cover the basics. What is an eval? The shortest version, the one that I use whenever I'm talking to somebody who's been an engineer for a while is that there are these things called traces and they are basically logs, and there's these things called evals and they're basically tests, and evals are running tests on your traces. The difference between an eval and a unit test is that evals are for outputs that are never exactly the same twice, which is to say the non-deterministic outputs that you get from LLMs.

</details>

**Lauri Voss**: Trace 能以令人惊叹的精细程度记录下你的 AI 所做的一切：包括 Agent 的每一步操作、每一次工具调用（tool call）、每一次 LLM 调用，以及每一步的输入和输出。一条 trace 是由我们所说的 span（跨度）组成的。每个 span 就是执行过程中的一个步骤，你可以把它简单理解为日志中的一行。因此，Agent 的一整个交互回合就是一个 span，里面嵌套着其他的子 span。每一个 span 都会记录它的输入、输出、耗时多久、消耗了多少 token，有时还会记录花费了多少成本。所以，trace 告诉你“发生了什么”，而 eval 告诉你“这到底好不好”。这就是今天全部的心智模型，其实离深奥的高精尖科技还差得很远。

<details>
<summary>Original English</summary>

**Lauri Voss**: Traces record what your AI did at an incredible level of detail. So every agent step, every tool call, every LLM call, the inputs and outputs at every single step. A trace is made up of what we call spans. Each span is one step in the execution. You can think of it as just a line in the log. And so a whole agent turn is a span that has other spans nested inside of it. And each one records its input, its output, how long it took, how many tokens it used, and sometimes how much it cost. So traces tell you what happened and evals tell you whether it was any good, and that is the whole mental model for today. This is very far from being rocket science.

</details>

### 从打地鼠到可量化指标

**Lauri Voss**: “我看着挺好的”（Looks good to me）根本算不上测试套件。然而，大部分 AI 功能就是这么上线的：你写好功能，自己试了三次，看起来对不对？嗯，挺对的，发布！在你试的那三次输入里，它可能确实挑不出毛病。但试三次绝不是测试套件。常规的解决办法是写单元测试，但在这里单元测试根本行不通，因为即使面对完全相同的 prompt，应用每次运行返回的文本也会不一样。完全不同的两个回答可能都是正确的，一千个完全不同的回答也可能全都是正确的，只是正确的方式不同罢了。因此根本没有一个固定的期望字符串能让你直接断言（assert）。

结果大家往往退回到依靠人工主观判断：看着输出的字符串，心想“嗯，这个看着没毛病”。但这套做法根本无法扩展，抓不住退化（regression），更不可能跑在完全没有人类值守的 CI 流水线里。

<details>
<summary>Original English</summary>

**Lauri Voss**: Looks good to me is not a test suite. But it's how most AI features get shipped. You build it, you try it a few times, does it look right? Yeah, that looks good. You ship it. And it probably does look good on the three things that you tried. But three tries is not a test suite. And the usual fix is unit tests. But unit tests don't work here because the same prompt is going to give a different answer text every single time you run your application. So two completely different answers can both be right. A thousand different answers can all be right, just differently right. So there's no expected string to assert against. So humans tend to fall back on human judgment. They look at the strings being output and they're like well this looks fine. But that doesn't scale. It doesn't catch regressions and it certainly doesn't run in CI where there are no humans to watch things.

</details>

**Lauri Voss**: 在实践中这会导致什么后果呢？你改动了 system prompt 来优化语气，语气确实变好了，但机器人转头开始胡编乱造产品功能了；而且直到客户踩坑投诉，你才发现这个问题。每一次 prompt 的改动，都可能波及用户输入的各种各样场景，你根本不可能全靠人工肉眼测完。最后你就会陷入一场无休止的“打地鼠”游戏：刚按下这个 bug，别的地方又冒出来了；修好了那个地方，又有新地方崩了。

eval 解决的就是这个问题——它为你提供了一个可以追踪、对比并据此采取行动的量化数字指标。

<details>
<summary>Original English</summary>

**Lauri Voss**: What that looks like in practice is you change your system prompts to fix the tone and the tone gets better. But now the bot is making up product features. And you don't find out until a customer does. Every prompt change can affect every kind of input your users send. And you can't test all of those by hand. So you end up playing a game of whack-a-mole where you fix one thing and something else breaks, and you fix that and something else breaks. Evals fix that by giving you a number that you can track and can compare and act on.

</details>

**Lauri Voss**: 这件事情每个月都变得越来越关键。因为每隔几周就会有人发布一个新模型，大家的第一反应往往是：“哇，我想切到新模型上去。”但除非你手头有一套完整的 eval 测试套件可以跑一遍，否则你根本无法知道新模型到底在哪些方面表现更好，又在哪些方面会出现退步。

这正是我们今天要做的事情：我们先从 Claude 4.5 开始，然后把模型升级到 Claude Haiku 5.5。赶巧的是它大概一周前才刚发布，让这次演示的设计变得非常顺理成章。我当时就想着“这次演示一定要带大家升一次模型”，于是正好拿它来做演练。有了 eval 之后，你跑一遍套件，对比一下指标数据，到今天下午结束的时候，你就能心里有数地知道自己的模型到底能不能升级了。

<details>
<summary>Original English</summary>

**Lauri Voss**: This matters more every month because every couple of weeks somebody releases a new model and you're like, "Oh, I want to switch to the new model." But you have no way of knowing which things the new model is going to be better at and which things the new model is going to be worse at unless you have a set of evals that you can run things through. And that's exactly what we're going to do today. We're going to start with Claude 4.5 and then we are going to upgrade it to Claude Haiku 5.5, which was conveniently released like a week ago making this demo extremely easy to put together. I was like I want to upgrade the model for this demo. So I'm going to make that the demo. So with eval you run the suite you can compare the numbers and by the end of the afternoon you know whether you can upgrade your model.

</details>

### 第一类评估：代码评估（Code Evals）

**Lauri Voss**: eval 分为好几种类型。第一种是代码评估（code evals）。代码评估执行速度飞快，完全免费，但也有点脆弱。它们与传统的单元测试非常非常相似，本质上就是普通的函数，用来对字符串做基础断言。当然，你可以使用很多技巧让它们比只断言固定字符串的简单单元测试更具灵活性，但其底层逻辑是一样的。那么，用代码评估可以测些什么呢？比如：输出的内容是否能成功解析为 JSON？长度是否在限制范围内……

<details>
<summary>Original English</summary>

**Lauri Voss**: And there are a few kinds of evals. The first kind is code evals. Code evals are fast and free and a little bit brittle. They are very very similar to unit tests. They are just ordinary functions where you basically assert a string. There are a bunch of techniques you can use to make them more flexible than a straight unit test that asserts a basic string. But fundamentally that's what they're doing. So the things that you can test with a code eval are stuff like did the output parse as JSON? Is it under

</details>

<!-- chunk 2/13 -->

### 三种评估方式：代码匹配、大模型裁判与人工评估

**演讲者**：字数是否达到了500字？它是否提到了我问到的内容？这类基于代码匹配的评估，优势在于执行只需几毫秒，且运行成本几乎为零。然而，存在大量符合要求的有效回答，是单纯的字符串匹配根本无法判断的。

<details>
<summary>Original English</summary>

**Speaker**: 500 words? Did it mention the thing that I asked about? The advantage of them is that they run in milliseconds and they cost nothing to run. Um, but there are lots of valid answers that a string match can't tell you about.

</details>

**演讲者**：为此，你需要第二种评估方式，也就是大模型裁判（LLM-as-a-judge）评估。这也是大多数人在谈论评估（evals）时首先想到的形式。在这种方式中，你会使用第二个大模型来给第一个大模型的输出打分。

<details>
<summary>Original English</summary>

**Speaker**: Um, and for that you need the second kind of eval which is the LLM is a judge eval. Uh, which is what most people think about when they're thinking about evals. In this one you use a second LLM to grade the output of the first LLM.

</details>

**演讲者**：你会依据所谓的“评分准则（rubric）”来进行打分。在评估领域有一堆直接借用自机器学习的术语，在我看来反而把事情的本质给搞晦涩了。比如“链路追踪（traces）”、比如“评估（evals）”，再比如“评分准则（rubric）”。我常想，rubric 其实不就是规则（rules）吗，为什么非得造个专门的生僻词？无论如何，大模型裁判理解的是语义，而不单单是字符串匹配。比如：内容是否准确？是否严格遵循了源文档？语气是否符合面对客户的规范？

<details>
<summary>Original English</summary>

**Speaker**: [snorts] Um, you grade it against what is called a rubric. There are a bunch of terms in uh eval land that are borrowed from ML uh that I find obscure the meaning of what's going on. One of them is traces and one of them is evals and the other one is rubric. I'm like rubric just means rules. Why do we have a special word for it? Anyway, uh L&M judges understand meaning not just strings. So stuff like is this accurate? Does it stick to the source documents? Is the tone right for a customer?

</details>

**演讲者**：但关键问题在于，正因为大模型裁判本身就是一个大模型，它同样具备大模型所有的固有缺陷。因此，它的表现可能不可预测，两次运行的结果永远不会完全一致，并且它也会犯错。此外，调用大模型也是要花钱的。更要命的是，它们有时会“自信满满地给出完全错误的判断”。所以，你必须对裁判本身进行校验，而这正是我们今天要做的事情之一。

<details>
<summary>Original English</summary>

**Speaker**: Um, the catch is that because the LLM judge is itself an LLM, it has all of the flaws that LLMs have. So, it can be unpredictable. It is never the same twice. Uh, and it can make mistakes. Uh, they also cost money because you're using an LLM. Uh, and they can be confidently wrong. So, you have to check them. And that is one of the things that we're going to do today.

</details>

**演讲者**：接着是第三种评估方式——人工评估。由懂业务领域的人员来通读模型输出，并以专家的标准去打分。人类在质量评判上是公认的“黄金标准”。但缺点在于人工既缓慢又昂贵，而且人会感到疲倦，读着读着就开始泛泛浏览。所以，你应该同时结合使用这三种评估手段。它们之间并不是非此即彼的竞争关系，而是互补的。稍后我们会更深入地探讨如何以互补的方式去综合运用它们。

<details>
<summary>Original English</summary>

**Speaker**: Then there's a third kind of eval uh, which is the human eval. somebody who knows the domain, who can read the output and grade it as an expert. Uh, humans are the gold standard for quality. Um, they're also slow and expensive. Uh, and they get bored and start skimming. So, uh, you want to use all three at the same time. These are not competing approaches. They are complimentary approaches. And we're going to talk about a little bit about how you use them in a complimentary way later.

</details>

**演讲者**：那么，到底什么时候该用哪种评估呢？当答案具备确定性规则时，使用代码评估。比如输出格式、字符长度、必填字段以及违禁词/敏感词拦截等。而当你需要模型去理解语义时，使用大模型裁判，比如：内容是否准确？是否有事实依据（grounded）？是否真正有用？至于人工评估，则用于处理那些你之前从未见过的失败场景、未预料到的意外情况，以及用来抽查校验你的大模型裁判打分是否客观公正。

<details>
<summary>Original English</summary>

**Speaker**: So which eval do you use when? Use code when the answer is deterministic. So things like formats and lengths and required fields and band phrases. Uh but use an LLM judge when you need understanding. Is it accurate? Is it grounded? Is it useful? Uh and use humans for the kinds of failures you haven't seen before. Stuff that you haven't anticipated. And to check that your LLM judges are judging correctly.

</details>

### Agent 带来的评估挑战与级联故障

**演讲者**：上述原则适用于任何 LLM 应用，但对于智能体（Agents）而言，会让这一切变得尤为困难，因为 Agent 的复杂度要高得多。一次简单的单一 LLM 调用相对直截了当：输入提示词，获得输出。但 Agent 往往需要将一整串步骤串联起来执行。

<details>
<summary>Original English</summary>

**Speaker**: Um, all of that applies to any LLM app, but agents in particular make all of this stuff harder because agents are more complicated. A single simp a single LLM call is relatively simple. You give it an input, you get an output. Uh, but an agent tends to chain a whole bunch of steps together.

</details>

**演讲者**：因此可能出现的一种严重故障就是：在链路执行的最早期，Agent 犯了一个微小错误，随后这个错误就会沿着后续所有的执行步骤层层传导、级联放大，导致后面的每一步都越来越脱轨失控。其中最棘手的问题之一莫过于“自信满满地给出错误答案”。自信的错误比显而易见的荒谬错误要危险和隐蔽得多。

<details>
<summary>Original English</summary>

**Speaker**: So, one of the things that can go wrong is very early on in the chain, the agent makes a mistake and it cascades through all of the rest of the steps in your agent and each one gets progressively more off the rails. Um, and one of the biggest problems is being confidently wrong. Confidently wrong is worse than obviously wrong.

</details>

**演讲者**：关于我刚才提到的这种级联故障，举个具体例子：假设你编写了一个金融分析 Agent——这也是我今天稍后要向大家演示的 Agent 类型。你让它生成一份关于特斯拉（Tesla）的研报。它去执行搜索，然而它检索到的不是这家电动汽车公司，而是那位 18 世纪的物理发明家。于是，它洋洋洒洒写出了一篇格式极其精美、行文无懈可击的关于 18 世纪发明家的分析报告。你设置的所有常规校验检查都不会报错，因为从指标上看，格式标准、语气专业、语法完全正确，唯独整个主题南辕北辙。在 Agent 系统中，这种潜在的隐蔽故障是非常让人头疼的。

<details>
<summary>Original English</summary>

**Speaker**: Uh, so I talked about the cascading failure. Um, one example of that is say you've written a financial analysis agent, which is the kind of agent that I'm going to show you today. Um, and you ask it for a report on Tesla. It searches for Tesla and instead of getting results about the car company, it gets results about the 18th century inventor. It writes an beautiful, perfectly formatted report about an 18th century inventor. Uh, and none of your checks fail because you're like, it's well formatted. It's in a great tone. Everything is grammatical. Uh, it's just about completely the wrong subject. Uh, and that is the kind of failure that is uh um insidious with uh agents.

</details>

**演讲者**：Agent 还可能在另一个截然相反的维度上发生“故障”。开发 Claude 的 Anthropic 之前运行过一个名为 Tau-bench 的基准测试，用来模拟客户服务的真实对话场景。他们给 Agent 安排了这样一个任务：用户要求更改机票航班。按照原有测试的设计预设，这个测试用例应该判定 Agent 失败，因为用户买的是经济舱，而航空规则是不允许在经济舱直接选座换座的。

<details>
<summary>Original English</summary>

**Speaker**: Agents can also fail in the opposite direction. Um, Anthropic uh, who make Claude ran a benchmark called Ta2 bench which simulates customer service conversations and they uh, gave it this task where the user asked to change their flight. Uh, and the test according to the test the user was supposed to fail the test uh, or rather the agent was supposed to fail because uh, the person was in economy and you're not allowed to switch seats in economy.

</details>

**演讲者**：然而 Claude 竟然钻研出了另一条路径：它发现自己可以先把这名乘客升舱到头等舱，因为头等舱是允许任意更换座位的；在头等舱成功改换座位后，它又把乘客降舱转回了经济舱！这样一来，它完美达成了用户最初提出的诉求。但原有的测试逻辑却判定它失败了，理由是“系统规则本不应允许你这么做”。其实是 Agent 比设定测试规则的人还要聪明。所以你在构建评估体系时必须充分预期到：有时 Agent 能够找到连你都未曾设想过的问题解法。因此，你的测试体系必须具备极高的灵活性。

<details>
<summary>Original English</summary>

**Speaker**: Uh but what cloud found is that they can upgrade the person to first class. You're allowed to change your seat in first class and then they downgraded them back after changing their seat back down to economy. Uh and pass and like did the thing that the user asked for and the test said no you failed because you weren't supposed to be able to do that. Um but the agent had been smarter than the rules that it was in. Um so you have to expect that uh when you are building eval that sometimes the agent is going to come up with a solution to the problem that you did not expect. So your tests have to be very flexible.

</details>

### 评估结果的结构与闭环工作流

**演讲者**：通常情况下，一个标准的评估结果包含三要素：分数（score）、标签（label）以及解释（explanation）。分数通常是一个数字，常见的是简单的 0 或 1；标签是供人类阅读的对应含义词汇，比如“通过（pass）/ 失败（fail）”、“可执行（actionable）/ 不可执行（not actionable）”。

<details>
<summary>Original English</summary>

**Speaker**: Um here's what an eval result generally looks like. Uh it comes with a score, it comes with a label and it comes with an explanation. The score is a number usually just zero or one. Uh and the label is just a word that the human can read that matches what the score means. Uh so stuff like pass and fail, actionable and not actionable.

</details>

**演讲者**：而大模型裁判额外增加的第三个要素——解释，阐明了为什么会给出这个得分与标签。这正是大模型裁判最核心的价值所在。这份解释不仅直击痛点，指出哪里出错了、遗漏了什么关键信息，更在很大程度上直接提示了你该如何去修改提示词以修复问题。

<details>
<summary>Original English</summary>

**Speaker**: Uh and LLM judges add a third thing which is an explanation of why you got the score you did, why you got the label you did. Um and it is the most valuable part of an LLM judge. Uh because the explanation is where the value is. It tells you what was wrong and what was missing and it tells you a a lot of the time what to fix in your prompt to get this right.

</details>

**演讲者**：当进行大规模评估时，这一点的价值尤为显著。你可以从大模型那里收集到 50 条、100 条乃至上千条解释，然后让另一个大模型去通读并汇总这些解释：“看样子这些错误原因中存在某种固定模式，我们可能遇到了系统性问题。”接着你只需把这些反馈喂回给你的 Agent，Agent 便能自动解析：“我看到有 50 条链路追踪都具有相同的报错原因解释，我知道该如何去修复它了。”

<details>
<summary>Original English</summary>

**Speaker**: Uh this is especially useful when you're running your evals at scale because you can get, you know, 50, 100, a thousand explanations from your LLM and you can get another LLM to read all of those explanations and be like, it looks like there is a pattern in these explanations. It looks like we have a systematic problem. And you can just feed them to your agent and your agent goes, okay, I see 50 traces all doing the same all with the same explanation of what went wrong. I can fix it.

</details>

**演讲者**：这就是我们今天将要搭建的闭环工作流：对 Agent 进行链路追踪（Trace）；审查它的具体行为；针对核心关键指标编写评估规则；验证这些评估本身是否准确可靠；随后修改 Agent 并验证改进确实奏效；最后，将其集成并固化进持续集成（CI）流程中，确保修复成果被长久锁定。

<details>
<summary>Original English</summary>

**Speaker**: Um, so this is the loop that we're going to be building today. We're going to trace your agent. We're going to read what it did. We're going to write evals for what matters. Uh, we're going to check that those eval can be trusted. Uh, then we're going to change the agent and we're going to prove that the change worked. Then we're going to lock that in so that it stays fixed by putting it into CI.

</details>

### 环境配置与实战项目介绍

**演讲者**：那么，现场还有谁需要配置环境的协助吗？谁刚才迟到了还没配好环境？请举一下手。好的，让我切换回配置引导屏幕，看大家能不能跟上。没错，就是屏幕上这个专属 URL。如果你还没打开它，只需通读 README 并执行其中的安装说明，或者直接把 README 丢给你的 AI Agent，让它帮你把所有配置全部搞定。在 2026 年做技术演示的奇妙之处正在于此：我们可以一步步手把手演示如何操作，也可以直接告诉你如何让自己的 Agent 把所有脏活累活全给干了。我们在日常工作中也多半是这么做的。

<details>
<summary>Original English</summary>

**Speaker**: So, uh, who still needs help getting set up? Who walked in late and needs set up? Show of hands. Okay, let me head back to the setup screen and see if you can get it. Right, this is the magic URL. If you haven't got this one, uh, all you have to do is read the readme and, uh, run the instructions or just, you know, paste the readme into your agent and your agent will read the instructions and get it all done for you. One of the weird things about doing tutorials in 2026 is that we're just like, well, I could show you how to do all of this stuff, or I could just tell you how to tell your agent to do all of this stuff. Uh, and that's what we do a lot of the time.

</details>

**演讲者**：好了，我现在假定大家都已经拿到了那个 URL。太棒了。那么我们从第一步开始。第一步就是链路追踪（tracing）。在进行任何维度的评估之前，你必须先捕获到赖以运行评估的底层数据，这就是 Traces。今天我们将会使用 Phoenix。想必到目前为止这并不会让任何人感到意外。Phoenix 是 Arize 出品的开源 AI 可观测性平台。无论你使用什么开发框架构建 AI 应用，它都能收集其链路追踪信息；它会将你的评估结果直接保存在对应的追踪记录旁边，并提供直观的 UI 供你逐层深入下钻探查。它还支持数据集管理与对比实验，这也是我们今天课程会讲到的内容。而且它是完全运行在你本地笔记本电脑上的，因此你可以保持完全私有，也可以将其部署在服务器上与团队协作共享。

<details>
<summary>Original English</summary>

**Speaker**: All right, I'm now going to assume that everybody has that URL. Cool. So let's start with step one. Step one is tracing. Before you can evaluate anything, you need to get the data to run the to run the evaluations on. And that is what that is traces. Today we are going to be using Phoenix. I hope that's not a surprise to anybody by now. Uh, Phoenix is ARIS's open-source AI observability platform. Uh, it collects traces from your AI AI app with in whatever framework you use to build it. It stores your evals next to those traces. Uh, and it gives you a UI to dig through all of it. It also does data sets and experiments, which we're going to be talking about today. Uh, and you run it on your laptop. So, uh, you can keep it entirely private to yourself, or you can run it on a server and share it with your team.

</details>

**演讲者**：现在我要冒险尝试切屏看看……噢，这个字体太小了，我把它放大一些。好的，我们今天实战所采用的技术栈是 TypeScript。虽然社区里有大量 Python 的范例，Phoenix 本身也拥有非常成熟优秀的 Python SDK，但我个人更偏爱 JavaScript，所以我们将采用 TypeScript。这个代码仓库由一套轻量脚本组成：`instrumentation.ts` 负责初始化并配置链路追踪；`agent.ts` 是 Agent 自身的核心逻辑；`prompts.ts` 则集中管理所有的提示词模板。这些文件都在哪里呢？找到了，就在这里。接下来……

<details>
<summary>Original English</summary>

**Speaker**: So now I'm going to dangerously see if I can actually Oh, that's so that is so small. Let's make that bigger. Okay, so what we're working in today is Typescript. Uh you'll see a ton of examples in Python and Fenix has great Python SDKs as well. Uh but I like JavaScript so we're going to use TypeScript. Um the repo is a small set of uh scripts. Instrumentation.ts sets up tracing. Agent.ts is the agent itself. Prompts.ts has the prompts. Uh where are all of these things? There we go. Um and

</details>

<!-- chunk 3/13 -->

### 项目结构与金融分析 Agent 介绍

**讲师**：大家后续会在这个文件夹——抱歉，是在这个文件中编辑 Prompt。另外，`evals` 文件夹用于存放我们的评估测试，而 `queries.json` 则是我们的测试数据集。希望今天大家的每一步操作都只需要执行一条 npm 命令。每一个步骤都是独立的，所以如果你落后了，完全可以直接跳到下一步，并使用我在代码仓库中预先提供的初始数据（seed data），这样就不会跟不上了。

<details>
<summary>Original English</summary>

**Instructor**: You'll be editing the prompts in this folder. Sorry, in this file. And the `evals` folder is where our evals go. `queries.json` is our test data. Hopefully every step today is just going to be one npm command. Each one stands on its own, so if you fall behind, you can skip straight to the next one and use the seed data that I put in the repo so that you don't get left behind.

</details>

**讲师**：我们今天要做的事情——或者说我已经为大家构建好的——是一个金融分析 Agent。它的运作方式是：你提供一个股票代码和一个关注方向（比如特斯拉的汽车交付量），它就会自动在网络上搜索实时数据，并针对该主题为你撰写一份分析报告。市面上甚至有许多初创公司就是专门基于“为你提供是否应该买入某只股票的金融分析”这一理念建立的。但我们今天这个 Agent 故意做得非常简陋，因为我需要它产生一些错误，这样我们才能在后续环节中去修复这些错误。

<details>
<summary>Original English</summary>

**Instructor**: So what we're building today, or indeed what I've already built for you, is a financial analyst. How it works is you give it a stock ticker and something to focus on like Tesla vehicle deliveries, and it will go and search the web for live data and write you a report about that. There are whole startups built on this idea of giving you financial analysis of whether or not you should buy a stock. But ours is deliberately simple because I needed something that would make mistakes so that we could fix the mistakes.

</details>

**讲师**：今天重点并不是教你如何从零构建一个 Agent。我已经把 Agent 写好了。我假设大家手头已经在某个地方运行着自己的 Agent，而你们真正想要的是获得帮助，以使其运行更加稳定可靠。我们的 Agent 分为两个轮次（turns）工作：首先是一个调研轮次，在此轮次中它会在网络上进行检索；接着是一个报告撰写轮次，它会根据检索到的调研结果撰写分析报告。

<details>
<summary>Original English</summary>

**Instructor**: Today is not about how to build an agent. I've just built the agent for you. I assume you've already got an agent running somewhere and what you want is help on making it reliable. Our agent works in two turns. It has a research turn where it searches the web, and then it has a report writing turn where it takes the research and it writes the report about it.

</details>

### 技术栈与可观测性（Tracing）集成

**讲师**：我是使用 Claude Agent SDK 构建这个 Agent 的。如果你之前没用过，它是 Anthropic 推出的 Agent 框架。它实际上与 Claude Code 底层运行的是同一套引擎，这点在稍后会显得尤为重要，尤其是当你正使用 Claude Code 来配合操作时——因为两套不同版本的 Claude Code 往往会互相尝试协作，导致它们在评估测试中“作弊”，这可帮不上什么忙。该 SDK 提供了工具调用、网络搜索以及跨轮次持续对话等功能。

<details>
<summary>Original English</summary>

**Instructor**: I've built it using the Claude Agent SDK. If you haven't used it, that is Anthropic's framework for agents. It is the same engine that runs underneath Claude Code, which is going to become relevant later, especially if you're using Claude Code to work with it, because the two versions of Claude Code tend to try to cooperate with each other and that makes them cheat the eval, which is not very helpful. It gives you tool use, web search, and conversations that carry on across turns.

</details>

**讲师**：除了这个 SDK，我们还兼容市面上的许多其他方案，比如 Vercel AI SDK、Mastra、LangChain 以及 OpenAI 的 Agent SDK。Phoenix 为你能想到的所有框架以及所有 LLM 供应商都提供了适配器（adapters）和插桩（instrumentation）。无论你的 Agent 是用什么构建的，Phoenix 都能与其协同工作，并且插桩过程完全是自动化的。我今天只是为了演示需要挑一个，所以选了这个。

<details>
<summary>Original English</summary>

**Instructor**: There are also lots of other options that we are compatible with: the Vercel AI SDK, Mastra, LangChain, OpenAI's Agent SDK. Phoenix has adapters and instrumentation for every possible framework that you can think of and every LLM provider that you can possibly think of. Wherever you have built your agent in, Phoenix will work with it and the instrumentation will happen automatically. But I had to pick one for a demo, so I picked this one.

</details>

**讲师**：接入追踪（tracing）只需要大约五行代码。首先，我们要调用 `@arizeai/phoenix-otel` 包中的 `register` 函数，它会设置好链路追踪并将其指向 Phoenix。该行业的一个好现象在于，几乎所有人都在使用相同的插桩标准。整个行业都建立在 OpenTelemetry 之上，而在 OpenTelemetry 之上还有一个名为 OpenInference 的标准（由 Arize 负责维护）。各大框架早已在内部内置了这种插桩能力。

<details>
<summary>Original English</summary>

**Instructor**: Tracing takes about five lines. First, we're going to call `register` from the Phoenix OTel package that sets up tracing and points it at Phoenix. One of the good things about the industry is that everybody has pretty much picked the same instrumentation standard. Everything is built on OpenTelemetry in the industry, and on top of OpenTelemetry there is a standard called OpenInference, which Arize takes care of. And everybody has already built the instrumentation into their frameworks.

</details>

**讲师**：正因如此，我们才能兼容所有这些主流框架。你所要做的就是使用这个 `register` 命令，相当于在说：“嘿，把你已经内置在框架里的插桩功能打开，并把数据推送到这边来。”在这个案例中，你只需要将数据指向你本地的笔记本电脑即可，除此之外不需要做任何多余的操作。现在，我们 Agent 发起的每一次调用都会被追踪记录下来。

<details>
<summary>Original English</summary>

**Instructor**: That is why we are compatible with all of those frameworks. All you have to do is use this `register` command to say, "Hey, that instrumentation that you've already built into your framework, turn it on and point it over here." In this case, you're just going to point it at your laptop, and that's all you have to do. Every agent call that our agent makes is now going to be traced.

</details>

**讲师**：这样做的好处在于，我们不必为每一次单独的模型调用都手动去写日志行，也不必为 Agent 做的每件事都手动编写追踪代码，它完全会自动进行。当然，有时候我们会希望添加一些额外的元数据信息，该框架对此也提供了完美的支持，但你绝对不需要每件事都手动处理。

<details>
<summary>Original English</summary>

**Instructor**: So the good thing about this is that we don't have to write a log line for every single call. We don't have to write a trace for every single thing our agent does. It's just going to do it automatically. Sometimes we will want to add additional information and the framework absolutely supports that, but we don't have to do it for every single thing.

</details>

### TypeScript 插桩避坑点与 Agent 配置

**讲师**：在 TypeScript 版本中有一个大家必须留意的坑（gotcha）：你应该使用 `manuallyInstrument`，它会返回一份经过插桩处理的实例副本，并且后续你必须使用这个返回的副本。原因在于 Claude Agent SDK 是一个 ES Module，而 ES 模块的导出是只读的。因此，插桩工具无法像在 Python 中那样直接动态替换内部对象并全局修改一切；你必须显式使用它返回的那个已经替换了插桩的副本。如果你不使用它给你的副本，代码不会报错崩溃，但它就是不会记录任何追踪日志。因此，在这个代码仓库中，我们到处都是从我们自己的插桩文件中导入 Claude Agent SDK，而绝不直接从原始包中导入。

<details>
<summary>Original English</summary>

**Instructor**: There's one gotcha in the TypeScript version that you should know about, which is that you should use `manuallyInstrument`, which will hand you back a copy of the instrument, and you should use the copy of the instrument, because the Claude Agent SDK is an ES module and ES module exports are read-only. So the instrumentation can't do the thing like it can do in Python where it swaps out your instrument and just changes everything. You have to use the copy that it gives you which has that instrument swapped out. It won't break; it just won't log anything if you don't use the copy that it gives you. So everywhere in this repo we import Claude Agent SDK from our instrumentation file, never straight from the package.

</details>

**讲师**：现在如果你打开 `agent.ts`，就会看到我们 Agent 的各项配置选项。我们首先会使用 Claude Haiku 3.5（注：口误提为 Haiku 4.5），因为它速度很快、成本非常低廉，而且处于一种“恰到好处的低智”状态。即使是在相对简单的 Agent 架构下，它犯下的错误也是非常规整且易于预测的。而前沿顶级模型虽然肯定也会犯错，但往往需要非常复杂的 Agent 和极为复杂的任务场景才会暴露，这在现场演示时会增加不少麻烦。

<details>
<summary>Original English</summary>

**Instructor**: Now if you open `agent.ts`, you'll see our agent's options. We're going to start using Claude Haiku 4.5 because it is fast, it is cheap, and it is sort of usefully dumb. It makes mistakes that are nice and predictable even with a relatively simple agent, unlike the frontier models which will still definitely make mistakes, but you have to have quite a complicated agent and quite a complicated set of tasks, and it makes it harder for the demo.

</details>

**讲师**：如果你之前没接触过这些配置项：`allowedTools` 赋予了它网络搜索的能力，这样它才能查到最新的金融数据；而权限模式 `permissionMode: 'dontAsk'` 意味着它将以非交互模式运行，它不会中途停下来向你提问确认，因为在自动化运行环境中并没有人工坐在那里去点“同意”。这个配置选项稍后会和一种特定的失败模式密切相关。

<details>
<summary>Original English</summary>

**Instructor**: If you've not used it before, `allowedTools` is giving it web search so it can find the current financial data. And the permission mode `dontAsk` means that it's going to not be interactive. It's not going to pause and ask you questions because there's nobody there to say yes. That option is going to become relevant to a failure mode later.

</details>

**讲师**：另外还有三个配置选项，正如我之前提到的，它们的作用是将你宿主机环境与 Agent 完全隔离开来。Claude Agent SDK 运行的引擎与 Claude Code 相同。如果你刚好是在 Claude Code 内部执行这些代码，它往往会自动继承你配置给本机 Claude Code 的选项、工具和技能，而不是使用它自身隔离副本的环境。这往往会以一种毫无益处的方式导致极度不可控的不确定性。因此我在代码中加了几行逻辑，确保该 SDK 在完全独立的隔离沙盒中运行，不会盗用你本机的数据、密钥或环境配置。顺便说一句，这并非 Phoenix 特有的问题，而是同时使用 Claude SDK 和 Claude Code 时必然会面临的潜在冲突。

<details>
<summary>Original English</summary>

**Instructor**: And the other three options, like I mentioned, they keep your laptop out of the agent. The Claude Agent SDK runs the same engine as Claude Code. So if you're doing this in Claude Code, it tends to pick up the options, the tools, and the skills that you've given to your copy of Claude Code instead of its copy of Claude Code, which tends to make things extremely non-deterministic in an unhelpful way. So I've thrown in a couple lines of code there that make sure that the Claude SDK is running in its own isolated version of the Claude SDK and not stealing your copies of keys and things from your data. Right, none of that is Phoenix-specific, by the way. That is just a danger of using the Claude SDK at the same time as you're using Claude Code.

</details>

### 双轮次交互、Span 聚合与动手运行

**讲师**：在这个 SDK 中，一个轮次对应一次 `query` 调用。你向它传入 Prompt，随着 Agent 的工作推进，它会以流式方式返回各类消息：它进行思考、调用工具、读取工具执行结果，可能还会调用下一个工具；当一切结束后，你会收到一条包含最终文本和 `sessionId` 的结果消息。这个 `sessionId` 就是我们延续多轮对话的关键机制所在。

<details>
<summary>Original English</summary>

**Instructor**: In this SDK, one turn is one `query` call. So you give it a prompt. It streams back messages as the agent works. It thinks, it calls a tool, it reads the result, it maybe calls another tool, and when it's finished you get a result message with the final text and a `sessionId`. The `sessionId` is how we carry on the conversation.

</details>

**讲师**：如果我们将这个 `sessionId` 作为 `resume` 参数传回，下一轮对话就能完整记住上一轮所看到的一切。这就是我们实现“先做调研，再下达‘请基于这些调研结果写一份报告’指令”的机制——因为它知道自己处于同一个会话中，能够访问到前一轮刚刚生成的调研资料。

<details>
<summary>Original English</summary>

**Instructor**: If we pass it back in as `resume`, the next turn remembers everything that the last turn saw. So that's how we can do the research and then say, "Hey, write a report on this research," because it knows that it's in the same session, and it can find the research that the previous turn just created.

</details>

**讲师**：接着，我们将这两个轮次串联在一起，这样就可以把它们记录在同一个 Trace 链路中。先执行调研轮次，再执行报告撰写轮次，并通过恢复调研轮次的会话，让撰写者能够看到调研者发现的所有信息。随后，我们使用 `traceAgent` 将整个过程包裹起来。我们之所以这么做，是因为这样能生成一个包含所有数据的父级 Span（parent span）。如果不这么包装，在 Phoenix 中就会呈现出两个并列的兄弟级 Span，虽然也能看，但在阅读层级上会稍微费劲一点。所以我们现在先调整好数据结构，好让后续分析更加轻松。

<details>
<summary>Original English</summary>

**Instructor**: Then we put the two turns together so we get the two turns in one trace: first the research turn, then the writing turn, resuming the research turn session so the writer can see everything the researcher found. And then we wrap the whole thing in `traceAgent`. The reason we do that is because it gives us one parent span that encompasses all of the data. If we didn't do that, we would get two sibling spans in our Phoenix, which would be fine, but slightly harder to read. So I'm just shaping the data now to make our lives easier later.

</details>

**讲师**：现在，大家如果打开 `prompts.ts`，会发现里面写了一堆 Prompt。它们是故意写得很烂的：只有一行调研指令，以及一行撰写指令。我之所以故意这么写，是因为这能给我们后续留出充足的优化空间。如果你正在跟着动手写代码，现在就可以开始尝试调整这些 Prompt 了。大家可以随意修改，比如加上类似“绝对不能犯错”或者“如果你做得好我会给你 100 美元小费”之类的提示词——据说这些确实挺管用。我希望在场的每个人最终微调出的 Agent 都略有不同，这样我们就能获得不同的实验体验，在后续对比交流时也会更加有趣。

<details>
<summary>Original English</summary>

**Instructor**: Now, if you open up `prompts.ts`, you'll see that there are a bunch of prompts in there. They are deliberately bad. There's one line of research instructions, one line of writing instructions. And I did that on purpose because it gives us lots to improve later. If you're coding along, now is the time to start playing with things. Feel free to change them. Add stuff like "make no mistakes" or "I will tip you $100" — allegedly those help. What I want is everyone in the room to end up with a slightly different agent so that we get different experiences, which will make comparing notes more interesting.

</details>

**讲师**：如果你一直跟着操作并且环境与依赖都安装无误，现在应该就可以运行它了。大家可以运行命令：`npm run agent -- Tesla "growth outlook"`。当然，你可以针对特斯拉进行分析，也可以换成任何你想看的其他公司。程序运行可能需要一到两分钟的时间，因为它确实必须联网执行实际的搜索与分析任务。

<details>
<summary>Original English</summary>

**Instructor**: So now if you've followed along and you've installed everything and everything is going fine, you should be able to run it. You should run `npm run agent -- Tesla "growth outlook"`. You can do it on Tesla, you can do it on some other company if you like. It will take a minute or two because it really does have to...

</details>

<!-- chunk 4/13 -->

### Agent 的不确定性与评测需求

**讲师**：它实际上会去搜索网络，而大家现在用的是会场的 Wi-Fi。模型会进行几轮推理。在它为你们运行的过程中，实际发生的事情是：Agent 接收到了研究提示词。它判断自己需要进行搜索，这是一次工具调用（tool call）。接着它读取搜索结果，判定当前获取的结果是否充分，或者是否需要再次搜索。正是这一点让它成为了一个 Agent。我们并没有硬性规定它必须搜索网络多少次，也没有具体指定它必须去搜什么内容。Agent 完全是在自主做出这些决策。

<details>
<summary>Original English</summary>

**Speaker**: actually search the web and you're on conference Wi-Fi. And the model will do a few rounds of reasoning. What's happening here while that's running for you is the agent gets the research prompt. It decides that it needs to search, which is a tool call. It reads the results, decides whether it has enough results or whether it needs to search again. And that is the thing that makes it an agent. We haven't specified how many times it needs to search the web. We haven't specified what it needs to search the web for. The agent is making those decisions by itself.

</details>

**讲师**：因此，我们每个人运行的 Agent 所做出的决策都会略有不同。它们会使用稍有差异的搜索词，搜索的次数大概率也不一样。等这一切完成之后，撰写阶段开启，它会把搜集到的所有内容汇总成一份报告。所以从设计机制上讲，Agent 走的执行路径本身就是非确定性（nondeterministic）的。即便你把同样的任务运行两次，可能两次生成的报告表现都不错；也可能一份写得极好，另一份却漏洞百出，而你根本无法仅凭输入去预测输出。这正是为什么我们需要评测（evals）。现在有谁已经拿到跑出来的完整报告了吗？有人拿到了吗？

<details>
<summary>Original English</summary>

**Speaker**: So all of our agents are going to make slightly different decisions about those things. They're going to use slightly different search terms. They're probably going to search a different number of times. And then once it's done, the writing turn starts and it turns all of that into a report. So the path the agent takes is nondeterministic by design. Both reports might be fine if you run it twice, or one might be great and one might be wrong, and you can't predict that output from the input. Which is why you need evals. Who's got an actual report yet? Anybody?

</details>

**受众**：还在跑着呢。

<details>
<summary>Original English</summary>

**Audience**: Still running.

</details>

### 权限缺失与追踪排查

**讲师**：好的，我们还有时间。让我大着胆子，亲自在本地跑一下试试。我们会看到 Agent 遇到的一个典型问题：我们让它写一份报告，但并没有指明把报告写到哪里。于是它就自作主张，以为自己应该把报告写进一个文件里。看，跑出来了，大家可以看到我这边的输出：“我需要写入财务报告文件的权限。您希望我直接在这里显示报告吗？”这完全帮不上忙。Agent 根本不理解自己处于一个无权限的环境中，也不明白我其实是希望它直接将报告打印输出到命令行。这是因为我的提示词本身存在歧义。不过，有时它又不会这样，偶尔它自己能领会过来，直接把报告呈现给你。这就是我们刚才讨论的非确定性。

<details>
<summary>Original English</summary>

**Speaker**: Okay, we've got time. Let me be brave and actually try running it myself. One of the problems that we're going to see that the agent runs into is that we told it to write a report, but we didn't tell it where to write a report. And so it assumes that it should be writing the report to a file. There we go. So you can see mine. "I need permission to write the financial report file. Would you like me to display the report here?" This is completely unhelpful. The agent does not understand that it is running in a no permissions environment and that I wanted the report actually output to the command line. And that is because my prompt is ambiguous. But sometimes it doesn't do that. Sometimes it does just figure it out and give you the report. So that is the nondeterminism that we're talking about.

</details>

**讲师**：那么，我们来看看 Phoenix 从这一切中捕获到了什么。这是我的 Phoenix 101 项目，这里有我的财务报告记录，Trace（链路追踪）就是这个样子的。你可以清晰地看到 financial report agent 的运行轨迹，以及 Claude Agent 的两次调用。其中一次是研究报告阶段，你能看到它在内部调用工具去搜索，探测自己拥有哪些可用工具；接着它发现自己拥有网络搜索工具，于是连续执行了三次不同的网络搜索。你不仅能看到每一次的输入和输出、具体的查询语句是什么、每次工具调用返回了什么结果，还能看到它在这次执行中失误了：它生成了一份报告，随后试图把它写到我电脑的某个文件路径上，接着报告无法执行。

<details>
<summary>Original English</summary>

**Speaker**: So let's see what Phoenix captured from all of this. Here is my Phoenix 101. There is my financial report. This is what a trace looks like. So you can see the financial report agent running and you can see the two invocations of the claude agent. One is the this is the research report. You can see tool searches inside of it to find out what it's got available to it. You can then see it finds that it's got a web search tool. So it conducts three different web searches. You can see the inputs and the outputs. What the exact query is, what output it got from each tool call. And then you can see that it messed up in this case. It wrote a report and then it tried to write it to a file path on my computer and said that it couldn't work.

</details>

**讲师**：这里最关键的一点在于：我们根本没有给 Agent 额外添加任何日志代码。所有的这些信息、关于系统运行状态的所有极具价值的细节，在无需我们进行任何额外配置的情况下全部自动呈现了出来。我们没有特别交待“喂，你的工具需要埋点插桩”，也没有特别要求“你的网络搜索需要埋点插桩”。这一切完全是 Claude Agent SDK 自带的能力，因为它已经为我们完成了开箱即用的观测插桩。在 Phoenix 中，你可以点击进入任何一个 Span，查看关于系统底层执行的大量详尽数据。

<details>
<summary>Original English</summary>

**Speaker**: The important thing here is that we didn't have to add any logging to our agent. The important thing here is that all of this showed up, all of this very useful information about what's going on without us doing anything. We didn't say hey your tools need to be instrumented. We didn't say hey your web searches need to be instrumented. All of that just happens as part of the claude agent SDK because it's already instrumented for us. And you can click into any span in Phoenix and you can see an enormous amount of data about what's going on.

</details>

**讲师**：至于为什么会出现这种情况——它试图写入磁盘随后报错失败，原因在于我们之前配置了 `don't ask`（无需询问）参数。我们给它的设定是进行无人值守运行，指示它“不要向我提出任何确认问题”。它确实在没有任何人工干预的情况下径直往下跑，最终搞砸了。但是，如果你无法查看调用链路追踪，你根本不可能知道发生了什么，对吧？你只会收到一个莫名其妙的报错提示，说某些地方出了问题。只有在链路追踪中，你才能看清是哪一次工具调用发生了错误，才能看清它试图去做某些未被授权的操作。

<details>
<summary>Original English</summary>

**Speaker**: And the reason that all of this happened, the reason that it's trying to write to disk and then failing is because we gave it that don't ask setting. We told it you're going to be running unattended. Don't ask me any questions. It ran without asking any questions and then it messed up. But you wouldn't know that if you hadn't been able to look at the trace, right? You just would have got a mysterious output where it says something was wrong. The traces are where you can see that the tool call is failing. The traces are where you can see it's trying to do something that it's not been given permission to do.

</details>

### Span 数据结构与批量测试

**讲师**：这些详细信息正是存储在 Span 里的内容。Span kind 会标明当前步骤的类型：比如它是一个 Agent、一个工具调用、一次 LLM 生成等等。在工具调用和网络搜索这类步骤中，你可以看到我们的输入格式实际上是 JSON。这正是我们构建首个评测（eval）的基础，因为它为我们提供了结构化数据。除此之外，你还能获得执行耗时以及 Token 消耗量等关键指标，通常你的 Agent 还会把相应的成本开销记录下来。稍后我们编写评测逻辑时，要提取出来并进行评分打分的，就是这些字段。

<details>
<summary>Original English</summary>

**Speaker**: And that is the kind of stuff that lives in a span. So the span kind tells you what type of step it is. So it's an agent, a tool call, an LLM and so on. And in a tool call and a web search and things like that, you can see that our input is in fact JSON. And that's going to make our first eval because it gives us some structured data. You also get things like timing and token counts. And often your agent will record what it costs. When we write eval in a bit, these are the fields that we're going to pull out and grade.

</details>

**讲师**：到目前为止，大家各自只执行了一次测试。单次运行的数据量太少，根本不足以得出任何可靠结论。因此，我现在需要大家执行 `npm run batch` 命令，它会连续并发跑 15 个查询任务。这需要耗费一点时间，在它运行的同时，我继续往下讲。这个脚本每次并发跑 5 个请求，在现场的 Wi-Fi 条件下，乐观估计需要三到四分钟。大家现在就把它启动起来吧。

<details>
<summary>Original English</summary>

**Speaker**: So, you've run one test so far. That is not enough data to draw any conclusions from. So what I want you to do now is run `npm run batch`, which will run 15 queries in a row. That will take a little while. So I'm going to talk while you're doing that. It runs five at a time. It takes three or four minutes optimistically on Wi-Fi. So start it now.

</details>

**讲师**：如果因为网络等任何原因执行失败了，也不必担心。大家之前加载的种子项目中包含一个名为 `Phoenix 101 golden` 的工程，里面保存了我先前在稳定 Wi-Fi 环境下预先跑好的 16 次运行记录。如果你本地的批量任务跑不起来，直接用那些数据也是一样的。

<details>
<summary>Original English</summary>

**Speaker**: If it fails for whatever reason, don't worry about it. The seed project that you loaded earlier is called Phoenix 101 golden, and it has my 16 runs that I did earlier on reliable Wi-Fi on it. So, you can use those instead if you can't get your batch to run.

</details>

### 测试用例设计与边界测试

**讲师**：这里列出了一些具体的测试查询样本。里面既有像苹果（Apple）、英伟达（Nvidia）和亚马逊（Amazon）这样常规明确的目标，也有一些我特意埋进去让系统暴露出问题的边缘用例（edge cases）。比如，其中一条查询要求它对比苹果与微软，这显然比单纯分析单家公司要复杂得多；还有一条是关于 Rivian 的，而 Rivian 当时并不是上市公司，因此公开可查的数据要远远少于上市公司；再比如可口可乐（Coca-Cola），它的商业模式与科技公司截然不同；还有一条查询里的 `ZZQ` 根本不是真实的股票代码，完全是我随手捏造的。

<details>
<summary>Original English</summary>

**Speaker**: Here are some examples of the queries. There are obvious ones like Apple, Nvidia, and Amazon. And then there are some edge cases that I put in there to make things fall over. So one asks it to compare Apple and Microsoft, which is harder than just covering one company. One is about Rivian, which is not a public company. So there's much less data out there than it does about public companies. Coca-Cola is a very different type of company from a tech company. And ZZQ isn't a real ticker at all. I just made it up.

</details>

**讲师**：设置伪造股票代码的目的，就是为了观察 Agent 在面对无法识别的代码时会有何反应。它会凭空捏造一家虚假公司？还是会主观臆测你可能指的是哪家公司？抑或是给出我所期望的标准答案——明确指出“该股票代码不存在”？此外，还有一条关于特斯拉的查询，但提问的角度非常口语化：“老铁，这票现在能买吗（yo is it a buy right now?）”。因为真实用户就是这样向 Agent 发问的，他们习惯使用俚语口语，而且往往不会精准阐明自己究竟想要什么。所以，这些用例都非常贴近真实的用户输入场景。

<details>
<summary>Original English</summary>

**Speaker**: And that is to see what the agent does when it sees a ticker symbol that it doesn't recognize. Does it, you know, invent a company? Does it guess what company you mean or does it say what I'm hoping it says, which is that ticker doesn't exist? One of them is about Tesla, but the focus is "yo is it a buy right now?", because that is how real people send queries to agents. They do it in slang. And they don't often specify exactly what it is that they wanted. So these are all realish looking queries.

</details>

### 定义好与跨职能协作

**讲师**：正如我之前所强调的，在真正开始衡量指标之前，你必须先把“好”的标准白纸黑字明确下来。如果你连什么叫“正常运作”都没界定清楚，你就无从谈论你的 Agent 是否有效。那么针对我们这个分析师 Agent 而言，一份优秀的分析报告究竟应该满足什么标准？首先，它应该基于真实的最新数据；其次，分析的对象必须对应正确的公司；第三，结论必须严格忠于其实际检索到的客观事实；最后在我的场景要求中，我希望它能明确给出操作建议——直截了当地告诉我们究竟是该“买入”、“持有”还是“卖出”这只股票，而不仅仅是堆砌笼统的分析。

<details>
<summary>Original English</summary>

**Speaker**: And what you have to do is, like I said, you have to write down what good means before you measure it. You can't say that your agent doesn't work if you haven't specified what working means. So, for our analyst, what does a good report look like? It should use real current data. It should probably be about the right company. It should stick to what it actually found. And for my purposes, I want it to tell us what we should do. I want it to say buy or hold or sell this stock. I don't just want it to give me analysis.

</details>

**讲师**：这些要求一旦写成文档，听上去往往顺理成章、显而易见；但在写下来之前，整个标准可能非常含糊，团队中不同的人对于一个优秀的金融分析师 Agent 到底该做什么，也会各执一词。把标准落实在纸面上，才能将模糊的主观失望转化为可以被精准量化测试的具体指标。今天，我们将把上述每一项具体需求，逐一转化为可落地的评测项（eval）。

<details>
<summary>Original English</summary>

**Speaker**: Those sorts of requirements sound obvious once you've written them down, but before that, they could just be vague or different people on your team could have different ideas about what a good financial analyst agent would do. So writing them down turns vague disappointment into specific things that you can test and we are going to turn every single one of those requirements into an eval today.

</details>

**讲师**：定义“好”的标准绝不仅仅是工程开发人员一家的工作。如果你在为自己的业务产品制定这一标准，你必须与团队里的非技术利益相关者深入沟通，因为他们才是真正懂得业务标准的领域专家（domain experts）。作为一名工程师，对于什么构成优秀的 Agent 以及什么是优质的输出，你往往会有自己特定的预设假设与认知偏差，而这些预设并不总能与领域专家的视角保持一致。因此，在定义 Agent 的产品形态与评估标准时，直面客户业务的一线人员必须参与其中。另外，如果你当前缺乏真实用户，自己构造一些模拟用例也是极好的办法——你可以让大语言模型为你生成海量测试查询，并特意加入各种维度的表述变化：例如用“调研特斯拉财务表现”是一种问法，用“特斯拉股票最近咋样”是另一种问法，而用“老铁……”又是另一种风格。

<details>
<summary>Original English</summary>

**Speaker**: Defining good is not solely an engineering job. If you are defining good for your product, you have to talk to the non-technical stakeholders in your organization because they are the domain experts who are going to know what good looks like. You as an engineer are going to have specific guesses and biases about what makes a good agent and what makes good output, and you are not always going to agree with the domain experts. So the customer-facing people need to be in the room when you define what your agent looks like. It's also great if you don't have users that you can make some up. You can get an LLM to generate lots of test queries and vary them on purpose. So "research Tesla's financial performance" is one way to ask, "what's going on with Tesla stock" is another, and "yo..."

</details>

<!-- chunk 5/13 -->

### 合成数据与真实流量的价值

**讲师**：……询问“现在买入特斯拉怎么样”是其中三分之一的情况。接下来，你可以让人类去审查这个查询列表，因为大模型生成的这些查询虽然是为你提供初始种子数据的实用方式，但它们并不完美，这主要是由于大模型相对比较保守。它们往往不会像真正的人类用户那样天马行空、不着边际。人类用户的提问方式可能会是：“喂，告诉我我孩子的健康到底出了什么毛病”，而不是一本正经地向你索要一份财务分析报告，而你的智能体就必须设法去应对这类状况。

不过，合成数据确实是起步阶段极好的切入点。一旦你完成了冷启动，拥有了真实用户和真实业务流量，真实流量就成了测试智能体的黄金标准。你应当以最快的速度将其整合并沉淀到你的测试数据集中。

<details>
<summary>Original English</summary>

**Instructor**: is Tesla by right now is a third. Um then you can get a human to look at the list because LLM generated queries they are a useful way of seeding your initial data. They are not perfect u mostly because they are relatively conservative. They don't go as far a field as human users tend to actually go. Human users are like, you know, tell me what's wrong with, you know, my child's health instead of asking you for a financial analyst and you your agent has to have something to do with that. Um, but synthetic data is a great way to get started once you've got started and you have real users with real traffic. Real traffic is uh the gold standard for testing an agent. you want to get it incorporated into your data set as fast as you possibly can.

</details>

### 利用编程智能体与 CLI 自动集成追踪

**讲师**：在我们查看目前希望已经同步推送到各位笔记本电脑上的数据之前，先插一句题外话。我之前带着大家手动一步步实现追踪调用（Tracing），是因为大家必须理解它底层到底在做什么；但正如我刚才所言，你完全可以让你的编程智能体（Coding Agent）替你搞定这一切。

Phoenix 提供了一个非常出色的命令行工具（CLI）。只要在你的项目工程中运行它的设置命令（setup command），它就会指示你的编程智能体在你的应用程序中加入追踪逻辑，并且它会持续工作，直到你的应用成功安装并配置好追踪功能。你根本不需要自己费尽心思去琢磨怎么写注册命令（register command）以及诸如此类繁琐的细节。它在每一种编程语言中都能顺畅运行，表现极其优雅。

<details>
<summary>Original English</summary>

**Instructor**: Um, one aside before we look at the data that I'm hope hoping is arriving in your laptops right now. Um, I walked through tracing by hand because you should understand what it's doing, but you can, like I said, you can also get your coding agent to do all of this. Um, Phoenix has a really good CLI. Uh, and if you run it setup command in your project, it will give your coding agent um, it will get your coding agent to add tracing to your app. uh and it will work until your your app uh has tracing installed and you don't have to figure out how to add the register command and all of that stuff. It will work in every language. Uh it's really neat.

</details>

### 第二步：人工排查追踪记录与未知的未知

**讲师**：接下来第二步就是仔细审读你的数据。此刻你们有谁拿到数据了吗？请举手示意一下。一位，还有其他人吗？好的，太棒了，有几位拿到了，非常好！

在编写任何一行评测代码（Eval）之前，你必须亲自阅读你的追踪记录（Traces）。完完整整、端到端地阅读十几个甚至更多的追踪链路：输入到底是什么？输出究竟是什么？具体哪里出了问题？这听起来或许很人工、很原始笨拙，但这绝对是你所能做的极其高价值的事情。

当你构建一个智能体时，你必须进行人工检查以洞察内部运转的真实情况，唯有如此你才能揪出那些你预料之外的“未知的未知”（unknown unknowns）。Anthropic 团队就会定期聚在一起亲手阅读评测转录记录，甚至在内部专门打造了一整套工具来方便大家开展人工阅读。如果你在真正搞明白智能体会如何失败之前就盲目走向自动化，你最终衡量的只会是那些容易衡量的指标，而不是真正重要、切中要害的问题。

<details>
<summary>Original English</summary>

**Instructor**: So step two is reading your data. Who has any data at this point? Show hands. One person. Anybody else? Oh yeah. Cool. All right. Several people. Fantastic. Uh you have to read your traces before you write a single eval. Um reading a dozen or more of them end to end. Uh what was the input? What was the output? Um what specifically is wrong? This sounds manual and old-fashioned, but it's an incredibly high value high value thing that you can do. Um, when you're building an agent, uh, you have to manually inspect what is going on so that you can find things that you the unknown unknowns that you weren't expecting. Uh, Anthropics team regularly sits down and reads eval transcripts by hand uh, and have built a bunch of tooling internally to make that easy to do. [snorts] Um, if you automate before you understand how your agent fails, you're going to end up measuring what's easy to measure instead of what actually matters.

</details>

### 人工抽样与编程智能体分析的协同

**讲师**：因此，你必须阅读追踪记录，而我们待会儿就要开始做这件事。但是纯靠人工读追踪记录是无法无限扩展规模的。自己读 16 条追踪记录完全没问题，可要是面对 1600 条记录，虽然它们能提供大量极佳的数据，却得耗费你整整一周的宝贵时间。

不过事实证明，编程智能体在阅读追踪记录方面堪称高手。你可以把编程智能体指向你的追踪数据，让它们去寻找其中的诡异异常之处，让它们把分析脚本和工具编写出来。当然，它们找出来的东西并不总能完全契合你的预期，因此人工检查作为一种抽样手段，永远是一个绝佳的方法。

<details>
<summary>Original English</summary>

**Instructor**: Um, so you should read traces and we're about to do that. But reading traces doesn't scale. Reading 16 traces yourself is absolutely fine. Uh, but 1600 traces uh is going to give you a bunch of really great data and it's also going to take a week out of your life. Um, but it turns out that coding agents are aces at reading traces. Uh, so you can point your coding agent at your traces and get them to look for things that are weird in your traces. Get them to code stuff up. [snorts] Uh, but they're not always going to find what you expected. So manual inspection as a sampling technique always a really great idea.

</details>

### 安装 Phoenix 插件与错误分析技能

**讲师**：所以，如果你打算借助智能体替你分担工作，你需要根据自己使用的具体编程智能体来安装对应的 Phoenix 插件（plugin）或 Phoenix 技能（skill）。如果你手里还留着环境配置的 Readme 文件，这就是其中的最后一步，因此你们有些人可能已经安装过了。

针对 Claude Code，我们提供了一个只需运行两条命令即可搞定的插件；Cursor 和 Codex 也都有专属插件；对于其他任何编程智能体，都有现成的技能文件可用。这个插件会将你的编程智能体直接连接到你的本地 Phoenix 服务，并且它默认就已经指向了 localhost 606，因此完全无需任何额外配置。

此外，Phoenix 自身会向你的智能体提供一个名为“Phoenix 错误分析技能”（Phoenix error analysis skill）的能力，其中包含了关于如何规范执行错误分析的操作指南。安装过程大概只需 10 秒钟，我这里就不专门停下来等大家安装了。

<details>
<summary>Original English</summary>

**Instructor**: So, um, if you are using if you're getting the, uh, agent to do stuff for you, you want to install the Phoenix plugin or the Phoenix skill depending on which coding agent you're use you use. It was the last step in the setup readme if you've still got that. Uh, so you may have it already. Um, for cloud code, we have a plugin which is two commands. Uh, there are also plugins for cursor and codeex. Uh, and for any other coding agent, there is a skill file. Um, the plug-in connects your coding agent to your Phoenix. Uh, and it already points at localhost 606, so there's nothing to configure. Um, and Phoenix itself will hand your agent a skill called the Phoenix error analysis skill with instructions on how to do error analysis properly. Um, it should take about 10 seconds to install. Uh, and I'm not going to hang around waiting for you to install it.

</details>

### 启动智能体执行错误分类与回写标注

**讲师**：现在，请打开你的编程智能体，让它开始执行错误分析。如果你已经配置就绪的话——之前已经安装好这个技能的有哪些人？太棒了，我打算再次点你的名了。你已经让你的编程智能体开始跑任务了吗？

**学员**：好的，太棒了。

**讲师**：提示词（Prompt）就显示在幻灯片上。告诉它 Phoenix 的地址，命令它读取所有追踪记录，梳理归纳出失败的错误类型，统计各个类别的发生次数，并将各个错误分类作为标注（Annotation）回写并关联到 Phoenix 对应的追踪记录上。

所谓标注（Annotation），本质上就是附加在追踪记录上的可读文本字符串。它是一种为追踪记录增补上下文信息的机制，以便你本人或你的智能体在后续能弄清楚当时系统内部究竟发生了什么。你的插件在运行期间会弹出权限申请，请求允许调用 Phoenix 的工具，遇到这种情况直接点击允许（Yes）即可。

我自己之前运行这个流程时大概耗时 9 分钟，所以我暂时还不会马上抽查你的运行结果。另外，如果它请求往代码仓库里写入记录笔记，完全没问题，直接允许它把内容写入磁盘即可。

<details>
<summary>Original English</summary>

**Instructor**: Um, now open your coding agent and ask it to do the error analysis. Uh, if you've got it. Who's got who's got the skill installed from previously? Fantastic. I'm going to pick on you again. Can you have you asked your coding agent to do things?

**Participant**: >> Okay, great.

**Instructor**: Um, the prompt is on the slide. Tell it where Phoenix is. Tell it to read the traces. Come up with categories of failures. uh count them up and write each category back onto its trace in Phoenix as an annotation. An annotation is just a human readable string of text attached to a trace. Uh they are a way of adding additional information to traces so that either yourself or your agent can figure out what was going on. Um your your plug-in is going to ask permission to use Phoenix's tools. So you should say yes. Uh when I ran it, it took about 9 minutes. Uh, so I'm not going to pick on you quite yet. Um, uh, also if it asks to write notes into the repo, uh, that's fine. Just let it write stuff to disk.

</details>

### 实地排查案例：无效代码与不可操作的研报

**讲师**：现在，让我们回到 Phoenix 界面。我来冒个险，现场凭记忆敲一下我的搜索语法。哈，有了！大家看，这些全都是我之前跑出来的财务研报运行记录。我们可以直接点击查看其中的单个记录，看看能不能挖出几个有意思的典型例子。

先看 ZZQ 这个股票代码。我针对 ZZQ 的输出是什么来着？“ZZZQ 似乎不是一个有效或活跃的金融股票代码。”太好了，万岁！智能体准确执行了我们期望它做出的反应。

那么可口可乐（Coca-Cola）的表现又如何呢？首先，它一上来就进行道歉，说自己当前运行在受限模式下，无法直接写入文件——这显然是我们后续必须彻底修复的问题。随后它给出了分析结论：“可口可乐代表着一项高品质、低风险的股息投资标的……对于风险厌恶型投资者而言，KO 是一项优秀的长期收益载体。”这个例子可就很有嚼头了。

大家举手表决一下：有谁认为这是一份具备可操作性（Actionable）的研究报告？好的，我刚才其实已经给大家打过预防针了。它根本没有明确给出到底应该“买入”（Buy）、“卖出”（Sell）还是“持有”（Hold）的指令，仅仅是说它是一项良好的投资。这根本没有明确指导用户究竟该采取什么行动。对于这批研究报告，我设定的可操作性衡量准则是：它必须清晰地告诉我究竟是该买入、卖出还是持有该股票，绝不能模棱两可、含糊其辞。

<details>
<summary>Original English</summary>

**Instructor**: Now, let's look at Phoenix again. Um, I'm going to very dangerously try and remember my syntax for search. Ha. Okay, so these are all of my runs uh that are the financial reports. Uh we can click into individual ones of them. Let's see if we can find the interesting ones. Uh ZZQ, what was my output for ZZQ? ZZZQ does not appear to be a valid or active financial ticker symbol. Hooray. The agent did the thing that we were expecting it to do. Um how about uh Coca-Cola? First, it starts with the apology. It's running in restricted mode and it cannot write files directly. We're going to have to fix that definitely. Uh then it comes to a conclusion. Coca-Cola represents a high quality, lowrisk dividend investment. Um KO is an excellent long-term income vehicle for riskaverse investors. This one's going to be fun. Show of hands. Who thinks that this is an actionable report? [laughter] Okay, I primed you already. Uh it does not say buy, sell, or hold. So it just says that it's a good investment. That doesn't say what you should do. Uh I'm going to make my standard of actionability for these reports that it should tell me whether I should buy, sell, or hold the stock. I'm not going to leave it to be ambiguous.

</details>

### 权限越界与异常交互：Rivian 案例分析

**讲师**：在这一组数据集中，很多运行实例都表现各异。大家可以看到，这一个遇到了同样的毛病：它试图往磁盘写文件，结果执行失败了。

再来看 Rivian 的追踪记录，我之前特意做过笔记，提示 Rivian 的运行很值得玩味。找到了，就是这条。不知道为什么，它的输出里塞满了各种 emoji 表情符号。而且它一开篇居然反问我：“请问您需要创建研报文件吗？”——没错，正是这句。大家记得吧，我们在早些时候做现场实时运行演示时也遇到过这种情况。它反过来向我索要指令，但我明明已经预先明令禁止它这么做，向它强调过绝对不允许向用户提问，结果它偏偏还是违规发问。

所有这些形形色色的表现，都是各种不同维度的失败模式。这里面很多结果属于纯粹的失败，有些则勉强算过得去。

<details>
<summary>Original English</summary>

**Instructor**: Um a whole bunch of them do different things in this set. Uh you can see this one had the same problem. It tried to write to disk and it was and it was and it failed. Um, uh, the Rivian trace, I made a note that Rivian was interesting. There it is. Uh, it's full of emojis for some reason. Um, it opens by asking, "Would you like to Yes. Would you like to create the report file?" We saw that earlier when I ran it live. Uh, it's asking me to do things and it can't ask. I told it I told it it's not allowed to and it's asking to do things anyway. Um, all of these things are uh different ways of failing. Lots of these are failures. Lots of these are sort of okay.

</details>

### 特斯拉案例：荒谬的 116% 分析师共识与推理错误本质

**讲师**：但是，接下来特斯拉的案例才是尤其引人入胜的，具体来说就是那条询问“特斯拉现在值得买入吗”的记录。

在这一条记录中，智能体声称分析师的共识评级为买入。紧接着它写道：50% 的分析师建议买入，52.6% 的分析师建议持有，还有 13.1% 的分析师建议卖出——加在一起，给出意见的分析师总比例居然达到了惊人的 116%！而且它完全没有察觉到自己的基础数学计算已经荒谬透顶。

它底层究竟做了什么呢？原来它分别发起了两次不同的网页检索。在其中一次搜索中，它看到有 50% 的人持某种观点；在另一次搜索中，它又看到有 13% 的人持某种观点。它把这两次不同搜索抓回来的数据生拉硬拽地强行拼凑在一起，尽管这两组数据根本不是来自同一个统计样本集，最终硬生生凑出了 116% 的荒谬数字。不仅如此，它还以极其笃定的语气言之凿凿地写下“116% 的分析师持有相关观点”。

这恰恰是你在实际构建智能体时会频繁遭遇的典型智能体故障（Agentic Failure）：在犯下严重的数学低级错误后，依然“自信满满地给出了完全错误的答案”。如果你深入钻研这些网页检索的追踪细节，你就能清晰地追踪到它究竟是在哪些具体来源抓取了这些数据片段，以及它是如何把这些互不兼容的数据强行缝合在一起的。

因此，当你抓到一个系统失败时，你必须深究它之所以失败的根本原因。“答案给错了”只是表面病症，而不是底层病因。借助完整的追踪链路，你可以洞察系统真实输出背后的生成脉络：它是因为抓取到了劣质检索结果吗？如果是，那属于检索失败（Retrieval Failure），但眼前这起案例显然并非如此，这里的每一次网页搜索结果本身都是完全正常的。那么，是它拿到了正确的数据却推导出了错误的结论吗？如果是这样，那它就是不折不扣的推理错误（Reasoning Error）。而这正是本例中确凿无疑发生的事故，对吧？它分明观察到了两组截然不同的数据片段，却没有对它们进行合乎逻辑的正确推理。有时候它……

<details>
<summary>Original English</summary>

**Instructor**: Um, but then uh there's Tesla. Tesla is particularly fascinating. Uh specifically the yo is Tesla a buy right now one. So in this one uh it says that the analyst consensus is a buy. Uh it says 50% say buy, 52.6% 6% say hold and 13.1% say sell, which adds up to 116% of analysts saying things. And it did not catch that its math was completely wrong. What it did was it did two different web searches. One where it found 50% of people saying something, another one where it found 13% of people saying something. It took those two web searches and it munched them together even though they were not from the same data set and it came up with 116%. But it confidently wrote down that 116% of analysts say something. This is exactly the kind of agentic failure that you see. Uh it is confidently wrong having done uh bad math. Um if you go into these web searches, you can see the specific places where it got the data and how it uh put those things together. Um so when you find a failure, you have to ask why it failed. the answer was wrong is a symptom. It's not a cause. Um with the traces you can see what the actual answer was. Did it get bad search results? That would be a retrieval failure. That is not what happened here. This each search result was fine. Uh did it have the right data but the wrong conclusion? Then that is a reasoning error. That is uh definitely what happened here. Right? It saw two different bits of data and it did not reason correctly about them. Um sometimes it

</details>

<!-- chunk 6/13 -->

### 开放式编码与轴向编码：从 Trace 中诊断错误

**讲师**: 有时候模型会完全凭空捏造数字，那是幻觉（hallucination）。有时候它回答的并不是你问的问题，那是范围限定问题（scope problem）。每一种出错根因对应的修复方案都截然不同；但如果你不知道根因是什么，你也就无从下手去修复。这就是为什么阅读执行轨迹（traces）如此有用。

<details>
<summary>Original English</summary>

**Speaker**: ...will make numbers up completely. That is a hallucination. And sometimes it will answer a question that isn't the question you asked. So a scope problem. Each cause has a different fix. But if you don't know the cause, you don't know the fix. Which is why reading traces is useful.

</details>

**讲师**: 做这件事有一个非常棒的方法——我们切回到幻灯片。你应该“先写笔记，后归类别”。先通读所有的 trace，直接用自然语言把你看到的情况记录下来：“这里不好，因为它做了这个；那里很好，因为它做了那个。”这叫做开放式编码（open coding），这是从机器学习或质性研究领域借用来的术语。你只是在客观描述你看到了什么。

<details>
<summary>Original English</summary>

**Speaker**: Um there's a really great way to do this which is—let's switch back to slides. You should write notes first and categories second. So look through all of your traces and just write down in human language what you see happening. So this is bad because it does this. This is good because it does that. That is called open coding. Another term borrowed from ML. You're just saying what you saw.

</details>

**讲师**: 做完这一步之后，你就可以进行所谓的轴向编码（axial coding）。这时你再回过头去看刚才给自己写下的所有笔记，把它们归纳聚合到不同的类别中。作为一名工程师，非常容易忍不住想预先猜测会有哪些类别，从一开始就设定好类别然后硬往里套。因为那样看似省事，但结果往往会更差——因为你根本无法预先知道系统真正的失效模式（failure modes）会是什么。你预先挑好的类别要么太窄，要么太宽，要么根本就对不上实际出错的问题。

<details>
<summary>Original English</summary>

**Speaker**: Once you've done that, you can then do what is called axial coding where you look through all of the notes you've written to yourself and you group them into categories. It is very, very tempting as an engineer to try and guess in advance what the categories are going to be and come up with categories and just put things in categories from the get-go because that is less work, but you will do worse at it because you will not know in advance what your failure modes are going to be. So the categories you're going to pick are going to be either too narrow or too broad or just not the kind of stuff that actually went wrong.

</details>

### 评测的瑞士奶酪模型：构建多层防护体系

**讲师**: 顺便提一下，我之前讲过如何把代码评测（code evals）、LLM 裁判评测（LLM judge evals）和人工评测（human evals）层叠组合起来。这是借用自安全领域的一个模型，叫做“瑞士奶酪模型”（Swiss cheese model）。你部署的每一层防御都会有它的孔洞，你的每一个 eval 都会有它的盲区。你真正要做的是尽可能将多种不同的评测方式层叠在一起，使得错误极难一路穿透所有层级。

<details>
<summary>Original English</summary>

**Speaker**: While we're talking about this, I talked about how you stack up code evals and LLM judge evals and human evals. This is a model borrowed from the security world called the Swiss cheese model. Every layer of defense that you have is going to have holes in it. Every eval you have is going to have a blind spot. What you want to do is stack as many evals as you can on top of each other such that it is very hard for an error to get all the way through all of them.

</details>

**讲师**: 因为它们虽然都有漏洞，但孔洞的位置并不在同一个地方。如果你有足够多的 eval，运行着足够多不同类型的检查，它们就会层层互补，整体系统就会可靠得多。比如，代码评测能够精准捕捉格式问题，但会漏掉语义层面的问题；LLM 裁判能捕捉到推理逻辑断层，但可能会漏掉一些微妙的幻觉；人工往往能看出最细微的端倪，但人类不可能去肉眼审核每一个 trace。所以，没有任何单一方法可以包揽一切。

<details>
<summary>Original English</summary>

**Speaker**: Because they've all got holes, but the holes are not in the same place. So if you have enough evals, if you have enough different types of check going on, they will stack up on top of each other and be much more reliable. So code evals can catch formatting problems, but they will miss problems with meaning. LLM judges will catch reasoning gaps, but they will miss some subtle hallucinations. Humans will often catch the subtle stuff, but they can't look at every single trace. So no single method is going to catch everything.

</details>

**讲师**: 因此，我们今天要做的是构建几个小巧专注的 eval，而不是搞一个庞大笨重的大一统评测。这也是很多人初涉 eval 时的常见误区：人们一开始做评测总想着“我要把所有可能出错的情况全想出来，一股脑塞进一个巨大的 LLM 裁判里，让它找出所有毛病”。那其实是一种极度不可靠且极其复杂、根本解决不了问题的做法。

<details>
<summary>Original English</summary>

**Speaker**: So today we're building several small evals, not one giant super eval, which is also another failure mode. When people first get into evals, they're like, "I'm going to think of every possible thing that can go wrong and I'm going to cram it into one big LLM as a judge, and it's going to find everything." And that is a very unreliable and very complicated way of not solving the problem.

</details>

### 分析失效模式：框架泄露与严重程度优先级

**讲师**: Agent 会执行一整套复杂的动作，这就是 Agent 的输出样子。我之前已经在 Phoenix 里给你们展示过了各种它产生的结果。在这个案例中，我的编码 Agent 帮我审阅了所有的 trace，它同时完成了开放式编码与轴向编码，并且总结出了一个名为“框架泄露”（harness leakage）的类别。所谓框架泄露，就是它给这种现象起的名字：Agent 总是不停地向我们请求它本来就没有权限去执行的操作。

<details>
<summary>Original English</summary>

**Speaker**: So the agent is going to do a whole bunch of stuff. This is what the agent output looks like. I showed you already in Phoenix. I've already showed you the various things that it came up with. In this case, my coding agent looked through all of my traces for me. It came up with both open coding and axial coding, and it came up with a category called harness leakage. Harness leakage is what it decided to call that thing where it's constantly asking us to give it permission to do things that it doesn't have permission to do.

</details>

**讲师**: 这种情况发生的频次相当高。它还发现了许多其他问题，比如幻觉，比如推理错误——就像特斯拉那个例子，它在计算时把各种百分比胡乱相加。如果你自己运行了这套数据，你的编码 Agent 也生成了分析报告，你可能会得到不同的分析结果和一组不同的标签分类，因为我们每个人的 Agent 表现都不完全一样。现场有谁的编码 Agent 已经跑完分析了吗？还有人正在运行吗？

<details>
<summary>Original English</summary>

**Speaker**: So that's a ton of times for that specific thing to happen. It also found a bunch of other things. It found hallucination. It found reasoning errors like the Tesla one where it added up percentages. If you've run this data yourself and your coding agent has produced its own analysis, you're going to get a different analysis and a different set of labels, because all of our agents are different. Who has got their coding agent to complete an analysis yet? Anybody still running?

</details>

**学员**: 还在跑。

<details>
<summary>Original English</summary>

**Audience Member**: [Indicates still running]

</details>

**讲师**: 好的，那我们先继续往下讲。希望能赶快出结果，不过就算没有，直接用我的种子数据也完全没问题。一旦拿到数据，你就可以统计各个类别的发生频次。出现频率最高的失败案例往往是你最先去查看的地方，但频率最高的故障不一定是你最先要去修复的。你需要同时综合评估频率（frequency）和严重性（severity）。

<details>
<summary>Original English</summary>

**Speaker**: All right. Well, we'll keep going. Hopefully, you'll get some, but if not, you can just use my seed data. Once you've got data, you can count the categories. The most common failure is going to be where you look first, but the most common failure is not necessarily the first thing that you're going to fix. What you want to do is address frequency and severity.

</details>

**讲师**: 举个例子，如果有 40% 的概率它会出现事实幻觉，这确实是个大问题；但如果它有 1% 的概率会直接指导用户如何制造炸弹，哪怕它发生的概率只有 1%，你也必须立即修复它，因为这绝对不是一个财务分析助手该干的事。所以，你需要用频次乘以严重程度来决定你的修复优先级。

<details>
<summary>Original English</summary>

**Speaker**: So if, you know, 40% of the time it hallucinates, that's a problem. If 1% of the time it gives your user instructions on how to build a bomb, you fix that immediately even though it happens only 1% of the time because that's absolutely not what a financial analyst is supposed to be doing. So you multiply frequency by severity to get your priority.

</details>

### 第三步：代码评测（Code Evals）与 Phoenix 数据集成

**讲师**: 好，希望大家的环境很快能跟上进度，我接着往下推进。第三步是代码评测（Code evals）。代码评测属于最简单的评测方式，没有模型参与，不需要发起 API 调用，纯粹就是一段 TypeScript 代码。我能想到的最简单却最实用的评测就是：生成的报告究竟有没有提及我们要求分析的那只股票？

<details>
<summary>Original English</summary>

**Speaker**: All right, so hopefully your agents will catch up to where we are, but I'm going to keep going. Step three is code evals. Code evals are the simple ones. There's no model, there's no API call, there's just TypeScript. The simplest useful eval that I could think of was does the report actually mention the stock that we asked about.

</details>

**讲师**: 我们的 Agent 任务是分析某一家特定公司。如果它确实在做这件事，报告里就理应包含所分析公司的股票代码（ticker symbol）。如果我问的是特斯拉，它却长篇大论写了微软——而这在实测中至少真真切切发生过一次——那这份报告就彻底一文不值。股票代码要么存在于报告中，要么不存在，动用大语言模型去检查这个简直是大材小用。

<details>
<summary>Original English</summary>

**Speaker**: Our agent is supposed to analyze a specific company. If it's doing that, it should mention the ticker symbol of the company that it is analyzing. If I ask about Tesla and it writes about Microsoft, which is a thing that it really did on at least one occasion, that is a completely useless report. So either the ticker is in the report or it isn't. And using an LLM to check that would be complete overkill.

</details>

**讲师**: 要运行这一项检查，我们首先需要将数据从 Phoenix 中提取出来以便进行分析。提取逻辑是这样的：我们向 Phoenix 请求当前项目的 spans，传入 `parentID: null` 意味着只拉取没有父节点的 span，也就是最顶层的 span，正是我之前在 trace 视图里给大家展示的那些。代码仓库将这部分逻辑封装在一个名为 `getAgentRuns` 的辅助函数中，它会返回每次运行的 span ID、输入、输出，以及我们后续会用到的 research turns output。

<details>
<summary>Original English</summary>

**Speaker**: So to run that check, the first thing that we need to do is get our data out of Phoenix so that we can run the analysis. This is how that is done. We ask for spans for our project, and parent ID null means that only spans that have no parent. So those are the top-level spans, the ones that I was showing you in my traces. The repo runs this in a little helper called `getAgentRuns`, which hands back each run's span ID, its input, and its output, plus the research turns output, which we're going to need later.

</details>

### 实现 Ticker 检查与回写 Span 注解

**讲师**: 接下来就是股票代码检查（ticker check）。这里的 `createEvaluator` 来自 Phoenix 的 evals 依赖包。你只需传给它一个普通的函数，无需自己从头构建评测器包装。你只要告诉它这是一个代码评测（code eval），它就不会调用任何 LLM。该函数接收 input 和 output，解析拆分出我们查询的目标 ticker，逐一检查每个 ticker 是否都在最终报告中出现，最后返回一个标签（label）和一个分数（score）。如果有缺失，它还会明确指出具体缺少了哪个 ticker，因此失败原因一目了然。

<details>
<summary>Original English</summary>

**Speaker**: And then this is the ticker check. `createEvaluator` comes from the Phoenix evals package. You can just give it an ordinary function. You don't have to build an evaluator function yourself. All you have to do is tell it that this is a code eval so that no LLM is involved. The function gets the input and the output. It splits out the tickers we asked about. It checks that each one appears in the report. And it returns a label and a score. And if something's missing, it also says which ticker. So the failure explains itself.

</details>

**讲师**: 我之前提到过结构化输入的好处：发送给我们工具的输入是 JSON 格式，这在此时发挥了巨大的便利，让我们编写这个代码评测变得极其简单，因为结构已经是 JSON 了。我们清清楚楚地知道哪个字段是 ticker，哪个字段是它应该撰写的报告要求描述。如果你的输入能够规范化为结构化数据，你的评测编写起来会极其轻松；否则，你甚至还得专门再套一层 LLM 先去解析输入到底包含了什么，然后再传给评测函数。

<details>
<summary>Original English</summary>

**Speaker**: The structured inputs that I talked about earlier, how the input being sent to our tool was JSON, that is helping us out here because it's making it really easy to write this code eval because it's already JSON. So we already know which thing is the ticker and which thing is the description of the report that it should be writing. So if you can get your inputs to be structured data, that's going to make your evals really easy to work with. But if not, you're going to have to get another LLM involved to read your input, figure out what the input was, and then pass it to your eval.

</details>

**讲师**: 接下来我们执行评测，并将评估结果回写记录到 Phoenix。脚本会遍历每一个 agent run 执行评测器，然后调用 `logSpanAnnotations` 将每一条判定结果直接挂载到对应的 span 上。这就是我们今天运行每一个 eval 的通用范式：获取运行记录、执行评测、将结果回写记录到 Phoenix。对应的运行命令是 `npm run eval:code`，我来运行演示一下。

<details>
<summary>Original English</summary>

**Speaker**: Then we run it and we log the results back to Phoenix. So the script runs the evaluator on every agent run, and then it calls `logSpanAnnotations` which attaches each result to its span. That's going to be the same pattern for every single eval we run today: you get the runs, you evaluate them, and then you log the results back to Phoenix. So the command here is `npm run eval:code`. Let me see if I can get that to work.

</details>

**讲师**: 好了，运行成功，而且执行速度近乎秒级完成，因为这就是纯粹的代码评测（code evals）。它们根本不用停下来等待大模型做任何推理，刷地一下就跑完了。结果显示：15 个测试通过，2 个失败。失败的两个用例中，一个是特斯拉报告里完全漏掉了特斯拉，另一个是亚马逊报告里完全漏掉了亚马逊。你看，这是我们能想到的最基础、最简单的检查——“LLM 到底有没有针对我们要求的主题撰写报告？”仅仅这最简单的一招，就已经帮我们揪出了系统中的真实缺陷。

<details>
<summary>Original English</summary>

**Speaker**: All right, it worked and it ran almost instantly because it's code evals. They don't have to wait for an LLM to do anything. They just go, and it has reported 15 passes and two failures. One is Tesla is missing Tesla, and one is Amazon is missing Amazon. So this is the dumbest possible check that we could have made: Did the LLM actually write a report about the thing that we asked it about? And it has already found some errors. It has found cases where it wrote...

</details>

<!-- chunk 7/13 -->

### 代码评估与评估结果导向原则

**演讲者**：……关注错了重点。举个例子，据我所知，亚马逊（Amazon）的那个问题在于：评估提问的是 AWS 的盈利能力，结果 Agent 就一头扎进 AWS 里，写出了一份通篇只讲 AWS 及其业务进展的报告，却对大众熟知的亚马逊电商零售业务只字不提。因此，设计这种测试是非常有价值的，而且运行起来完全零成本。

所以说，基于代码的确定性评估（Code Evals）绝不是花架子小玩具。比如：输出是否能够成功解析为 JSON？长度是否控制在限制之内？是否规避了那些你绝不想看到的套话（例如“作为一名 AI 语言模型”）？而且它不仅限于简单的字符串检查。Code Eval 的核心定义在于评分机制是完全确定性的。也就是说，你的 Code Eval 可以通过直接查询数据库来核实系统状态是否正确；可以校验工具调用的实际执行是否符合预期；还可以直接调用外部 API，二次核对 Agent 所认定的股票价格是否与真实股价一致。只要对相同输入每次都能给出确定结果的逻辑，都可以封装成 Code Eval。因此，你的代码评估逻辑完全可以设计得非常高级。

不过，这里有一点你必须时刻保持警惕：评估应该针对最终结果，而不是纠结于实现路径。很多开发者容易在这里踩坑，试图去强行检查 Agent 是否按部就班地执行了某些特定步骤——比如它是不是必须先调用搜索工具，紧接着再调用另一个工具？Anthropic 对此给出的建议是，这种考核方式过于死板僵化。正如我们之前看到的，智能体具有创造性，它完全可能以出人意料的方式达成目标。你绝不能主观预设它必须分毫不差地按照你的思路来做。因此，不要去限制和考核它所走的具体路径，而是应当评估最终产出的结果是否合格。比如我们的股票代码检查（Ticker Check），它根本不在乎 Agent 究竟是如何找到数据的，它只关心最终报告里有没有包含正确的公司。对于许多评估场景来说，这就是恰到好处的颗粒度。后续我们还会专门讨论轨迹层面的评估（Trajectory-level Evals），在那类场景下我们确实需要评估执行路径，但那完全是另一码事了。

<details>
<summary>Original English</summary>

**Speaker**: ...about the wrong thing. I know for instance that the problem with Amazon is that it asked it about AWS profitability and the agent got focused on AWS and wrote a report that was only about AWS and what AWS was doing, and not about what Amazon, you know, the shopping company does. So this is a test worth doing and it cost you absolutely nothing to run.

So code evals aren't toys. Did the output parse as JSON? Is it under the length limit? Does it avoid phrases you never want to see like "as an AI language model"? And it doesn't have to be a string check. Code eval just means that the grading is deterministic. So your code eval can be querying your database to make sure that the state is correct. It can make sure that the tool calls did what the tool calls were supposed to do. It can call an API and double check that the stock price that the agent thinks is happening is really the stock price. Anything that gives the same answer for the same input every time can become a code eval. So your code evals can be quite advanced.

Um, but one thing you should be wary of is grading the outcome and not the path. There's a tempting mistake here to check that the agent took particular steps. Did it call the search tool first and then this other tool? Anthropic advises that this is too rigid an approach. Like we saw earlier, the agent can be creative. It can do things in an unexpected way. You don't want to assume that it's always going to do exactly what you would have done. So you don't want to grade the path that it took. You want to grade whether or not the outcome was good. Our ticker check doesn't care how the agent found its data, right? It just cares that the right company is in the report, and that is the right level for a lot of evals. We will talk later about trajectory level evals where we do actually want to grade the path, but that is a very different kettle of fish.

</details>

### 引入大模型裁判（LLM as a Judge）

**演讲者**：这就引出了第四步：将大语言模型作为裁判（LLM as a Judge）。我们先从 Phoenix 开箱即用的内置评估器开始。代码虽然能检查报告中是否包含了股票代码，但它无法替你判断分析内容到底写得好不好。比如：数据是否精准？报告是否完整详实？投资建议是否有理有据？这些都是关乎报告语义层面的问题，而非字面文本匹配能够解决的。面对这类诉求，你必须借助具备判断力的工具。

一个典型的大模型裁判主要由三部分构成：第一是裁判模型（Judge Model），即具体负责裁决打分的大模型；第二是评分准则（Rubric），即指导裁判如何界定优秀标准的提示词（Prompt）；第三是待评数据（Data），即接受评估的具体样本。Phoenix 将这三者解耦开来，方便你自由组合搭配：你可以用不同的模型测试同一套评分准则，也可以用同一个裁判模型套用不同的规则。

对各位来说，一个利好消息是 Phoenix 已经自带了一整套成熟的内置评估指标，因此你完全不必一开始就事事从零编写评估逻辑。例如，“正确性”（Correctness）用于校验回答是否准确；“忠实度”（Faithfulness）用于检验结论是否严格依据源材料得出（我们稍后会展示这两者的关键区别）；此外还有完整性（Completeness）、幻觉（Hallucination）、拒答（Refusal）、个人隐私信息防护（PII）以及有害内容过滤（Toxicity）等。绝大多数智能体日常需要核验的维度，它都已经内置支持了。对于 Agent 来说，还专门配备了针对工具使用的评估：它是否选对了工具？传入的参数是否无误？拿到工具返回的结果后，是否做出了合理的后续处理？这些评估逻辑并不神秘，本质上就是我们预先编写、历经实战检验并确保稳定好用的一系列 Prompt 模板。

<details>
<summary>Original English</summary>

**Speaker**: So that brings us to step four: the LLM as a judge. And we're going to start with Phoenix's built-in evals. Code can check whether the ticker is in the report, but it can't tell you if the analysis is any good. Are the numbers accurate? Is the report complete? Is the recommendation well reasoned? These are questions about the meaning of the report, not the textual content of the report. And for those, you need something that has judgment.

An LLM judge has three parts: it has a judge model, which is the LLM that is doing the judging; it has a rubric, which is the prompt that tells it what good looks like; and then it has the data, which is the examples that it's grading. Phoenix keeps those three separate so you can mix and match. You can try the same rules with different models. You can try the same judge with different rules.

The good news for you is that Phoenix ships a bunch of built-in evals. So you don't always have to write your own evals, at least not right off the bat. There's correctness, which checks if the answer is accurate. There's faithfulness, which checks if it sticks to the source material. We're going to see the difference between those two in a second. There's completeness, hallucination, refusal, PII, and toxicity. Lots of things that lots of agents need to check are built in. And for agents, there are evals for tool use: Did it pick the right tool? Did it pass the right arguments? Did it do something sensible with the result? These evals are not magical. They are just prompts that we've already written and battle-tested and made sure work for you.

</details>

### 配置裁判模型与规避同模型偏见

**演讲者**：接下来我们来看看裁判模型的具体配置。在 TypeScript 环境下，Phoenix 的评估模块是通过 Vercel AI SDK 与底层模型进行通信的。这意味着凡是 AI SDK 支持的模型，全都可以直接拿来充当裁判。在当前案例中，我使用的是 Claude Sonnet 3.5。前面提到过，我们的 Agent 自身运行在 Haiku 上，因为它廉价且速度快；而裁判则选用 Sonnet，原因在于裁判模型的能力通常必须高过被评估的 Agent 本身。所以，裁判请尽量选用 Sonnet 或者 Opus；或者更理想的做法是——直接选择完全来自不同厂商的模型。例如，如果你手头有 OpenAI 的 API Key，大可以让 OpenAI 的模型来评审 Claude 的工作产出。这是因为 Claude 存在所谓的“同模型偏见”（Same Model Bias）：相比于 OpenAI 或其他厂商模型的输出，Claude 往往天然更偏爱由其他版本 Claude 所生成的内容。

另外值得注意的是这里的最后一行配置：我们在裁判上抑制了追踪数据收集（Suppressing Tracing）。因为我们之前在全局开启了链路追踪，而裁判本身也是一个运行中的 Claude 实例。如果不做抑制，它默认就会把裁判本身的执行链路也记录下来——事实上在我之前的测试数据中，我就不小心忘记开启遥测抑制，导致追踪记录里充斥着裁判自身的调用轨迹，而这些冗余数据是你完全不需要的。因此，当前仓库里的每一个评估器都会配上这一遥测配置，从而确保裁判自身的运行痕迹不会混杂进智能体的追踪流程中。

<details>
<summary>Original English</summary>

**Speaker**: So let's find the judge model. Phoenix evals in TypeScript use the Vercel AI SDK to talk to models. So any model that the AI SDK supports can be a judge. In this case, I'm using Claude Sonnet 3.5. The agent runs on Haiku. Like I said, it's cheap and fast. Our judge is running on Sonnet because you want your judge to be more capable than the agent itself was. So give it Sonnet or give it Opus. Or give it, even better, give it a model from a different provider entirely. If you've got an OpenAI key, get OpenAI to judge the work of Claude. Because Claude has what is known as same model bias. So Claude tends to like the output of other versions of Claude more than it does the output of OpenAI or some other provider.

The last line here, in case you're wondering, is suppressing tracing on the judge, because we turned on tracing across the board. The judge is itself a copy of Claude. So by default—and in fact, in my test data, you will see that I forgot to turn on telemetry suppression. So my traces are full of the judge running itself and seeing all of the traces from the judge, which you don't need. So every evaluator in this repo gets this telemetry setting so that the judge stays out of our agent.

</details>

### 正确性评估的局限与时效性难题

**演讲者**：我们先从“正确性”（Correctness）评写入手，这通常是大家最容易想到的直观选择：这份报告到底正不正确？在代码层面，这只需要一个模块导入和一行初始化配置即可，无需复杂设置。你只需声明“我要运行正确性评估器，在我的数据上跑一遍看看效果”。接着调用 `evaluate` 方法，就会收到返回的判定标签（Label）、评分（Score）以及判定理由（Explanation）。测试脚本会遍历 Agent 的每一次运行，并将评测结果同步记录回 Phoenix 中，与我们之前做股票代码检查的流程一致。

我可以在这里直接运行一下。由于涉及到实际调用大模型进行推理，可能需要稍微耗费一点时间。无论运行成功与否都没关系，因为系统里已经提前保存好了现成的数据。在界面中的标注（Annotations）这一列里，你可以清晰看到之前多次评估运行的结果。当前屏幕上展示的是“可行性”（Actionability）这一项，但你同时也能看到正确性（Correctness）、忠实度（Faithfulness）、人工可行性（Human Actionable）以及提及股票代码（Mention Ticker）等指标。后续我们会逐一深入拆解。

首先映入眼帘的是正确性指标：所有这些条目的正确性得分全都是 0。整整 16 份报告全被判定为“不正确”。导致全部判错的根源在于：Claude 是基于它自身的预训练先验知识来核验正确性的，这也是它唯一掌握的参照物。而当前 Claude 的知识截止日期大约停留在 1 月份左右，可我的 Agent 探讨的却是 10 月份的最新股价。这导致 Claude 裁判瞬间陷入困惑并断定：“你说的全是未来的事情，这绝对是模型幻觉，这份报告绝不可能是正确的。”正因如此，我们开箱即用的正确性检查直接将所有报告全部判了死刑。

这显然无法为业务迭代提供有效参考。其实从本质上看，这项评估可以说是“对错参半”：在我记录的数据里，16 条判定解释中有 7 条都在抱怨裁判自身无法核实最新鲜的实时数据，这完全属于评估设计不当造成的误判；但与此同时，它确实也敏锐地揪出了一些真实问题，比如某些报告里的数字对不上，或者存在相互矛盾的日期信息。无论如何，全盘为 0 的得分在此刻失去了一切度量意义，它只是在全局层面上提醒我们：选用“正确性”这一评估维度，从一开始可能就挑错了切入点。我们需要抛给裁判一个它真正有能力回答的问题。

<details>
<summary>Original English</summary>

**Speaker**: Let's start with correctness, which is the obvious first choice. Is this report correct? That is one import and one line of setup. You don't have to do anything. You just say, "Hey, I'm running the correctness evaluator. Run it on my stuff and let's see how it goes." Then you call evaluate and you get back a label, a score, and an explanation. And the script runs it on every agent run and logs the results back to Phoenix, the same way we did the ticker check.

I should be able to run that as well. That's going to take a little while because it has to actually do some LLM stuff. If it works, it works. If it doesn't, I have stuff already built in. So you can see in my annotations column, you can see the results of various evaluations I've already run. In this case, it's showing you the actionability one, but you can see correctness, faithfulness, human actionable, and mention ticker. We're going to talk about what all of those are.

But first you're going to see correctness. Correctness on all of these is zero. All 16 reports have been judged as incorrect. And the reason that they've been judged as incorrect is because Claude judges correctness by what it knows. That's the only thing that it has available to it. And Claude's knowledge cutoff at the moment is in something like January. So my agent is talking about stock prices in October and Claude is freaking out and going, "You're talking about stuff that's in the future. That's obviously a hallucination. This report cannot possibly be correct." So our built-in check for correctness fails every single report for that reason, which is not terribly useful.

So the eval is half wrong and half right. In my data, seven of the 16 explanations complain that the judge can't verify fresh data, which is the eval definitely being wrong. But lots of them also point out something real: things like the numbers don't add up or dates that contradict each other. So a score of zero is telling us nothing here. It's telling us across the board that this eval is probably not the right choice of eval. What we want is a question that the judge can actually answer.

</details>

### 转向忠实度评估与上下文补全

**演讲者**：好的，刚才已经跟你们交代过这个背景了。那么，我们接下来要改用“忠实度”（Faithfulness）来评估。忠实度提出的是一个合理得多的好问题：它是在问“根据你当时所获取的参考资料，你的报告分析是否讲得通？给出的结论是否扎根于我们提供的数据？”这种评估机制表现要好得多，因为它使用的是与 Agent 拿到的完全一致的同一套上下文数据，以此来核验基于该数据推导出的报告是否合情合理。这才是裁判真正有能力客观回答的问题。

而且，这些必要的上下文信息其实早已完整沉淀在链路追踪（Trace）中了。正如我们此前观察到的，每一次网络搜索都会生成自己独立的 Span 记录；智能体在每一轮研究中的输出，本质上都是它记录下自己发现了什么的研究笔记。在最初的第一版评估里，我仅仅把 Agent 整理的研究笔记喂给了裁判。随后当我审查裁判给出的解释时，发现裁判模型不断把报告中的数字标记为“凭空捏造”——原因正在于我最初的评估版本并没有告诉它“这些数据是智能体通过实际网络搜索查询回来的真实内容”。因此，在大家现在看到的升级版中，我们向裁判提供了完整的上下文背景。我们的 `get_agent_runs` 辅助工具将会把原始的搜索数据……

<details>
<summary>Original English</summary>

**Speaker**: So what we're going to use instead is faithfulness. Faithfulness is asking a much better question. It's saying: given the data that you had, did your report make sense? Is the answer based in the data that we were given? This works much better because it can work with exactly the same data that the agent was given and see if it gets a report that makes sense. So that's a question the judge can actually answer.

And the context is already in the trace. Every web search is its own span, like we saw. Every research turn's output is the agent's own notes on what it found. So my first version, my first eval, only gave the judge the research notes. And then I read the explanations, and the judge was flagging numbers as made up because my version of the eval hadn't told it that, "Oh, I searched the web and actually found this data." So in the version you see, we've given it the full context. Our `get_agent_runs` helper is going to pull both the raw search...

</details>

<!-- chunk 8/13 -->

### 评估忠实度：输入、输出与上下文

**讲师**：...搜索结果和笔记，这样它就能看到研究智能体找到了什么，以及它是如何找到那些数据的。正如我所说，忠实度评估需要三样东西：输入，也就是用户的提问；输出，也就是生成的报告；以及上下文，也就是我刚才提到的搜索结果和笔记。

<details>
<summary>Original English</summary>

**Speaker**: ...results and the notes so that it can see what the research agent found and how it found that data. So like I said, faithfulness takes three things. It takes the input, which is what the user asked; it takes the output, which is the report; and it takes the context, which is the search results and the notes that I was just talking about.

</details>

**讲师**：运行它的模式和之前完全一样：创建评估器，对每一次运行进行评估，然后记录结果。正如我所说，它比正确性评估要慢一些，因为裁判模型需要阅读每一次搜索的内容。到目前为止，有谁跑出评估结果了吗？看来你那里的 Wi-Fi 又比其他所有人都快。还有其他人跑完吗？太棒了。

<details>
<summary>Original English</summary>

**Speaker**: And you run it using the same pattern as before. You create the evaluator, you evaluate every run, you log the results. Like I said, it's slower than correctness because the judge is reading every search. Who has got any results out of their eval so far? Again, you've got a faster Wi-Fi connection than everybody else. Anybody else? Cool.

</details>

### 分析 Phoenix 中的忠实度诊断解释

**讲师**：那么，让我们在 Phoenix 中看一下我的忠实度评估报告。在忠实度指标上，我得到了很多零分，但并非全都是零分。让我们来读一下针对微软（Microsoft）的那份解释，那是我读到的最有趣的一篇。正如大家所见，在每一项旁边，你都会得到具体的解释说明。

<details>
<summary>Original English</summary>

**Speaker**: So let's look in Phoenix at my faithfulness reports. I got a lot of zeros on faithfulness, but not all of them. Let's read the Microsoft explanation. That was the one that I read that was most interesting. As you can see, next to each one, you get the explanation.

</details>

**讲师**：在这项评估中，裁判指出了生成回答添加了若干缺乏上下文支持的主张：比如声称“Azure 是第二大云服务商”、“积压订单提供了三年的能见度”，并且还给出了“隐含的 2027 财年目标”。它直接告诉了我它不满意的地方在哪里，清晰地说明了为什么它认为这个回答是不忠实的。它指出某些 2027 年的目标纯属虚构，因为这些内容根本没有出现在任何搜索结果中。

<details>
<summary>Original English</summary>

**Speaker**: So in this one, the response adds several claims that the context does not support. "Azure is the number two cloud provider." "The backlog gives three years of visibility," and there are implied FY27 targets. It is telling me what it doesn't like about this thing. It's telling me why it thinks this thing is unfaithful. It's complaining that some of the 2027 targets are fabricated because they're not in any search results.

</details>

**讲师**：关于英伟达（Nvidia）的那条记录也很有意思，如果我能找到的话。看这里，在这一条中，裁判指出模型回答混淆了两个不同的数据点。这是智能体犯下的一个推理错误，而裁判准确地把它揪了出来。裁判说明了上下文信息中的这部分内容是伪造的。这些是非常实用的评估结果。虽然在这里 16 份报告中有 14 份被标记为不忠实，但这些解释要有用得多。它真正在做我们希望它完成的事情。

<details>
<summary>Original English</summary>

**Speaker**: The Nvidia one is also interesting if I can find that one. Right. In this one, it says the response conflates two different data points. This is a reasoning error that the judge has accurately found. It says the context information—this is fabricated. These are much more useful results. We've got 14 out of 16 reports marked as unfaithful here, but the explanations are way more useful. And it's actually doing the thing that we wanted it to do.

</details>

### 针对智能体的工具调用评估

**讲师**：对于智能体系统，你还可以对工具调用进行打分评估。之前我们在每个追踪记录（trace）内部都看到了网络搜索的 span。Phoenix 内置了针对所有这些行为的现成评估工具。

<details>
<summary>Original English</summary>

**Speaker**: So for agents, you can also grade the tool calls. So we saw the web search spans inside each trace. Phoenix has built-in evals for all of those as well.

</details>

**讲师**：其中，“工具选择”（Tool Selection）评估旨在考察：智能体是否挑选了正确的工具，或者是否在完全没有必要时执行了搜索。“工具调用”（Tool Invocation）评估则考察：它是否向这些工具传递了合理的参数，例如搜索查询词是否真正围绕着目标公司展开。而“工具响应处理”（Tool Response Handling）则评估：它在获得调用结果之后，是否做出了合理的后续处理。

<details>
<summary>Original English</summary>

**Speaker**: Tool selection asks: did the agent pick the right tool, or search when it didn't need to? Tool invocation asks: did it pass sensible arguments to those tools, like a search query that's actually about the company? And tool response handling asks: did it do something sensible with the result of that call?

</details>

**讲师**：这些决策往往决定了一个智能体的成败。而且所有这些环节，都发生在最终报告被实际阅读之前。我们已经知道自己的智能体有时会做出奇怪的工具选择，比如它会试图把报告保存到本地文件中。因此，我们可以观察内置的评估器是否能够捕获这种行为。我这里就不亲自运行这个评估了，不过大家可以自己跑一下。

<details>
<summary>Original English</summary>

**Speaker**: These are the decisions that can make or break an agent. And they all happen before the report actually gets read. And we already know our agent makes strange tool choices sometimes, like it tries to save the report to a file. So we can see if our built-in eval catches that. I'm not going to run this one, but you can run that one.

</details>

**讲师**：工具选择评估需要输入三个要素：智能体接收到的要求、它本可以使用哪些工具，以及它实际选择了哪些工具。评估脚本会遍历智能体的每一次轮次，分别查看研究与写作两个阶段的每一条追踪记录，并收集各自下属的工具 span。追踪记录本身记录了智能体调用了哪些工具，但并不会记录它当时“可以”调用哪些工具。因此，我们必须在 `tool_selection.ts` 文件中自己写出那个可用工具列表。

<details>
<summary>Original English</summary>

**Speaker**: Tool selection takes three things: what the agent was asked, which tools it could have used, and which ones it picked. And the script goes through every agent turn and every trace—research and writing separately—and collects the tool spans underneath each one. The trace records which tools the agent called, but not which ones it could have called. So we have to write that list ourselves in tool_selection.ts.

</details>

**讲师**：接下来就是与其他运行相同的操作模式了：执行 `npm run eval tools`，然后就完成了。这一项评测大概只需要 15 秒左右。

<details>
<summary>Original English</summary>

**Speaker**: Then it is the same pattern as every other run: npm run eval tools, and then you're done. That one should take about 15 seconds.

</details>

### 工具选择评估中的歧义与误判

**讲师**：现在让我们在 Phoenix 中查看工具选择评估的结果。在这里，系统判定我的某些工具选择是不正确的。比如这一条：用户要求基于先前的研究撰写一份简明扼要的报告；智能体使用 `write` 工具将报告写入文件看似合理恰当，因为 `write` 工具确实存在且安全无害；然而，大语言模型随后又进行了第二次多余的 bash 调用。确实如此，它确实调用了两次。

<details>
<summary>Original English</summary>

**Speaker**: So, let's look in Phoenix at tool selection. Tool selection. It's helping me out. All right. So, these are ones where it has decided that my tool selection was incorrect for whatever reason. The user asked for a concise report based on prior research. Writing it to a file with write is plausible and appropriate since write exists and is safe. However, the LLM made a second redundant bash call. Awesome. Yeah, it sure did.

</details>

**讲师**：裁判模型判罚了全部 6 个尝试调用两次工具的案例，使其未通过评估；而通过了 7 个案例，其中有 6 个是仅尝试调用一次的。总体来看，在我的 16 次写作轮次中，有 13 次都尝试了保存文件。而这些评语中只有一条指出：用户根本没有要求将内容保存到文件中。那么，这位裁判判定得不对吗？裁判判定该工具调用正确，真的准确吗？

<details>
<summary>Original English</summary>

**Speaker**: The judge failed six that tried twice. It passed seven—six of the seven that tried once. Overall 13 of my 16 writing turns tried to save a file. And only one of these explanations said that the user never asked for a file to be saved. So is this judge incorrect? Is the judge accurately judging that the tool call was correct?

</details>

**讲师**：我们在写作提示词中写的是：“根据你上面的研究，写一份简明的财务报告。”坦白讲，我们的提示词在这里本身就存在歧义。我们说了“写”，但没有说明要“写到哪里”；我们没有说明这篇报告是“为了什么目的”而写；我们也没有说明“目标读者究竟是谁”。

<details>
<summary>Original English</summary>

**Speaker**: Our writing prompt said, "Write a concise financial report based on your research above." Our prompt is genuinely ambiguous here. We said, "Write," we didn't say where to write it to. We didn't say what to write it for. We didn't say who the audience was going to be.

</details>

**讲师**：因此，工具选择评估器注意到了这一点，它查看了输入并认为：“好吧，智能体在此处尝试将内容写入磁盘似乎是合情合理的举动。”这就再次说明：你吩咐智能体去做的事情，与你吩咐评估器去检验的事情之间，存在着相互影响。你不能盲目相信工具调用评估的结果一定绝对正确，因为在这个案例中，工具调用评估实际上站在了智能体这一边。它给出的判断基本相当于：“没有错，智能体是合理的，它接收到了指令并在尽力完成。”

<details>
<summary>Original English</summary>

**Speaker**: So, the tool selection knows that and is looking at the input and is going, "Well, it seems a reasonable thing for the agent to try and write to disk here." So again, what you're telling the agent to do and what you're telling the eval to do interact with each other. You can't necessarily trust that the tool call invocation is going to be right because in this case the tool call eval is siding with the agent. It's like, no, the agent is right. The agent received instructions and did its best is basically the eval's position.

</details>

### 从追踪指标到核心洞察：选对评估器胜过盲目调优

**讲师**：评估结果同样保存在追踪记录之中。如果你在 Phoenix 中查看 traces，就能看到各项指标关联到了哪一条 trace，以及挂载到了该 trace 内的具体哪个 span 上。可以看到，“可操作性”（actionability）和“正确性”（correctness）被挂载到了根节点（root）；而“工具选择”则精确挂载到了发起该工具调用的特定轮次上。

<details>
<summary>Original English</summary>

**Speaker**: Eval results live in the trace as well. So if you're looking at the traces in Phoenix, you can see them here attached to which trace they got, which span in the trace they got attached to. So you see actionability and correctness got attached to the root, whereas tool selection is getting attached to the specific turn that made that tool call.

</details>

**讲师**：你可以根据任何评估维度对追踪记录进行过滤筛选，也可以按评分排序来找出表现最差的几次运行。你可以直接从一个不合格的分数一键跳转到导致该失败的具体执行步骤——从分数到根因，只需一次点击。所有这些功能都属于内置评估体系。

<details>
<summary>Original English</summary>

**Speaker**: You can filter your traces by any eval. You can sort by score to find your worst runs. You can click straight from a failing score into the step that caused it—from score to cause in one click. So all of that is the built-in eval.

</details>

**讲师**：我们在这里学到的教训是：选对评估维度，远胜过不断调优评估器本身。选择“正确性”作为评估完全是选错了方向，它没有为我们提供任何实质信息，只是笼统地告诉我们有一堆地方出错了；而“工具选择”确实揭示了一些问题，“忠实度”则为我们提供了相当丰富且深刻的洞察。因此，选用切中要害的评估项胜过盲目调参；清楚自己究竟在问什么问题，才是做对评估的核心关键。

<details>
<summary>Original English</summary>

**Speaker**: And the lesson here is that choosing the right eval beats tuning it. Choosing correctness was entirely the wrong eval. It didn't tell us anything. It just told us a bunch of stuff was wrong. Tool selection did tell us something, and faithfulness told us quite a lot. So checking the right eval beats tuning it, and knowing which question you're actually asking is really the core of getting this right.

</details>

### 步骤五：编写自定义评判标准

**讲师**：这就引出了我们的步骤五：编写属于你自己的裁判模型。在这个环节，评估逻辑将真正与你特定的业务应用紧密结合起来。

<details>
<summary>Original English</summary>

**Speaker**: Which brings us to step five, which is writing your own judge. This is where the eval gets specific to your application.

</details>

**讲师**：当人们思考评估（evals）时，大多数人脑海里浮现的往往就是这个环节。但我希望能确保大家先把基础知识打牢，而不是一开始就盲目跳进编写自定义评分规则（rubric）的深水区。你可以先编写代码级别的规则评估（code evals）来过滤掉一大批常规问题，也可以直接使用内置评估器来处理大量直观显见的检查，而无需自己从头去发明一套工具调用正确性评估器。

<details>
<summary>Original English</summary>

**Speaker**: And again, when people are thinking about evals, this is what most people are thinking about, but I wanted to make sure that you got the basics in first. You don't have to jump straight to writing a custom rubric. You can write code evals to get a bunch of stuff out of the way. You can use built-in eval to do a bunch of obvious stuff without having to invent your own tool calling correctness evaluator.

</details>

**讲师**：就我的场景而言，我希望自己的报告能够给出明确的“买入”、“卖出”或“持有”建议。没有任何现成的内置评估器能检查这一点，因为这显然是一个极其特定且定制化的业务需求。所以，我们需要自己动手来编写。

<details>
<summary>Original English</summary>

**Speaker**: What I wanted my report to do was give me a buy, sell, or hold recommendation. There is no built-in eval that checks for that because that would be a very specific thing indeed. So, we're going to write our own.

</details>

**讲师**：就我所见过的所有效果良好的评估提示词（eval prompt）而言，它们都包含五个关键组成部分，我们接下来逐一展开讲解。第一部分：赋予裁判角色设定与上下文背景。你经常会看到类似“你是一个某某领域的专家……”这样的措辞。这种提示词确实有效，这也是为什么每个人都在提示词里加上它的原因。明确告知智能体它的身份角色确实能起到一定的积极作用。在对比测试中，告诉模型它是一个“专家”，相比于只说它正在运行某种任务，确实能带来可观察到的表现差异。

<details>
<summary>Original English</summary>

**Speaker**: Every eval prompt I've seen that works well has five different parts and we're going to go through them one at a time. The first part is you give the judge a role and context. A thing you'll see all the time is "You are an expert blah blah blah blah blah." That does actually work. That's why everybody puts it in there. Like it helps a little bit to tell the agent what it is. Telling it it's an expert as opposed to just telling it that it is running up something else also seems to make a difference when they do side-by-side comparisons.

</details>

**讲师**：这是大语言模型诸多奇特特质之一：你需要夸赞它非常聪明，它就会变得自信并更努力地去完成任务。但真正至关重要的部分在于上下文背景。这是一份财务报告，我们期望得到一份能够深入剖析财务数据并阐明客观实情的报告；更具体地说，我们核心关注的是读者能否依据这份报告采取实际行动。

<details>
<summary>Original English</summary>

**Speaker**: It's just one of the weird things about LLMs. You need to tell it it's really smart and it gets confident and tries. But what really matters is the context. This is a financial report. We are expecting a report that analyzes financial data and tells us real things. And specifically what we care about is whether or not you could act on it.

</details>

**讲师**：因此，这为我们在评分规则中引入显式、具体的评判标准提供了依据。许多人在这个环节投入的精力往往远远不够。切记不要只泛泛地写“一个好的回答应当既有帮助又准确”，因为裁判模型根本无法理解在当前具体语境下何谓“有帮助”，何谓“准确”。面对这种模糊的标准，裁判模型根本无法做出非黑即白的明确判定。你必须清晰准确地写明：究竟具备哪些要素，才算是一份具有可操作性的报告。例如：给出明确具体的投资建议；列举切实的风险因素；以及它...

<details>
<summary>Original English</summary>

**Speaker**: So that gives us the explicit criteria that we include in our rubric. So this is where a lot of people don't put in enough effort. So don't write "a good response is helpful and accurate" because a judge doesn't know what helpful and it doesn't know what accurate means in this context. A judge can't make a yes or no decision from that. Write down exactly what makes a report actionable. So it makes a specific recommendation. It names concrete risks and it...

</details>

<!-- chunk 9/13 -->

### 构建评估标准（Rubric）的核心原则

**讲师**：它应该具备前瞻性，而不是仅仅停留在回顾过去。这些都是裁判模型可以切实验证的具体要求。需要说明的是，我们并不是凭空盲目构想这些维度的，你的评估标准必须直接来源于前期的错误分析。例如，“仅总结数据而没有任何解读”这个问题，正是我们在实际通读 trace 日志时发现的普遍缺陷。之所以把它列入评估规则，是因为它代表了我们正试图极力避免的具体问题。这就是在编写规则前先深入审视真实数据的意义所在。只有基于先验观察制定的具体标准，才能带来一致且可靠的判定结果。

<details>
<summary>Original English</summary>

**Instructor**: ...looks forward, not just back. Those are things that a judge can look at and actually check. And note that we're not just making up these things blind. Your criteria come from your error analysis. "Only summarizes data with no interpretation" is a problem that we saw when we were reading our traces. We are putting that in there because it's a problem that we are trying to avoid. That is the whole point of reading the data first. Specific criteria give you consistent judgments, and you get specific criteria by knowing in advance what the data is going to look like because you read it yourself.

</details>

**讲师**：优秀评估标准的第三个要素，是用清晰的边界标记数据。建议把每块数据都包裹在专属的 XML 标签中。Claude 在预训练阶段接触过海量的 XML 格式数据，非常擅长处理这种结构化语法。如果你去翻看我们自己代码中的评估标准实现，就会发现正是这么做的——我们的提示词都会把所有内容放进 XML 标签里。其中的双花括号是模板变量，Phoenix 会在运行时用每个 trace span 的实际输入与输出自动填充进去。之所以必须这样做，是因为我们需要在输入内容、输出内容以及人类提示词指令之间划定不可混淆的清晰界限。这不仅能有效防范提示词注入攻击，更能避免模型产生概念混淆；尤其是在你提供示例的时候，如果不用标签明确标示那是“示例”，模型就极易将其与正在评估的“真实数据”搞混。

<details>
<summary>Original English</summary>

**Instructor**: Part three of a good rubric is to mark the data clearly. Wrap each piece of data in its own XML tag. Claude was trained on billions and billions of XML tags, and it's really good at working with them. If you look into the code at our own rubrics, that's what we're doing. Our own prompts wrap everything in XML tags. And the double curly braces are template variables that Phoenix fills in with each span's input and outputs. The reason you do this is because you want clear boundaries between what is the input, what is the output, and what is your instructions. This helps against prompt injection, but it also helps the agent just getting confused. In particular, if you include examples, which we're going to see, mark the example as an example and not the data, otherwise it will get very confused about that.

</details>

### 是否在评估 Prompt 中提供少样本示例（Few-Shot Examples）

**讲师**：我个人非常推崇在评估准则中包含带标注的示例，但在整个评估（eval）领域，这实际上是一个存在广泛争议的做法。抽象的标准能够告诉裁判模型你的宏观意图，但具体示例能直观展示你的确切要求。作为人类，当有人给出具体示范时，我通常比只看一份抽象操作手册更容易把事情做对；很多大语言模型显然也有类似的倾向。不过，在接下来的实际测试中，我们强烈建议你对比测试两版评估标准：带示例的版本与不带示例的版本，看看哪一个表现更好。因为示例有时确实能显著提升模型的理解上限，但有时也会导致严重的过拟合——模型会死板地比对示例，一旦输出格式或表述与示例不完全一致便判为不合格，或者强行要求所有输出都必须长得和你的示例一模一样，反而降低了实用性。

<details>
<summary>Original English</summary>

**Instructor**: I love to include labeled examples, but it is in fact a controversial practice in the eval world. Criteria tell the judge what you mean in the abstract, but examples show it exactly what you mean. As a human, I find it much easier to do something when somebody has shown me an example of how it's supposed to work than if they've just given me a list of instructions of how to work. And a lot of LLMs feel that way as well, apparently. So when you test your rubric, which we're going to do in the next step, test it with examples and without examples and see which one does better. Because sometimes examples are going to help it do a better job, and sometimes an example will make it overfit. It will look at your examples and say, "Well, it doesn't look exactly like my example," or it will try and make every output look like your output example, which is less helpful.

</details>

**讲师**：我自己在现有的评估体系上做过严格的对照实验。在这个评估标准的测试中，出现了一个极富极客趣味的现象，这也是我专门把它拿出来分享的原因。在包含示例的配置下，裁判模型在三轮独立运行中，对我标注的 16 条真实样本均达成了 15/16、15/16、15/16 的判定一致率；而当我把示例全部剔除后，它居然有两轮达到了全部 16 条完全吻合（16/16），仅有一轮是 15/16。这让我非常好奇：为什么去掉示例后的一致性表现反而更高了？深入分析那个唯一的分歧样本后我发现，问题出在一份关于微软（Microsoft）的研报上，那份报告中没有列出风险项列表。

<details>
<summary>Original English</summary>

**Instructor**: I ran exactly that test on mine. So in the rubric that I used, this was fascinating in a really nerdy way, which is why I included it. I threw out my examples, and with the examples, the judge agreed with me 15, 15, and 15 times out of 16 in three different runs. And if I threw out the examples, it agreed with me 16 times twice—all 16 examples—and 15 times once. And so I was very curious as to how throwing out the examples made it better. And the specific problem that it was having is that in one of the reports it did not include a list of risks.

</details>

**讲师**：作为人工评测者，我当时读到那份微软报告，结论明确给出了“买入”建议，虽然全文没有列出任何风险提示，但我主观觉得它仍然具有很强的实操指导意义，包含了明确的买入行动建议，因此我人工将其标记为“具备可操作性”（actionable）。然而，我在提示词中提供的少样本示例明确强调了“必须包含风险分析”。因此，带有示例的 LLM 裁判在比对准则与示例后认定：既然没有列出风险，那就不符合示例规范，判定为“不可操作”。这实际上引发了一个开放式的深层讨论：究竟是我的人工标注更合理，还是模型的裁决更准确？模型在极其严苛地执行标准，而我在人工打标黄金数据集时反而有些失之于宽松和主观。

<details>
<summary>Original English</summary>

**Instructor**: So as a human, I read the report and it was like "Microsoft is a buy," and it didn't include any risks, and I was like, that's fine. It's still actionable. It included a buy. So I marked it as an actionable report. But my examples said you must include risks. And so the LLM judge was looking at the rules and looking at the examples and saying there must be risks in here, so this is not actionable because there's no risks. So that's genuinely an open question as to whether or not my human judgment was better or worse than the judge's. The judge was being very strict and I was being loosey-goosey when I as a human gave myself golden data.

</details>

### 现场互动：解释性输出与判定边界

**学员**：不好意思，我可以打断问一个问题吗？

<details>
<summary>Original English</summary>

**Audience Member**: Sorry, can I ask a question?

</details>

**讲师**：当然可以，请讲。

<details>
<summary>Original English</summary>

**Instructor**: Sure.

</details>

**学员**：那么你的假设是，在不提供示例的情况下，裁判模型之所有和你的人工判断达成了一致，是因为它也把那份微软报告判定成了具备可操作性？

<details>
<summary>Original English</summary>

**Audience Member**: So what's your hypothesis then as to without the examples it agreed with you, so it saw that Microsoft as being actionable?

</details>

**讲师**：是的，确实如此。

<details>
<summary>Original English</summary>

**Instructor**: Yeah.

</details>

**学员**：所以你的推断是，仅仅因为你没有把“风险”作为硬性必选项写进纯文本规则里，模型就认为那是一份合格的可操作研报？

<details>
<summary>Original English</summary>

**Audience Member**: Is that your hypothesis then that like simply because you didn't say risk was a necessary element, it felt that that was a good actionable?

</details>

**讲师**：这其实不仅仅是一个假设，因为现在的 LLM 裁判在输出判决时会附带完整的推理链条和解释说明。在不带示例时，它直接在理由中写明了为什么认为那份报告是具备操作性的。

<details>
<summary>Original English</summary>

**Instructor**: I mean, it's not a hypothesis, like the LLM judge comes with an explanation. So, it says...

</details>

**学员**：所以它在解释里确实明确指出那是具备可操作性的，对吧？

<details>
<summary>Original English</summary>

**Audience Member**: So, it said that that was actionable, right?

</details>

**讲师**：没错。所以就像我刚才提到的，在这个案例中，很难断言是我的人工主观裁量更正确，还是模型的严苛把关更合理。裁判模型选择严格执行显式的规则与示例要求，而我自己在标记黄金基准数据时，尺度确实放得更宽松了。

<details>
<summary>Original English</summary>

**Instructor**: Yeah. So, like I said, in this case, it's genuinely unclear whether or not I was doing the right thing or the judge was doing the right thing. The judge decided to interpret the rubric very strictly, and I, when I was marking these things as human actionable or not, was not being as strict.

</details>

### 正负样本对比与输出约束（Tool Calling）

**讲师**：我们来看一个典型的“可操作”报告正例：它给出了具体的量化指标、营收增长率、相对于行业板块的估值对比，明确指出了具体风险点，并在文末给出了投资者切实可以遵照执行的决策建议，甚至涵盖了何时应该改变投资立场的明确条件。反之，再看一个“不可操作”的反例：它的内容本身并没有事实性错误，讲的每一句话都是客观属实的，但它完全没有任何决策参考价值。比如“投资者应当综合权衡多重因素”，这种套话根本不能算作明确建议。当裁判模型同时见识过正反两类范例后，理论上它在遇到介于两者之间的模糊地带时，判定结果会更加稳定一致；而这种一致性究竟有没有真正建立起来，必须完全依赖系统性的测试集来验证。

<details>
<summary>Original English</summary>

**Instructor**: Here's an example of an actionable one: it has specific numbers, it has revenue growth, it has valuation compared to its sector, it names a concrete risk, and it ends with a recommendation you could actually follow, including when you'd change your mind. And this is what a not actionable one looks like: it isn't wrong; everything in it is true. It's just not very... useless. "Investors should consider various factors" is not a recommendation. Now that the judge has seen both, the hope is that it's more consistent on reports that fall somewhere in between. And whether it actually is, you find out by testing.

</details>

**讲师**：构建评估标准的第五个核心要素是收敛并严格约束输出范围。我们需要明确要求裁判仅输出“可操作”（actionable）或“不可操作”（not actionable）。在早期，我们通常需要在 Prompt 中硬性规定：“请输出一个字符串，且该字符串必须严格为 actionable 或 not actionable 之一”。现在完全不必采用这种脆弱的文本解析方式了。现代评估框架直接通过模型工具调用（Tool Calling / Structured Outputs）来约束结果。裁判能够选择的有效枚举值在工具调用的 JSON Schema 中被强行限定，而不是写在自然语言 Prompt 规则里，这极大增强了评测系统的结构化解析稳定性。

<details>
<summary>Original English</summary>

**Instructor**: Part five of putting together a rubric is you constrain the answer. You ask it for things that are actionable or not actionable. A thing you used to have to do is you used to have to say output a string and the string must be the word actionable or not actionable. You don't have to do that anymore. What modern evaluators use tool calls to put their output. So the choices available for that tool call are defined in the tool call and not in your rubric, which makes them a lot more reliable.

</details>

### 动手实操：编写评估标准并在 Phoenix 中分析

**讲师**：现在轮到大家亲自动手编写评估标准了。请打开代码文件 `evalactionability.ts`。里面已经包含了包含上述完整五个维度的现成模板，大家可以在此基础上自由定制：调整具体判定准则，或者修改示例。试想一下，什么样的研报内容能真正促使你采取投资动作？你在上一环节阅读自己生成的 trace 时注意到了哪些典型问题？把这些思考凝练成具体的判断准则，融入你自己的评估规则中。代码运行起来大约需要三到四分钟。现场有谁已经完全跟上进度了？请举手示意一下……太棒了，看到好几位都跟上了！正如我前面提过的，上次办这个工作坊时，大家被那个 200MB 的庞大仓库搞得焦头烂额，这次看到大家在当前阶段进展顺利，我由衷感到欣慰。

<details>
<summary>Original English</summary>

**Instructor**: So now it is your turn to write the rubric. Open `evalactionability.ts`. It has my rubric in it with all five parts, and you can make it yours. You can change the criteria, you can change the examples. What would make you act on one of these reports? What did you see in your own traces? Write that down and that should become your rubric. It will take three or four minutes to run. Who has managed to stay up with me so far? Like, who is at this point? Excellent. I have multiple hands. Like I said, the last time I did this workshop, everyone was completely lost because of the 200 megabyte repo. So the fact that anyone's got it this is just great for me.

</details>

**讲师**：这部分是底层的配置对接逻辑：我们实例化一个分类评估器（Classification Evaluator）来负责所有通信与管道串联。你需要为它命名、指定承载评测的基础大模型，并传入我们刚刚配置好的 Prompt 模板。如前所述，在主流程之外，我们为它绑定了受限的可选输出空间——明确划分为两种类别：得分记为 1 的“actionable”（具备可操作性），以及得分记为 0 的“not actionable”（不可操作）。

<details>
<summary>Original English</summary>

**Instructor**: This is how you wire it up. You create a classification evaluator which does all the plumbing. You give it a name, you give it the model, you give it your template. And like I said, out of band, you give it its options. So you give it its choices, which are actionable with a score of one and not actionable with a score of zero.

</details>

**讲师**：现在让我们回到 Phoenix 控制台里来查看这一轮可操作性评估的具体运行结果。（忍不住吸了口气）这里空调实在太冷了，冻得我手指都有点发木，打字都不利索了。好，我们来看第一份样本：这份报告分析了摩根大通（JPMorgan Chase）的利率敞口与贷款增长，并给出了前瞻性预测，但全文没有给出任何买入、持有或卖出的决断建议。太棒了，评估裁判完全按照我们预设的逻辑在工作——它精准指出了该报告缺少明确、具象化投资建议的硬伤。

<details>
<summary>Original English</summary>

**Instructor**: So let's look at actionability in Phoenix. It's so cold in here that my fingers have gone all numb and I can't type properly. Okay. So, the report analyzes JPM's rate exposure and loan growth and a forward-looking output, but makes no buy, hold, sell recommendations. Fantastic. It's doing exactly what it's supposed to do. It is complaining about the lack of concrete recommendations.

</details>

**讲师**：在逐一分析这些详细建议之前，我们首先应该重点关注评估结果的分布比例。在我测试的数据集中，16 份研报里有 5 份被判定为具备可操作性，11 份被认定为不具备可操作性。这种产生分化的评估结果，往往是工程中最有价值的评估资产。如果一个评估指标的所有测试样本都拿了满分，或者反过来全军覆没全是不及格，那它能提供的指导信息极度有限。只有当评估结果呈现出健康的阶梯式分布时，你才拥有了一座可以持续攀登的“性能山坡”：你既拥有了一批运转良好的正向标杆样本，也拥有了一批暴露缺陷的负向样本，从而可以系统性地深挖两类结果之间的本质差异。

<details>
<summary>Original English</summary>

**Instructor**: Before we look at all of these recommendations, we should look at the split in the recommendations. In my data, 5 of 16 reports were actionable and 11 were counted as not actionable. And that is one of the most useful types of evals you can get. An eval where everything is perfect is not particularly helpful. An eval where everything is wrong is also equally unhelpful. An eval where you've got an even split, that is a hill that you can climb. You've suddenly got a set of examples where things are actually working, a set of things where stuff isn't working, and you can start figuring out the differences between them.

</details>

**讲师**：我们继续快速浏览这些 trace 日志，我就不逐一点开所有样本了。例如在 Rivian 的报告中，裁判给出的理由是“从未提出买入、持有、卖出建议或任何实质性的后续行动指令”；在英伟达（Nvidia）的报告中，裁判指出“结语中将投资逻辑的风险等级定为‘中等’，这只是一个模糊的评级标签，根本算不上明确的决策指导”；而在 Meta 的报告中，裁决意见也明确指出“结论仅仅声称当前仓位维持稳健”。你会发现，几乎所有失败样本都暴露出高度一致的共性缺陷：模型在持续回避给出明确具体的投资指导……

<details>
<summary>Original English</summary>

**Instructor**: So if you click through these traces—I'm not going to bother clicking through all these traces. In Rivian, it says it never makes a buy, hold, sell recommendation or any equivalent next step. For Nvidia, it said the closing investment thesis risk level is moderate is vague rating, not guidance. And for Meta, the verdict is only that the position is solid. So this is the same problem over and over: it is refusing to give concrete...

</details>

<!-- chunk 10/13 -->

### 将评估提示词视同代码

**Speaker**: ……“买入”、“卖出”还是“持有”的建议。如果我们愿意，可以打开 Phoenix 的提示词模板，不过我现在先不打开了。但是，关于评分标准（rubric），还有一条非常关键的规则：你应该把评估提示词当成代码来看待。输入到自定义评估器中的评估提示词，对用词上的微小变化极其敏感。

<details>
<summary>Original English</summary>

**Speaker**: buy, sell, hold recommendations. Um, if we uh we can open the Phoenix prompt template. I'm not going to do it now. Um, but uh there's one more rule for rubrics, which is that you should treat eval prompts as code. Your eval prompts going into your into your custom eval are extremely sensitive to small changes in wording.

</details>

**Speaker**: 我在制作这个项目时就遇到了一个典型的例子：之前我跟你们说过，应该给各种内容加上 XML 标签。但我一开始忘了给自己的示例加上 XML 标签。当我的示例只是纯文本时，我得到了一连串判定为“不可执行”（not actionable）的结果，因为评估器彻底搞混了哪些是实际数据，哪些是我提供的示例。而当我用 XML 标签把示例包裹起来后，所有内容突然间都变得可执行了，因为它终于能分清我指的是什么了。这期间没有做任何其他改动——每一次我都给它相同的数据、相同的指令、相同的输入和相同的输出。仅仅是因为加上了 XML 标签，评估器对正在发生的事情减少了混淆。因此，你必须把评估逻辑当成代码一样对待：对它们进行版本控制、严格审查并进行充分测试。

<details>
<summary>Original English</summary>

**Speaker**: Um, so, uh, one example of that I ran into while making this was, uh, I told you that you should put XML tags around stuff. I forgot to put XML tags around my examples to begin with. Uh, and with my examples as plain text, uh, I got a string of not actionable stuff, uh, because it was getting confused about what the data was and what my examples were. And when I wrapped them in XML tags, everything suddenly became actionable because it could tell what I was talking about. Um, this is there was no other change. I'd given it the same data, the same instructions, the same input and the same output every time. Uh, it just got less confused in the evaluator as to what was happening. Uh, so you have to treat your evals as code. You should version them, you should check them, and you should test them.

</details>

### 避免“全能上帝评估器”的陷阱

**Speaker**: 正如我之前提到的，在编写评估器时很容易掉入一个陷阱，那就是试图写一个包揽一切的“全能评估器”（god evaluator）。这是一种非常普遍的反模式。你试图让它在单个提示词中同时检查准确性、语气、完整性、格式规范以及合规政策。这简直是一场噩梦，因为一旦评估失败，你根本不知道究竟是哪个环节出了问题：是事实不准确？还是语气不对？亦或是忠实度有问题？在这个被赋予了无数职责的“全能评估器”所考察的众多维度中，到底哪一项不合规？如果你试图通过让它输出 15 种不同的标签来解决这个问题，整个系统就会变得极其难以追踪。

<details>
<summary>Original English</summary>

**Speaker**: Um, as I mentioned earlier, uh, there is a trap to fall into with evaluators, which is to try and write write one evaluator that does everything for you. It is called the god evaluator because it is such a a common pattern. Uh, you try and get it to check accuracy, tone, completeness, formatting, policy all in a single prompt. Uh, and it is a nightmare because if it fails, what thing failed? Was it inaccurate? Was the the tone wrong? Was the faithfulness wrong? which of the many many many things that you've told this god evaluator to evaluate is it actually wrong and you try and solve that by giving it 15 labels that it can spit out uh and the whole thing becomes very hard to track.

</details>

**Speaker**: 最佳实践是将其拆解开来：你测试多少个维度，就将评估器拆分成多少个专职评估器。比如一个专门负责保真度（faithfulness），一个专门负责正确性（correctness），还有一个专门负责可操作性（actionability）。同时，你也应该清楚哪一个评估器是“护栏”（guardrail），哪一个是“北极星指标”（north star）。护栏是必须直接阻断发布的底线要求，例如，如果智能体捏造了股票价格，那就必须立即停止发布上线。而北极星指标则是你的追求目标，比如“推荐其他值得关注的股票”是一项很好的加分项，你的评估器可以检测这项能力，但不必将其作为发布的硬性门槛。

<details>
<summary>Original English</summary>

**Speaker**: Uh the best practice is to split this up split your evaluators into as many dimensions as you are testing. So one for faithfulness, one for correctness, one for actionability. Um, and you should also know which one of your evals is a guardrail and which one is a north star. So, a guardrail is something that should block the release. So, if the agent is making up a stock price, that should halt shipping. Uh, but north stars are things that you're aiming for. So, suggests other stocks worth a look would be nice to have. That would be a good thing to include. Your eval can look for that, but it doesn't have to gate shipping on that.

</details>

### 第六步：测试你的测试（评估裁判模型）

**Speaker**: 这就带我们来到了第六步：测试你的测试。我们已经构建了一个裁判模型（judge），它指出我们的一部分报告缺乏可操作性。但是，我们能信任这位裁判吗？我们怎么知道裁判的裁决是否正确？这里的诀窍在于牢记：在经典机器学习的意义上，你的裁判本质上就是一个分类器（classifier）。它审视一份报告，并预测其标签是“可操作”（actionable）还是“不可操作”（not actionable）。预测既可能是对的，也可能是错的。因此，就像评估任何分类器一样，你需要通过将它的预测结果与真实标签（ground truth）进行比对来衡量其准确性。而这里的“真实标签”，就是人类专家给出的评判。你必须给这位裁判的作业打分。

<details>
<summary>Original English</summary>

**Speaker**: Which brings us to step six, which is testing your tests. We've built a judge and it says that some of our reports aren't actionable. Uh but can we trust the judge? How do we know that the judge is right? Uh the trick to remember is that your judge is a classifier in the classic ML sense. Uh it is looking at a report and it is predicting a label as actionable or not actionable. Predictions uh can be right or wrong. So like any classifier, you measure it by comparing its predictions with the truth. Uh, and here the truth is what a human expert would say. You get to judge uh you get to mark the judge's homework.

</details>

**Speaker**: 在这个案例中，所谓的人类专家就是我。由我来判定这些股票到底属于买入、卖出还是持有。虽然我未必是你们心目中最理想的金融专家，但我们在尽力而为，这毕竟只是一次演示。具体的操作流程非常简单：打开一个追踪记录（trace），点击小铅笔图标，就可以添加标注（annotations）。我预先创建了一个名为 `human actionable` 的标注字段，我可以将其设置为 `actionable` 或 `not actionable`。这样我就能非常快速地浏览所有的追踪记录，并在每一条记录上打上标签——这些我都已经提前完成了。

<details>
<summary>Original English</summary>

**Speaker**: Uh, in this case, the human expert is going to be me. I'm going to be deciding whether or not stocks are buy, sell, or hold. Uh, not necessarily the expert that you want. Uh, but we're doing our best. It's just a demo. Um, how you do this is very simple. You open up a trace. uh you click the little pencil button and you can add annotations. So I have created an annotation in advance called human actionable uh and I can set it to actionable or not actionable and I can very quickly uh click through all of my traces and set that on each one which I've done in advance.

</details>

### 构建黄金数据集与对抗疲劳

**Speaker**: 在实际工作中，这就是你需要领域专家介入的地方。你可以让他们直接使用 Phoenix，跟他们说：“这里有 10 条、20 条甚至 50 条追踪记录，请逐一通读输出内容，并针对这些结果是否合格，为我标注出一份黄金数据集（golden data set）。”我此前花时间严格对照给裁判制定的同一套标准，认真标注了我手头的全部 16 份报告。这些标注已经内置在你们的基础种子项目中，省得你们自己花大量时间去逐个标注了。正如我所说的，你通过这种方式构建起来的资产被称为“黄金数据集”——在人类认知范围内，你可以确信这些样本的标准答案是完全正确的。

<details>
<summary>Original English</summary>

**Speaker**: Uh this is where you would get uh a domain expert involved. You would throw them at Phoenix. You'd say here are 10 traces, here are 20 traces. there's 50 traces. Go through and read the output and give me give me your golden data set about whether or not these things are good. Um, [snorts] I sat down and labeled all 16 of my reports properly against the same criteria that I gave the judge. Uh, and those are sitting in your seed project so that you don't have to do that because that would take you a long time. Um, what you're building when you do this, like I said, is called a golden data set. Uh it's examples where to the best of human knowledge you know that the answers are right.

</details>

**Speaker**: 人工标注是一项繁重的工作，所以你必须让每一份付出都物有所值。为此，你在标注时必须遵循与提供给裁判模型完全相同的具体准则。这也是我们前面提到过的那个失误——当时我并没有严格遵照自己写进评估准则里的规则。我自己违反了自己定下的规矩：我的规则明确写着“必须包含风险分析”，但我却判定一份根本没有包含风险分析的报告合格。结果导致我和裁判产生了分歧，而我认为裁判其实比我更准确，因为它执行得更加严格。在这个环节中，你最大的敌人是疲劳感。如果你给自己安排了 100 条追踪记录去评判，往往评到第 50 条时，你就会感到极度枯燥厌烦，标注也会随之变得敷衍草率。

<details>
<summary>Original English</summary>

**Speaker**: Um it is a lot of work so you should make that work count. So you should give yourself the same specific criteria that you gave the judge. That was the error that we were talking about earlier. Uh where I was not exactly reading the rules that I had put into my eval criteria. Right? I was disobeying one of my own rules. my rule said uh must include risks and I said that this report is fine even though it doesn't include risks. Uh and as a result me and the judge disagreed and I feel like the judge was actually more correct than I was. It was being stricter. Um so uh your enemy here is fatigue. Uh if you give yourself a hundred traces to judge by trace 50, you're going to be really bored of judging traces and you're going to get lazier about it.

</details>

### 黄金数据集的构建准则与正反向测试

**Speaker**: 因此，拥有 50 个经过严谨标注的高质量样本，远胜过拥有 100 个随意浏览后随手点“看起来还行”的低质样本。黄金数据集中的数据质量越高，后续整个评估体系就会越可靠。你能做的最好实践之一，就是持续不断地扩充你的黄金数据集：每当你在实际生产中遇到棘手的个案或古怪的异常行为时，去搞清楚理想的正确答案应该是什么，然后把它补充进你的黄金数据集里。构建优秀的黄金数据集有几条实用法则：首先，你编写的测试任务必须是人类能够完成的。如果你的智能体在某个任务上每次都失败，那几乎必然是任务设计本身有问题，而不是智能体出了故障。其次，针对每个任务，你都必须准备一个已知合格的标准答案，以此证明该任务确实是可行的。

<details>
<summary>Original English</summary>

**Speaker**: Uh so it is better to have 50 really well-labeled uh examples than a hundred where you were just clicking through and saying ah this looks fine. Uh the the higher the quality the data in your golden data set uh the more reliable everything is going to be. Um and one of the best things that you can do is that uh is continuously add to your golden data set. when you see a tricky example, when you see something strange happen in production, figure out what the answer should have been and put it into your golden data set. Uh, a few good rules for human go for a good golden data set is that you should write test tasks a human could pass. Uh, if your agent fails a task every single time, that is almost always going to be a broken task, not a broken agent. Um, and for each task, you should have an answer that you know is good, which proves the task can be done.

</details>

### 数据集划分与元评估实验

**Speaker**: 此外，你还必须进行正反双向测试。举例来说，如果你只在智能体理应搜索网页时检查它是否进行了搜索，你就会在无意中把智能体训练成不管何时何地、哪怕毫无必要也无休止地去搜索网页。这里还有一条源自机器学习并同样适用于裁判模型的铁律：千万不要在测试集上调优。把你的标注数据拆分成两组：一组用于调优评估器，另一组专门用于验证评估器是否有效。当你的黄金数据集中总共只有 16 条标注结果时，这会导致你的测试集显得非常小。因为通常的划分法则是 75% 用于调优集（开发集），25% 用于测试集，所以在我们的测试集里只有 4 条样本。但如果样本量达到 100 条，这样的拆分就会非常合适。

<details>
<summary>Original English</summary>

**Speaker**: Uh, you should also test in both directions. If you only check, for instance, that the agent searches the web when it's supposed to search the web, you're going to accidentally train your agent to search the web every single time, all the time, even when it doesn't need to. Uh, and here's a rule from machine learning that applies to judges as well. Don't tune on your test set. Uh, split your labels into two groups. One that you use to tune your evals and one that you use to test that they are working. Uh when you only have 16 answers in your golden data set, that makes it your test set very small. Uh because the rule is usually 75% in the tuning set, 25% in the test set. So there's only four in our test set. Uh but if you were up to 100, that would be fine.

</details>

**Speaker**: Phoenix 数据集原生内置了数据切分（splits）功能，因此实现起来非常轻而易举。我们来看看具体是怎样运作的：首先，它构建了带有数据切分的黄金数据集。它找到每一份带有人工标注的报告，将每一份报告转化为 Phoenix 数据集中的一个样本。输入是这份分析报告，期望输出是人类打上的标签。我们按照 `span ID` 对它们进行排序，然后每四个样本中的一个被划入测试集（test split），其余的划入开发集（dev split）。先排序意味着无论你运行多少次代码，同一份报告每次都会固定落入相同的切分数据集中；而 `span ID` 则将每个样本关联回它原本来源的追踪调用链，方便你随时点击跳转回原始的运行记录。

<details>
<summary>Original English</summary>

**Speaker**: Um Phoenix data sets have splits built in. So this is very easy to do. Uh see what that looks like. uh so first it builds the golden data set with splits. It finds every report with a human label. Uh uh and each one becomes an example in a Phoenix data set. The input is the report. The expected output is the human's label. We sort them by span ID. Then every fourth example goes into the test split and the rest go into dev. Uh sorting first means that a report always lands in the same split however many times you run this. Uh, and span [snorts] ID links each example back to the trace it came from. Uh, so you can always click through to the original run.

</details>

**Speaker**: 接下来，我们让裁判模型与人类的评判结果进行比对运行。这是一项实验（experiment），我们稍后会对此进行更深入的探讨。就目前而言，一项实验接收一个数据集作为输入，接收一个在每个样本上运行的任务（task），以及一组对运行结果进行打分的评估器（evaluators）。在这里，任务就是我们的裁判模型，而评估器则是一个轻量级的代码评估逻辑，用于校验裁判给出的标签是否与人类专家的标签完全一致。请注意，我们当前只在开发集（dev split）上运行它。大家也可以在终端运行 `npm run meta` 亲自跑一遍。我们来看看它能不能跑通——它即将调用一个大语言模型。我相信它的执行结果应该和昨天晚上运行的结果完全一致。脚本在最后应该会打印出一个汇总小表格。在我的这 12 份开发集报告上，裁判和我……

<details>
<summary>Original English</summary>

**Speaker**: Then we run the judge against the humans. This is an experiment which is something that we're going to dig into in a little bit. Um, but for now uh an experiment takes a data set. It takes a task task to run on every example uh and evaluators to score the results. The task here is our judge and the evaluator is a tiny Kodi val which checks whether the judge's label matches the humans. Uh notice that we only run it in the devs split. Uh you can run this yourself by running npm run meta. [sighs] Let's see if we can get it to go. It's going to run an LM. So, uh, I'm going to assume that it does the same thing that it did last night. Um, the script should print a little table at the end. Uh, and on my 12 dev reports, the judge and I

</details>

<!-- chunk 11/13 -->

### 评估结果分析：可口可乐与微软案例

**Speaker**: 模型每次都做出了相同的判定，这固然很好，但这仅仅是针对 12 份报告的测试。因此，目前只能说明尚未发现任何问题。在生产环境中实际运行这套系统时，显然需要一个规模大得多的测试集。很好，它实际上已经运行完毕了。更有意思的部分在于我个人认为最难标注的那两份报告。在我的 Phoenix 数据集中，有可口可乐（Coca-Cola）和微软（Microsoft）的报告。

<details>
<summary>Original English</summary>

**Speaker**: made the same call every time, which is great, but it's also only 12 reports. So read that as, you know, no sign of a problem yet. You're going to want a larger test set when you're running this in production. Cool. It actually completed it. The more interesting part is the two reports that I found hardest to label. So in my Phoenix data, there's Coca-Cola and there's Microsoft.

</details>

**Speaker**: 首先看第一份，也就是可口可乐的报告。正是这份可口可乐的报告，在我把 Prompt 从没有 XML 标签改为引入 XML 标签之后发生了判定反转。在它获得了具体的示例之后，表现确实变好了。但我发现，连我自己都觉得处于临界状态的案例，对大模型裁判来说同样非常模棱两可。可口可乐的那份报告称 KO（可口可乐股票代码）是“保守型收益导向投资组合的理想选择”，这听起来确实很像一个投资建议。所以作为人类，我当时反复纠结到底算不算给出了投资建议。最终我认为它不算，但大模型裁判在判断这到底算不算充分的建议时，也同样在反复摇摆。

<details>
<summary>Original English</summary>

**Speaker**: The first one is Coca-Cola. The Coca-Cola is the one that flipped when I changed from not having XML tags to having XML tags. This is where when it got the examples it got better. Borderline for me turns out to be borderline as well. The report calls KO ideal for conservative income oriented portfolios, which sounds like a recommendation. So as a human I went back and forth on whether or not I should count that as a recommendation. Ultimately I decided it did not, but the judge also goes back and forth on whether or not that counts as enough of a recommendation.

</details>

**Speaker**: 第二份报告是微软的，我就不特意点进去了，它的情况正好相反。这份报告明确给出了“买入”建议，并列出了理由和时间跨度，但它通篇没有提及任何风险。这就是我之前提到的那个例子。我的评分准则（rubric）中将“指明具体风险”列为一项评估标准。我人工评估时觉得这份报告没有大问题，但大模型裁判却判定不通过。裁判指出它在风险分析方面很薄弱，完全没有风险章节；虽然勉强达到了具备可操作性的门槛，但也仅仅是勉强过关。因此，裁判在审视这些内容时，所给出的判断与我的人类判断几乎完全吻合，包括那种模棱两可的模糊感也是一致的。

<details>
<summary>Original English</summary>

**Speaker**: And the second one was Microsoft, which I'm not going to bother to click into, which is the other way around. The report says buy with reasons and a time horizon, and it never mentions a single risk. This is the one that I was talking about earlier. My rubric lists name concrete risks as a criterion, and I decided that was fine and the judge decided that that was not fine. It said it was weak on risks. There is no risk section. It clears the bar for actionability though not by much. So, the judge looking at this stuff came up with exactly my human judgment on whether or not this was an actionable report, including the ambiguity.

</details>

### 修改评分准则的潜在风险

**Speaker**: 这种模糊性目前仍然存在于我们的评分准则中，因为我们还没有去修改它。所以很自然地，我们非常想去修正它。于是我尝试添加了一句话：“一份报告只有在完全满足全部四项标准时，才算具备可操作性。”因为在此之前这里的定义是模糊的，我原先写的是“报告应当包含所有这些要素”，并没说“必须包含”。所以你可以通过修改评分准则来让标准更加严格具体，明确规定必须绝对满足这四项标准。然而在开发集（dev set）上，这一改动直接让微软的报告判定失效了，原先 12 份报告中有 12 份与人工一致，现在变成了 11/12。

<details>
<summary>Original English</summary>

**Speaker**: And that ambiguity is still in our rubric because we haven't changed it yet. So it's very tempting to fix it. So, I tried I added one sentence which was a report is actionable only if it meets all four criteria because previously that was ambiguous. I said a report should include all of these things. I didn't say that it must. So you can change the rubric and be more specific and say yes this absolutely must contain all these four criteria. And on dev that broke Microsoft, my 12 out of 12 agreement became 11 out of 12 agreement.

</details>

**Speaker**: 不仅如此，在测试集切分中，它还导致苹果（Apple）的报告判定失效，因为在大模型裁判看来，苹果报告里的风险部分篇幅不够长。这说明了一个非常重要的现象：即便初衷是为了让标准更明确，盲目修改评分准则反而可能让评测效果变差，让评测失去原有的参考价值，甚至让它偏离人类真实的评判逻辑。

<details>
<summary>Original English</summary>

**Speaker**: And also in the test split it broke Apple, because Apple didn't have a big enough risk section as far as the judge was concerned. What that tells you is that I could change my rubric and make my eval worse. I can make my eval less helpful. I can make my eval less like what a human would do, even though I'm trying to be specific.

</details>

### 精准率与召回率的权衡

**Speaker**: 测试脚本同时还会打印出精准率（Precision）和召回率（Recall）。这些指标同样借用自机器学习或统计学领域，非常关键。精准率衡量的是：当裁判判定一份报告“不具备可操作性”时，这一判定的准确率有多高？而召回率衡量的是：在所有客观上确实不具备可操作性的报告中，裁判成功抓出了多少？这两个概念听起来非常接近，但衡量的维度完全不同。

<details>
<summary>Original English</summary>

**Speaker**: The script also prints precision and recall. These are very important things again borrowed from the ML land or rather from stats land. Precision asks when the judge says not actionable how often is it correct? And recall asks of all the reports that aren't actionable how many did the judge catch? Those two sound very similar but measure different things.

</details>

**Speaker**: 在绝大多数场景下，你都会倾向于优先保证召回率。因为高召回率能确保你捕获所有存在缺陷的内容，虽然高召回率抓得全，但代价是会带来更多的误报（False Alarms）。误报的代价无非是浪费你一两分钟时间，去人工复核一份其实原本合格的报告；然而如果出现漏报，一份劣质的报告就会直接流向最终客户。因此两者必须有所权衡：如果提高召回率，精准率通常就会下降，反之亦然。针对具体的业务应用，你必须权衡清楚：究竟是宁可产生误报（把实际上合格的样本挑出来人工核对），还是承担漏报导致劣质内容流出的风险更严重。

<details>
<summary>Original English</summary>

**Speaker**: In most cases, you're going to want to prioritize recall because what recall gives you is it catches everything, but high recall catches everything, but it will give you false alarms. A false alarm costs you a minute or two when you look at a report that turns out to be fine. But a missed failure would give you a bad report that reaches a customer. So you have to trade one for the other. If recall goes up, then precision will go down and vice versa. So for your application you have to decide whether being accurate as in throwing away some things that were actually correct but you decided they weren't is better or worse than getting false alarms where you say something is important and it turns out not to be.

</details>

### 大模型裁判的固有偏见与人类一致性基准

**Speaker**: 大模型裁判本身也存在各种固有偏见。我之前已经提到过其中一种。第一种是位置偏见（Position Bias）：当给它两个选项进行对比时，模型往往会倾向于排在前面或排在后面的选项，具体取决于模型训练时的数据偏好。因此在评测时应当调换选项的呈现顺序，避免模型始终以固定顺序观察输入。第二种是长度偏见（Length Bias），裁判通常更偏爱较长的回答；同时还存在自信偏见（Confidence Bias），裁判偏好语言表达流畅、语气笃定的回答。

<details>
<summary>Original English</summary>

**Speaker**: Judges also have biases. I mentioned one of them already. One is position bias. Given two options, they tend to prefer depending on the model either which one comes first or which one comes last. It depends which way around the model was changed. But you should swap your options so that it's not always looking at those things in the same order. They have length bias. Judges prefer long answers, and they also have a confidence bias. Judges prefer answers that sound fluent and confident.

</details>

**Speaker**: 还有我之前提及的自我偏好偏见（Self-preference）：大模型在给自己的输出打分时，给出的评分往往偏高。这就是为什么我们选择用 Claude Sonnet 来给 Claude Haiku 打分，而在理想情况下，你应该使用 OpenAI 的模型来充当 Haiku 的裁判。不过，在你对裁判的可靠程度过度焦虑之前，有一点必须认清：即便是人类专家评委，彼此之间在很多时候也存在极大的分歧。

<details>
<summary>Original English</summary>

**Speaker**: And the one that I mentioned already is self-preference. A model judging its own output tends to rate it higher. Which is why we judged Haiku with Sonnet, and ideally you judge Haiku with something from OpenAI. But before you get too worried about how much you can trust a judge, it's worth noting that human judges also disagree with each other a lot of the time.

</details>

**Speaker**: 如果你把相同的输出结果和评分准则交给两位专业人类评审，并衡量他们的一致率，统计学上有一个专门衡量这种一致性的标准指标叫做科恩卡帕系数（Cohen's Kappa）。在类似的任务中，这个系数往往只有 0.2 到 0.3，这意味着人类专家之间达成一致的概率仅仅比纯粹的随机猜测略高一点点。因此，模型裁判的对照基准就是人类的表现，而单看人类之间的相互一致性，人类表现本身其实并不怎么高。所以你根本不需要一个 100% 遵从你个人偏好的裁判，事实上裁判也绝不可能做到 100% 与你完全一致。你真正需要的是一个表现能超越普通人类评委的大模型裁判，因为裁判可以在成千上万个样本上快速执行，从而发挥巨大的规模优势。

<details>
<summary>Original English</summary>

**Speaker**: If you give two experts the same outputs in the same rubric and measured how often they agree, there is a standard score for that called Cohen's Kappa, and for this kind of task, it's often as low as 0.2 or 0.3. Which is to say they agree with each other not very much more often than just random chance. So the bar for your judge is human performance, and human performance is not actually that good when you compare humans to each other. So you do not need a judge that agrees with you 100% of the time. Your judge is never going to agree with you 100% of the time. What you want is a judge that does better than another human doing the judging would be, because your judge can run across thousands of examples and help itself out that way.

</details>

### 评测的合理性与 Benchmark 的持续迭代

**Speaker**: 关于大模型裁判，最后一条重要原则是：失败判定必须显得合理公正。当一个任务被判定失败时，Agent 究竟哪里做错了必须一目了然。如果你仔细查看被判失败的样本，心想“其实我觉得这完全挑不出毛病啊”，那么问题大概率出在你的评测本身。这里有一个非常著名的案例：当 Claude Opus 4.5 最初在一个测试智能体能否复现科研论文的基准测试 Corebench 上运行时，得分仅有 42%。Anthropic 对这个过低的分数感到非常困惑。

<details>
<summary>Original English</summary>

**Speaker**: One last principle on judges is that failures should seem fair. When something fails, it should be obvious what the agent did wrong. If you look at the failure and go, "Well, actually that looks fine to me," then the problem is probably your eval. There's a famous example of this when Claude Opus 4.5 first scored 42% on a benchmark called Corebench which tests whether agents can reproduce scientific papers. Anthropic were upset about that low score.

</details>

**Speaker**: 于是研究人员去审查了具体的执行记录，结果发现 Claude 的答案本质上并没有错，只是呈现方式不同：测试预期要求精确到小数点后 6 位，而 Claude 给出的正确答案保留了 4 位有效数字，测试用例就直接判定为错误。此外，还有许多任务描述本身含糊不清，甚至有些科研任务压根就无法被复现。因此 Anthropic 团队逐一修正了所有测试用例，并指出这些测试本身需要优化。修正之后，Claude 在该评测上的得分瞬间跃升到了 95%。

<details>
<summary>Original English</summary>

**Speaker**: So a researcher ran the actual transcripts and found that Claude was just being right in a different way. The test expected six digits of precision and Claude gave the right answer to four digits of precision rather. And the test said that was wrong. There were ambiguous task descriptions. Some of the tasks couldn't be reproduced at all. So Anthropic went through and they fixed all of the tests and they said these tests could be better. And magically they got 95% on the eval.

</details>

**Speaker**: 这种情况在行业内屡见不鲜。SWE-bench 以及大家见到的各类基准测试，都在不断地被重新评估和人工调优。这也是为什么业界知名的基准测试总是会推出 V2、V3、V4 版本的原因——因为人们在实践中不断发现这些测试基准本身存在缺陷。你自己的评测集最终也会遇到同样的问题。因此，你需要对测试集保持持续的审视与重估。

<details>
<summary>Original English</summary>

**Speaker**: This happens all the time. SWE-bench and all of the other benchmarks that you see are constantly being re-evaluated and manually tweaked, and that is why you see version two, version three, version four of the famous benchmarks, because people are constantly finding that the benchmarks are not actually as good as they could be, and your evals are going to end up with the same problem. So you need to be constantly re-evaluating your test set.

</details>

### 进入第七步：构建对照实验

**Speaker**: 这就把我们引向了第七步：开展实验（Experiments）。现在我们手里有了值得信赖的评测体系，接下来就要利用它们来切实改进智能体，并严格验证修改是否奏效。由于之前的节奏比较从容，时间开始有点紧了，我现在会讲得稍快一点。

<details>
<summary>Original English</summary>

**Speaker**: Which brings us to step seven which is experiments. We've got evals that we trust. Now we are going to use them to actually improve the agent and prove that the fix worked. I'm going to go a little faster now as I've been going on a very leisurely pace. I'm beginning to run out of time.

</details>

**Speaker**: 核心问题在于：我们现在已经知道部分报告缺乏可操作性，也查明了原因。那么我们修改了 Prompt 之后，接下来该怎么做？你怎么知道修改真的起效了？你怎么确定修改 Prompt 没有把之前本来正常的功能搞崩？如果你仅仅挑几个例子随便看两眼凭感觉判断，那就又退回到了“靠玄学感觉（vibes）”的状态。没有经过严格量化衡量的 Prompt 变更，纯粹就是凭感觉。你真正需要的是可控的对照实验（controlled comparison）：在修改前后保持完全相同的输入集、运行完全相同的评估流程，这才是真正的科学实验。在 Phoenix 中，你可以将筛选出来的那些判定为不可操作的评估样本勾选并添加到数据集中，从而形成一个专门用来验证特定缺陷的测试集。我这里就不重新演示具体操作了，因为我已经在旁边提前建好了。

<details>
<summary>Original English</summary>

**Speaker**: So here's the problem. We know that some reports aren't actionable and we know why. So we change the prompt and then what? How do you know that it worked? How do you know that you didn't break something that was working before? If you run it on a couple of examples and eyeball it, then you're back to vibes. A prompt change that you haven't measured is just a vibe. What you want is a controlled comparison. You want the same inputs, the same eval before and after. That is an experiment. So what you can do in Phoenix is you can take a bunch of your evals that you have filtered down to not actionable say, and you can select them and you can add them to a dataset. That gives you a set to test against specific things. I'm not going to do that since I've already done it over here.

</details>

<!-- chunk 12/13 -->

### 根据评测结果针对性优化 Prompt 与构建实验

一旦你拥有了一个数据集，就可以将其转化为一个实验，并专门针对该数据集运行你的实验——仅针对那些此前失败的评测项运行，而无需每次都在整个完整数据集上全部重跑一遍。要知道，如果你有一个规模不错的分割集和测试集，这种做法每次都能为你节省成千上万次测试的开销。现在我们要来修复评测所发现的问题。如果你还在跟着一起写代码，祝贺你。请打开 `prompts.ts`，里面为每个 Prompt 都准备好了改进版本，当然你也可以自己编写。

<details>
<summary>Original English</summary>

Once you have a dataset, you can turn that into an experiment and run your experiment against only the dataset, only against the evals that were failing, as opposed to against your entire set every single time. If you've got a decent-sized split and a decent-sized test set, that is saving you thousands and thousands of tests every time. Now we're going to fix what the eval found. So, if you're still coding along, congratulations. Open `prompts.ts`. There is an improved version of each prompt, or you can write your own.

</details>

这里的每一处修改都严格对应一项评测发现：评测裁判指出 Agent“未给出任何建议”，于是我们在 Prompt 中明确要求给出具体的建议；裁判指出 Agent“提到了风险但没有任何依据”，于是我们要求列出风险时必须附带支持数据；真实性评测发现了虚构的数据数字，于是我们规定“只能使用调研过程中实际出现的数字”；通过阅读 Trace 发现 Agent 总是在尝试保存文件，于是我们让它改为直接在回复中输出报告。我们在这里绝不是凭空瞎猜，而是完全基于先前评测运行的实际结果，为 Agent 量身定制具体的操作规范。

<details>
<summary>Original English</summary>

And every change maps to a finding. So, the judge said, "makes no recommendation," so we asked for an explicit recommendation. It said "mentions risks with no evidence," so we asked for risks with supporting data. Faithfulness found invented numbers, so we said "use only numbers that appear in your research." And reading traces found that the agent was trying to save files all the time, so we tell it to reply with the report instead. We're not guessing here. We are coming up with specific things for the agent to do as a result of the previous results of our evals.

</details>

这就是实验脚本的样子：一个实验由数据集、任务以及评估器组成。数据集就是我们刚才创建的那个；任务则是一个函数，用来针对每个样本运行 Agent。在当前这个例子中，我们要运行的是整个 Agent，但你也可以选择只针对 Agent 行为的某一部分或者某个特定的子集来运行。

<details>
<summary>Original English</summary>

This is what the experiment script looks like. An experiment is a dataset, a task, and evaluators. The dataset is the one that we just created. The task is a function that just runs the agent on each example. In this case, we're running the entire agent, but we could be running it on a specific subset of the agent's behavior or a specific part of it.

</details>

### 测试样本数量与 Agent 的非确定性（Pass@k 与 Pass^k）

我提前跑完了我的实验。一个非常好的问题是：我们到底需要多少个测试样本？10 到 20 个样本能够为你指明大致的演进方向，这在开发阶段非常有用；而如果你准备推向生产环境，那你需要成百上千个样本。虽然跑完需要很长时间，但对于保障准确率来说是非常值得的。在准确率评估中，为了将误差范围减半，你需要将样本数量增加到四倍。因此，从 25 个样本增加到 100 个样本是非常有价值的，而且付出的精力也不算太大；但要想再获得同等幅度的精度提升，你就得把样本增加到 400 个，这往往就进入了人们懒得去做的领域。不过总的原则是样本越多越好，并且你放入数据集中的生产环境失败案例越多越好。

<details>
<summary>Original English</summary>

I ran mine ahead of time. "How many examples do you need?" is a really good question. 10 to 20 examples gives you a rough direction of where things are going and is very useful in dev. If you're getting into production, you're going to want hundreds of examples. That is going to take a long time, but is very worth it for accuracy. To halve your error bars on your accuracy, you need to quadruple the number of examples. So, going from 25 examples to 100 examples is really, really helpful and is not that much effort. To get that big a jump again, you'd have to go to 400 examples, which begins to get into the territory of you're never going to bother to do this. But the bigger the better, and the more production failures you throw into your dataset, the better.

</details>

我把我的测试运行了 3 次，之所以这样做，是因为 Agent 本身具有非确定性，单个样本的单次运行可能会在正面或反面误导你。当一个 Agent 多次运行时，有两种非常有用的思考方式：第一种叫 Pass@k，意思是它在 k 次尝试中是否至少成功了一次；第二种叫 Pass^k，意思是在运行 k 次时，它是否每一次都成功了。随着 k 值的增大，这两个指标会产生分化：你给的尝试机会越多，Pass@k 成功的概率就越高，因为只要对一次就行；但给的尝试机会越多，出现至少一次失败的概率也随之升高，因此 Pass^k 就会下降。对于一个代码助手来说，第二次尝试写对是完全可以接受的，所以看 Pass@k 就行；但如果是一个客服机器人，每 5 次运行就有 1 次出错，那将是一个巨大的灾难；而一个给出不准确建议的金融分析师，同样也是致命的问题。对于这类场景，你必须看 Pass^k，要求它每一次都必须通过。

<details>
<summary>Original English</summary>

So I ran mine three times, and the reason I did that is because the agent is non-deterministic. Each run of each example can mislead you in either direction. And there are two useful ways of thinking about how an agent runs when it runs multiple times. The first is called Pass@k, which is does it succeed at least once in k tries. And then there is Pass^k, which is does it pass every single time I run k times. So as k goes up, those two numbers diverge. The more tries you give it, the more likely Pass@k is to succeed, because it succeeds at least once. The more tries you give it, the more likely it is to fail at least once, and then Pass^k will go down. A coding assistant that gets it right on the second try is fine, so Pass@k is fine. A support bot that's wrong one time in every five is a huge problem. And a financial analyst that gives inaccurate recommendations is also a huge problem. So you want Pass^k; you want it to pass every single time for those.

</details>

### Agent 优化的优先级次序

当你在优化一个 Agent 时，基于改动所能带来的实际收益，存在着一个明确的操作优先级顺序。首要的第一位是数据质量：如果底层数据很糟糕，如果数据难以阅读、难以让 Agent 或评测裁判解析理解，那么你之后做任何调整或修补都是徒劳的。一旦你拥有了高质量的数据，接下来才是优化 Prompt——这正是我们今天大部分时间在做的事情，即通过修改评测准则和调整 Agent Prompt 来在提示词层面进行改进。

<details>
<summary>Original English</summary>

When you're improving an agent, there's an order of operations based on how useful making a change is going to be. The first one is data quality. If your underlying data is bad, if it's hard to read, if it's difficult to interpret for the agent or for the judge, then nothing else you do, nothing else you tweak is going to be useful. Once you've got good quality data, then you move to the prompts. That is what we've been messing with mostly today, to make things better at the prompt level by changing our rubric, by changing our agent.

</details>

排在 Prompt 之后的则是模型选型。选择模型具有很大的杠杆效应，但它会同时改变一大堆底层的行为特征；而且换模型的常见方式通常是升级为更大的模型，这会让系统成本更昂贵，从而带来你未必愿意承受的权衡折中。最后是超参数调优，比如温度系数（Temperature）等设置。这类参数实际上几乎毫无用处，以至于现代主流模型甚至已经不再允许你进行调节，比如最新的 Claude 模型你根本无法传入 Temperature 参数。因此，哪怕你跃跃欲试，它也是所有手段中收益最低的一项。

<details>
<summary>Original English</summary>

Then there's model choice. Model choice has a lot of leverage, but it also changes a whole bunch of stuff at the same time. And also the usual way that you're going to change your model is you're going to change it to a bigger model and that makes things more expensive. So that creates a tradeoff that you don't always want to make. And finally, there's hyperparameters. Hyperparameters are things like temperature and stuff like that. They're so useless that modern models have stopped allowing you to tune them. You can't pass temperature to modern Claude models. So if you're tempted to, it is the least useful thing that you can pass.

</details>

### 评测结果分析：能力评测与回归评测

如果你查看我的实验——你也可以在自己的种子数据中查看完全相同的实验——你会发现，随着我对运行流程进行改进：第一项指标从 16 个中通过 15 个提升到了 48 个中通过 48 个；第二项指标从 16 个中通过 5 个跃升到了 48 个中通过 48 个；而真实性指标则从 16 个中通过 2 个变成了 48 个中通过 3 个。这个表现依然不理想，按理说采用了优化后的 Prompt，我们在真实性上的表现应该更好才对。

<details>
<summary>Original English</summary>

So if we're looking at my experiments—you can look in your seed data and see the same experiments—you'll see that as I improved my runs, I went from 15 out of 16 to 48 out of 48, and went from 5 out of 16 to 48 out of 48. And faithfulness went from 2 out of 16 to 3 out of 48, which is not that good, right? Like we really should have done better on faithfulness with my improved prompt.

</details>

至关重要的一点是：原本能通过的用例有没有被搞坏？我们可以过滤查看通过的切片。我现在不打算在 UI 上操作，但事实是在我改进 Prompt 的过程中，之前通过的那 5 份报告依然保持通过。因此，可行动性指标直接拉到了满分；然而真实性依旧糟糕，从 16 个过 2 个变成了 48 个过 3 个，即便 Prompt 里白纸黑字写着“只能使用调研中出现的数字”。也就是说，我们在 Prompt 中用一行指令修复了可度量的特定缺陷，却并没能解决 Agent 凭空捏造内容的问题。这是我们接下来必须为这个 Agent 攻克的难关。我们解决了它能否做出良好判断的问题，但还没能根除它时常捏造数据的问题。如果我们想看，可以深入查看每一次运行的具体情况，由于非确定性，每次运行给出的具体建议都不尽相同。不过由于时间所剩无几，我还想讲讲其他内容，这里就不逐一展开了。

<details>
<summary>Original English</summary>

The important thing is, did anything that used to pass break? We can filter down to the passes split. I'm not going to do it in the UI right now, but all of the five reports that passed previously as I improved my prompt still passed. So actionability went straight to perfect, but faithfulness was bad. Faithfulness went from 2 out of 16 to 3 out of 48, even though the prompt literally says "only use numbers that appear in your research." So we fixed what we measured in a single line of the prompt; it didn't fix the agent making things up. That is the next thing that we have to fix for this agent. We have fixed whether or not it is making a good judgment call, but we have not fixed that it is inventing the data some of the time. If we want to, we can look into each of the runs and you'll see that, because it's non-deterministic, each of the runs are coming up with different advice. But I'm not going to do that because I'm running out of time and I want to get to some other stuff.

</details>

一个好的评测，比如我之前提到在 16 个数据集上的 5/11 分割，属于典型的“能力评测”（Capability Eval）。能力评测衡量的是 Agent 目前还做不到的事情，它为我们提供了一座能够直观度量自己攀登进度的山坡；而当它能够稳定通过、也就是你拥有了一个 100% 通过的测试项时，千万不要把它扔掉，你应该把它转化为所谓的“回归评测”（Regression Eval）。回归评测就是那种可以纳入 CI 流程的测试，并且明确表示：“这项测试过去一直是 100% 通过的，如果突然不再是 100% 通过，那就说明出现了回归缺陷，我们应当立刻阻断发布。”

<details>
<summary>Original English</summary>

A good eval, like the 5/11 split that I was talking about on my 16 datasets, that is what is called a capability eval. A capability eval is a thing that our agent can't do yet, and it gives us a hill that we can measure ourselves climbing. When it passes reliably, when you get a test that passes 100% of the time, you don't throw it away; you turn it into what is called a regression eval. That is the kind that you can put into your CI and say, "This used to pass 100% of the time. If it suddenly stops passing 100% of the time, then we can call that a failure and we should stop release."

</details>

### 模型升级（Haiku 4.5 到 5.5）及其评测表现

接下来的问题是：我们如何翻过这座山坡？我们可以继续打磨 Prompt，或者也可以采取我之前提到的另一个方案——直接升级底层模型。你可以通过传入新模型 Haiku 5.5 来重新跑一遍实验，然后执行 `npm experiment`。我今天一开始就说过：没有评测，绝对不能擅自更换模型。而现在就是当你拥有评测机制后，更换模型应有的标准姿态，因为我们确信自己正在全面量化监控所有这些指标。进行 3 次重复测试需要花费 13 分钟，这已经超出了我们剩下的时间，所以我直接展示最终结果。这是 Haiku 4.5 与 5.5 的对比：真实性确实有所改善，提升到了原来的 3 倍以上，但依旧糟糕，这个 Agent 仍然在不断胡编乱造；不过调用的一致性变好了，因此它确实有所改进……

<details>
<summary>Original English</summary>

"How do we climb this hill?" is the question. We could work on the prompt again, or we could do the thing that I said that we would do, which is we can upgrade the model. So you can run the experiment again by passing in a new model, Haiku 5.5, and then run `npm experiment`. I said at the start of today that you can't switch models without eval. And this is what it looks like when you can switch a model with an eval, because we know now that we are measuring all of these things. With three repetitions, it takes 13 minutes, which is more time than we've got left. So, I'm just going to skip to the results. Here is Haiku 4.5 versus 5.5. Faithfulness improved; it got more than three times better. It is still terrible. This agent is still making things up all the time. But consistent calls got better. So, it is...

</details>

<!-- chunk 13/13 -->

### 模型一致性背后的权衡与过度保守陷阱

**演讲者**：至少它现在能够一遍又一遍地做出相同的决策调用了。但这真的好吗？呃，它的运行成本也是之前的四倍之多。付出这样的代价到底值不值得？呃，在生产环境中进行此类实践时，这是一个你们必须自行权衡和决定的关键问题。嗯，它之所以变得更加一致、不再在不同调用之间反复在“买入”和“卖出”之间摇摆不定的原因之一，呃，在于它直接变得更加保守了。事实证明，Haiku 5.5 呃在所有情况下都只输出“持有”。呃所以，呃这到底算是变好了还是变差了？很可能是变差了。呃我们大概需要针对 Haiku 5.5 在面对事物时过于保守这一倾向进行反复迭代与优化。

<details>
<summary>Original English</summary>

**Speaker**: at least making the same call over and over. Is that good? Uh, it's also costing four times as much money. Is that worth it? Uh, is a question that you need to make for yourself in production when you're doing this kind of thing. Um, one of the ways that it got more consistent, one of the ways it stopped varying between buy and sell between calls, uh, is it just got more conservative. Haiku 5.5 uh it turns out just says hold all the time. Uh so uh is that better or worse? Probably worse. Uh probably we need to iterate on Haiku 5.5 being too conservative uh about things.

</details>

**演讲者**：但至少我们现在明确知道模型行为发生了改变，而且这种过度保守正是 Haiku 5.5 存在的核心问题。嗯，这正是我所发现的具体症结所在。在总共 45 次调用中，它有 41 次都输出了“持有”——也就是说，在 41 次评估调用里全都选择了“持有”，占比达到了惊人的比例。嗯，这在多次运行测试之间确实表现出了近乎完美的一致性。呃所以，就我之前在屏幕这边所讨论的那个“一致性检验”指标而言，它在“输出一致调用”这一项上的表现确实提升了。呃但它达成这种高一致性的手段，却仅仅是每一次、毫无例外地直接给出完全相同的答案。

<details>
<summary>Original English</summary>

**Speaker**: But at least we know now that something has changed and that the conserviveness is a problem with Haiku 5.5. Um that is the problem that I found. It went it went to 41 of out of uh 45 calls it said uh hold 41% of the on 41 of the times. Um which is perfectly consistent between runs. Uh so it it got better at the uh consistency check that I was talking about over here the consistent call. Uh but it got there by just picking the same answer every single time.

</details>

**听众**：[轻笑出声]

<details>
<summary>Original English</summary>

**Audience**: [snorts]

</details>

### 评估驱动开发与闭环迭代流程

**演讲者**：嗯，但这就是完整的“评估-迭代”循环（eval iterate cycle）。呃而整个迭代循环本身才是真正产生价值的地方，价值从来不在于某个人一次性的静态评测得分。你的实际工作流是这样的：运行你的评估集，仔细审阅那些未通过的失败案例及其解释分析，敏锐地识别出背后的失败模式，进而针对性地调整提示词（Prompt）、工具集（Tools）或上下文数据，然后重新跑一遍实验。模型表现变好了吗？呃如今你的自动化评估体系能够实实在在地为你解答这个问题。你可以彻底跨越“我觉得它好像能工作”的主观猜想阶段，真正迈向“我能拿出确凿数据证明它确实有效”的工程确定性。

<details>
<summary>Original English</summary>

**Speaker**: Um but that is the eval iterate cycle. Uh and the cycle is where the value is not anyone's score. You run your evals, you read the failures and the explanations, you spot the pattern, you change the prompt or the tools or the data and you run the experiment again. Did it get better? Uh your evals can now answer that question for you. You can go from I think it works to I can show you it works.

</details>

**演讲者**：呃我刚好有充裕的时间来系统讲解最后一步：如何将评估无缝集成到持续集成流水线（CI）中。呃在业内，越来越多能够极速交付 AI 功能的工程团队，都习惯于在编写具体功能逻辑之前先写好对应的评测标准。这种工程范式被称为“评估驱动开发”（Eval-Driven Development）。嗯，假设你希望客户支持 Agent 在向用户发放退款之前，必须先严格核验客户的真实身份。呃你可以先把针对这一合规规则的评估用例编写好。这样一来，工作成果的“完成定义”（Definition of Done）便有了清晰且可量化的标准，成为你从一开始就可以全力攀登的量化高峰。

<details>
<summary>Original English</summary>

**Speaker**: Uh I have just enough time to talk about how to do the last step which is eval in CI. Uh more and more teams that ship AI quickly write the eval before the feature. That's called eval driven development. Um say you want your support agent to always check who the customer is before giving a refund. Uh you can write the eval that checks for that first and now done has a definition that you can measure a hill that you can climb from the start.

</details>

### 将评估集成进 CI：基于 Vitest 与 Phoenix 的工程实践

**演讲者**：嗯，我们前面已经深入讨论了能力评估（Capability Evals）和回归评估（Regression Evals）。嗯，接下来展示如何具体构建一个能够在 CI 环境中自动化执行的评估任务。嗯，如果你之前从未使用过 Vitest，Vitest 是一个现代 JavaScript 测试运行器，而 Phoenix 可以与其无缝直接集成。呃如果你打开 `agent.eval.ts` 源码文件，你会发现它看起来和普通的单元测试文件几乎一模一样，因为它本质上就是一个标准的测试文件。这里有一个 `describe` 测试块，并为我们回归测试集中的每一个查询用例都编写了一个独立的 `test`：包括可口可乐（Coca-Cola）、苹果对微软（Apple versus Microsoft）、Rivian，呃以及虚构的股票代码 ZZZQ。

<details>
<summary>Original English</summary>

**Speaker**: Um, we talked already about capability capability evals and regression evals. Um, here's how uh to create a eval that runs in CI. Um, if you've never used VEST, VEST is a JavaScript testr runner and Fenix can plug straight into it. Uh, if you open agent.eval.ts, you'll see that it looks like an ordinary test file because it is one. There is a describe block and a test for each query in our regression set. So Coca-Cola, Apple versus Microsoft, Rivian, uh, and the fake ZZZQ.

</details>

**演讲者**：嗯，每一个测试用例都会实际执行 Agent，将生成的分析报告记录为标准输出，呃随后在其上运行我们的全套评估流水线。这里复用的正是我们早先编写的同一个股票代码检查器（Ticker Check）和可操作性大模型裁判（Actionability Judge）。我们完全不需要为 CI 流水线额外编写新的评估逻辑。呃紧接着在测试文件的底部，我们根据验收标准（Acceptance Criteria）设置了构建门禁（Gate the build）。这就是我之前所提到的“防护栏”（Guardrails）与“北极星指标”（North Stars）的具体落地方式。

<details>
<summary>Original English</summary>

**Speaker**: Um, each test runs the agent, logs the report as the output, uh, and then runs our evals on it. And the same ticker check and actionability judge that we wrote earlier. We don't have to add new evals for CI. Uh, then at the bottom, we gate the build on acceptance criteria. This is where I talked about guardrails and northstars.

</details>

**演讲者**：“提及股票代码”（Mention ticker）是一项硬性防护栏——报告必须准确讨论目标公司的股票代码。“可操作性”（Actionability）则是一个北极星目标，其评测均值必须保持在 0.8 或更高水平。呃之所以这样设定，是因为单个大模型裁判在面对单份独立报告时可能会存在一定程度的打分噪声，因此我们基于整体批次的平均得分来设定门禁，呃而不是因单次波动就草率判断。呃设置完毕后，你只需要执行 `npm test`，它就会像任何标准的测试套件一样自动运行。嗯，在执行完毕后，测试报告器会完整打印出一份记分卡（Scorecard）。

<details>
<summary>Original English</summary>

**Speaker**: Mention sticker is a guardrail. It has to be talking about the right company. Um actionability is a target. The average has to stay 08 or better. Uh because an LLM judge can be a bit noisy on a single report. So we gate on the average uh not on just one. Uh and then you can run npm test uh and it runs like any test suite. Um and at the end the reporter prints out a scorecard.

</details>

### 构建门禁、排错与可解释性

**演讲者**：嗯，执行这套测试大约需要四分钟时间，这已经超出了我今天分享剩余的时间。嗯，如果构建失败——也就是出现了红色的构建失败状态（Red Build），你就会看到这样的界面反馈：全部四个测试用例都完整执行了，每份生成的报告也都正确提及了对应的股票代码，但 Rivian 的分析报告未达到可操作性标准。因此，整体可操作性平均分最终停留在 0.75。呃这并不是冰冷地宣告你彻底失败，而只是明确指出你偏离了既定指标。嗯，但相对地，呃一次全绿通过的运行（Green Run），呃则是所有这些指标全部顺利达标的状态。

<details>
<summary>Original English</summary>

**Speaker**: Um, and that'll take about four minutes, which is more time than I've got left. Um, a red build. If a failed build, if your build fails, this is what you'd get. All four tests ran and every report mentioned its ticker, but Rivian's report wasn't actionable. So, the actionability average came out at 75. Uh, it doesn't say you failed. It just says that you missed. Um, but, uh, a green run, uh, is where all of those pass.

</details>

**演讲者**：嗯，由于时间确实不够了，我在这里就不专门展示具体的实验对比视图（Experiment View）了。呃但极为关键的一点是：当持续集成构建失败时，你得到的绝不仅仅是一个毫无意义的红色叉号（Red Cross）。你将获得详尽的解释性诊断信息，清晰说明系统表现究竟是优是劣，以及出现偏差的具体根本原因。而这才是最具工程价值的核心所在。呃完全相同的这套测试套件可以直接放置在 GitHub Actions 中自动化运行。呃它会在后台拉起 Phoenix 作为服务容器（Service Container）。

<details>
<summary>Original English</summary>

**Speaker**: Um, I'm not going to show the experiment view because again, I'm running out of time. Uh, but when a build fails, you don't just get a red cross. You get an explanation that says whether things are good or bad and why they went wrong. And that is the important thing. Uh, this same test suite can be run in GitHub actions. Uh, it starts Phoenix as a service container.

</details>

### 全民评估与生产监控闭环

**演讲者**：呃现在，我此前向大家承诺的所有实践环节，我们都已经完整走过了一遍。呃你可以运行自己的评估集，可以全面测试各项能力，可以充分确保自动化评估结果与人类专家的真实判断高度契合，可以将评估无缝嵌入 CI 流程，并且能够严格保证代码构建门禁切实建立在大模型裁判对于“优质表现”这一编码化定义的判定之上。嗯，而且这其中有一个我极其推崇的优势：现在，任何真正懂得业务上什么是“好答案”的人，都能够参与到编写评估的工作中来。

<details>
<summary>Original English</summary>

**Speaker**: Uh, but now we've done everything that I've said that you can do. uh you can run your evals, you can test things, you can make sure uh that it matches your human judgment, you can put it into CI and you can make sure that your builds are gated on whether or not uh the LLM's judgment of what you've encoded as the definition of good uh really works. Um and there's something I love about this which is that anyone who knows what good looks like can write evals now.

</details>

**演讲者**：呃这包括你们的产品经理（Product Managers）、你们的客户支持团队（Support Team），以及在销售一线不断听到客户相同抱怨的销售同事。他们根本不需要懂怎么写 TypeScript 代码。呃他们只需要用自然语言清晰描述出优质的回答应当具备哪些具体特征，呃然后把这些规范提供给你，或者更棒的做法是——直接把描述交给一个代码生成 Agent（Coding Agent），由代码 Agent 自动为他们生成全部的自动化评测代码。

<details>
<summary>Original English</summary>

**Speaker**: uh your product managers, your support team, your person in sales who keeps hearing the same complaint. They don't need to write TypeScript. Uh they just need to describe what a good answer looks like uh and give it to you or even better just give it to a coding agent which will then write all of the evals for them.

</details>

**演讲者**：呃值得提醒的是，你们绝不应该在每一次 Git Commit 提交时都把整个复杂的 Agent 完整跑一遍，呃因为全量运行耗时极长，并且会消耗大量的 API 调用成本。嗯，但现在你们已经拿到了我承诺给各位的完整开源代码仓库。所有的核心代码都已经就绪，所有的实战示例也一应俱全。你们可以清晰看到每一个环节是如何具体落地的。呃你们可以直接将自己的 Coding Agent 指向该仓库并下达指令：“照着这个模式，为我自己的代码库实现一套”，呃你的智能体就能自动理解并完成搭建。

<details>
<summary>Original English</summary>

**Speaker**: Uh you shouldn't run your whole agent on every single commit because uh it's going to take a really long time and cost you a whole bunch of money. Um, but now you've got the repo I promised you. You've got all of the code. You've got all of the examples. You can see how everything is done. Uh, you can point your agent at it and say, "Do this, but for my codebase," uh, and your agent will figure it out.

</details>

**演讲者**：嗯，今天由于时间所限，确实还有一个关键模块我们没能亲手搭建，呃那就是：一旦系统正式上线生产，你必须坚持持续评估。你应当在真实的线上流量抽样样本上持续运行评估，呃并在评测指标下滑且持续低迷时及时触发告警。嗯，切记不要对每一次单一偶发的评测未达标都神经质地报警，因为单个失败往往只是不可控的噪声。嗯，但如果失败率呈现出明确的下滑趋势，呃生产环境下的持续监控就具有极其巨大的价值，而评估框架完全可以为你提供这种能力。

<details>
<summary>Original English</summary>

**Speaker**: Um, there is one thing that we didn't get time to build today, uh, which is, uh, once you're live, you should keep evaluating. You should run your evals on a sample of real traffic, uh, and alert when scores drop and stay down. um not on every single failure because one failure would be noise. Um but if you get a trend in failures, uh production monitoring is incredibly useful and eval can get you that as well.

</details>

### 从小处着手：构建完整的 AI 工程生命周期

**演讲者**：所以，这正是我们今天完整构建的闭环体系：我们追踪（Traced），我们研读（Read），我们评估（Evaluated），我们检验（Checked），我们改进（Improved），呃并且我们通过持续集成（CI）将这些工程成果牢牢锁定。呃但是，大家并不需要在下周一上班时就一口气把今天学到的所有东西全都硬塞进系统。你可以从小处着手、循序渐进。你可以先为你的 Agent 接入基础的追踪插桩（Instrumentation）。你可以仅仅花时间仔细阅读一些追踪链路。相信我，仅仅仔细研读 12 条完整的执行追踪记录，你所能收获的系统洞察，就远比光盯着最终输出结果所能看到的丰富得多。

<details>
<summary>Original English</summary>

**Speaker**: So this is the full cycle that we built. We traced, we read, we evaluated, we checked, we improved, uh and we locked it in with CI. Uh but you don't have to do all of the stuff that you've learned today on Monday. You can start small. You can just instrument your agent. you can just read some traces. You will get information reading 12 traces that you wouldn't have got uh by just looking at the output.

</details>

**演讲者**：嗯，所以尽管去跑一跑它们吧。认真观察运行结果，并在此坚实基础上逐步扩展构建。呃快去在你们自己的实际应用程序上亲手试一试吧。这正是包含所有内容的完整代码仓库。呃 Phoenix 的官方文档也已经附在其中。呃 Phoenix 本身也是完全开源的，所以大家完全可以深入探索其源码，或者在里面给我们指出任何潜在的问题或不足。呃卡着准点，我们今天的分享到这里就正式结束了。非常感谢各位！[掌声]

<details>
<summary>Original English</summary>

**Speaker**: Um so run them. Look at the results and build from there. Uh so go try it on a app of your own. This is the repo that I said that everything was in. Uh the Phoenix docs are there. Uh Phoenix itself is open source. So you can mess with the code and tell us that we got stuff wrong in there. Uh and that just on time is it. Thank you very much everybody. [applause]

</details>