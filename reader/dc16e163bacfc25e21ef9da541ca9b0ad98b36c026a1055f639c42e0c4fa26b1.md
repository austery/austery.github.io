---
author: Bloomberg Podcasts
date: '2026-04-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=sVfWn4PQ7vM
speaker: Bloomberg Podcasts
tags:
  - ai-progress-measurement
  - ai-safety
  - ai-autonomy
  - exponential-growth
  - benchmark-methodology
title: 解析AI最热门图表：Meter时间线图背后的AI能力与风险评估
summary: 本期播客深入探讨了AI领域备受关注的Meter时间线图表，该图表衡量AI完成工程任务的能力并显示出指数级增长。Meter作为一家非营利研究机构，致力于评估AI可能带来的灾难性风险，并利用这些图表揭示AI自主性增强对人类控制构成的潜在威胁。节目详细介绍了Meter的测量方法、对工程任务的侧重、AI能力倍增速度的加速趋势，以及AI快速发展与安全保障之间的紧张关系。嘉宾还讨论了吸引顶尖人才投身AI安全研究的挑战，以及私营企业在追求技术进步时可能面临的道德困境。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Meter
  - OpenAI
  - Anthropic
products_models:
  - Claude Opus 4.6
  - GPT-5.3 Codex
  - Gemini 3 Pro
  - GPT-4O
media_books: []
status: evergreen
---
### AI能力飞速增长与Meter图表

**Joe Weisenthal**: 大家好，欢迎收听《奇闻异事》播客的又一集。我是**Joe Weisenthal**。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Hello and welcome to another episode of the Odd Lots podcast. I'm Joe Weisenthal.

</details>

**Tracy Alloway**: 我是**Tracy Alloway**。Tracy，关于AI有一件事，就是有很多曲线都在向上。

<details>
<summary>Original English</summary>

**Tracy Alloway**: And I'm Tracy Alloway. Tracy, one thing about AI is that lots of lines that go up.

</details>

**Joe Weisenthal**: [笑声]

<details>
<summary>Original English</summary>

**Joe Weisenthal**: [laughter]

</details>

**Tracy Alloway**: 是的，众所周知，在所有向上走的曲线中，可能有一条曲线比其他任何曲线都更引人注目。是的，我们正在4月7日录制这期节目。你有没有看到**Anthropic**的营收图表？简直是极端，曲线向上增长的程度。我的意思是，有一些，我只是想说明一下。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Uh yes, famously there is perhaps one line that has captured the attention more than others when it comes to lines going up. Yes, but we're recording this April 7th. Did you see the **Anthropic** revenue chart, by the way? It's just extreme. It's just on the number of lines going up. I mean, there are some some really I just Let me caveat that.

</details>

**Joe Weisenthal**: 直到最近，有一张线图呈指数级上升，我认为可以公平地说，它成为了AI领域最热门的图表，对吧？是的，我完全同意。所以，在众多向上走的曲线中，有一条以某种方式捕捉了AI进展的衡量标准，以及它们能做什么。模型的能力等等，你知道，市面上有各种不同的基准，还有业余的基准创建者等等。各种各样的基准都有。一个叫做**Meter**的组织，总部设在旧金山，他们衡量AI模型在工程任务等方面的表现。他们有这些图表，显示某些任务需要多长时间，人类需要多长时间来完成，然后AI是否能完成，是的，这些曲线几乎是垂直的。我想大概在今年年初或去年年底，有一个图表显示了最新的**Claude**模型，简直是太疯狂了。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Up until recently, there was one chart of a line going up exponentially that became, I think it's fair to say, the most viral chart in AI, right? Yes, I would absolutely agree with that. So, one of the many lines that go up, and there are various lines that sort of capture this, is essentially just measures of AI progress and what they could do. What the models are capable of and so forth, and you know, there's all different benchmarks out there and hobbyist benchmark creators, etc. All kinds of benchmarks out there. An organization called **Meter**, based out in San Francisco, and they measure how well AI models are doing sort of engineering tasks, etc. And they have these charts showing how long, you know, certain tasks, how long it would take a human to do them, and then whether AI could do them, and yes, the lines just almost vertical. I think there was someone like one of the ones that came out maybe very early this year or late last year showing the latest **Claude** model, and it was just like, this is crazy.

</details>

**Tracy Alloway**: 当我看到这些图表时，它们被称为**时间线图表**。当我看到它们时，我直观上能理解它们在说什么，你也能看到一些之前的模型和**Claude**（最新的**Claude**模型）之间在进步上的飞跃。这就是让所有人兴奋的原因，你看到了那个特定AI模型能力上的巨大指数级提升。但是当我开始深入研究**Meter**网站上关于这些图表实际代表什么时，我开始感到非常困惑。我知道每个人都想对AI和普遍向上走的图表感到兴奋，但我认为这里有很多细微之处，我们可能应该讨论一下，因为**Meter**目前正在发生的另一件事是，他们已经成为行业标准基准。因此，很多投资决策都是基于这些图表的，如果你把它们过度简化为“曲线向上，然后突然又向上更多”，显然人们会开始变得有点过于兴奋。

<details>
<summary>Original English</summary>

**Tracy Alloway**: When I look at these charts, they're called **time horizon charts**. When I look at them, I like intuitively I kind of understand what they're saying, and you can kind of see the leap in progress between some of the previous models and **Claude**, right? The latest **Claude** model. And that's what got everyone excited was you had this big exponential shift up in the capability of that particular AI model. But then when I start like diving into what it actually says on **Meter**'s website about what these charts represent, I start getting really confused. I know everyone wants to get excited about AI and charts going up in general, but I think there's a lot of nuance here, and we should probably talk about it because the other thing going on with **Meter** right now is they've become sort of the industry standard benchmark. And so, a lot of investment decisions are being based on these charts, and if you oversimplify them as just like, okay, lines going up, and then suddenly it goes up even more, obviously people are going to start to get like maybe a little overexcited.

</details>

**Joe Weisenthal**: 我还能说一件事吗？我也非常好奇。我很高兴有人设计各种基准来衡量AI的进展。这似乎是一件很重要的事情。但是，如果我像，比如说，有足够的天赋或聪明来做这些事情，我就会去其中一个实验室工作，每年赚1000万美元之类的。所以我实际上很好奇，因为很多非营利组织等等，就像，你真的想在非营利组织从事AI的前沿工作吗？我的意思是，我想**OpenAI**是由一个非营利组织拥有的，这很奇怪。但你明白我的意思吗？我想要钱。好吧，我们应该和我们的嘉宾谈谈，他们现在就坐在这里。[笑声]没错。我很高兴地说，我们有两位完美的嘉宾来谈论目前AI领域最热门、也许最重要的图表。我们将与**Joel Becker**对话。他是**Meter**的技术人员，我们还将与**Meter**的总裁**Chris Painter**对话。所以，**Joel**和**Chris**，非常感谢你们来到《奇闻异事》。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Can I say one other thing, too, that I'm very curious about? Like, I'm really glad that there are people designing various benchmarks for measuring AI progress. Seems like an important thing to get a handle on. But like, if I were like, say, like talented or smart enough to be like doing these things, I would go work for one of the labs and make $10 million a year or something like that. And so, I'm actually curious because a lot of nonprofits, etc. It's like, do you really like want to be like working at the cutting edge of AI at a nonprofit? I mean, I guess it **OpenAI** is owned by a nonprofit, weirdly enough. But you know what I'm saying? Like, I would want the money. Well, we should talk about it with our guests who are currently sitting right here. [laughter] That's exactly right. I'm very excited to say we have the two perfect guests to talk about the most viral and maybe important chart in AI right now. We're going to be speaking with **Joel Becker**. He is a member of the technical staff at **Meter**, and we're also going to be speaking with **Chris Painter**, the president of **Meter**. So, **Joel** and **Chris**, thank you so much for coming on Odd Lots.

</details>

**Chris Painter**: 非常感谢邀请我们。

<details>
<summary>Original English</summary>

**Chris Painter**: Thank you so much for having us.

</details>

**Joel Becker**: 是的，感谢邀请我们。是的，很高兴能和你们两位聊天。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, thank you for having us. Yeah, really excited to chat with both of you.

</details>

**Joe Weisenthal**: **Chris**，既然你是总裁，我先从你开始。**Meter**是什么？它成立多久了？这个组织是什么？它的目标是什么？请给我们一个关于**Meter**的60秒概述。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Chris, since you're the president, I'll I'll start with you. What is **Meter**? How long has it been around? What is this organization? What's its goal? Just give us the the sort of 60-second synopsis of **Meter**.

</details>

### Meter的使命与时间线图表

**Chris Painter**: 是的，完全可以。我可以说说，你知道，有时我会说长版本，我在这里可以尝试说短版本。所以，**Meter**是一个位于湾区的研究型非营利组织，就像你说的，致力于推进衡量AI系统何时以及是否可能对全人类构成灾难性风险的科学。我们特别关注来自AI自主性或AI系统本身的威胁。所以，当你谈论AI领域中“危险能力评估”的整个领域时，人们会看到：“这个AI系统能否协助化学或生物武器袭击？它能否提升不良行为者大规模执行网络攻击的能力？”**Meter**专门评估AI系统的自主性有多高，它们能够独立完成的任务的规模、时长和难度。部分原因是，我们认为这为关于AI失调的讨论设定了赌注。所以，我们认为自己有责任在任何特定时间点向人类提供最有信息量的证据，以确定赌注：我们社会是否以一种方式依赖AI系统，如果它们失调，情况可能会变得非常糟糕？

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, totally. I can try and you know, sometimes I give a long version, I can try and do a short version here. So, **Meter** is a research nonprofit based in the Bay Area, like you said, dedicated to advancing the science of measuring whether and when AI systems might pose catastrophic risks to humanity as a whole. Focused specifically on threats that come from AI autonomy or AI systems themselves. So, when you talk about this kind of this whole field in AI of dangerous capability evaluations, people seeing, can this AI system assist with a chemical or biological weapon attack? Can it advance kind of like bad actors' ability to execute cyberattacks on a really large scale? **Meter** is sort of specialized in specifically assessing how autonomous are AI systems, what is the scale and like length and difficulty of tasks that they're able to do by themselves, partially because we think it sets the stakes for conversations about AI misalignment. So, we sort of see ourselves as being on the hook for at any given point in time giving humanity the bits of evidence that are most informative for establishing the stakes of, are we reliant on AI systems as a society in a way that could make it really bad if they are misaligned?

</details>

**Joe Weisenthal**: 我稍后会让**Joe**问你们为什么都在非营利组织工作而不是在实验室，但我确实有一个问题：当我想到**Meter**时，你们总是出现在这些**时间线图表**的背景中，我并不是要侮辱或什么的，但我几乎从未听任何人谈论过你们使命中实际的安全方面。你认为这是为什么？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: I'm going to let Joe ask the question about why you're both working at a nonprofit instead of one of the labs later, but one question I do have is when I think of **Meter**, you guys always come up in the context of these **time horizon charts**, and I I don't mean this as an insult or anything, but I hardly ever hear anyone talk about the actual like safety aspect of your mission. Why do you think that is?

</details>

**Chris Painter**: 是的，我认为我们的动机与它被世界其他地方使用的方式或世界其他地方对此感兴趣的起源之间存在一些区别。对于**Meter**来说，我认为我们之所以研究像**时间线图表**这样的东西，是因为如果我们试图为讨论设定赌注，即AI系统是否会失控，或者有一天它们是否会试图接管并颠覆人类控制？三年前，如果你回到**Meter**大约四年前刚开始的时候，如果你当时回去说，“我为什么不认为AI系统今天会失控并接管或推翻人类？”最直观的，你知道，你可以提出很多抽象的原因，关于AI系统最终可能或不可能拥有的目标的辩论，但当下最致命的原因是AI系统根本做不了多少，对吧？谈论一个甚至不能可靠回答编程问题的问答系统，说它会入侵我的系统或以某种方式给我开后门，这根本没有意义。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, so I think there's some distinction between our motive for assessing time horizons and the kind of how it gets used then by the rest of the world or kind of like what the origin of the rest of the world's interest in it. For **Meter**, I think the the reason that we work on things like the **time horizon charts** is because if we're trying to establish the stakes for talking about, could AI systems go rogue or one day could they like try to take over and subvert human control? Three years ago, if you went back to around when **Meter** started about four-ish years ago, and if you it was started by **Beth Barnes**, **Paul Christiano**, and this was kind of the initial motive, is if you went back then and you said, why don't I think that AI systems are going to go rogue and like take over or overthrow humanity today? The kind of most intuitive, you know, you can come up with a lot of abstract reasons, debates about the goals AI systems might or might not eventually have, but the kind of most damning in the moment reason is the AI system just can't do much, right? It doesn't make sense to talk about a question-answer system that like can't even reliably answer programming questions saying like, is it going to hack my systems or like backdoor me in some way? It just doesn't make any sense to talk about that.

</details>

**Joe Weisenthal**: 它会为你写一首你要求的诗。[笑声]对。或者它甚至不会。当时，它们自己什么也做不了。所以，如果你能颠覆人类控制，这取决于**自主性**。所以我们想出了一个衡量标准，可以随着时间跟踪**自主性**，以说明这个论点何时不再适用？AI系统何时能够自己完成足够长、足够复杂的行动，以至于论点，目标几乎转移到别处，比如“我们会抓住AI”或者“AI不想颠覆人类控制”。所以，我同意，我认为这之间存在区别，比如我部分认为，试图提出这些衡量标准的实践会产生一些非常扎实和直观的AI进展衡量标准，这些可能比仅仅是基准更直观，对吧？所以，如果你很多人都在玩制作基准的游戏，你可能会说，“这是我的危害基准”或者什么的，AI得到70%。这远不如一个扎实或持久的指标。比如，很难说这意味着什么，或者它如何泛化。但**时间线**的想法是，也许它更直观，我认为这有助于安全和商业理解。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: going to write you a poem that you asked for. [laughter] Right. Or it won't even At the time, they couldn't do anything by themselves. And so, if you're like kind of being able to subvert human control depends on **agency**. And so, we wanted to come up with a measure that kind of tracks **agency** over time to kind of say, when would this argument no longer apply? When are AI systems now able to kind of do long complex enough actions by themselves that the argument kind of the goalposts almost move somewhere else to like, well, we would catch the AIs or the AIs don't want to subvert human control. And so, I agree that there is a distinction between like how I think partially the exercise of trying to come up with these measures throws off things that are very like grounded and intuitive measures of AI progress that might be more intuitive than just benchmarks, right? So, if you a lot of people are in the game of making just benchmarks where you say like, here's my harm bench or something, the AI gets 70%. That's much less of a kind of grounded or long-lasting metric. Like, it's hard to say what that means or how that generalizes. But the idea with **time horizon** is like, maybe it's more intuitive, and I think that helps both for safety and for like business understanding.

</details>

### 时间线图表测量方法

**Joe Weisenthal**: 那么，让我们谈谈这张图表。**meter.org**的主页上，就是这张**时间线图表**，它显示**Claude Opus 4.6**在2026年2月能够以50%的成功率完成11小时59分钟的任务。我必须承认，我第一次看到这张图表或其版本时，我以为（我怀疑其他人也这么以为）它能够独立完成一项任务11小时59分钟，然后给出答案。但显然不是那样。你能不能给我们解释一下，这里真正衡量的是什么？顺便说一下，之前的最高纪录是**GPT 5.3 Codex**，是5小时50分钟。所以，我想这张图表之所以让人大吃一惊，部分原因是因为它几乎翻了一倍。但是，你能不能告诉我们这里真正衡量的是什么？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So, let's talk about what this chart I you go the the main chart here of meter.org right on the front page, it's this **time horizon chart**, and it shows **Claude Opus 4.6** as of February 2026 able to complete a task length in 11 hours and 59 minutes with a 50% success rate. I have to admit, the first time I saw this chart or versions of this chart, what I assumed, and I suspect others assumed, is that it was able to go off and work on a task for 11 hours and 59 minutes and then come back with an answers. But apparently it's not that. Why don't you walk us through like, what's what's really being measured here? By the way, the previous high was all was **GPT 5.3 Codex**. That was 5 hours and 50 minutes. So, I guess part of the reason this chart has blew people's minds cuz literally that's basically a double. But why don't you talk to us about what's really being measured here?

</details>

**Joel Becker**: 是的，所以从根本上说，你知道，简单来说，我们正在绘制AI能够随时间完成的任务的难度。你知道，我们衡量任务难度的特定方式是，人类完成我们要求AI做的相同任务需要多长时间。所以，在这种情况下，你知道，我们谈论的是**Opus 4.6**，它能够以大约50%的成功率完成人类需要12小时才能完成的任务。是的，你知道，事实证明，当你使用这种特定的难度衡量标准来绘制AI相对于人类完成这些任务所需时间的表现时，我们看到了AI能力呈指数级增长。这意味着，每隔大约四个月，根据最近的趋势，能力就会翻倍，你知道，下一个模型不一定会比前一个模型的时间线长一个小时，而是可能会是它的几倍。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, so so fundamentally, you know, in simple terms, we are plotting the difficulty of tasks the AIs are able to complete over time. And you know, the particular way that we measure the difficulty of tasks is in how long it takes humans to complete those same tasks that we're asking the AIs to do. So, in this case, you know, we're talking about for **Opus 4.6**, something like tasks that take humans 12 hours to do, we predict that it will succeed at those tasks around 50% of the time. And yeah, you know, it turns out that that when you plot using this particular difficulty measure how performant AIs are relative to how long it takes humans to complete these tasks, we see an exponential increase in capabilities for AIs. And what that ends up meaning is that you keep on having these doublings of of capabilities every, let's say, four months it seems on recent trends, where you know, the next model is not merely going to have necessarily, you know, an hour longer time horizon, but but perhaps be having some multiple of the time horizon of the of the previous model that's come out.

</details>

**Joe Weisenthal**: 那么，请解释一下这个12小时的数字是如何确定的。也就是说，有一个工程任务，你说，好的，这是一个需要12小时的任务。但是人类有各种不同的才能和能力。你们如何确定，好的，这是一个12小时的任务，这是一个6小时的任务，这是任何它是什么的任务。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So, then explain how that number, that 12 hours, is established. So, there is some engineering task, and you say, okay, this is a task that would require 12 hours. But humans have all different types of talent, capabilities. How do you establish that, okay, this is was a 12-hour task this was a 6-hour task this is whatever it is.

</details>

**Joel Becker**: 是的，所以简单的答案是，我们真的让人们坐下来完成我们交给AI的任务，尽可能在相同的条件下。所以首先我们提出任务，你知道，那是一个完整的问题，我们可以谈谈我们具体如何做到这一点。然后，基本上使用我们即将交给AI的相同工具，我们找来有才能的人，你知道，不是那些以前见过这种特定类型任务的人，而是那些具有相关专业知识的人。所以，如果是软件工程任务，你知道，他们有软件工程专业知识；如果是机器学习任务，他们有机器学习专业知识。然后我们计时。我们看看他们成功完成这些任务需要多长时间，然后我们大致将任务的难度（以人类完成时间衡量）定义为这些人完成任务的平均时间。然后我们会在同一组任务上运行AI，通常今天对于最简单的任务，它们或多或少总是会成功。有一些中等难度的任务，你知道，它们可能成功50%的时间，或者对于该范围内的某些任务，它们成功0%的时间，而对于其他任务则成功100%的时间，所以它们平均成功50%。然后对于更难的任务，它们可能接近0%。然后我们预测，你知道，在所有这些任务的0%和100%之间，我们预测它们有50%的成功机会，这要么是在某个任务上成功50%的机会，要么是该难度下我们认为它们会成功的50%的任务，这就是我们所说的这些模型的**时间线**。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah so so the simple answer is literally we get humans to sit down and complete the tasks that we give to AIs under as close to identical conditions as possible. So first we we come up with the tasks and that's you know that's a whole kind of kettle of fish we can we can talk about exactly how we do that and then using essentially the the same tools that we're about to give the AIs we take talented humans you know not people who have seen this particular type of task before but people who have relevant expertise. So if it's a software engineering task you know they they have software engineering expertise machine learning task they have machine learning expertise and then we time them. We see we see how long it takes for them to complete those tasks successfully and then roughly we call the difficulty of the task as measured in human times complete as the average time it took these humans to complete the task. Then we'll run the AIs on this same set of tasks typically today for the very easiest tasks that they're more or less always going to succeed. There's some mid-range of tasks where you know perhaps they succeed 50% of the time or perhaps for some tasks in that range they succeed 0% of the time and for others 100% of the time and so they're getting 50% on average let's say and then for the much harder tasks perhaps they're getting closer to 0% and then [snorts] the point at which we predict you know in the middle of all of these 0% and 100% by task the point at which we predict that they'd have a 50% chance of succeeding that is either a 50% chance of succeeding on some task or 50% of the tasks of that difficulty that we think they would succeed on that's what we're going to call the **time horizon** of these models.

</details>

**Chris Painter**: 我认为这里还需要解释的一点是**任务分布**。我的意思是，这并不是人类所做的所有活动，我们在这里特别感兴趣的是，或者说，有一个问题是，哪些任务是，你知道，就像**Joe**提到的，我们让人来到我们的办公室完成任务，以了解需要多长时间。我们不是让他们来画画或写小说，你知道，我们在这里特别关注的是**前沿AI实验室**的工程师可能正在做的工作范围内的任务。所以，这包括软件工程、AI模型微调，以及软件机器学习这类任务。

<details>
<summary>Original English</summary>

**Chris Painter**: I think one thing also that could be good to explain here is the **task distribution**. I mean this is not this is not all activities that humans do we are specifically here interested in or the like there's some question in what tasks are you know like Joe mentioned we're having people come into our office do the task to get a sense of how long it takes. We're not having them come in and like you know paint paintings or write novels or you know we're we're focused here specifically on things that are in the distribution of work that a um engineer at a like we like to think of it as like a **frontier AI lab** the tasks that they might be doing. So this is things like **software engineering** it's **fine-tuning AI models** it is like **software machine learning** that kind of task.

</details>

**Tracy Alloway**: 等一下，我能问一下你们为什么决定专注于工程任务吗？因为你们可以把它扩展到，你知道，如果我们谈论AI能够接管世界，那会有各种各样的实质性任务属于这个范畴，那么为什么只做工程任务呢？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Wait can I just ask why did you decide to focus on engineering because you could have widened it out to you know if we're talking about AI being capable of you know taking over the world there are all sorts of substantive tasks that would fall under that category so why just do engineering?

</details>

**Chris Painter**: 是的，我想一方面，也许团队里的其他人，也许**Joe**对此有想法，但我个人对软件任务的**时间线**感兴趣的动机是，首先，这是行业非常关注的事情，甚至在我们开始研究这个之前就已经很关注了，所以这是你预期最早出现的能力之一，这是很多优化压力正在施加的地方。然后我认为，这是一种早期预警的迹象，表明AI研发自动化。所以，在某种程度上，**Meter**认为自己正在尝试构建科学，或者说先进的科学，可以说明我们何时达到AI系统能够自我改进或加速AI发展步伐的程度，何时AI研究会自我滋养，而这方面的核心能力可能是软件工程和机器学习研究能力。还有其他技能可能与接管世界相关，嗯，我想其他人也做过像网络安全方面的时间线研究。是的。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah I think that for one thing maybe other people on the team are maybe Joe has thoughts about this but I think my particular motive in being interested in the time horizon on software tasks is that first of all it's the thing that the industry is very like already even before we started working on this is very focused on so it's one of the capabilities that you should expect to come along for the ride earliest it's the thing that like a lot of optimization pressure is being exerted on and then I think that it is kind of the like thing that you would expect as an early warning kind of sign of this **AI R&D automation**. So to some extent **Meter** thinks of itself as trying to build you know science that or advanced science that can say when are we getting to the point that AI systems could improve themselves or speed up the pace of AI development when will AI research kind of feed on itself and the kind of core capability for that might be **software engineering** and **machine learning research ability**. There are other skills that could be relevant to taking over the world um I think other people have done time horizons on like **cyber security** since yeah.

</details>

**Joe Weisenthal**: 但我想确实如此，像**巴兹利斯克**（basilisk）不会通过画画来获得权力之类的。好的，另一个可能会欺骗你，你可能会以某种方式非常具有说服力或狡猾，然后交出钥匙。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: But I suppose it is true like the basilisk isn't going to paint its way into like power or something like that. Okay the other might deceive you you might be very convincing or cunning in some way and hand over the keys.

</details>

**Chris Painter**: 我可能会说一些心智模型，你知道，我们没有任何完美的证据，但我粗略的理解，无论是口语上还是在证据出现之前的先验判断，是如果我们研究这些非常不同的任务分布，你知道，不是机器学习，不是软件工程，我不确定绘画，但你知道，也许我们可以列举的其他类型的任务分布，基本上我们会看到这种类似形状的指数级进展，随着时间的推移，每隔，我不确定具体时间，但比如说，你知道，4个月、6个月之类的，以**时间线**衡量的能力水平会以类似的速度翻倍，可能从一个低得多的水平开始。所以，你知道，我们确实有更好证据的一个例子是，今天的AI在任何需要视觉能力、查看屏幕、在电脑上点击操作的事情上表现要差得多，但它们在这类事情上的能力正在大幅提高。

<details>
<summary>Original English</summary>

**Chris Painter**: I might say a few a few mental models you know we don't have perfect evidence of this whatsoever but my rough sense sort of colloquially or you know my prior before evidence comes in is that if we did study tasks on these very different distributions you know not machine learning not software engineering I'm not sure about painting exactly but you know perhaps other kinds of task distributions that we could enumerate that basically we would see this similarly shaped exponential progress over time where every I'm not sure exactly but let's say you know 4 months 6 months something like that the level of capabilities as measured in **time horizon** would be doubling at something like that pace maybe from a much lower level. So you know one example that we do have better evidence of is that the AIs today are much less performant at you know anything that requires **vision capabilities** seeing what's on a screen clicking around at a at a computer but they're getting you know tremendously better at that at that sort of thing over time.

</details>

**Joel Becker**: 我只是想快速提一下，我们确实对其他任务分布进行了非常简短的调查，这在我们的网站上某个地方，比如“**跨领域时间线**”，我想我们查看了**特斯拉**分享的关于自动驾驶的数据。我忘了其他的，还有像操作系统世界，也许其中一些仍然与软件任务的分布有些相似，但我们试图将其扩展到像视觉这样的领域。

<details>
<summary>Original English</summary>

**Joel Becker**: I just do mention quickly we did actually do a very kind of brief investigation of this on other task distributions that's on our website somewhere like **cross-domain time horizons** I think we looked at data from the **Teslas** shared on **self-driving** I'm forgetting the other there's like **OS world** maybe some of these are like somewhat similar still kind of in the distribution of software tasks but trying to get further afield into things like **vision**.

</details>

### 测量挑战与50%成功率的考量

**Joe Weisenthal**: 实际工作的那些人类的样本量有多大？另外，让像人类工程师来与**Claude Opus 4.6**竞争，是不是越来越难了？比如说，如果我是一个平庸的工程师（我不是，我是一个不存在的工程师），但如果我是一个平庸的工程师，我可能会觉得与**GPT-3**之类的竞争感觉还不错，但如果与**Claude**竞争，我可能会感觉糟糕得多。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: How big is the sample size on the humans who are actually doing work? And also is it getting harder getting like human engineers into the room to compete with like **Claude Opus 4.6** versus say if I was a mediocre engineer and I'm not I'm a non-existent engineer but if I was a mediocre one I would like maybe I would feel good about going up against like **GPT-3** or something and maybe I would feel a lot worse about myself going up against like **Claude**.

</details>

**Joel Becker**: 是的，你知道，在这些任务上，我自己的处境和你差不多。所以我们每个任务大约有三个人类基准，尽管在不同任务之间差异很大，所以你知道，我们通常会取大约三个的平均值。我认为最终的数字，我的印象是它们对我们选择的特定基准不会那么敏感。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah you know on these tasks I'm in I'm in a pretty similar position myself to you. So we have approximately three although it varies quite a lot across tasks human baselines per task so you know typically we're averaging over something like three. I think the the final numbers it's my impression that they're not going to be so sensitive to the particular baselines that we choose.

</details>

**Chris Painter**: 较长的任务基准是不是更弱？

<details>
<summary>Original English</summary>

**Chris Painter**: Aren't the longer tasks weak more weakly baselined?

</details>

**Joel Becker**: 是的，所以确实如此，我认为随着AI能够成功完成的任务长度越来越长，对这些任务进行基准测试会变得越来越困难。你知道，你可能会认为在某个时候，它们能完成的任务长度会超过**倍增时间**。你知道，在4个月内，它们将能够完成超过4个月的任务，然后，你知道，获得这些4个月长的基准可能变得几乎不可能。当然，我们还没有到那个地步，但你知道，随着时间的推移，获得这些基准确实变得更加困难。目前并非不可能，但非常具有挑战性。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah so so indeed I think it will get a lot harder to baseline these tasks as the length of tasks the AIs are able to successfully complete gets longer and longer. You know you might think at some point the length of task that they can complete is longer than the **doubling time**. You know in in 4 months time they're going to be able to complete tasks of more than 4 months and then it's you know kind of becomes perhaps close to impossible to get these 4 months long baselines. Of course we're not at that point yet but you know definitely it has become more difficult to get these baselines as as time has gone on. At the moment not impossible but but very challenging.

</details>

**Tracy Alloway**: **Joe**，这些是未来被取代的工程师的工作，对吧？是为了基准测试目的而与代码竞争。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Joe these are the future jobs for displaced engineers right? It's competing against the codes for benchmark purposes.

</details>

**Joe Weisenthal**: 年度基准。我们找到了工作。所以我们一开始提到，AI领域最热门的图表就是你们网站首页上的这张图表，你们的网站默认显示这张图表，它显示了这种**倍增**。所以，如果我们回到比如说2025年11月，**Gemini 3 Pro**是3小时44分钟，**Claude Opus 4.6**是12小时。这是在50%成功率的基准下。如果我们看80%的基准（网站没有默认显示），改进的速度在我看来就没那么令人印象深刻了。所以，现在它显然没有相同的差距。现在80%仍然不是100%，我知道**Meter**的目标是关于人类安全等等，但当我们想到人们看到这个并将其用作衡量这些模型性能的替代品时，即使是80%，你知道，对于任何商业应用来说，也可能不够好。我理解你们并非专门服务于商业，但企业可能关心这个。当你查看80%的图表时，它看起来不像50%的图表那么疯狂。为什么专注于50%的图表，而不是看那个看起来不那么令人印象深刻的图表呢？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: benchmark of the year We found the jobs. So we mentioned at the beginning the most viral chart in AI is this chart that you have on the front of your website your website defaults to this and it shows you know this **doubling**. So if if we actually like go back to November let's say November 2025 **Gemini 3 Pro** 3 hours and 44 minutes **Claude Opus 4.6** 12 hours. That's at the 50% success benchmark. If we go to the 80% benchmark which the website doesn't default to the improve the pace of improvement looks a little less impressive to me. So okay now it's like it does not have the same gap pretty clearly. Now 80% is still not 100% and I know that this is your **Meter**'s goal is about like you know human safety and all this stuff but when we think about people look at this and they use it as a stand-in for how performant are these models even 80% you know certainly for like any business application. I understand you're not like serving business here per se but probably businesses care about this. Even 80% may not be very good enough and it does not look as crazy when you look at the 80% chart as it does at the 50% chart. Why the focus on the 50% chart and given like why not look at the chart that just does not look as impressive?

</details>

**Joel Becker**: 是的，也许有两点核心内容。第一，在我看来，80%的图表基本上也同样令人印象深刻，或者说**倍增时间**大致相同。这是我的一部分应对。它[笑声]是相同的，是相同的增长，但有一个偏移。它是相同的进步速度，你知道，它比50%的数字小大约五倍，但你知道，这只需要两次倍增，如果每次倍增大约需要4个月，那意味着在8个月后，你将拥有与今天50%成功率大致相同的80%成功率。这是其中一点。也许第二点是，你知道，还记得我一开始说过，我们基本上是在绘制这些AI随时间可以完成的任务的难度，只是用这种特定的衡量标准，最终显示出这种清晰的指数趋势，我们选择了一个特定的数字作为我们的难度数字，你知道，那就是这个**50%可靠性阈值**。我们本可以选择一个不同的。我认为选择50%的数字有其原因，特别是从统计学上讲，我们能够更好地衡量它，出于一些技术原因，它在以前的文献中出现过，还有其他几个原因使我们选择50%而不是80%。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah maybe two central things to say. One to my eyes the 80% chart basically does look as impressive or the **doubling time** is about the same. This is cope on my part. It [laughter] was it's the same it's the same increase but at a an offset of It's it's the same pace of progress you know it's something like five times smaller than the than the 50% than the 50% number but you know that only takes you two doublings and if each doubling takes around 4 months that means that in in 8 months time you're going to have the same 80% success rate roughly as as you do 50% success rate today. That's one thing to say. Maybe a second thing to say is you know remember at the beginning I said essentially what we're doing is plotting the difficulty of tasks that these AIs can complete over time just with this particular measure that ends up showing this clean exponential trend and we've picked a particular number as our difficulty number and you know that that is this **50% reliability threshold**. We could have picked a different one. I think there are reasons for picking the 50% one in particular it's the one that's statistically we're we're better able to to measure for some for some technical reasons it's the one that shows up in previous literature that there there are some couple of a couple of other reasons why why we can go for 50% rather than 80%.

</details>

**Chris Painter**: 也许最后要说的是，这个50%的数字有点模糊，介于它能够完成50%的时间的任务，以及它能够完成100%的时间的50%的任务，还有它能够完成0%的时间的50%的任务。实际上，我认为情况介于两者之间，但更接近后者，即有些任务它以近乎完美的可靠性完成，而有些任务在该范围内它以非常低的可靠性完成。对于下游的经济应用，或者这些主要AI公司内部的应用，你知道，你可能会认为这在某种意义上更有利，即有些任务我们即使在非常具有挑战性的情况下也能获得100%的可靠性。

<details>
<summary>Original English</summary>

**Chris Painter**: Maybe a final thing to say is that this 50% number is sort of equivocating between these tasks it's able to complete 50% of the time and 50% of the tasks it's able to complete 100% of the time and 50% it's able to complete 0% of the time. And actually I think the situation is it's somewhere in between but it's a little bit closer to the latter where there are some tasks that it's completing with near perfect reliability and some tasks in that range that it's completing with very low reliability. And for downstream economic applications or for applications inside of these major AI companies or something you know you might think that that's more favorable in some sense that there are some of these tasks where we're getting 100% reliability even even for very challenging tasks.

</details>

**Joel Becker**: 我认为另外两件事可能有助于解释，你刚才说出于技术原因，在50%处测量最容易。首先，确实如此，50%是它对分布最不敏感的点，分布最“厚”，对吧？如果我说错了请纠正，但我的意思是，为了解决像95%这样的问题，你需要更多的样本，因为你需要有一些，你需要更多的样本才能达到那种精度。

<details>
<summary>Original English</summary>

**Joel Becker**: I think two other things may maybe it could be useful to just explain when you you said that there are technical reasons why it's easiest to measure at 50%. One like it is just the case that it is 50% is the point at which it is like least sensitive to like the distribution is kind of thickest right? I mean correct me if this is wrong, but my I mean, there are like to resolve something like 95% you would need way more samples because then you need to have some that are like you need way more samples to be able to resolve that level of precision.

</details>

**Chris Painter**: 我认为这张图有一些注意事项，但让我们说更极端的情况。你知道，假设我们关心的是99%。在这种情况下，如果我们有1%的**标签噪声**，引号和引号，如果，你知道，如果我们有时不小心把一些失败的任务评为通过，一些通过的任务评为失败，那么我们就永远无法可靠地估计出来，对吧？好的。嗯，在50%的情况下，这会更接近于抵消。然后我认为这里还有另一个直观的方面，一个直觉是，如果你给我一个任务，你给我模型，我认为模型，如果你只告诉我**时间线**，即人类完成任务所需的时间长度，50%的**时间线**是我认为模型更有可能完成任务而不是不能完成任务的点。我只是觉得这很直观，是的。

<details>
<summary>Original English</summary>

**Chris Painter**: I think that there are some caveats to that picture, but but let's say even more extreme. You know, let's say that we cared about, you know, 99%. In that case, if we had 1% **label noise**, quotes and quotes, if you know, if sometimes we were accidentally grading some of the failing tasks passing, some of the passing tasks as as failing, then we just never be able to estimate that reliably, right? Okay. Um and at a 50% this comes a little bit closer to washing out. And then I think one other intuitive thing here, one intuition is that if you give me a task and you give me the model, it is the point at which I think that the model, if all you tell me is the **time horizon**, the length of task that it takes a human to do the task, the 50% **time horizon** is the point at which I think it is more likely that the model will be able to do the task than that it can't. And I just find that intuitive, yeah.

</details>

**Tracy Alloway**: 你们从潜在投资者那里对这些图表有多大兴趣？我问这个是因为我刚才随便查了一些东西，当**Opus**图表，最新的**Opus**图表出来时，有人把它发到**Reddit**上，我想第二个评论就是有人问：“我怎么投资**OpenAI**？”然后人们试图凑钱投资这些公司。所以很明显，有些人正在把这些图表当作投资工具。

<details>
<summary>Original English</summary>

**Tracy Alloway**: How much interest you got on these charts from potential investors specifically? And the reason I ask is because I was just messing around and like Googling some stuff and when the **Opus** chart, the latest **Opus** chart came up, someone posted it on **Reddit** and I think like the second comment on it was someone going, "How do I invest in **OpenAI**?" And like and like people were they were trying to club together to like invest in these companies. So clearly there are people out there who are using these charts as investment tools.

</details>

**Chris Painter**: 我会说，你知道，我们没有收到大量来自投资公司的咨询。我的意思是，有时，你知道，风投公司或什么的，我们总部在湾区，会联系我们。我认为这里有一些原则，我们的目标是告知公众，并向他们提供我们能提供的最佳证据，说明我们何时可能达到AI完全自主或能够自我改进的程度。这里有一些原则在起作用，就像我希望人们能够用这些信息做任何他们想做的事情。我认为我们不会过多参与工作的商业方面或投资影响。我有时会对自己说的一个思想实验是，如果我真的相信在某个时候我们会得到这种能够自我改进的AI，并且AI研究自动化了，你对奇点有各种担忧，我宁愿华尔街都错误地认为它不会到来，而我相信它会到来，还是我希望他们都知道它会到来，因为我相信它会到来？我认为全人类，这可能更多是个人观点，但我认为如果自动化AI研究是可能的，那么全人类都意识到它，意识到我们正在走向何方，是我们所有人能够弄清楚如何应对它的前提。所以，我不想让某些人或某一方或某个团队选择性地蒙在鼓里，因为他们可能会以此为基础进行投资或类似的事情。但我们没有，你知道，这不是我们投入时间的地方。我们专注于告知公众。公众包括一些投资者。

<details>
<summary>Original English</summary>

**Chris Painter**: I would say you know, we don't get an enormous amount of inbound from investment firms. I mean, sometimes, you know, VCs or whatever, we're based in the Bay Area will reach out to us. I think that there's some kind of principle of our goal is to inform the public and give them the best evidence that we can about when we might get to this point of kind of, you know, AI being, you know, fully autonomous or able to improve itself. And there's some principle at play here of like I kind of want to enable people to do whatever they will do with that information. And I think that we don't engage a ton in kind of the like business side or investment implication of the work. One kind of thought experiment I sometimes say to myself is, if I do believe that at some point we're going to get this AI that's improving itself and we're like AI research is automated and you have all these fears about a **singularity**, would I rather that like all of Wall Street like falsely didn't think that was coming when I believed it was coming or would I want them all to know that it was coming given that I believe it's coming? And I think all of humanity, maybe this is more of a personal view, but I think if this is possible that we will automate AI research, I think all of humanity being aware of it, aware of where we're heading is sort of a precondition for us all being able to figure out what to do about it. And so I don't kind of want like certain people or one side or one team to kind of like selectively be in the dark because they might invest on the basis of this or or something like that. But we don't, you know, it's not where we put our time. We're we're focused on informing the public. The public includes some investors.

</details>

**Tracy Alloway**: 那么，就此而言，我们所有人应该恐慌的实际水平是什么？或者说，如果一个政策制定者开始担心AI能够以最终对人类有害的方式自动化和自我改进，那么这个水平是什么？

<details>
<summary>Original English</summary>

**Tracy Alloway**: So on that note, like what is the actual level at which we're all presumably supposed to panic or at which like if you're a policy maker you would start to get worried about AI being able to automate and improve on itself in a way that eventually becomes detrimental to humanity?

</details>

**Joel Becker**: 我不知道这个**时间线**衡量标准的具体水平是什么。我认为，你知道，要说的一点是，我们在衡量这些AI系统及其能力的科学方面取得了真正的进展，但我认为还有很长的路要走，而且在重要的意义上，我认为我们在这项任务上是落后的。我们正在衡量一些潜在的技术趋势，在某些时候我确实认为这暗示着发生惊人事情的更大风险，尽管**Chris**可以更多地谈论我们可能退出的其他论点，即为什么即使AI能力很强，我们短期内仍可能看不到灾难性危险的出现。

<details>
<summary>Original English</summary>

**Joel Becker**: I don't know exactly what the level is on this **time horizon** measure. I think, you know, one thing to say is we have made real progress on the science of measuring these AI systems and how capable they are, but I think there's a long way to go and and in important sense I think we're behind on this task. We're measuring some underlying technical trend and some point I do think that's that implies greater greater risks of astonishing things happening, although Chris can speak more to other arguments that we might back out to for why even if AI is very capable we still might not see catastrophic dangers emerge in the short term.

</details>

**Chris Painter**: 是的，我不确定。你知道，我认为**AGI**（通用人工智能）的讨论之所以真正兴起，特别是在每个人都使用**Claude Code**之后，是因为很容易想象，你坐在那里，就像，“是的，做这个，做这个。”就像，“我甚至不需要在这里，对吧？”我认为你对人类如何能够脱离循环有一种非常直观的感觉。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, I'm unsure. You know, I think part of the reason why the **AGI** chatter has really picked up particularly in the wake of like everyone using **Claude Code** is it's very easy to imagine like you're sitting there it's like, yeah, do this, do this. It's like, I don't even need to be here, right? I think you sort of get a very intuitive feel for like how the human could come out of the loop.

</details>

**Joe Weisenthal**: 今天会发生什么，我相信这已经被尝试过了，比如如果你去**ChatGPT**，你说，“你现在有**Claude Code**的访问权限，去构建一些东西。”当AI与AI协作时，今天实际会发生什么？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: What happens today, as I'm sure this has been tried, like if you go to like **Chat GPT** and you say, here's a here you have **Claude Code** access, go build something. And the AI is, what actually happens today when AI is working with AI?

</details>

**Chris Painter**: 是的，我的感觉是，在某个时候，你知道，在一个比以前更远的未来，AI或多或少会失败。也就是说，你知道，今天它们在某些方面还不是那么有能力。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, my my sense is that at some point, you know, at a further away point than would have been true some some time ago, the AIs will more or less fall on their faces. That's that, you know, there are some things they're not so capable of today.

</details>

**Joe Weisenthal**: 比如**协作幻觉**，它们会像，你知道，只是退化成糟糕的东西吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Like collaborative hallucinations will they just like, you know, just like devolve into terrible

</details>

**Chris Painter**: 是的，我认为这有很多种可能。你知道，在某个时候它们需要依赖外部资源，而今天它们在有效管理这些外部资源方面能力不足。我认为它们在构思和对问题所处位置的自我认知方面，比在这些原始软件工程技能方面能力要差。你知道，就像你提到的，今天AI自主或接近自主的方式是人类有想法，然后，你知道，将这个想法提交给**Claude Code**或**Codex**或这些其他**代理AI工具**之一，然后它们处理软件工程部分。可能之后仍然有一些干预。我确实认为**自主性**的范围或类似的东西会随着时间变大。我确实认为AI拥有这些想法并提升到更高抽象层面没有根本障碍。但如果我们今天纯粹依赖这些完全自主的能力，你知道，你能在一家大型AI公司内部管理一个研究部门，或者你选择的任何部门吗？我的猜测是可能不行。嗯。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, I think all sorts of ways this this can go. You know, at some point they're going to need to rely on external resources and and and today they're they're not as capable at managing these external resources effectively. I think they're less capable at sort of **ideation** and sort of **self-awareness** about where they are in the problem today than they are at these kind of raw **software engineering skills**. You know, you know, as as you mentioned, the ways in which AIs are autonomous today or close to autonomous today is the human has the idea and then, you know, submits that idea to a **Claude Code** or a **Codex** or or one of these other **agentic AI tools** and then they handle the the software engineering component. And possibly there's still still some some intervention after that. I do imagine that the sort of circle of **autonomy** or something gets larger over time. I do think there's no fundamental barrier, it seems to me, to AIs having those ideas and and to be moved to a greater level of abstraction. But if we were purely relying today on on these fully autonomous capabilities, you know, could you manage research department, any any department of your choice inside of a major AI company, you know, my my guess is probably not. Mhm.

</details>

**Tracy Alloway**: 实际上，说到这里，这让我想起了一个我想问的问题。当你查看**领域特定时间线图表**时，就是那些显示，我想你们称之为**任务套件**之类的图表。比如，特定工作的生产力，你会看到这些不同的曲线。有时你会看到几乎是水平的曲线，有时你会看到波浪形或更陡峭的曲线。那里到底发生了什么？我们应该如何解释？这是测量问题，还是在非常根本地说明在当前条件下AI能做什么和不能做什么？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Actually, on this note, this reminds me something I wanted to ask. So when you look at the **domain-specific time horizon charts**, so the ones that show like, I think you call them **task suites** or something like that. Like I guess productivity by specific job and you see these different lines. So sometimes you see like almost horizontal lines and sometimes you see squiggly or steeper lines. What is actually happening there? Like how are we supposed to interpret that? Like is this a measurement problem or is it saying something very fundamental about like what AI can and can't do under current conditions?

</details>

**Chris Painter**: 我认为**Joel**最好解释的是，我认为这里存在一个区别，即AI是否会，我认为**时间线图表**本身并不能告诉你，因为AI的出现，某个特定类型工作的生产力是否会提高。

<details>
<summary>Original English</summary>

**Chris Painter**: The thing that I think would be good for Joel to explain is that I think that that there is a distinction here between will AI, like the **time horizon chart** doesn't by itself, I think, tell you will productivity in one specific kind of job increase because of access to AI.

</details>

**Joel Becker**: 是的，也许关于那张图表，关于这些不同任务分布上的**时间线**，相对于我之前的猜测，我想说，那些**时间线**非常相似。我认为**倍增时间**，AI的进步速度，似乎比我原先猜测的更接近我们发布的原始趋势，尽管并非完美如此。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, maybe one thing to say on that chart showing the **time horizon** on on on these different **task distributions** relative to my guesses ahead of time, you know, I think those **time horizons** are remarkably similar. I think the **doubling times**, the pace of progress in AI seems more similar than I would have guessed to the original trends that we that we published, although, you know, imperfectly so.

</details>

**Chris Painter**: 关于将我们可能称之为原始AI能力（在某种意义上，你知道，基准上的能力）转化为现实世界生产力的困难，我认为存在一些差异，特别是在某些方面，基准结果高估了我们可能在实际中看到的情况。你知道，并不是大幅高估。我认为我们确实看到人们从这些现代**代理AI工具**中获得了真正的效用，但在某种程度上是高估了。

<details>
<summary>Original English</summary>

**Chris Painter**: On this difficulty translating what we might call raw AI capabilities in some sense, you know, capabilities on benchmarks or something to to real-world productivity, I think there are a number of differences and a number of ways in particular in which the benchmark results are overestimating what we might see in the wild. You know, not not hugely overestimating. I I think we do see that people are getting real utility out of these modern **agentic AI tools**, but overestimating to some extent.

</details>

**Joel Becker**: 一方面是评分方式隐含地不同。在实际问题中，我评分是基于更全面的东西，而不是我们**Meter**和许多其他人在基准世界中使用的这些算法评分程序，这些自动评分程序。在软件工程中存在**代码质量**的概念，但对于其他任务，会有...

<details>
<summary>Original English</summary>

**Joel Becker**: One is that the scoring implicitly is different. In real problems I'm scoring based on something a bit more holistic than these algorithmic scoring procedures, these automatic scoring procedures that we're using at **Meta** and many other people are using in the in the benchmark world. There's some notion of **code quality** if you're if you're working in software engineering, but but for other tasks there's there's um

</details>

**Joe Weisenthal**: 人们总是谈论优美、优雅的代码。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Beautiful code, elegant code, people always talk about.

</details>

**Joel Becker**: 是的，是的，是的。对于其他任务，如果**Anna Wintour**在编码，它会是这样的。[笑声]

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, yeah, yeah. For for other tasks there's going to be If **Anna Wintour** was coding, this is what it would look like. [laughter]

</details>

**Chris Painter**: 还有一件事是，实际中出现的任务在某种意义上更容易混乱。它们涉及与其他人合作。它们涉及在更大的代码库中工作，或者更开放式的问题，甚至可能存在一些对抗性情况。在软件工程背景下，这可能是有人试图更改你当前正在处理的代码库部分，你需要围绕它进行工作。我们确实倾向于看到AI在处理这些更混乱的问题时能力较弱。我不想夸大这一点。你知道，这不是一个巨大的影响，但你知道，这是阻碍生产力提高的一个因素。

<details>
<summary>Original English</summary>

**Chris Painter**: One more thing is that the tasks that come up in the wild are more likely to be messy in some sense. They involve working with other people. They they involve working in much larger code bases or or sort of more open-ended problems, maybe with something even adversarial going on. In the uh in the software engineering context that might be that someone's trying to make a change to the part of the code base that you're currently working on and and you need to and you need to work around that. And we do tend to see that the AIs are less capable of working on these more messy problems. I I don't want to overstate that. You know, it's not it's not an enormous effect, but you know, that's that's one thing that gets in the way of these productivity increases.

</details>

**Joel Becker**: 你知道，然后我确实认为可靠性问题确实存在，对吧？你知道，如果对于某种类型的任务，你只有80%的可靠性，那么每次你都需要回去验证这些AI的工作。而且不仅仅是验证这些AI的工作，而且在没有它们如何实现解决方案的背景下，如果你自己完成任务，你脑子里就已经有了这些背景。所以这个“验证”步骤，引号和引号，会花费更少的时间。你知道，我并不期望这些摩擦在某种意义上是如此根本性的，或者说我设想它们会上升到抽象层面。我认为不仅潜在的技术进步是真实的，而且我认为生产力的提高也会越来越明显，但是的，所有这些摩擦都存在。

<details>
<summary>Original English</summary>

**Joel Becker**: You know, and then I do think there's there's something to the reliability question, right? Where, you know, if it was true that for a certain type of task you only had, you know, 80% reliability, then every time you're going to need to go back and verify the work of of these AIs. And not only verify the work of these AIs, but without the context of how they implemented the solution relative to if you went about the task yourself, you'd already have that in in your head. And so this verification step, quotes and quotes, would take less time. You know, I I don't expect these frictions to be sort of so fundamental in some sense or or I imagine they they go up levels of abstraction. I think not only is the underlying technical progress real, but I think the the productivity improvements are also going to show up increasingly, but yeah, there are all these frictions.

</details>

### AI行业矛盾与Meter的公共角色

**Joe Weisenthal**: **Tracy**在问及风投和投资者兴趣时提到了这个问题。所以人们看到这些图表，无论**Meter**的观点是什么，他们都会觉得“这太不可思议了，我必须投资这个。”但这让我想到AI领域一个非常奇怪的更广泛现象，那就是AI实验室（那些构建这些东西的人）和**对齐安全**人员之间存在一种奇怪的“浸信会和私酒贩”关系。他们来回拉扯，实验室的负责人说：“是的，这可能会毁灭世界，夺走你们所有的工作。”而安全人员和对齐人员也说：“是的，这可能会毁灭世界。”这真是一个非常奇怪的行业，对吧？我唯一能想到的是香烟，他们会警告你吸烟有害健康，但那是因为他们输了官司才不得不这么做。我不认为他们特别乐意这样做。我想不出还有哪个行业，最热情的人同时也在警告和预言他们正在构建的东西有多糟糕。所以，我很好奇，你知道，首先，就像我在开场白中谈到的，像**Meter**这样的人是怎样的人？他们有足够的技能进行高级评估，而且资金来源是什么？但是，请告诉我们**Meter**的幕后是谁，以及他们为什么在那里。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Tracy alluded to this question when she asked about VCs and investor interest. So people see these charts and regardless of what **Meta**'s point is, like, this is incredible, I got to invest in this. But this brings me to this broader thing that I find very strange about AI, which is this kind of odd sort of **Baptist and bootlegger relationship** between the AI labs, people who are building this stuff, and the sort of **alignment safety people**. And they sort of go back and forth and like the you have the heads of the lab saying, yes, this might destroy the world and take all your jobs. And the safety people and the alignment people says, yes, this might destroy the world and like I'm very strange industry, right? Like the only thing that I can think of is cigarettes where like they warn you that smoking is bad, except they had to do that because they lost a lawsuit. I don't think they were particularly inclined to do that. I can't think of any other industry where the most enthusiastic people about it are also warning and dooming about how bad the thing they're building could be. So, I'm sort of curious like you know, first of all, like and I talked about this in the intro, like who is the type of person that's like working at **Meter**? That is like skilled enough to do like advanced evaluations and like where's the funding coming from? But like talk to us about like who's behind **Meter** and why they're there.

</details>

**Chris Painter**: 是的，完全可以。所以，我认为关于湾区AI安全关注的历史，有一点要说的是，这种担忧可以追溯到很久以前。我会说超过十年。很多人进入这个领域是因为他们看到了**深度学习**的趋势，他们想，“如果深度学习成功了，并且一直发展到**通用人工智能**，然后是**超级智能**，那会怎么样？”如果那成功了，那么它可能会影响一切。我认为，当人们担心这个问题时，他们心中有一个关于**超级智能**的未来，它比今天那些自认为是“**AGI**信徒”的人所想象的更有能力。他们想象的AI系统能够运行整个经济。我认为，很久以前，或者说多年前，看到这个愿景并对其利害关系感到担忧的人，很多人都有这种直觉，认为应该做的事情是进入这个行业工作，因为如果你在帮助构建它，你知道，塑造未来的最佳方式就是构建它。我认为，当然，你可以质疑这对于行业中的许多人来说有多真诚，或者是否存在不同动机的混合，就像他们内心有不同的“狼”，也许他们部分是受此驱动，但他们也觉得这有点像**奥本海默**（Oppenheimer）的感觉，身处创造危险事物的地位可能感觉很好。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, totally. So, I think one thing to say on the history of kind of people caring about **AI safety** in the Bay Area is that this concern goes back like quite a a ways. I'd say for over a decade. There are many people who got into the field because they saw this trend of **deep learning**, like what if **deep learning** works and it kind of goes all the way to **artificial general intelligence** and then **super intelligence**. And if that works, then it could affect everything. I think possibly when people worry about this, there's a future that they have in mind with **super intelligence** that's even more capable than what people who think of themselves as like **AGI pill** today think of. They're imagining AI systems that can run, you know, the entire economy. And I think people who kind of a while ago, or many years ago, saw that vision and were sort of alarmed about the stakes of it. Many people have this intuition that the thing to do is go and work in the industry because if you're like helping build it, you know, what's the best way to shape the future? It's to build it. And I think that there's obviously you could have questions about how sincere that is for for many of the people who are in the industry or if there's kind of a mix of different motivations and like, you know, different wolves inside of them where maybe they partially are motivated by that, but also they're like there's kind of this like **Oppenheimer** like it feels good to feel like you're in the position of making something that's dangerous maybe.

</details>

**Joe Weisenthal**: 有人曾这样形容**OpenAI**，这是几年前的事了，一个朋友说**OpenAI**有点像**曼哈顿计划**，只不过目标是最终不造出原子弹，如果这样说有意义的话。所以，回到你提到的**奥本海默**那一点，这感觉很奇怪。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Someone once described **OpenAI** to me, this was years ago, a friend said it was like **OpenAI** was sort of like the **Manhattan Project** except the goal was to not build the bomb at the very end if that makes any sense. So, to your **Oppenheimer** point, it's like very strange.

</details>

**Chris Painter**: 我认为需要强调的一点是，你知道，虽然现在可能存在多种动机，但湾区肯定有很多人真诚地相信这项技术正走向一个对人类来说非常困难的境地，人类将很难在有意义的层面上保持主导地位或控制权。看起来好像人们谈论“哦，大型AI实验室有公关问题”之类的。他们不断提起这一点，这就像也许他们只是相信它。所以，我认为这种担忧由来已久，而且我认为很多人都有这种直觉，认为他们可以通过构建它来影响它。但现在出现了一个问题，那就是这种逻辑总是建议你继续构建更先进的技术，或者更先进的AI系统。现在你面临一个问题，所有这些公司都说他们需要构建它，因为如果他们不构建，其他公司就会构建。然后，即使所有公司，他们都可能对彼此对安全原则的承诺抱有疑虑。众所周知，这些实验室的领导者之间关系并不好。他们不是朋友。他们很难在彼此之间解决安全问题。然后，即使所有美国AI实验室都同意这样做，他们又面临着中国这个外部的“假想敌”，对吧？中国公司会怎么做？所以，在这种意义上，即使这种担忧是真实的，我认为行业中的很多人都有这样一种本能，即除了为自己争取未来的筹码之外，他们在安全方面应该做什么，没有指导原则。我认为这在全球AI发展中是一个令人担忧的局面。你知道，显然我们正在尝试做一些不同的事情，比如告知公众，或者提供，你知道，你可以想象，如果情况更好，或者说目前这张图景中存在一个空白，那就是那些构建技术的人最相信它会带来不稳定和包罗万象的影响。也许如果公众和政府都达成共识，相信同样的事情，如果它真的朝着那个方向发展，那么社会就会有更多时间来想出应对措施，这些应对措施来自那些不直接试图通过技术建立筹码，或者通过某种公共行动或政府来控制技术的人。

<details>
<summary>Original English</summary>

**Chris Painter**: And I think one thing to emphasize is, you know, while while it could be that there's a mix of motivations now, there're definitely many people, I think in the Bay Area, who sincerely believe that the the technology is headed to some place that will be very difficult for a human where it will be very difficult for humanity to stay kind of in the driver's seat or like stay in control in kind of a meaningful sense. It does seem as though like people talk about oh, the big AI labs have like a PR problem or something like that. They keep bringing this up and it's like maybe they just believe it. So, I think that this concern is quite old and I think many people have this intuition that they're like I can influence the thing by building it. But now there's this problem that that logic kind of always recommends that you continue building more advanced technology or like more advanced AI systems. And now you have this problem where there's all of these companies and they all say that they need to build it because if they don't build it, another company will. And then even if all of the and they could all have doubts about each other's commitment to safety principles. Famously, the leaders of the labs really do not get along. They're not friends. It's not easy for them to kind of sort out the safety thing among themselves. And then even if all of the US AI labs kind of agreed to do that, they then have this kind of external bogeyman of **China**, right? What will the Chinese companies do? And so there's this sense in which just like even if the concern is real, I think a a lot of people then have who are in the industry have the the instinct that they kind of there's no guiding principle for what they should do on safety other than to like build leverage for themselves for later. And I think that is a concerning state of affairs AI development to be in globally. You know, obviously we're trying to do something different by like informing the public or kind of giving like, you know, you could imagine that the situation would be better if or like one gap that exists right now in that picture is that it's the people building the technology who most believe that it's going to be destabilizing and sort of all encompassing. Maybe if the public and governments all were on the same page and believed the same thing, if it were true that it was headed there, then there would be kind of like more time for society to figure out a response from people who are not trying to build leverage over the technology themselves directly or or, you know, control the technology via some kind of like public action or government.

</details>

### 中国AI模型与Meter的资源分配

**Tracy Alloway**: 我能很快问一下吗，既然你提到了中国，我不想忘记问这个问题，但是**Kwenn**并没有出现在你们的主要图表上。我想你们之前做过初步评估，但是评估美国的封闭模型和中国的开源模型有什么区别？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Can I just ask very quickly since you brought up **China** and I don't want to forget to ask this question, but **Kwenn** doesn't show up on your like main charts. I think you did a preliminary assessment of it a while ago, but like what's the difference between assessing one of the closed models in America versus one of the open source models over in **China**?

</details>

**Chris Painter**: 我认为有一点要说的是，这些能力是落后的。我们认为它们是落后的。我不确定。

<details>
<summary>Original English</summary>

**Chris Painter**: I think one thing to say is that the capabilities are are lagging behind. We think that they're they're lagging behind. I'm not sure that

</details>

**Tracy Alloway**: 所以它们仍然相关，只是没有出现在图表上，是吗？

<details>
<summary>Original English</summary>

**Tracy Alloway**: So, they're still relevant, they just like don't make it onto the chart or

</details>

**Chris Painter**: 嗯，所以我们确实会优先考虑，因为**Meter**的资源有限，特别是员工时间。我们优先考虑那些我们预计会处于前沿的模型。一般来说，中国模型比美国模型落后大约9到12个月。我认为按**时间线**计算的差距可能比按基准分数计算的差距更大，在某种程度上，我不确定我能说得多么科学，但有一种口语化的感觉，或者类似的感觉。中国模型在基准分数上表现更强，而不是在某种意义上真正被保留的问题上。在**Meter**任务上的问题。

<details>
<summary>Original English</summary>

**Chris Painter**: Um so, we we do try to prioritize just because **Meter** has has limited resources, staff time in particular. The the models that we that we anticipate being on the frontier and in general, the Chinese models have been something like, you know, 9 to 12 months, let's say, behind the US models. And I think the gap by **time horizon** is is probably even larger than the gap by benchmark scores where there's some I'm not sure how scientific I can make this, but there's some colloquial sense or something like that. The Chinese models are stronger according to benchmark scores than they would be on, you know, truly held out problems in in some sense. Problems problems like on the on the **Meter** task.

</details>

**Joe Weisenthal**: 基准？那是这个意思吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: the benchmark? Is that what that means

</details>

**Chris Painter**: 我不确定技术上，你知道，具体会如何，但精神上，精神上接近那个意思。我不确定这是否适用于所有中国模型。我确信这适用于中国以外的许多模型。但这，我认为这至少是一种可能性。

<details>
<summary>Original English</summary>

**Chris Painter**: or I I'm not sure technically, you know, exactly how that shakes out, but but something spiritually spiritually close to that. I'm not sure that's true for for all Chinese models. I'm sure it's true for for lots of models outside of **China**. But that I I think that's at least one possibility.

</details>

### Meter的外部互动与政府角色

**Tracy Alloway**: 我很好奇，当你与所有这些外部参与者交谈时，我将他们分为政策制定者、投资者和实验室本身，你目前与谁互动最多？

<details>
<summary>Original English</summary>

**Tracy Alloway**: I'm very curious, when you talk to external actors in all of this, and I'm going to group them into, I guess, policy makers, investors, and the labs themselves, like who are you interacting the most with at the moment?

</details>

**Chris Painter**: 我认为在实践中，我们最终与AI实验室互动很多，因为需要整理一些事情，获取模型访问权限，与他们合作，在第三方红队测试和第三方风险评估等相关事宜上建立新的先例。我们认为我们的受众是“高背景”的公众成员。所以，他们有点像，你知道，可能也像你们一样的人，对吧？那些需要根据AI进展的速度或AI能力的整体概况做出重要决策的人。因为我们总部在湾区，我认为我们与那些正在构建技术并更接近它的人互动不成比例地多。部分原因，我想回到**Joe**之前说的观点，我认为这有点是因为，要关心很多这些前沿问题，你就会倾向于选择那些自己正在构建技术的人。在某种意义上，行业中的公司今天花更多时间思考前沿能力评估，而不是政府。

<details>
<summary>Original English</summary>

**Chris Painter**: I think that in practice, we end up interacting a lot with AI labs because there's some amount of sorting out, getting access to models, working with them to set new precedents on things related to **third-party red teaming** and **third-party risk assessment**. We think of our audience as being sort of like **high-context members of the public**. So, they're kind of like people, you know, who are maybe like you too, right? People who are kind of like People listening to this podcast. People with kind of who have to make important decisions that will be informed by the the pace of AI progress or like the the kind of profile of AI capabilities overall. Because we're based in the Bay Area, I think we like disproportionately end up interacting with people who are building the technology and like closer to it. Partially, I think back to Joe's point before, I think this is kind of because it is the case that to kind of care about a lot of these frontier problems, you're kind of selecting for people who are building the technology themselves. There's some sense in which like the companies in the industry spends more time thinking today about frontier capabilities assessment than the government does.

</details>

**Joe Weisenthal**: 是的。我想，有一天你可以想象我们达到政府非常关注这一点并投入大量资源的程度。到那时，我预计**Meter**会花更多时间与政府交谈。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. I think like one day you could imagine us getting to the point where the government is like very focused on this and dedicating a lot of resources to it. And at that point, I would expect **Meter** to be spending more time talking to governments.

</details>

**Tracy Alloway**: 是的，这正是我要说的，因为我们的感觉是，在很多对话中，我们与人交谈时，他们会说一些关于“哦，为AI赋能的未来建立社会安全网很重要”之类的话。但似乎没有人真正深入思考这个问题。当你说，你知道，很容易想象或者政府会更关心这个问题时，对我来说并不那么容易想象。在我看来，他们主要关心的是，你知道，我们的数据中心以及它们的位置等等。如果我们有政策制定者真正关注前沿能力之类的，那会很好。这似乎还有很长的路要走。但这很有趣，你知道，你正在谈论那种资本主义动态，对吧？存在竞争，就像你有很多非常担心“哦，如果其他人先达到**ASI**或**AGI**怎么办？”或者“如果中国人怎么办？”等等的人。自由市场资本主义和需求，你知道，风投基金的大投资者，他们想要回报。他们想要IPO。事实上，我们今年可能会有一些大型AI IPO。你认为这与安全因素有多大的冲突？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yeah, that's kind of what I was getting at cuz our sense is in a lot of the conversations, like we talk to people and they'll say something about like, oh, it's important to have a **social safety net** for an AI-enabled future. But no one seems to be really thinking about it in a lot of detail. And when you say, you know, it's easy to imagine or maybe the government will care more about this, not so easy for me to imagine. I seems like they mostly care about, you know, our **data centers** and like where they're located and stuff like that. It would be nice if we had policy makers really looking at like **frontier capabilities** and stuff. Still seems kind of a way off. But it is interesting, you know, you're like talking about like the sort of like **capitalist dynamic**, right? There's competition and it's it's like you have a lot of people that are really worried about oh, what if the other guys get to **ASI** or **AGI** first or what if the Chinese, etc. How much does the fact of like **free market capitalism** and the demand, you know, the big investors at the VC funds, like they want to return. They want an **IPO**. We might get some big AI **IPOs** this year, in fact. How much do you find that to be perhaps in tension with the safety element?

</details>

### 资本驱动与AI安全的潜在冲突

**Chris Painter**: 是的，我，也许我们团队的人会有不同的看法。我个人不觉得，是的，这里有一些事情，比如投资者是关键决策者，你知道，他们也是人。说投资者也是人听起来很奇怪。我听起来像**Mitt Romney**之类的。但我认为，我认为这其中感觉可能存在紧张关系的因素是，如果你建立了一大堆财务义务，无论未来风险如何，都要保持全速前进。所以，比如我经常思考的一件事是，如果你为了建造数据中心而积累了巨额债务。然后假设你确实发现了证据，让你现在担心AI系统失控，你确实发现了AI系统失控的例子。你现在是否有财务承诺来建造这些数据中心并继续保持进步的速度？我认为这是我强烈感受到紧张关系的一个地方。就像你正在向市场建立这些预期，这可能会迫使你继续开发，而你本来宁愿在安全方面投入更多，或者，是的，它至少给你一种财务义务，至少要继续扩展计算能力。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, I maybe yeah, people on our team would have different views on this. I personally don't feel that there's yeah, there's some thing here of like investors are key decision makers and, you know, they're people too. That sounds strange to say investors are people too. I sound like **Mitt Romney** or something. But I I think that like I think that the element of this that feels like it could be in tension is if you build a bunch of financial obligations to keep kind of the pedal to the metal no matter what the risks are going into the future. So, like one thing I think a lot about is if you're like building up a huge amount of debt to build **data centers**. And then say that you do find evidence that you're now worried about about the, you know, loss of control from AI systems, you do find instances of AI systems going rogue. Do you now have like a financial commitment to build out those **data centers** and like continue kind of the pace of progress? I think that is one place where I feel the tension pretty acutely. Like you're building these expectations into the market that could kind of force you to continue development when you otherwise would rather invest more in safety or yeah, like it at least gives you a kind of financial obligation to continue scaling at least compute.

</details>

**Joel Becker**: 我认为人们自己了解进展情况对我来说似乎不是坏事。我认为在某些方面，让每个人都对可能与未来颠覆人类控制相关的能力达成共识是好事。但我认为在**Meter**分享的信息之外的世界里，我确实认为存在一种紧张关系。比如，私营公司正在构建这个事实，我认为未来可能会导致非常尖锐的紧张关系，是的，人们做出了这些承诺，如果他们试图放慢速度或最大限度地提高技术的社会弹性，他们就不会做出这些承诺。是的，我不确定这些事情会如何发展，但我认为在另一方面也存在一些力量，对吧？比如，你知道，一些“促进安全的技术”（引号和引号）或技术确实使模型更有用，你知道，如果它们在某种意义上更好地符合你的意愿。所以，你拥有资本主义激励，标准的资本主义激励来投资那种研究。也许这并没有涵盖，你知道，所有重要的安全研究。所以，它当然没有排除能力进步作为一个重要的轴线，你确实想在这个轴线上进行扩展，但你知道，我认为每个方向都存在一些力量。

<details>
<summary>Original English</summary>

**Joel Becker**: I think that like the people themselves being informed about the progress does not seem bad to me. I think it's like good in some ways for everyone to be on the same page about capabilities that could be related to subverting human control later on. But I think in the world beyond like the information that **Meter** shares, I do think there is a tension. Like the fact that private companies are building this, I think could cause really acute tensions in the future where, yeah, people make these commitments that they wouldn't if they were trying to like slow or you know maximize social resilience of the technology. Yeah, I'm not sure how these things shake out, but I but I think there are some forces on the other side, right? Like, you know, some **safety promoting technologies**, quote unquote, or techniques do make the models more useful, you know, if they're if they're better complying better complying with your will in some sense. And so, you have **capitalist incentives**, standard **capitalist incentives** to to invest in in in that kind of research. Maybe that doesn't cover, you know, the broad suite of of safety research that that seems important. So, it it certainly doesn't rule out capabilities progress as as being an important axis on on which on which you do want to scale, but you know, I think I think there are some some forces in each direction.

</details>

### 算力投资与AI能力加速

**Tracy Alloway**: 既然你刚才提到了计算，你能否多谈谈**时间线**改进与当前**计算成本**之间的关系，以及你实际看到了什么，这如何影响它？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Since you mentioned compute just then, can you talk a little bit more about I guess the relationship between like the **time horizon** improvements and the cost of **compute** at the moment and like what you've actually seen and how that impacts it?

</details>

**Chris Painter**: 是的，所以从我的角度来看，有一个非凡的事实，我不确定如何将这些事实联系起来，但这些公司在**计算**方面的研发支出呈指数级增长，当然，实际上它以与**时间线**进展大致相同的速度呈指数级增长。你知道，我认为这并非必然，你知道，这本身并不意味着如果计算进展放缓，那么能力进展也会放缓，但你知道，它显然是AI进展的一个重要投入。我预计未来会继续如此。有时人们会问我们，我们认为能力进展（这种指数级能力进展）在未来某个时候放缓的可能性有多大。你知道，我很难认为它在未来至少几年内会放缓的一个原因是，很多这些**计算研发投资**基本上已经“板上钉钉”了，对吧？就像数据中心已经建成，你知道，甚至2027年、2028年之后的**数据中心**计划，大概，你知道，正在实现，正在发生。所以，这些投入投资在某种意义上已经“板上钉钉”了。所以，如果计算是重要的投入，那么看到能力放缓会令人惊讶。在那之后，也许你需要考虑，你知道，关于能力可能如何放缓的其他论点，但这大致是我思考的方式。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, so so one extraordinary fact from from my perspective, I'm not sure how to how to fit these facts together, but something like the **R&D spends on compute** of these companies has risen exponentially, of course, and in fact it's risen exponentially at essentially the same rate as **time horizon** progress. You know, I think there's nothing necessary about that, you know, it doesn't mean by itself that if compute progress slows then capabilities progress will also slow, but you know, it's clearly an important input into into AI progress. I expect that to to continue to be true in future. Sometimes people ask us if we think it's plausible or how plausible we think it is that that capabilities progress, this exponential capabilities progress, might slow down at some point at some point in the future. And you know, one reason it seems it's hard for me to consider it plausible that it will slow down in the next at least small number of years is that a lot of those **compute R&D investments** basically already baked in, right? Like the the **data centers** have already been built, you know, plans for **data centers** even beyond 2027, 2028 presumably, you know, coming coming to fruition, coming coming about. And so, some of these input investments are already baked in in some sense. So, it would be surprising to see capabilities slow to the extent that compute has been an important input. After that maybe maybe you need to think about, you know, other arguments for how capabilities might slow, but that's roughly how I think about it.

</details>

### 基准测试的激励机制与未来改进

**Joe Weisenthal**: 有一篇非常好的或有趣的批判性**Substack**文章，叫做《反对**Meter**图表》，作者是**Nathan Whitkin**，他提出了一个我若不读就不会想到的有趣观点，那就是你们付钱给软件工程师来完成这些任务，对吧？这似乎是，你知道，也许这将是人类的最后一项工作，就是坐着做基准测试。如果我是一个优秀的软件工程师，你对我说，“**Joe**，进来完成这个任务。”你如何阻止我？哦，天哪，这花了我很长时间。与此同时，我每小时继续赚100美元，看着我的电脑，哦，这太难了。我明天还得回来继续做。你们如何避免这种利益冲突，即被雇来解决问题的人可能会被鼓励尽可能长时间地解决问题。而且有时只有三个人在做，我[叹息和喘息]不知道。这，这对我来说似乎是一种利益冲突。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: There's a very good or interesting critical **substack** post called **against the meter graph** by someone named **Nathan Whitkin** who brings up one an interesting point that I wouldn't have thought of had I not read it, which is you're paying the software engineers to come in and perform these tasks, right? It seems like you know, maybe this will be the last job of humans is just sitting doing benchmarks. If I were like a good software engineer and you say, Joe, come in and do this task, how do you prevent me? Oh man, this is taking me a long time. Meanwhile, I keep getting $100 an hour for like looking at my computer and ooh, this is tough. I'm going to have to come back tomorrow and keep working on this. How do you avoid the sort of **conflict of interest** where the person who's paid to work on this problem may be encouraged to take as long as possible to solve it. And with only three people working on it at times, I [sighs and gasps] don't know. This like this does not It seems like a **conflict of interest** to me.

</details>

**Joel Becker**: 是的，所以简短的回答是，你知道，一般来说，我们激励这些人尽快完成任务。特别是要比他们的同伴更快地完成任务，那些同伴也在尝试完成相同的任务，他们完成任务所需的时间。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, so the short answer is, you know, in general we are incentivizing these people to to complete the task as soon as possible. Um in particular to complete the task faster than their peers who are attempting the same task the time that it will take for them to complete the task.

</details>

**Joe Weisenthal**: 如果他们做得比别人快，会有奖金吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: a bonus if they do it faster than

</details>

**Joel Becker**: 是的，是的，大致上，如果他们比其他人更快完成任务，就会有奖金。你知道，另一件事是，我认为我们的**基准测试方法**，或者说我们与人类比较的方式，在某些方面还有很多不足之处。你知道，理想情况下，我们应该投入100倍的资源，每个任务有100个人类基准，这些基准应该来自，你知道，也许是世界上最优秀的软件工程师或机器学习工程师。也许那才是我们正在进行的比较。而且，我们确实会在更多任务上执行所有这些程序，而不仅仅是更多任务，而是在比软件工程或机器学习工程更广泛的任务分布上执行。我的意思是，我确实认为**时间线**仍然代表着AI能力衡量科学的进步，但你知道，在某些方面，我同情对**时间线**的许多批评。我确实认为一些细节，至少对于我们目前所做的工作，你知道，不会像你天真地认为的那样重要。所以，选择我们最终观察到的最短基准时间或最长时间，你知道，实际上对最终测量结果不会有太大影响。你知道，当然，我们确实认为这些人是才华横溢的软件工程师或网络安全人员等等，取决于任务，但你知道，也许我们可以找到更有才华的人。他们会在一半的时间内完成，所以，你知道，天真地看，我们估计的这些模型的时间线会比我们实际观察到的短一半，但当然这不会改变**倍增时间**。这意味着你会在另外四个月后达到相同的水平。在某种意义上，我希望**时间线**指向的宏大图景，与其说是**Opus 4.6**特别需要12小时，不如说是我们正在看到这种显著的进步速度，在最近的过去和我认为在不久的将来都没有放缓的迹象。你知道，事实上，它甚至显示出一些加速的迹象。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, yeah, approximately there's a there's a **bonus** if they complete it faster faster than anyone else. You know, another thing to say is I think it just is true that our **baselining methodology** or or the ways in which we compare to humans in some ways leaves a lot to be desired. That's you know, ideally we would have invested, you know, 100 times as many resources in having 100 baselines human baselines per task and those would have come from, you know, perhaps the very best software engineers or machine learning engineers in the world. Maybe that would be the maybe that would be the comparison that we're making. And indeed, we'd be doing all of all of this procedure over many more tasks, not just many more tasks, many more tasks over wider task distributions than just software engineering or machine learning engineering. I mean, I I do think **time horizon** still represents progress over over what's come before in in the science of measuring AI capabilities, but you know, in some ways I'm sympathetic to a lot to a lot of criticisms of **time horizon**. I do think that some of the details, at least for the work we've done so far, you know, aren't going to matter as much as you might naively think. So, choosing the, you know, shortest baseline time that we end up observing or the longest time, you know, it's actually not going to make that much difference to the final measurements. You know, of course, we do think these people are talented software engineers or cybersecurity people or or so on depending on the task, but you know, perhaps we could have found even more talented people. They would have completed it in half the time and so, you know, naively it would seem like the **time horizon** that we estimate of these models would be half as long as we actually end up observing, but of course that that wouldn't change the **doubling time**. It would mean you'd get to the same level after another another four months. In some sense, the big picture that I want **time horizon** to point to is less this like **opus 4.6** is 12 hours in particular and more that we're seeing this remarkable pace of progress that shows no signs of of slowing in in the recent past and and I think in in the near future as well. You know, in fact, it shows some signs of speeding up.

</details>

### AI能力倍增速度的加速

**Joe Weisenthal**: 嗯，我本来想问这个，因为我认为最近你总是听到一个统计数据，比如每7个月翻一番之类的。你认为它在不久的将来会以多快的速度发展？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Well, I was going to ask about this because I think recently the statistic that you would always hear was like a **doubling every 7 months**, something like that. How fast do you see it going in the near future?

</details>

**Joel Becker**: 是的，所以我曾经是每7个月翻一番的观点。我们团队内部对此存在争议，因为大约一年前我们最初发布这项工作时，你会看到，如果你绘制一条直线，一个单一的指数曲线，你会得到大约6或7个月的结果，但如果你只限制在**GPT-4O**之后，即2024年模型之后的时间，你会看到更接近4或5个月的趋势。有些人相信这一点，你知道，像我这样的一些人直觉上认为，我们只有这么少的数据点。我们真的应该根据更多的数据点进行估计，而更多的数据点表明是每六或七个月。有几件事改变了我的想法，并让我意识到我的同事们是对的。其中之一是，对于此后发布的模型，什么趋势能更好地预测这些模型的性能？答案很明显是4个月的**倍增时间**，而不是7个月的**倍增时间**。你知道，它有可能再次加速。我们已经看到它加速过一次。我认为原则上有一些原因可以让你预期它会再次加速。我认为对此有一些注意事项，你知道，这些可能是我同事们会同意的一些看法，所以，你知道，也许你应该放弃这些看法，或者，你知道，你应该认为他们会像说服我接受4个月与7个月**倍增时间**一样说服我。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, so I was a **doubling over every 7 months** person. There was there was controversy in our team about about what to believe here because when we originally published this work approximately a year ago, you'd see, you know, if you plotted a a single straight line, a single exponential, you'd get something like, you know, six or seven months, let's say, but if you restricted to just the time since I think **GPT-4O**, since the 2024 models onwards, you'd see something closer to this sort sort of like four or five months trends. And some people believed in that and you know, some people like me have the intuition that well, we have so few data points. We should we should really be estimating over this larger number of data points and the larger number of data points says every six or seven months. There are a couple of things that have changed my mind and and made me realize my colleagues were right since since then. One is that for the models that have that have come out since, you know, what's what trends has has better predicted how performant those models would be and it's very clear that the answer to that is the the **four month doubling time** and not this **seven month doubling time**. You know, there's some some possibility that could speed up again. We we've seen it we've seen it speed up once. I think there are some reasons in principle why you why you might expect it to speed up again. I think there are some caveats about this, you know, these are these are maybe some some takes that my my colleagues would agree with and so, you know, maybe maybe you should discard that or you you know, you should think that they're going to convince me in the way that they did with the with the four month versus seven month doubling times.

</details>

**Chris Painter**: 我有些怀疑**Meter**衡量性能的任务，你知道，在某种意义上，是所有可能任务中越来越窄的一部分，特别是越来越窄的一部分，可能与你期望这些主要AI公司首先训练的任务类型相似。所以，在某种意义上，我们越来越多地（比以前更甚）衡量它们正在努力改进的精确任务类型的进展。你知道，你可能会认为，例如，那些适合作为良好**强化学习环境**的任务，那些可以快速、廉价和自动评分的任务。我认为这种进步是真实的。我认为这种进步在某种程度上可以推广到其他类型的任务。我认为我们正在看到，你知道，在这些更混乱的任务中取得了显著的进展，例如。

<details>
<summary>Original English</summary>

**Chris Painter**: I have some suspicion that the tasks that **Meta** is measuring performance on are, you know, in some sense, more and more narrow slice of possible tasks and in particular a more and more narrow slice that is perhaps similar to the kinds of tasks that you'd expect these major AI companies to be training on in the first instance. And so, in some sense, we're increasingly, more so than was the case before, measuring progress on the exact types of tasks that they're trying to get better at. You know, you you might think for instance the kinds of tasks that would make for good **reinforcement learning environments**, the kinds of tasks that you can score quickly and cheaply and and and automatically. I think that progress is real. I think that progress generalizes to some extent to other types of tasks. I think I think we're seeing, you know, remarkable progress in these more messy tasks for example.

</details>

### Meter团队、资金与人才瓶颈

**Tracy Alloway**: 我最后一个问题是，你们团队有多大，资金来源是什么，以及**Meter**有多少人基本上已经从AI领域赚了很多钱，他们觉得，“你知道吗，我已经够了。我不需要追求IPO之类的。我已经搞定了，现在我想做一些事情，让全人类都知道。”我看到过其他独立的AI研究人员，他们谈论过这个。他们说，“我想能够谈论我所看到的。”**Miles Brundage**，一个拥有小型智库的人，也谈论过这个。有多少人已经很富有，他们觉得，“好的，现在我想为一些面向公众的事情工作。”

<details>
<summary>Original English</summary>

**Tracy Alloway**: I've one last question, which is like how big's your team, funding, and like also how many people at **Meta** are basically like really rich from AI and they're like, you know what, I'm good. I don't need to pursue like stick around for the IPO or whatever. I'm set and now I want to work on something and let humanity know. I've seen like there are other independent AI researchers and they talk about this. It's like I want to be able to talk about what I saw and said **Miles Brundage**, someone who has like a little think tank, he's talked about this. What's like how many people are like rich already and they're like, okay, now I want to work for something that's public facing.

</details>

**Joel Becker**: 是的，所以**Meter**现在大约有30人，尽管我们正在增长，并希望快速增长。我应该说，我们正在招聘，请访问**meta.org/careers**。是的，你之前提到了非营利组织是否困难。你知道，我们不能用股权支付员工。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, so **Meta** right now is about 30 people, although we're growing and hoping to grow fast. We are hiring, I should say, **meta.org/careers**. And yeah, you were touching before and kind of the thing about is it difficult to be a nonprofit. You know, we can't pay people in equity.

</details>

**Joe Weisenthal**: 对，是的，**Meter**没有IPO之类的，但我们确实努力提供有竞争力的现金薪酬，对吧？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Right, yeah, there's no no IPO or anything for **Meta**, but we do try to pay competitively on cash compensation, right?

</details>

**Joel Becker**: 那是我们觉得可以与实验室在某种程度上竞争的领域，而且确实如此，我认为我们团队的很多人只是被尝试做一些不同的事情所驱动，而不是，你知道，所有公司在某种程度上都在做这种构建有点冗余产品，争夺世界相同角色的业务，而**Meter**目前处于一个非常独特的位置，我认为我们有能力接触并沟通这些想法，向许多受众解释AI研究的现状，这对于公司内部的个体研究人员来说可能很难。比如，我们可以直接与许多政府交谈。我们可以来这里与你们所有人交谈，这有点不同。我认为如果你看看所有在AI研究或AI安全前沿工作的人，如果你将我们与AI实验室员工进行比较，我认为我们的工作可以让我们每天都致力于我们认为对公众关于AI的决策最有信息量的研究。

<details>
<summary>Original English</summary>

**Joel Becker**: That's an area where we feel we can like somewhat compete with labs and it's true that I think a a lot of our team is just motivated by trying to kind of do something different, like not, you know, all the companies to some extent are in this business of kind of like building somewhat redundant products, kind of competing for the same role in the world and **Meta** is in a really unique position at the moment where I think that we have like access and the ability to communicate these ideas and explain the state of AI research to a number like a a lot of audiences that might be hard for like individual researchers inside of a company. Like we get to talk to a lot of governments directly. We get to come here and talk with you all and that's kind of different. I think if you look at all the actors that are working on the frontier of AI research or AI safety, you kind of if you compare us to AI lab staff, I think that our work gets to be we get to kind of every day work on whatever research we think will be most informative to the like public decision making about AI.

</details>

**Joe Weisenthal**: 不是前AI，而是前任AI实验室员工，他们可能在某个时候有过一段经历，现在他们在**Meter**工作？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: not ex-AI, but ex as in former AI lab staff who were maybe there was a tender at some point and now they work at **Meta**?

</details>

**Joel Becker**: 是的，我们确实有一些这样的人。是的。所以，我们确实有一些以前在AI实验室工作过的人。我确实认为随着时间的推移，我有一个希望，那就是会有越来越多的研究人员，他们已经通过在行业工作赚到了他们需要的钱，现在他们很高兴能够通过在一个组织内部工作来“提升所有船只”，这个组织的北极星是“对世界其他地方最有信息量”，而不是这些相对较小的公司。

<details>
<summary>Original English</summary>

**Joel Becker**: Yeah, we do have some of those. Yeah. So, we do have some people who previously worked at AI labs. I do think that as time goes on, I think one hope that I have is that more, you know, there there will be more and more researchers who have kind of like made the money that they need from working in the industry and now are excited in kind of like lifting all boats by working on kind of like inside of an organization where the north star can be what is most informative to the rest of the world outside of these like relatively small set of companies.

</details>

**Chris Painter**: **Chris**非常客气。我认为那很棒。

<details>
<summary>Original English</summary>

**Chris Painter**: Chris is very polite. I think that's I think that's wonderful.

</details>

**Joel Becker**: 我有点想更直接一点。在这次对话中，我认为我们已经谈到了**Meter**在世界上一些最重要问题上的工作。我认为这些问题将定义未来，不仅仅是未来几年，而是未来几十年，甚至可能是未来几个世纪。我们还谈到了**Meter**的工作在某些方面可能不如你所期望的那样。在评估这些AI的科学方面还有很长的路要走。我们为什么没有取得更多进展？你知道，也许有几个原因。我认为很明显，核心原因是我们在技术人才方面受到了瓶颈，缺乏非常有能力的人来研究这些问题。我最近参加了一个**Meter**工作务虚会，我们集思广益了20、30个看似对世界很重要的问题。我们认为如果我们不解决这些问题，就没有其他人会解决。我们能够对其中多少个问题进行研究？我认为是1、2个，你知道，也许如果我们这个季度做得非常出色，可能会是3个。正如**Chris**所暗示的，我认为如果你有兴趣，你知道，少在这些大型AI公司从事冗余产品的工作，而更多地推进我们对世界上一些最重要问题的理解，这些问题将在未来几年震撼世界，那么**Meter**是一个很好的去处。

<details>
<summary>Original English</summary>

**Joel Becker**: I'm tempted to be a little bit a little bit more aggressive. In this conversation, I think we have spoken through **Meter**'s work on some of the most important problems in the world. Problems that are going to define the future, I think, for not just the next years, but you know, coming coming decades, maybe maybe even coming centuries. And we've also spoken about some of the ways in which **Meter** work is is not might not what you might want it to be. That there's a long way to go in the science of evaluating these AIs. Why have we not made more progress? You know, maybe maybe a couple of reasons. I think clearly the central reason is that we are **bottlenecked on on technical talent**, on incredibly capable people to to to come work on these questions. I was on a **Meter** work retreat recently where we were brainstorming, you know, 20, 30 of these what seemed like world important problems. Problems that we think no one else is going to get to if we do not get to them. And we are able to conduct research on on how many of those problems? I think it's one, two, you know, maybe if we do an extraordinary job this quarter, it might be three. As Chris alludes to, I think if you're if you're interested in, you know, less working on redundant products at these major AI companies and more advancing our understanding on some of the most important questions in the world that are that are going to shake the world for years to come, **Meter**'s **Meter**'s a great place to go.

</details>

**Chris Painter**: 嗯，是的，关于那一点，还有一件事要说的是，**Meter**内部的氛围是一种**分诊状态**，对吧？我认为人们经常对自己说，外部的人可能会猜测，“哦，你知道，**Meter**是一个，它在任何AI实验室之外，所以它可能最挣扎的是像访问AI模型之类的事情，你知道，你不能做你想做的研究，因为你没有，你没有自己构建东西。”在实践中，或者说人们总是说的故事是，你必须构建未来才能塑造它。在实践中，我认为我们在**Meter**的经验是，当我们想尝试新型研究，需要新型结构化访问时，目前的情况是AI实验室非常乐意配合。嗯，而更多发生的事情是，我们不得不拒绝做这类事情的机会，因为我们没有足够的人员来完成这些事情。

<details>
<summary>Original English</summary>

**Chris Painter**: Well, yeah, one more thing to say about that is like the vibe inside of **Meter** is a state of **triage**, right? And I think people often tell themselves externally people might guess, oh, you know, **Meter**'s a it's outside of any of the AI labs so the thing it might most struggle with is things like access to AI models, you know, you can't do the research you want cuz you don't have you're not building the thing yourself. In practice or that's the story that people always tell is you have to build, you know, the future to shape it. In practice, I think our experience at **Meter** is that like when we want to try new types of research that would require new kinds of structured access, at this point has been that AI labs are like pretty game to play ball on that. Um and the thing that what is more happening is that we're having to turn down opportunities to do stuff like that because we don't have the staff that we need to make those things happen.

</details>

**Joe Weisenthal**: 有趣。**John**，**Chris**，非常感谢你们来到《奇闻异事》。这是一次绝对引人入胜的对话，我感谢你们抽出时间。很高兴你们来到演播室。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Interesting. John, Chris, thank you so much for coming on Odd Lots. Absolutely fascinating conversation and I appreciate you taking your time. Great to have you in studio.

</details>

**Chris Painter**: 是的，非常感谢。

<details>
<summary>Original English</summary>

**Chris Painter**: Yeah, thank you so much.

</details>

**Joel Becker**: 非常感谢邀请我们。

<details>
<summary>Original English</summary>

**Joel Becker**: Thank you so much for having us.

</details>

### 播客总结：AI发展与安全挑战

**Tracy Alloway**: 这真是一次非常有趣的对话。我们从结尾开始，有点像，“好的，这里有一些非常重要的问题。让我们把其他一切都放在一边。”

<details>
<summary>Original English</summary>

**Tracy Alloway**: That was a really interesting conversation. And it to that we were starting from the end sort of the idea of like, okay, here are some really important questions. Like let's just set everything aside.

</details>

**Joe Weisenthal**: 有30个人在研究这些问题。而且，你知道，有多少人想做呢？就像，“好的，我们尽量匹配现金薪酬等等。”这似乎是一个棘手的问题。如果你接受这些是我们需要正确解决的一些大问题，而且我们希望能顺利着陆这个“飞机”的前提。这确实是一个问题。是的。嗯，我认为另一个非常有趣的事情是中国模型并没有真正出现在图表上，尽管我们知道在市场本身，当**Deep Seek**的新版本发布时，那是一个巨大的事件，每个人都开始恐慌，然后却没有看到它甚至出现在**时间线图表**上，这有点有趣。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And there's 30 people working on them. And there's, you know, and like how many people want to do it? And it's like, okay, we try to match cash, comp, etc. Like that seems like kind of a tricky issue. If like if you accept the premise that these are some big questions we have to get right and we got to land this plane hopefully. Like that's a bit of an issue. Yeah. Um the other thing I thought was really interesting was the Chinese models not really making it on the charts even though like we know in the market itself like when **Deep Seek** when that new version came out, that was like this huge thing where everyone started to panic and then to not see it even like land on the **time horizon chart** is kind of interesting.

</details>

**Tracy Alloway**: 我想，我的意思是，我想我接受他们从他们的角度出发的推理，即从**Meter**的角度来看，唯一有趣的问题是最前沿的，这可能与商业上最有趣的图表略有不同，对吧？所以，就像，“好的，我们知道**Deep Seek**、**Quan**和**Kimmy**等等都非常令人印象深刻。”它们是否推动了最前沿？也许没有。但总的来说，我发现这个领域非常奇怪，因为就像，你看到这些人显然对这里的潜力感到非常担忧。而大多数人我认为看到这些图表时会说，“哇，这太棒了，我想投资这个，”或者“这太令人兴奋了。”

<details>
<summary>Original English</summary>

**Tracy Alloway**: I guess it's I mean I guess I buy the reasoning from their perspective that the only interesting question from **Meter**'s perspective is like the most cutting edge which may be slightly adjacent to the most interesting chart for like business, right? So it's like, okay, we know that **Deep Seek** and **Quan** and **Kimmy** and all those are like very impressive. Do they push like the very frontier? Perhaps not. But just in general, I find this space so weird because it's like here you have these people who are like clearly quite alarmed at the potential here. And most people I think look at these charts and they say like, wow, this is like I want to invest in this or this is like really exciting.

</details>

**Joe Weisenthal**: 知道。这就是为什么我的第一个问题是，你们是为了AI安全目的而在这里，但每个人似乎都对“曲线向上”的图表感到兴奋，对吧？存在脱节。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: know. Like that's why my first question was like you're here for **AI safety** purposes, but everyone seems to get excited about the line go up chart, right? Like there's a disconnect.

</details>

**Tracy Alloway**: 就像我说，当一个行业基本上自己说它很担忧时，是的。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Like I say when an industry basically says it's worried by itself, Yeah.

</details>

**Joe Weisenthal**: 注意。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: pay attention.

</details>

**Tracy Alloway**: 这真的很奇怪。这又回到了，你知道，一个非常奇怪的现象，这些公司的CEO在很多情况下是最危言耸听的。然后有一种愤世嫉俗的说法，我并不完全否定这种愤世嫉俗的解释，那就是“哦，他们这么说是因为他们想吸引投资者等等，他们需要所有这些钱。”但你看，**OpenAI**和**Anthropic**，但**OpenAI**更多一点，它们都是以非常奇特的**公司结构**成立的，比如一家由非营利组织拥有的私营公司等等。他们之所以这样做，大概是因为他们非常认真地对待这项技术和科学非常奇怪的事实，而不仅仅是……

<details>
<summary>Original English</summary>

**Tracy Alloway**: It's really strange. And this gets back to, you know, a very it's very strange where you have the CEOs of these companies who are in many cases the most alarmist. And there's this sort of cynical thing and I don't totally discount the cynical interpretation is like oh, they're saying this cuz they want to get investors and so forth and they need all this money. But look, it was also true that **OpenAI** and **Anthropic**, but **OpenAI** a little more, were like founded with these very exotic **corporate structures** like a private company owned by nonprofit, etc. Which they presumably did because they took pretty seriously the fact that this technology and science was like very strange and not just like

</details>

**Joe Weisenthal**: 它不仅仅是企业软件。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: it's not just enterprise software.

</details>

**Tracy Alloway**: 对。就像它们在某种程度上是自我限制的。另一个有趣的事情是，这个想法是，“好的，首先，7个月和4个月的**倍增时间**有什么区别？”没什么大区别。你知道，就像这些人说，“哦，我想AI会在两年内摧毁所有白领工作。”另一个人说，“不，不，我认为会是三年。”好像这有什么区别似的。但有一件事要考虑，**Joel**也提到了这一点。你知道，**OpenAI**关闭了它的视频项目等等。所以故事的一部分可能只是现在对软件工程方面的强烈关注，这是这些实验室正在努力的方向，而所有其他支线任务都不那么重要。所以也许我们会在一些技术基准上看到更快的进展，因为显然从实验室的角度来看，那里才是重点，而不是像制作图像或视频这样的消费者产品。是的。好了，我们就在这里结束吧？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Right. Like they were self-limiting in a way. One other interesting thing too that uh this idea is like, okay, like first of all, what's the difference between 7 months and 4 months **time doubling**? Not much. You know, it's like these people are like, oh, I think it's exponential, isn't it? I guess it's exponential, but it's still funny to me. It's like, oh, I think like AI is going to destroy all white collar work in 2 years. And someone else is like, no, no, I think it's going to be 3 years. As if that makes like any different whatsoever. But one thing to consider Joel sort of alluded to this. You know, you had like **OpenAI** shutting down its like video efforts, etc. So perhaps part of the story is just this intense focus now on the **software engineering side** as what these labs are working on and sort of like all these other side quests are not as important. So maybe we will see even more rapid progress on some of these technical benchmarks because clearly from the labs' perspective, that's where the action is more than some of these consumer things like making making images or videos. Yep. All right, shall we leave it there?

</details>

**Joe Weisenthal**: 就在这里结束吧。好的，这是《奇闻异事》播客的又一集。我是**Tracy Alloway**。你可以在**TracyAlloway**关注我。我是**Joe Wiesenthal**。你可以在**The Stalwart**关注我。关注我们的嘉宾**Chris Painter**。他的账号是**ChrisPainterYep**。还有**Joe Becker**，他的账号是**Joe_BKR**。关注我们的制作人**Carmen Rodriguez**，账号是**CarmenArmand**；**Dash Bennett**，账号是**DashBot**；**Kell Brooks**，账号是**KellBrooks**；以及**Kevin Lozano**，账号是**KevinLloydLozano**。获取更多《奇闻异事》内容，请访问**bloomberg.com/odd lots**获取每日新闻通讯和所有剧集。你可以在我们的**Discord**上24/7讨论所有这些话题，**discord.gg/odd lots**。如果你喜欢《奇闻异事》，如果你喜欢这些AI剧集，那么请在你最喜欢的播客平台上给我们留下积极的评论。记住，如果你是**Bloomberg**订阅者，你可以完全免费收听我们所有的剧集。你只需要在**Apple Podcasts**上找到**Bloomberg**频道并按照那里的说明操作即可。感谢收听。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Let's leave it there. Okay, this has been another episode of the Odd Lots podcast. I'm **Tracy Alloway**. You can follow me at **TracyAlloway**. And I'm **Joe Wiesenthal**. You can follow me at **The Stalwart**. Follow our guest **Chris Painter**. He's at **ChrisPainterYep**. And **Joe Becker**, he's at **Joe_BKR**. Follow our producers **Carmen Rodriguez** at **CarmenArmand**, **Dash Bennett** at **DashBot**, **Kell Brooks** at **KellBrooks**, and **Kevin Lozano** at **KevinLloydLozano**. And for more Odd Lots content, go to **bloomberg.com/odd lots** for the daily newsletter and all of our episodes. And you can chat about all these topics 24/7 in our Discord, **discord.gg/odd lots**. And if you enjoy Odd Lots, if you like these AI episodes, then please leave us a positive review on your favorite podcast platform. And remember, if you are a **Bloomberg** subscriber, you can listen to all of our episodes absolutely ad free. All you need to do is find the **Bloomberg** channel on **Apple Podcasts** and follow the instructions there. Thanks for listening.

</details>