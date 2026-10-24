---
author: Best Partners TV
date: '2026-04-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=m17jqrqBZSc
speaker: Best Partners TV
tags:
  - ai-evolution
  - scientific-discovery
  - prompt-engineering
  - human-ai-collaboration
  - evolutionary-algorithms
title: 大语言模型如何实现自我进化：Shinka Evolve的深度解析
summary: 本文深度解析了日本AI初创企业Sakana AI开源的Shinka Evolve框架，该框架融合大语言模型与进化算法，旨在解决AI的效率和自主发明问题。通过借鉴AlphaEvolve的经验并结合《伟大无法被规划》等理念，Shinka Evolve在样本效率、多模型集成（UCB）、语义层面探索等方面取得关键突破，并提出了未来“氛围研究”愿景，强调人机协作在科学发现中的作用。报告探讨了AI作为人类能力放大器的潜力，以及在AI时代人类工作角色的演变。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Robert Lang
companies_orgs:
  - Sakana AI
  - Google DeepMind
products_models:
  - Shinka Evolve
  - AlphaEvolve
  - GPT-5
  - Sonnet 4.5
  - Gemini
media_books:
  - 《伟大无法被规划》
status: evergreen
---
大家好，这里是最佳拍档，我是大飞。今天我们将深入探讨一个前沿话题：**大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）能否实现自我进化？日本AI初创企业**Sakana AI**开源的**Shinka Evolve**框架，正是这一理念的实践者。它深度融合了大语言模型与进化算法，构建了一个具备**开放式程序搜索**（Open-ended program search: AI自主探索和生成解决问题的程序）能力的系统，显著解决了过去**谷歌DeepMind AlphaEvolve**（Google DeepMind AlphaEvolve: 一个早期用于代码生成的进化算法系统）系统的核心痛点。Shinka Evolve不仅让AI能够解决固定问题，更迈出了**自主发明问题并解决**（Self-inventing and solving problems: AI主动发现新问题而非仅解决已知问题）的关键一步。

### 进化突破：效率与创新
Shinka Evolve的研发深受**AlphaEvolve**的启发，其负责人**Robert Lang**在一次播客访谈中详细阐述了设计理念。尽管AlphaEvolve成果斐然，但其核心效率问题在于，为解决特定任务需要采样上千个程序进行评估，这导致了高昂的计算成本和评估时间。Shinka Evolve的首要目标就是通过技术创新，大幅提升进化式搜索的**样本效率**（Sample efficiency: 用更少的计算资源或评估次数达到同等或更好的效果），即用更少的程序评估实现更好的求解效果。在经典的**圆堆积问题**（Circle packing problem: 一种经典的几何优化问题，目标是将圆紧密地排列在给定区域内）上，Shinka Evolve以极少的评估次数超越了AlphaEvolve的经典结果，验证了其在效率上的巨大提升。

### 创新源泉：发明新问题
AlphaEvolve作为一款进化式编码Agent，其局限在于专注于为给定固定问题优化解决方案。然而，在真实的科学研究中，真正的创新往往源于**发明新问题**（Inventing new problems: 创造全新问题以驱动技术或理论的突破），而非直接解决已知问题。现有AI系统普遍缺乏这种**递归式问题解决能力**（Recursive problem-solving: 能够通过解决一系列关联问题来达到最终目标的能力），而这恰恰是人类科学创新的核心。正如肯尼斯·斯坦利和乔尔·雷曼在《**伟大无法被规划**》（The Greatness Cannot Be Planned: 一本书，探讨了非定向探索在实现伟大成就中的重要性）一书中提出的观点：直接为既定目标优化并非实现伟大成就的最佳方式。自然进化也是如此，物种通过尝试各种可能性，看似无用的变异可能成为未来进化的基石。机器学习算法的一大短板在于无法处理“未知的未知”，而这正是科学创新的核心源泉。

### 理论启示：POET与PowerPlay
为了解决AI无法自主发明新问题、也无法从看似无关的问题中找到线索的困境，Robert Lang提出了从**POET**（Paired Open-Ended Trailblazer: 一种通过环境与Agent配对协同进化实现自动课程学习的理论）和**PowerPlay**（PowerPlay: 一种形式化学习者需为自己发明更难任务以避免停滞的思想）这两个经典理论中寻找灵感。POET通过环境与Agent的配对协同进化，实现自动课程学习，不断生成难度递增的环境让Agent进化。PowerPlay则强调学习者需要主动发明更难的任务以避免停滞。这两个理论最初应用于强化学习，但其核心思路——**问题与解决方案的协同进化**（Co-evolution of problems and solutions: 问题和解决方案相互促进、共同发展的过程）——可以拓展到通用科学领域，只要存在可运行评估的模拟器。

### 关键挑战与解决方案
尽管有理论支持，但大语言模型在自主运行时往往难以产生有价值的创新，甚至可能仅停留在对初始条件的表面重组。Robert Lang用**垫脚石理论**（Stepping-stone theory: 进化不需预设完美目标，而是通过重组现有“垫脚石”实现创新）回应了这一质疑。他指出，大语言模型缺乏创新很大程度上取决于初始条件；高度优化的初始解决方案容易陷入局部最优，而简陋的初始条件则为多样化探索提供了更大空间。这与**元学习**（Meta-learning: 学习如何学习，通过调整模型学习过程来提升学习效率和泛化能力）中的权衡类似：高约束条件收敛快但创新性低，无约束条件收敛慢但创新空间大。Shinka Evolve的核心创新之一即在于其**进化架构**（Evolutionary architecture: 一种模拟生物进化过程来构建和优化AI系统的架构），它能平衡这种权衡，实现高质量的多样化探索。

### MAP-Elites与程序存档
Shinka Evolve的进化架构底层采用了**MAP-Elites**（MAP-Elites: 一种质量多样性搜索算法，维护一个包含多样化高质量解决方案的存档）算法，其核心是维护一个包含多样化高质量解决方案的**程序存档**（Program archive: 存储大量程序及其相关信息的数据库）。与AlphaEvolve类似，Shinka Evolve的核心是一个程序存档，但进行了大量技术升级。系统的运行逻辑是：从存档中采样父程序和灵感程序，然后利用大语言模型对父程序进行改进（编辑、重写、交叉融合），生成新程序；接着在目标问题上评估新程序，收集反馈；最后将评估后的新程序重新加入存档，完成一次进化循环。这个过程是并行进行的，新程序的加入会将其知识扩散到整个数据库，如同程序树的分支，实现不同分支间的知识共享与共同进化。

### 架构创新：多模型集成与UCB
Shinka Evolve在架构上的第一个关键创新是实现了**多前沿大模型的集成与自适应选择**（Multi-frontier LLM integration and adaptive selection: 集成多种先进大模型，并根据其表现动态选择使用）。它整合了包括GPT-5、Sonnet 4.5、Gemini等在内的多种主流大模型。为了解决不同模型在不同任务上的表现差异及贡献的信用分配问题，Shinka Evolve引入了**UCB**（Upper Confidence Bound: 一种多臂老虎机算法，用于平衡探索与利用）算法。将每个大模型视为一个“摇臂”，系统根据模型在过往进化中的贡献动态调整其被选择的概率，在初期进行广泛探索，后期则偏向表现优异的模型，同时保留一定的探索概率，有效解决了探索与利用的权衡问题。实验表明，单一模型并非主导，不同模型在不同阶段展现优势，UCB算法能精准捕捉并实现自适应选择。

### 语义层面探索与知识扩散
第二个关键创新是**程序的语义层面探索**（Semantic-level exploration of programs: 不仅修改代码语法，更理解并利用程序的核心逻辑）。Shinka Evolve为每个程序生成摘要，从中提取**全局洞见**（Global insights: 从程序摘要中提炼出的、对改进程序有指导意义的抽象概念），并存储在**元草稿本**（Meta-scratchpad: 存储全局洞见，作为系统提示词的一部分）中，指导大语言模型的程序改进。这意味着系统不仅知道“如何”修改代码，还知道“为何”修改，能够从语义层面理解程序逻辑。然而，知识扩散需要平衡全局共享与局部隔离，过度共享可能导致单一优化方向，过度隔离则降低效率。Shinka Evolve正在探索自动调整这种平衡的方法，但这过程具有任务依赖性。

### 代理问题与MAP-Elites算法
第三个关键创新是Shinka Evolve在**圆堆积问题**（Circle packing problem）中验证了**代理问题**（Proxy problem: 一个简化或略微修改的问题，用于快速逼近原问题最优解）的重要性。在实验中，团队使用了带有微小松弛度的评估公式（允许圆有极轻微重叠）作为原问题的代理问题，系统在此上快速达到SOTA（State-Of-The-Art: 当前最先进水平）表现，再通过微调半径解决原问题。直接在原问题上运行则耗时更长。这证明了设计高效代理问题在科学发现中的价值，若AI能自主设计代理问题，将是协同进化的关键一步。Shinka Evolve的收敛速度快，性能在短时间内迅速提升，随后进入缓慢收敛阶段。

### 程序变异与交叉操作
Shinka Evolve实现样本效率提升的关键在于其**程序变异与交叉操作**（Program mutation and crossover operations: 进化算法中生成新个体（程序）的两种主要方式）。程序本质上是长字符串，需要保护核心代码区域不被随意修改。为此，Shinka Evolve引入了**可变区域标记机制**（Mutable region marking: 明确标注代码中允许被修改的区域），并结合拒绝采样与反思策略。相较于AlphaEvolve仅使用基于差异的变异，Shinka Evolve新增了两种关键变异操作：**全文件重写**（Full file rewrite: 让LLM基于父程序思路重写整个程序）和**交叉变异**（Crossover mutation: 融合两个父程序的优势生成新程序）。这些操作极大地提升了探索多样性，尽管并非在所有问题中都提升性能，但为**开放式进化**（Open-ended evolution: 进化系统能够持续产生新颖、复杂且有意义的解决方案，不受预设目标限制）提供了必要的维度多样性。未来的挑战包括实现多文件代码库的变异，目前Shinka Evolve仍局限于单文件程序。

### 未来愿景：氛围研究与人机协作
Robert Lang提出了一个极具想象力的未来愿景——**氛围研究**（Vibe Research）。他认为当前人机交互模式（单线程聊天助手）效率低下，未来科研模式应是**分布式、多线程的协作模式**（Distributed, multi-threaded collaboration: 研究者与AI系统并行、协同工作）。研究者白天引导AI确定探索方向，夜晚AI自主运行、并行实验、积累证据。研究者转变为探索的引导者，AI则承担重复性、低层次工作，使人类能聚焦高层次创意与决策。

### 规模化与自动验证
实现这一愿景需解决两个核心问题：**系统的规模化**（System scalability: 使系统能够以更低成本生成更多解决方案）和**自动验证能力的提升**（Improved automated validation capability）。规模化方面，Robert Lang设想通过并行化运行上千个Shinka Evolve实例，每个实例探索不同区域，并进行知识共享，甚至从空程序开始实现自主探索。自动验证能力是当前AI科学系统的短板；LLM易于生成解决方案，但**硬验证**（Hard validation: 在实际模拟器或硬件中运行并收集真实反馈）极为困难，目前多为**软验证**（Soft validation: 通过分析代码隐式模拟，精确度不足），易导致**Reward Hacking**（Reward Hacking: 系统找到评估函数漏洞而非真正解决问题）。若AI能实现高效硬验证，将是AI科学发现的关键突破。

### AI对人类工作的影响
主持人指出，大规模劳动力市场颠覆并未出现，反而作家、编辑需求增加，软件工程师薪资翻倍。这说明人类具有极强的适应性，AI是**人类能力的放大器**（Amplifier of human capabilities: AI增强而非取代人类现有能力），让人类聚焦创意、决策等优势领域。Robert Lang认同AI是放大器，而非替代者。未来科研模式下，人类成为AI的“牧羊人”，引导探索方向，验证成果；AI承担实验执行和数据处理。这种协作将大幅提升科研效率，解决重大科学问题。AI发展速度超越人类文化进化速度，需学习与AI协作，设计高效人机交互，培养AI素养。过度依赖AI如药物，会丧失独立思考能力；人类需找到协作的“度”。

### 总结与未来展望
当前的AI科学系统虽存在无法自主发明问题、自动验证能力不足等短板，但这些是发展中的问题，终将被解决。Robert Lang形容当前是AI科学发现的“**GPT-1时刻**”（GPT-1 Moment: 象征AI科学发现领域处于早期、具有巨大潜力的发展阶段）。尽管前路漫漫，未来充满希望。