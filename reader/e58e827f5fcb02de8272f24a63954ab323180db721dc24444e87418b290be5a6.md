---
layout: post.njk
source: https://yage.ai/share/simulator-collapse-deepseek-harness-20260815.html
speaker: yage.ai
title: |-
  同一个模型差 20 分：DeepSeek 的 harness
  依赖性和合成数据的隐藏天花板
date: '2026-08-15'
summary: 文章探讨了同一个模型在不同运行环境（harness）下表现剧烈波动的现象，揭示了模型性能高度依赖于其所处的特定环境。通过分析 DeepSeek 的测试结果和相关研究，文章指出模型性能的瓶颈不再是模型本身的能力，而是训练环境的行为分布的宽度，即 'simulator collapse' 机制。作者认为，解决这一问题的关键在于拓宽训练环境的行为分布，而非简单地升级测试容器，并提出了通过引入 Verbalized Sampling 和 Co-Training 等方法来增强环境反馈多样性的改进路径。
area: tech-engineering
category: ai-application
tags:
  - model-harness
  - simulator-collapse
  - agent-workflow
  - data-distribution
  - co-training
people: []
companies_orgs:
  - DeepSeek
products_models:
  - DeepSeek V4 Flash
media_books: []
draft: true
status: evergreen
---

DeepSeek V4 Flash 的官方跑分相当亮眼：13B 激活参数的 MoE
架构，价格只有同级模型的几十分之一，在 Terminal-Bench 2.1 上拿到 82.7
分，Toolathlon-Verified 70.3 分，Cybergym 76.7
分。但把同一个模型套进不同的运行环境，同一批任务的成绩就会剧烈波动。

2026 年 8 月，Composio
把 DeepSeek V4 Flash 接入 8 个不同的 agent harness，测试同样的 30 个
SaaS 工具调用任务。在模型完全不变的情况下，Pi Agent 跑通了 20
个任务，胜率 66.7%；而 OpenCode 只过了 14 个，胜率
46.7%。同一个模型，只因为换了 harness，通过率就差了 20 个百分点。（36kr
同步报道了这次测试。）

类似的偏差也出现在第三方复现中。Artificial Analysis 用自己的
harness 独立复现 DeepSeek V4 Pro 的 Terminal-Bench 2.1 时，只拿到 79
分，比官方公布的 87.9 分低了 9 分。Cloud Codes 在分析这笔差距时指出，87.9
分跑在 DeepSeek 自己的 harness 上，79
分则跑在外部环境里。跑分从来不只是模型自身的能力，而是模型与脚手架叠加后的综合输出。Hacker
News 上有人直接问了：“我们到底在测模型还是在测
harness？”

为什么换了脚手架成绩差距这么大？答案其实藏在 DeepSeek 自己的 API
changelog 里。官方 benchmark 表格下方有一行脚注：所有代码 Agent
任务的测试，都跑在 DeepSeek Harness 的 minimal mode
上。这个精简模式只提供常驻 bash 和 str_replace_editor
两个工具，没有加入网络搜索、技能库、子 Agent
或规划模块。在这个专门裁切过的极简环境里，模型跑得很顺；但只要离开这个环境，测试通过率就会掉下来。Agent
性能依赖 harness
本来是行业常识，但这行脚注暴露出的问题更具体：模型的高分表现，高度绑定在一个特定的极简运行环境上。

同一束光照只照亮了一个面，其余部分留在阴影里

## DeepSeek 为什么只能这么做

DeepSeek
走到这一步，背后既有技术路径的选择，也有产品形态的限制。首先是技术基因的惯性。从
R1-Zero 开始，DeepSeek
就全面转向合成数据，用数学和编程领域生成的合成数据来提升模型推理能力，证明了不用大规模人类标注也能训出强推理能力。这类单轮任务有明确的客观标准：数学题有唯一解，代码跑没跑对可以直接判定。R1-Zero
的成功奠定了合成数据的方法论。到了 V4 Flash 0731 版本，后训练依然沿用这条路线：按领域切分专家模型，用
SFT 和 GRPO 训练各个专家，最后合并蒸馏。GRPO
是一种组内相对强化学习算法，它直接在同组生成的多个采样之间按奖励比较优劣。这种算法特点，和后面暴露出的环境依赖直接相关。

这套合成数据路线在单轮任务上行得通，因为数学题有标准答案，代码能不能跑通有客观判定，合成数据可以自带
verifier。但多轮 Agent 任务不一样。一个客服 agent
要跟用户来回对话好几轮，一个编程 agent
要反复执行工具、看报错、再改，它的 reward
来自整个交互序列，没有标准答案可以提前判定。这时候训练环境里的用户行为或工具反馈本身就决定了模型学到什么策略，环境的行为分布就是训练分布。合成数据可以造出任务，但很难造出足够多样、足够真实的交互轨迹来覆盖各种用户反应。

这就引出了 DeepSeek 的数据难题：它没有大规模真实用户行为轨迹。OpenAI
有 Codex，Anthropic 有 Claude Code，Cursor 有自己的 IDE，这些产品是
agent
任务的执行环境，也是收集真实编程交互数据的入口。用户在实际使用中怎么澄清需求、怎么根据报错改代码、什么情况下选择放弃、哪些任务需要多轮迭代，这些行为轨迹都沉淀在厂商的基础设施里，成为在合规前提下优化模型
agent 能力的真实底料。ChatGPT 和 Claude
的订阅产品本身拿不到编程场景的真实交互数据，聊天界面和 agent
执行环境是两回事。DeepSeek
连前者都没有，后者更是长期空白。它的服务主要走
API，长期没有自有的终端产品和交互界面。我们在此前分析
coding agent 形态变化时已经指出，DeepSeek 一直不发布 first-party
harness，把执行环境里的行为数据入口让给了第三方。直到 2026 年 8 月 13
日发布 DSH（时间线见
orcarouter），DeepSeek 才第一次拥有了自己的
harness。开发者用它的模型搭 Agent 时，所有行为轨迹都留在 Codex、Claude
Code 或 OpenCode 这些第三方工具里，数据流不回 DeepSeek。

这里需要说明一点：没有自有终端产品就无法直接收集大规模真实用户行为数据，这是基于
DeepSeek 产品形态的逻辑推论，不是 DeepSeek
官方表述。但产品形态是公开事实，推论链条很短。

技术惯性与数据短板就这样成了一个循环：对合成数据的依赖，放慢了搭自主
harness
收集真实数据的步伐；而真实行为数据的匮乏，又反过来逼着训练继续靠合成环境。多轮交互成为
Agent 训练的主战场之后，这个瓶颈就暴露出来了。

## 合成数据的天花板终于有了量化

2026 年 8 月 12 日，来自 Stanford、UC Berkeley、Northeastern、NYU 和
UW 的联合团队发表论文《One
Frozen Simulator Is Not Enough: Simulator Collapse in Multi-Agent
RL》，揭示了一种叫 simulator collapse 的坍缩机制，正好解释了
DeepSeek 的 harness 依赖现象。论文指出了单模拟器训练的核心缺陷：只用单个
LLM 充当用户模拟器来训练
Agent，模型演化出的策略会专门针对这个模拟器的特定响应模式找捷径，对多样化的人类行为反而失去了适应能力。

经过对齐的 LLM 普遍存在 mode collapse
倾向，容易抑制边缘分布而集中输出高频典型回复。把这种模型当成环境模拟器，它在交互每一步给出的反馈都高度单一。Agent
的训练梯度因此集中在这种主导模式上，优化方向逐渐变成如何在固定回应下刷高分。随着强化学习继续跑，交互路径的多样性快速下降。研究团队追踪了训练过程，发现两个清晰的信号：同一批采样里，整组对话拿到的
reward 越来越趋同，最后超过 85% 的 batch
里所有样本分数完全一样，模型在这些 batch
上学不到任何区分性的信号；与此同时，策略熵从 1.9 nats 一路跌到 0.4
nats，意味着它几乎只产出同一种对话路径了。

这种坍缩会导致训练指标和泛化能力走向背离：虽然模型在训练环境里的
reward
一直在涨，但只要换到没见过的模拟器或真实人类场景，实际胜率就会掉下来。研究团队做了一项包含
320 个 Prolific sessions 的人类实验，让 Agent
执行劝说捐款任务。结果显示，用单一模拟器训练出来的 Agent，平均只筹到
0.46 美元捐款，反而低于未经强化训练的基线模型（0.51 美元）。

论文测试了 GPT-5-mini、Haiku-4.5 和 Gemini-3-Flash
三个不同家族的模拟器，都观察到了坍缩现象。哪怕把策略模型规模从 4B 扩大到
8B，坍缩依然会发生。这说明瓶颈不在于模型或模拟器的绝对大小，而在于环境行为分布有多宽。

论文发现的这种坍缩机制，正好对应上 DeepSeek 的测试表现。DeepSeek V4
Flash 0731 版本在后训练中用了 GRPO 算法。GRPO 的核心是 group-relative
advantage，也就是在一组采样序列里，通过奖励的均值和方差归一化来算相对排名。这和
simulator collapse 论文采用的组内奖励归一化机制，在算法逻辑上同源。

根据公开证据，可以推导出一个合理的解释：0731
版本的更新只改了后训练阶段，底座架构和参数没变，而官方公布的基准测试又全部跑在只给
bash 和 str_replace_editor 的 DSH minimal mode 上。如果在后训练时，Agent
loop 的实际运行模式和 minimal mode 高度重合，缺少网络搜索、子 Agent
协作和复杂规划，模型学到的最优策略就会深度绑定在这个特定环境里。跑在官方
harness 里时，任务还在训练分布内；一旦换到第三方
harness，环境一变，模型就跌出了训练分布。

需要明确说明的是，上述关于 harness
过拟合的逻辑属于基于公开证据的推论，并非 DeepSeek
官方确认。在没有公开训练日志的情况下，后训练时 Agent loop
的确切配置还无法确定。但从 0731 只改动后训练、官方高分绑定 minimal
mode、第三方复现成绩下滑，以及论文对坍缩机制的验证来看，这个推导有连贯的证据支撑。

## 为什么换个更好的 harness
不解决问题

模型换了环境成绩掉下来，直觉上的解决思路往往是升级测试容器，开启包含搜索、子
Agent 和规划能力的 Standard mode，想把分数拉回来。Simulator collapse
论文否定了这种简单替换的做法。研究显示，从 GPT-5-mini 到
Gemini-3-Flash，不同家族的模拟器无一例外都触发了坍缩。问题的根源不在于模拟器本身强不强，而在于它的行为响应分布太窄。对齐后的
LLM 自带 mode collapse
倾向，光靠换个模型，解决不了输出模式同质化的问题。

对应到 harness 上也是一样。如果训练时模型只接触过 minimal mode
的行为轨迹，到了推理阶段再换
harness，改变的只是暴露过拟合问题的程度，并没有解决训练时留下的分布偏差。即便在
Standard mode 下测出的成绩可能比 OpenCode 高，也只是因为 Standard mode
的工具配置离训练条件更近一点。这依然是原训练分布的局部延伸，算不上独立的泛化检验。

要解决这个问题，论文提出了两条改进路径，核心都是拓宽环境的行为分布，而不是去调整策略层面的探索调度。第一种方法是在推理阶段加入
Verbalized
Sampling。它要求模拟器在生成回复前，先输出候选文本列表和对应的概率分布，再从中采样。这样做能强行调出那些本来概率较低、模型容易忽略的非典型回复，重新恢复环境反馈的多样性。这种机制不需要重新训练模型，只增加推理时的解码计算量，就让
held-out 场景下的任务成功率最高提升了 9%。

第二种方法是在训练阶段引入
Co-Training。让模拟器和策略模型同步迭代更新，使模拟器的响应特性随着训练不断漂移。策略模型之前找的捷径会随着环境改变而失效，从而逼着策略维持泛化能力。论文还设计了
Population Co-Training 的增强版，每轮训练都从最近 5 个模拟器 checkpoint
里随机抽一个作为对战环境，最终把 held-out 成功率最高提升了 14%。

这两种方案的共同点，都是在拓宽训练环境的反馈分布。这也正好映照出
DeepSeek 之前的短板。在没有 first-party harness 的阶段，DeepSeek
训练环境的反馈分布完全由合成数据塑造，宽度上限受限于合成规则覆盖的范围。发布
DSH
为它打开了收集真实用户行为轨迹、拓宽分布范围的通道；不过因为这个工程刚刚上线，数据的积累才刚刚开始。

## DSH 是 DeepSeek
对这个天花板的回应

用 simulator collapse 论文的框架重新看
DSH，能对其架构设计有更深的理解。之前我们详细分析过
DSH 支持热替换 Agent loop
的特性，把它看作一种自进化基础设施。但如果放在多 Agent
强化学习的视角下，这种设计其实就是 Co-Training 思想在 harness
架构上的工程落地。

Co-Training
的核心逻辑，是让训练环境和策略模型同步演进，避免策略过拟合到单一的环境响应模式上。DSH
把 agent loop
拆成了可以在运行时动态加载的插件，让训练环境能够随着策略迭代跟着调整。如果
DeepSeek 在后面的后训练流程里引入 DSH 的多元 agent loop
配置，而不是继续局限于 minimal mode，其实就是在环境层面推行
Co-Training。

开源 DSH（代码在
GitHub）的价值，不只是为了方便社区复现已有的跑分。在一个已经过拟合的环境里重演测试，拿到的依然是有偏差的分数。它的真正意义，是把模型训练所依托的环境结构公开出来，让社区共同审计和扩充。通过在
DSH 中调整 agent loop
并观察分数漂移，开发者可以把模型自身的能力与脚手架的辅助作用拆开，这是诊断并纠正策略坍缩的必要步骤。

这些实验和理论框架，给 Agent 研发团队提供了一套明确的诊断依据。当
Agent 在特定训练容器里的 reward 稳步上升，但只要换个
harness、接入不同用户群或切换任务分布，成绩就大幅下滑，这就说明系统陷入了
simulator
collapse。这时候排查的重点，不该盲目去调策略探索算法或扩大模型参数，而应该放在拓宽训练环境的行为分布上。

对 DeepSeek
来说，他们的认知经历了一次转变：从最初相信合成数据能覆盖全流程，到意识到训练环境的分布宽度才是最终的屏障。这个转变推动他们从单纯做模型研发，走向搭建
harness 基础设施。开发 DSH 的初衷，是意识到限制 Agent
性能提升的核心瓶颈已经从模型架构转移到了数据分布。要想突破这个限制，就必须把
harness 的掌控权握在自己手里。至于和 Codex
抢终端市场，那是顺带的事。