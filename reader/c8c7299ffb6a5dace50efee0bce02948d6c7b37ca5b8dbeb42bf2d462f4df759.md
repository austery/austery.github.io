---
author: AI Engineer
date: '2026-10-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=opHmX7qClzE
speaker: AI Engineer
tags:
  - financial-services
  - capability-overhang
  - model-context-protocol
  - threshold-phenomenon
  - persistent-agent
title: OpenAI 如何打造面向金融从业者的 ChatGPT：从能力悬殊到专业工作流
summary: OpenAI 金融服务负责人 Joseph Kim 介绍了专为投行与股票研究打造的 ChatGPT for financial services。他阐述了“能力悬殊”概念、自建金融数据索引与微调经验、模型性能跨越“可用性阈值”的规律，并预测到2027年AI将在预测财报与投资判断上超越人类专家。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Morgan Stanley
  - Evercore
products_models:
  - ChatGPT
  - Codex
  - GPT-4
  - GPT-5 Soul
  - GPT-6 Astra
media_books: []
status: evergreen
---
### ChatGPT for Financial Services 介绍与金融工作流的变革

>> 大家好。我是 Joseph Kim，负责刚在一个月前推出的新产品——ChatGPT for financial services（金融服务版 ChatGPT）。

你们中的许多人已经体验过像 Codex 这样的工具如何改变了大家在软件工程中的构建方式。AI 已经成为大家日常工作中更大的一部分。模型也在以令人难以置信的速度持续提升。

但许多在金融等行业工作的人，尚未在日常工作中经历同样的变革。我预计在接下来的几个月里，这种情况将开始迅速改变。在场的各位构建者在加速这一进程中扮演着重要角色——那就是将这些模型中的智能转化为人们可以在日常工作中使用的产品。

今天，我将分享一些我们在构建 ChatGPT for financial services 过程中的经验，以及我们对未来的思考。我将首先展示我们构建的内容，包括一个简短的演示。然后我会解释我们为什么构建它，以及为什么我们认为现在是构建它的最佳时机。接着，我将向大家介绍我们是如何构建它的，并分享一些我希望你们能应用到自己产品中的技术经验。最后，我们将展望模型的发展趋势、产品走向，以及这在未来一年对金融工作可能意味着什么。

<details>
<summary>Original English</summary>

[music]

>> Hi everyone. I'm Joseph Kim and I lead ChatGPT for financial services, a new product we launched just 1 month ago.

Many of you have already experienced how tools like Codex have changed the way you build in software engineering. AI has become a much bigger part of the work you do every day. Model is continuing to improve at an incredible pace.

But many people working in industries like finance haven't yet experienced that same change in their day-to-day work. I expect that to start changing rapidly over the next few months. And builders like all of you in this room have a big role in making that happen quickly. Taking the intelligence in these models and turning that into products that people can use in their daily work.

Today, I will share a little bit about what we learned building ChatGPT for financial services and how we're thinking about what comes next. I'll start by showing you what we've built including a quick demo. Then I'll explain why we built it and why we think now is the right time to build. From there, I'll walk you through how we built it with some technical lessons that I hope you can apply to your own products. Finally, we'll take a look at where models are headed and products are going and what that could mean for financial work over the next year.

</details>

### 产品三大核心：数据、金融专用界面与机构规范

让我们从我们构建了什么开始。ChatGPT for financial services 是专门为金融专业人士（从投资银行和股票研究开始）量身打造的工作版 ChatGPT。它的设计旨在帮助大型金融机构的员工从日常工作中获得更多价值，就像 Codex 在软件开发中加速大家的工作一样。

在我们与设计合作伙伴摩根士丹利（Morgan Stanley）和 Evercore 一起构建该产品时，我们专注于三个核心领域。

第一，金融数据。金融数据是金融工作的基石，你能做的工作受限于你数据源的质量。我们希望人们能够直接在 ChatGPT 内部访问他们需要的数据。

第二，专为金融打造的界面。我们希望该产品让金融专业人士感到熟悉，提供检查原始材料、探索财务图表以及控制分析背后数据来源的方法。

第三，符合您公司的格式规范。金融工作是在组织的语境下进行的，人们制作的模型和演示文稿需要遵循其公司的格式和标准。我们通过使用针对特定公司的模板，让创建这些成果变得更加容易。

但俗话说，百闻不如一见，所以我先不多说了，直接给大家展示产品。

<details>
<summary>Original English</summary>

Let's start with what we built. ChatGPT for financial services is a tailored version of ChatGPT work built specifically for financial professionals starting with investment banking and equity research. It's designed to help people at the large financial institutions get more out of their day-to-day work similar to how Codex speeds you up in software development.

As we built the product with our design partners Morgan Stanley and Evercore, we focused on three core areas.

First, financial data. Financial data is a foundation of financial work, and the work you can do is limited by the quality of your sources. We wanted people to have access to the data they need directly within Chat GPT.

Second, an interface built for finance. We wanted the product to feel familiar to financial professionals with ways to inspect source material, explore financial charts, and control the sources behind an analysis.

Third, your firm's format. Financial work happens within the context of an organization, and the models and presentations people produce need to follow their firm's format and standards. We made it easier to create those artifacts using firm-specific templates.

But they say a picture's worth a thousand words, so I'll stop talking for a bit and show you the product.

>> [music]

[music]

[music]

</details>

### 跨越“能力悬殊”与产品体验的力量

>> 太棒了。现在，我想花点时间谈谈我们为什么构建它。

我们构建 ChatGPT for financial services 是为了帮助弥合我们所说的“能力悬殊”（capability overhang）。正如你们在这里看到的，过去几年模型能力以惊人的速度提升。在短短几年内，我们已经从模型能够解决高中数学问题，发展到系统能够解决千禧年大奖难题（Millennium Prize Problems）的程度。

然而，人们在日常工作中从这些模型中获得的价值并没有跟上这一步伐。你在新闻中读到那些突破，但对许多金融专业人士来说，他们的工作方式并没有以同样快的速度改变。我们将这种差距称为能力悬殊——即模型所具备的能力与人们实际能从中获得的价值之间的距离。

弥合这一差距不仅需要构建能力强大的模型。人们需要合适的数据和工具，并且需要一种契合其工作方式的体验。这就是像你们这样的构建者大显身手的地方。

我想向大家展示一个例子，说明一个恰到好处的产品体验能带来多么巨大的差异。这是一张展示 OpenAI 内部不同职能部门 Codex 使用量增长的图表。如你所见，工程师们很早就开始使用 Codex，并且这一比例稳步增长。

但是，看看财务、法务和招聘部门。在 2026 年初，他们的 AI 产出几乎没有一项是在 Codex 中生成的。到了 6 月，这一比例达到了约 90%。如果你仔细看，会注意到在今年 2 月到 3 月左右发生了一个巨大的拐点。我回去查看了那段时间发生了什么，本以为我们一定是发布了新模型，但我发现其实是我们推出了 Codex 桌面端应用。

我的感悟是，正是产品让工程之外的人更容易将这些能力投入实际工作。这就是我们在金融领域所追寻的机遇：构建一种体验，帮助金融专业人士从他们已经可以获取的智能中榨取更多的价值。

<details>
<summary>Original English</summary>

>> Wonderful. Now, I'd like to take some time to talk about why we built it.

We built ChatGPT for financial services to help close what we call the capability overhang. As you can see here, model capabilities have improved at a tremendous rate over the last few years. In just a few years, we've gone from models solving high school math problems to systems capable of solving millennial prize math problems.

But, the value people get from these models in their day-to-day work hasn't kept pace. You read about the breakthroughs in the news, yet for many financial professionals, the way they work hasn't changed nearly as quickly. We call that gap the capability overhang, the distance between what the model is capable of, and the value people can actually get from it.

Closing that gap takes more than building a capable model. People need the right data and tools, and and they need an experience that fits the way they work. That's where builders like you come in.

I want to show you an example of how much of a difference a right product experience can make. This is a chart that shows how Codex usage grew within OpenAI across different job functions. As you can see, engineers started using Codex early, and that share grew steadily.

But, look at finance, legal, and recruiting. At the beginning of 2026, almost none of their AI output was generated in Codex. By June, that share was around 90%. If you look carefully, you'll notice a huge inflection point that happened around February-March of this year. I went back to see what happened around this time, assuming that we must have released a new model, but instead I found that we had released the Codex desktop app in February.

My takeaway is that the product made it easier for people outside of engineering to put these capabilities to work. That's the opportunity we're pursuing in finance. Building an experience that helps financial professionals get much more value from the intelligence already available to them.

</details>

### 技术实现：自建数据索引、后训练与插件生态

现在，让我来谈谈我们是如何构建它的。

让我们从数据开始。在金融领域，你能做的工作受限于你所能访问信息的质量。因此，我们希望该产品自带专业人士所依赖的数据源，从财务报表、财报电话会议纪要到市场数据和未上市公司数据。

我们研究了现有的金融数据 MCP（Model Context Protocol）连接器，发现许多连接器在延迟、报错或搜索质量方面存在问题。因此，我们直接获取了大量此类数据的授权许可，并使用与我们的 Web 索引相同的基础设施构建了自己的托管和搜索索引。

我们仍然使用 MCP 协议来赋予模型访问数据的权限，但自行托管和建立索引使我们能够更好地控制体验的质量和可靠性。这也让我们拥有了后训练（post-training）模型以配合这些数据集工作的灵活性。

我喜欢用的一个类比是：MCP 和 Skills（技能）就像是给初级分析师一本操作手册；而经过后训练的模型，就像拥有了一位已经与这些数据打交道超过二十年的资深分析师，对其所有微妙的特性都了如指掌。MCP 和 Skills 赋予模型访问权限与操作指令，后训练则能帮助模型对数据本身建立更深入的熟悉度。

一旦我们搭建好了这个数据基础，下一步就是让将这些信息转化为专业级成果变得简单。对金融专业人士来说，这种工作通常表现为一个 Excel 模型、一个 PowerPoint 演示文稿，或者是一份需要审阅并与他人共享的书面分析。

因此，我们专注于帮助模型以符合公司现有工作流程的方式生成这些输出。我们构建了一个模板系统，让用户在生成电子表格和演示文稿时能够使用公司批准的模板。其目标是减少将产出准备好提供给团队或客户所需的工作量。

我们还添加了诸如交互式财务图表之类的功能，使用户在进行分析时可以直接在 ChatGPT 中探索股票价格和财务指标。我们还构建了引用查看器，允许人们检查答案背后的原始段落和表格。在金融领域，你需要能够核对某个数字的来源并理解其背后的上下文。我们希望这种审阅能成为体验中自然而然的一部分。这些产品细节有助于将模型的能力转化为人们可以直接使用的成果。

我认为对在场各位最相关的部分是我们如何构建它的。大家刚才看到的许多功能，都是使用同样面向各位开发者开放的 ChatGPT 插件平台构建的。

对于金融数据，我们使用了 MCP 工具和连接器来让模型获得所需的信息。我们使用引用元数据和 MCP 应用让用户能够检查数据来源，MCP 应用也驱动了交互式财务图表。我们结合使用 Skills 和共享制品工具来指导金融工作流程，并生成 Excel 模型和 PowerPoint 演示文稿。在金融入职流程方面，我们利用了原生的插件入职体验。

这对构建者来说意味着：你可以专注于让你的产品具备价值的专有领域知识。如果你拥有独特的数据、现有的工具，或者对特定工作流程有深刻的理解，你可以利用这些构建模块将其带入 ChatGPT，并围绕它打造体验。金融服务只是一个例子，但我坚信这个机遇远不止于金融领域。我个人相信，我们将看到数家仅仅作为 ChatGPT 插件构建出来的十亿美元规模的企业。随着模型能力的增强，这种机遇将不断演进。

<details>
<summary>Original English</summary>

Now, let me talk about how we built it.

Let's start with data. In finance, the work you can do is limited by the quality of the information you have access to. So, we wanted the product to come with the sources professionals rely on, from financial statements and earning transcripts to market and private company data.

We looked at existing MCP connectors for financial data and found that many had issues with latency, errors, or search quality. So, we went and licensed a lot of this data directly and built our own hosting and search indices using the same infrastructure as our web index. We still use the MCP protocol to give the model access to the data, but hosting and indexing it ourselves gives us more control over the quality and the reliability of the experience. It also gives us the flexibility to post train our models to work with these data sets.

The analogy I like to use is MCP and skills are like handing an instruction manual to a junior analyst versus post training, where the model's like having a senior analyst who's been working with the data for over two decades and knows all of its quirks like the back of their hand. MCP and skills give the model access and instructions. Post training can help it develop more familiarity with the data itself.

Once we had that data foundation in place, the next step was making it easy to turn that information to professional grade work. For financial professionals, that work often takes the form of an Excel model, a PowerPoint presentation, or written analysis that needs to be reviewed and shared with other people.

So, we focus on helping the model produce those outputs in a way that fits the firm's existing workflows. We built a template system that gives users access to the firm's approved templates when generating spreadsheets and presentations. The goal is to reduce the work someone has to do to get an output ready for their team or clients.

We also added things like interactive financial charts, so users can explore stock prices and financial metrics directly within ChatGPT as they work through an analysis. And we built citation viewers that let people inspect the source passages and tables in behind an answer. In finance, you need to be able to check where a number came from and understand the context around it. We wanted that review to be a natural part of the experience. These are the kind of product details that help turn a model's capabilities into work that someone can use.

The part I think that is most relevant for people in the room is how we built it. Much of the functionality you just saw was built using the same ChatGPT plugin platform that's available to you as developers.

For financial data, we used MCP tools and connectors to give the model access to the information it needs. We use citation metadata and MCP apps let users inspect the sources, and MCP apps also power interactive financial charts. We use skills together with shared artifact tools to guide what financial workflows and produce Excel models and PowerPoint presentations. And for financial onboarding, we leveraged the native plugin onboarding experience.

What that means for builders is you could is that you can focus on the expertise that makes your product valuable. If you have unique data, an existing tool, or a deep understanding of a particular workflow, you can use these building blocks to bring that into ChatGPT and create an experience around it. Financial services is just one example, but I do think this this opportunity expands far beyond finance. I personally believe that we're going to see multiple $1 billion businesses built simply as ChatGPT plugins. And that opportunity will keep evolving as the models become more capable.

</details>

### 模型能力的演进轨迹：扩展、算法与 Unhobbling

最后但同样重要的是，我想用剩下的时间谈谈未来的走向，以及这对我们今天应该构建的产品意味着什么。我想从模型能力和对未来的预期开始谈起。

模型提升得如此之快，以至于很难对其未来有一个直观的感知。建立这种直觉的一个有效方法是回顾过去。过去几年的一个显著特点是，这种进展的某些部分是多么具有可预测性。

模型的改进来自三个广泛的、有时重叠的驱动力：扩展计算量（scaling compute）、改进算法（improving algorithms），以及我们称之为“Unhobbling”（解除束缚）的过程——即找到从模型中榨取更多有用工作成果的方法。我们会在后面的幻灯片中回过头来讨论 unhobbling。

在 2022 年和 2023 年，最显而易见的驱动力是预训练，这意味着通过扩大模型规模和增加更多数据来扩展计算量。通过利用缩放定律（scaling laws），研究人员能够高度准确地预测模型性能。例如，在 GPT-4 完成训练之前，OpenAI 的研究人员就能够预测其最终损失（loss）以及它在代码评估中的表现。

算法方面的改进也令人惊讶地平稳。一项研究发现，从零开始达到给定的语言模型性能水平所需的计算量大约每八个月下降一半。尽管你无法预测每一次突破的具体时间点，但累积的改进速度遵循着一个惊人稳定的趋势。

在 2024 年和 2025 年，推理（reasoning）成为了推动进展的另一个主要驱动力。我们利用强化学习和后训练来教导模型更有效地解决问题，并且在模型作答时赋予其更多的思考计算量。这开辟了与预训练并行的另一条提升性能的途径。

然而，对于那些不知情的人来说，OpenAI 曾在预训练方面遇到了问题，因此在扩展模型时遇到了困难。在 2026 年，我们已经解决了许多这些问题，并且正如大家通过 GPT-5 Soul 和 GPT-6 Astra 所看到的那样，我们成功训练出了更大、更强的模型。

在这些年里，研究人员对进一步扩展的潜在障碍提出了担忧。例如在 2024 年，许多研究人员担心潜在的“数据墙”（data wall），即我们会耗尽用于训练的人类生成文本。但是，像合成数据生成、基于可验证奖励的学习，以及从每个单独 token 中学习更多内容的算法改进等技术，已经从根本上解决了这个问题。我们还通过稀疏注意力机制（sparse attention）和压缩（compaction）等技术解决了上下文窗口长度等问题。

展望 2027 年，我坚信过去的趋势线将会延续，我们将训练出更大、更高效、更强大的模型。显然，我们仍然有非常棘手的问题需要解决，尤其是在对齐和安全性方面。但就像过去一样，我相信在强大模型日益辅助下的人类智慧，也将帮助我们在这些问题上取得进展。

那么，模型在 2027 年底会达到怎样的水平？我们以数学为例。2023 年，GPT-4 在 SAT 高中数学测试中得了 700 分（满分 800 分）。到了 2025 年，一个 OpenAI 模型在国际数学奥林匹克竞赛中达到了金牌水平。而在 2026 年初，一个内部模型推翻了一个与数学家自 1946 年以来一直在研究的问题相关的长期猜想。最近，一个内部模型提出了纳维-斯托克斯千禧年大奖难题（Navier-Stokes Millennium Prize problem）的一个解法，并且我们还分享了涵盖 372 个结果家族的 719 篇数学研究手稿。

在短短几年内，我们已经从在高中数学考试中取得优异成绩，发展到 AI 系统在数学前沿产生原创性研究成果。如果我们在接下来的一年里看到与过去几年大致相符的进展，我预计到 2027 年底，在跨不同领域和专业的越来越多的高难度任务上，模型的表现将超越顶尖的人类专家。数学让我们初步看到了那会是什么样子。

<details>
<summary>Original English</summary>

Last but not least, I'd like to spend the rest of the talk on what comes next and what that means for the products we should be building today. I'd like to start by talking about model capabilities and expectations for the future.

Models are improving so quickly that it can be difficult to get an intuitive sense of what comes next. One useful way to build that intuition is to look backwards. Something remarkable about the last couple of years is how predictable parts of that progress have been.

Model improvements have come from three broad, sometimes overlapping drivers. Scaling compute, improving algorithms, and something we call unhobbling, which is about finding ways to get more useful work out of the models. We'll come back to unhobbling on a on a later slide.

In 2002 and 2003, the most visible driver was pre-training, which meant scaling compute by making the models bigger and adding more data. By leveraging scaling laws, researchers were able to predict model at performance with high accuracy. For example, before GPT-4 finished training, OpenAI researchers were able to predict its final loss, as well as its performance on a coding eval.

Improvements on the algorithm side have also been surprisingly steady. One study found that the compute needed to reach a given level of language model performance from scratch fell by roughly half every eight months. Although you can't predict the timing of each individual breakthrough, the cumulative rate of of improvement follows a surprisingly steady trend.

In 2024 and 2025, reasoning became another major driver of progress. We used reinforcement learning and post-training to teach models to work through problems more effectively, and we gave them more compute to think when answering. That opened up another way to improve performance alongside pre-training.

However, for folks that don't know, at OpenAI, we ran into problems with pre-training and therefore had difficulty scaling the model. In 2026, we've been able to solve many of these issues, and we've successfully trained larger and more capable models, as you've seen through GPT-5 Soul and GPT-6 Astra.

Throughout these years, researchers have raised concerns about potential barriers to further scaling. For example, in 2024, many researchers were concerned about a potential data wall, where we would run out of human-generated text to train on. But techniques like synthetic data generation, learning from verifiable rewards, as well as algorithmic improvements to learn more from each individual token, have essentially solved this problem. We've also solved concerns around things like context window length using things like sparse attention and compaction.

Looking ahead to 2027, I strongly believe that the trend lines of the past will continue and that we'll train larger, more efficient, and more capable models. We clearly still have very difficult problems to solve, especially around things like alignment and safety, but like we have in the past, I believe that human ingenuity, increasingly assisted by capable models, will help us make progress on those problems, too.

So, how good will models be at the end of 2027? Let's use math as an example. In 2023, GPT-4 scored 700 out of 800 on SAT high school math. By 2005, an OpenAI model reached gold medal status on the International Math Mathematical Olympiad. And in 20 In early 2026, an internal model disproved a long-standing conjecture related to a problem that mathematicians have been working on since 1946. More recently, an internal model proposed a solution to the Navier-Stokes Millennium Prize puzzle um problem, and we also saw shared 719 mathematical research manuscripts across 372 families of results.

In just a few years, we've gone from a strong score in a high school math exam to AI systems producing original research at the frontier of mathematics. If we see another year of progress roughly in line with what we've been seeing over the past couple years, I expect that by end of 2027, models will outperform even leading human experts on a growing range of difficult tasks across different fields and specialties. Mathematics gives us an early glimpse of what that could look like.

</details>

### “可用性阈值”现象与产品构建者的机遇

虽然能力曲线看起来可能是渐进的，但我们工作方式的变化可能会让人觉得很突然。我把这称为“阈值现象”（threshold phenomenon）。

对于任何给定的任务，都有一个“可用性阈值”——即模型变得足够有能力和可靠以至于能为你节省时间的临界点。这个阈值取决于你正在从事的工作，以及它需要多少检查或人工审阅。

在低于该阈值时，改进可能很难被感知到。模型可能会给出更好的答案，犯更少的错误，或者在任务中走得更远。但是，如果检查和修改它的工作仍然耗费与你自己完成相同的时间，那么你的实际评估并没有改变：它仍然没有用。能力上的实质性进步会让人觉得几乎没有进展。

随后，模型跨过了那个阈值。突然之间，它生成了你可以直接使用的东西。你花在审查它上面的时间变得远小于它为你节省的时间。你开始经常使用它，最终你放心地将该任务委托给它。这种转变会让人感觉像是一次巨大的飞跃，即使底层的技术改进与之前的几次改进幅度相似。所改变的是，这项进展对你来说变得有用了。

这有助于解释为什么模型的进展有时让人感觉突如其来，即使底层趋势的某些部分一直是稳定且可预测的。因为困难的任务具有不同的阈值，我们应该预期这些时刻会在我们所做的各种工作中在不同时间到来。

因此，当大家思考正在构建的产品时，我鼓励你们问问自己：今天我低估了哪些模型能力，仅仅因为它们目前还不太有用？一年后这些能力可能会达到什么程度？然后再想一想，如果这些能力跨越了可用性阈值，并且变得足够可靠以至于可以委托任务，你会构建什么？界面会发生怎样的改变？用户仍然需要控制、审查或批准什么？

这些是我们现在就可以着手解决的产品和设计问题。我们希望准备好合适的产品体验，以便当模型跨越该阈值时，人们能够立即利用这些能力，从而让大家能够始终领先竞争对手一步。

<details>
<summary>Original English</summary>

And while the capability curve may look gradual, the change in how we work can feel sudden. I call this the threshold phenomenon.

For any given task, there's a threshold of usefulness, the point where a model becomes capable and reliable enough to save you time. That threshold depends on the work you're doing and how much checking or human review it requires.

Below that threshold, improvements can be hard to appreciate. The model might produce better answers, make fewer mistakes, or get further through a task. But if checking and fixing its work still takes as long as doing it yourself, your practical assessment hasn't changed. It's still not useful. Meaningful improvements in capability can feel like like little progress.

Then the model crosses that threshold. Suddenly, it produces something you can use. The time you spend reviewing it becomes much smaller than the time it saves you. You start using it regularly, and eventually you become comfortable delegating that task. That transition can feel like an enormous leap, even if the underlying improvement was similar to the previous few improvements. What changed is the progress became useful to you.

This helps explain why model progress sometimes feels sudden, even when parts of the underlying trend have been steady and predictable. And because difficult tasks have different thresholds, we should expect those moments to arrive at different times across the work that we do.

So, as you think about the products you're building, I'd encourage you to ask yourself, what model capabilities am I under appreciating today because they aren't quite useful yet? Where might those capabilities be a year from now? Then think about what you would build if those capabilities crossed the threshold of usefulness and became reliable enough to delegate. How would the interface change? What would the user still need to control, review, or approve?

Those are product and design questions we can start working on now. We want to have the right experiences ready so that when the models cross that threshold, people can take advantage of the capabilities right away, and so you can stay one step ahead of your competitors.

</details>

### 金融领域的潮水与波浪：通用能力与特定后训练

那么，这对金融意味着什么？

我认为有两股力量将推动更多的金融工作跨越可用性阈值。我将它们想象为“上涨的潮水”以及“其上的波浪”。

上涨的潮水是底层模型的根本性改进。从历史上看，我们并没有专门为金融投入大量的训练时间或算力。大家今天看到的许多金融能力，都来自于构建更大、更强大的模型，以及从数学、代码编写和推理等领域培养的可迁移技能。随着这些通用能力的提升，它们水涨船高地拉动了许多类型金融工作的表现。

而波浪则是当我们直接专注于金融时所发生的事情。我的团队正在主导一项投资，大幅增加金融领域的针对性后训练。这里的核心思想是在那些广泛的能力之上，更直接地针对人们在金融中所做的工作来训练模型。这可以在上涨的潮水之上，针对特定任务创造出性能的峰值。

在接下来的 3 个月里，我们将专注于提升通用金融推理能力以及这些模型所生成工作的质量——分析财务信息、构建 Excel 模型和制作 PowerPoint 演示文稿。这些任务在初级分析师的日常工作中占了很大比例，我们希望其产出准确、结构良好，并在实际工作流中日益发挥效用。

除此之外，我们计划在资深银行家、分析师和投资人在应对更棘手问题时所展现的判断力上投入更多。这包括接收海量信息、判断什么是重要的，并在本质上尝试预测未来：预测公司的收益、评估大宗商品价格可能的走势，或评估哪些企业具有投资吸引力。我们的目标是在 2027 年的某个时候，让模型在这些类型的金融任务上匹敌顶尖人类专家的水平。

我们预计这种进展将来自这两股力量的协同作用：底层模型的持续改进，以及我们团队针对金融从业人员的实际工作进行更直接的训练。

<details>
<summary>Original English</summary>

So, what does this mean for finance? I think there are two forces that will push more financial work across that threshold of usefulness. I think of them as a rising tide and the waves on top.

The rising tide is the underlying improvements to the underlying model. Historically, we haven't dedicated a significant amount of training time or compute specifically to finance. Much of the financial capabilities you see today have come from building larger, more capable models, and from transferable skills developed in areas like mathematics, coding, and reasoning. As these general capabilities improved, they lift the performance across many kinds of financial work.

The ways are what happen when we focus directly on finance. My team is leading an effort to invest significantly more in finance specific post training. The idea here is to build on those broad capabilities and train the model more directly on the work people do in finance. That can create peaks in performance on particular tasks on top of the rising tide.

Over the next 3 months, we'll focus on improving general financial reasoning and the quality of the work these models produce, analyzing financial information, building Excel models, and creating PowerPoint presentations. These are the kinds of tasks that make up a significant percentage of the daily work of a junior analyst, and we want the output to be accurate, well-structured, and increasingly useful in real workflows.

Beyond that, we plan to invest more in the kinds of judgment that senior bankers, analysts, and investors bring to more difficult questions. This includes taking in large amounts of information, deciding what matters, and essentially trying to predict the future. Forecasting a company's earnings, assessing where commodity prices might go, or evaluating which businesses are attractive investments. Our goal is for models to match the the performance of the best human experts on these types of financial tasks sometime in 2027.

We expect that progress to come from both forces working together. The underlying model continuing to improve, and our team training it more directly for the work people do in finance.

</details>

### Unhobbling 的未来形式：主动且持久运行的 Agent

我们谈到了模型如何变得越来越强大，以及我们如何训练它们在特定任务上表现得更好，但我想回到我之前提到的第三个驱动力：Unhobbling（解除束缚）。

我们已经看到了一些例子。ChatGPT 使用 RLHF（基于人类反馈的强化学习）来教会模型遵循指令并与我们对话。工具使得它们能够搜索信息、编写和运行代码，并与我们使用的软件进行交互。这些都让模型在现实世界中变得更有用。

我认为解除束缚的下一种形式将是主动（proactive）且持久运行（persistent）的 Agent。

今天，我们与 AI 的许多交互仍然发生在我们打开对话并告诉它下一步该做什么的时候。一个持久运行的 Agent 可以坚持目标，记住相关的上下文，并在后台持续工作。一旦你给了它一个方向，即使你没有主动提示它，它也能取得进展。

持久性至关重要的另一个原因是它改变了 API，或者说改变了人们与 Agent 合作的方式。如今，要充分利用 AI Agent 需要学习一套新的工作流程：学习如何 prompt 它，学习如何使用它的工具。而一个持久运行的 Agent 可以以一种更熟悉的方式工作：你可以给它一个项目，共享上下文，并向它询问进度汇报。

这与人类与其他人类协作的方式更为相似，因此让那些没有掌握初始 prompt 技能的人更容易使用 AI。

<details>
<summary>Original English</summary>

We talked about how models are becoming more capable and how we can train them to perform better on specific tasks, but I want to come back to one third driver I mentioned earlier, unhobbling.

We've already seen few examples. Chat GPT used RLHF to teach models to follow instructions and have conversations with us. Tools allow them to search for information, write and run code, and interact with the software we use. Each of these makes the model more useful in the real world.

I think of the next form of unhollowing will be proactive and persistent agents. Today a lot of our interactions with AI still happen when we open a conversation and tell it what to do next. A persistent agent can hold on to a goal, remember the relevant context, and continue working in the background. Once you've given it a direction, it can make progress even when you aren't actively prompting it.

The other reason persistence matters is it changes the API or the way people work with the agent. Today getting the most out of AI agents requires learning a new workflow, learning how to prompt it, and learning how to use it to tools. A persistent agent can work in a way that's more familiar. You can give it a project, share context, and ask for an update.

It's much more similar to how humans work with other humans, and therefore makes the AI more accessible to people um that don't develop those initial skills.

</details>

### 针对 2027 年金融领域的三个预判

最后，让我以对 2027 年金融领域的三个预判来结束演讲。这只是我对随着模型改进将发生什么的几点预期。

第一，人们将极少甚至不再依赖 Excel 和 PowerPoint 来制作财务模型或路演 PPT（pitch decks）。

第二，AI 金融分析师将开始让人感觉像人类同事一样。它们会记住你的偏好和前几天的上下文，承担任务的主人翁责任，主动跟进，并在你专注于其他事情时在后台继续工作。

第三，在关键的金融任务上，模型将开始超越顶尖的人类专家。这包括预测财报收益和构思投资思路等任务。我预计在做出这些具有重要经济意义的前瞻性判断方面，模型将超越最优秀的人类。

这就是我对 2027 年的三个预判。如果这就是我们预期在 2027 年所处的位置，那么我留下最后一个问题供大家思考：

你今天应该开始构建什么，以便为模型明天必然跨越的阈值做好准备？

谢谢大家。

>> [掌声]

<details>
<summary>Original English</summary>

Let me close with three bets for finance in 2027. These are just a couple of my expectations for what comes as the models improve.

First, people will rely rarely, if ever, on Excel and PowerPoint to make financial models or pitch decks.

Second, AI financial analysts will start to feel like human coworkers. They'll remember your preferences and context from the previous days, take ownership of assignments, proactively follow up, and keep working when you're focused on something else.

Third, models will start to outperform the best human experts on critical financial tasks. That includes things like forecasting earnings and developing investment ideas. I expect models to become better than the best people at making these economically important forward-looking judgments.

Those are my three bets for 2027. And if this is where we expect to be in 2027, I'll leave you with one last question. What would What should you start building today to be ready for inevitable thresholds that the models will cross tomorrow?

Thank you.

>> [applause]

</details>