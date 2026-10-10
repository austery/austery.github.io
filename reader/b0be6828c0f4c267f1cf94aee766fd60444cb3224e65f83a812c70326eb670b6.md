---
author: Best Partners TV
date: '2026-05-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZdlA2Qt2cgY
speaker: Best Partners TV
tags:
  - artificial-general-intelligence
  - world-models
  - predictive-architecture
  - open-source-ai
  - ai-safety
title: Yann LeCun：生成式AI路线的终局与世界模型
summary: 图灵奖得主杨立昆深入剖析生成式大模型的局限性，指出基于 Transformer 的生成式路线无法通向通用智能。他强调以 JEPA 为架构的“世界模型”才是实现机器人、自动驾驶等物理世界理解的核心，并探讨了 AI 主权、安全缺陷及开源生态的未来。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Yann LeCun
  - Daniel Kahneman
  - Linus Torvalds
  - Geoffrey Hinton
  - Yoshua Bengio
  - Mark Zuckerberg
  - Andrew Bosworth
companies_orgs:
  - OpenAI
  - Meta
  - AMI
  - Sun Microsystems
  - Anthropic
products_models:
  - JEPA
  - Llama
  - GPT-4
media_books: []
status: evergreen
---
### 生成式路线困境

**Yann LeCun**（图灵奖得主、深度学习教父）在近期访谈中抛出惊人言论，直言五年内 **JEPA**（Joint Embedding Predictive Architecture：联合嵌入预测架构，一种旨在学习物理世界规律的表征预测框架）模型将全面统治全球智能系统。他判定 **OpenAI** 终将成为下一个被时代淘汰的 **Sun Microsystems**，并直接批评 **大语言模型**（Large Language Model：基于海量文本训练的 AI 系统）存在无法修复的内生安全缺陷。

很多人对 Yann LeCun 有个误会，觉得他在全盘否定当前的 AI，实际上并非如此。他并不否定 LLM 的价值，相反，他认为 LLM 本身没有任何问题，是当下诸多实用产品的基础。但 Yann LeCun 指出，虽然大模型在语言处理、日常对话、代码编写等领域展现出极强的实用性，但这无法改变一个核心事实：它无法通往人类级别的智能，更无法通往真正的通用智能（**AGI**：Artificial General Intelligence，具备人类水平智能的通用人工智能系统）。

这个结论根源于现实世界和语言世界的本质差异。我们熟知的大语言模型天生为处理语言而生，语言是离散的、符号化的、结构化的。而我们身处的现实物理世界是高度多模态的、连续的、充满噪声、混乱且复杂的。训练一个系统理解真实世界的难度，远高于训练它理解语言。

### 世界模型与JEPA

正是基于这种核心矛盾，曾经被寄予厚望的 **VLA**（Vision-Language-Action：视觉-语言-动作模型，直接迁移 LLM 技术至机器人控制的架构）路线宣告失败，系统可靠性极差。Yann LeCun 给出的唯一答案是：想要实现真正的机器人、L5 级自动驾驶和工业 AI，**世界模型**（World Model：能够预测自身行为后果并理解物理世界的智能模型）是唯一的出路。

为了推进世界模型的研发，他离开了 **Meta**，创办了 **AMI**（Advanced Machine Intelligence：高级机器智能）。在 Yann LeCun 的定义中，世界模型就是让智能系统拥有预测自身行为后果的能力，这是智能的核心。没有这个能力，就谈不上真正的智能。拥有预测能力之后，系统才能具备第二个核心能力：**规划**（Planning：智能系统先明确目标，通过搜索和优化找到达成目标的动作序列）。这与大语言模型机械延续文本序列的工作模式有天壤之别。

在技术路径上，Yann LeCun 和他的团队彻底否定了曾经的主流路线：**像素预测**（Pixel Prediction：预测图像或视频像素的生成式技术）。他直言，预测像素本质上就是一条死路，根本学不到世界的本质规律。真正实现突破的是他提出的 **JEPA** 架构，其完全颠覆了生成式路线。它不预测原始像素，而是将原始数据送入编码器得到抽象表征，再用一个表征预测另一个表征。简单来说，JEPA 是在抽象表征空间里做预测，而非原始数据空间。

### 机器人泛化瓶颈

话题转向当前火热的机器人领域，很多演示看起来智能，仿佛具备了规划和推理能力。但 Yann LeCun 直言这是假象。这些机器人背后是海量的模仿学习数据在支撑。研发团队通过人工演示采集百万小时数据，再辅以少量强化学习才实现效果。这种模式致命缺陷明显：数据采集成本极高、系统极度脆弱、泛化能力极差，无法应对未知场景。

相比之下，基于世界模型的机器人不需要这样做。它可以通过预测动作后果，直接规划出解决新任务的动作序列，实现零样本泛化，数据效率和人类、动物几乎一致。为什么整个硅谷看不到这个问题反而疯狂内卷 LLM？Yann LeCun 用了“羊群效应”来概括，硅谷公司都在同一条战壕里，没人敢承受落后于竞争对手的风险。为了避开浮躁氛围，他特意把 AMI 总部设在巴黎。

### 安全、主权与开源

关于 **AI 主权**，Yann LeCun 提出了 **Tapestry** 解决方案。该方案核心思路与 **联邦学习**（Federated Learning：一种无需共享原始数据，仅交换模型参数的分布式训练方法）完全一致，即数据不动，模型动。最终收敛出一个全球共识模型，成为人类知识与文化的仓库，每个参与者基于此微调适配自己的语言和文化。

针对开源与闭源，Yann LeCun 将 OpenAI 等闭源公司比作上世纪 90 年代的 Sun 和 HP-UX。他认为闭源模型的致命天花板在于训练数据耗尽，AI 平台化的趋势注定了开源终将追上闭源。至于大语言模型的安全问题，Yann LeCun 认为它从根本上就是不安全的，因为其唯一的依据是数据模式匹配，系统内部没有硬编码约束，不会理解任务目标，也不会预测行为后果。在现有范式下，LLM 永远存在逃逸可能，总会有一个提示词让它做出危险行为。

### 研发困境与未来

聊完产业，Yann LeCun 揭秘了 Meta 内部的困境。Meta 曾有一个衔接研究与产品的团队，但后来被解散，FAIR 实验室变成孤岛。2023 年 Meta 成立 GenAI 组织，从 FAIR 抽走了大量顶尖研究者，但该组织被短期业绩束缚，无法交流，导致 Meta 失去了前沿创新的能力。另外，他还澄清了一个外界最大的误解，即很多人认为 Llama 是他主导的，甚至说他反对 Llama。事实上，他对 Llama 没有任何技术贡献，唯一做的就是强力推动 **Llama 2** 的开源。

在播客结尾，Yann LeCun 回到了自监督学习的核心理念。他建议正在读博的研究者，不要把精力放在研究当前的 LLM 上，这是描述性的科学，缺乏创造性，应该聚焦下一代的 AI 系统。大语言模型的成功只是自监督学习的一个特例，因为语言是离散符号，预测难度低，而现实世界是连续高维的，必须用 JEPA 架构才能学习世界模型。杨立昆坚信，真正能改变物理世界和推动产业革命的，一定是能够理解现实世界的、更加智能的系统。