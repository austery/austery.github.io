---
author: a16z
date: '2026-10-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rn_afJaPldg
speaker: a16z
tags:
  - cloud-computing
  - ai-agent
  - custom-silicon
  - data-center
  - infrastructure-scaling
title: AWS CEO Matt Garman深度解析：如何为AI Agent时代重构云计算帝国与万亿算力底座
summary: AWS首席执行官Matt Garman深入剖析了云计算在生成式AI与Agent时代的根本性演化。访谈涵盖了AWS如何平衡前沿模型实验室与初创团队的算力分配、自研芯片（Nitro、Graviton、Trainium）的演进逻辑、年均数千亿美元资本支出的电力与供应链约束、为AI Agent重构的云原生基础设施（沙箱、瞬态数据库、精细化权限），以及大企业落地自主Agent的评估与组织架构重塑。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Matt Garman
companies_orgs:
  - AWS
  - Amazon
  - Nvidia
  - Anthropic
  - OpenAI
products_models:
  - Amazon Bedrock
  - Trainium
  - Graviton
  - Firecracker
  - Amazon EC2
media_books:
  - The Goal
status: evergreen
---
### 开场与核心议题预热

**主持人**: 欢迎大家收看本期播客。今天我们邀请到的重磅嘉宾是 **AWS** 的首席执行官 **Matt Garman**。我们正身处一个极其震撼的变革时代，无论是在算力基建的前沿，还是在企业级软件的演化方向上，都有太多令人兴奋的话题。马特，非常欢迎你来到我们的节目。

<details>
<summary>Original English</summary>

**Host**: Welcome to the podcast, Matt. We are truly living in an incredible, wild time in technology. There is just so much happening across compute infrastructure and the future of enterprise software that I can't wait to dig into. Welcome to the show, Matt. It's great to have you here.

</details>

**Matt Garman**: 太棒了，非常感谢你的邀请。我非常高兴能来这里和大家交流，现在这个行业里发生的一切确实令人心潮澎湃。

<details>
<summary>Original English</summary>

**Matt Garman**: Great. Thanks for having me on. I'm really excited to be here and chat with you. It really is an extraordinary moment in the industry.

</details>

**主持人**: 在深入探讨之前，我想先引用你在开场前提到的一些精彩洞察：**AI Agent**（人工智能智能体）在工作流中的运行表现，在 AWS 上往往比在其他任何云平台上都要出色得多。从计算沙箱、网关，到智能体权限与人类权限的分离机制，你们正在积极构建并打磨大量的底层组件。但与此同时，前沿大模型实验室正在吞噬市面上几乎所有的 **GPU** 算力，而你们又必须兼顾并培育那些未来可能成长为科技巨头的初创企业。你们究竟是如何在两者之间取得平衡的？

<details>
<summary>Original English</summary>

**Host**: Before we jump into the full story, I want to touch on what you mentioned earlier: agent workflows tend to perform significantly better on AWS than anywhere else. Computing sandboxes, gateways, agent permissions versus human permissions—these are all primitives you are actively building and refining. But at the same time, the frontier AI labs are consuming virtually every GPU available, while you also want to nurture the new startups that will become tomorrow's enterprises. How do you think about striking that balance?

</details>

**Matt Garman**: 从 AWS 成立的第一天起，初创企业就始终是我们业务的核心命脉。他们始终站在技术的最前沿，最先探索出什么才是可能的。因此，我们在为初创企业预留算力容量方面是非常自觉且具有战略意向的。我们最近宣布将在未来几年内采购大约 **200万颗 Nvidia GPU**。伴随着巨大的资本支出——到2026年全行业乃至相关的投入规模可能高达数千亿美元，这种旺盛的需求在短时间内绝对不会放缓。而在当前关于 AI 扩展风险、供应链韧性与安全漏洞的广泛讨论中，企业 CEO 们最关心的也是如何安全地拥抱这一浪潮。

<details>
<summary>Original English</summary>

**Matt Garman**: Since the very beginning of AWS, startups have been the core lifeblood of our business. These are the innovators who are at the cutting edge of technology, figuring out what's possible before anyone else does. We are very intentional about reserving capacity for startups. We recently announced that we will be purchasing something like two million Nvidia GPUs over the next couple of years. Across the industry, we're talking about massive CapEx numbers—something like $220 billion in total commitments. Demand is so enormous that we don't anticipate it slowing down anytime soon. And amidst all the talk about AI scaling risks and new attack vectors, enterprise CEOs are primarily asking how they can harness this securely.

</details>

### 从EC2初代GM到年化营收千亿级帝国

**主持人**: 让我们从最开始的故事聊起吧。很多人可能不知道，你其实是 **Amazon EC2** 的第一任总经理（GM），对吧？

<details>
<summary>Original English</summary>

**Host**: Let's take it from the very beginning. Many people might not know this, but you were actually the very first GM of EC2, right?

</details>

**Matt Garman**: 没错，确实是这样。

<details>
<summary>Original English</summary>

**Matt Garman**: Yeah, that's right.

</details>

**主持人**: 那可是早在 2006 年的事情了！而到了今天，AWS 的年化营收运行率已经达到了大约 1600 亿到 1700 亿美元的规模，年增长率依然保持在百分之三十几的高位。以如此庞大的体量实现这种增速，简直不可思议。

<details>
<summary>Original English</summary>

**Host**: That goes back to 2006, right? And today, your revenue run rate is somewhere around $160 billion to $170 billion, growing at something like 35% to 37% year-over-year. To deliver that kind of percentage growth at a $160-plus billion run rate is just mind-boggling.

</details>

**Matt Garman**: 是的，现在我们大约是在 1690 亿到 1700 亿美元这个区间，并且保持着强劲的增长势头。这里的商业机会实在是太宽广了。当你回想起业务产生第一块钱收入的第一天，再对比今天的规模，确实非常奇妙。

但真正有趣的地方在于，无论是这项业务未来的成长空间，还是我们能够为客户带来的商业价值，我们目前其实依然处于**极早期阶段**。现在世界上绝大多数的 IT 工作负载，依然运行在传统的本地部署（On-Premise）数据中心里。而且，人类社会和企业每天所消耗的计算总量，都比前一天要多得多。我们一方面享受着传统工作负载向云计算迁移的长期顺风，另一方面又迎来了人工智能带来的巨大算力推力。能够参与并推动这项业务以如此之快的速度狂飙突进，是一件极具成就感的事情。

<details>
<summary>Original English</summary>

**Matt Garman**: Yeah, we're right around $169 to $170 billion, growing very rapidly. It's awesome, and there are just so many opportunities ahead. When you reflect on Day 1, when we brought in our very first dollar of revenue, it's pretty fun to see how far it has come. But what's even more interesting is that in terms of where this business can go and the opportunities that exist for our customers, we are still in the very early stages. The vast majority of global workloads are still running on-premises, and the total amount of computing people are doing every single day is higher than it was the day before. You've got the tailwind of the secular shift to the cloud, combined with this massive tailwind from AI. It has been a ton of fun to see the business grow so fast and to be a part of it.

</details>

**主持人**: 确实如此。关于这段历程，未来很多年里都会有历史学家和商学院学者不断著书立说。你刚才提到了本地部署，这让我非常感慨——过去各家企业都把资产留在自己的物理机房里，而如今大家都在千方百计地把它们迁移到 AWS 上。

回想 EC2 刚起步的时期，你们最初是向初创公司推销计算资源，而今天 AWS 已经成为全球最顶级的综合云平台。回顾这段进化史，最令你印象深刻的是什么？初创公司服务模式的本质又发生了怎样的变化？

<details>
<summary>Original English</summary>

**Host**: Absolutely. People will be writing history books and business school cases about this for a very long time. It blows my mind how much compute used to be tied up on-premises, and now the entire world is trying to migrate all of that into AWS. But think about the early days of EC2: it started with selling to startups, and now it's this comprehensive global cloud platform. When you look back at that evolution, what stands out to you the most? And how has the fundamental nature of how you serve startups shifted over time?

</details>

### 初创企业：AWS永不枯竭的创新源泉

**Matt Garman**: 这背后其实有一段挺有意思的渊源。我在 2005 年夏天以 MBA 实习生的身份加入了亚马逊，当时 AWS 还只是一个内部孵化项目。我在商学院实习期间接到的课题是：做一份战略分析，搞清楚**谁会对 AWS 的云计算构想最感兴趣**？

我最终得出的结论是：**初创企业**。现在回头看，这个答案可能显而易见，但在当时却是一个非常明确的方向定位。因此，从 AWS 正式推向市场的那一刻起，初创公司就成了我们业务核心的生命线，这主要有两个深层原因。

首先，AWS 针对初创企业提供的价值主张极其具有吸引力。我们投入了海量的时间和精力，努力成为创业者最值得信赖的合作伙伴。我们不仅为他们提供底层基础设施，还指导他们如何搭建架构、如何规划未来的弹性扩展，甚至传授如何高效运营一家技术型公司。

更重要的是，从商业逻辑来看，**今天的初创企业就是明天的跨国巨头**。虽然这不是一个精确到小数点的统计，但我们估算过，**AWS 历史上大约有 30% 到 40% 的累计营收，来自于那些在最初与我们合作时还只是初创阶段的企业**。

<details>
<summary>Original English</summary>

**Matt Garman**: Yeah, it's actually a fun story. I was an intern at AWS back in the summer of 2005. At the time, it was basically an internal skunkworks project. My business school internship project was to analyze who we thought would find AWS the most interesting. The answer came back: startups. Probably not surprising in retrospect! So from the very beginning, startups have been a core lifeblood of our business for a couple of key reasons.

One is that the value proposition of AWS to startups is extraordinarily compelling. We spend a ton of time and energy trying to be a great partner to them—not just providing raw infrastructure, but also giving them tactical advice on how to get up and running, how to architect their systems so they can scale seamlessly down the road, and how to operate efficiently.

The second reason is that it's simply great business: today's startups are tomorrow's enterprises. While I don't have the exact audited number, we estimate that something like 30% to 40% of AWS's revenue comes from companies that at one point in AWS's history were early-stage startups.

</details>

**Matt Garman**: 伴随这些企业一路成长，看着他们从车库走向庞大规模并最终成为行业支柱，对我们来说是一件无比兴奋的事。这就是为什么我们至今依然坚持在初创生态中进行重仓投资，并且对那些“两个人在车库里写代码”的原型团队保持着极高的关注度。

这绝不仅仅是为了将来的财务回报，更是因为**他们是最好的老师，我们在向他们学习**。初创团队往往站在技术革新的最尖端，他们最敏锐地理解技术边界究竟在哪里。他们会推着我们的服务往前走，不断向我们提出严苛的要求：“我们需要这个新特性”、“你们必须把这个延迟降低”、“如果我们能做到某某功能，我们就能实现突破”。在绝大多数情况下，他们在技术边界上的探索，远远比传统商业银行、大型医疗机构或政府部门要激进得多。初创企业在不断拓宽技术的极限，正是这种压力迫使我们不断迭代进化，确保当大型银行在五年后提出类似的技术需求时，我们的平台早已具备了坚实且成熟的承载能力。

<details>
<summary>Original English</summary>

**Matt Garman**: It's incredibly fun for us to watch companies grow over time, scale up, and effectively become massive enterprises. That's why we invest so heavily in startups and stay hyper-focused on those brand-new, "two people in a garage" types of companies. And it's not just about the long-term business upside—it's because that is where we learn the most.

They are the innovators at the absolute bleeding edge of technology. They understand what is possible, and they push our services to their limits. They tell us what they want more of, what we need to make faster, and what capabilities they require to hit their goals. In many cases, they push us way harder than any bank, healthcare giant, or government agency ever does. Startups are the ones pushing the envelope, and that helps us get better and ensures we stay well ahead of the wave when banks come asking for that exact same technology five years later.

</details>

**主持人**: 那么对比当年和现在，初创企业向你们索取和期望的东西发生了怎样的质变？

<details>
<summary>Original English</summary>

**Host**: Let's compare then versus now. How has what startups are asking from you changed over the years?

</details>

### 初创格局剧变：超级估值、GPU狂潮与不变的基础工程

**Matt Garman**: 显而易见，现在所有人都在追着我们要大量的 **GPU**，我们稍后可以深入聊聊这个。但除此以外，行业发生了一些极其深刻的变化。

第一点，**初创公司起跑时的资本规模和雄心壮志发生了翻天覆地的变化**。在以前，一家初创公司拿到 1000 万美元的早期投资，然后慢慢打磨迭代一个应用的原型；而今天，许多 AI 初创企业从成立第一天起，估值就高达 10 亿美元，一笔种子或 A 轮融资就能拿到 2 亿美元。

<details>
<summary>Original English</summary>

**Matt Garman**: Obviously, the first thing is that everyone wants a ton of GPUs, which we can certainly talk about. But beyond that, a few things have fundamentally shifted. First, startups today begin at a scale that is completely unrecognizable compared to when we started. Back then, a startup might raise $10 million and slowly iterate on an application idea. Today, they're raising $200 million at a billion-dollar valuation on Day 1.

</details>

**主持人**: 确实，现在往往只凭一个优秀的顶尖团队和一个宏大的构想，估值瞬间就能冲上十亿美金。基本上就是刚走出风投机构的办公室，就直接推开你们的门要算力了。

<details>
<summary>Original English</summary>

**Host**: Exactly. You have a stellar founding team and an ambitious idea, and all of a sudden it's valued at a billion dollars. They walk straight out of the VC's office and walk right into your office to buy compute.

</details>

**Matt Garman**: 没错，正是这样。创意的规模和野心呈几何级数放大，因而需要海量的资本注入，导致他们在一开始就拥有庞大的资金和算力胃口。而且他们现在的商业探索非常昂贵，训练前沿基础模型、构建海量数据流水线，这些都是极其烧钱的工作。这是第一个维度的巨变——起跑线的体量极为庞大。

然而第二点，**有些底层工程逻辑其实从未改变**。即便他们拿到了天量资金，他们依然必须严肃面对那些经典的工程难题：当业务规模迅速膨胀时，底层的系统架构该如何设计？数据安全和合规性该如何保障？端到端的性能瓶颈在哪里？如果团队从 3 个人扩张到成百上千人，现有的技术栈是否能够支撑这种协同与迭代？

这正是为什么绝大多数团队最终依然坚定选择 AWS，而不是转向那些所谓的**新一代云厂商（Neo-clouds）**。因为初创公司心里很清楚，单纯堆砌 GPU 服务器是远远不够的，他们需要模型训练平台之外的一切周边工程能力、企业级安全隔离、高可用存储以及成熟的治理工具。这些基础工程底座的核心诉求，在二十年里始终如一。

但如果说有什么是全新出现的，那就是今天越来越多的技术团队不仅需要为人类工程师提供云基础设施，他们还需要**一个能够让 AI Agent 自主高效协作的云平台**。我们花了大量心血去思考：如何在大规模分布式场景下，为 Agent 提供定义极其清晰、具备极低摩擦力的标准 API 接口？如何让数据库在 3 秒钟内完全启动并就绪，从而满足 Agent 瞬间唤起算力的极致需求？这正是我们当下全力攻克的方向。

<details>
<summary>Original English</summary>

**Matt Garman**: Exactly. The scope and ambition of the ideas demand so much more capital, so they start large from the outset. And what they are doing is vastly more expensive—pursuing foundation model training and running massive workloads right out of the gate. So that initial scale is the first major change.

However, the second thing is what has remained completely unchanged. They still have to figure out how to architect for massive scale, how to think rigorously about security, and how to optimize for performance. What does it actually mean to have all the enterprise features in place so that when you grow past three employees, your systems keep scaling reliably? That is a huge part of why teams prefer AWS over neo-cloud providers. They need all the surrounding security, reliability, and breadth of capabilities that wrap around training clusters. That part has not changed at all.

What is undeniably different, though, is the sheer magnitude of scale and the fact that teams now want a cloud built to work seamlessly with AI agents, not just human engineers. We spend a tremendous amount of time thinking about how to provide well-defined API interfaces that agents can naturally traverse and orchestrate, and how to do things like spinning up databases in under three seconds so agents can execute instantly without stalling.

</details>

### 为AI Agent重构云原生积木：低延迟、沙箱与上下文层

**主持人**: 我最近一直在密切关注：你们是否已经推出了专门针对 Agent 场景构建的新服务？大家到底都在用哪些组件来打造 Agent？

<details>
<summary>Original English</summary>

**Host**: I've been meaning to check in on this: have you introduced new services specifically targeted at agents? How are people actually building these agentic workflows?

</details>

**Matt Garman**: 我们目前采取的核心策略主要体现在两方面：一是针对现有的核心服务进行深度优化，使其能够同时原生兼容人类工程师和自主 Agent 的调用；二是开发专门面向 Agent 的原生组件。

在专门构建的组件方面，我们推出了 **Amazon Bedrock Agent Core** 等一系列针对 Agent 工作流设计的编排与运行时服务。然而，如果你去看绝大多数企业用来构建数据湖和核心存储的底层底座——比如 **Amazon S3**，你会发现人类使用模式和 Agent 的数据调用行为既有重合，又有着本质不同。

为了解决这个问题，我们推出了名为 **AWS Context** 的全新功能（目前处于预览阶段）。它能够为企业构建一个统一的“上下文语义层”。无论你的企业数据是存放在 **Amazon Aurora** 关系型数据库、S3 对象存储，还是 AWS 上的其他数据仓库中，这个上下文层都能让 Agent 以极高的效率跨系统穿透并检索到所需的背景知识，而无需人类工程师编写繁琐的特定集成管道。

<details>
<summary>Original English</summary>

**Matt Garman**: What we've done is a mix of optimizing our existing services so they function natively for both humans and agents, and introducing brand-new primitives. On the dedicated side, we have capabilities like Bedrock Agent Core designed specifically for building agents. But if you look at fundamental primitives like Amazon S3, where most enterprises store their core data and build data lakes, many of the underlying use cases look similar on the surface, but require new paradigms.

For instance, we introduced AWS Context (currently in preview), which allows you to build a unified context layer. Whether your data lives in Aurora, S3, or across various AWS databases, this context layer enables an agent to easily locate and retrieve all the contextual data it needs across fragmented repositories. While a human might query each silo manually, an agent needs seamless programmatic cross-system access.

</details>

**Matt Garman**: 但更有意思的技术挑战在于：**系统的尾部延迟（Tail Latency）变得生死攸关**。

在过去，人类开发者可能并不太在意 S3 的 **P99.9 尾部延迟**，多等几十毫秒人类几乎感知不到。但对于一个需要自主执行链式思考、连续调用几十次工具的 AI Agent 来说，哪怕一次调用出现尾部延迟抖动，整个工作流就会被死死阻塞，从而导致级联延迟放大。我们在高并发、低延迟引擎方面有着长达二十年的深厚积累，因此在实际测试中，**Agent 工作流在 AWS 上的执行效率与响应表现，普遍显著优于其他云基础设施**。

<details>
<summary>Original English</summary>

**Matt Garman**: What's fascinating is how sensitive agents are to tail latency. A human developer might not obsess over the P99.9 latency of S3, but an agent executing autonomous, multi-step chains of reasoning gets completely blocked by tail latency spikes. That cascading delay ruins the entire workflow. Because low latency, high throughput, and rock-solid underlying engines have been our obsession for decades, agentic workflows consistently demonstrate superior performance on AWS compared to anywhere else.

</details>

**主持人**: 现在行业里有一个非常流行的论调：未来所有的代码都将由 Agent 编写，Agent 将全权替团队选择数据库、消息队列和邮件服务器。面对这种趋势，你们是否考虑过对那些已经存在了十几年的“遗留服务”进行彻底重构？

<details>
<summary>Original English</summary>

**Host**: There's a common refrain now that agents are going to write all the code, choose the databases, select the email infrastructure, and configure the systems. Have you had to rethink how you architect what some might call AWS's legacy services that have been around for a decade or more?

</details>

**Matt Garman**: 我们在这方面做了大量的深层思考。首先，底层的核心原子积木——计算、存储、网络协议栈——其健壮性是无可挑剔的。真正的重构在于**易用性与抽象层**。

过去二十年里，你在使用 AWS 时必须遵循极为严格的企业级规范：你必须先配置 **VPC（虚拟私有云）**，精细定义 **IAM（身份与访问管理）角色**，规划网络子网与路由表。对于初次接触或希望快速部署原型的开发者来说，这种心智负担极其沉重。用户向我们反馈：“我们知道在大规模生产时这些规则必不可少，但今天我只想在几十秒内跑通一个应用，能不能别让我处理这些复杂的安全配置？”

因此我们对新账户的开通流程进行了彻底改造：现在你可以直接使用 Gmail 账号注册，甚至无需立即输入信用卡；底层的 VPC 网络、基础 IAM 安全策略全部在后台默认自动化配置完成，**在 30 秒内就能启动一个功能齐备的完整 AWS 生产账户**。Agent 可以通过标准接口一键完成所有资源的调配，无需预先陷入网络拓扑的泥潭。

更关键的是，这绝不是一个简化的“玩具环境”。当你未来业务起飞、需要建立复杂组织架构和精细访问控制时，**你无需做任何底层架构迁移**，因为你本身就运行在原生的 AWS 环境中。你只需要平滑解锁那些深度的企业级特性即可。这种兼具极致上手速度与无上限扩展能力的架构，正是我们打磨的核心。

<details>
<summary>Original English</summary>

**Matt Garman**: We've spent a lot of time on this. The underlying building blocks are rock-solid, but we are rethinking the usability layer. Historically, setting up an AWS account required configuring a VPC, defining detailed IAM roles, setting up routing tables—all the things you absolutely need at massive scale. But customers told us that in the prototyping phase, having to manage all of that upfront was a painful trade-off when they just wanted to get an app running immediately.

So we rolled out an entirely streamlined experience. You can sign up with a Gmail account without entering a credit card upfront. All the baseline VPC configurations and IAM roles are provisioned seamlessly in the background by default, allowing you to have a fully operational AWS environment up and running in under 30 seconds. This is tailor-made for coding agents like Cursor, Claude, or Codex to deploy infrastructure immediately.

Crucially, you don't have to migrate away from this setup later. When your startup scales and you need fine-grained compliance and organizational controls, you are already on native AWS. You simply unlock that deeper functionality without any replatforming or technical debt.

</details>

### 范式重塑：瞬态资源、Firecracker与Agent安全边界

**主持人**: 随着 Agent 逐步接管开发与运维，最难适应和重构的技术痛点到底是什么？AWS 过去是靠服务人类开发者和运维团队起家的，而现在这些工作正在被软件智能体接管。作为全球最大的云提供商，这种转变带来了哪些最棘手的挑战？

<details>
<summary>Original English</summary>

**Host**: As agents take over software engineering and infrastructure management, what has been the hardest technical challenge to adapt to? AWS built its reputation serving human developers and operations teams. Now developers and ops engineers are increasingly being replaced or augmented by agents. What has been the most difficult part of that transition for the world's largest cloud provider?

</details>

**Matt Garman**: 这是一个极其深刻的范式转移（Paradigm Shift）。我们过去许多系统的设计哲学可以说是“极致的高可靠性”。

举个例子：过去当一个架构师在云上创建生产级关系型数据库（比如 **Amazon Aurora**）时，系统默认提供的是**“五个九”（99.999%）的持久性与高可用保障**，底层跨多个可用区做强一致性复制。但在 Agent 的使用场景中，大量的操作是**高度瞬态（Ephemeral）的**——Agent 可能只是想为了执行某项临时分析任务，快速拉起一个数据库，写入数据，跑完任务，然后在几分钟内将其彻底销毁。

对于这种“用完即弃”的瞬态场景，五个九的持久性架构在某种程度上可以说是严重过度设计的。但我们又不能简单提供一个不可靠的廉价存储，因为你根本无法预判 Agent 创建的这个数据库究竟只是临时测试，还是会随着后续业务演化变成一个核心生产库。因此我们必须解决这个工程两难：**既能让资源以毫秒级的极速被创建和销毁，杜绝资源浪费，又能保证在需要时能够无缝平滑演进为企业级持久化数据库**。

<details>
<summary>Original English</summary>

**Matt Garman**: It is a fascinating paradigm shift. Some of our systems were architected for absolute, uncompromising durability. For instance, if you spin up an Amazon Aurora database, it is engineered for five-nines (99.999%) of durability and high availability, replicating across multiple Availability Zones. But many agent workflows are fundamentally ephemeral—an agent might want to instantiate a database, do some processing for a few minutes, and immediately destroy it.

For an ephemeral agent use case, five-nines durability might look like an over-engineered constraint. Yet we can't simply offer non-durable, fragile infrastructure, because you never know if that database is going to be thrown away or if it will suddenly turn into a mission-critical production dataset. So the hard engineering challenge is enabling resources to be created and torn down in seconds without waste, while retaining the capability to scale seamlessly into a durable, multi-year production environment if needed.

</details>

**Matt Garman**: 另一个核心挑战在于：**Agent 需要一系列过去从未存在过的全新基础设施积木（Building Blocks）**。

例如**计算沙箱（Compute Sandboxes）**、**AI 网关（Gateways）**，以及**针对 Agent 的瞬态短期权限管理**。过去赋予人类工程师或特定微服务的 IAM 权限是相对长期且静态的；但面对 Agent，你绝对不能给它一个永久性的宽泛权限让它自由发挥。你必须赋予它**具备严格时间窗口限制、极其细颗粒度的短期凭证**。你甚至不能直接给它某个工具的完全访问权，而是需要把 Agent 隔离在一个极其严密的执行沙箱中，限制其输入输出边界。

幸运的是，我们在底层轻量级虚拟化技术上已经深耕了很多年。业内熟知的 **Firecracker MicroVM**（微虚拟机）就是我们在十年前研发并开源的。今天市面上几乎所有主流的 AI 代码执行沙箱初创公司，底层全部运行在 Firecracker 之上。它具备极高的启动速度（毫秒级），拥有硬件级的安全隔离边界，同时几乎没有任何传统笨重虚拟机的资源开销。这些轻量化、高密度的安全沙箱，正在成为 Agent 时代最关键的核心底座。

<details>
<summary>Original English</summary>

**Matt Garman**: Beyond latency, agents require entirely new building blocks that simply didn't exist before: dedicated computing sandboxes, intelligent gateways, and agent-specific permission frameworks. You cannot give an autonomous agent broad, permanent IAM roles and let it loose. You need hyper-ephemeral, time-bound, fine-grained permissions specifically scoped to a single sub-task. You need to sandbox its execution environment so it can execute untrusted code safely without compromising the broader production perimeter.

Fortunately, we've invested heavily in lightweight virtualization for over a decade. We developed Firecracker microVMs years ago to power AWS Lambda and Fargate, and today almost every leading sandbox startup in the AI ecosystem runs on Firecracker. It boots in milliseconds, offers hardware-enforced isolation, and strips away the heavy overhead of traditional VMs. These microVMs and secure runtime primitives are foundational to how agents will safely interact with production systems.

</details>

### 算力鸿沟：200万颗GPU采购与初创企业的容量保卫战

**主持人**: 让我们把焦点转向每一个创业团队最关心、也是每天被问到最多的现实问题：**到底怎么才能拿到足够的 GPU？**

前沿大模型研究实验室（如 Anthropic、OpenAI、Meta）每天都在疯狂吞噬所有能买到的 GPU 算力；而 AWS 自身又有庞大的内部业务需求。与此同时，你们还承诺要扶持中小创业团队。在这场全球性的算力抢夺战中，你们究竟如何平衡这种近乎失衡的供需关系？

<details>
<summary>Original English</summary>

**Host**: Let's pivot to the question on every founder's mind: how do you actually get GPUs? Frontier labs are swallowing every GPU coming off the line, you have internal workloads across Amazon, and you want to nurture early-stage startups that don't have massive balance sheets. How do you manage that allocation matrix?

</details>

**Matt Garman**: 这是一个极其严峻的现实挑战。首先，满足全球计算需求所需的**资本支出（CapEx）规模是前所未有的**。有机构预测，到 2026 年亚马逊的整体资本支出将达到 2000 亿甚至 2200 亿美元级别。这是人类商业史上任何单一企业都从未经历过的庞大资本投入规模。

然而，即便你拥有充足的资金，现实中依然存在无数的硬性物理瓶颈：数据中心建设速度、电网容量接入、高带宽内存（HBM）产能、芯片封装能力，甚至连专业施工承包商的调度，在各个环节都构成了制约。

<details>
<summary>Original English</summary>

**Matt Garman**: It's a huge challenge, exacerbated by several structural factors. First, the capital expenditure required to deploy this amount of compute is staggering. Projections indicate something like $220 billion in total capex by 2026 across our infrastructure investments. That is likely the largest capital deployment in a single period by any corporation in history.

Yet even with that level of capital, you hit hard physical constraints: how fast can you build data centers, how quickly can you secure grid power, and how fast can suppliers produce HBM, substrates, and chips? Even the availability of qualified construction contractors is a real bottleneck. Every single element of the supply chain faces constraints.

</details>

**Matt Garman**: 尽管算力供给极其紧张，我们在容量分配策略上保持了高度的克制与战略自觉。

我们确实与顶尖的前沿模型实验室（如 **Anthropic** 等）保持着极其深厚的战略合作关系，他们是 AWS 的超级核心客户，我们必须保障他们的超大规模训练集群；我们也有类似 **Salesforce**、**摩根大通（JPMC）** 这样对 GPU 和自研加速器有着确定需求的大型企业客户。

但是，**我们坚决拒绝把所有可用的 GPU 和 AI 加速器一股脑全卖给少数几家前沿巨头**。虽然在短期财务上看，直接签下几笔百亿美元的超级大单最简单，但我们选择不这么做。因为我们必须保护整个技术生态系统的多样性。初创企业代表着未来的技术生命力，保持多元化的客户生态对 AWS 的长期健康发展至关重要。

我们内部建立了一套严格的配额保护机制，专门为初创企业保留算力池。根据我最近看的数据，**对于初创企业提交的算力申请，我们最终能够在某种程度上满足大约 60% 的需求**。这可能意味着在时间上会有所排队延迟，或者需要部署在稍有差异的可用区，或者在拓扑配置上做微调，但我们一直在竭尽全力确保初创团队能够开箱拿到关键算力。这也是为什么我们公开宣布，将在未来几年内采购并部署多达 **200 万颗 Nvidia GPU**，以最大诚意为开发者建立容量储备。

<details>
<summary>Original English</summary>

**Matt Garman**: Despite the tight supply, our allocation strategy is highly intentional. We have massive, deep partnerships with frontier labs like Anthropic, OpenAI, and Meta, and we absolutely prioritize scaling with them. We also serve enterprise giants like Salesforce and JPMorgan Chase who require dedicated GPU clusters for fine-tuning and inference.

However, we deliberately avoid selling 100% of our capacity to a handful of frontier labs. It would be trivial to sign off our entire GPU inventory to the top three labs, but we explicitly choose not to. We need to cultivate the broader ecosystem. Today's startups will be the dominant tech companies of the next decade, and a diversified customer base is vastly healthier for AWS long term.

We actively reserve dedicated capacity specifically for startups. Right now, we are able to satisfy roughly 60% of incoming startup GPU requests in some shape or form. It might involve a slight scheduling delay, a secondary geographic region, or a slightly adjusted network topology, but we fight tooth and nail to say yes. That's also why we announced our plan to purchase two million Nvidia GPUs over the coming years—to ensure we have a massive baseline of capacity available for innovators.

</details>

### 万亿CapEx背后：AI存在泡沫吗？

**主持人**: 这确实是一场豪赌。很多人都在讨论：科技巨头投入如此庞大的 CapEx，是否正在酝酿一场巨大的 AI 基础设施泡沫？如果部分模型创企最终失败，这些服务器资产该如何收回成本？

<details>
<summary>Original English</summary>

**Host**: It is a staggering commitment. People constantly ask whether this colossal CapEx cycle is inflating a dangerous AI infrastructure bubble. What happens if a wave of these high-flying startups fails to monetize? How do you think about the risk of over-building?

</details>

**Matt Garman**: 我们经常被问到这个问题：“你们对目前的资本开支规模感到焦虑吗？你们不担心行业泡沫破裂吗？”

对于这个问题，我们的底气建立在三个关键事实上：

第一，**客户集中度风险极低**。如果你去观察某些新一代云厂商（Neo-clouds），你会发现他们往往极度依赖一两家超级大客户，前两家客户甚至占到了其总收入的 40%、50% 甚至 60%。一旦某家大模型公司调整技术路线或遭遇挫折，这些云厂商就会陷入灭顶之灾。而 AWS 的客户结构拥有极高的分散度，即便是我们最大的客户，在整体业务中的占比也仅是个位数的百分比，绝大多数客户甚至远低于这个比例。

第二，**工作负载的真实 ROI（投资回报率）已经显现**。AWS 不仅仅提供生硬的 GPU 租赁，更承载着全球最核心的企业级生产工作负载。目前我们在算力容量上的绝大部分日常消耗，实际上是来自于核心计算、存储以及**实际运行在生产线上的模型推理（Inference）**。

当我和各类企业的 CIO、CEO 沟通时，我问他们：“以你们今天在 AI 上的实际投入和成本，它是否已经为你们的业务带来了正向的投资回报率？”**几乎所有人的回答都是肯定的**。他们在代码生成、智能客服、内部数据检索、自动化审批流中已经看到了实打实的成本削减和效率倍增。这种由正向商业回报驱动的支出，根本不是靠故事吹出来的泡沫，企业绝不会停止这项支出。

<details>
<summary>Original English</summary>

**Matt Garman**: We get asked this all the time: "Aren't you nervous about a bubble? How can you justify this CapEx?" There are a few core reasons why we feel exceptionally confident in our deployment strategy.

First is diversification. If you look at some of the neo-clouds, they often have 40%, 50%, or even 60% of their entire revenue concentrated in just one or two frontier AI customers. If that customer pivots or falters, their entire business model collapses. AWS has zero customer concentration of that nature. Our largest individual customers represent low single-digit percentages of our business, and most are fractions of a percent.

Second, the vast majority of our capacity today is consumed by core compute, storage, and active inference running production applications. When you ask enterprise customers: "At today's performance and cost structure, are you seeing a positive ROI on your AI investments?" nearly all of them answer with an emphatic "Yes." They are automating code, streamlining customer support, accelerating underwriting, and seeing tangible business value. That is not bubble spending—that is durable, value-generating software engineering.

</details>

**Matt Garman**: 第三，关于创企的淘汰率——所有的 10 亿美金估值 AI 创企都能活下来吗？**当然不可能**。

但这本身就是风险投资和科技演进在过去五十年里一直遵循的法则。十个创业项目里，可能有八九个会倒下，但跑出来的那个超级赢家所创造的价值，足以抹平成本并重塑世界。

回想当年的互联网泡沫，无数投机的 Dot-Com 公司灰飞烟灭，但这丝毫没有阻碍互联网彻底改变人类社会，而像 Amazon 和 Google 这样拥有真实商业闭环的企业最终脱颖而出。今天的 AI 也是一模一样的逻辑。全行业对于计算潜力的长期需求是无比真实且跨越所有行业的，这就是为什么我们对长期的基础设施投资保持坚定不移的战略信心。

<details>
<summary>Original English</summary>

**Matt Garman**: Will every single billion-dollar AI startup succeed? Absolutely not. But that is the fundamental nature of technology investing, and it has been true for the last fifty years. You make ten bets, nine may underperform or fail, but the one generational breakout generates enough enterprise value to power the entire ecosystem forward.

Remember the dot-com bust: thousands of companies went under, but the internet didn't disappear. Companies with durable underlying business models, like Amazon and Google, thrived and redefined the global economy. AI is undergoing the exact same maturation curve. The secular demand across enterprise segments, government, and native AI builders is unprecedented, which gives us immense confidence in our capital deployment roadmap.

</details>

### 打破物理枷锁：电网、核能与供应链极限

**主持人**: 当资本支出的单笔支票从几十亿美元飙升到五百亿甚至上千亿美元时，你们的底层规划与供应链流程发生了哪些翻天覆地的变化？

<details>
<summary>Original English</summary>

**Host**: When you're cutting checks for $20 billion or $50 billion at a time rather than single-digit billions, how has the planning process and execution machinery had to change internally?

</details>

**Matt Garman**: 整个规划流程已经被彻底重塑了。回想十五年前，如果 AWS 在某个区域需要扩展电力，我们只需要给当地电力公司打个电话：“请为我们的机房追加几十兆瓦（MW）电力。”几十兆瓦在当时不算什么大事，电力公司很轻松就能调度并并网。

而到了今天，**我们必须亲自下场解决能源供给问题**。我们必须直接投资、资助并开发大型电力项目和可再生能源基础设施。在过去十年中，亚马逊是全球最大的企业级可再生能源买家之一。我们不仅在源源不断地并网大型太阳能和风能项目，还在积极投资新型**先进核能（Nuclear Energy）项目**。无论是在电表前（并网结算）还是在电表后（直接专线供电），我们都在全方位布局。现在我们必须提前规划未来十到二十年的电力供应、输电走廊以及土地资产，这种规划周期在过去是不可想象的。

<details>
<summary>Original English</summary>

**Matt Garman**: It has completely transformed. Fifteen years ago, if we needed more power for a data center cluster, we called the local utility and asked for an additional 10 or 20 megawatts. That wasn't a massive lift for the grid, and they could provision it relatively easily.

Today, we have to originate our own energy. We are directly financing, co-developing, and contracting massive renewable energy and advanced power projects. Amazon has been the world's largest corporate buyer of renewable energy for years. We are deploying massive utility-scale solar projects, wind installations, and exploring advanced nuclear energy initiatives. We do behind-the-meter projects, direct grid interconnects, and complex transmission planning looking out 10 to 20 years into the future. That is an entirely different operational discipline than anything we had to do a decade ago.

</details>

**主持人**: 你觉得在 2027 到 2028 年这个时间窗口，整个行业最大的硬约束会出现在哪里？哪里的瓶颈能够得到缓解？

<details>
<summary>Original English</summary>

**Host**: Looking out to the 2027-2028 horizon, where do you anticipate the most severe bottleneck constraints will be, and where will constraints begin to ease?

</details>

**Matt Garman**: 我在大学时读过高德拉特（Eliyahu Goldratt）写的经典管理学著作《目标》（*The Goal*）。书中阐明了一个核心法则：**在一个复杂的系统流程中，永远不可能存在“唯一的终极约束”，系统永远只有一个“当前处于主导地位的瓶颈约束”**。一旦你倾尽全力打破了这一个瓶颈，下一个瓶颈就会立即浮现。

算力基础设施也是完全相同的规律。今天所有人都在问：“电力够不够？”如果电力瓶颈在某个地区被解决了，紧接着可能就是 **台积电（TSMC）的晶圆制造与 CoWoS 封装产能**；封装搞定了，瓶颈可能立刻转移到 **HBM 高带宽内存**；内存跟上了，制约可能又变成了高速光纤连接器或网络交换机。

甚至在地理空间上，供应链也是不均衡的——可能印尼拥有充沛的富余电力，但德国的电网极度紧张。你必须统筹规划把哪种类型的算力部署在世界的哪个角落。

为了应对这一切，我们在十多年前就建立了一支顶尖的供应链深度管理团队。我们不仅追踪数以万计的整机柜服务器，更直接穿透供应链多达 **4 到 5 个层级（Tier 4/Tier 5）**，去跟踪每一个关键元器件的原材料与生产动态。大家应该还记得十多年前泰国特大洪水导致全球机械硬盘（HDD）断供的行业危机吧？正是经历过那样的冲击，我们深刻认识到，唯有在地理分布、制造基地以及全链条元器件上建立极致的多源化冗余，才能抵御不断变换的供给约束。

<details>
<summary>Original English</summary>

**Matt Garman**: Back in college, I read the classic manufacturing book *The Goal* by Eliyahu Goldratt. The central premise is that there is never a single, static bottleneck in an industrial system—there is simply whatever constraint happens to be active at that specific moment. As soon as you relieve one bottleneck, another inevitably takes its place.

That is exactly how modern compute infrastructure works. Every month the question is: "Is power the bottleneck?" If you solve power in a specific geography, the constraint shifts to TSMC advanced packaging capacity. Solve packaging, and it becomes HBM supply. Solve HBM, and it shifts to optical transceivers or high-speed network backplanes.

Moreover, supply is geographically fragmented: you might have massive power headroom in Indonesia, but severe grid constraints in Germany. Because workloads have varying degrees of fungibility, you have to match physical infrastructure with workload characteristics. We track hundreds of thousands of components down to Tier 4 and Tier 5 suppliers. People remember the Thailand floods over a decade ago that wiped out global hard drive manufacturing—that crisis taught us that you must actively manage supply chains deep into raw material layers across diversified global geographies.

</details>

### 数据中心与社区治理：不仅是消耗者，更是繁荣推动者

**主持人**: 随着数据中心在全球范围内的疯狂扩张，公众对数据中心的能耗和水耗产生了广泛的社会讨论。坦率地说，科技行业在向普通大众解释“为什么数据中心对国家和地方经济是巨大的利好”方面，做得并不算好。安迪·贾西（Andy Jassy）的管理团队内部是如何看待这个社会舆论问题的？

<details>
<summary>Original English</summary>

**Host**: There is a broader societal debate emerging around data centers. As an industry, tech has done a mediocre job articulating why data centers are actually beneficial for local communities and the broader economy. How are you and Andy Jassy's leadership team addressing that conversation?

</details>

**Matt Garman**: 我完全同意你的判断，科技行业确实需要在这个问题上更加坦诚、透明，并且主动发声。

事实上，我们在所入驻的社区做了大量深具建设性的工作，但我们过去习惯于埋头苦干，没有向外界宣传清楚。首先在水资源方面，AWS 的绝大部分现代数据中心主要采用**直接蒸发或自然空气冷却技术（Free Air Cooling）**，水消耗极低，并且我们制定了明确的“水资源正效益”（Water Positive）战略，向当地社区回馈清洁水资源。

其次，我们在地方税收和高薪就业岗位上的贡献是巨大的。我最近看到一份针对我们某个数据中心所在县区的独立财务报告：**由于 AWS 在当地缴纳的巨额商业财产税，该县区内的每一位普通居民，每年缴纳的个人房产税直接减少了 5000 美元**！然而，当地居民根本不知道这件事，因为我们从未公开做过宣传。如果你走进一个社区告诉大家：“因为这座数据中心的存在，你们每家每户每年可以少交 5000 美元税金，同时你们能享受 Netflix、智能手机服务并拥有更好的公立学校”，大家对那座建筑物的看法就会完全不同。

当然，行业内也确实存在一些不够规范的参与者，他们只图建设速度而忽视环境监管与社区沟通，导致整个数据中心行业被污名化。因此我们必须更加透明地展现模范运营者的标准，向公众证明技术基础设施能够与地方繁荣和谐共生。

<details>
<summary>Original English</summary>

**Matt Garman**: I completely agree with that critique. We need to be vastly more vocal and transparent, because we do an enormous amount of positive work in the communities where we operate, but we simply haven't told the story well.

Take water: our modern data centers utilize direct evaporative free-air cooling for the majority of the year, consuming minimal water, and we have committed to being water-positive. On the economic front, data centers generate high-paying jobs and massive commercial tax bases. I recently reviewed an economic impact study of one of the counties where we operate: because of the commercial tax revenue AWS contributes, every single resident in that county pays roughly $5,000 less in local taxes every single year!

Yet the average resident has no idea. If you knock on someone's door and explain: "By the way, because that facility is there, your tax burden is $5,000 lower, local schools are better funded, and your digital services run reliably," their perception changes entirely. There have certainly been irresponsible operators in the industry who disregard local regulations and build recklessly, giving data centers a bad reputation. We need to separate the good civic actors from the poor ones and clearly articulate the tangible benefits we bring.

</details>

### 自研芯片的十年复利：Nitro、Graviton与Trainium的底层演进

**主持人**: 在聊完物理设施之后，我们必须谈谈你们最硬核的自研硬件布局。很多人可能忘了，AWS 是最早下场自研定制芯片的云厂商。从最初颠覆虚拟化架构的 **Nitro**，到如今大放异彩的 **Graviton** CPU，再到面向 AI 的 **Trainium**。你们当初为什么决定走自主研发芯片这条道路？这一战略如今取得了怎样的成效？

<details>
<summary>Original English</summary>

**Host**: Before we move away from hardware, we have to talk about Trainium and AWS's long history of custom silicon design. You pioneered custom virtualization hardware with Nitro, Graviton has become a massive server CPU success story, and now you have Trainium. What drove the initial decision to build your own silicon, and where does that effort stand today?

</details>

**Matt Garman**: 这可以说是 AWS 发展史上最经典的一个技术创新范式：**从最痛苦的客户痛点出发，通过持续迭代逐步打破工程不可能**。

回到大约 13、14 年前，当时整个行业在运行云服务器时，CPU 算力中有相当大的一部分比例被传统软件虚拟化（Hypervisor）、网络包转发和存储 I/O 处理无情吞噬掉了。客户不断向我们抱怨：“我们需要裸金属（Bare-metal）级别的纯粹性能，我们买了一台机器，希望所有的 CPU 核心都能用来跑我们自己的代码，而不是被你们云平台的管理系统吃掉一大块。”

为了解决这个问题，我们最开始设计了一张专用的网络卸载加速卡（Offload Card），把所有的网络虚拟化开销从主 CPU 剥离出去。这让虚拟机的网络吞吐瞬间逼近了裸金属性能。初战告捷后我们非常兴奋，紧接着想：“能不能把复杂的存储虚拟化也从主 CPU 剥离到硬件卡上？”

但当时通用的网络芯片根本无法胜任这项任务。后来我们在以色列找到了一家富有极客精神的初创公司，他们的板卡上搭载了定制的 **ARM 处理器核心**。我们问他们：“能不能用你们的架构来实现硬件级的存储虚拟化？”他们说：“或许可以试试。”经过多轮联合研发攻关，我们被这支团队卓越的创新力和解决问题的执行力深深折服，这家公司就是 **Annapurna Labs**。我们最终在 2015 年果断将其收购。

<details>
<summary>Original English</summary>

**Matt Garman**: It is one of the proudest engineering chapters at AWS, and a prime example of how we invent on behalf of customers. If you go back roughly 13 or 14 years ago, virtualization overhead was consuming a substantial portion of host server CPU and memory resources. Customers kept telling us: "We want raw, bare-metal performance. When we rent an instance, we want 100% of the silicon power dedicated to our application, not eaten up by your hypervisor."

We started by building custom network offload cards to strip network virtualization out of the main host CPU. That brought networking performance remarkably close to bare-metal. We were thrilled by the results, so the immediate next question was: "Can we offload storage virtualization as well?"

Standard network ASICs couldn't handle that level of complexity. We eventually found an extraordinary team designing boards with embedded ARM cores for adjacent use cases. We approached them and asked if we could repurpose their architecture for storage virtualization. They said, "Maybe." We iterated closely together, fell in love with their mission-driven culture, and acquired them—that was the Annapurna Labs team.

</details>

**Matt Garman**: 收购 Annapurna Labs 之后，我们联手打造了彻底改变云计算底层的 **AWS Nitro 系统**。我们把所有的网络虚拟化、存储虚拟化、系统管理以及底层安全监控，全部抽离到了独立的专用 Nitro 硬件板卡上。主服务器的主板上不再运行任何 AWS 的虚拟化管理软件，它变成了一台 100% 算力归属于客户的纯粹裸金属服务器。

这不仅带来了性能和资源利用率的飞跃，更带来了革命性的**硬件级安全隔离**——我们可以在架构上向全球客户郑重保证：**即使是 AWS 内部拥有最高权限的系统管理员，在物理硬件上也绝对无法访问客户在主 CPU 上运行的任何内存与数据**。这一突破让我们在云计算基础设施领域遥遥领先了整个行业近十年。

随后我们观察到，随着 ARM 核心主频与能效比的不断提升，ARM 架构在通用服务器市场的能耗效率曲线，即将在某一时刻与传统 x86 发生决定性的交汇。我们在 Nitro 硬件卡上积累了海量的 ARM 开发经验，于是我们自问：“为什么不直接造一款属于我们自己的 ARM 服务器 CPU 呢？”这就是 **Graviton** 的诞生。

今天，Graviton 已经迭代到了第四代，取得了空前的成功。在我们的服务器采购结构中，**每年部署的 Graviton 芯片数量，已经远远超过了任何其他单一 CPU 架构**。它稳定提供比同代 x86 芯片**便宜 20%、性能强 20%** 的压倒性性价比。在 AWS 全球排名前 100 的超级大客户中，**超过 90% 的企业已经在核心生产线上大规模采用 Graviton**。许多客户将底层微服务全量迁移到 Graviton 后，服务器实例数量直接缩减了一半，而吞吐量反而大幅飙升。

<details>
<summary>Original English</summary>

**Matt Garman**: With Annapurna, we engineered the AWS Nitro architecture. We built dedicated PCIe offload cards that absorbed 100% of the networking, storage, management, and security hypervisor overhead. The host server effectively became an unencumbered bare-metal machine governed entirely by Nitro APIs.

This delivered massive performance and utilization gains, but more importantly, it established an unprecedented hardware security boundary. We can mathematically prove to customers that no AWS operator or system software can peek into their workloads running on the host CPU. That architectural leap put us years ahead of the industry.

From there, we looked at the performance-per-watt curves of ARM cores and recognized that ARM was on a trajectory to surpass traditional x86 server economics. Because we had mastered ARM silicon in our Nitro cards, we asked: "What if we built an entire server CPU?" That led to Graviton. Today, we ship more Graviton processors every year than any other CPU type. It consistently delivers 20% better performance at 20% lower cost. Over 90% of our top 100 customers run Graviton in production today, with many cutting their physical server footprint in half simply by recompiling for Graviton.

</details>

**Matt Garman**: 早在五六年前，我们就敏锐地意识到 AI 专用计算时代的降临。我们当时就坚信，未来的模型训练与推理不可能永远被通用的图形显示芯片所垄断。于是我们启动了自研 AI 芯片的征程。

如今，我们的专研 AI 芯片已经迭代到了第三代 **Trainium 2**，并且已经正式公布了 **Trainium 3 和 Trainium 4** 的演进蓝图。目前市场的反馈非常火爆，**Trainium 2 的所有可用产能已经被客户预订一空，排期已经一路排到了明年年底**。

这里还有一个非常有趣的命名小插曲：我们内部经常自嘲在产品命名上缺乏天分。最早我们为模型推理设计了名为 **Inferentia** 的芯片，为模型训练设计了 **Trainium**。但随着前沿基础模型体量呈现指数级暴涨，当你在生产线上对千亿参数模型执行推理时，需要的是极其庞大的互联带宽与显存池——结果我们惊讶地发现，**Trainium 凭借其独特的内存架构与超高带宽互联，竟然成为了当今市场上综合性能最强、成本效益最极致的顶级推理芯片**！

今天，Amazon Bedrock 上承载的绝大多数生产级推理流量，底层全部稳定运行在 Trainium 芯片之上。同时在训练端，像 Anthropic 这样的顶尖实验室，以及十多家头部 AI 初创企业，正在利用由数万颗 Trainium 组成的大型超算集群进行下一代前沿模型的预训练与后训练。

<details>
<summary>Original English</summary>

**Matt Garman**: Five or six years ago, we recognized that machine learning would fundamentally reshape computing architectures. We launched our custom AI silicon roadmap, and today we are rolling out Trainium 2, with Trainium 3 and 4 already on our public roadmap. The customer demand is extraordinary—our Trainium capacity is effectively sold out through the end of next year.

There's actually a humorous self-critique here: AWS is historically terrible at product naming! Initially, we designated Inferentia for inference and Trainium for training. But as frontier models scaled into massive multi-parameter architectures, inference suddenly required massive memory bandwidth and inter-chip interconnects. It turned out that Trainium is actually the single best, most cost-effective inference chip on the market today!

A vast portion of the inference traffic running on Amazon Bedrock today is powered directly by Trainium under the hood. At the same time, top-tier labs like Anthropic, alongside dozens of pioneering AI startups, are building massive training clusters on Trainium. Customers see our silicon roadmap and recognize that custom silicon is essential to the future of their infrastructure economics.

</details>

### 企业落地实录：告别工作流复制，拥抱白纸创新

**主持人**: 让我们把话题重新切回到企业端。从中大型企业的视角来看，他们目前在 AI Agent 落地上的真实进展究竟如何？他们已经获得了哪些切实的商业收益？下一步的演进路线图是什么？

<details>
<summary>Original English</summary>

**Host**: Let's pivot back to the enterprise adoption side. Looking at mid-market and Global 2000 enterprises, what is the reality of their agent deployments today? What real business value are they unlocking, and what does the implementation roadmap look like from your vantage point?

</details>

**Matt Garman**: 这是一个非常务实且关键的问题。今天绝大多数企业客户在与我们交流时都表示，他们从早期的 AI 探索中已经获得了非常可观的价值。但坦率地讲，**目前绝大多数企业内部构建的 Agent，依然处于相对初级、规则明确且高度依赖“人在回路”（Human-in-the-Loop）的辅助阶段**，远谈不上完全自主。

目前阻碍企业实现全面 Agent 化的核心障碍，主要有两个：

**第一，是思维方式上的根本误区。**
许多企业在刚接触 Agent 时，最直观的反应是：“太棒了，我们公司现有一套标准作业流程（SOP），张三平时是按照第 1、2、3、4、5 步来操作的；那我们就写一个 Agent，让它也机械地照搬第 1、2、3、4、5 步，最后由张三在后台点个确认按钮。”

我们极力劝阻客户采取这种思路！我们建议他们退后一步，从全新的视角重新审视业务目标：**如果你的终极目的是达成某项业务成果，由一个具备超强算力的 Agent 来执行，它为什么非要模仿人类线性的操作路径？** 

Agent 拥有强大的高并发探索能力。它可以瞬间并发尝试 50 种完全不同的求解路径，在毫秒级内完成交叉验证与数据回溯，然后以一种人类完全无法比拟的全新范式达成目标。**计算机解决问题的最优解，与人类受制于生物极限所采取的解决方式，是有着天壤之别的**。企业真正的核心价值，绝非在于把昨日的人工流程做数字化克隆，而在于采取一种“白纸化（Greenfield）”的全新视角，重构业务逻辑。

<details>
<summary>Original English</summary>

**Matt Garman**: Today, enterprise customers are extracting undeniable value from AI, but the vast majority of agent deployments are relatively straightforward, deterministic workflows that still keep a human firmly in the loop.

Two primary bottlenecks are holding enterprises back from unlocking fully autonomous scale. The first is a fundamental mental model trap. When enterprises first look at agentic workflows, their instinct is: "Great! Bob does steps 1, 2, 3, 4, and 5 today. Let's build an agent that mirrors steps 1, 2, 3, 4, and 5, and then Bob can review the final output."

We strongly urge customers to take a step back. Don't simply replicate existing human steps. If the goal is achieving an end-state outcome, an agent can approach the problem completely differently. An agent can operate in an massively parallelized fashion—it can test 50 distinct paths simultaneously, analyze the probabilities, and synthesize the result in seconds. How a distributed computer solves an optimization problem is radically different from how a human navigates a manual process. The massive enterprise unlock comes from a greenfield rethinking of business processes, not incremental automation of legacy human chores.

</details>

**Matt Garman**: **第二，是关于自主系统的信任、授权与安全防线。**
企业管理者目前最大的顾虑是：“如果我把业务全权交给 Agent，我怎么敢确信它不会在半夜失控，一键误删了生产数据库，或者向客户发送了错误的合同条款？”这种对系统失控的未知恐惧，是让许多大型机构在真正放权给 Agent 时裹足不前的核心根源。

因此，我们投入了巨大的资源，去构建一套能够让企业充满安全感的保障机制：包括强制执行的业务规则护栏（Guardrails）、严密的执行沙箱隔离、细粒度的瞬态数据访问权限控制。只有当底层的基础设施能够数学化地证明“Agent 绝对无法越权行事，也不会产生破坏性连锁反应”时，企业才敢放心地将其投入全自动的生产流水线。

<details>
<summary>Original English</summary>

**Matt Garman**: The second blocker is trust and governance. Enterprises hesitate to move toward fully autonomous agents because of legitimate anxiety: "How can I trust that this agent won't hallucinate, take an unapproved action, expose proprietary customer data, or accidentally delete a production database?" That apprehension is completely understandable.

That's why we spend immense engineering time building the enterprise guardrails, sandbox environments, and granular permission boundaries necessary to guarantee safety. Enterprises must feel total confidence that the blast radius of an autonomous agent is strictly contained. Until infrastructure can provably ensure that an agent cannot make a catastrophic error, organizations will hesitate to remove humans from the critical path.

</details>

### 破局评估困境：FTE战术与45天交付机制

**主持人**: 企业在落地 Agent 时，如何建立严密的评估系统（Evals）？如何实现持续的端到端测试闭环？如何对数据进行精准标注以模拟生产环境？目前大多数传统企业似乎根本不具备这些前沿的工程能力。

<details>
<summary>Original English</summary>

**Host**: How are enterprises navigating evaluations (evals) and continuous testing? How do they construct synthetic datasets, build ground-truth labels, and detect model drift in production? Almost no traditional enterprise today knows how to solve these problems natively.

</details>

**Matt Garman**: 你说得太切中要害了！坦率地说，在当今世界上，能够真正把复杂 Agent 评估系统和回测体系搭建得尽善尽美的团队，凤毛麟角。这正是目前全球企业客户向我们求助最多的领域。

为此，我们组建并重仓投入了大规模的 **FTE（前线部署工程师 / Forward-Deployed Engineering）** 专家团队。但我们推行 FTE 的哲学，与传统管理咨询公司有着本质区别：我们绝不想做那种靠堆砌人力、让顾问在客户机房里常驻数年、不断按人天收费的传统外包业务。

我们的核心目标是**“授人以渔”**：当我们的 FTE 专家团队进驻一家准备就绪的客户企业时，我们的考核指标是在 **45 天内**，帮助客户搭建起完整的评估基准框架，梳理数据标注流程，跑通自动回归测试闭环。在第 45 天离开时，客户内部的技术团队必须已经接受过完整培训，能够完全依靠自身力量独立运行这一套现代化 AI 工程底座。企业不想在接下来的五年里永远依赖外部顾问，他们需要把 AI 的核心控制权牢牢握在自己手中。

<details>
<summary>Original English</summary>

**Matt Garman**: You hit on the exact pain point. Frankly, very few teams globally have mastered evaluations, continuous testing loops, and drift mitigation for agentic architectures. This is by far the number-one area where enterprise customers ask for our direct hands-on assistance.

To solve this, we've invested heavily in our Forward-Deployed Engineering (FTE) teams. But our operational philosophy is strictly anti-consulting. We have zero interest in building a legacy, human-services business where dozens of consultants camp out at an enterprise for five years billing hours.

Our mandate for FTE teams is simple: embed alongside the customer, build their evaluation framework, structure their data labeling pipelines, establish automated regression harnesses, and train their internal team to be completely self-sufficient within 45 days. When our engineers roll off, the customer owns the capabilities end-to-end. Enterprises have made it clear that they do not want to be beholden to expensive external labor for the next decade; they want internal mastery.

</details>

### 数据主权保卫战：Amazon Bedrock与开源微调路线

**主持人**: 行业里目前有两派鲜明的观点：一派认为应该把所有业务数据直接接入 OpenAI 或 Anthropic 的最强通用前沿模型；而另一派则坚信，企业决不能把核心数据交给封闭模型厂商，真正明智的做法是在企业私有环境里采用开源权重模型（如 Llama 等），结合私有专有数据进行深度后训练（Post-training）和微调。你怎么看这两条路线的博弈？

<details>
<summary>Original English</summary>

**Host**: There's a major architectural debate raging: one camp argues you should pipe enterprise workflows directly into frontier closed models, while the other argues that proprietary enterprise data must never leave private enclaves, meaning companies should adopt open-weight models and run post-training and fine-tuning on their own infrastructure. How do you view this dichotomy?

</details>

**Matt Garman**: 对于“**数据是企业最神圣的资产**”这一点，我百分之百赞同。

这正是我们从一开始设计 **Amazon Bedrock** 时的最高指导原则。在 Bedrock 的架构下，我们向客户做出军工级的技术承诺：**你的任何企业专有数据、提示词（Prompt）与上下文，绝对不会离开你的专属 VPC**！无论你调用的是顶级的闭源前沿模型还是开源模型，数据永远不会回流给模型供应商用于二次训练，模型厂商甚至根本无法看到你的调用内容。数据在你的可信边界内实现绝对物理隔离。这就是为什么各行各业的大型企业都在将关键工作负载全量迁移到 Bedrock 之上，推动该项业务以令人难以置信的周环比速度爆发式增长。

三年前，当大模型浪潮刚爆发时，外界曾经对我们有一些批评，指责 AWS 在跟进大模型上显得“动作迟缓”。但在底层，我们当时是在极为冷静地打磨真正的安全底座。我们当时就明确表示：**我们绝不会为了赶时髦而仓促推一个玩具级的半成品；我们必须沉下心来，彻底解决企业级数据主权、模型隔离以及超高持久性架构这些最硬核的底座问题**。今天事实证明，当客户从概念验证（PoC）阶段迈向严肃的生产落地时，绝大多数企业最终都毫不犹豫地选择回流到 AWS Bedrock。

<details>
<summary>Original English</summary>

**Matt Garman**: On the fundamental principle that data is an enterprise's most precious asset, I agree completely. That foundational conviction is precisely why we architected Amazon Bedrock the way we did.

We guarantee that your data never leaves your VPC. When you invoke a foundation model inside Bedrock, your prompts, context, and completions are never piped back to the model provider, never stored externally, and never used to train third-party models. Your data remains strictly within your enterprise perimeter. That absolute data sovereign guarantee is why enterprises are flocking to Bedrock and why that business is exploding week over week.

Three years ago, AWS took some public heat. People claimed we were late to the generative AI party. But we intentionally refused to rush an unvetted, fragile API wrapper out the door. We said: "We are going to build the robust enterprise foundation first. We are going to ensure bulletproof data isolation, SOC compliance, enterprise governance, and scalable resilience." Now that the industry has graduated from toy demos to enterprise production, that deliberate engineering discipline is paying off massively.

</details>

**Matt Garman**: 与此同时，对于开源权重模型（Open-weight Models）的微调与部署路线，我们也给予了同等量级的全力支持。

今天许多企业手握极具价值的垂直领域专有数据。当他们把这些数据深度融入高质量的开源权重模型，并在其上执行专业的后训练与对齐时，他们完全能够以比调用超大闭源模型**更低的推理成本、更快的响应速度，获得在特定垂直领域更出色的任务表现**。

如今，全球大量前沿的模型训练与后训练工作，实际上全都运行在 AWS 的 **Amazon SageMaker** 平台之上。SageMaker 在生成式 AI 时代迎来了第二次技术新生，成为了企业打造专属定制大模型的首选工场。我们为客户提供极致的自由选择权：无论你是想一键调用顶级的闭源前沿模型，还是想在 SageMaker 上自主精调开源模型，AWS 都能提供全行业最强大的算力集群与安全编排底座。

<details>
<summary>Original English</summary>

**Matt Garman**: At the same time, we fully embrace the open-weight paradigm. Many enterprises possess deep, differentiated domain data. By taking open-weight models, mixing in proprietary corpora, and executing custom post-training and parameter-efficient fine-tuning (PEFT), they can achieve superior performance on their specific workflows at a fraction of the operating cost and inference latency of a frontier model.

Customers are leveraging Amazon SageMaker at massive scale to execute that exact strategy. SageMaker has experienced an incredible resurgence as the definitive platform for model fine-tuning and specialized inference hosting. We provide customers total optionality: whether you want to orchestrate multi-agent chains with leading frontier models on Bedrock or train tailored, sovereign open-weight models on SageMaker, AWS delivers the highest-performance, most secure substrate.

</details>

### 机器速度的安全防线：AWS Continuum与内部组织重构

**主持人**: 伴随着自主 Agent 的普及，行业内关于模型利用漏洞被攻击、Prompt 注入以及代码供应链投毒的担忧与日俱增。面对这些新型安全威胁，大企业 CEO 们普遍在担心什么？AWS 又是如何应对的？

<details>
<summary>Original English</summary>

**Host**: With autonomous agents proliferating, there is widespread anxiety over security vulnerabilities, prompt injections, and novel attack surfaces. What are enterprise CEOs asking you about these systemic risks, and how are you defending against them?

</details>

**Matt Garman**: 企业高管们的核心忧虑归结为一点：**当我授权 Agent 能够自主执行操作时，我该如何确保它不被恶意操纵？**

除了我们在 IAM 权限和沙箱层建立的确定性防御外，我们在安全理念上迎来了一个根本性转变：**未来的网络安全防御，必须以“机器的速度”来运行，而不能再停留在“人类的速度”**。

在过去，安全团队的运作依赖于人类分析师查看告警看板，然后开会研判对策。但面对能够在一瞬间以高并发发起攻击的自动化 AI 威胁，等人类做出反应，数据库可能早已被渗透。因此我们最近推出了一款名为 **Continuum** 的前沿安全服务。

Continuum 利用强大的顶尖 AI 模型，实时全天候扫描并理解客户复杂的全栈云环境，自主挖掘那些传统规则引擎根本无法探测到的深层安全隐患。更重要的是，它拥有客户环境的全局上下文语义，能够极其精准地评估出哪些漏洞在当前架构和补偿性控制下具有最高的实际危害，从而自动对漏洞进行防御优先级排序并在毫秒级实施自动化阻断拦截。这种“以机器对抗机器”的主动安全体系，正在成为企业防御体系的基石。

<details>
<summary>Original English</summary>

**Matt Garman**: The core question CEOs ask is: "When I empower an agent to act, how do I know it won't be coerced or manipulated into harmful behavior?"

Beyond strict sandboxes and dynamic permissions, the fundamental insight is that enterprise security must now operate at the speed of machines, not the speed of humans. In the traditional paradigm, an alert triggers, an engineer logs in, evaluates the ticket, and takes remedial action. When an automated agentic exploit executes in milliseconds, human response times are useless.

That is why we launched our new security service, AWS Continuum. Continuum utilizes cutting-edge foundation models to continuously inspect a customer's entire AWS topology, discovering complex, multi-hop vulnerabilities that traditional static scanners miss entirely. Because Continuum deeply understands environmental context—how IAM roles interact, where network perimeters sit, and what compensating controls exist—it prioritizes real risks and initiates proactive defenses at machine speed.

</details>

**主持人**: 在 AWS 内部，你们自己是如何使用 AI Agent 的？你们的内部组织架构又因此发生了哪些剧烈变化？

<details>
<summary>Original English</summary>

**Host**: How is AWS itself utilizing agents internally? How is this transforming your own software engineering processes and broader organizational design?

</details>

**Matt Garman**: 我们在亚马逊全员范围内深度推广了智能助手与 Agent 技术。从软件工程、安全审计到日常职能部门，Agent 已经渗透到了业务的每一个毛细血管。

举个非常具体的例子：我们全员部署了 **Amazon Q**。现在我们的人力资源团队和财务团队都在自主构建业务 Agent。过去为了对全球各业务线的税法合规性和预算配额进行多维度交叉核算，往往需要整个财务分析师团队耗费几个星期；而现在，一名财务人员指挥着定制的 Agent，在几个小时内就能完成全套复杂的合规检索与跨系统对账。业务人员不再被传统软件开发的排期所阻塞，他们能够直接调用 Agent 工具快速释放生产力。

但在所有业务板块中，**受到最剧烈冲击、也是生产力提升最夸张的领域，是软件开发本身**。

我们在内部成立了专门的**“前沿工程团队（Frontier Teams）”**。在这些团队里，我们不再推行传统的“代码补全”模式，而是全面转向了**“Agent-First（智能体优先）”**的全新开发范式。在这些团队中，所有的基础代码、测试用例和部署脚本，100% 全部由 Agent 协同编写；人类工程师的角色从“代码敲击者”彻底转变成了“架构指挥官与 Agent 团队管理者”。

这也带来了组织架构层面的剧烈重构：过去在产品研发体系中，要长期维护一个核心复杂功能模块，通常需要一个由 10 名资深全栈工程师组成的紧密团队；而今天在 Agent 的赋能下，**一个仅由 3 到 4 个人组成的敏捷小单元（Pod），就能以十倍于以往的惊人速度完成新特性的研发与上线**。这使得我们能够将极其精干的人才团队在不同的前沿挑战之间极速调度，保持小团队极致的敏捷与创新爆发力。

<details>
<summary>Original English</summary>

**Matt Garman**: We have deployed Amazon Q across all of Amazon, and agents are actively reshaping every functional domain—from finance and HR to compliance and core software delivery. Our HR and finance teams regularly construct autonomous agents to resolve complex, cross-jurisdictional tax compliance problems and headcount modeling tasks that previously required a dedicated team working for three weeks. Today, a single operator orchestrates an agent to resolve it in a couple of hours.

However, the single biggest, most disruptive productivity leap has been in software development. We established internal "Frontier Teams" operating on an uncompromising "Agent-First" paradigm. This is not simple autocomplete; the agents write 100% of the raw code, generate unit tests, and provision environments. The human engineers act purely as system architects and agent managers.

This is radically altering our organizational structure. Historically, delivering a complex, long-lifecycle product capability required a dedicated engineering pod of perhaps 10 developers. Today, a tight pod of 3 to 4 engineers, augmented by autonomous agentic swarms, can ship capabilities faster and with higher fidelity than a 10-person team ever could. This allows us to maintain the nimbleness of an early-stage startup even within an organization of AWS's unprecedented global scale.

</details>

### 尾声

**主持人**: 这真是一场信息量拉满且极具前瞻性的深度对谈。我们正处于技术史上一段令人敬畏的黄金时代。非常感谢你今天抽出宝贵时间做客节目，向我们分享了如此多深刻的底层工程洞察与商业思考。

<details>
<summary>Original English</summary>

**Host**: This has been an extraordinarily illuminating conversation. We are undeniably living through a golden era of technological transformation. Thank you so much for your time, your transparency, and your incredible insights today, Matt.

</details>

**Matt Garman**: 非常感谢你的邀请。我们非常珍视行业里所有的初创企业与开发者客户，陪伴他们成长并向他们学习是 AWS 最美妙的体验。再次感谢你，非常期待下次再来交流！

<details>
<summary>Original English</summary>

**Matt Garman**: Thanks for having me on. We are thrilled to partner with builders and startups everywhere and learn alongside them every single day. I truly appreciate the conversation.

</details>

**主持人**: 精彩绝伦，非常感谢大家收看，我们下期节目再见！

<details>
<summary>Original English</summary>

**Host**: Wonderful. Thank you so much, everyone. See you next time!

</details>