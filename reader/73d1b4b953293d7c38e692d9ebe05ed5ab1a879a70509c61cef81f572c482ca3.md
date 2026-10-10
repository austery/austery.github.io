---
layout: post.njk
source: https://yage.ai/share/mcp-vs-openai-state-20260703.html
speaker: yage.ai
title: 两条相反的路：MCP 去状态，OpenAI 加状态
date: '2026-07-03'
summary: 文章对比了MCP和OpenAI在状态管理上的两种不同路径。MCP从隐式状态（stdio）演进到显式会话再走向无状态，是社区被动演进的结果；而OpenAI则主动通过平台战略推动有状态化，将推理过程和托管工具收归服务端，形成商业锁定。这种差异反映了开放标准与商业驱动的组织定位对协议演进方向的影响。
area: tech-engineering
category: ai-application
tags:
  - state-management
  - mcp
  - openai
  - protocol-evolution
people: []
companies_orgs:
  - MCP
  - OpenAI
products_models:
  - GPT-5
media_books: []
draft: true
status: evergreen
---

## 一个去状态，一个加状态

2026 年 7 月，MCP
发布了新版规范的候选版本，把协议核心从有状态改回无状态。简单说，以前调一次工具要先握手、拿一个会话编号、后续请求都带上它，现在这些都没了，每个请求自己带着全部信息，任何一个服务端实例都能接。官方在公告里说，新版本能在普通
HTTP 基础设施上水平扩展，不需要服务端维护连接状态。

方向相反的另一头是 OpenAI。从 2025 年 3 月随 GPT-5 推出 Responses API
起，OpenAI
就在持续往有状态走。新接口让服务端保留模型的推理过程和会话历史，开发者不用每次自己传完整上下文。2025
年 8 月 OpenAI 公告 Assistants API 将在 2026 年 8 月下线，引导大家迁到
Responses。2025 年 12 月 Codex 团队通知 custom provider 把接口迁移到
Responses 格式。官方博客里写”就像
Chat Completions 取代 Completions 一样，我们期望 Responses 成为开发者用
OpenAI 模型构建应用的主流方式”。

一个去状态，一个加状态，方向相反。

## MCP 一年半改了三次状态管理

MCP 在一年半内改了三次状态管理，每次都是被外部采用率推着走。

第一阶段是 2024 年 11 月 5 日。MCP 诞生时只支持
stdio，协议没有显式会话管理。客户端和服务器必须同机、单进程通信。实验室场景下这套设计没问题：一个研究员跑一次实验，开一个进程，用完关掉，状态不需要管理。今天MCP
官方规范页把这一版标为 Legacy。

第二阶段是 2025 年 3 月 18 日。MCP 引入 Streamable HTTP
支持远程部署。从单进程到多请求、可能命中不同实例，需要某种连续性。设计者选了最熟悉的方案：客户端先发个握手请求拿一个会话编号，后续请求都带上它。这跟
REST 革命之前 SOAP
时代的做法一样，单实例能跑，多实例水平扩展就出问题。

这一步的工程视野缺位最明显。stdio 时代的设计假设是单机单进程，HTTP
时代直接套了会话制这个最熟悉的远程连续性方案。它没有考虑过负载均衡后面的多实例怎么共享状态，也没有给网关留出不解包就能路由的余地。社区里有人当时就指出
client 和 server 必须同机的限制诡异，Anthropic 在 roadmap 里提到 2025
年可能改掉，但具体怎么改、改成什么、怎么迁移，很长时间没有答案。

到 2025 年 6 月 18 日稳定版，MCP 仍沿用会话制传输。社区开始部署远程
MCP server，会话设计撞上扩展性的墙。开发者 Sai
Nitesh Palamakula 在他的复现实验里记录了一个真实故障：两个 MCP
server 实例挂在轮询负载均衡后面，客户端发握手请求落到 A 实例，A
在内存里建会话返回编号。随后 SDK 的长连接请求被哈希到 B 实例，B
本地找不到会话返回 404，客户端挂死。运维要么开 sticky session
把同一个客户端绑死在单实例上，破坏水平扩展，要么引入 Redis
共享会话存储，增加链路复杂度和延迟。网关要智能路由还得深度解包请求体提取会话编号，拉高
CPU 消耗。

2026 年 7 月 28
日候选版本删掉握手和会话编号，把协议核心改回无状态。协议版本、客户端身份、能力描述这些信息改成塞进每个请求里，请求变得自包含，任何
server
实例都能处理。网关不用解包请求体就能路由，工具列表可以缓存，分布式追踪也能跨
SDK 串起来。这是六个提案一起改的结果，不是单点修补。

MCP 的状态管理从来不是长远规划的结果。stdio 时代不考虑远程，HTTP
时代惯性套用 session，水平扩展出问题才去状态。每一步都在补昨天的洞。

时间线：MCP 状态管理三段路。2024-11-05
stdio 隐式状态（进程即会话），2025-03-18 Streamable HTTP
引入显式会话编号，2025-06-18 沿用，2026-07-28 RC
删掉会话变无状态。每一步都是被采用率推着走。

图：MCP 状态管理一年半三段路。从左到右：stdio 隐式状态（进程即会话）→
Streamable HTTP 引入显式会话编号 → 稳定版沿用、社区撞扩展墙 → RC
删会话变无状态。每一步都是被采用率推着走。

## 状态藏在哪一层，决定了它好不好拆

MCP 这种被动演进和它的起源有直接关系。

MCP 最初是 Anthropic 的 AI
科学家在实验室里设计的。它的初衷是让研究员快速迭代 Agentic AI
实验。核心假设：所有信息交换都流经模型的上下文窗口，模型对工具调用和结果有完整可见性。这在语义层是无状态的，状态由模型通过上下文窗口管理，协议本身不记录历史。

但传输层加 HTTP
时状态被引进来了。服务器向客户端推送消息、中途请求用户输入这些操作需要持久连接。语义层无状态和传输层有状态的错位，就是后来生产部署所有麻烦的根源。

2026-07-28 候选版本修了这个错位：删掉会话编号，传输层改无状态，用显式
handle
解决连续性。工具返回一个购物车编号，模型下次调用把它当普通参数传回来。状态变成模型可见、可推理的标识符。这跟
HTTP API 用资源编号维持状态是同一个思路，REST 当年走的就是这条路。

这反而帮了 agent
推理。在会话设计里，状态藏在传输层元数据里，模型看不见。改成 handle
后，模型能跨工具组合、能在步骤间传递、能推理它。比如模型可以同时创建两个购物车，拿到两个编号，在推理中对比商品列表，或把商品从一个搬到另一个。这种跨工具编排在传输层会话设计里做不到。官方公告里说，这种把状态外显的做法不只是会话状态的替代品，在实际开发中往往更强大。

代价是工具作者要自己管 handle
的作用域、校验、过期。别让一个编号变成无限制的万能通行证。

## OpenAI 从无状态走向有状态

OpenAI 的 API 从第一天就是为生产设计的。它的演化走向了 MCP
的反面。

Chat Completions 是无状态的，客户端自己维护
history，每次请求把完整对话发给服务端。这个接口统治了整个 AI
行业。DeepSeek、Qwen、MiniMax、Moonshot、GLM、Gemini
OpenAI-compatible、OpenRouter，几乎所有 provider 都暴露 Chat Completions
入口。它成了事实标准。对开发者来说，无状态意味着切换成本极低，改个 model
ID 就行，provider 之间没有摩擦。

2025 年 3 月随 GPT-5 推出 Responses
API，可选有状态。默认行为还像以前一样无状态，但开发者可以选择让服务端保留推理过程，下一轮接着用，不用每次重传完整上下文。后来又加
Conversations API，把会话历史持久化也收进服务端。OpenAI
官方说法是推理过程跨轮保留在 benchmark 上有 +5% TAUBench
的提升，这是技术上真实的价值，不是纯营销。

但 Responses API 不只是加了推理状态持久化。它把 hosted tools
也收了进去：网页搜索、文件检索、代码执行、控制电脑、MCP 全部在 OpenAI
服务端执行，客户端不用自己跑。这意味着 agent 的核心循环从客户端迁到了
vendor 基础设施里。

OpenAI 在官方博客里写”就像
Chat Completions 取代 Completions 一样，我们期望 Responses 成为开发者用
OpenAI 模型构建应用的主流方式”。2025 年 8 月公告 Assistants API 将在
2026 年 8 月下线。2025 年 12 月 Codex 团队通知 custom provider
把接口迁移到 Responses 格式。

这不是技术退化，是平台战略。无状态下 API 是普通商品，Chat Completions
格式高度统一，开发者随时换底层模型。有状态筑起壁垒：推理状态存服务端，托管工具跑服务端，会话历史留服务端。用得越深，迁移代价越大。agent
平台的锁定逻辑在这里同样成立：system prompt、skill
配置、工具连接、harness
配置一旦在某个平台上建立，迁移的工作量远大于替换一个 API key。Responses
API 把这个锁定从配置层推进到了运行时状态层。

## 社区留在无状态那一边

OpenAI 全力推有状态 Responses，社区大面积留在无状态 Chat
Completions。

首先是性能退步。OpenAI
开发者论坛上有多个帖子贴出实测数据：Responses API 比 Chat
Completions 慢 2-3 倍，引用上一轮响应时延迟能到 10 秒以上，极端的到 2-10
分钟。OpenAI 工程师 Steve Coffey
自己出来建议关掉服务端存储来降延迟，等于退回无状态模式。

其次，token 经济性没兑现。社区实测发现引用上一轮响应时
input token 数量和 Chat Completions
几乎一样，服务端内部还是要跑完整历史。所谓”不用传完整上下文”只省了网络传输，没省推理成本。

第三，开源社区明确反对把 agent 循环收进 vendor 基础设施。Hugging Face
在 Open Responses
博客里直接写”Chat Completion format is still the de facto standard
despite the alternatives”，说 Responses 格式”is closed and not as widely
adopted”。评论区有人写”Agent loops are supposed to be implemented in the
agent system not in the LLM vendors system”，反对 vendor 把 agent
循环收进自己的系统。

左右对比：左边 OpenAI 从无状态 Chat
Completions 走向有状态 Responses
API（推理状态、会话历史、托管工具收进服务端），社区留在左边；右边 MCP
从隐式状态 stdio
走向显式会话再走向无状态，社区跟着走。两条路方向相反。

图：左右对比。左 OpenAI 从无状态 Chat Completions 走向有状态
Responses
API（推理状态、会话历史、托管工具收进服务端），社区留在无状态那一边；右
MCP 从隐式状态 stdio
走向显式会话再走向无状态，社区跟着走。两条路方向相反。

## 激励结构决定了协议方向

MCP 和 OpenAI 在状态管理上选了相反的路，背后是激励结构的差异。

OpenAI 是
vendor，有状态创造锁定，锁定支撑收租，收租维持模型研发投入。MCP 是 Linux
Foundation
下的开放标准，没有收租动机。它的目标是让协议活下来、能被互操作、能扛生产负载。无状态对生态好，有状态对
vendor 好。

这和当年 web 协议演进是同一类事。SOAP 是 vendor 主导的有状态协议，带
WS-Session、会话复制、粘性路由、网关深度解包，一旦要水平扩展每一条都变成运维成本和故障源。REST
是社区驱动的无状态反击，把状态外化成显式的资源路径，互联网应用的水平扩展才真正成立。REST
赢了。MCP 走的是同一条路，慢了十几年。

但两条路也暴露了两个阵营在工程视野上的差距。

MCP 的无状态不是一开始设计好的。stdio 时代不考虑远程，HTTP
时代套了会话制，水平扩展出问题才去状态。每一步补昨天的洞，不是在给明天打地基。

OpenAI 的有状态化是主动的平台战略。它从第一天就在想怎么把推理过程和
agent 循环收进自己的基础设施，并用废弃旧接口来推动标准更替。

一个被形势推着走，一个主动塑造形势。这不是技术品味差异，是组织定位差异：MCP
是科研遗产被动转工程，OpenAI 是商业驱动做平台锁定。