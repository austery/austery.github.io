---
author: AI Engineer
date: '2026-11-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jDwc0aXTAFg
speaker: AI Engineer
tags:
  - agentic-system
  - state-estimation
  - institutional-memory
  - world-model
title: 用 Agent 构建企业世界模型：Citadel Securities 的组织记忆层实践
summary: Citadel Securities 工程师介绍如何利用类似机器人学状态估计器的 Agent 系统构建企业世界模型。系统综合自上而下的幻灯片报告与自下而上的通讯、代码等杂讯，通过更新、时效老化、观察、评级与人工纠偏闭环追踪真实状态并预测延期风险。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Citadel Securities
products_models: []
media_books: []
status: evergreen
---
### 组织中缺失的世界模型

[音乐]

很高兴来到这里。请再次为 AI 工程大会的各位工作人员鼓掌，到目前为止，这真是一场非常非常棒的会议。谢谢大家。
<details>
<summary>Original English</summary>
[music]

>> Pleasure to be here. Another round of applause for everyone at AI engineering. This has been a really, really exceptional conference so far. Thank you.
</details>

好了。我想先请大家想一想你们公司里那个似乎无所不知的人。他们经历过 17 次组织架构调整，知道所有八卦、所有的内情，而且不知怎的，他们总能预测出这些重大战略举措的最终走向。
<details>
<summary>Original English</summary>
All right. So, I want to begin by asking you to think about that person in your company who just seems to know everything. They've been through 17 reorgs. They know all the gossip, all the politics. And somehow they always seem to predict what's going to come out of these like big strategic moves.
</details>

那个人本质上就是一家公司的世界模型。问题在于他们无法规模化，而且也没有人会真正把他们说的话记录下来。
<details>
<summary>Original English</summary>
That person is a company's world model, essentially. And the problem is that they don't scale, and nobody really writes down what they say.
</details>

我是来自 Citadel Securities 的 Wenzel，今天我将谈一谈我们如何尝试通过一个 Agent 系统来逼近这一能力。
<details>
<summary>Original English</summary>
I'm Wenzel with Citadel Securities, and I'm going to talk a little bit about how we try to approximate that with an agentic system.
</details>

稍微介绍一下 Citadel Securities：我们自研所有技术，一直深入到底层芯片。目前，我们超过三分之二的员工都会写代码。因此，我们自然全方位拥抱了 AI，并且 Agent 已经在机构内部的许多方面为我们提供协助。
<details>
<summary>Original English</summary>
So, a little bit about Citadel Securities. We build our own technology down to the silicon. At this point, over 2/3 of our employees write code. So, naturally, we are completely AI pilled, and agents already help us with a lot of things at the organization.
</details>

所以，领导层自然开始对战略提出疑问：这些测试与运行框架非常擅长生成高质量代码，但它们究竟能否真正帮助定义和完善我们公司的战略？
<details>
<summary>Original English</summary>
So, naturally, leadership started asking questions about strategy. These harnesses are really good at producing high, you know, high-quality code, but can they actually help define and refine the strategy of our company?
</details>

### 构建机构记忆层

这是我从 Tim Urban 那里借鉴来的一张我最喜欢的图表。战略归根结底其实就是三个问题：我们现在处于什么位置？接下来会发生什么？以及我们是如何走到这一步的？
<details>
<summary>Original English</summary>
So, this is one of my favorite visuals I've borrowed from Tim Urban. Strategy really comes down to three questions, right? Where do we stand right now? What's going to happen next? And how did we get here?
</details>

而要回答其中任何一个问题，Agent 都必须对其所处的公司拥有非常丰富的背景画像。
<details>
<summary>Original English</summary>
And to answer any of those questions, an agent has to have a really rich profile of the company that it's operating in.
</details>

所以，大致来说，这是一场关于工程化构建**机构记忆层**（不妨这么称呼它）的演讲。Agent 需要掌握关于各种关系的信息，比如：因重组而不再交流但曾经合作过的两个团队；某个项目背后的故事以及它为什么被多次重新划定范围；或者是职场动态——谁在场、他们说了什么，以及他们没说什么？
<details>
<summary>Original English</summary>
So, this is broadly a talk about engineering a institutional memory layer. Let's Let's Let's call it that. The agents to have information about relationships, right? Two teams that used to work together but no longer stop talk because there was a reorg or a project story and why it was rescoped several times or the politics, right? Like who's in the room, what are they saying and what are they not saying?
</details>

切入方式有两种：自上而下与自下而上。
<details>
<summary>Original English</summary>
There's two ways in, right? There's top down and there's bottom up.
</details>

自上而下的路径中，你有演示文稿、战略文档、会议及状态报告，它们整洁美观，但带有一种独特的人为主观偏差。人们通常喜欢把自己的想法和观点融入其中，有时甚至是有意为之，结果就出现了我所说的**“西瓜项目”**——表面是绿色的，内部其实已经见红。
<details>
<summary>Original English</summary>
Top down, you have the decks, you have your strategy docs, your meeting and status reports and they're tidy and they're pretty clean but there's a unique human twist. People generally like to infuse their thoughts and opinions into these things, sometimes by design, so you end up with what, you know, things I call watermelon projects, right? They're green on the outside and red on the inside.
</details>

然后，在底层则是极其嘈杂的内容，里面蕴含着惊人数量的信号，但往往难以发掘：会议记录、Slack 消息、代码变更，甚至是与你偏爱的测试框架之间的会话调用追踪。
<details>
<summary>Original English</summary>
Then you have on the bottom, you have the really noisy stuff which has a surprising amount of signal but it it's hard to uncover, right? You have meeting notes and you have slack and code changes and even your session traces with your favorite harness.
</details>

而模型正是两者交汇的地方，证据就在这一层级完成综合。
<details>
<summary>Original English</summary>
And the model is where they meet. The evidence is synthesized at that level.
</details>

### 借鉴机器人学的状态估计器

这些证据有时存在问题，因为它们要么不完整，要么就是错的。但事实证明，在机器人学中其实有现成的解决方案，叫做**状态估计器**。你的做法是：对你关心的某个事物持有某种信念，距离上次看到或观察到支持它的证据时间越久，你对它的信任度就越低，它就越模糊；直到你拿到一份演示文稿、一段讨论串或某份会议记录打破了这种状态，你便拥有了新证据。此时你对它更加确定，从而生成一次更新。
<details>
<summary>Original English</summary>
Now the evidence piece sometimes is problematic because it's either partial or wrong but it turns out that in robotics you actually have the solution for this and it's called a state estimator, right? What you do is you have some sort of belief about something you care about and the longer it's been since you've seen or observed evidence that supports it, the more you the less you trust it, right? The fuzzier it gets until you have a deck or a you know, some thread or some meeting note that sort of collapses that and you now have new evidence, right? And now you're more certain of it and therefore you produce the update.
</details>

而在生成更新时我所关心的——或者说 Agent 应当关心的——有三件事：
1. 距离接收到某个信号已经过去了多久？
2. 该信号来自何处，它目前是否依然值得信赖？
3. 它与其它传感器是否大体一致？

这里与自动驾驶等领域有很多相似之处，我稍后会再回到这一点。
<details>
<summary>Original English</summary>
And the things that I care about when producing an update or that the agent should care about, there's three things. There's how long has it been since it been since some signal has been received, there's where that signal come from and is that still what trustworthy and then does it broadly agree with other sensors, right? You can there's a lot of parallels here with like self-driving, for example, that I'll come back to.
</details>

那么我们先从自上而下开始。一个非常简单的例子是 BizOps 人员制作的一张幻灯片，他们会制作月度状态报告演示文稿。
<details>
<summary>Original English</summary>
So, let's start at the top, right? Like a very simple example is something like a slide that is produced already by someone in BizOps, and they produce a monthly status deck.
</details>

问题在于，你如何从这张幻灯片中提取数据？我相信你们很多人都尝试过，这其实极具误导性。因为假设你尝试去解析文件，解包 PowerPoint 文件得到 XML，突然之间你就会陷入一个非常耐人寻味的概念性问题：什么是绿色？绿色的十六进制色值究竟是多少？面对这类脚本处理，很多流程就瓦解了。
<details>
<summary>Original English</summary>
And the question is, how do you get data out of the slide, right? It's Many of you, I'm sure, have tried that. It's this It's deceptive, actually, right? Because, let's say you try to parse the file, right? Like you unpack the PowerPoint file, and you get an XML, and all of a sudden, you get into this really interesting conceptual question. What is green, right? What is the hex code for green? Um and you sort of things break down when it comes to this type of script.
</details>

接着解决方案就变成了：“好吧，我直接截个图扔给视觉模型。”但到了那一刻，即便截图分辨率相当高，你面对的也是某个人把截图复制粘贴回演示文稿的情况，实际上就变成了让 Claude 眯着眼睛费劲分辨那到底是 31 还是 81。
<details>
<summary>Original English</summary>
Then, the solution is to say, "Well, I'm just going to take a screenshot of it and throw it at a vision model." But at that point, even if it's like pretty high-res, you're dealing with someone who copy-pasted a screenshot back into a presentation, and like essentially, you have Claude trying to squint and trying to figure out if it's a 31 or an 81.
</details>

因此，这次演讲的主题其实就是：优雅源于对事物的综合与更多信息的补充。在这个例子中虽然很基础，但将 XML 与视觉模型的输出结合起来，你才能获得真实的全貌。
<details>
<summary>Original English</summary>
And so, you know, the theme of the talk, really, is about like elegance comes from just synthesizing things and adding more information. And in this example, it's very basic, but you get the true picture by taking both the XML and the output of a vision model.
</details>

这还只是相当基础的部分。问题在于你希望建立某种跨越时间的连续性，公司积累的这些材料实际上是一直在不断叠加的。在当前这个具体例子中，有个项目早在三月份就突然改名了。因此，当你围绕公司的机构记忆创建这种共享上下文层时，你必须建立起这种纵向且可追溯的审计层。
<details>
<summary>Original English</summary>
Now, that's pretty basic, right? But the issue is that you want to establish some continuity over time, right? Like these this collateral that your company accrues is very much sort of always building up. And so, in this particular example, you have a a project that just spontaneously names back in March. And so, you know, you have to establish that sort of longitudinal traceable audit layer as you as you create this shared context layer about the sort of institutional memory of your company.
</details>

讽刺的是，这里有两点：其一在于即便你把这件事做得很好，依然会遗漏一半的拼图。你看向演示文稿，但你的 Slack 说的却完全是另一回事——因为那是 5 天前的文件，现在 Slack 上有人在说：“顺便说一下，我认为我们在这个项目上进度正常。”但随后有人回复了一张仪表板截图，表明情况早已并非如此。事情就这么开始崩溃了。
<details>
<summary>Original English</summary>
And the irony, there's two things. The irony here is that even if you do this really well, you're still missing half the picture, right? You're looking at a deck, and your Slack says otherwise, because that was 5 days ago, and now you have someone on Slack saying, "Hey, by the way, I think we're on track for this." But then someone replies with a picture of a dashboard, and it's no longer the case. So, things just start breaking down.
</details>

### 五步闭环：更新、时效、观察、评级、纠偏

因此，我们需要在整合所有这些信息方面做得更好。你们公司对自身并没有一个模型。
<details>
<summary>Original English</summary>
And so, we need to do a better job of like integrating all these things, right? Your company has no model of itself.
</details>

所以我在此提出一个简要方案。核心思路就是采用我前面描述的状态估计器的三项要素：包含**更新（update）**、**时效老化（age）**和**观察（observe）**阶段，接着是**评级（grade）**。评级阶段基本上就是比对观察到的现象与预期情况。然后**纠偏（correct）**阶段基本上是为人工提供一种途径，让系统获取新反馈并引导系统行为。
<details>
<summary>Original English</summary>
So, I'm proposing just a brief plan here, right? The idea is you take the three things that I described earlier about the state estimator. You have the update, age, and observe observe um stages, and then you have grade. The grade stage is basically comparing what you're observed versus what you expected. And then the correct stage is basically a way for people to allow the system to get new feedback and steer the behavior of the system, right?
</details>

在 Citadel Securities，我们构建的系统在这个特定循环的每一个环节都部署了 Agent。但最关键的是：由模型提出这些变更建议，然后由代码和人工来决定如何更新记录。
<details>
<summary>Original English</summary>
At Citadel Securities, the system that we've built has agents at every part of this of this particular loop, right? But the key thing is that the model is proposing these changes, and then you have code and people deciding how the records are updated.
</details>

当然，你可能会问自己：为什么不直接用 RAG 呢？RAG 大概就能搞定吧？事实上它真的不行。在这个例子中，我提问：“这项项目的状态如何？进展正常吗？”截至 3 月 16 日，某个模型会很乐意抓取几条 Slack 消息和一些幻灯片，然后回答：“是的，处于绿色正常状态。”但它遗漏了大量的上下文，这根本不够用。
<details>
<summary>Original English</summary>
And of course, you're probably asking yourself, like why not just rag, right? Like probably rag would do the trick. And in fact, it it it really doesn't, right? Like you you in this example, I asked, "Hey, what's what's the status of this project? Is it on track?" And as of March 16th, some model would happily pick up a couple of Slack messages and some slides and say, "Yep, it's green." But it's missing a lot of the context, right? It's not enough.
</details>

以下是我们着手构建这一世界模型的方式。第一阶段是关于一致且稳健地更新信息。
<details>
<summary>Original English</summary>
So, here's how we start building this world model. The first stage is about updating information consistently and robustly.
</details>

在这个我提取一些幻灯片和演示文稿的简单示例中，我们基本上就是在每个月到来时，提取上个月的记录与当月的幻灯片，尝试构建出一种纵向记录。我们这项工作已经进行了 3 年，积累了相当庞大的历史记录数据库，使我们现在能够构建起这种稳健的所谓机构级或企业级世界模型。
<details>
<summary>Original English</summary>
In this simple example, where I'm taking some slides and some decks, we are basically just looking at, you know, every month, you know, new month comes around, we take last month's record and this month's slide, and you try to construct a sort of longitudinal record, right? And we've been doing this now for 3 years, right? We have a pretty large historical database of these records that now allow us to construct this robust so-called institutional or enterprise world model.
</details>

你可以从最基础的开始。有时这些模型在最基础的事情上会犯难，但这些情况很常见：某个具体项目的实际名称会自发改变，但通过实际观察那套历史记录，模型能够根据参与人员、目标类型的连续性等线索，看出并推断出它实际上指的就是 Northstar 项目。
<details>
<summary>Original English</summary>
You start with the basics, right? Like, you know, sometimes these models struggle with the most basic things, but but they're normal, right? The the actual name of a of a particular project change spontaneously, but by actually looking at that historical set of records, it can see and infer that it actually refers to project Northstar by virtue of who was involved, by virtue of some continuity in the types of goals, those kinds of things.
</details>

但更有趣的是，你希望让 Agent 系统尝试去区分汇报上来的内容与支持该言论的实际证据。
<details>
<summary>Original English</summary>
But more interestingly, what you want to do is you have the agentic system, try to discriminate between what's being reported and actual evidence for what it's saying.
</details>

比如你查看某份状态报告文稿，在这里系统识别出：虽然文稿上标为绿色，但实际上应当标示为黄色警示，因为有人留了一条评论，提到还有一项依赖项悬而未决。
<details>
<summary>Original English</summary>
So, you look at some status deck, for example, and here it's identifying that while it is green on the deck, in fact, it should be highlighted as a yellow and should be flagged as such because there's a comment someone left talking about how there's a dependency still outstanding.
</details>

这里的关键在于你不去篡改之前月份的记录，只是采用类似前馈的机制进行修复。这能让你在后续阶段开展稳健的评估评测。
<details>
<summary>Original English</summary>
The main thing here is that you don't touch previous months, right? You just sort of heal in the sort of feed forward mechanism. What that allows you to do is to actually do some robust evals down the line, right?
</details>

实际的更新步骤写入的内容非常简单：这是汇报的内容、这是证据指向的方向、以及为什么会这样。
<details>
<summary>Original English</summary>
So, here's what the actual update step writes, you know, very simple. This is what it was reported, this is how it, you know, the evidence, this is where the evidence points, and this is why.
</details>

然后引入第二个组成部分：**时效老化（age）**。现实情况是，每个事实都有半衰期。我们都见过这种情况：你回头去看一些幻灯片，会发现某个具体项目的上线日期不断推迟——1 月份时说是第二季度，后来变成第三季度，现在又变成了 10 月。通过实际收集所有这些数据，你确实能观察到这一现象，并开始获得一些相当有趣的分析洞见。
<details>
<summary>Original English</summary>
And then you fold in the second component, age. The reality is every fact has a half-life. We've all seen, you know, you go back at some slides and you you see that the go-live date for a particular project keeps slipping. It was Q2 in January, then it was Q3, now it's October, right? And you actually observe this, right? By by actually collecting all this data, you can have some pretty interesting beginnings of analytical insights.
</details>

例如，在过去 3 年中观察这些交付日期，平均有一半的交付日期会在 2 个月内发生变动，其中 90% 都推迟到了比最初提议更晚的日期。到目前为止还算顺利，都很基础。但这迫使你必须引入与特定断言相关联的“日期”概念，以便在询问特定项目、人员或整体公司意图的状态时，Agent 能够引入某种近因偏差。
<details>
<summary>Original English</summary>
For example, in the last 3 years, you look at these delivery dates, and on average, half the delivery dates change within 2 months, and 90% of those change for into a date that is after what was originally proposed. Right? So far, so good. Pretty basic. But what you what this forces you to do is then introduce this notion of like a date that it is associated to a particular claim, so that the agent can introduce some sort of recency bias when you ask about the status of a particular project, person, or or or all of the corporate intent, let's say.
</details>

接下来是**观察（observe）**环节。关于观察部分，我打算快速带过，只给大家一些非常实操的内容。刚开始时，大家的惯常做法基本上就是直接“不管不顾全量扔给模型”（YOLO），让 Claude 或其它模型通读整个语料库，看看它能得出什么。事实证明，显然有大量信息丢失了，模型丢失了对细节的关注。因此，我们最终不得不工程化设计出一套简单的 Agent 工作流：由一系列专精 Agent 对这些资产材料进行拆解，寻找特定要素，交由其它 Agent 审查，以此类推。
<details>
<summary>Original English</summary>
Then the observe section. The observe section here, I'm going to pretty quickly gloss over it, but I just kind of give you something very tactical. In the beginning, it always produced active to just basically say, well, let's just YOLO this. Let's have Claude or some other model take a look at the entire corpus of things and let's see what it does. And as it turns out, it's it's pretty clear that a lot of um information is is lost, right? It loses some attention to detail. And so, what ultimately we had to do was engineer a simple agentic workflow where you have a series of specialists break down the collateral of these assets, look for specific things, be reviewed by other agents, and so on.
</details>

大家在右侧可以看到，采用这种做法后，针对特定项目的有价值洞察更新数量实际上翻了一倍多。因此，这里的经验之谈是：构建这些工作流时要有针对性规划，不要假设无脑丢给模型的方法能行得通。
<details>
<summary>Original English</summary>
And what you see here on the on the right-hand side is that actually the amount of insightful updates to a particular project more than doubled after doing this. So, I guess the takeaway here is be intentional about how you how you build these workflows and don't just assume that a YOLO method is going to work out.
</details>

### 回测验证与预测能力

但现在到了我认为真正有趣的地方：一个世界模型应当能够告诉你接下来会发生什么。哪个项目即将延期？或者哪个绿色项目下个月会变红？事实证明你确实可以做到这一点，因为你可以回溯并在过去的某个日期建立快照，基本上就是进行一次回测。例如，如果我们截取截至 2 月份的快照，我们可以查看此后出现的未来标签，对比 Agent 预警会延期或标记的内容与实际发生的情况。
<details>
<summary>Original English</summary>
But now you get, I think, to the really interesting stuff, right? A world model should tell you what happens next. What project is about to slip or which green turns red the next month? And it turns out that you can actually do this, right? Because you can look back and establish a snapshot as of some sort of past date and essentially run a back test. So, for example, if we take a snapshot as of February, we can look at the future labels that came after that and see and compare what the agent said was going to slip or flagged versus what actually happened.
</details>

可以看到，随着 Agent 对所有这些信息进行分析，那些原本显示为绿色但被标记预警的状态，实际转变为黄色或红色的概率高出了两倍。
<details>
<summary>Original English</summary>
And you can see that as the agent um analyzes all this information, that for statuses that were green but flagged, they were twice as likely to actually turn yellow or red.
</details>

所以再次说明这是令人鼓舞的，因为我们开始看到初步的端倪：虽然它无法精确预测具体会出什么问题，但至少能够提示你应当重点关注什么。
<details>
<summary>Original English</summary>
And so, again, this is encouraging because we're starting to see some beginning of the inability to say, well, it's not predictive of exactly what's going to go wrong, but at least it should tell you what to look at.
</details>

### 人在回路与自下而上的多源感知

我们在 18 个不同案例中获得了 Agent 标记的判断结果，但那些没有标记的情况该怎么办呢？这就需要引入一些产品直觉了。首先，你如何整合一个非常优雅的闭环，把真实用户、利益相关者以及人工包含进来？你向他们询问什么？你在哪里接触他们？为了找出实际采集这些信息的最佳方式，我投入了相当多的心力。关键在于在用户所在的地方与他们接触，无论是在他们正在使用的应用中、Slack 上还是电子邮件里。你距离他们越近、反馈采集机制越简单，流程就会越具扩展性与稳健性。
<details>
<summary>Original English</summary>
So, you know, we have 18 different cases where you have a verdict from a agent that's flagged, but what about those where you don't? And this is where some product intuition comes in. First of all, how would you incorporate a very elegant sort of loop where you include uh an actual user, stakeholder, a human? And what do you ask them? And where do you meet them, right? I put a non-trivial amount of work into finding out how best to actually capture this information. It's meeting the users where they are, whether it's the app they're using or Slack or email, whatever. And the closer you can get to them and the simpler you can make that feedback collection mechanism, the more scalable and and robust the process is going to be.
</details>

你问什么也很重要。你需要明确你是在询问一项事实（这只能修正单次输出），还是在询问一条规则。一旦 Agent 理解了该规则模式，它在修正其覆盖的所有输出方面就会表现得好得多，无论是当前还是未来。
<details>
<summary>Original English</summary>
It also matters what you ask, right? You want to understand whether like you're asking a fact, which only fixes one output, or if you're asking about a rule. And once that an agent understands that pattern, it does a much better job of fixing every output it covers, both both now and into the future.
</details>

因此，我们现在的记录不仅包含 Agent 推断的内容，更重要的是包含有人实际提供该信号后得到确认的内容。
<details>
<summary>Original English</summary>
So, we have this notion now of our record containing not just an element of what was inferred agent, but more importantly confirmed after someone actually provided that signal.
</details>

好，现在看自下而上的途径。你有会议记录，包含了人们公开说出的强信号；你有 Slack，显然信息持续不断、充满噪音，但极其贴近事实真相；代码变更描述了实际交付了什么；当然还有 Agent 会话追踪，它记录了成果是如何制作出来的。我鼓励大家去探索所有这些分散的数据源，来构建起这样一个模型。
<details>
<summary>Original English</summary>
Okay, so now bottom-up, right? You have meetings with you know, really strong signal what people say out loud. You have your Slack, you obviously it's constant, it's noisy, it's very close to the truth. Code changes describe what shipped. And then of course the agent sessions, which is how the sausage was made. And I think I encourage you all to explore all of these disparate data sources to kind of build such a model up.
</details>

对于 Slack，处理起来相对直接：只需浏览每个讨论串，根据附件、参与者和内容，去理解你希望 Agent 记录或更新的断言。这是什么时候发生的？谁负责或与谁相关？涉及哪个项目？关联的证据链接是什么等等。
<details>
<summary>Original English</summary>
With Slack, it's relatively simple, right? Like you're just looking at every thread and trying to understand based on attachments and participants and content, the claims that you want the agent to record or update. When was this? Who was responsible or who does this relate to? Um what project? What What's What is the sort of link to the evidence and so on.
</details>

对于 Pull Request，它当然展示了具体修改了什么，是观察项目演进非常好的方式。但在项目如何运行和部署的实际细节方面，观察那些选择加入跟踪的用户和工程师的实际轨迹会非常有趣：你能了解需求是如何随时间演变的、测试失败情况，或者是开发者的特定决策等等。这些最终汇聚成一个 PR，但综合这些信息会带来巨大差异。
<details>
<summary>Original English</summary>
With PRs, of course, it shows you what changed. And it's a really nice way to see how a project is evolving. But, when it comes to the actual like subtleties of how projects are are sort of run and deployed, it's really interesting to look at the actual traces you know for users and engineers who opt into that, right? Like you understand how the ask was what how it evolved over time, test failures or you know particular decisions from the developer, those kinds of things. Ultimately these culminate in a pull request but the synthesis of these things I think makes a big difference.
</details>

另一个我想分享的注意事项是：要留意你如何看待来自不同“传感器”信号的有效性。举个例子，如果你在高速公路上开车，速度表突然不显示了，这并不意味着你当前的时速变成了零英里，那只是一个故障信号。在我们的自下而上方案中，有时也遇到了类似问题：系统根据某种断言认为“某个特定频道安静下来了，到底发生了什么？”但在现实中，我们把它当成了零活动信号，而实际上并不应该这样处理。因此我们随着时间不断迭代，去理解如何纳入我们上次尝试从该传感器获取信息的时间、它上次正常的时间，以及当这些信号产生分歧时该怎么做。
<details>
<summary>Original English</summary>
The other gotcha just I just want to share is to just be mindful of how you think about the validity of signal coming from different so-called sensors. If you're driving down a highway for example and your speedometer just you know just goes to just disappears, it doesn't mean you're now going at zero miles an hour, right? It's just like a faulty signal. So for example here we ran into a couple of issues sometimes when the bottoms-up approach, you had some semblance of a claim saying hey this particular channel, this thing is is going quiet, what's going on? But in reality, you know we were treating it as a zero when really it shouldn't have been. And so we sort of iterated over time to understand how to incorporate when we last tried to get information from that sensor, when it was last okay and what do you do when these diverge.
</details>

### 应用场景与未来挑战

现在如果看我们构建的实际记录，Agent 在理解世界的真实状态方面将会有效得多：状态并不是绿色的，上线日期推迟了两次，证据显示为黄色，大家在讨论测试失败的情况，进展将会很棘手。
<details>
<summary>Original English</summary>
So now if you look at the actual record that we constructed, the agents are going to be much more effective in understanding the true state of the world, right? It it it it's not green, right? It it's the go-live slipped twice, the evidence is yellow, people are talking about failing tests. It's going to be tricky.
</details>

那么我们用它来做什么呢？我们用它来引导领导层的讨论。与其向每个人传阅一份大家都只是草草翻过的演示文稿，不如直接从真正重要的事情切入，从文稿与证据不一致的地方谈起。
<details>
<summary>Original English</summary>
So what do we use this for, right? We use it to steer leadership conversations. Instead of you know circulating a deck to everyone and forcing everyone to just go through some slides everyone glosses over, you start with the stuff that actually you know matters. You start where the deck and the evidence disagree.
</details>

我们还会为管理层和领导者生成每周简报，汇报哪些工作卡住了、哪些项目沉寂了。但我认为最重要的是，你拥有了一个每个 Agent 都能依赖的上下文层雏形。
<details>
<summary>Original English</summary>
You also produce a weekly read for managers and leaders on what stuck and what went quiet. But I think also most importantly you have the sort of beginning of a context layer that every agent can rely on.
</details>

我们正在使用这一模式，并将其构建为可扩展到其它不同使用场景的形式。例如在我们的客户业务部门，我们很好奇如何构建类似的模型来协助服务客户。已知我们有某个客户，我们希望通过汇集来自各种分散的内部和外部源头的信息，尽可能预测他们的需求，了解谁持有何种资产、他们对什么感兴趣。
<details>
<summary>Original English</summary>
And we're using this pattern and constructing it so that it's extendable to other different use cases, right? In our client franchise for example, we're curious about how we can build similar models to help serve our clients. We know we have some client and we want to understand who holds what, what are they interested in, how can we anticipate their needs as best as possible by folding in information from all sorts of disparate internal and external sources.
</details>

有两件事做起来很困难，或许我们可以在场外交流一下你们的解法，我非常想听听看：
1. 当你面对大量碎片记录时——例如一个客户在四个不同系统中拥有四条记录，却没有规范的统一标识符——你如何以一种非常优雅的方式进行映射？对于这个问题，我不认为我们已经有了明确的答案。
2. 我们如何才能最有效地从利益相关者和用户那里捕获信号？当模型确定且风险较低时，我们应当直接自动应用；当风险较低但模型不确定时，只需等待更多证据；但如果涉及重大风险，向谁询问、何时询问以及整个互动机制就会变得至关重要。
<details>
<summary>Original English</summary>
So, a couple of things are difficult to do, just to kind of maybe we can chat outside about your solutions. I'd be very curious to hear. Are when you have a lot of, you know, for example, one client with four records in four different systems with no canonical identifier, how do you go about mapping those in a very elegant way? That's one thing that I don't think we have a clear answer to. The second thing is how can we both be most effective at capturing signal from stakeholders and users? Where the model is sure and the stakes are pretty low, we should just apply it automatically. When if those stakes are low, but you you know, the model's unsure, just wait for more evidence. But if the stakes are high, it really matters like who you ask, when you ask it, and kind of the whole mechanism there.
</details>

再次回顾这个循环：**更新、时效老化、观察、评级、纠偏**。我想请大家带走三点体会：
1. 你们公司拥有的模型，应当被视为一个**状态估计器**。不要认为仅仅把所有东西索引和编目一遍就足够了，因为根据定义，这些事情极其微妙，那些存在于字里行间的内隐信息，即便是最顶尖的模型也难以捕捉。
2. **对照接下来发生的事情进行评级**。要深思熟虑，从一开始就思考如何整合并落地评估评测。
3. 思考一套优雅的解决方案，让你的模型、Agent 和业务利益相关者能够良好协同。
<details>
<summary>Original English</summary>
So, here's the loop again. Update, age, observe, grade, and correct. And three things I want you to take home. The model that your company has should you should think about it as a state estimator, right? Don't assume that just like indexing everything and cataloging everything is enough because by definition, these things are extremely nuanced and this intrinsic information that lives almost between the lines is hard for even the best state-of-the-art models to capture. Grade it against what happens next, right? So, be intentional and think through how you can integrate and implement evals from the get-go. And think about an elegant solution that allows your models and your and and your agents and your stakeholders to kind of play nice together.
</details>

你们的公司完全可以拥有一个针对自身的模型。如果你目前还没有开始收集数据，我鼓励你现在就开始收集。特别是如果你身处规模较大的公司，像我一样有幸或不幸地要处理成千上万份演示文稿，那绝对是你应当开始考虑的事情。因为我确实亲眼见证了这些 Agent 在重构企业记忆并将其应用于各类日常任务时所带来的实质性改善，而不会对各种状况感到毫无头绪。
<details>
<summary>Original English</summary>
Your company can have a model of itself. I encourage you to start collecting now if you're not collecting already. And certainly if you have, if you're at a bigger company and like me you had the I mean fortune or misfortune of dealing with thousands of decks, uh definitely something you should start thinking about because I I've definitely seen material improvements in how these agents are able to reconstruct that sort of corporate memory and and apply it in all sorts of daily tasks uh without sort of being all confused about things.
</details>

好的，非常感谢大家。我是 Joel，大家如有疑问我会在场外交流。祝好。

[掌声]
<details>
<summary>Original English</summary>
Okay. Thank you very much. I'm Joel and I'll be outside for any questions if you want. Cheers.

>> [applause]
</details>