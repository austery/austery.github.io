---
layout: post.njk
source: https://yage.ai/share/vercel-eve-agent-directory-20260618.html
speaker: yage.ai
title: |-
  Vercel 开源 eve：「一个文件夹就是一个
  agent」这句话为什么不是废话
date: '2026-06-18'
summary: 文章探讨了 Vercel 开源的 'eve' 项目，它提出了将 Agent 视为独立软件（一个文件夹）而非单一框架或模型延伸的观点。通过对比 LangChain 的零件拼装路线和 Claude Managed Agents 的云端配置项路线，eve 强调了 agent 生产生命周期中对部署、版本管理和持久化执行等基础设施的需求，并提出了一种将运行能力与个人认知上下文（context infrastructure）相结合的三层分工模型。
area: tech-engineering
category: ai-application
tags:
  - agent-architecture
  - software-development
  - workflow-tools
  - deployment
people: []
companies_orgs:
  - Vercel
products_models:
  - eve
media_books: []
draft: true
status: evergreen
---

2026 年 6 月 17 日，Vercel 在伦敦 Ship 大会上以 Apache 2.0 协议开源了
eve，代码仓库在 github.com/vercel/eve。官方博客直接给了一句话做标题：An agent is a
directory。翻译过来就是，一个 agent 就是一个文件夹。

第一眼读到这句话，困惑很难避免。建个文件夹谁不会。如果说 agent
框架的终极答案只是一个目录结构，那过去几年整个行业在争论什么。

困惑不是凭空来的。这句话冲撞了我们心里对 agent
框架的默认设定。过去两年搭 agent，基本是两条路。一边是 LangChain
的路线：用 Python 把 Tool、Chain、Memory
拼到一起，自己管注册、管部署。另一边是 Claude 的路线：在 Anthropic
的云上配几个 connector，让 Claude 伸手去碰你的 Slack 和数据库。eve
说这两条路都走偏了。eve 把 agent 当独立软件来建：文件系统做定义，Git
管版本，一条命令部署上线。

三种做法的背后，是同一个问题给出的三个不同答案：agent
到底是什么。LangChain 把它当成编程问题，答案是零件你自己拼。Anthropic
把它当成模型的延伸，答案是给 Claude 开几扇门。eve
把它当成独立软件，答案是一个文件夹。这不是功能多少的差别，是路线分歧。沿着不同的路线往下走，agent
能不能从 demo 变成 24/7 的生产服务，结局完全不同。

## LangChain：零件你自己拼

做 agent 开发的人，多半最先碰到的就是 LangChain。LangChain
给了一套编程抽象：Agent、Tool、Chain、Memory、Retriever。你在 Python
里把这些组件拼好，给每个 tool 写输入输出 schema，写注册代码把它们挂到
agent 上，自己管 session 状态，自己接 vector store 搞 RAG，部署时自己搭
API server、自己配监控。自由度极高，代价是每块都得自己动手。

这件事很像在宜家买柜子。木板和螺丝全摊在你面前，理论上能拼出各种形状。但拼完才只是第一步，后面还有刷漆、上墙、装把手。LangChain
的职责到零件怎么连为止。你的 agent 文件怎么组织、怎么上线、跑到一半的
session 部署时会不会断、审批等待时要不要烧 compute，这些事它一概不管。The
New Stack 的报道 把 LangChain 的 LangGraph 称为最成熟的 agent
框架，但它的 durable execution
跟部署、运维、版本管理是割开的，你得自己缝到一起。

宜家模式的好处是形状自由，坏处是你得自己是木工。多数团队没有这种余裕，最终
agent 停在 demo，上线那一步从来没有人走完。

## Claude Managed
Agents：给模型开几扇门

Anthropic 走的是相反的路。Claude Managed Agents 的逻辑是：Claude
是中心，agent 是 Claude 把手伸进外部系统的管道。你配一个
connector，Claude 就能读到你的 Slack、查你的数据库。agent 全程跑在
Anthropic 的云上，只绑 Claude 一个模型。数据、调用、执行上下文全部落在
Anthropic 的服务器里。

Anthropic 的 sub-agents
文档 和 skills
文档 写明了这套逻辑：connectors 对接 MCP server（挂在 Anthropic
云上），custom connectors 则是把你的 MCP server 接入 Anthropic
云。你配置的不像一个能独立行动的新员工，而是 Claude 能碰哪些东西。

这条路的好处是开箱即用，零运维。代价叠了三层。第一，agent
不是你拥有的软件，它是云上的一个配置项，改一句 instructions 没有 diff
可看，没有版本历史可追溯，没有 preview deploy 可以灰度。第二，模型绑死在
Claude 上，你只能等 Anthropic
升级，没有自己做模型选型的余地。第三，数据全在 Anthropic
的服务器上，合规要求高的场景过不去。

## 第三条路：把 agent
当独立软件来建

回到开头那句话。eve 说 agent is a
directory，不是在宣称用文件夹组织代码是什么新鲜事。它实际在说三件事，这三件事各对准了
LangChain 和 Claude Managed Agents 缺失的那一环。

三种 agent 路线对比

第一，文件名就是定义，免掉注册这一步。在 eve
里，agent/tools/run_sql.ts 这个文件名本身就是工具名，框架
build 时自动发现、自动注册。agent/skills/revenue-rules.md
自动变成按需加载的上下文，模型聊到收入话题时它才出现。你不需要写任何把
tool 挂到 agent 上的胶水代码。eve 的 官方文档 把这套规则摊开了：eve is
filesystem-first，文件的位置决定了它的角色，不存在需要人工同步的独立注册表。加一个
tool 就是加一个文件，删一个 tool 就是删一个文件。LangChain
让你写注册代码的地方，eve 让文件系统自己说话。

第二，agent 是你真正拥有的软件。eve agent 就是一个 Git 仓库。改一句
instructions 是一个 commit，有 diff 可 review，有历史可追溯。每笔 commit
自动生成 preview deploy，eve eval 接入 CI 当 deploy
gate，出了问题秒级 rollback。管理 agent 的方式和管理普通 Web
应用一模一样。Claude Managed Agents 则是云上的配置项，不是你能随时
commit、diff、rollback 的代码。分歧再往深一层看：Anthropic
认为模型是平台，agent 是模型的延伸；Vercel 认为模型是商品，通过 AI
Gateway 一行代码就能在 Claude、GPT、Gemini 之间切换，agent
是独立软件。两种假设往下走，agent 的生产生命周期会完全不同。

第三，生产运行时打包进了同一个目录。eve 内置了三项能力。Durable
execution：每一步自动 checkpoint，部署不会打断正在跑的
session，审批等待期间零 compute 消耗，Workflow SDK 保证 runs resume from
the last good step, instead of from zero。Sandbox：agent
写的代码跑在隔离 microVM 里，有自己的 kernel
和文件系统，和宿主完全隔绝。Channels：eve channels add slack
一条命令就让 agent 出现在 Slack 里，审批渲染成 Slack 按钮，提问变成
select menu，agent 打字时你还能看到 typing indicator。同一个 agent
可以同时出现在 Slack、Discord、Teams、HTTP 上，session 在这些 channel
之间自由迁移：Slack 上的问题能切到网页接着聊，HTTP 收到的 webhook
能自动开一条 Slack 调查线程。这三项能力，LangChain 不内置，Claude
Managed Agents 也没有同等级别的深度。

eve
像一个精装厨房。灶台、冰箱、洗碗机全部就位，你只需要决定冰箱里放什么菜就行了。代价是你不能改厨房的格局（目录约定不可协商），并且这个厨房默认盖在
Vercel 这栋楼里。官方对多平台支持的承诺是 on the
way，还没给时间表。但跟宜家木板和给 Claude
开几扇门比起来，这已经是离生产最近的一条路了。

## 厨房有了，菜从哪来

eve 解决的是 agent 怎么跑、怎么部署、怎么接 Slack、怎么不死。它不解决
agent 想什么、输出有没有判断力。这里面最容易发生误读。

eve 的 instructions.md 和 skills/
是装载位置，不是内容来源。官方博客明说了：That leaves the part no
framework can write for you: what your agent actually
does。精装厨房的灶台、冰箱、洗碗机全配好了，但菜还是你自己买、你自己切、你自己调味。你的
agent 输出的是 checklist 还是有判断力的分析，取决于你往
instructions.md 和 skills/ 里塞了什么，跟 eve
本身没关系。eve 默认的 instructions.md 示例就一行 You are a
concise assistant。

而这恰好是我过去一年在做的事。我把这套系统叫 context
infrastructure：从录音转写、微信对话、AI
对话历史、每一次纠正中反向蒸馏出判断原则，积累成一套按需加载的认知上下文。eve
的 instructions.md 默认是一行示例，我的
SOUL.md 是 73
行行为契约加上五十多条跨场景反复验证的判断原则。把后者塞进前者的装载位置，你得到的是一个既有生产级运行能力、又带着个人认知底色的
agent。

单独 eve 能跑，但输出很可能停在共识层：正确但平庸，换任何人来问 AI
都能得到差不多的回答。单独 context infrastructure
有深度，但没有生产运行时：它不能自己接 Slack、没有 durable
execution、不能一条命令部署。两者放一起才是完整的拼图。eve
负责运行，context infrastructure
负责认知内容。它们处在不同的抽象层，不互相排斥。

Agent 时代的三层分工

Agent 时代的分工正在变得清晰。Anthropic
负责协议：模型怎么理解世界、怎么操作工具，MCP 和 skills
格式已经是事实标准。Vercel 负责运行时：agent
怎么跑、怎么部署、怎么活过明天。每个人自己的 context infrastructure
负责认知内容：agent
想什么、判断什么、输出什么。三层各归各的，谁也不用替代谁。