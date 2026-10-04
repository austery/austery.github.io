---
layout: post.njk
source: https://yage.ai/share/cowork-3p-models-moat-shift-20260425.html
speaker: yage.ai
title: |-
  Anthropic 让 Claude Cowork
  跑别家模型，这件事比看上去更反常
date: '2026-04-25'
summary: Anthropic 的 Claude Cowork 支持第三方大模型，此举押注客户端粘性而非模型订阅和数据。文章将此置于四层 AI 基础设施模型中分析，强调了跨模型工作流和运行时/控制面层的重要性。文章对比了 Anthropic 的客户端策略与云厂商的治理策略，为初创公司、企业和投资者提供了 AI Agent 领域演进的洞察。
area: tech-engineering
category: ai-application
tags:
  - ai-infrastructure
  - llm-commoditization
  - agent-clients
  - enterprise-governance
  - multi-model-workflows
people:
  - Paweł Huryn
  - Charlie Dai
  - Janakiram MSV
companies_orgs:
  - Anthropic
  - AWS
  - Google
  - Microsoft
  - OpenAI
products_models:
  - Claude Cowork
  - Claude
  - GPT
  - Gemini
  - Claude Code
  - Cursor
  - OpenAI Codex
  - AWS Bedrock AgentCore
  - Google Vertex AI Agent Builder
  - Microsoft Entra ID
media_books: []
draft: true
status: evergreen
---

## 一件 72 小时前刚发生的事

四月二十二日到二十三日之间，Anthropic 在自家桌面 app Claude Cowork
里加了一个开关。打开它，Cowork 背后跑的就不再是 Claude，可以换成
GPT-5.5、Gemini 3.1 Pro、DeepSeek
V4，或者你公司内网部署的本地模型。这件事没有发布会，没有官方博客。最早把它公开化的是
The Product Compass 作者 Paweł Huryn 一条凌晨的 X 帖：

> Anthropic shipped it quietly. No announcement. No blog post. Just
> technical docs. I discovered it by accident. (The Product
> Compass, 2026-04-23)

字面读这件事，像是一家 frontier 模型公司在自我矮化。Anthropic
的核心资产是 Claude 模型，自家客户端却让你跑 GPT 和
Gemini，听起来跟把店面租给竞争对手没区别。事情真不是这样。Anthropic
这步棋的真实方向跟字面意思反着，且它跟同时间窗口里
AWS、Google、Microsoft 各自的动作合起来读，能讲出 agent
基础设施接下来一两年最值得跟踪的一条主线。

先说时间维度上的关键判断：这件事今天对你的工作没什么影响，十二到二十四个月之后会有。短期内
Cowork 用户基数还小，把模型换成 GPT 之后不少功能也降级了（语音、Computer
use、跨人共享 project 都没有）。72
小时窗口里你能找到的所有正向声音基本都来自 vendor
自己和首批尝鲜者，找不到完整的迁移故事，找不到独立
benchmark。如果你今天在用 Cursor 或 Claude Code
写代码，你不会因为这条新闻调整工具链。

但这件事提供了一个新的判断坐标。它和 AWS、Google、Microsoft
同时段的动作合起来读，能把”agent
基础设施的护城河接下来落在哪里”这个问题讲清楚。这才是它的真正价值。

## 先把今天的 agent
基础设施分四层

要看清这张地图，先需要一个共同坐标。我把今天的 agent
基础设施分成四层，从下往上：

模型层是大模型本身。Claude、GPT、Gemini、DeepSeek
这些。决定了任务能力的上限。

协议层是怎么调模型。OpenAI 的 Chat
Completions、Anthropic 的 Messages API、还有调外部工具用的 MCP（Model
Context Protocol，Anthropic 2024
年底提出，今天是跨厂事实标准）都属于这一层。它的特征是简单，文本进文本出，各家厂商最容易达成共识。

运行时层是真正用大模型干活的那段代码。Claude
Code、Cursor、OpenAI Codex、还有这次的主角 Claude
Cowork，都是运行时。它管的是怎么把任务拆成步骤、怎么决定调哪个工具、上下文怎么压缩、长任务跑了几小时之后怎么不走偏。同样的
Claude Opus，Matt
Mayer 实测在 Claude Code 里跑 SWE-bench 拿 77%，在 Cursor 里跑拿
93%，差出 16
个百分点。运行时这一层做不做得好，能决定一代模型升级的差距。

控制面层是企业要部署一堆 agent
时的那套基础设施。哪些 agent 注册在了系统里、每个 agent
调外部资源时用谁的身份、调用记录怎么审计、出了问题怎么追责、怎么扣预算。开发者很少直接接触这一层，企业
IT 和 CIO 是它的主要用户。AWS 的 Bedrock AgentCore、Google 的 Vertex AI
Agent Builder、Microsoft 的 Entra Agent ID 都在做这一层的产品。

四层之间正在发生一件事：单一模型不再覆盖所有任务，所以用户必然要跨家用。一家通吃这件事不再成立。frontier
模型已经分化出明显的强项弱项，写代码 Opus 4.7 强于 GPT-5.5，长文档检索
GPT-5.5 完胜 Opus 4.7，多模态 Gemini 第一，中文和高吞吐 DeepSeek
第一（对照一篇按任务派发的对比）。这个事实本身已经决定了今天严肃用
LLM 做事的团队都在跨模型组合工作流。

跟这个事实相关、但容易混淆的另一件事是模型公司之间的人才流动。NVIDIA
200 亿拿走 Groq 90% 的人，Google 24 亿拿走 Windsurf 核心团队，SpaceX
给了 Cursor 600 亿收购选项（acqui-hire
大势）。这不是”模型公司不重要了”，恰恰相反，这是模型团队太重要、公司护城河靠不住，所以买家直接买人。资本侧押的是核心能力会沿着团队流动，而不是沉淀在公司层面。这两件事合起来给到今天的状态是：模型能力很关键，但它会随团队流动，且没有一家覆盖所有场景。

这就给客户端这一层的玩家留下一个判断：用户必然要跨模型派发，问题只是在谁家客户端里派。Anthropic
这次动作就是回应这个问题。

## Anthropic 这步棋的真实方向

把视角往前挪一个月。三月二十一日，Anthropic 切断了第三方客户端用
Claude 订阅 token 调自家 API 的通道（HN 讨论）。原本
OpenCode、Cline、Aider 这些第三方 IDE 客户端可以让用户用 Anthropic
订阅来跑 Claude，那一天之后这条路被关闭，第三方客户端只能让用户走 API 按
token 付费。同时间 Anthropic 还在自家 Claude Code
里加了一整套防仿冒机制：原生客户端身份验证、故意植入的假工具用来反蒸馏、推理签名绑
API key。一整套机制的目的是让”Claude Code 是 Anthropic
自己的官方客户端”在协议层面变成可验证的事实。

把这两件事和四月二十二日的 Cowork 3P 摆在一起，方向就清楚了。

三月：把别家客户端蹭我家订阅这条路堵死。

四月：把我家客户端接别家模型这条路打开。

直接读这两步棋，是双面的：别人不许白嫖我的订阅补贴，我可以去白嫖别人。但底层判断只有一个：客户端是粘性，模型是过路货。模型可以换，但跑模型的客户端必须是
Anthropic 自己的；订阅必须绑在 Anthropic 自己的账号体系里；MCP
工具白名单、权限策略、审计、遥测都由 Anthropic
客户端这一层定义。Anthropic 自己 4 月 21 日发 Managed Agents 的那篇博客其实已经把这个姿态说出来了：

> We’re opinionated about the shape of these interfaces, not about what
> runs behind them.

意思是：我们的产品决定接口长什么样，不决定接口背后跑什么模型。这句话单独读不显眼，跟
Cowork 3P 一起读就是同一个战略的两面。

为什么 Anthropic
现在选这条路？因为模型层的差异化窗口在缩短，他们自己内部一定看到了。今年春天
Claude Opus 从 4.6 升到 4.7，社区出现一波”Opus 4.7 is
dogshit”的吐槽。已经有用户在 Substack 上写《我用
45 美元一个月的多模型组合替代了 Claude Code》。Anthropic
没法拦住这股势头。与其拦不如顺着：你想跨模型派发，就在我家客户端里派，别跳到别人那里去。

## 这是一个反常让步：连数据都不要了

跟商业模式直接相关的细节是 Anthropic 在 3P
这条路径上拿不到任何订阅费。文档明文写 “Third-party deployments have no
seat-based licensing from Anthropic”。如果你走这条路跑 GPT-5.5，钱付给
OpenAI；跑 Gemini，钱付给 Google Cloud。Anthropic
在这条路径上的收入是零。

但收入只是表层。更深一层的反常是：Anthropic
连数据也拿不到。

Bedrock 和 Vertex 路径下，prompt 和 completion 完全不经过 Anthropic
的 infra，数据驻留在客户云里。gateway 路径下情况一样。客户端的 telemetry
里也没有 prompt 和 completion 内容，只有用量和调试指标，且 admin
可以通过 MDM 把整套 telemetry 完全关掉。这意味着如果一家企业把 Cowork
部署在 Bedrock+GPT 路径上，Anthropic 拿到的是：一个 logo
装在用户桌面，几乎没有别的。

为什么这件事反常？一家 frontier
实验室的核心资产之一就是用户行为数据。这些数据用来做
RLHF（用人类反馈做强化学习对齐）、用来理解 agent
在真实场景里怎么工作、用来训下一代模型。OpenAI 把 Responses API
做成有状态的服务端，部分目的就是把会话状态和推理 trace
留在自己手里，这是头部模型公司的标准做法。Anthropic
这次的选择刚好相反。它主动把这个数据让出去，等于在赌：客户端品牌
+ 企业级 governance
控件，比模型层的数据飞轮和订阅费更值得守。

这是一笔大的 bet。如果赌赢了，Anthropic 在 agent
普及之后的格局里占住一个跨云、跨模型的客户端入口，相当于 LLM 时代的
Chrome 或 VS
Code。如果赌输了，它既没拿到钱也没拿到数据，剩下的只是品牌占位。Anthropic
主动选了这条路、且没开发布会，说明他们自己也意识到这个 bet
的非常规：既不愿意让市场把它解读成”模型公司认输”，也不愿意把新动作做成大新闻给投资人和合作伙伴造成预期错乱。

## 三家云厂在控制面层下注

跟 Anthropic 同一个时间窗口里，AWS、Google、Microsoft
都在动作。SiliconAngle 把这件事称为
agent control plane race hits overdrive at Next
2026。三家走的具体形态完全错开。

AWS 押的是 runtime 加 registry。Bedrock AgentCore 是
agent 跑起来的运行时，Agent Registry 是企业用来管理”我家这些 agent
都是谁”的目录。听起来很合理，但 InfoWorld 报道里 Forrester 的 Charlie
Dai 点了一个关键限制：这套
registry 必须跑在 AWS 账户里，他用的词是 “strategic
limitation”。注册的 agent 可以调外部系统，但 registry 本身不出
AWS。Thoughtworks Tech Radar Vol 34 给出的实施建议更直白：只用 AgentCore
的 runtime 部分，agent 的核心逻辑放在外面（比如
LangGraph）做。两个独立来源给出同一个判断方向。

Google 押的是工具治理。Vertex AI Agent Builder 加上
ADK（开发框架）加上 Apigee（企业 API
网关）凑成一条供应链。最关键的角色是 Apigee：把企业现有的几千上万个 API
自动转成 MCP 工具，灌进自家的 API Registry。开发者不需要重新封装，agent
现成就能用。这条路的赌注是：企业的 API 网关已经在 Google Cloud
上，agent 调外部系统的入口顺势接管。

Microsoft 押的是身份。它把每个 agent 当作一个
service principal（企业 IT 圈对”自动化账号”的标准说法）注册到 Entra
里（也就是原来的 Azure AD），每个 agent
像员工一样有自己的身份、权限、生命周期。Agent 365
是覆盖在上面的治理层，2026 年 5 月 GA，定价 15 美元 / 用户 / 月，需要
Microsoft 365 Copilot 许可证作前置门槛（Forbes 4-10 详细对比）。这条路赌的是：企业的身份系统已经押在
Active Directory 上，agent
的身份认证并进同一套体系是最自然的延伸。

把四家放一起看：

谁

主要押注

落在哪一层

Anthropic

Cowork、Claude Code、Managed Agents

客户端 + 运行时

AWS

Bedrock AgentCore + Agent Registry

控制面（偏 runtime）

Google

Vertex Agent Builder + ADK + Apigee

控制面（偏工具治理）

Microsoft

Foundry + Entra Agent ID + Agent 365

控制面（偏身份）

这里值得点出一个 Anthropic 这边特殊的地方。多模型客户端不是 Cowork
首创，Cursor、GitHub Copilot、Google Antigravity
都早就支持多家模型。但前面这些客户端要么属于产品公司（Cursor、Anysphere），要么属于云厂或平台公司（Copilot
是 Microsoft，Antigravity 是 Google）。Anthropic 是第一家自己是
frontier
模型公司、自己出客户端、还在客户端里让你跑别家模型的厂商。这个组合在行业里没有先例，方向跟
frontier 实验室的常规姿态相反。

云厂三家的赌注有个共同问题：控制面比客户端难做开发者粘性。开发者每天打交道的是
IDE、CLI、代码 review，不是 IAM
控制台。注册表、可观测性、审计这些东西对企业管理员是刚需，对实际写代码的人是低频接触面。云厂的赌注更靠近
CIO，Anthropic
的赌注更靠近开发者。哪一头权重更大，看行业看公司。在金融、医疗、政府这种合规驱动的行业里，CIO
权重更高，云厂占优；在创业团队、研发驱动的公司里，开发者权重更高，Anthropic
占优。中间地带是接下来一两年最有意思的战场。

## 三个具体场景，可以马上拿去对号入座

地图讲完了，回到读者自己的位置。这件事跟你的关系怎么落地？三个场景是接下来一两年最常见的：

场景一：你是创业团队的技术负责人，正在选 agent
工具链。如果你押 Cowork，意味着你押了 Anthropic
这条客户端粘性的赌注，换来的是模型层的灵活度（GPT、Gemini、Claude
你随时可以切）。如果你押 Cursor，模型层灵活度差不多，但工具链锁在 Cursor
自己的产品方向上。如果你完全押 OpenAI Codex，你拿到的是 Responses API
的高度集成，代价是模型选择被锁死、自托管几乎走不通。这三条路没有绝对优劣，但每一条都有它显式让出去的东西。看清楚自己让出去的是什么，比看哪家今天最火重要。

场景二：你在大企业 IT 部门，最近 CIO 让你做 agent
治理方案。云厂的三条路（AWS Registry、Google Apigee、Microsoft
Entra Agent ID）都在卖你”怎么管一堆
agent”的能力，但每条路把治理边界画在了自家产品线之内。AWS
的注册表只覆盖跑在 AWS 上的 agent，Microsoft 的身份治理只覆盖进了 Entra
的 agent。如果你是 Azure 重度用户，Microsoft
的身份这条路最自然。如果你是 AWS 重度用户，AgentCore
顺手。如果你跨云，你会发现没有一家给你跨云治理面，你必须自己拼。这一点不是产品
bug，是商业意图。

场景三：你在投资侧，看 agent infra
公司。最有用的一个问题是：“如果模型层 commodity
化、协议层全部开放，这家公司还剩下什么。” Anthropic 的答案是
Cowork、Claude Code、MCP 生态、企业级 governance 控件。OpenAI 的答案是
Codex、Responses API、跟 Microsoft 的渠道。Cursor 的答案是 IDE
体验加自有团队。一家公司答不出这个问题，长期处境就要打折扣。MCP
这一类协议层的开放化在加速，跨厂统一是趋势，但接入开放协议不等于摆脱平台锁定。治理流（注册、身份、审计、计费）仍然落在每家自己的私有控制面里。读招股说明书或产品文档时，要把协议互通和治理互通分开问。

## 最后一句

这次 Cowork 3P
上线对今天的工程实践影响不大，但它是一组同时发生的动作里的一个具体信号。Anthropic
三月切第三方客户端、四月开第三方模型；AWS 推 AgentCore Registry；Google
把 Apigee 接进 Vertex；Microsoft 推 Entra Agent ID 加 Agent 365；OpenAI
把 Responses API
做成有状态的私有控制面。每一家都在自己最有优势的那一层加固，每一家也都在等其他家先在某一层让步。当下没有赢家，但下注的方向已经在地图上画清楚了。

把模型层当成接下来一两年的 commodity
来看，把客户端、运行时、控制面这三层当作几组并行的护城河来看。Anthropic
那笔反常的让步是这张地图上最值得记住的一手：拿模型层的订阅费和数据，换客户端层的留存。它能不能赢，过两年回头看就知道了。

## 来源索引

### 一手资料

Use Claude Cowork with third-party platforms — Anthropic 官方支持文档

Install and configure Claude Cowork with third-party platforms

Anthropic Engineering: Managed Agents (2026-04-21)

AWS Blog: Running Claude Cowork in Amazon Bedrock

### 行业媒体与分析

The Product Compass: Cowork on 3P Any LLM (Paweł Huryn) — 事件首发

SiliconAngle: Agent control plane race hits overdrive at Next 2026

InfoWorld: AWS targets AI agent sprawl with new Bedrock Agent Registry — Forrester Charlie Dai 评价

Forbes (Janakiram MSV): Agent Registries Become The New Battleground For Cloud Giants

Thoughtworks Technology Radar Vol 34 (PDF)

Horses for Sources: How Anthropic is devouring IT services

Towards AI: Anthropic Just Shipped the Layer That’s Already Going to Zero

### 用户实测与行为证据

HN #46549823: Anthropic blocks third-party use of Claude Code subscriptions — 三月 OAuth 切断事件

Tyler Folkman: I Replaced Claude Code With a $45/Month Multi-Agent System

Matt Mayer: AI coding harness agents 2026 — Claude Code vs Cursor SWE-bench 对比

### 作者既有写作

GPT-5.5、Claude Opus 4.7、DeepSeek V4：什么任务该选哪个模型 (2026-04-24) — jagged frontier 与按任务派发

老马要买 Cursor：600 亿收购、100 亿合作，和科技圈正在流行的买人不买壳 (2026-04-21) — 模型层 acqui-hire 大势