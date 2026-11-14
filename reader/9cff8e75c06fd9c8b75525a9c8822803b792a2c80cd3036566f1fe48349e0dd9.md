---
author: AI Engineer
date: '2026-10-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=qZj7sqmidqA
speaker: AI Engineer
tags:
  - agent-evaluation
  - llm-as-a-judge
  - observability
  - continuous-improvement
  - software-development-lifecycle
title: AI Agent 评估实战：从链路追踪到自动化闭环迭代
summary: 本文介绍 AI Agent 评估的完整工作流，涵盖链路追踪、代码与 LLM 裁判评估、元评估及数据集实验。强调评估产出而非路径，利用编程智能体实现自动化改进，构建持续迭代的软件开发生命周期。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/12 -->

### 工作坊开场与讲师介绍

**Laurie Voss**: 大家好！在这场长达两小时的工作坊里，整个房间都坐满了人，这实在太棒了。欢迎来到 AI Engineer 大会！我知道大家可能已经听过正式的欢迎辞了，但还是要再次欢迎各位来到 AI Engineer。这个会场非常棒，今天来的人数也着实出乎我的意料。今天我为大家准备了非常充实的内容。我叫 Laurie Voss，目前在 Arize AI 担任开发者关系负责人（Head of Developer Relations）。

<details>
<summary>Original English</summary>

**Laurie Voss**: Hello, everyone. I have a packed room for a two-hour workshop, which is amazing. Welcome to AI Engineer. I know it's officially welcomed, but welcome to AI Engineer. This venue is amazing. This crowd is really quite surprising, and I have a ton of content for you today. My name is Laurie Voss. I am Head of Developer Relations at Arize AI.

</details>

**Laurie Voss**: 你们中的一些人可能还记得我以前联合创立 npm（npm, Inc.）的经历，所以你们可能会从以前 JavaScript 的时代认出我。不过最近这些年，我主要专注于探讨人工智能、如何对 AI 进行测试，以及如何让它稳定可靠地工作。那么，我们今天究竟要讲些什么内容呢？

<details>
<summary>Original English</summary>

**Laurie Voss**: Some of you may remember me from when I used to co-found npm, Inc., so you may remember me from like JavaScript days. But these days, I talk about AI and how to test it, and how to make it work. So what are we going to be covering today?

</details>

### 今日议程：从基础评估到 Agent 闭环迭代

**Laurie Voss**: 我们今天有相当充裕的一段时间在一起，因此我们会涵盖非常多的领域。我会先从基础知识讲起，这也是为什么本次分享被称为 101 入门课的原因。我们将明确什么是评估（Evals）、为什么你需要它们，以及为什么与单一的大语言模型（LLM）应用相比，Agent 会让评估变得更加困难。接下来，我们会在 Arize 中配置链路追踪（Tracing）。Arize AX 是你捕获后续运行评估所需原始数据的基础平台。

<details>
<summary>Original English</summary>

**Laurie Voss**: We've got a really good stretch of time together, so we're going to cover a lot of ground, and I'm going to start with fundamentals. That's why this is called the 101 session. We're going to say what evals are, why you need them, and why agents make evaluation harder than simple LLM applications. Then we're going to set up tracing in Arize. Arize AX is how you capture the raw data you need to run evals in the first place.

</details>

**Laurie Voss**: 我们会使用 Claude Agent SDK 构建一个简单的 AI Agent，运行它，并深入查看它所生成的 Trace 链路追踪数据。现场已经构建过 Agent 的朋友可以举个手吗？很好，看来不少人都做过。那我今天就完全不需要花时间去讲 Agent 本身是如何工作的了，因为我假设大家都已经清楚 Agent 的运作机制，大家今天来到这里是为了学习如何对它们进行评估。一旦我们获取到了一些数据，接下来就要做一件许多教程都会直接略过的事情——那就是真正去审视这些数据。我们会去仔细阅读这些 Trace，对出错的情况进行归类，并在写下任何一行评估代码之前，先理清究竟该测量什么指标。

<details>
<summary>Original English</summary>

**Laurie Voss**: We're going to build a simple AI agent with the Claude Agent SDK, we're going to run it, and we're going to look at the traces it produces. Can I get a show of hands if you've already built an agent? All right, great. I'm going to spend no time at all on how the agent works, because I assume everybody knows how an agent works, and you're here to learn how to evaluate them. Once we've got some data, we're going to do something that a lot of tutorials skip, which is we're going to actually look at the data. We're going to read our traces. We're going to categorize what went wrong, and we're going to figure out what to measure before we write a single eval.

</details>

**Laurie Voss**: 然后，我们将编写三种不同类型的评估。首先是代码评估（Code Evals），它们是简单的确定性检查，非常类似于传统单元测试。接着，我们将使用内置的 LLM 评估指标，比如忠实度（Faithfulness），也就是让第二个 LLM 来作为裁判评判第一个模型的输出。此外，我们还会从零开始构建一个自定义的 LLM-as-a-judge 评估器。同时，我们还会测试这些大模型裁判本身的评判是否客观准确，这个过程被称为元评估（Meta-evaluation）。最后，我们将结合数据集和实验来进行收尾，这就是你在实践中如何对 Agent 进行迭代并切实衡量它是否有所提升的方法；其中我们还会演示如何利用 Claude Code，根据评估反馈自动改进我们的应用程序。

<details>
<summary>Original English</summary>

**Laurie Voss**: Then we're going to write three kinds of evals. There are code evals, which are simple deterministic checks, very similar to unit tests. Then we're going to use built-in LLM evals like faithfulness, where a second LLM judges the output of your first one, and we're going to do a custom eval—LLM as a judge from scratch. And we're also going to test whether our judges are judging correctly, a process called meta-evaluation. Then we're going to finish with datasets and experiments, which is how you iterate on your agent and actually measure whether it's getting better, including we're going to use Claude Code to automatically improve our app in response to feedback from our evals.

</details>

### 环境准备：Notebook 与 API 密钥

**Laurie Voss**: 首先，第一件事是获取你的 Notebook。我之前设置时出了点纰漏，权限没配对；如果你刚才扫码打不开，现在已经修复了，大家可以正常访问。请拿到这份 Notebook 并在你自己的环境中保存一份副本，我们今天一整天的操作都会在这份 Notebook 里进行。我会在这里稍等大家一会儿把 Notebook 复制好，否则我后面还得不断把幻灯片切回到这一页。

<details>
<summary>Original English</summary>

**Laurie Voss**: So first things first, get your notebook. I messed up earlier and didn't have permissions set correctly. So if you scanned this earlier and it didn't work, it works now. Grab this notebook and make a copy for yourself. That is where we're going to be living all day, and I'm going to wait for that to happen because otherwise I'm going to have to keep swapping back to this slide.

</details>

**Laurie Voss**: 好，大部分人都弄好了吗？还没，我看到还有人在拍照。好的，没问题。我们今天还需要一些 AI 基础设施支持。我今天演示时会使用 Anthropic 和 Claude Code。不过 Arize AX 同样适用于 OpenAI 以及市面上所有其他的 LLM 供应商，只是为了方便进行工作坊教学，我必须挑一个来展开，所以我选择了 Claude。因此，这份 Notebook 需要大家提供一个 Anthropic API Key，你可以从 console.anthropic.com 获取；如果你足够熟练，也可以自己快速切换到 OpenAI。

<details>
<summary>Original English</summary>

**Laurie Voss**: All right, most of those down? No, no, I'm still seeing people taking pictures. All right, cool. We're also going to need a certain amount of AI infrastructure. I'm going to be using Anthropic and Claude Code today. Arize AX works with OpenAI, works with every other LLM provider, but I had to pick one in order to do a workshop about it, so I have used Claude. So this notebook is going to expect you to have an Anthropic API key, which you can get from console.anthropic.com. If not, you can, if you are very clever, do a fast swap to OpenAI.

</details>

**Laurie Voss**: 另外，大家还需要一个 Arize 账号。请访问 arize.com 注册免费试用版。注册完成后，你需要获取一个 Arize Space ID 和一个 Arize API Key，这两个都可以在设置页面中找到。站在会场角落的那位是我非常出色的助手 Ant Datis。如果大家在获取 API 密钥或者任何配置上遇到麻烦，直接向他招手示意，他会马上跑过去帮大家解决，他真是太热心了。谢谢你，Ant！

<details>
<summary>Original English</summary>

**Laurie Voss**: You're also going to need an Arize account. Go to arize.com and start a free trial. From there, you will need an Arize Space ID and an Arize API key, both of which you can get from the settings page. My lovely assistant, Ant Datis, that's him in the corner. If you run into any problems getting your API keys or anything like that, just flag him down and he will run over to you and help you figure it out, which is incredibly nice of him. Thank you, Ant.

</details>

### 账号注册与 Arize AX 平台定位

**Laurie Voss**: 好的，有谁已经把这些都准备齐全了吗？有谁已经注册好 Arize AX 账号了？好的，我会留出一些时间让大家把账号和配置先弄好。具体操作是访问 arize.com……哎呀，它直接把我跳到了文档页面，因为我平时总是在看文档。访问 arize.com 之后，点击那个醒目的粉色“Get Started”按钮。大家请直接从这里注册，千万不要不小心注册成了 Phoenix。Phoenix 是我们非常优秀的开源项目，在 Phoenix 之下也提供托管服务。有时在 Google 上搜索 Arize 时，可能会被引导到 Phoenix 页面。请注意，今天不要注册 Phoenix，我们今天要使用的是 Arize AX。

<details>
<summary>Original English</summary>

**Laurie Voss**: Yes, so who had all that stuff already? Anybody already gotten an Arize AX account? All right. I'm going to let you set that one up for a little while. The way you do it is you go to arize.com and you hit—oops, it sent me to the docs because I always live in the docs. You go to arize.com, thank you, and you hit the big pink "Get Started" button. And then you sign up from here. Do not accidentally sign up Phoenix. Phoenix is our lovely open source project, which also has a hosted service underneath Phoenix. Sometimes when you Google Arize, you get sent to Phoenix instead. Don't sign up Phoenix. You are doing AX today.

</details>

**Speaker 0**: 没问题。

<details>
<summary>Original English</summary>

**Speaker 0**: All right.

</details>

**Laurie Voss**: 趁着大家注册账号的时间，我再多介绍一下 AX 究竟是什么。它是一个面向 AI 应用的可观测性与评估平台（Observability and Evaluations Platform）。它能够捕获你的 AI 应用运行时的 Trace 链路追踪数据，存储并运行你的各项评估，同时在生产环境中持续监控你的应用，一旦发生异常就会发出告警。默认情况下，我们为用户提供云端托管服务，这也是我们今天选用它的原因——你不需要自己部署和运行任何复杂的底层软件，没有运维基础设施的负担。当然，如果你们企业对数据隐私极其敏感，坚决要求本地自建，你也完全可以自行部署运行。

<details>
<summary>Original English</summary>

**Laurie Voss**: While you are signing up, I'm going to say a little bit more about what AX is. It is an observability and evaluations platform. It captures traces from your AI application, it stores and runs your evaluations, and it watches your app in production and alerts you when something goes wrong. By default, we host it for you. That is why we're using it today, because you don't have to like run some software to make it run. So there's no infrastructure to manage, though if you are from an enterprise that is super precious about your data and you're like, "No, we need to run it ourselves," you can absolutely do that if you want to.

</details>

**Laurie Voss**: 正如我刚才所提到的，如果你以前使用过我们的开源工具 Arize Phoenix，你会发现很多概念都是相通的。它们拥有相同的核心理念，区别在于一个专注于开源的易用性与灵活性，而另一个则是专为企业级生产环境、团队协作等场景深度打造的。大家目前申请密钥的进度怎么样了？现场的 Wi-Fi 实在有点慢，这其实也在意料之中对吧？现场有没有人现在迫切需要技术协助？好的，建议大家可以直接切换成手机热点。对于现场 Wi-Fi 的状况我深表歉意。我其实特别担心今天下午两点的那场工作坊，因为那个 Git 仓库有足足 200MB，我真担心大家因为网速太慢连代码库都拉不下来。好的，大家现在可以先克隆起来了。

<details>
<summary>Original English</summary>

**Laurie Voss**: And like I said, if you've used Arize Phoenix, which is our open source tool, a lot of this will feel familiar. They have the same core ideas. One is built for open source accessibility, and the other one is built for enterprise with production and teams and things like that. So how are we doing on signing up for keys right now? The Wi-Fi sucks, that is predictable really, isn't it? All right, is anybody desperately in need of assistance right now? All right, okay. Well, the advice is to switch your phones as a hotspot. I apologize for the Wi-Fi. I'm really worried about my 2:00 PM workshop, where I have a Git repo that I know is 200 megabytes large, and I'm like no one is going to get the repo because it's too big. Yeah. Yes, start cloning that repo now.

</details>

### 核心心智模型：Evals 是测试，Traces 是日志

**Laurie Voss**: 闲话少叙，我们先来聊聊这些核心基础概念。本次工作坊包含相当一部分理论内容，这也正好给大家留出赶上环境进度的缓冲时间。这里有一个核心的心智模型：Evals（评估）相当于 AI 世界里的软件测试，而 Traces（链路追踪）就是 AI 世界里的日志记录。至于为什么我们非得给这两样东西发明两个完全陌生的新名词，我其实也不是很理解。在传统开发中，你写测试的逻辑是：给定这个输入，我期望得到特定的输出；Evals 做的事情完全一样，只不过针对的是 AI 的输出——因为 AI 的输出从来不会出现两次完全一模一样的情况。

<details>
<summary>Original English</summary>

**Laurie Voss**: Anyway, let's talk about these fundamentals. There's a lot of theory in this workshop, which gives you time to catch up. Here is the mental model: Evals are testing for AI, and traces are logs for AI. Why we had to come up with two completely new names for those things, I don't really know. You write tests for your code: given this input, I expect this output. Evals do the same thing, but for AI outputs where the outputs are never exactly the same twice.

</details>

**Laurie Voss**: 就像传统日志会记录你的服务器在运行时所执行的操作一样，Traces 记录的是你的 AI 实际做了什么。这意味着它会记录每一次 Agent 调用、每一次 Tool 工具调用、每一次 LLM 调用的具体过程，包括在每一步当中的输入和输出。构成 Trace 的基本构建块被称为 Span。从屏幕上的这张截图中，你可以看到 Arize AX 中的一条 Trace。它由一堆 Span 组成，整体呈现树状层级结构；每个 Span 都代表执行过程中的某一个单一步骤。一次 LLM 调用是一个 Span；一次工具调用是一个 Span；整个 Agent 回合（Turn）也是一个 Span，并且其内部可以嵌套包含其他的子 Span。

<details>
<summary>Original English</summary>

**Laurie Voss**: Just as logs record what your server did at runtime, traces record what your AI did. So every agent call, every tool call, every LLM invocation with the inputs and outputs at each step. The building blocks of a trace are called spans. In this screenshot, you can see a trace in Arize AX. It's made up of a bunch of spans. It's got a tree structure, and each span represents one step in the execution. An LLM call is a span. A tool call is a span. A full agent turn is a span that contains other spans inside of it.

</details>

**Laurie Voss**: 每个 Span 都会详尽记录它的输入、输出、耗时、Token 消耗量以及大量的元数据——包含了解该步骤中所发生的一切所需的所有信息。简而言之：Traces 告诉你究竟发生了什么，而 Evals 告诉你结果到底好不好。这就是我们今天需要建立的核心心智模型。

<details>
<summary>Original English</summary>

**Laurie Voss**: Each span records its input, its output, timing, token counts, and a whole bunch of metadata—everything that you need to understand what happened at that step. Traces tell you what happened; evals tell you whether it was any good. That is the mental model for today.

</details>

### “凭感觉开发”的困境与评估的必要性

**Laurie Voss**: 这其实并不是什么高深莫测的火箭科学。但接下来我想谈谈为什么我们从一开始就极其需要 Evals，这就是所谓的“凭感觉驱动（Vibes-based）”所带来的隐患。现阶段 AI 功能的发布流程通常是这样的：团队构建好某项 AI 功能，随手跑几个 Query 查询，看看结果然后问：“这看起来对吗？嗯，看着挺不错的。”紧接着就直接发布上线了。这是目前构建和发布 AI 应用时最普遍的做法。而这种方式的致命问题在于：一旦遇到那些你没测试过的输入，系统就会当场崩溃。

<details>
<summary>Original English</summary>

**Laurie Voss**: This is not rocket science, but let me talk about why we even need evals, and that is the "vibes" problem. AI features usually get shipped by building an AI feature, running a few queries, saying, "Does this look right? Yeah, it looks good," and then you ship it. That is by far the most popular method of shipping AI applications today. And the problem is that then it fails on inputs that you didn't test.

</details>

**Laurie Voss**: 问题在于，在你随手测试的那几个 Query 上，它可能确实表现不错；但现实是，你仅仅手动跑了三次测试，跑三次根本算不上什么测试套件。解决软件不稳定的常规手段是编写单元测试，但在 AI 场景下单元测试却失效了——因为大模型的输出具有非确定性（Non-deterministic）。哪怕是完全相同的 Prompt，每次运行生成的文本也大相径庭，这意味着两个完全不同的回答可能都是正确的，你根本没有一个固定的预期字符串能用来做断言校验。因此，许多团队只能退而求其次依赖人工审查：人肉盯着它跑，感觉没问题就上线发布。但这种方式根本无法扩展，无法拦截回归缺陷，而且最关键的是，它根本无法集成到 CI 持续集成流程中自动运行。

<details>
<summary>Original English</summary>

**Laurie Voss**: And the thing is, it probably looks good on your test queries. But the problem is, you ran it three times; three times is not a test suite. The usual fix for flaky software is unit tests, and they don't work here because the output is non-deterministic. The same prompt produces different text every run. So two different responses might both be correct. So there's no expected string that you can assert against. So teams fall back on human review. They watch it run, it looks fine and ship it. That doesn't scale. It doesn't catch regressions. And most importantly, it doesn't run in CI.

</details>

**Laurie Voss**: 这里列举一些如果没有 Evals 你就根本无法做到的事情。例如，当你修改了 System Prompt 以修复某种语气（Tone）上的瑕疵时，表面上看语气确实改善了，但你的 Bot 却可能在暗中开始幻觉出各种不存在的产品功能。如果没有可靠的评估机制，你根本察觉不到这种退化，直到真实用户踩坑投诉；而如果配置了忠实度评估（Faithfulness Eval），你就能在功能发布之前精准捕捉到这类幻觉指标的剧烈异常。毕竟，对 Prompt 的每一次微调，都有可能波及用户输入的各种边界情况。

<details>
<summary>Original English</summary>

**Laurie Voss**: Here's some things you can't do without evals. If you change your system prompt to fix a tone issue, the tone one would get better. But now your bot is hallucinating product features. Without evals, you wouldn't catch that until a user reported it. With a faithfulness eval, you would have seen the spike before it shipped. And every prompt potentially affects every kind of input that users send.

</details>

<!-- chunk 2/12 -->

### 为什么不能单靠人工测试：评估（Evals）的作用

**Speaker 1**: 你可能只是为了某个局部需求去修改 Prompt，结果却在应用程序完全不同的另一个地方引发了完全意想不到的连锁反应。这是因为发送给 AI 的 Prompt 本质上就是一大块文本。你根本不可能手动测试所有的输入组合。

<details>
<summary>Original English</summary>

**Speaker 1**: so you can be changing the prompt for one thing and have a completely unexpected effect at some totally different part of your application because the prompt is just a huge block of text that you're sending to your ai. You can't manually test every combination.

</details>

**Speaker 1**: 所以如果没有评估系统（Evals），你就是在玩打地鼠的游戏：修好了一个问题，又在其他地方搞坏了别的东西。而 Evals 能为你提供一个具体的数值，让你能够追踪、比较并据此采取行动。

<details>
<summary>Original English</summary>

**Speaker 1**: so without evals, you're playing whack-a-mole, you fix one problem and you break something somewhere else. Evals instead give you a number that you can track and compare and act on.

</details>

**Speaker 1**: 此外，没有评估系统你也无法随意切换模型。这一点变得越来越重要，因为这个领域的发展速度太快了，每隔几个月就会有新模型发布。如果没有评估体系，切换模型就意味着长达数周的手工测试。新模型到底变好了还是变差了？有什么东西漏掉了吗？有什么功能损坏了吗？你根本无法确定。而有了评估系统，你只需要跑一遍测试套件，对比分数，几个小时内就能得出结论。这就是“凭感觉盲开”与“靠仪表盘飞行”之间的本质区别。

<details>
<summary>Original English</summary>

**Speaker 1**: you also can't switch models without evals. and this matters more and more, because this field moves so fast new models drop every few months. without evals switching models means weeks of manual testing. is it better? is it worse? did something get—did something break? you don't know. with evals, you run the suite, you compare the scores, and you know, within hours. and that is the difference between flying by the seat of your pants and flying by instruments.

</details>

**Speaker 1**: 这绝不是纸上谈兵。真实团队——比如 Descript、Bolt 以及 Anthropic 自己的 Claude Code——都遵循了同样的演进轨迹：起初全凭直觉和体感交付（shipping on vibes），随后发现这种凭感觉的方式根本无法规模化，最终不得不搭建起严谨的评估系统。这也是我们在今天的工坊中要一起实践的演进过程。

<details>
<summary>Original English</summary>

**Speaker 1**: and this is not theoretical. real teams, Descript, Bolt, and Anthropic's own Claude Code, all follow the same arc of shipping on vibes and then discovering that vibes don't scale and then building evals. and that is the same arc that we're going to follow in today's workshop.

</details>

### 代码评估与 LLM 裁判评估：特性与权衡

**Speaker 1**: 正如我之前提到的，评估大体上可以分为两大类型。第一类是代码评估（Code Evals），它们是确定性的函数。它们的执行时间只有几毫秒，几乎没有任何调用成本，并且能给出即时、明确无误的答案。例如：输出能否成功解析为 JSON？输出的 Token 数量是否少于 500 个？它是否提及了我要求的内容？代码评估的最大优势在于快速、低廉且完全可复现。面对相同的输入，它们每一次都会给出完全相同的结果，这与传统的单元测试非常相似。

<details>
<summary>Original English</summary>

**Speaker 1**: as i mentioned earlier, there are two broad types of evals. code evals are deterministic functions. they run in milliseconds and they cost nothing. and they give you an immediate unambiguous answer, like, did the output parse as JSON? is the output less than 500 tokens? did it mention the thing that i asked about? the big advantage of code evals is that they are fast and cheap and totally reproducible. they get the same input, and they give the same answer every time. that makes them very similar to old style unit tests.

</details>

**Speaker 1**: 但缺点也和传统的单元测试一样：它们可能非常脆弱。我们有一些策略可以帮助规避这种脆弱性，我稍后会详细介绍。因为对于同一个问题，完全正确的答案可能会用截然不同的措辞来表达，你必须调整对单元测试的预期，才能应对这种情况。

<details>
<summary>Original English</summary>

**Speaker 1**: the downside is that like old style unit tests, they can be brittle. we have some strategies that can help avoid that. and i'm going to be covering those later. because two perfectly correct answers might be worded completely differently, and you have to adjust your expectations of unit tests to be able to handle that.

</details>

**Speaker 1**: 第二种评估方式是 LLM 即裁判评估（LLM-as-a-judge Eval）。这种方法使用第二个大语言模型，依据特定的评分规则（Rubric）来对你的输出进行打分。“Rubric”其实就是我们造的另一个词，它的本质含义就是规则。它是你在 Prompt 中规定的一整套用于判断结果好坏的标准。LLM 评估要灵活得多，它们能够处理那些代码评估无法解答的问题：这个回答在事实上准确吗？它是否忠实于原始参考材料？其语气风格是否符合客户服务场景的要求？LLM 裁判的核心优势在于它们理解语义，而不仅仅是匹配输出中的特定字符串。

<details>
<summary>Original English</summary>

**Speaker 1**: the second type of eval is an LLM as a judge eval. these use a second LLM to grade your outputs against a rubric—rubric being yet another word that we made up, that just means rules. it is your set of rules that you put in your prompts about what counts as good. LLM evals are much more flexible. they can handle the kinds of questions that code evals can't answer: is this response factually accurate? did it stay faithful to the source material? is the tone right for a customer service context? the strength of LLM judges is that they understand meaning, not just the strings that are in your output.

</details>

**Speaker 1**: 但 LLM 裁判也有其取舍。它的短板在于运行是需要成本的，而且它们本身具有非确定性。也就是说，它们同样可能犯错，这意味着你必须对照人类专家的判断来对它们进行校准。我们今天晚些时候就会做这项校准工作。

<details>
<summary>Original English</summary>

**Speaker 1**: but LLM judges have trade-offs. the weakness is that they cost money to run, and they are non-deterministic themselves. so they can be wrong, which means that you need to calibrate them against human judgment. and we're going to do that later today.

</details>

**Speaker 1**: 此外还有第三种评估方式：人工评估（Human Evaluation）。由领域专家直接阅读并为你系统的输出打分。这是质量评判的黄金标准，但它的缺点是速度慢且成本高昂。而且人是会感到疲劳的，这就是为什么我们不能时时刻刻都依赖人工评审。这里有一个不太令人愉快的事实：人工标注员由于疲劳，漏检的缺陷率最高可达 50%。所以人类也并非完美无缺。因此，当你构建了一个 LLM 裁判并抱怨“它并没有帮我抓住所有的错误”时，请记住，即便换成人类来评审，人类同样无法抓住每一个错误。这些方法实际上是互补的。绝大多数真实的生产级应用都会综合使用代码评估、LLM 裁判和人工评估的组合拳。

<details>
<summary>Original English</summary>

**Speaker 1**: there's also a third type of eval: human evaluation. a domain expert can read your output and grade it. that is the gold standard of quality, but it is slow and expensive. and humans get tired, which is why we can't use it all the time. fun fact, that's not very fun: human annotators miss up to 50% of defects due to fatigue. so they're not perfect either. so when you build an LLM as a judge and you're like, well, it doesn't always catch my errors, remember that if you were judging with humans, the humans would also not always catch your errors. but these are complementary approaches. most real applications are going to use a collection of code evals, LLM as a judge, and human evaluation.

</details>

**Speaker 1**: 那么，什么时候该用哪种评估呢？当答案本身是确定性的时候，使用代码评估：比如格式校验、长度限制、违禁词检测、必填字段检查等。当你需要语义理解时，使用 LLM 裁判：准确性评估（Correctness Eval）关注的是“它是否准确回答了问题”，忠实度评估（Faithfulness Eval）关注的是“它是否严格遵循了源文档且没有产生幻觉”。至于人类评估，你应该将其保留在处理从未见过的新型故障模式上，以及用于验证你的 LLM 裁判打分是否确实正确。LLM 裁判也有可能出错，拿人类专家的判断与其比对，正是检验你是否可以信任它们的关键途径。

<details>
<summary>Original English</summary>

**Speaker 1**: so when do you use which? use code evals when the answer is deterministic: so format validation, length limits, forbidden phrases, required fields. use LLM judges when you need semantic understanding. a correctness eval asks, did it answer the question accurately? a faithfulness eval asks, did it stick to the source documents without hallucinating? and you should keep humans in the loop for failure modes that you haven't seen before, and to verify that your LLM judges are actually judging correctly. LLM judges can be wrong; judging them against human judgment is how you know whether or not you can trust them.

</details>

### Agent 系统带来的阶梯式复杂度与级联故障

**Speaker 1**: 上述原则适用于任何使用大模型的常规应用。但对于 Agent（智能体）而言，情况在某些方面变得更加棘手，这非常值得单独提出来强调。你可以把它想象成一个复杂度的阶梯。单次 LLM 调用相对简单：你给一个输入，它给一个输出。但当我们谈论 Agent 时，一个 Agent 会进行一系列的工具调用并做出连贯的决策，这意味着在调用链的每一个步骤中，犯错的几率都在层层递增，导致它偏离既定轨道（脱轨）的可能性也随之越来越大。

<details>
<summary>Original English</summary>

**Speaker 1**: all of that is true of any application that uses LLMs. but agents make things even harder in some ways that are worth calling out. you can think of it as a ladder of complexity. a single LLM call is relatively simple: you get an input, you get an output. when you're talking about an agent, an agent is making a series of tool calls and a series of decisions, which means that at every single step in the chain, the chances that it has made a mistake are getting higher. and so the chances that it will go off the rails are going to get greater.

</details>

**Speaker 1**: 因此，你必须对中间步骤同样进行评估与评判。你需要检查你的 Agent 是否使用了正确的工具？传递的参数是否正确？它是否清楚何时该停止执行？陷入死循环对于 Agent 来说是一个非常真实的典型故障案例。而如果你在构建多 Agent 系统，则会再叠加一层复杂度：它们涉及到任务交接（Handoffs），一个 Agent 决定将工作转交给另一个 Agent。分流 Agent（Triage Agent）的路由是否准确？专门领域的 Agent 是否平稳承接了这次交接？系统中的每一层都会引入新的出错可能，加上非确定性的存在，意味着你需要引入更多的评估，因为错误是会发生级联放大的。

<details>
<summary>Original English</summary>

**Speaker 1**: so you have to judge the intermediate steps as well. you have to check whether your agent is using the right tool, did it pass the right arguments, did it know when to stop? getting stuck in loops is a real failure case for agents. and then multi-agent systems, if you are building those, add yet another level of complexity: they add handoffs, one agent decides to pass work to another. did the triage agent route correctly? did the specialist agent handle the handoff gracefully? each layer adds new ways that things go wrong, and non-determinism means that you need to have more evals, because errors can cascade.

</details>

**Speaker 1**: 级联故障的一个典型例子是这样的：如果你输入了一个关于“Tesla”（特斯拉）的查询，本意指的是那家汽车公司；你的 Agent 执行了网络搜索，却搜到了一大堆关于 18 世纪发明家尼古拉·特斯拉的信息；Agent 把这些信息汇总起来，撰写了一份关于 18 世纪发明家的格式精美、排版完善的报告，并将其呈交给了你的老板。从执行步骤上看，它做的事情没有一步是直接报错的：你让它在网上搜 Tesla，它搜了 Tesla；它拿到了 Tesla 的资料，并据此写成了报告。可是究竟哪里出错了呢？这种情况比显式的报错更严重，因为你必须人工审查输入和输出才能发现问题，没有任何传统的单元测试能够捕获这种语义级偏差。

<details>
<summary>Original English</summary>

**Speaker 1**: here's what an example of a cascading failure looks like: if you ask a query about Tesla, meaning the car company, your agent searches the web, finds a whole bunch of information about an 18th-century inventor, passes that back to your agent, which writes a beautiful, well-formatted report about an 18th-century inventor and passes that to your boss. nothing that it did there was wrong: you told it to search the web for Tesla, it searched the web for Tesla, it got information about Tesla, it wrote a report about Tesla. where did it go wrong? this is worse than an obvious failure because you have to be reading your inputs and outputs for that to work. there was no unit test that would have caught that.

</details>

**Speaker 1**: 但 Agent 也可能走向另一个极端：它们可能会以一种超出测试预期的方式把事情办成了，结果却被判定为不合格。这种情况曾经发生在 Anthropic 运行 TAU-bench 基准测试的时候，该基准测试用于模拟多轮客户服务任务。测试中他们要求 Agent 帮忙改签航班，并要求它做一件他们认为不可能办到的事——改签经济舱机票。然而事实证明，他们提供给 Agent 的政策规则允许 Agent 先将该机票升级为头等舱，而头等舱机票是可以改签的，经济舱则不行。于是 Agent 另辟蹊径找到了改签经济舱的方法，但却在测试中被判为失败，因为测试原本预设它应该“无法做到”。但事实上它成功做到了。这个例子说明了灵活的 Agent 能够找到你意想不到的路径，而这种特性必须在你的测试体系中得到妥善考虑。“创造性地做对”与“真正做错”之间有着本质区别。稍后在讨论为 Agent 或为评估系统打分时，我们还会回到这个话题。

<details>
<summary>Original English</summary>

**Speaker 1**: but agents can also do the opposite: they can get things right in a way that your tests weren't expecting and get graded wrong as a result. this happened to Anthropic when they ran a benchmark TAU-bench, which simulates multi-turn customer service tasks. they asked the agent to book flights and asked it to do something that they thought was impossible, which was reschedule an economy class flight. but it turned out the policies that they gave the agent allowed the agent to first upgrade the flight to first class; first class flights can be rescheduled, which economy flights cannot. so the agent found a way to reschedule the economy flight and failed the test because it was supposed to be not able to do that, and it was able to do that. so this is an example of how flexible agents finding things that you didn't think of needs to be accounted for in your tests. there is a difference between being creatively correct and wrong. and we're going to come back to that when we talk about grading your agents later, or rather grading your evals.

</details>

### 能力评估与回归评估，以及裁判的解释反馈

**Speaker 1**: 评估还可以从另一个维度划分为两类：能力评估（Capability Evals）与回归评估（Regression Evals）。能力评估关注的是“Agent 究竟能不能完成这件事？”通常情况下，能力评估绝大多数时候预期是失败的，Agent 在这些项上的得分通常非常低，因为它们为你设立了一座待攀登的高峰，为你的 Agent 提供了努力迭代提升的目标。一旦你翻过了这座山峰，原本的能力评估就会转化为回归评估。回归评估是你期望 Agent 每次都能完全通过（或接近完全通过）的评估项。因此，随着 Agent 的不断成熟，你会持续向它提出一个个能力评估，并逐步将它们转化为你日常频繁运行的回归测试套件，以确保原有的功能与表现没有发生倒退。

<details>
<summary>Original English</summary>

**Speaker 1**: there's also a second way of categorizing your evals into two categories, which is capability evals and regression evals. a capability eval asks, can the agent do this thing at all? capability evals are expected to mostly fail; the agent is expected to get a very low score on them because they give you a hill to climb. it gives you something for your agent to try and get better at. once you've climbed that hill, your capability eval turns into a regression eval. a regression eval is an eval that you expect your agent to pass completely or nearly completely every single time. so as your agent matures, you'll be giving it capability eval after capability eval and slowly turning them into a suite of regression evals that you run all the time to make sure that previous behavior has not regressed.

</details>

**Speaker 1**: 这就是一个典型的评估结果形态。每一项评估都会生成一个得分和一个标签。在这种情况下，数值得分通常只是 0 或 1，这种二元打分对于大语言模型来说非常容易执行。同时它还会附带一个人类可读的标签，例如“正确 / 错误”或“有效 / 无效”。而 LLM 裁判还增加了第三项内容：解释说明（Explanation）。纯代码评估不会生成解释，因为它们只是冰冷的代码逻辑；而 LLM 裁判不仅能指出某个结果是错的，还会详细说明它判定其正确或错误的具体原因。

<details>
<summary>Original English</summary>

**Speaker 1**: this is what an eval result looks like: every eval produces a score and a label. in this case, a numeric score, often just 0 or 1—binary scores are very easy for LLMs to do—and it comes with a human-readable label like correct or incorrect, or valid or invalid. LLM judges add a third thing, which is the explanation. code evals don't produce explanations because they are just code, but an LLM as a judge will say not just that something is incorrect, but it will say why it decided that something is correct or incorrect.

</details>

**Speaker 1**: 这具有极其巨大的价值。因为在当今由 Coding Agent 主导的环境中，你可以把一批评估中收集到的大量解释原因打包反馈给你的编程智能体，告诉它：“这是你在上次测试中搞砸的所有原因，你能做些什么来改进这一点？”你的编程智能体就会心领神会：“太棒了，感谢你的反馈，我会去改进你的应用程序”，并在下一次测试中表现得更好。这就是我今天要在工坊中向大家展示的内容：如何把一次失败的评估转化为对 Prompt 的精准改进。下面就是一个真实的裁判解释示例。在这个例子中，测试对象是一个旅行规划 Agent……

<details>
<summary>Original English</summary>

**Speaker 1**: and this is incredibly valuable, because if you are living in a world of coding agents, you can take a whole bunch of explanations from a bunch of evals and pass them back to your coding agent and say, here are all the reasons that you messed up in the last test, what could you do that would make you better at this? and your coding agent will just go, cool, thank you for the feedback, improve your application, and it will get better at it next time. this is something i'm going to show you in today's workshop: it is how you turn a failing eval into a prompt improvement. this is a real judge explanation in this example. it's a travel planning agent...

</details>

<!-- chunk 3/12 -->

### 评测解释的作用与错误归类（Coding）

**Speaker 1**: 假设你正在运行一个正确性评测（correctness eval）。评测模型（Judge）并不仅仅是判定“回答错误”，它会准确告诉你具体遗漏了什么。例如，用户要求推荐经济型航班，但模型没有给出预算明细；或者评测指出 Agent 提供了目的地信息和推荐，但用户询问的是廉价旅行，结果却没有包含任何费用估算。这种解释使评测具备了可操作性，因为你现在掌握了一个具体的失败案例，明确知道需要在 Prompt 中修复什么。正是这种解释，让评测从单纯的分数榜变成了真正实用的调试工具。

<details>
<summary>Original English</summary>

**Speaker 1**: And you're running a correctness eval. The judge doesn't just say incorrect. It tells you exactly what's missing. You asked for a budget flight and it didn't give a budget breakdown. It says the agent provided destination info and recommendations, but the user asked about budget travel, and there were no cost estimates. That explanation makes the eval actionable because you now have a concrete failure. You know what to fix in the prompts. And the explanation is what makes evals into a useful debugging tool, and not just a scoreboard.

</details>

**Speaker 1**: 如果你在 50 个不同的 Trace（调用追踪）中都看到了相同的解释，你就知道这是一个系统性问题，而不是偶然的边缘情况（edge case），这也就意味着它是你最应该优先修复的内容。因此，你需要提取这些评测解释，将它们归类为不同的失败类型，并统计各分类的数量。这被称为“打标签/编码”（Coding）。同样，我们可以从机器学习领域借用术语，但将事物进行归类在统计分析中就被称为 Coding。

<details>
<summary>Original English</summary>

**Speaker 1**: And if you're seeing the same explanation across 50 different traces, you know you have a systematic problem and not a one-off edge case, which makes it the first thing you should fix. So you have to take your eval explanations and categorize them into types of failures and count up the categories. This is called coding. Again, we can make up words from the ML world, but categorizing things is known as coding.

</details>

**Speaker 1**: 当然，每条解释都是自然语言，因此人工去做这种归类非常困难，除非你引入另一个大语言模型（LLM）来替你完成分类工作，我们今天晚些时候会演示具体是如何运作的。而且正如我之前所说，你可以将这一大堆解释直接交给一个编程智能体（Coding Agent），让它去自动修复问题。这就是我们今天将要构建的完整闭环。

<details>
<summary>Original English</summary>

**Speaker 1**: And of course, each explanation is natural language. So it is hard to do this coding unless you use yet another LLM to do the categorization for you. We'll be seeing how that works towards the end of today. And like I said, you can hand a whole pile of these explanations to a coding agent and let the app fix it for you. This is the full loop that we're going to build today.

</details>

### AI 软件工程的闭环生命周期

**Speaker 1**: 我们将进行埋点追踪（Instrument）、捕获链路（Trace）、执行评测（Eval）以及持续迭代（Iterate）。每一个环节都会向下传递：首先定义你想要的目标，然后构建它、衡量其表现、发布上线、在生产环境中监控它，并根据观察到的情况进行迭代。每一个传统的软件产品都会经历这样一个循环，但对于 AI 应用而言，度量（Measurement）环节往往是大多数团队折戟沉沙的地方。评测正是我们如何进行度量的方式，评测是贯穿整个生命周期的核心纽带。

<details>
<summary>Original English</summary>

**Speaker 1**: We're going to instrument, trace, eval, and iterate. Each step feeds the next. You define what you want, you build it, you measure how well it works, you ship it, you monitor it in production, and you iterate based on what you see. Every traditional software product goes through a loop like this, but for AI, the measurement step is where most teams fall down, and evals are how we measure. Evals are the connective tissue across this whole lifecycle.

</details>

### 第一步：使用 Arize Phoenix 设置链路追踪

**Speaker 1**: 那么我们现在开始构建。第一步是使用 Arize Phoenix 设置 Trace 追踪。在能够运行评测之前，我们需要一些数据来作为评测的对象，而你无法评估你无法观测到的东西。因此，可观测性（Observation）必须放在首位。希望大家现在都已经搞定了 Wi-Fi 并打开了我们的 Notebook，助教也在现场巡视以确保大家都能跟上。让我们看第一个代码单元格，这里是安装依赖的地方。

<details>
<summary>Original English</summary>

**Speaker 1**: So let's get started building it. Step one is setting up tracing with Arize Phoenix before we can run evals. We need some data to run our evals on, and you can't evaluate what you can't observe. So observation comes first. So hopefully, you've conquered the Wi-Fi and you have our notebook at this point, and TA is running around to make sure that you do. Let's go to our very first code cell, which is where I install our dependencies.

</details>

**Speaker 1**: `claude-agent-sdk` 不用多说，它就是 Claude Agent SDK。而 `openinference-instrumentation-claude-agent-sdk` 是专门针对 Claude Agent SDK 的自动埋点包，这就是它能够在不需要你修改业务代码的情况下，自动从 Claude Agent 捕获 Trace 的原理。正如我刚才提到的，如果你想改用 OpenAI 或者其他框架，我们也为所有这些框架提供了对应的包，你只需要替换它们即可。

<details>
<summary>Original English</summary>

**Speaker 1**: Claude Agent SDK is self-explanatory; that is the Claude Agent SDK. OpenInference instrumentation Claude Agent SDK is the auto-instrumentation package for the Claude Agent SDK. This is how it knows to capture traces from Claude agents without you changing your application code. As I mentioned earlier, you can use OpenAI instead if you want to, or some framework; we have packages for all of those as well. You just need to swap them in.

</details>

**Speaker 1**: `arize` 和 `arize-otel` 是将你的 Trace 发送到 Phoenix 并允许你反查读取它们的包。里面还有一个 `phoenix` 包作为我们使用的工具类库，不用太担心它。而 `anthropic` 包则允许你使用 Claude，既用来驱动我们的 Agent，也用来在后续环节中作为评测裁判（Judge）评判输出。如果你还没运行的话，请运行这个单元格。

<details>
<summary>Original English</summary>

**Speaker 1**: `arize` and `arize-otel` are the packages that send your traces to Phoenix and let you read them back. And there's a Phoenix package in there that we use as a utility package; don't worry about it. The `anthropic` package lets you use Claude, both to power our agent and to judge its output later. So go ahead and run this cell if you haven't already.

</details>

### Agent 框架与 OpenInference 生态

**Speaker 1**: 在安装依赖的同时，我来聊聊我们实际要构建的内容。Claude Agent SDK，如果你以前还没用过的话，它是 Anthropic 推出的用于构建智能体的框架，可以看作是 Anthropic 对 LangChain 这类框架的回应。它可以使用工具查询天气，也能跨轮次维护对话上下文。OpenAI 也有自己的 Agent SDK。当然，市面上还有像 CrewAI、LangChain、Masthead 等一系列成熟的 Agent 框架，而 Phoenix 与所有这些框架都是兼容的。因此，无论你的 Agent 是用什么框架构建的，它都已经支持埋点，你只需开启日志记录，所有的 Trace 就会在面板上点亮。

<details>
<summary>Original English</summary>

**Speaker 1**: And while it's installing, I'm going to talk about what it is that we're going to actually build. The Claude Agent SDK, if you haven't already used it, is Anthropic's framework for building agents. It's Anthropic's answer to LangChain and things like that. It can use tools to search the weather, and it can maintain conversation context across turns. OpenAI has their own Agent SDK. And of course, there are whole agent frameworks like CrewAI, LangChain, and Mastra, and Phoenix is compatible with all of those. So no matter what framework you've built your agent in, it is already instrumented, and you can just turn on logging, and all of your traces will light up.

</details>

### 配置密钥与环境变量

**Speaker 1**: 希望大家的安装现在已经完成了，虽然我这个时间预估可能偏乐观了点。接下来是设置你的密钥（API Keys）。就我这里而言，我是直接从 Colab Secrets 里拉取的密钥。如果你想省事，也可以直接把它们粘贴到单元格里。这里需要填入三项内容：第一，正如前面所说的，你需要一个 Anthropic API Key，它将用于驱动我们 Agent 的 LLM 调用，并在后续驱动 Judge 评测；第二，你需要一个 Arize API Key，可以从你的设置中获取，用于向 Phoenix 服务验证你的流量身份；第三，你需要 Arize Space ID，用于告知 Phoenix 把所有数据归属到哪个工作区。

<details>
<summary>Original English</summary>

**Speaker 1**: Hopefully your install is done by now, which is optimistic timing on my part. Next, set your keys. In this case, I have stored my keys in Colab. If you are feeling naughty, you can just paste them directly into your cell and put them there. Three things go in here: like I said earlier, you need an Anthropic API key, which is going to power our agent's LLM calls, and it's also going to power the judge later; you need an Arize API key, which you get from your settings, which authenticates your traffic to the Phoenix service; and you need Arize Space ID, which tells Phoenix which workspace to put all of your data in.

</details>

**Speaker 1**: 如果你的密钥报错无法使用，常见罪魁祸首一般是复制粘贴错误。当然，助教还在现场四处走动随时提供协助。有人甚至把助教戏称为“行走的内部安全漏洞”，所以如果你实在搞不定密钥，他肯定会直接借给你一个密钥供调试使用。现在我们滚动到注册（Register）部分的代码。我这里先把字体调大一点。需要再出示一次二维码吗？好的。

<details>
<summary>Original English</summary>

**Speaker 1**: If your keys aren't working, the usual culprit is a copy-paste error. And of course, TA is still running around to help you if your keys aren't working. TA has been described as a walking security hole, so he will definitely give you a key if you can't figure out how to get your keys to work. So now we will scroll to the register section. I'm going to bump up my fonts here. The QR code one more time? Sure.

</details>

**Speaker 0**: 大概是第三个……

<details>
<summary>Original English</summary>

**Speaker 0**: Probably 3...

</details>

**Speaker 1**: 对，我自己一般不直接把密钥明文写在 Colab 里，而是通过 Colab Secrets 功能读取出来。好的，我回退到刚才讲的地方，希望我操作顺利。

<details>
<summary>Original English</summary>

**Speaker 1**: Yeah, I don't put my keys in Colab, so Colab Secrets feature pulls it out. Alright, I'm going to go back to where I was, hopefully I can do that.

</details>

**Speaker 0**: 但是这个这个，说说说这个这个……好的。

<details>
<summary>Original English</summary>

**Speaker 0**: But this, this, speaking of this... alright uh.

</details>

### OpenTelemetry 与注册埋点代码实现

**Speaker 1**: 我们已经安装了依赖，讲解了 SDK，配置了 Secrets 密钥，现在来到了 `register` 注册环节。这就是见证奇迹的时刻。任何在 Arize 工作的人都会告诉你：你只需要在应用程序中增加两行代码，就能实现代码埋点。眼前这两行代码正是如此。我们这里所做的是传入 Arize Space ID、API Key 以及我们要追踪命名的工程标识。

<details>
<summary>Original English</summary>

**Speaker 1**: We've installed dependencies, we've talked about the SDK, we've talked about the secrets, and we're at the register. So this is the magic. Anybody who works for Arize will tell you that you only have to add two lines of code to your application in order to instrument your code. And these are the two lines of code. What we're doing here is we're passing Arize Space ID, our API key, and a name for it to trace everything to.

</details>

**Speaker 1**: `register` 函数在底层初始化配置了 OpenTelemetry。OpenTelemetry 是应用可观测性领域的工业标准，而在它之上还有一层叫做 OpenInference，它补充了专属于 LLM 的属性维度，比如 Prompt 文本、Completion 补全文本、Token 消耗量、调用了具体哪个模型、触发了哪些工具等。我们把数据流指向 Phoenix，并指定项目名称，这样你的 Trace 就能在 UI 界面中按项目聚类分组。

<details>
<summary>Original English</summary>

**Speaker 1**: The register function is setting up OpenTelemetry. OpenTelemetry is the industry standard for application observability, and it has a layer on top called OpenInference, which adds LLM-specific attributes: things like prompt text, completion text, token counts, which model was called, and which tools were invoked. We point it at Phoenix, and we give it a project name, and that is how your traces get grouped in the UI.

</details>

**Speaker 1**: 在当前示例中，我们还传入了 `batch=False`。在 Notebook 环境中运行时，你会希望遥测数据在发生时立即发送，而不是像生产环境为了提升吞吐效率那样进行批量打包发送。底部的那一行 `ClaudeAgentSDKInstrumentor` 告诉 Claude SDK：每当它发起 LLM 调用或执行工具调用时，都向 Phoenix 发送一个 Span（跨度记录）。至此，埋点就完全生效了。

<details>
<summary>Original English</summary>

**Speaker 1**: In this case, we're also passing `batch=False`. When you run in a notebook, you want to send your telemetry as soon as it happens, and not batch stuff up, which it does for efficiency in production. That one line at the bottom, the Claude Agent SDK instrumentor, tells the Claude SDK to send a span to Phoenix every time it makes an LLM call or invokes a tool. And that is now instrumented.

</details>

**Speaker 1**: 之所以仅需如此少量的代码就能跑通，是因为 OpenTelemetry 是几乎所有人都在遵循的开放标准。因此，Claude SDK 的作者、OpenAI SDK 的作者、LangChain 的作者，都已经提前在各自的 SDK 内部实现了调用 OpenInference 并回传数据的逻辑。你所需做的仅仅是声明：“嘿，我是一个 OpenInference 采集器，我的地址在这里，把数据发给我吧。”

<details>
<summary>Original English</summary>

**Speaker 1**: The reason this works with so little code is because OpenTelemetry is an open standard that nearly everybody uses. So the Claude SDK authors, the OpenAI SDK authors, the LangChain authors—all of them have already written the code inside of their SDKs that calls OpenInference and sends data back. So all you have to do is say, "Hey, I'm an OpenInference collector, I live here, send it to me."

</details>

### 从 Phoenix 读取追踪与副本准备

**Speaker 0**: 还有一点配置说明需要注意。

<details>
<summary>Original English</summary>

**Speaker 0**: One more bit of setup.

</details>

**Speaker 1**: 这里的关键在于：`register` 调用负责把数据发送给 Phoenix，而 Arize Client 客户端则用于从 Phoenix 把数据读回。我们接下来会用它把生成的 Spans 重新拉取回 Notebook 本地，这就是下面这行代码的作用。因此大家必须确保在这两处配置了完全相同的密钥，或者正确完成了复制。另外，如果大家需要编辑代码，请记得先在 Colab 的“文件”菜单中创建 Notebook 的副本。好的，如果大家执行完毕这几个单元格，我们就准备好开始构建了。

<details>
<summary>Original English</summary>

**Speaker 1**: Is that the register call sends data to Phoenix, and the Arize client reads data back out of Phoenix. So we'll use it to pull our spans back into the notebook. That is what this line is about. So you need to make sure that you've put in the same keys there or copy them across. Oh, you need to make a copy of the notebook from the File menu to be able to edit, cool. All right, so if you run those cells, then we are ready to build.

</details>

### 动手实操与自动化 Agent 技能（Arize Skills）

**Speaker 1**: 在正式编写代码前，有一点值得大家了解：我们今天手动操作的所有流程，其实也完全可以交由你的 Coding Agent 来代劳。之所以今天我们要亲自动手一步步来，是为了让大家从底层真正理解这些机制背后的运行本质，而不是全凭直觉和运气碰巧成功。不过，我们官方确实发布了一套叫做 Arize Skills 的工具集。

<details>
<summary>Original English</summary>

**Speaker 1**: Before we build, one thing worth knowing about: everything we're going to do by hand today, you can also get your coding agent to do for you. The reason we are doing it by hand is so that you have a fundamental understanding of what it is that you're doing, and you're not just vibing your way to success. But we publish a set of skills called the Arize Skills, which know how to do all of this for you at the skills level.

</details>

**Speaker 1**: 这套 Skills 能够直接在 Agent 技能层面上帮你处理这一切：安装 Arize Skills 后，它能自动运行评测、创建数据集，甚至一开始就替你的应用程序完成埋点改造。它们全部遵循 Phoenix 推荐的最佳实践范式，仅需一条简单的 `npx` 命令即可完成一次性安装。它们不仅支持 Claude Code，还适配 Cursor、Codex 以及其他几十种主流 Coding Agent。虽然我们今天以教学目的手动实操，但在实际的生产环境中，我们每天都在使用这套技能来自动化这部分工作。

<details>
<summary>Original English</summary>

**Speaker 1**: So you can install your Arize Skills and run evaluations, create datasets, and instrument your app in the first place. They all use Phoenix's recommended patterns, and you install them once with a single npx command. They work in Claude Code, they work in Cursor, they work in Codex and dozens of other coding agents. So we're going to do stuff manually today, but in production in a real-life environment, we are using our own skills every day to do this stuff.

</details>

### 构建金融分析智能体

**Speaker 1**: 现在让我们来构建这个智能体。刚才我问大家是否曾经写过 Agent 时，全场都举手了，所以我不会花太多时间去细讲这个 Agent 本身的基础机制。我假设大家手头已经有现成的 Agent，现在只是想给它加上链路追踪并让它顺利跑起来。我们今天使用的示例 Agent 是一个基于 Claude Agent SDK 构建的金融分析聊天机器人。

<details>
<summary>Original English</summary>

**Speaker 1**: So now let's build our agent. When I asked if everybody had written an agent before, everybody put their hand up, so I'm not going to spend a lot of time explaining how this agent works. I'm going to assume that you already have an agent somewhere, and you're just trying to instrument it and make it work for you. The mock agent that I'm using today is a financial analysis chatbot using the Claude Agent SDK.

</details>

**Speaker 1**: 你向它提供一个股票代码和一个关注领域，它就会在网络上检索关于该股票代码的最新动态，调研真实的实时财务数据，并为你撰写一份分析报告。这是一个真实存在的业务场景，市面上甚至有整个初创公司围绕这一方向构建产品，尽管我们这里的 Agent 版本经过了极度简化。我们的 Agent 分为两个轮次执行：第一轮是调研轮次（Research turn），它通过调用工具进行网络搜索并收集必要数据。

<details>
<summary>Original English</summary>

**Speaker 1**: You give it a stock ticker and a focus area, and it searches the web for the latest information about that stock ticker, researches real current financial data, and writes a report for you. This is a real use case that whole startups are built around, although my agent version is extremely simple. I'm assuming that you built an agent already; our agent works in two turns. The first is a research turn that uses tools to search the web and gather data.

</details>

<!-- chunk 4/12 -->

### 构建双轮 Agent：调研与报告撰写

**Speaker 1**: 接下来是写作环节，它负责将调研成果整理成一份可读的报告。我带大家来看一下这部分内容。这里是我的调研提示词（research prompt）和写作提示词（write prompt），我故意把它们设计得极其简单。它们之后肯定会引发一些错误，而这正是我们要利用评测（evals）来进行调试的地方。接着，我正在设置 Claude Agent 的选项。在底层，我使用的是 Claude Haiku 模型作为 Agent，因为 Haiku 既具备足够的能力，同时又难免会犯错。我们正需要它犯一些错误，这样我们才能进行修复；此外它速度快、成本低，在我们做这个实验时不会消耗太多大家的预算。

<details>
<summary>Original English</summary>

**Speaker 1**: Then there is a writing component, which compiles the research into a readable report. So let me walk you through that. Here's my research prompt, and my write prompt. These are deliberately extremely simple. They are going to cause errors later, and those are the things that we are going to use our evals to debug. And then I'm setting up my Claude Agent options. I'm using Claude Haiku as the agent underneath, because Haiku is capable, but it makes mistakes. And we want some mistakes so that we can fix them. And it's also fast and cheap, so I don't burn a lot of your money as we do this.

</details>

**Speaker 1**: 权限模式（permission mode）控制着 Agent 能够自主执行哪些操作。在我做出的具体选择以及我现在赋予该 Agent 的具体可用工具中，其实暗藏着一个玄机，我们稍后就会发现。现在我们来看这两个轮次（turns）：第一轮是调研（research），这里有许多模板代码我就不细讲了，它们的作用纯粹是为了把中间输出打印出来，以便我们能实时看到它在执行过程中的动作；第二轮则是撰写报告，同样包含一部分模板代码。

<details>
<summary>Original English</summary>

**Speaker 1**: The permission mode controls what the agent is allowed to do autonomously. There is a catch hiding in the specific choices that I've made and the specific allowed tools that I am giving this agent right now, as we're going to find out later. And now let's look at our two turns. Turn number one is research. There is a bunch of boilerplate in here that I'm not going to explain, which is just about outputting the output so that we can see what it's doing as it's going. Turn two is writing the report with, again, a pile of boilerplate.

</details>

**Speaker 1**: 提示词非常关键。因此在你们自己的 Notebook 中，我希望大家从这里开始动手做修改。我在最顶层给出的都是极其基础的提示词。大家可以想想看，如果让你脱口而出一个更好的提示词来解决这个问题，能够比我写的内容更好地完成最初的调研，或者比我写的提示词更好地完成报告撰写，你会怎么写？如果你能一步到位写好（one-shot），后续要做的工作就会少很多。

<details>
<summary>Original English</summary>

**Speaker 1**: The prompts are critical. So this is where I want you to start doing your own changes in your own notebook. I have given it extremely basic prompts at the top. If you can see, if you can think of a better prompt just off the top of your head that is going to do a better job than the prompt that I put to solve this problem—what would be better than what I put in to do the research in the first place, what would be better than what I put in to do the report writing? And if you one-shot it, then you're going to have less stuff to do later on.

</details>

### 链路追踪与非确定性执行

**Speaker 1**: 我们在这里做的一件事是把整个流程包裹在一个 OpenTelemetry Span 里面。这是因为如果我不这样做，Claude 就会把这两个轮次感知为两个彼此独立的 Span，而我们希望它们在 UI 界面上被归组到一起。所以我把它们包在同一个 Span 中，让它们作为一个统一的 Agent 交互轮次展示出来。这只是为了在后续帮我们节省一些时间，我想向大家解释清楚写这几行代码的原因。现在我们可以运行 Agent 了。我自己已经提前运行过了，因为我想确切了解它会产生什么行为，但现在大家该启动你们自己的 Agent 了。我给它的要求是分析特斯拉（Tesla），特别是其财务表现和增长前景。大家可以直接运行这个单元格，这需要花上一两分钟时间，因为 Agent 确实会去搜索网络，而且大语言模型（LLM）正在进行多轮推理。

<details>
<summary>Original English</summary>

**Speaker 1**: One of the things we do here is we wrapped the whole thing in an OpenTelemetry span. This is because if I don't do that, then it senses the two turns as two separate spans, and we wanted them to be grouped together in the UI. So I've wrapped them in a span together so that they come out as a single agent turn. This is just saving us some time later. I wanted to be clear about why I'm doing this bit of code, and now we can run our agents. I have run my agent in advance because I wanted to know exactly what it was going to do, but now is the time to kick off your own agent. I've asked it to analyze Tesla, specifically its financial performance and growth outlook. You should go ahead, run this cell. It'll take a minute or two, because the agent will actually search the web, and the LLM is doing multiple rounds of reasoning.

</details>

**Speaker 1**: Agent 接收到我们的调研提示词后，判断出自己需要搜索网络，于是发起工具调用（tool call）。它读取搜索结果，判定当前信息是否充分，必要时再次发起搜索。这就是具有自主性（agentic）的部分。你并没有命令它“先进行一次网页搜索，提取信息，然后写一份报告”。相反，是 Agent 自己在决定：“这次搜索获得的信息足够了吗？如果不够，我就继续执行更多次网页搜索。”它会运行不确定次数的网络搜索来获取足够的信息，直到它自己认为“足够”为止，然后再去撰写报告。

<details>
<summary>Original English</summary>

**Speaker 1**: The agent receives our research prompt, decides it needs to search the web, which is a tool call. It reads the search results, it decides if it has enough information and maybe searches again. That is the agentic part. You didn't say do a web search, take the information from the web search and write a report about it. The agent is deciding: is this web search enough information? And if not, I will run more web searches. It will run an indeterminate number of web searches to get enough information until it has decided what enough means, and then it will write the report.

</details>

**Speaker 1**: 这种执行路径从设计上讲就是非确定性的（non-deterministic），这是需要理解的核心要点。如果你用相同的输入再次运行它，你的 Agent 可能会搜索不同的内容，可能会检索到不同的结果，写出的报告也可能完全不同。两份报告可能都很出色，也可能一份很好而另一份很糟糕。这恰恰就是我们需要评测的原因：我们无法仅凭输入就预测出输出结果，而 Agent 做出的每一个细微决策都被完整记录为了 Trace（追踪）。

<details>
<summary>Original English</summary>

**Speaker 1**: This execution path is not deterministic by design, and that is the key here to understand. If you run this again with the same input, your agent might search for different things, it might find different results. It might write a different report, and both reports might be good or one might be good and one might be bad. And that is exactly why we need evals. We can't predict the output from the input alone, and every single one of those decisions is being captured as a trace.

</details>

### 可观测性与静默失败排查

**Speaker 1**: 我打开过去 12 小时或者 24 小时的记录看一下。好的，这里有一大堆 Traces。稍后大家就会明白这些内容的含义。但在这里你们可以看到我之前运行的那个特斯拉任务。当我逐项点进去时，界面呈现的就是这个样子。大家可以看到每一个轮次：它在调用 Skill，在搜索工具，在执行网页搜索……它所做的每一件事都清晰可见。你们能看到它一共发起了 4 次网页搜索，随后才判定信息已经足够。接着它进入这一步骤的第二个调用，开始撰写报告。

<details>
<summary>Original English</summary>

**Speaker 1**: So I'm just going to pop open my last 12 hours or my last 24 hours, I guess. Cool. This is a pile of traces. You're going to understand what all of this is later. But here you can see the Tesla one that I ran earlier. This is what it looks like when I go through. You can see every single turn. It's calling a skill, it's doing a tool search, it's doing a web search. You can see every single thing that it does. You can see that it ran four web searches before finally deciding that was enough information. Then it did the second call in the step, and it wrote the report.

</details>

**Speaker 1**: 它执行的操作中有一点我们之后会看到——我之前提到过，我给它的工具集里其实藏着一个玄机。在我们在搭建这个演示案例时，出现了一个意料之外的步骤：它尝试去写报告，我让它撰写一份报告，结果它尝试把这份报告作为 Markdown 文件写入磁盘。但它当前运行在 Colab Notebook 虚拟环境中，根本就没有供它写入的目标文件系统。所以写入文件的这一步注定会失败。这正是你需要评测的原因所在：你需要通过评测去发现你的 Agent 何时在执行某种看似有用但实际上错误的操作。因为这种错误是静默发生的（failed silently），它依然向你输出了最终结果，但在后台却悄悄执行了这种毫无必要的额外写入磁盘步骤，而你如果不看 Trace 根本察觉不到它的存在。

<details>
<summary>Original English</summary>

**Speaker 1**: One of the things that it does that we're going to see later is—I told you there was a catch in the tools that I gave it. Here's this step that was unexpected when we were putting this demo together: it tried to write the report. I told it to write a report. It tried to write the report as a markdown file to disk. It is living in a Colab notebook, so there is no filesystem for it to write to. So the write step would fail. And this is something that you need evals for: you need evals to detect when your agent is doing something helpful but incorrect, because this failed silently. It gives you output anyway, but it's doing this unnecessary extra step of trying to write to disk without you knowing that it was there.

</details>

**Speaker 1**: 回到 Colab 中，这是一份相当不错的报告：里面有财务业绩表格与具体数字、增长驱动因素、风险因素以及分析师目标价和结论。作为初稿来看它确实挺好，但这只是凭感觉（vibe）觉得不错，而我们在这里的目标是用确凿的数据来替代主观感觉。正如我刚才所说，你可以在 Traces 里面看到所有这些细节。我们无需额外做任何埋点插桩（instrumentation）就能获取这些全部信息，不必为了捕获大模型的调用情况去对每一行代码手动埋点。所有这些功能都内置在 Claude Agent SDK 中，就像 OpenAI SDK 中内置的功能一样。这个表格中的每一行都代表一个 Span，Trace 会揭示 Agent 做出的每一个决策；如果没有它们，你看到的就仅仅是“我给了一个提示词，然后拿到了一份报告”。有了 Trace，你能看到每一步动作；如果点进任何一个 Span，你都能确切看到模型接收到了什么输入以及准确返回了什么输出。这就是可观测性在实践中的真正意义：不仅仅关注“它是否成功运行了”，更要关注“它是如何运行的”以及“它究竟在哪个环节出了错”。

<details>
<summary>Original English</summary>

**Speaker 1**: So back to the Colab. This is a pretty good report. It's a financial performance table with real numbers, growth drivers, risk factors, and analyst price targets, the conclusion. It's not bad for a first pass, but it's not bad as a vibe, and we are here to replace vibes with actual numbers. So like I said, you can see all of that stuff in the traces. We didn't have to do anything to get all of that information. We didn't have to instrument every single line to get the LLM calls and all of that stuff. All of that is built into Claude Agent SDK, just like it's built into OpenAI SDK. And each one of these rows in this table is a span. Traces reveal every decision the agent made. Without them, all you see is: I gave it a prompt, and I got a report. With traces, you see every step. If you click into any span, like I said, you'll see exactly what the model received as input and exactly what it returned. And that is what observability means in practice: not just did it work, but how did it work? And where exactly did it go wrong?

</details>

### 构建测试集与错误分析

**Speaker 1**: 我们过几分钟就会开始运行评测。我们将从这些 Span 中提取输入与输出属性，并将它们喂给我们的评估器（evaluators）。Span 的输入会成为评估器的输入，而 Span 的输出则会成为被评分的对象。现在我们需要生成一些测试数据，以便运行有意义的评测。仅仅靠大家刚才生成的单次 Trace 是不够的，我们需要在 Notebook 中准备一批数据集。Notebook 中提供了 12 个测试查询（test queries），涵盖了不同的股票代码和分析类型。大家现在就应该把它们跑起来。假设网络正常且运行顺利，大约需要 5 到 10 分钟。我来给大家展示一下它们在 Notebook 中的样子，就是这些。

<details>
<summary>Original English</summary>

**Speaker 1**: We run evals in a few minutes. We're going to pull the input and output attributes out of these spans, feed them to our evaluators. The input becomes the evaluator's input, output becomes what gets graded. Now we need to generate some test data to run meaningful evals. We need more than the one trace that you've generated so far, we need a body of data in the notebook. There are 12 test queries covering different tickers and analysis types. You should kick those off now. They take about 5 to 10 minutes to run, assuming that you've got Wi-Fi and everything's working, and I'm going to show you what they look like in the notebook. This is them here.

</details>

**Speaker 0**: 是不是有意见？

<details>
<summary>Original English</summary>

**Speaker 0**: 是不是有意见？

</details>

**Speaker 1**: 这里的核心在于多样性（diversity）。我给它提供了一批理应能够正常跑通的显而易见查询；同时我也给它设置了一些边界案例（edge cases）。比如我给了一个包含两个股票代码（苹果和微软）并让它进行对比的查询，这是它理论上能够处理的任务。另外，我也在不同查询中多次使用了相同的股票代码，这样我们就能观察非确定性输出的差异——比如“亚马逊的盈利能力、趋势与展望”对比“亚马逊 AWS 的业绩与盈利能力”。不同的股票代码、不同的问题以及不同的复杂度级别，对于生成能够覆盖真实用户提问维度的测试数据而言至关重要。虽然剧透一下：真实用户提问的古怪程度，永远是你无法提前完全预料到的。这也是评测之所以极其重要的另一个原因。比如关于 Rivian（RIVN）的查询，询问的是一家公开数据远少于苹果或微软的公司；而关于可口可乐股息率的查询，与成长股查询相比则是完全不同的分析类型。再次强调，这种多样性非常关键。只有通过测试集，你才能抓出 Agent 不擅长处理的情况。

<details>
<summary>Original English</summary>

**Speaker 1**: So the key thing here is diversity. I've given it a bunch of obvious queries that should work. I've also given it some edge cases. For instance, I've given it one where I gave it two tickers, Apple and Microsoft, and told it to run a comparison, which is something it could theoretically do. I've also given it the same tickers multiple times in places so we can see the non-deterministic output: when we say Amazon profitability, trends, and outlook versus Amazon AWS performance and profitability. Different tickers and different questions, different levels of complexity are important to generate test data that's going to cover the range of things that users will actually ask. Although spoiler alert: real users are going to ask weird things that you're not going to be able to predict in advance. That is another one of the reasons that evals are important. The Rivian query (RIVN) asked about a company with much less public data than Apple or Microsoft, and the Coca-Cola dividend yield query is a very different kind of analysis from a growth stock query. Again, this is diversity that is important diversity, and your test set is how you catch things that your agent is going to be not good at.

</details>

**Speaker 1**: 当大家的任务还在运行时，我的已经加载完成了，所以我可以向大家展示我这边所有的数据。这些就是从那几次运行中生成的所有 Span。大家可以在底部看到一共 13 次，包括最初的特斯拉运行以及后续的 12 次测试查询，每一次都是 Claude 财务分析师的完整执行过程。现在我们已经拿到了数据。但在编写任何评测之前，我们需要实际去查看这些数据。这就是错误分析（error analysis），而整个步骤其实只有一条指令：在编写评测之前、在写下哪怕一个评估器之前，务必先仔细阅读你的 Trace！从你的数据出发，端到端完整阅读十几个或更多的 Trace。这是整个工作坊中最重要的一项实践操作。重点关注那些出错的 Trace：输入是什么？输出是什么？具体是哪里坏掉了？这听起来可能非常老派——“直接去读输入内容”——但它却是 Agent 开发中价值最高的一项工作。例如，Anthropic 就专门针对这个环节投入了工具开发……

<details>
<summary>Original English</summary>

**Speaker 1**: So while yours are running, mine have already loaded, so I can show you all of my data. These are all of my spans from all of those runs. You can see at the bottom there 13, which is the initial Tesla run and 12 test queries. Each one is a complete execution of the Claude financial analyst. So now we have the data. But before we write any evals, we need to actually look at the data. This is error analysis, and the whole step is one instruction: read your traces before you write evals! Before you write a single evaluator, start with your data. Read a dozen or more of your traces end to end. This is the most important practice in this entire workshop. Focus on the ones where something went wrong: what was the input? What was the output? What specifically is broken? This sounds extremely old-fashioned—just read the input—but it is one of the highest value activities in agent development. Anthropic, for instance, invested in tooling...

</details>

<!-- chunk 5/12 -->

### 评估前必须明确需求与成功标准

**Speaker 1**: 特别是在审查评测轨迹（eval transcripts）方面，他们的团队每天都花费大量时间专门查看这些评估轨迹。追踪记录（trace）能清楚告诉你，智能体究竟是犯了真正的错误，还是评估者误判并否决了一个有效的解决方案。如果你在搞清楚系统到底是如何失败之前就急于做自动化，那么你最终构建出的评测只会去衡量那些容易测量的指标，而不是真正重要的东西。你必须先有需求。在对失败模式进行归类之前，你首先需要知道成功是什么样子的。如果连“正常运作”的定义都没有明确，你就根本无法断言它“无法正常运作”。

<details>
<summary>Original English</summary>

**Speaker 1**: specifically reviewing eval transcripts, and their team spend a whole lot of time just looking at eval transcripts every day. A trace tells you whether the agent made a genuine mistake or whether the evaluators rejected a valid solution. If you automate before you understand your failures, then you're going to create an eval that measures what's easy to measure instead of what actually matters. You need requirements first. Before you can categorize failures, you need to know what success looks like. You can't say it doesn't work if you haven't defined what it works means.

</details>

**Speaker 1**: 对于我们的财务分析师来说，一份优秀的报告究竟应该具备什么？它应当引用正确的股票代码（ticker）；应当包含真实、近期且具备可操作性的财务数据；应当给出切实可行的建议；还应当明确区分前瞻性分析与历史总结。这些就是我们的成功标准。当你把它们逐条写下来时，它们看起来再明显不过了。然而很多团队却从不这么做：他们直接发布智能体，然后疲于应付各种用户投诉，而不是预先划定标准底线。将需求白纸黑字地写下来，能把模糊的失望感转化为具体的、可测试的指标，而正是这些标准构成了后续评测的基石。

<details>
<summary>Original English</summary>

**Speaker 1**: For our financial analyst, what does a good report look like? It should reference the correct ticker. It should include some real, recent, actionable financial data and include actionable recommendations. It should distinguish between forward-looking analysis and historical summary. Those are our success criteria, and they seem obvious when you write them down, but lots of teams never do. They ship an agent and then react to complaints, instead of defining the bar up front. Writing requirements down turns vague disappointment into specific testable criteria. And those criteria are what turn into your evals.

</details>

### 定义成功：业务领域专家的关键角色

**Speaker 1**: 关于定义成功标准，还有一点非常重要：这绝不是你的工程师能够独立完成的事情，工程师甚至不能单方面主导这件事。“好”的定义往往深植于领域知识之中，而这些领域知识恰恰掌握在你们公司通常略带讽刺地称之为“非技术人员”的人手里——比如你的产品经理、QA、支持团队。这些人才是真正清楚“优秀”的定义是什么的人，他们深知潜在的失败场景会是什么模样，也正是他们应该协助你共同编写评测标准。OpenAI 曾总结得非常精辟：他们说“人员管理技能就是 AI 技能”。明确的目标、直接的反馈、清晰知晓自己的价值主张——当系统是概率性（probabilistic）的时候，这些技能比以往任何时候都更加重要。这也是整个工具平台围绕的核心理念之一：团队中的任何人都可以阅读追踪记录、添加标注并对评估标准作出贡献。这不仅仅是一个纯工程界面，我们本就期望其他团队成员也能参与其中。

<details>
<summary>Original English</summary>

**Speaker 1**: Here's the thing about defining success that it's important to note, though, which is that it is not something that your engineers can do, or not something your engineers can do alone. The definition of good usually lives in the domain knowledge, and the domain knowledge lives in the people that your company will often laughably refer to as non-technical. So your product managers, your QA, your support team. Those are the people who know what the definition of good really is. They know what the failures are going to look like. Those are the people who should be helping you write your evals. OpenAI put it really nicely: they said that people management skills are AI skills. So clear goals, direct feedback, knowing what your value proposition is—those skills matter more than ever when the system is probabilistic. And this is one of the things that Arize is built around: anyone on your team can read traces or annotations and contribute to your criteria. This is not just an engineering surface. You're expected to have other members of your team in here.

</details>

### 测试数据的构建：从合成数据走向生产环境

**Speaker 1**: 顺便简单说一下从哪里获取这些测试数据。我们目前拥有这些追踪记录，是因为我们自己已经运行过该智能体了。但如果你正在开发一个新产品，尚未拥有真实的生产流量，该怎么办？你可以采取我们刚刚的做法，即使用合成数据（synthetic data）。你可以让大语言模型在你预期的各个类别中生成多样化的查询。例如，“调研特斯拉的财务表现”是一种表达方式，“特斯拉股票最近怎么样了”是另一种表达，而“特斯拉现在值得买入吗”是第三种问法。它们的意图完全一致，但字面表述截然不同。因此，需要丰富句式、复杂度和具体程度。领域专家应当审核你的这组查询，因为 LLM 生成的查询往往容易扎堆在常见表述上，容易遗漏真实用户会写出的各种千奇百怪的问题。

<details>
<summary>Original English</summary>

**Speaker 1**: A quick note on where to get this test data. We have these traces because we already ran the agent ourselves. But what if you're building something new and you don't have real traffic yet? You can do what we just did, which is you can use synthetic data. You can have an LLM generate diverse queries across your expected categories. "Research Tesla financial performance" is one phrasing. "What's going on with Tesla stock?" is another query that's asking the same thing. "Is Tesla a buy right now?" is a third way of expressing the same query. They're all the same intent, but they look very different. So vary the phrasing, the complexity, the level of specificity. A domain expert should review your set of queries, because LLM-generated queries tend to cluster around obvious phrasings and miss the weird stuff that real users write.

</details>

**Speaker 1**: 你还需要在测试数据中包含边缘情况（edge cases），比如不存在的股票代码、多部分组成的复杂问题，以及越狱攻击尝试（jailbreak attempts）。这些可能只占你总流量的 1%，但这 1% 的流量一旦失控，往往就会演变成媒体报道中的公关灾难。你的测试数据应该反映生产环境的真实面貌，而不是你一厢情愿希望的生产环境模样。合成数据可以帮你起步，但一旦有了真实生产数据，你就应该立即换用生产数据来进行测试评估。

<details>
<summary>Original English</summary>

**Speaker 1**: You also need to include edge cases in your test data, so things like nonexistent tickers, multiple-part questions, jailbreak attempts. Those might be 1% of your traffic, but they are the 1% of your traffic that ends up, you know, being a PR disaster in the press. Your test data should look like production data, not what you wish production looked like. So synthetic data can get you started. But as soon as you have production data, production data should be what you're running on.

</details>

### 分析追踪记录：静默失败与幻觉问题

**Speaker 1**: 现在让我们实际查看一下追踪记录。正如我之前所说，最开始的十三条追踪记录是我运行生成的。其中大部分都在输出中直接生成了长篇结构化报告。比如特斯拉、苹果、英伟达等公司的报告，直接在追踪记录的输出框里生成了 3,000 到 7,000 个字符的报告，包含执行摘要、估值表格，以及明确的“买入”或“持有”建议。从表面上看，绝大多数结果似乎都很正常。但正如我提到的，这十三条中有三条表现非常怪异：它们的输出内容异常简短，只是简单交代一句：“我已经为你把内容保存到磁盘上了。”实际的输出内容被写到了磁盘中。因此，系统最终展示的并不是一份完整的报告，而只是报告的摘要，而报告的主体内容却写入了实际上根本不存在的磁盘路径。这就是评测机制要揪出的问题：智能体在没有任何权限的情况下擅自决定写入文件，写入操作静默失败，它却反馈告诉我们报告已保存。这种模式只有在你亲自深入阅读追踪记录时才能发现。

<details>
<summary>Original English</summary>

**Speaker 1**: So let's actually examine our traces. Like I said, the first thirteen traces are the first thirteen traces that I wrote. Most of them produced long structured reports inline. So Tesla, Apple, Nvidia, stuff like that—3,000 to 7,000 characters of report right there in the trace output with executive summaries, valuation tables, explicit buy or hold recommendations on the surface. Most of these look fine. But like I said, three of the thirteen were doing something weird, which was they were... the output in them is much shorter, because it just says, "Oh, I wrote this to disk for you." And the output went to disk. So instead of having a full report, it has a summary of the report and the actual body of the report went to the nonexistent disk. This is what the eval is designed to find. The agent decided to write to disk with no permission, the write silently failed, and it told us the report was saved. And that is the kind of pattern that you only see if you actually read the trace.

</details>

**Speaker 2**: 呃，所以这应该是……

<details>
<summary>Original English</summary>

**Speaker 2**: Um so this is,

</details>

**Speaker 1**: 我想这是其中一条源记录……不，那一条正常跑通了。噢糟糕，这网络延迟……看，这里找到了。这条追踪记录展示了另一种失败形式：它陷入了无限循环。它当时试图检索关于微软的信息，结果陷入了一连串无休止的网络搜索中，耗费了极长时间。这是它尝试写入磁盘的内容，而这是它实际返回的输出——看这里：“报告已保存为 microsoft cloud segment financial report.md”。这份报告毫无价值，因为它引用了一个根本不存在的外部文件。另外还有一个表现为“自信胡说”的典型例子：如果我们看 Rivian 的报告，它和微软那条存在同样的写入磁盘问题，但更严重的是，即便在它尝试写入磁盘的完整报告内部，充斥着大量关于非上市私有公司的极度自信的断言，而这些信息是根本无法核实的。这些内容可能是幻觉，也可能不是，但我们完全没有做任何检验来核实这份报告是否立足于事实。因此，我们稍后要专门针对这种情况做一个评测。

<details>
<summary>Original English</summary>

**Speaker 1**: I believe one of the three sources... no, that one, it worked. Oh no, the Wi-Fi, here we go. So this one is showing another kind of failure where it just got stuck in a loop forever. It was trying to find information about—who was it trying to find information about? Microsoft—and it just got into an endless series of web searches and took forever. This is what it tried to write to disk, and this is what it actually wrote to output right here, here we go: "The report has saved as microsoft cloud segment financial report.md." This report is useless because it's referring to a report that doesn't exist. There's also an example of a confidently wrong: if we go to the Rivian reports, Rivian has the same problem that the Microsoft one does, but even inside of the full report that it tried to write to disk, there's a whole bunch of really confident information about a private company that you can't possibly verify. These might be hallucinations, they might not be hallucinations, but we haven't done anything to check whether or not this report is really grounded in reality. So we're going to do an eval about that later.

</details>

### 定性研究方法：开放式编码与轴心编码

**Speaker 1**: 阅读分析这些追踪记录有一种系统化的方法，正如我之前提到的，它被称为“编码”（coding）。它分为开放式编码（open coding）和轴心编码（axial coding），源自质性研究方法。开放式编码的意思是：你逐条仔细阅读追踪记录，看到什么问题就如实记下什么。比如“建议过于模糊”、“捏造数据”、“分析了错误的股票代码”。此时你不需要试图表现得像个有强迫症的程序员那样工整。作为程序员，往往会忍不住提前定义好各类标签，然后套用说“噢，这是一个检索失败”之类。在做开放式编码时千万不要这么做，只需用最自然的日常语言如实记录具体问题所在即可。

<details>
<summary>Original English</summary>

**Speaker 1**: There is a structured way to do this reading, which, as I mentioned earlier, is called coding. There's open coding and axial coding, and it comes from qualitative research. Open coding means you read each trace, and you write down what you see. So stuff like "vague recommendation", "made up a number", "talked about the wrong ticker." You're not trying to be neat. As a programmer, it is very tempting to try and come up with categories in advance and say, "Oh, this is a retrieval failure" or whatever. Don't do that when you're doing open coding; just write down what the problem was in as natural language as possible.

</details>

**Speaker 1**: 然后，当你梳理完这些失败现象后，接下来才进行轴心编码。轴心编码是指你综合审视所有整理出来的开放式代码，然后进行归类聚类。你会发现：“好的，现在这里有五条现象本质上是相似的，我要把它们归入同一个类别”，从而提炼出结构化的分类。这第二道工序——轴心编码阶段——才具有结构性。正如我所说，人们往往倾向于、或者忍不住想一步到位直接做轴心编码，你必须克制这种冲动。当你发现一个错误时，应该追问它究竟为什么失败。输出回答错误仅仅是一个表象症状：是因为检索到的搜索结果质量差吗？那是检索失败（retrieval failure）；是因为获得了正确的数据却推导出了错误的结论吗？那是推理错误（reasoning error）；是因为它凭空编造了一个股票价格吗？那显然是幻觉（hallucination）；是因为它的回答超出了职责范围吗？那是越界违规（scope violation），说明它执行了未被授权的操作。每一个根本原因、每一个轴心编码都对应着完全不同的修复方案。如果你搞不清楚根本原因，你就选不对正确的修复方案。

<details>
<summary>Original English</summary>

**Speaker 1**: And then you want to do axial coding afterwards. Axial coding is when you look at all of the open codes you put together and then you do the categorization. You say, "Okay, now there are five things that look similar. I'm going to give them all a single category and turn them into categories." The second pass, the axial coding pass, is structural. And like I said, the tendency, the temptation is to try and go straight to axial coding, and you should resist that. When you find a failure, you should ask why it failed. The response being wrong is a symptom. Did it get bad search results? That is a retrieval failure. Did it get the right data, but the wrong conclusion? Then that is a reasoning error. Did it make up a stock price? That's obviously hallucination. Did it answer outside of its domain? That is a scope violation—did it do something that you didn't tell it that it should be able to do? Each root cause, each axial code points to a different fix. If you don't know the cause, you can't pick the right remedy.

</details>

### 根本原因优先级与瑞士奶酪模型

**Speaker 1**: 完成分类之后——就像我这里所做的——你可以将它们汇总成一张表格。坦白讲，我并没有真正把所有这些轨迹通读并打上标签，我只是随机赋予了它们一些轴心编码。但最终你得到的就是这样一张根本原因频率统计表，涵盖了诸如“状态良好”、“潜在幻觉”、“推理断层”、“无法验证的数据”、“缺失投资建议”等维度。人们通常容易盯着排在第一位的指标（比如“潜在幻觉”），并主观认定这是最需要优先解决的问题。但在实际操作中，你必须在发生频率与严重程度之间取得平衡。举个例子，如果在一百次运行中，它有一次没有输出财务报告，而是给用户生成了制作炸弹的指南，你必须最优先修复这个问题，因为那是可能发生的最严重的灾难性故障。因此，你必须将严重性乘以发生频率，以此来决定优先修复哪些缺陷。这就是为什么在动手编写评测脚本之前，你必须先深入分析真实数据。

<details>
<summary>Original English</summary>

**Speaker 1**: Once you've categorized, which I did here, you can sum them up into a table. So confession time: I didn't actually read all of those traces and code them, I just gave them random axial codes. But what you end up with is this table of root cause frequency, things like "looks good", "possible hallucination", "reasoning gap", "unverifiable data", "missing recommendation." It's tempting to look at the top one, the possible hallucination, and decide that that is the most important one to fix. But in reality, you're going to want to balance between frequency and severity. So if one time in a hundred, instead of doing a financial report, it gives the user instructions on how to make a bomb, you fix that one first, because that is the most severe possible failure. So you have to multiply the severity by the frequency to get to which ones you decide to fix first. And that is why you look at the data before you write your evals.

</details>

**Speaker 1**: 在正式开始之前，还要讲一个概念，那就是“瑞士奶酪模型”（Swiss cheese model）。这是安全工程领域的一个经典概念。想象每一层防御机制就像是一片瑞士奶酪，每一片奶酪上都有孔洞和漏洞，问题可能会从中穿透过去。但是，如果你叠加了足够多的奶酪片，这些孔洞就不会重叠对齐。这样一来，即使穿透了其中一层，也会被下一层防御拦截下来。你的代码断言评测能够捕捉到格式错误，但会漏掉语义层面的问题；你的 LLM 裁判评测能够捕捉到推理断层，但会漏掉微妙隐蔽的幻觉；而人工审查能够发现那些细微深层的问题，却无法扩展覆盖到每一条追踪记录。在整个评估体系中，没有任何单一评测手段能够独揽全局、拦截所有错误。

<details>
<summary>Original English</summary>

**Speaker 1**: One more concept before you get started on that is the Swiss cheese model, which is a concept from safety engineering. Imagine each layer of defense as a slice of Swiss cheese. Each slice has holes, gaps where problems can slip through. But if you stack enough slices, the holes don't line up. So what gets through one layer gets caught by the next. Your code-based eval catches format issues but misses semantic problems; your LLM judge catches reasoning gaps but misses subtle hallucinations; and your human review catches the subtle stuff, but it can't scale to every trace. No single eval in that set catches everything.

</details>

<!-- chunk 6/12 -->

### 构建确定性代码评估器（Code Evals）

**Speaker 1**: 正是两者的结合才为你提供了全面的覆盖率，所以要把各层“奶酪”叠在一起。既然我们已经知道了问题出在哪里，那就开始自动化检查吧。下一步是代码评估器（Code Evals）。这里不需要配置模型，没有 API 调用，只有纯粹的 Python 代码。我们要编写一个我能想到的最简单、却又非常实用的评估器：我们的智能体原本应该分析特定的股票代码（ticker），因此我要写一个代码评估器，专门检查该股票代码是否真正出现在了最终报告中——而在我最初的演示里，好几次测试都彻底在这个问题上翻了车。对于这种检查，使用大模型作为裁判（LLM-as-a-judge）完全是大材小用。你只是在寻找特定的字符串，看它是否包含在报告中的某个位置，根本不需要让 LLM 来判定你到底有没有提及这个代码。

<details>
<summary>Original English</summary>

**Speaker 1**: And the combination is what gives you coverage, so stack the cheese. Now that we know what's wrong, let's automate the checking. The next step is code evals. This is no model configuration, no API calls, just Python. We're going to write the simplest useful eval that I can think of: our agent is supposed to analyze a specific stock ticker. What I'm going to do is write a code eval that checks whether that stock ticker actually showed up in the report, which is a test that my initial demos absolutely failed a number of times. An LLM judge would be overkill for this. You're looking for a specific string somewhere in the report. You don't need an LLM to judge whether or not you mentioned the ticker.

</details>

**Speaker 1**: 要实现这一点有两种方式。在 Arize AX 中做什么事情基本都有两种方式：一种是通过编程代码实现，另一种是通过 Notebook 中的 UI 界面操作。你可以看到编程实现的方式，而我现在在屏幕上展示的是如何通过 UI 来完成。右上角这个大按钮就是你需要的，点击“添加评估器”（Add Evaluator）。在这里我已经添加好了我的提及检查评估器（mention evaluation），但你们操作时需要点击添加评估器。

<details>
<summary>Original English</summary>

**Speaker 1**: So there's two ways to do this. There's two ways to do everything in AX: one is programmatically, and one is via the UI in the notebook. You can see the programmatic way; what I'm going to show you on screen is how you do it in the UI. So this big button in the top right is what you want: you want to add evaluator. In this case, I've already added my mention evaluator, but you will want to add an evaluator.

</details>

**Speaker 2**: 点击后就会进入当前这个界面。

<details>
<summary>Original English</summary>

**Speaker 2**: Which will give you this screen here.

</details>

**Speaker 1**: 你在 Notebook 里基本能看到一些 Python 代码。我在 Notebook 中已经提供了相应的 Python 代码，你可以用它来跑代码版本，也可以在 UI 界面中使用。这是一个非常简单的 Python 函数，它返回一个评估结果（Evaluation Result），其结构和形态跟我之前给你们展示过的评估结果完全一样，包含一个标签（label）和一个分数（score）。一旦你写好了代码评估器的逻辑，它就会有一些输入参数。在当前这个例子中，我把参数命名为 `query` 和 `report`。接着你必须告诉 AX，在你的调用链路追踪（Trace）中，哪些变量分别对应这两个参数。

<details>
<summary>Original English</summary>

**Speaker 1**: Are you going to see basically some Python in the notebook? I've given you the Python that you can use to either do your programmatic version or your version in the UI. This is a very simple Python function which returns an evaluation result, which looks exactly like those evaluation results that I showed you earlier: it has a label, it has a score. So once you've written what your code evaluator does, you're going to have parameters to your code evaluator. In this case, I've called them `query` and `report`, and you're going to have to tell AX which variables in your trace are those variables.

</details>

**Speaker 1**: 这里提供了一个非常有趣的单链路追踪界面（Single Trace UI），你可以查看单条 Trace。你完全可以直接点击输出结果中你想要作为该变量的具体内容，告诉它：“好，这个字段应该映射为 query，那个字段应该映射为 report。”这样字段映射就完成了。另外，你应该把评估器的评估粒度改为在整个 Trace（调用链路）级别运行，而不是只针对单个 Span（执行跨度）。只有这样才能调出这个配置界面。完成这些之后，你需要将你的代码评估器保存到我们的评估器仓库（Evaluator Hub），然后点击保存来保存这次评估任务。假设大家都已经搞定了这步——

<details>
<summary>Original English</summary>

**Speaker 1**: So there's this extremely fun UI, the single trace UI, where you look at a single trace. And you can literally just click the specific thing in your output that you want to be that variable. And you tell it, okay, that one should be the query, and that one should be the report, and then it's mapped. You should also be changing your evaluator to work on a trace as opposed to a span; that is what gives you that UI. Once you've done that, you need to save your code evaluator to our evaluator hub, and then you hit save to save the evaluation. So assuming you've done that, yeah—

</details>

### 代码评估器的运行机制与原则

**Speaker 0**: 你们光斯东会长，我也在这等着光光赛我来做产品，然后他他就是就是我们上班 sure。

<details>
<summary>Original English</summary>

**Speaker 0**: 你们光斯东会长，我也在这等着光光赛我来做产品，然后他他就是就是我们上班 sure。

</details>

**Speaker 1**: 刚才有人询问关于代码评估器具体如何工作的更多细节。代码评估器是完全确定性的函数。你只是接收输入和输出，然后根据某种对“好”的定义来判定：“这个输出符合标准吗？”所以在这段代码中，我用了非常简单的 Python 逻辑：找出所有大写单词，剔除我已经知道的常见缩略词，然后在剩下的单词里检查是否存在我们要找的那个代表股票代码的缩写。它做的事情仅此而已。

很多代码评估器甚至比这还要简短。比如：“输出内容是否少于或等于 500 个字符？”或者“输出内容是否为合法的 JSON 格式？”你所做的是非常简单、高度确定性的逻辑检查，目的是在你的“瑞士奶酪”模型中筑起第一道坚固的防线。

<details>
<summary>Original English</summary>

**Speaker 1**: So he asked for more detail on how code evaluators work. Code evaluators are completely deterministic functions. You are just taking input and output and saying, was this output good according to some definition of good? So in this code, I'm doing very, very simple Python: I'm saying, look for all of the words that are in capital letters, rip out the ones that are obvious acronyms that I already know, and of the remaining words, are any of them the acronym which is the stock ticker I'm looking for? That's all it's doing. Lots of code evaluators are even shorter than that: there's something like, "Is this output 500 characters long or less?", "Is this output parseable JSON?" You're doing something very simple, very deterministic for the purposes of having that first line of defense in your Swiss cheese.

</details>

**Speaker 1**: 我刚才已经讲了怎么在 UI 界面中添加评估器。在 Notebook 中，你也可以用代码方式来运行这个评估。如果你按照刚才展示的步骤操作，那就是通过 UI 来完成的指南；另一种替代方案是在开发环境中直接用代码运行它，如果你是一边听一边跟着 Notebook 演练，这种方式会更加直接。代码评估器会返回一个标签和一个分数。正如我前面所说，这里完全不需要 LLM，也不涉及 API 调用，所有计算都是瞬间完成的。

如果你好奇为什么我们要把它包裹在 `suppress_tracing` 中，那是因为评估本身是对 SDK 的一次调用，如果不加限制，它自身也会被作为 Trace 记录下来。我可不希望在我的链路追踪里再递归记录追踪本身的调用，那层级就太套娃（meta）了。因此我设置了在运行评估时抑制追踪记录。

<details>
<summary>Original English</summary>

**Speaker 1**: So I talked about how to add it already in the notebook. You can run the eval programmatically. These are the instructions on how to do it via the UI if you follow that. The alternative is to do it in the dev environment; you can run it directly, which is easier to do if you're following along in a notebook. A code evaluator returns a label and a score. Like I said, there's no LLM needed, there's no API calls, it's instantaneous. And if you're wondering why we're wrapping it in `suppress_tracing`, it's because the evaluation is itself a call to the SDK, which would then get stored as traces, and I didn't want traces of my tracing happening because that gets too meta. So I told it to suppress tracing when I'm running evaluations.

</details>

### 分析评估失败用例与代码评估的价值

**Speaker 1**: 如果你看这次代码运行的评估结果，就会发现有 12 个样本通过了，有 1 个失败了——亚马逊（Amazon）的股票代码丢失了。出错的那个具体 Trace 很有意思。你们会记得我之前提到过，我对亚马逊发起了两次查询：一次是询问公司的整体盈利能力，另一次则是询问 AWS 的盈利能力。如果你点击深入查看链路追踪详情（我现在可以尝试点进去看），你就会发现，那个被问及 AWS 的任务所生成的报告，通篇只讨论了 AWS 这一单一业务分支，而完全没有提及亚马逊整体。因此它彻底遗漏了亚马逊的股票代码，只字不差地全在谈 AWS。

这是一个非常隐蔽的失败案例：智能体确实进行了深入研究，找到了大量关于亚马逊内部正在发生的事情，但它并没有把亚马逊作为一家整体公司来思考，而仅仅局限于 AWS，因为我当时给它的补充提示是“我还想了解 AWS 的盈利能力”。回到 AX 平台中查看这些结果，它们会作为标注（annotations）显示在我们每条 Trace 的旁边。

<details>
<summary>Original English</summary>

**Speaker 1**: If you look at this programmatic run, you'll see that 12 passed and 1 failed: there was a missing ticker for Amazon. The specific trace that went wrong—you'll notice I told you earlier that I made two queries to Amazon: one where I asked about profitability, and one where I asked about AWS profitability. If you click into the traces, which I could attempt now, you'll see that the report that asked about AWS wrote a report that was entirely about AWS only, only about the AWS branch of Amazon rather than all of Amazon. And so it failed to mention the Amazon stock ticker entirely and talked only about AWS. So it's a really subtle failure, because it did open research, found out a whole bunch of stuff about what was happening at Amazon; it just didn't think about what was happening about Amazon as a company, only about AWS, because I gave it that extra prompt like, "I also want to know about AWS profitability." So looking at those results back in AX, they show as annotations next to our traces.

</details>

**Speaker 1**: 你可以点击进入这里的任何一条链路，就能看到评估信息。我已经运行了比你们目前多得多的评估，但你们可以看到，“股票代码提及评估”（mentioned ticker evaluation）已经在相应的 Span 上运行了。它在给定的 Span 上顺利执行，标记为通过（pass），并给出了 1 分的得分。Notebook 里面包含一个名为 `log_eval_to_ax` 的辅助小工具，它在后台帮你们完成了上报工作：它把离线运行的 Span 以及离线执行的测试结果提取出来，并自动推回同步到 AX 平台中。这样一来，每一个评估都拥有了一个股票代码提及指标，你可以随时查看、按其筛选，并快速定位出那些失败的样本。

为什么这件事情如此重要？因为它是你的第一道防线。试想一下，如果用户明明询问的是特斯拉（Tesla），你的金融分析智能体却写出了一篇关于微软（Microsoft）的极其华丽漂亮的报告——这在我构建这个系统的过程中确实发生过——那么此时你的智能体语言表达有多么辞藻华丽、逻辑流畅都已经毫无意义了，因为答案从根本上就是错的。而你仅仅用五行 Python 代码就能够逮住这类错误。股票代码检查虽然抓到的都是非常低级的错误，但它能以极低的成本将它们捕获，这就是它的价值所在。

<details>
<summary>Original English</summary>

**Speaker 1**: So you can click into any one of these traces, and you'll see evaluations. I've run a lot more evaluations than you have so far, but you can see my mentioned ticker evaluation has run with the span. It's run over the span, it has hit a pass, and it's given a score of 1. The notebook has a little helper called `log_eval_to_ax` which is doing that work for you: it takes the spans that it ran offline and the tests that it ran offline and pushes them back to AX for you. So now every eval has a mentioned ticker evaluation that you can look at, filter by, and look for the failing ones. So why does this matter? Because it is your first line of defense. If your financial analyst agent writes a beautiful report about Microsoft when the user asked about Tesla—which is a thing that actually happened to me when I was building this—no amount of eloquence from your agent matters, because the answer is wrong. So you can catch this with five lines of Python. The ticker check catches really basic failures, but it catches them really cheaply. That is why it is important.

</details>

**Speaker 1**: 代码评估绝不仅仅是玩具示例。在实际场景中，你通常必须确认输出是否为标准 JSON、长度是否在合理范围内，或者是否规避了像“作为一个人工智能语言模型”这样的禁用短语。这些都是关乎生产环境稳定性的关键检查。而且，代码评估并不局限于简单的字符串匹配操作。“代码评估”的核心含义是评估打分的逻辑是确定性的，但它的执行过程完全可以很复杂：它可以替你查询数据库，也可以调用外部受信任的 API 获取真实的实时股票价格，以验证模型是否在股票价格上产生了幻觉。任何只要针对相同输入始终给出相同评判答案的逻辑，都可以作为一个代码评估器。

这里有一个非常重要的原则：**评估智能体最终产出的成果，而不是评估它达成目标所走的路径**。我前面提到过，人们经常会有一种冲动，非要去检查智能体是否严格遵循了某套特定的执行步骤——比如它是不是先调用了工具 A，紧接着按顺序调用了工具 B。但在工程实践中，同行们发现这种方式太僵化了。智能体经常会找到评估设计者未曾预料到的有效途径。如果你去评估执行路径，你实际上是在惩罚它的创造力与灵活性。相反，你应该评估产出的最终内容：输出是否包含了正确的信息？最终状态是否符合你的预期？我们的股票代码检查根本不在乎智能体到底通过什么手段搜集到了数据，它只检查输出结果中是否包含了该股票代码。对于绝大多数代码评估而言，这就是恰到好处的抽象层级。

<details>
<summary>Original English</summary>

**Speaker 1**: Code evals aren't just toy examples. Often you're going to want to know that your output is JSON, or that it has a certain length, or you're going to want to avoid forbidden phrases like "as an AI language model." And those are production-critical checks. A code eval doesn't have to be a simple string operation. Code eval means the grading logic is deterministic, but it can do complicated things: it can query a database for you; it could hit an API and get the actual stock price to make sure that it wasn't hallucinating a stock price. Anything where the grading always gives the same answer for the same input can be a code evaluator. One important principle is to grade what the agent produced and not the path that it took. I referred to this earlier: there's a common urge to check that the agent followed a specific sequence of steps: did it call this tool first, and then that tool in that order? Practitioners have found this to be in practice too rigid. Agents regularly find valid approaches that the eval designer didn't anticipate. So if you grade the path, you punish creativity. Instead, grade what the agent produced: did the output have the right information? Did the final state match what you wanted? Our ticker check doesn't care how the agent found the data; it just checks: is the ticker in the output? That is the right level of abstraction for most code evals.

</details>

### 迈向大模型裁判评估（LLM-as-a-Judge）

**Speaker 0**: 嗯。

<details>
<summary>Original English</summary>

**Speaker 0**: 嗯。

</details>

**Speaker 1**: 那么现在，我们来构建 LLM 评估器。这正是事情开始变得更有意思的地方。代码可以检查股票代码是否出现，但代码无法判断分析报告的质量高低：财务数据是否准确？报告内容是否完整？给出的投资建议是否推理得当？这些全都是语义层面的问题。面对语义层面的问题，你就必须引入一个智能裁判。

每一个“LLM 裁判”（LLM-as-a-judge）都由三个核心要素构成：
1. **裁判模型（Judge Model）**：负责实际执行打分评估的底层大语言模型。
2. **提示词模板（Prompt Template）**：正如我之前提到的，这也叫评分标准或准则（Rubric），即裁判所遵循的准绳，定义了究竟何为“优质”的规则集合。
3. **评估数据（Data）**：也就是被送入评估的具体用例样本。

Arize AX 将这三者完全解耦拆分，这意味着你可以自由混搭：你可以用不同的裁判模型去测试同一套评分准则，也可以让同一个裁判模型套用不同的准则。这种设计天然就是高度模块化的。好消息是，AX 开箱即自带了大量内置的通用评估器，你甚至不需要自己编写。在大部分 AI 应用中，有相当一部分评估类型具有普适性，因此我们已经提前为这些场景写好了提示词，免去了你重复造轮子的麻烦。举个例子，“正确性”（Correctness）评估器会检查回复内容是否属实准确；而“忠实度”（Faithfulness）评估器则会检查……

<details>
<summary>Original English</summary>

**Speaker 1**: So now let's get to building LLM evals. This is where it begins to get more interesting. Code can check whether the ticker appears, but it can't check whether the analysis is good: is the financial data accurate? Is the report complete? Are the recommendations well-reasoned? These are semantic questions, and for semantic questions you need a judge. Every LLM-as-a-judge has three parts: it has a judge model, which is the LLM that is doing the grading for you; it has a prompt template, which as I mentioned is also called the rubric, which is the criteria that the judge applies, the rules of what defines good; and it has the data, which is the examples being evaluated. AX keeps these three things separate, which means that you can mix and match: you can try the same criteria with different judge models, the same judge model with different criteria. It is modular by design. The good news is that AX ships with a bunch of built-in evals, so you don't have to write your own. There are a bunch of types of evals that are often going to apply to most AI applications, so we've already written the prompts for those, and you don't have to write them yourself. Correctness, for instance, checks whether a response is actually accurate; faithfulness checks—

</details>

<!-- chunk 7/12 -->

### 内置评估指标与“正确性”评估的局限

**Speaker 1**: 评估内容包括回答是否立足于源素材，并且还提供了用于工具选择的评估指标：智能体是否挑选了正确的工具？工具调用是否正确？传递给该工具的参数是否正确？此外还包括文档相关性、拒绝检测等诸多内容，你在智能体应用中想要检查的大多数指标，框架基本上都开箱即用。

<details>
<summary>Original English</summary>

**Speaker 1**: whether the response stays grounded in the source material, and there are evals for tool selection. Did the agent pick the right tool and tool invocation? Did it pass the right arguments to that tool? Stuff like document relevance, refusal detection, many of the things that you'd want to check in an agentic application come out of the box.

</details>

**Speaker 1**: 我们首先要运行的是一个“正确性”（Correctness）评估。先剧透一下：它根本行不通。设置其实非常简单：我们给它分配一个大语言模型（LLM），这里我选了 Anthropic 的 Claude 3.5 Sonnet，因为它比实际执行任务的 Haiku 表现更好。你通常会希望挑选一个规模更大、速度较慢的模型来充当裁判。然后我直接把大模型传给正确性评估器，就在这里运行它。

<details>
<summary>Original English</summary>

**Speaker 1**: So the first eval that we're going to run is a correctness eval. And spoiler alert: it's not going to work. Setting it up is very easy. We give it an LLM; in this case I've chosen the Anthropic LLM Sonnet 3.5, because it is better than Haiku, which is the thing that is doing the work. You often want to pick a bigger, slower model to be your judge. And then I've just given correctness evaluation the LLM and run it right here.

</details>

**Speaker 0**: 嗯，就像我说的那样。

<details>
<summary>Original English</summary>

**Speaker 0**: Like I said,

</details>

**Speaker 1**: 一旦我们通过 `evaluate_dataframe` 运行了这项评估，并且开启了追踪抑制（suppress tracing）——这样我们的评估过程就不会向 Arize/Phoenix 发送大量多余的 trace。它会为我们生成这样一份输出，也就是一堆评估结果行。这些数据可读性并不是很好，这也是为什么你需要一个 UI 来查看它们。裁判模型会根据评分标准（rubric）读取每次运行的重要输出，然后我们可以看到，每一个样本的得分全部都是零分。

<details>
<summary>Original English</summary>

**Speaker 1**: once we've run the evaluation with evaluate dataframe, we've also turned on suppress tracing, so our evaluation doesn't send a bunch of extra traces to Phoenix. It gives us this output, which is a bunch of evaluation rows. They are not very readable. This is why you need a UI to look at them. The judge reads the important output from each span against the rubric, and we can see that every score is zero.

</details>

**Speaker 0**: 如果我横向滚动查看状态……

<details>
<summary>Original English</summary>

**Speaker 0**: If I scroll across status,

</details>

**Speaker 1**: 状态显示为已完成，评估名称为 correctness，得分是零分。它之所以全打零分，是因为“正确性”评估是依据大模型自身对“什么是正确、什么是真实”的定义来进行评判的，这意味着它完全依赖该大模型原有的预训练数据。而在我们这个智能体中，它执行了大量的实时网络搜索来获取当前的股票价格和最新的财务信息，也就是说智能体讨论的是发生在 2026 年的事情。然而负责裁判的大模型，其训练知识早在今年一月份就已经截止了。

<details>
<summary>Original English</summary>

**Speaker 1**: completed, name: correctness, score: zero. The reason it's doing this is because correctness is judging against the LLM's definition of what is correct and what is true, which means that it is relying on the LLM's training data. What we're doing in this agent is a whole bunch of live web search to get current stock prices and up-to-date financial information, which means the agent is talking about things that happened in 2026. But the LLM that's doing the judging only has information that stops in January.

</details>

**Speaker 1**: 因此，如果你在 UI 内部阅读我们这次正确性评估的具体解释，你可以滚动到评估详情，查看 correctness。你可以看到它判定为不正确。我就不让你去读那大段密密麻麻的文本了，裁判模型核心抱怨的就是：这里充斥着大量来自未来的内容，它根本不可能知晓。所以我们这里的正确性评估彻底失效了。但这并不是你想要达到的测试目的。

<details>
<summary>Original English</summary>

**Speaker 1**: So if you read the explanations of our correctness eval inside of Phoenix, you can scroll to evaluations, you can look at correctness, you can see that it's incorrect. I'll save you a bunch of reading of a very densely packed explanation: what it is doing is complaining that there's a bunch of stuff that comes from the future that it couldn't possibly know. So our correctness eval here has completely failed. This is not what you wanted to do.

</details>

### 转向“忠实度”评估：基于上下文的公平裁判

**Speaker 1**: 因此，我们将改用“忠实度”（Faithfulness）评估。忠实度评估对我们的应用场景来说是一个好得多的指标，因为在忠实度测试中，裁判模型实际上拥有了上下文上下文背景。在忠实度评估中，你将智能体赖以生成内容的背景信息直接提供给担任裁判的大模型，然后问它：“基于我的智能体所收集到的同一批信息，它写出的报告质量合格吗？”通过这种方式，双方处于同一个公平的竞争环境。它们拥有相同的信息量，这样你那个运算更慢、更复杂的裁判智能体就可以评估你那个轻量、快速的 Haiku 智能体是否把工作做好了。

<details>
<summary>Original English</summary>

**Speaker 1**: So instead, we are going to use a faithfulness eval. Faithfulness is a better eval for our use case because the judge actually has context. In faithfulness, you give the LLM as a judge the information that it is being based on and then say, "Based on the same information that my agent collected, did it do a good job of writing the report?" This way they are on a level playing field. They both have the same amount of information, and your slow, complicated judge agent can judge whether your quick, fast Haiku agent was doing a good job.

</details>

**Speaker 1**: 那么我们来看看忠实度评估。就像其他所有指标一样，这些评估既可以在线运行，也可以离线运行。系统提供了一个内置的忠实度评估器——虽然不在当前这个视图里，但确实有一个内置的忠实度评估组件。你可以把它调出来，把你的输入、输出以及上下文信息再次传给它。你也可以完全在代码中实现这一点。如果你在使用技能库（skills），很可能发生的情况是：你的流程会倾向于说“我不打算用 UI，我要在代码里跑”，这也是为什么我在这里展示代码写法。

<details>
<summary>Original English</summary>

**Speaker 1**: So let's look at the faithfulness evals. Just like everything else, these can be done online as well as offline. So there is a faithfulness built-in evaluator, which isn't in this view, there is a faithfulness built-in evaluator. You can pull up, and you can give your input, output, and your context to it. Again, you can do this in code as well. And if you're using the skills, this is probably what's going to happen: your skills will say, "Oh, I'm not going to use the UI, I'm going to use the code," which is why I show it here.

</details>

**Speaker 1**: 我们要做的第一件事，就是从执行追踪（traces）中提取出调研上下文。大家应该还记得，我们采用的是一个两阶段的流程。因此，我拿出了第一步（即负责调研的步骤）的输出结果，并将其作为裁判开展工作所依据的上下文，附加到了我所有的 spans 上。接着，我运行忠实度评估器。在这里你可以看到带有上下文的 spans（spans with context）。这些就是我刚刚从系统中提取出来的同一批 spans，我在数据列层面上把所有上下文都挂载了上去。

<details>
<summary>Original English</summary>

**Speaker 1**: So the first thing we do is we extract the research context from the traces. As you remember, we do a two-step process. So I take the output from the first step, where it does the research, and I attach that to all my spans as the context for the judge to work on. And then I run the faithfulness evaluator. So here you can see spans with context. These are the same spans that I just pulled out of Phoenix; I attached at the column level all of my context.

</details>

**Speaker 1**: 然后，我针对这些带有上下文的 spans 调用了 `evaluate_dataframe`，并传入了忠实度评估器。这个评估器是我在这里实例化的，就像我刚才实例化正确性评估器一样。这为我们带来了有趣得多的数据：结果显示不忠实（unfaithful）的有 7 条，忠实（faithful）的有 6 条。也就是说，大约有一半的时间，我这个非常简易的研报智能体在产生幻觉。根据 Sonnet 的判定，它编造出了源数据中根本不存在的内容。

<details>
<summary>Original English</summary>

**Speaker 1**: And then I called evaluate dataframe with those spans, and I gave it the faithfulness evaluator, which I instantiated here, just as I instantiated the correctness evaluator. This gives us much more interesting data. This gives us unfaithful: 7, and faithful: 6. So roughly half the time, my very simple report is hallucinating. It is coming up with things that were not in the source data according to Sonnet.

</details>

**Speaker 1**: 这就是一个非常有价值的评估。这是一个我们在半数情况下都会失败的评估。这是一项能力评估，让我们有了明确的爬坡目标，可以去优化提示词，让智能体在撰写立足于事实依据的报告上表现得更好。这正是你所需要的那种评估指标。至此，我们介绍了两个内置评估器，它们给出了截然不同的信号。这里包含一个至关重要的教训：正确性评估给出了 0/13 的全挂结果，而忠实度评估则告诉我们大约一半的时间报告没有立足于来源数据。区别并不在于哪个评估指标更好，而在于应用场景。

<details>
<summary>Original English</summary>

**Speaker 1**: And that is this is a useful eval. This is an eval we are failing half the time. This is a capability eval where we can climb the hill, modify our prompt, and get it better at writing a grounded report. This is exactly the kind of eval that you want. So that's two built-in evals yielding two very different signals. There's a really important lesson here, which is correctness gave us zero out of 13, and faithfulness told us that reports aren't grounded in their sources roughly half the time. The difference isn't that one eval is better than the other; the difference is the use case.

</details>

### 从内置指标走向自定义业务评分标准

**Speaker 1**: 在很多场景下，我之前展示给你们看的正确性评估表现得完全没有问题；但在我们这个需要实时调研的具体用例中，它就是不适用。因此，弄清楚你在评估中真正想要问的问题至关重要。内置评估是你的起跑线，它们无需任何提示词工程就能为你提供立竿见影的反馈信号。但是，即便是像忠实度这样优秀的内置指标，仍然有很多东西是它无法检验的。

<details>
<summary>Original English</summary>

**Speaker 1**: So there's lots of use cases where that correctness eval that I showed you earlier works just fine for some use cases; it's just not in this specific use case where we're doing live real-time research. So it's important to know the question that you're actually asking. Built-in evals are your starting point; they give you an immediate signal without any prompt engineering. But even with a good built-in like faithfulness, there are a bunch of things that it can't check.

</details>

**Speaker 1**: 我们的财务分析智能体应该产出具有可操作性的投资建议，而不应该只是对数据进行简单摘要。也就是说，它不能仅仅是给你一份财务报告，而是要告诉你面对这份财务报告该采取什么行动：我究竟该买入、卖出还是持有？没有任何开箱即用的内置模板会去检查这一点，现有指标体系无法覆盖所有的具体业务场景。你必须构建专门针对你自身业务领域的自定义评估器，来检验内容是否具备可操作性（actionability）。如果你要编写真正有深度的评估，你绝对必须去编写自定义评估标准，明确定义那些通用指标未曾考虑到的“优秀标准”。

<details>
<summary>Original English</summary>

**Speaker 1**: Our financial analyst should produce actionable recommendations; it shouldn't just summarize data. So not just, you know, give you a financial report, but tell you what to do with the financial report: should I buy, sell, or hold? No built-in template checks for that. This suite does not cover every single use case. You have to build a specific eval that checks for actionability. You have to build a custom eval that is about your domain. If you are writing real evals, you are absolutely going to have to write a custom eval with a definition of good that we didn't think of.

</details>

### 构建高质量评估评分标准的四个要素

**Speaker 1**: 这就引出了我们的下一步：编写自定义评估评分标准（custom eval rubric）。通过这一步，你才能让评估指标真正切合你的具体应用场景。编写一个出色的评估标准是一件复杂的事情，因此我打算花一点时间来谈谈怎样才算一个优秀的评估标准。针对自定义评分标准，我们推荐包含四个核心组成部分：第一是定义裁判的角色；第二是明确列出具体的通过与不通过标准；第三是使用 XML 标签对数据进行标记标注；第四是在提示词之外独立定义输出选项。

<details>
<summary>Original English</summary>

**Speaker 1**: So that brings us to the next step, which is writing a custom eval rubric. This is where you make evals truly specific to your application, and writing a good eval is complicated. So I'm going to spend a little time talking about what makes a good eval rubric. We recommend four parts of a custom rubric: the first is to define the judge's role; you should spell out explicit pass and fail criteria; you should label the data with XML tags; and you should define the output choices outside the prompt itself.

</details>

**Speaker 1**: 在这四点之上，我还想额外补充一条，这一条在实际从业人员当中其实颇具争议：我个人倾向于在标准中包含优秀和劣质输出的示例样本（few-shot examples）。部分从业人员认为，包含具体示例会导致你的评估发生过拟合。不过，让我们先把这几个要素逐一梳理一遍。

<details>
<summary>Original English</summary>

**Speaker 1**: I'm going to add one more thing on top of those, which is actually kind of controversial amongst practitioners, which is I tend to include examples of good and bad output. Some practitioners believe that including examples will make your eval overfit. But let's walk through all of those.

</details>

**Speaker 1**: 第一部分是定义角色。大家会注意到这样一种如今已经司空见惯的陈词滥调设定：“你是一名专业的财务分析评估专家”。测试表明，这类角色设定对评估是否奏效产生的影响微乎其微。真正重要的，是向它提供它所审视内容的上下文背景：“你正在审视一份财务报告，而我期望得到的是深度的财务分析。”这些才是你通过提示词赋予大语言模型的关键上下文信息。与此同时，你也要向它传达核心诉求：你期望得到的是具备实操指导意义的成果。

<details>
<summary>Original English</summary>

**Speaker 1**: So the first part is defining the role. You'll notice what is by now a tired trope, which is "You are an expert financial analyst evaluator." That is not the important part; tests show it makes a very small difference to whether an eval works. The important thing is to give it the context of what it is looking at: "You are looking at a financial report, and what I am expecting is financial analysis." Those are the important pieces of context that you are giving the LLM there. You're also telling it that what you want is something actionable.

</details>

**Speaker 1**: 接下来进入第二部分。这正是大多数人投入不足的地方：千万不要泛泛地写“好的回答应当……”，因为那只是一种愿景，根本不是可判定的标准。写成“好的回答应当既有帮助又准确”，听起来你好像补充了更多细节，但你本质上依然非常模糊，因为在模型眼里，“有帮助”和“准确”没有任何明确的界定。相反，你应该一五一十地列出到底什么构成了报告的“可操作性”，列出哪些特征算具备可操作性、哪些算不具备可操作性。

<details>
<summary>Original English</summary>

**Speaker 1**: So that brings us to part two. This is where most people under-invest: don't say "a good response," because that is an aspiration, that is not a criterion. "A good response is helpful and accurate" sounds like you're adding more detail, but you're still being just as vague, because "helpful" and "accurate" don't have any meaning as far as the LLM is concerned. Instead, you should be listing exactly what makes a report actionable: exactly what makes it actionable and not actionable.

</details>

**Speaker 1**: 每一项标准都必须是具体且可被观测到的（specific and observable），必须达到这种程度：如果换作一个真人来看这份报告，他能够明确判断该特征是否存在，并能毫不犹豫地给出“是”或“否”的回答。例如：“包含具体的行动建议”，这绝对是一个你可以明确回答“是”或“否”的指标；又如：“包含前瞻性分析，而非仅有历史数据”，这也是一个非黑即白、界限分明的评判点。

<details>
<summary>Original English</summary>

**Speaker 1**: Every criterion should be specific and observable—something that if you were a human looking at this report, you'd be able to know whether or not it was there, and you'd be able to say yes or no. So "contains specific recommendations"—that's something you can definitely say yes or no to. "Includes forward-looking analysis, not just historical data"—that's a clear distinction that you can say yes or no to as well.

</details>

**Speaker 1**: 最为关键的是，这里的每一条评判标准，都必须对应我们在前期错误分析中真实发现的问题。当我们在阅读智能体生成的研报、审查系统 traces 时（至少在我阅读 traces 时），我们切切实实观察到了这些报告在哪些具体维度上出现了偏差。这绝非凭空捏造。错误分析才是指引你确立正确标准的源泉；你不可能凭空凭直觉编造出这些标准，因为你根本想不到。这些数据完全来自于你一行行去读 traces 并恍然大悟：“原来它在这里遗漏了这一点，我的分析表明它犯了这处特定错误。”明确具体的标准能够带来一致稳定的判断，而模糊宽泛的标准只会让模型像抛硬币一样随机下定论。

<details>
<summary>Original English</summary>

**Speaker 1**: And the important thing here is that each of these criteria maps to something we saw in our analysis. When we were reading the reports, we actually observed when we read our traces—or at least when I read our traces—that these are ways that these reports are going wrong, specifically. That is not a coincidence. Error analysis is what tells you what criteria are right. You don't come up with them from whole cloth because it's not going to occur to you; where you get that data from is from reading your traces and going, "Oh, it didn't do that. My analysis showed it does this specific wrong thing." So specific criteria produce consistent judgments, while vague criteria produce coin flips.

</details>

**Speaker 1**: 评分标准的第三个要素，是用 XML 标签对数据进行结构化标记。特别是当你使用 Anthropic 的模型时，Anthropic 极其推崇 XML 结构，能够非常轻松地理解其中的层级关系。你的评分标准中通常包含变量，例如输入内容与输出内容……

<details>
<summary>Original English</summary>

**Speaker 1**: The third thing you should do in your rubric is you should label the data with XML tags, especially if you are using Anthropic. Anthropic loves XML and finds it very easy to understand. Your rubric has variables: the input and the output,

</details>

<!-- chunk 8/12 -->

### XML 标签与示例：为裁判模型划定清晰边界

**Speaker 1**: 你需要确保大模型裁判能够明确区分你的指令、输入和输出，而 XML 标签正是实现这一点的绝佳方式。所以，可以在输入外层包裹 `<user_query>` 标签，在输出外层包裹 `<financial_report>` 标签。清晰的边界可以显著降低裁判模型混淆“问题”与“答案”的概率。

<details>
<summary>Original English</summary>

**Speaker 1**: And you want to make sure that it can tell the difference between your instructions and the input and the output, and XML tags are an excellent way to do that. So put a user query tag around the input, a financial report tag around the output. Clear boundaries reduce the chance that the judge confuses the question with the answer.

</details>

**Speaker 1**: 如果你要在提示词中包含示例（few-shot examples），用 XML 标签将这些示例标记出来尤为关键。因为如果不做明确标记，模型很可能会认为：“啊，这正是我应该输出的内容”，然后直接把示例原封不动地吐回给你。这就引出了“示例”的重要性。

<details>
<summary>Original English</summary>

**Speaker 1**: It is especially important if you're including examples to label the examples with XML tags, because otherwise it will go, "Oh, this is exactly what I'm supposed to write," and just spit out the example back to you, which brings this to the examples.

</details>

**Speaker 1**: 很多人在构建评测时会跳过示例这一步。但在我看来，这是最能提升评测质量的一环。大模型在遵循抽象指令方面表现还算可以，并且越来越强；但它们真正擅长的是模仿你给出的现成示例，并根据当前具体情境替换掉相关要素。因此，如果你给它一个完全符合你预期的报告范例，它就会严格遵循那个格式。

<details>
<summary>Original English</summary>

**Speaker 1**: This is a part a lot of people skip. In my opinion, it is the part that most improves quality. LLMs are okay at following instructions. They are increasingly good at following instructions. But what they are really good at is copying an example that you've already given them and replacing the things that are relevant to the current situation. So if you give it an example of exactly the kind of report that you're looking for, it's going to follow that format exactly.

</details>

**Speaker 1**: 这根据你所处的业务领域，可能是好事，也可能不是。如果你的示例规定得过于死板，大模型就会永远输出一模一样的报告模式，从而压缩了它的创造力空间。但另一方面，如果模型表现得过于随机、非确定性，导致输出的报告天马行空，那么给它一个具体的示例就能将其牢牢锚定在你的预期标准之内。

<details>
<summary>Original English</summary>

**Speaker 1**: That might or might not, depending on your domain, be a good idea. If your example is too rigid, then the LLM will always give the same report, and you have reduced its scope for creativity. But on the other hand, if it is being too nondeterministic and your report is being crazy, then giving it an example will ground it in what exactly you are expecting.

</details>

### 可操作性正反例对比

**Speaker 1**: 模板中包含了一个真正的正例。它面面俱到：包含营收增长百分比、市盈率（P/E ratio），用具体数字支撑指出的明确风险，并给出了具体可执行的建议。这就是所谓“具有可操作性”（actionable）的样子。与此同时，这里还有一个“不具可操作性”（non-actionable）的结果对比。

<details>
<summary>Original English</summary>

**Speaker 1**: Here's what an actual example looks like in the templates. It has everything: it has percentage revenue growth, the P/E ratio, it identifies a concrete risk with a number to back it up, and it gives a specific recommendation. That's what actionable looks like. Here is a non-actionable result.

</details>

**Speaker 1**: 这个反例本身并没有事实错误，它说的每一句话都是对的，但没有任何实际用处。它没有任何具体数据，也没有点明任何具体风险，只是泛泛地写着“投资者应考虑多重因素”。这根本称不上是建议。这样一来，裁判模型对于你所给出的标签究竟代表什么含义，就有了具象且坚实的参照。这能极大提升评测的一致性，尤其是那些原本处于模棱两可灰色地带的边缘用例（edge cases）。

<details>
<summary>Original English</summary>

**Speaker 1**: It's not wrong—everything it says is correct, but it doesn't say anything useful. It doesn't have any specific data. It doesn't have any specific risks. It just says "investors should consider various factors." That's not a recommendation. So the judge now has a concrete reference for what you actually mean by the labels that you were giving it. And this can dramatically improve consistency, especially on the edge cases where the report would have otherwise been somewhere in between.

</details>

### 评测标准设计：工具调用、二元标签与思维链

**Speaker 1**: 还有一个关键细节：当你编写评分标准（rubric）时，很容易忍不住写上一句“请输出单词 Correct 或 Incorrect”，因为你希望它这么做。但现在完全不需要这样做了。底层实际的运作机制是：我们给大模型提供了一个工具（Tool），并告诉它“当你完成评判后调用此工具”，它完成后就会带着 Correct 或 Incorrect 参数调用该工具。因此你根本不需要在提示词里规定输出格式；事实上，强行命令它输出特定字符串反而更容易混淆模型，导致你的评测运行失败。无论是在 UI 界面中还是在代码中，只需配置好预设选项（choices），让大模型自行处理即可。

<details>
<summary>Original English</summary>

**Speaker 1**: And this is an important part: it is very tempting if you're writing this rubric to say, "and now spit out the word 'correct' or 'incorrect'," because that is what you want it to do. You do not need to do that anymore. The way that actually works under the hood is we have given the LLM a tool that says, "You call this tool when you are done," and it will call that tool with correct or incorrect when you're done. So you don't need to tell it what output. And in fact, telling it to spit out a specific string output is more likely to confuse it and make your eval fail. So just in the UI set your choices, or when you are creating it programmatically set the choices and let the LLM do its thing.

</details>

**Speaker 1**: 在设计这些选项时，最好保持简洁。二元分类（Binary）是最好的方案：两个明确的标签。像 1 到 5 分这种数值打分量表看似诱人，但大模型其实很不擅长处理。3 分和 4 分之间究竟有什么区别？你必须写出一大堆细分规则大模型才能搞懂，它无法凭直觉判断。相反，如果你给它“通过/失败”（Pass/Fail），它在判定是否合格上就会表现得非常出色。如果你确实需要更多梯级，可以引入部分达标（partial result），比如用 0.5 分表示“完成了一半”，但默认情况下，优先坚持 0 或 1 的二元打分。

<details>
<summary>Original English</summary>

**Speaker 1**: When you are coming up with these choices, it is best to keep those choices simple. Binary is best: two clear labels. Numeric scales like a scale of one to five, they are tempting, but the LLMs are bad at them. What is the difference between a three and a four? You would have to write a whole bunch of rules for the LLM to know that; it doesn't know that automatically. Whereas you can give it a pass/fail, and it will be pretty good at deciding what is a pass and what is a fail. So if you really need more categories, you can do like a partial result; you can say a 0.5 score where it did a half-assed job. But by default, go for a 0 or 1.

</details>

**Speaker 1**: 另一个实用的建议是为裁判模型引入思维链（Chain of Thought）：要求裁判在给出最终分数前先进行推理，先陈述并解释其思考过程。这在可衡量的指标上显著提升了准确率。当裁判模型必须先阐明为什么某项内容具有或不具有可操作性、或者为什么正确或不正确时，相比未经思考直接选择标签，它犯的错误要少得多。这种理由阐述对你审查很有帮助，但更重要的是它能帮助裁判本身理清逻辑——这是大模型身上很奇妙的特性之一。

<details>
<summary>Original English</summary>

**Speaker 1**: One more practical tip is chain of thought for judges: ask the judge to reason before it scores and have it explain its thinking first. This measurably improves accuracy. When the judge has to articulate why something is actionable or not, or why it is correct or not, it makes fewer mistakes than when it just picks a label without thinking first. This explanation is also very helpful for you, but it also helps the judge think better—just one of those weird things about LLMs.

</details>

### 在 UI 与代码中配置在线评估器

**Speaker 1**: 如果你跟着一起写代码，现在可以打开你的“可操作性评估模板”（actionability template）了。它包含了我们刚才讨论的全部示例与全部指令。你可以看看能否做得比我更好——你能否通过调整这个评测模板，一发入魂直接拿到完美的评测结果？就像 Arize / Phoenix 中的所有功能一样，这也可以通过图形界面来完成：你可以创建一个在线评估器（online evaluator），新建一个 LLM-as-a-judge。这里我已经建好了我的可操作性评估器，里面的文本内容与我刚才在 Notebook 里给你们展示的完全一致。

<details>
<summary>Original English</summary>

**Speaker 1**: So if you are coding along, now is the time to find your actionability template. This contains all of the examples, all of the instructions that I was just talking about. Can you do better than me? Can you one-shot your way to a perfect eval by modifying this eval template? As with all things in Arize, you can do this via the UI as well. So you can create an online evaluator, and you can create a new LLM-as-a-judge. In this case, I've already got it: my actionability evaluator, which has literally exactly the same text that I just showed you in the notebook.

</details>

**Speaker 1**: 和之前一样，我需要选择一个 Trace 作用域。因为这是一个裁判大模型，我需要在 UI 中为它配置底层调用的模型，也就是说你需要再次传入你的 Anthropic API Key。我通过单条 Trace 方式指定了输入和输出映射，然后保存。在线评估器的一大特性是：你可以将其配置为持续针对新进来的追踪数据运行。这是你在生产环境中几乎必然会做的事情。

<details>
<summary>Original English</summary>

**Speaker 1**: And as before, I had to pick a trace scope. And because it's an LLM-as-a-judge, I had to set up a template—sorry, I had to set up an LLM for it to use in the UI, which means that you need to give it your Anthropic API key again. And I picked my inputs and outputs via the single trace method, and then I saved it. One of the things that you can do with online evals is you can set them to run continuously against new incoming traces. This is something you will almost certainly do in production.

</details>

**Speaker 1**: 如果你的评测成本昂贵或者流量极大，你肯定不想对所有流量全量评测。你可以将其配置为仅对一定百分比的流量进行评分，这就是采样率（sampling rates）。你可以设置比如只评估 1% 的生产流量，这样就能在不超出预算的前提下，持续获取大量宝贵的评测数据。现在回到代码实现版本。

<details>
<summary>Original English</summary>

**Speaker 1**: And if your evals are expensive or you have a whole lot of traffic, you won't want to do it on all of your traffic. You can set it to rate only a percentage—that's the sampling rates. You can say, you know, "just look at one percent of my traffic," and that will still give you a whole bunch of eval data without breaking your budget. So back to the code version.

</details>

### 代码端执行与多维度评测结果筛选

**Speaker 0**: 在代码中将其连接起来，与我们之前配置其他评估器一模一样。我们创建了一个分类评估器（classification evaluator），命名为 `actionability`，配置了一个大模型，传入了刚才展示的提示词模板，并设定了选项。这就是用编程式的方法来实现我们在 UI 中所做的操作。打分选项是 actionable 与 not_actionable，对应得分 1 或 0。

<details>
<summary>Original English</summary>

**Speaker 0**: Wiring it up is just like wiring up the other evaluators that we've given. We've created a classification evaluator, we've given it a name `actionability`, we've given it an LLM, we've given it the template that I just showed you, and we've given it those choices. This is us programmatically doing what we would have done in the UI: your choices are actionable or not actionable, scores 1 or 0.

</details>

**Speaker 0**: 我们调用 `evaluate_dataframe`，它会产出评测数据（前面我已经提前运行过了，所以刚才跳过了这一步）。你可以看到可操作性的评定结果。如果我们切换到 Evaluations 标签页并向下滚动到 actionability，就会看到模型生成的精彩解释，详尽陈述了为什么该报告具有或不具有可操作性。很多报告都被评为了 actionable，但也有几篇被评为 not actionable。这太棒了，因为这意味着我们找到了系统能力边界，找到了可以进一步优化的攀登目标。

<details>
<summary>Original English</summary>

**Speaker 0**: We ran `evaluate_dataframe`; that gives us the data that I was skipping over because it was already run earlier. So you can see actionability: actionable. If we look at our evaluations tab, we can scroll down to our actionability, and we get this really great explanation about why the report is actionable or not actionable. Lots of our reports scored actionable, but several are not, which is awesome, because it means that we have, again, a capability baseline and a hill that we can climb.

</details>

**Speaker 0**: 在 Notebook 中，你可以把评测结果记录回 Phoenix / Arize；如果你是在 UI 里运行在线评测，结果就像我们刚才看到的那样，已经直接呈现在界面中了。现在在平台中可以看到，每一个 Span 都拥有多个维度的评测分数：是否有提及股票代码（mention ticker）、正确性（correctness）、忠实度（faithfulness），以及可操作性（actionability）。你可以针对特定的评测结果进行过滤和筛选。

<details>
<summary>Original English</summary>

**Speaker 0**: In the notebook, this is where you log your results back to Phoenix, or if you've run it online in the UI, your eval results are already in the UI as we've seen. So you can see now that every span has multiple eval scores: it has mentioned ticker, it has correctness, it has faithfulness, it has actionability. And you can filter and select for specific eval results.

</details>

**Speaker 1**: 比如执行 `evals.actionability.label == 'not_actionable'`，就能把所有未通过的失败样本子集筛选出来。

<details>
<summary>Original English</summary>

**Speaker 1**: So `eval.actionability.label == 'not_actionable'`, that finds you the failing set.

</details>

**Speaker 0**: 这正是你想要定位的数据集：“评测表明我的代码在这里出现了偏差”。你可以直接把这个失败集导出为一个测试数据集，开始针对它运行新的提示词并开展对比实验，就像我们接下来要演示的那样。

<details>
<summary>Original English</summary>

**Speaker 0**: This is the set that you would like. Okay, my eval says that my code messed up here; I can turn this into a dataset, and I can start running new prompts against this. I can run experiments against this, as we're going to see.

</details>

### 评测常见反模式：提示词即代码与拒绝“上帝评估器”

**Speaker 0**: 在继续之前，我想指出几个常见的反模式（anti-patterns），这些做法会把有用的评测工具直接变成毫无意义的噪声。第一个反模式是：没有像对待代码一样对待你的评测提示词。我说的是字面意义上的“当成代码看”。大模型评测对措辞极其敏感，评测提示词中微小的词句变动，都可能导致最终的评测结果发生巨大偏差。

<details>
<summary>Original English</summary>

**Speaker 0**: Before we move on, I want to flag a few common anti-patterns that turn evals from a useful tool into noise. The first one is to treat your eval prompt like code. And I mean that literally: they're very sensitive to wording; small shifts in your eval prompt can lead to dramatic changes in your eval results.

</details>

**Speaker 0**: 因此，你应该对评测提示词进行版本控制，并使用已知标准答案的示例去测试评测本身。如果作为裁判的大模型在 40% 的样本上都与人类标注员的判定不一致，那么大概率是你的评测标准写错了。这并不意味着你的生成结果出了问题，而是你的评测逻辑本身存在缺陷。Phoenix 提供了提示词演练场（Prompt Playground），你可以在完全不改动业务代码的情况下快速迭代评测标准（rubrics），这对于评测本身的调优非常有用。

<details>
<summary>Original English</summary>

**Speaker 0**: So you should version them. You should test them on examples where you know the right answer. If the LLM-as-a-judge disagrees with your human labels on 40% of examples, then your eval is probably wrong. It's not that your results are wrong; it is that you have written the eval incorrectly. Phoenix has a prompt playground where you can iterate on rubrics without touching your code, and it's very useful for doing this kind of iteration of your eval.

</details>

**Speaker 0**: 第二个反模式是“上帝评估器”（The God Evaluator）。人们总是倾向于构建一个庞大无比的超级评估器，试图在一个提示词里同时检查所有维度：准确性、语气、完整性、合规性以及格式规范。千万不要这么做，因为它的校准过程简直是一场噩梦。

<details>
<summary>Original English</summary>

**Speaker 0**: The second anti-pattern is the "God Evaluator." It is tempting to build one big mega-evaluator that checks everything: it wants to look for accuracy, tone, completeness, policy compliance, and formatting all in a single prompt. Don't do this, because it is a nightmare to calibrate.

</details>

**Speaker 0**: 当你的“上帝评估器”给出“失败”时，到底是这五个维度里的哪一个出了问题？你无从得知。接着你可能会想：“好吧，那就让它分别输出不同标签”，随后它就会吐出十几个五花八门的标签，整个逻辑瞬间变得不可收拾地复杂。你既无法据此做准确裁决，也无法科学打分。将它们拆分成每个维度一个独立的评估器要简单得多、也容易得多。就像我们今天已经做到的：我们有一个股票代码检查器、一个忠实度评估器、一个可操作性评估器——三个独立、聚焦的评测指标，每个指标都能为你提供精准明确的诊断反馈。

<details>
<summary>Original English</summary>

**Speaker 0**: When your God Evaluator says fail, which of those five dimensions failed? You don't know. So suddenly you're like, "Oh, well, have it spit out labels," and then it's spitting out 15 different labels. Suddenly it's way too complicated. You can't judge by it, you can't score by it. It is much, much simpler and easier to split this up into one evaluator per dimension. I've already done this today: I have a ticker check, I have faithfulness, I have actionability—three separate, focused evals, and each one tells you something specific.

</details>

<!-- chunk 9/12 -->

### 组合评估与护栏指标

**Speaker 0**: 将多种评估组合起来，能为你呈现比任何单一评估都更加丰富的全局图景。如果你发现自己正在撰写一个包含六项不同响应要求的评分标准（rubric），那就停下来。那是六个评估器，而不是一个。

<details>
<summary>Original English</summary>

**Speaker 0**: The combination gives you a richer picture than any single eval ever could. If you find yourself writing a rubric that lists six different things that the response should do, then stop. That is six evaluators, not one.

</details>

**Speaker 0**: 第三点是：分清你的护栏指标（guardrails）与北极星指标（north star metrics）。有些评估是护栏，是上线阻断器（ship blockers）。例如，如果一个智能体幻觉编造了一个股票价格，这就是致命硬伤（hard fail），绝对不能据此发布上线。

<details>
<summary>Original English</summary>

**Speaker 0**: The third one is know your guard rails and your north star metrics. So evals are guard rails, they are ship blockers. If an agent hallucinates a stock price that is a hard fail, don't ship on that.

</details>

**Speaker 0**: 而另一些则是北极星指标，属于期望达成的愿景目标。例如，“始终推荐互补性投资”只是一个加分项（nice to have）。在这种情况下，它并不是决定成败的一票否决项。

<details>
<summary>Original English</summary>

**Speaker 0**: Others are north star metrics, they are aspirational. So "always recommend complimentary investments" is a nice to have. In this case, it is not a deal breaker.

</details>

**Speaker 0**: 因此，必须明确你的各项评估究竟属于哪一类，这会改变你对结果采取行动的方式。后续，它还会改变你设置生产监控（production monitors）的策略：护栏指标的退化应该在半夜触发警报并呼叫值班人员；而北极星指标的下滑，则是你在周报中查看分析的内容。

<details>
<summary>Original English</summary>

**Speaker 0**: So know which of your evals is which. It changes how you act on the results. And later, it changes how you set up your production monitors: a guard rail regression should page someone in the middle of the night; north star dip is something that you look at in a weekly report.

</details>

### 评估评估器与分类器心智模型

**Speaker 0**: 这就引出了下一个部分：你能够信任你的裁判（judges）吗？这是我们一直在探讨的问题，我之前也提及过几次。现在是时候对你的评估器本身进行评估了（evaluate your evaluator）。我们构建了一个大模型裁判（LLM judge），它告诉我们某些报告不具备可操作性（not actionable）。但我们能信任它吗？我们如何确信这个裁判是正确的？

<details>
<summary>Original English</summary>

**Speaker 0**: Which brings us to the next section, which is: can you trust your judges? This is a question we've been dancing around. I mentioned it a couple of times. It's time to evaluate your evaluator. We built an LLM judge, and it told us that some reports are not actionable. But can we trust it? How do we know that the judge is correct?

</details>

**Speaker 0**: 这里的核心心智模型是：你的裁判其实就是一个分类器（classifier）。因此，你可以把它当成分类器来对待。它接收输入——在这个案例中是一份财务报告——然后做出预测：具备可操作性或不具备可操作性。该预测可能正确，也可能错误。因此，就像评估任何分类器一样，你可以通过将其预测与真实基准（ground truth）——也就是人类裁判的判断——进行比对，来衡量其性能。你可以核查裁判的工作成果。

<details>
<summary>Original English</summary>

**Speaker 0**: The key mental model here is that your judge is a classifier, so can treat as a classifier. It takes an input, in this case a financial report, and it makes a prediction: actionable or not actionable. That prediction can be right or wrong. So just like any classifier, you can measure its performance by comparing its predictions against ground truth. In this case, a human judge, you can check the judge's homework.

</details>

### 人工标注与构建黄金数据集

**Speaker 0**: 引入人类判断的关键在于，这是一项庞大的工作量。你必须通读每一份输出，认真思考并打上标签。Arize Phoenix（AX）通过允许你直接在界面中定义标注并关联到链路跨度（spans），尽其所能提供帮助。让我向大家展示一下这是什么样子的。

<details>
<summary>Original English</summary>

**Speaker 0**: The thing about applying human judgment is that it is a ton of work. You have to read actually every single output, you have to think hard and apply a label. AX does what it can to help by letting you define annotations and attaching them to spans right in the UI. So let me show you what that looks like.

</details>

**Speaker 0**: 当你查看一个 span 时，你可以点击“标注跨度”（annotate span），并添加或移除标注类别。在这个示例中，我已经创建了一个名为 `human_actionable` 的标注。你可以将该 span 标记为具备可操作性或不具备可操作性。接着，你只需使用这些小箭头逐个翻阅所有的跟踪记录（traces），将它们逐一标记为具备或不具备可操作性，这部分我已经提前做好了。

<details>
<summary>Original English</summary>

**Speaker 0**: When you are looking at a span, you can click "annotate span", and you can add and remove annotation categories. In this case, I have already created one called `human_actionable`. And you can set this span as being actionable and not actionable. And then you can just use these little arrows to flip through all of your traces and set them as actionable or not actionable, which I have conveniently already done.

</details>

**Speaker 0**: 这类工作你可以委托给非技术背景的业务人员，这也是该界面如此设计的原因。他们只需点进去，阅读报告，勾选复选框。他们不需要编写任何代码，除了自身判断这份报告是否应被视为具有可操作性的领域专业知识外，不需要了解其他内容。我们在添加人工标注时所做的事情，本质上就是在构建一个黄金数据集（golden dataset）。

<details>
<summary>Original English</summary>

**Speaker 0**: This is the kind of work you can hand to a non-technical member of staff. That is why the UI looks like this: they can just click in, read the report and click a checkbox. They don't have to write any code. They don't need to know anything other than their domain expertise of whether or not this report should be considered actionable or not actionable. What we're doing here when we add human annotations is building a golden dataset.

</details>

**Speaker 0**: 构建黄金数据集极具价值，因为它是你衡量评估器是否切实履行其职责的基准。其构建方式与设定大模型评分标准一致：设定明确具体的标准并严格执行。不要模糊地写“这很好”或“这很差”，要具体明确。就像你要求大模型保持明确一样，说明具体在哪个细节未达标，指出原本应该出现却缺失的内容，从而消除在标注疲惫时产生偷懒敷衍的可能。

<details>
<summary>Original English</summary>

**Speaker 0**: Building a golden dataset is incredibly helpful, because it's how you measure whether an evaluator is actually doing its job. The way to do it is the same thing that the LLM did: give yourself real concrete criteria and stick to them. So don't say "this was good", "this was bad", be specific. The same way that you've told the LLM to be specific: you failed at this specific thing, this thing was supposed to be present and it wasn't, and eliminate the chance to get lazy when you get tired of labelling.

</details>

**Speaker 0**: 正如我所说，标注极其耗费时间，所以我已经提前做好了。一旦我在界面中对某些 span 进行了标注，我就可以将这些 span 重新导出到 Notebook 中。这也是 AX 的优势所在：我手工添加的人工标注，会作为列直接包含在导出的数据中。

<details>
<summary>Original English</summary>

**Speaker 0**: As I said, the labelling is extremely time consuming, so I did it already. Once I've labelled some spans in the UI, I can re-export the spans into the notebook. And this is a nice thing about AX is that the human annotations that I added by hand come back as columns in the export.

</details>

**Speaker 1**: 好的，所以我们在此筛选出仅包含我标注过的那些行。

<details>
<summary>Original English</summary>

**Speaker 1**: So we filter down to just the rows that I labelled here.

</details>

### 数据集拆分与任务明确性

**Speaker 0**: 现在我们要对比我认定为具备与不具备可操作性的结果，与裁判判定为具备与不具备可操作性的结果。不过在深入展开之前，我们先补充一点关于黄金数据集的注意事项：务必保持任务明确、无歧义。如果你的智能体持续得分 0%，这几乎总是说明任务本身有问题，或者评分标准编写有误。如果你把任务设计成只有人类才能完成的事情，或者更糟的是谁都无法真正做到的事情，那么你自然会得到零分。

<details>
<summary>Original English</summary>

**Speaker 0**: And now we're going to compare what I said was actionable and not actionable to what the judge says is actionable or not actionable. Before we do that though, a little bit more about golden datasets: keep your task unambiguous. If your agent scores zero percent consistently, that's almost always a broken task. That's almost always you've written your rubric incorrectly. If you've made your task something that only a human can do, or worse, that nobody could really do, then you're going to get a zero score.

</details>

**Speaker 0**: 因此，针对每一个任务，你都要创建一个参考基准解（reference solution）——即一个已知能通过所有评分器的正确输出。这证明了该任务是可解的。此外，你还必须进行双向测试：既要涵盖期望该行为出现的案例，也要涵盖不应出现该行为的案例。举个例子，如果你只测试“它是否搜索了网络”，最终你将得到一个无论何时都在联网搜索的智能体，即便完全没有必要；相反，你同样应该包含一个测试，验证“对于显而易见的常识答案，它是否没有进行多余的联网搜索”。

<details>
<summary>Original English</summary>

**Speaker 0**: So for each task, you create a reference solution, a known working output that passes all of your graders. This proves that the task is solvable. And you should also test in both directions: you should have cases where a behavior should occur and cases where it shouldn't. So if you test for instance "does it search the web", then you will end up with an agent that always searches the web even when it doesn't need to; whereas you should also have a test that says "did it not search the web for this very obvious answer where it didn't need to do that?"

</details>

**Speaker 0**: 如果你在生产实践中开展这项工作，应该把刚才创建的标注数据划分为开发集（development set）和测试集（test set）。你可以使用大约 70% 的标注数据来迭代你的评估指标，微调评判标准和示例，直到裁判的判定与你一致；然后保留剩余的 25% 左右的数据，用于运行裁判并验证其是否切实给出了预期分数。这样你才能确认裁判真正泛化到了新的案例，而不仅仅是过拟合（overfitting）了你提供的特定数据集。这与机器学习中的训练集/测试集拆分原理完全一致：切勿让评估器对你的黄金数据集产生过拟合。

<details>
<summary>Original English</summary>

**Speaker 0**: And if you're doing this for real, you should split your labelled data that you just created into a development set and a test set. Use maybe seventy percent of your labels to iterate on your eval, tweaking criteria, adjusting examples until the judge agrees with you. Then hold out the remaining twenty-five percent to run the judge and see that it actually gets the scores that you are expecting. That's how you know that the judge is actually generalizing to new examples instead of just fitting to the specific dataset that you gave it. This is the same principle as train-test splits in machine learning. Don't overfit your evaluator to your golden dataset.

</details>

### 元评估分析与评分标准迭代

**Speaker 0**: 现在让我们来看看可操作性裁判的表现。我对一些示例运行了裁判，它整理出了一份判定一致与不一致的列表。剧透一下：我之前是随机点击“具备”或“不具备可操作性”的，这样就会产生大量的不一致，因为实际上该模型的默认能力相当出色。这导致我们的一致率只有 46%——

<details>
<summary>Original English</summary>

**Speaker 0**: Now let's look at our actionability judge. I have run the judge on some examples, and it has come up with a list of where they agree and disagree. Spoiler alert: I just hit actionable and not actionable at random so that I would get lots of disagreement, because actually it is pretty good at this stuff. That gives us an agreement rate of forty-six percent—

</details>

**Speaker 1**: 13 次里有 6 次一致。

<details>
<summary>Original English</summary>

**Speaker 1**: Six out of thirteen times.

</details>

**Speaker 0**: 在实际工作中，这正是你需要深入排查的地方。在这个环节，你会追问：究竟是我的评分标准写错了，还是人工标注标签打错了？当裁判与你的意见不一致时，你应该仔细阅读裁判给出的原因解释，判断究竟是裁判正确还是你正确。这是元评估（meta-evaluation）中最有价值的产出。它通常能暴露出规则中的歧义，指引你修正评分标准。通过阅读分歧案例的解释并找出模糊之处，进而收紧评判标准。例如，不要只写“包含前瞻性分析”，而是写成“包含具有具体建议或指引的前瞻性分析”。这样的表述更为精准，排除了报告虽提及未来发展却未明确告知裁判该采取何种行动的情形。

<details>
<summary>Original English</summary>

**Speaker 0**: In real life, this is exactly where you dig in. This is where you would ask: is my rubric wrong, or were my human labels wrong? When the judge disagrees with you, you should read its explanation and decide whether or not the judge was right or you are right. That is the most valuable output of meta-evaluation. It usually reveals an ambiguity in the rules that you wrote. To fix the rubric, you should read the explanations on the disagreements, find the ambiguity, and tighten the criteria. So instead of just "includes forward looking analysis", I'd write "includes forward looking analysis with specific recommendations or guidance". That's more precise. It rules out the case where the report talks about the future, but never tells the judge what to do about it.

</details>

**Speaker 0**: 然后，我会在相同的示例上重新运行裁判，观察分歧是否消失。这又是另一轮评分标准的迭代。你的评估提示词本身就是一个应用程序，是另一个大模型应用程序，因此它和你的智能体一样需要测试与迭代。这就是我此前所强调的“应将评估视作代码（treat your evals as code）”的真正含义。

<details>
<summary>Original English</summary>

**Speaker 0**: Then I'd rerun the judge on the same examples and see if the disagreement goes away. This is another rubric iteration. Your eval prompt is an application, it is another LLM application, so it needs testing and iteration just like your agent does. And that is what I meant when I said that you should treat your evals as code.

</details>

### 精准率与召回率的权衡

**Speaker 0**: 现在我来简要谈谈机器学习中的精确率（precision）和召回率（recall）概念。精确率关注的是：当裁判判定报告为“不具备可操作性”时，它真正不具备可操作性的概率有多大？而召回率关注的是：在所有实际不具备可操作性的报告中，裁判成功捕捉到了多少？

<details>
<summary>Original English</summary>

**Speaker 0**: Now I'm going to talk very briefly about an ML concept called precision and recall. Precision asks: when the judge says "not actionable", how often is it really not actionable? And recall asks: of all the reports that are actually not actionable, how many did the judge catch?

</details>

**Speaker 0**: 在只有大约 12 个示例的小样本量下，这些指标数值的波动会非常大。但即便仅凭手头的这 12 个样本，你也足以看出裁判的表现是在大致合理的范围区间内，还是彻底跑偏。在绝大多数场景下，你都会倾向于优先保障召回率。这两个度量指标彼此权衡对立：如果你优先考虑召回率，就会出现假阳性（false positives），即裁判在没有任何问题的情况下误报有错。这通常远比不小心放过错误内容要好得多。

<details>
<summary>Original English</summary>

**Speaker 0**: With a tiny sample like twelve examples, these numbers are going to jump around a lot. But even with the twelve that I have, you can see whether the judge is in the right ballpark or completely off. In most scenarios, you want to prioritize recall. These two measurements are at odds with each other: if you prioritize recall, then you're going to get false positives where the judge has said something is wrong when nothing is wrong. That is much better than accidentally letting through things that are wrong.

</details>

**Speaker 0**: 然而，在某些场景的调优过程中，你可能会表示：“其实我更需要高精确率。我希望它只要判定有错就必须百分之百正确，即便遗漏一些问题我也并不介意。”确实存在需要这种特性的应用领域。但在大多数情况下，你仍会选择优先保障召回率。

<details>
<summary>Original English</summary>

**Speaker 0**: However, in some cases when you are tuning, you will say: actually, I want precision. I want it to be absolutely right when it's right, and I don't care if it misses some things. There are domains where that is the output that you want. But most of the time you want to prioritize recall.

</details>

### 大模型裁判的固有偏置陷阱

**Speaker 0**: 使用大模型充当裁判存在几个已知的常见偏置陷阱（biases）。其一是位置偏置（position bias）：如果提供两个选项供其裁决，裁判往往会偏向首先呈现的选项。具体取决于模型，有时模型也会偏爱排在最后的选项，但它几乎总是存在某种基于呈现位置的偏好。

<details>
<summary>Original English</summary>

**Speaker 0**: A few known pitfalls with using an LLM as a judge. One is position bias: if you present it with two options to judge between, the judge tends to favor whatever comes first. This depends on the model. Sometimes the model prefers whichever comes last, but it always has some kind of preference to position.

</details>

**Speaker 0**: 此外还存在长度偏置（length bias）：大模型青睐更长的回复，往往会给较长的回答打出更高分数，认定其质量更佳，即便这些额外增加的篇幅纯粹是废话填充。

<details>
<summary>Original English</summary>

**Speaker 0**: There's also length bias: LLMs like longer responses, and they tend to score those higher and say that they are better, even if the extra length is just filler.

</details>

**Speaker 0**: 最后一个是我很感兴趣的偏置，即自信偏置（confidence bias）。裁判模型很容易被语气自信的回复所蒙骗，这与人类如出一辙：如果你的大模型生成了错误的内容，但使用了极其自信的口吻进行表达，那么你的大模型裁判就更容易信以为真。

<details>
<summary>Original English</summary>

**Speaker 0**: And the last one I love, which is confidence bias: the judge gets fooled by a response that sounds confident, just like humans do. If your LLM says things that are wrong, but it says them in a really confident tone, your LLM judge is more likely to believe them.

</details>

**Speaker 0**: 另外还存在自偏好偏置（self-preference bias）：如果你使用同一个模型既负责内容生成又负责评判打分，它往往会偏爱它自己的生成输出。因此，如果条件允许，应该采用不同的模型分别承担这两种职责——

<details>
<summary>Original English</summary>

**Speaker 0**: There's also self-preference bias: if you use the same model to do the generation as you use to do the judging, they tend to like their own output. So if possible, use both—

</details>

<!-- chunk 10/12 -->

### 交叉模型评测与人类基准一致性

**Speaker 0**: 比如说 OpenAI 和 Anthropic，你可以用其中一家厂商的模型来驱动智能体，用另一家厂商的模型来进行评估和裁判，这样它们之间产生盲目互相认同的概率会低得多。我之前之所以用 Claude Sonnet 作为裁判去评估 Haiku 生成的内容，就是为了规避自我偏好偏差（Self-preference bias）；但如果你直接换用另一家完全不同的实验室所训练的模型，效果还会更好。而且请记住，这里的基准参照是人类的表现。人类在判断事物是否具有可操作性（actionable）时，本身也做不到完美无缺。人类在相当多的情况下也会出现误判。你所努力追求的，是构建出一个在判断上相当贴近人类水准的评估体系（eval）。

<details>
<summary>Original English</summary>

**Speaker 0**: Say OpenAI and Anthropic, use one to do your agent and one to do the judging, and they are less likely to agree with each other. Self-preference bias is why I used Sonnet as a judge for output generated by Haiku, but it works even better if you use a different lab's model entirely. And remember that the benchmark here is human performance. Humans are not going to be perfect at judging whether things are or are not actionable. They're going to get it wrong quite a lot of the time. What you're trying to do is come up with an eval that is reasonably close to human judgment.

</details>

**Speaker 0**: 人类之间的判断本身也存在个体差异，也就是所谓的评分者信度（inter-rater reliability）。两位人类专家在评审同一份输出内容时，其一致性得分往往甚至低至 0.2 或 0.3。也就是说，面对同样的模型输出和相同的评估规则，两位人类专家发生分歧的频率高得令人惊讶。因此，如果你用大语言模型（LLM）构建的裁判，其判断的一致性高于人类之间的一致性，那么它实际上就已经做得比人类更出色了。裁判偶尔与你的意见相左，这本身绝不是让你不信任它的理由。真正值得警惕并视为危险信号的，是裁判每一次都和你唱反调；如果裁判只是在部分时间与你意见不一致，那恰恰说明它正在正确处理一项原本就具有真正歧义的任务。此外，失败必须显得合情合理。这是 Anthropic 评估团队总结出的一条核心原则，我想分享给大家：当一个任务失败时，必须能够清晰地看懂智能体究竟在哪个环节做错了、以及为什么做错。如果你在查看失败的追踪日志（trace）时心想“这个回答在我看来完全没问题啊”，那么问题很可能出在评估体系本身，而不是智能体身上。

<details>
<summary>Original English</summary>

**Speaker 0**: Human judgment also varies from human to human, human inter-rater reliability. So two humans judging the same thing is often as low as 0.2 or 0.3. So two experts with the same output and the same rules disagree a surprising amount of the time. So if your LLM judge hits that higher consistency than humans, then it is doing better than humans. The judge sometimes disagrees with me is not by itself a reason to distrust it. What you're looking for is a judge that disagrees with you all of the time—that is the danger signal. A judge that disagrees with you some of the time is a judge correctly handling a genuinely ambiguous task. And also failures should seem fair. That is a principle from Anthropic's eval teams that I want to leave you with: when a task fails, it should be clear what the agent got wrong and why. If you look at a failing trace and you think that answer looks fine to me, the problem is probably the eval and not the agent.

</details>

### 从单点修补转向结构化闭环与失败数据集

**Speaker 0**: 现在我们已经搭建了评估器并对其进行了测试，接下来让我们利用它们来真正改进我们的智能体。这就是你如何将整个流程闭环起来的关键所在。单点修补（one-off fixes）的问题在于：假如你发现了一些失败用例，读了系统给出的解释，知道了需要改进什么，然后你修改了提示词。接下来呢？你怎么知道这次修复是否真的起作用了？你又怎么知道它有没有破坏之前原本正常运行的功能？如果你只是在几个样例上重新运行智能体，全凭直觉和感觉扫上两眼，那么你立刻就又退回到了凭直觉做开发的“氛围工程”（vibes）中。你需要一种结构化的方式来严谨对比修改前后的差异。正如我之前提到的，这就是“实验”（experiments）存在的价值所在。

<details>
<summary>Original English</summary>

**Speaker 0**: So now we've built evals, we've tested them. Let's use them to actually improve our agent. This is how you close the loop. Here's the problem with one-off fixes. If you found some failures, you read some explanations, you know what to improve, you change the prompt. And then what? How do you know whether the fix actually worked? How do you know if it didn't break something that was working before? If you just run the agent again on a couple of examples and eyeball it, then you're back to vibes. You need a structured way to compare before and after. And as I mentioned earlier, this is what experiments are for.

</details>

**Speaker 0**: 正如我刚才展示的，你可以对所有的追踪日志进行过滤筛选，只保留那些评测失败的记录，并将它们直接转化为一个数据集。具体操作方式是：选中所有这些追踪日志，点击“添加到数据集”（Add to Dataset），然后创建一个新的数据集。在这个例子中，我把它命名为“AIEWF financial demo fails”。我已经提前创建好了这个失败数据集。这能为你提供一个规模较小的数据子集，里面集中了所有评估失败的场景，以便你可以专门针对它们运行修改后的提示词。这种做法不仅速度更快，而且成本更低。

<details>
<summary>Original English</summary>

**Speaker 0**: As I showed you earlier, you can filter your traces down to just the ones that are failing, and you can turn them into a dataset like this. So you select all of your traces, you click Add to Dataset, and you create a new dataset. In this case, I've called that "AIEWF financial demo fails", and I've already created my failure dataset. But this gives you a smaller set of places where you know that your eval is failing, so that you can then run your changed prompt against just them. This is faster and cheaper.

</details>

### 回归测试集与真实黄金数据集演进

**Speaker 0**: 这是一个回归测试集。顺便说一下，你也应当保存一个常规的回归测试集。更确切地说，你应该把那些评估通过的用例收集起来，确保它们也组成一个数据集。你可以以较低的频率去运行这个测试集，以验证当你修改模型或者调整评估细则（rubric）时，不会意外导致原本成功的地方反而出现失败。此外，你的数据集并不是一成不变的静态资产。在产品上线前，当你还没有真实用户时，你的数据集可能大多是由你自己生成的合成查询（synthetic queries），或者是让大语言模型为你生成的查询。这完全没有问题，它能帮你把项目冷启动跑起来。但一旦真实流量开始涌入，你就应该立刻把真实数据转化进你的评估集中。真实的失败案例必须取代凭空想象出来的失败用例。把你的失败用例与通过用例求并集，就是大家常说的“黄金数据集”（golden dataset）——这是一个经过精心策展、标注、并被你完全信赖作为衡量系统质量基准真相的集合。

<details>
<summary>Original English</summary>

**Speaker 0**: This is a regression test set. Sorry, you should also save a regression test set. Rather, you should get the ones where it is not failing and make sure that those are also a dataset that you can check less frequently to make sure that when you've changed your model—sorry, when you've changed your rubric—that you haven't accidentally made it fail in places that it was succeeding before. And your datasets are not static pre-production. When you don't have users yet, your datasets are probably going to be synthetic queries you generated yourself or queries that you got an LLM to generate for you. That is fine, it gets you off the ground. As soon as real traffic starts coming in, you should turn that into your eval sets. Real failures should replace imagined ones. The union of your failure cases and your passing cases is what people call your golden dataset: the curated labeled set that you trust as ground truth for measuring quality.

</details>

### 数据驱动的自动化提示词工程

**Speaker 0**: 现在我们要来改进智能体了，但我们并不打算纯靠手工去手写修复方案。正如我前面所说，这一切都可以借助技能（skills）来完成，都可以由编程智能体（coding agent）来代劳。我假设在 2026 年的今天，每个人绝对都在使用编程智能体来完成所有的编码工作。既然你可以让 Claude Code 自动拉取所有失败的追踪记录，替你修改代码并优化应用程序，那你为什么还要亲自动手去修改提示词呢？这正是我们接下来要演示的操作。Claude 会拉取所有失败的追踪记录，仔细阅读所有的评估解释，然后将这些解释直接转化为对你的代码库所执行的具体行动。

<details>
<summary>Original English</summary>

**Speaker 0**: Now we're going to improve our agent, but we are not going to handwrite the fix. As I mentioned, you can do all of this with skills. You can do all of this with a coding agent. I am assuming, it being 2026, absolutely everyone is using a coding agent to do all of their coding. So why would you modify your prompts by yourself when you can get Claude Code to pull down your failing traces, modify your code for you, and improve your application for you? That is what we're going to do here. Claude will pull down all of the failing traces, it will read all the explanations, it will turn the explanations into action that it takes on your codebase.

</details>

**Speaker 0**: 这里最核心的关键在于：整个过程中没有任何一步是凭空猜测的。Claude 并不是凭空捏造改进方案。你并不是仅仅对它下达“在这方面做得更好一点”或者“不要犯任何错误”这种模糊的指令。它提出的每一处修改建议，都可以精确追溯回具体的失败原因解释。举例来说，如果裁判指出输出内容缺乏具体的执行建议，Claude 读取后就会重写提示词，确保它给出具体建议；如果裁判指出输出内容陈述了风险却没有提供支撑证据，它同样会重写提示词来修复这一缺陷。这就是真正的数据驱动型提示词工程（data-driven prompt engineering），而现在我们已经可以将其全自动化。

<details>
<summary>Original English</summary>

**Speaker 0**: And here's the important thing: nothing here is guessed. Claude isn't inventing improvements out of thin air. You haven't just told it "get better at this", you haven't just told it "make no mistakes". Every change it proposes traces back to a specific failure explanation. So if the judge said that it lacked specific recommendations, Claude will read that and rewrite the prompt so that it does. If the judge said that it presents risks without supporting evidence, then it will rewrite the prompt so that it fixes that too. This is data-driven prompt engineering, and now we can automate it.

</details>

**Speaker 0**: 请留意我们传入了哪些信息：我们传入了需求规格（即我们希望达成的目标），并且传入了一个改进提示词，明确告诉它当前应该致力于优化哪些方向以及如何去改进它。这是又一个大语言模型应用，也是另一个具有非确定性（nondeterministic）特性的环节，意味着它同样存在出错的潜在可能。如果我们有充裕的时间，你甚至可以构建一个元评估器（meta-evaluator）来评估这个改进评估器本身，确保元评估器的运作准确无误。但由于这会让流程变得过于复杂，而且我们的时间有限，所以今天我们不在这里展开。但严谨明确的需求能够确保 Claude 保持可靠与诚实，因此你应当投入足够精力，尽可能确保这个评估体系达到最高的准确度。

<details>
<summary>Original English</summary>

**Speaker 0**: So notice what we have passed in: we've passed in our requirements, what we were trying to get done, and we've passed in an improvement prompt telling it what you should be working on and how to get better at it. This is yet another LLM application, and yet another thing that is nondeterministic, and yet another way that it can go wrong. You could, if we had more time, meta-evaluate your meta-evaluator and make sure that your meta-evaluator is doing the right thing. But we're not doing that here because it gets too complicated, and also we only have so much time. But good requirements keep Claude honest, so you should be spending time making sure that this evaluator is as accurate as you can make it.

</details>

### 双通道智能体提示词重写与实验配置

**Speaker 0**: 在这个案例中，我们获取了这个提示词，并将它们接入到我们的两阶段处理管道（two-pass pipeline）中。我们根据 Claude 拉取失败追踪记录后提炼出的改进建议，将它们回传给 Anthropic 的模型，明确要求：“请基于这些失败原因的解释，写出更优质的提示词——写出更优质的调研提示词（research prompt），写出更优质的撰写提示词（write prompt）。”随后，我们把这些优化后的提示词重新注入到我们的智能体中，现在我们就可以正式开始运行对比实验了。

<details>
<summary>Original English</summary>

**Speaker 0**: So in this case, we are taking this prompt and we are wiring them into our two pass. We're taking the recommendations that we got from Claude based on pulling the failing traces, and we're passing them back to Anthropic saying, "Based on these explanations, write a better prompt, right? A better research prompt, write a better write prompt." And then we're going to feed them back into our agent, and now we're going to run an experiment.

</details>

**Speaker 0**: 在用户界面中，我们能看到数据集与实验列表，其中包含了我的金融演示失败数据集。只要我能在界面上顺利向下滚动，我们就可以使用这些全新优化后的提示词来组装并运行一个改进后的智能体。你可以直观看到优化后的调研提示词和优化后的撰写提示词；除了这两处修改之外，智能体的其余部分与之前完全一致。接着，你可以在实验中为其关联一个评估器。我们这里的做法是为它指派一个任务（task）。这个任务可以是任何内容——它可以是智能体所执行操作的某一个子组件。比如，如果你正在运行一个专门评估工具调用的评估器，那么你的任务就可以仅仅设计为调用该工具并查看该工具的输出结果，然后你再对此进行评估。而在我们当前的场景中，我的任务是从头到尾完整地重新运行整个智能体，不过实际场景中并不局限于此。接着，针对这个重新运行的任务，我们再执行相同的评估套件。也就是说，我们修改了智能体，重新运行了智能体，并重新运行了评估，把这一整套流程固化为一个严谨的实验。

<details>
<summary>Original English</summary>

**Speaker 0**: So over in the UI, we have datasets and experiments, we have my demo financial fails. We can, assuming I can scroll, wire up an improved agent using those new improved prompts. So you can see the improved research prompts and the improved write prompts. This is otherwise exactly the agent as before. And you can create an evaluator with an experiment. So what we're doing here is we're giving it a task. A task can be anything. So a task could be some subcomponent of what your agent did. So if we were running an evaluator that was about tool calls, then your task could be just call this tool and see what the output of the tool is, and then you would evaluate that. In this case, my task is run the entire agent again from start to finish, but it doesn't need to be. And then we are running the same evaluation results against this new running of the task. So we've changed the agent, we've rerun the agent, and we're rerunning the eval, and we're turning that into an experiment.

</details>

### 实验结果对比与任务抽象设计

**Speaker 0**: 实验配置好的全貌就是这样，目前实验尚未开始执行。我们为它指定了名称，分配了要处理的数据集，定义了任务，挂载了评估器，然后点击触发运行。运行结束后，我们就得到了这里的实验结果。对于每一次具体的运行，我们都能清楚看到它生成的输出内容以及最新的评估得分。正如你所见，如果你还记得的话，在这份数据集里此前所有的用例都是不具备可操作性的；而在这次评估运行之后，你可以看到其中一部分用例现在已经成功达到了具有可操作性的标准。这证明我们的优化确实带来了实际提升。

<details>
<summary>Original English</summary>

**Speaker 0**: This is what the experiment looks like, the experiment's now run. We've given it a name, we've given it the dataset that it will work on, we've given it the task, we've given it the evaluator, and we've told it to run. This gives us the results, which are here. So for every single run, we've got the output that it got and the new eval score. So as you can see, this was a dataset if you recall where previously all of them were not actionable. The eval has run, and you can see that some of them are now actionable. So we have improved.

</details>

**Speaker 0**: 如果我们看一下这里的整体综合得分，实际上我这一次甚至直接拿下了满分。当然，这是因为我之前有很多次调试验证的机会，所以我恰好单次尝试（one-shot）就成功把提示词从 50% 的错误率一路拉到了 100% 正确。但在现实生产环境的评估迭代中，事情通常不会如此一蹴而就，真实的工程迭代不会进行得这么顺风顺水。这正是为什么我们需要通过折线图来追踪进程。在实际工作中，你预期的工作流应该是接连不断地运行一次又一次的对比实验，随着你的评估体系越来越完备、能力越来越强，眼看着那条评估曲线在图表中逐步稳健攀升。这就是我一直在说的你必须一步一个脚印去攀登的那座技术高山。

<details>
<summary>Original English</summary>

**Speaker 0**: And if we look at the overall score here, actually I've nailed it because I had, you know, a lot of chances to get this right. I have one-shotted my prompt getting from being wrong 50% of the time to being right 100% of the time. Real evals won't work like that. Real iteration won't run so smoothly, that is why this is a graph. What you are expecting to do is run experiment after experiment and slowly watch the graph climb as your evals get more and more capable. That is the hill that I'm talking about that you're trying to climb.

</details>

**Speaker 0**: 支撑这一整套实验体系背后的核心抽象在于：任务本质上就是一个纯粹的 Python 函数。它从数据集中提取一个示例样本，执行你所期望的任意逻辑代码，最后返回一个处理输出。因此，实验框架本身根本不在乎这个任务内部具体在做什么；正如我刚才所说，它既可以运行完整的端到端智能体，也可以仅单独运行某一个组件，或者也可以仅仅调用一次外部 API。只要它能够接收一个输入并返回一个输出，你就可以围绕它构建并运行实验。实验体系最强大的力量源于其“受控变量对比”（controlled comparison）：你输入完全相同的数据样本，施加完全一致的评估判定标准，整个系统当中唯一发生改变的只有智能体的提示词本身。这意味着评估得分上出现的任何差异，都可以百分之百明确地归因于你所做出的那一次提示词修改。

<details>
<summary>Original English</summary>

**Speaker 0**: So the key abstraction behind experiments is that a task is just a Python function. It takes an example from the dataset, it runs whatever you want, and it returns an output. So experiments doesn't care what the task does internally, so it can run the full agent or just one component, like I said, or it could call an API as long as it takes an input and returns an output. You can run experiments on it. The power of experiments is controlled comparison. So you take the same inputs, the same evaluators, and the only thing that changed is the agent's prompts. That means any differences in scores is attributable to your change.

</details>

<!-- chunk 11/12 -->

### 评估迭代循环与样本量权衡

**Speaker 0**: 你不再需要去纠结：“这次得分更高究竟是因为我的 Prompt 改善了，还是仅仅因为这次网络搜索碰巧返回了更好的结果？”好吧，其实你可能仍然会有那么一点点疑问，因为 Agent 本身是非确定性的（non-deterministic），它这一次完全可能会执行十次网络搜索而不是五次。但你至少已经消除了一大关键的变量来源，那就是测试用例本身的差异。所以正如我之前所讲，我的 Agent 尝试单次直接运行成功（one-shot），这确实很棒；但现实中事情绝不会那么简单。我们这里探讨的“评估-迭代循环”（eval iterate cycle）——即运行一次实验、修改你的 Prompt、一遍又一遍重新运行实验——它的真正价值恰恰在于这个循环过程本身，而不仅仅是最终得出的那个分数。

<details>
<summary>Original English</summary>

**Speaker 0**: you're not wondering did it score higher because of my prompt um or did it score higher because the web search happens to return better results this time？ well， that actually still still ondering that a little bit buck as the agent is non deterministic。 so it could have done ten web searches instead of five web searches。 but you've elimiitted a major source of variation， which is the test cases。 so like i said， um my agent has one shot of this， um which is great。 but in reality， uh， it's not going to be that simple um the eval iterate cycle that we're talking about here where you go through uh run an experiment， change your prompt， run the experiment again over and over and over。 that is where the real value lies not in the score itself， but in the cycle，

</details>

**Speaker 0**: 你运行评估，观察失败用例，查看判别解释，找出共性模式，然后调整你的 Prompt；或者就像我们本次所做的那样，让 Claude 来替你调整 Prompt。“系统是否变好了？”这是一个只有通过评估才能回答的问题。你将“好”的定义进行了量化，并以一种极其有价值的方式固化下来。这就让你能够从“我觉得它能正常工作”跨越到“我能证明它在正常工作”。紧接着一个迅速出现的实际问题就是：你到底需要多少个评估样本？对于像今天这样的工作坊级别实验，12 到 20 个样例就足以给你提供方向性的信号。但对于实际的上线发布决策，你显然会希望有更多数据，200 到 400 个样本是一个非常合适的目标。

<details>
<summary>Original English</summary>

**Speaker 0**: you run the evalils。 you look at the failures， you ad the explanations， you identify a pattern and you adjust your prompt。 or as in this case， you get cloud to adjust your prompt for you。 did it get better？ is a question that can only be answered by evalals。 you have taken the definition of good， and you have qudified it in a way that is incredibly useful。 um。 so this allows you to move from。 i think it's working to。 i can prove it's working a practical question that comes up fast。 is how many samples do you need um for workshop scale experiments like today， twelve to twenty examples gives you a directional signal for actual shipping decisions you're going to want。 uh more you're going to want something like two hundred to four hundred is a good target。

</details>

**Speaker 0**: 不过你要知道，200 到 400 依然是一个人类可以企及的规模数字，你完全可以在几周时间内积累完成；它绝不是你训练传统机器学习模型时所需要的那种成千上万甚至数以百万计的数据量。在样本量上是存在边际收益递减的：为了将误差范围减半，你必须将样本量扩大四倍。因此在某个节点上，你其实就已经拥有足够的信号来推进工作并做出判断了。

<details>
<summary>Original English</summary>

**Speaker 0**: but now that two hundred to four hundred is still like a human sized number that you could possibly accumulate over a couple of weeks。 uh it's not tens of thousands or millions， like you would use if you were training an ml model。 um they're diminishing returns。 uh， to have your your margin of error。 you have to quite druble your sample size。 um so at some at some point， you have enough signal to be able to get along um to get along。

</details>

### 优化投入层级与评估驱动开发（EDD）

**Speaker 0**: 当你在迭代时，究竟该把精力投资在哪里？这里存在一个明确的优先级层级。首先，数据质量的修复具有最高的投资回报和影响力。如果你的 Agent 检索了错误的源头，或者你的知识库里充斥着陈旧过时的信息，那么无论你做多少轮 Prompt 迭代都是无济于事的。你应该优先修复底层数据。其次是 Prompt 层面的改进：Few-shot 示例、明确的指令要求、我今天提到的各类限制条件约束，以及规范 Agent 不该做什么。这些改动往往能为你的 Agent 带来最高的 ROI。

<details>
<summary>Original English</summary>

**Speaker 0**: um you're iterating。 where do you invest？ there's a hierarchchdata quality fixxes have the highest impact。 if your agent is searching the wrong sources or your knowledge base has steal information， then no amount of prompt iteration is going to help。 you should fix the data first， then prompting improvements are next few shot。 examples， explicit instructions， the kind of self that i mentioned today， constraints， ts， what the agent ent shouldn't dn't do。 these are often the highest ROI change to your agent。

</details>

**Speaker 0**: 排在第三位的是模型选择。有时候更强大的模型能够解决 Prompt 无法攻克的难题，但它同时也会带来更高的调用成本以及更慢的响应速度，所以这是你必须权衡的取舍。至于最不应该耗费大量时间的事情，就是超参数调优（hyperparameter tuning），比如调节 temperature 或 top_p。大家很容易忍不住去调这些参数，因为它们调整起来太省事了，但它们极少能像改进 Prompt 或提升数据质量那样带来高杠杆的改变。你可以尝试调节它们，但这绝对应该是你最后才考虑的手段。

<details>
<summary>Original English</summary>

**Speaker 0**: um model selection comes third， sometimes a more capable model sellls problems that prompting atat， but it will also cost more and be slower。 so that is a trade off that you have to make um h thing thing not spspend。 a lot of time on is hyparameter tuning things like like mperperature top p。 it's very attempting to just go for them because they're easy to tweak。 they very seldom make a high leverage change like prompting wood or improving the quality of your data wood， so you can try them， but they should be the last thing you try

</details>

**Speaker 0**: 另一个值得掌握的最佳实践是“评估驱动开发”（Eval-Driven Development，简称 EDD）。在构建具体功能特性之前，先写好对应的评估。例如，如果你希望你的 Agent 在处理退款操作之前始终先验证客户身份，那就先编写专门检查该逻辑的评估项。这能给你一个关于“什么是好”、“什么是完成”的清晰且可衡量的标准定义。之后你再去开发功能，直到评估全部通过为止。这与测试驱动开发（TDD）是完全相同的哲学。评估驱动开发让我尤为推崇的一点是，最贴近产品需求的人往往最适合定义什么是成功。产品经理、客户支持人员乃至销售人员都可以为评估任务贡献力量。他们能告诉你实际场景中什么算好、什么算不合格，他们根本不需要去写代码，只需用自然语言描述他们眼中的良好标准，而你则可以将其提炼转化为具体的评估打分细则（eval rubric）。

<details>
<summary>Original English</summary>

**Speaker 0**: a practice worth knowing。 is eval driven development， right？ the eval， before you build the feature， uh， if you want your agent to always verify customer identity before does something before processing a refunferenstance， then write the eval the checks for that。 first。 that gives you a clear measurable definition of what good looks like of what done looks like， then you can build the future until the evl passes。 this is the same philosophy as test， driven and development。 and something i love about eval driven development is that the people closest to product requirements are best position to define success。 so product managers， customer service people， even sales people can contribute to eval task。 they can tell you what looks good and what doesn't look good in practice。 they don't need to write code。 they just need to describe in natural language， what good looks like to them。 and you can boil that down into your eval rubicc。

</details>

### 线上评估与生产闭环

**Speaker 0**: 到目前为止，我已经向大家展示了如何进行离线与线上操作。虽然我们一直在 Notebook 实验环境里操作，但真正的完成绝不是你的开发实验 Trace 通过就万事大吉了。只有当你的 Agent 能够在生产环境中持续应对从未见过的新流量并稳定表现时，才算真正大功告成。因此，花几分钟探讨这一点非常有价值。首先是线上评估（online evals）。顾名思义，线上评估就是直接把你今天编写的那些评估器——事实核查、忠实度、可操作性等——自动运行在传入的生产环境 Trace 数据上，用完全相同的评估标准去检验新鲜数据。

<details>
<summary>Original English</summary>

**Speaker 0**: and so far， i've shown you how to do things both offline and online。 we've been doing everything in a notebook um， but you're not really done when you're death experiment， trace passes。 you're done when youagent um keeps performing inproduction on traffic that you've never seen um and it's worth spending a couple minutes talking about that， even though we're going to stick in the notebook uh for this workbook for this work session。 um the first thing is online evalils。 um like i said， and like i showed you earlier online evalls are exactly what they sound like they take the evaluators that you wrote today。 uh the tickcheck， the faithlness， the actionability uand run them automatically on incoming production， traces the same evals running on new data。

</details>

**Speaker 0**: 我之前展示了如何在单个 Trace 上运行评估。Arize 允许你在三个作用域维度执行此操作：你可以在 Span 级别运行评估，比如对某个特定 LLM 调用或特定工具调用每次都运行评估；或者在 Trace 级别运行评估，此时它能看到完整的调用树，从头到尾进行全局评估。你可以选择与你所探究的问题相契合的作用域。同时，你不需要在每一个生产 Trace 上都全量运行评估。生产规模下的 LLM as a Judge 是有成本的，费用会不断累积。因此你可以抽样 10% 或 1% 的流量，这样既能获得具有统计指导意义的信号，又不必为每一次应用调用都承担昂贵的评判成本。

<details>
<summary>Original English</summary>

**Speaker 0**: uh， i showed you how to run this on a trace eggs。 lets you do this at three scopes。 you can run your evalils at the span levels。 you can say this particular ellymm call this particular tool call， run a trace on it every single time。 sorry， run a eval on it every single time， or you can run it at the trace level， where it has the full tree to look at。 and it can evaluate everything from start to finish。 um you pick the scope that matches the question that you're asking um and you don't need to run e thousand and every single productrtrace， i uh production trace， rather um LM judges costs money at at production uh scale。 those costs can add up。 so you sample ten percent of your traffic or one percent of your traffic。 and that gives you a directional signal without you having to run an expensive LM as a judge on every single iteration， every single instance of your application。

</details>

**Speaker 0**: 如果你不想手动编写评估器，这里有一个好消息：我们在 Arize 内部构建了一个专门的 Agent，名字叫 Alex。你可以用纯自然语言描述你的评估逻辑，或者让非技术背景的同事直接用通俗语言描述合格标准，Alex 实际上会替你操作 UI，自动创建评估器、编写评判细则、正确设置分值并搞定所有配置，然后告诉你一切就绪。这对于非工程师来说极为实用。整个生产闭环的运作流程如下：应用程序产生 Trace，流向线上评估器；评估器对这些 Trace 进行打分并生成标注与原因解释；评估标注随后流入监控模块（我们今天暂未展开讲解）；监控模块在出现异常时向团队发送告警；团队介入排查，定位失败的 Trace，将其保存为回归测试数据集；随后改进 Agent，运行实验进行验证，最终上线修复方案。

<details>
<summary>Original English</summary>

**Speaker 0**: if you don't want to write your evalls by hand， we have good news sphere， which is that we have built an agent into AX itself。 it is called alex。 you can describe your evl in plane english， or you can get your non technical colleagues to describe a describe the definition of good in plain english， and alex will actually manipulate the ui for you。 create an eval write the ruubrick settle the scores correctly， get all the configuration correcct。 and then just tell you that it's done this especispeciuseful for non engineers um and the full loop and production looks like this。 you go from application， which produces traces to online evalils， which grade those traces and produced labels and explanations the eval labels feed into monitors， which we didn't cover today。 um the monitors can alert your team。 when something goes wrong， the team can investigate ffind the failing traces， say them as a ggression atata set， improve the agent， run an experiment to verify and ship the fix。

</details>

**Speaker 0**: 接着整个循环再次运转。随着生产流量的不断累积，你会捕获到新的失败模式和极端边界用例（edge cases）。你将始终处于对评估规则和生产监控的持续迭代中。但这是一种具有复利效应的回报：线上评估捕获到的每一个失败案例都会变成新的测试用例；你将其保存到数据集中，它就成了下一轮变更的回归测试用例。久而久之，这将沉淀出一个完全为你自身应用量身定制的专属数据集——对应你特有的失败模式、特定的用户群体以及特定的质量基线，这是其他任何人都不具备的数据资产，更是一项随着 Agent 每次运行而不断扩大的核心竞争优势。

<details>
<summary>Original English</summary>

**Speaker 0**: and then the loop can run again um as new production traffic accumulates， you will accumulate new failure modeds。 you will accumulate new educases。 you're always going to be iterating on your evalils and iterating on your production monitoring。 but it is a payoff that compounds every failure that your online evelcatch becomes a new test case。 you save it to a dataset。 and now it's a regression test for your next round of changes over time。 this creates a dataset that is unique to your application。 so your specific failure， res， your your specific users， your specific quality bar， nobody else has that data。 and that is a competitive advantage that grows every single time your agent runs。

</details>

### 用 Coding Agent 驱动自动化修复与双重防线

**Speaker 0**: 最后我想给大家留下一个模式，这也是最为强大的模式。我们今天演示了最简化的版本：将裁判大模型的解释反馈给 Claude，让它重写两条 Prompt。针对两条 Prompt 这种做法效果拔群，但在真实的工业级系统中， Prompt 往往分散在许多不同文件之中，并且与检索设置、工具定义深度交织在一起，根本不是调用一次 API 让大模型重写那么简单。对于能够看到你整个代码仓库的编程智能体（Coding Agent）而言，这才是你应该采用的标准范式：你从 Arize 中导出失败的 Trace 及其判别解释，将这一整批数据作为上下文投喂给 Claude Code、Cursor 或其他编程智能体。

<details>
<summary>Original English</summary>

**Speaker 0**: there's one last pattern that i want to leave you with， which is the most powerful。 when i know we did the simplest version today， we fed the judgeexplanations back to clad and had it rewrite two prompts。 this works beautifully for two prompts， but a real system isn't too prompt its prompts scattered across many files。 retrival settings， two definitions， all tangle together rewriting that isn't a single api call to jage for a coding agent that can see your entire repository。 um so this is the pattern you want to export your failing traces from ax， along with their examinations。 and hand the whole batch two cloud code or curse， or or another coding agent as context。

</details>

**Speaker 0**: 这正是我们在开头提到的 Arize Skills 插件发挥巨大威力的地方，因为你根本不需要知道怎么去调用其底层 API 或处理相关繁琐细节。你只需把这些技能配置给它，然后对 Claude Code 下达指令：“嗨，去拉取一批 Trace，分析哪里出了问题，然后改进我的应用代码。”它就能切实生效。不过，对于这种自动化方法，必须设立两道安全护栏。第一道护栏：你应该给它输入核心业务需求，而不仅仅是失败用例的解释。因为如果目标仅仅设定为“让评估通过”，它就会投机取巧作弊——它会把你的测试数据硬编码进评估逻辑，从而自动通过所有评估。因此你必须确保向 Claude Code 传达的需求极其清晰：你的目标不是机械地刷通评估，而是实现具体的业务目标，并由业务的正确实现自然而然地使评估通过。第二道护栏：你应该要求它去归纳提炼共性主题，而不是盲目迎合追踪单个独立的失败特例。

<details>
<summary>Original English</summary>

**Speaker 0**: uh this is where the ariarise skills plugin that i mentioned the beginning。 uh works really well because you don't have because you don't have to know how to call her API。 you don't have to know how to do any of that stuff。 you give it the skills and then tell cloud code。 hey， pulled down， some traces， see what's wrong and make my application better。 and it works。 there should be two guard rails on that approach first。 however， first， you should feed it rerequirements and not just the failure explanation。 so the goal isn't make the evalils pass because otherwise it will cheat。 it will include all of your test data into its evalil and automatically pass all of your evals。 so you have to make um your， you have to make sure that your requirements to your cloud code are clear that you don't wanted just to pass the evalls。 you wanted to do this specific thing， which then makes the evalils pass。 and second， you should tell to find thethemes and not chase individual failures。 it。

</details>

<!-- chunk 12/12 -->

### 构建评估闭环与软件开发生命周期的自我迭代

**Speaker 0**: 对编程智能体（Claude Code）来说，很容易陷入一种诱惑：盯着某一条单独失败的 Trace，然后写上一大堆代码去针对性地修复它。然而实际上，往往有十条失败的 Trace 都是由同一个根因导致的，这才是它真正应该重点关注的地方。由于时间只剩下十二分钟，我就不把所有这些步骤都实操一遍了。不过一旦你跑通了评估流程（Evals），这就是你利用它们能发挥出的最高杠杆价值的事情之一。

<details>
<summary>Original English</summary>

**Speaker 0**: It's very tempting for Claude Code to look at one particular failed trace and write a whole bunch of code to fix that particular failed trace when there are actually ten failing traces that are all the same cause that it should be focused on. Instead, I'm not going to do all of that time, all of that because I only have twelve minutes left, but once you have evals running, this is one of the highest leverage things that you can do with them.

</details>

**Speaker 0**: 让我们退后一步，看看整个体系的全貌：生产环境产生 Trace，线上评估（Online Evals）对其进行打分并生成解释分析；编程智能体读取这些解释并提出修复方案，实验模块则验证这些修复是否有效；随后你将代码发布，返回的生产流量再次被最初开启整个闭环的同一批线上评估打分。这就是软件开发生命周期（SDLC）形成了自我闭环。你的 AI 软件正在协助你改进自身的 AI 软件，而 Arize（AX）正是将这一切串联起来的底层基座——涵盖你的 Trace、评估、解释、数据集、实验、线上评估以及监控。

<details>
<summary>Original English</summary>

**Speaker 0**: So let's step back and look at the whole shape of it. Production produces traces, online evals grade them and produce explanations. A coding agent reads the explanations and proposes fixes and experiments verify that the fixes work. And then you ship the production traffic that comes back, gets graded by the same online evals that started the loop. And this is the software development lifecycle closing in on itself. Your AI software is helping you improve your AI software and AX is the substrate that ties it all together: your traces, the evals, the explanations, the datasets, the experiments, the online evals, and the monitors.

</details>

### 工作流回顾：从埋点到持续改进

**Speaker 0**: 所以我们简单回顾一下：我们只用了两行代码就为应用程序完成了埋点；我们对其进行了追踪，并读取了我们的数据；我们编写了一个基于代码的评估器（Code Eval），也使用了内置的 LLM 评估器；我们从零手写了一套自定义评分标准（Rubric）；我们对照人工标注验证了我们的裁判大模型（Judge LLM）；我们将失败案例保存到了数据集中；我们让 Claude 优化了 Prompt；我们运行了实验证明优化切实有效；接着我们看到了 Arize 如何通过线上评估将所有这些能力带入生产环境。这就是完整的闭环流程。

<details>
<summary>Original English</summary>

**Speaker 0**: So just to recap, we instrumented application with two lines of code, we traced it, and we read our data. We wrote a code eval and built-in LLM evals. We wrote a custom rubric from scratch. We validated our judge against human labels. We saved failures as a dataset. We had Claude improve the prompts. We ran an experiment to prove that it worked. We saw how AX takes all of that into production with online evals. This is the full loop.

</details>

### 从小步做起：让评估成为基础设施

**Speaker 0**: 现在，你们已经掌握了全貌。但是，你完全不需要一次性把所有事情都做完。我知道，过去这两个小时充斥着极其密集、高质量的干货信息。你可以从非常微小的地方起步：先从阅读你的 Trace 开始，只需加入那两行代码，并开始观察你的 Trace 即可。这立刻就能为你提供关于你的智能体正在做什么的未知信息。花 15 分钟阅读真实的输出结果，能让你学到比花一小时搭建看板多得多的应用认知。

<details>
<summary>Original English</summary>

**Speaker 0**: And now, you know all of it. However, you don't have to do all of it at once. This has been two hours of extremely good dense information, and I'm aware of that. You can start very, very small. You can start by reading your traces, just add those two lines of code and start looking at your traces. And that is immediately going to give you information about what your agent is up to that you didn't know. 15 minutes reading real output will teach you more about your application than an hour building dashboards.

</details>

**Speaker 0**: 接下来，写一个基于代码的评估器。基于代码的评估比 LLM 评估要简单得多，不仅速度更快，而且成本也更低。把这个评估器用在你最关心的指标上——无论是准确性（Correctness）、忠实度（Faithfulness），还是任何契合你具体场景的指标。运行它们，查看结果，观察有哪些模式浮现出来，然后再以此为基础逐步构建。

<details>
<summary>Original English</summary>

**Speaker 0**: Then write one code eval. Code evals are easier than LLM evals and they're faster and they're cheaper, and make it for the thing that matters most: so correctness, faithfulness, whatever fits your use case. Run them. Look at the results, see what patterns emerge and build from there.

</details>

**Speaker 0**: 评估是一项基础设施，绝不是事后补救。有些团队在研发的最开端就创建评估，有些团队则是在系统达到一定规模后再添加。但无论如何，最核心的是你要把评估视为系统的核心组成部分。它们应当像单元测试一样成为常规操作，而且其价值只有持续投入才会产生复利。每当系统出现回归问题、但能在它触达用户之前被捕获而不是在事故发生之后才发现时，你就会明白为什么所有这些努力都是值得的。不要仅仅寄希望于优秀。你可以通过明确规格、衡量表现并持续朝之迭代，系统性地达到卓越。

<details>
<summary>Original English</summary>

**Speaker 0**: Evals are infrastructure. They're not an afterthought. Some teams create evals at the very start of development, others add them later once they are at scale. But either way, the important thing is that you treat evals as a core part of your system. They should be as routine as unit tests and the value compounds only if you keep investing. Each time a regression shows up before it reaches your users instead of after, you'll understand why all of this work is worth doing. Don't hope for great. You can get to great systematically by specifying it, measuring it, and improving towards it.

</details>

### 上手实践与资源获取

**Speaker 0**: 所以，现在是时候在你们自己的应用上真正动手试一试了。在 Wi-Fi 连上的时候，我想大家应该都已经注册好 Arize 账号了。在 docs.arize.com 上提供了配套的 Notebook，里面包含我们今天讲到的所有内容的可运行代码。如果你希望让编程智能体来承担繁重的开发工作，只需要一条 npx 命令就可以安装 Arize 的 Skills 插件，那个链接就在今天的 Notebook 里。如果你坚持听到了最后，还可以使用屏幕上正在展示的兑换码免费获得一年的 Arize Pro 会员。今天的内容就到这里，非常感谢大家的时间与关注！

<details>
<summary>Original English</summary>

**Speaker 0**: So now is the time to try this for real on an app of your own. You already got an AX account, I hope, by the time the Wi-Fi kicked in. docs.arize.com have companion notebooks with runnable code for everything that we covered today. And if you want your coding agent to do the heavy lifting, you can install the Arize plugins, the Arize Skills plugin with one npx command. And that link is in today's notebook. If you've made it all the way to the end of this, you can also get a free year of Arize Pro using code. It's up on the screen right now. And that is it. Thank you all for your time and attention.

</details>