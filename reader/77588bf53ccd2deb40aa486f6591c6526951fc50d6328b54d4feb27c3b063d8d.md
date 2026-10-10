---
layout: post.njk
source: https://yage.ai/share/ollama-cloud-vs-api-vs-subscriptions-20260428.html
speaker: yage.ai
title: |-
  开源模型推理采购指南：GLM-5.1、DeepSeek V4 Pro、Kimi
  K2.6 的 API、订阅和 Ollama Cloud 对比
date: '2026-04-28'
summary: 本文对比了 GLM-5.1、DeepSeek V4 Pro 和 Kimi K2.6 这三款开源模型的推理服务。从价格、隐私和速度三个维度，分析了 DeepSeek、z.ai、Kimi 和 Ollama Cloud 等厂商的 API 按量计费与订阅方案，详细对比了不同用量和数据敏感度下的成本与政策。文章还讨论了速度和限流情况，并为不同场景下的模型选型提供了具体建议。
area: tech-engineering
category: ai-application
tags:
  - ai-inference
  - model-pricing
  - data-privacy
  - cloud-services
  - open-source-ai
people: []
companies_orgs:
  - DeepSeek
  - z.ai
  - Moonshot
  - Ollama
products_models:
  - GLM-5.1
  - DeepSeek V4 Pro
  - Kimi K2.6
  - z.ai Coding Plan
  - Kimi Code
  - Ollama Cloud
media_books: []
draft: true
status: evergreen
---

如果你已经确定开源模型能满足你的需求，接下来的问题就变成了一个采购决策：推理去哪买？同一个模型，你可以走官方
API 按量付钱，也可以买厂商自己的订阅（z.ai Coding Plan、Kimi Chat
Pro），还可以走 Ollama Cloud
的包月。不同渠道的计费逻辑差异大到能改变你的工作流设计。价格只是第一层。当你的
prompt
里包含客户数据或内部代码时，计费方式的差异远不如数据去向的差异重要。

这篇文章聚焦三个当前最受关注的开源模型：GLM-5.1、DeepSeek V4 Pro 和
Kimi
K2.6。我们从三个维度做对比——价格、隐私、速度——最后给出不同使用场景下的选型建议。

## 三种买法，三种计费逻辑

先搞清楚各自在卖什么。

官方 API 是模型厂商自己运营的按量计费服务。DeepSeek
在 platform.deepseek.com，GLM-5.1 在 z.ai，Kimi 在
platform.kimi.ai。input 和 output
分开计价，用多少付多少。三家都以美元结算。

厂商订阅 是模型厂商自己的包月方案。z.ai 有 Coding
Plan（Lite ~$10/月、Pro ~$30/月、Max ~$80/月），包含 GLM-5.1
在内的全线模型，按请求次数计费，可以接入 agent 编程工具。Kimi
也有面向开发者的 Kimi Code
订阅，用音乐术语命名档位：Moderato（$19/月）、Allegretto（$49/月）、Vivace（更高，价格未公开），包含
CLI 接入和优先计算资源。DeepSeek 目前只有面向消费者的 Chat 订阅（Growth
$35/月），不暴露 API，不能用于 agent 编程工作流，不纳入本文对比。

Ollama Cloud 是 Ollama
公司的云端推理服务，订阅制：Free $0、Pro $20/月、Max $100/月。按 GPU
时间消耗计算用量，不按
token。三个模型在上面都有（glm-5.1:cloud、deepseek-v4-pro:cloud、kimi-k2.6:cloud）。同样不公布具体
token 限额，只说 Pro 是 Free 的 50 倍、Max 是 Pro 的 5 倍。

## 价格：API 按量计费

先看官方 API 的单价。所有价格以每百万 token 为单位。

模型

Input（

/

M

t

o

k

e

n

s

）|

O

u

t

p

u

t

（

/M
tokens）

备注

DeepSeek V4 Pro（折扣价）

$0.435

$0.87

75% 折扣，截至 2026/05/31

DeepSeek V4 Pro（原价）

$1.74

$3.48

6 月 1 日起恢复

GLM-5.1（z.ai）

$1.40

$4.40

上下文 202K，缓存 input $0.26

Kimi K2.6

$0.95

$4.00

上下文 256K，最低 $1 起充

来源：DeepSeek
定价、z.ai
定价、Kimi
定价

折扣期的 DeepSeek V4 Pro
是三者中最便宜的。折扣结束后，局面翻转：GLM-5.1 的 input（$1.40）比
DeepSeek 原价（$1.74）低，但 output（$4.40）反而比 DeepSeek（$3.48）和
Kimi（$4.00）都贵。如果你的工作负载 output
重（代码生成、长文写作），GLM-5.1 的 API
单价反而是三者中成本最高的。

z.ai 的 API 还有一个容易忽略的特点：缓存 input 只需 $0.26/M
tokens，是全价 input 的不到五分之一。如果你的 prompt
有大量重复前缀（比如系统 prompt + 上下文不变），实际 input
成本会比标价低得多。

### 两个场景的 API 成本

场景 A：轻量 agent 编程。每次 10K input / 2K
output，每天 100 次，一个月 3000 次。总计 30M input + 6M
output。这是一个每天开着 agent
做编码辅助、每天几十到上百次调用的典型用量。

模型

月成本

DeepSeek V4 Pro（折扣价）

$18.27

Kimi K2.6

$52.50

GLM-5.1

$68.40

DeepSeek V4 Pro（原价）

$73.02

这个用量下 DeepSeek 折扣价仍然很能打，$18
就够了。折扣过期后三个模型都在 $50-73 之间，而 z.ai Coding Plan Lite
只要 $10、Ollama Cloud Pro 只要
$20，订阅在这个用量下已经开始有明显的价格优势。

场景 B：重度 agent 编程。每月约 7.5 亿 input + 8500
万 output（总计约 8.35 亿 token），input 与 output 比例约
9:1。这个量级的推算依据是：用 ccusage 工具追踪的 Claude Code $200 Max
计划用户报告月消耗在 $2,000-3,000 之间（按 Sonnet 4.6 API
价格等价折算，假设 75% 的 input 命中缓存），反推得出约 8-13 亿
token/月。这里取其中位数。

模型

月成本

DeepSeek V4 Pro（折扣价）

$400

Kimi K2.6

$1,053

GLM-5.1

$1,424

DeepSeek V4 Pro（原价）

$1,601

到这个量级，纯 API 的月成本从 $400 到 $1,601
不等，取决于模型和折扣。相比之下，z.ai Coding Plan Max 只要
$80/月、Ollama Cloud Max $100/月——如果订阅能撑住这个用量（z.ai Max
根据实测可以），成本差距是 5-20 倍。

## 包月订阅：谁在什么用量下划算

现在把订阅方案拉进来比较。困难在于，各家的订阅不按 token
计费，限额口径不统一，很难直接换算。下表列出已知信息，再尝试估算。

订阅方案

月费

包含模型

限额描述

z.ai Coding Plan Lite

~$10

GLM-5.1, 5-Turbo, 4.7, 4.6, 4.5-Air

“3× Claude Pro 用量”

z.ai Coding Plan Pro

~$30

同上 + GLM-5

“5× Lite 用量”

z.ai Coding Plan Max

~$80

同上 + GLM-5

“4× Pro 用量”

Kimi Code Moderato

~$19

Kimi K2.6 及全线

CLI 接入，优先计算

Kimi Code Allegretto

~$49

同上

更高限额

Kimi Code Vivace

未公开

同上

最高限额

Ollama Cloud Pro

$20

全部 cloud 模型

“Day-to-day work”，Free 的 50x

Ollama Cloud Max

$100

全部 cloud 模型

Pro 的 5x

来源：z.ai
Coding Plan、Kimi
Code 指南、Ollama 定价

这里有一个关键的数据点。z.ai Coding Plan 的限额描述用了”Claude Pro
用量的 N 倍”这种参照物，而不是具体的请求或 token 数。有用户报告在 Max
档（~$80/月）下每月用掉数百万甚至上千万 token
都没有触及上限。根据实际重度使用测试（每月 8 亿 token 的消耗量），z.ai
Coding Plan Max（$80/月）能够撑住。纯 API 在同等用量下要
$400-$1,601，z.ai Max 相比之下能省下 5-20 倍。

Ollama Cloud 的限额同样不透明。社区逆向估算 Free 档约 28
GPU-hours/月，Pro 档约为 Free 的 50 倍。但 GPU 时间和 token
的换算取决于模型大小和请求复杂度，无法精确折算。在每月 8 亿 token
的重度用量下，Ollama Cloud
Max（$100/月）可能刚好能撑住，也可能不够——取决于你主要用哪个模型（大模型消耗
GPU 时间更快）。Pro 档（$20）在这个量级下几乎可以确定不够。

Kimi Code 的 Allegretto（~$49/月）或 Vivace 在重度 agent
场景下可能够用，但 Vivace 的价格未公开，限额也不透明，需要实测。DeepSeek
V4 Pro 在重度 agent 场景下没有可用的订阅选项——它的 Chat 产品不暴露
API。重度 DeepSeek 用户只能走 Ollama Cloud
的订阅，或者接受按量计费的高成本。

回到场景 A（30M+6M token/月）的数据。轻量 agent 在纯 API 下需要
$18-$73。Ollama Cloud Pro 的 $20 和 z.ai Lite 的 $10
都在这个范围内，如果订阅能覆盖（大概率可以），那订阅更划算。

而到了场景 B（7.5 亿+8500 万 token/月），纯 API 的月成本在
$400-$1,601 之间，而 z.ai Max 只要 $80、Ollama Cloud Max
$100，订阅依然有 5-20 倍的价格优势。z.ai Max
是最明确能撑住这个量级的选项。Ollama Cloud Max 有风险但值得试。

不过这个结论有一个前提：你主要用同一个厂商的模型。如果你的工作流跨多个模型（比如
GLM-5.1 做编码、Kimi 做调研、DeepSeek
做推理），那每家买一个订阅就不划算了。这时候 Ollama Cloud
的优势就体现出来——一个订阅包含所有三个模型。反过来说，如果你只用 GLM-5.1
一个模型，z.ai 的 Coding Plan 专注度更高，限额也更宽松。

## 隐私：数据去了哪里

这一节的结论可能会改变前面纯价格维度的判断。

四家服务商——三家中国模型厂商（DeepSeek、月之暗面、智谱）和一家海外服务商（Ollama）——在数据政策上的差异比价格差异更大。以下是逐一核查的结果。

Ollama Cloud
的隐私承诺在四家中最明确。官方隐私政策原文写道：使用云端模型时，prompt
和 response 内容仅在请求处理期间短暂存在（“process this content
transiently”），“不会存储超过完成请求所需的时间”（“not stored beyond the
time required to fulfill the
request”），并实施了技术措施来最小化保留时间。服务条款中单独声明：“我们不使用你的输入或输出来训练
AI 模型。” 与 NVIDIA 云服务商的合作合同中，Ollama
要求对方遵守”无日志、无训练、零数据保留”策略。来源：ollama.com/privacy、ollama.com/terms

DeepSeek 的隐私政策使用”may
collect”（可能收集）的措辞描述对 prompt 和输入内容的处理，没有像 Ollama
那样明确排除存储。政策中提到企业集团内的实体会将数据用于”基础模型训练和优化”，但同时提供了
opt-out（退出训练）的权利。不过，API 场景下如何执行
opt-out（是通过后台设置还是 API 参数），政策中未说明。来源：DeepSeek
隐私政策

Kimi / 月之暗面
在隐私政策中明确将对话内容列为收集的信息种类之一，并说明用途包括”优化模型”。用户服务协议第五条写道：“您授予我们一项免费的使用权，以在法律允许的范围内将您输入输出之内容及反馈用于模型服务优化。”
来源：Moonshot
隐私政策、Moonshot
用户协议

智谱 / z.ai
的用户协议第十条第三款授予了一项范围极广的许可：在法律允许的范围内，用户”免费授予智谱及其关联公司非排他的、无地域限制的、永久的、免费的许可使用（包括存储、使用、复制、修订、编辑、发布、展示、翻译、分发上述信息或制作派生作品）及可再许可第三方使用的权利”。这条授权覆盖了非个人信息的全部内容，且允许再许可给第三方。来源：智谱用户协议

汇总成一张表：

维度

Ollama Cloud

DeepSeek

Kimi / Moonshot

z.ai / 智谱

是否存储 prompt/response

不存储

可能收集

明确收集

明确收集

是否用于训练

不用于

默认可能，可 opt-out

明确用于优化

授权范围极广，未排除训练

第三方审计

无

无

无

无

数据存储地

美国

中国（推断）

中国

中国

这里不做价值判断。不同使用场景对隐私的要求不同，读者需要根据自己
prompt
中是否包含客户数据、商业敏感信息或个人数据，来判断哪家政策适合自己的场景。

## 速度：体感差异有多大

三个模型在各自官方 API 上的输出速度（tokens/second），基于 Artificial Analysis
的独立测试（10K input token 工作负载，P50 中位数）：

模型

官方 API 输出速度

首 token 延迟

Kimi K2.6

~106 t/s

未公布（含 thinking time）

GLM-5.1

~52 t/s

1.43s

DeepSeek V4 Pro

~38 t/s

2.02s

Kimi K2.6 的 106 t/s 大约是 DeepSeek V4 Pro 的 2.8
倍。体感上，生成一段 500 token 的回复，Kimi 大约需要 4.7 秒，DeepSeek V4
Pro 大约需要 13 秒，GLM-5.1 居中约 9.6 秒。

不过 GLM 系列在第三方优化后速度提升空间最大。推理服务提供商 Novita 在
FP8 精度下跑 GLM-5 跑出了 213 t/s，Baseten 用 MTP speculative decoding
达到了 186 t/s。这说明官方 API 的 52 t/s
更多是服务端优化程度的限制，而非模型本身的能力上限。如果你通过第三方提供商（如
Together AI、Fireworks）来调用 GLM-5.1，速度可能会明显好于 z.ai 官方
API。

Ollama Cloud 没有公开这三个模型的吞吐量数据，也没有独立的第三方
benchmark。底层硬件是 NVIDIA Blackwell
系列，理论上应该比消费级本地硬件快不少，但缺少公开数据来做精确比较。

Rate limit 方面，DeepSeek V4 Pro 的 60 RPM
是一个实际瓶颈。如果你的工作负载是高频短请求（比如多个 agent
并发调用），会先撞到 RPM 上限而不是 TPM 上限。Kimi 的 rate limit
随充值金额递增，最低档（$1 充值）只有 3 RPM 和 1 并发，充到 $10 后跳到
200 RPM。z.ai 的 rate limit 没有公开文档，有用户报告 GLM-5 和 5.1
在使用数天后触发限流。

## 选型建议

把使用量和隐私敏感度组合在一起，大致是四个象限：

低用量 + 隐私不敏感（轻量 agent
编程，每天几十到上百次调用）：API 按量计费和低价订阅都可以。折扣期的
DeepSeek V4 Pro 每月 $18，和 Ollama Cloud Pro（$20）打平。z.ai Coding
Plan
Lite（$10/月）如果限额够用，是性价比最高的选项。这一档有多个合理选择，看你对模型的需求。

高用量 + 隐私不敏感（重度 agent 编程，每月数亿到十亿
token）：订阅制几乎是唯一选项。纯 API 在这个量级要 $400-$1,600/月。z.ai
Coding Plan Max（$80/月）是目前最明确能撑住重度用量的订阅。Ollama Cloud
Max（$100/月）也值得尝试，但 GPU
时间计费在大模型上消耗更快，需要实测。如果你跨多个模型工作，Ollama Cloud
的一个订阅覆盖所有模型比买多家订阅划算。

低用量 + 隐私敏感（prompt
包含客户数据或商业信息，轻量 agent）：Ollama Cloud
是目前隐私承诺最明确的选项。它的”不存储、不训练”政策在四家中措辞最强，虽然缺少第三方审计认证。Pro
档（$20）应该足够轻量 agent 使用。

高用量 + 隐私敏感（企业级 agent
工作流，数据敏感）：目前没有完美选项。Ollama Cloud
的隐私承诺最强但无审计认证，且 Max
档在重度用量下能否撑住不确定。中国厂商的数据政策（尤其是智谱的宽泛授权条款和
Kimi
的明确收集声明）需要逐条对照你的合规要求再做决定。如果审计合规是硬性要求，自建基础设施或寻找带
SOC 2 认证的专用推理服务可能是唯一出路。

最后提一个时间维度的注意点。DeepSeek V4 Pro 的 75% 折扣在 2026 年 5
月 31 日到期，之后 API 价格会跳到原来的四倍。在场景 A（轻量
agent）下，折扣到期后 DeepSeek 的月成本从 $18 跳到 $73，和 z.ai Coding
Plan Lite（$10）或 Ollama Cloud Pro（$20）的差距立刻拉开。在场景 B（重度
agent）下，折扣到期后 DeepSeek 的月成本从 $400 跳到
$1,601，订阅制的优势会变得更加明显。