---
author: Peter Pang
date: '2025-12-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=a_8Y8nHJCCg
speaker: Peter Pang
tags:
  - monte-carlo-simulation
  - computational-power
  - probability
  - chaos-theory
  - scientific-computing
title: 蒙特卡洛模拟：驾驭不确定性，暴力破解科学难题
summary: 本视频深入浅出地介绍了蒙特卡洛模拟这一颠覆性的算法。从计算机算力局限及宇宙不确定性出发，阐述了该算法如何通过大量随机模拟来近似复杂过程的结果，并追溯了其在核武研发中的起源。视频通过抛硬币、掷骰子、打扑克等实例，直观展示了蒙特卡洛模拟在统计学上的应用及其随算力提升而增强的威力。最后，文章探讨了该算法在量子物理、金融乃至图形学（光追、DLSS）等广泛领域的强大通用性，强调了其作为“暴力破解”科学难题的价值。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books:
  - 《三体》
status: evergreen
---
### Uncertainty's Challenge

计算机自发明伊始，其**计算能力**就经历了爆炸式增长，犹如坐上火箭般飞速发展。然而，无论**算力**多么强大，终究是有限的，在浩瀚无垠的宇宙面前，不过是沧海一粟。真正限制我们的，并非宇宙之大，而是它固有的**不确定性**。

看过《三体》的观众想必能深刻理解**混沌理论**（Chaos Theory: A branch of mathematics and physics that deals with complex systems whose behavior is highly sensitive to initial conditions.）的威力：微小的初始误差会被指数级放大，导致计算结果与真实情况产生天壤之别。面对这一挑战，一位天才提出了一个绝妙的构想：如果过程难以精确计算，不如绕过过程本身，直接模拟结果。通过进行大量的随机模拟来获取海量数据，再从统计学角度寻找最接近真相的答案。这便是**蒙特卡洛模拟**（Monte Carlo simulation: 通过大量的随机模拟获得大量的数据，再从统计学的角度找到最接近真相的答案），它被誉为现代科学史上最“赖皮”却也最有用的算法之一。

### Algorithm's Genesis

时间回到1945年，在美国成功试爆“胖子”和“小男孩”原子弹之后，**美国**立即着手更复杂的核武研发。然而，在计算原子内部能量释放的过程中，由于**不确定性原理**的影响，中子轨迹、原子核撞击的能量等关键参数都无法精确计算，研发工作因此陷入了瓶颈。

负责此项任务的物理学家**Ulam**，在一次家中打牌时，偶然想到可以用数学知识计算不同牌型的概率。他发现直接计算过程繁琐，不如直接发100次牌，然后统计出现的牌型，这样就能得到一个相当接近的答案。Ulam由此获得灵感，这种方法或许也能应用于他的科研工作。随后，他与**冯·诺依曼**（John von Neumann）合作，启动了一个秘密项目，项目代号就取自著名的**蒙特卡洛赌场**。借助世界上第一台计算机ENIAC，他们在1948年首次成功完成了对粒子运动的蒙特卡洛模拟，打破了计算瓶颈，为三年后引爆的第一个氢弹奠定了理论基础。

### Probability's Playground

如果核物理的专业性过于高深，令人感觉遥远陌生，那么**蒙特卡洛模拟**在**统计学**上的应用则极为平易近人。日常生活中，我们常玩的抛硬币、掷骰子、打扑克等，本质上都是概率游戏，都可以通过蒙特卡洛模拟获得精准的答案。

抛硬币出现正面的概率是多少？只需抛掷约100次，便可初见端倪。掷6个骰子恰好出现1到6点组合的可能性有多大？掷上1万次，便能明了。而一副牌开局直接发出同花顺的概率？恐怕需要进行1,000万次模拟，才能得出相对靠谱的结果。

### Computing Power Unleashed

万幸的是，正如Ulam当年所做的那样，我们可以借助**计算机**的能力，用编程代替人力进行模拟。我们以抛硬币为例，模拟了从100次到100万次不等的抛掷过程。在模拟过程中，正面出现的概率被实时绘制在图表上。

可以看到，随着模拟次数的增加，概率曲线在0.5附近上下波动。在100次和1,000次的模拟中，波动的幅度较大，且与理论上的“五五分”仍有一定距离。然而，从1万、10万到100万次的模拟曲线显示，模拟越深入，波动的幅度越小，曲线几乎与0.5的直线融为一体。在100万次模拟中，甚至需要将曲线图放大100倍才能勉强看出其波动轨迹。

这恰恰解释了一个关键问题：为何**大数定律**（Law of Large Numbers: A theorem that states that as the number of trials increases, the average of the results obtained from those trials will approach the expected value.）和**中心极限定理**（Central Limit Theorem: A statistical theorem that states that as the sample size increases, the distribution of sample means will approach a normal distribution.），这些在18世纪就已提出的数学理论，直到第二次世界大战结束后才催生出**蒙特卡洛模拟**这种具有实际应用价值的算法？答案并非等待算法本身，而是等待**算力**的出现。我们足足等待了200年，才等到第一台计算机的诞生，才第一次见证了量变引起质变的奇效。

### Solving Intractable Problems

一旦拥有了近乎“无穷”的算力，我们就能运用蒙特卡洛模拟，对那些原本需要复杂方程和推导的问题进行“无情”的**暴力破解**。回到前面提到的两个问题：投掷6个骰子出现1-6的概率有多高？开局发5张牌能发出同花顺的概率有多高？如果在概率学课堂上认真听讲并稍加思考，或许能写出正确的公式并算出答案。但现在，借助蒙特卡洛模拟，我们无需耗费过多脑细胞，只需通过代码构建整个游戏场景，简单模拟1,000万次，答案便会呼之欲出。

问题的复杂度越高，蒙特卡洛模拟的优势越发凸显。例如，计算同花与顺子的概率，其复杂度会略高于同花顺。虽然各位或许仍能写出正确的公式，但这将需要更多的时间和更仔细的推理。而通过代码模拟，我们仅需简单调整检查发牌结果的逻辑即可。这再次体现了蒙特卡洛模拟的核心价值：当问题的路径变长、维度增加时，依据原理推导的公式会日益复杂，计算量和难度也随之剧增。但通过模拟，我们只需将模拟场景搭建妥当，计算的难度和复杂度便能保持基本不变。

### Ubiquitous Algorithm

蒙特卡洛模拟的强大之处在于其**通用性**。只要存在大量符合规律的随机样本，就能确保样本具有足够的代表性，从而使模拟结果足够接近真实情况。因此，它能够被应用于攻克诸如**量子物理**、**流体力学**等因自然法则导致计算难度超出人类能力范围的问题。

它同样能解决那些因可能性过多、根本无法一一列举分析的**金融问题**，如衍生品定价、投资组合优化。对于那些因计算量过大、从时间和成本上都无法完成的问题，蒙特卡洛模拟也允许我们仅计算一小部分随机样本，便能获得足够准确的结果。

### Graphics & AI Synergy

最终，这种方法被广泛应用于大家熟知的**光追**（Ray Tracing: A rendering technique that simulates the physical behavior of light, producing photorealistic images.）和**DLSS**（Deep Learning Super Sampling: An AI rendering technology that boosts frame rates using dedicated Tensor Core AI processors.）技术中。试想一下，如果真的要计算显卡中的每个光源在每个物体上的每个像素的每一次折射，显卡的价格恐怕会再加一个零也不够。

最后，如果你希望亲手复现视频中的蒙特卡洛模拟，代码将会在Disco粉丝群中分享。那么，最后的最后，让我们“make simulation great again”，拜拜！