---
layout: post.njk
source: https://yage.ai/share/open-source-acquisition-ai-infra-20260519.html
speaker: yage.ai
title: 既然都是开源的，为什么还要花几亿去买
date: '2026-05-19'
summary: 文章分析了Anthropic和OpenAI等AI巨头为何不直接fork开源项目，而是斥巨资收购。核心逻辑在于获取原开发团队的隐性知识、化解竞对截胡风险、掌控项目路线图，以及确保关键基础设施的深度整合与长期稳定性，而非仅仅是使用代码。
area: tech-engineering
category: ai-application
tags:
  - open-source-strategy
  - ai-infrastructure
  - m-and-a-strategy
  - technical-debt
  - agentic-workflow
people:
  - Jarred Sumner
  - Alex Rattray
  - Charlie Marsh
companies_orgs:
  - Anthropic
  - OpenAI
  - Bun
  - Stainless
  - Astral
  - Google
products_models:
  - Claude Code
  - Bun
  - Stainless
  - uv
  - Ruff
  - MCP
media_books: []
draft: true
status: evergreen
---

5 月 18 日，Anthropic 以超过 3 亿美元收购了 Stainless——一家为
OpenAI、Google、Cloudflare 等公司生成 SDK 的工具厂商。六周前，Anthropic
花 4 亿美元股票买了只有六名员工的 AI 生物技术公司 Coefficient
Bio。两个月前，收了西雅图 AI agent 初创 Vercept。再往前推，2025 年 12
月，收购了 JavaScript 运行时 Bun。

六个月内四笔收购。初看这是一家公司在一口气囤积开发者工具，但只要注意到一个细节，问题就变了：这些被收购的东西几乎全是开源的。Bun
是 MIT 许可证，Astral 的 uv 和 Ruff 是 MIT 和 Apache 2.0，Stainless
生成的 SDK 代码客户拥有完整版权。每条路都允许 fork——而且是零许可费的
fork。

那么问题就变成了：Anthropic、OpenAI
这些公司为什么宁愿花几亿买，而不是直接 fork
一份自己维护？答案是同一套逻辑，在三个不同的案例里反复出现。

## Bun：团队、风险和竞对截胡

Bun 是用 Zig 写的 JavaScript 运行时，月下载量 700 万，GitHub 82,000
星。Claude Code 的 native installer 直接绑在 Bun 上启动——3 毫秒，Python
慢 15 倍。Anthropic 收购声明里 Mike Krieger 的原话是 “Bun represents
exactly the kind of technical excellence we want to bring into
Anthropic”（Anthropic
公告）。

收购后 Anthropic
没有把它变成内部工具——继续开源，继续对外发布。但方向变了：内置图像处理
API、HTTP/3 支持、测试运行器的分片能力——都是 Claude Code
需要的，不是社区最急迫的。

2026 年 5 月，Bun 创始人 Jarred Sumner 在 GitHub 上提交了一份 Zig 到
Rust 的移植指南。四天后，超过 100 万行 Rust 代码被合并到主分支（DevClass）。Sumner
的说法是团队”好几个月不手动写代码了”——整项重写主要靠 AI agent
完成。这笔重写解决了 Bun
长期的内存泄漏问题，同时也化解了一个尴尬的冲突：Zig
创始人在官方行为准则里加了一条”严格禁止 AI/LLM 生成内容”的规则，而
Anthropic 的主业就是 AI。

一个外部 fork 能不能完成这种重写？不能。Zig
是小众语言，运行时的内部逻辑复杂，fork
代码可以跑，但要深度改动核心逻辑、调内存问题、做性能优化，没有原团队对每一行的理解就是盲飞。100
万行 Rust 在四天内合并——只有原团队加上 Anthropic 的 AI agent
配合才可能。这就是 fork 和收购的第一个差距：团队就是隐性知识。

还有三个差距同样重要。

第二个，依赖的可靠性。Claude Code 年化收入超过 $10
亿，它的运行时依赖绑在一家零收入、VC
支持的创业公司上。上游如果被竞对收购、倒闭、或者改变方向，fork
能护住代码但你要自己扛运行时的全部维护成本。收购消解了这种不确定性。

第三个，竞对不能拿。如果 OpenAI 买了 Bun，Claude Code
的运行时依赖就控制在竞对手里。fork 阻止不了这件事，收购可以。

第四个，路线图控制。fork 是防守，收购是进攻。收购后 Bun 的优先级向
Claude Code 倾斜。如果只是
fork，你和上游方向分歧时只能在自己的分支上越走越远，长期维护成本非线性增长。

Bun 的价格是 $2600
万融资额后的零收入出售。和它承担的风险相比，这笔账单是划算的。

## Stainless：同样的逻辑，不同的层

Bun 是运行时，Stainless 是连接层，但解答收购理由的框架不需要换。

Stainless 把 OpenAPI 规范自动转成跨语言的生产级
SDK——TypeScript、Python、Go、Java、Kotlin、Ruby、PHP、C#，外加 CLI
工具和 API 文档站点。Anthropic 自 API
开放第一天就在用它：anthropic-sdk-python 仓库里 825
个源文件的头部都是同一行注释
# File generated from our OpenAPI spec by Stainless。OpenAI
的 Node SDK 不仅用 Stainless 生成的代码，连发布脚本都直接把构建上传到
pkg.stainless.com（openai-node
仓库）。

Stainless 的客户名单覆盖了 AI API 生态的核心层：OpenAI、Google、Meta、Cloudflare、Replicate、Runway、Cerebras、LangChain。创始人
Alex Rattray 在收购公告中写道，全球约四分之一专业开发者使用过他们生成的
SDK 或文档站点（Stainless
blog）。

同样的问题：替代方案存在——Fern、Speakeasy 功能覆盖接近，开源的
OpenAPI Generator 支持 50 多种语言——为什么 OpenAI、Google
不自己换一个，而让 Stainless 成为共享依赖，直到 Anthropic 把它买走？

答案在同一个框架里。团队层面：Stainless 49 人团队里有 Robert
Craigie（Prisma Client Python 创建者），有四年的 SDK 生成工程积累——每次
API 变更自动反映到所有语言的所有
SDK，这种流水线的隐性知识迁移成本极高。竞对截胡层面：Stainless 同时服务
Anthropic 和它的所有主要竞对，收购后托管产品关闭，OpenAI 和 Google
失去了自动 SDK 同步。路线图层面：Stainless 还做 MCP Server 生成——从 API
规范自动生成 Model Context Protocol 服务器——这正好在 Anthropic 创建的
agent 连接标准上。Anthropic 在 2024 年底开源 MCP，2025 年 12 月移交给
Linux Foundation 下的 Agentic AI Foundation（AAIF
公告），MCP 生态已有超过 10,000 个公开服务器。拥有 SDK 到 MCP Server
的自动生成工具链，等于在所有人都能用的标准上拥有最快的执行速度。

Forbes 把 Stainless 收购称为 “infrastructure denial play”（Forbes）。这个说法捕捉了对竞对的影响，但没有捕捉到为什么竞对没有提前防御——答案也在
fork 框架的第三层：在 Stainless 被买走之前，OpenAI 和 Google 可以 fork
SDK 代码但没法 fork
维护能力，而竞对截胡是只有在收购发生时才暴露的风险。

## OpenAI 在对侧，同一套逻辑

把视野从 Anthropic 拉开。2025 年 4 月，OpenAI 试图以约 $30 亿收购 AI
代码编辑器 Windsurf，但排他期到期后交易破裂——Google 在 7 月介入签了
licensing deal，核心团队加入 Google DeepMind（Fortune）。OpenAI
之前还试过收购 Cursor，被拒（TechCrunch）。2026
年 3 月终于拿下两笔实质性交易：Astral——Python 工具链 uv、Ruff、ty
的团队；Promptfoo——AI 安全测试平台。

Astral 是这个框架最好的对称验证。uv 是 MIT
许可证的包管理器，月下载量超过 1.26 亿次，Simon Willison 用的词是
“load-bearing”——Python 生态的承重墙（Willison）。Ruff
和 ty 同理。OpenAI 完全可以 fork，但它要的不是代码，是 Charlie Marsh
的团队和路线图的决策权。通过 Astral，Codex
进入的不再是”生成代码”这一层，而是从依赖管理到代码检查的开发者完整工作流。

两家的收购呈现镜像结构：

层

Anthropic

OpenAI

运行时

Bun（$2600 万融资，零收入出售）

Astral（uv/Ruff/ty，月下载过亿）

Agent 产品

Claude Code（自研）

Windsurf 收购失败，Google 截胡

连接层

Stainless（$3 亿+）

自研 Agents SDK + 采纳 MCP

安全

—

Promptfoo

垂直行业

Coefficient Bio（$4 亿，6 人）

—

这些交易背后站着相同的 VC：a16z 同时是 Stainless 和 Astral
的投资方，Sequoia 投了 Stainless，Accel 投了 Astral。资本在主动促成 AI
lab 对共享基础设施的整合，而非鼓励这些工具公司保持独立。

把 Bun、Stainless、Astral
三个案例放在一起，叉开来看，收购不是偶然也不是炫富，是同一个判断的重复执行：MIT
许可证给了你 fork
的自由，但没有给你原团队的认知、阻止竞对截胡的能力、以及路线图的决策权。当一个
AI lab 年化收入 $300
亿、核心产品绑在第三方运行时上、竞对在同一个池子里抢同样的工具——「为什么不直接
fork」这个问题的答案，就是那笔收购费用的正当性。

## 从模型战争到管道战争

2024 年 AI 竞争的核心问题是「谁的模型最好」。2026 年的问题是「agent
跑在谁的基础设施上」。驱动力来自 agent 架构的成熟——当 AI
从回答问题转向执行动作，能力的天花板不再由参数规模决定，而是由 agent
能连接到什么系统、连接的速度和可靠性决定。Anthropic 的表述是 “agents are
only as capable as the systems they can reach”（Anthropic）。

在这个框架下，四笔收购落在同一个 thesis 的不同环节上。Bun 解决了
agent 启动速度——3 毫秒的冷启动对 CLI agent 是体验基石。Vercept 增加了
agent 能力深度。Stainless 解决了 agent 连接外部 API
的广度与维护效率。Coefficient Bio 是垂直行业的验证——当一个 lab
的基础设施足够强，向行业应用延伸成为自然选择。

而整个收购策略的核心驱动力，回到开篇的问题：这些被收购的东西都不是不可替代的——代码是开源的，替代品是存在的——但它们承担的依赖风险和隐性知识深度，让
“fork” 成了一个表面省钱、实际昂贵的伪选项。

## 这个趋势走多远

审视这个问题需要同时看两个相反的力。收紧的力在上升：Anthropic 收购
Bun 后，它的 Zig 版本在四天内被 100 万行 AI 生成的 Rust
代码替换——这不只是”继续维护”，而是用 AI
脱胎换骨地重写了基础设施本身。Stainless 的托管产品被关闭，竞对失去了自动
SDK 同步能力。Each case is shared infrastructure being internalized.

放松的力也存在。MCP 是中立标准，A2A 是中立标准，AGENTS.md
是中立标准。Stainless
的替代品——Fern、Speakeasy——存在。但关键问题不在于替代品是否存在，而在于迁移的隐性成本：四年的
SDK
生成流水线、九语言同步、零依赖的包大小优化——这些积累不是换一个工具能复现的。

两股力对峙的结果取决于速度差。如果竞对能在 6-12
个月内重建工具链，收购的长期价值收敛到团队和隐性知识。如果 Anthropic
能把 Stainless 和 Bun
的整合推进到竞对无法通过独立工具复现的程度——不只是生成 SDK，而是 Claude
agent 的连接体验形成系统性差异——那窗口期的先发优势就转化为产品壁垒。

对于在 AI 生态中 build
的团队，这轮收购改变了风险计算的方式。以前看一个开源工具，看到 MIT
许可证觉得安全——fork
是最后保障。现在需要多问一层：维护团队背后是谁的资本？路线图受谁影响？如果工具被竞对收购，fork
之后你扛得住多少维护成本？这些不是在杞人忧天——它们是在 2026
年真实发生的事。