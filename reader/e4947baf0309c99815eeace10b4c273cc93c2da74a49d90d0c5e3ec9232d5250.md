---
author: How I AI
date: '2026-06-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5FKBkUCaLa8
speaker: How I AI
tags:
  - vibe-coding
  - ai-assisted-development
  - autonomous-agents
  - software-engineering-efficiency
  - product-prototyping
title: Gusto CTO 的 10 周颠覆之旅：5 人团队如何用 AI 智能体重构产品交付
summary: 本期访谈中，Gusto CTO 兼联合创始人 Eddie Kim 分享了如何利用 AI 工具在短短 10 周内，通过由 4 名工程师和 1 名设计师组成的极简团队，开发出全新智能体产品 Gusto Co-founder。他们摒弃了会议、Figma 和 Jira 看板，依靠 24 小时在线的 Zoom 和极快的 PR 审查速度，实现了敏捷交付。同时探讨了设计师转型工程师的可能以及 AI 时代下研发团队的敏捷交付新模式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Gusto
  - Cloudflare
  - Vercel
  - Coinbase
products_models:
  - Cursor
  - Claude Code
  - Magic Patterns
  - Chat PRD
media_books: []
status: evergreen
---
### 伦敦延误的创意火花

**Eddie**: 我们没有会议，没有消息回复（textbacks），没有 Figma，没有用来追踪 Story 或工作任务的 Jira 看板。我们什么都没有。我们只用 **Cloudflare Worker** 来运行实际的 **Agent 循环**，以及 **Vercel AI SDK**。仅此而已。

<details>
<summary>Original English</summary>

**Eddie**: We had no meetings. We had no textbacks. We had no Figmas. We had no Jiraboard where we tracked stories or tracked work. We had nothing. We used Cloudflare worker for the actual agent loop and Vercel AI SDK. That's it.

</details>

**Claire**: 人们常常被构建 Agent（智能体）这个想法吓倒，而我的态度是，这无非就是一个运行在云端某处的 **Agent SDK**，如果你使用 AI SDK，你还可以随时切换模型。就这么简单。它可以查找文件，可以拥有工具。这真的没那么可怕和复杂。

<details>
<summary>Original English</summary>

**Claire**: People get really intimidated by the idea of building an agent and I'm like literally it's an agent SDK running somewhere in the cloud and if you use AI SDK you get to switch your model. That's it. It can look up files. It can have tools. It's really not that scary and complicated.

</details>

**Eddie**: **Gusto Co-founder** 主要由 5 个人在 10 周的时间里开发完成，从最初的想法、零代码，到最终在 **Gusto** 进行的一级发布（Tier One Launch）。

<details>
<summary>Original English</summary>

**Eddie**: Co-founder was primarily built by five folks over the course of 10 weeks from initial idea, zero code to a tier one launch at Gusto.

</details>

**Claire**: 你们是如何做出那些只有天才产品经理才能做出的、关于功能是在范围内还是范围外的珍贵决策的？这真的重要吗？

<details>
<summary>Original English</summary>

**Claire**: How did you all make those precious decisions that only genius product managers can make about in or out of scope? Will this matter?

</details>

**Eddie**: 我们会直接构建功能，然后进行讨论：保留这个功能有意义吗？如果有，我们就会当场进行代码审查；如果没有，我们就会直接删掉它。

<details>
<summary>Original English</summary>

**Eddie**: We would build features and we'd have a discussion like does this make sense to have or not? If it is then it would get code reviewed right then and there and if not we would just delete it.

</details>

**Claire**: 我称之为软件工程的 **“垃圾桶开发法”（trash can method）**。在当下，你完全可以直接废弃所有代码，比如开一个 V2 分支，然后从头重写，这完全是合理的，因为编写代码的成本太低了。欢迎回到《How I AI》。我是 **Claire Vo**，一名产品负责人和 AI 狂热爱好者，我的使命是帮助大家利用这些新工具构建更好的产品。今天，我邀请到了 **Gusto** 的 CTO 兼联合创始人 **Eddie Kim**，他将向我们展示他如何带领三名工程师和一名设计师，在短短 10 周内完全重构了他们的应用。这不是一家小公司，但他们的交付速度却像初创公司一样。让我们开始吧。本期节目由 **Magic Patterns** 赞助播出。如今的工程师使用 **Cursor** 和 **Claude Code** 在几个小时内就能交付以前需要数周才能完成的功能。如果你是设计师或产品经理，你可能也感受到了这种转变。面临着更快行动、更快验证的压力，必须跟上以完全不同速度运转的团队。你可能已经尝试过使用 AI 原型设计工具来缩小这一差距。但是，如果你的原型看起来不像你的实际产品，无论你构建得有多快，最终还是需要手动重新绘制。**Magic Patterns** 能够带领你的产品团队从想法走向生产，并且直接基于你真实的系统设计开展工作。

<details>
<summary>Original English</summary>

**Claire**: I call this the trash can method of software engineering right now where you can actually trash all the code, start like a [music] slash V2 branch, and rebuild it from scratch and it's totally reasonable to do because the cost of the code is so [music] low. Welcome back to How I AI. I'm Claire Val, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Eddie Kim, CTO and co-founder of Gusto and he's going to show us how he three engineers and one designer completely rebuilt their app in just 10 weeks. This is not a small company and yet they're shipping like they're a startup. Let's get to it. This episode is brought to you by Magic Patterns. Today's engineers use Cursor and Claude code to ship features in hours that used to take weeks. [music] If you're a designer or PM you've probably felt a shift too. The pressure to move faster, validate sooner, and keep up with a team that's operating at a completely different speed. You've already tried AI prototyping tools to close that gap. But, if your prototypes don't look like your actual product, [music] it doesn't matter how fast you can build. You still end up redrawing it by hand. Magic Patterns takes your product team [music] from idea to production and works from your real design system.

</details>

**背景音乐**: [音乐声]

<details>
<summary>Original English</summary>

**背景音乐**: [music]

</details>

**Claire**: 当你构建原型时，你得到的东西实际上看起来就像你的产品。你将能够更快地进行验证，更快地达成共识。当需要真正构建时，工程师可以使用 **Magic Patterns MCP** 将你的原型连接到 **Cursor** 或 **Claude Code**，从而在你离开的地方继续开发。你的工程团队就拥有了 AI 优势。让 **Magic Patterns** 成为你的得力助手吧，今天就在 `magicpatterns.com/howiai` 试用。Eddie，感谢你来到《How I AI》。我非常兴奋你能联系我聊聊，因为我现在最喜欢的主题之一就是 CEO、CTO、创始人和高管们重新亲自动手构建产品。你今天来这里就是要告诉我们，你和团队是如何以一种极快且完全不同的方式来构建产品的。

<details>
<summary>Original English</summary>

**Claire**: When you build a prototype, what you get back actually looks like your product. You'll validate faster, get alignment sooner, and [music] when it's time to build, engineers can connect your prototype to Cursor or Cloud Code with the Magic Patterns MCP to pick up where you left off. Your eng team has their AI advantage. Make Magic Patterns yours. Try it today at magicpatterns.com/howiai. Eddy, thank you for joining How I AI. I'm so excited you reached out to chat because one of my favorite themes that I'm seeing right now is CEO, CTOs, founders, executives getting back to building product. And you're here to tell us how you built some product with the team both in a very fast and in a completely different way.

</details>

**Eddie**: 好的，感谢你的邀请，非常高兴能再次联系。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, thanks for having me and uh great to connect again.

</details>

**Claire**: 是啊，请给我们讲讲 Co-founder 的故事吧。鉴于你运行这家公司、作为领导者和构建者的所有经验，为什么你认为这次经历与你以前见过的截然不同？

<details>
<summary>Original English</summary>

**Claire**: Yeah, so tell us the story of Co-founder and why you think this is, you know, given all your experience, you know, running this company, being a leader, being a builder, why this is so different than what you've seen before.

</details>

**Eddie**: 首先，这个产品与我们之前构建的任何东西都非常不同。但真正让我兴奋的是我们构建它的方式，以及我们如何将构建 Co-founder 过程中获得的经验——包括我们构建它的质量和速度——应用到 Gusto 研发团队的其他部分。你知道，我们研发团队有 1000 多人。所以，我觉得自己好像发现了一些非常不可思议的东西。我只想弄清楚，我们该如何将这种方法推广出去，不仅是在我们今天的公司内部，而且推广给任何从事工程、设计或产品管理领域的人。

<details>
<summary>Original English</summary>

**Eddie**: So, first of all, the product is really different from anything that we've built before, but what I'm actually really excited is kind of more of how we built this and how we can take the learnings that we had um in building Co-founders, the quality and the speed in which we built this, and apply this to, you know, the the rest of our R&D organization here at Gusto, which, you know, we have over a thousand people. And so, I think we're just, you know, I feel like I just discovered on something like really incredible. And I just want to like kind of figure out how do we spread the word to not just our company today, but to any kind of engineering, um, design, or product management discipline person.

</details>

### 五人团队与零文档模式

**Claire**: 你提到你们的研发团队大概有一千人，但请再提醒我一下，构建这个产品一共花了多少人手？

<details>
<summary>Original English</summary>

**Claire**: And so, you say you have about a thousand people in your R&D organization, but remind me, how many people did it take to build this product?

</details>

**Eddie**: Gusto Co-founder 主要由 5 个人完成：我本人、另外三名工程师（我自己也算一名工程师，所以算是四名工程师）以及一名设计师。也就是说，我们有一名设计师和四名工程师。我们在 10 周的时间里完成了它——从最初的想法、零代码，到 10 周后发布并成为 Gusto 的一级主打项目。

<details>
<summary>Original English</summary>

**Eddie**: Gusto co-founder was primarily built by uh five folks, myself, three engineers, I count myself as an engineer, so four engineers, and one designer. So, we had one designer and four engineers, and we we built it over the course of 10 weeks from initial idea, zero code, um to 10 weeks shipping it to a tier one launch at at Gusto.

</details>

**Claire**: 这感觉一定太棒、太有趣了。我不知道你是否像我一样，在 AI 时代到来之前的几年里，我把大量时间花在做优先级排序、做季度规划上，嘴里念叨着：“这能挤进第一季度吗？还是得等到下一个财年？”而现在，你竟然可以只剥离出不到半打的人手，就在不到一个季度的时间里，交付一条完全全新的、真正的产品线，这太神奇了。

<details>
<summary>Original English</summary>

**Claire**: It's got to feel so much so fun. I don't know if you're like me, I I spent the past couple years uh pre-AI spending so much of my time like prioritizing and planning out quarters and saying, "Can this come in Q1, or is this going to be a next fiscal year thing?" And now, where you can take, you know, peel off less than half a dozen folks and ship a real

</details>

**Eddie**: 是的。

<details>
<summary>Original English</summary>

**Eddie**: Yeah.

</details>

**Claire**: 在不到一个季度的时间里开发出一条完全全新的产品线，真是太神奇了。

<details>
<summary>Original English</summary>

**Claire**: a real product line completely net new in less than a quarter, it's pretty amazing.

</details>

**Eddie**: 这确实不可思议。而且这个项目的源头并不在任何路线图上。这绝不是我们真正计划要做的事情。它的诞生完全是因为，在今年二月份我正在度假，当时我从马德里飞回来，在伦敦转机。而从马德里到伦敦的航班延误了，这导致我刚好错过了从伦敦飞往旧金山的后续航班。因为错过了这班飞机，我不得不改签下一班，这让我在伦敦有了长达 5 个小时的滞留时间。当时我有点生气，因为原本离家那么近了。于是我想：“好吧，现在我有 5 个小时需要打发。我回到旧金山的时间肯定会非常晚。我该做点什么呢？”

在那之前，我一直在尝试玩一些 **Claude Code** 类似的东西。我大概就是那种你偶尔会听说过的技术管理者：在周末凭着一股冲动“情绪化写代码”（vibe code）搞出一个东西，然后跑去工程团队面前炫耀：“看，我把这玩意儿写出来了，为什么你们自己做不到呢？”然后把大家惹毛，因为首先这完全是“情绪化编码”出来的，根本不具备生产环境的质量。

但这确实就是我切入的契机。我开始越来越多地使用 Claude Code 来做一些原型，将自己脑子里冒出来的各种零散想法具体化。在伦敦那 5 个小时的延误中，我拿出电脑，开始把脑子里琢磨已久的一个想法用 Claude Code 实现出来，看看自己能走多远。当我在旧金山落地时，我已经搞出了一个原型，也就是后来 Gusto Co-founder 的雏形。

一落地，我就把它拿给我经常沟通的几位资深工程师看。我也和我们的设计师 **Katie Kovalcin** 聊了聊。我们开始在这个想法上进行脑暴和迭代。虽然 Gusto Co-founder 最终呈现的形式与我当时做的原型有些出入，但这确实是整个项目的起点。而在那之后的 10 周，我们就把这玩意儿发布了。

<details>
<summary>Original English</summary>

**Eddie**: It is incredible, and the origin of this was not on it wasn't on any road map. It was not anything that we really thought about. It kind of just came about because um, I was actually on vacation in February, and I was flying back from uh Madrid, uh my flight had a layover in London, and my the mid the flight from Madrid to London was delayed, and I I just barely missed my flight from London to San Francisco. And I had this like five-hour layover now because I missed the flight, and they had to book me on the next flight. And I was kind of pissed about it because I was so close, and so I was like, "Okay, now I have like five hours to like waste. I'm going to get home super late in San Francisco. What do I do?" And I had been like kind of playing around with Cloud Code. I was probably one of those like tech leaders that you sometimes hear about that like vibe code something over a weekend and then come to their engineering team and say like, "Look, I built this whole thing. Why can't we do it yourself? You know?" Like and then just kind of like piss people off because, you know, first of all, that was like completely vibecoded. It's not production ready. Um but that was that was my start into it. I was I started using Cloud Code a lot more for the prototype things and just kind of like, you know, materialize random ideas that I would have. And so, in this like 5-hour layover, I just took out my computer and started Cloud Coding this um idea that had been percolating in the back of my mind and just seeing how far I can get with it. And by the time I had actually landed in San Francisco, um I had this like prototype of of what ultimately became Gusto co-founder. And um I just took it to a few engineers that I talked to regularly, our our senior engineers. I talked to Katie Kovalcin, our designer. And we just started like riffing on the idea a little bit. The ultimate uh materialization of Gusto co-founder is a little bit different from that prototype that I had made. Um but that was the really the origin of this all of this all. And 10 weeks after that, like we we shipped this thing.

</details>

### 极低代码成本与垃圾桶模式

**Claire**: 我太喜欢这个故事了，我要稍微跑个题，因为我经常从身边的朋友那里听到类似的故事。你知道我觉得公司应该多给员工放什么假吗？那就是育儿假和长时间的长途飞行。我一次又一次地听到那些“情绪化编码”的奇迹就是在这些时间里发生的。比如：“我当时在度假，但我用 Claude Code 搞出了一个很棒的东西。”或者“我当时在休育儿假，一只手抱着娃，另一只手在调 CodeX，然后我就把东西发布了。”我觉得这种模式会逐渐渗透到开发者的日程表里。如果你能给人们一段不受会议打扰的完整时间，我们就能推动产品向前迈出非常有意义的一步。这就是我对我们未来工作模式可能需要发生转变的一个小小的假设。

<details>
<summary>Original English</summary>

**Claire**: So, what I love about this story, I'm going to take a little detour because I've heard this over and over again from friends, is you know what I think companies need to give? Just a little bit more time off. Parental leave and like long flights. That is where I have heard the vibe coding magic happens over and over again. Like, "I was on vacation, but

</details>

**背景笑声**: [笑声]

<details>
<summary>Original English</summary>

**背景笑声**: [laughter]

</details>

**Claire**: “我虽然在度假，但我用 Claude Code 写出了很棒的东西。”或者“我当时在休产假，一只手抱着宝宝，另一只手在敲代码，然后就上线了。”我觉得这种模式应该推广到创作者的日常安排中。如果能给团队一整块不被会议打断的时间，我们就能把产品推进得更有深度。这就是我对我们工作方式需要做出改变的一个小猜想。

<details>
<summary>Original English</summary>

**Claire**: I Cloud Coded something awesome." Or "I was on parental leave and I've got like a baby in one arm and like Codex in in the other and I've shipped something." I just think it's going to it's going to trickle down into like maker schedules a little bit more where if you can give people just a block of time where they're not in meetings, we can move product forward a lot more meaningfully. So, that's a little a little hypothesis that I have about how how some of our work might need to shift.

</details>

**Eddie**: 我完全赞同。实话说，经历过这次之后，我甚至想多去度几次假了，因为上一次度假竟然催生出了这么大的一项成果。说不定下次去度假还能再搞出什么新东西呢。所以我们要开始谋划下一次去哪儿玩了，要是中间能再碰上一个 5 小时的航班延误，我实际上会非常高兴的。

<details>
<summary>Original English</summary>

**Eddie**: I I totally agree. Like now after going through this experience, I mean I I kind of want to take more vacation, honestly, cuz I actually I actually went to my wife and I were going to take another vacation because like this huge thing came out of the last vacation that that that we took. And so maybe like another thing will come out of it. So, let's go like let's figure out where to go and then you know, if I have a 5-hour layover, I'm actually going to be really really happy about that.

</details>

**Claire**: 哈哈，这就是每位 CEO 或高管推广 AI 落地时的绝佳话术了：“看，如果你能在度假时通过情绪化编码搞出很棒的产品，我们非常乐意给你批更多的假期。”不过，让我们言归正传，聊聊你们是怎么把这东西做出来的。你在伦敦中转延误时有了这个想法，并在脑海中反复琢磨，接着做出了一个原型，带回给了那个我称之为“元老院”的产品与工程师骨干团队，问他们“这需要花多少工夫？”能跟我讲讲那 10 周具体是怎么度过的吗？给我们展示一些在过程中产生的、与以往不太一样的流程或产出物吧。

<details>
<summary>Original English</summary>

**Claire**: Okay, this is how every uh CEO or executive can land the AI adoption pitch. It's like, "Look, if you go on vacation and write code something awesome, we're we're happy to give you happy to give you more." Well, let's go back to how you built this. So, you were on a layover, you have this idea was kind of like percolating in the back of your mind. You built a prototype, you brought it back to this like council I call them council of elders like this council of a product builders or engineers just saying like, "What what would it take?" Tell me though how you how those 10 weeks actually happened. And maybe show us some of the process and some of the artifacts along the way that were a little bit different.

</details>

**Eddie**: 没问题。其实我们没有什么官方的“元老院”，只是一些我经常打交道的资深个人贡献者（IC）工程师。我为这个原型录制了一个 Loom 视频，然后在他们之间传阅。

就是这群人对这个想法表现出了更大的兴趣，纷纷讨论：“那个功能怎么样？这个功能怎么实现？这非常酷！”接着到了我们公司每季度一次的 **Anchor Week**。这时，公司所有的资深领导和资深个人贡献者都会聚在我们的一个办公室里办公。那一次正好是三月份，在科罗拉多州丹佛的办公室。

于是，我们就在周四那天（我记得大概是 3 月 20 日）预订了一间会议室。我们这五个对项目感兴趣的人，就在会议室里对着白板讨论。白板上画的非常简单，其实就只有一页 Gusto Co-founder 应用的草图。接着，我们就动手开发了。

最疯狂的地方在于，我们的开发过程更多是由“我们不做什么”来定义的，而不是“我们做了什么”。我们实际上把所有繁文缛节都归零了。我们没有任何会议，没有任何消息回复，没有任何 Figma，没有任何用来跟踪 story 和日常工作的 Jira 看板，没有每日站会，没有复盘会，什么都没有。

我们唯一决定保留的，就是 **24/7 全天候在线的 Zoom（Perma-Zoom）**。因为这个团队中的所有人都是远程办公的，我们就开设了这样一个一直不关的 Zoom 会议室。有些人喜欢整天待在里面，安静地各干各的活；有些人则在有需要的时候随时加入或退出。这是我们唯一的结构化机制。

而我们当时拍下来的那块白板照片，就是在这整个 10 周的过程中，我们所产生的**唯一一份文档**。在开发期间，随着其他人听到了风声，他们经常跑来问我：“能发一份关于这东西工作原理的文档吗？”而我非常乐意回答他们：“我们没有任何文档。”

<details>
<summary>Original English</summary>

**Eddie**: Yeah, I mean there was no like official council. It was like just senior engineers that I regularly like IC's that I regularly talk to and you know, I recorded a loom of this thing and I just started sharing it around. Um and these were the folks that kind of like engaged a little bit more in the conversation like, "What about that? What about that? That's pretty cool." And then so we have at at at our company this thing called anchor week uh which happens quarterly. We all like kind of the senior leaders and senior IC's um across the company they they meet in one of our offices. This particular one uh was in March uh in in Denver, Colorado in our office up there. And so we just reserved a room that Thursday. I think it was like March 20th or something like that. And we we just started like whiteboarding with this like group of five that I had sort of, you know, had that had expressed some interest in this. We just white boarded like what this would potentially look like. And it was just like literally a page of the Gusto co-founder app. And we just got to building. The crazy thing is this was more defined our build process was more defined by like what we didn't do versus what what we did. We actually just zeroed everything out. We had no meetings. We had no text backs. We had no Figmas. We had no Jira board where we tracked stories or tracked work. We had no stand-ups, no retros. We had nothing. The only thing we decided to keep was 24/7 perma-zoom, which is basically a zoom room that we just keep cuz every cuz every everybody is remote on in this particular group. And we just had this zoom room that's going 24/7. And some people like like to honestly stay in there all day and just like do their work. They just kind of like sit there quietly. And some people will like kind of pop in and out when they need something. That was the only structured thing that we had was this zoom. It was like literally just zoom, a lot of cloud code, tokens, and some like really passionate people about turning this thing in into reality. And that that whiteboard um that we took a photo of was like literally the only documentation that we ever produced in this whole 10-week process. And I can't tell you how many times I loved as people like caught wind of this thing getting built. They were like, "Oh, can you send some documentation on how this works?" And I love to say, "We don't have any documentation."

</details>

**Claire**: 好的，这就是当时那块白板的草图。对于那些只听音频的听众，我来描述一下，这上面只有一些涂鸦，写着“Chat”（聊天），有一个图表，写着“Task Name”（任务名称），旁边还有几个没有怎么详细说明的组件。作为 CTO，你告诉我，你们基本上仅凭这些草图，在 Perma-Zoom 里用 AI 写出了整个产品？

<details>
<summary>Original English</summary>

**Claire**: Okay, so this is the whiteboard. And just for folks that are not listening, it's a scribble a that says chat. It's a chart, it's a thing that says task name, and then like a couple components on the side that are not very well specked out. And what you're telling me as CTO is we built the entire product basically off this cloud code in a perma-zoom.

</details>

**Eddie**: 是的，没错。虽然功能后来不断演进，但如果你看一下 Gusto Co-founder 的核心机制与底层功能，它们跟白板上画的几乎是一模一样的。我们稍微调整了命名，比如在现在的 Co-founder 里，其中一个核心原语被称为“自动化（Automation）”，它基本上能帮你运行这些工作流。这就是你在白板上看到的“任务（Tasks）”——任务下面会有对应的“任务运行（Task Runs）”。

在今天的 Co-founder 里就是这样的结构。任务运行会产生一些图表、文档或 Markdown 文件。在白板上我们叫它“资产（Assets）”，但最终我们把它重新命名为了**“神器”（Artifacts）**。

当然，还有“Chat”（聊天）和“建议任务（Suggested Tasks）”。如果你看今天的 Co-founder，它完全就是白板上那些草图的具象化呈现。如今回过头来看，我都有些惊讶我们竟然如此紧密地遵循了当时的白板构想。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, totally. And And if you look at obviously things have evolved a bit, but if you look at sort of the core primitive and core functionality of Gusto co-founder, um it's largely the same. They kind of like change the names of things, but one of the main things in Gusto co-founder is what we call now an automation. And it's basically just create these automations that like run these workflows for you. Um that's what you see here on this whiteboard called tasks, right? So it's like tasks have task runs. Um And that that's exactly what we have in co-founder today. Um we have assets of So tasks runs can produce these um charts or documents or markdown files. We call those in this whiteboard here assets, but eventually those got got got got renamed to artifacts. Um and then you obviously have chats. You have like suggested tasks. So like basically this like if you look at co-founder today that it is like the the actual like materialization of what you have on this whiteboard. Looking back on it, I'm actually kind of surprised right now how how close we we stuck to this.

</details>

### 敏捷产品决策与“垃圾桶”精神

**Claire**: 我必须问你几个关于你们如何做到的战术性问题，因为这也是听众们最想了解的。我的第一个发现是，你提到你们有四名工程师和一名设计师。我这里没听到有产品经理（PM）这个角色。在没有任何名义上的产品经理的情况下，在这支 5 人团队里，你们是如何进行产品决策并确定哪些功能要放入 Scope（范围），哪些不要的？

<details>
<summary>Original English</summary>

**Claire**: So I have to ask you a couple tactical questions about how you pulled the this off because that's what people listening are going to want to know. So my first observation is you said you had four engineers and a designer. I don't I don't hear a product manager in there. So how did you all make you know those precious decisions that only genius product managers can make about in or out of scope, will this matter? I mean this sort of feels like the thing where you just had conviction and knew you needed to build it, but you know, in this world where there was no actual titled product manager on the team, how did you approach product decisions across this team of five?

</details>

**Eddie**: 我觉得，团队里的每一个人其实都是产品经理。我们会直接去写功能，然后在这个 Perma-Zoom 里向彼此演示。接着我们就会展开讨论：做这个有意义吗？如果有，当场就会进行代码审查（Code Review）并合并；如果没有，我们就直接把它删了。

在以前，这样做是极其痛苦的，因为写一段代码需要耗费太多心血。但现在有了 AI 工具，我们写一个功能，提交并开启一个 Pull Request（PR）——这不是那种草稿 PR，而是随时准备好供人类进行 Code Review 的 PR。

然后我们开始讨论这个功能是否是大家想要的。如果答案是否定的，我们就很坦然地把这个 PR 关闭并删除。一个写得非常好、随时能过审并上线的 PR，哪怕你确实花了不少时间去确保代码质量与运行无误，在讨论后觉得不合适，也直接就关掉了。

这成了我们决定功能去留的方式。现在编写代码的成本太低了，你完全可以采用这种方式来做产品开发，而在六个月前，我认为这是完全行不通的。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, I would say everybody was kind of a product manager. We would build features and we would go in that perma-zoom and sort of share it with each other. And we just have a discussion like does this make sense to have or not? If it is then like it would get code reviewed right then and there. And if not like we would just delete it. And normally that would be really really hard to do cuz like it takes so long to build something. But these days with Cloud Code we literally like write something a feature. We submit we open a pull request and this is not a draft pull request. This is actually a pull request um that is ready for a uh uh human code review. And we discuss it. We discuss if that's the thing that we want to have a functionality that we want to have. Um and we're okay with deleting that pull request if if the answer is no, right? You have a perfectly good pull request that was written that's like ready for human review. It's not slat. You actually like spend time to like you know, make sure this code works and and is written really well and then you just close it sometimes. That was like the that was like how we figured out what decided what goes in and what doesn't go in to this feature. Like the cost to write code is now so low that you can actually uh build uh products in in this way. And whereas I think you couldn't do that you know, six months ago.

</details>

**Claire**: 没错，我称之为软件工程的“垃圾桶模式（trash can method）”。在这个模式下，你写了代码，然后完全接受它们可能会被直接扔进垃圾桶。我认为这有两种表现模式：一种是你提到的，通过 PR 和预览分支来验证这是否是我们要的功能，如果不是，就关掉 PR；另一种我经常做的是，比如我们在 10 周内交付了 V1 版本，用户开始使用了，我们对产品形态和架构有了更好的感知。这时候从零开始重构是非常便宜的。你不需要在原有的废墟上缝缝补补，完全可以直接废弃之前的代码，起一个 `/v2` 分支，从头重写。因为代码编写成本极其低廉，这种做法完全是合理的。

<details>
<summary>Original English</summary>

**Claire**: Yeah, I call this the trash can method of software engineering right now where you build code and you're like actually literally okay with throwing it in the trash. And I I see two models of this. One is exactly what you say like a PR and maybe a preview branch branch to even validate is this the thing we want to build? And if the answer is no, you just close the PR. The other version of this that I do quite frequently is let's say we ship this V1 in 10 weeks. Customers start to use it and then we actually have a sense of what the product shape and architecture should be. Like it's very cheap to just build again from zero. You don't even have to build on top of what you've built. You can actually trash all the code, start like a /v2 branch, and rebuild it from scratch, and it's totally reasonable to do because of the cost the cost of the code just is is so low.

</details>

**Eddie**: 关于这一点，我有一个很有意思的故事。因为我带回来的那个原型，我自己其实非常满意，觉得写得很不错。当我们在那次白板会议上决定正式开干时，我的默认假设是大家会基于我的原型继续往下写。

然而，当时有一位工程师提出：“嘿，你觉得我们改用 TypeScript、用 Cloudflare Worker 来写，把实际的 Agent 做成一个独立的、无状态的 Repo 怎么样？”

当时我内心是非常抗拒的。我觉得这是我写的代码，写得挺好的，而他们竟然建议我直接重头来过。但最终，出于对团队的信任，我同意了。我们彻底删掉了我写的代码，从第一天起就从零开始。

如今回过头来看，那绝对是当时最正确的决定。但当时我确实感到很不舒服，因为毕竟投入了心血，那是我的代码，谁都不喜欢把自己写得好好的代码删掉，就像把一盘美味的食物倒进垃圾桶一样。但现在，我已经完全习惯了，现在当这种事情发生时，我完全不会有任何失落感。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, I have I have a funny story about that because um this prototype that I brought to the team, um I was you know, I was pretty pretty happy with it. Like and when we decided in that um that whiteboarding session to like actually like go ahead and build this, like my assumption was that we're going to continue to build on my prototype. And so someone one of the engineers brought up, "Hey, what do you think about like uh using uh building this in TypeScript and using a Cloudflare worker and kind of like making the actual agent like sort of a stateless thing that sits in its own repo." And I was like I didn't really didn't want to do it. I feel like I felt like this is my code. Like it was good code. And here they were suggesting to us start from scratch. And ultimately like I I you know, I trusted them. So I we agreed to it. We deleted my code and then we started from from scratch on that day. Um in hindsight that was like absolutely the best decision. And now but I think back then I had a lot of discomfort with that because like I had invested, you know, um that was my code. I like I don't like you don't like to delete perfectly good code. Like throwing something some good food in the trash. Uh but now like I'm totally used to it, right? It's It's there's no like sense of loss when that happens anymore.

</details>

### 云端无状态智能体架构

**Claire**: 这种体验确实很神奇。我发现自己也经常写了成百上千行代码，结果由于没有达到我的产品标准，或者在技术实现方式上有了更好的点子，就完全废弃掉。现在我非常习惯去提那些包含大量红字删除的 Diff，去重构底层的架构。我想问你一个关于架构的具体问题。跟我们聊聊 Gusto Co-founder 背后的技术原理和核心底座。我听你提到了 Cloudflare Worker。大家目前对智能体产品的技术架构都非常感兴趣。我很想知道，你们最终落地的是怎样的一套技术栈？为什么会选择这个架构？

<details>
<summary>Original English</summary>

**Claire**: It's It's totally It is just totally wild to me how how frequently I find myself writing lines and lines of code that ultimately are are great and never make it. Either because they don't hit my product bar or they just aren't technically how we want to implement. Um and then how often I'm just like taught like major red diffs uh all the time to just re-architect stuff. I do want to ask you a quick question about architecture. Tell us a little bit about um, co-founder and kind of some of the primitives behind the scene. I heard you say Cloudflare workers. People are actually pretty interested on how to technically build agentic products and so I'm curious kind of what stack you all landed on and and why and how you how you chose that architecture.

</details>

**Eddie**: 我们的技术栈非常简单。我们使用 Cloudflare Worker 来运行底层的 Agent 闭环，并使用 Vercel AI SDK。就这些，没有任何其他多余的框架或套件。其他的所有机制都是我们在内部自己写的。在过去，我可能会去想怎么引入第三方的内存组件、规划组件之类的。但对现在的我们而言，所谓的内存（Memory）就是通过一个工具，往数据库的“Memory”字段里写一条数据，就是这么简单。我觉得现在很多号称用于构建复杂 Agent 技术栈的重型框架已经不再是必须的了。只需要 Cloudflare Worker 和 Vercel AI SDK 就能跑得很好。

<details>
<summary>Original English</summary>

**Eddie**: Our stack is surprisingly simple. We build on we use Cloudflare worker for the actual agent loop and Vercel AI SDK. That's it. We don't have any other harness on top of that. Everything else was built in-house. You know, in the past I would have thought about how to use, you know, some third-party tool for memory or planning or things like that and it's really just, you know, memory to us is a tool that writes to a database column called memory and that simple, right? Everything is just like all the harnesses and things that we used to build like to is complex like AI agent loop stack. I think is no longer needed. It was literally just um, um, Cloudflare worker and and Vercel.

</details>

**Claire**: 哈哈，我太喜欢这个架构了。这与我在 Chat PRD 使用的技术栈非常相似。听到这一点很令人欣慰。因为人们常常被如何构建智能体这件事吓退，而事实上它非常轻量：一个在云端运行的 Agent SDK，允许你随意切换底层的 LLM 模型，它能读写文件，能调用 Tools（工具）。它真的没那么高深莫测。

<details>
<summary>Original English</summary>

**Claire**: Ah, I love it. That's very similar to my stack at at Chat Purity. So it's it's good to hear that, you know, people get really intimidated by the idea of building an agent and I'm like literally it's an agent SDK running somewhere in the cloud and if you use AI SDK which which your which switch your model. That's it. Like this it it can it can look at files. It can have tools. It's really not that scary and complicated. Um,

</details>

**Eddie**: 没错，甚至都称不上是一个循环。因为我第一次使用的时候也很惊讶，代码里根本没有写 `while(true)` 这样的硬循环，你直接调用 Stream 方法，SDK 自动就帮你处理好底层的 Agent 反复调用了，这确实很神奇。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, it's not even I was like blown away cuz it's my first time using it that there's not even a loop. There's not a while loop somewhere, right? It's just like call stream and it takes care of the loop for you. It's crazy.

</details>

### 首席设计师转型高产工程师

**Claire**: 是的。我还想从工程角度问问你是怎么推进日常开发的。因为按照你的说法，PR（Pull Request）在这里几乎取代了传统的 PRD（产品需求文档）。PR 既是你想构建什么功能的 Proposal，同时也是解决方案，大家直接看代码做决策。这大大压缩了整个开发闭环。你们当时是直接把这些代码合并到生产分支，然后放在 Feature Flag（功能开关）后面来测试和推进的吗？

<details>
<summary>Original English</summary>

**Claire**: Yeah. Well, I have another question technically on how you how you ran this because PR as like the PRD is almost almost what I'm hearing, which is PR is the proposal of what to build, how it gets built, the solution, you look at it in code, and so you've almost compressed that that loop. Were you merging those into your production app and putting them behind a feature flag and just Is that how you were technically managing this development process?

</details>

**Eddie**: 没错。这也是从 0 到 1 项目的红利之一，在其他成熟业务上你可能不一定能这么做。我们当时在 Web 应用里开辟了一个隐藏页面，并直接把代码合并部署到这个隐藏页面上，接着在此基础上以“渐进雕琢”的方式去打磨它。我们常开玩笑说这就像面对一块大理石，我们要一点点地凿去多余的部分，慢慢把它雕刻成一件艺术品。而且我们是在生产环境里原地进行这项雕琢工作的。

我们做过的一件非常酷、我也强烈推荐的事情，是关于我们的设计师 Katie。她最开始在生产环境里部署了一个“假体验”。这个页面拥有完整的 UI，正如我们在白板上画的那样。但如果你在输入框里输入文本并点击提交，它每次只会给你返回一条一模一样的固定假响应。它当时甚至没有连接到任何 Agent 闭环，也没有读写任何数据库，完全是纯前端。这有点像你在 Lovable 或类似工具上做出来的第一版前端效果。

接着，我们把这个纯前端页面通过 Feature Flag 部署到了生产环境。与此并行，工程师们开始在后端构建数据模型和 Agent 循环，并逐步将其接入这个原本是假的前端体验。前端界面保持不变，但原本死板的 canned response 被我们原地替换成了真实生成的智能体数据。你会看到这个原本只是用来演示、本该被丢弃的原型，在生产环境里被我们“原地注入了生命力”。这就是我们的开发模式。

同时，工程师在做后端逻辑时，有时也必须写一些前端界面来配合。虽然功能调通了，但前端样式可能写得比较粗糙。我们也直接把这合并到生产分支。随后，设计师 Katie 会跟进，去优化这个页面的前端体验。在生产环境里持续迭代，虽然在任何特定时刻看它都可能有些小 Bug，但它就是这样在生产环境里慢慢蜕变、打磨成了一个非常棒的成品的。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, exactly. So, I mean, that that is one of the benefits of like kind of a zero-to-one type thing. You may not be able to do that in all instances. Um but we had essentially a a hidden page in our web app, and we would land stuff into that hidden page. It would be on production, and then we would sort of like chip away at it. Like I think the analogy we use a lot was like we started with a block of marble, and we're just slowly kind of like chipping at this thing and forming it into like a piece of art over time. And we're doing that in production in place. So, one of the really cool things that we did, uh which I would highly recommend, is Katie, our designer, she actually shipped started shipping to production like a a faked experience essentially. So, it had like the UI, the the thing that we white-boarded, but if you go in and like, you know, hit put in some text into the text field and hit submit, it would just give you the same response like uh every single time, right? It's not actually going to any kind of agent loop. It's not hitting any kind of database. It's pure front end. It's kind of like what what you would maybe build as a first pass on Lovable or or something like that. And that actually got shipped to production behind this feature flag. And then in parallel, the engineers would start to build out the data models, uh they'd build the the agent loop, and they would start to connect this to the faked front end experience. And the front end would stay the same, but the canned like responses would get slowly and in place not even better. Like Like would actually be like real, right? And so you would see this thing kind of like morph from like um a a literal prototype that you would normally have thrown away because like it's just for demonstration purpose, but it would actually turn we would like like literally breathe life into this thing over time. And that's kind of how we how we built this. Um at the same time we would have engineers like build features and they would you know, have to do some front end stuff. They would they would ship the design for this, right? And the functionality on the back end would work really well, but then you know, the front end probably could use some improvement there. And we would ship that, too, right? And then and then Katie the designer would then go in and sort of like, you know, make make the experience a lot better on the front end. And so that was another example of like just shipping something into production and then like continuing to chip chip away at it to make it better over time. So if you look at it at any given time, there was always something wrong with it like in production, but then gra- over time like it turned into like this really nice thing.

</details>

**Claire**: 跟我多聊聊 **Katie** 吧。也许我们未来会邀请她也上一次播客。Katie 作为一个设计师，竟然在直接往生产环境提交代码。她的代码成为了承载这些后台逻辑的骨架。跟我聊聊，她原本就有技术背景吗？她是怎么过渡到直接编写代码的？在这个团队里，她的什么表现最让你感到惊讶？

<details>
<summary>Original English</summary>

**Claire**: And tell me a little bit more about Katie. We might have her on on the podcast, but Katie the designer is shipping stuff into production. Her code is the skeleton on which a lot of this functionality is is being built. Tell me how you know, was she was she technical? Is she technical? Was she a software engineer? How did she come to shipping code? Like what what blew your mind about her role in this team?

</details>

**Eddie**: 最让我震惊的，是她竟然蜕变成了一名极其出色的工程师。我前阵子看了我们在 DX 效率平台上的 PR 统计数据。在 Gusto 整个庞大的研发组织里，Katie 的代码吞吐量（True Throughput，即最终合并到生产分支的 PR 数量）居然排在 **第 94 百分位**。这可是把全公司所有科班出身的、经过系统培训的软件工程师都算进去之后的排名！作为一个设计师，她能排到全公司前 6%，这简直不可思议，而且她写的代码质量非常好。

我曾问过她：“你身上有什么特质让你能做到这一点？我们该怎么把这种能力推广到更多的设计师和 PM 身上？”她的回答主要有两点：

第一，她虽然不是科班出身，但她比普通的设计师有更强烈的技术好奇心，自带这种技术探求欲；
第二点也最关键：在这个项目组里，她身边有三四个非常乐意为她看 PR、给她提反馈的工程师。这群工程师愿意教她如何更精准地给 Claude 提 Prompt，以及如何去评判 AI 生成的代码是好是坏。

我们花时间去带她、和她进行结对编程（Pair Programming）。很多时候，我听到别的工程团队抱怨：“这太拖慢进度了，设计师还是老老实实画 Figma 吧，把设计稿还原成代码是我们开发的事。”在短期内这确实能省事，但只要你愿意做这笔初期投资，为设计师提供一个优秀的工程指导环境，它能带来的长期回报是极其丰厚的。

<details>
<summary>Original English</summary>

**Eddie**: What blew my mind was that she would turn into this incredible engineer. And I was just looking at our our our our PR stats, which we use this this tool called DX for it. She across our entire R&D org, she is night- in the 94th percentile of uh true throughput, which is a measure of like how many PRs you're landing into production. And that includes every single engineer, like classically trained software engineer in the company, right? She's out of 20, she's she's a top, right? Uh which is which is kind of insane and it's really good code. Like I asked her like, how how what is special about you and how do we get more of this like across, you know, design and and product management? And her answer was basically twofold. One is that she she's not an engineer, uh she's not a software developer, but she she feels like she was a little bit more like technically curious than than most designers. So she just kind of has a little bit of that more technical bent. And then most importantly is that she had a team of like three or four engineers, particularly on this team, that was willing to actually, you know, review her code, like give her feedback, um show her like how to prompt Claude a little bit better and like also how to judge um that taste of like what is actually good code that it's producing and what is not. We took the time to kind of like, you know, uh pair pair with her, right? Whereas I think a lot of engineers, what I hear them say is like, well, it just slows us down and like designers should just focus on uh producing Figmas so that we can like really focus on turning that into real products. And yeah, that's true in the short term, but like now I think once you make that investment, you have a support of an uh software developer uh around her um or any designer, I think the dividends dividends pay off really really quickly.

</details>

**Claire**: 听到这里，我的心都要融化了。可能有些听众不知道，我本身也不是计算机科班出身的，但我坚信我能写代码。我已经写了 20 多年代码，管理过非常庞大的技术团队。在我职业生涯早期，我要特别鸣谢 Dave、Yelland 和 Jeremy 这几位工程师，他们当时愿意耐心地坐下来和我结对，解答我那些幼稚的问题，包容我那些超出技术水平的宏大产品野心。

现在虽然有了 AI，你相当于有了一个极具耐心的结对编程助手，但在团队文化层面上，我仍然认为**工程团队积极去引导、辅导和包容非工程背景的合作伙伴**是极其关键的。

我经常给很多团队做压力测试。有很多工程团队跟我诉苦，说他们被 Code Review 压得喘不过气来，或者抱怨非技术背景同事提的 PR 审核起来太慢。我就会问他们：“在你们团队里，非工程师提的 PR 的审核优先级和审核速度，是不是明显低于工程师提的？”毫无疑问，绝大多数人都会回答：“是的，确实慢很多。”

我告诉他们：“这就是一个典型反模式（Anti-pattern）。你们必须把这些非工程师提的 PR 视作和日常代码同样的高优先级。因为通过你的反馈，你能帮助他们构建更好的代码习惯与质量。况且很多非工程师的 PR 里包含着非常有价值的产品创见。在文化层面上打破这个壁垒，长期来看能赚取巨大的红利。”

<details>
<summary>Original English</summary>

**Claire**: This makes my heart grow 10 sizes. As someone who folks don't know, I did not get a software engineering degree and yet I I'm believe I can code. Um I have been I've been coding for over 20 years. I've run very large engineering organizations and a lot of that was early in my career. Folks, shout out to like Dave and Yelland and Jeremy, like were willing to sit with me and pair with me and answer questions and tolerate where my ambition outstripped my technical ability. Now, you know, even with these AI tools, you sort of have that very patient pair programmer next to you, but I do think culturally it's very, very important for software engineering teams to extend that mentorship and guidance and feedback loop to their non-engineering partners. And this is a stress test I give to a lot of teams because I hear a lot of teams being really overwhelmed by code review and being really overwhelmed by like what may maybe they'll call like slow PRs from non-technical folks. And I just say like on average is your engineering teams PRs getting faster review than their non-engineering teams PRs? And like across the board people are like, yeah, of course they are. I'm like, that is an anti-pattern. You need to prioritize reviewing these non-engineering PRs just as high as you do your engineering ones because you can give feedback, you can create systems that improve code quality. Um a lot of those PRs are actually really good ideas. Um and so I do think there's this cultural aspect to it that I'm really pleased to hear you've you've unhooked because I think it's going to pay dividends over the long term.

</details>

**Eddie**: 是的，我 100% 同意。在我们团队里，第一优先级的事务永远是 **PR 审查**。我们之前做过分析，发现我们团队的 **中位数 PR 响应时间是 9 分钟**。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, 100% agree. And and our priority has uh always been uh PR reviews. Um I think we did an analysis and I think our median PR review time was 9 minutes.

</details>

**Claire**: 只是在你们这支 5 人团队里吗？

<details>
<summary>Original English</summary>

**Claire**: On this team?

</details>

**Eddie**: 是的，就在这支小团队里，当然不是全公司。因为随时都有人待在那个 Perma-Zoom 里。只要你在 Zoom 里喊一句“我有个 PR 写好了，谁能来看一下？”，大家就能直接在里面进行讨论，或者开个分流讨论室（Breakout Room）结对过一遍，当场解决。

<details>
<summary>Original English</summary>

**Eddie**: On this team. Yeah. Not definitely not in like in the in the R&D org, but definitely on the team. And and the reason why is like there would always be someone on this perma-zoom. And so like you just show up in this perma-zoom and say, I have this PR ready, can we talk about it? And then someone um sometimes it's in a group setting, sometimes you just go in a breakout room with someone. We you just kind of talk through it together and and review it together.

</details>

**Claire**: 本期节目由 **Jira Product Discovery** 赞助播出。AI 确实极大地提升了单个产品经理的个人产出，但在团队协作上依然困难重重。想要在“究竟应该构建什么”上达成共识，决策过程往往散落在上周的 Markdown 文档里，路线图则躺在无人问津的电子表格里。Jira Product Discovery 是团队决定真正构建什么的地方。收集想法、团队协作进行优先级排序，并分享一张所有人都在协同更新的实时路线图。它基于 Atlassian 的 Teamwork Graph 构建，可以拉取客户反馈、开发团队交付的内容以及你们的既定目标，并对下一步应该构建什么给出智能化建议。一旦决策落地，你可以直接将其同步到 Jira 任务中，让工程师或智能体快速接手。Canva、Deliveroo 和 Toast 都在使用它，欢迎点击 `atlassian.com/hia` 试用。

这是否让你找到了早期创业的感觉？

<details>
<summary>Original English</summary>

**Claire**: This episode is brought to you by Jira Product Discovery. [music] AI has made individual PMs incredibly productive, but multiplayer mode is where it still breaks. Getting everyone aligned on what should actually get built. Decisions live in a markdown file from last week. The road map's a spreadsheet no one's looking at. Jira product [music] discovery is where teams actually decide what to build. Capture ideas, prioritize them as a team, and share a living road map everyone works from. It's powered by Atlassian's teamwork graph, so it can pull in customer feedback, what your team shipped, plus your goals, and suggest what to build next. And when a decision is made, you can hand it off straight to Jira, so a developer or even an agent can pick it up and start building. Teams at Canva, Deliveroo, and Toast already use Jira product discovery. Join more than 25,000 teams at atlassian.com/hia. Start building the right things together. Does this bring you back to like early founder days?

</details>

**Eddie**: 确实非常像初创公司。早年我们刚创办公司时，每一个人也都是直接写代码的。我们招来的设计师也必须懂一点代码，虽然跟现在的代码不太一样。当时他们写很多 HTML、CSS 以及一些轻量级 JavaScript，但大家都会提交 PR 并合并代码。

但随着公司业务规模变大，这套模式逐渐消失了，取而代之的是把大家塞进一个个传统的专职岗位（swim lanes）。现在这个项目，就感觉像是一次怀旧的回归：几个人对着几块白板，实时沟通并决定写什么，然后立刻就写。说实话，这挺辛苦的，要在 10 周内完成这样一个系统，意味着有很多晚上和周末我们都在干活。但我从来没有命令谁加班，大家纯粹是因为对我们在做的事感到兴奋，而且干得非常开心。虽然很累，但其乐无穷。

<details>
<summary>Original English</summary>

**Eddie**: It did feel a lot like the like startups. Actually, when we started, um also everybody coded back then. Like we hired designers at like, you know, um I mean, it's different type of code. They they wrote a lot of like HTML and CSS, and maybe some light JavaScript, but they coded, right? They they actually um uh open pull requests and and merged it. Um over time, I think that kind of went away. We said, "Oh, like everybody's got to go into these like traditional swim lanes." Um and this was like kind of almost a throwback to when we just started, right? Uh we just had maybe like a few whiteboards. We kind of like discussed in real time what we're going to build. We built it, and um yeah, and honestly, I mean, it was it was a lot of work. I I I will say that to ship something like this in 10 weeks did take a lot of like nights and and weekend time. Um but I didn't ask anybody to do it. They just did it because people were so um passionate about what we're doing, and honestly, they were having a lot of fun. It's so much fun. It was intense, but so much fun.

</details>

### 实战演示：智能体跑发薪

**Claire**: 这也是我从很多嘉宾那里听到的反馈。在经历了这一轮技术变革后，大家都表示“我现在干得比以前更拼了，但我也过得更快乐了。”工作变美妙了，因为所做的工作更具创造性，且更接近业务最终结果。你已经为我们描绘了这么棒的图景。但听众们回去可能会面临来自老板的无理要求：“人家 5 个人 10 周就能交付这么大的产品，而且 median PR review 只需要 9 分钟！”你在无意中拉高了整个行业的标准。不过，让我们来做个演示吧。能给我们展示一下你们到底做出了什么产品吗？顺便我们也很想看看你个人是如何利用 AI 编程助手来为项目做贡献的。

<details>
<summary>Original English</summary>

**Claire**: Uh that's that's what I hear from so many people. Um we've done so many of these I've done so many of these interviews and almost everybody says I'm working harder than I ever have and I am so much happier. I'm having so much more fun. Work is just better because the work that I'm doing is more creative. It's It feels like it's closer closer to impact. Okay. You've You've painted this vision. People are going to walk away and unfortunately their teams are going to be like, "You can ship this huge product in 10 weeks. It'll only take five people. I want nine minute per PR review review times." So you're setting the bar high. But let's like let's prove it. I mean show show us what you built and then maybe we'd love to see how you personally use Cloud Code or used Cloud Code to contribute to this product.

</details>

**Eddie**: 没问题，我来分享一下屏幕。对于音频听众，我会在演示过程中做一些口头描述。这就是大家所熟知的 Gusto 页面，我们在内部开玩笑地叫它“Gusto 经典版（Gusto Classic）”。不过，如果你是在 Co-founder 团队里，你才有特权把经典的旧版叫作 Classic。

这是 Gusto Co-founder。它是一个跑在后台、连接了各种工具的 Agent 闭环。

从用户的角度来看，它最核心也最有趣的一点是：它**直接内置了 Gusto 目前已经在为你处理的所有企业数据**。它拥有关于你公司所有信息的所有权，比如你的员工、薪资历史、排班、调休申请等等。

我们非常看重的一点是，除了在 Web 页面上使用它，用户主要可以通过 **SMS 短信** 或 **Slack** 来直接和它沟通。这里我在手机上输入一条：“我有什么需要审批的调休申请吗？”它会调用与 Web 端完全相同的底层工具，在后台运行并在短信里回复我。

我现在向大家展示的是我的 Android 手机的短信界面。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, sounds great. Let me um just share my screen here and I'll I'll for the folks on audio I'll try to walk through what's on my screen. This is Gusto This is the Gusto that everybody knows, right? This is kind of uh ironically we call it classic now. Uh when you're co-founder we would never But if you're in if you're in the co-founder group like you get to call the traditional Gusto Gusto classic. This is Gusto uh co-founder here. It does the things, you know, basic stuff. I don't think any of this stuff is particularly interesting. Um it's kind of like the normal agent loop that's connected to tools. Um I would say the really interesting thing about this from a user perspective is that it comes out of the box with all of the things that Gusto is is already doing for you, right? It has all the information that Gusto already has about your business, like your employees, uh your payrolls, your schedules, uh your time off requests and and things like that. And one of the things that was really important to us was just being able to communicate it communicate with it not just through the web, but actually we want people to primarily talk to it through SMS or or Slack actually, right? So here I'm going to say something like, "Do I have any time off requests that I need to approve?" And it would be the same exact thing as if I were to like ask this in the in the web application. Um it's calling the same tools and it's going to respond to me in through the same channels. By the way, for those listening in, I'm I'm showing a screen of my phone basically, my my uh messaging app on my on my Android phone. And I just typed in, "Do I have any time off requests that I need to approve?"

</details>

**Claire**: 我可以想象这种多渠道体验对于很多中小企业老板来说是极其关键的。因为他们整天忙于生计、四处奔波，大多数时候只能掏出手机来处理事务。对于我们这些长期构建 B2B Web App 的人来说，突然发现产品的交互界面缩减成了简单的短消息，这是一个非常奇妙的产品设计与技术架构挑战。比如你怎么向用户展示流式生成、降低用户对延迟的感知，让他们知道 Agent 正在后台为您干活。

<details>
<summary>Original English</summary>

**Claire**: What I'd imagine is this sort of like multi-channel experience is really important for kind of like small business owners in particular who are probably like running around doing stuff always operating on on their phone. Um And so I do think it's interesting as somebody who has like built B2B web apps for so long to think now my surface area is texting. It's just a very interesting product design problem. Um and then technical problem with, you know, how do you how do you show streaming or latency or make sure people understand that you are working. Um we're working on it. So I I think this whole surface area is very interesting.

</details>

**Eddie**: 没错。目前我们支持 Slack 和 SMS，未来我还想把 WhatsApp 和 Telegram 也加进去。这也是我之前在家折腾 Open Claw 时得到的一大感悟：即时通讯工具作为控制入口的威力是非常强大的。

你看，短信里它已经回复我了，它查到了有一位叫 Todd 的员工提交了调休申请。我只需要直接回复“Yes”，它就会帮我在后台把调休通过，我完全不需要再登录 Gusto 的 Web 页面了。

我们让它在后台自己跑着，回头再来看结果。我想向大家展示一个更复杂、也更有趣的真实客户案例。

我们有一位开按摩 SPA 馆的真实客户。他们平时使用 Mindbody 这个第三方系统来追踪店里按摩理疗师的工时和业绩（比如他们做了多少个 60 分钟的按摩，多少个 90 分钟的按摩）。此外，如果理疗师成功推销了特定的热石（Hot Stone）理疗或者 CBD 精油，他们还能拿到对应的 Bonus 提成。不仅如此，他们店里还有一个复杂的机制，要把所有客人的 Tips 收集起来在店员里进行平分。

所以这位老板每周发薪时，都得从 Mindbody 里导出数据，塞进一个像这样的 Google Sheet 电子表格里，接着在里面手动套公式计算出每个理疗师这一周的奖金、佣金和分摊的小费。计算出总数后，他再登录 Gusto，跳转到“运行发薪（Run Payroll）”页面，把这些计算好的数据逐个输入进去。

虽然在 Gusto 里的录入步骤很快，但真正繁重的是我所说的**“运行发薪前的准备工作（work before the work）”**。在有 AI 之前，小企业老板每周都要循环往复地做这种数据计算工作，这占用了他们大量的时间。

而在 Gusto Co-founder 里，我们内置了一系列连接器（Connectors）。Co-founder 可以直接读取 QuickBooks、Google Sheets、Notion 等第三方系统。

现在我只需要在聊天框里写出我的自然语言发薪指令：

“嘿 Gusto Co-founder，帮我发一下这周的薪水。数据请看这个叫作 `export from Mindbody` 的 Google Sheet 表格。以下是计算规则：每推销一次热石理疗，给对应的理疗师加 15 美元的奖金；每推销一次 CBD 精油，给对应的理疗师加 20 美元奖金。另外我们要把 Tips 平分，所以读取表里汇总的 Tips 总额，并除以这一周上班的理疗师总数。”

发送之后，Co-founder 就会像运行自动化脚本一样，在后台自动去读取这个 Google Sheet 里的表格数据，解析并应用这些计算规则，在后台自动套算并自动更新 Gusto 发薪系统里的数据。

完成计算后，它会停下来并列出明细对我说：“这是最终算出的金额。你确认要帮您提交本期发薪吗？”我只需要回复“Yes”，它就会自动帮我完成发薪。

大家可以在屏幕上看到，它已经算出了所有数据，包括工时、奖金和最终发薪总额。我只需要输入：“确认提交发薪。”它就会自动完成这一期的发薪。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, exactly. So we have right now today Slack and SMS, but um you know, I kind of want to add like WhatsApp and Telegram. I think that's kind of one of the things I learned from using OpenClaw of like the power of like the these uh messaging channels. Okay, so it responded um actually looked up that there is someone named Todd uh who uh has a time off request. And um I could just say, "Yes." And it'll actually approve that time off request. I don't have to do that in the web app anymore. So I'll just let that run so we can come back to it to uh see that it actually approved it. But I want to show something that's a little bit more interesting and and more more complex. Uh so this actually came from a real customer. And uh this particular customer that we have is a massage spa in New New City. And what they do is they use Mindbody to track all of their work of the of their massage therapists. And they basically have, you know, how many 60-minute massages did they do, how many 90-minute massages. They also get paid like a bonus if they do certain upsells like hot stone or CBD oil. And they have like a rate for that. They also like decide how they split they decided to split their tips like as like they group their tips together and and they split it. So what this owner has to do every week is they actually, you know, they export something from Mindbody, they put it into a Google spreadsheet like this, then they actually run these calculations of like how much to pay them in terms of bonus and commission and tips. And then, and only then, they actually go into Gusto and, you know, they they go to the run payroll page and then they they actually input all that all that in, right? That part is really fast, of course, but it's all this like what I call the work before the work that a business that is not using AI has to do to run the payroll every single week. And they do this like week in and week out, right? And so in Gusto co-founder I have a set of connectors where I can Gusto co-founder can actually access third-party systems like QuickBooks, Google Sheets, Notion and things like that. And what I can do is actually just literally say my process here. So I wrote here like, "Hey Gusto co-founder, I need you to run my payroll. Look at this spreadsheet that's called export from Mindbody. And here's how I calculate it. You know, for every hot stone upsell add $15 of bonus for that therapist. For every every CBD oil add $20 bonus for that therapist. We pull tips, so just take the group tips amount and divide it by how many therapists we have." And it just goes. And it's kind of like cloud code where it'll it's going it's going to that spreadsheet, it's pulling in the data, it's running those calculations, it's updating the payroll as you see here. And then it's actually going to get to a point where it'll stop and say, "Here the amounts. Do you want me to actually submit this payroll?" And I'll say, uh, "Yes." And and it'll actually submit and and run that payroll. So, basically, you can see here that it's calculated all my payrolls, um, the hours, the bonuses, the total payroll amounts, and I'll just type in, "I'd like to submit my payroll." And it'll actually submit the payroll.

</details>

### 实战演练：用 AI 修复 GitHub 缺陷

**Claire**: 太不可思议了。这一切居然仅仅源于你在机场延误那 5 个小时写出来的原型。而且它处理的不是玩具数据，而是真正的企业业务流。每当我跟许多大公司的管理者聊天时，他们经常兴奋地对我说：“Claire，我们正为今年 12 月的 AI 规划感到无比兴奋！”我心里想的则是：“12月？现在已经是 6 月了。你们现在就应该把它做出来。”

从这个故事的宏观层面来看，你向大家证明了：把你有野心的想法带到桌面上，并快速动手去实现它，在今天根本不需要多么庞大的团队投资就能做到。五个人，在 1000 人的研发组织里开发 10 周。哪怕退一万步讲，你把东西做出来并推向市场后发现客户根本不要，从研发资金支出的角度来看，这其实是一笔非常便宜的试错账。这只占你庞大研发开销里极其微小的一部分，但是一旦它赌赢了，能带来的业务杠杆和回报将是极其巨大的。

所以我经常建议别人：你们可以变得更有野心，在产品开发流程中，你们完全可以承受更多的风险。

<details>
<summary>Original English</summary>

**Claire**: Amazing. So, and all this came out of a Vibecode prototype because you had a layover. And this is real like this is real business business data. And so, you know when I'm talking to leaders at companies, they tell me, "Oh my gosh, Claire, I am so excited about our December AI launch." And I'm like, "December? It is June. Like, what are you talking about? You need to do this today." And so, I think, you know, one of the meta stories of this is like bring forward your ambitious ideas and just executing on them quickly is really possible with not that much investment. You know, the other thing that I think about is five people for 10 weeks in an R&D organization of a thousand. Let's say at the end of the day, you ship something you're like, "Ah, I just customers don't want it." is actually not that expensive in fun outlay. Like, it feels like a lot maybe, but it's it's a very small fraction of your overall R&D investment. And the payoff can be very huge. And so, part of the advice I give people that I think you're encapsulating is you can be a lot more ambitious. Um, and you can you can you can afford a lot more risk in your product development process.

</details>

**Eddie**: 100% 同意。试想一下，如果你的千人研发团队里，同时有 10 个这样的小项目组在并线推进呢？把这笔投资乘以 10，在千人规模的研发费用里也仅仅是九牛一毛。这其中的两三个项目，很有可能会彻底改变你们公司未来的业务走向。

<details>
<summary>Original English</summary>

**Eddie**: 100% yeah. Just imagine if you had maybe 10 of those going, which even if you multiply this by 10, that's not even that's not a big investment across a company of a thousand in in R&D. You know, you're going to have like two or three of those, I think. meaningfully change the trajectory of the business.

</details>

**Claire**: 我太喜欢这套方法论了。好吧，既然你一开始就自称也是这支团队的一名工程师，那跟我们秀一秀你是怎么在命令行使用 AI 开发工具的，或者展示一下你觉得顺手的日常开发环境。

<details>
<summary>Original English</summary>

**Claire**: Yeah, I love it. Well, okay, and then let's prove you said at the very beginning, well, I consider myself an engineer on the team. So, tell me a little bit about how you're using Cloud Code or maybe show show a little bit of your setup that you find useful.

</details>

**Eddie**: 哈哈，刚好今天早上我看到了一条用户反馈，其中有一个我想要修复的 Bug。要不我们现在就当场结对，用 AI 把它修好吧。

<details>
<summary>Original English</summary>

**Eddie**: It's funny, I was looking at some user feedback um this morning and I had a feature that um I wanted to build. And so, I thought maybe we could just build it together right now.

</details>

**Claire**: 太棒了，直接现场写代码！

<details>
<summary>Original English</summary>

**Claire**: Yeah, let's do it.

</details>

**Eddie**: 跟大家简单展示一下我是如何通过 AI 进行“情绪化编码”的。

这个 Bug 来自用户的真实反馈。我们在产品发布后一直在和用户保持紧密沟通。我在 GitHub Issue 里记录了这个缺陷：如果用户在 Gusto Co-founder 里询问“如何在旧版 Gusto（Gusto Classic）里操作某项功能”，Co-founder 会直接回答“点击这个链接，点击那个链接”。

但由于用户是在 Co-founder 页面内进行对话的，他可能根本不在 Gusto Classic 的页面上，这就会给用户造成极大的困惑。我们需要在给指引前，先明确地告诉用户：“请先切换并前往 Gusto 经典版”。

我把产生这个问题的一段真实对话记录也贴到了 GitHub Issue 里。

现在，我准备在终端里启动 AI 助手。这感觉简直像是在作弊一样。

<details>
<summary>Original English</summary>

**Eddie**: a little overview of how how I write code, how I Cloud Code. All right. So, this came out of some user um feedback. We've talking to customers since we've launched and I actually wrote this in a GitHub issue where uh we have this issue where if Gusto co-founder says how to do something in Gusto classic, um it says, "Oh, go click on this link and that link." And that doesn't make any sense based on the page that the user is on because they're not in Gusto classic, right? So, we need to basically tell them go to Gusto classic first. Um so, I basically like copied a example um uh user conversation that happened here where it caused some confusion. So, it feels like cheating almost is um I'm going to start Cloud Code here on my terminal. Always uh you know, you can introduce

</details>

**系统提示**: 正在跳过权限检查。

<details>
<summary>Original English</summary>

**系统提示**: skipping permissions.

</details>

**Eddie**: 另外顺便说一句，我日常频繁使用语音输入，现在很少手动打字了。

在终端启动 AI 后，我会对它说：“这有一个记录在 GitHub Issue 里的客户缺陷。我把 Issue 的链接发给你。请先阅读这个链接，并针对里面描述的缺陷给出一个修复方案。在开始写修复代码之前，我要求你先编写一个能够稳定复现该缺陷的 Failing Eval（测试用例）。接着，针对性地编写代码进行修复，并再次运行该测试，向我证明刚才失败的测试现在可以通过了。就这些。”

AI 随后会自动去读取整个 GitHub Issue 的内容，查看用户产生困惑的那段聊天历史，编写 Failing Eval，然后通过修改 Prompts 或底层逻辑让测试通过。

这非常有意思。其实在以前，我绝不是一个坚定的**测试驱动开发（TDD）**实践者。在写传统业务代码时，我很难强迫自己必须先写一个失败的单元测试，然后再去写逻辑把它调通。但当涉及 AI、涉及大语言模型的对话与 Prompt 修复时，这几乎成了我们团队**唯一的开发工作流**。

我们现在的步骤雷打不动：
1. 针对坏掉的 Conversation 场景，先写一个失败的评估用例（Failing Eval）；
2. 编写代码或调整 Prompt 进行修复；
3. 运行该 Eval 并验证其通过；
4. 跑一遍测试套件里的其他评估用例，确保没有引入 Regression（衰退），然后开启 Pull Request。

在 AI 自动跑测试的这几分钟里，我完全可以起身边去冲一杯咖啡，甚至在另外的终端窗口里并行启动第二个或第三个开发任务，静静等待结果就行。

当它运行完毕后，最核心的一步——也是最需要人类发挥主观能动性的一步——就是去 Review AI 写的代码和 Eval。在此处通常会涉及一些 Prompt 微调。我们要用自己的人类 Taste（品味）去判断 Prompt 修改得是否足够优雅、简练，是否容易维护。

确认无误后，让它把 Pull Request 提交上去。随后我就会在 Perma-Zoom 里跟其他同事喊一声，让他们帮忙 Review。

<details>
<summary>Original English</summary>

**Eddie**: And I'm going to just say uh by the way, I use Whisper flow a lot. I barely type these days. So, I'm going to just say there's a customer issue that is outlined in this GitHub issue. And I'm going to paste in actually just a link to that. Can you please read this issue and come up with a fix for the problem that's outlined here? I'd love for you to first write an eval that fails to show that you can reproduce this issue. Then, come up with a solution and then prove that the solution works by uh showing that the eval now passes. And that's it. Um it's going to actually just read the whole issue. It's going to look at the conversation uh where this problem surfaced. It's going to write an eval that fails and then get that eval to pass. It's interesting. I was never actually a true like test-driven developer. Like I never was like could really get behind like writing a failing unit test first and then writing the code and getting it to pass. But when it comes to like eval stuff, like AI stuff, like it's basically kind of the only way we work now when we're trying to fix a conversation, right? So always write a eval a failing eval first, then write the code to fix it, prove that it works by seeing that the eval passes, and then seeing how the rest of the evals in your suite pass and then open up a PR. So like at this point like I like go grab a cup of coffee or or maybe I'll start a second or third work item in a in a separate cloudcode terminal and and then just wait for it to finish. Uh when it's finished, and this is honestly the part that is the most important, is actually like reviewing the code that it wrote, the eval. In this case, it's probably going to make a prompt change somewhere. Making sure that it's concise. There's like judgment on like what the prompt should look like. And and then and only then asking it to open up a pull request. Then I go to the Zoom perma-zoom and and you know, uh get someone to review this.

</details>

### 领导力转型：亲自下场码代码

**Claire**: 我太喜欢这个工作流了。为了方便听众，我把这个全新开发世界的几个好点子复盘总结一下：

首先，通过快速产出一个 Vibe Code 的原型来在公司内部获取心智共识和立项支持是完全可行的。作为联合创始人和 CTO，你当然自带这种越过条条框框的绿灯权限。但我相信你也会把这种权限下放给你们团队的任何一个人：只要你有很棒的想法，就动脑把它做成原型，大家一起来看。

其次，基于热情组建团队。被这个想法所吸引的人自然而然会聚拢过来，就像形成了一种引力。

第三，把团队规模控制得极小。

<details>
<summary>Original English</summary>

**Claire**: I I love it. So I just want to recap for everybody cuz there's so many good nuggets on how to build something in this in this new world. And so the first thing is it's okay to prototype an idea to get internal buy-in that we should get excited about something new. And you know, you did that. I think you have a lot of permission as as co-founder and leader in this organization. But I think you would extend that permission to anybody on your team, right? If you have a good idea, let's prototype it and look at it. It seems like you gathered a team around who was most excited to build on this. It's something that I sort of heard is you're like, people were leaning in and it's almost like the gravity of who was interested formed some of of the team, which I think is is quite quite fascinating. Um I heard kept the team small.

</details>

**Eddie**: 是的。

<details>
<summary>Original English</summary>

**Eddie**: Yep.

</details>

**Claire**: 抛开所谓的专职岗位划分，抛开所有没必要的会议和文档，就是开干。

<details>
<summary>Original English</summary>

**Claire**: No dogs, no nothing. No no nothing.

</details>

**Eddie**: 没狗，哈哈。

我们当时是特意将团队规模限制在 5 个人以内的。因为 5 人团队的沟通损耗极低，我们能够以难以置信的速度向前狂奔。虽然这种状态不可能永远保持下去——我们现在已经开始往这个团队里塞更多的人、让其他同事也参与进来了——但在最开始的零到一阶段，保持极小的精英化规模是决定项目成败的关键。

<details>
<summary>Original English</summary>

**Eddie**: No dogs. Um Yeah, I mean there were people that wanted they like they really like what was going on and they wanted to like contribute, but we kind of like intentionally kept it as small as possible because um we just were able to move really really fast with a team of five. Now, that's not going to stay like that forever. We're starting to add more people uh to the team and more people are starting to help out. Um but I think it was critical to keep it small in the beginning.

</details>

**Claire**: 很多人可能不爱听我这句话，但我个人的“秘诀”是：要让项目跑得快，最有效的战术就是把闲杂人等从项目组里踢出去。

<details>
<summary>Original English</summary>

**Claire**: No No one likes what I say this, but I say that my secret trick to getting things to move fast is kicking people out of projects.

</details>

**背景笑声**: [笑声]

<details>
<summary>Original English</summary>

**背景笑声**: [laughter]

</details>

**Claire**: 我双手赞成，这绝对是一个行之有效的招数。

<details>
<summary>Original English</summary>

**Claire**: I I go sign. It is an effective tactic.

</details>

**Eddie**: 确实良药苦口。

不过我觉得我们团队也有一个特殊变量，不一定适用于所有公司：那就是在这个团队里，我作为公司的联合创始人直接参与了开发。这意味着我拥有打破 Gusto 内部一切条条框框的隐含特许权。

如果换作别的普通团队，要是敢不写文档、不做 Figma 设计搞、不写 Tech Specs 技术规约就直接动手上线代码，肯定会被管理层警告。所以我最近一直在思考：如何将这种超高吞吐量的开发模式规模化推广到其他普通研发团队？

我的结论是：我们不能指望普通团队能拥有隐含的特权。作为管理层，你必须主动走向他们，明确地授予他们免死金牌，告诉他们：“我们授权你们以这种新方式去工作：免除一切技术文档，不做任何 Figma 设计，不需要写 Specs。你们只需要开着 Perma-Zoom 直接撸代码就行，我们明确授权你们这么做。”

甚至我认为高管可以走得更远，直接把授权变成一种要求：“我们不允许你们用传统方式工作。如果你们还在那里吭哧吭哧写繁琐的架构文档或者画大块的设计稿，反而会吃黄牌警告，因为我们不需要那些。”

当项目组里没有高管或联合创始人坐镇时，管理层必须更加旗帜鲜明地给予这种工作流授权。因为我与很多团队聊过，他们内心非常渴望用这种 AI 结对的工作流来小步快跑，但他们只是觉得自己**“不被允许”**这样做。

<details>
<summary>Original English</summary>

**Eddie**: It is harsh but true. Um Yeah, and I I I do like I think so that I think there's one important um difference here that like applies to this particular project that may not apply to others, right? And it's I think it is honestly the fact that I as one of the company's co-founder was was part of this, right? So, I had like kind of the permission to you know, break all the rules that we created at Gusto, right? Mhm. If any other like teams had ever going to we're going to skip text specs and Figmas, they actually might get a slap on the on the wrist about it. Um and so how do how do I've been thinking a lot about how do you scale this to other teams? And I think um unlike me where the permission is sort of implied, like I think you actually have to go to these teams and say, we we are we want you to work in this way like where you don't do any docs, no Figmas, no text specs. We just want you to have a perma-zoom and like we're giving you permission to do it in that way. And in fact, I would even go even further and say, uh we're not giving you permission to do it in any other way. Like, if you actually produce a doc or Figma, like, you will get a slap on the wrist because we explicitly don't want you to do that, right? That's one important difference. I I I think when you don't have like a co-founder on this team, like, you actually have to be more explicit cuz I have talked to teams that want to do it in this way, but they they just don't feel like they're allowed to.

</details>

**Claire**: 是的。这让我想起了我在 **Coinbase** 的朋友 **Chintan** 曾在他的工程团队里做过的一系列非常极端的效率实验。其中我最喜欢引用的一个是，他走向工程师们对他们说：“把你们的 IDE 全删了。不允许用任何本地集成开发环境，删掉。”

<details>
<summary>Original English</summary>

**Claire**: Yeah. This This reminds me of what my friend Chintan at Coinbase did is he actually he does these extreme experiments with his engineering team. One that's my favorite to reference is he's like, "Delete your IDE. Like, you are not allowed to have an IDE. Delete it."

</details>

**Eddie**: 哈哈，好的。

<details>
<summary>Original English</summary>

**Eddie**: Yeah.

</details>

**Claire**: “直接在网页端或者终端里用 AI 写。另外一个规定是：你们绝对不能用手去修改 AI 吐出来的代码。你们唯一的控制手段就是去写输入、去 Re-prompt（重新提示）。只准给 AI 提要求，不准自己动手改代码。”

这是一种非常有趣的“技术心理学实验”，以此强迫团队跳出固有的舒适区，给他们打破陈规的勇气和动力。

说到这里，我们进入本期的“闪电提问环节”吧。时间有限，我也想赶紧让你回去继续用 Claude 写代码，这才是我们目前最该干的要紧事。

我的第一个闪电问题是：经历过这 10 周后，你真的认为**“文档已死”**了吗？这是未来的唯一出路吗？

<details>
<summary>Original English</summary>

**Claire**: Write code. Um, and his other one that he does is he's like, "You don't touch the outputs of agent code. You only get to touch the inputs. You only get to re-prompt. You don't get to rewrite the code." It's like a very interesting just, um, tech What do they call it? Techno-psychological experiment on on your team to get people ex- get people permission to to work in a radically different way. Um, you know, that that brings me to lightning round. We'll do lightning round. We're almost out of time and I want to get you back to Claude coding, which I think is the most important thing any of us could be doing. So, my first question is, you know, coming off this conversation, do you really think docs are dead? Like, is this the way?

</details>

### 智能体时代的文档与提示策略

**Eddie**: 我认为对于特定类型的项目——比如那些从零到一的项目——技术文档已经完全死掉了。

<details>
<summary>Original English</summary>

**Eddie**: I think for a subset of projects, like kind of more zero to one, I think docs are absolutely dead.

</details>

**Claire**: 哈哈，你知道吗？虽然外界不太了解 **Chat PRD** 的技术细节，但我创立 Chat PRD 的初衷，就是想在产品经理界把 PRD（产品需求文档）彻底干掉。我是带着“消灭 PRD”的终极执念来做这款 PRD 生成工具的。所以我完全赞成你的看法，这绝对是未来的技术趋势。

另外透露一个独家内幕：在我使用新的 **Fable** 模型的体验中，现在有很多文档被写出来，但这根本不是给我看的产品设计文档。我的新心智模型是：**Agent 写文档是给别的 Agent 看的**，根本不是给人类读的，所以我永远不会去阅读它们。文档虽然存在，但它的受众变成了机器，这真是一个非常巧妙的技术架构。

<details>
<summary>Original English</summary>

**Claire**: I I you know what? People don't know this about Chat PRD, but my actual intention with Chat PRD is to be the one in the product management world that legitimately kills PRDs. And And so, I'm like the anti-PRD PRD maker. So, I am all about this. I think this is truly the model. And, you know, even in my experience working with, uh, this breaking news, working with the new Fable model, is there are docs written now that are none of my business. That's what That's my new my new frame of mind is agents can write docs and they are absolutely none of my business and I will never be reading them. And that's actually a very interesting interesting model where maybe docs exist, but they're for the agents, not not for the humans. Um

</details>

**Eddie**: 是的，这太妙了。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, that's awesome.

</details>

**Claire**: 我的第二个闪电问题是关于创始人或技术高管在团队开发中扮演的新角色。我经常在 LinkedIn 上看到有很多工程师吐槽：“救命，我老板每天都在群里发一些他用 Claude 写出来的 Slop（垃圾代码）”，或者“我们 CTO 突然觉得自己能直接在 Main 分支提交 PR 了。”

在行业内，大家对于这种由 AI 带来的、高管插手一线开发的现象其实充斥着焦虑和迷茫。而在很多健康的文化里可能并没有显现。但对于那些存在此类焦虑的研发组织，你作为从高管重回一线写代码（IC 模式）并顺利落地的代表，你会给这些高管和工程师什么建议，来让团队能更兴奋、更健康地去与创始人、CTO 甚至 CEO 一起协同开发？

<details>
<summary>Original English</summary>

**Claire**: My my second question is about this like co-founder executive leader role in building teams. I hear so much or I see on LinkedIn like, "Oh my god, my CEO was like sending over Claude slop or, you know, all of a sudden my CTO thinks that he can he can um commit PRs to to main." And there's actually a lot of I think a combination of like anxiety about the shifting more hands-on role of leadership. And then sort of an leaders who have maybe in the past, depending on your culture, have been like at a little bit more at arms length with hands-on product development now are sitting with the team. And, you know, most most teams that have really healthy cultures don't actually grapple with this and so it seems like you all have a a healthy culture and it creates not so much anxiety. But for for orgs where you can imagine that anxiety exists, what perspective or advice would you give from the leadership side of that equation um that can make teams more excited to build with their co-founders, their CEOs, their CTOs,

</details>

**Eddie**: 我对技术管理者的建议是：**请真正下场，去合并并交付高质量的、经过严格 Review 的生产环境代码。**

千万不要停留在只写原型（Prototype）的阶段。诚然，亲自动手写一个原型去向团队证明“看，这个技术方案完全是可行且成立的”，作为突破重围的第一步确实很有价值，我也曾经犯过类似的错误。但如果你仅仅止步于原型，会让高管对一线研发的各种复杂细节产生误判和“低估”——比如把一个半成品原型打磨成符合线上发布标准的真正工程实体，中间到底需要额外付出多少心血。

因此，如果你是一个管理者，绝对不能在原型做完后就当起甩手掌柜。去亲自经历每一次 Code Review，去把高质量的代码行合并进主干分支。

在过去的 10 周里，我其实走到了一个相当极端的境地：我几乎完全切换回了个人贡献者（IC）的开发模式。在 DX 效率度量上，我甚至达到了我们公司前 5% 的高产行列。我这么做是为了向团队成员证明：我今天不是来跑个 Demo、空口无凭地催你们快写代码的。我用我的实际提交证明，我正和你们在同一条战壕里，把代码一路推到生产发布。

<details>
<summary>Original English</summary>

**Eddie**: I think my advice to leaders is like actually get hands-on in building like production code. Don't just I think it I think it is an important first step to build a prototype and come to your team and be like, "Look, like this is actually feasible and possible, right?" And then like, you know, like that that still that still has value, right? But I do think that and I've made this mistake before in the company where I've like literally done just that. Um it can lead to a little bit of like um, under-appreciation of like the like the actual um, nuances of the work, like how much it more work it takes to actually get something into into real-life production quality like stuff, right? And so I think my advice is like don't just stop there if you're a leader, right? Actually, um, be hands-on in like merging real reviewed like high-quality code. Um, and in my case, I kind of took it to an extreme where I like went into almost IC mode for the past 10 weeks and I was like literally building I'm like 90 like fifth percentile on D DX for the past 3 months. Uh, I and just part of that was I wanted to prove that like I'm not here to just show you like prototypes and and and like tell you that you could move faster, right? I'm going to prove it by actually going and taking it all the way through.

</details>

**Claire**: 我 100% 赞同。在这个时代，高管必须重拾一线硬技能。我常对很多高层开玩笑：“对不住了各位，现在不是靠空洞的领导力演讲、PPT 赋能或者对齐会议来糊弄的时代了。是时候亮出你们的硬实力了。”

管理者必须把双手再次插泥土里——去写文档、调试代码、策划真实的营销活动。这出于两个维度的原因：
1. 你只有和团队坐在同一张长椅上，你才能切身感受到在新范式下团队应该如何协同运转；
2. 如果你日常根本不重度使用各种 AI 原型工具，你根本不可能制定出优秀的 AI 业务战略。你无法理解那些底层交互逻辑、智能体响应的边界，不知道它在哪些场景是神兵利器，在哪些场景会彻底掉链子。一个脱离了日常编码体验去大谈 AI 顶层路线的高管，无异于盲人摸象。

<details>
<summary>Original English</summary>

**Claire**: I just I could not agree more. This is just the moment where everybody has to be hands-on and I tell a lot of executives like, "Sorry, bud. It's time for the hard skill to to show up again, not leadership, inspiration, alignment." It's like get your hands in a in a document, your hands on the code, write a campaign, build something. I think for two reasons. One, you have to be in it with your team to really understand um, how your team should be working. And two, I think it's very hard to build great AI products if you are not spending all your time using AI products right now. It's just like it's very hard to understand the primitives, the user experience, where it can solve problems, where it can't. And so a leader trying to come up with an AI AI product strategy without spending all their time practically using AI products, I think is really hamstrung.

</details>

**Eddie**: 我可以分享一个内幕。Gusto Co-founder 最初的想法，完全源自我自己在家里折腾 Open Claw。我之前听别人提过，我觉得“听起来在自己电脑上运行一个个人智能体助手很酷”。

但如果我只是停留在听别人描述，或者只是通过手机 Telegram 消息和它随便打几个字，我永远无法对它的核心爆发力产生那种**切肤的直观感受**。我必须自己在本地环境里把它跑起来。

正因为我经历了极其繁琐的本地部署（不得不去买一台很难买到的 Mac mini，配置冗长的环境），我们团队才确立了 Co-founder 的立项假设：这套系统必须运行在安全的云端以降低门槛，并且我们将短信（SMS）和 Slack 定为一等公民（First-class）通信渠道。如果我当初没有亲自动手去折腾部署本地的 Open Claw，我是绝对得不到这些根本性的产品洞察的。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, I I think so one thing like that I'll disclose is that the original original idea for Gazo co-founder came from me actually just setting up openclaw myself, right? I had heard about it. Uh and I was like, "Yeah, cool. That sounds like really neat that you can like run an agent personal agent on on your own computer." Um but it really took me setting it up myself and not actually texting with it over Telegram to one like understand like the power of that like viscerally experience it. And then also like, you know, learn what's wrong with it, right? It's incredibly hard to set up. Uh you have to buy a Mac mini which you can't even get today. And that was like one of the the hypothesis of co-founder, right? Like we want it to be safe. Um you can runs in the cloud. But then also that's how we made like SMS and Slack a first-class um communication channel with it, right? And that I don't I don't think I would have gotten that insight if I didn't actually like set up an openclaw in my home myself.

</details>

**Claire**: 极其赞同。我认为每一位技术管理者都要经历这样一个“被 AI 震撼的时刻”。当我最开始跑通 Open Claw 的那一瞬间，我立马转头跟我丈夫说：“天呐，我感觉又回到了当年第一次看见 ChatGPT 的震撼时刻。”它从根源上彻底重构了我对产品的认知，这在以前是前所未有的，甚至连 Cursor 都没有像它那样彻底地重构我的世界观。

<details>
<summary>Original English</summary>

**Claire**: I I love it. I mean, I think every leader needs to feel feel the claw um for that exact reason. I when I started using open claw, I remember I turned to my husband and like, "Oh my god, I'm having a chat GPT moment." In terms of it just changed my mental model of what product could be in a way that I just hadn't felt or experienced prior to like even since um chat GPT first came out. Even Claude code didn't like change my world in the same way that that open claw really did.

</details>

**Eddie**: 确实，虽然经常听到别人鼓吹这些技术是多么疯狂的创新，但因为现在媒体上的通稿和天花乱坠的宣传实在太多了，难免会让人产生免疫和疲劳。你只有抛开喧嚣，自己亲手去写两行，你才能真正拥有那种顿悟的体感。

<details>
<summary>Original English</summary>

**Eddie**: And and you probably heard of other people talking about that that like how it's like such a crazy like innovation, right? But then you don't really you That's That's the problem like there's so much press out there and like so much hyperbole that like you kind of become numb to it. So you do kind of have to experience it yourself, I think.

</details>

**Claire**: 完全一致。最后一个问题，问完就放你走。当 Claude 没有写出好的测试用例、没有听懂你的需求，或者你明知道要废掉这个 PR 的时候，你会采用怎样的 Prompt 技巧来把模型重新拉回正轨？

<details>
<summary>Original English</summary>

**Claire**: Yep, completely agree. Okay, last question and then we will get you out of here. You know, when when Claude is not writing a great eval, when it's not listening, when you know you're about to have to trash a PR, what is your prompting strategy to get it back on track?

</details>

**Eddie**: 我在性格上是个比较温和、讨厌冲突的人。所以我在和我的 Claude 交流时也是极其有礼貌的。我会非常客气地问它：“你为什么要采用这种方式来实现呢？你能否请考虑一下这个方案？”

我发现其实这有一定的实际效益。模型在设定上往往非常顺从，它会倾向于顺着你的话说。但我实际上希望我的 Claude 来挑战我，给我提供更好的解决方案和更好的技术实践。所以我采用这种开放、客气的询问口吻，能更容易引导它对我的架构方案进行“推敲和反驳”。

<details>
<summary>Original English</summary>

**Eddie**: I'm naturally a very polite person.

</details>

**背景笑声**: [笑声]

<details>
<summary>Original English</summary>

**背景笑声**: [laughter]

</details>

**Eddie**: 比较温和。所以我和我的 Claude 沟通挺客气的。我会礼貌地问它：“你能否考虑一下这个方案？”我发现这样其实更有效，因为模型有很强的顺从倾向，而我其实希望它反驳并挑战我，提出更好的技术选择。所以我更喜欢留下开放性的礼貌提问，给它推翻我的空间。

<details>
<summary>Original English</summary>

**Eddie**: Uh non-confrontational. But I and so I'm pretty nice to my Claude. I kind of like, you know, ask it nicely why did it do this way or like, could you please consider this? And actually I I for me I don't know if this is true, but I think there's a actual like practical benefit of it. I find that AI is so differential and it just kind of like defaults to doing what you want it to do, but I actually want mine to challenge me, right? And like give me different uh ways of doing things that might be better, ways of building things that might be better. Um so I have some for some reason I just feel like kind of being polite, leaving it open-ended. Uh if you think this is a good idea, could you try this? Like cuz I kind of wanted to a little bit more of like pushback.

</details>

**Claire**: 哈哈，大家确实都很礼貌。除非它实在跑得太偏了，我才会使用比较强硬的态度。哪怕可能会浪费不少 token 和地球资源，我也依然会这么干。好了，Eddie，今天聊得非常开心。我们在哪里可以找到你和你们团队的产品？听众们该如何提供帮助？

<details>
<summary>Original English</summary>

**Claire**: Yep. Yep. Love it. Uh you know, most people are are very polite. I'm I'm often very polite unless it's gone real off the track. And then what I use is a 15 oh, no. I don't I'm wasting tokens, you know, it costs a drop of water, but I do it anyway. All right. Well, Eddie, this has been so fun. Where can we find you and how can we be helpful to you and the team?

</details>

**Eddie**: 好的，大家可以前往 `gusto.com/cofounder` 找到 Gusto Co-founder。目前我们开启了等待名单，感兴趣的听众可以去注册排队，通常几天内就会开放测试权限。欢迎大家来试用并向我们疯狂吐槽，期待大家的反馈。

<details>
<summary>Original English</summary>

**Eddie**: Yeah, you can find Gusto Co-Founder at gusto.com/cofounder. Um we have a waitlist, so if you're interested in it, please sign up for it. We'll give you access probably within a few days. Um and check it out. Give us feedback.

</details>

**Claire**: 没问题。我作为 Gusto 的忠实企业客户，我要向你申请开个后门直接进 Beta 体验。我会给你提一堆长长的反馈，说不定顺便还会给你们提交几个 PR。

<details>
<summary>Original English</summary>

**Claire**: Great. I'm a I'm a very happy Gusto customer, so I'm going to ask you to to feature flag me into into the beta and I will send you all the feedback and hopefully some PRs will come out of it.

</details>

**Eddie**: 随时欢迎，求之不得。

<details>
<summary>Original English</summary>

**Eddie**: I would love it.

</details>

**Claire**: 再次感谢 Eddie 抽空来到我们的节目。

<details>
<summary>Original English</summary>

**Claire**: Great. Well, thanks for joining, Eddie.

</details>

**Eddie**: 谢谢 Claire。

<details>
<summary>Original English</summary>

**Eddie**: Thanks, Claire.

</details>

**Claire**: 非常感谢大家的收看。如果你喜欢这一期节目，请在 YouTube 上一键三连，或者在下方评论区写下你的任何想法。我们的播客也同步登陆了苹果 Podcast、Spotify 以及各大播客平台。如果能给我们留下五星好评，将极大帮助更多人发现这档节目。大家也可以访问 `howiaipod.com` 查看所有往期节目并了解详情。我们下期节目再见。

<details>
<summary>Original English</summary>

**Claire**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. [music] Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>