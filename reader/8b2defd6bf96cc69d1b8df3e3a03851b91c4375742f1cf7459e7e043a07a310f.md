---
author: Internet of Bugs
date: '2026-05-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=E_xN-uC-lT0
speaker: Internet of Bugs
tags:
  - developer-productivity
  - software-quality
  - ai-tokenomics
  - technical-metrics
  - ai-feedback-loop
title: Tokenmaxxing：程序员生产力的荒诞指标与 AI 泡沫的投机真相
summary: 本文深入剖析了近期出现的 'Tokenmaxxing' 概念——一种强迫程序员最大化 AI Token 使用量的所谓指标。资深工程师 Carl 指出，这不仅是软件工程史上最糟糕的生产力衡量标准，更是 AI 巨头与风险投资公司为了消耗 Token、美化 IPO 财报、利用员工输出‘废料’训练模型的阴谋。文章探讨了代码质量的本质、死代码的致命风险，以及为何真实的生产力反馈回路在现有商业评估体系中难以落地。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Jensen Huang
companies_orgs:
  - Nvidia
  - Andreessen Horowitz
  - The New York Times
  - Meta
  - Shopify
  - Amazon
  - Knight Capital Group
products_models:
  - xAI
media_books: []
status: evergreen
---
### 资本推手下的 "Tokenmaxxing"：一场针对程序员的荒诞实验

近期在软件工程领域出现了一个极具争议的概念：**Tokenmaxxing**（Tokenmaxxing：一种主张程序员应尽可能消耗更多 AI Token 以体现其生产力的评价指标）。这种观点认为，程序员每天消耗的 Token 越多，就代表其越具生产力，而未能达到 Token 消耗上限的工程师则被视为工作不力。这一想法并非空穴来风，而是由一系列极具影响力的资本力量在背后推动。

**黄仁勋**（Jensen Huang: Nvidia 创始人，AI 硬件竞赛的最大受益者）在 2026 年 3 月 19 日的 **All-In podcast** 中公开表示，如果一个工程师没有消耗足够的 Token，他会感到担忧。紧接着，**《纽约时报》**（The New York Times）在 3 月 20 日撰文将“最大化 Token 预算”的概念大众化。而到了 3 月 23 日，深度参与 AI 泡沫投资的顶级风险投资公司 **Andreessen Horowitz**（a16z）发布了一封致软件公司 CEO、创始人和董事会的公开信《软件仅剩的两条路》，极力兜售由 AI 驱动的开发者生产力指标。某些公司甚至设置了排行榜，公开展示哪些程序员消耗的 Token 最多。这种将程序员视为缺乏自主性和创造力的计件劳工的行为，是过去 30 多年软件工程史上最令人担忧的退步。

<details>
<summary>Original English Source</summary>

So today, I'm going to talk about "tokenmaxxing", which is this stupid new idea that programmers should max out the number of tokens they use every day, or if not max them out, at least use as many as they possibly can, and that any programmer who doesn't max out their token uses isn't being as productive as they should be.

Jensen Huang, from Nvidia, who makes more money on AI than any other company, was on the All-In podcast on March 19th, saying that he would be alarmed if an engineer wasn't using enough tokens, and then March 20th, an article from The New York Times popularized the idea of maxing on token budgets, and then on March 23rd, the most prestigious venture capital firm, who is HEAVILY invested in the AI bubble, published a letter, quote, "to software CEOs, founders, boards, and the investor community," unquote, called, quote, "There are only two paths left for software," unquote, in which they push the idea of AI-driven developer productivity.

Some companies are even putting up leaderboards to show which programmers are burning through the most tokens. Now, I have no hesitation in saying that's an incredibly counterproductive way to incentivize for real productivity. It's just yet another, and arguably the worst, attempt to turn programmers into micromanage laborers with no agency or opportunities for creativity I've seen in 30-something years.

</details>

### 质量的本质：为什么更多的代码往往意味着更糟的软件

关于程序员生产力的衡量，必须明确一个核心共识：**并非所有的代码都是好代码**。除了那些在任何情况下都不能使用的极烂代码外，代码质量本质上是情境化的（Situational）。只有当代码在被调用的特定环境下完成了其应该完成的任务时，它才是好代码。

软件工程中最困难且最关键的部分在于：
*   **预测各种调用条件**：准确识别代码块可能被调用的所有不同情境。
*   **跨组件协调**：确保当前编写的代码与周围所有其他代码的逻辑保持一致。
*   **对抗性环境**：时刻防范攻击者（Hackers）通过构造恶意的特殊情境来利用代码漏洞。

在任何情况下，单纯通过更快速地编写更多代码，都无法让上述过程变得更好。事实上，大多数难以定位的漏洞，其根源正是代码在程序员未预料到的情境下被调用了。

<details>
<summary>Original English Source</summary>

"Not all code is good code." In fact, some code is bad code, in addition, with the exception of code that's so bad it should never be used under any circumstances. All code quality is situational. Code can only be good if it does what needs to be done in the situation in which the code is called. 

And that's one of the most crucial and most difficult parts of writing code: anticipating all the different conditions under which the code being written might be called, what the right thing to do is in each of those situations - in coordination with all the things being done in that situation by all the other code around the code currently being written - and then doing all that while keeping in mind that there are people out there, often referred to as hackers, who will intentionally try to force your code to encounter malicious situations so they can try to take financial advantage of what it does wrong. Under no circumstances does writing more code faster make that process any easier or better. In fact, quite the opposite.

</details>

### 指标的陷阱：从“代码行数”到“Tokenmaxxing”的退化

管理层总是倾向于寻找易于衡量的指标，但在软件领域，这些指标往往具有误导性。

1.  **代码行数**（Lines of Code: 传统的生产力衡量单位）：由于无法自动区分“好行”和“坏行”，这是一种极其糟糕的度量方式。
2.  **测试覆盖率**（Test Coverage: 自动化测试覆盖的代码行百分比）：虽然略好，但仅在测试本身正确、彻底且准确模拟了真实世界情境时才有意义。
3.  **故事点/T恤尺码**（Story Points / T-shirt Sizes: 敏捷开发中用于评估任务复杂度的抽象单位）：它们试图在预期功能的语境下衡量代码，虽然不完美，但至少有所尝试。
4.  **Tokenmaxxing**：这是有史以来最荒唐的指标。它相当于以最大化代码行数为目标，且每一行代码都会直接向公司计费。

这里适用**古德哈特定律**（Goodhart's Law: 当一个指标变成目标时，它就不再是一个好指标了）。当程序员为了满足指标而博弈系统（Game the system）时，公司不仅会得到低质量的代码，还必须向 AI 供应商支付巨额费用。

<details>
<summary>Original English Source</summary>

Counting the lines of code a person or team writes in a certain period of time is a very easy thing to measure, so people often use it as a metric. But it's a horrific measure of productivity. Because to do that correctly, lines of good code should add to your score, but lines of bad code should be deducted from your score, but there's no easy way to tell what lines of code are which.

Another attempt at metrics are "story points" or "t-shirt sizes" or "planning poker" or whatever crap method you use to try to estimate the size of a piece of functionality. It does, I guess, approximate productivity better than just counting lines of code.

But "tokenmaxxing", it's literally the worst metric for measuring good programming I've ever heard of. Goodhart's law tells us that when people start being judged based on a metric, it ceases to be a good metric because people will game the system. But with this nightmare, the more people game the system, the more companies who are pushing the metrics have to pay their AI vendor, which I guess is great revenue if you're the AI vendor, but not so great for everyone else's finances though.

</details>

### 巨头的真实目的：利用员工作为“数据肉盾”训练模型

为什么 **Meta**、**Shopify** 和 **Amazon** 这样的大公司会推动这种指标？真正的动机可能在于**内部 AI 模型训练**。目前，公网上的高质量训练数据已近枯竭。如果公司能追踪程序员如何通过 AI 生成输出，并在现实中使用、提炼和修改这些输出，这些反馈数据（Feedback Data）就成了极具价值的训练素材。

这本质上是一场豪赌：
这些公司正在下注，认为当前由 AI 产生的**劣质代码**（Slop: AI 生成的低质量、冗余或充满漏洞的输出）给客户造成的短期损失和漏洞痛苦，将小于未来拥有更训练有素的模型所带来的长期收益。但这忽略了由于跟风而盲目模仿大公司的中小企业的处境，这种“大厂迷信”在软件行业屡见不鲜，就像当年盲目照搬 LeetCode 面试、敏捷开发（Agile）或 Pull Request（PR：原本用于开源管理的门槛接口，现已成为内部开发标准）一样，缺乏对自身业务情境的审视。

<details>
<summary>Original English Source</summary>

So some of the earliest companies who are reported to be doing this, like Meta and Shopify and Amazon, are probably pushing this metric for purposes of training their in-house AIs. In theory, if you could take the output of your AI and then track how that output gets refined and changed as it gets used in the real world, and then add that tracking and change information back into the model, that could become good training data.

Now there's a bet there: Those companies are betting that the pain caused by the bugs that your current customers are feeling now because of the slop that your current AI is pushing to your production environment will be smaller than the gain that you get later from having better trained models in the future. I'll be honest, it sounds like a bad bet to me, but time will tell.

Now some other companies aren't training their own AIs, and they're doing it because they aspirationally mimic everything that they read about the big companies doing, without having a clue as to whether the reasons the big companies are doing it apply to the smaller companies or not.

</details>

### 死代码的致命代价：Knight Capital 的 4.4 亿美元教训

Tokenmaxxing 必然会导致大量未经验证、甚至从未运行过的代码被推向生产环境。这引出了软件工程的一个核心准则：**永远不要发布死代码**（Dead Code: 存在于库中但逻辑上不被执行的代码）。

一个极端的案例是 2012 年的 **Knight Capital Group 崩溃事件**。该公司因一段隐藏在**功能开关**（Feature Flag：通过配置动态控制功能开启的技术）后的、本不应运行的代码由于实现漏洞被意外触发，导致在极短时间内损失了 4.4 亿美元。死代码在生产环境中绝非无害，它会误导后续的程序员进行错误的调用或复制，从而埋下未知的炸弹。

<details>
<summary>Original English Source</summary>

And what was REALLY fun was when idiots just wrote a bunch of code they never actually ran and stuck it in the code base without ever calling it just to get credit for the lines, which often leads to some other idiot assuming that that code - since it's in production - works and either copies it and pastes it in somewhere else or calls into it expecting it to do what it says it's going to do.

So a quick word of advice, don't ever, ever ship dead code. The largest amount of real money ever lost to a bug, $440 million, was because a code hidden behind a feature flag that was not supposed to be run, but there was a bug in the way the feature flag was implemented. It's the 2012 Knight Capital Group meltdown.

</details>

### 回溯性修正：真正有效的生产力评估方法

如果 Tokenmaxxing 是错误的，那么什么是正确的评估方式？答案是**追溯性减分机制**。在每次代码变更（特别是修复 Bug）时，应当回溯原始代码的编写者，从其生产力评分中扣除该 Bug 修复所需的成本。

然而，这种方法在商业现实中举步维艰：
*   **管理层抵制**：这意味着每个 Bug 修复都需要花费额外的时间进行追溯，拉低了账面上的产出速度。
*   **程序员厌恶**：程序员通常讨厌处理繁琐的文书工作和对历史决定的复盘。
*   **会计制度限制**：现代企业的 bonus 或 raise 评估通常以固定周期（如季度）为界，不支持对过去已结算周期的指标进行追溯修订。

但只有那些真正花时间进行“回看”练习，理解当初的决策如何导致了今天的 Bug 的人，才能学到最宝贵的工程技能。而这种技能，无论是 Tokenmaxxing 还是 AI，都无法习得。

<details>
<summary>Original English Source</summary>

The answer is to allocate time on every code change, especially bug fixes, to be spent looking back at the code that was changed and deducting the value of the current bug fix from the metric score for the original code.

Now people hate this. First off, management hates it because it means that everything takes more time. Programmers hate it because it means more paperwork time and less programming time. But the exceedingly rare people that do manage to do this "looking back" exercise, those people learn incredibly valuable skills that, in my experience, just can't be taught or learned any other way. And those skills certainly can't be learned by "tokenmaxxing", and the AI has no chance of learning from any kind of such exercise.

</details>

### 尾声：IPO 的烟雾弹与泡沫的终章

Tokenmaxxing 热潮预计很快会因高昂的成本而消退。然而，更深层的担忧在于：AI 公司是否会在热潮退去前，利用这笔人为创造的营收来支撑其 **IPO** 财务报表？

即将到来的 **xAI** 与 SpaceX 的复杂合并（被称为“科学怪人”式整合）将是 AI 泡沫的一个关键节点。如果 IPO 获得足够资金，泡沫可能还会持续。在 **Anthropic** 与 xAI 之间、以及 **NASDAQ** 临时修改规则的过程中，隐藏着大量的财务异常。在这个充斥着 Bug 的互联网世界里，当有人向你推销一个完美的、由 Token 驱动的生产力未来时，请记住：他们很可能只是在推销自己的新股。

<details>
<summary>Original English Source</summary>

Personally, I expect the "tokenmaxxing" fever will die off. I've already started to see reports of companies complaining about how expensive it is. The question is, "will the fever die down before or after the AI companies use the revenue they get from it to prop up their IPO paperwork?"

These upcoming IPOs, starting with the Frankenstein X.AI and SpaceX conglomeration in a few weeks, are going to be a Groundhog Day event for the AI bubble. There are others, including the financial irregularities going on between Anthropic and X.AI, the way that NASDAQ is changing its rules right in time for the series of IPOs. Please at least remember that the Internet is full of too many bugs already, and anyone who says different might well be trying to sell you their new IPO.

</details>