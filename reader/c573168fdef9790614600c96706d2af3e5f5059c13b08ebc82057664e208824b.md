---
layout: post.njk
source: https://yage.ai/share/ai-coding-revertability-survey-20260622.html
speaker: yage.ai
title: 让 AI 更准，还是让错误更便宜
date: '2026-06-22'
summary: 文章探讨了 AI 编程工具在可靠性上的两种核心哲学路线：一是追求模型准确率，让 AI 更准；二是降低错误成本，通过提供强大的回滚能力来应对必然的错误。文章分析了 Replit 和 Claude Code 等厂商在实现这两种策略上的不同路径，指出可回滚性是决定用户敢于让 AI 进行大胆探索的前置条件，并对比了 Git-first 与 Snapshot-first 的工程路线。
area: tech-engineering
category: ai-application
tags:
  - rollback-mechanism
  - coding-agent
  - reliability-metrics
  - git-integration
people: []
companies_orgs:
  - Anthropic
  - Replit
  - OpenAI
products_models:
  - Opus 4.8
  - Cursor
  - Claude Code
media_books: []
draft: true
status: evergreen
---

## 让 AI 更准，还是让错误更便宜

AI 一轮改 14 个文件，你来不及看
diff，跑起来发现走错了方向。这时候怎么退回去。

这个问题在 AI 编程工具的 benchmark
榜单上看不见，但它决定了一个更根本的东西：用户敢不敢让 AI
放手做。回退能力不是错误发生后的补救，是决定用户让 AI
做多少事的前置条件。回退便宜，探索就大胆；回退昂贵，每一次放手都要反复犹豫。

AI 编程工具的安全叙事，在这个问题周围分出了两条路。

一条路在追问怎么让 AI 更准，准到不需要回滚。这条路的主力是
Anthropic，Opus 4.8 发布时焦点放在 honesty
指标上：模型放任自己写的代码里的缺陷不被注意到的概率，比上一代低了大约四倍（来源）。从
benchmark 上看这条路势头极强：多个模型已经把 SWE-bench Verified 的
resolved rate 推到了 93.9%，OpenAI 随后发博客说这个 benchmark
已经不再能测量前沿编码能力（来源）。行业的回应是造新
benchmark，继续在同一个维度上往难了做。

另一条路追问的是另一个前提：AI
一定会错，只是不知道什么时候错，那就让出错的代价尽可能低。这条路目前只有一个厂商在显式地、系统性地站台。Replit
CEO Amjad Masad 在 2025 年 12 月转发 Replit 的 Snapshot Engine
技术博客时，把核心哲学写得直截了当：编程 agent
一定会犯错，所以它们必须跑在让每一个操作都可以逆转的基础设施上（来源）。回滚属于基础设施层的设计约束，不该等到事故发生了才想起来做。

两条路的分歧在定义层面：一边用正确率来定义可靠性，另一边用恢复能力来定义可靠性。

## Replit 把回滚做成了安全哲学

Replit 的回滚系统有两层，演化路线明确。2022 年的 File History
是字符级 OT 记录，解决一个人改坏一个文件的小问题（来源）。2024 年 9 月
Checkpoints & Rollbacks 随 Agent 上线（来源），2025
年 5 月升级为 App History / Time Travel，覆盖范围从文件代码扩展到 AI
对话上下文、Agent memory
和环境变量副本，把代码和环境等所有副作用的回滚做进了同一套机制。

这些工程能力没有停在实现层。Amjad Masad 在 Possible.fm
播客里用电子游戏做类比：存档和读档是探索游戏的重要部分，不该让玩家走错一步就从头再来；Replit
要让用户感觉任何操作都能逆转（来源）。存档读档本身就是探索机制。你往前探了一步，知道探错了能退回来，所以才敢探下一步。挪到
AI
编程里，回滚不在错误发生后才生效，从上手的第一个动作起就在改变用户行为。

Replit
为什么是唯一把这条路走到底的厂商，答案在它的市场定位和产品形态里。Replit
的目标用户是非程序员，用自然语言让 Agent 搭 app 的人。Amjad Masad 在
2025 年初公开说过 Replit 不再以职业程序员为目标（来源）。这个人群看不懂
diff，不会用 git，也没有能力在 AI
改坏代码后手动恢复。对他们来说，回滚不是便利功能，是唯一的安全网。准确性指标对这群人没有意义：他们连代码都看不懂，benchmark
刷到 93.9% 和 73% 之间的差别他们感知不到。但”AI 把我的 app
改坏了能不能退回去”他们一秒就能感知到。

产品形态是第二个原因。Replit
是全栈托管环境，编辑器、运行时、数据库、部署都在它里面。Amjad 在 Sequoia
播客里说 Replit 要做的是”你构建软件需要采用的最后一个工具”（来源）。因为它托管了一切，所以它能
snapshot 一切。Cursor 和 Claude Code
只碰代码文件，碰不到数据库和运行时状态，想做 Replit
那样的全状态回滚也做不了，它们不在那条信息链路上。回滚做到基础设施层，前提是你得拥有那层基础设施。

第三个原因是事故倒逼。2025 年 7 月 Replit Agent 在投资人 Jason Lemkin
的 SaaStr app 里执行了破坏性操作，Amjad Masad 公开致歉，随后的产品更新里
Checkpoints & Rollbacks 排在四项安全举措的首位（来源）。checkpoint
功能在事故之前就有，但事故把它从一个默认存在的功能升成了显式的安全叙事。Replit
没有主动选择 revertability
作为卖点，是它的用户群体和产品形态决定了它没有别的牌可打：你不能让非程序员去读
diff 判断 AI 改得对不对，你只能让他们知道改坏了能退。

Replit 的 checkpoint 策略沿用了这个思路。checkpoint 由 Agent
自动在逻辑里程碑创建，存在 git 层，用户可以用 git
工具访问，但设计上不要求用户懂 git（来源）。这划出了
Replit 路线和 git-first 路线的边界：git
管底下的存储，用户在上层看到的始终是一道更薄的抽象，走到哪了自动存，想回退点一下。

## Claude Code
的回滚是社区逼出来的

Claude Code 在 v2.0.0（2025 年 9 月下旬）加入了 /rewind
命令，触发方式是双击 Esc 或输入 /rewind。每次 Claude
响应完成后自动对修改过的文件做 snapshot，每个 session 上限 100
个。提供四种回滚模式：Restore Code and Conversation、Restore
Conversation Only、Restore Code Only，以及 Summarize from Here（来源）。有独立文档页，投入了工程资源。

限制同样写在文档里。/rewind 不追踪 bash
命令产生的文件变化、手动编辑、外部工具修改。跨 session 也不能
rewind。把这几条放到一起，bash 命令恰是 Agent
执行高风险操作的主渠道，而跨 session 不能 rewind
意味着把一次探索拆成两次会话时，回滚安全网自动失活了。

GitHub issue #6001 的标题直白：Feature Request: Native
Undo/Checkpoint/Restore Functionality（来源）。提出者的诉求写得像用户研究摘要，那句
game-changer for user trust 在开头已经引过了。同一 issue
里还有另一句批评同样到位：这种核心的安全和可用性功能应该是工具里的一等公民，而不是丢给高级用户自己拿
hooks 拼的 DIY 项目。

这句话的锋芒指向 Anthropic 给 /rewind 的定位。Anthropic 把 /rewind
当工程功能来发布，没有把它提到安全哲学的高度。没有新闻稿，没有高管把它拉到和
honesty
指标同等的位置，没有一篇博客去论证让用户能回滚和让模型更准确是两种并列的安全策略。拿
Opus 4.8 发布博客里对 honesty 的大段铺陈来对照，/rewind
整件事停在了文档层。Reddit
社区给了一个更敏锐的信号：一位用户把帖子标题写成 PLEASE WE NEED REVERT
FEATURE（来源），全大写，像在喊。

社区没有等着。三个第三方工具各自从一个 gap 切入。ccundo 读取 Claude
Code 的 session jsonl 文件，覆盖 6 种文件操作的 undo，但 bash
命令仍需人工处理（来源）。mrq
直接把自己的定位写为 continuous protection between
commits，抓到的核心矛盾是：用户不会在 flow 中间停下来 commit，而 git
的保护只在 commit 之后才启动（来源）。claude-file-recovery
从 ~/.claude session 日志里提取曾经读过、编辑过或写过的文件，在 Hacker
News 上拿了 99 points（来源）。这几个工具的存在本身比它们各自的能力更能说明问题：它们共同指向了一个事实，/rewind
的覆盖范围在设计层面就有缺口。

## 光靠 git，接不住 AI
的修改节奏

剩下四家可以按工程路线分成两类。

Aider 是 git-first 路线最纯粹的实现。每次 AI 编辑文件后自动 git
commit，commit message 由 weak model 生成，/undo 就是 git reset（来源）。Aider 首页把 Git
integration 列为核心特性：用熟悉的 git 工具轻松 diff、管理和撤销 AI
的改动（来源）。作者 Paul Gauthier
没有写过为什么选 git 而不是 snapshot 的哲学文章，但 Aider 从第一天起就把
auto-commit 配 git 集成作为设计的骨架。优势直白：透明、可
push、零额外存储。劣势同样明确：不回滚对话，对非 git
用户有天然门槛。

snapshot-first 路线下有三家，宣传力度差异显著。Cursor 在每条 chat
request 处理前自动 snapshot，hover 到历史消息点 restore
按钮回滚，不单独宣传这个功能，社区反馈按钮会失效，恢复粒度过粗（来源）。Windsurf（Cascade）机制类似，多了
named checkpoint，Wave 11 blog 作为亮点宣传过，但 revert 不可逆（来源；来源）。Cline
在这三家里面最接近把回滚当一等功能来做：独立的 shadow git 仓库，每次
tool use 后 commit，粒度比 Cursor 和 Windsurf
都细，提供三选一回滚（只文件、只对话、两者），也是唯一把文件回滚和对话回滚解耦的（来源）。代价出现在规模上：有用户遇到了
262GB 的 .git/objects/pack（来源）。

放平了看，Replit 走的是中间路线，Cline
是最接近但没有站上叙事台面的第二名，其余三家要么有实现缺宣传，要么有宣传缺深度。

AI 编程工具回滚机制横向对比

用 git
就行了，这是这个领域里传播最广的反方论点。它有道理，但至少有三个现实漏洞。

第一个，git 的 commit 节奏和 AI 的迭代速度接不上。开发者在 flow
里不会停下来 commit。mrq 那篇博客的标题抓的正是这个错位。git 保护的是你
commit 过的内容，但 AI 每次编辑之间那几十秒的中间状态，git
完全看不见。issue #6001
那位批评者说透了：回滚应当是一等公民功能，不该是让高级用户拿 hooks
自己拼出来的二手方案。

第二个，git 的 commit 是人的有意动作，AI
编码需要系统自动的细粒度快照。git
的工作流一直围绕一个前提设计：你知道什么时候该 commit、你知道 commit
了什么。AI 编码推翻了这个前提。用户不知道 AI 在几十次 tool use
里动了哪些文件、改了哪些逻辑，自然也不知道该在哪一步按下 git
commit。事后去看 git log，commit
之间那些沟壑里全是用户回不去的中间态。Cline 的 shadow git
是一个解法，但它用 git 的方式已经偏离了 git 的设计原意。把 git
逼成一个自动 snapshot 引擎，262GB 的 pack 文件是 git
在被迫做它不擅长的事的直接后果。

第三个，git 对非程序员的门槛太高。GitHub 联合创始人 Scott Chacon 在
a16z 播客里承认 git 的 UI 自 2005
年几乎没有变过，团队正在重新设计版本控制以适配 AI agent 工作流（来源）。The
Register 2026 年 5 月的标题更干脆：Git is unprepared for the AI coding
tsunami（来源）。在
Cline 的 shadow git 胀到 262GB
这个背景下，这句话读起来不再像夸张的标题。

## Benchmark
的计分板上看不到回滚

主流 AI coding benchmark 没有一个测量可回滚性。SWE-bench 的核心指标是
resolved rate，patch 是否通过原始 PR 的单元测试（来源）。LiveCodeBench
测 Pass@1。Aider leaderboard 测 Pass rate 1 和 Pass rate 2（来源）。AgentBench 测
task success rate。即便有 pass@3 这种 undo-and-retry
变体，它测的仍然是模型最终有没有做对，从未触及做错之后的恢复过程。这像测一辆车的油耗和加速，制动距离完全不在计分板上。

学术研究也敲了 benchmark 的信号质量。ICSE 2026 的一篇论文发现
SWE-bench 的 patch 验证有 7.8% 的假阳性，标记为 resolved
不代表真的正确解决了（来源）。整个
benchmark 文化仍然围绕这个有缺陷的指标在转。

Amjad Masad 在 2025 年 7 月转述了一位上市公司 CEO 的观察：AI
确实生成了他们大量的代码，但生成代码省下的时间，全都赔回了调试、回滚 bug
和安全审计里（来源）。这句话点出了
benchmark 和工程现实之间的断层：benchmark
捕捉的是代码生成效率，而实际工作里真正的成本消耗在调试、回滚和安全审计上。AI
帮你省掉的编写时间，可能在一次事故里加倍赔回来。

SWE-bench 冲到 93.9% 的饱和信号已经足够强烈，OpenAI
率先声明不再以它作为评测标准。行业的回应是启动新的
benchmark，去测量更难的任务。新 benchmark
测量的是什么呢。还是正确率，只是换了一批更难的题。可回滚性作为一个评测维度，在整套
benchmark
体系里依然完全不可见。这暴露了行业对可靠性的理解起点：它只选择测量正确率，完全放弃了恢复能力这个维度。

## 两种信任，一种选边

两条路线背后是两种信任模型。

准确性路线把信任建在 AI
能力上。模型越强越可信，一次做对就不需要回滚。这个逻辑在直觉上成立，谁不希望
AI
一次做对呢。但它的鲁棒性有一个脆弱的断面：模型一错就无计可施，用户只能站着等下一个版本。

可回滚路线把信任建在人的恢复能力上。回退越容易越敢让 AI 试，AI
错了人能拉回来。这条路线的核心变量是错误成本：AI
错了之后，纠正的代价有多大，能不能降到用户可以随手兜底的程度。自动驾驶领域有一个对应的参照：SAE
Level 3 的安全假设就是人能随时接管，系统不需要永远做对（来源）。AI
编程工具和 L3
自动驾驶在安全结构上是同构的，两者都是高自主性、高代价错误、人类仍在回路中的系统。学术文献里区分了
overtrust（导致 misuse）和 undertrust（导致 disuse），强调 calibrated
trust 是目标（来源）。但这些研究的默认前提始终是信任落在
AI 这一侧，把 AI
校准到用户既不过信也不低用的那个点上。可回滚路线的信任落点不同：它倚靠的是用户自己能兜底的能力。

回退能力是一个放大器。issue #6001 里那句 empower users to let Claude
attempt more ambitious tasks, knowing they can easily roll back
已经把关键点了出来。因为知道能一键恢复，用户就敢让 Agent
去试那些一次做对概率不高、但做成之后价值巨大的事。回滚压低了探索的代价，代价降低本身就是行为激励。

这条路仍在早期，每个实现都带着清晰的限定。Replit 的 checkpoint 粒度由
Agent 决定，用户想回到哪一个具体状态上面去不完全自己说了算。Cline 的
shadow git 能胀到 262GB。Aider 不能回滚对话。Claude Code 的 /rewind
不追踪 bash 命令。Snapshot Engine 的技术博客里能看到 Replit
在存储效率上下了硬功夫，但也承认目前的回滚精度仍有工程取舍（来源）。这些限定说明了路线目前的位置：从概念走到产品化，中间要穿过几道工程窄门，每一道都还亮着。

方向已经清楚。AI
编程工具的可靠性需要两个维度并行：让模型更准，也让错误更便宜。两个维度不互斥，各自需要独立的工程投入。今天只有一个厂商在显式地、系统性地投入后一个维度，而用户的反馈、社区的补丁工具、加上
issue #6001 这样的原声，正在证明这个维度已经变成了前置条件。