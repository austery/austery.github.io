---
layout: post.njk
source: https://baoyu.io/blog/2026-02-27/from-writing-code-to-managing-agents
speaker: baoyu.io
title: 从写代码到管 Agent：斯坦福首门 AI 软件开发课的讲师说，大多数工程师还没准备好 | 宝玉的分享
date: '2026-02-27'
summary: 本文报道斯坦福 AI 软件开发课讲师 Mihail Eric 的观点，指出初级开发者面临挑战，AI 改变软件开发流程。强调管理 Agent、优化代码库（如增加测试）是关键。探讨了 AI 时代开发者技能转型、初级工程师的“无知无畏”优势，及过度工程化风险。引用 Rem Koning 见解，展望 AI 原生组织未来。
area: tech-engineering
category: ai-application
tags:
  - agentic-workflows
  - ai-software-development
  - future-of-development
  - developer-skills
people:
  - Mihail Eric
  - Rem Koning
companies_orgs:
  - Stanford
  - Anthropic
products_models:
  - Claude Code
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-02-27

# 从写代码到管 Agent：斯坦福首门 AI 软件开发课的讲师说，大多数工程师还没准备好

作者：

宝玉

Mihail Eric 在斯坦福开了一门课，CS146S“The Modern Software Developer”，2025 年秋季首次开设，全美第一门把 AI 贯穿整个软件开发流程的大学课程。开放选课几小时，超过 100 名学生抢着报名。

Mihail 同时在旧金山一家早期创业公司担任 AI 负责人，之前在 Amazon Alexa 带过技术团队，也创办过 YC 支持的 AI 编码公司，斯坦福 NLP 组出身，导师是 Christopher Manning。

在 EO 频道“The Thinking Mode”系列的访谈中，他用 14 分钟谈了几个问题：初级开发者正在遭遇什么、顶尖工程师如何管理 Agent、什么样的代码库对 Agent 友好、以及为什么初级工程师的“无知无畏”在 AI 时代反而是优势。

原始视频链接：https://www.youtube.com/watch?v=wEsjK3Smovw

## 要点速览

初级开发者正面临“三重风暴”：COVID 后企业裁员 20-30%、CS 毕业生十年内翻了一倍多、AI 让雇主考虑“少招人+AI”的策略，三者叠加让新人求职极难

管理多个 Agent 是“游戏里的最终 Boss”，不要因为别人跑 10 个 Agent 就觉得自己也该跑 10 个，从 1 个开始逐步增加

Agent 只能基于显式“合约”（测试）运作，代码库需要在测试覆盖、文档一致性、设计模式一致性上做好准备

品味在“最后一公里”培养，连 Claude Code 团队自己也在每周重写代码

资深开发者往往最抗拒 AI 工具，初级工程师因为没有历史包袱反而学得最快

## 初级开发者的“三重完美风暴”

Mihail 从一个故事讲起。他认识一个刚从 Berkeley 毕业的人，投了大约 1000 份简历，只收到了 2 个回复——不是面试邀请，只是回复。

这不是个例。他认为初级工程师的困境是三件事同时发生的结果。

第一，过度招聘后的大裁员。 2021 年前后，COVID 之后很多公司觉得自己需要扩招，疯狂招人。然后发现招多了，大规模裁员开始了。很多公司发现砍掉 20%、30% 的员工，业务照样转。

第二，CS 毕业生数量暴涨。 Mihail 说自己毕业时是一个数字，现在大概翻了两到三倍。

第三，AI 改变了雇主的算盘。 雇主开始算一笔账：我是继续招更多的人来填坑，还是招更少但 AI 原生的人，用更少的人完成同样的工作？

三者叠加的结果：一大批被裁的资深工程师和一大批新毕业的年轻人同时涌入市场，而雇主的招聘意愿因为 AI 反而在收缩。

Mihail 认为，当前这一代进入职场的初级开发者会是”AI 原生转型”的第一代。他们必须同时具备扎实的传统基本功和完整的 AI 原生能力，缺一不可。

## 不要因为别人跑 10 个 Agent 就觉得自己也该跑 10 个

在 Mihail 看来，AI 原生工程师的核心定义是：传统编程、系统设计、算法思维的底子要扎实，同时要非常擅长使用 Agent 工作流（agentic workflows）。

但他特别强调了一个常见误区。Claude Code 的创造者 Boris Cherny 曾来课堂做客座演讲，Boris 同时跑 10 个甚至更多 Agent 的工作方式在开发者社区广为流传。Mihail 说他的学生听完后，第一反应是“我也应该从 10 个开始”。他认为这恰恰是错误的结论。

> 注： Boris Cherny 是 Anthropic 的 Staff Engineer，Claude Code 项目的创始工程师。他曾公开分享自己的工作流：终端里开 5 个 Claude Code 会话，浏览器里再开 5-10 个，同时管理十几个并行任务。

他的建议是 “逐步搭建”（build it up piecemeal）。

先用一个 Agent 把一件复杂的事做好，确认自己完全掌握了这个工作流。然后看看有没有第二个隔离的小任务，比如修一个 logo。再加一个 Agent 改网站的文案。

关键是每个任务之间必须是互相隔离的、没有依赖的。

第一个跑顺了，加第二个。第二个也稳了，再加第三个。不是 10 个一起上。

> 真正学会管理多个 Agent，就像通关游戏的最终 Boss。能做到这一点的人，即使在今天也是最顶尖的那 0.1%。
> （”Knowing how to properly handle multiple agents is like the last boss in a game. If you can do that really, really well then you are literally the top top 0.1% of users.”）

## 上下文切换：管 Agent 的真正难点

谈到多 Agent 工作流的核心技能，Mihail 指向了一个很日常的能力：上下文切换。

他打了一个比方：这些 Agent 就像一群热情聪明的实习生，你把任务派出去，它们就在终端里埋头干活，代码哗哗地写出来。但有时候它们会卡住。

这时候你需要从 Agent 1 切到 Agent 2，再切到 Agent 3。每切换一次，你得记住上一个 Agent 做到哪了，还要有足够的上下文来推进当前任务。即使对人来说，这也很难。

然后 Mihail 说：他刚才描述的这些，就是一个好的人类管理者每天在做的事。跟 Agent 没关系，这件事做好了，你也是一个优秀的团队经理。

他观察到，Agent 编排做得最好的那些人，往往有过管理人类开发团队的经验。他们在管理人的过程中学会了怎么在多个任务间切换、怎么分配注意力、怎么在信息不完整的情况下做出判断，然后把同样的原则用在了 Agent 身上。

## 什么是“Agent 友好的代码库”

Mihail 提出了一个概念：Agent 友好的代码库（agent-friendly codebase）。

核心问题是：如果把一个 Agent 放进你的代码库，它能理解正在发生什么吗？

他逐一拆解了几个要点。

### 测试是“合约”

当你让 Agent 在代码库里开发新功能时，它靠什么确认自己没有搞坏东西？靠测试。

测试是定义软件正确性的合约。如果你的测试覆盖不够，就等于没有给 Agent 立规矩。

> Agent 只能基于显式定义的合约来运作。如果你没有足够的测试覆盖，你就没有给你的软件定义合约。
> （“Agents only can operate on contracts, like explicitly defined contracts of software.”）

### README 和代码要一致

做过开发的人都知道，README 几乎一写完就和代码脱节了。代码说一回事，README 说另一回事。Agent 同时读到两个互相矛盾的描述，就会犯迷糊：到底该听谁的？

### Agent 会快速复合错误

如果 Agent 在第一步产生了一个误解，它看到自己第一步创建的错误代码后，不会纠正，而是在错误的基础上加倍错下去，像滚雪球一样放大，慢慢把代码变成一锅 “意面代码”（spaghetti code）。

所以最重要的是：Agent 看到的第一版代码必须是自洽的、设计完善的、测试充分的。

在你开始让 Agent 写代码之前，先把代码库本身搞对。

### 设计模式要一致

如果你的代码库中有一个地方用 API 1 来创建某种对象，另一个地方用 API 2 来创建同一种对象，Agent 不知道该选哪个。

但 Mihail 补了一句：

> 如果我走进你的代码库，看到两种不同的做法，我也会问自己：该用哪个？我不知道，两种都在用，我大概率会去问一个同事。
> （“If I were walking to your codebase and saw the two different ways of doing it, I would also ask myself: should I do one or two?”）

Agent 友好的代码库，其实就是对人也友好的代码库。

好的工程实践没有变，只是在 Agent 时代变成了硬性要求，而不是”最好这么做”的建议。

## 品味：功能性软件和卓越软件的分界线

什么把“能用的软件”和“了不起的软件”区分开？Mihail 的回答很直接：品味（taste）。

在他的课堂上，每个项目有基础要求，比如必须实现五个不同的功能流程。大多数人完成要求就停了。但有些学生不一样，他们已经拿到了满分，还在继续打磨、扩展功能、让应用更健壮。

> 品味的培养发生在最后一公里。
> （“The taste building happens in that last mile.”）

区别在于谁更想解决问题本身，而不只是拿到分数。

Mihail 说，课上表现最好的学生，现在有的已经在围绕课程项目创业了。课程结束了，但他们还在继续做同一个东西，因为他们觉得还有更多值得做的。

顶尖工程师不会在完成任务时停下来，他们在发现可能性时加速。

## 连 Anthropic 都在边做边学

谈到实验精神，Mihail 举了一个例子。Boris Cherny 来课堂演讲时提到，Anthropic 的 Claude Code 团队基本上每一两周就会用 Claude 重写 Claude Code 本身。他们用自己造的工具重写自己的工具。

即使是像 Anthropic 这样在构建最前沿 AI 编程工具的团队，也没有“全部答案”。他们自己也在不断实验、根据用户反馈迭代，摸索什么有效什么无效。

Mihail 在课堂上反复强调：我可以来这里给你推荐工具、分享我觉得什么好用。但归根结底你得自己去撞墙。

你得自己实验，看什么对你管用、什么不管用。把实验和试错变成工作流的一部分，这就是软件开发的新方式。

## 初级工程师的“无知无畏”是一种超能力

Mihail 指出，资深开发者往往是对 AI 工具最抗拒的人。写了 20 年代码的人太习惯自己的方式了，觉得“做这件事只有我一直以来的方法”。

而第一次进入行业的人完全不一样。他们像海绵一样，一切对他们来说都是新的，一切皆有可能。他们还没有被行业的种种困难“吓到过”。他们不知道医疗行业有多难，不知道金融监管有多严。他们只是看到一个问题，然后说：为什么我不去试试呢？

> 年轻人有一种“好的无知无畏”，这对创业者来说是完美的品质。
> （“There's like a good naivety to how young people think, which is perfect for a startup founder.”）

Mihail 认为，即便就业市场确实在变难，但那些最早掌握 AI 原生技能的人，恰恰就是这些初级工程师，最终会成为最灵活、学习最快的一批人。

## “开发者的傲慢”与过度工程化的陷阱

Mihail 还谈到了 CS 教育的本质。他认为软件开发教的是如何用数字化手段构建复杂系统、如何用算法去解决系统问题，更接近数学思维而非狭义的编程技能。

开发者有一种独特的心态，他称之为 “开发者的傲慢”：看到任何问题，第一反应就是软件能搞定。这种傲慢听起来像贬义词，但它其实是一种极其强大的驱动力。

但这种傲慢在 AI 时代有了新的风险。你让 Claude 做一个东西，再让 Codex 做一个东西，然后不断加功能。一个月过去了，你造出了一个精美绝伦、过度工程化的产品，上线之后发现没人要。

> 你造出了最精美的软件，工程过度得离谱，然后你发布了，没人想要它。
> （“You've built the most beautiful piece of software, it's crazy overengineered, and then you launch and nobody wants it.”）

AI 让构建变得太容易了。 容易到你可能忘了先验证有没有人需要你做的东西。

## Rem Koning：AI 原生组织的关键

视频最后，哈佛商学院副教授 Rem Koning 简短出镜，预告了下期内容。

> 注： Rem Koning 全名 Rembrand Koning，哈佛商学院副教授，研究方向是创业与 AI，Harvard D^3 研究所 Tech for All Lab 联合创始人。

他提出了几个值得思考的观点。

第一，“分配智能”的能力将越来越重要。 不是你自己有多聪明，而是你能不能把智能合理地配置到正确的位置。

第二，AI 原生组织的关键不是用 AI 来做你的工作，而是把 AI 嵌入产品本身，让 AI 直接和客户协作。最终目标是把人类从环节中移出去。

第三，当 AI 开始和 AI 对话、AI 开始彼此协作，它们需要什么？ Koning 认为，想清楚这个问题的公司，可能会成为万亿美元级别的企业。

Mihail Eric 在这 14 分钟里传达的核心信息可以浓缩为三条：

AI 原生工程师需要在传统功底之上叠加 Agent 编排能力；

代码库本身需要为 Agent 的到来做好准备，测试、一致性、文档缺一不可；

而在这个转型期，初级工程师的 “无知无畏”和灵活性反而可能是最被低估的资产。

问题是：从“写代码”到“管理 Agent”的转型过程中，谁会被留下，谁会被淘汰？

当 Agent 的能力继续提升，“管理 Agent”这个技能本身会不会也被自动化？

Mihail 没有给出答案，但他的课程和实践本身，就是对这个问题的一种探索。按照他自己的逻辑，答案大概率也在不断变化。

完整访谈视频：https://www.youtube.com/watch?v=wEsjK3Smovw

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme