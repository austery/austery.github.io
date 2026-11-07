---
author: Latent Space
date: '2026-10-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KM3VQZKjpiY
speaker: Latent Space
tags:
  - autonomous-agents
  - wealth-management
  - ai-harness
  - financial-services
  - human-in-the-loop
title: Arca：利用自主 AI Agent 构建原生财富管理公司与长周期金融工作流
summary: 在 2026 年纽约 AI Engineer 大会上，Arca AI 平台负责人 Aman Singh 介绍了其近期融资 6400 万美元打造的 AI 原生财富管理公司。Arca 并非 SaaS 软件商，而是直接经营财富管理业务的机构。系统通过自主开发的模型无关 Harness、跨越数天的长期记忆与反思系统以及严格的人机协同护栏，让 Agent 在后台主动提示人类顾问并驱动复杂财务规划与合规验证。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Aman Singh
companies_orgs:
  - Arca
  - Anthropic
  - OpenAI
products_models:
  - Claude
  - Opus
  - Sonnet
  - GPT
  - Gemini
  - Luna
  - Jev
media_books: []
status: evergreen
---
### 引言与业务定位：AI 原生财富管理机构

**>>**: 我们实际上并不是一家 SaaS 公司。我们本身就是这家财富管理机构。Agent 提示人类的次数比人类提示 Agent 的次数还要多，这是一种为他们全天候 24/7 运行的主动式服务。

<details><summary>Original English</summary>

**>>**: We're actually not a SaaS company. We are we are the firm ourselves. Agents prompt people more than people prompt agents and it is a proactive kind of service that is running for them 24/7.

</details>

**>>**: [音乐]

<details><summary>Original English</summary>

**>>**: [music]

</details>

**>>**: 我们现在是在 2026 年纽约 AI Engineer 大会现场，坐在我身旁的是来自 Arca 的 Aman Singh。Arca 最近刚刚完成了 6400 万美元的融资，旨在打造一家 AI 原生的财富管理公司。首先，Aman，你能向我们简单介绍一下你在 Arca 的职责、你们所提供的金融服务，以及你们是如何利用 AI Agent 来运行这些业务的吗？

<details><summary>Original English</summary>

**>>**: So we're here at the AI Engineer New York conference 2026 and I'm here with Aman Singh from Arca and Arca's recently raised $64 million for an AI native wealth management firm. So first of all, Aman, can you tell us a bit about your role at Arca and the financial services you provide and how you're using AI agents to run them?

</details>

**>>**: 好的，没问题。感谢邀请我。

我在 Arca 的职责是领导 AI 平台团队。我们正在构建底层的 Harness 机制以及我们的各项能力，以便用 AI 来运转业务，这也是我们的终极目标。

就我们向客户提供的服务而言，这涵盖了广泛的金融服务。其中包括财务建议、针对客户资产的财务规划，以及随着人们财富增长而涉及的税务筹划、保险和遗产规划。

例如，你可能是一位刚刚卖掉了一家公司的人，涉及所有不同合伙人等诸多复杂情况，对吧？我们可以帮助你理清这些细节。我们的客户中也有大型科技公司的高管，他们正在试图制定一个切实可行的提早退休计划；还有一些小型家庭，比如正在尝试购买他们的第一套住房。

<details><summary>Original English</summary>

**>>**: Yeah, for sure. Thanks for having me. My role at Arca is I lead the AI platform team. So we're building the underlying sort of harness and our capabilities to kind of run the business with AI, which is our ultimate goal. In terms of the services that we provide to our clients, this is a broad spectrum of financial services. So that includes sort of financial advice, financial planning for for their assets and sort of um tax planning and insurance and estate planning as as people get wealthier. Maybe you are someone who just sold a business for example and there's lots of complexities with all the different partners etc, right? So we can help you think through that. We also have clients that are you know, really large technology executives that have are trying to figure out a real plan for retiring retiring early, right? And also small families that um that are trying to buy their first home for example.

</details>

**>>**: 是的。

<details><summary>Original English</summary>

**>>**: Yeah.

</details>

**>>**: 是的。

<details><summary>Original English</summary>

**>>**: Yeah.

</details>

### 人机协作模式：重塑顾问周边工作而非取代人类

**>>**: 那么对于你们目前拥有的客户，你们是否需要向他们详细解释使用 Agent 的情况、为什么要使用 Agent，并向他们介绍背后的技术？

<details><summary>Original English</summary>

**>>**: So the the clients that you have so far, are they do you have to kind of talk them through using agents and and why you're using agents and tell them a little bit about the technology behind it?

</details>

**>>**: 是的，在 Arca，AI 的角色并不是去取代顾问，而是取代顾问周围所有的繁杂工作。因此，我们的客户实际上并不直接与 AI 交互。他们所体验到的，是通过人类顾问的同理心与关怀所传达出的、在这个行业中以往从未实现过的服务水平。

我们正在为每位客户构建背后的运转机制，它在持续思考：现在的市场走势如何，这对 Richard 有什么影响？你的生活中还有什么其他事情在发生？比如，你生活中哪些具体细节会影响你的财务状况？

借助由 AI 处理所有后台事务，我们能够表现得更加主动、更加敏捷，并提供更优质的客户服务。

<details><summary>Original English</summary>

**>>**: Yeah, so the role of AI at Arca is not to replace the advisor. It is to replace all of the work around the advisor. So, our clients don't really interface with AI directly. All they experience is a level of service that has not been been been possible in this industry before, delivered through the empathy and care of a human advisor. So, we're building the machinery behind every client that's constantly thinking about you know what what is the market doing and how does it impact Richard? You know, what what what else is going on in your life? Like what are you what are the the textures of your life that impact your finances? And we're able to be way way more proactive, way more responsive, and just deliver a better kind of level of client service using AI that does all of the the back office stuff.

</details>

### 底层模型架构与自研 Harness

**>>**: 好的。那我们深入探讨一下其中的一些技术细节。你们目前正在使用哪些模型来驱动你们的 Agent？你们又是如何决定哪个模型最适合哪类操作的？

<details><summary>Original English</summary>

**>>**: Okay. So, let's get into the some of the technical aspects of it. Which models are you using to power your agents and how do you decide which model is best for for which action?

</details>

**>>**: 好的。目前我们使用的是来自前沿实验室（例如 Anthropic 和 OpenAI）的前沿模型。Claude 一直是我们主要使用的模型，但多年来我们经历了几轮模型迭代。很久以前我们用过 Gemini，然后是 OpenAI，再之后是 Anthropic。

指导我们所有决策的，是我们在内部建立的基准测试，这些基准涵盖了我们通用 Harness 在运营业务中所必须表现出的各项能力。

例如就在最近，尽管外部基准声称 Luna 表现优异，但它在我们这里的实际表现并没有达到我们的预期。它要么太慢，要么成本很高。因此，我们的内部基准会指导我们的模型决策；作为原则，我们希望保持模型无关性（model-agnostic），尽量不依赖某个特定供应商或某家实验室提供的特定 Harness，从而为自己保留这种灵活性与选择空间。

<details><summary>Original English</summary>

**>>**: Yeah. So, today we're using the frontier models from from the frontier labs like Anthropic and and Open AI. Claude is kind of our primary model has been but we've gone through several iterations of models over the years. We used to be in Gemini way back when and then Open AI and then and then Anthropic. And what's guiding all of our decisions are our benchmarks that we have internally for all of the various capabilities of our general harness that it has to express in in running our business. And so, just recently for example, despite the external benchmarks claiming great things for Luna, it didn't really quite work out for us as as well as we had expected. It was way too slow or and it was costing a lot. And so, our internal benchmarks kind of guide our model decisions and as a principle we we want to be model agnostic and and sort of not, um, you know, um, take a dependency on on a a certain provider or certain harness from one of these labs and kind of keep that that optionality open for us.

</details>

**>>**: 明白。你刚才提到了 Harness。那么你们是根据所使用的模型来采用不同的 Harness 吗？

<details><summary>Original English</summary>

**>>**: Okay. So, you just mentioned harnesses. So, are you using different harnesses depending on which model you're using?

</details>

**>>**: 不是，我们使用的是在内部构建的自有 Harness，它是模型无关的。

<details><summary>Original English</summary>

**>>**: No, we have we have our our own kind of built internally that is model agnostic.

</details>

**>>**: 好的。当财务顾问在制作税务报告或类似事务时，Harness 是如何决定使用哪种模型的？这个过程是自动化的吗？

<details><summary>Original English</summary>

**>>**: Okay. So, you know, when when your when a financial advisor is doing something like a taxation report or something like that, how does the harness decide which model to use? Is that automated?

</details>

**>>**: 是的。我们会根据任务的不同复杂度划分某些模型层级。比如协助制定税务计划或进行税务分析这类任务，会分配到我们最高级别的模型层级。

在这一层级内部具有一定灵活性，你可以使用类似 Opus 级别的模型、Sonnet 级别的模型，或者参数量较大的 GPT 模型。

但与此同时，我们的 Agent 会参与很多后台活动，这些活动会根据任务复杂度使用较低层级的模型。这就是我们如何决定由哪个模型来服务哪项任务的大致机制。

<details><summary>Original English</summary>

**>>**: Well, yes. So, we have, um, certain tiers of models based on different complexities of tasks. So, a task like assisting with a tax plan or doing a tax analysis would get our like heaviest tier of models. Inside of that tier, it is a little bit flexible, so you could use, like an Opus tier model or a Sonic tier model or a heavy GPT model. But, based on there's a lot of like background activity that our agents are participating in, right? That is using the a lower tier of model based on the complexity of the task. So, that's kind kind of how we how we make decisions on on which model serves which task.

</details>

**>>**: 明白。那么是在财务顾问使用产品的过程中由他们亲自做出这个决定吗？

<details><summary>Original English</summary>

**>>**: Okay. So, is it the the financial advisor that's actually making that decision while they're using the product?

</details>

**>>**: 并不是。他们并没有意识到这一过程的发生。我们已经把这些完全抽象化了。他们只是像平时一样与我们的产品交互，而这些决策是由我们系统内部自动完成的。

<details><summary>Original English</summary>

**>>**: Not really. They're they're they're not aware of the happening. We've abstracted this away from them entirely. They kind of just interact with our product as they would, and those decisions are made internally by us.

</details>

### 长周期任务执行与人机回环安全护栏

**>>**: 好的。在你今天早些时候在大会上的演讲中，你谈到了一个税单的例子。我想知道你是否可以带我们走一遍调整客户投资组合的实例——比如从发现需要对投资组合进行再平衡，一直到执行交易。你能详细讲讲整个流程中哪些部分是由 Agent 完成的，哪些部分是由人类顾问完成的吗？

<details><summary>Original English</summary>

**>>**: Okay. So, in your presentation at the conference earlier today, you talked about a tax bill example. I just wondered if you could maybe walk us through an example of adjusting a client's portfolio, investment portfolio, you know, from identifying a need to maybe rebalance the portfolio to executing trades. Can you talk us through, you know, what parts of that process the agent does and and what parts the human advisor does? Right.

</details>

**>>**: 就像在演讲中提到的那样，这是一件跨越 10 天的事情。Agent 最终负责推动交付该结果，但其中某些部分是它们做的，某些部分则是它们不做的事情。

在这个例子中，当客户就这笔税单向我们发送电子邮件时，其中涉及一部分分析工作：该客户目前的资金配置在哪里？为了变现出 100,000 美元，最理想的变现方式是什么？这最适合作为一项分析任务交给 Agent 处理。

<details><summary>Original English</summary>

**>>**: Um so, just like in the talk, this is a thing that will span 10 days. Um and so, agents are ultimately um responsible for delivering that outcome, but there are are are certain parts that they do and certain parts that they do not. So, in this example, um when uh when the client emails us uh with this whole tax bill, there's a there's a piece of the analysis of like, where is this client's money allocated today? And what is the most optimal way um to liquidate some of that to to produce $100,000? That is best suited for agents

</details>

**>>**: 确实。

<details><summary>Original English</summary>

**>>**: >> Right.

</details>

**>>**: 让他们将其作为分析任务接手。

<details><summary>Original English</summary>

**>>**: >> to take on as an analysis task.

</details>

**>>**: 是的。

<details><summary>Original English</summary>

**>>**: >> Yeah.

</details>

**>>**: 所以它们就专门执行这部分。

<details><summary>Original English</summary>

**>>**: >> So, that they do exactly that.

</details>

**>>**: 它们是否有某些限制，比如不能以正确的金额直接执行交易？

<details><summary>Original English</summary>

**>>**: >> Do they have certain limits though that they can't, you know, they can't execute a trade at correct amount?

</details>

**>>**: 分析部分是完全自动化的，但它们无法自动执行任何资金划转或资产变现操作。

我们与托管机构有着非常深度的集成，托管机构确实为我们提供了能够执行此类操作的 API，但对于涉及转移资金、变现资产甚至直接与我们的终端客户沟通的事情，我们设置了严格的人机协同（human-in-the-loop）安全护栏，因为我们追求极高的服务标准与质量。

因此，所有内部分析都将由 Agent 完成，但在需要时它们也会拉入合适的人选来执行交易。Agent 会为相关人员提供一份方案供其审核和调整，然后再从那里继续推进。

<details><summary>Original English</summary>

**>>**: So, the analysis part is fully automated, but um they're unable to actually execute uh any sort of money movement or liquidation automatically. We have a very deep integration with our custodian uh that actually gives us APIs to be able to do that, um but we have strict guardrails around human in the loop for things that would either move money or liquidate assets or even directly communicate with our with our end clients uh because there's a level of service that that uh service service and quality that we expect. Um so, all of the like internal analysis will be done by agents, but the the they will also pull in the right person to be able to execute the trade when needed. So, and they'll give it give the personal plan that they they're able to review and kind of like adjust. Um and yeah, go from there.

</details>

### 跨天持久化记忆与“反思做梦”机制

**>>**: 是的。你提到这些流程往往需要 10 天，或者至少比目前大多数 Agent 任务具有更长的运行周期。那么，当一个 Agent 在几天后重新恢复一项任务时，你们如何进行状态恢复？你们如何确认该方案仍然符合客户的需求？

<details><summary>Original English</summary>

**>>**: Yeah. Yeah, so you mentioned that um these processes tend to be, you know, 10 days or at least a longer sort of uh running time than most sort of agent stuff these days. So, um when an agent kind of resumes a task maybe days later than they, you know, than they started it, how do you restore How do you check that the plan still fits the client's uh you know, uh needs.

</details>

**>>**: 是的，这是一个很有意思的切入点。正如我在演讲中描述的，我们有大量的这类信号。

例如，你可以设想有一封正在收到回复的邮件往来，里面正在进行讨论。你可以想象，对该邮件的任何追加回复都会交给负责阅读该邮件并做出反应的同一个 Agent。

但是，如果在中间打来了一个电话，那这就是一个全新的信号，它并不附属于任何其他正在进行的流程。此时会有一个全新的 Agent 唤醒来弄清楚这意味着什么。它们理解当前正在发生什么的方式，是依靠我们的内部记忆系统。

针对每一位客户，我们都维护着持久化记忆：当前正在发生什么、我们正试图提供什么服务、谁负责哪项事务、迄今为止发生了什么、我们下一步正在追踪什么、未来几天内需要立即处理什么、我们正在长期追踪什么、具体哪个人负责哪项操作。所有这一切都由我们的记忆系统进行追踪，而我们的 Agent 也会向其贡献内容。

不仅如此，系统还有一个类似于“做梦”的反思过程，它会反思与客户 Richard 相关的世界状态，并能够更新这些记忆系统，以维持长周期的任务推进。因此，那个接收到新信号的 Agent 能迅速了解该客户当前的最新状况，并认识到：“好的，我们实际上正在处理一笔大额税单。”它将能够确认：“我的信号与这笔税单有关，因此让我为该世界状态贡献更新。”

<details><summary>Original English</summary>

**>>**: Yeah. Um so, this is an interesting interesting one to think about is we have tons of these signals like I described in the talk. Um some are for example, you can imagine there's an email thread that is receiving responses and there's chatter happening, right? You can imagine that that any ad- ad- additional response to that goes to the same agent that's kind of like reading that that email thread and reacting to it, right? But a a fresh signal of it's like a like a phone call that was made in the middle, um that is a brand new signal that isn't attached with any other ongoing process. And so, there's like a fresh agent that wakes up to figure out what this means, right? And the way they way they understand what is happening right now is our internal memory systems. So, we have um we have this this persistence of for every client um what is happening right now, what are we trying to service, who owns what, what has happened so far, what are we tracking for next, right? What what needs to happen immediately in the next couple of days, what are we tracking for the long term, right? Which individual is responsible for which action? All of this is being tracked by our memory systems that our agents contribute to. But also, there is a a kind of really sort of dreaming process that reflects on the state of the world as it relates to Richard, the client, um and is able to kind of like update these memory systems to to persist long horizon kind of tasks. So, that agent that received a new signal quickly ramps up on what uh the situation is with the client and it'll know, "Okay, we're we're actually executing a big tax bill." Um and we'll be able to see, "Okay, my signal relates to that tax bill, so let me kind of contribute to the to to the state of that world."

</details>

### 安全体系、确定性防御与合规审计

**>>**: 你能谈谈你在产品或 Harness 中构建的安全方面措施吗？显然要确保在整个过程中不会造成资金损失。

<details><summary>Original English</summary>

**>>**: Can you talk a little bit about the the safety sort of aspects that you've maybe built onto your product or harnessed to to to to make sure obviously that uh no money is lost along the way?

</details>

**>>**: 好的。我们所有的安全限制都是完全确定性的，它们将决策权从 Agent 手中剥离出来。

例如，某些工具允许 Agent 自身直接执行。如果它属于简单的记录保存类工具，系统就会直接执行它。此外，每次调用写入数据的工具时，我们都会针对该操作运行基于大语言模型的验证。这些轻量快速的 LLM 调用会分析向我们数据库进行的每一次写入。这是我们正在运行的另一层验证。

另外，我们还会摄取大量的外部信息。这里有进来的电子邮件、进来的文档、打进来的电话，这些都是 Prompt 注入的目标。因此，我们在系统边缘运行各类验证，用于检测某些特定类型的 Prompt 注入。

每当遇到数据流出我们系统的情况时——例如最典型的网络搜索，或者比如我们要给 Richard 发送一份日历邀请——针对这种外部数据传输，我们既包含用于识别特定 PII（个人身份信息）存在的确定性检查，同时也采用小型模型共识机制，以确保不会发生任何形式的数据外泄企图。

我们在 Harness 中内置了大量不同类型的安全护栏，其核心原则是将其约束在能力边界的边缘，而不是在更早的阶段对其进行过度限制。

<details><summary>Original English</summary>

**>>**: Yeah. Um so, all of our safety restrictions are are fully deterministic and they they take the decision making off the the agent's hands. So, for example, um certain tools let the let the agent kind of execute the tool itself. So, if it's like a simple record keeping kind of tool, um it will execute it. We also with every time a tool is called that writes data, we have um uh LLM based verification running on uh on that action. Um these like fast uh LLM calls that that analyze every single write to our database. Um so, that's another layer of verification we're running. And then uh we also ingest a lot of like external information. So, there's emails coming in, documents coming in, phone calls being made, which are targets for prompt injection. So, we run um sort of verifications at the at at the edges that detect presence of certain um you know, flavors of prompt injection. And then anytime there is a um there's a case where uh data leaves our system, for example, in like a a web search in in the most obvious case, but also So, if we're sending a calendar invite to Richard, right? That's an external kind of uh data where we have both deterministic checks on presence of certain information that we know is PII, uh but also a consensus of small models that that ensure that there isn't any kind of data exfil being attempted. Um so, we have tons of different different kind of guardrails built into the harness uh with the principle that we want to kind of contain them at the edges of capability uh and not earlier than that. Yes.

</details>

**>>**: 鉴于你们身处金融行业，是否存在某些监管要求必须在你们所使用的技术层面予以遵守，还是说监管更多只关注最终结果以及你们对待客户的方式？

<details><summary>Original English</summary>

**>>**: And and because you're in the financial uh you know, industry, are there certain kind of regulations that uh are required that you have to sort of keep to in terms of the technology that you're using or is that is it just more about outcomes and and the way you sort of deal with clients?

</details>

**>>**: 行业关注结果，但合规关注可审计性。

因此，我们的系统设计使得可审计性成为默认内建属性。

Agent 采取的每一个操作都会生成变更日志：变更了什么、谁变更的、来自系统的哪个部分以及何时变更的。顺便提一下，这不仅适用于 Agent，同样适用于人类参与者。如果你在 UI 中更改了影响客户的内容，我们也会记录该操作。

这不仅让我们在默认情况下获得了可审计性，同时也赋能了我们的一些 Agent 能力——用来追踪 UI 更改的机制，也可以用来通知 Agent 该事件已经发生。

可审计性一直是我们发展的重要组成部分，这既是为了显然符合监管要求，也是为了支撑我们的 Agent 循环。

<details><summary>Original English</summary>

**>>**: Yeah, the the industry cares about outcomes, but um compliance cares about auditability, right? Um and so, um our um our system is is is such that auditability is by default. Um we have every single action that that an agent takes produces a change log of what changed, um, who changed it, from which part of the system, and when. And this [clears throat] applies not just to agents, by the way. It applies to human actors as well. So, if you change something in the UI that affects the client, uh, we'll log that action. So, it lets us both get auditability by default, but also powers some of our agentic capabilities where the same thing that that we tracks like a UI change also could be used to like inform the agent that that happened. >> Right. >> Um, so auditability has been a big part of our, um, our story both for, obviously, compliance with regulation, uh, but also for our, um, agentic loop.

</details>

### “Agent 提示人类”与机构运营标准化

**>>**: 确实。在你之前的演讲中有一句很有意思的话：“Agent 提示人类的次数比人类提示 Agent 的次数还要多。”那么 Agent 是如何决定该引入哪个人，以及它们需要向该人员提供多少上下文以帮助其完成任务呢？

<details><summary>Original English</summary>

**>>**: Yes. In your, uh, presentation, uh, you had a nice line, "Agents prompt people more than people prompt agents." Um, so how do the agents decide who to involve and, um, you know, what sort of how much of the context that they need to provide that person in order to do what they need to do?

</details>

**>>**: 是的，这也是一个很有意思的问题。在我们行业中，这与人类的工作方式类似：存在一个我们要追踪超过 10 天的流程，涉及多个参与方。处在第 7 步的参与者可能暂时还不需要知晓此事，对吧？他们会在适当时机被拉入流程。

因此，依靠长久期持久记忆以及对日常发生事务的反思，我们的 Agent 会反思当前世界状态处于什么阶段。当出现表明必须拉入某个人的信号时，Agent 能够在恰当的时间拉入合适的人。

所有这些都是我们为将该行业的运作上下文落地为可操作流程所做的工作。但不仅如此，这还涵盖了 Arca 希望它如何运作，以及我们对该行业工作方式所坚持的原则。

这也是我们作为一家机构、而不仅仅是一家 SaaS 公司的另一个优势。我们实际上不是一家 SaaS 公司，我们本身就是这家机构。因此，我们甚至可以规范这项工作发生的方式，从而让我们的 Agent 能够以标准化的方式参与到各项既定工作中去。

<details><summary>Original English</summary>

**>>**: Yeah. Um, another interesting one. So, um, this is similar to how humans work in in in, uh, in our industry is there is a process that we're tracking over 10 days. There's multiple actors involved. The the actor at step seven may not need to know about this just yet, right? They're pulled in at the right time. And so, our agents with our kind of like long memory persistence plus the daily reflection on what is happening, um, reflect on where the the state of the world is at the moment. And they're able to pull in the right person at that time when it is when when there's a signal that that implies that that person must be pulled in. And all of this is, um, work that we have done to operationalize the context of how this industry works. But not just that, but how does Arca want it to work? And what are our principles of of how work happens in this industry? Um, and that is another advantage of us being sort of a a um, a not just a SaaS company. We're actually not a SaaS company. We are um, we are the firm ourselves. So, we can standardize the way this work even happens. Um, so that our agents can participate in standard ways that um, that work must happen.

</details>

### 对比托管 Agent 与外部金融服务

**>>**: 在本次大会早些时候，Anthropic 针对其托管 Agent（Managed Agents）基础设施举办了一场研讨会。如今很多环节甚至包括编排都在变得更加自动化。鉴于人类不一定再时刻参与其中这显然存在潜在风险，你预见到未来会采用这种功能吗？你有考虑过使用该技术来进一步自动化更多流程吗？

<details><summary>Original English</summary>

**>>**: So, um, earlier in the conference, uh, Anthropic uh, did a workshop about their uh, managed agents uh, infrastructure. And a lot of it uh, even the orchestration is becoming more automated now. So, do you foresee kind of using that type of functionality cuz it obviously it presents a danger in that the human is not necessarily always in the loop anymore. So, have you had any thoughts about using that technology to automate even more of the process?

</details>

**>>**: 我想说，我们非常看好来自 Anthropic 以及 OpenAI 等实验室的基础模型，但对依赖像托管 Agent 这样的产品则持保留态度。

因为对于托管 Agent 而言，其关键特性之一在于模型如何持久化并构建关于外部世界正在发生什么的记忆，以及它们赖以取得成功所需的全部业务操作知识。

因此，将这部分业务控制权让渡给他们是一种风险。掌握核心智能，才能赋予你对业务产生实质影响的能力。如果你将智能交给另一家提供商，你就会失去必要的一部分控制力，而这种控制力恰恰是你构建能够深度契合、高度定制并真正推动自身业务发展的产品所必需的。

<details><summary>Original English</summary>

**>>**: Um, I think we are very bullish on the models from uh, from Anthropic and and labs like OpenAI. Um, but less so on on taking a dependency on a product like managed agents. Um, because managed agents, one of their their key things is how the models kind of persist and and contribute memory as to what is happening in the world. Um, and all of the operational knowledge that they need to be uh, need to use to to be successful. Um, and so, letting them own that part of the business is kind of like um, a a risk because um, owning that is owning your intelligence is kind of uh, gives you the ability to impact the business. If you if you hand off uh, the intelligence to to another provider, you lose some of that control that you need to kind of like build something that is unique and tailored to your business to such a great degree um, that it can actually impact your business.

</details>

**>>**: 关于 Anthropic，他们最近也推出了金融服务，正在与许多不同的公司展开合作。你认为他们正在做的事情与你们的目标构成竞争，还是你认为两者截然不同？

<details><summary>Original English</summary>

**>>**: And just on Anthropic, they've they've also recently released uh, financial services. So, they're partnering with a whole bunch of different firms. Do you think what they're doing is kind of competitive to what you're trying to do or do you see them as different things?

</details>

**>>**: 是的，我认为 Anthropic 涉足我们这类行业，对整个行业而言是非常有力的认可。

但在我看来，一家拥有 AI 工具的服务公司，与一家生来即为 AI 原生的机构，两者有着极大的差别。

拥有 AI 工具的公司需要其用户去提示 Agent 以产出工作或完成任务。

但在 Arca，正如我之前所言，是 Agent 提示人类的次数多于人类提示 Agent 的次数。它是一项全天候 24/7 为他们运转的主动式服务，它以我们所期望的最规范方式、以及我们所追求的服务水准来驱动业务运营。这与一家仅仅配备了 AI 工具的公司相比，形态截然不同。

<details><summary>Original English</summary>

**>>**: Yeah, I think uh, I think Anthropic getting into our kind of industry is is very validating for for our industry. But the way I think about it is that it is very different to be an a a services firm that has access to AI tools versus a firm that was built to be AI native. The firm with AI tools requires their users to prompt the use the the agents kind of to to produce work or to do work. But here like I said in at Arca agents prompt people more than people prompt agents and it is a proactive kind of service that is running for them 24/7 and it's kind of like running the business in the most standard way that we that we expect at the level of service that we that we aspire to which looks very different if you're if you're a an AI AI sorry a company with AI tools.

</details>

### 沙箱环境与财务方案生成校验

**>>**: 明白。关于安全方面我们再多谈一点：你能解释一下在你们的流程中，有哪些部分是在沙箱（sandbox）内部运行的吗？在任何人采取行动之前，你们又是如何验证诸如财务计划变更等内容的？

<details><summary>Original English</summary>

**>>**: Yes. Yes. Okay. So a little bit more about on the security side. So can you explain like what in your processes runs inside a sandbox and how do you verify like a change to a financial plan you know before anyone acts on it? Um

</details>

**>>**: [清嗓子] 我们使用沙箱的方式是：沙箱只是我们 Harness 的一个组件。我们的 Agent 本身实际上并不在沙箱内部。它利用沙箱来卸载计算任务，并且我们构建了相应的系统，以确保沙箱内的代码能够安全地访问我们的数据。

我们拥有一套机制，可以将它编写的代码转换成我们预期的严格格式，然后丢弃原始代码，并在该格式到达后端之前为其注入安全护栏。

因此，我们允许 Agent 使用代码来查询我们的数据，这意味着它们可以按需聚合数据、清洗加工数据，并进行各种处理，以生成财务规划之类的产物。

在同一个沙箱内，它们会生成这些可以与客户共享的精美 Artifact。例如一份 PDF 文件，上面写着“这是您的财务规划，以及我们计划如何在财务上规划您的生活”。

一旦该产物生成，我们的校验器（verifiers）就会随即介入运行。由于这是从沙箱中产出的特定类型 Artifact，在它生成的那一刻，我们就会对其运行一系列不同的验证。

一部分是确定性检查，比如检查“你是否刚刚把原始账号放进去了？你不应该这么做”。我们能够通过确定性方式对此进行检查。

同时我们也会使用快速模型（比如体量较小的模型或 Jev）来分析是否存在可能导致该 Artifact 违规的内容。例如，你绝对不能在该产物中向客户承诺投资回报率。这也是我们在其具备可发布资格之前会检查的另一项内容。

关于这一点我想说的最后一点是，这样做实际上让我们的合规表现比完全由人工处理更好，因为在找出文本中哪怕最微小的违规表述方面，AI 是不知疲倦的。

因此，我们将继续加大这方面的投入，并在能力边缘对其进行严密约束。

<details><summary>Original English</summary>

**>>**: Yeah. So [clears throat] this the the way we use sandboxes is that the the sandbox is a one component of our harness. Our agent isn't actually inside of the sandbox. It uses the sandbox to offload computation and we've we've built systems to make it safe for code inside of that sandbox to access our data. Um so we kind of like have this thing which translates the code it wrote into a strict format that we expect throw away the code and you kind of instill guardrails on that format before it reaches your back end. So we allow the agents kind of to use code to query our data which means that they can like aggregate it and they can munch it they can kind of like work with it as they as they see fit to produce such a thing like a like a financial plan. Um inside of the same sandbox they produce this, you know, beautiful artifacts that we we can share with clients that has like it's a PDF of like here's your financial plan and here's how we're going to planning to kind of like approach your life uh financially. Um and once that is produced is where we run our verifiers. So, um it's a certain type of artifact that is produced from the sandbox. The moment that is produced we run bunch of different different verifications on it. Um some deterministic that check for presence of like, "Hey, did you just put like a raw account number in there?" You should not do that. Um so, deterministically we can check that. Um but also um fast models like um like the the smaller models or Jev um to analyze for presence of things that might make this artifact non-compliant. Like for example, you really should not be like um promising returns uh in in that artifact. So, that's another thing that we will check before it is um it is kind of a publishable. Um and the last thing I'll say on that is that um doing this is actually um makes our kind of compliance uh better than if humans were doing it because AI is tireless at at at finding even the smallest mention of a non-compliant um piece of writing in there. Um so, yeah, we'll continue to invest in in in more of that and kind of like uh constrain at the capability edges.

</details>

### 决策模型与金融严谨性校验

**>>**: 好的。你刚才提到了 Jev。你们已经开始在流程中使用决策模型（decision models）。除了 Jev 之外，你们还在关注哪些其他产品？

<details><summary>Original English</summary>

**>>**: Yes. Yeah, you uh mentioned Jev there. Um so, uh you have started to use decision models uh as part of your process. So, what other um products other than Jev are you sort of looking at?

</details>

**>>**: 是的，我们注意到的是，当模型在处理金融数据、回答需要金融专业知识的问题时，它们对自己所掌握的知识表现得极度自信。

举个小例子，模型会非常乐于直接使用 2025 年的税率档次来完成分析，并表示“好了，就是这样”。但这显然是不正确的。

因此，这是我们在 Harness 中使用决策模型的方式之一：当模型即将提出财务建议或执行任何需要金融严谨性的操作时，系统会进行检测，并促使模型去参考我们已验证事实的知识库（反映当今世界的真实情况），或者促使其使用网络搜索。

这正体现了掌控自有 Harness 的关键价值，它能让你执行类似操作，确保模型在至关重要的环节保持准确性。

<details><summary>Original English</summary>

**>>**: Yeah, so what we noticed is um when when models are um working with financial data, right? When they're answering questions that require financial knowledge, they are they're very confident in in uh in the knowledge that they have. So, a small example is that um models will very happily use the tax brackets from 2025 um to to come up with an analysis and be like, all right, that is it. Um, but that is that is obviously incorrect. And so, um, that is one of the ways in which we're using decision models in in our harness is to to check when the the model is about to make a financial recommendation or or anything any action that requires financial rigor will detect and will nudge the model to kind of use our knowledge base of verified facts about the world that is true today. And or use their kind of web search. So, kind of makes it um, this is kind of a a a point about the the harness and and owning the harness that lets you do things like this that that help your um, your models be be accurate where it matters.

</details>

**>>**: 那么在交易执行失败的恢复环节，你们是否会使用决策模型？这里是否有决策模型参与，还是说有其他途径让 Agent 重回正轨？

<details><summary>Original English</summary>

**>>**: And do you use um, decision models in for example, recovery if like a trade fails to execute? Is there a decision model involved there or is there another path to to get the agent back on track?

</details>

**>>**: 目前没有。这不是我们目前正在探索的用例。

<details><summary>Original English</summary>

**>>**: No, not today. That is not a use case that we're exploring today.

</details>

**>>**: 好的。如果某一步骤中的交易确实失败了，在你们目前的流程中 Agent 是如何恢复的？

<details><summary>Original English</summary>

**>>**: Okay. Um, so, um, you know, if a step a trade does fail for example, how does the agent recover at the moment in your process?

</details>

**>>**: 目前我们并没有让 Agent 进行自主交易。现在的模式是：由 Agent 提议我们执行交易。

<details><summary>Original English</summary>

**>>**: So, um, so, at the moment, we are not doing autonomous trading with with agents. It is very much a um, the agents will propose that we we make trades.

</details>

**>>**: 我明白了。

<details><summary>Original English</summary>

**>>**: >> I see.

</details>

**>>**: 这完全取决于我们的专家来判断这是否是该进行的正确交易并由其执行该交易。

<details><summary>Original English</summary>

**>>**: >> Um, and it is fully up to kind of our our experts to figure out if that is the right trade to be making and to execute the trade.

</details>

### 评估与反馈闭环：从人类修正到 Prompt 迭代

**>>**: 好的。沿着这个思路，你的 PPT 幻灯片上提到，员工的每一次修改或取消都会附带一个“原因（Why）”，并转化为一个评测项（eval）。那么这些反馈是如何反馈回系统并转化为可衡量的改进的？

<details><summary>Original English</summary>

**>>**: Okay. So, uh, on the on the same sort of uh, line of that, um, your slides um, say that every staff edit or cancellation comes with a Y and come it becomes an eval. So, um, how does that feedback uh, get turned back into uh, the system as a measurable improvement?

</details>

**>>**: 是的。这同样是我们作为自身业务经营者而非单纯 SaaS 公司的优势之一：我们有能力要求他们必须向我们提供反馈。

至于我们将反馈闭环转化为改进的方式，正如你所预期的那样：所有这些反馈都会被导入到一个数据存储中，将该反馈与产生该行为的 Agent Trace 关联起来。

我们能够获取该 Trace 并将其与反馈放在一起；每晚我们会运行一个流程，收集现实世界中运行的 Agent 所产生的 Trace，并在其上运行一个 Meta-Agent，由其向我们的 Harness 提出改进建议。例如哪些工具具有误导性、哪些地方发生了报错，或者我们的知识库中缺少了哪些知识。

它们会将这些信息呈现给我们，然后我们便能对其进行改进。目前在实际发布 Prompt 变更之前，我们依然让人类工程师参与在闭环中。

我注意到，如果你完全放手让 Agent 自己修改 Prompt，它们会做出非常糟糕的修改。每一个细小的修补都会变成充斥整个 Prompt 的内容，它们无法保持 Meta 视角，也无法将修复泛化为具有通用性的 Prompt。

因此，我们通过产品收集直接反馈，并将其作为一等公民级的产品功能来收集评测数据，进而转化为系统改进。

<details><summary>Original English</summary>

**>>**: Yeah. Um, that is another one of the advantages of us um, being the business and not a SaaS company um, is that we have um, we have the ability to have to require them to give us feedback. Um, and yeah, the way that we loop the feedback back into improvements is something that you would um, you would expect is all of that feedback gets piped into um a data store that um that couples that feedback with the trace of the agent that produced it. Um and so we're able to kind of like take that take take that trace um put it put it next to the the feedback and every night we run this process where we take collect traces from uh the real world from our agents in the wild and run run a meta agent on top that suggests changes to our harness. So maybe tools that were misleading or um things that were were errored or there's missing knowledge in our knowledge base um and they'll surface this information to us and then we'll we'll be able to kind of improve it. Um today we still have a a human in in like a human engineer in the loop before we actually ship a prompt change. Yes. Um I've noticed that uh that agents will will make really nasty prompt changes if you leave them leave them do it. Um every little fix becomes the whole prompt. Hm. Uh and they're they're unable to stay meta and kind of generalize uh the fix into into a prompt that generalizes. Um so but yeah we have we have feedback loops from our product that we collect directly as first class product features to collect evals and turn them into improvements.

</details>

**>>**: 嗯。

<details><summary>Original English</summary>

**>>**: >> Hm.

</details>

### 企业业务知识转化为 Agent 上下文

**>>**: 好的。你在演讲中还提到了将“一家公司的运作知识”转化为“Agent 上下文”，这实际上也是很多前线部署工程师（Forward Deployed Engineers）极力想做的事，即把组织的内部知识转化为 Agent 可执行的内容。在技术层面，你们公司是如何实现的？你们又是如何保持其更新的？

<details><summary>Original English</summary>

**>>**: Okay. Um and you also mentioned in your presentation about uh turning knowledge of how a firm works into agent context which is actually something a lot of forward deployed engineers uh do try to do is is turn an organization's kind of internal knowledge into uh actionable things for agents. Um what does that look like uh for your company technically and and how do you sort of keep it up to date?

</details>

**>>**: 是的。我们拥有一个由文件形式呈现的知识库，它在系统中表现为各类文件。

我们保持其更新的方式是将其交给我们的专业人员来进行维护和更新。这是我们产品中的一项一等公民功能：在界面的左侧有一个名为“知识（Knowledge）”的标签页，其中包含了我们 Agent 所使用的完整运营上下文。

当 Agent 处理各项事务时，它们能够引用这些知识。这就形成了一个闭环：比如我们发现某些知识是不正确的，这会在我们的 Trace 分析中暴露给我们；又因为它是产品本身的一部分，相关人员可以直接进入并直接编辑该技能/知识。这就是它的运作方式。

<details><summary>Original English</summary>

**>>**: Yeah. So we have um a knowledge base of um of files that is represented as as um as files and um the way we keep that up to date is we we've handed it to our experts to curate and update. So it is a a first-class um feature in our product. So, on the left-hand side there's a tab called knowledge, which has the full operational context that our agents are using. And as they they work on work on things, they're able to cite knowledge. And so, it kind of like creates this this loop of like, oh, we notice that the knowledge is incorrect. And we that gets surfaced to us in our trace analysis. And because it is a a part of the product itself, people are able to go in and like edit the edit the skill directly. That's how it kind of works.

</details>

### 实证案例：细节洞察与主动式合规服务

**>>**: 好的，明白。你之前提到你们是通过顾问员工向客户提供这些服务的，我猜你们公司内部拥有一个财务顾问团队。那么你能否给我们举一个实际客户的例子：该客户通过 Agent 系统在投资或税务等方面获得了可衡量的改善？以及在 Agent 架构中具体是哪些技术细节帮助该客户获得了如此良好的结果？

<details><summary>Original English</summary>

**>>**: All right. Okay. So, you know, you mentioned you're you're you're actually offering these services to to clients through, you know, I'm assuming you have a staff of financial advisers in your firm. So, can you maybe give us an example of some, you know, a client that you've had that's had a measurable improvement in their investments or taxation or whatever through the agent system and and maybe some sort of details about what in the agent architecture kind of helped that client, you know, get such a good return?

</details>

**>>**: 好的，我给你举一个最近的例子。

这个人当时还不是我们的正式客户，但他正处于即将成为客户的阶段。因此我们拿到了他所有的文件、账单声明、现有投资组合等等。而这个人之前已经有合作的财务顾问了。

当他与我们会面时告诉我们：“看，我已经有这位顾问了，他们收取我 1,500 美元的服务费，而且对我并不怎么积极响应。所以我才来和你们聊聊。”

于是我们的 Agent 通读了所有这些文件，对其进行了分析，分析了该客户陈述的个人财务目标；同时它们也分析了关于这位现有顾问是谁的账单陈述，以及该顾问向其收取了多少费用。

随后 Agent 发现该顾问向他收取了一些他自己并不知情的费用，并将此结果呈现给客户。这不仅让他意识到自己被多收费了，而且还让他意识到该顾问甚至并不是受托人（Fiduciary），意味着对方没有在法律上以客户的最佳利益行事的义务。

正是这种细致入微的洞察力，体现在我们的 Agent 对整体财务全貌的分析之中。如果我们没有这套系统，这是不可能做到的。

关于我们的 Agent 所展现的主动性，还有许多其他例子：比如某位客户即将面临某个截止日期，或者他们面临错失 RMD（最低必要提款额）的风险，等等。这类事情单靠人类在大规模扩展下是很难保持追踪的，但在 Arca，这正是我们 Agent 的默认内建行为。

<details><summary>Original English</summary>

**>>**: Yeah, I'll give you a recent example. This is this person wasn't a client yet, but they were they were at the the point of becoming a client. So, we had all of their their documents, their statements, their current investments, et cetera. And this person was already working with an adviser. And so, they meet with us, they tell us that, hey, I have this adviser already. They're charging me $1,500 for for their services, and they're not very responsive to me. So, I'm I'm chatting with you. And so, our agents have kind of like, you know, read through all of those documents, they've analyzed them, they've analyzed what the person's goals are that they state, right? They've also analyzed the statement of like who this current advisor is, uh, right? And how much they're they're charging them. And, um, they discover that that there is there are fees that this person was charging them that they weren't aware of. Uh, and surfaces this it to them, um, and kind of like makes them not only aware of, um, of the fact that they're being overcharged, but also aware that that person wasn't even fiduciary. Um, so they're not uh, obligated to act in their interests. So, it is this is the sort of like attention to detail that our agents bring about in in when they're analyzing a financial picture, um, that that sort of, um, would not have been possible possible if we didn't have, um, have these. There's several examples of, um, proactivity, uh, that our agents kind of like produce of like someone has a deadline coming up. Or they're at risk of missing their RMD or, um, that kind of thing. And so, um, this is difficult at scale for humans to keep track of, but it is the the default behavior of, uh, of our agents at at Arca.

</details>

**>>**: 好的，太棒了。这确实是一个非常好的总结点。非常感谢 Aman 接受我们的采访。

**>>**: 感谢邀请。

<details><summary>Original English</summary>

**>>**: Yeah. Wonderful. Well, that's probably a good, uh, point to stop at. So, thank you very much, Aman, for joining us.

**>>**: Thank you for having me.

</details>