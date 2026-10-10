---
layout: post.njk
source: https://yage.ai/share/grok-bot-context-engineering-20260827.html
speaker: yage.ai
title: |-
  Grok Bot 泄露：为什么 agent 的 system prompt
  必须冻结
date: '2026-08-27'
summary: 文章深入探讨了 Grok Bot 源码泄露后，在 Agent 系统设计中如何管理 system prompt 的稳定性与动态性。核心思想是，将 system prompt 视为需要显式管理失效边界的工程对象，并提出了‘稳定’（冻结到 compaction 边界）、‘追加’（append-only 序列化）、‘外置’（超过 12KB 的内容写到文件系统）等六条纪律，以平衡模型性能、运行成本和上下文容量。
area: tech-engineering
category: ai-application
tags:
  - system-prompt
  - context-engineering
  - kv-cache
  - agent-workflow
  - context-management
people: []
companies_orgs:
  - Anysphere
products_models:
  - Grok Bot
media_books: []
draft: true
status: evergreen
---

2026 年 8 月，社区把 Grok Bot 0.18.0 逆向出来，源码公开，发布在 GitHub。Grok
Bot 是 Anysphere，也就是 Cursor 的公司，做的桌面 agent 产品。上篇用这个代码库拆了能力层，工具怎么按需扩展、为什么
Cursor 只给模型一部分工具的完整定义。这篇拆 context 层：system prompt
怎么组装、怎么保持稳定、装不下时怎么办。同一个泄露，两个切面。

这是一个罕见的机会：能看到一个生产级 harness
的真实内部编排代码，不是博客声明。

过完源码，它的设计原则和领域里的 best practice
对得上。对得上有两种可能：巧合，或者模仿。怎么分辨？拿相隔一年的 Manus
对照。Manus 团队 2025 年 7 月发表过一篇 Context
Engineering，讲他们怎么管理 agent 的
context。两个团队独立设计，如果收敛到同一条约束，这条约束大概率是底层逼出来的，不是谁的风格偏好。

## 被冻住的 system prompt

把 memory、当前状态这类动态内容放进 system
prompt，每轮重新渲染，相邻两轮的字符串就不同。Grok Bot
的设计选择了另一条路。

FrozenMemorySnapshot 里存着两个字段：渲染好的字符串
render，和一个整数
compactionEpoch。resolveFrozenMemoryPrompt
每次调用时先检查缓存：如果缓存存在、且缓存里的 epoch 等于当前
epoch，就直接返回 render，不调用
renderLive，也不重新查 memory。只有首轮、或 compaction
发生使 epoch 递增时，才会重新 recall + 渲染，并把新的
render 和新的 epoch 写入缓存。

agent profile 用同一套机制。AgentProfilePromptSnapshot
同样以 compactionEpoch 作为冻结键，identity
发生变化时，profile 段保留原文，只在后面追加一段 update
文本，把变更叠加进去。

结果是：在同一个 epoch 内，无论对话进行了多少轮，system prompt 的
memory 段和 profile 段的字节内容都保持不变。只有 context compaction
发生、epoch 递增时，prompt 才会重新生成。

为什么 Cursor 要费劲把 prompt
冻住？每轮重拼不是更能反映当前状态吗？

因为 prompt 是 cache 前缀，位于模型看到的 token
流最前面，每变一次，整个前缀的 KV cache 就失效。这是成本，不是洁癖。

## 前缀一变的成本

模型每处理一个 token 会算出它的 key 和
value，后面生成时注意力读前面所有 token 的
KV，算过的能复用。跨请求还有一层：如果这次开头一段 token
和上次完全相同，这段的 KV 直接复用，按缓存价计费，比原价便宜 10
倍。Claude Sonnet 的 cached input token 是 0.30 美元每百万
token，uncached 是 3.00，Anthropic
的缓存文档里有这个定价和失效规则。

agent 运行时 input 和 output token 的比例大约是 100:1，每一步 context
在增长，输出却只是短短的 function call，成本大头在
input。在这个比例下，前缀稳不稳直接决定运行成本。

自回归模型的性质决定了：前缀里任何一个 token 变了，从那个 token
往后的 KV cache 全部失效。第 p 个 token 变了，第 p 个的 key 和 value
变，第 p+1 个读到不同的第 p 个也跟着变，一路传下去，缓存只能用到第 p-1
个。system prompt
在最前面，它一变，等于整个前缀每一轮都重算，付的是原价。

前缀失效：system prompt 在 token
流最前面，变一个 token 往后的 KV cache 全失效，价格从缓存价 0.30
回到原价 3.00

Manus 那篇 Context Engineering 里给了一个具体的反例：有人在 system
prompt 开头放一个精确到秒的时间戳，让模型知道现在几点，cache
命中率随之归零，每一轮都从头重算。为了知道现在几点，付了全部 input
的原价。

这条经济学还推出两条配套约束：context 要 append-only，不修改历史
action 和 observation；序列化要确定性，很多语言序列化 JSON 对象时 key
顺序不稳定，会悄悄破坏
cache。这两条都是前缀一变全失效的直接推论，上篇那条约束（序列化的工具面必须稳）也是。工具
schema 在 tools 参数里，provider 把它序列化在 context
最前面，动一次全失效。上篇展开了 Manus 的 Mask Don’t Remove 和 Grok Bot
的 hint + meta-dispatch 怎么各自解决这个约束。有了这条经济学做地基，Grok
Bot 在生产代码里实现了三条具体纪律，每条都有 Manus
的独立因果做对照。

## 该稳定时稳定：冻结到
compaction 边界

第一条纪律是把动态前缀冻结到 compaction 边界。Grok Bot 借助
resolveFrozenMemoryPrompt 检查
compactionEpoch，保证同一 epoch 内 memory
段字节级稳定，不随每轮对话变化。AgentProfilePromptSnapshot
是同样的结构，announcedIdentity 变化时 profile 段追加一段
update 文本。把 system prompt 当成 cacheable prefix 来管，只允许它在
compaction 边界变化，这是一等设计约束，不是实现细节。没做冻结的
harness，动态内容一变，整个前缀的 cache 就失效，成本直接翻到原价。

Manus 在 2025 年 7 月那篇里给了同一条因果，原话是 “Keep your prompt
prefix stable”。Grok Bot 在 2026 年 8 月的生产代码里用 compaction epoch
冻结独立实现了它。两个团队、相隔一年、同一个解法，说明这条约束是底层压出来的，不是谁的设计偏好。

冻结有个代价：prompt 不再实时反映最新状态。memory 变了，prompt
还是旧的，直到下一次
compaction。这会不会让模型基于过时的信息做决策？

## 该变时变：运行时状态注入

冻结的是该稳定的部分，不是所有部分。getMcpDiscoveryStatusSection
把这个区分做出来：如果本轮 MCP discovery 因为后端失败，prompt
里会注入一个 <mcp_status> 块，内容是：

> 你的 MCP 工具暂时不可用：本轮从后端发现用户的 MCP
> 连接器失败了。这不代表用户没有 MCP
> 连接器，不要声称没有或某个连接器缺失；如果用户需要 MCP 工具，告诉他们
> MCP 暂时不可用、稍后重试。

这是一个运行时 guard，不是静态指令。prompt
反映的不只是产品策略，还有这一轮发生了什么。

和冻结不矛盾。冻结的是前缀里稳定的部分，动态注入的是必须反映当前状态的部分。失效边界的意义正在于区分这两类：哪些内容可以冻结，哪些内容必须每轮更新。

失效边界的意义在于区分两类内容：system
prompt 字节级冻结只允许在 compaction 边界变化，mcp_status
每轮注入反映本轮发生了什么

Manus 那篇里隐含同一原则：context
内容要反映当前状态，但反映的方式是外置到文件系统，不是每轮重拼。Grok Bot
选择了更轻量的运行时注入。这条纪律目前只有 Grok Bot 一个实现，Manus
是原则层面的对照，不算独立收敛。

prompt 能反映当前状态了，但 context
本身会不断膨胀。网页内容、工具返回的大 JSON，都会把 context
撑大。装不下时怎么办？

## 装不下时外置：文件系统

GetMcpTools 的结果如果超过
12KB，FILE_OUTPUT_THRESHOLD_BYTES = 12_000，Grok Bot
就把内容写到 box 上的 agent-tools/
目录，返回文件路径让模型去 Read。context 里只留路径，不留内容。

更关键的是校验：checkMcpToolDefinitionRead 用
hasReadPath 追踪模型是否真的读过那个 schema
文件，没读过就拒绝调用。读过没有是一个可验证状态，不是模型的自我声明。

外置文件系统：超过 12KB 的完整内容写进
agent-tools/ 文件，context 里只留一条路径，hasReadPath
校验模型真的读过

Manus 给了同一个机制的原则：文件系统是终极 context，“unlimited in
size, persistent by nature, and directly operable by the agent
itself”。压缩策略 “always designed to be restorable”：网页内容可以从
context 丢掉，只要保住 URL；文档内容可以省略，只要 path 还在
sandbox。为什么压缩必须可恢复？Manus 的解释是，agent
要基于全部先前状态预测下一步，你无法可靠地预知哪条 observation
十步后变关键，任何不可逆的压缩都携带风险。

这个机制上篇从能力层提过一句：GetMcpTools 结果超过 12KB
写到文件、只留路径。本篇从 context
容量管理和可恢复压缩的角度展开它。同一个机制，两个切面。

这条纪律也有独立收敛：Manus 给了原则，文件系统等于终极
context，压缩必须可恢复；Grok Bot 给了实现，12KB 阈值加
hasReadPath 校验。两个团队、相隔一年、同一套外置纪律。

Grok Bot 三条纪律（稳定、追加、外置）都有对照证据。Manus
那篇里还有三条，Grok Bot 源码里没有直接体现，属于同一套 context
工程纪律，但目前只有 Manus 一条证据链。

## Manus 的三个补充机制

Manus 处理复杂任务时会建一个
todo.md，不断重写、逐项打勾。这是刻意操纵注意力，不是可爱行为。一个典型任务平均
50 次 tool call，长循环里模型容易漂移、忘了全局目标。通过不断重写 todo
列表，Manus 把全局目标复述到 context 尾部，推入模型的近期注意力，对抗
lost-in-the-middle 和 goal misalignment。用自然语言把注意力 bias
到任务目标上，不需要架构改动。

agent 会犯错，这是现实，不是
bug。多步任务里，失败是循环的一部分，不是例外。常见冲动是清理
trace、重试、重置状态，但擦除失败等于移除证据，没有证据模型无法适应。把错误留在
context 里，模型看到失败的 action 和 stack trace
会隐式更新信念，降低重复同样错误的概率。Manus 认为 error recovery 是
agentic 行为最清晰的指标之一，却在多数 benchmark 里代表性不足。

模型是优秀的模仿者，会模仿 context 里的行为 pattern。如果 context
里充满相似的 action-observation 对，模型会跟随那个
pattern，即使它已不再最优。Manus 的例子：批量 review 20 份简历，agent
陷入节奏，机械地重复相似动作，导致 drift、overgeneralization，有时
hallucination。解法是注入结构化变异：不同序列化模板、换措辞、顺序和格式的小噪音。context
越均匀，agent 越脆。

这三条目前只有 Manus 一条证据链，Grok Bot
源码里没有直接体现，标注为未独立验证。

把 prompt 和 context
当一等工程对象，不是配置字符串。一套六条纪律：

维度

该怎么做

因果

独立收敛证据

稳定

前缀冻结到 compaction 边界

KV cache 10x

Manus 因果 + Grok Bot compaction epoch 冻结

追加

append-only，序列化确定性

前缀一变全失效

Manus 因果 + Grok Bot 不重拼

外置

大 artifact spill 到文件系统，可恢复压缩

context 容量 + 不可逆压缩有风险

Manus 原则 + Grok Bot 12KB spill + hasReadPath

复述

目标复述到 context 尾部

对抗 lost-in-the-middle

Manus recitation

保留

错误留在 context

模型靠证据隐式更新信念

Manus keep-wrong-stuff-in

变异

序列化注入结构化变异

对抗 few-shot 模式化

Manus don’t-get-few-shotted

前三条（稳定、追加、外置）两个团队独立收敛，是承重的。后三条（复述、保留、变异）目前只有
Manus 一条证据链，未独立验证。

给写 harness 的人一个收尾：把 system prompt
当成需要显式管理失效边界的工程对象。什么该稳定、什么只追加、什么外置、什么复述、什么保留、什么变异，每条都有因果，不是风格偏好。两个独立产品收敛到同一套纪律，这套纪律就是判断该不该抄的依据。

## 系列文章

同一个泄露，两个切面：

Grok Bot 泄露：Cursor 为什么只给模型一部分工具的完整定义：能力层，模型能调用什么、怎么按需扩展

Grok Bot 泄露：为什么 agent 的 system prompt 必须冻结：context 层，模型看到什么、prompt 怎么管理