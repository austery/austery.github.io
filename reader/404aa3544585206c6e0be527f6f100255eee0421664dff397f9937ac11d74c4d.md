---
layout: post.njk
source: https://yage.ai/share/ai-model-task-dispatch-20260424.html
speaker: yage.ai
title: |-
  GPT-5.5、Claude Opus 4.7、DeepSeek
  V4：什么任务该选哪个模型
date: '2026-04-24'
summary: 本文分析了 2026 年春季发布的 GPT-5.5、Claude Opus 4.7、Gemini 3.1 Pro 及 DeepSeek V4 模型。文章指出，没有单一模型能在所有任务上最优，各模型在编码、推理、事实性、多模态和成本等方面各有优势与短板。作者建议采用团队式 AI 任务分配，并构建支持模型切换的抽象层系统架构，以应对模型能力的“锯齿状前沿”现象，实现效率和质量的最大化。
area: tech-engineering
category: ai-application
tags:
  - llm-selection
  - model-comparison
  - ai-strategy
  - jagged-frontier
  - llm-applications
people:
  - Ethan Mollick
  - Zvi Mowshowitz
  - Cline CEO
companies_orgs:
  - OpenAI
  - Anthropic
  - Google DeepMind
  - DeepSeek
products_models:
  - GPT-5.5
  - Claude Opus 4.7
  - Gemini 3.1 Pro
  - DeepSeek V4
  - Codex
media_books: []
draft: true
status: evergreen
---

2026-04-24 调研。

## 两个可能让你踩坑的场景

先看两件眼下特别容易踩坑的事。

场景一。你的 agent
流水线大量做长文档理解，比如合同分析、long codebase reasoning、把客户的
8 小时会议转录丢进去生成结构化摘要。一直用 Claude Opus 4.6，因为它在 1M
needle-in-haystack 测试上是 91.9%，是所有模型里做长上下文 retrieval
做得最好的。4 月 16 日 Opus 4.7 发布，价格不变，SWE-Bench Pro、AA
Intelligence Index
全线领先，你想都没想就把生产环境切过去了。两天后监控告警开始响：在 600K
以上 token 的任务上，输出质量明显下降，经常漏掉文档后半段的关键事实。翻
Anthropic 的 System Card 才看到那行字，Opus 4.7 在 1M needle-in-haystack
上是 59.2%，比 4.6 退了 32 个百分点。Anthropic 主动把
retrieval 容量换成了 agentic 推理能力。如果你的工作流刚好是
RAG，这次升级对你是明确的倒车。长文档 retrieval 这个位置现在反而是
GPT-5.5 做得最好，Graphwalks BFS 1M 从 GPT-5.4 的 9.4% 跳到 45.4%。把
Opus 的旗舰当成长文档处理默认首选，这个直觉在 2026 年春已经不成立。

场景二。OpenAI 把 computer use 当作 GPT-5.5
发布稿里最亮的新能力之一，附带的 OSWorld-Verified 78.7%
这个分数很扎眼，发布稿还单独强调了浏览器交互和文件操作。看起来马上就能接进你的
agent 产品。你决定下周就把 agent 切到
GPT-5.5，让它能操作用户的浏览器完成自动化任务。打开 Responses API
文档一查才发现，里面的 computer-use-preview tool 还是
GPT-5.4 级别的能力，5.5 的那个 78.7% 并没有同步到 API。那 78.7%
在哪里兑现？答案是 macOS 上的 Codex 桌面应用：你要让用户装 Codex、装
plugin、授予 macOS accessibility
权限，欧盟和英国的用户甚至没法用。你以为你在用 GPT-5.5 的新
capability，实际能拿到的只是一个锁在特定
OS、特定应用、特定地区的产品形态。

这两件事都是用过之后才知道的坑。2026 年春这批 frontier
模型发布密集，每家的强项、短板、接入路径、定价断档都不一样，想用好它们需要自己花时间踩坑、对照
system card、翻 release
note、跟进社区反馈。这篇文章把这些坑整理出来，省掉你自己走一遍的时间。

## 四家模型的能力画像

### GPT-5.5

发布于 2026-04-23。整体定位是全能型选手：agentic
coding、长上下文、reasoning
三个维度同时占第一梯队，但在事实可信度上明显吃亏。Artificial Analysis
Intelligence Index 上发布当天 60 分，领先当时并列第二的 57 分（AA
随后回归更新，目前 GPT-5.4、Opus 4.7、Gemini 3.1 Pro 三家在 57
分档并列，GPT-5.5 的 AA v4.0 完整分数还未公开）。最大的单项优势在
agentic coding loop：Terminal-Bench 2.0 上 82.7%，比 Opus 4.7 的 69.4%
高 13 个百分点，是所有 benchmark
里它领先幅度最大的一项。长上下文这次明显稳了，Graphwalks BFS 在 1M scale
上从 5.4 的 9.4% 跳到 45.4%（OpenAI benchmark
表）。纯推理也在第一梯队，FrontierMath Tier 1-3 是 51.7%、Tier 4 是
35.4%。

代价主要在价格。API 单价翻倍到 $5/$30 per 1M tokens，AA
实测单位任务成本相对 GPT-5.4 上升约 20%（per-token 翻倍 × token 用量减少
40%）。事实可信度是它最大的短板，AA-Omniscience 测出的 hallucination
rate 是 86%，市场几乎倒数，对比 Opus 4.7 的 36%（AA
Omniscience 报告）。OpenAI 自己在 System Card §6.1
里的说法是”individual claims are 23% more likely to be factually
correct”相对 GPT-5.4，但这是 OpenAI 选的评测集，和 AA
独立测量指向不同结论（GPT-5.5
System Card）。把 GPT-5.5
派去做事实敏感任务，你要接受它不知道答案时倾向硬答这个毛病。

### Claude Opus 4.7

发布于 2026-04-16。和 GPT-5.5 的全能路线不同，Anthropic
这次升级明显做了专科化取舍，把 Opus 推到了资深代码工程师这个位置：真实
GitHub issue 修复、tool use
精准度、事实可信度都是市场第一，同时主动放弃了长文档 RAG
和通用对话温度。SWE-Bench Pro 64.3% 是 GA 模型里市场第一，比 GPT-5.5 的
58.6% 高 5.7 个百分点；MCP-Atlas tool use 77.3% 超过 GPT-5.5 的
75.3%；AA 的 GDPval-AA 拿到 1753 Elo，领先第二名 Sonnet 4.6 的 1674 有
79 个 Elo。最明显的变化在 hallucination：rate 从 Opus 4.6 的 61% 降到
36%。这里要把机制分开看。AA 报告显示 accuracy 没变，attempt rate 从 82%
降到 70%，也就是 12 个百分点的硬答换成了承认不知道（AA
Opus 4.7 报告）。4.7 相对 4.6
的改进在于变得更敢拒答，而不是变得更准。

Opus 4.7 为这个定位付出了两个代价。第一是前面场景一提到的 1M 长
context retrieval 从 91.9% 退到 59.2%（Anthropic 自己在 System Card
里披露），主动取舍。第二是创意写作和对话里的温度感。Reddit
在发布当天出现大量 “Opus 4.7 is dogshit”
的帖子，社区反馈说它啰嗦、模板化，原来那股温度没了。boringbot 拿 5
个结构化 PM 任务（PRD、exec summary、RICE、用户研究、GTM）做盲测，Opus
4.7 全部胜出。所以这不算模型退步，是 Anthropic
在主动调整定位。如果你的用户群是文学写作、brainstorm、角色扮演，这次升级对你是负信号；如果是结构化知识工作，正信号。

### Gemini 3.1 Pro Preview

2026 年春 Google 的旗舰推理模型。和 Opus 4.7 一样在 AA Intelligence
Index 上打到 57 档，性价比是最大优势。AA
Cost to Run Index 只要 $892，对比 GPT-5.2 的 $2,304 和 Opus 4.6 的
$2,486，便宜 61%。在几项具体任务上它是明确第一：Video-MMMU
87.6%、ScreenSpot-Pro 72.7%、OmniDocBench 编辑距离 0.115，视频理解、UI
截图操作、PDF 文档抽取这三类多模态任务都是它的主战场。BrowseComp
搜索整合 85.9% 也是第一。

它最大的毛病是社区叫做 parametric hubris
的那个问题：不知道答案时几乎从不拒答，直接自信地编。AA-Omniscience
hallucination rate 88%，比 GPT-5.5 的 86% 还略高；但 accuracy
同样第一（55.9%），知道得最多，也编得最多。一个行为层面的信号最能说明问题：Google
自家的 Antigravity IDE 把它当作 Claude 的
fallback，开发者反馈是在长循环里把代码库写崩（Antigravity
负面 Medium），自家产品用脚投票。另一个短板是长循环 agent
不稳，Terminal-Bench 2.0 只有 68.5%，VERTU 实测还有长 session
内存泄漏。Gemini 3.1 Pro
适合短任务、高价值、多模态或搜索密集的场景，不适合 24/7 跑的自治
agent。

### DeepSeek V4

2026-04-23 和 GPT-5.5 同日发布。DeepSeek
自己在发布材料里给的定位非常直白，落后 frontier 3 到 6 个月、便宜 9 到
30 倍（Gizmodo
转引）。V4-Pro 定价 $1.74/$3.48 per 1M tokens、V4-Flash 定价
$0.14/$0.28，是 GPT-5.5 的 1/9 和 1/30。开源 MIT license 可自托管。

落后 3-6 个月这个说法是对所有任务取的平均，容易让人忽视实际 benchmark
的分化。短任务、可验证答案的代码题上它是市场第一，LiveCodeBench 93.5
分、Codeforces 3206 Elo，都超过 Opus 4.7、GPT-5.4 和 Gemini 3.1
Pro。中文上也是长期领先，Chinese-SimpleQA 84.4，美国 frontier 模型都在
76 左右，差 8 个百分点。技术报告里还披露了一条不起眼但重要的数据，V4-Pro
在 1M context 上只用 DeepSeek V3.2 27% 的 inference FLOPs 和 10% 的 KV
cache（DeepSeek
V4 Technical Report）。换句话说，V4
能便宜下来，有相当一部分来自架构层面的效率提升，不是靠烧钱补贴。

真正的短板在长 horizon agentic。Terminal-Bench 2.0 67.9% 对 GPT-5.5
的 82.7%，差 15 个百分点，是所有 benchmark 里它最大的差距。SWE-Bench Pro
55.4% 也落后 Opus 4.7 的 64.3% 近 9 个百分点。视觉能力也没有，V4 preview
是 text-only。

V4 在商业部署里最大的挑战不在
benchmark，在合规。意大利、台湾、澳大利亚、韩国已禁用 DeepSeek
应用，美国 NASA、海军禁止员工使用，韩国 PIPC 公开报告 100
万韩国人数据未授权流向中国（CSIS
分析）。对金融、医疗、法律、政府类应用来说，走 DeepSeek 官方 API
的方案在 audit
环节过不去。问题不在模型本身，在于数据要流到中国管辖下。开源权重让自托管这条路径开放，这是
V4 跟其他中国闭源模型的核心差异：你可以在自己的 VPC 里跑
V4-Pro，数据不出本地，合规风险降到和任何 open-weight
模型相当的水平。

## 实战中的几个典型坑

能力画像只是一半，另一半是接入时才会发现的细节。下面这几个坑在发布几天后已经在社区里反复出现。

computer use 锁 Codex
桌面应用。前面场景二已经展开。GPT-5.5 的 OSWorld 78.7%
能力目前只在 macOS 上的 Codex 桌面应用里可用，Responses API 里的
computer-use tool 是 GPT-5.4 级别，EU/UK 没开放。如果你做 API-based
agent，这一项拿不到。Opus 4.7 的 computer use 则是走 Messages API 的标准
tool computer_20251124，配合 3.75 MP 分辨率和 1:1
坐标映射，集成成本明显低。OSWorld 分数两家差不到 1 个百分点（78.0% 对
78.7%），但能不能用到完全是两回事。

Opus 4.7 超过 200K prompt 单价翻倍。Opus 4.7 sticker
价 $5/$25 看起来跟 GPT-5.5 持平，实际 200K 以上单价跳到
$10/$37.50，GPT-5.5 全程 flat $5/$30。也就是说长 prompt 场景下，Opus 4.7
的输出反而比 GPT-5.5 贵 25%。Anthropic 的 tokenizer
同时换了，同样内容要算多 1.0 到 1.35 倍的
token，代码和非英语内容膨胀明显。如果你的任务涉及大文档或大
codebase，账单要按 +20% 估。

Gemini 3.1 Pro 的 200K 成本拐点。Gemini 在 ≤200K 是
$2/$12，>200K 翻到 $4/$18。Verdent AI
的工程报告记录了一个典型踩坑，agent 把自己的输出反复回灌到下一轮
context，前三轮还在 200K 以内，到第四轮就跨过阈值，从此每个 token
按双倍价计费（Verdent AI
报告）。这不是模型问题，是 agent 设计时必须显式考虑的成本断档。

GitHub Copilot 的 multiplier 不跟 sticker
绑定。Copilot 把 GPT-5.5 和 Opus 4.7 都从 1.0 倍（GPT-5.4
的水平）调到 7.5 倍，Opus 4.6 时期是 3.0 倍。也就是说 Copilot 在它的
quota 模型里认为这批新 frontier 消耗成本跳了 7.5 倍，不是 sticker 上的 2
倍。r/GithubCopilot 的典型反应是”是时候迁到 Anthropic 直 sub
了”。中间代理平台的定价经常比 sticker 更能反映真实账单。

DeepSeek V4 三种接入方式的风险不同。官方
API（api.deepseek.com）最便宜但数据驻留中国，合规敏感场景过不去。第三方推理（OpenRouter、DeepInfra、Fireworks、Together）定价照搬官方，能绕开中国数据驻留，但要核实第三方路由本身是否会跨多个
provider。自托管（MIT license）是合规最干净的路径，V4-Flash 单 H200
能跑（FP4+FP8 ~158GB），V4-Pro 要 8x H100 80GB（~862GB）。WaveSpeed
实测：日吞吐 50M tokens 以下走官方 API 划算，300M+ 自托管回本。

Opus 4.7 的 extended thinking 被全删。原来的
thinking={"type": "enabled", "budget_tokens": ...}
现在直接返回 400 错误。要迁到 thinking={"type": "adaptive"}
+ output_config={"effort": ...}。你的代码如果有硬编码的
thinking budget，切 Opus 4.7 前要先重写。这是 Caylent 专门标出的
breaking change。

## 按任务派发的决策矩阵

场景

例子

推荐模型

依据

Agentic coding loop

30+ 步 shell / build / test / fix

主选 GPT-5.5，备选 Opus 4.7

Terminal-Bench 2.0 上 GPT-5.5 82.7% 领先 Opus 4.7 的 69.4% 共 13
个百分点，是 GPT-5.5 所有 benchmark 里最大单项优势。DeepSeek V4
不派（67.9%，差 15 个百分点）

真实 GitHub issue 修复 / 跨文件 refactor / 生产级 PR resolution

线上 bug 回归、依赖升级、跨模块重写

主选 Opus 4.7，备选 GPT-5.5

SWE-Bench Pro 64.3% 是 GA 模型市场第一，比 GPT-5.5 的 58.6% 高 5.7
个百分点。

Cursor 内部
CursorBench 58% → 70%、Rakuten 自报生产任务解决量 3×

是生产级行为证据。DeepSeek V4-Pro 备选（SWE-Pro 55.4% 差 9
个百分点，但便宜 9 倍）

事实敏感报告

法规分析、财务摘要、医疗文本整理

主选 Opus 4.7

AA-Omniscience hallucination rate 36%，是市场唯一低于 50%
的。GPT-5.5 是 86%、Gemini 3.1 Pro 是 88%，差距大到不能混用

纯推理 / 数学

FrontierMath、AIME、数学证明

主选 GPT-5.5，备选 Gemini 3.1 Pro

FrontierMath Tier 4 GPT-5.5 35.4% 对 Opus 4.7 的
23%，差距稳定。Gemini 3.1 Pro AIME 95% 同档可替代

长文档 retrieval / RAG

合同分析、长会议转录查找、long codebase 精准定位

主选 GPT-5.5 或 Opus 4.6

Graphwalks BFS 1M GPT-5.4 9.4% → GPT-5.5 45.4%。Opus 4.7 不派：1M
needle-in-haystack 59.2%，比 4.6 的 91.9% 退步 32 个百分点

长文档推理

跨 500K+ 上下文做多跳推理、长 codebase 架构分析

主选 Opus 4.7

长 context 上的推理质量（不是 retrieval）Opus 4.7 仍是第一梯队，跟
GDPval-AA 1753 Elo 的 agentic 能力一脉相承

多模态

视频理解、UI 截图操作、PDF 文档抽取

主选 Gemini 3.1 Pro

Video-MMMU 87.6%、ScreenSpot-Pro 72.7%、OmniDocBench 0.115
三条全面领先。GPT-5.5 本次发布对多模态基本没动，DeepSeek V4 preview 是
text-only

搜索密集 agentic deep research

多轮检索 + 综合写报告

主选 Gemini 3.1 Pro，备选 GPT-5.5

BrowseComp 85.9% 第一，Search Grounding 每月 5000
次免费额度是额外优势。Opus 4.7 不派（BrowseComp
79.3%，本次唯一回归项）

Computer use / RPA / 屏幕自动化

让 agent 操作用户的浏览器、桌面应用

主选 Opus 4.7

OSWorld 78.0% 对 GPT-5.5 78.7% 几乎持平，但 Anthropic 的 computer
use 是标准 Messages API 的 tool，集成成本低。GPT-5.5 目前只有 macOS
Codex 桌面应用路径，不通用

高吞吐、低复杂度 API 调用

分类、摘要、抽取、form filling

主选 DeepSeek V4-Flash 或 Sonnet 4.6

V4-Flash $0.14/$0.28 + 90% cache hit 折扣能把 effective input 压到
$0.028/M。GPT-5.5 不派：大吞吐场景下能力溢出、翻倍单价会直接吃掉
margin

中文任务

中文客服、中文内容生产、中文 QA

主选 DeepSeek V4-Pro 或 Gemini 3.1 Pro

Chinese-SimpleQA DeepSeek 84.4、Gemini 3.1 Pro 85.9，美国 frontier
都在 76 档，差 8 个百分点是长期差距

成本敏感 side project / 学术研究

个人项目、hackathon、无商业 margin 限制的实验

主选 DeepSeek V4

开源权重、1M context、$0.14/M input，成本结构允许高吞吐实验。

Cline
CEO 的 anchor：Uber 用 DeepSeek 代替 Claude，2026 年的 AI 预算够撑 7
年而不是 4 个月

金融 / 医疗 / 法律 / 政府合规场景

需要过 audit、GDPR、HIPAA、SOC 2 的生产流水线

主选 Opus 4.7 走 Bedrock、GPT-5.5 走 Azure、Gemini 走 Vertex

DeepSeek V4 官方 API 不派：多国政府已禁用、GDPR / CCPA
跨境传输风险、audit 过不去。必须用 DeepSeek
的话，唯一方案是自托管在自己的 VPC 里

创意写作 / 对话 / brainstorm

小说、角色扮演、头脑风暴

主选 Gemini 3 Pro 或继续用 Opus 4.6

Opus 4.7 不派：Zvi Mowshowitz 的 literal instruction following
观察、Reddit dogshit 帖子、boringbot PM 盲测都指向同一结论，4.7
结构化输出强、自然对话温度劣化

## 为什么你需要的是一个团队，不是一个模型

上面这张表最有信息量的地方不在任何一条具体派发建议，在整体看过去的那个
pattern：2026
年春，没有任何一个模型能在所有场景里做到最优。GPT-5.5 在
agentic coding 和 reasoning 上第一，hallucination 市场倒数；Opus 4.7
在长 horizon coding 和事实可信度上第一，但 1M retrieval
退步、创意写作退化；Gemini 3.1 Pro 在多模态和 browsing
上第一、性价比最好，但 hallucination 同病；DeepSeek V4 在价格和短任务
reasoning 上第一，但长 agentic 差 15 个百分点，合规是硬 blocker。

这种分布更像是模型能力到一定水平之后的必然结果，而不是市场暂时的噪音。每家的训练预算、数据、产品定位、合规边界都在把各自推向不同的取舍点。OpenAI
把 Codex 做成 superapp，把 computer use 锁在桌面应用里；Anthropic 把 1M
retrieval 容量换成 agentic 推理能力；Google
把价格打到对手三分之一但牺牲事实可信度；DeepSeek 用便宜 9 到 30 倍加 MIT
license
做差异化。每一条都是主动设计过的定位：每家都在定义自己最赚钱的那部分任务类型，然后围绕它做产品、定价、合规的组合。

把你的 AI
需求绑在任何一家身上，等于在你没选中的那些维度上持续承担风险。如果你的流水线上
80% 是长 horizon coding 加真实 issue 修复，Opus 4.7 是明显主力；但剩下
20% 的多模态、搜索、高吞吐批处理，强行用 Opus 4.7
就是在烧钱。反过来全部任务挂在 GPT-5.5 上，事实敏感的场景要接受 86% 的
hallucination rate，高吞吐任务要付翻倍 sticker，多模态基本没戏。

合理做法是把这件事当成组一个团队来做。不同任务派给不同的模型，每个模型去做它最擅长的那部分：长
horizon coding 给 Opus 4.7、agentic shell 给 GPT-5.5、多模态和 browsing
给 Gemini、高吞吐批处理给 DeepSeek V4-Flash、中文或自托管敏感数据给
DeepSeek
V4-Pro。这种组合不是过度工程，是跟每个模型的强项和短板配套的自然选择。代价是要维护多
provider
接入的复杂度，换来的是每个任务类型都用到市场最优，不用在某一家的劣势区段持续多付钱或者在质量上持续吃亏。

这套思路落下去会改变两件事。一是 cost 模型要按任务类型分层算，不是按
token 单价算总账：高频低复杂度任务每次调用一分钱和长 horizon agent
每次调用五美元完全是两件事，不能共用一个预算。二是 evaluation
要内置，每个任务类型定义 5 到 10 个代表性
case，每次考虑切模型时跑一遍对比。这比看 AA Intelligence Index 或
SWE-Bench Pro 数字有用，那些 benchmark
给的是一般情况的平均值，你的生产流量分布可能跟任何一个 benchmark
都对不上。

## 总结

第一，这个参差不齐的能力边界（Ethan Mollick 所说的 jagged
frontier）短期不会收敛。四家的取舍点指向不同方向，每家都在主动强化自己的差异化：OpenAI
走 superapp 路线、Anthropic 走 agentic 工人路线、Google
走性价比加多模态路线、DeepSeek 走 open weight 加成本路线。2027
年这个分布会更清晰，但不会回到一个模型打天下的状态。

第二，因此你的系统架构需要一个抽象层。不要把业务代码直接绑死在某一家的
SDK
上，也不要在产品里硬编码某个固定模型。这里说的抽象层是一种架构原则，不是某个具体工具：你的系统要在模型选择这个维度上留出切换空间，任务类型和模型之间要有一条显式的
routing
逻辑，每个任务类型可以独立评估、独立切换。这种原则层面的决定比选哪家今天最强重要得多。今天谁最强这件事每三到六个月就要重新评估一次；能按任务切换这件事只要做一次架构设计，就够用未来几年。

把这件事做好的团队，都是每次新发布出来就先在自己的任务矩阵上跑一遍、然后决定在哪些任务上切、哪些不切的团队。这是
2026 年做 AI 选型的基本功。

## 来源索引

官方一手： - OpenAI: Introducing
GPT-5.5 - GPT-5.5
System Card（PDF） - Anthropic: Claude
Opus 4.7 发布 - Anthropic
Opus 4.7 System Card（PDF） - Google
DeepMind: Gemini 3.1 Pro 模型卡 - DeepSeek
V4 技术报告（PDF） - DeepSeek V4 API
定价

独立 benchmark 与分析： - Artificial
Analysis: GPT-5.5 是新 leading AI model - Artificial
Analysis: Opus 4.7 deep dive - Artificial
Analysis: Gemini 3.1 Pro Preview - Artificial
Analysis: DeepSeek V4-Pro - LLM-Stats:
GPT-5.5 vs Opus 4.7 - Vellum:
Opus 4.7 benchmarks explained - Epoch
AI: Opus 4.7 ECI score

独立技术评论： - Simon Willison:
GPT-5.5 - Simon
Willison: DeepSeek V4—almost on the frontier - Ethan
Mollick: Sign of the future - Zvi
Mowshowitz: Opus 4.7 Part 1 - Zvi
Mowshowitz: Opus 4.7 Part 2 - Jake Handy:
DeepSeek V4

生态与合规： - CSIS:
Delving into Dangers of DeepSeek - WIRED:
DeepSeek 数据流向中国 - GitHub
Copilot premium request 计费表 - Lovable
生产数据 - Decrypt:
DeepSeek V4 + Cline CEO Uber anchor - Verdent AI:
Gemini 3.1 Pro 工程报告