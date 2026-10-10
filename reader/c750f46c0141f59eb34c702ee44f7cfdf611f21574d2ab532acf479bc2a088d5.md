---
layout: post.njk
source: https://yage.ai/share/vercel-ai-cloud-platform-survey-20260605.html
speaker: yage.ai
title: Vercel 的 AI Cloud：2026 年产品路线图全景
date: '2026-06-05'
summary: 本文分析了 Vercel 在 2026 年的产品路线图，指出其正从单纯的前端部署平台演变为 agent 开发的统一基础设施。通过整合 AI SDK、AI Gateway、Sandbox 和编排服务，Vercel 降低了开发成本，试图定义 agent 应用的标准技术栈。虽然定价复杂和功能性缺口仍存在，但其整合策略正在让它成为 AI 应用开发的高效起点。
area: tech-engineering
category: ai-application
tags:
  - agent-infrastructure
  - ai-cloud
  - ai-gateway
  - sandbox
  - workflow-orchestration
people:
  - Guillermo Rauch
companies_orgs:
  - Vercel
  - Accel
  - GIC
  - Suno
  - Portkey
  - E2B
  - Temporal
  - LangSmith
products_models:
  - AI SDK
  - AI Gateway
  - Sandbox
  - Workflow
  - Fluid Compute
  - Vercel Agent
  - MCP server
  - Next.js
  - Socket.IO
  - Claude Code
  - Cursor
  - ChatGPT
  - Codex CLI
  - VS Code Copilot
media_books: []
draft: true
status: evergreen
---

大部分人提起 Vercel 想到的是一键部署 Next.js，或者 AI SDK
上那个一行代码切模型的 generateText()。这个印象在 2024
年是对的，放在今天已经漏掉了最关键的东西。

站在 2026 年中回看，Vercel 在过去一年半里做的事不是加了几个 AI
功能，而是围绕”agent 时代的基础设施”重新定义了整个产品线。AI SDK
已经从统一调用接口演进到包含 agent abstraction 的完整框架。AI Gateway
已成为数百模型的生产级路由层，背后承载的真实数据——200K+ 团队、数十万亿
token——揭示了一个多模型 agent 架构正在成为默认选项的市场。Sandbox 从
beta 进入 GA，增加了持久化存储和 Docker 支持，从”跑一段 AI
生成代码的临时环境”变成”agent 的远程工作机”。Workflow 和 Fluid Compute
补齐了长任务编排和 AI-native 计费模型。Vercel Agent 和 MCP server
在把平台本身变成可被 AI 工具操作的对象。

把这些拼在一起，Vercel 想做的事逐渐清晰了：不是做一个能跑 AI
的前端平台，而是像当年 unified frontend cloud 一样，把 agent
开发需要的所有基础设施——模型路由、隔离计算、任务编排、可观测性——统一成一个平台。

## 路线图：从三代抽象理解
Vercel 的逻辑

Vercel 的创始人兼 CEO Guillermo Rauch（也是 Next.js 和 Socket.IO
的创造者）在 2025 年 10 月写过一篇文章叫 The AI
Cloud，里面有一张对比表（原文）：

传统云

AI Cloud

静态 UI / 一次性响应

动态生成 UI / 流式响应

React / Next.js

AI SDK

CloudFront（像素 CDN）

AI Gateway（token CDN）

EC2

Sandbox

Lambda

Fluid

这张表概括了一个工程判断：AI 应用的流量形态、计算模型和安全需求跟传统
Web 有本质差异，需要一套新的基础设施抽象。

理解这套抽象从何而来，回看 Vercel 的三次基础设施升级会清晰很多。

第一代（2015-2020）把 Web
运维的碎片化步骤收进一个平台。CI/CD、CDN、域名管理、serverless
function、预览环境——这些组件被统一到 Next.js 部署按钮后面。用户写 React
组件，Vercel 生成基础设施。官方后来叫它 Framework-defined
Infrastructure，本质上是一个编译器：源代码是框架代码，编译产物是云资源。

第二代（2023-2025）把这个思路复制到了 LLM 调用层。2023 年做 AI
应用，需要分别接入 OpenAI、Anthropic、Google 的 SDK，管理各自的
key、限流、计费。AI SDK 把这些统一到一个 generateText()
调用，底层处理 provider 选择、工具调用、流式输出。到 2025 年 AI SDK 5
发布时，ai 这个 npm 包已经是 AI 类第二大包，仅次于
openai 本身，每周 300 万下载。AI SDK 6 进一步加入了 agent
abstraction——定义一个 agent 一次，在不同界面和工作流中复用（官方博客）。

第三代就是现在。Vercel
把统一化的对象再次升级：不再是”如何调用模型”，而是”agent
应用运行在什么基础设施上”。一个 agent
不光需要模型调用，还需要沙箱执行环境、工作流编排、模型路由和容错、可观测性。这些组件每一层都有独立的竞品：E2B
做沙箱、Portkey 做网关、Temporal 做工作流、LangSmith 做观测。Vercel
的策略是把它们全部变成同一个平台的不同配置项。

## 现在可用的产品栈

Vercel 目前可用的 AI 产品线可以分四层来看。

模型路由层：AI Gateway。 统一 API
接上百个模型，不额外收 token 加价，按上游 list price 透传。Gateway
的真正价值在路由逻辑：fallback、retry、load balancing。Vercel 5 月发布的
production index 报告（原文）披露了几个值得注意的数据：高流量团队在生产中平均使用
35 个以上的 distinct models，agentic 请求已经占了 59% 的 token 流量（6
个月内翻倍），fallback 机制拯救了约 3.5%
的请求。这些数据指向一个正在发生的市场变化：多模型路由已经从”高级选项”变成生产环境的默认设定。Gateway
还支持 team-wide Zero Data Retention、budgets 和 usage
monitoring，面向企业的合规需求。

隔离计算层：Sandbox。 底层是 Firecracker
microVM，运行 Amazon Linux 2023，提供 Node 和 Python runtime。2026
年上半年的两个关键更新：持久化 GA（filesystem 在 stop 时自动
snapshot，下次按名字 resume），以及 Docker in Sandbox（可以安装
Docker、拉镜像、运行 Redis/Postgres 作为测试依赖）。组合效果是 agent
可以拥有自己的工作环境——依赖、缓存、dev
数据库、工具链都留在里面，不再每次从零搭建。Sandbox 按 active CPU
计费，I/O 等待时间不收费（官方文档），这对 agent
这种大量等待模型响应的工作负载比传统按 wall time 计费合理很多。

编排与运行层：Workflow + Fluid Compute。 Fluid
解决了 AI 应用的 idle billing——多个请求共享同一个 function 实例，一个等
I/O 时另一个占 CPU。Workflow 处理长运行任务的暂停、恢复、状态管理。Suno
作为 beta 测试者在 function workload 上节省了约 40% 的费用（Runtime.news
报道）。

平台互联层：Vercel MCP + Agent。 Vercel MCP 是
remote MCP server with OAuth，已支持 Claude Code、Cursor、ChatGPT、Codex
CLI、VS Code Copilot 等 12 个主流 AI 客户端，让 AI 工具能直接管理 Vercel
项目。Vercel Agent（产品页）是一个会自动 review 代码、在
Sandbox 内跑测试、提 PR 的 AI 同事。这层产品的策略方向很清楚——让 Vercel
平台本身成为 agent 可编程操作的对象，而不仅仅是部署的目标。

## 产品策略：整合优于单品

逐项对比的话，Vercel 没有哪一项是绝对最好的。Sandbox
在功能成熟度上不如 E2B（后者有 150ms 冷启动、24 小时 session、BYOC、GPU
支持），但 Vercel 的方案胜在和平台的集成——如果你已经在 Vercel
上，Sandbox 用 OIDC 直接认证，不需要额外配置 credential（Northflank
对比分析）。AI Gateway 在治理深度上不如 Portkey 或
LiteLLM，但对于已经在用 Next.js + AI SDK 的团队，Gateway
是零配置默认接入的。

这个策略的核心是降低每一步的切换成本，而不是追求单点最优。用 Next.js
的团队自然用 Vercel 部署，自然用 AI SDK 调模型，自然走到 AI Gateway
做路由，需要隔离执行时自然选
Sandbox。每一步的切换成本接近于零。但离开的代价在累积——把已经深度集成
Gateway + Sandbox + Workflow + Observability
的应用迁出去，每一步都需要重新对接。AI SDK 是开源的（Apache
2.0），Sandbox 底层是标准
Firecracker，技术上迁移可行，但便利性绑定本身已经构成 moat。

Vercel 2025 年融资数据从侧面印证了这个策略的市场认可：$200M
ARR，$9.3B 估值（$300M Series F，Accel + GIC 领投），Next.js 每周 2
亿次下载，AI SDK 每周 300 万下载。这些数字说明 Vercel
的分发能力已经足够强，接下来的问题是能否把这些分发转化为平台层的持续收入。

## 几个值得注意的局限

定价的复杂性。Vercel 的 credit-based billing 有超过 15
个独立计量维度——Functions 三个计费面、Sandbox 五个、加上 Edge
Requests、Fast Data Transfer、ISR、Image Optimization 等。2024 年 HN
上有多次讨论提到从旧模型迁移到 credit 模型后账单跳涨（有从 $20 涨到 $500
的案例）。AI Gateway no-markup 是真的，但 Gateway 是入口，它引向的
Sandbox 算力、Functions 计算、CDN 流量各自独立计费。

Sandbox 的功能完整度还有缺口。没有 GPU
意味着推理场景需要外部补齐。没有 BYOC 意味着数据 residency
和合规性约束无法满足。5 小时 session 上限对需要长时间运行的
agent（监控、持续巡检、后台任务）是硬限制。单区域部署（iad1）对全球用户不友好。Vercel
的产品迭代速度很快——persistent sandbox 从 beta 到 GA
只用了不到一年——但这些缺口目前是实在的。

信任方面，2026 年 4 月的安全事故是一个提醒（Vercel
官方公告）：第三方 AI 工具被攻破，通过员工的 Google Workspace
账号进入了 Vercel 内部系统。Vercel 的应对算透明，但攻击路径通过 AI
工具链进入这一点，暴露了 all-in 单一平台的结构性风险。

## 这对做 agent platform
的人意味着什么

Vercel 的产品路线图里埋着一个对 agent
平台创业者尤其相关的信号：它正在定义”agent
应用的标准技术栈”应该长什么样。

一个典型的 agent 应用今天需要拼接五到六种服务：模型
API、代码沙箱、任务队列、向量数据库、用户认证、前端 UI。Vercel
的策略是把这些全部收进一个统一的 TypeScript-first 平台。这不会消灭 agent
创业公司的机会——正相反，Vercel 提供了一个更快的 starting
point。真正的产品差异化仍然在应用层：你的 agent
解决什么问题、理解什么领域、怎么跟用户交互。Vercel 提供的是底层
plumbing。

Sandbox 的 persistent + Docker 组合对 agent
基础设施类产品尤其有用。如果你有需要隔离执行的
skill——比如运行一个需要特定依赖的脚本、访问某个需要认证的
API、处理一批敏感文件——Vercel Sandbox
可以提供一个可预热的执行环境，而不会像传统 serverless
那样每次冷启动时重装依赖。配合 AI Gateway 的多模型路由，agent
的后端从”自己搭五六个服务”简化到”定义能力、选择模型、执行、返回结果”。

Vercel 正在成为 AI
应用开发的默认起点。它赌的不是某个产品的技术优势，而是所有产品都在同一个地方的整合优势。理解这个策略，比单独评估任何一个产品都更重要。