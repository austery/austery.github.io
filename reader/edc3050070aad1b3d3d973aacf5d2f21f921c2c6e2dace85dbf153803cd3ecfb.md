---
layout: post.njk
source: https://yage.ai/share/pi-coding-agent-locked-out-20260518.html
speaker: yage.ai
title: Pi：一个更好的 AI 编程工具，被挡在了门外
date: '2026-05-18'
summary: Mario Zechner开发的极简AI编程代理Pi，摒弃复杂机制，强调透明度与可观测性。尽管其性能优异，但受限于模型厂商的生态锁定与订阅政策，其商业普及面临挑战，凸显了技术方案与商业策略的矛盾。
area: tech-engineering
category: ai-application
tags:
  - ai-agent
  - coding-tool
  - minimalist-design
  - ecosystem-lock-in
  - software-engineering
people:
  - Mario Zechner
  - Armin Ronacher
companies_orgs:
  - Anthropic
products_models:
  - Pi
  - Claude Code
  - Cline
media_books: []
draft: true
status: evergreen
---

2025 年 4 月，Mario Zechner 开始用 Claude
Code。那时候它还很基础——一个终端里的
Claude，能读文件、跑命令、改代码。Mario 喜欢这种简单：四五个工具，system
prompt 不过几千 token，行为稳定可预测。

到了 2025 年下半年，情况变了。Claude Code 每个 release 都在改 system
prompt 和工具定义，Mario
习惯的工作流反复被破坏。功能膨胀到他自己估计”80% 我用不上”。Sub-agents
作为黑盒 spawn 出来，你看不到里面发生了什么。Terminal UI
开始闪烁。他写了一个 cchistory
网站来追踪这些变化，越追踪越沮丧。

2025 年 11 月底，Mario 发布了一篇博客和一套代码——Pi，一个他自己用的 AI
编程 agent。system prompt 不到 1000 token，四个工具。博客标题：“What I
learned building an opinionated and minimal coding agent.”

## 缺什么比有什么更重要

Pi 的设计哲学可以从它的 “NO 列表” 来理解。Mario
在博客里逐一列出了他拒绝加入的功能和每条的理由。

No MCP。 Playwright MCP server 有 21 个工具定义，占
13,700 token——还没开始干活就用掉了 7% 的 context window。Mario
的替代方案是用 CLI 工具加 README 文件：agent 需要某个能力的时候自己读
README，用 bash 调用工具。只在需要时占用 token，不是每次 session
都背上全量工具定义。

No sub-agents。 Claude Code 的 orchestrator spawn
sub-agent 去做复杂的子任务，用户看不到 sub-agent
读了什么、做了什么、在哪里犯了错。Mario 的说法是黑盒套黑盒。Pi
的替代方案是用 bash 启动一个新的 Pi instance，需要时可以放进 tmux 做
full observability——你能看到 sub-agent
的完整交互过程，可以在中间介入。

No plan mode。 不需要一个专门的”只读分析模式”。Agent
可以跟你一起想问题，把计划写在 PLAN.md
里。你能看到它读了哪些文件、忽略了哪些——这在 Claude Code 的 plan mode
里做不到，因为 orchestrator spawn sub-agent 之后你就失去了可见性。

No built-in to-dos。 内置待办列表会让模型困惑。Pi
的做法是写一个 TODO.md 文件，用 checkbox 标记状态。状态对人和 agent
同时可见、可编辑。

No permission popups。 Mario 认为编程 agent
的权限弹窗是安全剧场。只要 agent 能读数据、执行代码、访问网络，game
over。与其假装控制，不如接受 YOLO 模式，或者在容器里跑。

No background bash。 用 tmux 做后台进程管理。tmux
让你能看到 agent 跑 dev server 的完整输出，可以列出所有活跃
session，可以中途进入 co-debug。Claude Code 的后台 bash
功能在早期版本里，agent 在 context compaction
之后会忘记自己在跑什么、也没有工具去查询——Mario 觉得这不如直接用 tmux
干净。

No compaction。 这是争议最大的一项。Mario
说他个人没遇到需要 compaction 的场景，几百轮对话能轻松塞进一个
session。但其他用户——包括 Pi 最忠实的推广者 Armin Ronacher——在长 session
里确实遇到了需要压缩 context 的情况。

## 不止是”做得少”

如果 Pi 只是一个刻意精简的 Claude Code 替代品，它不会引起 Armin
Ronacher 和 Nader Dabit 这些人的注意。Pi 有三层设计是其他 harness
没有的。

第一是 session trees。Pi 的 session
可以分支、可以回退、可以在分支间跳转。假设 agent 在修一个 bug
的过程中把一个工具搞坏了，你可以 fork 到新分支修好工具，回到主分支，Pi
自动把侧分支上的修改总结出来。这个机制让 agent
的试错成本大大降低——你不需要担心 agent 在探索过程中把 context
污染掉。

第二是 extensions 系统。Pi 的 extension 是
TypeScript 代码，hot-reload，agent 可以读写修改自己的
extensions。没有插件市场——你告诉 agent
你想要什么功能，它自己写代码实现。Armin 的几个常用 extension 全是 agent
写的：/answer（提取 agent
回复里的问题重新排版）、/todos（管理 .pi/todos
下的 markdown 文件）、/review（fork 到新分支做 code review
然后带回主分支）、/files（列出 session
里改过的文件）。Mario 维护了一个 agent-tools
仓库，里面是各种 CLI 工具，每个带 README 让 agent 按需读取——web
search、图片生成、YouTube 搜索、arXiv
论文检索。就是普通的命令行脚本，没有 MCP server。

第三是 RPC mode。Pi 可以作为一个 subprocess
嵌入更大的自动化系统。你的编排层发任务，Pi
执行编码工作，返回结构化结果。Nader Dabit 的指南从 pi-ai 的裸 API
开始，一层层加到 pi-agent-core 的 agent loop、pi-coding-agent 的 session
management、pi-tui 的终端界面——演示了怎么用 Pi 的 stack 从零构建一个
production-grade agent。OpenClaw 就是这么建的。

## 用起来是什么感觉

Armin Ronacher 在 2026 年 1 月底写了他切换到 Pi
的体验。不闪烁，不吃内存，不会随机崩溃。在 VS Code
内置终端里有轻微闪烁，但比 Claude Code 好——Armin 说他已经习惯了 Claude
Code 的闪烁，“没有反而觉得不自在”。

更实质的差异在透明性。Armin 对比了 Claude Code 的 plan mode 和 Pi
的做法：Claude Code spawn sub-agent
去做分析，你看到的是结果但看不到过程——不知道 agent
读了哪些源文件、忽略了哪些。Pi 里你看到 agent 的每一次 read、每一次
bash、每一次 edit。计划写在文件里，你可以和 agent 一起编辑。Armin
的原话是：“I need observability for planning and I don’t get that with
Claude Code’s plan mode.”

Paweł Józefiak 在 2026 年 4 月做了一次六个 harness 的横评。他对
Pi 的评价是整篇文章里最个人化的：“I love Pi, but I can’t use it.”
喜欢它的速度快、灵活、干净——但用不了。原因不是 Pi 本身。

Terminal-Bench 2.0 的数据也能说明问题。Cline 团队在 2026 年 5 月跑了
Pi-Code、OpenCode 和 Cline 在四种 open-weight 模型上的对比：

模型

Cline

Pi-Code

OpenCode

kimi-k2.6

55.1%

45.5%

37.1%

deepseek-v4-pro

53.9%

52.9%

51.7%

glm-5.1

49.4%

51.7%

52.8%

minimax-m2.7

42.9%

46.0%

39.3%

Pi 在两个模型上超过了 Cline（glm-5.1 和 minimax-m2.7），在
deepseek-v4-pro 上落后 1 个百分点。整体来看，Pi 在 open-weight
模型上的表现不输任何竞品。

## Pi 孵化了什么

Pi 不是一个孤立的 coding agent。它的 stack 成了一层基础设施。

OpenClaw 是 Peter Steinberger 做的多渠道 AI
agent。用户通过 Telegram、WhatsApp、Slack 等通信工具发消息，OpenClaw
在后台执行。2026 年 1 月底 viral 爆发时，Armin 写的那篇博客标题就是 “Pi:
The Minimal Agent Within OpenClaw”——OpenClaw 的 agent 引擎就是 Pi。

mom 是 Mario 自己用 Pi 的 stack 写的 Slack
bot。per-channel agent 隔离、Docker sandbox、定时任务。Mario 说 Pi
指向自己的代码库和 mom 的配置，就能让 agent 自己搭一个新的出来。

Extensions ecosystem 在 Armin 和 Nico
等人的推动下快速演化。Nico 写了 pi-subagents，用
Pi 的 extension API 给 Pi 加了 sub-agent 能力——Mario
拒绝不代表别人不能加。有人写了 pi-interactive-shell
让 Pi 在可观测的 TUI overlay 里跑交互式 CLI。有人写了
pi-agentic-compaction，用虚拟文件系统做 compaction，弥补了 Pi 缺少自动
compaction 的缺口。Tao of Mac 网站开始追踪 Pi
生态里的项目：Graphone 桌面客户端、pi-queue 任务队列、pi-token-burden
token 统计、pi-generative-ui 生成式界面、Mercury 个人 AI
助手。还有人把整个 Pi 代码库 fork 成了独立项目 earendil-works/pi，到
2026 年 5 月已经有 4,176 个 commit。

这些项目的共同模式是：用 Pi 的 primitives（pi-ai 的 LLM
抽象、pi-agent-core 的 agent loop、pi-coding-agent 的 session
management）作为底座，在上面搭自己的应用。Pi 的核心仓库只有 Mario
一个人在维护——他明确说了自己是 dictatorial maintainer——但基于 Pi
构建的东西已经远远超出了一个人的范围。

## 那为什么用的人不多

Benchmark 上看不出差距。Terminal-Bench 上 Pi 对 Cline 和 OpenCode
互有胜负，说明四个工具和不到 1000 token 的 system prompt
在性能上没有吃亏。四个工具覆盖了编码所需的基本操作，extensions 系统允许
agent 在需要时补上缺失的功能。Session trees、RPC mode、跨 provider
切换——这些能力在其他 harness 上要么没有，要么做得不如 Pi 自然。

但实际 adoption 不高。Paweł Józefiak 的 “I love Pi, but I can’t use
it” 代表了最核心的障碍。

Pi 是 BYOM——你用自己的 API key。Claude 用户如果想用 Pi，需要在已有的
Max 订阅（$100-200/月）之外额外付 API 费。Anthropic 不允许 Max
subscription credits 在第三方 harness 上使用——你付给 Anthropic
的订阅费只能在 Claude Code 里消耗。Paweł 在测试 Pi 时收到了 Pi
的明确提示：通过 Pi 调用 Claude 的流量走 API billing，不算在 Max
订阅里。

这等于让 Claude 用户为同一个模型付两次钱。Anthropic 的 API
定价本来就不便宜——Opus 每百万 token 输出 $25，长 coding session 的 token
消耗轻松上万。再加上已经付过的 $100-200 月费，经济账完全算不过来。

Google 的策略一样。Gemini CLI 免费但锁定自家 harness，订阅 credits
不能用在第三方工具上。对比 OpenAI：API credits 可以在任何兼容的第三方
harness 上自由使用。你用 Pi 调 GPT-5，只付 API
费，不需要额外订阅。同一笔钱在 Anthropic 生态里只能花在 Claude Code
上，在 OpenAI 生态里可以花在任何兼容工具上——这个差异直接决定了一个独立
harness 在哪个模型生态里有存活的可能性。

这不是 Pi 的问题。Pi 在 GPT 和 open-weight
模型上成本模型清晰——付你用的模型 API 费就行。但 AI
编程工具的用户群体里，Claude 用户占比很大。等于 Pi 最好的潜在用户群被
Anthropic 的订阅策略挡在了门外。

## 然后呢

Pi 证明了几件事。四个工具加不到 1000 token 的 system prompt
能做出一个有效的 coding agent——而且 benchmark 数据和社区反馈都不差。让
agent 自己写代码扩展自己能运转起来——extensions 系统不是噱头，Armin
的日常使用证明了这一点。保持核心最小、用 primitives
做底座的思路是对的——OpenClaw、mom、以及社区里十几个基于 Pi
的项目都是证据。

Pi 没证明的是：一个独立 harness
能否在与模型公司的生态锁定中生存。技术可行性从来不是问题，商业策略才是决定因素。Mario
不在乎——他做 Pi 是为了自己用，用户多少无所谓。但如果 Pi
的设计哲学是对的——如果好的 agent runtime 不需要上万 token 的 system
prompt 和三十个工具——那这个哲学需要一种方式去触达它最适合的用户群。

现在的方式是绕路。用 GPT 或 DeepSeek 的人可以直接用
Pi，成本清晰。Claude 用户要么接受付两次钱，要么等着 Anthropic
改变策略。或者像 Cline SDK 那样，做足够多的 hill climbing 让 Anthropic
的用户看到切 harness 的收益大过额外成本。

Mario 在博客结尾写过一句话：如果 Pi 不适合你的需求，fork
它。他说这不是客套话。

Pi 代码仓库：github.com/badlogic/pi-mono。Mario
的原始博客：mariozechner.at。Armin
的体验文章：lucumr.pocoo.org/2026/1/31/pi。Paweł
的横评：thoughts.jock.pl。