---
layout: post.njk
source: https://yage.ai/share/loop-engineering-senior-manager-20260630.html
speaker: yage.ai
title: |-
  Loop Engineering
  详解：从管理执行到设计自收敛的循环
date: '2026-06-30'
summary: 文章详细阐述了“Loop Engineering”的概念，它代表了从单纯的Prompt使用向设计自收敛的循环系统转变。核心在于将AI从执行者升级为“AI Manager”和“Senior Manager”，通过建立反馈闭环、可检验的评估机制（如evaluation harness、tracking UI）以及将经验沉淀为SOP等机制，构建一个能自我诊断、修正和优化的开发引擎。文章强调，评估的艺术是关键，AI时代的评估应从路径约束转向边界约束，而非依赖传统TDD模式。
area: tech-engineering
category: architecture
tags:
  - loop-engineering
  - ai-manager
  - system-design
  - evaluation-art
  - feedback-loop
people:
  - Addy Osmani
  - Boris Cherny
companies_orgs:
  - Anthropic
  - Business Insider
  - Elastic
products_models: []
media_books: []
draft: true
status: evergreen
---

最近在 AI 辅助开发领域，Loop Engineering 成为行业热词。Business
Insider 用 Forget
Prompts: “Loop Engineering” Is All the Rage Now 概括这波讨论，Addy
Osmani 随后写了更系统的定义性拆解。

我起初有些犹豫，迟迟没有动笔写这个话题。因为从实践角度来看，在前沿的开发者社区中，这属于常识。在我们的
AI Builders
课程中，这套关于反馈闭环与系统设计的方案已经讲授了一年多。

但这次把文章写出来，是因为这个词定义得较好，正适合作为线索，帮大家厘清底层本质。我们正好也可以结合课程中的部分内容，来分析如何真正用好这一范式。

从 Prompt 到 Loop
的跨越，核心在于两点：第一是思想的升维，第二是评估的艺术。

## 1. AI
Manager：从执行者到委派者的第一步

使用 AI
的第一步是建立管理思维。你需要从一名亲自写代码的执行者，转变为定义问题和把关结果的
AI Manager。Anthropic 对约 40 万条 Claude Code session
的研究也观察到，表现得像管理者的人更容易获得成功结果，研究脚注里的说法是
“perhaps
acting like a manager confers greater success”。

在这个阶段，我们可以将 AI
视为一个会失忆的实习生。要让这位实习生输出高质量的工作，管理者需要提供三个层面的支持：

AI Manager
需要同时提供上下文、问题边界和可检验终点

第一，提供自包含的上下文。由于大模型单次运行的无状态特征，它不了解项目背后的历史决策和隐性规则。你必须把这些背景知识整理成整洁的文档。

第二，定义清晰的问题边界。不给模糊的口头指令，而是用自然语言把任务的输入、输出以及限制条件描述清楚。

第三，先定义可客观检验的终点。这需要让 AI
明确知道什么时候算做完，以及做错时的具体表现。

尽管 AI Manager
的思路解决了大模型冷启动和猜测意图的问题，但在这个阶段，人类依然深度参与管理环。你需要不断拆任务、补背景、看中间结果、判断下一步，让
AI 沿着你的判断往前走。这种人肉管理环限制了系统的总体吞吐量。

## 2. Senior
Manager：把人类从执行环中解脱出来

手动管理存在瓶颈，但这个瓶颈已经不再是“把报错贴回给 AI”。现代 coding
agent 已经能自己写代码、运行验证、读取错误日志并继续 debug。Elastic
团队在 2025 年就在 Buildkite CI 里跑过类似的 self-healing
loop，第一个月修复 24 个 broken
PR。这说明基础的自写、自跑、自修，在工程上已经成立。

真正卡住人的地方，发生在更高一层。任务一旦变长、变多、跨会话、跨项目，人仍然要不断决定下一步该做什么，判断某次改动是否真的变好，诊断失败集中在哪里，再把一次成功的经验重复讲给下一轮
Agent。人不再是日志搬运工，但仍然是系统里的隐性 manager。

Senior Manager 要解决的是这个问题。它不是让人把某个 bug
修得更快，而是把 manager
的动作变成系统能力：清楚地委派任务，建立能反复运行的 evaluation，用
observability 看见失败原因，再把有效的 coaching 沉淀成
SOP，让系统下次自己调用。

Neurotype auto-correction
是一个更贴切的例子。这个项目要让用户自由打字，即使有漏字、误触、大小写混乱，也能由
AI 把文本清理到接近 ground
truth。真正难的不是写一个纠错函数，而是让系统知道哪种纠错更好。

于是我们先让 AI 建 evaluation
harness：样例集覆盖相邻键误触、遗漏、重复和大小写等情况，指标用归一化编辑距离和错误类型记录，baseline
则来自 dummy corrector 或旧
prompt。这样一来，系统不再依赖人临时感觉，而是有一条固定刻度。

接着，我们让 AI 构建 tracking
UI。总览视图展示整体分数的变化趋势，单例视图则记录每个 case 的
rationale。evaluation
分数只能告诉我们好不好，却无法解答为什么不好。如果没有这种微观
visibility，即便在统计上知道哪类 case
错得最多，也无法得知模型到底卡在了哪里。我们看到的只是结果分布，却看不见模型内部的错误路径。rationale
与 trace 的价值就在于暴露单例的错误原因，在 evaluation 之外真正建立起
observability。

最后，manager 不再直接替模型改 prompt，而是让 AI
分析失败样例，找出错误模式，再给它一个有针对性的
nudge。成功之后，把这次“问题、诊断、修正”的过程写进 SOP。后面的
auto-tuner 参考这份 SOP 自己提出改动、运行评估、记录结果。Senior Manager
交付的不是一个修好的 bug，而是一个能持续修自己 bug 的系统。

## 3. Loop
Engineering：Senior Manager 的机制落地

Loop Engineering 本质上是 Senior Manager 思想的技术落地。Boris Cherny
在 CNBC 采访中把这个转变说成：Claude 自己写 prompt，人和负责协调的
Claude 对话；Business Insider 对这句话做了转述。

所以理解 Loop Engineering 时，不应该先盯着 cron、worktree
这类实现细节。它们有用，但属于工程载体。真正重要的是：Senior Manager
路线里的二阶管理动作，在 Loop Engineering 里都有对应的系统组件。

Senior Manager 路线

Loop Engineering 组件

为什么重要

把成功经验写成 SOP，例如

scale.md

或 playbook

skills 和知识资产

让下一轮 Agent 不必重新摸索，把一次 coaching
变成长期可调用的能力。

建立 evaluation harness：样例集、指标、baseline

verifier 和自动评估

给系统一条固定刻度，避免每次改动都靠人临场判断。

建 tracking UI，记录 rationale 和 trace

state、trace 与 observability

分数只告诉你变没变，trace 才告诉你该修哪里。

从 fixer 变成 coach，让系统自己诊断失败模式

maker/checker 反馈回路

执行者负责尝试，检查者负责校准，系统才不会自我打分过宽。

让真实使用不断生成新样例

memory 和 data flywheel

静态测试集会过期，真实数据回流才能让系统长期变强。

在工程实现上，一条 Loop Engineering
闭环流水线通常会用到这些承载方式：

时间调度：定期的起搏器。Boris 在 Sequoia AI Ascent 上描述的 /loop 就是让 Claude 通过 cron 调度一个重复任务，可以每分钟、每 5 分钟或每天运行；这段在 Sequoia 访谈里有完整上下文。类似地，也可以使用 /goal 指令，由独立的 checker 在每次迭代后评估是否可以安全退出。

分支隔离：并行开发的安全沙箱。利用物理分支隔离技术，让多个子 Agent 运行在不同的临时目录中，互不干扰。

知识资产：将 SOP 规范沉淀为 SKILL.md 文档。这是 Agent 的无状态运行指南，用来解决金鱼效应带来的记忆债务。

外部连接：通过 MCP 协议将 AI 接入真实的物理工具链，如 CI/CD、Slack、Linear 数据库。

分立审计：物理拆分 maker 与 checker。执行者拼命干活，审核者根据约束把关，杜绝自我打分偏差。Addy Osmani 在文章里指出：写代码的模型给自己的作业打分时太宽容。

状态外部化：在 Agent 重新启动或上下文重置间，利用磁盘文件或项目状态看板记录任务进度，防止状态丢失。

## 4. 决定循环质量的两大硬杠杆

运行一条流水线并不难，难在让它产出高可靠的结果。在实践中，决定循环能否真正收敛而非失效的，是以下两个硬杠杆。

### 4.1 评估的艺术：为什么
TDD 不是 AI 时代的答案

在真实工程中，对工作结果的评估往往非常主观且繁杂，绝非一句编译通过所能概括。

很多人直觉上认为，既然 AI 的行为难以预测，那我们只需要套用 TDD
的模式，多写一些单元测试，逼着 AI 跑绿测试就能保证质量。

但在实际运行中，这犯了方向性错误。在我们之前发表的文章《为什么
TDD 反而不是 AI 时代的答案》中，我们详细分析过这个悖论的成因：

第一，传统 TDD
能够成功，依赖于一个人类社会特有的隐含前提：人类开发者自带追求正确性的动机结构（对凌晨两点被叫醒的恐惧、对
Code Review 难堪的担忧）。测试在人手上是辅助前行的路标系统。

第二，AI 没有任何隐性维护负担。在 TDD 的闭环里，AI
接收到的唯一反馈只有测试过没过。此时，Goodhart’s
Law（当指标变成目标，它就失去了作为指标的意义）会迅速生效：如果为了跑通权限测试，AI
发现最快的方法是直接改写代码使其硬编码
return True，它会毫不犹豫地这么做。测试变成了它的目的地，而非路标。

第三，如果我们为了堵死漏洞，去写大量高度特化的 Mock 和
Stub，这就锁死了 AI 的实现路径，等于强行塞给了它过程确定性的枷锁。AI
失去了探索更优架构的自由度。

因此，设计评估标准是一门艺术。AI
时代的解法不是写更多细碎的单元测试，而是将确定性约束从具体的代码路径撤到系统边界上：

AI
时代的评估应从路径约束转向边界约束

我们需要使用契约测试、属性测试，或者引入另一个完全独立的 AI
实例，使用自然语言的验收规范对生成结果进行语义维度的共识核对。这虽然牺牲了机械的确定性，但换取了极大的语义灵活性。

### 4.2 任务自动发现的局限

在当前的 Loop 宣导中，有一个概念被包装成卖点：让 AI 自动扫描 CI
日志和 Bug 反馈，自己发现工作并决定要改什么。

在实际生产中，这种完全由 AI
决定优先级和需求发现的思路，大多是一个噱头。原因表现在两点：

第一，优先级排布需要大量的商业上下文、用户同理心和公司中长期的战略诉求。这些背景知识高度抽象且动态漂移，AI
在缺乏这些隐性上下文的前提下做出的决策极易走偏。

第二，任务发现是一个发散系统。如果实现代码写错了，大不了编译不通过或测试报错，这是收敛的局部问题；但如果方向决策和架构设计走错，Agent
可能会在错误的基础上不断累积代码，堆砌出极难挽回的屎山系统，再想回头成本高昂。

在当前的阶段，任务发现仍然需要人类牢牢把握方向。AI
可以用来辅助查漏补缺，但决定做什么、以什么顺序做，依然是人类的核心防线。

## 结语：领先行业一步的系统设计师

Loop Engineering 的爆火，标志着行业正在从微操 Prompt
的工具使用者，向设计自运转体系的系统设计师升维。

如果你想不再做不断拆任务、补背景、判断下一步的 AI
管理员，而是成为能够搭建自演化开发引擎的设计师：

👉 欢迎了解我们的课程：Superlinear Academy -
AI Builders。在这里，我们将这套走在行业变化前列的 AI
协同、系统评估与闭环体系，系统性地交付给你。