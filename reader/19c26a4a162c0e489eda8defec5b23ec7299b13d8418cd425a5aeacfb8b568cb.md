---
author: Latent Space
date: '2026-09-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=z9OkBD2-MDU
speaker: Latent Space
tags:
  - computer-use
  - agentic-workflow
  - prompt-caching
  - context-compression
  - function-calling
title: OpenAI全新Agent架构剖析：Computer Use、Decisions API与超低延迟推理
summary: 在OpenAI开发者日特别对话中，Ari Weinstein与Nikunj Handa深入揭秘了最新推出的智能体技术栈。核心涵盖云端原生Linux环境下的Computer Use能力演进、基于结构化推理与极速TTFT的Decisions API、支持双向异步与消息注入的Responses/WebSocket架构，以及多层次提示词缓存与上下文压缩机制，展示了AI从辅助生成迈向自主操作系统的全新范式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ari Weinstein
  - Nikunj Handa
  - Sam Altman
companies_orgs:
  - OpenAI
  - Apple
  - Stripe
products_models:
  - GPT-4o
  - Codex
  - ChatGPT
media_books: []
status: evergreen
---
### 开篇引言：超人级计算机操作与黑客文化

**主持人**: 如今电脑的运行速度越来越快，而在完成日常任务方面，普通用户在大多数情况下可能已经习惯了现有的交互方式。但我认为下一个前沿挑战在于：计算机能否展现出超人般的能力来提供服务？不仅速度极快，甚至能超越经验丰富的资深用户操作软件的效率。如果这一愿景得以实现，那将是一件意义深远且令人无比振奋的事情，因为我们将突然进入一个能够构建全新实时交互体验的时代。

<details>
<summary>Original English</summary>

**Host**: Computers today are getting faster at completing tasks, and for average humans, that might often be enough. But I think the next frontier challenge is for computers to provide superhuman service—running software just as fast, or even faster, than experienced power users like us. If that happens, it will be profoundly significant and exciting, because we will suddenly be able to build products that offer true real-time experiences.

</details>

**主持人**: 仅仅四周之前，情况还完全不是这样。外界甚至有人质疑计算机自动化的进展停滞不前。然而就在最近，开源社区和产业界涌现的创新极大地激励了团队。可以说，先锋实验室的探索被迅速吸收并迭代。我强烈感觉到 **OpenAI** 内部依然葆有极为纯粹的黑客文化，工程师们对技术突破充满执着与激情。面对新型推理范式的挑战，基础设施团队直呼“这太不可思议了，我们必须全力攻克它”，随即几天内就构建出了运行良好的原型。现在团队全力以赴优化延迟，力求在最短时间内将这一突破推向市场。

<details>
<summary>Original English</summary>

**Host**: Just four weeks ago, this was not the case. But recent breakthroughs energized us. OpenAI still maintains an incredibly intense hacker culture where people are deeply passionate about everything. When this new reasoning type emerged, someone from the infrastructure team said, "This is insane. We have to be there and hack on this." They built a functional prototype, and now the focus is entirely on slashing latency and bringing it to market as quickly as possible.

</details>

### Computer Use 重磅发布：从浏览器沙箱到完整云端 Linux

**主持人**: 欢迎大家收看 OpenAI 开发者日（DevDay）特别播客节目。今天我们非常荣幸邀请到了负责产品与计算机使用代理（Computer-Using Agent）团队的 **Ari Weinstein**。Ari，能不能先向大家概括一下，今天围绕 Computer Use 都有哪些重磅发布？

<details>
<summary>Original English</summary>

**Host**: Welcome to this OpenAI DevDay special edition podcast. We have Ari here, who leads product for the computer-using agent team. Ari, could you briefly summarize what was announced today regarding Computer Use?

</details>

**Ari Weinstein**: 今天的发布会简直太令人兴奋了！如果你听了早上的主题演讲，就会发现我们推出了一系列关于 Computer Use 的全新能力。与市场上其他同类产品或以往方案相比，最根本的区别在于：过去的工具通常只能让模型操作一个受限的无头浏览器沙箱，或者在本地权限受限的环境中打转；而现在，开发者和用户可以直接在云端获得一台由 Agent 完全掌控的完整 **Linux** 计算机环境。

<details>
<summary>Original English</summary>

**Ari Weinstein**: Yes, it has been absolutely thrilling! We just finished the keynote announcements. The fundamental difference from traditional approaches or other products is that instead of just getting a sandboxed cloud browser, you now receive a dedicated, full Linux computer in the cloud.

</details>

**Ari Weinstein**: 这意味着 Agent 不仅可以浏览网页，还能直接启动并操控完整的桌面原生图形界面应用程序，运行本地编译器、终端命令行以及各类复杂的生产力软件。之所以让我对 Computer Use 感到如此兴奋，是因为世界上绝大多数软件最初都是专为人类交互界面设计的。当 Agent 能够像人类一样看懂屏幕、移动鼠标、敲击键盘时，它就能够无缝接管并使用这世上已有的全部软件生态，替你处理任何繁琐的日常事务。

<details>
<summary>Original English</summary>

**Ari Weinstein**: This means the agent can execute complete desktop applications alongside a web browser. The immense power of Computer Use—and what excites me most—is that virtually all software in the world was built for human interfaces. Now, agents can utilize the exact same software stack, allowing you to delegate virtually any task on your computer.

</details>

### 从订餐到 YouTube：现实场景中的效率跃迁

**主持人**: 这确实打开了无限的想象空间。日常生活中，很多人都在思考自己把时间耗费在哪些重复性劳动上，以及如何将这些繁杂事务托付给 Agent。从预订机票、网购比价，再到玩游戏或数据收集，只要能自动化，就能释放巨大的精力。

<details>
<summary>Original English</summary>

**Host**: It truly opens up endless possibilities. People spend hours on repetitive digital chores. Delegating flight bookings, online shopping, or even routine gaming and data tasks to an agent can save enormous personal bandwidth.

</details>

**Ari Weinstein**: 没错。分享一个我自己生活中的真实案例：我最近订购了健康餐食定制服务，为了搭配合理的健身营养比例，我需要精确计算每顿餐食中鸡肉、碳水化合物和蔬菜的克数。但那家服务的网页点单系统交互极其反人类，调整一次菜单往往要手动点击耗费近两个小时。后来我直接把这个任务交给了 Computer Use Agent，它自主打开页面、逐项核对并调整克数配置，仅仅用了 15 分钟就全部搞定，帮我硬生生节省了接近两个小时的时间。而且它前后帮我调整了八次，准确率甚至比我自己手动点选还要高。

<details>
<summary>Original English</summary>

**Ari Weinstein**: Exactly. A personal example: I subscribe to a meal preparation delivery service to manage my diet. Adjusting the exact grams of chicken and carbs across meals used to take me two hours of tedious clicking because of their complex interface. I finally had a computer-using agent handle it; it finished the entire task in 15 minutes. It saved me two hours each time, performed it eight times, and was faster and more accurate than me doing it manually.

</details>

**主持人**: 作为内容创作者，我深有同感。我最刚需的场景之一就是 **YouTube** 后台的自动化运营。YouTube 的很多功能并没有开放公开的 REST API，例如后台特定格式的视频 A/B 测试、创作者社区动态的批量分发等，开发者只能被迫在虚拟机里手动点击网页。而借助 Computer Use，这些完全缺乏 API 支持的平台瞬间具备了完全自动化的可能。

<details>
<summary>Original English</summary>

**Host**: As a content creator, my number-one use case is automating YouTube creator workflows. YouTube offers very limited APIs for things like multi-variant thumbnail A/B testing or community tab interactions. Without public APIs, having an agent operate the web UI directly in a virtual environment bridges that massive gap.

</details>

### 破除停滞论调：自动化架构的演进路线

**主持人**: 坊间甚至有某些知名 AI 播客曾断言，过去两三年里计算机视觉控制与 GUI 自动化技术几乎原地踏步。作为业内深耕此领域的专家，你怎么看待这种论调？回顾你从开发 **Workflow** 捷径工具被 **Apple** 收购，再到创立 Sky，最终加入 OpenAI 的历程，是什么驱动了这一轮技术的质变？

<details>
<summary>Original English</summary>

**Host**: Some popular AI podcasts argued that computer use hadn't made meaningful progress over the last two years. Having spent years in this domain—from building Workflow, joining Apple, founding Sky, and now leading this at OpenAI—how do you see the evolution? What drove this massive leap?

</details>

**Ari Weinstein**: 我想那些认为技术停滞的人如果看到现在的进展，一定会发生 180 度的态度转变。计算机自动化是我毕生的热情所在。过去在编写脚本或开发规则引擎时，我们必须提前穷举界面的所有状态分支；后来在大模型早期，虽然可以让模型看截图点击，但模型的规划深度和推理可靠性极低，只要遇到弹窗或加载延迟就会彻底卡死崩溃。

<details>
<summary>Original English</summary>

**Ari Weinstein**: I believe anyone claiming stagnation would change their perspective 180 degrees seeing where we are today. Early models could initiate tasks but failed brittlely whenever an unexpected modal or latency hiccup appeared. They lacked self-debugging capabilities.

</details>

**Ari Weinstein**: 而在过去这一年里，底层基础模型发生了根本性的蜕变。最大的质变在于：现代前沿模型不仅能稳定启动复杂任务，更具备了强大的自主调试与反思修正能力。当一次点击未达预期时，它能主动分析失败原因并尝试备选路径。此外，在交互机制上，我们不再仅仅让模型单步输出坐标并盲目点击，而是将 Computer Use 提升为代码级调度——模型能够直接在沙箱环境中编写并执行结构化的 JavaScript 与 **Playwright** 脚本，在一个执行周期内批量完成数十个状态操作，运行效率与容错率呈指数级提升。

<details>
<summary>Original English</summary>

**Ari Weinstein**: Over the past year, models developed profound debugging capabilities. When something fails, they can diagnose why and try alternative strategies. Furthermore, instead of sequential single-action mouse clicks, the agent can write and execute JavaScript and Playwright scripts directly in the environment, bundling multi-step actions into a single cycle, which dramatically accelerates execution.

</details>

### 评测基准与多模态感知：不仅是截图，更是语义树

**主持人**: 主题演讲中提到，全新模型的运行速度提升了整整七倍，在各类自动化基准评测中均取得了重大突破。在 OpenAI 内部，你们是如何量化评估 Computer Use 性能提升的？这主要归功于模型能力还是系统调度线束（Harness）的优化？

<details>
<summary>Original English</summary>

**Host**: The keynote highlighted a 7x speedup and major benchmark leaps. Internally, how do you measure these improvements? Is the gain primarily coming from the model itself, or from the harness surrounding it?

</details>

**Ari Weinstein**: 评估这一能力极其复杂，因为生产级产品中包含了动态的安全拦截与验证机制。我们通过大量真实场景的排列组合进行闭环测试。结论是：性能跃迁既来自于模型权重的智力增强，也来自于外围线束工程的巨大突破。例如在成本效益方面，新一代模型相比以往方案不仅吞吐翻倍，推理成本更是大幅下降，帕累托前沿曲线显著外推。

<details>
<summary>Original English</summary>

**Ari Weinstein**: It's a combination of both. In our benchmarks, we see steady compounding gains from both the raw model intelligence and the surrounding harness architecture. The Pareto frontier has shifted dramatically, offering substantially higher success rates at significantly reduced token cost.

</details>

**Ari Weinstein**: 过去系统最大的顿悟时刻之一，就是摆脱了对纯像素视觉截屏的单一依赖。以前的 Agent 浏览网页，需要截一张图、分析、下滑滚动、再截一张图，整个过程充斥着无谓的网络 I/O 和延迟。而现在，我们打通了多模态辅助功能树（Accessibility Tree）和 DOM 结构树，Agent 可以同时获取全页面的语义元数据，直接定位深层元素，并结合视线截图辅助确认，大幅消除信息死角。

<details>
<summary>Original English</summary>

**Ari Weinstein**: A major breakthrough was moving beyond pure pixel screenshots. Previously, an agent had to screenshot, inspect, scroll, screenshot again, and repeat. By integrating Accessibility APIs and direct DOM tree access, the model perceives the full structured context of an application alongside visual cues, eliminating massive amounts of latency.

</details>

### AppShots 机制与端到端系统瓶颈

**主持人**: 这就像我们在 **macOS** 上的 **Codex** 或 **ChatGPT** 桌面端双击 Command 键触发的应用快照（AppShots）功能一样。很多普通用户误以为那只是一张普通的屏幕截图，实际上它底层捕获了全部无障碍语义节点与元数据？

<details>
<summary>Original English</summary>

**Host**: That resembles the AppShots feature in Codex and the macOS desktop app when you double-press Command. Users often assume it's a basic screenshot, but under the hood, it captures the entire accessibility tree and structural metadata, right?

</details>

**Ari Weinstein**: 完全正确。如果只传一张截图，模型根本无法感知那些被遮挡的超链接目标、隐藏字段或日历中被截断的会议全名。而 AppShots 提取了系统底层的可访问性语义表示。我们团队投入了大量心血对这些语义文本进行了极致的 Token 压缩，既保留了精准的层次关系，又避免了上下文窗口的过度膨胀。这也是计算机辅助技术对 AI 发展反哺的一个绝佳案例。

<details>
<summary>Original English</summary>

**Ari Weinstein**: Exactly. A visual screenshot alone cannot reveal target URLs of buttons or clipped text in a calendar invite. AppShots extracts the structural accessibility representation. We spent extensive engineering effort optimizing token efficiency so that this rich context fits compactly into the model's prompt.

</details>

**主持人**: 展望未来两到三年，Computer Use 走向真正自主代理的核心瓶颈到底在哪里？究竟是模型推理智力的限制，还是物理环境加载与执行工具的延迟？

<details>
<summary>Original English</summary>

**Host**: Looking ahead two to three years, where are the primary bottlenecks holding back fully autonomous computer agents? Is it model intelligence, or the physical latency of environments and application loading?

</details>

**Ari Weinstein**: 随着模型推理速度的狂飙，我们越来越明显地观察到：瓶颈正从模型端转移到外部应用本身。例如在自动化基准测试中，Agent 执行一个外卖订餐任务，超过 80% 的时间其实是在干等网页资源和第三方脚本的加载。因此，如何构建事件驱动（Event-Driven）的响应架构，而非简单的静态轮询（Polling），让模型在页面状态变更的毫秒级瞬间做出下一步反应，是未来必须攻克的工程高地。

<details>
<summary>Original English</summary>

**Ari Weinstein**: As models become faster, the execution environment increasingly becomes the bottleneck. In tasks like ordering food on DoorDash, the agent spends most of its time waiting for web pages and network assets to load. Shifting from synchronous polling to event-driven architectures where the agent reacts instantly to DOM mutation events is crucial for closing this gap.

</details>

### 开发者实践、安全红线与自主软件工程

**主持人**: 面对已经开放的 API，你对广大开发者有哪些避坑建议？在给予 Agent 如此强大的系统操控权时，该如何权衡生产安全与用户信任？

<details>
<summary>Original English</summary>

**Host**: For developers building on this newly released API, what pitfalls should they avoid? How should they balance expansive agent capabilities with safety boundaries and user trust?

</details>

**Ari Weinstein**: 首先，必须坚持“关键决策引入人类确认（Human-in-the-Loop）”的原则。对于敏感操作，例如大额支付、不可逆的系统设置更改或涉及隐私凭据的操作，必须强制弹出授权请求。其次是最小权限原则，开发者应严格限定 Agent 可访问的域名白名单和应用目录，绝不能在无沙箱隔离的环境下赋予其全局根权限。

<details>
<summary>Original English</summary>

**Ari Weinstein**: First, maintain human-in-the-loop safeguards for high-stakes actions like financial transactions or destructive data modifications. Second, enforce least-privilege scoping: sandbox the agent's environment and restrict network access strictly to the domain whitelist required for the designated task.

</details>

**Ari Weinstein**: 另外，我个人最痴迷的一个用例是“Agent 闭环软件工程”。在以前，开发者用 Codex 生成代码后，必须自己充当 QA 人工测试并排错；而现在，我们可以让一个 Agent 负责编写代码，另一个 Computer Use Agent 负责拉起真实浏览器或桌面客户端进行端到端视觉与功能测试，并自动截屏反馈缺陷报告。这种多 Agent 协作将彻底重塑软件开发生命周期。

<details>
<summary>Original English</summary>

**Ari Weinstein**: One of my absolute favorite use cases is closed-loop software engineering. Previously, engineers generated code with Codex and manually tested the UI. Now, a coding agent can build a feature, while a computer-using agent launches the application, runs end-to-end tests, inspects UI regressions, and reports back fixes, completely automating the development feedback loop.

</details>

### API 架构跃迁：异步工具调用与消息注入

**主持人**: 非常感谢 Ari 的精彩分享！接下来让我们欢迎掌管 OpenAI API 产品线负责人 **Nikunj Handa**。Nikunj，你好！能否先向大家介绍一下你在团队中的职责，以及本次 API 层面有哪些核心架构升级？

<details>
<summary>Original English</summary>

**Host**: Thank you so much, Ari! Next, let's welcome Nikunj Handa, Head of API Products at OpenAI. Nikunj, could you introduce yourself and walk us through the major architectural advancements introduced in the API today?

</details>

**Nikunj Handa**: 大家好，我叫 Nikunj，在 OpenAI 负责 API 产品团队已经近三年了。我们的核心职责就是紧密对接后训练（Post-Training）和研究团队，将最前沿的模型能力以最低延迟、最高可靠性的工业级接口开放给全球开发者。

<details>
<summary>Original English</summary>

**Nikunj Handa**: Great to be here! I'm Nikunj and I lead the API product team at OpenAI. Our mission is to bridge post-training research breakthroughs into robust, low-latency, scalable developer primitives.

</details>

**Nikunj Handa**: 本次底层架构最核心的演进之一，就是推出了原生的**异步函数调用（Asynchronous Function Calling）**与**运行中消息注入（Steering / Message Injection）**机制。以往的工具调用是严格阻塞的：模型触发工具后必须暂停生成，等待外部系统返回结果后再继续。但在复杂的 Agent 任务中，某些工具执行耗时极长。现在，开发者可以发起异步工具调用，让后台长时间运行，同时模型可以继续执行其他子任务；在工具返回前，开发者甚至能动态向流式会话中注入控制指令（Steering Instructions），动态调整模型的执行轨迹，极大增强了系统的灵活性与可控性。

<details>
<summary>Original English</summary>

**Nikunj Handa**: One of the biggest architectural upgrades is native asynchronous tool calling and mid-stream steering. Previously, function calling was strictly synchronous and blocking. Now, models can dispatch long-running asynchronous tasks while continuing reasoning, and developers can inject steering instructions into the active trajectory to correct or pivot agent behavior dynamically.

</details>

### WebSocket 架构与极速推理通道

**主持人**: 这背后的通信协议支撑必然经过了重构。是不是全面依赖了 **WebSocket** 双向通道？这与大家热议的超高速推理模型有何关联？

<details>
<summary>Original English</summary>

**Host**: This must require major communication protocol changes. Is this built entirely on bidirectional WebSockets, and how does it relate to the ultrafast reasoning capabilities being discussed?

</details>

**Nikunj Handa**: 没错。早先我们在实时语音产品中引入了 WebSocket，而现在我们将其作为通用 Agent 交互的基石架构。基于全双工连接，客户端与服务端能够以微秒级延迟完成消息收发、事件通知与中断信号传递，这使得模型交互具备了近乎实时的顺畅感。

<details>
<summary>Original English</summary>

**Nikunj Handa**: Exactly. We leveraged our WebSocket foundation from real-time audio to create a unified duplex transport for agentic APIs. Full-duplex connections allow bidirectional streaming of tool outputs, interrupts, and steering tokens with minimal transport overhead.

</details>

**Nikunj Handa**: 尤其是在配合超低延迟模型运行时，WebSocket 的优势体现得淋漓尽致。为了让 Agent 做出决策的速度媲美人类神经反射，推理团队在架构层面对 首字延迟（TTFT, Time To First Token）进行了极限压榨，让前沿模型的推理吞吐迈入全新量级。

<details>
<summary>Original English</summary>

**Nikunj Handa**: This becomes indispensable when paired with our ultrafast inference stacks. By aggressively optimizing Time To First Token (TTFT), the model can produce tactical decisions almost instantly, matching human conversational and operational cadence.

</details>

### 揭秘 Decisions API：专为高频分类与决策而生

**主持人**: 聊到极速推理，就不得不提今天备受瞩目的 **Decisions API**。最近两周开源社区对类似高速决策架构的讨论甚嚣尘上。请问 Decisions API 诞生的背景是什么？它到底是不是一个全新的独立预训练模型？

<details>
<summary>Original English</summary>

**Host**: Speaking of speed, let's address the elephant in the room: the Decisions API. The community has seen a massive surge of interest around fast decision models. What was the genesis of Decisions API, and is it a completely new foundation model?

</details>

**Nikunj Handa**: 首先必须向开源先锋团队致敬，社区的敏捷探索极大地启发了行业。大约几周前，我们内部运维与客户支持团队急需一个能够以极限速度对海量工单进行实时高精度分类的系统。基础设施团队迅速介入，验证了在保留前沿大模型核心权重的前提下，通过专有推理优化实现超高速确定性输出的可行性。

<details>
<summary>Original English</summary>

**Nikunj Handa**: Credit to the open-source community for pioneering incredible ideas in this space. Internally, our customer operations team needed ultra-low-latency ticket triage. Our infrastructure engineers realized we could optimize our frontier reasoning weights to serve rapid, deterministic classification tasks at breakthrough speeds.

</details>

**Nikunj Handa**: 需要澄清的是：Decisions API 在第一版中并不是一个从头全新预训练的模型，它直接复用了我们前沿核心模型的知识底座，但通过深度重构推理管线，剔除了冗余参数评估逻辑，专门为**结构化输出（Structured Outputs）**进行了硬件级优化。结合并行推理解码技术，将 TTFT 压缩到了极致，使开发者能够在数十毫秒内获得确定的枚举判断或路由决策。

<details>
<summary>Original English</summary>

**Nikunj Handa**: To clarify: version one is not a ground-up pre-trained model. It leverages our proven frontier weights, but strips away decoding overhead and heavily optimizes the inference stack specifically for structured outputs. This delivers deterministic categorization decisions within tens of milliseconds.

</details>

### Agency API 与第一方产品生态实践

**主持人**: 在实际业务中，开发者该如何将 Decisions API 与更高阶的 **Agency API** 结合使用？你们内部有哪些典型的落地实践？

<details>
<summary>Original English</summary>

**Host**: How should developers architect solutions using Decisions API alongside the higher-level Agency API? What are the prominent internal use cases at OpenAI?

</details>

**Nikunj Handa**: 内部最直接的应用就是高吞吐路由与自动化安全合规审查。以往的大模型作为仲裁者（LLM-as-a-Judge）成本高且响应慢，而在 Decisions API 加持下，实时流审查变得切实可行。

<details>
<summary>Original English</summary>

**Nikunj Handa**: The most immediate application is high-throughput routing, automated triage, and real-time safety classification. Traditionally, using an LLM as a judge incurred significant latency and token costs. Decisions API turns real-time moderation and arbitration into a zero-latency utility.

</details>

**Nikunj Handa**: 与此同时，我们发布了全新的 Agency API。实际上，OpenAI 最近亮相的一系列第一方高级智能体产品——例如可自主加入 Zoom 会议生成交互式摘要的智能日程助手、以及深度协作画布工具——全部是直接构建在 Agency API 之上的。它原生封装了长程记忆检索、沙箱隔离执行与环境交互协议，开发者完全可以复用这些经过海量生产验证的基础构件。

<details>
<summary>Original English</summary>

**Nikunj Handa**: Furthermore, our newly released Agency API serves as the underlying backbone for OpenAI's own first-party agent products, including our interactive meeting assistants and collaborative editing tools. It natively encapsulates long-term thread state, sandboxed runtime management, and tool routing.

</details>

### 缓存体系演进：从 30 分钟默认到 12 小时长效保障

**主持人**: Agent 在连续多轮对话中会频繁携带庞大的历史上下文。面对由此带来的延迟与 Token 账单痛点，底层 Responses API 在缓存（Prompt Caching）方面有哪些重大改进？

<details>
<summary>Original English</summary>

**Host**: Agents inherently generate massive historical context over prolonged trajectories. How does the Responses API evolve its Prompt Caching infrastructure to mitigate cost and latency?

</details>

**Nikunj Handa**: 缓存对于长程 Agent 来说就是生命线。我们在 Responses API 栈中全面重写了上下文调度逻辑。除了现有的自动缓存匹配外，我们正式推出了长效缓存保障机制：标准缓存提供约 30 分钟的高速命中，而针对高频会话与生产级服务，我们开放了最长达 **12 小时的长效缓存保障（12-Hour Cache Guarantee）**。

<details>
<summary>Original English</summary>

**Nikunj Handa**: Prompt caching is existential for long-running agents. We completely re-architected the caching layer in Responses API. Beyond our standard 30-minute transient cache, we are introducing an extended 12-hour cache SLA for enterprise workloads.

</details>

**Nikunj Handa**: 不仅如此，我们还上线了**缓存预热 API（Cache Warmup API）**。如果开发者预知未来数小时内将发起密集批处理或交互式会话，可以提前以极低费用触发预热，确保后续调用 100% 命中缓存。结合最新推出的高性价比模型，提示词读取费用直降 95%，为极大规模上下文的持续运行提供了坚实的经济可行性。

<details>
<summary>Original English</summary>

**Nikunj Handa**: We also added a Cache Warmup API. If you anticipate a traffic burst or an intensive agent session, you can pre-warm the prompt cache ahead of time. Coupled with our new efficient model variants, cache read costs drop by up to 95%, making large-context deployments economically viable.

</details>

### 上下文极限与压缩策略：服务端托管与手动紧缩

**主持人**: 尽管百万级 Token 上下文窗口已经普及，但面对长达数天甚至数周的自主任务，上下文依然不可避免地会触及物理上限。目前行业最佳实践中的上下文压缩（Context Compression）是如何设计的？

<details>
<summary>Original English</summary>

**Host**: Even with million-token context windows, long-horizon agents running over days will eventually exhaust context limits. What is the current state-of-the-art methodology for context compression?

</details>

**Nikunj Handa**: 我们在 API 层面提供了两种主流解决方案。第一种是**服务端全托管自动压缩**：当会话上下文逼近安全阈值时，Responses API 会在服务端自动触发语义摘要与关键状态剪枝，平滑释放上下文空间，对上层逻辑完全透明。

<details>
<summary>Original English</summary>

**Nikunj Handa**: We support two primary paradigms. The first is server-managed automatic compaction: when the trajectory nears context thresholds, Responses API automatically executes background semantic pruning and summarization transparently.

</details>

**Nikunj Handa**: 第二种则是面向追求极致控制力的大型机构的**显式手动压缩（`/compact` 接口）**。正如大家在开源的 **Codex-Harness** 中看到的那样，许多高阶团队更倾向于自主掌控压缩触发时机，结合专用算法与文件系统挂载状态来精确保留关键变量。我们正在持续探索基于分布式文件状态的上下文卸载技术，未来将为开发者提供更加模块化的压缩原语。

<details>
<summary>Original English</summary>

**Nikunj Handa**: The second approach is manual compaction via explicit endpoints like `/compact`, mirroring the design in our open-source Codex-Harness. Advanced engineering organizations often prefer programmatic control over compaction policies, preserving key architectural state while pruning redundant trajectory history.

</details>

### 总结展望：构建原生 AI 云计算基础设施

**主持人**: 节目的最后，回望整个平台的发展，这不仅是发布了几个孤立的模型或接口，而是如同一年前所预示的那样：OpenAI 正在搭建一套完整的原生 AI 云基础设施。

<details>
<summary>Original English</summary>

**Host**: Looking at the broader picture, this is not just about isolated model releases. It aligns with the long-term vision: OpenAI is methodically constructing an AI-native cloud computing platform.

</details>

**Nikunj Handa**: 正是如此。正如几十年前 AWS 定义了云计算的 **EC2** 计算实例与 **S3** 存储桶一样，今天我们在 AI 原生时代，也在定义属于智能体的基础算子——从底层的 Decisions API 快速仲裁、Responses 异步双向连接、到长效缓存与云端原生 Computer Use 运行环境。这些积木正在快速成熟，我们热切期待与全球开发者共同定义智能体计算的未来！

<details>
<summary>Original English</summary>

**Nikunj Handa**: Exactly. Just as AWS pioneered EC2 and S3 for internet-scale compute and storage, we are defining the foundational primitives for the agentic era—Decisions API for instantaneous control flow, Responses for duplex streaming, and hosted Computer Use environments. We invite developers worldwide to build this future alongside us.

</details>