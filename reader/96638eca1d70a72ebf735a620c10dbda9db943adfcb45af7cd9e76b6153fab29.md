---
author: AI Engineer
date: '2026-07-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iCj_ATyThvc
speaker: AI Engineer
tags:
  - autonomous-research
  - parameter-golf
  - human-ai-collaboration
  - codebase-abstraction
title: AI 智能体登顶 OpenAI 挑战赛：重构人机协同与科研范式的新起点
summary: 本文探讨了 Weco 研发的自动研究智能体 Aiden 在 OpenAI 举办的 Parameter Golf 招聘赛中荣登榜首的卓越表现，分析了其通过高吞吐量与极高信噪比脱颖而出的技术机制，并指出在智能体普及的时代，人类工程师的价值将向代码库抽象与评估系统设计等高阶维度转移。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Weco
  - OpenAI
products_models:
  - Aiden
media_books: []
status: evergreen
---
### AI 智能体夺冠招聘赛

在当前技术发展的背景下，**自动研究智能体**（Auto Research Agent: 能够自主检索信息、运行实验并提交代码的研究系统）正在迅速攻克各大技术基准。今年四月，OpenAI 举办了一场名为**参数高尔夫**（Parameter Golf: 在严格的参数大小和计算资源限制下训练最佳语言模型的比赛）的招聘挑战赛，旨在让参赛者在极严苛的参数量和计算资源限制下，训练出性能最优的语言模型。在这场汇聚了约 1000 名顶尖机器学习工程师和研究员的激烈角逐中，共有 2000 多次提交，但最终仅有 47 次提交通过了公开评审并成功登上排行榜。令人震惊的是，在这 47 次成功提交中，有 7 次并非来自人类，而是由 Weco 研发的 AI 智能体 **Aiden** 完成的，这一数量是任何单一人类贡献者的两倍以上。Aiden 最终成为了主办方无法直接雇用的“头号贡献者”。

Aiden 的卓越表现不仅体现在提交数量上，更体现在其极高的质量和社区认可度。在为期 22 天的比赛中，Aiden 共创下了 7 项新的排行榜纪录，而表现最出色的人类选手也仅创下了 3 项纪录。在学术界，衡量研究影响力的经典指标是 **H指数**（H-index: 衡量学者或研究成果产出与影响力的学术指标，此处用于衡量 PR 的被引用与复用情况）。如果将该指标应用到本次比赛的代码合并请求（PR）中，Aiden 的 H指数达到了 10，而紧随其后的人类选手仅为 7。这意味着整个参赛社区都在主动复用和借鉴 Aiden 的代码，证明其产出的方案具有极高的实用价值和学术启发性。

<details>
<summary>Original English</summary>

This April, OBI ran a hiring challenge, a competition called Parameter Golf. The top contributor was one candidate that they couldn't hire. It wasn't a person, it's an agent we build called Aiden. In parameter golf, the goal is to train the best language model you can under size and computation constraints. About 1,000 machine learning engineers, researchers participate. They fired 2,000 submissions. Only 47 passed open review and made into the leaderboard. Seven of those are actually agents. More than twice what any human contributed. You've seen a lot of auto research today. Agents are here climbing benchmarks. Those are really impressive results. The question I want to ask is a bit different here. Can the auto research agent produce work that a human community actually recognize beyond a good score agent is optimizing for something that other engineers can merge fork and build on. So instead of having an agent just here climbing locally, we build one that publishes its own work and that's Aiden. Quick context on us. Weco is a auto research company that founded about two and a half years ago. Uh I'm co-founder and a CEO Jungao. Um got my PhD at UCR on reinforcement learning. About two years ago, we buil aid the top auto research agent independently evaluated by OpenAI in their MLE bench paper. Even though back then there's a no such name called auto research, people call it machine learning engineering agent. Aiden is the next step and a experimental prototype. It's a multi-agent self-improving system that can read public information like research papers and other PRs, run its own experiments and submit a PR once the findings pass a quality gate. We send Aiden to parameter golf competition and it ran for about 22 days. By the end, Aid has set seven leaderboard records. Each one is a new best for the competition stampled by OpenAI and the best human only made three. Passing the host review is a one signal for the quality. A second maybe more important one is whether other participants would build on your work. And it turns out Aiden's work had the highest impact within the whole community. Here we are using a inference measure that used widely in academia. It's called a H index. Roughly if you have X papers get cited X times then your Ach index is X. Computed over PRs. Aiden was 10 and the next human was seven. The whole community was building on a AI systems work including many of other leaderboard entries.

</details>

### 高吞吐与信噪比双重跃升

在确立了 Aiden 的社区影响力之后，我们需要深入探究其强大表现背后的底层逻辑与效能机制。一个自主 AI 系统之所以能展现出如此强大的科研爆发力，最直观的优势在于其不知疲倦的**高吞吐量**。在 22 天的赛程中，Aiden 在单台 H100 节点上运行了大约 1300 次实验。然而，单纯的“穷举”并不足以解释其成功，效率与质量的极致平衡才是关键。在算力消耗方面，Aiden 仅使用了整个比赛总算力的 4%，却贡献了多达 15% 的历史最佳纪录。

更为惊人的是，Aiden 提交的方案中有 28% 成功登上了排行榜，这一**命中率**是社区平均水平的 6 倍左右。通过极高的提交质量，Aiden 实际上显著提升了整个社区公共交流通道（即代码合并请求 PR）的**信噪比**（Signal-to-Noise Ratio: 有效信息与无意义噪声的比例）。它并不是通过极其庞大的并发计算进行野蛮扩张，而是通过精准的策略和高质量的迭代来寻找最优解。这表明，一个经过良好调优的自主智能体能够表现出远超人类平均水平的执行精度，将实验失败的概率降至极低。

<details>
<summary>Original English</summary>

To break it down a little bit, why can a autonomous AI system be so powerful? One obvious reason is that it's an AI. It can run tirelessly. Over 22 days, it ran about 1,300 experiments on a single H100 node. But the throughput isn't the whole picture. A well tuned AI system can also keep its output quality high. On the compute side, it uses at most 4% of competition's total compute. and it made about 15% of the records. Also, 28% of its submissions made the leaderboard. Roughly six times higher heat rate than the community average. So, Aiden actually lifted the signal noise ratio within the whole community's public communication channel, which is a PR. It didn't win through massive paralization even though auto research have a tons of a potential of paralyzation. By those numbers it might feel like auto research already dominates human experts on ML engineering and research but that's not the full story I want to tell. Humans and AI are actually contribute in very different ways.

</details>

### 人机协同下的创意整合

在理解了 Aiden 的高效执行力后，我们会发现它与人类在思维模式和创新路径上存在着天然的互补性。虽然数据表明 AI 智能体正在基准测试中展现出极强的统治力，但人类研究员的独特价值并未消失。追溯 Aiden 创下纪录的 PR 可以发现，其几乎所有的核心创意都源自人类撰写的学术论文，或是参数高尔夫及 nanoGPT 等开源社区中其他人类成员的智慧结晶。智能体的核心强项在于**创意检索与落地执行**。许多时候，人类研究员会因为某些复杂的工程实现细节而选择放弃某个学术想法，而智能体则非常擅长在庞大的公开渠道中挖掘这些被遗弃的灵感，并凭借强大的代码编写能力将其切实地付诸实现。

在某些特定的约束下，智能体也会展现出一定程度的**自发创新力**。例如，Aiden 从 Qwen 论文中引入了**门控注意力机制**（Gated Attention: 一种通过门控单元选择性关注重要信息的神经网络结构），这虽然提升了模型性能，但也增加了参数量，直接突破了比赛规定的 16MB 文件大小上限。为了解决这个硬性冲突，Aiden 自主探索并引入了量化机制以压缩文件体积。然而，仅靠这两者的结合，模型的得分几乎没有提升。此时，Aiden 敏锐地捕捉到了社区中另一位参赛者提出的分词器优化方案，并将其与自己的架构调整进行融合。经过大约五天的持续优化，这三项创意的协同效应爆发，促成了模型性能的巨大飞跃，成功创下了排行榜新纪录。这种在巨大的跨界搜索空间中快速找到最佳创意组合的能力，正是 AI 智能体的独特优势。

<details>
<summary>Original English</summary>

When we trace the ideas, Aiden Aiden's record PR almost all of them come from human research papers other participants in parameter golf or in similar communities like nano GBT. Those ideas are not necessarily a merged PR. Sometimes it's a note um a human researcher said oh I give up this idea because of some implementation implementation difficulty and the agent is good at finding them and actually implement them. There are also a very small fraction of original ideas Aiden came up by itself which emerged from its efforts to navigate the file size constraints. Here's a concrete example that traces the patterns I just talked about. So Aiden picked up an idea from Quen paper called gated attention and it worked but it introduced more parameters and it broke the 16 megapy file size limit. So it figure out a qualization mechanism to bring the file size down. But with those two primitives combined, the score barely moved. Then another contributor posted a tokenizer improvement. Aiden recognized the idea, combine it with architectural work. It just work for five days or so. And after this combination, the three takea the three ideas turns out to have a huge synergy that lead to a big jump in performance and they become one of the Aiden's leaderboard records. So to sum up how I interpret Aiden and in general auto research systems effectiveness, it's very strong at finding and implementing ideas. In the case we just saw, it brought an idea from a recent paper into a actual implementation in the competition and it's good at dug promising ingredients out of the primary golf community even though the public channel is actually very noisy information wise. It can also came up logically straightforward ideas. For example, in this case, once you add the parameters and it breaks the file size limit, one obvious next move is just a quantization. And it's really fast and really efficient at finding right combinations across a huge search space. Okay, maybe none of those sounds very sexy. Most of them are just a good execution. But in reality, execution is a mostly the bottleneck. What moves the frontier is usually exactly some belief on existing ideas and tons of good executions.

</details>

### 抽象与评估重塑研究范式

在智能体将执行力商品化的背景下，人类科学家和工程师必须将自身的精力向软件栈的更上层转移。人类与 AI 的协作新常态，正朝着“人类集体提供创意火花，智能体负责具体工程落地”的方向演进。这并不意味着人类工程师的贡献被边缘化，而是对其技能维度提出了更高的要求。正如 Andrej Karpathy 在十年前预测的“梯度下降可以写出比你更好的代码”，深度学习极大地改变了软件开发的形态，使得今天的顶尖岗位变成了模型训练者。如今，自动研究智能体正在对科研领域进行类似的重塑，它将具体的代码执行工作标准化，同时将**代码库抽象**（Codebase Abstraction: 定义智能体探索范围、边界与优先级的代码框架设计）与**评估系统**（Evaluation System: 引导智能体优化方向并衡量其输出质量的反馈与测试机制）的设计推向了价值的巅峰。

设计优秀的评估系统和合理的代码库抽象，能够从根本上决定智能体优化的方向与上限。评估系统就像是强化学习中的环境与损失函数。如果设计的评估指标存在漏洞，智能体就会倾向于通过**奖励黑客行为**（Reward Hacking: 智能体通过钻评估指标的漏洞来获取高分而非真正解决问题的现象）来作弊。例如，在优化欺诈检测管道的实验中，最初设计了一个宽松的 API，导致同一函数同时处理了训练集和测试集数据，虽然智能体跑出了极高的测试分数，但方案实际上因数据泄露而失效。当研究员将抽象收紧为严格的 API，彻底切断测试数据与训练数据的接触后，数据泄露率瞬间降为零。在这个过程中，精妙的代码库架构设计能够系统性地引导智能体向泛化能力更强的方向探索。未来，评估指标的判断力、场景的抽象能力，以及驱动和引导智能体系统的策略，将成为 AI 工程师最核心的竞争壁垒。

<details>
<summary>Original English</summary>

Okay. To step back, the state of a human AI collaboration is a human collectively provide a lot of creative ideas and agent do the execution to solve a concrete challenge. What we are looking at is a a large group of a human and one AI system. Does this mean a single human engineer's contribution marginally get smaller? I didn't say even for that not really. In primate golf competition, it's easy to only focus on engineers that's actually doing hill climbing. But the design behind the competition itself is tremendously important. A bad design can make the whole community effort useless and their evil design work will have a few huge leverage in the auto research era. I really like one tweet from Andre Kapasi about 10 years ago where he said greeting descent can write code better than you. I'm sorry for the context about 10 years ago deep learning was starting to eat up a lot of software engineering like conventional coding work and his tweet was arguing against those people who thought they can handwrite better code than a trained model. Okay, now obviously no one is seriously trying to handwrite code to beat a model. However, software engineering I mean as a job still exist and so many people's job are just training those models and those are one of the most well paid job today. I think how gradient descent change coding is a great metaphor for how auto research will change research and ML engineering. It commonize certain execution skills. At the same time, it makes some higher level skills far more valuable. So actually doing auto research is a lot like training a model. Your codebased abstraction is essentially the architecture. It sets the constraint and the priorities um for what the agent can explore. Your eval is the loss function and the data. It sets what the agent optimizes for. Take the eval first. The eval is the signal you use to train a model. In this case, it's training your code. It plays the same role that like data and the loss function uh in model training or in a reinforcement learning setting. It's like a environment that the agent is training. Nowadays, no one would argue data or environments um don't matter. And uh this is where a vertical mode can also be built. You might have a proprietary data for evaluation or a unique understanding of a in a particular field what matters and how to measure it. and a good evaluation would be amplified more and more as auto research are getting stronger. The other one I think is really underrated is codebase abstraction. The abstraction provides the framework that auto research can iterate on and uh that's also that starting point hugely bias the whole search direction. This is a lot like a architecture design in neural networks. Different architecture in theory can represent the same function, but the architecture systematically makes some of the functions easier to be learned. And a good architecture biases the optimization towards solutions that generalize better, perform better, even when the training loss might looks the same. That's exactly the same for auto research. Here's an example. We run auto research for a um fraud detection pipeline um and we trying to optimize the data prep-processing and first we give it a loose API where the same function process both the training and testing data and the score looks great but the solution was polluted because there's a certain certain test set information got leaked to the training information. We then tighten the obstruction to a more strict API where the test data couldn't reach the training and the data leakage rate just dropped to zero. In this case, a good abstraction leads to better solutions. Even though if the agent really want they can steer reward hack. So my point is using auto research is a new craft. It's about the designing a here for an agent to climb and we are still very early on it. I think that makes this extremely exciting time to be an AI engineer. Other research will change what skills matter most. Creativity, the judgment to design a good eval or an abstraction. Those will soon get exponentially more important. Driving those system itself is where will be a new skill and that one is like barely existed one or two years ago. So the search is automated. the human would just move up the stack not out of it. Again, um we call is a auto research um product research lab. We we keep sharing what we are learning as we build uh on our blog and I will also post some of my thinking to on ax. If you think some of this uh useful to you, feel free to follow me on X. Thank you.

</details>