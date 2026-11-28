---
author: Latent Space
date: '2026-05-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9d899Ram9Bs
speaker: Latent Space
tags:
  - theoretical-physics
  - quantum-gravity
  - scattering-amplitudes
  - scientific-discovery
  - reasoning-models
title: AI 物理学的奇点：GPT-5 如何破解困扰物理学家一年的难题
summary: 理论物理学家 Alex Lubyansky 分享了 AI 在基础物理学研究中的革命性进展。他详细描述了 OpenAI 的推理模型如何独立推导并证明了关于胶子（Gluon）和引力子（Graviton）散射振幅的非零性质，将原本需要一年的复杂研究缩短至几周甚至几小时。这标志着 AI 已从简单的辅助工具演变为能够推动科学前沿、具备“超人”科研能力的深度合作伙伴。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Alex Lubyansky
  - Andrew Strominger
  - Alfredo Guevara
  - David Skinner
  - Mark Chen
  - Terry Tao
companies_orgs:
  - OpenAI
  - Vanderbilt University
  - Harvard University
products_models:
  - GPT-5
  - o3
  - Codex
  - GPT-5.2 Pro
media_books: []
status: evergreen
---
### 跨越科学门槛：AI 在理论物理中的超人时刻

**Alex Lubyansky** 教授指出，我们正处于一个特殊的历史节点：AI 在某些特定科学任务上已经展现出了**超人**（Superhuman: 超越人类专家的能力）的表现。一个典型的里程碑是，AI 最近解决了一个困扰该领域顶级物理学家一年之久的难题，且处理速度之快令人震惊。对于普通人来说，这或许只是深奥的理论物理研究，但从科学范式的角度看，这标志着我们已经跨越了一个深刻的门槛。作为范德堡大学教授及 OpenAI 的研究员，Alex 拥有极其显赫的背景，包括获得 2024 年“物理学新视野奖”（Breakthrough Prize: 被誉为科学界的奥斯卡）。

<details>
<summary>Original English Source</summary>

Okay, so I think we're at a special time now where at least in some directions AI has become superhuman at least on certain tasks. And that's what led to these recent papers that resolve a problem that was puzzling physicists experts in the field for over a year. And they were unable to resolve it and AI was able to do it very quickly. So I think that's a certain milestone that we've passed. I think maybe for the average person on the street who doesn't care about theoretical physics, this is not very noticeable, but I think it's a very profound change and we've really passed some kind of a threshold. Welcome to the AI for Science podcast, part of Lean Space Network. I'm Brandon... joined by my co-host RJ Honicky... it's a pleasure to introduce Alex Lubyansky, Professor at Vanderbilt University and fellow at OpenAI. He has quite a storied background... winner of the 2024 New Horizons Breakthrough Prize. It's the Oscars for science. Right now he's having fun at OpenAI doing some really cool research of pushing the foundation of theoretical physics using GPT models.

</details>

### 从怀疑到震撼：物理学家的 “AI 觉醒” 之路

在过去的一年里，Alex 经历了一个从 AI 怀疑论者到坚实信徒的剧烈转变。起初，他认为 AI 虽然擅长写邮件，但绝对无法处理复杂的**理论物理计算**（Theoretical physics calculations）。然而，一系列进展彻底改变了他的看法：首先是 **o3**（OpenAI 内部强大的推理模型）展现出了极强的数学推理能力，节省了他大量时间；随后，当 **GPT-5** 问世时，它仅用 30 分钟就复现了 Alex 曾经花费极长时间才完成的最优秀论文。这一刻他彻底被“AI 化”了（AI pilled: 指对 AI 能力产生深刻认同），意识到这是他一生中最重要的科学发现，将永久改变科学研究的方式。为了不与这一变革失之交臂，他选择在学术假期间加入 OpenAI。

<details>
<summary>Original English Source</summary>

The one message I wanted to convey is that I think we're on this trajectory which I personally find very surprising and yeah, kind of surreal but also amazing. Where I would say a little over a year ago AI was very useful for email but not the kind of work that I do that I consider important theoretical physics calculations. I thought, "Oh, that's special. It's much harder than email and AI is not going to be able to do that." And then there were a series of developments that came in rapid succession that completely changed my mind. Specifically in particular ChatGPT o3 was the first really strong reasoning model that could do actual math that was useful for my research and could save me a lot of time. That's when I started to really pay attention and use it a lot more. Then when GPT-5 came out it was able to reproduce one of my best papers that took me a very long time to come up with in like 30 minutes. And that's when I really became AI pilled. I thought, "Oh my god, this changes everything. It's the most important discovery in my lifetime. It's going to affect everything about how we do research." To understand that this is happening and not be a part of it is a huge mistake so I have to go to OpenAI.

</details>

### 物理学基石：量子场论与散射振幅的奥秘

为了理解 AI 的具体贡献，必须先了解 20 世纪物理学的最高成就之一：**量子场论**（Quantum Field Theory: 描述自然界基本作用力的统一框架）。量子场论试图调和**相对论**（Relativity: 光速不可超越）与**测不准原理**（Uncertainty Principle: 量子世界的模糊性）之间的紧张关系。在该理论中，研究的核心是**散射振幅**（Scattering Amplitudes: 描述粒子碰撞概率的复杂量）。通过计算这些振幅，物理学家可以预测在粒子对撞机（如 CERN 的 LHC）中发生各种物理过程的概率。散射振幅不仅涉及粒子的能量和动量，还涉及**偏振**（Polarization: 粒子携带的螺旋方向），它是掌握自然界四种基本力的关键：电磁力、引力、强核力和弱核力。

<details>
<summary>Original English Source</summary>

In physics there are two basic principles of nature that we think every law should respect... relativity... you cannot transmit information faster than the speed of light. But then there's another principle which is the uncertainty principle... everything is a little fuzzy. There's a tension between these two principles. The great achievement of 20th century physics is the elaboration of this framework called quantum field theory. What you're trying to compute are the probabilities for certain events to occur. Probability distributions are obtained by squaring certain complex quantities... which we call quantum amplitudes. These quantum amplitudes... called scattering amplitudes... describe the following scenario. Suppose you have a bunch of particles that you throw at one another... smash them together. Stuff happens. Scattering amplitude is the object that describes the probability for a particular type of attraction. It turns out in quantum field theory that if you have a particular force and you're able to compute the n-point amplitudes... then you know everything about the theory.

</details>

### 胶子之谜：AI 如何通过线性化简化复杂系统

Alex 与 **Andrew Strominger** 等顶级物理学家合作，利用 AI 挑战了一个传统物理学中的“定论”。长期以来，物理学教科书认为**单负螺旋胶子树振幅**（Single-minus gluon tree amplitudes）应该是零，即这种特定交互在自然界中是被禁止的。然而，科学家们意识到在特定条件下（如粒子对齐的共线情况）存在漏洞。物理学家 Alfredo Guevara 曾试图通过手算来破解它，但计算量呈**阶乘增长**（Factorial growth: 随着粒子数量增加，复杂度爆炸式上升），导致六粒子情形下的公式极其臃肿。令人惊叹的是，**GPT-5.2 Pro** 不仅发现了极其简洁的简化形式，将复杂度降低到了**线性增长**（Linear growth），还独立发现了证明该结论的三步逻辑。这一发现类似于 80 年代著名的 Parke-Taylor 公式，彻底颠覆了人们对胶子交互的认知。

<details>
<summary>Original English Source</summary>

The title says single minus gluon tree amplitudes are non-zero. Gluons are the particles that carry the strong force. Single minus... single minus amplitudes. It's been known for a long time that actually in that case, the amplitude is just zero. Which means the interaction is forbidden and cannot happen. Andy, David and Alfredo understood a year ago that this statement is not exactly correct because the usual argument in the lecture notes and textbooks has a loophole... in a certain regime where the particles are exactly aligned, we say they're collinear. Alfredo did a lot of really hard work to compute these things by hand. By the time you get to six terms, it explodes in your face. 32 terms. But ChatGPT... it says, "Hop. Yep, simplifies to this." And we thought, "Whoa, okay. That is really nice." Instead of 32 terms, it reduces to just four terms. It's not a sum... it's a product. The amazing thing is that the formula that it proposed, instead of having this factorial growth which is super exponential... here it's actually linear. It's the nicest possible behavior you could imagine. This is the equivalent of the Parke-Taylor formula.

</details>

### 引力加速：从胶子到引力子的跨学科飞跃

在胶子研究成功三周后，AI 又在**引力子**（Graviton: 假设的引力量子）领域实现了类似的突破。引力子的计算比胶子复杂得多，因为它们具有自旋 2（Spin-two）的数学特性。Alex 仅用两个段落对 **GPT-5.2 Pro** 进行引导，提供胶子论文作为“锚点”，并鼓励模型扮演“天才理论物理学家”。模型思考了 30 分钟后，竟通过应用**定向矩阵树定理**（Directed matrix tree theorem）完成了极其困难的引力振幅推导。人类物理学家花费了绝大部分时间来验证 AI 给出的答案，而非进行计算本身。这一过程表明，AI 能够进行“概念性跳跃”，将一种物理力的洞察迁移到另一种完全不同的力中。

<details>
<summary>Original English Source</summary>

We wrote this paper which is called single minus graviton tree amplitudes are non-zero. It came out three weeks after the first one, which is really fast. I think this is a great example of AI accelerating science. Most of the time was spent verifying the answer, not writing, which is insane. We gave it the gluon paper as a seed. We said, "Read and understand the paper... generalizations to the gravity case." GPT Pro was able to do the graviton calculation, which is really different mathematically. There's a crucial application of something called the directed matrix tree theorem. We're like, "Whoa, that's really cool. We hadn't thought of that." From section three onwards, it's pretty much very close to what the AI wrote. All the math was derived by ChatGPT Pro.

</details>

### 范式转移：AI 时代的科学教育与 “侦察兵” 模式

AI 的介入正迫使学术界重新思考人才培养模式。过去，研究生需要通过繁重的计算积累自信，但现在这些任务已被 AI “秒杀”。Alex 认为，AI 现在是他最好的老师和**科研侦察兵**（Scout: 快速探索未知领域的探路者）。他可以同时启动 10 个对话，让 AI 探索不同的计算路径，从而快速筛选出有潜力的方向。这大大缩短了他处于“困惑状态”的时间。他强调，未来的核心竞争力将不再是计算能力，而是**提出正确问题的品味**（Taste for asking the right questions）。就像顶级教授知道如何分配任务给学生一样，研究者需要掌握引导 AI 的艺术，从而获得“AI 超能力”。

<details>
<summary>Original English Source</summary>

How do we train the next generation? Because the way we were trained is by going through these difficult rites of passage where you have to do these really arduous calculations. These models can probably crush these problems. AI can totally help you with that. It's the best teacher and knows everything. There's two key ways in which my research is completely changed. One is that I spend much less time being confused. With GPT, the amount of time you spend confused just dramatically shrinks. The other is that you can launch 10 instances of chat and have each one try a different route and send it as a scout that moves very fast into the unknown. AI right now is a very good physicist, but one of the things that it doesn't quite have yet is knowing what is the right question to ask. The difference between a good physicist and a great physicist is knowing what is the right question to ask.

</details>

### 终极愿景：打破学术论文瓶颈与 AI 驱动的发现奇点

Alex 提出了一个激进的观点：传统的学术论文可能已成为科学进步的瓶颈。撰写、投稿、同行评审的周期（通常为 6 个月以上）与 AI 驱动的“一天一篇论文”的速度极度不匹配。他设想未来的论文应该是**交互式文档**（Interactive documents），内置大型语言模型，读者可以随时向模型提问以展开复杂的逻辑细节。尽管目前的 AI 在面对数十年未解的社区难题时尚未展现出完全的独立性，但随着智能规模的持续扩大，这一天终将到来。我们正在进入一个必须提高“好论文”标准的时代，利用 AI 的超能力去攻克诸如**量子引力**（Quantum Gravity）等人类最深邃的未知领域。

<details>
<summary>Original English Source</summary>

I spend so much of my time writing papers... it just feels like not the right way somehow to store and communicate knowledge. The huge bottleneck is writing it up. If you ask me would I be confident that in 20 years we'll have these sort of like static documents in which we publish our results as papers, I would think not. Maybe some kind of interactive paper which lives in some LLM. We haven't seen an AI yet solve a question that stumps an entire community of physicists for decades. That hasn't happened yet. But I think given the trajectory that we're on, at some point hopefully not too far in the future we should see that. I think we should just raise the bar for what it means to write a good paper. Like we should aim higher basically.

</details>