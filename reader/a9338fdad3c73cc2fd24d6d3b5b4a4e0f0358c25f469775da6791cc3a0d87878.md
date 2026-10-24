---
author: The Pragmatic Engineer
date: '2026-03-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=julbw1JuAz0
speaker: The Pragmatic Engineer
tags:
  - ai-agent-workflow
  - autonomous-coding
  - software-engineering-productivity
  - agentic-security
  - human-in-the-loop
title: 对话 Claude Code 之父 Boris Cherny：AI 时代的‘印刷机’革命与工程师的进化
summary: Anthropic 工程师 Boris Cherny 深度解析了 Claude Code 的诞生与演进。他分享了如何在 AI 辅助下实现日均提交 30 个 PR 且零手写代码的高效工作流，提出了 AI 编码如同 14 世纪印刷机革命的深刻类比，并探讨了工程师如何从‘抄写员’转型为‘作者’，以及通用型工程师在 AI 时代的独特优势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Boris Cherny
companies_orgs:
  - Anthropic
  - Meta
  - OpenAI
  - Statsig
  - Sonar
  - Work OS
products_models:
  - Claude Code
  - Claude 4.5
  - Claude 4.6
  - Claude Co-work
  - TypeScript
media_books:
  - Accelerando
  - Three-Body Problem
  - Functional Programming in Scala
status: evergreen
---
### AI 编码的“印刷机”时刻

**[主持人]**: 你曾经为 O'Reilly 编写了第一本 **TypeScript** 书籍。

<details>
<summary>Original English</summary>

**[Host]**: You were the first ever TypeScript book with O'Reilly.

</details>

**Boris Cherny**: 是的，我曾在日本的一个小镇上看到那本书的日文版，那真是一个超酷的时刻。但随后我意识到，我已经完全不记得 TypeScript 了。现在我们已经到了这样一个阶段：在 **Anthropic**，平均约 80% 的代码是由 **Claude Code** 编写的。我每天大概会提交 10 到 20 个 PR，而在 **Opus 4.5** 和 Claude Code 的帮助下，每一个 PR 的代码 100% 都是由它们完成的，我一行代码都没有手动改过。

<details>
<summary>Original English</summary>

**Boris Cherny**: Yeah, I found that book translated in Japanese in this little town in Japan. That was just the coolest moment. And then I realized I don't remember TypeScript at all. Now we're at the point where Quad Code writes, I think something like 80% of the code had Enthropic on average. I wrote maybe 10 20 p requests every day. Opus 4.5 and Quad Code wrote 100% of every single one. I didn't edit a single line manually.

</details>

**[主持人]**: **Andrej Karpathy** 曾发帖说，作为一名程序员，他从未感到像现在这样落后。

<details>
<summary>Original English</summary>

**[Host]**: Andre Karpathy posted that he's never felt as much behind as a programmer as he is now.

</details>

**Boris Cherny**: 这也是我一直在挣扎的事情。模型改进的速度如此之快，以至于旧模型行之有效的想法在现有的新模型上可能不再奏效。我对当前这个时刻有一个比喻：它是 1400 年代的**印刷机**时刻。因为当时有一群专门负责书写的**抄写员**。

<details>
<summary>Original English</summary>

**Boris Cherny**: This is something I really struggle with. The model is improving so quickly that the ideas that worked with the old model might not work with the new model. One metaphor I have for this moment in time is the printing press in the 1400s because there was a group of scribes that knew how to write.

</details>

**[主持人]**: 雇佣这些抄写员的一些国王甚至自己都是文盲。

<details>
<summary>Original English</summary>

**[Host]**: Some of the kings were illiterate who are employing the scribes.

</details>

**Boris Cherny**: 如果你思考一下那些抄写员后来的遭遇：他们不再是抄写员了，但现在出现了一个全新的类别——**作家和作者**。这些人现在之所以存在，是因为文学市场的规模瞬间扩大了无数倍。

<details>
<summary>Original English</summary>

**Boris Cherny**: And if you think about what happened to the scribes, they ceased to become scribes, but now there's a category of writers and authors. These people now exist. And the reason they exist is because the market for literature just expanded a ton.

</details>

### 早期黑客经历：从计算器到 YC 创业

**Boris Cherny**: 这一切要追溯到很久以前。我大概 13 岁左右开始在 eBay 上卖旧的宝可梦卡片，并发现可以编写 **HTML** 来装饰列表。后来在中学，我们使用 **TI-83** 图形计算器。我发现如果我把数学考试的答案编进计算器，我就能拿到更好的分数。于是我写了一些小程序来记录答案，后来考试变难了，我就得写解方程程序（solvers）。最后为了让程序运行得更快，我不得不从 Basic 降级到**汇编语言（Assembly）**。

<details>
<summary>Original English</summary>

**Boris Cherny**: It starts a while back. So, when I was maybe 13 or something like this, I started selling my old Pokemon cards on eBay. And I realized that on on eBay, you can actually like write HTML... Then the second thing was... we had these old TI83 graphing calculators... I wrote these little programs to just program the answers... then the math got more advanced... so I had to drop down from basic to assembly to just make the program run a little bit faster.

</details>

**[主持人]**: 哇，你在中学就开始写汇编了。

<details>
<summary>Original English</summary>

**[Host]**: Oh wow. So like in high school you dropped down to assembly.

</details>

**Boris Cherny**: 当时班里每个人都想要我的解题器，于是我买了一根串口线把程序传给他们。结果下一次数学考试全班都是 A，老师气疯了。对我来说，编程一直是非常**实用**的工具。我在大学学的是经济学，后来为了创业退学了。我从未想过编程会成为一种职业，它只是我用来构建有用东西的一种手段。

<details>
<summary>Original English</summary>

**Boris Cherny**: Then the thing I realized is everyone in my class was starting to realize that I had the solver... so I bought this little serial cable... then the next math test, everyone on the class just got A's... But for me, it was very practical. Coding is a means to build things and to to make useful things.

</details>

### Meta 的七年：构建世界级开发工具

**Boris Cherny**: 我在 Meta（当时的 Facebook）待了七年。起初在 **Facebook Groups** 团队工作，那时我遇到了很多早期的 JavaScript 大拿。后来我去了 **Instagram**，发现那里的技术栈非常混乱——Python 的类型检查器不起作用，点击跳转定义也不行。于是我开始转做**开发基础设施（Dev Infra）**，负责代码质量。在离开 Meta 之前，我领导着全公司的** Better Engineering** 计划。

<details>
<summary>Original English</summary>

**Boris Cherny**: Yeah, so I started on Facebook groups... I was really excited about it because of this mission of connecting people to their community... Then I spent a few years at Instagram after... what I very quickly realized is that I was just not effective at working on the stack because it was such a terrible stack and so I just went and started working on Dev Infra... By the time I left, I was leading code quality for all of Meta.

</details>

**[主持人]**: 听说马克·扎克伯格曾强制要求每个工程师投入 20% 的时间来修复技术债务？

<details>
<summary>Original English</summary>

**[Host]**: Zuck mandated that every engineer at the company 20% of their time has to be spent fixing tech debt.

</details>

**Boris Cherny**: 没错，我们称之为“Better Engineering”。我们通过**因果分析（Causal Analysis）**发现，代码质量对工程效率有两位数百分比的提升。即使在最大的规模下，一个干净、模块化的代码库对于工程师和现在的 **LLM** 模型来说都至关重要。如果代码库中充斥着多种废弃的框架，模型就很可能选错工具。

<details>
<summary>Original English</summary>

**Boris Cherny**: And we called this better engineering... quality actually contributes like you know double digit percent to to productivity. It turns out even even at the biggest scale... As a model, you might just pick the wrong thing and then, you know, like the user has to course correct you.

</details>

### Claude Code 的诞生：从副作用到核心工具

**Boris Cherny**: 我加入 Anthropic 后，提交的第一份 PR 被 Adam Wolf 拒绝了。不是因为代码写得不好，而是因为我是**手动编写**的。他告诉我：“你应该用 **Clyde**（Claude Code 的前身）来写。”那时候 Clyde 还非常简陋，是用 Python 写的，启动要 40 秒，而且不是智能体化的。但当我配置好参数让它一键生成了一个可运行的 PR 时，我体验到了第一个“哇”的时刻。

<details>
<summary>Original English</summary>

**Boris Cherny**: When I joined Anthropic, I did a bunch of ramp up projects... and I wrote my first pull request by hand because I thought that's how you write code... But even at the time... there was this thing called Clyde... Adam rejected my PR and he was like, "Actually, you should use this Clyde thing for it instead." ...it sped out a working PR. It just one-shotted it.

</details>

**Boris Cherny**: 后来我开始实验如何使用 Anthropic 的公共 API。我不想做 UI，就写了一个终端里的聊天工具。当**工具调用（Tool Use）**功能发布后，我给它增加了一个 **Bash** 工具。我问它：“我正在听什么音乐？”它直接写了一个 AppleScript 脚本去查询我的音乐播放器。那是我的第二个“哇”时刻：如果你给模型一个工具，它会自己想办法利用它去完成任务。这就是**苦涩的教训（Bitter Lesson）**的一个推论：让模型去做它该做的事，不要试图把它困在框里。

<details>
<summary>Original English</summary>

**Boris Cherny**: I just wanted to, you know, hack something up quite quickly cuz we didn't have quad code back then... and I gave it a single tool which was the bash tool... and I asked it you know like I actually didn't know if it could even do this but I asked it like what music am I listening to and uh it just wrote a little Apple script program... This is one of the corollaries is just let the model do it do its thing. Don't try to put it in a box.

</details>

### 极限效率：日均 30 个 PR 的工作流

**Boris Cherny**: 我的工作流通常是开 5 个终端标签页，每个都对应一个不同的代码分支。我几乎总是使用 `plan` 模式。当一个 agent 在第一个标签页里执行计划时，我就跳到第二个、第三个。随着 **Opus 4.5** 和 **4.6** 的发布，模型几乎可以“一键（one-shot）”完成实现。我现在甚至已经卸载了 IDE，因为我根本不需要手动编辑代码了。

<details>
<summary>Original English</summary>

**Boris Cherny**: So for me, the way that I do it generally is I have five terminal tabs. Each one of them has a checkout of their repository... Almost every time I start in plane mode... Once there is a good plan, it just it will oneshot the implementation almost every time... I just uninstalled my ID cuz cuz I just didn't need it at that point.

</details>

**[主持人]**: 如果每天提交 20 到 30 个 PR，代码审查（Code Review）怎么处理？

<details>
<summary>Original English</summary>

**[Host]**: Shipping this much code... The obvious question that comes up is well the review.

</details>

**Boris Cherny**: 在 Anthropic，每一份 PR 都会先由 Claude Code 进行第一轮审查，它能捕捉到大约 80% 的 Bug。它还会自己运行测试、甚至在子进程里启动自己来进行**端到端验证**。但最后，必须有一个人类工程师进行二次审查并批准更改。我们现在已经实现了“自动化自我（Automate myself away）”，工程师应该从繁琐的重复劳动中解放出来。

<details>
<summary>Original English</summary>

**Boris Cherny**: So today the way this looks is... every pull request at Enthropic is code reviewed by quad code. Uh and that actually catches maybe like 80% of bugs... There's always an engineer that does the second pass of code review. Um and you know there there always has to be a person in the loop approving the change.

</details>

### 智能体团队：分布式协作的未来

**Boris Cherny**: 我们最近推出了 **Agent Teams**，这是我们对“智能体集群（Swarms）”的实现。它允许一个主智能体将任务委托给具有“非相关上下文窗口（Uncorrelated Context Windows）”的子智能体。这意味着子智能体不携带主对话的沉重负担，能够更专注、更高效地处理具体任务。我们之前尝试过 **RAG（检索增强生成）**，但最终发现这种基于工具的“智能体化搜索（Agentic Search）”——也就是让模型自己去用 `glob` 和 `grep`——效果反而更好。

<details>
<summary>Original English</summary>

**Boris Cherny**: We launched agent teams earlier this week. This is our implementation of swarms... You have a bunch of different uncorrelated context windows... It's uncorrelated because the main agent prompts the sub agent but the sub agents context window is fresh... it turned out that agentic search just outperformed everything and when I say agentic search, this is a fancy word for glob and grap. That's all it is.

</details>

### 工程师的未来：从“抄写员”到“作者”

**Boris Cherny**: 对于工程师来说，那些关于代码风格、语言选择的争论已经不再重要了，因为模型可以随时帮你重写。现在最宝贵的技能是**好奇心**和**跨界能力**。未来的“十亿美金产品”可能只由一个人打造，因为他能同时思考工程、设计、业务和财务。今年将是**通用型人才（Generalist）**的元年。

<details>
<summary>Original English</summary>

**Boris Cherny**: Okay, so the stuff that's left behind is maybe like very strong opinions about like code style and languages... Other skills that I think are more valuable are being curious and being open to doing things beyond your swim lane... So in in some ways I think this will be the year of the generalist.

</details>

**Boris Cherny**: 即使编程语言不再是门槛，我仍然推荐去读一读《**Scala 函数式编程**》。学习如何“在类型中思考（thinking in types）”是一门艺术，它能让你成为更好的思考者。此外，我还推荐刘慈欣的《三体》和 Charles Stross 的《**Accelerando**》，后者简直就是未来 50 年的技术路线图。

<details>
<summary>Original English</summary>

**Boris Cherny**: And then on the technical side, I would strongly recommend functional programming in Scola... it'll just teach you how to think in types... For people that are new to sci-fi... I really love Accelerondo by St. This is a book I would totally recommend. It's like essentially the product roadmap for the next 50 years.

</details>