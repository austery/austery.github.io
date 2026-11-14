---
author: Latent Space
date: '2026-11-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LL0YmIyBKSU
speaker: Latent Space
tags:
  - software-engineering
  - autonomous-agent
  - developer-tool
  - system-architecture
  - benchmarking
title: Warp 创始人 Zach Lloyd：云端软件工厂的基础设施架构与工程化
summary: Warp 创始人 Zach Lloyd 探讨了从零散使用编码 Agent 转向“软件工厂”基础设施的演进路径。他提出工厂应具备声明式代码定义、集中化追踪、评测打分与自优化闭环等六层架构，并分享了团队将单个 PR 成本从 80 美元降至 15-20 美元、吞吐量提升 40% 的实践。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people:
  - Zach Lloyd
companies_orgs:
  - Warp
products_models:
  - Warp
media_books: []
status: evergreen
---
### 引言与背景

**[Host]**: 嘿，又是我。我听到了很多关于我们每期节目开场介绍的正面反馈，所以只要时间允许，我会继续做下去。今天，我们将与 Zach Lloyd 一起深入探讨 Warp。

Zach 研发 Warp 已经有一段时间了，如今它已经转型成为现在的形态——基本上是一个权威的软件工厂，并且它也是开源的。

我认为他提出了一整套非常出色的定义。他在 AIE 上的演讲一直在病毒式传播，成为有史以来最火爆的演讲之一。我认为实际上每个人现在都在试图为自己搭建这套系统。他们为你提供了一个解决方案，但它在某种程度上也是一个开放规范，正在成为大家所期望的标配。我认为你会需要云端支持、需要控制平面，会需要所有这些你认为理所当然的基础安全功能和团队协作功能。

因此，我们发布这期节目，作为 AIE Code 的预热。AIE Code 是今年最后一场 AIE 旗舰活动，将在旧金山举行，届时我们将汇聚顶尖的后生工程师，探讨软件工厂等诸多话题。

系统 1 模型，Diogo 会回归并拉高你的预期目标。Tariq、Jason，还有来自 ArtCraft 的 Brandon 将带来他有生以来的第一次大会演讲。所以如果你感兴趣的话，Zach 也将带来一场关于软件工厂的精彩主题演讲，回顾这一年并展望未来的发展。欢迎加入我们，现场会非常精彩。回见。
<details><summary>Original English</summary>
Hey, it's me again. I have heard a lot of positive feedback about our episode intros, so I'm going to keep trying to do them as far as time allows. Today, we're going to dive into Warp with Zach Lloyd. Um

Zach has been working on Warp for a while and it's pivoted into what it is today, which is basically the definitive software factory that is also open source.

And he has this whole definition, I think, which has done really well. His his basic his talk yet AIE has been going viral as one of the top talks of all time. And I think effectively everyone is trying to set this up for themselves. They have a solution for you, but it's also, you know, kind of an open spec that is becoming table stakes for what you're going to want. And I think you are going to want cloud, you're going to want a control plane, you're going to want all of these sort of basic security features and team features that are you take for granted. So, we're releasing this episode as part of a preview for AIE Code. AIE Code is the last AIE flagship of the year. It's going to be in San Francisco, where we're gathering all the top epigenetic engineers and talking about software factories, among other things.

System One models, Diogo is coming back and raising your ambitions. So, Tariq and Jason and Brandon from ArtCraft is doing his first conference talk ever. So, if you're interested, Zach will also be giving a great keynote on software factories and sort of recapping the year and previewing what's next. Join us and it'll be lots of fun. See you.
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>

>> 我们正在远程演播室连线 Warp 的 Zach Lloyd。欢迎。
<details><summary>Original English</summary>
>> We're in a remote studio catching up with Zach Lloyd from Warp. Welcome.
</details>

>> 很高兴来到这里。感谢邀请我。
<details><summary>Original English</summary>
>> Good to be here. Thanks for having me.
</details>

>> Zach，你在 AIE 上彻底火了。怎么回事？你触动了大家的神经。[笑声] 你触动了痛点。
<details><summary>Original English</summary>
>> Zach, you've been going viral on AIE. What's up? What's the What's the What You've hit a nerve. [laughter] You've hit a nerve.
</details>

### 什么是软件工厂

>> 大家对软件工厂非常感兴趣。这正是我一直关注的领域，也是 Warp 一直聚焦的领域。

我认为对于什么是软件工厂、以及它对身为软件工程师意味着什么，我们有一些非常明确且有趣的观点。所以是的，大家对此非常投入。
<details><summary>Original English</summary>
>> People are really interested in software factories. And that is a area that I've been focusing on, that Warp has been focusing on.

I think we have some, you know, strong kind of interesting takes on what a software factory actually is and what it means for being a software developer. So, yeah, that's and that's people have been into it.
</details>

>> 你们落地页的主标题写着“云端软件工厂的开放基础设施”。既然你花在向人们介绍工厂上的时间比我多，那么在大家看来，什么是软件工厂？他们真正需要的又是什么？
<details><summary>Original English</summary>
>> Your H1 on the landing page says open infrastructure for cloud software factories. I think maybe if since you spend more time than I do talking about telling people about factories, what do people think is a software factory and what do they actually need?
</details>

>> 当我与企业或开发者交流时，世界上大多数团队都在试图构建某种内部软件工厂或一套软件工厂。我认为它的含义——或者说它对我而言的定义——就像是云端的一个 Agent 化系统，你在其中定义各种 Agent 在为团队或产品构建软件过程中的角色，并且该系统中具备一定程度的自主性。也就是说，这些 Agent 能够独立完成任务；而这个系统在我看来，应该是一个高度可衡量、高度闭环的系统，随着时间的推移，你的团队可以对其进行调优、衡量、基准测试，并最终确信：随着大家转向这种 Agent 开发模式，他们是以最具扩展性和最高效的方式在进行。
<details><summary>Original English</summary>
>> When I talk to companies or developers, most of the world is trying to build some sort of internal software factory or set of software factories. What what I think it means or maybe I'll just define what it means to me is like a agentic system in the cloud where you're defining what are the roles of various agents across building software for your team or for your product and there's a certain amount of autonomy in that system. So, it's like the agents can do things on their own and that system to me should be something that's very measurable, very close loop, which over time you as a team can like tune, measure, benchmark, and just ultimately get confidence that as people switch to this way of doing agentic development, that they're doing it in the most scalable and efficient way.
</details>

>> 那么大家带着怎样的常见误解来找你呢？比如他们会觉得，“只要我做了某件事，或者买了某个工具，另一端就会源源不断吐出一台神奇的赚钱机器”？
<details><summary>Original English</summary>
>> And what what do people come to you with that perhaps is a common misconception, right? Like they're like, okay, if I if I do whatever, if I buy whatever, I'm going to come out the other end with like this amazing money machine.
</details>

### 工厂即代码与工作流编排

>> 是的。当人们来找我们想搭建自己的软件工厂时，他们往往只是把各种自动化脚本拼凑在一起。有时人们心目中的软件工厂并不是一个具体的东西，而只是一种说法：“我们在大量使用 Agent 来交付软件，我们就把这称为内部软件工厂。”

我们试图让这个概念更加具体，我们会说：不，不，不，你实际上应该把软件工厂视为一个非常具体的事物。你应该用代码来定义你的工厂。你应该确保工厂具备所有的工作流、技能、MCP，一切都是一个具象的实体，你能够在某个时间点运行它并衡量它的表现。因为人们对这些工厂有着各种随意的想法。

因此对于我们的平台 Warp Factories 来说，我们说不，它实际上是一个真实存在的系统。你可以编排它，可以衡量它。每个产品界面（surface）对应一个工厂。我们试图将其从那种“由任意自动化和交互式 Agent 组成的模糊集合”的范畴中剥离出来，变成一个实实在在的系统。

思考软件工厂的方式，或者我们看待它的方式——你在这里看到的就是 Warp 软件工厂平台——是一个工厂作用于某个产品界面上。想象一下你正在构建你的移动端应用，或者在构建你的服务端应用等等。工厂本身操作一组代码仓库，拥有一组它所需的技能，拥有一组 MCP。

然后它有一套与之关联的工作流。这个工作流大致匹配你的团队当前为了修改该代码库所采取的操作流程。比如，可能包含分诊（triage）步骤、编写规范（specking）步骤、实现步骤。关键在于存在某种定义好的工作流，而且该工作流本身是用代码定义的。对我们来说，基本上就是一个 YAML 文件，其中声明了：“这些是你可以使用的所有仓库，这些是所有挂接好的 MCP 和集成。”因此，你基本上是在某个地方完整定义了整套系统。

理解如何使用工厂的方式，在于它实际上对应两类角色。一类是构建产品的人，他们进行产品工程开发，通过工厂交付功能。对于这些人，他们使用工厂的方式是通过现有工具。例如，他们可以通过 Slack 给工厂发消息来派发工作，可以使用像 Linear 或 Jira 这样的任务跟踪工具，可以通过 GitHub 与工厂交互，也可以通过 API 或 MCP 调用它。这里的比喻就像是你把一个工作项放进工厂里。一旦进入工厂，就会启动一个预定义的工作流，而该工作流是用代码定义的。到目前为止能理解吗？
<details><summary>Original English</summary>
>> Yeah, so so when people come to us and they're trying to build their own software factory, like often they'll be like stringing together different automations. Sometimes people are conceiving of software factories as just like just like a not a not a specific thing, but it's just like we're using agents a lot to ship software and we're calling that our internal software factory. And what we try to to do to make that more concrete is be like, no, no, no, you should actually think of a software factory as a very specific thing. Like you should define your factory in code. You should make sure that the factory has all of the workflows, skills, MCPs, everything is like it's like a concrete thing that you should be able to run at some point in time and measure how it's doing. Cuz people have all sorts of kind of random ideas around what these factories are. And so for for Warp factories, which is our platform, it's like what we say no, no, it's actually it's a real thing. You can orchestrate it, you can measure it. You have one factory per product surface. And we try to like take it out of the realm of just being like this nebulous uh it's a collection of like arbitrary automations and interactive agents into a a thing that's an actual What the way to think about a software factory or the way that we think about it, what you're looking at here is is Warp software factory platform, is a factory operates on some product surface. So, imagine you're building like your mobile app or you're building you know, your server app or whatever. And the factory itself is operating on a set of repos and has a set of skills it needs, it has a set of MCPs.

And then it has like a a workflow associated with it. And this workflow you know, roughly matches what you know, your team is probably already doing to make changes to that code base. So, there could be a step where you're doing triage, it could be where you're doing specking, implementation. The important thing is like there's some kind of defined workflow and that that workflow itself is defined in code. So, for us, we basically have a YAML file which says, "Okay, these are all the repos that you could be using, these are all of the MCPs, all of the integrations that are hooked up." So, you basically have this whole thing defined someplace.

The way to think about using the factory is that there's actually sort of two personas. So, there's someone who is building the product, they're doing product engineering, they're shipping features through a factory. And for those people, the way they use the factory or the way that is through their existing tools. So, they could be slacking the factory to put work into it, they could be using a task tracker like Linear or Jira, they could be interacting with the factory through GitHub, they could be calling it via API or MCP. And the metaphor is like you're putting a work item into the factory. And when it goes into the factory, that starts like a predefined workflow, and that workflow is defined in code. That makes sense so far?
</details>

>> 我非常喜欢“用代码定义一切”。
<details><summary>Original English</summary>
>> I love defining things in code.
</details>

### 可观测性、集中化与评估指标

>> 是的。你用代码设置好了整套体系，一旦搭建就位——再次用这个比喻——有人在 Slack、Linear 中发起任务，或者通过自动化触发（比如出现了服务器报错）。核心关键在于：所有这些都流经同一个系统。

一旦你让它运转起来，你基本上就能从中获得大量的收益。其中一个巨大收益在于，无论这些 Agent 在哪里运行——你现在看到的是 Warp 内部团队如何使用我们自己工厂的实时视图——在任何配置了工厂的产品上，你都能获得所有人在编码 Agent 方面操作的完整追踪记录（trace）。这不仅很酷于“我想看看大家在做什么”，比如“我想看看 Sofic 在做什么”，更关键的是，它开始把整个团队中编码 Agent 的所有对话、产出物以及完成的所有工作进行集中化管理。

因此，当我谈到拥有一个闭环系统时，这些 Agent 对话和追踪记录正是该系统如何改进的核心要素。举个例子，看看其中一条 Agent 追踪记录，Sofic 正在处理我们的移动端应用。Sofic 是在 Slack 里发起这个操作的，所以如果我想的话，我可以在 Slack 中调出它。

但系统实际上生成并保留了对话的完整记录，保留了构建该内容时产出的所有计算机使用（computer use）屏幕截图。你可以完整看到编排 Agent 的不同组件当时究竟在执行什么操作。你拥有的不仅是单次记录，而是每一项任务的完整记录。

在当今的大多数团队中，据我与各家公司的交流，绝大多数都没有类似的基础设施，因为他们的大多数工程师都是各自在终端里单独使用 Claude Code，或者在各自的本地环境中使用 Codex 客户端之类的工具。

但他们希望进入一个拥有这种集中化管理的世界。一旦实现了这种集中化，你基本上就可以获得关于全公司范围内 Agent 编码运转情况的各种有趣数据。你可以从不同维度来分析这些数据。

你可以将其视为：“在引入编码 Agent 后，我们团队的产出如何？”这包括传统的 DORA 指标，比如交付某样东西需要多长时间；也包括你的自动化程度如何。比如我们有一个指标：每合并一个 PR，人类平均需要介入处理多少次？你们的吞吐量是多少？

还有成本方面的指标。我们一直在密切跟踪这项指标。当我们与企业沟通时，成本问题非常非常关键：你希望能够为工厂配置合适的模型和合适的技能，从而随着时间推移切实降低每个 PR 的平均成本。你希望能够按人员细分成本，按自动化任务细分成本，按软件开发生命周期（SDLC）的不同环节来分析资金都花在了哪里。

最后一件非常酷的事情是，一旦你建立了这种闭环系统，你实际上可以深入底层，查看你的编码 Agent 在不同维度上的表现。你可以将这理解为线上评估（online evals），或者我们称之为评分器（scorers）。

这些评估可以涵盖非常通用的维度，比如：你的 Agent 是否过于啰嗦？它们是否高效？代码质量是否良好？我们在这些方面还有工作要做。
<details><summary>Original English</summary>
>> Yes. So, okay, so you have this whole thing set up in code, and then once you have that in place, and so the again metaphor is like someone starts a task in Slack, or in Linear, or through an automation like, you know, there's a server error. It all goes through one system is the kind of key thing. And once you have that working, you basically get a whole bunch of benefits that flow out of it. And so, one of the big benefits is that wherever these agents are running, and you're sort of seeing a real-time view across Warp's internal team, how are we using our own factories, you get a full trace of what everyone is doing with coding agents across any product that has a factory for it. And this is cool not just for like, oh, I want to see what people are doing, like I want to see what Sofic is doing, which is cool, but it also starts centralizing all of the agent conversations and agent artifacts and all of the work that are is being done by coding agents across your team.

And so, when I talk about like having a closed-loop system, these agent conversations, these agent traces, are like the key aspect of how this system improves. And so, for instance, just to look at one of these agent traces, Sofic is working on our mobile app here. Sofic was doing this in Slack, so I could pull this up in Slack if I wanted to.

But like, the thing is actually generating it has a full record of the conversation, has a full record of all of the These are computer use screenshots that are coming out of building this thing. And you can see a full record of exactly what the different pieces of the orchestration agent were doing. And so, you have this, but you have it not just for one thing, you have it for every single thing.

So, on your team today, what we when I talk to companies for the most part, they don't have something like this because most of their engineers are like individually using Cloud Code in their terminal or Codex the Codex app or something like that in their own local setups.

But, they want to get to a world where they have this centralization. When you have this centralization, you can basically get all this interesting data on how your agentic coding is working across your company. And you can think of this data along different dimensions. So, you can think of this data as like, okay, what's our team's output in the world of using coding agents? And so, that's things like, you know, traditional Dora metrics, how long does it take to ship something? It's things like how automated are you? And so, we have a sort of metric around like, for every PR that gets merged, how many times did a human have to do something with it? What's your throughput? It's metrics around cost. So, we're using this like constantly, and when we talk to companies, this cost thing is very, very important where you want to be able to tune your factory with the right models, the right skills to basically bring this cost per PR down by time. You want to be able to slice the cost by person. You want to be able to slice it by automation, by by where in the SDLC are you spending money? The final thing that's that's really cool, once you have this sort of closed-loop system going, is that you can actually look underneath the hood at how well your coding agents are doing along different dimensions. And so, you can think of this as like online evals or we call it scorers.

And these can go from very general things to like, are your agents being too verbose? Are they being efficient? Is the code quality good? We got work to do on this.
</details>

>> 这些是由我作为用户来定义，还是由你们作为平台提供？
<details><summary>Original English</summary>
>> Do I as a user define this or do you provide this as a platform?
</details>

### LLM as a Judge 与自优化闭环

>> 两者兼有。我们开箱即用地提供了一组我们认为具有普遍价值的评估器。

但在与企业合作的过程中，他们可能会有自己特别关注的 Agent 故障模式想要追踪。比如他们会问：“Agent 是否在做某种会导致我们构建中断的特定修改？”他们可能需要针对自身工作流非常定制化的东西。同样，这一切都通过代码定义，并且完全可定制。当你配置其中一个评估器时，后台实际发生的逻辑是：系统获取一组运行记录——我说的运行记录是指保存下来的历史 Agent 对话——然后由一个 Agent 去对它们进行追溯性打分。

这里有一个很好的例子，它正在检查冗余测试，这是使用编码 Agent 时常见的故障模式。有时候它们会写一堆你并不需要的测试；它们是在探索如何实现某些功能的过程中写下的，之后却留在了代码库中。这会导致代码库膨胀，浪费 Token。如果你想检测这种情况，你就可以创建这样一个评测项。

进一步展示一下评测项的具体结构：可以把它理解为“以大模型作为裁判”（LLM as a judge）。你需要选择一个裁判模型，查看它们在哪里运行，评判的提示词是什么，以及设置采样率——因为运行这些评估本身也是 Agent 在跑，你必须警惕运行它们的成本。

但一旦设置就绪，你就可以把它看作拥有了一群聪明的 Agent，在全团队范围内审视所有编码会话的进展。它们会指出：“有的 Agent 有时会写太多冗余测试。”于是你就获得了这份记录和洞察，明白应该从哪里着手去改进团队使用编码 Agent 的方式。目前为止听起来如何？因为我还想展示其他几个功能，以便更具体地说明你能用它做什么。
<details><summary>Original English</summary>
>> Yeah, so both. So, we provide out of the box a set of ones that we think are like generically useful.

But then, you know, as we work with companies, you know, they may have specific failure modes for their agents that they're interested in tracking. They may be like, "Hey, is the agent making a specific type of thing that is like change that is like breaking our build?" They may want something, you know, very specific to their workflow. So, again, this is all defined in code and all customizable. And what you do is like when you set up one of these, what's actually happening behind the scenes is that there's some set of runs that you you know, when I say runs, I mean like historical agent conversations that have been stored that an agent then goes and like retroactively grades. And so, this is a good example of one where it's grading for redundant tests, which is like a This is a common failure mode for using coding agents. Like sometimes they write a bunch of tests that you don't need. They write it in the course of like figuring out how to like implement something and then they leave it in the code. And so, this like bloats your code base. It wastes tokens. And so, you know, say you wanted to check for that, you you know, you basically create one of these evals.

And just to show you like a little more about what the eval looks like, the eval is Again, think of it as LLM as a judge. So, you're picking a a judge model. You're you're then seeing, okay, like where do these run? What's the prompt for judging it? And then a sampling rate because you might not like these are agents that are running. You might You got to be wary of the cost of them.

But when you have this set up, think of it then as like you have all of these smart agents that are looking across your team as at how all your your coding sessions are going. And they're saying, "Okay, sometimes there are agents that are writing too many tests." Right? And so, you get this record and this understanding of where you should look to sort of improve the way that your team is using coding agents. So far so good? Cuz I want to show a couple other things just to like make it more specific what you can do with this.
</details>

>> 总体来说很棒。我稍微有点好奇的是，Warp 是否存在不同的层级？你展示给我们看的像是 CTO 级别的视角，对吧？这是管理公司、手握程序员预算的人看的。
<details><summary>Original English</summary>
>> Overall good. I'm I'm a little bit wondering if this if basically there's different levels of insta of of Warp where there's like this is the CTO level what you're showing us, right? This is you're you're running the company, you've got a budget of coders.
</details>

>> 使用这个工具的人，一部分是工程经理或 CTO，但非常普遍的是平台团队。这通常不是日常业务工程师使用的界面。当我们与企业合作时，他们往往有一个内部团队——比如 DevX 开发者体验团队或平台团队——正在探索如何优化编码 Agent。因此，我在这里向你展示的，正是他们用来回答“我们如何在公司内最大化发挥 Claude Code、Codex 等工具价值”的工具集。
<details><summary>Original English</summary>
>> This is like the the people who use this, it's partly the engineering manager or the CTO, but it's also like very commonly like the platform team. But it's not your like day-to-day engineer typically. But like when we work with companies, you know, they'll often have an internal team that's been trying to like that's like the DevX team or the platform team and they're trying to figure out how to optimize coding agents. So what I'm showing you here, yeah, is like the tool set that they are using to be like, "How do we get the most out of Claude code at our company or Codex or something like that?"
</details>

>> 这一部分很清晰。
<details><summary>Original English</summary>
>> And that that part is clear.
</details>

>> 好的。我只想再强调几点，并不是为了单纯推销 Warp Factories，而是面向任何试图构建内部工厂的人——无论是否基于 Warp Factories——通用原则都在于：你必须达到这样一个状态，即一切皆有存储、一切皆可观察、一切皆可衡量，因为只有这样，你才能真正开始将工程严谨性应用到优化编码 Agent 的过程中。

你可能经常在 Twitter 上看到，大家总是在发推讨论：“你应该试试这个新模型，或者用这个新运行环境（harness）。哪个更好？是 Pi、Claude Code，还是 Cursor 等等？”

对此我们的看法是，而且整个行业真正需要的，是走出凭借感觉（vibes）来理解这些编码 Agent 的阶段，真正进入度量驱动的世界。

因此我们认为这是企业未来的必然走向。他们会希望部署一个像 Warp Factories 这样的系统——无论他们最终是直接使用 Warp Factories 还是自研——来收集所有这些信息，并提供观察编码 Agent 运行状态的全面手段。

我想提的另一项系统默认包含的能力，就是你可以在其周围创建各种自动化任务。我猜想很多人习惯在 Slack 中工作，但人们也在设置各种基于触发器的方式将任务输入工厂。

一旦你拥有了我之前展示的对工厂运行状况进行评分的视图，你还可以设置另一层 Agent 闭环——如今一切都在走向闭环——让这些 Agent 专门监控评分中的失败情况。它们在寻找运行不顺畅的地方，并尝试提出针对系统的修改建议以使其表现更好。

举个非常简单的例子，我们称之为“自优化”（self-improvement）：我们的自优化 Agent 在审查分诊步骤的执行效果。我们有一个分诊步骤，Agent 发现：我们有 54 个特定形式的失败案例，在这些案例中，如果分诊器能够派生出一个子 Agent（sub-agent）来进行调查，效果本可以更好。

因为你的整个工厂都是以代码形式定义的，而这些本身就是编码 Agent，它们所能做的——如果你愿意，你可以去查看它得出这一结论的原因——最酷的地方在于，它们实际上可以针对工厂的定义代码提交一个 Pull Request，试图优化工厂本身。

这是一个内置在系统内部的完整学习闭环，旨在实现真正的自我优化。我们目前还没上线、但下一步计划要做的是：对于任何此类提议的修改，你可以回溯、重放历史运行记录，验证该修改是否确实能带来改进。一旦拥有了合适的基础原语，对这些系统进行工程化改造的可能性就会变得非常强大。

在展开更泛化的讨论之前，我最后再展示一个功能。我认为这是各家公司都应该追求、且我们在内部发现极为有用的能力，那就是我们所说的“基准测试”（benchmarking）。

在这个语境下，在工厂的上下文中，基准测试本质上意味着：对于系统中运行的任何编码 Agent，你都可以将其加入基准测试套件中。这意味着你可以挑选一组与前端编码等任务相关的 Agent 历史运行记录。

一旦拥有了这些记录，你就有能力针对由不同配置组成的矩阵，重放完全相同的任务。

我非常坚信的一点是：不仅要允许变换模型，还要允许变换运行环境（harness）。在 Warp 中我们有自己的 harness，但我们允许你针对 Claude Code、Codex 或 Pi 进行基准测试。你可以选择模型。当你执行这样的测试时，最终得到的结果看起来会与 SWE-bench 或 TerminalBench 等公开发布的评测结果非常相似，但它是基于你自己公司的真实运行记录生成的。

例如，我们在这里看的是某组任务在成本与正确率之间的权衡关系。

你希望落在左上角，也就是追求最低的成本和最高的正确率。随着技术迭代过快，图中的这些模型稍微有点旧了，但基本思路在于：我们可以看到，GPT-5 6 在这组任务集上的正确率是 95%，但平均成本是 6 美元；而 GLM-5 35 的正确率是 93%，成本只有 2 美元。

最酷的是，你可以提取这些信息，并将其输入到专门为你自身工作流和代码库定义的模型路由策略中——坦白说，甚至是 harness 路由策略中。

如果要再次拉高视角，我认为这里最宏大、最强大的地方在于：你摆脱了盲目猜测，进入了我们所谓的“工厂工程化”（factory engineering）领域。你秉持的是真正的工程思维：面对编码 Agent 这一惊人的全新基础原语，作为团队和公司，我们如何确信自己是以正确的方式在部署它们？

因此，我们正在努力为企业构建实现这一目标的基础设施和工具。很多一直在尝试自研版本的公司，对这种方法产生了非常强烈的共鸣。这是我对“工厂”含义的一个快速概览。我可以先停下来听听你的想法。
<details><summary>Original English</summary>
>> Yep, cool. Yeah, and so like a a couple other things that I would just want to emphasize not to make this just like completely about Warp Factories, but like the general principle here for anyone who's trying to build their internal factory, whether it's on Warp Factories or not, is like you want to get to a spot where everything is sort of stored, everything is observable, everything is measurable, because that's when you can actually start to like apply engineering rigor to how you make coding agents better.

You know, you probably see this on Twitter all the time. Everyone is always tweeting about like, "You should check out this new model, or you should use this new harness. What's better? Is it Pi or Claude code or, you know, Cursor or whatever?"

And so what our opinion on this is and what the the world sort of needs is like out of the the realm of vibes for understanding these coding agents and actually into the world of measurement.

And so we think that this is the direction that companies are going to want to go. They're they're going to want to like put in place a system that's like Warp Factories, whether they actually use Warp Factories or they build their own, which collects all this information and then provides all this way to see how your coding agents are doing. I guess one of the thing I like to kind of take for granted that's part of this system is like you can create all these different automations around it. So like I I imagine people work in Slack, but people are also setting up a different trigger-based ways of putting work into the factory.

Once you you have this view that I showed earlier of uh like scoring how your factory is doing, you can also set up another kind of loop of agents, everything is kind of loops these days, where those agents are looking over they're looking for failures in your scores. Like, they're looking for things that aren't going well and trying to suggest changes to your system to make it go better. And so, like, a really simple example here, that we call this self-improvement, is like, okay, our self-improvement agents were looking at how well our triage step was doing. So, we have a triage step and they're saying, okay, we have 54 failure cases of this particular form where it would have been better if our triager had been able to spawn a sub-agent to do its investigation. And so, what they're able to do, and like, you could go look at like why it thinks this if you want, but the cool thing is like, because you have your whole factory defined as code, and these are coding agents, they can essentially make a pull request against the factory definition to try to improve the factory itself. And so, this is like a like a full learning loop that's built into the system to try to actually self-optimize. And like, we don't have this yet, but the next thing that we want to do with this is like actually for any suggested change like this, you could go back, replay the runs, and make sure that this actually would have improved them. So, the possibilities of like how you can engineer this stuff get pretty cool once you have the right primitives in place. And I'll show one last thing, and then we could sort of maybe talk more generally about the whole approach here. But the other thing that is um you know, I think companies should strive for, that we find very useful internally, is like the ability to actually do what we call benchmarking. And so, benchmarking in this context, in the factory context, means essentially the ability to like take any coding agent that's running your system, you can sort of add it to a benchmark suite, which means like, you know, you might curate a set of coding agent runs that were related to like doing front-end coding or something like that.

And then once you have that, you have the ability to sort of replay those same tasks against a matrix of different configurations. And so, you know, I'm a big believer in not just allowing you to vary the model, but also to vary the harness. And so, you know, in Warp, we have our own harness, but we actually will let you benchmark against Cloud Code or Codex or Pi. You can pick the model, and when you do something like this, what you end up getting is a result that looks very similar to like the published results for SweetBench or CriminalBench, but on your company's own real runs. For instance, we're looking at like a sort of cost versus uh correctness trade-off for a certain set of things here.

And like, you want to be in the upper left-hand corner, so you want like lowest cost, highest correctness. These are These models are now slightly older cuz the world's changing so fast, but the idea is basically, you know, we could see, okay, GPT-5 6 sole here was like 95% correct on this task set, but it cost six bucks on average. And GLM-535 was 93% and cost two bucks.

And then, the cool thing about this is you can take this information and feed it into a model routing strategy, or harness routing strategy, honestly, that's defined specifically for your own workflows and code base. And so, the you know, if I had to again to zoom out, the really big picture thing that I think is so cool and powerful here is like, you're getting out of the realm of guessing, and you're getting into what we call factory engineering, where it's like, you are taking a real engineering mindset. You're like, how do I We have this amazing new primitive of of coding agents. How do I know as a team, as a company, that we're actually deploying them in the right way? And so, you know, we're trying to build this infrastructure and tools for companies uh to do this. And like this approach is really really resonating with a lot of companies that have been trying to build, you know, their own their own versions of this. So, that's like a quick tour of like what do I mean when when I talk about factory? I can I can sort of stop talking for a sec.
</details>

>> 我确实认为，一种极具威慑力的打法在于：通过极强的思想引领，让每个人最终都试图去构建一个 Warp，哪怕他们并不直接使用 Warp。

在你们的落地页和演讲中，有几点我非常认同。比如“支持任意产品界面”（any surface），必须能适配任何界面；必须做到“工厂即代码”；必须有评估闭环。大家称之为 ADLC（Agent 开发生命周期）？我不知道你是否用这个词，看起来你还在用 SDLC。
<details><summary>Original English</summary>
>> I do think that, you know, the the the power power move, I guess, is to sort of thought lead so hard that everyone ends up trying to build Warp even if they don't use Warp. Yeah.

So, you know, you have on your landing page something I I like and in your talks you've they've done a few of these as well. Uh something I really like also is any surface, right? It really has to be any surface. It has to be factories as code. Um you have to have that eval loop. Like what is the whole Like people calling this the ADLC? I don't know if you use that term. It looks like you use SDLC still. You know, all all that stuff.
</details>

### 软件工厂的六层技术栈

>> 我是这样思考这个问题的。再次声明，不论最终是否选用 Warp——当然 Warp 完全专注于此，我们为此构建了出色的平台——但普遍而言，如果你想在这个领域构建系统，我建议将其视为一个技术栈，视为基础设施。

在技术栈的最底层，我认为最基础、最关键的是用声明式代码来定义你的工厂。这就像 Terraform 一样。你不仅能获得与 Terraform 相同的好处，甚至还要更多：

通过代码定义，你可以获得开发生命周期（无论是 SDLC、ADLC 还是 PDLC）的版本化视图。你可以在其之上创建分支并进行测试；如果不合适，还可以随时回滚。版本控制带来的所有显而易见的好处都得以保留。更酷的额外好处在于：因为它是代码，编码 Agent 可以直接对它提出改进建议。在我看来，声明式定义工厂是构建具备自优化能力的软件工厂的基石。

在这个架构栈中往上一层，是用于收集 Agent 产生的所有信息的存储层。

因为你希望能够审查这些信息，排查故障模式，或者用不同的变量重放过去的任务，从而从度量的角度真正优化你的系统。因此你需要数据支撑，需要 Agent 的对话记录和产出物，需要各工具达成某个结果的完整交互记录。

这意味着一个工厂对话可能始于 Slack，随后进入 Linear，接着转入 GitHub，伴随有代码审查评论，整个交互过程最终形成一段被合并的代码。甚至可能在发布后引发了服务器崩溃。你希望拥有追溯能力——多半是借助一个 Agent，当然也可以由人工来进行——去诊断：当初如何才能做得更好？其中的失败根因是什么？

再往上，你还需要数据输入系统的通道。你需要接入 MCP 的途径。我们发现，随着企业规模扩大，不同部门需要不同的访问权限。例如市场团队、销售团队和工程团队分别能访问哪些 MCP。如果你要在一定规模的组织中推行这套体系，根据企业体量，这里会涉及不少复杂度。

你还需要一个计算层，应该将其视为独立的模块。目前显然有很多 Agent 沙箱提供商。如果你打算采用第三方沙箱，我建议将其设计为可插拔的。我们在内部主要使用 Namespace。
<details><summary>Original English</summary>
>> This is how I would think about it. Again, whether it's Warp or not, if it's I would obviously, you know, Warp Warp is is this is what we're fully focused on. We have an awesome platform for it. But just in general, what I would think about if you are trying to build something in this space is A, I would view it as like a stack. So, as infrastructure. At the bottom of the stack, I think it's really foundational and important that you define your factory declaratively as code. So, again, the analogy is like Terraform here. You get the same benefits, but actually more. So, the benefits you get uh from defining as code is like you get a versioned view of like what was your we SDLC I DLC PDLC, whatever DLC you want. You get a version view of that. And then you get the ability to create branches off it, which you can test. You get the ability if you change it to revert it. So, all the obvious things about source control that are great. And then you get the added benefit that's extremely cool where because it's in code, coding agents can suggest improvements to it. So to me this is like the foundation of a self-improving software factory setup is define your factory declaratively.

The next step up in this stack as you think about architecting it is some place to gather all of the information that agents are producing. Cuz what what you want to be able to do is examine that information, look for failure modes, or replay those same past tasks with different variables to sort of I don't know scientifically is the right word, but from a measurement standpoint really optimize your system. So that's the mindset. So you need the data to do that. You need the agent conversations, and you need the agent artifacts. You need a record of all of the interactions from all of the tools to get to a result. And so what I mean by that is like you might have a a factory conversation that starts in Slack and then continues into linear, and then continues into GitHub, and there's a code review comment, and that whole interaction is going to result in some piece of merged code. In fact, it might even result in something that gets shipped and then has a server crash. And you want the ability to like retroactively go back with an agent most likely, but you could do it as a person and and diagnose how could that have been better? What was the failure in it?

You also need This part will seem fairly obvious, but you need a way of getting data into this system. So you need some way of plugging in MCPs. And then we find that as companies get bigger, they want different access for different parts of their organization. So they want things like what MCPs can the marketing team access versus the sales team versus the engineering team. And so like again, you'll you'll find there's a bunch of complexity if you depending on how big your organization is if you're trying to roll something like this out.

You really want a compute layer. You should think of that as a separate thing. And so there's there's obviously a lot of agent sandbox providers at this point. So if you're going to use a third-party one, I would make just make that pluggable. We use namespace as our primary one. Um
</details>

>> 噢。
<details><summary>Original English</summary>
>> Ooh.
</details>

>> 他们在 AI Europe 上发布的。Namespace 非常出色，但这一层必须是可插拔的，我认为这至关重要。因此如果你想用 Daytona、Modal 或 E2B 等，架构设计上应保持其可插拔性。根据具体需求，你还要确保支持不同的运行平台。默认情况下大家通常使用 Linux 沙箱；但对于计算机使用（computer use），比如我们测试 iOS 应用的方式，你就需要运行 Mac 虚拟机，实际启动模拟器并在里面点击交互。

我们对推理层采取了非常开放的态度。这非常符合我们追求极高灵活性的理念。我们发现很多公司目前与 Anthropic、OpenAI 或 Google 签有预付消费协议，需要去消耗这些额度。因此我们提供了广泛的灵活性：你可以接入自己的推理提供商，也可以通过我们采购推理算力。你甚至可以接入自己的 harness，我认为这非常关键。你可以编排像 Pi 这样的工具，基本上只要是 ACP 兼容的 harness 都可以。

接下来你需要优化层（improvement layer）。这就是我在演示中展示的部分：整套系统的真正威力在于优化能力。分享一些 Warp 的实际数据：当我们刚开始采用工厂模式时，每个 PR 的成本大约是 80 美元，因为我们在不该用 Opus 的地方用了 Opus，分诊 Agent 跑在极高配置的模型上，而且 Agent 的结构存在大量冗余——比如相较于精简的 Agent 组合，我们派生了过多的子 Agent。

随后，我们利用这些内置功能进行了大量的内部调优和测试，成功将单个 PR 的成本降低到了 15 至 20 美元左右。与此同时，我们可衡量地提升了 PR 的吞吐量：在过去一个月中吞吐量提升了 40%。我们持续监控代码回滚率（revert rate），它并没有上升。因此，我对这种“观察、度量、调优”的通用路径抱有极大信心。

最后，你需要某种编排器（orchestrator）。有时人们谈论编排器时，仿佛它代表了整个平台，我认为它只是其中一个组件。我所说的编排器是指：你需要一个系统来读取工厂的定义代码，推进工作流在不同阶段流转，调用正确的模型，加载正确的技能等等，并触发相应的自动化任务。

最上层则是各种访问入口点。在这个环节，大家的理念可能有所不同，而我们的理念是把工厂引入企业现有的知识工作工具中。最显而易见的例子就是 Slack，我们内部大约 60% 的工作都是从 Slack 发起的。但有时从任务跟踪系统发起更合适；有时对于习惯在终端中使用 Claude Code 的工程师来说，在终端完成一部分工作后把规范（spec）提交到工厂更为顺畅。

因此，我们的理念是让整套系统完全由 API 和 MCP 驱动，使工厂本身成为一种无头（headless）基础设施，对外暴露各种不同的接入入口。当我们向企业展示这种分层视角时，反响非常积极。大家会觉得：“是的，这很合理。这是开发者基础设施栈中的一个新物种。”它处于 CI/CD 靠前一层的位置，但我认为未来大多数软件开发公司都会拥有类似的系统。
<details><summary>Original English</summary>
>> They launched it at AI Europe. Namespace is awesome, but this should be pluggable. I think that's really important. So if you wanted to use Daytona or Modal or E2B or whatever, like I would architect it so this is a pluggable component of it. I would make sure, depending on your requirements, that you can do different platforms. So again, by default, you know, I think you'll probably want to use like a Linux-type sandbox, but for computer use, like the way that we test like iOS apps is you're going to want to have the ability to run a Mac VM and actually like have it run the simulator and click around. We have a very open approach to inference.

And this is like this is very much with our ethos of trying to be super duper flexible. So we find that a lot of companies right now will have pre-existing commits with Anthropic or OpenAI or Google that they want to burn down. And so we're we provide like a very big variety of like you can plug in your own inference provider or you can buy inference through us. You can even plug in your own harness, which I think is a pretty big deal. So you know, you you can orchestrate things like pie like I mentioned earlier. Basically any ACP-compatible harness. And then you want this improvement layer. And so this is some of the stuff that I showed in the demo where it's like the real power of this whole system is is the ability to improve it. And so just to give some stats at Warp, when we first started using the factory approach, it was costing us about $80 per PR because we were using like Opus where we shouldn't have. Our triage agent was using like a really high-powered model. You know, we were doing a bunch of redundant work with our the shape of agents. Like we were doing too many sub-agents relative to just having fewer agents. And so we basically did a whole bunch of internal tuning and testing using these built-in features, and we were able to get the cost per PR down to like 20 bucks or 15 bucks, something like that. Well, we can measurably improve the throughput of our PRs.

Over the last month, it's gone up by 40%. We measure like the revert rate, and it hasn't gone up. And so, I really feel like a lot of confidence in this general approach of like observe, measure, tune.

Finally, you need some sort of like orchestrator. Sometimes people talk about the orchestrator like it's the whole platform. I think it's a piece of it. What I mean by orchestrator is like you need some system that will take the factory definition code, and then actually move work along the different stages, calling out to the right models, loading the right skills, etc. You need something that will fire the right automations.

And then finally, you need a bunch of access points. And again, our philosophy with this, which you can I could see people have different philosophies. Our philosophy is to sort of bring the factory into a company's existing knowledge work tools. So, think of like, you know, the most obvious one is Slack, and like we're doing like 60% of our work is starting in Slack. But sometimes it makes sense to start in the task tracker. Sometimes it makes sense for for a developer who is more comfortable using like cloud code in their terminal to do a bunch of work there, and then submit a spec into the factory. And so, you know, our philosophy is to try to to make this whole thing API driven and MCP driven, so that the factory itself is like a piece of kind of headless infrastructure where it has all these different entry points. So, I think this this stack-based view of it, when I've shown it or we talked to companies, seems to land very well. It's like, okay, yes, this this makes sense. This is a new thing in the like developer infrastructure stack. It kind of sits one level back from like where CI/CD is, but I think most companies will have something like this for software development.
</details>

>> 这确实包含很多层级。我还从没见过有人像你这样把它完整拆解出来。

我在想——因为我担任 Cognition 的顾问，也了解 Cursor 等产品——它们都在尝试对从底层到顶层的某些层级进行打包捆绑。所有软件行业都存在一定程度的捆绑与解绑。因此这里有一个关键问题：作为一家 B2B SaaS 公司的 CTO，我只想做好我的本职工作，[笑声] 我真的需要所有这六个层级吗？
<details><summary>Original English</summary>
>> Yeah, that's a lot of layers, actually. I've never actually seen it spelled out like like you have.

I wonder because I think most, you know, I advise Cognition and I've seen I, you know, Cursor, what are all these words? They all try to do some bundle of like the like from bottom to top.

And there's a little bit of bundling unbundling with all software. And so there's a critical question of like Look, I'm trying to do my job here as CTO of a, you know, a B2B SaaS. Like

>> [laughter]

>> do I need like all these like six layers?
</details>

### 适用规模与“Happy Stack”

>> 我认为核心问题在于：这是为谁准备的？与我们交流并产生最强烈共鸣的企业，必须具备一定的人员规模。如果是几个人的团队，坦白说这纯属杀鸡用牛刀。千万别这么做，直接买 Claude Code 订阅或 Codex 订阅，你们的开发速度会更快。你大概不需要这套系统。
<details><summary>Original English</summary>
>> I think it's like who's this for? Maybe is is the kind of the question. So, when we talk to companies that where this resonates the most is it has to be a company that has some some amount of scale. Like this is if you're like a few people honestly, this is this is overkill. Don't do this. Use the Cloud Code sub or the Code X sub or whatever and just you'll go faster. You probably don't need
</details>

>> 你也可以使用它。对于任何大型团队的技术栈也是同理，对吧？在某个阶段，你会从单打独斗模式转变为“我们需要一套平台系统来加速整体进程”。
<details><summary>Original English</summary>
>> You could use this. Yeah. Same for like any like larger team stack, right? Like you at some point you switch from like Fire Yolo, whatever to we actually need a platform system here to accelerate everything.
</details>

>> 没错。企业需要达到一定的规模。我们观察到，大约 5 到 10 名工程师可能是这套方案开始体现合理性的门槛。

向上延伸到非常大型的企业，他们都想要类似的体系。公司越大，落地所需的实施工作就越多。如果你在 Cognition 工作过，或者了解 Cursor 的企业落地，想要在企业自有的基础设施内部搭建起这样的系统，绝非纯粹的即插即用。团队内部开发环境的复杂度会随着规模膨胀。

但在中间地带存在大量公司，比如拥有 10 到 100 名工程师的快速成长期初创公司，落地实际上非常偏向自助化。如果他们使用的是一套标准的集成栈（happy stack），比如 Slack、Linear、Jira……
<details><summary>Original English</summary>
>> Exactly. Yeah, so you have to be a certain scale. We start seeing that maybe around like five to 10 engineers would maybe be the floor where this makes sense.

And then all the way up to to very large companies, they want something like this. The bigger the company the more that this requires you know, implementation work. Like I'm sure if you're, you know, you're working with Cognition or or I don't know if Canvas Cursor does, but you know, to get something stood up like this within a company's own infrastructure, it's not going to be purely plug-and-play. There's like you know, the sort of complexity of a team's internal developer setup just grows with size.

Within like but there's a bunch of companies where, you know, maybe like it's like a 10 to 100 engineers fast growing like growth stage startup where it is pretty self-serve, actually, where it's like you just if they're using like the happy stack of like Slack you know, linear, Jira
</details>

>> 等等，你刚才称它为什么？“Happy Stack”？
<details><summary>Original English</summary>
>> Hang on, did you call it the happy stack?
</details>

>> 我管它叫……是的，我无意冒犯 Teams 或其他工具，但在初创公司中存在一组非常普遍的集成工具，你可以直接把类似系统接入进去，无需繁琐配置就能立即产生价值。

不知道你平时工作模式如何，但如果你与 Devin 等工具协作，在原生支持多人的协同环境（如 Slack 或 Linear）中工作时，你能体会到类似的好处。将工厂作为中央记录系统会带来很多意想不到的优势：通过 Slack 集成，信息流可以一部分来自服务器故障频道，一部分来自用户反馈频道，你可以直接将它们喂给工厂去执行任务。工厂可以根据代码库知识分布，自动拉入团队中的多位成员参与。

因此，你不需要达到特别庞大的规模就能发挥其价值；但对微型团队确实不合适。它最适合那些希望建立正确基础设施的公司，从而在底层模型和 Agent 持续演进的过程中，团队拥有一个可以不断积累的系统。
<details><summary>Original English</summary>
>> I call it like yeah, I that's like our I don't know no no no shade to to teams or whatever like sure, but like there's like a you know, like a set of integrations that I find very common at startups where you can plug something like this in and get like immediate immediate value without too much set up.

I don't know if you how much you're working like this, but if you're working with like Devon or something, you can kind of get some of the same experience where when you're working in a some environment that's natively multiplayer, so like Slack for instance or linear there's all these benefits that you might not realize just by having like this central system of record where you can have, you know, for like the Slack integration for instance, it's like you can get some flow of information coming in through like a server crash channel and some through a user feedback channel. You can just feed that directly into the factory to have it do the work. The factory can loop in multiple people on your team depending on who knows the right part of the code base. And so yeah, I don't think you have to be that big for this for this to make sense, but it definitely doesn't make sense for us for a small team and it really makes the most sense for a company that's like I want to I want to put in place the right infrastructure so that as models and agents continue to change, we have a system that we're building upon.
</details>

### 最强质疑：订阅套利与商业模式

>> 这里包含的信息量很大。最后一个问题，之后请你介绍一下你在 AIE 上的演讲以及大家可以在哪里关注你。

搭建这整套体系最强有力的反面论点（steel man criticism）是什么？当你遭遇批评或推迟采用的声音时，大家遇到的是怎样的现实阻碍？
<details><summary>Original English</summary>
>> There's a lot to go on here. The the one final one final question and then I'm going to have you plug your AIE talks and just generally where to where to follow up with you.

If you what is the most steel man criticism of setting up all this? Like that when you encounter criticism or pushback, what should people know as like here here is like what people are running into?
</details>

>> 我分情况来回答。有一类特定客户，我认为采用这套体系确实不太合理……
<details><summary>Original English</summary>
>> I'll answer this in like there's a certain class of customer where I don't think it makes sense to like go on to this particular thing and that's like
</details>

>> 是的，在团队规模之外的原因。
<details><summary>Original English</summary>
>> Yeah, and beyond the size thing, yeah.
</details>

>> 我们目前遇到挑战的地方，是那些拥有高度定制化基础设施的企业，或者像 Uber、Ramp 这样的公司，它们不是我们的目标客群。它们在自研专属系统，拥有庞大的内部平台开发团队。

但撇开团队规模不谈，我认为对于某些人来说，直接使用订阅制显然更经济划算。比如小型和微型团队。不过这又绕回了规模问题。
<details><summary>Original English</summary>
>> Where we have challenges right now are companies with very very bespoke infrastructure or companies with like our our kind of not a good fit customer for this for instance would be like Uber or ramp. Like they're building their own thing. They have very large internal developer teams.

But apart from the size thing, I'm thinking like I mean there's definitely like the for some people they should it's just going to be more economical to just use the subs. Like for small and very small teams. But that comes back to the size thing.
</details>

>> 是的。我并不想略过订阅这个话题，因为很多人直接按 API 计费去调用，其成本比购买一堆订阅账号要高出 5 到 50 倍。真的有人这么做吗？这是否严重违反服务条款，以至于大家根本不该尝试？
<details><summary>Original English</summary>
>> yeah. I don't want to actually omit the subs stuff because I think a lot of a lot of people go straight to API of pay by API and that is between 5 to 50 times more expensive than just getting a whole bunch of subs. Do people do that? Is is that like so against terms of service that like just don't bother or like
</details>

>> 我们接触过很多小公司，他们会说：“这个系统看起来太棒了，我们很想要，但我们目前是在轮流使用一批 200 美元的订阅账号。”我心想这总不至于轮流用 17 个不同的订阅吧？你很难想象这是被允许的做法，但说实话，我确实也不太清楚。
<details><summary>Original English</summary>
>> Talk to like a lot of small companies we talk to where they're like oh this system seems amazing. We want this but we're on these like collection of $200 subs that we're rotating through. I'm like it's probably not like 17 different subs, right? And then you can't imagine that's allowed but I I don't the truth is I just don't really know.
</details>

>> 但他们确实在这么做，坦白说，如果你能这么干，那绝对是最便宜的方式。但这样做会失去很多其他收益，而且无法扩展；如果公司规模发展到一定程度，肯定不被允许这么操作。但这在现阶段确实存在。
<details><summary>Original English</summary>
>> But like they they are and it's it's like and it makes like honestly it's like if you can do that that's going to be the cheapest way. But you you you do lose a whole bunch of other benefits if you do that and it's not a scalable thing and if your company scales to a certain point they're you know, you're definitely not going to be allowed to do that. But it's like it it makes sense.
</details>

>> 是的，我只是想说明补贴的力度有多大。比如一个 200 美元的套餐，你相当于获得了价值 8,000 美元的 API 额度，对吧？
<details><summary>Original English</summary>
>> Yeah, I'm just you know, I'm just saying like that's the extent of subsidy. Like you get for like a $200 plan you get 8,000 of API. Right?
</details>

>> 是的，非常夸张。
<details><summary>Original English</summary>
>> Yeah, it's crazy.
</details>

>> 这笔钱可不是个小数目。
<details><summary>Original English</summary>
>> That's not that's not money to sneeze at.
</details>

>> 确实。纯粹从商业角度来看，这也是我不想涉足纯编码 Agent 业务的原因之一：你无法在一个成本高得多的底座之上，打造出具备竞争力的编码 Agent，这就是现实。Cursor 做得非常出色，他们跑通了这一步，随后我认为他们达成了极佳的退出路径，转型成为了模型实验室，因为我认为他们充分认识到了背后的经济学逻辑。

Warp Factories 的优势在于，我们卖的不是转售 Token 的产品。我们推向市场的是一套编码 Agent 优化平台和生产力平台。在这款产品上我们不参与转售 Token 的竞争，这是一种优势。如今市面上仅剩少数独立的编码 Agent 工具，我不知道他们未来该如何维系。
<details><summary>Original English</summary>
>> No, I don't know. And it's like it's one of the I mean just from like a business perspective it's one of the reasons that you know, I I don't want to be in like the pure coding agent business because you just can't you can't build a on top of a Build a competitive coding agent on top of a that cost so much more money and like that's just the reality. I mean cursor was brilliant. They did it. And then I think that they had a perfect exit and became a model lab because I think they fully realized the economics of it. And so yeah, the the cool thing about warp factories is like we're actually not we're not trying to pitch like a token reselling product. We're trying to pitch basically an you know, a coding agent optimization platform and a coding agent like productivity platform. So we were we're not in that game with this product which is a strength and like that game is I know there's still a few independent coding agents out there. I don't know how they're going to how they're going to do it.
</details>

>> 基本只剩下 Cognition 和 OpenCode 了，就这些。当然还有你们。

最后请为你的演讲做个宣传，大家会去现场听讲，我们也会提供线上直播。请为我们勾勒一下你最近一直在构建的思考脉络，以及你接下来要分享的核心内容。
<details><summary>Original English</summary>
>> It's basically cognition and open code. That's it. Oh and in fact you of course.

Let's wrap up with like little plug for your talk and people will come see you and we'll we'll live stream it and all all that but give us a general arc of the the sort of series that you've been developing and where where you're going to talk about next.
</details>

### 未来展望：工厂工程化作为新学科

>> 这场演讲将聚焦于：在这个工厂工程化日益普及的世界里，身为一名工程师究竟意味着什么？你的角色是什么？你的工作会变成怎样？产品工程（product engineering）与工厂工程（factory engineering）这两类工程角色分别是什么？如果用“工厂工程化”这个词来定义一门新学科，它究竟长什么样？需要用到哪些工具？

作为工程师，你该如何培养合适的能力，从而去工程化构建“用于生产软件的系统”，而不仅仅是直接编写软件本身？
<details><summary>Original English</summary>
>> What the talk's going to focus on is what it looks like to be an engineer in this world of increasing factory engineering and like what it what are what are your roles? What's your job going to be? What are the two types of engineering product engineering factory engineering and then what is this new discipline if you want to use the word of factory engineering actually look like? What are the tools? How do you as an engineer build the right skills so that you're engineering the system that builds the software and not just building the software directly.
</details>

>> 这是极其精彩的总结和概览。如果大家想与你交流，应该去哪里找你？如果你们在招人，招聘哪些岗位？有什么行动号召吗？
<details><summary>Original English</summary>
>> That is a perfect recap and overview of if people want to talk to you where should they find you? If you're hiring what are you hiring for? Anything that's like a call to action?
</details>

>> 欢迎访问 warp.dev，大部分内容都在上面。我们正在招聘工程师、GTM 市场拓展团队成员、数据团队成员，还在招聘一名设计师，覆盖了大量岗位。

如果你对我关于软件工厂的思考感兴趣，我经常在 Twitter 上发布内容，账号是 Zach Lloyd tweets。欢迎关注，我会持续分享我的见解。
<details><summary>Original English</summary>
>> Yeah, so come check out warp.dev. So most stuff is there. We're hiring engineers. We're hiring on our go to market team. We're hiring on the data team. We're hiring a designer. So hiring up for a whole bunch of roles. If you're interested in like my my musings on factories, I I put out a lot of content on my Twitter now. So Zach Lloyd tweets. So come come follow that.

I'll keep sharing how I'm thinking about it.
</details>

>> 一定关注。非常感谢你抽出时间，Bo。

太棒了，感谢邀请我。
<details><summary>Original English</summary>
>> We'll do. We'll do. All right, thanks so much for the time, Bo.

Cool. Thanks for having me.
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>