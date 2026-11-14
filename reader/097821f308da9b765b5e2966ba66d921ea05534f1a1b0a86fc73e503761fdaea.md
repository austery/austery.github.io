---
layout: post.njk
source: https://yage.ai/share/prompt-injection-harness-eval-20260802.html
speaker: yage.ai
title: |-
  打破 99% 安全假象：为什么 Prompt Injection
  的防线与评测都在 Harness？
date: '2026-08-02'
summary: 文章探讨了Prompt Injection（提示词注入）在Agent时代面临的安全挑战，指出传统的模型微调或更换无法解决问题。核心观点是安全防护的有效性取决于外部工具链和运行时策略（如Harness）的边界控制，而非模型本身的内生属性。文章还批判了现有评估体系中存在的五大陷阱，包括静态评测集过拟合、LLM-as-a-Judge带来的漂移以及忽视Utility Under Attack等问题，强调构建基于系统架构隔离和确定性Harness控制的防御体系才是工程实践中的关键。
area: tech-engineering
category: ai-application
tags:
  - prompt-injection
  - agentic-workflow
  - harness
  - system-architecture
people: []
companies_orgs: []
products_models: []
media_books: []
draft: true
status: evergreen
---

安全研究界在 Ghostcommit 实验里展示过一个让人警醒的现象：在同一份
Sonnet 模型权重下，Claude Code 连续测试 10 次都拒绝了来自 PNG
图片内部的恶意指令；然而把同样的图片放入 Cursor 与 Antigravity 中，系统
10/10 顺从了图片里的指令，将 .env
文件中的敏感信息编码为整数常量并提交到了公开仓库。研究者随后在 Gemini 与
GPT-5.5 上也观察到类似的宿主环境差异（详细实验见 Ghostcommit
分析报告）。

同一模型在不同 Harness
中的安全结果并不相同：外部内容进入后，真正决定能否触达敏感资源的是工具边界与运行时策略。

这就是提示词注入（Prompt Injection）在 Agent 时代最典型的威胁变种。当
Agent 开始具备读取外部文件、PNG 图片、网页或 PR
评论的能力时，攻击者只要把控制指令藏在数据中，就能让 Agent
误以为这是用户的真实意图去执行。按理说，行业对 Prompt Injection
并不陌生，各大厂商和榜单上也充斥着“99% 防御成功率”的喜报。但 Ghostcommit
实验打破了这个普遍的安全假设：安全防护并不是通过更换或微调模型即可自动获得的内生属性。同一个模型权重，仅仅改变外部工具链与
Harness 交互壳，敏感数据泄露率就从 0/10 上升至
10/10。在真实生产环境中，Agent 防线常常因宿主环境的轻微变动而失效。

## 实验室安全假象：解构
Prompt Injection Eval 的五大陷阱

要解释为什么实验室里的喜报到了工程现场会失效，首先需要审视我们用来评估
Prompt Injection
的“尺子”出了什么问题。过去大家习惯看排行榜数字，但主流评测体系其实潜藏着五个设计缺陷。

最先失指的是静态评测集本身。厂商在训练时可能对公开 Benchmark
产生过拟合，OpenAI 在 GPT-5.2 System
Card 中明确写道，Agent JSK 和 PlugInject 是训练数据的
split，因此不代表模型对新型攻击的泛化能力。OpenAI 在 2025 年 12 月发布的
ChatGPT Atlas 博客中进一步明确表态，Prompt Injection
很难被完全解决（相关分析可见 Oleria
研发博客）。英国国家网络安全中心 NCSC 的 官方技术声明
也指出，Prompt Injection 不像 SQL
注入那样容易通过形式化的输入与代码分离彻底消除；这说明不能把安全性押在纯模型侧技术上。

当我们跨榜单对比攻击成功率 ASR（Attack Success Rate）时，尝试预算
Attempt Budget
的差异揭示了一个不对称的现状：攻击者并不只攻击一次，且只需要成功一次。Chouldechova
等人在 NeurIPS
2025 论文 与 promptfoo
评测分析 中揭示了不同 Benchmark 在 Attempt Budget
设定上的显著差异。若把单次 ASR 为 1% 的独立尝试简单外推到 392
次，至少一次成功的概率约为
98.0%；但真实攻击未必独立，防御也可能因上下文变化而改变，因此这只能说明预算对结果的敏感性，不能直接当作每个系统的实测攻破概率。

更棘手的是依赖 LLM-as-a-Judge 带来的评估漂移。像 BIPIA
这种早期评测使用 GPT-3.5
作为自动裁判，但裁判模型在读取包含恶意注入的上下文时，更容易被干扰或者带入固有的偏好偏差。评测实验表明，仅更换裁判模型，排行榜上的防御排名就会发生多达
14 个百分点的位移。为了消除这种判定漂移，AgentDojo 在 AgentDojo
Leaderboard 中弃用了 LLM 裁判，全面转向了基于代码与工作区实际状态的
Formal State Check 确定性核验。

很多纯攻击测试集还忽略了 Utility Under Attack
这一关键指标。InjecAgent、BIPIA 和 AdvBench 等测试主要报告
ASR，忽视了过度拒答对 Agent 正常可用性的破坏。Alex Becker 就对
InjecAgent 的威胁模型提出了批评，指出其通过修改 Planner 的 Tool 列表并将
Tool 输出直接插入上下文轮次，可能测量了模型对 Tool-Calling
的忠实度，而非 Prompt Injection 防御能力。AgentDojo
的做法则更有实战意义，它同时测量基线任务完成率 Benign Utility（Claude
3.7 Sonnet 为 88.66%）、遭攻击时的任务完成率 Utility Under
Attack（77.27%）与 Targeted ASR（7.31%）的三维平衡。

脱离系统 Harness 的裸模型 API
测试模式，更是偏离了真实的工程现实。许多评测将模型 API
视作孤立节点，切断了环境交互、文件解析、系统 Hook
与权限控制链条，导致得出的安全数据难以映射到包含真实工具壳的工程实践中。

## 物理根因与动态对抗：为什么
LLM 能力日新月异，Prompt Injection 却无法在模型层收敛？

当看到 LLM
的通用推理与代码能力以月为单位高速迭代时，很多人会产生一个直觉：随着基座模型越来越聪明，Prompt
Injection
这个漏洞早晚会被模型自己收敛解决。然而现实却是，模型能力日新月异，Prompt
Injection 却依然坚固。这背后是由两大核心原因决定的。

第一大原因是当前 LLM
上下文处理路径缺少可靠、不可绕过的指令与数据硬隔离。在传统计算机架构中，程序指令与数据可以通过内存权限和语法边界建立更明确的分离；而在常见的
LLM 应用里，系统 Prompt、用户输入、外部网页、图片文字和 Tool Call
返回值最终都会进入模型可注意到的上下文。即使应用用标签或分隔符标记来源，模型仍需通过概率性理解来决定哪些内容具有指令效力。当攻击者把恶意指令藏在
Tool 返回值或图片里时，模型就可能把数据当成指令执行。

这种上下文混流与指令跟随能力的叠加，引发了一个违反直觉的模型能力悖论：基座模型的理解与推理能力变强，并不自动带来更强的抗注入能力。因为更强的模型在精准执行正向指令的同时，也可能更敏锐地理解并顺从隐藏在未信任数据里的注入指令。Luca
Sambucci 转述的 Gemini
研发团队测试表明，推理提升并没有带来对投毒数据的免疫。在 ARPIbench
的公开测试中，Llama-3.3-70B 的 ASR 高达 99.9%，显著高于参数量较小的
Llama-3.1-8B（94.2%）。Anthropic 的官方 System Card
中也记录了类似现象：当 Opus 4.6 开启 extended thinking
深度思考模式时，其在 ART 评测集上的 ASR 反而从 14.8% 上升到了
21.7%。这说明更多推理计算并不保证更强的抗注入能力。

第二大原因是安全对抗的动态演进属性。Prompt Injection
防御不是一个静态的模型训练任务，而是一个矛与盾持续升级的动态博弈。模型能力在进步，攻击者的攻击手段与自动化优化也在同步进化。攻击者会持续探索与利用潜在的薄弱点，这决定了防守方在模型层写再多规则也无法一劳永逸。一项由
OpenAI、Anthropic 和 Google DeepMind 的 14
位研究者联合发起的自适应攻击研究（论文见 arXiv:2510.09023，总结分析见
博客解读）清楚地展示了这一点。研究团队测试了包括
StruQ、SecAlign、MetaSecAlign、Spotlighting 与 Prompt Sandwiching 在内的
12 种此前在论文中声称接近零 ASR
的模型层防御方案。在面对梯度下降、强化学习、随机搜索以及人类红队组成的自适应动态攻击时，超过
90% 的防御方案被击穿，其中人类红队的攻击成功率达到了 100%。

这种动态博弈与上下文混流共同印证了 Ghostcommit
实验揭示的核心真相：ASR 并不是模型权重内生的静态属性，而是一个受宿主环境
Harness
决定的系统变量。单靠提示词包裹或模型微调，无法在动态对抗中建立稳定防线。

把不可信内容限制在低权限摘要层，再由
Harness 决定哪些结构化结果可以触达高权限工具。

## 落地指南：架构隔离与
Harness 工程防护

当意识到单点模型的评测充满假象、物理层存在架构缺陷与动态博弈、且模型层防御在自适应攻击下几乎全灭时，真正的工程解法必须全面转移至系统架构隔离与确定性
Harness 控制。

在系统架构设计上有着清晰的隔离解法。Google DeepMind 提出的 CaMeL
架构通过将受信规划器 Trusted Planner 与非受信执行器 Untrusted Executor
分离，确保控制流由规划器生成，而非信任的数据仅在执行器的隔离数据通道中流动。OpenClaw
采用的双 Agent 隔离方案则让 Agent 1
仅负责对外部不可信输入进行结构化摘要，Agent 2
在不直接接触原始未过滤文本的前提下执行 JSON 格式化工具调用；在 649
个攻击样本的测试中，该方案将 ASR 从 100% 降至 0.31% 并最终收敛至
0%。需要指出的是，这类架构隔离方案是通过分离执行路径来降低风险暴露，若后续攻击突破结构化格式限制，依然需要配合底层的物理沙箱。

在 Harness 工程层，真正能挡住攻击的是那些确定性规则与配置防线：

必须建立起确定性的工具执行拦截机制。对于涉及文件修改、代码提交、网络外发与凭证读取的高危操作，必须由
Harness
层强制触发鉴权逻辑与确定性检查，而非依赖模型自行判断是否拒绝。

系统配置文件与 Hook 的安全边界也往往是容易忽视的环节。CVSS 评分 8.8
的 Claude Code CVE-2025-59536
漏洞表明，.claude/settings.json 中配置的 Hook
可以在用户信任弹窗弹出之前、模型开始运行之前自动执行任意代码。这证明
Harness
自身的配置文件与扩展机制具备独立的攻击面，必须实施严格的签名校验与隔离保护。

在运行环境上，实施沙箱隔离与最小权限管控是基础的工程防线。将 Agent
的运行环境限制在容器或微虚拟机内，限制网络出站访问与文件系统读写范围，确保即使模型理解被绕过，系统层面的权限边界依然能够遏制损害扩散。

Prompt Injection
的安全治理并不取决于寻找一个免疫攻击的模型，而在于构建能够容忍模型不确定性的
Harness
与架构边界。通过解构评测假象与物理悖论，并在系统层落实确定性控制，才能在不牺牲可用性的前提下建立稳健的
Agent 安全体系。