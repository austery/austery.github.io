---
layout: post.njk
source: https://yage.ai/share/deepseek-v4-flash-0731-agent-economics-20260801.html
speaker: yage.ai
title: |-
  DeepSeek V4 Flash 0731：用 Nano
  级价格买中端性能，斩杀线叙事遮蔽的真实 Agent 经济学
date: '2026-08-01'
summary: DeepSeek V4 Flash 0731 发布了新的 API 版本，以 Nano 级价格提供中端性能。文章分析了其在性价比上的优势，但指出其真实能力仍处于轻量级定位，并非旗舰模型替代品。核心讨论了API定价、跑分口径差异（Harness）、幻觉率以及Agent生产经济学中的'Cost per accepted task'等工程落地细节。
area: tech-engineering
category: ai-application
tags:
  - model
  - cost-efficiency
  - agentic-workflow
  - harness
people: []
companies_orgs: []
products_models:
  - DeepSeek V4 Flash 0731
media_books: []
draft: true
status: evergreen
---

2026 年 7 月 31 日，DeepSeek 官方通过 Changelog 发布了 API
更新，推出 build 名称为 DeepSeek-V4-Flash-0731 的 Public Beta 版本，API
模型 alias 保持为 deepseek-v4-flash。这次更新仅升级了
DeepSeek-V4-Flash API，网页端与
V4-Pro API 均未做更新。底层架构上，它与 4 月 Preview 版结构相同，依然是
284B 总参数、单 token 激活 13B 参数的 MoE
架构，只是进行了重新后训练（Re-post-trained）。

自媒体与朋友圈迅速被 0731 性能封神、逼近 Opus 4.8、性价比斩杀线等
Headline 刷屏。单从账面上看，它的定价具备明显的低价优势：Cache miss
时输入单价为 $0.14 / 1M tokens，输出单价为 $0.28 / 1M
tokens；而在长上下文触发 Context Cache Hit 时，折扣为 98%，输入单价降至
$0.0028 / 1M tokens。在 Artificial Analysis 测算的
7:2:1（hit:input:output）典型混合工作负载下，综合成本仅约 ~$0.06 / 1M
tokens。对比 GPT-5.6 Sol（$5/$30）、Claude Opus 5（$5/$25）、Sonnet
5（$2/$10）、Gemini 3.6 Flash（$1.5/$7.5）乃至 Gemini 3.1
Pro（$2/$12）等顶级与主力模型，0731
稳居市场最低单价区间。账面标价低，并不等于最终产出便宜，更不等于能力打平了前沿。

API
标价与每个被接受任务的真实成本之间的差距：低单价下仍可能叠加额外
token、重试、工具修复与人工审核成本

在 2026 年 7 月 31 日发布的 Artificial
Analysis Intelligence Index v4.1 独立测量中，DeepSeek-V4-Flash-0731
在 Max effort 设置下得分为 50 分。虽然较 Preview 版的 40 分提升了 10
分，并在开源模型（Open-weights）分类榜中位列 #2（仅次于 57 分的 Kimi K3
max），但若放眼整个大模型市场，50 分的横向定位其实相当于商用中端与轻量
API 模型梯队，即与闭源的 Gemini 3.6 Flash（50 分）、GPT-5.6 Luna（51
分）以及 GLM-5.2（51 分）处于同一水平，距离 60~70+
分的顶级前沿旗舰阵营依然存在明显差距。

综合这些独立测量，其真实的品类定位一目了然：在主流厂商的产品梯队中（从
OpenAI 的 Sol/旗舰、Terra/Mini 到 Luna/Nano，或 Google 的 Pro 到
Flash），Flash 属于位于旗舰之下两档的
Nano/轻量级定位。DeepSeek-V4-Flash-0731 的真正价值，在于它用低于 Nano
档模型的单价，跑出了 Nano
档的性能，在轻量梯队中具备显著的性价比。然而，自媒体与朋友圈的宣传迷思，在于误将一个
Nano/轻量档的模型，包装成了能够直接替代 Sol 或 Opus 这类旗舰级
Controller 的前沿突破者。

## 跑分背后的 Harness 口径真相

在官方 Changelog 中，DeepSWE 的跑分增长最为突出：0731 的得分从
Preview 版的 7.3 分提升至 54.4 分，并在对比表中与公认测试测出的 Opus
4.8（58.0
分）同表展示。在没有改动底层预训练架构、仅靠重新后训练的前提下，一个轻量模型在软件工程测试上取得明显的提升，确实容易引发广泛关注。然而，复盘我们在
2026 年 5 月写的深度分析 《SWE-Bench
Pro
饱和之后，有人做了一把新尺子》，就会发现这里的成绩对比存在需要厘清的机制细节。

在容易发生数据污染与过拟合的 SWE-Bench Pro
榜单上，各大模型得分一度相当接近：GPT-5.5 获得 82.6%，Claude Opus 4.7
获得 82%，Gemini 3.5 Flash 获得 79.8%，DeepSeek V4 Pro 获得 76.2%。当
Datacurve 团队在 5 月推出验证更严格的 DeepSWE
测试时，曾对各大模型进行过一次性审计抽测，成绩发生了明显分化：GPT-5.5
保持在 70%，Opus 4.7 为 54%，Gemini 3.5 Flash 下降至 28%，更高级别的
DeepSeek V4 Pro 则下调至 8%。DeepSWE
这把新尺子的公信力建立在两个核心机制上：一是 113
个由维护者从零撰写且非公开的隐蔽题库（Held-out
Dataset），二是所有模型统一在 mini-swe-agent Harness 测试外壳与同一
Docker 环境下执行评测。

最关键的技术细节在于测试数据集公开后的指标演变。正如古德哈特定律（Goodhart’s
Law）所提醒的：当一个指标变成优化目标，它就不再是一个中立的衡量标准。随着
Datacurve 将 DeepSWE 的任务细节与评估框架通过 GitHub
开源，当测试集的任务结构与验证逻辑公开后，后续的后训练（Re-post-training）与外壳工程自然会围绕该分布进行定向优化。查验
Datacurve DeepSWE 官方公开
Leaderboard，截至 2026 年 8 月 1 日，公开榜单上由 Datacurve
统一盲测的模型中并没有 0731 Flash。而 DeepSeek 官方 Changelog 自报的
54.4 分，标注使用的则是其未公开的 DeepSeek Harness minimal mode。正如 Mehmet
Özel 以及 Hacker News
社区讨论 中 Iolaum
所指出的，在公开数据集上通过自定义外壳跑出的 54.4 分，与标准盲测下测出的
Opus 4.8（58.0
分）同表对比，体现的是外壳与特定数据集分布联合优化的结果，需要结合其绑定环境理性看待。

同名 benchmark 在统一公共 harness
与厂商私有 harness 下的测量口径差异

要理解这里的 Harness
差异，需要明白测试外壳在商业工程中的真实作用。历史上 DeepSeek
专注于底层预训练与强化学习算法，并没有自己的面向 C 端的 Coding
订阅产品（如 Cursor 或 Claude
Code），在评测外壳工程上此前一直存在相对短板。这次 0731 推出自研的
DeepSeek Harness minimal
mode，表明团队开始补齐应用层外壳工程能力。这里的 minimal mode
是大模型评测中的常见术语，指对标 mini-swe-agent 的精简单 Agent
外壳（仅提供基础的文件查看与编辑工具，不叠复杂的 Multi-Agent
架构）。Harness
本质上是包裹在大模型外层的软件工程外壳，负责处理系统提示词包装、工具调用解析、环境状态管理与重试策略。虽然
DeepSeek
尚未开源该外壳的具体源码，但从外壳工程的一般规律来看，自定义外壳通常会针对自家模型的输出习惯优化提示词，并对特定格式瑕疵提供容忍解析。这种工程补强体现了团队在应用层适配上的进步，但也解释了为什么自定义外壳下跑出的分数不能直接等同于标准盲测外壳下的成绩。

## 84% 幻觉率与工具调用格式瑕疵

如果说 Benchmark
的口径差异属于评估维度的细节，那么模型在基础可靠性上的短板，则是影响工程落地的核心因素。Artificial
Analysis 针对模型事实准确度的 AA-Omniscience Index 显示，0731
的幻觉率虽然较 Preview 版的 96% 下降了 12 个百分点，但依然保持在
84%（准确率为 37%）。对比不同梯队模型的表现，Claude Sonnet 5
等旗舰模型的幻觉率通常控制在 37% 左右，Gemini 3.6 Flash 等 Mini 档模型在
55% 左右，而 GPT-5.6 Luna 等 Nano 档模型则在 90% 左右。0731 的 84%
幻觉率，清楚地印证了其处于典型 Nano
档模型的可靠性区间，在面对无法确定的解答时依然倾向于生成内容而非拒答。

这种较高的幻觉率，被其偏长的吐字倾向进一步放大。Artificial
Analysis 测得 0731 在跑完 Intelligence Index 时消耗了 2.06 亿 Output
Tokens（中位数为 9,900 万），Verbosity 评级达到 4/4 满级。我们在 《一张草稿纸，一个
Controller：重新理解大模型推理》 中曾探讨过，Agent
系统能力的天花板取决于 Controller
的确定性与上下文质量，而非单纯的输出长度。冗长的输出增大了潜在的幻觉暴露面，也推高了实际的
Token 消费账单。

在具体的工具调用 Tool Calling
工程落地中，表现出的格式瑕疵更为具体。根据 Ahmad
Awais 与 Kilo.ai
的工程复盘，0731 在工具调用时频繁出现为可选字段发送
null、将 JSON
数组输出为转义字符串、将数组错误包装为单对象，以及将文件路径输出为
Markdown 自动链接（例如
[notes.md](http://notes.md)）这四类格式问题。如果不构建
Tool-calling repair layer（即自动修复畸型 JSON
或路径错漏的代码层），Agent 工作流很容易中断。此外，API
接口层的稳定性也存在适配成本，n8n Issue #29661
与 DeepSeek-V3
Issue #1244 均记录了相关报错与输出格式漂移问题。

## Cost per accepted
task：真实 Agent 经济学算账

抛开跑分细节，站在生产工程落地的角度，评估 0731
需要回归整体算力成本与接受率的平衡。Lindy 的 Bruno Škvorc 在官方博客中分享过，将托管
Agent 流量迁移至 DeepSeek 后推理成本下降了约
90%，但强调单次验证并不等同于长期的产品稳定。Dan Gurgui 在 ArchitectureForGrowth
的实测中记录，在某些切换场景下 Sub-agent 运行时间显著延长且消耗更多
Token，产出依然需要人工审核。这对应了 NxCode
提出的 Agent 生产经济学概念：Cost per accepted
task，即每次被接受修改的真实成本，才是最终的决定性指标。一个单次触发便宜但多次重试的流程，综合成本未必低于单次价格较高但一次通过的流程。

从任务类型的物理特性来看，0731 在 Agent
场景与数据处理场景下的表现存在本质分水岭。在开放式 Agentic
任务中（例如跨多个文件的自主重构或无约束代码研发），问题的决策错误空间很大。一旦子节点在多轮循环的前几步做出错误决策，错误就会呈指数级累积放大，导致模型连续运行半小时、消耗近十万
Tokens 最终依然失败。

相反，在具备强确定性验证机制或低决策错乱空间的数据流水线中，0731
则展现出显著的实用价值。最典型的场景包括大规模数学公式与数据标注打标、配合
Pytest 或 Linter 进行的确定性代码修补，以及基于 Pydantic Schema
的长文档数据提取。在这些任务中，每一步都有硬性的判定规则拦截错误，0731
的低单价与 98% 的缓存折扣可以转化为实际的成本优势。

综合 API 标价、吐字倍率、重试次数与防御层维护成本，要把 0731
用好，工程上需要建立三项关键防线。第一是必须部署 Tool-calling repair
layer 自动修复转义字符串、null 可选字段与 Markdown
自动链接污染；第二是在提示词中硬性设定思维链与输出长度上限，抑制其 4/4
满级 Verbosity 带来的额外 Token
消耗；第三是采用分工明确的混合架构，由前沿旗舰模型担当 Controller
负责规划与审核，将大量细碎的子任务派发给 0731
处理。通过这种架构安排，才能在保证系统确定性的同时，真正释放出低单价模型的经济价值。