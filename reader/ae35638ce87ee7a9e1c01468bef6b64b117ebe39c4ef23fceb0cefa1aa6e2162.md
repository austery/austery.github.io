---
layout: post.njk
source: https://yage.ai/share/ai-coding-self-model-survey-20260419.html
speaker: yage.ai
title: |-
  AI 编程工具的自研模型之争：盈利是否必须拥有自己的
  LLM？
date: '2026-04-19'
summary: 文章探讨了AI编程工具的盈利模式与自研LLM的必要性。分析指出，尽管API成本快速下降，但AI编程工具因用量激增、用户对最新模型的需求以及模型厂商的补贴，独立工具公司若要实现盈利并建立竞争优势，通常需要自研或深度定制模型，以降低边际成本、积累数据飞轮并规避供应商风险。纯API消费的独立工具公司难以实现规模化盈利，而自研模型成为了Cursor等公司在推理成本趋零前建立护城河的关键赌注。
area: tech-engineering
category: ai-application
tags:
  - ai-programming-tools
  - llm-strategy
  - inference-cost-reduction
  - business-models
  - vendor-risk
people: []
companies_orgs:
  - Cursor
  - GitHub
  - Microsoft
  - Cognition
  - Amazon
  - Anthropic
  - OpenAI
  - Moonshot AI
  - Fireworks AI
  - Augment Code
products_models:
  - Composer
  - Composer 2
  - Kimi K2.5
  - Claude Code
  - Codex
  - Devin
  - Amazon Q Developer
  - SWE-1
  - SWE-bench Verified
media_books: []
draft: true
status: evergreen
---

Cursor 以 $50B 估值融资 $2B+ 的消息在 4 月 17
日传出后，最受关注的细节是企业客户已实现正毛利，主要依赖自研的 Composer
模型降低第三方 API 成本。

与此同时，LLM 推理成本正在以每年约 10 倍的速度下降。Stanford HAI 2025
报告的数据显示，达到 GPT-3.5 等效性能的推理成本在 18 个月内下降了
280 倍。按这个速度，两三年后 API
调用的成本可能比今天自研模型还低。既然如此，为什么 Cursor
还要花大力气自研模型？

把整个赛道的主要玩家摆到一张表上，一个 pattern 就浮现了：

公司

模型策略

ARR

背景

Cursor

底座 + 垂直定制

$2B

独立工具公司

GitHub Copilot

底座 + 垂直定制

$450-850M

平台公司（Microsoft）

Cognition (Devin+Windsurf)

全栈自研

$150M

独立工具公司

Claude Code

纯 API（自家模型）

$1B+

模型厂商（Anthropic）

Codex

纯 API（自家模型）

未单独披露

模型厂商（OpenAI）

Augment Code

纯 API（放弃自研）

$20M

独立工具公司

独立工具公司中，做到大规模的全部在自研或深度定制模型。纯 API
消费的独立工具公司里，最大的 Augment 只有 $20M
ARR，而且它试过自研后才放弃。Claude Code 和 Codex
做到了大规模，但它们背靠模型厂商，模型本身就是自己的。没有一家纯调第三方
API 的独立工具公司做到过 $100M 以上的 ARR。

这里有一个反直觉的地方：API
价格降得这么快，为什么整个赛道还是没人赚钱？三个机制同时在起作用。

第一，推理变便宜了，用量就暴增。Cursor 的 agent
使用量在过去一年增长了 15
倍，而 agent 模式每个任务消耗的 tokens 是普通代码补全的 5-30 倍。单价降了 10 倍，用量涨了 15
倍，总成本反而更高。

第二，用户要的不是去年的便宜模型，是今年最强的模型。推理成本下降 280
倍是指达到 GPT-3.5 等效性能的成本，但产品竞争要求用最新的 Claude Opus 或
GPT-5，这些前沿模型的价格并没有跟着同步降。Newcomer.co
的报道显示，Cursor 亏损最严重的就是那些大量消耗 Anthropic
最贵模型的重度用户。

第三，模型厂商在用自己的利润补贴编程工具。Claude Code 的 $200/月 Pro
计划据估算实际消耗约 $5,000
的计算资源，Anthropic 用 $30B
年化收入的整体毛利承担这个差额。独立工具公司要在用户体验上跟这个价格竞争，要么自己也亏钱，要么自研模型把成本降下来。

这三层叠加的结果是：推理的单位成本在降，但产品要求的推理量和质量都在涨，竞争环境又要求把省下的成本让利给用户。利润没有留在工具公司手里。自研模型在这个局面下的价值就不只是省
API 费，而是把边际成本从线性（API 按量计费）变成次线性（自有 GPU
的边际成本趋近于零）。量越大，自研的优势越明显。这就解释了为什么做到大规模的独立公司都选了自研。

这个 pattern
引出一个分析框架：自研模型是否必要，取决于公司在价值链的位置。模型厂商做编程工具，模型是自家的，不存在
API
成本问题。平台公司有生态壁垒，模型定制是降本手段之一。独立工具公司两者都没有，自研模型几乎是活到大规模的前提条件。

下面按这个框架展开，先看 Cursor 作为独立工具公司面对的具体困境。

## Cursor 的成本困境和解法

先看数据。Cursor 在 2026 年 2 月达到 $2B
ARR，大约 300 名员工，零营销预算。从零到 $2B 用了不到三年，这是 B2B
SaaS 历史上最快的增长曲线之一。

但增长的背面是亏损。Newcomer.co
的报道 揭示了成本全貌：Cursor
整体处于负毛利状态，最大的亏损来源是一部分个人开发者，他们的 Anthropic
API 账单远超 $20/月的订阅费。独立分析机构 Foundamental 估算 Cursor
每年向 Anthropic 支付约 $6.5 亿，而当时年化收入约 $5 亿，对应约 -30%
的毛利率。

这个困境的根源在于，当一个 AI 编程工具把最核心的能力外包给第三方 API
时，每多一个深度用户就多一份亏损。个人开发者的 $20
月费覆盖不了一个重度用户一天的 Claude API 消耗。

Cursor 的解法分两步。

第一步是调定价。2025 年 6 月从”500 requests/月”切换为按 token 消耗的
credit
制。这引发了严重的用户反弹。开发者论坛上的投诉集中在不可预测性：有人一个半小时用掉了
30% 的月度额度，有团队一天耗尽
$7,000 的年度订阅，有用户报告$119
的意外扣款。Cursor 最终承认沟通失误并退款，但信任损伤已经造成。

第二步是建自己的推理引擎。2025 年 10 月 Cursor 推出了第一个自研模型
Composer，2026 年 3 月发布 Composer 2。经济动机是消除 API
中间商加价，用专用模型替代通用前沿模型来降低单次推理成本。

## Composer
的技术路线：在已有底座上做垂直定制

Composer 的技术路线在之前的分析中已经详细展开过。简要回顾：Composer
2 以 Moonshot AI 的 Kimi K2.5 为底座，经过 continued
pretraining（调整任务分布和能力重心）和大规模 RL 后训练（在 Cursor
自己的编辑器环境中训练工具调用行为）。Moonshot
官方确认了这一合作关系，Fireworks AI 提供托管平台。

Cursor 没有从头训练一个基础模型（那需要数亿美元和上千张
GPU），而是在一个已有的开源级别底座上做垂直定制。这条路线的成本比完整预训练低一到两个数量级，但产出的模型在编程这个垂直场景里可以做到速度更快（官方称
4x faster）、token 消耗更低。

从 Composer 2
的技术报告来看，这个策略的回报体现在 benchmark 上：CursorBench 从 1
到 1.5 提升了 6.2 分（20x RL 算力），从 1.5 到 2 提升了 17.1 分（引入
continued pretraining），后者接近前者的三倍。这暗示 RL-only 路线在 1.5
阶段已经接近收益递减，而底座质量对后训练效果有乘数效应。

## 各路线的具体做法

开头的表格已经呈现了模型策略的分化。这一节补充每条路线具体做了什么，以及那些表格里看不到的细节。

### 底座 + 垂直定制：GitHub
Copilot

Cursor 的做法前面已经讲过。GitHub
Copilot 走的是同一条路：拿 OpenAI 的模型做底座，在上面做 continued
pretraining、SFT 和 RL。Copilot
目前的定制模型主要覆盖代码补全（接受率提升 20%、3 倍吞吐量、延迟降
35%），但补全是高频低成本操作，真正吃 token 的 agent 场景（Copilot
Workspace、跨文件编辑）仍然依赖 GPT-4o 和 Claude 等前沿模型。这也是
Copilot 虽有定制模型，$10/月个人版仍在亏损的原因之一。

垂直定制路线的经济逻辑是把成本结构从按量计费的变动成本转成自有 GPU
集群的固定成本，但前提是 agent 场景也能用上定制模型。独立分析显示，自有 H100 集群相比纯
API 方案可节省约 76%，月消耗量要足够大（对标 GPT-5 API 价格，约 2.56 亿
tokens/月才开始省钱）。Cursor 日处理近 10 亿行代码，在这个区间里，而且
Composer 直接服务于 agent 场景，成本节省落在了最贵的地方。

速度优势同样重要。Composer 的推理速度约 200 tokens/秒，是 Claude
API（约 70 tokens/秒）的近 3 倍。更快的响应让开发者留在 flow state
中，使用量反而增加。自有推理栈还允许更激进的 KV cache
和投机解码优化，调用第三方 API 时无法做到。

### 全栈自研：Cognition 和 Amazon

Cognition（Devin +
Windsurf 的母公司）走得更远：SWE-1
系列从头预训练，参数规模达数百亿级，只用宽松许可的代码数据。Devin
内部运行多模型协同架构，Planner、Coder、Critic、Browser 各自独立训练。Amazon Q Developer
也属于这一类，用内部数十亿行代码训练，深度优化 AWS 基础设施场景。

全栈自研的投入最大，但掌控力也最强，不存在被上游供应商同时做竞品的风险。

### 纯 API 消费：Claude Code 和
Augment

Claude
Code 直接使用 Anthropic 的通用 Claude 模型（Opus 做规划，Sonnet
做执行），没有为编程单独训练模型。Anthropic
的判断是通用推理能力足够覆盖编程场景，Opus 4.6 在 SWE-bench Verified
上达到 80.8%。

Claude Code 能做到大规模，靠的是模型公司的整体经济结构：年化收入
$500M，背后是整体 $30B 年化收入在支撑推理基础设施。$200/月 Pro
计划据估算实际消耗约 $5,000
的计算资源，这个补贴率只有模型公司能承受。

Augment
Code 提供了一个反面案例。这家拿了 $252M
融资的公司在尝试自研后明确放弃，CEO 的理由是模型每几个月换代，自研的
fine-tuned 模型很快被下一代通用模型超过。Augment 把差异化押在 Context
Engine（企业代码库的 RAG 检索）和智能模型路由上，目前 ARR 只有
$20M。

## 自研模型的隐性代价：用户感知到了什么

三条路线的经济逻辑各自成立，但自研路线有一个在融资叙事中很少出现的风险：为了降本，工具公司有动力把更多请求路由到自研的更便宜模型上，用户可能感知到质量下降。

Cursor 论坛上多人报告了质量退化。一个三人团队的描述是：“过去两个月，Cursor
变得极度愚蠢，犯太多错误和不必要的假设。”另一位用户的观察更具体：“质量可能差不多，但
token 消耗疯了。输出很臃肿，成本快速累积。”

与此形成对比的是 Claude Code 的用户反馈。有开发者从
Cursor 迁移到 Claude Code 后评价：“Claude Code
非常简洁、高效，准确完成任务。”Pragmatic Engineer 对 906
名开发者的调查显示，Claude Code 以 46%
的”最受喜爱”评分排名第一。

Hacker News 上有人指出了这个张力的机制：“如果
Cursor 的成本优化导致它比模型提供商的 coding agent 少保留 20% 的 context
tokens，在其他条件相同的情况下，它的表现必然更差。”省下的推理成本如果以用户流失的形式花出去，自研模型的经济优势就会打折。

## 自研模型的窗口期有多长

开头提到，自研模型的价值在于把边际成本从线性变成次线性。但推理成本每年降
10 倍，这个优势的窗口期在收窄。两三年后 API 调用成本可能比今天自有 GPU
还低。

窗口收窄的同时，自研积累的东西不会随 API 降价消失。Cursor 日处理近 10
亿行代码产生的编辑行为数据，是模型改进的持续燃料。这个飞轮一旦转起来，后来者即使拿到同样便宜的
API，也缺少同等规模的训练信号。推理栈的掌控也是如此：KV cache
策略、投机解码、context 管理这些优化需要从推理层到产品层的端到端调试，纯
API 消费者做不到。

还有一层供应商风险。Cursor 最大的 API 供应商 Anthropic 同时在做
Claude Code，OpenAI 曾试图以 $3B 收购
Windsurf，交易虽未完成但信号已经够清楚。最大的供应商随时可能变成最大的竞争对手。自研模型在这个意义上是生存保障，和成本优化同等重要。

$50B 估值背后的核心赌注：Cursor
能否在推理成本趋零之前，用自研模型争取到的毛利窗口建立起足够深的数据壁垒和产品护城河。Cursor
的模型在很多场景下并不比 Claude
更聪明，但如果成本优势换来的时间足以建起飞轮，模型本身的绝对能力差距就变成次要问题。

## 附录：主要来源

TechCrunch: Cursor in talks to raise $2B+ at $50B valuation

Newcomer: Cursor’s Popularity Has Come at a Cost

TNW: Cursor is raising $2B at $50B valuation

Cursor Blog: Composer 2 Technical Report

Moonshot/Kimi 官方确认 Composer 2 底座

GitHub Blog: Building a faster, smarter Copilot with a new custom model

Cognition Blog: SWE-1.5

Augment Code: The Era of Single-Model Engineering is Over

WorkOS: Augment Code CEO interview at HumanX 2026

Stanford HAI 2025 AI Index Report

a16z: LLMflation — LLM inference costs are declining 10x per year

Cursor Forum: Model output quality dropping

DEV.to: Why we’re moving from Cursor to Claude Code

Pragmatic Engineer survey: Claude Code #1 most loved

Hacker News: Cursor pricing discussion

ainews: Cursor faces backlash over pricing changes