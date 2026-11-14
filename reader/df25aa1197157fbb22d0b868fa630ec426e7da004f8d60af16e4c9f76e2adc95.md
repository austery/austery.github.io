---
layout: post.njk
source: https://yage.ai/share/grok-bot-dynamic-tools-20260827.html
speaker: yage.ai
title: |-
  Grok Bot 泄露：Cursor
  为什么只给模型一部分工具的完整定义
date: '2026-08-27'
summary: 文章深入分析了 Grok Bot 源码泄露后，Cursor 如何设计其动态工具加载机制，并探讨了将工具定义放在 context 层还是 tools 数组层对模型性能和成本的影响。核心观点是，将动态性推到 context 层（通过一行 hint 形式存在）可以保持工具面稳定，同时实现按需加载，这与 Manus 的静态全量加载策略在底层约束上是相通的。
area: tech-engineering
category: ai-application
tags:
  - agent-harness
  - dynamic-loading
  - context-engineering
  - kv-cache
  - tool-schema
people: []
companies_orgs:
  - Cursor
  - Anysphere
products_models:
  - Grok Bot
media_books: []
draft: true
status: evergreen
---

2026 年 8 月，社区把 Grok Bot 0.18.0 逆向了出来，源码公开。Grok Bot
是 Anysphere，也就是 Cursor 的公司，做的桌面 agent 产品。0.18.0
版本是一个编译后的 app，重建的源码是可读的 TypeScript，发布在 GitHub。事件之后
Anysphere 撤下了 0.18.0 的安装包，没有官方声明，也没有 DMCA。

这是一个罕见的机会。谈 agent harness
的设计，平时看到的是博客和设计哲学，这次能看到一个生产级 harness
的真实内部编排代码：system prompt 怎么组装、工具怎么暴露给模型、context
怎么管理。而且这个重建是 evidence-based
的，每行恢复的代码都有可检查的产物锚点，它描述的行为就是产品实际的行为。

过完源码，它的很多设计原则和领域里的 best practice
对得上。对得上有两种可能：巧合，或者模仿。怎么分辨？拿相隔一年的 Manus
对照。Manus 团队 2025 年 7 月发表过一篇 Context
Engineering，讲他们怎么管理 agent 的
context。两个团队独立设计，如果收敛到同一条约束，这条约束大概率是底层逼出来的，不是谁的风格偏好。

这篇文章拆 Grok Bot 的能力层：模型能调用什么、怎么按需扩展。下一篇拆
context 层：模型看到什么、prompt 怎么管理。

## 一道先查后调的门槛

Grok Bot 有 30 多个工具。其中 9 个 dynamic 工具，模型每一轮只看到一行
hint；其余 18 个静态工具直接给完整 schema。比如 CloudAgent
这个工具，模型看到的是一行话：“Launch and manage Cursor cloud coding
agents for repository work.”。要用它，模型得先调 GetMcpTools 把完整
schema 拉进 context，再调 CallMcpTool 去执行。schema 太大（超过
12KB）时不塞进 context，而是写到文件、只把路径返回给模型，这个机制的
context 容量一面下一篇展开。

这给 Cursor 自己加了一道门槛。为什么不直接把 30
个工具的完整定义都给模型？

先说一个次要原因。工具太多会干扰模型，工具越多越容易选错，Manus
那篇里说 “your heavily armed agent gets dumber”，就是这个意思。但 30
个工具的量级还不算大，干扰有限，这不是主因。

主因是 KV cache。跨请求有一层前缀缓存：这次开头一段 token
和上次一模一样时，这段按缓存价计费，比原价便宜 10 倍（Claude Sonnet 的
cached input 是 0.30 美元每百万 token，uncached 是 3.00）。agent 运行时
input 和 output token 的比例大约是 100:1，成本大头在
input。失效机制和这些数字下一篇展开，本篇只引用结论。

这里要分清两种放工具定义的方式。用结构化的 tools 参数时，provider
把它序列化在 context 最前面，Manus 在博客里观察到的正是这个位置。API
层面你看不到这个序列化结果，tools
只是个独立参数，但缓存行为会暴露它：改一次 tools，连后面 messages
的缓存也全失效，Anthropic
的缓存文档把这个失效顺序写得很清楚。它每一轮不变时，整个前缀（工具、system
prompt、到目前为止的对话）都和上一轮相同，全部命中缓存，只有新加的这一轮按原价算。

tools 参数一变就不一样。工具在最前面，第一个不同的 token
出现在很靠前的位置，从那个位置起缓存失效，等于整个前缀每一轮都重算，付的是原价，而且前缀很大，每一轮都在付。工具本身只占一小段，但它控制着后面整段大前缀能不能拿到
10 倍折扣。

把工具定义写进对话内容是另一条路。位置自己控制，追加在对话末尾，前面的
token 一个不动，前缀缓存完整保留，只有新加的那段按原价算。API 允许每轮改
tools 数组，也允许在 message 里定义工具，限制不在
API，在缓存经济学：动态 schema 放哪一层，决定前缀稳不稳。Grok Bot 的
meta-tool 走的就是这条：动态 schema 不进 tools 数组，进对话。

Cursor 加那道门槛，目的是让工具面保持稳定。tools
数组里只有静态核心工具（READ、SHELL、WRITE、GLOB、GREP
这些每轮都要用的）加上 GetMcpTools 和 CallMcpTool 两个稳定入口。其余 9
个工具的完整 schema 不进 tools 数组，以一行 hint
的形式存在，需要时才拉进 context。

那个一行 hint 不是自动截断工具 description 生成的。源码里有一个叫
SAND_DYNAMIC_TOOL_HINTS 的常量，9 个 hint 全是手写的。CLOUD_AGENT
对应的那行，是有人专门写了告诉模型这个工具能做什么、什么时候该选它。这是产品决策，需要逐条打磨。但这里有个没答的问题：为什么只有这
9 个工具需要这套动态机制？其余 18 个静态工具为什么不用？

## “动态加载”掩盖了两个正交维度

答案在于工具本身有两种不同性质。模型能对外界做事，靠的是 tools
数组，它通过结构化的 tool call 调用里面的工具。但 tools
数组里不只有专门工具，还有 bash、read、write 这类通用工具。bash
尤其强，通过它模型能调任何 CLI、跑 Python、curl 任何 HTTP
端点。模型的手，大部分时候是这少数几个通用工具。

这里有个容易忽略的事实：很多新能力不需要新工具。一个能力如果能用 bash
表达（一个 CLI、一段 Python、一个 HTTP
端点），模型只需要知道怎么驱动它，知识放进 context 就够了。能力由已有的
bash 提供，skill 只提供知识，不用往 tools 数组里加任何东西。我们的 skill
体系就是这么做的：skill 是 markdown，教模型怎么调一个 CLI，模型用
bash 执行。这也是 thin
harness fat skills 能成立的原因。

动态加载把两种事情混在一起了。一个是知识层：按需把怎么做拉进
context。载体是 markdown，机制是检索、路由、加载。Claude 的 Agent Skills
就是这一层，加载一个 skill 是读文件进
context，模型知道怎么做了，用已有的 bash 去执行。

另一个是能力层：按需把能调用什么暴露给模型。载体是 tool
schema，也就是传给 API 的 tools 参数里的 entry，不是 context
内容。这一层只在能力没法用已有通用工具表达时才需要：一个要在沙箱远端 box
里跑的功能、一个需要 app
内部状态或鉴权的功能、一个需要特定结构化接口的功能。这些没法用 bash
表达，必须往 tools 数组里加一个新的 tool schema。Grok Bot 的
GetMcpTools/CallMcpTool 就是这一层。

关键区别在机制归属：skill 是知识载体，它的机制是检索、路由、把
markdown 读进 context，它没有能力去改下一次请求的 tools 参数。tools
数组是 harness 的东西，由构建每次请求的应用代码决定。skill
的加载改变的是 context 内容（模型知道怎么做），能力层的加载改变的是
tools 数组（模型能调什么）。能力必须走 tool call 而不是 bash，skill
的机制就覆盖不到，得用能力层的机制。

这个分层之所以能成立，是因为知识层在 Grok Bot
出现前的一年里已经有了独立成熟的机制。如果知识层还没有自己的载体，两层就没法分开做。

知识层和能力层是两个正交维度：skill
加载把怎么做拉进 context，dynamic tool 加载把能调用什么放进 tools
数组，两者不能互相替代

## 知识层的演化时间线

理解 Grok Bot
为什么能把能力层和知识层分开做，需要先看知识层在这一年里怎么成熟的。2025
年 7 月，Manus 团队发表了 Context Engineering 那篇文章。当时还没有 skill
机制。Manus 解 context 工程时，知识层没有独立的 markdown skill
载体，它用文件系统和复述来外置和保持目标。

三个月后，2025 年 10 月 16 日，Anthropic 发布了 Agent Skills。Claude
先行，知识层第一次有了独立载体：一个文件夹，包含指令、脚本和资源，模型只在相关时按需加载。两个月后，2025
年 12 月 18 日，Anthropic 把它发布为开放标准，Codex、Cursor、VS Code
跟进支持。有一篇论文做了 8135 次受控实验，发现 65.7%
的提升靠的是步骤和检查单类的 skill，只有 4.5% 靠补充事实。这篇论文我们拆过：skill
是检查单，不是教材。

在我们的本地系统里，这对应一个三级缓存结构：L1 是每次都加载的
AGENTS.md（大约 200 行指针），L2 是按需查的索引，L3 是匹配后才加载的具体
skill 文件。Garry Tan 那篇 thin harness
fat skills 讲的就是这一层，harness 只做四件事，智能推到
skills，执行推到确定性工具。

到 2026 年 8 月 Grok Bot 泄露时，它已经有了 skill 和 plugin。system
prompt 里原话说 plugin 是”a marketplace bundle of connectors and
skills”。再往极端走，DSH 把连 agent loop
都做成了插件，这是知识层动态加载的极限形态，但需要 Cordis
那套运行时基础设施。

知识层有了自己的载体，能力层才能做干净的事：只处理 bash
表达不了的那部分。Grok Bot 在这一层的设计，才是本篇的主角。

## Grok Bot 的能力层机制

Grok Bot 的 dynamic tool 机制，拆开来是三块相互咬合的设计。

native 工具包成虚拟 MCP server：Cursor 把自己的 native
工具（CloudAgent、CopyToBox 等）包装成一个 namespace 为 “cursor” 的虚拟
MCP server。源码里的常量 CURSOR_DYNAMIC_TOOLS_NAMESPACE 就是
“cursor”。这样模型用同一对 GetMcpTools/CallMcpTool 访问 native
工具和外部 MCP 插件，只学一个调用模式。CallMcpTool 的 dispatch
层会拦截原始参数，解析出真实工具名，路由到 native executor 或者外部
server。

一行 hint 是产品决策。SAND_DYNAMIC_TOOL_HINTS 里那 9 个 hint
是手写的。每个 dynamic 工具都带上 contextType: { type: “dynamic”,
conciseStaticContext: hint }
标记，模型看到的就是那一行话。这是有人专门写的路由提示，不是从工具的
description
字段截断来的。工具多到一定程度，模型需要一层路由来判断该选哪个，这层路由需要手工打磨。

这个 index
是雅虎式的，不是谷歌式的。谷歌模式假设信息已经在那儿了，提问时实时检索出来就行；雅虎模式靠主编人工筛选、撰写、组织目录。这
9 行 hint
就是产品团队当了主编，在模型提问之前把工具面编成每工具一行。OpenAI
的数据 agent 里我们见过同一个模式：那篇文章里
LLM 接管离线主编的角色，把杂乱的数仓代码预先编译成高密度
context，在线端只检索编好的材料，不检索原始元数据。

skill 和 dynamic tool 正交，各管一层。Grok Bot 两个都有。skill 走
plugin 体系，管知识层。dynamic tool 机制只用于 app 自己的 native
工具，管能力层。两者不混。但这套设计不是唯一答案：同期独立设计的 Manus
走了一条完全相反的路。

Grok Bot 的先查后调流程：模型先看到一行
hint，用 GetMcpTools 拉 schema，再用 CallMcpTool 执行，dispatch 层路由到
native executor 或外部 server

## Manus 的对照：Mask, Don’t
Remove

Manus
的方向正好相反：不动态加载工具，而是一开始就把所有工具全量放进去，然后在解码时决定哪些不能选。原因有两个。工具定义序列化后位于
context 前端，任何改动都会 invalidate 后面所有 KV cache。历史的 action
和 observation 还在引用已经不存在的工具，模型会困惑并产生 schema
violation。

他们的解法叫 “Mask, Don’t Remove”：工具定义永远静态全量，用
context-aware 的状态机在解码时 mask token
logits，约束当前状态可选哪些工具。工具名刻意设计成一致前缀，比如
browser_ 开头的工具和 shell_ 开头的工具，方便按组约束。

看起来，Manus 说别动态加工具，Grok Bot
却在动态加载工具，两个答案相反。实际上两者守的是同一条底层规则：序列化的工具面必须稳定，把动态性推到别处去。差的只是推到哪一层。

Manus 推到解码时。工具全量常驻
context，动态的是当前能选哪些。代价是所有 schema 常驻 context 的 token
税，收益是 KV cache 完全稳定。

Grok Bot 推到 context 层。tools 数组里只有静态核心加上两个稳定的
meta-tool 入口，动态工具的 schema 不进 tools 数组，以一行 hint
存在，需要时才拉进
context。它看起来在动态加载，但序列化的工具面其实是稳定的。这正好符合
Manus 那条规则。

两个团队、相隔一年、独立设计，收敛到工具面必须稳这同一条约束。两者都走到这里，说明这条约束是底层压出来的，不是设计偏好。那剩下的问题就是：动态性推到哪一层，各有什么代价？

## 动态性住到哪决定整个设计

把四个 harness 放在一起看，动态性住到哪决定了整个设计：

harness

动态性住哪

代价 / 收益

Codex

声明式 + 重启（公开声明）

简单，但换工具要重启进程

Manus 2025/7

解码时

KV cache 全稳，但 schema 常驻 token 税

Grok Bot 2026/8

context 层

工具面稳 + schema 按需，但多一次 GetMcpTools 往返

DSH

进程内插件（连 loop 都可换）

最灵活，但要 Cordis 那套运行时基础设施

四个 harness
的动态性住哪决定整个设计：Codex 重启进程，Manus 解码时屏蔽，Grok Bot 放
context 层，DSH 进程内插件

什么时候该用 Grok Bot 这种方式？算一笔成本账：多一次 GetMcpTools
往返的边际成本，要小于 N 个未用 schema
的常驻税。只在工具面大、单轮使用稀疏、模型选择能力有限这三个条件同时满足时才划算。DSH
那篇里有个判断：上限相同，下限不同。工具少的时候几种方式差不多，工具多了之后下限的差距就出来了。

这条约束的因果链条下一篇会展开。KV cache 经济学的数字也在那边给。

给写 harness
的人一个收尾：先分清要拉的是知识还是能力，别用错层的机制。能力层的动态性，先决定它住哪一层，再谈实现。两个独立产品收敛到同一条约束，这本身就是判断该不该抄这个设计的依据。

## 系列文章

同一个泄露，两个切面：

Grok Bot 泄露：Cursor 为什么只给模型一部分工具的完整定义：能力层，模型能调用什么、怎么按需扩展

Grok Bot 泄露：为什么 agent 的 system prompt 必须冻结：context 层，模型看到什么、prompt 怎么管理