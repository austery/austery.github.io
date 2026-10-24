---
author: a16z
date: '2026-08-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Zx1Ec8LWFeM
speaker: a16z
tags:
  - ai-infrastructure
  - compute-capacity
  - data-centers
  - energy-transition
  - venture-capital
title: a16z 推出机器时代基金：从芯片、能源到铜矿，全栈重构 AI 物理与算力基础设施
summary: Andreessen Horowitz（a16z）正式推出机器时代基金（Machine Age Fund），专注投资支撑 AI 革命的算力底层与物理基础设施。Ben Horowitz、Martin Casado 与 Raghu Raghuram 深入探讨了从专用芯片、先进封装、内存与光互连，到吉瓦级数据中心、电力能源、液冷散热乃至铜矿资源的全栈重构机遇，并分析了软硬件一体化系统公司对抗巨头的破局之道与初创生态。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Andreessen Horowitz
products_models:
  - Machine Age Fund
media_books: []
status: evergreen
---
### 机器时代基金的诞生背景

**本·霍洛维茨 (Ben Horowitz)**: 我们迎来了一项全新的技术，这是有史以来最重要的一项技术。而你为此需要一套全新的**基础设施**。

<details>
<summary>Original English</summary>

**Ben Horowitz**: We have a whole new technology. That's the most important technology ever. And you need a whole new infrastructure.

</details>

**马丁·卡萨多 (Martin Casado)**: 通常当我们谈论基础设施领域时，我们谈论的是服务器、存储和网络。但这一次，它一路延伸到了铜矿的开采。这就是这场变革将波及的广度。

<details>
<summary>Original English</summary>

**Martin Casado**: Normally when we talk about the infrastructure world, we're talking about the servers on the storage and the network. Here it goes all the way down to the mines of copper min. That's how widespread this thing is going to be.

</details>

**主持人**: 过去当你构建某种东西时，它只是一个工程问题。而在这里，感觉它真正变成了一个资源限制问题。因此，无论是否关乎 Token，我们都在向系统中注入大量资金，然后这些系统产生结果。而现在我们的瓶颈在于系统是否有能力真正匹配我们正在投入其中的海量资源。

<details>
<summary>Original English</summary>

**Host**: It used to be when you built something, it was an engineering problem. And here it feels like it really is a resource limitation. So whether it's tokens or not, we're pouring a ton of money into systems and then those systems are producing a result. And right now we're bottlenecked on the systems ability to actually match the resources we're pouring into them.

</details>

**拉古·拉古拉姆 (Raghu Raghuram)**: 行业领先的存储器厂商表示，他们今天面临的需求需要 3 年的产能才能供应得上。

<details>
<summary>Original English</summary>

**Raghu Raghuram**: The leading memory vendor said the demand they have today will take them 3 years of capacity to supply.

</details>

**主持人**: 如果这只基金达成了我们的预期，我们如何看待 5 到 10 年后的世界？

<details>
<summary>Original English</summary>

**Host**: If this fund does what we think it will do, how do we see the world in 5 to 10 years?

</details>

**本·霍洛维茨 (Ben Horowitz)**: 美国在基础设施竞争中胜出，那将是一件极好的事情。

<details>
<summary>Original English</summary>

**Ben Horowitz**: America wins in the infrastructure and that would be awesome.

</details>

**主持人**: Ben、Martin、Raghu，欢迎各位。

<details>
<summary>Original English</summary>

**Host**: Ben Martin Ragu, welcome.

</details>

**本·霍洛维茨 (Ben Horowitz)**: 谢谢。

<details>
<summary>Original English</summary>

**Ben Horowitz**: Thank you.

</details>

**马丁·卡萨多 (Martin Casado)**: 好的，谢谢。

<details>
<summary>Original English</summary>

**Martin Casado**: All right. Thank you.

</details>

**主持人**: 我想先引用 Marc Andreessen 的一段话来引出这只新基金：“这是我一生中经历的最大技术革命。这显然比互联网还要宏大。与之相提并论的参照物是微处理器、蒸汽机和电力，或者可以说是轮子的发明。” 各位，**机器时代基金（Machine Age Fund）**。请为我们介绍一下它。Ben，请你先开始。

<details>
<summary>Original English</summary>

**Host**: I want to start with a Mark quote to introduce this new fund. This is the biggest technological revolution of my lifetime. This is clearly bigger than the internet. The comps on this are the microprocessor, the steam engine, and electricity, or maybe the wheel. Guys, the machine age fund. Please introduce it. Ben, start us off.

</details>

**本·霍洛维茨 (Ben Horowitz)**: 基本上发生的事情是，我们迎来了一项全新的技术，这是有史以来最重要的一项技术。每当有一种革命性的新方式来使用我们所热爱的所有基础设施事物时，你就需要一套全新的基础设施，而且从来没有任何一次的影响力像这一次这样巨大。因此，我们不仅需要新的芯片、新的系统软件，还需要全新的电力获取与分配方式，我们甚至需要寻找替代铜的方案。我的意思是，这涵盖了绝对的一切。所以这是一个非常令人兴奋的时刻。特别是对于这个新时代的硬件层面，我们需要一种全新的投资与支持方式。

<details>
<summary>Original English</summary>

**Ben Horowitz**: Well, um, basically what's uh happened is we have a whole new technology that's the most important technology ever. And what happens every time um there's a dramatic new way of using all of the things that we love infrastructure um you need a whole new infrastructure and never has it been more high impact as it is on this one. So not only do we need new chips, new system software, we need new ways of doing power, we need to replace copper. I mean like it's absolutely everything. So it's a very exciting time. So you know particularly for the kind of hardware aspects of of this new era um we needed a new approach.

</details>

**马丁·卡萨多 (Martin Casado)**: 是的，我非常赞同。在计算领域，通常当我们谈论基础设施时，谈论的是服务器、存储和网络，其主要受限于我们能编写的软件。如今，这一切真正一路延伸到了物理层，延伸到了变压器、能源电网乃至铜矿。这就是它所涉及的范畴之广。正如 Ben 所说，无论从国家安全、地缘政治角度，还是从我们构建的软件类型以及对世界的总体影响来看，这都是极为重大的。顺便说一句，如果退一步看全球 GDP，传统计算只占其中的极小一部分——大约 3%。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah I would agree. I mean normally when we at least in the computing when we talk about the infrastructure world, we're talking about the servers and the storage in the network. Here it goes all the way down to the mines, copper mines. That's how widespread this thing is going to be and as Ben said, it's just so massive from both a national security, geopolitical perspective, but also just the type of software we're building and the impact of the world. And by the way, if you take a step back and look at global GDP, computing is a very small part of it. It's like 3%.

</details>

**拉古·拉古拉姆 (Raghu Raghuram)**: 是的，非常低，只有大约 3%。

<details>
<summary>Original English</summary>

**Raghu Raghuram**: Yeah, it's very low. Is very low. Yeah. 3%. Yeah.

</details>

### 宏观条件与技术范式转移

**主持人**: 请解释一下导致这种转变的宏观条件——为什么现在有大量创业者涌入这些领域？他们看到了什么推动了这一切？

<details>
<summary>Original English</summary>

**Host**: And explain some of the macro conditions that have led to this this trans this change in terms of the surplus of founders pursuing these idea. Like what are they seeing that's that's enabled?

</details>

**马丁·卡萨多 (Martin Casado)**: 显而易见的是，对 AI 的需求基本上是无限的。因此，人们正在向其投入大量的资本支出（**CapEx**）。这从根本上拉动了底层的整个物理与工程堆栈。但从技术的历史发展来看，真正有趣的是——在过去 20 年里，我们一直生活在 **冯·诺依曼架构（von Neumann architecture）** 与互联网络的世界中。计算范式基本固定，我们主要是在上面构建各种应用层软件。

现在突然之间，我们正在重新思考计算机体系结构本身——重新思考存储器、重新思考处理器、重新思考互连网络、重新思考物理空间中的数据中心。这种全方位的重构在历史上只发生过一两次。这促使大量极其聪明的工程师进入这个领域并创办公司。

<details>
<summary>Original English</summary>

**Martin Casado**: Well, I mean the obvious is like you know the the demand for AI is basically infinite and as a result, massive CapEx is being poured into it, which is pulling on the entire stack. But from kind of a history of technology perspective, what's so interesting is you know for the last 20 years we've kind of been living in the von Neumann networked world. You know compute is compute and we kind of build all of these abstractions on top of it. Now all of a sudden, we're rethinking computer architecture. We're rethinking memory, we're rethinking processing, we're rethinking interconnect, we're rethinking physical data centers. And this kind of reset has only happened once or twice in the entire history of computing, and it is driving just really, really smart founders into the space to build companies.

</details>

**拉古·拉古拉姆 (Raghu Raghuram)**: 我想补充一点：上一次发生这种规模的基础设施变革，大约是在 20 年前**云计算（Cloud Computing）**兴起的时候。但即便在云计算时代，其底层也是基于现有的组件构建的——普通的 x86 服务器、标准的以太网交换机和传统的存储阵列。

而这一次，正如 Martin 所指出的，工作负载发生了根本性的变化。传统的 CPU 架构在处理大规模张量运算时效率极其低下。你需要一个全新的分布式计算范式，单台计算机的定义已经扩展为由数万颗加速芯片组成的巨型超节点。为了支撑这种算力密度，现有的供电网络、散热系统、机架设计和芯片间互联必须全部推倒重来。

<details>
<summary>Original English</summary>

**Raghu Raghuram**: To add to that, the last time we saw a massive infrastructure wave was maybe 20 years ago with the rise of cloud computing. But even with cloud computing, it was built using existing building blocks: standard x86 servers, standard Ethernet switches, standard storage arrays. This time, the workload is so fundamentally different. The CPU architecture is just not suited for tensor processing at scale. You need a completely new distributed computing paradigm where the "computer" is now the entire cluster of tens of thousands of accelerators. To power that density, existing power grids, cooling, rack designs, and interconnects have to be reinvented from scratch.

</details>

**本·霍洛维茨 (Ben Horowitz)**: 如果你回看软件吞噬世界的历程，过去二十年风险投资的逻辑主要是“轻资产”的纯软件模式。因为硬件和基础设施已经标准化了，你只需要租用 AWS，雇佣几个程序员写代码就能上线产品。但现在，**算力即权力，物理世界重新成为了核心瓶颈**。如果你的底层物理基础设施无法提供足够的能源、散热和互联带宽，你的前沿模型训练和大规模推理就会直接停滞。这也是为什么我们设立这只独立基金的原因——传统的软件风投逻辑已经无法完全覆盖这一波深刻的物理世界重构。

<details>
<summary>Original English</summary>

**Ben Horowitz**: If you look back at "software eating the world," the VC playbook for the last two decades was asset-light pure software. Hardware and infrastructure were commoditized; you just spun up AWS instances and wrote software. But today, compute is power, and the physical world is the bottleneck again. If your physical infrastructure cannot supply the power, cooling, and interconnect bandwidth, your frontier training and inference ground to a halt. That is why we raised this dedicated fund—the old SaaS playbook is not sufficient for this deep physical and systems reconstruction.

</details>

### 从工程问题到资源约束的范式演变

**主持人**: 你们之前提到，过去构建系统主要是解决工程架构上的逻辑问题，而现在它变成了硬性的物理资源限制问题。能否详细谈谈这种“资源受限”的具体表现？

<details>
<summary>Original English</summary>

**Host**: You mentioned earlier that building systems used to be primarily an engineering problem, whereas now it has become a hard physical resource limitation problem. Can you elaborate on how this resource constraint manifests in practice?

</details>

**马丁·卡萨多 (Martin Casado)**: 在过去，如果你想扩展一个互联网服务，比如 Google 搜索或 Facebook，你的瓶颈通常是分布式系统的软件工程优化——如何设计缓存、如何做负载均衡、如何降低数据库锁冲突。服务器本身是充裕且现成的商品。

但今天在 AI 时代，我们面临的是刚性的物理墙：
1. **电力墙（Power Wall）**：单机架功率密度从过去的 10kW 飙升到现在的 100kW 甚至更高，公用电网根本无法在短时间内提供吉瓦级别的增量电力。
2. **内存墙与互联墙（Memory & Interconnect Wall）**：计算核心的算力增长远超内存带宽和通信带宽的增长，数据传输延迟成为了算力利用率的最大杀手。
3. **供应链物理极限**：高带宽内存（HBM）、先进封装（CoWoS）、特种光学器件的产能扩张周期长达数年。

这直接导致了从软件优化向硬核物理创新的转移。

<details>
<summary>Original English</summary>

**Martin Casado**: In the past, if you wanted to scale an internet service like Google Search or Facebook, the bottleneck was distributed systems software engineering—caching, load balancing, database sharding. The servers were commoditized and readily available off the shelf. But today in the AI era, we are hitting hard physical walls: first, the power wall, where rack power density jumps from 10kW to 100kW+, and utilities cannot supply gigawatts on short notice; second, the memory and interconnect wall, where compute growth outpaces communication bandwidth; and third, physical supply chain limits in HBM and advanced packaging. This forces a shift back to deep physical innovation.

</details>

**拉古·拉古拉姆 (Raghu Raghuram)**: 这也深刻改变了客户的采购行为。以前企业购买 IT 设备是按年度预算和折旧周期逐步采购。而现在，顶级前沿实验室和超大规模云厂商（Hyperscalers）是在不惜一切代价锁定未来三到五年的电力配额、芯片产能和机房空间。这种恐慌性的资源争夺战，在整个工业史上都极为罕见。

<details>
<summary>Original English</summary>

**Raghu Raghuram**: This has also completely changed customer procurement behavior. Previously, enterprises bought IT gear according to annual budgets and depreciation cycles. Today, frontier AI labs and hyperscalers are racing to lock in multi-gigawatt power agreements, chip allocations, and data center capacity 3 to 5 years in advance. This panic-driven resource land grab is unprecedented in industrial history.

</details>

### 芯片设计与计算架构的多样化爆发

**主持人**: 既然存在如此巨大的资源约束，目前的芯片格局会如何演变？英伟达处于绝对的主导地位，但新的创业公司和超大规模厂商自研芯片（ASIC）的机会在哪里？

<details>
<summary>Original English</summary>

**Host**: Given these massive resource constraints, how do you see the chip landscape evolving? NVIDIA has a dominant position, but where are the opportunities for new startups and custom hyperscaler ASICs?

</details>

**马丁·卡萨多 (Martin Casado)**: 这是一个经典的市场规律问题。首先，英伟达打造了令人难以置信的生态系统，尤其是 **CUDA** 软件壁垒和全栈系统集成能力。但在万亿美元级别的算力市场中，即使你只占据特定细分领域的 5%，这也足以支撑起一家数百亿美元估值的巨型公司。

更重要的是，AI 工作负载正在发生分化：
* **训练（Training）**与前沿大模型预训练依然极度依赖通用 GPU 和极致的集群互联。
* 但在**推理（Inference）**端，随着模型推理计算（如测试时计算、长思考链）和垂直领域边缘计算的爆发，专用的推理加速芯片、近存计算架构、低功耗微架构展现出巨大的能效比优势。

<details>
<summary>Original English</summary>

**Martin Casado**: This comes down to the laws of markets. NVIDIA has built an incredible moat with CUDA and full-stack system integration. But in a multi-trillion dollar compute market, capturing even 5% of a specialized segment creates a massive standalone company. Furthermore, AI workloads are diverging: frontier training still requires universal GPUs and massive cluster scale, but inference—especially with test-time compute and reasoning agents—has wildly different latency, cost, and power profiles, creating enormous room for custom silicon and near-memory computing.

</details>

**本·霍洛维茨 (Ben Horowitz)**: 我们还看到系统级设计的崛起。今天创办一家芯片公司，仅仅画出优秀的逻辑电路图是远远不够的。你必须是一家**系统公司（Systems Company）**。你需要从最底层的半导体物理、封装工艺、光学互联，一直向上整合到编译器、运行时软件框架以及与数据中心供电水冷的协同。这种全栈工程的复杂度极高，但也构成了极宽的护城河。

<details>
<summary>Original English</summary>

**Ben Horowitz**: We are seeing the rise of the systems company. You cannot just design a neat silicon die anymore; you have to build a full system. You need to co-design from semiconductor physics, advanced packaging, and optical interconnects, all the way up through compilers, runtime software, and data center cooling. The complexity is immense, but so is the defensive moat.

</details>

### 数据中心重构：吉瓦级电力、液冷与光电互连

**主持人**: 让我们回到数据中心的基础设施。到 2028 年，新建数据中心预计将需要 44 吉瓦（GW）的额外电力，而电网预期的增量可能只有 25 吉瓦左右。在座各位如何理解“吉瓦”这个概念及其带来的挑战？

<details>
<summary>Original English</summary>

**Host**: Let's return to data center infrastructure. By 2028, new data centers are projected to require roughly 44 gigawatts of additional power against perhaps 25 gigawatts of expected grid additions. How should we conceptualize a gigawatt and the challenge it presents?

</details>

**马丁·卡萨多 (Martin Casado)**: 人们现在经常随口说“我们要建一个吉瓦级的数据中心”。但你知道 1 吉瓦有多大吗？我在亚利桑那州的弗拉格斯塔夫（Flagstaff）长大，那是一个有 5 万到 6 万人口的城镇。整个城镇的总用电量还不到 1 个吉瓦。换句话说，1 个吉瓦的电力足以点亮并为空调驱动一整座中型城市或 5 万多户家庭！

现在行业正在规划单体容量达到数吉瓦的 AI 超级数据中心园区。这意味着你需要直接在旁边建造专用核电站、大型天然气发电厂或地热发电设施。

<details>
<summary>Original English</summary>

**Martin Casado**: People throw around the word "gigawatt" casually now. But what is a gigawatt? I grew up in Flagstaff, Arizona, a town of 50,000 to 60,000 people. Our entire town ran on less than a gigawatt of power! A single gigawatt can power and air condition an entire city. Now the industry is designing multi-gigawatt AI campuses. That means you literally need dedicated nuclear SMRs, massive natural gas plants, or geothermal facilities co-located on site.

</details>

**拉古·拉古拉姆 (Raghu Raghuram)**: 当电力密度达到每机架 100kW 时，传统的风冷（Air Cooling）在物理上已经彻底失效了。你必须采用全**液冷（Liquid Cooling）**，包括直接芯片冷板冷却（Direct-to-Chip）甚至全浸没式液冷（Immersion Cooling）。

此外，配电系统也正在从传统的低压交流电转向 800V 高压直流配电（HVDC）。传统的机房铜缆互联由于信号衰减和体积过大，正在迅速被**共封装光学（CPO）**和光互联技术替代。数据中心的物理形态正在发生自诞生以来最彻底的重构。

<details>
<summary>Original English</summary>

**Raghu Raghuram**: When rack power density hits 100kW+, traditional air cooling is physically obsolete. You must shift entirely to liquid cooling, whether direct-to-chip or immersion. Furthermore, facility power delivery is transitioning to 800V DC architectures to minimize resistive losses. Copper interconnects are hitting physical distance-bandwidth limits inside clusters, accelerating the transition to co-packaged optics (CPO). The physical data center is undergoing the most radical reconstruction since its inception.

</details>

**本·霍洛维茨 (Ben Horowitz)**: 这就是为什么现在许多算力部署甚至外溢到了美国之外，或者需要深入能源腹地。如果你无法解决能源接入和水冷许可，你拿到再多的 GPU 也只是一堆无法通电的硅片。基础设施的物理瓶颈直接决定了 AI 发展的速度上限。

<details>
<summary>Original English</summary>

**Ben Horowitz**: This is why compute deployments are expanding into unconventional geographies with abundant energy. If you cannot secure power interconnects and cooling permits, having allocations of GPUs is meaningless—they are just cold silicon. Physical infrastructure is the ultimate governor on the rate of AI progress.

</details>

### 为何命名为“机器时代”与智能的本质

**主持人**: 为什么将这只基金命名为“机器时代基金”（Machine Age Fund）？这个名称背后有什么哲学或技术层面的考量？

<details>
<summary>Original English</summary>

**Host**: Why name it the "Machine Age Fund"? What is the philosophical and technological thinking behind this name?

</details>

**马丁·卡萨多 (Martin Casado)**: 我认为 Ben 之前说得非常准确：“人工智能”（Artificial Intelligence）这个词在某种程度上其实用词不当。它不应该被称为人工智能，它实际上是**机器智能（Machine Intelligence）**。

这并不是人类大脑生物学意义上的思考方式。它是人类集体知识与思维产物的极其庞大的索引与表征，运行在由硅片、电力、光子构成的物理机器之上。未来智能水平的每一次重大跃迁，都将由底层机器系统的物理能力、能效比和通信带宽直接决定。机器本身就是智能的载体与放大器。

<details>
<summary>Original English</summary>

**Martin Casado**: I think Ben is completely right: "Artificial Intelligence" is almost a misnomer. It really is Machine Intelligence. It is not necessarily how biological humans think; it is a cache and synthesis of human thought, executed across physical machines made of silicon, electricity, and optics. The next breakthroughs in intelligence will be driven by the raw capability and efficiency of the underlying machines. The machine is the vessel and multiplier of intelligence.

</details>

**本·霍洛维茨 (Ben Horowitz)**: 而且这也是一个非常酷的名字，极具未来感与工业革命的力量感。它向工业时代的先驱们致敬，同时也宣告我们正在进入一个机器与计算系统全面重构物理世界的全新时代。

<details>
<summary>Original English</summary>

**Ben Horowitz**: It is also just a great, futuristic name. It honors the heritage of the Industrial Revolution while signaling that we are entering a new epoch where machines and compute systems rebuild the physical world.

</details>

### 新一代创始人的画像与投资哲学

**主持人**: 鉴于基础设施领域具有极高的资本密集度（CapEx Intensive），且研发周期漫长，什么样的创始人能够在这一领域取得成功？这与传统的互联网或 SaaS 创业者有何不同？

<details>
<summary>Original English</summary>

**Host**: Given that infrastructure is extremely CapEx intensive with long R&D cycles, what archetype of founders can succeed here? How does this differ from traditional SaaS or software founders?

</details>

**本·霍洛维茨 (Ben Horowitz)**: 最大的区别在于，这些公司在造出第一个可用产品之前，往往就需要投入数千万甚至数亿美元的资金。这非常考验创始人的资本运作能力、战略远见以及在极高不确定性下的系统工程执行力。

此外，芯片和硬件工程领域有着独特的人才代际特征。那些真正精通尖端存储器、模拟电路、晶圆封装的老兵，很多都是在这个行业深耕了数十年的资深专家。优秀的年轻创始人必须具备一种特殊的能力——能够赢得这些资深行业老兵的信任，并将他们聚合在一起攻克硬核难题。

<details>
<summary>Original English</summary>

**Ben Horowitz**: The defining difference is that massive amounts of capital must be deployed before there is even a finished product. This demands extraordinary capital strategy, technical vision, and systems execution under uncertainty. Moreover, in hardware and silicon, domain expertise takes decades to accumulate. Great young founders in this space must have the maturity and charisma to recruit and lead seasoned industry veterans who have built chips and physical infrastructure for thirty years.

</details>

**拉古·拉古拉姆 (Raghu Raghuram)**: 他们必须是**系统级创始人（Systems Founders）**。你不能仅仅是一个纯粹的理论算法研究员，也不能仅仅是一个单一芯片设计者。你必须能够站在整个数据中心、整个分布式集群乃至端到端软件栈的全局视角来做权衡与架构设计。

<details>
<summary>Original English</summary>

**Raghu Raghuram**: They must be true "systems founders." You cannot just be an algorithm researcher or an isolated chip designer. You must understand the holistic system tradeoffs spanning semiconductor physics, networking topologies, distributed runtime compilers, and data center operations.

</details>

**马丁·卡萨多 (Martin Casado)**: 现在创业环境还有一个非常有利的因素：前沿实验室和超大规模客户极其渴望获得任何能够提升能效和降低成本的创新方案。过去大客户对初创公司的硬件方案往往持观望态度，而现在他们愿意在非常早期的阶段就与初创团队开展深度合作与 PoC 测试。这种前所未有的市场拉动力为新一代基础设施创业者提供了极佳的历史机遇。

<details>
<summary>Original English</summary>

**Martin Casado**: Another key environmental factor is customer desperation. Frontier labs and hyperscalers are so bottlenecked that they actively partner with early-stage startups to test alternative silicon, optical switches, and cooling designs. This creates early commercial validation and feedback loops that were impossible in previous hardware cycles.

</details>

### 愿景展望：十年后的世界格局

**主持人**: 如果机器时代基金实现了它预期的使命，你们希望看到 5 到 10 年后的世界呈现出怎样的格局？

<details>
<summary>Original English</summary>

**Host**: If the Machine Age Fund accomplishes what you set out to do, how do you see the world transformed in 5 to 10 years?

</details>

**本·霍洛维茨 (Ben Horowitz)**: 最核心的期望是，美国在这一场关乎未来国运的基础设施科技竞争中保持领先与胜利。我们希望能看到极其丰富、充沛且廉价的清洁能源，看到极其高效环保的下一代绿色数据中心，看到芯片、内存、算力与先进制造的大繁荣。

这不仅关乎经济与投资回报，更关乎我们的核心价值观。美国之所以特殊，是因为它为全世界任何怀揣梦想、渴望做出深远贡献的人提供了从零开始创造伟业的土壤。而要让这种开放与创新精神延续下去，我们必须在底层核心技术上牢牢保持领导地位。

<details>
<summary>Original English</summary>

**Ben Horowitz**: Hopefully, America wins in the infrastructure race. We want to see an abundance of clean, efficient power, hyper-efficient sustainable data centers, and an abundance of chips and memory. It goes back to why America is special: it is the best place in the world for ambitious people to come with nothing and build something profound. Sustaining that open innovation ecosystem requires maintaining leadership in frontier technology and foundational infrastructure.

</details>

**主持人**: 总结得非常精彩。Martin、Ben、Raghu，非常感谢各位的深度分享！

<details>
<summary>Original English</summary>

**Host**: Fantastic wrap-up. Martin, Ben, Raghu, thank you so much for joining us.

</details>

**本·霍洛维茨 (Ben Horowitz)**: 谢谢。

<details>
<summary>Original English</summary>

**Ben Horowitz**: Thank you.

</details>

**拉古·拉古拉姆 (Raghu Raghuram)**: 谢谢。

<details>
<summary>Original English</summary>

**Raghu Raghuram**: Thank you.

</details>

**马丁·卡萨多 (Martin Casado)**: 谢谢大家。

<details>
<summary>Original English</summary>

**Martin Casado**: Thanks, yeah.

</details>