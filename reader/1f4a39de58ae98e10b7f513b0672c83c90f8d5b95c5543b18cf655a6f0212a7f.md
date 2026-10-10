---
author: AI Engineer
date: '2026-06-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wjXowoQ7E8c
speaker: AI Engineer
tags:
  - ai-engineering
  - agentic-workflow
  - inference-efficiency
  - open-weights
  - llm-memory
title: AI Engineer Melbourne 2026：模型之外的 AI 工程、推理经济学与代理记忆架构
summary: 2026 年墨尔本 AI 工程师大会主旨演讲涵盖了 AI 领域的最新趋势：从单纯的模型竞争转向服务与数据生态，探讨了推理成本与性能的权衡、Open Weights 模型的崛起，以及如何通过多模型可选性和 CPU 工作流优化工程成本。此外，专家们深入分析了 AI 代理的记忆架构和实时语音代理的低延迟挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - George Cameron
  - Sarah Saxs
  - Jeff Huntley
  - Igor Costa
companies_orgs:
  - Artificial Analysis
  - Notion
  - GitHub
  - Anthropic
  - OpenAI
  - Google
  - Vercel
  - AutoHand
products_models:
  - Claude Opus 4.8
  - GPT-5.5
  - Gemini 3.5 Flash
  - DeepSeek V4 Pro
  - Cursor
  - Claude Code
media_books: []
status: evergreen
---
### AI 工程师的崛起与六大主题

**[主持人]**: 我非常擅长总结主题，所以我准备了六个主题，想以此为这次会议接下来的内容定个基调。

<details>
<summary>Original English</summary>

**[Host]**: I'm really good at sort of summarizing themes and so I prepared six themes that I wanted to set your pallet with I guess for the rest of this conference.

</details>

**[主持人]**: 我想谈的第一件事是 **AI 越来越多地不仅仅是模型**。这里有两张并排的照片，OpenAI 正在转向……模型正日益成为一种“载体”。AI21 也在转型，AI 同样关乎**服务、数据、品牌和产品**。我认为这些趋势对 **AI 工程师** 来说非常有利，因为这涉及模型之外的一切。

<details>
<summary>Original English</summary>

**[Host]**: The first thing I wanted to talk about is how AI is increasingly not just models. Um here's two sideby-side shots of open AI saying into um a model is increasingly the harness right AI21 is pivoting to is as well and also uh AI is also about services and data and brand and product right so I think this all these trends are really good for AI engineers because it is everything outside the model.

</details>

**[主持人]**: 第二个趋势显示模型依然关键。我认为最真实的衡量基准可能是 **AI 编写的代码量**。这是 GitHub 上 **Cloud Code** 提交量随时间变化的截图。截至 2 月，这一比例约为 4% 到 5%。现在，它可能处于 10% 左右。到今年年底，它将达到 40% 到 50%。大家都能意识到这正在改变整个世界。

<details>
<summary>Original English</summary>

**[Host]**: But the second trend also shows that the models are and I think the realist world benchmark is probably the amount of code that's written by AI. Uh this is a screenshot of cloud code commits in GitHub over time. Uh as of February, it was about 4 to 5% of all code. Right now, it's probably sitting at around 10% and towards the end of the year, it's going to be around 40 to 50%. Everyone is sufficiently appreciating that is currently changing the entire world.

</details>

**[主持人]**: **Cloud Code 代理**，或者说代理本身正在实现自我托管和启用“插槽分支”（slot forks），这非常有趣。当然，显然还有 **O1 定律（Oplaw）时刻**，我不需要多说。这也标志着代理在**不可验证领域**的出现。最后，高潜力的 AI 正在超越普通的知识工作，向科学、技术、数学等前沿领域迈进。

<details>
<summary>Original English</summary>

**[Host]**: Cloud code agents are I mean agents are also just self-hosting and enabling slot forks which are really interesting. And also of course obviously there's the Oplaw moment which I don't need to tell you guys about you've heard enough about it already but I'm also very which starts to mark the emergence of agents in non-verifiable domains and I think lastly the high potential is exceeding normal knowledge work knowledge work towards the frontier uh science and technology and math software development life cycle first starting with the idees last year.

</details>

**[主持人]**: 这被称为**杰文斯悖论（Jevons Paradox）**。这就是为什么我认为 **AI 工程将是最后一份工作**，为什么你们都有职业安全感，以及为什么你们将接管世界。希望接下来的两天你们能有卓有成效的讨论。

<details>
<summary>Original English</summary>

**[Host]**: This is called the jevans paradox as well. And really this is my argument around why AI engineering will be the last job, why you guys all have job security and why you guys will take over the world. So I hope over the next two days you have really fruitful discussions and I'm looking forward to catch up online. See you.

</details>

### AI 智能基准与模型景观

**[主持人]**: 好的，接下来我们要开始正式演讲。首先有请 **George Cameron**。George 是一位澳大利亚人，现在在旧金山。他几年前为了解决自己的问题创办了一家公司。他和 **Artificial Analysis** 的创始人曾在 **Latent Space** 接受过 Shan Wang 的采访。他们消耗大量 Token 来通过各种基准测试客观验证模型的排名和对比。

<details>
<summary>Original English</summary>

**[Host]**: All right. And now Sean really owes me one. So we'll be getting here before too long. Don't you worry. All right. So to kick off the talks proper, we have George Cameron. So George is an Aussie who now is in San Francisco. There seems to be a bit of a a patent there and started something kind of to solve their own problems a couple of years ago. There's a great interview with Shan Wang on Leighton Space with uh the founders there at artificial analysis which is the firm that he founded.

</details>

**[主持人]**: 这在今天的对话中非常有价值，我们将讨论 **Token 经济学** 以及推理成本如何开始影响我们的产品策略。有请来自 Artificial Analysis 的 George Cameron。

<details>
<summary>Original English</summary>

**[Host]**: So if you want to hear the backstory and everything they do, I highly recommend that. Um but what they do is essentially they burn lots of tokens to uh objectively verify across all kinds of benches and benchmarks their own and uh and open ones that um uh uh you know what how the models rank, how they compare. So this is very valuable as part of the conversations we're going to have this morning where we're going to look about tokconomics and and how uh kind of the cost of using inference is starting to build into our product strategies. But to set the scene with all the insights that he has into the modern uh model landscape, would you please welcome George Cameron from artificial analysis.

</details>

**[George Cameron]**: 大家好，我是 George，Artificial Analysis 的联合创始人之一。我们是一家独立的 **AI 基准测试公司**。我们通过网站 artificialanalysis.ai 帮助数百万用户了解 AI 动态，并通过独立基准测试在不同技术间做出选择。

<details>
<summary>Original English</summary>

**[George Cameron]**: All righty. Are we uh there we go. Great. Thanks for having me here. Um so I'm George, one of the co-founders of Artificial Analysis. Very quickly about us. We're an independent AI benchmarking company. We help millions of users with our website artificial analysis.ai understand what's happening in AI and choose between all the different technologies with our independent uh benchmarks.

</details>

**[George Cameron]**: 本周初，Jensen 在发布 **Neotron 3 Ultra** 时提到了我们；上周 Anthropic 发布 **Opus 4.8** 时也引用了我们的数据。我很高兴能在这里分享我们如何看待 2026 年 6 月的 AI 现状。我们对整个 AI 栈进行基准测试，包括代理、模型、推理提供商和硬件。

<details>
<summary>Original English</summary>

**[George Cameron]**: Um and we're also quite widely referred to in the industry. At the start of this week, Jensen referred to us for the Neotron 3 Ultra release. Last week, Anthropic with Opus 4.8 and our GDP vala benchmark the week prior to that. Sunda with a GPT, sorry, Gemini uh 3.5 flash release. Um and so very happy to be here and share a bit about um what we do and give an overview of how we see the state of AI in June 2026. We benchmark across the AI stacks. We benchmark agents, models, uh in inference providers and and hardware. Uh and we also benchmark um kind of text focused language models but also image, video, speech, uh and music models as well.

</details>

**[George Cameron]**: 这张图表显示了过去几年主要 AI 实验室发布的领先模型。看起来有些眼花缭乱，因为这几年确实非常疯狂，进展神速。我想展示的是，AI 的进步并未放缓。2025 年底有人说进步变慢了，但随后 **Opus 4.6** 发布，代理开始处理更长周期任务，这些声音就消失了。

<details>
<summary>Original English</summary>

**[George Cameron]**: I think to start off with um I'll provide essentially this chart. It's a bit hectic. Um, which shows the leading releases from the leading AI labs over the last few years. And it's a bit hectic, but I think that's probably no surprise to us in this room because it's been a hectic few years. There's been a lot of releases uh and a lot of progress. And I think why I like to start with this chat is it shows that AI progress has not slowed down. I think claims of that have been greatly uh greatly exaggerated. I heard a lot of that in late 25, but then um Opus 4.6 came out. Um agents started working for much longer horizons and uh people quieted down a bit. And I think this chart shows that really well is that there's more dots on this chart than ever. Um if you look at the last 3 months here, which shows there's been more leading releases um and it's going up and to the right pretty quickly, which is showing progress in intelligence.

</details>

**[George Cameron]**: 我们推出了 **Artificial Analysis 智能指数**。这是综合了 10 个基准测试后的指标，用于对比语言模型的智能。目前的领先模型中，上周发布的 **Claude Opus 4.8** 已经超越了 **GPT 5.5**，成为最智能的语言模型。

<details>
<summary>Original English</summary>

**[George Cameron]**: I'll first introduce our artificial analysis intelligence index metric. Now this is a synthesis metric of 10 benchmarks that we run to test language model intelligence which provides an highle synthesis overview uh and relative comparison of the intelligence of these models. We have the current set of leading models on this chart here. And I think to note, Claude Opus 4.8 last week took the mantle from GBT 5.5 um as the leading language model in terms of intelligence.

</details>

**[George Cameron]**: 但不仅仅是看谁最聪明。由于成本、速度和各种权衡，目前仍然有理由使用其他模型。从全球分布看，主要是**美国和中国**的故事。法国有 Mistral，韩国也有成功的**主权 AI** 计划，还有阿联酋。值得注意的是，澳大利亚目前还没有能与前沿智能竞争的模型。

<details>
<summary>Original English</summary>

**[George Cameron]**: But I think rather than kind of stopping there, if if we're able to stop there, it'd make our jobs a lot easier. But I think there's a the story is is that there's a reason still uh to use other models considering the cost, the speed, and other trade-offs at play amongst language models today. I'll first take a look at different perspectives on thinking around the current state of models. You can see here that it's very much a US and China story when looking at where the labs making these leading language models are based. Also present on this chart is France with Mistral, South Korea with a number of labs in a very successful sovereign AI initiative. Um and then also the United Arab Emirates. Um I think to us in this room notedly missing is Australia. Australia doesn't have kind of language models that are competitive with the frontier in terms of intelligence. Um and from my perspective, I I don't think that's going to happen uh h happen soon either.

</details>

**[George Cameron]**: 另一个视角是**权重开放（Open Weights）**模型。开放权重模型在智能上一直落后于私有模型，但大约保持着 **3 到 9 个月** 的差距。这在几年前并不是定论，但我们看到它们跟上了。因为对于那些寻求灵活性、微调能力的用户来说，开放权重模型很有吸引力。

<details>
<summary>Original English</summary>

**[George Cameron]**: Another perspective is looking at open weights or colloally open source models um compared to that of proprietary models and proprietary intelligence achieved. On the y-axis we have our intelligence index uh and then on the x-axis release state and what these lines plot is the leading model that is kind of proprietary compared to open weights and open weights has always trailed proprietary intelligence. This chart is really going back to um kind of mid mid 23 with the Llama 270B release and you can see that yes open weights has trailed open uh sorry proprietary intelligence but it's in a sense kind of kept up roughly 3 to n months behind that of proprietary intelligence. This was not a given. It was an open question uh years ago um or only a few years ago people asking around the commercial models um that could support open weights um but I think what we've seen is kept up for a number of reasons and I think our perspective is this is going to continue with there being sufficient incentive there um particularly for labs wanting to serve those looking for open weights models for their flexibility the ability to fine-tune uh and other reasons.

</details>

**[George Cameron]**: 如果开放权重模型落后 3 到 9 个月，这意味着你现在可以通过开放权重的 **KimK 2.6** 或 **DeepSeek V4 Pro** 获得类似 Opus 4.5 或 GPT 5.2 级别的智能。这仍然是一个非常有力的选项。

<details>
<summary>Original English</summary>

**[George Cameron]**: And then secondly, I think another perspective on this is if open weights is kind of 3 to 9 months behind, we're looking at opus maybe 4.5 territory GBT 5.2 for the intelligence that um you can essentially get with open weights models with a Kimk 2 point Kim K 2.6 or the the latest kind of Deep Seek uh V4 Pro. Um and so it remains an option. Um you could do a lot with with with Opus 4.5 or GBD 5.2 And so it remains an option. Um and it looks like that's going to continue based on based on the last few years and our house perspective.

</details>

### 推理经济学：为何成本依然在上升？

**[George Cameron]**: 我们通过 **GDP vala** 代理基准测试发现，代理在处理经济价值任务上取得了显著进步。现在的模型（如 GPT 5.5）提供的分析比一年前深入得多。同时，现在的 **智能正变得越来越便宜**。你可以比六个月前买 Opus 4.5 更便宜的价格买到 Kim K 2.6。

<details>
<summary>Original English</summary>

**[George Cameron]**: We benchmark using quantitative benchmarks but we try and essentially ensure that those benchmarks are aligned from real world use. ... and I think what we tell here with our GDP vala agentic benchmark that uses an open AI data set we turned it into an aentic benchmark is a perspective of okay a leading model a year ago with claude 4 ... and then now with GBD 5 GBD 5.5 and you can see progress is being made in terms of real world knowledge work output... I think one kind of two things that are hard to reconcile in AI today is one that we have cheaper intelligence. So it's cheaper than ever to access GPT4 level of intelligence. Kind of going back to what I was saying earlier, you can get kind of Kim K 2.6 now cheaper than you can get Opus 4.5 uh you know six months ago.

</details>

**[George Cameron]**: 但是，为什么我们公司的**开销却在增加**？大家纷纷转向每月 200 美元的 Claude Code 或 Codex 计划。我认为有六大驱动因素：1. 模型更聪明但更密集；2. 推理软件效率提升；3. 硬件效率提升（如 **NVL72** 节点）；4. 对前沿智能的无限需求；5. 推理模型需要消耗更多 **推理 Token** 来提升思考质量；6. 代理模式——过去是一问一答，现在代理需要多次交互来检查工作，一个任务可能产生 **60 到 100 次对话（Turns）**。

<details>
<summary>Original English</summary>

**[George Cameron]**: And so I think this speaks to you can get intelligence cheaper than ever, but we're also spending more than ever uh within our companies. We're kind of upgraded to the $200 a month uh claude code or codeex plans and kind of why is that is and I kind of break it down into six drivers here that we see is the most critical... 1. smaller models able to achieve more intelligence... 2. software efficiency gains... 3. hardware efficiency. A NVL72 node is able to offer a lower cost when serving at scale... 4. insatiable demand for frontier intelligence... 5. reasoning models. Labs are increasing intelligence through more reasoning tokens... 6. agents. ... Dealing with multiple turns for the same task. ... commonly seeing 60 turns uh for a GDP valet task. Um and so kind of 20 to 100 turns is quite sensible for many knowledge work tasks and it acts as a multiplier on the cost.

</details>

**[George Cameron]**: 在 6 到 18 个月的时间跨度内，达成同等智能水平的成本通常会下降 **10 到 100 倍**。如果你有一个任务可以用之前的模型完成，现在你可以通过选择新发布的较小模型来实现数量级的降本。

<details>
<summary>Original English</summary>

**[George Cameron]**: And what we see here is really in kind of six to uh 18 month periods you have the cost of that intelligence falling often 10 to 100 times. And this is something that we can all think about and take advantage of. If a task was able to you could do it with Opus 4.5. Odds are now that you can there's orders of magnitude at play. It's not 2x cheaper. It's you can go 10x cheaper in many cases by choosing a cheaper model that has more recently been uh been been released.

</details>

### Notion 的多模型策略与“可选项”杠杆

**[主持人]**: 接下来有请 Notion 的 AI 负责人 **Sarah Saxs**。她曾就职于 Google 和 Robinhood，主导 AI 建模、推理和代理编排。她将讨论 Token 成本如何反向影响产品策略。

<details>
<summary>Original English</summary>

**[Host]**: So Sarah is now head of AI at notion. ... she's the head of AI at Notion, but she's formerly been at Robin Hood and Google and she she's the engineering lead on AI modeling uh reasoning, agentic orchestration and model infrastructure. ... she's going to talk there's a bit of a theme emerging as I mentioned around tokens the cost of tokens how that feeds back a kind of back pressure of itself of its own back into our product strategy. So to hear about what they're doing there uh at notion would you please welcome Sarah Saxs.

</details>

**[Sarah Saxs]**: 谢谢。我完全同意刚才的演讲。我想谈谈实际服务客户时的挑战。如果你没有《财富》50 强公司那样的议价权，你该如何为客户提供最好的产品？

<details>
<summary>Original English</summary>

**[Sarah Saxs]**: Hi. Thank you for having me. ... I completely agree with everything that was just presented. And I think what I want to talk about is the challenge of actually serving that and making those decisions. ... What does it mean to work at when you don't have the scale and the negotiating power, but you want to be delivering what's best to your customers?

</details>

**[Sarah Saxs]**: 来看几个真实案例。案例 A：某推理模型升级了，单价没变，但处理同样任务产生的 **输出 Token 增加了三倍**，因为它思考得更多了。案例 B：一个后续模型比前代贵 40%，但前代模型四个月后就要停用。你会把价格提高 40% 吗？显然不能。

<details>
<summary>Original English</summary>

**[Sarah Saxs]**: Exhibit A, a reasoning model gets upgraded, but don't worry, it's the same price. Okay? Um it might be the same price per token, but you run it on the same exact task. And what happens? It's three times as many output tokens. ... Exhibit B. There's a successor model. ... It's 40% more expensive than its predecessor. But breaking news, the predecessor is being deprecated in four months. And you've built your whole product on top of it. Are you increasing your prices by 40%. No, hopefully not.

</details>

**[Sarah Saxs]**: 供应商有时也是你的竞争对手。在 Notion，我们处理每月数十万亿的 Token，但我们有超过 1 亿客户。我的工作就是代表这 500 万家中小企业进行规模化谈判。

<details>
<summary>Original English</summary>

**[Sarah Saxs]**: So the supplier is your competitor, right? ... My job at Notion is to represent that Fortune 5 million because they're our customers. Especially with usage based pricing, the accessibility of AI is determined by the price by the price of those workflows. ... we're handling um tens and tens of trillion tokens a month. Um but we also have over a hundred million customers. What does that mean? It means that I get to play that job of negotiating at scale, but bringing it to the rest of you.

</details>

**[Sarah Saxs]**: 很多公司被单一供应商锁死（Locked in）。他们为了获得巨额折扣而承诺了数千万美元的支出，结果失去了切换到更好或更便宜模型的能力。在 Notion，我们相信 **可选项（Optionality）就是价值**。我们刚刚推出了管理代理产品，你可以混合使用不同厂商的代理，让 Claude Code 编写修复，然后让 Codex 审查。

<details>
<summary>Original English</summary>

**[Sarah Saxs]**: One, I see that people are locked in. They have no exit. ... they've committed $20 million to one of that uses the best model available whatever it is. So for instance at notion um we just launched this. This is our manage agents product. We believe that there's value in optionality. You'll see in this example, you can use decagon agents, move them so Claude code can write a fix and then perhaps have Codex review it and then put it in a task list for humans to review, right?

</details>

**[Sarah Saxs]**: 并非所有流量都是平等的。修改数据库字段或分拣邮件，我们不需要最新的 GPT-6。我们会尽快让这些任务运行在 **Minimax** 或开放权重模型上。而对于深度研究和数据分析，我们需要提供最前沿的模型。我们的客户需要我们帮他们做选择，否则产品会变得极其昂贵。

<details>
<summary>Original English</summary>

**[Sarah Saxs]**: Not all traffic is equal. ... In notion, it looks like this. Changing a database field, triaging an email... let's get him on Miniax as soon as possible. ... Summarizing meeting notes. These are all things that we actually don't want to pay 40% more when GPT6 comes out... But for the frontier task, we need to be giving that frontier to our customers. Data analysis, deep research. The point is that our customers need us to choose for them. Otherwise... your product is inaccessible.

</details>

**[Sarah Saxs]**: 我们大约每三到四周就会为客户更换默认模型。这需要强大的 Eval（评估）团队。如果你被锁死了，你就在给用户提供糟糕的体验。

<details>
<summary>Original English</summary>

**[Sarah Saxs]**: We're changing our default model for our customers probably every three to four weeks. ... if you are, the second you go from January to February, you're giving your users a worse experience. Okay? It's not worth the discount.

</details>

### Token 之外：重回 CPU 与确定性

**[Sarah Saxs]**: 但是，如果根本不需要 LLM 呢？我们要离开“Token 镇”。为什么工程师把 CSV 转成 PDF 还需要消耗 LLM 的推理 Token？因为前沿实验室希望你 **Token 最大化**，但你的用户希望你 **结果最大化**。

<details>
<summary>Original English</summary>

**[Sarah Saxs]**: But what if you don't need an LLM at all? I know we said that this is welcome to Token Town, but we're leaving. ... Why would he ever need an LLM to do that? Why would you want that repeated task constantly using reasoning tokens to navigate MCPS? Okay, well because Frontier Labs want you to token max. ... Your users don't. Your users want you to outcome max.

</details>

**[Sarah Saxs]**: 许多任务在 **CPU** 上完成得更好。确定性是有价值的。我们与 Vercel 合作推出了 **Workers**，你可以托管小段代码作为 LLM 调用的 Action。对于某些重复性任务，这降低了 **80% 的 Token 成本**。我们要让 AI 变得负责、持久且价格合理。

<details>
<summary>Original English</summary>

**[Sarah Saxs]**: At notion, we believe that many tasks do better work on CPUs. Determinism is a valuable thing. State machines existed, right? ... So we've partnered with Verscell on the capabilities to launch what we call workers where you can actually call on internal APIs computer sandboxes host small small code as an action that your LLM calls. We've seen this decrease token cost by up to 80% for some of our customers on repeated tasks.

</details>

### 软件开发的商品化与好奇心测试

**[主持人]**: 接下来有请 **Jeff Huntley**。他一直在创新关于反压（Back pressure）和循环的想法。你们现在使用的 Codex 或 Cursor 强力模式（Grind mode）都有他的影子。

<details>
<summary>Original English</summary>

**[Host]**: So, please welcome or or maybe curse the man who brought us Ralph the Ralph Loop, um, Jeff Huntley.

</details>

**[Jeff Huntley]**: 软件开发现在的成本已经低于最低工资了。软件已经被 **商品化（Commoditized）** 了。产品经理现在也可以是软件开发者。这一年里，很多事情发生了变化。

<details>
<summary>Original English</summary>

**[Jeff Huntley]**: I'm going to say some pretty provocative things like software development now costs less than minimum wage. I want you to think deeply about this. Software has been commoditized. ... Product managers can now be a software developer. Doesn't mean they're a software engineer.

</details>

**[Jeff Huntley]**: 去年，我在 Atlassian 裁员前一周去演讲，说商业的**单位经济学**已经永远改变了。软件现在很容易创建，但这并不意味着你创建了正确的东西。我看到很多非专业开发者玩得很开心，因为技能已经被商品化了。

<details>
<summary>Original English</summary>

**[Jeff Huntley]**: ...talking about the unit economics of business have forever changed. ... software is now easy to create. Doesn't mean it is like you're creating the right things. ... Roslin is not a classical software developer by any means. At this meetup, there was product managers, designers. They're all having the time of their lives, folks. not really software engineers up there because our skill set has been commoditized.

</details>

**[Jeff Huntley]**: 以前软件是被“守门”的。我们要么懂控制电脑，要么给你一个界面让你配置。现在这种范式被粉碎了。每个人都可以控制电脑，可以写代码。

<details>
<summary>Original English</summary>

**[Jeff Huntley]**: Previously, software was gated. ... But that's just completely changed now. That's just smashed. The paradigms have smashed. Everyone can now control the computer. They can now write code. Previously, this was gatekeeped.

</details>

**[Jeff Huntley]**: **PewDiePie** 写的测试代码可能比在座的大多数工程师都好。他用 Antivus 和 Bomadil 进行属性测试，而你们还在用 Playwright。曾经稀缺的技能现在变得过剩了。

<details>
<summary>Original English</summary>

**[Jeff Huntley]**: I saw something yesterday. PewDiePie, believe it or not, PewDiePie is writing better tests than most software engineers here right here today. Go look at his GitHub. He's using Antivus with Bomadil with property based testing. Meanwhile, you're using Playright. What does it mean when the these skills that used to be scarce are now abundance.

</details>

**[Jeff Huntley]**: 现在的公司分为两类：一类是极其精简的初创公司，不到 50 人；另一类是需要经历三四年转型期的传统公司。**Block** 裁掉了一半员工，因为 Jack 是对的，AI 允许重新构思组织架构。

<details>
<summary>Original English</summary>

**[Jeff Huntley]**: I think there's now two classes of companies. We now have the companies that are already lean ... Meanwhile, we got everyone down the down on the bottom, which is every single other company out here, and they got to go through a J curve transformation program. ... You might have seen this block lays off nearly half its start because of AI. ... My honest take is Jack is right. AI would would allow to reimagine the organizational charts within most companies.

</details>

**[Jeff Huntley]**: 对于工程师来说，这是一种 **“好奇心测试”**。如果你不投资自己，你就无法保持竞争力。一名资深工程师应该能够白板解释什么是代理（Agent）。其实它很简单，就是一个 **While True 循环**，获取提示，存入数组，发送推理，检查是否需要执行工具，然后反馈结果。

<details>
<summary>Original English</summary>

**[Jeff Huntley]**: ...I call this a curiosity test ... A senior engineer should be able to explain how AI works under the hood. ... why is it when I ask a software engineer what is an agent? ... An agent is really simple folks. ... It's a wild true loop. It takes it takes the prompt, adds it to an array. You send it off for inferencing, and you look whether it needs to execute a tool ... and it sends it off for another turn. It's really simple.

</details>

**[Jeff Huntley]**: 消除系统中的**浪费**比 AI 本身更能加速发展。如果你还在用敏捷开发吗？改变了什么？作为工程经理，你应该问 AI 破坏了哪些旧流程。执行现在已经商品化了，**“构建什么”** 才是最难的问题。

<details>
<summary>Original English</summary>

**[Jeff Huntley]**: ...removing waste in from your systems and processes is a bigger accelerator than AI itself. ... asking them what is AI broken in the systems and processes like do you use agile anymore? ... ideas are more important execution because execution is now commoditized.

</details>

### 代理为什么会“遗忘”？记忆与架构

**[主持人]**: 接下来有请 **Igor Costa**。他是前 GitHub AI 负责人，也是 Copilot 幕后的功臣，现在创办了 **AutoHand**。他将探讨为什么编码代理会遗忘一切。

<details>
<summary>Original English</summary>

**[Host]**: So, next up we're going to try the highwire act again and we have Eigor Costa. ... Eager was a former leader of GitHub's AI efforts behind Copilot and over the last year or so he has founded AutoHand. ... he's going to talk to us about why our coding agents forget everything and the architecture of memory.

</details>

**[Igor]**: 为什么代理会忘事？我们过去认为增加上下文窗口就能解决问题，但上下文（Context）和记忆（Memory）是两回事。

<details>
<summary>Original English</summary>

**[Igor]**: Um in today talk I'm talking about like why agents forget things? ... We've added context window. ... and we treating this as normal. ... we treating the same thing as context and memory. They are very different things and probably they're the same thing. I don't know.

</details>

**[Igor]**: 我研究了九种记忆类型，但在 18 分钟内我只重点讲四个：1. **语义记忆**（定义规则）；2. **过程记忆**（技能累积）；3. **情境记忆**（时间维度的经验）；4. **反射记忆**（适应性）。

<details>
<summary>Original English</summary>

**[Igor]**: ...let's talk about like the nine types. ... I probably focus in four. So let's talk about semantic memory. ... then we went to procedure memory ... and then we talk about episodic memory. ... then comes the reflective memory.

</details>

**[Igor]**: 我们开源了 **Commander** 和编码 CLI。我们发现，与其把一切都塞进大模型，不如让记忆本身成为模型。我们尝试让代理像人类一样协作，通过“基因共享” trace 来孕育新代理，而不是加载所有上下文。

<details>
<summary>Original English</summary>

**[Igor]**: ...we open sourced the CLI ... we came with this concept at Autoan that we open so it's called commander. ... the memory is the model. ... the agents instead instead of like you try to load everything in the context, you load what is task at hand, you reflect upon and then you spin a new version of that with a different opinion.

</details>

**[Igor]**: 我们进行了一个实验：尝试让 AI 自动将 **Linux 内核迁移到 Rust**。目前已经运行了 10 个月，虽然还没完全成功，但已经从最初的 12% 进度稳步提升。我们使用的是来自新加坡 AI 实验室的**层级推理模型（Hierarchical Reasoning Model）**。

<details>
<summary>Original English</summary>

**[Igor]**: ...let's use the taste that Linux 12 has. So I want I I run I've built this application. We run this to for more than 10 months. ... We are still trying to migrate the Linux kernel to Rust. ... um they came up with this new architecture called hierarchical reasoning model. So the mo the memory is the model.

</details>

### 实时语音代理与 Rust 的力量

**[Vampi]**: 我们的经验来自于在印度为千万级用户构建全双工语音代理。在语音交互中，哪怕是轻微的停顿也会毁掉用户体验。

<details>
<summary>Original English</summary>

**[Vampi]**: This talk was to share a little bit from the trenches what we experienced when we started building full duplex voice agents ... scaling for countries like India ... where even the slightest glitch or pause would really ruin the voice user experience.

</details>

**[Vampi]**: 我们的结论是：**状态机和正则表达式** 与 LLM 结合效果最好。你不需要每次都让 LLM 处理语音转写，一百万个正则模式可以完成小模型能做的大部分工作，而且延迟极低。

<details>
<summary>Original English</summary>

**[Vampi]**: ...state machines and reg x go really well together. You don't need an LLM to constantly operate on the transcript. uh you could essentially have a reg x of a million odd patterns to essentially do what a small capable LLM can do. ... it gives ultra low latency. You don't need to waste an LLM call to do that, right?

</details>

**[Vampi]**: 如果你想要毫秒级的生产级语音代理，你必须转向 **Rust**。语音代理的架构本质上就是“延迟预算管理”。它是完全不容错的，所以我们选择了 Rust 并重建了 SDK，每天支持百万级外呼。

<details>
<summary>Original English</summary>

**[Vampi]**: If you want to use production voice agents at scale with a millisecond budget, you know, you've got to move to Rust. And the idea is that the latency budget is the architecture here for voice agents. ... you don't have any UX forgiveness it's completely unforgiving so therefore we chose Rust.

</details>