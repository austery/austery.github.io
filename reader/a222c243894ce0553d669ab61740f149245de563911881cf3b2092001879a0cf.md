---
author: Dwarkesh Patel
date: '2026-05-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=X_ZVSPcZhtw
speaker: Dwarkesh Patel
tags:
  - reinforcement-learning
  - monte-carlo-tree-search
  - automated-science
  - computational-complexity
  - test-time-scaling
title: 从零构建 AlphaGo：Eric Jang 深度解析 AI 搜索、强化学习与自动科研的未来
summary: 前 DeepMind 研究员 Eric Jang 详细讲解了如何从零开始构建 AlphaGo，深入剖析了蒙特卡洛树搜索（MCTS）、策略与价值网络以及强化学习的核心机制。对话探讨了 AI 如何通过模拟压缩计算复杂度，并对比了 LLM 的 RL 训练与 AlphaGo 的不同。最后，Eric 分享了利用 LLM 自动化科学研究的实践经验与未来展望。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Eric Jang
companies_orgs:
  - Google DeepMind
  - 1X Technologies
  - Jane Street
  - Prime Intellect
products_models:
  - AlphaGo
  - KataGo
  - AlphaZero
  - MuZero
  - AlphaFold
  - AlphaTensor
media_books: []
status: evergreen
---
### 为什么在休假期间选择重构 AlphaGo

**[Host]**: 今天，我邀请到了 **Eric Jang**。他最近担任 **1X Technologies** 的 AI 副总裁，此前曾是 **Google DeepMind Robotics**（现 DeepMind）的高级研究科学家。在过去的几个月里，你一直在休假，而你做的一件事就是重新构建、改进并破解 **AlphaGo**。今天，你将向我们解释如何从头开始构建 AlphaGo，以及它对未来 AI 研发的启示。在进入正题之前，为什么 AlphaGo 如此有趣？为什么你选择在休假期间做这个项目，而不是在沙滩上放松？

<details>
<summary>Original English</summary>

**[Host]**: Today, I'm here with Eric Jang, who was most recently vice president of AI at 1X Technologies, and before that, senior research scientist at what is now Google DeepMind Robotics. You've been on sabbatical for the last few months. One of the things you've been doing is rebuilding, improving, and hacking on AlphaGo. Today, you're going to explain building AlphaGo from scratch and what it tells us about the future of AI research and development. Before we get to that, why is AlphaGo interesting? Why is this the project you decided to do on sabbatical rather than just hanging out at the beach?

</details>

**Eric Jang**: 我喜欢创造东西，而 AlphaGo 和**围棋 AI** 是真正让我进入这个领域的契机之一。当我看到 2014 至 2016 年间 AlphaGo 的早期突破时，看到 AI 系统能变得多么聪明，以及它们能通过**深度学习**解决什么样的计算复杂度问题，我感到非常震撼。长期以来，人们一直认为围棋是一个搜索无法解决的难题，但它却被深度学习攻克了。这对我来说非常神秘，我一直想更好地理解这一现象。

我的背景是机器人领域的深度神经网络，在那里神经网络做出的决策更直观。但 AlphaGo 是一个决策源于极深度搜索的问题。对我来说，一个十层的网络如何能摊销（amortize）游戏树中如此深度的模拟过程，始终是一个谜。

如果你画出多年来构建强力围棋机器人的计算量，你会发现 2020 年有一个由 **Jane Street** 的 David Wu 开发的开源项目 **KataGo**，它实现了将从零（tabula rasa）训练一个极强围棋机器人所需的计算量减少了 40 倍。由于 **LLM 代码生成**的出现，过去 DeepMind 整个研究科学家团队花费数百万美元研发和计算才能完成的工作，现在只需花费几千美元租用计算资源就能完成。

<details>
<summary>Original English</summary>

**Eric Jang**: I like making things, and AlphaGo and Go AI is one of those things that really got me into the field. When I saw the early breakthroughs on AlphaGo in 2014, 2015, 2016 and so forth, it was profound to see how smart AI systems could become and the computational complexity class they could tackle with deep learning. This is a problem that has long been understood to be intractable for search, and yet it was solved through deep learning. That was quite mysterious to me, and I've always wanted to understand that phenomenon a little better. My training is in deep neural nets for robotics, where the decisions made by the neural networks are a bit more intuitive. But AlphaGo is a problem where the decisions are the result of a very, very deep search. It's always been very mysterious to me how a ten-layer network can amortize the simulation of something so deep in the game tree. If you plot out how much compute it took to build various iterations of strong Go bots over the years, you can see that in 2020 there was an open-source project called KataGo by David Wu from Jane Street, which achieved a 40x reduction in the compute needed to train a really strong Go bot tabula rasa. Thanks to LLM coding, what took a whole team of research scientists at DeepMind and millions of dollars of research and compute can now be done for a few thousand dollars of rented compute.

</details>

### 围棋规则与计算属性

**[Host]**: 我们首先应该讨论一下围棋是如何运作的。这个游戏是怎么玩的？

<details>
<summary>Original English</summary>

**[Host]**: We should first discuss how Go works. How does the game work?

</details>

**Eric Jang**: 围棋是一个非常简单的游戏，可以很快在计算机上实现。目标是放下黑白棋子，尝试占据尽可能多的领土。黑棋总是先走。捕获对手棋子的方法是，对于每一个交叉点，如果你能用你的棋子围住它所有的四个邻居，那么它就被切断了“氧气”，成为死棋。

围棋规则在中国规则、日本规则和所谓的 **Tromp-Taylor 规则**之间存在细微差异。Tromp-Taylor 规则旨在完全消除歧义，因此所有的围棋 AI 都会针对该规则进行训练和结算。在普通围棋中，人类玩家不允许进行“自杀”步，但在 Tromp-Taylor 规则中这是可以的，棋子放下后会立即被判定死亡，所以结果是一样的。

围棋之所以优美，是因为你可以输掉局部的战斗，但赢得整场战争。随着棋盘尺寸的增大，这种微观与宏观动态的复杂性会变得更加有趣。

<details>
<summary>Original English</summary>

**Eric Jang**: Go is a very simple game that can be implemented quickly and easily on a computer. The objective is to put down black and white stones and try to occupy as much territory as possible. Black always goes first. The way you capture an opponent's stones is that for every intersection, if you can surround all four of its neighbors with your stones, then it's cut off from oxygen, if you will, and it's a dead stone. There are slight variations between Chinese, Japanese, and what are called Tromp-Taylor rules. Tromp-Taylor rules are designed to be completely unambiguous, so this is what all Go AIs train and resolve against. In typical Go, when humans play, you're actually not allowed to put this white stone down here. It would be instant suicide. In Tromp-Taylor, it's actually fine. You put it down, and it immediately resolves to death, so the outcome is the same. This is what makes Go a beautiful game: you can lose the battle but win the war. As the board size increases, the complexity of these micro versus macro dynamics gets more interesting.

</details>

### 游戏结束与价值判断

**[Host]**: 游戏如何结束？

<details>
<summary>Original English</summary>

**[Host]**: How does the game end?

</details>

**Eric Jang**: 游戏在玩家选择认输或双方连续弃着（pass）时结束。关于如何判定胜负，人类和计算机有不同的处理方式。大多数人类看到某种棋型就知道黑棋已经完全包围了白棋，白棋没有活路，于是双方达成共识。

这种人类的共识映射到深度神经网络中，就是所谓的**价值函数**（Value Function）。人类玩家在落子时会隐式地运行一个神经网络，观察棋盘并评估胜率（p-win）。人类只需看一眼，就能通过结晶化的知识和经验，在几秒钟内判断棋盘是否可胜。

这给了我们一个启示：在围棋这类游戏中，有办法从根本上加速搜索过程。你可以训练一个价值函数来观察棋盘并快速结算游戏，而不需要搜索到极深的树深度。

<details>
<summary>Original English</summary>

**Eric Jang**: The game ends when either a player chooses to resign or both players pass consecutively. Those are the rules. We should talk about how you resolve scores between humans and how you resolve scores in computer Go, because there's some ambiguity in how humans evaluate this. Most humans would look at this board configuration and conclude that black has totally surrounded white, and white has no chance of life. This will map later to how we think about the deep neural network. You can think about humans as implicitly having a neural network called a value function that takes in a board state and evaluates p(win). The human glances at the board and knows, "I'm probably going to lose." They're essentially running a neural network that looks at a board and implicitly amortizes a huge number of possible game playouts. This gives us a hint that in games like Go, there are ways to radically speed up the search process. You can train a value function to look at a board and quickly resolve the game without playing out all of these trees to a very deep search depth.

</details>

### 蒙特卡洛树搜索 (MCTS) 的原理

**[Host]**: 现在帮我用 AI 攻克它。让我们了解 AlphaGo 实际上是如何运作的。

<details>
<summary>Original English</summary>

**[Host]**: Now help me crack this with AI. Let's understand how AlphaGo actually works.

</details>

**Eric Jang**: 围棋树极其庞大。在 19x19 的棋盘上，平均每步约有 361 种选择，一局棋大约 300 步。这意味着可能的结局数量级约为 $361^{300}$，远超宇宙中的原子总数。这就是为什么计算机科学家多年来认为围棋在本世纪是不可攻克的。

AlphaGo 的核心概念突破是使用神经网络使这个搜索问题变得可处理。我们使用**蒙特卡洛树搜索**（MCTS）。在每一步，AI 都会运行数千次模拟。每次模拟包含四个步骤：**选择**（Selection）、**扩张**（Expansion）、**评估**（Evaluation）和**回溯**（Backup）。

我们使用一种称为 **PUCT**（预测上置信度树）的准则来选择动作。它平衡了 Q 值（平均动作价值，即“开发”）和探索奖金（奖励尝试未曾走过的步法）。通过这种方式，我们可以在搜索过程中不断缩小搜索范围，只关注那些更有希望的路径。

<details>
<summary>Original English</summary>

**Eric Jang**: The number of steps in the game can be somewhere from 250 to 300 moves. If you keep on expanding possible moves, you end up with an enormous explosion in the possible game outcomes. This is something on the order of 361^300, which is far more than the number of atoms in the universe. AlphaGo's core conceptual breakthrough was using neural nets to make this search problem tractable. We use Monte Carlo Tree Search (MCTS). Every simulation involves this four-step process: selection, expansion, evaluation, and backup. In AlphaGo, they use a slightly different action-selection criterion called PUCT, short for Predicted Upper Confidence with Trees. Q(s,a) is the mean action value, how good a given child is on average. In both UCB and PUCT, there's this term that basically rewards taking actions you haven't taken before.

</details>

### 神经网络架构：策略与价值

**[Host]**: 让我们谈谈其中的神经网络部分。

<details>
<summary>Original English</summary>

**[Host]**: Let's talk about the neural network part of this.

</details>

**Eric Jang**: 这里有两个网络（或一个网络的两个头）：**价值网络**（Value Network）预测胜负概率，**策略网络**（Policy Network）给出优秀动作的分布。

在架构选择上，**ResNet** 在小数据量下通常优于 **Transformer**。这是因为卷积神经网络（CNN）提供了局部相关性的**归纳偏置**。然而，KataGo 的一个有趣发现是，在网络中聚合全局特征非常有用。Transformer 虽然有全局注意力，但需要更多数据来学习。

AlphaGo Lee（对阵李世石的版本）最初是用人类专家的棋谱进行**监督学习**初始化的。后来，AlphaZero 移除了这一限制，通过自我博弈从零开始学习。但我建议研究者总是从一个容易的初始点开始，先用人类数据训练一个模型，它已经能打败大多数人类了，然后再层叠搜索等复杂功能。

<details>
<summary>Original English</summary>

**Eric Jang**: There are two networks. There is the value network, which takes in a state and predicts, am I going to win or lose? Then we have a policy network, which induces a distribution over good actions to take. Transformers work, ResNets work. For small data regimes, my experience is that ResNets still outperform transformers and give you more bang for the buck at lower budgets. They provide the inductive bias of local convolutions. One interesting finding from the KataGo paper was that they found it quite useful to pool together and aggregate global features throughout the network. The original AlphaGo paper, called AlphaGo Lee, initialized this network with a supervised learning dataset of expert human play. Later, they removed this restriction by having the model teach itself how to play well. I find it super nice for implementation to always initialize your experiments to something easy and get the problem working before trying to bite off the whole thing and learn tabula rasa.

</details>

### 自我博弈与强化学习 (RL)

**[Host]**: 它是如何通过自我博弈变得更强的？

<details>
<summary>Original English</summary>

**[Host]**: We now talk about the RL part of how this thing gets stronger by playing itself.

</details>

**Eric Jang**: 核心思想是 MCTS 作为一个**改进算子**（Improvement Operator）。在每一手棋，MCTS 都会产生一个比原始策略网络更准确、更“尖锐”的动作分布。当游戏结束时，我们将 MCTS 的搜索结果作为新的标签，告诉策略网络：“嘿，下次不要让我费力搜索才得出这个结论，直接预测这个结果吧。”

这就像将 1000 步搜索的知识“蒸馏”回神经网络的单次前向传播中。这种训练非常稳定，因为它实际上是将 RL 变成了一个监督学习问题。

相比之下，目前 **LLM 的强化学习**通常使用策略梯度（Policy Gradient）方法，比如 **REINFORCE** 或 **PPO**。这就像“通过吸管吸取监督信号”。你必须跑完整个轨迹才能得到一个微弱的奖惩信号。而 AlphaGo 的方式可以在每一步都获得高质量的改进标签，这在计算效率上要高得多。

<details>
<summary>Original English</summary>

**Eric Jang**: The beauty of how AlphaGo trains itself is that it can actually take this final search process and tell the policy network, "Hey, instead of having MCTS do all this legwork to arrive here, why don't you just predict that from the get-go?" It's almost as if you could amortize the first 1,000 steps into the policy network instead of the search process. This is very related to DAgger in robotics and imitation learning. The inefficiency of policy gradient RL is that you have to roll out a whole trajectory to get any learning signal at all. In LLMs, they treat this entire sequence as a single action. AlphaGo is doing something very fundamentally different. It's not trying to do credit assignment on wins. It's trying to improve the label for any given action you took.

</details>

### AlphaGo 对计算复杂度的深刻启示

**[Host]**: 深入理解 AlphaGo 后，你是否觉得 2017 年的这一成就似乎没那么令人震撼了？因为你为它构建了非常明确的搜索树。

<details>
<summary>Original English</summary>

**[Host]**: If you understand it more deeply, AlphaGo seems less impressive in retrospect the more you understand it. You're building this very explicit tree search for it. I don't know if you share that intuition.

</details>

**Eric Jang**: 我完全不同意。我认为 AlphaGo 是深远的。最深刻的一点是：一个 10 层的神经网络（仅 10 步推理）能够通过单次前向传播，高度近似地解决一个近乎不可处理的搜索问题。

这挑战了我们对 **P=NP** 或计算硬度问题的理解。虽然它不是 P=NP 的证明，但它表明许多在最坏情况下不可解的问题（如蛋白质折叠、天气预测）实际上具有某种宏观结构，可以被神经网络捕捉。AlphaGo 是第一篇真正展示了如何将深刻的模拟过程压缩进少量计算中的论文。

<details>
<summary>Original English</summary>

**Eric Jang**: I personally disagree. I think they're profound for different reasons. I think the most profound thing here is that a 10-layer neural network pass is able to amortize and approximate to very high fidelity a nearly intractable search problem. This was a breakthrough that I think most people don't even fully comprehend today. It actually makes me wonder if our understanding of problems like P=NP, or these fundamental computational hardness problems, is incomplete. I wouldn't say this solves Go, but in practice, it is extremely useful. To me, AlphaGo was the first paper that really showed this profound level of simulation being compressed into a small amount of compute.

</details>

### 自动化科学研究的未来

**[Host]**: 听说你是通过自动化 LLM 编程助手完成这个项目的。你对自动化科研有什么观察？

<details>
<summary>Original English</summary>

**[Host]**: One thing I really wanted to talk to you about is that you did a bunch of the research for this project through this automated LLM coding assistant loop. What are your observations about what the AI is good at?

</details>

**Eric Jang**: 目前的 AI（如 **Opus 4.6**）在超参数优化和执行具体实验方面非常出色。我可以写一个名为“实验”的技能（Skill），描述我想要绘制的图表，它就会跑去运行实验、生成报告并分析原因。

但它们目前还不擅长**横向思维**（Lateral Thinking）。它们很难跳出当前的轨道，反思“这个思路从根本上就不对，我们应该回到第一原则”。

围棋是一个极好的自动化科研试验场。它的外部循环非常明确（胜率），但内部循环涉及复杂的工程问题。如果我们能训练出一个能在围棋这类环境中自主发现规律的 AI 科学家，那么这种能力就能迁移到药物研发或机器人技术中。

<details>
<summary>Original English</summary>

**Eric Jang**: I think automated scientific research is one of the most exciting skills. What works is that the models can do a very good job of hyperparameter optimization. It is also fantastic now at basically executing any experiment. But they don't seem to be that great at stepping back and do the lateral thinking. Often I had to catch infra bugs myself. Go captures a lot of very interesting research problems. You can check the outcome of a Go game quite easily. Once you acquire these skills, maybe you can apply them to other domains like biosciences or robotics. Or automating AI research.

</details>

### 总结与展望

**[Host]**: Eric，感谢你的分享。大家可以去哪里了解更多？

<details>
<summary>Original English</summary>

**[Host]**: Awesome, Eric. Thanks for doing this. Where do people go next?

</details>

**Eric Jang**: 我的网站是 `evjang.com`，上面有交互式教程。在我的 GitHub（`ericjang`）上有一个 `AutoGo` 仓库。我还强烈推荐大家阅读我的博文 **《石头也思考》**（As Rocks May Think），探讨思考如何成为一种计算原语。

<details>
<summary>Original English</summary>

**Eric Jang**: My website is evjang.com. On my GitHub, there's an AutoGo repo. I also highly recommend people check out this blog post, "As Rocks May Think." Thank you. It's an honor to be on the podcast.

</details>