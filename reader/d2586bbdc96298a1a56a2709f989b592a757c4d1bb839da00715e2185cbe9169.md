---
layout: post.njk
source: https://yage.ai/share/claude-tag-deconstructed-20260623.html
speaker: yage.ai
title: |-
  Claude Tag
  拆开看：技术上没那么新，但企业授权的对象变了
date: '2026-06-24'
summary: 文章分析了 Claude Tag 等 Agent 产品在技术层面与企业应用层上的变化。核心观点是，这些产品并非模型技术的本质突破，而在于将 AI 视为需要正规授权、治理和计费的非人类执行体。真正的变革在于企业管理对象从“谁装了 App”转向“这个 Agent 以什么身份存在、能访问什么、谁负责它”，这正在重塑企业软件的分发逻辑和定价模式。
area: PAI
category: ai-tooling
tags:
  - agentic-workflow
  - governance
  - context-management
  - enterprise-adoption
people: []
companies_orgs:
  - Anthropic
  - Microsoft
products_models:
  - Claude Tag
media_books: []
draft: true
status: evergreen
---

6 月 23 日，Anthropic 发布了 Claude
Tag：@Claude 变成
Slack 里一个永远在场的团队成员，ambient mode
让它能在频道里主动介入，不必每次等人点名。官方的说法是，它像一个可以 @
的同事，记得频道里发生的事，会主动跟进被遗忘的任务。听起来像是 agent
形态的一次大跃迁：一个不关机的 AI 同事上线了。

但拆开看，技术上它没有那么新。底下还是给 HTTP endpoint 发请求，Slack
@
只是换了种触发方式；它记住的是频道聊天记录，和组织的经验智慧是两回事；和你开一个
Claude session 一直不关，区别也没宣传的那么大。

那它到底改变了什么？真实的变化在另一层：企业开始把 agent
当作一个需要正经授权、治理、单独计费的非人类执行体。底层还是那些无状态的模型调用，但企业管理的对象从「谁装了这个
app」变成了「这个 agent
以什么身份存在、能访问什么、谁负责它、花了多少钱」。这一层的变化是真的，而且正在改写企业软件的分发和定价方式。

再往深一层看，这些产品宣称的「持续学习」目前还没做到。它们持久化的是协作痕迹，不是可复用的组织经验。真正的护城河，是能把上下文压缩成受治理、可执行、会过时的组织记忆。这件事还没人做出来。技术的路线图指着那个方向，但落地的渗透率还很低。

Claude Tag 拆开看：表层是常驻同事，底下是
HTTP endpoint 加治理层

## Claude Tag 是什么

Claude Tag 以团队成员身份加入 Slack
频道。管理员授权它可以访问哪些频道、工具、数据源和代码库，频道里任何人
@Claude
就能委派任务。Claude 把任务拆成阶段，用获授权的工具执行，在 Slack thread
里回复成果。它基于 Opus 4.8，面向 Enterprise 和 Team 客户，以 research
preview 形式上线，会在 30 天内取代旧的 Claude in Slack app。

它的 multiplayer 设计让一个频道共享一个 Claude
identity，多人可见工作进度，每个人都可以从上一个人停下的地方接手。持续学习机制让
Claude
跟着频道积累上下文，用户不必每次都从头解释，经授权后还能从其他频道和数据源获取信息。ambient
mode 打开后，Claude
主动汇报它认为频道成员需要知道的事，跨频道标记相关信息，跟进变冷或未完成的
thread 和任务。这三个特性合在一起，听起来像一个在协作工具里常驻的 AI
同事。

## 技术没有本质变化

Claude Tag 这类产品在工程上有整合，但没有模型层的突破。

先看 ambient 这件事。Claude Tag 的 ambient mode，听起来像是 AI
自己在「听着」频道里发生的事情，随时判断要不要插嘴。但拆到实现层，Slack
@、webhook、定时触发，底下都是给同一个 endpoint
发一次请求，让模型跑一遍。LLM
本身不记得世界，每次调用都要从外部把上下文重新装配进去，所谓的持续性全靠外部的存储、调度和循环在撑。这件事在触发和调用上和定时任务没有本质区别。但
Claude Tag 在运行时确实多了一层东西：独立的 agent identity、按频道设的
spend limit、记录每次调用和 memory 写入的 audit log、可以跑数小时数天的
scheduled
tasks。这些是普通定时任务没有的运行时契约。但注意它们都是治理性质的——身份、预算、审计、生命周期。这恰好引出了下面那层真正的变化。

再看记忆这件事。Claude Tag
宣称的「持续学习」，实际存的是频道聊天记录加检索。这是原始的 I/O
痕迹，不是组织真正的记忆。真正的组织记忆是 tribal
knowledge：上次在哪个系统踩了坑、某个客户的特殊偏好是什么、改这块代码前必须先跑哪个检查、团队对「完成」这个词的定义是什么。这些是从多次经验里抽象沉淀出的可复用知识，不是对话原文。

从聊天记录到 tribal
knowledge，中间隔着一个压缩过程：把单次事件提炼成可复用的规则，经团队确认，进入执行流程，过时了要能废弃。让
LLM 记住东西，目前就两条路：把上下文全塞进窗口，或者用 RAG
检索相关片段。这两种方式都给了它读取能力，但写不进去。每次调用结束，模型权重纹丝不动；外部记忆如果没人主动把结构化规则写进去，系统状态就不会真正更新。理论上把全部聊天记录从头回放，agent
能表现得像掌握了经验，但 token
成本会随着时间累积爆炸，每一步都要重新读取之前的所有内容，工程上不可行。值得说一句的是，Anthropic
自己并非没有这层技术：它的 Managed Agents 有一个叫 Dreams 的
API（research preview），做的是 memory 去重、解决矛盾、copy-on-write
式的整理；claude.ai 个人版也有每 24
小时自动摘要的轻量整理。但这两样都没集成进 Claude Tag，所以 Claude Tag
的记忆仍然停在 retained context 加检索这一层。

一个一直开着的 Claude
session，对话连贯性甚至可能比多人碎片的频道历史更强。前者的对话线是连续的，后者要从多人讨论里重建意图。真正的区别不在上下文长度，而在系统归属：Claude
Tag 属于协作空间，共享、可审计、有独立授权；私有 session
属于个人。这些区别主要在治理层。ambient mode
的后台运行和跨频道拉取相关上下文算超出纯治理，但那个跨频道学习仍然是浅层检索，不是从经验里沉淀可复用的知识。一个产品如果没有独立授权和共享审计，就退化成了
Slack 里的长 session。

Claude Tag 在技术层面是工程整合，不是认知跃迁。ambient
的触发和调用没有超出事件驱动加模型调用，运行时多出来的 identity、spend
limit、audit 都是治理性质的增量；记忆存的是聊天记录而不是组织智慧；和长
session 的核心差异在治理不在上下文长度。

## 真实变化在企业授权

企业开始把 agent
当作一个需要授权、治理、计费的非人类执行体。在这条路线上想得最清楚的是微软。

微软的 Entra
Agent ID 直接把 agent 当作企业目录里的一等公民来管理。每个 agent 有
blueprint（类型模板，定义一类 agent 的特征和权限），有
sponsor（业务责任人，决定 agent 什么时候不再需要）和
owner（技术运营人，负责日常技术运营和事件响应）双轨责任制。微软官方原文是这么写的：agent
身份让 agent “traceable, authenticated, authorized, and secured, just
like any user in your organization”。

这件事改变了分发的逻辑。过去企业授权的是人使用
app，信息安全模型围绕「谁装了哪个软件」展开。现在企业要授权的是一个
agent：允许它访问哪些数据、以什么身份行动、谁为它的行为负责、权限什么时候过期。治理本身成了新的分发入口。微软的
Agent 365
用身份、威胁防护、数据防泄漏、注册登记、生命周期这套五件套把这条逻辑产品化了。

微软 Work IQ 官方博客有一句话，说的就是这个判断：“Software
is moving from applications built for people to agents that can reason,
retrieve context, and even act on a user’s behalf.”
把这句话写在官方路线图里，本身就是信号。

a16z 的
Sarah Wang 说得更进一层：system of record（记录业务数据的系统，如
CRM、ERP）正在降级成单纯的存储层，战略杠杆转移到「谁能在 agent
替员工干活时控制那个执行环境」。

定价也在跟着变。always-on agent
一旦持续运行，成本就是连续的、不可预测的。Reddit
上有一个真实案例：一个用户在 5 台机器上跑 persistent agent，一个月烧了相当于
$41,952 的 API 成本，其中 99.6%
是反复读取已有上下文的成本，真正生成新内容的部分不到万分之四。一个持续在场的
agent，钱主要花在维护和回放上下文，不在产出。这种成本形态和订阅制的固定配额在数学上不兼容：配额太松厂商亏钱，太紧用户受不了。OpenAI
Codex 在 4 月把 Enterprise 计费转成 token-based credits，微软 Work IQ
从按人头切到 consumption-based 的 Copilot Credits，Salesforce Agentforce
用 per-conversation 计费，Workday 推出了 Flex
Credits。同一时期，多家头部企业 SaaS
把核心计费从按人头转向按实际消耗。

这一层的变化，不需要 agent
已经学会组织记忆就能发生。一个工程整合型的产品，只要它变成了企业正经管理的执行体，就足以改变企业怎么买软件、怎么付钱。底层技术没什么新东西，但企业的治理对象从人扩展到了
agent。这个变化是真的。

## 持续在场不等于持续学习

Claude Tag 这类产品越是强调 persistent
context，就越暴露它们还没解决真正的记忆问题。raw context
越长，回放越贵，噪声越多，越需要一个能抽象和压缩的中间层。前面那个每月
$41,952
的案例已经点出这层：钱几乎全花在回放上下文而不是产出，说明一个长期运行的
agent 真正需要的不是无限回放，而是把历史压缩成可复用的知识。

目前没有任何一个产品做到从经验中自动沉淀可复用的 SOP。微软 Work IQ 的
playbook 是人写好存在 SharePoint 里的，不是 agent
从执行经验里提炼出来的。微软官方演示里用的是一份人工维护的响应程序文档，agent
只是在执行时查询它。Letta
的 sleep-time compute 是对单次 context 的离线预处理和推断，不是跨
session 的经验积累。学术界在 procedural memory 方向上的探索，比如 Mem^p，还停在 benchmark
阶段。SOP-Bench
的数据显示 agent 执行复杂 SOP 的成功率只有
27-48%，连执行都还没到位，更谈不上从经验中自动沉淀。

这并不否定产品的商业价值。一个能持续在场、受治理、按用量计费的
agent，即使还没学会组织智慧，已经改变了企业软件的运行时对象。但它离真正的同事还差一层认知突破。持续学习和
tacit knowledge
积累，产品宣称的护城河，目前都是空的。真正的护城河是能把原始上下文压缩成受治理、可执行、会过时的组织记忆，这件事还没人做出来。这是当前架构的硬限制：LLM
是 pattern
matcher，单次调用里能推断，但调用结束权重不变；外部记忆如果不主动写入结构化规则，系统状态就没有真正更新。这是下一波竞争的焦点。

这个从原始上下文到可复用知识的压缩，在个人层面已经有了可行的方向。关键在于一个判断：模型智能跨过一道坎之后，决定产出质量的瓶颈会从模型本身转移到上下文的密度和质量。我们之前写过这个转折，并开源了一套叫
Context
Infrastructure
的参考实现，核心是从原始的行为数据里分层精炼出可复用的判断原则。企业级
agent
要补的那一层，本质上是这个机制的组织版本：多人协作、受治理、会过期。

## 落地还早，但方向是确定的

Claude Tag 这类产品的本质，还没有到达它们宣称的「agent
变成同事」。那需要认知突破，还在等待发生。已经发生的，是企业第一次要正经管理一个非人类执行体：给它身份、权限、预算、审计。底层技术没那么新，但企业授权和治理的对象变了，分发和定价跟着变了。

落地上要保持冷静。Gartner
预测超过 40% 的 agentic AI 项目会在 2027
年前废弃，原因主要是集成差、归属不清、扩产时成本飙升。微软 Copilot
的试点只有约 6% 转成了大规模部署。Gartner 把 agentic AI
放在期望膨胀的顶点，目前只有约 17% 的组织部署了 agent，大量号称 agent
的产品其实是 chatbot 在重新包装。Gartner 同时预测，到 2028 年 agentic AI
将驱动超过 $4500 亿的企业软件收入，至少 15% 的日常决策将由 agentic AI
自主做出。方向成立，渗透率还很低。

更确切地说，企业软件的运行时对象正在从 app 变成受管
agent。这是治理和商业系统的迁移，不是模型认知系统的跃迁。而谁能先解决持续学习那一层，把聊天记录和组织经验之间的那条沟填上，谁才可能把「同事」这个词从营销变成现实。