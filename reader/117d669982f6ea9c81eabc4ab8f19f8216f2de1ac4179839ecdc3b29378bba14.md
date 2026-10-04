---
author: Latent Space
date: '2026-09-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KS_IpnX7n9I
speaker: Latent Space
tags:
  - neural-operator
  - physics-simulation
  - multiphysics
  - foundation-model
  - scientific-computing
title: 物理世界的通用大模型：Accelerated Understanding 如何用神经网络算子重构多物理场仿真
summary: Accelerated Understanding 联合创始人 Anima Anandkumar 与 Benedict Janik 深入解析其物理通用大模型技术。团队突破传统单点仿真局限，通过神经算子（Neural Operators）与 4D 全时空建模，实现了高达 5 万亿 Token 的推理上下文与万亿参数训练，展示了多物理场联合训练的涌现能力及其在半导体协同设计与地热、关键矿产等能源领域的商业落地前景。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Anima Anandkumar
  - Benedict Janik
companies_orgs:
  - Accelerated Understanding
products_models: []
media_books: []
status: evergreen
---
### 破局物理仿真：从专用模型走向通用物理大模型

**R.J.**: 大家好！我是 **R.J.**，今天我和搭档 **Brandon** 一起主持这期 **Latent Space** 与 **Lightning AI** 联合呈现的 **AI for Science** 播客。一周前，我们刚刚发布了与 **Anima Anandkumar** 录制的一期精彩节目，反响非常热烈。这很大程度上得益于她在节目发布前几天刚刚公开了她的新创业公司 **Accelerated Understanding**。不过在一个月前录音时，她还处于隐形状态（Stealth），无法公开讨论公司细节。

今天我们把 Anima 再次请回节目，同时还邀请到了她的联合创始人 **Benedict Janik**。他们将向大家详细介绍 Accelerated Understanding，以及之前录制时不得不保密的那些核心技术。顺便提一句，Anima 刚刚入选了《时代》（**Time**）杂志评选的年度百大最具影响力人物（**Time 100**），稍后我们也会聊聊这个话题。首先，Benedict，欢迎你！Anima，欢迎回来！

<details>
<summary>Original English</summary>

**R.J.**: What's up everybody? I'm R.J. I'm here with my co-host Brandon for a latent space lightning AI for science podcast. A week ago, we released a fantastic episode with Anima Anandkumar. It got a great reception, probably helped by the fact that she brought her company Accelerated Understanding Out of Stealth days before we released. But when we recorded a month ago, she couldn't talk about her company. So now we have Anima back on the pod with her co-founder Benedict Janik to tell us about accelerated understanding and the things that she had to keep under wraps uh when we were recording before. By the way, just a little thing, Anima was just named Time magazine by Time magazine as one of the 100 most influential people of the year and we want to talk about that too. But first, Benedict, welcome. Anima, welcome back.

</details>

**Brandon**: 能请两位给我们介绍一下 **Accelerated Understanding** 吗？

<details>
<summary>Original English</summary>

**Brandon**: Uh please tell us about accelerated understanding.

</details>

**Benedict Janik**: 好的。本质上，我们的思考逻辑是这样的：我们回顾了 Anima 过去所做的所有成功项目——比如导管流体模拟、天气预测模型，以及她在上期播客中分享的各项突破。我们发现了一个规律，正如语言模型领域曾经发生过的那样。

如果你回顾语言处理的历史——在最近这轮 **AI 革命** 之前，那简直像远古时代——当时人们都在为特定任务训练专用模型：比如拼写检查模型、机器翻译模型、文本自动补全模型。随后 **OpenAI** 出现了，他们提出：为什么不把所有东西都放进同一个大模型里？事实证明这种做法极其成功，其表现全面超越了几乎所有专用模型。

因此我们问自己：我们能否将同样的范式应用于**物理模拟**（Physical Simulation）和**物理世界理解**（Physical Understanding）？我们在语言领域看到的通用性（Universality）与规模效应（Scale），在物理世界中的对应物究竟是什么？这就是 Accelerated Understanding 正在全力下注的方向。

<details>
<summary>Original English</summary>

**Benedict Janik**: Yeah. Essentially what we have been thinking about is we've been looking at uh all the successful projects that Anima has been doing all those like the catheter the weather model all those things she talked about on that last podcast and then we figured the thing that has happened in language like if you look back in language and that's now ancient times before the recent AI revolution people were training models for specific things like we had a spellchecking model there was a translation model. There was an autocomplete model and then OpenAI came along and was like, let's just put everything into one model and that turned out to work phenomenally well and exceed pretty much everything else those specialized models. And so now we were asking ourselves, can we do the same thing for physical simulation and for physical understanding? Yeah, you know that universality and scale that we've seen play out for language. What is that counterpart for the physical world and that's the bet that accelerated understanding is making?

</details>

**Brandon**: 我脑海中浮现的第一个问题是：要将大量不同物理领域的数据输入到同一个统一模型中，背后的统一性到底是什么？对于语言模型来说，无论你输入的是哪种语言，底层都是人类生成的文本标记，遵循着某些潜在的语法和语义结构。但在物理学中，有量子力学、宏观流体力学（**Fluid Mechanics**）、空气动力学、天体物理、地质物理，甚至是微观尺度的半导体输运。

这些领域所依赖的基础偏微分方程（**PDE**）在数学形式上存在巨大差异。物理世界中是否存在某种底层的“普适语元”或通用结构，让你可以构建一个跨流体力学、电磁学和材料力学的统一物理大模型？

<details>
<summary>Original English</summary>

**Brandon**: The first question that comes to my mind with this so it's a you know basically you're trying to apply a bunch of different domain data to a single model. What is the commonality there across you know? In language, all the data is human-generated text, it has a certain kind of underlying structure regardless of whether it's, you know, this language or that language. With physics, there's you know, quantum mechanics, macroscopic, you know, aerodynamics, astrophysics, all these different things. The underlying PDEs are very different. Is there a underlying, you know, universality across the physical world in a way that lets you build a single model of, you know, fluid flow and, you know, aerodynamics and astrophysics, etc.

</details>

**Anima Anandkumar**: 这是一个极其深刻的问题。首先，我们可以从自然法则与数学结构两个维度来看待这个问题。从根本上说，物理定律是由能量守恒、动量守恒、质量守恒等基本守恒定律（**Conservation Laws**）支配的，它们还具有平移不变性、旋转对称性以及规范对称性等基础对称性。

虽然在宏观上看，天体物理的尺度与微观半导体的尺度相差数个数量级，但描述它们演化的偏微分方程（PDE）在连续算子层面具有深层的共通性。无论是在流体中模拟涡流，还是在电磁场中模拟电荷分布，波动方程、扩散方程和对流输运方程的核心数学算子（Operator）是高度相通的。

更重要的是，深度学习特别是神经算子（**Neural Operators**）能够自动在不同尺度的物理现象之间学习共享的隐空间表征（Latent Representations）。这就像人类物理学家能够用相似的微积分工具和场论框架去分析不同的自然现象一样，神经网络可以在不同物理学科的数学模型之间捕捉到大量的共享特征。

<details>
<summary>Original English</summary>

**Anima Anandkumar**: That's a great question. And in fact, you know, when you think about the physical laws, right, there are fundamental conservation laws, symmetries, and principles that govern all of physics, whether it's conservation of energy, momentum, mass, or symmetries like translation, rotation, and gauge symmetries. And even though mathematically the equations may look different across domains, whether you're looking at fluid dynamics or electromagnetics or quantum systems, there are underlying shared mathematical structures and operators. And what we have seen with neural operators and deep learning for science is that across these different domains and different mathematical models there's a lot of shared features that these neural models can pick up.

</details>

---

### 突破 4D 全时空建模：万亿上下文与基础设施重构

**R.J.**: 明白了。那么在构建这个通用模型的过程中，目前最令人兴奋的进展是什么？团队目前走到了哪一步？

<details>
<summary>Original English</summary>

**R.J.**: I see. And and so what what is some of the most interesting? So actually where do we stand with building this model? How far have you gotten so far?

</details>

**Benedict Janik**: 事实上，我们已经持续训练和迭代模型一年多了。我们完成了所有必须进行的架构探索实验。这里最有趣且极具挑战性的一点在于：你必须彻底重构很多传统深度学习的基础设施，因为物理数据的数据形态（Data Shape）与语言数据截然不同。

在语言模型中，数据是由一维的 **Token** 构成的，序列长度沿单一维度增长，目前领先的语言模型可以容纳数百万 Token。但在物理世界中，数据是在多维空间中同时展开的。我们坚持不走捷径，致力于让数据完全忠实于真实物理世界。

这意味着空间维度是在三维（3D）中连续展开的，我们没有像大多数视频生成模型那样进行大幅有损压缩，而是保留完整的三维物理几何空间；同时，物理系统还要在时间维度上进行演化推进（Rollout）。

很多现有方案为了图省事，采用自回归（**Autoregressive**）方式一步一步预测未来时间步，但这会导致误差迅速累积，并且会丢失整个时空演化的物理连续性，进而无法清晰理解输入中的初始扰动究竟是如何导致输出变化的——而这种因果反演能力对工程设计至关重要。

因此在时间维度上，我们选择直接对完整的 4D（三维空间 + 一维时间）时空全演化进行一体化建模。

然而，一旦进入四维时空建模，由于各个维度独立增长，将它们相乘后，上下文长度（**Context Length**）会呈爆炸式激增，瞬间达到数十亿乃至数万亿（Trillions）的级别。

这正是我们在模型架构上取得的重大突破：我们的模型已经能够在高达 **1 万亿 Token 上下文**的输入和输出下完成全流程训练，并且在推理阶段实现了惊人的 **5 万亿 Token 上下文（5 Trillion Context Length）**！

如果你来自传统 NLP 领域，这个数字听起来不可思议。而且我们并没有采用视频大模型常见的降采样妥协方案——比如对像素做平均池化或大块 Patch 切割。即便不采用这些有损压缩手段，我们依然稳定支持了这样超大规模的上下文。

为了支撑如此庞大的模型训练，我们在工程底座上做了大量重构。传统的分布式训练技术（如 **FSDP**）会将模型层分片切分，并在前向与反向传播时将整层重新组装在单张 GPU 显存中。但我们的模型单层参数量极其庞大，根本无法装入单张 GPU；单个物理样本的体积甚至超过了一台整机节点（Node）的全部显存。

因此，我们从零重构了整套底层分片策略与分布式通信基础设施。至今我们已经完成了数百次大规模训练迭代，成功训练了高达**万亿参数级别（Trillion-parameter Models）**的物理基础模型。

此外，我们严格验证了多物理场联合训练（**Multiphysics**）的收益。我们特意挑选了多个在物理特征和数学机理上极具差异性的物理领域，将它们放入同一个模型中进行端到端 4D 时空训练，充分释放了模型的通用潜力。

<details>
<summary>Original English</summary>

**Benedict Janik**: Yeah, so we have actually been training for a bit more than a year. We've done all the usual architectural experiments you need to do. The interesting thing here even is you need to reinvent a lot of the things because the shape of our data is so different. Like if you look at for example language, you have tokens and those tokens grow in one dimension. You can fit like a million of them in leading models. for us uh it grows in more dimensions and that is kind of like the the special thing here is we don't want to cut any corners. So we are like let's make everything as it is in the real world. So we have space that grows in three dimensions. It's not compressed like in video models. It's actually staying in those three dimensions and then you also have the roll out over time. And there again people like to take the easy path do auto reagive meaning you predict one step at a time except then errors build up and you lose kind of that continuity and the understanding of what in the input actually led to the output which is really important for designing stuff. So even then for the time dimension we prefer to just model the full rollout which is what we're doing. But then you're in this place where it's suddenly four dimensions and all of those four dimensions grow independently and when you multiply those numbers out, you're very quickly in the billions or even trillions in context. And that is something we've actually achieved with our models. Like we're able to train up to a trillion context input. We're able to train with um like even inputs outputs both trillion context length. We are able to do inference at 5 trillion context. Like those are ridiculous numbers when you come from language and we're not even doing most of those like if you look at video models they do a bunch of tricks to make it more efficient. They like average over pixels. They patch them. We're not doing those things. We're still able to do this ridiculous context. But now going back on what have we done? How are we making it happen? Fitting this stuff is non-trivial. training this stuff is non-trivial. Like you may have heard of those standard techniques like FSTP where you shard but then you reassemble a layer in a GPU to do the training. Uh except our layers are so big you can't reassemble it inside a GPU. Our data samples are so big they don't fit an accelerator or even a full node. So we had to reinvent this whole sharding infrastructure, the whole sharding strategy to be able to train those models at scale. And we've done so we've trained done hundreds of training runs. We've trained up to trillion parameter models. So we've really shown this stuff to take off. The other thing that we've made sure is that we're actually benefiting from multifysics like not just doing everything big that was done small before but actually putting those things together. So we've on purpose picked a number of areas of physics that we believe are very diverse in their features, in their challenges and put them in the same model, done the full 4D roll out for those and we're able to train them.

</details>

**Anima Anandkumar**: 我想补充非常关键的一点：实验证明，在相同总参数量下，一个**同时学习多个物理领域**的统一模型，其综合性能显著优于为每个单一物理领域分别训练的独立模型。

换言之，即便你把相同规模的巨大参数量全部单独分配给单一物理领域，它的泛化与预测效果依然不如多物理场联合训练的通用模型。这强力证明了物理模型中存在着**跨领域共享表征与知识迁移（Shared Learning）**。这不仅是把模型做大就会变强那么简单，而是引入更多的物理规律能够反哺模型在每个具体物理任务上的理解能力——这正是我们在自然语言大模型中看到的**涌现能力（Emergent Learning）**在物理世界的重现。

<details>
<summary>Original English</summary>

**Anima Anandkumar**: And in fact uh I was going to add that it turns out that having the model of the same size with multiple areas of physics does better than giving all of those parameters to each single physics. So if you had separate models and made them big enough as the original one, it still is worse. And so that's saying that it's benefiting from shared learning. It's not just we make the model bigger and it gets better. That's true. But adding more areas of physics helps it to learn better in all of them. And that's the same kind of emergent learning we've seen play out in language.

</details>

---

### 神经算子的数学本质与分辨率无关性

**Brandon**: 在上期节目中，我们深入讨论了神经算子（Neural Operators），特别是你引入模型中的归纳偏置（**Inductive Biases**）——例如通过傅里叶神经算子（**Fourier Neural Operators, FNO**）转换到频域，或者在球面上操作以引入几何归纳偏置。

当你们现在尝试处理极其多样的几何构型时，迁移学习是如何运作的？你们目前是限制在规则矩形网格几何结构中，还是已经找到了有效融合任意复杂几何以及不同偏微分方程类别（例如具有不同阶次时间导数）的统一机制？

<details>
<summary>Original English</summary>

**Brandon**: In your episode, we talked a lot about um neural operators and we talked about in particular some of the inductive biases you put into your models like uh Forier neural operators where you go in for space where you operate on a sphere and then you you have an inductive bias about geometry. How does transfer learning work when you have are now trying to do many different geometries? like are you actually now limiting yourself to say like we're only doing you know rectangular geometries or is there actually some now tricks where you can actually integrate different types of um different classes of PTE like maybe with different time derivatives or things like that

</details>

**Anima Anandkumar**: 鉴于商业机密，我们无法透露底层模型架构的全部技术细节，但我可以明确的是：**神经算子（Neural Operators）** 是我们整个系统的核心基石，因为它是实现**分辨率无关性（Resolution Invariance）**的关键所在。

刚才 Benedict 提到我们在推理时实现了 5 万亿 Token 的上下文，在训练时实现了 1 万亿上下文。但这并不意味着每一次运行或每个应用场景都需要如此庞大的分辨率。对于极其复杂的物理场景，我们能够直接赋予它超大上下文以捕捉全部微观细节；而对于粗粒度任务或工程初期的设计空间探索，我们无需耗费巨大的算力，可以灵活降低分辨率。

这种动态自适应能力将我们与现有的所谓“世界模型”（无论是视频生成模型还是计算机视觉模型）彻底区分开来。传统的视觉/视频世界模型在训练和推理时都强依赖于固定分辨率网格。这在游戏娱乐或视觉展示中也许够用，因为物理规律稍微失真或模糊并无大碍；但在精密工程设计与科学发现中，这种妥协是绝对不可接受的。

神经算子赋予了我们在不同上下文长度（即不同网格分辨率）之间自由无缝切换的能力。

另一方面，如果尝试直接将自然语言领域取得巨大成功的标准 **Transformer** 架构套用到物理模拟中，面对 5 万亿 Token 的上下文，哪怕动用全世界所有的算力，其 $O(N^2)$ 的二次方计算复杂度也是完全不可承受的。

更重要的是，物理世界本身拥有丰富的局部性与场论数学结构，绝非任意节点间的全连接随机关联。因此我们必须针对物理世界的内在规律重新设计架构。

如同前沿 AI 实验室在语言模型上从早期架构到 **MoE**（专家混合架构）的系统性演进一样，Accelerated Understanding 也在持续推进物理大模型架构与硬件利用率的协同设计（**Hardware-Software Co-design**），深度优化通信拓扑与显存带宽。

<details>
<summary>Original English</summary>

**Anima Anandkumar**: yeah so we cannot tell you every exact detail of our architecture since uh that's proprietary but what I can tell you is neural operators do form the basis because that's how we can make this resolution invariant. So Benedict talked about a five trillion context length at inference time that we've achieved and a trillion context length during training. But does that mean every single run we're going to do that? No. Every single application needs that much resolution no right. So you know those are for the hardest physics that really requires all the details. we can give it the big context length and those that do not need that or even during the process like if you're doing design exploration all of these tasks in the beginning you don't need every single detail you don't need to burn that much compute and so that flexibility is crucial and if you see that immediately distinguishes us from other so-called world models whether it's video models vision models they all assume during training and inference it's a fixed resolution and that's Okay, for uh you know for our visual features, right? Because we don't really necessarily need to zoom in more especially for gaming and entertainment. It's okay. The physics is somewhat a bit tan wavy. But you know for the engineering design, scientific discovery, we can't get away with those tricks. And so neural operators form the key to ensuring that uh we can be flexible at giving different context lengths which is equivalent to different resolution. On the other hand uh if you think about using transformer architectures that have worked so well for language that just wouldn't be able to support a 5 trillion context length no matter all the compute in the world is thrown at it. So that kind of quadratic complexity is infeasible and also unnecessary because the physical world has more structure than completely arbitrary alltoall correlation. So we have to rethink what works better for the physical world and that's what we've done very systematically like how in the frontier labs for language there is a lot of systematic experiments and lot of evolution of architecture you see from the earlier models to mixture of experts and so on you know we kind of like gone through and we continue to go through that same evolution within our uh accelerated understanding to ensure that we have the best architecture as well as the best hardware utilization, you know, thinking about communication, bandwidth, all those requirements. So, that code design is really critical.

</details>

---

### 万亿 Token 的工程底座与算力伸缩

**R.J.**: 插一句，如果观众还没看过上一期节目，强烈推荐大家去补一下。如果想深入了解神经算子的理论细节，可以跳转到上期大约 20 分钟处。

回到当前话题，我知道这涉及很多专利与专有技术，但两位能否给我们建立一个直观认知：在算法与底层集群基础设施层面，你们是如何支撑起 1 万亿乃至 5 万亿 Token 的运算规模的？

<details>
<summary>Original English</summary>

**R.J.**: Oh, real quick, I just want to say people who for um people have not watched the original episode. Uh we recommend you watch it if you want to learn about neural operators, I think it starts around 20 minutes. We'll have a link directly to jump to that scene where we start talking about some other things. Um but yeah, wanted to make sure we got that plug in real quick. Um, yeah. So, I guess for for either of you, and I know a lot of this is probably proprietary, but can you give us an intuition for how how do you get to a trillion or five trillion tokens and how do you, you know, sort of that's both like a algorithmic question and also an infrastructure question.

</details>

**Benedict Janik**: 产生这样巨大的数值其实逻辑非常直接：如果在空间三维的每个轴向上各取 1000 个网格点分辨率（$1000 \times 1000 \times 1000 = 10^9$ 个空间网格），同时为了精确解析物理演化而追踪 1000 个时间步，两者相乘便直接达到了 $10^{12}$，即 1 万亿（1 Trillion）的时空单元。

从数据吞吐量来看，在我们完成的一次 **5 万亿 Token 运行** 中，仅单次输出的物理场数据量就高达 **22 TB**！为了避免严重的 I/O 瓶颈，这类规模的数据必须尽可能驻留在加速卡显存中，否则整个流水线会变得极其缓慢。

当然，我们的模型具备全谱系的伸缩能力：我们既能在超大规模集群上进行极高分辨率的分布式推理，也可以将较小上下文的模型直接部署在 **MacBook** 或 **Mac Studio** 上运行。

要驾驭这种规模，核心挑战在于：你必须让极大的活跃数据工作集（Working Set）在加速器集群中高效交互并完成模型前向流通。这高度依赖于低延迟、高可靠的高性能互连网络（**High-Performance Interconnect**）。

语言大模型（LLM）当前正在逐步面临的工程瓶颈——现代并行加速技巧与经典 **高性能计算（HPC）** 方法的深度结合——我们在创业第一天就必须全面解决。我们必须攻克如何切分并放置单个无法装入单台节点的样本，以及如何在层内交互计算时将状态高效保存在加速器内。

<details>
<summary>Original English</summary>

**Benedict Janik**: Yeah. So, um, how you add end up with those large numbers is fairly simple. Like if you say I have a thousand resolution in each spatial dimension and then I care about resolving the thousand time steps exactly then I'm at a trillion so that is a really large number and then when you think on a little bit in that math uh how big of data is that like for example our 5 trillion run that we did the outputs were uh 22 terabytes and you want that kind of stuff in accelerator memory. That's just what it is. Otherwise, it's going to be slow. So that is kind of like how you need to think about. Obviously, we can drive it uh all the sizes like we have done inference on huge clusters. We have done inference on like we can the small models with smaller context or even medium big models with smaller context fit on a MacBook or Mac Studio like you have that whole span. So like having this there is like like there is a bunch of scaling tricks that need to work out but the big one is you need a working set of your data that needs to fit somewhere and that is kind of like what drives all of this and then again I can talk about what you actually do but ultimately you can think of you want to interact the pieces of data with each other in some way over the mo like the throughput through the model and uh that means to a good degree you will also need to rely on large clusters with very reliable very good interconnect. So like a lot of those challenges that LLMs are walking more and more into where there's like both modern tricks and the good old HPC methods. We had those from the get-go. Like we had to figure out how do you fit a sample that does not fit into a node. We had to figure out how to do an interaction within a layer where you can keep the state around in an accelerator. So all those tricks require quite a bit of scaling and quite a bit of infrastructure work that we have been able to put together.

</details>

---

### 物理数据的生成机制：课程工程与密集反馈自进化

**Brandon**: 我们刚才一直在讨论数据规模。这引出了一个非常关键的问题：这些物理训练数据究竟长什么样？你们主要是通过求解大规模偏微分方程数值解来合成训练数据，还是从各种渠道采集真实物理测量数据？你们又是如何将数值仿真计算数据与现实物理观测数据有机融合的？

<details>
<summary>Original English</summary>

**Brandon**: We're just talking about data. That's actually I think a really interesting question that we haven't really expanded upon. Can can you can we double click a bit on that? Like what does the data look like? Are you is this primarily you're doing like large scale differential equation solving uh as like a to generate training data? Are you um getting physical data from a variety of sources? How do you integrate both physical data and also you know simulation computation data?

</details>

**Benedict Janik**: 这触及了物理 AI 领域最核心的历史痛点。在过去，很多狭义专用代理模型（Surrogates）往往受困于数据瓶颈：某些公司可能拥有一小块优质私有数据，训练出一个惊艳的 Demo，但一旦进入客户关心的分布外（Out-of-distribution）工况，模型就会彻底失效无法上线。

此外，物理仿真领域普遍存在“仿真到真实差距”（**Sim-to-Real Gap**）。我们致力于彻底打破这一局限。

偏微分方程（PDE）具有极其坚实的数学基础：只要你严谨求解偏微分方程，你所得到的物理规律就是绝对真实准确的。通过将模型的训练分布覆盖到足够宽广的物理参数空间，我们能够确保模型在面对实际物理任务时始终处于分布内（In-distribution）。

在数据生成方面，我们可以利用经典数值求解器合成海量且无限的训练数据。更重要的是，我们引入了**课程工程（Curriculum Engineering）**机制——模型可以从简单基础方程、低分辨率数据开始学习，逐步进阶到高度非线性与复杂多物理场。

这与自然语言大模型的训练形成了鲜明对比：在语言模型中，人们从互联网下载数万亿被随机打乱的海量文本，其中充斥着低质甚至错误内容，这完全违背了人类由浅入深的认知学习规律。而我们可以利用数值模拟器为模型定制高质量、渐进式的物理学习课程。

但这还远远不够。如果仅停留在模仿数值求解器，模型的表现最多只能达到训练数据分布的平均水平。为了超越训练数据本身的质量瓶颈，我们引入了**物理自进化机制（Self-Improvement）**。

偏微分方程不仅能用来生成初始数据，更能被作为精细的**训练损失信号（Training Signal）**。我们可以直接通过物理控制方程检验模型输出的残差与物理守恒程度，并以此作为损失函数指导模型自优化。

在语言模型中，自我演进往往依赖于稀疏的人类反馈（**RLHF**），反馈信号非常单一粗糙（仅有点赞/点踩等二元判断）。而在物理世界中，物理定律提供了极其精确且**密集的物理反馈（Dense Feedback）**。这种基于稠密物理约束的自我进化能力，让模型能够真正突破现有数值求解器的数据上限，并在实验中展现出了卓越的精度与稳定性。

<details>
<summary>Original English</summary>

**Benedict Janik**: Mhm. And that is that is actually quite an interesting point because that used to be a bottleneck especially for a lot of those narrow surrogates and you may have seen it. Company has some really nice pocket of data. You have a flashy demo but then the area they actually care about is out of sample and nothing gets deployed. So having this kind of limitation is something that we wanted to step out of. At the same time, we all know for simulating physics, the big theme is sim to real gap that you somehow need to overcome. So, how do we do both? Uh, one interesting thing with PTE is we are actually fairly confident like the math is known that when you solve a PD correctly, you're doing the physics correctly. Like obviously you still need to make sure that you're representing the task that you're trying to solve within that but you can solve the like sensial gap by making sure your skill domain is wide enough that you're guaranteed to be in distribution. Now for training itself what does that allow us to do? We can use numerical simulators to generate as much training data as we need and even further we can do what is called curriculum engineering meaning we can start with uh simple equations we can start with lower resolution simpler data that's which is a stark contrast to how language is trained like language you download all of the internet it's a giant mess it's shuffled all over some of it is correct some of it isn't and this is not how for example as humans would have learned like learning in order is much better. So we're able to do that. We're able to build our own curriculum using numerical simulators. But it doesn't stop there. Like if you were to stop there, you kind of end up as everything else in machine learning does at the average quality of your training distribution. And we wanted to exceed that. That's where also uh self-improvement comes in. So the interesting piece is you can use those PDEs both for numerical simulators to generate data, but if you're clever about it, you can even use them as a training signal. You can check how well is my model actually doing on the PTEs themselves and use that as an additional training signal where you're suddenly in a place where you can push beyond the quality of the data in your model quality. And the difference there is compared to language where self-improvement needs something like human feedback or other reward signals that are very sparse. They just tell you yes or no, thumbs up or down. We have dense feedback because the physics laws there's so multiple of them and you can decide again a curriculum of how to arrange them but also the feedback you're getting from them is dense and so that kind of self-improvement can be even better and that's what we see in our experiments.

</details>

**Brandon**: 物理系统中另一个极具挑战的难题是**多尺度特性（Multiscale）**——即宏观尺度的宏大现象与微观尺度的细微效应需要被同时建模表达。这种横跨数个数量级的动态特征往往是传统物理建模的核心难点。你们是如何在统一模型中同时兼顾大尺度与小尺度物理表征的？

<details>
<summary>Original English</summary>

**Brandon**: Maybe this is already implicit in your answer your previous um statements but one thing I'm curious about in physics is this idea of multiscale where like large scales are you know you need to simultaneously represent things happening at large scales and things happening at small scales and a lot of the times the difficulty of good physical representations is this you know is that you do need multiple scales which gives you this like large like orders of magnitude and understanding. um how do you represent that simultaneously like how do you how do you deal with that problem?

</details>

**Anima Anandkumar**: 这正是我们在神经算子诸多已发表研究中所重点解决的核心议题。面对多尺度问题，系统必须支持多分辨率处理。

如果对所有区域一律采用最高分辨率求解，计算成本将呈天文数字般不可承受。因此最佳策略是：首先在较低分辨率下采集大量宏观数据，甚至可以借助粗化（Coarsen）忽略微观扰动的低成本求解器。尽管这些粗糙数据在微观上是不准确的，但它们是捕捉宏观平均效应与大尺度趋势的绝佳起点；在此基础上，再使用能够解析精细微观特征的高精度求解器进行精准微调。

神经算子的独特优势在于，它具备在模型内部自适应融合跨尺度特征的数学灵活性，而无需像传统的物理混合机器学习方法那样通过外部硬编码规则进行强制划分。这赋予了模型极高的数据利用效率和更卓越的泛化学习能力。

<details>
<summary>Original English</summary>

**Anima Anandkumar**: Yeah. So if you see uh lot of our published work with neural operators that's exactly what we address right. So in terms of like if there multiple scales you also need multiple resolutions. Of course you could do everything at the highest resolution but that's extremely extremely expensive. So you're better off first uh collecting more data at lower resolution, maybe even cheaper solvers that coarsen and ignore the fine scale effects. They're wrong, but there are good starting points to kind of get the overall average effects, the core scale effects, and then you can fine-tune with more specialized uh that take into solvers that take into account those finer scale features. And neural operators have this flexibility because they can allow you to mix across different scales within the model rather than be prescribed externally like a lot of other hybrid machine learning for physics do and that you know allows us to be a lot more data efficient and much better at learning.

</details>

---

### 商业落地前沿：半导体芯片协同设计与清洁能源

**R.J.**: 鉴于时间关系，我想探讨一下具体的行业应用落地。你们走出隐形状态后，首先瞄准的商业化落地场景有哪些？

<details>
<summary>Original English</summary>

**R.J.**: We don't have a ton of time. I want to hear a little bit what are the the applications here? What are you what are you chasing first? um you've come out of stealth. So presumably there's something that you're doing uh more publicly with commercialization. Can you talk a bit about that?

</details>

**Benedict Janik**: 我们的商业落地战略由两个维度定义：底层物理领域与对应的垂直产业。当前全行业需求最迫切、最渴望取得颠覆性性能提升的两个核心赛道，正是我们的绝对长项：**半导体（Semiconductor）** 与 **能源（Energy）**。

虽然受保密协议限制我们无法公开具体客户名单，但在半导体领域，物理效应正变得空前重要。

回顾过去芯片设计的工作流：工程师往往先在纯数字逻辑层面完成设计并锁定，然后再导入物理仿真工具进行一次性的物理规则检查。例如依据台积电等晶圆厂的 **PDK** 规则，确认某项物理特征是否达标、工艺裕量（Headroom）是否足够，若达标则交付流片。

但这种割裂的流程完全没有利用物理裕量去榨取额外的芯片性能与能效。借助我们的物理通用大模型，设计工具能够深入物理底层，探索物理规律允许的极限，通过全流程的数字-模拟-物理协同优化重构布局布线。此外，在半导体晶圆制造的先进工艺制程中，同样存在大量极端复杂的物理与化学传递挑战，这正是我们发力的重点。

<details>
<summary>Original English</summary>

**Benedict Janik**: The way we're thinking about it is like there's two perspectives. There is the domains of physics and then there's the areas that can be served by them. So if you look at areas that are obviously very interesting right now because everybody needs improvement there the big ones to everybody are semi and energy and those are precisely right in our wheelhouse. So we can't tell you fully who we're talking to, who our customers are, but like within Sammy, you can think of a lot of problems that physics become increasingly relevant. And the interesting thing is if you look at how a lot of stuff worked there. Um especially when you look at uh the chip design itself, it was much more a let's start in the digital, let's freeze the digital in, let's send it through some physics for a one-time check. Like the PDK dictates I have to have the following feature otherwise TSNC doesn't make it for you. And it stops there. Like it's like do we have enough headroom to push it through? But we're not taking advantage today of that headroom to get extra performance. So there's this potential to unlock much more of the skill set when you're also able to grab into what does the physics allow me to do to push the envelope a bit more and can I rearrange everything a little bit to push the envelope even further. That's one area. Obviously the semi-production process itself also has all these interesting physical challenges that we're addressing. So lots and lots of work to do. Um we're excited.

</details>

**Brandon**: 我理解得对吗？也就是说，你们正在实现半导体领域的**数字与模拟/物理协同设计（Digital-Analog-Physical Co-design）**？

<details>
<summary>Original English</summary>

**Brandon**: So do I understand correctly like semiconductor digital uh uh analog code design

</details>

**Benedict Janik**: 没错。显然这需要从基础一步步构建，整条工具链正在持续升级。我们正在自底向上赋能物理层面的真实模拟与反向设计。

过去行业为了简化计算做了大量折中——比如仅优化线长（Wire Length），或者做局部的热尖峰（Thermal Spike）和电磁干扰（EM Spike）检查。而我们能够全局掌握芯片物理场的整体分布，充分利用过去被过度简化的物理潜力。

<details>
<summary>Original English</summary>

**Benedict Janik**: like obviously you need to start somewhere and that there is like this whole pipeline that is also now improving like we are making sure that like we're bottom up enabling that physical like eventually that's where the journey is going obviously um there's different companies that do different pieces we're starting from that direction because we think that direction is opening up a lot of impact where previously there was a lot of simplifications like you did wire length you did certain optimizations you're like oh do I have a thermal spike somewhere do I have an em spike somewhere that messes with me but not oh I have all this other stuff where it's actually fairly cool where there's fairly little craziness happen can I take advantage of that

</details>

**Brandon**: 太棒了！在能源领域，我们之前探讨过滤波聚变与核能。这依然是你们的核心方向之一吗？你们是否也覆盖了太阳能以及其他新能源领域？

<details>
<summary>Original English</summary>

**Brandon**: nice and and energy presumably we've talked about nuclear before I presume assume that's that's one of the areas there is are you also doing solar and other things like that

</details>

**Benedict Janik**: 在能源领域主要分为两类需求：

第一类是正向设计问题——设计具有特定性能极限的物理装备或器件，这是我们的强项；

第二类是反演推断问题——基于现实世界的观测数据，反推地下未知的物理场分布。例如在**地热能（Geothermal）**勘探中，精准推断地下深处的高温储层分布以及适合注水循环的岩层结构；或者勘探现代电子电气工业不可或缺的**关键关键矿产（Critical Minerals）**。

这些应用无一例外依赖于深厚的物理学机理。由于不同物理领域的底层控制规律具有高度同构性，一旦模型达到了足够的通用性水平，大量跨行业的工程大门都会随之敞开。

<details>
<summary>Original English</summary>

**Benedict Janik**: there is both the design kind of piece which is uh I want a physical object with certain capabilities that's was something we're really good at there's other areas where um the question is I have observations of the world what does that tell me about the world like think geodermal where you want to know where It's warm down there with the right mix of water that you can pump through. Like all of those things were or where are the critical minerals for for all the electronic devices we need? Uh like all of those things kind of end up in our wheelhouse and you get there with you need a good amount of physics but physics at the same time like there's not that many things that are different from each other. So you like once you're at this point where your model reaches a good level of universality, suddenly a lot of doors open.

</details>

**Brandon**: 顺着这点深入一下：在你们当前推进的真实商业客户应用中，你们是否已经切实观察到了这种跨领域的**物理知识迁移（Physical Uplift / Transfer Learning）**？

<details>
<summary>Original English</summary>

**Brandon**: Just to push on that a little bit and you're seeing some of that transfer happening in the applications that you're chasing with with real commercial.

</details>

**Benedict Janik**: 没错，我们真真切切地观察到了这种**跨物理场的性能飞跃（Physical Uplift）**！

我们在内部做过严格的对照实验：先单独训练一个配置完善的特定领域专用模拟器，确保其数据管线无误；然后将相同任务接入到通用多物理场大模型中。结果表明，通用物理大模型在具体垂直任务上的精度与泛化表现，全面且碾压性地超越了单一领域的专用模型！

<details>
<summary>Original English</summary>

**Benedict Janik**: Exactly. Like we're seeing that physical uplift happening. We mentioned it earlier. We've trained models where we were like, let's just make sure our simulator is fine, configured fine, and we can actually train it. And then we were like, oh, and let's add it to the universal one. Like, you want to always test those kind of things. Like there's this whole bunch of pipeline work that you want to make sure you're correct. And what we observed is we had like like in terms of the performance characteristics we're seeing in the narrow one versus what we suddenly saw in the broad one, it was like broad all the way.

</details>

---

### 未来展望与 Time 100 荣耀时刻

**R.J.**: 节目时间差不多了，最后一个问题：Accelerated Understanding 的下一步规划是什么？你们目前在招募人才、扩张团队吗？

<details>
<summary>Original English</summary>

**R.J.**: We're running low on time, but maybe is the last question. What what is next for accelerated understanding? Uh what do you want people to know? And uh are you you hiring, you're opening offices, like what's going on?

</details>

**Anima Anandkumar**: 毫无疑问，所有这些都在全速推进中！我们在持续扩大模型规模，同时也在迅速扩充团队。自上周公开亮相以来，我们收到了大量合作意向与咨询，我正在抓紧一一回复。

对于我们而言，这只是物理模型 Scaling 壮丽征程的起点。面对人类在科学发现与技术发明中遇到的终极物理挑战，我们一方面将不断攻坚最硬核的多物理场复杂机理，另一方面也将立足商业实体，持续为产业客户释放巨大的商业价值。

<details>
<summary>Original English</summary>

**Anima Anandkumar**: Yeah, certainly all of that. I mean we are scaling our models and we continue to scale our company. So yes, you know, we are getting a lot of inbound interest since last week. So I'm just getting through that. So I apologize if I haven't gotten back to someone yet, but it's a really exciting time. And you know, and for us, this is just the beginning in the journey of the model scaling, right? If we have to go towards the biggest challenges we are facing in scientific discovery and inventions, those are really hard physics, hard phenomena. But at the same time we have to be also true to our commercial side and ensure along the way we unlock [clears throat] a lot of value to our customers. So it's that combination that it we are very excited about.

</details>

**R.J.**: 在结束前，能花 30 秒跟我们分享一下入选 **Time 100** 的感受吗？整个过程是怎样的？

<details>
<summary>Original English</summary>

**R.J.**: Well and actually I want to just hear for 30 seconds tell me about the time 100 thing like what what happened there? How did it go down? I' I've never received one so I just I'm curious.

</details>

**Anima Anandkumar**: 能够入选 **Time 100 AI** 榜单，我感到极其荣幸和惊喜。去年我非常幸运地获得了 Time 100 影响力大奖，并受邀前往迪拜与众多行业先驱交流。我认为《时代》杂志在汇聚来自不同背景与视角的 AI 探索者方面发挥了极其积极的作用，能够参与其中是一件非常美妙的事情。

<details>
<summary>Original English</summary>

**Anima Anandkumar**: You know, I was just thrilled and really surprised to be included in the time 100 AI list. Uh, you know, I was also very lucky to receive the timeund impact award last year. So, I was in Dubai for that and you know, got to meet a lot of uh luminaries in the field and now uh you know this year. So, it's uh I think it's good what they're doing trying to bring people with different perspectives on AI together. So yeah, so that's a good thing.

</details>

**R.J.**: 再次祝贺你，实至名归！非常感谢二位再次做客我们的播客，我们非常期待见证 Accelerated Understanding 带来的颠覆性变革！

<details>
<summary>Original English</summary>

**R.J.**: Yeah. Well, congratulations. Welld deserved and thank you so much for for jumping back on with us and we're really excited to see how everything unfolds with accelerated understanding.

</details>

**Benedict Janik**: 非常感谢你们邀请我们回来！

<details>
<summary>Original English</summary>

**Benedict Janik**: Thanks a lot for having us back.

</details>

**Anima Anandkumar**: 谢谢大家！

<details>
<summary>Original English</summary>

**Anima Anandkumar**: Thank you.

</details>

**R.J.**: 大家保重，再见！

<details>
<summary>Original English</summary>

**R.J.**: Take care. Bye. [music]

</details>