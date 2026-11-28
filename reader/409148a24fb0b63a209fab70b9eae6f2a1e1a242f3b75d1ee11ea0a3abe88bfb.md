---
author: a16z
date: '2026-04-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=krdrkl38nRw
speaker: a16z
tags:
  - ai-transformation
  - workforce-reduction
  - agentic-systems
  - generative-ui
  - business-strategy
title: AI 驱动的组织变革：Block 的裁员、AI 基础设施与未来战略
summary: 本次访谈聚焦 Block 公司在 AI 浪潮下的组织变革。Owen Jennings 详细阐述了公司为何进行大规模裁员，强调 AI 在提升生产力方面的革命性作用，并介绍了 Block 自主研发的 AI 基础设施如 Goose 和 Builderbot。访谈还深入探讨了 AI 如何重塑软件开发、客户支持及产品形态（如生成式 UI），并展望了企业未来的可持续竞争壁垒将源于对复杂事物的深刻理解。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Owen Jennings
  - Jack Dorsey
  - Alex
companies_orgs:
  - Block
  - Square
  - Cash App
  - Afterpay
  - Nvidia
  - Meta
  - OpenAI
  - Anthropic
products_models:
  - Goose
  - G2
  - Builderbot
  - Moneybot
  - ManagerBot
  - Opus 46
  - Codeex 53
  - GPT-4o
media_books: []
status: evergreen
---
### AI 驱动的组织变革与生产力飞跃

**Interviewer**: 最大的壁垒将是哪些公司能够理解一些别人很难理解的东西。如果你的答案是“我不知道”，那么你可能会被“氛围编码”淘汰。

<details>
<summary>Original English</summary>

**Interviewer**: The biggest moat is going to be which companies understand something that's super hard for other people to understand. And if your answer to that is I don't know, then you maybe could get vibe coded away.

</details>

**Interviewer**: Block 是最早做出一个非常重大决定，裁减 40% 员工的公司之一。是什么导致了那个决定？

<details>
<summary>Original English</summary>

**Interviewer**: >> Block was one of the first to make a pretty drastic decision in cutting 40% of the workforce. What led up to that decision?

</details>

**Owen Jennings**: 二三十年前，公司人数与产出之间就存在一种相关性。我认为那基本上被打破了。我们看到的是，一两个工程师，或者一个在工具方面的设计师和工程师，随着时间的推移，他们的生产力可以提高 10 倍、20 倍，甚至 100 倍。很明显，这些系统将比一千个做同样工作的])): 
我们正看到，1000个人工在做这些工作。我认为，从根本上来说，对于一个给定的产品或路线图，你将需要更少的工程师、更少的设计师、更少的产品经理。我认为那非常非常清楚。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> There's been this correlation between the number of folks at a company and the output from the company for decades and decades. I think that basically broke and what we were seeing is that one or two engineers who was on the tools is able to be 10 20 100x more productive over time. It's like pretty obvious that these systems are just going to be so much better than like having a thousand humans who are doing that work. I I do believe that fundamentally for a given product or for a given road map, you're going to need fewer engineers, fewer designers, fewer PMs. I think that's like very very clear.

</details>

**Interviewer**: 那么，你周一上班，公司 40% 的人没了。你们的运营方式上，最大的区别是什么？

<details>
<summary>Original English</summary>

**Interviewer**: >> So you show up on Monday, 40% of the company's gone. What's the most meaningful difference in how you're operating?

</details>

**Owen Jennings**: 我认为最大的事情是，一家大型上市公司围绕 AI 重塑自身，这究竟是什么样子？ Owen Jennings 是 Block 的业务主管，负责 Square、Cash App 和 Afterpay 的产品运营和客户支持。在此之前，他曾是 Cash App 在关键增长期的 CEO。最近，Block 执行了约 40% 的裁员，并且他们坦诚 AI 是这一决定的关键组成部分。Owen 已经大规模地经历了跨产品线和业务单元的 AI 转型，所以我们将深入探讨这次裁员的决定，Block 如何适应业务的当前和未来状态。非常感谢你 Owen，欢迎来到舞台。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> I think the biggest thing is what does it actually look like for a large public company to restructure itself around AI? Owen Jennings is the business lead at Block where he oversees product operations and customer support across Square, Cash App, and Afterpay. Before this role, he was the CEO of uh of Cash App during its critical scaling period. And recently uh block executed a roughly 40% reduction in force and they've been pretty candid about AI being a critical component of that decision. Owen has gone through the AI transformation at scale across product lines and business units and so we're going to dig into the that decision around the riff how block has adapted the current and future state of the business. So thank you so much Owen. Welcome to the stage.

</details>

**Owen Jennings**: 谢谢。

<details>
<summary>Original English</summary>

**Owen Jennings**: Thanks.

</details>

**Interviewer**: 太棒了。

<details>
<summary>Original English</summary>

**Interviewer**: Awesome.

</details>

**Owen Jennings**: 嗯，你知道，Jonathan，我认为他非常出色地为这次对话奠定了基础。你知道，谈论成为一家创始人领导的公司有多么重要。你知道，Block 是最早做出相当大的决定的公司之一，裁减了 40% 的员工。嗯，也许可以跟我们讲讲是什么导致了那个决定，以及你是如何思考的。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> Um, so you know, Jonathan, I think did an amazing job kind of setting the stage, you know, for this conversation. Uh, you know, talking about how important it is to be founderled. Uh, you know, Block was one of the first to make a pretty drastic decision in cutting 40% of the workforce. Um, maybe walk us through kind of what led up to that decision and how you thought about it.

</details>

**Owen Jennings**: 好的。我认为这一切大概始于两三年前。我认为 Jack 的一个特质是，我觉得 Jack 通常是对的，而且通常是早期的。嗯，有时是非常早期的。嗯，我认为这一点贯穿了 Twitter、Square、Cash App、Bitcoin 等。所以我们在 agentic development（自主式开发）方面非常早就开始了。我们实际上在 2024 年初推出了 Goose，这是我所知的第一个 agent harness（代理能力聚合平台）。然后这开始改变我们处理软件开发的方式，以及我们如何思考内部工具。我想说，在 24 年和 25 年的那个时期，我们取得了非常有意义的进展。嗯，然后在 11 月底，12 月的第一周，发生了一个二元变化。你基本上有 Opus 46，你有 uh codeex 53，基本上你得到了一个转变，我认为工具和基础模型在编写代码方面相当好，尤其是在新项目和类似绿色领域方面。嗯，几乎在一夜之间，或者说在几周内，变得清楚的是，现在它们在处理现有的复杂代码库方面能力超强。嗯，所以发生了一个巨大的范式转变，至少从我的角度来看，几十年来，公司人数与产出之间一直存在着一种相关性。我认为这在 12 月的第一周基本上被打破了，我们看到的是，一到两个工程师，或者一个设计师和一个工程师，他们在使用这些工具（我们所说的“quote unquote”）时，生产力可以提高 10 倍、20 倍，甚至 100 倍。所以，这确实是我们几周前做出决定的根本原因。我们在第一季度讨论了“这从根本上意味着什么？这在我们如何构建产品、如何为客户构建软件以及如何运营一家公司方面意味着什么？意味着什么？”我们和 Jack 以及执行团队一起在第一季度讨论了这个问题。嗯，最终，这让我们走到了今天这个地步，我们进行了裁员，人数略高于 40%。你知道，甚至不像我们刚才谈到的那样，工具在开发方面得到了非常显著的流转，所以裁员的幅度要大得多。如果你想到像外展销售或客户管理这样的事情，裁员就非常少。嗯，所以这就是我们正在应对的。我能稍微推敲一下吗？我是说，Alex 在大约一小时前介绍会议时，谈到了“零增长期”。你知道，多少裁员是 2021 年过度招聘的遗留问题，还是 AI 和产品实际生产力提升在业务中的作用？如果你看看我们从 2019 年到 2024 年的每名全职员工的毛利润，我们基本上处于所有竞争对手的中游。嗯，如果你看看去年，我认为我们处于中等水平，我不知道，可能是第二梯队或什么的。我认为主要是 Nvidia 和 Meta 在我们前面。嗯，然后当你看看我们所做的事情的构成时，如果你认为那是“效率低下和臃肿”等等，那么这次裁员本应影响运营团队和类似的东西。这些实际上是对开发团队进行的非常有意义的裁员。如果不是因为一项技术和一种工具从根本上改变了我们的构建方式，你不会对开发团队进行如此大规模的裁员。我的意思是，我们不再手工编写代码了。那已经结束了。那就结束了。嗯，所以，总之，每个人都有自己的说法。嗯，基本上不属实。

<details>
<summary>Original English</summary>

**Owen Jennings**: Sure. I I think I would pro it probably starts two or three years ago. I think one thing about Jack is I I find Jack to be generally right and generally early. Uh sometimes very early. Um and I think that's flowed through Twitter, Square, Cash App, Bitcoin, etc. And so we were pretty early on the agentic development side. We actually launched Goose, which was the first agent harness, at least that I know of, um, in early 2024. And that started to augment how we approached software development, uh, how we thought about internal tooling. And I would say that over the over that period 24 and 25, it was like pretty meaningful progress. Um, and then late November, first week of December, it was just there was a binary change. you basically have Opus 46, you have uh codeex 53 and essentially you get this shift where I think the the the the tools and the foundational models were pretty good at writing code especially for new ventures and kind of like green space. Um it became clear almost overnight maybe in a couple of weeks that now they're incredibly capable working with existing complex code bases. Um and so there was a massive paradigm shift where at least from my perspective there's there's been this correlation between the number of folks at a company and the output from the company uh for you know decades and decades. I think that basically broke the first week of December and what we were seeing is that one or two engineers or a designer and an engineer who was on the tools quote unquote as we say is able to be 10 20 100x more productive. And so that's really what led us to make the the decision a few weeks ago. We spent Q1 discussing like what does this mean fundamentally? What does this mean in terms of how we're going to build products, how we're going to build software for customers, and then also um how we're going to run a company. What is it going to mean to actually run a company? And we spent Q1 as an executive team uh with Jack um working through that. Uh and ultimately that's what led us to this place where where we we did a reduction in force that was you know slightly greater than than 40%. And that wasn't even uh you know to the to the conversation we were just having the tools were flowing through really meaningfully on the development side and so the cuts were way larger on the development side. If you think of something as outbound sales or account management um the cuts were you know fairly dimminimous. Um and so that was really what we were reacting to. C can I push you a bit on this a little bit? I mean, Alex when he kind of introduced the, you know, the conference uh just, you know, an hour ago talked about the zer period. Uh, you know, how much of the riff was sort of overhang from 2021 kind of overhiring versus AI and and kind of like the product actual productivity gain is going to be in the business? Like if you look at where we were from a from a gross profit per full-time employee basis from like 2019 through 2024, we're basically like right in the middle of the pack with all of the um uh with all the competitors. Um if you look at last year, I think we were kind of I don't know second quintile or something like that. I think it's basically like Nvidia and Meta that are ahead of us. Um, and then when you look at the composition of what we did, if you thought it was like croft and bloat and so on and so forth, then like this riff would have acred to the operational teams and like like that sort of stuff. Those were really really meaningful cuts on the development side. You don't make really really significant cuts on the development side if you're not seeing a technology and a tool that's just fundamentally changed how we build. I mean, we're we're like we're not writing code by hand anymore. That's over. That's done. Um and so so anyway, everyone has their narrative. Um it's largely not true.

</details>

**Interviewer**: 嗯，那么，能否让我们了解一下，你们是如何在文化和运营上实际执行这次转型的？

<details>
<summary>Original English</summary>

**Interviewer**: >> Um so maybe just walk through like tactically how did you actually execute you know this this transition you know culturally you know operationally in the business.

</details>

**Owen Jennings**: 嗯，我认为，嗯，这次裁员的好处是，相对于 Block 或其他公司发生的一些事情，我们是从盈利和营业收入的优势地位出发的。所以有时，当裁员是出于严格的财务动机时，CFO 或 CEO 会说，“好吧，我们需要裁员 16% 来达成这个目标。” 而事实并非如此。我们说，“考虑到现在 AI 工具的普及程度以及我们对未来几个月和几个季度的预期，组织应该是什么样的？” 我们有一些核心原则。嗯，第一个是可靠性。当你做这么大的事情时，最坏的情况是发生宕机或服务中断。所以这是零容忍，完全不可接受。显然，过去几周情况一直很好，这很棒。第二个是与客户建立信任、合规以及应对监管环境。我们都身处一个超级复杂、细致入微的监管环境中。这是不可妥协的。我们必须确保我们做得对。例如，我们基本上没有触碰我们的合规团队和合规技术团队。即使工具在那里，我们也觉得“我们不冒险。” 然后第三点是继续推动可持续增长。所以路线图上有一些我们知道我们正在构建的东西。我们需要继续做。我们知道这可能是一个三人的小组，而不是一个 14 人的功能团队在构建它。我们想确保我们继续构建这些功能，并继续进行长期的投资。然后我们从零开始构建了组织。在某些领域，比如监管委员会团队或 SDRBDR 团队，组织看起来与一月份非常相似。嗯，在开发方面，它看起来完全不同。嗯，然后，你知道，从执行的角度来看，你知道我们考虑得非常周全，显然我在公司已经 12 年了。我们分道扬镳的许多人是我们十多年的朋友和同事。嗯，我们能够慷慨地提供遣散费。我们没有立即切断人们的技术访问权限，这可能会很糟糕。我们选择进行一次全员大会。所以 Jack 和执行团队面对大家解释这个决定及其背后的驱动因素。嗯，我想那是在周四。我想，周五、周六、周日，有很多震惊，处理模糊性。嗯，然后我们一直在做的是，我们大大减少了会议数量，大概减少了 70% 或 80%。所以现在我有时间去构建和工作，而不是连续不断的会议。我们每周也与公司开会。所以我们每周一都会与 Jack 进行一到两个小时的全员大会。感觉就像我们更小了，更精简了，层级更少了，跨度更大了，这又回到了构建。

<details>
<summary>Original English</summary>

**Owen Jennings**: So I think so we were um the the the nice part about this riff uh relative to some other you know things that have happened at block or at other companies is we were coming from a position of strength on a on a profitability and operating income side. And so sometimes when it's really financially motivated, you know, the CFO or the CEO says, "Okay, we need to do a 16% riff in order to like hit this hit this target." And um that wasn't the case at all. We said, "What should the org look like given how these AI tools are flowing through now and what we expect to happen in the in the coming months and quarters." We had some core principles. Um the first one was reliability. When you do something this size, worst case scenario is you have an outage or you go down. So that's like P 00 not acceptable at all. Obviously, you know, things have been great over the past several weeks, which is fantastic. Second is building trust with customers and um compliance and navigating the regulatory environment. We all operate in a super complex nuanced regulatory environment. That's a non-negotiable. We have to make sure that we're that we're doing doing right there. For instance, like we we basically did not touch our our compliance team and our compliance technology team. Even if the tools are there, it's like let's not take any risks. And then third was let's continue to drive durable growth. So there's things that are on the road map that we already know that we're building. We need to continue to do that. We know that it might be a squad of three people instead of a feature team of 14 who's building that. We want to make sure we're continuing to build those features and that we're continuing to make longerterm bets. And then we built up the org from scratch. And in some areas like um the regulatory council team or the SDRBDR team, the org looked pretty similar to how it looked in January. Um on the development side, it looks completely completely different. Um and then you know from a from an execution perspective um you know we thought very deliberately obviously I've been in the company 12 years. A number of folks who we parted ways with are friends and colleagues for for you know more than a decade. um we were in a position where we're able to be generous in terms of you know the the the severance packages that we gave. We didn't cut people's technology access instantly which can suck. Uh we chose to have an all hands with everybody at the company. So Jack and the executive team were um you know looking each other in the eyes and explaining this decision and explaining the the drivers behind it. And um I I think that that it was on a Thursday. I think like the Friday, Saturday, Sunday there's a lot of shock uh dealing with ambiguity. Um and then what we've been doing is uh we massively reduced the number of meetings we have probably like 70 or 80%. So I now have time to like build and work and it's not backto-back meetings. We're also meeting with the company every week. So we have like a one or two hour all hands with Jack every every Monday. It just feels like we're we're smaller, we're leaner, we have fewer layers, we have larger spans, and it's it's been back to building.

</details>

**Interviewer**: 那么，周一你上班，公司 40% 的人没了。运营上最大的不同是什么？我不知道，也许是在 EPD（工程、产品、设计）或其他部门？

<details>
<summary>Original English</summary>

**Interviewer**: >> So, you show up on Monday, 40% of of the company's gone. Like, what how is what's the most meaningful difference in how you're operating? I don't know, maybe it's in the EPD or elsewhere.

</details>

**Owen Jennings**: 嗯，我认为，有几个不同的方面。我认为最大的事情是，我对像这样的一些组织变革可能如何在科技行业传播有一些担忧，这又回到了创始人的观点。如果你不是创始人领导，也没有能力去大胆决策，那么你可能会采取更渐进的方式。所以，感觉就像你裁员 15%，然后觉得“哦，没关系”，然后你再裁员 15%，这在文化上对你的团队来说是毁灭性的，因为总有一种潜在的裁员阴影笼罩在你的肩头。嗯，这显然是一个走向不同方向的决定。我认为我们从这次裁员中获得的一个好处是，我们已经看到了 AI 工具使用量的显著增加，尤其是在开发方面。这是一个巨大的强制性功能。就像，如果我们正在构建 Moneybot，并且想将其推广到 50% 的用户，而过去有一个 15 人的团队在负责，现在只有四个人加上 2000 美元的代币。这是无限的代币访问，你可以在 Cloud Code 上使用快速模式。嗯，所以现在你有四个人加上这些工具。就像，好吧，你需要有八个 Goose 实例在运行，你需要将工作流程从顺序处理 PR、提交、获取审查、进行更改，转变为我这里有 14 个代理正在代表我构建 PR，我将需要在所有这些之间进行上下文切换，这不仅仅是在软件开发方面，也适用于产品经理，也适用于增长营销人员。我本人也一样，我有很多代理在运行，我必须去检查。嗯，它不再是一个线性的工作流程，而是更像，在后台有 10 到 20 个代理在做很多事情，然后我需要检查工作，推动它，改变它，或者你懂的，然后我就可以提交到 GitHub，然后我就可以获取 markdown 文件。我们可以把它放在“事实来源”中，然后继续前进。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> Um, I think that there's a there's a few different components to this. I think the biggest thing is so one concern that I have with like how some of these org changes might flow through the tech industry is that and and it gets back to the to the founder point. If you're not founder le and you don't have the the ability to be bold, then you're going to probably take a more incremental approach. And so the way that that's going to feel is like you do a 15% riff and it's like, oh, it's fine. and then you do another 15% riff and then culturally that's just like devastating for your team because there's always this like pending riff looming looming over your over your shoulder. Um this was obviously a decision to go in a different direction. I think one of the benefits that we got from this is like we were already seeing a a very meaningful increase in AI tool usage especially on the development side. This is just a massive forcing function. Like if we're building um okay, we're building Moneybot and we want to roll Moneybot out to 50% and there used to be a team of 15 people working on it and now there's a team of four people plus $2,000 on the tokens. That's this is like un unlimited access to tokens and you can use fast mode on cloud code. Um so now you have four people plus the tools. It's like okay well you need to have eight instances of goose up and you need to shift your workflow from sequentially working through a PR submitting it getting a review making the change to I have 14 agents who are building PRs on my behalf right now and I'm going to context switch between all of those and it's not just uh on the software development side it's for PMs too it's for growth marketers too the biggest shift myself included I I have you know countless agents running right now that I have to I have to go check on. Uh it's it's not um it's less of a linear workflow and it's more of like in the background there's 10 or 20 agents who are doing a whole bunch of stuff and then I have to check in on the work and nudge it and change it or what have you and then I can commit it to GitHub and I can I can get the markdown file. We can put it in the source of truth and we can move on.

</details>

**Interviewer**: 是的。所以我们现场有很多上市公司，也有很多创始人创办的企业。你是否预计其他公司会走类似的道路？我猜想，为了成功，需要具备哪些条件？

<details>
<summary>Original English</summary>

**Interviewer**: >> Yep. So we have a lot of you know public companies in the audience. We have a lot of founder businesses in the audience. Do you expect other companies to kind of follow a similar path and and I guess what conditions need to be in place for that to be successful?

</details>

**Owen Jennings**: 我不一定想……我在开头谈到了 2023、2024 和 2025 年所做的基础工作。比如我们构建了这个 agent substrate（代理基底）Goose，然后我们在其之上构建了大量公司内部的工具。我们有一个内部使用的 agentic operating system（自主式操作系统）叫做 G2，任何人都可以自动化任何确定性工作流。所以，我认为要成功需要付出努力。我预计许多公司都在做这项工作。有些公司比其他公司领先得多。嗯，所以，我不知道会发生什么。我想说的是，就我而言，我确实相信，从根本上说，对于一个给定的产品或一个给定的路线图，你将需要更少的工程师、更少的设计师、更少的产品经理。我认为这在 12 月之后非常非常清楚。嗯，这并不一定意味着世界上工程师、设计师和产品经理的总数会减少。这就像经典的 Jevons 悖论，我认为现在可能只是有更多可以构建的东西了。嗯，所以，我不知道，你知道，一家科技公司可能会小得多，但可能会出现 50 或 100 家新的科技公司，或者你将在历史上从未有过这些开发工作的行业和领域开始出现开发工作。嗯，但我不是来预测未来的，我专注于 Block。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> I I I don't I don't necessarily want to like I I talked at the beginning about um the ground work that happened in 23 24 and 25 like we built this agent substrate goose and then we built a lot of tooling at the company on top of it. We have an agentic operating system internal only called G2 where anyone can automate any deterministic workflow. So anyway, I think there's work to do to to be successful. I would expect many companies are doing that work. Some of them are incredibly um far ahead than than others. Um and so I I I don't know what to expect. What I will say is like to the extent that I I do believe that fundamentally for like a given product or for a given road map, you're going to need fewer engineers, fewer designers, fewer PMs. I think that's like very very clear based after like December. Um that doesn't necessarily mean that there's going to be fewer engineers, designers, and PMs in the world. Um, it's like the classic Jevans paradox thing where I I think that there's probably now just a superset of things that that can be built. Um, so I don't know, you know, a given tech company might be might be way smaller, but there might be 50 or 100 more tech companies or you're going to start getting this development working in in sectors and and areas where that hasn't historically been the case. Um, but I I'm not here to to predict the future. I'm focused on block.

</details>

**Interviewer**: 嗯，你说得对。你谈到了你构建的一些 AI 基础设施。也许你可以更深入地讲讲，你知道，它如何影响技术？我也很好奇，你在你负责的其他业务领域，比如运营和客户支持，是如何使用 AI 的？

<details>
<summary>Original English</summary>

**Interviewer**: >> Uh, fair. you you talked a bit about kind of the some of the AI infrastructure you build. Maybe you can get go in a bit more depth uh you know both in how it's impacting the kind of technology or I'm also curious about you know how are you using AI in other parts of the business you oversee ops customer support.

</details>

**Owen Jennings**: 是的。嗯，上周在一个投资者会议上，有人问我 AI 如何在 Block 中发挥作用。对我来说，这就像在问“计算机是如何在 Block 中发挥作用的？”这是一种根本性的、内在的东西，在过去 18 个月里以二元方式发生了改变，然后在过去四个月里感觉又发生了翻天覆地的变化。嗯，所以我会将其分为内部和外部，以及我们如何思考我们的产品，我们提供给客户什么，然后我可以谈谈未来以及我们认为事情的发展方向。在内部方面，我认为最大的区别在于组织的构成。所以我们过去有那种经典的层级结构。它很实用，非常好，但基本上是标准化的，就像你在许多中型科技公司看到的。所以你会有大约八名服务器工程师，四名客户端工程师，一位产品经理，一位设计师，你会按部就班地推进你的路线图。现在我们有小型团队。所以团队大约有一到六人。嗯，比其他团队小很多。我们有更多的灵活性和流动性，一个团队可以在这个产品上工作几个周期，上线后，再转向另一个产品。嗯，这与一两年前的情况不同，那时我属于银行团队，我将永远属于银行团队。我们层级也少得多。所以，在开发方面，我认为我们可能削减了 50% 或 60% 的层级。嗯，在产品方面，我只有两层，可能在少数地方有三层，信息流动非常自由。我认为，就我们实际的构建方式而言，在开发方面，事情已经发生了变化。我认为每个人都可能已经看到了，你知道，美国的每个 CEO 都在 Twitter 上展示他们在 GitHub 上的绿色标记。嗯，但这是真实的。我们所有的设计师都在提交 PR。我们所有的产品经理都在提交 PR。这已经不再那么令人兴奋了。我认为更有趣的是，我们有类似于 Cloud Code 的内部工具，但它们更深入地集成到我们的基础设施中。我们有一个叫做 Builderbot 的工具。Builderbot 正在自主合并 PR，并真正地将功能构建到 100%。我们有一些相当复杂的功能已经构建到 100% 了。但更多时候，它是将它们构建到 85% 或 90%，然后由一个拥有大量上下文并理解的人来完成最后的 10%。所以这感觉非常非常不同。从想法到它能够到达数十万或数百万客户手中，这个过程自去年 12 月以来被大大压缩了。在开发之外，我认为我们看到的大部分情况是，只要存在确定性的工作流，我们就能自动化它。因此，一般来说，在一个大型科技公司里，你会看到个体员工在处理队列。很多这方面的工作正在被完全自动化掉，比如从客户支持的角度来看，这并不新鲜，但我们的聊天机器人和 AI 电话支持等等正在自动化我们收到的大部分查询。然后它涉及到产品运营、风险运营和合规运营，以及任何类型的决策，一般来说，模型和代理会比人类做得更好。目前，我认为至关重要的是我们要有人参与。这是你与合作伙伴和监管机构交谈时的关键“流行语”。嗯，但随着时间的推移，很明显，这些系统将比拥有成千上万的人来做这些工作要好得多。所以，这是内部方面。嗯，在产品方面，我认为……

<details>
<summary>Original English</summary>

**Owen Jennings**: >> Yeah. Um so I got asked at a investor conference uh last week like how is AI like flowing through block and to me that it's like asking um how are computers flowing through block? uh like it's it's a uh fundamental in-built thing that has changed on in like a binary way over the past 18 months and then feels like it changed all over again in the past four months. Um so I'll break it down into internal and then external and how we're thinking about our products, what we're putting in customers hands and then I can talk a little bit about the the future and where we think things are going. So on the internal side, I think the biggest difference is the shape of the of the org. So we used to have kind of like a classic hierarchical uh structure. It it was functional. Um which was great, but it was like fairly standard if you like averaged through a bunch of medium-sized tech companies. Um and so you would have kind of like eight server engineers, four client engineers, a PM, a designer, and you would work linearly through your road map. Now we have um small squads. So squads of like one to six people. Um so meaning meaningfully smaller than the other teams would be. And we have way more flexibility and and fluidity where a given squad can work a few cycles on this product, get it live and then a cycle on this other product. Um which is different than how things worked a year or two ago where it's like I'm on the banking team. I'm going to be on the banking team forever. We also have way fewer layers. So on the development side, I think we probably cut our layers by I don't know 50 or 60%. Like on the product side, I only have I think two layers, maybe three layers in a in a couple places and so information is flowing um way more freely. I think that then in terms of how we actually build on the development side, things have changed. I think everyone's probably seen, you know, every every CEO out there is going on Twitter and showing their like green dot on on uh on GitHub. Um, but that's real. Like all of our designers are are shipping PRs. All of our product managers are shipping PRs. That's not that interesting anymore. I think more interesting is that we have uh internal tools that are similar to clawed code, but they're like more plugged into our infrastructure. So we have a tool called Builderbot. Builderbot is just autonomously merging PRs and actually like building features to 100%. We've had some fairly complex features that are built to 100%. More often than not, it's building them to like 85 or 90%. and then a human who who has a lot of context and understands does like the final the final 10%. So that feels really really different. The ability to go from um to go from idea to like this is in the hands of 100,000 or a million customers has been compressed massively since uh since December. Outside of development, I would say most of what we're seeing is like anytime there's a deterministic workflow, we're we're able to automate that. And so generally at a at scale tech company you have individuals who are working cues. Um a lot of that is just being completely automated away like from a customer support perspective. This is not new but you know our chat bots and and AI phone support and and whatnot are automating a a majority of inquiries that we get. And then it gets into like um product operations and risk operations and compliance operations and any sort of decisioning like generally um generally the the the models and the agents are going to do a better job than humans. Right now I think it's critical that we have a human in the loop. Uh that's like the key kind of buzzword uh when you talk to talk to partners and regulators and and what have you. Um, but over time it's like pretty obvious that these systems are just going to be so much better than like having a thousand humans who are who are doing that work. So that's on the internal side. Um, on the on the product side, I think that

</details>

**Interviewer**: 并且，也许可以向大家介绍一下公司目前的业务构成。显然你们有 Square，有 Cash App，你们还进行了一项大型收购，Afterpay。

<details>
<summary>Original English</summary>

**Interviewer**: >> and maybe just catch people up on kind of the shape of the business. Obviously you have Square, you have Cash App, you you made a big acquisition, Afterpay.

</details>

**Owen Jennings**: 好的。嗯，我们过去是按业务单元运作的。所以 Square 曾经是它自己的业务单元，有自己的 CEO。Cash App 也是它自己的业务单元，有自己的 CEO。嗯，那并没有带来正确的结果。所以大约在 18 个月前，我们对公司进行了功能化。也就是说，所有的工程都向我们的工程主管汇报，所有的设计都向我们的设计主管汇报，所有的产品都向我汇报。所以我们有一个跨越 Block 全部的金融平台团队。我们有一个业务平台团队，正在做许多跨越 Block 全部的自动化工作。然后我们越来越多地构建功能和产品，这些产品实际上连接了 Square 端、Cash App 端和 Afterpay 端。所以自然而然，你在构建技术，你在构建不特定于品牌的基础设施。而这实际上是我们整体战略和整体理念的核心。嗯，是的，我是说，Cash App 在我 2016 年加入 Cash App 时，我们才刚刚开始探索如何变现，并有了我们的第一笔毛利润。现在我认为 Cash App 贡献了公司大约 60% 的整体毛利润。所以过去十年整体增长健康。嗯，但 Cash App 和 Afterpay 的增长确实更快，但我们越来越多地从生态系统的角度思考问题，这也许就是 Goose 这样一个平台出现的原因。我们内部构建了 Goose。看待 Goose 的方式是，它是对 Top Gun 或某个副驾驶的致敬，但看待 Goose 的方式是，它是一个代理能力聚合平台，而且是模型无关的。所以我可以在 Anthropic 模型、OpenAI 模型或开源模型上运行 Goose。我们大概有 120 个模型。根据我想做的事情，我会更换模型。然后这对人类来说很有用，但我们在此之上构建了代理层。所以现在 Block 的许多自动化实际上是通过 Goose agent harness 进行路由的。嗯，我们能够利用这一点来构建产品。所以，Moneybot，我们将其视为你口袋里的 CFO，但它本质上是一个主动的聊天机器人，可以在 Cash App 中代表你采取行动。它是建立在 Goose 之上的。Managerbot，在 Square 端与之类似，也是建立在 Goose 之上的。所以，它是关于代理系统的大量基础工作，以及驱动它们所需的数据和事件，这些工作正在整个公司范围内进行。所以，在产品方面，我认为……

<details>
<summary>Original English</summary>

**Owen Jennings**: >> Sure. So um, so we used to operate in a business unit structure. So Square used to be kind of its own business unit with its own CEO. Cash App was its own business unit with its own CEO. Um that wasn't leading to the right outcome. So about 18 months ago, we functionalized the company. Just meaning that all of engineering rolls up to our head of engineering, all of design to our head of design, all of product to me. So we have a financial platform team that spans the entirety of block. We have a business platform team that's doing a lot of this automation that spans the the entirety of of block. And then increasingly we're building features and products that actually connect the Square side, the Cash App side, and the Afterpay side. And so naturally you you're building technology and you're building infrastructure that is not um brand specific. And that's actually like kind of central to our our overall strategy and and and overall thesis. Um, but yeah, I mean, CA Cash App went from when I joined Cash App in 2016, uh, we had just just started to to figure out how to monetize and had our first dollars of gross profit. And now I think Cash App's probably like I don't know 60ish% of like overall gross profit at the at the company. So overall been been growing at a healthy clip over the past decade. Um but uh Cash App and Afterpay have definitely been growing um more quickly, but increasingly we're trying to think about things from an ecosystem perspective and and that's maybe where like goose as a platform comes in which is we bu we built goose internally. The way to think about goose is um it's a nod to a top gun or whatever the co-pilot thing but the way to think about goose is it's a it's an agent harness and it's model agnostic. So I can run goose on an anthropic model, on a on a on an open AI model, on an open- source model. There's probably like 120 models that we have. And depending on what I'm trying to do, I'll kind of swap out the swap out the models. And then that was useful for a human to use, but we've built like the agentic layer on top. And so now a lot of the automations at at block are actually routing through the goose agent harness. And um we've been able to leverage this across the products that we're building. So, Moneybot, which we'd like to think of as like a CFO in your pocket, but it's essentially like a proactive um a proactive uh chatbot that can take actions on your behalf within Cash App. That's built on top of Goose. Manager bot, which is roughly a similar thing on the Square side, that's built on top of Goose. So, it's a lot of this foundational work on agentic systems and then like the the the triggers and the underlying data and events that you need to power them that's working across the uh the entirety of the of the company. So, on the on the product side, um I think that the the biggest shift has really been like we're going from a world where for the past 10 or 15 years, everyone's used to a static UI, a rigid UI. you tap through the UI, everyone has the same, everyone's Uber or Lyft or Cash App or whatever looks the same. That's going to fundamentally change in the next like six months. Um, generative generative UI is is is here. We're seeing it with Moneybot. We're seeing it with manager bot as the models get better.

</details>

**Interviewer**: 生成式 UI 在实践中会是什么样的？我很好奇。

<details>
<summary>Original English</summary>

**Interviewer**: >> What what is that going to look like kind of in practice? I'm curious.

</details>

**Owen Jennings**: 我觉得，最简单的来说，就像你的 Cash App 应该和我看起来非常不同。原因是，好吧，我把工资发到 Cash App，而你不是。你一直很喜欢 Bitcoin。假设是这样，你不用。你一直都在用 Afterpay。很好。当我们打开我们的应用程序时，那应该完全不同。你可以通过个性化来实现这一点。那没什么意思。实际上我们看到的是，Anthropic 这周发布了一些令人难以置信的内容。我们实际上看到的是，我可以进入 Moneybot 并说，“我的钱是怎么花的？”它会给我展示一些图表和可视化，实际上是即时生成了可视化。它实际上不在代码本身中。所以这非常酷。从 QA 的角度来看，这也可能是一场噩梦。所以我们需要弄清楚如何对数千万客户的这些非确定性输出进行 QA。但在 Square 端的一个很好的例子是 ManagerBot。也许图表对你来说不太有吸引力，但有了 ManagerBot，假设你拥有一个多地点连锁的快餐店。你说，“嘿，你能为我创建一个应用程序，让我可以管理这两个地点的排班，并通过 WhatsApp 或 Signal 或其他方式自动向我的员工发送短信吗？”它实际上会为你创建那个应用程序。那个应用程序的外观和感觉不在我们推送到应用商店的实际应用程序的源代码中。所以我认为，它给了人们更多的控制权。它能带来更好的产品，最终我认为它将带来更高的参与度。嗯，我认为它将带来更好的产品，而且我真的认为关键在于，如果我们让客户自己去提示这些工具，他们不一定知道正确的提示语，也想不出正确的答案。所以，我们在主动智能方面进行了大量投资，我们发现，尤其是在涉及金钱方面，我们需要主动向客户推荐我们认为对他们有意义的事情，而这就是我们创造大量价值的地方。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> I think I mean in simplest terms, it's like your Cash App should look really different from mine. And the reason why it's like, okay, well, I get my paycheck into Cash App and I'm super into Bitcoin. Let's say like you don't and you use Afterpay all the time. Great. When we open up our apps, that should be totally different. That you could probably achieve that just through personalization. That's not that interesting. What we're actually seeing and Anthropic had some releases this week that are that are incredible. We're actually seeing is like I can go into Moneybot and say, "How have I been spending my money?" And it'll show me a bunch of charts and uh and visual visualizations where it is actually like on the fly generating generating that visualization. It's not actually in the code itself. So that's really cool. It's also potentially a nightmare from like a QA perspective. And so we need to figure out how you're going to QA all these like non-deterministic outputs for for tens of millions of customers. But um a great example on the on the Square side is with ManagerBot. Maybe charts aren't that impressive to you, but with Manager Bot, let's say you're a you're a uh you own a multilocation quicks serve restaurant. you say like, "Hey, can you build me an app where I can uh manage scheduling for these two locations and like automatically fire off text via, you know, WhatsApp or or Signal or whatever to my um to my employees. It's actually going to like create that app for you. And the the way that that app looks and feels is not in the source code of the actual application that we push to the to the app store." And so I think it's um it gives folks way more control. It's way more uh ultimately I think it'll lead to higher engagement. Um I think it'll lead to better product and and really I think the key thing I I don't think that if we ask customers to to like prompt these tools themselves, they're going to necessarily know the right prompts and come up with the right answers. So, we've invested massively on the proactive intelligence side where what we've found, especially as it relates to money is like we need to be prompting our customers with things that we think make sense for them and that's where we're creating a lot of the the value.

</details>

**Interviewer**: 所以，我想我们都对 AI 对所有这些企业运行方式以及你能创造的产品所带来的影响非常看好。这对你们的股价如何反馈？我知道你们的股票价格大概已经横盘七八年了。但业务却增长了很多。你如何调和这两个方面？

<details>
<summary>Original English</summary>

**Interviewer**: >> So, I mean, I think we're all incredibly bullish on on kind of the impact of AI, you know, in kind of in the way that all these businesses run and the products you can create. How does that flow back to your stock price? you know the the business is the stock has been roughly flat for I don't know six or seven years.

</details>

**Owen Jennings**: 嗯，我认为，你知道，市场是周期性的，而且有很多事情正在发生。我记得 2021 年，我们的股价大约是 260 美元，我觉得那有点不理性。你可以从一个更长远的、成熟的视角来看待，并说，短期内市场是投票机，但长期来看是称重机。只要专注于构建。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> yeah I think um so so I think you know markets are markets are cyclical and there's all sorts of things that are happening I remember uh in 2021 when our stock price was like I don't know 260 bucks and I was like that was a little bit irrational um you can take a a kind of longer term mature view and say you So markets are voting machines in the near term, but they're weighing machines in the long term. Just like focus on building,

</details>

**Interviewer**: 你知道，David 和 Jonathan 早些时候谈到了“防御性”。你如何看待你们在 Square（抱歉，是 Block）的护城河？你知道，你们谈到了生态系统。显然你们拥有监管基础设施。那么，你如何看待整个业务在那个背景下？

<details>
<summary>Original English</summary>

**Interviewer**: >> you know, David and Jonathan earlier talked a bit about kind of defensibility. How do you think about your own moes at Square? I mean, at Block, excuse me. You, you know, you talked a bit about the ecosystem. You guys obviously have, you know, regulatory infrastructure. Um, you know, how do you think about, you know, that the business overall in that context?

</details>

**Owen Jennings**: 是的，我认为在近期和中期，Block 存在着许多护城河，我们可以更广泛地讨论这个行业。我认为分销和网络效应是其中之一。我同意关于 Catrinite 和 DoorDash 的观点。我认为在接下来的几周内，没有人会“氛围编码”DoorDash。我想说的是，我们中的任何一个人都可以在大约一周内创建一个 P2P 应用。没有人会“氛围编码”拥有 5000 万或 6000 万月活跃用户并实际使用它。所以我认为那是真实的。嗯，我认为，你知道，许可证和监管地位确实存在。我认为硬件，现在很难想象一些 AI 工具如何流向硬件方面。就像你不能“氛围编码”一块 Square 的硬件。嗯，但我认为从长远来看，如果我们继续……如果我们看看变革的速度以及变革中的变革，我认为从长远来看，能够让一家公司具备防御性的关键在于，它在多大程度上理解了其他公司难以理解的东西。所以我们正越来越多地朝着一个世界迈进，并将 Block 视为一个智能系统本身。

<details>
<summary>Original English</summary>

**Owen Jennings**: Yeah, I think in the I think in the near term and the medium term, um there's a bunch of there's a bunch of modes that exist for for block and and we can talk about the industry more broadly. I think I think distribution and network effects are are one of them. I I agree on the the catrini piece and uh and Door Dash. I don't think anyone's vibe coding Door Dash in the next couple of weeks here. Uh I like to say like any of us can can create a peer-to-peer app in probably a week. uh no one's going to vibe code you know 50 or 60 million monthly activives who are actually using that. So I think that that's true. Uh I think um you know licenses and and regulatory posture um definitely exists. I think hardware right now it's like harder to imagine how some of the AI tools flow through to the to the hardware side. Like you can't vibe code a piece of square hardware. Um but I I think longer term if we continue like if we look at the rate of the change and and the change in the change I think longer term the key thing that's going to make uh a company defensible is um the extent to which the company understands something that is pretty hard for other companies to understand. And so we're increasingly building toward a world and talking about block as an intelligent system itself.

</details>

**Owen Jennings**: 所以，基本上，我看到这种情况的未来发展方向是，最终一家公司坐拥某种信号，某种丰富的 [数据](https://www.google.com/search?q=data) 和深刻的洞察。对我们来说，那就是“卖方和买方如何在经济中参与”。嗯，我认为大多数公司都有他们深刻理解的东西。然后问题将是，你能多快地迭代来随着时间推移来改善这种理解。所以我们正在构建内部和外部的世界模型，关于理解我们的客户是谁，然后也理解 Block 如何运作。就像你可以想象，你可以想象对于任何一家公司，就像一个 markdown 文件，记录你是谁，然后你需要一个反馈循环，其中有两个东西。你需要一个反馈循环，其中有信号，那就是，你深刻理解了什么，而其他人却很难理解？然后你需要一个像 Builderbot 或 Cloud Code 这样的工具。然后你就可以一遍又一遍地迭代这个循环。就像，这就是我看到的。这就是正在发生的。很好。这是我们 Block 的 markdown 文件。这是我们的价值观。这是我们试图优化的指标。嗯，这是我们关心的事情。这是我们不关心的。然后你有一个 agentic system（自主系统），所以你可以随时构建东西。而现在，你基本上是把人类过去做的事情。以前构建一个功能需要几个月。现在可能需要一到两周，并且仍然有人参与。很明显，未来你将能够每天运行这个循环数百次，数千次，也许会有人参与。也许不会。也许人类更像是编辑。所以，我认为最大的壁垒将是，哪些公司理解了一些别人难以理解的东西。如果你的答案是，“我不知道”，那么你可能就会被“氛围编码”淘汰。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> So basic like the the the the the way that I see this going if we can if you extrapolate forward the past several months is that ultimately a company is sitting on top of some sort of signal, some sort of like rich data and and and deep insight. Um for us it's like how sellers and buyers participate in the economy. Um and and most companies I think have this thing that they understand deeply. And then the question is going to be how quickly can you iterate to improve that understanding over time. And so we're building world models internally and externally of like understanding who our customers are but then also understanding how block operates. It's like you can imagine you can imagine for any company just like a markdown file of like who you are and then you need the feedback loop with two things. You need a feedback loop with the signal which is like what do you what do you deeply understand that's hard for others to understand and then you need a tool like builderbot or clawed code or what have you. And then you can just iterate through that loop over and over and again. It's like this is this is what I'm seeing. This is what's happening. Great. This is our markdown file for for block. These are our values. this is the metrics we're trying to optimize for. Um, this is what we care about. This is what we don't care about. And then you have a gentic system, so you can just build stuff. And right now, you basically you've taken that humans used to do that and it used to take a couple months to build a feature. Um, now it takes maybe a week or two and there's still humans involved. Pretty clear that in the future you'll be able to run that loop like I don't know hundreds, thousands of times a day and maybe there's some humans involved. Maybe not. Maybe the humans are more like editors. And so I think the the biggest moat is going to be like which companies understand something that's super hard for other people to understand. And if your answer to that is is um I don't know, then uh then you maybe could get vibe coded away.

</details>

**Interviewer**: 这是一次非常精彩的对话。谢谢你。非常感谢你加入我们。

<details>
<summary>Original English</summary>

**Interviewer**: >> This has been an amazing conversation. Thank you. Uh thank you so much for for joining us.

</details>

**Owen Jennings**: 非常感谢。

<details>
<summary>Original English</summary>

**Owen Jennings**: >> Appreciate it. Thanks so much.

</details>

**Interviewer**: 太棒了。

<details>
<summary>Original English</summary>

**Interviewer**: >> Awesome.

</details>