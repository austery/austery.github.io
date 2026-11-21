---
author: Latent Space
date: '2026-03-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=nxnQl4AcqFg
speaker: Latent Space
tags:
  - type-safety
  - code-execution
  - ai-observability
  - llm-agents
  - python-interpreter
title: Monty：AI 代理的超高速 Python 解释器——Pydantic 的 Samuel Colvin 访谈
summary: 本访谈中，Pydantic 团队的 Samuel Colvin 深入探讨了他们新推出的超高速 Python 解释器 Monty。他分享了 Monty 的灵感来源，解释了其如何在传统工具调用与沙箱之间找到定位，尤其强调了其在类型安全、低延迟和企业级应用方面的独特优势。Colvin 还阐述了 LLM 在加速代码实现（尤其是标准库和测试生成）中的巨大潜力，并对比了不同的 AI 编程助手。最后，他展望了可序列化代理的未来发展，及其在代理优化和状态管理中的应用。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Pydantic
  - Anthropic
  - OpenAI
  - Google
  - Cloudflare
  - Walmart
  - Prefect
products_models:
  - Monty
  - Pydantic AI
  - Logfire
  - Pyodide
  - Devon
  - Claude Code
  - Gemini CLI
  - Opus 4.6
  - Genai prices
media_books: []
status: evergreen
---
### 访谈开场

**主持人**: 欢迎回到 Lind Space 现场直播间。今天我们邀请到了来自 **Pydantic** 团队、最近推出了 **Monty** 的 Samuel Colvin。欢迎。

<details>
<summary>Original English</summary>

**主持人**: Welcome back to the Lind Space uh live studio. Uh we are here with Sam Kovvin from Pyantic who's recently launched Monty. Welcome.

</details>

**Samuel Colvin**: 非常感谢邀请我。很高兴再次来到这里。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Thank you so much for having me. Yeah, it's great to be back.

</details>

**主持人**: 自从我们上次见面以来，你过得怎么样？Pydantic 和 **Pydantic AI** 最近如何？

<details>
<summary>Original English</summary>

**主持人**: How have you been since the last time we saw you? How's uh Pyantic and Pidantic AI?

</details>

**Samuel Colvin**: 我们上次是什么时候聊的？大概一年前吧？

<details>
<summary>Original English</summary>

**Samuel Colvin**: When did we last speak? Like about a year ago, I'm guessing.

</details>

**主持人**: 是的，没错。你当时刚推出。

<details>
<summary>Original English</summary>

**主持人**: Yeah, exactly. Yeah, you just launched it. Yeah,

</details>

**Samuel Colvin**: 嗯，我不想沉溺于“太疯狂了”之类的陈词滥调。吹嘘一下。吹嘘一下。是的。但我的意思是，一切都变了。倒也不是说我们没有过得很开心，而是一年之内一切都变了。比如，如果我们在去年这个时候谈话，你告诉我，我当时基本上还在嘲笑那些说自己不读代码的人，而现在，我正在用 **AI** 构建这个，如果你愿意，可以称之为 Python 的“简陋分支”。我认为它非常强大，我为此感到自豪。但这是一个疯狂的世界，你可以在圣诞节期间坐下来写 30,000 行 **Rust** 代码，而且这些代码确实强大且有用。是的，很多事情都变了。我认为 Pydantic 的 **Logfire**，是我们的**可观测性**平台。那么，对于一个可观测性平台，一个 AI 原生可观测性平台，这意味着什么呢？

<details>
<summary>Original English</summary>

**Samuel Colvin**: Well, I mean, I don't want to indulge in all the cliches of like it's been crazy, yada yada yada. Brag a bit. Brag a bit. Yeah. But I mean, no, I meant there's like everything has changed. Not not so much. I mean, sure, we've had a great time, but like everything has changed in a year. I mean, LA, if we had spoken this time last year and you told me, you know, I I basically was slightly laughing at anyone who said that they weren't reading all their code and now [snorts] here I am building this like if you want to be porative slop fork of Python, mostly with AI. I I think it's incredibly powerful. I'm proud of it. But like this is a crazy world where you can sit down over Christmas and write 30,000 lines of Rust that that is actually powerful and useful. Yeah, the loads of stuff has changed. I think a pantic logfire, our observability platform. And what does that mean for an obser observability platform? What does that mean for you know an an AI native observability platform?

</details>

### AI 原生可观测性平台 Logfire

**Samuel Colvin**: 我们有点特别，因为我们主要将自己与其他的 **AI 可观测性**平台（如 **Brain Trust**、**Langmith**、**Langfus**）区别开来。但我们实际上是**全方位可观测性**，完全**开放遥测**。你向我们发送日志、指标和追踪。我们的定价比其他通用可观测性服务便宜一些，而不是贵 50 倍。但我们做了很多 AI 相关的事情，比如评估、提示词演练场、**LLM** 追踪等。我认为人们对 AI 可观测性有两种理解：为 AI 提供可观测性，以及用 AI 实现可观测性。我们两者都做。特别是 **Logfire** 允许你编写任意 **SQL** 查询数据。我不认为我们在 MCP 服务器中做了什么特别的事情，但因为 AI 可以直接编写 SQL，这比许多平台上的功能强大得多。我们基本上实现了 AI SRE 的体验，而无需人工干预，因为 AI 可以自行编写 SQL，它可以发现错误，显示 P95 下最慢的五个端点，或者对某个属性进行随机调查。如果你没有在 2023 年做出允许用户编写任意 SQL 这种奇特的决定，这是不可能实现的。

<details>
<summary>Original English</summary>

**Samuel Colvin**: So we're weird because we're the only I guess we mostly consider ourselves against the other AI observability platforms. Brain Trust, Langmith, Langfus, those guys. But we're actually full observability, full open telemetry. You send us logs, metrics, traces. Our pricing is a bit cheaper than other general observability rather than 50x more expensive. But we do lots of the AI stuff, the evals, prom playground, LLM traces, all that stuff. And then, and I suppose the people mean two things by AI observability. They mean observability for AI and AI for observability. We do a bit of both. in particular because Logfire lets you write arbitrary SQL to query your data. I don't think we've done anything particularly special in our MCP server, but because the AI can just go write SQL, it's way more powerful than I think on many platforms. We basically have like the AI S sur experience without having to do anything because the AI just goes and write a SQL and it can it can find a bug or it can show you the five slowest end points by P95 or it can go do some random investigation on some attribute which isn't possible if you don't happen to make this like weird esoteric decision back in 2023 to allow arbitrary SQL from your users.

</details>

### Monty 的灵感与起源

**主持人**: 是的，如果允许那样做，听起来像一场噩梦。那么你是在圣诞节期间启动了 **Monty** 项目，灵感是什么？它的起源故事是怎样的？

<details>
<summary>Original English</summary>

**主持人**: Yeah, that is seems like a nightmare if you allow that. So you started Monty over Christmas. What's the inspiration? What's the origin story?

</details>

**Samuel Colvin**: 实际上，我几年前就有一个非常早期的版本，但后来完全放弃了。然后我与 **Anthropic** 的大约四个人交流，他们每个人都独立地提到**类型安全**的重要性。因为我认为类型安全对人类很重要，但对 **AI** 来说至关重要。我经常和人们说这一点，有些人会点头，有些人不会。但这四位来自 Anthropic 的人，每个人都独立地说：“是的，如果你正在链式调用工具，或者使用代码进行工具调用，类型安全就非常重要。” 当他们中的第一个人与我交流时，我就觉得他们肯定在思考什么。我觉得 Anthropic 很有趣，因为他们是最神秘的公司，但每个人都对 Anthropic 内部发生的事情感到兴奋，他们都会向你暗示当前正在进行的任何事情。很难抗拒，对吧？但这也意味着你在和开发者交谈，而不是营销人员。营销人员是不会看到任何东西的，因为你没有……

<details>
<summary>Original English</summary>

**Samuel Colvin**: So I actually had had a like very early version of this that I had done a couple years ago and had completely abandoned and then I spoke to maybe four different people at anthropic and each of them independently. I like did my standard thing about how important type safety is because I, you know, I think type safety is important for humans but it's critical for AIs. And I say this to people all the time and some of them nod and some of them don't nod. But like these four people I spoke to are anthropic. each independently said, "Oh yeah, type safety is super important if you're chaining tool calling or if you're like using using code for tool calling." And when the first fourth of these people spoke to me, I was like, they're obviously thinking about something. I find Anthropic hilarious cuz they're like the most secretive company and yet everyone gets excited about whatever's going on inside Anthropic and suddenly everyone and they all hint at you about whatever it is that's going on at the moment. It's hard to resist, you know, but it also means you're speaking to the builders, not the marketers, right? The marketers won't see anything because you don't

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Samuel Colvin**: 所以我开始构建它，果然在去年 12 月份，他们发布了一个程序化**工具调用**的功能，然后又有一个关于使用代码调用 MCP 服务器的功能。**Cloudflare** 某种程度上发明了**代码模式**（code mode），或者至少是发明了这个术语并大力推广。

<details>
<summary>Original English</summary>

**Samuel Colvin**: And so I kind of started building it and then sure enough in whatever it was December, they came out with a programmatic tool calling piece and then there was another one on uh using code to call MCP servers. Cloudflare kind of invented code mode or at least invented the term and have like pushed it hard.

</details>

### Monty 在工具调用与沙箱之间的定位

**Samuel Colvin**: 后来我与一位一直在关注**沙箱**领域的投资者交流，他说他猜测 70% 的沙箱调用本质上是**工具调用**或其升级版，无论是渲染图表还是进行计算，这些操作实际上不需要完整的计算机使用权限，但编写代码却非常强大。所以，**Monty** 试图介于简单的工具调用（非常安全、相对容易实现、不需要外部基础设施，但对 LLM 的表达力不足）和沙箱（表达力更强，可以做更强大的事情，但其成本反而是其次，主要是设置复杂性）之间。对于初创公司来说，将信用卡绑定到 **Modal**、**E2B** 或 **Daytona** 还不算太糟。但对于需要自托管一切的大型金融机构，这些就不是可行的方案。因此，对他们来说，为我的代理添加工具调用或代码模式基本不可能。当然，对于经济上无法负担的用户也是如此。但从客户角度来看，其强大之处在于企业端，对他们而言，仅仅使用沙箱并不是一个特别简单的解决方案。另一个巨大的优势是**延迟**。如果你的 **Python 解释器**可以在同一个进程内运行，那么启动时间就会非常快。我的意思是，在热循环中，我们可以从代码到执行结果在 800 纳秒内完成，即不到一微秒。实际上，运行代码或执行下一步骤，或者调用主机上的函数，通常都在个位数微秒内完成。而例如为我创建一个 Daytona 沙箱则需要一秒钟。当然，恢复沙箱时不会那么慢。但你知道，这些在时间上是巨大的差异。

<details>
<summary>Original English</summary>

**Samuel Colvin**: And then actually I was speaking to I spoke to an investor who had been looking at the sandboxing space and he said his guess was that 70% of sandbox invocations are basically this like tool calling or glorified tool calling whether it be like to render a chart or do a calculation stuff that doesn't actually need like full computer use but where writing code is very very powerful. So yeah, Monty attempts to slot in between simple tool calling which is very safe and relatively easy to implement, doesn't require external infrastructure, but isn't that expressive for the LLM and like sandboxes which are much more expressive, you can do much more powerful things, but they require well the cost is actually the least of it, right? It's the it's the complexity of setup which is not too bad if you're a startup and you can just go and put your credit card into Modal or E2B or Daytona or whoever. But if you're a massive financial institution and you need to self-host everything, those are not an option for you. And so just add tool calling to add code mode to my agent is like basically not not possible for them. Obviously also true for people who can't afford it. But like from [snorts] a customer point of view for us, the the power is on the the enterprise side where just use a sandbox is not a particularly easy solution. And then the other massive win is latency because if you can have a Python interpreter that runs inside the same process, you're looking at a boot time. I mean in a hot loop we can run we can go from code to execution result in under a microcond in like 800 nconds. In reality it's like singledigit microsconds to run code or singledigit microsconds to run the next step of a ripple or singledigit microsconds to call a function on the host. Whereas if you're like creating um Daytona sandbox for me was taking one second. Obviously it's not as bad as that for like resuming. But you know these are these are big differences in terms of time.

</details>

### Monty 与 Pyodide 的对比及开源优势

**Samuel Colvin**: 是的。我认为现在是展示屏幕的好时机，我知道你有一个非常好的对比表格，我喜欢……你知道，它显然是一个 **Python 解释器**，所以它能运行 Python，对吧？我不知道你还会演示什么。是的，我现在可以分享我的屏幕，我可以展示那个表格并进行解释。我会直言不讳地指出，这是有**权衡**的。我不是……我希望看到设计空间是怎样的，对吧？因为这完全是一个设计问题。所以，这是 **GitHub**，显然有 6,000 颗星，而且还在增长，这对于一个**开源项目**来说令人难以置信，但你在这方面非常擅长。如今你在开源领域有着良好的声誉。我们通常在下载量方面比星标表现更好，但是的，它确实引起了人们的兴趣。你们会追踪下载量吗？是的，我的意思是目前还不多。我想我们上周大概有 27,000 次下载，这显然是一个不错的数字，但对于维护 Pydantic 的我们来说，这只是个很小的数字。但无论如何，对我来说，这是一种从**类型安全**到**代码执行**的整体安全性的一种逻辑上的演进。但这是一个拥挤的领域。熟悉它的人首先会提到 **Pyodide**，对吧？因为你会想，如果想要一个 **WebAssembly** 轻量级 Python 解释器，就会去找 Pyodide。是的，我们确实这样做了。我们犯了使用 Pyodide 的经典错误。需要澄清的是，我是 Pyodide 的忠实粉丝。维护它的 Hood 是我的好朋友。我对这个项目充满敬意。但事实证明，它在**非浏览器环境**中运行 Python 的方式非常糟糕。所以我们维护了一个叫做 MCP run Python 的东西。我们构建这个项目的一个动力是，人们不断报告 MCP run Python 的**安全漏洞**。解决这些漏洞变得越来越困难，因为 Pyodide 确实在 WebAssembly 中运行 Python，但 WebAssembly 本身并不是隔离的。所以你不能在 **Node.js** 中运行它。如果你在 Node 中运行它，你可以导入 JS 模块，然后运行任意 **JavaScript** 代码来访问宿主。所以你必须在 **Deno** 内部运行它。现在 Deno 允许你设置对文件系统和网络的限制。但随后你必须暴露一堆文件，因为如果你希望它能够下载包，它就必须能够写入 node modules 目录。即使你不允许那样做，Deno 也没有办法控制内存。所以即使有人不能运行任意代码，他们也可以随意地耗尽你的机器内存。我们遇到的另一个问题是有人指出，尽管你无法逃脱 Deno 沙箱，但你可以在 Deno 沙箱内运行任意代码，并基本上污染该服务器。所以每次调用你都需要杀死 Deno 沙箱并创建一个新的。所以你的**延迟**实际上比一个完整的沙箱还要差。就像，是的，我在这里用 Pyodide 运行 1+1 基本上需要 2.88 秒，你可能能够稍微改进一点，解决一些安全问题，但从根本上说它非常**重量级**。当然，即使你解决了所有这些问题，你还需要安装 Deno，然后下载 Pyodide。你可能会看到一些数字，Deno 是 50MB，Pyodide 包是 12MB，要让它运行起来并不轻松。Monty 的一个优点是它最终只是一个**Rust** 二进制文件，你可以通过 **Pippi** 或 **npm** 安装。目前甚至有 PR 支持 **Dart** 和 **Kotlin**。它应该非常非常容易安装。最终，你可以在任何可以运行 Rust 的地方运行它。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Yeah. Uh I think this is a good point to bring up the screen just to show I know I notice you have a really nice comparison table and I like to you know obviously it's a Python interpreter so it can run Python, right? I don't know what what else you would demo there. Yeah, I I can share my screen now and I I can just show that table and talk through and I'll be I'll be blunt about the fact that there are trade-offs. It's not I I want to see like what is the design space, right? Because this is all a design question. So, this is the the GitHub obviously 6,000 stars and still growing which is incredible for an open source project, but you're very good at that. You're you have a well established reputation in open source these days. We're generally better at getting downloads than stars, but yeah, it's definitely struck a struck a level of interest with people. You track downloads for this? Uh yeah, I mean it's nothing yet. I think it's a I think we were like 27,000 downloads last week, which is obviously a nice number, but it's not. Yeah. Yeah. Um those of us who are maintaining Pantic, it's a tiny number. But anyway, so so it's it's kind of like you know this is to me like a logical progression from type safety to just overall safety I guess of a code execution. But this is a crowded space. The the first thing that someone who's familiar with this mentions is pyodide right because you're you're like all right you want a web assembly sort of lightweight Python interpreter you'll go to piodide. Yes and indeed we did that. We made the classic mistake of using pyodide. To be clear I'm a massive fan of piodide. Hood who maintains it is a good friend of mine. I have nothing but respect for pi as a project. It turns out it's a very bad way of running Python in like not in the browser. So we maintained a thing called MCP run Python. And one of the impetuses for this for us to build this is people just kept reporting security vulnerabilities with MCP run Python. And basically solving them got harder and harder because sure Podide runs Python in um in Web Assembly, but Web Assembly is not inherently isolated. So you can't run it with Node. If you run it with node, you can import the JS module and go and run arbitrary JavaScript code to access the host. So you have to run it inside Dino. Now Dino, you can go and set restrictions on what what file system what networking it's allowed. But then you have to expose a bunch of files because if you want it to be able to download packages, uh it has to be able to write to the node modules directory. Even if you don't allow that, Dnode does not have any way of controlling memory. So even if someone can't run arbitrary code, they can om your machine as often as they like. The other problem we had was someone pointed out that although you can't escape the dino sandbox, you can go and run arbitrary code within that dino sandbox and basically taint that server. So every single invocation you basically need to kill the dino sandbox and create a new one. So your latency is actually worse than a full-on sandbox. It's like, yeah, I got 2.8 8 seconds here for running basically oneplus 1 in a piad you might be able to improve that slightly you can work around some of the security problems but like fundamentally it's pretty heavyweight and of course even if you get all those sorted you need to install dino then you need to download piodide you're looking at like I think I might have a number here uh yeah so dino is 50 megabytes the piodide package is 12 megabytes it's not trivial to just go and get it running and one of the nice things about Monty is because it's just a single rust binary ultimately that you can install with Pippi or with npm. There's actually and there's actually PRs to have support for Dart and Cotlin at the moment. It should be very very simple to install. Ultimately, you can run it anywhere where you can run Rust.

</details>

**主持人**: 太棒了。

<details>
<summary>Original English</summary>

**主持人**: Amazing.

</details>

### Monty 的权衡与 LLM 在实现中的作用

**主持人**: 你们做了哪些**权衡**？

<details>
<summary>Original English</summary>

**主持人**: What what trade-offs do you make?

</details>

**Samuel Colvin**: Monty 最大的缺点是它不是完整的 **CPython**。我们正在自行实现所有功能，所以我想我这里有一些比较，说明你可以做什么和不能做什么。我们支持一些标准库模块，比如 **async.io** 和**数据类**，但不支持直接安装第三方库。将来也不会直接支持，也就是说，我们永远无法与 CPython ABI 交互，并安装 Pydantic 或 **NumPy** 等库。目前甚至不能在 Monty 中定义类。我们可能会在某个时候实现这个功能。我们还不支持 `match` 语句，但未来可能会支持。我们不能直接使用标准库。所以我们必须弄清楚要手动实现标准库的哪些部分。这听起来像一项巨大的任务，而且也有些自我牺牲，因为这是一个 Pydantic 运行时却不支持 Pydantic。

<details>
<summary>Original English</summary>

**Samuel Colvin**: So the the biggest downside of Monty is that it is not full CPython. we are implementing it all ourselves and so I think I have some comparisons up here what what you can and can't do. We have a few standard library modules like async.io and data classes that we support little bits of but there's no support for third party libraries just to be installed. There never will be directly as in you'll never we'll never be able to speak the C Python ABI and like install Pyantic or install NumPy or something. You can't yet even define classes in in Monty. You may we may at some point make that work. We don't support match statements yet but we probably will. Like we can't just go go use the standard library. So we have to work out which bits of the standard library we want to manually go and implement. This is sounds like an enormous task and also kind of like uh self-sacrificial that you don't this is a pyantic runtime that doesn't allow pyantic.

</details>

**Samuel Colvin**: 我明白你的意思。我认为非常强大的一点是，我们这里有一个非常简单的例子，是一个在 Monty 中运行标准异步循环的玩笑式示例。但重点是，你可以调用主机上的外部函数，比如这里的 `call_lm`。所以你可以通过注册一个 `fetch` 方法来进行网络请求。你可以通过外部函数调用对 **JSON** 数据进行 Pydantic 验证。所有这些都可以做到。只是这些外部包不会在运行时内部运行。我的意思是，我想说的另一件事是，我曾想实现 Python 中大约 20 个内置函数。我基本上对 **LLM** 说，去实现所有你觉得需要实现、需要经常使用的标准库函数。我们做了一些规划，它就开始运行了 2 个小时。一个经验丰富的开发者需要数周才能完成的工作，在几个小时内就完成了。我的看法是，有四件事，如果你能覆盖这四件事，LLM 的速度不是快 3 倍或 5 倍，而是快 100 倍：
1.  **内部实现**对模型来说是众所周知的，也就是说，它知道如何实现**堆**，如何实现**字节码解释器**。
2.  **外部 API**对模型来说是众所周知的，你不需要解释 Python 应该如何工作，外部接口应该是什么，它在内心深处、在它的权重中就知道了。
3.  **单元测试**非常简单。你只需要问：“它与 Python 匹配吗？”所以它几乎可以自己通过测试。你只需要说回溯需要是字节码，也就是与字节码完全相同。
4.  最后，你根本不需要纠结接口应该是什么。你不需要纠结当你将字符串添加到整数时错误消息应该是什么，或者当你有一系列参数时会发生什么。所有这些都由 Python 定义。所以人类没有必要去争论，它就是行得通。

如果你覆盖了所有这四件事，这就是为什么现在每个人都在用 Rust **克隆 Reddit**。你知道，这就是现在的潮流，因为这四条规则都非常适用。LLM 知道它们内部需要做什么，知道外部需要做什么。单元测试很容易，而且不需要对 API 进行任何修改。如果你能做这四件事，任务的速度就会提高大约 100 倍。所以，我想 Monty 上现在有一个 PR，我承认我还没读过，它实现了 `math` 模块中的大约 50 个函数。我对此 PR 一无所知，我还没读过，但重点是有人启动了一个 LLM，它添加了 800 个测试。或者那可能是完整的现有测试，我需要看看。我不是说我对实现了解那么多。

<details>
<summary>Original English</summary>

**Samuel Colvin**: So I think I I hear you I hear you. I think there's a fair bit that so so what's what's super powerful I think we have a like very trivial example here in this this is a kind of like joke example of running the like standard aantic loop within Monty. But the point is you can call in this case call lm which is a external function on the host which you can just go and call. So you can do you can make a network request by registering a fetch method. You can do some pyanic validation of some JSON data by basically having an external function call. You can do all of that stuff. It's just that those those external packages don't run within the runtime. I mean, I think the other thing to say is like I I wanted to implement the like 20 or so built-in functions available in Python. I basically said to the LLM, go and implement all the standard library functions that you find need to implement, you need to use regularly. We did a bit of planning and it sets off and it goes and runs for 2 hours. And what would have taken uh an experienced developer weeks to do was done in a couple of hours. My take is that there are four four things where if you can if you can cover all four of these things LLMs are not like 3x faster or 5x faster they're like 100x faster internal implementation is well known to the model as in it knows how to in this case implement a heap uh implement a bite code interpreter if the external API is well known to the model you don't need to explain how Python should work what the external interface should be it just knows it in its soul in its weights thirdly Unit testing is really [ __ ] simple. You're just like, does it match Python? So it can almost Ralph itself into into passing, right? You just say the trace back needs to be bite code, you know, to the bite identical. And lastly, you don't have to bike shed at all about what the what the interface needs to be. You don't bike show bike shed about what the error message needs to be when you add a string to an integer or what happens if you have the following sequence of arguments. It's all just defined by Python. So there's no need for the humans to go and argue. It just worked. If you cover all four of those things, that's why everyone is like basically cloning Reddit right now in Rust. You know, that's the kind of meme right now because those four rules all apply really well. There are loads of, you know, the LLMs know what they need to do internally. They know what they need to do externally. The unit tests are easy and there's no bike shedding about the API. If you can do those four things like tasks get like I mean yeah I would say ballpark 100x faster and so you know I think there's a there's a PR on Monty right now which I profess I haven't actually read yet that implements like 50 functions in the math module I don't know anything about this this PR I haven't read it yet but the point is someone has set off an LLM and it's added 800 tests or maybe that's the the full test existing and I need to look at it. I'm not saying I know that much about the implementation.

</details>

**主持人**: 你有一个很漂亮的橙色东西在上面是什么？

<details>
<summary>Original English</summary>

**主持人**: You have you have a nice uh what is that? What is that orange thing at the top? What is that? A

</details>

**Samuel Colvin**: 所以它被插入在这里。基本上，这开始是因为 **OpenAI** 的一位联合创始人向 Pydantic 提出了一个问题，我们披露了它并说它是错误的。所以我们有这个东西，它会自行注入并尝试总结某人，它会给他们一个 1 到 5 的残酷分数。

<details>
<summary>Original English</summary>

**Samuel Colvin**: so it's a it gets inserted here. Basically, this started off cuz one of the OpenAI co-founders created an issue on Pantic and we disclosed it and said it was wrong. [ __ ] And so we have this that like injects itself and tries to summarize someone and it it gives them a like brutal score of one to five.

</details>

**主持人**: 是的，是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. Yeah.

</details>

**Samuel Colvin**: 关于他们的重要性。所以我们基本上不会像下次 Dario 提出问题时那样，直接说那很蠢就关闭它。

<details>
<summary>Original English</summary>

**Samuel Colvin**: On how important they are. So we basically don't go and like when Dario next issue, we're not just going to like say that's dumb and close it.

</details>

### AI 代码审查工具与效率

**Samuel Colvin**: 无论如何，我认为 AI 审查还有更大的空间。我开发过一个 AI 审查工具，像这样的还有很多。我想知道你觉得这些工具是否有帮助。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Anyway, well so so uh I think there's there's more scope for for AI reviews. I have worked on an AI review tool that many many others like there. I wonder if you find those those helpful at all.

</details>

**Samuel Colvin**: 我们在 **Pine AI**，那些家伙大量使用 **Devon**。并且实际上发现它很有用，我们尝试了几个，但其他都没用，只有 Devon……不，也不是说其他都没用，但在尝试了几种不同的选择后，Devon 似乎是现成方案中最好的。我认为我们现在实际上有一个自己的，基本上是基于我们所有的审查进行训练的，它正在并行运行。但是的，我的意思是，如果你看，例如，**datetime** 的实现（它在这里的某个地方）。我想 datetime 已经合并了，但 datetime 的实现涉及大量的代码，但重点是 AI 确切地知道它在做什么，因此它可以非常快地实现它。是的。我的意思是，我已经审查过几次了。我需要合并它。这是一个很大的 PR。有 4,000 多行。但你可以查看测试，最终你会觉得：“是的，果然是测试。”你知道，它基本上会遍历并测试所有东西。当然，关键是这些测试中的每一个都与 CPython 和 Monty 一起运行，并检查输出是否完全相同。所以你知道，这些任务更容易完成。我同意你的观点，实现完整的标准库将是一项艰巨的任务。但我认为没有必要。我认为我们还需要做三四个模块，你只需对 AI 描述，你只能使用以下内容，它在这方面表现得非常出色。对于大量的任务来说，它在可能性以及模型执行任务的效率方面，让代码模式可用，带来了巨大的改变。

<details>
<summary>Original English</summary>

**Samuel Colvin**: We So in pine AI the guys are using Devon quite a lot. Um and actually finding useful we tried quite a few nothing else worked but Devon well not not nothing else worked but like having gone through a few different options. Devon seemed to be the best of the like offtheshelf ones. I think there we actually now have our own one trained on basically all of our reviews that is that is running alongside it. But yeah, I mean like if you look I mean if you look at the for example the datetime implementation which is here somewhere. I think datetime is already merged but like the datetime implementation is an awful lot of code but like the point is that like the API the the AI knows exactly what it's doing and so it can implement it pretty pretty quickly. Yeah. I mean like uh I've reviewed this this a few times. I need to get on a merge it. It's a big PR. It's 4,000 plus. But like you can you can go and look at the tests and ultimately you can be like yep sure enough tests you you know it's basically going to go through and test all of the stuff and of course the point is that every single one of these tests just runs with CPython and Monty and checks that the output is exactly the same and so you you know these are the kinds of tasks that are much easier. I agree with you that implementing the full standard library would be a like a hellish task. I don't think that that's necessary. I think we need to do like three or four more modules and you describe you just say for the AI you don't need to you can only use the following and it's amazingly good at doing it and for an enormous number of tasks. It just makes an enormous difference in in terms of what's possible in terms of how efficient the models are to to perform the task to have uh like this code mode available.

</details>

**主持人**: 是的。太棒了。我觉得软件的**护城河**普遍很小，这很有趣。因为 Pyodide 已经存在了十年，也许更少，但你知道，像 **Redis** 这样的东西也存在了很久。而我们现在突然心血来潮地尝试重写所有这些东西，而且我们确实能做到，这真是太疯狂了。当我们谈到这个话题时，你通常会用 Devon 吗？你肯定会用 **Claude Code**，对吧？有没有什么编程技巧，或者如果你想尝试实现一个完整的运行时，有什么建议？

<details>
<summary>Original English</summary>

**主持人**: Yeah. Amazing. I think it's interesting how little moat software just generally has because your this is piodide pi's been around for I don't know how many 10 years maybe maybe less than that but you know like reddis has been around forever and like here we are trying to rewrite all these things on a whim and we can like we we actually can like this is absolutely crazy while we're on this topic just generally did you uh what you use devon I'm sure you use cloud code yes no um or was that the main thing any sort of coding tips anything you know if people were to try to attempt the same kind of thing like implement a full runtime what advice would you have so I

</details>

**Samuel Colvin**: 我用 **Claude Code** 和 **Gemini CLI**，我主要用 Claude Code，但我用……

<details>
<summary>Original English</summary>

**Samuel Colvin**: use cloud codeex and gemini I use mostly claude code but I use

</details>

**主持人**: **Gemini CLI** 还是 Gemini？

<details>
<summary>Original English</summary>

**主持人**: Gemini CLI Gemini or Gemini

</details>

**Samuel Colvin**: **Gemini CLI**。不过，我的看法是，你可以把它们想象成超级英雄。Claude Code 就像你刻板印象中的美国队长，正直先生。能力很强，大部分事情都做得对。有点过于自信，但还好吧。**Codex** 就像邦德电影里的 Q 先生，一个神经质、书呆子气的人，对一些不那么重要的小细节非常执着。而 Gemini 则像**小丑**，一个精神错乱的疯子，偶尔会做出令人难以置信的工作，但一半时间会删除你所有的文件。我几乎从不让 Gemini 有能力做任何事情，除了……实际上我现在可以给你看。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Gemini CLI although so my take is that like you can think of each of them as if you thought of them as a superhero claude code is like your cliched Captain America like Mr. right? Like pretty competent, does most things right. A bit overconfident, but like whatever, fine. Codex is this like neurotic, geeky, like the kind of Q guy in in Bond, like this neurotic geeky person who's like very specific about little things that don't particularly matter. And then Gemini is like the Joker. It's just this like unhinged lunatic that will occasionally do an incredible job, but half the time just delete all of your files. And I almost never run Gemini with the capacity to do anything other than actually I can I can show you now.

</details>

**主持人**: 是的，请务必。我遇到的 **Gemini CLI** 用户不够多，显然他们正在努力，但他们还没有市场份额。

<details>
<summary>Original English</summary>

**主持人**: Yes, please. I don't meet enough Gemini CLI users which obviously they're working hard on it but they just don't have the market share.

</details>

**Samuel Colvin**: 例如，这是我非常粗暴的审查方式。我只是简单地将其导入 Gemini，而 Gemini 默认不允许编辑任何文件，它只会去审查特定的分支并给我写一份报告。然后我基本上就是把这份报告指向 Claude Code，并说：“实现以下内容。”如果有什么不对劲，我会进行编辑。我对 Codex 也做了类似的事情，效果相当不错。我的意思是，你可以用它做很多更干净的事情。我确信有更优雅的方法。我真的很想开始使用 **Code Puppy**。我只是还没有时间去做。

<details>
<summary>Original English</summary>

**Samuel Colvin**: So for example, this is my like very brutal way of like doing reviews. I just literally pipe that into Gemini and Gemini doesn't is not allowed to by default run like edit any files and it will just go off and like review a particular branch and write me out a report and then I basically just point claw code at that report and say implement the following things. I'll edit it if there's stuff that's wrong and I do something fairly similar with codeex works fairly well. This is I mean look you could you could do lots of cleaner things with this. I'm sure there are more elegant ways of doing it. I really want to start using Code Puppy. I just haven't got around to it yet for this.

</details>

**主持人**: 我从没听说过 Code Puppy。

<details>
<summary>Original English</summary>

**主持人**: I've never heard of Codeuppy.

</details>

**Samuel Colvin**: **Code Puppy** 是 **Walmart** 的一位名叫 Michael Fafesberger 的出色工程师，用 Pydantic AI 构建的一个编程代理。它没有获得很多星标，也没有很多炒作，但我不知道我能公开说多少，但它在开发者和非开发者中获得了巨大的采用，可以基本上自动化他们工作的一部分，这也是我发现它非常吸引人的原因之一。我不会再说更多，因为我不确定我能公开说多少，但你知道，我听过很多关于它的好评，我也想尝试使用它。但你知道，所有开放代码，我的意思是，我发现开放代码愿意妨碍我的滚动，成为一个完整的 **TUI**，对我来说简直是杀手锏。所以我不能，我宁愿老实说选择 Gemini CLI。是的，你只想要简单的来回对话，而不是成为一个完整的用户界面，那样就太多了，对吧？是的，我经常听到这种说法。所以有人对我说，这很有道理，世界上唯一最大的私有代码库是 **Google**，据说 Gemini 就是在它上面训练的。所以，在技术领域，这很有道理，对吧？就像 Monty 并不是普通的“为我构建一个 Web 应用”。它涉及到一些非常技术性的问题，比如如何最好地实现字节码解释器？如何让结构体小几个字节？无论是什么，对吧？这些东西真的令人难以置信，Gemini 知道如何做其他模型不知道的事情。所以我想这就是我尝试它的原因。有时它会带来一些神奇的东西。显然，我需要将它们每个运行三四次，才能进行科学测试，看看哪个最好。我没有这样做。我只是混合使用它们。我认为这是一个合理的理由来思考 Gemini，但你知道，我问过真正的 Google 员工，他们使用一个内部工具叫做 **Jet Ski**。我的意思是，原因很简单，他们有所有其他东西的内部版本。所以如果他们真的将内部版本发布到外部世界，那就毫无意义了。就像它只会引用 Borg，而没有人拥有 Borg。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Code Puppy is a coding agent built by an amazing guy called Michael Fafesberger at Walmart built with Pantic AI and it's got like hasn't got very many stars, hasn't got lots of like hype around it, but I don't know how much I'm allowed to say publicly, but it has got an enormous adoption amongst developers and non-developers to to basically automate bits of their job, which is one of the reasons I find it really fascinating. I I won't say more about it because I'm not sure how much I'm allowed to say publicly, but yeah, it's it's um but you know, I've heard really good things about it and I want to try using it, but like you know, all open code I mean I find open code's willingness to like get in the way of my scroll and be a full TUI is just like killer for me. So I I can't I'd rather honestly have Gemini CLI. Yeah, you want you want just like just only do back and forth. Don't become a full user interface like that that that's too much, right? Yeah. I I I hear that a lot. So someone said to me which makes sense like the single biggest private codebase in the world is Google and supposedly Gemini is trained on it. So it makes sense that in the like very technical end of the spectrum, right? Like Monty is not your average like build me a build me a web app. Like it's there are some very technical like what's the best way of implementing a bite code interpreter? How can I make the strct a few bytes smaller? Whatever this might be, right? That stuff really credible that the things that Gemini knows how to do that other models don't. And so that that's I think that's my reason for trying it. Sometimes it comes up with something magic. Obviously, I would need to run each of them three or four times to like do a scientific test of which one's best. I haven't done that. I just use use a mixture of them. I think it's a reasonable story to to think about Gemini, but like uh you know, I've asked actual Google people this uh they use an internal thing called jet ski. And I mean, the simple reason is they have internal versions of everything else. And so if they actually train the they release the internal version to the external world, it would just make no sense. Like it would just reference Borg and nobody has Borg.

</details>

**主持人**: 有趣。所以你认为它实际上并不是在很多……

<details>
<summary>Original English</summary>

**主持人**: Interesting. So you think it's it's not actually trained on much of

</details>

**Samuel Colvin**: 它不是直接训练的，但可能受到启发，这已经足够接近了。但“训练”是一个非常具体的说法，如果它是直接训练的，模型会吐出一些你根本不知道的 Google 内部名称，那对你来说毫无意义。所以有什么用呢？是的。但这很有道理，它受到了在 Google 工作过的那些人的启发。因此它拥有那些技术专长，这些东西很难用语言表达。我想说的另一点是，与 **Codex** 和 **Claude Code** 相比，它的审查速度非常快。因为我的意思是，我实际上不知道，但我的直觉是，它们基本上会打包你的拉取请求的整个差异，如果你尝试审查一个分支，它只会发出一个请求。模型会运行一两分钟，然后返回一份报告。而 Codex 则会像蚁群一样，深入调查所有的变化，并尝试将它们联系起来，看看它们之间有什么关联？也许它的工作做得更好一些，但一个可能需要半小时，而另一个只需 90 秒就能完成。所以，很多时候，Gemini 的首次审查会发现 Claude Code 和我做错的地方，以便更快地修复。

<details>
<summary>Original English</summary>

**Samuel Colvin**: it's not trained on but it's probably informed by which is close enough but trained on is a very specific thing where it's like it would have not like the model would spit out names of internal Google names which you which would be meaningless to you because you don't have it. So what's the point right? Yeah. But uh but it makes sense that like it's informed by the same people that worked on that. Therefore it has those like technical proficiencies right which is just it's hard to articulate what those things are. The other thing I will say about it in comparison to to both codeex and claude code, it is so fast to review because I mean I I don't know actually but my my inclination is they basically wrap up the entire diff of your pull request if you're trying to review a branch and just makes one request of it. The model sits there and churns for a minute or two and returns you a report. Whereas Codeex is going to like go through and like aantically investigate all of the changes and try and link them up and how does that relate? And maybe it does a marginally better job, but one can take honestly half an hour and one is going to be done in like 90 seconds. And so quite often that like Gemini first review will find things that that Claude called Code and I have done wrong to to to fix more quickly.

</details>

**主持人**: 是的，我认为我们需要将此标准化。我觉得人们被激励拥有越来越多的自主权，但这有点草率。有时你只是想要一个快速的答案，但有时却没有选择退出的按钮来做到这一点。所以人们想要接管越来越多的事情。我当时在使用……我的意思是，我大部分时间都用 **Opus 4.6**，但我确实遇到过这样的任务，我觉得我可以比它做得更快。我的意思是，即使它读过 claude MD，我对代码库的心智模型也比它好得多。我并不是说这在其他方面是一场公平的竞争，但当然，在很多情况下，我宁愿它运行 30 分钟，而我可以在 10 分钟内完成。但确实存在这样的情况，我觉得我可以更快地完成那个更改。我听到的（谁知道是不是真的）是，对于 Opus 4.6 或最近的 Claudes，他们基本上采纳了这个反馈，即 Codex 更精确，然后基本上让它思考得更深入，调查的时间更长。这很好。到你的观点，有些地方这种自主权是值得的，但有些地方我需要完成一些事情，我宁愿更快速地行动。

<details>
<summary>Original English</summary>

**主持人**: Yeah, I think we need to standardize this. I think it's getting a little sloppy how people are incentivized to have more and more autonomy but actually sometimes you just want a quick answer and there's like sometimes no opt- out button to just do that and so people want to just take over more and more things. I was using I mean I use Opus 4.6 for the most part but I have I have honestly had tasks where I'm like I could do this faster than that as in sure I have a much better mental model of the codebase than it does even after it's read claude MD. I'm not saying that it's a fair fair fight in any in other ways, but like and of course there are many situations where I would rather it churned for 30 minutes when I could do it in 10, but there are genuinely situations where I'm like I could have done that change faster. And what I hear I who knows whether this is true is that for Opus 4.6 or the most recent Claudes, they basically took this feedback that codeex was more precise and like basically made it think harder, made it investigate for longer. Fine. There are places basically to your point there are places where that autonomy is worthwhile but there are places where I need to get something done where I would rather like you know move a bit more quickly

</details>

### Monty 的商业化前景与代理优化

**Samuel Colvin**: 是的。那么我想这就是 Monty 的现状。下一步它会走向何方？这其中有没有任何商业化的角度，或者你是怎么考虑的？

<details>
<summary>Original English</summary>

**Samuel Colvin**: stuff. Well so I I think that is the state of uh of Monty. Where's it going next? Is there a commercial sort of angle to this uh at all or what are you thinking?

</details>

**Samuel Colvin**: 是的。我向你展示一个快速示例会不会很有趣？因为我想这可能会引起兴趣。我将向你展示我们在这个示例中正在做的事情，因为我想这可能会让人们对正在发生的事情有更多的了解。所以，从根本上说，我们这里试图做的是从 LLM 模型的网站上抓取价格。众所周知，AI 公司在幽默感方面非常发达。因此，在通过抓取互联网赚取数百万之后，他们又让我们很难从他们的网站上获取数据。我们维护一个名为 **Genai prices** 的库，其中包含所有模型的价格。目前，这基本上是手工完成的，也就是说，当有新模型发布时，我们就会去读取它。那么，如果我们要下载这些数据，会是怎样的呢？所以这是一个 Podkai 代理。在这种特定模式下，我们实际上正在运行它。我们手动实现了循环。通常情况下，你不需要这样做。通常情况下，你只需使用 Pydantic AI 中的代码模式功能。但我想做一些略微不同的事情。但这里有趣的是，我们使用了 **Playwright**，并且有一个 `open_page` 函数，当它有权访问浏览器时，它会返回一个页面类型的实例。回到你关于如何在 Monty 内部注册内容的问题，这里的**数据类**页面，它有一堆方法，比如 `go_to`、`click` 和 `fail` 等等。这内部使用了真实的 Playwright，但你可以将这个数据类暴露给 Monty，这样 Monty 代码就可以访问并运行所有这些函数。另外值得一提的是，Monty 内置了 TY 类型检查器。所以在运行任何代码之前，它会使用这些**类型存根**进行类型检查。所以 LLM 应该确信它的**类型**是正确的，除非 LLM 的类型写错了，否则代码不应该运行。然后我们有这个 **Beautiful Soup** 函数，它会给我们返回一个基本的对象，允许我们查询 **DOM**。它会给我们返回这个标签类型，我们再次做同样的事情。我们有一堆可以向 LLM 注册的函数。所以最终，让我运行这个例子，看看它是否能让你对我们正在做的事情有所了解。Wix，这有道理吗？或者我应该更好地解释一下吗？

<details>
<summary>Original English</summary>

**Samuel Colvin**: Yeah. Would it be interesting for me to show you a like quick example of it cuz I think that might might be interest. I'll show you kind of what we're doing in this example cuz I think it will like hopefully give people a bit more compunction about what's going on. So, fundamentally what we're trying to do here is scrape the prices of LLM models from their websites. As we all know, AI companies have a very well-developed sense of irony. And so having made their millions out of scraping the internet, they then make it incredibly hard for us to get data back from their websites. And we maintain a library called Genai prices where we where we have the prices of all of the models. And at the moment that's basically handwritten as in we go and you know when a new model comes out we go and read it. And so what would it look like for us to go and download that that stuff? So this is a podkai agent. In this particular mode we're actually running it. We've manually implemented the loop. In general you wouldn't need to do that. In general, you would just use the like code mode feature in padantic AI. But I wanted to do some slightly different things. But the interesting thing here is we we take this we take playrite and we have a like open page function when it has access to to the browser and it will return me an instance of this page type. And coming back to your question about like how do I register stuff inside inside Monty these data classes page here which has a bunch of methods like well some attributes and a bunch of methods like go to and click and fail and everything. This is using real playright internally but you can expose this data class inside Monty and so the Monty code gets access to to run all of these functions. Uh it's also worth saying Monty has the the TY type checker built into it. So before it will go and run any code, it's running type checking with these type stubs. So the the LLM should be confident that it's got the the code shouldn't run unless the LLM has got the typing right. And then we have this beautiful soup function which is going to give us back this like basic thing that allows us to query the the DOM and that gives us us this tag type where again we do the same thing. We have these like a bunch of functions that we can register with the LLM. And so ultimately, let me run this example and see if it will give you some idea of of what we're doing. Does that does that make sense, Wix? Or is there anything there I should explain better?

</details>

**主持人**: 我目前跟得上。

<details>
<summary>Original English</summary>

**主持人**: I'm I'm following so far.

</details>

**Samuel Colvin**: 看看 **Logfire** 里面发生了什么可能会更有趣。

<details>
<summary>Original English</summary>

**Samuel Colvin**: It'll be probably more interesting to look at what's going on inside Logfire.

</details>

**Samuel Colvin**: 来了。所以你在这里看到，我们有**系统提示词**，我们基本上告诉它可以使用什么 Python 代码，而且指令不多，其中大部分我们会实现一个子集，所以我们没有浪费数千个令牌来解释它可以做什么和不能做什么。然后我们给它提供了这些函数的**类型提示**，你可以调用这些函数，这里是打开的页面，这里是函数**文档字符串**，你可以调用等等。它会去编写需要执行的代码。所以在这里你看到的是 LLM 编写的代码。所以它会去从 **Claude** 的文档中获取定价。它会将其转换为 Beautiful Soup 标签，然后它会检查该标签，并用它来调查并返回一些关于表格的 HTML。它会进行大量的调查，最终如果演示之神与我同在（这次花的时间特别长，但有时不会这么久），它会返回并给我一个模型价格的摘要。你会看到它这里运行中遇到了一堆错误。所以，特别是它认为 **async.io** 不需要导入，因为它假定是一个循环。结果模型在编写 Python 代码时，非常倾向于假定一个循环。所以我们基本上正在等待 Pydantic AI 支持**代码模式**的大事就是我们需要循环，我们正在努力解决最后的一些问题。但重点是，因为它没有导入 async.io，所以类型检查失败，并告诉它需要这样做。所以下一次运行时，它又出错了，但最终一旦它对了，它就能够运行代码。如果你看这里的完整代理运行，你会看到它编写了许多不同的代码块，但最终它返回并成功提取了价格。完全代理化的网络爬虫。但是，当然，你可以通过设置 Claude Code 或你选择的**编程代理**来做这件事。如果你在本地运行，并且你要么观看它，要么随意地危险地跳过权限，那没问题。但如果你在云中运行这种东西，并且你最终会遇到不信任的人提示模型，那实际上就等同于让一个不信任的人编写代码。所以你需要这种级别的控制，你可以确切地说允许它做什么。这些是你能够调用的确切函数。如果你允许它，例如加载网页或发起 GET 请求，你可以非常具体，因为所有这些函数调用都通过主机进行，你可以精确控制它可以连接到哪些域和不能连接到哪些域。你可以控制它可以执行多长时间，可以使用多少内存。所以你知道，理想情况是，在不久的将来我们会达到一个境地，你可以基本上运行这个，并让任何旧代码运行，而最坏的情况就是得到一个错误。是的。太棒了。但我想说的是，我这里没有这个例子，但你看这花了 102 秒，耗费了 30 美分。如果你在 LLM 的响应中，除了价格信息，还要求它返回再次运行此任务的最佳 Python 代码，然后你在它再次运行时给它那个函数代码，它就能第一次就正确地运行，因为你有效地让它运行那个脚本。所以，我认为在应用程序内部有一个新的状态层存在巨大的机会，你可以将其视为内存，但它通常远不止内存，它是**代理优化**的当前状态。其中一部分是代码，一部分是模型选择和模型设置，一部分是系统提示词。这就是我们现在在 Logfire 中的主要驱动力。所以基本上是超越评估，让代理随着时间的推移不断改进，无论是完全自主地，还是在用户查看更改并点击接受的情况下。所以 Monty 本身没有托管版本是没有意义的，因为关键是你不需要使用托管服务。但我认为在其之上存在巨大的服务空间，你会觉得：“是的，你当然可以在你选择的语言中使用它，但顺便说一句，我们有可以使其性能提高如此多的服务。”我认为很多人，很多可观测性领域的人最终都会发现这种**自我改进代理**是理想的。问题是它需要比你目前拥有的更大的范围，包括访问我的代码库，我不知道你会如何处理，但这会很有趣。是的，我部分同意你的观点。我的意思是，我们现在在 Pydantic AI 中正在做的一件事是，我们即将引入（我想这有一个 PR）可**序列化代理**。所以你基本上可以在一个 **TOML** 文件中完全定义一个代理。从模型到系统提示词，到所有的能力，无论是代码模式还是压缩，还是注册 MCP 服务器。这样做有很多好处，但其中之一是，你现在有一个文件，你可以在其中运行优化。理论上，你可以达到这样一个程度，即该文件可以基本上运行……

<details>
<summary>Original English</summary>

**Samuel Colvin**: Yeah. Beautiful. But but what I was going to say in answer to your question is I don't think I have an example of this here, but you see this took 102 seconds and cost 30 cents to run. If you ask the LLM in its response as well as the information about the prices to say please also return the optimal Python code to run this task again and then you give it that that function code when it runs again it gets it right first time because you effectively it's just going to go and run that script and so I think that there is an enormous opportunity for effectively a new layer of state within applications you could think of it as memory but it's often a lot more than memory it's the like current state of agent optimization. Some of which will be code, some of which will be model choice and and model settings, some of which will be system prompt and that is the like big drive we have now in logfire. So basically moving beyond eval to the agent improving over time whether that be completely autonomously or with a user like looking at the changes and clicking accept. And so so Monty itself doesn't make sense to have a like hosted version of it because the whole point is you don't need to use a hosted service but I think there's an enormous space for basically services on top of it where you're like yeah of course you can go and use it in in your language of choice but by the way we have the service that will make it that much that much more performant. I think a lot of people, a lot of observability people eventually find this sort of self-improving agents ideal. The problem is it requires a lot more scope than you currently have, including access to my codebase, which I don't know how you're going to handle that, but it it's going to be interesting. I I I agree with you. Yeah, I agree with you to some extent. I mean, one of the things we're doing now in Pyantic AI is we're we're about to introduce I think there's a PR out for this, so I think this is public serializable agents. So basically you can define an agent entirely in a toml file. Everything from the model to the system prompt to all of the capabilities whether they be code mode or compaction or registering an MCP server. There are lots of advantages to that, but one of the things is you have now one file where you can go and run that like optimization and in theory you can get to the point where that one file can basically run

</details>

**Samuel Colvin**: 不受信任的，因为它只拥有你注册给它的能力，而 Monty 正在运行所有……

<details>
<summary>Original English</summary>

**Samuel Colvin**: untrusted as in it only has the capabilities that you have registered with it and Monty is running all of the like

</details>

**Samuel Colvin**: 在该进程中执行的任意代码。

<details>
<summary>Original English</summary>

**Samuel Colvin**: arbitrary code that's being executed in that process.

</details>

**主持人**: 我觉得这是个好主意。我不确定 **TOML**……但因为主要思想是 TOML，就像任何规范语言、任何标记语言一样，它们只是一个 **DSL**。你必须重新发明一个 DSL，你会发明分支、变量和循环，然后你就得到一个半生不熟的通用语言版本。

<details>
<summary>Original English</summary>

**主持人**: I think this is a good idea. I'm not sure about the toml uh uh but uh because the the the main idea is that toml just like any specification language any markup language they are just a DSL right uh and you would have to reinvent a DSL you're going to invent branching and variables and looping and then you then you just have a half poorly implemented version of a general language

</details>

**Samuel Colvin**: 我同意你的观点，我认为如果我们达到那个程度，我们会诉诸 Python，或者我们会诉诸 Monty 来处理其中的一些东西。我认为 Monty 就是它。我认为 Monty 就是它。你已经做到了。

<details>
<summary>Original English</summary>

**Samuel Colvin**: I agree with you and I think if we get to that point we we resort to Python or we resort to Monty for some of that stuff I think Monty is it. I think Monty is it. You're already there.

</details>

**Samuel Colvin**: 好的，好的，我明白你的意思。我的意思是，我认为重点是，如果你思考**代理**是什么，当然有例外，但有很多代理是相当程式化的。你有一个系统提示词，一个模型，一个输出 schema，一些你注册的 MCP 服务器，一些设置，比如是否是持久性压缩等等。大概有 30 种这样的能力，实际上就是选择要开启哪些能力。当然，如果我想去注册任意工具，那又是另一回事了，这种方式就会失效。但通常，这些工具在企业中越来越多地被打包并放在 MCP 服务器后面。所以又回到了设置是 MCP 服务器的链接以及我们如何做……

<details>
<summary>Original English</summary>

**Samuel Colvin**: Okay. Okay. I I hear you on that. I mean, I think the point is that like most if you if you think about what what agents are, there are exceptions of course, but there's an awful lot of them that are somewhat formulaic. You have a system prompt, you have a model, you have an output schema, you have some MCP servers that you register, you have some some settings like is it durable compaction, yada yada yada. there's like 30 of or so of these capabilities and it's effectively a choice of like which ones do I switch on and sure if I want to go and register arbitrary tools that's a whole different thing and this this thing breaks down but often those tools are more and more at least in enterprise being packed up and put behind MCP servers and so again it comes down to like the settings are the link to the MCP server and how we're going to do or

</details>

**主持人**: 哦，是的，OAuth 是另一回事。但是的，我确实认为这可以成为一个标准。我认为你在定义标准方面很出色，而且**可序列化代理**是一个非常好的名称。所以，我很高兴看到它传播开来。太棒了。我想这就是我们播客的全部内容了。你将在伦敦的 AIE 大会上发表更多演讲，我们都非常兴奋。我确实认为这是一种对欧洲 AI，特别是伦敦 AI 领域一切成就的盛大庆祝。是的，我很高兴在那里见到你。

<details>
<summary>Original English</summary>

**主持人**: oh yeah off is another thing but yeah I think I I do think that this can work as a standard I think um you have a at defining the standard and um serializable agents is like a really good name for it. So, I'm excited to see that spread. Excellent. I I think that's I think that's going to be it for our pod. You're going to come speak more at AIE in London, which is we're we're all we're all very excited. I I do think like this is kind of a big celebration of everything in like sort of European AI, particularly London. And uh yeah, I'm excited to see you there.

</details>

### 会议与未来展望

**Samuel Colvin**: 是的，我非常期待。我不知道这个播客什么时候播出，但我们也对下周的会议感到非常兴奋。但我猜这会播出。我想我们反正已经售罄了，所以我觉得我们很棒。但是的，非常期待伦敦之行。那一定会很棒。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Yeah, really looking forward to it. I don't know when this podcast is going out, but we're also super excited for our conference next week. But I presume this will go out. I think we're we're sold out anyway. So, I think we're good. But yeah, really looking forward to to London. That's going to be great.

</details>

**主持人**: 你的会议应该会在你的 YouTube 频道上播出，我们会把人们引到那里。

<details>
<summary>Original English</summary>

**主持人**: Presumably your conference is going to be out on your YouTube and we'll send people there.

</details>

**Samuel Colvin**: 是的。所以我们是与 **Prefect** 共同举办的。所以有些内容会在我们的 YouTube 上，有些会在 Prefect 上，但所有内容都会有链接，你知道，你可以相对容易地找到它们，并且都会被录制下来。所以是的，我们很幸运能有像 **Guido** 和 **Sebastian** 以及 **Armen** 这样的人演讲。我们有一个很棒的演讲阵容。所以我非常兴奋。那会是很棒的一天。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Yeah. So So we're co-hosting it with Prefect. So some stuff will be on our YouTube, some will be on Prefect, but it will all there will be links to all of it on, you know, you'll be able to find it relative easily and it will all be recorded. So yeah, we've got we're so lucky to have people like Guido and Sebastian uh speaking and Armen like we have an amazing lineup of speakers. So I'm super excited for it. It'll be a great day.

</details>

**主持人**: 太棒了。非常感谢你的时间，恭喜你在开源领域找到了一个新角度，可以渗透到**运行时代理**的对话中。我确实认为，就像 **Deno** 和 **Bun** 在 AI 时代之前彻底改变了 Node.js 一样，你正在 AI 原生时代做同样的事情，并精确地构建代理需要的东西。我确实看到 Python 在这方面存在空白。所以你们……

<details>
<summary>Original English</summary>

**主持人**: Excellent. Well, thank you for your time and congrats on finding like a new I guess angle for open source to sort of penetrate the the the sort of runtime agent conversation. I do think like this is a like in a way that I guess Dino and Bun has revolutionized Node.js like preAI. I think you're kind of doing this in the AI native sort of era and building exactly what agents need. I do see that there's a gap in Python for that. So you guys

</details>

**Samuel Colvin**: 我给我的朋友 David Sora Pereira 看了 Anthropic 的这个东西，他说：“是的，这正是每个人需要的。”

<details>
<summary>Original English</summary>

**Samuel Colvin**: I spoke to my friend David Sora Pereira Anthropic showed him this and he was like yeah this is exactly what everyone needs.

</details>

**主持人**: 问题是你们要如何从中赚钱？我当时想：“是的，我认为这是……坦率地说，关于 Monty 最大的问题是：我们如何从中赚钱？”但我觉得我们在牛津做得很好。

<details>
<summary>Original English</summary>

**主持人**: Question is how are you going to make money out of it and I was like yep I think that's you know from a bluntly the biggest the biggest question on Monty is like how do we make money from it? But like hey I think we're doing well in Oxford.

</details>

**Samuel Colvin**: **Bun** 不必考虑这个问题。就这么说吧，对吧？[笑声]

<details>
<summary>Original English</summary>

**Samuel Colvin**: Bun didn't have to. Let's just put it that way, right? [laughter]

</details>

**Samuel Colvin**: 是的。我有一个关于那个的有趣故事，但我不会把它放到播客里。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Yeah. I I've got a funny story on that, but I I won't include it in in the post.

</details>

**主持人**: 不适合公开。好的，好的。那么，我们就此结束录音，伦敦见。

<details>
<summary>Original English</summary>

**主持人**: Not Not for public consumption. Okay. Okay. All right. Well, so stop the recording there and I'll see you in London.

</details>

**Samuel Colvin**: 酷。太棒了。非常感谢。

<details>
<summary>Original English</summary>

**Samuel Colvin**: Cool. Great. Thank you so much.

</details>