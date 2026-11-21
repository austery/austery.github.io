---
author: Latent Space
date: '2026-02-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9QSm_mRGpN8
speaker: Latent Space
tags:
  - ai-evaluation
  - capability-explosion
  - developer-productivity
  - prediction-market
  - ai-safety
title: 衡量 AI 的指数级增长：专访 METR 研究员 Joel Becker
summary: 本期访谈深入探讨了 AI 评估机构 METR 的核心使命。研究员 Joel Becker 详细解释了著名的“时间线图表”如何衡量 AI 的自主能力，分析了从 GPT-4 到 Opus 4.5 的飞跃。对话涵盖了开发者生产力随机对照实验、预测市场的博弈论，以及闭环 R&D 自动化可能带来的风险。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Joel Becker
  - Sam Altman
companies_orgs:
  - METR
  - OpenAI
  - Anthropic
  - Manifold
products_models:
  - Opus 4.5
  - GPT-4
  - Claude Code
media_books: []
status: evergreen
---
### METR 的定义

**Joel Becker**: **METR** 的名字由两部分组成。前两个字母 **ME** 代表模型评估（Model Evaluation），即思考 AI 模型在今天和未来的能力，以及它们在具备一定能力后的行为倾向。最后两个字母 **TR** 代表威胁研究（Threat Research），我们试图将这些能力与特定的**威胁模型**联系起来，以确定 AI 是否会对社会造成巨大或灾难性的风险。

<details>
<summary>Original English</summary>

**Joel Becker**: METR stands for... first two letters, Model Evaluation. That is, we think about what their capabilities of AI models might look like today and tomorrow, as well as their propensities—what they'll actually do in the wild given that they have some level of capability. And then Threat Research, the final two letters. We try to connect those capabilities and propensities to particular threat models that we have in order to determine whether AI models pose enormous or catastrophic risks to society.

</details>

**Allesio**: 你觉得你们目前的工作是偏向 ME（评估）更多，而 TR（威胁研究）是下一个阶段，还是现在已经有 TR 方面的工作了？

<details>
<summary>Original English</summary>

**Allesio**: Would you say that you've done a lot more ME and TR is like kind of the next phase, or is there TR side of work that I'm [missing]?

</details>

**Joel Becker**: 我认为 TR 已经存在了。虽然最知名的工作可能看起来更像 ME，比如**时间线图表**（Time Horizon）和开发者生产力的**随机对照实验**（RCTs），但我们的网站上有一份关于 GPT-5 及其后续版本的完整报告。我们试图建立一个结构化的案例，分析为什么它目前不构成大规模风险。虽然结论是目前没有，但值得思考原因：为什么它在基准测试中得分很高，却无法做出严重错误的事情？我们发现目前的模型能力还不够。但在未来，当模型能够完成更非凡的任务时，我们就需要更多地依赖“倾向性”研究，即现有的防护措施是否足以防止它构成**生存威胁**。

<details>
<summary>Original English</summary>

**Joel Becker**: I think there is TR. Some of the most publicized work does look more like the ME—looks like this Time Horizon stuff and the developer productivity RCTs. But there's this wonderful full report on our website, GPT-5 report, trying to make this more structured case that it doesn't pose these really large scale risks. Eventually coming to the conclusion that it doesn't, but it's worth thinking: why exactly is that the case? Why is it not able to do something really enormously wrong? Well, we find it's not capable enough on the basis of some of this capabilities evidence. But perhaps in future, we will think it's capable of doing pretty extraordinary things, the kinds of things that would be necessary to provide really serious threats. And then maybe you'd lean more on the propensities part—are the protections that we have against these dangerous capabilities sufficient for it not to pose an existential threat?

</details>

### 时间线图表

**Swix**: “模型时间线图表”可能是被引用最多的图表。它的起源故事是什么？

<details>
<summary>Original English</summary>

**Swix**: The model Time Horizon chart is probably the most quoted... What was the origin story of it?

</details>

**Joel Becker**: 2023 年 METR 内部有一份试图规划研究愿景的 PPT，里面有一张草图：纵轴是自主能力或危险能力，横轴是时间或算力，上面有一些向右上方散射的数据点。我们后来的研究就是为了让这个图表更具体。当我们真正绘制出数据时——纵轴改为“人类完成任务所需的时间长度”，即模型能以 50% 可靠性完成的任务难度——我们发现趋势线异常笔直。这种规律性非常惊人，甚至比我加入 METR 前看到的那些零散的数据点还要直。

<details>
<summary>Original English</summary>

**Joel Becker**: There's this internal METR PowerPoint from 2023 where we're trying to lay out our ambitions for what METR research might look like. There's this graph. It has a y-axis that's some measure of autonomous capabilities or dangerous capabilities, and then an x-axis labeled time or compute. And then it has a bunch of sort of scattered points that kind of go up and to the right. Many of METR's research bets have been trying to make this ever more concrete. And then when we actually did the full thing, when we had this y-axis—which turned out to be this task difficulty as measured by the length of time it takes for humans to do at which models can complete these tasks with 50% reliability—when we actually plotted that data over time, it turned out to be remarkably straight.

</details>

### 任务筛选原则

**Allesio**: 你们是如何选择任务的？比如“训练分类器”或“修复 bug”，看起来有些随机。

<details>
<summary>Original English</summary>

**Allesio**: How did you pick the tasks? You have some labels like "train classifier", "fix bugs". They all seem kind of arbitrary. What's the process of task selection?

</details>

**Joel Becker**: 这是一个大家普遍关心的问题。我们的目标是选择具有经济价值的任务，特别是与通用自主权和**威胁模型**相关的任务。一个误读是认为这个图表代表了 AI 能完成的所有任务，但并非如此。例如，需要**计算机视觉**能力的任务，AI 今天的表现可能远不如不需要视觉的任务。我们通过内部人员创建任务和外部悬红（Bounty）来采样。为了能够大规模运行评估，我们倾向于选择可以自动评分的任务，这确实带来了一些限制，但这是我们的愿景。

<details>
<summary>Original English</summary>

**Joel Becker**: People are right to be worried about task selection. The aspiration was to pick economically valuable tasks relevant especially to sort of general autonomy and the threat models that we're primarily interested in. One misreading of the Time Horizon graph is this is referring to the full distribution of any tasks. In particular, tasks that are requiring of vision capabilities, they're probably much less capable today as measured by Time Horizon. We sample these tasks by having people inside of METR create them and by having a bounty so people from outside can provide them. In order to be able to scalably run our evals, it's helpful for the success on the tasks to be automatically gradable, which means some types of tasks are included and others are not.

</details>

**Allesio**: 除了计算机视觉，还有哪些任务是被排除在外的？

<details>
<summary>Original English</summary>

**Allesio**: Any other disqualifiers? What are other things where you would expect the chart to be a lot worse?

</details>

**Joel Becker**: 我们要求任务原则上是模型可以完成的，即它拥有足够的信息。我们的参考标准是：一个具备通用技能但缺乏特定背景知识的“低上下文人类”能否完成？这排除了一大部分现实工作，因为现实工作往往依赖于复杂的心理模型，而这些模型并不会完全写在 Issue 描述里。此外，我们的任务通常比较闭环，不像现实世界那样“杂乱”（Messy），比如需要与外部世界进行开放式互动。我们后续会聊到的开发者生产力研究中，那些任务就比 METR 的基准测试任务要杂乱得多。

<details>
<summary>Original English</summary>

**Joel Becker**: One thing is fairness—we want tasks to be in principle completable by a model. Could a low-context human who was sufficiently skilled at general skills, but maybe not the particulars in the background, be able to achieve success? That rules out a lot of real work because a lot of real work involves people having careful mental models of the situation that are not fully listed in an issue description. Another thing is that our tasks tend not to be so open-ended or interacting with the outside world—"messy", as we call it internally. Relative to tasks in the real world, our tasks are somewhat nicely scoped.

</details>

### Opus 4.5 与不连续性

**Swix**: 当 **Opus 4.5** 发布时，它在你们的图表上表现出了巨大的飞跃。这似乎打破了你们辛苦建立多年的趋势线。

<details>
<summary>Original English</summary>

**Swix**: Let's talk about Opus 4.5. There's a very big jump. You're the first people to call out how much better Opus 4.5 was than the status quo... But it broke your trend line.

</details>

**Joel Becker**: 确实。关于 Opus 4.5 是否符合每 4 个月能力翻倍（而不是我之前相信的 7 个月）存在争论。它在某种程度上证伪了我的趋势线。我看到很多顶尖工程师从对 AI 编码持挑剔态度，转变为几乎不亲手写一行代码。虽然这种飞跃在直觉上很大，但从多年来的算力和有效算力增长来看，进步依然是相对连续的。只是模型能力的惊人程度让我们觉得它是跃迁的。

<details>
<summary>Original English</summary>

**Joel Becker**: There was some speculation that maybe the appropriate trend line to use is this faster 4-month doubling time, which Opus 4.5 would be perfect for. I was more of a believer in 7 months, so it is kind of falsifying my trend line in some way. I've seen some of the most talented engineers I know go from being picky about not using AI for coding to practically not writing a line of code. In some ways, I think the story of Time Horizon is that progress has been remarkably continuous over so many orders of magnitude of compute. But yeah, model capabilities are astonishing.

</details>

**Swix**: 我同意你的看法。即使是很资深的开发人员，现在也开始转向 **Agentic Coding**（智能体编码）。去年这时候没人会说“我们团队要实现 100% 智能体编码，不写一行代码”。

<details>
<summary>Original English</summary>

**Swix**: I would cosign what you said there with even very senior developers being finally pilled into agentic coding. Now very serious people are telling me that they want to commit to 100% agentic coding, which is not something that you would have said a year ago.

</details>

### 开发者生产力研究的挑战

**Allesio**: 既然 Opus 4.5 这么强，你们之前的研究（认为 AI 可能减慢人类速度）是否失效了？你们会重做吗？

<details>
<summary>Original English</summary>

**Allesio**: How do you invalidate previous research? Take the developer productivity study—you had AI slowed people down. If you redo it with Opus 4.5, would you expect results to be dramatically different?

</details>

**Joel Becker**: 我们一直在后台重做。但现在做这个实验比过去难得多。首先是“样本偏差”：现在很难找到愿意在实验中被分配到“禁用 AI”组的开发者。其次是工作流的改变：现在的开发者习惯于同时处理多个 Issue，而传统的实验设计要求一次只做一个。2025 年 3 月的时候，人们还没这么多并发工作。所以重复同样的实验设计已经不可行了。

<details>
<summary>Original English</summary>

**Joel Becker**: We have been redoing it in the background. It is much harder to do it today. First, as AIs get better at coding, it's harder to find developers willing to be randomized to "AI disallowed". There's a selection issue. Second, a common workflow today is to work on multiple issues concurrently, which wasn't really true before. If you flip a single task to be AI allowed or disallowed, you're supposed to work on that single task. But that's not how developers are working today. These weren't threats to the previous study design in March 2025.

</details>

**Allesio**: 我现在用 **Claude Code** 进行审查和迭代，效率提升了很多，但我无法量化。你觉得人们是否高估了这种增速？

<details>
<summary>Original English</summary>

**Allesio**: Today I do a lot of just Claude Code and then review and iterate. It's much better and I don't know how to quantify it. People maybe overestimate... like 10x, but it's probably not right.

</details>

**Joel Becker**: 这里有几个问题。由于 AI 的存在，你可能会做一些以前根本不会去做的副作用项目（Side Projects），从这个角度看，加速是“无限大”的，但这些项目的经济价值可能较低。此外，人们对增速的预期往往过于乐观。正如我们在原始论文中记录的，人们往往没有意识到，他们能额外完成的任务价值其实比想象中低，否则他们以前就会想办法完成了。不过，我并不怀疑 AI 显著加快了即使是以前就会做的任务。

<details>
<summary>Original English</summary>

**Joel Becker**: There are a couple of side projects I have that I simply wouldn't be doing were it not for AI. In some sense, the speed up there is infinite, but these wouldn't really line up with additional value. I think that very bullish estimates of speed up today are inflated by what we document in that original paper—that people's expectations of speed up tend to be too optimistic. They also tend to be inflated by not quite grokking that the value of the additional tasks they're able to complete is lower than you might think. There's a reason they weren't doing them previously.

</details>

### 闭环自动化与能力爆炸

**Swix**: 你们提到了“能力爆炸”（Capabilities Explosion）。如果 AI 能够完全闭环地改进下一代 AI，情况会发生突变吗？

<details>
<summary>Original English</summary>

**Swix**: This concept of capability explosion... If you believe in emergence, it should be discontinuous in some sense.

</details>

**Joel Becker**: 这确实是我最担心的：如果 **AR&D**（人工智能研发）在实验室内部完全实现了自动化，那么能力爆炸的条件就成熟了。即使模型现在能完成 90% 的自动化，剩下的 10% 也是关键。有趣的是关于“仅限软件的智能爆炸”与“涉及硬件的循环”的争论。有人认为即使硬件固定，模型自我改进也能带来极端飞跃；也有人认为你需要闭环到芯片设计甚至芯片生产。如果芯片生产、软件改进和芯片设计这三个环节全部闭环，那将是非常令人担忧的。

<details>
<summary>Original English</summary>

**Joel Becker**: The thing that would really concern me is if AR&D was fully automated inside of a lab. The conditions are there for potentially a capabilities explosion. For things to be fully automated, 90% isn't enough; you need some full loop to be closed. Some people talk about software-only intelligence explosions—even holding hardware fixed, models improving themselves could lead to some extreme takeoff. Or instead, you need chip design or even chip production, and that's this larger loop that can close. Closing the chip production, software, and chip design loop is potentially very destabilizing.

</details>

**Allesio**: 那就是真正的“回形针工厂”了。如果 AI 被激励去制造自己的算力，它会把整个星球都变成芯片。

<details>
<summary>Original English</summary>

**Allesio**: I think that is the actual paperclip factory. If you incentivize a model to go build its own compute, it will turn the planet into chips.

</details>

### 预测市场的策略

**Swix**: 让我们聊聊 **Manifold** 预测市场。你是上面获利最多的交易员之一。你有什么秘诀吗？

<details>
<summary>Original English</summary>

**Swix**: Do we want to talk about Manifold? You were the most profitable trader... what is your secret for Manifold markets alpha?

</details>

**Joel Becker**: 听起来很牛，但其实主要是因为一个特定的慈善市场。Manifold 当时有一个项目，根据每月的捐赠金额开盘。我注意到作为一个会捐款的人，我可以操纵这个市场——通过增加捐赠来推高预期。我用大量的虚拟货币（Mana）买入高于线性预测的选项，人们因为没看到有人捐款而疯狂跟我对赌，我就一直加码。最后我确实捐了大约 5000 美元，从而赢取了大量的虚拟积分，成为了“最赚钱的交易员”。这在规则内是完全合法的。

<details>
<summary>Original English</summary>

**Joel Becker**: The secret... actually mostly comes down to this one market where Manifold had opened up a charity program. The market is on how much is going to be donated. I noticed that you could manipulate this market by giving more to charity. So the strategy was to put a ton of Mana into the option that was above the linear projection. People keep betting against you because it doesn't look like that's happening. Eventually they caught on that someone's going to make this donation to move over the edge. I ended up donating something like $5,000. I won lots of fake internet points and became the number one most profitable trader.

</details>

**Allesio**: 这就是所谓的“高主体性”预测市场，你亲自去创造未来。

<details>
<summary>Original English</summary>

**Allesio**: This is called prediction markets with high agency—you actually going [and making] the future what you make it.

</details>

### 总结与愿景

**Joel Becker**: 到 2026 年，你会看到 METR 提供更多高质量的能力证据。我们还在研究监控技术（Safeguards），即能否在模型尝试危险任务时成功应用防护措施。此外，METR 正在**招聘**研究工程师、研究科学家和运营总监。我们不只看 AI 背景，也欢迎有初创公司经验或经济学背景、能够脚踏实地完成前沿科学工作的人。

<details>
<summary>Original English</summary>

**Joel Becker**: From METR, I think you're going to see more hopefully high quality capabilities evidence. We also have some monitoring research directions—thinking about if we can successfully apply safeguards to models attempting dangerous tasks. Maybe now is a good time to say that we are hiring. On my team, we're hiring for research engineers, research scientists, people from startup backgrounds. We are accepting a pretty wide range of people who get stuff done.

</details>

**Allesio**: 最后一个关于**卡拉 OK** 的问题，听说你经常组织这类活动？

<details>
<summary>Original English</summary>

**Allesio**: Did you have a karaoke question? What is this karaoke thing that you organize?

</details>

**Joel Becker**: 是的，我主持过几次现场乐队卡拉 OK。虽然 AI 生成歌曲很强，但我认为在现场唱歌有一种“超越感”，这是 AI 无法提供的。我期待在下一次活动中见到你们。

<details>
<summary>Original English</summary>

**Joel Becker**: I've hosted a couple of these live band karaoke events. I think there's kind of transcendence to singing in person that the AI generator songs are not providing me. I look forward to seeing you both at the next one.

</details>