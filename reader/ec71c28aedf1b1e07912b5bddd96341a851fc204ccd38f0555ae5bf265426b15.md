---
author: AI Engineer
date: '2026-11-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=v0UkV5qS9E4
speaker: AI Engineer
tags:
  - ai-agent
  - financial-technology
  - code-generation
  - enterprise-software
title: Compound AI：为何我们要为金融 AI Agent 从头重写微软 Office
summary: 前 Coatue 副总裁、Compound 创始人分享了金融机构落地长程 AI Agent 的核心挑战与解法。针对买方投资流程对多方协作、海量上下文处理及高保真执行的需求，团队引入邮件级多人交互，用 Agent 编写 800 万行代码重构无头 Office 引擎，并借助代码 Agent 群并行检索，推动金融流程从 Copilot 转向自主 Autopilot。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Yijia Liang
companies_orgs:
  - Compound
  - Coatue
products_models:
  - Microsoft Office
  - IronCalc
media_books: []
status: evergreen
---
### 为什么个人 AI Agent 的成功无法直接复制到机构金融？

[music]

>> 我在上辈子曾是一名分析师。我在 Coatue 担任了大约 3 年的副总裁，专注于后期非公开市场软件投资。我在 Excel、PowerPoint 上花费了太多时间，深夜都在做这类工作，因此我决定离开，开始打造能够取代我过去工作的工具。

<details>
<summary>Original English</summary>
[music]

>> I was previously an analyst in a previous life. I was a vice president at Coatue for about 3 years specializing in late stage private software investments. Spent way too much time in Excel, PowerPoint, and late nights doing that type of work and so decided to split and start building tools to replace my old job.
</details>

快速举手表决一下，在场的各位有多少人在过去一天里使用过 Muser Instinct？

好吧，我原本以为会有更多人举手，不过也许大家只是不好意思举手。

那么，有多少人认识能在金融领域完全把工作委托给 AI——也就是完全放手让其自主运行的分析师？好的，有一个。但这要少得多。

<details>
<summary>Original English</summary>
Quick show of hands, how many people in here have used Muser Instinct in the last day?

All right, I expected more hands, but uh maybe people are too shy to raise them.

And how many people know an analyst in finance that fully delegates their work to AI, like fully hands-off running autonomously? All right, one. But a lot fewer.
</details>

我认为如果你思考这个问题：为什么个人 Agent 会在过去 3 个月里爆发？在内部，我们总结出了三个主要答案。

第一，可靠的后台 Agent。你可以委托一项任务，预订餐厅、预订航班，它现在能够可靠地完成。计算机使用 Agent 已经变得非常精密，模型本身也变得更好了。

第二是主动性。它会在你没有要求的情况下做事。比如 Instinct 叫醒你，告诉你今天是你妻子的纪念日，去买点花吧，或者更好的是，“我已经帮你把花买好了”，这就是那种神奇体验的一部分。

最后是集成。它连接了对你而言最重要的上下文系统：电子邮件、云端硬盘、日历。

<details>
<summary>Original English</summary>
I think if you think about the question, why did personal agents take off within the last 3 months? Internally, we came up with three main answers.

The first, reliable background agents. You can delegate a task, book a restaurant, book a flight, and it'll do it reliably now. Computer use agents have gotten sophisticated. The models themselves have gotten better.

The second is proactivity. It'll do things without you asking. It's part of that magical experience when Instinct wakes you up saying it's your wife's anniversary, go buy some flowers, or better yet, I already bought the flowers for you.

And finally, integrations. It's connected to the systems of context that matter most for you. Email, drive, calendar.
</details>

但是，让个人 Agent 表现如此出色的所有因素，如今并不能真正平移到机构金融中。

如果我们考虑后台任务，像预订餐厅这样简单的事情，在买方金融中对应的等价任务可能是：你如何从一个数据室（Data Room）直接生成一整套准备就绪的投资委员会（IC）模型、幻灯片和备忘录，把通常需要 4 周时间、经历多轮迭代与审查的流程压缩到几天之内。

如果我们考虑主动性，你的董事总经理其实并不希望一个脱缰的 Agent 到处乱跑、做一大堆事情并消耗 token，却不向他们提供和征求意见。

最后，如果你考虑真正关键的上下文，它不仅是电子邮件，不仅是日历；它可能是一个包含 15,000 个文件的数据室，可能是 SharePoint 或 Box 中一家机构在其 40 年历史中收集的数 PB 非结构化数据。

那么，你该如何应对这些问题？

<details>
<summary>Original English</summary>
But all the factors that make personal agents work so well doesn't really translate to institutional finance today.

If we think about background tasks, something as simple as booking a restaurant reservation, the analog equivalent in buy-side finance might be how do you go from a data room to a fully prepared set of IC models, slides, and memos, taking a process that would normally take 4 weeks, multiple rounds of iteration and review, and compressing that to a few days.

If we think about proactivity, your managing director doesn't really want agent rogue running around doing a bunch of things and burning tokens without them providing and soliciting input.

And then finally, if you think about the context that matters, it's not just email, it's not just calendar, it could be a data room with 15,000 files, it could be SharePoint box with petabytes of unstructured data a firm has collected in its 40-year history.

So, how do you deal with these problems?
</details>

### Compound 的长程金融 Agent 架构

因此，今天演讲的目的是进一步讨论我们在 Compound 是如何着手解决金融领域的长程 Agent 问题的。

一方面，是打造一个能与你及项目团队协同工作的真实队友。这就是多人协作，并将其嵌入到应用中。

另一方面，是解决你如何在后台并行运行长时间任务并可靠地执行它们。为此，我们实际上从头重写了 Office。

最后，则是你如何管理一切事物的上下文——也就是我们刚才讨论的所有内容，SharePoint 和 Box 中数 PB 的数据。我们也会简单聊聊我们为此设计的解决方案。

<details>
<summary>Original English</summary>
So, the purpose of today's talk is to discuss a bit more about how we at Compound have approached the problem of solving long-running agents in finance.

On one hand, it's creating a real teammate that collaborates with you and the deal team. So, that's multiplayer embedding that into the app.

On the other hand, it's solving for how you can you run long tasks in parallel in the background, reliably execute them. And so, for that, we actually rebuilt Office from scratch.

And then finally, it's how do you manage the context of everything, everything we just discussed, petabytes of data in SharePoint and Box. And we'll talk a little bit about how we've designed a solution for that.
</details>

### 多人协作与原生邮件集成

那么我认为我们必须问的第一个问题是：为什么多人协作对金融真正重要？

如果你观察一个项目团队的结构，对于那些长程工作流所涉及的任务——例如，从数据室生成最终呈现在投资委员会面前的所有材料——单人孤岛式的工作流是行不通的。

如今，对于在机构内部署了 Claude 或 ChatGPT 的人来说，它们全都是单人的。人们在插件里工作，在 Web 应用里工作，产出结果，但不可避免地，这些人需要与团队协作。那会是什么样子？意味着下载文件，上传到邮件中，上传到 Teams 里，征求反馈意见。

我认为正确的处理方式，也是我们在 Compound 思考的方式，就是如何让项目上每一个关键成员都加入到同一个对话线程中？他们如何都能与同一个 Agent 交流，从而让这一个 Agent 能够共享该特定工作流中所有相关人员的上下文？

<details>
<summary>Original English</summary>
So, the first question we have to ask, I think, is why does multiplayer actually matter for finance? If you look at the anatomy on a deal team, right, the type of tasks that matter for long-running type of workflows, for example, going from a data room into all the sorts of materials that make its way in front of an investment committee, it doesn't work for the single-player siloed workflows.

Today, for people who have deployed Claude or ChatGPT in their institutions, it's all single player. People working in a plugin, people working in the web app, producing outputs, but invariably, those people need to collaborate with their team. And what does that look like? It means downloading the file, uploading it into email, uploading it to Teams, asking for feedback.

I think the right way to approach this, and this is the way we've thought about at Compound, is how do you get every person who matters on a deal onto the same thread? How can they all talk to the same agent so that one agent can share the context of everyone who matters for any particular work stream?
</details>

当我们思考如何将多人协作带入一个熟悉的场景时，我们再次把目光投向了个人 Agent。它们为什么能运作得这么好？因为你可以很方便地在 iMessage 里发短信，或者在 WhatsApp 里发消息。

因此对于 Compound 上的 Agent，你创建的每一个 Agent 都自带一个内置收件箱。因为归根结底，对于机构金融而言，绝大多数工作流程都是通过 Outlook 运转的。你会有包含 20 封甚至更多邮件的往来邮件链。你希望 Agent 能参与到每一个这样的对话中。

为 Agent 设计电子邮件实际上绝非易事。它并不像直接连上一个电子邮箱那么简单。首先需要进行身份验证，确保该邮件链中的每个人对该 Agent 都拥有读写权限。在这些金融机构中，隐私极其关键。无论你看什么项目，你始终都处于保密协议（NDA）约束之下。因此你必须确保该邮件链上的每个人确实都能与该 Agent 对话。

但在身份验证之外，你还必须考虑如何设计出真正的拟人化体验。毕竟，我们试图创造的是一个真正的队友。如果多个人在短时间内相继在同一个邮件链中发送邮件，你并不希望有多个确认回复在群组里刷屏。你实际上希望加入一定的延迟，让它感觉更像人类。在思考如何为企业金融构建真正的邮件 Agent 时，还涉及到其他这类设计决策。

<details>
<summary>Original English</summary>
When we thought about how do we actually bring multiplayer into a familiar context, we looked again towards personal agents. Why did they work so well? Well, you can easily text one in iMessage or you can text one in WhatsApp.

So for agents at Compound, every single one you create comes with a built-in inbox. Because ultimately at the end of the day for institutional finance, most workflows run through Outlook. You'll have chains of emails 20 or more running. You want an agent to be part of every single one of those conversations.

Designing email for agents is actually non-trivial. It's not just as simple as hooking it up with an email inbox. It requires A, authenticating, making sure everyone part of that thread has read and write access to that agent. Ultimately at these financial firms, privacy is incredibly important. You're always under NDA no matter what deal you look at. And so you want to make sure everyone on that thread can actually talk to the agent.

But then beyond authentication, you also have to think about how do you design a real human-like experience? Because after all, we're trying to create a real teammate. If multiple people email in the same thread in quick succession, you don't want multiple acknowledgements spamming that group. You actually want to bake in some more latency to make it feel more human. And so there are other design decisions when thinking about how to create real email agents for enterprise finance.
</details>

### 消耗 1.5 万亿 Token，重写 800 万行代码的无头 Office 引擎

但抛开多人协作不谈，我们意识到即使在征求了所有关键人员的意见之后，如果你想扩充任务数量并全部并行运行，现有的现成方案根本无法满足要求。

我们评估了很多方案。Excel、PowerPoint 和 Word 的桌面插件；我们评估了计算机使用（Computer Use），通过虚拟机来尝试扩充能够在 Excel、PowerPoint 和 Word 中原生工作的 Agent 数量；我们还评估了大量现成的引擎，无论是像 OpenPyXL 这样的开源包，还是可供购买的商业引擎。

没有一个能真正满足我们的需求。随着代码 Agent 的大幅提升并将软件成本降低，我们决定直接从头构建我们自己的 Office。

正如一个优秀的 AI 工程师会做的那样，我们让 Agent 运行在许多循环中，消耗了 1.5 万亿输入输出 token，编写了超过 800 万行代码，从而从头重写了 Office。

我会稍微介绍一下我们是如何实现的。

但它其实很简单：就是让 Agent 对准一个目标函数——全保真复刻 Office，然后让它运行。

<details>
<summary>Original English</summary>
But multiplayer aside, we realized even after you solicit the input of everyone who matters, if you wanted to scale up the number of tasks and run them all in parallel, existing off-the-shelf solutions simply don't cut it.

We evaluated a lot. The desktop plugins of Excel, PowerPoint, and Word. We evaluated computer use using virtual machines to try to scale up the number of agents that could work in Excel, PowerPoint, and Word natively. And we also evaluated a ton of off-the-shelf engines, whether those are open-source packages like Open PyExcel or commercial engines that are available for purchase.

None of them really cut it for what we were trying to look at. And with coding agents dramatically improving and bring the cost of software down, we decided to just build our own office from scratch.

And like a great AI engineer would, we ran agents in many loops, spend 1.5 trillion input-output tokens and over 8 million lines of code to rewrite office from scratch.

And I'll walk through a little bit of how we approached it. But it's as simple as pointing agents at an objective function, which is recreate office in full fidelity, and then letting it run.
</details>

以 Excel 为例。我们从一个名为 IronCalc 的开源解决方案开始。我们决定：“好吧，如何为 Excel 完美重现它，把 Office 当作真值判定（Oracle），然后不断循环运行？”我们在真实文件上进行基准测试，这些文件既来自我们在网上获取的真实语料库，也来自我们在内部创建的文件。

在写了 800,000 行 Rust 代码之后，我们得到了一个与 Excel 相比性能高得多的、一比一完美复刻的产品。

有了这个，我们不仅能对 Excel 做到这一点，还能对 PowerPoint 和 Word 做到这一点。对吧？所以我们在每一个产品上都运行了循环，并且拥有了忠实的复现。你今天就可以在 thecompound.ai 上亲自尝试。它使用的是相同的方法：让 Agent 循环运行，以 Office 作为评判裁判。

我们使用 Rust 渲染器来确保这些产品的渲染达到像素级完美。因此你在 Compound 中看到的，与你下载到 Office 时看到的内容完全一致。我们需要一比一的对齐，因为归根结底，这些机构只信任他们能够下载并发送的内容。

<details>
<summary>Original English</summary>
So, take Excel as an example. We started with an open-source solution called Iron Calc. We decided, "Okay, how can you recreate this perfectly for Excel, use office as an oracle, and just run loops?" Benchmarking it on real files from both real-world corpus that we grabbed online, and also ones that internally we created. And 800,000 lines of Rust later, we had a performant much more performant compared to Excel, one-for-one replica of the product.

With this, we're actually able to do that for not only Excel, but also PowerPoint and Word. Right? So, we ran loops across every single one of these products, and we have faithful recreations. You can try it for yourself today at the compound.ai. And it's the same method, loop agents against office as a judge.

Using Rust renders to make sure that the rendering of these products was pixel perfect. So, what you see in Compound is what you see when you download to office. We needed one-for-one parity because at the end of the day, these firms only trust what they can download and they what they can send.
</details>

现在，我们来谈谈性能。为什么无头引擎相比于使用虚拟机或桌面版 Excel 要好得多？

首先，桌面版的 Excel、PowerPoint 或 Word 是受限于单台机器的 CPU 的。而使用无头引擎，你可以大幅加快并行执行任务的速度。你可以在短得多的时间内构建出一个复杂的模型。你可以把 20 MB 大小的 Excel 文件的重新计算速度提升 4 倍。因此，对于分析师期望 Agent 完成的每一项具体工作——再次强调，他们的预期是以极快的速度和极低的成本达到人类的质量——你必须拥有一个无头引擎才能做到这一点。

如果你试图用 Excel 和 PowerPoint 去做横向扩展，我认为你走错了方向。

<details>
<summary>Original English</summary>
Now, let's talk about performance. Why is a headless engine so much better compared to using a VM or using desktop Excel?

Well, for one, desktop Excel or PowerPoint or Word is bound to that CPU. With headless engines, you can do tasks in parallel much, much faster. You can build out a complex model in a much shorter amount of time. You can recalculate 20 MB Excels 4x faster. So, every single piece of work of an analyst would expect an agent to do cuz again, their expectation is quality of the human at much lower speed and much lower cost. You have to have a headless engine to do this.

If you try to scale this up with Excel and PowerPoint, I think you'd be going down the wrong path.
</details>

但这不仅仅关乎性能。拥有编辑器实际上能让你打造丰富得多的产品体验，让你与 Agent 的异步协作比在其他产品上做得好得多。

比如，你今天看到的整套演示幻灯片，全都是我在 Compound 里仅通过添加批注制作完成的。我让它生成了初稿，然后正如你在界面上看到的那样，我针对每一个排版细节留下了批注。从我的咨询生涯、从我在 Coatue 的日子里，我将所有关于“什么是优秀幻灯片”的心得都传授给了 Agent。

这同样适用于多人协作。你可以让同一个团队中的多个人使用我们搭建的同一套多人协作基础设施来添加批注。

这样一来，一个五人团队可以在一个下午刷完一份 100 页的幻灯片，而不必坐在会议室里花好几个星期去反复修改。

<details>
<summary>Original English</summary>
But, it's not just about performance. Owning the editor actually allows you to create a much richer product experience that allows you to work and collaborate with agents asynchronously much better than you can with other products.

So, this entire slide deck you're seeing today, I built in Compound just by dropping in comments. I had it create a first draft, and then as you can see here on the UI, I dropped in comments for every single piece of formatting. From my consulting days, from my Coatue days, all the learnings I had on what makes a great slide, I imparted with the agent.

This can also work for multiplayer. You can have multiple people part of the same team using the same multiplayer infrastructure we set up, dropping in comments. So, for a team of five, you can rip through a 100-page deck in an afternoon rather than sitting in a room revising it for multiple weeks.
</details>

最后，就构建自己的引擎而言，它还使我们能够更好地运行迭代检查循环。

举例来说，如果你有一项编写复杂模型的任务，可能需要耗费几个小时。

但我们该如何让它更快？如何让它更准确？如果你使用的是像 openpyxl 这样的代码库，你无法使用渲染器去检查格式。你只能猜测并寄希望于模型写出了正确的内容，或许你可以做一些解析来看单元格是否有特定颜色或特定字体。

如果你尝试使用微软自己的接口，你将受限于微软提供给你的能力，而公认的是，微软提供的接口非常有限。

因此，拥有自己的引擎后，你就真正拥有了“编写、渲染、检查、修复”的闭环。这样你就可以为用户快速迭代输出结果。

<details>
<summary>Original English</summary>
Finally, with respect to building your own engine, it also allows us to run iterative checking loops much more as well.

So, if you have a task that, for example, is writing a complex model, it might take a few hours. But, how do you How can we make that faster? How can we make it more accurate? If you're using, for example, an OpenPyXL code library, there's no render you can use to check formatting. You're just guessing and hoping that the model writes the right thing, and maybe you do some parsing to see a cell has a particular color, has a particular font.

If you try to use Microsoft's own interface, you're going to be limited by what Microsoft provides you, which is admittedly very little.

So, with an own engine, you actually own the write, render, check, and fix loop. So, you can rapidly iterate on the output for the user.
</details>

### 处理数据广度与深度：Agent Swarm 与专用引擎

那么除了多人协作和构建我们自己的 Office 之外，我今天最后想讨论的一点是，如何处理这些机构所拥有的上下文。

对于买方机构，他们面临的情况兼具数据的广度与深度。你可能会遇到数据室包含超过 15,000 个文件的情况，而且数据室中的单个文件可能远远超过 20 MB。

金融行业的人一直在抱怨：“嘿，我有一个 30 MB 的 Excel 模型。由于我们有 200 万个公式以及每次都必须重新计算的 5 个敏感性分析表，它重新计算一次就需要 5 分钟。”

那么，你该如何应对这种情况？

<details>
<summary>Original English</summary>
So, the last thing I sort of want to discuss today beyond multiplayer and building our own office is how to deal with the context that these firms have.

For firms on the buy side, they deal with situations where cross is both breadth and depth of data. You may have situations where you have a data room of over 15,000 files, and then files in that data room might be well over 20 megabytes.

People in finance complain all the time, "Hey, I have an Excel model that's 30 megabytes. It takes 5 minutes to recalculate because we have 2 million formulas and five sensitivity tables that need to recalculate every single time."

So, how do you deal with this?
</details>

在数据广度方面，我认为我们同样可以借鉴编写代码的思路，将 Agent 集群（Agent Swarms）应用到海量文件上。

你不再需要把所有内容都索引进向量数据库，除非是为了非常特定的用例。实际上更好的做法是使用代码 Agent 通过 grep 或其他方法读取文件，然后由一个主管 Agent 对文件目录内容进行切片，接着让一群 Agent 带着见解返回给你。然后你在循环中不断迭代，直到满足所需的输出质量。

此外，通过这个流程，你实际上能够将每一个发现都与源文档中的引用相互印证，从而确保你在屏幕上展示的内容准确对应到某个分析师能够信任的数字上。

<details>
<summary>Original English</summary>
Well, for breadth, I think again we take a look at a page out of the coding book and apply agent swarms to the large number of files.

No longer do you have to index everything in a vector DB unless it's for it's for a very specific use case. It's actually much preferable to use coding agents to read files either through grep or through some other methodology, and then have a lead agent slice the contents of the file directory, and then have swarms of agents come back to you with insights. And then you iterate that in a loop until you're satisfied with the output required.

Furthermore, through this process you're actually able to ground every single finding inside citations in the source document, so that you know exactly what you show on the screen is linked to some number that the analyst can trust.
</details>

如果我们考虑数据的深度，对吧？以那个 30 MB 的工作簿为例。你究竟如何才能更准确地处理它？

在当今世界，如果你直接拿现成的 ChatGPT 或 Claude 来处理那个 30 MB 的模型，它会编写代码，会使用像 openpyxl 这样的开源包。这不仅成本高昂而且非常缓慢，因为它在代码中为模型打印出了该模型的所有上下文细节以供读取。

但因为我们为 Excel 开发了自己的引擎，我们不仅更准确，而且速度快得多、成本低得多，因为引擎在处理完后，会以非常易于阅读和处理的格式呈现给模型。

这意味着我们可以为 Agent 暴露丰富得多的 API 集合以及丰富得多的工具集以供操作。这使我们能够以快得多的方式处理这些模型。

<details>
<summary>Original English</summary>
If we think about the depth of data, right? Take that 30 megabyte workbook. How can you actually process this more accurately?

In today's world, if you were to just use ChatGPT or Claude off the shelf to process that 30 megabyte model, it would write code, it would use open-source packages like openpyxl. It would be expensive and slow because it's printing out every single piece of context about that model in code for the model to read.

But because we've developed our own engine for Excel, we're actually not only more accurate, but a lot faster and cheaper because the engine processes it and then lays it out in a very easy-to-read and easy-to-process format for the model.

This means we can expose a much richer set of APIs and a much richer set of tools for the agent to work over. And that allows us to process these models in a much faster manner.
</details>

如果我们退一步想一想：“构建所有这些上下文归根结底是为了什么？”

归根结底，我们希望做的是防止人们把时间浪费在查找文件、提醒模型这该怎么做上。相反，他们应当把精力集中在将自己的判断注入到交易流程中。他们应当专注于调整、训练 Agent，并将它们部署到交易流程的各个环节。

所以它的层级从最底层开始：连接的源系统（比如连接到 SharePoint 或 Outlook 的开箱即用连接器）；到基于关键源文档引用的结论；最后，嵌入至关重要的偏好和公司专有知识——比如“模型该怎么做？呈现效果应当如何？”，这在每家机构都各不相同。

这样一来，人类就可以把大部分时间花在施加判断上。他们可以把绝大多数时间花在思考“这到底是不是一笔好交易？”上，而不是去核对所有数字是否对得上、模型看起来是否正确、我的副总裁会不会因为格式不同而冲我大吼。

<details>
<summary>Original English</summary>
So, if we sort of take a step back and think about, "Okay, what is all of this context built for?"

At the end of the day, what we want to do is prevent people from spending time finding files, from reminding the model this is how to do things. Instead, they should be focused on importing their judgment on the deal process. They should be focused on tailoring, training agents, and deploying them on every part of the deal flow.

And so, it goes from the bottom level, connected sources, off-the-shelf, you know, connectors to SharePoint or Outlook, to the cited findings grounded in the sources that matter. And then finally, embedding in the preferences, company knowledge that matters. How do you do it, model? How should it look? Which differs by every single firm.

So, that for humans, they spend most of their time imparting judgment. They spend most of their time thinking about is this actually good deal? Not did all the numbers tie? Does the model look right? Will my VP yell at me because it looks different way?
</details>

### 从 Copilot 迈向 Autopilot

所以，

噢。Cursor 需要更新一下。

如果我们退一步，思考目前处于 Autopilot（自动驾驶）状态与处于 Copilot（副驾驶）状态的任务类型，我认为有几项金融任务用现成工具已经可以完成得相当不错了。比如展开可比公司分析（Spreading comps），正如 ChatGPT 金融负责人之前提到的，他们现在对此有了自己的产品。

但我认为还有很多长程任务是现有解决方案无法胜任的。你如何信手拈来直接起草一份 50 页的投资委员会报告？你如何让 Agent 完全按照私募股权专业人士或对冲基金专业人士的要求去构建一个模型？我认为使用现成工具时，这些任务仍然属于 Copilot 的范畴。人们希望深度参与到这个过程中而不愿放手。

<details>
<summary>Original English</summary>
So,

Oh. Cursor needs to update.

If we take a step back and think about the type of tasks that currently are on autopilot um versus what are on copilot, I would say there's already several finance tasks you can do pretty well with off-the-shelf tools. Spreading comps, as the ChatGPT head of finance mentioned earlier, they have now their own products for this.

But I think there are a lot of longer running tasks that are not capable with existing solutions. How do you draft a 50-page IC presentation off the cuff? How do you get agents to build out a model exactly the way you want it for a private equity professional or a hedge fund professional? I think those are tasks that with off-the-shelf tools still exist as co- as sort of within the copilot realm. People want to be embedded deeply in that process without letting go.
</details>

但借助我们今天打造的一些工具，我认为我们能够拓宽金融机构中 Autopilot 可以接管的范围。

因此，与其仅仅使用嵌入在 Excel 中的插件工具、一路小心翼翼地手把手引导，你可以开始放手委托。你可以开始对 AI 的能力抱有更大的野心。

如果思考当今金融领域所处的阶段，这很大程度上让我想起了去年 12 月 Opus 4.5 发布时的情形：人们不再把代码工具当作简单的 Copilot 来生成下一个文件或下一行代码，而是开始委托远具野心的任务。他们开始意识到，也许我真的可以直接凭直觉开发（vibe it）。如果我有足够的检查，如果有足够的测试，也许我可以完全信任它写出的所有代码。

我认为借助我们今天构建的部分工具，加上我们未来的规划，这些正是你在金融领域达到这一目标之前必须解决的问题。

分析师以及整个项目团队该如何对 AI 变得更加雄心勃勃？他们如何能够直接扔进去一个数据室并下定决心：“好吧，我要信任输出的每一个结果，然后让我们把这个过程放大十倍，这样我们就能看更多的交易，从而扩大关键业务的视野。”

总而言之，企业级 Agent 必然会进入金融领域。我坚信我们正处于采纳曲线的拐点上，人们正在逐渐变得更加有抱负，正在从 Copilot 转向 Autopilot。

以上就是我们在 Compound 对此的探索方案。

如果你在金融机构工作，并且有兴趣部署我们的 Agent 来推进更多的交易工作，请与我们联系。或者如果你是一名工程师，对讨论我们的方法和分享想法感到好奇，请在线联系我们，或者我也在现场，随时可以找我。非常感谢。

<details>
<summary>Original English</summary>
But with some of the tools we've built today, I think we're able to expand the aperture for which autopilot can take over in finance firms.

So, rather than just using tools embedded in Excel as plugins, hand-holding along the way, you can start delegating. You can start becoming more ambitious about what AI is capable of. If I think about where we are today in the world of finance, it very much reminds me of when Opus 4.5 launched last December, where people stopped using code as a simple co-pilot to generate the next file or the next line of code, but they started delegating far more ambitious tasks. They started realizing, maybe I can just truly vibe it. If I have sufficient checks, if I have sufficient tests, maybe I can just trust all the code it writes.

I think with some of the tooling we've built today, along with what we're planning in the future, these are the type of problems you have to solve before you get to that point for finance. How can analysts, how can the entire deal team become more ambitious with AI? How can they just drop in a data room and decide, okay, I'm going to trust every single one of the outputs, and then let's do that tenfold so we can see more deals, so we can expand the aperture of what matters.

So, to conclude, enterprise agents are certainly coming to finance. I strongly believe we're at an inflection point in the adoption curve, and that people are slowly becoming more ambitious, and they're moving away from co-pilots to auto-pilots.

And so, this was sort of how we've approached it here at Compound. If you work at a firm and you're interested in deploying our agents to drive more of your deal work, please reach out. Or if you're engineer and you're curious about talking about our approach and sharing ideas, please either reach out online or I'll be around if you want to find me. Thanks so much.
</details>