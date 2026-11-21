---
author: Latent Space
date: '2026-05-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kaX43RRRUKY
speaker: Latent Space
tags:
  - ai-agent
  - compute-sandbox
  - bare-metal-infrastructure
  - computer-use
  - agent-cloud
title: AI 智能体需要电脑：Daytona 的 74% 月增长背后的计算基建革命
summary: Daytona 创始人 Ivan Burazin 深入探讨了 AI 智能体（AI Agents）计算基建的演进。文章揭示了智能体与人类在计算需求上的本质差异，分析了 Daytona 如何通过裸金属架构实现 60 毫秒级的极速沙箱启动，并预测了价值 25 万亿美元的“计算机使用”（Computer Use）市场将如何重塑软件产业，最终催生出专门为智能体设计的“智能体云”。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Ivan Burazin
companies_orgs:
  - Daytona
  - OpenAI
  - Anthropic
  - Salesforce
  - Microsoft
  - Equinix
products_models:
  - Devon
  - OpenHands
  - Docker
  - Kubernetes
  - Firecracker
media_books: []
status: evergreen
---
### 从浏览器 IDE 到智能体沙箱：Daytona 的战略转折

**Ivan Burazin** 作为 **CodeAnywhere**（最早的基于浏览器的 IDE 之一）的联合创始人，长期以来一直深耕于开发者体验领域。他与合伙人的合作经历了多次创业的磨合，从早期的服务器虚拟化到举办名为 **Shift** 的开发者大会，最终回归到技术底层，创立了 **Daytona**。最初，Daytona 的目标是为人类工程师自动化开发环境（End of localhost），但在 2024 年底，随着 **Devon**（现名为 **OpenHands**: 开源的 AI 软件工程师）等智能体的出现，Ivan 敏锐地察觉到了市场的剧变。

他们发现，虽然为人类设计的开发环境自动化已经很成熟，但**大语言模型智能体**（AI Agents: 能够自主执行任务的 AI 系统）对计算环境的需求完全不同。当他们尝试将现有的基础设施提供给智能体开发者时，收到的反馈几乎全是负面的。智能体需要的不是一个持久的、适合人类长期工作的桌面，而是一个能够通过 API 快速调用、具备极高性能且高度可编程的**计算沙箱**（Compute Sandbox: 隔离的、可编程的执行环境）。这种极其强烈的市场需求（Market Pull）让 Ivan 意识到，他们正站在一个比人类开发者市场大得多的蓝海面前——即为未来每一个可能存在的智能体提供计算动力。

<details>
<summary>Original English Source</summary>

I've never experienced this that people literally call you if you do not give them access. Like they want access right now. And so it's like, okay, they don't want this. The thing that they want doesn't seem to exist or they have not found it and they really really want what what we want. And then when we understood that we're on to something. And then when you think about the size of the market, like the market for every single agent that will exist ever in the future is just like what is that market? How big is that?

I was one of the co-founders of code anywhere the first browser based idea and so we were thinking a long time of like local host should die. We originally started stacking stacking servers doing like virtualization in the early 2000s and you know routters and doing basically all these things at a foundational level and that was a services company which we sold to focus on what my co-founder actually invented which was the very first browser based IDE.

3 years ago we started something similar with Daytona which is not what we were what we are today but it was automating dev environments for human engineers. the basically the underlining stack of code anywhere and then we we did a hard pivot last January to sandboxes and so here we are.

</details>

### 裸金属架构与 60 毫秒启动：重构智能体计算原语

在技术实现上，Daytona 选择了与主流路径完全不同的**第一性原理**（First Principles）。大多数提供商（如 **Firecracker**）选择在虚拟机（VM）之上运行沙箱，但这会带来显著的网络延迟和 I/O 损耗。Daytona 决定直接运行在**裸金属**（Bare Metal: 不经过虚拟化层的物理服务器）上，并自主编写了**调度器**（Scheduler: 负责分配计算资源的系统组件）。这种架构带来的优势是毁灭性的：一个带网络延迟的沙箱启动请求仅需 **60 毫秒**即可完成。

这种极速性能对于**强化学习**（Reinforcement Learning: 通过试错进行学习的 AI 训练方法）任务至关重要。目前，Daytona 约 50% 的工作负载来自 **RL** 训练和评估。在这些场景中，GPU 的成本远高于 CPU，因此开发者希望 CPU 端的环境准备能够瞬间完成，以确保昂贵的 GPU 保持 100% 的利用率。此外，Daytona 的沙箱具备**动态调整大小**（Dynamic Resizing）的能力，可以在运行过程中无缝增加内存或 CPU 核心，这在传统的 **Kubernetes** 环境中几乎是不可能实现的。这种“即时计算”的能力，使得 Daytona 更像是一个计算领域的 **Twilio** 或 **Stripe**，通过极简的 SDK 和 API 提供底层复杂的计算能力。

<details>
<summary>Original English Source</summary>

The reason why Daytona is like super super fast and you see this on benchmarks is we essentially we run on bare metal. We have our own scheduler. um we use the underlining uh disk, CPU and RAM of the underlining machine which means your IOPS are insanely fast because there's no you know there's no network between an EBS or something like that but also the snapshot the point in time the templates are also preloaded on the bare metal machines.

So when you fire off a sandbox from a template or a snapshot, um you you're essentially directed to the bare metal machine where that snapshot is based on that NVMe drive and then it literally just turns on that machine and it's local. There's no network latency, anything on there.

Our time to spin up one is 60 milliseconds with network latency. So request spin up reply 60 the whole thing 60 milliseconds that is one. But if you want to spin up 50,000 at once, we are now at about 75 seconds.

The reason why a lot of people come to us is because GPUs are more expensive than CPUs right so you want your GPU running at what 100% the entire time and so when you're running runs on CPUs when the CPU cycle is like down and spinning up the next one you want that to be instantaneous so that your GPU doesn't go down right.

</details>

### 计算机使用（Computer Use）：解锁 10 万亿美元的知识工作市场

Ivan 提出了一个极具前瞻性的论点：智能体最强大的形态是能够像人类一样使用计算机。尽管目前提倡 **无头模式**（Headless: 无图形界面的操作模式）或通过 API 交互，但全球价值 **50 万亿美元**的知识工作市场中，有超过一半的工作流被锁定在 **Windows** 等系统的遗产应用（Legacy Apps）中。这些应用没有 API，也不会在短期内被重写。因此，给智能体一个能够运行完整操作系统（甚至是带显卡的 Windows 桌面）的沙箱，是解锁这些价值的关键。

这标志着 **RPA**（Robotic Process Automation: 机器人流程自动化）的二次飞跃。传统的 RPA 极度脆弱，但具备**计算机使用**（Computer Use: AI 直接操作 GUI 的能力）能力的智能体可以像人类实习生一样登录网站、导出报表并处理端到端的复杂任务。Daytona 正在积极推进 **Windows 沙箱**和 **Mac OS 沙箱**的支持。尽管 Mac OS 存在极其严苛的许可限制（如每台机器仅限两个并行虚拟机、每 24 小时只能分配给一个用户），但对于顶级 AI 实验室来说，为了让模型学会在 Mac 环境下工作，这些成本是必须付出的。

<details>
<summary>Original English Source</summary>

If we look at knowledge work in general, there's about 100 million knowledge workers in the US, about a billion in the world and knowledge workers and the salaries of them aggregate to 10 trillion in the US, 50 trillion worldwide. And most of them most of that work is actually still locked into legacy apps inside of Windows which is not going anywhere for a very very long time.

If an agent is more sophisticated, can go through more runs, figure stuff out, let's say it's like 40%, right? And so if you take 40% of that, you get to essentially like 10 trillion dollars. That is a T.

We've created an actual sandbox. So it's a second instead of milliseconds but you have like point in time snapshots. You have like forking. Windows specifically is something very very new. We will have Mac OS sandboxes fairly soon. The problem with Mac OS sandboxes is a licensing thing. one, you're allowed to run only two parallel VMs per machine. Two, you can only license to a different user every 24 hours.

</details>

### 智能体云（Agent Cloud）：未来计算的新范式

Ivan 认为，软件行业的估值逻辑正在发生变化。过去，市场会给那些转售 AI 令牌（Tokens）的 **SaaS** 厂商溢价，但他认为这是错误的，因为这种模式的毛利率极低且缺乏粘性。真正的价值增长点在于**API 消耗**（API Consumption）：像 **Salesforce** 这样将所有产品通过 API 暴露给智能体，并按使用量计费，才是真正的再加速。随着智能体数量呈指数级增长，对 CPU 的需求最终会像 GPU 一样出现短缺，因为每一个智能体任务都需要一个独立的计算沙箱。

最终，市场将催生出一种全新的基础设施形态——**智能体云**（Agent Cloud）。这种云不再仅仅提供原始的虚拟机，而是集成了一系列专门为智能体设计的**原语**（Primitives）：包括极速启动的沙箱、智能体专用的数据库（如 **SQLite** 或 **Neon**）、网页搜索接口以及智能体协作层。在这个范式下，传统的 **Git** 和 **CI/CD** 流程也将被重构，因为智能体会产生海量的 **PR**（Pull Request）和测试需求，目前的基建已无法承载。Daytona 的目标正是成为这个智能体云的核心计算层。

<details>
<summary>Original English Source</summary>

I feel that the market is adding premium to SAS vendors that are reselling tokens. And I think that's incorrect. I don't want your agent essentially because what happens Right now we have a problem that you have data siloed in click house quickbooks and now you're giving me an agent that'll give me the data but it's still siloed.

Just expose everything and charge me for that so charge me for consumption of API. That is actual revenue and that is actual real acceleration.

There will be an equivalent everyone says like an AWS for AI agents but it might look more like stripe than AWS. There will be a cloud built out specifically for agents and so that cloud will have sandboxes and it will have web search and it'll have databases like SQLite or neon specifically for agent and other things. We are not at the end of the new infrastructure primitives for agents. There are more coming.

</details>