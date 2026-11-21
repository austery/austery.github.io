---
author: How I AI
date: '2026-08-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=p2qmX6TM0kw
speaker: How I AI
tags:
  - ai-agent-workflow
  - personal-productivity
  - product-management
  - context-management
  - self-improving-system
title: 用 Claude Cowork 重塑产品管理：打造一天完成一周工作的自优化 AI 工作流
summary: Miro 产品经理 Daniel Bloom 深度拆解了他基于 Claude Cowork 与 Notion 构建的个人 AI 工作流。该系统通过每周准备与晨会简报自动化管理会议纪要与跨工具待办，更具备上下文主动捕获、间接改写学习、技能推荐与多源建议审核等自愈自优化闭环，并将工作站机制推广至全团队。
insight: ''
draft: true
series: ''
category: ai-workflow
area: PAI
project: []
people:
  - Daniel Bloom
  - Claire Vo
companies_orgs:
  - Miro
  - Anthropic
  - Optimizely
products_models:
  - Claude Cowork
  - Claude Enterprise
  - Notion
  - Gemini Enterprise
  - Granola
  - Slack
media_books:
  - How I AI
status: evergreen
---
### 效率跃迁与深度工作

**丹尼尔·布鲁姆**: 我简直无法用言语来形容它有多么强大。我现在真正能在一天之内完成过去需要整整一周才能做完的工作。但更重要的是，我认为它带来了更多**深度工作**（deeper work）。今天我所能做到的很多事情，在过去是根本无法企及的。

<details>
<summary>Original English</summary>

**Daniel Bloom**: I cannot describe how powerful it is. I'm really able to do in a day now what used to take me a week. But more than that, I'll say it's a lot of deeper work. There's things that I do today that I just wasn't able to do before.

</details>

**丹尼尔·布鲁姆**: 无论是指更深入透彻的研究、拥有更强有力的数据支撑，还是你今天所做的任何事情，你几乎都能以顶尖水准来完成。即便是在公司层面，我经常对大家说的一点也是：听着，你必须经历切换系统所带来的阵痛，一开始它确实不会那么高效。是的，当然，老方法肯定更快，因为那属于**肌肉记忆**（muscle memory）。但只要你跨入下一个层级，你不仅会拥有一个运作得更好的系统，而且团队里的每个人都会掌握更多的技能。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Whether it's more in-depth research, whether it's being more databacked, anything you do today, you can do it almost at the top level. One of the things even at a company level that I tell people is look, you got to go through the pain of switching your systems and it's not going to be as efficient. And yes, of course, like the old way will be faster because it's muscle memory, but if you get to the next level, not only will you have a system that works better for you, but everybody will have more skills.

</details>

**丹尼尔·布鲁姆**: 如今可以说，我在电脑前大约 70% 到 80% 的工作时间都是仅通过 **Claude Cowork** 来管理的。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Today, I say I manage about 70 to 80% of my time in front of the computer with co-work alone.

</details>

**克莱尔·沃**: 我们之前在节目里见过好几种晨间简报系统，但我想看看你觉得自己的系统有什么与众不同之处。

<details>
<summary>Original English</summary>

**Claire Vo**: We've seen a couple morning briefs, but I want to see what you think makes yours different.

</details>

**丹尼尔·布鲁姆**: 在这份每日简报中，我的 Coworker 会浏览我最近的 **Slack** 消息、电子邮件以及个人笔记，并在其中寻找它尚不理解的上下文。它会说：“这里有一个我之前不知道的文件，或者某个里程碑、某个目标”，它就会主动向我提问：“嘿，这是什么？这很重要吗？我需要阅读这个吗？”我认为这正是真正产生神奇魔力的地方。

<details>
<summary>Original English</summary>

**Daniel Bloom**: In this daily brief, my coworker runs through my recent slacks, my emails, my personal notes, and it looks for context that it doesn't understand in these things. And it says like, oh, if there's a file I wasn't aware of, there's a milestone, there's a goal, it would ask me about it and say, hey, like, what is this? Is this important? Should I read this? And this is, I think, where the real magic happens.

</details>

### 系统构建与核心痛点

**克莱尔·沃**: 这真的太天才了。我很想知道这套系统如何扩展到你之外的范围。你有自己的系统，你现在已经成了 **10x PM**，恭喜你。但这会对团队产生什么影响？团队成员又是如何使用类似系统的？

欢迎回到《How I AI》。我是 **Claire Vo**，一名产品领导者和 AI 狂热探索者，致力于帮助大家利用这些新工具更好地构建产品。今天我邀请到了 **Daniel Bloom**，他将向我们展示他那套统领一切的 Claude Cowork 系统。它具备**自我修复**（self-heals）、**自我优化**（self-optimizes）的能力，远比你目前见过的任何晨间简报都要强大得多。让我们马上开始。

**Optimizely** 面向营销人员的 Agent 平台建立在一个更宏大的理念之上：一个完整的 Agent 目录，现在又加入了一支新近亮相的虚拟队友战队，每个人都有明确的角色设定与独特个性。这不仅仅是为了更快地产出草稿，更是为了处理那些繁杂的协调工作——调研、审批、交接、路由，以及那些悄无声息地吞噬掉你整周时间、却从未出现在任何工作亮点集锦中的来回沟通。了解背后的故事，听听那些已经交接了杂务的营销人员的自白，在 `optimizely.com/howiai` 结识这支战队，了解虚拟队友能为你做些什么。

Daniel，欢迎来到《How I AI》。我非常高兴你能来参加这期节目，因为每周、每月技术都在变得越来越好，而除了我之外的每个人似乎都在用 AI 和个人生产力工具把自己组织得井井有条，这总让我印象深刻。那么告诉我，是什么促使你构建了这么庞大的一个系统？你试图解决什么问题？

<details>
<summary>Original English</summary>

**Claire Vo**: This is really genius. I'm curious how this scales beyond you. So, you have your system, you're, you know, 10x PM now. Congratulations. How does this affect the team? How do they use systems like this?

Welcome back to How I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Daniel Bloom and he's going to show us his clawed co-work system to rule them all. It self-heals, it self-optimizes, and it's way better than the morning briefing you have going on. Let's get to it.

Optimizely agent platform for marketers is built on a bigger idea. A whole directory of agents now joined by a newly revealed squad of virtual teammates. Each with a defined role and a personality of their own. This isn't about faster drafts. It's about handling the coordination, too. The research, the approvals, the handoffs, the routing, the back and forth that quietly eats your week and never makes it into anyone's highlight reel. Get the story behind it all. Hear the confessions from marketers who have handed off the busy work. Meet the squad and understand what virtual teammates can do for you at optimizely.com/howiai.

Daniel, welcome to how I ai. I am so excited to have you on this episode because every week, every month, I think things get better and I'm always impressed with how much more organized everybody but me seems to get with their uh AI and their personal productivity. And so tell me like what brought you to building this big system and what problem are you trying to solve?

</details>

**丹尼尔·布鲁姆**: 太棒了。Claire，非常感谢你邀请我，我很高兴来到这里。作为很早以前就开始深度拥抱 AI 的人，早在几个月前甚至一年前，我们就能用一些更简单的工具（比如 Google 的 **Gems**）来解决或至少改善产品经理的一些重大核心任务（jobs to be done）——你可以借此改进产品需求文档（specs），优化调研流程。

但在我深入推进 AI 应用的过程中，我真切地感受到，一直笼罩在我头顶并真正让我日常工作变得极其艰难的，正是作为一名 PM 所必须承担的所有繁琐的管理杂务（overhead）：协调大量事务、记住 Slack 上不断冒出来的无休止的任务、跟进会议中的待办事项（action items），以及在每一天发生的纷乱混沌中艰难斡旋。与此同时，我还渴望进行深度工作、保持专注和认真思考。我曾觉得这对我来说真的无比艰难，而且迟迟找不到解决的途径，直到我能够利用 Cowork 构建起这套系统。坦白说，我现在依然对它的强大功能以及它帮我彻底重塑这一难题的程度感到有些惊叹。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Cool. Well, Claire, thank you so much for having me. I'm really excited to be here. As somebody who's been an early adopter of AI for quite a while, I think it took a already like a a good few months ago or even a year ago, we were able to solve some of the big or at least improve some of the big jobs to be done for PMS with uh even with simpler tools like with uh gems. Uh you could improve your specs and you could improve your research. But I think uh as I was progressing with my AI adoption, I really felt that one of the biggest things that hangs over me and and really makes my day-to-day more difficult is all this just overhead of of being a PM of coordinating a bunch of things, remembering endless tasks that arise on Slack and meetings and action items and just trying to maneuver this whole uh this whole chaos that happens every single day. um while at the same time wanting to do in-depth work and focus and and really think I felt that that was something that was really really difficult for me and I was getting nowhere near solving it um until I was able to actually build a system with co-work that I'm actually still a little bit surprised at how powerful it is and how much it's helped transform uh this this problem for me.

</details>

### 技术栈选型与系统进化

**克莱尔·沃**: 那跟我讲讲你作为产品经理的个人 AI 技术栈吧。你是如何挑选其中的工具的？然后我希望你能向我们演示一下整套系统究竟是如何协同运转的。

<details>
<summary>Original English</summary>

**Claire Vo**: So tell me about your personal AI stack as a PM. How did you pick the tools that go into it? And then I want to I want you to show us how how it all kind of works.

</details>

**丹尼尔·布鲁姆**: 好的。我认为我的大部分技术选型其实是由我所在的公司 **Miro** 决定的，也就是我们技术栈中现有的工具。不过值得庆幸的是，我对这些工具相当满意。在很长一段时间里，我们只有 **Gemini Enterprise**，我们一直用它；直到几个月前，我们引入了 **Claude Enterprise** 和 Cowork，这真正为我带来了转折。除此之外，基本上就是绑定在我们拥有和使用的任何现有工具上，这就是我开展所有工作的基础。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Perfect. Uh so I'll say I think most of my choices were made by my company Mio. Um and the tools that I'm uh I'm are in our stack. Uh but uh thankfully I'm I'm pretty satisfied with those. So for a long time we only had like the Gemini enterprise and we were using that and uh just a few months ago we got uh the claude enterprise and co-work uh and that's when things really changed for me. Uh and besides that I'm basically bound to whatever whatever tools we have and use uh so this is this is what I work based off of.

</details>

**克莱尔·沃**: 这对所有受限于公司既有工具的人来说是个好消息：你依然能让它发挥效用。显然 Claude 是这个技术栈的重要支柱。Cowork 对你而言是那个决定性的重大突破（big unlock）吗？你最早是从什么时候开始构建这套系统的？早期的工具和现在的相比有什么不同？

<details>
<summary>Original English</summary>

**Claire Vo**: Okay. So this is good for everybody out there who is stuck with the tools that they're stuck with. You can still make it work. I at work. I think that Claude is obviously like a big part of this stack. Was co-work just the big unlock for you? Like where did you when did you start building this and what was the early tools versus what you use now?

</details>

**丹尼尔·布鲁姆**: 是的，对于你刚才的第一句话，我非常赞同。总体来说，在日常工作中我和普通 PM 一样受到各种现实约束，比如 Token 额度并不是无限的，必须在预算和官僚流程内行事。我认为在真实 PM 所面临的所有这些限制条件下，做到这一点是非常可行且完全办得到的，强调这一点很重要。

至于工具方面，Cowork 绝对是我的重大突破。但尽管我很喜欢 Cowork，关键其实并不在于 Cowork 这个产品本身。我认为像 **Codex** 或者 **ChatGPT Work** 也能很好地实现这一点。我认为真正的核心要点在于：
1. 系统必须能够**重写自身的底层核心文件**（rewrite its own core files），这意味着它能持续不断地自我改进；
2. 尽可能深度连接并集成到你的整个工作生态中。

当满足这两个条件时，你改善工作方式的潜力和空间将极其巨大。虽然我之前使用 Gemini Gems 也能做出一些不可思议的成果，但这双重特性真正让一个系统变得无比强大，既能无缝融入日常，又具备自优化能力——这正是最大的飞跃。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yeah. So I think first of all on your first saying I think it's very correct and in general I'll say like I was bound by constraints of an average PM all the time in terms of having you know not endless tokens and needing to work within budgets and bureaucracy and I think it's very possible and very doable within all those constraints that you know real PMs face and I think it's it's very important to say um and in terms of the tool so co-work was definitely the big unlock for me but I While I love co-work, it's not co-work in itself. Uh, and I think codeex could be great for this as well or uh, Chad GBT work. I think the real importance is for a system to a be able to rewrite its own uh, core files and that means that it keeps on improving and b just have connections and integrations to as much of your ecosystem. when these two rules apply um there is a significant significant opportunity to really really improve the way you work and while I was working with uh Gemini gems earlier and there's obviously some incredible things that can be done with those these two elements make a system really powerful and also really integrated into your daily life but also self-improving which is one of the biggest unlocks here

</details>

**克莱尔·沃**: 好极了，那就展示给我们看看吧！我想看看你实际上是如何管理你作为 PM 的日常的。

<details>
<summary>Original English</summary>

**Claire Vo**: okay well let's let's show show it to us I want to I want to see how you actually manage your life as a PM.

</details>

### Notion 看板与深度上下文

**丹尼尔·布鲁姆**: 让我先从这个 **Notion 看板**开始展示。这本身并没有什么惊天动地的地方，就是一个标准的 PM Notion 仪表盘。它包含三个部分：
1. **Top of Mind（核心关注）**：我在任何给定时间正在思考的重大战役或举措；
2. **This Week（本周重点）**：我本周设定的优先级事项；
3. **Inbox（收件箱）**：从 Slack、电子邮件、日历中捕获的事项，Cowork 会自动识别并填充到这里。

这个看板最酷的地方不在于它存在本身，而在于两点：第一，它完全是 Cowork 自动构建出来的。我之前一直在用一份非常简陋杂乱的 Google 文档，我想 Cowork 肯定是受够了那份文档，于是决定主动为我建了这个看板；第二，它实际上是在代表我进行实时管理。

最关键的一点是，它非常极其了解我，因为我投入了大量的时间和精力对其进行**上下文注入**（contextualizing）与维护，并将我所有的工作集中于此。虽然一开始需要时间去适应，但带来的投资回报率（ROI）绝对高得惊人。在为本期节目做准备时，我真切地体会到了它有多了解我——因为这是我的真实工作环境，我不能展示敏感的人名和项目，所以我直接在 Claude 上创建了一个名为“demo”的技能，告诉它：“把所有的专有名词和具体细节替换成通用术语。”正因为它对我太了解了，只用一条提示词，它就自动把我经理的名字替换成了“Your Manager”，把我的主导项目替换成了“Headline Feature”。这种深度的认知让协作变得极其无缝和顺畅。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Let me start with this uh notion board, right? So, this is uh nothing incredible. It's just a standard uh PM notion board. It has three sections. One is top of mind, which are the large initiatives uh that I I just think of uh you know on any given uh time. It has my this week, which is basically the priority that I have for this week. And it has inbox, which is things that arise from Slack, email, calendar, and co-work picks up and fills them in here. Now, the cool thing about this board is not that it exists, but the fact that not only did Coowork build this completely on its own, I was working with a very simple and messy uh Google doc before, and I think notion got I think co-work got tired of of it and basically decided to build this for me, but also it actually manages it on my behalf. And I think that's the pretty cool thing that I want to show and I'll walk you through how it does it. I'll say that um the most important thing about this is that it knows me really really well uh because I spent a lot of time uh and effort contextualizing it uh and maintaining this context and also centralizing all of my work in it which took some time to get used to. But the ROI is just absolutely insane there. And I really felt how well it knows me just when prepping for this uh for this episode when I knew that because this is my real environment I couldn't show you know names and projects and sensitive stuff. So basically I just created this skill on cloud called demo and I just told it replace all the terminology and like specifics with generic terms. But because it knows me so well basically in in one prompt I was able to replace my manager's name with your manager and my top initiative. You can see here with headline feature and that's how well it knows me. It was just able to replace all of these and it just makes it for a really really seamless and comfortable collaboration.

</details>

**克莱尔·沃**: 跟我讲讲这些上下文是如何存储的？是你把所有东西都丢进 Notion 里以便它检索，还是有更针对性的上下文管理机制？

<details>
<summary>Original English</summary>

**Claire Vo**: Tell me a little bit about how that context is saved. Is it just that you just put everything in notion so when it's searching it kind of knows? Is there something more purposeful around your kind of context setup?

</details>

**丹尼尔·布鲁姆**: 确实有更针对性的机制。在 Cowork 里，你有一个全局的 `context.md` 文件。我的原则是：**任何被证明具有长效价值的事物，都会进入上下文**。这涵盖了我的角色职责、我的个人关注点、团队目前的状态、我们正在推进的项目，甚至我与不同干系人合作的方式。

同时，我还拥有一个专门的“知识库技能”（knowledge skill），里面沉淀了关于我的各种详细细节。所以它不仅知道我是一家公司里的一名 PM，更知道我负责的是哪块业务范围、我的战略支柱是什么、我正在跟进的关键指标是什么，以及目前正在推进的各项实验。拥有如此精确的上下文，是让它输出高质量结果并真正像一位协同工作者一样行事的前提。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yeah, so definitely something more purposeful. So in co-work, you have a context.md file that exists. And my rule is that anything that has been proven to have long-term value goes into the context. So it includes my role, it includes my focus, where the team is, what we're working on, how I work with different stakeholders. And I also have a dedicated knowledge skill that has a bunch of specifics about me. So it knows not only that I'm a PM in a company, but it knows which domain I work on, what are my pillars, what are my metrics, what are current experiments that we're running. And having that level of context is really what unlocks the high-quality output and the ability to actually act like a coworker.

</details>

**克莱尔·沃**: 太棒了。那我们切换到 Cowork 界面吧，给我们展示一下这个系统的架构是怎样的，以及你是如何日常维护和使用它的。

<details>
<summary>Original English</summary>

**Claire Vo**: I love it. Well, let's let's switch over to co-work and show us how kind of the system is architected and then how you maintain it and use it over time.

</details>

### 每周准备与计划落地

**丹尼尔·布鲁姆**: 好的。这一切都始于一个名为 **Weekly Prep（每周准备）** 的周期性定时任务（recurring task），它是由几个不同的技能组合而成的。每周准备是我开启一周工作的非常基础的任务。它会在每周日晚上或周一清晨自动运行，帮我盘点上一周未完成的事项，拉取最新的日历安排，扫描团队的战略重点，并生成一份清晰的本周行动建议。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Perfect. So, it all starts with um one recurring task uh which is a composition of several skills called the weekly prep. So the weekly prep is the very basic uh uh task that helps me start my week. It runs on Sunday evening or Monday morning, looks at what was left over from last week, pulls in the calendar, looks at our strategic priorities, and drafts my proposed focus for the week.

</details>

**克莱尔·沃**: 那它会把所有这些内容直接推送到 Notion 里面吗？

<details>
<summary>Original English</summary>

**Claire Vo**: and does that push all of it into notion?

</details>

**丹尼尔·布鲁姆**: 是的。我之前运行的测试基本上就自动生成了我们现在看到的这个 Notion 看板状态。稍后我还会向你展示它是如何在日常中动态更新这个看板的。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yes. And that basically this test that I ran earlier basically created this state that we have uh now the the notion uh that we have right now. But I'll also show you how it updates it.

</details>

**克莱尔·沃**: 好啊，我们来看看具体过程。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah, let's look at that.

</details>

**丹尼尔·布鲁姆**: 好的。这个系统独特的地方在于——这也是我在创建了第一个每周准备流程后遇到的实际问题——我认为任何 PM 都会对此感同身受：世界上存在着两个完全不同的世界。一个是我们每周优先级计划或产品路线图中那个极其干净、井井有条的美好世界，在那里一切都条理分明、各就其位；但另一个则是现实世界，充满了来自 Slack、各类会议、紧急突发事件、高管临时需求以及无休无止涌入涌出的混乱琐事。

起初我深切地体会到一种脱节感：我在计划中精心准备的东西，与现实中耗费大量时间处理碎片杂务的状况截然不同。因此我构建这套系统让它真正与我并肩作战。而它极为了解我的另一个体现，在于它深谙我的具体工作习惯。比如，在 Slack 和邮件上我都是 **Inbox Zero（收件箱清零）** 践行者。所以它知道，如果在 Slack 上某条消息之前被标记为已保存（saved），而现在取消了保存，就意味着这件事大概率已经处理完了；如果在 Gmail 中某封邮件离开了收件箱，就意味着我已经读过了。这极大促进了我们平滑流畅的协作。

接下来让我运行下一个定时任务——**Morning Brief（晨间简报）**。我认为真正的魔法正是在这里发生的，我们现在就现场实时运行它。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Perfect. So the unique thing about this is that I think and this is something I ran into uh after having created the first weekly prep. I think one of the things any any PM uh can resonate with is the fact that there's two worlds, right? There's this beautiful clean organized world that's in our weekly priority or our road map where everything is very clear and beautiful and fits in and then there's reality where as we said this chaos of Slack and meetings and urgent priorities and executive asks and endless things that just flow in and out and what I was feeling in the beginning is this real um this real gap between what I was doing and prepping and what it was happening in real life where I was spending all this time doing all these small tasks. And I think I've built the system to really work alongside me. And part of the fact that it knows me really well is also that it knows how I work. So for example, I'm inbox zero both on Slack on on email. So it knows that if something is was saved on Slack and is no longer, it means it's likely done. Or if something was on inbox in in Gmail and is no longer so, then it probably means I already read it. And that really really helps in how we collaborate smoothly. So basically, let me run to uh my next scheduled uh my next scheduled task. And this is called the morning brief. And this is I think where the real magic happens. So actually we're going to run this live right now.

</details>

**克莱尔·沃**: 我忍不住笑了，因为我觉得每个人的 AI 配置都是其内在个性的真实写照。你给我的印象是一个极其有条理、深思熟虑的人，是个 Inbox Zero 达人。而我对那些试图给我发短信或邮件的人深感抱歉，因为我属于“混乱统治一切”的那类人。我没法把我的东西规整到表格或者看板里，我只需要一个 Bot，不论是凌晨两点、早晨六点还是下午两点，我只需要对它说：“亲爱的 Bot，现在到底什么情况？发生啥了？”

所以看着那些在 AI 时代之前就拥有极强结构化工作方式的人，在 AI 时代之后将这种特质完全映射在自己构建的系统中，这总让我着迷。我的系统可能理应长成你这样，但实际上完全不是这个样子的。

<details>
<summary>Original English</summary>

**Claire Vo**: I had to laugh because I think folks AI setup is a real reflection of their internal personality. And you strike me as somebody who is organized and thoughtful. You're an inbox zero person. I am sorry to anybody that tries to text or email me. I am like a chaos reigns person. I cannot put my stuff in a table. I cannot put my stuff in a conbon board. I need just a bot and I need when it's 2 in the morning or it's 6:00 in the morning or it's 2 in the afternoon. I just need to be like, "Dearbot, what's going on? What's going on?" And so it's always fascinating to me to watch people who I just pre-AI have like a much more structured approach to their work and then post AI I think it really reflects in how you build build your system because mine looks it probably should look like something like this but it looks nothing like this.

</details>

**丹尼尔·布鲁姆**: 首先你说得很对，我确实是个相当有条理的人，但在现实中很多时候也一团糟。我发现我的大脑里其实驻留了大量的“业务逻辑”。在与这套系统共处的过程中，我经历了一个不断对自我及工作方式进行“用户调研”（discovery）的过程。我经常会发现系统在某些地方表现不够好，因为它没有覆盖到某种场景；而只要有没覆盖到的地方，就会形成盲区，系统的威力就会大打折扣。所以随着时间的推移，我逐渐覆盖了各种不同的死角。

在直到最近之前，我的操作方式在某种程度上也是杂乱无章的：有些任务保存在 Slack 上，有些在邮箱里，还有些就是 Chrome 浏览器里打开的标签页。我所做的就是让 Claude 学会适应所有这些习惯，并且对我说：“好吧，虽然我无法把一个打开的网页标签当作任务来处理，但对于其他所有信息，我已经学会了用与你完全相同的方式去审视它们。”

<details>
<summary>Original English</summary>

**Daniel Bloom**: Well, I think I I'll say first of all that uh you are correct in in me being quite an organized person, but I will say like again in reality a lot is a mess and a lot is like I I've found out how much is like business logic in my brain and I've had this experience with the system where I continuously like do discovery on myself and how I work and I continuously run into this places where the system is not good enough because it doesn't cover this and what it doesn't cover like it has a blind spot and it becomes much less powerful. So over time I've like covered all different angles. Um and I think it's doable. I think it's doable. And up until recently I would say in a way I was also operating chaotically. You know some of the tasks were saved on Slack. Some of them were like in my inbox. Others were just like tabs that are open in Chrome. And I've just had Claude like learn to work with all of these um and say, "All right, I'll take unfortunately it can't take an open tab as as a task, but uh everything else I just learned to look at uh the same way I do."

</details>

### 晨间简报与会议自动化

**克莱尔·沃**: 那我们来看看这份晨间简报吧。我们见过好几种简报，但我想看看你认为自己的简报究竟有何不同。

<details>
<summary>Original English</summary>

**Claire Vo**: Well, let's look at this morning brief because we've seen a couple morning briefs, but I want to see what you think makes yours different.

</details>

**丹尼尔·布鲁姆**: 好的。这里面包含好几个模块，我快速过一遍不同的部分并重点讲解有意思的地方。

第一部分：这份简报会梳理我的所有会议。产品经理最大的痛点之一就是会议极多，需要提炼待办事项并付诸行动。几乎每场会议都会产生新的工作，但我们往往得立刻赶往下一场会议，背靠背开会一直持续到一天结束。而这个模块能帮我快速补齐昨天的会议进展。它读取 **Granola** 转写的会议记录，为每场会议生成一句话总结，并提取行动项。你可以看到，从所有这些会议中，它抓取到了一个行动项：“与 GTM 团队在功能专属频道中分享演示视频录像和说明文档。”就是这么清晰。它还会主动询问我是否需要展开或起草相关摘要。

接下来进入第二阶段，这非常酷。使用 Cowork 这类 Harness 极其强大的一点在于你可以配置它们实现**自我进化**。我一直在逐步推动 Claude 变得更具 **Agentic 特性**，让它更能自主行动。

在这套流程中有一个极大的难点：**如何保持上下文的清晰与最新？** 即使你给系统注入了背景信息，它懂很多事情，但你怎么确保它能跟得上变化？我的做法是：在每日简报中，Cowork 会扫描我最新的 Slack、邮件和 Granola 笔记，在其中寻找它**读不懂的上下文**。一旦发现它不知道的文件、里程碑或新目标，它就会主动问我：“嘿，这是什么？这重要吗？我需要阅读并学习它吗？”

你看它现在标记出了一个概念：“一个我不认识的术语——**结算上限（settlement cap）**。”这是某个支付相关的概念。它说：“我读了这个讨论串，理解这是正在商讨的限额。需要我把它存入上下文吗？”我点击“确认保存”。这就是 Claude 如何帮我主动维持上下文最新、不遗漏任何新概念的机制。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Okay. So, I think that there's several things, but I I'll walk through this uh very quickly and and show uh the different parts and I'll highlight the interesting things. So the first part is that uh this brief basically walks me through my meetings. I think one of the biggest pains of PMs is we have ton of meetings. Uh we need action items, we need to act on them. Almost every meeting creates new work, but we have to run to the next meeting and often times it's backtoback until the end of the day and then you know so this helps me kind of catch up on on yesterday's meetings. Um and it shows all the different things and basically you can see this takes the granola transcripts uh and it gives me a oneliner about each meeting and if there's an action item. So here I can see uh from all of these meetings looking through them uh there is one action item uh to share the walkthrough and recording of a of and a write up in the feature channel uh with go to market. Um and that's it. So it's going to offer me to uh expand or draft any summaries. I'm going to say uh no, let's continue for now. And we're going to walk walk on over to the next phase which I think is pretty cool.

One of the things that I think is super powerful with co-work and and with these harnesses is that you can set them up for improving themselves. And one of the things I've done is I've over time uh I'm building up towards uh Claude being more agentic and being more able to act on itself. Um and I'll show you this and I think it's pretty visible in this flow. This part is pretty cool where basically one of the difficulties in life is keeping the context clear, right? So you have the system, you contextualize it, it knows things, but then how do you make sure that it keeps track. So this is one of the ways I've thought of. So basically what it does is imagine in this daily brief my coworks through my recent slacks, my emails, my granola notes and it looks for context that it doesn't understand in these things and it says like oh if there's a file I wasn't aware of, there's a milestone, there's a goal, it would ask me about it and say hey like what is this? Is this important? Should I read this? Uh so here it flagged something. Let's see what it is. A term I didn't know the settlement cap. All right. This is some payments thing and it says like I read the thread and understand it's a limit working through. Want me to save? Yeah. So I'll say save. Yes. Save it to the context. So basically this is how Claude helps me keep it contextualized and not lose track of things.

</details>

### 主动上下文捕获与对齐

**克莱尔·沃**: 这真的太精妙了。我希望大家停下来认真体会一下这意味着什么：在你的上下文构建中，你是在确保 Claude 能真正理解公司的内部定义、术语和业务目标。我们很多人所在的公司，日常讨论的话术根本不在大模型的预训练数据中（至少目前还不在）。因此，能够主动提示 Claude 识别盲区并提问：“我不明白你这里说的是什么，我们能一起给它下个定义吗？确认后我会存入上下文，以后我就能理解了。”这设计极其犀利，我们在播客之前的节目里从未见过。我太喜欢这个设计了。

<details>
<summary>Original English</summary>

**Claire Vo**: This is really genius and I want people to just take a pause and reflect on what this is because it looks like for your context you are making sure that Claude understands internal definitions, terms, goals, etc. And so many of us work inside companies where the things that we say are not in the training data. They well not yet at least they're not in the training data. And so actually proactively prompting Claude to say like I don't understand what you're talking about here. Can we define it together and then I'll save it to my context and I'll know what you're talking about moving forward is really really sharp and something we haven't seen on the podcast yet. I love this.

</details>

**丹尼尔·布鲁姆**: 确实，单靠人工去追踪维护这些变化太困难了。这里的核心突破在于：你可以让 Claude 成为你维护上下文的合伙人，让它自动跟进、主动坚持获取未知领域的知识，这是一个巨大的能力飞跃。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yeah. So, it's it's super hard to just keep track and and the unlock is that you're able to say, "Oh, I can just ask Claude to be my partner in doing this and automatically, you know, follow up and and insist on on getting this knowledge is a really really big unlock."

</details>

**克莱尔·沃**: 太棒了。你每周运行它，每天也运行它。那你平时还会花时间手动去调整或编辑这个 Notion 看板吗？

<details>
<summary>Original English</summary>

**Claire Vo**: Amazing. So you run it weekly, you run it daily. Do you actually spend time in the board itself?

</details>

**丹尼尔·布鲁姆**: 基本思想是：**Notion 对我来说几乎是一个只读界面（read-only）**。我看 Notion 的目的，纯粹是为了在脑海中对各项事务保持清晰的全局视野（helicopter view）。除了某些极其微小的调整，我几乎从不手动编辑它。所有任务的创建、状态更新和归档，完全是由 Cowork 在后台代我执行的。

<details>
<summary>Original English</summary>

**Daniel Bloom**: So the main idea is that notion is almost a read only for me. I I look at the notion just to have clarity in my own mind and have like a helicopter view. I I barely almost never edit it with you know small small exceptions. It's completely made for me by co-work.

</details>

### 工具使用边界与真实效益

**克莱尔·沃**: 你在使用 Cowork 时会配合 Chrome 浏览器吗？比如使用浏览器自动化（Browser Use），还是主要依赖 API 和文件集成？

<details>
<summary>Original English</summary>

**Claire Vo**: are you using co-work with Chrome at all like are you using browser use or are you mainly just using files?

</details>

**丹尼尔·布鲁姆**: 刚开始的时候我确实经常配合 Chrome 使用。但在我看来，让 Agent 直接操控浏览器往往容易出现卡顿和不稳定，速度也相对较慢。我发现通过集成的 API、结构化的文件连接以及专有工具来处理数据，运行效率要高得多，也更稳定可靠。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yeah. So I I would say in the beginning I was using like Chrome a lot. In my personal experience, it gets hung up and and it's slow. I found that connecting through APIs and files and dedicated tools is just way way faster and more reliable.

</details>

**克莱尔·沃**: 你觉得这套系统真的为你节省了大量时间吗？它带来的核心价值是什么？单纯是为了节省时间，还是让你能做更多事情？因为建立和维护这套系统本身也需要投入精力。

<details>
<summary>Original English</summary>

**Claire Vo**: and do you feel like this is really saving you like what's the benefit here? Is it time saved? Is it capacity increased? Like how do you justify the overhead of maintaining this?

</details>

**丹尼尔·布鲁姆**: 这是一个极好的问题。坦白说，很多时候人们搭建了一套复杂的系统，最终却发现维护系统本身成了全职工作。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yeah. So, it's it's a great question and I think honestly oftenimes we make systems and maintaining the system becomes a full-time job.

</details>

**克莱尔·沃**: 我觉得……

<details>
<summary>Original English</summary>

**Claire Vo**: I I think

</details>

**克莱尔·沃**: 你应该去看看我们和 Meme Lord CEO Jason 录制的那期节目，他讲的正是很多自动化系统的实际维护负担。

<details>
<summary>Original English</summary>

**Claire Vo**: because you need to watch our episode with Jason, the CEO of Meme Lord, who actually talked about this exact thing.

</details>

**丹尼尔·布鲁姆**: 我还没来得及看，但那期绝对排在我待看清单的最顶端。

<details>
<summary>Original English</summary>

**Daniel Bloom**: So, I I haven't watched it yet, but I will say it's literally like the top to-do item for me.

</details>

**丹尼尔·布鲁姆**: 回到你的问题，我认为这极其关键。如果这套系统需要我投入大量时间去维护，那它就是失败的。它的核心理念恰恰是**低维护开销**，甚至让它自己来维护自己。

至于带来的效益，我不单单看“节省了多少小时”。最颠覆的是我开头提到的：**深度工作能力的倍增**。在过去，作为一个 PM，你一整天都被碎片化的消息、琐碎的任务和会议追着跑，根本没有整块的时间去深入思考战略、做深度调研或者细致分析数据。而现在，所有这些日常运转的繁琐杂务被这套自动化工作流稳稳接住，我每天能把原本需要一周才能完成的高质量深度产出浓缩在一两天内完成。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yeah. Um, but I'll say I think it's a really really good question and I will say like if this was high maintenance, it wouldn't be worth it. The whole point is that it's low maintenance and self-maintaining. And in terms of benefit, it's not just hours saved, it's the depth of work. You go from being constantly interrupted and managing small items to actually having uninterrupted focus to do deep PM work, high quality specs, and real strategy.

</details>

**丹尼尔·布鲁姆**: 真的，这听起来很疯狂。当我审视现在的产出质量与节奏时，那种对比是震撼性的。

<details>
<summary>Original English</summary>

**Daniel Bloom**: but it's it's it's true, you know. It's it's insane. And I I look at um I look at the difference in output quality and it's night and day.

</details>

**克莱尔·沃**: 太棒了，你完全说服我了。虽然我自己可能还是改不掉混乱的习惯，但我非常认可这背后的价值。你刚才提到了系统自愈和自优化的闭环，在我们进入团队工作站（Workstation）之前，请展开讲讲你的自优化循环是如何运转的。

<details>
<summary>Original English</summary>

**Claire Vo**: I I love it. I love it. You you've sold me. Um I don't know if I'm going to get out of my chaos, but I love the self-improving aspect. Before we get to how you scale this across the company with workstations, tell us about these self-improving loops. How does it actually get better week over week?

</details>

### 自愈与自优化的四大循环

**丹尼尔·布鲁姆**: 你提到的这一点非常切中要害。这也是为什么几个月前当大家都在疯狂热炒 Cursor 和 Claude Code 时，我选择保持观望。对于非纯技术人员而言，那些工具门槛极高甚至有些令人望而生畏。我很庆幸自己等到了 Cowork，因为它更注重用户体验、交互的简洁性以及价值的直观呈现。无论是我们一年前为团队开发的用于撰写产品 PRD 的 Gem，还是我们稍后要展示的工作站，只要你能做到门槛低、易上手、价值明确，推广普及就会顺畅得多。

在进入工作站之前，我先为你拆解这套自优化循环。

<details>
<summary>Original English</summary>

**Daniel Bloom**: A lot of what you brought up is is super relevant in that sense. Um and I think one of the things that have made me you know in a sense uh wait for uh for co-work for example when a few months ago there was this endless hype about cursor and about cloud code and you know I was kind of sitting on the sidelines um and and waiting like should I adopt these like tools that are not meant for me and are super super technical can be scary um and I'm glad I waited for for cowork because it's a lot about like you know just UX and and experience and simplicity and a lot of the tools that we've built for for the team and whether it's the gem that helps the team write uh specs product specs that we did almost a year ago or uh what we call the workstation that we have that I'll show a little bit later at the end of the day if you make something accessible and simple and the value is clear um then it then it gets adopted much better.

</details>

**丹尼尔·布鲁姆**: 这是帮助我持续改进整个系统、同时又无需投入过多个人时间的最酷突破之一。本质上，这是 Claude 在帮我改进它自己。

这是一个每周定时运行的任务，名为 **Self-Improvement Loop（自优化循环）**，它挂载了几个不同的专业技能：

1. **草稿改写追踪（Drafts Delta Analysis）**：
   在日常协作中，Claude 会给我提供文案或邮件草稿。有时我修改了它的草稿并直接发了出去，但过去 Claude 根本不知道它给的草稿与我最终发送的内容之间存在什么差距。现在，这个定时任务会专门回溯：找出 Claude 曾经给过我、但我没有直接采纳而是换了种方式发出的内容。它会自动比对我最终发送的版本与初始草稿的差异，自主反思学习：“原来在实际表达中我们更倾向于这种语气和结构。”从而持续微调 Claude 对我个人写作风格的理解。

2. **新技能挖掘与推荐（Skill Opportunity Detection）**：
   Claude 会持续观察我的高频日常操作，并主动建议将重复性的工作流固化为新的独立技能（Skills）。我现有的很多技能最初都源于这个机制的推荐。例如，由于我最近频繁进行原型制作，它便主动建议我构建一个“设计交接技能”（Design Handoff Skill），打通 Cowork 的调研环节与原型搭建工具之间的连接。

3. **现有配置诊断与遥测（Friction & Feedback Telemetry）**：
   在我所有的技能和定时任务底层文件中，都埋设了自动收集交互摩擦（friction）和反馈的逻辑。当我和 Claude 对话、指出某处做得不好或要求修复时，系统会自动记录下这些摩擦点。每周运行自优化循环时，它会汇总出本周交互中最主要的痛点，并提出具体的改进建议。

4. **外界前沿建议审核（The "Improve" Filter Skill）**：
   社交媒体（X、LinkedIn、各类新闻通讯和技术博客）上每天充斥着海量的“AI 最佳配置教程”、“必看 Prompt 秘籍”。这种信息过载让人焦虑。我不想被淹没，但也希望能吸纳真正有价值的思路。于是我创建了一个名为 `improve` 的审计技能。当我在手机上刷到有意思的内容时，直接转发到我和 Claude 的专属 Slack 频道，让它扮演一个极其挑剔的审计师：“这个方案是真实的还是营销炒作？它有多大价值？它如何融入我们现有的系统？”它会帮我做客观评估，共同决定是否值得落地采纳。比如它之前对我评估了 Claire 你关于循环设计的那期播客，指出我们可以吸纳其中的某些目标循环机制。这帮助我在不被营销炒作裹挟的前提下，稳步吸收行业最佳实践。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yeah, so I think this is one of the coolest unlocks that have helped me continuously improve the setup while not dedicating too much time to it. And basically, it's almost not self-improvement, but it's Claude helping me improve it. So, I'll walk you through something called the self-improvement loop. It's a scheduled test task that runs weekly and it has several skills attached to it and and I'll walk through them.

So, again, it it works in parts. Uh a trick I found really helpful when when I have a bunch of information that Claude feeds me. So, I'm going to walk through this uh in retroactive. Uh so, first of all, the first part is how my drafts landed. So, what I found over time is that when I write with Claude, it'll give me a draft and then I'll change it and I'll just send it. But the thing there is that Claude doesn't learn what the gap is between uh the draft that it wrote and what I actually sent. So, I have Claude uh when running this task looking for drafts that it it shared with me and I didn't respond and then looking to see if I sent them in a different way and learning from those draft and saying, "Oh, so we actually ended up writing this and doing the learning on it on its own." So in this specific uh in this specific week I see that there was nothing learned and insignificant but this is very helpful in continuing improving and you know uh polishing claude on on how I write.

Now this is a cool one. The second one and this is skills that are worth building. So basically Claude on an ongoing basis looks for things that I do uh on a recurring uh basis and suggests turning them into skills. Many of my skills actually ended up being uh from this flow. Uh, so you could see it. Uh, I've been prototyping a bunch lately. So, it's, uh, helping me. Uh, it's suggesting I create a claw design handoff, uh, skill between co-working where I do the research and design where I actually build the prototype. Um, and a bunch of other interesting skills uh, that I've built. I have a skill like this, by the way, that's handoff between co-work uh, which I use kind of as the exe executing arm of co-work. This is the second part.

The third part is fixes to my existing setup. So basically all of my skills and recurring tasks have uh lines in their in their files to collect feedback and friction for my interaction with them. So over time they gather this I don't need to do this proactively. Whenever I ask for a fix or something they gather and track this information and every week it surfaces the top frictions from my interaction with Claude and suggests to improve them. Um so these are also super helpful as you can see.

And then finally, this is a a really cool one. This is actually the uh the improve scale. So basically, uh we're all dealing with an endless flood. I think this resonates with anybody. Endless flood of tips, uh hyping up from X and LinkedIn and and and newsletters and blogs about setups and how to improve your AI usage and you must have this and you must build that. And I found this incredibly overwhelming. on one hand I don't want to drown in it at the same time I want to be able to actually implement what's relevant so I've built a skill called improve which is basically like a very critical um auditor for these uh and I share them uh usually through my phone through a slack channel with claude and I ask them like is this real is this powerful how how does this adapt to what we have now is this needed and then it helps me review it and together we basically decide whether we want to build it or not uh so here I ran it against uh Claire, your uh how I AI episode on designing loops. Um and it basically gave me like a a criticism of the episode. It said it's like a good vid a video and it says like listen loops at the end of the day are essentially like scheduled test. So you're running loops in many ways but I don't have goal loops that are uh the way you suggested. So this is something I can adapt. um uh there's some things I can adopt and basically this is helps me you know keep track of all the things that I run into and all these like tips and tricks and at the same time not drown in them and also not um you know give into the hype too much. So these are all the different things I do to you know claude helps me continuously improve it over time with as little you know dedicated effort as possible.

</details>

### 间接信号学习与遥测机制

**克莱尔·沃**: 我太喜欢这些设计了！我们完全可以把过去三分钟单独剪成一期完整的精彩节目。

第一点——通过分析你重写或丢弃的草稿来间接捕获负反馈并进行自学习，这简直太神了。我们之前看到 Alex Lieberman 拥有一个“像我一样写作”的自学习循环，但你的设计尤为精妙，因为它是通过捕捉**间接信号**（indirect signals）来自动完成闭环学习的。我在播客关于 Loop 的那期里也提到过技能编写循环。让我再仔细看看第三个点……

<details>
<summary>Original English</summary>

**Claire Vo**: Love the we could have done the entire episode on the last three minutes. so good. You know, I the first one where it's like take everything that you wrote for me that I hated and did it did it separately or dropped or rewrote and then just learn from that. That's genius. We saw Alex Lieberman had like a write like me self-learning loop, but this one is really interesting because it takes the indirect signals of rewriting and built it. I also in the loops episode have a skill writing loop. So, I think that's a good one. look at our work over the last couple week or last week and and write loops. And then what was it? Let me look at the third one real quick.

</details>

**丹尼尔·布鲁姆**: 第三个点就是从整周与 Claude 的交互中提取摩擦。它类似于构建新技能，但侧重于**修复现有的技能和工作流**。

<details>
<summary>Original English</summary>

**Daniel Bloom**: So the third one is just taking interactions with Claude over the week. It's similar to building new skills but just fixing existing.

</details>

**克莱尔·沃**: 是的，第三点太天才了，我真希望更多人能学会这么做：**在你的技能里内置反馈与遥测机制（telemetry），然后定期回溯并持续优化**。我见过太多人试图在团队内部做培训，反复强调步骤一、步骤二，但效果甚微。那么你是如何把这些成果打包并分发给全团队的？

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. And then um and then the third one which is so genius and I wish more people did this is build in feedback or telemetry into your skills and then review that over time and improvement. I've seen so many people try to train this into their team like sit and say okay step one step two step three step four etc. just making a skill to say, "Okay, do you have all your connections set up? Do you have this set up?" and then putting it in a shared repository is great. Tell me about how you distribute this across Miro.

</details>

### 工作站模式与团队赋能

**丹尼尔·布鲁姆**: 确实如此。对我们团队来说至关重要的一点是降低门槛。我们当时在纠结到底是用功能极其强大但门槛很高的 Claude Code，还是用 Cowork。最终我们选择了 Cowork，因为对大多数非技术 PM 而言，命令行工具太容易让人退缩了。

为了让全团队都能轻松享受到这些能力，我们构建了一套名为 **PM Workstation（产品工作站）** 的共享插件体系。任何新 PM 想要使用时，不需要去阅读冗长复杂的手册，只需要安装这个插件，它内置了一个引导技能（Onboarding Skill）。该技能会像一位耐心的助手一样逐步询问你：“你的产品领域是什么？你的关键指标有哪些？你常用的沟通频道是哪些？”然后一键自动为你生成定制化的上下文文件、预置好每周准备与每日简报的定时任务。

<details>
<summary>Original English</summary>

**Daniel Bloom**: for sure so basically um I'll say that one of the one of the main things that were important for us and we were debating whether to do this with cloud code which was much more powerful or with uh co-work which was much simpler is accessibility. And we created this plugin called the PM workstation. Instead of having long documentation, it has an onboarding skill that guides each PM through setting up their context, asking what their pillar is, what their goals are, and configuring their morning briefs and weekly preps automatically.

</details>

**克莱尔·沃**: 这太棒了！我见过太多团队试图通过开会培训来硬推 AI 工具，效果往往很差。而通过一个交互式 Skill 来自动完成连接配置和初始化引导，直接放入共享库，这种体验好太多了。

<details>
<summary>Original English</summary>

**Claire Vo**: I love this. I have seen so many people try to train this into their team like sit and say okay step one step two step three step four etc. just making a skill to say, "Okay, do you have all your connections set up? Do you have this set up?" and then onboarding you is so much better.

</details>

**丹尼尔·布鲁姆**: 没错。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Yeah.

</details>

**克莱尔·沃**: 那么你们是将它作为一个共享技能发布的吗？它是作为企业内部插件库的一部分，每个人都可以直接点击安装使用吗？

<details>
<summary>Original English</summary>

**Claire Vo**: I love it. And then do you just do this as like a shared skill? This is a plugin so everybody has it in our library and anybody can access it and you know now it's already like it's become quite a big thing?

</details>

**丹尼尔·布鲁姆**: 完全一致。当大约一年前我构建了用于撰写产品需求文档的 Gem（我们称之为 `Spectacular`）时，我就深刻体会到了这一点。早期为了让大模型产出高质量的需求文档，需要极其繁琐的 Prompt 约束和严苛的规则限制，普通人很难掌握。而一旦你将这些最佳实践封装成即开即用的标准插件或工作站，全员采纳度就会成倍提升。

<details>
<summary>Original English</summary>

**Daniel Bloom**: Uh but yeah I I couldn't agree with you more. I think for me this this landed when about a year ago I built uh uh our spec writing gem call it call it uh spectacular and I I was using it for my own and I built it to be really you know back back in the day a year ago you know getting you know holding its hand to write a great spec was hard. But once you package it into an accessible workstation or plugin, team-wide adoption skyrockets.

</details>

### 未来演进与自主 Agent 愿景

**丹尼尔·布鲁姆**: 关于未来的演进，我认为当前最缺失的拼图——而且凭我个人的直觉，它已经离我们非常近了——主要有两个方面：

1. **脱离本地电脑的云端自主运行能力（Cloud Execution）**：
   目前像 Cowork 这样的工具在很大程度上依然依赖于本地电脑处于开机和运行状态。我认为系统能够在云端全天候独立运行（类似于具有持续运行环境的 Agent 机制）是极其关键的下一步。虽然我现在通过搭建专门的 Slack 频道实现了异步轮询，当我离开电脑时可以通过手机向频道发消息让 Claude 稍后读取，但这仍然不是完全彻底的云端自主运行。一旦 AI 能在电脑关机状态下在云端自主监测、响应并协调事务，那将是质的飞跃。

2. **从“规划建议”到“自主执行”的跃迁（Autonomous Action Execution）**：
   我一直在为这一天做系统准备。目前我的系统不仅能捕获任务，还在主动观察我对每类任务的“关闭条件”（closed scenarios）以及我是如何解决它们的。比如有人在 Slack 上向我索取某个文件或询问会议安排，当系统观察到我在特定场景下的标准回复并取消标记时，它就在学习这一模式。我正在逐步训练它，希望未来针对那些最简单但繁琐耗时的琐事（提供既有文档、确认排期等），系统能够完全自主地代我执行回复，无需我介入。

<details>
<summary>Original English</summary>

**Daniel Bloom**: So it's a really really good question. I think the missing piece and I'm my my personal sense is that it's very close is a the ability to operate in a in the cloud essentially in a way that's uh unrelated to when my computer is open and running. I think that's critical and I think that was also created with the uh with a cloud tag which we don't yet have in our company but I've heard good things also that it's expensive. I don't know. But I think the ability to run uh Claude away from your computer or have it run on its own, something like OpenClaw or like a Hermes, uh is really really critical to do more of these things and to achieve more. I've found some ways to work around this. Like I have a ch a Slack channel that claude poll polls and when I'm away from the computer, I can send him some things uh and then he could read them later. But it's it's still something that has to happen online. Um, and this is I think the the real missing piece. Once I have something that's able to operate uh in the cloud when I'm away from my computer when it's off and you know uh coordinate like act on things uh that that will be huge.

And also closely related is just the ability to actually like you know do do things. So I've been building up the system in order to enable to to basically prepare for it. Um, I've been having Claude not only capture my tasks and when they're done, but basically it looks at my tasks, it assigns like what it looks what it would imagine is a closed scenario. So, let's say something somebody asked a question and I saved it on Slack. So, it would say, okay, if there's a reply and it's unsaved, it means it's done. And then it looks at how I resolve these things. And that's building up towards the the time where I hope that for the simplest task that may take up time and be annoying, you know, when people somebody asks you for something or somebody asks about a file that you need or or know or to or to schedule a meeting, then it would just know to do that on its own and it wouldn't need me and and that's what I'm building up towards and that will be really powerful.

</details>

**克莱尔·沃**: 那确实是终极梦想。虽然我们现在还没完全达到那个阶段，但随着你释放出了如此多的时间和精力，作为一名产品经理，你现在把精力加倍投入到了哪些核心事务上？你认为大家应该把释放出的精力用在哪里？

<details>
<summary>Original English</summary>

**Claire Vo**: That's that's the dream. But we're not at the dream yet. And so I'm curious, you know, we our audience is a lot of PMs and I'm just curious now that you have this extra capacity and time, what are the the product tasks that you're doubling down on that you're doing even more, you're spending even more time on, where do you think the effort should go?

</details>

**丹尼尔·布鲁姆**: 我的回答可能并不出人意料：第一，绝对是**纯粹的深度工作**——与真实客户及用户深入访谈交流，以及进行大量扎实严谨的业务调研。这是任何 PM 梦寐以求希望获得更多时间去深耕的领域。

第二，是当今时代尤为关键的一项全新职责：**持续迭代和改进你的 AI 系统**。这套系统最美妙的地方在于，如果它的底层根基搭建得当，它就能伴随你持续进化。我每周都在利用省下来的时间去研究学习最新的 AI 技术进展，并通过前面提到的 `improve` 技能去甄别筛选外部建议，与 Claude 共同维护升级我们的工作流。在今天，掌握“打磨系统”的能力对于保持竞争力至关重要。

<details>
<summary>Original English</summary>

**Daniel Bloom**: I'm not going to say anything surprising, but just purely in-depth work, that's one. Um so talking to customers, talking to users and a lot of research. I think those two are uh really really important and given and also just the standard things that NEPM aims to get more time for. But I think that in today's world something that really really is important and interesting um and that is new is a um improving the system. So I think the beauty about this is that if a system is built correctly and on the right pillars, it can grow and improve over time. And I've improved my system basically week over week. Uh and this is done through, you know, dedicating time to research and learn about AI, catching up to speed on how things are progressing and implementing them. Um, I have a skill that's called improve uh which I send uh posts and tweets and articles to with like recommendations and tips about uh AI setup and together we review it and see if it fits for me or if it's just like LinkedIn hype and how it can collaborate with what my system is today and we continuously improve the system together with you know tips from uh from a bunch of resources. This is a skill that I think is critical today in order to be able to keep up and and become better. Um, yeah,

</details>

### 情绪共鸣与总结展望

**克莱尔·沃**: 我太喜欢这个回答了。最后是我向每位嘉宾都会提的保留问题：你平时非常有条理，或许脾气也比我温和得多。但当 Claude 不按你的指令行事、当 AI 没有给出你期望的回答时，你会怎么做？你会大喊大叫吗？你还是会保持礼貌客气吗？

<details>
<summary>Original English</summary>

**Claire Vo**: I I I love it. And then finally, my favorite question I ask everybody, you're organized, so maybe maybe you're nicer than me. When Claude is not doing what you want, when AI is not giving you the response that you want, what do you do? Do you yell? Are you nice? Are you polite?

</details>

**丹尼尔·布鲁姆**: 看了你那么多期节目之后，我想我的反应和大家其实差不多。如果我当时在使用 **Whisper** 语音输入，我可能会直接吼出来。我平时没有路怒症（road rage），但我有 **Claude Rage（Claude 暴怒症）**！我不确定自己有没有爆过粗口，但我绝对提高过音量。而且最让我抓狂的是，Whisper 根本识别不出我的情绪起伏——我明明在情绪激动地大声质问，转写出来的文字却平淡如水，就像在问“为什么这个不工作呢？”所以 Whisper 的工程师们，如果你们在听的话，提个功能需求：请在转写中体现出我强烈的惊叹与愤怒情绪！

<details>
<summary>Original English</summary>

**Daniel Bloom**: So, I think after having watched quite a few of your episodes, I think my response is pretty similar to everybody. Um, if I'm using whisper, I may yell. I don't get road rage, but I get clawed rage. So, I think like I can I don't I don't know if I've cursed, but I I've definitely like raised my voice. And I'm also frustrated at the fact that that doesn't go through whisper well enough. like I'm like, you know, exclaiming passionately and then I just see the transcript and it's like, why isn't this working? So, whisper folks, if you're out there, this is a feature request. Make make my exclamations be more felt.

</details>

**克莱尔·沃**: 太搞笑了！说到 Claude Rage，我戴着 **Oura Ring** 智能戒指，我一直有个假说：从我的焦虑和压力心率水平就能准确判断出我当时正在跟哪个大模型打交道。也许未来我们可以推出一个全新的《How I AI》基准测试——“恼火指数测试”（Annoy Bench），专门测试某个 Agent 能把人逼得多抓狂！

<details>
<summary>Original English</summary>

**Claire Vo**: I love it. Yeah, I have this, Speaking of Claude Rage, I have this hypothesis. I have this aura on. I have this hypothesis that you can tell what model I'm working with with like how agitated and stressed I am. So maybe maybe that will be a future how I AI benchmark. I'm I'm baking annoy bench which is like how furious

</details>

**丹尼尔·布鲁姆**: 那绝对太棒了，精准衡量一个 AI 能让人有多抓狂。

今天聊得非常开心。非常感谢 Claire 能让我展示整套系统。我认为这套方案完全是触手可及、人人可用的。相信很多人都会把它加入自己的 `improve` 技能库中。

大家可以在 LinkedIn 上搜索 **Daniel Bloom** 找到我，也可以访问我的个人网站 `danielbloom.com`。这套系统的大部分核心模板与资源都可以在我的网站上免费下载，欢迎大家去体验。

<details>
<summary>Original English</summary>

**Daniel Bloom**: that would be amazing an agent or an AI makes me. This has been so much fun. Thank you for showing us your full system. I think it's totally accessible. Um I think a lot of people are going to put this in their own improved skill and I love how you're figuring out ways to share this with the rest of your team. Where can we find you and how can we be helpful to you?

Awesome. So, this has been super fun, Claire. Thank you so much. Um, people can find me on LinkedIn, Daniel Bloom. Um, and also on my website, I'm Daniel Bloom.com. Uh, I can share some of these resources. Um, this this a big part of this uh system is available uh for download. So, check out the website and yeah.

</details>

**克莱尔·沃**: 太棒了。再次感谢你做客《How I AI》！

<details>
<summary>Original English</summary>

**Claire Vo**: Awesome. Well, thank you for joining How AI.

</details>

**丹尼尔·布鲁姆**: 谢谢你，Claire！

<details>
<summary>Original English</summary>

**Daniel Bloom**: Thank you, Claire.

</details>

**克莱尔·沃**: 非常感谢大家的收看！如果你喜欢本期节目，请在 YouTube 上点赞并订阅，更欢迎在评论区留下你的思考与心得。你也可以在 Apple Podcasts、Spotify 或任何你喜爱的播客平台上收听本节目。欢迎为我们评分和留下评论，这能帮助更多人发现这个节目。如需查看往期所有剧集并了解更多信息，请访问 `howiaipod.com`。我们下期再见！

<details>
<summary>Original English</summary>

**Claire Vo**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>