---
layout: post.njk
source: https://yage.ai/share/cursor-agent-harness-evaluation-first-20260501.html
speaker: yage.ai
title: |-
  Evaluation-First：Cursor 这篇 Agent Harness
  文章真正值得读的地方
date: '2026-05-01'
summary: Cursor的文章强调了“evaluation-first”在Agent Harness持续改进中的核心作用。文章阐述了如何通过定义北极星指标、诊断指标，利用CursorBench等数据集和标准化的决策协议，来驱动AI产品开发中的每一次变更。同时，作者提出了“停止和拒绝”作为评估的第四维度，并分析了Cursor在上下文策略、模型适配、成本优化等方面的具体实践，指出评估系统是应对Agent平台复杂性增长和任务难度提升的必要条件。
area: tech-engineering
category: software-development
tags:
  - agent-harness
  - evaluation-first
  - ai-product-development
  - continuous-improvement
people:
  - Jer Crane
companies_orgs:
  - Cursor
  - PocketOS
  - Railway
products_models:
  - Claude Opus 4.6
media_books: []
draft: true
status: evergreen
---

Cursor 今天发布了一篇关于 agent harness 持续改进的文章：Continually
improving our agent harness。只看标题和分节——context window
的演进、tool reliability 分类、多模型定制 harness、mid-chat
switching——它读起来像一篇典型的工程博客，很多做法对关注 harness
engineering 的读者来说也不陌生，甚至就是自己在做的事。

换个读法，文章的重点会从这些做法本身，转向 Cursor
的决策方式：哪些做法该保留，哪些该撤掉，哪些要按模型重写。比如，几周前为了弥补模型能力加上的静态
guardrail，现在模型变强后能不能删？新模型接入时，是沿用旧工具格式，还是为它单独改
harness？更贵的 summarization model
带来的是质量提升，还是只增加成本？这些问题不能靠经验回答。Cursor
文章给出的线索是：它用同一套 evaluation
流程给这些决策提供依据。这条线比具体技巧更值得读。它要应对的困境也不只属于
Cursor。

这就是 evaluation-first
的思路：先定义什么叫做好，用实验验证每个假设，再决定是否全面部署。读这篇文章时，与其盯着某个
harness 技巧，不如看它如何让 evaluation system
参与每一次变化。CursorBench 承担离线回归，线上 A/B
实验承担真实使用验证；两条线合在一起，让每次改进可观测、可回归、可验证。少了这套系统，harness
改进只能靠直觉。

3 月中旬 Cursor 公开 CursorBench 时，我们写过一篇调研：CursorBench
调研：当 Benchmark 遇见现实，讨论 benchmark 在 agent
产品里的角色。那时 CursorBench 给人的印象还是一个评估不同模型在 Cursor
环境里表现的工具。这次 harness 文章把问题推进了一层：evaluation
不再只用于模型选择，它开始进入产品运营的核心，驱动上下文策略、工具可靠性、新模型适配和日志回溯。同期我们也写过工程视角的总结：Harness
Engineering：当人类从写代码转向设计 Agent
的工作环境，讨论当人类从写代码转向设计 agent
的工作环境时，文档、约束、反馈回路和验证基础设施比 prompt trick
更重要。Cursor 这篇正好是那个判断的一个具体实例。

## Evaluation
三组件：metric、dataset、protocol

如果问 Cursor 的 evaluation system
由什么构成，可以分解成三个层次：metric（怎么定义好）、dataset（用什么场景测）、protocol（metric
如何进入决策循环）。

### 指标的分工：north-star 和
diagnostic

先说 metric。Cursor 把指标分成两类，这个分类比指标本身更有价值。

第一类是贴近用户质量的 north-star 指标。其中最有意思的是 Keep
Rate——agent
生成的代码，在固定时间后还有多少比例留在用户代码库里。如果用户反复要求
agent 修改同一段代码，或者手动回退、自己重写，那意味着 agent
做的事没有被真正采纳。Keep Rate
不直接问模型会不会写代码，它测的是用户行为：这段代码最后有没有留下。它是一个行为指标，不是能力指标。正因如此，它比那些问模型有没有通过某项测试的检测更接近真实价值。

另一个 north-star 是语义级别的用户回应分析。Cursor 用语言模型读用户在
agent 输出后的回应：用户进入下一个 feature 开发是正信号，用户贴 stack
trace 是负信号。这里会引入 judge model
的误判，但它仍然提供了一个可持续追踪的方向信号。

第二类是 diagnostic 指标：latency、token efficiency、tool call
count、cache hit rate、tool error
rate。这些指标能提供方向，例如降低延迟、减少 token
消耗、提高缓存命中率，但它们不能单独证明 agent 做得好。一个 agent
可以极快地生成错误代码，也可以在低 token
消耗下反复做无用工具调用。诊断指标负责定位问题，north-star
负责定义质量。两者缺一不可：只有 north-star
没有诊断指标，团队面对质量变化时不知道问题出在哪；只有诊断指标没有
north-star，团队可能会把系统优化到效率极高但用户并不满意的状态。

### CursorBench 的位置

有了指标之后，还需要一个标准化的场景集合来稳定产生这些指标。CursorBench
承担的就是这个角色：提供离线、可复现、跨时间可比的 evaluation
读数，让团队在每天多次迭代中快速判断这次改动比上个月好还是差。

CursorBench 的一个关键属性容易被忽略：它测的是模型在 Cursor harness
里的表现，分数同时受模型能力和 harness 设计影响。对 Cursor
内部的产品迭代来说，这恰恰是它有价值的地方。团队真正需要知道的，是哪个模型在自己这套系统里表现更好。标准评测上的模型强弱只能作为参考；产品决策最终要优化的是系统表现。

这个属性同时划定了 CursorBench
的边界。它不能简单用作通用模型排行榜的依据。外部无法独立复现它的任务集合、评分标准和运行环境，理解
CursorBench 的结果时必须带这个上下文。

### Protocol：metric 如何进入决策

指标和数据集只是基础设施。要让它们进入工程决策，需要
protocol——一套固定的执行流程：提出假设、离线评估、线上
A/B、对比决策、上线或回滚。

Cursor 的 protocol 有三层。第一层是 offline eval，用 CursorBench
做快速回归。第二层是 online experiment，在生产环境中部署多个
variant，用真实用户行为做对比。第三层是 weekly
automation——每周自动运行一个具备 skill 的
agent，教它搜索日志、发现新问题或异常 spike，并在 backlog 中创建或更新
tickets。这套 automation 把线上日志转成可执行的 harness
修复任务，形成了从发现问题到修复再到验证的闭环。

没有 protocol 的 metric 只是数字。有了 protocol，metric 才能决定是否
ship、是否 rollback、是否该开 ticket。

### 第四维：停止和拒绝

讲完三组件之后，还剩一个问题：如果 evaluation system 只测量 agent
完成了多少任务，它就看不见 agent 在什么时候该主动停下来。

2026 年 4 月，PocketOS 创始人 Jer Crane 在 Cursor 中使用 Claude Opus
4.6 时，agent 遭遇了 staging 环境的凭证错位。它找到了一枚未被限制权限的
Railway API token，随后调用 volumeDelete
接口删除了生产数据库和卷级备份，整个过程大约 9
秒。事后它还自动生成了一段解释，承认自己在没有确认边界的情况下做了猜测并执行了破坏性操作。Railway
通过内部灾难备份恢复了数据并增加了安全措施。Crane 在 X
上报告了经过，The
Register 和 NeuralTrust
随后做了跟进。

这个案例的价值不在 AI 会犯错这个宽泛的判断上。它暴露的是当前 agent
evaluation 设计里一个没被定义的前提：CursorBench 和大多数 coding-agent
benchmark 默认 agent
应当尝试完成给定任务，然后在这个假设下测量代码写对没有、测试通过没有、keep
rate 是多少。这些指标衡量的是 agent 该动的时候动了多少，不衡量 agent
不该动的时候停没停。

危险也不只是模型越强越危险。能力较弱的模型可能连生产 API key
都找不到，任务自然失败，没有破坏。足够成熟的模型应当在发现凭证和任务权限不匹配时停下来、问用户。真正危险的是中间状态的模型：它有能力绕开障碍找到
token、拼出可执行的 API
调用，但还没有判断这样做对不对的意识。路上最危险的司机不是刚拿到驾照的新手，也不是开了十几年的老司机，而是刚开了两三年、觉得自己已经很熟的阶段——手法够用，判断还没跟上。PocketOS
事件里的 agent 正是这种状态：技术能力足以找到 token 并拼出 API
调用，判断能力却还停在有办法就要做这一层。

这个问题不能靠换一个更强的模型解决——PocketOS 事件里用的已经是 Claude
Opus
4.6。停止和拒绝是一个独立于代码生成能力的能力维度，需要被单独定义、单独测量。在
evaluation 框架里，这意味着在 metric、dataset、protocol
之外增加第四个维度：一套场景和评分方式，专门衡量 agent
在权限不明、目标模糊、操作不可逆时是否会停下来。评分上，回避率应当独立计算，不和任务完成率合并。一个代码生成表现平平但从不越权操作的
agent，比一个代码生成能力很强但偶尔删库的 agent 更值得部署。

工程上，这个维度可以从 protocol
的演进开始。线上每发生一次越权或破坏性操作相关的事件，离线 eval
集就在一个 sprint 内补充对应的 scenario。做法本身不复杂，但它要求
evaluation system 的设计者接受一件事：在 agent
产品里，有些任务的目标就是不做。

## 用 evaluation
重读 Cursor 的几个 harness 决策

把上面这套框架装回 Cursor 的工程场景里，每个决策的 evaluation
底色就更清晰了。

从静态 context 到动态 context discovery。
早期模型弱，Cursor 在 harness 里放了很多静态 context 和
guardrail：每次编辑后展示 lint 和 type
错误、改写太长的文件内容、限制单轮 tool call
的数量。随着模型变强，这些静态注入的内容被逐步撤掉，转向让 agent
在工作过程中自行决定需要什么信息。这个迁移需要回答一系列具体问题：撤掉
guardrail 后，质量掉了吗？token 消耗降了多少？错误率有没有上升？keep
rate 是变好还是变差？没有 evaluation，这些决策就没有依据。有了
evaluation，每一次护栏调整都能落在可核对的读数上。

新模型适配不是接通用接口就行。 Cursor
举的例子落在工具格式上：OpenAI 模型更熟悉 patch-based file edit
格式，因为训练数据里这种格式出现得多；Anthropic 模型更习惯 string
replacement。Cursor 为不同模型定制 tool format 和
prompt，甚至在同一模型的不同版本之间也做微调。评估对象不是模型本身，而是模型加
harness 的组合系统。新模型接入时，Cursor 从最接近的现有模型 harness
起步，跑 offline eval、让内部团队试用、调整
prompt，直到有信心推到线上。每一步都在问同一个问题：这个组合是否比现有的好。论文里的
benchmark 分数只能给一个起点，真正回答这个问题的是自身 evaluation suite
的读数。

成本优化：更贵的不一定更好。 Cursor
试过用更强的模型做 context
summarization，发现质量改善不明显，不值得额外成本。这是一个典型的
evaluation-first
决策场景：有成本诱惑（更贵的组件看起来更高级、应该更好），也有直觉压力（上下文总结的质量直接关系到
agent 能否在长对话中保持连贯）。但如果 north-star
指标没有显著变化，决策就清晰了——不换。缺乏 evaluation
的团队容易在这种场景里过度优化中间指标，比如总结的忠实度，而忽略最终用户感知的质量变化。

Tool reliability 的分类能力。 Cursor
把工具调用错误分成两类：unknown error 和 expected
error，后者再按原因拆分为
InvalidArguments、UnexpectedEnvironment、ProviderError、UserAborted、Timeout
等类别。更重要的是，它按 per-tool、per-model 建立
baseline，用异常检测发现真正的 spike。这个分类的价值在于：tool error
rate
上升可能有多种原因。模型变了可能改变调用模式，代码库规模变了可能影响工具行为，用户分布变了也可能改变使用频率。如果没有分类和
baseline，错误率上升只会触发一个笼统的告警，团队不知道从哪里开始排查。分类先把问题域缩小，anomaly
detection 再告诉团队这次是否真的异常。tool error rate
在这里像体温计——提示系统生病了，但不能自己诊断病因。

Mid-chat switching 和 subagent。
用户可能在对话中途切换模型，比如用 Claude 写完了一段核心逻辑，改用 GPT
继续开发另一个功能。切换时新模型要接管旧模型生成的对话历史，这对新模型来说是
out of distribution
的；而且不同模型使用的工具集可能不同，调用历史里出现过但当前模型不支持的工具会导致问题。Cursor
的做法是加 custom instructions
告知模型现在是在中途接管，并避免调用不属于当前工具集的工具。切换还会导致缓存失效，Cursor
用切换时总结对话来降低 cache penalty，但在复杂任务里 summary
可能丢细节。因此 Cursor 推荐复杂对话尽量保持一个模型，或用 subagent 的新
context
绕过这个问题。新架构能力会带来新的失败模式，评估问题也随之改变：除了能不能切，还要判断什么时候切比不切好。这个问题只有
evaluation 能回答。

## 结尾

回到开头那些日常问题：新模型要不要接、旧 guardrail 要不要撤、更贵的
summarizer 值不值得。它们不会消失，反而会随着 agent
平台的能力提升变得更多、更复杂。这些问题没有放之四海皆准的正确答案，但可以通过一套
evaluation system 持续得到更好的判断信号。

这套信号不需要一开始就完美。Cursor 的做法——定义 north-star
指标、建立标准任务集、用固定 protocol
把测量变成决策节奏——背后的框架是可迁移的：先想清楚什么叫做好，再找到贴近真实使用的场景去测，然后把测量结果固定进发布决策。规模小的团队可以从人工记录和定期
review 开始，核心是建立这个循环，而不是一步到位复制 Cursor
的基础设施。

当然也要说清楚文章本身的局限。它是厂商自述，不是第三方审计——Keep Rate
的具体数值、A/B 实验的样本量、CursorBench
的全量任务和评分机制都没有公开。我们讨论的是方法论的合理性，不是效果的可验证性。每个
metric 也都有自己的失效场景：Keep Rate
在大型项目中可能受限于用户注意力而非质量，Semantic follow-up
面对简短回应时信号不足。但这些局限不改 evaluation
的优先级——它在上升，而不是下降。

背后的原因不止是 agent 平台变复杂了。更根本的是，agent
正在被派去做更困难的任务，涉及的领域我们自身可能并不完全精通。传统工程中，一段代码改得好不好，编译是否通过、测试是否绿色、线上延迟有没有上升——这些信号明确且可观测。agent
生成的代码则不同：bug
可能藏在自动生成的逻辑里，直到最终用户的运行环境中才暴露。可观测性在变差，任务难度在上升。这两个趋势合在一起，让
evaluation 不再是锦上添花，而是维持产品可信度的必要条件。

两周一更新的模型能力、越来越长的 context window、越来越丰富的 tool
ecosystem——agent
平台的组件在持续变化。但变化越快，越需要一套不变的方法去回答三个问题：什么叫做好？哪个改动真的变好？坏在哪里？Cursor
这篇文章的价值在于它把这件事讲具体了：evaluation
正在从测试团队的附属工作，变成 agent 产品工程的主线。