---
layout: post.njk
source: https://yage.ai/share/agent-first-class-citizen-20260618.html
speaker: yage.ai
title: |-
  当 CEO 把 agent-friendly 写进 KPI：钉钉、Salesforce
  和一条从 Unix 开始的工程线
date: '2026-06-19'
summary: 文章探讨了企业如何将‘agent-friendly’理念融入KPI，并分析了从Unix哲学到API-first再到Agent-first的工程演进路径。核心观点是真正的沉淀不在于‘agent’这个词本身，而在于构建一套以function-calling为优先的基础设施，即让软件能力能够被结构化发现、语义化调用和安全执行。
area: tech-engineering
category: ai-application
tags:
  - agent-friendly
  - function-calling-first
  - api-first
  - unix-philosophy
people:
  - 陈宇森
  - 邓悟
  - 陈航
companies_orgs:
  - 钉钉
  - Salesforce
  - ServiceNow
  - Snowflake
products_models:
  - Headless 360
  - Action Fabric
  - AISQL
media_books: []
draft: true
status: evergreen
---

2026 年 6 月 18 日，晚点 LatePost
拿到了一封钉钉的内部全员信。发信人是 CEO
陈宇森。信里大部分内容是组织调整，但末尾有一条指令很容易被扫过去：“成立公司信息技术部，负责优化迭代公司各业务系统，让一切系统易于被
Agent 使用，邓悟负责，向我汇报。”

让一切系统易于被 Agent 使用。这句话被直接写进了一个向 CEO 汇报的部门
KPI。第一财经、界面新闻、IT之家、凤凰网、36氪 和晚点先后交叉验证了原文。它来自内部信而不是公关稿，没有市场话术的缓冲层。国内
ToB 厂商里，把 agent-friendly 写成有汇报线的部门职责，这是头一回。

就在不到一个月前，Salesforce 在 TDX 开发者大会上发布了 Headless
360。执行副总裁 Jayesh Govindarjan 的原话和陈航如出一辙：“不是把功能藏在
UI 后头，而是把它们暴露出来，让整个平台从任何地方都能被编程”（凤凰网报道）。Salesforce
把平台上每一项能力拆成了 API 端点、MCP 工具或者 CLI
命令，超过一百个新工具。外部编码 agent 第一次拿到了对 Salesforce
完整环境的实时访问权。

ServiceNow 和 Snowflake
也在做同一个方向的改造，路线各有侧重。ServiceNow 今年 5 月全量上线了 Action
Fabric，把自家的 Skills、Workflow、Knowledge Graph 重组成 MCP
工具，宣布”向每一个 AI agent 开放，无论它是建在 ServiceNow 上的，还是用
Claude、Copilot 或客户自建的 agent”（ServiceNow
新闻稿）。Snowflake 更早一些，去年 6 月就把 AI 做成了 SQL
原生算子：AISQL
里的 AI_COMPLETE 和 FILTER、AGGREGATE 同级。

四家公司没有商量过路线图。它们在做同一件事：把软件从 GUI 优先变成
agent 能直接消费的格式。Postman 2025 年 11 月发布的 State
of the API 2025 报告甩出了一个对照数字：89% 的开发者日常在用生成式
AI，但只有 24% 在设计 API 时想过 agent 这个消费者。中间那个 65
个百分点的窟窿，对应的是海量企业软件：功能都在，接口不是给 agent
留的。那头 89%，这头 24%。

## 工程底座是陈航铺的，陈宇森把它写成
KPI

陈宇森这封信做了一件具体的事：把前人在工程上已经铺好的路，写成了组织层面的制度。真正干活铺路的人是陈航。

陈航 2025 年 4
月回归钉钉，启动了一个为期一年的底层重构。他把钉钉的全部企业级能力（IM、音视频、文档、审批、日程、差旅）一条一条重写成
AI 能调用的命令行指令，总数上万条。2026 年 3 月 17 日 AI 钉钉 2.0
发布会上，陈航自己是这样说的：“今天钉钉提供的所有页面，现在全部幻化成能力，以命令行方式压缩，提供给
AI 操作”（品玩报道）。他补了一句，说这套东西是在建一套类似
Unix 内核的控制体系。

围绕这套 CLI，陈航的团队还搭了 Realdoc 真经文件系统（专门为 AI
高频读写和频繁回滚设计的）和一套企业级安全体系。2026 年 3
月底，钉钉和飞书在不到 24 小时内先后在 GitHub 开源了各自的命令行工具（凤凰网报道）。钉钉的
CLI 不是只给自家悟空 agent 用的内部管道，任何能调命令行的 agent
都能用。

陈宇森新成立的”公司信息技术部”，定位是内部 infra
团队，改的是钉钉和悟空自己的
ERP、HR、财务、审批系统，目标就一个：让这些系统能被 agent
调得动。部门负责人邓悟直接向 CEO
汇报。这件事不再靠工程团队自发去推了，CEO
签了字，定了部门，划了汇报线。

## 这条线的根，在 Unix
哲学和 API-first 那里

这些事看着像新闻，根扎得比新闻深得多。

Unix 哲学最早开始做这件事：everything is a file，programs do one
thing，pipe &
compose。这套设计让人能写命令行加脚本，把一段工作委托给机器批处理，不用每次手动操作。人把工作
delegate 给机器的最早工程实践就是这里开始的。陈航说建一套类似 Unix
内核的控制体系，不是比喻，他真的在把 Unix
哲学往企业协作软件里重新做一遍。

Unix 之后，这条线的下一个关键节点是 Roy Fielding。2000 年他在博士论文里提出了
REST，核心是两个概念：uniform interface 和
HATEOAS。接口应该自描述，支持运行时发现，调用方不依赖外部知识。HATEOAS
在实践中几乎没人完整实现过（开发者总是把端点路径硬写在代码里），但它的思想被
MCP 完整地继承了下来：progressive disclosure，self-describing tool
registry，agent 在运行时自己探索有哪些工具可以用。

到了 2010 年前后，Kin Lane 以 API Evangelist 的身份推 API-first
设计。他的主张是：接口应该优先为机器消费者设计，UI 往后排。Twilio 和
Stripe
是最早把这条路走通的商业公司：它们的客户不是终端用户，是写代码的开发者。开发者通过
API 把通信和支付委托给 Twilio 和 Stripe 的机器。

API-first 和今天的 agent-first 有两处关键差别。API-first
假设消费者是另一个开发者写的确定性代码，agent-first 假设消费者是 LLM
自主调用的、非确定性的工具使用者。API-first 关心 contract 和
schema，agent-first 除了这些还要想 intent-revealing 怎么命名、recovery
hints 怎么写、幂等性怎么保证。原因是 agent
旁边没有一个人类开发者帮它处理 edge case。2010 年代的 headless CMS
把这套思路推到了内容层：能力独立于呈现层存在，什么消费者都能调。

2023 年，两个节点把这条线拽进了 LLM 时代。OpenAI 在 6 月 13 日发布了
function
calling，LLM 第一次能输出结构化的函数调用。9 月 28 日，Andrej
Karpathy 发了一条 tweet：LLM
不是聊天机器人，是新型操作系统的 kernel，agents 是进程，tools 是 system
calls。他说的其实是一件事：agent 是运行在 LLM 之上的委托层，人委托给
agent，agent 调用 tool，tool 是被暴露出来的能力。

2024 到 2025 年，协议层连续出了三个东西。Anthropic 在 2024 年 11
月发布了 MCP，解决
agent 跟 tool 怎么通信。Google 在 2025 年 4 月发布了 A2A，解决
agent 跟 agent 怎么通信。Anthropic 在 2025 年 10 月发布了 Agent
Skills，解决 agent 跟 procedural knowledge
怎么通信。这三个摞在一起就是一个协议栈：MCP 纵向，A2A 横向，Skills
语义层。2025 年 12 月，MCP 被捐给了 Linux
Foundation 下面的 Agentic AI
Foundation。OpenAI、Google、Microsoft、AWS、Block 全是创始成员。

## 但这件事真要做下去，阻力一层叠一层

就先说定义。Simon Willison
一直到 2025 年 9 月 18 日才松口，说 agent
这个词在工程圈有了”勉强可用的共识定义”，然后立刻补了一句：企业圈到现在没共识。一个连定义都没对齐的词，已经被用来定组织架构和汇报线了。

再说钱。Goldman Sachs 半导体首席分析师 Jim Covello 在 2026 年 5 月 26
日的公开访谈里说：企业今天在
AI 整合上亏的钱比两年前还多，数据根本还没准备好被
agented。投入在加，产出没见着。

目前最大规模的 agent 整合实验是 Microsoft 365 Copilot。Gartner
2025 年的调查数据是：40% 的企业在试点，只有 5%
从试点走到了扩大部署。卡在哪？Gartner 起了一个词叫 oversharing：agent
能读的东西比人多，数据安全的边界还没划清楚。Salesforce Agentforce
那边也不轻松，18 个月内换了三种定价模式，头两个季度
5000 笔交易里只有 3000 笔是付费的。

还有一个更难看的。开放这两个字，发布会上和实际条款里写的不是一回事。

SAP 在 TechEd 2025 上铺天盖地宣传 MCP 开放，但同期，2026 年 4
月，更新的 API
Policy v4 在 Section 2.2.2 里写了什么？禁止第三方 agent 直接调 SAP
API。只放行自家的 Joule、MCP gateway 和 BTP。Techzine
的报道副标题没给面子，直接写：“SAP blocks external AI agents.
Salesforce and ServiceNow don’t.”

Slack 走的是另一条路。2025 年 10 月生效的 API ToS
写了什么？禁止第三方索引、复制、长期存储 Slack 消息。这条一出来，Glean
这类企业搜索平台直接挨了一刀，有客户管这事叫 crisis
of trust。台上讲开放，合同里把门关上。

最后还有一层更难绕过去的矛盾。Gartner 的 oversharing
警告背后藏着一个死结：你让 agent 容易访问，就是让所有 agent
都容易访问，包括不该来访问的那一批。2025 年年中，Supabase 的 Cursor
agent 出了一次 Lethal
Trifecta 事故：service-role 特权、untrusted
input、对外通信，三件事撞在一起，数据泄露。MCPTox
benchmark 扫了一遍 MCP 生态，结果显示 tool poisoning
已经相当普遍。这不是某个供应商修几个 bug 能解决的事。agent
能读什么、能改什么，每多一项能力，都要重新想一遍谁能调用、怎么审计。

## 真正在沉淀的，是
function-calling-first infrastructure

把上面这些问题叠在一起看，这场运动的核心不在 agent 这个词。在
function-calling-first infrastructure。

Postman”下一个消费者既有可能是人也有可能是
agent”这个判断的方向是对的。但 agent 这个词带的歧义太多了。Willison
追了两年半才勉强承认工程圈有一点共识，企业圈到现在没有。Covello
的数据显示企业在 agent 整合上还在亏钱。继续把整件事绑在 agent
这个词上，讨论很容易拐进定义之争里出不来。

换一个说法更准：agent
只是消费端的一个实例，真正在沉淀的是一套让软件能力可以被结构化发现、语义化调用、安全化执行的基础设施。这条
infrastructure 包含的东西已经很具体了：protocol 层有 MCP、A2A、Agent
Skills；API 设计规范里有 intent-revealing 端点、结构化的 recovery
hints、幂等性保证；知识组织上有 progressive disclosure 和
filesystem-based skills；访问治理上有 lethal trifecta 约束和 oversharing
边界。这些才是已经在沉淀的工程资产。agent as first-class citizen
这个词好记、好传播，但工程上真正在动的，是 function-calling-first
infrastructure。

Postman 那 65 个百分点的落差，对上去的正是 CLI、MCP、structured
schemas、访问治理这些现在就能动手做的工程部件。喊一句 agent
时代来了，填不上这个窟窿。

## 工程收敛的方向比标准更早露面

我自己每天在用的 context
infrastructure（完整实现开源在这里），放到这条线里看，干的也是同一件事：把环境、知识、工具做成
agent 能直接消费的接口。SOUL.md、USER.md、WORKSPACE.md、AGENTS.md 这些
markdown 文件，做的事情就是在文件系统层面手工搭一套 agent
运行需要的信息架构。这个方向跟 Snowflake 把 AI 做成 SQL
原生算子、ServiceNow 把 Skills 重组成 MCP 工具、陈航把钉钉全量能力 CLI
化，是一致的。

Progressive disclosure 加 filesystem-based skill 这个组合，Anthropic
在 2025 年 10 月用 Agent Skills
做了标准化发布，但在这之前，它早就零零散散出现在各个独立的 agent
工程实践里了。我自己写过一篇讲先写 skill
再执行的文章，说的就是同一件事：把工作知识外化成 markdown
文件，agent 才有可复用的东西可调。MCP 出来之前，各种 tool-use
协议在不同项目里各自跑着。REST 出来之前，各种 RPC
方案在不同公司里各自演化。标准追上的时候，工程实践已经走了一阵了。

Unix 开始的这条路，现在还在往前推。agent as first-class citizen
是不是最终形态不好说，但 function-calling-first infrastructure
这个方向，已经不太可能退回去了。那些在 GUI
下面藏了几十年的企业能力，正在一块一块被拆出来。不是因为谁写了
KPI，是因为不用 agent 的时候它们还能藏。Postman 那 65
个百分点的落差一天不消，这些能力就会被继续往外拆。