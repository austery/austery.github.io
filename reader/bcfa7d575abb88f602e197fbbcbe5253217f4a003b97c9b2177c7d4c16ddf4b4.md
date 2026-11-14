---
author: AI Engineer
date: '2026-06-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=SKDJo2CopRs
speaker: AI Engineer
tags:
  - stateful-serverless
  - code-generation
  - sandboxing
  - real-time-sync
  - distributed-systems
title: Cloudflare AI Agents：持久化对象与动态代码沙盒的未来
summary: Cloudflare 探讨了有状态无服务器架构（Stateful Serverless）如何成为构建 AI Agents 的理想计算单元。他们介绍了能直接安全运行模型生成代码的沙盒环境，以及为模型上下文协议（MCP）提供跨平台同步与持久化连接的新型范式。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cloudflare
  - Vercel
  - OpenAI
products_models:
  - Durable Objects
  - Dynamic Workers
  - Cloudflare Workers
media_books: []
status: evergreen
---
### 开场与自我介绍

**Matt**: 哦，是的。嗯，欢迎。我是 Matt，这位是 Sunil。我们在 **Cloudflare** 负责 AI Agents（智能体）。就是这个东西。所以，是的，也许你想做一个比我更好的自我介绍。我是 Matt Carey。我的团队只招募我的朋友。说点什么吧。确保对着麦克风说。

<details>
<summary>Original English</summary>

Oh, yeah. Well, uh welcome. Um uh I'm Matt and this is Sunil. Um we work on agents at Cloudflare. This this thing. Um so, yeah, maybe you want to introduce yourself a little better than me. Uh this is Matt Carey. Uh I only hire my friends for our team. Uh say something. Make sure it's on the microphone.

</details>

**Sunil**: 好的，好的。哦，是的。我的麦克风开了吗？我一直觉得 Cloudflare 是一家属于朋友和家人的公司。我们喜欢帮大家忙。所有我们最亲密的朋友，没有人需要支付 Cloudflare 的账单，顺便说一下，它本身就已经便宜得离谱了。这简直不可思议。

<details>
<summary>Original English</summary>

Yeah, yeah. Oh, yeah. Mine's Is mine on? Like I keep thinking about Cloudflare as a friends and family company. Uh we love doing favors. All our closest friends, no one pays for Cloudflare bills, which is already dirt cheap, by the way. It's ridiculous.

</details>

### AI Agents 与 Durable Objects

**Sunil**: 所以，大概一年多前，我们开始认真地构建 AI Agents，而且进展非常顺利。在座有多少人被“橙色洗脑（orange peeled）”了？也就是使用 **Durable Objects（持久化对象）**。哦，是的。哦，是的。这是名字起得最糟糕的技术，但它确实令人难以置信，对吧？每个人都说，它是个数据库。我说，不，但它包含一个数据库。但是，我们开始使用它，结果发现它的效果非常好。它有一些独特的能力。有人可能称之为供应商锁定（vendor lock-in），有人可能称之为创新。

<details>
<summary>Original English</summary>

Um so, we started building out AI agents seriously a little over a year ago and it's gone remarkably well. Uh how many folks here are like orange peeled? Which is to say durable objects. Oh, yeah. Oh, yeah. Worst named technology, but incredible, right? Everyone's like, it's a database. I'm like, no, but it has a database. And I'm like, uh but uh but we started using that and it turned out to work out really well. There's some unique capabilities about it. Uh some might call it vendor lock-in, some might call it innovation.

</details>

**Sunil**: 从那以后，团队一直在壮大。我们的大本营——大多数人都在伦敦。嗯，你是英国人，但你刚搬到了里斯本，顺便说一句，那真是太棒了。各位，你每天都在喝葡萄酒，吃鱼、土豆和面包。简直是国王般的生活。

<details>
<summary>Original English</summary>

Uh but like and ever since then the team has grown. Uh we are based in like most of us are in London. Well, you're British, but you just moved to Lisbon, which is amazing, by the way. Folks and uh you spend your days drinking wine and you do fish, potatoes, bread. It's just king's life.

</details>

**Matt**: 我住在纽卡斯尔。天气要糟糕得多。不过我确实挺喜欢那里的。我试着看了《乔迪海岸》（Geordie Shore），我后悔那么做了。我不会——不，那不是我想的。无论如何，所以，我们一直在构建 agents，而且……

<details>
<summary>Original English</summary>

Uh I live in Newcastle. The weather is way worse. Uh but I do like it. Uh I tried watching Geordie Shore and I regret doing that. I will No, that's not what I think of. Anyway, so, we've been building agents and

</details>

**Sunil**: 回到正题。抱歉，是的，当然。我不知道，我们可以告诉你们我们目前的进展，我们正在使用的一些技术，以及一些即将推出的新东西。值得庆幸的是，这里没有录像，所以我们可以告诉你们一些即将发布的秘密功能。但是，我很乐意花几分钟时间听听大家的想法。如果你们有任何问题，可以提出来，否则我们准备了大概五个我们认为讨论起来会很有趣的话题。但是，关于 Cloudflare 和 AI agents，你们想了解什么？

<details>
<summary>Original English</summary>

Back on topic. Uh sorry, yes, of course. Uh and uh I don't know uh we can tell you about our journey so far, some of the tech we're using, some of the new upcoming stuff. Uh thankfully, none of this is recorded, so we can tell you about some secret features that are coming out. Uh but uh I'd love to put it out there for a couple of minutes. If you have any questions, otherwise we have like five like topics we thought would be interesting to talk about. But what do you want to know about Cloudflare and AI agents?

</details>

**观众**: 给我们讲讲这个吧。

<details>
<summary>Original English</summary>

Tell us about this.

</details>

### Stateful Serverless 架构解析

**Sunil**: 太棒了。那么，这一切都始于 **Durable Objects**。好吗？大家都相信，现在构建服务器的方式是，你编写一个接收请求并返回响应的函数。对吧？最简单的模型。然后你决定你想做一个——你想为你的网站构建一个访问计数器。所以，你的做法是，设置 `let x = 0` 或者 `let counter = 0`，并且对于每个请求，你会执行 `counter++`。它在本地运行良好，然后你部署了它。结果它立刻就崩溃了。为什么它会失败？

<details>
<summary>Original English</summary>

Amazing. So, uh So, it starts with durable objects. Okay? So, you know how everyone believes the way you build servers nowadays is you write a function that takes a request and returns a response. Right? Simplest model. And you decide you want to do you want to build a hit counter for your website. So, what you do is you say, uh let x = 0 or let counter = 0 and for every request you'll say counter++. And it works locally and you deploy it. And it immediately fails. Why does it fail?

</details>

**Sunil**: 因为它没有状态。它启动起来，执行完任务，然后就消失了。计数器将始终为零。至少大多数时候是这样。比如在有流量的情况下，它可能会重用这个隔离区（isolate）。所以，现在你必须使用一个数据库来存储状态。你需要做一大堆事情。相反，对于给定的 ID，如果你能拥有一个类（class），它只针对某个特定的请求启动一次，然后所有未来的请求、所有的 websocket 连接都会落到同一个地方，那会怎样？所以，我们称之为 **Stateful Serverless（有状态的无服务器计算）**，这是最令人困惑的概念，因为服务器本身就是有状态的。但它的工作方式像 serverless，因为它可以在全球范围内进行扩展。

<details>
<summary>Original English</summary>

There's no state. Like it spins up, it does the thing and it disappears. Counter will always be zero. Most times, at least. Like on traffic, it might reuse the isolate. So, now you have to use a database to store state. You need to do a whole bunch of things. Instead, for a given ID, what if you could have a class that spun up once for a given like spun up once and then every future request, every websocket connection lands in the same place. So, we call this stateful serverless, which is the most confusing thing, because servers are stateful. Uh but it works like serverless in that it's uh it scales across the planet.

</details>

**Sunil**: 而且因为有了 Cloudflare 神奇的全球网络，这意味着比如在伦敦，你大概能获得 15 毫秒的延迟。作为对比，60 FPS 是 16 毫秒，略多于 16 毫秒。这意味着如果你正在使用——如果你们用过 **TLDraw**，它就是基于这项技术构建的。如果你在同一共享屏幕上打开一堆手机，然后开始在上面画画，你会看到所有手机上都实现了完美的同步。我知道我有偏见，但这真的太棒了。

<details>
<summary>Original English</summary>

Uh and because of the Cloudflare magical planetary network, it means like in London you get like 15 ms latency. Uh for contrast, uh 60 FPS is 16 ms, little over 16 ms. Which means if you are using uh if you folks have used uh TLDraw, it's built on this tech. Uh if you open up a bunch of phones on the same shared screen and you start like drawing on it, you'll see in like perfect sync on all phones. It's Ah, I know I'm biased, but so good.

</details>

**Sunil**: 无论如何，所以，我们只是——事实证明，那也是构建 AI Agents 的完美计算单元。它们是可寻址的。你可以在里面运行长期运行的任务，即使没有请求发送给它。它们可以在后台运行。它们会休眠。它们会进入睡眠状态。它们具有持久性。而且它们可以连接到其他所有东西。所以，这就是我们最初下的赌注。

<details>
<summary>Original English</summary>

Anyway, so, we just It turns out that that's the perfect compute unit for building AI agents as well. They're addressable. You can run long-running things in it even if there are no requests going to it. They can run in the background. They hibernate. They go to sleep. They have persistence. Uh and they can connect to like everything else. So, that was the original bet we made.

</details>

### 后台运行与定时调度

**Sunil**: 我想知道我是否可以——让我们向下滚动。我想知道这个 API 是否在这个页面上可用。一些关于营销的东西。哦，是的，看，它看起来大概就是这样。你基本上是在创建一个云，你从 agents 导入。请不要问我们为这个 NPM 包付了多少钱。

<details>
<summary>Original English</summary>

And I wonder if I can Let's scroll down. I wonder if like the API is available on this page. Something something marketing marketing marketing. Oh, yeah, see, that's kind of like what it looks like. You basically make a cloud you import from agents. Please don't ask us how much we paid for this NPM package.

</details>

**Sunil**: 你继承它，然后就可以添加东西。你设定，哦，当它启动时，安排好这些事情。你可以创建一些小型的可调用对象。所以，agents 也作为一个全栈的东西提供。我们为你提供 React hooks，而且——不一定非得是 React，但我假设——我们也有纯 JavaScript 客户端。你可以定义那些实际上由客户端调用的东西。你可以在后台运行一些任务。调度（scheduling）是我最喜欢的功能，因为这意味着你可以这样说：每周五晚上 9 点，翻阅我整个 Git 历史记录、我的 wiki 和 Notion，把它们整理出来并发送给我的经理。确保你故意拼错几个词，这样看起来就像是我自己写的。

<details>
<summary>Original English</summary>

Uh you extend it and you can add. You're like, oh, when it starts up, schedule these things. Uh you can make little callables. So, agents also comes as a full stack thing. We give you like React hooks and like from doesn't have to be React, but I assume Uh we have plain JavaScript clients as well. Uh you can define things that are actually called from clients. You can run things in the background. There's like like scheduling is my favorite thing because it means you can say stuff like every every Friday at 9:00 p.m. look through my entire Git history and my uh wiki and the notion, compile it and send it to my manager. Uh uh make sure you mess up the spellings so it looks like I wrote it.

</details>

### MCP 服务器与 Code Mode 的起源

**Sunil**: 所以，你可以做到所有这些。这很棒。而且它可以扩展到数百万、数万亿，或者某个荒谬的 Cloudflare 级别的数字。那就是它的起点。在过去的一年里，我们构建了很多东西。因此，我们为 **Vercel** 的 AI SDK 提供了一流的后端。事实证明 AI SDK 非常棒。Nico 在这里吗？不在。不管怎样，我们不允许 Vercel 的员工进入我们的聊天室。

<details>
<summary>Original English</summary>

So, you can do all of this. Like it's nice. You can And you can like it spins up to millions, trillions, some absurd Cloudflare number. Uh that's uh that's where it starts. And over the last year we have built a bunch of things. So, we have a first-class uh back end for Vercel's AI SDK. And it turns out the AI SDK is great. Is Nico around here somewhere? No. Anyway, um we don't allow Vercel employees into our uh chat rooms.

</details>

**Sunil**: 结果发现，要让它达到生产就绪状态，要进行工具调用，要实现同步、恢复能力以及跨标签页的功能，还需要做很多事情。所以，我们拥有世界上最好的 AI SDK 后端。我想跟你们谈谈 **Code Mode（代码模式）**，顺便说一句，大概在整个旅程的这个阶段，**MCP (Model Context Protocol)** 在去年 4 月左右变得超级受欢迎。结果发现，Durable Objects 实际上是构建 MCP 服务器的绝佳方式，因为如果你对 MCP 了解的话，当它最初推出时，你需要在客户端和服务器之间保持有状态的连接。

<details>
<summary>Original English</summary>

Uh so, it turns out there's a lot more to make it production-ready, to do tool calls, to do synchronize to do resumability, things across tabs. Make So, we have the world's best back end for like the AI SDK. I'm saying a lot of things. So, we have that. We have I want to talk to you about code mode, which is, by the way, about maybe this point in the in the journey, uh like MCP got mega popular around April last year. And so, it turns out durable objects are actually a great way to do MCP servers, cuz if you know anything about MCP, uh when it was originally launched, you needed to have um a stateful connection between client and server.

</details>

**Sunil**: 这是将 MCP 服务器部署到生产环境、部署到云端时最令人烦恼的事情之一。而 Durable Objects 可以非常容易地维护有状态的连接。这其实就是它的核心意义。所以，我们很早就抓住了这个机会。我们拥有一些最早的 MCP 服务器，比如 PayPal、Century，所有的大型服务都在使用这个。Linear，Intercom，你能想到的都有。

<details>
<summary>Original English</summary>

And this is one of the most annoying things about deploying MCP servers to production to the cloud. And durable objects maintain a stateful connection like very very easily. That's kind of the whole point. And so, we like jumped on that really early. We had some of the like first MCP servers, like PayPal, Century, All the big ones are on this. Linear, Intercom, um name it.

</details>

**Matt**: 是的。所有的都是。有些我们不能说出名字。而且——是的，所以，事实证明 MCP 在这方面真的非常非常好。而这又引导我们进入了更多的兔子洞，我认为这正是我们引入 **Code Mode** 的契机。

<details>
<summary>Original English</summary>

Yeah. all of them. Um Some we can't name. Uh and uh and yeah, so, it turns out MCP was like really really good for this. And this this led us down like very many more rabbit holes, really, where um I think this is our lead into code mode, really.

</details>

### Dynamic Workers 与代码沙盒

**Sunil**: 当然。是的。所以，我们有 Durable Objects。我们有 **Workers**，它有点像无服务器函数即服务。你可以把它想象成类似于 Lambda，设想 Lambda 是在 10 年、15 年后才被设计出来的那样。它比 Lambda 更好。然后，我们有了这个新的原语，我们称之为 **Dynamic Workers（动态 Workers）**，它就像一个普通的 worker，但你不需要提前将它部署到云端，你可以从一个正在运行的 worker 出发，然后说，我有一串代码，它可能是一个客户发给我的、或者是 LLM 生成的。

<details>
<summary>Original English</summary>

Sure. Yeah. And then so, then we have So, we have durable objects. We have workers, which is sort of like a serverless function as a service. Like a lambda, you think. Like imagine a lambda was designed 10, 15, 20 years later, something like that. Like it's better. Um Then then we have this this new this new primitive, which we're calling dynamic workers, where it's like a worker, but instead of having to deploy the worker to the cloud, you can go from one worker and be like, I have this string of code that a customer sent me or a user sent me or an LLM generated.

</details>

**Sunil**: 然后我打算把它放在一个独立的 worker 中运行这行代码。所以，仅仅通过一段字符串，你就可以运行这段代码。这感觉打破了很多人的常识。上周我参加了 MCP 开发者峰会，我旁边有一家初创公司，那个家伙一直试图说服我，说任何企业环境都不会允许人们去运行生成的代码，而且他们也从未见过这样的情况。然后一位来自 **Lockheed Martin（洛克希德·马丁）** 的人走到我面前说，哦，我们很喜欢这种模式，我们非常喜欢动态生成代码的做法。我当时觉得这种反差实在是太搞笑了。

<details>
<summary>Original English</summary>

And I'm going to run that piece of code in its own isolated worker. So, from a string, you can run you can run the code. And this is like kind of breaks a lot of people's brains. I was at MCP Dev Summit last week and there was a startup next to me and th- th- this guy was just trying to convince me that no enterprise environment would allow people to run generated code and that they'd never seen. And then someone from Lockheed Martin came up to me and was like, oh, we love code we love this like uh generating code. And I just like the dichotomy was really funny.

</details>

**Sunil**: 但基本上，你可以在这个被称为 Dynamic Worker 的沙盒里，运行别人生成的代码。我们认为这是一个非常好的沙盒，并且是在你所习惯的沙盒环境中。它不是一个虚拟机。它没有完整的文件系统或虚拟机那种沉重感。但它是一个隔离区，你可以按需启动它，并且可以启动数十亿个。

<details>
<summary>Original English</summary>

But basically, you can run people's code that they generate in this thing called a dynamic worker. And we think it's a very very good sandbox um in the sandbox you're used to. Well, not a VM. Not a full It doesn't have a full file system. It doesn't have like all of the the VM like heaviness. But it is an isolate that you can spin up and you can spin up billions of them on demand.

</details>

**Sunil**: 所以这挺酷的。无论在哪里，只要你想运行用户生成的代码，或者你以前可能会使用 DSL（领域特定语言）的地方。就像你之前可能会生成一个 JSON 文件。然后你拿到它并将其转换为代码。现在，你只需要直接写代码就行了。

<details>
<summary>Original English</summary>

So, that's kind of cool. So, anywhere where you want to have like user-generated code or you previously would use something like a DSL. Like you would have some JSON file that was generated or was built from some front ends, from some big form. And then you would take that and you would convert that to code. Now, just write code. At least I hope this is it. Yeah.

</details>

**Matt**: 所以，我讨厌成为那种四处对人说“哦，你应该去读读我的博客”的人。但是，你们确实应该去读读我们的博客。Cloudflare 的博客非常棒，技术性极强。我们唯一试图向你推销东西的地方，就是营销人员要求我们在最底部放一个号召性用语（CTA）的地方。你可以忽略那部分。但除此之外的一切都非常棒（dope）。我们会在里面深入探讨这些细节。

<details>
<summary>Original English</summary>

So, I love uh uh so, uh I hate being that guy who's like, oh, you should read my blog. But you should read our blog, by the way. The Cloudflare blog, really nice, incredibly technical. Like the only part where we try to sell you something is where the marketing folks ask us to put a CTA at the like very bottom. You can ignore that bit. But everything else is dope. We go into details about this.

</details>

**Matt**: 通常沙盒是如何从一个虚拟机或一个容器开始，然后你试着在周围添加安全层的。我们的做法完全相反。在里面你唯一能运行的就是 JavaScript，但它无法访问 `fetch`，没有 API，什么都没有。然后你可以从外部决定，好吧，这里有四个 API 可以用。我只允许向 github.com 发送请求。见鬼，可能是 github.com/xyz 或者 `math.random`。你可以通过编写代码来实现这些控制。

<details>
<summary>Original English</summary>

So, you know how like sandboxes start like from a VM or a container and then you try to add security like from around it. So, like we start the complete opposite way. The only thing you can run is JavaScript in it, but it has no access to fetch, no APIs, nothing. And from the outside you can decide, okay, here are like four APIs. Uh and I'm only outgoing fetches to github.com are allowed. Hell, github.com/xyz or math.random. I don't know, some requests fail. You can write code that does it.

</details>

**Matt**: 我们推荐的方式是，直接屏蔽所有对外的 `fetch` 请求。你赋予沙盒可以在其中运行的明确的能力（capabilities）。不要将任何环境变量暴露给这些代码。你们应该去看看这个。我应该演示一下那个 MCP 服务器吗？比如，我能展示一下你构建的那个 MCP 服务器吗？

<details>
<summary>Original English</summary>

And the way we recommend it is, no, just block outgoing fetches. You give the sandbox explicit capabilities that you can run in. No environment variables exposed to any of this code. Uh you should check this out. Should I do a demo of the MCP server? Like can I show the MCP server you built?

</details>

**Sunil**: 因为我要剧透我的演讲内容了。我们可以给我们的演讲预热了。好的。所以，基本上，使用这个技术，我们可以宣称我们不仅修复了 MCP 一次，可能还修复了两次。这就是我们两个人的演讲主题。

<details>
<summary>Original English</summary>

cuz I'm going to tell you my talk. We can tease our talks now. Okay. Oh, we get to tease our talks. Okay, okay. So, basically, using this, we kind of claim that we fixed MCP not once, maybe twice. Um and that is both of our talks. Uh yours is

</details>

**Matt**: 没错。下午 5:40，我要做一个关于 **Code Mode** 的演讲。我戴着这顶帽子。对于那些问在哪里可以弄到“Code Mode”帽子的人，我们在 cloudflare.com 上有一个招聘页面。我明天要讲的是，你如何在 MCP 服务器中使用 Code Mode，仅用 1000 个 tokens，就能赋予模型访问 Cloudflare 全部 2600 个 API 端点的权限。像 Code Mode 这样能够生成并立即运行代码的想法是超级强大的。我认为我们在这里没有足够的时间来充分解释它是如何工作的，所以我邀请大家来听我们的演讲。

<details>
<summary>Original English</summary>

That's right. Uh 5:40 p.m. I'm giving a talk about code mode, what we call code mode. I have the I have the hat. For people who are asking where you can get code mode hat, we have a careers page on cloudflare.com. And I'm going to talk tomorrow about how you can use code mode in your MCP server to give access to all 2,600 API endpoints of Cloudflare in just only 1,000 tokens. So, code mode like this this idea of being able to generate code that you then run is super super powerful. I don't think we have enough time here to like fully explain how that works, so I would just ask to come to our talks.

</details>

**Sunil**: 是的，我一直这样跟别人解释，在过去的 20 多年里，他们一直告诫你，永远不要在代码中使用 `eval`。事实上，在 Cloudflare Workers 中，你甚至根本没有 `eval` 这个选项。这很危险。但是我们把它拿来了，而 Dynamic Workers 就像是 `eval++`。

<details>
<summary>Original English</summary>

Yeah, you should have like so the way I've been telling it to people is for the last 30 years, 30 20 something odd years. You go to being such an old guy in the room so fast. They've told you never to use eval in code. In fact, on Cloudflare workers eval you don't have eval. It's dangerous. But we took it and dynamic workers are like eval plus plus.

</details>

**Sunil**: 仿佛科技树中有一个完整的分支，我们已经差不多 30 年没有探索过了。而现在，我们为你提供了一种快速、安全且廉价的方法。你们必须亲自去试一试然后告诉我们。你们将有机会重新思考构建界面以及事物运作的方式，尤其是在一个所有用户都会编写代码的世界里，对吧？

<details>
<summary>Original English</summary>

So, I think about it how there's an entire branch of the tech tree that we haven't explored in like 30 years. And now we are giving you a fast, secure, and cheap way. Is there such a thing as fast good fast and cheap? Yeah. Maybe it's not good. I don't know. You have to try it out and let us know. And you get to reconsider the way you build interfaces and how things happen, especially in a world where all your users can write code, right?

</details>

**Sunil**: 这就是 Dynamic Workers。这非常酷，我在玩这个东西的时候找到了很多乐趣。我们要不要再剧透一点其他东西？

<details>
<summary>Original English</summary>

That's so that's that's dynamic workers. That's like It's pretty cool, man. Like I've been having a lot of fun playing with this. It's very new. Should we tease some stuff or do you want to talk about We had we had some other releases previous recently.

</details>

**观众**: 我有个问题。你们显然超级懂。我很难找到一种方法，把我正在构建的所有东西映射到你们描述的这个世界中去。我只是想听听你们的看法：行业里有哪些正在被大家构建的东西，其实根本不应该那样去构建。他们应该用你们这种方式来构建。我有个很好的轶事，我很乐意给出一些例子。

<details>
<summary>Original English</summary>

Go on. Yeah, question. I have a quick one like cuz I think it sounds like you guys are I mean you obviously are like super you know Maybe this is just me. I'm struggling to find a way to like map all the things that I'm building to this world. I don't quite know if it's just me or I'm trying to find a bridge. I just want to hear some of like what you think people are building in the in the industry that like they really shouldn't be building it like that. They should be building it this way. I I've got a good anecdote. That would be very helpful to you. I'd love to give examples. Okay.

</details>

**Matt**: 让我们举个例子，我们每人说一个。

<details>
<summary>Original English</summary>

Let's let's give an example We do one each. I should I mean we'll do five each. Go ahead.

</details>

### 用例：Generative UI 与可恢复流式传输

**Sunil**: 好的。我们来这里就是为了推销的，兄弟。我最喜欢的例子是目前业界非常流行的 Generative UI（生成式 UI）。大家基本上在生成 JSON 然后去渲染它。为什么你要生成 JSON？为什么不直接生成 HTML，甚至直接生成 React 代码，然后直接渲染呢？

<details>
<summary>Original English</summary>

Okay. So, um I mean we're here to shill, bro. Like that's So, my favorite example is the there's a big thing going around about generative UI at the moment. And people are basically Have you heard of Jason Bender? Yeah. You're like generating JSON that then you render. It's kind of the name. Why are you generating JSON? Why don't you just generate HTML or even generate React and then just render that?

</details>

**Sunil**: 因为某些平台没有用来渲染不可信代码的原语。如果你能这样做，你完全可以让运行在云端的 AI agents 生成代码，并将这些代码直接渲染到 UI 中。像 **Claude Artifacts** 就是这样，它只是 HTML 并在浏览器上渲染，所以人们不在意安全性。但是如果在服务器上渲染，事情就变得棘手了。于是人们觉得需要 JSON。但你现在不再需要 JSON 了，你可以直接渲染 React。

<details>
<summary>Original English</summary>

Well, why why why can't you do that? Well, some platforms don't have a primitive to render untrusted code. Well, if what happens if you did? You could literally get your users get your get your get your customers get your client codes get your agents living in the cloud to generate code that they run that then is rendered in the UI. Like anyone tried Cloud Artifacts?

That's basically yeah, that's it, right? It's just HTML but it's rendered on your browser. So, people don't care so much about that security. What they care about is when they're rendering it on their servers. That's that's when it starts getting a little bit dodgy. And now they're like right, you need JSON. You don't need JSON anymore. You could render React. And that's this is how you build it. So, this is like there's one fun thing here.

Yeah, do you want to do the next one? Which feature? Dynamic workers. Dynamic workers. Yeah, yeah, yeah, workers.

</details>

**Matt**: 我来说个简单点的例子。假设你想构建一个可恢复的流式传输（resumable streaming）。你让 LLM 讲一个长篇故事。然后在讲到一半的时候按了刷新键。你该如何确保流式传输能够继续进行？

<details>
<summary>Original English</summary>

I'll go like a little simpler. Okay, so because our agent thing is like not is more of the execution environment than the library you use. Like you can use LangChain AI SDK, anything with our agents SDK. We give you that. But because there are these durable object model, it means let's say you wanted to build resumable streaming. Okay, so you tell the LLM give me a long story. And you hit refresh in the middle of it. How how do you make sure it continues streaming?

</details>

**Matt**: 在一个 serverless 的世界里，你需要数据库、副本复制和粘性会话。而在 Durable Objects 和 Agents SDK 的世界里，你只需重新连接到它，如果有一个数据流正在进行，它只会说这是数据流的开头，然后继续向你发送字节。这意味着你会自动获得跨标签页、跨浏览器的同步功能。这些功能开箱即用。我们最初使用 Durable Objects 的杀手级用例，就是为了构建实时协作同步功能。

<details>
<summary>Original English</summary>

In a serverless world. Okay, now you need to do a database, you need to do replication, you need to do sticky sessions. In the durable objects world in the agents SDK world, you just reconnect to it and if there's a stream going on, it just says well, here's the beginning of the stream and I'm just going to continue giving you bytes. It means that you automatically get multi-tabs multi-browser sync. Like you're looking at your phone and the laptop same time. All of these things come out of the box for you. In fact, like the killer use case where we started with durable objects was for building real-time collaborative sync.

</details>

**Sunil**: 我坚信 AI 应该是一个多玩家游戏。你有没有注意到，为什么我不能把我的 ChatGPT 对话链接分享给你，然后我们在同一个对话中操作？那是因为 **OpenAI** 还没有构建这个功能，他们可能觉得有一半的员工每隔三个星期就辞职了，有更大的问题需要解决。

<details>
<summary>Original English</summary>

Now, I'm a believer that AI should be a multiplayer game. You have you noticed like why can I not share a link to my chat GPT chat with you and both of us work in the same conversation? It's because OpenAI hasn't like built that and they're like oh, we have like bigger problems to solve. Half our people quit like every 3 weeks or something like that.

</details>

**Sunil**: 事实证明，有了像这样的原语，你就不必在用户态（userland）修补，不用逼自己成为疯狂的分布式系统工程师。你只需要把它变成 Cloudflare 的问题。虽然我说是我们的问题，但我们只是在上面写写 JavaScript。

<details>
<summary>Original English</summary>

It turns out like with primitives like this, you don't have to patch it in userland and become this crazy distributed systems engineer. You make it Cloudflare's problem. Well, our problem. Well, I say our problem but we take credit for the people who actually build it. We do the JavaScript on top of it.

</details>

**Matt**: 我非常喜欢开箱即用的同步和流式传输功能。这意味着你可以专注于你真正关心的事情。那是真正的杀手级演示。展示那个同步功能就已经非常有趣了。

<details>
<summary>Original English</summary>

So, I really like that. Like the fact that you get sync, streaming, etc. out of the box. It just it means you can play with you can build your you can focus on the things that like you care about. That's the killer demo, isn't it? I I like it so much. Like just showing like the sync is just so fun. Because then it like unlocks they're like oh, okay, fine. If you can do that, I'm going to worry about making money. It's it's a fun thing to do. Would it be fair to say we'd be able to Cloud Code's Cloud interface which just Should we start leaking secrets? Yeah, we can start leaking secrets now. Okay.

</details>

### Cloudflare 的代理沙盒生态

**Sunil**: 想象一下，一个在 Agents SDK 中运行的智能体处理后端。现在你有一个持久运行的服务器。你可以从终端、手机、iOS 应用、Web 应用等任何客户端连接到它。所有的东西都会在所有客户端之间同步。一切都是可恢复且有状态的。

<details>
<summary>Original English</summary>

Um yes. Yes. Yes. Yeah. So, so there's some cool things you can do here. Um because imagine an agent loop that ran in the agents SDK that did the back end of Cloud Code. Now, you have a server that runs that's persistent and you can connect to it from any client. So, a terminal, from a chat, from a phone, from an iOS app, from from a web app. It doesn't really matter. Like like everything is synced between all between all of your clients. Everything is resumable. Everything is stateful.

</details>

**Sunil**: 现在轮到 Cloudflare 来构建一个工作流控制层（harness）了，一个纯粹运行在 workers 上的代码生成智能体。我们要构建那个吗，伙计？

<details>
<summary>Original English</summary>

And I guess So, I guess it's up to Cloudflare to now build a harness, right? A coding agent that runs purely on workers and you're Should we build that, man? Should we should we be building this?

</details>

**Matt**: 我们确实正在构建它。我们希望很快就能发布它。我们的理念是，你不仅拥有可快速启动和关闭的有状态的 AI agents，而且它们具备即时生成代码并瞬间运行的能力，开箱即用地支持恢复性。并且，我们的团队也负责 Cloudflare 的 Sandbox SDK。

<details>
<summary>Original English</summary>

Well, we're building it just so we're clear. If I wasn't obvious enough, we hope to ship it imminently. It just like the the conference is taking my time away from burning tokens is what it is. As quickly as I can go back to that. No, but no, we believe in that world. Look, everyone's building a harness and everyone's leaning into the benefits of their infrastructure or their philosophy. This is ours. Where not only do you have these spin-up spin-down stateful agents, but with capabilities of generating code on the fly and running it like instantly, really fast, resumability, etc. out of the box. And if you want to delegate to a big container, you should absolutely be able to do that. We have Well, our team also handles sandbox Cloudflare sandbox SDK.

</details>

**Sunil**: 你想用 Daytona 等产品运行也可以。但是，Workers 和 Agents SDK 会成为连接所有组件的核心枢纽（nexus）。这就是我们的愿景。这将会比预期更快地实现。那之后你将如何创造一个能够自己创建技能的系统？你发一条语音消息给它，它就会告诉你：我已经设定了一个非常棒的定时计划。

<details>
<summary>Original English</summary>

You want to run it in a browser? Well, we have a browser. You don't really have to use our stuff. You want to use Daytona, a great product by the way. I love their sandbox stuff. You want to use browser use or you want to run What's the light panda? Is that what it's called? You can do that. But workers and our agents SDK becomes the the nexus of where like it connects all of the things. That's the vision we have. It's uh It's happening sooner than later. How would you then create a Cloudflare, particularly one that can like create its own skills? Cuz I think that for me is the the thing I love the most. You'd be able to just say like send it a voice message and it says I've got a cron that does really great thing now.

</details>

**Matt**: 我们直接在 Durable Object 里内置了 SQLite，你也可以把东西存在 **R2** 里。虽然目前还得自己连接组件，但很快就不需要了。什么是开放云（open cloud）？你需要一个拥有心跳机制、拥有虚拟文件系统、并且能与各项服务相连接的东西。你还需要扩展（extensions），这意味着你需要能够生成并在安全的沙盒环境中运行代码。

<details>
<summary>Original English</summary>

So, so we have um we have a bunch of storage solutions. Uh we have one in the durable object. So, we have like SQLite directly in the durable object. So, you can store stuff there. You can store stuff in R2. And all of that at the moment you have to kind of wire up, but imminently you won't. All right. So, here's the thing. What is open cloud? You want a thing that has a heartbeat. You want a thing that has a virtual file system. And you want a thing that's connected to services. Exactly. And you want extensions. Which means you want to generate code that's run in a safe sandboxed environment.

</details>

**Sunil**: 我今天早上刚实现了扩展功能。它在我们的平台上运行得非常完美。我们非常喜欢 Pi 代码智能体，事实上，我们也想直接在 Workers 上运行 Pi。我们现在正没日没夜地在这上面工作。如果不是为了在座的各位，我现在已经在烧 tokens 了。

<details>
<summary>Original English</summary>

I implemented extensions this morning. It works really well on our thing. By the way, I'm friends like with Mario. Hi Mario. And yeah, 100%. We love Pi by the way, the Pi coding agent. In fact, we want to run Pi directly on workers as well. We've been talking to him about it. Because why not? But this is the future. Yes, we're we're working I'm we're working non-stop on this right now. If it wasn't for you people, I'd be burning tokens. Do you have any more questions? How much time do we have? I don't even know how long we have.

</details>

### 多语言支持：Python、Zig 与 WebAssembly

**观众**: 你们考虑过支持 Python 吗？

<details>
<summary>Original English</summary>

Would you like Python?

</details>

**Sunil**: 我们也会支持 Python。Dynamic Workers 和 Workers 本身已经支持 Python。Python 是一等公民，JavaScript 是一等公民。其他所有的语言都是通过 WASM 支持的。我们最近一直在玩的是 **Zig**。Zig 最棒的一点是，它的 WASM 编译包相较于 Go 和 Rust 来说体积小得可怜。

<details>
<summary>Original English</summary>

Amazing. So, we'll do Python as well. The dynamic workers and workers itself supports Python. You just need to spend a little time like polishing the rough edges. Python is first class. JavaScript is first class. Everything else is WASM. The thing we've been playing with lately is Zig. Our boy here is one I think you're the first person bring Zig into production in Cloudflare workers for a bunch of things that we actually cannot talk about today. But Zig the nice thing about Zig is the WASM bundles are like tiny compared to like Go and Rust.

</details>

**Sunil**: 对于其他语言使用 WASM，如果原生运行它对你来说很重要，你可以启动一个容器执行任务。话虽如此，在现阶段你的 LLM 都在帮你写代码了。管它是 JavaScript 还是什么别的语言，其实已经没那么重要了，对吧？目前的基础设施，一等公民是 JavaScript 和 Python。

<details>
<summary>Original English</summary>

So, other languages do we do WASM or if it is that important to you to run it like natively, you spin up a container instead. Again, like we have a first class SDK that lets you spin it up and do things. That being said, brother, your LLM is writing code at this point. Like, why does it matter, right? Like, whether it's JavaScript or not. That's That's kind of my point as well. Like, what if if if you write whatever it was Yeah. Yeah, yeah. So, the infrastructure right now, first class is JavaScript Python.

</details>

**Sunil**: 我是一个 React 程序员，所以觉得 Python 太难了。但是我们会支持的。我们现在甚至有一个能让你直接在 Worker 里面运行打包器（bundler）的东西，叫 worker bundler。它能从 NPM 拉取依赖项，剥离类型、JSX 等生成你想要运行的东西，它会利用 Cloudflare 的缓存来获取依赖而不用担心 NPM 宕机。

<details>
<summary>Original English</summary>

Uh and uh as you could tell, I'm a React programmer, so I'm like, "Eh, Python too hard." Uh but no, we'll polish off those rough edges and we'll do that as well. Hell, we have a thing which lets you run a bundler inside a worker right now. It's literally called worker bundler. It pulls down dependencies from NPM, strips out types, JSX, TypeScript, all of that, and generates like the thing that you would like run inside it. So fun, because then it uses the Cloudflare cache for dependencies instead of worrying about NPM uh downtime. It's quite nice.

</details>

**观众**: 当你提到现在还必须手动把 SQLite 存储连接起来，并且说以后就不需要了，你所说的“很快”是什么意思？

<details>
<summary>Original English</summary>

All right. Uh when you said you have to wire up the SQLite storage right now and so you won't, what What do you mean by soon?

</details>

**Matt**: 哦，不是的，它其实已经可以使用了。它被称为 `@cloudflare/shell`。它为你提供了一个完整的文件系统——底层既叠加在 Durable Object 的 SQLite 之上，也叠加在用于处理更大文件的 R2 之上。它今天就可以使用了。我不太想谈论那个项目的黑历史。

<details>
<summary>Original English</summary>

Um Oh, no, it actually works. It's called atcloudflair/shell. Uh the APIs shouldn't break, uh but it's usable today. Uh it gives you a full file system inside uh layered on top of both durable object SQLite and R2 for like bigger files. I see. It works today. You can use it today. Actually, that's just it. I I don't want to talk about the history of that project. Uh anything else? He searches his own name on Twitter, you'll find the history of that project. Yeah, it was a little dramatic.

</details>

**Sunil**: 我们上周推出了一款名为 **M-** 的 CMS 系统。它完全运行在 Workers、Durable Objects 之上。M- 最棒的地方在于，它的插件系统完全建立在 Dynamic Workers 之上。你可以锁定运行这些插件的环境，开箱即用地安全运作。而且它实际上可以完全部署在任何平台上。

<details>
<summary>Original English</summary>

Uh anything else I can help you folks with? Anyone want free credits and Like I said, friends and family company, so. Uh we I don't know if you wanted to talk otherwise about the new CMS that we launched last week. Uh it's called M- Great name for a product in this day and age. Uh it runs fully on Workers Durable Objects, etc. And like, the nice thing about M- is the plugin system is built fully on dynamic workers. So, So, you know how like WordPress has a bunch of security incidents of its plugins? Well, you just lock down where you run the plugins, and it just works out of the box. M- otherwise deploys actually completely on any platform. It's not Cloudflare specific, and we are working on other platform support for this dynamic worker bit that we that we have right now.

</details>

**Sunil**: 我们有一个完全运行在 Wheat 上的 **Next.js** 版本，使用起来非常有趣。

<details>
<summary>Original English</summary>

Yeah. Uh other things is We Next. We have a version of Next.js that runs fully on Wheat, and it's so fun to use. Uh what else do we What do we do, bro? What do we do?

</details>

**Matt**: 下周是我们公司的 Agents Week，所以下周你们会看到很多来自我们的消息。我们会宣布一大堆有趣的东西。

<details>
<summary>Original English</summary>

Uh the problem is it's like next week is our in one of our is our Agents Week, so you'll be seeing a lot from us next week. Oh, yeah. Like, twice a year we have these announcement weeks where we get really noisy, and next week's is going to be particularly noisy, where we announce a bunch of fun stuff. Yeah. Any more questions? Go on.

</details>

### Cloudflare 的定价理念与结语

**观众**: 今天我们要来回答一些“朋友和家人”提问了。请发送你们的账户 ID，也可以选择性地附上贿赂。

<details>
<summary>Original English</summary>

going to come friends and family questions for us today. Uh send account ID and optionally bribes.

</details>

**Sunil**: Cloudflare 之所以如此便宜，是因为十年前做出的决策。我们不建造庞大的数据中心，而是在 ISP 附近安装硬件。我们从顶级的 ISP 那里大量批发带宽，并且签署协议，在跨越边界传输字节时实际上不需要为此付费。我们的免费账户并不是营销支出。这仅仅是这门生意的构建方式。

<details>
<summary>Original English</summary>

See, it's You can consider it a bribe or protection money. Like, I'm trying to also develop a little like mafioso vibe around that. Uh but no, dude. Like, we we The way that Cloudflare is constructed, the reason it's so cheap is because of decisions made 10 years ago. We don't build massive data centers. Instead, we install hardware near ISPs. We buy bandwidth in bulk from uh level zero like top level ISPs, and we do agreements where bytes that cross boundaries, you don't really pay for it and stuff. So, our free accounts aren't marketing expenditure. It's just how the business is constructed. Uh and I need more people to know that.

</details>

**Sunil**: 我一直在想，“他们怎么能把它卖得这么便宜？”不然的话它就是每个月 5 美元，而且我们知道有人在这之上构建了价值数百万美元的 SaaS 应用。但是，如果你想花不到 5 美元，我们可以交个朋友。

<details>
<summary>Original English</summary>

Like, I spent a a bunch of time. I was like, "How do they give it out for so cheap?" So, it's otherwise $5 a month, and we know people building multi-million dollar like SaaS's on top of that. But, if you want less than $5, well, we can become friends friends with us. That's cool. I think Uh other fun stuff we have

</details>

**Matt**: 时间到了吗？我们在展厅里有一个展位。我今天下午 5:40 有一场演讲。他明天也会有一场演讲。你们应该去看看这两场演讲。为了这次活动，我还专门理了个发呢，伙计们。欢迎过来和我们聊天。访问 `agents.cloudflare.com` 获取所有的文档。在 `github.com/cloudflareagents`，你可以提交 Issue。非常期待看到你们能够构建出什么样的东西。

<details>
<summary>Original English</summary>

Uh is that time? Oh, well, I guess we are at time. How's no one knocking at Oh, you are you are I'm so sorry. Uh especially after we made a thing about the previous session. Thank you so much. We have a booth on the expo floor. I'm speaking today at 5:40 p.m. He's speaking tomorrow. You should watch both talks. Uh like, look at us. Like, uh I got a haircut for this, you guys. Like, like Uh it's going to be fun. Also, just come hang with us. We love just like chatting with people. Uh agents.cloudflare.com or developers.cloudflare.com/agents for all the docs. Uh github.com/cloudflareagents, you can file issues. We love That's just it. Like, have your clan curl talk to our clan curls. Uh and uh looking forward to seeing what you build.

</details>