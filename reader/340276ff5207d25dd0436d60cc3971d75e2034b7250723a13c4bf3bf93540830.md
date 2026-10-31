---
layout: post.njk
source: https://yage.ai/share/llm-distillation-misconceptions-20260414.html
speaker: yage.ai
title: '"蒸馏"到底帮了中国 AI 公司什么忙'
date: '2026-04-14'
summary: 文章探讨了中国AI公司通过“蒸馏”技术获益的争议。作者区分了经典知识蒸馏、输出模仿和推理链迁移，指出后者是关键。虽然蒸馏能帮助后发者快速获得推理和工具使用能力，跳过大量研发成本，但存在泛化能力缺失和时效性限制。随着后发者自建数据飞轮，蒸馏作为冷启动策略的价值递减。DeepSeek 的独立创新被视为长期竞争力的范例。
area: tech-engineering
category: ai-ml
tags:
  - knowledge-distillation
  - large-language-models
  - ai-competition
  - imitation-learning
  - agentic-systems
people:
  - Hinton
companies_orgs:
  - Anthropic
  - OpenAI
  - DeepSeek-AI
  - Microsoft
  - Mistral AI
  - Moonshot
  - MiniMax
products_models:
  - Claude
  - GPT-4
  - DistilBERT
  - DeepSeek R1
  - Qwen3
  - Llama
  - Magistral
  - Kimi K2
  - Alpaca
  - Vicuna
  - Orca
media_books: []
draft: true
status: evergreen
---

调研日期：2026年4月14日
数据来源：学术论文（ACL、EMNLP、AAAI、ICLR、ICML、Nature）、技术报告、独立基准测试

2026 年初，Anthropic 和 OpenAI 相继指控中国 AI
公司通过”蒸馏”来大规模提取它们的模型能力。Anthropic 报告了约 1600 万次
API 调用、24,000 个账户的使用规模。媒体广泛报道，“蒸馏”成了中美 AI
竞争里的关键词。

但如果你对机器学习有一些了解，这个指控读着会觉得哪里不太对。

## 两个矛盾

“蒸馏”在机器学习里有一个经典的含义。2015 年 Hinton 提出的知识蒸馏，核心是让小模型学习大模型的完整概率分布，而不只是最终答案。举个例子：大模型判断一张图片是”猫”的时候，它内部的概率输出可能是
{猫: 0.7, 豹: 0.15, 狗: 0.1, 马:
0.05}。这个分布本身就包含了丰富信息：猫和豹比猫和马更像。Hinton 管这叫
“dark knowledge”。经常被引用的 DistilBERT 就是用这种方法做的：从 BERT
内部拿到完整的概率分布、中间层特征、甚至直接复制了一部分权重，最终实现了参数减少
40%、准确率保留 97%。

但中国公司调用 Claude 或 GPT-4 的 API
时，拿到的是什么？只有最终的文字回答。没有概率分布，没有中间层，没有权重。DistilBERT
那套方法在这里完全不适用。

这是第一个矛盾：概念上的。
大家说的”蒸馏”和实际发生的事情是两码事。实际发生的事情更像是”大量抄作业”：收集前沿模型的回答，然后拿去训练自己的模型。学术上管这叫
imitation learning 或者 SFT on synthetic data，和 Hinton
的蒸馏在技术上几乎没有关系。

第二个矛盾是效果上的。
如果这只是”收集了一批高质量的问答数据然后去训练”，那后发者到底省了什么？预训练还是要做（或者用开源模型），训练的计算量取决于模型大小，和数据来源无关。更要命的是，ICLR
2024 的一篇论文 “The False
Promise of Imitating Proprietary LLMs” 直接做了实验：把模仿数据从
25M token 加到 150M token，13B 模型在 MMLU、HumanEval、GSM8K
上的分数基本没涨。结论是：模仿学习传递的主要是回答的风格和语气，而不是推理能力。

如果经典蒸馏的技术不适用，纯模仿的效果又有限，那”蒸馏”到底是怎么帮后发者的？

## 先厘清：三种不同的操作

在回答之前需要区分一下，因为”蒸馏”这个词在不同场景下指的是三种机制完全不同的操作。

第一种：经典蒸馏。
需要打开教师模型的内部，拿到完整概率分布和中间状态。DistilBERT
用的就是这种。对闭源 API 做不了。

第二种：输出模仿。
只拿教师模型的最终文字回答来训练。Alpaca（$500 成本，52K 条 GPT-3
输出）、Vicuna（$300 成本，70K 条 ChatGPT 对话）用的是这种。OpenAI 2024
年推出的”蒸馏”产品功能本质上也是这种。前面说了，这种方式传递的主要是风格，不是能力。这和我以前在微调文章中得出的经验一致：微调适合让模型学会你说话的语气，但教不了它新本事。

第三种：推理链迁移。
训练数据里不只有教师的最终回答，还有完整的推理过程。教师不只说”答案是
42”，而是说”首先我们知道 X，由此推出 Y，结合 Z 条件，得到 42”。Microsoft
Orca 和 DeepSeek R1 蒸馏版用的是这种。而且这个方向在 2025-2026
年进化得很快：从最初的”一次性抄回答然后训练”（off-policy），发展到了让学生先自己做题、再让教师批改的迭代方式（on-policy）。后者效果好得多，Qwen3
的技术报告显示 on-policy 蒸馏在 AIME’24 上达到 74.4%，而 off-policy 只有
55.0%，差了近 20 个点，且计算成本只有 RL 的十分之一（Qwen3 Technical
Report）。更值得注意的是，微软研究院的 GAD（2025）证明了这种 on-policy
方法在纯黑盒条件下也能做：用一个判别器来区分学生和教师的输出，替代了对教师内部状态的需求。

中美蒸馏争议涉及的操作，根据 Anthropic
描述的行为模式（批量提取推理链、工具调用模式、代码生成数据），主要是后两种的混合。

## 后发者到底获得了什么

大多数文章会列一串好处：省了训练成本、免费获得了
alignment、获得了推理能力。但逐项拆开来看，这些好处的实际含金量差异很大。有些被高估了，有一个被低估了。

### 回答的格式和腔调：拿到了，但不值钱

一个没经过训练的原始模型（比如 Llama 的 base
版本）拿到一条指令后，它最可能做的事情是接着你的话往下编，而不是回答你的问题。你问它”写一首关于秋叶的诗”，它可能会接着写”写一首关于冬雪的散文，写一首关于春花的…“，因为它在预训练中看到的就是这种连续文本。

在 ChatGPT
的回答上训练一轮之后，模型就知道”哦，人类问我问题的时候，我应该回答问题”。这听起来很基础，但确实是需要学的。InstructGPT
的数据显示，光是学会”回答问题而不是接话茬”这一件事，就能让一个 1.3B
的小模型在用户满意度上超过 175B 的 GPT-3（Ouyang et al., NeurIPS
2022）。

所以后发者通过模仿确实能获得这一层：指令遵循、对话结构、Markdown
输出格式、多轮对话的上下文维护。这些和价值观无关，是产品基本可用性的一部分。

但这层东西非常便宜。 LIMA 这篇论文（Zhou et al., NeurIPS
2023）做了一个很极端的实验：只用 1,000 条精选数据做训练，65B 的
LLaMA 在 43% 的盲测对比中被评为优于
GPT-4。论文的结论很直白：模型的知识和能力几乎全在预训练阶段学到了，后面的训练只是教它”用什么格式回复用户”。1,000
条数据就能教会的东西，犯不着大规模调用 API 去获取。

### 安全审查：对后发者基本没用

很多文章把”省掉了 alignment
成本”作为蒸馏的一大好处来讲。前沿模型确实花了大量资源做安全对齐（InstructGPT
用了约 40 名标注员、33K-50K 条偏好比较，前沿模型的 RLHF 成本在 $5-20M
级别）。但这里有一个被忽略的前提：这笔钱花在了西方政治和文化语境下的安全审查上。中国模型需要的内容过滤涉及完全不同的话题，这部分必须从头做。反过来，西方模型的过度审查在中国语境下可能还需要被移除。

对于以性能和价格为主要竞争维度的后发者，精细的安全对齐排在核心能力开发之后。所以这笔
$5-20M 的 alignment 成本，后发者既不需要也无法通过蒸馏来省掉。

### 跳过
thinking trace construction：这才是真正被低估的好处

前面说了，推理链迁移的效果远好于纯输出模仿。但它真正的价值不只是”学到了解题思路”这么简单。更大的价值在于：后发者跳过了整个
thinking trace construction 的研发过程。

什么是 thinking trace
construction？就是让模型从零开始学会推理的过程。DeepSeek R1
的技术报告（发表在 Nature）详细记录了这有多难：先在
671B 参数的底座模型上跑纯 RL（GRPO），每一步生成 512
个候选回答，跑了数千步，直到模型自发地学会了自我验证和反思（所谓的”aha
moment”）。然后用这个 RL 模型的输出做 rejection sampling，筛选出 600K
条推理样本和 200K 条通用样本。然后再跑一轮 RL
做微调。整个四阶段流水线需要一个世界一流的 RL 基础设施、一个 671B
参数的底座模型、以及大量试错和工程投入。

后发者通过蒸馏可以跳过这一切。

DeepSeek 自己的数据是最有说服力的证据。他们对比了同一个 32B
底座模型的两种训练路径（DeepSeek R1 论文, Section
4.1）：

从头做 RL（R1-Zero-Qwen-32B）：AIME 2024 得分 47.0%

蒸馏 R1 的推理链（R1-Distill-Qwen-32B）：AIME 2024 得分 72.6%

蒸馏比从头 RL 高了 25
个点，且计算成本只是后者的零头。更极端的数据来自 Hu et al.（arXiv:2505.21067）：只用 920
条蒸馏样本，蒸馏出来的 32B 模型就超过了多个从头 RL 训练的 32B
模型（DAPO-32B 34.8%，SimpleRL-32B 9.4%）。

一个直觉：蒸馏就像是”请了一个特别好的家教，把他的解题套路抄了一遍”。前沿实验室花了巨大的研发投入（RL
基础设施、671B 模型、四阶段
pipeline）才让模型学会推理。后发者通过蒸馏可以直接拿到这些推理链，跳过整个研发过程。这比”省了标注成本”或”免费获得
alignment”的叙事要具体得多，也更有说服力。

### 但蒸馏有一个根本性的代价：泛化的缺失

如果故事到这里就结束了，那蒸馏确实是一个”银弹”。但 2025
年的一篇重要论文揭示了一个根本性的限制。

Chu et al. 在 ICML 2025 上发表了 “SFT Memorizes, RL
Generalizes”（Google /
Berkeley）。他们的实验设计很直接：在同一组任务上对比
SFT（蒸馏的底层机制）和 RL
的表现，然后测试两者在训练分布之外（OOD）的表现。

结果很清晰：RL 模型在 OOD 任务上有 3.5-11% 的正向迁移，而 SFT 模型在
OOD 上退化高达 79.5%。

回到家教的比喻：抄了解题套路的学生在考试范围内可能比自学的同学分数更高（DeepSeek
的数据证明了这一点）。但如果出题超出考试范围，自学的同学反而更稳。蒸馏模型记忆了解题模板，但没有学到底层的泛化能力。

DeepSeek 自己的数据也印证了这个限制。完整的 R1（经过 RL 训练）在 AIME
2024 上是 79.8%，蒸馏版最高只到 72.6%（32B）。在 LiveCodeBench 和 GPQA
Diamond 上差距更大。而且蒸馏版在稍微改变题目表述时会有 6-14%
的准确率下降（MathGPT.AI
分析），这正是”记忆而非理解”的典型表现。

2025 年 6 月的一项研究进一步确认了领域限制：R1
蒸馏版在医疗领域的准确率比 Qwen-Base 低 14.7%（arXiv:2506.02126）。数学推理的思维框架可以搬，但医学知识搬不了。

Mistral 的 Magistral（2025）提供了一个很有说明力的对照：纯
RL 训练（不用蒸馏）在 AIME 2024 上达到 73.6%，而且数学 RL
训练带来的能力自动迁移到了编程领域。这种跨领域迁移是蒸馏做不到的。

## Agentic 数据：2026 年的新战场

前面的分析主要围绕推理链展开，但 Anthropic
的指控里还提到了另一类数据：tool use、agent reasoning、代码生成。这类
agentic 数据在 2026 年变得特别重要，因为 agent
已经成了各家模型的主要竞争维度。

### 为什么 agentic
轨迹和推理链不一样

推理链教的是”怎么拆解一个数学题”，agentic
轨迹教的是”怎么和外部世界交互”：什么时候该调用搜索引擎、拿到结果后怎么判断下一步、多步执行中怎么处理错误和分支、怎么在多个工具之间做编排。这是一种不同类型的能力。

而且制造高质量的 agentic 训练数据本身就是一个完整的工程
pipeline。Kimi K2 的技术报告（arXiv:2602.02276）记录了
Moonshot
是怎么做的：构建带持久状态的合成工具环境，创建有多样化沟通风格的模拟用户，生成多轮
tool_call/tool_response 交互轨迹，用 LLM judge
过滤只保留成功的轨迹，然后用这些数据做 SFT + RL。整套 pipeline
不依赖任何外部 API。

如果后发者能直接从前沿模型的 API 里收集百万条 tool-use
轨迹，就可以跳过这整个 pipeline
的构建。逻辑和推理链蒸馏一样：蒸馏推理链跳过的是 RL 的研发成本，蒸馏
agentic 轨迹跳过的是合成环境和 trajectory pipeline 的构建成本。

### 时间线
cross-check：三家公司的故事完全不同

Anthropic
的报告把三家公司放在一起讲，但仔细看数据，它们做的事情差异很大。更重要的是，把指控的时间线和各家模型的发布时间对照，会发现
correlation 的强度完全不同。

MiniMax：correlation 最强。 MiniMax 贡献了总调用量的
81%（1300 万次），主要提取 agentic coding 和 task orchestration
能力。Anthropic 描述的行为模式非常具体：他们抓到 MiniMax
的蒸馏活动时，M2.5 还没发布。Claude Opus 4.6 在 2 月 5 日上线后，MiniMax
在 24 小时内就把一半流量切到了新模型。M2.5 最终在 2 月 12
日发布，被评价为”接近 Claude Opus 4.6 性能但成本低得多”。从 MiniMax
蒸馏活动的规模、时间点和行为模式来看，蒸馏数据和 M2.5
的研发之间存在直接的时间关联。

Moonshot：独立 pipeline 有文档，但时间上有重叠。
Moonshot 的 340 万次调用目标是 agentic reasoning、tool use 和 computer
vision。但 Kimi K2 的技术报告（2025 年 7 月发表在
arXiv）详细记录了自研的 trajectory 生成 pipeline。K2.5 在 2026 年 1
月发布，带有 Agent Swarm（100 个并行 sub-agent）和 PARL（Parallel-Agent
Reinforcement Learning）。这两个都是 Claude 里没有的独立创新。Anthropic
的报告说蒸馏活动”跟随 K2.5 的 1
月发布”，这意味着这些数据可能是在喂后续模型而非 K2.5 本身。Moonshot
的情况更像是：有独立的研发能力，但同时也在从 Claude 那里补充数据。

DeepSeek：correlation 最弱。 DeepSeek
的调用量最小（15 万次，不到总量的 1%），而且目标不是 agentic
数据，而是推理链和 RL reward 信号。更关键的是时间线：DeepSeek
的主要能力跃升（V3 在 2024 年 12 月，R1 在 2025 年 1 月）发生在被指控的
Anthropic 蒸馏活动开始之前（约 2025 年 7 月）。R1 论文 2025 年 9
月发表在 Nature，经过同行评审确认
GRPO 方法论是独立创新。后续的 V3.1（2025 年 8 月）和 V3.2（2025 年 12
月，带有
Thinking-in-Tool-Use）的进步幅度和时间间隔也更符合持续迭代而非蒸馏驱动的突变。

值得一提的是，OpenAI 的调查是一个独立的故事：Microsoft 在 2024
年秋季检测到 DeepSeek 相关账户对 OpenAI 系统的可疑活动。这和 Anthropic
的指控是不同的事件、不同的时间、不同的目标。

### Agentic 蒸馏的窗口期

把三家公司的故事放在一起看，一个模式浮现出来：蒸馏 agentic
数据最有价值的时间点，是在后发者自己的 agentic
产品还没有足够用户数据的阶段。一旦有了自己的产品和用户流量，就有了自己的
trajectory 数据来源。

Cursor 是正面的例子。它拿了开源的 Kimi K2.5
作为底座，用自己的用户编程数据做 RL 后训练（Phil Schmid 分析,
2026）。它不需要蒸馏 Claude 或 GPT-4 的 agentic
轨迹，因为它自己就有数百万次用户编程会话作为训练数据。这是 agentic
数据的正当获取路径：用自己的产品流量产生训练数据。

到了 2026 年初，Kimi K2.5 有了 Agent Swarm，GLM-5 在 SWE-Bench 上达到
77.8%，DeepSeek V3.2 有了 Thinking-in-Tool-Use。这些公司已经有了自己的
agentic 产品和用户基础。蒸馏前沿模型的 agentic
轨迹作为冷启动策略的价值，在这个时间点已经大幅降低了。

## 所以到底省了什么

回到最初的问题。蒸馏对后发者的帮助，和大多数文章描述的不一样。

常被提到的那些好处大多站不住脚：省训练计算成本（不省）、免费获得
alignment（安全审查维度不匹配，行为格式太便宜）。这些判断不变。

但有一个好处比我们最初预想的要大：跳过 thinking trace
construction 和 agentic trajectory pipeline 的整个研发过程。
前沿实验室花了巨大投入才让模型学会推理和工具使用，后发者通过蒸馏可以直接获得这些成果。920
条样本的推理链蒸馏就能超过从头 RL 训练的模型。on-policy 方法（2025-2026
年的最新进展）进一步提升了效果，14B 学生模型可以接近 GPT-5
教师水平。而且 Anthropic 自己的指控数据显示，agentic 数据（tool
use、agent reasoning）正是蒸馏活动的主要目标。

但这个好处有两个根本性的限制。

第一是泛化的缺失：蒸馏出来的模型在训练分布内很强，分布外会脆。SFT
记忆模板，RL 学到泛化。

第二是时效性：蒸馏作为冷启动策略的价值会随着后发者自身产品的成熟而递减。一旦有了自己的用户流量和
agentic 产品，后发者就有了自己的 trajectory 数据来源。Anthropic
指控中三家公司的差异化时间线印证了这一点：DeepSeek
的能力跃升在被指控之前就已经发生（Nature 确认独立创新），Moonshot
有公开文档证明的自研 pipeline，MiniMax 的 correlation
最强但它的故事也说明蒸馏提供的是追赶加速而非持续优势。

这意味着蒸馏是一个快速追赶策略，不是一个长期竞争策略。后发者面临的选择不是”蒸馏还是不蒸馏”，而是”先蒸馏快速追上，然后在什么时间点开始建自己的
RL pipeline 和 agentic 数据飞轮”。

DeepSeek 自己就是这条路径的最佳范例。它的 R1 论文被 Nature
确认 为独立创新。它的竞争优势不是来自蒸馏谁的输出，而是来自自己的
post-training 方法创新（GRPO、四阶段 pipeline、R1-Zero
实验）。蒸馏可以帮你追上当前的前沿，但要超越前沿，你需要自己的 RL
pipeline。

## 来源索引

学术论文（同行评审）

Hinton et al., “Distilling the Knowledge in a Neural Network,” 2015. arXiv:1503.02531

Sanh et al., “DistilBERT,” 2019. arXiv:1910.01108

Hsieh et al., “Distilling Step-by-Step!” ACL 2023. arXiv:2305.02301

Gudibande et al., “The False Promise of Imitating Proprietary LLMs,” ICLR 2024. arXiv:2305.15717

Mukherjee et al., “Orca,” 2023. arXiv:2306.02707

Li et al., “Structure, not content, is what matters!” EMNLP 2025. arXiv:2502.07374

DeepSeek-AI, “DeepSeek-R1,” 2025. Nature / arXiv:2501.12948

Chu et al., “SFT Memorizes, RL Generalizes,” ICML 2025. 论文

Hu et al., “Why Distillation can Outperform Zero-RL,” 2025. arXiv:2505.21067

Ye et al., “GAD: Black-Box On-Policy Distillation,” 2025. arXiv:2511.10643

Qwen Team, “Qwen3 Technical Report,” 2025. arXiv:2505.09388

Mistral AI, “Magistral,” 2025. arXiv:2506.10910

Ouyang et al., “InstructGPT,” NeurIPS 2022. arXiv:2203.02155

Zhou et al., “LIMA: Less Is More for Alignment,” NeurIPS 2023. 论文

Meta, “The Llama 3 Herd of Models,” 2024. arXiv:2407.21783

Song & Zheng, “A Survey of On-Policy Distillation for LLMs,” 2026. arXiv:2604.00626

技术博客与独立分析

Nathan Lambert, “Frontier Model Post-Training.” 分析

Nathan Lambert, “DeepSeek R1 Recipe for o1.” 分析

Thinking Machines Lab, “On-Policy Distillation.” 博客

Epoch AI, “What went into training DeepSeek.” 分析

Stanford CRFM, “Alpaca.” 博客