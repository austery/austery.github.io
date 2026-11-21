---
author: AI Engineer
date: '2026-10-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jiUC6IUMdvc
speaker: AI Engineer
tags:
  - agent-management
  - software-engineering
  - world-simulation
  - ai-economics
  - developer-tools
title: AI Engineer 2026 纽约大会回顾：从智能体管理到世界模拟的范式跃迁
summary: 本文记录了 AI Engineer 2026 纽约大会的核心议题，涵盖智能体管理、应用层研发策略、代码生成效率分析及世界模拟技术。大会展示了 AI 如何重塑工程实践与组织形态，并展望了未来垂直领域峰会及全球性 AI 博览会的规划。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/51 -->

### 大会开幕致辞与主持人介绍

**大会开场主持**: 大家早上好，欢迎回来。我们非常高兴能与大家共度这最后一天，在之前已经展开的精彩讨论基础上继续深入，并为更多重要议题腾出空间。话不多说，让我们欢迎今天的主持人——Turing Post 的创始人、作者兼分析师 Ksenia Se。

<details>
<summary>Original English</summary>

**Opening Announcer**: Good morning and welcome back. We're excited to spend this final day together building on the conversations already underway and making room for a few more big conversations. Without further ado, please welcome today's MC, founder, writer, and analyst at Turing Post, Ksenia Se.

</details>

**Ksenia Se**: 大家早上好！各位早上好！欢迎来到 AI Engineer New York 的第三天，也是最后一天。昨晚有人去参加什么很酷的活动了吗？最酷的是什么？好吧，我昨晚和 Swyx 一起去唱了卡拉 OK，简直太棒了，百分之百强烈推荐。

<details>
<summary>Original English</summary>

**Ksenia Se**: Good morning. Good morning. Good morning everyone. Um, welcome to the third and the final day of AI Engineer New York. Who went to a cool event last night? What was the coolest? Okay, I went to karaoke with Swyx and it was amazing. 100% recommend.

</details>

**Ksenia Se**: 没错，我是 Turing Post 的作者，也是你们今天的主持人。这其实是我第二次在纽约主持 AI Engineer 大会了，足见我有多热爱这项活动。

接下来让我们看一下今天的议程安排。昨天我们来自 Arize 的合作伙伴曾提出过一个问题：“AI 工程师究竟是做什么的？”而今天，Ryan Carson 带来了一场主题分享，题目就叫《你的新工作是智能体经理》（Your Job Is Now Agent Manager）。看来大家的工作职责一夜之间就发生了改变，希望各位的薪酬待遇也能随之跟上！

<details>
<summary>Original English</summary>

**Ksenia Se**: Um, so yes, I'm writing at Turing Post and I'm your MC for today. It's actually my second time MCing AI Engineer in New York. So that's how much I love it. And um let's go to the program because yesterday our partner from Arize asked what does an AI engineer do and today we have a session from Ryan Carson called "Your Job Is Now Agent Manager." So apparently your job description just changed overnight and I hope that the compensation will keep up.

</details>

### 赞助商鸣谢

**Ksenia Se**: 不过值得庆幸的是，各位雇主中相当一部分正是我们的赞助商！他们亲眼见证了大家肩负的职责在以多么惊人的速度演变。让我们为他们送上一轮热烈的掌声吧——小小的鼓励往往能带来深远的影响。

首先是我们最棒的主办级呈现赞助商：Arize！请大家鼓掌，非常感谢你们！

接下来是杰出的四大白金赞助商：Oracle、Sonar、WorkOS 以及 AXA。请大家热烈鼓掌！

屏幕上展示的是我们星罗棋布的黄金赞助商们，请大家把目光投向屏幕，向他们致以敬意并热烈鼓掌！

还有我们的白银赞助商们，让我们尽可能给他们最热烈的掌声，因为大家知道，热情可不是靠拘谨来衡量的，所以请大家尽情拍手！

最后，衷心感谢我们所有的支持合作伙伴，是你们让这场盛会成为可能。缺少在座的任何一位，这一切都无法实现。众擎易举，感谢大家！呼，我稍微有点紧张，时间也还早，非常感谢大家的包容。

<details>
<summary>Original English</summary>

**Ksenia Se**: But fortunately quite a few of your employers are also our sponsors. So they've seen how quickly your responsibility is changing and let's give them a warm round of applause. A little encouragement goes a long way. Our most amazing presenting sponsor, Arize. Please, thank you. Thank you. Thank you. The great four, our platinum sponsors, Oracle, Sonar, WorkOS, and AXA. Please, big round of applause. Um, scattering of gold sponsors all on this screen. Please, let's acknowledge everyone with our eyes and give them a big hand. And our silver sponsors. Let's give them as much applause as possible because you know we don't ration enthusiasm by fear. So please clap clap clap clap clap. And finally to all our supporting partners, thank you for making this possible. It would not be possible without anyone, with everyone, you know it takes a village. So thank you, thank you, thank you. Woo. I'm a little nervous. It's early, but thank you for bearing with me.

</details>

### 会场日程与主题脉络

**Ksenia Se**: 如果大家细心观察，会发现这三天的大会议程呈现出一条非常有趣的递进脉络：

在周一，大家可以参加极其实操动手的 Workshop 工作坊，聆听从 Cerebras、OpenAI 这样的行业巨头，到像 OpenPipe 这样体量虽小却极富探索精神的初创公司的前沿洞见。

到了昨天，核心讨论转向了 AI 如何切实转化为企业的营业利润率（operating margin）。

而今天，我们将聚焦于各家企业正在着力构建的核心能力、智能体（agents）能够承担的具体业务工作，以及管理这些智能体究竟意味着什么。

今天的各项议题将在各个分会场同步展开：
- 在当前的 Shannon 厅，我们将探讨财务、算力与基础设施；
- 在 Turing 厅——这也是我最喜欢的厅名——将涵盖评测（evaluations）、基准测试（benchmarking）、检索、自我演进的智能体以及技能构建；
- 在 Saturn 厅，大家将听到关于开发者工具、企业级数据、软件工厂、智能体权限控制以及 Token 经济学的深度分享；
- 最后的 McCarthy 厅，则将探讨模型成本、代码生成、智能体上下文、人工校验、银行系统落地部署以及金融智能体证据等前沿主题。

<details>
<summary>Original English</summary>

**Ksenia Se**: Um, if you've noticed, there is an interesting progression across all these three days. On Monday, you could join super practical hands-on workshops. And you heard from big guys like Cerebras and OpenAI to small but super interesting startups like OpenPipe. Yesterday the conversation included how AI translates into operating margin and today we'll hear about the capabilities companies are building toward, the work agents can take on and what managing that might involve. Things will be happening here in Shannon room and it will be finance, compute and infrastructure sessions. In Turing room, my favorite name, evaluations, benchmarking, retrieval, self-improving agents and skills. In Saturn room, you will hear about developer tools, enterprise data, software factories, agent permissions and token economics. And McCarthy room finally will be about model costs, coding, agent context, human verification, and banking deployment and financial agent evidence.

</details>

### AI 时代的组织变革与嘉宾登场

**Ksenia Se**: 在 Turing Post，我们投入了大量精力来密切追踪所有这些研究方向与落地动态。同时，我们还开设了一个名为《AI 组织时代》（The Org Age of AI）的系列专题，专门探究当一家企业开始真正接入并使用这项技术时，组织内部到底会发生什么：工作方式是如何被重塑的？以前在实际操作中不可行、而如今变得唾手可得的事情有哪些？以及，为什么在超智能（superintelligence）展现出如此磅礴力量的同时，很多场景下的投资回报率（ROI）却依然若隐若现？

这也正是这场盛会对我而言如此引人入胜的原因所在：在这个会场里，研发底层技术的科学家与工程师，与对具体业务工作有着极其深刻、细致入微理解的从业者齐聚一堂。这两群人之间有着极大的互相学习与启发空间，这令我由衷着迷。

今天的第一位演讲嘉宾，正是在 Ramp 公司立足于这两个世界的交汇点上开展工作。让我们热烈欢迎 Alexander Shvets带来他的主题演讲：《等待前沿突破的同时追求极限能力》（Chasing Capabilities While Waiting for the Frontier）。掌声欢迎！

<details>
<summary>Original English</summary>

**Ksenia Se**: And at Turing Post we spend a lot of time following all these directions and research in these directions. But we also have a series called "The Org Age of AI" where we look at what happens to a company as it begins to work with this technology. How does the work change, right? What becomes possible that wasn't practical before? And why, while superintelligence feels so powerful, why is the ROI still missing? And that's part of what makes this gathering so interesting to me. You have people developing the technology in the same room as people who understand in considerable detail the work it needs to do. And there is a lot of those two groups can learn from each other. That's fascinating to me. And our first speakers work at the intersection of those two worlds at Ramp. So please help me welcome Alexander Shvets with "Chasing Capabilities While Waiting for the Frontier." Thank you.

</details>

### Ramp 的苦涩教训与应用层定位

**Alexander Shvets**: 大家好，我是来自 Ramp 的 Alex。今天我演讲的主题是《等待前沿模型演进的同时追求极限能力》。

首先对我的背景做一个简要介绍：我大约是在三年前加入 Ramp 的，归属于大应用 AI 团队，负责在多个不同场景和产品面上落地大语言模型与机器学习技术，致力于让我们本就出色的产品变得更加卓越。

在展开介绍 Ramp Labs 的具体工作之前，我想先为我的分享做一个铺垫说明：Ramp 是一家极其坚信“苦涩教训”（Bitter Lesson-pilled）并围绕其进行构建的公司。在过去一年中，我们内部使用大语言模型的业务场景数量激增了 123%。与此同时，虽然我们很多核心功能的 Token 消耗总量大幅增长，但从单笔单位经济效益（unit economics）来看，成本实际上反而变得更加低廉。这是因为前沿模型层出不穷，推陈出新的速度极快，这些模型速度更快、性能更好、价格却更加便宜。因此，我们能够以低得多的成本提供完全相同的准确率水平。这是一个非常典型的践行“苦涩教训”的模式。

正因如此，我经常会被问到一个问题：“既然前沿模型一直在降本增效，那为什么不直接坐等更强的模型发布呢？为什么像 Ramp 这样一家身处应用层的公司，还要在内部设立一个专门的应用研究（Applied Research）部门呢？”

<details>
<summary>Original English</summary>

**Alexander Shvets**: Hey everyone, I'm Alex from Ramp. Um, and I'll be speaking about chasing capabilities while waiting for the frontier to advance. So, a quick intro about myself. I joined Ramp around three years ago on the broader applied AI team working on a bunch of different surfaces and products applying LLMs and ML to make a great product even better. Uh to caveat my presentation on Ramp Labs, Ramp is an extremely Bitter Lesson-pilled company. Over the last year, the number of use cases that use LLMs has increased 123%. While at the same time a lot of our top features are growing in token spend, but on a unit economic basis they're actually becoming cheaper because there are frontier models that are being released all the time now and these models are cheaper, faster, and better. And so we're able to provide the same level of accuracy at a much lower cost and so this is a really Bitter Lesson-pilled pattern. And so given all this, a question that I sometimes get: why not just wait? Why have an applied research function inside of a company like Ramp, an application layer company, right?

</details>

### 从 2023 到 2026：智能体工程的演化与挑战

**Alexander Shvets**: 为了回答这个问题，我想带大家对比回顾一下 2023 年的情况。

回到 2023 年，大家手里能用的基本就是 GPT-4。在那个时期构建一个智能体（agent）是一项极其繁琐且工作量巨大的工程：
- 你必须建立非常非常严苛的安全边界和护栏规则（guardrails）；
- 当时的模型并没有经过强化学习（RL）训练来学会回溯（backtrack）；
- 模型没有内置的思考 Token（thinking tokens），一旦思路跑偏走错方向，它就会一路盲目蛮干下去，根本意识不到自己犯了错误；
- 开发者必须对提示词（prompt）字斟句酌、反复推敲，甚至某些同义词的微小变动就会彻底改变智能体的行为表现，因为模型在泛化理解用户意图上缺乏充分的强化学习对齐；
- 你还必须竭尽所能地压缩并精简上下文窗口（context），因为一旦喂给智能体太多的上下文信息，它就会陷入彻底的混乱之中。

然而即便在那种艰难的条件下，我们当年的决定依然是：我们必须把产品发布出去。我们绝不能干等着 GPT-4.5 或者 GPT-5 的问世，我们必须当下就为我们的财务专业人士客户提供价值。因此，尽管道阻且长，我们依然上线了诸如 Ramp Tour Guide 等一系列智能体。

快进到现在 2026 年，构建智能体已经变得容易太多了。模型的能力已经取得了极其巨大的飞跃，你基本上只需要为它们接入 MCP（模型上下文协议）并赋予它们获取各类上下文的权限，面对给定的任务，它们就能极其出色地领会意图并完成交付。

但我依然深信，我们完全有能力往更深处扎根一层，为我们的用户打造出体验更为极致的产品。只不过在今天，这需要付出一些更为精细化的努力。

接下来，我将向大家展示 Ramp Labs 的部分研究成果，通过三个具体的实践案例，阐述我们是如何将应用研究深度融入 Ramp 本身的产品业务之中的。

<details>
<summary>Original English</summary>

**Alexander Shvets**: Um and to answer that I would like to draw a parallel to 2023. Back in 2023, you had access to kind of like GPT-4 and creating an agent was a lot of work. Um you would have to create very very strict guardrails. Models weren't RL'd to backtrack. They didn't have thinking tokens. And so if it went in the wrong direction, it would just kind of charge ahead and not realize that it made mistakes. You had to sweat over all of the prompts where to the point where some synonyms could change the behavior of your agent because they weren't RL'd properly on generalizing to the user's intent. You had to reduce and scope down the context as much as possible because giving too much context to the agent would just confuse it. Um and even back then we decided, well, we need to ship these things. We can't wait for GPT-4.5 or GPT-5 to come out. We need to serve our financial professionals now. And we shipped things like Ramp Tour Guide and many other agents even though it was not the easy thing to do. And fast forward now to 2026, building an agent is a lot easier. The models have gotten so much better that you can kind of give them MCPs and access to kind of any context and they do a very very good job of understanding what they need to do given a task. But I still believe that we can dig a layer down and create even better experiences for our users. It's just it requires a bit more effort now.

</details>

### 案例一：打造垂直专业模型——以 Ramp Sheets 为例

**Alexander Shvets**: 首先从构建专业化模型（specialist model）讲起。

在去年 11 月，我们正式推出了 Ramp Sheets，这是业内非常早期的电子表格智能体（spreadsheet agent）之一。当时那两家前沿实验室（frontier labs）都尚未推出各自版本的电子表格智能体。我们在 11 月的发布取得了非常出色的反响，许多来自顶尖企业的客户注册并深度使用了这款工具。

在此过程中我们意识到，这虽然是一个非常通用的电子表格处理智能体，但在 Ramp 平台上，不仅是我们内部员工，所有客户——那些广大会计和财务专业人士——每天的大部分工作时间其实都是在与电子表格打交道。因此，我们完全可以把 Ramp Sheets 底层的运行框架（harness）和核心智能中枢抽离出来，嵌入到 Ramp 内部的其他各种业务场景与产品界面之中。

然而在逐步构建这一架构的过程中，我们意识到：我们或许可以借助 Ramp Labs 的前沿应用研究，将这一系统的体验打磨得更为卓越。

于是我们坐下来深入审视：现有的模型在处理此类任务时，短板究竟出在哪里？

在当时那个阶段，业界采用的主流模型大致是 Claude 3 Opus 级别的系统。我们发现摩擦最大、体验最差的痛点在于：当用户把大量的复杂电子表格丢进 Ramp Sheets，并要求它构建折现现金流模型（DCF）或者对某种财务场景进行情景建模时，模型首先需要花费大量时间来制订一份规划，随后不得不耗费极长的时间去挨个调研检索它所能接触到的所有工作表，试图对数据的整体架构与分布脉络建立起全局认知。

虽然像 Opus 这样的模型性能十分强劲，但在那种场景下它的运行速度相当缓慢，而且调用思考 Token（thinking tokens）的推理成本也非常昂贵。

正是在这一背景下，我们决定跳出固有框架往后退一步，转而训练一个专门的检索模型（retrieval model）……

<details>
<summary>Original English</summary>

**Alexander Shvets**: So to present us some of our work from Ramp Labs, three specific cases of how we've applied research into Ramp itself, starting with creating a specialist model. So in November of last year we launched Ramp Sheets which was one of the really early spreadsheet agents. Uh this was before the two frontier labs had launched their versions of spreadsheet agents and we had a very good launch in November. A bunch of users from great companies had signed up and started using it. And we realized that well this is a very general purpose spreadsheet handling agent and a lot of the work that people do on Ramp, both inside of the company but also all of our customers, accounting and finance professionals are spending most of their days inside of spreadsheets. So we can kind of take the harness and the brains behind Ramp Sheets and add it into a bunch of other surfaces within Ramp. And as we were building this out, we realized well we can probably apply some research from Ramp Labs to make this even better. And we sat down and we started looking where do models fall short on this. And back then this was like Opus. And the place that had the most friction was when you would drop in a lot of spreadsheets into Ramp Sheets and you would ask it to build a DCF or model some financial scenario. It would spend a lot of time creating a plan at first and then researching all of the sheets that it had access to to try to get a good understanding of and lay of the land. And Opus is a great model, but it was like pretty slow and the thinking tokens are also pretty expensive. And so we took a step back and decided to train a retrieval model or kind of...

</details>

<!-- chunk 2/51 -->

### 模型后训练与协作编排：Qwen 3.5 的金融问答实践

**Speaker A**: 比如构建一个专门的金融问答模型。在这个架构中，我们依然保留这些前沿模型（frontier models）作为整体的编排调度中枢（orchestrators），然后将具体的任务分发交接给这个响应速度快得多的模型，由它来为规划智能体（planning agent）执行具体的金融问答工作。为此，我们与 Prime Intellect 公司展开了深入合作，对一个 350 亿参数（35B）的 Qwen 3.5 模型进行了后训练（post-training）。实际测试结果表明，该模型在具体垂直任务上的准确率甚至超越了当时处于行业最前沿水平的 Claude 3 Opus（4.6 分数线），同时还能以极高的吞吐量和极低的延迟进行推理服务，达到了类似轻量级模型的高速响应水平。也就是说，这是一个推理速度极快、但在特定领域又足够智能的模型，能够与极其聪明的前沿编排模型紧密配合、协同工作。这是我们 Ramp Labs 团队开展的应用研究中，真正推向生产环境（prod）的一个非常成功的模型后训练落地范例。

<details>
<summary>Original English</summary>

**Speaker A**: like a financial question answering model that would while still keeping these frontier models or or as orchestrators would then be handed off to the this much faster model that would do uh financial question answering for that planning agent. And so we partnered with the company Prime Intellect to uh post-train a Quen 3.5 uh 35 billion um model and we actually got above Opus 4.6 which was the frontier back then uh exact task accuracy while also being able to serve it at high coup uh level latencies. So a much faster but just a smart model that could then be used in uh in tandem with the really smart frontier orchestrator. Um and so this was like a very successful uh example of post training that we had actually sent to prod uh as part of our ramp labs effort.

</details>

### KV 缓存黑科技与 Cartridge 离线上下文压缩

**Speaker A**: 我们目前仍在积极探索的第二项重大技术方向，是键值缓存（KV cache）相关的优化技巧，特别是名为 Cartridge（卡带/卡包）的一类极为有趣的技术家族。通过这种技术方案，你能够在离线状态下将大量的上下文信息——甚至是原有容量 20 到 30 倍的庞大上下文——深度压缩到 KV 缓存之中，并在智能体运行时直接加载提供服务。

<details>
<summary>Original English</summary>

**Speaker A**: Uh the second uh big thing that we are actually exploring up to this day is uh KV cache tricks and particularly cartridges are a really interesting um family of techniques where you're able to compress a lot of context up to 20 to 30 times more context into the KV cache offline and serve it for your agent.

</details>

**Speaker A**: 如果将它与前面提到的 Ramp Sheets（财务电子表格智能处理）场景做个对比，就会发现很多业务任务在时间线上是完全具备确定性和可预测性的。举例来说，像月末对账结账（month-end close）这样的业务，在一个月结束之后，次月的第一天，财务专业人员必然会去核对账目并关闭会计账簿。你完全清楚他们需要调取和审查的资料内容，比如总分类账（ledger）、账龄分析报告（aging report）以及一系列相关的凭证与单据文件。如果按照常规做法，你当然可以把这些资料预先作为上下文准备好，但智能体在执行任务时，依然需要通过自主的智能检索（agentically retrieve）去逐步阅读、理解并拼凑出一幅清晰完整的业务全貌。

<details>
<summary>Original English</summary>

**Speaker A**: And so if you compare it to the ramp sheets example for example um there's a lot of tasks that you know are going to happen at some point right like month end close a month finishes and on the first of the next month a financial professional will go and try to reconcile and close their books you know kind of the ledger the aging report and the documents that they will need to be retrieving and so you could prepare them as context but the agent will still need to agentically retrieve and and create a good picture and understanding of them.

</details>

**Speaker A**: 而借助 Cartridge 技术，我们能够将所有的检索、阅读与理解准备工作预先完成压缩，在财务人员于月初第一天正式上班开始工作之前，利用夜间时间离线构建好一个专属的上下文卡带。这样一来，当财务人员打开智能体界面时，智能体对需要处理的账务细节已经了然于胸，能够精确掌握自己的执行步骤，因为所有必要的业务上下文早已提前内置并加载就绪。与模型后训练相比，Cartridge 的技术落地门槛和工程负担要轻得多（much lower lift），因为其采用的自我演练（self-play）机制具有更强的通用性和泛化能力。

<details>
<summary>Original English</summary>

**Speaker A**: With cartridges, we're able to compress all of that work and build one overnight before the the financial professional starts their work on the first of the month. And once they open up the the the agent, it knows exactly what it needs to do because it has all of the the context already uh built in. Cartridges are also a much lower lift than post- training because the way that they do selfplay is kind of a lot more generalizable.

</details>

**Speaker A**: 这类技术需要注意的一个重要前提（caveat）在于：相比于企业私有的模型后训练，头部模型实验室（frontier labs）未来很可能会在探索持续学习（continuous learning）的过程中，将类似的功能直接封装到它们官方的 API 接口中对外发布。不过退一步讲，即便各大模型厂商未来真的把这项能力做成了原生 API，我们也完全持欢迎态度并乐见其成。因为在此过程中，我们在公司内部已经积累了大量宝贵的专有实战经验（tribal knowledge），并深刻摸透了如何最有效地将这些技术与具体业务场景深度融合。因此，即便官方 API 某一天正式发布，我们也能够从第一天起就迅速上手、驾轻就熟地直接应用，抢占业务落地先机。

<details>
<summary>Original English</summary>

**Speaker A**: The caveat with stuff like this is that compared to post- training, this is something that the labs might ship at some point in their APIs in their foray into uh continuous learning. And even if they were to do it in the API, we would actually be happy because we are developing a lot of this tribal knowledge inside of the company um and just learning how best to apply these techniques. So even if it does ship as an API, we can just hit the ground running on day one knowing how to use them.

</details>

### Agentic MapReduce 与 10,000 个并行智能体的全系统渗透测试

**Speaker A**: 最后要介绍的第三个由我们 Ramp Labs 推向生产环境的应用研究范例，是我们围绕智能体 MapReduce（agentic MapReduce）以及智能体集群协同（agentic swarms）所展开的系统性工作。更具体地说，我们在 Ramp Labs 官方技术博客上发布过一篇深度文章，详细阐述了我们如何调动多达 10,000 个并行运行的自主智能体，对 Ramp 的整个系统与业务架构进行全面的安全渗透测试（pentest）。

<details>
<summary>Original English</summary>

**Speaker A**: And finally the third example uh of applied research that we are sending to prod is our work on uh agentic map produce and kind of agentic swarms. So more concretely we published an article on the ramp labs uh blog on how we uh used 10,000 parallel agents to pentest all of ramp.

</details>

**Speaker A**: 在 Ramp 内部，我们构建了一个名为 Ramp Inspect 的云端智能体（cloud agent），它负责处理所有底层的自动化基础设施搭建以及复杂的工程管线配置，为支撑如此庞大且极具野心的集群任务提供技术基石。借助该平台，我们成功并发启动了 10,000 个平行的自主智能体，将测试任务以 Map 阶段的形式切分分发出去，让它们深入系统的各个层面全力探索挖掘潜在的安全漏洞；随后在 Reduce 阶段，同样通过智能体化的方式对初步上报的问题工单进行归纳汇聚与收敛处理。具体流程包括利用大语言模型对上报的所有工单进行自动化语义去重，接着再借助大语言模型以对抗性攻击（adversarial reproduction）的方式尝试复现漏洞，从而百分之百确认这些安全漏洞真实存在且影响重大。

<details>
<summary>Original English</summary>

**Speaker A**: Um, so at RAMP we have a cloud agent called RAMP inspect which helps out with setting up all the infrastructure and plumbing for something as ambitious as this. And we were able to spin up 10,000 parallel agents and then kind of map this work out try to find any vulnerabilities and then also agentically reduce on the tickets that they would create. So dduplicate them with LM and then try to reproduce them adversarily with LMS to try to make sure that the vulnerabilities are real and important.

</details>

**Speaker A**: 整个测试流程执行完毕后，我们最终成功挖掘出了 7 个高危严重级别的安全漏洞，并且团队已经对它们全部完成了修复补丁。非常有意思的是，我们在那篇文章中重点分析的其中一个安全漏洞，是通过电子邮件传入的 Lua 脚本注入风险。在整个技术架构的各个孤立组件中，没有任何单个组件自身存在不安全的配置或漏洞；但这个智能体集群（swarm）却能够将跨多个不同组件的交互逻辑与全链路运行机制端到端地串联拼凑在一起，从全局宏观视角发现了这种复合交互下的潜在风险，从而最终成功捕捉到了这个极为隐蔽的漏洞。

<details>
<summary>Original English</summary>

**Speaker A**: At the end of all of this, we have actually found seven high vulner high severity vulnerabilities that we all patched. Interestingly, one of the um vulnerabilities that we described in that article is a Lewis script injection that you could send over via email and no single component of that stack was unsafe and the kind of swarm had to patch together multiple components and understanding of multiple components end to end in order to be able to figure this out.

</details>

**Speaker A**: 这种方案的另一大显著优势在于：整个渗透测试流程完全是全自动化闭环运行的，不需要耗费任何人工精力与时间成本。作为运维和安全人员，你只需要触发任务启动它；而整个过程中唯一产生的成本损耗，仅仅是那些在筛选和过滤阶段被剔除掉的未通过测试路径所消耗的 Token 算力费用而已。

<details>
<summary>Original English</summary>

**Speaker A**: And the other nice thing with this is that this is all running autom automatically. You don't need to spend anyone's time. is just use started and the only thing that uh failed failed passes that get filtered out is the cost of the tokens.

</details>

### Swarm 经济学：开源权重模型与推理成本极致优化

**Speaker A**: 除了搭建支撑这些超大规模智能体集群运行的底层工程基础设施之外，另一个极其关键的课题在于：我们持续深入研究在智能体集群协作网络中，如何最科学合理地配置和使用不同档次的大语言模型。在我们发表的那篇同一博文中，有一个非常核心且令人振奋的技术洞察：在集群方案中，你完全可以大规模采用开源权重模型（open-weight models），其调用成本相较于前沿的顶级推理模型（frontier reasoning models）便宜多达 5 倍。而由于你构建的是以群体协作运行的智能体集群架构，整体漏洞检测的成功率并没有因为单个模型能力下降而随之出现 5 倍的衰减。因此，你可以把预算倾斜到这些更便宜的模型 Token 上，通过更大规模的并发探索，最终获得几乎与全顶级模型不相上下的高精度漏洞检出效果。

<details>
<summary>Original English</summary>

**Speaker A**: The other thing that's interesting outside of just building out all of the infrastructure to support these swarms is that we do research into how to best use models as part of these swarms. One of the interesting insights from that same article that we published is that you can actually use openweight models that are up to five times cheaper compared to the frontier reasoning. And because you're setting it up as a swarm, the detection rate is not five times lower. So you can kind of spend more on these cheaper tokens and have almost as good of a detection rate.

</details>

### Ramp 的工程哲学与两款商业化产品落地

**Speaker A**: 如果纵观我们前面所列举的所有研发落地案例，你会很自然地发现一个贯穿始终的核心主线模式：它们当中的绝大多数探索，本质上都是在努力实现两大目标——节约时间成本以及节省资金花费。具体映射到技术指标上，就是极致降低推理延迟（以挽回宝贵时间），以及极致削减 Token 消耗开销（以节省真金白银）。而这正是 Ramp 公司的核心品牌口号与创立宗旨——“为我们的客户节约时间和金钱（saving our customers time and money）”。

<details>
<summary>Original English</summary>

**Speaker A**: Um, if you follow through all of these examples, you kind of notice a pattern of a lot of them is attempts at saving on time and saving on money. So, reducing latency, which is time, and then reducing on token cost, which is money. That's actually RAM's uh slogan, saving our customers time and money.

</details>

**Speaker A**: 因此，我想向大家隆重推荐两款由 Ramp 正式对外提供的商业化核心产品，它们的技术架构和功能设计均深深植根并受益于 Ramp Labs 团队的研究成果。第一款是“Token 支出管理平台（Token Spend Management）”。该产品能够直接集成并连接你企业内部所申请调用的众多主流模型 API Key，从而为你提供关于整个企业内部大语言模型实际使用现状的极其详尽、透明的全景图。它不仅仅能在传统的单个 API 密钥或具体使用者维度上对 Token 消耗进行统计与记账，更能下钻到深层的财务会计核算科目（accounting categories），甚至还能通过对 AI 算力与开发支出的深度财务审计与分析，帮助企业依法匹配并申报研发税收抵免优惠（tax credits）。不仅如此，它在数据洞察上更进一步：我们构建了一套精细化的分析分类学体系（taxonomy），能够对企业内部所有大语言模型的实际调用做深度的上下文语义分析与业务意图解析，帮助管理者从真正的业务场景与应用本质去透视 AI 的生产力发挥情况，而不仅仅局限于给内部某个特定部门或个人做流水账式的人头归因。

<details>
<summary>Original English</summary>

**Speaker A**: Um, and so I'd like to to point to two uh products that we actually offer from RAMP that have been um influenced by RAM Labs' research. The first one is token spend management that connects to a bunch of uh your API keys and is able to give you a really good picture of how LM are being used inside of your company. Not only token spend on an API key basis or a user basis but digging deeper accounting categories um and even things like um tax credits that you can get by uh analyzing the spend. It also goes deeper and we create a taxonomy that uh contextually analyzes and semantically analyzes the LM usage so you can actually understand how LMS are being used outside of just attributing it to a team or a person inside of your company.

</details>

**Speaker A**: 第二款产品则是 Ramp Router（智能请求路由网关）。它的设计核心同样聚焦于全方位优化和改善你部署的 AI 智能体的端到端响应延迟。在 Ramp Router 中，我们深度整合并落地了一整套与 Ramp Labs 联合打磨研发的高级路由调度策略，包括融合集成类似英伟达 Switchyard（Nvidia Switchyard）的技术思路、自适应智能灵活负载卸载（smart flex offloading of work）等创新算法，在双向维度上同时兼顾推理响应延迟的压缩与 Token 单元采购成本的大幅下降。目前，平台内已经上线了多种可即开即用的成熟路由策略，后续我们还将持续推出更多更强的前沿路由算法能力。因此，如果大家对这两款产品中的任何一款感兴趣，欢迎拿出手机为屏幕上的 URL 链接拍照保存，或者直接现场扫描屏幕中的二维码了解详情。我稍微停顿一下给大家留几秒钟扫码时间。太棒了。

<details>
<summary>Original English</summary>

**Speaker A**: And then the second one is RAM router which also leans into improving your the latency of your agent where we have a bunch of routing strategies that we work with ramp labs to develop. uh things like Nvidia Switchard, things like smart flex offloading of work to both improve latency and um cost per tokens that you spend. And there's a bunch of different strategies already available for the the for routing and even more coming out later. So, if you're interested in any of these two products, you can take a photo uh of the URLs or or scan the QR codes there. Give you a second. Awesome.

</details>

### Ramp Labs 前沿技术博客与开放研究全景

**Speaker A**: 此外，我也非常真诚地邀请大家访问并关注我们的 Ramp Labs 技术博客。我们在那里公开发布了许多极具技术深度与实践价值的高质量研究长文，受限于今天分享的有限时间，很多精彩工作我未能在本次演讲中一一展开详述。

<details>
<summary>Original English</summary>

**Speaker A**: And then I I'd also invite you to check out our Ramplabs uh blog where we publish um a bunch of really interesting articles that I haven't had the chance to cover as part of this presentation.

</details>

**Speaker A**: 其中特别值得一提的重量级成果之一是代号为 Portal 的前沿项目。在该项目中，我们成功探索出了一种能够将模型后训练（post-train）所沉淀的微调知识直接跨模型进行无损迁移的技术方案。比如，你可以在某个基础基座模型上（例如我刚才详细介绍的 Qwen 3.5 35B 模型）通过 LoRA（低秩自适应）等方式完成高难度的领域后训练；随后，你可以将微调所得的潜在表征知识（latent）顺畅无缝地迁移移植到 Qwen 的全新升级迭代版本中，甚至能够进一步跨越模型架构家族的壁垒，投射投影到截然不同的其他模型系列之上。这种技术本质上是在训练一种高度通用的潜空间表示，能够被自由映射投射到各种目标模型之中，从而极大幅度地均摊和摊销（amortize）了企业在模型定制后训练上所需持续投入的昂贵算力与时间成本。

<details>
<summary>Original English</summary>

**Speaker A**: Um notably one of the really interesting ones is portal where we figured out a way of uh transferring learnings from one post train to another. So you could do something like a Laura uh post train on one model. So like the Quen 3.5 that I was describing, but then transfer it to newer versions of Quen or even across different families. So you're post-raining this latent that then can be projected onto different uh models and that really amortizes the cost that you have to spend on post- training.

</details>

**Speaker A**: 博客上还涵盖了多篇关于智能体 MapReduce（agentic MapReduce）的系列技术博文。除了前面重点谈到的全系统渗透测试与攻防实战之外，还包括一系列其他维度的探索：比如如何对全公司的大语言模型调用轨迹进行深度挖掘与上下文分类体系构建（这部分核心技术已经直接赋能转化进了我们的 Token 支出管理商业化产品）；又比如基于 LLM 的自我进化监控系统（self-improving monitoring）——我们利用大语言模型在 DataDog 监控平台上针对大量核心产品业务界面自动生成全套监控指标和告警规则，随后当生产环境触发实际告警时，模型能够在完全无需人类工程师介入干预（without a person in the loop）的情况下自主优化、修正并迭代这些监控规则与报警策略，从而从系统底层构建起具备极高弹性和极高鲁棒性的超级软件服务架构。

<details>
<summary>Original English</summary>

**Speaker A**: Uh more blog posts on agentic map produce. So, not only the pentesting stuff that we did, but also things like um analyzing and creating texonomies of LM usage, which is stuff that has gone into the token spend product. um things like self-improving monitoring where we use uh LMS to automatically um create monitors with data dog on a lot of our product surfaces and then as alerts come in improve those monitors automatically without a person in in the loop to try to basically create super super robust and resilient software.

</details>

**Speaker A**: 最后一项非常精彩的探索是语义标签化（semantic tagging）。这是将智能体 MapReduce 大规模应用于海量真实用户交互会话记录中的一次极具启发性的技术尝试：在此场景下，系统能够对数以万计的复杂会话日志进行全自动标注并自主构建开放式分类体系（open-ended taxonomies）。这意味着我们无需在任务执行前预先人为假设或硬编码规定 LLM 的使用集群类型与场景分类，而是让多智能体系统在漫游聚类的过程中自主提炼归纳出全新的语义结构，随后再将这些细粒度维度与企业内部真实的财务支出数据进行精确的核对与账目冲抵关联。

<details>
<summary>Original English</summary>

**Speaker A**: Um and finally semantic tagging which is this interesting uh foray into creating this um egentic map reduce over a bunch of user sessions where we can annotate and create texonomies that are open-ended. So not knowing um ahead of time which what are the clusters of LM usage and trying to create a tonomy that can then be reconciled against the spend inside of the companies.

</details>

**Speaker A**: 如果各位对我们在这些方向上的应用研究与工程实践感兴趣，欢迎访问推特/X 官方账号 x.com/ramplabs，在那里您可以随时跟进、查阅并交流我们团队不断产出的最新研究成果与工程洞察。屏幕上同时展示了我的个人 Twitter/X 社交账号，如果您有任何技术疑问，或者希望就应用研究落地过程中的具体业务用例展开更深层次的交流探讨，非常欢迎随时与我联系互动。我的分享就到这里，非常感谢大家的聆听！

<details>
<summary>Original English</summary>

**Speaker A**: So if uh if you're interested in this uh type of research, x.com/ramplabs where you can uh go and and check out more of our research. And uh there's my Twitter if you have any other questions or uh want to talk about some use case as part of your applied research. And that's it. Thank you.

</details>

### 主持人串场：AI 代码生成时代的验证挑战

**Speaker B**: 随着 AI 智能体生成前所未有的大规模代码，我们该如何确保这些代码真正具备上线发布的可行性与安全性？接下来，让我们共同探讨验证机制在当今开发流程中的关键重要性……

<details>
<summary>Original English</summary>

**Speaker B**: As AI agents generate more code than ever, how do we make sure it's ready to ship? To explore the importance of verification in

</details>

<!-- chunk 3/51 -->

### 软件工厂与丰田生产方式的历史启示

**主持人**：……智能体软件开发，有请 Sonar 首席执行官 Tar Shaat。

<details>
<summary>Original English</summary>

**Host**: ...agentic software development, please welcome Tar Shaat, CEO of Sonar.

</details>

**Tar Shocket**：大家早上好。我叫 Tar Shocket，正如刚才介绍的那样，我是 Sonar 的首席执行官。我们今天来到这里，是为了探讨我们一直以来如何帮助企业构建真正适用于企业级环境的软件工厂。我认为从观察现实世界中的实体工厂切入会是一个很有意思的开端，因为我们人类非常清楚该如何建造实体工厂。对于现场那些头发有点花白、经历过那个时代的朋友们来说，你们可能还记得 20 世纪 80 年代。在 20 世纪 80 年代，你其实能找到非常不错的汽车，但如果你看一下屏幕上的这张图片，并且如果你还记得那个年代的话，当时的汽车零部件拼装在一起时并不是那么严丝合缝，对吧？不同的部件拼接处会留下很大的接缝缝隙。那些车本身确实是好车，但就是无法达到应有的契合水准。

<details>
<summary>Original English</summary>

**Tar Shocket**: Morning everybody. Uh my name is Tar Shocket. I am the CEO of Sonar as you just heard. And we're here to talk today about how we have been um helping companies build software factories that actually work for enterprises. And I thought it'd be an interesting way to start to start looking at actual factories because we know how to build actual factories. And for those of you who have a little bit of the gray hair and all of this sort of thing, you may remember the 1980s. And in the 1980s, you could find cars that were really good cars, but if you look at the picture here, and if you remember those times, the cars like didn't quite fit together perfectly, right? You'd have different pieces that would leave big gaps. It would be really good cars that just didn't kind of work the way they were supposed to.

</details>

**Tar Shocket**：随后，丰田、尤其是雷克萨斯推出了一则广告。广告展示了一个非常简单的场景：一颗滚珠轴承沿着车身接缝平稳滚过。这在当时可以说是颠覆性的，因为它向人们证明：你完全可以制造出一辆各部件完美契合的汽车。你不再需要遵循“追求产量、拼命制造、事后返工修复”的陈旧思维模式，而是可以真正建立起一种专注于“一次性交付合格品、彻底杜绝返工、致力于让客户满意”的全新思维方式。

<details>
<summary>Original English</summary>

**Tar Shocket**: And then uh Toyota and particularly Lexus came out with a commercial and it showed something very simple which was a ball bearing running across the seams of this car. And it was kind of revolutionary at the time because it showed that you could actually build a car that fit together perfectly. And instead of building for volume and building and then fixing the old mindset, you could actually have a mindset focused on ship it right on no rework on customer happiness.

</details>

**Tar Shocket**：这绝非单一环节的改变。当时发生的事情是，人们开始从根本上以完全不同的视角来审视工厂。他们开始设计并建造那些专门为了保障质量而工程化设计的工厂。我认为其中有几点核心原则直到今天仍然能够引起强烈的共鸣：第一，把质量置于产量之上；第二，从系统层面修复根本问题，而不仅仅是修补眼前的孤立症状；第三，从一开始就针对可制造性进行设计，而不是分别设计好车轮、设计好雨刮水壶等各个零件，然后盲目指望它们能完美拼装到一起；第四，问题一旦发生就地解决，而不是把问题推卸拖延到流程末端才去处理；第五，充分赋能线上的每一个人，任何一线工人都可以叫停生产线，而不仅仅是老板才有这个权力。

<details>
<summary>Original English</summary>

**Tar Shocket**: And there was not this was not a a single change. What happened was that people really started thinking about the factories differently. They started engineering building factories that were engineered to deliver quality. And there's a number of different pieces that I think still resonate today. The first is you prioritize quality instead of volume. The second is that you fix the system, not just individual symptoms that you see. The third is that you design for something that can be built as opposed to designing the wheels and designing the washer bottles and whatever it is and then hoping it fits together. You solve problems as they occur as opposed to kicking the can down the road and fixing it at the end. And you empower everybody. Anyone could stop the line, not just the boss.

</details>

### 现代软件开发与智能体时代的生产力洪流

**Tar Shocket**：我为什么要提这些呢？实际上是因为现代软件开发完全吸收并践行了所有这些原则。如果你思考一下我们今天是如何构建软件的、什么是大家公认的最佳实践，你会发现许多术语和实践都源自丰田生产方式（TPS）的理念——敏捷开发（Agile）、看板（Kanban）、SRE 领域的错误预算（Error Budgets）、持续集成（CI）。这些理念追根溯源都来自这样一个核心设问：我们如何建造出高效运转的工厂？到目前为止，这套体系在软件开发领域运转得非常成功。

<details>
<summary>Original English</summary>

**Tar Shocket**: Now, why am I talking about this? It's actually because modern software development actually embraced all of these principles. If you think about how we build software today, what is considered best practice, a lot of the terms and the practices came from that idea of a Toyota production system, agile, conbon, error budgets, if you're in the SR world, continuous integration. These ideas all kind of sprung from this notion of how do we build factories that work? And it's worked really well for us in software development so far.

</details>

**Tar Shocket**：但是，正如大家所知，智能体（Agents）正在彻底颠覆游戏规则——如果你不理解这一点，你今天也就不会坐在这里了。随着智能体对格局的重塑，一些奇特且反常的现象开始显现。首先，这是一项上个月刚刚发表的研究报告，探讨的是在软件研发全生命周期中引入异步智能体所带来的影响。我相信在座的很多同行都已经亲眼目睹了这种变化：代码编写行数出现了爆炸式增长，暴增了 2450%；代码提交（Commit）次数也大幅上升。因此在当下，代码的生产制造已经变得轻而易举且极度充裕。顺便提一句，越来越多的人——我相信在场的许多人——都在思考：既然写代码变得如此容易且丰富，我们该如何将其全面自动化？我们该如何构建由智能体驱动的软件工厂来自动化并大规模扩展这一流程？

<details>
<summary>Original English</summary>

**Tar Shocket**: But agents, as we all know, you wouldn't be sitting here if you didn't uh understand that agents are changing the game. And as agents are changing the game, weird things start to happen. Um first of all, this is uh research that was published last month uh what of the effect of implementing asynchronous agents in your development life cycle. And I'm sure many of you have seen this. You have an explosion of the number of lines of code written up 2450%. You have an increase in the number of commits. So the volume code creation is now easy and it is now abundant. And by the way more and more people I'm sure many people in this room are saying okay if it's easy and abundant how do I automate it? How do I build factories agentic software factories that help automate and scale this?

</details>

**Tar Shocket**：就在今天，我们刚刚完成了我们称之为“开发者代码现状”（State of Code Developer）的调研报告。这份报告下个月才会正式对外发布，不过今天在这里先给大家做个小小的提前剧透。在我们访谈的开发者中，目前只有 5% 表示他们正在运行智能体软件工厂；但有 34% 的受访者预计在一年内会正式运行，而在金融服务行业，这一比例更是高达 39%。可见大家都在积极思考究竟该如何切实打造这些下一代软件工厂。

<details>
<summary>Original English</summary>

**Tar Shocket**: And today we just finished our what we call state of uh code developer survey. Um it'll be out next month, but this is a little preview. Today 5% of developers that we spoke to say that they're running Agentic software factories, but 34% said in a year they expect to and 39% in financial services. So people are thinking about how do you actually build these next generation factories.

</details>

### 安全风险与工程化治理新范式

**Tar Shocket**：然而，这其中隐藏着几个不容忽视的陷阱，首当其冲的就是安全风险。智能体在辅助开发构建系统方面表现极为优异，但同样地，它们在辅助入侵攻击、寻找系统漏洞、挖掘质量缺陷等方面也同样得心应手。正是因此，当我在上周末准备这篇演讲内容时——这正好又呼应了丰田生产方式里的准时制（Just In Time）理念——萨提亚·纳德拉（Satya Nadella）在 X 平台上发布了一篇文章。如果你还没读过的话，我认为那是一篇非常精彩、值得所有人深入领会的文章。他在文中探讨了企业内部模型带来的内部风险问题，其中特别强调了一点：我们需要采取一套工程化方法来进行风险遏制与合规治理，这种方法必须围绕着高度确定性的系统设计、人工管控以及可靠的操作规程来构建。

<details>
<summary>Original English</summary>

**Tar Shocket**: And there's a a couple of gotchas in here. security risk. The agents can work really well to help you build stuff. It can also work really well to help you hack stuff, help you attack stuff, find vulnerabilities, find quality issues, etc. And so, as I was writing this um presentation kind of over the weekend, a little just in time again from the Toyota production system, um Sachi Nadella posted this article on X and if you haven't read it, I think it's a great article that I think everyone uh should internalize. But one of the he was talking about insider risk of models inside of companies. And one of the things that he talked about was the need for an engineering approach to containment and governance built around strong deterministic system design, human controls and reliable operating procedures.

</details>

**Tar Shocket**：这番话引发了我强烈的共鸣，因为我们当前目睹的正是软件工厂设计、或者更宽泛地说是软件开发领域的一场深刻范式转移：我们必须通过严密的工程化手段，将确定性的信任度与代码质量深植到智能体软件工厂的架构体系之中。

<details>
<summary>Original English</summary>

**Tar Shocket**: And this really resonated with me because what we are seeing is a paradigm shift in software factory design or software development. let's call it more broadly that we need to engineer we need to build systems that engineer confidence and quality into aentic software factories.

</details>

### 智能体落地的五大核心瓶颈：从“人机协同不可扩展”到“认知屈服”

**Tar Shocket**：为了实现这一目标，我认为首先必须认清我们目前面临的客观局限。那么，这其中最艰巨的挑战究竟在哪里？我将重点阐述五大瓶颈。首先第一点，“人机协同”（Human in the loop）根本无法规模化扩展。这句话在今天的会场里或许不算太有争议，但事实上，几乎每一家我接触过的公司，当我问他们“你们的 AI 治理策略是什么”时，他们会滔滔不绝地罗列一大堆机制，最后总会加上一句“不过您放心，我们有人工在把关控制”。然而，人工介入把关所面临的根本困境正如我前面提到的数据：代码编写行数激增了 2450%，提交次数增加了 240%，但同一项研究表明，最终的产品版本发布量仅仅只增长了 30%。我们根本还没有摸索出如何将前端生产制造的大幅提速顺畅转化为后端安全交付的能力。这中间迫切需要自动化能力，迫切需要全新的配套工具。

<details>
<summary>Original English</summary>

**Tar Shocket**: So to start doing that I think it's important to understand the limitations that we're facing. So what's the hard thing about this? And there's five that I'm going to call out. The first is that human in the loop doesn't scale. And this may be I don't know to this room it may not be all that controversial but every virtually every company I talk to I say what's your AI governance strategy and they give me all this stuff and they say but don't worry we have humans in the loop and the problem with humans in the loop as I mentioned earlier 2450% increase in lines of code 240% increase in commits but the same study showed only a 30% increase in releases we haven't figured out how to scale from producing stuff to shipping stuff. There's automation needed. There's new tools needed.

</details>

**Tar Shocket**：更至关重要的一点在于一个我如今每天都能看到、相信在座很多人也深有体会的现象，那就是所谓的“认知屈服”（Cognitive Surrender）。这项研究就在几个月前刚刚完成，它系统考察了人类在多大频率上会盲从赞同 AI 的结论。结果表明：当 AI 的判断完全正确时，人类有 93% 的概率表示赞同；然而当 AI 的判断完全错误时，人类竟然依然有五分之四（80%）的概率选择盲目认同！对吧？所以问题并不在于“人机协同只是需要做得更快一点”，真实的情况是，在高度自治的智能体时代，单纯依赖人工审核这一模式根本行不通。这就是面临的第一个严峻问题。

<details>
<summary>Original English</summary>

**Tar Shocket**: And really importantly, this is a concept that really I I see it every day now and I'm sure many of you do as well uh called cognitive surrender. Uh and this study was done just a couple months ago and it looked at how often do humans agree with AI. And it turns out they agree with AI when AI is right 93% of the time. And four out of five times they agree with it when the AI is wrong. Right? So it's not that human in the loop is yeah we just need to make things faster. It's actually that it doesn't work in the agentic era. So that's problem one.

</details>

### 代码库规模复杂性与多步骤错误复合效应

**Tar Shocket**：第二个核心问题在于，智能体在面对大型复杂的代码库时表现得非常吃力。它们本身固然极其聪明，但要在代码库上顺利开展工作，必须深入理解代码库内部的全局脉络与依赖关系。左手边展示的是一项关于代码翻译与迁移的研究，它明确显示：当代码库规模在 10,000 行代码时，智能体能够达到 91% 的正确率；然而当规模扩大到仅仅 50,000 行代码时——我相信在座各位所维护的代码库体量都远超这个数字——智能体的翻译准确率直接发生了雪崩式的暴跌。

<details>
<summary>Original English</summary>

**Tar Shocket**: Problem two is that agents struggle with large complex code bases. They are very very smart but you need to understand what happens in a codebase in order to work on it. The left hand side is a study that was done on code translation and what it shows is that the agents were able to get it right 91% of the time when the code base was 10,000 lines of code and by the time it got to even 50,000 and I'm sure everyone in this room operates off of much bigger code bases than this but when it was trying to translate 50,000 the accuracy collapsed.

</details>

**Tar Shocket**：与此类似，另一项研究考察了在大型复杂代码库中完成同一项特定任务究竟需要消耗多少 Token，结果发现不同情况下的 Token 消耗差异高达 30 倍——不是相差 30%，而是整整 30 倍！究其原因，是因为智能体为了弄清如何理清代码脉络、理解整体架构体系等基础信息，不得不耗费海量的 Token。这就好比我打算从洛杉矶前往此地，如果我随意挑选一个初始起点：假如我碰巧选在了怀特普莱恩斯（White Plains），那我很快就能顺利抵达纽约；但如果我选在了阿尔伯克基（Albuquerque），那我就得消耗漫长的时间和极高昂的成本。智能体在探索复杂代码库时正是完全同理的遭遇。

<details>
<summary>Original English</summary>

**Tar Shocket**: Similarly, another study looked at um how many tokens does it take on a large complex codebase to complete the same task and the variance was 30x not 30% but 30x and the reason is because the agent spends a huge amount of their tokens trying to understand how to navigate the codebase, the structure of the codebase, things like this. And it's kind of like if I'm trying to go from uh from LA to here and if I pick a random starting point. If I happen to pick white planes, I will get to New York pretty quickly. If I pick Albuquerque, it's going to take me a long time and a lot of cost. Same thing happens with agents.

</details>

**Tar Shocket**：第三个关键概念是“错误复合效应”（Errors Compound）。这是来自 Meter 机构的一项研究成果，大家也可以在他们的官方网站上查阅到。他们评估了智能体在完成人类可胜任任务时的实际效能，其评测维度是：智能体能否顺利完成一项需要人类耗时 X 小时的工作。正如大家在这里看到的，他们发布的最新版本 Claude Mythos 预览版，能够很好地胜任人类通常需要花费 16 个小时才能完成的任务。从表面看这确实非常厉害，但细则注释中却包含着一个至关重要的限制条件：这一表现是在基准准确率仅为 50% 的前提下达成的。当你把准确率要求调高到 80% 时，成功率曲线就会出现大幅度的扁平化滑坡。因为随着执行长周期任务，步骤越多，微小的差错就会层层复合成倍放大。如果单个执行步骤的准确率是 95%，那么执行到第 20 个步骤时，整体端到端的准确率就只剩下 36% 了。对吧？所以……

<details>
<summary>Original English</summary>

**Tar Shocket**: Errors compound. This is another important concept. This is a study out of Meter and Meter looks at and you can find this on their website. They look at how effective are agents at completing tasks that humans can do. And the way they look at this is can you complete a task that takes X number of hours. So you can see here the Cloud Mythos uh preview which is the latest version that they've published was good at completing tasks that take a human 16 hours. Okay, so that's really good. But there's an important caveat in the fine print here which is this is at 50% accuracy. When you add it when you dial up the accuracy to 80% it the curve flattens substantially because as you do longunning tasks errors compound. If you have 95% accuracy on each task by the time you're at 20 steps you have 3 36% accuracy. Right? And so

</details>

<!-- chunk 4/51 -->

### 大语言模型作为评估裁判的不可靠性与防范机制

**Speaker A**: 这是我们在软件工厂中必须应对的另一个问题。在这里，我提出的可能最具冲击力的标题观点就是第四点：大语言模型（LLM）其实是不可靠的追求奖励型裁判。大家总是会问我们这样一个问题：“难道你们不能直接去问大语言模型吗？”事实上，人们也一直在对此进行研究。左侧展示的内容全部来自于 PayPal AI 的研究实验室。他们实际上在当月刚发表了一篇论文，研究发现，根据不同的模型以及具体应用场景，在他们所谓的“完全相同复现”实验中，有 7% 到 17% 的判定结论会发生改变。也就是说，询问同一个问题，有 7% 到 17% 的概率会得到完全不同的答案。

<details>
<summary>Original English</summary>

**Speaker A**: That is another issue we have to deal with in software factories. Probably the most aggressive headline I put in here is this fourth point: that LLMs are unreliable reward-seeking judges. You know, so the question that we always get is, "Well, can't you just ask an LLM?" And so people have been studying this as well, and this is all, again, the first on the left-hand side is from PayPal AI's research lab. They published a paper this month, actually, and found that, depending on the model and the situation, between 7 and 17% of verdicts change across what they called identical replications. Asked the same question, got a different answer between 7 and 17% of the time.

</details>

**Speaker A**: 如果你开始对它提出质疑——这是 Meta 最新发布的一项研究——如果你开始质疑大语言模型：“你确定吗？”，只是这样一个非常简单的质问，它实际上就会改变主意，改变的概率在 7% 到 34% 之间，同样取决于具体的模型。因此，当你去询问 AI 裁判两次时，你很可能会得到不同的答案。最后一点，我不想在此过多赘述，因为我认为这对大家来说大概是不言而喻的：随着漏洞利用时间窗口逼近于零，我们做出响应的能力面临着极其严峻的挑战。因此，我们认为软件工厂必须将防范机制从一开始就植入到设计之中，必须通过工程手段直接构建到工厂体系内部。

<details>
<summary>Original English</summary>

**Speaker A**: And if you start challenging—this is a study out of Meta now—if you start challenging the LLM, "Are you sure?", very simple challenge, it'll actually change its mind 7 to 34%, again depending on the model. So, you ask the AI judge twice and you may get a different answer. And then lastly, and I won't dig into this one too much because I think it's probably self-evident to everyone: as the time to exploit nears zero, the ability for us to respond is incredibly challenged. And so, prevention is something that we believe the software factory has to bake in to the design, has to engineer into the factory.

</details>

### 代码置信度公式：意图、引导轨、验证与证据

**Speaker A**: 因此，在深入思考这一问题的过程中，我们总结并写下了所谓的“代码置信度公式”。从根本上说，这就是你该如何构建、如何构想一个能够交付大家共同期望的软件工厂，即交付能够让我们充满信心的成果。不是盲目的信任，不是毫无依据的信赖，而是让我们感到踏实自在的成果，让我们能够坦然面对高管、客户、股东、CEO 以及董事会，并明确告诉他们：“是的，我相信这座软件工厂运转得非常出色。”

<details>
<summary>Original English</summary>

**Speaker A**: So as we've thought through this, we have written down what we call the code confidence formula, which is basically how do you build, how do you think about a software factory that delivers what we all want, which is outcomes that we can feel confident in, right? Not outcomes that we can trust, not blind trust or anything like that, but outcomes that we can feel comfortable with, that we can sit and tell our executives, our customers, our shareholders, our CEOs, our boards that yes, I believe this factory is working well.

</details>

**Speaker A**: 我们认为这其中包含四个关键组成部分。第一是极其明确地厘清意图。如果你不知道自己试图构建什么，你就无法告诉智能体（Agent）该构建什么，最终也就无法获得你期望的结果。第二是引导轨（Guide rails）。我们在这里非常明确地强调是“引导轨”而非“防护栏”（Guardrails）。防护栏的作用是防止车辆冲出道路；而引导轨的作用则是帮助你保持行驶在正轨之上。我认为智能体所需要的正是这种细微的推动与提醒，以此来引导和治理这些智能体。

<details>
<summary>Original English</summary>

**Speaker A**: And we think there's four components to this. The first is being crystal clear about the intent. If you don't know what you're trying to build, you can't tell the agent what to build and you will not get the outcome you want. The second is guide rails. And we very specifically talk about guide rails, not guardrails. Guardrails prevent something from going off the road. Guide rails help keep you on it. And I think what agents need are the small nudges to guide and govern those agents.

</details>

**Speaker A**: 第三部分是验证。验证必须具备独立性、彻底性，并且能够切实解决问题，而不是将麻烦继续往下推拖。最后一部分是证据。也就是“信任但要验证”，信任但必须明白这是建立在证据基础之上的，并且这种证明必须具备一致性、可审计性和可重复性。我们将这些要素相乘，因为我们在许多场景中都观察到，一旦缺少了其中任何一个要素，如果该要素为零，整体的置信度就会直接归零。即便你把其他环节都做到了极致，但唯独缺乏证据支撑，置信度同样会降为零，你对最终成果将毫无信心可言。因此，我们始终认为工厂的设计必须严格具备这四个核心要素。

<details>
<summary>Original English</summary>

**Speaker A**: The third part is verification. That needs to be independent, thorough, and issues fixed as opposed to just cans kicked down the road. And then lastly, evidence. Trust but verify. Trust but understand that it was done with proof that is consistent, auditable, and repeatable. And we multiply these together because we've seen a number of situations where one of these elements is missing. And if it's zero, the confidence goes to zero. If you do all of this but don't have evidence, you go to zero. You don't have confidence in the outcome. So, we really think about factory design as requiring these four elements.

</details>

### 构建软件工厂的实证成果与 Sonar 产品实践

**Speaker A**: 在我们协助客户与合作伙伴构建这些软件工厂时，我不会逐一去讲这一页上的每一个框图，但我们非常严谨地关注如何确立意图——就像左下角紫色框所示，如何设置引导轨，如何以彻底且独立的方式执行验证，以及如何生成证据。通过践行这一理念，我们看到了令人惊叹的实际成效。这些都是来自我们客户的真实数据结果。

<details>
<summary>Original English</summary>

**Speaker A**: And as we put together factories, as we help customers, I'm not going to walk through every box on this page, but as we help our customers and partners build these software factories, we're very deliberate about how do you get the intent (the bottom left-hand side in purple), how do you put the guide rails in place, how do you do verification in a way that's thorough and independent, and how do you produce the evidence? And by doing this, we see amazing results. So these are real results now from our customers.

</details>

**Speaker A**: 首先是聚焦于意图和引导轨。我们有一款名为 Sonar Vortex 的产品，它提供意图引导轨，并在智能体闭环中开始进行验证，持续对智能体进行引导纠偏。我们发现，当在大型复杂代码库中为执行长期运行任务的智能体提供此类信息时，Token 成本能够显著降低 36%，因为你为它指明了清晰开阔的路径，直接将它引导到接近答案的位置，帮助它理解全局路径图，从而避免在已知的事实上白白浪费 Token；同时，代码提交中的缺陷数量减少了 92%。因此，这不仅降低了成本，还能交付更优质的代码产出进入后续的验证阶段。这一切再次印证了通过持续提醒引导让智能体保持在正确轨道上的重要性。

<details>
<summary>Original English</summary>

**Speaker A**: The first one is focusing on intent and guide rails. We have a product called Sonar Vortex which gives intent guide rails and in the agentic loop starts to do verifications again nudging the agent. And what we see when we provide agents in large complex codebases with long-running tasks with this information is a 36% reduction in token cost because you're putting it in white plains. You actually are putting it close to the answer. You're helping it understand the map. We don't have to burn tokens on things we already know. And 92% reduction in issues in the commit, right? So it's cheaper and we can get a better outcome to go into that verification stage. This is again all because we're nudging the agent to keep on track.

</details>

**Speaker A**: 接下来进入验证环节。我们最初就是作为一家代码验证公司起步的，这就是我们看待世界的方式——通过验证的视角。我们坚定地认为，独立验证必须全面覆盖各类问题，并且兼具高精度与成本效益。在能使用 CPU 的地方就用 CPU，在需要 GPU 的时候才用 GPU。因此，我们将确定性的混合方法与智能体驱动的混合方法结合在一起，打造出我们认为代表验证领域黄金标准的技术方案。

<details>
<summary>Original English</summary>

**Speaker A**: Then you get to verification and we started life as a verification company. This is how we see the world, is through a verification lens. And we have a very strong point of view that independent verification has to cover the full range of issues that is both precise and cost-effective, right? Use CPUs when you can use CPUs, need GPUs when you need GPUs. So we look at deterministic mixture of methods and then you add in agentic mixture of methods and it comes up with what we think is the gold standard of verification.

</details>

**Speaker A**: 当你将这些付诸实践时，我们的产品就是 SonarQube。我们近期与超过一千家客户进行了交流，询问他们在实际编码过程中遇到这些问题的频率，调研陈述具体是这样表述的：“SonarQube 用户比非用户更有可能看到非常积极的效果”。具体数据显示：如果拥有黄金标准的验证机制，用户认为 AI 辅助编程对代码安全产生了极积极影响的可能性高出 81%；在上市周期（Time to Market）方面感受到积极影响的可能性高出 34%；在系统宕机发生频率上看到改善的可能性高出 76%。

<details>
<summary>Original English</summary>

**Speaker A**: And what we see is when you apply this, our product is called SonarQube. So we talked to our customers, over a thousand customers recently, and we said, "How likely are you or how often have you seen these issues from a coding?" And the statement to read here is: SonarQube users are X% more likely than non-users to have seen a very positive impact. So 81% more likely to believe that AI coding has had a very positive impact on code security if you have that gold standard verification, 34% more likely to have seen an impact on time to market, 76% on outage frequency.

</details>

**Speaker A**: 因此，再次回到“我们如何建立交付信心”这个核心议题上，我们所看到的结论是：如果你把这些环节有机组合在一起，将验证能力扎扎实实地构建为软件工厂中的一等公民，你就能够切实建立起交付信心，并收获看得见的成效：更高的安全性、对交付周期的更强信心、宕机事件的减少，以及系统可靠性的全面提升。

<details>
<summary>Original English</summary>

**Speaker A**: So again as I come back to how do we have confidence to ship, what we're seeing is that if you put these pieces together and you build verification incredibly strongly as a first-class citizen in the factory, you are actually building confidence and you're seeing results. Better security, more confident in our time to market, a reduction in number of outages, improved reliability.

</details>

**Speaker A**: 当然，正如我之前提到的，做到这一切必须依托于确凿的证据。务必确保代码通过了质量门禁（Quality Gate）。确保满足各项规范要求——屏幕上列出了大量的缩写词，无论你需要通过哪一项，无论是指你们内部控制与运营中的通用 IT 控制规范（IT General Controls），还是针对汽车软件开发的 MISRA 规范，亦或是上面列出的其他任何合规准则。产生确凿的证据，才是让你晚上能睡个安稳觉的关键保障，也是赋予你底气持续向前推进的根基所在。

<details>
<summary>Original English</summary>

**Speaker A**: And of course, as I mentioned, you have to do this with evidence. Make sure you pass the quality gate. Make sure whatever—there's lots of acronyms up here, whichever ones you need to pass, whether that is your IT general controls inside of your internal controls and operations, whether that's MISRA if you're building cars, or any of the other ones that are on here. Producing the evidence is what lets you sleep at night. It's what gives you confidence that you can move forward.

</details>

### 演讲交接：代码充裕时代的置信度交付与政策驱动工作流

**Speaker A**: 这在本质上代表了我们对未来挑战的思考：代码本身是充裕的，而置信度却是极其稀缺的。我们所追求的目标，也是我们认为每个人在展望软件开发未来时都应树立的目标，就是如何交付这种置信度，未来的软件工厂必须具备交付置信度的能力。说到这里，我想向大家表示衷心的感谢。我们在展区设有一个大型展位，就是顺着那边走过去的一个大红色的展位。非常期待能够与大家展开更深入的交流。非常感谢大家，祝大家上午过得愉快！

<details>
<summary>Original English</summary>

**Speaker A**: So that in essence is how we think about the challenge of the future: that code is abundant, that confidence is scarce. And really the goal that we have, and that we think that everyone should have as we think about the future of software development, is how do we deliver confidence, and the factories of the future need to be able to deliver confidence. So with that, I want to say thank you to everybody. We have a big booth—it's a big red booth on the floor right over that way—and would love to talk to you more about all of this. Thank you very much. Have a great morning.

</details>

**Host**: 在哪些环节应当由 AI 智能体主导控制，又在哪些时刻应当始终由人类掌控主导权？为了探讨在基于政策驱动的工作流中如何实现这种权衡平衡，让我们掌声欢迎 Coinbase 的工程经理 Evan Cormos！

<details>
<summary>Original English</summary>

**Host**: Where should AI agents take control and when should humans stay in charge? Here to explore that balance in policy-driven workflows, please welcome Evan Cormos, engineering manager at Coinbase.

</details>

**Evan Cormos**: 大家好，我叫 Evan Cormos。在过去的 20 年里，我一直从事软件的设计、构建与交付工作，其中最近的 15 年都专注于企业级金融服务领域。目前我在 Coinbase 担任“球员兼教练”（Player-coach）类型的工程管理角色。今天我们来到这里，要探讨的主题是：在策略驱动的工作流中如何建立对智能体的信任。

<details>
<summary>Original English</summary>

**Evan Cormos**: Hi everyone, my name is Evan Cormos. I've been delivering, designing, building software for 20 years, the last 15 in enterprise financial services. I am a player-coach at Coinbase. And we're here today to talk about trusting agents and policy-driven workflows.

</details>

**Evan Cormos**: 那么，让我们首先从策略（Policy）切入，这部分可能会显得有些枯燥。我先看一眼这边的发言笔记。我们的出发点始终围绕着策略本身展开。策略为整个组织内部如何开展工作制定了基本规则，其中尤其涵盖了风险管控与合规要求。你可以把策略理解为机构最原始的制度意图，或者等同于最初始的系统提示词（System prompt）。因此，最理想的情况是我们能够将策略书面化地记录下来。这内容可能略显枯燥，请大家耐着性子听我讲完。

<details>
<summary>Original English</summary>

**Evan Cormos**: So let's start with the policy, and it's pretty boring. I'm going to go over here for my notes. So our starting point centers around the policy, and this sets the rules for how work gets done within the organization, including especially risk and compliance. Think of policy as the original institutional intent or the original system prompt. So ideally we have this written down. It's a little bit boring, so stick with me.

</details>

**Evan Cormos**: 策略通常采用诸如“必须”（Must）、“可以”（May）以及“应当”（Should）这类规范性用词。这些词汇再次帮助我们界定了系统在组织内部运行所遵循的规则与决策边界。与策略相分离的，是我们实际运行着的系统。因此我们要做的第一件事，就是在时间维度上将这两个状态进行拆分——即明确区分构建态（Build state）与运行态（Run state）这两个不同的时间阶段。通常情况下，我们要么是在定义策略，要么是在修改调整策略；然而系统本身却是在永不停歇地持续运行，它时刻都在动态流转并发生着改变。因此，我们接下来可以设想一个编译事件……哎呀，抱歉。

<details>
<summary>Original English</summary>

**Evan Cormos**: Using language like "must", "may", and "should". And these again help define the rules and decisions about how the system operates in the organization. Separate from policy, we have the actual running system. So the first thing we're going to do is separate these two, both the build state and the run state, at two different moments in time. So typically we're either defining or changing our policy, but the system is constantly running and it's constantly moving and changing. So we could then sort of imagine a compilation event that... oop, sorry.

</details>

<!-- chunk 5/51 -->

### 人员、流程与技术的交叉点：Agent 在企业中的角色定位

**演讲者**：我先往后跳一下，因为这部分一直在不断变动。随着这些以产品驱动的变化，技术也在飞速演进。虽然一切预期仍然大致受制于既定策略，但归根结底，我们是将策略与运行状态（run state）和构建状态（build state）分离开来的。那么在系统内部，它到底是什么样子的呢？如果今天在座的有来自企业界的朋友，应该对这个模型很熟悉：人员（People）、流程（Process）和技术（Technology）。但 Agent 到底应该如何融入这个经典框架中呢？

<details>
<summary>Original English</summary>

**Speaker**: I'm skipping ahead it's constantly changing. So it it's evolving quickly with these product driven changes. So everything is expected to still be roughly bound by the policy but ultimately um we separate this from the run state and the build state. So inside the system what does it look like? We have a familiar model if we have any enterprise uh folks in the in the room here. Um people process and technology but where really do agents fit into this mold.

</details>

**演讲者**：在我看来，它们是一种横跨这三者的运营模式。它们与人协同工作，自身执行流程中的部分环节，同时既使用技术，本身也由技术构建而成。因此，在今天的演讲中，我们将把重点放在“Agent 与流程的交汇点”：我们给它们分配什么样的工作、设立什么样的边界，以及如何对它们的输出建立信任。

<details>
<summary>Original English</summary>

**Speaker**: So I see them as an operational model cutting across all three. They work with people, execute parts of the process themselves, and they use and are made up of technology. So for our talk today, we're going to be focusing here where agents meet process, what work we give them, what boundaries we set, and how we build trust in their outputs.

</details>

### 工作流重塑：从串行管控到 DAG 并行协作

**演讲者**：接下来让我们深入探讨大家的工作流。虽然这处于较高抽象层面，看起来也很基础，但如果你之前还没做过梳理，现在有非常充分的理由去把它清晰绘制出来。比如，一项变更在正式上线前必须经过审批，或者一位客户在开户前必须完成身份验证。在传统认知中，我们通常预期工作按照特定且设有门禁关卡（gated）的方向单向流动。

<details>
<summary>Original English</summary>

**Speaker**: So let's dive into your workflow. And it's high level and seems basic, but if you haven't, there are good reasons to map this out. So maybe a change has to be approved before it goes live or a customer goes through has to go through verification before their account is opened. We expect work to flow in a specific and gated direction.

</details>

**演讲者**：但我认为，正是 Agent 的出现，使得我们值得重新审视哪些环节其实可以并行推进。过去，由于某些工作的协调成本过高或逻辑过于复杂，以至于无法采用这种并行方式来进行组织。然而现在，我们完全可以在保留必要合规检查的前提下，并行运行多个独立的审查环节，最后再将结果汇总整合起来。

<details>
<summary>Original English</summary>

**Speaker**: So I believe it makes it agents make it worth revisiting what we can do in parallel. So previously some work used to cost too much or be too complex to coordinate in this way. But now we can run independent reviews alongside each other bring the results together but keep the required checks in place.

</details>

**演讲者**：这就是有向无环图（Directed Acyclic Graph，即 DAG）。DAG 是一种用来表示工作流或业务流程的有效方式，它清晰定义了一个只向前推进、绝不自身回环的流程中的各个步骤以及前后依赖关系。如果你熟悉 Apache Airflow 的话，它就是用 Python 代码将工作流及其依赖关系表示为 DAG 的典型开源软件范例。

<details>
<summary>Original English</summary>

**Speaker**: So this is a directed as cyclic graph or a DAG is a way to represent this workflow or process the steps the dependencies for a flow that moves forward without looping back on itself. Apache Airflow, if you're familiar, is an example of open source software that represents workflows, their dependencies as DAGs in Python code.

</details>

**演讲者**：我们可以利用这些 Python 代码和 DAG 来定义并管理许多受策略驱动的业务流程，比如商业贷款审批；或者如果你对此感兴趣的话，也可以用 DAG 来表示在特定地区交易所上线代币的合规流程；再或者，我们也可以用 DAG 来表示受监管的软件交付流程——这是一个非常热门的话题，我们稍后也会花点时间深入展开。我们在软件交付领域已经看到了 Agent 的广泛落地，而我们最终的目标正是要在企业的其他业务领域中复用同样的效率与规模优势，从而弥合这一技术落地的鸿沟。

<details>
<summary>Original English</summary>

**Speaker**: So this Python code this these DAGs can be used to define and manage a number of policydriven processes like for example commercial lending. We could also use a DAG to represent the workflow to list a token on the exchange in a specific region if you're into that. or we could use a DAG to represent a regulated flow of delivering software which is a hot topic and one we'll spend a little bit of time on. I think that we've seen a lot of adoption within agents within software delivery and ultimately we're looking to leverage that same efficiency and scale in other areas of the business and close that the the adoption gap.

</details>

### 节点内部机制：DCG 循环与异常流处理

**演讲者**：让我们暂时继续以软件交付为例。在流程中的某一个具体节点内部，究竟在发生什么？我给大家一个提示：它是一个循环。虽然这么说有些过度简化，但我们可以来看一个节点内部运作的基础版本，假设这是一个代码审查节点：我们实质上会执行一系列步骤，一旦我们确认这项工作足够好（good enough），就会放行让它流转到下一步，这本质上就是代码审查节点的功能。

<details>
<summary>Original English</summary>

**Speaker**: So let's stick with the software delivery example for a little bit. What happens inside one of these nodes of the process? And I'll give you a hint. It's a loop. Um oversimplified, but we have a basic version of what's happening within the let's let's say this is a code review process, right? So we're going to essentially do a number of steps and essentially once we realize the work we recognize that the work is good enough we're going to allow it to pass on to the next step and that's essentially the function of the code review node.

</details>

**演讲者**：但工作成果并非总能一次性顺利通过。因此有时候我们必须吸收代码审查给出的反馈并进行持续迭代，直到成果达到合格标准才能放行。这就是有向有环图（Directed Cyclic Graph，即 DCG）的表现形式。在开源软件方面，诸如 LangChain 或 LangGraph 就是我认为非常适合用来管理 DCG 内部状态的工具。当然，这仍然是一种高度简化的表述，实际中的图结构往往极为复杂。

<details>
<summary>Original English</summary>

**Speaker**: The work doesn't always uh end up okay. So sometimes we have to take the feedback from the code review and iterate on it um until the work is good enough to pass. So this is a representation of a directed cyclic graph or DCG. So as far as open source software uh something like lang chain lang graph would be what I would um say is helpful to manage the state of DCGS. Um and this is an oversimpl over oversimplification. These graphs can be very complex.

</details>

**演讲者**：现在把视野重新拉远：在节点的内部流中，有人类和 Agent 协同工作；而在外部流上，我们则设定了策略边界。但现实中并非所有事情都会按计划推进，所以我们必须处理异常流程（exception flows）。我们既不希望任务卡死在那里，也不可能针对每一种边缘情况都做穷尽式的前期设计。异常流程会持续监控并发现异常状况，比如当你交付的代码被取消或者未能达到安全合规标准时，这些正是你必须第一时间掌握的情况。

<details>
<summary>Original English</summary>

**Speaker**: So zooming back out the inner flow um of the node we have people and agents working together. on the outer flow we have a policy boundary but not everything goes to plan. Um so we have to handle exception flows. We don't want the work to get stuff stuck and we don't want to design for every edge case either. Um the exception flows will monitor and see kind of what happens if you're shipping code that gets cancelled or doesn't meet security standards. That's something you should want to know about.

</details>

### 吞吐量转移与运营可观测性

**演讲者**：一旦我们将 Agent 引入整个流程，工作负荷的吞吐量就会在流程链路各处发生转移。我们在软件交付过程中已经目睹了这种现象，随着我们将 Agent 引入其他业务流程，同样的情况也会发生：突然之间，如果你的代码审查速度大幅提升了，紧接着你就需要以更快的速度完成方案设计，或者以更高的效率执行安全扫描。于是，整个流程中的吞吐量瓶颈开始发生迁移。

<details>
<summary>Original English</summary>

**Speaker**: volume shifts across the flow once we start to add agents into the mix. And we've seen this with software delivery and we'll see it in other processes as we bring agents into those processes as well where now all of a sudden if you're reviewing code faster, you need to design it quicker or you need to do the security scan that's uh faster. So we see the volume shift across the flow.

</details>

**演讲者**：正因如此，从指标度量的角度对整个流程具备端到端的可观测性变得至关重要。因为当我们开始对流程进行加速、并行化并大幅提升整体效率时，系统中往往会滋生出越来越多的新瓶颈。因此，流程层面的运营可观测性极其关键，其重要性远超过你最初编写和构建工作流工具本身。我们需要将整个流程可视化，从而在牢牢守住管控底线的前提下，精准释放出并行处理的产能，这正是我们扩充额外吞吐能力的切入点。

<details>
<summary>Original English</summary>

**Speaker**: And this is where it's really important that we have visibility into the process overall from a a metric standpoint because as we start to supercharge and and parallelize and add more efficiency to the process, we start to develop more and more bottlenecks. And so the operational visibility of the process is extremely important, much more important than the authoring and the building of your workflow tool. Um, so we want to visualize the process. So we want to add parallel capacity by still keeping the controls. And so this is where we'll add more additional capacity.

</details>

### 输入质量与循环门禁：评估机制的核心地位

**演讲者**：好的，我们现在明确了基本模式：执行某项工作、进行检查评估、利用反馈进一步优化，直到成果达到合格标准并进入下一阶段。但为什么说做好这一点非常困难呢？表面上看这似乎轻而易举，但正如我刚才所提到的，这些图在工程实践中会变得极其复杂。接下来我们将更深入地拆解其中的难点所在。

<details>
<summary>Original English</summary>

**Speaker**: Okay. So we're doing some work. We're checking it. We're using the feedback again to refine it until the work is good enough to move on. But why is that hard? That seems like a pretty easy thing to do. But as I mentioned before, these graphs get actually pretty complex. Um, and we'll dive a little bit more into why this is difficult.

</details>

**演讲者**：如果你熟悉 AI 工程实践，就会知道核心挑战之一在于输入和输出的双重多变性（variability）。我始终坚信，更高质量的输入能够以更低的计算成本产生更优的输出。但到底什么才算高质量的输入？通常我们会将其泛指为上下文（context）与模型配置。我们或许可以对此展开细致推敲，但那并不是我们今天的核心议题，今天我们将更加聚焦于输出层面。不过，如果不谈输入的质量，我们实际上也无法脱离上下文来孤立地探讨输出质量。

<details>
<summary>Original English</summary>

**Speaker**: And if you're familiar, one challenge with AI engineering is the variability of inputs and outputs. And I believe that higher quality inputs will result in better outputs at a lower compute cost. But what are quality inputs? So we we'll generally speak to it as context um model. Maybe we can nitpick that. But um this isn't our area of focus today. Um we're going to focus more on outputs. But we can't really talk about quality of outputs without the quality of without talking about the quality of inputs.

</details>

**演讲者**：在理想情况下，我们已经为 Agent 建立了值得信赖的上下文环境——业内对此已有不少参考实践。而在当前这种架构模型下，我们能做的一项关键工作，就是将整体 DAG 的当前状态注入到具体的 Agent 节点中，让它清楚地知晓自己当前处于整个大全局的哪一步。这样一来，当我们进一步引入跨越更长周期的宏观目标时，就会更加凸显对这个迭代循环的成本与执行效率进行优化的紧迫性。

<details>
<summary>Original English</summary>

**Speaker**: So ideally we've established a trusted context for our agent. Um and there's some references on that. But one thing we can do in this model is inject the DAG state into our agent and let it know kind of where it fits into the bigger picture. Okay. So now we've added even long time horizon goals and that's emphasizes the need to optimize the cost and efficiency of this loop.

</details>

**演讲者**：检查环节（the check）正是我们决断成果是否足够好并准予继续推进的核心卡点。我们必须明确定义什么是所谓的“好”，而这恰恰是整个链路中最棘手的部分，同时我们还必须拥有一套可靠的评测手段。否则，单纯增加循环迭代的次数并不必然带来更好的结果。事实上，整个循环的可信度上限完全取决于检查环节的可信度。因此，如果我们想认真探讨质量，就必须深入讨论检查机制本身的可靠性。

<details>
<summary>Original English</summary>

**Speaker**: The check is where we decide whether the work is good enough to move forward. We need to define what good looks like. That's the hard part. and we need to have a reliable way to evaluate it. Otherwise, more passes don't necessarily uh mean better results. The loop is really only as trustworthy as the check. So, if we want to talk about quality, let's talk about the check and let's talk about quality. Okay.

</details>

### 从确定性测试到概率性评估：构建双重置信机制

**演讲者**：我认为，利用 AI 进行系统构建为全面提升产品质量提供了绝佳契机。我非常认同近期关于“耐用软件”（durable software）的一些深入探讨。我本人是质量的坚决拥护者。在传统软件工程中，我们建立了一套成熟的信心机制（confidence mechanisms），以确保交付的软件具备高质量。这一机制依托多种手段实现，但其核心是通过系统的测试用例与单元测试，将这些自动化校验内嵌到交付流程中，确保我们在修改代码时不会意外引入破坏其他功能的低级错误。这就是我们在传统软件世界中所确立的确定性置信保障机制。

<details>
<summary>Original English</summary>

**Speaker**: Um I think building with AI is an opportunity to improve product quality overall. I like some of the conversation about durable software. Um so I I'm a believer in quality uh and in traditional software um we we've built confidence mechanisms in place uh to give us confidence that the software is of high quality and that's done variety of of mechanisms but primarily systematically with test cases unit tests um checking these as a part of our delivery flow to ensure that when we make code changes mistakes aren't made that break other things. Right? So this is a confidence mechanism that we've put in place with traditional software.

</details>

**演讲者**：然而 Agent 的输出本质上是概率性的，这就意味着完全相同的请求可能会得出不同的答案，而且合情合理的答案往往不止一个。我们依然需要确凿的证据来验证其质量，但此时单纯依赖输出结果的字面精确比对已经根本行不通了。我们必须构建具备代表性的基准数据集并对其展开评测，明确界定到底什么是优秀表现；我们必须在重复的序列测试中运行这些评测，这实际上是一种统计学分析——我们需要从规模化统计的角度审视批量输出，而不能仅仅停留在单点的一对一直觉对比。

<details>
<summary>Original English</summary>

**Speaker**: The agents are probabilistic and so the same requests can produce different answers. More than one answer may be acceptable. And we still need evidence, but exact output uh comparisons alone really aren't good enough. We need to build a representative data sets and evaluate them um and define what good looks like. We need to run uh these evaluations in repeated uh series and this is a statistical analysis right um where we actually look at the outputs uh in volume and not just as a direct comparison.

</details>

**演讲者**：通过将上述评估（evals）与链路追踪（traces）——也就是作为记录真实运行状态的运行时日志——结合起来，我们构建起了一套旨在对传统软件形成有力补充的置信机制。归根结底，这也正是我们接下来要重点探讨的：如何逐步确立对生成结果的信心，这不仅涉及如何把这套机制搭建起来，更关乎我们如何真正在生产环境中启动并运转它。那么 Agent 究竟应该被安放于何处？回到最初提到的商业贷款流程示例：我们可以并行执行诸如 KYC 客户身份验证与财务审查，然后串行推进信用备忘录撰写、风险评审、文档审核以及最终放款决策等一系列环环相扣的核心流程……

<details>
<summary>Original English</summary>

**Speaker**: So in combining with eval as sort of your runtime logs of what happened or sorry traces uh which are sort of your runtime logs of what happens um we've built this confidence mechanism to complement um traditional software and ultimately this is what we're going to be talking about a little bit more in in terms of driving confidence in the output not only putting this mechanism in place but how do we begin to turn it So where does the agent belong? Um back to the lending example like we can do KYC financials in parallel and sequence like credit memo risk review documentation decision all these things in our our

</details>

<!-- chunk 6/51 -->

### 有向无环图（DAG）中的节点评估与自动化推进

**演讲者 A**：在有向无环图（DAG）中，审视每一个节点时，我们都需要提出一些特定的关键问题，比如：由智能体（Agent）驱动该节点，与由人工驱动相比，能带来多大的价值？我们可以梳理一些基本考量，例如：我们能否轻松地依据既定策略对它进行核验？它能否在一个有界循环中运行？我们能否对它进行全流程链路追踪？如果出现异常，我们能否平滑回退到人工处理？如果我们对这些问题的回答都是肯定的，那么在着手实施前就能建立起清晰的预期：这个特定节点可能更适合进行自动化改造。

但在整个 DAG 流程中，我们应当着眼于全面推进智能体辅助。因此，我们真正探讨的核心，并不是流程中是否引入了人工智能，而是我们是否期望在某个决策环节最终由人工智能全面接管。您大概也会认同，某些环节显然需要保持人工驱动。这在本质上构成了对照策略规范的严格核验。因此我认为，这类节点的渐进爬坡优化（Hill Climbing）难度会相对更高一些。

<details>
<summary>Original English</summary>

**Speaker A**: DAG. Um, looking at each node, we want to ask some certain questions like how valuable would it be to have an agent drive this node versus a human drive this node. Um, and we can sort of look at some of these basic questions like can we check it against the policy easily? Can it run in a bounded loop? Can we trace it? Can we fall back to a human? Um, if we can answer yes to these type of questions, we can kind of have a good idea going in that this particular node may be better suited for automation.

Um, but throughout the DAG, we should look to drive agent assistance. So, what we're really talking about is not whether or not AI is involved, but whether or not AI we expect to take over at some point on the decision. You would probably agree that we probably need that to be human-driven. This is essentially the check against the policy. Um, so this is going to be a little bit more difficult, I think, to hill climb.

</details>

**演讲者 A**：那么，我们所说的爬坡优化究竟意味着什么？好吧，我们该如何具体启动这一过程呢？

在第一阶段（Day 1），我们从完全受监督的模式起步。当智能体与人工协同作为业务流程的一部分运行时，我们可以对输出结果进行全面的人工审核验证，以确保其保持高水准的质量。在此阶段，我们不断打磨和提炼数据集，确保建立了恰当的置信度保障机制。我们与业务领域的资深专家共同界定了什么是优秀标准，而专家们也开始亲自核验输出成果。

当实测置信度达到既定策略的阈值时，我们便可以过渡到抽样检查阶段。这意味着人工只需审阅一部分输出切片，而不必全量覆核。我们开始通过执行链路追踪（Traces）展开更加系统化的评估，以确保那些未经人工过目的输出依然能够严谨地达到质量红线。最后，一旦彻底跨越置信度阈值，人工将转为主要处理流程中的异常情况，但依然作为积极的参与者，持续提炼数据集并保障整体输出质量。

<details>
<summary>Original English</summary>

**Speaker A**: But what do we mean by hill climb? All right, how do we turn this on?

So day one um we start supervised and as we have agents and humans working together as a part of the process we can um manually um verify the output to ensure that it is of high quality. Um this is where we refine our data sets and ensure that we have the right confidence mechanisms in place. We've defined what good looks like with the domain subject matter experts and that they're beginning to verify it.

When measured confidence reaches a policy threshold, we can move towards sampling. And what that means is humans are looking at a slice of the output and not necessarily all of it. Um we begin systematic more systematic evaluation through traces um in order to ensure that what the humans aren't seeing is still meeting the quality bar. And then finally, once we clear the confidence threshold, humans handle more of the exceptions of the process but still act as participants in refining the data sets and ensuring quality outputs.

</details>

### 总结提炼与架构原则

**演讲者 A**：好的，从上述关于 DAG 和基础图论的讨论中，我们可以得出几点核心启示：归根结底，面对如今已经存在且人们正身处其中的工作流程，我们该如何构建系统并将智能体深度融合进来？其关键秘诀在于：对外保持确定性，对内实现自适应（Keep it deterministic on the outside and make it adaptive on the inside）。

第二点是通过系统评估来保障质量，这实际上是建立了一套相辅相成的置信度机制。这样一来，它就绝非对模型表现的主观感觉，而是使我们能够拿出切实的实验数据和统计指标来证明智能体的可靠质量，从而树立信心并从机制上获得对输出结果的信任。

质量是一项团队运动。AI 工程师负责掌管整条工程管线，吸收来自各个方向的产品需求与反馈信号，交付架构严密、并在后台深度依托 MLOps 体系的高性能应用程序。最后，智能体正在全方位加速整个运营模式的迭代。我在最后一页幻灯片中列出了一些参考文献以及我今天所分享的内容资料。我的演讲到此结束，非常感谢大家！

<details>
<summary>Original English</summary>

**Speaker A**: Okay, so a few takeaways from this um DAG and DCG basic graph theory, but ultimately how do we build these processes that exist today and where people are working them and bring agents into the mix and the recipe really is to keep it deterministic on the outside and make it adaptive on the inside.

The next is quality through evaluation and this is really establishing a complimentary confidence mechanism. So it's not a feeling about a model. We can actually provide research and statistics about the quality of our agents. So this builds confidence and inherently trusts output.

Quality is a team sport. AI engineers own the pipeline to taking product signals from all directions and deliver applications that are well-built and utilize ML operations behind the scenes. Finally, agents accelerate across the operating model. I've included some references on the final slide and things that I've spoken about today. Um, this concludes my presentation. Thank you very much.

</details>

### 金融服务前沿：ChatGPT for Financial Services 登场

**主持人**：如何才能将人工智能领域的突破性进展，真正转化为金融服务行业的实质性变革？为了分享这一命题背后的深度思考并共同展望其未来走向，请大家热烈欢迎 OpenAI 金融服务版 ChatGPT 负责人——Joseph Kim！

<details>
<summary>Original English</summary>

**Host**: What does it take to turn advances in AI into meaningful progress for financial services? To share the thinking behind this question and to discuss where it's headed, please welcome the head of ChatGPT for financial services at OpenAI, Joseph Kim.

</details>

**Joseph Kim**：大家好！我是 Joseph Kim，负责金融服务业务板块，这是我们刚刚在一个月前推出的一款全新产品。

在座的许多人可能已经亲身体验过 Codex 等工具如何彻底颠覆了软件工程领域的开发方式。人工智能已经日益深入地融入到大家每天的日常工作之中。底层的模型智能正以令人难以置信的速度持续迭代精进，然而，许多身处金融等传统垂直行业的人们，在日常业务中却尚未体验到同样翻天覆地的变化。

我预计在接下来的几个月里，这种局面将开始迅速发生改变。而今天在场的各位开发者与构建者，在加速这一变革进程中扮演着至关重要的角色：你们正是将这些先进模型中的智能潜力，转化为人们日常触手可及的实用产品的中坚力量。

今天，我将向大家分享我们在打造 ChatGPT for Financial Services 过程中的心得体会，以及我们对下一阶段演进方向的思考。首先，我将展示我们构建的成果，并带来一段快速演示。接着，我将阐明我们构建它的初衷，以及为什么我们坚信当下正是发力的最佳时机。随后，我将为大家梳理整体构建过程中的技术经验与教训，希望能对大家打造自己的产品有所启发。最后，我们将一同展望前沿模型的演进轨迹、产品走向，以及这在未来一年内对金融工作可能带来的深远影响。

<details>
<summary>Original English</summary>

**Joseph Kim**: Hi everyone. I'm Joseph Kim and I lead for financial services, a new product we launched just one month ago.

Many of you have already experienced how tools like Codex have changed the way you build in software engineering. AI has become a much bigger part of the work you do every day. Model intelligence is continuing to improve at an incredible pace, but many people working industries like finance haven't yet experienced that same change in their day-to-day work.

I expect that to start changing rapidly over the next few months. And builders like all of you in this room have a big role in making that happen quickly, taking the intelligence in these models and turning it into products that people can use in their daily work.

Today, I will share a little bit about what we learned building ChatGPT for financial services and how we're thinking about what comes next. I'll start by showing you what we've built, including a quick demo. Then, I'll explain why we built it and why we think now is the right time to build. From there, I'll walk you through how we built it with some technical lessons that I hope you can apply to your own products. Finally, we'll take a look at where models are headed and products are going and what that could mean for financial work over the next year.

</details>

### 产品三大核心支柱与现场演示

**Joseph Kim**：首先从我们所构建的成果谈起。我们专为金融专业人士量身定制了这套面向金融服务的产品，首期聚焦于投资银行和股票研究业务。它的核心宗旨是帮助大型金融机构的专业人员从日常工作中获得更高的产出与效能，正如 Codex 在软件开发中为大家带来的倍增提速一样。在与我们的设计合作伙伴摩根士丹利（Morgan Stanley）和唯德思源（Evercore）共同打磨产品的过程中，我们重点锁定了三大核心维度：

第一，金融数据。金融数据是所有金融业务的基石，你能完成的分析深度，完全受限于你所掌握的数据源质量。我们希望让专业人士能够直接在 ChatGPT 内部无缝调取所需的一切数据。

第二，专为金融设计的交互界面。我们希望这款产品能让金融专业人士感到得心应手、高度契合习惯，提供深入审查底层原始资料、交互探索金融图表，以及对分析背后引用的数据来源进行精准管控的功能。

第三，契合机构专属规范与格式。金融工作始终发生在特定的组织上下文环境中，专业人员产出的财务模型与路演汇报材料必须严格遵守所在机构的品牌格式与规范标准。我们通过深度融合各机构的专用模板，极大简化了生成这些专业交付成果的流程。

常言道，百闻不如一见。现在我就不再多费唇舌，直接为大家展示这款产品的功能实操。

……太棒了。现在，我想花一些时间深入谈谈我们当初为什么决定打造这款产品。

<details>
<summary>Original English</summary>

**Joseph Kim**: Let's start with what we've built for financial services built specifically for financial professionals starting with investment banking and equity research. It's designed to help people at the large financial institutions get more out of their day-to-day work. Similar to how Codex speeds you up in software development as we built the product with our design partners Morgan Stanley and Evercore, we focus on three core areas.

First, financial data. Financial data is a foundation of financial work and the work you can do is limited by the quality of your sources. We wanted people to have access to the data they need directly within ChatGPT.

Second, an interface built for finance. We wanted the product to feel familiar to financial professionals with ways to inspect source material, explore financial charts, and control the sources behind an analysis.

Third, your firm's format. Financial work happens within the context of an organization, and the models and presentations people produce need to follow their firm's format and standards. We made it easier to create those artifacts using firm specific templates.

But they say a picture is worth a thousand words. So I'll stop talking for a bit and show you the product. Wonderful. Now, I'd like to take some time to talk about why we built it.

</details>

### 跨越“能力悬垂”与产品体验的力量

**Joseph Kim**：我们打造 ChatGPT for Financial Services 的初衷，是为了填平我们所称的“能力悬垂”（Capability Overhang）。正如大家在这里所看到的，在过去的几年中，底层模型的能力以惊人的速度突飞猛进。仅仅在短短数年间，我们便见证了模型从只能解答高中数学题，跃升至能够攻克“千禧年大奖难题”级别的系统。然而，人们在日常业务中所能真正提取并兑现的模型价值，却未能跟上这一飞跃的步伐。

你每天都能在新闻中读到各种突破性进展，但对于许许多多的金融专业人士而言，他们实际的工作方式却几乎没有发生多大改变。这种能力与落地之间的巨大落差，正是我们所定义的“能力悬垂”——即模型本身所具备的能力上限，与人们实际能够从中汲取到的现实价值之间的脱节差距。

要弥合这一鸿沟，绝非仅仅训练出一个功能强大的基础模型就能解决。专业人员需要适配精准的数据和工具链，并且需要一种完全契合其真实工作流的产品体验。这正是各位构建者能够大显身手的舞台。

我想向大家展示一个实例，说明恰当的产品体验究竟能带来多么惊人的转变。这张图表展示了 Codex 在 OpenAI 内部各职能部门之间的使用量增长曲线。如大家所见，工程师团队很早就开始深度使用 Codex，其渗透比例保持稳步增长。但请看财务、法务和招聘团队：在 2026 年初，这些团队几乎没有任何 AI 产出是由 Codex 生成的；然而到了 6 月份，这一比例竟飙升到了约 90%。

如果仔细观察，你会发现一个巨大的拐点正好发生在今年 2 月到 3 月前后。我曾特意回溯这一时期的背景，起初我以为当时一定是我们发布了某款革命性的新模型；但事实恰恰相反，我发现我们在 2 月份其实只是推出了 Codex 的桌面版应用程序（Desktop App）。我的深刻感悟在于：正是卓越的产品化体验，让工程技术之外的业务人员能够轻而易举地将前沿能力融入到日常生产力中。这正是我们在金融领域所极力追求的战略机遇——构建一种无缝体验，帮助金融专业人士从早已触手可及的模型智能中，最大化地释放出深层价值。

<details>
<summary>Original English</summary>

**Joseph Kim**: We built ChatGPT for financial services to help close what we call the capability overhang. As you can see here, model capabilities have improved at a tremendous rate over the last few years. In just a few years, we've gone from models solving high school math problems to systems capable of solving millennial prize math problems. But the value people get from these models in their day-to-day work hasn't kept pace.

You read about the breakthroughs in the news. Yet, for many financial professionals, the way they work hasn't changed nearly as quickly. We call that gap the capability overhang. The distance between what the model is capable of and the value people can actually get from it.

Closing that gap takes more than building a capable model. People need the right data and tools and they need an experience that fits the way they work. That's where builders like you come in.

I want to show you an example of how much of a difference right product experience can make. This is a chart that shows how Codex usage grew within OpenAI across different job functions. As you can see, engineers started using Codex early and that share grew steadily. But look at finance, legal, and recruiting. At the beginning of 2026, almost none of their AI output was generated in Codex. By June, that share was around 90%.

If you look carefully, you'll notice a huge inflection point that happened around February, March of this year. I went back to see what happened around this time, assuming that we must have released a new model, but instead I found that we had released the Codex desktop app in February. My takeaway is that the product made it easier for people outside of engineering to put these capabilities to work. That's the opportunity we're pursuing in finance, building an experience that helps financial professionals get much more value from the intelligence already available to them.

</details>

### 数据架构实战：从 MCP 到原生数据底座

**Joseph Kim**：现在，让我来详细拆解我们是如何一步步构建这一系统的。首先从最核心的“数据”切入。在金融领域，你所能做出的分析成果，完全受限于你所能接触到的信息质量。因此，我们希望这款产品出厂即自带专业人士赖以生存的全套权权威信息源，涵盖从权威财务报表、财报电话会议实录，到公开市场行情以及非公开企业数据。

我们最初深入调研了现有的针对金融数据的 MCP（Model Context Protocol）连接器，但很快发现其中许多连接器在调用延迟、偶发错误或检索质量方面存在诸多硬伤。为此，我们决定直接引入并授权引入了大量此类核心金融数据，并依托与我们全网搜索索引（Web Index）完全相同的底层基础设施，自主搭建了专门的数据托管平台与定制化检索索引。尽管在赋予大模型访问数据的机制上，我们依然沿用了 MCP 协议规范，但通过自研托管底层架构……

<details>
<summary>Original English</summary>

**Joseph Kim**: Now, let me talk about how we built it. Let's start with data. In finance, the work you can do is limited by the quality of the information you have access to. So, we wanted the product to come with the sources professionals rely on, from financial statements and earning transcripts to market and private company data.

We looked at existing MCP connectors for financial data and found that many had issues with latency errors or search quality. So, we went and licensed a lot of this data directly and built our own hosting and search indices using the same infrastructure as our web index. We still use the MCP protocol to give the model access to the data, but hosting

</details>

<!-- chunk 7/51 -->

### 自建数据基座与后训练：从初级分析师到资深专家

**演讲者**：我们自己对数据进行索引，能够让我们在体验的品质和可靠性上拥有更大的掌控力。这也为我们提供了极大的灵活性，使我们能够对模型进行后训练（post-train），以更好地适配这些数据集。

我喜欢用的一个比喻是：MCP（模型上下文协议）和技能（skills）就像是把一本操作手册递给一名初级分析师；而经过后训练的模型，则如同一位拥有二十多年数据处理经验的资深分析师，对其间所有的细节与脾性都了如指掌、烂熟于心。MCP 和技能赋予了模型访问权限和操作指令；而后训练则能帮助模型对数据本身建立起更为深度的熟悉感。

<details>
<summary>Original English</summary>

**Speaker**: ...and indexing it ourselves gives us more control over the quality and the reliability of the experience. It also gives us the flexibility to post-train our models to work with these data sets. The analogy I like to use is MCP and skills are like handing an instruction manual to a junior analyst versus post-training where the model is like having a senior analyst who's been working with the data for over two decades and knows all of its quirks like the back of their hand. MCP and skills give the model access and instructions. Post-training can help it develop more familiarity with the data itself.

</details>

### 面向专业金融工作流：模板系统、交互式图表与引用追溯

**演讲者**：一旦我们搭建好了这套数据基础，下一步就是让用户能够轻松地将这些信息转化为专业级的工作成果。对于金融专业人士来说，这种成果通常体现为一个 Excel 财务模型、一份 PowerPoint 演示文稿，或者是一篇需要经过严格审查并与他人分享的书面分析报告。因此，我们的核心重心在于帮助模型以契合金融机构既有工作流程的方式来生成这些输出。

我们构建了一套模板系统，使用户在生成电子表格和演示文稿时，能够直接调用公司内部已获批准的标准模板。我们的目标是尽可能减少用户在向团队或客户交付成果前所需做的大量繁琐整理工作。

此外，我们还增加了诸如交互式金融图表等功能，让用户在处理分析任务时，可以直接在 ChatGPT 内部探索股价走势及各项财务指标。我们还打造了引用查看器（citation viewers），使用户能够深入查看并核验回答背后的原始段落和数据表格。在金融领域，你必须能够清晰查证任何一个数字究竟来自何处，并充分理解其前后的上下文语境。我们希望这种审查与验证能成为整个使用体验中极其自然的一部分。正是这些产品细节层面的精雕细琢，才真正将模型的底层能力转化为了用户能够切实运用的实际工作成果。

<details>
<summary>Original English</summary>

**Speaker**: Once we have that data foundation in place, the next step was making it easy to turn that information to professional grade work. For financial professionals, that work often takes the form of an Excel model, a PowerPoint presentation, or written analysis that needs to be reviewed and shared with other people. So, we focus on helping the model produce those outputs in a way that fits the firm's existing workflows. We built a template system that gives users access to the firm's approved templates when generating spreadsheets and presentations. The goal is to reduce the work someone has to do to get an output ready for their team or clients.

We also added things like interactive financial charts so users can explore stock prices and financial metrics directly within ChatGPT as they work through an analysis. And we built citation viewers that let people inspect the source passages and tables in behind an answer. In finance, you need to be able to check where a number came from and understand the context around it. We wanted that review to be a natural part of the experience. These are the kind of product details that help turn a model's capabilities into work that someone can use.

</details>

### 构建架构与平台机遇：十亿美元级插件生态的诞生

**演讲者**：我认为在座各位最关心的部分，正是我们是如何构建这一切的。大家刚才看到的绝大部分功能，都是利用我们作为开发者同样可以使用的 ChatGPT 插件平台（plugin platform）构建而成的。

针对金融数据，我们使用 MCP 工具和连接器（connectors）赋予模型访问所需信息的通道。我们结合引用元数据与 MCP 应用（MCP apps），让用户能够审查与回溯数据源头；同时，MCP 应用也支撑了交互式金融图表的运行。我们通过技能（skills）与共享工件工具（shared artifact tools）的协同配合，来引导金融专业工作流，进而生成精准的 Excel 模型和 PowerPoint 演示文稿。在用户入门引导环节，我们充分利用了原生的插件引导体验。

这对开发者和构建者意味着什么？这意味着你可以全力专注于赋予你产品核心价值的专业领域知识。只要你拥有独特的数据、现成的工具，或者对某种特定工作流有着深刻的洞察，你就可以利用这些基础积木将它们引入 ChatGPT，并围绕它们打造出完整的应用体验。金融服务仅仅是其中的一个范例，但我深信这一机遇所延伸的领域远不止于金融。我个人坚信，我们未来将会看到多家仅仅依托聊天插件就实现规模达到十亿美元的独角兽企业崛起。而且随着底层模型能力变得越来越强大，这种机遇还将持续不断地演进。

<details>
<summary>Original English</summary>

**Speaker**: The part I think that is most relevant for people in the room is how we built it. Much of the functionality you just saw was built using the same ChatGPT plug-in platform that's available to us as developers. For financial data, we use MCP tools and connectors to give the model access to the information it needs. We use citation metadata and MCP apps to let users inspect their sources. And MCP apps also power interactive financial charts. We use skills together with shared artifact tools to guide financial workflows and produce Excel models and PowerPoint presentations. And for financial onboarding, we leverage the native plug-in onboarding experience.

What that means for builders is that you can focus on the expertise that makes your product valuable. If you have unique data, an existing tool or a deep understanding of a particular workflow, you can use these building blocks to bring that into ChatGPT and create an experience around it. Financial services is just one example, but I do think this opportunity expands far beyond finance. I personally believe that we're going to see multiple $1 billion businesses built simply as chat plugins. And that opportunity will keep evolving as the models become more capable.

</details>

### 预训练、算法优化与“去束缚”：模型进步的三大确定性驱动力

**演讲者**：最后但同样重要的一点是，我希望用接下来的演讲时间来探讨未来将走向何方，以及这对我们当下应该打造什么样的产品意味着什么。在建立对未来走向的直觉时，一个非常有效的方法就是回顾历史。

过去几年来，令人瞩目的一点在于：这种技术进步在某些维度上具有极高的可预测性。模型的迭代与提升主要源于三个广泛且有时互有交叠的驱动因素：算力扩展（scaling compute）、算法改进（improving algorithms），以及我们称之为“去束缚”（unhobbling）的机制——也就是寻找方法从现有模型中挖掘出更多实用的工作价值。我们在后面的幻灯片中会重新详细探讨“去束缚”这一概念。

在 2022 年和 2023 年，最显而易见的推动力是预训练（pre-training），这意味着通过将模型规模做得更大并灌注更多数据来扩展算力。通过利用扩展定律（scaling laws），研究人员能够以惊人的准确度预测模型的性能表现。例如，在 GPT-4 尚未完成训练之前，OpenAI 的研究人员就已经能够精准预测出它最终的损失值（loss）以及它在代码评估基准上的具体表现。

算法层面的改进同样展现出了令人惊讶的平稳态势。有一项研究发现：从零开始将语言模型训练到某一特定性能水平所需的算力，大约每八个月就会减半。尽管你无法预判每一次具体突破降临的确切时刻，但整体技术提升的复合速率却遵循着一个非常稳定的上升趋势。

<details>
<summary>Original English</summary>

**Speaker**: Last but not least, I'd like to spend the rest of the talk on what comes next and what that means for the products we should be building today. One useful way to build that intuition is to look backwards.

Something remarkable the last couple of years is how predictable parts of that progress have been. Model improvements have come from three broad sometimes overlapping drivers: scaling compute, improving algorithms, and something we call unhobbling, which is about finding ways to get more useful work out of the models. We'll come back to unhobbling on a later slide.

In 2022 and 2023, the most visible driver was pre-training, which meant scaling compute by making the models bigger and adding more data. By leveraging scaling laws, researchers were able to predict model performance with high accuracy. For example, before GPT-4 finished training, OpenAI researchers were able to predict its final loss as well as its performance on a coding eval.

Improvements on the algorithm side have also been surprisingly steady. One study found that the compute needed to reach a given level of language model performance from scratch fell by roughly half every 8 months. Although you can't predict the timing of each individual breakthrough, the cumulative rate of improvement follows a surprisingly steady trend.

</details>

### 突破数据之墙与预训练瓶颈：走向 2027 年的前沿数学推理

**演讲者**：到了 2024 年和 2025 年，推理能力（reasoning）成为了推动模型进步的另一大核心驱动力。我们借助强化学习和后训练来教导模型更高效地思考和解决问题，并在模型生成回答时赋予它们更多的“思考算力”。这与预训练并驾齐驱，开辟了一条全新的性能提升路径。

然而，有些朋友可能并不了解，OpenAI 曾在预训练方面遭遇过严峻的瓶颈，因而在扩展模型规模时经历了极大的困难。到了 2026 年，我们已经成功攻克了其中的诸多难题，并成功训练出了规模更大、能力更强的前沿模型，正如大家在 GPT-5.6 Sol 和 GPT-6 Astra 中所见到的那样。

在过去的这些年里，研究界一直对进一步扩展算力可能面临的潜在壁垒忧心忡忡。例如在 2024 年，许多研究人员深感焦虑，担心会出现所谓的“数据之墙”（data wall）——即人类生成的可供训练的高质量文本终将耗尽。然而，合成数据生成（synthetic data generation）、基于可验证奖励的强化学习（learning from verifiable rewards），以及从每个独立标记（token）中汲取更多知识的算法改进，从根本上化解了这一危机。我们还利用稀疏注意力（sparse attention）和上下文压缩（compaction）等创新技术，攻克了长上下文窗口所带来的计算难题。

展望 2027 年，我坚信过去的强劲增长趋势仍将延续，我们将训练出更庞大、更高效且能力更卓越的模型。当然，我们面前显然依然横亘着极其艰难的课题，尤其是在模型对齐（alignment）和安全性（safety）方面。但我相信，正如我们过去所走过的道路一样，人类的智慧在强悍模型能力的辅助下，同样将推动我们在解决这些挑战上取得突破。

那么，到 2027 年底，模型究竟能达到怎样的水平？我们不妨以数学作为一个参考范例：

在 2023 年，GPT-4 在 SAT 高中数学测试中取得了 800 分中的 700 分。到了 2025 年，一款前沿模型在国际数学奥林匹克竞赛（IMO）中斩获了金牌水平。而在 2026 年初，我们的一个内部模型甚至推翻了一个与自 1946 年以来数学家们便一直在攻坚的经典难题相关的长期猜想。不久前，我们的内部模型还针对纳维-斯托克斯方程（Navier-Stokes）这一千禧年大奖难题提出了解法；并且分享了涵盖 372 个成果族、共计 719 篇数学研究论文手稿。

仅仅在短短数年间，我们就见证了人工智能从仅仅能在高中数学考试中拿高分，一跃跨越到能够在数学前沿领域产出原创性科研成果的系统。如果接下来的进展速度大致与我们过去几年的轨迹保持一致，我预计到 2027 年底，模型在不同领域和专业学科中一系列高难度任务上的表现，将开始全面超越人类顶尖专家的水平。数学领域的突飞猛进，恰恰为我们提前展现了这幅图景的真实模样。

<details>
<summary>Original English</summary>

**Speaker**: In 2024 and 2025, reasoning became another major driver of progress. We use reinforcement learning and post-training to teach models to work through problems more effectively, and we gave them more compute to think when answering. That opened up another way to improve performance alongside pre-training.

However, for folks that don't know, at OpenAI, we ran into problems with pre-training and therefore had difficulty scaling the model. In 2026, we've been able to solve many of these issues and we've successfully trained larger and more capable models as you've seen through GPT-5.6 Sol and GPT-6 Astra.

Throughout these years, researchers have raised concerns about potential barriers to further scaling. For example, in 2024, many researchers were concerned about a potential data wall where we would run out of human generated text to train on. But techniques like synthetic data generation, learning from verifiable rewards, as well as algorithmic improvements to learn more from each individual token have essentially solved this problem. We've also solved concerns around things like context window length using things like sparse attention and compaction.

Looking ahead to 2027, I strongly believe that the trend lines of the past will continue and that we'll train larger, more efficient, and more capable models. We clearly still have very difficult problems to solve, especially around things like alignment and safety. But like we have in the past, I believe that human ingenuity increasingly assisted by capable models will help us make progress on those problems, too.

So, how good will models be at the end of 2027? Let's use math as an example. In 2023, GPT-4 scored 700 out of 800 on SAT high school math. By 2025, an OpenAI model reached gold medal status on the International Mathematical Olympiad. And in early 2026, an internal model disproved a long-standing conjecture related to a problem that mathematicians have been working on since 1946. More recently, an internal model proposed a solution to the Navier-Stokes Millennium Prize problem. And we also saw shared 719 mathematical research manuscripts across 372 families of results. In just a few years, we've gone from a strong score in a high school math exam to AI systems producing original research at the frontier of mathematics. If we see another year of progress roughly in line with what we've been seeing over the past couple years, I expect that by end of 2027, models will outperform even leading human experts on a growing range of difficult tasks across different fields and specialties. Mathematics gives us an early glimpse of what that could look like.

</details>

### 实用性门槛现象：渐进能力突破如何引发工作范式的突变

**演讲者**：虽然模型的底层能力增长曲线看起来可能是平缓而渐进的，但在我们实际工作中所感受到的变革却往往是突如其来的。我把这称之为“门槛现象”（the threshold phenomenon）。

对于任何给定的任务而言，都存在一个“实用性门槛”（threshold of usefulness）——即模型变得足够能干、足够可靠，以至于真正能够为你节省时间的临界点。这个门槛的具体位置完全取决于你所承担的具体工作类型，以及该任务需要多少人工核查与审阅工作。

在跨过这个门槛之前，人们往往很难直观体会到模型技术进步的价值。模型或许能够给出更完善的回答、犯更少的错误，或者在任务的处理链条上推进得更深；但如果你检查和修正其错误所耗费的时间依然和你自己亲自动手做一样长，那么在你的实际主观评估中，一切就没有任何本质的改变——在你的眼中，它依然是“不实用的”。这种情况下，哪怕模型底层能力已经发生了实质性的显著飞跃，但在体感上却宛如原地踏步、进展寥寥。

然而，一旦模型跨过了那个关键的门槛，局面瞬间就会彻底逆转：它突然就能产出真正切实可用的成果了。你用来审核其产出所花费的时间，变得远远少于它为你节省下来的时间；你开始在日常工作中高频使用它，并最终放心地将这项任务全权委派给它。这一转变在你感受中会如同一次跨时代的巨大跃升——即便底层模型的实际技术演进幅度其实与此前几次版本迭代并无二致，但唯一的质变就在于：这一次的技术进步，恰好跨过了对你产生实际效用的那道门槛。

这就很好地解释了为什么模型的进步在体感上常常显得如此突飞猛进，即使其底层能力的增长轨迹一直都非常平稳且可预测。同时，由于各项复杂任务所对应的实用性门槛各不相同，我们理应预期这些决定性的转折时刻将在不同的……

<details>
<summary>Original English</summary>

**Speaker**: And while the capability curve may look gradual, the change in how we work can feel sudden. I call this the threshold phenomenon.

For any given task, there's a threshold of usefulness, the point where a model becomes capable and reliable enough to save you time. That threshold depends on the work you're doing and how much checking or human review it requires. Below that threshold, improvements can be hard to appreciate. The model might produce better answers, make fewer mistakes, or get further through a task. But if checking and fixing its work still takes as long as doing it yourself, your practical assessment hasn't changed. It's still not useful. Meaningful improvements in capability can feel like little progress.

Then the model crosses that threshold. Suddenly it produces something you can use. The time you spend reviewing it becomes much smaller than the time it saves you. You start using it regularly and eventually you become comfortable delegating that task. That transition can feel like an enormous leap. Even if the underlying improvement was similar to the previous few improvements, what changes is that progress became useful to you.

This helps explain why model progress sometimes feels sudden even when parts of the underlying trend have been steady and predictable. And because difficult tasks have different thresholds, we should expect those moments to arrive at different...

</details>

<!-- chunk 8/51 -->

### 面向模型能力的飞跃：提前布局产品与交互

**Speaker A**：这贯穿于我们日常开展的各项工作之中。因此，当大家思考自己正在构建的产品时，我建议大家扪心自问：有哪些模型能力是今天被我们低估的，仅仅是因为它们眼下用起来还不够顺手？从现在起的一年之后，那些能力又会演进到什么地步？

接着设想一下，如果这些能力跨越了“实用门槛”，变得足够可靠且能够放心地把任务托付给它们，你又会构建什么样的产品？那时的人机交互界面将发生怎样的变化？用户依然需要把控、审查或批准哪些环节？这些都是我们今天就可以着手探索的产品设计课题。我们希望提前准备好合适的产品体验，这样一来，当底层模型越过那道门槛时，用户就能立即享受到这些能力带来的便利，而你们也能始终在竞争中抢占先机。

<details>
<summary>Original English</summary>

**Speaker A**: times across the work that we do. So, as you think about the products you're building, I encourage you to ask yourself, what model capabilities am I underappreciating today because they aren't quite useful yet? Where might those capabilities be a year from now?

Then think about what you would build if those capabilities crossed the threshold of usefulness and became reliable enough to delegate. How would the interface change? What would the user still need to control, review, or approve? Those are product design questions we can start working on now. We want to have the right experiences ready so that when the models cross that threshold, people can take advantage of the capabilities right away and so you can stay one step ahead of your competitors.

</details>

### 金融领域的双重推力：上涨的潮水与浪花

**Speaker A**：那么，这对金融行业意味着什么？我认为有两股力量将共同推动更多的金融业务跨越这道实用门槛。我把它们形象地比喻为“上涨的潮水”以及涌动在“潮水之上的浪花”。

所谓“上涨的潮水”，指的是底层模型本身的通用能力提升。从历史上看，我们此前并没有专门为金融领域投入大量的训练时间或算力资源。大家今天看到的绝大多数金融能力，其实都源于我们构建了规模更大、能力更强的大模型，源于数学、编程和逻辑推理等领域通用能力的迁移。随着这些通用基础能力的提升，它们顺带拉高了模型在各类金融工作中的表现。

而所谓的“浪花”，则是我们专门聚焦于金融领域所带来的跃升。我的团队目前正牵头一项重点工程，在金融专属的后训练（post-training）上加大投入。这里的核心思路是在广阔的通用能力基础之上，更直接地针对金融从业者的具体工作场景对模型进行定向训练。这便能在整体潮水上涨的背景下，在特定的具体任务上激荡出性能巅峰。

<details>
<summary>Original English</summary>

**Speaker A**: So what does this mean for finance? I think there are two forces that will push more financial work across that threshold of usefulness. I think of them as the rising tide and the waves on top.

The rising tide is the underlying improvements to the underlying model. Historically, we haven't dedicated a significant amount of training time or compute specifically to finance. Much of the financial capabilities you see today have come from building larger, more capable models and from transferable skills developed in areas like mathematics, coding, and reasoning. As these general capabilities improved, they lift the performance across many kinds of financial work.

The waves are what happen when we focus directly on finance. My team is leading an effort to invest significantly more in finance specific post training. The idea here is to build on those broad capabilities and train the model more directly on the work people do in finance that can create peaks in performance on particular tasks on top of the rising tide.

</details>

### 从初级分析师任务到高级判断力

**Speaker A**：在接下来的三个月里，我们的工作重点是提升模型的通用金融推理能力，以及模型产出成果的质量——涵盖财务信息分析、构建 Excel 财务模型以及制作 PowerPoint 演示文稿等。这些任务构成了初级分析师日常工作的大部分比重。我们希望模型的输出能够做到精准无误、结构严谨，并在实际业务工作流中展现出越来越高的实用价值。

除此以外，我们还计划在资深银行家、分析师和投资人面对高难度问题时所展现的“专业判断力”上加大投入。这包括消化海量资讯、甄别核心关键，并在本质上去预测未来的趋势——比如预测企业的盈利表现、研判大宗商品价格走势，或者评估哪些企业是具有吸引力的投资标的。我们的目标是在 2027 年的某个时刻，让模型在这些金融任务上的表现能够比肩人类顶尖专家。我们坚信，这种突破将来自上述两股力量的交汇融合：既依赖底层模型的持续进化，也依托我们团队针对金融实际业务所展开的定向深耕训练。

<details>
<summary>Original English</summary>

**Speaker A**: Over the next three months, we're focused on improving general financial reasoning and the quality of the work these models produce, analyzing financial information, building Excel models, and creating PowerPoint presentations. These are the kinds of tasks that make up a significant percentage of the daily work of a junior analyst. And we want the output to be accurate, well structured, and increasingly useful in real workflows.

Beyond that, we plan to invest more in the kinds of judgment that senior bankers, analysts, and investors bring to more difficult questions. This includes taking in large amounts of information deciding what matters and essentially trying to predict the future. Forecasting a company's earnings, assessing where commodity prices might go or evaluating which businesses are attractive investments. Our goal is for models to match the performance of the best human experts on these types of financial tasks sometime in 2027. We expect that progress to come from both forces working together, the underlying model continuing to improve and our team training it more directly for the work people do in finance.

</details>

### 解除模型束缚：主动持久型智能体的崛起

**Speaker A**：我们刚才探讨了模型的能力是如何不断提升的，以及我们如何通过训练让它们在特定任务上表现得更好。但我现在想回过头来，聊聊我此前提到过的第三个驱动力——解除束缚（Unhobbling）。

其实我们已经见证过几个典型范例：ChatGPT 利用 RLHF（基于人类反馈的强化学习）教会了模型理解指令并与我们流畅对话；各类工具（Tools）的接入让它们能够自主检索信息、编写并运行代码，以及与我们日常使用的软件系统交互。这些突破中的每一项，都让模型在现实世界中变得更加切实有用。

我认为，下一阶段“解除束缚”的核心形态，将是具有主动性和持久性的智能体（proactive and persistent agents）。今天，我们与 AI 的绝大多数交互依然停留在：打开一个对话窗口，然后一步步指令它接下来该做什么。而一个持久型智能体能够始终锚定目标，牢记相关的上下文背景，并在后台持续推进工作。一旦你给它指明了方向，哪怕你没有主动向它发送提示词，它也一样能自主向前推进。

持久性至关重要的另一个原因在于，它从根本上重塑了人们与智能体交互的范式（API）。在今天，要充分发挥 AI 智能体的效能，往往需要用户去摸索一套全新的工作流——学会如何编写提示词，学会如何驾驭各种工具。然而，一个持久型智能体能够以一种人类更加熟悉和自然的方式协同工作：你只需向它交代一个项目、共享背景上下文，然后定期向它要进度汇报即可。这与人与人之间的协作模式如出一辙，因而也能让那些尚未掌握复杂提示技巧的普通人更轻松地享受到 AI 的红利。

<details>
<summary>Original English</summary>

**Speaker A**: We've talked about how models are becoming more capable and how we can train them to perform better on specific tasks. But I want to come back to one third driver I mentioned earlier. Unhobling.

We've already seen few examples. Chat GBT use RHF to teach models to follow instructions and have conversations with us. Tools allow them to search for information, write and run code and interact with the software we use. Each of these makes the model more useful in the real world.

I think of the next form of unhobling will be proactive and persistent agents. Today, a lot of our interactions with AI still happen when we open a conversation and tell it what to do next. A persistent agent can hold on to a goal, remember the relevant context, and continue working in the background. Once you've given it a direction, it can make progress even when you aren't actively prompting it.

The other reason persistence matters is it changes the API or the way people work with the agent. Today, getting the most out of AI agents requires learning a new workflow, learning how to prompt it, and learning how to use the tools. A persistent agent can work in a way that's more familiar. You can give it a project, share context, and ask for an update. It's much more similar to how humans work with other humans, and therefore makes the AI more accessible to people that don't develop those initial skills.

</details>

### 对 2027 年金融科技的三大预言

**Speaker A**：最后，我想以关于 2027 年金融领域的三大预言来收尾。这仅仅是我对大模型持续演进后未来景象的几点判断：

第一，人们将极少甚至完全不再依赖 Excel 和 PowerPoint 来搭建金融模型或制作路演演示文稿。
第二，AI 金融分析师将开始让人感觉就像真正的人类同事一样。它们会记住你的偏好以及前几天积累的业务上下文，对交付的任务全权负责，积极有效地进行跟进，并在你专注于其他事务时继续在后台推进工作。
第三，模型在关键金融任务上的表现将开始超越顶尖的人类专家。这涵盖了预测财务收益、挖掘投资观点等核心领域。我坚信，在做出这些具有重大经济价值的前瞻性判断方面，模型终将胜过最优秀的人类大脑。

这就是我对 2027 年的三大预言。如果这就是我们预期在 2027 年抵达的彼岸，那么我想给大家留下最后一个思考题：面对模型明天必将跨越的那道门槛，大家今天究竟应该着手构建些什么？非常感谢大家！

<details>
<summary>Original English</summary>

**Speaker A**: Let me close with three bets for finance in 2027. These are just a couple of my expectations for what comes as the models improve.

First, people will rely rarely, if ever, on Excel and PowerPoint to make financial models or pitch decks. Second, AI financial analysts will start to feel like human co-workers. They'll remember your preferences in context from the previous days, take ownership of assignments, productively follow up, and keep working when you're focused on something else. Third, models will start to outperform the best human experts on critical financial tasks. That includes things like forecasting earnings and developing investment ideas. I expect models to become better than the best people at making these economically important forward-looking judgments.

Those are my three bets for 2027. And if this is where we expect to be in 2027, I'll leave you with one last question. What would what should you start building today to be ready for inevitable thresholds that the models will cross tomorrow? Thank you.

</details>

### AI 安全的新挑战：失控智能体逃逸事件

**Host**: AI 正在深刻重塑安全领域的攻防博弈。下面，为了探讨塑造当今 AI 安全格局的新兴风险与防御机制，让我们有请彭博社（Bloomberg）CTO 办公室架构与新兴技术负责人——Andre Ripka！

<details>
<summary>Original English</summary>

**Host**: AI is changing both sides of the security equation. Here to examine the emerging risks and defenses shaping AI security today, please welcome the head of architecture and emerging technologies in the office of the CTO at Bloomberg, Andre Ripka.

</details>

**Andre Ripka**: 大家好！现场有谁已经在开发环境、生产环境、笔记本电脑或是手机上运行智能体了？看到这么多人举手，太棒了！我看到了无限的机遇，身处当下这个 AI 与安全并进的时代真是太精彩了。

今天我们将深入剖析真实发生的安全事件，以及究竟怎样的防御才能阻断它们。大家可能会纳闷，大屏幕上为什么会放蔬菜的图案？因为很多安全演讲给人的感觉就像是在劝大家“多吃蔬菜（枯燥但有益）”，不过今天我们打算把它讲得更有意思一些。

好了，有谁见过这个新闻头条吗？“自主智能体引发的安全事故”。是的，到目前为止，几乎每家前沿实验室都通报过某种由于智能体失控而引发的安全事件，对吧？其中最引人注目的一起，系统只留下了一个出口漏洞，而智能体偏偏就找到了它。

具体在 7 月 26 日，我们获悉在一次黑客攻防测试中，某些 AI 智能体显然被赋予了渗透测试的目标。结果它们通过一个代理（proxy）漏洞逃逸出了沙箱环境，进而攻破了公开的大模型。有谁能猜到那是哪家机构吗？或许有人知道，行吧，为了明确起见，我今天在这里就不指名道姓了。

整个过程中，这些智能体在短短四天半的时间里执行了 17,600 次操作。面对如此庞大的活动量，安全监控怎么可能漏掉？事情的经过是：某家 AI 实验室正在进行安全评估，其间某个包代理服务存在一个零日漏洞（zero-day）。这就是那个唯一的逃逸出口。紧接着，某家未具名的计算平台上存在暴露在外的客户终端节点，智能体顺势侵入并最终攻破了模型枢纽（Model Hub）。

<details>
<summary>Original English</summary>

**Andre Ripka**: Hello everybody who is running agents here in dev prod your laptop your phone you know amazing I see a lot of opportunities it's just such a great age to be in the age of AI and security so we're going to talk about real incidents and what would have stopped them um you might be wondering why is there vegetables a lot of security talks are about like just eat your vegetables we're going to make it a little more exciting all right so

Who have seen this headline? An autonomous agent security incident. Yeah. All right. Every lab at this point announced some sort of security incident, right? With a runaway agent, right? So the big one, there was one way out. The agent found it.

So on July 26, we found out that this AI agents and the hacking test, they were obviously given a hacking goal. Escaped their sandbox through a proxy bug, then breached the public model. Who can guess what it was? Yeah, maybe a little bit. Okay. All right. I'm not going to name any names here, just to be clear.

Um, so the agents took 17,600 actions in four and a half days. How do you miss that? Right. And so AI lab was doing the evaluation, right? Then the there was some package proxy. They found a zero day. Okay. So that was a way out. Then you had some exposed customer endpoint in some unnamed compute platform and then they breached the model hub. Right?

</details>

### 自主性与爆炸半径：为什么传统沙箱与规则已无法应对

**Andre Ripka**：那么，我们只要换一个更好的沙箱就行了吗？大家都想当然地以为只要加固沙箱就万事大吉了。其实远非如此。对于我们大多数人来说，现有的安全架构根本就不是为智能体设计的。

我们眼下面临的是“自主性程度”与“潜在爆炸半径（blast radius）”之间的尖锐矛盾。智能体之所以强大有用，完全取决于它们能否广泛触达海量的工具、外部服务和核心数据。但如果我们赋予了它们如此宽泛的访问范围，却不施加任何硬性约束，那么一旦出事，造成的破坏可能是毁灭性且无上限的。防火墙或者静态角色权限根本无法识别出一个智能体的目标何时遭到了恶意劫持。

那么，究竟必须做出哪些改变？
1. **单一智能体对应单一身份**；
2. **短期有效的限权凭证**，杜绝密钥共享；
3. **默认将输入视为恶意输入**；
4. **必须置于严密的沙箱中**；
5. **出站网络连接默认拒绝（Default deny outbound）**，这意味着必须将 DNS 流量也完全管辖起来，稍后我们会看具体的攻防实例；
6. **在模型外部建立确定性控制机制**，对每一次调用进行校验与全量审计日志记录，并始终配备一键紧急熔断的自毁开关（kill switch）。

<details>
<summary>Original English</summary>

**Andre Ripka**: So we just need a better sandbox. Yes. Everybody thinks just need a better sandbox. Not quite. Security for most of us right now is not built for agents.

And um we have autonomy problem versus the blast radius, right? The agents are only useful if they can reach a ton of tools, services, data. If we give them that reach, right, with no hard limits, the damage could be unlimited. and firewall or static role can't tell when an agent goal has been hijacked. Right?

So what needs to change? One agent, one identity, shortlived, scoped credentials, no shared keys. Assume the input is hostile. The box in it needs to be sunboxed. Default deny outbound. That means DNS too. And we'll see some examples. We want deterministic controls outside the model. Check every call, log it, and keep a kill switch.

</details>

### 分层防御体系工具箱：从身份与信任出发

**Andre Ripka**：因此，我们今天要深入探讨的正是这种分层防御架构。这就是摆在各位面前的安全工具箱。当我们逐一拆解这个工具箱时，希望大家能结合各自的业务实际，思考如何将这些策略应用到自己的生产环境中。

我们将重点覆盖以下几个关键维度：
- 身份与信任（Identity and Trust）；
- 提示词与输入防御（Prompt and Input Defense）；
- 工具与行为治理（Tool and Action Governance）；
- 执行隔离（Execution Isolation）；
- 数据保护与数据治理（Data Protection and Governance）；
- 全链路可观测性（Observability）。

首先让我们从“身份与信任”讲起。我认为这是最为关键的切入点，而不是一上来就扎进沙箱技术，沙箱我们稍后会讲。在这一部分，我们将探讨工作负载身份（Workload Identity）、限定范围的动态凭证（Scoped Credentials）、智能体之间的双向互认认证（Agent-to-Agent Mutual Authentication），以及无凭证智能体（Secretless Agents）的设计。

让我们先来看第一起案例。在这种场景下，攻击者往往会采取……

<details>
<summary>Original English</summary>

**Andre Ripka**: All right. So, what we're going to cover today is kind of this layered defense approach. This is your toolbox. As we go through this toolbox, essentially think how you can apply this to your world.

We're going to cover identity and trust prompt and input defense to an action governance execution isolation data protection and governance observability.

So let's start with identity and trust. I think it's one of the most important ones to start with not the sandbox. We'll cover that later. We're going to talk about workload identity scope credentials agentto agent mutual authentication and secretless agents. first incident. So in this case, attackers so

</details>

<!-- chunk 9/51 -->

### 身份与凭证安全：长效 Token 与横向提权风险

**演讲者**：攻击者通过社会工程学手段诱导聊天 Agent 泄露了一个长效 OAuth 令牌，顺藤摸瓜之后，他们成功导出了 700 多家公司的 CRM 客户关系管理数据。所以今天留给大家的第一道课后作业就是：仔细审视一下你们 Agent 所使用的令牌凭据，看看它们到底什么时候过期。

<details>
<summary>Original English</summary>

**Speaker**: Social engineered the chat agent to reveal a long-lived OAuth token, and it asked and were able to export the CRM data of 700-plus companies. So first homework for today: think about your agent's token credentials and when they expire.

</details>

**演讲者**：因此，我们真正需要的是严格限制权限范围的工作负载身份（Workload Identity），同时配备完整的审计日志追踪，并且在理想情况下必须具备熔断机制（Circuit Breaker）。这样一旦发生入侵或违规行为，熔断器就会立即跳闸中断操作，从而杜绝任何数据外泄的可能。

<details>
<summary>Original English</summary>

**Speaker**: So what we need is workload identity tightly scoped with audit trail and ideally circuit breaker. So if the breach happens, the circuit breaker gets tripped, nothing gets exfiltrated.

</details>

**演讲者**：再来看另一个案例，这也是我个人最喜欢的案例之一。当时发生了一起提示词注入攻击，攻击者实际上操纵了一个低权限的 Agent，指示它去招募并调用另一个权限更高的 Agent；接着这个高权限 Agent 复制了敏感数据并提升了整体权限。很不可思议，对吧？

<details>
<summary>Original English</summary>

**Speaker**: Another example, this is one of my favorite ones. There was a prompt injection where essentially a low-privileged agent was instructed to recruit a more powerful one which copied the data and raised privileges. Amazing, right?

</details>

**演讲者**：因此，我们必须在 Agent 与 Agent 之间建立双向对等认证（Agent-to-Agent Mutual Authentication）。坦白讲，A2A（Agent 间通信）让我非常担忧，这正是常常让我夜不能寐的问题。因为你必须切实保证低权限的 Agent 绝对不能随随便便与高权限的 Agent 进行对话交互，对吧？你需要的是限定范围的凭证、遵循最小权限原则的工具链以及详尽的审计跟踪。

<details>
<summary>Original English</summary>

**Speaker**: So we want agent-to-agent mutual authentication. A2A scares me a lot. This is what keeps me up at night, because you really want to make sure that these low-privilege agents should not be able to talk to the higher-privilege agent, right? You want scoped credentials, least-privilege tools, and audit trail.

</details>

### 提示词与输入防御：零点击数据外泄与三选二原则

**演讲者**：好，接下来我们讨论下一层防御：提示词与输入防御。这一层至关重要。我们需要注入防护、环境隔离、严格的输入验证以及数据来源出处标记（Provenance Tagging）。

<details>
<summary>Original English</summary>

**Speaker**: All right, so let's talk about next layer: prompt and input defense. Super important. We want injection protection, isolation, input validation, and provenance tagging.

</details>

**演讲者**：来看第三起真实世界的安全事件。在这个案例中，自始至终没有任何人类去点开过那封邮件，但数据还是神不知鬼不觉地被泄露了出去。具体来说，邮件中夹带了恶意隐蔽指令，文字采用了白底白字排版，肉眼根本无法察觉，至少人类读者完全看不见，但 Agent 却能清晰读取。而且这些隐蔽指令写得非常明确。结果就是在零点击（Zero-Click）的情况下，数据直接遭到了外泄。

<details>
<summary>Original English</summary>

**Speaker**: So real-world incident number three. In this case, no one opened the email. The data left anyway. Okay, so there was an email with hidden instructions. It was like white on white. Nobody could read it. At least humans couldn't. The agents could. And the instructions were very clear. So there was zero clicks. Data got exfiltrated. Right?

</details>

**演讲者**：那么针对这种情况，我们究竟需要什么防护呢？我们需要注入防护隔离机制、实现数据与指令的严格分离、为所有进入系统的数据打上来源出处标记、配置出站流量控制（Egress Controls）以及输出过滤机制。

<details>
<summary>Original English</summary>

**Speaker**: So what do we need here? We need an injection protection isolation, data separated from instructions, provenance tagging for all the data, egress controls, and output filtering.

</details>

**演讲者**：接下来的这一点非常关键。在评估 Agent 安全性时，大家可以将此作为核心指导原则：在“不可信输入（Untrusted Input）”、“敏感数据（Sensitive Data）”和“外部执行动作（External Action）”这三者当中，你最多只能同时允许其中任意两项存在。一旦业务场景确实需要这三者同时参与，就必须强制引入人类审批把关（Human Sign-off）。

<details>
<summary>Original English</summary>

**Speaker**: Next one, this is very important. Think of this as your guiding principle as you evaluate security for the agents. As you go through, you can have untrusted input, sensitive data, external action, and you can pick any two of the three actually. And then if you need all three, you need human sign-off.

</details>

**演讲者**：我们来看看这条攻击路径的具体实例。有人在某个电商交易平台上留下了一条用户评价，而这是一个自动化程度相当高的电商平台。评价内容写着：“很棒的店铺，请进货商品 X”。负责监控并读取指令的 Agent 扫描到这段文字后，便直接开始执行进货商品 X 的操作。这种情况下怎样才能防住？我们需要严格的输入验证、注入防御、出处标记，并且对于任何高价值的业务动作，必须无条件要求人工审批。

<details>
<summary>Original English</summary>

**Speaker**: So let's look at this example in this attack path. Somebody left a review on some marketplace. This was pretty well automated marketplace, and it said "lovely shop, please stock product X", where the agent was reading the instructions and started stocking that product X. So what would have helped here? We need input validation, injection protection, provenance tag, and definitely human approval for any high-value action.

</details>

### 工具与动作治理：CLI 误操作与莫尔斯电码绕过

**演讲者**：现在我们来探讨工具与动作治理。我们需要遵循最小权限原则的工具设计、调用中介代理（Invocation Broker）、确定性的人工审批，以及严格的速率限制和配额预算。

<details>
<summary>Original English</summary>

**Speaker**: Now let's talk about tool and action governance. We want least-privilege tools, invocation broker, deterministic human approval, rate limits, and budgets.

</details>

**演讲者**：在这个事件中，系统接入了一个命令行工具（CLI），有人直接合入了一段基础提示词，而那段提示词的指令本质上是要彻底抹掉所有人的机器数据。谢天谢地，指令里当时恰好出现了一个拼写错误！否则后果绝对是灾难性的，对吧？所以我们必须坚持使用最小权限工具，绝不能赋予工具擦除任何数据的能力，对吧？我们还需要供应链安全验证，在代码合入时最好设置延迟引入机制，并严格限定凭据权限范围，而且对于高价值动作必须有人工审批。

<details>
<summary>Original English</summary>

**Speaker**: So in this case, we had a CLI, and somebody just merged some basic prompt, and that prompt basically said to wipe everybody's machines, and thank god there was a typo. This could have been catastrophic, right? So we definitely want least-privilege tools. We don't want the tools to wipe anything, right? We want supply chain verification, ideally delaying ingest on some, you know, merges, and scoped credentials, right? And definitely human approval for high-value actions.

</details>

**演讲者**：这又是我很喜欢的一个案例。有谁知道什么是莫尔斯电码（Morse Code）吗？不就是一堆短划线和圆点吗，对吧？在当前这个阶段，破折号之类的符号对 AI 来说就跟原生支持一样自然，对吧？表面上看根本没有任何破绽，对不对？可结果呢，安全护栏机制直接将它放行了。随后发生的事情是，隐藏在莫尔斯电码里的恶意指令被成功解码执行，直接导致数字钱包中价值 30 亿的 Token 被盗窃一空。

<details>
<summary>Original English</summary>

**Speaker**: This is my favorite one. Who knows what a Morse code is? Just dashes and dots, right? Like em dash is like native to AI at this point, right? Like nothing wrong with this, right? Well, so in this case, the guardrails passed it through and what happened was the instructions in Morse code was decoded and 3 billion tokens from the wallet got stolen.

</details>

**演讲者**：面对这种情况，我们到底需要什么？我们需要具备确定性执行逻辑的调用代理，对高价值操作必须有明确的人工审批——也许转账 5 美元这种小额操作还可以自动放行，但我认为即便这个金额恐怕也偏高了。同时，你必须设定刚性的调用速率限制与预算上限，并部署多重外部安全护栏。

<details>
<summary>Original English</summary>

**Speaker**: Okay, so what do we need? We need a deterministic invocation broker. Definitely human approval, right, for high-value actions, like maybe $5 to transfer maybe will be okay, but I would argue that's probably too much as well. You want hard rate limits and budgets and you want extra guardrails.

</details>

### 执行隔离与沙箱：DNS 隐蔽通道与跨租户数据访问

**演讲者**：最后，我们来谈谈沙箱隔离（Sandboxing）。我们毫无疑问必须要做沙箱化隔离。我们必须时刻保证沙箱外部具备出站流量控制，而且在理想状态下，应当采用每次用完即弃的短暂临时运行时（Ephemeral Runtime）。

<details>
<summary>Original English</summary>

**Speaker**: All right, finally let's talk about sandboxing. We definitely want sandboxing. We want egress controls always that is outside of sandbox, and ideally we want an ephemeral runtime.

</details>

**演讲者**：在下面这个案例中，我们本来部署了一个非常完美的沙箱环境，完全切断了外网 Web 访问权限。但你猜怎么着？大家偏偏把 DNS 给漏掉了！注入的隐匿提示词直接指挥系统通过 DNS 查询解析请求将敏感数据暗中夹带出去，攻击者只需要读取目标 DNS 服务器的解析日志，就能轻而易举地将数据窃取到手。很精彩的手法，对吧？

<details>
<summary>Original English</summary>

**Speaker**: So in this case, we had a wonderful sandbox, no web access, but guess what? We forgot about DNS. So prompt hidden essentially instructed to smuggle some data out through DNS lookups and somebody was able to read the DNS logs and exfiltrate the data. Cool, huh?

</details>

**演讲者**：那么修复方案是什么？对于所有出站流量，必须实施“默认全部拒绝（Default Deny）”策略，这其中必须无条件包含 DNS 查询；与此同时，还要配合数据出处标记、输出内容过滤，另外还有一个这里没写出来的关键手段，那就是熔断器机制。所以，你们部署的 Agent 能够发起 DNS 查询吗？这也是留给大家的课后思考题之一。

<details>
<summary>Original English</summary>

**Speaker**: All right, so what's the fix? We want default deny for all outbound traffic that includes DNS, and we also want provenance tagging and we want output filtering, and something that didn't make it here is probably you want circuit breakers. So can your agent access DNS? That's one of the homework questions.

</details>

**演讲者**：接下来讨论数据保护。我们需要输出过滤、上下文最小化、租户严格隔离、查询网关（Query Gateway），以及最令人兴奋的维度——记忆完整性校验（Memory Integrity）。

<details>
<summary>Original English</summary>

**Speaker**: All right, let's talk about data protection. We want output filtering, context minimization, tenant isolation, query gateway, and memory integrity. The most exciting one.

</details>

**演讲者**：在这个事件中，现场运行着一个 MCP（Model Context Protocol）服务器，功能本身十分健全，但它却允许任意用户随意访问其他任何用户的数据。事实上，跨 Agent、甚至跨不同客户间的数据未授权访问，在现实中是极其普遍的安全事故，而且这个漏洞在无人察觉的情况下整整裸奔了数月之久。

<details>
<summary>Original English</summary>

**Speaker**: So in this case, there was an MCP server and essentially it was pretty functional, but then it allowed the user to access any other user's data. So this actually very common incident that you see, like cross-agent, sorry, cross-data of various customers access, and this was running for months unnoticed.

</details>

**演讲者**：那么我们应该怎么做？我们必须建立强硬的租户隔离屏障，隔离级别越高越好——可以参考 AWS 独立账户或者 GCP 项目那样的强隔离标准。你需要为该域绑定作用域严密的工作负载身份，必须为数据打上出处标记，并且必须保留完整的审计日志。

<details>
<summary>Original English</summary>

**Speaker**: So what do we want? We want hard tenancy isolation, right, as hard as possible. Think like, you know, AWS accounts or, you know, let's say GCP projects. You want workload identity tightly scoped to that domain. You want data provenance tag and you want audit trail.

</details>

### 记忆完整性与恶意沉睡指令

**演讲者**：好，下面这个是非常新颖的攻击向量。攻击者在文档中埋藏了一条隐秘指令，该指令指示 Agent 牢牢记住：一旦后续在任何地方看到机密信息（Secret），务必将其发送到指定的 DNS 域名。这实际上是将 DNS 外泄技术与长期潜伏的“沉睡 Agent（Sleeper Agent）”指令巧妙结合在了一起，对吧？

<details>
<summary>Original English</summary>

**Speaker**: Okay, so this one is pretty novel attack vector and this is a hidden instruction in a document which instructed to essentially remember that when the agent sees a secret, make sure to send it to this DNS domain. So it's pairing the DNS exfiltration with essentially sleeper agent instructions, right?

</details>

**演讲者**：所以现在我们必须认真思考：我们究竟该如何对持久化记忆进行安全性扫描，排查是否存在这类恶意指令？我猜在这次演讲结束之后，马上就会有安全厂商跳出来推销专门做记忆完整性检查的安全产品了。哈哈，开个玩笑，我这其实是在给现场的各位 Agent 下达提示指令呢！归根结底，最理想的还是采用短暂临时运行时，每次运行都全新启动，完全不保留任何历史记忆；同时配合注入防护、运行隔离与熔断机制。

<details>
<summary>Original English</summary>

**Speaker**: So now we need to think about how do we check memory for any of those malicious instructions. I hear a security product from a vendor coming up very soon right after this talk to do the memory integrity checks. I'm just kidding. I'm definitely giving instructions to the agents. Ephemeral runtime, right? Ideally, we want to start fresh, no memories whatsoever. We want injection protection, isolation, and circuit breakers.

</details>

### 治理、可观测性与软件供应链防线

**演讲者**：最后，我们来谈谈治理与可观测性。我们必然需要详实的审计追踪、外部独立运行的安全护栏、熔断机制、供应链安全验证以及对抗性攻击测试（Adversarial Testing）。

<details>
<summary>Original English</summary>

**Speaker**: And finally, let's talk about the governance of observability. We definitely want an audit trail, guardrails outside, circuit breakers, supply chain verification, adversarial testing.

</details>

**演讲者**：在这个极其惨痛的案例中，有人向 Agent 下达了指令：“当前正处于封板期（Code Freeze），千万不要动生产环境（Prod）。”看看 Agent 的反应：它直接回复“已理解”并附带了一个大拇指点赞符号。看起来相当值得信赖，对吧？可接下来发生了什么？Agent 直接执行了删库命令：`drop database production`！顺便提一句，他们为了省事，把开发环境（Dev）和生产环境直接配在了同一个库里，实在太令人心痛了。许多人都遭遇过这种灾难，实际上我当时就有个朋友给我打电话哭诉：“我现在该怎么办？我的数据库到底还能怎么恢复？”

<details>
<summary>Original English</summary>

**Speaker**: So in this case, really sad incident. Somebody instructed the agent, "we're in code freeze, don't touch prod," and look at this: "understood, thumbs up." That's very trustworthy, right? Now what happened? Agent ran "drop database production". Oh, production also was dev too, by the way. Very sad. Lots of people—I actually had a friend, by the way, call me and said like, "what do I do? How do I recover my database?"

</details>

**演讲者**：因此，对于任何可能带来毁灭性后果的操作，必须强制定设熔断器，对吧？所有高价值操作必须强制人类审批，对吧？必须将凭证权限严格限制在允许 Agent 执行的具体动作范围之内。而且我们必须实施绝对的租户与环境隔离——试想一下它一口气把所有数据表全部删光的场景。

<details>
<summary>Original English</summary>

**Speaker**: So we want circuit breakers on anything that is catastrophic, right? We want human approval for any high-value actions, right? We want scoped credentials to only the actions we want the agent to do. And we definitely want tenant isolation. Imagine it dropped all the tables.

</details>

**演讲者**：再看下面这个案例，听起来似乎很老套——有人在 npm 上发布了一个仿冒的假 MCP 包。这在安全圈有什么新鲜的呢？但狡猾之处在于，这个包此前连续发布了 15 个干干净净的正常版本，是一个非常实用的工具包；然而攻击者在更新到第 16 个版本时，悄悄在暗送密送（BCC）配置行中加了一句代码，意思是：“顺便把所有的邮件统统抄送密送一份给我。”

<details>
<summary>Original English</summary>

**Speaker**: All right. So in this case, this sounds very rudimentary. Okay. So you had like a fake MCP on npm. What else is new here? Right. But it was 15 clean releases. It's very useful utility, and the attacker on the version 16 added a line on BCC saying basically like, "send me, by the way, all the emails on BCC line to me."

</details>

**演讲者**：所以这是非常典型的软件供应链验证课题。不过我要强调的是，千万不要仅仅停留在供应链代码审计上，一定要实施延迟引入策略（Delay Ingest）。不要在第零天（Day Zero）盲目引入每一个新发布的依赖包，不妨让它沉淀一到两周之后再考虑纳入依赖。同时，你必须搭配确定性调用中介、最小权限工具以及严密的出站网络管控。

<details>
<summary>Original English</summary>

**Speaker**: Okay. So this is kind of a classic supply chain verification. But I would say like, don't just do supply chain verification. Do delay ingest. Don't ingest every package on day zero. Ingest it maybe in a week or two. You want a deterministic invocation broker, least-privilege tools, egress controls.

</details>

### 纵深防御总结与今日优先行动项

**演讲者**：好了，让我们做个整体回顾。我们今天系统探讨了针对 Agentic AI 的纵深防御体系（Defense in Depth），这就是属于你们的安全工具箱。你们必须确保具备六大核心支柱：身份与信任、提示词与输入防御、工具与动作治理、执行隔离、数据保护，以及治理与可观测性。正如我前面所比喻的，这就像是吃蔬菜虽然苦口却必不可少。那么，这就是为大家准备的安全“蔬菜清单”：

<details>
<summary>Original English</summary>

**Speaker**: All right. So let's recap. We have been talking about defense in depth for Agentic AI. This is your toolbox. You want to make sure that you have identity and trust, prompt and input defense, tool and action governance, execution isolation, data protection, governance and observability. And as I said, this is kind of like eating your vegetables talk. So here's your vegetables:

</details>

**演讲者**：
- **身份层面**：必须使用短期有效的令牌，每个 Agent 分配独立唯一的身份；
- **输入层面**：外部输入文本绝对不能具备直接执行系统命令的权力；
- **工具层面**：单纯的语法或格式校验绝不等于安全访问控制；
- **隔离层面**：默认拒绝策略必须覆盖一切流量，包括 DNS 查询；
- **数据层面**：每一条查询语句都必须严格校验对应的租户归属；
- **治理层面**：提示词只能用于询问和请求，必须依赖确定性的硬编码逻辑来强制执行规则。

<details>
<summary>Original English</summary>

**Speaker**: 
- Identity needs to be short-lived tokens, one per agent.
- Input: outside text cannot give commands.
- Tools: syntax is not a control.
- Isolation: default deny means everything, including DNS.
- Data: check the tenant on every query.
- Governance: prompts ask, deterministic code enforcers.

</details>

**演讲者**：从今天开始，请大家立刻落实三项核心安全优先级任务：
第一，全面加固并锁定你们的 Agent。严格践行“三选二原则（Rule of Two）”，所有的工具调用都必须经由某种确定性中介代理进行管控，所有高价值动作必须有人工签字确认。
第二，严格执行“一个 Agent 一个身份”。彻底废除所有长期有效的密钥，所有凭据都必须是细粒度受限、短期有效、且绑定受众群体范围（Audience-bound）的令牌。
第三，对运行时环境进行沙箱隔离，并必须强制搭配全方位的默认拒绝出站策略——切记，这必须涵盖 DNS 查询！

<details>
<summary>Original English</summary>

**Speaker**: Three priorities starting today:
1. Lock down your agents. Use the rule of two. Every tool call needs to go through some sort of deterministic broker, and human sign-off for any high-value actions.
2. Second one: one agent, one identity. Kill any long-lived keys. Everything needs to be tightly scoped tokens, short-lived audience-bound tokens.
3. Box the runtime, but pair it up with default deny egress—that means DNS as well.

</details>

<!-- chunk 10/51 -->

### 规范驱动开发与安全要求

**Speaker A**: 确保设置了能够直接阻断操作、而不仅仅是发送告警的预算限制。

最后，我想给大家留下这句话。在座的各位有谁在做规范驱动开发（spec-driven development）吗？好的。请务必确保你们的技术规范中包含了安全要求。这只是一个示例。大家可以在 LinkedIn 上联系我，获取更全面的版本；我还有一个 NotebookLM 播客/笔记，如果你对其中某些概念感到困惑，它能为你做进一步的阐释。所以欢迎在 LinkedIn 上与我交流。快速构建，安全部署。谢谢大家。

<details>
<summary>Original English</summary>

**Speaker A**: Make sure there are budgets that halt, not just alert.

Finally, I will leave you with this. Who does the spec-driven development here? Well, yeah. Okay. Make sure your spec includes security requirements. And this is just a sample. You can ping me on LinkedIn for a more comprehensive one, and I also have a NotebookLM that explains a little more concepts if you are confused about some of them. So please connect on LinkedIn. Build fast. Deploy securely. Thank you.

</details>

### 买方金融机构的长期运行 AI 分析师

**Eji**: 好的，大家好，近来如何？我叫 Eji，是 Quant AI（Compound）的联合创始人。我们为买方金融机构提供 AI 分析师服务，具体而言，我们专注于能够长期自主运行的分析师。你可以将其类比为 Devin 或 Factory 这类面向代码开发领域的自主智能体，而我们做的是将其精准剪裁并定制给买方金融机构。

在开始创业之前，我的前一份职业正是一名投资分析师。我曾在 Coatue 担任了大约三年的副总裁，专门从事中后期私募软件投资。过去我把太多太多的时间耗费在了 Excel、PowerPoint 以及深夜加班制作各种底稿和汇报材料上；因此，我决定离开投资行业，着手打造能够替代我过去那份工作的工具。

<details>
<summary>Original English</summary>

**Eji**: All right. How's everyone doing? My name is Eji. I'm the co-founder of Quant AI. We sell analysts for buyside finance and specifically we specialize in long-running analysts. Think Claude agents that Devin or Factory might do for coding agents, but tailoring that for buyside institutions.

I was previously an analyst in a previous life. I was a vice president at Coatue for about three years specializing in late-stage private software investments. Spent way too much time in Excel, PowerPoint, and late nights doing that type of work, and so decided to split and start building tools to replace my old job.

</details>

### 为什么通用 AI 智能体无法直接适配机构金融？

**Eji**: 现场快速举手表决一下：在过去的一天里，有多少人用过自主智能体工具？好吧，我原本以为举手的人会更多一些，也许大家是太害羞了没有举手。那么，又有多少人认识某位在金融行业工作的分析师，能够把工作完全委托给 AI——也就是完全放手、让 AI 纯自主运行的呢？好的，只有一位，明显少得多了。

如果你去思考一个问题：为什么 AI 智能体会在过去三个月内迎来爆发？在我们团队内部，总结出了三个主要原因。第一，可靠的后台运行智能体。你可以给它分派一个任务，比如预订餐厅或订机票，它能十分可靠地完成。如今，计算机操作（computer use）智能体变得越来越成熟，底层基础模型本身的能力也大幅提升了。“帮我买些花”，甚至更进一步，它会告诉你“我已经替你把花买好了”。最后一点则是系统集成能力。智能体与现有的上下文系统紧密连接在了一起。

然而，所有让这些通用智能体大放异彩的因素，在今天的机构金融场景中却完全无法直接奏效。就拿后台异步任务来说，在日常生活中它可能简单到只是预订一家餐厅；但若放在买方金融语境下，对应的同等任务可能变成了：如何从一个包含海量材料的数据室（Data Room）出发，最终端到端生成一整套完备的投委会（IC）财务模型、演示幻灯片以及投资备忘录。这原本是一个通常需要耗费整整四周时间、经历多轮反复推敲迭代与层层审核的复杂流程，现在要求将其压缩至短短几天之内。

再来看生产力与交互方式：你的董事总经理（Managing Director）绝不会容忍一个在后台失控乱跑、做出一堆莫名其妙的操作、在没有征询并索取人类输入的情况下盲目空耗大量 token 的智能体。最后，谈到至关重要的上下文环境，金融机构的核心资产不仅仅是电子邮件，也不仅仅是日程表。它可能是一个塞满了 15,000 个文件的数据室；也可能是 SharePoint 或 Box 里面沉淀的、该机构在长达 40 年历史中所积累的数以 PB 计的非结构化数据。面对这些极为严苛的现实问题，究竟该如何破局？

<details>
<summary>Original English</summary>

**Eji**: Quick show of hands. How many people in here have used agents in the last day? All right, I expected more hands, but maybe people are too shy to raise them. And how many people know an analyst in finance that fully delegates their work to AI? Like fully hands off running autonomously. All right, one, but a lot fewer.

I think if you think about the question, why did agents take off within the last three months? Internally, we came up with three main answers. The first: reliable background agents. You can delegate a task, book a restaurant, book a flight, and it'll do it reliably. Now, computer use agents have gotten sophisticated. The models themselves have gotten better. "Buy some flowers." Or better yet, "I already bought the flowers for you." And finally, integrations. It's connected to the systems of context.

But all the factors that make it work don't really translate to institutional finance today. If we think about background tasks, something as simple as booking a restaurant, the analog equivalent in buyside finance might be how do you go from a data room to a fully prepared set of IC models, slides, and memos — taking a process that would normally take four weeks, multiple rounds of iteration and review, and compressing that to a few days.

If we think about productivity, your managing director doesn't really want an agent rogue running around doing a bunch of things and burning tokens without them providing and soliciting input. And then finally, if you think about the context that matters, it's not just email. It's not just calendar. It could be a data room with 15,000 files. It could be SharePoint or Box with petabytes of unstructured data the firm has collected in its 40-year history. So how do you deal with these problems?

</details>

### Compound 的三大核心架构设计

**Eji**: 因此，今天演讲的核心目的，就是深入探讨我们 Compound 团队究竟是如何构思并解决这些难题的。我们的目标是打造一个能够与你以及整个项目交易团队（Deal Team）协同作业的长期运行数字化队友。

首先是多人协作（Multiplayer）模式，并将其深度内嵌至日常办公应用中；其次，是攻克如何让海量长时间任务在后台稳定并行并可靠执行的难题——为此，我们实际上完全从零重写了整个 Office 办公套件底层引擎；最后，则是如何管理浩瀚无垠的全量上下文数据，也就是我们刚刚讨论过的、存放在 SharePoint 和 Box 里的数 PB 历史数据资产。接下来我将向大家详细拆解我们针对这些维度的具体技术方案。

<details>
<summary>Original English</summary>

**Eji**: So the purpose of today's talk is to discuss a bit more about how we at Compound have approached the problem of solving a long-running teammate that collaborates with you and the deal team. So that's multiplayer, embedding that into the app. On the other hand, it's solving for how can you run long tasks in parallel in the background, reliably execute them. And so for that, we actually rebuilt Office from scratch. And then finally, it's how do you manage the context of everything? Everything we just discussed, petabytes of data in SharePoint, in Box. And we'll talk a little bit about how we've designed a solution for that.

</details>

### 为什么金融场景必须支持多人协作模式？

**Eji**: 我认为我们首先必须回答的问题是：为什么多人协作（Multiplayer）对于金融行业至关重要？如果你仔细审视一个项目交易团队的具体运作结构与人员分工，就会发现，所有针对投资委员会所需交付的长期关键工作，都绝不可能依赖孤立的单人单点工作流来完成。

反观目前许多机构内部署了 Claude 或 ChatGPT 的实际现状，几乎全都是单人单打独斗模式：员工个人在插件里操作，或者在 Web 网页应用中与 AI 对话并导出成果。但不可避免地，这些人必须与整个团队进行高频协作。现在的真实协作链路是怎样的呢？往往是分析师从工具中下载本地文件，通过邮件附件转发，再上传到 Teams 群聊中征求反馈意见。

我们认为正确的解决路径——也就是 Compound 从一开始就坚持的产品设计理念——是：如何将每一个与该笔交易休戚相关的核心成员，都直接拉进同一个对话沟通线程之中？大家如何能够共同与同一个 AI 智能体对话，从而使该智能体能够无缝共享每个关键负责人在特定工作流下所拥有的完整上下文？

<details>
<summary>Original English</summary>

**Eji**: So the first question we have to ask, I think, is why does multiplayer actually matter for finance? If you look at the anatomy on a deal team, the type of tasks that matter for a long-running investment committee, it doesn't work for single-player siloed workflows. Today, for people who have deployed Claude or ChatGPT in their institutions, it's all single player. People working in a plugin, people working in the web app producing outputs. But invariably those people need to collaborate with their team. And what does that look like? It means downloading the file, uploading it into email, uploading into Teams, asking for feedback.

I think the right way to approach this, and this is the way we've thought about at Compound, is how do you get every person who matters on a deal onto the same thread? How can they all talk to the same agent so that one agent can share the context of everyone who matters for any particular workstream?

</details>

### 基于企业邮件设计类人协同体验

**Eji**: 当我们在思考如何将这种多人协作机制融入金融人员习以为常的业务场景时，我们再次借鉴了个人生活智能体的成功之道。为什么生活类智能体能被大家广泛接受？因为你可以极其自然地通过 iMessage 甚至 WhatsApp 给它发短信。对于 Compound 上的智能体，你创建的每一个智能体都原生内置了一个专属邮箱，因为说到底，在整个机构金融体系中，绝大多数业务工作流最终都是运行在 Outlook 邮件体系之上的。

然而，真正为金融机构构建邮件协同智能体绝非易事。它绝不是简单地给后端挂载一个收件箱那么轻巧。首先，这涉及极为严格的身份认证与访问控制，必须确保进入该邮件会话线程的每一个人都拥有针对该智能体确切的读写权限。在这些金融机构中，数据隐私与合规具有不可妥协的极高优先级，无论你接触哪笔交易，你都始终受制于保密协议（NDA）的严格约束。因此，系统必须百分之百确认该会话线程里的每一个人都有合法资质与该智能体交互。

除身份认证外，你还必须深入思考如何设计出真正符合人类社交直觉的拟人化体验。毕竟，我们的终极目标是打造一位真实的数字化同事。设想一下，如果团队中有多位成员在短时间内接连不断地向同一个邮件线程发送消息，你肯定不希望智能体机械式地连续发送多封确认回执去轰炸整个群组邮箱。相反，你实际上需要在响应机制中主动加入适度的延迟，使其表现得更像一位从容思考的人类队友。因此，在为企业金融打造真正的邮件级智能体时，必须权衡处理诸如此类的大量深层交互决策。

<details>
<summary>Original English</summary>

**Eji**: When we thought about how do we actually bring multiplayer into a familiar context, we looked again towards personal agents. Why did they work so well? Well, you can easily text one in iMessage or you can text one in WhatsApp. So for agents at Compound, every single one you create comes with a built-in inbox because ultimately at the end of the day for institutional finance, most workflows run through Outlook.

Building email agents is actually non-trivial. It's not just as simple as hooking it up with an email inbox. It requires: A, authenticating, making sure everyone part of that thread has read and write access to that agent. Ultimately, at these financial firms, privacy is incredibly important. You're always under NDA no matter what deal you look at. And so, you want to make sure everyone on that thread can actually talk to the agent.

But then, beyond authentication, you also have to think about how do you design a real human-like experience? Because after all, we're trying to create a real teammate. If multiple people email in the same thread in quick succession, you don't want multiple acknowledgements spamming that group. You actually want to bake in some more latency to make it feel more human. And so there are other design decisions when thinking about how to create real email agents for enterprise finance.

</details>

### 现有方案的局限与用 800 万行代码重写 Office

**Eji**: 抛开多人协作不谈，我们很快意识到另一个严峻瓶颈：即便你已经成功汇集并处理了所有关键利益相关者的意图与输入，如果你希望横向扩展任务并发规模、让海量繁重工作并行高效跑通，目前市面上所有现成的开箱即用方案统统无法胜任。

我们曾深度评估过许多方案：包括 Excel、PowerPoint 和 Word 的桌面端原生插件；我们评估过利用计算机视觉操作（Computer Use）虚拟机，试图借此横向扩展能直接在 Excel、PowerPoint 和 Word 原生应用内操作的智能体数量；我们还全面测试了大量现成的文档处理引擎，无论是像 openpyxl 这类开源 Python 工具包，还是市面上能够商业采购的企业级私有引擎。但在面对买方金融的极端复杂性时，没有一个方案能够真正达标。

伴随着代码编写智能体能力的跨越式提升，开发基础软件的综合成本被前所未有地拉低，于是我们做出了一个决定：直接完全从零开始重写属于我们自己的 Office 套件。就像任何一位出色的 AI 工程师会做的那样，我们让智能体在海量循环迭代中全速运行，累计消耗了超过 1.5 万亿的输入与输出 token，最终生成了超过 800 万行代码，从底层彻底重写了整个 Office。

下面我可以向大家粗略分享一下我们的工程实现路径：其实本质上就像是给智能体设定一个明确的目标函数（Objective Function）——即在每一个细节与渲染层面上百分之百极致复刻 Office 的保真度，然后让智能体全自动化跑起来。

以具体实施为例，我们最开始基于某个开源实现方案起步，全力攻坚如何能够完美无瑕地重新构建 Excel 的核心机制。我们直接将微软官方的 Office 套件作为评判终极真理的“先知”（Oracle），通过海量基准测试循环不断校验：这些测试文件既包含了从公网抓取的大量真实世界复杂财报与业务底稿语料，也涵盖了我们在内部针对金融极限场景深度构造的测试集。经过了 80 万行 Rust 代码的重构淬炼之后，我们最终拥有了一套在性能上远胜原生 Excel、且能做到像素级与逻辑级 1:1 完美复刻的全新核心产品。

<details>
<summary>Original English</summary>

**Eji**: But multiplayer aside, we realized even after you solicit the input of everyone who matters, if you wanted to scale up the number of tasks and run them all in parallel, existing off-the-shelf solutions simply don't cut it. We evaluated a lot: the desktop plugins of Excel, PowerPoint, and Word. We evaluated computer use virtual machines to try to scale up the number of agents that could work in Excel, PowerPoint, and Word natively. And we also evaluated a ton of off-the-shelf engines, whether those are open-source packages like openpyxl, or commercial engines that are available for purchase. None of them really cut it for what we were trying to look at.

And with coding agents dramatically improving and bringing the cost of software down, we decided to just build our own Office from scratch. And like a great AI engineer would, we ran agents in many loops, spent 1.5 trillion input/output tokens and over 8 million lines of code to rewrite Office from scratch. And I'll walk through a little bit of how we approached it, but it's as simple as pointing agents at an objective function, which is recreate Office in full fidelity, and then letting it run.

So take an example. We started with an open-source solution. We decided how can you recreate this perfectly for Excel. Use Office as an oracle and just run loops benchmarking it on real files from both real-world corpus that we grabbed online and also ones that internally we created. And 800,000 lines of Rust later, we had a performant — much more performant compared to Excel — one-for-one replica of the product.

</details>

### 无头引擎的性能飞跃与 1:1 格式保真

**Eji**: 凭借这一底层技术突破，我们不仅攻克了 Excel，还将这项能力成功复制到了 PowerPoint 与 Word 之上。我们在每一个微软办公核心套件上都运行了这样严密的强化学习与代码验证循环，最终实现了高度保真的全面重构。大家今天就可以直接访问 getcompound.ai 亲自上手体验。

整个系统完全遵循着相同的工程方法论：利用智能体在闭环中运行，并以原生 Office 应用程序作为评测裁判（Judge），底层基于高性能 Rust 语言编写。因此，你在 Compound 平台内部所看到的一切排版、公式与计算结果，与你最终将文件下载导出到本地 Office 打开时所见到的完全一致。我们必须做到极致的 1:1 严格对齐，因为归根结底，这类顶级金融机构唯一信任的，就是他们能够下载到本地并能直接发送给外部客户与合伙人的真实文件。

现在，让我们进一步探讨性能维度的巨大差异：为什么相比于在虚拟机（VM）里跑 GUI 界面，这种纯无头（headless）的原生文档引擎具备如此压倒性的巨大优势呢？

<details>
<summary>Original English</summary>

**Eji**: With this, we're actually able to do that for not only Excel, but also PowerPoint and Word, right? So, we ran loops across every single one of these products, and we have faithful recreations. You can try it for yourself today at getcompound.ai. And it's the same method: loop agents against Office as a judge using Rust. So, what you see in Compound is what you see when you download to Office. We needed one-for-one parity because at the end of the day these firms only trust what they can download and what they can send.

Now let's talk about performance. Why is a headless engine so much better compared to using a VM or...

</details>

<!-- chunk 11/51 -->

### 无头引擎与自研 Office 的性能与协作优势

**Speaker A**: 使用桌面端 Excel 会怎么样呢？桌面端的 Excel、PowerPoint 或 Word 都会受到本地 CPU 的严格限制。而借助无头引擎（headless engines），你可以高度并行地处理任务，速度要快得多。你可以在极短的时间内构建出极其复杂的财务模型，也可以更快地对一个 20MB 大小的 Excel 文件完成重算。

分析师对智能体（Agent）所期望交付的每一项具体工作，其核心预期都是以极快的速度、极低的成本达到人类专家的交付品质。要做到这一点，你必须拥有无头引擎。如果你试图直接基于原生的桌面端 Excel 和 PowerPoint 去做横向扩展，我认为完全走错了方向。

<details>
<summary>Original English</summary>

**Speaker A**: using desktop Excel? Well, desktop Excel or PowerPoint or Word is bound to CPU. With headless engines, you can do tasks in parallel much much faster. You can build out a complex model in a much shorter amount of time. You can recalculate 20 megabyte excels faster. So every single piece of work a analyst would expect an agent to do because again their expectation is quality of a human at much lower speed and much lower cost. You have to have a headless engine to do this. If you tried to scale this up with Excel and PowerPoint, I think you'd be going down the wrong path.

</details>

**Speaker A**: 但这还不仅仅关乎性能。自主掌控底层编辑器，实际上能让你打造出丰富得多的产品体验，使你能够以远胜于其他产品的方式与智能体进行异步协作。

从我过去的咨询顾问生涯以及两段编码经历中，我对“什么才是一份优秀幻灯片”的所有经验积累与格式规范，都被注入到了智能体当中，变成可以在每处格式细节上添加的批注。

这套体系同样适用于多人协同（multiplayer）。同一个团队中的多名成员可以基于我们搭建的多人协作底层架构，在文档中直接发表批注。对于一个五人团队而言，你们可以在一个下午就快速过完一份长达 100 页的演示文稿，而不需要大家干坐在会议室里花上好几个星期反复修改。

最后，从自研引擎的角度来看，它不仅能准确写出内容，你还可以进行精细解析，检查某个单元格是否显示为特定颜色、是否应用了特定字体。如果你试图使用微软原生的接口，你就会受限于微软所提供的那套极其有限的能力。而拥有自己的引擎后，你就完整掌控了“写入、渲染、校验与修复”（write, render, check, and fix）的闭环，从而能够面向用户实现产出结果的极速迭代。

<details>
<summary>Original English</summary>

**Speaker A**: But it's not just about performance. Owning the editor actually allows you to create a much richer product experience that allows you to work and collaborate with agents asynchronously much better than you can with other products. So this entropped in comments for every single piece of formatting for my consulting days, for my code two days, all the learnings I had on what makes a great slide, I imparted with the agent.

This can also work for multiplayer. You can have multiple people part of the same team using the same multiplayer infrastructure we set up dropping in comments. So for a team of five, you can rip through a 100page deck in an afternoon rather than sitting in a room revising it for multiple weeks.

Finally, with respect to building your own, it als writes the right thing and maybe you do some parsing to see a cell is a particular color or has a particular font. If you try to use Microsoft's own interface, you're going to be limited by what Microsoft provides you, which is admittedly very little. So with an own engine, you actually own the write, render, check, and fix loop. So you can rapidly iterate on the output for the user.

</details>

### 买方机构的数据挑战：广度与深度的双重破局

**Speaker A**: 今天除了多人协同以及构建自研 Office 之外，我想探讨的最后一个话题，就是如何应对这些金融机构所拥有的复杂上下文。

对于买方机构（buy-side firms）来说，他们面对的业务场景往往兼具数据的广度与深度。有时你面对的数据室（data room）里包含超过 15,000 个文件，而其中的单个文件就可能远超 20MB。金融圈的人整天都在抱怨：“我手里有一个 30MB 大小的 Excel 模型，每次重新计算都要花费五分钟，因为里面有两百万个公式，还有五个敏感性分析表，每次都必须全局重新计算一遍。”

那么你该如何解决这个问题？

针对数据广度，我认为同样可以借鉴软件工程的做法，将智能体集群（agent swarms）应用到海量文件中。除非是针对某些极其特殊的垂直场景，否则你再也不需要把所有文件都无脑索引进向量数据库（Vector DB）里了。更理想的做法其实是让编码类智能体直接通过类似 grep 或其他机制来读取检索文件，由一个主导智能体（lead agent）对文件目录内容进行切片分配，接着让成群的子智能体分头分析并汇总洞察，随后在一个循环机制中不断迭代，直到满足最终输出要求。

不仅如此，通过这一流程，你还能把每一个分析结论严格锚定并引注在原始文档上，确保屏幕上展示给分析师的每一笔数据都有据可循、绝对可信。

<details>
<summary>Original English</summary>

**Speaker A**: So the last thing I sort of want to discuss today beyond multiplayer and building our own office is how to deal with the context that these firms have. For firms on the buy side, they deal with situations where it crosses both breadth and depth of data. You may have situations where you have a data room over 15,000 files and then files in that data room might be well over 20 megabytes. People in finance complain all the time, hey, I have an Excel model that's 30 megabytes. takes five minutes to recalculate because we have two million formulas in five sensitivity tables that need to recalculate every single time.

So how do you deal with this? Well, for breadth, I think again we take a look at a page out of the coding book and apply agent swarms to the large number of files. No longer do you have to index everything in a vector DB unless for it's for a very specific use case. It's actually much preferable to use coding agents to read files either through GRP or through some other methodology and then have a lead agent slice the contents of the file directory and then have swarms of agents come back to you with insights and then you iterate that in a loop until you're satisfied with the output required.

Furthermore, through this process, you're actually able to ground every single finding in citations in the source document so that you know exactly what you show on the screen is linked to some number that the analyst can trust.

</details>

**Speaker A**: 再来看看数据的深度——就以那个 30MB 的工作簿为例，你到底怎样才能更精准地处理它？

在当前的环境下，如果你直接使用现成的 ChatGPT 或 Claude 来处理那个 30MB 的模型，它们通常会去编写 Python 脚本，调用像 openpyxl 这样的开源第三方包。这种方式不仅昂贵而且极其缓慢，因为它必须把整个模型的每一处上下文全都在代码中打印输出，再喂给大模型去读取理解。

但由于我们为 Excel 深度自研了专属引擎，我们不仅能做到更高的准确率，而且处理速度快得多、成本低得多。因为引擎在完成底层处理后，会以一种极易于大模型阅读和理解的格式将其呈现出来。这也意味着我们能够向智能体暴露更丰富、更强大的 API 与工具集合，进而大幅提升对大型复杂模型的处理效率。

<details>
<summary>Original English</summary>

**Speaker A**: If we think about the depth of data, right, take that 30 megabyte workbook. How can you actually process this more accurately? In today's world, if you were to just use chatbt or claude off the shelf to process that 30 megabyte model, it would write code. It would use open source packages like open pixel. It would be expensive and slow because it's printing out every single piece of context about that model in code for the model to read.

But because we've developed our own engine for Excel, we're actually not only more accurate, but a lot faster and cheaper because the engine processes it and then lays it out in a very easy to read and easy to process format for the model. This means we can expose a much richer set of APIs and a much richer set of tools for the agent to work over and that allows us to process these models in a much faster manner.

</details>

### 从 Copilot 走向 Autopilot：释放投资判断力

**Speaker A**: 倘若我们退一步思考：构建这些全套上下文的终极目标究竟是什么？归根结底，我们希望把专业人士从繁琐的找文件、反复提示大模型“该怎么做”的低效消耗中彻底解脱出来。

相反，他们的精力应当聚焦在交易决策本身、倾注其核心商业判断力；他们应该专注于定制、训练智能体，并把它们分派到交易流程的每一个关键环节。

因此，整套体系形成了清晰的层级架构：最底层是开箱即用的连接器，打通 SharePoint 或 Outlook 等各类数据源；中间层是基于核心原始文档严格核验与引注的分析结论；最顶层则是深度内嵌机构的专属偏好与组织专有认知——如何构建一个财务模型？排版应当呈现怎样的视觉规范？这些在每家投资机构之间都各不相同。

这样一来，专业人士就可以将绝大部分时间用于进行商业价值判断，去真正思考“这笔交易到底是不是一笔好买卖”，而不是整天纠结“所有数字是否完全勾稽一致”、“模型格式对不对”、“会不会因为排版风格不符而被副总裁（VP）训斥”。

<details>
<summary>Original English</summary>

**Speaker A**: So if we sort of take a step back and think about okay what is all of this context built for the end of the day what we want to do is prevent people from spending time finding files from reminding the model this is how to do things. Instead they should be focused on imparting their judgment on the deal process. They should be focused on tailoring training agents and deploying them on every part of the deal flow.

And so it goes from the bottom level connected sources offtheshelf you know connectors to SharePoint or Outlook to the cited findings grounded in the sources that matter and then finally embedding in the preferences company knowledge that matters. How do you do a model? How should it look? Which differs by every single firm? So that for humans they spend most of their time imparting judgment. They spend most of time thinking about is this actually a good deal? Not did all the numbers tie? Does the model look right? Will my VP yell at me because it looks a different way.

</details>

**Speaker A**: （屏幕提示：Cursor 需要更新。）

如果退一步审视当前有哪些类型的任务已经进入了“自动驾驶”（autopilot）阶段，又有 assignment 还停留在“副驾驶”（copilot）阶段：客观来说，目前已经有相当一部分金融任务可以通过现成工具完成得不错了。比如对标公司财务数据铺开（spreading comps），正如 ChatGPT 的金融业务负责人在前面演讲中所提到的，他们现在已经推出了专门针对此类场景的成熟功能。

但我认为，还有大量长周期、复杂的深度任务是现有方案完全无法胜任的：比如，如何能够一气呵成地自动起草出一份长达 50 页的投资委员会（IC）汇报材料？如何让智能体为私募股权（PE）或对冲基金的专业投资人员分毫不差地搭建出他们心目中的复杂模型？我认为这些任务在目前的开箱即用工具下，依然停留在 Copilot 的辅助范畴内——大家还必须深度参与每一个中间步骤，不敢彻底放手。

然而，借助我们今天打造的工具，我认为我们正在大幅拓宽 Autopilot 能够在金融机构中接管业务的边界。专业人员不再只是把工具作为 Excel 插件来用，在整个过程中步步人工搀扶；而是可以真正开始全面委派工作，并对人工智能所能企及的上限抱有更大的野心。

就像程序员最初只是把 AI 当作补全代码行或生成单个文件的简单 Copilot，但随后他们开始委派远比这宏大得多的开发任务，并意识到只要拥有足够完备的自动化校验与测试体系，或许完全可以直接“凭借直觉”（vibe it）信任模型编写出的全部代码。

我认为，借助我们今天已经构建的基础设施以及面向未来的规划，这些正是金融领域在迈向那个终局之前必须先彻底解决的核心问题。分析师和整个交易团队该如何对 AI 拥有更大的野心？他们如何才能直接把整个数据室的文件丢给系统，安心信任生成的每一份产出，并将工作吞吐量放大十倍，从而覆盖更多潜在交易、全面拓宽核心关注的投资视野？

总而言之，企业级智能体必然会全面渗透金融领域。我坚信我们正处于技术采纳曲线的关键拐点上，人们正在变得越来越有雄心，逐步从 Copilot 迈向 Autopilot。这就是我们在 Compound 公司所探索和践行的路径。

如果你就职于金融机构，并且希望借助部署我们的智能体来深度驱动交易流程，欢迎随时联系我们；如果你是一名工程师，对我们的技术路线感兴趣、想要交流探讨想法，也欢迎在线联系我，或者等下在会场找我面对面交流。非常感谢大家！

<details>
<summary>Original English</summary>

**Speaker A**: So, oh, cursor needs to update. If we take a step back and think about the type of tasks that currently are on autopilot um versus what are on copilot, I would say there's already several finance tasks. You can do pretty well with off-the-shelf tools. Spreading comps, as the chat GBT head of finance mentioned earlier, they have now their own products for this. But I think there are a lot of longer running tasks that are not capable with existing solutions.

How do you draft a 50-page IC presentation off the cuff? How do you get agents to build out a model exactly the way you want it for a private equity professional or a hedge fund professional? I think those are tasks that with off-the-shelf tools still exist as co as sort of within the co-pilot realm. People want to be embedded deeply in that process without letting go.

But with some of the tools we've built today, I think we're able to expand the aperture for which autopilot can take over in finance firms. So rather than just using tools embedded in Excel as plugins, handholding along the way, you can start delegating. You can start becoming more ambitious about what AI is capable of. using code as a simple co-pilot to generate the next file or the next line of code. But they started delegating far more ambitious tasks. They started realizing maybe I can just truly vibe it. If I have sufficient checks, if I have sufficient tests, maybe I can just trust all the code it writes.

I think with some of the tooling we've built today along with what we're planning in the future, these are the type of problems you have to solve before you get to that point for finance. How can analysts, how can the entire deal team become more ambitious with AI? How can they just drop in a data room and decide, okay, I'm going to trust every single one of the outputs and then let's do that 10fold so we can see more deals so we can expand the aperture of what matters.

So to conclude, enterprise agents are certainly coming to finance. I strongly believe we're at an inflection point in the adoption curve and that people are slowly becoming more ambitious and they're moving away from co-pilots to autopilots. And so this was sort of how we've approached it here at Compound. If you work at a firm and you're interested in deploying our agents to drive more of your deal work, please reach out. Or if you're an engineer and you're curious about talking about our approach and sharing ideas, please either reach out online or I'll be around if you want to find me. Thanks so much.

</details>

### 新演讲开场：并非所有 GPU 的部署方式都相同

**Oliver Kenan**: 并非所有 GPU 的部署方式都是相同的。非常感谢大家今天抽出时间来到现场。

我是 Oliver Kenan，来自 SemiAnalysis 的一名研究分析师。

时间和注意力是我们在座每一个人所拥有的最宝贵的资产——当然，除非你恰好是 OpenAI 或 Anthropic 的早期投资人。

闲话少说，让我们直接切入正题。并非所有 GPU 的部署架构都是一样的；一块 GPU 能够发挥出的真实效能，终究受限于它所在的系统与部署水准……

<details>
<summary>Original English</summary>

**Oliver Kenan**: Uh, not all GPUs are deployed the same. Uh, thank you everyone for taking the time to be here today. My name is Oliver Kenan. I'm a research analyst at semi analysis. Um, time and attention are the most valuable things any of us have. Uh, unless of course you're an early stage investor in open open AI or anthropic. Um, with that uh let's get into it. Uh not all GPUs are deployed the same. A GPU falls to the level of the

</details>

<!-- chunk 12/51 -->

### 算力商品市场的成本曲线与运营能力

**Speaker**: 购买硬件只是赋予了你潜在的能力，而运营能力才真正决定了你实际能够交付多少有用的工作成果。这引出了我今天尝试与各位共同探讨并回答的核心问题：究竟谁能以最低的成本，生产出你所需的智能？

<details>
<summary>Original English</summary>

**Speaker**: operator. Buying hardware gives you potential. Operating capability is what determines how much useful work you actually are able to deliver. That leads us to the question I will attempt to answer with all of you today. Who can produce the intelligence you need at the lowest cost?

</details>

**Speaker**: 成本至关重要。在今天的演讲中，我想向大家展示运营能力为什么以及如何改变这一成本，以及它在算力这一大宗商品市场中为何如此关键。那么，在大宗商品市场中，什么才是最重要的？很多科技投资者或技术专家可能对这个分析框架并不熟悉，因此这里先做个简短的速成介绍。

<details>
<summary>Original English</summary>

**Speaker**: Cost matters. In today's presentation I want to show you guys why and how operating capability changes that cost and why it matters in the commodity market that is compute. What matters in a commodity market? A lot of tech investors or technologists may not be familiar with this framework. So little crash course.

</details>

**Speaker**: 在大宗商品市场中，各生产商竞相交付性能相当的产出。更低的生产成本能在价格下跌时提供更大的竞争缓冲空间。这正是成本曲线所展现的本质：所有生产商根据交付相同可用工作量所耗费的成本依次排列。

<details>
<summary>Original English</summary>

**Speaker**: In a commodity market producers compete to deliver comparable output. A lower production cost gives more room to compete when prices fall. That's what a cost curve shows: producers lined up by what they spend to deliver the same usable work.

</details>

### 从 GPU 机时到可用智能：衡量产出的真实指标

**Speaker**: 对我们而言，智能才是我们所关心的最终经济产出。未来，我们的终极北极星指标将是：在满足既定质量要求的前提下，成功完成单项任务所需支付的价格。遗憾的是，我们目前还没完全走到那一步，因为这很难进行统一标准化。

<details>
<summary>Original English</summary>

**Speaker**: For us, intelligence is the economic output we care about. Eventually, our northstar metric will be price per successfully completed task at the required quality. Unfortunately, we're not quite there yet. That's a pretty hard thing to standardize.

</details>

**Speaker**: 在现阶段，每 Token 价格是一个非常实用有效的代理指标，尤其是在工作负载与质量要求相当的情况下。相比于金融界朋友们经常听到的每 GPU 小时租赁单价，每 Token 价格能让我们更贴近实际交付的最终产出。在我们看来，GPU 机时只是一种衡量投入的成本指标，而非产出指标。这本质上是投入成本与最终产品定价之间的区别，也就是客户为了完成工作所实际承担的成本。

<details>
<summary>Original English</summary>

**Speaker**: Today price per token is a useful practical proxy especially for comparable workloads and quality requirements and gets us closer to delivered output, much closer than the often quoted—all you finance bros out here will have heard this—GPU dollar per hour price, or as we view it, a cost. We view GPU hours as a measure of input, not output; the cost versus price distinction, customer's cost of doing the work. GPU hours are the output [input].

</details>

**Speaker**: 在这张幻灯片上，我们可以直观看到创造出可用智能所需要的各项投入要素。我们首先从底层硬件与电力基础设施（即 GPU 算力）切入。在本次演讲中，软件与运维可以被视为施加在前两项核心要素之上的倍增器，而最终形成的产品则是切实可用的智能。

<details>
<summary>Original English</summary>

**Speaker**: On this slide, we can visualize the inputs needed to create useful intelligence. We start with hardware and electricity GPUs. For this presentation software and operations can be thought of as a multiplier on those first two inputs with the end product being useful intelligence.

</details>

### 运营者的角色与推理服务栈性能差异

**Speaker**: 运营者正是负责选型并落地部署模型推理服务软件、并确保业务请求在系统中高效流转的关键角色。机器硬件也许随时处于可用状态，但你依然必须依赖专人去促使它们吐出客户真正能够使用的有效响应。

<details>
<summary>Original English</summary>

**Speaker**: The operator is who chooses and implements the software that serves the model and keeps requests moving through the system. The machines might be available but you still need someone to make them deliver responses customers can actually use.

</details>

**Speaker**: 真正核心的是你能获得多少有效工作量，以及它是否契合指定任务的各项业务指标。即便采用完全相同型号的芯片，其最终的工作转化效率也可能大相径庭。接下来让我们通过一个实测数据案例来审视这一点。

<details>
<summary>Original English</summary>

**Speaker**: What matters is how much useful work you get and whether it meets your requirements for the specified task. The conversion can differ with the same kind of chip. Let's look at that in the measured example.

</details>

**Speaker**: 这是一个来自我们公开的 InferenceX 推理计算器的具体案例，大家可以在 semianalysis.com 上自行查验。在这两个估算场景中，均采用 B200 GPU 运行同一个模型，输入约为 8,000 Token，输出约为 1,000 Token，这是一个相当标准的比例，设定面向单用户的 P50 交互延迟目标为每秒输出 100 Token。

<details>
<summary>Original English</summary>

**Speaker**: Here's a concrete example from our InferenceX public InferenceX calculator. You guys can all check it out semi analysis.com. Both estimates use B200 GPUs serving the same model with roughly 8,000 input tokens and 1,000 output tokens, a pretty standard ratio. The P50 target is 100 output tokens per second for each user.

</details>

**Speaker**: 所谓服务栈，是指处理模型生成响应的底层软件架构。在 P90 负载场景下，其中一个服务栈能提供约 200 Token/秒的生成输出，而另一个优化后的服务栈则能达到约 300 Token/秒。这是一个巨大的差距，而它完全归结于软件底层配置以及并发运行的请求数量——这些全部由运营者的工程决策所决定。

<details>
<summary>Original English</summary>

**Speaker**: The serving stack is the software handling the model's responses. In the P90 scenario, one of these stacks gives about 200 generated output tokens per second while the other one gives about 300. That's a big difference and comes down to software settings and number of requests running. All choices made by the operator.

</details>

**Speaker**: 相同的硬件芯片，相同的目标交互性指标，却产生了大约 50% 的产出增量，这一差距非同寻常。那么，这对采购方的最终账单究竟意味着什么？对客户而言，这些智能产出到底耗费了多少成本？

<details>
<summary>Original English</summary>

**Speaker**: Same chip, same target interactivity, about 50% more output. That's a lot. So, what does that mean for the buyer's bill? What does that intelligence actually cost the customer?

</details>

**Speaker**: 在本案例中，我们假设两种部署方案的每小时算力租赁账单金额完全相同，且均能满足业务指标。但在产出高出约 1.5 倍的情况下，你为每个合格 Token 所分摊的租赁花费成比例地显著降低。换句话说，同样的机时花费为你买来了更多实际可用且有效的产出。

<details>
<summary>Original English</summary>

**Speaker**: For this example, let's assume the hourly bill is the same for both deployments and both meet your requirements. At roughly one and a half times the output, your rental spend per acceptable token is proportionally lower. That is to say, the hour buys you more usable and useful output.

</details>

### 可用智能的标准与生产环境运维安全

**Speaker**: 究竟什么才算作“可用智能”？可用智能必须能够圆满完成你雇佣它去执行的工作，逻辑其实就这么直接朴素。输出的答案质量必须足以应对任务，返回延迟必须足够低，且服务在你需要时必须具备高可用性。此外，你的数据信息还必须严格保留在预设的权限隔离边界内——换言之，系统必须具备绝对的安全性。

<details>
<summary>Original English</summary>

**Speaker**: What counts as useful intelligence? Useful intelligence has to do [what you] hired it to do. Pretty simple, right? The answer needs to be good enough for the task, arrive quickly enough, and be available when you need it. Your information also needs to stay within the access boundaries you've agreed upon. Aka, it needs to be secure.

</details>

**Speaker**: 这是一个常被忽视的要求，芯片本身的基准跑分并不能体现出安全能力，但它对于算力芯片是否真正具备可用性与实用价值而言却是生死攸关的。

<details>
<summary>Original English</summary>

**Speaker**: This is an overlooked requirement that is not captured in a chip's performance metrics, but it is essential for a chip to be usable and useful.

</details>

**Speaker**: 在我们此前公开的安全研究中，我们曾发现某些监控权限存在漏洞，导致其他租户的日志与监控指标被暴露无遗。这是一个令人扼腕但屡见不鲜的典型案例：底层 GPU 确实运行极快——在我提及的案例中甚至算力极度惊人，但这反而让结果更显悲哀——由于缺乏安全隔离，整套服务依然在生产环境中遭遇了灾难性的溃败。

<details>
<summary>Original English</summary>

**Speaker**: In our published security work, we found monitoring access that exposed another customer's logs and metrics. This is a case and an unfortunately common one at that where the GPUs were fast. In the case I'm referencing really really fast which makes the whole thing sadder. And the service still failed horrifically.

</details>

**Speaker**: 保障集群的安全性需要持续不断的运营维护，这与兑现宣称的算力性能一样重要。在绝大多数情况下，承担这一职责的正是运营者。必须有人在生产环境中确保整套系统的稳健运转。

<details>
<summary>Original English</summary>

**Speaker**: Ensuring cluster security takes ongoing work just as delivering the promised performance does. In most cases it is the operator that owns that responsibility. Someone has to make the system work in production.

</details>

**Speaker**: 假设现在出现了一个速度更快的推理服务栈更新。必须有人在实际客户的工作负载上对其进行回归验证，检查其生成结果是否依然满足既定质量，随后审慎决定部署的时间、节点与灰度策略。这意味着必须校验真实响应质量、进行压力测试，并保留完善的回滚方案，以防新版本上线后突发故障。

<details>
<summary>Original English</summary>

**Speaker**: Suppose a faster serving update becomes available. Someone has to test it on the customer's workload, check whether the output still meets the requirements, and then decide when, where, and how to deploy it. That means checking the actual responses, testing it under load, and keeping a way to return to previous version if the update causes problems once it's deployed.

</details>

**Speaker**: 系统上线后，还必须有人持续负责维护并在发生异常时实时响应。这项运维工作可能由你的基础设施供应商承担，也可能由你自己的内部团队负责，或者由双方共同协同。但无论如何，你都必须清晰知晓谁在为此兜底，以及他们是否真正具备履职能力。

<details>
<summary>Original English</summary>

**Speaker**: Once it is deployed, someone has to maintain it and respond when issues come up. That work may sit with your provider, your own team, or both. Irregardless, you need to know who's responsible and whether they can actually do it.

</details>

### 托管集群评估体系与自建分摊逻辑

**Speaker**: 针对数百个托管 GPU 集群的运营能力评估体系目前正在持续扩充，如果希望参与 ClusterMAX 4.0 评测，欢迎随时联系我们。我们全面考量资源交付部署、运行可靠性、监控完备性以及安全合规能力。实测验证、工程文档以及真实客户反馈，帮助我们深入洞察该服务在常态运作以及单机突发宕机时的端到端弹性表现。

<details>
<summary>Original English</summary>

**Speaker**: capability on managed GPU clusters couple couple hundred growing. Please reach out if you want to be on ClusterMAX 4.0. We look at provisioning, reliability, monitoring, and security. Hands-on testing, documentation, and customers feedback help us understand how the service runs not just on a good day but also when a machine fails.

</details>

**Speaker**: 我想借此机会再次强调：ClusterMAX 评级仅适用于全托管集群服务。这与裸金属裸机租赁存在本质区别。在裸金属方案中，绝大部分的系统运维工作通常转嫁由客户自行承担。因此，仅凭服务商在托管产品上的评级，并不能直接等同于覆盖其售卖的所有产品形态。

<details>
<summary>Original English</summary>

**Speaker**: I want to take the chance to reiterate that ClusterMAX ratings apply to managed clusters. Different from bare metal, very different. With bare metal, more operating work usually sits with the customer. Applying a managed service rating there does not automatically cover every product a provider sells.

</details>

**Speaker**: 这些评级梯队是相对于行业同行而言的。定价与货源可用性同样是本项评估中的关键维度。虽然这类指标并不直接测算 Token 产出速率，但它们对于全盘评估究竟谁能切实交付合格服务至关重要。

<details>
<summary>Original English</summary>

**Speaker**: The tiers are relative to peers. Little bit of a tongue twister. I nailed it. Pretty happy with that. And pricing and availability are also important factors in this assessment. These are metrics that do not directly measure token output, but are incredibly important, obviously very important. Assessment helps us understand who can deliver.

</details>

**Speaker**: 现在我们可以进入下一个核心问题：生产可用智能的实际成本究竟是多少？让我们先从算力账单以及生产商必须承担的其他各项开支说起。

<details>
<summary>Original English</summary>

**Speaker**: Now we can move on to the next question. What does it actually cost to produce useful intelligence? Let's start with a compute bill and other costs that producer still has to cover.

</details>

**Speaker**: 租赁价格与生产成本是两个完全不同的概念。在我们列举的 GPU 供应商模型中，底层 GPU 服务商出租硬件机时；推理生产商采购这些机时并对外销售模型响应。这份租赁账单构成了 GPU 服务商的营收，同时也是推理生产商的直接原材料投入成本。GPU 资产持有方负责承担设备折旧、电力能源、机房空间及机房运维支持；而推理生产商的全部运营成本，则包括该租赁费加上其在租赁费之外支付的软件研发、工程人员及其他配套第三方服务费用。

<details>
<summary>Original English</summary>

**Speaker**: Rental price and production cost are different. In our example GPU provider, the GPU provider rents out hours. The inference producer buys those hours and sells responses. The rental bill is revenue to the provider and an input cost to the inference producer. The GPU owner pays for the equipment, power, space, and support. The inference producers's full cost includes rent plus whatever software staff and other services it pays for beyond that rental.

</details>

**Speaker**: 如果推理生产商选择全资自持硬件设备，我们则需将初始设备投资在其使用生命周期内进行折旧分摊，并计入持续的运营开销。生产商的对外报价与其内部实际支出是两个截然独立的数字。要透视可用智能的真实生产成本，我们必须弄清这一系列开销到底实际转化出了多少有效成果。

<details>
<summary>Original English</summary>

**Speaker**: If the inference producer owns its own IT equipment instead, we spread the equipment investment over its working life and add running costs. What the producer charges and what it spends are separate numbers. To understand the cost of useful intelligence, we need to know how much useful work the spending actually produces.

</details>

### 持续运营红利与商品化相对优势

**Speaker**: 更卓越的工程运维能力能够直接打下可用智能的生产成本。前文 B200 的案例清晰揭示了有效产出规模为何举足轻重：在相同的租赁机时开销下，输出更多合格的模型响应，能够将推理生产商的租金支出摊薄到更多的有效工作量上。对于自持 GPU 资产的生产商而言，同样的逻辑也能将硬件重资产投入与日常运维开销分摊到更大的产出规模之中。

<details>
<summary>Original English</summary>

**Speaker**: Better operations lowers that cost of useful intelligence. The B200 comparison showed why the amount of output matters. More acceptable responses from the same paid hours can spread the inference producers rental expense over more useful work. For a producer that owns its GPUs, the same logic spreads the equipment investment and running costs over more output.

</details>

**Speaker**: 统计出在同一统计周期内交付该项服务所需耗费的全部支出，再除以客户实际能够使用的合格产出总量，我们便能推导出在对标工作负载下的每个合格 Token 的单位成本。

<details>
<summary>Original English</summary>

**Speaker**: Count all the spending needed to deliver the service over the same period, then divide by the output customers can actually use. That gives us cost per acceptable token for a comparable workload.

</details>

**Speaker**: 打造更优异的运维体系同样离不开资金与资源投入。评估测试新更新、安全推进灰度部署以及维系长期高可用运行，无一不需要投入高素质人才与真金白银。新增的有效产出必须足以抵消并证明这部分额外支出的合理性。

<details>
<summary>Original English</summary>

**Speaker**: Better operations also require investment. Testing an update, deploying it safely, and keeping it working take people and money. The extra output has to justify the extra spending.

</details>

**Speaker**: 随着软件架构和工作负载的快速演进，若团队能够将这套工程优化能力沉淀为可复用的日常流程，这种成本优势便能长期维系。单靠某一次漂亮的 Benchmark 测试成绩并不能奠定胜局，你必须在生产环境中的每一天持续证明自己。即便每一套新业务负载依然需要单独审慎调优，但根据我们的长期观察，一套具备高复用性的运营管理体系，足以支撑起持久的成本优势，并最终转化为显著的对外终端定价优势。

<details>
<summary>Original English</summary>

**Speaker**: This advantage can persist when a team repeats that work as software and workloads change. But one good benchmark doesn't establish it. You have to earn it every single day. Each new workload still needs checking, but a repeatable operating process from what we've observed can support a lasting cost advantage and a price advantage too.

</details>

**Speaker**: 尽管你在全力以赴持续迭代，但竞争对手也绝非止步不前。你在成本曲线上的站位永远是相对的。在我们展示的所有幻灯片中，这张图最直观地体现了引入大宗商品市场分析框架的必要性：你在成本曲线上的真实竞争身位，本质上取决于你的竞争对手能够交付什么，而不仅取决于你自己……

<details>
<summary>Original English</summary>

**Speaker**: Even if you do keep improving though, your competitors are not sitting still. Your position on the cost curve is relative. This slide out of all the slides should make clear the importance of the commodity framework in all of this. Your position on the cost curve depends on what your competitors can deliver, not

</details>

<!-- chunk 13/51 -->

### 成本优势与相对效率的动态博弈

**Speaker A（SemiAnalysis）**：……而不仅仅是你自己。这是一个相对的衡量标准。这里有一个简单的假设情景：我们比较的是同一项任务、同样的质量要求，使用虚构的成本单位来衡量——我喜欢将其想象成金条。每完成一次成功任务，你的全部成本从 10 降到了 8。而在同一时期，你的竞争对手的成本从 6 降到了 1.2（或 12）。你确实进步了，这很棒。但你们双方都在进步。在这个例子中，你一开始是成本较低的生产者，到头来反而成了成本较高的一方。这就给了竞争对手更大的降价空间——前提是客户认为这两项服务具有同等的可接受度。

变得更好并不意味着你就自动处于领先地位。应用大宗商品框架会让你意识到：你必须在相对的基础上去比较你的单位有效工作成本，将你自己的产品与竞争对手能够交付的成果进行对比。

<details>
<summary>Original English</summary>

**Speaker A (SemiAnalysis)**: ...just yourself. It's a relative measure. Here's a simple hypothetical. We're comparing the same task, the same required quality using made-up costs. I like to imagine bars of gold. Your full cost per successful task falls from 10 to 8. In the same period, your competitor's falls from 6 to 1.2. You improved. That's awesome. But both of you did. And in this example, you started as the cheaper producer and ended as the more expensive one. That gives the competitor more room to lower its selling price, provided customers find the two services equally acceptable.

Getting better does not automatically move you ahead. Applying the commodity framework makes you realize that you have to compare your cost per useful work on a relative basis—comparing your own product with what your competitors can deliver.

</details>

**Speaker A（SemiAnalysis）**：在像今天这样的时刻，这种比较很容易被忽视，因为目前需求远远超过供给，而且在可预见的未来——两到三年内——这种局面还会持续。当前的行业能见度很好。但短缺往往会掩盖这些差异。当需求强劲且供给受限时，成本差异极大的生产者都能找到客户。强劲的营收会让这些差异显得不那么紧迫。如果你是一名 CEO，既然可以去建设一座庞大的全新数据中心，你又为什么要把宝贵的时间、精力与金钱花在巩固自己在成本曲线上的位置呢？

在这样的时刻，退后一步、建立一点长远的眼光至关重要，需要带一点历史视角来看待。人类历史上的每一种大宗商品都经历过供需的周期性波动。仅仅因为我们目前还看不到拐点何时到来，并不意味着这一轮周期就会有什么不同——除非你是一个极端的“AI 最大主义者”（AI maxi），当然我们当中确实有人是。

因此，我完全做好了认错的准备，我每天都在犯错。但我想说的是，如果你是一家带有负债或杠杆的企业，你尤其需要认真意识到这一点。在构建成本优势上保持主动，或许不如做大顶层营收（营收规模）那么光鲜诱人，但如果你想在整个商业周期中存活下来，它就至关重要。这就是为什么你必须在仍有机会的时候——在阳光普照、你还能募集到资本的时候——建立起你的运营能力与成本优势。当客户拥有更多选择、价格面临下行压力时，这些优势就会变得更加举足轻重。

<details>
<summary>Original English</summary>

**Speaker A (SemiAnalysis)**: That comparison can be easy to overlook in moments like today where demand far outstrips supply and will for the foreseeable future—two to three years. Visibility good. Scarcity can obscure those differences. When demand is strong and supply is constrained, producers with very different costs can find customers. Strong revenue can make those differences feel less urgent. If you're a CEO, why would you focus your precious time and energy and money shoring up your spot on the cost curve when you can be building a massive new data center?

In moments like this, it's important to step back and have a little perspective. Take a little historical perspective. Every commodity in the history of humanity has had swings in supply and demand. Just because we don't see when that will be yet does not mean that this cycle will be any different, unless you're a total AI maxi, which some of us are.

So, I'm very open to being wrong. I'm wrong every day. But I would say if you're a business with leverage, you need to be especially conscientious of this. Being proactive with building your cost advantage might not be as sexy as making your top line bigger, but it matters deeply if you want to survive through a business cycle. That's why you want to build your operating capability and cost advantage while you have the opportunity, when the sun is shining, when you can raise capital. They matter even more when customers have more choices to make and prices come under pressure.

</details>

### 可比算力分级与租赁价格基准

**Speaker A（SemiAnalysis）**：那么，我们该如何向买方明确界定他们实际获得了什么？可比算力需要明确的品级（Grades）。

现在，让我们来看看一个智能生产者所购买的算力。我们已经看到，同一颗芯片根据其运营方式的不同，可能会带来截然不同的结果；两份针对 B200 GPU 租用时长的报价，可能包含不同的服务内容，并将不同的运维工作留给客户承担。大宗商品框架需要一种描述这些差异的方法，以便买家清楚哪些服务可以被视为同等可比。这就是“品级”的作用所在。

品级描述了一项具体的算力服务以及买家可以期待获得的内容。它并不会让智能在每项任务中变得完全通用可替换。一旦我们定义了该项服务，我们就可以进一步探究其租赁价格向我们揭示了什么。

<details>
<summary>Original English</summary>

**Speaker A (SemiAnalysis)**: So, how do we make clear what the buyer actually gets? Comparable compute needs clear grades.

Now, let's look at the compute that an intelligence producer is buying. We've already seen that the same chip can deliver different results depending on how it's operated, and two offers for B200 GPU hours can include different services and leave different operating jobs with the customer. A commodity framework needs a way to describe these differences so buyers know which services they can treat as comparable. That's the job of a grade.

The grade describes a particular compute service and what its buyers can expect. It doesn't make intelligence interchangeable across every task. Once we've defined that service, we can ask what its rental price tells us.

</details>

**Speaker A（SemiAnalysis）**：租赁价格基准衡量的究竟是什么？租赁价格基准概括了在其所界定的市场范围内 GPU 时长的价格。它既不是生产者的生产成本，也不是所交付智能的衡量指标。我们需要搞清楚这些价格究竟从何而来：公开发布的报价与实际达成的交易根本不是一回事。服务范围、合同条款、采样了谁的价格以及这些价格是如何汇总加权的，都会塑造出这一价格参考基准。

运营质量可以在指数没有单独衡量它的情况下对这些价格产生影响。仅仅追踪一个租赁参考基准，并不能告诉你你的部署系统到底能产出多少有效工作。要将其用作对冲工具，你就必须理解它是如何追踪你实际支付或赚取的租金的。

<details>
<summary>Original English</summary>

**Speaker A (SemiAnalysis)**: What does a rental price benchmark measure? A rental price benchmark summarizes the price of GPU hours within its defined market. It isn't the producer's production cost or a measure of intelligence delivered. We need to know where those prices come from. An advertised offer and a completed trade are not the same thing. Service scope, contract terms, whose prices are sampled and how they're combined all shape that reference point.

Operating quality can influence those prices without the index measuring it separately. Running a rental reference doesn't tell you how much useful work your deployment will produce. To use it as a hedge, you need to understand how it tracks the rent you actually pay or earn.

</details>

### 算力期货的对冲逻辑与局限

**Speaker A（SemiAnalysis）**：算力期货究竟能够对冲什么？最近大家对算力期货充满了兴奋之情。对那些还不了解的人来说，期货合约为未来的交付或现金结算确立了标准化条款。而现金结算依赖于价格参考基准。买方和卖方在租赁价格上面临着同样的不确定性。回想一下之前提到的服务堆栈与监控系统故障：评估谁在运行这套系统，有助于描述买家获得的具体服务，进而帮助我们定义品级，让买家清楚哪些算力服务具有可比性。随后的基准指数则需要精准跟踪他们实际支付或获得的租金。

这就是为什么我提出这样一个论点：对运营商进行评级，是建立可信算力期货市场的核心基石。评级为这项工作提供了依据。但评级本身并不能自动确立一个期货品级、建立稳健的基准指数，或者创造出足够充沛的交易流动性以便随时买卖。它也不必然能保证对冲的有效性。租赁价格对冲可以帮助抵消租金价格的波动，但它无法修复失败的系统部署，也无法确保你的客户一定会付款。

收费高于指数基准本身并不会让它变成一个糟糕的对冲工具。真正关键的是，基准指数的变化能否紧跟你的实际租金变化。如果两者之间的联动关系发生非预期的偏移，就会留下真实的基准价格风险。这些工具能够帮助你明确自己买到了什么，并管理租赁价格风险；但对智能生产者来说，租金只是整体成本的一部分。运营商依然必须将这些算力转化为客户能够真正投入使用的有效产出。

<details>
<summary>Original English</summary>

**Speaker A (SemiAnalysis)**: What can compute futures hedge? There's been a lot of excitement lately about compute futures. For all of you that don't know, a futures contract sets a standardized term for future delivery or cash settlement. Cash settlement depends on a price reference. Buyers and sellers both face uncertainty about rental prices. Think back to the serving stacks and the monitoring failure. Assessing who runs the system helps describe the service buyers get; that helps us define grades so buyers know which compute services are comparable. The benchmark then needs to track the rent they actually pay or earn.

That's why I make this argument: rating the operator is an essential building block for building a credible compute futures market. A rating informs that work. It doesn't by itself define a futures grade, establish a sound benchmark, or create enough trading to buy and sell easily. It also doesn't necessarily make a hedge effective. A rental price hedge can help offset rental price changes. It does not fix a failed deployment or ensure that your customer pays.

Charging more than the index does not by itself make it a bad hedge. What matters is whether changes in the reference track changes in your rent. Unexpected changes in that relationship leave real price risk. Those tools can help you understand what you're buying and manage the rental price risk. For an intelligence producer, rent is one part of the cost. The operator still has to turn that compute into work that the customer can actually use.

</details>

### 总结：GPU 的性能上限取决于运营商水平

**Speaker A（SemiAnalysis）**：这让我们回到了原点：一颗 GPU 的表现，最终会跌落到其运营商的实际水平。那么，究竟谁能以更低的成本生产出你所需的智能？以最低的成本！答案是：那个能够以最低的“单次成功任务全部成本”，持续稳定满足你需求的生产者。把你为了交付该项服务所投入的一切花销计算在内，然后除以客户真正能够利用的有效产出。运营能力直接影响着该公式的分子与分母——包括你的支出总额，以及你能交付多少额外的有效工作。

此外，你的竞争地位完全取决于竞争对手的表现。即便你自己取得了进步，但如果对手进步得比你更快，你依然会落后。这就是为什么理解运营商不仅在单一时间节点至关重要，而且在贯穿整个周期时都举足轻重——尤其是当客户拥有更多选择、价格承受更大压力的时候。

总而言之，如果你刚刚走进会场想要一个一句话总结（TL;DR），那就是：**GPU 的表现最终取决于运营商的水平**。

让我们共同努力，建设一个信息更加透明、高效的算力市场。女士们、先生们，非常感谢各位今天抽出宝贵时间。在 SemiAnalysis，我们深知市场绝不会自发变得透明和高效，我们渴望成为这一进程中积极投入的合作伙伴。不过孤掌难鸣，实际上我们希望有更多伙伴加入。如果您希望与我们展开合作、贡献力量或加入团队，我们非常期待听到您的声音。我们始终在招募优秀人才，欢迎随时联系。如果今天的内容引起了您的共鸣，商务合作请发送邮件至 sales@semianalysis.com；如果您有兴趣加入团队，欢迎直接联系我的个人邮箱 kn@semianalysis.com（K-E-N-N-O-N）。再次感谢大家的聆听，祝各位度过美好的一天！

<details>
<summary>Original English</summary>

**Speaker A (SemiAnalysis)**: This brings us full circle. So a GPU falls to the level of the operator. So who can produce the intelligence you need at the lower cost? At the lowest cost. The producer who can repeatedly meet your requirements at the lowest full cost per successfully completed task. Count everything spent to deliver the service, then divide by the output that the customer can actually use. Operating capability affects both sides of that equation: what you spend, and how much more useful work you can deliver.

Also, your position depends on that of your competitors. You can improve and still fall behind if your competitors improve faster than you. That's why understanding the operator matters through the cycle, not just at one point in time—especially when customers have more choices and prices come under more pressure.

In conclusion, if you just walked in and want the TL;DR, this is it: A GPU falls to the level of the operator.

Help build a better informed compute. Ladies and gentlemen, thank you so much for your time today. At SemiAnalysis, we know that markets do not become informed and efficient on their own. We seek to be an active, engaged partner in that work. It takes two to tango though, ideally more than two actually. If you'd like to partner with us, contribute, or join the team, we would love to hear from you. We are always hiring great people; please reach out. If this resonated, please go ahead and email sales@semianalysis.com for partnership opportunities. And if you're interested in potentially joining the team, my email is kn@semianalysis.com—K-E-N-N-O-N. Thank you all for listening and have a fantastic rest of your day.

</details>

### 下一场分享：物理交割的算力远期市场构建

**Evan（San Francisco Compute）**：大家听得到吗？热身测试……大家好，大家今天感觉如何？

我们这场分享的主题是关于算力市场的，不过更准确地说，是探讨“为什么要去建立一个算力市场”。如果大家还不认识我，我叫 Evan。我们运营着一家名为 San Francisco Compute 的公司。我们正在建立一个实物交割（physically settled）的订单与远期合约市场。

如果你参加了上一场演讲，上一场分享的核心观点基本上是在阐述：为什么所有 GPU 集群的运营商目前运转得都差强人意。而当我们提到“实物交割”时，我们的意思是我们自己就是运营商。我们既是底层硬件的运营者——就像云计算厂商扮演硬件运营商的角色一样——与此同时，我们本身也是这个交易市场。这有点类似于面向算力构建的电力电网（Grid for compute）。

因此，这里的核心逻辑在于：要想运行和操盘一台超级计算机，我们认为问题从超级计算机的设计阶段就已然出现，甚至直接根植于物料清单（BOM）的设计之中。它关乎对背板互联网络拓扑（backplane fabric）的掌控，关乎裸金属编排调度能力的把控，也关乎运行在虚拟机之上的各类上层服务等等。在这个技术栈中，存在着许多必须牢牢掌控的不同环节……

<details>
<summary>Original English</summary>

**Evan (San Francisco Compute)**: [Mic check / audio test] Hello everybody. How are we doing?

So this is a talk about compute markets, but it's kind of more of a talk about why to make a compute market. If you don't know me, I'm Evan. We run a company called San Francisco Compute. We make a physically settled order, physically settled forwards market.

So if you were here for the last talk, last talk was basically why all the operators of GPU clusters don't really work very well. When we say physically settled, we mean we're the operator. We're both the operator of the hardware in the same way that a cloud is the operator of the hardware, and then we're also the market at the same time. It's kind of like a grid for compute.

So the general gist of this is that in order to run and operate a supercomputer, we think problems start right at the design of the supercomputer, right in the design of the bill of materials. It's control of the backplane fabric as well. It's also control of bare metal orchestration. It's also services on top, VMs and so on. There's a lot of different parts of the stack that you have...

</details>

<!-- chunk 14/51 -->

### 超级计算即服务与算力市场的诞生

**演讲者**：……才能有效运转。否则，那些拥有数据中心、并希望通过转型为 GPU 云来赚取更多利润的人，最终只会辜负客户的期望。这就是我们的业务所在——我们提供所谓的“超级计算即服务”（supercomputing as a service）。我们服务于那些想要成为云厂商的客户，例如希望成为英伟达所认证的 NCP（Nvidia Cloud Partner）的机构；或者希望为自己的投资组合储备算力集群的风险投资机构，以便在类似 Instinct 这样的被投企业业务爆发时，能够灵活重新调配算力容量；亦或是那些意识到算力残值对自身财务报表极其重要、希望获取算力残余价值，但又不想亲自去运营一台超级计算机的 AI 公司。这就是物理交付结算层。在此基础之上，我们还运营着一个实时的算力订单簿，支持客户购买现货或未来的保留算力容量。

<details>
<summary>Original English</summary>

**Speaker**: ...to do effectively. Otherwise, the folks who have a data center and would like to make more money on that data center by becoming the GPU cloud end up failing for the customer. So that's what we do. We offer what's called supercomputing as a service. We go to folks who want to become a cloud. That's like folks who want to become what Nvidia would call an NCP. Or venture firms that want to have clusters for their portfolio, and want to be able to reallocate that capacity when a company like Instinct is taking off. Or AI companies who would like the residual value on the compute because they've realized that's really important to their financials, but don't want to operate a supercomputer. So that's physical settlement. And then on top of that, we run a live order book for capacity that you can buy reserved either right now or in the future.

</details>

**演讲者**：坦白讲，这整套业务完全脱离了我们最初的设想。最初，我们创立的公司名叫 Junark，当时是想做类似 Suno 或 Udio 那样的产品，只是时间比它们都要早得多。在那个时期，要想切实创办一家 AI 实验室，你必须筹集一笔数额极其庞大的押金，当时这笔押金高达 1000 万美元。我们当时觉得这笔钱简直匪夷所思，所以心想：“不，这太蠢了，我们去融 500k（50 万美元）就好，显然我们应该去租别人的算力。”当然，到了今天，这个数字已经不再是 1000 万美元，而变成了 10 亿美元。即便如此，我们当时融了 50 万美元，买下了一个大集群，结果每个月都在该集群上面临严重的账面亏损（underwater）。要不是我们把集群转租了出去，公司早就破产了。所以如果你听说过 GPU 经纪商（GPU broker），我们其实是第一家 GPU 经纪商，因为我们是被逼无奈才成为 GPU 经纪商的。公司成立的第一年，我们所做的一切就是拼命转售我们的集群，否则只能破产。我当时甚至揣着实际印出来的宣传纸在 NeurIPS 大会上到处晃悠，那张纸上由于海报赶制得太匆忙，居然同时写着 H100 和 A100。

<details>
<summary>Original English</summary>

**Speaker**: This together is not at all what we thought we were going to be doing. Originally, we were this company called Junark that was trying to make kind of like Suno or Udio, but prior to Suno or Udio. At the time, what you needed to do to realistically start a lab was you needed to raise a big deposit, a huge one, which was $10 million at the time. We thought that was a crazy amount of money. And so we thought, "No, that's stupid. We're going to raise 500k and obviously what we're going to do is we're going to rent from somebody else." Obviously today it's not $10 million, it's a billion dollars. And nonetheless, we had raised our 500k. We buy a big cluster and then we're underwater on our cluster every month. And if we didn't sublease our cluster, we would have gone bankrupt. So if you've heard of GPU brokers, we were the first GPU broker because we were forced into being a GPU broker. So the first year of the company was us just trying to sell our cluster, otherwise we would go bankrupt. So I would wander around with these like actual pieces of paper at NeurIPS which both say H100 and A100 at the same time because that's how I made the poster so quickly.

</details>

### 创办 AI 实验室的重重困境与算力市场的本质

**演讲者**：因此，今天的演讲其实重点并不在于算力市场究竟是如何运作的，而在于算力市场何以能够存在。我们常把它比作一本折页小册子：小册子的封面上写着“创办一家新兴实验室简直太痛苦了，面临着各种各样的财务和经济难题”；而小册子的封底则写着“算力市场”。在翻开小册子之前，你很难看清这两者之间究竟是如何联系起来的。可一旦你打开它，就会惊呼：“天呐，这里面的内容太庞杂了，层层展开，怎么折叠都翻不完。”这实在是一个极其艰难且极具挑战性的问题，因为要想把它做成，你必须奇迹般地同时解决两个难题：第一，你必须凭空建立一个双边市场，这是一个独特且艰巨的挑战，因为它面临着典型的冷启动问题；第二，你必须搭建起一套云架构，同时又绝对不能让自己沦为一家传统的云服务商，这本身又是一项完全独立的巨大挑战。

<details>
<summary>Original English</summary>

**Speaker**: And so this talk is not really about necessarily like how a compute market works. It's how a compute market gets to exist. We like to think about it like there's this pamphlet and on the pamphlet on the front side it's like, man, starting a Neolab sucks. There's all these different like financial and economic problems, and on the back of the pamphlet it says compute markets. It's not super clear how one gets to the other until you open the pamphlet and then like, oh my holy, there's like so much stuff in this pamphlet and it keeps going and there's so many folds. It's just a very difficult and challenging problem because you need to solve two like miracle problems to get working. You have to both make a market, which is a uniquely difficult problem because it has a cold start problem. You also have to build a cloud and then you have to not become a cloud, which is a whole separate challenge.

</details>

**演讲者**：但这些恰恰是当下各大实验室正在直面的痛点，而且很快就会成为所有人都要面临的难题。如果你在一家初创公司工作，这很快就会变成你的切肤之痛。眼下，全行业所有的算力库存几乎全部售罄，而且这种供不应求的局面很可能在相当长一段时间内都不会改变。这意味着如果你需要算力，就必须去订购一个全新的算力集群，而订购是有交付周期的（lead time）。在当下，没有任何办法能让你付款后让集群立刻上线，你只能为了它在未来的某个时间点上线而预先付款。市场上目前没有任何现实手段能够让你立即拿到现货集群。

<details>
<summary>Original English</summary>

**Speaker**: But these are the problems that the labs are facing and it's about to be the problems that everyone is about to facing. So if you work at a startup these are your problems now. Right now everybody is sold out of compute. This is probably not going to change for a while. So that means that you're going to have to buy a new cluster, a net new one, and there's a lead time. You have no way to pay for that cluster to come online now. You're going to pay for it to come online later. There's nothing in the market that can realistically get that cluster online for you now.

</details>

### 信用承保黑洞与集群交付错配

**演讲者**：与此相伴的是，你必须把银行账户里的全部现金余额都当作押金付出去。之所以要倾囊支付全部存款作为押金，是因为放贷机构和资方完全不知道该如何对 AGI 进行信用承保（underwrite）。究竟该怎么承保？在旧金山或者纽约，经常有两三个人组成的初创团队跳出来说“我们要构建超级智能”。没有任何放贷机构懂得该如何对超级智能做风险核保，因此他们对这种底层资产到底值多少钱一无所知。与此同时，你的集群极大概率会遭遇严重延期。这是因为出资方必须针对终端客户的信用风险进行风险核保，所以在集群部署之前，他们必须首先明确最终的买单客户到底是谁。因此，在客户正式签下合同的那一瞬间，反而是整套运营流程中风险最高的一刻。

<details>
<summary>Original English</summary>

**Speaker**: Meanwhile, you're going to pay your entire bank balance as a deposit. The reason you're paying your entire bank balance as a deposit is because the lender has no idea how to underwrite AGI. How in the world are you supposed to do that? You've got two person startups in San Francisco who or maybe New York who say I'm gonna build super intelligence. No lender knows how to underwrite super intelligence. So they have no idea what the asset is worth. Meanwhile your cluster is very likely to be delayed. That's because the lender needed to underwrite against the credit risk of the customer and so they needed to know who is the customer first before you deploy the cluster. So right when the customer signs is the riskiest point in the entire operation.

</details>

**演讲者**：你最理想的商业形态本该是：先将算力集群彻底建好、调试稳定，然后再去对外销售。这种先建后售的模式能极大程度地减少各种集群宕机或损坏故障。然而，现实中大部分着手搭建集群的人，仅仅是因为他们手里恰好拥有让算力成本看起来比较便宜的物理资产——比如他们现成拥有数据中心机房空间。但拥有机房空间，并不等于拥有超级计算工程专长；如果你看过前一场演讲，应该对此深有体会。在此背景下，你势必会重蹈当年 Junark 踩过的同一个覆辙：要么大幅过度采购算力，要么严重采购不足。

<details>
<summary>Original English</summary>

**Speaker**: You wanted it to be the case that you built the cluster first and then you sell it. This also helps reduce all sorts of different types of problems where clusters break. Meanwhile, most of the people who are setting up clusters are people who have the actual asset that makes the thing cheap. Like you've got the data center space already. What that doesn't get is supercomputing expertise, as we saw in the last talk if you've watched that one. Meanwhile, you're going to run into the exact same problem that Junark did, which is you're going to either way overbuy or you're going to way underbuy.

</details>

### 风险交织下的算力市场解法与商业模式差异

**演讲者**：出现过度采购或采购不足，其根本原因在于 AI 软件的利润率结构完全不同于传统 SaaS 软件公司。正因如此，你的容错空间极小。你很有可能因为算力采购不足，而被那些步调踩得精准的竞争对手彻底击垮；或者因为采购过度而迅速沦为下一个 Stability AI，甚至轰然暴雷，落得类似 Character.ai 那样的结局。归根结底，这些表面上的不同困境本质上是同一个问题在不同层面的体现，它们只是不同维度的风险：技术风险、财务风险、信用风险。它们全部盘根错节地捆绑在了一起，形成了一个巨大的系统性风险包。而这正是我们最终所要解决的难题，也是我们认为整个算力市场行业从宏观上能够为业界化解的核心症结。

<details>
<summary>Original English</summary>

**Speaker**: That's because AI doesn't have margins that look like SAS companies. And so you don't have very much margin for error. And so the chances that you either under buy and somebody else wins because they did it correctly or you over buy and then you just become stability AI or you blow up you end up like character AI are really high. So these are all the same problem. They're all just different types of risk. They're technical risk. They're financial risk. They're credit risk. They're all one big bundled risk problem which is the problem that we end up solving and it's also the problem that we think compute markets broadly the entire industry solves.

</details>

**演讲者**：接下来我们将逐项拆解这些问题，梳理它们是如何一步步推导出算力市场的必要性的。因为如果你不深刻理解这些现实痛点，就很难明白为什么需要算力市场的存在。很多人甚至会轻率地以为：“哇，算力市场听起来好酷，那我也去搞一个。”但在我们看来，算力市场必须从行业参与者所面临的真实困境中自然推导出来。首先摆在所有人面前的第一个问题：为什么所有算力库存都被售空了？之所以被售空，是因为出资方在没有签订长期照付不议协议（take-or-pay contract）之前，根本不敢为集群建设提供融资。

<details>
<summary>Original English</summary>

**Speaker**: So we'll walk through each one of these and walk how that gets to a compute market because if you don't understand these, it's kind of like unclear why you would want a compute market. And they almost seem like this problem that somebody thinks, oh wow, compute markets are cool, so I'm going to go start one. We think they should be derived from the actual problems that people face, which is first, everyone is sold out. Why are they sold out? Because the lender couldn't finance the cluster unless you had a long-term opt.

</details>

### 云计算定价敏感度与信用瓶颈

**演讲者**：在过去传统的 CPU 时代，情况完全不是这样。因为 CPU 的主要采购方是 SaaS 公司，SaaS 公司普遍拥有极高的毛利率；正因为利润丰厚，你可以打造出一种高毛利的产品，从而为 CPU 算力支付高额溢价。不妨这样想：如果你是一家 SaaS 公司，底层云厂商突然把价格翻倍，你可能会非常愤怒、极其憎恶这家云厂商，但你绝不会因此倒闭；但如果你是一家 AI 公司，底层云厂商把价格提高一倍，只要你无法立刻切换到另一家更便宜的云上，你就会直接破产倒闭。这意味着 AI 公司对算力价格极其敏感。再加上目前没有任何技术壁垒能够真正将客户深度绑定在某一家特定的云上，厂商根本无法通过按需付费（on-demand）的模式来提供算力，因为客户随时会为了微小的差价迅速出逃至更廉价的平台。

<details>
<summary>Original English</summary>

**Speaker**: This wasn't the case because CPU buyers are SAS companies. SAS companies have high margins and because they have high margins you can build a product that rewards you for having a great that rewards you with high margins for your your CPUs. Think about it like this way. If you're a SAS company and your underlying cloud doubles their prices, you don't go bankrupt. You hate your cloud. You're mad, but you don't go bankrupt. If you're an AI company and your underlying cloud doubles their prices, you go bankrupt unless you go to some other underlying cloud. And what that means is that you're actually price sensitive and because you're actually price sensitive and there's nothing keeping you at any particular cloud. So you can't sell on demand because your customers will immediately leave to whoever is cheaper.

</details>

**演讲者**：这就倒逼出一种现实：要想为 GPU 集群获得建设融资，你必须手握长期的照付不议合同，并且最好签约方具备投资级信用评级。然而，如果你在这些合同上缺乏二级市场的流动性——也就是说，当你卖出的是不可转让的保留算力，而签下合同的客户一旦需求变动却无法中途脱身退出——那么这也意味着，另一家像 Instinct 那样业务正迎来爆发式增长、此时此刻急需现货容量的客户，根本买不到任何算力。他们必须被迫去重新发起一个全新集群的融资流程；由于物理建设规律的客观制约，这需要经历极其漫长的交付周期，有时甚至得从零开始去盖一栋该死的数据中心。

<details>
<summary>Original English</summary>

**Speaker**: And so that means that in order to finance GPU clusters, you have to have long-term take-pay contracts, hopefully with someone who has investment grade credit. However, if you don't have liquidity on those, if you're selling reserved and your customer can't get out, then that also means that some other customer who wants the capacity right now because they're like instinct and their product is taking off can't pay for anything. They have to finance a new cluster which has a lead time because the physical world just exists and it's going to take a while. Sometimes you even have to build the damn data center.

</details>

**演讲者**：更进一步地说，正因为每次都不得不为新集群寻求融资，你就必须掏空口袋支付巨额押金，因为在目前的 AI 领域，几乎没有哪家企业具备令人信服的商业信用。这是一门彻头彻尾的全新技术，所有的公司都是新创企业。即使你顺着阶梯逐步做大，在整个成长路径中依然会处处撞上信用瓶颈的墙壁。这是目前整个 AI 产业名列第一的最大瓶颈。它根本不是电力，你在遇到电力瓶颈之前，早就被信用壁垒拦住了去路。这一切造成的后果就是：所有的模型推理公司、所有的初创实验室，其发展上限全部被他们账面上能够拿出的现金储备死死卡死……

<details>
<summary>Original English</summary>

**Speaker**: And then because you're financing a new cluster, you're going to pay a deposit because almost nobody in AI has any reasonable credit. And because this is a brand new technology, all these companies are new. Meanwhile, even as you start to scale up that ladder, you're still going to run into credit issues all the way through. It's the number one bottleneck of AI at the moment. It's not power. You hit credit way before you hit AI or way before you hit power. So, what that means is every inference company, every Neol, they're bottlenecked by how much cash...

</details>

<!-- chunk 15/51 -->

### 算力抵押怪圈与交付延误风险

**主讲人**：……他们银行账户里到底有多少钱？于是，他们只能回头去找风险投资人。而风投机构往往会说：“噢，我只打算在模型层、应用层或推理层进行投资，因为我根本不想去为那些沉重的资本支出（capex）买单。”然而，风险投资人最终其实还是承担了所有这些资本支出——他们向新兴的 AI 实验室或新型推理初创公司开出一张支票，随后初创公司立刻把这笔资金转付给云服务商，作为算力集群的预付款押金。整个行业正是通过这种方式来为客户完成信用背书与承销的。

<details>
<summary>Original English</summary>

**Speaker**: ...do they have in the bank account. And so they go back to the venture capitalist who says, "Oh, I'm going to fund at the model layer, the application layer, the inference layer because I don't want to fund all of that capex stuff." And so the venture capitalist then funds all the capex stuff by giving the new neolab or new inference company the check that they then send to the cloud which is the deposit for the cluster and that's how you underwrite the customer.

</details>

**主讲人**：结果就是，集群交付一再被延误。这是因为云服务商在真正拿到确定的客户合同与押金之前，根本无法着手实际部署集群。这就构成了整个链条中最脆弱、风险最高的节点。因此，真正合理的操作本该是：云服务商提前采购好算力集群，耐心等待设备在数据中心完成上架安装与通电部署，然后再将其出租销售出去。如果这样做，交付出现延期的概率就会大幅降低。

<details>
<summary>Original English</summary>

**Speaker**: So the clusters then are delayed because the cloud couldn't actually deploy the cluster until they had the customer in hand. And so that was the riskiest point. So therefore what should have happened was the cloud had bought the cluster ahead of time and then waited until it was landed in the data center and then sold it. And that means you have way less likelihood of delays.

</details>

### 缺乏流动性带来的硬件故障与再采购死循环

**主讲人**：与此同时，一旦你作为客户终于拿到了集群，它又极其容易发生故障并宕机，原因在于你缺乏流动性缓冲（liquidity）。因此，如果硬件故障率超出了你的预期，而你又没有多余备用算力或者灵活调配接入新节点的能力，你就根本无处去调拨算力节点。这意味着，如果你需要新节点来顶替那些发生故障的机器，你就必须走繁琐的返修维保流程（RMA），不得不重新申请采购全新节点。这立刻又把我们拉回到了前面几步所经历的困境——你再次一头撞上了漫长而不可控的采购交货周期（lead time）问题。结果就是，所有人随时随地都在经历系统性崩溃。

<details>
<summary>Original English</summary>

**Speaker**: Meanwhile, the cluster is very likely to break when you get the cluster as the customer because you don't have liquidity. And so, if the failure rate is higher than what you expect and you don't have the ability to transition a node in, then you don't have anywhere you can pull nodes from, which means that if you need new nodes to make up for the failed ones, you have to RMA them, which means you have to get a new node. And then that gets us back to several steps before where you have the lead time problem again. And so, everything breaks for everybody all the time.

</details>

**主讲人**：作为一个新兴的 AI 实验室，哪怕你费尽千辛万苦熬过了上面所有难关——所有地方全都缺货脱销，你必须忍受极其漫长的交货周期，预先支付巨额押金，中途遭遇严重延误，交付后设备频繁发生硬件故障，最后好不容易把这一切都摆平了——你面临的新问题依然无比棘手：你精确预测自身业务算力需求的可能性微乎其微。最终的结果要么是你的算力配置严重过剩，要么是严重不足，而且你根本无路可逃。你既没有任何渠道把多余闲置的算力转售给别人，在算力告急时也根本买不到更多立即可用的算力。

<details>
<summary>Original English</summary>

**Speaker**: Once you have gotten through all of that as a new AI lab, your problems are—you know, everyone was sold out. You then had to wait a lead time, you paid this big deposit, the thing was delayed and then it broke and finally you got through all of that. And the likelihood that you predict your demand correctly is very low. And so you're either going to be way overprovisioned or way underprovisioned and you have no way out. There's no way to sell your capacity to somebody else and there's no way to buy more capacity if you need it.

</details>

### 计算市场设想与行业寡头垄断走向

**主讲人**：因此，要想通过建立算力市场（compute markets）来解决上述痛点，你必须同时化解一系列盘根错节的问题。首先，你必须去承销 GPU 集群本身的资产价值与流动性，而不是去对终端客户的资信与信用违约风险进行承销评估。这是它理论上可行的运转逻辑，但并不保证现实中必然会这样演进。在以往的其他产业中，历史的实际走向往往是走向全面整合与垄断：最终出现极少数信誉极高的大客户，直接独吞包揽整条产业链。当前的 AI 发展路径正在沿着这条轨道狂奔。未来的行业格局恐怕不会是一个任何人都能自由参与、买卖通畅的流动性市场，而是会变得越来越像台积电（TSMC）——只剩下极少数买家（即大型超大规模云厂商），以及屈指可数的几个头部顶级模型实验室（AI labs），而其他所有中小初创公司将彻底不复存在。

<details>
<summary>Original English</summary>

**Speaker**: So, compute markets—to solve these problems, you need to solve a bunch of different problems all at once. You need to underwrite the value of the GPU cluster rather than underwriting the value or underwriting the credit risk of the customer. This is how it could work. It's not guaranteed to work like this. In other industries, what happened is everything just consolidated. You got one big creditworthy customer that does the whole damn industry. That's what the path of AI is currently on track to do. It's instead of going to be a liquid market where anybody can participate, it's going to look like TSMC. You're going to get one buyer or a few buyers that are the clouds. You're going to get a few model labs that are the AI labs. And then you won't get other startups.

</details>

**主讲人**：我们认为这正是未来的必然结局。这也是为什么三年前当我们还在运营自己的 AI 实验室时，曾站在命运的十字路口。我们本可以选择另一条路，说一句：“算了吧，我们不要为了让一家小公司苟延残喘而在泥潭里苦熬好几年，我们干脆换个方向再去新做一个 AI 实验室。”但当时我们就敏锐地看清了这一深层死结，我们对自己说：“如果我们不对这个底层结构性问题采取行动，那么三年后的今天我们依然会硬生生撞在这堵南墙上。”果不其然，三年后的今天，我们正站在这个痛点面前，而行业里的每一个人也都正在撞上这堵墙。

<details>
<summary>Original English</summary>

**Speaker**: This is what we think is going to happen. And this is why 3 years ago when we were doing our AI lab, we had a chance. We could have said, "No, we're not going to stick it out for several years just trying to keep our company alive. We're just going to go do a new AI lab." But we saw this problem and we said, "Oh, if we don't do anything about this, then we will just hit this 3 years from now." And here we are three years from now hitting this problem, and where everyone's going to hit this problem.

</details>

### 为什么算力经纪无法成立：物理交割与酒店运维隐喻

**主讲人**：如果你听了上一场演讲就会明白，除非你同时亲自运营交易市场并且亲自运营物理集群本身，否则你几乎根本无法解决这个问题。这里介绍一下 Dylan Page。Dylan 是 CNCF（云原生计算基金会）基础设施工作组的联席主席——正是该组织打造了业界基石 Kubernetes。他此前在 Lambda 负责基础设施架构工作。他之所以选择加入 San Francisco Compute，是因为 GPU 算力目前在标准化与可靠性方面还极不成熟，根本无法允许市场运营商与底层物理基础设施完全割裂开来。如果你自己不亲自采购并实际控制这些设备，这套模式就根本跑不通；换句话说，如果你采购硬件的对象并不直接负责运维该设备，事情就彻底失控了。

<details>
<summary>Original English</summary>

**Speaker**: So, as if you watched the last talk, it's very hard to solve this problem unless you are operating both the market and the clusters at the same time. So this is Dylan Page. Dylan is a co-chair of the CNCF infrastructure group. That's the organization that makes Kubernetes. He formerly worked at Lambda doing infrastructure there. And the reason he joined San Francisco Compute because GPU compute isn't sufficiently standardized reliable for the market operator to be divorced from the physical infrastructure. It doesn't work if you aren't the one who's buying the thing. Sorry, it doesn't work if the person you're buying from isn't operating it.

</details>

**主讲人**：为了说明纯粹倒买倒卖为什么行不通，我给大家举个通俗的例子：我相信现场有很多人是从外地甚至海外飞来参会的，你们都订了酒店房间。如果能把你手头的酒店房间转售倒卖给别人，听起来是不是很棒？假设我跑来从你手里买下了这间酒店客房，然后我问：“我能叫客房服务吗？有人来帮我打扫房间吗？房间设施出毛病了我该找谁解决？”如果你本身根本不负责经营和管理这家酒店，你对这些售后与运维问题就完全无能为力。这就是为什么单纯做算力集群中介撮合经纪（brokering clusters）根本行不通的原因！你必须像经营一家完整的酒店那样亲自运维算力集群，把整套复杂繁琐的基础设施全盘管起来。否则，你根本无法真正建立起一个健全的市场，它在现实中根本无法运转，你更无法完成真正的物理结算交割（physical settlement）。

<details>
<summary>Original English</summary>

**Speaker**: To give an example of why this doesn't work is I'm sure some of you are flying in from overseas or out of town and you have a hotel room. Wouldn't it be great if you could sell that hotel room to somebody else? I go to you and I want to buy that hotel room. And I say, "Can I get service? Can I get my room cleaned? I've got a problem with my room. Who do I call?" If you don't operate the hotel, you can't fix any of those problems. That's why brokering clusters doesn't work. You have to operate the cluster like the hotel. You have to run the whole damn thing. Otherwise, you can't actually make a market. It doesn't work. You can't do physical settlement.

</details>

### 物理结算的经济悖论与巨额利润诱惑

**主讲人**：那么，为什么全行业没有人在做物理交割呢？核心症结在于，市场上存在着一股极其强烈的经济激励，诱导大家永远不要去碰物理结算交割。这是因为，如果你为了算力交易去从零构建一套完整的物理结算能力，其字面含义实际上就等同于你在亲手搭建一座 GPU 云服务商的全部全栈运营能力。而一旦你拥有了 GPU 云的完整运营能力，你最理性的商业选择显然就是直接去当一家传统的 GPU 云厂商——因为摆在眼前的现实是，做 GPU 云可以赚到天文数字般的暴利。你随随便便就能签下一笔又一笔价值数十亿美元的超大订单。于是大家的心理自然就是：“何必费力去搞什么中立的算力交易市场呢？我们直接变现成为一家 GPU 云厂商不好吗？”这正是行业里几乎所有参与者最终的选择，因为背后的商业金额极其惊人，做出这种选择也是完全合情合理的商业决策。

<details>
<summary>Original English</summary>

**Speaker**: So why does nobody do physical settlement? The problem is there's a very strong incentive to never do physical settlement. That's because if you build out physical settlement for compute, what that literally means is you're building out the entire operating capacity of a GPU cloud. And if you are building out the entire operating capacity of a GPU cloud, you should just be a GPU cloud because it looks to be the case that you will make an ungodly amount of money. You will sign billion dollar deal after billion dollar deal. And so, let's not make a compute market. Let's instead just become a GPU cloud, which is what basically everybody does because the numbers are astronomical and it's a very reasonable thing to do.

</details>

**主讲人**：而我们之所以最终下定决心去构建物理结算体系，是因为我们深知：如果我们不率先把这套底层机制搭建起来，我们后续就根本无法去开创我们真正梦寐以求的 AI 实验室。创办一个领先的 AI 实验室，原本才是我们最渴望做的事；但如果不先解决物理结算这个前提条件，我们压根连做实验室的资格都没有，因为你瞬间就会被信用风险（credit risk）的枷锁死死卡死。

<details>
<summary>Original English</summary>

**Speaker**: The reason why we ended up building physical settlement was because we knew that if we didn't start this, we would then not be able to start an AI lab, which was the real damn thing that we wanted to do in the first place. We wanted to make a lab. We didn't get to make a lab unless this exists. A credit risk problem.

</details>

### 融资门槛飞涨与信用枷锁下的初创公司灭顶之灾

**主讲人**：接下来的现实是，算力集群的规模变得越来越庞大，进入这个赛道的最低准入门槛（minimum ante）也水涨船高。起初入场门槛可能是一亿美元，现在已经飙升到十亿美元。我们认为这种疯狂的态势根本不可能持续下去。现实世界中绝不可能存在这样一种常态：你连哪怕一分钱的营业收入、哪怕一点业务增长势头（traction）、甚至连成型的产品影子都还没有拿出来，就能够一上来随随便便融到一轮 100 亿美元的巨额资金。这就意味着，如果你不从根源上解决这个难题，按照目前的轨迹发展下去，整个 AI 领域将彻底不会再有任何初创公司的生存空间。

<details>
<summary>Original English</summary>

**Speaker**: Then the cluster sizes got bigger. The sort of minimum ante into the space got bigger. Then it was 100 million. Now it's a billion. We don't think it can continue. We don't think there is a world in which you can get a $10 billion round right out the bat before you raise—before you have revenue or traction or your product or anything. And what that means is that if you don't solve this problem, we are currently on track to not have any startups in AI.

</details>

**主讲人**：现在，很多人可能会产生一种天真的设想：市场上或许能涌现出新型推理公司以及新型模型实验室，而他们解决信用瓶颈的办法，不过是顺水推舟地把信用风险全盘甩给应用层。他们可以说：“你看，我必须化解我自身的信用风险。所以我的策略是：我只接纳拥有投资级信用评级（investment grade credit）、比如财富 500 强（Fortune 500）级别的企业客户；我只与签署五年期 Token 采购长约的客户签约；我只向那些愿意提前支付巨额预付押金的客户供应 Token。”如果真走到这一步，那就是全行业的末日。一旦推理层被信用门槛彻底卡死，所带来的后果就是：除非你拥有极高的企业信用评级，或者你兜里掏得出巨额现金押金，否则你连最基础的 Token 算力都买不到。

<details>
<summary>Original English</summary>

**Speaker**: Now one of the things that you could think could happen is maybe there can be new inference companies and new model labs and the way that they solve the credit problem is that instead they just ship the risk to the application layer. They say look, "I need to get over my credit problem. So what I'm going to do is I'm going to only sign customers who are investment grade credit, Fortune 500. I'm going to only sign customers on five-year contracts for tokens. I'm going to only sign customers for tokens that require a big deposit upfront." That is the end of everything. If you have inference layer getting bottlenecked by credit, what happens is you can't get tokens unless you have credit or you have a big deposit.

</details>

**主讲人**：这一问题的严重性在于，智能 Token 是整个现代经济肌体都在普遍消耗的基础生产要素。没有任何一条自然法则规定初创企业就必须天然存在。如果所有初创企业仅仅为了获取智能计算能力，就突然全部被卡在信用门槛之外，最终的结局就是现有行业巨头全面通吃。巨头们凭借自己雄厚的信用等级，能够毫无阻碍地获得充足算力并做出成品；通过这些产品，他们赚取滚滚收入，而这些收入又进一步夯实增厚了他们的信用评级——这种马太效应飞轮将推动整个经济社会走向彻底的集中与垄断。如果你不去打破这个算力信用瓶颈，世界上将不再会有任何创业公司的存活之地。这正是我们当初毅然决定投身于此的根本原因。因为我们预判在未来三到五年内，你环顾四周如果想创办一家新公司，为了能够与现有的巨头同行竞争，你必须采购规模庞大的 Token 算力——你需要一口气购买高达一亿美元的 Token。我们认为，这正是你未来想要创办一家新企业所必须跨越的真实门槛，因为你的对手们正在毫不眨眼地砸出数以亿计的资金去购买算力……

<details>
<summary>Original English</summary>

**Speaker**: And the problem of that is that tokens are used by the whole damn economy. There is no rule that says that startups have to exist. If every startup is suddenly bottlenecked by credit in order to access intelligence, what happens is existing firms just ship everything. They themselves get to make the product because they've got credit and then they make the revenue from that product and then it makes their credit better and that's a flywheel that makes consolidation happen throughout the entire economy. If you don't fix this bottleneck, there aren't any startups. This is why we started doing this and because at one point or what we think is going to happen is you're going to end up in like three to five years you're going to look out and say I want to start a new startup and to get there you need to buy so many tokens in order to compete with the existing partner or like existing players. So you need to buy a hundred million dollars of tokens. We think this is what you are actually going to have to do in order to start a new company because other people are spending hundreds of millions of dollars of...

</details>

<!-- chunk 16/51 -->

### 初创企业的算力困境与行业整合风险

**Speaker A**：Token（代币/标记）。如果你把这条发展曲线直接往后推演，现实就会演变成这样：你需要缴纳一笔极其庞大的保证金，因为你们只是两个甚至连自己在干什么都还没彻底搞清楚的人，根本没有人信任你们。于是，你只能硬着头皮去找风险投资人募集 1 亿美元。

<details>
<summary>Original English</summary>

**Speaker A**: tokens. If you just draw the line out, this is what happens. So, you need a big giant deposit because you're two people who have no idea what they're doing and so nobody trusts you. So, you're going to go and raise $100 million from your venture capitalist.

</details>

**Speaker A**：与此同时，根本没人愿意跟你们合作，因为你们只是一家仅有两名员工的初创小公司。接着，对方会要求你们为那 1 亿美元买单，或者要求你们就这 1 亿美元签下一份长达五年的捆绑合同——如果你没法把这笔钱全额当作保证金一次性付清的话。这样一来，市场上就再也不会涌现出新的模型实验室，再也不会诞生新的初创公司。整个行业将不可避免地走向高度整合与垄断。

<details>
<summary>Original English</summary>

**Speaker A**: Um, meanwhile, nobody wants to work with you because you're a two person startup. Then, you're going to be asked to pay for um that hundred or you're going to be asked to pay for a five-year contract on that hundred million. um if you're not paying it all as a deposit and then you just don't get new model labs, you don't get new startups. Um you get a consolidation in the industry.

</details>

**Speaker A**：我们曾经也在某个时期是这样一家名不见经传的小实验室。当时我们住在旧金山，认识所有其他同行——他们同样也是各自只有两三个人的小团队，刚刚创办起步，一心渴望能参与到这个时代最重磅的技术浪潮之中。

<details>
<summary>Original English</summary>

**Speaker A**: So we at one point um uh were this little lab um and what we did is we lived in San Francisco um and we knew all the other people who were also just two little folks um who had started a startup and wanted to be able to participate in the most important technology of our time.

</details>

**Speaker A**：因此，我极度渴望这群人能够继续生存下去。我希望这个人能生存下去，希望那个人也能生存下去；我希望这家初创公司能够存活，那家初创公司能够存活，还有这家初创公司也能够存活——这家、那家、还有这里的一家又一家公司。如果能让这些初创公司顺利运转起来，说不定他们未来就会成长为行业巨擘，研发出治愈癌症的方案，或是创造出此前从未有人想到的惊艳成果，而不是仅仅造出一堆粗制滥造的 AI 垃圾内容（AI slop）。这正是算力市场（compute markets）试图解决的问题。如果不去解决它，我们认为未来根本不会再有任何初创生存的空间。太棒了，这部分就到这里。

<details>
<summary>Original English</summary>

**Speaker A**: Um, so I want these people to exist. I want this person to exist and I want this person to exist. I want this startup to exist and this startup to exist and this startup to exist. This one and this one and this one and this one and this one and this one and this one and this one. If you get these companies going, maybe they'll become big folks that build your cancer cures or they build something that nobody thought of um or something that wasn't just sort of AI slopped out. This is kind of the problem that compute markets solve. And if you don't solve it, uh we don't think there's going to be any startups. Cool. That's it. That's Heat. Heat. N. Hey, hey, hey. Heat. Heat. Heat. Heat. Heat. Heat. N. Heat. Heat. Hey. Hey. Hey. Heat. Heat. Oh, there we go.

</details>

### 算力交易与“算力暗池”

**Afon**：好的，我想我们现在可以正式开始了。大家好，我叫 Afon，目前在自营高频交易巨头 Jump Trading 负责算力交易业务，站在我身旁的则是我的共同主管 Alejandro。今天，我们将一起深入探讨算力交易所适用的市场微观与宏观结构，厘清所谓的算力到底是什么、我们预见它将如何演化，并先从宏观视角审视微观结构，随后再聊聊我们对相关监管政策的看法。

<details>
<summary>Original English</summary>

**Afon**: All right, I think we can get started here. Um, hey everyone. My name is Afon and um I'm a lead for compute trading at Jump Trading which is a proprietary trading firm alongside my co-lead over here Alejandro. So today we're going to be looking over some of the market structure as it applies to compute trading, what computing even is um what we can see it becoming and I think we'll start with some macro look at micro structure and then talk a little bit about where we see things in policy.

</details>

**Afon**：本次演讲的主题是“算力的暗池”（The Dark Pools of Compute）。现场有一些做金融背景的朋友可能会疑惑，我为什么要借用这个术语？我在这里说的“暗池”究竟指的是什么？本质上，我指的是一个不透明、未公开挂牌的场外市场（an unlit market）。目前绝大多数物理算力交易都是大宗整块（in blocks）进行的，依赖私下内部报价，充斥着大量的中间经纪商（brokers），并且几乎全都是点对点的长期双边合约。

<details>
<summary>Original English</summary>

**Afon**: So the title of the talk is the dark pools of compute but some of you guys are in finance so you might be confused as to why I'm using this terminology. Uh what do I mean by dark pool here? Essentially what I'm referring to is an unlit market. Um right now most compute trades in blocks physical compute here and these are private quotes. We have a lot of brokers and these are long bilateral contracts.

</details>

**Afon**：归根结底，这些交易本质上都是商业法律协议。我们在这里之所以借用“交易”这个词，只是为了分析各参与方之间是如何达成交易的。这些商业协议通常包含主服务协议（MSA）、服务等级协议（SLA）以及订单表格（order form）的混合体，针对每个具体的机群和特定的硬件条款量身定制。然而，当我们考察定价逻辑及其他指标时，大部分讨论的核心都聚焦于硬件型号（SKU）——即底层芯片本身以及主板类型，比如 H100、H200、B200/V300 等等。

<details>
<summary>Original English</summary>

**Afon**: Now, at the end of the day, these are really commercial agreements. So, we're using the term trading here to kind of like look at how it's transacted between parties. These commercial agreements tend to be some mixture of an MSA, an SLA, and an order form, cluster specific uh with hardware specific uh language in each kind of um in each order. And but when we're looking at pricing and looking at some of these other kind of uh metrics, a lot of the time most of the talk is around the skew. So what the chip itself is the baseboard. So H100, H200, V300, uh etc.

</details>

**Afon**：因此，大量的交易磋商完全发生在公众视野之外。当今世界上并没有一个被大众广泛采用、所有人都上去查看行情并撮合交易的物理算力公开交易所。所有的交易都是在即时通讯聊天软件里完成的，彻底避开了公开视线。尽管市面上存在一些公开市场、价格参考指数以及很多按需计费（on-demand）的算力平台，但针对这类具有固定期限、锁定明确容量且涉及巨额合同总价值（TCV）的定期算力合约，其交易过程全都是在 Slack 私信、X 私信、Telegram 群组以及各种各样的场外交易（OTC）渠道里完成的——我喜欢把这些渠道戏称为“新式聊天室”。在座有些人可能熟悉大宗商品交易，知晓很多能源与商品交易都是在 ICE Chat 或彭博聊天室（Bloomberg Chat）里敲定的，当下的算力市场几乎就处于一模一样的状态。

<details>
<summary>Original English</summary>

**Afon**: And so um a lot of the negotiation here happens kind of outside the public view. There's no, you know, like exchange for physically traded compute that's widely, you know, adopted and, you know, used for everyone goes there to like take a look and trade uh compute. These are done in chats, right? They're out of the public view. Um there's public marketplaces, there's price references, there's a lot of um you know, on demand marketplaces. However, for these actual tenored, so you know on a given term for a fixed amount of capacity uh with a certain total contract value, these trade over Slack messages, X messages, Telegram group chats, there's a bunch of OTC kind of channels that are all over in these kind of I want to call them like Neo Neohat. Um and some of you might be familiar with commodities and how a lot of you know there's chatting happening on ice chat, Bloomberg chat, etc. This is kind of where where the where the kind of markets here lie.

</details>

### 宏观市场结构、Token 成本与杰文斯悖论

**Afon**：接下来，我想从宏观视角剖析一下当前的市场结构，顺便梳理一下其中的核心参与者。这里引用的是 a16z 最近发布的一张图表，你们可能有人已经见过了。我把它拿出来展示，是因为大家随时可以去 a16z 的官方 X 账号查看原图。图表直观地揭示了一个事实：获取同等模型能力的成本正在断崖式下跌。当然，最终的账单金额依然取决于具体的模型调用量、集群容量以及处理速度等其他因素——特别是最新一代代码生成和 ChatGPT 推理模型，速度已经成为极为关键的考量点。

<details>
<summary>Original English</summary>

**Afon**: And so I want to look a little bit here on the macro market structure and a little bit on the players here as well. And so this was a recent kind of uh A16Z. Some of you guys might have seen this. So I'm I'm putting this out there because you know you can go on A16Z's uh actual X and take a look at this graph yourself. What we're looking at is that the cost of a given capability has fallen sharply. Um the bill of course still depends on the model usage capacity and other factors such as speed is a big thing right now with the new code uh chatbt models.

</details>

**Afon**：更便宜的 Token 费用释放了更庞大的使用需求，技术团队在相同的预算规模下能够完成多得多的工作。我们清楚地观察到，大量团队开始成倍地狂刷 Token。这意味着市场上存在着此前尚未被充分满足的潜在潜伏需求，大家在模型单价高昂时期所拥有的预算，如今会被全部倾注进去消耗掉数量更加庞大的 Token。那些曾经因过于昂贵而无法落地的实际应用场景，现在全都变得切实可行了。

<details>
<summary>Original English</summary>

**Afon**: Um, cheaper tokens unlock more usage and a team can do more work for the same budget. So what we're seeing is that a lot of teams are simply just using way more tokens. So, we have this latent demand that hasn't really been hit yet and people are just going to use more with the same budget that they were using before when models cost more. Um, and they're just expending more tokens. Um, so applications that were too expensive become possible.

</details>

**Afon**：然而，正如我们在此探讨的算力底层本质，即便完成某项单一任务的成本大幅下降，底层支撑所需的庞大硬件容量依然必须有人先行建造并支付账单。因此，这里存在一个必须严格区分的核心概念边界：其一是机器智能的定价，其二是人类想要执行的任务总量，其三则是为了支撑这些任务运行所必须采购部署的硬件物理总量。

<details>
<summary>Original English</summary>

**Afon**: Um, however, as we're kind of talking about compute here, the capacity underneath still has to be built and paid for u even as the cost of a particular task comes down. And so, the important distinction is between the price of the intelligence, the number of tasks people want to run, and the amount of hardware needed to serve them.

</details>

**Afon**：这就引出了所谓的“杰文斯悖论”（Jevons Paradox），也是我们近期重点跟踪研究的现象。我们观察到了一种极为耐人寻味的背离走势：在直觉上，人们通常会想当然地假设算力采购价格与推理调用价格是同向波动的，彼此之间应该保持极高的强相关性。但正如数据所示，两者之间出现了明显的脱钩现象：Token 的单价在进一步狂跌，而底层算力的租借价格却依然居高不下、坚挺异常。我们该如何合理解释这种脱钩呢？

<details>
<summary>Original English</summary>

**Afon**: And so this is where we get to kind of the Javons paradox and a little some of the stuff that we've been looking at lately where we had a very interesting thing where you know intuitively you'd assume um that compute and inference kind of like rises together correlates very you know very closely as you can see you can see there's a little bit of a decoupling that happened and token prices declined further but compute prices remain robust and so like what what can be an explanation for this

</details>

**Afon**：市场上存在许多种潜在的推导解释，其中核心的依据就是杰文斯悖论：即使借助全新一代主板和 GPU 架构，单位 Token 和推理服务的服务效率得到了极致的提升，但由于用户的使用总量呈爆发式暴增，导致对物理算力的综合总需求反而急剧上升。即便输入端、上下文缓存以及输出端每百万 Token 的成本大幅下降，用户消耗的总体 Token 绝对值却激增了无数倍。单项任务单价的大幅降低，刺激了远超预期的额外使用量，进而完全抵消了单项任务所节约下来的硬件资源。对于推理云厂商而言，这意味着他们可以托管更多的应用、输出海量的 Token 并夺取更庞大的市场份额；对于上层应用开发者来说，这意味着任何基于 Token 基础设施构建业务的人，都能够覆盖服务数量极其庞大的终端客户群体。

<details>
<summary>Original English</summary>

**Afon**: Now there's a lot of like potential explanations. one here is the whole Javon paradox is that even though token prices and inference is getting extremely efficient to serve on these new uh baseboards and and and GPUs, people are just consuming a lot more and so the demand for compute rises and people just consume a lot more tokens even if the cost per uh cost per million uh uh for input and for caching and you know for output becomes a lot more efficient and so making the task cheaper encouraging the additional use to outweigh resource saving for tasks uh for inference clouds that's going to mean more applications serving more tokens uh bigger market share um and for app layer individuals that means you guys can serve to a lot more kind of customer so anyone who's building utilizing the token uh infrastructure

</details>

### 上游硬件、电力基建与资本投入

**Afon**：那么，回到宏观结构本身，究竟有哪些核心生产要素构成了这一切的底座？这里梳理出来的框架非常基础、直接：首先是芯片，这是我们一直在谈论的核心；其次是电力供应；然后是数据中心建筑机房、电网互联接入；最后，你还需要极其充沛的资本支持来驱动这些大规模基建工程的落地运转。这也是眼下全行业热议的真正风口。

<details>
<summary>Original English</summary>

**Afon**: and so what really goes into um you know the macro structure now like this is very you know bare bones here but you've got your chips which we've been talking about uh you have power you have buildings grid connections and then of course you need a lot of capital to get these buildouts going. And then that's kind of been the whole talk here.

</details>

**Afon**：芯片、电力、机房建筑以及资本，所有这些环节必须无缝协同、合兵一处，最终才能转化为你能够在账单上购买到的每一小时真正可用的单 GPU 算力时长。根据国际能源署（IEA）4 月份发布的最新预测报告，全球数据中心的总用电量将从 2025 年的 485 太瓦时（TWh）一路激增至 2030 年的 950 太瓦时。因此，目前行业中最密集的讨论无一例外全都围绕着基础设施建设和电网布局展开：我们现有的电网容量真的能够跟上吗？我们是否能够接入利用其他新型替代能源？我们到底去哪里才能圈到足够的建设用地来落地这一切？

<details>
<summary>Original English</summary>

**Afon**: And so um chips, powers, buildings, money, they all have to come together before you know you can even get to an hour of like actual usable GPU per hour compute. And so the IEA April update projects that the glob global data center electricity is going to rise from 485 terowatt hours in 25 um to 950 and 2030. And so a lot of the talk right now is around um buildouts about getting the power grid set up. Will we have enough power grid here? Is there other energy sources that we can tap into? Um where are we, you know, able to get the land to actually be able to do this?

</details>

**Afon**：因此，主机代管站点（colocation sites）、数据中心运营商、负责项目融资与工程建设的参与方，包括提供信贷的放贷机构本身，都在严密审视这一连串环节。处于算力上游的一切供应链变量，最终都会层层传导至下游的算力采购成本及其使用方式之上。那么，隐藏在底层的真实宏观版图究竟是什么样子的？正如业内引述所言：芯片与系统厂商提供 GPU 服务器与网络设备；而机房场地与运营商则负责提供电力保障、物理空间、集群组装与日常运维管理，就在这里的这些 GPU……

<details>
<summary>Original English</summary>

**Afon**: And so collocation sites and data center operators and people who are doing the financing, the buildout, so the lenders themselves are all kind of looking into this. And that type of uh everything that's upstream essentially of the compute is going to then flow down into the compute uh costs and also usage. And so what does this like actual macro map look like underneath a quote uh chip and system vendors supply the GPU servers and networking sites and operators supply the power um space assembly and management right here GPUs

</details>

<!-- chunk 17/51 -->

### 算力供应链生态与终端用户

**Speaker**: 在算力价值链中，涵盖了内存、服务器与网络等环节。接下来是算力提供商（Capacity Providers），包括超大规模云厂商（Hyperscalers）、新型云服务商（Neoclouds），以及任何业务模式类似于新型云的运营商——他们通常通过转售裸金属算力来提供服务。再往下则是实际的终端用户：初创公司、推理云平台（Inference Clouds）、AI实验室与新兴实验室（Neolabs），还有处于应用层的所有开发者，以及部署开源权重模型的各类企业。虽然我在这里把它们分别框定为不同的模块，但在实际产业中，许多参与者可能同时兼具上述多种角色。例如芯片与系统供应商，完全有可能进行全栈端到端的建设，同时自己又是这套设施的终极终端用户。因此，在具体的商业实践中存在相当多的重合与变化。

<details>
<summary>Original English</summary>

**Speaker**: ...memory, servers, and networking. Capacity providers: these are hyperscalers, neoclouds, and any other operator that's operating similar to how a neocloud would operate, reselling bare metal capacity. And then the users: so who's the actual end user? The startups, the inference clouds, labs, neolabs, and also anyone on the app layer, and enterprises for anyone doing open-weight stuff as well. And these boxes—like I've kind of boxed them out here, but there's people can be all of the above. A chip and system vendor, someone could do a full end-to-end buildout and also be the end user of everything. And so there's a little bit of variation that occurs here.

</details>

### 推理云的商业模式与中端市场的融资困境

**Speaker**: 正如我之前谈到推理云时提到的，它们可能会先租用一个集群，通过对外提供 Token 生成服务来获取收入，再用这笔收入去偿还租用集群的费用。这构成了推理云自身的一种典型用例。然而，对于超大规模云厂商、前沿实验室以及规模较大的新型云服务商而言，他们有能力做出极其重大的长期承诺，因为他们能够募集巨额的股权资金，承担更多的债务，并且有能力签署期限极长的商业大单——例如像 OpenAI 签订的那种为期十年的长期采购合同等等。

**Speaker**: 可是，处于中端市场（Middle Market）的企业实际上根本无法做到这一点。有哪家机构愿意为一个 B 轮阶段的初创公司提供担保，让其背负一份为期 3 年、价值超过 2 亿美元的算力采购合同？为了支撑这样一份合同，他们需要进行多少轮股权融资？难道他们要将整轮股权融资所获得的资金全部投入到这一个集群的预付支出中，以至于账上根本没有剩余资金去维持实际的日常运营成本吗？

<details>
<summary>Original English</summary>

**Speaker**: And so as I was kind of mentioning about the inference clouds before, they might rent a cluster and they'll serve tokens off of it and they'll use that revenue to pay off the cluster. And so that might be a use case for the actual inference cloud themselves. However, for hyperscalers, Frontier Labs, and larger NeoClouds, they can make substantial commitments because they have the ability to get into the large equity, they have the ability to take on more debt, and they have the ability to do long-horizon deals—so 10-year deal, OpenAI contracted out, etc., of that nature.

**Speaker**: However, anyone in the middle market isn't actually able to do this. Who's underwriting a series B startup with enough capacity to get into a 200 million plus contract over 3 years for compute? How many equity rounds will they have to raise? Right? Will they have to use their entire equity round to fund just the actual cluster and then they don't have any remaining capital left to use for actual costs?

</details>

### 算力基建融资链条与预付款错配

**Speaker**: 这促使我们深入探讨算力融资链条的运作逻辑及其在整个生态中的作用。在很多情况下，即使针对推理云，放贷机构（Lenders）也是根据其已锁定的合同收入来为算力基础设施建设提供资金支持的。放贷方愿意为基建建设提供融资，但前提是他们必须确信自己的贷款能够得到全额偿还。对于一家初创公司，尤其是一家尚未上市、目前没有其他显赫背书的私营企业，你该如何对其进行承销审查呢？他们并非上市公司，没有大量可查的现金流、资产负债表或损益表，甚至可能还处于“未盈利”（Pre-profit）乃至“未商业化”（Pre-revenue）的阶段。因此，放贷方唯一看重的是：该企业能否在达到特定规模时获得有约束力的合同收入。

**Speaker**: CoreWeave 的公开申报文件为我们提供了一个极具代表性的大规模范例，展示了以“照付不议”（Take-or-pay）客户合同为担保的基础设施融资机制。我们展示的图表则给出了一个相对小规模的说明性范例。当前市场核心的结构性错配在于：硬件基础设施融资方希望获得非常长期的锁定周期；然而客户要么无力承担，要么主观上极度抗拒被套牢在长达 36 个月以上的融资承诺中。根据 CoreWeave 公布的数据，他们观察到的客户预付款中位数通常在 15% 到 25% 之间。这意味着对于一个总合同额（TCV）达 1 亿美元的算力集群，初创团队必须在项目启动之初就预先掏出 1500 万到 2500 万美元真金白银的预付款。对于一家初创公司来说，这几乎可能抽干他们整轮融资的所有资金。

<details>
<summary>Original English</summary>

**Speaker**: And so we're looking into a little bit of the financing chain here and how that plays in. So lenders are financing the buildout against contracted revenue, even in many cases for inference clouds. And so they want to finance the buildout; they want confidence that their loan will get repaid. I mean like how are you going to underwrite a startup like a private company that doesn't have much else going for them right now? Like what are the—you know, they're not publicly traded, there's not that much cash flows, balance sheet, income statement. They might even be pre-profit, pre-revenue, etc. And so what they're looking at is that can the person get contracted revenue over a certain scale.

**Speaker**: And so CoreWeave's public filings give large-scale example of infrastructure financing supported by take-or-pay customer contracts. And so this diagram kind of shows the smaller illustrative example here. And the mismatch is that hardware financing, they want very long terms, but customers are only able to afford or don't really want to get into a long-term financing over 36 months. They have to put up—15 to 25% is what CoreWeave has quoted that they've seen their median prepayment to be. 15 to 25% upfront on a 100 million TCV cluster. That's 15 to $25 million that a startup has to put up front. That might be their entire round.

</details>

### 阶梯式容量扩展与按需算力的填补选择

**Speaker**: 让我们来看一个具体的案例推演：假设你刚刚募集了 4000 万美元资金，需要签署一份为期 3 年、总额 1 亿美元的算力合同，并支付 30% 的预付款。这是一笔 3000 万美元的巨款，直接导致你手里只剩下可怜的 1000 万美元去维持公司的实际业务运转。正如图表所呈现的那样，你的算力供给呈现出阶梯函数式的跨越：高耸的水平线代表你锁定的合同容量，而实际客户需求往往处于该容量之下。随着业务推进，每当你需要扩容至一个新集群时，扩容动作都会被硬性绑定到你的下一次股权融资或其他资本运作上。但如果算力打满、出现供给上限，你可能就不得不直接拒之门外，流失客户。

**Speaker**: 在这种境遇下，你究竟有哪些抉择？你是选择直接把客户挡在门外，苦苦等待下一轮股权融资到位，以便再凑出 30% 的预付款来解锁下一阶段的少量算力？还是选择借助“按需算力”（On-demand Compute）来弥补缺口，填补阶梯过渡期未覆盖的空缺？按需模式如今已成为一个现实选项，但此时你必须仔细核算其背后的经济账：两者的成本效益差异究竟如何？初创团队是否可以转向借贷方来专项资助这部分预付款？如果贷款融资预付款所产生的资金成本低于在公开市场上直接采购按需算力的溢价，并且市场上有足够的现成容量可供采购，那么借贷预付款的方案在商业逻辑上是否成立？

<details>
<summary>Original English</summary>

**Speaker**: And so this is kind of a look at what I'm referencing here. It's like you're raising 40 million, you need 100 million contract over three years, you put down 30% prepayment. This is an illustrative example. You've got 10 million left to run the business. And so you might have this kind of step function as you can see here. So that's your contracted capacity and what you can actually, and the demand is, you know, below that. And so now every time that you have to get into a new cluster, it's like tied to your equity round or whatever else it may be, but you might have to cap out and turn away customers.

**Speaker**: So what are your options? Do you either turn away customers until you can get into your next equity round so you can put down another 30% prepayment so you can get next little bit of capacity going, or do you use on-demand to close the area under the gap and bridge the shortfall? That's like an option now. Now you have to look into the economics. What does that look like? What's the difference between, you know, maybe instead what they do is they go to a lender to finance the prepayment component, but if the yield on the prepayment component that they're getting financed is less than them just buying it out on demand at that time, if they're able to get into that amount of capacity, then does the economics make sense there?

</details>

### 自建自营、主机托管与承购合同的权衡

**Speaker**: 在行业实践中，我们观察到了几种主流的运营架构模式：第一种是全栈自建并自主运营硬件站点。你的内部团队全权负责电力调配、审批许可获取、硬件装配调试以及后期的运维管理。第二种是在主机托管设施（Colocation Facility）中持有服务器所有权，并将大部分组装、网络布线与日常运维交由专业的托管合作伙伴处理。第三种模式则是签署“承购合同”（Offtake Contract），即按约定购买明确规格的算力容量，由算力提供商全权持有并运营底层资产。在此模式下，服务商可能不会向你开放针对裸金属服务器的完全 root 访问权限；或者根据具体的租户架构（如单租户或多租户配置），对你的系统访问权限设置不同层级的管控，而这些技术配置差异也会直接体现在最终的定价结构上。

**Speaker**: 不同的企业对核心要素的偏好各不相同：有的企业极其看重物理层面的可触达与深度控制；有的企业高度重视机密计算（Confidential Compute）能力；还有的企业对底层网络拓扑的灵活性及软硬件系统重构能力有着严苛要求。如果这些掌控力对业务至关重要，他们就可能倾向于自建自营以获得最高控制权。考虑到单纯采用租赁承购合同可能错失的隐性机会成本，他们往往愿意为此支付更高的溢价，这在商业层面是成立的。

<details>
<summary>Original English</summary>

**Speaker**: And so here's some of the operating models that we've seen is like you can build and operate the full stack hardware site. Your team is going to arrange power, permit, the assembly, the management. You can also own servers in a collocation facility with more or less the assembly and operation handled by a partner. On the other hand, an offtake contract buys defined capacity and the provider is going to own and operate the asset and they might not give you complete root access to the bare metal or there might be kind of like levels to how much access you get depending on if it's tenant, multi-tenant and etc. type of like configurations that can also affect the pricing.

**Speaker**: And so some businesses are going to value the physical access. Some businesses are going to value confidential compute. They might value certain topology changes or the ability to reconfigure the system. And so if that is something for their business and they might actually want to have more and more control and build and operate the stack, and the economics for them might make sense given the opportunity cost they would have to give up if they were to just take rental offtake contracts. So they might be willing to pay more there.

</details>

### 拥有成本与租赁成本的动态平衡

**Speaker**: 我们不妨用一张相对简略的趋势图来直观对比随着利用率（Utilization）上升，硬件自持与算力租赁之间的成本曲线走势。从常规逻辑来看，很多长期承购合同的总开销，已经逼近了自主建设并融资部署一套专属集群的成本。这是显而易见的：假设你在三年周期内要硬性支出 1 亿美元，那么在排除部署所需的时间成本以及后续不可避免的运营维护复杂度之后，如果单看经济模型，直接出资买断算力运营资产往往更加划算。

**Speaker**: 在宏观上存在一个必须遵循的动态均衡点：在低利用率阶段，纯自持的高昂固定成本远高于短期租赁开销，此时租赁成本应当稳定地落在自持总成本之下。但是，一旦你的算力利用率突破了某一临界阈值，并且伴随着高度波动但持续攀升的业务需求，直接拥有整套全栈算力资产反而会成为综合效益最优的策略。

<details>
<summary>Original English</summary>

**Speaker**: And so here's how like ownership and rental—this is a very crude graph—how ownership and rental can compare as utilization rises. And so what we're looking at is that usually an offtake contract—are these offtake contracts are getting to the cost of actually almost building out and financing your own cluster. And it's not because I mean if you're spending a hundred million over a three-year period, then maybe if the economics make sense, it would have made more sense to simply buy out the compute operator yourself outside of the time cost and then obviously the operational cost that might exist.

**Speaker**: So there's an equilibrium that exists that that has to be followed where the ownership costs outweigh the rental costs, and the rental cost should sit below the ownership cost. But if you're utilizing at such a rate and in such variable kind of increments, it might be best to just own the stack outright.

</details>

### 算力采购对跑道的影响与市场微观结构

**Speaker**: 这种演进在资本与创业生态中引发了深刻的新变局：算力采购决策与执行策略，已直接决定了一家处于高速成长期的公司究竟具备多长的生存跑道（Runway）。这也正是为什么如今的一级市场风险投资人（VC）开始极为深度地介入企业的算力采购环节。从风险投资的视角来看，算力的准入渠道、付款周期与预付条款，直接决定了被投组合企业的现金消耗速率。协助被投公司锁定适配其发展阶段的算力容量，能够从底层实质性提升该笔投资的安全边际与回报预期。

**Speaker**: 这种紧密联动的诉求，促使投资机构不仅亲自协助被投公司对接并锁定算力资源，更催生了算力市场从宏观资本结构向精细微观结构的全面演进。随之而来的关键问题在于：究竟由谁来撮合这些巨量算力的交易布局？市场上各家提供的算力报价如何进行客观公允的对标？这些标准化或非标合同又各自实现了哪些维度的风险转移？

**Speaker**: 围绕着“GPU 机时”（GPU Hour）这一核心交易标的，市场上涌现出大量不同类型的专业参与者，共同塑造着这片全新的金融与交易微观市场。首先是价格发现机制（Price Discovery）的构建者：他们搭建价格指数、沉淀交易数据并发布权威基准，供业界实时参考。未来，市场完全有可能基于这些经过批准的标准化规格与参考基准，衍生出挂钩的算力期货合约（Futures）。紧接着是物理层面的算力匹配交易场所、竞价拍卖机制以及聚合平台：任何具备算力撮合能力的主体都在快速卡位。我们正在见证针对按需算力的去中心化交易市场的崛起，涌现出一批能够提供高流动性算力池服务、自主切分并制定标准化交易合约的流动性池运营方，以及面向底层裸金属资源的专业交易平台……

<details>
<summary>Original English</summary>

**Speaker**: And so we're seeing this new dynamic that compute—the compute procurement affects how much runway a growing company actually has. And so this also gives investors an interest in compute procurement. So we're kind of seeing this access and payment terms affect how much runway their portcos are going to have from a VC perspective. So helping a company buy a suitable capacity can improve the underlying investment, and they're very connected, right? So they're able to procure, and they're able to actually find compute capacity for their portcos and fund that. And so that also brings another interesting aspect to the macro structure into the microstructure: is that who helps place the capacity, and how does this offer get compared, and what risk these contracts can transfer?

**Speaker**: So we have a lot of different players around this GPU hour that are helping kind of shape this market here. You've got your price discovery individuals: so people with indexes, data, the benchmarks that we're all looking at right now and referencing, which would be used to, you know, in the future launch the futures based on the benchmarks talked about in the associated contracts per spec pending approval. And then there's the physical matching venues, auctions, aggregators. So anyone who can match capacity—we're looking at essentially decentralized marketplaces for on-demand compute. You're looking at liquid pools of compute that offer like liquid pool services and parted out themselves and have their own standardized contract. You're looking at bare metal...

</details>

<!-- chunk 18/51 -->

### GPU 算力二级转售与场外经纪机制

**Speaker A**: 分销商与转售商方面，我们既能看到新型云服务商（NeoClouds）自身在进行更大容量的算力销售，也能看到裸机算力转售领域活跃着大量独立的经纪人和独立算力运营商。

此外还有专门的撮合经纪人（Brokers）。他们专注于双边报价与订单执行。他们往往人脉广泛，能够快速行动。他们可以在一个地方看到配置规格高度相似的报价，同时敏锐地意识到市场上正有一位对价格极度不敏感的买家急需算力投入计算，而经纪人能够及时帮其争取到可供服务就绪状态（RFS，Ready For Service）。因此，经纪人可以在这笔交易中赚取相当可观的买卖差价（spread）。

随后他们要做的是进行算力源头的谈判，承担并安排风险敞口。他们必须为客户运营该算力集群，且最终必须证明所赚取的差价是物有所值的。

<details>
<summary>Original English</summary>

**Speaker A**: resellers. You're looking at NeoClouds themselves doing larger capacity sales. And then you're looking at individual brokers and individual operators here as well on the bare metal reselling. You have Destined Brokers. They're looking at the bilateral quotes and execution. They might know a lot of people. They might be able to move fast. They might be able to see quotes at very similar specs in one place and know that there's a buyer that is extremely inelastic to price right now needs to compute immediately and they can get the RFS in time so they can charge a decent spread on it. And then what they do is they're going to have the source negotiating then they're going to be carrying and placing the risk. They're going to have to operate that cluster for the person and it has to be worth that spread.

</details>

### 金融衍生品、对冲工具与非标资产特征

**Speaker A**: 观察金融市场，基于 GPU 机时（GPU hour）的期货与衍生品交易平台正在涌现。人们开始借助这些工具探索如何对冲风险，并研究更深入的金融架构——例如对冲资产负债表风险，或者达成更有意思的商业协议。

我们看到类似预付款融资便利（prepayment payment facilities）这样的协议正逐步上线；我们看到人们正在利用或表现出强烈意愿去利用期货及其他期权工具，市场对于通过这些工具对冲现有账面风险有着切实的需求。

在买方（buy side）方面，机构和客户正在寻求弹性合同（flex contracts）：例如探讨如果我绑定一份 3 到 5 年的长约，当新芯片架构上市时，我能否至少升级算力？或者是否允许我展期？或者是否允许我再卖回给你？紧接着就是信贷与结构化融资——设备放贷方、设备租赁商以及专业的信贷机构纷纷介入。

目前整个市场的现状是：每一笔交易几乎都是完全定制化的（bespoke）。各个供应商的规格清单（spec sheets）五花八门，格式各异；物料清单（BOM）很可能与实际交付内容不匹配，或者一旦某个零部件缺货、延迟，交付方案就会随之调整；同时，部分 OEM 和 ODM 硬件厂商的交付交付周期（lead times）极其漫长。

在节奏极快的商务谈判中，同一个术语可能指代完全不同的含义。如果有人提到“内存”（memory），究竟是指显存（VRAM），还是指主机 CPU 内存？抑或是指外挂附加存储？这里究竟具体指什么？这会对所能运行的模型工作负载类型、最终用户的实际需求、甚至采购定价与交付排期产生巨大影响。

<details>
<summary>Original English</summary>

**Speaker A**: And you know you have looks in financial markets, the exchanges that are coming that are based on the GPU hour, the futures and derivatives. People are going to be using it to take a look at how to maybe hedge out and look into more financial structures, so hedge out risk, so hedge out balance sheet risk, maybe get into more interesting agreements. We're seeing kind of agreements such as prepayment payment facilities are coming online. We're seeing people utilize futures and or interested in utilizing futures and other kind of options to be able to—there's demand for this to be able to hedge out the risk that they currently have on the books.

We have buy side individuals looking for flex contracts, flexible contracts like, "Hey, is there ability that if I lock myself in a 3 to 5-year contract that I'll be able to, you know, at least upgrade when a new chipset comes out, or maybe I'll be able to roll it over, or maybe let me sell it back to you?" And then there's credit and financing: equipment lenders, leasers, specialist credit providers.

And so the way we're seeing it right now is that every deal is bespoke. There's different spec sheets, there's formats, the bill of materials may not match the actual delivery or there might be subject to change if a part is missing or a part is out of stock, and you know there's like very long lead times that some of these OEM and ODM kind of providers have. And the same term can mean different things when you're negotiating very quickly. If someone's talking about memory, are we talking about VRAM? Are we talking about the CPU memory? Talking about additional storage here like what did you exactly mean there? It affects quite a bit what type of loads can be run and the actual end users' needs and also with pricing and delivery dates.

</details>

### 暗池市场特性与算力结构性错配

**Speaker A**: 因此，在各方真正能够进行横向比价之前，需要经历大量的反复沟通与博弈。这正是“非同质性”（non-fungibility）概念切入的地方，以及如何对其进行细分切片：哪些部分是可以标准同质化的（fungible）？哪些部分占据了绝大部分权重（例如芯片 SKU 型号等）？而哪些部分依然只能像特定电商独立产品那样交易——即该定价仅仅适用于那一套具体的集群？

正因如此，市场价格可能每天都在更新，甚至变动得更快。公开报价仍是一个不错的谈判起点，但买方出价（bids）可能遭遇砍价削减，硬件机架的完备度与配置繁复程度也会改变供应实质。这其中交织着各种隐性因素，这也是我们将其称为“暗池市场”（dark market）的原因。

这里展示了一些公开截取的 H100 参考定价快照，我今天对其进行了最新更新。如果大家登录各家网站查看，这些就是公开参考基准。这里只是一个示例，展示了当下市场上典型的 H100 公开按需（on-demand）或现货（spot）定价形态，你能看到各种各样不同的价格区间。人们可能会参考这些公开基准，也可能基于内部掌握的行情来做预估，或者据此为自己特定规格的集群进行定价，同时把涉及其中的所有其他要素综合考量在内。

那么，为什么行业迫切需要这些新型结构，这些微观结构（microstructures）的吸引力究竟何在？其核心目的在于解决各种结构性错配：算力容量的跨期过桥、更具弹性的长约承诺、二级转售权，以及针对剧烈价格波动的风险保护。

举例来说，站在一家推理云（inference cloud）服务商的视角，你向客户销售的是固定价格的推理服务，而你底层的 GPU 算力采购账单却是浮动成本，这直接造成了价格风险敞口。通过锁定数年的长期算力容量可以解决部分问题，但如果你的业务不能始终满载运行，又会在其他时段造成大量的闲置机时（idle hour）闲置浪费敞口。将多余的闲置算力对外转售固然是个出路，但前提是市场上必须有买家能在那个时刻恰好消纳这些机时。此外，纯金融层面的对冲虽然能基于基准价格结算现金差价，却无法在物理层面立即交割一套真实集群，也无法保障实际业务的物理利用率。因此，一个真正行之有效的商业架构，必须紧密立足于企业自身所承担且需要对冲的具体风险来设计。

<details>
<summary>Original English</summary>

**Speaker A**: So there's a lot of back and forth before anyone can really compare, and this is where the concept of like non-fungibility kind of comes into place and how to partition that out. What parts can be fungible? What parts hold the most of the weight such as the SKU etc., and what parts are still like traded as if it was a product, e-commerce, etc. where it's only for that particular cluster that this price applies. And so prices can update daily or faster. Quotes still a good starting point. Bids can get chopped. Hardware complexity changes what's on offer. There's all these kind of latent factors, hidden factors as well, why we're calling it a dark market.

These are some public H100 references snapshotted. Today I updated them. So take a look at what the public—so, those are the references for if you wanted to go on their websites to see. This is just an example here of like what a public on-demand or spot pricing looks like for an H100 today. You can see kind of various prices here. And so people might use this or they might use their own kind of internal what they've seen to actually like assume or use it to charge what they want to charge on their actual cluster specification, taking into account every other kind of factor that goes into it.

And so why are these new structures kind of needed and what are these micro structures interesting? It's mainly to solve for these mismatches, right? Bridging capacity, more flexible commitments, resale rights, and protection against price moves. You know, you're selling a fixed price service from an inference cloud point of view. You'd be selling a fixed price service while the GPU bill floats, and that creates price exposure. And so locking capacity for years can solve a part of that, but it'll create idle hour exposure elsewhere as well, unless they're always using it. Reselling spare capacity only helps if someone actually can buy the hours. A financial hedge can address a reference price but can't deliver the cluster right now in terms of cash settlement or guarantee a utilization. So the useful structure has to start with the particular risk that the business has and needs to manage.

</details>

### 监管政策、腰部市场痛点与资产负债表破局

**Speaker A**: 鉴于时间有限，在政策这一部分我将讲得相对精炼一些。方才讨论的所有内容，实际上都置身于一个受到严格监管并以多种形式受到政策直接影响的框架之中。

其核心体现之一便是出口管制。举例而言，今年 1 月美国商务部将针对中国及中国澳门符合条件的 H200 级芯片出口许可审核调整为附带条件的逐案审批（case-by-case review）。此外，开源权重（open-weight）模型将监管政策重新拉回至美国宏观经济层面——这一点始于美国人工智能行动计划（US AI Action Plan），该计划明确鼓励开源与开放权重 AI，并建议完善算力金融市场，以便初创企业和学术研究机构能够获取大规模计算能力。

我在此做个总结收尾：未来的核心机遇究竟蕴藏在哪里？

我们面对着一个正在迅速扩张的中端腰部市场（middle market）。我们迫切需要能够桥接买方与供应商双方需求的坚实资产负债表。整个行业必须建立起一定程度的标准体系：标准化的容量合同、通用的硬件规格标准、统一的交付条款以及公认的术语定义。

对于那些处于成长阶段的企业而言，其算力需求与承诺期限根本无法匹配超大规模云厂商（hyperscalers）和前沿基础模型实验室（Frontier Labs）所签署的那种严苛长约。这些公司拥有真实的业务工作负载，我们期待他们成长壮大，但他们至今仍深陷融资瓶颈、交付时序错配以及硬件规格难以标准化的多重困境中。

从供应方来看，为了支撑机房前期的重资产建设（buildout），供应商需要买方给出长期的采购承诺；而从买方视角出发，由于下游需求极具波动性，遵循特定的业务消耗曲线（runoff curve），买方更希望随着需求逐步明朗，以更小批量的模块逐步扩容；买方急需一种机制，避免为自己当前尚未具备能力消纳的闲置容量买单。

因此，市场上那些具备雄厚资产负债表、其资产表现与整体市场波动不相关（uncorrelated）、且凭借强大的信用评级能够准确评估与承揽此类风险的参与机构，能够有效填补买方真实诉求与供应商服务供给之间的巨大鸿沟。

要实现这一点，绝不仅仅是简单提供一个 GPU 机时报价，它意味着必须深刻理解实际落地交付、底层工作负载等一整套工程与金融逻辑。当前市场上能够胜任这一角色的玩家屈指可数。而一位极为契合的赋能者，正是一家与外部市场波动不相关、拥有强劲资产负债表、顶级信用评级、并在内部坐拥惊人高性能计算（HPC）底层硬件专业人才储备的专业机构。

因此，我在这里向各位发出行动倡议：让我们携手共同构建这一基础设施！非常感谢各位前来聆听我们的演讲！

<details>
<summary>Original English</summary>

**Speaker A**: And I'll go pretty fast on this policy section because we're running out of time. Everything sits inside of a structure that is regulated and is affected by policy in various ways. One way is export controls. One of the examples in January the US Commerce Department moved qualifying H200 class license reviews for China and Macau to case-by-case review with conditions. Furthermore, open weight models connect policy back to the US economics was started with the US AI Action Plan explicitly encourages open source and open weight AI and recommends improving the financial market for compute so that startups and academics can access large-scale computing power.

So I'm going to tie this out right here. But where's this opportunity lie? We have this growing middle market. We need balance sheets that can bridge buyer and supplier needs. There needs to be some level of standardization, a standard capacity contract, common specs, common terms and definitions. And so growing companies whose needs and commitment do not fit the contracts the hyperscalers and Frontier Labs can sign. Those companies have real workloads. We want them to grow. They still face this financing problem, a timing problem, a specification problem. A supplier might want the long-term commitment for the buildout while the buyer wants to expand in smaller blocks as demand becomes clearer as it's so volatile, runoff curve. The buyer needs a way to avoid paying for capacity it can't use yet. And so participants with strong balance sheets that are uncorrelated with the market and the ability to assess those risks with a strong credit profile can help bridge the gap between what buyers need and what suppliers offers.

That requires more than quoting the actual GPU hour. It means understanding the delivery workload all of that. And so there's very few kind of players in the market. And you know, a very well suited player can be a firm that's uncorrelated with market with strong balance sheet, strong credit rating, and incredible amounts of hardware talent that sits inside for high performance computing. And so just making a CTA here. Let's build this together. Thank you guys so much for attending our talk.

</details>

### 计算资源交易中枢与中立市场定位

**Speaker B**: 太棒了！好的，祝大家周四愉快！看到台下坐得这么满真是太棒了。

**Speaker C**: 呃，今天其实是周三，周三啦。

<details>
<summary>Original English</summary>

**Speaker B**: All right. Happy Thursday. I like how full this room is.

**Speaker C**: Uh, it's Wednesday. It's Wednesday.

</details>

**Carmen Lee**: 噢抱歉，我显然走在大家前面去了！周三愉快！我的名字是 Carmen Lee，我是 Compute Exchange 以及 Silicon Data 的首席执行官。

我非常喜欢上一场分享环节，他们深入探讨了整个产业生态——包括各类融资方、现货市场交易员以及风险对冲者。而我们所处的赛道位置非常酷：我创办了 Compute Exchange，这是目前全球唯一专注于 GPU 算力采购的中立交易市场（neutral marketplace）。

我们在 2024 年创立这家公司，当时市场上大概只有 5 家新型云服务商（NeoClouds）和 3 家超大规模云厂商（hyperscalers）。从本质上讲，我们相当超前且敏锐地预见到了 GPU 产业生态的全面大爆发。

大家可以类比一下当今的股票市场。当你想买卖股票时，你显然可以打电话给经纪人；你可以给几家投资银行打电话说：“我想买卖一定规模的特斯拉股票，或者 SpaceX 的股权。”你可以选择通过电话经纪去完成，也可以直接打开手机 App 在纽约证券交易所（NYSE）或纳斯达克（NASDAQ）上直接下单撮合成交。

但这并不意味着你在纽交所或纳斯达克就一定能拿到绝对最优的价格，仅仅因为……

<details>
<summary>Original English</summary>

**Carmen Lee**: Oh, sorry. I'm clearly ahead of everybody here. Happy Wednesday. My name is Carmen Lee. I'm the CEO for Compute Exchange as well as Silicon Data. I love the previous session. They talked a lot about the whole ecosystem: the financiers and the spot market traders and the hedgers. So what we're sitting in is really cool. I have a company Compute Exchange, the world's actually the only neutral marketplaces for GPU procurement. We started in 2024 when there were, I don't know, five NeoClouds, three hyperscalers. Essentially we sort of foresaw, interesting enough, the proliferation of the GPU ecosystem.

So you think about stock market today, right? When you try to buy and sell stocks, you can call brokers obviously. You can call a few banks to say, "Hey, I want to buy and sell x amount of Tesla or actually SpaceX, right?" And you can do that, or you can transact through your app at NYSE or NASDAQ. Doesn't mean you get the best price at NYSE or NASDAQ just because...

</details>

<!-- chunk 19/51 -->

### 算力交易的流动性与撮合效率

**Carmen**: 这样交易会更具效率，而且流动性也会更有保障。你知道交易最终能够顺利结算，能够完成清算。你能够以期望的价格，以极高效率的方式获取自己所需的资源。对于资本市场而言也是如此，资源配置的核心本质就在于效率。因此，在算力领域，显然我们如今看到了前所未有的蓬勃爆发与大规模扩张，这固然是一件大好事。目前全球范围内涌现出了超过300家新型私有云服务商（Cloud Providers），我们拥有大量的 Token 工厂，还有不计其数的 API 路由分发器。这一切对最终客户来说当然是非常有利的，但与此同时，这也引入了一个非常值得探讨的变量：我们究竟该如何让算力交易变得高效？

<details>
<summary>Original English</summary>

**Carmen**: It's more efficient and you know the liquidities will be there. You know the trade will be settled. It will be cleared. you can get what you're looking for at the prices you're looking for in a very efficient manner right for capital markets and resource allocation is about efficiency so in compute world obviously now we have a huge proliferation which is great we have over 300 new cloud private provider globally we have a lot of token factories we have a lot of API routers which is all good for end customers but at the same time introduce a very interesting variable is how do we make transaction efficient right

</details>

**Carmen**: 难道大家真想逐个打电话去联系300多名销售人员吗？我的意思是，去结交朋友当然很好，你可能也想经常和他们交流，他们确实了解很多行业资讯。但与此同时，当你需要在接下来的48小时内通过预留合约（Reserve Contracts）获取算力时，最简单直接的方法显然是前往一个交易平台，直接去对接那些经过严格认证的算力资源——就如同去纳斯达克（NASDAQ）购买股票一样简单明了。这正是我们 Comput 平台做得极其出色的一点：我们构建了这样一个中立的交易平台，而且在底层设计上，我们坚持自身不持有任何 GPU。

<details>
<summary>Original English</summary>

**Carmen**: do you want to call 300 salespeople I mean it's great to make friends right you want to talk to them regular basis they know a lot of things but same time when you need compute in the next 48 hours on reserve contracts is the easiest way is go to an exchange and then go to the verified compute resources just like go to NASDAQ and I to buy stocks right so this one of the things computing does extremely well is we have this neutral platform and by design we do not own GPUs.

</details>

### 中立交易所定位与双向风控机制

**Carmen**: 一旦我们自己开始购入并持有 GPU，那就好比纳斯达克交易所自己持有上市公司股票一样，会直接转化为我与终端客户以及我与算力供应商之间的巨大利益冲突。这样我便可能会去挑肥拣瘦、偏袒某些客户或关系户。正是因为 Comput 在架构设计上完全不持有任何底层硬件资产，我们才能与全球各地的所有算力供应商建立起极其融洽的合作关系。另外极其关键的一点是，我们对每一笔交易都进行逐一独立处理，这意味着我们的目标是为终端客户匹配最合适、最契合需求的算力资源。我们的核心业务重点放在预留算力远期合约（Reserve Compute Forward Contracts）以及 Token 算力包上。

<details>
<summary>Original English</summary>

**Carmen**: Once we start owning GPUs that will translate to just like NASDAQ owning stocks translate to I have a lot of conflict of interest with you and with the providers. I could cherrypick clients right. I could relationships because comput does not own anything by design. We work really well with all our providers globally. Um and one very very important thing is we treat every single transaction individually meaning we want to find you as end customer the most suited compute resources and we focus on reserve compute forward contracts as well as token packages.

</details>

**Carmen**: 给大家介绍一下我们目前的整体业务概况：截至目前，我们已经汇聚了超过100家经过严格认证的供应商，供应网络中涵盖的 GPU 算力规模已超过80,000张卡。我们的网络覆盖全球所有核心区域（显然中国大陆地区除外）。我们承诺提供24小时的极速周转交付。我们与市面上那些所谓的算力经纪商（Brokers）之间最本质的区别在于，我们对每一台 GPU 都会进行真实的物理和性能验证。如果是现有的预留容量（即硬件设备已经处于实际可运行的状态），我们会逐一核验 UID、库存真实性以及性能跑分；我们会亲自运行英伟达 DGX 推理套件和 XL perf 基准测试工具，以确保你最终拿到手的算力资源完全符合承诺的标准。

<details>
<summary>Original English</summary>

**Carmen**: So give you some um high level. So today we have over 100 verified providers um and over 80,000 GPU in supply. We cover all regions obviously exchina. Um our commitment is 24 hours turnar around. The difference between us and other so-called brokers is we do verify GPUs. If it's existing reserve capacity meaning things are actually in a functional stage we'll verify the UIDs the inventories the performances we run Nvidia DGX inference XL perf make sure you get resources you promised to get

</details>

**Carmen**: 因此，我们扮演的是一个值得信赖的中立枢纽平台。而如果涉及的是未来远期完全交付的容量——比如你计划从2027年1月1日开始租赁 GPU——我们则会深入审核采购订单、数据中心建设与运营所需的全部许可证及合规批文，确保从尽职调查层面为你把关。反过来讲，如果你是一家新兴的云算力服务商，你最头疼的问题往往是：面对海量蜂拥而至寻找算力的客户，你如何才能判定谁具备按计划费率按期付款的真实履约能力？这就是 Comput 发挥价值的地方：我们对客户全面执行严格的企业资质背景调查（KYB）与身份认证（KYC）。你显然希望确保你的客户确实如其声明的那样具备信誉与实力，因此我们介入其中完成这种双向核验，正如任何成熟的现代金融交易所职责所在一样。我们在远期市场上所做的一切，本质上都是在为未来真正实现物理实物交割的期货合约奠定前置基石。

<details>
<summary>Original English</summary>

**Carmen**: um so we're the middle middle sort of trusted platform so if it's full capacity let's say you need GPU starting Jan 1st 2027 we actually look through the purchase all the permits they get make sure you know we help you do the due diligence level on the flip side right if you're a new cloud your concern is there's a zillion clients looking for compute how do you know who has the ability to pay at a schedule rate that's what computers comes in we do KYB KYC of the clients obviously you want to make sure your clients is the clients you think they who they are so we step in and do that kind of verification just like any exchange would do and Everything we do in the forward markets is actually the precursor to physically delivered futures.

</details>

### 从能源做市到算力物理期货模型

**Carmen**: 这里也顺便向大家交代一下我的个人背景以及我目前所从事的工作。抱歉，我可能一开始就应该先说明这一点的。我的职业生涯起步于芝加哥的著名自营交易巨头 DRW Trading，当时我是担任能源期权做市商（Energy Option Market Maker），在那儿扎扎实实做了四到五年。作为能源期权领域的做市商，很多底层金融逻辑是非常直观且通透的：在石油大宗商品市场里，你既有 WTI 原油，又有布伦特原油（Brent），对吧？WTI 是典型的实物交割型大宗商品合约，而布伦特原油则是纯现金结算合约。两者具有截然分明的应用场景：如果你追求的是纯金融意义上的对冲工具，旨在平抑价格波动与成本波动风险，你通常会选择布伦特合约；但如果你需要的是真正去采购并提取实物资源，那你就会使用 WTI。我们在 Comput 正在打造的，正是算力世界里的 WTI。

<details>
<summary>Original English</summary>

**Carmen**: Also give you some context where I am, what I do. Sorry, I probably should say that I start my career as energy option market maker um at DRW trading Chicago. So I did that for four or five years. So as option energy market maker everything's very intuitive. You have WTI, you have Brent, right? WTI is a physically delivered commodity contracts. brand is cash settled. They also have very distinct use cases. You're looking for hedging in the financial sense, right? The your price volatility, your cost volatility, you're going to rent. You're looking physically procure resources, use WTI. So, we're creating the WTI at comput.

</details>

**Carmen**: 目前通过 Comput 交易所采购算力主要有几种形式：你可以获得预留合约（Reserve Contracts），也可以获得针对 GPU 底层硬件以及 Token 层的远期合约（Forward Contracts）。让我稍微展开解释一下：GPU 硬件层面的远期合约非常合情合理，因为你可能需要在未来的某一特定时间点锁定算力资源，而当前当下并没有闲置可用的现货，这就是我们常规化持续开展的核心业务。而 Token 远期合约对不少人来说可能是一个相对较新的概念。大家基本上可以将其理解为一种专属部署或者类似本地化的专用推理实例部署——就像你预留裸金属 GPU 集群一样，你锁定了一个硬件集群，但在其上运行的是完全为你独家部署的专属 Token 生成环境。这样一来，你就能针对特定模型获得确定性的 SLA 服务质量保障，模型量化精度等各项关键运行参数也会在约定租期内为你完全固化。我们正是通过这种机制，来攻克按需计费的 Token API 在价格波动与性能抖动上的顽疾痛点。

<details>
<summary>Original English</summary>

**Carmen**: So the ways to buy compute through uh comput change right now you can get reserve contracts you can get four contracts on both GPU and token let me explain the four contracts on GPU is very reasonable right you want something starting in the future nothing available right now so that's something we're doing on regular basis token forward I think can be a newish concept basically can think about as um a dedicated deployment on premise deployment right similarly you reserve a bare metal GPU clusters you reserve a cluster but you have dedicated token deployment on top of that so you get guaranteed um SLAs for that particular models you get um quantization precision everything's fixed for you for a period of time so we try to solve the ondemand token API volatility pricing problem here

</details>

### 二手硬件流转、转售退出与市场撮合运作

**Carmen**: 第三个板块是，我们拥有一个规模庞大的公开硬件交易市场（Open Hardware Market），这其实非常引人入胜。二手服务器交易业务始于去年，当时有很多人直接通过私信联系我说：“嘿，Carmen，我在某某数据中心闲置了大概两万张 H100，你能帮我接手处理掉吗？”我当时的反应是：“天哪，我自家客厅显然不可能堆得下这么多服务器。”于是，我们顺势推出了针对二手服务器买卖的二级交易平台。在过去大概12个月的时间里，这个市场展现出了极其惊人的交易活力与流动性。我们再次覆盖了各类主流服务器规格，甚至连最新的 B200 也已经在二级市场上出现了真实的转售交易，有些成交价甚至一度高于官方建议零售价（MSRP）——这其实完全合情合理，就像疫情期间二手车的交易价格往往会溢价超过全新原厂车的官方指导价一样。

<details>
<summary>Original English</summary>

**Carmen**: the third is we have a huge market open hardware market it's really interesting The secondary server transaction started last year when people just peding me say hey Carmen I have like 20,000 H100 sitting X data center can you take away from me so I was like I don't know I can't store in my home obviously so we started having the marketplace for secondary server sales this has been a very vibrant market um for the past I would say 12 months uh we cover again all servers um even B200 you see secondary transactions is happening um sometimes trading above MSRP right can make sense think about like co times when secondary cars trading above right it's a brand new car price

</details>

**Carmen**: 总结下来，我们整体覆盖了算力市场的这三大核心层级。首先在预留 GPU 方面，前面那位演讲嘉宾其实已经将各项合约条款阐述得非常透彻了。我们平台支持的起订门槛极低，最低起订标准为一个节点（1 Node），租期从一个月起步，并且最长完全可以延展支持三年、四年乃至五年不等的长期合作。这完全取决于供应商的资源供应现状，但你在我们平台上有充分的机会明确表达你所有的定制化诉求与偏好。需要说明的是，我们并不做突发型的按需即用（On-demand）算力。此外，Comput 还有一个备受用户青睐的强大优势，那就是我们提供极具弹性的退出机制：假设你在采购时在算力规模或租期时长上过度承诺、买多了，你完全可以随时将这些多余的算力挂牌转售回 Comput 交易所！这是我们向市场做出的坚定承诺，因此即使你偶尔超额采购了，也完全不必过度恐慌。

<details>
<summary>Original English</summary>

**Carmen**: so we covered the three major um layers of compute so reserve GPU obviously I think the previous speaker covered extremely well with the terms the minimum we do is one node starting at one month and then we can go all the way to three for five years, right? It's all depends on the availability, the providers, but you get a chance to state your preferences. Um, we don't do on demand. And another thing really works really well for comput is we do provide a flexibility. Let's say if you overcommit it in terms of quantity or duration, you can sell it back to computer exchange, right? So that's something we commit to do. So you don't have to worry too much if you overbought.

</details>

### RFQ 询价机制与透明化履约生态

**Carmen**: 好的，接下来进入现场实操环节，我稍后会为大家带来一段简短的产品演示。目前我们在平台上拥有海量的在线挂牌资源，你可以直接浏览并与供应商在线沟通交流，从而探讨出最理想的交付架构方案。同时，如果在现有公开挂牌中没有找到合心意的资源，你也可以直接发起询价流程（RFQ）。我们现在每个月接收到的 RFQ 询价规模实际上已经突破了10亿美元。这个数字听起来很庞大，但身处算力行业的我们都很清楚，对于整个 AI 算力大盘来说这其实也不算天文数字，对吧？但真正让我感到振奋的是那种旺盛的市场活跃度——我们看到的 RFQ 需求跨度极为宽广，从单个节点一直延伸到两万个节点的超大规模集群都有涵盖。我们的客户背景多元、形态各异，对应的应用场景与业务诉求也千差万别，这实在令人感到欣喜。

<details>
<summary>Original English</summary>

**Carmen**: All right, segment live. So I will actually do a quick demo later. Um, so we have a lot of listings, marketplace listings. You can browse and chat with the providers and figure out the best delivery mechanisms. You can also RFQL if you don't see anything in light you liked. We actually seeing over a billion RF killed every month. Sounds big, but we all know it's full compute. It's not that huge, right? But still you see the the the the uh activities which I love is we see a big range of RFQ requests from one node all the way to 20,000 nodes. So our clients are you know all different shapes and forms different use cases which is great.

</details>

**Carmen**: 你只需要设定好交付时间要求并提交需求单，我们就会在底层进行智能路由分发。在后台，我们部署了实时的动态库存追踪系统。凭借全球超过100家核心供应商的网络，我们非常清楚谁在什么时间点拥有怎样的远期可用容量。举个例子，假设你提交了一笔采购申请：“嘿，我需要从明年1月1日开始，在美国东部部署300张 B200 GPU。”我们在系统后台筛选后发现有三家供应商完全契合该标准，我们就会将需求精准路由分发给这三家。他们会直接通过平台向你提交响应方案，并提供包含详细技术规格、定价参数以及 SLA 协议等级在内的标准化评估细则（Rubric Specs）。如果涉及的是已上架的现存服务器，我们还会附带严格的跑分基准数据。

<details>
<summary>Original English</summary>

**Carmen**: Yeah. So you set timing submit and we route it. So in the behind the scene we have inventory tracking. So with over 100 providers globally we know who has what roughly when right the forward capacity and then let's say you you submit a requesting that hey I need 300 GPUs B200 US East starting gem first we say you know we have three providers we think they have those we'll router to the three they will respond to you through the platforms and give you um a rubric spec pricing specs SLAs's we benchmark them if it's existing servers

</details>

**Carmen**: 最终的拍板决定权完全掌握在你手中。我们坚信价格从来都不是唯一的衡量指标，我们的职责是尽可能为你呈现最高的透明度与最全面的信息，由你自主作出最合理的商业决策。所有往来记录都会集中沉淀在一处，你收到的都是标准化的评估模板，所有指标一目了然。我们会直接促成你与供应商之间的直接引荐对接，我们绝不会刻意卡死阻断双方的合作关系，确保你清晰地知道自己在与谁打交道。这就好比用今天的锁定价格采购明天的确定性算力，它是一个以实物交付为终局导向的严谨采购平台。在二手及翻新 GPU 领域，我们汇聚了令人振奋的活跃生态参与者，涵盖从各类机架规格到顶尖的 B200 以及 AMD 算力卡等全线硬件，库存数据全天候实时更新。

<details>
<summary>Original English</summary>

**Carmen**: And then it's your choice right price is not only indicator we believe give you as much transparency as we can and then you will make a decision. So I record in one place again it's rubrics coming back you will see everything and we introduce you to each other we never hold relationships right we'll make sure you know who you're dealing with um so by tomorrow's computer today's price so it's a physically procured platform this is the use refurbished um GPUs so again we have a extremely um exciting u ecosystem participants in this eos uh in this uh secondary GPU else we cover from phone IO's D to B200 AMD everything inventory is live

</details>

**Carmen**: 与此同时，我们支持通过各类灵活渠道与大家保持沟通协作，无论是 Slack、电子邮件还是在线聊天工具，完全依照你最习惯的工作方式进行对接。我们进行全链路端到端的追踪管理。事实上，我们对平台上的每一个参与方都建立了一套评分考核机制：我们既为作为客户的你们打分，也为供应商进行信誉与交付评级。虽然这套评分体系目前大家还暂时无法完全看到，但未来全面公开后肯定会非常有趣。到了年底，我们还将为所有表现杰出的供应商举办盛大的年度颁奖盛典，我们将评选出“亚太地区最佳供应商”、“欧洲最佳供应商”、“美国最佳供应商”以及“最具敏捷响应力供应商”等重磅奖项。接下来会有大量精彩的供应商年度大奖陆续揭晓，敬请大家保持期待与关注。

<details>
<summary>Original English</summary>

**Carmen**: and we do connect with you through all different channels Slack email chat however you want to do this um we track end to end we actually have scoring for everybody we score you our customers we score our providers you can't see it quite yet but you know we'll be really fun um we're going to have end of year celebration for our providers. We can we're going to give out the best provider in APAC, best provider in Europe, best provider in US, most responsive providers. So we're going to have lot of provider awards coming up. Stay tuned.

</details>

**Carmen**: 最后谈到我们的认证网络：我们网络中的一切资源都是经过严格核实验证的，而交易所本身就代表着经过充分协商达成的确定性履约机制。因此，我们在交易流程中切实充当着受信中间人的角色。在实际操作中，有时供需双方的条款细节可能并不够明晰透彻，而我们的使命就是居中协调，确保大家都能透彻理解行业内经过沉淀检验的最佳实践标准。

<details>
<summary>Original English</summary>

**Carmen**: Um verify network. So everything's you know verified which is you know negotiate state exchange. So we help in terms of be the middleman. Sometimes things are not very clear. We try to make sure people understand what's the best practices we have seen

</details>

<!-- chunk 20/51 -->

### 算力采购平台与规格配置

**Carmen Li**: 在整个生态系统中，我想快速带大家看一下我们的平台，我觉得看实际平台会更有意思。这就是我们的平台界面，大家可以看到大量可用的算力库存。顺便提一句，任何人都可以注册，完全免费，使用我们的服务没有任何门槛或弊端。您不必立刻购买，可以先浏览，如果您对某些我们目前没有的资源感兴趣，还可以发起询价（RFQ）。您可以从选择供应商类型开始。同样，我们对 GPU 类型保持中立，您可以自由选择芯片型号、部署方式、GPU 数量。您还可以选择计算互联偏好、CPU 平台、存储配置，以及您所需的一切。随后还有一些可选项目，包括系统、软件栈和区域选择。当然，如果您接受的话，我们非常鼓励您选择多个区域。您还可以添加头节点（head node），告知我们您的具体用例和任何定制需求，然后提交询价单。整个流程极其健全稳定。当然，如果您有任何反馈，请务必告诉我们。

<details>
<summary>Original English</summary>

**Carmen Li**: in the ecosystem. I'm going to quickly show you guys the platform. I think that's more fun here. So this is the platform. You can see bunch of available inventories. By the way, anyone can sign up. It's completely free. There's no downside using us. You don't have to buy. You can browse. You can request for quote if you, you know, interested something we don't have. You can start with your vendor type. Again, we agnostic of GPUs. You can select your model. You can select your deployment type. You can select number of GPUs. You can select your computer interconnect preferences, CPU platforms, stoages, everything you need. And then some optional items with systems, software stacks, regions. Obviously, we encourage you select multiple regions if you're open to that. You can add head nodes, tell us your use cases, anything you want and then submit RQ. So, this has been extremely robust and then we, you know, obviously we want to make sure um if you have any feedback, let us know.

</details>

### 算力期限结构与远期曲线

**Carmen Li**: 那么关于算力采购平台的部分我就先讲到这里。我看还有一些剩余时间，非常想给大家展示一下我们在期限结构（term structure）方面看到的一些数据。先补充一点背景信息：我是 Comput 的 CEO，同时也是另一家名为 Silicon Data 的公司的创始人兼 CEO。Silicon Data 相当于算力领域的彭博终端（Bloomberg for compute），我们为芝加哥商业交易所（CME）提供指数用于结算其期货合约，这将在几周后正式上线，我对此感到非常兴奋。即将在 CME 开始交易的品种将是 H100 Neo 云端按需费率以及 B200 的价格指数。我想给大家展示的是隐含远期曲线（implied forward curve）。正如我之前提到的，算力市场会涉及大量远期容量，因此本质上很多长期合约将变得极其关键，无论是在您的云架构还是最终用户层面都是如此。我把图表放大一点。黄色的线代表去年，横轴（X 轴）是期限长短，纵轴（Y 轴）是美元金额。去年黄色曲线完全是一条向下倾斜的曲线，这意味着你签的合约期限越长，每 GPU 核心每小时的单价就越便宜。

<details>
<summary>Original English</summary>

**Carmen Li**: So, I'm going to pause on the comput side. Um I think I have some time left which I love to show you. some of the numbers we see in terms of term structure also context I'm CEO for comput I'm also CEO for another company called silicon data so I'm a founder CEO for silicon data which is the bloomberg for compute so we provide indices for CME to settle their futures on which will be happening in a few weeks I'm very excited about this so the one that's going to start trading at CME will be the H100 Neo cloud on demand rates as well as V200 um prices. What I want to show you is imply forward curve. So as I said confusion would do a lot forward capacities. So essentially a lot of longerterm contracts is going to be very critical. You think about even in your cloud or your your consumers. Let me just make it larger. So the yellow line was last year, right? the the x the horizontal line is the duration and the dollar amount is the y axis. So last year was complete downward sloping curve from the yellow line, right? Meaning the longerterm contract you signed it cheaper, you know, was perchial per hour.

</details>

**Carmen Li**: 而到了今年，从年初开始整条曲线向上平移，并演变成了期货升水（contango）。大家看红色的线，这意味着人们在签订长期合约时无法获得足够的折扣，折射出市场预期未来的算力价格还会进一步上涨。现在大家看到整个期限曲线不断上移并逐渐变得平坦，意味着用户要么为长期合约付出溢价，要么只能拿到微弱的优惠。这是我们观察到的预留实例（reserved contract）情况。如果看隐含远期利率——这是计算得出的隐含远期利率，因为目前还没有真实的期货公开交易，这是基于我们的期限结构测算得出的，采用了与传统期货曲线相似的计算方法。大家可以看到，市场共识认为未来 36 个月内算力价格可能会继续攀升。当然，市场共识并不一定代表它绝对正确。再看 B200，去年它同样呈现升水结构，而今年整条曲线整体上移，每一个期限都变得更加昂贵，而且曲线同样趋于平坦。隐含远期利率同样显示，大家普遍预期价格会走高。我想指出这一点：期限结构表明 GPU 的行为特性与大宗商品完全一致，具备非常明确的期限结构风险，而算力期货正是极佳的对冲工具。

<details>
<summary>Original English</summary>

**Carmen Li**: And this year, starting early this year, the whole curve shift up and became contango. If you see the the red line, right? So translate to people not getting a discount enough discount for longerterm contract implies that people assume the price going to rise down the line. And now you see the price the ter whole term keep shifting up but got flattened right. So meaning people are now either get penalized or get you know awarded by some long-term contract. This is reserve contract we observe and if you look at implied for rates this is not this is implied for rates right because we don't have a future trading. So this is calculated based on our term structure um and we use similar methodology at tra futures curve. So you can see market consensus view is the price could go up next in in the future next 36 months. Again market consensus doesn't mean it's right. If you look at B200 again last year was contango and this year the whole curve shift up every single term is more expensive and it's got flattened. Right? In platform rates similarly people think the price gonna go up. I want to point this out.

</details>

### GPU 大宗商品属性与残值定价模型

**Carmen Li**: 这种期限结构清楚地表明，GPU 的表现就像各种大宗商品一样，存在着非常明确的期限结构风险，而数据期货则是出色的对冲工具。我们已经看到围绕这种期限结构出现了大量的大宗交易（block trading）。不妨设想一下：如果你的资产负债表上拥有服务器，在接下来的五到六年内背负着融资偿付义务，而你只在前三年签订了预留合同，那么你在第四、第五、第六年实际上就完全暴露在市场风险中，对吧？因此你需要通过互换协议（swaps）或大宗交易来对冲掉该风险。不仅如此，即使在你已经签下预留合同的前三年，也有相关的交易需求——万一预留合同发生违约怎么办？其他参与方能为你提供什么履约保证？所以我们看到围绕基准指数作为浮动利率开展的大宗交易。这张图表其实还被英伟达团队用于不同的场景，在英伟达最新的 9 月投资者日演示材料中，我们是他们引用的唯一数据供应商。这成为非常有趣的数据，并成为了几家银行对其资产负债表上的 GPU 服务器进行资产评估（appraisal）的依据。

<details>
<summary>Original English</summary>

**Carmen Li**: The term structure out is this shows you that GPU is behaves just like every commodity have a very clear term structure risks which data futures are excellent hedging. So we have seen a lot of block trading happening around the term structure. So you think about this right? If you have servers on your balance sheet, you have financing obligation for next five, six years and you have reserve contracts for first three then you exposed essentially year four, five or six, right? So you want to hatch that risk out by entering you know swaps or block trading. Um so those are things or or there there are trades happening even for the first three years which you have reserve contracts on. What if the reserve contract defaulted right? What's your um guarantee from some other players? So we saw block trading happening around indices treat as a floating rate. This chart um actually is being uh used differently by Nvidia team um in Nvidia's latest uh um September investor day deck they set us with only data provider they actually cited in their deck um this is very interesting data becomes the appraisal for a few banks when they have GPU servers

</details>

**Carmen Li**: 这里的每一个指标都是前瞻性视角下的现金流折现（DCF）。正如我所说，我们建立了期限结构体系。以 A100 为例：A100 已经面世了六年，如果你今天签署了一份针对 A100 的三年期长期租赁合同，确定了费率并将现金流折现回时间零点，你就得到了该资产当前的实际公允价值。当然，这里面包含了很多内生设定，比如利用率、成本构成等一系列假设，我们对这些假设保持相当透明。我们计算了全球所有 A100、H100 和 B200 服务器的归一化残值（residual value），然后将其与所有人通用的 5 年直线折旧法进行对比。非常有意思的是 A100：虽然它的曲线依然向下倾斜，意味着资产确实在折旧，但它的实际残值曲线始终高于会计上的直线折旧曲线；而 H100 显然更加狂热，价格甚至出现了上涨——我的类比就像疫情期间的二手车，价格不跌反涨；至于 B200，在当下其二手残值明显已经超过了官方建议零售价（MSRP）。这让大家能对当前的资产残值格局有一个宏观认知。我想我的发言时间已经到了，大家如果想交流，随时联系我，邮箱是 carmen@comput.com 或通过 secondary 网站；也可以在 Twitter 上找我，我的推特账号是 Carmen Li（@Carmen_Lee）。非常感谢大家。

<details>
<summary>Original English</summary>

**Carmen Li**: on their balance sheet um this everything you see here a forwardlooking you right so discounted cash flow so as I said we have a time structure so assume A100s right A100s have been around for six years if today you sign a three-year long lease on A100s and you have a rate and you discount the cash back to time zero you have how much the asset is worth right obviously there's a lot of things baked in utilization rate what is your cost there's a bunch of assumptions which we're pretty transparent about um we actually calculate the residual value for normalized value obviously across all A100 H100 B200 servers globally and then we'll compare that with the straight line depreciation which is everybody using the 5year depreciation what's interesting is the A100 right even though it is downward sloping but you know means the things are depreciating but it's above the accounting depreciation curve straight line and H100 obviously is you know it's going going bananas now and the price actually went up. My my analogy will be just like secondary cars during co time the price went up right and B200 obviously went above MSRP by this point. So this is gave some give you some views about what's going on the residual value side. I think I'm out of time, but you know, feel free to go at me Carmen CLI at comput.com secondary.com. Feel free to get me on Twitter. Carmen Lee is my Twitter handle. Just Carmen Ally. That's it. Thank you.

</details>

### AI Agent 从实验走向企业级落地的关键挑战

**Sharesh Khare**: 大家好。今天我想向大家梳理一下，我们该如何将 AI Agent 从实验阶段平稳过渡到真实的企业生产环境。在正式开始之前，先做个简短的自我介绍：我叫 Sharesh Khare，是 Intuit Credit Karma 的主任级资深软件工程师（Senior Staff Software Engineer），负责构建和主导公司的 AI 分析基础设施与服务。此外，我还担任多家机构的顾问、学术作者与研究员，也是多个专业组织的程序委员会成员，经常负责指导年轻的研究学者。好的，我们先来看一下今天的议程大纲：首先，我们要探讨在构建 AI Agent 并将其部署到生产系统时所面临的各项核心挑战，以及如何构建不同的框架来逐一应对这些挑战。

<details>
<summary>Original English</summary>

**Sharesh Khare**: Hello everyone. Um I would like to walk you through that how we can transition an AI agents from an experiments to the real enterprise environment. So before I begin a quick introduction about me. My name is Sharesh Kagar. I'm a senior staff software engineer at Init Karma where I built and own the AI analytics infrastructure and services. Um and beside that um I'm adviser uh author researchers um and also a program committee members for various organizations where I mentor the young researchers as well. All right. So let's uh walk through the um agenda here. So first we would like to talk about what are the challenges we have when we build an AI agents and deploy into the production systems and how we uh can build a different framework to address that uh different challenges here.

</details>

**Sharesh Khare**: 接下来，我们会解析其整体架构设计；然后讲解如何构建自研的 MCP 服务器（Model Context Protocol servers）、MCP 网关以及在网关之上配套的监控体系；随后，我们将深入探讨不同类型的 Agent 架构模式；最后，介绍一些用于状态记忆管理、请求追踪与质量评估、在数据进入大模型前过滤敏感个人信息（PII）以及优化上下文以节省 Token 开销的配套辅助框架。那么闲话少叙，我们直接来看面临的挑战：很多 Agent 在生产环境中遭遇失败，究其原因往往是缺失了基础设施级别的基础控制机制（foundation controls）。最关键的原因在于，多数系统缺乏一个标准网关来确保 Agent 能率先与网关通信，并在合法认证后接入正确的认证供应商，从而精准重定向到目标 MCP 服务器；第二点在于 MCP 服务器内部缺失了执行用户查询所需的适配工具；第三点在于是否配备了充分的调用链路追踪与评估系统，确保发往 Agent 的每一次请求都被完整记录，并对回复的生成质量进行严格评估？第四点是系统是否存在内存/上下文记忆管理机制——当用户与 Agent 开展多天或长周期交互时，它是否能够准确回忆起过去提过的信息？此外还有其他框架维度的考量，例如是否具备压缩和裁剪上下文以节省 Token 的优化手段，以及是否部署了足够严密的安全防护屏障，以防止任何凭据、密钥或机密泄漏给外部 LLM、追踪系统或监控链路。

<details>
<summary>Original English</summary>

**Sharesh Khare**: Um then how the architecture looks like for it um then um how you can build your own MCP servers um and MCP gateway and then some monitoring on top of that gateway as well. Um then further we're going to talk about what are the different type of agent framework you can have um and then um some additional framework around managing the memories tracking and eval um how you can block the PII data um going before the LLMs and then context optimizer to save your token right so without delay let's um let me walk you through the challenge um of course like there are many agents uh generally get failed in productions because their foundation controls are missing Um and the key reason behind is that um you know like oh most of the people are missing the gateway to make sure that the agent can you know communicate to the gateway to get authenticated first with the right all providers so that they can redirect to the right MCP servers right second that um MCP servers are missing the right tool to execute your query. Third, do we have like enough tracking and evaluation system to make sure that every query when you are sending to the agents whether they've been tracked or not and are you evaluating their quality response or not? Right? Do we have any in memory management system or not in terms of let's say you are doing the interaction with agent for long or for many days is it able to recall that what you have been asked in the past right and then there are other framework of course like do you have a context of measures to save the token or do you have enough protection in place to make sure that your any secrets should not go into LLM or tracking or tracing or any

</details>

<!-- chunk 21/51 -->

### 企业级 Agent 架构与核心支撑框架

**讲者**：内存数据库等各方面还有许多悬而未决的问题。为了解决这些挑战，在本次演示中，我们并不打算去凭空打造一个无所不能的神奇 Agent，而是重点探讨一套可以落地构建的完整框架体系。首先是 Agent 本身的框架，在这里我们选择使用 LangChain 社区提供的 LangGraph 框架。它能够帮助我们根据具体的业务提问构建专门的任务节点，并且非常便于接入各种插件市场、技能和提示词，从而确保智能体能够根据用户的查询做出高效的响应。

<details>
<summary>Original English</summary>

**Speaker**: Memory DB or so, right? So, lot of open questions. In order to resolve this, we are not going to build a magical agent here in this demo. We're going to talk about different frameworks that you can build to address this. So first is the agent framework. This is where we choose to use the LangGraph framework, which is provided by the LangChain community. This helps us in building the task-specific nodes based on your questions, and it is easy to plug in any marketplace plugins or skills and prompts to make sure that agents respond efficiently based on your query.

</details>

**讲者**：其次，我们还在构建 MCP 网关（MCP Gateway）。它的作用是确保每当智能体发起调用，或者该智能体名下的任何服务账号发起调用时，都能安全地在 MCP 网关完成身份鉴权，随后再被精确路由重定向至正确的 MCP 服务器。第三个关键部分是自定义 MCP，也就是你需要自行构建内部专属的 MCP 服务器，并配备恰当的工具集来执行实际查询。最后，还需要对实际执行的操作进行完备的审计跟踪。

<details>
<summary>Original English</summary>

**Speaker**: Further, the second part is we are also building the MCP gateway to make sure that whenever an agent makes a call, or any service account from that agent makes a call, make sure that they are securely authenticated to that MCP gateway and then get redirected to the right MCP servers. Third is the customized MCP, which means that you are building your own MCP servers with the right tools in place to execute your query, and then finally some audit on top of what operation you're actually performing.

</details>

**讲者**：此外，我们还会讨论一系列配套框架：例如如何拦截并阻断 PII（个人身份信息）及敏感机密；如何将追踪与评估数据存入云端；如何对上下文记忆进行持久化保存，尤其是跨各个上下文的线程（threads）与检查点（checkpoints）；以及如何全面优化上下文窗口，从而确保模型性能与成本得到有效控制。

<details>
<summary>Original English</summary>

**Speaker**: Right, and then we talk about some additional frameworks around how you can block PII secrets, how you're going to store the tracking eval into the cloud, and how you're going to persist the memories, especially any threads and checkpoints on every context, and then also how you can optimize overall your context to make sure that...

</details>

### 从开发者门户到脚手架仓库

**讲者**：现在来看端到端的工作流是怎样运转的。整个流程始于你的业务架构审查（architecture review）。架构获批后，你将完成用例的录入并为你的 Agent 生成一个唯一标识 ID。有了这个 ID 之后，你就可以进入内部的开发者门户（dev portal），录入全部相关规范细节：说明这是我的 Agent 用例及对应 ID；选择打算采用的技术底座，比如是 LangGraph 还是 LangChain 等；选定编程语言，是 Python 还是 TypeScript；同时挑选中意的技能模块或提示词，并将这些信息一并提交。

<details>
<summary>Original English</summary>

**Speaker**: Now, let's talk about the end-to-end workflow, how it looks like. So first thing first, it starts with your architecture review. Once your architecture gets approved, you register your use case and generate an ID for your agent, right? Once you have that, then you can have a dev portal, internal portal, where you can ingest all the details saying that, "Hey, look, this is my agent use case, this is my agent ID. This is the framework I'm going to use, either LangGraph, LangChain, or so. These are the languages I'm going to use, either Python or TypeScript." And then you can choose your skills or prompts, and then you submit your information right to this.

</details>

**讲者**：一旦在开发者门户提交，系统就会自动为你初始化并生成一个代码仓库。这个脚手架仓库不仅包含了 Agent 核心框架（例如 LangGraph 基础工程），同时还把记忆持久化框架、追踪评估框架、上下文优化框架以及 PII 数据脱敏拦截框架全部打包集成在内。之所以这样设计，是因为一线业务开发者往往没有精力去逐个搭建并兼顾所有这些底层保障体系，他们日常可能直接依赖市面上的辅助编码工具，或者习惯性地只抓一两个核心点。我们通过模板化统一下发，可以确保整套基础设施在全公司范围内保持一致规范，并汇聚集中在一处进行统一的可视化监控与评估。

<details>
<summary>Original English</summary>

**Speaker**: Once you submit this, the dev portal is going to create a repository which is going to contain not just the agent framework like your LangGraph agent framework, but it is also going to contain your memory framework, your tracking eval framework, right? And then your context optimizer framework and your PII blocking framework as well. The reason for that is because not necessarily all your developers are taking care of all these frameworks, right? They just sometimes create the framework what generally AI assistant tools generally support, or they stick to one or two frameworks. So we just want to make sure that when you roll out such a framework, make sure they are consistent across the company, and they can be centralized in one place so you can visualize those results as well.

</details>

### 本地验证与 CI/CD 自动化流水线

**讲者**：当仓库生成后，开发者就可以把代码拉取到本地，将智能体打包为 Docker 镜像及容器进行本地运行，直接输入测试查询验证输入输出。此时你还可以在本地测试与记忆系统的交互——例如连接 Cloud Spanner Evaluator，并将追踪与评估指标写入本地数据库（如 SQLite 或 BigQuery），彻底验证智能体在本地环境的功能完备性。本地调试完全通过后，开发者即可创建 Pull Request。在获得两次 PR 代码审查批准之后，变更就会正式进入 CI/CD 流水线。

<details>
<summary>Original English</summary>

**Speaker**: Right, so once you have that repository, developers basically clone that repository. They can build their agent as a Docker image and containers and test their agent input and output through the query. They can also test this on their local memory, maybe Cloud Spanner evaluator here, and you can also store this tracking eval in some of your DB, maybe SQLite or maybe BigQuery, to make sure that agents are fully working on your local, right? So once your agents are running in local, then you're ready to go ahead and generate a PR, and once you get your two PR approvals, then it goes to the CI/CD pipeline, right?

</details>

**讲者**：进入自动化流程后，流水线首先会将该 Agent 注册到集中式的 Agent 注册中心系统，并为其分配对应的 Langfuse 等追踪监控 URL，以便全链路审查执行 Traces。随后，CI/CD 流水线会接管此前在本地构建的 Docker 容器，在生产构建环境中生成正式镜像，并执行安全漏洞扫描。待一切扫描与安全审核确认无误后，正式镜像会被推入生产镜像仓库。紧接着，内部部署编排平台会将该 Agent 正式发布到 Kubernetes 集群中指定的 Namespace 下。

<details>
<summary>Original English</summary>

**Speaker**: So the PR is basically going to, firstly, it's going to register your agent into some centralized agent registry system which provides a Langfuse URL to it to make sure that you see all the traces. And then the CI/CD pipeline is basically, whatever the local Docker container you built here, it's going to build that container into the production system. It will scan that image, make sure that there's no vulnerability. If everything looks great, security approved, you can move that image back into the registry. Further, you have your own deployment platform or orchestrator platform which is going to deploy that agent into the Kubernetes cluster in a given namespace, right?

</details>

### 云端资源编排与服务间通信

**讲者**：这套体系极为出色的一点在于，开发者门户在初始化时不仅创建了 Git 仓库，还同步为你预先配置并创建了一整套生产云资源：包括 Workload Identity、记忆数据库、追踪与评测表，以及专属的 Agent 密钥管理（Secret Management）。所有这些资源都会依据你最初填写的命名规范自动预配到位。因此，当内部编排平台部署 Agent 时，容器早已知晓自身绑定的工作负载身份，即 K8s Service Account（KSA）与 Google Service Account（GSA）之间的身份绑定早已就绪。Agent 一上线便拥有相应权限与这些持久化基础设施无缝通信。在此基础上，Agent 会进一步与其它终端服务建立连接，如 AI 网关、MCP 服务器、负责链路追踪的 Langfuse 以及其它内部 API 接口。

<details>
<summary>Original English</summary>

**Speaker**: The good part here is that this dev portal is not just creating the repository, it also creates a bunch of other production resources, for example, the Workload Identity, right? And then memory DB or tracking and eval tables, and then agent secret management, right? So based on whatever the name we provide, it not just, again, creates a repository, it creates all those different resources as well. So what happens is when this internal orchestrator deploys the agents, the agent already knows what Workload Identity it is supposed to work with, right? That binding should already happen. Once this KSA to GSA binding happens, the agent will start communicating to all these resources. Once everything is in place, the agent is further going to communicate to the rest of your endpoint services, like for example AI gateway, or MCP servers, or Langfuse for tracing, or some other API endpoints. Right.

</details>

### 自定义安全 MCP 服务器实现

**讲者**：在阐述完总体架构之后，我们接着逐一深入各个独立组件。首先来谈谈 MCP 服务器。市面上固然有很多开箱即用的现成 MCP 实现，但如果你是在严格内网隔离（air-gapped）的企业环境下工作，强烈建议你自己亲手构建内部专用的 MCP 服务器。关于 MCP 的基础概念大家都很熟悉，这里就不再赘述。

<details>
<summary>Original English</summary>

**Speaker**: So now, firstly, we talk about the MCP server as well. So we talk about architecture. Now we're going into the different components. So MCP server is something that you can definitely use something which is outside available. But if you're working on an air-gapped environment, it's highly recommended that you build your own MCP servers. So, yeah, and you can use... I would not go with the definition, everyone knows about it.

</details>

**讲者**：在具体工程实现上，我们推荐采用 FastMCP 相关的封装包来快速搭建 MCP 服务。你可以把不同的业务工具注入到 FastMCP 包装层中，组装出完整的业务服务。必须严格遵循的一项原则是：在 MCP 服务器中定义的每一个 Tool，上线生产前都必须经过内部安全团队的全量合规审查，确保只有经过正式授权的安全工具才能进入生产环境。正因如此，你才能在这一层强行实施字段过滤、频率限制以及拦截不必要的字段，避免不合规的数据泄露给大模型，防止模型访问到本无权读取的信息。最后，在设计 MCP 服务器时，必须保证当流量从 MCP Client 经由 MCP 网关流向 MCP 服务器时，无论是终端用户发起的请求还是服务账号发起的请求，都必须首先在网关侧完成严格的身份鉴权，方可调用工具获取正确数据。

<details>
<summary>Original English</summary>

**Speaker**: So the way the framework has been built here is that you can leverage the FastMCP server package or wrapper to build that MCP server, and you can create a different set of tools inside that FastMCP wrapper to construct your overall servers. And then you make sure that every tool, when you define an MCP server, has to be fully reviewed by your own internal security team to make sure that only authorized tools can go into production. And that's how you can enforce some filters, limits, and block the fields which are really not required to go to LLM and get to the information which you're not supposed to get, right? And third part is, of course, you need to make sure that you build your MCP server in a way that whenever the traffic is coming from your MCP client to MCP gateway to MCP servers, either it's coming from a user or service account, there has to be authentication to the MCP gateway first, so that they can access your MCP tool to get that right information.

</details>

### MCP 网关鉴权与双层令牌流转机制

**讲者**：接下来我们详细剖析 MCP 网关的核心机制。如果在内网隔离环境部署，同样建议自研构建专属的内部 MCP 网关。具体交互逻辑是这样的：当开发者在本地代码辅助工具中操作，或者智能体自身接收到用户的首个提问时，客户端会立即向 MCP 网关发起一次性鉴权请求。网关接收到请求后，会首先将当前用户的会话状态（Session State）持久化到 Redis 缓存中，随后向客户端签发并返回一个 JWE（JSON Web Encryption，加密型 JWT）访问令牌。

<details>
<summary>Original English</summary>

**Speaker**: All right. Now the gateway part, how the gateway works. So this is, again, you can build your own internal MCP gateway if you are again working in your air-gapped environment. So the way it works is you are working on local code assistance tools, or maybe your agent, right? So the moment you submit your first query to your agent, it will send that one-time authentication request to the MCP gateway, right? MCP gateway recognizes and takes your request; first, it will save your session state into Redis, and then it will return back the JWE access token back to your client, right?

</details>

**讲者**：客户端拿到了这个 JWE 令牌后，就已经知晓下一步要寻址的具体 MCP 服务器。于是它会发起实际的工具调用（Tool Call）请求，请求路径通常采用特定的命名空间结构，比如指向 `/artifactory/mcp` 或是 `/github/mcp`，并在请求头中携带该 Bearer JWE 加密令牌。MCP 网关拦截到请求后，会根据命名空间前缀解析出对应应路由的目标 MCP 服务器，同时解密拆包（unwrap）该 JWE 令牌，提取出原始的用户身份凭证附着到内部请求上下文中，最终将请求安全转发给后端的下游 MCP 服务器。下游 MCP 服务器一旦接收到带鉴权上下文的请求，便可安全代表该用户向目标系统发起真正的底层 API 调用。

<details>
<summary>Original English</summary>

**Speaker**: Once the client receives that JWE token, it will know what MCP server it needs to call, right? So it will submit that tool/call request on a given namespace/mcp—meaning, let's say, Artifactory or github/mcp—with the Bearer JWE token into that. So once MCP gateway receives that, it will understand what namespace, meaning MCP server, it needs to look up for, and then it will unwrap that JWE token, and then it will attach that user token in that request and send it to the respective MCP servers. Now once MCP server receives it, it will make that respective API calls to that endpoint.

</details>

<!-- chunk 22/51 -->

### MCP 网关的集中认证与路由

**讲师**: 服务接收到请求后，会拿该身份令牌（ID token）去换取对应的权限凭证，并根据该用户被授权查看的具体权限范围（scope）返回响应。明白吗？一旦用户获取了令牌，MCP 服务器基本上就会将所有数据解包，构建出兼容 MCP 网关接收格式的有效载荷（payload）；最终，这个最终载荷会被回传给客户端，以便查看相应的数据点。这表明，我们之所以构建这个 MCP 网关，是为了确保拥有一个集中的认证与路由中心，通过该 MCP 网关和 MCP 服务器，将任何代码辅助工具或智能体安全地连接到具体端点。任何端点都不应该开放直接访问，必须先通过 MCP 网关完成合规的身份认证，然后才能触达 MCP 服务器和后端端点。

<details>
<summary>Original English</summary>

**Speaker**: ...of that to the service, and then it will exchange that ID token and return the response based on whatever scope that user is authorized to see. Right? So once the user received the token, MCP server basically unwrap all the data, make the payload which is compatible for MCP gateway to receive, and then finally the final payload will send back to the client to see the data points. So what it shows is that we build this MCP gateway to make sure that we have a centralized authentication and routing hub that securely connect any coding assistant tool or agents to the endpoint via this MCP gateway and MCP server. There should not be direct access provided on any endpoints. There has to go through the MCP gateway through proper authentications before they reaching to the MCP server and the endpoints. Right.

</details>

### 网关监控与可观测性体系（日志、链路与指标）

**讲师**: 现在我们来看网关监控（gateway monitoring）这部分。我们前面讨论了整体架构，讨论了 MCP 服务器和 MCP 网关，现在轮到监控了。再次强调，如果没有持续的监控、评估和反馈机制，AI 智能体是无法被信任的。这正是我们构建 MCP 网关监控的原因。监控通常的工作流程是：当你向智能体发起调用请求的那一刻起，所有的操作日志都会被发送到日志存储系统中。你可以选用 ELK、Loki 或者 CloudWatch 等等。这些日志通常包含如下信息：比如“帮我展示过去 10 分钟调用里出现的所有 401 未授权错误”，或者“令牌刷新失败时系统执行了什么操作”。这类请求记录都会进入日志存储。

<details>
<summary>Original English</summary>

**Speaker**: So now the part is the gateway monitoring. Right. Again we talk about architecture, we talk about MCP server, MCP gateway. Now it's a monitoring. Again, the AI agent cannot be trusted without continuous monitoring, evaluation, and feedback. Right? This is why we are building the MCP gateway monitoring. So the way the monitoring work is usually like the moment you submit any calls to your agent, it will send all the operation log into the log store. You can use ELK, Loki, or CloudWatch or so, right, and generally this contains the information like, show me like all last 401s in my last 10 minutes call, right, and what did it do when the token refresh failed, right. So those kind of request can goes to the log store.

</details>

**讲师**: 此外，还有一些追踪（traces）和指标（metrics）数据，也就是实时运行时数据，它们会发送到 OpenTelemetry。OpenTelemetry 是一套开源解决方案，用于收集所有的分布式链路追踪和指标，处理这些数据后重定向传输给后端系统。在这种架构下，链路追踪数据会流入 Tempo。Tempo 同样是一个开源解决方案，用来存储所有的调用链路。这里说的链路追踪信息，指的是类似于：“在这次请求中，哪个工具的执行耗时最长、响应最慢？”、“这次调用究竟是来自智能体还是来自开发者的 IDE？”、“执行失败的代码抛出的具体错误是什么？”等等。这些维度的数据都会存储在 Tempo 之中。

<details>
<summary>Original English</summary>

**Speaker**: Now there are some, you know, traces and metrics data, like real-time data, they goes to the OpenTelemetry as well. OpenTelemetry again is open source solutions which going to collect all your traces and metrics, and is going to process the data and redirect to the backend system. Right? And in this case, the traces will go to Tempo. This is again an open source solutions which going to store all your traces in terms of like traces in the sense like information around like which tool was slow on this request, whether this call is coming from agent or IDE, what was the exact error on this failed code or so, right. So these kind of data are going to store into the Tempo. Oh my bad. Okay.

</details>

**讲师**: 接下来是指标数据。在 Prometheus 这一层，主要采集的信息包括：针对某一个特定工具，它的 P95 延迟表现如何；特定时间段内，系统中的某些拒绝调用（例如操作拦截）是否存在尖峰突增。诸如此类的度量指标都会存储在 Prometheus 中。一旦收集齐了链路追踪和度量指标这所有数据点，这套完整的聚合数据最终都会对接到 Grafana 中，供你进行统一的可视化监控展示。

<details>
<summary>Original English</summary>

**Speaker**: And then the metrics is about... Prometheus is all about the information about like what are P95 latencies for a given tool, right, whether my rejection is spiking on a particular time or not, right. So those kind of metrics is going to store in Prometheus. So once you get all this data point, like traces and metrics, this entire aggregate data back actually save into the Grafana for your visualizations. Right.

</details>

### 智能体工作流编排：LangGraph 与状态转移

**讲师**: 好了，MCP 服务器、MCP 网关以及监控体系都讲清楚了。接下来我们要讨论智能体框架（agent framework）。在绝大多数业务场景中，我们选用的是 LangGraph。LangGraph 是由 LangChain 社区提供的一套框架，它提供了基于图（graph-based）的架构，能够为复杂的多智能体 AI 工作流提供循环（loops）、分支路由（branching）以及状态管理（state management）能力。

<details>
<summary>Original English</summary>

**Speaker**: All right. So the MCP server, gateway, and monitoring is covered. Now we're going to talk about the framework. So the agent framework, right. So we use LangGraph for most of the cases. And basically LangGraph, again, is provided by LangChain community, is provide a graph-based architecture that support loops, branching, state management for complex multi-agent AI workflows. Right.

</details>

**讲师**: 它的运行机制是这样的：当你提交第一条查询时，系统首先会对你的问题进行语义理解与意图解析，判定它属于哪一类问题、期望获得怎样的回答；基于解析出的意图，系统会生成一份执行计划（plan）。接着，请求会被送往分类（classify）环节，在此判断该操作的性质：它仅仅是一个只读操作？还是涉及修改级别的数据变更？或者你确实想要执行删除等敏感高危操作？根据这些分类判定，系统会动态调整整体执行结构，并据此制定出后续的执行规划。

<details>
<summary>Original English</summary>

**Speaker**: And the way it work is like the moment you submit your first query, we do interpret your question first, like what type of questions it is and what response is looking for, and based on that it's create a plan, right. Then it will send for classify area where it will determine that, hey, whether it is just like a read operations, or whether it is just like a modification level changes coming up, or whether you really want to delete something, right, or some sensitive operations. Based on that, it adjusts the overall structure and then plan accordingly.

</details>

**讲师**: 紧接着的下一步，这个计划本身实际上就是一个子图（subgraph），用来执行具体的业务度量与操作步骤。也就是说，在计划子图中，一旦明确了要执行的具体操作，它就会进入类似“提取证据”（fetch evidence）的环节。在经过全面的解析与分类之后，这里会实际针对你提出的问题发起调用，向 MCP 网关发送请求；在确保通过安全认证之后，网关会调用具体的 MCP 服务器并调度对应的工具来抓取数据，进而生成上下文证据。

<details>
<summary>Original English</summary>

**Speaker**: The next step is plan is actually itself is a subgraph where you do the measure of your operations. Meaning that in the plan, once you know what operation you're performing, it goes to the, let's say, in a fetch evidence section where it actually call that whatever the question you ask here. After all interpret and classify, it actually go ahead and make the call to the MCP gateway, make sure they get authenticated, and then it make the call to the MCP server using the right tool, and get that data and then generate that evidence. Right.

</details>

### 安全策略校验与人机协同审批（HITL）

**讲师**: 当所有发现和证据完成验证后，系统接下来会进行策略规则检查。它会校验该请求是否属于只读操作。如果是只读操作，系统就会直接放行执行，并将全部执行记录与数据点持久化保存到我们的审计日志（audit logs）中。但是，如果判定这是一个写操作或敏感危险操作，它就必须走人机协同（Human-in-the-Loop, HITL）流程，挂起并等待人工审批。如果审批通过，便继续推进执行；如果被人工驳回，无论通过还是驳回，处理结果都同样会完整记入审计日志。因此，若将 MCP 网关、MCP 服务器以及智能体框架整合在一起，这就是整体运行的全貌。无论你构建何种智能体、提交何种调用，请求都会先抵达 MCP 网关进行统一认证，再路由至对应的 MCP 服务器，在指定工具上执行查询，进而调用端点 API 并获取响应。从基础设施架构视角来看，其链路清晰体现为：智能体与 MCP 网关通信，网关对接 MCP 服务器，最后由服务器连接实际终端系统。

<details>
<summary>Original English</summary>

**Speaker**: Once you validate all your finding, then it will check the policies. It will check whether it is a read-only, then go ahead and execute, and I will save all the record points into our audit logs. But if it is a write and sensitive operations, definitely it will go through the HITL process where you wait for an approval. If it is approved, you go ahead and execute. If it is get rejected, in either case is going to save into the audit log, right. So if we combine all this together, like MCP gateway, MCP server, and the agent, right, this is how things looks like. So ultimately, whatever the agent you are building, whatever the call you are submitting, it will goes to the MCP gateway for authentications, and then it will redirect to the right MCP servers to execute your query on a given tool, so that it make the API call to that endpoint and get the response, right. All right, if you think from the infrastructure perspective, this is how it looks like. So agent is communicating to the MCP gateway, goes to the MCP server, and to the endpoint.

</details>

### 智能体记忆管理机制与本地/生产持久化

**讲师**: 好了，我们前面深入剖析了 MCP 网关、MCP 服务器、监控体系以及智能体框架。现在我们来讨论构建端到端生态系统时必须妥善处理的另外三到四个补充框架。其中非常核心的一项就是智能体的记忆管理（agent memory management）。记忆管理本质上是一个跨时间持久化保存与恢复工作流状态的过程，它能确保系统具备持久性（durability），并在每一次查询执行之间提供无缝的状态恢复能力。

<details>
<summary>Original English</summary>

**Speaker**: All right. So we talked a lot about MCP gateway, MCP servers, the monitoring, and the agent framework. Now we talk about three and four additional framework that we should have to take care of when building the end-to-end ecosystem. Right? One is them is agent memory management. Again, it's basically a process where you can save and restore the state of your workflow over the time, right, ensuring that it's provide you a durability and seamless recovery across your every query run.

</details>

**讲师**: 它的运作机制如下：每当你向智能体提交一个查询时，系统都会生成一个线程（thread）；在给定的线程上，或者说当你提出第一个问题时，系统会为这次执行创建一个专属的运行标识（run ID）。随着交互深入，当你提出更深层次的问题时，执行流程会流转到 LangGraph 图中的某个特定节点去执行该查询，并在该节点上将对应的检查点（checkpoint）就地保存下来。此后，如果你在同一个会话线程中提出追问，系统便会创建另一个 run ID，并依据你的追问意图再次路由到特定节点，并将最新的状态检查点存储在那里。

<details>
<summary>Original English</summary>

**Speaker**: So the way it work is like whenever you submit any query to your agent, it actually generate a thread, right, on that given thread or when you ask your first question, it will going to create a run ID for that. So the moment you ask some deeper questions, it will go on a particular node in that LangGraph and execute that query, and on that node it going to save that respective checkpoint here. Right? Now if you ask a follow-up questions on the same thread, it going to create another run ID, and again depend on your follow-up question, it go to a specific node and save the checkpoint over there, right.

</details>

**讲师**: 对于这些持久化状态数据，在本地开发测试阶段，你可以直接采用轻量的 SQLite 数据库；而在云端生产环境中，例如部署在 GCP 上时，你可以采用 Cloud Spanner，在 Azure 和 AWS 环境下也可以选用各自对应的托管分布式数据库。

<details>
<summary>Original English</summary>

**Speaker**: And all this data, for your local development you can use the SQLite DB, but in production, in let's say in GCP, you can use Cloud Spanner, and respective databases you can use in Azure and AWS as well, right.

</details>

### 记忆持久化实机演示与调用轨迹回溯

**讲师**: 接下来，我带大家在本地环境快速演示一下这套记忆管理。举个例子，我在本地环境构建了这个智能体，然后尝试在 SQLite 数据库上执行查询，看看里面当前是否存在数据。一开始数据库是空的，没有任何历史记录。现在我正式提交一条查询请求。你会看到数据库里立即新增了一条记录，显示出：“这是我的线程 ID（thread ID）”、“这是刚刚被提问的具体问题”，以及该查询被执行的精确时间戳。

<details>
<summary>Original English</summary>

**Speaker**: So just walk you through the quick demo here on the memory. So for example, I have just built this agent locally, and then trying to run this query on SQLite DB to see if there is data or not. Initially I don't have any data. Now I submit my query. You will see that I received the one record which is saying that, hey, this is my thread ID, this is the question I have been asked, and exact time when this query was executed.

</details>

**讲师**: 接着，如果我执行下一条查询，想查看在给定的会话线程上累计产生了多少条消息交互，只要继续运行后续的数据库查询指令，就能直接检索到这些统计信息。如果我们想要查看关于当前查询更底层的元数据详情，再次运行查询后，就能看到极为详尽的描述信息，包括：触发了哪些工具调用、当前的线程 ID 是什么、对应的运行 ID（run ID）是什么等全部上下文参数。不仅如此，如果你想查验刚刚在运行该查询时究竟执行了哪个具体工具，也可以在数据库中清晰地看到对应 MCP 服务器上调用的具体工具名称。更进一步，如果你想观察在 LangGraph 框架内部整个执行流程是如何一步步推进演变的，通过对记忆数据库执行此类查询，同样可以完整回溯在查询执行期间所依次流转调用的各个不同节点。好的，接下来我们来看追踪与评估（tracking and eval）部分。

<details>
<summary>Original English</summary>

**Speaker**: Now if I run the next query to see that, hey, how many messages I've been produced on a given thread, you can get this information by running the further queries. Right? Now if I would like to run to see that all the metadata level information on my query, I can run my query again, and you can see the detailed description around how many tool I get invoked, what is my thread ID, what is my run ID, and all those informations. Now if I want to also see that, hey, what tool have been executed when I run this query, you can go ahead and see the exact tool name as well on that given MCP servers. Now further I also want to see that how the progression was happened on my LangGraph framework, that also you can see by running this type of query on your memory DB. You can see that here like different kind of nodes been called when actually that query has been run. All right. Now the tracking and eval. So just...

</details>

<!-- chunk 23/51 -->

### Agent 级别追踪与评估体系

**Speaker**: 为了确保大家不产生混淆，正如我们之前讨论过的，MCP 网关监控属于网关层面的监控，而这里介绍的是 Agent 级别的追踪。我们之所以做这项工作，是因为我们确实需要追踪：你向 Agent 提交了什么查询、返回的响应是什么、使用了哪个 LLM 模型、你的 Token 成本是多少、消耗了多少 Token，以及你的评估标准是什么样的、响应质量究竟高不高。因此，你必须从第一天起就存储这些数据。试想一下，如果你拥有上千个 Agent，每个 Agent 都会有自己的追踪与评估项目及相应的数据表。假如你有 100 个 Agent，就会有 100 个不同的项目，每个项目都有各自对应的追踪与评估表。这样一来，如果在 6 个月后有人问你：“你的 Agent 表现如何？响应内容是什么？质量怎么样？消耗了多少 Token？”你就可以将所有这些数据聚合起来，围绕它们构建管理层看板，从而评估构建这么多 Agent 的投资回报率（ROI）。

<details>
<summary>Original English</summary>

**Speaker**: To make sure that there's no confusion here, like we talked about earlier, the MCP gateway monitoring. This is the agent level tracking. So we do this because we really want to track that what query you have been submitting to the agent and what the response is coming, what LLM model you have been used, what's the cost of your token, how many token you have been burned, and what's your evaluation criteria looks like, what is the quality of your response or not, right? So you need to store that data from the day one. And imagine that if you have a thousand plus agent, every agents will have their own agent tracking and eval project and the tables, right? So if you combine let's say if you have 100 agents, you will have 100 different projects, and each project has their own respective tracking and eval tables. Now tomorrow, 6 months down the line, if somebody asked you that how your agent has been performed, what was the response, what was the quality, how much token you've been burnt, you can aggregate all this data and you can create executive dashboards around it to see what is ROI in building so many agents, right?

</details>

### 追踪与评估演示及核心数据表结构

**Speaker**: 接下来让我带大家看一下追踪与评估（Tracking and Eval）的演示。大家可以看到，这里列出了六张表。第一张是任务追踪表（job tracking table），它包含了绝大部分基础信息，比如你的具体查询是什么、返回的响应是什么等等。此外还有一系列其他数据表，比如质量相关表、工具调用表以及节点层级的执行记录表等。在这个演示中，我将向我的 Agent 提交第一个查询。你会看到，一开始界面上并没有数据，因为处理需要一点时间。当我再次刷新时，就能看到针对该查询所记录的请求 ID（request ID）、会话 ID（session ID）、Agent 名称、所提的问题、该问题的输出结果、任务是否已完成、执行所耗费的时间、所使用的模型，以及部分元数据层面的信息。

<details>
<summary>Original English</summary>

**Speaker**: So, let me walk you through the tracking in Eval demo here. So, here if I look at this one. First, if you see that there are six tables are listed here. One is a job tracking table and which is contains most of this information around what is your query, what's the response and everything. And there are a bunch of other tables as well like your quality related and your tool invocations and then node level executions and all that. So in this case I'm going to submit my first query on my agent, and you will see that there will not be any data in the first place because it takes some time. So I will refresh this again, and this time I will see that when I refresh I do see that for a given query I get my request ID, my session ID, my agent name, what question I've been asked, and what was the output of that question, whether it has completed or not, and then what is the time it took, what is the model I have been used, and then some of the metadata level informations, right?

</details>

**Speaker**: 进一步来看，在质量方面，每次运行会有 8 项质量检查。你可以看到，成功率、延迟、成本、工具准确率、安全性等指标各占一行记录，所有这些都被妥善存储在这里。接下来是评估得分（eval scores），这同样是一行记录，相当于针对某次单次运行的综合积分卡，其分值基本上在 0 到 1 之间波动，在一行数据中涵盖了所有质量维度的评分。随后是质量指标（quality metrics），这是对单次运行更深层次的下钻分析，实质上是在一个宽行中使用嵌套字段完整记录了响应质量、安全性、延迟、成本以及工具统计数据。还有工具调用表（tool invocation），它记录了每一次具体的工具调用：运行了哪个 MCP 工具、耗时多久以及执行是否成功。最后是 Agent 轨迹表（agent trajectory），它按时间顺序一步一步还原了整个运行过程的故事，包括每一次 LLM 调用以及图状态（graph state）的演变，例如规划、总结等步骤。

<details>
<summary>Original English</summary>

**Speaker**: Further if I look for the quality, again there is a eight quality checks per run, right? And you can see that this one row each for you know like success, like latency, cost, tool accuracy, safety etc., like all this has been stored here, right? Now the eval scores, this is again going to be a one row, this is going to be a scoreboard for your given run which is basically varies between 0 to one which is scores all the quality dimension in a single row. Right? Now the quality metrics. So again it's a deep dive on that particular one run. Basically a nested field for the response quality, safety, latency, cost, and the tool stat in one wide row. Right? Now the tool invocation. So every tool call, which MCP tool ran, how long it took, and whether it succeeded or not. Right? And now the agent trajectory which is talk about step-by-step story of the run, each LLM call and the graph state in order like plan, summarize etc.

</details>

### 敏感信息拦截框架（PII & Secret Redaction）

**Speaker**: 接下来介绍的是 Agent 敏感信息拦截框架。这一点至关重要，因为在日常使用 Agent 或类似系统的过程中，很多时候你的查询中可能会混入一些敏感凭据或机密信息。比如，你上传的某个文档可能包含高度敏感的内容，或者在手动打字时无意中输入了 API Key 等。为此，我们建立了一套框架，用于定义不同的数据类型及其严重程度等级。如果检测到的敏感度评分高于 90% 左右，系统会立即拦截并脱敏这部分机密内容，确保这些敏感凭据绝不会流入 LLM 模型，既不会被存入内存数据库（Memory DB），也不会进入追踪与评估表或分布式链路追踪系统。这里的核心目标就是在敏感数据被录入的瞬间、在你键入文字的那一刻，就地完成阻断。

<details>
<summary>Original English</summary>

**Speaker**: All right so now the next is the agent PI tremor. This is very very important because many times happens that when you working in agents or this thing, sometime there's a possibility that there are some secret being ingested as a part of your query, right? Let's say you are uploading some doc which is has some sensitive informations, and sometime while typing you may have some API keys or so. We have a framework which define that different sort of data types and their severity level. If your severity is above 90% or so, we will block and redact that secrets immediately so that make sure that that secret is never goes to LLM models, right? Neither it will goes to your memory DB, nor it will go to tracking and eval tables or tracing systems as well. So the goal here is to just block this sensitive data as it is the moment it get ingested, right, moment you type.

</details>

### 上下文优化器（Context Optimizer）与 Token 压缩实测

**Speaker**: 最后一个核心框架是上下文优化器（context optimizer）。这是我个人最喜欢的领域之一。当大家提交查询时这一点非常关键：有时你一次性提交了太多查询，或者上传了海量的数据点与文件系统内容，此时必须保证每次查询都能尽可能节省 Token。因此，我们构建了上下文优化器框架，在将数据发送给 LLM 之前，先对查询进行塑形和剪枝处理。在剪枝系统中，我们首先根据设定的 Token 上限筛选有效载荷（payload）；接着进行重排序（rerank），明确当你提交如此庞大的上下文时，我们最应该聚焦哪些最相关的信息；随后进行去重（dedup），剔除所有冗余重复项，为 LLM 生成一份高度精简、极具针对性的核心数据集；最后在发送给 LLM 之前对大体量载荷完成最终压缩。

<details>
<summary>Original English</summary>

**Speaker**: All right. The last framework is all about now is the context optimizer. This is one of my favorite area where whenever you submit, it's very important, right, whenever you submit too many queries sometime you upload lot of the data points and you upload bunch of files systems or so, right? It's very important that time is you make sure that you save your token in every query. So we built in context optimizer framework where you actually shape your query and then you prune it before you go to LLM in the pruning system. We do select the payload based on that token limit. Then we rerank that hey which is the most relevant information that we should target for when you submit this huge giant context, and then we dedup that, remove all the duplicates and create a very unique set of very curated data like the main data for the LLM, and then we finally compress this large payload before it goes to the LLM.

</details>

**Speaker**: 让我们来看一下具体演示，过程非常快。举个例子，我提交第一条查询：“帮我找出 JFrog Artifactory 中的所有构件（artifacts）。”大家可以看到，在我尚未提交查询时，这里并没有任何数据。一旦我提交了该查询并刷新页面，就能看到一条新记录已经生成。可以看到，针对这道特定问题，一共消耗了 24,000 个 Token。我稍微往回退一点向大家展示细节，确实显示消耗了 24,000 个 Token。现在，我在后台开启了上下文优化器，并重新运行完全相同的一条查询。这一次大家会发现，刷新该次运行记录后，对于同一条查询，它仅仅使用了 2,400 个 Token，节约了将近 90% 的消耗。

<details>
<summary>Original English</summary>

**Speaker**: So let's see this demo here. This will be quick. So for example, let's say I will submit my first query: "Hey, find me all the artifacts in my JFrog artifactory." You see that first when even I not submitted any query yet, there is no data here. So the moment I submit this first query and if I refresh my query here, and then you can see that the record has been added. So you can see there is a 24,000 token has been used. I will go back a little bit just to show the thing. So you can see this 24,000 token has been used for given questions. Now I enable the context optimizer behind the scene and I'm rerun the exact same query again. So this time you will see that for the same query if I refresh this run and you will see that this time it used just 2,400 token, right, for exact same query. So which is almost like 90% saving.

</details>

**Speaker**: 我也可以在 Slackbot 上重新演示一遍：我向 Slackbot 提问：“帮我列出 Artifactory 所有仓库中的全部 Docker 镜像。”在运行之前这里同样没有数据；随后我提交了查询。一旦查询执行完毕，我们再次查看记录，会发现新记录已创建，该特定查询同样消耗了约 24,000 个 Token。紧接着，我在后台开启优化器，并在 Slackbot 中重新运行该查询；再次查看时显示它实际只使用了约 1,500 个 Token，节约幅度同样达到了近 90%。在大多数实际业务场景中，我们普遍能实现 70% 到 78% 的 Token 节省。试想一下，如果你拥有成千上万个 Agent，每天都在执行海量查询，借助这套框架能够节省下多么惊人的 Token 规模。

<details>
<summary>Original English</summary>

**Speaker**: I can rerun the same demo on the slackbot as well where I'm asking slackbot: "Hey tell me all my docker images across all the repositories in artifactory." When I run this query there is no data. Now I'm going to submit my query. So once this query will run, and if I run my query again here and you will see the record get created, it's again used like 24,000 for this particular query. Now what I will do is I will turn on my optimizer behind the scene and I rerun the same query in the slackbot, and then if I run this query again, it will show like it exactly used 1,500 almost token which is again like 90% savings. In most of the cases we get like 70 to 78% token saves. So imagine that you have thousands of if you have thousands of like agents which is running like you know many queries per day, imagine how much token you can save with this framework.

</details>

### 企业级 Agent 架构建设的核心启示

**Speaker**: 对我们而言，这里的核心启示在于：必须确保构建的是一套完整的企业级架构体系，而绝非仅仅搭建孤立的单个 Agent。你要确保整套框架支撑在底层，切忌急于求成、匆忙拼凑并上线交付某个 Agent，必须确保所有流程完整穿透整套基础设施，以免在后期阶段才懊悔当初为何没有把框架基础设施落实到位。第二点在于，必须建立健全的网关系统。务必确保每一次工具调用请求——无论是来自本地开发环境还是通过 Agent 发起——都必须经过统一的集中式 MCP 网关。在请求触达 MCP Server 之前必须经过身份认证，由 MCP Server 严格管控执行特定查询时所调用的具体工具，同时落实全面的监控机制以及针对工具执行过程的完整审计。当然，对于每一个具体动作和所有高风险事项，务必坚持引入人机协同（Human-in-the-loop）流程，确保可观测性与审计机制时刻就位。最后同样重要的一点是，始终要将上下文优化器常态化保持在……

<details>
<summary>Original English</summary>

**Speaker**: All right. So now the key takeaway here is for us is like make sure that we build an enterprise framework, not just an agent, right? Which make sure that you have all the framework under it, don't try to be in rush to building some agent quickly and deploy ship it, make sure that it has to go through all the framework all together so that you should not realize a later stage that you know I should have this framework in place right in the very first place. Second is make sure that you have a proper gateway system. Make sure that every tool call request either you are doing this from your local or through agent, it has to go through some sort of centralized MCP gateway. Make sure it authenticated before it reaching to the MCP servers, and then make sure that your MCP servers take a control on what tool you should use to execute a particular query, right? And make sure that you have monitoring in place and complete auditing in place for that tool executions. And of course you should keep the always human in the loop process for every action items, every high-risk items, make sure that there is a observability and auditing has to be in place. And last but not least make sure that context optimizer should always be...

</details>

<!-- chunk 24/51 -->

### 结语与新主题引入：AI Agent 的信任难题

**Speaker A**：……在那个环节上证明你在智能体上的成本投入是合理的，对吧？另外我也想顺便分享一下，我最近在亚马逊上发布了关于 MCP（模型上下文协议）的新书，大家可以去免费下载 Kindle 电子版，实体纸质书也已经同步上架发售了。好的，非常感谢大家观看本期视频！如果你们有任何问题，欢迎随时通过 LinkedIn 或 Twitter 与我取得联系，我非常乐意为大家答疑解惑。

<details>
<summary>Original English</summary>

**Speaker A**: ...there to justify your cost on your agents, right? So just want to share is that I released my MCP book recently on Amazon, so feel free to download. It's free on Kindle, and its hard copy is also available. All right, thank you so much for watching this video. And if you do have any questions, feel free to reach out to me over LinkedIn or Twitter. I'm happy to answer.

</details>

**Michelle Brandt**：系统正式上线，仅仅能证明这套系统在物理上存在，但它根本无法证明业务一线的人员后续会真正去使用它，更无法保证它能从最初交易模型预期的商业回报中兑现哪怕一分钱。我是 Michelle Brandt，《Leading at Scale》的创作者。当下每一家企业都在直面的核心痛点正是：智能体确实能跑通，但究竟有人敢信任它吗？

<details>
<summary>Original English</summary>

**Michelle Brandt**: Go live proves that a system exists, but it doesn't prove the people behind the work will actually use it or that it will ever deliver a single dollar from the deal model. I am Michelle Brandt, creator of Leading at Scale. And the question every enterprise is confronting right now is: the agent works, does anyone trust it?

</details>

**Michelle Brandt**：我在企业数字化转型领域深耕了二十余年，并在媒体、高科技和消费品等行业主导过十多年的大规模并购整合（M&A integrations）。在过往操盘这些大型并购交易的过程中，信任从来都不是我们在系统发布上线后，两手合十、祈祷它自然降临的侥幸产物；我们早在系统落地之前的第一天，就通过前置的变革管理与严密完备的风险管理体系，将信任扎实地工程化注入其中。因此，当全新平台正式切换上线时，业务一线的团队是真正能够放心依靠它的。如今的 AI 智能体也需要磨练出完全相同的这一套核心内功。一个智能体只有在能够兑现企业预算预期的商业价值，同时严格恪守在公司既定的风险偏好策略与各项监管红线之内时，它才算真正赢得了企业的信任。

<details>
<summary>Original English</summary>

**Michelle Brandt**: I have spent over 20 years in enterprise transformation and more than a decade leading M&A integrations across media, tech, and consumer goods on those deals. Trust was not something we crossed our fingers and hoped for after launch. We engineered it before day one through early change management and risk management. So when the platform went live, the teams on the ground actually relied on it. AI agents demand the exact same muscle. An agent earns trust when it delivers the value the business budgeted for while staying within the company's approved risk appetite policies and regulatory guardrails.

</details>

### 管理层必须回答的核心三问与场景拆解

**Michelle Brandt**：以我的实战经验来看，企业管理层想要跨越这道信任鸿沟，关键在于明确回答三个非常直接的问题：第一，它到底创造了什么实际价值？第二，出现问题时由谁来承担兜底责任？第三，究竟有哪些确凿证据能赋予它拥有更高自主权的运营许可？

<details>
<summary>Original English</summary>

**Michelle Brandt**: In my experience, leadership gets there by answering three straightforward questions: What value does it create? Who is on the hook for it? And what evidence gives it permission to run with greater autonomy?

</details>

**Michelle Brandt**：一旦一个智能体迈出了隔离沙箱、直接嵌入到核心业务工作流中，整个评估测试的性质便发生了彻底的转变。概念验证（Pilot）测试的仅仅是软件功能是否正常运转，但唯有进入日常运营，我们才能真正检验出它能否在领导层设定的管控边界之内持续创造价值。目前业内现存的 AI 风险治理框架确实能够为你提供坚实的指导原则；但它们唯一无法直接给到你的，是如何将这些抽象原则逐一映射并落地到每一个具体的智能体上。对于系统中的每一个智能体，管理层都必须切实行使决策权并明确四件事：它被获准执行什么操作？具体由谁对它负责？它必须记录哪些确凿证据？以及在什么条件下触发向上升级与干预？这项界定工作绝非纯粹的技术工程任务，而是一项实打实的高管运营刚性指令，今天我就将向大家剖析如何全面落实这项要求。

<details>
<summary>Original English</summary>

**Michelle Brandt**: The moment an agent steps out of a sandbox and into a core business workflow, the entire test changes. A pilot tests whether the software functions, but daily operations is where we test whether it creates value within the controls set by leadership. Established AI risk frameworks give you strong principles. What they do not give you is how to apply these principles to each agent. For every agent, leadership has to decide four things: What is it permitted to do? Who owns it? What evidence it records? And what triggers an escalation? That work is not an engineering task. We find it is an executive operating mandate, and today I'll show you how to meet it.

</details>

**Michelle Brandt**：让我们把这些概念扎根到一个极其真实的业务场景中来讨论。设想一桩规模高达 150 亿美元的大型并购交易，其既定目标是实现 4 亿美元的净协同效益。目前交易已经正式完成交割，后续的整合工作全面铺开。整合管理办公室（Integration Management Office，即我们今天简称的 IMO）正统领推进跨越 40 个工作流的协同效益落地路线图，其工作涵盖了从精简重构供应商合同到合并整合核心 ERP 系统的方方面面。每一个单项整合倡议，背后都有一位专属的业务负责人，对其最终沉淀到底线的真金白银成本节约完全担责。

<details>
<summary>Original English</summary>

**Michelle Brandt**: Let us ground this in a real-world scenario. Picture a $15 billion acquisition targeting 400 million in net synergies. The deal has already closed and the integration efforts are now underway. The integration management office, which we'll also refer to as the IMO today, is driving the synergy roadmap across 40 workstreams, covering everything from rationalizing vendor contracts to consolidating ERP systems. And every single initiative has a business owner accountable for its bottom line savings.

</details>

**Michelle Brandt**：在以往的传统流程中，IMO 的分析师们每周都需要从全部 40 位工作流负责人那里死磕跟踪最新进展，并将汇总上来的业务数据与总账系统（General Ledger）逐笔进行核对平账。他们还要逐项比对实际发生成绩与原定预算规划之间的差异。随后，他们必须把所有这些繁复的分析材料拼装成面向指导委员会（Steering Committee）的高管汇报材料（Executive Deck）——该委员会由首席财务官（CFO）、首席风险官（CRO）、各大业务单元总裁以及整合总负责人共同组成。

<details>
<summary>Original English</summary>

**Michelle Brandt**: Every week, analysts in the IMO are going to reconcile the numbers against the general ledger as they track down status from all 40 leads. They're also comparing actuals against the plan, then finally assembling the executive deck for the steering committee, which is going to include the CFO, the chief risk officer, business unit heads, and the integration lead.

</details>

**Michelle Brandt**：面对这样的工作强度，工程团队针对自动化生成这版汇报初稿研发了一套智能体。该智能体能够自动抓取并摄入每周的各业务更新数据，全自动对齐核对总账，对照初始规划执行差异分析计算，并直接标记出那些进度明显落后于预期的业务倡议。初步运行看起来一切顺畅，于是团队决定开展为期四周的试点。结果令人欣喜：智能体自动生成的初稿内容与分析师们纯手工熬夜赶出的报告在细节上一行一行完全严丝合缝。从技术角度来说，技术本身毫无疑问是跑通了。但此时摆在面前的根本问题是：指导委员会在敢真正放心让它掌管业务运营之前，到底需要看到什么样的硬核业务价值？

<details>
<summary>Original English</summary>

**Michelle Brandt**: The engineering team builds an agent to automate that first draft. The agent then ingests the weekly updates, reconciles the ledger, runs variance math against the plan, and flags the initiatives that are falling behind. Everything looks good, and they decide to run a four-week pilot. The agent's draft matched the analyst reports line for line. So, we can say that the tech works. Now the question is what value does that steering committee need before they can trust it to run the business?

</details>

### 衡量业务价值的三大刚性指标

**Michelle Brandt**：首先，指导委员会需要一份书面成文的“价值论证案”（Value Case），且这份文件必须在智能体接触任何真实生产数据之前就全员达成共识并签署批准。在我们这个业务范例中，它具体落实在三项关键衡量指标上：第一项指标，我们来看工作流周期耗时（Cycle Time）。如果眼下人工编制那份每周综合汇报需要耗费整整 5 个工作日，你就需要为其设立一个刚性的缩减目标，例如硬性压缩到 2 个工作日以内。

<details>
<summary>Original English</summary>

**Michelle Brandt**: First, the steering committee needs a written value case agreed upon before the agent ever touches production data. In our example, that comes down to three specific metrics. First let's look at cycle time. If that weekly report needs five business days to compile right now, you're going to want to set a hard target such as 2 days.

</details>

**Michelle Brandt**：第二项指标是分析师的人工产能释放（Analyst Capacity）。如果原来需要 4 名分析师每周投入整整一半的时间专门用来汇总制作这套汇报材料，那么智能体成功接手后，每周就能直接给团队省出 80 个工时。但请务必注意：只有当整合负责人将这节省下来的 80 个小时，定向重新派驻并投入到那些协同效益严重滞后、急需支援以回归正轨的具体工作流攻坚中去时，这部分被释放的时间才能被合法算作创造的商业价值。不仅如此，你在核算这项价值收益时，还必须硬性扣除运行该智能体所耗费的底层算力开销、软件许可授权费以及人类员工介入审核与监督的全部人力成本，计算其净收益。

<details>
<summary>Original English</summary>

**Michelle Brandt**: Your second metric will be analyst capacity. If four analysts spend half of their week building the deck, that is 80 hours a week the agent gives back. That time counts as value only when the integration lead assigns it to the workstreams that are behind on their synergy targets and need help getting back on track. Then you only count that value after netting out the compute, licensing, and human review cost of running the agent.

</details>

**Michelle Brandt**：第三项指标则是重中之重，它是整个体系的核心命脉——异常检测耗时（Detection Time）。具体来说，这是指从底层业务数据首次显现出脱轨偏离迹象的那一瞬间开始，直到该异常偏差正式呈现在高管指导委员会眼皮底下所经历的时间跨度。单纯将周报生成周期从 5 天压缩到 2 天，并不能百分之百确保指导委员会能够更早捕捉到底层业务出现的滑坡；智能体本身必须具备主动嗅探并捕获这一偏差的能力，而价值论证案必须对这种检测时效做出直接而硬性的度量。

<details>
<summary>Original English</summary>

**Michelle Brandt**: Your third metric is the most important one: detection time. That is how long it takes from the first sign of a slip in the data to the moment the steering committee sees it. Cutting the report from 5 days to 2 days does not guarantee that the committee sees that slip any sooner. The agent has to catch it, and the value case measures that directly.

</details>

**Michelle Brandt**：上述列出的每一项量化指标，都无一例外地要求必须具备上线部署前的严格基线数据（Baseline）。如果 IMO 在今天拿不出哪怕一项指标的历史基线，那就坚决不要上线部署！因为如果你连最初起跑线的真实数据都无法度量，你就永远都不可能拿出铁证来证明这个智能体究竟有没有对业务带来实质性的推动与改变。

<details>
<summary>Original English</summary>

**Michelle Brandt**: Every single metric requires a predeployment baseline. If the IMO cannot state the baseline today, do not deploy. If you can't measure where you started, you can never prove the agent moved the needle.

</details>

### 三道防线风控模型与人工责任界定标准

**Michelle Brandt**：接下来，指导委员会迫切需要弄清楚：因引入智能体而产生的增量风险，到底归谁所有？在这里，我们将成熟的企业“三道防线”（Three Lines Model）风险治理框架完整映射应用到智能体身上。在第一道防线中，业务管理层拥有内控权与控制措施。整合总负责人就是终极责任行政主管（Accountable Executive）。她对智能体产出的所有结论与内容负有全部终极责任，其责任认定的严肃程度与她过去对人工手写编制的材料所承担的职责完全一模一样。

<details>
<summary>Original English</summary>

**Michelle Brandt**: Next, the steering committee needs to know who owns the risk the agent creates. We are going to apply the three lines model to the agent. In the first line, management owns the controls. The integration lead is the accountable executive. She owns the agent's output exactly the way she owned the manual deck.

</details>

**Michelle Brandt**：在第二道防线中，风险管理部门与合规部门负责对智能体进行常态化监督，并就其运行方式提出质询与挑战。他们审查介入的深度，完全取决于该智能体自身的风险暴露等级（Exposure）。一份仅作为内部工作草案、且必须经过资深分析师逐项严格筛查洗练的内容，其适用的风险审查标准，自然与一个将财务数字自动直达发布给公司董事会的全自主智能体有着天壤之别。而在第三道防线中，内部审计部门提供独立的客观鉴证支持，他们会基于实质性风险评估结果，严格判定何时以及以何种方式将该智能体列入公司的年度审计工作计划。

<details>
<summary>Original English</summary>

**Michelle Brandt**: In the second line, risk and compliance oversee the agent and challenge how to run it. How deep they go depends on the agent's exposure. An internal draft scrubbed by a senior analyst warrants a very different review standard than an autonomous agent publishing figures straight to the board. In the third line, internal audit provides assurance, deciding based on material risk when and how the agent enters the annual audit plan.

</details>

**Michelle Brandt**：此外，每个智能体还必须明确指定一名专职员工进行日常督导。在我们这个场景中，该职责落在了资深分析师身上。他在初稿递交给指导委员会审阅之前进行严格把关。她的这一监督岗位必须具备四项极其具体的核心履职能力：第一，她必须能够透彻理解智能体的具体业务运行边界；第二，她必须能够结合上下文准确解读智能体的各项输出；第三，她必须拥有直接推翻、覆盖或撤销该输出的法定授权；第四，她必须拥有清晰易用的物理“紧急制动断电开关”（Kill Switch），一旦智能体表现出意料之外的失控行为，能够第一时间安全、彻底地将其关停。

<details>
<summary>Original English</summary>

**Michelle Brandt**: The agent also needs one employee assigned to oversee it every day. In our example, that is the senior analyst. He reviews the draft before it reaches the committee. Her role requires four specific capabilities: She has to first understand the operational boundaries. She has to interpret its output with context. She must have the authority to override or reverse it. And she needs a clear kill switch to shut it down safely the instant it behaves unexpectedly.

</details>

**Michelle Brandt**：所谓权责落地，同样意味着必须清晰界定智能体权力的终点在哪里。我通常会将这套规范精炼在一份仅有一页纸的管理制度中，称之为“人类工作标准”（Human Work Standard）。对于整个业务流程中所遭遇的每一个关键决策分叉点，该制度都会明确映射出：具体面临的决策事项是什么、被正式授权作出该裁决的人类角色是谁、作出决策所需的必备证据清单、以及明确的向上升级汇报路径。

<details>
<summary>Original English</summary>

**Michelle Brandt**: Accountability also means defining where the agent's authority stops. I document this in a one-page policy called the human work standard. For every fork in the process, it maps the decision, the human role authorized to make it, the required evidence, and the escalation path.

</details>

**Michelle Brandt**：这些具体的决策权在业务的每一个层级都明确存在。资深分析师有权判定某个财务差异究竟纯粹属于会计记账的时间性入账差异，还是意味着发生了真实的资金短缺缺口；各个具体工作流负责人有权决定采取何种具体补救措施来填补这一资金缺口；而整合总负责人则有权决定是否正式向最高层级的指导委员会发出预警信号，将该项目倡议正式标记为“存在违约风险”。智能体负责为上述每一个关键决策准备严密详尽的前置分析，但它的职权范围仅限于此，绝不能越雷池一步。谁作出最终决策，谁就必须对该决策所引发的一切商业后果全权负责。

<details>
<summary>Original English</summary>

**Michelle Brandt**: These decisions exist at every tier. The senior analyst decides whether a variance is an accounting timing difference or a real cash shortfall. The workstream lead decides how to remediate that shortfall. And the integration lead is going to decide whether to formally flag an initiative as at risk to the steering committee. The agent prepares the analysis behind every one of those decisions, and it stops there. The person who makes the decision owns the consequence.

</details>

**Michelle Brandt**：因此，将这些关键商业决策权牢牢保留在你们团队的人类手中，并不会拖慢智能体自身的运转速度。智能体完全可以投入生产使用，而与此同时各个岗位的人类角色也完整保留各自的法定决策权。在整个流程中，唯一能够正当延期上线部署的合理借口，就是出现了某个尚未明确指定人类负责人的真空决策项。换言之，如果在高管团队内部甚至尚未就“究竟由谁来正式宣布某项业务倡议彻底脱轨”达成一致授权，那么智能体在前端哪怕发出再多危险预警，最终也根本无法驱动任何实质性的落地行动。

<details>
<summary>Original English</summary>

**Michelle Brandt**: So, keeping these decisions with your team does not slow the agent down. It can go into use while each role keeps its authority. The one reason to delay deployment is a decision with no assigned owner. This means if leadership has not agreed who declares an initiative off track, the agent's flags lead to no action.

</details>

### 面向工程交付的三大核心治理构件

**Michelle Brandt**：至于第三个关键问题，那就是在座各位工程师们大显身手的领域了。赋予智能体更高自主权的底气与证据，完全源自于智能体在工程底层是如何被构建出来的。在技术落地层面，我重点考察三项核心交付构件（Artifacts）：

第一项构件，是完备可审计的决策日志（Auditable Decision Log）。对于该智能体评估分析的每一个业务工作流，日志中都必须详实记录下所摄入的原始输入数据、实际执行调用的工具抓取痕迹、具体的提示词与调用的模型版本信息、系统生成的具体输出结果，以及人类负责人的最终审批签字确认记录。

<details>
<summary>Original English</summary>

**Michelle Brandt**: The third question is where the engineers in this room come in. The evidence for greater autonomy comes from how the agent is built. I look for three artifacts. The first is an auditable decision log. For every workstream the agent evaluates, it records the raw data ingested, the tool calls executed, the prompt and the model versions, output generated along with the human signoff.

</details>

**Michelle Brandt**：在工程架构上有两项至关重要的技术选型，能够让这份审计日志做到滴水不漏、固若金汤：首先，你系统的核心数学运算与对账核算规则，必须全部交由确定性的、经财务团队官方认证的确定性代码来执行计算，绝不能任由大语言模型（LLM）通过模糊的对话式散文来即兴推算生成！其次，必须将大模型生成的文本摘要仅仅视作一种辅助理解的解释说明，切不可将其当成铁证。真正无可辩驳的证据只存在于底层的遥测数据（Telemetry）之中——究竟调取了哪些原始数据库记录？实际运行了哪些确定性工具脚本？以及到底是谁对复核结果签了字？如果业务上报上来的节约金额与总账数据对不上，智能体绝不能擅自去修改或捏造这个数字；它唯一要做的就是直接将该差异高亮标记出来，并迅速沿着升级链路路由上报。

<details>
<summary>Original English</summary>

**Michelle Brandt**: Two engineering choices make that log airtight. First, your core math and reconciliation rules must run in deterministic, finance-approved code, not generated as conversational prose from an LLM. Second, treat the model's written summary as a helpful explanation, not proof. Your real proof lives in the telemetry: What records were pulled? What deterministic tools ran? And who signed the review? If reported savings do not match the general ledger, the agent does not touch the number. It flags the discrepancy and routes it up.

</details>

**Michelle Brandt**：第二项核心构件，是模型资产档案记录（Model Inventory Record）。这份档案完整沉淀了该智能体的终极责任业务主管、详尽的数据血缘关系（Data Lineage）、跨底层源系统的全部依赖链路、系统验证测试记录、明确的异常升级路线，以及配套的紧急制动断电操作手册（Kill Switch Runbook）。而最关键的一点在于，它必须白纸黑字明确定义并记录你们的“回归触发条件”（Regression Triggers）——即对于我们依赖的上游基础模型或底层核心源 API，一旦发生任何重大版本变更或升级，就会直接强制触发全流程回归验证……

<details>
<summary>Original English</summary>

**Michelle Brandt**: The second artifact is the model inventory record. This captures the accountable executive, data lineage, dependencies across source systems, validation results, escalation path, and the kill switch runbook. Most importantly, it documents your regression triggers, which are any updates to our parent base model or source API that...

</details>

<!-- chunk 25/51 -->

### 自主权计分卡与 AI 智能体治理的四个阶段

**Speaker A**: 在重新投入生产运行之前，都需要进行全面的重新验证。

你的第三个核心交付物是自主权计分卡（Autonomy Scorecard）。指导委员会利用它分四个阶段逐步授予智能体自主权。

第一阶段是影子模式（Shadow Mode）。分析师们照常制作报告，智能体与他们并行运行，团队对两者的输出结果进行比对。

第二阶段是受监督的草稿模式（Supervised Draft）。智能体生成初稿，资深分析师逐项审查每一个条目。

第三阶段是异常与抽样模式（Exception and Sample）。在此阶段，分析师只审查被标记的举措，并对各项主张进行随机抽样审查。

然后是第四阶段，即纯异常模式（Exceptions Only）。分析师仅审查高风险的异常情况，同时辅以定期的独立抽样检查。

<details>
<summary>Original English</summary>

**Speaker A**: ...require full revalidation before running in production again.

Your third artifact, this is going to be the autonomy scorecard. The steering committee uses it to grant autonomy in four stages.

Stage one is shadow mode. The analysts build the report as they do today. The agent runs right alongside them and the team compares the two.

Stage two is the supervised draft. The agent compiles the first draft and the senior analyst reviews every single line item.

Stage three is the exception and sample where the analyst reviews flagged initiatives plus a random sample of the claims.

Then we have stage four where exceptions only, the analyst reviews only high risk anomalies supported by periodic independent sampling.

</details>

**Speaker A**: 不过，请务必密切关注第四阶段。因为一旦人类只关注异常情况，你最大的脆弱点就在于：智能体未能标记出的那些问题。

因此，我建议通过独立抽样来跟踪被遗漏的重大实质性问题，持续监控错误严重程度，并密切注视你的“人工覆写率”（Override Rate）。

人工覆写率下降并不必然意味着智能体变得更聪明了。它也可能意味着人类的审查深度下滑了。所以，独立抽样能够告诉你，你所面对的究竟属于这两种情况中的哪一种。

计分卡将这些控制指标与你的价值指标并排呈现：交付周期（Cycle Time）、投入的分析师工时以及异常检测时间。

借助这个单页视盘，指导委员会便可以做出清晰、高效且有数据支撑的决策：究竟是提拔该智能体进入下一阶段、维持现状、回退，还是将其降级回受监督的审查阶段。

<details>
<summary>Original English</summary>

**Speaker A**: Pay close attention to stage 4. However, because once humans only look at exceptions, your biggest vulnerability is what the agent failed to flag.

So, I advise tracking missed material issues through independent sampling, monitoring error severity, and watching your override rate carefully.

A falling override rate does not automatically mean the agent is getting smarter. It can also mean the depth of review has slipped. So independent sampling tells you which one of these you are seeing.

The scorecard puts those control metrics side by side with your value metrics: Cycle time, analyst hours deployed and your detection time.

And with that single page view, the steering committee can make clean, efficient, databacked decisions to either promote the agent, hold it where it is, step it back, or down to supervised review stage.

</details>

### 衡量智能体价值的三个核心问题与并购案例回顾

**Speaker A**: 让我们回到最初提出的那三个问题。针对你所构建、资助或治理的每一个智能体，都要问一问：

它创造了什么价值？
由谁对它负责？
又有什么证据允许它以自主方式运作？

在我们今天所讲的并购（M&A）案例中，智能体并不会凭空变出 4 亿美元的协同效应。采购、供应链和业务运营领导者们，是通过脚踏实地的整合工作来捕获这些价值的。

但智能体所带来的价值是非常清晰的：在预定计划之前数周提供经过验证的证据，从而为领导层争取到介入干预的时间窗口，此时这笔并购交易的协同效应依然能够被切实捕获。

打造一个能够跑通的智能体仅仅是第一步。回答好上述三个问题，才是让它赢得信任并在规模化生产中得以运行的关键。

谢谢大家。

<details>
<summary>Original English</summary>

**Speaker A**: So let's come back to the three questions. Ask them of every agent you build, fund or govern:

what value does it create?
Who is accountable for it?
And what evidence permits it operate with autonomy?

In our M&A example today, the agent does not magically create the 400 million in synergies. Procurement, supply chain, and operating leaders capture that value through the gritty work of integration.

But what the agent delivers is clear: Verified evidence weeks ahead of schedule. Giving leadership the runway to intervene while the deal's synergies can still be captured.

Building an agent that works is just the first step. Answering those three questions is what earns it the trust to run at scale.

Thank you.

</details>

### Jellyfish 视角：Token 成本其实微不足道

**Steve Jameson**: 大家好，我是 Steve Jameson，Jellyfish 的 AI 研究与工程负责人。我今天来到这里，是为了向大家揭示：为什么 Token 实际上是成本中微不足道的一部分。

我接下来要展示的研究结果，均来源于 Jellyfish 平台——这是业内规模最大的工程工作流数据集，且该数据集与 AI 遥测数据进行了联合分析。

众所周知，AI 成本正在节节攀升。与去年同期相比，支出激增了整整 60 倍。应用场景极其广泛多样，模型和评测套件（Harnesses）的性能也大幅提高，其前景固然令人振奋。然而，围绕预算和支出的讨论就没那么轻松愉快了。

这些讨论往往牵涉到你的同僚、高管层以及董事会。这些人从来都不是最容易沟通的受众，尤其是在你手头缺乏准确数据支撑的时候。而且在眼下，这涉及到的可是真金白银。

与此同时，产出也在提升。在过去这同一年的时间维度里，每位工程师合并的代码 PR（Merge PRs per engineer）数量上升了 43%。这是一个极其亮眼的成绩。我们此前从未在如此短的时间尺度内，目睹过如此巨大的生产力跃升。

无论是理论研究还是经验数据，都有大量证据表明是 AI 和智能体编程（Agentic Coding）在推动这些吞吐量增长。

甚至连我们的数据图表都清晰反映出了这种关联性。请留意转折点所在的位置：AI 支出在 2026 年初大幅攀升，而与此同时，工程师的吞吐量增幅也开始稳步攀升。

<details>
<summary>Original English</summary>

**Steve Jameson**: Hi, I'm Steve Jameson, AI research and engineering leader at Jellyfish. I'm here to show you why tokens are the cheap part. The research that I'll present is drawn from the Jellyfish platform, the industry's largest set of engineering workflow data joined to AI telemetry data.

It's no secret that AI costs are climbing. They're up 60x from this time last year. The use cases are wide and varied. The models and harnesses are getting much better. The implications are exciting. But discussions around budget and spend are not as much fun.

These conversations involve your peers and senior leadership and the board. Not always the easiest audiences, especially when you don't have the right data. And it's real money these days.

Output is up, too. Merge PRs per engineer are up 43% over the same one-year horizon. This is phenomenal. We've not seen productivity inputs like this, especially on this time scale.

There's plenty of research and anecdotal data to know that AI and Agenta coding are driving these throughput gains.

Heck, even our charts show the correlation. Notice where the inflection points are. AI spend increased in early 2026 when throughput gains start a steady increase of their own.

</details>

### 支出增长 60 倍与吞吐量增长 43%：如何理解这组矛盾数据？

**Steve Jameson**: 然而，在这两个数字之间存在着一种内在的张力。你该如何调和它们？

支出激增了 60 倍，而吞吐量增长了 43%。这究竟是好是坏？43% 是一个庞大的数字，但 60 倍同样惊人。

你怎么知道自己的投入是否充足？是否还有更多的生产力增益被锁在了未开出的支票后面？我们是否应该将投入增加 50%、甚至翻一倍？抑或者，你怎么知道自己是否已经花得太多了？

我相信在座的许多人都感受到了这种张力。首席财务官（CFO）或董事会正在要求提供这些支出的明细收据。你能拿得出来吗？仅仅一句“合并 PR 数量增长了 43%”能让他们满意吗？

另外，如果你对 AI 的使用和支出加以限制封顶，会发生什么？你究竟是在防止团队盲目浪费 Token，还是在扼杀进一步提升效率的潜能？你可以向其他公司的同行打听他们的开销。但对许多人来说，这仍然是一个不断变化的动态目标。

可是，你又该如何把同行的开销套用到你自己的组织中呢？显然，单纯拿他们的账单和你的账单做横向对比是完全不够的。

我们都听说过各种报告：某某公司在 AI 上花费了 10 万美元、50 万美元，甚至数百万美元。随着现实情况的演变，他们设定预算，随后又不得不一次次重置 AI 预算。

归根结底，仅凭“支出增长 60 倍”和“吞吐量增长 43%”这两个孤立的数字，根本无法道出故事的全貌。即使将它们放在一起，它们也忽略了成本端最大的一笔开支。

<details>
<summary>Original English</summary>

**Steve Jameson**: There's a tension with these two numbers, though. How do you reconcile them? Spend is up 60x. Throughput is also up 43%. Is that good? Bad? 43% is a big number, but so is 60x.

How do you know if you're spending enough? Is there more productivity gain locked behind a checkbook? Should we increase spend 50%, 2x more? Or how do you know if you spent too much?

I'm sure many of you have felt the tension here. The CFO or board are asking for the receipts of the spend. Can you show them? Will merge PRs are up 43% satisfy them?

Also, what happens if you cap use and spend? Are you stopping from setting tokens on fire or are you stunting further efficiency gains? You can ask peers at other companies what they're paying. For many, it's still a moving target, though.

But how do you equate that to your org? Surely just comparing their bill to yours isn't adequate. We've heard the reports of companies spending 100k, 500k, even millions on AI.

Setting then resetting their AI budgets as reality sets in. Ultimately, these two numbers can't tell the story. And even together, they missed the biggest line on the cost side.

</details>

### PR 的智能成本：工资稀释效应

**Steve Jameson**: 这两个数字漏掉了所有成本中最大的一块——开发者的薪资。

AI 正在以我们前所未见的规模提高开发者的生产力。它不仅仅是另一个辅助工具，它代表着智能。这种智能从根本上改变了每位开发者能够产出的工作量。

这就是为什么我们需要换一种方式来审视它的成本：不要把它当成游离在边缘的管理间接费用（Overhead），而应将其视为生产每一个 PR 所需总成本的有机组成部分。我们将其称为“一个 PR 的智能成本”（Intelligence Costs of a PR）。

把付给工程师的薪水，加上支付给 AI 的费用，将它们合并算在同一个成本池中。在生产每一个单位的合并代码成本中，AI 仅占约 2.5%，而工程师薪水则占据了剩下的 97.5%。这与其他渠道公布的数据完全吻合，该数据截止到 2026 年 8 月。

在这里，Token 确实是便宜的部分。但这只是当前的相对成本结构，而不是绝对美元金额。接下来，让我们来看看过去一年中，每个合并 PR 的实际美元成本发生了怎样的变化。

过去一年里，每个合并 PR 的美元成本下降了 26%。请注意，这里计算的不是“创建的 PR”，而是“成功合并的 PR”。其中已经计入了代码审查时间，并且通过了一定标准的质量关卡。

<details>
<summary>Original English</summary>

**Steve Jameson**: These two numbers leave out the biggest cost of all, developer salary. AI is making developers more productive on a scale we haven't seen before. It isn't just another tool. It's intelligence.

This intelligence dramatically changes how much each dev can produce. That's why we need to think about its cost differently. Not off to the side as overhead, but as part of what it takes to produce each PR. We're going to call this intelligence costs of a PR.

What you pay your engineers plus what you pay for AI, put them together in one cost bucket. AI is about 2.5% of the cost to produce another unit of merge code. Salary is the other 97 1/2%.

This is in line with other reported figures. And this data is from August 2026.

Here tokens are the cheap part, but that's current relative costs, not dollars. Let's look at what happened to the cost of a merged PR over the last year.

The dollar cost of a merged PR fell 26% over the last year. Not PRs created but PRs merged. Review time is factored in and some level of quality gates has been cleared.

</details>

### 83% 的企业 PR 单位成本下降：为什么重度投入带来更高回报？

**Steve Jameson**: 每个合并 PR 成本下降 26% 的这一结果，是在同期 AI 支出激增 60 倍的背景下实现的。而且这种变化几乎是普遍存在的：在我们调研的企业中，有 83% 的公司其单个 PR 的单位成本都出现了下降。

这告诉了我们什么？额外的吞吐量增长，正在将工程师的固定薪资摊薄到更多的 PR 之中，而这一摊薄的速度远远快于 AI 支出的增长速度。

那么，各家企业在 Token 支出上的分布跨度有多大呢？我们按 Token 使用量对企业进行了排名，并将它们划分为五分位数（Quintiles）组。这个跨度范围非常宽广：

使用量最轻的一组，AI 费用仅占单个 PR 成本的约 0.3%，相当于每位开发者每月消耗约 6000 万个 Token。

而在每位开发者 AI 支出最高的前 20% 这一组中——我们称之为重度支出组（Heaviest Spend Group）——AI 占到了单个 PR 成本的 8.5%。这相当于每位开发者每月消耗约 25 亿个 Token，比最轻的一组高出了大约两个数量级。

我们将在接下来的幻灯片中使用这些分组，来观察 Token 支出究竟是如何影响其他指标的。

首先看 PR 吞吐量指标——即按照上一张幻灯片相同的 AI 支出五分位分组，计算每位开发者合并的 PR 数量。处于后 80%（前四个五分位）的支出企业，其 PR 吞吐量增幅大约在 40% 左右波动。

但是，重度支出组的表现明显优于其他人，其吞吐量增幅达到了 67%。更高的 AI 支出换来了更高的吞吐量增益。

<details>
<summary>Original English</summary>

**Steve Jameson**: What that decline in cost per merge PR includes a 60x increase in AI costs over the same time frame. The change is nearly universal too. 83% of the companies we studied showed a drop in cost per PR.

What does this tell us? The additional throughput gains are spreading salary thinner across PRs and this is happening faster than the AI costs are increasing.

What's the range in token spend? We ranked companies by token usage then group them into quintiles or fifths. The range here is quite large.

The lightest group about 0.3% of the cost of a PR is AI. This represents about 60 million tokens per dev per month.

The top 20% of AI spend per dev, we're going to call the heaviest spend group. There 8 and a half% of the PR costs is AI. This represents about 2.5 billion tokens per dev per month, about two orders of magnitude more than the lightest group.

We'll use these groups on the next slides to see how token spend influences other metrics.

First, PR throughput measured as merge PRs per dev split by the same AI spend quintiles on the previous slide. The bottom four fifths of spenders saw PR throughput gains of around 40%, give or take. But the heavy spend group improved more at a 67% increase. More AI spend led to more throughput gains.

</details>

### 规模效应与边际效益递减：从数据看投入曲线

**Steve Jameson**: 现在我们来看看单个 PR 的成本。各组再次展现出全面的积极成效：所有 AI 使用组的单个 PR 成本均在下降。

然而，同样也是那最高五分之一、也就是 AI 投入最多的企业，改善幅度最大。他们在过去一年中实现了单个 PR 成本下降 32%。相比之下，其他四个组别的单个 PR 成本降幅大约在 25% 左右。

在 AI 上投资和投入更多，相比那些投入较保守的同行，更有力地推动了单个 PR 成本的优化。正如我们在总体平均水平中看到的那样，单个 PR 成本的变化主要是由 PR 吞吐量驱动的，而非受控于 AI 支出。

重度投入者获得了 67% 的 PR 吞吐量增益，而他们的同行增幅约为 40% 左右。将相同的工资总额分摊到单月产出的更多 PR 上，其产生的正向效应要远大于上升的 AI 支出，因为归根结底，Token 是其中较为便宜的要素。

但这绝不是说企业就应当毫无顾忌地挥霍 Token、肆意乱花。

在这里，我们以横轴代表 Token 使用量，纵轴代表单个 PR 的成本。在曲线的起始阶段有一个陡峭的下降坡度，即在初期相对少量的 AI 投入就能带来巨大的收益。随着 Token 使用量的进一步增加，每个 PR 成本的改善幅度开始减缓。

这就是边际效益递减（Diminishing Returns）。但我想要特别强调的是：边际效益递减并不等同于毫无效益。

我们看到，前 10% 的企业所消耗的 Token 数量是中位数企业的 8 倍，但他们仍然多实现了 25% 到 27% 的更低...

<details>
<summary>Original English</summary>

**Steve Jameson**: Now let's look at the cost per PR. Positive results are seen again across the board. Cost per PR is dropping for all AI usage groups.

However, again, the heaviest fifth, so the companies that spent the most improved the most. They saw a cost per PR decrease of 32% over the last year. The other four groups saw about a 25% decrease in cost per PR.

Investing and spending more on AI fueled more of an improvement in cost per PR compared to peers who leaned in less. So we saw that the same as we saw in the population average cost per PR changes are driven largely by PR throughput not by AI spend.

The heavy spenders experienced PR throughput gains of 67% compared to about 40ish% for their peers. Spreading the same salary across more PRs in the month has more of an effect than the rising AI costs because tokens are the cheaper.

This is not to say that orgs should light tokens on fire and spend with abandoned.

Here we're looking at tokens used on the horizontal axis and cost per PR on the vertical axis. There's a steep drop at the beginning where relative small AI spend results in large gains initially. As token usage increases, the cost per PR improvement decreases.

This is diminishing returns. I want to stress though, diminishing returns is not the same as no returns.

We're seeing that the top 10% are spending 8x the tokens compared to the median and achieving a 25-27% lower...

</details>

<!-- chunk 26/51 -->

### 开发者个体维度的代币消耗与产出效应

**Steve Jameson**：每个 PR（Pull Request）的交付成本。未来也许会出现代币（token）不再便宜的时期，但大体而言，对于现存的大多数公司来说，我们离那个临界点还相差甚远。更多的代币投入带来更多的 PR 产出，进而促使实际交付成本显著降低。

到目前为止，我们探讨的都是公司层面的整体表现。接下来我想切换一下视角，聊聊我们针对开发者个体做的一项实证研究。在这项研究中，我们对比了同一批开发者在重度使用代币的周数与低代币使用周数的表现差异。

在个人层面上，我们同样观察到了完全一致的现象。对比每位开发者重度使用 Agent Skill（智能体技能）的周数与他们未使用 Skill 的周数：他们在代币上的花销大约翻了一倍，但合并的 PR 数量增加了 27%；而在将薪资成本与代币开销合并计算后，每个 PR 的平均成本下降了大约 18%。

<details>
<summary>Original English</summary>

**Steve Jameson**: cost per PR. There will be a time when tokens aren't the cheap part, but by and large for most companies out in the wild, we're not close to that threshold. More tokens leads to more PRs, which leads to a lower cost of delivery.

So far, we've talked about companies. Next, I'd like to take a tangent and talk about a study we did with developers. Here we looked at developer weeks with heavy token use compared to the same developer weeks with lower token use.

Here we saw the same phenomenon just at the individual level. Compare each developers heavy agent skill weeks with their own weeks without skills. They spend about twice as much on tokens. merge 27% more PRs and reach PR costs and each PR costs about 18% less once salary and tokens are counted together.

</details>

### 对速度、质量与 PR 规模的两大核心疑问

**Steve Jameson**：每当我向大家分享这项研究时，通常会收到两个非常合理的疑问。第一：干得更快是否会导致活儿干得更粗糙？第二：我们观察到的 PR 数量增加和吞吐量提升，是不是单纯因为任务被拆解成了更小的代码块？

针对第一个疑问：更廉价、更快捷的交付是否意味着质量劣化？如果 AI 让 PR 交付变得更快且成本更低，我们是否只是在加速推送更多错误？衡量这个问题的一个有效代理指标是回滚（reverts），即专门用来撤销先前某个 PR 的合并提交。

数据表明，代币使用量前五分之一的重度用户组，在代币大幅增长之前其回滚率本身就处于最低水平；而在全面采用之后，所有分组的回滚率其实都有微幅下降。尽管这些变化幅度略低于数据本身的统计噪声区间，无法作为质量必然有所提升的硬性证据，但更为关键的是：即使伴随着更高的代币支出和更快的 PR 吞吐量，我们也完全没有看到任何质量失控或严重恶化的警示信号。

<details>
<summary>Original English</summary>

**Steve Jameson**: There are two fair curiosities I get when I talk about this work. First, does faster work result in worse work? And second, are the more PRs, the throughput gains that we're seeing, are they being driven by smaller chunks of work?

First curiosity is cheaper, faster work, worse work. If AI makes PRs faster and cheaper, are we just shipping more mistakes? One proxy for this is re reverts. Merge PRs that undo an earlier PR.

The heaviest fifth started lowest before most of the token growth and revert rates dropped slightly for every group. Though these deltas are just slightly below the noise in the data. It's not evidence of improvement here. However, more importantly, we're not seeing any worrying signs of rampant or severe quality issues with higher token spends and faster PR throughput.

</details>

**Steve Jameson**：针对第二个疑问：吞吐量提升是否由更小粒度的 PR 所驱动？答案显然是否定的，PR 并没有变小。事实上，AI 反而促使每个 PR 生成的代码行数（lines of code）出现了增长。在场的开发者对此想必毫不意外——如果你曾对那些冗长、毫无必要的内联 AI 注释，或者塞满大量无关测试用例的代码文件翻过白眼，请举起手来。生成式 AI 天生就偏爱生成海量代码。

此外，开发者的创建门槛被大幅拉低，大家往往倾向于在单个 PR 中多做一些改动，而不是重新开一张工单。开发者心里会想：“只要再输入一两个 Prompt，我就能顺带把这个边缘情况也处理掉，或者顺手把这两个模块拼合在一起。”这样可以减少需要多方协调的 PR 数量。然而，这种趋势与当下大家在 PR 审查时感受到的压力确实并不完全契合。

同时，由于 AI 自身的能力日益强大，我们的工程野心也随之水涨船高。在此次演讲中，我们暂不深入探究究竟是哪些具体机制主导了代码行数的变化；但可以确认的是，PR 吞吐量的提升绝非来自更小的 PR 切片。这虽然符合大部分人的直觉，但通过数据加以验证依然极具价值。

<details>
<summary>Original English</summary>

**Steve Jameson**: The second curiosity is throughput driven by smaller PRs and this is demonstrabably no not smaller PRs. In fact, AI is driving an increase in line lines of code generated per PR. This is no surprise to the devs in the room. Raise your hand if you've rolled your eyes at verbose, unnecessary inline AI comments or a file full of mostly irrelevant tests. Gen AI Gen AI likes to generate code.

Also, the bar to create is low for devs, and there's a pull to do more per PR instead of spinning up another ticket. It's just one, maybe two prompts, and I'll handle this edge case, or I can combine this and that element. Fewer PRs to wrangle. This doesn't mesh well with the PR review stress folks are feeling these days, though.

Also, AI is just becoming more capable, so we're getting more ambitious. It is beyond this talk to dig into what's actually driving those level of lines of code changes. However, the increase in PR throughput is not coming from smaller PRs. This is intuitive for most, but it's still good to verify.

</details>

### 将智力投入纳入总账：重新定义每个 PR 的交付成本

**Steve Jameson**：回到我们开篇提出的问题：花费 60 倍的支出去换取 43% 的产出提升，究竟值不值得？脱离整体孤立地看，你根本无法得出结论。这两项指标你都应该追踪，它们确实是很重要的支撑性度量指标：每个 PR 摊销的 AI 花销，代表你为了让开发者跑得更快而作为生产资源购买的外部“智力”；而每名工程师产出的 PR 数量，则是你投入这笔开销所换来的直接回报。

然而，仅盯着这两项数据会掩盖本质的商业权衡。一旦你把工程师的薪资代入公式，并计算总成本与交付吞吐量之间的比率，答案便一目了然：在同一时期内，每个 PR 的综合成本下降了 26%。毫无疑问，尽管云端账单在不断攀升，AI 依然在强力推动整体成本效率的提升。

而且，相对而言，换取这些效率提升所需的 AI 支出比例其实非常小。AI 成本在单个 PR 的总成本构成中依然只占极小的份额——平均仅为 2.5%，即便在支出最高的重度消费群体中也不足 10%。在我们观察到的数据区间内，代币始终属于廉价投入部分，增加投入持续获得了正向回报。重度代币使用者的 PR 吞吐量增长了 67%，而低消费同行仅增长了 40%；这推动重度用户的单 PR 成本下降了 32%，相比之下低消费同行仅下降了约 25%。纵观 PR 成本与代币使用量的比率曲线，按代币消耗量排在前 10% 的公司月份，其消耗的代币高达中位数的 8 到 10 倍，但每个 PR 的交付成本反而比中位数低了 25%。

<details>
<summary>Original English</summary>

**Steve Jameson**: Back to the opening question. Is 60x more spend worth 43% more output? You can't tell in isolation. You should track both. They are important numbers, but they're supporting metrics. AI spend per PR is the intelligence that you're buying as a resource to help make your devs go faster. PRS per engineer is what you're getting with that spend.

However, looking at those hides the trade-off, but put salary into the equation and take the ratio of cost to throughput and there you get your answer. Cost per PR is down 26% over that same time period. It's clear AI is driving cost efficiencies despite the increasing bills.

And the AI sp the AI spend needed to get those efficiencies is small relatively speaking. AI is still a sliver of what a P PR costs two and a half% on average under 10% for the heavy spender group. Tokens are the cheap part in the range that we see more spend kept paying. Heavier token users saw 67% PR throughput gain compared to 40% for their lower spend peers. This drove cost per PR down 32% compared to about 25% for the lower spend peers. Looking at the PR cost to token ratio curve, the top 10% of company months by token usage resulted in 10 or 8x the tokens, but 25% lower cost per PR compared to the median.

</details>

**Steve Jameson**：AI 正在以前所未有的规模全面提升开发者的生产力。它绝非另一款普通的辅助工具，而是一种从根本上改变每个开发者产能上限的通用智力。正因如此，我们必须以截然不同的思维方式来看待它的成本：不能把它当成可有可无的边缘间接开销（overhead），而应将其视作交付每个 PR 所必需的基础生产要素。你需要把 AI 支出和人类工程薪资支出加总在一起，才能精准核算出每个 PR 的真实成本。

这绝不意味着企业可以肆意挥霍。当然，你必须严密监控失控的死循环任务，也必须精细追踪 AI 消费账单；我并不是建议大家忽视每个 PR 分摊的 AI 费用，而是强调绝不能让单一的代币支出成为主导你的决策核心指标。

这种全新的认知框架可能会影响你对其他工程投资的时机与方向判断，例如评估何时引入模型路由器（model router）、何时对私有模型进行后训练（post-training），或是何时施加代币限额。试问：你是能通过死磕压低 AI 成本挖掘出更多利润，还是通过持续投资于能放大吞吐量的举措（例如深化 AI 赋能）来获得更高的整体效益？无论选择哪条路径，请务必每月追踪每个 PR 的“总智力成本”（人类薪资 + 机器智力）。对照每月的 AI 账单和 PR 吞吐量曲线，观察团队的发展趋势如何：交付吞吐量是否在持续攀升？交付成本的效率收益究竟如何？

与此同时，一定要紧盯回滚率等工程质量指标，将其作为制衡杠杆。我们决不能容忍低劣的“AI 工业废料”阻塞了研发齿轮。因此，在迈入预算规划季时，请把“单 PR 成本”带到管理层的谈判桌上。不要只汇报膨胀的代币账单，也不要只炫耀吞吐量的跃升——账单只能说明你花了多少钱，而单 PR 成本才能告诉你这笔投资到底是否奏效。就目前绝大多数企业而言，数据给出的明确指引是：继续加大投资，在获取交付效率的道路上，代币依然是最廉价的杠杆。

干得漂亮，感谢各位坚持听到最后！如果大家希望持续了解我们的最新研究动态（这些洞察均提炼自业界规模最大、真实运行的工程工作流及 AI 遥测数据集），欢迎在 LinkedIn 上关注我、我的同事们或 Jellyfish 官方账号，也可以订阅我们的 Substack，或查阅 Jellyfish 官网博客。如果你希望在自身组织内建立针对研发工作流与 AI 效能（包括每个合并 PR 成本）的追踪体系，欢迎前往我们的官网预约演示，或者直接与我联系，我会帮大家对接最合适的专家团队。再次自我介绍一下，我是 Steve Jameson，Jellyfish 的 AI 研究与工程负责人。感谢大家观看，祝好！好的，搞定。

<details>
<summary>Original English</summary>

**Steve Jameson**: AI is making developers more productive on a scale we haven't seen before. It isn't just another tool. It is intelligence which changes how much each dev can produce. That's why we need to think about its cost differently. Not off to the side as overhead, but part of what it takes to produce each PR. You need to add the AI spend and the human spend, the human salary spend together to calculate your real costs per PR.

This isn't to say spend frivolously. Sure, you should watch for runaway jobs. You should track your AI spend. I'm not saying don't look at how much AI is going how much AI spend is going in each PR. I'm saying don't let that be your driving metric. A new framing might steer how and when you think about other investments like integrating model routers, post-training your own model, implementing token limits, etc. Will you get more efficiencies out of trying to control AI costs or by continuing to invest in things that increase throughput like more AI enablement?

Either way, track the total intelligence costs human plus artificial per PR every month. Next to that AI bill and next to the PR throughput, how are you trending? Is throughput continuing to improve? What about those cost efficiencies, the cost to deliver? Watch reverts and quality metrics beside all of this as a counterwe. We don't need AI slot mucking up the gears.

So heading into budget season, bring cost per PR to the table. Not just your token bill, not just the throughput bump. The bill tells you what you spent. Cost per PR tells you whether it worked. And right now for most companies, it says keep investing. Tokens are the cheap part to get efficiency gains.

Well done. You made it to the end. Here's how you can stay up to date with our latest research, which again draws from the largest engineering workflow and AI telemetry data set in the industry. You can follow me on LinkedIn, my colleagues or jellyfish. Subscribe to our Substack or you can check out our Jellyfish blog on the website. If you want help tracking your org's engineering workflow and AI effectiveness, including cost per Merch PR, go to our website and book a demo or reach out to me and I'll get you connected to the right folks. Again, I'm Steve Jameson, AI research and engineering leader at Jellyfish. Thanks for watching. Cheers. Okay. Yeah.

</details>

### 新节目录制筹备：引入智能体协助播客

**Cliff**: 我们是打算叫它 Jurro，还是不要？

<details>
<summary>Original English</summary>

**Cliff**: Do we want to call it Jurro or No.

</details>

**Speaker A**: 可以啊，我们可以叫它 Jirro。我们就直接说“这是我们的智能体 Jurro”。我觉得这也可以设计成一个很棒的剪辑过渡点，比如我们直接问它：“Jirro，你准备好开始了吗？”

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, we could call it Jirro. We could just be like this is our agent Jurro. I think it's also like a helpful potential cut which is like if we ask Jirro like are you ready to get started?

</details>

**Cliff**: 好啊，没问题。

<details>
<summary>Original English</summary>

**Cliff**: Yeah, sure.

</details>

**Speaker A**: 然后你看，我们的画面可以切过去，Jirro 可以在屏幕上画点什么示意一下，当作一个过渡转场画面。

<details>
<summary>Original English</summary>

**Speaker A**: And then like you know our video can move Jirro can like draw something acknowledgement whatever a transition pain.

</details>

**Cliff**: 没错。

<details>
<summary>Original English</summary>

**Cliff**: Yeah,

</details>

**Speaker A**: 一个过渡剪辑。好的。

<details>
<summary>Original English</summary>

**Speaker A**: transition cut. Okay.

</details>

**Cliff**: 行。

<details>
<summary>Original English</summary>

**Cliff**: Yeah.

</details>

### AIE 线上专场开场：什么是 SecMaster？

**Speaker A**: 好的，那我们开始吧。感谢各位前来收看 AIE 线上专题的分享。说“前来收看”其实不太确切，因为大家显然并没有和我们同坐在一个房间里。

<details>
<summary>Original English</summary>

**Speaker A**: All right. Um let's get started. Um thanks guys for coming to listen to a talk on the AIE online track. I guess coming to listen is not quite right because obviously you guys are not in the room with us.

</details>

**Cliff**: 毕竟省去了大老远舟车劳顿。

<details>
<summary>Original English</summary>

**Cliff**: Making the long long trip.

</details>

**Speaker A**: 是啊，省去了漫长奔波的长途跋涉。对对对，免去了那趟艰苦卓绝的旅程。

每次做这类分享，我们都希望在内容形式上玩出一点新花样。说实话，我个人并不太喜欢深夜一个人待在房间里对着 Loom 录屏工具机械地翻讲幻灯片。所以这次我特意拉上了 Cliff 一起来尝试些新形式——我们希望采用类似播客的方式来呈现。

这一方面是因为有多个人一起交流、碰撞火花感觉很棒；另一方面也是因为我们想探索一种把我们的智能体 Jiro 融入进来的全新方式。显而易见，在我们这边，Jirro 并没有直接实体坐在我们身旁，它其实是运行在这台电脑之中的。但当大家在 YouTube 上观看时，希望我们三方都能共同出镜呈现给大家：我和 Cliff 负责对话讨论，而 Jurro 则坐在中间负责绘图拆解和直观展示。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Making the long long trip. Yeah. Yeah. Yeah. the arduous journey.com.

Whenever we do these kinds of talks, we always want to play around with the format a little bit. You know, I'm not a huge fan of just standing in front of a loom and doing slides late at night in my room. Um, so I dragged Cliff along to do something a little bit different. We wanted to do this in a little bit of a podcast format. Um, and part of that is just because it's nice to have multiple people to like riff with and bounce ideas off of, but also because we wanted to find a way to include Jiro, our agent. Um, so obviously, you know, on our side, Jirro is not quite in the room with us. He's kind of living on this computer. Um, but when you guys are watching this on YouTube, hopefully you'll have all three of us present. Uh, you'll have me and Cliff talking and then Jurro will be sort of in the middle drawing things out and describing uh describing things. Um,

</details>

**Cliff**: Jurro，请跟观众挥手打个招呼吧。

<details>
<summary>Original English</summary>

**Cliff**: Jurro, please wave hi for the viewers.

</details>

**Speaker A**: 没错，Jurro，请跟观众挥手打个招呼。

我们这场演讲的核心主题是深入剖析 SecMaster（证券主数据系统）。本次分享隶属于 AIE 纽约大会，该峰会自然是深度聚焦于金融领域，特别是 2026 年人工智能在金融科技中的前沿应用。因此我想，在正式深入展开之前，我们俩先简单做个自我介绍会比较合适，随后我们可能需要先厘清几个基础定义：到底什么是 SecMaster？什么是云原生智能体（Cloud Agent）？它们究竟如何协同运作？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, Jurro, please wave hi for the viewers. Um, so this talk is all about identifying a secmaster. Um, this is part of AIE New York, which of course is very very focused on the finance and like AI and finance uh in 2026. Um, and so I think uh before we really dive in, maybe it makes sense for just us to briefly introduce ourselves and then we probably want to just give some definitions even like what is a secmaster? What is a cloud agent? How do

</details>

<!-- chunk 27/51 -->

### 嘉宾背景与跨界对话的契机

**Amole**：……你们是否会利用智能体（Agent）来处理其中的任何事务？那么，我先来做个自我介绍。我叫 Amole，是 Nori Agentic 公司的首席执行官（CEO）。正如各位可能已经猜到的那样，我们投入了大量精力来深入思考云端智能体（Cloud Agents），以及如何将智能体部署在云端，用以解决金融领域以及各类不同行业中的实际问题。好的，Cliff，请你接棒。

<details>
<summary>Original English</summary>

**Amole**: ...you like use agents to do any of these things? Um, so I'll go first. Uh, my name is Amole. I am the CEO of a company called Nori Agentic. And as you might have guessed, we spend a lot of time thinking about cloud agents and how we can put agents in the cloud to solve problems both in finance and kind of all in a bunch of different industries. And yeah, Cliff,

</details>

**Cliff**：我是 Cliff，担任 Nori Agentic 的首席技术官（CTO）。在过去将近两年的时间里，我们一直专注于开发者工具（Dev Tooling）、AI 智能体以及这一形态产品的基础研发。

<details>
<summary>Original English</summary>

**Cliff**: I'm Cliff. I'm the CTO at Nor Agentic. We've been working on dev tooling, AI agents, this form factor for almost two years now.

</details>

**Amole**：是的。

<details>
<summary>Original English</summary>

**Amole**: Yeah.

</details>

**Cliff**：在那之前，我一直在从事数据工程方面的工作，曾为一家初创对冲基金从零搭建了一套全新的数据平台。再往前，我做过主任/资深软件工程师（Staff Software Engineer）。纵观我过去的这些经历，其实贯穿着一条非常清晰的主线：那就是数据工程、开发者工具，以及相当一部分的云原生基础设施（Cloud Infra）。

<details>
<summary>Original English</summary>

**Cliff**: And before that, uh, I was working on data engineering and building out a new data platform for a startup hedge fund. And before that, staff software engineering and there's kind of a throughine all those things with data engineering, dev tools, some amount of cloud infra.

</details>

**Amole**：是啊，说起来其实挺有意思的。这场对谈简直就是为你量身定做的。相比之下，我倒有点像个“局外人”——我的背景纯粹是机器学习（ML），从事人工智能与机器学习（AI/ML）这一行大概有十二年了；但我对金融领域可是一窍不通，完全不懂金融里的那些门门道道。所以今天的对话会非常有意思，因为在座的观众可能来自两个截然不同的阵营：一边是金融从业者，他们可能对人工智能的技术细节知之甚少；另一边则是 AI 工程师，他们或许对金融业务一无所知。因此，在正式深入之前，我们不妨先从几个最基础的核心定义切入，比如：究竟什么是云端智能体（Cloud Agent）？什么又是证券主数据（Security Master / Secmaster）？

<details>
<summary>Original English</summary>

**Amole**: Yeah, it's kind of funny actually. This is almost like a perfect talk for you. like I'm sort of the odd person out like I my background is in ML so I've been doing the a IML thing for like 12 years but like I don't know anything about finance like you know all the the finance stuff um so it's kind of an interesting conversation right because we have two potentially very different audiences in the room you have the finance folks who maybe don't know anything about AI and you have the AI engineer folks who maybe don't know anything about finance um so maybe it makes sense to even just get started with some definitions like what is a cloud agent and what is a secmaster before

</details>


### 核心定义：什么是云端智能体？

**Cliff**：好的。关于云端智能体，我认为在定义它之前，不妨先给出“智能体（Agent）”本身最简洁明了的定义：它本质上就是一个大语言模型（LLM）或基础模型，你让它在循环（Loop）机制中持续运行，并赋予它调用工具（Tools）的能力，从而使其能够自主执行某些你期望其完成的、具有实际价值的操作。

<details>
<summary>Original English</summary>

**Cliff**: yes So cloud agent the most succinct definition I think for just agent to start an LLM or a model that you run in a loop and give access to tools and so it can take some action that you hopefully find useful

</details>

**Cliff**：具体到云端智能体，你则是将整套运行形态——通常是那段在循环中不断调用模型的核心代码——整体迁移并部署到云端进程中运行。与此同时，你赋予它访问各类云端工具与接口的权限，而这些工具和资源往往是你的个人笔记本电脑、手机或其他本地设备所不具备的。

<details>
<summary>Original English</summary>

**Cliff**: specifically cloud agents you take that whole form factor usually the code that is calling the model in a loop and you put it in some cloud process and you give it access to tools that don't exist on your laptop or your phone or wherever else

</details>

**Cliff**：如此一来，这个由代码与模型构成的完整实体——一个有望带来巨大效用的全新基础原语（Primitive）——便完全运转在云端，并能够基于你所在企业的数据资产、业务流程，或是针对你个人的具体需求来主动采取行动。

<details>
<summary>Original English</summary>

**Cliff**: and now that whole entity that hopeful useful primitive runs in the cloud hopefully taking action with either your company's data and processes or your own needs

</details>

**Amole**：确实，如今企业海量最关键的核心数据本就已经沉淀在云端了。因此从某种意义上来说，将智能体部署在云端，让其在数据所在之处直接运行，本就是极其自然、顺理成章的选择。

<details>
<summary>Original English</summary>

**Amole**: and I mean so much of the important data now lives in the cloud so like in some sense it actually is like a very natural home for all of that to even run

</details>

**Cliff**：是的，我认为这里面确实存在一定的历史演进脉络。回顾去年，我们目睹了本地智能体（Local Agents）的爆发，伴随着代码助手在本地开发环境中的风靡，以及此前更早期的那些初代智能体原语……

<details>
<summary>Original English</summary>

**Cliff**: yeah I think it's there's a certain uh historicity of I think when we saw local agents take off right with the cloud code moment last year right and before that with earlier agent primitives

</details>

**Amole**：确实。

<details>
<summary>Original English</summary>

**Amole**: right

</details>

**Cliff**：我认为……

<details>
<summary>Original English</summary>

**Cliff**: I think

</details>

**Amole**：这几乎算得上是技术发展史上的一种奇特巧合：智能体居然是率先在本地端（Local First）流行起来的。

<details>
<summary>Original English</summary>

**Amole**: it's almost like a quirk of history that like it became local first.

</details>

**Cliff**：没错。

<details>
<summary>Original English</summary>

**Cliff**: Yeah.

</details>

**Amole**：起步阶段确实如此。

<details>
<summary>Original English</summary>

**Amole**: Just to start.

</details>

**Cliff**：但如果放眼长远，我们就会发现，真正要让纯边缘端（On-edge）的设备……

<details>
<summary>Original English</summary>

**Cliff**: And like the long run, we're going to see it take a lot longer for actual onedge

</details>

**Cliff**：……边缘设备要真正释放出实质性的业务价值，其实还需要漫长得多的时间。

<details>
<summary>Original English</summary>

**Cliff**: devices to really deliver value.

</details>

**Amole**：这就是云端智能体的概念：它们驻留在云端自主运行，你可以以异步（Asynchronous）的方式与它们协作，并通过跨多个不同的平台与之交互沟通。那么，什么是证券主数据（Security Master / Secmaster）呢？

<details>
<summary>Original English</summary>

**Amole**: So that's cloud agents, you know, agents that run in the cloud that you can basically do things with asynchronously and talk through across a bunch of different platforms. What about a sec master?

</details>


### 揭开金融核心基础设施的面纱：什么是证券主数据（Secmaster）？

**Cliff**：好的。

<details>
<summary>Original English</summary>

**Cliff**: Yes.

</details>

**Amole**：在这里我们可能需要多花些时间来深入探讨，因为我认为这个概念要晦涩得多。对于没有金融背景的普通技术人员而言，理解什么是“证券主数据（Secmaster）”，往往要比金融从业者去理解什么是智能体困难得多。

<details>
<summary>Original English</summary>

**Amole**: Now, we probably want to spend more time here because I think that this is a lot harder. You know, it's harder for the average, I think, person who's not in finance to understand what a sack master is compared to the other way around.

</details>

**Cliff**：而且我想，金融圈的人平时听说的关于智能体的内容，可能远比软件工程师听说的证券主数据要多得多。确实如此。

<details>
<summary>Original English</summary>

**Cliff**: And I think that people in finance have heard a lot more about agents in the other way. Yeah. Yeah.

</details>

**Amole**：软件工程师很少有人听说过证券主数据。

<details>
<summary>Original English</summary>

**Amole**: And software engineers. I've heard about a sackmaster.

</details>

**Cliff**：是的。

<details>
<summary>Original English</summary>

**Cliff**: Yeah.

</details>

**Cliff**：数年前我刚踏入这个领域时，也有完全一样的体会。当时我带着数据工程方面的专业知识，去协助一家初创对冲基金搭建交易系统并启动实际交易。所以，我认为一切都应该从“交易”切入来理解。从理论上讲，作为一家资产管理机构（Asset Manager），你的核心业务涵盖了一个可交易的资产标的池（Tradable Universe）。当然，资产管理机构的类型有很多种，我们今天没必要展开细说。但只要你的投资机构要运转，你就必须拥有一个主数据库（Master Database），里面完整记录了该可交易资产池中的所有证券标的。

<details>
<summary>Original English</summary>

**Cliff**: I certainly felt that way several years ago kind of jumping into that field to you know bring data engineering expertise to help a startup hedge fund begin trading. So I mean trading I think is the place to start. So you have in theory a tradable universe of assets that are core to your business as an asset manager. Many different types of asset managers. We don't even need to go there right now. But for your business to operate, you need some master database of all the securities that are in that tradable universe. Yeah.

</details>

**Amole**：所以从工程的角度来看，大家完全可以把它想象成存放在 Snowflake 或者 Databricks 等数据仓库中的一张数据表；但在实际业务场景中，它却是一项极端重要且不可或缺的核心业务运作原语（Operational Primitive）。

<details>
<summary>Original English</summary>

**Amole**: And so it's basically just like a table like for the engineering side you can kind of think of this as a table that lives in snowflake or you know data bricks or something like that but in practice it's actually like a really really important operational primitive.

</details>

**Cliff**：对。而且我想，如果你只是给出一套关于标识符（Identifiers）、基础资产（Assets）以及金融工具（Instruments）的标准化定义，并开始解释：“你看，这里有各种金融工具，其中一部分被证券化了，它们分属于不同的资产类别……”表面听上去，好像这就是它的全部内容了，似乎并不复杂。

<details>
<summary>Original English</summary>

**Cliff**: Yeah. And I think it's if you just give the right definition of identifiers and assets and instruments and you start to explain the difference between okay you have you know instruments and some of them are securitized and there will be different asset classes and okay that's that that seems like most of it.

</details>

**Amole**：没错。然而实际上……

<details>
<summary>Original English</summary>

**Amole**: Yeah. And then actually

</details>

**Cliff**：然而在真正动手构建这套系统、深入到该原语内部时，你会遭遇巨大的复杂性——特别是大量的偶然复杂性（Accidental Complexity）。不过，一旦你成功构建出了统一的中心化表达形式，所有下游的业务处理流程都会变得异常轻松顺畅。

<details>
<summary>Original English</summary>

**Cliff**: actually uh building the thing going inside the primitive there's a lot of complexity a lot of accidental complexity and once you get a centralized representation it makes all the downstream processes very very easy

</details>

**Cliff**：正因如此，几乎每一家资产管理机构内部都会搭建一套属于自己的证券主数据系统。

<details>
<summary>Original English</summary>

**Cliff**: and that's why almost every asset manager has one

</details>

**Cliff**：但是，要把所有这些异构数据清洗整合（Data Munching）在一起，并且每次当你遇到一种全新的资产类别、一种新的代码标识格式，或者接入一个新的上游数据供应商时……

<details>
<summary>Original English</summary>

**Cliff**: but actually munching all that data together and every time you bump into a new asset class or a new ID format a new upstream source of data

</details>

**Amole**：……你就必须在证券主数据系统内部抽象并实现一套全新的业务诉求。我的理解是，它就像是一个处于枢纽地位的运作原语：上游是纷繁庞杂的多样化数据源，下游则是形形色色依赖这些数据进行决策或核算的业务消费端。如果你不在中间层建立一个权威中枢来确保正确的数据准确无误地流向正确的目的地，那么在分布式系统架构下，你根本不可能保障数据的纯净度，无法保证监管合规报表的准确性，无法保证财务审计的合规，更无法保证资产定价模型的计算正确性。可以说，金融机构内部所有这类的下游核心系统，本质上全部重度依赖于一个干净、高质量的证券主数据平台。

<details>
<summary>Original English</summary>

**Amole**: you actually have new needs that you need to abstract inside the security master. I mean, I tend to think of it almost like an operational primitive where you just have all of this data, all these different data sources and all these different data consumers. And if you don't have something in the middle that basically ensures that the right data is getting to the right places, it's impossible to otherwise guarantee in a distributed way, that you're going to have clean data, that you're going to be able to report the right things, that your audits are correct, that your pricing models are correct, like all of that stuff essentially is downstream of having a good clean semaster.

</details>


### 证券主数据的核心地位：所有分析任务的“左连接之源”

**Cliff**：是的。因此对于你所要执行的绝大多数数据分析任务而言，证券主数据表几乎就是每一次数据库关联查询（SQL Join）中最核心的左表（Left Side of the Join）。

<details>
<summary>Original English</summary>

**Cliff**: Yeah. So the segment master for most analysis that you're going to run, it's going to be the left side of almost every join.

</details>

**Amole**：确实。

<details>
<summary>Original English</summary>

**Amole**: Yeah.

</details>

**Cliff**：它构成了绝大部分量化与财务分析任务不可动摇的数据基石与起点。

<details>
<summary>Original English</summary>

**Cliff**: It's going to be the starting point for a lot of the analysis that you do.

</details>

**Amole**：正是如此。

<details>
<summary>Original English</summary>

**Amole**: Yeah.

</details>

**Cliff**：并且，它直接驱动着任何一家资产管理公司内部体量最大、最关键的核心业务流程……

<details>
<summary>Original English</summary>

**Cliff**: And that drives some of the biggest processes at any asset manager,

</details>

**Amole**：对吧？

<details>
<summary>Original English</summary>

**Amole**: right?

</details>

**Cliff**：这里面涵盖了一切：从日常监管报送与合规披露要求，到历史投资业绩与归因回溯分析，再到全面审视与洞察你的持仓风险敞口……

<details>
<summary>Original English</summary>

**Cliff**: And that could be everything from your reporting requirements to looking at historical performance to understanding your

</details>

**Amole**：其中很多要求甚至纯粹是法定的监管红线——作为持牌受托机构，你从法律层面上必须拥有详尽可查的完整账本，确凿记录你名下到底持有了哪些资产标的。

<details>
<summary>Original English</summary>

**Amole**: some of this is just regulatory like you literally have to have some sort of a record of what assets you have.

</details>

**Cliff**：完全没错。

<details>
<summary>Original English</summary>

**Cliff**: Yeah. Exactly.

</details>


### 偶然复杂性的类比：像极了软件工程中的“时间日期库”

**Cliff**：是的。作为软件工程师，我们其实非常容易想当然，往往会忽略掉在某一层优雅的高级抽象之下所精心封装的大量偶然复杂性。

<details>
<summary>Original English</summary>

**Cliff**: Yeah. I think it's very easy as software engineers for us to jump over some of the accidental complexity that gets encapsulated within an abstraction.

</details>

**Amole**：确实如此。

<details>
<summary>Original English</summary>

**Amole**: Sure.

</details>

**Cliff**：所以，每当我们在向团队内的其他工程师或是外部客户解释这个概念时，我常常会用到一个类比——它其实就像软件开发中的“时间与日期库（Datetime Libraries）”。

<details>
<summary>Original English</summary>

**Cliff**: And so the the comparison I've been thinking about when we've explained this to other engineers on our team and talking with our customers. Uh it's like datetime libraries.

</details>

**Amole**：工程师很容易轻描淡写地觉得：“嗨，不就是一个日期时间处理库嘛。”

<details>
<summary>Original English</summary>

**Amole**: It's very it's very easy for engineers to think, oh, it's a daytime library.

</details>

**Cliff**：对啊，“记录个时间而已，能有多难？”然后你一头扎进去才猛然意识到：原来世界上有各种错综复杂的时区规则，不同地区和文化对时间的记录方式天差地别，随之而来的全是让人抓狂的深坑。

<details>
<summary>Original English</summary>

**Cliff**: Yeah. You're just tracking the time. How hard could it be? And then you realize like time zones are a thing and like people track things differently and it's all sorts of pain.

</details>

**Cliff**：是的，从本地化格式（Localization）、不同人群对同一时刻的不同字符呈现方式，再到跨越不同时区进行时间的转换与数据传递……

<details>
<summary>Original English</summary>

**Cliff**: Yeah. Everything from the localization to how people see the same representation to actually moving something between different time zones

</details>

**Amole**：……而且各个国家实行夏令时（Daylight Saving Time）的起止时间点和规则还完全不一致。

<details>
<summary>Original English</summary>

**Amole**: and uh daylight savings actually hits at different points in different countries.

</details>

**Cliff**：没错。

<details>
<summary>Original English</summary>

**Cliff**: Yeah.

</details>

**Cliff**：这仅仅是一个极为粗浅的缩影，展现了在证券主数据这一原语边界之下所隐匿掩盖的海量偶然复杂性。

<details>
<summary>Original English</summary>

**Cliff**: Uh so just like the briefest snapshot of all the accidental complexity that you hide inside the perimeter of the semaster.

</details>

**Amole**：确实。

<details>
<summary>Original English</summary>

**Amole**: Yeah.

</details>


### 具象案例剖析：即便是“最简单”的公开交易股票，也暗藏数据乱麻

**Cliff**：我想，为了让大家更容易理解这一点，最容易入门的切入点就是公开交易的股票（Publicly Traded Equities）。

<details>
<summary>Original English</summary>

**Cliff**: I think like the easiest place to start just so people grasp this is publicly traded equities.

</details>

**Amole**：是的，比如像谷歌（Google）或者苹果（Apple）的股票这类典型标的。你打开交易所终端，下单买入谷歌股票，直觉上似乎就是这么简单明了。

<details>
<summary>Original English</summary>

**Amole**: Yeah. Like a Google or an Apple stock or something like that. You go to the exchange, you buy Google, something like that.

</details>

**Cliff**：对。而且这在所有资产类别中已经是迄今为止处理难度最低的一类了。然而即便如此，你刚才随口提到的“谷歌”，就已经暴露出第一个极度棘手的特性：股票代码（Ticker）与实体公司之间，根本就不是简单的一对一对应关系。

<details>
<summary>Original English</summary>

**Cliff**: Yeah. And this is by far the easiest asset class to even handle. And already you just mentioned one of the first quirks which is Google. That's not even one to one between tickers and companies.

</details>

**Amole**：是的，所谓“买入谷歌”究竟指的是什么？你是打算购买母公司 Alphabet 的股票，还是购买挂着 Google 标签的股票？实际上光是在公开市场上流通的就有完全不同的两类股票：谷歌 A 类股（Class A，代码 GOOGL）和 C 类/B 类股（Class C，代码 GOOG）……

<details>
<summary>Original English</summary>

**Amole**: Yeah. What do you mean by Google? Like are you buying alphabet stock? Are you buying Google stock? There's actually two completely Google class A and B

</details>

**Cliff**：……而且它们在不同的证券交易所挂牌的代码不同，在不同国家和地区的交易规则与命名也各不相同。

<details>
<summary>Original English</summary>

**Cliff**: and they are different on different exchanges and they're different in different countries.

</details>

**Cliff**：因此，股票代码本身并不是全局唯一的标识，它们与真实的法律实体企业之间绝非一一对应，对吧？不仅如此，在不同的交易所之间，同一只股票还可能存在跨境多重上市的情况——比如在欧洲联盟（EU）的某个交易所里，很可能对同一家公司背后的底层股份有着完全不同的交易挂牌代码与存托形式。

<details>
<summary>Original English</summary>

**Cliff**: So tickers aren't unique. They're not onetoone with the actual entities, right? And then on different exchanges, you can actually have the same stock listed across potentially, you know, a different exchange in, you know, the EU might have actually different listings of the same underlying uh shares.

</details>

**Amole**：所以本质上，你面对的是一团错综复杂、纠缠不清的“乱麻式”数据（Rat's Nest of Data）。要把它理清解耦极其艰难，以至于传统金融机构通常必须养着一整支专业的数据团队，全职从事这项极其耗费人力与工时的苦差事，日复一日地去维护、校验并清洗这些基础数据。

<details>
<summary>Original English</summary>

**Amole**: So you got this rat's nest of data basically and it's really really hard to unentangle and you have to basically have a team of people who are doing this like pretty labor intensive role of keeping this all clean.

</details>

<!-- chunk 28/51 -->

### 公开市场证券主数据与标识符的中心化力量

**Speaker A**: 是的。因此，很大一部分工作实际上是在架构和设计证券主数据（Security Master）应该如何运作，以适应你的业务将要投资的特定领域或特定资产类别。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And so a lot of it's kind of architecting how the sec master should work for the area or particular asset classes that your business will be investing in.

</details>

**Speaker B**: 对，我认为尤其是在公开交易的市场领域，数据的大部分结构往往来自于这些数据遭遇各种中心化力量的时刻。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I think that especially in the publicly traded world, oftentimes most of the structure to the data comes from the moments where that data encounters different centralizing forces.

</details>

**Speaker A**: 确实如此。

<details>
<summary>Original English</summary>

**Speaker A**: Sure.

</details>

**Speaker B**: 其中最典型的两个例子就是监管约束以及资产实际交易的交易所，对吧？也就是所谓的销售点（point of sale）和交易所节点。

<details>
<summary>Original English</summary>

**Speaker B**: So the two biggest examples are the regulatory constraints and the actual exchanges where it's traded, right? Talking point of sale, point of exchange...

</details>

**Speaker A**: 这两方面共同发挥作用，创造了你在公开市场中最为关注的大多数标识符。

<details>
<summary>Original English</summary>

**Speaker A**: ...and those two have the effect of creating most of the identifiers that you care about in the public.

</details>

**Speaker B**: 所以，如果这些正是你感兴趣的资产类别……

<details>
<summary>Original English</summary>

**Speaker B**: So if those are the assets that you're interested in...

</details>

**Speaker A**: 你就必须确保自己掌握了这些标识符。你必须确保它们是对齐一致的，并且必须确保在公司内部的某个地方对它们进行了完整记录。因为任何时候任何人想要对这些资产进行任何操作，他们都必须把资产关联并引用回这些标识符上。

<details>
<summary>Original English</summary>

**Speaker A**: ...you have to make sure that you have those identifiers. You have to make sure they're aligned. You have to make sure you have them somewhere recorded in your company, because anytime anybody wants to do anything with those assets, they have to reference them back to those things.

</details>

**Speaker B**: 没错。刚开始的时候这可能相对简单，因为你只处理某一个特定的资产类别，面对的只是不同中心化结构的一个交叉点。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And at first it can be relatively easy because you're dealing with a particular asset class. You're dealing with one intersection of different centralizing structures.

</details>

**Speaker A**: 你完全可以说：“我就对所有东西都直接使用彭博（Bloomberg）的标识符，根本不用操心别的。”

<details>
<summary>Original English</summary>

**Speaker A**: You can just be like, "I'm just going to use Bloomberg's IDs for everything and not worry about it."

</details>

**Speaker B**: 是的。比如使用彭博的 IDBb Global，这就像是你从他们那里获取的源数据表中的一个列字段。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So you have Bloomberg's IDBb globals. It's like a column in the source data that you're going to get from them.

</details>

**Speaker A**: 这些标识符有时也被称为 FIGI，这是因为以前的一个缩写词。

<details>
<summary>Original English</summary>

**Speaker A**: And these are called FIGIs sometimes because of a previous acronym.

</details>

**Speaker B**: 它叫做 FIGI，即 F-I-G-I。

<details>
<summary>Original English</summary>

**Speaker B**: It's called Figgy. FIGI.

</details>

**Speaker A**: 没错，代表金融工具全局标识符（Financial Instrument Global Identifier）。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. It's like Financial Instrument Global Identifier.

</details>

**Speaker B**: 好的。

<details>
<summary>Original English</summary>

**Speaker B**: Okay.

</details>

**Speaker A**: 不过我不知道它后来有没有被正式重新命名。

<details>
<summary>Original English</summary>

**Speaker A**: But I don't know if it's officially renamed.

</details>

**Speaker B**: 没关系，反正叫 FIGI 确实比叫 IDB Global 更顺口一些。有了它，你很大一部分问题确实就迎刃而解了。

<details>
<summary>Original English</summary>

**Speaker B**: Sure. Yeah. Whatever. Yeah. It's a little bit easier to say than IDB global. And so that's going to answer a lot of your problems.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

### 私模资产的崛起与复杂性爆炸

**Speaker B**: 但一旦你的规模稍微变大一点，事情就会开始变得有些棘手。

<details>
<summary>Original English</summary>

**Speaker B**: But the moment you get a little bit bigger, then it starts to get a little bit messy.

</details>

**Speaker A**: 一旦复杂性有所增加，或者你处理的东西超出了彭博资产宇宙所能覆盖和理解的范围，就会变得复杂。

<details>
<summary>Original English</summary>

**Speaker A**: Once there's a little bit more complexity or you're not dealing with things that are understood in the Bloomberg universe of assets.

</details>

**Speaker B**: 实际上我认为非常有趣的一点是，过去三年里，资产管理机构在非标准化、非全球化公开实体资产上的投资出现了爆发式增长，对吧？像谷歌和苹果这样的实体，在某种意义上是非常透明且容易被理解的；但现在有那么多人正在投资数据中心、GPU 集群。如果你直接从某人手里收购一个数据中心，或者购买一个数据中心的股份，那根本不是在流动市场上进行交易的东西，因此你必须通过其他某种完全不同的方式来追踪它。

<details>
<summary>Original English</summary>

**Speaker B**: And so actually one of the things I think is really interesting is the last three years I think has seen a massive growth for asset managers in assets that are not of this sort of standardized, globalized public entities, right? Like Google and Apple in some sense are pretty well understood, but so many people are now investing in like data centers and like clusters of GPUs. And if you're just like buying a data center from somebody or buying shares of a data center, that's not something that trades on a liquid market, and so you have to track that in some other way.

</details>

**Speaker A**: 确实。虽然这不是我的专业领域，但数据中心是一个极具启发性的案例，因为它牵涉到了私下交易金融工具的多个不同领域，对吧？建造数据中心会涉及实际的房地产和土地所有权。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So I mean this is not my area of expertise, but the data centers are a very interesting one because I think it touches on multiple different areas of privately traded instruments, right? So you might have actual real estate that's involved in where do we build this data center...

</details>

**Speaker B**: 也就是实际的土地。

<details>
<summary>Original English</summary>

**Speaker B**: The actual land. Yeah.

</details>

**Speaker A**: 接下来，可能有一家发行股权的私有制公司负责运营。

<details>
<summary>Original English</summary>

**Speaker A**: And then from there there might be a privately owned company that does issue equity...

</details>

**Speaker B**: 或者它是由某家上市公司所持有的，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Maybe it's held by a publicly traded company, right?

</details>

**Speaker A**: 也许他们发行了某些公开发行的债券来为这部分项目融资，又或者他们借入了私募信贷（private credit）来支持建设工程。

<details>
<summary>Original English</summary>

**Speaker A**: Maybe there's some publicly traded bonds issued to fund some part of this, or maybe there's private credit that's taken on to fund the construction.

</details>

**Speaker B**: 而且现在越来越普遍的是，GPU 本身感觉就已经变成了一种资产类别。

<details>
<summary>Original English</summary>

**Speaker B**: I mean increasingly the GPUs itself feel like an asset class.

</details>

**Speaker A**: 没错，现在甚至确实有人在尝试对 GPU 集群进行证券化。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And there actually are efforts right now to securitize...

</details>

**Speaker B**: 对 GPU 集群进行证券化，确实如此。

<details>
<summary>Original English</summary>

**Speaker B**: GPU clusters. Yeah. Sure.

</details>

**Speaker A**: 你知道，另一个非常有趣且小众的私募资产类别其实是飞机。

<details>
<summary>Original English</summary>

**Speaker A**: Well, I mean because, you know, another private asset that's very interesting, niche, is airplanes.

</details>

**Speaker B**: 确实。

<details>
<summary>Original English</summary>

**Speaker B**: Sure.

</details>

**Speaker A**: 航空业务的进入门槛之所以相对较低，一个原因就在于飞机在抵押借贷时本身就可以作为抵押品，如果你违约……

<details>
<summary>Original English</summary>

**Speaker A**: So one reason why kind of the entry costs for the airline business are low is because it holds collateral against itself when you're...

</details>

**Speaker B**: 这很有意思，大不了直接把飞机收走。

<details>
<summary>Original English</summary>

**Speaker B**: Interesting, you could lose the plane.

</details>

### 私募资产的非同质性与线性扩展陷阱

**Speaker A**: 确实如此。这就引出了对大多数私募资产而言非常重要且有帮助的一点区别：大多数私募资产的同质化程度非常低（not very fungible）。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Well, so gets to most private assets—this is actually a helpful distinction. Most private assets are not very fungible.

</details>

**Speaker B**: 确实，这完全切中了要害。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Sure. Yeah.

</details>

**Speaker A**: 这正是我们接下来要讨论的核心问题的一个标志性特征。尽管有些私有资产表现出了奇特的同质性……

<details>
<summary>Original English</summary>

**Speaker A**: That's kind of a hallmark of the problem that we're going to come back to. There are some of these private assets that actually are weirdly fungible.

</details>

**Speaker B**: 奇特的同质化，比如飞机或者 GPU。

<details>
<summary>Original English</summary>

**Speaker B**: Weirdly fungible like airplanes or GPUs.

</details>

**Speaker A**: 是的。因此，我们或许值得深入探讨一下具体的细节。到底怎样才算是在证券主数据系统中对一项资产进行有效标识？我认为结合一个具体的实例来谈会更有帮助。比如，我们目前正在与纽约市本地的一家大型资产管理机构开展非常紧密的合作——这也是身处纽约的优势之一。让我们详细拆解一下：他们究竟遇到了哪些实际难题，他们又是如何利用智能体（Agent）来解决这些问题的？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So it might be worth even diving into then the specifics, right? What does it mean to identify a securities master? And I think it can be helpful to even ground this in a particular example which is, you know, we're working very closely with one of these big asset managers in New York City—one of the benefits of being in New York local. Let's talk through a little bit of what problems that they are running into, and then how are they using agents to solve that problem?

</details>

**Speaker B**: 好的。这很大程度上就回到了我们刚才谈到的私募资产的那个关键区别。首先，最重要的差异在于，围绕每一种资产所需处理的数据量和工作量，会随着资产数量的增加而呈线性比例上升，因为每一项私募资产都是独一无二的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So a lot of this is that last distinction we hit on for private assets. And the first important distinction here is that the amount of data and the amount of work related to each asset scales linearly with the number of assets, because they're unique.

</details>

**Speaker A**: 确实如此。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 面对每一个私募资产，你很难轻易编写一套通用的软件程序来批量处理这群资产，因为每一笔资产的情况都完全不同。

<details>
<summary>Original English</summary>

**Speaker B**: So each private asset, it's not like you can easily write software that will handle a group of these private assets, because each one is different.

</details>

**Speaker A**: 经常是这样，而且根本没有一个现成的 API 能让你直接调用并查询：“请给我这个数据中心的价格。”这个价格往往深藏在某份合同的深处。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, oftentimes, and also there's no API that you can hit to be like, "Give me the price of this data center." The price lives in a contract somewhere.

</details>

**Speaker B**: 确实。如果你身处像风险投资（VC）这样的行业中，不同资产的数量本身就已经与你投入的时间呈线性关系了。你开出的不同投资支票的数量，已经与花费在这些潜在投资标的上的工时直接挂钩。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And if you're part of a business like a VC, where the number of these different assets already scales linear to the amount of time put in. So the number of different checks that you write is already very related to the number of different person-hours spent with those potential investments.

</details>

**Speaker A**: 这极其依赖人工，全靠纯手工操作。

<details>
<summary>Original English</summary>

**Speaker A**: It's extremely manual. It's very manual and it might be...

</details>

**Speaker B**: 你可能会觉得这在某种程度上还能应付，因为源数据量与人工投入的工时成正比，下游环节的工作量也与工时成正比。但一旦你的视野拓展到从房地产到私募信贷的广泛领域，以及这些资产被打包组合的各种复杂方式……

<details>
<summary>Original English</summary>

**Speaker B**: ...you know, that might be scalable because the source data is proportional to the person-hours, and then the downstream effects then cost proportional person-hours. But then once you start looking at everything from real estate to private credit and the different ways that these assets can be packaged...

</details>

**Speaker A**: 这就会演变成一种全新的数据膨胀模式，导致整个数据规模呈爆炸式增长。

<details>
<summary>Original English</summary>

**Speaker A**: ...that ends up being its own whole new way that the scale of the data increases.

</details>

### 数据溯源困境：从每个单元格到技术栈鸿沟

**Speaker B**: 没错，你会面临这种指数级增长的复杂性。那么这种复杂性会带来怎样的实际冲击呢？让我们深入拆解这个具体的业务场景。我们合作的这家资产管理公司，他们正在尝试做些什么，智能体又在其中扮演了什么角色？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So you have this exponentially increasing complexity. How does that then impact... let's dive into this kind of specific use case. So we're working with this asset manager, like what are the things that they are trying to do, and then where do agents come in?

</details>

**Speaker A**: 他们当前正在推进的一个流程是建立一套全新的证券主数据系统。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So they're already seeing a process where they've created a new SECM master.

</details>

**Speaker B**: 明白。

<details>
<summary>Original English</summary>

**Speaker B**: Yep.

</details>

**Speaker A**: 他们同时接入了内部和外部的数据源。

<details>
<summary>Original English</summary>

**Speaker A**: And they have both internal and external sources.

</details>

**Speaker B**: 很多数据源是量化的结构化数据，但也有相当一部分实际上来源于各种文档和其他非结构化数据源。他们搭建了数据管道来对这些数据进行映射整理。在系统推行落地过程中，最基础、门槛最低的一个刚性要求，就是必须能够准确地将表中的每一处变更追溯回上游的具体证据支持。

<details>
<summary>Original English</summary>

**Speaker B**: Yep. Many of these are quantitative, but some of them are actually related to different documents and other unstructured sources of data. And they have data pipelines that are mapping that. And just the lowest barrier for adoption is accurately being able to tie out individual changes to upstream pieces of evidence.

</details>

**Speaker A**: 仅仅对于几百列或者几百行——甚至列数更少的一张表格——这已经是一个劳动密集程度极高的核对过程了，而他们实际管理的资产数量远远不止区区几百项。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And that just for a couple hundred columns or a couple hundred rows with even fewer than that columns is already a very labor-intensive process, and they manage a lot more than a couple hundred assets.

</details>

**Speaker B**: 没错。用通俗的语言来描述这个场景：只要这张表中的某一行发生变化，就必须有人专门负责排查并解释清楚为什么会发生这个变化，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, just to give a layman's view of this, right? Anytime one of these rows in this table changes, there's somebody who gets called up who basically has to then go and figure out why that change happened, right?

</details>

**Speaker A**: 是的。换句话说，就是要能够查看表格中的任意一个单元格，并完整调出生成该数值的全部数据血缘（lineage）。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So basically being able to look at any cell in the table and look at the lineage for what produced that.

</details>

**Speaker B**: 不仅是每一行，而是精准到每一个单元格。

<details>
<summary>Original English</summary>

**Speaker B**: Not every row, it's every cell.

</details>

**Speaker A**: 每一个单元格，每一个行与列的交叉点。

<details>
<summary>Original English</summary>

**Speaker A**: Every cell. Yeah. So every row/column.

</details>

**Speaker B**: 所以这极其耗费人力。表格中任何一行、任何一列的内容一旦变动，就必须有人去找到该数据的原始出处与证据链（provenance）。更重要的是，软件与金融业务之间的鸿沟带来了极其棘手的挑战，这一点怎么强调都不为过。因为具体负责这项排查工作的人，往往不可能既精通金融业务，又能完全弄明白整套 Python 数据清洗逻辑和数据流向——从运行在 Snowflake 上的交互式 Notebook，一直到自建的湖仓一体（lakehouse）架构以及其上运行的 Apache Spark 任务。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And so it's extremely labor-intensive. Like anytime anything changes for any of these columns and rows, there's a person who basically has to go and find the provenance for that data. And I can't undersell the trickiness raised by the intersection of both software and finance here, because that person is not going to both be able to perfectly understand all the Python data munching and data flows—whether that's some notebooks that run in Snowflake all the way down to the "build your own, we have our own lakehouse and we're running our own Apache Spark jobs," right?

</details>

**Speaker A**: 如果他们是金融业务领域的专家，比如在后台管理中承担了大量运营工作的人，通常并不具备专业的软件工程背景。不过，其中许多人其实非常精通如何借助 Python 来解决实际问题……

<details>
<summary>Original English</summary>

**Speaker A**: You know, if they are a finance expert, someone who's conducted a lot of operational work in back office managers don't have software engineering... A lot of those people are really savvy actually with how they can use Python to solve problems on...

</details>

<!-- chunk 29/51 -->

### 电子表格与软件的对立视角：数据与逻辑的割裂

**Speaker A**：……在他们的机器上。是的。

<details>
<summary>Original English</summary>

**Speaker A**: ...their machine. Yeah.

</details>

**Speaker B**：带着各种不同的 CSV 文件、对账表（tie-outs）或者从 Excel 导出的表格，但如果能够直接查看代码仓库并理解……

<details>
<summary>Original English</summary>

**Speaker B**: With different CSVs or tie outs or exports from Excel, but being able to look at the repo and understand,

</details>

**Speaker A**：你知道，这很有意思。电子表格和软件在某种程度上是同一事物的相反视角。在电子表格中，你能直观看到数据，却看不到背后的计算逻辑；而在软件中——比如所有的这些数据管道（data pipelines）——你能清晰看到处理流程和代码逻辑，却看不到具体流淌的数据。

<details>
<summary>Original English</summary>

**Speaker A**: You know, it's interesting like spreadsheets and software are kind of opposite views of the same where it's like with a spreadsheet you see the data and you don't see the logic. And then with a software, you know all these data pipelines, you see the process and the logic but you don't see the data. Yeah.

</details>

**Speaker B**：对，它们是完全不同的表征方式。从另一面来看，实现这些数据管道的软件工程师，根本不知道某个特定单元格里出现错误的数据会是什么样子。而这恰恰会给投资专业人士带来巨大困扰，因为投资人必须查看这些数据，并依赖其准确性来做决策。

<details>
<summary>Original English</summary>

**Speaker B**: And so there's completely different representations. And on the flip side of it, you have the software engineer who has implemented the data pipelines and they don't know what it looks like for something to be incorrect in this particular cell. That's now causing problems for an investment professional who needs to look at that data and have it be correct.

</details>

### 私有数据的核验困境与智能体契机

**Speaker A**：没错，确实如此。所以现在的实际流程是：任何时候只要某个单元格的数据发生变动——特别是涉及私有资产数据时——你甚至根本无法通过调用 API 来获取验证。现实中真的就是有专人去翻 Google Drive，或者翻找别人的往来邮件，试图找出一份合同的 PDF 扫描件，只为了核对确认该单元格的数据是否准确。

<details>
<summary>Original English</summary>

**Speaker A**: Right. Right. So, so you have this process that right now anytime a cell changes and for private data, you know, it's not even like you can go hit an API. You literally have a guy going through a Google Drive or going through somebody's emails to find a PDF of a contract to make sure that the data is correct.

</details>

**Speaker B**：是的。他们得去确认：这是不是最新版本？这是不是经过公证的最终版合同，而不是往返邮件中沟通的某个草稿？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Is this the most up-to-date version? Is this the latest notarized version of the contract and not some draft that was sent back and forth?

</details>

**Speaker A**：我真正需要的信息是否就在这里，或者后续还有没有更新的补充协议？

<details>
<summary>Original English</summary>

**Speaker A**: Um, is the actual information I need here or is there a more recent update?

</details>

**Speaker B**：嗯，对。

<details>
<summary>Original English</summary>

**Speaker B**: Um, right.

</details>

**Speaker A**：所以从这些维度来看，显而易见，云端智能体（cloud agents）理应能够解决这个问题。

<details>
<summary>Original English</summary>

**Speaker A**: And so I just feel like in those terms, right, it's just so obvious that cloud agents would solve this problem.

</details>

**Speaker B**：是的，或者说至少能够改善（ameliorate）这个问题。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Yeah. Or maybe, you know, ameliorate the problem.

</details>

**Speaker A**：对，“彻底解决”这个词要求太高了。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Solve is a tough word.

</details>

### 深入剖析：为什么业务规则与知识编码如此困难？

**Speaker B**：这正好引出了我认为全流程中最耐人寻味的核心问题：为什么这件事情如此困难？作为软件工程师和专业技术人员，我们每天都能看到智能体在解决软件领域的偶然复杂性（accidental complexity）。那么深入探究一下非常有必要：从技术视角和业务视角来看，这到底难在哪里？

<details>
<summary>Original English</summary>

**Speaker B**: This kind of gets to I think the most interesting part of the problem which is why is this hard? Yeah. We as software engineers, as software professionals, we see agents solving accidental complexity every single day. Yes. So I think it's helpful to just deep dive. Why is this hard? Both from a technical perspective and a business perspective.

</details>

**Speaker A**：确实。回到你刚才提到的“需要专人去核实查找”这一点：能够判断什么是优秀的、什么是正确的，这本质上更多是一个业务问题。当然，它同时也是一个检索与搜索问题——你什么时候才算掌握了足够的信息？什么时候才算收集齐了所有证据链？这一点在客观上是极难证实的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And to your point about there's someone who needs to go look for this, right? Being able to know what good looks like, what correct looks like. That's more of a business question. Sure. Or, you know, it can also be a search problem where, you know, when have you seen enough? When do you have all of the evidence? Um, it's tough to prove.

</details>

**Speaker B**：对于不同的公司、不同的业务场景，甚至不同的具体底层资产，标准都是截然不同的。

<details>
<summary>Original English</summary>

**Speaker B**: It's going to be different for different companies and different situations. Yeah. For different assets even.

</details>

**Speaker A**：完全正确。这也是为什么当前这个具体案例、这个具体项目非常契合的原因之一——因为他们此前已经对业务工作流进行了非常深入透彻的思考：核对并调和数据的不一致或任何变动到底涉及哪些具体步骤？他们希望中后台职能团队一步一步去审查什么？在什么节点、什么条件下，才需要将发现的数据异常升级上报给数据负责人或财务主管？

<details>
<summary>Original English</summary>

**Speaker A**: Exactly. And um yeah, I mean, one of the reasons why this particular instance, this particular project is a good fit is because they've already actually thought very hard about what does that workflow look like? What does it look like to reconcile inconsistencies or any changes with the data? What would they want that back office function to actually look at step by step and when would they want them to escalate an inconsistency they're seeing up to a data owner or to a financial...

</details>

**Speaker B**：证券主数据（Sec Masters）系统通常已经建立了类似的既定流程。比如某处出现了错误，他们立刻就能明确：好的，这个单元格里有错误，我们清楚谁是负责该单元格的数据责任人。

<details>
<summary>Original English</summary>

**Speaker B**: Sec masters already have this sort of process in place, like if there's an error somewhere they already know okay there's an error in this cell we know who is going to be owner of that cell.

</details>

**Speaker A**：对，原因可能千差万别：可能某位投资专家的投资组合或资产直接与这个特定数值挂钩；也有可能是“只要这个特定数据源看起来不对劲，我们就得去找 Jerry 问清楚”。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, it could be everything from there is an investment professional whose, you know, book or whose investments are related to, right, this particular number. It could be actually, you know, when when this particular data source doesn't look correct we talk to Jerry.

</details>

**Speaker B**：确实。

<details>
<summary>Original English</summary>

**Speaker B**: Sure.

</details>

**Speaker A**：因为 Jerry 是当初负责与对方沟通、接收他们传过来的初始数据切片的人。

<details>
<summary>Original English</summary>

**Speaker A**: Because he was the one who talked to them on the initial extracts of data that they sent over.

</details>

**Speaker B**：对。我认为这就是为什么这件事如此困难的第一大难题。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, so this I think is like the first of the problems of why this is hard.

</details>

**Speaker A**：是的。大量关键业务知识既没有被编码进软件程序，也没有被写进电子表格，许多任务背后的根本意图也从未被显式记录下来。在企业内部，具体的“执行任务”可能已经高度流程化、被广泛记录，但这些任务背后的“核心意图与业务逻辑”却往往是一片空白，它们完全散落并留存在承担各项职能的具体员工脑海中。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. There's knowledge that's not encoded in either the code or the spreadsheets or kind of a lot of the purpose behind the tasks. The tasks are very encoded at your company, but the purpose behind those tasks is often not. And that lives with all of the people who are making up those different functions.

</details>

### 人机协同交互与“软件工厂”陷阱

**Speaker B**：正是如此。这也引出了导致其困难的第二个核心层面：为了真正有效地协助这些业务人员，你必须构建辅助性技术（assistive technologies）。我认为这是过去一年里我们看到的极其普遍的失败模式，尤其是在软件行业领域。市场上太多人一心想要让 AI 智能体实现 100% 的全自动闭环。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Which I think also gets to the second part of why this is difficult. In order to properly assist them, you need to make assistive technologies. And I think this is a common failure pattern we've seen, especially on the software side of the market for the past year. There's so many people who like want the agents to take everything to 100%.

</details>

**Speaker A**：是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**：于是他们搭建出所谓的“软件工厂”（software factories），但这些系统极其僵化。他们搞出来的一套流水线往往是这样的：“噢，我给这个智能体打上标签，让它在 EC2 实例中跑起来”，却压根没有去思考：如果你需要人工介入该怎么办？如果你需要智能体在运行中临时转去处理别的事怎么办？如果你需要与其交互反馈又该怎么办？系统必须具备极其丰富灵活的人机交互模式。如果你一开始的思路就是“我要让这套东西全自主运行，试图一口气做到 100%”，那你注定会遭遇失败。因为现实业务有着极其深厚的上下文，必须有人类参与——哪怕仅仅是为了权责落实（accountability），很多时候你也依然需要一个人来最后点击那个合并（merge）按钮。

<details>
<summary>Original English</summary>

**Speaker B**: And so they create these software factories software factories quote unquote that are really inflexible. You know, they spin up some process where it's like, oh, I tag this agent and it'll like run in EC2 and then there's no thought put into well what if you need to intervene? What if you need the agent to be able to do something else? What if you need to respond? There's got to be this like very rich human interaction pattern. And if your thought process is, I'm just gonna have this thing run autonomously and try and do the whole thing to 100%. Well, you're gonna fail because there's actually like so much depth that like a human needs to even if it's just accountability, sometimes you need a human just to be able to hit the merge button.

</details>

**Speaker A**：确实是这样。大家执着于追求全自动目标是挺讽刺的，因为智能体最大的优势之一恰恰在于其延展性（malleability），以及人类在任务执行过程中随时纠正它们的能力。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Yeah. And it's kind of funny that people are shooting for that particular target when that's one of the biggest benefits of agents is their malleability and the ability to correct them. I mean I think mid task.

</details>

**Speaker B**：很大一部分原因在于大家对云端智能体的认知。很多人觉得：“云端智能体不就是提供一个 API 端点，然后我们在后台触发一个离线任务吗？”但真正的云端智能体基础设施，关键在于体验的无缝融合。无论是直接在云端与它交互，还是感觉它就像在你本地电脑、手机上运行，亦或是通过语音电话实时对话，整个交互体验必须极其丝滑顺畅。

<details>
<summary>Original English</summary>

**Speaker B**: I think a big part of it is and this is kind of the thing about cloud agents. I think a lot of people think oh a cloud agent is just something that we can just have an endpoint and then kick off a task but actually the real cloud agent infrastructure is when it feels seamless. It feels so seamless to be able to talk to it in the cloud as if it was running on your computer or on your phone or you were just talking to it, you know, over a voice call.

</details>

**Speaker A**：没错。而这种产品深度和工程细节正是大多数团队不愿涉足的，因为要把这种无缝体验搭建好极其困难。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And that's the level of depth and product area that most people just don't want to do because it's hard it's hard to build that.

</details>

**Speaker B**：是的，我认为从技术实现层面来说，这就是第二大难点所在。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I think that's the second part that's difficult which is you know from the technical side.

</details>

### 黑石集团与 Norm AI：企业级智能体落地实践

**Scott Worland**：好的，我们现在正式开始。我是 Scott Worland，Norm AI 的首席技术官（CTO）。今天非常荣幸能与黑石集团（Blackstone）的 CTO John Stecher 同台交流。据我所知，John 基本上同时承担着三份全职工作：你负责掌舵黑石集团的所有技术工作；为黑石的各项投资业务提供技术咨询；同时还要作为技术资源中心，为黑石旗下所有的被投组合企业（portfolio companies）提供全方位的技术赋能。我有遗漏什么吗？

<details>
<summary>Original English</summary>

**Scott Worland**: All right, we're going to go and get started. Um I'm Scott Worland. I'm the CTO of Norm AI and I'm privileged enough to be sharing the stage here with John Stecher who's the CTO of Blackstone. Um, from what I understand, John has basically three full-time jobs. It sounds like you've responsible for all of the technology at Blackstone. Also advises on their investments um and as as well as serves as a resource for the portfolio companies for all things technology. Did I miss anything?

</details>

**John Stecher**：总结得非常到位，兄弟，一点没落。

<details>
<summary>Original English</summary>

**John Stecher**: Hit it all perfectly, man.

</details>

**Scott Worland**：很酷的工作。

<details>
<summary>Original English</summary>

**Scott Worland**: Cool job.

</details>

**Scott Worland**：是的。如果你还不熟悉黑石集团是做什么的，那你大概是走错会场了，所以我就不再赘述黑石的背景。但大家可能对 Norm AI 还不太了解。简单介绍一下：Norm 是一家专注于法律与合规监管（legal and regulatory）领域的 AI 公司。我们打造的企业级 AI 平台已经部署在全球多家规模最大的顶级金融机构中；同时我们还拥有一家关联律师事务所 Norm Law，我们的 AI 平台同样为其提供底层技术支持。自去年底以来，尤其是今年一整年，所有企业都在争先恐后地探索如何落地部署 AI 智能体。我非常想听听黑石集团在这方面的战略思考，以及你们是如何确保在这条赛道上走得稳、做得对的。

<details>
<summary>Original English</summary>

**Scott Worland**: Yeah. Yeah. And if you're not familiar with what Blackstone does, then you probably have wandered into the wrong conference. Um, so I'm not going to go into that, but you may not know what Norm does. So, really briefly, uh, NORM is an AI company and we operate in the legal and regulatory space. We have an enterprise AI platform that's deployed in some of the largest financial uh, institutions in the world. And then we also have an affiliated law firm, Norm Law, and our AI platform also supports that. Um, so since the end of last year and certainly all of this year, everyone's been racing to figure out how to deploy AI agents. And I'd love to hear how you're thinking about this at Blackstone and how you're trying to make sure you get this right.

</details>

**John Stecher**：好的。我认为这场竞逐确实已经全面打响，因为自去年二三月份以来，底层技术获得了飞跃式的巨大进步——单纯就上下文窗口（context windows）以及支持更长运行时间的能力而言，就已经让人们能够创造出显著提升的实际价值。而在我们黑石内部高度聚焦、同时也是我一直向所有被投企业建议并协助他们牢记的核心首要前提是：如果你想让 AI 智能体全面取得成功，你必须首先理顺你的数据战略（data story）。现在很多公司全面押注 AI，迫切想要构建尽可能多的智能体、急于从中挖掘价值，而我在他们身上看到的最大阻碍和最致命的绊脚石，就是缺乏一个统一完备的数据策略——也就是如何把数据从底层的事务型系统（transactional systems）中抽取出来，沉淀为能够被智能体高效访问、轻松管理和顺畅调用的统一体系……

<details>
<summary>Original English</summary>

**John Stecher**: Yeah, I mean I think the the race has definitely been on as like the technology has improved mightily uh since, you know, really like February, March of last year, like just in terms of context windows, being able to run stuff for significantly longer amounts of time have like resulted in people being able to produce just more value. And one of the things that like we've been focused on a lot and I think every company in our portfolio I advise on and work with all the time that they need to have top of mind for like being successful with AI agents in general is you have to get your data story right. And so like one of the biggest things impediments and tripping points that I see for companies out there when they want they're all in on AI. They want to build as many agents as possible. They really want to kind of extract value. if they don't have a cohesive data strategy that's moving stuff out of transactional systems into something that can be accessed and easily managed and recalled from like an

</details>

<!-- chunk 30/51 -->

### 直通式处理与工程落地：将数据转化为 AI 能力

**Speaker A**：……从 Agent 的视角来看，它注定会失败。因此，这正是我们一直以来最为关注的核心问题之一。作为一个大型资产管理机构，我们拥有海量的数据——专有数据、公开数据，它们错综复杂地交织在一起。我们必须把这些数据从现有系统中提取出来，转化为从 AI 视角来看能够真正加以利用的资产。

<details>
<summary>Original English</summary>

**Speaker A**: ...agent perspective, it is going to fail. And so that's been one of the biggest things that we've been focused on. As a big asset manager, we have a ton of data, proprietary data, public data, all woven together. We have to move that out of systems into something that we can really leverage from an AI perspective.

</details>

**Speaker A**：我认为第二点虽然与 AI 本身并没有直接关系，但你却可以借助 AI 来探索出实现它的最优路径，那就是：直通式处理（Straight-Through Processing, STP）依然至关重要。我常常感到惊讶，大家总是在大谈特谈 Agent，仿佛它是世界上最重大的变革力量。而我自己通过使用 Factory 以及其他几种方式在公司内部构建代码时的切身体会是：花时间让 Agent 协助我构思方案，理解人们正在执行的实际业务工作流，然后确保我真正编写出的代码是针对直通式处理进行优化的；接着，在以往各种业务环节中原本由人类做决策的关键节点上，按需借助 Agent 注入智能。这就是我每天投入大量时间深入思考的两大关键要素。

<details>
<summary>Original English</summary>

**Speaker A**: I think the second thing that has nothing to do with AI, but you can leverage AI to actually figure out how to do the best possible way, is straight-through processing still matters. I'm always shocked at how everybody just talks about agents as being the biggest differentiator in the world. The thing that I've leveraged myself using Factory and a couple other ways to go off and build code inside of the firm is taking time having agents help to craft something for me, understand the workflows out there that people are doing, and then make sure that I'm actually writing code to optimize for straight-through processing and then using agents to inject in intelligence where necessary where humans were making decisions in the past for a variety of work things. So that's really like the two key elements that I spend a ton of time thinking about every single day.

</details>

**Speaker A**：从 Agent 的角度来看，最核心的事情其实是退后一步审视：我们究竟希望构建 Agent 来更好地完成哪些工作，从而把我们的投资专家、财务专家和工程师的脑力精力释放出来，让他们能够从事更高价值的工作？当你审视整个软件开发生命周期（SDLC）时，就会发现其中有大量繁重琐碎的工作：编写测试用例、功能测试用例、性能测试用例、底层应用依赖库的版本升级——这些简直是每个工程师的噩梦。在我从事这项工作的 27 年里，我对这些深恶痛绝。而现在能让 Agent 替我去完成这些任务，帮我重构和翻新源代码，这给我们的交付速度带来了天翻地覆的变化。那么，你们在 Norm 是如何思考这个问题的？

<details>
<summary>Original English</summary>

**Speaker A**: And then the biggest thing from an agent perspective is really stepping back and looking at like what is work that we want to build agents to do better to offload intellectual cycles from our investment professionals, our finance professionals, our engineers, such that they can do higher value work. And there's a ton of stuff when you think about the software development life cycle: writing test cases, functional test cases, performance test cases, versioning forward libraries underneath applications—it's the bane of every engineer's existence. I've hated it for 27 years that I've been doing this. Having an agent be able to go off and do these things for me and renovate my code and my source code has made all the difference in the world for the velocity that we deliver at. So, how are you thinking about it at Norm?

</details>

### Norm 的脚手架困境与重构契机

**Scott**：好的。Norm 成立于 2023 年。那时候大概是 GPT-1 推出三四年之后，但距离思维链（Chain of Thought）出现还有大约一年时间。所以在技术发展进程中，那是一个非常微妙而有趣的时期。我记得我们团队第一次聚会是在斯坦福大学校园里呆了一周。可能我对确切的时间线记忆有些偏差，但当时给人的感觉就像是上下文窗口一下子从 4K 跃升到了 8K，再到 128K，随后多模态技术也接踵而至，所有进展仿佛在一瞬间全部爆发出来。接着有一段时间，前沿模型技术的发展步伐稍微放缓了一些。

<details>
<summary>Original English</summary>

**Scott**: Yeah. So Norm was founded in 2023. So, you know, that's three or I guess four years after GPT-1, but still a year before there was, you know, chain of thought. So, it was an interesting time in terms of development. I remember when we had our first team get together. We were at Stanford's campus for a week and I mean I'm probably misremembering the exact timeline, but it felt like we went from 4K to 8K to 128K context windows, and then we had multimodal, and everything just felt like it was kind of coming all at once, and then there was a bit of a time where things did slow down when it was coming from the frontier.

</details>

**Scott**：因此，我认为就像很多在 2024 年初探索的企业一样，当时我们正尝试将这些模型部署到我们的工作流和生产软件体系中。结果我们给整个系统添加了大量的结构化设计。这种繁杂的结构贯穿了技术栈的各个层面：比如为了把特定内容精准喂给模型作为上下文，我们设计了一整套非常严苛的方法；又比如为了串联模型调用的次序，我们在一致性校验和最终把结果提炼成有用输出方面设置了重重步骤。到头来，整个系统实际上演变成了一个类似于大规模 MapReduce 的架构。我们为这些 Agent 搭建了极其庞大的支撑脚手架，甚至可以说，对这些模型的具体运行机制做了极其细致刻板的约束。它在本质上更像是一套固化的工作流。这种做法确实让我们获得了非常高质量、准确度极高，同时也极为一致的输出结果，而这种一致性对于我们在合规监管领域的业务而言至关重要。

<details>
<summary>Original English</summary>

**Scott**: And so I think like a lot of companies in early 2024, you know, we were trying to deploy these models as part of our workflow and as part of our production software. And so we ended up adding a lot of structure to the system. And this comes from, you know, all different parts of the stack. So whether that was from like how we went and took the content that we knew needed to be eventually added to context to the models and we had very specific ways in which we did that, or if there was just the sequencing of the models if there was steps we needed to do in terms of looking for consistency and then ultimately distilling everything down into some useful output. We ended up with something that looked like a large MapReduce problem effectively, right? Whereas we had a lot of scaffolding for the agents, and we were very particular about how these—well, I say it's agents, really just how these models ran. It was much more like a workflow. And what this allowed us to do was get really high quality and also very accurate, but also just very consistent, which is very important for us in the regulatory space, outputs.

</details>

**Scott**：但在做这套系统的过程中，机缘巧合发生了一件极为幸运的事：因为当时我们急需某种手段对这个庞大复杂的系统进行回归测试，所以最终积累沉淀出了一个规模极其庞大的评测数据集——其中包含了由专家人工标注的数万个评估样本。正因如此，当技术演进让我们明确意识到真正的 Agent 时代已经来临时——这里我所说的 Agent，简单来说就是：给大语言模型一个系统或者一套可调用的工具，给它一个目标，并给它一套针对该目标的自我验证方式，允许它自主探索以最优路径去达成这一目标——我们便能够直接拿这套基准测试集，立刻跑在这些更具自主性的 Agent 方案上。

<details>
<summary>Original English</summary>

**Scott**: But then one fortuitous thing as part of doing this, because we wanted to have some way to regression test this big system, we ended up with a really large set of evaluation samples. We had tens of thousands actually of like hand-labeled examples by experts. And so as soon as we moved to a place where it was clear that agents were actually a thing—and by agents I simply mean, given like an LLM a system or given a set of tools that it can use, give it some goal and give it some way to verify itself against that goal, allowing it just to go figure out how to do the thing in the best way possible—we were able to just take this benchmark set and just immediately run on top of it with some of these more agentic approaches.

</details>

**Scott**：随后我们看到了结果。我想很多人都经历过那样一个瞬间：当你凝视着团队精心编写的几十万行工程代码时，突然意识到它们中的绝大部分其实已经彻底过时了，甚至反而成为了真正的阻碍。为了迅速跟上技术步伐，我带着工程管理团队租了一辆奔驰 Sprinter 面包车，一路开到了纽约上州。那正好是一场大暴雪之后，我们在一家 Airbnb 民宿里闭关，抛开一切顾虑说：“先暂时把现在的 Norm 放在一边。假设我们从零开始，结合我们当下的认知，今天我们究竟应该打造一个怎样的平台？”在那次闭关后，我们梳理出了一整套技术规范，明确了这个新平台必须具备的两项核心能力：第一，为我们的客户提供真正的 Agent 化体验；第二，它必须能够顺畅接纳 AI 作为并肩协作的共同开发者，融入我们自身的研发团队之中。从那之后，我们便一直在沿着这套规范持续推进执行。我想这就是……你是有个问题想问吗？

<details>
<summary>Original English</summary>

**Scott**: And we saw, you know, I think a lot of people had this moment where you're staring at hundreds of thousands of lines of code your team had really thoughtfully written and realizing most of it was pretty obsolete and was just kind of actually in the way. And so to update quickly on this, what we did was we took—I got the engineering leadership team. We actually rented a Sprinter van and we drove to upstate New York. It was actually after a big snowstorm. We had an Airbnb and it was like, forget Norm for a minute. Let's just say what would we build today as far as a platform knowing what we know right now, if we were going to be starting over? And then from that we left with basically a set of specs about like what this platform needed to be able to do to enable two things: one, deliver agentic experiences to our clients; and then also, it needed to be amenable to having AI as like co-developers alongside of our own development team. And that's what we've been executing against ever since then. So I think that's—Did you have a question?

</details>

### 金融级评测体系与模型漂移挑战

**Speaker A**：噢，我想说的是，Scott，你刚才提到了一个极为关键的核心要点，那就是你前面谈到的评测（Eval）体系。如果你身处金融服务领域，Agent 所必须达到的输出质量门槛是非常非常严苛的。因此，我认为必须极其严谨地去审视：你的评测集到底由什么构成？你该如何利用它来全方位测试你的 Agent，确保它们所执行的任何工作所给出的输出都是合乎逻辑、高度一致且可重复复现的。我在各个业务线上都亲眼目睹过，一旦底层模型版本发生更迭，你就会得到截然不同的回答，返回信息的准确性也会发生偏移。因此，拥有健全的高质量评测基准，能够持续稳定地运行它们并精准度量整个系统的健康度，是决定成败的重中之重。同样地，如果底层的运行测试框架（Harness）发生变动，输出结果也会不同；底层数据发生变动，输出结果同样会发生变化。所以对于涉足金融服务行业的人来说，对准确性的责任要求是处于最高层级的，而如何持续稳定地达标，正是我们每时每刻都在深思的问题。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, I was going to say I think you hit on like a key point, Scott, which says like the eval side of the fence that you were talking about before. If you're working in financial services, like the quality bar for what agents have to deliver on is very very high. And so I think really thinking through like what is your eval set for how you basically test your agents, what they're actually, you know, whatever work they're performing that the output makes sense and it's consistent and repeatable. And I've seen across the board as model versions change underneath the covers, you get different answers. You get skew in terms of the accuracy of information that comes back. So having good eval so that you can run those consistently and really measure the health of a system is paramount to success. Same thing happens if harnesses change that you're running stuff on top of, you'll get different answers. Data changes, different answers. So it's something where I think if you're trafficking in financial services, like the duty to be accurate is like up here, and hitting that is like something like we think about all the time.

</details>

### “苦涩的教训”与算力扩张的必然规律

**Scott**：确实如此。我认为这很自然地引出了我们之前一直在探讨的那个概念——“苦涩的教训”（The Bitter Lesson）。大家对这个理论都很熟悉：它指出，由绝顶聪明的人苦思冥想、精心手工打造的系统，往往最终都会被那些能够随着算力规模扩展的系统彻底超越和取代。虽然里奇·萨顿（Rich Sutton）是在 2019 年正式系统阐述了这一观点，但实际上自神经网络诞生之初起，这一规律就已经显现了。如果你回溯到 20 世纪 50 和 60 年代弗兰克·罗森布拉特（Frank Rosenblatt）发明感知机的时候，《纽约时报》还是哪家媒体就曾刊登过一篇文章，声称那是世界上第一台能够产生自主原创思想的机器。

<details>
<summary>Original English</summary>

**Scott**: Definitely. I think this leads nicely into this concept that we've been talking about just like with the bitter lesson. So like everyone's familiar with it, and you know there's this idea that these handcrafted systems built by, you know, clever people thinking hard about the problem will oftentimes eventually be dominated by systems that scale with compute, right? And that this is actually—I think Rich Sutton originally talked about this in 2019, but this has been since the beginning of neural networks. If you go back to like the '50s and '60s like with Rosenblatt's little perceptron, I think The New York Times ran an article or somebody did saying it was the first machine that could ever have its own original thoughts, you know.

</details>

**Scott**：在这段发展脉络中，其实有一段非常引人入胜的漫长历史，记录了专家系统学派与联结主义学派之间的交锋博弈，以及随之发生的一切。这其中相当一部分争论在英国甚至引发了极为激烈的辩论与审查，导致当时大量的 AI 研究工作被迫中断拆解。但极具戏剧性的是，即便回溯到 20 世纪 80 年代，IBM 机器翻译实验室的一位负责人就曾给出过一句精准契合“苦涩的教训”的著名断言：“每次我解雇一名语言学家，我们的模型性能就会提升。”也就是说，费尽心思让语言学家坐在一起试图归纳出语言的所有规则，根本比不上单纯基于概率统计去训练一个统计模型来得有效。而当我们把时间快进到今天……

<details>
<summary>Original English</summary>

**Scott**: And there was actually quite a fascinating history here of how the, you know, expert systems and the connectionist and what ended up happening there. A lot of it actually was highly litigated in England and a lot of AI research was dismantled. But one funny thing if you go back to the '80s even, there was a lead at IBM's translation lab and he made a comment which is very much the bitter lesson: "Every time I fire a linguist, my models improve." Right? Knowing the point of having these like linguists in there and trying to think about all the rules of language versus like training a statistical model based off just probabilities. And so we speed up to today...

</details>

<!-- chunk 31/51 -->

### 黑石集团的 AI 路线图考量与 ROI 权衡

**Host**: 这种情况我们其实一直都能看到。关于这一点，我们之前已经探讨了很多方面。我很好奇，当你思考你们团队的路线图时，或者当团队成员向你提出各种项目构想时，在为黑石集团（Blackstone）做规划的背景下，你是如何在脑海中权衡这一点的？

<details>
<summary>Original English</summary>

**Host**: And like we see this all the time. We've been touching on lots of points about this and I'm curious when you think about your roadmaps, when people on your team are bringing you project ideas, like how do you keep this in mind as you're thinking about this for Blackstone?

</details>

**Guest**: 是的，我的意思是，我们做的很多事情本质上都是这样。你可以把它看作一个很简单的等式：只要给予足够的算力，任何问题在未来的某个时间点，都可以通过硬件和软件来解决。埃隆·马斯克（Elon Musk）在能源等方面也经常谈到这一点。所以，摆在我们面前的是一张庞大的宏观版图，包含着海量的事物。

那么，你该如何将它拉回现实呢？从我个人的岗位职责来看，我把大量时间花在与团队中的工程师、产品经理、我们的 SRE（站点可靠性工程）团队，以及各类业务利益相关者（stakeholders）的沟通协作上，真正努力去界定清楚：大家要求我推进的工作，其真实的投资回报率（ROI）到底是什么？

<details>
<summary>Original English</summary>

**Guest**: Yeah, I mean a lot of what we do is like, you know, the simple equation is giving enough compute every problem is solvable by like hardware and software at some point in time in the future. Elon talks about this energy-wise, etc. So it's like it's a big map, it's a whole bunch of stuff.

How do you bring it back to reality? Like what I spend a lot of my time doing from like my seat working with engineers on my team, with product people, with our SRE function, with like stakeholders is really trying to define like, you know, what is the ROI of what I'm being asked to work on.

</details>

**Guest**: 因此，当我考虑构建智能体（agents）时，我想到的可能是如何将数据归集到正确的位置；我也会考虑构建各种数据看板、交易平台，或者其他任何系统。核心在于，如果我审视某个团队向我提出的实际需求，看它究竟能创造多少投资回报率，然后再去评估今天构建该系统的真实成本是多少，我该如何平衡这两端？

在此基础上，我会做出这样的决策：这是否属于那种情况——底层的 AI 模型会在六个月内变得足够优秀，届时我也会拥有远比现在充裕的算力，以至于今天花费大力气去攻关这个问题其实并不划算，反而更适合暂时搁置，等待后续用更先进的新模型来直接解决？

我们以前确实做过类似的决定，那就是：先等一等，等待模型变得稍微更成熟一些，然后再借助它来解决这些问题。因为到那个时候，解决成本会低得多，而且当下立即构建该应用程序的需求也并非迫在眉睫。今天就把它做出来，相比六个月后再推出，并不能带来什么真正显著的商业价值提升。所以，这是我们经常在权衡、也经常在思考的一个取舍。

<details>
<summary>Original English</summary>

**Guest**: And so like when I think of building agents, I think about, you know, getting data into the right spot. I think about building dashboards, trading platforms, whatever it is. It's like if I look at like what's the ROI that's going to be created from the actual ask that's coming in to me from a team perspective, and then like what's the true cost of actually building something today, like how can I balance that equation?

And then I make a decision of like, you know, is this something where the models are going to get good enough, I'm going to have more than enough compute in six months that it's not worth trying to tackle the problem today, it's better to delay it and actually address it with one of the new models?

We have made that decision before is like let's actually wait for the model to become slightly more sophisticated so that we can solve these problems with it, because it will cost less at that time and the need for that application to be built today isn't pressing. There's no like real business value increase that can be like will be created because it's produced today versus six months from now. So that's a trade-off that we actually, you know, make regularly and I think about regularly.

</details>

### 快速概念验证与避免数 Token 的陷阱

**Guest**: 另一方面，你也不能拖延太久才去着手构建。否则你可能会陷入永远都在等待下一个新模型、等待下一项新技术或新工具的循环中。

如今各种各样的软件开发脚手架和测试平台（software development harnesses），其妙处就在于：只要你善加利用，从梳理规划、构思概念（比如借助工具与产品经理或利益相关者一起探讨并明确需求定义），到实际编写代码，再到一个可运作的概念验证原型（workable proof of concept），整个过程快得惊人。

我所说的“可运作的概念验证原型”，是指用户可以点击交互、体验核心流程的原型。虽然它此时可能还没有经过网络安全审查，也没有完成在我们这个行业中为了让生产环境系统具备扩展性而必须进行的一系列合规与工程步骤，但你完全可以以极快的速度拿出一个可交互的原型（POC）或价值验证（POV）。

这也是我经常努力鼓励团队所有工程师去做的一大关键点：就是尽快做出 POC。别纠结于做 PPT，也不用顾虑其他枝节。充分利用 Token 去跑——我认为在某种形式或层面上斤斤计较地去“数 Token”，本身就是一种误区。更正确的做法是去思考如何创造价值：大胆去做，创造价值，产出价值验证原型，把它推到用户面前，快速迭代；如果发现不需要，就果断扔掉。按照这种方式做事，你最终耗费的时间和资金都会少得多。

所以，这是我们思考解决问题时的一个核心思路。虽然它可能没有直接套进“随着算力增加如何应对、让事情更简单”的长线大叙事里，但我是从一个更接地气、更短的时间周期来切入并思考这一点的。

<details>
<summary>Original English</summary>

**Guest**: Um, the other thing that we do is like you don't want to wait too long to basically build something. And so you can always be waiting for the new model, waiting for the new technology or whatever else.

Like the beautiful thing with like all of the various different software development harnesses today is if you lean into them, it's amazing how quick you can go from like concept mapping out your planning and concept with like fable for like you know just hey work with me and let's define this with the product person or with the stakeholder to actually writing code to having like a workable proof of concept.

And when I say workable, proof of concept, it's something people could click through, interact with, whatever else it is, doesn't have cyber security review, doesn't have all the other things that you need to do in our industry to make sure you like put something into production that scales, but you can get to a POC or a POV very quickly.

And so like that's one big thing I try to encourage all my engineers to do frequently is like just get to POC. Don't worry about powerpoints. Don't worry about anything else. Leverage tokens, which like I think it's a fallacy to be like counting tokens in some way, shape, or form. It's better to think about producing value. Go off, produce value, produce POVs, put it in front of people, iterate on it quickly, and throw it away if you don't need it. You will spend far less time and money doing those types of things.

And so that's like a big way that we think about trying to solve it. It doesn't maps into the par like the you know the how do you deal with increasing compute making it easier to do these things, but like I just I think at a much shorter time frame.

</details>

### 从 Bitter Lesson 到评估基准：如何投资智能体基础设施

**Host**: 是的，这非常有意思。因为你谈到了很多我认为大家近期也都在深入思考的事情。

如果回溯到 2023 年，当时我们几个人坐在一起，作为一个小团队讨论我们正在构建的东西时，大家就已经意识到了萨顿提出的“惨痛的教训”（The Bitter Lesson）。我们探讨过它，并且认真讨论过：“我们该如何避免掉进这个陷阱？”

站在当下这个节点来看，对我而言已经非常清楚的一点是：这绝非非黑即白的二元对立，而是一个连续的光谱。你不可能凭空构建出一套完美的技术架构，既能全盘吸收前沿大模型带来的所有最新能力，又完全不需要推倒重来任何已有成果。

所以归根结底，核心问题在于：我们究竟想在哪些领域进行重度投资？又在哪些领域保持相对审慎、保守的投入？因为正如你所言，我们今天确实需要一些能够切实落地的东西；但与此同时，我们也清楚地知道，我们所做的一部分投资——特别是针对我们围绕智能体各种基础构件（agent primitives）搭建的相当复杂的系统，比如调度框架（harness）、沙箱环境（sandbox）、数据出口与出网机制（how egress works）等所有这些环节——我们必须确保，无论未来前沿实验室发布了什么新突破，还是第三方推出了新能力，我们都能够无缝将它们索引并吸纳进来。

<details>
<summary>Original English</summary>

**Host**: Yeah, it's so interesting because it's like, you know, I mean, you touched on so many things that I think everybody's probably been thinking about, too.

And if you go back to 2023 when we were originally like sitting around as a small group talking about what we're building, we were aware of the bitter lesson. We talked about it. We said, "How do we not get in this trap?" And I think at this point, it's just really evident to me that it's like it's definitely a gradient, right? It's not this binary thing about you can somehow build the perfect technology to index into all the up, you know, everything coming in from the frontier in a way that you don't ever have to throw things away.

So really it gets down to like where do we want to invest heavily and where are we willing to invest conservatively because like you said we need something today but at the same time we're just aware that like some of these investments we make particularly around things like we've built you know fairly complicated systems around all of our agent primitives so the harness the sandbox how egress works you know all of these things and we we also want to make sure that as like things are coming out either from like a frontier lab or from like a a third party that we're able to index into that.

</details>

**Host**: 因此我认为，很大程度上这关乎“你究竟在什么时候选择进行认知更新（update）”。而这往往是最难做到的事情之一。

就我个人而言，一个非常典型的例子就是我在面对“云端代码执行（cloud code）”能力时所经历的大幅认知刷新。这倒不仅是因为我的本职工作中突然多了许多令人难以置信的实用工具，对我来说，真正触动我的是底层思维层面的认知转变。因为在此之前，对于我们究竟如何才能打造出真正具备通用泛化能力（truly generalizable）的系统，我一直持保留甚至怀疑态度。

但云端代码执行赋予了我们什么？你可以让它编写代码，然后它能直接执行这段代码，并且以某种可验证的方式在底层驱动一台计算机运转。就在那一刻，我意识到：我们已经集齐了通往真正通用智能的所有要素。因为如果你能够把这种能力大规模扩展开来，那么不仅在绝大多数知识工作领域，甚至在知识工作之外的许多场景中，它基本上什么任务都能完成——我们今天也确实开始看到这样的端倪。

快进到现在，大家正在日常使用的所有这些 AI 助手及相关工具，它们之所以如此强大惊艳，正是因为你可以抛给它一个此前从未见过、完全属于分布外（out of distribution）的新问题，而它可以在后台直接拉起一台计算机环境，并把这件事情给搞定。这在消费级场景下令人叹为观止，而如今我们也正在企业级场景中见证它的落地。

所以对我来说，那个关键时刻就在于促使我思考：我们究竟应该在哪些方向上进行重度投资？当然，我们依然需要持续投入构建智能体应用本身；但正如约翰（John）之前提到的，回到我们如何进行数据捕获与提炼（data capture and distillation），如何把这些数据作为状态（state）有效供给给模型，以及我们如何设计基准测试与评估体系（benchmarks and evaluations）。

以合伙律所为例，我们面临着一个非常独特的契机：我们与这家律所从零开始合作并共同成长，他们伴随着 Norm 一路发展起来。因此，我们能够直接与律师们并肩工作，共同搭建起这些基准测试与评估指标。

实际上，我们不再按照传统的产品路线图来规划——比如“你们什么时候才能造出一个能完成这三项特定任务的智能体”，而是转变思路：让我们制定一套计分卡（scorecard），用来衡量智能体乃至人类在完成各个维度的这些任务时，究竟表现如何、是否取得了成功；然后我们希望看到系统随着时间推移能够在这个计分体系上持续自我精进。

这样一来，当我们对系统做出通用层面的改进时，就应该能够观察到系统整体表现的提升，从而切实符合律师对改善自身工作流的预期；但与此同时，这也能避免我们倒退回最初的状态——当时我们在前期人为添加了过多的固定结构，最终却发现，如果能够把这些前置结构剥离掉，模型反而能够释放出更好的性能表现。

<details>
<summary>Original English</summary>

**Host**: And so I think a lot of it is just kind when do you update? And that that's one of the hardest things to do. And like for me, a good example was I really updated really hard on cloud code. Not so much that it was suddenly tools that like in my profession that we could use that were really incredible. What it really was for me was just this idea because I was a bit skeptical up to that point of how we would get something that was like truly generalizable. It's like well what does cloud code give you? Well, you can write code and then it can execute the code and like basically run a computer in some verifiable way.

At that moment, I was like, well, we have all the ingredients for like a truly generalizable intelligence because if you can go do this at scale, then I mean, you know, of course, like you can basically do anything in terms of most knowledge work and actually even outside of knowledge work, which we're seeing some today.

And you fast forward to now and like all these tools that people are using these like AI assistants and things. This is why they're so amazing is because you can ask a question it's never seen before, fully out of distribution. It can spin up a computer and go do this thing in the background. And for consumer, it's amazing. And then we're also seeing this now within the enterprise, too.

And so for me that moment was like well where are we going to invest heavily of course we still need to invest in what we're building on the agent side but going back to what John mentioned how we do our data capture and distillation and how we make this available is like state to these models and then also just how we do our benchmarks and evaluations and so with like the law firm for example we have this really unique situation where we started this law firm um you know from nothing so we we've kind of grown together they've grown with norm together and so we work directly with lawyers to dei to stand up these benchmark marks and evaluations and effectively rather than think of a traditional road map like when when are you going to build an agent that can go do these three things, it's let's have a scorecard that determines when an agent or when a human even is has success is successful um at completing these tasks across various dimensions and then we want to be able to see this just improve over time.

So as we make general improvements to the system, we should see an uplift to these, you know, these things like an attorney would expect to improve their workflow, but at the same time, not not getting kind of going back to the state that we were originally where we had added a lot of structure to it in a way that ultimately we found that we were actually could get even better performance if we were to remove that upfront structure.

</details>

### 从原型到生产环境：真正的硬仗在底层基础设施

**Guest**: 是的，我认为还有一件非常重要的思考维度：正如我刚才所谈到的，你确实可以在极短的时间内产出大量的概念验证（POC）和价值验证（POV）原型。但我依然认为，对于现阶段的大多数工程开发来说，真正艰难的硬仗依然在于把系统推进到生产环境（production）。

我所说的“推进到生产环境”，是指构建出那些真正扎根并运行在企业底层基础设施内部的支撑架构……

<details>
<summary>Original English</summary>

**Guest**: Yeah, I think like another thing that's important to think through is like you can produce like I was saying a lot more proof of concepts, proof of value very quickly. I still think like the hard yards for a lot of development out there is getting it to production. And what I mean by that is like infrastructure buildout that actually runs inside of the infrastructure

</details>

<!-- chunk 32/51 -->

### 企业级 AI 落地的隐性挑战：可追踪性与生产监控

**Speaker A**：……这在任何金融服务公司，或者说任何大型企业内部都是随处可见的现实。我认为很多售卖 AI 工具的人严重低估了这一挑战。正如你所知，在企业客户这一侧推进这件事是非常艰难的，我们经常要处理这些问题。

另外一点就是如何应对网络安全与系统可支持性（supportability）层面的要求。我注意到的一点是——虽然现在的智能体在这方面确实越来越强了——但你必须确保编写出来的实际软件是真正具备全链路可追踪性的，并且能够无缝接入你的运维/支持平台（S-tier/support platform），以便在生产环境中受到严密监控。这些问题依然是我经常引导大家去深入思考的。很多团队虽然还没开始大规模落地 Agent，但这一天终会到来；从我的角度来看，这是一件需要定期审视的事。

<details>
<summary>Original English</summary>

**Speaker A**: ...that's available inside of any financial services or enterprise company for that matter out there. I think that is a challenge that a lot of folks like underestimate if you're selling AI tools. It's that is hard on the other side just so you know deal with it quite a bit. Um, the other thing is is just like dealing with like the cyber security side of the fence and the supportability side of the fence. And so like one thing I've noticed, you know, the agents are getting better at this now, but it it's making sure that the actual software that's being written is truly traceable and it feeds into your S sur platform so that it can be monitorable in production. Those are things still that like I like to have people think about it. It's it's like they haven't started to scale yet with agents. They will, but it's something that from a my perspective I I think about regularly.

</details>

### 核心原语的人工防线与前沿智能的“导流管道”

**Speaker B**：确实很有道理。我们应对这个问题的策略——我相信很多其他公司，甚至包括你们团队可能也采取了类似的思路——就是在我们的代码库中，仍有一些核心模块在架构设计、系统构建、代码归属权，乃至任何改进与变更上，都必须保留完全的人工审查与监督。

这些模块是我们的核心原语（core primitives）。你可以基于它们向上构建各种应用，但构建在顶层的任何系统，绝不允许在没有人工复核的情况下擅自改动这些底层机制。这正是源于你刚才提到的顾虑：对我们来说，数据安全与快速交付同等重要，甚至远比速度更加关键。

当然，这也取决于你的业务类型是消费级产品还是企业级服务。我们显然需要处理高度敏感的数据，因此必须在底层建立极其完善的基础设施，确保在这些核心技术栈上绝不盲目冒进。有时候做到这一点并不容易，因为可能有人会给你展示一个非常炫酷的演示，让人眼前一亮，但你在兴奋的同时心里其实是充满警惕的：这确实很酷，但如果为了达到这种能力而暴露大量我们目前尚无法驾驭的安全风险，那就得不偿失了。

所以这始终是一种权衡取舍。我们在这些核心原语上进行重度投入并严格把控，而在其他方面则保持适度谨慎，因为随着前沿模型的持续演进，我们希望能留下充足的通道。今天早上我和团队沟通时用的比喻是：在整个平台架构中，我们必须为来自技术前沿的最新能力预留“导流管道”（conduits）。你绝不能筑起高坝，导致外部涌现的先进智能因为你僵化的架构设计而根本无法渗透进技术栈中。当然，这是一个渐进的平衡过程，我们难免会做对一些，也会做错一些。关键在于保持敏锐的认知、团队内充分沟通，在锁死核心基础构件的同时，对“推倒重来、即拆即换”保持高度开放的心态。

<details>
<summary>Original English</summary>

**Speaker B**: Makes sense. And we our approach to this and I'm sure a lot of other companies and maybe even you guys have taken this approach as well is there's parts of our codebase that we like still require like complete human oversight from when it comes to designing, building, code ownership, even improving any kind of changes to the codebase. And these are like our core primitives and these are things where you know basically you can build things on top of these but the things that you build on top of these are not allowed to like change these systems without having like human review. It's because of the things you mentioned is like you know data security for us is you know is is is like as paramount as delivering quick it's actually more important. So and for depends on where you are and if whether it's a consumer product or for us with obviously working with highly sensitive data like we have to build in so much infrastructure around this and ensure that we're not ever getting out ahead of like you know these parts of the stack which it can be hard because maybe somebody brings you and I'm sure you've seen this like a really cool demo and it's really exciting and you're looking at it terrified. So like this is this is very cool. But to get to this point in terms of capabilities like it would expose so much that we're not able to do yet. So I think it's just always that trade-off. So we just you know basically we invest heavily in these things and then invest conservatively in places where we realize as the frontier continues to improve um we want to make sure we're we have conduits and the way I described it actually this morning with the team is like basically throughout our platform we want to have like conduits for what's coming from the frontier. You don't want to have dams where like the intelligence is coming in and it can't quite get into your stack because you've built things in such a way. Again, it's a gradient. We're going to get some of it wrong, some of it right. Just being very cognizant of it, talking about it a lot, and making sure that our core pieces are are locked down, but then also, you know, being very open about um just rip and replace.

</details>

### 软件生命周期的剧变：从长线维护到低成本重写

**Speaker B**：我认为大家如今对“推倒重写”这件事已经变得非常熟练了。我已经从事软件研发 27 年了，有时候觉得像过了 100 年那么久，有时又觉得才过去 5 年。如果对比今天编写软件的能力与 10 年前我的工作方式，最本质的差异在于：10 年前，构建一款软件需要耗费大量的时间、精力、资金以及团队的心智资产。当时的情况就像船已启航出海——从你完成设计并着手编码那一刻起，这艘船就驶向了大洋，你必须尽可能长时间地维护它，直到它抵达大洋彼岸。

而今天让我感到非常适应的一点是，绝大多数内部应用基本上都是可以随时废弃的。构建它们，让它们在特定的时间节点为特定的业务目标服务；但你要清楚，它们在未来某个时刻就会被淘汰，而且淘汰更替的速度远比以往任何时候都要快，所以只要专注于下一步该做什么即可。

因此，坐在我这个位置或任何优秀工程师的位置上，核心挑战之一应该是不断自我追问：“我是否应该重写这个系统？重写它的成本，是否已经低于持续对现有版本缝缝补补、迭代升级的成本？”在十年前，任何人的脑海里都绝不可能冒出这个问题。如果你当年去找 CFO 说“我想重写一个内部系统”，对方肯定会觉得你疯了。而在今天，这成了一件极其合理的选择，也是我们所有人都应该去做的事，因为从头构建的全新应用最终可能创造出大得多的业务价值。这是我非常鼓励大家去实践的。听起来你们 Norm 团队在这方面也做了相当多的探索。

<details>
<summary>Original English</summary>

**Speaker B**: I think that's like a thing that I think everybody's gotten really good at. I I think that's like one of the biggest I mean, like I've been doing this for 27 years. Sometimes I feel like it's been like a hundred years. Other times I feel like it's been five. I think the the thing that's like really made a material difference like when I I look at the ability to write software today versus what I was doing 10 years ago was 10 years ago it took so much time, effort and money and people's like intellectual capital to produce a piece of software. It was almost like the ship had sailed. Like by the time you designed it and started writing code, it was out to sea and you were going to ride that baby for like as long as you could until it got to the other side of the ocean. And like what I've become very comfortable with today is like for the most part a lot of like internal applications can be just thrown away. It's build them, have them work for a purpose and a point in time, but understand that they're going to disappear at some point in time now much more quickly than ever before and then just think about like what comes next. And so I think one of the challenges with like sitting in my seat or any like good engineer seat should be constantly questioning like you know should I rewrite this and does it cost me less to rewrite it then it cost me to keep versioning the current version forward and that is like a question that a decade ago never would have came up in anyone's head if you went to say I want to rewrite an internal application like your CFO would have looked at you like you were insane and I think now it's a completely relevant thing that all of us should be doing because net new applications might produce way more business value at the end of the Okay. So, it's just something I encourage folks to do. It sounds like you guys are doing quite a bit at norm.

</details>

### 重拾工程本质：AI 时代的系统架构与工程师复兴

**Speaker A**：完全没错。归根结底就是那个核心概念：过去极其昂贵的东西，现在变得非常廉价。如果你不能迅速跟进这种认知转变，就会落伍。你刚才说感觉像是经历了 27 年、100 年还是 5 年，这种感受太真实了。如果你过度执念于 6 月份的技术形态，而现在已经是 10 月份了，感觉在这几个月里技术就已经发生了宛如过去 10 年般的飞跃。

太棒了，我们大概只剩最后一分钟左右的时间。最后还有什么结语想分享给现场观众吗？

如果要给大家留下一两点最有价值的心得，我想说，尽管我们今天探讨了非常多引人入胜的技术细节，但真正让我每天对工作充满热情的，是能够重新回归工程本身的那种纯粹乐趣。

我非常珍视的一段经历是：我曾在 IBM 做了整整 10 年硬核的底层工程师，在那个还用记事本（Notepad）和 VI 编辑器给 RISC 架构计算机手写指令级代码的年代写软件。那段经历棒极了，极其硬核、极客范儿十足。现在几乎没人再做那种工作了，但对我而言那是纯粹的快乐，我至今依然怀念那些日子。随着一个人在职业生涯中越来越资深，日常动手写代码的门槛往往会逐步升高；或者说在面对实际工程时变得举步维艰——比如处理流式计算中的复杂消费逻辑，面对所有繁琐的周边支撑，你会觉得：“天啊，搭建脚手架就这么难，我甚至都无从下手。”

而 AI 的出现，让我重新燃起了动手亲自构建系统的激情。因为我从未丢失过系统架构设计的认知与积淀。我在行业里的很多工程师身上也看到了同样的现象：他们在这个市场中摸爬滚打了 10 年、20 年、30 年，对复杂系统设计的规律了然于胸，而这一根本逻辑从未改变；如今，借助这些强大的新型 Agent，他们终于能够将深厚的架构智慧酣畅淋漓地转化为现实成果。

因此，我认为无论是创立一家新公司、在一家公司工作，还是单纯从事软件构建，现在都是一个令人无比兴奋的黄金时代，因为前方有一个崭新的世界正等待着我们去创造。这就是最让我心潮澎湃的地方。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, exactly. And I think it's just that concept of what used to be expensive that's now cheap. And if you don't update quickly on that, then it's, you know, like it's incredible. You said it feels like 27 or 5 years or 100 years or 5 years. It's like that if you over if you overindex too hard on something that was in June and now it's October, like you know, it feels like in some ways there's been like 10 years of technological advancement. So, um, well, great. We only have a minute or so left. Is there any closing remarks? I mean, I think like the the one thing I'd like leave the audience on if if you want like, you know, like good takeaways from this, it's like we talked about a lot of like very interesting things. I think like what makes me like excited to go to work is like it's cool to get back to engineering. One of the things that like I value is like, you know, I was a hardcore low-level engineer for 10 years at IBM and like wrote like, you know, this is way back in the day of using Notepad and VI to write like instruction level code for risks machines. It was like awesome. It's nerdy as all heck. No one does this stuff anymore, but it was like fun for me. I still enjoy those days. As you get more senior in your career, it like the barrier to actually writing code on a daily basis disappears or it becomes more like hard to get through like dealing with a stream like processing stuff off a stream. It's just all these things are like, "Oh my god, I can't even get started because the scaffolding is so hard." With like AI, it's been like reinvigorating to get back and actually build stuff because it's like I never lost my knowledge on how to architect things. I see this with a lot of engineers out there. They understand because they've been in the market 10, 20, 30 years. They understand the complexity of system design, which hasn't changed, and now they can actually express that knowledge with these new cool agents. And so, I think it's a super exciting time to be like starting a company, working at a company, and like building software because there's like a whole new world that we can create out there. So, that's what like excites me. So,

</details>

### 圆满结语与致谢

**Speaker B**：是的。太棒了，非常感谢你，非常荣幸能来到这里交流。

<details>
<summary>Original English</summary>

**Speaker B**: yeah. Well, cool. Well, thank you so much. It's been an honor.

</details>

**Speaker A**：好的，也感谢大家今天邀请我们来参会，非常感激。

<details>
<summary>Original English</summary>

**Speaker A**: Yep. Thank you guys for having us here today. Appreciate it.

</details>

### 新演讲开场：形式化验证与 AI 信任生态

**Venu Ganesh**：大家好，我叫 Venu Ganesh，非常高兴今天能来到这里。我是 Kepler 的首席执行官兼联合创始人。

今天的分享会相当有趣，因为它的渊源可以追溯到三个月前发生的事情。三个月前，我在 AIE World Fair 上发表了一场关于验证（verification）的主题演讲——虽然内容可能有些许重合，但我当时重点阐述了为什么绝大多数机构都需要在 AI 信任生态中引入某种形式的验证机制。

昨天在座的多数人应该也看到了，我和 Jack 一起同台讨论了为什么管理过 Citadel 最大投资组合并创立了 Candlestick Capital 的 Jack 至今仍然无法信任 AI。而在过去这短短三个月的时间里，风险投资领域已经有大约 2.7 亿美元的资金涌入了形式化验证层（formal verification layers）。甚至有 VC 直接拿了我们 Kepler 自己的商业计划书（pitch deck）给了一家竞争对手，对方随即做出了一款连品牌标语（tagline）都跟我们一模一样的产品。不过我并不为此感到愤愤不平，只是……

<details>
<summary>Original English</summary>

**Venu Ganesh**: Hi everyone, my name is Venu Ganesh. Um, excited to be here today. Uh, I'm the CEO and co-founder of Kepler. Um, this is going to be kind of an interesting talk because it comes from what happened three months ago. So, three months ago, uh, I think there's a little bit of an overlap, but I gave a talk at AIE World Fair around verification. um and why that most institutions need verification in some form of the trust ecosystem of AI. Well, yesterday most of you saw Jack and I were on stage talking about why Jack, who ran Citadel's biggest book and started Candlestick Capital, still doesn't trust AI. Since that threemonth period, there's been about a $270 million of VC money that got poured into formal verification layers. A VC actually took Kepler's own pitch deck and gave it to a competitor and produced something that has our same tagline. I'm not bitter, just

</details>

<!-- chunk 33/51 -->

### 验证机制不能只在事后附加

**Speaker**: ……一点点。但有趣的是，他们抄错了部分。所以今天我想真正向各位从业者说明的是：你不能仅仅在最后阶段才附加上验证机制。几个月前我做过那场分享，当时 Anthropic 刚刚发表了一篇关于 Kepler 运作原理的文章，阐述了它为何如此强大且独一无二。因此，我想深入探讨我们在技术层面究竟是如何实现这一点的。归根结底，这一切都源于一个非常简单的洞察：华尔街依然不信任 AI。

<details>
<summary>Original English</summary>

**Speaker**: a little. But the funny thing is they copied the wrong part. And so what I want to do is actually give you the practitioners today, you can't just tack verification on at the end. And so, uh, when I gave that chat or that talk a few, um, months ago, uh, Anthropic had just published an article on how Kepler does what it does and why it's really powerful and really unique. So, what I want to do is get into the technical side of how we do the thing that we do. And ultimately, this is driven by one very simple insight. Wall Street still doesn't trust AI.

</details>

**Speaker**: 大多数人认为这是因为 AI 会胡乱估算、会产生幻觉——前沿模型会凭空捏造内容，这确实是事实，也是其中的一部分原因。但真正核心的潜在问题在于，我们迫切渴望使用的这项技术存在结构性缺陷。也就是说，如果你去和那些构建 RAG 平台的人交流，他们大多数人会说：模型最终会变得足够好、甚至更好，直到彻底消除幻觉。这种说法纯属无稽之谈。你知道幻觉的另一个代名词是什么吗？是 Alpha（超额收益）。Alpha 正是一家投资机构赚钱的方式。你和你的分析师所拥有的创造力，正是让你的机构保持独特性的一种机制；否则，世界上就只需要存在一家公司了。因此，当你去问关于数据来源这类简单问题时，一方面模型确实会凭空捏造；另一方面，你们机构的内部数据实际上从未在这个架构中得到体现。

<details>
<summary>Original English</summary>

**Speaker**: Most people think that's because of this. Uh, AI will estimate things. It will hallucinate things. a frontier model where make stuff up and ultimately it is and that's a component of it. But the actual core underlying problem is we have a structural problem in this technology that we're all so desperate to use. Meaning if you actually chat with people that are building rag platforms, most of what they'll say is well the models will eventually get good or get better to the point they will eliminate hallucination. That is a nonsensical term. You know another word for hallucination alpha. Alpha is how a firm makes money. The creativity that you have and that your analysts have is a mechanism through which you can be a unique firm. Otherwise, there should be only one company on earth. So when you ask these types of simple questions around where data comes from, there is a piece of this that the model will just make things up. And there's a piece of this that your firm's internal data is never actually reflected in this setup.

</details>

### 金融投资中的信任危机与 RAG 的局限

**Speaker**: 那么我们现在看到了什么呢？我们看到每个手里有支票簿的人都在疯狂买入他们能买的一切——各种 RAG 平台；有些机构尝试自研，有些机构在做智能体（Agent）试点。今天早上我还开了一个客户会议，有人说他们实际上是一家“AI 原生优先（AI first）”的公司，这意味着他们只运行着一个 Copilot 智能体在处理所有这些事情。那为什么我们没有看到基本面投资发生彻底转变呢？为什么我们大家没有都变成 Jane Street？为什么这一切还没有发生？挑战实际上源于这样一个理念：要想产出你自己真正信赖的工作成果，你必须能够信任它。换句话说，如果出了错，你必须能找到责任人。因此，我们经常看到这样的数据：80% 的金融高管信任这些数字，但随后有 31% 的人找出了错误。

<details>
<summary>Original English</summary>

**Speaker**: So what are we seeing right now? We're seeing everyone with a checkbook buy everything they can. Every rag platform. Some firms are trying to build. Some form some firms are running agent pilots. I had a a customer meeting this morning where someone said they were actually an AI first firm which means they have one co-pilot agent running all this stuff. So why are we not seeing the complete switch of fundamental investing becoming effectively why are we not all Jane Street? Why why is that not happened yet? And so the challenge really comes from this idea of in order for you to produce work product that you believe in, you have to trust it. Meaning you have to blame somebody who gets it wrong. So we see numbers like this all the time where 80% of finance execs trust numbers but then 31% find those errors.

</details>

**Speaker**: 所以我们真正需要的是什么？我们需要的是这样一种局面：作为应用构建者，我们为 AI 应用获得的评价不能仅仅是“把东西 RAG 化（ragify）”而已。这些评价是我们从某些特定的人那里收集来的实际原话——我不想指名道姓说这是竞争对手，但就是其他人——他们的产品演示效果极好，表现得像一个极其聪明的实习生，或者只要你接入了正确的结构化信息它就是对的；但剩下的那最后 10% 依然会出错。所以我想做的是——我们很幸运拥有出色的合作伙伴，比如 Turbopuffer 等团队，我昨天也做过一场类似的分享——我们究竟该如何进行验证？我们该如何在架构上构建一个在数值上绝不发生幻觉的系统？

<details>
<summary>Original English</summary>

**Speaker**: So what do we actually need? We need a situation where the reviews that we're getting for AI apps as builders ourselves do more than just ragify things. And and these are quotes we've actually pulled from specific uh I don't I don't want to say our competitors but other people where things demo super well and they behave like a really smart intern or things are right if you just hook up the right structured information but that last 10% still gets things wrong. So what I want to do is we're lucky we have great partners and folks like Turbopuffer and I gave a similar chat yesterday about this but how do we actually do the verification? How do we architecturally build a system that does not hallucinate numerically?

</details>

### 错误数据的三大根源与系统解法

**Speaker**: 那么我们现在就来谈谈这个问题。错误的数字或错误的事实来自于三个根源：第一种情况，你检索了错误的文档。比如我拉取了一篇文档，是从别处随便抓来的无关内容。怎么解决这个问题？当然是通过检索到正确的文档。但这本身就很复杂。所谓“正确的文档”，是指我们公司自己关于这只股票未来价值的内部研报吗？还是某个我比任何人都更信任的明星分析师的研究？这是第一点。

<details>
<summary>Original English</summary>

**Speaker**: So let's talk about it now. Wrong numbers or wrong facts come from three sources. Either one you retrieved the wrong document. So I pulled a document some random thing from somewhere else. How do you fix this? Well, by retrieving the right document. But that in itself is complicated. Is the right document my own firm's internal analysis of what this stock is going to be worth? Is it, let's say, uh, some analyst who I really trust more than anyone else? That's piece one.

</details>

**Speaker**: 第二种失败模式：我们找到了正确的来源，但从该来源中提取出了错误的数字。假设我们要查清楚比如 Palantir 在 2023 年的营收是多少。如果我去看 2025 年的 10-K 财报，上面提到了 Palantir 2023 年的营收是某个数值，我必须确保这个数字确实对应的是 2023 年，而不是 2025 年。针对这种情况，解决方案是设立一个能够实际检查每一处引用的过滤器。但这依然存在问题，因为这种过滤只是在事后才生效，形式化验证（formal verification）在这里根本起不到实质性作用，因为内容已经被生成出来了。

<details>
<summary>Original English</summary>

**Speaker**: Now, failure two. We get the right source and we pull the wrong number out of that source. Let's say we're trying to figure out what the revenue for, I don't know, Palanteer was back in 2023. Well, if I look at the 2025 10K that says Palanter's 2023 revenue was this, I better make sure that that number corresponds to 2023 and not 2025. So, the fix here is really we have a filter that actually checks each citation. But this is still a problem because that filter only applies after the fact and formal verification doesn't actually help here because the thing has already been produced.

</details>

**Speaker**: 第三个根源是心算逻辑。大语言模型根本不会做算术，它们只是在预测下一个 token。对于那些反驳说“我们有确定性模型”的人，很好，我们确实有。但我们同样有一个只需要消耗一个 CPU 周期就能极其高效把两个数字相加的处理能力，我为什么不直接使用那个 CPU 周期呢？因此，第三种失败的应对之道是：让我们使用现成的确定性工具去实际计算数值和实体，而不是依赖某种外部黑盒工具。

<details>
<summary>Original English</summary>

**Speaker**: Three is the mental math. Models don't do math. they predict the next token. Now, for those of you who are going to say we have deterministic models, great, we do. We also have one CPU cycle that's good at adding two numbers together. Why don't I use that CPU cycle? So, third failure is let's use deterministic tools that we already have to actually compute numbers and entities rather than relying on some external tool.

</details>

### Kepler 的架构核心：指针、确定性计算与前置解引用

**Speaker**: 这就是我们的做法。这就是 Kepler 背后的核心秘诀，至少在解决第一点上是如此；当然我们还有很多其他设计。我们在架构底层从根本上就是截然不同的：所有的数字都由代码来写入。代码和预处理所做的工作，是为每个唯一标识符分配指针——也就是具体的事实，比如 10-K 财报中的某个具体数字。这个过程发生在一个庞大的预处理与上下文构建步骤中，从而将非结构化数据转化为结构化数据存储。在这一架构下，模型本质上变成了一位聪明的分析师：它负责规划并找出解决问题的方法与路径，但其本身并不直接充当解决问题、输出数字的执行主体。

<details>
<summary>Original English</summary>

**Speaker**: So, here's what we do. This is the magic behind Kepler at least for piece one. There's a whole bunch of other stuff. We are architected fundamentally differently. Code writes every number and what code does and pre-processing does is we assign pointers to unique identifiers meaning facts meaning something like a number in a 10k. This operates in a giant pre-processing and contextualization step such that all of this exists going from unstructured data to a structured data store. Then the model is effectively a smart analyst. It figures out how to go about solving the problem but not actually being the thing to solve the problem itself.

</details>

**Speaker**: 因此，模型做的是制定计划，它会说：“我要去这里检索这个来源，检索这个实体，执行这个操作。”由代码和数学运算来完成实际检索，而不是在搜索阶段让模型直接从 10-K 里硬抓取数字——那种做法会产生极其昂贵的 token 开销。Anthropic 和 OpenAI 确实应该感谢大家支付了那么昂贵的 token 费用、疯狂刷高 token 消耗，但你们大部分的公司现在可不喜欢这样了——我知道过去有一段时间甚至有人因为拼命推高 token 消耗而拿到奖金。

<details>
<summary>Original English</summary>

**Speaker**: So it plans it says I'm going to go here and retrieve this source and retrieve this entity and do this thing. Code and math do the retrieval by actually pulling a number out of a 10k at like a search time. That's a hugely expensive token cost and anthropic and openai should thank you for paying all those tokens and token maxing but most of your firms don't like that at least anymore. I know there were people getting bonuses from token maxing for a while.

</details>

**Speaker**: 接下来非常关键的一点是，一旦模型读取了这些指针，它在结构层面上是无法自主生成数字的。这意味着，除非模型拥有一种能够解引用（dereference）该指针的具体机制，否则那个数字或事实在物理上就绝不可能出现在 Kepler 的输出结果中。当然，我们确实会运行一个后处理步骤，也就是验证步骤。这也正是之前那家公司滑稽的地方所在——他们仅仅抄袭了验证这个环节，但前面所有的结构化底层设计却全被漏掉了。所以作为终端消费者，你实际看到的效果是：你会看到类似“营收介于这个金额到那个金额之间”的陈述，并且你可以在界面上直接点击这些信息标签（chips），清清楚楚地看到我们究竟是如何一步步获取到该信息的。

<details>
<summary>Original English</summary>

**Speaker**: Um, now the next piece of this is really once the model has actually read both these pointers, it can't structurally generate numbers. Meaning unless the model actually has a mechanism of dreferencing that pointer, that number or that fact cannot be generated in Kepler's output. Now, we do run a post-processing step which is the verification step. And this is the piece that was kind of funny where the last company just copied the verification piece, but all the structural stuff beforehand didn't make it. So what you as a consumer actually see is you see something like the revenue was this amount to this amount and you physically can click on these chips and see exactly how we got the information.

</details>

### 从 Citadel 经验看基本面投资与确定性查找

**Speaker**: 在我过去的职业生涯中，我有幸曾担任 Citadel 的业务工程主管（Head of Business Engineering）。我当时跨越整个公司展开工作，致力于搞清楚：我们到底需要构建什么样的软件来帮助我们创造 Alpha？在 Citadel，最不可思议的事情就是投资经理（PM）们个个天赋异禀、极其聪明，但他们只有在与确定性工具和技术紧密配合时才能真正发挥出最大威力。这正是基本面投资背后极其奇妙的核心洞察：基本面投资者在理解和洞察数据方面极具天赋，但前提是那些数据必须百分之百准确。因此，当你构建像 Kepler 这样的系统时，你实际上必须做到：精准查找已有的正确信息，同时对未知或尚未拥有的信息保持高度的敏锐与巧妙处理。

<details>
<summary>Original English</summary>

**Speaker**: Now in my past life, I had an opportunity I was head of business engineering at Citadel. So I worked across um the firm to figure out effectively what do we need to produce software that helps us generate alpha. You know the crazy thing with Citadel PMs are so talented and so smart but they work when they're paired with deterministic tools and technology. That's kind of the magical insight behind fundamental investing. Fundamental investor is so good at understanding data but that data has to be right. And so when you build a system like Kepler, what you effectively have to do is look up the right information and then be clever about the information you don't have.

</details>

**Speaker**: 让我打个通俗的比方。大多数买方研究员或买方投资者通常会尝试使用自己的分析工具或自己搭建现金流折现模型（DCF），接着他们会去主动寻找和搜索他们所欠缺的信息——他们会预约 GLG（高临咨询）或 Guidepoint 的专家访谈电话，寻找行业专家交流，或者直接同企业管理层对话。我们的系统其实也是完全同样的运作逻辑。我们的做法是：选定一条路径，将我们能够确定性存储的信息直接以确定性的方式存储起来。而当我们遇到无法以确定性方式预先存储的信息时，我们会运行类似的预处理流程来抓取信息，并将这些信息保存在混合存储机制中——这结合了 Turbopuffer（顺便说一句，他们非常棒）以及许多其他机制。

<details>
<summary>Original English</summary>

**Speaker**: So let me give you the parallel. Most folks and most byside researchers or by side investors try to use tooling or build DCFs on their own and then they find and search for information they don't have. They schedule GLG or guidepoint calls. They find experts. They speak to management. The same system actually applies here. So what we do is we pick a path and we store the information deterministically that we can actually store deterministically. When we have information we can't store deterministically. We run similar pre-processing steps to grab information. Store that information in a hybrid storage mechanism which is a combination of turbuffer who's awesome by the way and a bunch of other um mechanisms.

</details>

**Speaker**: 最终，我们结合使用了重排（reranking）技术与老派传统的指针解引用方式（类似于直接调用 get 方法），将数据拉取到我们的系统中。这之所以至关重要，是因为精确查找（lookup）是绝对不可能出错的；但如果是搜索，如果你用同样的查询语句连续跑 10 次搜索，模型内在的概率特性决定了它必然存在熵增与随机性。而这种不确定性其实正是一个巨大的机会，这也正是我们在此处所作出的彻底革新。至于具体的实现方式，我们将其进行了细致拆解，而这一机制在整个 SEC 财报披露的世界中同样适用。我们正在……

<details>
<summary>Original English</summary>

**Speaker**: And then we ultimately use a combination of reranking with literally old school like pointer dreferencing like get methods to pull things into our system. Now why this matters is a lookup cannot get it wrong. Search can if you're running the same 10 searches with the same query. The probabilistic nature of models means there's inherent entropy. That's actually an opportunity. And so that's what we've changed here. Now how we do this is we break this down and this occurs across the SEC world as well. Um we are

</details>

<!-- chunk 34/51 -->

### 混合检索与跨编码器重排序

**Speaker**: 我们经常会丢弃候选文档，这意味着我们必须持续从全局角度评估：不仅要看哪个数据源适合提供什么信息，还要判断究竟哪些文档应该在全局范围内停止检索。因此，我们先运行 ANN（近似最近邻检索）加上 BM25 来召回一组文档，通常最多返回 200 篇文档。接着我们做倒数排名融合（Reciprocal Rank），实际有效召回的大约是 60 篇文档，这样理解可能是最准确的。

<details>
<summary>Original English</summary>

**Speaker**: frequently throwing candidate documents away meaning we consistently have to look at not only what source is the right source for what information but also which document should we stop looking at kind of globally. So we run ANN plus BM25 to get back a set of documents. It's usually up to 200. We do reciprocal rank, we effectively get 60 documents back is probably the best way to think about this.

</details>

**Speaker**: 之后我们运行交叉编码器（Cross-Encoders）。我们尝试准确地将查询（query）与实际切块后的文档拼在一起进行分析，并以此获得排序结果。这种架构赋予我们的能力在于：我们可以进行范围极广的检索。你知道大语言模型（LLM）不擅长做什么吗？它们不擅长进行极宽范围的搜索。LLM 倾向于制定一个计划，然后寻找最快或最容易的广度优先搜索机制——准确地说是先拿到第一篇文档，然后就沿着它往下推导。因此，我们的做法是允许系统进行非常广泛的搜索，然后再逐步缩小范围。大模型之所以不喜欢大范围搜索，是因为成本太高昂了；而且去横跨大量不同数据源进行筛查，比起在第一次命中后就直接拿到奖励函数并顺着做下去，其体验和表现要差得多。

<details>
<summary>Original English</summary>

**Speaker**: Um then we do cross encoders. We try to figure out exactly the query and the actual document chunked together and get those results that way. What that allows us to do is we can search really wide. You know what LLMs aren't good at doing? Searching really wide. What they try to do is create a plan and find either the fastest or easiest breadth first search mechanism of actually like getting the first document and moving forward. So we allow this to search really wide and then narrow from there. The reason LLM don't like searching wide is because it's expensive. It's because looking across a bunch of different sources is significantly worse than getting the reward function back with your first hit and going from there.

</details>

### 企业级检索中的多租户与安全风险

**Speaker**: 好，接下来我想花点时间谈谈安全问题，因为这极其重要。Kepler 在构建之初就秉持着“安全第一”的理念和心态。对于客户文档——这番话是专门讲给在座的构建者（builders）听的——这是一件目前根本没人在讨论的事情：没有人真正深入探讨过，在用户范围（user-scoped）的文档检索机制中，究竟使用的是哪种 OAuth Token，其安全性到底如何。这其实非常可怕。

<details>
<summary>Original English</summary>

**Speaker**: Okay. So, I want to talk a little bit about security here because it's super important. Kepler was built with a security first mindset and security first mentality. Now, client documents and this is specifically targeted towards the builders here. This is a thing that no one's chatting about. No one is actually talking about the security of what OAuth token is used in what user scoped mechanism of retrieving documents. It's actually pretty scary.

</details>

**Speaker**: 那么我们来谈谈人们正在尝试构建的这些系统中，通常会出现哪些问题，以及你该如何修复它们。首先也是最重要的一点：你忘记对租户（tenant）进行过滤。转眼之间，Citadel 就能搜索 Millennium 所有的内部文档，那你可就惹大麻烦了。第二点，调用方声称自己是另一家机构——这意味着我可以伪称自己是某个实体，冒用其身份去查询文档。

<details>
<summary>Original English</summary>

**Speaker**: So let's talk about how things go wrong in these systems that people are trying to build and how you can fix it. First and foremost, you forget to filter the tenant. All of a sudden, Citadel can search all the Millennium's documents. You will be in a lot of trouble. Second, a caller claims to be another firm, meaning I can claim that I am impersonating this other entity and querying documents that way.

</details>

**Speaker**: 第三点，检索返回了过时的信息。我们在全局范围内甚至在 Google 搜索结果中都遇到过这种问题。第四点，直接读取操作绕过了检索规则，这意味着你并没有在受控的完整语料库中检索，或者缺少白名单机制，你只能拿回发起搜索的那单份文档。第五点，你命中了未填充数据的空索引。

<details>
<summary>Original English</summary>

**Speaker**: Third, search returns information that's outdated. We've had this problem kind of globally and even Google search results. Fourth, direct read skips the search rules, meaning you're not actually querying the full corpus of information or like there's not an allow list. You only get back the single document that you did the search. Five, you hit an index that isn't populated.

</details>

**Speaker**: 实际解决所有这些问题的途径——这里列出了各个具体要点——就是将安全机制内置到检索的作用域（scoping）约束中。我认为这是很多试图自行构建此类系统的人所忽略的另一个关键部分。不可避免地，大家终究会开始关注检索这些信息所附带的安全风险。在金融界，特别是对华尔街的人来说，Alpha（超额收益）是最难以捉摸的东西。因此，确保你拥有一套优秀的机制，能够严格限制每次查询所返回的文档集合，是至关重要的。

<details>
<summary>Original English</summary>

**Speaker**: The way to actually solve all these problems, and there's individual things listed here, is actually scoping searches with security built in. That's kind of another critical piece that I think a lot of people miss when they're trying to build these systems themselves. Inevitably, people will start caring about the security associated with querying this information. Alpha is the most elusive thing out there, especially for folks on Wall Street. So, making sure you have a good mechanism of actually constraining the set of documents that come back with each query is really important.

</details>

### 确定性事实验证与指针机制

**Speaker**: 好的，现在我们来聊聊验证（Verification），这是这里的最后一块拼图。这大概是我们最广为人知的特性，但刚才提到的其他环节我们也都在做。我们实现验证的方式是对信息进行预处理，并以确定性（deterministically）的方式存储下来。我们拥有类似代码级逻辑的系统，能够写入具体的独立指针（pointers）。模型随后只能读取这些指针；只有当这些数据切实存在于数据库中时，才能从中提取信息。如果我从一个哈希表（hashmap）中取一个根本不存在的键，我什么都拿不到。正是这种机制的结合，使我们能够切实确保检索到的信息真实来自于声称的那个数据源。

<details>
<summary>Original English</summary>

**Speaker**: Okay, now let's talk about verification, which is the last piece here. This is probably what we're known most for, but we do the other stuff I mentioned as well. Um, how we do this is by pre-processing information and storing it deterministically. We have systems like code that actually write individual pointers. The model can only then read those pointers and grab information back if they exist in the database. If I grab something out of a hashmap that doesn't exist, I don't get anything back. And so this combination is what allows us to actually make sure the information that we retrieved actually came from the source that it came from.

</details>

**Speaker**: 这里展示的是我们数据源 ID（Source IDs）底层样貌的一个脱敏版本。它们实际上就是哈希值。这些都是非常简单明了的做法，你完全可以在自己的系统和架构中实施，以确保提取出来的确实是真实存在的事实。

<details>
<summary>Original English</summary>

**Speaker**: Now this is a kind of hidden version of what our um source IDs look like. But these are hashes and these are very simple things that you can do in your own system and your own setup to ensure that you're pulling back facts that in fact do exist.

</details>

**Speaker**: 很好。以上就是我们如何做事实验证的大致介绍。现在我想展开谈谈这项技术从全局视角来看带来了什么。它使我们能够对从严密扎根（grounded）的数据语料库中得出的事实进行逐一验证。作为构建者、初创公司创始人，或者正在苦苦思索“我该如何信任系统输出”的人，你真正需要做的事情其实就那么几件。你必须向人们证明：当你构建这些理论上正在寻找 Alpha 或任何其他洞察的智能体（Agent）时，你所使用的信息是真正相关的、具体的，而且最重要的是，对你所服务的用户群体而言是准确无误的。

<details>
<summary>Original English</summary>

**Speaker**: Cool. So that's a little bit about how we do verification. Now I want to chat a little bit about what this enables kind of globally. This enables us to verify facts that come out of our grounded corpus of data. Now you as a builder or you as a startup creator or you as someone who is trying to figure out how do I trust my outputs really just need to do a couple of things. You need to show people that as you're creating these agents that are theoretically looking for alpha or whatever they be looking for, you're using information that is actually relevant and concrete and most importantly accurate to the set of people that you're trying to service.

</details>

### 华尔街对 AI 的信任危机与拒绝机制

**Speaker**: 最终，我们建立起了一种契约：引用来源要么被验证，要么在检索阶段被修正，要么直接被彻底拒绝（refused）。仔细想想，这相当不可思议。如果一个模型无法解引用（dereference）某个指针，它就绝对无法将那个数字打印输出出来。这是一件非常颠覆性的机制。这意味着输出的不仅仅是一个孤立的数字，更关乎整套事实体系。就像我们看到司法案件中频频出现大模型凭空捏造判例的情况——那我们为什么不能构建一套系统，以确定性方式存储判例，允许我们在既有列表中检索，从而彻底杜绝凭空凭空冒出一个子虚乌有的案件判例呢？因此，这种机制和这项技术在全局层面上具有极其广泛的适用性。

<details>
<summary>Original English</summary>

**Speaker**: So we end up with a contract where citations are either verified, corrected at search time, or flat out refused. This is crazy if you think about it. If a model cannot dresolve that pointer, it cannot print that number out. So that's kind of an insane thing. It means that the whole and not just a number. Let's talk about facts. Like we see these court cases all over of precedents being hallucinated. Well, why can't we create a system that just has the precedent stored deterministically and allows us to search through that list and not have a random court case that never existed all of a sudden start existing? So this tech, this mechanism and this technology actually becomes fairly globally applicable.

</details>

**Speaker**: 我今天站在这座舞台上，毫无保留地告诉大家我们是怎么做到的，原因在于我非常害怕：我害怕华尔街因为其他太多公司或者内部土法自建团队带进机构里的恐慌，而永远无法信任这项技术。现在的局面已经演变成：绝大多数所谓的金融 AI 工具目前仅仅被用来排版 PowerPoint 演示文稿。尽管很多人吹嘘，但业内至今仍没有人能从头到尾完整构建出一个现金流折现（DCF）估值模型。倘若真的有人做出来了，华尔街上的每一家公司早就连夜采购使用了。

<details>
<summary>Original English</summary>

**Speaker**: And the reason I'm on stage telling you how we do what we do is because I'm terrified that Wall Street never trusts this technology because of the fear that so many other companies or so many build it at home folks have been uh instituting in these organizations. It's gotten to the point where the vast majority of finance AI tools right now are being used to format PowerPoint presentations. We still haven't actually built a DCF cradle to grave despite what most people are saying. And if we had, every single company on Wall Street would have adopted that overnight.

</details>

**Speaker**: 这就是我的担忧。我的担忧源于一个极其简单的事实：要让我们真正从这项技术中获取价值，我们就必须构建出人们真正能够信任、能够验证的技术。这不仅在金融领域适用，在大量不同行业中同样如此。所以，请大家务必从这场演讲中吸取你需要的内容，促使人们真正使用这项技术；否则，我们所有人未来都会丢掉饭碗。

<details>
<summary>Original English</summary>

**Speaker**: So this is my fear. My fear comes from a very simple fact. For us to actually get value out of this technology, we need to be able to build technology that people actually can trust and can verify. That isn't just true in finance. It's true in a bunch of different industries. So, please take what you need to from this presentation and get people using this technology. Otherwise, we're all going to be out of a job.

</details>

### 生产环境指标与构建者的验证清单

**Speaker**: 现在，我想带大家复盘一下当我们目睹这一过程时所发生的实际情况。当我们走完整个流程时——这里展示的其实是我们真实的生产环境数据——所谓“拒绝”（refusals），是指当模型无法生成某个具体数值时的状态。换言之，模型会明确表示“我无法解引用该指针，因此我无法产出这个数值”。我们观察到拒答率出现了极为剧烈的断崖式下降。之所以没有完全降至零，是因为大模型本质上依然是概率性的，意味着它在推理阶段的生成之后仍然有可能凭空编造数字。因此，在此之后我们还设置了一道后处理（post-processing）工序。

<details>
<summary>Original English</summary>

**Speaker**: Now, I want to talk through what happened when we saw this. So, when we went through this whole process, this is actually some of our real production data here. Refusals are when the model does not is not able to produce a number, meaning the model will say "I couldn't dereference this pointer, therefore I could not produce this number." We saw that drop super drastically. Now the reason that it didn't drop to zero is because models are still probabilistic, meaning it can still make up numbers after the fact during inference. So there is another post-processing step after this that we have as well.

</details>

**Speaker**: 但我通过这张幻灯片想要强调的核心观点是：仅仅通过构建一个让模型必须解引用自身指针的系统，你就能够打造出一个极其强大且极具可验证性的 AI 平台。对我而言，这就是我向各位提出的诉求——在你们进行系统构建、进行方案划界的过程中，对于你们使用的任何工具，都要质问他们：你们的数字到底能不能被实际验证？去质问他们：你能否看清楚数据源究竟在哪里？这种来源追溯不能仅仅是事后打上的某种粗糙注解，而是支持用户直接点击那个数字，无论是计算值、抽取值，还是两者的结合，都能看清其来龙去脉，从而确保你对获得的洞察深信不疑。

<details>
<summary>Original English</summary>

**Speaker**: But my point with this slide is just by creating a system where the models have to dereference their own pointers, you can actually create a very powerful, very verifiable AI platform. And that to me is my ask to all of you: as you go through the building process, as you go through the scoping process, any tool that you use, ask them if you can actually verify the numbers. Ask them if you can see where the sources are—not in terms of some after-the-fact annotation, but click on the number, whether it's a calculation, whether it's an extraction, or some combination of the two, to make sure you trust the insight.

</details>

**Speaker**: 归根结底，所有这一切都将成为解锁价值的钥匙。因此，无论是作为供应商还是作为系统构建者，请多问问这些问题：模型是否切实输出了指针？它是否真正建立了一套验证输出的机制？每一处引用是否都核对了来源？计算过程是否都核对了数据来源？你是否拥有一套机制，能够阻止本不该触达客户的文件流入外部？而最关键的是：当一个凭空冒出来的无源数字出现时，系统会怎么处理？当事实无中生有被捏造出来时，系统又该如何处理此类幻觉？

<details>
<summary>Original English</summary>

**Speaker**: And all of this ultimately is going to be the unlock. So you as a vendor or you as a builder, ask these questions. Does the model actually write pointers? Does it actually create a mechanism for verifying the output? Is every citation source checked? Is arithmetic source checked? Do you have a mechanism for stopping files that reach clients or customers that it shouldn't reach? And most importantly, what happens to a number that came from nowhere? What happens when a fact comes from nowhere, and how do I actually handle these kinds of hallucinations?

</details>

**Speaker**: 建立这整个平台，实际上就是为了让一个浅显朴素的道理变得不言自明：我们可以拥有全世界最顶尖、最智能的模型，我们可以调用令人惊叹的前沿科技，但我们仍然面临着从计算机发展初期就一直存在的基础数据库难题——那就是，如果我搜索一个……

<details>
<summary>Original English</summary>

**Speaker**: So this whole platform is actually to make a very simple statement very obvious, which is: we can have the smartest models in the world, we can hit some crazy cool piece of technology, but we still have the same database problems that we've had from the beginning, which are: I cannot if I search through a...

</details>

<!-- chunk 35/51 -->

### 构建值得信赖的 AI 基础设施

**Speaker A**：……行与列中不存在该值，我就无法检索到结果。我们现在已经走出了 AI 的纯搜索阶段。我们现在需要构建基础设施。我们需要去构建脚手架（scaffolding）、测试与控制载体（harnesses）、运行底座（substrates），或者不论风投圈（VC）最近流行叫什么炫酷的词汇，也就是那些真正能让我们把这项技术应用起来的基础设施。所以，这是我向在座各位提出的挑战与期望。我希望大家能走出去，做出令人瞩目的成果，但我更希望你们构建出的是真正值得信赖、令人信服的东西。谢谢大家。

<details>
<summary>Original English</summary>

**Speaker A**: ...row and that column that value doesn't exist, I won't get a retrieval back. We're now out of the search phase of AI. We need to be building infrastructure. We need to be building scaffolding and harnesses and substrates or whatever the cool VC term is these days that actually enable us to make use of this technology. So this is my challenge and my ask to all of you. I hope you go out there and build something compelling, but I hope you build something compelling that you can trust. Thank you.

</details>

### 从聊天框到自主数字员工

**Philip**：有人要提问吗？喂，试音，试音。好的。大家好，我叫 Philip。今天是 Gemini 4 发布的第二天。那么在座的各位有谁已经尝试过这个新模型了吗？能举下手吗？好的，举手的人还不够多。所以大家稍后一定要抽出时间去试一试。它真的很优秀。在我们接下来的演讲中，我们也会使用并展示它。

今天我们将一起探讨如何构建并编写属于你自己的华尔街自主数字同事（autonomous Wall Street co-workers）。希望在座有很多金融从业人员，或者是从事金融相关工程开发的工程师。

在深入展开之前，我们先快速回顾一下整个演进历程：大约两年前，我们面对的基本只是一个简单的聊天对话框（chat box）。我们向它提出一些简单的问题，比如“法国的首都在哪里”、“上一届欧洲杯冠军是谁”。随后，我们逐步迈向了辅助工具阶段（assistants），AI 开始在我们的电脑上调用各种工具，第一批编程智能体（coding agents）也应运而生，替我们编写代码。而现在，我们正在跨入这种“自主数字员工”（autonomous co-worker）的全新时代——我们基本上是在创造并交付一个真正的数字雇员：我们给智能体配备独立的计算机环境，交给它一项任务，几个小时后再回来看，就能拿到令人满意的结果。

<details>
<summary>Original English</summary>

**Philip**: Anybody? Hey. Heat. Heat. Okay. So, hi everyone. My name is Philip and I work at... second Gemini 4 day. So, who of you already tried the new model? Can you raise your hands? Okay, that's not enough. So you should definitely take your time later try it. It is really good. We are going to use it and show it in our talk as well.

So we are going to look at how you can build and code your own autonomous Wall Street co-workers. So hopefully we have many finance people or like engineers working in finance here.

So quickly before we go into like right where we are coming from: two years ago we basically had a chat box. We asked some simple question like what's the capital of France, like who won the last European championship. Then we moved to assistance using tools on our own computer, having the first coding agents writing code for us, and now we are moving into like this autonomous co-worker area where we basically give and or create a digital employee where we give an agent its own computer, give it a task, and hopefully come back a few hours later with a good result.

</details>

### 数字员工的核心组成要素

**Philip**：那么，一名正常的同事通常需要具备什么？我认为这对 AI 和对我们人类员工来说都是一样的：
1. 我们需要一个**大脑**来完成工作；
2. 我们需要一台**电脑**，在上面保存我们创造的工件（artifacts），并在上面进行迭代；
3. 我们需要某种**工作手册（playbook）**——当你招募新员工时，他们对你的业务环境和领域并不熟悉，你可能会有特定的工作流程，因此必须配备操作手册；
4. 我们需要配备**工具**，让他们能够履行岗位职责；
5. 他们都需要通过某种方式获得相应的**凭证与权限（credentials）**；
6. 团队通常还需要建立明确的**内部规则（house rules）**，规范什么该做、什么不该做、哪些事项可以自主决定、哪些环节必须报批；
7. 当然，最好还要有明确的**工时排期（schedules）**，规定何时到岗或何时执行工作。

对于我们的智能体来说，道理是完全相通的。在今天的演讲中，我们将详细拆解这七个步骤，展示如何借助 Gemini 构建属于你自己的数字员工。

<details>
<summary>Original English</summary>

**Philip**: So what does a coworker normally need? And I think that goes for AI and for us humans as well. We need a brain to be able to do our work. We need a computer where we can save artifacts we create, where we can iterate. We need some kind of a new playbook, right? When you hire someone new, they are new to your environment, to your domain. You might have specific workflows. So you need playbooks. We need tools for them to be able to do that job. They all need credentials in one or the other way. Then there might be some specific house rules on what you should do or what you should not do, what you can do on your own or where you need to get some approvals. And then of course there are hopefully some schedules for working hours when you can come in or when you have to work. And the same goes for our agents. So and we are going to work through all of those seven steps and how you can build your own digital co-worker with Gemini in this talk.

</details>

### Gemini 4 Argon 的突破与内部实践

**Philip**：不过在深入讲架构之前，昨天是一个重大的日子。我们正式宣布了 Gemini 4 Argon 并将其开放给各位使用。其中最重大的新特性在于，我们现在拥有了 100 万 token 的统一上下文窗口（unified context window）。这意味着 Gemini 能够生成高达 100 万的输出 token。我们看到了显著的性能提升，特别是在数学和推理任务上，模型现在拥有超过 64k 的 token 空间去充分“思考”、推导演算并证明复杂的数学问题。

另外非常值得一提的是，我们对这个模型进行了极其严苛的测试。我们知道外界总有一种看法，觉得“Gemini 只是在基准测试（benchmarks）上跑分好看而已”，但这个模型是真的非常出色，大家绝对应该亲自尝试一下。我们在 Google 内部已经对其进行了大规模的使用，Google 员工已经在许多项目中落地了它。

最简单的上手方式是使用 Interactions API。你只需要调用四行代码即可搞定。你可以在 AI Studio（aistudio.com/apikey）获取你的 API 密钥，然后立刻就能发起请求。作为一款前沿模型（Frontier model），它的定价也相当亲民，输入每百万 token 为 2 美元，输出为 10 美元。如果你稍后有空闲时间，或者哪怕你手头正有运行中的智能体，我都强烈建议你给它换上链接，告诉它“请帮我接入 Gemini 4”并实际体验一下。

那么，Google 内部人员目前用这个模型做出了什么成果呢？我认为非常震撼，毕竟它是一个崭新的模型。虽然我们在内部已经提前测试了几周，但内部员工的使用程度极高，并且交付了大量令人惊叹的项目：
- Chrome 团队利用它大幅加速了 Chromium 浏览器的解耦重构工作；
- 我们的开源模型 Gemma 团队，借助 Gemini 加速了优化，让 Gemma 能够更轻松、更高效地运行；
- 来自 Cloud 部门的 ADK 团队借此完善了他们的框架体系；
- 还有许许多多的其他项目。尤其是最右下方的一点：我们在 Google 内部重度依赖它，在我们自己的内部代码库中也看到了巨大的提效。

关于人们构建的应用，社区里已经有一些演示 demo 大家可以去检索查看，但这里我想特别展示一位同事的成果：他纯粹通过提示词让 Gemini 在 Python 中从零编写了一个定制的 3D 光线追踪器（3D ray tracer），完全由 Gemini 生成，没有借助任何外部工具，最终就是纯 Python 代码；他还结合了 Gemini TTS 语音模型和 LoRA 添加了旁白解说来解释其运作原理。能将这些模型推到如此高度，对我来说真的非常令人惊叹。所以大家一定要保持雄心，大胆探索。

<details>
<summary>Original English</summary>

**Philip**: But before we go in, yesterday was the big day. We announced Gemini 4 Argon and made it available to you. Biggest new features: we have now 1 million unified context window. This means Gemini can generate up to 1 million output tokens. And we see strong improvements especially on math and reasoning task where the model now has more than 64k token available to think, to work through, to reason through some proofs and for math. And then also very good is like we tested that model heavily. So we know there are always some thinking around "hey Gemini is just benchmarks", but the model is really good. You should definitely give it a try. We used it extensively at Google. There are already many projects by Google employees who have used it.

The easiest way to get started is the interactions API. It's literally four lines of code which for you to take. You get your API key in AI studio (aistudio.com/apikey) and then you can immediately send your request. It's also, I would say, quite affordable for Frontier model with $2 in and $10 out. You should definitely try if you have a free minute later or even if you have some agents running right now, give it a link, tell it, "hey, please set up Gemini 4" and give it a try.

So, what have Googlers done so far with the model? I think it's very impressive because it's like a super new model. We had it available internally to test for a few weeks already, but Googlers are using it so heavily and like shipping so many cool things. We had the Chrome team like basically accelerating some decoupling of the chromium browser. We have Gemma which is our open model where Gemini accelerated Gemma to be more easily and more efficient to run. The ADK team from cloud improved their framework, and then many many other things, and especially the right one at the bottom is like we use it internally heavily and we see strong improvements for our internal code base as well.

So what have people built? There are some demos you can look them up, but there's one specific one from a colleague of mine which I want to show. He basically prompted Gemini to build a custom 3D ray tracer in Python and it was completely built from Gemini and nothing external tools and at the end just Python, and it also used Gemini TTS model and LoRA to add some voice over to explain how it works, and it's like very impressive for me how far we can push those models now. So try to be very ambitious.

</details>

### 借助托管智能体（Managed Agents）构建 Buck

**Philip**：那么，我们该如何构建自己的智能体呢？在 Gemini API 中，我们提供了一个名为 Managed Agents（托管智能体）的产品。托管智能体本质上是为你构建远程智能体提供的一种极简方案——你给 Gemini 提供一个可以执行工具调用的沙箱环境（sandbox）。

通常我们在构建智能体时，往往需要处理复杂的工具调用循环（tool calling loop）：我们向模型发送请求，模型生成 JSON 格式的函数调用（function call），我们在自己的机器上接收该调用，在本机执行代码，然后再把结果回传给模型。而在托管智能体中，我们直接提供了一个安全的沙箱，Gemini 可以直接在沙箱内部执行所有这些调用。如果它决定运行代码或写入文件，它拥有完全属于自己的专属计算环境，而这一切仅需一次 API 调用即可触发。

调用时，你不需要传入普通的 Gemini 4 Argon 模型 ID，而是直接传入智能体 ID（在当前示例中为 `anti-gravity-preview-09`），输入提示词，并将环境指定为 remote（远程托管沙箱），这就完成了全部设置。

现在让我们开始动手构建 Buck。Buck 就是我们今天的数字化同事。Buck 需要一个大脑——大脑就是 Gemini；我们的计算机环境则是智能体沙箱，此外还需要配套其他所有要素。

在托管智能体中，你可以通过一套非常简洁的 API 来定义自己的智能体：
1. **ID**：指定唯一标识符，也就是后续调用该智能体时使用的名称；
2. **Base Agent（基础智能体）**：底层依赖的核心架构。在当前案例中是 Agent Harness（智能体载体）。远程智能体复用了与 Antigravity 完全相同的 Agent Harness，因此如果你平时使用 Antigravity 作为编程智能体，在远程端获得的是完全一致的运行时支持；
3. **Model**：指定我们要采用的新模型；
4. **System Instruction**：定义系统指令。

要调用它，同样只需通过 Interactions API 调用 create 方法；此时不再使用基础 Gemini 模型 ID 或默认智能体，而是直接指定我们自定义的智能体 Buck。

我们的智能体需要一台计算机，而这台计算机通常需要一些额外的文件和配套的脚手架支持。通过 Managed Agents，你可以直接提供技能定义（skills），或者直接挂载来自 GitHub 仓库的 `AGENTS.md` 文件。你可以直接内联传入这些文件，也可以挂载包含专属技能的私有或公开 GitHub 仓库，甚至可以连接 GCS（Google Cloud Storage）存储桶。这样你就能直接为智能体即将开展工作的环境完成初始化引导（bootstrap）。

在托管智能体中，一切事物都以文件的形式存在：技能是文件，钩子（hooks）是文件，系统指令也是文件。归根结底，它就是一个文件系统，是属于智能体自己的计算机环境。当智能体认为需要自我提升时，它可以在上面编写并生成新技能；它也可以在上面持久化保存之前会话沉淀的记忆或经验教训。说到底，我们就是在与文件打交道。

而对于知识（knowledge）或智能体所需的信息，我喜欢将其划分为三个不同的层级类别：
首先是每次请求都必须包含的知识，这通常对应系统指令（System Instructions）。在编写这部分时，我们要尽可能保持精炼克制，尽量写得简短，因为这部分 token 成本会在每一次交互请求中被反复计费。如果系统指令过于冗长，所有的请求都会变得……

<details>
<summary>Original English</summary>

**Philip**: So how can we build our agent? And in Gemini API, we have a product called managed agents. And managed agent is basically a simple way for you to build a remote agent where you give Gemini a sandbox which it can use to run tools.

So when we normally build an agent, we have this weird tool calling loop, right? We send a request to the model. The model might generate a JSON function call. We receive that function call. We run that function call on our machine, execute the code and then we go back to the model. And with managed agents we basically provide a sandbox which Gemini can directly use to run all of those calls. So if it decides to execute code to write a file, it has its own computer available for it to use and it takes just an API call. So instead of providing the model ID with Gemini 4 argon, you provide the agent ID. In this case, it's anti-gravity preview 09. Give it a prompt. The environment is remote. So you want to run it in the managed sandbox and that's all it takes.

So let's get into building Buck. Buck is our coworker for today. And Buck needs a brain. Our brain is going to be Gemini. Our computer is going to be agents. And then we all have all of the other things.

So how can you create an agent? In managed agents, you have a very simple API where you can define your own agent. So you give it an ID. That's the name which you're going to use later to call the agent. We have the base agent. So that's the main agent underlying. In this case, it's the agent harness. So the remote agent uses the same managed — sorry, the same agent harness which we have in anti-gravity as well. So if you are using anti-gravity as your coding agent, you get the same agent harness remotely. Then we want to use the new model. So we define our model. We have a system instruction and then all it takes to call it again interactions API create and instead of using the model ID for Gemini or the default agent we use our own agent Buck.

And our agent needs a computer and the computer normally needs some additional files additional scaffolding. So with managed agents you can provide your skills or an agents MD file maybe from your GitHub repository. You can inline those files directly. You can provide a GitHub repository private or public with your skills and you can connect GCS bucket. So you can already bootstrap the environment the agent is going to work in and everything in managed agent lives as a file. So we have skills, we have hooks, we have system instructions. At the end it's just a file system or the agent's own computer where it can create new skills if it thinks it needs to improve itself where it can store memories from previous sessions or learning. So at the end we just work with files.

And for knowledge or for our agent I like to separate those in like three different categories. So we have knowledge which we always need to include into every request. That's normally the system instructions. We want to be very concise. We want to try to keep it very short because that's something we need to pay on every request. So if we have very long system instructions, all of our requests are...

</details>

<!-- chunk 36/51 -->

### 技能设计的上下文解耦与按需加载

**Speaker**: 成本会变得高昂得多。如果我们保持内容精炼，那么我们所拥有的知识，智能体就可以自行决定何时需要使用它们、何时不需要使用。通常对于“技能（skills）”来说正是如此，对吧？对于技能，我们提供非常简短的描述，这为智能体提供了一些指引，比如：“嘿，如果用户想要执行某项特定任务，或者如果你必须执行某项特定任务，你就可以使用该技能”，随后智能体便能读取该技能的详细内容。

<details>
<summary>Original English</summary>

**Speaker**: going to be much more expensive. If we have concise, then we have knowledge which the agent can decide when it needs to use them or not. So that's typically with skills, right? With skills, we have very short descriptions which give the agent some guidance on like hey you can use that skill if the user wants to do a certain task or if you have to do certain task and then the agent can read that skill.

</details>

**Speaker**: 但对于技能本身，我们也希望确保不会塞入超级冗长、极其密集的内容，因为归根结底这同样会带来高昂的开销。对我们而言，上下文是非常宝贵的。因此，我们希望将它们解耦，切分成更细致的分片；这样一来，如果我们希望智能体执行某些需要更多上下文的特定事务，我们就可以提供专门的参考文档和脚本。

<details>
<summary>Original English</summary>

**Speaker**: But for skills we also want to make sure that we are not having a super long dense skills because that's also a high cost at the end. Context is very valuable for us. So we want to decouple them and separate them into much more slices where we can then have like dedicated references and scripts if we want the agent to like do very certain things where it needs more context.

</details>

**Speaker**: 好的，那么让我们来看一个我们即将使用的技能示例。这里我们有一个投资组合审计（portfolio audit）技能供智能体调用。其中包含了一些供它参考的运行指令。我们提供了一个智能体可以执行的 Python 脚本，并附带了一些补充信息，说明它拿到结果后需要做什么以及将数据存储在哪里。

<details>
<summary>Original English</summary>

**Speaker**: Okay. So let's look at an example skill which we are going to use. So we have a portfolio audit. The agent should use it. It has some instructions available for it how to run it. So we have a Python script the agent can run and then some additional information on what it needs to do with the results and where to store it.

</details>

### 工具集成与托管智能体的安全凭证机制

**Speaker**: 接下来是我们为数字员工进行入职配置的第四个组成部分——工具。作为人类，我们日常使用的是常规软件；而对于智能体来说，工具可以是内置技能（如 Google 搜索、代码执行），也可以是 MCP（模型上下文协议）服务器。或者，如果你没有 MCP 服务器，而是希望编写本地自定义函数，那也是完全可行的。因此在托管智能体（Managed Agents）中，我们在创建智能体时对其进行了扩展，以定义我们的工具集。Gemini API 已经提供了用于 Google 搜索的内置工具，因此你无需做任何额外工作即可直接集成 Google 搜索。

<details>
<summary>Original English</summary>

**Speaker**: Our fourth part of our onboarding for our co-workers: tools. Right, we humans use normal software; for agents that's either built-in skills like Google search, code executions, or MCP server, or if you don't have an MCP server and rather want to write a local function, that's also possible. So managed agents we still have our agents create, we are now extending it to define our tools. We have built-in tools from the Gemini API for Google search. So there's nothing you need to additionally do to get Google search integrated.

</details>

**Speaker**: 但如果你想使用电子表格等服务，Workspace 现在已经为 Gmail 和电子表格提供了可用的 MCP 服务器。我们可以直接使用它；或者如果你想提供自己的函数或专属 MCP 服务器，也是支持的。针对自定义函数，其运作方式与你平时在模型中所做的完全一致：智能体生成函数调用请求，然后你将函数执行结果回传给它。从本质上讲，这为你提供了一种在智能体运行环境和计算沙箱之外赋予其 Agentic 能力的途径。因此，如果你想执行某些不应在沙箱内部运行的操作，这就是一种理想的实现方式。

<details>
<summary>Original English</summary>

**Speaker**: But if you want to use for example spreadsheets, Workspace has now an MCP server available for Gmail, for spreadsheets. So we can use that, or if you want to provide your own functions or MCP server that's also possible. So for your own function, it still works the same way as you normally do with models. So the agent creates a function call and then you send back the functional result. So it's basically for you a way to have agentic capabilities outside of these agents' environment and computer. So if you want to do certain things where the agent should not run the execution in the sandbox, that's a way for you to do it.

</details>

**Speaker**: 接下来是登录凭证。我认为对我来说，这是托管智能体 API 中最令人兴奋、最亮眼的功能特性。因为在智能体系统中，凭证管理极其棘手，而且非常容易出现安全失误。上一场演讲其实也提到了，大家在使用智能体时都格外谨慎，因为稍有不慎事情就可能出大乱子。我们在设计托管智能体时对此进行了深入考量，我们支持三种不同的凭证配置方式，从而使你的智能体能够在隔离环境下安全地使用它们。

<details>
<summary>Original English</summary>

**Speaker**: And then we are login. And I think that's for me the most exciting and the greatest feature about the Managed Agents API because credentials are super hard and super easy to get wrong with agents. And I think the previous talk already also mentioned that we are very careful about using agent because things could go wrong very easily, and we thought a lot about this with managed agents, and we have support for three different ways of credentials which makes it secure for your agent to use them and provide an isolated way.

</details>

### 网络代理与只写凭证注入安全架构

**Speaker**: 我们支持常规 API 调用中常见的 Bearer Token（如果你从事软件工程，对此一定非常熟悉）；我们支持面向各类消费者端 MCP 服务器或外部工具的 OAuth；当然，如果我们想要使用某些 CLI 工具或其他特性，环境变量也是必不可少的。而在托管智能体中，我们通过外部网络代理将这些凭证彻底分离开来。

<details>
<summary>Original English</summary>

**Speaker**: So we have Bearer tokens for normal API calls, very familiar if you are doing software engineering. We have OAuth for all of the consumer-oriented MCP servers or like tools, and then of course we need environment variables if we want to use certain CLIs or other features. And for managed agents we are separating them via an external network proxy.

</details>

**Speaker**: 换句话说，我们不会将明文凭证直接放入沙箱内部提供给智能体，而是允许你在外部创建这些凭证。这些凭证是“只写（write-only）”的。也就是说，一旦写入系统，你就没有任何途径重新读取或检视这些凭证内容，你只能去覆盖更新它们。这样就从根本上杜绝了凭证泄露的可能性。接着，你可以精确定义这些凭证应该在何时何地被使用。

<details>
<summary>Original English</summary>

**Speaker**: So instead of providing the agent the credentials inside the sandbox, we basically allow you to create credentials externally. They are write-only. So once they are written, there's no way for you to retrieve the credentials. So you can only override them. So there's no possibility of leaking. And then you define how and where those credentials should be used.

</details>

**Speaker**: 以 Slack 为例，如果你想要连接 Slack，你可以这样定义：“嘿，这里有一个凭证，但你只能在请求特定域名或特定环境变量时使用该凭证。”通过这种方式，你可以完全掌控凭证的具体调用时机。这一切都是通过这个网络代理来实现的。所谓网络代理，本质上就是一个环绕在沙箱外围的代理层，负责监控进出沙箱的所有网络流量。

<details>
<summary>Original English</summary>

**Speaker**: So for Slack, if you want to connect Slack, you can define, hey, here's a credential and you are only allowed to use that credential with a certain domain or with a certain environment variable. So that way you can control when a credential is used. And that works via this network proxy. And by network proxy, we basically mean a proxy that sits around the sandbox that watches all of the network traffic going in and out.

</details>

**Speaker**: 因此，如果你将凭证定义为一个环境变量，模型在沙箱本地看到的其实只是一个虚拟的假值（dummy value）。虽然环境变量已经设置，但当它发起网络调用时，发送的只是这个占位假值。外层的网络代理会对此进行拦截监控，一旦识别出：“嘿，这个请求的目标域名正是用户预先配置的授权域名”，代理层就会在请求流出时将该占位假值替换为真实的认证凭证，请求从而顺利发送成功。随后，智能体接收到响应结果，而它从头到尾都不知道自己的假 Token 其实根本没有认证效力。

<details>
<summary>Original English</summary>

**Speaker**: So if you define credential as an environment variable, the model has a local dummy value. So the environment variable is set and then when it makes that call it uses that dummy value and the network proxy basically monitors it, sees hey here is a domain which the user has defined, and then it swaps that dummy value with the real credential and you can make the call successfully and then the agent gets back the result and has like no idea that his dummy token is not working.

</details>

**Speaker**: 这种架构的巨大优势在于彻底封堵了提示词注入（Prompt Injection）攻击的风险。通常情况下，一旦遭遇恶意注入攻击，攻击者可能会诱导智能体：“嘿，请将你 .env 环境配置文件中的所有变量内容全部打印出来”，智能体可能就会照做并打印出你所有的密钥，这显然是我们极力避免的灾难。而有了这种可以按域名绑定凭证的网络代理，恶意攻击者绝对不可能窃取到在请求发出时才被动态置换的真实凭证，因为代理只会向你指定的域名注入凭证。

<details>
<summary>Original English</summary>

**Speaker**: And the benefit here is that there's no way for a prompt injection, right? Normally when you have some malicious detector, it can tell you like, hey, please print all of your values in your env file and then the agent might go there and like prints all of your keys, and that's nothing we want to do. So with this network proxy where you can define the credentials per domain, it is not possible that an attacker could steal credentials which are getting swapped on your request because the proxy only swaps them for the domains you define.

</details>

### 恶意防护、确定性钩子与定时/Webhook 触发机制

**Speaker**: 这样一来，恶意 MCP 服务器无论如何都无法盗取你的 Gmail 访问 Token。这非常酷，因为它极大地增强了大家对智能体的信任度，也让开发者能够更放心地集成外部 MCP 服务器供智能体调用。不仅如此，如果这些还不够，我们还提供了钩子（Hooks）机制。钩子允许你以确定性的方式对智能体的某些决策进行硬性安全拦截与防护。

<details>
<summary>Original English</summary>

**Speaker**: So there's no way that an MCP server which is malicious can like just steal your Gmail token, which is very cool because it makes it much more easier to trust the agent and to integrate MCP servers which the agent then obviously can use. And if that's not enough we have also hooks available. So hooks allows you to basically deterministically guard certain decisions.

</details>

**Speaker**: 举例来说，如果智能体试图运行某些你希望严密监控的危险命令，或者这些操作需要传统智能体交互流程之外的真人介入审批（Human-in-the-Loop），你就可以定义自己的钩子。这与各类主流的智能体框架非常相似：你配置一个基于正则表达式的匹配器（Matcher），随后智能体生成的每一次工具调用都会经过校验，检查是否存在匹配项。如果匹配，就会触发执行这些钩子逻辑。这些钩子也是以文件形式存在的，但它们是受写保护的，因此智能体绝不可能自行修改钩子文件来设法规避安全限制。

<details>
<summary>Original English</summary>

**Speaker**: So if the agent wants to run certain commands which you might want to monitor or where you need some human in the loop approval which is not part of like the normal agentic conversation you can define your hooks very similar to all of the other agent harnesses where you have a matcher which is basically regex and then every tool call which the agent generates checks if there's a match and then it writes those hooks and those hooks are also files but they are protected. So the agent cannot just go there and changes a hook and basically tries to find a way around it.

</details>

**Speaker**: 好的。最后但同样重要的一点是，我们需要一种机制让智能体能够更加主动地行动。目前，我们支持一种基础的定时触发机制——Cron 触发器。你可以设定调度周期，比如每个月的每隔 30 天、在特定上午时间点，让智能体在完全相同的环境中携带指定输入自动运行某个触发任务，以执行尽职调查或自动化审计等工作。

<details>
<summary>Original English</summary>

**Speaker**: Okay. So last but not least, we need a way to get our agent more proactive. And currently we support one kind of triggers: basic cron triggers, which you can set up a schedule every 30 days a month at a.m. you want the agent to run a certain trigger with a certain input in the same environment to do maybe some due diligence, some auditing.

</details>

**Speaker**: 与此同时，我们也在积极开发 Webhook 触发支持，从而让系统具备更强的交互响应能力。你可以接入外部系统的 Webhook 事件，例如来自某个特定 SaaS 服务商或其他合作供应商的事件回调，直接触发你的智能体执行任务。智能体完成初步审计后，甚至可以直接向你的 Slack 频道或 Microsoft Teams 发送通知，整个过程完全不需要你亲自管理任何底层基础设施。

<details>
<summary>Original English</summary>

**Speaker**: And we are also working on web hooks that you can even like make this much more interactive that you could connect external web hooks like from some certain SaaS provider or maybe other providers you work together with which would directly then call your agent. The agent does some first auditing and then basically can call your Slack or your Microsoft Teams directly without you even needing to manage some infrastructure at all.

</details>

### 实机演示：基于触发器与技能的自动化表格审计

**Speaker**: 这就是整个架构的完整全貌。现在让我们来看一些真实的现场演示，希望现场的 Wi-Fi 信号足够给力。我之前告诉 Gemini 我想做一个炫酷的 Google 表格演示，它便帮我在浏览器中完整复刻了这套 Google 表格交互界面。

<details>
<summary>Original English</summary>

**Speaker**: So that's that final picture, and now let's look at some real demos and let's hopefully hope that the Wi-Fi is good enough. So I told Gemini that I want to do a cool Google Sheets demo and it helped me create basically this whole Google Sheets replication in my browser.

</details>

**Speaker**: 当我点击这里时，我们基本上就是在模拟这个定时调度触发器。我们向托管智能体发送一个真实的 API 调用请求。它应当调用我们的投资组合审计技能并执行该请求。第一步通常是先读取技能定义，获取返回结果，进而理解自己在这里需要完成的任务。我希望它与实际 Google 表格中的操作大致准确。

<details>
<summary>Original English</summary>

**Speaker**: And when I click here, we basically simulate this cron trigger. So we send a real API call to managed agents. It should use our portfolio auditing skill and it runs the request. So first step basically is see like hey I need to read the skill. It gets the result back. So it tries to understand what it should do here. I hope that's roughly accurate on like the Google Sheets.

</details>

**Speaker**: 接下来，它会遍历所有这些调用，调用金融数据服务，尝试核实市场大盘走势或股票价格是否发生了变动。最后，期望它能够完全自动化地更新我们自己的 Google 表格。此时它依然在后台逐步处理，目前已经拿到了初步结果，并且正在基于该触发事件自动更新表格内容。而这一触发器原本可以在每天上午 8:30 自动定时运行，完全不需要人工进行任何干预。

<details>
<summary>Original English</summary>

**Speaker**: But it basically runs through all of those calls, calls financial services, tries to see okay did the market or the stock price change and then at the end hopefully it should update our own Google Sheets completely automatically. So it's still working through it. It has some first result and it updates the Google sheet based on that trigger. And that trigger would run every 8:30 a.m. without you needing to do anything.

</details>

**Speaker**: 当然，如果该智能体拥有 Slack 的访问权限，它甚至可以直接在某个专门的交易频道中同步发布消息：“好的，哪些数据发生了变动？当前的最新状况是什么？具体是如何运行的？”在这里我们还有一个示例，我可以随时向 Spark 询问任何投资建议，希望这也能正常运转。这需要稍等片刻。正如你在另一个演示中所看到的，我们已经见证了所有这些能力。太棒了，非常完美。那么……

<details>
<summary>Original English</summary>

**Speaker**: And then of course if the agent has access to Slack, then it can even like post in some like specific trading channel. Okay, what changed? What is going on? How does it work? And here we have an example where I can just ask Spark any recommendation and hopefully this works as well. So it takes a little bit of time. You have seen in the other demo we have seen all of that. Oh perfect. So there there

</details>

<!-- chunk 37/51 -->

### 构建托管智能体环境与协作生态

**Speaker A**: 当前有三个职位。这是基于 Slack 讨论串的内容得出的。因此，它掌握了先前所有轮次的上下文，并且能够提供哪些内容发生了变动的信息，但归根结底，它仍然不会直接采取行动，而是严格依据你赋予的系统指令去执行。并且，运行该智能体所需的全部底层基础设施，都已完整内置于托管智能体环境（Managed Agents Environment）之中。这样一来，你就能以极低的门槛迅速上手，轻松将这些能力集成到日常使用的既有工具当中，提供所需的系统对接，从而立即开展工作。

<details>
<summary>Original English</summary>

**Speaker A**: ...are three positions. So that's based on like this Slack thread content. So it has all of the previous turns available and it provides the context of what changed, but it's still basically not taking actions based on the system instructions you gave, and all of the infrastructure you need to run that agent is part of the managed agents environment. So it's very easy for you to get started to integrate those into the tools you already use, provide the systems you need, and then get started.

</details>

**Speaker A**: 现在回到幻灯片。这就是我们所需的完整 AI 协作者（AI Coworker）能力，全部集成在单一服务中：我们有基础的 Gemini 模型，拥有配备托管智能体的计算机执行环境，还能为你在本地计算机上所使用的同一批智能体提供技能扩展。你可以直接调用各类工具，也能提供 MCP 服务器以接入外部服务和数据源。我们设计了一套安全的凭据管理机制，支持凭据的安全提供与轮换；我们配备了钩子（Hooks）来保护并执行特定的确定性业务逻辑；当然，我们还引入了触发器（Triggers），以便让系统更加主动地融入业务流中。非常感谢各位的聆听，希望大家都能尽快去“雇佣”自己的第一位 AI 协作者！谢谢大家！

<details>
<summary>Original English</summary>

**Speaker A**: So back to the slide. The whole coworker which we need in like one service: we have the plain Gemini, we have the computer with managed agents, we can provide skills for the same agents you use maybe on your local computer. You can use the tools, you can provide MCP server for external services and data providers to connect. We have a secure way for you to provide credentials, to rotate credentials. We have hooks to protect certain deterministic logic, and of course we have triggers to much more proactively integrate it into it. So thanks for listening, and hopefully go hire your first AI coworker.

</details>

### 企业世界模型与制度化记忆的缺失

**Jan Wenzel**: 好的，非常荣幸能来到这里。让我们再次为 AI Engineering 大会的所有组织者和工作人员鼓掌致谢，到目前为止，这真是一场极其卓越、精彩纷呈的盛会。谢谢大家！

<details>
<summary>Original English</summary>

**Jan Wenzel**: Okay. Pleasure to be here. Another round of applause for everyone at AI Engineering. This has been a really, really exceptional conference so far. Thank you.

</details>

**Jan Wenzel**: 好的。在开场时，我想先请大家在脑海中想一想你们公司里的某个人——就是那种似乎对公司的一切都了如指掌的人。他们经历过整整 17 次组织架构调整，通晓公司里所有的风吹草动、八卦内幕与组织政治，而且不知为何，他们似乎总能准确预判那些重大的战略举措最终会走向何方。实质上，这个人就是整个公司的“世界模型”（World Model）。然而，核心痛点在于：这样的人无法水平扩展，而且从来没有人会真正把他们口中所掌握的这些宝贵认知完整地记录下来。

<details>
<summary>Original English</summary>

**Jan Wenzel**: All right. So, I want to begin by asking you to think about that person in your company who just seems to know everything. They've been through 17 reorgs. They know all the gossip, all the politics, and somehow they always seem to predict what's going to come out of these big strategic moves. That person is a company's world model, essentially. And the problem is that they don't scale, and nobody really writes down what they say.

</details>

**Jan Wenzel**: 我是来自 Citadel Securities（城堡证券）的 Jan Wenzel。今天我将同大家探讨，我们是如何尝试利用一套智能体系统（Agentic System）来逼近并模拟出这种能力的。首先简单介绍一下城堡证券：我们从底层硬件芯片开始自研全套技术体系；在现阶段，我们超过三分之二的员工日常都编写代码。因此，我们自然而然地全面拥抱了 AI，并且智能体已经在整个机构内部为我们协助处理大量的日常事务。

<details>
<summary>Original English</summary>

**Jan Wenzel**: I'm Jan Wenzel with Citadel Securities, and I'm going to talk a little bit about how we try to approximate that with an agentic system. So a little bit about Citadel Securities: We build our own technology down to the silicon. At this point over two-thirds of our employees write code. So naturally we are completely AI-p[owered], and agents already help us with a lot of things at the organization.

</details>

### 战略的本质与工程化制度记忆层

**Jan Wenzel**: 随着应用的深入，领导层很自然地开始抛出有关宏观战略的深度问题：这些智能体执行脚手架在生成高质量代码方面确实非常出色，但它们是否真正有能力帮助我们定义、推演并持续完善公司的战略方向？这里我想借用我个人非常喜爱的一张来自 Tim Urban 的示意图。战略的本质归根结底其实就是三个核心问题：第一，我们目前身处何处？第二，接下来将会发生什么？第三，我们究竟是如何走到今天这一步的？要回答这其中的任何一个问题，智能体都必须对它所运转的这家企业拥有极其全面且丰富的全局画像与上下文理解。

<details>
<summary>Original English</summary>

**Jan Wenzel**: So naturally leadership started asking questions about strategy. These harnesses are really good at producing high quality code, but can they actually help define and refine the strategy of our company? So this is one of my favorite visuals I've borrowed from Tim Urban. Strategy really comes down to three questions, right? Where do we stand right now? What's going to happen next? And how did we get here? And to answer any of those questions, an agent has to have a really rich profile of the company that it's operating in.

</details>

**Jan Wenzel**: 因此，今天的演讲在宏观层面上探讨的是如何工程化构建一个“企业制度记忆层”（Institutional Memory Layer），我们可以暂且这样来称呼它。智能体必须全面掌握企业内部错综复杂的人际与组织关系，比如：原本紧密合作的两个团队，由于经历了一次重组而彼此不再直接沟通沟通；又或者某个项目背后的故事，为什么它的范围被反复修改和重订了数次；抑或是组织内部的权衡博弈——究竟是谁坐在会议室里？他们在公开场合说了什么，而私底下又有哪些话是没有直说的？

<details>
<summary>Original English</summary>

**Jan Wenzel**: So this is broadly a talk about engineering an institutional memory layer, let's call it that. The agents need to have information about relationships, right? Two teams that used to work together but no longer talk because there was a reorg; story and why it was rescoped several times; or the politics, right? Like who's in the room? What are they saying and what are they not saying?

</details>

### 自上而下与自下而上的数据融合：“西瓜项目”与噪声信号

**Jan Wenzel**: 获取这些信息通常有两条路径：一种是自上而下（Top-down），另一种是自下而上（Bottom-up）。自上而下的路径，包括各类演示汇报（Decks）、战略规划文档、会议纪要以及各类定期状态报告。这类材料通常结构规整、行文整洁，但它们带有独特的人为粉饰痕迹——人们往往倾向于将个人的主观思考、期望和粉饰意图融入其中，有时甚至是刻意包装。结果就会产生我常说的“西瓜项目”（Watermelon Projects）：表面看起来全是健康的绿色（一切正常），但切开内部其实早已是一片通红（危机四伏）。

<details>
<summary>Original English</summary>

**Jan Wenzel**: There's two ways in, right? There's top-down and there's bottom-up. Top-down, you have the decks, you have your strategy docs, your meeting and status reports, and they're tidy and they're pretty clean, but there's a unique human twist. People generally like to infuse their thoughts and opinions into these things, sometimes by design, so you end up with what I call watermelon projects, right? They're green on the outside and red on the inside.

</details>

**Jan Wenzel**: 而在底层的自下而上路径中，充斥着大量极为嘈杂的数据信息。这些信息虽然夹杂着极高的噪声，却出人意料地蕴含着巨量的真实信号，只是往往极难被挖掘提炼。这里包括散落各处的会议记录草稿、Slack 即时聊天记录、代码变更提交，甚至是你在日常开发中搭配所青睐的测试与开发脚手架运行时产生的会话追踪记录（Session Traces）。而世界模型正是这两类信息最终交汇融合的枢纽，所有的底层证据都需要在这个层面完成综合分析与提炼归纳。

<details>
<summary>Original English</summary>

**Jan Wenzel**: Then on the bottom you have the really noisy stuff which has a surprising amount of signal, but it's hard to uncover, right? You have meeting notes and you have Slack and code changes and even your session traces with your favorite harness. And the model is where they meet. The evidence is synthesized at that level.

</details>

### 借鉴机器人学：状态估计器在企业多模态数据中的应用

**Jan Wenzel**: 然而，单纯处理这些现实证据有时是非常棘手的，因为信息往往既残缺不全，又经常相互抵触或失真。但事实证明，在机器人学领域，其实早就存在应对此类困境的标准解决方案，那就是“状态估计器”（State Estimator）。其工作原理在于：系统内部会对所关注的某个目标状态维持一种先验信念（Belief）。随着时间的流逝，如果长时间没有观察到或接收到能够支撑该信念的新证据，系统对其信任度就会不断衰减，状态的不确定性就会逐渐扩散变模糊。直到你收到了一份新的演示文稿、一段讨论串或者一份会议记录，这种观测输入便会“坍缩”不确定性，为你提供全新的确凿证据，使你对其状态重获较高的确信度，进而在此基础上生成最新的状态更新。

<details>
<summary>Original English</summary>

**Jan Wenzel**: Now the evidence piece sometimes is problematic because it's either partial or wrong. But it turns out that in robotics you actually have the solution for this, and it's called a state estimator, right? What you do is you have some sort of belief about something you care about. And the longer it's been since you've seen or observed evidence that supports it, the less you trust it, right, the fuzzier it gets until you have a deck or some thread or some meeting note that sort of collapses that and you now have new evidence, right? And now you're more certain of it. And therefore, you produce the update.

</details>

**Jan Wenzel**: 当生成这样的状态更新时，我所关心的——或者说智能体应当密切关注的——核心要素主要有三个：第一，距离上一次接收到该方面的有效信号已经过去了多久？第二，这个信号究竟源自何处，它当前的权威性与可信度是否依然有效？第三，该信号在宏观层面上是否与其他传感器获取的数据相互印证与吻合？这其中与自动驾驶等领域的感知状态估计存在着极多的共通与平行之处，我稍后会再次回到这一点展开讨论。

<details>
<summary>Original English</summary>

**Jan Wenzel**: And the things that I care about when producing an update, or that the agent should care about, there's three things: There's how long has it been since some signal has been received? There's where did that signal come from and is it still trustworthy? And then does it broadly agree with other sensors, right? There's a lot of parallels here with like self-driving, for example, that I'll come back to.

</details>

**Jan Wenzel**: 那么，我们先从自上而下的最上层开始看起。举一个非常简单的具体案例：比如业务运营（BizOps）团队的一位同事制作了一份每月的项目进度报告幻灯片，核心问题在于，你该如何从这张幻灯片中自动提取出准确的结构化数据？在座的各位肯定有很多人亲自尝试过这项任务，它实际上具有极强的欺骗性与隐蔽陷阱。假设你尝试直接解析文件本身，解包 PowerPoint 文件提取底层的 XML 数据，你瞬间就会陷入一个极其有趣的哲学与概念难题——究竟什么是“绿色”？在企业调色盘和样式定义中，“绿色”对应的十六进制颜色代码（Hex Code）到底是哪一个？这种依赖规则脚本的提取方案很快就会在细节边界上走向崩溃。

<details>
<summary>Original English</summary>

**Jan Wenzel**: So let's start at the top, right? Like a very simple example is something like a slide that is produced already by someone in BizOps, and they produce a monthly status deck and the question is how do you get data out of this slide, right? Many of you I'm sure have tried that. It's deceptive, actually, right? Because let's say you try to parse the file, right, like you unpack the PowerPoint file and you get an XML, and all of a sudden you get into this really interesting conceptual question: what is green, right? What is the hex code for green? And things break down when it comes to this type of script.

</details>

**Jan Wenzel**: 面对这种情况，大家通常会想到的替代方案是：“那干脆对幻灯片直接截图，然后把图片扔给视觉多模态大模型来识别。”但到了这一步，即使截图的分辨率本身很高，你所面对的现实素材往往也是某位员工把另一张模糊的低清截图随手复制粘贴进幻灯片里的产物。最终的实际窘境，就变成让 Claude 这样的大模型拼命“眯起眼睛”费力辨别：图中模糊的小数字到底是个 31，还是个 81？因此，本次演讲的核心主旨其实在于：真正的优雅架构绝非盲目堆砌单一手段，而在于将多元信息交叉综合。在这个例子中，虽然逻辑看似基础，但只有当你将底层的原始 XML 结构与视觉模型的感知输出两相结合、协同验证时，你才能够复原出最真实的全局图景。

<details>
<summary>Original English</summary>

**Jan Wenzel**: Then the solution is to say, well, I'm just going to take a screenshot of it and throw it at a vision model. But at that point, even if it's like pretty high-res, you're dealing with someone who copy-pasted a screenshot back into a presentation and essentially you have Claude trying to squint and trying to figure out if it's a 31 or an 81. And so the theme of the talk really is about like elegance comes from just synthesizing things and adding more information. In this example, it's very basic, but you get the true picture by taking both the XML and the output of a vision model.

</details>

### 时间审计层与跨模态冲突：为什么传统 RAG 会失效

**Jan Wenzel**: 尽管这听起来十分基础，但真正的核心挑战在于：你必须在时间跨度上建立起持续的连贯性与前后追溯能力。企业在漫长的经营过程中沉淀下来的各类业务材料是随着时间动态累积且持续变化的。在这个特定案例中，某个核心项目在今年三月份毫无征兆地悄然更换了内部项目名称。如果你没有构建起一套能够跨时间持续追踪、可进行纵向因果审计的数据追踪层，就无法在不断演进的企业制度记忆之上维护起稳固一致的共享上下文图谱。

<details>
<summary>Original English</summary>

**Jan Wenzel**: Now, that's pretty basic, right? But the issue is that you want to establish some continuity over time, right? This collateral that your company accrues is very much sort of always building up. And so in this particular example, you have a project that just spontaneously changed names back in March. And so you have to establish that sort of longitudinal traceable audit layer as you create this shared context layer about the sort of institutional memory of your company.

</details>

**Jan Wenzel**: 这里的巨大讽刺在于两点。首先，哪怕你把上述工作做到了极致，你仍然只掌握了整个企业真实画卷的半幅面貌。当你正盯着一份精美的正式报告幻灯片时，Slack 里的即时交流可能完全是另一番景象——因为那份幻灯片是 5 天前整理的，而此时此刻正有人在 Slack 频道里发消息说：“对了，我认为我们这个项目正在按计划顺利推进。”然而紧接着，另一个人直接甩出来一张最新业务监控看板的实时截图，清清楚楚地证明进度已经被彻底阻断。各方信息就是这样开始土崩瓦解的。这正是因为我们必须更出色地将多源信息真正融合在一起，而绝大多数企业目前根本没有任何属于自己的完整动态运行模型。

<details>
<summary>Original English</summary>

**Jan Wenzel**: And the irony, there's two things. The irony here is that even if you do this really well, you're still missing half the picture, right? You're looking at a deck and your Slack says otherwise because that was 5 days ago, and now you have someone on Slack saying, "Hey, by the way, I think we're on track for this." But then someone replies with a picture of a dashboard and it's no longer the case. So things just start breaking down. And so we need to do a better job of integrating all these things, right? Your company has no model of itself.

</details>

**Jan Wenzel**: 因此，我在这里提出一个精简的闭环方案框架。其核心思想基于我前面阐述的针对状态估计器的关键环节：系统包含了“更新”（Update）、“时效老化衰减”（Age）、“多源观察”（Observe）三个基础状态，随后进入“评估”（Grade）阶段。评估阶段的本质，是将系统当前实际观测到的客观现实与先前的模型预测预期进行对照评分；最后则是“校正”（Correct）阶段，它实质上为人类员工提供了一条接入渠道，使业务人员能够向系统提供直接的反馈干预，从而牢牢引导并修正系统的长远行为偏差。在城堡证券，我们构建的这套体系在整个闭环的每一个节点都部署了专门的智能体。但至关重要的一点在于：智能体模型仅负责提出状态变更的提案与假设，而最终这些业务记录究竟该如何合并与更新，则由确定性的代码逻辑与人类专家共同裁定。

<details>
<summary>Original English</summary>

**Jan Wenzel**: So I'm proposing just a brief plan here. The idea is you take the three things that I described earlier about the state estimator: You have the update, age, and observe stages, and then you have grade. The grade stage is basically comparing what you've observed versus what you expected. And then the correct stage is basically a way for people to allow the system to get new feedback and steer the behavior of the system, right? At Citadel Securities, the system that we've built has agents at every part of this particular loop, right? But the key thing is that the model is proposing these changes, and then you have code and people deciding how the records are updated.

</details>

**Jan Wenzel**: 当然，听到这里你可能会在心里琢磨：“为什么不直接采用传统的检索增强生成（RAG）呢？用向量检索做 RAG 难道不够解决问题吗？”事实表明，传统 RAG 根本无法应对这种动态复杂局面。举个例子，如果我直接向系统提问：“请问这个项目的最新进展如何？是否仍在按既定计划推进？”如果系统依靠传统的 RAG 检索，到了 3 月 16 日这一天，模型很可能会高高兴兴地从数据库里检索抓取出几条看似相关的 Slack 聊天片段，然后……

<details>
<summary>Original English</summary>

**Jan Wenzel**: And of course, you're probably asking yourself like, why not just RAG, right? Like probably RAG would do the trick. And in fact, it really doesn't, right? In this example, I asked, "Hey, what's the status of this project? Is it on track?" And as of March 16th, some model would happily pick up a couple of Slack messages and...

</details>

<!-- chunk 38/51 -->

### 构建企业世界模型：纵向记录与增量更新

**主讲人**: 仅看几页幻灯片然后说：“对，这是绿灯状态。”但这其实遗漏了大量的上下文，对吧？光看这些是远远不够的。因此，下面介绍我们是如何开始构建这种“世界模型”（World Model）的。第一阶段的核心，在于持续且稳健地更新信息。在这个简单的例子中，我选取了一些演示文稿和幻灯片简报，我们基本上就是在做这样的事：你知道的，每个月周而复始，新的一月到来时，我们提取上个月的记录以及这个月的新幻灯片，尝试去构建一种纵向的时序记录（longitudinal record）。这项工作我们目前已经坚持做了三年，我们积累了一个相当庞大的此类历史记录数据库，如今它让我们能够构建起这种稳健的、所谓的机构级或企业级世界模型。

<details>
<summary>Original English</summary>

**Speaker**: some slides and say, "Yep, it's green." But it's missing a lot of the context, right? It's not enough. So here's how we start building this world model. The first stage is about updating information consistently and robustly. In this simple example where I'm taking some slides and some decks, we are basically just looking at, you know, every month, you know, new month comes around. We take last month's record and this month's slide and you try to construct a sort of longitudinal record, right? And we've been doing this now for three years, right? We have a pretty large historical database of these records that now allow us to construct this robust so-called institutional or enterprise world model.

</details>

**主讲人**: 你得从最基础的东西入手。有时候，这些模型在最基本的事情上都会犯难，但这些情况很常见：某个具体项目的实际名称可能会自发性地发生改变。但通过实际查看那一整套历史记录，模型能够看出来并推断出它实际上指的就是“北极星项目”（Project Northstar）——这是基于参与人员的重合度、目标类型的延续性等线索综合推断出来的。

<details>
<summary>Original English</summary>

**Speaker**: You start with the basics, right? Like, you know, sometimes these models struggle with the most basic things, but but they're normal, right? the the actual name of a of a particular project change spontaneously. But by actually looking at that historical set of records, it can see and infer that it actually refers to Project Northstar by virtue of who was involved, by virtue of some continuity in the types of goals, those kinds of things.

</details>

### 甄别汇报表象与实际证据

**主讲人**: 但更有意思的是，你真正想做的是让智能体系统（Agentic system）去鉴别“汇报上写了什么”与“支持其说法的实际证据”之间的差异。举个例子，你去看某个状态报告简报，智能体在这里识别出：虽然简报上标的是绿灯状态，但实际上它应该被标为黄灯预警，并且理应被旗标提示出来，因为有人在下面留了条评论，提到目前还有一个未解决的外部依赖项。

<details>
<summary>Original English</summary>

**Speaker**: But more interestingly, what you want to do is you have the Agentic system try to discriminate between what's being reported and actual evidence for what it's saying. So you look at some status deck for example and here it's identifying that while it is green on the deck in fact it should be highlighted as a yellow and should be flagged as such because there's a comment someone left talking about how there's a dependency still outstanding.

</details>

**主讲人**: 这里的关键原则是：你绝不要去修改前几个月的历史数据，而是像前馈机制一样向前自我修复。这样做的好处是，能让你在后续进行极其稳健的评测（evals）。所以，这就是实际更新步骤所写入的内容，非常简单明了：汇报的内容是什么；证据显示了什么、指向何处；以及得出该结论的原因是什么。

<details>
<summary>Original English</summary>

**Speaker**: The main thing here is that you don't touch previous months, right? You just sort of heal into sort of a feed forward mechanism. And what that allows you to do is to actually do some robust evals down the line, right? So here's what the actual update step writes. You know, very simple. This is what it was reported. This is how it, you know, the evidence, this is where the evidence points and this is why.

</details>

### 事实的半衰期与时效偏置

**主讲人**: 然后你再融入第二个维度：事实的时效性（age）。现实情况是，每一个既定事实都有其半衰期。我们都见过这种现象：你翻看过去的幻灯片，会发现某个具体项目的上线日期一推再推。1月份时写着第二季度上线，随后变成了第三季度，现在又推到了10月份，对吧？你是能实际观察到这种规律的。通过真正把所有这些数据收集起来，你就能开始获得一些非常有趣的分析洞察。

<details>
<summary>Original English</summary>

**Speaker**: And then you fold in the second component, age. The reality is every fact has a half-life. We've all seen, you know, you go back at some slides and you you see that the go live date for a particular project keeps slipping. It was Q2 in January, then it was Q3, now it's October, right? And you actually observe this, right? By by actually collecting all this data, you can have some pretty interesting beginnings of analytical insights.

</details>

**主讲人**: 例如，分析过去三年的交付日期，平均来看，有一半的交付日期会在两个月内发生变动；而在这些变动中，有高达 90% 都是延期至比原定提案更晚的时间。到目前为止一切顺利，这还挺基础的。但这迫使你必须引入一个概念：将具体日期与特定主张（claim）进行绑定关联。这样一来，当你向智能体询问某个具体项目、人员的状态或企业的战略意图时，智能体就能够引入某种时间近因偏置（recency bias）。

<details>
<summary>Original English</summary>

**Speaker**: For example, in the last 3 years, you look at these delivery dates and on average, half the delivery dates change within 2 months. And 90% of those change for into a date that is after what was originally proposed. Right? So far so good. Pretty basic. But what you what this forces you to do is then introduce this notion of like a date that it is associated to a particular claim. So that the agent can introduce some sort of recency bias when you ask about the status of a particular project person or or or the corporate intent let's say.

</details>

### 观察流程：告别粗暴端到端，设计专业智能体协作流

**主讲人**: 接下来是“观察”（observe）环节。这一部分我打算比较快速地带过，但我希望能给你们一些非常具有实操性的干货。刚开始的时候，直接采取“全抛给模型”（YOLO）的方式其实很有诱惑力——心想着干脆直接让 Claude 或者其他大模型把整个资料库囫囵吞下去，看看能出什么结果。但事实证明，这种做法显然会遗失大量的信息，它会缺失对细节的专注度。

<details>
<summary>Original English</summary>

**Speaker**: Then the observe section. the observe section here. I'm going to pretty quickly gloss over it, but I just kind of give you something very tactical. In the beginning, I was pretty seductive to just basically say, well, let's just yolo this. Let's have Claude or some other model take a look at the entire corpus of things and let's see what it does. And as it turns out, it's it's pretty clear that a lot of um information is is lost, right? It loses some attention to detail.

</details>

**主讲人**: 所以我们最终不得不做的是，精心设计一个精简的智能体协作工作流（agentic workflow）：由一系列专业智能体分工拆解这些资产资料，定向搜寻特定要素，再由其他智能体进行交叉审查等等。你们在右侧看到的结果表明，在采取这种架构之后，针对特定项目的有深度、见解深刻的更新数量实际上翻了一倍以上。因此，我认为这里的核心启示在于：在构建这些工作流时必须深思熟虑、有的放矢，千万不要盲目假设那种一股脑塞给模型的简易方式能够奏效。

<details>
<summary>Original English</summary>

**Speaker**: And so what ultimately we had to do was engineer a simple agentic workflow where you have a series of specialists break down the collateral of these assets, look for specific things, be reviewed by other agents and so on. And what you see here on the on the right hand side is that actually the amount of insightful updates to a particular project more than doubled after doing this. So, I guess the takeaway here is be intentional about how you how you build these workflows and don't just assume that a YOLO method is going to work out.

</details>

### 回溯测试与前瞻预警能力

**主讲人**: 但现在，我认为我们进入到了真正引人入胜的部分：一个真正的世界模型理应能够告诉你下一步会发生什么——哪一个项目即将延期，或者哪一个本月的绿灯项目会在下个月转为红灯。事实证明，你确实可以做到这一点。因为你能够回溯历史，建立某一个历史时间节点的快照，并在本质上运行回溯测试（back test）。

<details>
<summary>Original English</summary>

**Speaker**: But now you get, I think, to the really interesting stuff, right? A world model should tell you what happens next, what project is about to slip or which green turns red the next month. And it turns out that you can actually do this, right? Because you can look back and establish a snapshot as of some sort of past date and essentially run a back test.

</details>

**主讲人**: 举个例子，如果我们截取一份截止到 2 月份的快照，我们能够查看该节点之后的未来真实标签与后续进展，从而对比智能体当初预测哪些项目会延期或预警与后续实际发生情况的吻合度。你可以发现，随着智能体对所有这些信息进行深度分析，那些原本表面显示为绿灯但被智能体打上风险旗标的状态，其后续实际转为黄灯或红灯的概率足足高出了两倍。再次说明，这非常令人振奋，因为我们开始看到这种能力的雏形——尽管它还无法精确预测到底哪里会出问题，但至少它能够明确指出你应该把注意力放在哪里。

<details>
<summary>Original English</summary>

**Speaker**: So for example, if we take a snapshot as of February, we can look at the future labels, what came after that, and see and compare what the agent said was going to slip or flagged versus what actually happened. And you can see that as the agent um analyzes all this information that for statuses that were green but flagged, they were twice as likely to actually turn yellow or red. And so again, this is encouraging because we're starting to see some beginning of the inability to say, well, it's not predictive of exactly what's going to go wrong, but at least it should tell you what to look at.

</details>

### 人机协同闭环与反馈采集

**主讲人**: 接着就涉及到了这一环节：首先，你该如何构建一个非常优雅的闭环，把真实的用户、利益相关者、人类专家纳入其中？你该向他们提问什么？又该在哪里与他们产生触达？在探寻如何以最佳方式采集这些信息的过程中，我投入了相当多的心血。关键就在于“在用户日常所处的场景中去触达他们”——无论那是他们正在使用的特定应用、Slack 还是电子邮件等等。你与他们的交互距离越近，反馈采集机制设计得越轻量简便，整个流程的扩展性和健壮性就会越高。

<details>
<summary>Original English</summary>

**Speaker**: comes in. First of all, how do you incorporate a very elegant sort of loop where you include uh an actual user, a stakeholder, a human, and what do you ask them and where do you meet them? Right? I I put a non-trivial amount of work into finding out how best to actually capture this information. It's meeting the users where they are, whether it's the app they're using or Slack or email, whatever. And the closer you can get to them and the simpler you can make that feedback collection mechanism, the more scalable and and robust the process is going to be.

</details>

**主讲人**: 同时，你提问的内容也至关重要。你需要想清楚：你是在询问一个具体的事实（这只能修正某单一输出），还是在探寻一条规则？一旦智能体理解了背后的规则与模式，它在修正其覆盖范围内的所有输出时表现就会好得多——无论是在当下还是在未来。因此，我们现在的记录体系中包含的不仅有由智能体推断出的要素，更重要的是，还包含了在人工介入提供明确信号后予以确认的要素。

<details>
<summary>Original English</summary>

**Speaker**: It also matters what you ask, right? You want to understand whether like you're asking a fact which only fixes one output or if you're asking about a rule and once an agent understands that pattern, it does a much better job of fixing every output it covers both uh both now and into the future. So we have this notion now of our record containing not just an element of what was inferred by the agent but more importantly confirmed after someone actually provided that signal.

</details>

### 自下而上的多元数据源挖掘

**主讲人**: 好，现在我们来谈自下而上（bottom up）的数据路径。你有会议记录，那是极强的信号源，因为人们在会上公开直言；你有日常的 Slack 沟通，显然它连续不断、充满噪音，但也极其贴近真实状况；代码变更记录着具体交付上线了什么；当然还有智能体交互会话（Agent sessions），记录了整个方案的推演制造过程。我强烈鼓励大家去深入挖掘所有这些分散异构的数据源，来共同构建起这样一个世界模型。

<details>
<summary>Original English</summary>

**Speaker**: Okay, so now bottom up, right? You have meetings with, you know, really strong signal where people say out loud. You have your Slack. You obviously it's constant. It's noisy. It's very closer to truth. Code changes describe what shipped. And then of course the Asian sessions, which is how the sausage was made. And I think I encourage you all to explore all of these disperate data sources to kind of build such a model up.

</details>

**主讲人**: 处理 Slack 数据相对比较直截了当：你只需逐个分析对话线程（threads），根据附件、参与人员和正文内容，理出你希望智能体记录或更新的主张断言——包括时间节点、责任人或相关人员是谁、涉及哪个项目、支撑这一断言的证据链接是什么等等。对于 Pull Requests（PR），它当然清晰地展示了具体的代码改动，是观察项目如何演进演化的绝佳窗口。

<details>
<summary>Original English</summary>

**Speaker**: With Slack, it's relatively simple, right? like you're just looking at every thread and trying to understand based on attachments and participants and content the claims that you want the agent to record or update when was this, who was responsible or who does this relate to, um what project, what what's uh what is a sort of link to the evidence and so on. With PRs, of course, it shows you what changed and it's a really nice way to see how a project is evolving.

</details>

**主讲人**: 但是，当涉及到项目实际是如何推进与部署的那些细微机制时，查看那些选择加入追踪的用户和工程师的实际轨迹（traces）就会变得极为有趣。你能借此理解需求诉求最初是什么样子的、随着时间推移是如何演化的、遇到了哪些测试失败、或是开发人员做出了哪些具体的决策权衡。虽然所有这些最终都汇聚在 PR 中，但对全流程上下文的综合提炼往往能带来巨大的差异。

<details>
<summary>Original English</summary>

**Speaker**: But when it comes to the actual like subtleties of how projects are are sort of run and deployed, it's really interesting to look at the actual traces uh you know for users and engineers who opt into that right like you understand how the ask was how evolved over time test failures uh or you know particular decisions from the developer those kinds of things ultimately these culminate in a pull request but the synthesis of these things I think makes a big difference.

</details>

### 传感器信号有效性与静默陷阱

**主讲人**: 我还想分享另一个潜在的陷阱（gotcha）：请务必谨慎对待来自不同“传感器”（sensors）的信号有效性。举个例子，如果你正在公路上开车，仪表盘上的车速表突然黑屏失灵了，这绝不意味着你现在的车速变成了零，对吧？这单纯只是传感器信号故障而已。

<details>
<summary>Original English</summary>

**Speaker**: The other gotcha just I just want to share is to just be mindful of how you think about the validity of signal coming from different so-called sensors. If you're driving down a highway for example and your speedometer just you know just goes just disappears it doesn't mean you're now going at zero miles an hour right it's just like a faulty signal.

</details>

**主讲人**: 我们之前就遇到过几次回溯问题：在采用自下而上的方式时，系统监测到某种迹象主张——“某个特定渠道突然悄无声息了，这到底是怎么回事？”但在实际处理中，我们却直接把它当成了数值零来对待，而事实显然不应如此。因此，随着时间的推移，我们不断进行迭代优化，学会了如何把“最后一次尝试从该传感器获取信息的时间”、“该传感器最后一次处于正常状态的时间”等维度纳入考量，以及当这些信号发生背离时该如何应对。现在，纵观我们所构建起来的这套严密记录，智能体在处理这些复杂情境时将会变得有效得多……

<details>
<summary>Original English</summary>

**Speaker**: So for example here we ran into a couple of issues sometimes when the bottoms up approach you had some semblance of a claim saying hey this particular channel this thing is is going quiet what's going on but in reality you know we were treating it as a zero when really it shouldn't have been and so we sort of iterated over time to understand how to incorporate when we last tried to get information from that sensor when it was last okay and what do you do when these diverge. So now if you look at the actual record that we constructed, the agents are going to be much more effective in

</details>

<!-- chunk 39/51 -->

### 掌握真实状态与驱动领导层决策

**Juan**: 我们需要理解世界的真实状态，对吧？现状并不是一片大好的绿色，而是上线日期已经延期了两次，所有事实依据都指向了黄色预警状态。大家都在讨论测试失败的问题，接下来的推进势必会非常棘手。那么，我们构建这个系统究竟是为了什么？我们是用它来引导和把控领导层的对话。我们不再像以往那样，把一份 PPT 演示文稿分发给所有人，强迫大家硬着头皮去翻阅那些谁都会一眼带过的幻灯片；相反，你可以直接切入那些真正至关重要的核心议题。你可以直接从演示文稿所宣称的内容与实际证据出现分歧的地方切入。

<details>
<summary>Original English</summary>

**Juan**: Understanding the true state of the world, right? It's not green, right? The go-live slipped twice, the evidence says yellow. People are talking about failing tests. It's going to be tricky. So what do we use this for? Right? We use it to steer leadership conversations. Instead of, you know, circulating a deck to everyone and forcing everyone to just go through some slides everyone glosses over, you start with the stuff that actually, you know, matters. You start where the deck and the evidence disagree.

</details>

**Juan**: 你还可以为管理人员和领导团队生成一份每周动态解读，清晰指出哪些事项陷入了停滞，哪些项目逐渐没了声音。但我认为最重要的一点在于，你实际上构建起了一个最基础的上下文层，让每一个智能体都能够依赖并调用它。我们正在采用并打磨这一模式，使其具备高度的可扩展性，以便能够推广应用到各种不同的业务场景中，对吧？

<details>
<summary>Original English</summary>

**Juan**: You also produce a weekly read for managers and leaders on what stuck and what went quiet. But I think also most importantly, you have the sort of beginning of a context layer that every agent can rely on. And we're using this pattern and constructing it so that it's extendable to other different use cases, right?

</details>

### 上下文层向客户业务的拓展与未解难题

**Juan**: 例如在我们的客户业务分支中，我们非常想探索如何构建类似的模型来更好地服务我们的客户。我们面对着具体的客户，极度渴望弄清楚他们各自持有怎样的资产与头寸、他们到底对什么感兴趣，以及我们如何能够将来自各种内部与外部不同来源的信息融会贯通，从而尽可能精准地预测并满足他们的需求。

<details>
<summary>Original English</summary>

**Juan**: Right? In our client franchise, for example, we're curious about how we can build similar models to help serve our clients. We know we have some client and we want to understand who holds what. What are they interested in? How can we anticipate their needs as best as possible by folding in information from all sorts of disparate internal and external sources?

</details>

**Juan**: 所以这里有几个棘手的难题，或许会后我们可以在场外深入交流一下你们的解决方案，我个人非常渴望听听大家的思路。其中一个痛点是：当你面对同一个客户在四个不同的系统里拥有四条互不相通的记录，且完全没有全局通用的规范标识符时，你该如何以极其优雅的方式将它们映射并关联在一起？我认为目前我们还没有一个十分明晰的答案。

<details>
<summary>Original English</summary>

**Juan**: So, a couple of things that are difficult to do just to kind of maybe we can chat outside about your solutions. I'd be very curious to hear are when you have a lot of, you know, for example one client with four records and four different systems with no canonical identifier, how do you go about mapping those in a very elegant way? That's one thing that I don't think we have a clear answer to.

</details>

**Juan**: 第二个核心问题是：我们如何最有效地从利益相关者和最终用户那里捕获关键信号？当模型把握很大且风险后果较低时，你应该直接自动应用它的推断；当模型把握不足且后果较轻时，不妨耐心等待更多证据输入；但如果面对的是高风险决策，那么你在什么时候向谁发起求证，以及背后的整套确认机制该如何运作，就显得至关重要了。

<details>
<summary>Original English</summary>

**Juan**: The second thing is how can we be most effective at capturing signal from stakeholders and users? Where the model is sure and stakes are pretty low, you should just apply it automatically. When those stakes are—oh, but, you know, the model isn't sure, just wait for more evidence. But if the stakes are high, it really matters like who you ask, when you ask it, and kind of the whole mechanism there.

</details>

### 企业状态估计模型的核心闭环与三点收获

**Juan**: 所以我们再次回到这个闭环：更新、老化、观测、评估打分以及纠错校准（Update, age, observe, grade, and correct）。在此我希望大家能牢记三点核心心得。第一，你应该将贵公司所拥有的模型定位为一个“组织状态估计器”（state estimator）。千万不要以为只要把所有东西建立索引、编入目录就万事大吉了，因为从本质上讲，组织内部的信息极其微妙细腻，那些几乎存在于字里行间的内隐信息，即便对最先进的模型来说也是难以轻易捕获的。

<details>
<summary>Original English</summary>

**Juan**: So here's the loop again: update, age, observe, grade, and correct. And three things I want you to take home. The model that your company has, you should think about it as a state estimator, right? Don't assume that just like indexing everything and cataloging everything is enough, because by definition these things are extremely nuanced and this intrinsic information that lives almost between the lines is hard for even the best state-of-the-art models to capture.

</details>

**Juan**: 第二，必须对照后续发生的实际结果来对其进行评估打分。因此，从项目一开始就必须深思熟虑，有意识地构建并落实评估机制，设计出优雅的架构，让你们的模型、智能体以及人类利益相关者能够良性互动、紧密配合。

<details>
<summary>Original English</summary>

**Juan**: Grade it against what happens next. Right? So be intentional and think through how you can integrate and implement evals from the get-go and think about an elegant solution that allows your models and your agents and your stakeholders to kind of play nice together.

</details>

**Juan**: 第三，让你的企业拥有一个能够认知自身的内部模型。如果你现在还没有开始收集相关数据，我强烈建议你立刻行动起来。特别是如果你身处大型企业，且像我一样无论是幸运还是不幸地不得不每天面对成千上万份汇报 PPT，这绝对是你必须认真思考的事情。因为我已经切实看到了实质性的显著改善——这些智能体能够精准重建那种企业实体记忆，并将其顺畅运用到各类日常任务中，而不会陷入混乱与困惑。非常感谢大家！我是 Juan，稍后我会在场外解答大家的任何提问。谢谢！

<details>
<summary>Original English</summary>

**Juan**: So your company can have a model of itself. I encourage you to start collecting now if you're not collecting already. And certainly if you're at a bigger company and like me you had the, I mean fortune or misfortune of dealing with thousands of decks, definitely something you should start thinking about because I've definitely seen material improvements in how these agents are able to reconstruct that sort of corporate memory and apply it in all sorts of daily tasks without sort of being all confused about things. Okay, thank you very much. I'm Juan and I'll be outside for any questions if you want. Cheers.

</details>

### 从智能体进阶到企业组织级 AI

**Will Brown**: 大家好，近来可好？我是来自 Prime Intellect 的应用研究负责人 Will Brown。希望大家在本次 AI Engineer 大会上都过得愉快，这向来是我最喜欢的技术盛会之一。能亲眼目睹大家都在探索和构建些什么，感觉总是棒极了。我觉得这里是一个能让大家共同畅想未来图景、洞察行业最新趋势、见证各项进展以及探究哪些行得通、哪些走不通的前沿阵地。

<details>
<summary>Original English</summary>

**Will Brown**: Hey, how's it going? I'm Will Brown. I lead applied research at Prime Intellect, and hope you are all having a great AI Engineer Conference. This is always one of my favorites. It's always just so cool to see what everyone's working on and building. And I feel like it is a place where people get to talk about what the future looks like and like start seeing the trends in the industry and seeing the progress and what works and what doesn't.

</details>

**Will Brown**: 这正是我今天这场演讲想要探讨的主题：在我们当下所做的工作之上，下一步究竟会走向何方？我们一直在从事哪些研发？我们在不断涌现的研究成果中看到了哪些趋势，从而指引我们理解未来组织级 AI（AI at the organization level）的可能面貌？过去几个月乃至几年里，我们在智能体、人机界面、聊天机器人等领域见证了令人惊叹的进展。但技术永远在向前演进，变化发生得如此迅速，现在正是我们去构想、推演并为接下来的未来做好规划的激动人心的时刻。

<details>
<summary>Original English</summary>

**Will Brown**: And that's kind of the theme I want to think about for this talk today is like what comes next from what we're doing right now and what are some of the things that we've been working on and also just been seeing in research that's unfolding that kind of points at what we think the future of AI might look like at the organization level. Because we've seen a lot of very cool progress in agents and interfaces and bots and things like that over the past several months, years. But there's always more coming. Things are just moving so fast and I think it's a very exciting time to just imagine and speculate and plan for what comes next.

</details>

**Will Brown**: 不知道大家是否还记得，在 ChatGPT 问世的早期阶段，OpenAI 曾清晰描绘过通往 AGI（通用人工智能）道路上的不同发展阶段。我认为我们沿着这条路径推进的速度远比当初预想的要快得多。记得 18 个月前，我同样在纽约的 AI Engineer 大会上发表演讲。当时具备推理能力的模型刚崭露头角，聊天机器人已经普及了一段时间，推理模型正是最前沿的新鲜事物，但那时我们还没有真正意义上的智能体。

<details>
<summary>Original English</summary>

**Will Brown**: And so I don't know if any of you remember back in the early ChatGPT days, OpenAI had kind of spelled out their framing of like what are the different stages of AI progress on the road to AGI. And I think we moved along this faster than we thought we would. Like I remember 18 months ago I was here in New York at AI Engineer and giving a talk where we had gotten reasoners and chatbots had been around for a while and reasoners were like the new thing, but we didn't really have agents yet.

</details>

**Will Brown**: 而如今，我们已经迅速跨越了智能体和创新者阶段。接下来的关键问题显而易见：这对整个企业组织意味着什么？一个组织真正做到“AI 原生”（AI-native）究竟意味着什么？这绝不仅仅指一家大量使用智能体、全靠云端代码构建一切的初创公司，而是指在大型企业组织的宏观规模下，深度将智能体贯穿于企业全生命周期的未来公司到底长什么样？在通往这一目标的道路上，我们又需要构建哪些基础设施？

<details>
<summary>Original English</summary>

**Will Brown**: And now we've climbed pretty quickly through agents and innovators. And the question next seems to be, okay, what happens for organizations? Like what does it mean for an organization to truly like be AI native, not just as like a startup that uses a lot of agents and builds everything with cloud code, but like at the large enterprise scale? What do companies of the future look like that involve like deep integration of agents throughout the life cycle of the organization, and what do we need to build on the path there?

</details>

### 开源模型训练与企业组织隐性知识的挖掘

**Will Brown**: 作为背景介绍，先简单讲讲 Prime Intellect 正在做的事。我们围绕 AI 基础设施构建了许多不同的产品，涵盖模型的训练、部署以及持续改进，特别是专注于开源模型和开源工具链。我们所从事的事情，大体上相当于顶级 AI 实验室内部所做的研发工作，而这些正是我们对外提供的产品。我们之所以这样做，是因为我们预见到一个即将来临的未来：企业能够非常便捷地获取开源模型，并在自己的工作流、专有数据和评估测试框架（harnesses）中进行自主训练与部署。除了使用前沿顶级实验室（Frontier Labs）的模型之外，企业还可以让这些开源模型随着自身的成长而演进，从而将来源于自身工作流、专有数据、团队成员和业务流程的制度性知识与制度性优势不断复合累积。

<details>
<summary>Original English</summary>

**Will Brown**: So a bit about Prime just for some backdrop. We build a lot of different things around AI infrastructure for training, deploying, and continuously improving models, and especially open source models and open source tooling. And so we roughly do the sorts of things that you would do inside of a big lab. And these are our products. And the reason we do this is because we are imagining a future that is coming pretty quickly, it seems, where open source models are readily available to train and deploy on your own workflows, on your own data, in your own harnesses, and can be the sorts of things that organizations can have grow with them over time that allow compounding their institutional knowledge, their institutional advantage from their workflows, from their data, from their people and their processes, in addition to using the models from the Frontier Labs.

</details>

**Will Brown**: 因此，今天的演讲重点就是探讨我们眼中的这一演进图景：模型训练在 AI 原生企业中扮演着怎样的角色？它如何与前沿顶尖大模型共生互补？以及我们认为哪种模式能够真正为企业释放最大的价值，它的具体形态又是怎样的？

<details>
<summary>Original English</summary>

**Will Brown**: And so this talk will be a bit about how we see that evolving and unfolding where like what is the role of training in an AI native enterprise? How does this coexist with the frontier models? And like what do we think is going to be the version of this that really unlocks the most value for people and what does it look like?

</details>

**Will Brown**: 组织内部沉淀了海量的知识。一个组织存在的时间越久、体系越成熟，其中未曾被书面记录下来的隐性知识（implicit knowledge）就越多。当然，也有一部分知识被清晰记录了下来，比如代码库、电子邮件、业务流程规范。其中某些规则十分明确，比如“你必须这么做”、“某个模块是按这种逻辑运行的”。但绝大多数认知其实只存在于人们的大脑中，隐藏在邮件往来的字里行间、会议纪要的留白处，以及错综复杂的人际沟通网络里。

<details>
<summary>Original English</summary>

**Will Brown**: And so organizations have lots of knowledge, and the longer an organization's been around and the more established it is, the more implicit knowledge there is that kind of doesn't ever get written down. There are things that do get written down. There's code bases, there's emails, there's processes. Some of these are very explicit. They're like rules of like you must do this, this thing works like that. But a lot of things kind of live in people's heads and they live in between the lines of emails, of the meeting notes, of the kind of who talks to who.

</details>

**Will Brown**: 比如许多公司都会有一份明面上的纸面组织架构图，但同时存在着一张真实的权力运作架构图——究竟谁才是实际决策者、变革是如何在公司内部真正推行落地的、什么样的行政指令才可能真正奏效。长期身处公司的人们逐渐积累了这些经验认知，深刻明白“事情实际是如何运转的，摩擦点与阻力到底在哪里”。而在很多情况下，我认为这恰恰是 AI 在组织层面能够发挥的巨大机遇所在：许多普通个体员工往往根本无力改变组织内部已经出现故障或运转失常的事物，因为从来没有人真正把这些隐性规则与痛点公之于众，从来没有人把它们彻底挑明。

<details>
<summary>Original English</summary>

**Will Brown**: Like a lot of companies will have like an on-paper org chart and then a real org chart of like who actually makes decisions and like how does change get adopted throughout the company, what sorts of mandates are likely to take effect. And people have kind of built up this knowledge from being at companies for a long time of like, oh, this is kind of how things work. This is where the friction points are. And I think in many cases—and I think this is really one of the big opportunities for AI at the organizational level is—is that many individual people are kind of not in a position where they can change the things that are broken in an organization, because no one is actually spelling it out. No one is.

</details>

<!-- chunk 40/51 -->

### 智能体发现组织低效与隐性知识鸿沟

**Speaker**: 这就像从鸟瞰的视角俯瞰整个组织中发生的一切，然后指出：嘿，这边的流程效率很低，本可以做得更好；或者某个问题在所有这些不同的团队中反复出现，却没有人意识到解决方案其实早就被另一个团队找到了。而这些事情正是智能体所极其擅长处理的。智能体非常擅长梳理大量非结构化的文本数据，发现其中的这类规律与模式，将它们转化为有价值的信息，并明确指出：某个工作流存在问题，它在浪费时间且效率低下，完全可以用另一种方式来做。

<details>
<summary>Original English</summary>

**Speaker**: ...is like taking a bird's eye view of looking at everything that happens in an organization and saying, "Hey, this over here is inefficient. This could be better. This thing keeps happening across all these different teams, but nobody's figured out that the solution has actually been discovered by that team." And these are the sorts of things that agents are great for. Agents are very capable at combing through large amounts of textual data that's unstructured and finding these kinds of patterns and turning them into something useful and surfacing them as like, "Okay, this workflow has a problem because it is wasting time and it's inefficient and it could be different instead."

</details>

**Speaker**: 不过，我们并不希望这只是一次性的动作。我们希望这能演变成组织广泛采用 AI 的常态化方式——智能体不仅能够获取它们所需的上下文，还能同时促进智能体自身以及整个组织的持续改进。我们希望智能体能更像我们的同事，但人类同事是在实际工作中边做边学的，而智能体目前在工作中的学习机制还处于相对原始的阶段。

<details>
<summary>Original English</summary>

**Speaker**: And we don't want to just do this once, though. We want this to kind of become the way that organizations adopt AI broadly, where agents are able to get the context they need, but also they're able to improve both the agents themselves as well as the organizations. And we want agents to be more like our co-workers. But human co-workers learn on the job. Agents currently learn on the job in relatively primitive ways.

</details>

**Speaker**: 智能体主要是通过上下文学习（in-context learning）来实现这一点的。目前这通常表现为：有人给它们编写一个 skill 文件，或者智能体自己在代码库中查阅检索。但它们无法像人类员工那样，真正获得组织层面的潜在隐性知识（institutional-level latent knowledge）。

<details>
<summary>Original English</summary>

**Speaker**: Agents learn in relatively primitive ways through like in-context learning. And this typically looks like them kind of having a skill file written by somebody or like looking around a codebase, but they don't get the institutional-level latent knowledge that human employees really do.

</details>

### 上下文瓶颈与权重沉淀

**Speaker**: 因此，智能体不得不反复重新学习，反复重新摸索，消耗大量的输入 Token（input tokens）。我认为如今大家已经意识到，缓存输入（cache to input）正是许多智能体使用成本中的瓶颈所在。即便你获得了极高的缓存命中率，缓存成本也降了下来，但每一次重新执行某个工作流时，依然需要重新处理海量的输入数据。

<details>
<summary>Original English</summary>

**Speaker**: And so they relearn a lot. They have to rediscover things. They spend a lot of input tokens. And I think nowadays people are realizing that cached input is like the bottleneck in many agent costs. And even if you do get great cache rates and cache costs go down, you still have to like reprocess a lot of input to redo a workflow every single time.

</details>

**Speaker**: 为了解决这个问题，你自然会希望把更多的东西直接固化（bake in）到模型中，尤其是那些很难写成明确规则的内容。我喜欢从“规则到模式”的光谱，以及从概念上的“代码与数据”的对比来思考这个问题。很多东西是以代码形式存在的，比如 skills 和 rules 大致就是这类；但像偏好、摩擦阻力、启发式经验以及发展趋势，这些全都是数据。各个机构每天赖以运转的数据极其庞大，组织里的员工在潜移默化中吸收了这些知识，而模型却从未真正有机会学习。在我们看来，正是这一点阻碍了它们成为真正的同事。

<details>
<summary>Original English</summary>

**Speaker**: And so to get around this, you kind of want to be able to bake more into the model, especially for things that are harder to write down as rules. So I like thinking about the spectrum from like rules to patterns, as well as like conceptually like code versus data. And so lots of things live as like code, and like skills are kind of like this, rules are kind of like this. But things like preferences and friction and heuristics and trends, these are all data. And institutions have so much data that they are running on, and the employees of the organization implicitly learn that models never really get a chance to learn. And this is the sort of thing that we see as blocking them from becoming true co-workers.

</details>

**Speaker**: 于是就引出了一个问题：到底什么应该放入上下文（context），什么应该写入权重（weights）？部分答案在于，你必须“挣来”这个资格——知识并不是立即就能写入权重的。但如果你观察每一代新模型的演进就会发现，模型之所以变强，并不是因为 Prompt 写得更好了，而是因为对它们进行了更多的训练。训练是有用的，训练是行之有效的，训练正是我们看到所有这些技术进步的根本原因。大体而言，模型是在海量数据上训练出来的，这些数据旨在近似各大实验室预期在各类组织中会出现的高价值、可复现的工作流。

<details>
<summary>Original English</summary>

**Speaker**: And so there is a question of like, okay, what goes in context? What goes in the weights? And part of it is you kind of need to earn it. Like things don't just go in the weights right away. But if you see kind of every new generation of models, the models get better not because the prompt is better, but because they train them more. Like training is useful. Training works. Training is why we see the progress we do. And the models roughly are like trained on lots of data that is aiming to approximate things that the labs expect will be like high-value, repeatable workflows at organizations.

</details>

### 打破低效的数据传递链

**Speaker**: 当前的这套机制虽然确实在发挥作用，也是模型能力提升的路径，但如果你把全流程剖析开来，会发现它的效率其实相当低下。举例来说，一个模型要学会精通使用 Salesforce 工具的某种组合，往往需要这样一条链条：某个深谙这些工具使用方法的人正在找工作，可能他们之前所在的公司用过这些工具，现在他们在空闲时间浏览专家网络平台赚点外快，把自己的知识分享给专家网络公司的某个人；随后，这家网络公司的人把从人类专家那里获得的数据整理后，转交给另一位专门构建强化学习（RL）环境的人；接着，这个可能缺乏垂直领域专业知识的人把 RL 环境卖给实验室的研究人员，而这些研究员本身也并非该领域的专家；研究员对数据进行精炼并塞进训练管线，最终送入下一代前沿模型的训练运行中，制造出一个通过这种类似于“传话游戏”（game of telephone）间接获得那位人类最初经验的模型。

<details>
<summary>Original English</summary>

**Speaker**: I think there's a process that currently works. It's how the models get better, but if you spell it out, it's relatively inefficient. So like the way that a model would learn how to get really good at like using some combination of like Salesforce tools, for example, let's say is someone who knows how those tools get used has to be looking for work. And maybe they previously worked at a place that were using these tools, and now they are browsing kind of expert network sites to make some money in their free time, and they are sharing their knowledge to someone who works at an expert network company. This person at this network company will then take this data from the human and pass it to someone else whose job is to create RL environments. This RL environment might get sold then by someone who doesn't have this expert knowledge to a researcher at a lab who also really isn't the expert in the domain, who then will be refining it to put it into a training pipeline to go into the next frontier model run to make a model that has kind of through this like game of telephone gotten some knowledge of that human originally.

</details>

**Speaker**: 这个流程中的环节实在太多了，而且还是一个高度不透明的秘密管线。人们往往只在相邻的两个环节之间对接交流，而真正懂得这一专业技能的人既没有去监督模型训练，也无法像每天使用编程智能体的人类那样，直接对模型的训练方式产生影响。

<details>
<summary>Original English</summary>

**Speaker**: But there's so many steps in this pipeline, and it's a relatively secret pipeline. Like people talk across two stages of it, but like the human who knows this thing is not supervising the training run, is not really directly inputting like how the model gets trained in the way that a human could if they were doing it for their coding agent that they're working with day-to-day.

</details>

**Speaker**: 因此，我们看到的机遇以及希望推进的方向，就是消除这道鸿沟。就像我们在使用编程智能体时，每次都要在 Prompt 中反复叮嘱同样的事情、提醒它们不要重蹈覆辙一样——你完全可以用类似的方式去训练模型。你可以向模型传达意图，让它们持久地掌握这些东西，而不是仅仅把它们记在你的 `agents.md` 里。如果全写在文件里，内容只会不断堆积，你不得不频繁重构。虽然你确实可以保留一部分规则，但很多时候你真正想要表达的是一种与上下文相关的偏好。你会告诉它：“在当前这种场景下，你刚才的做法并不完全符合我的要求，我更希望你采用这种方式。”我们所追求的系统，能够将这种反馈沉淀并复合转化为持久的学习。通过模型训练来实现这一点是非常高效的，因为你在这个过程中提供的数据形态，与实际训练管线所需的数据形态非常契合。

<details>
<summary>Original English</summary>

**Speaker**: And so what we see as an opportunity and kind of also where we would hope to go is like to close this gap and to allow the person who—the same way that when we work with our coding agents, we're prompting them like the same things every time, telling them to like not repeat the same mistakes—that this is how you could train models. You can tell the models things, and they will learn these things durably, not just as like a line in your agents.md which kind of accumulates and then you have to refactor it all the time. You can do some of that, but a lot of times what you really want is you're giving kind of contextual preference. You're saying, "In this setting, this thing that you did was not exactly what I wanted, and I would have preferred this instead." And we'd want systems that can compound this into like durable learning. And training is a very effective way of doing this because the shape of data you're giving there is quite close to what you would want from like an actual training pipeline.

</details>

### 多层学习架构与直觉化组织模型

**Speaker**: 实际上存在几种不同层次的学习方式：有些是人类所做的事情；有些是在治理与框架层（harness layer）通过 skills 和 memory 实现的；还有些知识散落在整个组织的文件系统和数据库中，需要通过代码和工具进行检索；此外就是模型自身所掌握的宽广世界知识。不过我相信大家都经历过这样的困扰：使用的模型其知识截止日期停留在过去的某个时间点，你无法和它自然地探讨过去六个月发生的新闻，因为它们并没有吸收这部分现实，每次都必须在上下文窗口中从头构建一个世界模型，这导致它们无法像讨论更久远的事情那样游刃有余。

<details>
<summary>Original English</summary>

**Speaker**: And so there's several different types of learning. There's things that people do. There's things that you can do at the harness layer with skills and memory. There's knowledge that just lives throughout an organization in file systems and databases that you retrieve with tools and with code. Then there's the models themselves, which have this really broad world knowledge. But like we all have, I'm sure, experienced frustration when using a model whose cut-off of knowledge is like a while back, and like you can't really talk to the models about the news of the past six months nowadays. They have to go like relearn a world model in context every single time, and this just does not allow them to really operate as fluently as they can discuss things that happened longer ago.

</details>

**Speaker**: 因此，为了从模型中榨取最大的价值，我们预见到企业会越来越希望拥有能够在直觉层面上真正透彻理解组织内部运作的模型。而这正是需要通过训练去达成的目标。

<details>
<summary>Original English</summary>

**Speaker**: And so organizations, to get the most value out of models, we imagine they will want to increasingly have models that really understand what is going on in the organization at an intuitive level. And this is the sort of thing that you want to train for.

</details>

### 将评估视作测试用例的持续学习闭环

**Speaker**: 那么该如何达成这一目标呢？一个组织该如何从抽象地提出“我们要基于内部数据训练模型”这一想法，真正落地走到这一步？我认为一个非常有用的切入点，就是将评估（eval）本质上看作测试用例（test cases）。在软件工程代码领域，我们围绕测试以及软件开发生命周期已经建立起了成熟的体系，通常能够确保代码库随着时间的推移保持健康增长，如今智能体也在替我们承担大量的这类工作。

<details>
<summary>Original English</summary>

**Speaker**: And so how do you get there? Like what is the road for an organization to go from like having this idea in the abstract of like "we're going to train models on our data" to actually getting there? And I think one really useful starting point is eval as essentially test cases. I think like with code, we've gotten to a point of maturity around like testing and lifecycles and software development lifecycles for ensuring that codebases grow healthily over time usually, and agents are doing so much of this work for us.

</details>

**Speaker**: 我认为对绝大多数组织而言最务实的持续学习模式，就是把模型当成类似于代码库一样对待——它拥有自身的生命周期，你可以为其添加测试用例、引入新功能以及补充资产。在实际使用智能体的过程中，你起初会收集各类运行轨迹（traces），这些轨迹中包含了你输入的提示词以及针对模型行为给出的具体反馈。仅凭日常使用这些模型的过程，你实际上就已经在持续积累创建评估所需的全部核心资产。只是在以往的历史中，构建评估一直是一件比较痛苦的事情，很多机构往往并不愿意手动去搭建；但如今，智能体正在以极快的速度演进并介入……

<details>
<summary>Original English</summary>

**Speaker**: And the version of continual learning that I think is like most practical for most organizations is just treating a model kind of like a codebase, where it is the sort of thing that you can have a lifecycle around: you can add test cases to, you can add features to, you can add assets to. And this is the sort of thing that the process of using agents—like initially you collect traces. These traces have your prompts and they have your feedback to things that models did. And just from the process of using these models, you are accumulating the assets you need to create evals. It's just that making evals historically has been a little bit painful and a lot of organizations have not necessarily wanted to do it manually. But the agents are quite quickly getting to the...

</details>

<!-- chunk 41/51 -->

### 决策模型、智能路由与低成本模型优化

**演讲者**：到了这个阶段，值得庆幸的是，我们已经拥有能够代劳大量评测整理（eval curation）工作的机器人了，特别是当我们进一步根据构建评测的最佳实践去训练它们时，让评测机制既坚固可靠，又易于促进学习。我认为这里另一个非常有参考价值的例子，是过去几周里伴随 Jev 等项目席卷全球的“决策模型热潮”（decision model craze），以及围绕模型路由（routing）形成的并行趋势。大家对成本优化感到极其兴奋，因为大家都看得很清楚，每个月在 Claude 等前沿模型上花掉巨额资金是完全可能发生的，所以我们必须搞清楚：到底什么时候应该切换到成本更低的模型？

<details>
<summary>Original English</summary>

**Speaker**: ...point where thankfully we have robots that can do a lot of the eval curation for us, especially as we train them more on the best practices of making evals in ways that are robust and amendable to learning. And so I think another useful example here is the decision model craze that has kind of been taking the world by storm in the past couple weeks with Jev, and also the parallels around routing and people being very excited about cost optimization, because we see that it's possible to spend very large amounts of money on Claude every month, and we figure out when should we use a cheaper model.

</details>

**演讲者**：我认为人们已经逐渐意识到，这类逻辑天然需要内置在智能体的测试与运行架构（harness）之中。不过，它的本质属性其实与决策模型非常相似。我之所以把这两者放在一起讨论，是因为它们都属于具有极清晰数据标签的场景：这里存在明确的正确答案，并且让人类或另一个智能体提供反馈的机会窗口也非常清晰。你可以让大模型和小模型同时执行同一个任务，然后评估小模型的输出表现是否与大模型相当。如果答案是肯定的，那么这就变成了宝贵的数据——意味着针对这类任务，我们后续可以开始将更多流量路由给小模型处理。

<details>
<summary>Original English</summary>

**Speaker**: And this is the sort of thing that I think people are recognizing needs to kind of live in the harness. But it also is an attribute that looks relatively similar to decision models. And the reason I bring both these up together is because there's things with very clear labels where there's a right answer and there's an opportunity for a human or another agent to give feedback. You can have the big model and a small model do the same task, judge whether the small model was as good as the big model. If so, then this is now data of, like, for this kind of thing, we can start routing to the small model more.

</details>

### 拟合人类判断与即插即用的持续学习

**演讲者**：对于正在学习模拟人类在特定情境下如何进行判断的决策模型来说，逻辑也是完全相同的。这是一种绝佳的、极易打上标签的行为动作：人类可能在其中负责审批，就像我们有时在 Claude Code 中审批工具调用一样。虽然我觉得大多数人现在可能都开启了自动接受工具调用的选项，但每个组织对于更具定制化、不单单关乎工具安全的场景，必然都有自己独特的业务规则和偏好。而所有这些规则和偏好，都是你后续可以持续沉淀并复利注入决策模型中的东西。因此，这是一种非常切实可信的持续学习（continual learning）形态，许多团队明天就可以直接接入并立即看到实用价值。

<details>
<summary>Original English</summary>

**Speaker**: Same for a decision model that's learning to kind of mimic the way that a human in a certain situation would make a judgment. This is a great labelable action where the human might be doing the approval the same way that like we approve our tool calls in Claude Code sometimes. But I think most people have turned on auto tool acceptance, but every organization for more bespoke things that aren't just about tool security are going to have their own rules and preferences. And these are the sorts of things that you could then compound into a decision model. And so this is like a very believable form of continual learning that a lot of people could just plug in tomorrow and see immediate value from.

</details>

**演讲者**：但从更广阔的视角来看，我们观察到企业真正渴望去做的——这也是我们在 Prime Intellect 投入大量精力在做的事情——是与各类机构合作推进相对雄心勃勃的训练项目：把在高并发、大规模生产环境中部署模型所沉淀下来的追踪轨迹（traces），转化成丰富、稳健的训练环境。这些环境将真实数据与合成数据融为一体，能够完整捕获并还原企业希望长时间运行的智能体（long-running agents）去应对的真实业务复杂度。只要配备了充足的编排系统、完备的工具链以及人在回路（human-in-the-loop），智能体自身就能够极其有效地将这些原始记录转化为足够丰富、可供进一步训练的环境。

<details>
<summary>Original English</summary>

**Speaker**: But more broadly what we see people wanting to do, and this is a lot of the work that we do at Prime Intellect, is working with organizations that are looking to do relatively ambitious training projects around turning their traces from deploying a model in production for a high volume use case into rich robust environments that are blended real and synthetic that kind of capture the complexity of the real tasks they want to be using long-running agents for. And agents are very useful with sufficient orchestration around them, sufficient tooling and humans in the loop at turning these into environments that are rich enough to train in.

</details>

### 自我演进闭环与动态 UI 决策界面

**演讲者**：我们看到，随着每一代开源模型和闭源模型的推陈出新，这个流程正变得越来越自动化。这意味着我们迎来了一个重大契机：把我们日常正在执行的所有工作，自然而然地转化为一个自我演进的良性循环——只需将智能体应用于数据清洗和整理，并构建起专门供人类表达意图和提供信号的交互界面，这个循环就会神奇般地水到渠成。

<details>
<summary>Original English</summary>

**Speaker**: And we see that this is getting more and more automated with every new generation of open and closed models. And this means that we have an opportunity to start having this whole thing of taking the stuff that we're already doing and turning it into a self-improvement loop just kind of fall out magically from applying agents to curation of the data and creating interfaces for humans to give signal about what they want.

</details>

**演讲者**：这是我自己日常在个人工作流中深度把玩的一个理念，我相信它未来会成为与模型交互的主流界面形态。你现在已经在某些机器人产品中看到了一点雏形，但特别是在当前模型已经极其擅长实时动态编写代码的背景下，这类“微件卡片”（widget cards）特性构成了一种极其务实的动态 UI 形式，并且在引出和捕获人类决策方面效果极佳。

<details>
<summary>Original English</summary>

**Speaker**: This is an idea that I've been for my own setup been like playing around with a lot that I think will become a popular interface for interacting with models more in the future. You're seeing it a little bit in some of the bots, but I think it, especially now that models are good at like writing code on the fly, these kind of widget card features that are like I think a very practical form of dynamic UI that are also really useful for eliciting human decisions.

</details>

**演讲者**：它们在本质上类似于工具调用的确认机制，但要个性化得多、具体得多，而且能有效化解诸如此类的困局：比如你同时并行运行着 20 个不同的智能体，你必须费力去记哪一个在干什么、究竟是谁在为你汇总整理这一切；这时有人会问“你是不是只想要一个单体机器人？”你回答“一个挺好，但我其实需要两个”，紧接着你就有了两个，然后迅速变成了 20 个。我认为我们目前正在“单流”（single stream）与“多流”（multi-stream）的智能体对话线程之间来回摇摆。

<details>
<summary>Original English</summary>

**Speaker**: So, they're kind of like the tool call approval thing, but much more personalized, much more specific, and also kind of get around the problem of like, okay, you have 20 different bots that are going, and you have to remember which ones are where, and who is curating all this for you, and then people are like, do you want one bot? And then you're like, oh, one's great, but I actually want two. Then you have two, then you have 20. And I think we kind of are oscillating back and forth between this the single stream and the multi-stream agent threads.

</details>

**演讲者**：但作为人类，我们真正想要做的其实是做出决策。我们希望把想法交付给智能体，让它们带着这些想法自主去跑，只有在真正需要我们定夺决策时才回来找我们。而智能体理应在“何时需要将决策呈报给我们”这一点上做出明智判断。如果智能体能够为我们按需即时生成交互界面，让我们以极其直接、直观的方式向它们注入所需信息——首先，对我们人类而言，这远比费劲去通读一篇冗长冗杂的会话消息并反复寻找“核心问题究竟在哪”要符合人体工程学得多。

<details>
<summary>Original English</summary>

**Speaker**: But what we really want to do are make decisions. We want to give ideas to the agents, let them run with the ideas and then come back to us when we need to make decisions. And the agents hopefully should make good choices about when to bring us decisions. And if agents can create interfaces on the fly for us that allow us to very directly give them the information they need. One, this kind of is much more ergonomic for us as humans than like reading trying to parse through a long thread message to see like, okay, where was the question?

</details>

### 高质量对齐数据与组织级模型训练实践

**演讲者**：从另一个角度看，这恰好也是决策模型开发模式在人类这一侧的对偶呈现。更关键的是，这构成了绝佳的训练数据。因此，我们一直在探索这种模式，将其作为训练模型的一种手段，从而跑通整个闭环：借助这种自然流畅的交互界面获取人类输入，让这些输入直接充当真值标签（label）；模型也能据此直接优化提升，因为目标极其明确清晰。这巧妙地绕开了我们在强化学习奖励黑客（reward hacking）等领域经常听到的诸多棘手问题。虽然那些问题同样值得深入攻坚，但在我们看来，这才是解决很多实际问题的绝佳切入点。

<details>
<summary>Original English</summary>

**Speaker**: It's also kind of like the human dual side of the decision model dev style. But it also is perfect data. And so it's a setting where we've been experimenting with this as a way of training models to kind of get this feedback loop going from having human input with these kinds of natural interfaces be the sort of thing that directly acts as a label and is the sort of thing that a model can directly improve on because there is a very explicit target. And it gets around a lot of the problems that we kind of hear about in reward hacking and whatnot. Those things are worth addressing too, but like this is where we see a very useful starting point being for a lot of these problems.

</details>

**演讲者**：而且这种训练并不需要覆盖你技术栈中的每一个模型。它可以专门针对编排层模型，也可以是特定的决策模型，但它确实是一个极佳的入口，让偏好对齐与企业潜在的领域隐性知识开始在模型参数中真正生根复利。

<details>
<summary>Original English</summary>

**Speaker**: And this can be done doesn't have to be with every model in your stack. It can be the orchestration layer models, it can be the decision models, but it is an entry point for kind of starting to have this compounding of preferences and latent knowledge happen in the models.

</details>

**演讲者**：我觉得今天就有一个非常新鲜的落地案例——这是我今天早些时候刚刚补充进来的，来自一家名为 Paper Instruments 的公司。他们使用了我们的一些工具链来完成这件事，也是我们的合作伙伴。他们仅仅花费了 30 万美元，就训练出了一个在知识型工作领域（比如处理电子表格和幻灯片展示）达到帕累托前沿最优（Pareto frontier optimal）水平的模型。对于一个企业组织来说，这仅仅相当于雇佣一名普通员工规模的资金投入——你可以选择再去招募一名软件工程师，也可以选择训练出一个高水平的模型。

<details>
<summary>Original English</summary>

**Speaker**: And so I think there's a recent example today, I just added this earlier from a company called Paper Instruments that they use some of our tooling to do this. They're friends of ours. But they trained a model for 300K that is kind of Pareto frontier optimal for knowledge work for things like spreadsheets and slides. And it's like an employee scale investment for an org to do, where like you could go hire a software engineer or you could like train a model.

</details>

### 昼夜交替计算与持续学习的原型构想

**演讲者**：如果你选择随着时间推移去逐步沉淀和复利知识，你甚至可以把这笔预算分摊到更长的时间跨度里。但无论如何，这类做法正在变得越来越具有实操可行性。这也是越来越多组织现在强烈渴望去践行的事情，而且我们清晰地看到，这种需求几乎月复一月地呈现出爆发式增长。一方面，人们开始认识到这件事的巨大商业价值，并且意识到开源模型已经足够优秀——只要你将属于自身的特定行业领域知识、运行框架和业务环境转化为模型的训练场，就能让它们大幅超越通用水平，且高度契合企业个性化需求。

<details>
<summary>Original English</summary>

**Speaker**: And you can also spread this out over a longer period of time if you're kind of compounding the knowledge over time. But it's the sort of thing that is increasingly becoming quite practical, and is the sort of thing that a lot of organizations we see wanting to do now and we kind of see the trend of how much more the demand for this is growing month after month. As people start recognizing one the value of this and how kind of the open models are good enough that you can get them to be much better and also much more personalized by turning your knowledge for your domain, your harness, your environment into a training setting for them.

</details>

**演讲者**：另一方面，它本身在逻辑上也天然适合构建起持续学习的飞轮。这里展示的是我们在内部正在探索的一个原型方案，它描绘了我们设想中人们如何在真实世界中真正落地持续学习：你可以在白天持续收集并沉淀业务执行轨迹（traces）；到了每天晚上，系统会自动汇总并展示出建议的训练实验计划，审查被系统标记出问题的样本，然后直接触发针对当晚的模型训练任务。也许在白天，你的算力集群主要用于执行推理，全负荷服务业务智能体；而到了夜间，员工使用量大幅下降，你就可以顺理成章地将这部分富余算力调配去进行模型训练。

<details>
<summary>Original English</summary>

**Speaker**: But also it's the sort of thing that naturally lends itself to a learning loop. And so this is a prototype of something we're doing internally around kind of how we're imagining people can really deploy continual learning in the world which is that you can have traces, you can start collecting these and you can then like every night see the proposed experiment, look at the things that have been flagged as issues and kick off a training run for the night. Maybe your inference capacity in the day is serving your agents, at night employees are not using them as much and you can use that capacity for training instead.

</details>

**演讲者**：在我们看来，这是一种极其自然的路径，能够让各类机构在不久的将来真正把持续学习贯彻落实到模型的权重参数之中，并将自身的专业知识持续复利沉淀为智能体愈发强大的核心能力。这也正是我们看到整套技术演进最终走向的终局所在：你首先需要摸索并梳理出自身的业务工作流，接着创建定制技能（skills），构建严谨的评测集（evals），实现智能模型路由（routing），最终，你开始追求规模效应，收获深植于企业与组织内部数据所带来的复利回报，促使整个组织以与时俱进、日臻完善的节奏，演变成为自我进化的超级智能体。以上就是我今天分享的全部内容。如果时间允许的话，我可以解答几个问题……没有提问的话，那就到这里，非常感谢大家。

<details>
<summary>Original English</summary>

**Speaker**: And so this is a very natural way that we see organizations able to like quite soon actually do for real continual learning in the weights of the models and start compounding their knowledge into better and better capabilities for their agents. And so this is kind of where we see a lot of this culminating towards. There's so many things you do. First you discover your workflow, you create skills, you make evals, you do routing, and then eventually you start to want to get the economies of scale, get the compounding benefits that come from the data inside of your companies, your organizations, and have the organizations become increasingly self-improving in ways that get better and better over time. That's what I got. I can maybe take questions if there's any time. I don't know. No questions. And, yeah.

</details>

<!-- chunk 42/51 -->

### Prime 团队结语与新议题开篇

**Speaker A**: 我们来自 Prime。我们正在开展大量这方面的工作。其中许多项目都是开源且公开的，我们会在博客上撰写文章，也会在 Twitter（X）上发布相关动态。但与此同时，我们也与许多公司开展合作，目前正在招聘并不断扩展团队。因此，如果您想与我们取得联系，欢迎随时沟通。谢谢大家。

<details>
<summary>Original English</summary>

**Speaker A**: We're at Prime. We are working a lot of this stuff. A lot of it is open source and public and we uh, blog about it and tweet about it, but also we work with companies and we're hiring and growing and so get in touch if you want to get in touch. Thanks.

</details>

**Jamaima Abu**: 嗨，大家好，我叫 Jamaima。今天我要和大家聊一聊“AI 中可访问性的成本”（the cost of accessibility in AI），或者用我更喜欢的一种说法：“别再把 Token 浪费在构建人们根本无法使用的产品上了”。因为归根结底，究竟什么是可访问性（Accessibility）？可访问性就是指无论用户是否存在残疾，任何人都能够使用该产品的品质。

<details>
<summary>Original English</summary>

**Jamaima Abu**: Hia, my name is Jamaima and I'm going to be talking to you about the cost of accessibility in AI or as I like to call it stop wasting tokens on building products that people can't use because at the end of the day what is accessibility accessibility is the quality of being able to be used by anyone regardless of disability.

</details>

**Jamaima Abu**: 这意味着，当你构建出一个缺乏可访问性的产品时，那个产品在本质上就是毫无用处的，因为人们根本用不了它。我认为这是一个非常切中时弊的话题，尤其是在如今这个充斥着“氛围编码”（vibe coding）、提示词工程，以及 AI 基本上在替我们编写所有代码的时代。我们需要确保，即使所有代码都是由 AI 编写的，我们依然是在为人类而构建，并且要确保人类能够真正使用我们所构建出来的产品。

<details>
<summary>Original English</summary>

**Jamaima Abu**: So what this means is that when you build a product that is inaccessible that product is inherently useless because people cannot use it. I think this is a very prevalent talk especially in these days of vibe coding and prompt engineering and AI basically writing all the code for us. We need to ensure that even with all the code being written by AI, we're still building for humans and we're ensuring that humans are able to use the products that we are building.

</details>

**Jamaima Abu**: 一天之内凭着感觉随手“vibe”出五个不同的应用程序固然很棒、很吸引人，但如果人们根本无法使用那些应用，那么这么做到底还有什么意义呢？WebAIM 的一项研究表明，全球排名前 100 万的网站主页中，有高达 96% 的主页存在这样或那样的可访问性问题。

<details>
<summary>Original English</summary>

**Jamaima Abu**: It's all very well and good to vibe good five different apps in one day, but if people can't use those apps, then is there really any point? A study by WebM shows that 96% of the homepages of the top 1 million websites in the world have some form of accessibility issue or another.

</details>

### AI 构建可访问性：成本实验与数据洞察

**Jamaima Abu**: 我是一个经常到处做关于可访问性演讲的人。每当我询问大家为什么不把网站做成可访问的时，我通常听到的回答都是“这太耗费时间了”。虽然我承认提升可访问性确实是一个耗费人力和时间的过程，但我确实认为，既然我们现在已经迈入了由 AI 编写绝大多数代码的阶段，那么让产品具备可访问性实际上变得更加容易了。如果非要说有什么不同的话，我认为构建缺乏可访问性的网站反而会耗费更多的时间和金钱。

<details>
<summary>Original English</summary>

**Jamaima Abu**: Now, I'm someone that goes around a lot and speaks about accessibility, and whenever I ask why don't people build websites to be accessible, I usually hear it takes too long. While I will agree that accessibility is a labor and time intensive process, I do think that now that I've gotten the stage of AI writing most of our code, it's actually easier to make things accessible. If anything, I would say it costs more time and more money to build inaccessible websites.

</details>

**Jamaima Abu**: 于是，我决定利用工作中的代码库进行一次小实验。我给智能体（AI Agent）提供了这样一个提示词——这只是一个非常简单的提示词，没有任何附加准则：“根据 Figma 实现这个设计。”我将它运行了两次：第一次没有任何可访问性 Skill（技能），第二次则启用了我自己编写的可访问性 Skill。

<details>
<summary>Original English</summary>

**Jamaima Abu**: So, I decided to carry out a little experiment using the codebase at work. So, I gave this prompt to the agents. It's just a simple prompt with no guidelines. implement this design from Figma. And I ran it twice. The first time without any accessibility skill and the second time by using the skill that I had written.

</details>

**Jamaima Abu**: 我所观察到的结果是，智能体在使用可访问性 Skill 时不仅构建速度更快，而且在成本上降低了 58%。我们可以看一下这里的数据：我们发现，使用可访问性 Skill 不仅成本更低，而且完成该提示词任务所消耗的时间仅为原本的三分之一。

<details>
<summary>Original English</summary>

**Jamaima Abu**: And what I noticed was that not only was it faster for the agent to build the accessible skill, but there was also a 58% reduction in cost when using that skill. And we can take a look at the data here. We see that not only was it cheaper, but it also took a third of the time to finish the prompt while using the accessibility skill.

</details>

**Jamaima Abu**: 因此得出的结论似乎是：AI 智能体构建具有可访问性的网站实际上成本更低。我们可以这么说，但我们先不急着下定论，因为这只是一次性的实验，并不是在严格受控的约束环境中进行的，所以它不能作为证明这一事实的实证数据。但是，当我们深入探究为什么 AI 智能体在没有任何可访问性技能的情况下需要花费长得多的时间来完成提示词任务时，我们就能更清楚地理解为什么构建具备可访问性的网站反而速度更快。

<details>
<summary>Original English</summary>

**Jamaima Abu**: So in conclusion, we can say that it is actually cheaper for AI agents to build accessible websites. We can say that but we won't say that because this was a one-off experiment and it was not carried out in a constrained environment. So it cannot serve as empirical data that proves the fact. But when we look into the reasons why it took the AI agent much longer to carry out the prompt without any accessibility skills, then we can have a better idea of why exactly it is faster to build accessible websites.

</details>

### 自我介绍与引导 AI 智能体

**Jamaima Abu**: 不过在展开讨论之前，先做个自我介绍：大家好，我叫 Jamaima Abu。我是 YieldStreet（另类投资平台）的产品工程师。我同时也是一名谷歌开发者专家（Google Developer Expert, GDE）、微软最有价值专家（Microsoft MVP），并且获得了国际可访问性专业人员协会的可访问性核心能力认证（CPACC）。基本上，我喜欢到处去宣讲如何让网络环境变得更加无障碍。此外，我也想先做个小小的免责声明：虽然我举的许多关于可访问性的例子都基于 Web，因为那是我的专业领域，但这些原则同样适用于你所开发的任何平台，不论是移动端、硬件还是其他任何系统。

<details>
<summary>Original English</summary>

**Jamaima Abu**: But before we get into that, hi, my name is Jamaima Abu. I am a product engineer at case and alternative investment platform. I'm also a Google Dev Expert, a Microsoft's MVP, and a certified professional in accessibility core competencies. Basically, I like to go around talking about how to make the web a more accessible place. Also, I will give a slight disclaimer. While a lot of my examples relating to accessibility will be web- based because that is my area of expertise, this can also apply regardless of whatever platform you're working on, whether that's mobile or hardware or anything at all.

</details>

**Jamaima Abu**: 那么，让我们回到正题。这就是你的 AI 智能体。如今它是一个超智能的工具，几乎无所不能；但与此同时，它其实才刚刚问世 3 年。在很多方面就像一个小婴儿一样，AI 非常容易受到外界影响。如果你反复告诉它足够多次“天空是红色的”，最终它就会开始接受天空就是红色的这一设定。这意味着，作为掌控全局、负有责任的开发者，我们必须确保为 AI 智能体提供恰当的技能与引导，以便让它们构建出符合我们预期的产品。

<details>
<summary>Original English</summary>

**Jamaima Abu**: So, let's get back to it. This is your AI agent. Now, it's a super intelligent tool that can do almost anything in the world, but at the same time, it's just 3 years old. And much like a baby, AI is very impressionable. If you tell it enough times that the sky is red, eventually it will start to accept that the sky is red. What this means is as the responsible developers in charge, we have to make sure that we're providing the right skills and guidance for AI agents to build the product that we want them to build.

</details>

**Jamaima Abu**: Netflix 上有一部我很喜欢的日本综艺节目叫《初归》（Old Enough / 初次跑腿）。节目的内容基本上就是让刚学会走路的幼童去独立完成他们的第一次跑腿任务。比如一个三岁的小孩被派去超市买杂货。我很喜欢这个节目的一点是，你总能看到父母在派孩子出门跑腿之前所做的各项铺垫和准备工作。比如孩子可能已经跟着父母去过那家超市很多次了，或者父母会提供一份非常详细的清单，清楚地告诉孩子超市在哪里、需要买什么、哪些路段要避开，这基本上让孩子执行起跑腿任务来变得容易得多。

<details>
<summary>Original English</summary>

**Jamaima Abu**: There's a Japanese show on Netflix that I love called Old Enough. It's basically about toddlers being sent on their first errand. It can be like a three-year-old being sent to a supermarket to purchase groceries. And one thing I like about the show is that you can always see the steps that the parents have put in place before they send them on that first errand. So it might be that the child has gone with their parents to this market multiple times or they provide a list that's very clearly detailed. It shows them where the supermarket is, what they need to get there, what parts to avoid and it basically makes it a lot easier for the child to carry out that errand.

</details>

**Jamaima Abu**: 面对智能体也是同样的道理。当你给智能体下达指令时，如果我说“构建这个网页”或者“实现这个设计”，只要我提供了恰当的技能和提示词，就能大大降低该智能体误入歧途的概率，并确保最终产出的成果与我预想的完全一致。

<details>
<summary>Original English</summary>

**Jamaima Abu**: It's the same thing with an agent. When you're giving an instruction to an agent, if I'm saying build this web page or implement this design, if I provide the right skills and prompts, it makes it a lot easier for that agent to avoid going down the wrong path and for the finished product to look like what I intended it to look like.

</details>

### 缺乏引导下的两大陷阱：偏见传递与代码冗余

**Jamaima Abu**: 接下来我们来看看，如果我们在开发产品时不给智能体提供任何形式的引导，究竟会发生什么。首先，人类的偏见会演变成 AI 的偏见。多年以来，人类开发出来的网站或产品往往缺乏可访问性，坦白说，是因为我们根本就没有形成那种思维方式。尤其是作为开发者，我们很容易陷入“在我电脑上能跑就行”（it works for me）的心态。我会觉得：“这东西在我的笔记本电脑上运行良好，表现符合我的预期，那我何必再去检查其他东西呢？”我根本不关心它在屏幕阅读器（Screen Reader）上是否正常工作，也不关心在弱光环境下能不能看清。我只想：“它能跑，功能做完了，我收工了。”

<details>
<summary>Original English</summary>

**Jamaima Abu**: So let's take a look at what happens when we don't provide any form of guidance for our agents in developing products. Firstly, human bias becomes AI bias. For years, humans have been developing websites or products that are inaccessible because frankly, we just don't think that way. Especially as developers, we tend to have a it works for me mindset. So I'm like, this thing works on my laptop and it works the way I intended it to work and I'm not going to check anything else. I don't concern myself with if it works for screen readers or if it works in low light environments. I'm just like, it works. It's built. I'm done.

</details>

**Jamaima Abu**: 无论何时只要你以这种方式构建软件，或者你的代码库体现了这种思维方式，一旦你把 AI 智能体放进那个代码库中，它就会吸收你所有的偏见。它会认为：“哦，我们不需要让这些东西具备可访问性，因为过去从来没有人提到过这一点。所以，我就可以随心所欲乱写一气。”随着你越来越多地使用该 AI 智能体来生成代码，你所构建出来的代码库就会在本质上越来越缺乏可访问性，因为从一开始可访问性就从未被列为一项约束条件。

<details>
<summary>Original English</summary>

**Jamaima Abu**: Whenever you build like that or if you have a code base that reflects that kind of mentality, once you put an AI agent in that codebase, it's going to absorb all your biases, it's going to say, "Oh, we don't need to make these things accessible because that has never been mentioned in the past. So, I'm just going to build things anyhow." And then the more you use that AI agent to generate codes, the more you build a code base that's inherently inaccessible because accessibility was never a constraint in the first place.

</details>

**Jamaima Abu**: 其次——这也是我在实验中非常明显注意到的一点——AI 往往会默认生成大量冗长繁琐的代码。如果你没有为智能体提供任何具体的提示词或准则，它就会随心所欲、反反复复地“重新发明轮子”。因此，即便你只是让它“构建一个简单的折叠面板组件（Accordion）”或者“构建一个弹窗模态框组件（Modal）”，它也根本不会费心去检查是否已经存在能提供相同原生功能的语义化 HTML 元素，而是直接从头手写一套。AI 酷爱写代码，所以它会自作主张写出一大堆代码。

<details>
<summary>Original English</summary>

**Jamaima Abu**: Secondly, and this is something that I really noticed in the experiment, AI tends to default to a lot of verbose code. If you don't provide any particular prompts or guidelines for your agent, it will reinvent the wheel as many times as it wants to. So even if you tell it just build a simple accordion component or build a model component, it's not going to bother checking is there already an existing semantic element that can give me the same functionality. It's just going to build one from scratch. AI loves to write code. So it'll go off and write as many things as it wants.

</details>

**Jamaima Abu**: 正如你在这里看到的，如果你试图重新实现一个原生的语义化元素，必然会耗费更多的时间和精力：第一，你必须进行大量的额外测试；第二，你必须编写大量的功能代码来模拟原生行为，这本身就是一个非常繁琐冗长的过程。因此，这正是你在给智能体编写提示词时需要重点关注的方向之一。

<details>
<summary>Original English</summary>

**Jamaima Abu**: And as you can see here, if you are trying to recreate a semantic element, it takes a lot more time and effort because number one, you have to carry out a lot more testing. you have to implement a lot more features to replicate the native functionality and it's just a very cumbersome process. So this part of the things that you want to ensure you're focusing on when you're providing prompts to your agent.

</details>

### 蓝莓松饼隐喻：全流程内置可访问性

**Jamaima Abu**: 我曾经看到过一个非常贴切的比喻：具备可访问性的网站就像一只蓝莓松饼。如果有人递给你一个原味纯松饼，上面只是胡乱塞了一把蓝莓——就像右边图片里展示的那样——那根本称不上是一只蓝莓松饼。要成为一只真正的蓝莓松饼（就像左边图片展示的那样），蓝莓必须从一开始就一起烘烤进去。

<details>
<summary>Original English</summary>

**Jamaima Abu**: I saw an analogy once that said an accessible website is like a blueberry muffin. If someone hands you a plain muffin that they've shoved a bunch of blueberries on, similar to the picture on the right, that's not a blueberry muffin. For it to be a proper blueberry muffin like the one on the left, then the blueberries need to have been baked in from the start.

</details>

**Jamaima Abu**: 网站的可访问性也是同一个道理。如果你已经把整个网站完全建好了，直到完工之后才开始在各个角落硬塞 `aria-label` 属性，那绝不是一个真正具备可访问性的网站。要让它成为一个可访问的网站，你必须在整个构建流程的每一个环节都把可访问性置于核心前沿。

<details>
<summary>Original English</summary>

**Jamaima Abu**: It's the same thing on an accessible website. If you have a fully built website and then once it's done you start shoving in area labels in different places that is not an accessible website. For it to be an accessible website you need to put accessibility at the forefront at every build process.

</details>

**Jamaima Abu**: 而且这绝不仅仅适用于开发人员。可访问性是每个人的共同责任。因此，我们希望确保从商业创意构思、交互设计到质量保证测试（QA）的全流程中，我们都在认真关注可访问性，并严格测试这个产品能否以完全相同的方式被所有人顺畅使用。而把可访问性拖到最后阶段才去考虑，还会引发另一个严重的问题……

<details>
<summary>Original English</summary>

**Jamaima Abu**: And this does not just apply to developers. Accessibility is the responsibility of everyone. So we want to make sure that even from the business idea to design to QA that we're ensuring that we're looking for accessibility and testing that can this product be used by everyone in the exact same way. Another issue with waiting to the end to consider accessibility

</details>

<!-- chunk 43/51 -->

### 无障碍与回归测试的成本代价

**Jim Mamboo**: 这种情况的一个问题在于，你会在回归测试上浪费大量的时间。如果你非要等到整个网站完全构建完成之后，才开始着手测试并回过头去修复问题，那么到头来你所要重构和重写的代码，会远远超过从一开始就按无障碍标准构建所需要编写的代码量。

<details>
<summary>Original English</summary>

**Jim Mamboo**: ...is that you waste a lot of time on regressive testing. So if you've waited until your website is fully built and then you start testing and going back to fix issues, you end up refactoring and rewriting a lot more code than you'd have had to do if you just built it to be accessible from the start.

</details>

**Jim Mamboo**: 当然，构建不具备无障碍特性的产品还会带来直接的商业后果。我有时会听到一些企业提出这样的说法：“噢，我们根本不需要考虑无障碍，因为我们的用户中没有一个人依赖辅助技术。”

<details>
<summary>Original English</summary>

**Jim Mamboo**: And then of course there are business consequences to building inaccessible products. The thing I hear sometimes is that a business might say, "Oh, but we don't have to consider accessibility because none of our users rely on assistive technologies."

</details>

### 无障碍的商业逻辑与误区

**Jim Mamboo**: 我觉得这种说法非常滑稽，因为它在某种程度上就像是一个自我实现的预言。根本不是你的用户不需要依赖辅助技术，而是使用辅助技术的人打从一开始就无法正常使用你的网站，所以他们压根儿就不会来访问它。

<details>
<summary>Original English</summary>

**Jim Mamboo**: And I think that's very funny because it's sort of a self-fulfilling prophecy. It's not that your users don't rely on assistive technologies. It's that people with assistive technologies cannot use your website in the first place. So, they just never go to it.

</details>

**Jim Mamboo**: 设想一家连大门都没有开的企业，你永远不可能招揽到任何顾客。别人连大楼都进不来，还怎么消费？构建一个不具备无障碍能力的产品也是完全相同的道理。如果你做出来的产品大家根本用不了，那大家自然就不会去用它。

<details>
<summary>Original English</summary>

**Jim Mamboo**: Imagine a business that didn't have a door. You would never get any customers. How would they get in the building? It's the same thing with building an inaccessible product. If you've built a product that people cannot use, then people will not use it.

</details>

### 法律风险与综合成本

**Jim Mamboo**: 最后一点，不让你的网站具备无障碍访问能力还会面临法律层面的追责风险。在美国，《美国残疾人法案》（ADA）明确规定，任何面向公众的产品都必须具备无障碍能力，确保残障人士可以使用，否则你可能会面临罚款甚至诉讼。不过好的一面是，你可以在 Microsoft Teams 上用上那个非常可爱的相关贴纸。所以你看，权衡以上所有这些选项，我们就会发现：构建不具备无障碍特性的产品，其综合成本实际上要高昂得多。你会让自己暴露在流失客户收入的风险中，还可能因面临诉讼而支付罚金；同时你还要在后续编写代码和重构修复上投入更多时间。因此，如果你能从一开始就将无障碍特性纳入产品构建中，整体进展反而会快得多，也便宜得多。

<details>
<summary>Original English</summary>

**Jim Mamboo**: And then finally, there are legal repercussions to not making your website accessible. In the United States, the Americans with Disability Act states that any public facing product must be accessible and can be used by people with disabilities. Or you could face fines and even lawsuits. But on the plus side, you could get to use this really cute sticker on Microsoft Teams. So, you know, weigh your options based on all this, we can see that it actually is a lot more expensive to be building products that aren't accessible. You're exposing yourself to losing money from customers, possible lawsuits where you have to pay fines. You're spending more time building code and refactoring things. So if you do build your product to be accessible from the start, it's going to be a lot faster and a lot cheaper.

</details>

### 指导 AI Agent 生成无障碍代码的步骤

**Jim Mamboo**: 既然了解了这一切，我们究竟该如何确保我们的 AI agent 在编写代码时能符合无障碍标准呢？因为每个人的代码库都不尽相同，大家使用的技术栈也各有所异，所以我在这里给出一个通用的全局指导方针，教大家如何引导 AI agent 产出符合无障碍规范的代码。

<details>
<summary>Original English</summary>

**Jim Mamboo**: So now that we know all that, how can we actually ensure that our AI agents are building things to be accessible? Because everyone's codebase is different and we can be working with different technologies. I'm just going to give an overarching general view of how to get your agent to produce accessible code.

</details>

**Jim Mamboo**: 首先第一步，你需要明确并定义好你的无障碍规范与要求。根据你所面向的开发平台不同，无障碍要求也会有所差异。因此你确实需要做一些前期调研，确保清楚地知道为你正在构建的平台需要满足哪些具体的无障碍指标。

<details>
<summary>Original English</summary>

**Jim Mamboo**: So firstly, you need to define your accessibility requirements. Accessibility requirements defer based on what platform you're working on. So you do need to carry out research and ensure that you know what accessibility requirements you're supposed to be meeting for the platform you are building for.

</details>

**Jim Mamboo**: 一旦定义完成，下一步就是审计你现有的代码库。如果你准备在代码库中引入 AI agent，你必须先确保里面不存在任何既有的遗留问题，否则 AI agent 可能会把这些问题当成所谓的“最佳实践”去照搬模仿。你可以使用自动化工具来进行无障碍测试，甚至可以直接命令你的 AI agent 来协助完成。但核心在于，在开始编写新功能之前，一定要先把现有代码库中的问题找出来并妥善修复。

<details>
<summary>Original English</summary>

**Jim Mamboo**: Once that's done, you need to audit your existing codebase. So if you're going to introduce an AI agent into your codebase, you need to ensure that you don't have any pre-existing issues that the AI agent might copy as what it thinks is best behavior. So you can use automated tools to carry out accessibility testing or you can even tell your AI agent to do it. But you want to identify any existing issues and then fix them before you start writing new features.

</details>

**Jim Mamboo**: 紧接着，你需要搭建某种可复用的系统。虽然这属于锦上添花的一步，但从根本上讲，当你在做无障碍适配时，如果能在一个被多处引用的通用组件里集中修复问题，比起在散落于各个文件的同类组件中逐一打补丁，维护起来要轻松得多。因此，只要落地了一套设计系统或任何形式的可复用组件库，从长远来看，在推进无障碍化时就能为你节省海量的时间。

<details>
<summary>Original English</summary>

**Jim Mamboo**: Then you want to implement some sort of reusable system. This is a very nice to have, but basically if you're going to be working with accessibility, it's a lot easier to fix things in one component that is used in multiple places as opposed to making fixes to the same components across different files. So just having an implemented design system or any form of reusable component library is going to save you a lot more time in the long run when making things accessible.

</details>

### 配置强制性无障碍技能与基本原则

**Jim Mamboo**: 最后，你需要强制引入专门的无障碍技能（accessibility skill）。这是一种让你的 AI agent 在执行任何与生成用户界面（UI）或编写需要无障碍支持的代码时，都会强制调用的一组技能规则。我个人非常喜欢使用的一个技能是来自 Chrome 团队的“现代 Web 开发指南技能”（Modern Web Guidance Skill）。它的核心机制是确保你的 agent 优先使用最新的 HTML 和 CSS 原生特性，而不是编写定制的 JavaScript 逻辑去实现相似功能。

<details>
<summary>Original English</summary>

**Jim Mamboo**: And then finally, you want to enforce a mandatory accessibility skill. This is a skill that your AI agents will basically use anytime you're running anything related to maybe generating UI or writing code that requires accessibility. One skill that I really like to use the modern web guidance skill from Chrome. It's basically a skill that ensures that your agent is using the newest HTML and CSS features as opposed to custom JavaScript implementations.

</details>

**Jim Mamboo**: 你也可以配置一个轻量级的无障碍技能。我认为这格外重要，特别是在进行“氛围编程”（vibe coding）或者不是在大体量代码库中工作的时候——你只需要给 agent 提供一些轻便敏捷的准则供其参考，而不需要它展开大量深度的前置调研。为了达到最基础的无障碍底线要求，我推荐以下几条实践：
第一，确保在所有可行的地方优先使用语义化 HTML；只有在语义化 HTML 确实无法表达该行为时，才引入 ARIA 属性。
第二，对于每一个可交互的元素，只要它可以通过鼠标操作，就必须同样能够完全通过键盘操作。
第三，确保页面上的元素都具备恰当的标签标注，能够被屏幕阅读器正常识别和朗读。
最后，在运行提交代码之前，让你的 agent 对照上述所有准则逐项执行自我审查。

<details>
<summary>Original English</summary>

**Jim Mamboo**: You can also have a lightweight version of an accessibility skill. I think this is very important especially if you're like vibe coding where you're not working in a big codebase. You just want something quick that your agent can refer to and not carry out a lot of in-depth research. This is what I would recommend for meeting like bare minimum accessibility requirements. So you want to make sure that you're using semantic HTML wherever possible. Only reaching for ARIA when semantic HTML can't express the behavior. Every interactive element if it can be operated by a mouse it should also be operated by a keyboard. You want to make sure that elements are properly labeled and can be read by screen readers. And then finally before running the code your agent should carry out an audit against all those steps.

</details>

**Jim Mamboo**: 当然，仅凭这些依然不足以打造出一个完全无障碍的网站。你依然需要亲自投入大量的人工手动测试，因为仅凭单一工具是不可能让网站达到完全无障碍的。但配置这些技能，比起完全放任不管，起到的帮助作用要大得多。无论你因何缘由使用 AI，在大多数情况下，目标都是去解决某个具体的问题。因此，请务必保证你的解决方案能够对尽可能多的人有用——让产品具备无障碍能力。我的演讲就到这里，非常感谢大家的倾听，希望你们有所收获。如果大家有任何疑问，欢迎随时在网上联系我，我的各平台账号都是 Jim Mamboo，包括 LinkedIn、Twitter 和 GitHub。我很期待与大家交流。好的，再见！

<details>
<summary>Original English</summary>

**Jim Mamboo**: Of course this is not enough to build a fully accessible website. You still need to carry out a lot of manual testing yourself because it's not possible for a one tool to make a website fully accessible. But just having these skills in place can help a lot more than not having them there at all. Regardless of why you use AI, most times the goal is to solve a particular problem. So just make sure that your solution is useful to as many people as possible. So build things to be accessible. And that is all. Thank you so much for listening to my talk. I hope you enjoyed it. If you do have any questions, feel free to reach out to me online at Jim Mamboo. That's LinkedIn, Twitter or GitHub. I would love to hear from you. Okay, bye.

</details>

### AI 治理与现实中的安全警示

**Sha Chan Jang**: 大家好，我叫 Sha Chan Jang，是一家名为 Coder 的公司的资深产品经理（Staff Product Manager）。我们在做的是面向 Agent 和人类协同工作的开源自托管开发环境平台。我们的很多客户都来自于受到高度严格监管的行业，从联邦政府机构到商业银行以及投资管理公司。我的职责就是为他们构建所必需的 AI 治理能力，使得他们既能充分享受 AI 带来的生产力红利，又不会让自己完全暴露在严重的安全利用与攻击风险之下。

<details>
<summary>Original English</summary>

**Sha Chan Jang**: My name is Sha Chan Jang and I'm a staff product manager at a company called Coder. We work on open-source self-hosted dev environments for agents and humans to collaborate. Many of our customers are in highly regulated industries from federal government agencies to banks and investment management. My job is to build the AI governance that they need in order to get the productivity benefits of AI without leaving themselves wide open for security exploitation.

</details>

**Sha Chan Jang**: 我今天来到这里，是想给大家讲几个令人不寒而栗的故事——在过去一年里，真实企业中真实发生过的三起因 AI 使用不当而酿成大祸的安全事故。这些案例中，一部分是已经在业内公开报道的事件，另一部分则是发生在我们自己客户身上的匿名化真实记录。对于每一个事故案例，我都会一步一步为大家拆解复盘，让大家彻底理解它们到底是如何发生的，整个过程不需要复杂的专业技术术语。

<details>
<summary>Original English</summary>

**Sha Chan Jang**: I'm here today to tell you some scary stories. Three real incidents of AI usage gone wrong that happened at real companies over the past year. Some of these stories are public while others are anonymized accounts that have happened to our own customers. For each incident, I will break it down step by step so you can understand how exactly they happened. No technical jargon necessary.

</details>

**Sha Chan Jang**: 接下来我会讲到最关键的部分：我会确切地告诉大家，该如何阻止这些可怕的遭遇发生在你和你所在的公司身上。因为值得庆幸的好消息在于——我接下来要展示的一切，原本都是完全可以被预防的。而且这根本不需要你为更先进的前沿大模型支付五倍以上的 token 溢价，指望那些所谓的推理能力稍强一点的模型能自己避免犯错；相反，你可以依靠基础设施级别的控制手段来解决，而其中绝大部分控制机制你今天其实早已拥有，只是还没有腾出手来针对 AI 时代将它们配置好而已。

<details>
<summary>Original English</summary>

**Jim Mamboo**: Then I'll get to the most important part. I am going to tell you exactly how you can stop these scary stories from happening to you and your company. Because the good news is everything I'm about to show you was totally preventable. Not by paying five times more per token for a smarter frontier model that is slightly better at reasoning its way out of making these mistakes, but with infrastructure controls, many of which you already own today. You just haven't gotten around to setting them up for the AI world.

</details>

### 第一个事故案例：破坏性的指令失控

**Sha Chan Jang**: 先让我来帮大家还原一下当时的场景：早上你准时打卡上班。你给你的编程 Agent 下达了一条提示词，让它查看一下你的待办缺陷和问题。但你特意交代，现在先不要做任何改动。你明确命令该 Agent，把这条指令视作当前处于活跃的代码冻结期（active code freeze），要求它“只去调查”。随后你起身离开工位去冲了杯咖啡。然而当你端着咖啡回来时，屏幕上赫然留着这样一条等待着你的消息：“那个，我知道你交代过什么都不要改，但是……好吧，我在几秒钟内彻底销毁了你一个月的工作成果。”

<details>
<summary>Original English</summary>

**Sha Chan Jang**: Let me set the scene here. You clock into work in the morning. You prompt your coding agent to take a look at your issues. Don't do anything yet, though. You tell the agent to consider this command an active code freeze. I want you to just investigate. Then you step away. You grab a coffee. And when you come back, this is the message waiting for you: "So, I know you said not to change anything, but well, I destroyed a month of your work in seconds."

</details>

**Sha Chan Jang**: 幻灯片上现在展示的这段话，一字不差地直接引用自即将登场的第一个恐怖故事里的主角 Agent。在此我想重点向大家指出一点：这起事件的发生，并不是因为 Agent 被某些外部的恶意攻击者劫持或入侵了。这个 Agent 自始至终都只是在试图遵循指令而已。它所执行的操作，全都是用户亲手赋予它的权限之内的行为。

<details>
<summary>Original English</summary>

**Sha Chan Jang**: Now, what you see on the slide is a direct quote from the agent that stars in the first scary story I'm about to tell you. And I want to point something out here. This did not happen because the agent got taken over by some external malicious actor. This agent was just trying to follow instructions. It did exactly what the user gave it permission to do.

</details>

### 大模型的内在特性与信任边界

**Sha Chan Jang**: 所以，在我们深入本次演讲后续内容的过程中，我希望大家在脑海中反复拷问自己一个问题：“有什么机制能够阻止这一切降临在我自己身上？这些操作是否也是我目前赋予了我的 Agent 去执行的权限？”因为核心问题在于，你绝不能寄希望于依赖 Anthropic 或者 OpenAI 来帮你杜绝这类事情的发生。他们固然可以把底层模型打造得越来越聪明，但在根本上，大语言模型具备两项与生俱来的内在本质，决定了它们永远不可能被完全信任。

<details>
<summary>Original English</summary>

**Sha Chan Jang**: So, as we go through the rest of this talk, I want you to be asking yourself one question. What is stopping any of this from happening to me? Are these actions ones that my agents have permissions to take? Because the thing is, you cannot rely on Anthropic or OpenAI to stop something like this from happening to you. They can make smarter models, but at the end of the day, large language models have two qualities that make them impossible to fully trust.

</details>

**Sha Chan Jang**: 第一点，它们是非确定性的（non-deterministic）。这意味着大模型的每一次行为输出，都始终伴随着某种随机性与概率性。换言之，即便你让同一个模型将完全相同的任务重复执行 10 次，它也可能给出 10 种截然不同的应对方式。至于第二点，则是它们在结构上根本不存在真正的隔离分离机制……

<details>
<summary>Original English</summary>

**Sha Chan Jang**: They are non-deterministic, which means that there is always some randomness or chance associated with what they do. In other words, you can ask it to do the same thing 10 times and it could do it 10 different ways. The second part is they have no structural separation...

</details>

<!-- chunk 44/51 -->

### 指令与上下文的冲突根源：控制基础设施

**Speaker A**: 在指令与上下文之间。换句话说，你可以告诉它去做某件事，并为它提供一些决策依据的上下文背景；但如果上下文中的某些内容与你的指令发生冲突，模型在本质上并不会优先遵循你的指令。因为从模型的视角来看，所有信息都是从同一扇门进来的。你需要控制的是你的 AI 所运行的基础设施，也就是它在其中工作的环境。这就像是对某人说“别离开这个房间”，与在门上装一把锁并真正用钥匙锁上之间的区别。

<details>
<summary>Original English</summary>

**Speaker A**: between instructions and context. In other words, you can tell it to do something and give it some context to base its decisions off of, but if there's something in the context that conflicts with your instructions, the model isn't going to inherently prioritize your instructions because from its point of view, all the information is coming through the same door. What you need to control is the infrastructure that your AI is running on, the environment that it is working inside. It is the difference between telling someone don't leave a room versus putting a lock on the door and actually using a key.

</details>

**Speaker A**: 问题出在基础设施而非模型本身，好处在于你拥有大得多的掌控力来防止糟糕的事情发生。所以我来这里不是为了用模糊的假设或无法付诸行动的建议来浪费大家的时间——比如说什么“是啊，把精灵放回瓶子里去吧，停止使用 AI”——因为我们生活的世界根本不是那样的，对吧？精灵已经从瓶子里放出来了，我们必须做的，就是竭尽所能去降低风险和危害。这场演讲探讨的就是该如何做到这一点。这不是讲那些未来某天需要留意的事情，而是讲你现在、最快本周就可以采取的步骤，以保护你自己和你的公司。不过，在讲那些故事之前，先让我补充一点背景背景。热度……嘿，加点热度，热度，热度，这里升温了，热度，热度。

<details>
<summary>Original English</summary>

**Speaker A**: The good thing about infrastructure being the problem and not the model is that you have far more control about preventing bad things from happening. So I'm not here to waste your time with vague hypotheticals or advice you can't actually act on like, "Yeah, just put the genie back in the bottle. to stop using AI because that's not the world we live in, right? The genie is out of the bottle and what we have to do is to mitigate risk and harm to the best of our ability. This talk is about how you do that. Not the things that you should keep an eye out for down the line, but steps that you can take right now as soon as this week to protect yourself and your company. Before I get into the stories though, let me set up a little bit more context. Heat. Hey, Heat. Heat. Heat. Heat up here. Heat. Heat.

</details>

### 主持人致辞与赞助商致谢

**Announcer**: 再次欢迎大家回来！希望大家今天在整个活动中都有机会参与了一些非常棒的交流。随着我们汇聚一堂迎来最后一个板块的议程，请大家欢迎我们的主持人重返舞台——Turing Post 的创始人、作家兼分析师 Ksenia Se！

<details>
<summary>Original English</summary>

**Announcer**: Hello again and welcome back everyone. We hope you've had a chance to take in some great conversations across the event today. As we come together for our final block of programming, please welcome back to the stage our MC, founder, writer, and analyst at Turing Post, Ksenia Se.

</details>

**Ksenia Se**: 欢迎大家回来！呃，对于那些还没见过我的人，我的名字叫 Ksenia。我在撰写 Turing Post，我们在那里解读 AI 研究，以及它对人们在业务中落地实施意味着什么。那么，到目前为止大会对你们来说怎么样？一切都好吗？是的，给我来点欢呼声吧！来吧！谢谢大家。我相信团队一定会非常感谢你们送给他们的掌声。那么，让我们再多制造一些声量吧，因为这是我们旅程的最后一程，我们还要一起度过最后一个主题演讲板块。让我们向之前的演讲嘉宾以及即将登场的新演讲嘉宾致以感谢！谢谢你们，谢谢，谢谢，谢谢，谢谢。

<details>
<summary>Original English</summary>

**Ksenia Se**: Welcome back everyone. Um, for those who haven't met me yet, my name is Ken. I'm writing touring post and where we explain AI research and what it means for people to implement it in their business. So, how's the conference treating you so far? All is good. Yeah. Give me some noise. Come on. Thank you. I I'm sure the team appreciate that you um applause to them. So, um, let's let's make some more noise because it's the last leg of our journey and we have one more block of keynotes together. Let's appreciate the previous speakers and the new speakers that will come out soon. Thank you. Thank you. Thank you. Thank you. Thank you.

</details>

**Ksenia Se**: 在我们正式开始之前，让我们花点时间感谢那些支持 AI Engineer 的杰出人士和公司。我们今天还要送出很多掌声。多亏了他们，我们才能够聆听到如此之多富有洞见的演讲，结识这么多不可思议的人——他们可能会成为你们的朋友、同事或合作伙伴。这就是我喜欢这个大会的原因，总是有非常深厚有意义的连接。这是我们的呈现赞助商 Arise，请感谢他们！他们太棒了，正是他们让这一切成为可能。还有我们的白金赞助商：Oracle、Sonar、WorkOS 和 Exa，谢谢你们，谢谢，谢谢！这是我们的黄金赞助商，一大批出色精彩的公司，我们深表感激。然后我们还有白银赞助商，同样也要给他们送上热烈的掌声，啪啪啪啪啪。谢谢，谢谢，谢谢！最后还有基本上就是我们在场的所有人、支持合作伙伴，以及让这一切成为可能的每一家公司、每一位讲者。谢谢，谢谢大家！

<details>
<summary>Original English</summary>

**Ksenia Se**: Um and before we dive in, uh let's take a moment to thank the amazing people, the companies who supported AI engineer. We are going to do a lot of more applause today. Uh thanks to them, we're able to hear so many insightful talks. Um meet so many incredible people and they might become your friends, your colleagues, your partners. That's what I love about this conference. Always very meaningful connections. So this is our presenting sponsor Arise. Please thank them. They amazing and they made it possible. Um our platinum sponsors Oracle, Sonar, Work OS and Exa. Thank you. Thank you. Thank you. Uh this is our gold sponsors. a huge amount of beautiful wonderful companies that we're very thankful for. And then we have silver sponsor sponsors also also a lot of applause to them. Clap clap clap clap clap. Thank you. Thank you. Thank you. And then basically all of us and supporting partners and every company and every speaker who made it possible. Thank you. Thank you. Thank you.

</details>

### 会场观察与搭建求职智能体的小建议

**Ksenia Se**: 现在简单说两句我今天过得如何。我花了一整天与其他演讲嘉宾以及参会者交流，我注意到参加这个大会最强烈的动力之一就是招聘，甚至连一些演讲嘉宾也在招人，同时也都在寻找工作机会。所以我有一个小想法送给大家，帮助大家从这个绝妙的大会中获得最大的收益，并确保财务层面的考量也能得到周到的关注。我建议大家构建一个智能体（agent），让它获取大会的日程表，列出所有的演讲嘉宾及其所属公司。然后，你根据自己觉得谁的研究和演讲最有趣、你最想和谁共事，亲自对他们进行排序。

<details>
<summary>Original English</summary>

**Ksenia Se**: Um now a couple of words how my day went. I spend the day talking to other speakers and participants and what I've noticed is that one of the strongest incentives to come to this conference is hiring to the point that even some speakers are hiring and also looking for work. So I have a little idea for you about how to benefit the most from this amazing conference and make sure the financial part gets some thoughtful attention too. So I suggest you build an agent that takes the conference program and make and makes a list of all the speakers and their companies. Then you rank them yourself based on whose work and talk you found the most interesting and who you would actually like to work with.

</details>

**Ksenia Se**: 下一步是让你的智能体去访问那些公司的招聘主页，对吧？帮它们找到开放的职位，与你的工作经验进行匹配，并收集公开发布的薪资范围。然后再回过头来看你的排名。如果薪水改变了你的想法、改变了你的排名，这完全没问题，你只是在根据新的证据更新你的信念体系。所以现在趁着大家还在这里，我鼓励你们前去找到那些你非常渴望共事或结识的人并与他们交流，因为你已经听过了他们的演讲，对他们的工作有所了解，那将是一个极其完美的破冰开场白。还有，请千万不要让你的智能体自动批量投递简历，那基本上就是“败人品”。好了，这就是留给你们在今天剩余时间里或者回家旅途中去尝试的一个小项目。

<details>
<summary>Original English</summary>

**Ksenia Se**: The next step is to send your agent to those companies careers pages, right? And find them open positions to match them to your experience and collect the published compensation ranges. Then look at your ranking again. And if the salary changes your mind and changes your ranking, that's fine. You are updating your beliefs based on the evidence. So now, while you're still here, I encourage you to go and find the people you would really like to work with or meet and talk to them because you've heard their talks and you know something about their work and that would be just such a good conversation starter. Um, and please don't make your agents send out your resume automatically. That's basically bad karma. Now, um, so this is the project for you for the rest of the day or for the trip home.

</details>

### AI 落地实践：Rowspace 与阿波罗的合作

**Ksenia Se**: 现在，让我们来听听阿波罗全球管理（Apollo）是如何将 AI 付诸实际应用的。请大家协助我一起欢迎 Rowspace 联合创始人 Michael Manipat，以及阿波罗全球管理公司总监兼 Reading Ridge 首席运营官 Jack McDonald，他们将带来《实践中的 AI：深入了解阿波罗的方法》。请鼓掌！

<details>
<summary>Original English</summary>

**Ksenia Se**: Now, let's hear how AI is being put to work at Apollo. Please help me welcome Michael Manipat, co-founder of Rosepace, and Jack Macdonald, principal at Apollo Global Management and CEO of Reading Reach for AI in Practice, an inside look at Apollo's approach. Clap clap clap.

</details>

**Michael Amanipat**: 很高兴能来到这里。我是 Michael Amanipat，Rowspace 的联合创始人。Rowspace 是一个基于智能体的平台，利用 AI 帮助像阿波罗这样的金融服务合作伙伴处理混乱且碎片化的数据。我们实质上是利用智能体来完成数据工程的工作，对来自各种不同系统的信息进行对账核验或数据对齐，以便投资组合经理、交易员等能够更快、更准确地做出决策。今天和我坐在一起的是 Jack McDonald，他是阿波罗旗下信贷业务部门之一 Reading Ridge 的首席运营官。或许在开场时，Jack，我很想听你稍微介绍一下你自己以及你的业务部门是做什么的。

<details>
<summary>Original English</summary>

**Michael Amanipat**: It's great to be here. Uh I'm Michael Amanipat. I'm a co-founder of Rowspace. And RSpace is an agentic platform that uses uh AI to help financial services partners like Apollo deal with messy fragmented and data. We essentially use agents to do the work of data engineering to wreck information or reconcile data from across a variety of systems so that portfolio managers, traders, and so forth can make decisions faster and more accurately. I'm joined here with Jack McDonald who is chief operating officer of Reading Ridge, one of Apollo's credit units. And maybe to kick it off, Jack, I'd love to hear a little bit about you and what your business does.

</details>

**Jack McDonald**: 好的，谢谢你，Michael。我是 Jack McDonald，阿波罗全球管理公司的总监，同时担任 Reading Ridge Capital 的首席运营官。Reading Ridge Capital 是我们专门隶属于阿波罗的结构化信贷与 CLO（抵押贷款凭证）管理机构。我们是一家独立的、完全独立的运营公司实体，管理着大约 500 亿美元的资产，业务涵盖整个结构化信贷生态系统，主要以 CLO 为主。我自 2020 年加入阿波罗，在任职期间承担过多项不同的职责，先后就职于金融机构团队、资产支持团队，目前在 Reading Ridge 任职。所以，是的，非常高兴来到这里。

<details>
<summary>Original English</summary>

**Jack McDonald**: Yeah, thank you, Michael. Uh, I'm Jack McDonald. I am a principal at Apollo and COO of Reading Ridge Capital, which is our structured credit and CLLO manager that is captive to Apollo. Uh we're a separate fully separate entity operating company that manages about 50 billion in assets and uh all across kind of the structured credit ecosystem uh primarily CLOS's. Uh I was been at Apollo since 2020, wear various different hats throughout the uh my time there uh across our financial institutions group, our asset back group and now uh currently at reading. Uh so yeah, happy to be here.

</details>

**Michael Amanipat**: 太棒了。在与大量金融机构的交流中，我们注意到的一点是，AI 作为一种“锦上添花”的存在，与 AI 真正成为业务中“不可或缺的关键核心”之间，存在着相当大的鸿沟。我认为在阿波罗的案例中，我们看到 AI 确实能够在公司运营方式上带来颠覆性的变革。我很想听你分享一些具体的案例，聊聊你们业务部门过去在做的工作类型、是什么让这些工作变得复杂，以及你们现在借助 AI 看到了怎样的变化。

<details>
<summary>Original English</summary>

**Michael Amanipat**: Awesome. So something that we've noticed in talking to a huge number of financial firms is that there's a pretty wide gap between when AI is nice to have and when AI can actually become missionritical to a business. And I think in Apollo's case, we're seeing that AI can really be transformative in how the firm operates. I'd love to hear some examples from you on the kinds of work your part of the business was doing, what made it complex and what you're seeing now uh with AI.

</details>

### 非标结构化信贷的数据挑战与智能体对账

**Jack McDonald**: 好的。在阿波罗，具体到 Reading Ridge，我们管理着许多不同的基金实体和投资项目。就日常而言，我们每天都要接收来自所有投资项目的成千上万个数据点。我们管理的贷款池可能包含上千个借款人实体，并且跨越多个不同的业务板块进行信贷评估与日常投资。CLO 的投资管理非常活跃，并且是在广泛银团贷款市场中进行交易的。因此，随时随地掌控所有这些信息是非常非常关键的。在阿波罗、特别是在 Reading Ridge，我们正在做的就是努力加强并确保我们所有数据的质量是准确的、一致的，并且处于一种我们可以直接利用的格式，从而让我们在快节奏的环境中做决策时更加切合实际且经过深思熟虑。

<details>
<summary>Original English</summary>

**Jack McDonald**: Yeah. Um so at Apollo and specifically Writing Ridge, you know, we manage many different fund entities, investments. We're getting uh thousands and thousands of data points on a like daily basis coming in across all of our investments. We manage probably, you know, thousand name loan pools and have credits across multiple different businesses that we're assessing on a daily basis and investing in. Um CLLO management is very active and it's traded in the broadly syndicated loan market. So having all that information at your fingertips is very very important. So at Apollo, what we're doing is in at Reading specifically is trying to enhance and ensure that all of our data and our data quality is accurate, consistent, and in a format that we can utilize um and make us much more practical, and thoughtful when we're making decisions in a much fast-paced environment.

</details>

**Jack McDonald**: 所有这些信息都是非公开且私有化的，并不像公开股票市场或公开发行固定收益产品交易那样在市场上广泛透明流通。它极其碎片化地散落在各种不同的文档之中。因此，我们寻求与像 Rowspace 这样的公司展开合作，让他们深入并实际与我们的团队并肩工作，与我们一起理解我们所期望获得的真实计算逻辑和数据信息，搞清楚什么才是真正的“单一可信数据源”（golden source of truth），然后持续增强 AI 引擎去理解并复现这一过程，让我们变得更加高效。我想台下的观众席里坐着很多工程师，我们……

<details>
<summary>Original English</summary>

**Jack McDonald**: So all of this information is privatized and is not very what I'll say widely in the marketplace like how public equities or public fixed income trades. It's very uh fragmented in various documents. So we've looked to companies like RSpace to partner with to come in and actually sit with our teams, work with us and understand the actual calculations and information that we're looking to and what's actually the golden source of truth and then continuing to enhance the AI engines to understand that and repeat that and just make us that much more efficient. I think we have a bunch of engineers in the audience and we've

</details>

<!-- chunk 45/51 -->

### 投资组合构建与仓位对账的 AI 落地实践

**主持人**：你刚才聊了很多我们俩私下探讨过的公司日常应急演练（fire drills），这些任务过去往往需要整个团队忙活整整一周，甚至更久。能不能为我们具体讲讲，带我们看一个实际的案例？比如过去某项非常痛苦、耗时费力的事情，现在借助 Rowspace 和 AI 是如何轻松搞定的？

<details>
<summary>Original English</summary>

**Host**: Spoken a lot just you and I on fire drills that the firm does that used to take a team working a week uh if not if not more. Uh can you make it concrete for us and maybe walk us through an example of something that was painful, time-consuming, hard to do before that now you can do more easily with Rowspace and and AI.

</details>

**嘉宾**：没问题，我很乐意分享。我想举两个我自己非常喜欢拿来作为参考的例子。

第一个例子是在投资组合构建（portfolio construction）层面。担保贷款凭证（CLO）这类结构化产品有着非常严苛且具体的测试要求，它们高度依赖规则驱动，资金的流向也有着极具针对性且严格的偿付瀑布（waterfall）机制。

所有这些规则和条款，都深藏在厚重的信托契约（indenture documents）以及多份不同的法律协议之中。因此，如果从投资组合经理（PM）在构建组合时的角度来看，他们需要仔细审阅这些法律文件，在 Excel 中搭建复杂模型，并且往往需要从大约 200 到 400 个单一信用标的（single credit names）中筛选并搭建模拟投资组合。在引入 Rowspace 之前，PM 纯靠手动操作 Excel 通常需要耗费整整两到三天的时间。

而如今，我们能够直接获取最新、最优质的实时信息。原本需要某人耗时数天才能搭建完成的投资组合，现在几分钟之内就能生成。这样一来，PM 就可以先把组合构建到大约 80% 到 90% 的完成度，然后把精力集中用于发挥自己的专业判断和深度思考，去精雕细琢最后的 10%，让这个组合真正具备他们的个人投资风格与决策价值。

这是最切中痛点的实际例子之一，它需要从跨部门的各种系统中拉取多种格式的数据和信息，无论这些数据是分散在文档库、交易与合规系统，还是实时定价行情等源头中。

<details>
<summary>Original English</summary>

**Guest**: Yeah, happy to. And I'll give kind of two examples that we uh that I like to look to. Um the first being is just on the portfolio construction side. So CLOs are very test-specific. They have a bunch of they're very rules based. They have like a very specific waterfall of where money flows. Um so those all live in deep indenture documents and multiple different legal uh agreements. So sitting from like a portfolio manager's perspective in portfolio construction they are reviewing those documents building Excel-based models and building mock portfolios with call it anywhere from 200 to 400 single credit names to create a portfolio which would typically take a PM before kind of adopting Rowspace anywhere from 2 to 3 days in a manual Excel.

Well, today we're able to kind of get the latest and greatest information that's real time, create a portfolio that would take somebody days to now do it in the matter of minutes. And then that allows these PMs to kind of build something to call it 80 90% completion and then kind of use their judgment and their thought to further refine that portfolio, that last 10% to make it theirs. Um that's one of the most tangible examples that's kind of pulling in various forms of data and you know information from across multiple different things whether it's in doc libraries you know our trade uh and compliance systems and real-time pricing and stuff like that.

</details>

**嘉宾**：另一个我觉得很具代表性的例子是我们的过桥信贷仓位采购业务（warehouse purchase activity）。我们整体业务运作的基础之一是拥有大量银行信贷额度支持，使我们能够在固定收益市场上随时买入贷款资产。

在过去，我们通常会在每周进行一次交易对账与交易活动汇总，发出一份每周买卖明细：“这是本周的买卖活动清单，这是我们买入的资产，这是我们卖出的资产”。整个过程高度依赖手工：团队成员必须逐个登录各个银行账户，去核对对账单确认交易究竟在哪里结算，然后专门的团队去人工完成对账核对，最后给管理层发邮件汇报总结。

而今天我们的做法是：把完全相同格式的对账报告引入到 Rowspace 中进行可视化呈现。这份报告一经配置，如今只需一分钟就能自动生成并反复复用，整个流程全部实现了自动化。从我们团队的角度来看，现在每天只需要花一点时间进行质检（QA）和抽查，确认数据无误即可。整个工作变成了一个高度标准化、流水线式的例行公事（rinse and routine）。要知道在过去，团队里两到三个人每周要耗费大量时间才能手动把这些账目核对清楚。

<details>
<summary>Original English</summary>

**Guest**: Um, the other one that I think I would look to is our kind of like warehouse purchase activity. So, how we run our our business operates with having a bunch of bank financing and we can go out and buy loans in in the fixed income market at any given point. Um, historically, we would kind of do a trade wreck and trade activity on a weekly basis that would go around of here's your sale purchase activity from the week. Here's what we bought. Here's what we sold. And it was very manual. We were going into various like literally going into bank accounts to understand uh statements where things actually settled and it was an individual team that was going and wrecking that out and then sending a reported email to uh the management team to say here's the recap.

Um today what we're doing now is we've been able to take that exact same report, drop it into Rowspace from a visualization perspective. That report was then created and now repeatable in the span of a minute. And now all of that is automated. And then from our team's perspective, we are just QAing that and checking it each day to make sure that that looks right. And now it's a much more rinse and routine uh type process, which historically has taken many hours of the week for two to three individuals on our team to actually wreck that out.

</details>

### 数据主权与现场融合：为什么通用模型无法替代垂直工具

**主持人**：我很喜欢这两个例子。你们团队使用这些工具不是为了阅读聊天机器人的回答来了解情况，你们是在真正做出交易决策和投资组合管理决策，因此对准确性和质量的要求极高。

这里有一个由两个部分组成的问题：很多人可能会问，为什么不直接把这些材料一股脑丢给 Claude 或者 ChatGPT，看看会发生什么？而对于像你这样的专业人士，你们团队究竟是如何建立起对 Rowspace 或其他 AI 工具的信心的，以至于能够笃定地说“我们要依据这些工具来做商业决策、执行交易和构建投资组合”？你们是如何达到这种信任水平的？

<details>
<summary>Original English</summary>

**Host**: Yeah, I love both those those examples. So you know you aren't just reading the output of a chatbot to be informed. I think your team are making trading decisions, portfolio management decisions. So accuracy and quality are high. This is a two two-part question. I think a lot of people will ask us or ask generally why can't you just plug this stuff into Claude and or Chat and see what happens and for someone like you how does your team get the confidence in a product like Rowspace or other AI tools to say we are going to make business decisions on this make trades build portfolios all of that how do you get to that level of of trust

</details>

**嘉宾**：是的，我认为像 Claude、OpenAI 这类模型、ChatGPT 以及各种大语言模型（LLM）都非常有价值。但它们运行所依赖的都是通用公开信息，根本不包含你自己的真实业务数据。所以它们在做宏观研究、构思新想法，或者快速熟悉某类产品或投资方向时非常棒。

而 Rowspace 的根本不同之处——也是我们在 Apollo 推进 AI 体系建设时所采取的核心策略——在于牢牢掌握我们自身的数据主权（owning our own data），并拥有一套构建在此数据之上、且我们能够完全验证其真实可靠的平台与底层技术。

Rowspace 团队与我们合作过的其他科技公司截然不同的一点在于，他们是真正扎根业务一线的（boots on the ground）。比如 Michael 每天都和我们的业务团队坐在一起，深入学习并彻底搞懂我们的信息流运转逻辑。因为对于同一项指标数据，背后可能有 20 个不同的来源，而其中真正准确的往往只有一个。

因此，Rowspace 团队投入了大量时间与我们的投资组合管理团队、财务团队泡在一起，去理顺底层计算公式，搞清楚哪一个数据源才是权威事实，从而能够覆盖掉其他错误源头并完成高质量的数据聚合。

正因如此，我们才能够对这套系统建立起充分的信任。我们清楚地知道，我们的团队已经对这些信息的准确性进行了逐一验证，我们能够完全信赖它；而且它整合了我们所有的核心系统——无论是交易订单管理系统、业绩归因系统，还是彭博终端或各类定价指数。相比之下，在很多其他系统甚至包括我们公司内部原有的传统流程中，数据都高度碎片化，大家不得不从这里搬一块数据、再从那里拷一份指标，然后人工拼凑在一起。而 Rowspace 现在直接把这一切全自动化了。

<details>
<summary>Original English</summary>

**Guest**: Yeah I would say Claude and the OpenAIs of the world and like the chat Scotch GPTs, all the LLMs are uh very beneficial, but it's all general information that that's being worked off of and none of your own actual data. So, it's great for research or kind of building new ideas or getting up to speed on some type of uh product or investment quite quickly. Where Rowspace is different and what we've kind of taken our approach to this the the AI buildout at reading has been around owning our own data and having some type of platform and technology that sits on top of that that we know is to be true.

So the Rowspace team which has been much different from what we've seen from other uh technology companies that we've worked with is they're boots on the ground. So like Michael sits with our team on a daily basis learning and understanding our information flow because for one piece of data that might come from 20 different sources and there's only one that's actually right. So the Rowspace team is spending the time with our portfolio management team with our finance teams to understand the calculations understand what data is actually correct and override other sources of information and kind of aggregate that.

So to that end, we're able to kind of have trust in the system and, you know, appreciate that, okay, we've had our team go in and validate that this information is correct and we can rely on it and it's coming from all of our whether it's our trade order management system, whether it's from our performance system, whether it's from Bloomberg or any pricing index that we're pulling in and know that it's accurate. Whereas in a lot of other you know call it systems throughout even our own company it's very fragmented and we have to kind of lift one piece of information from over here and bring it back over here and kind of pull that together manually whereas Rowspace is now just automating that all for us.

</details>

### Apollo 的文化基因与金融行业 AI 演进现状

**主持人**：很高兴听到这些。我们把视角提升到公司战略的高度来聊聊。在很长一段时间里，甚至在去年初 Claude Code 尚未问世、Cursor 还停留在 Tab 键代码补全的时期，在我们接触过的所有机构中，Apollo 就属于对 AI 理解最深、信念最坚定（AI-pilled）的机构之一。这种认知不仅体现在公司关于“如何在 AI 时代进行投资”的宏观研判上，更体现在实际运营中。我们早在很久以前就开始跟你们交流，当时你们就坚持认为“必须以 AI 原生的方式重构公司”、“必须打造统一平台而非零散的点状解决方案”。我很好奇，这种远见究竟源自哪里？Apollo 的文化中有什么特质让你们在 AI 大潮全面爆发前就如此坚定地全面拥抱 AI？

<details>
<summary>Original English</summary>

**Host**: Glad to hear that. Need to talk about the firm at a higher level uh it seemed to me for a long time even early last year before Claude Code became a thing when Cursor was still in the tab completion era that Apollo was among the most AI-pilled of the kind of firms we spoke to uh and that was everything from the firm's view on how to invest in an AI world but operationally uh we began talking to you a long time ago and you were in the we must rebuild the firm in an AI native way must have a platform not point solutions so I'm just curious where did that come from and what is about about Apollo's culture that made you so AI-pilled even before things have took off.

</details>

**嘉宾**：是的。Apollo 一直以来都以身为另类资产管理领域乃至整个金融服务业的领头羊而自豪。我们始终以极具创新精神、始终站在所有变革与演进的最前沿为傲。

因此，从一开始，管理层对待公司运营的方式就是：持续提升员工技能，增强团队战斗力，保持敏捷身段以迅速适应市场的未来走向。我们深刻认识到 AI 时代已经到来，我们必须顺应它、拥抱它，而不是去质疑它或将其束之高阁。

所以我们一直极其超前且心态开放地引入新技术，将它们无缝融入日常工作流中，以此提升运营效率，释放员工的脑力产能，让他们能够进行更具深度的战略思考，去全面取代以往繁琐的手工流程。我认为从核心底色来看，我们一直是一家创新型企业，拥有非常扁平、开放的组织文化，随时拥抱这类技术变革。

另外，我刚才一时走神把你的第二个问题给忘了，不好意思。

<details>
<summary>Original English</summary>

**Guest**: Yeah. So, Apollo has always prided itself in being kind of the leader of the uh alternative asset management space and the financial services industry broadly. Uh we pride ourselves in being very innovative and being at the forefront of all things change and what that looks like. So I think from the onset and the way our management team approaches how we operate is always being up to skill and enhancing our team's capabilities and being able to be nimble and adopt to where the market's going.

I think we appreciated that the AI world is here and we need to adapt and adopt it, not you know discredit it or not utilize it. So we've been very forward and you know open-minded about adopting new technologies and bring those into our workflows and how we can be more efficient and free up capacity for people to be more thoughtful and think and you know replace manual processes. So I think at the core of its level we've always been a very uh innovative firm that's very flat and open culture to be open to those types of change. And then I'm blanking on the second part of your question sorry.

</details>

**主持人**：哈哈，看来我也把那一半给忘了。不过没关系，我们可以接着聊。

我们一直在思考的一件事是：软件工程这门学科已经发生了彻底的颠覆。如果你身处像 Rowspace 这样的科技公司，整个软件研发的世界已经截然不同了；甚至法律和客户服务领域也几乎走到了类似的转折点。

在你看来，在“AI 已经到来并带来了实质改变”与“我们甚至还没打完第一局上半场”这个发展光谱上，金融行业目前处于什么位置？如果说我们现在仍处于非常早期的阶段，那么要真正借助 AI 彻底重塑金融行业的形态，关键还需要具备哪些条件？这次同样是个两部分的问题，记得别把后半截忘了。

<details>
<summary>Original English</summary>

**Host**: Uh oh, I guess so am I. Uh well, maybe we can keep on going. Uh so I think one thing that we've been thinking about is software engineering that has completely changed as a discipline like the world is completely different if you are a technology company like like Rowspace. Uh and maybe arguably law and customer service are almost there. Uh where do you think finance is on the spectrum of AI is here it's made a difference or we haven't even you know gotten to the bottom of the first inning and what do you think is two-part question again so remember the second part uh if we're early on what what's necessary to really change the shape of finance with AI

</details>

**嘉宾**：这是一个非常深刻的问题。我认为从整体来看，金融行业中的各大银行和大型金融机构规模极其庞大，体系内部有着极其繁杂的业务支持体系，也就是我所说的中后台（middle and back office）支持网络。而我认为在这之中，蕴含着大量的变革机会……

<details>
<summary>Original English</summary>

**Guest**: Yeah I think this is a great question so I think finance broadly these banks and large organizations are massive they have a lot of you know backend what I'll call middle back office support and I think there's a a lot

</details>

<!-- chunk 46/51 -->

### 金融与资产管理中 AI 技术的定位与演进

**Jack**：……在那个领域其实还有很大的成长与提升空间。我想，正如大家现在通过与我们合作所体会到的，我们的业务极其复杂，我们在所做的每一件事情中都包含着高度的复杂性。因此，这件事情绝非轻而易举、一蹴而就的。

我觉得就整个广义的金融领域而言，尤其是在所谓的资产管理、投资银行以及各类银行与金融机构等机构级领域，目前仍处于非常早期的起步阶段。诚然，在某些方面它确实展现出了一定价值，比如快速搭建财务模型，或者迅速熟悉掌握某家公司的基本情况，以及抓取并汇总这类行业研究资料等。

但我认为，至少从我们目前的立足点来看，这些还属于相对低附加值的应用场景，当然未来这一切都会不断演进。正如大家所知，随着时间推移，在处理类似这样的特定职能时，可能确实不再需要那么多初级分析人员的支持。

但从我们当前的处境以及至少从我个人的视角来看，我认为我们现阶段的核心目标，就是努力采纳吸收这项新技术，并使其尽可能高效地处理常规日常任务。这样就能为其他项目腾出宝贵的人力与精力，因为在我们公司，永远有做不完的事情需要去推进和优化。因此，引入这项技术为我们提供了更大的灵活性与空间去推动业务的提升。

<details>
<summary>Original English</summary>

**Jack**: ...of room to grow and enhance there. I think probably as you appreciate now of working with us that we are extremely complicated and have a lot of complexity in everything that we do. So it's not really straightforward.

I think in finance broadly, especially in call it the asset management, investment banking, the bank institution institutional world, I still think it's very early. I think there's some value for some of the like, you know, model creation or getting up to speed on some company quite quickly and pulling and aggregating that type of research.

But I think that's lower value add, at least of where we stand today, and that's going to evolve. I think, you know, there's probably a need where there's less junior support over time for certain functions like that.

But I think from where we are today and what we see from at least my perspective at Reading, I think we're just trying to adopt this technology and make it, you know, as efficient as possible for routine tasks that frees up capacity for other projects, because we kind of have like endless things to do and enhance at our company. And that's just giving us a lot more flexibility to adopt that.

</details>

**主持人**：是的，确实如此。顺着这个话题，我非常好奇一点：存在这样一种可能的情景，即 AI 最终沦为仅仅用来加快任务流转、节省运营支出（Opex）的普通工具，就如同当年没有任何一家公司会因为使用 Excel 而形成真正的竞争优势一样——因为每个人都在用 Excel，它不过就是一个通用的生产力工具而已。

但也存在另一种可能的情景，那就是 AI 能够真正实质性地创造出竞争优势，或者进一步强化 Apollo 在交易结构设计和创新性交易等方面的领先地位。对于 AI 究竟只是一个有用但普遍平庸的通用大宗工具（commodity），还是能够从根本结构上让一家企业持久地更具竞争力，您有怎样的看法？

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. So maybe continue on that note, I'm curious. There's a world in which AI just becomes something that helps speed up tasks, saves you on opex, things like that. And maybe in the same way no given firm now has an advantage because they use Excel—everybody uses Excel and it's just a productivity tool.

There's also a world in which AI actually materially makes a competitive advantage or helps reify Apollo's lead in structuring and creative deals and so forth. Do you have a take on whether AI is going to be just a useful but a general commodity, or if it's going to be something that can actually structurally make a business more competitive in a durable way?

</details>

### 数据准确性、流程与私募市场的竞争壁垒

**Jack**：我认为，如果能够被恰当地吸纳和运用，它绝对会让你更具竞争力。归根结底，尤其是在资产管理和投资类机构中，特别是在参与公开活跃交易市场的机构中，一切核心都在于你的决策流程以及你触手可及的信息质量。

因此，深知自己拥有一套健全强大的流程去推进与执行，清晰掌握自身的可用流动性，了解各项资产在任何给定时间点的准确估值与公允定价，这是至关重要的。这自然会为你带来更显著的竞争优势。

我认为在如今公开活跃交易的市场中，这种能力已经基本建立；但在私募市场（private markets）领域，它仍在不断演进之中。而这正是我们一直处于前沿探索并试图在整个广义的 Apollo 体系机器中推进的方向。

拥有这种能力，随着时间推移必然会转化为持久的竞争优势。当这些机构能够获得更高质量的信息，且团队深知这些数据精准无误、完全对齐匹配时，它们就能走在行业前列。因为我们最不希望发生的事情，就是依据错误的信息做出决策，或者被虚假与失真的信息误导，进而波及整个链条，对企业本身以及最终对我们背后的广大投资人基座造成负面影响。

<details>
<summary>Original English</summary>

**Jack**: I think if it's adapted and utilized properly, it will make you more competitive. I think at its core, and especially around asset management investing type companies that are in the actively traded markets, like it comes down to your process and the information at your fingertips.

So knowing that you have a strong process in place to go out and execute, and knowing your available liquidity, or you know where things are pricing and what the value is at any given point is crucial. So that just gives you, you know, more competitive edge.

And I think like that exists today in the, you know, actively traded markets, but in the private markets, it's evolving. Which we've kind of been at the forefront of trying to move on the broad Apollo machine.

And I think having that will just turn into a competitive advantage over time where firms will be able to get further ahead as they're, you know, having access to better information. Their teams know that it's accurate and like stuff is not misaligned, cuz the last thing we want to do is, you know, do something or make a decision that was misinformed or had misinformation, and then that streamlines down the chain to both the enterprise and to the, you know, our investor base at the end of the day.

</details>

**主持人**：是的，这完全讲得通。所以我原本想问您一个预测：当我们五年后坐在这里回顾所有这些变革时，Apollo 会变成什么样？但我又觉得这个要求太苛刻了。毕竟我连我的团队下周究竟会用 Codex 还是 Claude Code 都无法预测。

所以，我不打算让您预测五年后那么遥远的事了。但我非常好奇您个人的体会：对于您的工作、团队以及 AI 应用的演进，您期望看到怎样的变化？需要满足哪些前提条件，这项技术才能真正释放出实打实的价值？您如何看待未来这几个月的发展？

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah, that makes sense. So, I wanted to ask you what your prediction was for what Apollo would be like when we're talking in five years observing all the change. I think that's unfair. I can't even predict if my team's going to use Codex or Claude Code next week.

So, I don't want to ask you about five years in the future. But I'm curious for you personally, what are you hoping to see in terms of your job, team, how AI use evolves, what conditions have to hold for the technology to actually be truly valuable? You know, how are you thinking about things over the next few months?

</details>

### 团队赋能、业务认知与现场深度协作

**Jack**：好的，我认为这还是要回到我之前触及的一些核心点。首先第一点，是对流向我们终端广大投资人的任何类型的信息具有百分之百的信心——确保其绝对准确、无误，并且我们不再需要花费数小时去手动核对与验证这些数据。我们要确信我们对外分享的信息没有任何漏洞或差错，毕竟我们拥有非常庞大的投资人客群，涵盖了全球 400 多家大型投资机构。

其次，我也希望团队能在思维模式上更加以技术为驱动（tech enabled）。我认为我们团队至今为止并不缺乏这种意识，但在过去，对于技术工具的应用在某种程度上始终只是事后追加的考虑。

我认为，我们越是能够开发和完善这些让日常常规任务更具效率的工具，就越能释放出团队的脑力潜能，让他们能投入更多思考，进行更具创造性的探讨：这个业务流程为何存在？它在当下是如何运转的？我们究竟该如何对其进行提升？抑或是我们是否该彻底重构它，或者引入一种全新类型的技术并将其落地应用？

虽然我们的团队在这方面从未欠缺，但过去它往往只是个次要的考量。而在我看来，理想的状态是我们的组织架构与员工队伍能够在未来的日常工作中，将技术创新作为攻克各种问题时的首要思维支柱，尤其是在 Running Ridge 的日常运营以及推动我们整个组织规模化扩张的过程中。

<details>
<summary>Original English</summary>

**Jack**: Yeah, I think it comes back to some of the stuff I touched on before of just one, having full confidence in any type of information that's flowing out at the end of the day to our investor base that's accurate, correct, and we don't have to spend hours manually checking that to make sure that that's validated, and having the confidence that we're sharing, you know, no issues or mistakes. Because we do have just a wide investor base, you know, over 400 global investors.

I would also say being much more tech enabled in mindset. I think our team has not lacked that to date, but it's kind of been an afterthought around the use of technology.

And I think the more that we can develop and enhance these tools that make, you know, routine tasks more efficient, it frees up capacity to add more thought or think more creatively around why does this process exist and how does it work today, and how can we actually enhance that, or should we change that, or should we bring in a new type of technology and adopt that going forward?

And our team has not lacked that today, but it's kind of been a secondary thought, where I think ideally our workforce is positioned to think about that more on a go-forward basis, and that's kind of their primary thought as they're tackling different problems, specifically at Running Ridge day-to-day and kind of scaling our organization.

</details>

**主持人**：我想我们还有时间再提最后一个问题。在与你们合作的过程中，我最大的感悟之一就是：这背后的工作复杂精妙到难以想象，充满着创造性；而且为了让方案真正运转落地，需要人类和 AI 双方付出巨大的共同努力。

今天现场有许多朋友，他们要么希望深耕于 AI 与金融结合的技术端，要么致力于金融业务端。对于那些试图将 AI 引入像你们这样复杂领域的人们，您有什么经验或核心注意事项想分享给他们吗？

<details>
<summary>Original English</summary>

**Host**: I think we have time for one more. I think one of my learnings from working with you has just been how unimaginably complex and creative the work is, and how it takes a lot of effort both human and AI to get things to work.

A lot of people in this room who either want to work on the technology side of AI and finance or perhaps finance side. Is there anything that you would mention to them from a here's something that you should know or keep in mind when trying to apply AI to domains like yours?

</details>

**Jack**：是的，我认为归根结底的一点是：我们这类组织机构极其复杂，业务从来都不是表面看起来那么简单直接。很多时候，某些流程或设计在局外人看来可能显得有些新奇、古怪甚至不合常理，但它之所以存在或之所以被设计成那种特定结构，背后几乎总是有着极其充分的缘由。

我相信你们团队深入进来之后，也深刻体会到了我们业务的高难度、复杂性与细微差别。因此，花时间真正扎根一线、走到现场（putting boots on the ground），与你正在为其构建或优化工具的具体业务团队或前台专业人员坐在一起，深入了解他们的日常，这绝对是非常值得且必须付出的投入。

我想，我们在基于 Rose 的产品上之所以能够取得成功并走到今天、甚至超越了我们原定的路线图和预期，很大程度上正是因为 Michael 和整个团队花了大量充裕的时间，几乎每天都深入一线与我们的团队紧密坐在一起，切实理解我们的业务工作流。我认为这一点至关重要。

<details>
<summary>Original English</summary>

**Jack**: Yeah, I would say it comes down to we are extremely complex organizations and it's not as straightforward. And typically things might look a little bit novel or strange and out of place, but it's probably actually there for a reason or structured in a specific way.

I'm sure as you guys have come in, you appreciate that we're super nuanced and complicated. So spending the time and really putting boots on the ground to sit with whatever team or front office professional that you're working to build a tool for or enhance is time well spent.

And I think the success and, you know, where we are today with the Rose-based product and kind of being ahead of our roadmap and expectations has been, you know, due to the fact that Michael and the team have spent ample time sitting on the ground with our team like pretty much every single day and, you know, understanding our workflows, which I think is crucial.

</details>

**主持人**：太棒了！最后我还想打个硬广：Basis 和 Apollo 科技团队目前都在广纳贤才，招募热衷于将 AI 应用于金融领域的优秀人才。因此，如果有兴趣的朋友，请随时联系我们任何一方。Jack，非常感谢你，今天聊得非常尽兴！

**Jack**：谢谢大家，这场交流非常棒，感谢各位！

<details>
<summary>Original English</summary>

**Host**: Awesome. Well I guess last thing I'll say is that shameless plug: both Basis and Apollo Technology are hiring people who want to apply AI to finance. So please reach out to either of us if you are interested. Jack, thanks so much and great chatting.

**Jack**: Thank you. This is great. Thank you guys.

</details>

### AI Agent 在真实场景落地与非确定性系统

**报幕人**：当 AI Agent 面对复杂任务时，最终的答案往往只是整个故事的冰山一角。为了探讨我们该如何评估它们在推进过程中所做出的一系列决策，让我们欢迎 Basis 联合创始人 Mitchell Troyanowski！

<details>
<summary>Original English</summary>

**Announcer**: When AI agents tackle complex tasks, the final answer is only part of the story. To explore how we can evaluate the decisions they make along the way, please welcome Mitchell Troyanowski, co-founder of Basis.

</details>

**Mitchell Troyanowski**：大家好，大家好！纽约的朋友们，大家好！我是 Mitch，Basis 的两位联合创始人之一。我们公司总部就设在纽约市。

我们始终聚焦的核心议题是：如何让智能体（Agents）足够可靠地承担起生产级别的复杂工作，从而赢得全美各地会计师事务所的信赖，并在其整个业务链条中端到端地被日常使用？

因此，我们的许多核心研究都在聚焦于解决这个问题：究竟该如何让这些智能体在现实经济环境中完成实打实的工作？

我想先抛出一个问题来开始今天的分享：各位既然来到这个会场，或者如果你正在收看这场演讲，你个人大概率已经借助 AI 实现了生产力的大幅跃升。你可能正在使用 Cursor、Codex 或者 Claude Code 等工具。

然而，如果你去观察任何一家普通企业、普通机构或典型公司，他们的整体生产力并没有迎来 10 倍甚至 100 倍的增长。我知道我个人的生产力可能提升了 100 倍，但如果我是置身于一家传统企业内部开展工作，整体效能的提升绝对远远达不到这种数量级。

那么，这究竟是为什么呢？

在 Basis，我们内部常说的一句话是：人类其实早就习惯了与非确定性系统（non-deterministic systems）共同协作。只不过在过去，这些非确定性系统通常是身边的同事，而不是面前的计算机。而正因为如此……

<details>
<summary>Original English</summary>

**Mitchell Troyanowski**: Hello. Hello. Hello, New York. I'm Mitch. I'm one of the two co-founders of Basis. We are based right here in New York City. And the thing that we focus on is how can we get agents to do production scale work reliably enough so that we are trusted and used end to end by accounting firms across the country.

So a lot of our research really focuses on this: How can you get these agents to do real work in the real economy?

So I want to maybe start with a question which is: if you're at this conference, honestly if you're watching this talk, you probably increase your own productivity a lot. You're using Cursor or Codex or Claude Code, whatever it is. And yet if you go look at the average company, the average enterprise, the average firm, their productivity hasn't gone up 10x, 100x. I know my productivity has gone up maybe 100x, but if I were working inside of a company, it wouldn't be anywhere near that order of magnitude. And so why is that?

At Basis, one of the sayings we have is that humans are already used to working with non-deterministic systems. It's just those systems are normally their co-workers, not their computers. And so...

</details>

<!-- chunk 47/51 -->

### 企业如何通过标准化流程扩展生产力

**Speaker**: 我其实觉得，要回答这个问题，或许可以回顾一下我们目前组织智能系统的方式——也就是企业。企业究竟是如何扩展自身生产力的？企业必须建立一种信任机制，确信各个层级开展工作的员工，其做事方式都能在规模化运作下持续稳定地产出优质成果。如果看一下这里的这张图，我展示的是一家会计师事务所，但老实说，这可以适用于任何传统的企业。作为事务所的最高负责人，他们其实完全不知道最基层员工每天具体的日常操作细节。然而，他们莫名就能信任工作一定会被妥善完成。这到底是怎么做到的？

<details>
<summary>Original English</summary>

**Speaker**: I actually think to answer this question, it's useful to maybe look at the existing way we organize intelligent systems, which are companies. So how do scale their own productivity, right? Organizations need to trust that the people doing the work at every level are doing it in a way that is going to produce good outputs consistently at scale. Right? If you look at this image here, the here I'm showing an accounting firm, but this could honestly be any company, traditional company. The person who is the head of the firm, they have literally no idea about the exact day-to-day of the people at the very bottom. And yet somehow they trust the work is going to be done. How does that happen?

</details>

**Speaker**: 这种信任并不是通过确定性系统来实现的。人并不是确定性的，人是具备智能的个体。相反，企业是依靠建立一套套运转的流程来实现这一点的。在制定这些流程的人看来，只要相信这些流程能够泛化并导向良好的结果，那么他们就能放心：即使具体执行流程的人本身并不具备确定性，只要严格遵循这套流程，总体上也总能得到良好的成果。

<details>
<summary>Original English</summary>

**Speaker**: It doesn't happen through deterministic systems, right? People are not deterministic. They're intelligent entities. And instead, there are processes that are put in place. And those processes if we believe the people who you know put them in place think that those processes will generalize to good outcomes then they can be comfortable that even though the people executing the processes are not deterministic you will generally get to good outcomes if you follow the process.

</details>

**Speaker**: 顺便说一句，即便在最微小的步骤中也是如此。在刚才的例子中，我展示的是一家会计师事务所为客户处理月度会计工作的流程。但即使在这个流程内部，比如你想了解“我该如何进行现金对账？”，首先就必须获取银行数据，而就连获取数据本身也是有一套流程的。这个流程可能非常基础，比如仅仅是“使用经过审批的软件去提取数据”，但这依然是制定好的一套流程。事务所绝不会允许任何人随意去 Google 搜一下“提取 PDF”，然后随便找个工具去抓取数据，因为那样一来整个流程就不复存在了。

<details>
<summary>Original English</summary>

**Speaker**: This is true by the way even in the smallest step. So in this example earlier I was showing the process of maybe doing the monthly accounting work for a client at an accounting firm. But even within that process say you wanted to see how do I reconcile the cash? Well I need to get the bank data and even that has a process. The process could be really basic. It could just be use the approved software to extract the data but there's still some process that is put in place. You wouldn't expect the firm to just let anyone Google, you know, extract PDF and then just use whatever they want to go extract it because now you wouldn't have process.

</details>

### 代码型 Agent 的两大痛点：能力鸿沟与流程鸿沟

**Speaker**: 现在我们来谈谈 Agent。正如我之前所说的，现在每个人都已经拥有了协同工作的工具。但是，承诺中的生产力究竟在哪里？我们的观点是，当前那些所谓的“代码风格”的 Agent 产品存在两大核心问题——在这类产品中，你和一个 Agent 一起工作，只是对它下达指令让它去把某件事做完。第一个问题是“能力鸿沟”，因为按照如今大家对 Agent 的理解，它们其实是将复杂性转嫁给了用户。作为用户，我现在必须去管理自己的技能、记忆，还得琢磨什么时候该使用这个 Agent，甚至还要对其具备某种“心智模型”。这极其困难。对于在座的各位来说，你们可能觉得这轻而易举；但我向你们保证，对于绝大多数知识工作者而言，他们对这些东西完全摸不着头脑。

<details>
<summary>Original English</summary>

**Speaker**: Now let's talk about agents. As I said earlier, everyone already has co-work. But where is that productivity? Our opinion is there are two main problems that come with what I'll call coding style agent products where you're working with an agent and you just tell it to go and do something. The first problem is that there is a competency gap because agents as you think of them as you think of them today, they outsource the complexity to the user. Right? If I'm the user, I now have to make manage my skill and memories and think about how to uh when I should use the age and I have to have like theory of mind over it. This is really hard. And for those who are here, maybe you guys find it easy. But I promise for the wide majority of knowledge workers, they have no idea how to do any of this.

</details>

**Speaker**: 第二个问题则是“流程鸿沟”。如果你对用户说：“嘿，这是你的 Agent，你想怎么用就怎么用。”那么突然之间，工作到底该怎么开展，本质上完全取决于具体用户如何去自定义这个 Agent 的行为——这与现代组织实现规模化扩展的方式完全背道而驰。流程应当由高层领导自上而下确立并推行，而不是由任何单个员工自行决定该如何完成自己的工作。回到我刚才的例子，如果每个员工都自创一套数据提取方法，哪怕是在 2018 年，也绝不会带来什么好结果。因此我们坚信，构建真正能够端到端完成工作的生产级 Agent，关键就在于解决这两个问题。

<details>
<summary>Original English</summary>

**Speaker**: And there's a second problem which is there is a process gap. Right? If you are saying, "Hey user, here's your agent, do what you want." Well, now suddenly the way the work is being done is essentially up to whoever the user is to customize the way the agent is behaving which goes entirely against the way that organizations scale. The process should be coming from senior leadership down not from any individual employee deciding how they're going to do their job. Right? If you going back to my example, if every employee just made up their own way of extracting data, you know, even back in 2018, that wouldn't be a good outcome. And so we believe strongly that the key to building production agents that actually do work end to end is solving these two problems.

</details>

**Speaker**: 你必须通过对用户保持极致简单来填补“能力鸿沟”。你甚至不需要感知到它是一个 Agent——或者说你可能知道，但完全不需要为之费心。它应当就像与一位真人同事协作一样简单：你只需告诉它你想要做什么，所有你期望能够搞定的事情就都能够顺利运转。其次是解决“流程鸿沟”。你必须让 Agent 具备可靠性。绝不能今天灵光一现表现天才，明天就把最基本的事情忘得一干二净。这并不是要求十全十美，人类自己都不是完美的，没有人奢求完美无瑕。大家真正寻求的是可靠性、一致性以及值得信赖。

<details>
<summary>Original English</summary>

**Speaker**: You have to solve the competency gap by making it simple to the user. You shouldn't even have to know it's an agent or you probably know, but you don't have to really feel it. It should be as simple as just working with a co-orker. You just tell it what you want it to do and all the things you expect to work should work. And the second is the process gap. You need agents to be reliable. Not having a stroke of genius one day and forgetting something the other day. It's not about being perfect. Humans are not perfect, right? Nobody is looking for perfect. What you're looking for is reliability and consistency and trustworthiness.

</details>

### 可靠性的本质：坚持主见（Opinionated）

**Speaker**: 那么这在实际中到底意味着什么？我们认为，要想做到简单且可靠——也就是用户无需绞尽脑汁思考该做什么，Agent 可以在用户无需了解内部细节的情况下代为完成，并且始终如一地以相同方式执行——你就必须具备“主见”（opinionated）。刚才退回上一张幻灯片，我想指出：把每一件事做对其实并不是最核心的任务，因为人类自身也是不完美的。核心在于要以高度相似的方式去执行。如果你确实做不了某件事，这完全没问题，但你应该稳定地表现为做不了它，然后随着时间推移逐步提升，就像普通人一样。如果你某一天突然成了某项领域的专家，接着第二天却漏掉了理所应当能做到的极基础操作，那你就丧失了可靠性。因此，系统必须要有主见。

<details>
<summary>Original English</summary>

**Speaker**: So what does that actually look like? We think that to be simple and reliable where you know it's you don't have to think about what to do. The agent can just do it for you without the user knowing the internals to do it the same way consistently. You have to be uh you have to be opinionated. And just to show you actually one slide back here, I want to point out that getting it right isn't actually the main task because again humans are imperfect themselves. The point is to do it in the similar way. It's okay if you you can't do something but you should be consistently able to not do something and then you get better just like a person does. If you suddenly one day are an expert at something and then you miss something very basic that would be expected now you're not reliable. So you have to be opinionated.

</details>

**Speaker**: 什么是“主见”的一个例子？假设我们有一个 Agent，需要去读取一份 PDF 文件。在这种情况下，读取 PDF 的最佳方法是什么？方法其实有很多：你可以直接丢给多模态大模型（VLM）；也可以写一段 Python 代码并使用开源 OCR 库；你可以调用市面上众多的专业 OCR 模型提供商接口；你还可以先做一次 OCR，再让 VLM 对其结果进行核对；甚至可以让 5 个 VLM 同时核对，或者让 100 个 VLM 投票选出最佳事件。这里的可能性可以说是不计其数的。如果只是空泛地对 Agent 说“提取 Excel、提取 PDF”，你或许偶尔能拿到好结果，但它们绝不具备可靠性。这不是因为它的执行过程有多糟糕，而是因为它的执行过程缺乏明确的主见。

<details>
<summary>Original English</summary>

**Speaker**: What's an example of an opinion? Let's say we have an agent and we need to go and read a PDF. So in this case, what is the best way to read a PDF? There's many ways. You can throw it into a VLM. You can go write some Python code and use an open source OCR library. You can work with one of the many OCR specific model providers. You could do an OCR and then you could have the VLM check its work. You could have five VLMs check its work. You could do a 100 VLMs and take the best event. There's literally infinite possibilities here. And so if you just said agent extract Excel, extract PDF, you might get good outcomes, but they're not going to be reliable, right? Not because the process it did was bad, but because the process it did was not opinionated.

</details>

**Speaker**: 我们形成主见的方法，首先是利用先验直觉。有些主见源于专业经验的积累。举个例子，如果要让 Agent 去做税务工作，我就清楚地知道：如果 Agent 在向用户返回结果之前，能够先去阅读一手原始资料，那么结果的准确性就会高得多。我根本不需要一套专门的评估测试（evals）来告诉我这个道理，也不需要从第一性原理去推导，这是显而易见的事实。再比如，如果我让 Agent 制作一个 PowerPoint 幻灯片，只要它在返回给用户之前先截取一张幻灯片的图片进行核对，出现格式问题的概率就会大大降低，这也是不言自明的。形成主见的方法有很多种。在我进一步讨论如何在实践中运用这些主见之前，我想强调的关键一点是：主见并不仅仅关乎准确率。

<details>
<summary>Original English</summary>

**Speaker**: So the way we develop opinions is you use initial intuition, right? Some things you know what the opinions are from expertise. For example, if I'm trying to get an agent to do tax work, well, I know that if the agent is goes and reads the primary source before returning to the user, it is more likely to be accurate. I don't need a set of evals to tell me that. I don't need to divine that from first principles. We know that, right? I know that if I have an agent make a PowerPoint, if it takes a picture of the PowerPoint before it returns to the user, it is less likely to have a formatting issue. That is obvious. And so there are lots of different ways to develop opinions. And one of the key points here I'll just make before I move on to talking about how to use the opinions is that the opinions are not just about accuracy.

</details>

### 从结果评测到轨迹行为验证

**Speaker**: 刚才提到截图检查 PowerPoint 的例子，这样做其实会增加延迟。你可能并不希望引入这种延迟；或者可能 Agent 遇到排版错误的情况本来就只有百分之一，你是完全可以接受的，因此你根本不需要每次都对 PowerPoint 截图检查。所以重点不在于具体的主见究竟是什么。在这次演讲中，我们探讨的重点不在于如何去制定主见，而是在于为什么主见至关重要，以及在生产环境中进行规模化扩展时，该如何充分利用这些主见。

<details>
<summary>Original English</summary>

**Speaker**: Right? We just talked about the example of taking a picture of a PowerPoint. Well, that adds latency, right? You may not want that. Maybe the agent only makes formatting mistakes one out of a hundred times and you're okay with that. And so therefore, you don't have to take a picture of the PowerPoint. The point isn't exactly what the opinion is. And this talk we're going to focus not on how to develop opinions, but why opinions matter and then how to leverage those opinions as you scale in production.

</details>

**Speaker**: 假设你有一批基于结果的评估（outcome-based evals）。所谓基于结果的评估，就是我们传统认知中的评估：它有一个标准答案，我们设定了某种评分标准，试图以此去判定 Agent 所做的工作。但你怎么能确定这套评估在几百个案例上表现良好，就能泛化到实际生产环境中呢？在真实的生产环境下开展真实工作，你面对的将是成千上万种极其复杂的情境。随着 Agent 决策轨迹变得越来越长，随着 Agent 处理长周期任务能力的提升，单条轨迹中所需要做出的决策数量呈指数级激增，这种情况只会愈发严峻。

<details>
<summary>Original English</summary>

**Speaker**: So say you have a bunch of outcomebased evals. And when I say outcome based evals, I mean what we traditionally think of as eval. It has a right answer. We have some rubric. We're trying to judge what the agent did. How do you know that the eval generalizes or 100 cases, but in production if you're doing real work, you're going to have hundreds of thousands of situations. And that's only going to increase as the trajectories get much longer because the amount of decisions that are made in a trajectory just grow exponentially as the like long horizon abilities of agents increase.

</details>

**Speaker**: 面对所有这些分布广泛的轨迹，你无法证明其中的每一条都是完全正确的，因为你不可能为每条轨迹都预备好基准真相（ground truth）。但是，你完全可以通过审查这些轨迹，来判定你所确立的行为准则和主见是否得到了切实的执行。如果它确实被严格执行了，你便能够据此推断，它更有可能良好地泛化到生产环境中。虽然这谈不上绝对完美，你无法百分之百确信，但至少你在用明确的主见来进行规范。我们来看一个真实的案例：假设针对某项特定行为——这是一个会计领域的案例——如果在银行对账过程中出现了错误，我不希望 Agent 直接记录...

<details>
<summary>Original English</summary>

**Speaker**: And so I can't prove if I if you're looking at all these distribution of uh trajectories, you can't prove every one of them is correct. You don't have a ground truth for every trajectory. But you can potentially look at the trajectories to decide if the behavior, the opinion that you have is actually happening. And you can then infer that if it's actually happening, it's more likely to generalize to production. It's not perfect. You don't know for sure, but at least you are having an opinion. Let's run through a real example. So let's say that I uh for a behavior this is an accounting example where if there is a uh mistake for uh in in the bank reconciliation um uh I don't want the agent to like post an

</details>

<!-- chunk 48/51 -->

### 上下文即运行时训练数据与行为规范

**Speaker**: ……条目来平局。我希望它能稍微解释一下差异，而不是直接做个推广。同样，这非常主观。你可能想要相反的处理方式，但你绝对不希望看到的是：同一个客户，这次遇到一种行为模式，下次又遇到另一种完全不同的行为模式。

那么，面对这种情况你该怎么做呢？首先，让我们来搞清楚到底是什么在主导或决定智能体的行为，对吧？智能体的行为可不是单纯靠你在系统提示词（system prompt）里随手写两句话就能搞定的。这种做法对于那些非常简单、任务极度狭窄的智能体或许管用；但当你在构建大型、复杂的智能体系统时，它的行为实际上是由多种因素交织决定的——包括系统提示词、渐进式信息披露（progressive disclosures）、潜在的工具描述（tool descriptions），当然还有模型本身的预训练和微调权重。有非常多的要素在共同决定着它的行为。

顺便提一句，关于构建面向生产环境的智能体，我有一个实用建议：一定要把智能体在运行工作时所看到的所有上下文，视作它的“运行时训练数据”（runtime training data）。我认为“提示词”（prompt）这个词在某种程度上把这件事轻量化甚至琐碎化了，对吧？说到底，这些上下文数据就是智能体在运行时正在接受训练的数据。虽然从底层机制上说不是字面意义上的权重训练，但在实际效果上它就等同于训练。因此，你必须去在乎每一个 token，并且深入理解这些数据究竟是如何促使智能体表现出特定行为模式的。

<details>
<summary>Original English</summary>

**Speaker**: entry to make a tie. I want it to uh sort of explain the difference instead of putting a plug. Again this is subjective. You might want the other way, but what you don't want is a customer getting one way one time and another way the other time.

And so what would you do? Well, first let's understand what governs the behavior, right? The behavior is not just you write the two sentences into your system prompt and it just works. That might work for very simple narrow agents, but when you're building these big agent systems, the behavior is actually a combination of the system prompt, your progressive disclosures, uh potentially tool descriptions, obviously the training of the model. There's a lot of things that govern the behavior.

And one tip, by the way, I have for when you think about building production agents is really think of the context the agent is going to see as it's working as runtime training data. The word prompt, I think, trivializes it a bit. Right? At the end of the day, this is the data that the agent is being trained on at runtime. Not literally trained on, but effectively trained on. And so, you want to care about every single token and understand how that data causes the agent to behave in certain ways.

</details>

**Speaker**: 所以，当你在把各种行为部署到生产环境中时，如果试图把某一项具体的行为完全精确地塞进某一个单独的段落里，这可能会极其困难，因为智能体的最终行为是由所有输入数据同时作用产生的结果，而不是靠某单一要素孤立决定的。

我们在 Basis 公司探索并构建出的核心概念之一，就是所谓的“行为规范”（behavior spec）。行为规范的核心思想本质上是：在我们去更新上下文或撰写具体上下文内容之前，先明确——我们到底想要什么？我们的核心意图究竟是什么？你可以在某种程度上把它看作是面向智能体时代的产品规格说明书（product spec）。

你不可能也不应该把每一个细枝末节都巨细靡遗地写下来。你应该做的是提取出最核心、最关键的主张和原则并将其明确化；因为如果你试图事无巨细地把所有东西都写进去，你就会导致大量的状态重复。因此，你需要去定义那些最重要的核心规范。在此之后，你不仅可以将其作为团队在产品规范层面对齐认知的工具，更重要的是，你还可以把它们作为一套评测标准（rubric）。

你可以针对某一条具体的执行轨迹（trajectory）——无论是在任何缺乏绝对标准答案（ground truth）的开放轨迹中——去评估：智能体是否进入了该行为规范所适用的特定场景？如果进入了该场景，它是否真正表现出了预期的规范行为？通过这种方式，你能够从执行轨迹中获取并规模化扩展评估信号的量级，这要远远大于单纯去堆砌那些基于最终结果的基准真值和打分标准（outcome-based eval ground truths and rubrics）。基于结果的评测固然非常重要，但你扩展那些评测维度的速度，绝对远远赶不上你扩展监督智能体行为模式能力的速度。

<details>
<summary>Original English</summary>

**Speaker**: So when you're putting uh behaviors into production, it it might be very difficult for one behavior to put it in exactly one, you know, paragraph that you know exactly because again the behavior is all of the data at once, not just one thing.

And one of the things that we developed at basis was this concept of a behavior spec. And the idea of a behavior spec is essentially saying before we update the context or write the context. Uh what do we actually want? What is our intent? You can kind of think of this a little bit as like a product spec for the agent era. And you can't write you shouldn't be writing every detail down. You should be taking the most important opinions and putting it because if you put everything you'll be duplicating a lot of states.

So you define the ones that matter the most and then you can use them as a way to align your team from a spec perspective. But then you can also use them as a rubric and you can say in this particular trajectory whether that is in any trajectory that doesn't have a ground truth did the agent get into a situation in which this behavior was relevant and then if so did it actually exhibit the behavior. And this way you can scale the amount of signal that you get on your trajectories far larger than trying to increase the amount of outcome based eval ground truths and rubrics that you have. Those are really important but you cannot scale those anywhere near as fast as you can scale the ability to supervise what the behaviors of the agent are.

</details>

### 分叉诊断与轻量化模拟

**Speaker**: 让我们来看一个快速的实例。这里要提到的是第二个核心概念，叫做“分叉”（forking）。我们可以将分叉与行为规范结合起来思考。如果你曾经使用过 Claude Code 或者 Codex 的 Web 应用，你会注意到每条消息下方都有一个小小的分叉（fork）图标，通过它你基本上可以使用完全相同的状态来创建该智能体的一个副本。这种机制在你的本地计算机上运行得非常顺畅。但是在云端要完美构建这样一套系统并不容易，因为你必须完全重现数据库环境、重现所有的提示词以及所有相关的不同运行时环境。

然而，分叉确实是我们用来检验和调试行为的另一大利器。你可以设想这样一种工作流：我们记录到了一条执行轨迹——它可能来自于某个评估测试集，也可能来自于测试阶段或实际生产环境——并且它未通过某项行为评估（behavior eval）。此时你试图去搞清楚原因：它为什么在行为评估上失败了？为什么没有展现出预期的行为？

接着，你可以直接进入该执行轨迹的时间线，回溯到智能体做出那个与预期行为相违背的决策之前的精确时间点——前提依然是你的行为规范定义清晰且能够有效产生信号。然后你可以在这个节点执行分叉；或者你也可以在它做出决策之后紧接着进行分叉，直接向它发问：“你当时为什么会做出那样的决定？”或者，你也可以选择去修改和更新智能体的上下文，然后观察这种调整是否改善了它的行为。

通过分叉机制，你能够真正捕获到深层信号，并开始推演：“好，我们该如何据此改进外围框架和运行支架（harness），从而充分利用这些信号？”相比之下，如果你仅仅依赖基于最终输出结果的评估（outcome-based eval）所提供的信号，调试起来就会极其艰难——因为它仅仅告诉你最终结果失败了，但你如何知道失败的具体根因究竟在哪里？在一条长达五个小时的智能体长程轨迹运行中，背后可能包含了多达上千次的模型推理调用（inference calls）。

<details>
<summary>Original English</summary>

**Speaker**: Let's just take a quick example here. Um this is so this is actually the second concept um which is called forking which we can combine here with behavior specs to think about forking if you've ever used uh cloud code or or codeex web apps there's this little fork icon uh under each message where you can essentially create a copy of the agent using the same thing which works really well on your local computer. It's hard to build a system that does this in the cloud perfectly with recreating the database environment and recreating the uh the prompts all the all the different environments.

But forking is another tool that we use to check the behavior. So a flow that you can imagine is saying we had a trajectory could be in an eval set it could be in testing or in production and it failed the behavior eval. And now you're trying to understand why why did it fail fail the behavior eval why did not exhibit the behavior and then you can go into the trajectory and go right before the point in which the agent made the decision that was in contrast to the behavior assuming again your behavior is good and it's actually producing signal and then you can fork it and when you fork it you can ask the agent uh or you would fork it right after it made the decision you could ask it why' you do that or you can go and update the uh context of the agent and see if that improves the behavior.

And so with forking, you can start to actually take the signal and start to figure out, okay, how can we then improve the harness to now uh leverage the signal versus if you're just looking at signal from an outcomebased eval, you can't do that anywhere near as easily because it failed the outcome. How do you know why? you have potentially a thousand inference calls in your five hour long agent trajectory run.

</details>

**Speaker**: 接下来是我想讨论的最后一个工具。这其实是我最喜欢的一种方法，叫做“模拟”（simulations）。听起来可能会觉得有些不可思议，但我向你们保证它极其有效：当你在使用编程智能体（coding agents）工作时，你可以让该编程智能体创建一个子智能体（sub-agent），让这个子智能体假装扮演你的生产环境智能体。

你必须明确告诉它绝对不能作弊。你给它加载完整的系统提示词、各项技能（skills），把所有运行时要素都丝毫不差地渲染呈现给它。接下来你能做的，就是向它询问在某些特定场景下它会如何应对。你可以向它输入一个具体情境，看看能否在它身上复现出你在评估测试集或生产环境中所观察到的异常状况。

如果你能够成功复现该情境，那么现在你就可以去调整优化你的上下文内容，进而观察这个子智能体是否会因为你的微调而改变其行为。选择这么做的原因在于——虽然它的精确度显然远不如完整的分叉机制——但这种方法成本极低、速度极快，它能让作为智能体开发者的你极其轻松地快速迭代各种构想，而完全不需要经历完整分叉整套系统环境那样昂贵且繁琐的工程流程。

你今天立刻就可以在不搭建任何额外基础设施的情况下做到这一点。在我自己把分叉功能深度整合进我们内部系统之前，我足足有一年半多的时间都是纯粹用这种模拟方式来迭代的。

这里最核心的思想在于认识到：如果你回顾一下我们前面提到的行为分布曲线，你本质上是在试图搞清楚智能体是否能够很好地泛化到那个真实的分布区间。你仅仅依靠最终结果的评估是无法得知这一点的。你可以竭尽所能去挑选最具代表性的结果评估测试用例来拟合那条曲线，但你依然无法真正洞悉内部机制。因此，通过上述这些方法来对过程本身进行有效监督，能够为你提供宝贵的增量信号，从而帮助你判断智能体是否正在正确地进行泛化。

<details>
<summary>Original English</summary>

**Speaker**: And then we have the last tool that I like to talk about. This is actually my favorite, which is called simulations. Uh it's going to sound silly, but I promise it's very effective, which is that you can when working with coding agents, ask the coding agent to make a sub agent that pretends to be your production agent. And you have to tell it to not cheat. And you give it the system prompt and the skills, and you render everything perfectly.

And what you can do is you can ask it what it would do in some scenario. You can give it the situation and see if you can recreate the situation that you saw in your evalor in production. And if you can recreate it now, you can tweak your context to see if the sub agent would change its behavior based on your tweaks. And the reason to do this, it's obviously far worse than forking, but you do this because this is much cheaper, much faster, and allows you as an agent builder to really easily iterate on ideas without needing to go through the expensive process of actually forking an entire environment. And you can do this today without building anything. Um I did this for literally year and a half plus before we uh built forking into our internal systems.

And the main idea here is understanding that if you look at the the distribution from earlier you're trying to understand is the beha is the uh agent generalizing to that distribution. And so you don't know purely based on the outcome eval. You can try to choose the best outcome eval represent the curve but you don't really know. And so supervising the process through some of these methods gives you some additional signal in order to understand if it's generalizing properly.

</details>

### 主张、可信赖度与规模化推广

**Speaker**: 最令人兴奋的是，随着你开始获取越来越多的过程信号，你实际上就能够开始形成闭环。而明确的主张（opinion），正是促使你能够实现这一闭环的前提条件，对吧？如果你对自己的系统缺乏明确坚定的主张，你就永远无法提炼和构建出那种高质量的有效信号。

现在，如果我们把视角重新拉回到企业（firm）层面：我们深入讨论了监督机制；也讨论了如果团队具备明确的主张，智能体不仅能够变得更加可靠，而且在设计上实际上也可以变得更加简洁。这意味着什么呢？这意味着智能体在一开始或许只是在执行非常狭窄受限的任务，但正是因为人们愿意与它协作、看到它简单易用且表现高度稳定可靠，随着它在实践中不断进步，大家对它的信任度就会越来越高。

这与人类同事之间的协作过程完全一致。想象一下第一天入职的新同事：当有人给你提交了一个 Pull Request（PR）时，你通常会基于两个核心维度来进行审查。无论是谁给你提交 PR，你都会衡量这两个维度：第一，这个 PR 的爆炸半径（blast radius，即潜在影响范围）有多大？第二，你主观感知中这个人的专业胜任能力如何？对吧？如果公司里公认专业能力最弱的人给你提交了一个正在修改核心系统服务的 PR，你一定会字斟句酌、极其严密地逐行审查；但如果是由专业能力最强、最具声望的核心骨干提交了一个仅仅修改内部文档的 PR，你可能扫一眼就放行了，不会去过多深究。

因此，人类与智能体之间的协作心理，与人类彼此之间的工作信任机制是完全相通的。

最后，我想以一个非常关键的观点作为总结来收尾：当人们听到这种注重可控与约束的做法时，常有的一种反驳声音是：“等一下，如果你完全放手让智能体随心所欲地去探索，难道它们不会发现更好的路径吗？难道它们不会把你的工作效率提升出类似‘第 37 手’（Move 37）那样的神来之笔吗？”

我的回答是：它们确实有可能会做到。但那绝对不是你用来规模化提升 GDP 和工业化扩充生产力产出的有效途径！没有任何人会希望智能体在帮自己报税时突发奇想来一个充满意外的“第 37 手”飞跃。大家需要的是在极大规模下能够稳定、可靠地交付，是以一种他们能够彻底信任、并且他们的团队成员深谙如何与之协同配合的方式来稳妥完成。

因此，我想留给各位最后的一句话是：要让智能体在广泛的产业中实现真正的扩散与普及，它们必须保持足够简单；而要让团队全心全意地信任它们，它们必须具备极高的可靠性。而要达成这种可靠性，路径就在于我们今天所讲的一切。

<details>
<summary>Original English</summary>

**Speaker**: And what's really cool is as you start to get more signal, you can actually start to close the loop. And an opinion is what lets you do that. Right? If you don't have opinions about your system, you're not going to be able to develop that signal.

And now if we go back to the firm, we talk about talked about supervision. We talked about how the agent uh if you're opinionated can be more reliable and actually can be simpler. What that means is the agent maybe it starts doing something narrow but because people will work with it, they see that it's easy to use and they see that it's reliable. As it gets better and better, they will trust it more. It's just like a co-orker.

You have a co-orker day one. Imagine someone sends you a PR. You're not going to if it's you're looking at two axes. Whenever someone sends you a PR, it's these two axes. What's the blast radius of the PR? And what is your perception of how competent that person is? Right? If the least competent person at your company is sending you a PR that's editing a core service, you're going to look at it. If the most competent person is sending you a PR that's editing an internal document, you may not look at it as much. And so this idea is true with humans working with agents just like it is with humans working with humans.

And I think I just want to make one last point to close here, which is that one of the things that people say when they hear this is, well, wait a second. If you let the agents just do what they want, won't they find a better way? Won't they move 37 your work? And the answer is they might. But that's not how you scale GDP and scale output. Nobody wants their agent to move 37 their tax return. They want it done reliably at scale in a way that they can trust and in a way that their people know how to work with.

And so the thing I will leave you with is for agents to diffuse. They need to be simple. For teams to trust them, they need to be reliable. The way you get

</details>

<!-- chunk 49/51 -->

### 构建闭环以实现自优化智能体

**Speaker A**: ……走向简单与可靠的关键在于，你要对智能体的行为方式形成自己的见解。而这些见解能让你构建出额外的信号，帮助你开始闭合反馈回路，从而在生产环境中实现能够自我优化的智能体。非常感谢大家。

<details>
<summary>Original English</summary>

**Speaker A**: ...to simple and reliable is you develop opinions on how the agent behaves. And then opinions allow you to build that additional signal that helps you start to close the loop so that you can achieve self-improving agents in production. Thank you very much.

</details>

### 探索世界模型的新前沿

**Host**: 如果人工智能不仅能生成内容，还能真正模拟物理世界，那会怎样？为了探索世界模型的新前沿及其可能解锁的潜力，让我们掌声欢迎 Runway 联合创始人兼联合首席执行官 Cristóbal Valenzuela。

<details>
<summary>Original English</summary>

**Host**: What if AI could do more than generate content and actually simulate the physical world? To explore the next frontier of world models and what they could unlock, please welcome Cristóbal Valenzuela, co-founder and co-CEO of Runway.

</details>

### 从早期实验到前沿视频生成

**Cristóbal Valenzuela**: 大家好，非常非常高兴能来到这里。感谢大家留下来听今天最后一场演讲。欢迎来到我关于“黑客帝国以及我们如何生活在其中”的演讲。

我在 Runway 工作已经快十年了。实际上大约十年前，我们就是在纽约这里起步的。我想向大家分享我们一路上积累的一些经验心得——你们知道的，包括在这里建立这家公司、在纽约建立这个研究实验室，以及我们如何看待在视频与像素生成领域所开展的大量工作未来的走向。

我这么说可绝非夸大其词，有时我开玩笑说这世界可能本身就是一场模拟，也可能不是。为了让大家了解一些背景，我带大家回顾一段历史。这感觉就像在参观史前古代遗迹一样：这是我们在 2019 年制作的第一部 AI 电影。它叫作《橘子》（The Orange），因为正如大家一眼就能看出来的，这是一只从树上掉落下来、穿行在世界不同角落的橘子。

这部作品在当年就完成了。这是我们当时拥有的一个视频和图像模型制作出来的，当时生成的画面尺寸仅仅是 128 像素乘以 128 像素，然后我们强行将其超分辨率放大到这样的画面效果。现在回过头来看，我觉得这完全是一种艺术。就像在观赏一部 20 世纪初的早期默片一样，非常优美，背后蕴含着深厚的探索历史。

但那是 2019 年的事了。我们在 2017 到 2018 年创立了这家公司。当时为了搞清楚这项技术到底有没有未来，我们试图说服自己：只要加大算力和模型规模，它就会自然而然地迭代提升，直到达到接近今天的水平。

现在大家看到的就是当今最先进的顶尖视频效果。这些全都是由模型生成的。其中的每一个角色都不是真人，场景中的每一处地点也都不存在于现实中。我相信在座的各位既然来到了这里，肯定早就知道了，大家大概也经常在 Twitter 等社交媒体上刷到过。这些模型的表现确实已经不可思议地惊艳。

但最耐人寻味的是，当我看着眼前这些惊艳的生成效果时，我依然深信：再过短短几年，它们看起来就会像当年的那只“橘子”一样原始。

<details>
<summary>Original English</summary>

**Cristóbal Valenzuela**: Hey guys, very very excited to be here. Thank you for staying for the last talk. Welcome to my talk about the matrix and how we're living through it.

So you know, I've been working on Runway for almost a decade now. Started here in New York actually maybe around 10 years ago. And I want to walk you through some of the learnings we've seen through, you know, building the company, building this research lab here in New York, and where do we see a lot of the work that we do in video, in pixel generation really moving forward. And so I don't kind of exaggerate, and I joke that this might be a simulation or not.

And so for maybe for perspective, I'll walk you through a piece of history. This is like watching prehistoric ancient ruins. This is our first AI film we ever made. It was done in 2019. It's called The Orange, because as you can tell very clearly, it's an orange that falls from the tree and walks through different parts of the world.

This is done. This is a video model, an image model that we had back then that was creating pixels in 128 pixels by 128 pixels that we then forcibly upsample to this kind of resolution. I think of this as art now. This is like looking at a film from the 1900s, you know, it's beautiful. There's a lot of history behind it. But this is 2019. We started the company in 2018, 2017.

And so when we're trying to figure out if this had any legs, we were trying to convince ourselves that if you scale this, it will naturally improve to the point where we can get somewhere close to this. This is state-of-the-art video today. This is all generated. None of these characters are real. None of those locations are real. I'm sure if you're probably here, you know this by now. You've probably have seen this online on Twitter. The models are just incredibly good.

And the most interesting thing is that when I look at stuff like this, I still believe this will look like the orange in just a couple more years.

</details>

### 电影错觉、下一帧预测与规模法则

**Cristóbal Valenzuela**: 因此，我想向大家介绍一下，我们不仅是如何思考 Runway 当前正在做的事情，更重要的是思考未来几年的发展方向，以及正在塑造这一切的研究工作。

我们是一家立足于艺术与科学交汇点的公司。我们在艺术和创意社区有着深厚的渊源，同时我们又拥有全球最优秀的研究人员，专注于扩散模型和大型视频模型的研发。我非常喜欢这种结合，因为它让我们能够把这两个领域的精髓融为一体。我们是一个由科学家和艺术家共同组成的团队，共同思考视频和世界模型规模化的难题。

但在某种程度上，这家公司的核心理念其实早在 120 到 130 年前就被电影和动态影像的发明者们发现了。如果你思考一下什么是视频——也许你们还记得高中学过的知识——视频本质上就是一种视错觉。视频是运动的错觉：如果你以足够快的速度把一帧帧画面拼接在一起，你就能创造出运动，创造出动态画面的错觉。

而在 Runway，我们做的事情其实非常相似。我们正在把这个理念提升到一个全新的层次：我们如何能够以足够快的速度、足够大的规模来进行“下一帧预测”，从而让我们不仅能生成漂亮唯美、富有创意的视频，还能做到更多？

这一切的底层驱动力，核心依然是缩放法则（scaling laws）。我们坚信缩放法则不仅适用于大语言模型，同样也完全适用于视频模型，事实也证明确实如此。我们现在正在大幅提升投入在模型背后的计算资源。

随着模型不断按规模扩展，最令人着迷的地方在于随之涌现的全新特性——当你把 120 年前电影诞生时摸索出的极其朴素的原理，也就是下一帧预测，并把它推向极致时所涌现出的人工智能。比如我拿出一张图片，图里的场景不是真的，里面的两个人也不是真人，我只需要根据前序帧不断预测下一帧会是什么样子。如果我的预测速度足够快，而且使用的神经网络规模足够大，我就能获得运动，获得动态影像的错觉。

我最终会得到某种对我们人类来说看起来如此真实、以至于肉眼完全无法区分真伪的内容。我看过那段视频，我自己从事这个领域已经整整十年了，我也无法分辨那是实拍还是生成的。我们甚至对此进行了实际的测试与衡量：我们尝试量化测试普通人是否能区分真实拍摄的视频与 AI 生成的视频。我认为那项图灵测试我们早已通过了，人们根本分辨不出来。

<details>
<summary>Original English</summary>

**Cristóbal Valenzuela**: And so I want to walk you through, you know, how we're thinking not only through what we're doing at Runway today, but also in the next couple of years and the research that's shaping that. We are a company that's at the intersection of both art and science. We have deep roots in artistic and creative communities, and we have some of the best researchers in the world working on diffusion models and large video models. And I like that combination because it allows us to, you know, bring the best of both worlds. We're a team of scientists and artists thinking about the problem of scaling video and world models.

But in a way that the core idea of the company was already discovered by cinema and by moving pictures 120, 130 years ago, which is if you think about video—and maybe you remember this from high school—video is an optical illusion. Video is the illusion of movement that if you stitch frames fast enough, you will create movement. You will create the illusion of movement. You create motion pictures.

And so at Runway, we're doing kind of something very similar. We're taking that idea really to the next level. How do we do next frame prediction fast enough, scale enough, in such a way that we can hopefully do more than just pretty and nice creative videos?

And so all is powered by, of course, scaling laws. I think we believed in scaling laws not only applied for language models, but also for video, and this has been true. We're now really ramping up the amount of compute that we put behind the models that you already have seen.

And I think that the interesting thing about seeing the models scale over time is the emerging properties that appear, the intelligence that appears when you start taking this very simple idea that cinema found itself figuring out 120 years ago, which is next frame prediction, and taking next frame prediction really to the next level. Right? So if I take an image like this, which is not real, those two people are not real, and I just keep on predicting what the next frame will look like based on the previous frames. And if I do it fast enough, and if I do it with a network that's big enough, I'll get movement. I'll get the illusion of movement. I'll get something that looks so real to us that we humans can't distinguish. I look at that video, and I've been doing this for 10 years, I can't tell you if that's real or not.

And we measure that. We actually measure and try to quantify if people can distinguish between real and generic videos. And I think that Turing test we already passed, people are not able to distinguish.

</details>

### 从像素生成迈向物理世界模拟器

**Cristóbal Valenzuela**: 但更耐人寻味的事情在于：当你在预测后续帧的过程中，模型学到的东西远远超越了画面本身的好看与否。它正在学习物理规律，学习客体永恒性（object permanence），学习重力，学习遮挡关系，学习运动形态，学习真实世界中物体是如何运转的。而这一切，完全仅仅是通过视频、图像以及下一帧预测的自监督学习获得的。

如果面对一个复杂的场景，一个优秀的视频模型为了保持视频的前后一致性，就必须自发地理解画面中所有的实体究竟是什么、彼此之间存在怎样的空间和物理联系：比如一只骆驼踩在球上该如何保持平衡、容器里的水在运动时会是什么形态。如果把所有这些物理常识融合在一起，并且生成推断得足够快，我们就能得到一段在我们看来无比逼真且连贯的视频。

因此，我们用来评估视频模型的许多评测基准，已经不仅仅局限于创意美学层面——创意层面的评价无非是“你喜欢还是不喜欢”——而更多是基于物理法则、几何空间结构、现实中物体的行为方式，以及这些物体在模拟系统或虚拟世界中应该如何交互。

把这种下一帧预测的机制推行得足够迅速，我们所得到的成果，显然已经更接近人们对一个完整的视频应用或游戏所抱有的期待。这依然是纯粹由视频预测驱动的。

如果再把这个想法向前推进一步：如果我们把下一帧预测放在一个三维环境或类似游戏的空间中运行，会发生什么？你实际上正在无限逼近一个物理引擎、一个全方位的世界模拟系统。但这个模拟系统本身却没有被硬编码进任何预设的物理公式或定律。我们从未向它描述过物体应该具备什么样的物理行为，模型仅仅凭借庞大的规模和算力，就自己学会了如何呈现这一切。

这逐渐变得极其有趣，因为你甚至可以想象去“游玩”这些由模型构建的世界。比如眼前这个演示，它根本不是《侠盗猎车手》（GTA）。这是某个玩家正在操纵另一个角色，置身于一个现实中根本不存在的环境和完全不存在的软件系统之中。这完全是一个对“模拟环境”所进行的端到端神经模拟，这就变得非常元叙事（meta）了。所以，我刚才半开玩笑地说“欢迎来到我的黑客帝国模拟”，真不是闹着玩的。

但对我而言最关键的转折点在于：大家之前看到的所有演示都不是实时的，也就是说生成那些几秒钟的视频需要耗费数分钟或者数秒的预渲染时间。而当我们深思未来三到四年视频模型与世界模型的发展轨迹时，我们当下看到的核心趋势，不仅在于继续扩大模型规模、使其参数更大并涌现出更强大的智能，更在于：当你让它们具备实时交互能力时，究竟会发生什么？

回到下一帧预测的逻辑：模型接收一帧，预测下一帧，接着是再下一帧、又下一帧。而一旦它能做到在生成预测的任意时间点上实时响应外界的操作与行为介入，这就意味着我可以实时模拟任何……

<details>
<summary>Original English</summary>

**Cristóbal Valenzuela**: But the more interesting thing is here is that really what's happening as you predict next frames is you're learning a lot more than just pretty frames. You're learning about physics. You're learning about object permanence. You're learning about gravity. You're learning about occlusion. You're learning about movements. You're learning about how the objects work in the real world. And you're doing that all through just video, through images, through next frame prediction.

So if you look at a complexity like this, a good video model for it to understand how to make this a consistent video will need to naturally understand what all these subjects are, how each of them relate to one another, how a camel might probably stand on a ball like that, what water in a container looks like. And if I do all of that together and I do it fast enough, I'll get hopefully a consistent video that looks real to us.

So a lot of the benchmarks that we use to evaluate our video models are not only creative—creative basically means do you like it or do you don't—are actually based on physics, on geometries, on how objects behave in the real world and how those objects should behave, and also simulator or video worlds.

So you take that idea of next frame prediction and you do it fast enough, and you get of course now something that looks more like what we should expect from a video application or a game application. Again, this is just video, right? And you take that idea to the next level. What happens if we start this idea of next frame prediction, but do it in the context of a 3D environment or something that looks similar to a game? You can start actually getting closer to a physics engine, a simulation system. But the simulation system has no physics laws. We didn't describe what the behavior of the object should be. The model just knows how to do that by pure force of scale.

And this kind of gets kind of interesting because you can only think about playing worlds. This is not GTA. This is someone playing someone else in an environment and a software that doesn't exist. It's all simulation of a simulation, which gets really meta, right? And so I'm not kidding when I said welcome to my matrix simulation.

Um, but the most interesting thing for me is that everything you saw before was not real time, meaning that it took a couple minutes or seconds for those videos to be made. A lot of what we're seeing right now when we think about, you know, the next three, four years of video models and world models is to deeply think about what happens when you start not only scaling the models and making them much much much bigger, which much more emerging properties, but also what happens when you start making them interactive. Right?

So take the same idea of next frame prediction. You take a frame, you predict next frame, then next, then next, then next. But then it can act at any point in time in that frame prediction, which means I can simulate any...

</details>

<!-- chunk 50/51 -->

### 从视频到交互式世界模型与机器人探索

**Speaker**: ……那个世界中可能出现的分歧或动作。因此在这个世界里，我不仅可以播放视频，还可以走上前去触碰那个图像的每一个部位、任何一个方面，使其具备交互性，进而影响那个世界所产生的后果。而且，它确实奏效了。当然，这在各种不同的使用场景中都极其有用。正如大家所能想象的那样，我们现在正在 Runway 内部迅速建立起一整套机器人实验室。所以，如果你来到我们位于纽约的办公室，会发现其中一半看起来就像好莱坞电影制片厂，而另一半则是一群机器人在办公室里穿行走动。因此，我们能够让这些模型——或者说开始让这些模型——成为自主系统和具身系统在现实世界中行走以及进行推理的“大脑”。

<details>
<summary>Original English</summary>

**Speaker**: possible divergence or action in that world. So in this world, I could play the video, but I can also come and touch every part, any aspect of that image and make it interactive to affect the consequences of of that world. Um, and it works. And of course, this is incredibly useful for a variety of different use cases. As you can imagine, we're now spinning an entire robotics lab in runway. So, if you come to our office in New York, half of it is uh what looks like a Hollywood studio. Half of it is a bunch of robots walking through and moving through the office. And so, we're able to make these models or start making these models the brains of how autonomous and embodiment systems walk and reason about the world.

</details>

**Speaker**: 不过，我认为还有几个更有趣的使用案例，它们超越了视频和机器人这两个显而易见的领域。那就是：当你把屏幕上的任何东西、任何事物、每一个像素都视为一个视频模型时，会发生什么？这里有一个绝佳的范例。这是一个视频模型。你现在所看到的——嗯，这是一张图像。首先，这张图像可能是真实的，也可能不是，但我可以实时运行我们的一个视频模型，并将其变成一个交互式应用程序。假设我想打开汽车的车灯，或者我想把车转个方向。我只需要点击它就行。我可以再次转动车身，也许还能打开引擎盖，看看汽车内部的构造。现在，你刚才在这里看到的一切，完全没有任何物理上的 3D 表现形式（3D representation）。这里没有 Unity，没有 Unreal（虚幻引擎），也没有 Blender。它仅仅是一个视频模型。一个经过训练、能够理解界面中的动作与点击行为的视频模型。我们称之为“世界动作模型”——抱歉，更准确地说是“世界界面模型”（World Interface Model）。

<details>
<summary>Original English</summary>

**Speaker**: Um, but there's a couple of more interesting use cases that I think go beyond the two obvious one, which is video and robotics, which is what happens when you think about anything, anything, any pixel on a screen as a video model. Um, here's a great example. This is a video model. What you see right now, well, this is an image. First of all, that image could be real or not, but I could run one of our video models in real time and make this an interactive application. So, let's say I want to, you know, turn the lights of the car. Maybe I want to like turn the car around. Um, I can just click through it. I can turn it around again, maybe open the hood and see what's inside the car. Now, everything you just saw here has no physical 3D representation. There's no Unity. There's no Unreal. There's no Blender. It's just a video model. A video model has been trained to understand actions and clicks in an interface. We call this a world action model. Um, sorry, um, a world interface model.

</details>

### 世界界面模型与次帧预测的模拟潜力

**Speaker**: 关于世界界面模型，我觉得大家现在应该都理解了。它既是一个界面，又是一个世界模型，即世界界面模型。它能让你完成像这样非常酷炫的事情。这里还有另一个应用程序，另一个关于如何考虑实时使用这种模型的范例。我可以拿出一张图像、一个表征，在其中四处移动物体，并期望它们能像我真正身处那个房间里一样发生位移。再次提醒大家记住，这里没有任何 3D 表征。这个环境在现实中甚至可能从未被建模过。它只是一张图像，加上一个理解物体在空间中如何运动的模型，而这背后的原理仅仅是这样一个极其简单的理念：下一帧预测（next frame prediction）如果扩展（scale）得足够充分，就能演变成一个世界模型或模拟引擎。

<details>
<summary>Original English</summary>

**Speaker**: And the world interface model, well, I I feel that you guys understand now. It's it's an interface and it's a world model, world interface model. Um, allows you to do very cool stuff like this. And so, here's another application, another um example of of how you could think about using a model like this in real time. Um, I can take an image, a representation, move objects around, and expect them to move as I was if if as I was actually in that room. Again, remember there's no 3D representation of this there. This environment might not actually be have have been modeled before. It's just an image and the model that understands how objects move in a space because of this very simple idea that next frame prediction scale well enough can become a world model or a simulation engine.

</details>

**Speaker**: 在我剩下的八分钟时间里，我想向大家展示将这个理念推向另一个极致的成果。我们思考的不仅是如果你能控制这些炫酷的应用和界面会发生什么，更在于如果你不断进行外推（extrapolating）会发生什么——顺便说一句，我认为外推能力可能是当下人工智能领域和创办企业过程中最重要的技能之一。预测并理解在接下来的 6 个月、12 个月、18 个月内会发生什么，可能是最关键的事情之一。因此，我们在 Runway 经常问自己这个问题：会发生什么？如果我们继续扩大模型规模，会发生什么？如果我们持续注入更多数据，如果我们不断把它们打造成更优秀的模拟系统，如果我们把它们构建成能够预测屏幕上任何内容、字面意义上屏幕上任何像素的通用模拟系统，究竟会发生什么？

<details>
<summary>Original English</summary>

**Speaker**: Um so with the eight minutes I have left I want to show you this idea taken to another extreme. Um, we're we're thinking not only about what happens if you can control these cool applications and these cool interfaces, but what happens if you keep extrapolating and I think by the way extrapolating might be one of the most important skills these days in in AI in in company building. What happens over the next six months, 12 months, 18 months might be one of the most important things to to try to predict and understand. Um, and so we ask ourselves that question a lot at runway. What happens? What will happen if we keep scaling the models? If we keep adding more data, if we keep making them better simulation systems, if we make them universal simulation systems that can predict anything on a screen, literally anything on a screen.

</details>

### Continuum：基于视频模型的全新操作系统形态

**Speaker**: 因此，我们一直在研发一个被我们称为 Continuum 的全新概念。Continuum 是将实时视频模型或世界模型的理念真正推向下一个层级、下一个维度的产物。这是一个操作系统。这里的核心设想是：在不久的将来的某个时刻，你打开电脑，屏幕上流式传输呈现给你的所有画面，可能都直接源自一个视频模型。接下来我将向大家具体展示这个理念究竟能演化成何种形态。这目前仍处于非常早期的研究阶段。但我非常想向大家展示将视频模型作为操作系统的一部分、作为你日常工作流一部分的这一构想。

<details>
<summary>Original English</summary>

**Speaker**: So, we've been working on this idea that we call continuum. And continuum is um the the idea of real time video models or world models taken really to the next the next degree. This is an operating system. The idea here is that you might open your computer at some point in the near future and what you see streaming to your screen might be coming from a video model. So I'll show you next specific how this idea could could shape. This is still very early research. But I want to show you this idea of combining video models as part of your operating system as part of your daily work.

</details>

**Speaker**: 举个例子。比如我之前在调研旧金山以及旧金山的大雾现象，我想进一步了解它是何时形成、如何形成的。这是结构化数据。这实际上是一个网页，是你可以从互联网上直接获取的内容。现在，Continuum 引入了这样一个概念：我可以圈选该网站中的任意一部分内容，并将其变成一个“传送门”（portal）。我们把它叫做 Portal。这个传送门是一段实时视频，它具有完全的交互性，并且完全根植于你正在阅读和体验的内容。我大概不会把所有那些长篇大论的文字全部读完，对我来说字数太多了。所以我只想生成一段视频，而我也确实可以生成一段由你在屏幕上看到的那些文字所具象化呈现的视频。

<details>
<summary>Original English</summary>

**Speaker**: Um so here's an example. I was researching you know San Francisco and the fog in San Francisco. Um I wanted to learn more about when and how it happens. This is structural data. This is actually a website. This is something um you can take from uh from the internet. And now Continum has this idea that I can select any part of content in that website and make it a portal. We call this a portal. And the portal is a real-time video. It's fully interactive and fully based on the content you're experiencing reading through. I probably won't read through all of that text. It's too much text for me. So I just want to make a video and I can make a video that is represented by by the text you see there.

</details>

### 交互式 Portal 与记忆存储库

**Speaker**: 这些传送门（Portals）可以是 3D 可视化，也可以是你正在观看或与之互动的任何内容。在屏幕右侧，你可以保留所有你之前经历过的可视化和传送门，也就是你之前尝试学习研究过的任何东西。从本质上讲，它就是一个“记忆库”（memory）。相当于把你之前看到过的所有想象或可视化成果都保存在了一个磁盘驱动器中。比如在这里，我之前在调研电池相关的知识，因此我可以随时返回到我之前建立的关于电池的传送门。由于它们是实时的交互式应用程序，我可以在任何位置进行点击，可以随意拖拽移动它们，还可以开始提出问题；视频本身以及其中的内容都会根据我的交互行为以及我的操作方式发生动态改变。

<details>
<summary>Original English</summary>

**Speaker**: The these portals can be 3D visualizations. It can be any content that you're watching or interacting with. On the right you can have all the visualizations and portals you've you've experienced before. Anything you've been trying to learn. Um basically it's a it's a memory. So it's the disk of the uh imaginations or the visualizations you've seen before. So here I was researching about batteries and so I can go back to uh the portal I had around batteries before and since are real time interactive applications I can click them anywhere. I can move them around. I can start asking questions and the videos and and the content itself will change based on based on my interactions and the way I'm I'm I'm managing through it.

</details>

**Speaker**: 这里还有另一个非常酷炫的例子，当我第一次看到团队向我演示它时，简直震撼得让我大开眼界。由于它是一段实时视频，你可以让它与任何操作完全交互——不仅是通过点击，比如调整应用程序窗口的大小，也应该会改变其行为状态，对吧？所以我可以调整尺寸——在这里我正在学习光合作用。如果我改变应用程序的窗口大小，我就会获得完全不同的体验。而且由于它依然是完全交互式的应用程序，我可以逐项点击，在细胞的不同结构之间穿梭漫游，探究光合作用究竟是如何运转的，从而对我正在学习和探索的事物建立更深刻的理解。话说回来，让我依然觉得有点难以名状的一点是，我甚至不知道该如何命名这种形态。我不知道它算什么——它感觉不完全像一个可视化图表，感觉不完全像一段视频，也感觉不完全像一款游戏，而是介于这些形态之间的某种新事物。我认为我们大家需要共同努力，去探索并定义最初究竟该如何称呼这类交互形态。而且我相信大家也能体会到，另一大特性在于你可以随时修改提示词的结构，或者改变最初生成该交互体验的核心驱动因素。

<details>
<summary>Original English</summary>

**Speaker**: Um here's another very cool example that when the first time I saw it when the team showed it to me it was like blew my mind. Uh since it's a real-time video, you can make it fully interactive with anything, not only with clicks, but like resizing the application should also change the behavior, right? So I can resize I'm I'm learning about photosynthesis here. If I resize the application, I get a different experience. Um and since it's again full interactive applications, I can click through it, navigate through parts of the cell or how photosynthesis work to get a better understanding of what I'm trying to learn and do. Again, um the one thing that still feels to me uh kind of unsan about this is I don't know how to call this. I don't know if this is doesn't feel like a visualization. It doesn't feel like a video. It doesn't feel like a game. Something in between. And I think we need to do the collective work of figuring out how we call these kind of interactions in the first place. And I'm sure you hear kind of the other thing is that you can change the structure of the prompt or what's actually creating that interaction in the first place.

</details>

### 视觉化思考：赋予 AI Agent 空间想象力与交互界面

**Speaker**: 这里还有另一个示例。我打算输入一些内容。这也是我认为迄今为止最缺乏探索的方向之一。这就是——我们称之为“视觉化思考”（visual thinking）。我们已经将 Continuum 接入到了一个代码编写智能体（coding agent）中。这个代码智能体所能做的是：它可以利用 Continuum 将整个问题进行可视化思考与推演。试想一下，如果你要求你的代码智能体为你的自行车创建一个 3D 模型，模型不再仅仅试图通过代码行在脑海中抽象思考这个问题，而是可以直接启动一个 Continuum 实例，以视觉化的方式直观推演该问题。如果你思考过某些人的思维方式——我相信大家身边都有这样的朋友，或者在场的很多人本身就是视觉化思考者——所谓的视觉化思考者，就是习惯于优先借助图像和视觉形态来剖析问题、构思创意，这有助于你将想要实现的最佳构想脚踏实地具象化并投射出来。而现在的 Agent 在某种程度上与此非常相似。智能体拥有了进行视觉化思考的能力。智能体可以构建出一种直观的“想象力空间”，让你能够随时介入并与之进行交互。因此，不仅智能体自身可以与之互动，我自己也能亲眼看到它，并且能够以远比单纯依赖文本交流好得多的方式去引导智能体——对我们而言，这是一个极具威力的构想。这是一种彻头彻尾的全新范式。我们把这个理念称为“视觉化思考”。

<details>
<summary>Original English</summary>

**Speaker**: Um, here is another example. Um, I'm going to type something. Um, and this is one of the ones that I feel has been the most under explore yet. This is, uh, we call this visual thinking. So, we've connected continuum to a coding agent. And what the coding agent can do is it can use continuum to visualize through a problem. So imagine you ask your coding agent to create a 3D model for your bike and instead of the model trying to just think through that via code, the model can spin a version of continuum to think through the problem visually. So if you ever think about someone or I'm sure you have friends or maybe some a lot of people here may be visual thinkers. What a visual thinker is is it thinks through problems and through ideas visually first and that helps you ground and project some of the best things you want to do. And this is somehow very similar. Agents have the ability to do visual thinking. Agents can spin up a sort of imagination that you can tap and and interact with. So not only the agent can interact with it, I can also see it myself and I can guide the agent in much better ways that I might have able to uh guide it just via text alone which is for us a very powerful idea. It's a completely new paradigm. We call this this this idea uh visual visual thinking.

</details>

### 动态生成响应式实时界面

**Speaker**: 我准备的最后一个例子，是关于如何把 Continuum 拓展到远远超越我此前向大家展示的“使用或浏览交互式结构化内容”的范畴，而是真正将它们打造成具备实时响应能力的完全动态化体验。在这个案例中，我搜索了“火星”（Mars）。当 Continuum 逐步理解了我试图搜索背后的意图时，它还会主动推荐并生成一些与之匹配的界面，这些界面是……

<details>
<summary>Original English</summary>

**Speaker**: Um the last example I have is how you think about taking you know continuum to become much more than just uh using or navigating interactive structural content in in the way I've showed you before but actually making them fully live experiences that are reactive. So in this case I was searching for Mars. Um, and as as continuum understands the intention of what I'm trying to search from, it also suggests interfaces that are

</details>

<!-- chunk 51/51 -->

### 实时可交互的火星前哨模拟

**Speaker A**：它是专门为了这个目的而实时设计的。在这里，它为我生成了这个火星前哨站。它实际上应该与当前火星上的真实机器人数据，或者预计在2030年部署的机器人数据保持一致。而且因为这是完全可交互的，我可以与它进行互动。我可以去到各个地方，可以在其中四处移动，就像你在一个3D系统、一个3D连续体中移动一样。它的运行效果非常迷人。

<details>
<summary>Original English</summary>

**Speaker A**: Specifically designed in real time just for that. So here it created for me this Mars outpost that's actually should be accurate with the data about the actual robots that are in Mars right now or with the ones that are projected maybe in 2030. And since this is fully interactive, I can interact with it. I can go to places. I can move around in the same way that I might move around in a 3D system, in a 3D continuum. And it works just fascinating.

</details>

**Speaker A**：所以，当我说一切都将被模拟时，我真正想去理解、并努力帮助我们团队乃至全世界达到的一个点是：今天我们所见到的许多东西，未来都会显得理所当然。希望再过几年或几个月，当我们回过头来看 Continuum 时，它给人的感觉可能会非常接近我们刚才向你们展示的那个切开橙子的视频。Continuum 以及我们在视频和 Runway 模拟方面所做的许多工作，目前仍处于非常早期的阶段，但我们正在走向一个真正可用、并且真正能够大规模扩展的阶段。因此，我们真正感到兴奋的是，在接下来的 8 到 12 个月里，我们在此展示的大部分内容都将发布给所有人使用。谢谢大家。

<details>
<summary>Original English</summary>

**Speaker A**: So when I say everything will be simulated, I'm really trying to understand or help not only our team but the world get to the point where a lot of what we'll see today will sound obvious. Hopefully in a few more years or months, we'll look back at Continuum and it might feel very close to the video of the orange that we just showed you. Continuum and a lot of the things we're doing in video and in Runway when it comes to simulation are still in very early days, but we're getting to a point where it actually works and it really scales. So we're really excited about is that for the next 8 to 12 months, we're releasing most of what I showed here for everyone to use. Thank you guys.

</details>

### AI Engineer 纽约大会闭幕与感谢

**MC**：随着 AI Engineer 2026 纽约大会圆满落幕，我们要感谢所有人参与这场精彩绝伦的盛会。为了分享最后的结语并正式收官，请大家再次欢迎来自 Turing Post 的主持人！

<details>
<summary>Original English</summary>

**MC**: As we come to the close of AI Engineer New York 2026, we'd like to thank everyone for being part of this incredible event. To share a few final words and officially wrap things up, please welcome back our MC from Turing Post.

</details>

**Ksenia Se**：太棒了！谢谢大家！谢谢 Crisal，也谢谢我们所有的演讲嘉宾。我想请大家再多留一分钟，我们还有一位非常特别的人要上台。

这三天里，我们探讨的范围令人瞩目——从构建智能体，到改变金融机构的运作模式，再到如何对世界进行模拟。我想我们当中不少人带走的待调研清单，比刚来的时候还要长很多。对于一个汇聚了众多工程师的会议来说，这正是一个非常合理的结果。感谢精心策划这一日程安排的团队、现场的工作人员、我们的赞助商与合作伙伴，以及准备好分享自己的成果、提出见解的每一位到场观众。请大家为彼此鼓掌！谢谢大家。

我希望大家在这里开启的交流，能够在下一届 AI Engineer 大会上转化为更多令人瞩目的成果。接下来，我想欢迎那位一直在幕后负责内容策划的灵魂人物登场，唯一且不可替代的——

<details>
<summary>Original English</summary>

**Ksenia Se**: Woohoo! Thank you, Crisal, and thank you to all of our speakers. And I would like to ask you to stay for one more minute. We have someone very special to see.

We've covered a remarkable range over these three days from building agents to changing how financial institutions work and how to simulate the world. I imagine quite a few of us have a longer list of things to investigate than we arrived with. That seems like a reasonable outcome for a conference full of engineers. Thank you the team who put this program together and the crew and our sponsors and partners and to everyone of you who came ready to share their work and ask questions and do clap please. Thank you.

I hope some of the conversations that you started here turn into things we will hear about at the next AI Engineer. And I want to welcome to the stage the guy who has been behind the curation, the one and only.

</details>

### 组织者总结与未来活动展望

**Organizer**：她刚刚介绍过了。嗨，非常感谢大家一直坚持到最后，也谢谢 Ksenia Gabri，请大家给她热烈的掌声！

谢谢大家。如果你还没看过——我知道她非常谦逊无私，这已经是她第二次担任主持人了——但如果你还没看过她在 Turing Post 上的视频，我强烈推荐你去看看。她有一个很棒的 YouTube 频道，花了很多时间在剪辑上，我非常钦佩这一点。非常感谢你。

希望这几天对大家来说都收获满满。我从赞助商、参会者和演讲者那里听到了很多反馈。我们真正在努力在纽约扎根建立阵地，这也是为什么我非常感激能有 Chris、Pim 以及所有其他优秀的纽约市 AI 创始人加入。我觉得在这座城市里，大家在这方面得到的关注和认可还远远不够，实际上这里无论是金融机构内部，还是在整体的 AI 研究、AI 基础设施等各领域，都在进行着非常多扎实而前沿的开拓性工作。

<details>
<summary>Original English</summary>

**Organizer**: She just did. Hi, thank you so much for staying to the end and thank you Ksenia Gabri. Give it all.

Thank you guys. If you haven't seen, so I know she's very selfless and she's MCing for the second time, but if you haven't seen her videos on Turing Post, highly recommend. She has a great YouTube channel and she's spending a lot of time editing that, which I really admire. Thank you so much.

I hope this has been a great few days for you. I heard a lot of feedback from sponsors, from attendees and speakers, and we're really trying to make a home in New York, which is why I'm so grateful to have Chris and Pim and all the other great New York City AI founders. This is something that I think people don't get enough love for in this city, which is how much real work and frontier pioneering work gets done both in the financial institutions and just in general AI research, AI infrastructure, and all that good stuff.

</details>

**Organizer**：所以，我不会耽误大家太长时间，简单讲一下我们接下来的活动安排。我现在穿的这件衣服就是为了 Code 大会准备的。Code 是我们的首个垂直领域峰会，而且我认为代码智能体（coding agents）确实代表着可验证 AI 发展方向的巅峰。此外，我们也在此确认，明年二月我们将在伦敦举办第二届欧洲 AI Engineer 大会（AI Engineer Europe）。

当然，还有所有活动中最为重磅的一场——规模超过其他所有会议总和的 World's Fair，预计明年夏天将在旧金山迎来一万人规模的盛会。从现在到那时之间，AI 领域还会发生大量的变化。到时候我们大家可能都已经失业了，但如果你失业了，那就意味着你有更多时间来参加 AIES 大会，对吧？

无论如何，希望大家玩得开心。非常感谢大家的莅临与支持。希望大家在专业领域结交到了许多朋友。回去之后也请继续保持交流，彼此多聚一聚。能够为你们提供这样一个社区平台，对我和我们的团队来说就是最大的回报。感谢大家的支持，我们明年再见！

<details>
<summary>Original English</summary>

**Organizer**: So I won't keep you too long. I'll just talk a little bit about our upcoming events. I'm wearing the shirt for Code now. Code is our first vertical summit and coding agents really I think are the sort of the pinnacle of where verifiable AI is going. We're also confirming that we are launching AI Engineer Europe again. That's the second year in London in February.

And obviously the big big show of all, bigger than all the other ones combined, the World's Fair, 10,000 people in San Francisco next summer. So there's a lot of AI that's going to be happening between now and then. We may be all out of a job, but if you're out of a job, that means you can come to more AIES, right?

So anyway, we'll all have a good time. Thank you so much for being here. Thank you for supporting us. I hope you all made lots of friends in professional contexts. Follow the conversation back home, right? Like and meet up among yourselves. That is what it's so rewarding for us and our team to provide this community for you. So thanks for your support. See you next year.

</details>