---
author: AI Engineer
date: '2026-09-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=8KkibGU_DDY
speaker: AI Engineer
tags:
  - agent-evaluation
  - token-economics
  - acceptance-criteria
  - mental-model
  - information-entropy
title: 鼠力隐喻与心智模型：破解 AI Agent 的价值度量困局
summary: Yutori 创始设计师 Maximillian Piras 探讨了当前 AI Agent 面临的核心瓶颈：能力增长与价值度量之间的脱节。类比瓦特发明'马力'来破除用户对蒸汽机的认知阻碍，文章提出了'鼠力'（Mouse Power）概念，并基于香农信息熵构建了涵盖'执行步骤不确定性'与'验收标准不确定性'的二维评估矩阵，指出理想的 Agent 场景应具备类似 NP 问题的特征——验证难度远低于执行难度，从而实现以算力速度度量价值。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Yutori
products_models: []
media_books: []
status: evergreen
---
### 后台并行探索与 Token 账单焦虑

在日常工作中，许多开发者与设计者已经习惯将 **AI 智能体**（AI Agent: 能够自主感知环境、规划路径并调用工具完成多步骤任务的系统）作为后台协处理器使用。当人类的主动注意力集中在单一核心任务（例如进行公开演讲）时，往往希望外围琐碎任务仍能同步推进。例如在演讲准备中，虽然设计规范与系统提示词已经完备，但单靠一个 Agent 往往难以穷尽所有可能；为了在截止时间前探索更多幻灯片的版式设计与排版风格，用户通常会一口气在后台并行拉起多个 Agent，让它们在不同视觉方向上同时展开探索。

这种工作流虽然极大扩展了单位时间内的探索广度，但也迅速催生出新的认知困惑与成本焦虑。随着 Agent 数量的激增，当月底收到账单时，用户不可避免地会陷入反思：我们是否陷入了过度 **氛围编程**（Vibe Coding: 依赖直觉与大模型快速生成代码而缺乏严格工程推导的开发方式）？这种无节制的 **Token 极大化**（Token Maxing: 不计成本地消耗模型上下文与调用量以换取覆盖率的行为）究竟创造了多少真实价值？在任务编排上是否存在更高效的路径？这一系列问题的核心，在于我们尚未建立起一套能够清晰评估 Token 成本与实际产出价值之间关系的度量标准。

<details>
<summary>Original English</summary>

Thanks a lot for your time. Really appreciate you dropping by, and it's always a great honor to speak at the World's Fair. So, I'll do my best to give you guys some valuable insights and hopefully make it worth your time.

My name is Maximillian Piras, and today I'll be talking about mouse power—this is a talk about measuring agents through mental models. But before I get into talking about measuring agents, I'm going to talk through a bit about how I use them every day. It might seem familiar to you, but just to level set, we'll go through it.

I tend to background them, like I'm sure a lot of you people are doing as well. While my active attention is focusing on one thing—like perhaps giving this talk to you—I still want to make some progress on peripheral tasks. So I'll keep my attention focused on giving this talk while my agents help me explore some designs in the background, because I think my slides need a bit of work. I've got my design system already set up, and I've given some guidance to my agents. I'll kick off an agent to explore different directions on typography and layout, trying to get as many explorations as possible.

Of course, one agent is never enough, so I like to kick off a bunch in parallel. I've got a lot of slides to get through, so I need all my agents running and exploring in different directions. Hopefully, I can get some interesting ideas to make my slides better before our deadline.

This is generally how I work, and it's probably familiar to many of you: kicking off agents in parallel as much as possible because it feels like there is always more research to do and more design directions to explore. Why not maximize your time by running agents concurrently while focusing on your main task? It is a lot of fun, until you get the bill. Then you start to wonder: was it all worth it? Did you vibe code too hard? Were you token maxing too much? Could you have been more efficient in how you sequenced your agents? That brings us to our core question: how do we value token costs, and specifically, how do we help our customers value them?

</details>

### 计算机操作模型与心智模型摩擦

在过去一年半的时间里，作为 **Yutori** 的创始设计师，主要聚焦于 **计算机操作模型**（Computer Use Models: 训练 AI 像人类一样通过屏幕视觉、鼠标点击与键盘输入直接操控操作系统的模型）的研发与落地。这类模型的关键应用场景在于：当目标系统缺乏现成的 API 或 **模型上下文协议**（Model Context Protocol / MCP: 规范 AI 与外部工具及数据源交互的标准协议）时，直接派遣 Agent 像人类一样操作图形界面，从中提取难以程序化获取的数据并进行自动化处理。尽管这种通过 GUI 交互的方式在能效上明显低于原生 API，但在缺乏接口集成的场景下，它构成了不可替代的兜底能力。

然而，在与大量客户的实际交流中可以发现，尽管市场对 Agent 充满兴奋，但绝大多数客户普遍感到“仅仅触及了皮毛”，对如何系统化利用 Agent 缺乏直觉认知。客户最常提出的疑问集中于三个层面：最佳应用场景究竟在哪里？如何正确构建使用 Agent 的心智模型？以及如何衡量 Token 支出与业务价值之间的投入产出比。早期的技术极客很容易陷入幸存者偏差——正如作家厄普顿·辛克莱（Upton Sinclair）的名言所揭示的，身处行业内部的技术布道者往往带着强烈的先入为主偏见，误以为自己构建多 Agent 舰队的高阶体验代表了大众市场；但现实中，绝大多数潜在用户甚至仍停留在手动向 ChatGPT 复制粘贴文本的阶段。因此，推广 Agent 的核心障碍不在于技术本身的能力上限，而在于缺乏能够匹配用户心智模型的价值衡量机制。

<details>
<summary>Original English</summary>

For the past year and a half, I've had the pleasure of working as the founding designer at a company called Yutori, where we focus on computer use models. These are models that learn to use a computer just like a human would. The primary use case arises when you cannot get information through an API or an MCP—why not send an agent out to use the computer like a human, extracting and manipulating data that wasn't previously accessible? Obviously, this is less efficient than native APIs and MCPs, but as a last resort, having an agent operate a computer gets the job done.

Here is an image of the Yutori agent using the Yutori website, checking out its own benchmark—admiring itself, in a way. A significant part of my role as founding designer is talking to customers to understand how we can make agents as intuitive as possible, and figuring out the mental models they use to evaluate the use cases they assign to agents.

So far, many customers seem quite confused. People are excited about agents, but a phrase that comes up repeatedly is that they feel they are "just scratching the surface." It is not yet intuitive how best to utilize them. In my customer discussions, it consistently comes down to questions like: What is the best way to use agents? What are the ideal use cases? How should we evaluate the trade-offs between token costs and actual value? We are still building this organizational muscle.

This brings me to the core thesis of this talk: agents have a fundamental measurement problem. Here is a photo of me at work attempting to measure agents; a coworker took it and remarked that I looked like I was trying to solve the Pepe Silvia conspiracy. It is not an easy task.

Some of you might think: "Hold on, what is this guy talking about? I have a fleet of agents working for me right now, building our next million-dollar app, and I have no problem measuring them." While that may be true for early adopters in this room, remember the mandatory Upton Sinclair quote: we are extremely biased early adopters. Our excitement does not represent the broader audience we ultimately need to help adopt this technology.

Whether directly or indirectly, we are all selling tokens. Is our personal token usage representative of people who have never touched an agent? Many people are still manually copying and pasting into ChatGPT. I might even be married to one of them—despite my efforts, she hasn't let me set her up with agents yet. When thinking about scaling adoption across the globe, we must remember this emotional and cognitive gap.

</details>

### 瓦特的马力策略：用旧基准量化新效率

新技术在诞生初期遭遇认知阻隔是一个经典的商业与工程命题。回顾 18 世纪工业革命早期，**詹姆斯·瓦特**（James Watt: 现代蒸汽机改良者与工业革命先驱）在推销其改良型蒸汽机时，面临着与今天极其相似的困境。当时磨坊与啤酒厂的主流动力源是 **马动磨盘**（Horse Gin: 由马匹牵引旋转臂绕圈行走以提供机械动力的装置）。瓦特清晰地意识到，技术扩散的最大阻力在于认知失调：当时的产业界完全以“马”的逻辑进行生产决策，面对冰冷、复杂且令人生畏的蒸汽机，人们无法直观感知其能效优势，甚至因为“马匹具有天然的良好情感体验（Great Vibes）”而本能地抗拒机械化替代。

为了击穿这种情感惯性与认知壁垒，瓦特深入测算马动磨盘的机械结构与马匹的平均做功输出，由此提出了 **马力**（Horsepower: 衡量功率的工程单位）这一度量概念。从现代严格的物理学视角来看，当时的“马力”定义并不绝对严密，甚至存在粗略估算的成分，但其划时代的价值在于：它创造了一个能够与客户既有心智模型完全对齐的能效基准。借助“马力”，客户可以直观算出用蒸汽机替代马匹后能够获得的效率倍率与清晰的 **投资回报率**（Return on Investment / ROI: 衡量投入成本与产生效益比例的核心财务指标），从而跨越尝试新技术的心理阈值。这一历史经验表明，如果我们无法为客户提供一套可感知、可计算的 ROI 衡量标尺，就根本无法有效传递 Agent 的技术价值。

<details>
<summary>Original English</summary>

It really boils down to the age-old problem of introducing a new technology. There is plenty of history we can study to see how people solved this in the past. We have this exciting new capability, but we haven't yet figured out the right framework to communicate it.

For this talk, let's go back to the 1700s and take notes from when James Watt was trying to sell steam engines. At the time, he decided that a prime use case for his engines was replacing the horse gin—the standard power source for mills and breweries used to grind barley and run machinery. The standard setup was simple: you hitched a horse to a rotary arm, the horse walked in circles, and that generated your power. It might seem primitive today, but it was ubiquitous back then.

Watt recognized that an efficient machine was vastly superior to a horse. However, he correctly understood that a major adoption barrier was cognitive dissonance. How do you convince people who think entirely in terms of horses to adopt an intimidating, unfamiliar machine that claims to solve all their problems when they can't visualize the benefits? Furthermore, regardless of efficiency, horses had great "vibes"—it is hard to compete with emotional attachment.

Watt knew he had to overcome emotion with tangible ROI calculations. His solution was to meet people within their existing mental model by creating a metric that established a baseline of relative efficiency. He studied horse gins, estimated the average mechanics and performance of draft horses, and coined the term "horsepower."

He used horsepower to quantify the general output horses were generating, providing a comparative baseline to demonstrate the exact efficiency multiplier a steam engine delivered. The metric was not strictly scientific or perfectly accurate at the time, but its primary function was communicating value. It allowed horse-reliant business owners to calibrate potential efficiency gains and gave them the confidence to try a steam engine. The crucial lesson is: if we cannot provide a tangible ROI for our customers, communicating real value becomes nearly impossible.

</details>

### 终结 Token 消耗的末日循环与结果导向归因

缺乏精准度量导致当前科技行业在 Agent 应用上陷入了典型的“末日循环”。很多企业在没有明确产出度量的情况下盲目消耗算力，导致一年的 Token 预算在一个季度内被迅速耗尽，随后在成本重压下被迫转向严苛的紧缩政策；直到下一次技术焦虑（FOMO）被重新点燃，又再度重启盲目尝试。这种在 **过度支出与利用不足**（Overspending & Underusing: 企业采购大量 AI 算力却未能转化为实际业务效能的脱节现象）之间的反复摆动，严重制约了技术的规模化渗透。

部分领先企业已经开始探索破解这一恶性循环的路径。例如 Coinbase 首席执行官曾公开分享，他们通过重构内部模型调用策略——默认采用轻量模型处理常规任务，仅将最复杂的长尾难题路由至前沿大模型，成功使业务价值曲线与纯粹的 Token 消耗量脱钩。然而，仅仅优化 Token 成本依然停留在系统内部的 **产出**（Output: 系统的直接工作量或中间计费指标）层面，而非终端的 **业务成果**（Outcome: 对实际业务目标产生的实质性推动）。企业真正需要的度量闭环，是将每一笔 Token 支出严格归因到具体的结果指标：
* 消耗的 Token 具体修复了多少个线上缺陷？
* 自动化解决了多少张客户支持工单？
* 对核心业务里程碑的推进幅度是多少？

只有将 Token 消耗从抽象的内部开销转化为与业务目标紧密绑定的量化成果，才能建立起可持续的 Agent 商业模型。

<details>
<summary>Original English</summary>

We only need to look at our own industry to see countless examples where technology teams struggle to calculate sound ROIs. In this room, we might assume this is a solved problem. But look at brilliant engineers who aren't deeply immersed in AI: they end up blowing through their entire annual token budget in a single quarter or obsessing over token leaderboards without clear business alignment.

We find ourselves in a doom loop of "overspending and underusing"—a term borrowed from a great blog post by Ramp. It is a vicious cycle where teams token-max themselves into austerity, pull back, and then re-enter the loop once FOMO strikes again. We must break this loop through better metrics that clearly communicate value.

Some organizations are heading in the right direction. The CEO of Coinbase recently shared a chart on X illustrating how changing internal routing defaults—reserving frontier models exclusively for the hardest tasks—allowed their AI value creation to diverge from raw token spend. Ramp highlighted similar findings.

However, the prevailing problem is an excessive focus on tokens. Tokens are a useful metric for internal system observability, but at the end of the day, tokens are merely an output. Tokens must be cleanly mapped to business outcomes: How many bugs were squashed with that token spend? How many customer support tickets were closed? How much measurable progress was made against core objectives? Without a tight coupling between spend and business outcomes, sustainable ROI remains elusive.

</details>

### 代码审查困局与以算力速度度量

在软件工程领域，由 Agent 带来的效率提升正遭遇严峻的 **验证瓶颈**（Verification Bottleneck: 生产端速度指数级提升后，人工审核与质量验收成为整体交付链条中最狭窄短板的现象）。目前行业普遍面临“死于千次代码合并请求”（Dying by thousand pull requests）的现状：即便是声称已经攻克代码自动生成的前沿实验室（如 Anthropic），也不得不承认 **代码审查**（Code Review: 由同行对代码变更进行正确性、安全性与可维护性检查的质量门禁）远未解决。当 Agent 以算力速度疯狂生成海量代码时，由于缺乏同等速度的自动化质检机制，所有审查压力全部堆积在人类工程师身上，导致端到端的实际效能提升被严重稀释。

代码审查之所以具备被彻底解决的可能性，是因为人类工程文化在长期的协作中已经对审查标准形成了高度收敛的先验假设与打分准则（Rubric）。正如技术学者 Noah Hein 在探讨代码审查重构时所指出的，当前的核心任务不是修补旧流程，而是重新审视代码审查底层的先验假设，使其适配 Agent 时代的生产特征。如果能够将这些工程共识转化为程序可判定的自动化验收机制，整个软件工程体系就能完成从 **以算力速度执行**（Execution at the speed of compute）向 **以算力速度度量**（Measurement at the speed of compute）的关键跃迁。

<details>
<summary>Original English</summary>

This dynamic is not just an abstract industry problem; many of us experience it firsthand. While we all enjoy coding alongside agents and feel a noticeable boost in personal velocity, teams are increasingly suffering from "death by a thousand pull requests." Even Anthropic, where some team members have claimed to solve code generation, openly admits that code review remains unsolved.

The bottleneck has shifted decisively to human verification. Efficiency gains from coding agents stall because engineers spend the majority of their time reviewing generated code, having not yet figured out how to scale verification in tandem with generation. When verification cannot match the speed of creation, measuring quality and calculating true ROI at scale becomes impossible. We generate vast amounts of code, but cannot efficiently verify whether enough of it is production-grade to justify the token expense.

Code review may have always had systemic flaws, but agents are exposing the cracks. As Noah Hein noted in a post about solving code review, the underlying assumptions of code review must be fundamentally revisited. We need to examine our priors to establish a new operational baseline for reviewing code in the agentic era.

Why does code review feel solvable? Because engineering culture has achieved strong convergence around shared assumptions and structured rubrics. Our immediate challenge is adapting those assumptions for the agentic age. If we succeed, we can transition from execution at the speed of compute to measurement at the speed of compute. Those measurements must align directly with the mental models of users, reinforcing the rule: if you build an agent for a task, you must equally build the methodology to verify its output.

</details>

### “鼠力”概念与基于信息熵的任务评估二维矩阵

基于上述思考，演讲者提出了对应于 Agent 时代的“马力”隐喻——**鼠力**（Mouse Power: 用于直观衡量 Agent 替代人类操作与计算任务时综合能效增益的心智模型）。“鼠力”并非指去测量屏幕光标移动像素等高维度的机械指标（这种尝试已被证实为毫无意义的过度工程），而是一种帮助用户判断特定任务是否适合由 Agent 承担的评估框架。借鉴 **香农信息熵**（Shannon Information Entropy: 衡量信息不确定性与概率分布离散程度的数学度量）理论，可以构建一个基于两个核心维度的任务评估矩阵：

1. **X 轴：任务执行步骤的不确定性（Uncertainty in Task Steps）**
   * **低不确定性**（如订购机票）：任务包含固定的起降地选择、座位确认等确定性步骤。此类任务路径完全可预测，直接编写确定性代码脚本即可解决，无需浪费昂贵的 LLM Token。
   * **高不确定性**（如绘制传世艺术杰作）：执行路径极度发散且缺乏规律，在预训练阶段极易落入 **分布外**（Out of Distribution / OOD: 样本特征偏离模型训练数据集分布的异常状态），在强化学习中也会遭遇极其稀疏的奖励信号，极难通过常规模型进行有效建模。
   * **中度不确定性**：步骤具有一定的分支与灵活性，但整体处于可控探索区间，构成了 Agent 施展能力的理想平衡点。

2. **Y 轴：验收标准的不确定性（Uncertainty in Acceptance Criteria）**
   * **高不确定性验收**：如果验证结果好坏的难度与重新执行一次任务完全相同（即人类必须从头重做一遍才能判断输出是否合格），那么构建 Agent 就毫无杠杆价值。
   * **低不确定性验收（NP 型任务特征）**：最佳的 Agent 任务场景应当具备类似于 **NP 问题**（NP Problems: 指解的验证可以在多项式时间内完成，但寻找解可能需要指数级复杂度的计算问题集合）的特性——**验证难度远低于执行难度**（Easier to verify than to execute）。

当一个任务具备中度步骤探索空间、且结果极易被结构化验证时，开发者不仅能够构建执行 Agent，更能轻松构建专门负责质量审查的 **验证 Agent**（Verifier Agent: 专职依据确定性规则或结构化标准对其他 Agent 的产出进行校验与过滤的子系统），从而真正实现兼具高容错性与可量化 ROI 的自动化系统闭环。

<details>
<summary>Original English</summary>

This brings me to the core concept of "mouse power"—the potential equivalent of horsepower for the agentic age. Just as James Watt demonstrated efficiency gains relative to the horse gins of his era, we must establish a baseline for how people use computers today and demonstrate the performance multiplier an agent delivers across specific vectors.

Of course, this is not as simple as tracking cursor coordinates across a screen. I actually joked with this idea and had Claude vibe-code a cursor movement measurement tool, thinking I could quantify mouse velocity to derive a clean metric. That is obviously a fool's errand because the information space of computer use is far too high-dimensional. Mouse power is not a literal physical metric; it is a mental model. The core principle is: if you sell someone an agent, you must also provide the rubric to verify that the agent is performing valuable work, proving that the consumed tokens are justified.

To operationalize this, I turn to information theory—specifically Claude Shannon's concept of entropy, representing uncertainty within a probability distribution, which underpins modern training techniques like cross-entropy loss. Entropy provides a compelling lens for evaluating not just agent capability, but the nature of the tasks we assign to them.

I mapped this into a two-axis matrix:
- **The X-axis represents the uncertainty in task steps.** Booking a flight has very low step uncertainty: you need a departure, destination, date, and seat selection; these structural requirements are invariant. In contrast, painting a masterpiece has near-infinite step uncertainty with no predictable operational pathway. When step uncertainty is extremely low, do not waste tokens—write a deterministic script. When step uncertainty is excessively high, the task is likely out-of-distribution for pre-training and suffers from sparse rewards in reinforcement learning, making it unsuitable for reliable agent modeling. The sweet spot lies in the middle.
- **The Y-axis represents the uncertainty in acceptance criteria.** When acceptance criteria uncertainty is high, verification becomes indistinguishable from execution—a person must essentially redo the entire task to confirm its validity, destroying any token leverage. 

The ideal deployment zone consists of tasks with moderate operational uncertainty paired with low acceptance uncertainty. These mirror **NP-style problems: tasks that are significantly easier to verify than to execute**. When verification follows a reliable, repeatable pattern, you can deploy agents to execute the work and deploy secondary verifier agents to validate the results. As you build your next generation of agents, ensure you simultaneously design their verification mechanics and quantify their mouse power.

</details>