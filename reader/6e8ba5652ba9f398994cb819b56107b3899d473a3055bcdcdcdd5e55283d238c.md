---
author: AI Engineer
date: '2026-10-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=oP2WLFpMoDY
speaker: AI Engineer
tags:
  - ai-agent
  - long-horizon-agent
  - event-driven-architecture
  - workflow-automation
title: Arca：由长周期 Agent 驱动的 AI 原生金融服务公司
summary: Arca 的 AI 负责人 Aman 介绍了他们如何构建由长周期（Long-Horizon）Agent 驱动的 AI 原生金融服务公司。金融业务跨越数天、多方参与且断续交接，Arca 通过外部信号监听系统、业务上下文、Agent 工具框架与长效记忆，将人类移出关键路径，让 Agent 主动调度员工完成闭环，实现通过引导 Agent 来引领整个业务运转。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Arca
products_models: []
media_books: []
status: evergreen
---
### Arca 与长周期 Agent

>> 我叫 Aman。我在 Arca 负责 AI。今天我想和大家聊聊 Arca 那些支撑并运转我们业务的长周期（long-horizon）Agent。

<details>
<summary>Original English</summary>

>> My name's Aman. Uh I lead AI at Arca. Um and today I'm going to talk to you about Arca's long horizon agents that run our business.
</details>

Arca 是一家 AI 原生（AI native）服务公司。我们为客户提供金融服务，比如财务规划、税务规划、资产管理和投资建议。

<details>
<summary>Original English</summary>

Arca is an AI native services firm. We provide our clients with financial services like financial planning, tax planning, asset management, investment advice.
</details>

我们服务于各类客户。他们当中有像科技高管这样积累了大量财富、需要切实规划来实现提早退休的人；也有在新罕布什尔州赚到了人生第一个一百万美元、终于想买下那套房子的家庭。

<details>
<summary>Original English</summary>

Um and we serve a range of clients. Some of them are like technology executives that um have amassed a lot of wealth and need a real plan to retire early. But also that family in New Hampshire that made their first million dollars and and want to buy that house finally.
</details>

我刚才提到我们是“AI 原生”的。如今这个词有很多种定义，被严重滥用了。但我们所说的 AI 原生，是指由 Agent 来运转我们的业务。

<details>
<summary>Original English</summary>

Um I said we were AI native. There's a lots There's lots of definitions of this this term these days, very overused. But what we mean by AI native is that agents run our business.
</details>

这并不是指它们站在某个副驾驶（co-pilot）的角落辅助业务，而是由它们去执行那些决定我们业务为客户交付最终成果的决策。

<details>
<summary>Original English</summary>

Not that they assist the business from some co-pilot corner. They They execute the decisions that shape the outcomes that our business has for our clients.
</details>

### 金融服务中的长周期工作流

了解这个行业里的工作形态是很有意思的。在金融服务领域，工作更多是长周期的（long horizon），而非长时间持续运行的（long running）。我的意思是，这并不是 Agent 一刻不停地消耗 token 算上数小时或数天，对吧？

<details>
<summary>Original English</summary>

Work in this industry, it's interesting to know what it looks like. In financial services, the work is more long horizon and less long running. And what I mean by that is this is less agents grinding tokens for like hours or days on end, right?
</details>

它更多是针对一个跨越 10 天的客户目标。它具有很强的走走停停（stop-start）特性，中间牵涉许多参与方、诸多决策点以及大量工作交接。

<details>
<summary>Original English</summary>

This is more one client goal that spans 10 days. It's very stop-start. There's many actors in between, many decision points, many hand-offs.
</details>

最终那个目标大概在 10 天后落地。这就是我们正在处理的那类工作。

<details>
<summary>Original English</summary>

Um and ultimately that goal lands like 10 days later. That is the kind of work that that we're working on.
</details>

举个例子：Jane 是我们的客户，相当富有，但在 4 月 15 日有一笔巨额税单，对吧？因此，我们要协助 Jane 搞清楚如何以最合算、最省税的方式筹措这笔现金来缴纳税款。

<details>
<summary>Original English</summary>

And so here's an example. Jane's our client, fairly wealthy, but has a big tax bill. Oh. Um has a big tax bill in uh in in April 15th, right? So, we're going to help Jane figure out what is the most tax optimal way for this cash to be to be raised to pay the tax bill.
</details>

这里面会有顾问来负责所有的账单分析，并分析如何实现税务最优。

<details>
<summary>Original English</summary>

So, there's the advisor that will do all of the the statement analysis and the analysis of of how to make this tax optimal.
</details>

会有交易员去实际变现这些资产。资产变现本身需要数天来清算结算，接着运营人员会介入并触发 ACH 转账，转账本身也需要几天才能到账。

<details>
<summary>Original English</summary>

There's the the trader that would actually liquidate the the assets. They the assets themselves will take like days to settle, and then the ops people will come in and kind of like trigger the ACH. That will itself take days uh to land.
</details>

这就是我所说的这个行业里的工作，需要数天才能完成交割。

<details>
<summary>Original English</summary>

So, this is kind of the work I'm I'm talking about in this industry, which takes like days to settle.
</details>

当然，如果你为多位客户规模化地处理这些事务，我们机构完成这类工作所耗费的时间就会呈指数级激增，对吧？

<details>
<summary>Original English</summary>

And of course, if you do this at scale for several several clients, the amount of time our firm takes to do this sort of work exponentiates, right?
</details>

### 从端到端接管长周期交付

所以在 Arca，我们采取了截然不同的方法。需要说明的是，Arca 并不是一家 SaaS 公司。

<details>
<summary>Original English</summary>

So, at Arca, we took a different approach. It's helpful to know that Arca is not a SaaS company.
</details>

我们不向其他企业或机构销售软件，我们自己就是这家金融机构。我们是一家应用型 AI 公司，刚好在这个行业里经营着一家服务企业。

<details>
<summary>Original English</summary>

We are not selling software to other businesses, to other firms. We are the firm. We're an applied AI company that happens to be running a services business in this industry.
</details>

我们采取的做法是：好，我们要让 Agent 端到端全权负责这整个长周期交付成果。

<details>
<summary>Original English</summary>

And so, the approach we took was, all right, we're going to have agents own this whole long horizon outcome end to end.
</details>

为此，我们给它们配备了几个关键组件，我先给大家提前透露一下。我们赋予它们来自外部世界的信号，让它们时刻感知正在发生的事情。因此，那封邮件会由 Agent 来阅读。我们给它们全部的业务运营上下文，告知它们面对那封邮件该如何处理、这个行业在面对这种税务情况时该怎么做，对吧？

<details>
<summary>Original English</summary>

And for that, we gave them a couple of key components, I'll give you a sneak peek of. We gave them signals from the external world that keeps them really aware of what is happening. So, that email will be read by agents. We give them all of our operational context on what to do about that email. What does this industry do with this situation of taxes? Right?
</details>

我们为它们配备了一个工具框架（harness），提供所需的全部工具与安全防护栏（guardrails）；更重要的是，提供在长周期时间内保持的持久化记忆，以便推进这项工作。

<details>
<summary>Original English</summary>

We gave them a harness that gives them all of the tools and uh the guardrails, and more importantly, persistence of memory over the the kind of long horizon period to carry that work out.
</details>

当然，我们还赋予了它们与人类协作的能力。

<details>
<summary>Original English</summary>

And of course, we gave them the ability to collaborate with people.
</details>

因此，有了 Agent 的参与，工作时间被大幅压缩，因为我们所做的仅仅是将人类从这项工作的关键路径（critical path）上移除了。没有人需要在这几天时间里全程照看这个目标，Agent 会盯紧它。在本次演讲中，我很想向大家介绍我们具体是如何做到的。

<details>
<summary>Original English</summary>

So, that work with um with agents compresses a lot because all we did was we took humans out of the critical path of of this work. Nobody has to babysit this this uh this goal over days. Agents are are on it. In this talk, I'd love to describe to you how we actually do that.
</details>

### 信号系统与协作空间

让我们顺着这封邮件的轨迹来看。Jane 欠了 10 万美元的税款。这封邮件就像我们平台中的许多其他信号一样，会被后台 Agent 读取。比如我们机构拨打的电话、接收到的文件、召开的会议、来自托管机构的事件、正在发生的市场波动——这些全都是我们的后台 Agent 为推进工作而持续评估的信号。所以，这封邮件就是其中一个信号。

<details>
<summary>Original English</summary>

Let's follow the journey of this email. Jane owes on the $100,000 for taxes. This email, much like many other signals in our in our platform, will be will be read by background agents. So, there's like phone calls our firm is making, there's documents that are coming in, there's meetings being had, there's events coming in from our custodian, there's market movement that's happening. These are all signals that our background agents are continuously evaluating to progress work. So, this email is one of those signals.
</details>

当信号被 Agent 接收后，它们就会着手投入工作，对吧？

<details>
<summary>Original English</summary>

And when the signal is is by agents, they actually get to the work, right?
</details>

我们有一个 harness 为它们提供专业知识，让它们知道该如何应对这种情况。它们拥有深度的客户记忆，所以它们知道：“嘿，千万别动 Jane 持有的苹果股票仓位，因为她大约 8 个月前在一次通话中提到过这个要求，对吧？”当然，我们还配备了沙箱环境，用于执行此项分析所需的全部财务计算。但我认为，当今各类 harness 正在趋向于统一的标准形态，因此 harness 外部所发生的事情才更有意思。

<details>
<summary>Original English</summary>

Um we have a harness that gives them the knowledge to know what to do about the situation. They have deep client memory, so they know, "Hey, let's never touch Jane's Apple position cuz uh she said that in a call like 8 months ago, right?" Um we of course have a sandbox for all of the financial computation that needs to happen for this analysis. Um but largely, I think harnesses today are are coalescing on a standard shape. So, um it's more interesting what happens outside of outside of this harness.
</details>

当它们完成这项工作后，会生成一份方案。

<details>
<summary>Original English</summary>

So, after they've done the work, they produce this plan.
</details>

这份方案本身脱离了人是无法执行的。因此在我们的产品中，Agent 会搭建一个协作空间，将这份方案展示出来。你可以与 Agent 对话沟通，借此了解方案的进展；多个人都可以同时与该 Agent 交流。更重要的是，这个空间也是它们在需要人类执行某项工作时拉入人类的地方。以当前案例而言，我们可以在这里审批方案，并批准向 Jane 发送邮件。

<details>
<summary>Original English</summary>

This plan by itself cannot be executed without people. So, in our product, we build a space, agents build a space, where they put out this plan, and there's you can chat with the agent to like kind of know what's happening with the plan. There's mult- multiple people that can be chatting with the agent. And more importantly, this space is where also they pull people in when they need people to execute some work. So here in this case, we would approve uh the plan and the email out to Jane.
</details>

随后便是一整套流程流转：Jane 回复了吗？她的回答对我们制定的方案意味着什么，对吧？以及在整个长周期工作中必须解答的所有其他问题。

<details>
<summary>Original English</summary>

And then there's this whole dance of has Jane replied? What does her What does her answer mean for the plan that we had, right? And then all of the these other questions that will have to be answered throughout this whole like long horizon work.
</details>

在 Arca，我们当然不会安排人员去时刻看守。因此，我们让 Agent 去监视整个世界的动态。

<details>
<summary>Original English</summary>

At Arca, we were like, of course we're not going to have people babysitting it. So we let our agents watch the world.
</details>

这样人类就不必去盯了，对吧？我们赋予了它们注册关注我们世界中发生之任何事情的工具。因此它们能够声明：“当 Jane 回复时通知我”，“当那笔 ACH 转账到账时通知我”，对吧？这背后依托的是我们后台的信号系统，Agent 会在其中将信号路由给对该信号感兴趣的特定 Agent。

<details>
<summary>Original English</summary>

So people don't have to, right? So we give them tools to be able to register interest in anything happening in our world. So they're able to say, let me know when Jane responds. Let me know when that ACH lands. Right? And this is powered by our signal system in the in the background where agents are routing uh signals to agents that are interested in it.
</details>

当然，如果预期的信号一直没有出现，Agent 也可以按设定的时间表自行唤醒，以跟进工作轨迹。

<details>
<summary>Original English</summary>

And of course, if the signal never lands, agents can like wake themselves up on on a schedule as well to keep track of work.
</details>

但现实世界是非常混乱繁杂的，对吧？大家在等待那封邮件，但 Jane 始终没有回复邮件。假设我们在现实中碰到了她，并了解到了一些会影响该方案的信息。

<details>
<summary>Original English</summary>

But then, of course, the real world is very messy, right? People are waiting for that email, but Jane never responds to that email. Say we we meet her in person and we learn some information that affects the plan.
</details>

于是工作人员进入系统，在我们的 UI 界面中录入了这条信息。

<details>
<summary>Original English</summary>

So the person goes in and they they add this information into our UI.
</details>

然而，在我们的 UI 中添加信息或处理工作的这一动作本身，同样是一个会唤醒 Agent 的信号。事实上，当员工在我们的产品中工作时，重新安排一次日历日程就是一个信号；将某个任务标记为已完成也是一个信号。

<details>
<summary>Original English</summary>

But this act of adding information or doing work in our UI is also a signal that will wake up an agent. In fact, when people work in our in our product, when they reschedule a calendar event, you know, that's a signal. When they mark a task complete, that is a signal.
</details>

因此，该系统让我们随着工作的推进，既能洞悉外部世界发生的一切，也能感知内部系统的一举一动，从而让我们的 Agent 能够真正参与到业务工作中。

<details>
<summary>Original English</summary>

So this system lets us be both aware of everything happening in the external world and the internal world as work is progressing so our agents can participate in work.
</details>

当然，Agent 之间也会彼此通信。因此，由后台 Agent 读取的这个信号可以让它通知另一个 Agent，以便后者更新该空间并指出：“嘿，我们现在只需要 8 万美元，而不是 10 万美元了。”工作内容便因为这些信号发生了变更。

<details>
<summary>Original English</summary>

And of course, agents are communicating with each other as well. So, this signal read by a background agent will let it notify another agent about this so that it can update the space to say, "Hey, we just need a need $80,000 instead of the $100,000." So, the work has changed because of because of these signals.
</details>

这套故事的最后一块拼图，是 Agent 能够在正确的时机拉入正确的人选。

<details>
<summary>Original English</summary>

And the last piece of the story is that agents are able to pull in the right people at the right time.
</details>

左侧的 Agent 读取了我们的业务运营上下文后得出结论：“好的，接下来的步骤是拉入负责交易这些资产的人员。”于是，那个人现在领到了一个任务，被接入参与到这项长周期工作中。

<details>
<summary>Original English</summary>

So, uh the agent on the left has read our operational context to be like, "Okay, this the next step here is to pull in the the person that trades these uh these assets." And so, that person now gets a task and gets pulled in to participate in this long-horizon work.
</details>

### 长周期工作的四大原语

退一步从整体来看，我们所做的，就是为我们的 Agent 赋予了驱动长周期工作的原语（primitives）。人们在工作中通常做什么？他们需要感知正在发生的事情，因此我们构建了这套高强度的信号系统，让 Agent 保持感知。

<details>
<summary>Original English</summary>

What we've done overall, if you take a step back, is we've given our agents the primitives for driving long-horizon work. What do people do at work, right? They They need to stay aware of what is happening, so we've built this very intense like signal system for our agents to be aware.
</details>

他们需要知道下一步该做什么，所以我们向它们提供了所有的业务运营上下文。

<details>
<summary>Original English</summary>

They need to know what to do next, so we've given them all of this operational context.
</details>

他们需要开展工作，因此我们的 harness 让它们能够实际执行工作并保持追踪，对吧？它拥有长效持久的记忆系统来维护状态，并且能够在正确的时机拉入正确的人。

<details>
<summary>Original English</summary>

They need to do the work, so it's our harness that lets them actually perform the work and keep track of it, right? It's long-persistence um memory systems that that hold the state. And bringing in the right people at the right time.
</details>

表面上看这是一个相当简单的想法，但它会产生大量的突现复杂性（emergent complexity）。

<details>
<summary>Original English</summary>

This is a pretty simple idea on the face of it, but there's a lot of emergent complexity.
</details>

你可以想象，在任何时间点都会有数百个此类信号涌入，任务被分配到员工的手头上，人员被拉入介入，后台 Agent 在相互通信，对吧？

<details>
<summary>Original English</summary>

You can imagine at any point there is hundreds of these signals coming in, and they are, you know, tasks tasks are being added on people's plates, they're being pulled in, background agents are communicating with each other, right?
</details>

所以在过去的 6 个月里，我们一直在致力于将这个系统打磨得极其出色。

<details>
<summary>Original English</summary>

So, over the last 6 months, we've we've been working on getting this system to be really good.
</details>

我们一直在消除所有的上下文鸿沟，以确保 Agent 拥有充分的感知。我们一直在提升任务指派的精准度，确保在正确的时机拉入正确的人。未来需要跟进的工作被记录在 Agent 的记忆中；当前可以执行的工作则转化为任务，对吧？因此，我们同样一直在打磨自身跨越长周期维持状态的能力。

<details>
<summary>Original English</summary>

We've been closing all of our context gaps so that agents are fully aware. We have been working on the precision of tasks, so pulling in the right person at the right time. Work that needs to be tracked for the future is tracked in the agent's memory. Work that is doable now becomes a task, right? So, we've been working on on our ability to hold state over long horizons as well.
</details>

而且由于我们本身就是业务机构，而不仅仅是一家 SaaS 公司，我们从一开始就在改变并规范化公司内部开展工作的方式，并将这些业务运营上下文沉淀到 Agent 的状态中。

<details>
<summary>Original English</summary>

And because we are the firm and not just a SaaS company, we've been changing and standardizing how work happens in the firm in the first place and operationalizing that context into our agent's state.
</details>

更因为使用我们产品的就是我们自己的同事，我们能从他们那里收集到详尽的推理逻辑，这些都成为了我们系统持续改进的评测基准（evals）。

<details>
<summary>Original English</summary>

And because these are our colleagues that use our product, we collect rich reasonings from them that become evals for for our system to improve.
</details>

### 让 Agent 提示人类，引领业务运转

那么，这里可能会有一个疑问：为什么要这么做？这能释放出什么价值？这里的核心启示是什么？对我们来说，这就是我们的整套立论基础：

<details>
<summary>Original English</summary>

So, I guess there's there's a question to be asked here, like why do this, right? What does this unlock? What is the takeaway here, right? For for us, this is our whole thesis.
</details>

那就是我们希望我们的平台做到极致的 AI 原生，由 Agent 来驱动业务，由 Agent 来运转业务。由它们来做出决定我们交付成果的决策。

<details>
<summary>Original English</summary>

Is that we want our platform to be so AI native that agents drive the business. Agents run the business. They they are making the decisions that shape our outcomes.
</details>

所以在 Arca，当员工登录系统时，他们看到的是 Agent 已经为他们准备好的任务列表。Agent 已经读过了那封邮件，看过了提交进来的文件，完成了大约 90% 的前期工作，仅在需要你采取行动时才将你拉入。

<details>
<summary>Original English</summary>

And so, at Arca, when people log in, right, they see a list of tasks that have been prepared for them by agents. They've already read that email. They've like looked at the document that came in. They've done like 90% of the work and they're pulling you in just when it's time for you to act.
</details>

因此，构建这个系统让我们在 Arca 达到了这样一个状态：Agent 提示（prompt）人类的频次，超过了人类提示 Agent 的频次，从而让我们的 Agent 能够驱动我们机构所开展的工作。

<details>
<summary>Original English</summary>

So, building this system lets us get to a point where at Arca, agents prompt people more than people are prompting agents, which lets our agents drive the work that our our firm does.
</details>

而正因为 Agent 在驱动公司所开展的工作，Agent 便能够驱动整个业务。

<details>
<summary>Original English</summary>

And because agents are driving the work the firm does, agents can drive the business.
</details>

举个例子：还记得 Jane 发给我们的那封邮件吗？这其实算是一次小小的失误，因为我们本应从一开始就主动出击，Jane 根本不需要主动发这封邮件。

<details>
<summary>Original English</summary>

Let me give you an example. Remember that email that Jane sent us? This is a bit of a failure, right? Because we should have just been proactive about this in the first place, right? So, Jane should never have to send this email.
</details>

所以假设在我们这个 AI 原生企业里，我们确立了一个新目标。我们的新目标是“主动性”（proactivity）：每年 1 月，为每位客户准备好其税务规划情况，并在任何人开口询问之前主动与他们沟通。这是我们企业要去推行的一个全新业务目标。

<details>
<summary>Original English</summary>

So, say at you know, our AI native business, we take on this new goal. Our new goal is proactivity. Every January, prepare each client's tax situation and proactively reach out to them before anyone even asks. This is a new business goal for our business to drive.
</details>

在一座 AI 原生机构中，我们所要做的，仅仅是把这个目标纳入到我们 Agent 的目标集合中。

<details>
<summary>Original English</summary>

And in an AI native firm, all we have to do is make this goal part of our agents' set of goals.
</details>

因为它们已经具备了通过协同人员来为业务推进工作的原语，它们便开始驱动这个目标的实现。就这样，在 1 月份，这些分析工作便自动完成，附带完整方案、支持一键批准的邮件便呈现在我们用户的待办列表里。

<details>
<summary>Original English</summary>

And because they have the primitives to be able to drive work through people for the business, they start driving this goal, and just like that, you have you have these analyses being done in January, and these these one-click approval emails with the full plan for every client showing up on our users' plates.
</details>

由于员工也认同主动性的目标，他们只需一键批准，便能推动业务迈向这个全新的成果。

<details>
<summary>Original English</summary>

And because they're aligned with the goal of proactivity, they can one-click approve and drive the business towards this this new outcome.
</details>

所以，我认为这就是一家使用 AI 工具的公司与一家 AI 原生公司之间的关键区别：

<details>
<summary>Original English</summary>

So, this is sort of I think the key difference between a a company that uses AI tools versus a a company that is AI native.
</details>

在 AI 原生公司中，当你可以通过引导你的 Agent 来掌控你的业务时，你便知道自己真正打造出了一家 AI 原生公司。

<details>
<summary>Original English</summary>

In an AI native company, you know you've built one when you can steer your business by steering your agents.
</details>

这就是我们在 Arca 的雄心壮志。我们正在招贤纳士，欢迎访问我们的网站。如果你有兴趣攻克这类难题，请随时与我联系。感谢大家的聆听。

>> [掌声]

<details>
<summary>Original English</summary>

And that is our ambition at at Arca, and we are we're hiring. Um so, please uh please check out our website. Please reach out to me if this is something that you you're you're interested in working on these sorts of problems. And um thank you for listening.

>> [applause]
</details>