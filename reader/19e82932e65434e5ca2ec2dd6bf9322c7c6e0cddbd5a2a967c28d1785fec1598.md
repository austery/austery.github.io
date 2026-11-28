---
author: AI Engineer
date: '2026-07-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=uU5Gv2h8-9g
speaker: AI Engineer
tags:
  - prompt-engineering
  - software-development
  - ai-agent
  - security-sandbox
  - multiplayer-collaboration
title: 炉边对话：深入剖析 Anthropic 的 AI 编程智能体生态
summary: 本篇双语访谈记录深入探讨了 Anthropic 的 Claude Code、Claude Tag 及新模型 Fable 在软件工程中的应用。Cat Wu 和 Thariq Shihipar 探讨了 AI 智能体如何从根本上重塑软件开发流程，包括自动代码评审、系统提示词优化、团队协作模式及安全沙箱防护等核心议题。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Simon Willison
  - Cat Wu
  - Thariq Shihipar
companies_orgs:
  - Anthropic
products_models:
  - Claude Code
  - Claude Tag
  - Claude 3.7 Sonnet
  - Fable
  - Opus
  - Haiku
media_books: []
status: evergreen
---
### 炉边对话与 Fable 的发布

**主持人**: 欢迎来到今天的炉边对话。今天我们非常高兴能邀请到来自 **Anthropic** 的 **Thariq Shihipar** 和 **Cat Wu**。我们将深入探讨 **Claude Code**，同时也会聊聊最近新闻中非常热门的 **Fable**。事实上，就在大约一分半钟前，**Fable** 重新上线了，我现在已经可以使用它了。所以，如果大家想现在跑出房间去消耗掉你们的 **Fable** 额度，我完全不会怪你们。但我们接下来会有一场非常精彩的对话，所以请大家务必留下来。现在，请大家用热烈的掌声欢迎 **Thariq** 和 **Cat**。

<details>
<summary>Original English</summary>

**Simon Willison**: Welcome to this fireside chat. I have with me Thariq Shihipar and Cat Wu from Anthropic. We are going to be diving deep into Claude Code and we'll probably talk a little about this Fable thing that's been going on that's been out there in the news. Actually, on the subject of Fable, literally a minute and a half ago, Fable came back. Like Fable is now available to me. So, if you all want to run out of the room and start using up your Fable credits, I wouldn't hold that against you. But we're going to have a great conversation. So, please stick around. But yeah, please welcome Cat and Thariq for me.

</details>

**Cat Wu**: 谢谢你邀请我们。是的，我们确实是特意为这次对话挑选的时机。

<details>
<summary>Original English</summary>

**Cat Wu**: Thanks for having us. Yeah, we timed it for the chat for sure.

</details>

**Thariq Shihipar**: 没错，这正是这一切发生的原因。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yep. Yep. This is why it's all happening.

</details>

---

### AI 智能体如何改变日常工作

**主持人**: 这一年确实有些不可思议。**Claude Code** 是在去年的二月份发布的，到现在还不到一年半的时间，而在当时它只是 **Claude 3.7 Sonnet** 发布会上的一个附带提及的要点。我想听听你们的看法，在过去的一年里，既然我们已经拥有了这些真正能为我们工作的编程智能体，你们日常的工作方式发生了怎样的变化？

<details>
<summary>Original English</summary>

**Simon Willison**: This year has been somewhat absurd. It's amazing. Claude Code came out in February of last year. It's under a year and a half old and it was a bullet point on the Claude Sonnet 3.7 launch. I'd love to hear from you. How has what you do on a day-to-day basis changed in the past year now that we have these coding agents that actually work for us?

</details>

**Cat Wu**: 我还记得当我们刚发布 **Claude Code** 和 **Sonnet 3.7** 的时候，你交给它一个任务，你必须非常仔细地监控它试图做的每一件小事。我记得当时我会极度仔细地阅读每一个权限请求提示，而且我经常会选择拒绝。我会总是对它说“不，不，不”，比如“你检查过这个文件了吗？”、“你检查过那个文件了吗？”。而现在，随着每一个模型世代的迭代更新，情况变得令人难以置信。我觉得我们都有机会往后退一步，把大量繁琐的底层的具体实现工作委托给 **Claude**。这为我们释放了大量的时间，让我们去思考更具创意的工作，比如既然我们知道 **Claude Code** 可以帮我们实现大部分功能，那么我们现在应该为用户提供怎样正确的体验。而现在有了 **Fable** 之后，这完全是又一次全新的阶段性跨越式的提升。对于我们大量的用例来说，你现在甚至可以直接使用 **Fable** 一次性生成（oneshot）一整套功能。所以能看到这种转变，并与社区中的各位共同经历这个过程，真的是太棒了。

<details>
<summary>Original English</summary>

**Cat Wu**: I remember when we first came out with Claude Code and Sonnet 3.7, you would give it this task and you would have to closely monitor every single little thing that it tried to do. I remember I would read every permission prompt extremely carefully. I would frequently say no. I would always say no no no like did you check this file? Did you check that file? And now it's been incredible with every model generation. I feel like we've all gotten a chance to just take a step back, delegate a lot more of the like menial implementation to Claude. And it just freed up a lot of our time to think about more creative work like what is the right experience that we should be providing to our users now that we know Claude Code can implement a lot of it. And now with Fable, it's just a totally different step change improvement. We see for a lot of our use cases that you can actually oneshot a ton of features with Fable now. So it's been amazing to see the transition and to go through this with all of you in the community.

</details>

**Thariq Shihipar**: 是的，我想我还记得收到关于 **Claude Code** 的第一条短信时的情景。我最好的朋友之一对我说：“哦，你必须去试试 **Claude Code**。”那大约是在 **Opus 4** 刚发布的时候。我试了一下，当时我的反应就是：“哦，天哪，我现在必须去 **Anthropic** 工作了。”那还只是 **Opus 4** 的时代。我的意思是，那是一个非常出色的模型，但是正如刚才所说，你当时必须面对各种权限提示。而且我觉得很疯狂的一点是，人类的遗忘症是多么严重，我现在会觉得“自动模式（auto mode）不是一直都在这里吗？”，我甚至都不记得以前点过“同意”和“允许”了。

对于我个人而言，我现在正试图突破自己的是：“我们必须做出比以往任何时候质量都更高、更卓越的工作。”因为现在的输出质量已经高得令人难以置信了。我一直在用它来剪辑大量的视频，我的态度是：“好吧，这必须在几个小时内达到我们品牌团队非常苛刻的要求，否则我们根本无法完成。”因此，我正试图借助 **Fable** 来实现这种工作方式的转变——我们可以比以往任何时候都更快地完成我们做过的最好的工作。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, I mean I think I remember the first text I got about Claude Code. One of my best friends was like, "Oh, you need to go try Claude Code." And it was about just when Opus 4 came out and I tried it and I was like, "Oh, shit." Like I need to work at Anthropic now, you know? And that was Opus 4 which I mean great model but like yeah you were permission prompts and uh yeah I think it's kind of crazy how much amnesia we have I think where I'm like oh like auto mode has always been here right like I don't even remember pressing like yes and allow. Um and yeah I think for me the big thing that I'm trying to push myself is like oh we have to do like higher quality work than we've ever done before. You know like the outputs are like incredibly high quality. Like I've been using it to edit videos a bunch and I'm like okay it has to meet the very exacting demands of our brand team and in a couple hours or we just can't do it you know and so um yeah I think that's how I'm sort of like trying to shift with Fable where it's like okay the best work we've ever done like faster than we've ever done it before.

</details>

---

### 软件工程的重构与代码库的本质

**主持人**: 我个人也有完全相同的感受。现在软件工程其实变得更难了，因为我们可以承接的任务的野心和上限被大幅拉高了。现在既然有这些工具作为后盾，我对自己的期望值变得高得多，这很有趣，但同时也需要做大量的思考工作。

<details>
<summary>Original English</summary>

**Simon Willison**: I've certainly been finding that myself like software engineering is getting harder because the level of ambition of the stuff we can take on has gone up like I have such higher expectations of myself now that I have these tools to back me up which is fun but it's a lot of work.

</details>

**Cat Wu**: 是的，所有的思考和规划过程都是非常消耗精力的。

<details>
<summary>Original English</summary>

**Cat Wu**: Yeah. It's all the thinking is you know it's tiring.

</details>

**主持人**: 那么，有哪些在一年之前被奉为圭臬的传统软件工程常识，在如今这个全新的世界里，你们认为已经不再适用了？

<details>
<summary>Original English</summary>

**Simon Willison**: And so what's a piece of conventional software engineering that was true a year ago that you don't think holds anymore in this new world?

</details>

**Cat Wu**: 我觉得我们在工程师技能要求上看到的最大转变之一是，在两年前，一个典型的产品经理去拜访一堆客户，然后在六个月的时间里与跨职能团队就某份产品需求文档（PRD）达成一致，接着写出非常详尽的规格说明书（spec），在写下第一行代码之前详细讨论如何实现，这在当时是非常普遍的。而现在，情况完全颠倒过来了。

对于很多工程师，我给出的建议是：大家应该更多地培养自己的商业直觉和产品感。去思考我们究竟应该构建什么，因为现在从产生想法到把它实际构建出来之间的时间线已经缩短得太多了。它从六到十二个月，缩短到了可能只需要一周。这意味着我们所有人对于“什么东西是值得构建的”、“什么东西能真正推动我们业务的发展”需要有更好的品味和判断力。因此，在大多数产品领域中，产品 taste 和商业直觉的价值在上升，而在具体执行层面的权重稍微有所下降。当然，对于基础设施（infra）而言，确保所有细节完全正确依然非常关键。

<details>
<summary>Original English</summary>

**Cat Wu**: I think one of the biggest shifts that we're seeing in the ENG skill set is I think you know two years ago it was pretty typical for a product manager to go talk to a bunch of customers and over the course of six months align with like cross functional teams on some PRD and then write this like thorough spec um and uh doc on how exactly we'll implement this before the first line of code gets written and now things are like completely turned the opposite way. I think for a lot of engineers, the push I would give to a lot of folks in the room is to develop more of your business sense and product sense on what is it that we should build because now that the timeline between having this idea and building it is so much shorter. It's down from six to 12 months to maybe even a week. That means all of us need to have better taste on what is it that is worth building. What is it that will actually inflect the businesses that we're working on. So I think it's like an increase in value on product taste and business sense and a bit lower on execution in most product domains. Of course for infra there's still a very heavy emphasis on making sure all the details are right.

</details>

**Thariq Shihipar**: 对我来说，现在“重写代码（rewrites）”变成了一件好事。因为我觉得以前大家觉得最糟糕、最不应该做的事情，现在其实完全可行了。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah. I think for me it's like rewrites are now good. Like I think that the worst thing you could do is now actually fine.

</details>

**Cat Wu**: 没错，完全同意。特别是以前那些关于“永远不要重写代码”的教条，我现在是重写代码的坚定支持者。如果你有一套优秀的测试套件，重写代码实际上会迫使你去确保你拥有足够好的测试。

<details>
<summary>Original English</summary>

**Cat Wu**: Yeah. Exactly. Exactly. Like especially mythical man stuff like never rewrite like I'm a pro rewriting now you know like if you have a good test suite I think actually the rewrite forces you to like make sure you have a good test suite.

</details>

**Thariq Shihipar**: 我觉得人们往往低估了一点：代码库本身就是一份规格说明书（spec），而且它可能是你手中唯一一份最真实的规格说明书。因为没有人能了解代码库里的每一个分支逻辑。你可以把它作为一个现成的上下文实体，去提炼它，或者基于它创建其他版本。比如，我们用 **Rust** 重写了 **Bun**。它运行得非常好，我现在日常就在使用它。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: I think that what people undercount is like a codebase is a spec and maybe it's the only copy of the spec that you have right because like no one knows every branching part of the codebase and yeah you can take this as like an artifact and like distill it or create other versions of it. Obviously like yeah we rewrote Bun in Rust. And it works great like it's live for me right now.

</details>

**主持人**: 不过你们还没有在 **Bun** 和 **Rust** 上正式发布 **Claude Code** 对吧？还是说已经……

<details>
<summary>Original English</summary>

**Simon Willison**: But you're not shipping Claude Code on Bun in Rust yet right or is that...

</details>

**Thariq Shihipar**: 在内部我们已经开始这样做了。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Internally we have.

</details>

**主持人**: 哇，那太令人兴奋了。

<details>
<summary>Original English</summary>

**Simon Willison**: Wow. Oh that's exciting. Yeah.

</details>

**Thariq Shihipar**: 是的，没错。你刚才提到的关于重写的观点非常有趣，因为对我来说也是如此。你可以先写好一套优秀的测试套件，然后生成三种不同的实现方案，并挑选其中最准确的一种。我现在做了大量的原型设计。我一直都喜欢做原型，而现在我甚至可以在参加会议期间在手机上做原型，这样我随后就可以直接接手继续开发，这现在完全行得通，真的很不可思议。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah. Yeah. I think what you're saying there about the rewrites thing has been really interesting for me as well because you can almost come up with a good test suite and then spin up three implementations and pick which of those implementations was the most accurate. I'm doing a lot more prototyping now. I've always been a prototyper and now I prototype things on my phone during the conference just so I've got something that I can pick up later on and that's working now which is kind of extraordinary.

</details>

---

### Claude Tag 与团队多人协作

**主持人**: 最近的另一个重大发布是 **Claude Tag**，对于我们其他人来说，这大概是一周前发布的产品。据我了解，**Claude Tag** 在 **Anthropic** 内部被非工程人员大量使用。非工程师都在用 **Claude Tag** 做些什么？

<details>
<summary>Original English</summary>

**Simon Willison**: So the other big launch recently was Claude Tag which that's what a week old now I think at least for the rest of us. Claude Tag I understand that's being used in Anthropic by non-engineers a great deal. What kind of things are non-engineers doing with Claude Tag?

</details>

**Cat Wu**: **Claude Tag** 是一个嵌入在你们团队协作工具中的智能体。我们上周在 Slack 中推出了它。**Claude Tag** 的核心不同之处在于，它在默认情况下就是**多人协作模式（multiplayer）**。一旦你将 **Claude Tag** 添加到一个 Slack 频道中，你和你的队友都可以随时介入，共同协作处理 PR。

另一个重大区别在于它是**主动式（proactive）**而非响应式的。你可以告诉 **Claude Tag**：“嘿，监控这个频道里的每一个 Bug 报告，提交一个 PR 去修复它，并标记最后修改这部分代码的工程师。”它就会在整个频道的生命周期中自动执行这些操作，无需你每次手动去触发它。

第三个重大转变是，我们为它加入了**团队记忆（team memory）**功能。如果你在频道中告诉它你的偏好，它会在未来的每一次交互中记住它。例如，如果你总是希望它去调试系统崩溃（outages），但不想让它调试普通警告（warnings），你只需要在频道中用自然语言告诉它，它就会为你以及团队中的每一个人记住这一点。在内部，我们视 **Claude Tag** 为 **Claude Code** 的自然演进，我们认为这是我们内部工作方式的重大转变。目前，**Claude Tag** 已经完成了我们产品团队 65% 的 PR 提交。

<details>
<summary>Original English</summary>

**Cat Wu**: So Claude Tag is a Claude that lives in your team's collaboration tools. We launched it last week within Slack. The thing that's different about Claude Tag is it's multiplayer by default. And so once you add Claude Tag into a Slack channel, you can chime in, your teammates can chime in, and you can collaborate together on the PR. The other big difference is that it's proactive instead of reactive. So you can tell Claude Tag, hey, monitor every bug report in this channel, put up a PR to fix it, and tag the engineer who last touched this part of the codebase, and it'll do it for the lifetime of the channel without you having to manually tag it in. And then the third big shift that we've seen is we've added team memory into this. So if you tell Claude Tag your preferences in the channel, it'll remember this for every future post. So if you wanted to always debug outages, but you don't want it to debug warnings, just tell it that in natural language in the channel and it'll remember it for you and everyone else on your team. Internally we see Claude Tag as the evolution of Claude Code. So we see this as a large shift in how we work internally. Claude Tag currently lands 65% of our product PRs.

</details>

**主持人**: 这 65% 是指整个 **Anthropic**，还是仅针对 **Claude Code** 团队？

<details>
<summary>Original English</summary>

**Simon Willison**: For all of Anthropic and for Claude Code or just for Claude Code?

</details>

**Cat Wu**: 这是针对我们的产品工程团队。也就是说，我们内部版本的 **Claude Tag** 提交了我们产品工程团队 65% 的产品 PR，这是一个巨大的转变，这已经超过了一半的 PR 数量。

我们观察到人们在 **Claude Code** 和 **Claude Tag** 之间的分工是：当你需要交互式地与智能体协作迭代、处理最复杂的任务时，**Claude Code** 依然是最佳选择。而 **Claude Tag** 则非常适合让它代表你主动开展工作，这样你就不再需要为可能出现的每一个 Bug 报告手动去启动 **Claude Code**。

<details>
<summary>Original English</summary>

**Cat Wu**: Uh this is just for our product engineering team. So our internal version of Claude Tag lands 65% of our product PRs right now. And this is a huge shift. This is like this is more than 50% of our PRs. Um, and the way that we actually see people split work between Claude Code and Claude Tag is Claude Code is still the best place for your most complex tasks when you're interactively iterating with the agent. But Claude Tag is great for having it work proactively on your behalf so that you no longer need to manually kick off Claude Codes for all of the bug reports that might come up for features that you're working on.

</details>

**Thariq Shihipar**: 至于非编程场景，我看到人们也会使用 **Claude Tag**。比如在这次演讲之前，我们问 **Claude Tag**：“嘿，**Fable** 什么时候发布？”我们想确保我们的演讲时间能跟官方公告对齐。**Claude Tag** 会去搜索我们的 Slack，查看谁说了什么。所以作为公司内部的搜索引擎，它非常有价值。因为它拥有你们产品的所有上下文。你可以向它询问指标相关的问题。很多时候，当你做决定时，你希望有数据支持，那么你就可以把它接入到你的事件存储（event store）中。我看到我们的市场团队会做类似的事情，比如：“嘿，给我讲讲这个功能。”他们虽然不是程序员，但 **Claude** 是。它可以直接克隆代码库并解释：“哦，是的，这就是那个功能，它是这样运作的，这是我使用该功能的录像。”它开启了非常广泛的用途，我们目前仍然处于探索这一模式的早期阶段。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah. And for like non-coding cases like I think we've seen people use Claude Tag just uh like for example before this talk we asked Claude Tag like hey when is Fable releasing? We wanted to make sure that like you know we'd line it up with the announcement. Um, and so Claude Tag would search our Slack and look at, you know, who's been saying what. Uh, so as a search engine for your company is really valuable. Uh, it has all the context for your product. So you can ask it like metrics related questions. And often times when you're making decisions, you want it to be informed by like, you know, what do the metrics say? And then so like you hook it up to your event store. Um, I've seen like our marketing team do things like, oh, like, hey, tell me about this feature. And, you know, they're not programmers, but Claude is a programmer. It can clone the codebase and be like, "Oh yeah, this is like, you know, the feature. This is what it looks like. This is a recording of me using the feature, you know." So like um yeah, it just enables a whole wide variety of things. And I think we're still early on in figuring that out. Yeah.

</details>

**主持人**: 这正是 **Claude Code** 故事中最引人入胜的地方之一——你们用 **Claude Code** 来构建 **Claude Code**，而且在一年半前公开发布之前，你们就已经在内部这样做了。对于编程智能体，我之前的一个困惑是：我明白如何作为个人去使用它们，但我不清楚如何在团队协作环境中使用它们。听起来 **Claude Tag** 就是你们目前对于团队协作层面的解答。

<details>
<summary>Original English</summary>

**Simon Willison**: Well, I feel like this is one of the fascinating things about the Claude Code story is you use Claude Code to build Claude Code and you've been doing this since presumably before the public launch of Claude Code a year and a half ago. And yeah, one of the problems I've had with coding agents is I get how to use them as an individual, but I'm not really clear on how I use that in a team environment. It sounds like Claude Tag is your current answer to that sort of team collaborative layer for this stuff.

</details>

**Cat Wu**: 没错。目前我们很大一部分会话实际上都是多人协作模式。这意味着我可能会说：“嘿，我认为我们应该在协作空间里实现这个新功能。”然后我会标记 **Claude Tag** 让它来做第一版实现。接着我会告诉 **Claude Tag**：“分享一段你最终实现效果的录像。”然后我会标记设计团队来看看，他们会给出微调意见，之后再把 PR 转给前端或相关工程师推向生产环境。这是一种非常流畅的体验。我们仍在摸索如何让多人更好地在同一个会话中进行引导，但我们发现大家只需观察别人如何使用，就能很自然地遵循那些协作规范，将 **Claude Tag** 整合进团队其实非常直观和简单。

<details>
<summary>Original English</summary>

**Cat Wu**: Exactly. And a large percentage of our sessions are actually multiplayer right now. So that means maybe I say, "Hey, I think we should like implement this new feature in co-work." And I'll tag in Claude Tag to do a first pass at it. And then I'll tell Claude Tag, hey, just like share a recording of your final implementation. And then I'll tag in design to take a look and they'll nudge it and then they'll pass it on to eng to like take it to the finish line and get it out to prod. And so it's been this like very fluid experience. We're still trying to iron out what the social dynamics are for steering the same session, but we found that people just like observe how others use it and then follow those social norms and it's actually been pretty easy for pretty intuitive for us to integrate Claude Tag into our teams.

</details>

**Thariq Shihipar**: 是的，我认为这对于教学非常有帮助，而且能有效打破信息孤岛。因为当大家看到有人在频道里直接说“@Claude 帮我修复这个”时，每个人都在看着这个协作过程，无形中大家都提升了使用 **Claude** 的水平。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, I think it's great for like teaching people and also like reducing silos because you know like if you see someone just be like hey at Claude fix this or something you're like uh you know like there's some societal or not societal like just like the fact that everyone is seeing you use Claude together sort of levels up how you use Claude as well.

</details>

---

### 产品功能的优先级与决策机制

**主持人**: 既然大家都公开看着你用 **Claude** 工作，质量自然不能滑坡。那么，在我们讨论如何使用 **Claude** 来构建 **Claude** 的过程中，你们是如何处理工程中最难的问题——也就是优先级排序的？当构建和交付一个功能的成本变得如此低廉时，你们如何决定哪些功能是值得构建和发布的？这绝对是个难题。

<details>
<summary>Original English</summary>

**Simon Willison**: Right, you want to do work that you're proud to do in public where the quality doesn't fall off the cliff. So since we're talking about using Claude to build Claude, how do you deal with the hardest problem in all of engineering—it's prioritization right? How do you decide which features are worth building and shipping when building a feature is so much more inexpensive now?

</details>

**Cat Wu**: 我们有几种应对方法。首先，我们每天都在深度吃自己的狗粮（dogfooding）。一旦我们在产品中遇到想要做但做不到的事情，我们不会去寻找别的替代方案，而是直接修改和升级我们的产品，让它能够支持这个用例。我们内部有非常浓厚的“吃狗粮”文化。在我们将产品分享给全世界之前，我们会先分享给 **Anthropic** 内部的每一个人，并分享给一些能给我们提供非常坦率、甚至“毒舌”反馈的早期客户。反馈越犀利越好，我们会不断迭代，直到大家爱上它。

我们内部对于一个功能在分享给世界之前，需要达到多少活跃用户和留存率有非常明确的指标门槛。因为这个标准非常清晰，每个工程师都知道自己要努力达到的目标。这也提升了我们产品的打磨精细度，因为如果一个功能不够精致，用户就会流失，那我们就不能发布这个功能。

<details>
<summary>Original English</summary>

**Cat Wu**: So there's a few ways we approach it. One is we dog food our products every single day. Whenever there's something that we want to be able to do in our products that we're not able to instead of finding a different solution we fix our product so that it can support this case. We have a very heavy dog fooding culture internally. So before we are able to share our products with everyone in the world, we share it with everyone within Anthropic and we share it with some early customers who give us very honest feedback about it. The more brutal the better and we iterate until people love it. So we have an internal bar for the number of active users and the amount of retention a feature has to have before we share it with the world. And because this bar is very clear, every engineer knows what they're trying to hit. And I think this also levels up our polish because if the feature isn't polished, people will churn and then we shouldn't ship that feature.

</details>

**主持人**: 你们能举个让你们感到惊讶的功能例子吗？比如在你们推出它时，用户参与度出乎意料地高，从而从一个原本可能不会发布的小尝试变成了最终的正式产品？

<details>
<summary>Original English</summary>

**Simon Willison**: Do you have an example of a feature which surprised you? You rolled it out and the engagement was off the charts and it became something that was unlikely to be shipped that actually turned into a real product thing.

</details>

**Cat Wu**: 我有一个例子。我们团队里有很多人非常喜欢**远程控制（remote control）**功能。远程控制允许你使用移动设备或者在 Web 浏览器中，连接到你本地 CLI 中运行的 **Claude Code** 会话。我个人其实从来没有这个需求，因为我可以直接在手机上启动任务，让它在云端会话中运行，而不需要占用我本地的环境。我想这是因为我做的都是比较简单的编码任务。原来我不太理解这个需求，我觉得大家直接配置好自己的远程开发环境就好了。

但实际上，一旦我们推出了远程控制，我交流过的非常多的人都说：“现在我每天晚上做的事情就是，把笔记本电脑插上电源，合上屏幕或者开启一堆远程控制会话，锁定屏幕，然后坐在沙发上用手机去控制 **Claude Code**。”因此，我们现在正在全力跟进这一工作流。我现在自己也完全是这样做的，我能在更舒适的环境下在笔记本电脑上完成更多工作，因为我可以随时进行远程控制，这真的非常有趣。

<details>
<summary>Original English</summary>

**Cat Wu**: I do have one. So a lot of folks on our team love remote control. So remote control lets you connect use your mobile device or Claude in the web browser to connect a local Claude Code session running in your CLI. I never have this need because I just kick off the task directly on mobile and it runs in a cloud session and doesn't use my local environment. I think this is because I'm doing very easy coding tasks. But this is something where I didn't totally understand it. I was like, hey, people should just set up their remote dev environments. But in practice, once we rolled out remote control, so many people who I talk to are like, "Okay, now what I do every night is I plug my laptop into a power charger, close the screen or like open a bunch of remote control sessions, lock the screen, and then use their mobile phone from their couch to control Claude Code." And so this has been this flow that we're now leaning into that I didn't originally get, but now I do. I do exactly that. I get so much work on my laptop done from more comfortable environments because yeah, I can remote control it now. That's really fun.

</details>

---

### 自动化代码评审与信任建立

**主持人**: 代码评审（code review）是如何工作的？会有真人去审核进入 **Claude Code** 生产环境的每一行代码吗？如果没有，你们是怎么做的？如何保持代码质量？

<details>
<summary>Original English</summary>

**Simon Willison**: How does code review work? Are you reviewing does a human being review every line of production code that makes it into Claude Code? And if not, what are you doing? How do you keep the quality up?

</details>

**Thariq Shihipar**: 这在很大程度上取决于具体的任务。对于重要的区域，我们设有**代码负责人（code owners）**。例如系统提示词（system prompt）就是一个例子，你修改它必须获得负责人的批准。代码负责人会对该代码区域的质量负直接责任，他们必须批准所有触及该区域的 PR。

此外，我们的代码评审机器人会审核所有的 PR，并且往往承担了大部分的评审工作。对于复杂的 PR，你可能会创建一个“Artifact”来解释这个 PR，以便其他人进行评审。同时，我们在自动化测试和 CI/CD 验证上做了大量投入，确保一旦有任何测试失败，我们能立刻发现。我们有一个非常强大的测试环境，能让 **Claude** 去运行 **Claude Code** 并测试它。所以我们采取的是一种多管齐下的代码评审方式。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Sure. Yeah. It varies on the task a lot. So we for important areas we have code owners, right? And so, the system prompt is kind of an example where we have a code owner, you really need to submit your you need to get their approval. I guess the code owner is directly responsible for the quality of that area of the code and they need to approve the PR that touches it. That's right. We have code review Git bots review everything and so that goes on every PR and often times like that's doing the bulk of the review. I think that for more complex PRs you might make like an artifact to explain the PR so that other people can then review. And yeah we just invest a lot into verification CI/CD things like that to make sure that anytime anything fails like we have a test, we have a really robust environment. Claude can control Claude Code and test it. So there is a multi-pronged approach to code review.

</details>

**Cat Wu**: 总的来说，我们正在努力迈向一个不需要人类参与评审的阶段。因此，对于最核心、最关键的代码修改，目前仍然会有代码负责人进行人工审查。但是，对于边缘和外围区域的修改，我们现在已经开始完全让 **Claude Code Review** 自动进行审查了。

这听起来有些令人担心，但我们经历了六个多月的实践才走到这一步。建立对自动代码评审的信任是一个循序渐进的过程。在最开始，我们对所有的修改进行人工审查；随后，我们逐渐发现对于某些特定文件的修改，自动评审能够捕获 100% 的问题，那么这些文件就不再需要人工干预了。

每当我们进行故障复盘（incident review）时，我们会回看导致故障的 PR，并思考：“我们该如何升级自动代码评审，以便下次能捕获此类问题？”接着我们会把这些 PR 加入到评估集（eval set）中，确保未来的代码评审更新绝对不会在此类指标上发生退化（regress）。所以，将人类从代码评审中解放出来是一个巨大的进步。这并非一朝一夕之功，但通过长达数月在基础设施上的持续投入，它能给你足够的信心，确信自动评审能够替你把好关。

<details>
<summary>Original English</summary>

**Cat Wu**: In general we are trying to move to a world where humans don't need to be in the loop. And so for the most critical core changes to the core of Claude Code and other the cores of other products, there is always a code owner and they do manually review all the changes. But increasingly for the changes that are at the outer layers, we actually have Claude Code Review fully review those. That sounds pretty scary but we've had this six plus month long process to get here and I think there are like baby steps that you take to build up trust with code review. So in the beginning we would have human review for everything and then increasingly we would say okay for code changes that touch these files, code review is catching a 100% of the issues there. So we actually don't need a human to be manually reviewing those. And then also when we have incident review, we look at the PRs that cause the incident and we say okay how do we update code review to catch that and then we also take those PRs and add it to an eval set to make sure that our future changes to code review never regress that metric. So removing humans from the code review loop is a big step forward. I think it can sound scary and it's not something that you can do overnight, but it is something that you can do through like many months of investment in the infrastructure to give you the confidence that code review is catching everything that you care about.

</details>

---

### 模型评估与提示词的“减肥”艺术

**主持人**: 提到建立对模型的信任，这非常有趣。因为我发现，比如对于 **Opus 4.8**，如果我让它构建一个运行 SQL 查询并输出 JSON 的端点，我确信它能完全写对，我不需要仔细去审阅它。但是当新模型出现时，我仍然不知道如何快速建立对新模型（比如 **Fable**）的信任，确保它不会在旧模型表现良好的地方翻车。当新模型发布时，它是如何影响你们对于它“能做什么”和“不能做什么”的直觉判断的？

<details>
<summary>Original English</summary>

**Simon Willison**: So, it's interesting you mentioned building trust in the models because that's something I found is like I know that Opus 4.8 if I ask it to build me a JSON endpoint that runs a SQL query and outputs JSON, it's just going to get it right. Like that's not something I have to review closely. But then a new model comes along and I still don't know how do I build trust in Fable quickly that it's not going to mess things up that Opus didn't. Is that something that you have to think about much—how does the new model affect your intuition for what it can do and what it can't do?

</details>

**Cat Wu**: 这正是我们随着时间推移不断构建评估集的原因，只有这样新模型才能实现“即插即用（drop-in）”。当我们拿到一个新模型时，我们会运行整个评估集，确保比如 **Fable** 的表现指标严格优于 **Opus 4.8**，这才能给我们直接替换的信心。

<details>
<summary>Original English</summary>

**Cat Wu**: The main reason that we're building up this eval base over time is so that new models can be a drop-in replacement because what we do when we have a new model is we run the whole eval set and we make sure that for example Fable is strictly better than Opus 4.8 and that gives us the confidence to drop it in.

</details>

**主持人**: 这些评估指标是针对整个 **Anthropic** 的，还是针对你们 **Claude Code** 团队特有的？

<details>
<summary>Original English</summary>

**Simon Willison**: And are those model evals for Anthropic as a whole or are these Claude Code team specific evals that you're using?

</details>

**Cat Wu**: 两者都有。我们团队有专门的评估集，同时因为我们会在 **Anthropic** 内部的每个代码库上运行代码评审，所以我们也有针对这一部分的评估指标。而对于自动模式（auto mode），我们不仅在公司内部的所有用户中进行评估，还委托了多个外部测试团队进行红队测试（red teaming），让他们创建包含提示词注入（prompt injections）和恶意输入的对抗环境，以确保自动模式不会让任何恶意输入通过。

<details>
<summary>Original English</summary>

**Cat Wu**: We have both. So we have evals on our team and we run code review across every repo within Anthropic and so we have evals for that and for things like auto mode we not only have evals across every user within Anthropic but we've also commissioned multiple external testers to red team this to create environments with prompt injections and malicious inputs and make sure that automode doesn't let any of those pass.

</details>

**主持人**: 至于 **Claude Code** 本身，这也是我在自己构建工具时遇到的挑战。我想知道我对系统提示词做出的改进，是否真的提升了产品质量？这是最基本的产品特定评估。但我目前仍然没有很好的方法来做这件事。你们是如何做到能完全确信对系统提示词的微调确实带来了更好的输出？

<details>
<summary>Original English</summary>

**Simon Willison**: So for Claude Code itself and this is a challenge I've had with stuff I'm building. I want to know if the system prompt improvement I made actually improved the product. Right? That's the sort of most basic form of product specific eval. And I still don't have a great feel for how to do that. Is that something that you're doing such that you have complete confidence that this tweak that you've made to the system prompt does result in better output?

</details>

**Cat Wu**: 我们其实并没有 100% 的确信，但我们做了很多努力来确保性能不会发生退化。我们的起点是我们信任的一套外部评估集，并辅以一套更大的、我们同样信任的内部评估集。

首先，我们主要针对**能力（capability）**进行优化。即在给定任务的完整定义和全部代码库的情况下，**Claude** 能否做出正确的决策，完整地修复 Bug 并通过所有测试。这是我们优化的出发点，因为这最符合用户的直接诉求。

但是，还有很多行为会影响用户在使用 **Claude Code** 时的感受。例如，人们非常不喜欢 **Claude Code** 对他们说“我该去睡觉了”（笑声），或者说“我已经完成了五部分中的两部分，你想要我继续吗？”——用户的心态是“当然，请继续工作”。

因此，我们正在构建一套**行为评估集（behavioral evals）**来捕捉这些问题。当收到用户反馈时（请大家务必多向我们反馈意见），我们会对这些问题进行优先级排序，然后逐一为它们构建评估指标。虽然这无法做到 100% 的覆盖率，但不断提高覆盖率绝对是我们的首要任务。

<details>
<summary>Original English</summary>

**Cat Wu**: We don't have complete confidence but we do a lot to make sure that we don't regress performance. So the starting point that we have is we have a suite of external evals that we trust and we complement that with an even larger suite of internal evals that we trust. Uh to start we mainly optimize for capability. So given a complete definition of a task and the full codebase does Claude make the right decisions and fully fix the bugs and pass all the tests. So that's the starting point and that's the thing that we optimize for because it is like most directly what users want. But there's a lot of like behaviors that impact how users feel when they work with Claude Code. For example, people really don't like it when Claude Code says it's like time to go to sleep. [laughter] Or people really don't like it when it says like, "Hey, I finished two out of five parts. Like, do you want me to continue?" Like, "Yes, please continue." Um, and so we're building up a set of behavioral evals to catch these. And as we get user feedback, please be loud with us about your user feedback. As we get user feedback, we just rank, okay, these are the priority issues. And we go down one by one and build evals for each of them. So, it's not 100% coverage, but it is a priority for us to increase the coverage.

</details>

**主持人**: **Claude Code** 团队与 **Anthropic** 内部训练模型的团队之间有多少交集或互动？这是一种非常紧密的合作吗？

<details>
<summary>Original English</summary>

**Simon Willison**: And how much overlap is there between the how much interaction is there between the Claude Code team and the teams at Anthropic who are training the models in the first place? Is that quite a close collaboration?

</details>

**Cat Wu**: 在 **Anthropic** 内部，大家的协作非常紧密。我们会经常开会讨论，比如我们期望下一代模型能够具备什么能力。我们的研究团队在向公众展示成果方面也做得非常棒，我们经常会在博客中讨论我们如何锁定更长跨度（longer-horizon）的任务，以及如何训练 **Claude** 达到“诚实、无害和有帮助（HHH）”。我们也花了很多精力确保模型符合你的意图，即使你的意图表达得比较模糊。当然，我们建议大家还是尽量具体地描述你的需求。虽然模型能结合所有上下文并做出合理的假设，但这确实是一个富有成效的合作过程。

<details>
<summary>Original English</summary>

**Cat Wu**: Across Anthropic, we all work quite closely together. So we meet often to talk about like what do we expect the next generation of models to be able to do. I think our research team has also been amazing about just like showing this publicly. So we often talk in our blog posts about how we're targeting ever-increasing longer horizon work, how we train Claude itself to be honest, harmless, and helpful. Um, we also put a lot of effort into making sure that it's aligned with your intent, even if your intent is expressed in a fuzzy way. Of course, try your best to be specific about what you want. So Claude has all the context, but even when you're not specific, we teach Claude to make good assumptions and yeah, I think it's been a productive partnership.

</details>

---

### 系统提示词瘦身与大模型裁判

**主持人**: **Thariq**，你今天早上提到，因为 **Claude Fable** 的出现，**Claude Code** 的系统提示词（system prompt）减少了 80%。你能详细聊聊这是怎么回事吗？你们得以删掉了哪些内容？

<details>
<summary>Original English</summary>

**Simon Willison**: And so Thariq, this morning you mentioned that the system prompt for Claude Code has been reduced by 80%. Because of Claude Fable, can you go into a little bit more detail about what that looks like? What kind of things have you been able to drop?

</details>

**Thariq Shihipar**: 好的。这不单单是因为 **Fable**，也是因为 **Opus 4.8** 以及未来的新模型。我们目前针对不同的模型采用了不同的系统提示词。

我们发现的一个规律是，以前我们对 **Claude** 进行了**过度约束（over-constraining）**。在早期类似 **Opus 4** 的模型时代，我们需要提供大量的示例（examples）。而现在，移去这些示例反而非常有用，因为模型自己发挥的创意，往往比我们给出的那些死板示例要好得多。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah. So it wasn't just Fable, it was Opus 4.8 as well. And going forward the future models, but we do sort of we have different system prompts for different models now. I think that some of the patterns we saw is that we were over constraining Claude, right? So I think the initial like maybe Opus 4ish kind of models wanted a lot of examples and removing examples was extremely helpful because it was just more creative than like the examples we gave it.

</details>

**主持人**: 这真的很有意思。因为我给别人的首要提示词技巧之一就是“给它例子”，例子是最简单的方法。如果现在不再需要了，这在一定程度上颠覆了我的提示词心智模型。

<details>
<summary>Original English</summary>

**Simon Willison**: That's really because one of the top prompting tips I give people is give it examples like examples are the easiest ways. If that's no longer true that kind of breaks my prompting model a little bit.

</details>

**Thariq Shihipar**: 我们也有相同的感受，得知这一点时我也很惊讶。现在，它更多地取决于你为 **Claude** 提供的**工具链的结构（shape of the tools）**以及你的系统提示词。

另一件我们做过的事情是，我们给它更多的上下文，并减少了“不要做这个”之类的负面约束。因为这类硬性指令很容易让 **Claude** 产生冲突，尤其是当它与用户随后的具体指令冲突时，会让模型感到极度困惑。因此，我们尽量减少强约束，提供更多上下文，并在整体上减少指令字数。这绝对是一门科学，需要大量的评估测试。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, same same here. I think I was surprised to hear that. I think that now it's more about like sort of the shape of what you give the tools to Claude and like yeah your system prompt and things like that. The other thing we did is we try and give it more context and fewer like "do not do this" you know because like I think that it's just a very strong impulse to Claude and especially if that conflicts with user instructions later on that can be like extremely confusing to Claude, right? Because you're like, "Oh, like I've got this skill that says this and the system prompt says this." Um, and so we try and like have fewer hard constraints and more just like sort of context and just like fewer instructions overall. Um, yeah, I think it's definitely a science. It took a bunch of like evals to build.

</details>

**Cat Wu**: 一般来说，当你给这些模型写指令时，应该时刻思考：“我给它的这条指令是否存在边缘情况？”当我们回头审阅 **Claude Code** 系统提示词中的所有指令时，我们发现很多表述在 90% 的情况下是正确的，但在剩下的 10% 的情况下并不适用。我们不想约束模型或者让它困惑，误以为自己必须总是这样做。

一个很好的例子是**代码验证（verification）**。大家都希望 **Claude** 去验证它写出来的代码。我们在提示词里曾有一条指令写着：“如果你做出了前端的修改，必须总是进行验证。”但在实际操作中，这其实有它的局限性。比如，如果它只是将一个字符串的文案做一下快速修改，而用户说“做一个快速修改并更新一下测试即可”，那你可能就不需要大费周章地去启动并验证前端。

因此，我们将提示词从生硬的“总是验证、验证、验证”，改为了“通常情况下，当你进行前端工作时，单纯请求后端端点可能无法完全体现真实的用户体验。所以当你对用户体验做出较大改动时，请本地运行 App 并实际验证它”。但实际上甚至连这一条指令也不够完美，因为什么是“大改动”？也许小改动也同样需要验证。

总之，当你向模型提供提示词时，你应该始终思考这些话可能会如何被一个善意的人所误解，从而优化提示词，使其达到 100% 的准确。但更神奇的是，你现在实际上是在**依赖模型自身的判断力**。这绝对需要达到 **Opus** 和 **Fable** 级别的模型智能。一年前的模型根本不具备这种判断力，无法自己决定是否去测试某项改动，这绝对令人着迷。但如果你是在为各种低端模型做适配，并试图让低成本模型去执行简单任务，这个逻辑就会面临挑战。

<details>
<summary>Original English</summary>

**Cat Wu**: I think in general when you're prompting these models, you should always think about like are there edge cases to the instruction that I'm giving it? And when we went back and we reviewed all the instructions in the Claude Code system prompt, we found a few cases where yes, this statement is like 90% true, but there's like a real 10% of cases where this is not true. And we didn't want to constrain the model or like confuse it into thinking, hey, it should always do this. Like one good example is verification. Everyone here wants Claude to verify its work. Um, and we had some instructions in the prompt that just said um, if you make a front-end change, always verify. But you know, there there is a limit to it. Like for example, if you if it's changing copy from one string to another string and the user tells says it says like just make a quick fix and update the test, maybe you don't want to verify. And so we we've also adjusted our wording from saying always verify verify verify verify to like hey most of the time when you're doing front-end work you can't always understand the full experience by hitting the backend endpoints. So like when you make like more changes to the user experience uh please run the app locally and actually in fact that instruction probably isn't even good because what is a large change like maybe it wants to change it test it for small changes too. Um, in general, whenever you give a prompt to the model, you should always think about the ways in which it could be misinterpreted by like a well-intentioned other user or human in order to better understand how the model might interpret it and in order to make sure that you can soften the prompt such that it is actually 100% accurate because you are giving this prompt to the model 100% of the time. But what's fascinating about that is you're relying on the model's judgment. And that's got to be a Opus Fable level thing. Like models a year ago did not have the levels of judgment necessary to decide if they were going to like test a change or not. That's absolutely fascinating. But that does break down if you're building for a wide range of models and trying to run the cheaper models for cheaper tasks and stuff.

</details>

**Thariq Shihipar**: 正是由于这个原因，我们现在针对**每个模型采用了不同的系统提示词**。只有我们最前沿的旗舰模型（frontier models）享受到了 80% 的提示词字数缩减，而老旧模型其实依然使用着完整的长系统提示词。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: We actually have a different system per model now because of this very reason. So, it's only our most frontier models that have this 80% token decrease and the older models actually still have the full system prompt.

</details>

**主持人**: 你们认为 **Fable** 和 **Opus** 是否已经足够聪明，能够理解 **Haiku** 具有较少的判断力和 Taste，从而能够在调用它时为它提供带有更详尽细节的提示词？

<details>
<summary>Original English</summary>

**Simon Willison**: Do you think Fable and Opus are smart enough to be able to prompt Haiku with more details because they understand that Haiku has less judgment, has less taste?

</details>

**Cat Wu**: 我们还没有做过系统的测试评估，所以目前没有硬性数据来证明这一点。但在小模型上确实存在挑战。有时我们发现，在面对一个难题时，大模型反而比小模型具有更高的 **Token 效率**。因此，建立这种直觉很有必要，因为有时候你其实在任何时候都更需要最前沿的旗舰级智能。

<details>
<summary>Original English</summary>

**Cat Wu**: We haven't been able to eval, but we don't have any hard data to show it. I think there's a tough thing with um smaller models sometimes because like uh you know we saw this with um just like sometimes the the larger models can be more token efficient on a hard problem than the smaller models. And so uh you know there's like a little bit of that uh intuition to build about like you know sometimes you really just want frontier intelligence almost all the time you know um but it's uh yeah like the paralle curve shifts you know and so it's hard to find. Yeah.

</details>

**主持人**: 这非常有趣。在一年前，我绝对不会信任由模型写出的提示词。但到了今天，优秀的高阶模型在编写提示词方面已经表现得非常出色了。我现在很多提示词都是由模型代写的，这听起来有些荒谬，但效果真的极佳。这也让我开始接受并思考**子智能体（sub-agents）**的模式——由一个 **Claude** 模型为另一个 **Claude** 模型配置提示词，让它清楚知道自己应该去做什么。

<details>
<summary>Original English</summary>

**Simon Willison**: I mean that's something I found fascinating. I feel like a year ago I did not trust a model to write a prompt. Like today the good models are very good at prompting. Like a lot of my prompts are written by models which feels absurd but it actually works really well. And something that helped me come to terms with that was thinking about sub agents which is entirely about a Claude model setting up a prompt for another Claude model so that it knows what to go and do.

**Thariq Shihipar**: 是的，我认为工作流（workflows）就是一个极佳的例子。因为这不仅仅是 **Claude** 去给单个子智能体写提示词，而是去给一系列子智能体的**编排与协同（orchestration）**编写提示词，而且它们之中的每一个都会获得非常详尽的指令。这基本上比单纯产生一个子智能体高出了一个层级，模型在这方面表现得非常出色。

我也一直在我的个人机器上使用这个功能。比如我会提供 **Gemini API**，让它去自动生成图片。它在编写提示词方面比我勤快得多，效率高得多。所以真的是“子子孙孙无穷尽也”（Claude prompting Claude all the way down）。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, I think workflows are actually a really good example of this because it's like Claude not just prompting a single sub agent, but it's like prompting like the orchestration of many sub agents and each one of them gets like, you know, a very detailed prompt. So, it's like almost like a level above like, you know, just spawning a sub agent. Um, so yeah, it's quite good at that. Yeah, I've also been using on my personal machine like giving it the Gemini API and being like, oh, like here, generate images. And it's so good at it's way less lazy than I am at prompting an image model, you know. So, um yeah, it's just Claude prompting Claude all the way down. Yeah,

</details>

**Cat Wu**: 我记得，**Claude** 甚至把我们工作流工具的提示词也给写了。

<details>
<summary>Original English</summary>

**Cat Wu**: I think Claude also wrote the prompt for the workflow tool.

</details>

**主持人**: 至于工作流工具的提示词，我已经读过它了，写得非常好。不过这也正是我对 **Anthropic** 感到有些沮丧的地方——你们会在专门的网页上公开 **Claude** 的普通提示词，但你们没有公布工具（tool）提示词和 **Claude Code** 的提示词。我甚至必须在本地通过配置代理拦截，才能一窥它们的真容。我非常希望你们能主动公开这些 **Claude Code** 的提示词，因为提示词本身就是最棒的文档。它告诉我们这个工具能做什么，以及它是如何工作的。

<details>
<summary>Original English</summary>

**Simon Willison**: For the workflow tool, I've read that prompt. It's a good prompt. I mean, that's actually um a frustration I have with Anthropic generally is you publish the prompts for Claude. There's a web page with them on, but you don't include the tool prompts and the Claude code prompts. I still have to run a proxy to intercept them. I would love it if the Claude code prompts were deliberately published because they're the documentation. They're how you know what the tool can do and how it works.

</details>

**Thariq Shihipar**: 我记下了这个需求。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: I'll write down that feature request.

</details>

**主持人**: 太感谢了。

<details>
<summary>Original English</summary>

**Simon Willison**: Please do.

</details>

**Cat Wu**: 我会让我们的 **Claude Tag** 自动去完成这个发布任务。

<details>
<summary>Original English</summary>

**Cat Wu**: I'll have Claude tag do it.

</details>

**主持人**: 还有就是提示词的差异比对（diffs）。我时不时会去比对新旧版本提示词的差异，这是我学习新模型能力的重要途径。我非常期待能看到这次 80% 瘦身之后的提示词长什么样。

<details>
<summary>Original English</summary>

**Simon Willison**: And also the diffs like every now and then I'll do I'll diff the older and the newer prompt and that's how I learn the capabilities of the new model. I'm really looking forward to seeing what this 80% reduction actually looks like.

</details>

**Thariq Shihipar**: 好的，这包在我身上。我随后会发一篇长文详细解释这件事。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, this is on me. I have to make a post about this in detail. Yeah.

</details>

---

### 工具引入的门槛与设计哲学

**主持人**: 让我们聊聊工具。**Claude Code** 在本质上就是一个庞大的**工具箱（bag of tools）**。那么，你们引入一个新工具的门槛是什么？你们如何决定何时值得在工具层面投入额外的工程力量？

<details>
<summary>Original English</summary>

**Simon Willison**: So, what's your bar? Let's talk about tools a little bit. Claude code is basically a just bag of to a big bag of tools. What's your bar for introducing a new tool? How do you decide when it's worth doing that additional engineering at that level?

</details>

**Thariq Shihipar**: Cat，你要来回答这个问题吗？因为你引入了我们最好用的工具之一。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Do you want to take it? Because you introduced one of the best tools we have.

</details>

**Cat Wu**: 好的。其实当我在我的职业生涯巅峰期引入了“向用户提问（ask user question）”这一工具时，我发现这其实非常难。因为对于像“提问”这样的工具，它是 **Claude** 主动向你发起询问，所以在测试评估上很棘手，而且很多时候这关乎用户的个人偏好。特别是在早期阶段，我们几乎没有现在的各种评估体系，只能完全依赖内部“吃狗粮”的体感。

不过总体而言，我们目前的趋势是**减少工具的数量（fewer tools）**。我们最近引入的工具似乎是任务工具（task tool），我们试图为 **Claude** 提供更具通用性的工具版本来解决问题。

<details>
<summary>Original English</summary>

**Cat Wu**: Yeah. I mean, yeah, it's like my career peaked when I introduced the ask user question tool. I think so. Um, it it's really hard. I think especially for some tools like ask user question is Claude's tool to ask you and so it's hard to eval and sometimes it's more of a user preference thing. So like especially back then we had fewer evals. It was very dog fooding based. Um, but yeah I mean I think overall we've been trying to trend towards fewer tools. I think the last set of tools we introduced were like the task tool I think um and try and give Claude more general versions to do this. Um

</details>

**主持人**: 其中最有趣的工具之一是文件编辑工具（file editing tool）。为了编辑文件，你既可以直接给模型提供一个专门的修改工具，也可以直接让它去使用系统的 `sed`、`grep` 或其他命令行工具。你们的文件编辑工具目前演进到了什么状态？

<details>
<summary>Original English</summary>

**Simon Willison**: Right, one of the most interesting tools is the file editing tool which but you can have file editing as a tool or you can tell teach it tell it to use said and grep and do things that way. What's the latest evolution of your file editing tool?

</details>

**Cat Wu**: 我们目前仍然保留着它，但比如我们移除了我们定制的 `grep` 和其他文件搜索和 Glob 匹配工具，直接转而让它使用原生的 `bash`。

这也呼应了我之前在演讲中提到的观点：大模型更像是一门**生物学**，而非物理学。在工具设计上确实很难，甚至有些艺术和生物学的色彩，不知道 Thariq 是否同意？

<details>
<summary>Original English</summary>

**Cat Wu**: Uh I think we still have one but like for example we removed our grep and uh other search tools. glob tools for just like native uh like bash and so uh yeah we still have one I I think this is kind of like I said in my uh talk earlier that the models are kind of like more of a biology than a physics you know and so like you know it's hard to like especially tool design I think is quite hard and I'm not sure if actually if Cat disagrees and is like oh like we should no there's like a science to the ebal of it but I'm sort of like yeah tool design is more of an art maybe or like a biology. Yeah.

</details>

**Thariq Shihipar**: 我在很大程度上表示赞同。随着我们不断引入更多工具，我们努力保持其**低基数性（low cardinality）**，确保我们添加的每一个工具与现有工具相比都具有完全独立、清晰的功能，只有这样 **Claude** 才能非常容易地去决定在什么时候调用哪一个工具。

至于我们设计文件编辑工具的初衷，是因为我们需要在 UI 上进行渲染。因为以前我们需要在终端上向用户展示：“大模型即将对文件做出以下修改，你是否批准这次改动？”为了让程序能够 100% 确定地捕捉到 **Claude** 即将对文件做出的修改并渲染出精美的提示界面，我们需要一个专属的文件编辑工具。对于刚开始上手的新用户来说，他们非常喜欢这种视觉交互体验，所以我们保留了它。

但是，对于我们大部分开启了自动模式（auto mode）甚至“YOLO 模式”的资深用户而言，这其实无关紧要了，我们甚至可以直接拿掉这个特定工具，直接让模型去运行 Shell 命令，它也同样能完成得很好。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: I think I largely agree, but that I think in general as we introduce more tools, we try to keep the cardinality pretty low and make sure that every tool we add has a distinct function from every other tool so that Claude can very easily distinguish when to call each. For file edit, actually, the reason that we have file edit is because we can render it because back in the day we used to show or I guess we still do. Um, so we show people when Claude makes a file change and there's this nice like dedicated UI that just says uh do you approve this edit to this file? And the reason that we had a dedicated file edit tool was so that we could deterministically know that Claude was making a file so we could show people this nice UI. And for a lot of the new users who are onboarding, I think they still really like this experience. So, we've kept it around. But for a lot of us who are on auto mode right now, or hopefully you're not on YOLO mode. But anyway, for a lot of us right now, I don't think actually it matters and we probably could just remove file edit and we'll be totally fine.

</details>

---

### 安全沙箱与自动模式防护

**主持人**: 让我们聊聊自动模式，以及安全和网络防护。我非常清楚提示词注入的风险，如果别人通过我让 **Claude Code** 阅读的网页或代码去控制了我的智能体，可能会发生非常可怕的事情。但我目前仍然在 YOLO 模式下使用它，并为此感到有些愧疚。在 **Anthropic** 内部，对于如何安全地运行 **Claude Code** 有什么建议？

<details>
<summary>Original English</summary>

**Simon Willison**: So, let's talk about auto mode or let's talk about safety and security in general. Like I am deeply aware of the risks of prompt injection and there so much bad things can happen if somebody else tells my Claude Code what to do. I still mostly run Claude Code in YOLO mode and feel incredibly guilty about it. What's the advice within Anthropic for safely running Claude Code? Like what do you tell people to do?

</details>

**Thariq Shihipar**: 你为什么不用自动模式（auto mode）呢？

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Why not auto mode?

</details>

**主持人**: 我现在正开始使用它，但我对它了解不够，无法确定它到底有多安全。但大体上，从三周前开始，我已经开始默认使用自动模式了。

<details>
<summary>Original English</summary>

**Simon Willison**: I am starting to use auto mode and I don't understand it enough to get how safe it is. But yeah, that's as of maybe three weeks ago, I'm defaulting to auto mode.

</details>

**Thariq Shihipar**: 好的。在 **Anthropic** 内部，几乎每个人都在使用自动模式。这是在保证安全的同时，让 **Claude Code** 运行长时间复杂任务的最佳方式。我们进行了极大量的内部红蓝对抗（bashing），我们有数千个安全评估用例，并且雇佣了许多外部红队人员在对抗环境中试图欺骗 **Claude Code** 去执行危险操作，我们修复了他们发现的每一个漏洞。我们将在接下来的几周内公开一些我们的评估结果，供大家评估和参考。

当然，没有任何工具敢声称自己是 100% 绝对安全的。但针对我们最关心的核心风险（如提示词注入、数据外泄），自动模式防线出错的概率，已经远远低于人类代码评审员的失误率了。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Okay, so broadly within Anthropic, almost every single person uses auto mode. It is the best way to do long-running work in Claude Code while being safe. We've done extensive bashing. We have thousands of evals. We've commissioned many red teamers to create adversarial environments in order to trick Claude Code into doing bad actions. And we've mitigated every single issue that they found. And so we're going to publish some evals in the coming weeks, but we've pretty much mitigated every attack. We'll share the evals for it so folks can assess, but we've been extremely diligent about identifying all the ways in which Claude might mess up and then updating auto mode to counter it. It doesn't catch 100% of things. I don't think any—yeah, that would be way too strong of a claim. But for the main categories of risks that we're concerned about like prompt injection, data exfiltration, the risks are far lower than the average human reviewer.

</details>

**Cat Wu**: 另外，关于自动模式的工作原理，建立一个清晰的心智模型也很有帮助。当 **Claude Code** 发起一次 `bash` 命令行调用时，会有一个专门的 **Sonnet 分类器** 去评判该工具的性质、以及对话的上下文和你的当前指令。

因此，有些权限是直接依赖于你的具体请求的。你显然不想在任何时候都默认放开 `git push` 权限，但如果你在提示词中明确说明“将此推送到 GitHub”，分类器就会放行；反之，如果你的上下文里写着“不要推送”，它就会予以拦截。

对于我而言，我经常会遇到类似的情况——**Claude** 尝试去做一些非常具有建设性和主动性的事情，但自动模式基于安全策略认为不应该执行，并将其弹回给用户进行确认。所以它在结合提示词动态研判权限方面表现得非常出色，这对于安全而言至关重要。

另外，它与我们的**沙箱基础设施（sandboxing infrastructure）**结合得非常紧密。沙箱安全有极其多的边缘情况，很难通过规则来一刀切地锁定。但既然有了沙箱，当大模型尝试发起网络请求等逃逸沙箱的操作时，自动模式就会对该请求进行分析，评估其合理性，并据此决定是否予以放行。

<details>
<summary>Original English</summary>

**Cat Wu**: So, and oh yeah, a little bit on how auto mode works. I think it's useful to build this mental model. So, whenever Claude is doing a turn, uh there's a or a bash call, uh there's a Sonnet classifier that is judging the tool and also the context of the conversation, your instruction, right? And so there are some things around like uh permissions which are dependent on your request right so you don't want to give git push like permissions all the time but if you say hey push this to github you want it to do it right and so auto mode will or if you say don't push you want it to deny it right and so auto mode will do that particular thing happens to me a lot where it's like oh like auto mode like Claude tried to do this because it's very helpful and proactive and auto mode saw like oh like you know don't do this and it like surfaced it. So it's good at like the dynamic permissions that you yourself give inside of the prompt which I think is really important. Um it also works well with our sandboxing infrastructure because like sandboxing is one of those things where there are so many different edge cases. Uh and it's hard for like us to deterministically follow them. But if you we have a sandbox and something needs to escape the sandbox like a you know a network request auto mode can then look at that request and be like oh hey does this like you know does this make sense right and just allow that in.

</details>

**主持人**: 我之前居然不知道自动模式也直接参与了网络沙箱的管理。

<details>
<summary>Original English</summary>

**Simon Willison**: So I hadn't realized auto mode is interacting with the networking sandbox as well.

</details>

**Cat Wu**: 是的，它也是沙箱的组成部分，它会介入原本需要用户手动介入的每一个权限确认。

<details>
<summary>Original English</summary>

**Cat Wu**: Yeah exactly. So it's also part of sandbox. Um yeah it interacts with any permission prompt that the user would otherwise see.

</details>

**主持人**: 自动模式诞生多久了？我感觉我作为普通用户能接触到它，也就是最近几个月的事情。

<details>
<summary>Original English</summary>

**Simon Willison**: And how old is auto mode? Like I feel like as a feature that I had access to, it's only a couple of months old, right?

</details>

**Cat Wu**: 我们在 **Anthropic** 内部从今年一月份起就已经开始使用它了，所以我们对它进行了很长一段时间的加固。**Anthropic** 高度重视安全和防御。我们与模型对齐（alignment）和安全防护团队紧密合作，才在内部逐步推开、建立更强大的评估集，并最终将其分享给全世界。

<details>
<summary>Original English</summary>

**Cat Wu**: We've been using it within Anthropic since January. So, we've been hardening it for quite a while. And it's obviously Anthropic is extremely focused on safety and security. And so, we've been working broadly across our um alignment and safeguards teams in order to enable the rollout internally, build out these eval even more robust before sharing it out with the world.

</details>

**主持人**: 我对自动模式的主要困惑在于我对它的底层机制不够了解。对于任何关乎我系统安全的工具，我需要尽可能多地了解它是如何工作的、能防范什么、不能防范什么，只有这样我才能决定给它多少信任。

<details>
<summary>Original English</summary>

**Simon Willison**: I think my only my main problem with auto mode is I don't understand it deeply enough. Like for anything that's looking after my security, I want to know as much as I can about how it works and what it protects me against and what it doesn't so I can decide like how much I can trust it.

</details>

**Cat Wu**: 没错，这也是 Thariq 正在撰写相关技术博客的原因。另外，这也是为什么 **Claude Tag** 表现如此出色的基础——因为 **Claude Tag** 直接基于自动模式运行。我听到很多关于团队是应该自己构建 Slack 机器人，还是直接购买成熟方案的讨论。我想警告大家：你可能不应该尝试自己去写一个 AI 协作机器人，因为这里的安全攻击向量（attack vectors）实在太多了。

举个例子，如果你们有一个供用户发帖反馈的公共渠道，而你的机器人会去读取这个渠道中的输入，它就随时面临被注入的风险。而我们在自动模式中投入了巨大的精力，建立了针对安全防御的多重防线（Swiss cheese defense），包括在强化学习（RL）层面的安全对齐。这正是 **Claude Tag** 能够平稳落地、无缝适配团队权限并防范 Slack 渠道中提示词注入的根本保障。

<details>
<summary>Original English</summary>

**Cat Wu**: I think yeah Thariq was working on a post about this. So um a little bit just a little bit more about auto mode. This is also the reason Claude Tag is so so good, right? Because Claude Tag uses auto mode and like you can imagine that like one of like I've heard a lot of like build versus buy questions on a Slackbot. I'm like please you probably shouldn't build your own AI Slackbot, you know, like there's so many attack vectors, you know what I mean? And like um like you have a feedback channel that like you know users can post feedback into and now your bot is reading it, right? And so I think that like this the work we've put in with auto mode and you know we have a general Swiss cheese defense of like security, right? We also like yeah you know like RL against this stuff and things like that. Um I think this is really what makes Claude Tag work. It like just works seamlessly with your permissions and yeah like you know we you don't want to be prompt injected in your Slack. Yeah.

</details>

**主持人**: 除了自动模式，你们在安全管线上还有什么其他后续规划吗？

<details>
<summary>Original English</summary>

**Simon Willison**: Do you have any are there any more security things in the pipeline beyond that go beyond auto mode?

</details>

**Cat Wu**: 目前我们的防御已经非常稳固了。比如在 **Claude Tag** 中，你可以为 **Claude** 配置专属的**凭证管理（credentials）**，让它作为一个独立的数字身份实体开展工作，而不是完全代表你个人。这使得审计（audit）和督导 **Claude** 的行为变得更加容易。

<details>
<summary>Original English</summary>

**Cat Wu**: Um I think we're very secure like with Claude Tag you can provision your own like sort of credentials for Claude so it doesn't need to act on your behalf. You can have like Claude as an identity and that also makes it easier to audit and inspect what Claude is doing.

</details>

**主持人**: 因为 **Claude Tag** 会受到任何能在 Slack 频道里发言的人的潜在影响，它的受众和潜在指令来源要广泛得多。

<details>
<summary>Original English</summary>

**Simon Willison**: Well I guess cuz Claude Tag is influenced by anyone who can talk to it. So it's got a much wider pool of people who are telling it what to do.

</details>

**Cat Wu**: 确实如此。当然，在模型端我们也通过 **Fable** 的迭代注入了更强的安全防御，这也是我们的安全和对齐研究工作的直接体现。这也是 **Anthropic** 作为一家以“AI 安全”为核心理念的公司的价值变现时刻——我们需要 **Claude** 能够在长跨度任务中持续保持对齐，而自动模式必须做到近乎无懈可击，这一切才能运转起来。

此外，针对远程控制，我们推出了**受信任设备（trusted devices）**机制；同时在远程开发环境中支持**凭证代理注入（credential injection）**。这意味着，如果你想让 **Claude Code** 去访问 Datadog，但又不想让它直接读取你的 Datadog 密钥，你可以配置我们的凭证管理系统，在 **Claude** 发起请求时在网关代理层动态填入密钥，而模型本身是无法接触到密钥明文的。

<details>
<summary>Original English</summary>

**Cat Wu**: That's right. Yeah. Yeah. And of course we have probes as well like with like Fable um and that's also like a downstream effect of our safety and research work. And I think this is the moment where you sort of see AI like Anthropic being an AI safety company really paying off when you like you know we really want Claude to be able to run in an aligned way over long periods of time and like yeah automode has to be basically flawless for this to work right and it's sort of like all downstream of our being an AI safety company. We also launch trusted devices for the remote control users out here who want to be safer. Um, and for all of our remote environments, we support uh credential injection. So if you want like Claude Code to be able to access Datadog but you don't want Claude Code itself to hold the Datadog credential you can set up um our identity credential management system so that the Datadog credentials are only usable by the agent but not accessible by the agent. So we insert it on the fly when the agent tries to make a Datadog request.

</details>

**主持人**: 这就是典型的**代理令牌劫持与替换机制（token proxying trick）**。网关发现请求发送至 datadog.com 时，自动在请求头中将临时占位符替换为真实密钥。我非常喜欢这个模式，并在很多地方看到了它的应用，这显然是非常正确的安全实践。

<details>
<summary>Original English</summary>

**Simon Willison**: This is that token the proxying trick, right? Where the proxy knows anytime somebody calls this an API. Dog.com address with a token, replace the token with the real thing. I love that pattern. I'm seeing that in a whole bunch of places. It feels so obviously right to me.

</details>

---

### 技术失落感与工程师的雄心

**主持人**: 让我们聊聊人性的层面。你在今天早上的主题演讲中也提到了这一点，但是现在很多工程师都在经历一种“失落感”，因为他们原本认为自己扮演的编写软件的角色，正在被模型逐步蚕食。你们怎么看待这一点？过去的一年半里，AI 编程工具是如何重构你们对于自身手艺和自身所能贡献的价值的理解的？

<details>
<summary>Original English</summary>

**Simon Willison**: Let's talk a little bit about the human element. And you touched on this in the keynote this morning, but a lot of people are feeling a sense of loss now that so much of what they considered to be their role in building software is being subsumed by the models. Um how do you think about that? Like um how firstly how has the past year and a half changed the way you think about your own craft and the value that you add?

</details>

**Thariq Shihipar**: 对我来说，Cat 以及团队中的其他同事（如 Ken 和 Boris）一直在扮演我的“警钟”。他们总是提醒我：**你必须变得更加雄心勃勃（be more ambitious）**。他们会说：“我们的业务增长得如此之快，我们必须始终站在最前沿，做出我们所能做出的最棒的成果。”因此，当我发现自己在某项工作上进展缓慢时，我会自我审视：“我能做得更快吗？我的志向能更远大一些吗？”

关于你提到的那种“技术失落感”，我觉得它非常真实。如果你在有了大模型之后，依然固守着在 LLM 出现之前你习以为常的那种工作内容，只去做那些现在只要写一行提示词就能自动完成的平庸工作，那你确实会感到非常沮丧和难过。而消除这种失落感的唯一解药，就是**将你的志向和目标调得更高**。

我非常喜欢 Jared 的例子。他曾在奥克兰的公寓里闭门不出长达一年，独自用 Zig 语言手写了全部的代码。他当时沉浸在代码的乐趣中；而最近我看到他正在用 Rust 重新改写整个项目，他依然乐在其中。这种重写更大、更复杂项目的野心，正是我们用来抵消失落感、找到手艺乐趣的途径。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, I think for me and I think Cat is always such a good reminder. Ken and Boris are such good reminders of like you have to be more ambitious. They're always like, you know, you have to like like, you know, we're growing so fast, we have to be on the edge, we have to do like the best work we can. Um, I think that that's kind of like a constant reminder for me where I'm like anytime I'm like kind of like slow on something. I'm like, okay, can I do it faster? Can I be more ambitious here? Um, I think the like point on and like oftentimes the answer is Claude because Claude is getting better as you go. So, I'm like, "Oh, the last time I tried this, it was with the previous model or something." Um, I think with your point on loss, I think this is real. And I do feel that like if you're only trying to do the same work you were doing before LLMs and now it's like a prompt, it is like I think kind of a sad feeling. And I think the way you offset that is by being more ambitious, right? And you're like, you know, like I think Jared is such a good example where he's like hand wrote all of the Zig code in his Oakland apartment in like a year barely left his house, you know, and then and he had so much fun doing that and now I see him like rewrite all of Bon into Rust and he's having so much fun doing that, right? And it's like so much more ambitious and that's how how like he sort of like offsets that.

</details>

**主持人**: 这就是改变你的抱负，去改变你所做的事情。因为以前的工作现在变得极其容易，我们可以转而挑战更宏伟的目标。

<details>
<summary>Original English</summary>

**Simon Willison**: It's changing your ambition. It's changing what you do because what you did before is a lot easier in quotes but now we can take on these bigger challenges.

</details>

**Thariq Shihipar**: 没错。我想每个人心里其实都有一份“以前想做但没有能力或时间做成”的愿望清单。现在既然有了工具，就让我们放手去做吧。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, I think there's just like on average everyone has things they wish they did you know what I mean and that they were better at and I think now it's Let's let's do it, you know, like let's...

</details>

**主持人**: Cat，从产品管理的角度来看，这呈现出怎样的状态？

<details>
<summary>Original English</summary>

**Simon Willison**: And Cat, what does that look like from a sort of product management perspective?

</details>

**Cat Wu**: 我觉得产品经理的职能几乎每个月都在发生变化。目前，我们团队中的产品经理在技能上都是“工程师、设计师和产品经理”的混合体。事实上，我们团队的大部分产品经理以前也都是全职的软件工程师。

对我们来说，这意味着我们要随时去填补团队中的任何空缺。如果我们有了一个很好的想法，但还没有工程师去动手构建它，那我们就会直接去把它写出来，做成一个 Demo 并激发大家把它推向生产环境的灵感。如果我们发现设计有些粗糙，那我们就直接基于类似页面做出第一版设计，然后拉细节控的同事过来帮忙微调。

或者，如果由于我们产品的受众规模越来越大，大家需要清楚了解 **Claude Code** 和 **Claude Tag** 接下来会推出什么功能，我们就会直接将发布日历和周会更新全盘自动化，这样就不会打扰到大家的日常工作。因此，产品经理在当下的工作，就是去看一个好点子到最终交付给客户之间，还有什么缺口和阻力，然后尽可能通过自动化去消灭这些阻力。

<details>
<summary>Original English</summary>

**Cat Wu**: I feel like the product role just changes every single month and it's very much just identifying, okay, what are um like all the PMs on our team are like this like mix of engineer, designer, PM. Um most of the engineers on our team actually used to be uh full-time engineers in the past. And so for us it really means like plugging in whenever there's any kind of gap. So if it's like okay we have this idea and we didn't inspire any engineer to go build it then like we should just build it and then put it into a notebook and inspire people to take this to production. Or if the designs look a little off, well let's let's take a page that's similar and do a first pass design and uh tag in tag in someone who's very detail oriented to like fill in the gaps. Or if we notice that like hey now now our team uh and our product adoption is a bit bigger within the company and more people need to know what's coming down the pipe for Claude Code Claude Tag and co-work uh what we do then is like okay let let us like automate figuring out our whole launch calendar let's automate getting those status updates asynchronously so we're not bugging people and then let's figure out okay these are our three internal announce channels and make sure that our updates there are fully detailed and to the point. And so for us, it's very much just understanding what is the gap right now between a great idea and getting something to our customers and then how do we automate it as much as possible.

</details>

**主持人**: 这听起来像是产品经理永远有忙不完的事情。我此前工作过的每家公司，都会有积压着一千多个点子却苦于没有资源去做的 Backlog 任务，这也是体现产品经理价值的地方。

<details>
<summary>Original English</summary>

**Simon Willison**: It sounds to me like with product management, there's always more to do, right? It's I feel like one of the things that makes me feel good is I've never worked at a company that didn't have a backlog of a thousand things they wanted to do and didn't have the resources to take on.

</details>

---

### 令人惊叹的视频剪辑与户外攀岩智能体

**主持人**: 能聊聊大模型曾经让你们感到最震惊或惊艳的时刻吗？它做出了什么你们之前认为模型根本无法完成的事情？

<details>
<summary>Original English</summary>

**Simon Willison**: Um, so what's a moment when Claude has surprised you? Like when when when the model has done something that genuinely surprised you that you didn't think it would be able to do.

</details>

**Thariq Shihipar**: 虽然我之前发过很多关于 **Claude 视频剪辑**的内容，但最近我参加了 ACM Agentic 研讨会并做了演讲。随后我问主办方：“嘿，你们剪好我的演讲视频了吗？我想把它发给我们的公关团队。”他们说：“哦，这需要很长的时间。”我说：“好吧，那你能把所有的生素材（原始音频、PPT 画面和现场视频）直接发给我吗？”他们说：“那祝你好运。”

接着我直接把这些素材全部打包交给了 **Claude**。我同时也把我的 HTML 格式的 PPT 发了过去，对它说：“嘿，你能帮我把这些剪在一起吗？”

它做出来的效果简直是惊人的，我可以直接把它发布出去。它不仅转录了全部的音频，还发现现场拍摄的 PPT 视频画面有些反光和重影，它居然在提示词里说：“我不应该直接用视频里的 PPT 画面。我将自动分析你的音频，识别你当前讲到了哪一页 PPT，并直接用你发给我的原版 HTML PPT 去渲染切片并覆盖画面。”

此外，现场视频中的我是在讲台上不断走动的。**Claude** 自动在视频画面中对我进行了动态裁剪和**人物追踪（capturing & tracking）**，将我、演讲 PPT 以及转录字幕完美融合在了一起。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, I mean I've posted a lot about uh Claude video editing, but like like most recently I I gave a talk at the ACM Agentic conference and uh I was like, "Hey guys, do you have the edited video? I'd love to post it and share with my coms team." And they're like, "Oh, it's taking so long." And I'm like, "Okay, could you send me the raw files?" So they send me the video of me talking on stage, the video of the deck and the audio file, and they're like, "Good luck." And and so I like give this to Claude. I give it my HTML deck as well, and I'm like, "Hey, can you just like edit this together, you know?" And um what it does is like honestly incredible. Like I I'm ready to ship it. Like so it transcribes the entire video. Um it notices that sometimes the video of my deck is a little bit weird. There's like a popup of like an auto update in the middle and it's like, "Oh, I probably shouldn't use the video of your deck. Actually, what I'm going to do is I'm going to slice up and figure out which um slide you're on and instead use your h the HTML source, right?" And so, it's displaying the HTML source. Then, it's got a video of me, but you know, like I'm only taking up a small part of the stage. And so, it's cropping dynamically where I am on the stage. Um, and like I'm I'm pacing. So, it's like tracking me as I'm pacing. And I've got me, the deck, and then like it's transcribing what I'm saying.

</details>

**主持人**: 这用的是 **Fable** 吗？

<details>
<summary>Original English</summary>

**Simon Willison**: This was Fable, right?

</details>

**Thariq Shihipar**: 没错，这用的是 **Fable**。这是一个单次生成（oneshot）的任务。随后我还让它帮我加上了一些非常有趣的转场特效和图形，我完全被它的表现给惊艳到了。它在后台自己调用了 `ffmpeg` 和 `remotion` 等工具去完成这一切。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: This Fable. Yeah. Yeah. Absolutely. Yeah. Um and it's just like like, you know, it was a good prompt, but it was a oneshot prompt. And and then I asked it to like add some like interesting animations and graphics, and it I was just like blown away kind of, you know, and it just like does all this stuff. It does ffmpeg, it does remotion, it does.

</details>

**主持人**: 那我必须追问一句，目前它还有什么**做不到（can't do）**的地方，以至于让你们仍然感到失望？你们还在等待 **Claude Fable 6** 去帮你们解决什么痛点？

<details>
<summary>Original English</summary>

**Simon Willison**: So I have to ask the follow-up. What can't it do? What are the things where you're still disappointed? You're waiting for Claude Fable 6 to to figure out for you.

</details>

**Thariq Shihipar**: 我非常渴望模型能够具备更好的**设计与体验品味（UX taste）**。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: I wanted to have better design and UX taste.

</details>

**主持人**: 没错（笑声）。

<details>
<summary>Original English</summary>

**Simon Willison**: Uh-huh. [laughter]

</details>

**Thariq Shihipar**: 我觉得如果你写出一份非常详尽的规格说明书，描述你希望页面如何交互，它通常都能准确实现。但最终交付出来的页面，往往边距（padding）不太对，或者整体感觉不够精致和令人愉悦。它虽然在拼命遵循目前应用设计的最佳实践，但在前沿的 AI 原生应用设计中，有很多全新的交互模式仍然需要我们人类去从零开始摸索和设计。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Like I feel like it's now at the point where if I give it if I write out a prompt with a detailed spec of how I want a feature to behave, it will usually behave that way. But, you know, the the paddings might be off or like the the interface is it's just not delightful yet. Um, I think it kind of leans on like existing best practices for apps for how apps are designed, but I feel like for Frontier AI products, there's so many new interaction experiences that we still have to have yet to design.

</details>

**主持人**: 这就是所谓的“大模型美学（Opus aesthetic）”，你打眼一看就知道“是的，这页面肯定是由 Opus 设计的”。我们确实需要跨越这个阶段。

<details>
<summary>Original English</summary>

**Simon Willison**: There's an Opus aesthetic. You can look at something and go, "Yeah, that was designed by Opus." It'd be good if we could move beyond that.

</details>

**Thariq Shihipar**: 没错，我很期待未来的模型能真正成为我们**交互设计上的思考伙伴**。此外，我也期待它能更深刻地融入真实世界，例如去帮我们做科研实验等复杂任务。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah. Yeah. It like I I'm very excited for future models to hopefully be like interaction design thought partners. Hm. Uh what can't it do? Um I I think I would love to see it, you know, interact more with the real world like okay like can it do this like you know can it solve science right? Like can it like orchestrate you know the experiments and there's some amount of coding that goes into that but there's also this like other taste of uh you know like the broader world that it needs. So

</details>

**主持人**: **Claude Science** 是几天前刚发布的新产品吧？

<details>
<summary>Original English</summary>

**Simon Willison**: Claude Science is a new product that just came out a few days ago right?

</details>

**Thariq Shihipar**: 是的，不过这一块不是我们在做，而是我们的兄弟团队负责。大家一定要去尝试一下。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah but I have no context on it. It's our partner team. Gotcha. Try it out, though.

</details>

---

### 企业文化与最荒谬的创意尝试

**主持人**: 我还有最后两个收尾问题。第一，你们认为 **Anthropic** 的企业文化中，有哪些独特的特质帮助你们在使用这些工具时实现了极其高效的产出，是其他公司应该去学习和借鉴的？

<details>
<summary>Original English</summary>

**Simon Willison**: Um, so we've got I've got a couple of closing questions. Um, which parts of Anthropic's company culture do you think uniquely help Anthropic be productive with these tools that other companies should steal? What are the cultural hacks that people should be should be adopting from you?

</details>

**Cat Wu**: 我先分享一个。**Claude Tag** 在公司内部的所有渠道**默认公开（public channels）**时，其工作效果是最好的。因为这意味着它能够自动读取和检索几乎所有公开频道的讨论上下文，从而以极高的准确率给出答案。这非常依赖于扁平、公开的沟通文化。

<details>
<summary>Original English</summary>

**Cat Wu**: I'll share one and then you go. Um, I'll share one for Claude Tag. So Claude Tag works best when you have it in a public channel and when most of your channels are public. Claude Tag is able to search across all public channels to get as much context as possible to give you the highest accuracy answer. And it's only able to do this if it has access to everything.

</details>

**Thariq Shihipar**: 我在今天早上的主题演讲里也提到过，但我仍然想强调这一点。我们创始人经常对我们说：“**千万不要在心里对自己进行妥协（We don't negotiate against ourselves）**。”

这极其关键。因为很多时候，你会在脑海中自我拉扯、权衡各种利弊，并最终说服自己不要去做某件极其具有雄心壮志的大事。我们的态度是：让我们直接去动手做，去验证这到底是一个真实存在的冲突和障碍，还是仅仅只是听起来像一个障碍。要让真实的阻力呈现在你面前，在此之前，请保持你最大的野心。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah, I mentioned this in my keynote, but I I think I it's so important to me. I want to reemphasize like I I think the co-founders say like we don't negotiate against ourselves, you know, and I think this is really important where you're like you can imagine trade-offs in your head and talk yourself out of doing something ambitious, you know? Um or you can just try and do the ambitious thing. And I think that like we're just so often being like, okay, what if we just did it? Like what if like, you know, like is this a real trade-off or not, right? Or like and if so, like why? Like where's the proof that it's a real trade-off and not just like it sounds reasonable, right? And so I think just yeah like you know make the trade-offs show themselves to you. Be as ambitious as you can.

</details>

**主持人**: 这很有意思。因为我有 25 年的传统软件开发经验，它给我的直觉反应往往是“不，这个不行，那是个冲突，任何事情都有极高昂的迭代成本”。而现在，我们必须重构我们所有的直觉。

最后一个问题，你们用 **Claude** 构建过的最不可思议、甚至听起来有些“荒谬”的功能或应用是什么？纯粹只是因为你们有能力去把它构建出来。

<details>
<summary>Original English</summary>

**Simon Willison**: That's so because that goes against I've got 25 years of software experience that says the default answer should be no. Everything is a trade-off. Everything has a cost. And now we're having to reimagine all of those intuitions. It's it's kind of fascinating. Okay. And so final question for both of you. What is something what what's one of your favorite absurd things that you've built with Claude just because you could build it?

</details>

**Thariq Shihipar**: 我可以先聊聊。我目前正在使用 **Claude Code** 开发一款 **2D 街头霸王（Street Fighter）格斗游戏**，我本人是里面的一个可玩角色，同时我的朋友们也在里面。

它会调用 **Claude Code** 去写提示词调用 **Gemini**，Gemini 负责帮我生成 2D 游戏动画帧，生成的画面简直不可思议。而且大模型甚至能帮我自动研判和计算出角色的**碰撞箱（hitboxes）**——模型可以识别出：“哦，你的拳头现在挥到了这个像素位置，我自动帮你画出对应的 JSON 格式碰撞箱。”这真的太让人震惊了，不过我不确定我最后会不会公开发布这个游戏。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: I can go. Well, you think um I'm working on a 2D Street Fighter fighting game uh with me as a character and like my friends as well. Um and it uses Claude Code to prompt you know Gemini and honestly the image generation model is pretty good like uh to make like video animations. Um, and uh, it works great like like it's so good at prompting. It's like, you know, it can verify like the frames to check if this was a good animation. Yeah, exactly. Yeah. Yeah. Yeah. Like like 2D sprites. The animation looks amazing. And it can also figure out hitboxes. It can be like, oh, you know, your fist is like here, I'll draw the JSON hitbox. Yeah. Yeah. It's like incredible. Yeah. Yeah. So, um, I don't know if I'll put this out, but it's uh

</details>

**主持人**: 我们至少需要一张游戏截图，这听起来太酷了。

<details>
<summary>Original English</summary>

**Simon Willison**: I feel like we need a screenshot at least. This sounds...

</details>

**Thariq Shihipar**: 好的，这没问题。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: I can make a screenshot happen. Yeah. Yeah.

</details>

**Cat Wu**: 我的尝试相对简单一些。我是一个攀岩爱好者，我的很多朋友也是。所以我们利用 **Claude Code** 构建了一个定制小应用，用来记录和规划我们所有的岩友攀岩项目，以及我们的户外出行行程。

这非常依赖 **Claude Code** 的工作流（workflows）功能，这个功能在做深度背景调研方面表现得令人叹为观止。我也用它来策划我们团队的户外团建（off-sites），它非常擅长去网上筛选能够同时容纳我们这么多人的团建场地。

而对于攀岩应用，它会帮我调研攀岩目的地，筛选从我们每个人所在地出发是否有直飞航班；自动在 Mountain Project 网站上筛选出符合我们攀爬等级的线路；匹配合适的 Airbnb。最重要的是，我不喜欢徒步登山，所以我对攀岩线路到停车场之间的步程距离（approach distance）有非常苛刻的要求——步行不能超过五分钟。

**Claude Code Workflows** 帮我完美过滤和筛选出了所有符合条件的岩壁线路。在以前，我只能自己在 Mountain Project 上逐个点击筛选，而现在，它为我们团队生成了一个完全量身定制的应用。

<details>
<summary>Original English</summary>

**Cat Wu**: Mine is much more simple. Um I'm a big rock climber and a lot of my friends climb and so we have this little app that we built with Claude Code that where we just log all the projects that we're working on and we also uh go outdoors together a lot. So we have uh Claude do all this research with workflows. Workflows is amazing. Like we brand it as a coding tool but it's amazing for doing deep research for travel. Um, I also plan our team off sites and it's good at finding venues that can fit all of us. Um, it yeah there it has a lot of uh side benefits. But anyway, um I also use workflows to just research all the climbing destinations that we might want to go to, what has direct flights from where all of us are located. It goes to Mountain Project and finds all the climbs that are in our grade level. It finds the Airbnb and it actually maps out like I I don't like hiking and so I care a lot about it having a very short approach. So very short walking distance from where the car parks to where the rock actually is. And so it it filters for this and so I like with existing apps I have to like manually click through Mountain Project but with this I just put in all of our preferences and it's just a custom app for us.

</details>

**主持人**: 所以你基本上是用大模型给自己写了一个攀岩界的 Jira（笑声），这太棒了。接下来我们有时间回答几个观众的问题，请台下的观众到麦克风前，我会为台上的嘉宾重复你们的问题。

<details>
<summary>Original English</summary>

**Simon Willison**: So you're you're basically vibe coding Jira for mountain climbing. Exactly. That's that's pretty fantastic. Um, you know what? We have time for a couple of audience questions. Um, if you want to sh if you want to come forward and say them to me and I will repeat them so everyone can hear them. But yeah, um, tell you what, anyone who gets here first gets to ask a question. Sorry for people at the back. Hey um actually yeah

</details>

---

### 观众提问互动

**观众 A**: 谢谢。我的问题是，你们在近期是否有计划为我们提供更多关于编写评估集（evals）的数据集的工具？或者是更强的工作流与智能体性能的可观测性工具（observability tools）？

<details>
<summary>Original English</summary>

**Audience Member A**: my question is that um do you have any near plan to build more uh eval uh tools for us to build eval data set or anything like that and um more observability tools to monitor the performance of agents and uh workflows.

</details>

**Cat Wu**: 我们确实考虑过编写评估工具。但是我们发现目前制约客户建立高质量评估体系的瓶颈，并不是缺乏工具，而是大家在方法论上缺乏经验——即如何编写一个出色的 Eval。这是我们非常期待在内部加大投入，并在未来与行业分享和输出优秀实践的地方。

<details>
<summary>Original English</summary>

**Cat Wu**: We've considered building eval tools, but I think the limiting factor actually tends to be that it takes a long time for customers to build really high quality evals. And so I think the tooling is less of the constraint and more of the skill set of how do you build a great eval? And that's an area where we're excited to both invest internally and also hopefully we can share some of the best practices externally.

</details>

**观众 B**: 你们好，我的名字是 Sai。我对记忆系统（memory）和多人协作非常感兴趣。你们的记忆系统目前是如何设计的？我猜测它是基于文件存储的。另外，你们是否有考虑过用非文件型的数据库来存储这些记忆，以便能够实现更好的扩展性？

<details>
<summary>Original English</summary>

**Audience Member B**: Hey Katar, uh my name is Sai. Uh so my question was because I'm more interested in the memory and the multiplayer. How does how is memory being designed? So two questions right uh so how is memory being designed today I I assume it's around files. So and second part of it is have you thought about thinking in an orthogonal direction where you would actually need a data store to store these memory instead of files to scale it better. So I think that's my question.

</details>

**Thariq Shihipar**: 目前在 **Claude Tag** 中，我们的记忆是以 Slack 频道为单位进行隔离的。即同一个频道里的所有 **Claude** 实例共享相同的记忆，同时会话也可以随时把结果更新回主记忆中。

在记忆管理方面，我们正在进行大量的实验，它其实有很多反直觉的挑战。目前，我们在 **Claude Tag** 里的实现方式非常轻量，每个 Slack 频道对应一个后台的 **Markdown 文件**。当然，我们也会不断推进这一方面的研究工作。

<details>
<summary>Original English</summary>

**Thariq Shihipar**: Yeah right now for Claude Tag the memory is channel specific. So every Claude in that channel has a shared memory and then you know the instances have a session um but like the session can contribute back to main memory. We do a lot of memory research and it's you know can be kind of unintuitive like what what is the right way to do memory. Uh but yeah we're always working on this. So yeah uh yeah I mean we're always running memory experiments. I don't have you know anything to yeah like how it works right now in Claude Tag is a markdown file per channel. Yeah.

</details>

**主持人**: 谢谢大家。很遗憾我们今天的时间到了，请大家用最热烈的掌声感谢 Cat 和 Thariq。我们随后会在外面的走廊上与大家继续交流，解答大家的疑问。

<details>
<summary>Original English</summary>

**Simon Willison**: Thank you. So I'm afraid we're out of time. Please join me in thanking Cat and Thariq and we will be around for more questions um in the hallway.

**Thariq Shihipar**: Thanks guys.

**Cat Wu**: Thank you.

</details>