---
author: AI Engineer
date: '2026-10-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mJ7q8CuVmbw
speaker: AI Engineer
tags:
  - ai-agent
  - durable-execution
  - workflow-orchestration
  - production-readiness
title: 我们信任每天都在崩溃的 AI Agent：Temporal 揭示从原型到生产的四大鸿沟与持久化执行方案
summary: Temporal 开发者布道师 Shay 结合第二届《开发者现状调查》对 554 位工程师与技术负责人的调研数据，指出了 AI Agent 落地生产面临的四大差距：日常使用与生产交付的脱节、高信任度与频繁系统崩溃的矛盾、大企业面临的长达数月的部署周期，以及可观测性与系统恢复能力间的断层。演讲通过支付反欺诈工作流的现场演示，阐述了如何利用 Temporal 的持久化执行机制保证状态留存与失败恢复，避免重复消耗 Token 并降低故障成本。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Shay
companies_orgs:
  - Temporal
  - KPMG
products_models:
  - Qwen
media_books: []
status: evergreen
---
### 演讲开场与背景

好的，大家好。我是 Shay，Temporal 的开发者布道师。我完全看不到台下的人，所以要是你们冲我喝倒彩或者想扔番茄什么的，我可一点都不知道。好的。

<details>
<summary>Original English</summary>
[music]

>> All right. Hi everyone. I'm Shay. I am a developer advocate at Temporal. I cannot see anyone in the room. So if you boo me or like want to throw tomatoes or something, I I will have no idea. Um All right.
</details>

哎呀，翻页笔不太好使。好了，看来我今天是用不上翻页笔了。

<details>
<summary>Original English</summary>
Oop. Clickers are difficult. There we go. I guess I'm not using a clicker today.
</details>

### Agent 的普及与金融行业的采用现状

说到 Agent，它们现在无处不在。我猜如果你们坐在这个房间里，大概率正在构建 Agent 或者正准备交付 Agent，对吧？是的。

<details>
<summary>Original English</summary>
So agents, they are everywhere. I'm guessing if you are in this room, you are probably building an agent or shipping an agent. Does that sound about right? Yeah.
</details>

去年毕马威（KPMG）做了一项调查，根据他们的 Agentic AI 报告，2025 年我们已经见证了 3 万亿美元的企业生产力提升。在这 3 万亿美元中，金融服务业确实处于领先地位。94% 的金融科技公司表示，AI 是他们业务运作的核心；他们已经认定 AI 不仅仅是一个辅助项目，而是业务不可或缺的一部分——这就是我们的运作方式。然而，这些团队中有 62% 因可靠性问题而蒙受了可量化的时间或收入损失。所以，决定“我们要采用 AI”并不等同于“将其交付到生产环境”。这两者之间显然依然存在着一条鸿沟。

<details>
<summary>Original English</summary>
Um so last year KPMG conducted a survey and they figured out that we have seen $3 trillion in terms of corporate productivity gains in 2025 and that's from their agentic AI report. Uh and from that $3 trillion, it's really fin financial services that are leading the way here. So 94% of fintech are saying that AI is core to how their businesses operate and they've decided that AI isn't just a side project, but but it's like it's part of the business now. Like this is how we operate. Uh and 62% of those teams lose measurable time or revenue to reliability issues. So they haven't you know, deciding that AI is something we're doing isn't necessarily the same as shipping it. There's definitely still a gap between those two things there.
</details>

深入分析来看，部分原因在于工作流本身的形态。金融业务依赖的是**长生命周期工作流（long running workflows）**，而不是孤立的单个模型。以他们的业务流程为例，比如贷款发放、KYC 与反洗钱（AML）审核、欺诈审查、打款支付等。其中的每一个流程都会跨越多个工作日、多个系统，而且通常涉及多个人员。

<details>
<summary>Original English</summary>
Now to break it down, part of this is the shape of the work. Finance runs on long running workflows, not not on individual models. You know, for some examples of their process, you can think of loan origination, KYC and AML, fraud review, paying people. Each of these processes spans multiple days, multiple systems and usually multiple people.
</details>

因此，这里面包含非常非常多的步骤、非常非常多的系统，并且涉及到真金白银。所以，他们绝不能犯任何错误。现在想象一下，我们要把一个 Agent 放到这样一个流程的中间。

<details>
<summary>Original English</summary>
Uh so there's many many steps. There's many, many systems, and there's real money involved. So, they can't mess anything up. And now imagine that we're going to go ahead and put an agent into the middle of that process.
</details>

### 调研背景与受访人群画像

在 Temporal，我们想要了解实际情况究竟如何。于是我们开展了一项调查。这是我们第二年开展这项《开发者现状调查》（State of Development Survey）。我们调研了 554 位目前正在积极使用 AI Agent 的工程师和技术管理者。本演示幻灯片上的每一个数字，要么来自该报告，要么会在左下角注明我所引用的具体报告出处。首先，我们可以看一下本次调查的人群画像。48.4% 的人拥有 11 年以上的行业从业经验，所以我们面对的并不是业余爱好者。另外三分之一的受访群体也拥有 6 到 10 年的经验。因此，这些人绝非业务新手，他们都是每天奋战在一线的专业人士。

<details>
<summary>Original English</summary>
So, uh, at Temporal, we wanted to understand how things are actually going. So, we conducted a survey. It is our second year running this survey, the State of Development Survey. Uh, we surveyed 554 engineers and engineering leaders who are actively using AI agents right now. Every number on this slide deck is either from that report, uh, or it'll be qualified in the bottom left from the report that I'm pulling it from. So, to start things off, we can talk take a look at the demographic of that survey. 48.4% have 11 plus years of experience working in industry. So, we're not talking about hobbyists. And then the remain another third of that segment also has 6 to 10 years. So, none of these people are hobbyists. They're all professionals working, um, every day.
</details>

他们由工程师、AI 工程师、数据工程师、平台团队以及 IT 管理者构成。三分之二来自美国，三分之一来自英国和欧洲、中东及非洲地区（EMEA）。

<details>
<summary>Original English</summary>
Um, it's a mix of engineers, AI engineers, data engineers, platform teams, IT leaders. Two-thirds of them were from the US, a third of them were from the UK and EMEA.
</details>

我们发现了四大鸿沟。正如在演讲标题中向大家承诺的，这次分享是关于鸿沟的。数据显示存在着四大主要差距，我想逐一阐述，最后以一个核心观点作结。

<details>
<summary>Original English</summary>
Uh, and what we found, uh, is four gaps. I promised you all that this talk was about gaps in the title. Uh, and the data shows that there are four major gaps, and I wanted to walk through each of them and then close with kind of one big idea.
</details>

### 第一大鸿沟：日常使用与生产落地的差距

那么我们来看**第一大鸿沟：使用与生产的差距（usage versus production）**。在我们 2025 版的调查中，大约 47.3% 的受访者表示每天都在使用 Agent。而今天，差不多一年之后，这一比例翻了一番，达到了 80.8% 的用户在日常工作中使用 Agent。

<details>
<summary>Original English</summary>
So, let's go into gap one, and that's the gap between, uh, usage versus production. So, daily agent use from our 2025 version of this survey had us at about 47.3% of the folks that we talked to were using agents daily. Uh, today, uh, nearly a year later, we've doubled that to 80.8% uh, of users are using agents in their day-to-day.
</details>

然而，日常使用 Agent 并不等同于在生产环境中交付 Agent。如果我们再看这些团队并询问他们在做什么：大约一半的人正在生产环境中运行这些 Agent，或者表示这些 Agent 是他们交付产品的核心环节；而另一半人仍然在实验阶段，或者实际上仅将其作为辅助工具使用。也就是说，我们访谈的对象中有 49.1%（也就是半数）在生产环境中运行 Agent，或者表示这些 Agent 是流程交付的核心。

<details>
<summary>Original English</summary>
Um, Now, using agents isn't necessarily the same thing as shipping agents. Uh, and so if we take a look at those teams again and ask them what they're doing, about half of them are running those agents in production, or they say that those agents are core to how they ship. And then the other half of that is still experimenting or still only really using assistants. So, we've got 49.1% of the folks that we talked to, half of the folks that we talked to are running agents in production or saying that those agents are core to how how things ship.
</details>

这是一个巨大的差距，对吧？80% 的人每天都在使用 Agent，但实际上只有 50%（49.1%）将其交付并在生产环境中应用，这中间有着 30% 的鸿沟。进入生产环境的人数远远少于日常使用的人数。

<details>
<summary>Original English</summary>
Um so, that's a huge gap, right? Like, that's a 30% gap between 80% of the people are using agents every day and 50%, 49.1% are actually shipping them and using them in production. So, far fewer people in production than actually using them daily.
</details>

### 第二大鸿沟：高度信任与频繁故障的矛盾

在通往生产环境的路上，似乎总有什么东西在不断损坏。我们来聊聊这究竟是什么。这就引出了**第二大鸿沟：信任与现实的差距（trust versus reality）**。我们在调查中询问受访者的一件事是：你究竟有多信任 Agent 的输出结果？实际上，大家的信任度非常高，这个数字着实让我印象深刻。在我们调查的人群中，有四分之一几乎完全信任 Agent 的输出；大多数人表示比较信任；几乎没有人不信任。我自己没有被邀请参与这项调查，因为我本人属于完全不太信任的那一类。所以看到调查得出的这个数字，我确实感到很吃惊。

<details>
<summary>Original English</summary>
And something seems to keep breaking on the way to production. And let's talk about what that is. And that brings us to gap number two, which is trust versus reality. Now, one of the things we asked folks in the survey was how much do you actually trust your agent output? And trust is really high, actually. I'm really impressed by this number. Uh a quarter of the folks that we we surveyed trusted the agent output almost completely. Most people trusted it somewhat. And almost no one disrupted distrusted it. I did not get asked to to participate in this survey because I'm in that complete somewhat distrust category myself. So, I'm actually really surprised by this number from that survey.
</details>

是的，85.5% 的人至少在某种程度上信任 Agent 的输出。这是一个很关键的数字，稍后我们会再回来看这个 85.5%。

<details>
<summary>Original English</summary>
Um Yeah, 85.5% trust agent output at least somewhat. Uh and that's going to be an important number. Let's come back to that 85.5 in a little bit.
</details>

我们还问了一个问题：你们的 Agent 多久出现一次故障？粉色柱状图代表每天甚至更频繁地发生故障。对于一个有 85% 的人表示信任的技术来说，粉色区域的占比实在太高了，远远超出了我对 85% 信任度评级的预期。

<details>
<summary>Original English</summary>
So, we also asked how often do your agents have issues? Um the pink bars are daily or worse. And that's a lot of pink for a number that uh 85% of people trust. That's a lot more pink than I would expect for an 85% trust rating.
</details>

41.1% 的人每天或更频繁地遇到 Agent 故障。也就是说，在我们访谈的对象中，每 10 个人里就有 4 个每天都会遇到问题。更有 16.4% 的人每小时都会遇到问题——受访者中每 6 个人就有 1 个每小时都要经历一次 Agent 故障。这就把我们带回了那个信任差距：85.5% 的人信任它，但有 41.1% 的人面临系统崩溃。也就是说，我们信任它的输出和系统，但它每天仍然会崩掉。这两种情况同时真实存在着。

<details>
<summary>Original English</summary>
Uh 41.1% of those folks hit those agent issues daily or more. So, that's four in 10 of the people that we talked to see issues every day. And then 16.4 hit them every hour. So, one in six of the people that we surveyed were getting an agent issue every hour. And then that brings us back to that trust that 85.5% gap versus the 41.1% uh system breaking. Uh so so, we trust the output and the system, but it still breaks every day. Uh both of those things are true at the same time.
</details>

而且，技术熟练似乎并不能解决这个问题，你无法仅靠提升技能来摆脱这种困境。我们发现，那些自称非常成功的团队，遇到持续性故障（即处于按小时或按天发生故障的区间）的概率实际上要高出 1.7 倍。这并不是因为他们运行了更多的 Agent。报告发现，Agent 的数量与故障频率之间实际上没有任何相关性。我和 Temporal 团队的推测是，也许是因为这些团队在更严苛地排查问题，所以他们发现了更多的故障。这无疑是我们明年做下一版调查时需要进一步深挖的方向。

<details>
<summary>Original English</summary>
And getting good at agents doesn't seem to to make this go away. You can't skill your way out of this. Um we were seeing teams that call themselves successful were actually 1.7 more times likely to hit issues continuously. So, be in that hourly or daily category. Uh and it's not because they've run more agents, right? The report found that agent count and issue frequency aren't actually correlated in any way. I'm guessing and the team at Temporal are guessing that maybe those folks are just looking harder for issues and so they're finding those issues so more. That's definitely something we need to dig into a little more when we do next year's version of this survey.
</details>

但我想，核心的启示在于：无论你有多信任你的 Agent，故障都不会凭空消失。你必须考虑到它，必须为它做好规划。所以，我们在生产中使用 Agent 时，目标并不是实现“零故障”，而是**如何确保这些故障不会给我们带来任何代价**。

<details>
<summary>Original English</summary>
But, the important, I guess, takeaway is that even with how much you trust your agents, failure isn't going away. Uh you have to account for it. You have to plan for it. So, the goal isn't zero failures, right, when we're using agents in production. It's just how do we make it so these failures don't cost us anything.
</details>

这里还有一个非常有趣的数据：受访团队中有 40% 表示安全是真正阻碍他们实现自主 Agent（autonomous agents）的因素。这是一个独立的话题。昨天在工作坊日，Temporal 团队的 Mason 和 Keycard 团队的 Kim 刚刚就此做过专门演讲。因此，我建议大家去看那场演讲的录像，这里我就不展开讨论了。

<details>
<summary>Original English</summary>
Now, a really interesting stat is saying that 40% uh of the teams that we talked to says security is truly the thing that is blocking them from autonomous agents. And that's its own talk. Mason uh from the Temporal team and Kim from the Keycard team actually gave a talk about this yesterday on the workshop day. So, I'm going to defer to the recording of that talk uh rather than going to it myself. Um as well.
</details>

### 第三大鸿沟：原型构建与企业级部署的周期差异

接下来进入**第三大鸿沟：原型与企业级部署的差距（prototype versus enterprise deployment）**。也就是我们去年可能都在经历和研发的原型，对比客户真正在使用的生产就绪型代码系统。大多数从 AI 原型起步的团队都希望极快地过渡到生产就绪代码，我们确实看到了非常短的耗时数字：51.3% 的人能够在数小时或更短时间内将 AI 原型转化为生产就绪状态。这完全是初创公司的速度，典型的创业公司节奏。

<details>
<summary>Original English</summary>
And let's jump into that third gap. The prototype uh that we we're probably all seeing and working on last year versus the enterprise deployment, you know, customers are actually touching it. That prototype to production-ready code system. And most teams going from an AI prototype want to go to production-ready code uh really fast. We're seeing it in like really low numbers. Uh 51.3% uh are able to get an AI prototype to production-ready in hours or faster. Uh that's like startup speed, right? That's traditional startup speed.
</details>

然而，如果你在大型企业工作，这一套就行不通了。如果你身处一家拥有 5000 名以上员工的公司，这个过程往往需要数月时间。数据在这个维度上出现了分化：在规模最大的企业中，大约每 5 家就有 1 家表示需要数月；而在其他规模的企业中，只有大约二十分之一表示将 AI Agent 部署到生产需要数月。

<details>
<summary>Original English</summary>
Uh this falls apart, though, if you work somewhere big. Uh so, if you work somewhere uh 5,000-plus employees, it tends to take months. Uh and the data breaks down at that point. The biggest companies, about one in five says it takes months. Everywhere else, it's about one in 20 saying that it takes months to get an AI agent deployed into production.
</details>

因此，大企业的交付速度截然不同。我们使用的是同样的工具，交付速度却大相径庭。半数团队能在几小时内完成部署，而在这些大企业里，五分之一的团队要耗费数月。大型公司、强监管业务——我们谈论的是银行、保险公司、支付机构，我猜现场现在就坐着很多来自这类机构的人。这些公司都极其需要一系列至关重要的机制：他们需要审批流程、需要审计追踪、需要确保绝不丢失任何一笔支付的系统。依我理解，那数月的时间正是花在了满足可审计性以及建立对所有这些机制的信任上。调研本身没有细分这些耗时项，但我希望这并非官僚作风本身，而是为了产生效益并达到可靠性门槛所付出的必要流程。

<details>
<summary>Original English</summary>
So, big companies are shipping at very different speeds. We're using the same tools at very different speeds. Half are shipping in hours, and then at these large companies were doing it one in five taking five months. Um big companies, regulated work, we're talking about banks, we're talking about insurers, we're talking about payment companies. I'm guessing there's a lot of those in the room right now. And those companies all need something really need a bunch of things that are really important, right? They need approvals, they need audit trails, they need systems that will not lose a payment. My read is that's where the five months are going into the auditability and the trust of all of those things. And the survey doesn't break that down, right? But it's not bureaucracy for its own sake, or at least I hope it's not. I hope it's it's bureaucracy for something productive and like getting to that reliability bar.
</details>

### 第四大鸿沟：可观测性与系统恢复能力的断层

这就引出了最后一个痛点，也就是**可靠性鸿沟：可观测与故障恢复的差距（seeing versus recovering）**。这也是我演讲标题中提到的要点之一。我们询问了是什么限制了你们团队的生产力？排名第一的是**跟踪状态（tracking state）**，排名第二的是**调试（debugging）**。模型本身根本没进入前两位。

<details>
<summary>Original English</summary>
Which brings us to that last rub, I reliability gap, seeing versus recovering. And this is one of the ones that was in the title, right? So, we asked what limits your team's productivity. Number one is tracking state, and number two is debugging. The models aren't in the top two at all.
</details>

35.7% 的受访者表示，跨服务跟踪状态是他们的头号障碍；30.9% 表示是隔离和调试问题。调查中有 22.2% 的团队因为崩溃和重启而丢失进度并不得不重复劳动。也就是说，五分之一的团队在蒙受工作成果丢失的代价。在去年的另一项调查中，有 27% 的人称其状态管理十分脆弱。今年，它直接跃升为首要障碍。虽然两次调查的问题不同，不能算作一条严格的趋势线，但背后的逻辑是高度一致的：**随着 Agent 变得越来越落地，状态管理变得越来越重要**。

<details>
<summary>Original English</summary>
35.7% were saying state tracking state across services their top blocker, and then 30.9% says that it's isolating and debugging debugging issues. 22.2% of that survey are losing progress and redoing work because of crashes and restarts. So, that's one in five losing work. And then last year in a different survey, 27% called their state management fragile. This year it's the number one blocker. Different surveys, different questions. So, it's not a trend line, but the story is consistent. State got more important as agents got more real.
</details>

最让人啼笑皆非的回答之一是：当 Agent 出故障时，你们去哪里寻求帮助？排在第一位的答案居然是 YouTube，这让我大开眼界。我写代码从不看 YouTube，这跟我构建系统的方式太不一样了。但这就是当你的系统无法告诉你发生了什么时，调试所呈现出的狼狈样子——你最终只能上 YouTube，试图找一个能解决的人。

<details>
<summary>Original English</summary>
And one of the wildest responses that we got was when when an agent breaks, where you go for help. And the number one answer to that being YouTube is kind of wild to me. I don't really code with YouTube, and so this is very different for me in the way that I build things. Um but that's what debugging looks like when your system can't tell you what happened. is you end up going to YouTube and trying to find someone that can.
</details>

目前的可观测性工具只会告诉你：你的 Agent 挂了。大部分团队都有这种能力，对吧？链路追踪（Traces）、日志、LLM 可观测性工具；然而，真正的“可靠性”意味着**发生故障时你无需付出任何代价**。在我们访谈的人群中，只有 13% 的人非常有信心能够在大规模环境下对 AI 工作流进行观测和调试。同时有 22% 的人因为系统崩溃而丢失进度。因此，“看见问题”与“恢复状态”之间的鸿沟，现实中就是一个工程师在凌晨两点看着链路追踪日志，然后手动去修复状态数据。这根本不切实际，要求有人在凌晨两点手工修复数据完全是不现实的。

<details>
<summary>Original English</summary>
>> [gasps]

>> Observability right now just tells you your agent failed. Most teams have that, right? Traces, logs, LLM observability tools, but reliability means that failure doesn't cost us anything. Uh only 13% of the people that we talked to were very confident that they can observe and debug AI workflows at scale. And then 22% of the people that we talked to lose progress because of crashes. And so the gap between seeing uh and recovering is a person reading a trace at 2:00 a.m. in the morning and then fixing their state by hand. And that's not realistic, right? Like that's not a realistic thing to expect uh is someone fixing things at 2:00 a.m. in the morning.
</details>

### 支付与反欺诈工作流演示

我想做个简短的 Demo 展示一下这是什么样的场景。我准备转移 2500 美元。这是一个虚拟客户，但运行的是一个真实的 Temporal 工作流。这也是一个运行在这台笔记本上的真实 LLM——我此刻在笔记本上跑着 Qwen 9B 模型。我将向大家演示接下来会发生什么。简而言之，我们正在运行一个支付工作流。这是一个包含 9 个阶段的工作流，比实际生产环境中的流程要简短得多。资金将被划转，这笔资金交易看起来有些异常；于是 Agent 会介入并展开欺诈调查。Agent 会查看这笔交易并作出判断：是需要上报给人工处理，还是可以直接放行通过？随后，我们会引入人机协同（human-in-the-loop），由人工来做最终决策，决定是否批准这笔交易。我们将验证请求、冻结资金、获取外汇（FX）报价，这些资金会被冻结。因此，真实的资金状态将留存在另一个外部系统中。

<details>
<summary>Original English</summary>
So, I want to show a quick little demo, right, of what this looks like. And I'm going to move 25,000 2,500 dollars. It's a synthetic customer, but it's a real Temporal workflow. It's a real LLM running on this laptop. I have Qwen 36B uh 9B 9B running on this laptop right now. Uh and I'll show you a demo of what we're about to go through. But basically, we're running a payout workflow. So, this is going to be a nine-stage workflow uh which is going to be much shorter than I think it would be in like in production. Uh money is going to move. Uh the money is going to look kind of weird. Uh and so an agent is going to jump in and is going to do a fraud investigation. The agent is going to just take a look at the transaction and decide, do we need to escalate this to a human being or is this good to just wave it through? Uh and then we're going to have a human in the loop that actually makes the decision and decides what to uh whether or not to make the final call of this transaction getting approved or not. We're going to validate the request, reserve the funds, check in with the FX quote, and those funds will be reserved. So, the real estate will exist in another system.
</details>

接下来，抱歉，我们会让 Agent 去执行真正的任务、进行工具调用，然后我会直接杀掉这个进程。

<details>
<summary>Original English</summary>
And then I'm going to go ahead and kill uh sorry. And we're going to have that agent do the real work, do those tool calls, uh and then I'm going to kill the process.
</details>

我会直接让 Worker 终止运行。我停止该 Worker，进程就此终结。这可能是由任何原因引起的，比如超时、部署错误、或者内存溢出（OOM）。我通过手动杀掉进程来模拟 Worker 崩溃，然后我们看看会丢失什么。

<details>
<summary>Original English</summary>
Um so, I'm going to just tell the worker to die. I'm going to stop the worker. Uh and so our process will die. Uh and that could be for any reason, right? Like it could be a timeout, it could be a deploy error, we could run out of memory. I'm going to just intentionally kill it to simulate a worker crash, and we'll see what we lose.
</details>

在传统架构下，我们会丢失的是：资金已被冻结却无法完成支付发放；而且生成了一份审查简报，却永远无法送达审批人手中。因此，在传统架构中，我们必须重新消耗 LLM Token 来重新生成那份 AI 审核草稿或摘要。在传统技术栈中，所有这些数据都驻留在进程内存里，一旦 Worker 崩溃，一切都灰飞烟灭。资金仍然处于冻结状态，但不在我们的系统中，而是在银行系统中。因此，以往我们必须编写恢复代码、构建状态表、编写重试逻辑、创建对账任务，而所有这些代码都与我为了处理支付交易而编写的核心业务逻辑无关。有 30% 的受访者抱怨的问题正是：他们耗费精力构建的大量代码与核心业务逻辑毫无关系。

<details>
<summary>Original English</summary>
Um what we would lose traditionally is that the funds would be reserved with no payout, uh and a brief would get produced that never actually makes its way to the approver. So, we're going to have to re-spend our LLM tokens traditionally to regenerate that AI uh draft or summary for the check. Um in that tech in like a traditional stack, all of that is going to live in process memory, and when that worker crashes, it's all gone. And so, the reserved funds are still reserved, it's just not in our system, it's in the bank system. So, traditionally we'd have to write recovery code, we'd have to build state tables, we'd have to build retry logic, we'd have to create reconciliation jobs, and that's all code that's unrelated to the core business logic that I'm building to just do a payment transaction. And that's something that 30% of our respondents complained about is that they're building all of this code unrelated to business logic.
</details>

### 持久化执行机制与故障自愈

或者，你可以使用一个具备记忆能力的平台，这就是**持久化执行（durable execution）**的用武之地。持久化执行是 Temporal 的核心概念：本质上，即使进程没有执行完毕，代码也应当确保执行直至完成。我们知道崩溃不可避免，但在 Temporal 中，状态能够留存，执行进度能够留存，并且每一步都被记录在类似这样的事件历史（event history）中。在这个状态中，我们也记录了 AI 的执行情况。稍后我们会在实况演示中看到这条时间线，它来自于我们将要运行的这笔支付 Demo。AI 的每一个步骤——选择调查方案、Agent 循环中为查询客户信息所执行的工具调用，以及随后的简报起草——每一个都是带有记录结果的独立 Activity。这里的黄色条带本质上就是等待人工审批的 Activity。

<details>
<summary>Original English</summary>
Or you could use a platform that remembers you, and uh that's where durable execution comes in. So, durable execution is a temporal concept that code essentially should run to completion even when the process doesn't. We know that crashes happen, but with temporal state survives, progress survives, uh and every step is recorded in an event history that looks like this. And so, we've also recorded the AI in this state. So, this is a timeline that we'll we'll see in a second live that's a run from the payout demo that we're going to run in a second. Uh each of those steps, uh each of those AI steps, choosing the investigation, the tool calls that the agentic loop is going to make uh for the lookup of the customer and then drafting the brief, each of those is its own individual activity with a recorded result. And the yellow bar is going to be our our essentially activity waiting for a human approval.
</details>

工作流代码负责决定下一步做什么，并且它是**确定性的（deterministic）**。任何非确定性或具有副作用的操作（例如调用 LLM），都会在 Activity 中运行。因此，工具调用或银行 API 调用都会作为一个 Activity。而人工批准或拒绝该交易的操作也是一个事件。在 Temporal 中我们称之为 **Signal（信号）**，它会像其他所有数据一样被持久化记录在 Temporal 历史中。即使此时没有 Worker 处于运行状态，该 Signal 依然会被成功捕获和处理。因此，当某个 Worker 挂掉时，另一个 Worker 能够从上一次成功的状态继续执行。

<details>
<summary>Original English</summary>
Um the workflow code is deciding what's next, and it's deterministic. Anything non-deterministic or side-effecting like the LLM is going to be run in an activity. So, a tool call or a bank API call is going to be an activity. And then the person, when they approve or reject the transaction, is going to be an event too. It's a signal is what we call them in Temporal, which is like recorded in history uh like everything else is recorded in the temporal history. Even though the worker is not running, that signal is still going to get captured and get processed. So, when the worker dies, another worker is able to resume from the last previous success.
</details>

是的，历史记录保存在 Temporal 服务中，我们不会重复执行 LLM 工具调用，因此不会把 Token 浪费在重复调用上。我们保留了 Agent 的工作成果，无需重来一遍。如果 Worker 崩溃时某个调用正在进行中，我们会重试该 Activity，但在此之前的所有步骤都会被完整保留。这一点非常重要。每 10 个人中就有 8 人表示成本限制了他们对 Agent 的使用。因此，能够保留 Agent 的记忆是非常有帮助的。如果每次崩溃后都重新运行一遍 Agent，那无异于在白白烧钱。

<details>
<summary>Original English</summary>
Yeah, and the history lives in the temporal service and we're not running our LLM tool calls multiple times, so we're not wasting tokens on multiple tool calls. We're going to retain the agent's work and not redo it. If the call was mid-flight while the worker died, we would retry that activity, but everything before that is is kept. And that matters. Eight in 10 people say that cost limits how they use their agents. So, being able to hold on to the agent's memory is really helpful. Rerunning an agent after every cash is a lot of money that you're burning right there.
</details>

### 实况操作与故障恢复验证

我们来看一下这个简短的 Demo。这就是我的转账页面。我将其金额设置为 2500 美元，设定为一个新收款人，并标记为对该客户而言是一笔异常金额。为了确保 AI 会将其标记为需要调查的异常项，我们在客户记录中设置存在一条未解决的账户警报。我点击启动该任务，从而触发这个新的工作流。大家可以在下方的这条时间线中看到，我们讨论过的所有 9 个步骤正在逐步执行。我们冻结资金、进行验证，AI 正在运行 Agent 循环并作出判断：好的，先查询客户画像，再查看历史支付记录，然后起草一份简报供人工审核。此时界面上出现了一个“批准”和“拒绝”按钮供我点击。但在点击之前，正如我前面提到的，我将故意杀掉 Worker。我直接点击停止。可以看到，此时已经没有任何运行中的 Worker 了。在这种状态下，我点击批准这笔交易。

<details>
<summary>Original English</summary>
So, let's go into the quick demo and Yeah, so this is my payment transfer. So, I'm going to go ahead and set it to $2,500. I'm going to say that it's a new recipient. I'm going to say it's an unusual amount for this customer. And just to make sure that our AI flags it as something that needs an investigation, we're going to go ahead and set the customer record to say that there's an unresolved account alert. I'm going to go ahead and start this job, which is going to trigger this new workflow. And you can see down here in the timeline, all of those nine steps that we talked about are happening. So, we're going to reserve our funds, validate the AI is doing an agentic loop and deciding, okay, we're going to look at the customer profile, we're going to look at the payouts, and then we're going to draft a breach, a brief for a human being to review. So, I've got an approve or reject button that I can click right here. But before I click them, like I said, I am going to intentionally kill my workers. So, I'm just going to hit stop. You can see that there are no workers running at this point. So, I'm going to go ahead and approve my transaction.
</details>

可以看到，审批操作作为一个 Signal 被记录了下来。在传统系统中，这个操作通常就直接丢失了。稍后我们会收到一个超时提醒，但这没什么大不了的，因为我们的重试策略会自动处理它。只要我重新启动 Worker，它就会立即读取该 Signal，恢复行为，并从上一个成功的事件继续执行。我们启动 Worker。这需要一点时间。现场演示时耗时总是会稍微长一点，平时基本上是瞬间完成的。让我刷新一下页面。

<details>
<summary>Original English</summary>
And we can see the approval gets logged as a signal. Now, traditionally, that would be something that just gets lost. We'll get a timeout in a second, but that's not really a big deal cuz we're going to have a retry policy that'll handle this automatically. So, as soon as I return on my worker, it's just going to pick up that signal and resume the behavior and continue on from that last successful event. So, we'll start our worker. This will take a second. Of course, it takes a little longer when I'm demoing it live. Usually, it's instantaneous. Um let me just go ahead and give it a refresh.
</details>

你们知道吗？我专门为这种突发情况准备了一段视频，我们可以直接跳到视频里看看效果——如果视频能播的话。好的。让我看看能不能跳到中间部分。哎呀，视频在另一个标签页里，我这是在干嘛呢。

<details>
<summary>Original English</summary>
You know what? I have a video for just this scenario, so we can go ahead and just skip straight forward in the video and see what it's like uh if the video plays. Yeah. Let me see if I can skip to the middle of this. Oop. Oh, it's in the other tab. What am I doing? >> [sighs]
</details>

在 Worker 停止的情况下我点击批准，随后我在下方重新启动 Worker，它应该直接接手并恢复执行。Agent 完成调查并编写了简报，然后我给予了批准；接着在等待银行核准交易或标记完成的过程中，我还可以再次杀掉 Worker。同样的，Signal 会记录下来，每当我重新打开 Worker，它都会重新拉起并继续运行。

<details>
<summary>Original English</summary>
>> So, I'm going to approve while the worker is dead uh and then I'm going to go ahead and resume the worker right below uh and it should go ahead and just uh pick things up and like resume uh resume. So, the agent is going to investigate right the brief uh and then I give the approval and then, you know, I can go ahead and crash the worker again while we're waiting for the bank to approve the transaction or mark that it was completed. Again, the signal logs and then whenever I turn the worker back on, it's going to pick it up and rerun again. So.
</details>

### 事件历史与解决核心阻碍

根据事件历史的记录，实际发生的过程是这样的。我给大家再切回全屏。自顶向下看：我们的每个 AI Activity 都只运行了一次，尝试了一次，成功了一次，并且没有再次运行。我们没有重复执行整个工作流，没有重新消耗那些 Token，只是运行了一次，因而只产生了一次性的成本。我们审批的 Signal 是在没有任何 Worker 运行的情况下接收进来的；随后的银行提交操作同样是在 Worker 未运行的情况下接收的。这两件事都是由新启动的 Worker 接手处理的。我们中途停止了 Worker，而新拉起的 Worker 直接接管了状态。即使 Worker 归零，付款也会处于等待状态，审批被记录保留，我们不需要从头重新执行任何步骤。

<details>
<summary>Original English</summary>
So, this is what happened according to the event history. And let me full screen that again for y'all. Oop. There we go. Um so, reading from top to bottom, each of our AI activities ran once. They attempted once. They worked once. And they didn't run again. We didn't rerun that workflow. We didn't respend those tokens. We just ran it once and so we got that one-time cost. Uh our approval signal came through while there were no while there were no workers running. Uh and then our bank submission also, you know, came through while no workers were running. And both of those things happened on new workers. We stopped the workers each time uh and then we got new workers that just picked things up. So, zero workers, uh the payout waited, uh the approval landed, and we didn't have to rerun anything from the beginning.
</details>

那么，技术管理者们提到的拖慢团队步伐的问题完整清单是什么？刚才的 Demo 刚好解决了他们列出的排名前七的难题：状态管理、调试、成本、重试、审批、长周期任务以及崩溃恢复。我们可以看一下各项对应的代码实现。状态管理是调查中列出的头号障碍，而在 Temporal 中，工作流状态仅仅是普通的变量字段。我没有去搭数据库，也没有搭建缓存。崩溃之后，重放（replay）过程会完全精准地将它们重建出来。

<details>
<summary>Original English</summary>
So, what are the full list uh of what those engineering leaders are saying uh slow them down? Um our demo just handled seven of the top uh use cases right there that they gave us for problems. Um so state debugging cost retries approval long-running work and crash recovery. Um and we can take a look at the code for each of them. So state management in Temporal is the number one blocker or sorry was the number one blocker in that survey and a workflow state is just fields. It's plain variables. There's no database that I built. There's no cache. After a crash the replay just rebuilt them exactly.
</details>

正常情况下多次运行 LLM 会产生昂贵费用。但在此次运行中，由于我们保留了状态，所以 Agent 仅执行了一次。工具调用的执行结果被持久保留，无需耗费额外 Token。重试机制本身是一种策略（policy），而不是一段硬编码的循环代码。我们在配置中声明了一次重试策略，它便自动应用于该交易内的每一次调用，代码里没有任何手写的循环。

<details>
<summary>Original English</summary>
Uh our LLM calls uh would cost us normally for multiple runs. In this run the agent we maintained the state so we only ran it once. The tool run was held was sustained so we didn't need to spend any new tokens. Retries themselves were a policy not a loop. We declared the retry policy uh in our uh configuration once and then it applied to every single call in that transaction. There's no loop anywhere in that code. Um
</details>

这可能是对在座各位来说最重要的一页幻灯片：Agent 本身提供的是建议，工作流本身掌控着资金与状态。AI 拥有明确有界的介入范围；哪怕模型出现故障，打款流程依然可以脱离该简报继续进行，模型的服务中断并不会导致整体系统降级。我们设置了人工审批节点，计时器可以根据需求随意设定多久，代码逻辑完全一致——我们甚至可以等待一年后再恢复 Worker，系统依然安然无恙。此外，我没有编写任何一行崩溃恢复代码，所有这些能力都内置在 Temporal 之中。

<details>
<summary>Original English</summary>
The uh This is probably the most important slide for the room. So the agent itself gave us advice. The workflow itself owned the money and the state and the AI had a really bounded uh attempt to to jump in and if the model had failed the payout would have continued without the brief. A model outage wouldn't have degraded anything. Um we had our human approval uh and we could have set that timer for as long as we wanted uh and it would have been the same code. Um we could have waited for a year and resumed that worker and it would have been fine. And then I didn't write any crash recovery code. That was all built into Temporal. Um
</details>

关于调试：在大多数技术栈中，可观测性记录与系统恢复记录是两套分离且彼此漂移的数据，最终全靠人工将它们拼凑对齐。而在 Temporal 中，我们在 UI 界面里用于调试的历史记录，与 Worker 用来重放执行的历史记录是完全同一份数据，从而弥合了两者之间的断层。因此，面对七大阻碍，我们用一个工作流方案将它们全部解决。

<details>
<summary>Original English</summary>
So debugging uh in most stacks observability and recovery are two separate records that drift apart and then a human brings them together. Here we were able to have the history that we debugged in the UI be the same history that our worker replays which closed the gap for. So we had seven blockers and we solved them with one workflow.
</details>

### 生产案例与总结

这绝不仅是一个 Demo。目前已经有人在真实的生产环境中大规模使用这些方案。OpenAI 的 Codex 就是基于 Temporal 运行的；大家日常大量使用的编程 Agent 正在 Temporal 上运行；Replit 也在 Temporal 上运行他们的 Replit Agent。他们的工程团队表示，当一个 Agent 已经深度执行到了某个阶段，突然遭遇灾难性错误，用户体验是非常糟糕的——而这正是我们亲历过或者通过持久化执行避免发生的事情。由于时间快到了，我就快速跳过这部分。从 AI 工程师的角度来看，你编写 Prompt，执行它；如果输出不理想，你把它丢弃，Temporal 会自动为你执行重试。模型输出质量差本质上就是一个 Activity 失败，适用完全相同的重试策略。回到开头的四大鸿沟，一份事件记录就将它们全部弥合了。

<details>
<summary>Original English</summary>
And this isn't just a demo. So there are people using this stuff in production for real right now. OpenAI's Codex runs on Temporal. Uh the coding agent that you use a lot of the day is running on Temporal. Uh Replit runs their Replit agents on Temporal. Their engineering team says it's a bad user experience when the agent gets super far into something and then hits a catastrophic error. And that's just what we have watched happen or watched not happen. Um and I'm going to skip through this cuz I know I'm running out of time. Uh so from the AI engineer's side, you write the prompt, you run it, and the app if the output's bad, you throw it away, and then Temporal retries it for you. Um bad model output is just an activity failure, so same similar retry policy uh as well. Um so back to the four gaps, one record uh closed them all.
</details>

快速重温一下那四大鸿沟并再次总结：可靠性与可观测性通过同一份记录实现了统一。我在演讲中提到的每一个数据，均收录在 temporal.io 的《开发者现状调查》报告中。我把页面留在大屏幕上，方便大家拍照并亲自查阅。我们团队有许多成员在 Temporal 展台现场运行这个 Demo，欢迎大家过来交流或者打个招呼。那么，这就是我的演讲，非常感谢。

<details>
<summary>Original English</summary>
Um and just to skip through what those four gaps were uh again [laughter] uh and re-summarize that uh that yeah, reliability and observability uh were just one record. And so every number of this talk that I I um mentioned is in that temporal.io report state of development, and I'll leave that up screen if anyone wants to take a photo and come check it out. Uh and there's a bunch of us that'll be at the Temporal booth running this demo live if anyone wants to come see it or say hi. So, um yeah, that's that's my talk. Let's have >> [applause]
</details>