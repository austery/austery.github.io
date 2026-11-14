---
author: AI Engineer
date: '2026-04-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_zdroS0Hc74
speaker: AI Engineer
tags:
  - ai-agent
  - mcp-protocol
  - software-development
  - model-evaluation
  - developer-experience
title: AI Engineer Europe 第二天回顾：从模型发布到 Agent 生态的深度重构
summary: 本次会议涵盖了谷歌 Gemma 4 的发布、Anthropic 的 MCP 协议演进，以及 Cursor、Linear、Cerebras 等顶尖团队在 AI Agent 编排、验证与品味构建上的实战经验。核心议题围绕‘快速推理下的开发者策略’、‘Agent 原生代码库构建’以及‘超越聊天界面的交互范式’展开，强调了在 AI 自动化浪潮中，人类的判断力和对质量的坚持（Friction）依然是软件工程的核心。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Omar Santoro
  - David Sora Par
  - Mario Zechn
  - Armen Ronacher
  - Sarah Chang
  - Thomas Artman
  - Swix
companies_orgs:
  - Google DeepMind
  - Anthropic
  - Cursor
  - Cerebras
  - Linear
  - Hugging Face
products_models:
  - Gemma 4
  - MCP
  - Codex Spark
  - Devon
  - Pi
media_books: []
status: evergreen
---
### 开场：欧洲 AI 创新的崛起

**Tjisk Kumar**: 大家早安！非常荣幸能在这里见到大家。看看这个房间，全坐满了。昨天过得开心吗？昨天最让我难忘的是 Malta 展示的那张幻灯片，它展示了欧洲在 **AI 创新** 方面的领先地位。作为一个住在柏林的人，我有时觉得自己像个弱者，但看到 DeepMind 在柏林设立办公室，看到这么多真正的创新来自欧洲，真的让人倍感振奋。

<details>
<summary>Original English</summary>

**Tjisk Kumar**: Good morning. Thank you. Thank you. Good morning. We are here. Look at this. It's a full room. We are so excited. How many of you enjoyed yesterday? My highlight was Malta yesterday when he shared this slide of how Europe is leading AI innovation. And I think this is so cool because oftentimes we feel like the underdog, and this was so validating that real innovation is coming out of Europe with even the DeepMind office in Berlin.

</details>

**Tjisk Kumar**: 今天是第二天，我们将讨论很多有趣的话题：**Coding Agents**、**MCP**（谁在用 MCP？几乎所有人，太棒了）、AI 架构、媒体和 GPU。在开始之前，请和我一起感谢我们的赞助商，首席赞助商 **Google DeepMind**，以及白金赞助商 **Brain Trust**、**WorkOS** 和 **OpenAI**。

<details>
<summary>Original English</summary>

**Tjisk Kumar**: Today is day two and we're going to talk about a lot of interesting topics. So, we're going to talk about coding agents. We're going to talk about MCP. Who's using MCP here? Look at that. Almost everybody. Incredible. We're going to talk about AI architecture, media, GPUs. But before we do that, will you join me in giving it up for our sponsors, Google DeepMind, our presenting sponsor? Let's also give a huge round of applause for our platinum sponsors. We got Brain Trust, WorkOS, OpenAI.

</details>

### 谷歌 Gemma 4：在个人设备上运行的强大开源模型

**Omar Santoro**: 大家好！我非常激动，因为就在七天前，我们发布了 **Gemma 4**。Gemma 是 Google Mind 的一个**开放模型（Open Models）**家族。这意味着你可以下载并在自己的基础设施、设备上运行它们，也可以针对自己的用例进行微调。

<details>
<summary>Original English</summary>

**Omar Santoro**: All right. Hi everyone. I'm super excited to give this talk because just seven days ago we released Gemma 4. So GM is Google minds a family of open models. Open models means that these are models that you can take, you can download, you can run in your own infrastructure, your own devices, you can fine-tune for your own use cases.

</details>

**Omar Santoro**: Gemma 4 是谷歌迄今为止发布的性能最强的开放模型家族，参数量从 **20 亿 (2B)** 到 **320 亿 (32B)** 不等。最小的两个模型可以在安卓手机、iPhone 甚至树莓派上运行，它们具备多模态能力和推理能力，可以完成非常酷的离线 **Agent** 任务。而 **31B** 模型则是最智能、能力最强的，即便如此，它也能在消费级 GPU 上运行。

<details>
<summary>Original English</summary>

**Omar Santoro**: So, Gemma 4 is the family of most capable of open models that Google has released ever. These are models that go from two billion parameters all the way to 32 billion parameters. The smallest two models can run in an Android phone, in an iOS, in a iPhone phone as well, even in a Raspberry Pi. These are really small models that are multimodel have reasoning can do like very cool ondevice agentic things. Then you have the 31B that's the most intelligent model the most capable. But even the 31B is a model that can run in a consumer GPU.

</details>

**Omar Santoro**: 架构方面，Gemma 4 引入了 **Per-layer Embeddings**。简单来说，每一层都有对应的嵌入，它的工作方式更像是一个查找表，而不是复杂的计算。这使得它运行极快，你甚至可以将其放在 CPU 或磁盘中。这就是为什么 5B 模型实际上只需要在 GPU 中加载 2B 参数量，其余部分可以利用更慢的内存，因为它不需要进行传统的矩阵乘法。此外，我们还将授权协议更改为了 **Apache 2**，给予开发者充分的灵活性。

<details>
<summary>Original English</summary>

**Omar Santoro**: So actually Yema E2B has a new novel kind of architecture called per layer embeddings. The TLDR here is that pretty much there is like a embedding kind of per each layer, and it works more of a lookup table rather than a computation that you need to do. So pretty much this is a extremely fast thing. You don't need to have this in the GPU. You can have this in the CPU. You can have this in the disk. leveraging lama CPP with a simple flag override tensor and then you move the per layer embeddings to CPU or even to disk. With the M4 we change our license to an actual Apache 2 license.

</details>

### MCP 协议：构建 Agent 互联的神经系统

**David Sora Par**: 欢迎大家。这是一个 **MCP 应用**。这是一个自带界面的 Agent，它不是通过插件或 SDK 实现的，也不是在客户端硬编码的，而是通过 **MCP 服务端** 提供的。你可以把这个服务端放在 Claude、ChatGPT、VS Code 或 Cursor 中，它都能直接运行。

<details>
<summary>Original English</summary>

**David Sora Par**: Okay. Well, welcome. This is an MCP application. That's an agent shipping its own interface, not through like a plug-in, not through an SDK, not rendered on the fly by the model on the client side or hardcoded into the product. That is something that is served over an MCP server. And you can take the server, put it into cloud, you can put it into chatbt, you can put it into VS Code, cursor, and it will just work.

</details>

**David Sora Par**: 为了实现这一点，我们需要语义化。客户端和服务端都需要理解对方在说什么，理解 UI 是如何渲染的。因此我们需要一套协议。目前 MCP 的月下载量已经达到了 **1.1 亿次**。作为对比，React 达到这个下载量所花的时间大约是 MCP 的两倍。

<details>
<summary>Original English</summary>

**David Sora Par**: For doing that you need semantics. You need to have both sides the client and the server to understand what each side is talking to understand how you render this. And for that you need a protocol. We're now like at 110 million monthly downloads. Just a bit for context, React, one of the most successful open-source projects probably of the last decades, took roughly double the amount of time to reach that download volume.

</details>

**David Sora Par**: 我认为 2025 年是关于探索的一年，而 2026 年则是关于将 Agent 投入生产环境。我们正在进入一个通用的 **Knowledge Worker** 时代，财务分析师或市场营销人员需要的不是调用编译器的本地 Agent，而是能连接五个 SaaS 应用和共享驱动器的 Agent。连接性（Connectivity）是核心。在 2026 年构建 Agent 时，你需要考虑三件事：**Skills**、**MCP** 以及 **CLI/Computer Use**。

<details>
<summary>Original English</summary>

**David Sora Par**: But I still think this is just the absolute beginning because I think 2025 was all about exploring in 2026 is all about putting these agents into production. We're going to have general agents that will do real knowledge worker stuff like things a financial analyst want to do. And they need one thing in particular: connectivity. In my mind, there are three major things that you want to consider building an agent in 2026. It's skills, MCP, and of course, like CLI or computer use.

</details>

**David Sora Par**: 我们还需要构建 **Progressive Discovery**（渐进式发现）模式。目前很多人直接把所有工具塞进上下文窗口，导致上下文膨胀。相反，你应该使用工具搜索（Tool Search），只在模型需要时才加载工具。此外，我们正在改进核心协议，包括由谷歌提议的 **Stateless Transport Protocol**（无状态传输协议），这将使 MCP 服务端更容易像普通的 REST 服务一样部署到 Cloud Run 或 Kubernetes 上。

<details>
<summary>Original English</summary>

**David Sora Par**: The number one thing we're going to do there is that we need to go and start building something called progressive discovery. Everybody so far has done is to simply put all the tools into the context window. But what you should do instead you should start using this progressive discovery pattern which is to say use something like tool search to defer the loading of the tools. We have a proposal from our friends at Google who are working with something called a stateless transport protocol which make it significantly easier to just treat MCP servers like another stateless rest server.

</details>

### AgentCraft：借鉴游戏机制进行 Agent 编排

**Ido Salamon**: 早上好伦敦。如果一个 Agent 这么神奇，为什么我们不扩展到 10 个、20 个甚至 100 个，让它神奇 100 倍呢？原因在于瓶颈不在于启动 Agent，而在于我们自己。我们才是编排这些 Agent 的瓶颈。

<details>
<summary>Original English</summary>

**Ido Salamon**: So good morning London. agents are amazing. Uh, but if one agent is so amazing, why don't we scale up to 10 or 20 or 100 different agents and be a 100 times more amazing? It is pretty simple. spinning them up isn't the problem. It's us. We are the bottleneck in orchestrating all of these agents.

</details>

**Ido Salamon**: 幸运的是，这些管理技能并非全新的。如果你是一个游戏玩家，管理几十个单位听起来应该很熟悉。这就是我构建 **AgentCraft** 的原因，它是一个旨在通过将**游戏领域的经验**转移到生产力领域，从而提升人机协作上限的编排器。

<details>
<summary>Original English</summary>

**Ido Salamon**: Luckily, they're not really brand new. If you're a gamer or used to play games, managing dozens of units probably sounds a little bit familiar, which is why I built AgentCraft, which is an orchestrator that aims to raise the ceiling of human agent collaboration by taking learnings from gaming and transferring them into productivity.

</details>

**Ido Salamon**: 在 AgentCraft 中，每个 Agent 都有物理表现。你可以看到它们在地图上工作，而这个地图实际上是我**文件系统 (File System)** 的投影。你可以看到 Agent 正在处理哪个文件，查看完整的变更历史。我们甚至可以创建一个**热力图 (Heat Map)** 来可视化冲突并主动预防。当 Agent 需要你的帮助（如审批计划或回答问题）时，你可以利用 **RTS 游戏** 中的肌肉记忆，在 Agent 之间快速切换。

<details>
<summary>Original English</summary>

**Ido Salamon**: this is a physical manifestation of a coding agent. if we look at the map, you would notice that it's actually a projection of my file system. I can actually track and see visually what the agent is working on, which file. why not just create a heat map? I can actually try and see visualize collisions and I can even prevent them proactively. We can simply use muscle memory to quickly cycle between the agents that need our help.

</details>

### Pi 与 OpenClaw：反思 Agent 对开源软件的冲击

**Mario Zechn**: 嘿大家，我是 Mario。我构建了 **Pi**。在一切的开始，有了 Claude Code，它确实很棒，让我们都兴奋得睡不着觉。但随着功能越来越多，Bug 也随之而来。更严重的问题是，我的上下文不再受我控制，Claude Code 会背着我修改系统提示词，在不合时宜的地方插入提醒，这搞乱了模型并破坏了我的工作流。

<details>
<summary>Original English</summary>

**Mario Zechn**: Hey there, I'm Mario. I built Pi in a world of slop. In the beginning there was cloud code and was good. Back then, it was simple and predictable. But eventually the team got bigger and they built a lot of features. With more features come more bugs. The real problem is that my context wasn't my context. Cloud code is the thing that controls my context. And behind my back, cloud code does things to the context.

</details>

**Mario Zechn**: 我反思之后构建了 Pi。它是一个适应你的工作流而非相反的 Agent。它只有四个核心工具：Read、Edit、Bash 和微调。它非常轻量，系统提示词极其简洁。为什么？因为现在的模型经过了大量的**强化学习 (RL)** 训练，它们天生就知道什么是 Coding Agent，你不需要花 10,000 个 token 去告诉它。

<details>
<summary>Original English</summary>

**Mario Zechn**: So that's Pi. It's an agent that adapts to your workflow instead of the other way around. It comes with four tools. Read, edit, bash. Here's Pi's system prompt. That's it. The models are actually reinforcement trained up the wazoo. So they know what a coding agent is. You don't need 10,000 tokens to tell them you're a coding agent.

</details>

**Mario Zechn**: 现在的 Agent 正在制造大量的**垃圾 (Slop)**。它们从互联网上学习，而互联网上 90% 的代码都是旧垃圾。Agent 不像人类那样有痛感，它们会开心地不断往你的代码库里“排泄”。这种局部修复、全局搞砸的行为，让你最终既无法信任代码，也无法信任测试。

<details>
<summary>Original English</summary>

**Mario Zechn**: OSS in the age of clankers. Clankers are destroying OSS. The problem is that agents are emergent learned complexity. 90% of code on the internet is our old garbage. And that's what the models learn from. Agents will happily keep [ __ ] into your codebase. So the agent patches locally and [ __ ] up globally. You cannot trust your codebase anymore and also not your test because your agent wrote your test.

</details>

**Mario Zechn**: 所以，请**慢下来 (Slow down)**。不要因为 Agent 能做就去堆砌功能。学会说“不”是你目前最有价值的能力。对于关键代码，请亲手编写并阅读每一行。那点“摩擦力”正是你在大脑中构建系统理解的关键。

<details>
<summary>Original English</summary>

**Mario Zechn**: My final slide, slow the [ __ ] down. Think about what you're building and why. And don't just build because your agent can do it. Learn to say no. Critical code, read every [ __ ] line. Write it by hand. And that friction is the thing that builds the understanding of the system in your head.

</details>

### Arendil：摩擦力即判断力

**Armen Ronacher**: 刚才 Mario 提到了“摩擦力”。我创建了 **Flask** 框架，讽刺的是，现在很多人是通过机器生成的代码了解到它的。我们在过去 12 个月里一直在用 Agent 构建系统，虽然获得了巨大的杠杆，但也遇到了巨大的失望。

<details>
<summary>Original English</summary>

**Armen Ronacher**: Today I want to talk with Christina about friction a little bit. I have created Flask, which is a Python framework, which ironically is so much in the weights that a lot of people are learning about it now because the machines are producing it. We have been building with or on agents for a good 12 months. We had huge leverage and great disappointment.

</details>

**Christina Ponella Cubro**: 我是一个“原生 AI 工程师”，这些工具出现的时间比我入行的时间还长。问题在于，这些工具非常有成瘾性。你会不断输入下一个 Prompt，期待它是那个能让产品跑通的神来之笔，但它也可能是压死骆驼的最后一根稻草。因为产出很快，我们被欺骗，认为自己更有效率了，但实际上我们失去了停止、思考和设计的时间。

<details>
<summary>Original English</summary>

**Christina Ponella Cubro**: I am what I like to call a native AI engineer. what this means is like they've been super foundational in how I've become a software engineer. these tools are super addictive. You never know if that next prompt is going to be the one that makes your product work or if it's going to be that last drop of slop. because we produce a lot of output very fast, we are tricked into thinking that we're actually being more efficient.

</details>

**Armen Ronacher**: Agent 编写的代码往往过于追求“不卡壳”。比如读取配置失败时，它会默默加载默认值。作为一个工程师，你知道这很糟糕，因为你可能几个小时后才发现数据库里全是错误数据。Agent 没有情绪，它不会因为写出烂代码而感到难受。

<details>
<summary>Original English</summary>

**Armen Ronacher**: the agents are writing kind of code that when you as a human start learning how to write code you wouldn't necessarily write. they optimize towards making progress towards shipping stuff. And as a result, they're creating many more failure conditions than human written code normally would do. because you as a human feel a little bit bad when you write code like this. But the agent doesn't have a reason for this.

</details>

**Christina Ponella Cubro**: 我们的对策是构建 **Agent-Legible Codebase**（Agent 易读的代码库）。这包括：
*   **Modularization**（模块化）：不仅仅是组件，还有代码流本身的模块化。
*   **机械强制执行**：通过 Lint 规则禁止空的 Catch 块，强制要求唯一的函数名（为了 **Token 效率**）。
*   **Erasable Syntax Only TypeScript**：代码本质上是 JavaScript 加上类型注解，没有转译过程，这让 Agent 在查找错误时更高效。

<details>
<summary>Original English</summary>

**Christina Ponella Cubro**: what we're proposing here is an agent legible codebase. one of the main points is modularization. we enforce unique function names. And the reason for this is not just more legibility, but it's actually also the token efficiency. we've started exploring something recently called erasable syntax only TypeScript mode. there's one source of truth between your actual code and the compiler.

</details>

### Cursor 实践：用 Markdown 技能取代上万行代码

**David Gomez**: 大家好！今天我要讲的是，**Markdown 基本上就是新的代码**。在 Cursor 中，我们最近用一个仅 200 行的 **Skill**（技能文件）取代了 12,000 到 15,000 行复杂的 TypeScript 代码。

<details>
<summary>Original English</summary>

**David Gomez**: I'm going to be talking about how markdown is basically the new code. we recently replaced a lot of code in the cursor application with just markdown just a skill. Like I think it was around 15,000 lines of code deleted.

</details>

**David Gomez**: 这个功能就是 **Git Worktrees**（工作树）。以前为了实现它，我们需要写大量的代码来管理隔离的 Checkouts、处理清理逻辑、注入上下文。现在，我们只需要两个原语：**Agent Skills** 和 **Sub-agents**。

<details>
<summary>Original English</summary>

**David Gomez**: We decided that there are two primitives that we could use to effectively allow cursor users to use word trees. One is Asian skills and the other are subentations.

</details>

**David Gomez**: 现在的实现非常简单。我们编写一套指令，告诉模型如何创建 Worktree，如何运行用户配置的安装脚本，并严令模型只能在该 Checkouts 中操作。虽然这听起来有点“凭感觉”（Vibes-based），因为它不再是物理隔离，但通过强大的 **Prompting** 和 Evals（评分器），效果惊人地好。我们可以让不同的模型在不同的 Worktree 中竞争完成同一个任务，这就是我们的 **Best Event** 功能。

<details>
<summary>Original English</summary>

**David Gomez**: The skill is written is actually really simple. it's basically a set of instructions telling the model how to create word trees. We have to instruct the model to stay on that work tree. we do that with some aggressive prompting effectively. it's effectively a way for you to compete on have have different models compete on the same task. And then you can even preview the changes.

</details>

### Cerebras：极速推理模型下的开发者策略

**Sarah Chang**: 过去几年，我们因为 AI 生成代码速度慢而养成了一些坏习惯，比如写巨大的 Prompt 试图 One-shot。但上个月，我们发布了 **Codex Spark**，它的生成速度达到了 **1,200 tokens/second**。作为对比，Claude Sonnet 的速度大约是 40-60 tokens/second。

<details>
<summary>Original English</summary>

**Sarah Chang**: over the past few years, we as developers have developed a series of bad habits as a result of slow AI code generation. Codex Spark can generate code at 1,200 tokens per second. So in this new era, this is 20 times faster.

</details>

**Sarah Chang**: 当验证变得“免费”时，一切都变了。你没有理由不在每一步都加入单元测试、Lint 和 Diffs 评审。我建议大家尝试 **Cherry-picking**（择优挑选）：以前你需要等待一个模型生成一个版本，现在你可以让五个 Sub-agents 在同样的时间内生成 75 个版本，然后挑选最好的那个。这实际上是在用数量诱发“品味”。

<details>
<summary>Original English</summary>

**Sarah Chang**: at 1200 tokens per second, a model like codec spark makes validation basically free. There is no excuse why you should not be doing things like test suites, linting, diff reviews. Another tip is exploring cherrypicking. I can generate five sub aents that are each generating 15 versions and now I have 75 versions and I pick the one that's best.

</details>

**Sarah Chang**: 在这个新机制下，你应该把 AI 看作 **Pair Programmer**（结对编程者），而不是那种你发个指令就跑去吃汉堡的离线工具。你需要坐在它旁边驾驶，给它具体的约束：比如禁止删除文件、限制 Diff 大小。我们推荐使用一个四文件系统来管理外部记忆：`agents.md`（定义 Agent）、`plan.md`（整体计划）、`progress.md`（进度跟踪）和 `verify.md`（验证逻辑）。

<details>
<summary>Original English</summary>

**Sarah Chang**: You should view it much more as a pure programmer. sit down with it and actually steer it. You can do things like ban the model from deleting files, give it a max diff size. a good way that you can think about how do I externalize this memory is with this four file system: agents MD, plan MD, progress MD and verify MD.

</details>

### Incident.io：用 AI 调试 AI 系统

**Lawrence Jones**: 我们的目标是完全自动化生产环境的调查。但这带来了一个挑战：我们背后有成百上千个 Prompt，系统变得极其复杂，人类已经无法直观地理解它的表现。

<details>
<summary>Original English</summary>

**Lawrence Jones**: our goal is actually to fully automate production investigations. But behind this investigation is like hundreds, if not thousands of prompts. So, how on earth do we scalably understand how this system is performing? They are now complicated enough that you can't as a human really tractably dig into how these things are performing.

</details>

**Lawrence Jones**: 一个巨大的突破是：我们将原本用于人类观察的 UI **转换为可下载的文件系统**。Agent 在处理文件系统方面表现卓越。当出现问题时，我们把整个交互轨迹下载到一个沙盒中，让 Claude Code 或 Codex 去阅读。它能看到所有 Prompt 的输入输出，并直接在代码库中指出哪里需要修改。

<details>
<summary>Original English</summary>

**Lawrence Jones**: can we just download all of the UI that we have as a file system? And that's kind of what we've done. these agents are fantastic at using file systems and just going through this data. You sit there in the session and you go hey like have a look at this. Tell me what you think has gone wrong. and then it will be able to tell you where you should be making the modification.

</details>

**Lawrence Jones**: 我们还建立了一个名为 `scrapbook` 的仓库，里面有非常结构化的流程，教 Agent 如何分析这些下载的数据。我们会启动 25 个并发 Agent 进行实体分析，然后进行**群组聚类 (Cohort Clustering)**，总结出故障模式。这不仅仅告诉你哪里错了，还告诉你系统为什么表现不好。

<details>
<summary>Original English</summary>

**Lawrence Jones**: we created this repo called scrapbook. we parallelize out all of your agents. they can all individually build their analysis of an investigation. and then you go into the next stage of the pipeline where you do some cohort clustering. by clustering it together, you end up with actually a really really useful report.

</details>

### Factory：支持多日运行的“任务”系统

**Luke Alvo**: 现在的软件工程瓶颈不在于智能，而在于**人类的注意力**。再优秀的工程师一天也只能处理几个任务，因为每个 Commit 都需要他们评审。如果人类决定构建什么，而系统决定如何构建，那会怎样？

<details>
<summary>Original English</summary>

**Luke Alvo**: the bottleneck in software engineering nowadays is not intelligence. It's now limited by human attention. we kept asking ourselves, what if a human decides what to build and then a system figures out how to do so? An agent could just work for hours for days and you come back to finish work.

</details>

**Luke Alvo**: 我们提出了 **Missions**（任务）系统。它不是一个单一的 Agent 会话，而是一个通过结构化交接和共享状态进行协作的 Agent 生态。它采用三角色架构：
1.  **Orchestrator**（编排者）：处理规划，生成 **Validation Contract**（验证契约）。
2.  **Workers**（执行者）：拥有干净的上下文，实现功能并 Commit。
3.  **Validators**（验证者）：它们没见过代码，只根据验证契约来测试行为。它们像 QA 一样启动应用、填写表单、点击按钮。

<details>
<summary>Original English</summary>

**Luke Alvo**: notably, a mission is not a single agent session. It's an ecosystem of agents. It uses a three-role architecture: orchestrator, workers, and then there's validators. the orchestrator produces a plan that includes features, milestones, and then something that's called a validation contract. workers handle implementation. and then the last role are validators. They handle verification.

</details>

**Luke Alvo**: 我们最长的一个任务运行了 **16 天**。这之所以可行，是因为我们采用了**串行执行 (Serial Execution)** 而不是并行。虽然并行看起来更快，但 Agent 之间会互相踩踏、产生不一致的决策。通过串行的结构化交接，错误率大幅下降。

<details>
<summary>Original English</summary>

**Luke Alvo**: our longest mission ran for 16 days. The difference with missions is that we run features serially. Within a feature, we allow for parallelization on readonly operations. It seems slower on paper, but the error rate drops dramatically and when you have tasks that run for many days, the sort of correctness compounds.

</details>

### Linear 炉边谈话：追求软件品味与“零 Bug”文化

**Gergely Orosz**: Thomas，我们曾在 Uber 共事过。那时 Uber 处于疯狂增长期，为了营收可以不惜一切代价牺牲质量。但在现在的 AI 时代，当每个人都能瞬间生成大量功能时，你认为趋势是否在向错误的方向发展？

<details>
<summary>Original English</summary>

**Gergely Orosz**: things are trending the wrong way right now. what happens when when agents are capable of doing everything immediately for you? the pendulum has swung too far into the wrong direction. Uber was a winner takes it all market. you just had to ship immensely. what I saw at Uber was that hyperrowth that I never want to go through again.

</details>

**Thomas Artman**: 确实。Steve Jobs 曾说，优秀的产品源于对 999 件事说“不”。现在因为 AI，说“是”变得太容易了。在 **Linear**，我们依然对大量请求说“不”。我们要弄清楚客户真正的痛点，然后设计出完美的解决方案。AI 确实帮我们加速了，比如 10% 的 Bug 现在是由 AI 自动修复并提交 PR 的，未来这个比例会接近 100%。

<details>
<summary>Original English</summary>

**Thomas Artman**: great products come out of saying no to you know 999 things and yes to one thing and with AI we might be in a place where it's just too easy to say yes. We still say no to a lot of custom requests. 10% of our bugs are automatically fixed by a singleshot AI instance. I do foresee a future where like it gets closer to 100%.

</details>

**Thomas Artman**: 我们有一项名为 **Quality Wednesdays**（质量周三）的传统。全公司 25 名工程师每人展示一个他们做的质量修复，哪怕只是挪动一个像素。这个传统的 side effect 是让所有人即便在开发无关功能时，也会留意那些细微的体验问题。

<details>
<summary>Original English</summary>

**Thomas Artman**: every engineer would show one fix that they did was quality and it went from like a one pixel change to oh I just made our backend way more efficient. people kept on finding problems in the product because they knew they had to come to the next Wednesday meeting with a fix.

</details>

**Thomas Artman**: 我们还有 **Zero Bug Policy**（零 Bug 政策）。只要发现 Bug，它就会立即被分配，并成为最高优先级。你必须停下新功能开发，先修复它。这背后的逻辑是：Bug 产生的速率是恒定的，不管你现在修还是三个月后修，工作量是一样的。唯一的区别是你的产品会因此变得越来越烂还是保持卓越。

<details>
<summary>Original English</summary>

**Thomas Artman**: zero bug policy literally means that if a bug gets reported it gets assigned to somebody automatically and that becomes your highest priority. the rate at which you have to fix bugs is again constant. It doesn't matter whether you fix them two months from now or immediately.

</details>

### Lagora：超越聊天界面的垂直 AI

**Jacob Laurson**: 现在的瓶颈已经从“做功”转移到了“规划”和“评审”。如果你用过 Claude Code 这样长序列运行的 Agent，你可能会陷入那种“它改了条款 3，但有没有顺便改了别的？”的困惑中。

<details>
<summary>Original English</summary>

**Jacob Laurson**: planning work and reviewing work is the new bottleneck. doing the actual work is extremely cheap. if you've ever worked with a longunning complex agent, you get a new contract. Does it look was it only clause three that was changed? Probably not. And so you end up in this state.

</details>

**Jacob Laurson**: 根据 **Verifier's Rule**（验证者规则），如果一个任务容易验证，AI 就能解决它。法律领域很特殊，写合同容易，但验证很难，只有法官才能真正验证。我们通过分解任务，把风险评估、先例选择留给人类，把格式调整、定义校验（类似于代码的 Lint）交给 Agent。

<details>
<summary>Original English</summary>

**Jacob Laurson**: verifiers rule states that if it's a task is solvable and it's easy to verify then it's going to get solved by AI. verticals have tasks that are different places on the spectrum. Writing a contract is very easy to solve, but actually extremely difficult to verify. You can decompose task. leave picking risk profile to the human, but I can try to get other stuff down where it's easy to verify.

</details>

**Jacob Laurson**: 聊天框是一个非常低带宽的界面。它试图把复杂的工作树压缩成一维的线性对话。我认为人类和 Agent 应该在**高带宽的持久化 Artifacts（制品）**中协作。比如在一个文档里，你可以直接高亮条款 3 并打上标签，让特定的 Agent 只修改这一部分。不要把 Agent 限制在人类语言中。

<details>
<summary>Original English</summary>

**Jacob Laurson**: Chat is one-dimensional. It's a very low bandwidth interface. So what's a better interface? Well, I think humans and agents should collaborate in high bandwidth artifacts. durable interface where it makes sense to collaborate. agents aren't humans and so we should not constrain them to human language.

</details>

### Arena.ai：模型仍待突破的局限性

**Peter Gstiff**: 大家都看着那些一路向上的曲线，觉得 AGI 就在下个转角。但我们 Arena 的数据展示了另一个故事。我们有一个 **Nonsense Benchmark**（废话基准测试），专门问模型一些毫无逻辑的问题。

<details>
<summary>Original English</summary>

**Peter Gstiff**: any benchmark you seem to look at line goes up. this could create this kind of psychosis that we all see. I think there's still quite a few things missing. the idea behind the [ __ ] benchmark is quite simple. what happens if you ask nonsense questions?

</details>

**Peter Gstiff**: 结果令人惊讶。即使是像 GPT-5.4 这样具备强大推理能力的模型，往往也会在指出问题“不合逻辑”后，接着写 20 个段落试图去强行解释它。这说明它们被过度训练去“不惜代价解决任务”。我们的数据显示，前沿模型的 **Dissatisfaction Rate**（不满意率）依然在 9% 左右。模型在数学和物理上进步巨大，但在创意写作、法律和游戏设计上，进步非常缓慢。它们依然完全不理解游戏机制。

<details>
<summary>Original English</summary>

**Peter Gstiff**: quite often it would maybe have one line where it would question the premise of this question and then spend 20 paragraphs trying to solve it. the reason why that happens is that they were trained so much to solve the task at any cost. 9% of the time people would get two responses from two good models and they don't like them. whenever you try to build games with LLMs, it just feels like they have no idea like how to build actual games.

</details>

### Swix 总结：Agent 正在渗透一切

**Swix**: 我虽然在 Cognition 工作，但我为 AI Engineer 组织这个会议时，所有的工作都是由 **Devon** 完成的。我不再需要自己去弄 Figma 还原，我把 Figma 发给 Devon，它就能生成像素级还原的代码。

<details>
<summary>Original English</summary>

**Swix**: I start introducing a workflow of our contract designer showing me a Figma page and asking me to turn it into reality. I just added Dev into it. hooked up Devon to Figma and in very short order we have a perfectly functioning website that is pixel perfect to the Figma.

</details>

**Swix**: 最让我惊讶的是，这让我的员工工作得更开心了。我的设计师在印尼，他醒来就开始和 Devon 互动，给它画红线标注。这消除了原本等待我反馈的阻塞感。我们还用 Devon 来管理 130 名演讲者的日程，处理各种繁琐的 ETL 任务，甚至让它帮我在伦敦买一只作为装饰的龙虾。

<details>
<summary>Original English</summary>

**Swix**: I am getting more work out of my employees because they enjoy doing it because the feedback cycle for them from waiting blocking on me is gone. this entire schedule is managed by Devon. whenever someone comes in with a speaker change, I just say, "Devon, handle it for me." I asked Devon to research where can I get a lobster in London. that's literally the the lobster that you had was bought from Devon.

</details>

**Swix**: 2026 年的一个大趋势是 **AI 正在取代 SaaS**。我会跟员工争论，为什么要付钱买某个 SaaS？我们可以让 Agent 直接帮我们写一个。现在的用户不再只是人类，Vercel 60% 的用户已经是机器人。这意味着你的仪表盘不再重要，你的 **API、CLI 和 MCP** 才重要。Agent 正在冲出牢笼，渗透进除了代码之外的每一项知识工作中。

<details>
<summary>Original English</summary>

**Swix**: once you get enough psychosis, you are thinking about replacing entire pieces of SAS. here is me arguing with my employees about kicking out a SAS tool and building it ourselves because we can. 60% of the user base of Versell now is bots is agents. It's not humans. So actually your dashboards don't matter. Your APIs matter your CLI matter. Your MCPs matter. Agents for everything else are coming.

</details>

**Tjisk Kumar**: 我们做到了！这两天真是一段不可思议的旅程。我们要感谢所有的演讲者、赞助商和组织者。接下来晚上 7:00 在 Fabric 俱乐部有 Afterparty，那不是去蹦迪，而是去深入交流。请务必带上你的证件（Badge）。现在，让我们一起上台拍张大合照！

<details>
<summary>Original English</summary>

**Tjisk Kumar**: We did it. Y'all are such an amazing crowd. What a journey. Give it up for your speakers each and everyone. we have a party coming up at 7:00 local time in a club called Fabric. But here's the deal. It's not clubbing. we're going to create an atmosphere that's not you can talk to each other and ideally you do. come with your badge. let's move to taking a group photo together.

</details>