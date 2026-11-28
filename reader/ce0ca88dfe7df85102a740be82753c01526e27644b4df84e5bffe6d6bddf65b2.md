---
layout: post.njk
source: https://yage.ai/share/openrouter-llm-gateway-survey-20260419.html
speaker: yage.ai
title: 用 OpenRouter 做企业 AI Sandbox 入口
date: '2026-04-19'
summary: 本文探讨使用 OpenRouter 作为企业 AI 沙盒入口的策略。文章分析了其连接多家模型提供商、统一账单的优势，但重点强调了启用前必须处理的三个关键问题：Prompt Caching 失效、Agent 场景下成本失控、以及数据留存策略。此外，还讨论了延迟、可用性、限速等日常使用中的体验问题，并给出了在数据安全、治理或仅使用少数模型时的替代方案建议。
area: tech-engineering
category: ai-application
tags:
  - openrouter
  - llm-gateways
  - ai-sandbox
  - cost-management
  - prompt-caching
people: []
companies_orgs:
  - OpenRouter
  - OpenAI
  - Anthropic
  - Google
  - DeepSeek
  - Moonshot
  - LiteLLM
  - Portkey
  - Helicone
  - Cloudflare
  - TrueFoundry
  - Requesty
products_models:
  - OpenRouter
  - Claude Opus
  - Claude Sonnet
  - Claude Haiku
  - Gemini 2.5
  - GPT-5.2
  - VSCode Copilot
media_books: []
draft: true
status: evergreen
---

## 背景和判断

公司想让团队自由试各家模型，但为每个开发者分别开
OpenAI、Anthropic、Google、DeepSeek、Moonshot
的账号不现实，合同和法务成本就能占掉大半预算。统一入口是自然选择。OpenRouter
提供一个 OpenAI 兼容的 endpoint，后面挂 300 多个模型、60 多家
provider，接入只需要改 base_url 和 API key，计费统一到一套 credit
系统，企业只和 OpenRouter 一家对账。同类产品还有
LiteLLM、Portkey、Helicone、Cloudflare AI Gateway、TrueFoundry、Requesty
等，解决的是同一组问题，区别在托管模式和企业控制力上。

Per-token 费用和上游一致，CostGoat 对 Claude
Opus/Sonnet/Haiku 的比价确认了这一点。额外成本是充值手续费：信用卡
5.5%，加密货币 5%，单笔最低 0.80 美元，大额预付可以摊薄。BYOK 方面，2025-10
起的政策每月头 100 万次 BYOK 请求免费，超出按上游定价 5%
收取，中等规模团队通常够用。

探索性 sandbox 用 OpenRouter 合理，门槛低，覆盖广，起步快。但 5.5%
手续费只是账面上看得到的成本，实际使用中有三个地方会产生远超手续费的隐性开销，需要在启用前就处理好。

## 启用前要处理的三件事

### 1. Prompt caching
可能在网关层失效

Anthropic 的 cache read 只按原价 10% 计费，cache write 5 分钟 TTL 按
1.25 倍、1 小时 TTL 按 2 倍。OpenAI 自动缓存打五折。典型 agent
工作流有大量重复前缀，caching 命中率高的话总成本能降 60% 到
90%。这个差异比 5.5% 手续费大一个量级。

OpenRouter 支持 caching，但机制在不同 provider
上不一样。OpenAI、DeepSeek、Gemini 2.5 走隐式缓存，provider
自动按前缀匹配，客户端不需要做额外处理。Anthropic
走显式缓存，客户端要在请求里加 cache_control breakpoint。OpenRouter
的 caching 文档说明两种模式都支持，并且通过 provider sticky routing
来维持缓存热度：同一用户的后续请求会被固定到上次服务的 provider
上，前提是该 provider 的 cache read 比普通 prompt 便宜。sticky provider
不可用时 fallback 到下一家，缓存归零重建。

问题出在实际命中率上。opencode 的一个
issue 记录了典型场景：通过 OpenRouter 调 Anthropic，第一条 system
message 成功缓存，但对话变长后 OpenRouter
不再更新缓存边界，每一轮都按完整上下文重新计费，成本变成直连的数倍。

常见失效原因有三个。指定 provider.order 会禁用 sticky
routing，官方文档明确说两者不共存。Anthropic 的 top-level
cache_control 只对 Anthropic 直连生效，走 Bedrock 或 Vertex
的请求会被排除。还有一个更隐蔽的：system prompt
里任何动态内容（时间戳、session id）都会打碎 cache
prefix，这个问题直连也有，但经过网关多一层包装后更难排查。

怎么办：上线前用同样的工作流分别走 OpenRouter 和直连
Anthropic 各跑一天，比对 activity dashboard 里的 cache_discount
字段。落差明显的工作流走直连。System prompt 里不放动态内容，不手动指定
provider.order。

### 2. Agent 场景下账单容易失控

5.5% 手续费本身不高，但 agent 场景的实际账单经常远超预期。Trustpilot
上有开发者报告在 VSCode Copilot 里调 Sonnet 4.5，几分钟烧掉 50
美元。原因是 agent 模式一次提问触发几十次 tool
call，每次都按完整上下文计费。如果 caching 同时失效（见上一节），tool
call 的每一轮都按全价走，成本是正常预期的十倍以上。

聚合网关在这个问题上比直连更危险。直连时开发者至少能在 provider 的
dashboard 上实时看到每个请求的花费，OpenRouter
多加了一层抽象，per-request
成本的可见性降低，团队自助使用时更难察觉开销在累积。

怎么办：启用前按人或按 API key
设日预算和月预算上限。OpenRouter 的 Spend Caps 需要 admin
主动配置，默认不开。如果 sandbox 里会跑 agentic 工作流，预算上限是必须在
day one 就配好的。

### 3. 数据留存选项要在第一天决定

OpenRouter
默认不存 prompt 和响应，只记录 metadata（token 数、延迟、请求
ID）。在这个基础上有两条 opt-in 路径。

第一条是 Input/Output Logging。打开后 prompt 和响应存到隔离的 GCP
bucket，AES-256 静态加密，保留至少
3 个月。对调试和审计有用，但数据离开了你的基础设施。

第二条是用数据换 1% 折扣。Char Blog
的分析认为 ToS 授予 OpenRouter 对 prompt 和响应的 irrevocable
commercial rights，授权一旦生效无法撤回。企业 sandbox
不应该开这个选项。

上游 provider 层面，OpenRouter 提供 Zero Data Retention (ZDR)
变量，可以把请求只路由到承诺零留存的 provider，代价是可选模型变少。

审计能力方面，OpenRouter 默认档缺少 SOC2 Type II 认证、完整 audit log
和 RBAC 组织架构，Requesty 和 Merge.dev
都指出了这一点。key rotation 只能通过 Management API
手动触发。Enterprise 档位补齐了一部分（SSO、EU in-region
routing、SLA、专属工程师），但需要签企业合同。

怎么办：Sandbox
只跑内部实验、不碰敏感数据，默认档够用。一旦 sandbox
里出现客户数据或合规敏感业务，要么升
Enterprise，要么换一个治理层默认打开的方案。出现客户数据时启用 ZDR only
routing。

## 日常使用中的体验问题

上面三件事需要在启用前解决。以下问题不影响是否采用
OpenRouter，但会影响日常使用体验，提前了解可以避免排查时走弯路。

延迟。所有请求多经过一跳，额外延迟大约 50
到 150 毫秒。官方延迟文档列出三种会放大延迟的情况：新
region 的边缘缓存冷启动（前 1 到 2 分钟明显变慢）、余额低时 credit
balance 检查变频繁、主 provider 失败触发 fallback 重试。新加坡 Azure
访问 OpenRouter 时 TLS 握手和首包回复本身不慢，但访问美国 provider
的后端仍要穿越太平洋，延迟和直连一样，多出来的是 OpenRouter
在路径上做计费、路由、fallback 判断的时间。

可用性。Status page 显示 2026 年 4
月整体 operational，只有 4 月 14 日一次约一小时的 generation endpoint
故障。但 r/openrouter
上社区报告的 timeout 频率更高。Status page 监控的是 endpoint
可达性，用户体验的是端到端完成率，provider
层面出问题时两个指标会脱节。LeadAI
的总结准确：OpenRouter is production-ready, but it does add a dependency
— if OpenRouter’s infrastructure fails, all routed requests fail。

Rate limit。平台层面的限制不严：免费模型每分钟 20
请求，购买 10 credits 以下每天 50 次，10 credits 以上升至 1000
次/天，付费模型充 10 美元以上没有显式平台级限制（官方文档）。但上游
provider 自己的限额仍然存在，r/openrouter
上持续有 429 错误报告，多数来自 Gemini 在高峰期打满自身限额，OpenRouter
透明传递。big-AGI issue
#980 还记录了长 session 高 token 数的请求在 OpenRouter
上被截断，同样请求直连 Anthropic 或 Google 可以完整返回。OpenRouter 的
fallback 机制可以绕开部分问题：主 provider
失败时自动试下一家，代价是首包延迟叠加。

:online 后缀。folding-sky
发现用 :online 时 OpenRouter 在请求到达模型前强制做一次 web
search，把结果塞进
prompt，每次都搜，包括在同一个对话里继续上一轮的话题。这会覆盖
GPT-5.2、Claude、Gemini 本身的搜索判断，增加延迟和 token 成本。

区域限制。OpenRouter 对中国大陆 IP 返回 403 Author
Banned，LinkedIn
上有记录，OpenRouter 的解释是上游 provider 合规要求。新加坡 Azure
部署不受影响。OpenRouter 上标注为 MiniMax、Moonshot、Zhipu GLM 的
provider 实际注册在新加坡，数据中心在新加坡或美国。ChinAI
#349 指出真正在中国境内 host 的只有
DeepSeek，且默认关闭。聚合网关的可用性绑定在每一家上游 provider
的政策上，任何一家的政策变化都会传导过来。

这些问题的通用缓解方式是给最常用的 provider 保留一份直连 fallback
key，OpenRouter 出问题时可以立刻切换。

## 什么时候该用别的方案

OpenRouter 适合探索性 sandbox，门槛低、覆盖广、5.5% 手续费换的是多家
provider 合同和法务的多头成本。以下几种情况应该考虑其他方案。

数据必须留在自己的基础设施上：LiteLLM 或 Helicone 提供 self-hosted
网关。LiteLLM 支持 100 多个 provider，有管理面板、虚拟 API key、per-team
budget，代价是自己运维一个 proxy。

需要 guardrails 和完整审计链路：Portkey 在这个方向上定位最清晰，PII
redaction、prompt injection 检测、jailbreak detection、audit trail
默认包含。

需要 EU 数据驻留或 SOC2 Type II：Requesty 和 TrueFoundry
的商业模式假设客户是企业，这些能力默认包含。

只用一两家 provider：直连更合适。聚合网关的价值随模型多样性增长，只用
Claude 或只用 OpenAI 时，它只是多了一跳和 5.5% 手续费。

LLM
网关正在分成两条路线：以便利为主（OpenRouter）和以治理为主（Portkey、LiteLLM、TrueFoundry）。大多数团队务实的做法是拿
OpenRouter 当 sandbox 入口，正式负载出来再做迁移决策。OpenAI
兼容接口意味着迁移成本可控，用它不等于绑定它。

## 来源

OpenRouter 官方文档： - FAQ · Pricing · Enterprise · Enterprise
Quickstart - Data
Collection · Provider
Logging · Input
& Output Logging - BYOK ·
1M
Free BYOK - Prompt
Caching · Latency
& Performance - Rate Limits ·
Model
Fallbacks · Usage
Accounting - Status
Page

第三方评测与对比： - remio.ai:
OpenRouter vs Claude Direct API · TrueFoundry:
LiteLLM vs OpenRouter · Merge.dev:
OpenRouter alternatives - Helicone:
Top 5 LLM Gateways 2025 · Requesty vs OpenRouter
· LeadAI Review · CostGoat Pricing

用户反馈与行为证据： - Trustpilot
reviews · r/openrouter:
Outage reports · r/openrouter:
Reliability issues · r/openrouter:
Gemini 429 errors - opencode issue
#1245: Anthropic caching broken · big-AGI issue
#980: Cutoff responses - folding-sky:
OpenRouter search behavior · Char
Blog: Data retention analysis

区域和生态： - ChinAI
#349: Tokens Made in China · LinkedIn:
OpenRouter China 403