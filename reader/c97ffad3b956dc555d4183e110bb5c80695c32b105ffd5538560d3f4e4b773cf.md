---
layout: post.njk
source: https://yage.ai/share/ambient-agents-20260601.html
speaker: yage.ai
title: AI Agent 的下一个形态：从聊天窗口到后台守护进程
date: '2026-06-02'
summary: 本文探讨了AI Agent产品形态的系统性迁移，即从会话式的聊天窗口转变为后台常驻的守护进程（ambient agent）。以Google推出的Gemini Spark为例，分析了周期性任务与反应性任务自动化模式的差异，指出该转变在产品交互、使用频率和平台锁定逻辑上的深远影响，并提出了关于可靠性、信任机制及用户需求等亟待解决的问题。
area: tech-engineering
category: ai-application
tags:
  - ai-agent
  - ambient-agent
  - daemon-mode
  - automation
  - product-evolution
people:
  - Jay Peters
  - Christopher Meiklejohn
companies_orgs:
  - Google
  - The Verge
  - Anthropic
  - OpenAI
  - Apple
products_models:
  - Gemini Spark
  - ChatGPT
  - Claude.ai
  - Cursor Agent Mode
  - Claude Code
  - Codex
  - Devin
  - Manus
  - Caucus V1
  - Antigravity 2.0
media_books: []
draft: true
status: evergreen
---

2026 年 6 月 1 日，Google 向美国 Google AI Ultra 订阅用户推送了
Gemini Spark。按照 Google 的说法，这是一个”24/7 个人 AI
agent”，能持续监控用户设定的条件，跨 Gmail、Calendar、Drive
执行多步骤工作流。用户可以设定规则（“每周一早上把上周邮件摘要发给团队”），也可以临时下指令（“查一下我们今年的平均月度杂货开支，给我太太写封邮件”）。

The Verge 的 hands-on 评测抓住了这件事的矛盾感：Spark
在简单任务上表现得令人震惊。作者 Jay Peters 让 Spark 从他的 Drive
预算表中提取月度食品开支、计算平均值、找到他妻子的邮箱地址、起草邮件。Spark
全做对了，连他们夫妻之间的私人签名落款都用上了。Peters 的原话是”Wow,
that’s actually nuts.”但同一个 Spark
在面对更复杂的开放任务时就开始出问题：让它策划街区派对，它编造了一个不存在的共享报名表，生成了一份关于城市许可的丑陋幻灯片，邮件里提到的东西有些根本不存在。Peters
的结论是”impressive, but it’s not worth the cost just yet.”

评价 Spark 本身的好坏不是重点。Spark
是第一个由大型平台正式推出的、以后台常驻形态运作的 agent
产品，它的完成度不够好，但它的产品形态指向了一个更大的变化。把视野拉远一点，会看到一个更完整的图景：AI
agent 的产品形态正在经历系统性的迁移，Spark
只是这个迁移中最显眼的一个信号。

## 从聊天到守护进程：四代产品形态的迁移

要理解这次迁移，得先看清楚我们是从哪里走过来的。

第一代是聊天窗口。ChatGPT、Claude.ai、Gemini，打开一个页面或
app，输入一句话，AI
回一句话。会话结束，状态归零。这一代的核心限制不在模型不够聪明，而在模型没有记忆也没有手脚。它只能在对话的边界内回答问题，对话之外的世界跟它无关。

第二代是 agentic 工具。Cursor Agent Mode、Claude Code、Codex、Devin
这些产品给 AI
装上了手脚：读写文件、执行命令、跑测试、看结果、根据结果调整。它们仍然在对话窗口里运行，但对话本身变成了一个迭代循环：AI
执行一步，看到反馈，决定下一步。这一代的突破在于把”观测、执行、纠错”的闭环装进了产品里。我们在
Agentic AI
危机里分析过这一代的核心矛盾：当 AI
能执行但不能感知结果时，它的自我迭代就断了。

第三代是后台 agent。从 2025 年底开始，编程工具开始把 agent
从对话窗口里解放出来。Cursor
Background Agents（2025 年 10 月）可以在云端独立工作，最多 8
个并行，每个跑在隔离的 git worktree 里。OpenAI Codex
Automations（2026 年 2 月）支持 cron 定时调度，结果进 Triage
inbox。Anthropic
Claude Code Routines（2026 年 4 月）支持定时、API webhook 和 GitHub
event 三种触发方式，跑在云端不需要本地开机。这一代的核心变化是：agent
不再需要你发起对话才会工作。它们像 cron job
一样，在后台按时间表或事件触发执行。

但它们仍然是开发者工具。受众是写代码的人，场景是代码仓库。

第四代是 Spark 代表的 consumer ambient
agent。它把第三代的”守护进程”模式从开发者工具搬到了消费者产品上。Spark
不是 Gemini 聊天窗口的增强版，它是另一个产品品类。它跑在 Google
Cloud 的专用 VM
上，你关掉笔记本、锁上手机，它继续工作。它不依赖你主动发起对话；它监控你设定的条件，或者接收你的指令，然后自己去完成。

这不是”Gemini 变强了”的故事。产品形态翻了一页。

要更具体地理解这个翻页的意思，可以看一个对照物：Manus。Manus
同样跑在云端，同样能跨应用执行多步骤任务，同样在你关上电脑之后继续工作。从基础设施角度看，Manus
和 Spark 做的事差不多。但它们的交互模式不同。Manus 仍然是
session-based：你打开它，给它一个任务，它去执行，执行完了把结果交给你，会话结束。你不打开
Manus，它什么也不做。它不知道你收到了什么邮件，也不会在某个条件满足时主动跳出来通知你。Spark
是
daemon：你设定好规则或触发条件之后，不需要再打开它。它在后台持续运行，监控你的邮箱、日历、Drive，在你设定的条件满足时自动行动，在你没有设定条件但出现了它认为你该知道的事时也可以主动汇报。用一句话概括：Manus
替你干活，但需要你告诉它什么时候该干活。Spark
替你盯着，不需要你告诉它去看，你只需要告诉它该盯什么。

这个差异在工程上很轻，本质上只是加了一个调度层和一个事件监听层。但在产品体验上很重，它把
agent 从”工具”变成了”环境”。这也是为什么 Digital Applied 在分析中把
Spark 称为”the first ambient personal agent from a Big Three lab”。

## Periodic vs
Reactive：两种后台自动化模式

退一步看，这些产品在做的事情可以分成两类。

第一类是周期性任务。你设定一个时间表，agent 按时执行。Claude Code
Routines 每天凌晨跑一遍代码审查、Codex Automations 每小时检查一次 test
coverage、Spark
每周一早上把上周的邮件摘要发给团队。这类任务的可靠性要求相对可预期：如果一次没跑对，下次修正就行；如果结果有问题，你可以在下一次执行之前介入。

第二类是反应性任务。某个事件触发了 agent 的动作。GitHub 上有人提了
PR，Claude Code Routine 自动检查代码风格；Betterment
给你发了封邮件说需要 opt out 仲裁条款，agent
读到了这封邮件，自动写了回复草稿；Slack 上有人 @ 了你提到一个 bug，agent
自动去查了相关代码并开了
issue。这类任务的即时性更高，但出错后果也更直接。一封自动发送的错误邮件，比一份没跑对的周报严重得多。

这两类模式不是互斥的。现实中大部分有用的自动化是两者的组合：事件触发后，agent
执行一个多步骤工作流，其中某些步骤会进入周期性监控状态（比如发完 PR 后每
30 分钟检查一次 CI 状态）。Christopher
Meiklejohn 在 Caucus V1 里把这个循环做到了一个具体的实现：agent
实现代码、开 PR、另一个 agent review、如果 review
要求修改就回到实现环节继续。他用一个小的 vector clock
原语来追踪每个环节的执行次数，确保 agent 知道自己在循环里的位置。

这两种模式各自有不同的信任门槛。周期性任务因为你可以在两次执行之间人工审查，容错空间更大。反应性任务的信任门槛更高。你本质上是在授权
agent 在事件发生时独立判断并行动，中间没有审查窗口。

这也是为什么 Google 在 Spark 的安全设计上格外保守：默认所有 Workspace
连接关闭，花钱和发邮件前必须先确认，分 trusted testers、US-only
Ultra-gated beta 逐步放开。Digital Applied
的分析用了一个准确的框架来理解这种策略：控制 blast radius。ambient agent
出错的影响范围远比 session-based agent
大，因为它在你没有监督的情况下工作。

## 为什么这件事比看起来大

第一轮反应通常聚焦在”谁先出了这个功能”上。但”先”本身不太重要。Cursor
的后台 agent 比 Spark
早了八个月，但没人把它当作行业转折点，因为它面向的是一个窄得多的用户群。

真正重要的是产品形态的迁移在三个层面上改变了竞争规则。

第一，使用频率变了。聊天窗口的使用频率上限是你想起去问的次数。后台守护进程的下限是你忘记关掉它的次数。两者的使用量不在一个数量级上。这意味着”好用”的标准也不同：聊天窗口的容错空间大，一次回答不对可以追问；守护进程的容错空间小，因为你不会盯着它。The
Verge 评测里 Peters 写的”I found myself constantly watching it or
checking the notifications it sent to my
phone”就是这个矛盾的精确表达。如果后台 agent
的可靠性让你不得不回到”盯着看”的模式，它就没有真正兑现守护进程的价值。

第二，平台锁定逻辑变了。聊天窗口的产品，切换成本是导出对话记录。守护进程的产品，切换成本是重建所有跨应用的工作流、规则、触发条件和长期积累的个人上下文。Google
在这件事上有一个不对称的优势：它拥有 Workspace
生态（Gmail、Calendar、Drive、Docs），Spark
可以直接读写这些服务，不需要通过第三方 API 桥接。Anthropic 和 OpenAI
没有同等深度的消费者生产力套件，它们的主要优势在开发者工具这一侧。Apple
走的是另一条路，on-device
加隐私优先，但这条路的前提是你能接受功能范围的限制。

第三，这个形态在解决 agent 一直以来的一个根本问题：context window
的时效性。聊天窗口里的 agent，context
是静态的快照，是你打开对话时喂给它的信息。守护进程里的 agent 的 context
持续更新，它在后台不断接触新的邮件、新的事件、新的文件。这让 agent
从”回答你这一刻想知道的事”变成了”帮你盯着你一直需要盯着的事”。

## 未解决的问题

可靠性是最明显的。但可靠性不只是模型能力的问题，它是系统设计的问题。Meiklejohn
在 Caucus V1 文章里有一句话把这个判断讲得很清楚：“If the models are
inconsistent, the surrounding system has to get stronger.”agent
的执行环境需要有隔离边界、失败恢复、状态追踪、可观测性。这些是基础设施层的问题，不是模型层的问题。

信任是第二个。一个会话级的 chatbot
的信任模型是”每次对话时我自己判断要不要信它”。一个常驻后台的 agent
的信任模型是”我授权它在我不知道的时候做判断”。前者是点状的、可审查的；后者是持续的、审计成本很高。Google
的分阶段推出策略，是从 trusted testers 到 Ultra-only beta 再到未来的 Pro
用户和国际市场的渐进铺开，本质上是一个逐步扩大信任半径的实验。

第三个问题更根本：用户真的需要一个 24/7 的 agent 吗？目前 Spark
展示的使用场景，查开支、写邮件、整理信息，大部分在传统的聊天窗口里也能完成，只是多花一些时间。只有当
agent
能处理在你睡觉时发生的事情，比如半夜收到的紧急邮件、跨时区团队的沟通、持续监控某个外部条件的变化，它才真正提供了聊天窗口无法替代的价值。这个价值主张目前还停留在
demo 层面，没有被大规模使用数据验证。

## 接下来看什么

有几个信号会决定这个方向的实际走向。

Antigravity 2.0 SDK 的采用率。Google 在 I/O 同一天发布了 Antigravity
2.0，它是 Spark 底层执行栈（VM execution + MCP tool
surface）的开发者版本。如果第三方开发者开始在 Google 的 harness 上构建
ambient agent，这意味着 Google
在做的不只是推出一个产品，而是定义了一类新软件的运行栈。这个模式可以参考
Firebase/Android 的历史。

编程 agent 和消费者 agent 会不会收敛。Claude Code 有 Routines，Codex
有 Automations，Cursor 有 Background
Agents，这些都是编程场景下的守护进程。Google 用 Spark
把同一套逻辑搬到了消费者场景。如果这两条线最终合并（比如 Claude Code 的
Routines 开始支持读写 Gmail 和 Calendar），那”编程 agent”和”消费者
agent”的品类边界就会消失，只剩下”你的 agent
能访问哪些系统”这一个维度。

信任机制的标准化。目前每个平台都在自己定义 agent
的权限模型和数据边界。随着 agent 跨平台操作的场景增多（Spark 已经在通过
MCP 接入
Canva、OpenTable、Instacart），没有一个通用的 agent
权限标准会越来越成为瓶颈。Agent2Agent 协议和 MCP
在这一层上有互补性，但它们解决的是 agent 之间的通信问题，不是 agent
和用户之间的信任契约问题。

Gemini Spark 的”第一”不重要。重要的是它把一个问题从”AI
能不能在后台干活”变成了”在后台干活的 AI
需要什么样的产品形态、信任框架和执行环境”。所有主要平台都在回答这个问题，只是各自的起点不同。Google
从 Workspace 起手，Anthropic 从代码仓库起手，OpenAI
从开发工具起手，Apple
从设备隐私起手。它们的终点可能在同一个地方：一个你不必主动打开、但知道你什么时候需要它的
agent。