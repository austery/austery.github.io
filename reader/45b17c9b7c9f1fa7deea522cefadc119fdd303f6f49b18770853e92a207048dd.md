---
author: AI Engineer
date: '2026-11-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=MDI81OaZAD4
speaker: AI Engineer
tags:
  - coding-agent
  - engineering-culture
  - collaboration
  - developer-tools
title: Ramp 内部协作编码智能体 Inspect 的演进与工程文化
summary: Ramp 工程师 Zach 介绍了内部自研协作编码智能体 Inspect 的演化历程。Inspect 承担了 Ramp 约 75% 的代码编写与发布，其演进遵循打破信息孤岛、公开透明建立信任以及共同构想三大文化经验，并催生出代码审查等扩展智能体。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Zach Bruggeman
  - Dylan Garcia
companies_orgs:
  - Ramp
products_models:
  - Inspect
media_books: []
status: evergreen
---
### 介绍 Inspect 与 Ramp 的工程演进

我叫 Zach，是 Ramp 的一名工程师。我非常高兴能向大家介绍一下，Ramp 在今年如何借助我们的机器人伙伴 Inspect 来演进其工程文化。

<details>
<summary>Original English</summary>
My name is Zach and I'm an engineer at Ramp. I'm just really excited to tell you all a bit about how Ramp has evolved its engineering culture this year through the help of our robotic friend Inspect.
</details>

简单介绍一下，Inspect 是 Ramp 的协作编码智能体。大约一年前，我们决定押注构建自己的编码智能体，让每个会话都在远程运行，并且完全支持多人协作。Inspect 可以与你以及你的团队协同工作，无论是在 Inspect 本身、Slack、Linear，还是在我们的任何其他集成中。现在，它的能力已经远远超出了单纯写代码的范畴，内置了设计原语、审查智能体和验证流程，让任何构建者都能完全在 Inspect 内部完成从提示词到代码发布的全过程。Inspect 还与我们公司层面的所有集成相连接，因此每个人都能自动连接到最重要的数据和工具，无论是遥测、数据库，还是任何其他可用工具。

<details>
<summary>Original English</summary>
As a quick introduction, Inspect is Ramp's collaborative coding agent. About a year ago, we decided to take a bet on building our own coding agent with every session running remotely and being fully multiplayer. Inspect can work alongside you and your team, whether that be an Inspect itself, Slack, Linear, or any other of our integrations. And now it goes far beyond just writing the code with built-in design primitives, review agents, and verification flows that let any builder go from prompt to shipping all inside Inspect. Inspect is also connected with all of our integrations company-wide, so everyone's automatically connected to the to the data and tools that matter most, whether that be telemetry, databases, or any of the other tooling available.
</details>

通过这种方式，我们现在看到 Ramp 大约 75% 的代码都是由 Inspect 编写并发布的。

<details>
<summary>Original English</summary>
Through this, we now see around 75% of all of Ramp's code being being written and shipped by Inspect.
</details>

年初我们开始公开分享 Inspect 时，技术本身是比较新颖的部分——在 5 秒内启动沙盒、接入所有内部上下文、让智能体在多人协作环境中共同工作。人们对底层管道有许多疑问。但现在，随着这些概念得到广泛采用，且 Inspect 本身也已成为推向市场的产品，技术已经不再像曾经那样是个障碍了。

<details>
<summary>Original English</summary>
When we started sharing Inspect publicly at the start of the year, the technology itself was the more novel part, spinning up sandboxes in under 5 seconds, wiring up all that internal context, having agents work together in a multiplayer setting. People had a lot of questions about the plumbing. But now with much broader adoption of these concepts and Inspect itself now being a product on the market, the technology isn't nearly the barrier that it once was.
</details>

相反，我想从另一个角度来谈谈：围绕 Inspect 建设文化所学到的经验，以及你可以带走哪些启发，去激励与你共事的人员和团队。

<details>
<summary>Original English</summary>
Instead, I want to talk about the other angle, the lessons we've learned around building a culture around Inspect and what you can take away to inspire the people and teams that you work with.
</details>

我今天不会过多讨论 Inspect 的那些技术细节，但如果你对此感到好奇，可以阅读我们的博客文章，或者看看 Pragmatic Engineer 几个月前与我们一起做的深度剖析。

<details>
<summary>Original English</summary>
Uh I'm not going to talk as much about those technical aspects of Inspect today, but if you are curious about that, you can read our blog posts or take a look at Pragmatic Engineers deep dive that they did with us a few months ago.
</details>

你也可以关注我的好兄弟 Dylan Garcia。他一直在社交媒体上努力耕耘，自从我们发布 Inspect 以来，他也发了很多非常棒的关于 Inspect 的见解。所以，向 Dylan 致敬，请大家去关注他。

<details>
<summary>Original English</summary>
You can also follow my boy Dylan Garcia on He's on his social media grind, but he's also been posting a ton of really great Inspect insights since we've launched it. So, shout out Dylan. Please go and follow.
</details>

### 第一课：打造打破信息孤岛的工具

在 Ramp 工作的一点是，它确实会让你开始从节省时间和金钱的角度来思考一切。尽管我认为理解与你共事的系统并理解你的工具如何运作是很重要的，但如果你是一个几百人或几千人的组织，每个人都必须经历比方说 15 分钟的配置，一旦你把这个时间乘以整个组织的人数，那就是在非常死板机械的工作上损失了数天时间。

<details>
<summary>Original English</summary>
One thing about working at Ramp is that it really makes you start thinking about everything through the lens of saving time and money. And although I think it is important to understand the systems that you work with and understand how your tooling works, if you're a multi-hundred or multi-thousand person organization and everyone has to go through say 15 minutes of setup, once you start multiplying that across an organization, this is days lost for what is very rote work.
</details>

然后，如果你考虑到最佳实践和配置智能体的新方式在前沿演进得有多快，你就会意识到这种配置成本并不是一次性的。

<details>
<summary>Original English</summary>
Then, if you consider how fast the frontier moves here on best practices and new ways to set up an agent, you realize this setup cost isn't just one time.
</details>

更不用说，这些进展并不总是平均传播开来。因此，现在你花费了不确定数量的时间和精力在维护上，知识却没有均匀分布，从而导致整个组织出现参差不齐的结果。

<details>
<summary>Original English</summary>
Not to mention, these advancements won't always spread equally. So, now you have an indeterminate amount of time and effort spent on this maintenance without an equal spread of knowledge leading to disparate outcomes across an organization.
</details>

虽然在个人层面上你可以将这视为一种优势，但当你想要赢的时候，你需要让每个人都发挥出最佳状态。

<details>
<summary>Original English</summary>
While you can perceive this as an advantage on an individual level, when you're trying to win, you need everyone on your A-game.
</details>

所以，这是我们的第一课：**打造打破信息孤岛的工具**。

<details>
<summary>Original English</summary>
So, this was our first lesson. Build tools that kill information silos.
</details>

当我们发现行之有效的模式或让每个人受益的工具时，我们可以立即将其推送到全公司。如果你想花时间调整自己的配置，那没问题，但 Inspect 始终可以作为一个非常稳固的基准线。我们的发现是，我们从未需要强制使用 Inspect，因为它的基准线地位减少了人们一直去寻找自己定制配置的需求。

<details>
<summary>Original English</summary>
When we found patterns that worked well or tools that benefited everyone, we could push it to our entire organization immediately. If you want to spend time tweaking your own setup, that's fine, but Inspect is always available as a very solid baseline. And what we've found is that we've never needed to mandate usage of Inspect because it existing as this baseline reduced the need for people to reach for their own setups all the time.
</details>

我认为让这一点同样强大的部分原因在于，这个行业的现实情况是，作为个体，你不太可能在所有事情上始终掌握与智能体协作的绝对最佳方式。

<details>
<summary>Original English</summary>
Part of what I think makes this powerful as well is that the reality of this industry is that it's unlikely that you as an individual always know the absolute best way to work with agents across everything.
</details>

即使紧跟这些发展是你的全职工作，我们所有人也都会遗漏事物、持有偏见并存在盲点。因此，Inspect 的设计中有一部分就是全公司只有一个唯一的 Inspect。

<details>
<summary>Original English</summary>
Even if keeping up with this is your full-time job, we all miss things, hold biases, and have blind spots. So, part of the design of Inspect is that there's just one single Inspect for the whole company.
</details>

当有人发现了更好的使用方式，或者对如何使其更好地契合自己的工作有了想法时，我们能够将其带给全公司。

<details>
<summary>Original English</summary>
When people figure out better ways to use it or have ideas for what would make it better for the work they do, we're able to bring it to the entire company.
</details>

其中最棒的部分在于，对于大多数改动而言，对其他所有人都是无感的。你只需像往常一样继续使用 Inspect，就能享受到大家随着时间推移所带来的改进。

<details>
<summary>Original English</summary>
The best part of this is that for most changes, this is invisible to everyone else. You just keep using Inspect as you normally would and benefit from the improvements that everyone's making over time.
</details>

而我们的发现是，针对 Inspect，我们真的不需要举办那些正式的、坐下来的“如何有效使用 AI”培训会议。由于默认情况下每个 Inspect 会话在公司内部都是公开的，在公开状态下工作实际上比在私下更容易。因此，大家会默认在公开场合工作，你可以通过在自己已经身处其中的频道里观察队友如何使用来学习如何使用它，而你的队友也可以向你学习。你甚至可以直接让 Inspect 浏览他们最近的会话，告诉你他们是如何工作的、他们如何组织提示词，或者他们如何拆解棘手的问题。

<details>
<summary>Original English</summary>
And what we've found is that we really don't have to run these formal sit down here's how you use AI effectively training sessions for Inspect. With every Inspect session being public within the company by default, it's actually easier to work in public than in private. As such, you default to working in public and you can learn how to use it by watching how your teammates use it in the channels that you're already in, and your teammates can learn from you. You can literally ask Inspect to go through their recent sessions and tell you about how they work, how they structure prompts, or how they break down gnarly problems.
</details>

我认为这不仅对 Ramp 的构建者有所帮助，对 Inspect 团队本身也是如此。

<details>
<summary>Original English</summary>
I I think this is not just been helpful for the builders at Ramp, but also for the Inspect team itself.
</details>

我们经常看到大家以我们最初未曾想象到的方式使用 Inspect。这随后便启发了我们应该朝什么方向构建，无论是针对常见模式提供更多原生原语，还是发现缺少工具和数据的地方。

<details>
<summary>Original English</summary>
We frequently see the way that people use Inspect in ways that we didn't originally imagine. This then informs what we should build towards, whether that should be more native primitives for common patterns or where tools and data are missing.
</details>

总而言之，它创造了一个自我维持的循环，在这个循环中，通过观察人们已经使用 Inspect 取得了什么成果，我们能够朝着让 Inspect 最为成功的方向去构建。

<details>
<summary>Original English</summary>
All in all, it creates this self-sustaining loop where we're able to build towards what makes Inspect the most successful by seeing what people are already achieving with Inspect.
</details>

### 第二课：在公开透明中建立信任

这引出了我们学到的第二课：**一切都关乎建立信任**。我认为可以公平地说，采用智能体驱动的编码，对今年每位工程师来说都是一次巨大的信任建立过程。

<details>
<summary>Original English</summary>
This feeds into the second lesson that we've learned. It's all about building trust. I think it's fair to say that adopting agentic driven coding has been a massive trust building exercise for every engineer this year.
</details>

模型在编写高质量代码方面变得更加称职起到了帮助作用，但这其中有很大一部分只是在学会去信任智能体构建出的东西。

<details>
<summary>Original English</summary>
It's helped that the models have become more competent at writing high quality code, but there's a large part of this that's just learning to trust what an agent builds.
</details>

对工具建立信任，很大程度上来自于向其他人学习。毕竟，这也是我们大多数人来到这里的原因，对吧？你想聆听你尊敬的人——或者至少我希望你尊敬的人——向你讲授他们学到的东西。但是，如果我们把知识语料库局限在那些在公开演讲中获得异样乐趣的人身上，我们依然无法了解全貌。

<details>
<summary>Original English</summary>
So much of building trust in tools comes from learning from other people. After all, that's why most of us are here, right? You wanted to listen to people you respect, or at least I hope you respect, teach you about the things that they learned. But if we limit our corpus of knowledge to just those who find the perverse enjoyment in public speaking, we're still not getting the full picture.
</details>

这种知识分享的民主化作为一个概念让我着迷。我们能否构建出本身就能分享每个人的知识的系统，而不是围绕着少数选拔出来的领导者聚集？

<details>
<summary>Original English</summary>
This democratization of knowledge sharing is just fascinating to me as a concept. Instead of grouping around a select few leaders, can we build systems that inherently share the knowledge of everyone?
</details>

这就是 Inspect 所致力于构建的方向。每当有人用 Inspect 发布了东西，大家都可以直接在所完成的工作上看到它。会话本身就是一个易于分享的载体，是这项改动是如何产生的活生生的人工制品。

<details>
<summary>Original English</summary>
This is what Inspect has built towards. Every time someone ships something with Inspect, people can see it right there on the work you've done. The session itself is an easy to share. It's living artifact of how that change came to be.
</details>

当提交 PR 时，任何审查人员都不只是看到扔过来的 400 行代码差异然后听天由命。他们能看到你进行过的确切对话、Inspect 使用过的所有工具、修改前后的屏幕截图，甚至是验证智能体在浏览器中点击应用程序以证明其工作经得起检验的录屏视频。

<details>
<summary>Original English</summary>
When a pull request goes up, anyone reviewing it doesn't just see the 400 line diff dropped over the wall and hope for the best. They can see the exact conversation that you had, all the tools that Inspect used, before and after screenshots, or even a video recording of the verification agent clicking through the app in the browser to prove its work holds up.
</details>

这使得不仅展示修改了什么，而且展示为什么你可以信任它变得毫不费力。这也更容易让那些平时不常合作的人融入进来。

<details>
<summary>Original English</summary>
It makes it effortless to show not just what changed, but why you can trust it. It also just makes it easier to bring people you don't work with all the time into the fold.
</details>

关于这一点有个有趣的瞬间：那是在二月份，我们的一位工程师 Andrew 报告了 Inspect 中的一个错误。所以，我很自然地使用了 Inspect，让它去排查。

<details>
<summary>Original English</summary>
A fun moment on this one, it was back in February, one of our engineers, Andrew, reported a bug in Inspect. So, naturally, I reached for Inspect and asked to investigate.
</details>

有趣的是，尽管 Inspect 接入 DataDog 已经有一段时间了，但我们才刚刚完成 Inspect 本身的插桩埋点。

<details>
<summary>Original English</summary>
What's funny here is that although Inspect had access to DataDog for a while, we'd only just finished instrumenting Inspect itself.
</details>

我是说，Inspect 主要是由前端产品工程师构建的，因此链路追踪对我们来说是一个有点陌生的概念。但无论如何，这都是我们对 Inspect 进行检验的绝佳时机。结果 Inspect 说，是插桩埋点导致了该错误。是的，正是让我们能够调试此错误的插桩埋点本身引起了这个错误。

<details>
<summary>Original English</summary>
I mean, Inspect was primarily built by front-end product engineers, so tracing is a little bit of a foreign concept for us. But in any case, it was a great time for us to put it to the test for Inspect. And Inspect says the instrumentation was causing the error. Yes, the very instrumentation that was letting us debug this error was actually causing this error.
</details>

所以，我和 Dylan 当时并没有完全被这个机器人说服。而 Andrew 就觉得无所谓，我用 Claude Code 就行。虽然我们没有强制要求使用 Inspect，但就个人而言，这可不是我想听到的话。

<details>
<summary>Original English</summary>
So, Dylan and I were not exactly convinced by the robot here. And Andrew is just like, whatever, I'll use Claude Code. And and while we don't have a mandate to use Inspect, I mean, personally, these were not the words I wanted to hear.
</details>

所以，现场没有人真正相信任何人。

<details>
<summary>Original English</summary>
So, nobody here is really trusting anybody.
</details>

我和 Dylan 不相信机器人的解释。

<details>
<summary>Original English</summary>
Dylan and I don't trust the robot's explanation.
</details>

Andrew 不相信我们能做出有用的东西。至于 Inspect，我……我不知道 Inspect 会不会信任任何人，但没关系，这没关系。

<details>
<summary>Original English</summary>
Andrew doesn't trust us to build something that works. And Inspect, well, I I I don't know if Inspect trusts anyone, but that's okay. That's okay.
</details>

但因为这一切是在公开场合共同进行的，我们继续追查。Dylan 让 Inspect 查看正在使用的遥测库代码，看看这是不是之前就存在但由于缺乏可见性而没被发现的问题，因为按理说现在编码问题都已经被解决了，不可能存在由我们引入的错误。

<details>
<summary>Original English</summary>
But because this is happening together in public, we keep prodding at it. Dylan asks Inspect to look through the code of the telemetry library using and see if this was just something that was happening before without visibility because surely by now coding has been solved and there can't be bugs that we introduced.
</details>

这一次它返回了更具体的内容：otel 库调用了 fetch，但从未读取或取消响应体。这在当时只是 Cloudflare 平台的一个限制，尽管它发生在一个专门为 Cloudflare workers 制作的库中。但这种事确实会发生，毕竟这个库是在 AGI 之前编写的。

<details>
<summary>Original English</summary>
And this time it comes back with something a bit more specific. The hotel library calls fetch, but it never reads or cancels the response body. This was just a Cloudflare platform limitation at the time, albeit happening in a library specifically made for Cloudflare workers. But that happens. This library was written pre-AGI after all.
</details>

此时，我们让 Inspect 打一个补丁。它更新了导出器，显式地取消响应体。在部署过程中我们在帖子中稍微咕哝了几句，但我们看到部署之后，就再也没有出现过任何错误了。所以太棒了，Inspect 修复了一个错误，在当下这一点本身并没有什么特别的，但在这个帖子中正在上演一个重要得多的故事。

<details>
<summary>Original English</summary>
At this point, we ask Inspect to make a patch. It updates the exporter to explicitly cancel the response body. We grumbled in the thread a bit while it was deploying, but we see after it deployed, there haven't been any errors since. So great. Inspect fixed a bug, which at this point that's nothing special in itself, but there was a much more important story playing out in this thread.
</details>

在 Inspect 出现之前，像这样的报告可能会被确认收到，建一个工单，然后我们中的一个人私下去调试它。Andrew 稍后可能会收到一条说明问题已修复的消息，但有趣的工作原本都会在私下完成。

<details>
<summary>Original English</summary>
Before Inspect, a report like this might have been acknowledged, a ticket filed, and then one of us would have gone away to debug it. Andrew might have received a message later saying it was fixed, but the interesting work would have been done in private.
</details>

然而现在，在公开场合完成所有这些工作变得更加容易。

<details>
<summary>Original English</summary>
Now though, it's easier to do all of this in public.
</details>

因此，Andrew 自然而然地开始参与进来，想要发表自己的想法和经验。随后在同一个帖子中，引发了关于 Inspect 如何为其他工作赋能的构想。这一切都不需要任何督促或协同工作的压力。相反，就像是“噢，这些家伙在做很酷的事情，我们可以一起在这上面做”。

<details>
<summary>Original English</summary>
And as such, Andrew naturally starts becoming engaged, wanting to chime in with his thoughts and experiences. And then in that same thread, this leads to ideas coming up about how Inspect could power other work. And none of this required any prodding or pressure to work together. Instead, it was just like, oh, these guys are doing something cool and we could work on it together.
</details>

所以在短短一个小时内，我们从一个经历着损坏体验且持怀疑态度的用户，转变为一位想要共同构建的积极参与的同事，并获得了一个更加稳定的 Inspect。

<details>
<summary>Original English</summary>
So in the span of an hour, we go from a skeptical user with a broken user experience to an engaged colleague wanting to build together and a more stable Inspect.
</details>

### 第三课：打破孤狼思维，共同构想更大蓝图

因此，一旦你拥有了一个在第一天就为每个人提供最佳配置且没有信息孤岛的工具，并且建立了将创新凝聚在一起的信任体系，接下来会发生什么？

<details>
<summary>Original English</summary>
So once you have a tool that gives everyone the best setup on day one with no information silos and you've built a system of trust that brings innovation together. What happens next?
</details>

这是我想分享的最后一课。我认为剩下的唯一事情就是**共同构想更大的蓝图**。

<details>
<summary>Original English</summary>
This is the last lesson I want to share. I think the only thing left is to think bigger together.
</details>

今年让我感到痛心的一件事，是对“孤狼”操盘手产生了如此多的崇拜。在 AI 的帮助下，我们每个人在个体层面能做更多的事情，这固然很棒，但在我看来这绝不能是终局。

<details>
<summary>Original English</summary>
Something that's pained me this year uh is how much reverence has been built for the lone wolf operator. It's great that we can all do more individually with the help of AI, but this can't be the endgame in my opinion.
</details>

如果我们不向外构建、不与他人协作，并不继续分享我们取得的进展和心得，我认为这一切最终都会内卷坍塌。我们会只将自己视为唯一的目标受众，而且我们无法通过考量他人的视角和经验来获得成长。

<details>
<summary>Original English</summary>
If we don't build outwards, collaborate with other people, and continue to share the progress and learnings we make, I think this is all going to collapse in on itself. We'll only consider ourselves as our target audience, and we won't grow through the consideration of others' perspectives and experiences.
</details>

这并不是说我对此全持悲观论调。希望我们所有人都在这里，正是连接价值的明证。

<details>
<summary>Original English</summary>
This is not to say I'm all doom and gloom about this. The fact we're all here hopefully is a testament to the value of connection.
</details>

但更重要的是，我认为我们可以塑造我们的工具，使这些连接能够比以往更加茁壮地蓬勃发展。

<details>
<summary>Original English</summary>
More importantly though, I think we can shape our tools to enable these connections to flourish even stronger than before.
</details>

我讲述的关于 Andrew 的那个故事已经在 Ramp 内部上演了无数次。坦白说，这对我而言可能是关于 Inspect 最鼓舞人心的事情。

<details>
<summary>Original English</summary>
That story I told about Andrew has played out so many times within Ramp. It's probably the most inspiring thing about Inspect to me, honestly.
</details>

当然，它是一个编码智能体，但引人注目的是，它已经成为文化的一部分。Ramp 的每个人都知道它的面孔。我们在节假日给它打扮，随着时间的推移加入彩蛋，我们随着 Ramp 本身的演进而演进它。正如任何 Ramp 工程师都可以告诉你的那样，并不是所有的迭代都尽善尽美，但我确实认为每一次迭代都是大家共同完成的。

<details>
<summary>Original English</summary>
Sure, it's a coding agent, but remarkably, it's become part of the culture. Everyone at Ramp knows its face. We dress it up on holidays. We throw in Easter eggs over time, and we evolve it as Ramp itself has evolved. Not all iterations have been perfect, as any Ramp engineer could tell you, but I do think every iteration has been together.
</details>

回到今年早些时候，Inspect 根本没有如今拥有的这么多功能。一个很好的例子就是它的代码审查智能体。在此之前，我们使用过各种现成的代码审查产品，并经常在它们之间轮换以寻找合适的产品。

<details>
<summary>Original English</summary>
Going back to earlier this year, Inspect didn't have nearly the amount of functionality it has today. Uh great example is its code review agent. Before this, we were using various off-the-shelf code review products, frequently rotating between them to find a good fit.
</details>

但在某个时刻，两位工程师 Daniel 和 Pranjal 意识到我们或许可以自己构建它，因为 Inspect 已经拥有从各种来源触发的自动化触发器，包括在创建 PR 时。

<details>
<summary>Original English</summary>
At some point though, a couple engineers, Daniel and Pranjal, realized that we could probably build it ourselves, as Inspect already had automation triggers that fired from a variety of sources, including when a pull request was opened.
</details>

仅凭我们已经构建好的基础，他们就开始着手构建 Ramp 另一个备受喜爱的智能体——Review Buddy。而最酷的地方在于，非常像 Inspect 自身作为业余项目的起源一样，这些人在做这件事情时，不需要寻求构建许可。他们只是挑战自己去构建更好的东西，利用 Inspect 走得更快，并迅速构建出了一个对全 Ramp 来说都更好的智能体。

<details>
<summary>Original English</summary>
With just what we built already, they got to work building another beloved agent at Ramp, Review Buddy. And what was so cool about this is that, much like Inspect's own origins as a side project, these were working on this. They didn't need to ask for permission to build it. They just challenged themselves to build something better, used Inspect to move faster, and quickly built an agent that was better for all of Ramp.
</details>

这确实促使我们在做 Inspect 的人以不同的方式思考 Inspect。在那个时间节点，我们对于 Inspect 所谓的“仅仅”是一个编码智能体是相当满意的。但一旦我们看到了其他人正在推动它去做的事情，这让我们开始思考 Inspect 如何才能形成完整的闭环。

<details>
<summary>Original English</summary>
This really did force us working on Inspect to think about Inspect differently. At that point in time, we were pretty okay with Inspect quote unquote just being a coding agent. But once we saw what others were pushing it to do, it got us thinking about how Inspect could become full circle.
</details>

如果这种推动没有自然发生，我认为 Inspect 团队要达到那个阶段需要花费长得多的时间。

<details>
<summary>Original English</summary>
If this push didn't happen naturally, I think it would have taken the Inspect team a lot longer to get there.
</details>

这就是我所说的共同构想更大蓝图。

<details>
<summary>Original English</summary>
This is what I mean about thinking bigger together.
</details>

特别是随着模型性能的不断提升，现在正是推动自己和身边的人去构想更大蓝图的时候。我鼓励大家在接下来的一周里花点时间去问问和你共事的每个人：“有什么事情是我们一直想做但还没去做的？”

<details>
<summary>Original English</summary>
Especially with the continued improvements in model performance, now's the time to push yourself and the people around you to think bigger. I encourage all of you to take some time in this coming week to ask everyone that you work with, what have we been waiting to do that we haven't done yet?
</details>

一旦你找到了那些事情，尝试着一起去构建它们。真的不再有不去尝试的借口了。你拥有与其他人相同的模型访问权限。但你必须从某个地方开始。我相信在解锁成功方面有巨大的潜力，不仅为你自己，也为你身边的人。

<details>
<summary>Original English</summary>
And once you've found those things, try to build them together. There's really not an excuse to not just try anymore. You have access to the same models as everyone else. But you have to start somewhere. And I believe that there is so much potential in unlocking wins, not just for yourself, but for the people around you.
</details>

Inspect 本身就是这样诞生的。不仅因为这是我想构建的以及 Jason 想构建的东西，更是出于想为一支我真正热爱且真正尊敬的团队构建某些东西的愿望，让他们的工作变得更有趣一点。

<details>
<summary>Original English</summary>
Inspect itself was born this way. Not only as something that I wanted to build and Jason wanted to build, but out of a want to build something for a team that I truly love and truly respect that would just make their jobs a little more enjoyable.
</details>

现在，如果你想使用一款体现了我们所学到的所有这些经验的编码智能体，我很高兴地宣布，Inspect 现在已在 Ramp 之外提供。如果你访问 inspect.com/aie，我们会在候补名单上优先考虑你和你的团队。我们处理这个候补名单的速度其实相当快，所以敬请期待我们的消息。

<details>
<summary>Original English</summary>
Now, if you'd like to use a coding agent that has embodied all these lessons that we 've learned, I'm happy to say that Inspect is now available outside of Ramp. If you go to inspect.com/aie, we'll prioritize you and your team on the wait list. We're actually moving through this wait list pretty quickly, so expect to hear from us soon.
</details>

除此以外，我希望大家喜欢了解我们的机器人朋友 Inspect。如果这些话题引起了你的兴趣，欢迎在此处或在 X 上与我联系。除此之外，非常感谢大家的倾听。

<details>
<summary>Original English</summary>
But otherwise, I hope you've enjoyed hearing about our robotic friend Inspect. If these topics interest you, feel free to reach out here or on X. But otherwise, thanks so much for listening.
</details>