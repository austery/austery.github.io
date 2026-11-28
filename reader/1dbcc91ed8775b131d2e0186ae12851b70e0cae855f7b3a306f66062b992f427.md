---
layout: post.njk
source: https://yage.ai/share/harness-canonical-form-20260418.html
speaker: yage.ai
title: Harness 的标准化：一个不会到来的标准
date: '2026-04-18'
summary: 文章认为，AI agentic 领域的“harness”运行时层，因厂商间的商业竞争和产品差异化需求，难以实现类似 Chat Completions 的统一标准。厂商各自构建专有运行时，导致技术分叉。真正的标准化趋势体现在运行时层的上下游：下层是极简的命令行接口，上层是 AGENTS.md 等通用协议，而运行时层本身将是各家厂商竞争的主战场。
area: tech-engineering
category: software-development
tags:
  - agentic-ai
  - runtime-layer
  - standardization
  - ai-integration
  - business-strategy
people:
  - Sean Goedecke
  - Matt Mayer
companies_orgs:
  - OpenAI
  - Cursor
  - Anthropic
  - Linux Foundation
products_models:
  - Chat Completions
  - Claude Code
  - Codex CLI
  - Cursor Agent
  - Responses API
  - MCP
  - AGENTS.md
  - Claude Opus
media_books: []
draft: true
status: evergreen
---

现在 agentic AI 领域有一批产品看起来在做同一件事。Claude Code、Codex
CLI、Cursor、OpenCode、Responses API、OpenClaw、微软的 Copilot
系列，都是接一个大模型，加一个工具调用循环，再管一套运行时状态。自然的问题是：这些东西会不会像当年的
Chat Completions
那样，最后收敛成一个统一标准，开发者写一遍就能到处跑？

我的判断是不会。这篇想说清楚为什么。重点不是技术上做不到，而是这件事的商业逻辑本来就不通。

## Chat Completions
当年为什么能成为标准

先回头看看 Chat Completions 这个标准是怎么来的。

OpenAI 最早把 chat completion 的接口设计得很简单。输入一个 messages
数组，输出一条
message，无状态，没有副作用，调完就结束。正是这种简单，让每一家厂商都能照着实现一份，哪怕背后的模型完全不同，对外的接口也可以做得一模一样。到
2026 年，超过八成的新模型服务商上线时都会默认暴露一个 /chat/completions
端点。DeepSeek、Kimi、GLM、Qwen、Mistral，一家都没落下。这是目前 LLM
生态里覆盖面最广的事实标准。

它能走到这一步靠两个条件。一是那个时代所有智能都在模型内部，接口只负责把字符串送进去、再把字符串拿出来，不承担额外的语义。二是厂商没有动机在接口上做差异化。自家的护城河在模型里，接口越通用、用户越容易用上自家模型，对自己就越有利。

这两个条件现在都不成立了。要看清楚为什么，先得搞清楚 harness
到底在做什么。

## Harness 属于运行时层

我之前在 Claude Code
作为运行时 那篇文章里把 AI
集成分成了四层。简单复述：模型层决定用哪个大模型，协议层决定怎么调它，运行时层决定状态怎么管、工具怎么调、上下文怎么组织，契约层决定什么算做完。

AI 集成四层架构

Chat Completions
属于协议层。那个年代协议层可以很简单，是因为运行时和契约这两层都由应用自己实现，协议本身只传字符串。

Harness 属于哪一层？属于运行时层。Claude Code 的价值不在它怎么发 HTTP
请求，而在它怎么管对话上下文：什么时候压缩历史、在哪里放 prompt cache
的断点、tool 调用要不要先问用户、前缀怎么保持稳定让缓存命中率不降。Codex
CLI 的价值不在它的协议实现，而在它的沙箱设计、AGENTS.md 的组装方式、子
agent 之间的状态怎么传。Cursor Agent 的价值不在它接了哪家模型，而在它把
IDE 里的上下文和 agent 的指令放进同一个界面的做法。

协议层和运行时层有一个关键差别。协议层的复杂度有上限，就那么几条消息传递规则，实现空间很窄。运行时层的复杂度没有上限。光一个上下文管理，就能再分出压缩策略、缓存断点、子
agent 边界、工具 schema
组织、状态序列化几十个子问题，每一个子问题都有好几种做法都说得通。

所以问题就变成了：运行时层能不能像协议层那样收敛到一种公共形态上？

## 各家解的根本就不是同一个问题

2026 年第一季度发生了一件事。OpenAI、Cursor、Anthropic
三家几乎同时发了各自的 harness
engineering 文章，用词高度一致，讲的却是三件几乎不相干的工程。

Anthropic 在解决一个 agent 怎么连续跑四小时还不走偏的问题。Cursor
在解决几百个 agent 同时开工怎么不互相干扰的问题。OpenAI 的 Symphony
在解决人怎么用最少的介入调度一大片 agent
的问题。三家共用一个词，背后是三种完全不同的产品压力。

这种分叉顺着传到了每家的设计里。Claude Code
的对话压缩策略、八层防仿冒机制、thinking 签名绑定 API
key，都是围绕着长会话不漂移这件事做的。Cursor 的递归 Planner-Worker
架构、worker
之间互相隔离、允许一个小而稳定的错误率，都是围绕着并行吞吐量做的。Codex
的 App Server 协议、Thread/Turn/Item 原语、内核级沙箱，都是围绕着同一个
agent 核心要接到 TUI、IDE、网页、Xcode 各种界面上去做的。

用户在不同场景需要的也是不一样的东西。长写作和深度思考最依赖长会话能力，所以
Claude Code 在这类任务上表现好。批量发 PR 和团队协作最依赖并行规模，所以
Cursor 和 Symphony
在企业里用得多。跨设备的零门槛入口最依赖人机协同的顺畅度，所以 OpenClaw
和 Dispatch 在普通用户里火。你今天要做 A，明天要做 B，两个 harness
的能力就是没法互相替代。这是一个人会同时用几个 harness
的原因，也是它们合不起来的原因。

三家厂商用同一个词做三件事，这件事本身就说明运行时层没有一个公认的问题定义。没有公认的问题，就没有公认的答案，所谓统一形态也就无从谈起。

## 每一项运行时设计都是一份双面合同

运行时层上的每一项设计，都同时在干两件事：提供技术能力，建立商业壁垒。

Claude Code 的源码泄露把这件事讲得很清楚。泄露代码里可以看到它有 八层防仿冒机制：Zig
写的原生客户端认证、故意植入的假 tool 用来反蒸馏、thinking 内容签名绑定
API key、识别中间代理网关，等等。这一整套机制的作用，是让 Claude Code 在
API
这一端有一个官方身份，第三方仿冒或者中间代理走过来都能被服务端认出来。2026
年 3 月 21 日 Anthropic 直接切掉了第三方 harness 的 OAuth
登录通道，所有第三方工具想用 Claude 都得走 API 付费。这之后 Kimi、GLM
还想接进 Claude
Code，只能走绕弯子的兼容办法，用户想在一个会话里切换模型服务商都很不方便。

同一事实换到 Responses API
上看，不必靠源码泄露也能从接口设计里读出来。Sean Goedecke 分析过，这个
API 做成有状态的，真正用意是把 reasoning trace
藏在服务端。客户端只能拿到一个
previous_response_id，看不见完整的推理链。对 OpenAI
来说这是合理的商业选择，要保护自家模型的推理能力不被蒸馏走。但这个动作同时也让第三方服务商没法真正兼容
Responses API，因为兼容就等于帮 OpenAI 一起把 CoT 藏起来。到 2026 年 4
月，Responses API 的第三方兼容名单就只有 Amazon Bedrock
一家，再加几个聚合层。对比 Chat Completions
那边八成主流服务商都跟进的情况，差了整整两个数量级。

Matt
Mayer 做过一组实测。同一个 Claude Opus，在 Claude Code 里跑
SWE-bench 拿 77%，在 Cursor 里跑拿 93%。两种 harness 差出 16
个百分点，而且这回不是 Claude Code 赢。这组数字的含义很直接：harness
对结果的影响大到一代模型升级的量级，厂商有充分动机把这种影响做成自家的差异化卖点。当
harness
本身就能决定这么大的性能差距，它就从一个可共享的基础设施，变成了一个产品竞争维度。

协议层上的机制只管通信，所以可以共享。运行时层上的机制一手管能力、一手管护城河，就无法共享。这不是愿不愿意的问题，是只要一共享就会撞上自家的商业逻辑。

## 协议层的跨厂商统一，同样在松动

前面讲的是运行时层。协议层这边的局面也在变化，MCP
的遭遇就是一个完整的例子。

MCP 是 Anthropic 2024 年底提出的工具调用协议，位置和 Chat Completions
类似，希望在协议层做一个简单标准，让各家厂商都来接。采用面的数字很好看。SDK
的月下载量从 2025 年初的约 10 万涨到 2026 年 3 月的 9700 万，PulseMCP
上列了 8600 多个公共 server，财富 500 强里大概 28%
的公司已经在自家系统里跑 MCP server，Linux Foundation 2025
年底接过了治理。

这些数字主要反映采用面；往下看各家实际怎么接
MCP，分歧早就写进实现了。OpenAI 的 Apps SDK 在 2025 年
10 月扩展了 MCP，加了一个叫 _meta 的域，用来绕开大模型的 context
window，直接把 GUI 状态传给前端。这个做法违反了 MCP
原本的核心设计：所有信息交换都应该经过大模型可见的
context。但从工程角度讲它有道理，往 context 里塞十几 KB 的 HTML
会污染推理、抬高成本、让成功率掉下去。_meta 后来被 OpenAI 做成了正式的
openai/* 扩展路径，任何深度用到 Apps SDK 的 MCP server，在 Anthropic
或者别家宿主环境里都跑不通。

其他层面也在分裂。stdio 传输被废弃、往 streamable HTTP
迁移的过程里出了不兼容改动，已经上线的企业 server 得重写传输层。OAuth
2.1 的引入带出了一连串 CVE 和 localhost
相关的攻击面，为修漏洞又引入了新的不兼容改动。Kiro CLI 对部分 MCP server
的兼容性已经有实测故障，Websets 的鉴权在跨宿主场景下失效。

飞书和钉钉 2026 年 3
月的选择把话讲得更直白。两家中国最大的企业协作平台，不到 24 小时内先后在
GitHub 开源了自己的命令行工具，钉钉覆盖了 10 项核心能力，飞书直接把
2500 多个 API 整理成了一套 CLI。两家都没有同步发布 MCP
server。平台方的选择已经说得很清楚：现在让 agent
接入平台能力，首选路径是命令行加 JSON 输出加 –help 当说明书，不是
MCP。

MCP 的处境说明一件事。就算是为 agentic
时代专门设计的协议，因为要承载的内容远比 Chat Completions
那种纯字符串复杂，跨厂商也很难再共用同一套规范。采用量这一侧还在往上走，各宿主上的实现却越来越不一致。

## 真正收敛的地方在运行时层的上面和下面

讲到这里可能会让人觉得 agentic
时代没有任何东西能标准化。这不是结论。准确的说法是：收敛正在发生，但发生在运行时层的上面和下面，不发生在运行时层本身。

最明显的一条是命令行作为事实接口。现在主流的 agent runtime 本身就跑在
shell 里。Claude Code、Codex、Cursor Agent
都是如此，它们最可靠、最低成本的动作就是读文件、写文件、执行命令。任何平台只要把自己的能力整理成一个命令行工具，加上
–json 输出和 –help 文档，任何 agent
都能拿来就用，不需要专门适配。这是一套极简约定，简单到几乎不算协议，就是
Unix 四十年前那套 stdin、stdout、exit
code。正因为简单到没有可差异化的地方，各家厂商也没有动力在上面做私有扩展，它自然就成了事实接口。飞书钉钉、Google
Workspace 实验性的 gws、香港大学的
CLI-Anything，都是同一条路径上的例子。

AGENTS.md 是另一条。2025 年 8 月由 OpenAI 发布，现在 6
万多个开源项目在用，Claude Code、Codex、Cursor、Windsurf、Aider、Gemini
CLI、Copilot、VS Code 等 16 家主流 harness 都支持从项目根目录读它。Linux
Foundation 的 Agentic AI Foundation 2025 年 12
月接过了治理。它统一的是文件名、位置，以及「agent
会去读这份文件」这个共识。它没有统一的是内容该怎么组织、什么时候注入、子目录和根目录的合并规则，以及怎么和
CLAUDE.md、.cursor/rules、.github/copilot-instructions.md
这些老格式共处。严格讲它更像一份社会契约而不是技术标准，但这已经是
agentic 时代覆盖面最广的协议层共识。

这两条事实接口有一个共同点：都不在运行时层。命令行加 JSON
属于协议层的最底下，简单到不承担状态管理。AGENTS.md
属于契约层的最上面，就是一份
markdown，不承担执行语义。它们一上一下夹在运行时层两侧，恰好落在各家都没有动力去做私有扩展的位置。

回头看看运行时层上那些想做标准的尝试，结局都差不多。Responses API
只有 Bedrock 一家第三方兼容。Claude Code 被 Anthropic 主动封闭。MCP
的采用量还在增长，但各家的实现已经分叉。Linux Foundation
的治理也没能拦住各家宿主在 MCP 之上再叠一层自家方言。

不是运行时层不重要。正相反，运行时层是这个时代最重要的一层。就因为它太重要，各家厂商把它当作主战场，没有一家有动力把它交出去做标准。

## 使用者和构建者各自该怎么办

对使用者来说，接受 harness
不会收敛这件事，然后把精力放在不同场景选哪一个 harness 上就行。Claude
Code
在长会话、长写作、长思考里的稳定性来自它对长会话这件事的工程投入。Cursor
Agent 在 IDE 内嵌场景的流畅度来自它对交互响应的设计。Codex CLI
的开源让它在需要深度改动的场景里有独特价值。OpenClaw、Dispatch
在零门槛入口上的探索对普通用户有价值。同时用几个 harness
并不是混乱，而是按场景在几种不同的可扩展能力之间做选择。

对构建者来说，一年前我写过一篇讲
agentic 框架的文章，核心是忘掉所有框架，从第一性原理出发自己搭
agent。2026 年这件事需要更新。现在不是忘不忘框架的问题了，agent
的主循环也不用自己写了，Claude Code、Codex、Cursor 这些 harness
已经把它做到了能直接复用的程度。真正需要避免的新误区是，不要对通用运行时抱有期待。没有任何一个运行时会变成事实标准，厂商的纵向整合只会越做越深。可以依赖的事实接口只剩两条：基于
shell 的命令行加 JSON，以及项目根目录的 AGENTS.md
和相关文档。除此以外的所有东西，状态怎么管、工具怎么调、子 agent
怎么协作、缓存怎么复用、上下文怎么压缩，都会在各家 harness
里被重新发明一遍。

在协议层做集成，可以跨厂商。在运行时层做产品，就得选一家绑深。这条边界比过去清楚，也比过去更重要。Chat
Completions 那种不用关心跑在谁家基础设施上的便利，在 agentic
时代换到了别的地方。