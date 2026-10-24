---
author: How I AI
date: '2026-09-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4_SHhSMHzNo
speaker: How I AI
tags:
  - software-factory
  - ai-agent
  - devops
  - continuous-integration
  - automation
title: Warp CEO 详解软件工厂：Agent 如何重塑端到端开发流程与管理范式
summary: Warp 创始人兼 CEO Zach Lloyd 深入剖析了“软件工厂（Software Factory）”的定义与落地实践。对话探讨了如何通过 Slack 驱动多 Agent 协作、打通从需求到 PR、端到端自动化测试、多模态验证（Computer Use 录屏）、自我改进（Self-Improvement）闭环以及工程管理度量指标（如单 PR 人类交互次数）。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Warp
products_models:
  - Claude
  - Slack
  - Figma
media_books: []
status: evergreen
---
### 软件工厂与人类瓶颈

**Clarvo**: 我能向你抛出一个尖锐的问题吗——人类其实才是真正的瓶颈所在？因为如果你观察从任务启动到提交 **PR**（Pull Request）的时间，只需要 35 分钟；但如果你看从 PR 提交到首次人类审查的时间，却要长达 3.5 个小时。而且上个月你们团队一共处理了超过 2,000 个 PR。在这样的节奏下，你如何防止团队陷入所谓的“混乱统治”？

<details>
<summary>Original English</summary>

**Clarvo**: Can I give you a hard time that humans really are the bottleneck? Because if you look at kickoff to PR time, it's 35 minutes, but if you look at PR to first human review, it's 3 and 1/2 hours. And when you're doing I think it was like over 2,000 PRs in the last month. Like how do you keep things in the team from going as I say like chaos reigns?

</details>

**Zach Lloyd**: 到底什么是**软件工厂**（Software Factory）？至少对我们来说，它是一个具体的名词。它更像是一个产品概念，由一系列代码仓库（Repos）、一堆 **MCP**（Model Context Protocol）服务器、大量的系统配置，以及本质上的一组 **Agent** 共同构成。

这里面包含了代码审查 Agent、设计相关的不同 Agent、各种自动化流程，而且这一切完全以代码的形式被定义。评分与评估机制贯穿于所有的运行过程。不仅如此，系统还包含当前在 Twitter 上非常热门的第二重循环——即所谓的**自我改进**（Self-Improvement）。在这个闭环中，观察者 Agent（Observer Agent）能够主动为你的软件工厂生成更新，从而专门针对性地预防某种特定的失败模式。

其中最有帮助的功能之一，就是可以让工厂内的 Agent 进行 **Computer Use** 级别的端到端验证。比如在某个任务中，它甚至录制了一段操作视频。我现在就像是在与一个正在接管我过去 20 年所做工作的系统对话，而且它现在的表现甚至有点比我还要好。剧透一下：人类确实成了瓶颈所在。

<details>
<summary>Original English</summary>

**Zach Lloyd**: What is a software factory? For us at least, it's an actual noun. It's like a product concept where it consists of a bunch of repos, a bunch of like MCP servers, like a bunch of configuration and then a bunch of agents essentially. So like a code review agent design different agents, different automations and it's all defined in code. Scoring happens across all runs. But then there's a second loop popular thing on Twitter right now called self-improvement where you have like an observer agent and it can then create updates to your factory that will try to prevent the particular failure mode. One of the things that's most helpful is like you can have these factory agents do computer use verification. So in this case it made a video. I'm just like talking to this thing that is doing this job that I've done for the last 20 years and it's now it's like doing it kind of better than me. Spoiler alert, the humans are the problem.

</details>

**Clarvo**: 欢迎回到《How I AI》。我是 Clarvo，一名产品负责人和 AI 狂热爱好者，致力于帮助大家利用这些新兴工具更好地构建产品。今天我们邀请到了 **Warp** 的 CEO **Zach Lloyd**，他将为我们现场展示“软件工厂”到底意味着什么。他将向我们演示如何在 **Slack** 中直接启动任务、如何超越传统的软件开发生命周期（SDLC），以及一位技术型 CEO 如何借助 AI 驾驭非技术类工具。让我们马上开始。

本期节目由 **DX** 赞助播出。在最近一项针对 500 多家工程组织的调研中，DX 发现过去一年中企业在 AI 工具上的支出激增了 28 倍。AI 工具在整体工程研发预算中的占比正在迅速上升，但工程管理层却面临着一个关键挑战：如何衡量这些支出的实际业务回报。这就是为什么顶级团队选择使用 DX 的原因。DX 能够清晰地向你展示 AI 的实际采纳率、具体使用场景以及投资回报率（ROI），从而让你基于客观事实而非行业炒作做出投资决策。欢迎访问 getdx.com/howiai 预约演示并获取独家研究成果。

感谢大家，今天我们非常荣幸邀请到 Zach Lloyd。Zach，欢迎来到节目！

<details>
<summary>Original English</summary>

**Clarvo**: Welcome back to How I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Zach Lloyd, CEO of Warp, and he's going to show us exactly what he means by the software factory. He's going to show us how you can kick off tasks in Slack, what it means to go beyond the software development life cycle, and how a technical CEO uses non-technical tools with AI. Let's get to it. This episode is brought to you by DX. In a recent study across more than 500 engineering organizations, DX found that spend on AI tools has grown 28x over the last year. The share of AI spend in overall engineering budgets is climbing fast, but engineering leaders are dealing with a key challenge: how to measure the actual business return on this spend. That's why top teams use DX. DX shows you real AI adoption, specific use cases, and ROI, so you can make decisions backed by facts, not hype. Visit getdx.com/howiai to book a demo and grab the research. Thanks, and today I have the pleasure of being joined by Zach Lloyd. Zach, welcome to the show!

</details>

**Zach Lloyd**: 非常感谢你的邀请，很高兴来到这里。

<details>
<summary>Original English</summary>

**Zach Lloyd**: Thanks for having me. Excited to be here.

</details>

### 从传统 SDLC 到自动化流水线

**Clarvo**: 社交媒体时间线上目前充斥着各种趋势，但我认为 2026 年（乃至当前）最重大的趋势之一就是“软件工厂”。过去我们常说软件开发生命周期（SDLC），而现在大家开始将其视作一种流水线式的制造过程：输入想法与规格说明，输出交付产品。这种模式真的现实吗？它在 Warp 内部究竟是如何运作的？

<details>
<summary>Original English</summary>

**Clarvo**: There are a lot of trends on the timeline right now, but one that I think is going to be big for 2026 or seems to be big right now is this idea of the software factory. Historically, we had software development life cycles and now people are starting to think of this as like you put idea and spec in, you output product. Is that real? How how does that really work?

</details>

**Zach Lloyd**: 是的，它确实在以这种方式运作。在我看来，软件工厂主要面向两种不同的人群角色。我可以在 Warp 内部实际展示给大家看。

第一种角色是个人开发者或构建者（Builder）。比如在我们的 Slack 内部，我们有一个名为 `@Wilson` 的 Agent。你可以随时呼叫 Wilson 并对它说：“嘿，帮我们做一个这样的功能。”当你这么做时，Wilson 不仅仅做最直接的单步工作，它还会启动一系列完整的端到端任务流。

<details>
<summary>Original English</summary>

**Zach Lloyd**: Yeah. So, it kind of works like that. Um the the way that I think of of factories is like there's there's basically two types of personas who are using them. So, there's I'll show you like basically how we do this in warp. There's the builder, so like the individual persona where um inside Slack we have this agent named Wilson. And you can say, hey, Wilson, like I'd like you to build something for us. And when you do that, uh, what Wilson will do is like essentially do not just like the direct work, but kick off a whole bunch of steps.

</details>

**Clarvo**: 对于那些还在努力理解“什么是软件工厂”的人来说，过去一个想法需要经历很多手工环节：沿着产品传送带进入缺陷追踪漏斗，然后人工编码，再进行 QA 测试，接着通过特定的验证流程贴上合格标签，最终部署上线。

而现在你所描绘的图景是：通过在 Slack 中呼叫一个 Agent，所有的前置步骤都被浓缩并自动触发了。这是不是意味着它把从想法到 PR 的整套流水线都打包封装起来了？

<details>
<summary>Original English</summary>

**Clarvo**: Yeah. And you know, I think what I'm reflecting for folks who are maybe still trying to grapple with okay, like what's a factory, it's this idea that an idea needs to go through several steps. It needs to go down the conveyor belt of product and into like the funnel of issue tracking and then we need to code it and then we need to QA it and then we need to have these very specific verification loops where we can take our sticker and say quality control past, and then we ship it. And what you're showing here is that by starting in Slack with an agent, it's running a whole set of those steps, right? Like it's encapsulating that whole conveyor belt from idea to PR, is that right?

</details>

**Zach Lloyd**: 确实包含了这部分。它覆盖了更广泛的软件开发生命周期，自主完成更多的环节，并且在幕后协调多组 Agent 协同运作。

但对我而言，工厂理念还有一个更庞大的核心维度。刚才我展示的是从个人构建者的视角来看。但工厂方法最根本的不同点在于：**一切都在云端集中化管理**。

这里有一整套专门面向工程管理者的全新控制台。在过去，如果作为工程负责人或工程副总裁，你可以查看 CI/CD 指标、DORA 指标、PR 吞吐量等。但现在，我们开始度量全新的指标维度。比如在过去 30 天内，我们启动了 1,885 次工厂运行，生成了 2,168 个 PR，其中 1,220 个已合并。更重要的是，我们度量了诸如**平均每次 PR 的人类交互次数**（Human Interactions per PR，当前为 1.2 次），以及从启动到生成 PR 的耗时（平均 35 分钟）。

<details>
<summary>Original English</summary>

**Zach Lloyd**: That's that's definitely part of it for sure. It's like it does it does more of the the software life cycle. So it does more of the steps autonomously and there are like agents orchestrating agents under the hood. The there's a a whole other bigger part of it to me which um is so I showed you this from like the perspective of the the individual builder. If you're managing this, it looks very different. But what's really different in the factory approach is that everything is like centralized in the cloud. And there's a whole like manager dashboard. So in the past, if you're like a head of engineering or VP of engineering, you might look at like CI/CD metrics, you might look at DORA metrics, you might look at like PR throughput. We're looking at things like over the last 30 days, we've had 1,885 factory runs, 2,168 PRs created, 1,220 PRs merged, human interactions per PR, 1.2, kickoff to PR time, 35 minutes.

</details>

**Clarvo**: 终于有专门给管理者使用的工具了！（笑）

<details>
<summary>Original English</summary>

**Clarvo**: Finally something for the managers. [laughter]

</details>

### 管理度量新范式：单 PR 人类交互次数

**Zach Lloyd**: 哈哈，这不正是大家一直想要的吗？之前大家对一线构建者关注太多了。不过严肃地说，作为工程组织负责人，你现在最关心的问题是：瓶颈到底出在哪里？

最根本的洞察在于：人类是软件生产链条中的终极瓶颈。当然，人类也是最核心的创造力源泉。但通常来说，企业希望在 Warp 中实现的是更高程度的端到端自动化——将那些本就可以通过 Agent 独立完成的事情彻底交给 Agent。

你越是频繁地需要去微调、引导或纠偏你的 Agent，你的整体研发吞吐量就会受到越大的限制。在工厂的世界里，这就好比你在运营一家特斯拉超级工厂：你究竟需要人工介入流水线多少次，才能让一辆车顺利组装下线？

<details>
<summary>Original English</summary>

**Zach Lloyd**: It's what everyone's been wanting, right? Too much attention on the builders. No, but in all seriousness, if you're like running an engineering org now, you're like, where's the bottleneck? You know the sort of instinct underlying this is that um we are going to be not not to put this the wrong way but it's like humans are the bottleneck in terms of production and software. They're also the the creative force. Um, but in general, what companies want and we're, you know, we're trying to build for companies at warp largely is like how do you automate more? How do you make things that can truly just be done agentically be done? And the more times you have to steer or like like cajul your agent, that's like that's going to be a limiter on throughput. In a factory world like this is like imagine you're running like a Tesla plant or something. It's like how many times do you have to stop the line or like take manual intervention to make a car go down the conveyor belt?

</details>

**Clarvo**: 快速插一句，作为一个曾经的 CTO，我对这个指标非常着迷。你所说的“人类交互”具体指什么？是指前期的 Prompt 编写、过程中的人工干预，还是 PR 评审？

<details>
<summary>Original English</summary>

**Clarvo**: And quick question, are those just because my mind I mean I you know, as a one-time CTO, I'm like, yeah, this is exactly the metric I want to be tracking. Are these interactions do you think of these interactions as like the prompts, the sort of like upfront steering? Are you thinking about this as review interventions? Like human interactions per PR. Just yeah talk us through why that because honestly I haven't heard that one before and I like it.

</details>

**Zach Lloyd**: 实际上它涵盖了上述所有内容。当然随着时间推移，这套定义还会不断演进。你可以看到，从任务 Kickoff 到生成 PR，平均耗时 35 分钟；但从 PR 生成到首次人类介入审查，平均需要 3.5 小时。人类审查往往需要几小时甚至几天，这正是造成积压的原因。

如果未来我们能够将代码审查本身也交给工厂里的专用 Agent，那么整体研发效率将实现数量级的跃升。

<details>
<summary>Original English</summary>

**Zach Lloyd**: It's it's all of those. So because the and again I think this could definitely be refined over time and bear in mind we're like trying to figure out so what is this new world look like? But like here's another chart. So this is like kickoff to PR is 35 minutes. But then PR to first human review is 3 and 1/2 hours. Right. So like human review takes hours, sometimes days, and it's like that's what backs the queue out. Um, also just so you have good capacity for high quality human review on the things that really matter.

</details>

**Clarvo**: 100% 认同。在 Agent 时代，代码审查在很大程度上转变为一种**风险管理**（Risk Management）机制。

<details>
<summary>Original English</summary>

**Clarvo**: 100%. Um, I think code review becomes an exercise in risk management.

</details>

### 工厂核心架构与多 Agent 协同

**Zach Lloyd**: 没错。我来展示一下工厂内部的其他关键机制。

在这里你可以对所有的 Agent 运行进行抽样评估与打分。比如系统会自动将运行任务分类，并标记出各类情况：例如某次任务中 Agent 编写了多余的测试用例（Surplus Tests），或者哪些步骤存在冗余。

更酷的是，工厂支持多模态的 **Computer Use** 自动验证。例如，Agent 在完成前端修改后，会在沙盒环境中启动浏览器，实际操作 UI 并录制成视频供人类回放确认。这比单纯让人肉眼看代码 diff 直观且高效得多。

<details>
<summary>Original English</summary>

**Zach Lloyd**: I think that's right. I want to show you some other stuff in the factory just to show you like how this is done. You have this whole scoring. You have it classified in terms of like for this task like how did it look? Uh you pick like a sort of sampling rate on in terms of how you want to do this and then you get over time a set of runs where you can see that like sometimes this agent thinks that there were some like surplus tests. One of the things that's most helpful is like you can have these factory agents do computer use verification. So in this case it made a video.

</details>

### 自我改进闭环（Self-Improvement Loop）

**Zach Lloyd**: 我们刚才提到的第二重循环——**自我改进**。你可以配置专门的观察者 Agent，去分析近期所有失败或低评分的任务，生成帕累托图（Pareto Chart），找出导致错误的高频根因，并自动向工厂的 Prompt 或系统配置提交改进 PR。

这种工程化、科学化的方法，使得整个团队的研发流水线能够像工业制造业一样实现良性自迭代。

<details>
<summary>Original English</summary>

**Zach Lloyd**: And then there's the self-improvement loop. You can have an observer agent analyze failed runs, create updates to your factory prompts or tools, and prevent that failure mode in the future. It generates a Pareto chart of failures. If you take this factory approach and are really scientific around it, you can continuously optimize throughput and quality.

</details>

### 非技术场景赋能：从产品设计到业务协作

**Clarvo**: 刚才我们探讨了后端与工程自动化。但我知道你作为技术型 CEO，在很多原本非技术的领域（如 Figma 设计、销售物料、文档方案）也重度依赖 AI 进行协同。能给我们分享一下你是怎么做的吗？

<details>
<summary>Original English</summary>

**Clarvo**: We've talked about engineering and backend automation. But I know that as a technical CEO, you also use AI heavily in areas that aren't strictly traditional coding, like Figma designs, marketing materials, and planning. Can you show us how you approach those?

</details>

**Zach Lloyd**: 比如在设计方面，我个人其实完全不擅长画图或专业 UI 设计。但现在通过结合多模态模型与 **Figma** 插件/MCP，我可以直接用自然语言描述：“我想要一个类似火箭发射台风格的产品 Launchpad 页面，包含任务跟踪模块。”

AI 会直接在云端画布上生成结构化的 UI 草案。尽管初始版本可能还需要专业设计师打磨，但它让我作为 CEO 能够在几分钟内将脑海中的产品构想具象化并传递给团队。AI 赋予了每个人跨越专业技能壁垒的“超级能力”。

<details>
<summary>Original English</summary>

**Zach Lloyd**: For someone like me who can't design or draw at all, having this superpower is incredible. I can go into Figma and describe what I want—like a rocket-themed launchpad dashboard with tracking modules—and the AI starts generating the UI layouts directly. Even if it needs polish from our design team, it allows me to communicate visually at lightning speed.

</details>

### 总结与未来展望

**Clarvo**: 总结得太精辟了。最后一个问题：当 AI 没有给出你期望的结果时，你通常的应对策略是什么？

<details>
<summary>Original English</summary>

**Clarvo**: I love it. Amen. I could not say it better. Okay, last question and then we will get you out of here: when your AI is not doing what you want, what is your go-to strategy?

</details>

**Zach Lloyd**: 我的核心法则是：**不要在同一个失败的上下文中反复纠缠**。如果一个 Agent 走偏了，最有效的做法是清空上下文、重新提炼更清晰精确的约束条件并重新启动任务；或者将大任务拆解为更小的可验证子任务。在软件工厂体系中，系统性的 Prompt 调优和评估测试集永远胜过单次的即兴调试。

<details>
<summary>Original English</summary>

**Zach Lloyd**: My main rule is: don't get stuck in a bad context loop. If an agent goes off the rails, wipe the context, refine your constraints and specifications, and start fresh. Or break the task into smaller, highly verifiable steps. In a software factory setup, investing in systematic prompt improvements and eval sets always beats ad-hoc prompt wrestling.

</details>

**Clarvo**: 非常感谢 Zach 为我们带来的精彩分享！

如果你喜欢本期节目，请在 YouTube 上点赞并订阅，或者在评论区留下你的思考。你也可以在 Apple Podcasts、Spotify 或各大播客平台上收听《How I AI》，并欢迎留下评分与评论。访问 howiaipod.com 查看往期所有节目。我们下期再见！

<details>
<summary>Original English</summary>

**Clarvo**: Thank you so much, Zach, for sharing these incredible insights! If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>