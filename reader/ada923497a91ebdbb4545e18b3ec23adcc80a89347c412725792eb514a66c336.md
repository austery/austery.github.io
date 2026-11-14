---
layout: post.njk
source: https://yage.ai/share/thin-harness-fat-skills-20260414.html
speaker: yage.ai
title: |-
  Garry Tan 的 Thin Harness, Fat
  Skills：五个概念拆解，以及怎么落地
date: '2026-04-14'
summary: Garry Tan 的 'Thin Harness, Fat Skills' 提出构建高效 AI 系统的五大概念：Skill Files、Thin Harness、Resolvers、Latent vs. Deterministic、Diarization。文章将其与项目中的 Skills 体系、Agentic Runtime 外包、三级缓存、结果确定性及分层蒸馏等实现对应，并探讨了通过认知上下文打破 LLM 共识天花板的 'Consensus Ceiling'。
area: tech-engineering
category: architecture
tags:
  - thin-harness
  - fat-skills
  - agentic-runtime
  - ai-architecture
  - ai-management
people:
  - Garry Tan
  - Steve Yegge
companies_orgs: []
products_models: []
media_books: []
draft: true
status: evergreen
---

> 日期: 2026-04-14 来源: Garry Tan, X
> Article (2026-04-11, ~1M views) 类型: 概念解读 +
> 实践映射

上周 Garry Tan 在 X 上发了一篇长文 Thin Harness,
Fat Skills，百万阅读，几千收藏。Steve Yegge 说用 AI coding agent
的人比用 Cursor 聊天的人效率高 10x-100x。Garry
的解释是：差距来自架构，具体来说是五个概念的组合。

这五个概念每一个都指向了一个实际的工程问题。这篇文章逐个拆解它们，同时给出我们过去一年在实践中找到的对应实现。我们在今年早些时候把这套实践体系开源了。下面每个概念后面，我会直接链到对应的文件或目录，有兴趣的读者可以直接看代码。

## 概念一：Skill Files

Garry 定义 skill file 为用 markdown
写成的可复用程序。它描述的是判断过程，而非固定答案。同一个 /investigate
skill，传入安全科学家和 250
万封邮件就变成医学调查，传入竞选资金数据就变成政治献金追踪。他说这不是
prompt engineering，是 software design，只不过用 markdown
当编程语言。

他提到一个多数人忽略的洞察：skill file
像方法调用一样接受参数。同一个流程，不同参数，完全不同的能力。

在我们的系统里，这对应 Skills
体系。当前有 40 多个 skill
文件，每个都有触发词、参数、依赖声明和执行流程。比如深度调研工作流定义了从初步扫描到多
Agent 并行到交叉验证的完整流程，并行
Subagent 工作流定义了什么时候该拆任务、怎么控制并行度、overlap
怎么设。这些 skill
在使用中被修正和扩展，积累的知识不随会话结束消失。

Garry 说”every skill you write is a permanent upgrade to your
system”。这正是我们观察到的：每个 skill 是系统的永久升级，模型更新时
skill 自动受益，确定性步骤保持稳定。Skills
索引是完整列表。

## 概念二：Thin Harness

Garry 的核心主张是
harness（运行模型的那层程序）只做四件事：循环调用模型、读写文件、管理上下文、执行安全策略。他反对
fat harness：40 多个工具定义占掉半个上下文窗口，God-tools 每次 MCP 调用
2-5 秒。他用 Playwright CLI vs Chrome MCP 的 75
倍性能差距来量化这个问题。

设计原则是方向性的：把智能向上推到
skills，把执行向下推到确定性工具，中间保持最薄。

我们在实践中得到了相同结论，并且在《从过程确定性到结果确定性》中做了更细的分析。我们提出
AI 集成有四层：Model、Protocol、Runtime、Contract。多数人把注意力放在
Protocol 层（怎么调 API），但 Runtime 层消耗最多时间。好消息是 Runtime
层正在成为公共产品：Claude Code、Codex、Cursor Agent 都在收敛为可复用的
Agentic
Runtime。模型提供商为了兼容这些工具，主动适配自己的故障模式，意味着长尾问题从你一个团队的负担变成了整个生态的共同投入。

所以 Garry 说 harness 要薄，我们更进一步：harness
应该直接外包给现有的 agentic runtime，你只需要在上面叠 skills
和确定性工具。我们的系统就是这么做的：AGENTS.md
是整个系统的入口，它在 Claude Code 或 OpenCode 的 agentic loop
上面运行，harness 本身不是我们写的，我们只写上面的 skills 和下面的
tools。

## 概念三：Resolvers

Garry 的 resolver 是上下文的路由表。当任务类型 X 出现，先加载文档
Y。他举了一个例子：开发者改 prompt 文件，resolver 自动加载 eval
文档，开发者甚至不知道 eval suite 存在。他还提到自己的 CLAUDE.md 从
20,000 行砍到 200 行指针文档，因为模型注意力在大量上下文中退化。

在我们的系统里，这对应一个三级缓存结构，灵感来自 CPU 内存层级。

L1 cache（每次都加载）：AGENTS.md。200
行左右，只有指针和最核心的行为定义。Garry 砍 CLAUDE.md 到 200
行的经验，我们也经历过，最终的解法一样。

L2 cache（按需查索引）：Skills
INDEX.md 和 Axioms
INDEX.md。模型知道有哪些能力和原则可用，但不加载具体内容。

L3 cache（匹配后加载）：具体的 skill
文件和 axiom
文件。只有当模型匹配到用户意图后才加载。每个文件都有 description
和触发词，路由是自动的。

Garry 的 resolver 路由到 skill 和文档。我们多做了一层：除了路由到
skill（改变模型怎么做事），还路由到
axiom（改变模型用什么判断框架做事）。这层差异后面会展开。

我们把这套分层方案的设计思路写在了《为什么 AI
只会说正确的废话》里。

## 概念四：Latent
vs. Deterministic

Garry 说系统中每一步要么属于 latent space（模型做判断），要么属于
deterministic space（程序做执行）。模型可以考虑 8
个人的社交动态来安排座位，但让它安排 800
个人的座位就会输出看似合理、完全错误的方案。他在 YC
系统里的正确做法是：模型发明主题（latent），确定性算法执行分配（deterministic）。

这条分界线在我们的体系里对应公理 T02：结果确定性优于过程确定性。Garry
关注怎么划界。我们在划完界之后多走了一步：对 latent
一侧的输出，怎么建立信任？

答案是把验收标准写成可执行的检查。在翻译场景中，我们发现翻译失败的根本原因是模型不知道什么叫”完成”。一旦把标准写成脚本（格式是否正确、有没有中文泄漏、术语是否一致），模型就能自己跑检查、自己修正、循环到达标为止。我们把这个过程的完整案例写在了《从过程确定性到结果确定性》里。

另外，我们在 2025 年 11 月提出的 Generative
Kernel 里有一个组件叫 Leverage Toolkit，专门处理 latent 和
deterministic
的交界地带：对于模型概念上理解但执行容易出错的任务，提供确定性工具让模型调用。这和
Garry 说的 deterministic foundation 是同一个位置。

## 概念五：Diarization

Garry 的 diarization
是让模型读取关于某个主体的所有材料，输出一页结构化画像。他举了一个具体例子：一个
founder 说自己做”Datadog for AI agents”，但 80% 的 commit 在 billing
模块。模型需要同时读 GitHub 提交历史、申请表和 advisor
transcript，三者交叉才能发现”说的和做的不一致”。他明确说 no SQL query
produces this, no RAG pipeline produces this。

这个判断我们完全认同。我们的对应实现是一套三层蒸馏机制，不过维度不同。Garry
的 diarization 是横向的（多源交叉，per-entity），我们的 Layered
Distillation 是纵向的（时间蒸馏，per-person）。

L1 Observer 每天扫描文件变化和对话记录，提取有意义的观察。L2
Reflector 每周合并去重、识别跨项目的重复模式。L3 Axiom
把经过时间检验的稳定模式提炼为决策原则。筛选标准是稳定性：只有在不同情境和不同时间跨度中反复出现的判断，才进入公理层。

一年积累下来，我们的系统蒸馏出了 43
条 axiom，覆盖 AI 协作、技术决策、管理哲学和信任验证四个领域。每条
axiom 都有具体的来源场景、应用判定和边界条件。比如 A04：可靠性是管理问题说的是
AI 不可靠的根源通常是你把它当工具而非团队成员，V02：可验证性是信任的地基说的是要设计可检测错误的架构而非期望零错误。

Garry
和我们的共同判断是：这一步只有模型能做，关键词搜索和向量检索都做不到。分歧在于蒸馏的方向：横向（多源交叉发现矛盾）还是纵向（时间过滤出稳定模式）。两者解决不同的问题，可以组合。

## Garry
跳过的一步：怎么让人愿意放下键盘

Garry
整篇文章有一个隐含前提：读者已经接受了设计系统让模型执行、自己不亲自写代码的工作方式。但在实际观察中，这一步恰恰是多数技术人员卡住的地方。

技术能力越强的人越容易掉进这个陷阱：看到模型犯了一个你能三秒修复的错误，本能反应就是自己上手。表面上你比模型快，但如果你管理的是多个并行
AI 会话，每次都抢键盘的话效率会迅速崩塌。

我们在《AI
管理三大陷阱》中分析了这个问题，并在公理 A03：从
IC 到经理的心智转变中把管理者的五个职能映射到了 AI
协作场景。选人对应模型选择，委派对应任务分解加上下文准备，培训对应持久化的知识库（也就是
Garry 说的 skill
files），指导对应教方法而非给答案，验收对应可观测的标准（也就是结果确定性）。

换个角度看，Garry 描述的整套架构其实就是 AI 管理学的工程实现。Skill
files 是培训材料，resolvers 是工作分配系统，latent vs. deterministic
是任务委派的边界判断，thin harness
是管理者不应该做的事。只不过他跳过了起点：怎么让一个技术专家完成从执行者到管理者的转变。

## 再多走一步：Consensus Ceiling

Garry
的框架让模型高效执行。但还有一个问题他没有触及：模型输出的认知深度。

我们用一个对照实验展示了这个问题。两个配置几乎相同的
AI 系统（相当的模型、相同的 skill、相同的工具、相同的
prompt），唯一区别是背后的认知上下文。一个有一年积累的判断框架，另一个没有。两个系统分析同一个话题，产出的报告在性质上完全不同。一个给出行动清单：建
AGENTS.md、写规则进 repo、CI
检查文档。另一个给出判断：完美主义是吞吐量的敌人，两家公司都接受了纠错比等待便宜这个权衡。

LLM 的训练机制决定了默认输出是共识。Next token prediction
输出最高概率 token，RLHF
进一步惩罚争议性输出。两层叠加，默认行为就是回归均值。这就是 consensus
ceiling。

打破这个 ceiling，需要的不只是更好的
skill，而是密度足够高的个人认知上下文去覆盖训练时植入的共识先验。这就是为什么前面提到我们的
resolver 多了一层 axiom 路由。Skill 改变模型怎么做事（执行效率），axiom
改变模型用什么框架做判断（认知深度）。两者是正交维度。

Garry 的读者在应用他的框架后，会得到一个高效、准确、可扩展的 AI
系统。加上 axiom
层之后，这个系统还能产出超越共识的判断。

## 概念映射总表

Garry Tan 的概念

我们的对应实现

代码 / 文档

Skill Files

Skills 体系

rules/skills/

Thin Harness

Agentic Runtime 外包

AGENTS.md

（在
Claude Code 上运行）

Resolvers

三级缓存 On-Demand Loading

Skills
INDEX

+

Axioms
INDEX

Latent vs. Deterministic

T02 结果确定性

axioms/t02

Diarization

Layered Distillation → 43 条 Axiom

rules/axioms/

Self-rewriting skills

知识飞轮

workflow_knowledge_flywheel.md

（未涉及）

IC → Manager 心智转变

axioms/a03

（未涉及）

Consensus Ceiling 的突破

上下文基础设施全文

完整的开源仓库在 github.com/grapeot/context-infrastructure。

## 参考来源

Garry Tan, Thin Harness, Fat Skills, X Article, 2026-04-11

我们的相关文章（按时间顺序）:

当 AI 变成你的下属：技术人必须跨越的三道管理陷阱, 2025-02

Beyond DRY: Thoughts on AI-Native Software Engineering, 2025-11

从过程确定性到结果确定性, 2026-01

OpenClaw Deep Dive, 2026-02

为什么 AI 只会说正确的废话, 2026-03