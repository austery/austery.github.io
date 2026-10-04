---
layout: post.njk
source: https://yage.ai/share/agent-filesystem-survey-20260507.html
speaker: yage.ai
title: Agent 文件系统：从喂给模型记忆到让模型自己翻文件
date: '2026-05-07'
summary: 本文深入分析 AI Agent 记忆机制从向量数据库向文件系统的演进，指出成本、LLM 能力及渐进式披露是驱动因素。文章介绍了 Anthropic、Vercel、Turso 等公司的实践，讨论了语义弹性、安全与 GC 等挑战，并预测未来架构将以文件系统为核心的状态层。
area: tech-engineering
category: tech-trends
tags:
  - ai-agents
  - file-systems
  - agent-architecture
  - context-management
  - progressive-disclosure
people:
  - Arpit Bhayani
  - Lance Martin
  - Simon Willison
  - Daniel Miessler
  - Peak Ji
companies_orgs:
  - Anthropic
  - Vercel
  - Turso
  - Manus
products_models:
  - AgentFS
  - MCP
  - Agent Skills
  - SQLite
media_books: []
draft: true
status: evergreen
---

如果你在过去一年留意过 AI agent
基础设施的动向，应该注意到一个奇怪的趋势。越来越多的团队在讨论文件系统——不是数据库、不是向量检索、不是记忆层，就是文件系统。Turso 发布了一个叫 AgentFS 的产品，用 SQLite 给 agent
创建一个虚拟文件系统。Anthropic
的两篇工程博客，一篇教你怎么把 MCP
工具调用改成文件系统上的代码文件，一篇说 agent
skill 就是文件夹加 Markdown。Vercel
开源了一个 knowledge agent template，核心卖点是”没有向量数据库，没有
embedding，没有 chunking pipeline”。Manus
的 context engineering 博客被广泛引用，核心技巧就是”把文件系统当作
context 来用”。

这些事发生在同一个时间窗口里。它们共同指向一个方向——大家发现 agent
的外置记忆这件事，过去几年的做法可能一直没抓住关键。

## 从记忆到文件系统——三代演化

回头梳理一下这条线，可以分为三个阶段。

第一代：裸 context。 最早的 agent 就是在一个 context
window 里跑完所有事。对于一个涉及 50
步工具调用的任务，每一步的结果都堆在 context 里。Manus
报告说他们平均 input-to-output token 比例是
100:1。这不只是慢的问题——Claude Sonnet 的 cached input 是
$0.30/MTok，uncached 是 $3.00/MTok，差了 10 倍。你需要在这个 context
里塞进所有工具定义、历史轨迹、中间结果。很快就塞不下，而且越来越贵。

第二代：记忆系统。 行业针对这个问题的第一反应是”给
agent 加个外置记忆”。Mem0、MemGPT、Pinecone、ChromaDB
之类的产品应运而生。思路是：把对话历史或知识库 embedding
化，存在向量数据库里，需要时检索回来塞进
context。这确实解决了持久化的问题——agent 不再每次从头开始。但它没有解决
context 的
economics。你仍然需要把检索回来的内容塞进窗口，检索本身也有成本和延迟。而且向量检索是模糊匹配。一个问题在于：当你不知道
RAG 捞回来的 chunk 对不对，你在 model call 之前就已经失去了确定性。

第三代：文件系统即 context。 这个转折点出现在 2025
年下半年。Manus
的博客明确写道：“the file system as the ultimate context: unlimited
in size, persistent by nature, and directly operable by the agent
itself”。做法是把内容放在文件系统里，只把一个文件路径或 URL 放进
context，需要的时候 agent
自己去读。压缩是可逆的——你丢掉的不是内容，只是路径。这和 Anthropic
说的 progressive disclosure 是同一个原理：agent
只在需要的时候加载它需要的那部分信息。

这一代的核心转变是：从 push 变成
pull。第二代的做法是”我把我觉得你需要的信息推送进
context”，第三代的做法是”你自己去文件系统里找你需要的”。这个转变背后有一个重要的前提条件——LLM
天生就会操作文件系统。它们在大量编程任务上训练过，已经知道怎么
ls、grep、cat、find。

## 为什么是文件系统，为什么是现在

三个条件同时成熟，才让这个模式成立。

第一，LLM 的文件系统能力是一个免费遗产。 正如 Arpit
Bhayani 在一篇 LinkedIn 帖子中总结的：“models are trained heavily on
coding tasks inside sandboxed environments with shells and filesystems.
Hence, they get really good at navigating directories, reading files,
running shell commands”。如果你的非编程 agent 也有一个 shell
和文件系统，它免费继承了所有这套能力。不需要专门训练，不需要特殊的 tool
calling 格式。

第二，context 的经济学已经不可忽略。 Manus
报告了一个数据：100:1 的输入输出比，10x 的 cached/uncached 差价。Anthropic
更直接——他们在一个例子里算了一笔账：直接加载所有 MCP 工具定义需要
150,000 token，改成让 agent 通过文件系统按需发现工具定义后只要 2,000
token，省了 98.7%。当 context 的成本从”可以忽略”变成”agent
运行的最大开销”时，任何能大幅降低 token 消耗的架构都会胜出。

第三，渐进式披露利用了 LLM 注意力机制的特性。 Anthropic
的 Agent Skills 设计分三层：启动时只加载 name 和
description，匹配到时加载完整的
SKILL.md，真正需要时才读取附属文件。这就是 progressive disclosure
的核心——agent 自己决定需要多少 context，而不是开发者预先猜。Manus 的
todo.md recitation 用的是同一个原理的变种：通过反复把目标写进 context
末尾，把目标推到模型的近期注意力范围里，对抗 lost-in-the-middle。

## 谁在做什么，以及他们的设计选择

虽然大家都在往文件系统的方向走，但具体做法分歧很大。这些分歧暴露了不同团队对”核心问题是什么”的不同判断。

Anthropic 的判断是：问题出在 tool calling 的 token
消耗。 他们的
MCP 文章（2025 年 11 月）提出的方案是：保留 MCP 作为连接协议，但把
MCP 工具的调用方式从直接 function calling
改成通过文件系统发现、通过代码执行。agent 列出 ./servers/
目录看到有哪些可用工具，读它需要的工具文件，然后写 TypeScript
代码调这些工具。他们的核心洞察不是 MCP 不好，而是直接 tool calling
让每一步的结果都必须经过 model 的 context
窗口，这在大文件场景下代价太高。把中间结果留在执行环境里，只 log
必要的输出给 model，可以省掉大量 token。

这个方案有几个容易被忽略的深度。第一，Anthropic
明确说了数据隐私的好处：agent 执行环境里流转的数据，不需要经过 model 的
context，所以 PII 可以只在执行环境和目标服务之间流动，永远不出现在
prompt 里。第二，Agent Skills 的
filesystem 模式已经被 Cursor、GitHub Copilot、OpenAI Codex
跟进，文件系统正在成为 agent 行为的可移植层。

Vercel 的判断是：问题出在 RAG 的不确定性。 他们的
knowledge agent template把”没有向量数据库”当作核心卖点。agent 在一个
Firecracker
sandbox 里运行，通过
grep/find/cat
搜索知识库文件。结果是完全确定的——同样的问题，同样的文件，同样的 grep
命令，永远返回同样的结果。Vercel
自己的博客写了一个案例：sales call 总结用文件系统加 bash
的方式，每次调用成本从 $1.00 降到了 $0.25。

不过 Vercel 自己也很诚实地披露了一个反例。他们和一个叫
Braintrust
的团队做了对比评估：对于结构化查询（比如”上个月销售额最高的客户是谁”），SQL
的准确率是 100%，bash 加上文件系统只有 53%，而且 bash 用了 7 倍的
token、6.5 倍的成本。最终结论是 hybrid：用 grep 做探索，用 SQL
做查询。

Turso/AgentFS
的判断是：文件系统和数据库不应该是二选一。 他们的方案在 SQLite
上实现了一个 POSIX 兼容的虚拟文件系统——agent 看到的
/output/report.pdf 是一个文件系统路径，背后实现是一个
SQLite 表的 inode 和 dentry。这意味着 agent
可以同时用文件系统接口（读文件、列目录）和 SQL 接口（同一个 SQLite
文件可被直接查询）。AgentFS 还支持 FUSE 挂载，可以让 agent
直接在这个虚拟 FS 上运行 git、grep 和其他 Unix
工具。从 GitHub
数据看，这是目前最活跃的 agent 文件系统项目（3.1k stars，755
commits，58 个 release）。

Manus 的判断是：问题出在 context 窗口是 agent
架构的中心瓶颈。 Lance Martin 对
Manus 的深度分析详细解释了他们三管齐下的方案：reduce（对老的 tool
result 做 compaction 和
summarization）、offload（把内容通过文件路径引用放到 context
之外）、isolate（sub-agent 用自己的 context
window）。在这三者中，offload
到文件系统是最核心的创新——“可逆压缩”原则保证 agent
不会因为丢内容而丢失信息。

## 这个趋势的盲区

所有这些方案都面对几个尚未被充分讨论的问题。

第一，文件系统缺乏语义弹性。
这里有一个很少被讨论的问题，可以叫”路径幻觉”：当 agent 期望的路径
/state/user_prefs.json 不存在时（因为系统把它移到了
/config/users/prefs.json），LLM
倾向于假装它存在或干脆创建一份新的，而不是系统性地搜索。在向量记忆系统里，schema
变更不会导致查询失败——语义检索总能找到相关的内容。文件系统把问题从”可确定”变成了”可路径”，付出的代价是失去了语义容错性。

第二，GC（垃圾回收）问题。
向量记忆有一个自然的衰减机制：老的内容在 embedding
空间里的匹配度自然下降，新内容自动取代旧内容。文件系统里一个文件写进去就永远在那里，直到谁明确去删它。如果
agent 持续往 /tmp/agent_workspace/ 里写
scratchpad、中间推理步骤、状态文件，谁来清理？agent
自己管理磁盘空间？AgentFS 的 snapshot
能力部分解决了这个问题（回滚到任意历史状态），但”什么是应该被忘记的”这个问题在文件系统范式里还没有一个好的答案。

第三，安全是一个被低估的问题。 ClawHavoc
攻击事件（2026 年 1 月）展示了文件系统访问权限被恶意 skill
利用的真实风险：攻击者通过 ClawHub 上的恶意 skill，读取 agent 的
~/.clawdbot/.env、SSH
密钥、浏览器密码和加密货币钱包文件。文件系统 + shell + 代码执行 =
巨大的攻击面。AgentFS 的 copy-on-write 隔离能防止 agent
破坏宿主环境，但它不能防止 agent 被 prompt injection
引导去读取不该读的文件。Simon
Willison 的总结一针见血：“The word safe is doing a lot of
work”。

第四，MCP 的未来是什么。 Anthropic 同时是 MCP
的创造者和文件系统方案的主要推动者。这造成了一个解读上的分裂：Daniel
Miessler 认为 MCP 被”降级成了服务目录”。Cloudflare
的工程团队独立得出了相同结论并称之为 “Code Mode”。David Mohl
则持反对意见，认为”Skills 是手册，MCP
是连接器”，两者需要配合使用。

最可能的走向是分化：MCP
成为控制平面（负责认证、发现、传输），文件系统/代码 API
成为数据平面（负责执行和交互）。MCP daemon
把远程工具”挂载”为本地文件系统，agent 和文件系统交互，底层 daemon
把文件读写翻译成 MCP 协议消息。Anthropic
的文章原文也说得很清楚：“MCP provides a foundational
protocol”——它只是说应该给这个协议加一个文件系统层，不是说这个协议要被替换。

## 什么样的架构会胜出

综合来看，最有可能的未来架构是分层的：

最底层是
连接层（MCP/connector），负责认证、远程访问、策略执行。这层是
MCP 的真正价值。

中间层是 状态层（SQLite-backed virtual FS），类似 AgentFS 的模式。提供 POSIX
接口给 agent 操作，背后是结构化的持久化存储。agent
得到的是它最熟悉的文件系统界面，开发者得到的是可查询、可回滚、可审计的数据层。这一层的关键是”文件系统和数据库不是二选一”——SQLite
自然可以做两者的桥梁。

最上层是 行为层（Skills/filesystem
code），用代码和指令文件表达 agent
应该如何完成特定任务。这层目前由 Anthropic 的 Agent Skills
标准主导，已经被多个平台采纳。

这个分层架构没有单一的设计者。它是多家团队从不同出发点、经过多轮迭代后收敛到的结构。Manus
做了 5 次重写，每次都在调 context 和文件系统的关系。Anthropic 从 MCP
出发，在半年内从”直接 tool
calling”走到了”通过文件系统发现和调用工具”。Vercel 从 sandbox
出发，发现纯代码执行 + 文件系统已经足够覆盖大量用例。

## 最后，“苦涩的教训”提醒了我们什么

Manus
的创始人 Peak Ji 在博客的最后提到一个判断：agent 的 harness
可能会限制模型的进步。如果换更强的模型 agent 表现没有提升，说明 harness
在拖后腿。每次模型能力跨过新门槛，之前的 harness
结构都需要重新审视。Manus 从 3 月到写博客时的 7 月做了 5
次完整重写。

文件系统是一个足够古老的抽象。它够通用，比定制的 tool calling
格式更有希望”活过”几代模型进步。但它也不是通用的。Vercel
的对比评估已经说明结构化的数据查询明显需要 SQL。LlamaIndex
也指出大规模的非结构化检索明显需要索引层。验证、安全、GC
这些在数据库领域已经解决几十年的问题，在 agent
文件系统的架构里被重新引入了。

从记忆到文件系统，这个迁移的实质不是”哪个技术更好”。它是一个约束条件的转移：当
context
成本成为瓶颈时，任何能减少它的方案都会胜出。代价是失去语义容错性，引入新的安全面和运维负担。下一轮瓶颈很可能是验证和信任——文件系统上的内容是否可靠，agent
生成的文件是否准确，跨 session
的状态是否一致。这些问题，目前还没有任何一个 agent
文件系统产品给出完整的答案。

## 鸭哥每日手记

日更的深度AI新闻和分析

订阅

Built with Kit

🔊

Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a>