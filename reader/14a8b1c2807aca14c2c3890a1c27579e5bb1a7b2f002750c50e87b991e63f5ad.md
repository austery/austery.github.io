---
author: AI Engineer
date: '2026-10-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=obfPzbapMIM
speaker: AI Engineer
tags:
  - llm-evaluation
  - ai-agent
  - observability
  - error-analysis
title: 使用 Langfuse 进行 AI 应用与智能体评估工作坊
summary: Langfuse 团队在工作坊中介绍了 AI 智能体在生产环境中的评估难题与工程闭环模式，涵盖链路追踪、标注队列与错误分析、数据集构建以及使用大语言模型作为裁判时的评估一致性优化方法。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Langfuse
products_models:
  - Langfuse
  - ClickHouse
media_books: []
status: evergreen
---
<!-- chunk 1/7 -->

### 欢迎与背景介绍

好了，我们开始吧。欢迎大家参加关于使用 Langfuse 评估 AI 应用的工作坊。我叫 Annabelle，是 Langfuse 的一名 AI 解决方案工程师。今天和我一起的还有我的同事 Donelli，他在 Langfuse 负责带领 AI 解决方案架构团队。我们与规模最大的客户合作，确保他们能切实将可靠的 Agent 部署到生产环境。

<details>
<summary>Original English</summary>

All right, let's get started. Welcome everybody to our workshop on evaluating AI applications with Lancuse. My name is Annabelle. I'm a um AI engineer uh AI solutions engineer at Langfuse. And I'm today joined by my um colleague Donelli who is leading AI solution architecture at Langfus. So working with our biggest customers on making sure they actually shipping reliable agents to production.
</details>

我自己在“前世”——我喜欢这么称呼它，因为那段经历感觉像是过去了一辈子——是在一家为医疗器械合规性构建 AI Agent 的公司工作。在那个行业里，确保系统持续运行至关重要。我们要确保拥有经客户验证的真实值（ground truth）数据集，同时也运行了大量人机协同（human-in-the-loop）系统。我当时有大量时间其实都花在 Langfuse 上。后来到了某个节点，我决定换个角色，去帮助其他正在将 Agent 部署到生产环境（尤其是受监管行业）的团队，于是在大约七个月前加入了 Langfuse 团队。

<details>
<summary>Original English</summary>

I myself uh was in my previous life how I like to call it because it feels like a lifetime in a company building AI agents for medical device compliance. And in this industry it was super important to make sure we are running. We're making sure we have ground truth data set that is validated by our customers and we also ran a lot of human in the loop systems and a lot of my time I actually spent in Lenfuse and at some point I decided okay why not swap sites and also help other teams that are shipping agents especially also in regulated industries and uh joined the langu team uh roughly seven months ago.
</details>

### 现场互动与 AI 应用评估难题

所以在我们正式深入之前，想先了解一下今天到场大家的背景，看看我们今天与哪些朋友在一起。想请问大家，你们当中有谁之前将 AI Agent 部署到过生产环境？我指的是亲自作为团队的一员参与其中，而不仅仅是公司里有其他人做过，也就是实际参与了将其推向生产环境的流程。

<details>
<summary>Original English</summary>

So but before we dive right into it we wanted to get a little bit of a feeling of who is here today and who we are um yeah coming together with. So uh we were wondering who of you has brought AI agents to production before and with that I mean been part of a team doing it not necessarily yes someone in the company did it so actually like been part of a process to bring it to production
</details>

好的，太棒了，有很多人举手，这也正是我们所期待的。那么你们当中有谁之前使用过 Langfuse 呢？

<details>
<summary>Original English</summary>

okay that's good amazing it's a lot of people and we hoped uh to have this also and who of you has worked with languages before
</details>

好的，相当一部分人。那有使用过其他任何可观测性或评估工具的吗？

<details>
<summary>Original English</summary>

okay quite some and any other kind of observability in evas tool
</details>

好的，也有一些，非常棒。最后，有谁已经彻底解决了 AI 应用的评估（EVALs）问题？

<details>
<summary>Original English</summary>

Okay. Yeah, also a few uh amazing. And then finally, who has solved EVAs for AI applications?
</details>

对于那些自信举手的朋友，非常欢迎大家待会儿来我们的展台，给我们讲讲你们是怎么做到的。因为这其实相当困难，我想你们所有人如果从事 AI 相关工作，或者只是平时与 ChatGPT 或 Claude 聊天，都体验过这一点。它确实非常棘手，因为 AI Agent 可能会在系统各项指标看起来都正常（全绿）的情况下发生故障。

<details>
<summary>Original English</summary>

For the confident hands, I would love you to come by at our booth and explain us how. Um because actually it is quite hard and I think um all of you have experienced it if you're working with AI or also just chatting with Chat GPT or Claude. H it is quite tough uh because AI agents can fail while the system metrics themselves look green.
</details>

例如看一下这里的这个案例：我们有一个用户支持 Agent，用户提问说“我能申请退款吗？”Agent 接收了请求，查询了一些政策，然后回复说“好的，没问题，我已经为您办理了退款。”用户说“谢谢你。”这需要过几天用户才能知道退款是否真的到账。而此时系统状态是绿色的，按照传统的系统可观测性标准来看，没有发生任何错误，也没有出现延迟问题。但如果我们深入挖掘底层实际发生的情况，就会发现 Agent 根本没有办理任何退款——对应的工具从未被调用，也从未被执行过。Agent 在面对用户时撒了谎，说自己已经办好了。而我们要等到几周后，用户找回来说“嘿，对了，我一直没拿到退款”，才会发现这个问题。

<details>
<summary>Original English</summary>

So if you for example look at this example here we have a user support agent and the user is asking can I get a refund. The agent takes in the request looks up some policies and then it's like yeah sure I issued your refund and the user is like thank you and it will take some days until the user sees if it actually worked out and the status is green. Nothing went wrong in traditional observability terms. There's also no latency issues. But if we dig deeper into what actually happened, the agent never did refund anything. So the tool was never called. It was never executed. And the agent lied about doing it to the user. And we will only know about it in a few weeks when the user come backs and is like, "Hey, by the way, I never get I've never gotten my refund."
</details>

这就是我们面对这些非确定性系统时遇到的难题。它们可能会告诉我们它们做了某些事情，但实际却没有做。这就是为什么你必须找到一种方法和途径，去持续挖掘那些出现问题的信号，并确保这类问题不再发生，或者最好从一开始就完全不发生。

<details>
<summary>Original English</summary>

And this is the problem that we have with those nondetermin deterministic systems. They might tell us they do things, but they actually don't. And this is why you have to find an approach and a way to continuously mine for those signals where things are going wrong and make sure they don't happen again or maybe not even at all in the first place.
</details>

### Langfuse 与 AI 工程闭环

这也是我们创始人在三年前身处 Y Combinator 批次时所面临的问题，当时他们意识到，市场上根本没有针对 AI 应用的单元测试工具，我们需要为此找到解决方案。于是他们打造了 Langfuse，如今它已经发展成为一个用于持续追踪（trace）、监控（monitor）和改进 AI 系统的开源平台。

<details>
<summary>Original English</summary>

And this is a problem our founders also faced three years ago when they were in the way combinator batch and they realized okay there's nothing like a unit test for AI applications and we need a solution for it. So they built Langfuse which is by now an open source platform to continuously trace monitor and improve your AI systems.
</details>

虽然我们起初主要是一款面向开发者的工具，但到现在，领域专家也成为了我们的目标受众——他们与 AI 工程师协同合作，确保系统切实达到预期效果。此外，在过去大概 8 到 12 个月里，还出现了一个新的用户群体，那就是编程 Agent，它们也在协助我们的工程师处理 AI 应用并对其进行改进。

<details>
<summary>Original English</summary>

And while we started out as a dev tool mostly by now we also have domain experts as a target group. So collaborating with AI engineers to make sure the system does what it actually should be doing. Uh but also a new user group for the past probably 8 to 12 months uh which are coding agents that are helping our engineers also to work with AI applications and improve them.
</details>

Langfuse 目前在全球已被超过 15 万名开发者采用，这在很大程度上得益于我们的开源生态。当然，财富 50 强企业中有 21 家在部署 AI 应用时将我们纳入其核心技术栈。每个月有超过 900 亿条观测数据被摄入到 Langfuse 实例中。当然，随着 Agent 执行越来越多的步骤、接管越来越多的任务，这一数据还在呈现增长趋势。像 Ramp、Canva、可汗学院（Khan Academy）和 SAP 这样的公司都在与我们合作。在过去的三年里，我们自然与他们进行了大量的深入交流。在与这些企业合作的过程中，我们认识到一件事：那些成功将可靠 Agent 部署到生产环境并能够持续改进它们的团队，都遵循了某种我们称之为“AI 工程闭环”（AI engineering loop）的模式。它包含了一套实践规范，帮助你通过系统化的方法持续改进系统。

<details>
<summary>Original English</summary>

Lenfus is by now adopted by more than 150,000 uh developers globally also largely driven by our open source um setup. Of course, 21 of the Fortune 50 have us as part of their core tech stack when shipping AI applications. And every month more than 90 billion observations are ingested into uh length use instances. Uh of course increasing tendency as agents are taking more more and more steps and also taking over more and more tasks. Companies like RAMP, Canva, Khan Academy and SUP uh work with us and over the last three years we of course spend a lot of time with them and one thing we realized working with those companies is that the ones that successfully manage to ship reliable agents and also continuously improve them follow something that we call like some form of this and the AI engineering loop and it is about a set of practices that help you to continuously improve your system by taking a systematic approach.
</details>

### AI 工程闭环的核心步骤

这套体系的基础始终是链路追踪（tracing）。追踪的核心是将 Agent 所执行的所有步骤记录成某种日志，但最理想的是以一种人类能够审查的方式进行呈现。监控（monitoring）则是关于从中找出值得关注的样本：哪些地方出错了？哪些地方运行良好？我们应该对哪些环节做进一步深挖？同时也用于了解系统的平均表现如何。构建数据集（building data sets）是指找到一组具有代表性的示例，涵盖你希望应用程序能够处理的场景以及你期望它处理的方式。接着你需要在数据集上运行实验，尝试系统的不同变体，以检验它的表现和运行状况。随后，你自然需要对它的表现进行评估。而这并不是一次性的工作，你需要不断闭环这一流程，持续改进这些 AI Agent，从生产环境中汲取经验并将其沉淀回数据集中。下面让我们把这些步骤逐一展开做更详细的探讨。

<details>
<summary>Original English</summary>

The foundation to this is always tracing. Tracing is about getting all the steps of what your agent is doing into a more or less lock, but ideally also in a way you can inspect it as a human. Monitoring is about finding the interesting ones. So what is going wrong? What is going right? Where should we look deeper into? But also understanding how is it performing on average. Building data sets is about finding a representative set of examples that you want your application to be able to handle and also how you want it to handle it and then you want to run experiments on it. So try different variations of your system to check um how it is performing, how it's going and then of course you want to evaluate how it's going and this is not something you do once but you continuously close this loop and want to improve uh those AI agents and learn from production and get get it back into data sets. Uh but let's dive in each of those steps a little bit more into detail.
</details>

首先对于追踪（traces），最重要的目标是让你能够深入洞察 Agent 实际上在做什么。在屏幕右侧，我们可以看到一条追踪记录，这也是一张来自 Langfuse 的界面截图。在这个案例中，它是一个 IT 支持 Agent——也就是那种帮你回答父母提出的技术问题、让你不用亲自去应答的 Agent。我们可以看到，首先有一个根追踪节点，我们可以看到这个步骤聚合的时间以及成本。同时，我们还能看到该 Agent 执行的每个单独步骤的细分拆解：既包括属于 OpenAI 调用的生成步骤，也包括前面带有小工具图标的工具调用步骤。这样我们就对正在发生的情况拥有了详尽的视图；如果屏幕再宽一些，我们还能看到输入、输出以及涉及的所有元数据。这便成为了跟踪成本、延迟、所消耗 Token 数量的基础，同时它提供了一份可供人类审查的日志，让你真正深入弄清楚系统内部发生了什么，也便于编程 Agent 大规模处理和分析它，拥有这样一份可审查的日志来确切记录系统到底在做什么。

<details>
<summary>Original English</summary>

So for traces, the most important goal is that you want to get deep insights into what your agent is actually doing. On the right side of the screen, we can see a trace that is also a screenshot from Lenfuse and in this case it's an IT support agent. So an agent that is answering questions from your parents so you don't have to do it. And we can see that there's first like the root trace and we can see aggregate um time and also uh costs of this step. But we then also get a breakdown of each of the individual steps that agent is taking. So both the generations which are the open AAI chat ones and also the tool calls which we can see with a little tool in front of it. So we have a detailed view of what's going on and if the screen would be wider we would also see that we can see the inputs and outputs and all the metadata involved. This is then the foundation to track the cost, the latency, the tokens involved, and also have a log to inspect for you as a human to really dig into what's going on, but also for your coding agents to work with it and look at it at scale and just have this this inspectable lock of what's actually been going on.
</details>

而监控则是为了在大规模场景下理清这些数据。因为特别是现在，随着自动化水平的不断提升、追踪链条变得更长、应用场景非常丰富，作为人类完全手动去翻阅这些日志已经不再现实了。你实际上需要一种方法来获取有关运行现状的聚合指标，并且能够探测到出现问题的信号。比如成本和延迟指标，但或许也可以是质量方面的信号，例如我们的合规护栏机制是否得到了切实遵守，或者有多少用户实际上对我们的系统感到沮丧——有多少用户因为可能对 Agent 刚才的操作有些不满而发送全大写字母的消息等等。把所有这些信息聚合起来，然后当然还要从中发现值得深挖的有趣内容。

<details>
<summary>Original English</summary>

Monitoring is then about making sense of it at scale because especially now with increasing uh automation levels, longer traces and like a lot a lot of use cases. It's just not feasible anymore for you as a human to look through those logs completely manually. But you actually want a way to get aggregate metrics on what's actually going on and also uh detect signals where things are going wrong. So for example, cost and latency metrics, but maybe also quality signals like our compliance guardrails um kept true to or also like how many users are actually frustrated with our system. How many are writing all caps messages because they are maybe a bit upset with what uh the agent just did and um yeah all of this aggregating and then u of course also finding the interesting stuff that you want to dig deeper into.
</details>

通过这种监控从生产环境中获得的数据，接下来也是你可以用来构建数据集的基础之一。归根结底，数据集所体现的就是你期望 Agent 在生产环境中处理的内容：包括它可能收到的所有情况，也可能包括超出处理范围的请求（你希望系统能够正确地将其转交推迟处理，确保 Agent 不会尝试给出投资建议，或者回答纽约的天气怎么样……）

<details>
<summary>Original English</summary>

what you get from production through this monitoring is then also one of the foundations um that you can use to build out your data sets and data sets are in the end a representation of what you want your agent to handle in production. So all the cases that it might be getting also maybe out of scope requests that you want to like correctly also be deferred and make sure that like the agent is not trying to give investment advice or also uh answering what the weather in New York is
</details>

<!-- chunk 2/7 -->

### 构建数据集、实验与评估体系

会是什么样，如果它实际上只是一个已经死掉的 IT 支持智能体。这些条目接着可以包含输入，以及你预期它生成的输出——这既可以是一段示例回复，也可以是你希望看到的预期行为，或者你希望覆盖的关键词。然后，这可以用作一个稳定的基准，既可用于离线改进和迭代，也可以作为 CI/CD 的一部分。

<details><summary>Original English</summary>
going to be like if it's actually just a dead IT support agent. And those um items you can then have like the input but also what you expect um it to have as the output which can both be like a sample reply or also expected behavior that you want to see or keywords you want to have covered. And this can then be used as a stable benchmark either for like improving and iterating offline or also as part of your CI/CD.
</details>

这些数据集随后用于运行实验。实验——如果你回顾一下大学里的统计学或者你可能学过的任何东西——归根结底就是这样一种理念：改变你的设置中的某些东西，然后观察接下来会发生什么。例如，更改提示词、更换模型、修改上下文或工具描述，看看它是否能更好地处理你实际想要处理的问题，并且理想情况下要隔离关注点。所以，如果你想检查同一个模型在不同提示词下是否表现更好，理想情况下你只更改提示词，而不是同时更改另外五件事，因为否则你将很难解释自己实际看到的结果。

<details><summary>Original English</summary>
Those data sets are then used to run experiments on and experiments are um if you maybe look back into university and statistics or anything that you might have done. It's in the end this idea of varying something about your setup and looking what happens then. So for example, changing a prompt, changing a model, changing the context or the tool description and to see if it's then better dealing what you actually what you with what you actually wanted to deal with and ideally isolating concerns. So if you want to check if the same model performs better with a different prompt, you ideally only change the prompt and not five other things because otherwise it's going to be hard for you to interpret what you actually see.
</details>

最后，你需要 evals（评估）或评估方法，以确保你也能衡量在这些实验中发生的情况，因为同样地，你不想什么事情都亲自查看——顺便说一下，你有时可能确实应该看一看。但你依然需要可扩展的方法，比如“LLM 作为裁判”（LLM as a judge），也就是用另一个 LLM 来检查该 LLM 做了什么；或者基于代码的评估，用于像分类任务这样的事情，在这些任务中你可以检查完全匹配；或者检查行为也可以是一种确定性检查，又或者你是在检查全部大写之类的情况。

<details><summary>Original English</summary>
And then finally, you need evals or evaluation approaches to make sure you can also measure what's happening in those experiments because again you don't want to look at everything yourself. Uh which you by the way should should probably sometimes do. Um but still you also want the scalable approaches which are for example LLM as a judge. So using another LLM to check what the LLM did. um or also code based evals for things like um classification tasks where you can check for an exact match or um also checking behavior can be a a deterministic check or if you are checking for all caps type um things.
</details>

这就是 AI 工程闭环。我们在许多客户身上观察到的是，根据你的具体用例，进入这个闭环的切入点会有几种不同。例如，如果你处于一个低风险环境中，仅仅是在构建内部聊天智能体，你起初可能根本没有配置可观测性工具；然后你可能从链路追踪（tracing）开始上手，并添加一些监控来仅仅检查大家在哪些地方感到沮丧，但你一开始并不太关心评估部分。你只是随着时间的推移逐步构建，随着进展把那些测试用例添加进去，但你可以直接上线到生产环境。然而，如果你构建的是面向客户的案例，特别是如果你构建的是处于受监管环境中的案例，你可能就不想冒风险让智能体做出实际上不应该做的事情。

<details><summary>Original English</summary>
So this is the AI engineering loop and what we observe with um many of our customers is that there's depending on your usecase a few different entry points into this. So if you're for example in a low stakes environment and you're only building your internal chat agent, you might first not have a observability tool in place at all and then you maybe get started with tracing and add some monitors to just check where are people getting frustrated but you don't care about the eval part too much in the first place. You just build it out over time and just like add those test cases as you progress but you can go to production directly. However, if you're building a case that is customerf facing and especially if you're building a case that is in regulated environments,
</details>

### 受监管行业的落地路径

你可能不想冒风险让智能体做出它实际上不应该做的事。因此，对于那些受监管行业，我们看到涌现出了一些方法，而其基石始终是链路追踪。所以你总是想要了解实际发生了什么、它在采取什么步骤、它看到什么输入和输出，以及正在调用什么工具。在此之上，受监管行业中的那些团队找到了一些构建这些真实真值（ground truth）数据集的方法，然后你也可以在此基础上进行循环、改进；而且你们可能也都听说过自动改进。所有这些绝对都需要以真实真值数据集为基石，而达到这一目标确实有几种方法。例如专家策展，即与公司内部的领域专家合作，以确保你在构建出真值数据集。然后比如影子运行（shadow runs）：你持续手动运行该流程，但与此同时智能体也在并行运行，你可以随时对比智能体本来会如何处理、智能体会如何着手解决，并以此衡量准确性，同时也构建出你的真实真值。最后，就像我们在我之前的公司所做的那样，运行一个完全人机协同（human-in-the-loop）的系统，随着时间的推移，把数据切分成两部分：一部分是你确信可以自动化的，另一部分则是你始终希望有人工参与的。

<details><summary>Original English</summary>
you probably don't want to risk the agent doing something that it's actually not supposed to do. So for those regulated industries, we've seen a few approaches emerging and the foundation is always tracing. So you always want to know what is actually happening, what steps is it taking, what inputs and outputs is it seeing and also what tools are being called. And then on top of this um those teams in regulated industries found a few approaches on how to go about building out these ground truth data sets that you can then also loop on improve on and also you probably all heard about auto improvement. Um all of this definitely needs the foundation of a ground truth data set and you yeah have a few approaches to get there. For example expert curation so working with your domain experts within the company to make sure you're building out the crown to data set. Then for example shadow runs. So you run the process continuously manually but in parallel you also have the agent running and you can always compare how would the agent have handled it? How would the agent have gone about it and then like this measure the accuracy but also build out your ground truth and then finally um like we did it also in my previous company. Run a fully human in the loop system and over time slice the data into parts where you are confident to automate versus things where you always want a human in the loop.
</details>

关于介绍就讲这么多。我们现在想进入一个更实际的示例。为此，我也再次欢迎 Donelli 上台，我们将一起探讨如何将智能体的执行过程追踪到 Langfuse 中，如何评估和改进你的系统，以及如何持续闭合这个闭环。

<details><summary>Original English</summary>
So, so much on the introduction. Uh, we now want to go in a more practical example. And for this, I'm also welcoming Donelli again on stage and we're going to look together into how to trace your agent execution into length use, how to evaluate and improve your system, and how to continuously close this loop.
</details>

### 金融级智能体的防护与演示

>> 大家好。正如 Annabelle 所说，我是 Don，但大家叫我 Don 就可以，这样对大家都更简单。只有在我惹麻烦的时候，我妈妈才会叫我 Don。嗯，是的，好的，太棒了，听到几声轻笑。所以，你们懂的，挺不错的破冰。这就是第一次 eval，进行得很完美。那么，我现在要向大家展示的是我们为正在合作的几家金融机构构建的示例，因为他们正处于这样一种过程中：他们构建了自己的第一个原型，构建了自己的第一个演示，但随后领导层或者团队可能会提出问题：我们该如何评估我们正在构建的这些面向客户的智能体解决方案？现场有多少人从事金融服务或金融行业？是的，我们在纽约，所以理所当然大家都是。除金融服务之外的其他行业呢，像医疗健康之类的受监管行业？好的，太酷了。真棒。所以我认为这将会引起大家极大的共鸣。

<details><summary>Original English</summary>
>> Hi everybody. Like Annabelle said, I'm Don, but you can call me Don to keep it easier for everybody. Only my mom calls me Don when I'm in trouble. Um, yeah, that okay, that's great. heard a few giggles. So, you know, nice nice icebreaker. So, that's the first eval. It went perfectly. Um, so now what I'm going to show you is an example that we built for a few financials institutions that we're working with because they're in the in in kind of this process of they build their first prototype, they build their first demo, but then the question comes from leadership or maybe from the teams. How do we we evaluate this customerf facing agentic solutions that we're building? How many of you here are in financial services or in finance? Yeah, we're in New York. So, of course, you all are. Um, any other industries others than financial services, regulated industries like healthcare and stuff like that? Okay, cool. Awesome. So, I think this is going to this going to speak to you very much.
</details>

大体上我这里展示的，就是一个典型的银行助手。我们当中任何享受银行服务的人，可能都在各自的银行里见过这个，对吧？然而，背后发生的所有事情，对于银行本身或机构向你提供极其准确的信息而言都非常重要，因为这涉及到财务责任、法律责任。当这类解决方案由大语言模型（LLM）驱动时，银行本身要承担大量风险；而众所周知，LLM 本质上是不确定性的。因此，我们希望确保降低不可预测性，并且能够尽可能复现结果，找出故障模式在哪里、智能体在何处给出了我们不想要的结果，以便我们能够据此进行改进。

<details><summary>Original English</summary>
Um, so basically what I have here is, you know, a typical, you know, banking assistant. Everybody, anybody of us that has a banking services probably have seen this in each of of your banks, right? However, the all the stuff that happens behind is you know very important for the bank itself or for the institution to provide you with very accurate information because there is like financial liability, there's legal liability. There's a bunch of you know risk for the bank itself to put out these type of solutions when they are powered by LLMs which as we all know are inherently non-deterministic. So we want to make sure that we reduce the unpredictability and that we can then reproduce the outcomes as much as we can and figure out where are the failure modes and where is the agent giving us the results that we don't want so that then we can you know improve upon those.
</details>

在这个示例中，我有几件事想向大家展示。第一件事是，我可以模拟几种不同类型的客户，因为显而易见，银行总是会有像日常普通人一样的客户，比如我自己，在银行里只有几块钱；但随后你也会有超高净值人群等等。因此，我们可以在这里进行不同种类的身份模拟。这一点很重要，因为我们希望能够知道，在面对我们拥有的这类画像时，智能体是否能够遵守我们设置的任何护栏（guardrails）。另一件事是，如果你注意到这里——也许让我把它放大一点——我们还启用了 PII（个人身份信息）识别，任何被视为 PII 的数据在持久化到 Langfuse 之前都会被自动脱敏。

<details><summary>Original English</summary>
In this example I have a few things that I I would like to show you. The first thing is that I can impersonate, you know, a few different type of clients because obviously a bank is always going to have customers that are like, you know, your everyday Joe like myself. I only have a couple of bucks in the bank, but then you're going to have your ultra high net worth individuals and all of that. So, we can have here impersonation of different kinds. And this is important because we want to be able to know if the agent is able to respect any guard rails that we have put in place when it comes to those type of uh personas that we have. The other thing is if you notice here maybe let me blow it up. We also have PII identification uh enabled and any sort of uh data that is deem as PII is automatically masked before it gets persisted into Langfuse.
</details>

同样，这是专门针对金融机构的另一项非常重大的要求，他们不想在可观测性系统中持久化其客户的信用卡信息或社会安全号码。他们希望把这些保留在记录系统（systems of record）中，并尽可能保留在他们自己拥有的系统中。因此，该功能也已启用，我将向大家展示几个示例，说明我们如何实现这一点。然后，我们还将观察智能体本身是否遵守了我们设置的一些控制措施、它是如何被评分的，以及我们定义的质量门禁（quality gates）是否也得到了执行。所以我们将对所有这些进行衡量。我将向大家展示几个示例，然后带大家看看产品本身的幕后情况，展示如何进行设置，以及端到端流程看起来是什么样的。假设我在这里以 Anna 的身份进入，我询问关于国际汇款手续费的问题。非常简单的问题，仅涉及知识库。几秒钟后，它就会返回并给出我们知识库中的结果。看，就在这里。你们看到这里，我呈现出来的信息显然是不会展示给客户的，但我在这里是为了演示目的而将其呈现出来。

<details><summary>Original English</summary>
Again, this is another very big requirement for spec specifically financials institutions that they don't want to, you know, persist in an observability system their credit card information or social security numbers or their clients. They want to keep that on the systems of record and as much as possible in their systems uh that they own. So, that is also enabled and I'll show you a couple examples on how we can uh get that to work. And then we're also going to see if the agent itself is respecting some of the controls that we have put in place and how is being scored and if the quality gates that we have defined are also being enforced. So we're going to me measure all of that. I'm going to show you a few examples and then take you behind the scenes in the product itself to show you how you can set that up and then how an end toend flow looks like. So let's say that I am, you know, in this case I'm coming in as Anna. I'm asking about international wire fees. Very simple question, just a knowledge base. And then in a few seconds, it's going to come back and give me the results from our knowledge base. And here you go. You see in here, I'm surfacing information that obviously I wouldn't surface to a to a customer, but I'm doing it here for the purposes of the demo.
</details>

<!-- chunk 3/7 -->

但我在这里指出正在调用的工具、正在调用的数据源，以及构成该 Agent 在返回此答案时的配置的一些细节。如果我接着说：“好，你看，我信用卡丢了。这是我的卡号。它被锁了吗？”我把我的信用卡号以明文形式输入进去了，对吧？所以那显然很糟糕。因此你要确保，即使用户——你无法控制这一点，你无法控制用户在系统中输入什么——你要确保在进行插桩和构建评估时能捕获到这一点。

<details><summary>Original English</summary>
But I'm calling out here the tools that are being called, the the data sources that are being called as well and some of the details as well that make up the configuration of this agent when it comes to giving back this answer. If I were to then say, okay, look, I I lost my card. This is my number. Is it blocked? I'm putting my credit card number in clear text, right? So that is obviously that's not not great. So you want to make sure that even though that the user you cannot control that you cannot control what your uses your users input in the system you want to make sure that you catch that whenever you are instrumenting and whenever you are uh building your evals
</details>

现在我们会在 trace 本身中看到，信用卡号确实会被遮蔽。如果我来到 Langfuse 打开我的 trace，你会看到现在的提问是“my car number is”，然后它进入系统后完全被遮蔽了。那是因为我有一个脱敏函数，能自动将我定义的任何个人身份信息（PII）立即遮蔽，这样它就不会以纯文本形式持久化保存在我的系统中。

<details><summary>Original English</summary>
so now we'll see in the trace itself that the credit card will be indeed redacted if I come here to langfuse and I open my trace you'll see that now the question is my car number is and then it landed in LA completely redacted That is because I have a masking function that automatically any sort of PI information that I have defined will be immediately masked and then is not persisted in plain text in my system.
</details>

所以只是给你们展示一下典型交互是什么样子的。我可以从最上面这里看到，这是用户发送的 prompt；但正如大家所知，后台还有很多事情在发生，我们不一定会把这些展示给最终用户，但对于我们这些平台团队和开发者来说，了解 Agent 的行为表现以及输出质量是至关重要的。我可以看到它所采取的所有步骤的完整树状结构。比如在这里，它调用的 Anthropic LLM，可用的工具。这里它调用了一系列工具，列出了账户等等，这些是输出结果。

<details><summary>Original English</summary>
So just to show you uh in terms of what a a typical interaction looks like and I can see from the top here this was the the prompt that the user sent but then as you all know behind the scenes there's a lot of stuff going on that we don't necessarily surface to our end users but are critical for us as the platform teams as the developers to understand how the agent is is behaving performing and the quality of the outputs as well. I can see the entire tree of all the steps that he took. You know, here the the the anthropic LLM call that he made, the tools that are available. Here it called a list of tools. It listed the accounts and and so forth. And these are the outputs.
</details>

但更重要的是，在上方这里，我可以看到我为这个特定用例定义的所有评分。你可以看到，每当有新的交互或系统捕获到新的 trace 时，它们都会自动计算。我可以捕获各种情况，比如我给客户的信息是否符合银行业务规范——意思是如果客户问天气，我就不会提供那类信息，因为那不合规；是否存在任何失败模式；是否存在任何正在拦截返回给客户的答案的 guardrail。

<details><summary>Original English</summary>
But then more importantly here on the top, I can see all the scores that I have defined for this particular use case. You see that they're they're automatically calculated whenever there's a a new interaction or a new trace being captured by the system and I can I can capture things if you know down from if the information that I gave to the customer is compliant with banking information meaning that the customer is asking about the weather I'm not going to give that information it's not compliant um if there's any sort of failure modes um if there's any guard rails that we're that we're blocking any any answers that we're giving back to the customer.
</details>

举个例子，有人可能会来问：“我能把储蓄投到比特币里吗？”对吧？这是银行本身不应该提供相关信息的事情，因为那会带来一些影响。Agent 正确地处理了这一点，但同时它也将其标记为投资建议，这需要由个人去咨询顾问或其他途径，而我们正是在使用一个评分来实现这一点。如果我再次查看我的 trace，就会看到它是这样的：我这里有输入 guardrail，提示我主要风险是投资建议；而在评分这里，我可以看到该评分中客户的意图确实是投资建议。这样我就可以非常轻松地针对这些情况进行筛选。

<details><summary>Original English</summary>
One example of that is for instance I can come someone can might come and ask can I put my savings in bitcoin right so that is something that the bank itself shouldn't be providing information about that because that is you know that has some ramifications and the agent you know correctly does that but at the same time it is flagging it as investment advice and this requires you know for the person to either talk to an advisor or or something else and we are using a score to do that. And if I go again to my trace, this is how I see it. I have the input guard rail here that tells me that this is the primary risk is investment advice. And in the score here, I can see that the intent of the customer on this score was indeed investment advice. So that way I can very easily go out and filter for those in particular.
</details>

不过总之，我想向大家展示这么一个简单的流程。在进入端到端讲解如何构建数据集以及如何构建评估流程之前的最后一个点，是我们还能支持多模态。假设客户不是通过聊天机器人输入文字，而是致电你们的联络中心。我们可以来到这里，选择“我要处理这通通话”，它会进行语音转文字，然后对文本进行评估，查明这里是否存在任何违规行为。我接着可以来到这里，上面显示客户在询问关于锁卡的事宜，我确实可以在这里看到 trace，甚至能看到客户发送的媒体的实际链接，即客户打来的音频或通话录音，还有转录文本以及助手的回复内容。所以就 tracing 而言，这就是我如何捕获所有这些活动的方式。

<details><summary>Original English</summary>
But anyways, I wanted to show you kind of a simple flow of this. The last one before getting into the end to end on how you build a data set and how you build an evaluation flow is that the fact that we can also support multimodal. So let's say that instead of you having the customers writing via chatbot they're calling your contact center. We can come here. We can say I want to process this call and this going to do a speech to text and then the text is going to be evaluated to to figure out if there's any violation on on here and I can come then in here it says that the customer was asking about blocking his card and I can indeed see the trace here and I can even see the actual link to the media that the customer was sent or in terms of that audio uh or that call that the customer made and also the transcript and what the assistant gave back. So that is in terms of the tracing how can I capture all of those activities.
</details>

### 构建评估数据集

现在，当我开始思考：好吧，我该如何搭建或落实一套框架，来评估客户将通过我的系统发送的这些交互？因为众所周知，客户是不可预测的。我们在设计系统或解决方案时可能会有一个特定的意图，但我们的客户总能找到非常巧妙的方式以不同方式去使用系统。而且，尤其是在面对大语言模型驱动的解决方案时，当将其发布到实际环境中供客户使用时，我们根本无法预见可能发生的每一个结果。

<details><summary>Original English</summary>
Now when I am trying to then think about okay how do I then put together or put in place a framework on how to evaluate this interactions that my customers are going to be sending through my system because as we all know customers are unpredictable. We might design a system or a solution with a a specific intention, but our customers are always going to find very clever ways to use a system in a different way. And we also cannot anticipate every single outcome specifically with LLM power solutions that are going to happen when we we release this into the wild for customers to use.
</details>

因此，这就是我们开始依赖构建评估标准的时候，对我们而言，这其中的基石就是构建数据集。那么什么是数据集？数据集基本上——我们来看这个通用的——数据集基本上就是你的问题集和预期输出集，让你能够据此衡量你的 LLM 或 AI 解决方案的输出质量。如果你有软件开发背景，我喜欢将它们理解为：这些就是你的测试用例。

<details><summary>Original English</summary>
So that is when we start relying on building our evaluation criteria and for for us the anchor of that is building data sets. So what is a data set? A data set is basically and let's go to this one that is the the generic one. A data set is basically your set of questions and expected outputs that allow you to then measure the quality of the outputs of your LLM or AI solution. If you come from a software development background, the way that I like to think about this is that these are your test cases.
</details>

我认为这里在座发布过生产软件的人，都不会在没有通过 QA 的情况下就将任何东西发布上线，除非你直接 merge 到 main 或 prod——我敢肯定你们大多数人都干过这事，但这并不是最佳实践。我知道我干过，不过无所谓了。但与此同时，这也是一种能让你拥有证据的方式，证明你的 Agent 已经通过了一系列衡量你想要捕获的所有指标的步骤或要求。

<details><summary>Original English</summary>
And I don't think anybody here that has shipped software into production will ship anything without passing into QA unless you merge into main or prod, which I'm pretty sure most of you have done it, but it's not a best practice. Um, I know I know I have, but whatever. Um, but at the same time, this is the way that you can then have the evidence that you pass the agent through a series of steps or requirements that measure all the things that you want to capture.
</details>

这里需要注意的一点是，预期输出并不一定必须是 Agent 将要给出的答案。也可能是你想要衡量 Agent 的意图，你想要衡量 Agent 应该做什么；如果你想衡量行为，有不同的方式来衡量输出质量。这就是为什么你通常会有多套不同的数据集，来衡量你的 Agent 队列中的特定事项或特定的质量维度。

<details><summary>Original English</summary>
And one thing to note here that the expected output doesn't necessarily need to be the answer that the the agent is going to give. It could also you want to measure maybe the intent of the agent. You want to measure what the agent is supposed to do. If you want to measure behavior, there are different ways that you can measure the quality of the output. And that is why you typically end up with different sets of data sets to measure a specific things or or specific areas of quality in your agent fleet.
</details>

你们在这里看到我有一套数据集基本上是对我的 Agent 进行红队测试，寻找 prompt 注入攻击以及任何允许他人绕过我们设置的 guardrail 进而获取不应获得的信息的攻击。我这里的另一套则非常专门针对某个用例：我想知道哪些案例处于争议状态，以及争议未得到解决的地方。所以这里的核心在于，我可以来精心组织特定的数据集，这些数据集不仅非常贴合具体的用例，而且也非常贴合我对该 Agent 提出的技术要求。

<details><summary>Original English</summary>
You see here how I have one that is like basically red teaming my agent and looking for prompt injection attacks and any sort of uh attack that will allow someone to come in and circumvent the guardrails that we have put in place to then provide information that they shouldn't get. The other one I have here is like very specifically for a use case that I want to know which uh which cases have been disputed and where the dis the that dispute has not been solved. So the point here is that I can come and and curate a specific data sets that are very specific to not only the use case but also the technical requirements that I have for that agent.
</details>

在这方面我想说，并非不幸，因为我仍然认为我们人类非常重要——所以在这个环节你仍然需要领域专家参与其中（human-in-the-loop），与开发团队协同定义这些内容。创建黄金数据集主要有两种方式，而这两种形式我都见过。一种是你的团队已经在某个地方准备好了电子表格，记录了“这些都是我们想在 Agent 上测试的所有内容”，直接上传就可以了，这非常容易。你可以来到这里说：好的，完美，我想创建一个测试数据集，然后我想上传一个 CSV；你可以上传这个 CSV，它就会完全还原你之前所拥有的全部内容。

<details><summary>Original English</summary>
This is where I would say that not unfortunately because I think I still think humans we are very important. So this is where you still need your domain experts in the loop working with the development teams defining what are these. There are two main ways that you can basically create your golden data sets. You either have a team and I've seen variations of both. You either have a team that already has a spreadsheet somewhere. these are all the things that we want to test on my agent and just upload it and that's pretty easy. You can come here and say okay perfect I want to create a test data set and then I want to upload a CSV and you can upload the CSV and it will exactly bring up everything that you just had before.
</details>

我还想在这里提一下，我展示的所有操作，你完全可以通过我们的 CLI，或者我们 API 中的 MCP 以完全相同的方式进行。只是我认为在 UI 中展示比让 Claude 从头到尾操作要更直观一些，毫无疑问。好，那么关于这点就讲到这里。不过我也可以来到这里说，我想将例如已经属于我生产 trace 一部分的条目添加到我的数据集中。那么假设大家看到了我之前是如何收集大量

<details><summary>Original English</summary>
The other thing I like to mention here everything that I'm showing you can do it as well identically through our CLI or NCP in our APIs. It's just that I think it's very it's better for me to show it in a UI rather than telling claude to do it end to end. Make no mistakes. Okay. Um so that is that on that but then I could also come here and say that I want to add um you know items into my data set for instance that are already as part of my production traces. So let's say that you saw how I was already collecting a lot of
</details>

<!-- chunk 4/7 -->

来自我的应用程序的活动。我可以来到这里，说我想把所有这些都添加到我的数据集中，然后选择我想要选择的数据集。这样一来，你就可以通过查看你的智能体正在产生的生产追踪记录，在某种程度上对你要使用的数据集进行“自产自用”（dogfooding），只要你已经确定，是的，这些都是我希望未来输出或追踪记录呈现的良好示例。

<details><summary>Original English</summary>activity from my application. I can come here and say I want to add all of these into my data set and then select the data set that I want to select. So this way you can kind kind of dog food in a way the data set that you're going to use by looking at the production traces that your agent is producing as long as you have determined that yes these are good examples of what I want future outputs or traces to look like.</details>

### 错误分析与标注队列

现在，这里要做的一件重要事情是我一直喜欢提倡的一个过程，那就是错误分析。对吧？所以错误分析基本上就是这样一个概念：我想查看我的追踪记录。我认为 Annabelle 之前作为 Langfuse 的用户时，也非常透彻地谈到了这一点，她当时必须——我们今天早些时候也聊过。她花了几天时间，简直字面上就是盯着追踪记录看，那就是她的工作，比如查看追踪记录的结构，输出是什么等等所有这些内容。这仍然是一个非常重要的过程，因为当你查看追踪记录时，你首先开始理解智能体是如何运作的：它是否采取了你需要它采取的所有步骤，它是否调用了所有它需要调用的工具，以及它是否给出了你想要的输出。那是非常、非常重要的。

<details><summary>Original English</summary>Now an important thing here to do is a process that I always like to call out which is error analysis. Right? So error analysis is basically this idea that I want to look at my traces and I think Annabelle kind of talked about this uh very eloquently as well when she was on the other side as a user of of Langfuse that she had to like and we were talking earlier today. She spent like days like literally looking at traces like that was her job like looking at the trace the structure what was what were the outputs and all of that. And that is still a very important process because when you look at the trace you you first start understanding how the agent is behaving if it's taking all the steps that you needed to take if it's calling all the tools that it needs to call and if it's giving you the output that you want. That's you know very very important.</details>

但接下来你该如何简化这个过程呢？因为显而易见，一旦系统投入生产，我作为一个人去逐一查看成千上万条追踪记录是不可行的。所以我们通常的做法是，我们希望精选出一批能代表我们生产系统的追踪记录样本，供人类专家前来查看并给我反馈。对吧？这就像是：嘿，我有这么多活动，我只抽取 10% 或 20%，而且我可以指定我只想关注客户正在谈论纠纷或信用卡信息等等的内容，无论你想要什么过滤器，你都可以做到。

<details><summary>Original English</summary>But then how do you simplify that process? because obviously it is not feasible for me as a human to go out and look at thousands of traces once the system is in production. So what we typically do is we want to curate a sample that is representative of our production system on of traces for a human expert to come look and give me feedback. Right? It's the same as like hey I have all this activity. I'm just going to take 10% or 20% and I can say I just want to focus on the ones that the customer is talking about, you know, disputes or credit card information, whatever filter that you want, you can do that.</details>

然后你可以为他们构建我们所说的标注队列，对吧？在这个标注队列中，你实际上在做的事情是告诉领域专家——在这个例子中比如说是我——嘿，你是风险专家，我需要你看看智能体提供给我们或提供给我们客户的这个输出，并给出你的意见。这里的关键在于，你希望让领域专家操作起来非常、非常简单，因为显然他们有自己的本职工作，他们不可能花上好几个小时单单来看这个。

<details><summary>Original English</summary>And then you can build for them what we call an annotation queue, right? In this annotation queue, effectively what you're doing, you're telling a domain expert, in this case, let's say me, that, hey, you are the risk expert. I need you to take a look at this output that the agent is giving us or is giving our clients and give me your input. And the thing is here you want to make it very very simple for the domain expert because obviously they have their day job. They cannot spend just hours looking at this.</details>

所以我通常建议的事情是，你可以给他们几个评分选项让他们打分，你知道的，是、否、对、错、1 到 10 的等级，不论是什么标准。然后他们也可以来到这里给出一条评语。比方说这里的失效模式，为了讨论起见，我们假定在这个例子中是缺失了引用。然后我要——我要写上一条评语：“没有引用。在所有这些案例中都需要包含进去”，对吧？你将完成这个过程，看看对我来说它是多么简单。大概花了我什么，可能 10 秒钟吧。

<details><summary>Original English</summary>So the the typical things that I recommend is you can give them like a couple scores that they can give you, you know, yes, no, true, false, a scale 1 to 10, whatever that is. And then they can also come here and give you a comment. So let's say here failure mode, let's just say for for for the sake of argument that in this case is missing a citation. And then I'm going to I'm going to put a comment. Citation is not there. Needs to be included in all these cases, right? You're going to go through this process and and look how you know it was simple for me. It took me what 10 seconds maybe.</details>

假设我有一百个这样的案例，每个花费我 30 秒。那是多长时间，50 分钟？不，不，根本不到。好吧，我今天数学算得不行。但不管怎样，你们明白这个意思，对吧？所以你——你可以对你的领域专家说：嘿，分给我你的一小时时间，我会为你精选一批活动，只要给我你的反馈，只要给我几句评语就行。现在有了 Whisper Flow 或类似工具，他们甚至可以直接口述，都不需要打字了。对吧？所以让它变得非常简单。

<details><summary>Original English</summary>So let's say I have I don't know a hundred of these and it takes me 30 seconds each. That is what 50 minutes. No, no, not even. Right. I'm I'm bad at math today. But anyways, you get the idea, right? So you you you can tell your domain expert, hey, give me an hour of your time. I'm going to curate a bunch of activity for you. Just give me your feedback. Just give me a few comments. And now with whisper flow or something, they can just dictate it. They don't even need to type it. Right? So make it very simple.</details>

你要用这个做的第二件事——我先把这个标记为已完成。现在这个人工标注就作为证据与追踪记录保存在一起了。但接下来我想做的第二步是，获取所有这些信息，获取他们给我们的所有这些标注，然后实际使用一个大语言模型（LLM）来找出在他们所有评语中作为模式出现的所有失效模式或类别。对吧？所以这里可能并不是——你不是要求团队去凭空发明类别。你只是告诉他们，针对这些追踪记录给我你们未经筛选的原汁原味评述，然后你将使用 LLM 来归纳出这些类别，因为那是它们所擅长的。它们擅长模式匹配，擅长从文本中提取信息。因此，这样既保证了领域专家的操作简单，又发挥了大语言模型的长处。

<details><summary>Original English</summary>The second thing that you're going to do with this, I'm going to mark this as completed. Now this human annotation lives with the trace as evidence. But then the second step that I want to do is take all this information, all this annotation that they gave us and then actually use an LLM to find all the failure modes or categories that are patterns across all of their comments. Right? So it there might be you're not asking the the the theme to invent categories. You're just telling them, give me your unfiltered raw commentary on these traces and then you're going to use an LLM to then figure out the categories because that's what they are great at. They are great at pattern matching. They are great at extracting information from text. So that way you keep it simple for the domain expert and use LLM for what they are great at.</details>

### 定义评估指标与评估器

现在，一旦你拥有了所有这些类别，那就是我们接下来可以深入到我们的失效模式的地方。那些失效模式，如果我来到这里查看我的实验，那就是你在我每次运行评估时都会看到的——你看到我正在对照评估的所有这些项目。也许让我在这里打开它。

<details><summary>Original English</summary>Now once you have all those categories that is where we can then get into our failure modes and those failure modes if I come here and look at my experiments that is what you're going to see whenever I run an evaluation you see all of these things that I'm measuring against. Maybe let me brought it up here.</details>

所以在我的领域专家给出了输入、并且我根据我的领域专家提取出我的数据语料库中出现的最常见类别之后，我接下来就可以定义我所谓质量的向量或维度是什么了。我们就把它统称为分数，对吧？但我喜欢用一些花哨的词汇来表达事物。但你看这里，其中一项就是引用专家预期来源的正确性；语域正规性，意思是你知道在某些语言中你想用更正式的语气称呼你的客户；语言是否与客户进来时所使用的相匹配；必须包含非主动提供的信息，诸如此类。

<details><summary>Original English</summary>So now after I have my domain expert give me the the the inputs I extracted what are the most common categories that appear in my corpus of data based on my domain expert. I can then define what are my vectors or dimensions of you know quality. Let's just call it we just call it scores right but I like to come up with fancy words to to say things. But you see here how one of them was sites experts expected source correctness for formal register meaning that you know in some languages you want to address your customers with a more formal tone uh if the language matches what the customer came in with u must include non solicited and so forth.</details>

既然我现在有了我要用来衡量输出质量的类别的基础，那么我就可以决定：好的，太棒了，那么我现在要如何对其进行评分呢，对吧？那属于什么类型的分数？那属于什么类型的评估器？为此，我既可以来到这里构建我的评估器库，对吧？这样随着追踪记录的进入，它们会自动为我计算那些分数；但与此同时，每当线上实时发生某些情况时，我也可以让分数直接从客户端应用程序中计算出来，以便随后将其反馈回系统。但基本上，我希望有一种方式，能够跨越“以 LLM 作为裁判”（LLM-as-a-judge）的分数或评估器，以及确定性评估器，来衡量智能体的输出。

<details><summary>Original English</summary>So now that I have that foundation of the categories that I'm going to measure on the quality of my outputs, then I can decide okay cool. So now how am I going to grade that right? What type of score is that? What type of evaluator is that? And for that I can either do come here and build my kind of library of evaluators, right? So that those as as you know traces coming in they're automatically calculating those scores for me but at the same time I can have the scores being calculated directly from the client application whenever something happens online in real time so that then I can surface it back to the system. But basically, I want to have a a way of me measuring the outputs of the agent across both LLM as a judge scores or evaluators, but also deterministic evaluators.</details>

我们在与这些客户合作中总结出的另一个经验是：根据你识别出的类别类型，你越能在 LLM 裁判评估器与确定性评估器之间实现一种组合——一种平衡的组合——效果就越好。因为这样做的好处是，如果你百分之百仅仅依赖 LLM 作为裁判，那么由于大语言模型本身的特性，有非零的几率会出现某些输出是不准确的情况。但如果你引入一些无论发生什么情况、对于相同输入始终完全相同的确定性检查，那么你就可以获得关于智能体质量的综合评分或混合评估。所以这正是我们通常希望看到的。

<details><summary>Original English</summary>Another lesson that we've that we've seen working with these clients is that the more that you can have a mix um a balance mix that is depending on the type of categories that you identify between LLM as a judge evaluators and deterministic evaluators the better because what that's going to do is if you rely 100% just on LLM as a judge there's a nonzero chance that some of the outputs are going are not going to be accurate because that's just the nature of the LLMs. But if you factor in some deterministic checks that are always going to be exactly the same for the same inputs irrespective of what happens, then you can have a blended score or a blended assessment on the quality of your agent. So that's what we typically would like to see.</details>

你在这里看到，当我正尝试定义一个新的评估器时，我可以过来指定我希望它是一个新的 LLM 裁判评估器，或者我希望它是一个代码评估器，并且我可以定义关于我将如何评估该特定智能体活动的所有细节。就是这样。然后如果我想要一个代码评估器，你看，这纯粹就是代码。它是一个函数，是代码。这非常简单，只是一个正则表达式，执行的是完全匹配。但这在 100% 的时间里都会给我完全相同的输出。这不会是只有 95% 或 80%，对于相同的输入，它始终会产生 100% 相同的输出。所以再次强调，这里的经验是，你希望将两者结合起来。

<details><summary>Original English</summary>And you see here when I'm def trying to define a new evaluator I can come and say I want it to be a new LLM as a judge evaluator or I want it to be a code evaluator and I can define all the details on as to how I'm going to evaluate that particular agent activity. So that's that. And then if I want to have a code evaluator, you see this is just code. It's a function. It's code. This is very simple. It's just a reax. This is doing an exact match. But this is going to give me the same output 100% of the time. This is not going to be well 95% or 80%. It's always going to be 100% the same output for the same input. So again, the lesson here, you want to have a mix of both.</details>

### 基于数据集的实验与对比

这就是评估方面的内容。那么现在我们已经讨论了——正如 Annabelle 所说，也许让我回到这里的 AI 工程闭环中。我们在这里已经讨论了构建数据集。我们触及了如何通过运行实验来将这些智能体的质量衡量流程化。然后也许让我回到这里。所以基本上，一个实验是锚定在一个数据集上的。那就是我的测试用例，那些是我要针对我的智能体运行的任务。现在我要说，你知道吗，这个智能体今天是在使用这个系统提示词、这个模型、这些工具运行的。如果我更换了模型会发生什么？如果

<details><summary>Original English</summary>So that's on the evaluation side. So now we've talked about like Annabelle said and maybe let me go back here to the AI engineering loop. So we've talked about here building the data sets. We've we touched on how we can then operationalize the measurement of the quality of those agents running experiments. And then maybe let me go back here. So basically an experiment is anchored on a data set. That's my test cases. Those are my tasks that I'm going to run against my agent. And now I'm going to say, you know what, this agent is running today with this system prompt, this model, these tools. What happens if I change the model? What</details>

<!-- chunk 5/7 -->

如果我修改了系统提示词，会发生什么？如果我现在突然给它提供新工具来访问新数据，又会发生什么？所以你会希望在将它推向生产环境之前能够做这种原型验证，而不是仅仅凭感觉运行——而凭感觉基本上就是我们大家一直以来的做法，对吧？就像是说：“啊，对，看起来挺不错的，让我直接推到生产环境吧。”但这是一个让你系统化开展这项工作的方法。几分钟后，我会向大家展示如何将它作为 CI/CD 流水线的一部分整合进去，这样你就不需要介入流程中了。每当你的智能体发生变更时，就会触发一个 CI 任务来针对数据集运行实验。它会评估采用新配置的智能体，并在我之前提到的所有评分和评估器维度上，切实为你提供一个通过/失败的门禁。这样，对于如何评估和衡量这些智能体的输出，你就拥有了一套一致的方法。听得明白吗？好的，太好了。

<details><summary>Original English</summary>
happens if I make a change on the system prompt? What happens if I now all of a sudden I give it access to new tools to access new data? So you want to be able to kind of prototype that before, you know, promoting into production and just running on Vibes, which is pretty much what all we've all been doing, right? It's like, ah, yeah, it looks kind of good. Let me just push it into prod. But this is a a systematic way of you doing that. And in a few minutes, I'll show you how you can incorporate this as part of your CI/CD pipeline, so you don't have to be in the loop. So that anytime a change hits on your agent, then a CI job is going to kick off to run the experiment against the data set. It's going to evaluate your agent with a new configuration and it's going to give you a pass fail gate effectively across all of the scores and evaluators that I mentioned before. So you have a consistent way on how you evaluate and measure the outputs of these agents. Make sense? Okay, perfect.
</details>

这就是实验部分。那太棒了。我们讨论了实验，也讨论了数据集和人工标注，以便将这些人员及其专业知识融入到流程中。那么现在，我该如何把这一切整合在一起呢？对吧？如果我来到这里，有我的提示词——也就是我正在 Langfuse 中进行版本控制的系统提示词。你可以在 Langfuse 这里做，你知道我们不……没关系，我们这项功能甚至都不收费，所以完全可以。我们很多客户的做法是使用另一个版本控制系统，他们在 GitHub、GitLab 或任何系统里进行版本控制。但你应该把这个当作触发器，用于随后触发完全自动执行评估的自动化流程。

<details><summary>Original English</summary>
So that's experiments. That's great. So we touched on experiments. We touched on data sets and human annotation to bring those humans and their expertise into the loop. So now how do I bring it all together? Right? If I come here and I have my prompt this my system prompts that I'm versioning here in Langfuse. You can do it either here in Langfuse. You know we don't we don't have it's okay. We don't we don't even charge for this. So that's fine. A lot of our customers what they do is they have another version in system. they have a version in GitHub, GitLab, whatever that is. But you should look at this as your trigger for then kicking off the automation to do your eval completely automatically.
</details>

具体的过程是这样的：我已经在这里定义了一个自动化流程。如果你看一下配置，它会在我这里的任何提示词发生变更时触发。然后它的操作是，它将在我的 GitHub 中启动一个 CI 任务，也就是右边这个。希望我不会……我不会遇到 GitHub 的独角兽错误页面。就是右边这个。所以我已经设置好了 CI，让它处于设置好的状态，等待我智能体配置中的任何变更。让我把它移近一点。然后我就可以过来查看我的提示词。我们就看看这一个。我有五个版本的提示词。你可以看到提示词随着时间推移是如何演进的。版本一以前包含这个，然后版本二做了一点微调。到了版本三，你知道，我们尝试了一些不同的东西，这是用于开发的。接着版本四，我们添加了更多细节，并且向智能体的配置中传递了不同的参数。但我现在可以做的是，我说：你知道吗，这是我目前运行的生产环境系统提示词。我想针对版本 4 重新测试，因为我发现了一些退化。所以我可以来到这里，执行推向生产环境。

<details><summary>Original English</summary>
So the way that this happens is I already have defined an automation here. And if you see the configuration is triggering on any prompt changes that I have here. And then the action is it's going to launch a CI job in my GitHub, which is this guy right here. Hopefully I don't I'm not get I'm not getting the unicorn from from GitHub. So it's this guy right here. So I have already my CI set it up set up waiting for any changes in the config of my agent. Let me bring it closer here. And then I can come and see my prompt. Let's just see this one. I have five versions of the prompt. You see how the prompt has evolved over time. Version one, it used to have this and then version two, a slight change. Then version three, it was, you know, we tried something different. This is for development. Then version four, we added more details and also passing different parameters into the configuration of the agent. But what I can do now is I can say, you know what, this is the production system prompt that I have right now. I want to test again with version 4 because I saw some regressions. So I can come here and do promote into production.
</details>

再次强调，我是作为一个人在给大家展示这些，就像原始人一样一步步点击。所有这一切都可以通过 CLI 上的 API 来完成。所以你甚至不需要手动执行这些操作。你只需调用 API，说把带有 production 标签的这个提示词版本推向生产，它就会为你触发执行。我有 production 标签。我要保存并推向生产，推向生产环境，也就是应用新的配置。几秒钟之内，我们应该就会看到这里启动了一个新的 CI 任务，随后它将触发实验来运行我的评估流程。好了，开始运行了。谢谢 GitHub，非常感谢。

<details><summary>Original English</summary>
And again, I'm showing you this as a human, you know, like a caveman like clicking through. All of this can be done via the API on the CLI. So you don't even have to do this by hand. You can just call the API and say promote this prompt version with a production uh tag and it will kick it off for you. I have the production tag. I'm going to save and promote promote to production which is the new configuration. In a few seconds we should have a new CI job that is going is going to launch here that then is going to kick off the experiment to run my evaluation run. Okay, there you go. Thank you GitHub. Thank you so much.
</details>

太完美了。现在我有了这个自动运行的任务。因此，每当我推送智能体配置中的任何变更时，它都会触发 CI。它将运行评估门禁，告诉我是否通过了我们之前定义的各项评估器。借助这种方式，我就能获得证据和确信度，了解是否可以安全地将这个新配置推向生产环境，知道智能体的质量究竟是在下降还是提升，或者是否违反了我所设立的任何保护栏。这需要运行几分钟，不过让我给大家展示一个我早些时候运行的任务。为了展示结果，我可以来到这里看看输出是什么。它告诉我发送的提示词是什么、版本、标签，然后告诉我有通过的门禁，对吧？

<details><summary>Original English</summary>
So perfect. So now I have this job that is running automatically. So any time that I push any changes in the config of my agent, it's going to hit the CI. It's going to run the eval gates to tell me if I'm passing or failing any of the evaluators that we have defined from before. And then with this way, I can have the evidence and also the assurance if I can go into production, you know, safely with this new configuration. if it's actually the agent is degrading or improving in quality or maybe even violating any sort of guard rails that I have put in place. That's going to run for a few minutes, but let me show you one that I run earlier. And to show you the result, I can come here and see what the output is. And it's telling me that this was the prompt that was sent, the version, the labels, and then it's telling me that they gave passed, right?
</details>

太好了。这些就是我用来衡量我的智能体的评估器。我这里有 must include、source recall、language match、correctness 以及 not unsolicited upsell。而且我还可以定义最低限额。我可以规定：这就是我对这一特定分数的最低阈值。如果不达标，它就不会被视为通过以进入生产环境。当然在当前情况下，我还没疯狂到直接说“行，不错，既然通过了，那就去合并并推送到 main 分支”。我只是让它留在那里。但平心而论，你完全可以建立一个端到端流程，让它直接为你创建 PR 并等待有人来审查该 PR；或者像如今大家所做的那样，只要达到了标准，就直接把 PR 合并推送到 main 分支。但至少你在这里拥有了证据，对吧？这样你提交 PR 就不是仅仅凭感觉，或者仅仅凭你主观认为这个智能体擅长做什么。在做出采用智能体新配置的决定时，你实际上拥有了所谓的书面记录和证据。

<details><summary>Original English</summary>
So, perfect. And these are the evaluators that I measured my agent against. I have here the most include, the source recall, the language match, the correctness and not unsolicited upsell. And I can also define minimums. I can say this is the minimum threshold I have for this specific score. If it doesn't clear that bar, it's not going to be considered as a pass uh to go into production. Now, obviously, in this case, I'm not crazy enough to just say, okay, cool. So you pass, go merge it and push into into main. I'm just letting it sit there. But admittedly, you could have a full end to end process that it will just create the PR for you and it will just wait for someone to review the PR or maybe if you are, you know, like like everybody's doing today, just pushing the PR into main straight up uh if it's clearing the bar, but at least you have the evidence here, right? So you're not pushing a PR just running on vibes or just running on what you think that the agent is good at at doing. You're actually have the the paper trail so to speak and the evidence on why you make that decision for this new configuration of the agent.
</details>

### 实际业务指标与失败模式分析

太好了。现在我想给大家展示另外几样东西，作为一个实际的使用案例，对吧？因为我们一直在深入讨论 Langfuse 的技术层面，而越来越多的组织非常关注 Token 经济学，对吧？我认为在 2025 年到 2026 年初，大家都在追求 Token 数量最大化；现在大家都在追求 Token 价值最大化，或者不管他们现在怎么称呼它，大家都想从他们的 Token 中榨取尽可能多的价值。那么现在，让我向大家展示几种方法，你可以向老板、领导或任何人展示，或者你可能想为业务利益相关者构建这些内容，让他们更加确信你所构建的智能体解决方案确实在为业务带来效益。这不仅仅是“哦，我们正在构建一件很酷的东西”。

<details><summary>Original English</summary>
Perfect. So now I want to show you one couple more things as an actual like use case, right? because we've been talking a lot about the technical aspects of of langu and more you know organizations are focused a lot on tokconomics right I think 2025 in beginning 2026 everybody was token maxing now everybody is like token valuing or whatever they're calling it now so everybody's like trying to extract as much value as they can of their tokens. So now let me show you a couple of ways that you can then show your bosses or your leaders or whoever or maybe you want to build this for your business stakeholders for them to feel a little bit more reassured that whatever agent solution that you're building is actually bringing benefits to the business. This is not just like oh the cool thing that we're building.
</details>

现在我这里有一个仪表板，我尝试整合几个指标，以便根据我从智能体收集到的数据向业务部门进行汇报。对吧？第一个是——这里的底层逻辑你可能会跟我有争议，但是你知道，每个组织的情况各不相同。但我在这里试图展示的是：在过去七天里，这个智能体完成了 1,400 次交互，而这些交互不需要转给人工坐席，对吧？所以这很好。这意味着我节省了人力资本，避免让人力花时间去和客户交谈，然后再算一算账。这花费了我多少成本？在过去七天里花费了不到 7 美元，对吧？如果你算上任何联络中心……我 20 年前曾在联络中心工作过，你知道付给那个人的工资是每小时 15 到 20 美元，对吧？那个人是不可能在一个小时内处理 1,400 通电话的。所以通过部署这个解决方案，你已经在展示出至少某些方向性的业务收益了，对吧？

<details><summary>Original English</summary>
Now I have here a dashboard that I'm trying to put together a few metrics that I can report on to the business based on the data that I'm being collecting from my agent. Right? The first one is and this is where you might argue with me in the logic behind this but you know every organization is different. But what I'm trying to show here is that I've had 1,400 interactions of this agent over the last seven days that didn't need to go to a human agent, right? So that's great. So that means that I'm saving, you know, human capital from spending time to talking to customers in in and do the math then. How much has that cost me? It has cost me less than $7, right? Over the last seven days. If you take any contact I used to be a contact center employee back in the day 20 years ago you know what you gonna pay that person $15$20 an hour right so that person is not going to handle 1400 calls in one hour so already you're showing at least some directional business benefit by having this solution in place right so that's the first thing
</details>

这是第一点。第二点是，你也可以开始精准定位你的智能体在哪些领域频频出错，对吧？如果大家还记得的话，我们定义了类目，或者用行业术语来说就是失败模式，即智能体没有给出我想要的结果或答案的情况。这些是我记录的过去七天内按发生频率排序的项。你可以看到，现在 out of scope、informal register 和 dispute not resolved 是排名前三的模式，而且随着时间的推移一直在逐渐增加。因此，我现在不需要去翻阅数千条甚至数十万条追踪记录来试图查清是智能体的哪项活动导致的错误最多或问题最大，而是可以直接来到这里缩小范围。我已经知道这个失败模式是排在第一位的：autoscope、foremost registered 以及 dispute not

<details><summary>Original English</summary>
the second thing is you could also start pinpointing what are the areas where your agent is tripping Right? If you remember, we define the categories or the failure modes as we call them in the industry where the agent is not giving me the results or the answers that I want. And these are the ones that I'm capturing in order of occurrence over the last seven days. You see here that now out of scope, informal register, and dispute not resolved are are my top three and they've been creeping up over time. So now, instead of me having to go through thousands or hundreds of thousands of traces trying to figure out which one is the activity from the agent that is causing the most errors or the most trouble, I can come here and scope it down. And I know already that this failure mode is my top one, the autoscope, the foremost registered and the dispute not
</details>

<!-- chunk 6/7 -->

### 跟踪过滤与争议排查

resolved.

所以现在我可以来到我的追踪界面这里，做一个非常简单的过滤，选择“争议未解决”（dispute not resolved）。我可以把它保存为一个视图。这样我甚至不需要每次都去过滤。你们看它是怎么在顶部为我进行过滤的。甚至在侧边，我也可以过来设置“争议未解决等于 0”。这就会显示所有客户提出争议或要求对某个产品提出争议，而该问题尚未被智能体解决的实例。因此，这要么必须转交给人工客服，要么就是一直搁置着，直到会话关闭且什么也没处理。但现在，我可以不用去翻看成千上万条记录，而是把范围缩小到几十条或几百条。

<details><summary>Original English</summary>
resolved.

So now I can come here in my tracing and do a very simple filter and say dispute not resolved. I can save it as a view. So I don't even need to every time filter it. You see how it's filtering up top for me. And even on the side I can come here and say dispute not resolved equals zero. So that shows all the instances where the customer had a dispute or was asking for a dispute of a product and it hasn't been resolved by the agent. So it either had to go to a human agent or it just lingered and the session closed and nothing happened.
</details>

现在我可以进行更有针对性的排查了。而且现在我也能找出智能体究竟在哪里出现了失误。这是第一点。第二点是，如果我想来到仪表盘这里，我希望能够查看客户给我点赞或点踩的次数。我可以非常轻松地将其记录为一个评分。你们看这里，每次我都可以来到这里看点赞、点踩，我可以把它们直接呈现在仪表盘上，非常易于查阅。任何业务人员、任何用户、任何人实际上都能看到这个，然后说：好的，大部分都是好评，这很棒；但是差评呢？让我们关注一下那 18% 的差评，看看都发生了什么。

<details><summary>Original English</summary>
But now I can then spend my time instead of going through thousands, I can scope it down to maybe dozens or hundreds. And now I can do um an investigation that is more targeted. And now I can also find where are the areas where my agent is actually uh tripping itself up. So that's that's one. The second one is that if I want to come here in the dashboards, I want to then be able to say okay what are the number of times where my customers are giving me either thumbs up, thumbs down. I can I can capture that as a score very easily. You see here every time I can come here thumbs up thumbs down and I can just show it here in a dashboard very easy to consume any business person any user any human actually is going to be able to see this and say okay most of them are thumbs up that's cool but what about the thumbs down let's focus on that you know 18% of them what's been happening
</details>

### 安全风险与护栏验证

另一部分是围绕安全组合。好消息是，我们智能体的大多数交互都没有检测到任何与客户交互中的风险。但我们在这里看到，在过去 7 天的 89 起案例中，实际上是客户在索要投资建议，而智能体可能给出或可能试图给出了投资建议。因此，我们就可以重点排查这些案例。同样也是一样的操作。我可以回到这里说，让我回到默认视图。现在我可以不用数值评分，而是选择分类评分添加一个条件。然后设置意图或安全风险是什么，在安全风险中，比方说选择投资建议。现在我就能看到被标记为涉及投资建议的具体实例，而这些是智能体不应该与客户进行互动的内容。你们看这里，甚至包括我之前展示给你们的那个例子。

<details><summary>Original English</summary>
and then the other one is around the security mix more in here good news most of our interactions from the agent is not catching any sort of risk in the interaction that is having with the customers. But we see here that in 89 cases over the last seven days, it actually the customer was asking for investment advice and the agent might have given or might have tried to give investment advice. So we can then go out and focus on those. And again, same thing. I can come here and say, let me go back to my default view. And now I can say instead of the numeric score, I can come and say the categorical scores add a condition. And then say what is the intent or the security risk and then the security risk, let's say investment advice. And now I can see what are the specific examples where investment advice was identified as a reason for being flagged and that the that the agent shouldn't engage on that with the customer. And you see here even from the previous example um that I was showing you.
</details>

这就是我想要展示的内容：首先是构建端到端面向客户的解决方案的本质。显然，这在责任方面具有许多关键影响，包括财务影响以及声誉影响，因为你绝不想将不准确或幻觉产生的信息呈现在客户面前；以及你如何遵循系统化的流程，从而能够出示证据并验证这些智能体的输出确实遵循了你所设立的护栏和控制机制。说到这里，我想再次把时间交给 Annabelle，这样我们可以做结语，最后也许我们还可以回答几个问题。谢谢。

<details><summary>Original English</summary>
So that's kind of what I wanted to show in terms of first the the nature of going end to end on a solution that you're putting customerf facing first. Obviously, which has a lot of critical implications in terms of liability, you know, financial implications for and reputational as well because you don't want to be putting out information that is not accurate or is hallucinated in front of your customers and how you can follow a systematic process so that then you can show evidence and validate that the outputs of these agents is actually following the guardrails and the controls that you have put in place. And with that I would like to leave you with Annabelle again so we can close and then maybe we can take a couple of questions at the end. Thank you.
</details>

### 人工品味与自动化循环

>> 我们看到有些公司或团队试图这样做：“请修复我的智能体，不要犯任何错误。”我们最不推荐的做法大概莫过于此了。即使你的智能体可能通过 MCP 或 CLI 与你在 Lenfuse 或你可能使用的任何工具中的数据连接起来。我们发现这种做法产生的多半是劣质垃圾（slop），而不是真正对你有帮助的东西。但当然，我们也极为支持与编码智能体协作，以持续改进你的应用程序。

<details><summary>Original English</summary>
>> So what we see some companies trying to do or some teams trying to do is this. Please fix my agent. Make no mistakes. And there's probably a few things that we can recommend less than this. Even though your agent might be hooked up via MCP or CLI with your data in Lenfuse or in whichever tool you might be using. Um this is something that we just see producing rather slop than anything um that is actually helping you. But of course we're also very much in favor of working with your coding agents to continuously improve your applications.
</details>

所以我们想分享这张图表，或许可以帮助大家记住它。这里有两个轴。一个是时间投入，即花费大量时间或花费极少时间；另一个是低质量系统或高质量系统。你绝不会想落在那个区域。如果你将其完全自动化，完全放手让你的智能体去做，只说“帮我修复一切，全替我做了吧”，结果是不会好的。你最终会得到一个低质量的系统；是的，虽然你不需要做任何事，但你的客户也不会感到非常满意。

<details><summary>Original English</summary>
Um so we wanted to share this just as a picture how you can maybe memorize it. So we have two of those a here. We have one uh being the time invest. So, a lot of time spent or very little time spent and then also a low quality system or a high quality system and you don't want to be down there. If you fully automate it and just let your agent go for it and just be like fix everything, do it for me. Um, this is not going to turn out well. You will end up with low quality and yes, you don't have to do anything, but also your customers will not be super satisfied.
</details>

与此同时，你也不想再走完全人工的老路了。你不想再亲自去为应用程序做埋点检测（instrument），这是可以自动化的。你也不想自己去捕获所有的失效模式并亲自复审所有数据，这同样是可以自动化的。但在同一时间，对于某些事情，你应该融入自己的品味。你应该把领域专家请到现场来构建数据集，去策划你的应用程序实际应该解决的问题是什么，以及你希望它朝着哪个方向发展。

<details><summary>Original English</summary>
At the same time, you also don't want to go go the full manual way anymore. You don't want to instrument your app yourself anymore. This is something that can be automated. You don't want to catch all the failure modes yourself and re review all the data yourself. This can be automated. Um but at the same time, for some things, you should get your taste in. You should get your domain experts in the room to build out the data sets to curate what is actually um what actually is the problem that your application should be solving and in which direction you want it to go.
</details>

为此，你会希望落在中间的某个位置。也就是理想的平衡点：一方面你审核数据、带入品味、带入领域专长，另一方面也与编码智能体协作完成所有可以自动化的工作，例如埋点检测、寻找失效模式、运行评估，或许还能尝试 20 种实验，而不是仅凭自己想出的那一种。是的，就是避免掉进左下角，努力成为一名有品味的 AI 工程师，融入品味，确保评估表现出色，随着时间的推移，你也可以将这个循环越来越自动化。

<details><summary>Original English</summary>
And for this um you want to land somewhere here. So where the ideal balance is between like um you reviewing data, bringing in your taste, bringing in your domain expertise, but also working with your coding agent for all the things that you can automate like instrumenting it, finding failure modes, running the evals, maybe making also 20 experiments instead of only one um that you would come up with and yeah, just like avoid getting down there in the left uh down corner, but try to be the the tasteful AI engineer that is bringing in the taste, making sure the the emails are great and then you can also more and more automate this loop over time.
</details>

### 入门建议与相关资源

如果我们处于各位的位置，并且明天就必须着手开始，我们会这样做：我们会安装 lenuse skill，这是一个智能体技能。它是一套 Markdown 文件，用于帮助你的编码智能体理解如何使用 lenfuse 以及如何实施这些最佳实践。它连接了我们的文档和所有的集成页面；它也连接了我们的学院，我们在那里融入了关于数据集、如何埋点以及如何编写评估器等所有方面的最佳实践。所以这是一个极好的起点，既能自动完成那些你应当自动化处理的事情，也能帮你整理出一套应该人工查看的数据集。然后，你应该开始收集基准真相（ground truth），以便针对它来评估你的智能体，这些数据可能来自历史数据、生产环境，或者与你的领域专家一起运行的一些样本。如果你处于强监管领域，请以某种方式定义你的硬性限制，确保明确哪些事情是绝对不能发生的——例如对于金融服务，它绝不应该给出投资建议。因此，请确保在评估集中也融入这一点，理想情况下永远不会发生，但至少当它发生时，你能够知情。

<details><summary>Original English</summary>
If we were you and we would have to get started tomorrow, h this is what we would be doing. We would install the lenuse skill which is a yeah it's an agent skill. So it's a set of markdown files that is helping your coding agent to wrap its head around how to work with lenfuse and how to implement those best practices. It is hooked up with our documentation with all our integration pages. um it is hooked up with our academy where we ingrain the best practices around data sets and how to instrument and how to write evaluators and all of this. So it's a a great starting point um to do the things uh automatically um that you should be doing automatically but also to maybe curate a set um of data that you should look manually at. uh you should then start to collect um also ground truth that you can evaluate your agent against maybe from historical data also from uh production or from some samples that you're running with your domain experts and if you're in a regulated space uh define your hard limits in a way to make sure these are the things that definitely shouldn't happen for financial services for example it should never give investment advice so make sure that you're ingraining this also in your evaluation set um that ideally never happening but at least you will know about it um when it's going to happen
</details>

我们还为大家准备了一些资源。Donelli 向大家展示并使用的那个代码库也可以在网上获取。大家可以亲自去查看，你可以从中提取任何你想要的内容，并将其用于你自己的用例。里面的数据当然是虚构的，并不是直接从我们客户那里采集的内容。而且我认为本次会议也会有录像，所以大家可以再次回顾。此外，我们还推荐 langu academy，这是一篇关于如何进行 AI 工程的大篇幅专文，完整步骤都在其中进行了再次阐述。我们还有一个自助式工作坊，基本上会引导你完成所有步骤，以便你理解一次后，就可以着手处理你自己的应用程序了。

<details><summary>Original English</summary>
and we have a few resources for you. So the repository Donelli showed you and used um is also available online. Uh you can check it out yourself. You can take everything that you want from it and also use it for your own use cases. It's of course fictional data and not um not something that actually um was taken from our customers and I think also this session will be recorded so you can take a look again. uh we then also recommend the langu academy which is like a larger writeup of uh how to go about AI engineering um the whole steps um described again and we also have a self-s serve workshop that is basically guiding you through all the steps so you understood it once and then um yeah can go ahead with your own application
</details>

在接下来的几天里，有一些机会可以与我们偶遇。一个是，Donelli 在周三也会发表一场关于为 AI 智能体构建部署关卡（deployment gates）的演讲。如果你想了解如何确保进入生产环境的 AI 模型确实通过了质量关卡，欢迎前来参加。另外，我们还有一个展位，9 号展位。我还没去看它具体在哪里，但我确信你们会找到的。你们可以在那里与团队见面，还可以拿到定制贴纸。就是拍一张你的面部照片，然后由 AI 生成关于你的脸和 length 的贴纸

<details><summary>Original English</summary>
there's some opportunities to bump into us over the next days uh one is um Donelli is giving a talk also on building deployment gates for AI agents on Wednesday so Check it out if you want to understand how you can make sure uh that AI models that go to production are actually um clearing quality gates. Uh we're also having a booth, a booth 9. Um I haven't checked out where it is, but I'm sure you will find it. Um you can meet the team there, but also you can get custom stickers. So you take a picture of your face and then it AI generates stickers of your face and length
</details>

<!-- chunk 7/7 -->

### 社区活动与提问环节

……使用，可能还包含一些笑话。嗯，你们可以把它们带回家，贴在你们有的任何东西上。最后，我们还有一个社区跑步活动。所以如果你想走出会议中心去见见团队，我们有两位联合创始人也在这里，嗯，还有几位团队成员，而且我们都很喜欢跑步。所以我们觉得可以邀请大家一起来加入我们，嗯，参加这个活动。所以，是的，欢迎大家也来参加这个。我们非常乐意用剩下的几分钟时间回答任何类型的问题。他们这里也有一些非定制的贴纸。虽然只是一张长条贴纸，但我认为它依然很酷。所以如果你想要一些，你可以走上来，呃，拿一些。我们很乐意回答任何问题。还有，请过来见见我们，别客气。我现在把这个交给 Delli。

<details><summary>Original English</summary>
use with a maybe some jokes also included. Um and you can take them home and sticker it on everything you have. And then finally, we also have a community run. So if you want to step out the conference center and meet the team, we also have two of our founders here um and a few more team members and we're all big runners. So we thought we just might invite everyone else as well to join us um for this. So yeah, please come for this one as well. And we're super happy to use the remaining minutes for any kind of questions. They also have some non-custom stickers here. It's just a lengthy sticker, but I think it's still pretty cool. So if you want some, you can come up uh and get them. We're happy to take any questions. and ple please meet us and don't be a stranger. I'm handing this to Delli.
</details>

### 数据存储与部署

>> 是的。嗯，Langfuse 本身对其存储有针对 ClickHouse 的硬性依赖。嗯，这只是因为，你知道的，在产品的演进过程中，它最初使用的是 Postgres。呃，但后来 Postgres 无法承受我们所达到的规模，比如每天数十亿、数百亿的事件。那就是我们转向 ClickHouse 的时候。因此，在那个数据平面方面，是的，在 ClickHouse 中。但也许想追问你一下，就那些数据存储而言，你的需求是什么？因为我们也为你提供了导出数据的能力，你可以将它导出到 S3，你可以使用……啊是的，如果你想从 Langfuse 消费数据，你可以使用 API、CLI 或者 MCP，所以这完全取决于你，是的。

<details><summary>Original English</summary>
>> Yeah. Well, the Langfuse per se has a hard dependency for their stores with click house. Um that is just because you know in the evolution of the product it started with Postgress. Uh but then Postgress couldn't handle the scale that we achieved and like billions of billions of events per day. That's when we moved over to Clickhouse. So in terms of that data plane yes in clickout so but maybe the followup for you what is the need for you in terms of that data stores because we also offer the ability for you to export the data you can export it to S3 you can use the a yeah you can use the API the CLI or the MCP if you want to consume the data from langfuse so it's totally up to you yeah
</details>

>> 我想把它托管在……

<details><summary>Original English</summary>
>> I want to host it on
</details>

>> 是的，你完全可以 100% 托管在 Amazon 上。嗯，你知道的，我们也有自托管部署方式。嗯，你既可以使用我们的云服务产品——那是完全开箱即用的 SaaS，你不需要做任何事情，它运行在 Amazon 上；但如果你想自己运行底层基础设施，比如因为你有，我不知道，你知道的一些闲置在那里的 EC2 实例想要使用，我们也有一种对应的部署模型，并且它预先打包好了所有组件。

<details><summary>Original English</summary>
>> yeah you you can host it 100% on Amazon um it's you know we have a self-hosted deployment as well um you can either use our cloud offering that is fully SAS turnkey you don't need to do anything it runs on Amazon but if you want to run the infra yourself because you have I don't know some you know EC2 instances lying around there you want to use we also have a deployment model for that and it comes prepackaged with all the components
</details>

### LLM as a Judge 与评估一致性

>> 是的，非常重要的问题。刚才的问题是关于评估者间信度（inter-rater reliability），嗯，大概也关乎作为裁判的 LLM（LLM-as-a-judge）评估器的一致性，以确保它确实捕获到了，嗯，你想要它捕获的内容。嗯，实际上这项语言技能的一部分也在处理这个问题，并帮助你……嗯，有一个专门的术语，嗯，我一下想不起来了，但它归根结底是一个确保 LLM 能像人类那样做出评判的过程。呃，你基本上要做的就是自己去评判一个样本，嗯，最好是一个具有代表性的样本，然后你运行你的 LLM-as-a-judge，接着你针对“让 LLM-as-a-judge 与你的人类评分员所做的评判保持一致”来进行优化。理想情况下你会安排几个评分员，那是学术上的处理方法。那么比较实际的做法可能就是让一个人标记一些数据，然后对照这个基准真相进行优化；接着在理想情况下你只需随着时间推移去检查它，以确保你的数据集保持代表性。特别是如果你将它用于，嗯，运行在生产数据上，在理想情况下，你刚开始最好允许出现稍多一些的假阳性（误报），这样你捕获到的虽然比必要的稍多一点，但不会遗漏任何东西，然后你只需要随着时间推移去逐步下调它。

<details><summary>Original English</summary>
>> yeah super important question so the question was about interator reliability um and also probably just consistency of LLM as a judge evaluators to make sure it's actually catching um what you want it to catch um there's actually also part of this language skill is handling this as well and helping you to um h there's a term for it. Um it fell out of my head but it's in the end about the process of making sure the LLM is judging like a human would judge and uh what you do basically is you judge a sample um ideally a representative sample yourself and then you run your LLM as a judge and you then optimize for the LLM as a judge being coherent with what your human human raiders do and ideally you have like a few human raiders and that's academic approach to it. So probably the practical approach to it is have one human label some data and then optimize against this ground truth and then ideally you just check it over time to make sure your set stays representative and especially if you are using it for um running on production data it's in the end ideally you just start with having a a few too many false positives so you catch a little more than necessary but don't miss anything and then you just tune it down over time.
</details>