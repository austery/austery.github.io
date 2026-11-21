---
author: AI Engineer
date: '2026-11-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=prGP0huECPo
speaker: AI Engineer
tags:
  - llm-benchmarking
  - agent-cost
  - prompt-caching
  - pareto-frontier
  - inference-optimization
title: Artificial Analysis：优化智能成本与 Agent 权衡
summary: Artificial Analysis 联合创始人 George Cameron 探讨了 AI 智能成本的演进与权衡。随着 Agent 任务走向复杂化，任务成本跨度达数个数量级。分析指出 Prompt 缓存命中率、输入 Token 数与任务轮数已成为决定 Agent 运行成本的关键驱动因素，并提出按需求区分有限与无限智能任务以优化模型选择。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - George Cameron
companies_orgs:
  - Artificial Analysis
  - Anthropic
  - OpenAI
  - Google
  - Nvidia
products_models:
  - Opus 5.5
  - GLM 5.3 Flash
  - Optima
media_books: []
status: evergreen
---
### 介绍 Artificial Analysis 与全栈基准评测

[music]

大家好，感谢各位的光临。我是 George，Artificial Analysis 的联合创始人之一。今天我将分享关于优化“智能成本”的主题。
<details>
<summary>Original English</summary>
[music]

>> Hey everyone. Thanks for coming. I'm George. I'm one of the co-founders of artificial analysis. Today I'll be talking through optimizing the cost of intelligence.
</details>

先简单介绍一下我们 Artificial Analysis 的背景，我们是一家独立的 AI 基准评测机构。我们对整个 AI 技术栈进行基准评测：从 Agent 层（包含 Coding Agent 基准及其他 Agent 评估）、语言模型智能水平、图像/视频/语音与音乐模型，一直覆盖到硬件和推理层。这样我们就能评估所有这些层级之间的权衡取舍。当你在做决策时，你不仅是在选择模型，同时也是在做推理层面的决策：我该如何访问该模型？我要为此支付多少费用？我获得的响应速度如何？缓存命中率是多少？我们坚信技术栈的各个层级都是相互关联的，我们在各个层面上都在做选择。这就是我们评测 AI 全栈的原因。
<details>
<summary>Original English</summary>
To give a quick background to who we are at artificial analysis, we're a independent AI benchmarking company. We benchmark across the AI stack. So the agent layer without coding agent benchmarks and other agent benchmarks, language models for their intelligence, image, video, speech, and music models, as well as the hardware and inference layers. So that we can benchmark the tradeoffs between all these layers. When you're making decisions, you're not just choosing a model, you're also choosing you're making an inferences decision. How do I access the model? How much am I paying for it? What's the speed that I'm that I'm getting? What's the cash hit rate? We believe strongly that all of the kind of layers of the stack are interrelated. We're all making decisions across them. And so that's why we benchmark the full stack of AI.
</details>

不少业内领先的公司都会引用 Artificial Analysis 和我们的测试结果。但在这里我们最自豪的是，当我们看来自 OpenAI、Anthropic、Google 和 Nvidia 的引用时，他们不仅仅是引用我们纯粹的智能基准分数。这不只是一张简单的柱状图。我们固然非常喜欢我们的智能指数，但我们最热衷的是去探讨在这些技术之间所做的权衡权衡。
<details>
<summary>Original English</summary>
Kind of leading companies kind of reference artificial analysis and our results. I think but what we're most proud of here, when we take a look at these references from OpenAI, from Anthropic, from Google, and and Nvidia, they're not just referencing our raw intelligence benchmark numbers. It's not just a bar chart. We We're big fans of our intelligence index, but we're kind of most interested in talking through the tradeoffs that we're making between these technologies.
</details>

这也是为什么我们感到自豪：这些图表全都是展示权衡关系的二维象限图，呈现了开发者需要做出的抉择。有时这些选择不是发生在让系统跑通的阶段，而是在真正推向生产环境部署的时候。
<details>
<summary>Original English</summary>
And so that's why we're proud that all of these are kind of two by two charts showing tradeoffs between uh, choices developers need to make. Um, sometimes not when they're when they're getting things working, uh, but really when they're rolling it out in production.
</details>

我们也被传统媒体和新媒体相当广泛地引用。我们总部位于旧金山，目前拥有一支 50 人的团队，正在招兵买马。我们在招聘前线部署工程师（FDE）、技术研发成员（MTS）中的 AI 研究人员，以及机器学习工程师。如果有兴趣加入 AI 基准评测领域，欢迎会后找我交流或随时联系。
<details>
<summary>Original English</summary>
We're also quite widely referenced, um, by kind of traditional and, uh, and new media. We are based in San Francisco. We've got a team of 50, um, and we are hiring. Um, so we're hiring across uh, four deployed engineers, um, AI research staff as part of our member of technical staff team, and ML engineers. Um, and so, you know, catch me after or please reach out if you if you might be interested, um, in joining the the world of AI benchmarking.
</details>

### 智能指数与 AI 发展现状

我认为在理解成本之前，我们需要先了解 AI 的整体格局以及用于理解和优化的各项指标。首先从了解 AI 格局开始，我先介绍一下我们的“智能指数”（Intelligence Index）。在我们看来，这是了解语言模型通用智能水平的最佳单项数值指标。它综合了覆盖不同 AI 能力维度的 10 项独立评测。
<details>
<summary>Original English</summary>
I think before we understand cost, we need to understand the kind of landscape of AI and the metrics to to understand and to optimize. And so, starting with understanding the AI landscape, I'll first introduce our intelligence index. It's we view it as the best single number to understand the general general intelligence, uh, of language models. It's a synthesis metric of 10 different evaluations covering different capability areas of AI.
</details>

其中涵盖了**知识性工作**、**科学推理**、**编程与终端使用**，以及包括幻觉认知在内的其他关键能力和考量因素，这些都是人们在语言模型之间进行选型时所关注的维度。我们所针对的是当前正在构建的应用场景以及下一代用例。这并不一定是为了衡量或评估迈向 AGI 的进展，而是切实帮助开发者为他们正在用 AI 构建的下一批应用场景做出决策。
<details>
<summary>Original English</summary>
That includes knowledge work. It includes scientific reasoning. Uh, it includes coding and terminal use, uh, and it includes other capabilities including kind of knowledge, uh, hallucination and other relevant capabilities and considerations, um, regarding intelligence that people use when when choosing between language models. What we say is for the current use cases being built and the next use cases. It's not necessarily to measure and

>> [clears throat]

>> and benchmark progress towards AGI. It's really to help developers make decisions for the next use cases that they're building uh, using AI.
</details>

目前该指数榜首自然是来自 Anthropic 的 Opus 5.5。我想对在座的大多数人来说，这并不算什么意外。但今天同样需要探讨的是，如大家所见，这里还有非常多的其他模型。在 Artificial Analysis 官网上，我们收录了超过 500 个模型。
<details>
<summary>Original English</summary>
And so of course Opus 5.5 from Anthropic is currently leading the index. I think to many in this room that won't be a big surprise. But also to discuss today is that there's as you can see here many other models. We have over 500 models on the artificial analysis website.
</details>

当前图表上展示了许多模型。而我们今天将要探讨的核心要点之一是：除了世界上最聪明的模型之外，开发者同样有充分的理由去选用其他模型。
<details>
<summary>Original English</summary>
Um and many kind of current and and and presented on this chart. And I think what we'll be talking through today is a bit that that kind of takeaway that there's also reason to use models other than the most intelligent model in the world.
</details>

我们也会发布单项评测结果。比如我们推出了 AA Analyst Agent，这是一个专注于财务与会计领域的基准测试。考虑到今天是在纽约，我想分享一下这个。我们向那些希望深入到更具体维度来考虑模型及其他技术选型的人提供这些单项数据，因为模型在实际表现中并不总是完全符合通用智能指数的整体画像。
<details>
<summary>Original English</summary>
We also publish individual eval results. So we released AA analyst agent which is a finance and accounting focused focused benchmark. Thought I'd share that this being New York. And we share the individual results for those wanting to go to the next layer of specificity when thinking about their model selection and and selection of other technologies because it's not always the case that models exactly follow the generalist view of the intelligence index.
</details>

例如在这里我们可以看到，Gemini 系列模型实际上非常擅长处理复杂的电子表格。当然，Anthropic 系列模型表现也非常优异。
<details>
<summary>Original English</summary>
And so here we kind of highlight that the Gemini series of models is actually very good at navigating complex complex spreadsheets. Of course Anthropic series of models is is of course as well.
</details>

稍微退一步来看，纵观我们的智能指数以及来自前 12 家左右主流实验室的模型随时间演进的轨迹。首先，最直观的感受是非常密集繁杂。图上有大量的散点，我想在座很多人在过去几年里都会对此深有共鸣——模型发布的数量极多，而且发布节奏越来越快。某种程度上说，在我们看来技术进步的步伐本身也在加速，这张图清楚地反映了这一点。
<details>
<summary>Original English</summary>
To step back a bit looking at our intelligence index and the leading model over time from the top 12 or so labs here. Um firstly I think big takeaway it's kind of hectic. There's many dots and I think probably that resonates for a lot of us in the room who have kind of felt this over the past few years where there've been huge number of model releases and the number of model releases in is increasing. And in a sense kind of the the pace of progress in our view is also accelerating and I think that is shown in this chart here.
</details>

因此这里的核心结论是：AI 正在飞速向前演进，技术进展非常迅猛。大家试图紧跟步伐时可能会感到疲于奔命，但投入时间和精力去跟进是完全值得的，因为如果你想紧跟 AI 前沿并掌握其最新能力，跟上新模型发布的节奏是至关重要的一部分。
<details>
<summary>Original English</summary>
And so I think the takeaway here is that AA is moving quickly, progress is moving quickly, and so kind of we might feel exhausted trying to keep up with it, but um it makes sense to to it to invest that time and energy because if you want to stay on on top of AI and what AI's capable of, um then staying on top of releases um is a a big part of that.
</details>

下一个视角我们就不做过深展开了，这本身就能单独讲一场：开源权重模型目前持续与顶尖专有闭源模型保持在 3 到 9 个月的差距之内。因此开源权重模型依然是一个可行的选择。这是今天的要点之一，它直接关系到诸多成本考量，开源权重模型有时具备极具优势的成本特征。
<details>
<summary>Original English</summary>
The next view won't deep dive, this could be a whole talk, but open weights models continue to keep within 3 to 9 months of the leading proprietary models. And so open weights models remain an option. Uh and so I think that's that's the takeaway for the talk today and and it flows through to a lot of um kind of cost implications uh which sometimes open weight models can have favorable uh characteristics.
</details>

### 任务成本的演进与数量级差异

接下来让我们深入探讨成本以及该如何看待成本。我想站在 2026 年中后期的视角来探讨成本，因为如果这场演讲放在哪怕 6 到 9 个月前，内容都将截然不同。
<details>
<summary>Original English</summary>
Next, let's dive into cost and how to think about cost. And I want to discuss think talking about cost from the perspective of being kind of mid-late 2026 because I think if we were doing the if I was doing this talk even six or nine months ago, I think it would be a different talk.
</details>

AI 已经走过了漫长的发展历程。稍后我们会剖析成本的各项驱动因素，但首先说明我们为何对成本如此敏感：根本原因在于，如今这些模型在完成单项任务时往往要花费数美元。这在 12 个月前并不是常态。现在大家在 AI 上的支出比以往任何时候都多，在单项任务上能够花掉的成本也突破了以往的上限。在此处我们展示了 Opus 和 Fable，它们完成一项任务的花费都超过了 5 美元。
<details>
<summary>Original English</summary>
AI has moved a long way. And so we'll go into the drivers, but to kind of start with a little bit kind of the answer of why we're so conscious of cost is because these models are costing many dollars um to complete individual tasks. That wasn't the case uh 12 months ago. Um people were spending more than ever on AI and can spend more than ever on a single task um on AI. And so here we present Opus and Fable costing above $5 to complete a task.
</details>

但另一方面，也有一些模型完成单项任务的成本在 5 美分甚至更低。也就是说，我们看到不同模型之间的成本存在着数个数量级的差距。这意味着成本考量与模型选型决策至关重要。
<details>
<summary>Original English</summary>
But on the other side, um there's also models that cost 5 cents and less to complete a task. And so what we're seeing is there's orders of magnitude, multiple orders of magnitude uh difference in cost uh between the between the models. And that means that the cost decision and the model decision uh matters.
</details>

你可能会说：“左边的那些模型智能水平没那么高。”这完全属实。但它们依然非常优秀。比如这里的 GBD6 Luna，单次任务只需 7 美分，而且它远比当初的 GBD4 要强得多，更是大幅超越了真正开启这波大语言模型浪潮的 GBD3.5 Turbo。因此可以说，顶尖闭源模型与那些便宜得多却依然非常优秀、极具能力的模型之间，存在着整整两个数量级的成本差距。
<details>
<summary>Original English</summary>
And what I would say is that yes, you might say oh the uh the models on the left here are less intelligent and that's totally true. But they're still very good. Uh uh Luna here, GBD5 um sorry, GBD6 Luna is 7 cents uh per task um and it's much better than than GBD4 was um originally, right? Which kind of and and and way better than GBD3.5 Turbo, which really kind of like opened up um th- this wave of kind of language models. And so, I would say that there's two orders of magnitude difference between the leading proprietary models and much cheaper, but still very good, very capable models.
</details>

审视成本的另一个维度是**时间维度**。我们所做的是将模型按智能水平进行分档，观察该智能梯队首次被攻克的时间，随后追踪使用能达到该水平的最便宜模型，其调用成本随时间是如何变化的。我们在这里发现：在短短 1 年之内，获取同等水平智能（例如智能指数达到 30 或 50 分位）的成本，基本上会下降一个数量级，大约降低 10 倍。以图中的淡紫色曲线为例，当最初达到 30 分时，单次成本略高于 1 美元；一年后降至大约 10 美分；而现在已远低于 10 美分，进入了 1 美分至 10 美分的区间。
<details>
<summary>Original English</summary>
A next way to kind of consider looking at cost is uh from a time perspective. And what we've done is we've bucketed models by their intelligence and looked at when that intelligence tier was first reached and then how did the kind of cost of trying to access the intelligence with the cheapest model develop over time. And what we see here is that within 1 year, accessing that level of intelligence, a 30 on the intelligence index or a 50 on the intelligence index, essentially reduces by an order of magnitude, kind of 10x, within around a year. So, picking the the light purple here, um once we reached a 30, cost a bit over a dollar. A year later, it fell to around 10 cents. And then now we're well below uh the 10 cent. We're in the kind of um 1 cent to 10 cents territory.
</details>

所以这里还有一个时间维度的考量：我们一方面需要基于当下做出抉择，但另一方面也必须意识到，就我们能够获取的智能水平而言，情况会变化得极快——当下某项庞大任务可能要花费 100 万美元，大概一年后我们就能用 10 万美元获得同等智能水平，而到了两年后可能只需约 1 万美元。
<details>
<summary>Original English</summary>
And so, I think it's there's also a time dimension here whereby we should be um you know, making choices for now, but also conscious that that is going to change very quickly in terms of the intelligence that we can achieve and and that maybe $1 million um spent for a big gigantic can you know, is likely we can access that level of intelligence at 100k and then in 2 years potentially around 10k.
</details>

### Agent 任务成本拆解与缓存的重要性

现在我们来看单次任务成本的构成剖析。这比 12 个月前、更不用说 24 个月前要复杂得多。12 个月前我们在讨论推理模型（Reasoning Models），当时我们在说需要为推理 Token 付费，而各大实验室往往只公布输出 Token 的单价，因此整个社区必须专门做分析来计算推理 Token，才能真正算清成本。
<details>
<summary>Original English</summary>
Now, here we have a build up of the cost per task. This is a lot more complex than where we were 12 months and definitely 24 months ago. I think 12 months ago we're talking about reasoning models. We're saying that we have to pay for reasoning tokens and um you know, the the labs were just talking about the output token price um and so we needed to do an analysis um as a as a community to really understand the cost because we have to count reasoning tokens.
</details>

而在 Agent 时代，情况变得复杂得多。为了拆解单任务成本构成，我们这里采用了 AA Briefcase Agent 基准评测。该基准让 Agent 置身于包含数千个文件的环境中完成知识工作任务，例如生成报告、制作演示文稿或制作营销视频。从数据中可以看到，Opus 完成单项任务的平均花费为 21 美元。它的执行效果非常出色，这一点毫无争议。
<details>
<summary>Original English</summary>
Now with agents it's become way more complex. Way more complex. So, to understand the build up of a cost per task, here we use our AA briefcase agent technology workbench mark. It looks like agents in an environment of thousands of files completing knowledge work tasks like creating reports, creating PowerPoints, creating marketing videos. And what we can see here is on average Opus is costing $21 to complete a task. And it does a great job. No arguments there.
</details>

但如果将焦点放在成本上，我们可以看到：最终答案 Token 的花费大约只有 16 美分；推理 Token——抱歉，答案 Token 大概是 2 美分，推理 Token 会稍微多一些。但当我们逐步拆解单次语言模型调用时（也就是图中的第一列，稍后我会讲第二列），单次调用的成本仅为 13 美分。然而面对 Agent 的轨迹（Trajectories），我们必须考虑步数：完成整项任务总共耗费了 165 个步骤。这就是我们在面对 Agent 时必须考虑的一个全新维度。
<details>
<summary>Original English</summary>
Focusing on cost though, what we can see here is that uh answer tokens, you know, cost around 16 cents. Reasoning tokens, um oh sorry, uh it's like 2 cents.

>> [laughter]

>> Um and then we have then we have reasoning tokens a bit more, but then really where the you know, building up to the single language model call, the first kind of column that hits the ground and I'll talk about the second there. Um so each call is 13 cents, right? But with agentic trajectories we're having to think about the number of steps, of course. And so it took 165 steps to complete the task. And so that's where that's a new dimension that we need to think about when it comes to agents.
</details>

进一步拆解单次模型调用，它由答案 Token、推理 Token 和输入 Token 构成。而在输入 Token 中，你必须考虑有多少输入 Token 命中了缓存，从而享受输入 Token 单价大约 10 倍（10x）的折扣。从成本构成分析来看，决定单次模型调用成本的最大驱动因素是**输入 Token 的数量**，其次是这些输入 Token 中**命中缓存的比例**。而在此之外，整个任务最大的成本驱动因素其实是**每项任务的交互轮数（Turns per task）**。
<details>
<summary>Original English</summary>
And then thinking to kind of what goes into a single language model call, you can see there's answer tokens, reasoning tokens, input tokens and then with input tokens you need to think about how many of those input tokens uh kind of cash hits um and so get that roughly 10x uh discount on an input token price. And what we can see with the build up is the biggest driver of the kind of input into what a single language model calls is the number of input tokens and then secondly the amount of or proportion of those input tokens that are cache hits. And then the third biggest driver after that is of course or it's actually the biggest but it is the number of turns per task.
</details>

一年前我们还在谈论输出 Token 的数量、推理量以及推理的冗长程度；而在今天，我们真正需要谈论的核心指标是**输入 Token 数**、**缓存命中率**以及**任务轮数**。我想特别强调一下缓存命中次数的重要性：如果没有任何缓存命中，缓存命中率为零、缓存失效（比如自己搭建了 VLM 却没有启用 Prompt Caching），那么完成单项任务的成本将从 21 美元直接飙升到超过 200 美元。这充分说明了在谈论 Agent 和推理提供商时，缓存究竟有多重要，你必须对此给予极高关注。我们最近也开始在官网上发布有关缓存命中率的基准评测。
<details>
<summary>Original English</summary>
And so we were talking a year ago around the number of output tokens, how much reasoning, the reasoning verbosity. I think today we really need to be talking about input tokens, uh cache hit percentage, um and then the number of turns per task is the key metrics that we should be thinking about when thinking about the cost um of running of running agents. And I think just to really emphasize the number of cache hits, if we don't have that then and and we don't have any cache hits, right? Cache hit percentage is zero, caching isn't working, maybe we've got our own setup with VLMs, we haven't enabled prompt caching, um then instead of $21 per task, this costs over $200. So that's just to really emphasize how much caching matters here when we're talking about agents and also when talking about inference providers, how much you really need to to care about that. We started recently publishing benchmarks around cache hit percentage on our website.
</details>

### 推理深度与开源模型对比

下一个考量因素是不同的**推理深度（Reasoning Efforts）**。这里展示了 Opus 5.5 在不同推理努力程度下的柱状图及其对上述指标的影响。这里的核心结论是：当我们谈论推理努力程度时，它指的不单是单次 Agent 调用产生的推理 Token 数量，它还会直接影响交互轮数。而且这些推理 Token 会随着消息历史机制在整个 Agent 执行轨迹中持续传递，转化为多得多的输入 Token。因此即使使用完全相同的模型，认真权衡推理努力程度也极其关键：在低设定下，Opus 5.5 完成单项任务的成本大约是 1 美元，而在最高设定下则高达 21 美元。
<details>
<summary>Original English</summary>
And next consideration is um you know different reasoning efforts. And so here we have um kind of column um column charts showing the different reasoning efforts um for Opus 5.5 and the implications on these metrics. And so I think pretty much the key takeaway here is when we're talking about reasoning efforts, we're not just talking about um uh kind of reasoning the number of reasoning tokens um for an agent single agentic call, it does impact the number of turns. Um And of course then you have reasoning tokens and then those reasoning tokens feed throughout the agentic trajectory into kind of much more input tokens um because of the way that like message histories work uh when it comes to comes to using agents. And so even with it when using the same model, very important to think about the reasoning effort because here we can see that at low Opus 5 can cost 5.5 can cost a dollar per task and at max it can cost $21.

>> [clears throat]
</details>

这里我们做了一个从 Opus 5.5 到 GLM 5.3 Flash 的对比拆解。后者是一款开源权重模型，价格便宜得多，但依然极其出色且能力强大。查看这个细分数据主要是为了说明两点：第一，顶尖模型与低成本模型之间存在巨大差异；第二，前面谈到的所有成本驱动因素都在各模型间的成本差异中发挥了作用；第三，在执行长周期的复杂 Agent 任务时，输入 Token 价格和缓存命中率是决定成本的最大驱动因素。
<details>
<summary>Original English</summary>
>> And here's kind of um a breakdown going from Opus 5.5 to GLM 5.3 Flash, a much cheaper but still extremely good, very capable model um that's that's open weights. And I think when we look at this when we look at this breakdown, this is really just to show that one, there's big differences between as we saw between the leading models and the and much cheaper models and two is that all of the different drivers that I was talking about play a role in driving cost differences um between models. And then thirdly, of course, that input token prices and your cache hit percentage um are the biggest driver um of cost when doing long uh horizon agent tasks.
</details>

### 帕累托最优与任务分分类决策框架

我们已经讨论了成本，而大家都知道 GLM 5.3 Flash 比 Opus 5.5 便宜，知道 Luna 比 Astra 便宜，这并不稀奇。作为开发者，我们面临的真正挑战在于如何做出**权衡决策**。这是最困难的部分：我们该如何理解自身任务的权衡曲线？
<details>
<summary>Original English</summary>
So we've talked about the cost and I think there's no points for knowing that GLM 5.3 Flash is cheaper than Opus 5.5. I think a lot of people in this room know that Lunar is cheaper than than Astra. Great. So the challenge for us as builders is making the trade-off decision. That's the hard thing. How do we understand our trade-off curves for our tasks?
</details>

我们认为一个有用的切入点是基于“智能水平与任务成本”的通用帕累托前沿（Pareto）。首先明确：结合所需模型来看，我的任务在这条智能帕累托曲线上处于什么位置？如果预算更充裕或者追求最顶尖的智能，就应该看向帕累托前沿的右侧；如果想要更便宜，就应该看向帕累托前沿的左侧——帕累托前沿即图中所描绘的这条曲线。当需要选择更便宜的模型时，可以查看帕累托前沿并思考：“我的预算有限，那么在这个价位上能提供最佳智能的模型是哪一款？”或者换一个角度思考：“我需要这种水平的智能，获取它的最廉价途径是什么？”
<details>
<summary>Original English</summary>
And I think a starting point that we think is useful to use is the generalist um view of intelligence versus cost per task and starting with the Pareto. So starting with okay, my task um where does it sit across this uh this intelligence Pareto in terms of the model that's needed. If I'm able to spend more or wanting leading intelligence, I want to look to the right of the Pareto. If I want cheaper, then I should let look to the left of the Pareto. The Pareto being this this line depicted in this in this chart here. And when choosing and wanting a cheaper model, let's take a look at the at the Pareto and seeing, "Okay, I'm willing to my budget is less and so what's the model that at that point offers the best intelligence for that that dollar?" Or from the other perspective of I want this level of intelligence, what's the cheapest way I can get it?
</details>

该如何引导这一决策并向自己提出正确的问题？我们认为一种有效的方法是将任务划分为两大类：

第一类是**无限智能任务（Unlimited Intelligence Tasks）**，在这类任务中，更强的智能总是能带来更好的结果。例如：“分析我业务中的成本驱动因素，以及我该如何优化它们？”在这种场景下，模型越聪明，给出的结果通常就越好。
<details>
<summary>Original English</summary>
How to think about navigating that decision and asking yourself those questions? A way that we think's helpful is to bucket tasks into two categories. So first is unlimited intelligence tasks, whereby more intelligence can always deliver a better result. An example being, "Analyze drivers of the costs in my business and how do I optimize them?" Kind of smarter will always deliver a better result there.
</details>

第二类是**有限智能任务（Limited Intelligence Tasks）**，在这种情况下，更高的智能不会带来更好的结果。例如这个问题：“上个月我在各类订阅上花了多少钱？”一个像 Luna 这样更廉价的模型只要配置了合适的 MCP，就能直接告诉你花掉了 80 美元；换用 Astra 同样会告诉你 80 美元，更高的智能无法带来任何额外收益。因此在这种情况下，我们应当聚焦于完成任务所需的智能上限究竟是多少，以及达到该水平的最经济途径是什么。这就是有限智能任务。而在无限智能任务中，核心问题则是：“我的预算是多少？我愿意为提升智能支付多少成本？”
<details>
<summary>Original English</summary>
Next, the second bucket is limited intelligence tasks and here is when more intelligence won't give you a better result. So the question, "How much did I spend on subscriptions last month?" I think a cheaper like Luna will answer that question as long as it's set up with the right MCPs. Currently, it'll tell me $80. Using Astra will also tell me $80. $80. I'm not getting any benefit from more intelligence. Um and so then I should focus on what's the cheapest way what's the level of intelligence needed, the ceiling, and what's the cheapest way that I can get that level of intelligence. So that's limited intelligence. Unlimited intelligence, the question is, "What's my budget? How much am I willing to pay for increased intelligence?"
</details>

关于我们建议如何使用 AI 并做好这些权衡决策：我们建议首先理解技术格局与评估指标；接着根据优先级对比并筛选候选模型；随后对于较小型的原型工作流，在自己的上下文和 Agent 中基于候选名单进行测试。
<details>
<summary>Original English</summary>
In terms of how we suggest using artificial intelligence, we suggest to kind of and how to navigate these decisions. I think it's understand the landscape, the metrics, then compare models based on priorities, shortlist models, and then for kind of smaller prototypy workloads, use the shortlist, test on your own, uh you know, in your own context and your own agents.
</details>

对于更深入的用户，尤其是推向生产环境部署时，由于当前涉及的成本量级巨大，我们建议建立专属的基准评测，将候选模型精简到大约五款，从而对决策进行深度优化。我们近期推出了一款名为 **Optima** 的产品，它允许用户访问 Artificial Analysis 并上传自己的业务上下文。结合我们沉淀在 Optima Agent 中的大量专业认知，我们可以协同生成专属于你的评测基准，为你呈现专属任务视角下的智能与成本权衡曲线，帮助你做出最优权衡抉择。
<details>
<summary>Original English</summary>
For more advice users, particularly when rolling out in production, we recommend creating your own benchmark to take that shortlist to five models and try and make um the decision optimize for the decision um because of the kind of magnitudes of cost that we're dealing with now. Um we recently released a product called Optima um that allows users to come to Artificial Analysis, upload their context, and we will um together with you using a lot of our um knowledge that we've distilled into this kind of Optima agent, we generate you a benchmark um and give you your own trade-off curves between your view of intelligence for your task um and the cost to help you help you make these trade-offs.
</details>

以上就是关于智能成本的分享。非常感谢大家的聆听。欢迎访问我们的官网 artificialanalysis.ai。正如开场所述，我们正在广泛招募各类岗位。非常感谢大家！

>> [applause]
<details>
<summary>Original English</summary>
So, that's the cost of intelligence. Um thanks very much for for listening. Come check us out our website at artificialanalysis.ai, and um as mentioned at the start, we're uh we're hiring quite broadly across roles. So, thank you very much.

>> [applause]
</details>