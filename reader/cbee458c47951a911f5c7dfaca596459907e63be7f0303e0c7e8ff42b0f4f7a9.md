---
layout: post.njk
source: https://baoyu.io/blog/2026-02-25/laura-tacho-ai-pragmatic-summit
speaker: baoyu.io
title: 92.6% 开发者每月使用 AI 编码助手，但每周节省时间只有 4 小时 | 宝玉的分享
date: '2026-02-25'
summary: 本文基于 12 万开发者数据，分析了 AI 编码助手的应用现状与组织影响。数据显示，AI 采用率高（92.6%），但每周节省时间稳定在 4 小时，暗示编码加速空间触顶。AI 作为放大器，加剧了组织间绩效差异。文章强调，AI 并非解决组织问题的灵丹妙药，真正的变革在于解决系统性问题、提升开发者体验、以及通过聚焦真实客户问题进行实验。Agentic 工作流是未来趋势，但需关注共识问题。
area: tech-engineering
category: tech-trends
tags:
  - ai-coding-assistants
  - developer-productivity
  - organizational-impact
  - agentic-workflows
  - ai-adoption
people:
  - Laura Tacho
  - Gergely Orosz
  - Martin Fowler
  - Kent Beck
  - Steve Yegge
  - Abi Noda
  - Nicole Forsgren
  - Brian Houck
  - Carl Sagan
companies_orgs:
  - DX
  - The Pragmatic Engineer
  - MIT
  - Google
  - Microsoft
  - Thoughtworks
  - OpenAI
  - Haven Headache and Migraine Center
  - Cisco
  - JP Morgan Chase
products_models:
  - Cursor
  - Codex
  - Copilot
  - Claude (AI assistant)
  - ChatGPT
  - SPACE framework
  - DORA AI Capabilities Model
  - FOREST framework
  - Ralph loops
  - Linear
  - Figma
  - MAFA
  - GPT 5.3 Codex
  - Gas Town
  - Windsurf
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-02-25

# 92.6% 开发者每月使用 AI 编码助手，但每周节省时间只有 4 小时

作者：

宝玉

Laura Tacho 是 DX 公司 CTO，Core 4 开发者生产力框架的联合作者，手里握着 12 万开发者、450 多家公司的真实数据。2 月 11 日在旧金山 Pragmatic Summit 上，她做了一场 30 分钟的主题演讲，用最新行业基准数据回答一个问题：AI 到底有没有让组织变好？

【注：Pragmatic Summit 是 The Pragmatic Engineer 创始人 Gergely Orosz 于 2026 年 2 月举办的首届线下峰会，约 500 名工程领导者参加。DX 是一家帮助企业度量和改善工程效率的开发者体验平台公司。】

原始视频链接：https://www.youtube.com/watch?v=LOHgRw43fFk

要点速览：

12.1 万开发者样本显示，92.6% 每月使用 AI 编码助手，但每周节省时间稳定在约 4 小时，连续几个季度没有增长

AI 编写并合并到生产环境的代码占比达 26.9%，较上季度的 22% 显著提升，日活用户突破 30%

AI 是放大器：有些公司客户端事故减少了 50%，有些公司事故翻了一倍。同样的工具，不同的结果

MIT 研究结论：“高采用率、低转化率”。92% 的开发者在用 AI，但组织层面的真正变革很少发生

95% 的企业级 AI 项目无法产生可衡量的财务影响（MIT 研究数据）

入职时间减半可能是 AI 目前影响最深远的效果：第 10 个 PR 的表现能预测未来两年的产出，AI 让达到这个里程碑的时间缩短了一半

Agent 间共识将是 2026 年需要解决的重大问题

Martin Fowler 闭门研讨会的核心判断：AI 不解决组织系统问题，除非你先承认系统问题的存在

## 【1】12 万开发者的最新数据：92% 在用，但时间节省卡在 4 小时

Laura 带来了一组首次公开的行业基准数据。样本量是 121,502 名开发者，覆盖 464 家公司，数据采集时间从 2025 年 11 月到 2026 年 2 月 1 日。

先看采用率：92.6% 的开发者每月至少使用一次 AI 编码助手。其中 44.1% 每天使用，30.3% 每周使用，18.2% 每月使用，只有 0.8% 从来不用。这里的“AI 编码助手”，大部分开发者将其定义为 Cursor、Codex、Copilot、Claude 这类工具，不一定包括 ChatGPT。

再看时间节省。在 95,301 名开发者的样本中，自报每周因 AI 工具节省约 4.08 小时。按使用频率细分，每天使用的人节省最多（约 4.8 小时/周），每周使用的约 4 小时，每月使用的约 3.6 小时。这个数字和 2025 年 Q2 差不多，和 Q4 的 3.67 小时也接近，一直在 4 小时左右徘徊。Google 在 2025 年发表的一项研究称约 10% 的生产力提升，DX 的数据基本印证了这个量级。

但这个数字没有随着工具迭代而明显增长。模型在变强，工具在变好，每周节省时间就是卡在 4 小时附近。Laura 没有解释原因，但数据本身就是一个信号：仅靠加速编码任务的优化空间，可能已经接近天花板。

变化最快的指标是 AI 编写代码（AI authored code） 的比例。在 42,644 名开发者的样本中，26.9% 的生产代码由 AI 编写，基本未经大幅修改就通过代码审查并进入生产环境。上一季度这个数字是 22%，季度环比增长近 5 个百分点。每天使用 AI 的开发者，这个比例已经突破 30%。

## 【2】AI 让新人入职时间减半，且效果持续两年

Laura 一直有个直觉：AI 会是入职（onboarding）的利器，能帮新人更早地接触到项目信息。她用数据验证了这个直觉。

在 35,594 名 2024 年 1 月后入职的开发者样本中，从 2024 年 Q1 到 2025 年 Q4，入职时间缩短了一半。衡量标准是达到第 10 个合并 PR 的天数，这是行业普遍认可的入职里程碑。从图表看，2024 年 Q1 大约需要将近 100 天，到 2025 年 Q4 降到了不到 50 天。把这个曲线和 AI 使用率的增长曲线放在一起，走势高度吻合。

【注：PR（Pull Request）是开发者向项目提交代码变更的标准流程。第 10 个 PR 通常意味着开发者已经独立完成了多次有意义的代码贡献，是衡量“真正上手”的常用指标。】

Microsoft 有一项相关研究。SPACE 框架联合作者 Brian Houck 发现，一个开发者在第 10 个 PR 时的表现水平，能预测这个人在未来两年内的产出模式。不是“入职快的人之后也快”这么简单，而是第 10 个 PR 本身就是一个预测信号。

【注：SPACE 框架是 2021 年由 Nicole Forsgren 等人提出的开发者生产力度量框架，覆盖满意度、绩效、活动量、沟通协作和效率五个维度，被业界广泛采用。】

逻辑链条是这样的：AI 帮新人更快达到第 10 个 PR → 第 10 个 PR 预测未来两年表现 → 入职加速的效果可能在两年内持续放大。如果这个推论成立，入职加速可能是 AI 对组织影响最大的单一效果。

Laura 补充说，这不仅适用于公司新员工，也适用于转项目的工程师甚至非工程师。AI 降低了理解代码库的认知门槛，过去新人加入一个大型项目，光理解现有代码结构可能就要花几周，现在可以直接问 AI。

## 【3】均值是骗人的：有公司事故减半，有公司事故翻倍

Laura 展示完行业均值后，话锋一转：

> 均值不等于典型体验，不等于会发生在你身上的事。
> （“Average does not mean typical, it does not mean what is going to happen to you.”）

她用大爆炸做了个比喻。AI 进入组织就像一场大爆炸，释放了巨大的能量，但冲击波把不同的组织推向了完全不同的方向。组织绩效是多维的，AI 作为加速器和放大器，正在把这些维度上的差异拉得越来越大。

质量维度上，差距最大。在 67,084 名开发者的样本中，有些公司的客户端事故增加了一倍，而同一时间段内，另一些公司的事故减少了 50%。

Laura 说：

> 本来就运转不良的组织，现在更加运转不良了。而且是以更快的速度运转不良。
> （“Organizations that were dysfunctional already, now they're more dysfunctional. They're dysfunctional and dysfunctional faster.”）

那些已有健康系统的公司，AI 放大了它们的优势，让它们更快、质量更高、变更信心更强。而那些本就有问题的公司，AI 放大了问题，制造了更多事故，更快地把代码推到了不该推的地方。

AI 不是药，是放大器。好的更好，差的更差。

## 【4】92% 在用，但组织转化率很低

Laura 引用了 MIT 在 2025 年 7 月发布的研究《The GenAI Divide: State of AI in Business 2025》。这项研究调查了 152 家组织，结论是：当前行业处于“高采用率、低转化率”的状态。

【注：该研究由 MIT 的 Project NANDA 团队发布，基于 52 次高管访谈、153 份高管调查和 300 多个公开 AI 项目的分析。】

PPT 上的图表显示：80% 的组织调研过通用大语言模型，但只有 50% 进入了试点阶段，最终成功实施的只剩 40%。嵌入式或任务专用的 GenAI 更惨，从 60% 调研到 20% 试点再到 5% 成功实施，漏斗极其陡峭。从试点到生产再到利润，每一步都有大量掉队者。

这背后有一个 Laura 观察到的规律：那些曾经放弃云转型的组织、放弃敏捷转型的组织，现在也在放弃 AI 转型。转型需要组织直面自身的问题，而这件事本身就令人不适。

> 采用不等于影响。
> （“Adoption doesn't mean impact.”）

Laura 的 PPT 里引用了 MIT 的一句话：“这些工具主要提升了个人生产力，而非损益表（P&L）表现。” 当 AI 仅被用来加速一个人在电脑前敲代码的环节，生产力提升的天花板很低。如果想要组织级的成果，就必须在组织层面思考 AI 的应用，而不是停留在编码任务层面。

MIT 研究还揭示了一个错配：超过 50% 的 AI 预算被投向了销售和营销工具，但最高 ROI 其实来自后台自动化，比如削减外包和减少代理费用。购买专业供应商工具的成功率约 67%，自己内部构建的成功率只有三分之一。

还有一个正在快速扩大的“影子 AI 经济”：只有 40% 的公司购买了官方 LLM 订阅，但超过 90% 的公司里，员工在工作中定期使用个人 AI 工具。

PPT 上直接列了三步：“1. 用 AI 做实验 → 2. ??? → 3. 利润！”。中间那个“???”才是真正困难的部分，它叫组织变革管理。

## 【5】Agentic 工作流在扩展可能性的边界

Laura 用宇宙膨胀来比喻 agentic 工作流的兴起：我们的宇宙正在变大，炒作在变多，但可能性也在变大。

她把 1969 年人们对月球殖民地的幻想和 2026 年的 Gas Town 放在一起做对比。

Gas Town 是一个实验性的 AI 编程工具，PPT 的插图标着“Vibe Coding Floor: Throughput Over Precision”（凭感觉编程车间：吞吐量优先于精度），一群水獭在混乱的工厂里搬运标着“Features”、“Bugs”、“Reviews”的桶。

Laura 形容 Gas Town“完全疯狂”，PPT 列了几条使用警告：“如果你不能同时运行至少 5 个 Claude Code，别用 Gas Town”、“如果你在乎钱，别用 Gas Town”、“别用 Gas Town”。

【注：Gas Town 是 Steve Yegge 开发的实验性 AI 编程代理工具，同时并行运行多个 AI 编码代理完成任务，以激进的自主性和极高的 token 消耗著称。】

这些工具让构建变得更有趣，但 Laura 很清醒：自己在美甲沙龙用 AI 做一个指甲油配色 App，和一家跨国银行靠 AI 改变营收，是完全不同的事。她类比登月：我们没有住在月球上，但太空探索带来了太阳镜、条形码、石英手表。实验和探索本身有价值，Agent 同样在扩展我们能做什么、怎么做、为谁做的边界。

Agentic 使用的具体数据来自一个较小的样本：6 家先行公司的 2,920 名开发者。在这些公司中，50.5% 每天使用 agentic 工作流，30.2% 每周使用，11.7% 每月使用。Laura 提醒，这些公司走在行业前沿，已经为 agentic 工作流部署了遥测（telemetry），不能代表行业平均水平。

关于 Codex，Laura 分享了一组数据：Codex 桌面版在 2 月 2 日发布后一周内超过 100 万下载，上周用户增长了 60%。OpenAI 内部每周处理数万亿 token，95% 的 OpenAI 开发者在用 Codex。上周四（约 2 月 6 日）还发布了 GPT 5.3 Codex。使用 Codex 的开发者比使用其他 AI 工具的开发者每周多提交约 60% 的 PR。

【注：Codex 桌面应用是 OpenAI 于 2026 年 2 月推出的 Mac 端 AI 编码工具，可以同时运行多个 AI Agent 并行处理任务。GPT-5.3-Codex 是其底层模型。这些数据来自 OpenAI 官方公布，存在利益相关性。】

Laura 对这个数字的态度很审慎：这是一个数据点，不是唯一的数据点，但它说明 agentic 工作流有很高的上限。

## 【6】企业实战：Haven 医疗、Cisco、JP Morgan

Laura 介绍了一家非 AI 行业的公司：Haven Headache and Migraine Center，一家位于旧金山的虚拟远程医疗创业公司，专注头痛和偏头痛。Haven 的核心问题很朴素：能不能通过 Zoom 解决头痛问题？事实证明可以。

在医疗领域，Laura 强调了一个关键区分：用 AI 生成的代码是“耐用代码”（durable code） 还是“一次性代码”（disposable code）。Haven 作为一个医疗场景的小型创业公司，两种都在做。

在开发层面，Haven 用 Ralph loops 快速搭建全新患者门户的原型。PPT 展示了完整的工作流链路：(Linear + Figma) → PRD → JSON → Claude Code。产出不是一次性垃圾代码，而是高质量的原型，迭代速度更快，文档更清晰。

在临床层面，Haven 训练了一个 HIPAA（美国医疗隐私法规）合规的模型，处理数十万条历史患者消息。模型对消息进行分类、路由和工作流自动化：是需要续药还是需要预约随诊。结果是客户满意度达到行业平均的 3 倍，患者的头痛天数和严重程度都有了实质性下降。

大型企业也在动。Cisco 有 18,000 名工程师每天都在使用 Codex，主要用于复杂的代码迁移和代码审查，代码审查时间减少了 50%。JP Morgan Chase 发表了一篇关于 MAFA（Multi-Agent Framework for Annotation，多智能体标注框架）的论文：多个专业化智能体独立标注客户交互数据（意图、实体、FAQ 分类），然后由一个“评判智能体”通过共识和置信度评分来聚合和重新排序结果。

Laura 预测，智能体之间的共识（consensus among agents） 将是 2026 年需要解决的重大技术问题。这和分布式系统中的共识问题一脉相承，但在 AI Agent 的语境下是全新的挑战：当多个 Agent 各自有不同的“判断”时，如何达成共识？

## 【7】Martin Fowler 闭门研讨会：“AI 不解决组织问题”

2026 年 2 月 1-3 日，Laura 被邀请参加了 Martin Fowler 和 Thoughtworks 组织的“软件开发的未来”闭门研讨会，地点在犹他州鹿谷。选这个地点有历史意义：2001 年 2 月，敏捷宣言就是在犹他州的雪鸟滑雪度假村诞生的。25 年后，一群人回到同一个州的山区，讨论 AI 时代的软件开发。参与者包括 Kent Beck（极限编程创始人）、Steve Yegge（Gas Town 的开发者）、Gergely Orosz 等人。

【注：Martin Fowler 是 Thoughtworks 首席科学家，《重构》作者，也是 2001 年敏捷宣言的 17 位签署者之一。Kent Beck 是极限编程（XP）的创始人，同为敏捷宣言签署者。】

一天半的讨论集中在一个话题：如何负责任、合乎伦理、可持续地使用 Agent。现场有大量实验（Steve Yegge 在玩 Gas Town），气氛活跃。但最终的结论出乎意料地冷静：

AI 不解决组织的系统问题。 只有当你主动把 AI 应用到系统问题上时，它才能发挥作用。而前提是，你首先要承认系统问题的存在。

Kent Beck 见证了软件行业过去 30 年的每一次“银弹”承诺，Steve Yegge 在 Google 和 Amazon 经历过大规模工程组织的现实，Laura 手里有跨 450 家公司的实际数据。三个人从不同角度看到了同一件事。

PPT 上放了一张 Laura 和一位参会者的合影，旁边是贴满便签纸的讨论板，议题涵盖生产力度量、编程语言的未来等。Laura 说，她和 Kent Beck、Steve Yegge 在会议间隙的走廊里聊了一阵，总结出了这样一段话：

> 组织受制于人和系统层面的问题。我们对任何声称可以在不先解决这些人和系统层面约束的情况下改善组织绩效的技术，保持怀疑。我们保持怀疑，我们也保持为人。

> （“Organizations are constrained by human and systems-level problems. We remain skeptical of the promise of any technology to improve organizational performance without first addressing human and systems-level constraints. We remain skeptical and we remain human.” — Kent Beck, Laura Tacho, and Steve Yegge）

Laura 用太空类比收束。PPT 展示了一幅火星上堵车的漫画，火星表面到处是垃圾、废弃卫星和排着长队的汽车，地球在远处的天空中。

> 如果我们不解决系统层面的问题，我们只会把它们一起带到太空去。
> （“If we don't address the systems level problems, we will just take them to space with us.”）

有人问 Martin Fowler：是不是该写一个新的宣言了？Fowler 的回答是：不，太早了。人们还在实验想法。他说他对宣言本身没什么兴趣，大多数宣言被大多数人明智地忽略了，只不过敏捷宣言碰巧是个例外。

## 【8】赢得 AI 竞赛的组织做对了四件事

在研讨会和大量数据分析的基础上，Laura 总结了四个她反复看到的成功模式。

第一，有目标，有度量。 “撒网祈祷”（spray and pray）不奏效，就是给所有开发者发 AI 工具许可证，然后祈祷好事发生。Laura 说她有大量证据证明这行不通。赢的组织会把 AI 创新对准一个具体问题，设定可衡量的目标，然后跟踪进展。

为此她和 DX CEO Abi Noda 联合发布了一个 AI 度量框架：

第一层“利用率”：AI 工具的日活/周活、AI 辅助 PR 的比例、AI 生成代码的比例、分配给 Agent 的任务数

第二层“影响”：AI 节省的时间、开发者满意度、DX Core 4 指标（PR 吞吐量、交付感知速率、开发者体验指数、代码可维护性、变更信心、变更失败率），以及 Agent 完成的人类等效工时（HEH）

第三层“成本”：AI 总支出和人均支出、每个开发者的净时间收益（时间节省减去 AI 花费的时间）、Agent 时薪率（HEH / AI 支出）

她同时推荐了两个 AI 就绪度模型。一个是 DORA AI Capabilities Model，包含七项能力维度：清晰传达的 AI 立场、小批量工作、健康的数据生态、以用户为中心、AI 可访问的内部数据、高质量的内部平台、强版本控制实践。另一个是 Thoughtworks 的 FOREST 框架，包含六个维度：基础架构、运营模型、数据就绪度、可信 AI、人机协作体验、战略对齐。

【注：DORA（DevOps Research and Assessment）是 Google Cloud 旗下的研究团队，以其年度 DevOps 报告闻名。】

第二，开发者体验比以往任何时候都更重要。

Laura 说：

> 把你原来要跟领导层谈的“开发者体验”改名叫“智能体体验”，你就能拿到预算了。
> （“Just call it agent experience and you'll get money for it.”）

好的反馈循环、清晰的服务定义、完善的文档、快速的 CI（持续集成），这些开发者体验的基本功，喊了几十年，一直拿不到预算。到了 AI 时代，同样的东西换了个名字，管理层突然愿意投资了。因为好的测试实践、好的文档，恰恰是 agentic 工作流能跑起来的基础。

Laura 说：

> 我们为开发者体验呼吁了几十年，一直在为几毛钱乞讨。不愿意为人类工程师花这个钱，但为机器人工程师花钱就没问题了。这让人有点心寒，但策略上，抓住这个机会。
> （“We have been screaming about this for decades... It is disheartening that we didn't want to spend the money when it came to human engineers but when it comes to robot engineers we're okay with it.”）

PPT 展示了一张来自 134,085 名工程师的调查图表，按年化时间分布排列各工作流阶段对开发者时间的影响。排在最前面的是“会议密集日”和“中断频率”，远超“AI 时间节省”。构建和测试等待时间、开发环境繁琐度、审查等待时间、代码理解、信息搜索排在后面。

AI 节省的每周 4 小时，无法弥补糟糕的会议文化和频繁的中断。 成功的组织不是用 AI 加速编码，而是把 AI 指向这些系统性问题本身，比如用 AI 减少会议、优化 CI 等待时间、降低开发环境的重复劳动。

第三，把 AI 当作组织问题而非个人问题。

如果你想要营收、损益表、上市时间这样的组织级成果，就必须在组织层面思考 AI 的应用。AI 需要跨越整个价值流的工作流。

MIT 研究展示了组织层面 AI 采用的障碍排名：

变革管理困难

缺乏高管支持

用户体验差

模型输出质量担忧

不愿采用新工具

前三项都不是技术问题。Laura 点名了一个现象：高管团队说“上 AI”，但自己从来没打开过 Windsurf、Claude Code 或 Codex。

第四，通过解决真实客户问题来做实验。

去火星探险很酷，但不能让整个组织都去探险。成本太高，对核心业务干扰太大，也不服务于客户。实验要继续，但实验也可以精准地对准实际的客户问题。这才是看到组织级成果的路径。

## 【最后】

Laura 这场演讲，作为一个每天泡在 12 万开发者数据里的人给出的判断：AI 的采用已经不是问题，从采用到影响之间的鸿沟才是。 那些事故翻倍的公司和事故减半的公司，用的是同样的工具。差别在组织本身。

几个值得持续关注的信号：AI authored code 比例在快速攀升，从 22% 到 27%，日活用户突破 30%，这条曲线还在加速。而时间节省指标卡在 4 小时不动，暗示仅靠编码层面加速的空间可能已经到顶。Agentic 工作流是下一个增长点，但目前的数据来自先行者，主流企业能否复制还是未知数。

在敏捷宣言 25 周年的背景下，Laura 和 Kent Beck、Martin Fowler 这群人得出的结论，和 25 年前如出一辙：技术不能替代组织变革。AI 不例外。

Laura 用 Carl Sagan 的话结束了演讲：“某处，某个不可思议的东西正等待被发现。”

然后她加了四个词：

> 保持脚踏实地，保持怀疑，保持人性，保持务实 (stay grounded, stay skeptical, stay human, stay pragmatic)

完整演讲视频：https://www.youtube.com/watch?v=LOHgRw43fFk
Slides: https://docs.google.com/presentation/d/1WQMMBfHDBg5xeUWmQPQ86tlBatk_OEV0EsbVDf9sHPo/edit?usp=sharing

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme