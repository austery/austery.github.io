---
author: Latent Space
date: '2026-04-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=RrkGoX3Cw7o
speaker: Latent Space
tags:
  - ai-workflow
  - auto-research
  - simulation-learning
  - distillation
  - ci-cd
title: AI 速度下的 CI/CD 变革：Shopify CTO 深度解析 Tangle、SimGym 与 Liquid AI 实践
summary: Shopify CTO Mikhail Parakhin 详细介绍了 Shopify 如何利用 AI 重塑工程工作流。重点讨论了第三代数据处理系统 Tangle、自动研究循环 Tangent 以及基于十年历史数据的客户模拟器 SimGym。此外，还分享了 Shopify 在生产环境中使用 Liquid AI 非变换器架构实现超低延迟搜索的实战经验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Mikhail Parakhin
companies_orgs:
  - Shopify
  - Microsoft
  - NVIDIA
  - Liquid AI
products_models:
  - Tangle
  - Tangent
  - SimGym
  - GPT-4o
  - Liquid Neural Networks
media_books: []
status: evergreen
---
### AI 时代的代币消耗与工程质量

**Sean**: 我确实认为 **Jensen Huang**（黄仁勋）最近受到了一些负面评价。他曾说，如果一个年薪 50 万美元的工程师在年底时，你问他花了多少代币，如果他说只花了 5000 美元，那我会非常生气。

**Mikhail Parakhin**: 是的，但我认为那些批评是不公平的，他其实是对的。我认为他在大方向上是完全正确的。

<details>
<summary>Original English</summary>

**Sean**: I do think Jensen gotten a lot of bad press. That $500,000 engineer at the end of the year, I'm going to ask him how many token how much did you spend in tokens? If that person said $5,000, I will go ape something else.

**Mikhail Parakhin**: Yes, but uh I actually think that's undeserved. I think he he is actually right. Uh I do think he's directionally correct.

</details>

**Mikhail Parakhin**: 我们通过反复试验学到了两件非常重要的事情。第一，这不仅仅是消耗代币的问题。你可以消耗很多代币，但最典型的**反模式**是在没有相互沟通的情况下并行运行过多的 **Agent**。与少数高效燃烧代币的 Agent 相比，那种做法几乎是徒劳的。我们需要建立正确的**批判循环（Critique Loop）**，特别是使用高质量模型：一个 Agent 执行任务，另一个（最好使用不同的模型）对其进行批判。这确实需要更长的时间，人们可能不喜欢，因为延迟增加了，他们必须等待这场“辩论”完成。但最终生成的**代码质量要高得多**。

<details>
<summary>Original English</summary>

**Mikhail Parakhin**: The thing that I do want to say and this is something that we learned through trial and error and very important is like two things. One is that it's not about just consuming tokens. Uh you can consume tokens and and in fact the antiattern is running multiple agents too many agents in parallel that don't communicate with each other. that's almost useless uh compared to just fewer agents and burns tokens very efficiently. uh setting up the right critique loop, especially with the high quality models where one agent does something, the other one ideally with a different model critiques it. It takes much longer. So people don't like it cuz latency goes up. You know, they they have to wait till this debate is happening. But uh the quality of the code is much higher.

</details>

### Shopify 的 AI 工具普及率与模型选择

**Sean**: 好的，我们现在在远程演播室，对话嘉宾是 Shopify 的 CTO **Mikhail Parakhin**。欢迎。

**Mikhail Parakhin**: 谢谢。

**Sean**: 你们团队准备了一些图表，我们来看看。这里有一个内部 AI 工具的采用率图表，我们看到的是什么？

**Mikhail Parakhin**: 这是一个非常有趣的统计数据，显示的是**日活跃工作者（DAO）**占公司总人数的百分比。你可以看到两点：第一，绿色曲线（总计）现在已经接近 **100%**。现在的局面是，如果你不深入使用至少一种 AI 工具，几乎无法完成工作。第二，去年 12 月是一个明显的**相位转变（Phase Transition）**点，模型突然变得足够好，一切都爆发式增长了。

<details>
<summary>Original English</summary>

**Sean**: Okay, we're here in a studio, a remote studio with Muel Parkin, CTO of Shopify. Welcome.

**Mikhail Parakhin**: Thank you. Welcome.

**Sean**: Your team kindly prepared some slides actually... So here we have uh an internal AI tool adoption chart. What are we looking at here?

**Mikhail Parakhin**: Yeah, this is very interesting statistics. Uh this is number of daily active workers. You know, think of DAO basically daily active users of AI tool as a percentage of all the people in the company... one is the greenest total... it approaches really 100% by now. It's hard not to do your job now without interacting deeply at least with one tool. You could see another interesting thing is just as many people commented in December was the phase transition when suddenly models gotten good enough that that everything took off and started growing.

</details>

**Mikhail Parakhin**: 另一个趋势是，基于 **CLI** 的工具和不要求你时刻盯着代码的工具变得越来越流行。虽然像 **GitHub Copilot** 或 **Cursor** 这样需要 IDE 的工具并没有萎缩，但它们的增长速度没有内部 Agent 工具那么快。在 Shopify，我们鼓励每个人完成任务，可以使用任何工具，代币预算实际上是**无限制**的。但我们会通过底层控制模型选择，基本上不允许使用低于 **GPT-4o** 水平的模型。

<details>
<summary>Original English</summary>

**Mikhail Parakhin**: The other thing I would claim you could see is that uh CLI based tools and tools that don't require you to look at the code becoming more popular... tools that require ID such as uh GitHub copilot or cursor they're not exactly shrinking but they're not growing as fast... we effectively fund unlimited tokens for everybody. Uh we we do we do try to control the models that uh people use but from the bottom not from top like we basically say hey please don't use anything less than us 4.6 (4o).

</details>

### AI 时代的 PR 审查与 CI/CD 瓶颈

**Mikhail Parakhin**: 现在的代码行数正在爆炸式增长，部分是因为 AI 比较啰嗦，部分是因为 AI 能写出比人类多得多的代码。因此，你必须在 **PR（拉取请求）**审查阶段设置一个非常强大的“瓶颈”，否则 Bug 的数量会冲破屋顶。

**Sean**: 没错。我注意到你的图表中没有任何外部审查工具。

**Mikhail Parakhin**: 我还没发现一个好的、能达到我预期水平的公开 PR 审查工具。要挡住 Bug 涌入生产环境的潮水，你需要使用最顶级的模型。你生成的代币不一定要多，但需要高质量的模型轮流进行深度思考，这需要时间。我其实不介意一个专业级模型花一两个小时来审查我的 PR，因为人类可能需要一周。

<details>
<summary>Original English</summary>

**Mikhail Parakhin**: ...the overall budget is just like lines of codes lines of codes are exploding for everybody right now... partially just because AI can write a lot more code you know doesn't get tired and so you have to have to have a very strong narrow waste during PR review otherwise just the number of bugs will go through the roof.

**Sean**: Totally. Uh, I noticed in your chart you didn't have any review tools.

**Mikhail Parakhin**: I haven't found a good PR review tool that that does what I think should be done... you want to run the largest models that means I know codex or or cloud code is not going to cut it. You need to have prolevel models. If you really want to uh stand the tide of bugs going into production... I actually don't mind a prolevel model taking an hour or two hours to review my PR because I have dealt with humans who take a week to review my PR, right?

</details>

**Mikhail Parakhin**: 真正的挑战在于，由于代码量剧增，测试失败的概率也随之上升。你必须不断剔除有问题的 PR 并重新测试，部署周期反而变长了。所以，如果在 PR 阶段让模型思考一个小时能避免后续的测试失败和回滚，那么从**系统总成本**来看是完全值得的。目前的 **CI/CD** 流程是为人设计的，在 Agent 化的世界里，这种旧模式必须演变成全新的形态。

<details>
<summary>Original English</summary>

**Mikhail Parakhin**: ...the real problem is since there's so much more code then uh probability of at least some tests failing going up... it's total time savings if you spend more time on a longer model like thinking for an hour because then then you you don't have to spend all that time during testing and rolling you know rolling back the deployment... clearly the old thing were designed for humans will need to be morphed into something new.

</details>

### 第三代数据处理系统：Tangle 与 Tangent

**Sean**: 我们谈谈你们正在开发的 **Tangle**。它是如何运作的？

**Mikhail Parakhin**: Tangle 是我所说的第三代数据处理系统。它不仅针对机器学习实验，也适用于任何需要大规模迭代和协作的数据处理任务。传统的机器学习工作流就像“数字考古”，六个月后你可能连自己之前的脚本为什么崩溃都不知道。Tangle 完全基于**内容哈希（Content Hashes）**。如果输入没变，即使版本号变了，也不会重复运行。如果不同团队的人在做同样的预处理，系统会自动检测并只运行一次，实现全局效率最大化。

<details>
<summary>Original English</summary>

**Sean**: How would you explain them in together?

**Mikhail Parakhin**: Tangle first and then tangent is a thing on top of tangle. And the tangle is the third generation I claim of uh systems of uh running any data processing but bit with a skew for ML experiments... Everything is based on content hashes. So even if the version changed, but if the output didn't change, nothing is being rerun. It's very efficient. If you multiple people start experiments the same sort of data prep-processing, it's not repeated multiple times. It's automatically done only once.

</details>

**Mikhail Parakhin**: 而 **Tangent** 是建立在 Tangle 之上的自动研究循环。它是一个 Agent，可以分析实验，自动修改代码并反复运行，直到最大化某个目标。我们在 Shopify 看到这种模式像野火一样蔓延。例如，通过纯粹的自动研究循环优化，我们将搜索吞吐量从 **800 QPS** 提升到了 **4200 QPS**，且质量完全没有下降。最棒的是它实现了**民主化**，现在我们使用率最高的竟然是一位产品经理（PM），因为他不需要精通底层算法，只需利用领域知识通过 Tangent 进行迭代。

<details>
<summary>Original English</summary>

**Mikhail Parakhin**: And tangent is basically an automatic auto research loop that can help and kind of do your work for you... our search recently we moved from it's hard to even quote from 800 QPS to 4200 QPS with the same quality just by pure optimizations and not a research loop that kept running and changing code... tangent in particular are extremely democratizing... PMs are like the highest user right now.

</details>

### SimGym：基于十年历史数据的客户模拟器

**Sean**: **SimGym** 似乎是你们最成功的发布之一。很多人不太信任模拟客户，认为 Agent 只会重复你给的提示词。

**Mikhail Parakhin**: 这正是重点。如果你没有历史数据，Agent 确实只能在真空中运作。但 Shopify 拥有**数十年的历史数据**，记录了人们如何修改网站以及这些修改如何影响销售。我们花了近一年的时间进行优化，使模拟器与真实“加购”事件的相关性达到 **0.7**。

<details>
<summary>Original English</summary>

**Sean**: ...Sim AI... there's a very small cottage industry of people trying to do like the simulate customer thing. I think a lot of people maybe don't super trust this yet...

**Mikhail Parakhin**: That's exactly actually the thing I wanted to cover because if you don't have the historical data, all you can do is prompt agents in a vacuum... Yes, except Shopify has decades of history of how people made changes and what they what it resulted in terms of sales... our internal goals of correlation of hitting internal goal was to hit 0.7 correlation with add to cart events.

</details>

**Mikhail Parakhin**: 你必须在模拟浏览器环境中运行这个系统，因为它需要捕获视觉信息——比如图片变大会增加销量还是减少销量？通常人们的直觉是图片大更好，但实际销量往往会下跌。没有这种**视觉反馈循环**，模拟就没有意义。现在我们可以直接告诉商户：“基于你的网站，我们预测这些修改能增加转化率。”这种能力是初创公司无法复制的，因为他们没有数十年的数据积累。

<details>
<summary>Original English</summary>

**Mikhail Parakhin**: ...you want to detect the effects like hey if I make my image just larger will I have more sales or fewer sales and like usually people's intuition here... is that I increase my images I'll have more because they look nicer... usually your cells tank... we run over it and we say, "Hey, here's what predicted values of of uh conversions are and here's how we think you should modify it to increase your conversions."

</details>

### Liquid AI：非变换器架构的实战突破

**Sean**: 听说你们已经在内部积极使用 **Liquid AI** 的模型了？

**Mikhail Parakhin**: 是的。Liquid Neural Networks 是 **SSM（状态空间模型）**的进阶版。它是非 Transformer 架构，具有亚二次方（Sub-quadratic）的复杂度，非常紧凑且高效。我们在 Shopify 发现，对于**低延迟**应用，Liquid 是表现最好的。例如，在搜索查询理解中，我们通过与 NVIDIA 和 Liquid AI 合作优化，在 **30 毫秒**内运行一个 3 亿参数的模型，完成全量查询理解和个性化处理。

<details>
<summary>Original English</summary>

**Sean**: I think the surprise to me was that you guys are actively using it already in internally inside of Shopify...

**Mikhail Parakhin**: ...liquid neural networks are you can think of them as a next step like uh sort of uh state space model square... It's sub quadratic in in length of your context. Uh it's very compact way to represent things... we run it at 30 milliseconds a a tiny model like 300 million parameters in but we run it in 30 milliseconds end to end for search.

</details>

**Mikhail Parakhin**: 在另一个极端，我们也用它进行大规模的**离线分类**。当面对数十亿商品时，延迟不重要，但吞吐量和成本至关重要。我们会将最强大的模型（如 GPT-5 水平）的知识**蒸馏**到 Liquid 模型中，用于分类标签提取和属性归一化。它是目前我发现的唯一能与 Transformer 架构真正竞争的替代方案。

<details>
<summary>Original English</summary>

**Mikhail Parakhin**: There's different end of the spectrum where this is maximum through uh bandwidth throughput for things like for example offline categorization... We would take a large model like we would take something huge... we would distill into liquid for a specific task... it's definitely for this scenario of smaller models and distilling into they're second to none.

</details>