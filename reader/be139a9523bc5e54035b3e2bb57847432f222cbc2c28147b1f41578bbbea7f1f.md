---
author: Bloomberg Podcasts
date: '2026-06-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=BrpadR5KuMo
speaker: Bloomberg Podcasts
tags:
  - ai-inference
  - gpu-infrastructure
  - data-center-financing
  - compute-commoditization
  - model-routing
title: 算力市场深探：从成本冲击到AI基础设施金融化
summary: 本期播客探讨了激增的AI推理需求如何引发企业的预算焦虑与模型路由需求。CoreWeave联合创始人解析了算力客户结构向华尔街等企业的扩散、长达五年的基础设施锁定合约、Nvidia在推理端的持续垄断，以及通过特殊目的实体（SPV）实现数据中心非追索性融资的创新模式。同时指出，由于模型浮点运算利用率（MFU）等性能差异，算力在短期内难以成为标准大宗商品。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - CoreWeave
  - Nvidia
  - Jane Street
products_models:
  - Hopper
  - Blackwell
  - Vera Rubin
  - H100
media_books: []
status: evergreen
---
### 预算冲击与推理市场的崛起

随着人工智能在企业界从初步尝试步入实质性部署，焦点已由单纯的模型实验转向高频的实际应用。这种转变带来了前所未有的计算成本冲击（Sticker Shock），促使全球企业的CFO们开始对激增的AI推理开支进行严格审查。例如，Uber为控制成本，为员工设定了每月1500美元的代币（Tokens）消耗上限，其首席运营官更是着手评估这些庞大支出是否真正转化为了生产力收益。

在建立这种成本控制意识后，企业的底层使用逻辑正在发生演变。未来，随着基础设施账单的增加，企业将加大对**模型路由（Model Routing）**的投资力度——即不再将所有简单任务盲目交由最昂贵的前沿大模型处理，而是根据具体查询需求，将任务动态分配给成本可能低至百分之一的适配模型，以此寻找成本与效能的最佳前沿。这种趋势也直接打破了“旧款GPU将迅速贬值”的传言。

<details><summary>Original English</summary>
That phase of AI is long over and we know that companies specifically are spending a ton on compute. So much so that CFOs around the world are getting sticker shock about their compute budgets. And there was even a headline of like Uber saying like, okay, like $1,500 of max per employee, like don't spend more than that in a month on tokens.

You're starting to get headlines about, I guess, a corporate reckoning with AI as more people experiment and spend money on it. The Uber headline that you mentioned, apparently Uber burned through its entire 2026 AI budget in four months basically. And like what's more important is the COO was actually asking whether or not that was worth it, like whether they saw productivity gains or whatever as a result of that.

I predict is that companies are like clearly you know they're going to keep using it more and more would be my guess but there will probably be a lot of investment made in sort of like optimal model routing because some models are like a hundth per query of what a frontier model is probably a lot of people don't know like what is the sort of like efficient frontier model usage and So actually routing the query to the sort of most uh efficient model. I have a feeling we're going to see a lot of investment in that area specifically.

You can kind of conceptualize this matrix of different sizes of workloads relative to different sizes of GPUs. And all of a sudden that tells you my god like H100s could last six, seven, eight years. A100s are going to last longer. And it totally changes the entire conversation around depreciable life of infrastructure.
</details>

### 客户结构演化：从大模型实验室到华尔街

仅仅一两年前，算力的消耗还高度集中在少数顶级大语言模型实验室和超大规模云服务商（Hyperscalers）手中。然而，**CoreWeave**的客户数据表明，算力需求正在发生本质扩散。尽管他们依然服务于全球排名前十中的九家AI实验室，但来自更广泛企业的真实需求正在爆炸性增长，企业群体的标识（Logos）录得了历史最高增速。

尤其在金融服务领域，这种需求已经达到惊人的规模。CoreWeave直接来自金融企业的未完成订单（Backlog）已接近100亿美元。以量化巨头 **Jane Street** 为例，他们并未通过OpenAI或Anthropic等底层模型提供商间接获取算力，而是直接对接算力平台，管理底层基础设施，以部署和运行其内部的高机密推断与训练工作流。这标志着越来越多具备技术实力的企业正在走向“基础设施直连”模式。

<details><summary>Original English</summary>
We got a lot of flack for this in our IPO, right? Like people were uh noting that we only had a handful of large clients um that our clients were like just the hyperscalers and AI lab or two and I think that we have made tremendous progress in driving diversification.

We have hyperscaler clients who continue to grow with us. We have AI lab clients. Um as I said, nine of the top 10 AI labs on the planet choose Core Reef. And then we have this enterprise base.

On our end, I think we have 10 over1 billion dollar clients at this point and our financial services client backlog is in the tens of billions of dollars at this point.

The scenario you presented anthropic would be our client. So what I'm highlighting I want to correct the number I said earlier our financial service clients and this is direct to those financial services they're approaching 10 billion in backlog okay so this would be you know a good example of this and that's something we made recently is with Jane Street okay right that's not Jane Street coming through open AI or anthropic to get to us that is Jane Street coming directly to us and using our platform.

At the end of the day we don't know what exact workloads okay these entities are running. Um especially for entities like Jane Street. I would imagine that's highly secretive. Um but the point I would say is more that this is not them coming through an AI lab to us. They are interfacing with and managing the infrastructure directly on our platform.
</details>

### 基础设施锁定与下一代架构迭代

随着模型参数规模的膨胀（遵循Scaling Laws），AI实验室对算力基础设施的诉求发生了深刻的行为转变：他们渴望获取规模更大且锁定周期更长的算力资源。两年前，标准的算力承诺往往是三年期；去年这一数字延长为四年（主要针对**Hopper**或**Blackwell**架构）；而如今，客户开始寻求长达五年的全生命周期合约，并且明确要求保持统一的经济条款，拒绝任何服务中断或架构变更。

在此诉求之上，算力硬件本身也迎来了结构性的复杂化演进。当前正在大规模部署的 Blackwell 架构（特别是 NVL72 配置）带来了范式转换：它彻底抛弃了过去以八卡服务器为主的42U风冷机架，转而采用巨大的全液冷整机柜架构。而面向未来的 **Vera Rubin** 架构目前已进入机架测试阶段。值得注意的是，硬件更新换代并未淘汰旧设施，对前代芯片的需求依然强劲。

<details><summary>Original English</summary>
The observation I would make in a behavior change for the AI labs is they want access to more infrastructure for longer duration. Right? A year two years ago we were signing three-year committed contracts. Last year it was four-year contracts, right? They were saying we want explicit access to Hopper for four years or Blackwell for four years.

Now they're coming and saying well actually we want it for five years and we don't want any interruption of use. We'll commit to the exact same economics throughout the full duration of the contract. You can't upgrade or change the infrastructure within it. You cannot cancel the contract. We want it for 5 years. And they want it at more scale.

The current architecture that we're deploying today is Blackwell. Blackwell comes we deployed predominantly in a MBL72 configuration which was an entire architecture change from deployment right if you recall hopper came before Blackwell. Hopper you could deploy these 42U racks which was typically like eight GPUs in a server case.

Blackwell for our deployments um is overwhelmingly liquid cooled in its deployment configuration. And instead of eight GPUs in a 42U configuration, it's in this larger 72 GPU rack.

Vera Rubin uh will be the next architecture that comes out and we've started receiving testing racks uh for Ver Rubin. But that doesn't necessarily mean, going back to the point earlier, that everyone only wants the latest generation of GPU, right? We have massive demand for Ampear, Hopper, Blackwell, etc.
</details>

### Nvidia的双重护城河与数据中心瓶颈

尽管市场不断传出微软、亚马逊自研芯片的消息（如 Maia 200 或 Trainium），但在实际客户端视角中，**Nvidia**的生态壁垒依然牢不可破。外界曾有论调认为，Nvidia仅在模型训练领域具备垄断地位，而在推理侧存在突围可能。但行业实际运行数据给出了反驳：在CoreWeave平台上，推理工作负载占比已远超50%，且客户仍一致要求使用Nvidia芯片。Nvidia长达15年构建的CUDA架构，加上其无可比拟的系统规模扩展性，让所有大规模投资只能向其靠拢。

在这种芯片高度集中的背景下，当前市场的最大扩张瓶颈已不再是获取GPU，或是寻找可用土地，而是极度缺乏 **带电空壳（Powered Shell）**。这是一个内部已接通能源、备用电池、大型变压器以及关键冷却系统的“完备式空置数据中心”。此外，人才供应链（如需要5年学徒期才能成熟的重型电力安装电工）的刚性约束，也使得物理场馆的落成难以像软件一样无限扩容。

<details><summary>Original English</summary>
The client isn't asking for anything but Nvidia infrastructure. And I think a large contributor to that is I mean they built this incredible ecosystem around their chipset. um they have been dedicating to that for I think over 15 years at this point through the CUDA architecture and Nvidia from what we hear from our clients that platform just remains the most efficient the most scalable the most reliable uh set of infrastructure that is in the market.

In our last quarterly report our CEO Mike qualified that inference workloads represent well in excess of 50% of infrastructure utilization on our platform. The exact same infrastructure they use for training as well. Those customers are choosing Nvidia to work with on imprints.

Landed usage specifically, I wouldn't say is as much of a concern. Having a powered shell is the bottleneck. PowerShell is effectively an empty data center that is energized, right? It has all the power and associated components. I can come into it and deliver electrons into a rack. Has the cooling system built within it.

That is the bottleneck because of all of the supply chains that that come into that, right? Like not only you have electricity, do you have the land etc. But you have the backup battery supplies, you have the transformers, um you have personnel, right? Like think about the electricians for these sites. I think it's a 5year plus apprenticeship to be able to go through that program.
</details>

### 算力资产金融化：构建GPU债务市场

数据中心的大规模激增需要天文数字的资本支持，而CoreWeave通过开创性的融资结构，成功打通了华尔街与AI硬件之间的桥梁。年内筹集超210亿美元资金的背后，是一套将长期合同转化为金融资产的复杂系统。

这种融资模型分为母公司融资与资产公司（Asset Co.）融资。其核心操作是将实体GPU、数据中心运营成本与长达五年的“照付不议（Take-or-pay）”无条件支付合同打包，注入一个**特殊目的实体（SPV）**中。SPV产生的稳定现金流直接用于偿还债务和支付运营开支，最终还能向母公司输送高达25%的边际利润。凭借这一确定性极高的逻辑，这类非追索GPU融资成功获得了投资级评级（Investment Grade rated），并以极其优越的资本成本（如SOFR+225基点）吸引了庞大但保守的保险资金入场，为AI超级计算机的扩张奠定了金融基石。

<details><summary>Original English</summary>
You know a bottleneck that existed for us previously I think was access to financing. I mean, year to date, we've raised over $21 billion of financing for our business.

The way that we finance our business, you kind of break it into two broad buckets, right? You have parent co- financing and asset co financing. And asset co financing is where all of the GPUs get financed, right? It's where all of our client contracts sit and we could take these financings and put them into STDs or we'll just call it a box.

These SPVS uh and these these SPVS they have the infrastructure they have the data center costs and they have the uh the the debt agreements within them. And so you're able to pair this like five-year take or pay contract to an amortization schedule on the debt and you have the revenue come into the box, pay down the amortization schedule, pay down the operating costs of the data center, and it still contributes a it has a 25% contribution margin of profit up to the parent code.

One of the latest ones we did was uh as we call DDTL4 this was a investment grade rated first of its class. No one had done this before for GPU financing, nonreourse HPC infrastructure financing and got done at sofur plus 225 like that that is a phenomenal cost of capital for us and importantly we were able to bring in uh the insurance trunch of capital.
</details>

### 算力商品化迷局：不可替代性与技术屏障

随着算力成本和需求的攀升，市场开始设想建立像原油或天然气一样的“算力期货市场”。但在技术极客与运营商眼中，短期内这只是海市蜃楼，因为算力严重缺乏金融商品最核心的特质：**同质化（Fungibility）**。

即使是完全相同的物理硬件（如一张 **H100**），部署在不同的云环境中所表现出的性能也天差地别。在业界，衡量这种效能的指标被称为 **Goodput（有效吞吐量）** 或 **模型浮点运算利用率（MFU, Model Flops Utilization）**。决定这些指标高低的并非纯粹的硬件堆砌，而是背后复杂的软件调度能力——比如云服务商能否准确预测显卡故障并实现热切换，以及能否优化集群通信网络。只要建设和运营这些庞然大物的技术门槛还在逐代升高，计算能力就无法被剥离为标准化的金融标的物。

<details><summary>Original English</summary>
Shortterm, no. Let me offer why no short-term and then I'd say maybe in the long term and it all comes back to fungeibility. GPU compute today is not fungeable.

This idea that an H100 deployed in one cloud doesn't have the same performance of an H100 deployed in another cloud and the the metrics that people use are things like good put or model flop utilization MFUs and there are these measurements of like how much more performant is one G the exact same GPU by the way versus another GPU deployed in another facility. And so in order for something to be commoditized, it it has to be fungeible, right?

But the rest of it honestly is just how you operate the the GPUs and that is the coreweave software stack that is how do you keep these GPUs online, right? Like what happens if a GPU fails? Can you predict if a GPU is about to fail and swap in other infrastructure so that the client doesn't have downtime on that component? And there's there's an immense suite of software solutions that and and infrastructure management solutions that we have built to have the best goodput to have the best MFUS in the industry.

Goodput measures the fraction of peak hardware performance that the training job can extract. And MFU's model flops utilization hardware metric for evaluating real world efficiency of LLM's training.

The reality is this stuff isn't getting easier to operate, right? We've moved from these kind of relatively simple 42U aircooled racks of hopper to these immensely complex blackwell deployments moving into Vera Rubin following that like it's not getting easier to to build operate provision deliver these GPUs it's getting more difficult and I I I think until it starts becoming easier you don't really have a path to commoditization.
</details>