---
layout: post.njk
source: https://yage.ai/share/anthropic-coding-agents-dna-divergence-20260416.html
speaker: yage.ai
title: |-
  从 Claude Code Routines 看 agent coding
  工具的基因分化
date: '2026-04-16'
summary: Anthropic、OpenAI、Cursor 的 Agent Coding 工具分析：产品差异源于营收模式与目标用户。Anthropic 侧重企业 API，OpenAI 服务个人开发者，Cursor 瞄准企业自动化。云端 Agent 异步验证闭环的成熟是技术基础，不同验证条件塑造了产品路径。
area: tech-engineering
category: tech-trends
tags:
  - agent-coding
  - developer-tools
  - business-models
  - enterprise-automation
  - product-strategy
people:
  - Dario
  - Jonas Nelle
  - Michael Truell
companies_orgs:
  - Anthropic
  - OpenAI
  - Cursor
products_models:
  - Claude Code Routines
  - Codex
  - Cursor Automations
media_books: []
draft: true
status: evergreen
---

四月十四日 Anthropic 发了 Claude
Code Routines，云端 agent 任务跑定时、API、GitHub webhook
三种触发。第二天发了 desktop
rebuild，并行 session 管理、drag-and-drop 面板、macOS/Linux 原生
SSH、plugin 兼容 CLI。

从时序上看这次发布来得晚。OpenAI 二月二号就发了 Codex macOS app 和
Automations，Cursor 三月五号发了 Automations。Anthropic 比 Codex
晚十周，比 Cursor 晚五周。社区里很快出现”Anthropic
又在追赶”的读法。但细看三家的产品会发现，这个追赶的说法得成立有一个前提：三家在做同一件事。而事实是，它们只是共享了一个名字。

## 三家在招的是三种不同的人

看清差异最直接的方式是问：如果这三个 agent
是你公司招进来的员工，它们分别对应哪种岗位？

Codex Automations 是一个坐你旁边写 shell
脚本的初级开发者。每天早上给你 git log
简报，每周跑一次 skill 升级，就这些。它跑在你自己的 Mac 上，Codex app
必须开着，项目文件必须在磁盘上（官方文档明写
“The app needs to be running, and the selected project needs to be
available on disk.”），只认 cron，不接 webhook，跟着 ChatGPT
订阅走，不单独计费。它服务的是坐在电脑前的个人开发者，替代的是你自己手写的几行
crontab。

Cursor Automations 是一个企业里的 DevOps。推 main
分支时它做 security review，PagerDuty 报警时它拉 Datadog
日志自动诊断，Linear 开新 issue 它评估 PR 风险，结果写回 Slack 或
Notion。触发源是 Slack、Linear、GitHub、PagerDuty 加自定义 webhook，跑在
Cursor 云 sandbox 里。首个 external showcase 是 Rippling。Cursor 工程
lead Jonas Nelle 对 TechCrunch
说过：“人没有完全退出，只是不再总是发起者，而是在流水线的正确节点被叫进来。”这是
Cursor 对标 GitHub Actions、PagerDuty、Zapier
的位置，服务的是已经有完整自动化链路的企业。

Claude Routines 是一个企业 CI 团队里写 webhook handler
的工程师。每个 routine 是一个独立 API endpoint，有自己的 bearer
token，企业的 CI、Jenkins、内部 orchestrator 可以按标准 HTTP
调用方式触发它。独立配额（5/15/25 每天 + overage）和独立计费，让 agent
任务能按部门归属到成本中心。desktop rebuild 带的 SSH 让 agent
可以在企业内网的开发机上执行，代码不出内网。Routines 服务的是把 agent
写进 IT 架构图、要走采购流程、要签合同的企业。

这三种岗位对应的 agent 做的活不一样。Codex 的 cron 脚本做不了
PagerDuty 自动化，Cursor 的 switchboard 不能替代一个可程序化调用的 API
primitive。三家走的是三条路径，不在一个赛道。

## 这三条路径是营收结构直接推出来的

为什么三家做出这样三种产品？因为每家真正在服务的是自己的主要付费用户。

Anthropic 约 80% 的营收来自企业和 API，消费端 Claude
Pro/Max 占 15-20%。Dario 在 2026 年 2 月 Series G 之后的表述是 “80% of
revenue from business
customers”。它有三十万以上的企业客户，约一千家年付百万美元以上，Claude
Code 年化 25 亿美元，其中过半来自企业订阅（Anthropic 自己在 Series G
公告里的数据）。Claude.ai 消费端付费用户 2026 年 Q1 翻倍，但 Claude Code
六周内也翻倍，结果是消费端占比不升反微降。相比之下 Claude.ai
周活一千九百万对 ChatGPT 九亿，份额 4.5%，十八个月里没明显追赶。把
Routines 做成企业能写进合同的 API
primitive，是服务自己主要客户的自然结果。

OpenAI 70% 的营收来自 ChatGPT 订阅，API 和企业各
15%。九亿周活是它最大的资产，Codex 嵌在 ChatGPT Plus（月费 20 美元）和
Pro（月费 200 美元）订阅里按消息配额给，不单独出 SKU。Codex Automations
要求 Mac app
开着、文件在磁盘上，架构层面锁定了”坐在电脑前的个人开发者”这个用户画像。这是
ChatGPT 2C 基因在开发者产品上的延续。

Cursor 20 亿美元年化营收里约 12 亿来自企业、8 亿来自约 330
万付费个人。企业客户覆盖 Fortune 500
的大约一半（Rippling、Brex、Ramp、Stripe、Discord、Samsara、Airtable、Sierra
AI、NYT 都是公开披露）。Michael Truell 对 The Verge 说过 vibe coding
和业余用户”不是 Cursor 的主要受众”。估值要往 $10B+ 走只能靠企业。所以
Cursor 3（代号 Glass）把 IDE 降级成 fallback surface，Truell
在发布博客里写”我们会继续投资 IDE，直到 codebase 变得
self-driving”，这句话等于明说 IDE 是 transitional。

我在 2025 年 5 月写过 AI
产品的错位，当时看的是这个基因在消费端 app 上的表现：Claude.ai 切走
app 任务就丢、iOS 长输出手机过热、chat history 变
Untitled，那篇的总结是”Claude 是 B2B
公司所以消费端是半成品”。十一个月后再看，这个基因在 B2B
产品线上的展开更清楚：Anthropic 没在修消费端，而是把精力全压在 Claude
Code 上，做成 API 批发之外的第二条 B2B 支柱。

## Routines 是
Anthropic 两个月动作链条的第五步

Routines 不是孤立事件。过去两个月 Anthropic
做过五件事，方向高度一致：

runtime 层降 reasoning effort（二月起，Stella Laurenzo
四月初用六千多个本地 session 反向审计才逼
Anthropic 承认）；订阅 OAuth 收紧禁止第三方（三月二十一号的 legal
compliance 页面，OpenCode 当天被断连）；Defense in Depth（四月一号加
Zig attestation、FFI 反调试、客户端混淆）；Managed
Agents（四月八号，用户交出 agent 定义，Anthropic 托管
credential、memory、events）；Routines + desktop
rebuild（四月十四到十五号）。

这五件事每一件单拎出来可以解释成独立产品动作。放在一起看的意思是：Anthropic
系统性地在把 Claude Code 从一个 terminal CLI
推成一个企业可采购、可审计、可写进 IT 预算表的 agent runtime
平台。runtime 层降级保毛利，OAuth 收紧防止 context 流出产品边界，Defense
in Depth 让 client 作为企业基础设施稳定，Managed Agents 提供托管
agent，Routines 提供可程序化的 agent primitive。每一步都直接对应企业采购
agent 产品时会问的问题：成本可控吗？数据留在产品内吗？client
稳定吗？能托管吗？能集成到我们的 CI 里吗？

我在 runtime
层降级、订阅不是开发者凭证、Defense in
Depth、Managed
Agents 分析 四篇里分别展开过这四步的具体机制。现在把它们加上
Routines 放在一起，能看到一条完整的企业 agent 平台建设节奏。Anthropic 把
Claude.ai 放着几乎没动，资源全投在 Claude
Code。这是基因决定的资源分配。

## 云端 agent 的价值条件

如果三家做的是服务三种不同用户的不同产品，为什么都集中在 2026 年 Q1
发力？底下有一个共同约束在变紧：云端 agent
开始能在生产环境跑通了，但跑通的条件对每种用户不一样。

云端 agent
的实际价值取决于异步验证闭环能不能关闭。企业团队的闭环是
CI/CD：diff 进来、测试跑完、部署到 staging、pager 叫值班，每一步都能被
agent 自动推进，最后人在手机上点确认。Rippling 的 Cursor 早晨 agent 能
work 就是因为 CI 基础设施已经在那。Firdaus Fauzi 在 LinkedIn
上描述”Cursor 云 agent 接进完整 CI/CD 之后就像魔法”是同一个意思。Gergely
Orosz 引过 OpenAI Codex 团队的内部原话：“structure the codebase to make
it inevitable for the model to succeed”，说的正是这个前提。

没有这个闭环的场景，云端 agent 立刻塌掉。Every.to 一个 Claude Code
mobile 实验的报告直接点出”手机上没法 load app 看它 work 不
work，所以没法完成任何事”。OpenAI 社区论坛里关于 Codex cloud 创建 PR
失败的 bug
报告也是同类：链路中断一处，云端的异步优势归零，人必须回电脑前接手。

把这个条件映射回三家的产品选择就合拢了。Cursor 和 Anthropic
的企业客户天然有 CI/CD，所以两家把云端 Automations/Routines
做成企业自动化的 primitive。OpenAI 的 ChatGPT
订阅用户大多是个人开发者，大多没完整 CI/CD，所以 Codex Automations
就设计成 Mac 本地跑、app 必须开着，让用户直接肉眼验证。Anthropic 的 SSH
支持是把这个概念扩展到企业内网：agent
在公司的开发机上跑，验证闭环走企业内部
CI，代码不出去。三家的产品设计都是对自己用户群验证闭环能力的准确响应。

## 结尾

三家在 2026 年 Q1 做的 agent
云端化动作底下是同一个技术拐点：异步验证闭环在越来越多场景里能跑通。但每家怎么做差异大到这三个产品没法互换。这些差异是营收结构决定的路径。Anthropic
约 80% 的 B2B 营收让它把 Claude Code 做成企业级 agent 平台；OpenAI 70%
的 ChatGPT 订阅让它把 Codex 做成个人桌面助手；Cursor 60%
的企业营收拉着它从 IDE 往企业编排 switchboard 爬。

“Claude Code 有没有
Routines”这种问题回答不了更有价值的事。把基因看清楚，比追时序更有用。