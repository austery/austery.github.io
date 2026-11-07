---
author: AI Engineer
date: '2026-11-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=T-42NrYjwxM
speaker: AI Engineer
tags:
  - agentic-workflow
  - post-training
  - llm-inference
  - context-caching
title: Ramp Labs 实践：在前沿模型迭代中追赶能力与优化成本
summary: Ramp 的 Alex 介绍了应用 AI 团队及 Ramp Labs 的实践，包括通过后训练专业模型超越前沿模型、探索 KV 缓存 cartridges 离线预载上下文，以及运用万级别智能体群体进行 MapReduce 渗透测试，助力企业降低延迟与 Token 成本。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Alex Shevchenko
companies_orgs:
  - Ramp
  - Prime Intellect
products_models:
  - Ramp Sheets
  - Qwen 3.5
  - Opus 4.6
  - Ramp Inspect
  - Ramp Router
media_books: []
status: evergreen
---
### 引言与背景：应用层公司的“苦涩教训”

大家好，我是来自 Ramp 的 Alex。我今天要讲的主题是：在等待前沿模型演进的同时追赶能力。先做个简短的自我介绍。我大约在三年前加入 Ramp，在较广泛的应用 AI 团队工作，负责多个不同的业务界面和产品，应用大语言模型（LLM）和机器学习让优秀的产品变得更好。在介绍 Ramp Labs 之前先说明一下，Ramp 是一家充满了“苦涩教训”（bitter lesson）的公司。在过去一年里，使用 LLM 的用例数量增长了 123%。

<details>
<summary>Original English</summary>
Hey everyone, I'm Alex from Ramp. Um I'll be speaking about chasing capabilities while waiting for the frontier to advance. So, quick uh intro about myself. I joined Ramp around 3 years ago uh on the broader applied AI team working on a bunch of different surfaces and products applying LLMs and ML to make a great product even better. Uh to and to to caveat my presentation on Ramp Labs, Ramp is an extremely bitter lesson filled company. Over the last year, the number of use cases that use LLMs has increased 123%.
</details>

与此同时，我们许多核心功能的 Token 开销在增加，但从单位经济效益来看，它们实际上正变得更便宜。因为现在不断有前沿模型发布，这些模型更便宜、更快、更好。因此，我们能够以低得多的成本提供相同水平的准确率。这是一个真正充满“苦涩教训”的模式。基于所有这些，我有时会被问到一个问题：为什么不干脆等待？像 Ramp 这样的应用层公司，为什么内部还要设立应用研究职能呢？为了回答这个问题，我想对比一下 2023 年的情况。

<details>
<summary>Original English</summary>
While at the same time, a lot of our top features are growing in token spend, but on a unit economic basis, they're actually becoming cheaper because there are frontier models that are being released uh all the time now, and these models are cheaper, faster, uh and better. And so, we're able to provide the same level of accuracy at a much lower cost. And so, this is a really bitter lesson filled uh pattern. And so, given all this, a question that I sometimes get, why not just wait? Why have an applied research function inside of a company like Ramp, an app application layer company, right? Um and to answer that, I would like to draw draw a parallel to 2023.
</details>

### 从 2023 到 2026：智能体构建的演进

回到 2023 年，当时大家能接触到的大概就是 GPT-4，构建智能体需要做大量工作。你必须建立非常严格的防护栏。模型无法回溯，也没有思考 Token。因此如果它走错了方向，就会一直往前冲，意识不到自己犯了错误。你必须在所有的 Prompt 上费尽心思，甚至某些同义词都会改变智能体的行为，因为它们没有在泛化用户意图上做好强化学习（RL）。你必须尽可能缩减和限定上下文范围，因为给智能体提供过多上下文只会让它陷入混乱。

<details>
<summary>Original English</summary>
Back in 2023, uh you had access to kind of like GPT-4, and creating an agent was a lot of work. Um you would have to create very, very strict guardrails. Models weren't allowed to backtrack. They didn't have thinking tokens. And so, if it went in the wrong direction, it would just kind of charge ahead and not realize that it made mistakes. You had to sweat over all of the prompts where to the point where um s- some synonyms could change the behavior of of your agent because the they weren't RL'd properly on generalizing to the user's intent. You had to reduce and scope down the context as much as possible because giving too much context to the agent would just confuse it.
</details>

即便在当时，我们也决定：我们必须发布这些东西，不能坐等 GPT-4.5 或 GPT-5 面世；我们现在就需要为财务专业人士提供服务。于是，尽管这并不容易，我们还是推出了像 Ramp Tour Guide 以及许多其他智能体。快进到现在 2026 年，构建智能体变得容易得多了。模型已经变得如此优秀，你基本上给它们 MCP 以及任何上下文，面对给定的任务，它们在理解该做什么方面做得非常出色。但我依然相信，我们能够再往下深入一层，为用户打造更加出色的体验，只是现在需要付出多一点努力。

<details>
<summary>Original English</summary>
And even back then, we decided, well, we need to ship these things. We can't wait for GPT-4.5 or GPT-5 to come out. We need to serve our financial professionals now. And we shipped things like Ramp Tour Guide and many other agents even though it was not the easy thing to do. And fast forward now to 2026, building an agent is a lot easier. The models have gotten so much better that you can kind of give them MCPs and access to kind of any context and they do a very very good job of understanding what they need to do given a task. But, I still believe that we can dig a layer down and create even better experiences for our users. It's just it requires a bit more effort now.
</details>

### 实践案例一：后训练专用财务模型

为了展示这一点，我带来了来自 Ramp Labs 的一些工作成果，分享三个我们将研究成果落地到 Ramp 本身的具体案例。首先是构建专业模型。去年 11 月，我们推出了 Ramp Sheets，这是非常早期的电子表格智能体之一。那是在两家前沿实验室推出各自版本的电子表格智能体之前。我们在 11 月的发布非常成功，一大批来自优秀公司的用户注册并开始使用它。我们意识到，这是一个非常通用的电子表格处理智能体；而 Ramp 内外部人员，包括我们所有的会计和财务专业客户，大部分时间都在与电子表格打交道。因此，我们可以将 Ramp Sheets 背后的框架与核心逻辑引入 Ramp 内部的许多其他场景。在构建这个功能的过程中，我们意识到可以通过 Ramp Labs 的研究让它表现得更好。

<details>
<summary>Original English</summary>
So, to present this uh some of our work from Ramp Labs, three specific cases of how we've applied research into Ramp itself. Starting with creating a specialist model. So, in November of last year, we launched Ramp Sheets, which was one of the really early uh spreadsheet agents. This was before the two frontier labs had launched their versions of spreadsheet agents and we had a very good launch in November. A bunch of users from great companies had signed up and started using it. And we realized that well, this is a very general purpose spreadsheet handling agent. And a lot of the work that people do on Ramp both inside of the company, but also all of our customers accounting and finance professionals are spending most of their days inside of spreadsheets. So, we can kind of take the spread the harness and the brains behind Ramp Sheets and added into a bunch of other um surfaces within Ramp. And as we were building this out, we realized, well, we can probably apply some research uh from Ramp Labs to make this even better.
</details>

我们坐下来开始审视：模型在这方面有哪些不足？当时使用的是类似 Opus 4.6 的模型，阻力最大的地方在于，当你将大量电子表格放入 Ramp Sheets 并要求它构建 DCF（现金流折现模型）或建立某种财务场景模型时，它一开始会花很多时间制定计划，然后调研其所能访问的所有表格，试图充分理解并理清全局情况。

<details>
<summary>Original English</summary>
And we sat down and we started looking, where do models fall short on this? And back then, this was like Opus 4.6 and the place that had the most friction was when you would drop in a lot of spreadsheets into Ram Sheets and you would ask it to build a DCF or or model some financial scenario, it would spend a lot of time creating a plan at first and then researching all of the sheets that it had access to to try to get a good understanding of and lay of the land.
</details>

Opus 4.6 是一个出色的模型，但它比较慢，而且思考 Token 也相当昂贵。因此我们退一步思考，决定训练一个检索模型，或者说类似财务问答的模型。在仍然保留前沿模型作为编排者的同时，将任务移交给这个快得多的模型，由它来为规划智能体执行财务问答。

<details>
<summary>Original English</summary>
And Opus 4.6 is a great model, but it was like pretty slow and the thinking tokens are also pretty expensive. And so, we we took a step back and and decided to train a retrieval model or kind of like a financial question-answering model that would while still keeping these frontier models as orchestrators, would then be handed off to the this much faster model that would do uh financial question-answering for that planning agent.
</details>

于是，我们与 Prime Intellect 公司合作，后训练了一个 Qwen 3.5 35B 模型。在具体任务的准确率上，我们实际上超越了当时处于前沿水平的 Opus 4.6，同时还能以极快的延迟提供服务。这样一来，就得到了一个速度快得多但同样聪明的模型，可以与顶尖智能的前沿编排模型协同工作。这是我们作为 Ramp Labs 工作的一部分，真正推向生产环境的一个非常成功的后训练范例。

<details>
<summary>Original English</summary>
And so, we partnered with the company Prime Intellect to uh post-train a Qwen 3.5 uh 35 billion um model and we actually got above Opus 4.6, which was the frontier back then uh exact task accuracy, while also being able to serve it at high cool uh level latencies. So, a much faster, but just as smart model that could then be used in uh in tandem with the really smart frontier orchestrator. Um and so, this was like a very successful um example of post-training that we had actually sent to prod as part of our Ramp Labs effort.
</details>

### 实践案例二：KV Cache Cartridges 离线上下文压缩

我们至今仍在探索的第二大方向是 KV 缓存技巧，尤其是 cartridges。这是一类非常有趣的技术，它允许你在离线状态下将多达 20 到 30 倍的上下文压缩到 KV 缓存中，并将其提供给你的智能体。对比刚才 Ramp Sheets 的例子，有很多任务是你明知在某个时间点必然会发生的。比如月末结账，一个月结束了，在次月的第一天，财务专业人员会去对账并封账。你知道他们需要检索的总账、账龄分析表以及相关文档。你可以将它们准备为上下文，但智能体仍然需要以 Agentic 方式进行检索，并建立清晰的全局理解。借助 cartridges，我们能够将所有这些工作进行压缩，在月初财务人员开始工作的前一天晚上离线构建好。

<details>
<summary>Original English</summary>
Uh the second uh big thing that we are actually exploring up to this day is uh KV cache tricks and particularly cartridges are really interesting um family of techniques where you're able to compress a lot of context up to 20 to 30 times more context into the KV cash offline and serve it for your agent. And so if you compare it to the RAM sheets example, for example, um uh there's a lot of tasks that you know are going to happen at some point, right? Like month-end close, a month finishes and on the first of the next month a financial professional will go and try to reconcile and close their books. You know kind of the ledger, the aging report and the documents that they will need to be retrieving. And so you could prepare them as context, but the agent will still need to agentically retrieve and and create a good picture and understanding of them. With cartridges, we're able to compress all of that work and build one overnight before the the financial professional starts their work on the first of the month.
</details>

一旦他们打开智能体，它就确切知道该做什么，因为所有上下文都已内置其中。与后训练相比，Cartridges 的门槛也低得多，因为它们进行自我对弈（self-play）的方式更具通用性。这类技术的注意事项在于，相比于后训练，实验室未来可能会将其作为 API 的一部分推出，作为其进军持续学习领域的一环。但即便他们真的在 API 中提供该能力，我们也会感到高兴，因为我们已经在公司内部积累了大量这种隐性知识，学习如何最好地应用这些技术。因此，即便它作为 API 发布，我们也能在第一天就驾轻就熟地直接上手使用。

<details>
<summary>Original English</summary>
And once they open up the the the agent, it knows exactly what it needs to do because it has all of the the context already uh built in. Cartridges are also a much lower lift in post training because the way that they do self-play is kind of a lot more generalizable. The caveat with stuff like this is that compared to post training, this is something that the labs might ship at some point is in their APIs and their foray into uh continuous learning. And even if they were to do it in the API, we would actually be happy because we are developing a lot of this tribal knowledge inside of the company um and just learning how best to apply these techniques. So even if it does ship as an API, we can just hit the ground running on day one knowing how to use them.
</details>

### 实践案例三：基于智能体群体与 MapReduce 的安全渗透测试

最后，我们推向生产环境的应用研究第三个例子，是关于智能体 MapReduce 以及智能体群体（agentic swarms）的工作。具体来说，我们在 Ramp Labs 博客上发表了一篇文章，介绍我们如何使用 10,000 个并行智能体对 Ramp 进行全面的渗透测试。在 Ramp，我们有一个名为 Ramp Inspect 的云端智能体，它帮助搭建起支持这种雄心勃勃的项目所需的所有基础设施与底层管道。我们能够启动 10,000 个并行智能体，将这项任务分解映射（Map）出去，尝试发现任何潜在漏洞，然后再对它们创建的工单进行智能体层面的归约（Reduce）。也就是说，利用 LLM 对漏洞进行去重，然后利用 LLM 进行对抗性重现，以确保这些漏洞是真实存在且严重的。

<details>
<summary>Original English</summary>
And finally, the third example uh of applied research that we are sending to prod is our work on uh agentic map reduce and kind of agentic swarms. So more concretely, we published an article on the RAMP Labs uh blog on how we uh used 10,000 parallel agents to pen test all of Ramp. Um so at Ramp we have a uh cloud agent called Ramp Inspect, which helps out with setting up all of the infrastructure and plumbing for something as ambitious as this. And we were able to spin up 10,000 parallel agents and then kind of map this work out, try to find any vulnerabilities, and then also agentically reduce on the tickets that they would create. So deduplicate them with LLMs and then try to reproduce them adversarially with LLMs to try to make sure that the vulnerabilities are real and important.
</details>

在所有这一切结束时，我们实际上发现了 7 个高危漏洞，并且全部完成了修复。有趣的是，我们在文章中描述的其中一个漏洞是通过电子邮件发送的 Lua 脚本注入攻击。在该技术栈中，没有任何单一组件是不安全的，群体智能体必须将多个组件拼凑在一起，并端到端地理解多个组件，才能发现这一问题。这项工作的另一个优势在于，它完全是自动运行的。你不需要占用任何人的时间，只需启动它即可，被过滤掉的未通过测试仅仅消耗了 Token 的成本。

<details>
<summary>Original English</summary>
At the end of all of this, we have actually found seven high vulner- high severity vulnerabilities that we all patched. Interestingly, one of the um vulnerabilities that we describe in that article is a Lua script injection that you could send over via email. And no single component of that stack was unsafe. And the kind of swarm had to patch together multiple components and understanding of multiple components end-to-end in order to be able to figure this out. And the other nice thing with this is that this is all running automa- automatically. You don't need to spend anyone's time, it's just you start it and the only thing that uh failed failed passes that get filtered out is the cost of the tokens.
</details>

除了构建支持这些群体的全部基础设施之外，另一件有趣的事情是，我们会研究如何在这类群体中最好地使用模型。我们在同一篇文章中发表的一项有趣洞察是，你实际上可以使用比前沿推理模型便宜多达 5 倍的开放权重模型。而且由于你是以群体形式搭建的，检出率并不会降低 5 倍。因此，你可以花更多预算在这些较便宜的 Token 上，同时获得几乎同样出色的检出率。

<details>
<summary>Original English</summary>
The other thing that's interesting outside of just building out all of the infrastructure to support these swarms is that we do research into how to best use models as part of these swarms. One of the interesting insights from that same article that we published is that you can actually use open weight models that are up to five times cheaper compared to the frontier reasoning. And because you're set- setting it up as a swarm, the detection rate is not five times lower. So you can kind of spend more on these cheaper tokens and have almost as good of a detection rate.
</details>

### 产品赋能：Token 开销管理与智能路由

如果纵观所有这些案例，你会发现很多做法都有一个共同模式：试图节省时间和金钱。降低延迟即节省时间，减少 Token 成本即节省金钱。这其实正是 Ramp 的口号——“为我们的客户节省时间和金钱”。在此，我想介绍两款 Ramp 实际提供的、受到了 Ramp Labs 研究影响的产品。第一款是 Token 开销管理（Token Spend Management），它接入你的一系列 API Key，能够清晰呈现 LLM 在公司内部的使用情况。它不仅能在 API Key 或用户维度展示 Token 开销，还能进一步深入到会计类别，甚至是分析开销可获得的税收抵免等。它还会更进一步，构建一套分类体系，对 LLM 的使用情况进行上下文与语义分析，让你真正了解 LLM 的使用场景，而不仅仅是归因到公司内部的某个团队或个人。

<details>
<summary>Original English</summary>
Um if you follow through all of these examples, you kind of notice a pattern of a lot of them is attempts at saving on time and saving on money. So, reducing latency, which is time, and then reducing on token cost, which is money. That's actually Ramp's uh slogan, uh saving our customers time and money. Um and so, I'd like to to point to two uh products that we actually offer from Ramp that have been um influenced by Ramp Labs' research. The first one is token spend management that connects to a bunch of uh your API keys and is able to give you a really good picture of how LLMs are being used inside of your company. Not only token spend on an API key basis or a user basis, but digging deeper, accounting categories, um and even things like uh tax credits that you can get by uh analyzing the spend. It also goes deeper and we create a taxonomy that uh contextually analyzes and semantically analyzes the LLM usage, so you can actually understand how LLMs are being used outside of just attributing it to a team or a person inside of your company.
</details>

第二款产品是 Ramp Router，它同样致力于改善智能体的延迟。我们与 Ramp Labs 合作开发了多种路由策略，比如 Nvidia Switchyard 以及智能灵活工作卸载等，以此兼顾延迟优化和单位 Token 开销降低。目前已有多种不同的路由策略可用，未来还会推出更多。如果你对这两款产品中的任何一款感兴趣，可以拍下屏幕上的 URL 或扫描二维码。给大家留一点时间。

<details>
<summary>Original English</summary>
And then the second one is Ramp Router, which also leans into improving your the latency of your agent, where we have a bunch of routing strategies that we work with Ramp Labs to develop, uh things like Nvidia Switchyard, things like smart flex offloading of work to both improve latency and um cost per tokens that you spend. And there's a bunch of different strategies already available for the the for routing, and even more coming out later. So, if you're interested in any of these two products, you can take a photo uh of the URLs or or scan the QR codes there. Give you a second. Awesome.
</details>

### 更多前沿研究与结语

此外，我也邀请大家关注 Ramp Labs 的博客，我们在上面发表了许多我今天没来得及在此次演讲中涵盖的非常有趣的文章。其中非常值得关注的一篇是关于 Portal 的，我们找到了将后训练经验从一个模型迁移到另一个模型的方法。你可以在一个模型（比如前面提到的 Qwen 3.5）上进行类似 LoRA 的后训练，然后将其迁移到 Qwen 的更新版本，甚至跨越不同的模型家族。这种使用潜在表示进行后训练、随后再投射到不同模型的方法，确实摊薄了后训练所需付出的成本。

<details>
<summary>Original English</summary>
And then I I'd also invite you to check out our Ramp Labs uh blog, where we publish um a bunch of really interesting articles that I haven't had the chance to cover as part of this presentation. Um notably one of the really interesting ones is portal where we figured out a way of uh transferring learnings from one post train to another. So, you could do something like a Laura uh post train on one model, so like the Quen 3.5 that I was describing, but then transfer it to newer versions of Quen or even across different families. So, you're post training with this latent that then can be projected onto different uh models and that really amortizes the cost that you have to spend on post training.
</details>

博客上还有更多关于智能体 MapReduce 的文章，不仅涉及我们所做的渗透测试，还包括分析并建立 LLM 使用分类法（这项工作已融入了 Token 开销管理产品中）；还有自改进监控（self-improving monitoring），我们利用 LLM 在 DataDog 上为大量产品服务自动创建监控，并在警报触发时无需人工介入自动改进这些监控，力求打造超级健壮、极具弹性的软件；最后是语义标记（semantic tagging），这是在一系列用户会话上进行智能体 MapReduce 的有趣尝试，我们可以对开放式的分类体系进行标注和构建，即在事先不知道 LLM 使用集群分布的情况下尝试建立分类，并与公司内部的开销进行对账。如果你对这类研究感兴趣，可以访问 x.com/ramplabs 查看更多研究成果。

<details>
<summary>Original English</summary>
Uh more blog posts on agentic map produce, so not only the pen testing stuff that we did, but also things like um analyzing and creating taxonomies of LLM usage, which is stuff that has gone into the token spend product. Um things like self-improving monitoring where we use uh LLMs to automatically um create monitors with DataDog on a lot of our product services and then as the words come in, improve those monitors automatically without a person in in the loop to try to basically create super super robust and resilient software. Um and finally semantic tagging, which is this interesting uh foray into creating this um agentic map produce over a bunch of user sessions where we can annotate and create taxonomies that are open-ended. So, not knowing um ahead of time which what are the clusters of LLM usage and trying to create a taxonomy that can then be reconciled against the spend inside of the companies. So, if uh if you're interested in this uh type of research, x.com/ramplabs where you can uh go and and check out more of our research.
</details>

如果大家有任何其他问题，或者想探讨应用研究中的具体用例，屏幕上有我的 Twitter。我就讲到这里，谢谢大家。

>> [掌声]

<details>
<summary>Original English</summary>
And uh there's my Twitter if you have any other questions or uh want to talk about some use case as part of your applied research. And that's it. Thank you. >> [applause]
</details>