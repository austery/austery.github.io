---
author: Bloomberg Podcasts
date: '2026-03-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=paN2aYVoUkw
speaker: Bloomberg Podcasts
tags:
  - ai-productivity
  - software-development-lifecycle
  - model-governance
  - token-economics
  - developer-transformation
title: 高盛CIO马可·阿根蒂谈AI如何重塑软件开发与金融业
summary: 高盛首席信息官马可·阿根蒂在播客中深入探讨了人工智能对软件开发生命周期、企业生产力、成本结构及人才需求带来的变革。他强调AI已从实验阶段迈入实用阶段，通过内部平台如GSA助理和Darwin，显著提升了工作效率、缩短了项目交付周期。马可还讨论了AI模型集中化管理、代币成本预期、合规监管以及AI对银行信息不对称优势的潜在影响，指出未来开发人员需更具规划、解释和管理智能体的能力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Marco Argenti
companies_orgs:
  - Goldman Sachs
  - Anthropic
  - OpenAI
products_models:
  - ChatGPT
  - Claude
  - GPT
  - GSA assistant
  - Darwin
media_books: []
status: evergreen
---
### AI对软件开发生命周期的影响

**马可·阿根蒂**: 如果你审视**软件开发人员**的生命周期，很多方面都在变化。如今，开发人员通过**编写规范**来开发软件。所以，如果你过于沉溺于底层机制，而没有适应**人工智能**或**智能体**在软件开发生命周期的部署、回滚、监控、可观测性等方面的工作，我认为这条道路将受到极大冲击。或者，如果你在事物上添加某种用户体验（UX），那是另一类。所以你有一个非常简单的流程，比如你在做调查或费用报告之类的。现在人们会开始期望他们的**个人助理**或智能体为他们完成所有这些机械性工作。因此，我认为这条道路可能充满了更大的不确定性。所以我总是先问自己流程问题——流程转型部分，先问问题，然后才考虑什么工具能支持它。但就在这一点上，你们是否已经用内部通过AI开发的东西取代了任何第三方软件提供商？我们已经终止了一些合同。是的，绝对如此。

<details>
<summary>Original English</summary>

**Marco Argenti**: If you look at the software developer lifecycle, a lot of that is changing. Developers are or are developing software by developing specs today. And so if you are too much in the weeds down there in that mechanics, and you don't adapt for AI or agents doing that work in software development lifecycle deployments, rollbacks, monitoring, observability and all that. I think that path will be very much disrupted. Or if you're adding a sort of a UX on things, that's another class. So you have a very simple process. I don't know, you're doing surveys or expense reports or whatever. And now people are going to start expecting, you know, their personal assistants or agents to kind of do all that mechanic for them. And so I think that path is probably something that has a bigger question mark on top. And so I always ask myself the process question first. The process transformation section, the question first, and then consequently what's the tool that is going to support that? Just to press on this point though. Have you replaced any third party software providers with something that's been developed internally through AI? We have we have terminated contracts already. Yes, absolutely.
</details>

**特蕾西·阿洛韦**: 大家好，欢迎收听《**奇思妙想**》播客的又一集。我是**特蕾西·阿洛韦**。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Hello, and welcome to another episode of the All Thoughts podcast. I'm Tracy Alloway.
</details>

**乔·魏森塔尔**: 我是**乔·魏森塔尔**。特蕾西，关于人工智能，我觉得它加速了我们所有的时间线，对吧？就像，回想起**ChatGPT**问世的日子，对我来说简直不可思议。那是什么时候出来的？2020年？2022年？真是难以置信。然后能力的爆炸式增长更是令人难以置信。我一直在思考这件事。当我思考时发现，在它问世大约一年后，我们和高管们交流，问他们“你们如何在工作流程中使用人工智能？”每个人都在尝试，这很棒。每个人都在改变，因为我当时说得很模糊。而现在是2026年，主流的说法是人工智能太强大了，它将摧毁所有这些传统的软件公司。所以我想说的是，我们一定已经过了实验阶段。我认为真正有用的用例，在使用它时最好能有一些例子，比如“这是我们正在使用它的一个工作流程”。嗯，没错。就这一点而言，既然我们已经过了实验阶段，我很好奇高管和经理们现在是如何评估人工智能的**投资回报率**的，以及他们目前希望从中看到什么。所以，你们是要用内部程序员取代所有第三方**SaaS**承包商吗？从实际的**员工人数**和**成本节约**角度来看，这将是什么样子？我们现在可以得到一些具体的细节。所以我很高兴地说，我们确实请来了最完美的嘉宾，我们之前也请他来谈论过人工智能，他所在的公司也很快地投入了这项技术。我们上次和这位嘉宾交流是在2024年，即使从那时起，感觉也像是人工智能世界的“光年”了。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And I'm Joe Weisenthal. Joe. The thing about AI, I feel like it's accelerated all of our timelines, right? Like, it's phenomenal to me to think back that, like back to the days of ChatGPT. And when did that come out? 20 2020 2220. 2222? That's just crazy to think. And then really unbelievable the gap. And I've been thinking about this like just a the explosion of capabilities. Yeah. And the thing I've been thinking about is that, you know, after the first year or so and it came out, you know, we talked to executives and we were like, how are you using AI and your workflow? And everyone's experimenting. It's great. Everyone is using changing because I was very vague. And now in 2026, the so story is that AI is so powerful that it's going to destroy all these legacy software companies. So what I would say is we must be past the age of experimentation. I think that to. Really use cases. Using it better have some example of like, here is a workflow where we're using. Well, exactly. And to this point, now that we're past the age of experimentation, I'm very curious how executives and managers are actually evaluating the return on investment in AI and what they actually want to see from it at this point. So, you know, are you going to replace all your third party SAS contractors with internal coders, and what does that look like from an actual headcount perspective, from a cost savings perspective? We can actually get some concrete details on this now. So I'm very excited to say we do in fact have the perfect guest, someone who we had on before to talk generally about AI and someone at a company that has been doing, you know, they got into it pretty fast. The last time we spoke to this person was in 2024, and even since then, I guess it just feels like light years in AI time.
</details>

**特蕾西·阿洛韦**: 所以关于人工智能最近几年的最后一件事是，当 **ChatGPT** 刚问世时，我玩了很多，你知道的，我写诗歌什么的。但我敢打赌，如果你真的看我的AI使用情况，会发现它经历了一个低谷，我没有真正获得任何生产力，它没有我需要的任何功能，仍然有点像个玩具。所以我在最初几个月有一段高强度使用期，然后就是低谷。而现在，随着功能扩展，特别是**云代码（cloud code）**，我发现了各种新事物。所以我们正走出低谷。我想很多人都在找到新的用途，至少如果我能从自己的经验来推断的话。是的，绝对如此。所以我们确实请来了最完美的嘉宾。我们请回了**马可·阿根蒂**，他当然是**高盛**的**首席信息官**。我们曾在2024年8月的播客中请过他。马可，非常感谢您今天再次回到节目中。

<details>
<summary>Original English</summary>

**Tracy Alloway**: So just one last thing on the last few years of AI, which is that when ChatGPT used it, when it when it came out, I played around with a lot, you know, and I have read poems and all this stuff. And then I bet if you actually looked at my AI usage, went for through a trough, whereas like, I wasn't really getting any productivity, there was nothing it really could do that I needed and still sort of seemed like a toy. So I had this like intense burst of use for the first several months and then this trough. And now these days, with the expansion of capabilities, particularly cloud code, I'm finding all kinds of new things. So there is like we're coming out of the trough. I think a lot of people are actually finding things, at least if I can generalize from my own experience. Yeah, absolutely. So we do, in fact, have the perfect guest. We've brought back Marco Argenti, who is, of course, the chief information officer over at Goldman Sachs, someone we had on the podcast back in August of 2024. So, Marco, thank you so much for coming back on today.
</details>

**马可·阿根蒂**: 谢谢邀请。

<details>
<summary>Original English</summary>

**Marco Argenti**: Thank you for having me.
</details>

### AI发展速度与高盛的实践

**乔·魏森塔尔**: 对您来说，情况变化有多大？在人工智能时间里，2024年现在感觉像20年前吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: How much have things changed for you? Does 2024 seem like 20 years ago now in AI time?
</details>

**马可·阿根蒂**: 是的，我几乎都不记得当时发生了什么。这是一种委婉的说法，意思是您忘记了我们在播客上谈过什么？也许是吧。但实际上，现在几乎每周都有新的变化。如果我回顾过去一年的演变，不仅仅是一年前，甚至是六个月前发生的事情，我认为简直是革命性的。一年前，我们几乎不谈论**智能体（agents）**，这个词几乎不存在。我们使用人工智能就像一个聊天伙伴。是的，当时它会告诉你：“哦，对不起，我不知道美国总统是谁，因为我的信息截止日期是一年半前”，或者类似的事情。现在你可以说，“嘿，我的航班取消了”，它会重新规划你所有的行程，检查可用的航班，它会做所有这些个人助理的功能。这在公司中也转化成了日常任务中的大量实用价值。所以，我想说，我喜欢对我的团队，也对所有人说，这不是演习，这是真的。我们不再处于实验时代。这是一种现在可以为你做很多事情的工具。所以我们让它发挥作用，从开发人员开始，并扩展到许多其他领域。所以，我想说，如果我看看这些模型能力的提升，我们在过去六个月左右看到的这种**高级推理能力**的演变，我想这最终让我们有信心，可以在适当的监督下，将人工智能用于日常工作。而且，在很多情况下，对于**关键任务应用**来说，它不再是玩具，你可以期望它能带来结果。我认为这是最大的变化。所以今天我想说，没有人不受其影响。我们把我们的 **GSI（GSA 助理）**分发给了**47,000名员工**，他们中的大多数人每天都在使用，甚至每天多次使用。有趣的是，这就像你第一次看到像**微软Excel**这样的工具时，你几乎无法预测人们会用它做什么。它可能最初是为了进行某种会计工作而诞生的，然后人们在上面编写了整个应用程序，或者用它进行项目管理等等。人工智能也正朝着这个方向发展。如果我看看人们用它做了什么，每天都会有令人惊讶的事情发生，因为……

<details>
<summary>Original English</summary>

**Marco Argenti**: Yeah, I barely remember even what, what happened back there? That's a nice way of saying you forgot what we talked about on the podcast. Maybe that. But literally, like, things are really changing on a on a weekly basis almost right now. And, and if I look at the evolution, not only, since, a year ago, but events in six months ago, I think, it has been nothing short than, than revolutionary. A year ago, we barely talked about agents or the word almost didn't exist. We were using AI is like a chat companion. Yeah. There was, Yeah, it was telling you. Oh, I'm sorry, I don't know who's the president of the United States, because, you know, my cutoff date is like a year and a half before or things of that nature. Now you can say, hey, you know, as a as a person, you can say, hey, my plane, my plane just got canceled and is going to redo all your plans, is going to check for, you know, like available flights is going to do all these, capabilities of personal assistant, and, and that translates in corporations also in a lot of utility that you can see in everyday tasks. So, I would say, you know, what I like to say, to, you know, to my people, but also in general, let's say this is not the drill. This is real. You know, it's not the age of experimentation anymore. This is a tool that now can do a lot for you. And, and so we put it to work and we put it to working, you know, starting from developers. But on expanding in many, many other areas. So, I would say, actually, if I look at the increase of capabilities of these models that, what well, we've seen in the last six months or so with really the evolution of, this advanced reasoning capabilities, they came out, I think, that finally got us the confidence that, you can use, AI for every day's work with the right supervision. And also, you know, in many cases for mission critical applications, is not a toy anymore is something that, you know, you can expect results from. And I think that's the biggest change. So today I would say that, there is nobody that is not touched by, you know, we gave our, GSI or GSA assistant to 47,000 people. Most of them use it every day. More. Most of them use multiple times a day. And what's interesting is, it's like, you know, like the first time you see a tool like, know Microsoft Excel, you can almost not predict what people are going to do with that. Okay. Maybe it's born for, you know, doing some form of accounting and then people write entire applications on top of that or use it for project managers, what management or things of that nature. And AI is kind of turning, turning that way. If I look at what people do with that, it's, it's, it's really things that surprises every day because,
</details>

**特蕾西·阿洛韦**: 但为什么不给我们举一些例子呢？那么现在，在生产环境中，你目前在高盛看到了哪些以前不存在的工作流程或新颖事物？

<details>
<summary>Original English</summary>

**Tracy Alloway**: But why don't you give us some examples? So in production right now, what are some workflows or novel things that were not workflows before the you see within Goldman that I was doing for people today.
</details>

### AI在金融领域的应用案例

**马可·阿根蒂**: 那么我们从 **GSA 助理**说起。它能回答基于外部和内部数据的真正复杂的问题，这些问题以前通常需要数小时甚至数天，有时甚至是数周才能得到答案。它可以为你进行非常复杂的专题研究。例如，我们可以提出来自客户的问题，比如“**霍尔木兹海峡**最近的地缘政治事件如何影响这个投资组合？潜在的**再平衡策略**是什么？”或者，你可以问，“美联储关于**利率**的某个决定如何影响某些资产的**波动性**？”所以你提出了这种多维度的问题，**GSA 系统**会调用模型，检索相关信息，并制定一个计划来回答这个问题。这才是关键，因为这些**人工智能**在回应之前会进行规划，而不是仅仅给你第一个想到的答案。所以，从表面上看，这是一种最常见的用例，即我们通过更快地回答内部和外部问题来真正提升客户体验。但这是真正复杂的问题，而不是简单问题。我们连接了数百个数据源，最重要的是，这也是我告诉所有问我“嘿，给我一些关于如何在公司中实施人工智能的建议”的人的一点：**数据质量**才是决定人工智能好坏的关键。所以我们做了大量工作，不仅要获取大量数据，还要让它对人工智能来说是可理解的。例如，为了更深入地说明，我们有一个名为 **Legend AI** 的工具，它是我们的湖仓（lakehouse），它允许你从查询到 **MC 服务器**，连接到 GSA 助理，即从数据到答案。你只需两三次点击就能完成所有这些。它会为你完成所有这些。所以数据的质量和数量，不仅仅是这些，因为这里不仅是痛苦的教训，也是你**需要管理你的数据**的教训。你会不成比例地得到更好的答案。这就是它的驱动力。所以这是一种知识方面的人工智能，我想说它是最广泛的，因为公司里的每个人都有它。而且它的用户量是最高的。我们每月处理的**提示词（prompts）**超过一百万，而且增长速度非常非常快。当然，你问我生产中的实际影响，高盛的每个开发人员都配备了一个巨型人工智能。我们可能是最早推出 **Darwin** 的公司之一，它是一款完全巨型的开发人员助理，大约在一年前就推出了。我们有**云代码**，我们还有许多其他工具，**GitHub Copilot**，智能体等。但在这一点上，你确实看到了质的变化。毫无疑问，它正在改变开发人员的工作方式。顺便说一句，这不仅仅是更高效地做同样的事情。它正在改变开发人员实际工作的方式。这非常容易看到。这如何改变了开发人员的工作范式。你更像一个**产品经理**。你更像一个**规划师**。你更像一个**创意人员**。总的来说，对于今天的开发人员来说，最重要的是能够**解释事物**，而不是直接跳进去编写代码。

<details>
<summary>Original English</summary>

**Marco Argenti**: So let's start from, the GSA assistant. Great. That can answer really complex questions based on external and internal data that generally before used to take sometimes hours or even days, sometimes weeks to answer. Okay. It can do very complex research for you in topics. There are, you know, for example, we can ask questions, that come from clients such as a hey, how does the recent geopolitical events on the Hormuz Strait actually, impact this portfolio? What could be a potential rebalancing strategy? Or, you could ask, intersection of, you know, like, I don't know, how does, a certain fed decision on interest rate actually impact, you know, the volatility of certain assets. So you ask this multi-dimensional questions and, what GSA system does, it calls out the model, retrieves, the relevant information and creates a plan to answer that question. And that's kind of the key, because this AI's, they really plan before responding rather than just giving you the first thing that comes to mind. And so that's what kind of at the very surface thinks that one of the most, you know, common use cases, which is, we really enhance the client experience by being able to answer questions internally and externally in a much, much faster way. But really complex question, not simple questions. We had to wire up hundreds of data sources and also most importantly, which is something that I tell everybody that asked me, hey, give me a, you know, some, some, some advice on how to implement the AI in a corporation. Data quality is really the determinant between good AI and not so good AI. And so we do a lot of work to not only take a bunch of data, but also making it, understandable to, to the AI. So for example, to better be deeper, we have a tool called legend, the AI, which is our lakehouse, which allows you to go from, query to MC server, connect to GSA assistant, i.e. from data to answers. You can wiretap literally in 2 or 3 clicks. And it does all of that for you. And so the quality of the data, the quantity of the data, not only that, because not just the, you know, the bitter lesson here, but is also the lesson of, you need to curate your data. You get better answer disproportionately. That's something that is driven there. So that is kind of the knowledge, aspect of AI, which is, I would say the most widespread because every single one in the firm has that. And it's, you know, the highest users. We are like way above a million prompts per month. And it's growing really, really, really fast. And then, of course, you know, you're asking me like really impact in in production, every developer in Goldman is enabled with a gigantic AI. Okay. So we were probably one of the first, if not the first to launch Darwin almost like a year ago, which is the fully gigantic, developer assistant. We have cloud code. We have, you know, many other tools, GitHub, copilot, agent, etc. but, on that, you really see the step change. There is no question that, that is changing the way developers work. And by the way, it's not just about doing the exact same things more efficiently. It's changing the way developers actually do their work. And that is very, very easy to see. How, you know, that kind of changes the paradigm of what a developer does. You're much more of a product manager. You're much more of a planner. You're much more of an idea. Generally, the most important thing for a developer today is to be able to explain things rather than jumping and coding things.
</details>

**乔·魏森塔尔**: 这引起了我的共鸣，因为我真的很喜欢凭感觉写代码（**vibe coding**），但我无法解释它是如何工作的。所以如果有人说，你知道，我喜欢构建一些小型玩具应用程序之类的，但我真的很焦虑。我无法解释，这就是为什么我不是一个软件开发人员。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And that resonates because I really like vibe coding, but I can't explain how any of it works. So if someone is like, I would, you know, I like build little like toy apps and stuff, but I get really anxious. I couldn't explain, that's why I'm not a software.
</details>

**特蕾西·阿洛韦**: 是的，是的。关于这一点，当谈到人工智能提高生产力时，人们倾向于泛泛而谈。或者说人工智能改变了我们的工作方式，或者它带来了一些新想法。在高盛，您作为一名经理，审视着所有这些业务的底线，您希望看到您的开发人员使用**云代码**这样的工具时，具体能带来什么结果？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yeah, yeah. Well, just on this note, I mean, people tend to talk in generalities when it comes to AI boosting productivity. Or maybe AI changes the way we work, or it leads to some new ideas from your seat at Goldman. You know, you're a manager. You're looking at the bottom line of like all these businesses. What exactly is the outcome, the specific outcome that you would like to see from your developers using something like cloud code?
</details>

### AI提升开发效率与项目交付

**马可·阿根蒂**: 这实际上是为了提高**产出**。所以我想看到——我今天早上还在讨论这个问题。我查看了一些关于我们的**云迁移**的一些可交付成果的报告，这对我们来说非常重要。我看到一个非常大的项目，它不仅是绿灯，还**提前了两个月**。我当时说，这就是我们知道事情会成功的方式。你将持续看到项目提前完成，这意味着人们有抱负，他们想做更多，因此你的产出将比以前高得多。听着，对于开发人员，每个人都会问的最大问题是：好吧，你要做什么？你要裁减开发人员吗？等等。所以首先，在我过去30年左右看到的所有创新中，我从未见过真正减少开发人员数量的时刻。因为如果我看看那些因为预算原因、复杂性原因、优先级原因而没有在某一年完成的事情，积压的工作很多，但其中很多确实推动了业务增长。所以能够这样做是很好的选择。你知道，你现在可以选择说，我有120%的产能。我有130%的产能。我想多做130%。太棒了。如果我不做，我也有减少的选择。所以，我们就是这样衡量的。它确实影响了交付时间。它是产出。它基本上是质量和时间，你知道，**质量实际上变得更好，时间线缩短了**。所以这就是我们衡量的。

<details>
<summary>Original English</summary>

**Marco Argenti**: It's really about increasing the output. So I want to see I was actually having this discussion this morning. I was looking at some of the reports on some of the deliverables for our cloud migration, which is a very important thing for us. And I was looking at this really big, a project that was saying it was not only green, it was like two months ahead of schedule. And I was saying, this is how we know when things are going to work. You're going to consistently start seeing projects that are actually finishing ahead of schedule, which means that then people are ambitious, they want to do more, and therefore you end up with output that is much higher than what you had before. And listen with developers, obviously, the biggest question that everybody ask is, okay, what are you going to do? Are you going to cut developers this and that? So first of all, with all the innovation that I've seen in the last 30 years or so, I kind of never seen a moment where really people were reducing the number of developers, because if I look at, the things they were not doing in a certain year because of budget reasons, because of complexity reason, because of prioritization, the stuff that is below the cut of the backlog, it's a lot and not a lot of that is really driving the growth of the business. So it's good to have the optionality to do it. You know, you have the optionality of, say, I now I have 120% of my capacity. I have 130% of my capacity to do. I want to do 130% more. Great. If I don't, I have the option to reduce, so but so that's really what, how we measure it. It's really the impact on the timelines of delivery. It's output. It's basically quality and timeline becoming you know, quality gets actually better and the timelines get short. So that that's what we measure.
</details>

**乔·魏森塔尔**: 显然，今年市场的一个大问题是人工智能对**传统软件提供商**有什么影响。关于它们可能如何被颠覆，有各种各样的理论。我想到有报告说，**Anthropic** 在高盛内部有所谓的“**前沿部署工程师**”。所以 Anthropic 的员工在高盛内部构建人工智能系统，这也许可以取代一些传统软件。您能说一下，当一件软件需要谈判时，力量平衡是否发生了变化？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Obviously one of the big questions for the market this year is what is the impact of AI on legacy software provider. And there's various theories about how they could be disrupted. And there are reports, I think about, anthropic having quote, forward deployed engineers inside Goldman Sachs. So anthropic employees building out AI systems internally, maybe that could, you know, replace some legacy software right now. Can you say, like there is a change in the balance of power when there is a given piece of software up for negotiation?
</details>

### 传统软件与AI时代的颠覆

**马可·阿根蒂**: 我认为总体上是的。首先，这种紧张关系一直存在。例如，想象一下当软件不运行在**云**上的时候。然后突然间，一群新供应商走过来对你说：“嘿，等等，为什么你们要在大型机或本地服务器上运行它？为什么不把它运行在云上？”或者还记得软件需要安装的时候吗？然后一切都变成了基于浏览器的。所以，总是存在一个**更新周期**。我想说的是，今天这个更新周期的速度快得多。这就是它的本质。我通常会抵制进行非常宽泛的分类。**人工智能**，顺便说一句，它是一个尽可能大的假设，就像说“计算机”一样。是的。但即使是软件也范围非常广。所以在软件类别中，我认为有赢家也有输家，在长期来看有赢家也有输家。但这就像人们倾向于把它归为一类，然后可能把孩子和洗澡水一起倒掉。所以我举个例子。我问自己的问题是，未来几年我将拥有哪些供应商，哪些软件？软件通常与流程或特定的工作方式相关联。它为你做一些事情。他们以应用程序的形式提供给你使用。真正的问题是，这个流程和/或工作方式在五年后会保持不变，还是会改变？然后你就可以判断该软件在这种变化下是否会保持稳健的可能性。例如，会计或结账在五年后会大不相同吗？我不认为会。它真的没有太大变化。我的意思是，一切都在变化，但它没有太大变化。所以如果你在**总账**这类业务中运营，我不认为会突然出现一个GPU或云服务能够神奇地帮你结账，你仍然需要做很多会计工作。而且重要的是，它受到严格监管，对吧？它受到极其严格的监管，你知道，不同的司法管辖区，不同的国家，不同的产品，不同的行业。所以对我来说，那一部分处于**安全模式**。然后你再看光谱的另一端，有时你会发现有些软件，它与人们现在做事的方式是吻合的，就像软件本身就是其中之一。你知道，如果你看看软件开发人员的生命周期，很多都在变化。开发人员正在通过开发规范来开发软件。所以，如果你过于沉溺于底层机制，而没有适应人工智能或智能体在软件开发生命周期的部署、回滚、监控、可观测性等方面的工作，我认为这条道路将受到极大冲击。或者，如果你在事物上添加某种用户体验（UX），那是另一类。所以，你知道，一个非常简单的流程。我不知道，你正在做调查或费用报告之类的。现在人们会开始期望他们的个人助理或智能体为他们完成所有这些机械性工作。因此，我认为这条道路可能充满了更大的不确定性。所以我总是先问自己流程问题——流程转型部分，先问问题，然后才考虑什么工具能支持它。但就在这一点上，你们是否已经用内部通过AI开发的东西取代了任何第三方软件提供商？我们已经终止了一些合同。是的，绝对如此。

<details>
<summary>Original English</summary>

**Marco Argenti**: I think generally there is. Okay. If first of all, that is kind of always been that tension because, imagine, for example, you know, like imagine when they were software, they didn't run on the cloud. And then all of a sudden a bunch of new vendors are coming to you and say, hey, wait, this like, why are you running that on your mainframe or your or your on prem? Why don't you run it in the cloud? Or remember when software needed to be installed? Then everything became browser based and so? So there is always been a little bit of a cycle and renewal. What I say is that today that cycle of renewal is is much faster. That's really what it is. And I would say I generally resist, making like really broad categorizations. I is, by the way, largest possible assuming it's like saying computers. Okay. Yeah. But even software is very broad. And so within the software, category, I think there are winners or losers and there are winners and long term and losers in the long term. But it's really like, people tend to make it the category and then then maybe throw the baby with the bathwater. So here's an example to me. The question that I asked myself, with regards to what is which vendors am I going to, which software am I going to have like a few years down the road? Is software generally is attached to a process or a certain ways of working? Okay. It does something for you. And and they put it in the form of, of an application that you use. The real question is, is that process and or ways of working going to be the same, or is it going to change in five years? Then you can determine what the is, basically the likelihood that the software is going to be robust to that or not. For example, is accounting or closing the books going to be very different from five years from now? I don't think so. Really, he hasn't really changed. I mean, everything changes, but he hasn't really changed much. And so if you are operating in the general ledger type of category, I don't think, there is a, you know, all of the sudden you take, you know, a GPU or a cloud that is going to close your books magically, you know, you should. Have to do the accounting, and. You still need to do a lot of that. And it's very regulated importantly. Right. It's extremely regulated, you know, jurisdiction by jurisdiction, country by country, you know, product by product, industry by industry. So that part is scandal to me, you know, in, in kind of the safe mode way. And then you go to the, you know, other end of the spectrum and you have, sometimes, you know, software that, you know, kind of is aligned to the way people do things today, like software being one of them. You know, like if you look at the software developer lifecycle, a lot of that is changing. Developers are, are, are, are developing software by developing specs today. And so if you are too much in the weeds down there in that mechanics and you don't adapt, for eyes or agents doing that work, software development, lifecycle deployments, rollbacks, monitoring, observability and all that, I think that path will be very much disrupted. Or if you're adding a sort of a UX on things, that's another class. So, you know, a very simple process. I don't know, you're doing surveys or expense reports or whatever. And now people are going to start expecting, you know, their personal assistants or agents to kind of do all that mechanic for them. And so I think that path is probably something that has a bigger question mark, on top. And so I always ask myself for the process question first, the process transformation section, a question first, and then a consequently, what's the tool that is going to support that? And just to press on this point, though, have you replaced any third party software providers with something that's been developed internally through AI? We have we have terminated contracts already. Yes, absolutely.
</details>

**乔·魏森塔尔**: 好的。我现在不会再问您后续问题了，因为我知道您的名字会出现在这些股票上。但我总的来说会问。当然，当然。你知道，这就像整个“购买与自建”的问题。好的，是的。这个等式已经发生了很大的变化，因为以前，“购买与自建”总是像“好吧，各位，构建这个需要多长时间？”你得到了答案，就是我们可以用X年和X百万美元来完成。现在我开始看到有人对我说：“顺便说一句，我这周有一些时间，然后这是一个完美运行的应用程序。”所以，对于简单的应用程序来说，构建成本，或者至少从时间角度和额外成本角度来看，已经大大降低了。所以现在，你知道，小东西很可能会被构建出来。那些非常大型的软件，需要部署到成千上万的人，等等，那种大的复杂性，你知道，我们都在家里用我们的**云代码**玩一些小玩意。你知道，仍然有一些粗糙之处，所以很难想象所有大型应用程序会突然消失。所以，我真正想说的是，如果我看看我今天购买的应用程序，有很多都是小型应用程序。所以我想说，构建的钟摆正在开始摆回自建的一方，至少对于那个类别来说是肯定的。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Okay. Now I'm not going to ask you your follow up questions again, because I know that your name's. On these stocks. Like I would I will. But overall, yes, absolutely. Absolutely. You know, the thing is like the whole buy versus build okay. Yeah. The equation has changed quite a bit because if you know before it well buy versus build was always like okay guys how long does it take to do the to build this. And you get that answer, which is where we can do it in like, you know, X amount of years and X amount of millions of dollars. Now I'm starting to see people coming to me and say, by the way, I had some time, you know, this week and then here is a perfectly working application. So the cost, or at least, you know, for simple applications, the cost of kind of, you know, but builder from a time perspective and from a, you know, extra cost perspective has gone down quite dramatically. So right now, you know, like the little things are most likely going to be build the very big large, the software that is to be, you know, deploy that scale across thousands of people and etc., so that that big complexity, as you know, from, you know, we all do toy stuff with our cloud coats at home and whatever. You know, there are still some rough edges like, you know, and so it's hard to think that all all of the sudden the big applications are going to disappear. And so that's really what, what I'm saying that if I look at the applications that I buy today, there is a lot of small applications. So I'm saying and so the build is kind of the pendulum is starting to swing back towards the build, at least for that category for sure.
</details>

### 前沿部署工程师与AI集成

**特蕾西·阿洛韦**: 什么是**前沿部署工程师**？我知道这是2026年的热门流行词之一。我看到头条新闻说，**Anthropic** 在高盛有前沿部署工程师。我完全不知道那是什么意思。

<details>
<summary>Original English</summary>

**Tracy Alloway**: What is a forward deployed engineer? I know that's like one of the hot buzzwords of 2026. And I saw headlines that there were anthropic forward deployed engineers at Goldman. I have no idea what that means.
</details>

**乔·魏森塔尔**: 是的，你知道，那个术语是什么？我觉得他们到了那里后会做什么。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. You know, like what is that term? I think they do when they got there.
</details>

**马可·阿根蒂**: 好的。所以我认为，那个名称已经改变了很多。过时了。不，不，不，不，不，不，我的意思是那是最新的。哦，所以你完全是在那个术语的最新版本中。但请记住，我的意思是曾经有一段时间，你们称他们为**解决方案架构师**。对吧。所以，重点是现在，我认为我看到的一个趋势，对我们来说也是如此，当事情变化如此之大和如此之快时，你会想要追溯这种新事物的起源。好的。所以你拥有的中间环节越少，可能你前进的速度就越快。所以直接与模型提供商合作通常是个好主意，因为如果你在中间放一个人，这家公司将不得不接受培训。它将不得不，你知道，有一个周期，在这一点上，快速的变化会让你慢下来。所以这个术语的第一个含义是，那些人实际上通常是构建产品的人。他们通常是构建云或GPT或X的人。所以这是第一个区别，直接接触AI生产的源头。其次是，他们通常是**产品人员**。所以是那些真正构建了这些工具的人，而不是那些更像支持和部署人员的人。所以这种特点是，你拿经典的销售支持团队或解决方案支持团队，他们主要做集成。当事情如此之快时，你知道，就像，想象一下如果有什么东西，我不知道，如果云样式工作变化如此之快。与其找一个时尚助理，不如找裁缝，因为他们真的能做到。是的。你知道，事情变化如此之快。所以那些就是裁缝。

<details>
<summary>Original English</summary>

**Marco Argenti**: Okay. So I think, Lisa, that name has changed quite a bit. Out of date. No no no no no no I mean that is the latest. Oh so you are fully you are in the V in the V v latest of of that term. But remember, I mean there was a time where you used to call them solution architects. Right. And so, so the point is right now, I think one trend that I see, which is also kind of true for us, is when things change so much and so rapidly, you kind of want to go to the origin of who produces this new thing. Okay. So the least intermediaries you have and probably the faster you can go. And so going and working directly with the model providers is generally a good idea, because if you're putting someone in the middle, this company is going to have to be trained. It's going to have to be, you know, there is a cycle which, at this point, a very rapid change is going to slow you down. And so the first thing that that term means is, those are people that are actually normally building the product. They're normally building the cloud or GPT or X or so that's the first differentiation there, straight to the source of of of of of the, of the AI production in a way. And second is that, they are generally product people. So people that have actually built those tools, rather than people that are more like support and deployment people. And so this characterization is you take the classic, you know, sales support, team or solution support team, which was mostly doing integration. And when things are so rapid, you know, you know, it's like, you know, imagine if there is like something like, I don't know if, if the cloud style works changes so fast. Instead of a fashion assistant, you want to talk to the tailor because they can actually make it. Yeah. You know, things are changing so fast. So those are the tailors.
</details>

**特蕾西·阿洛韦**: 关于这一点，我们听到支持 **SaaS** 的一个观点是，集成仍然非常重要，这将是很多事情的主要障碍。您是否发现人工智能正在使集成更快？现在这是否已经变得无关紧要了？

<details>
<summary>Original English</summary>

**Tracy Alloway**: So on this note, one of the things we heard in support of Sass was this idea that while integration is still going to be really important, and that's really going to be like the major hurdle for a lot of the stuff. Have you found that AI is making integration even faster at this point? Has that, you know, basically become irrelevant nowadays?
</details>

**马可·阿根蒂**: 不，我认为集成仍然极其重要，特别是对于行业所称的**记录系统**。所以当你做一些事情，比如当你执行一个流程，那么你有一个数据源，例如你的 **CRM 系统**可能是一个记录系统，或者，你有你的客户记录系统，你的会计记录系统，当它们成为答案的**权威来源**时，它们需要与公司的其余部分、其余的数据、其余的应用程序集成。所以我可以看到，那些位于这些系统之上的供应商，我们可以说他们会实施，没有人比他们更适合实施人工智能，这种人工智能将向外扩展并实际进行那种集成。所以我认为那些供应商会进化，这样你仍然可以获得相同水平的自动化，你仍然可以获得相同的速度优势，但它有点像是从内部产生的。我认为这部分可能仍然非常有价值。所以总的来说，我完全不反对SaaS这个类别。但总的来说，我有不同的看法，关于谁将真正适应未来，谁不会适应未来。

<details>
<summary>Original English</summary>

**Marco Argenti**: No, I think integration is is extremely important, especially, you know, for, you know, what the industry calls like systems of record. So when you do something like, you know, when you do a process, so then you have a source of data, like, you know, your CRM systems could be a system or record or, you know, you have your client system or record your accounting system or record and those when they become the authoritative source of an answer, they need to integrate with the rest of the FA and the rest of the data, the rest of the applications. So I can see that those vendors that sit on top of those, we can argue that they will implement, there's nobody that is better position than them to implement the AI that will kind of reach outwards and actually do that kind of integration. So I think those who will evolve, so that, you still get the same level of automatism and you still get the same, the same benefit of speed, but it kind of comes from within. I think that part is probably something that, that would be remain very valuable. And so in general, I don't have anything against the again, I don't have anything. It has the SAS category at all. But I overall but I have you know, as I said, of different opinions on who actually is going to adapt to the future and adapt to the future. And those who don't know.
</details>

**乔·魏森塔尔**: 您提到了人们在周末有额外的几个小时，早上来上班时说：“我有一些额外的时间，所以我决定做这个。”在有限的时间内，人们凭感觉写代码（**vibe coded**）做出的最酷或最新颖的例子是什么？是那种在两年前根本不可能发生的事情？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: You know, you mentioned this idea of people have a few extra hours over the weekend and they come in in the morning and they're like, well, you know, I had some extra time and I decided to to do this. What's the coolest or most novel example of something that people basically vibe coded in a limited amount of time that wouldn't have happened, say, two years ago?
</details>

### AI辅助下的快速创新案例

**马可·阿根蒂**: 我见过人们做过，比如将遗留应用程序从本地迁移到**云**端，一旦他们获得了这些工具的支持，只需要很短的时间。我见过有人在开会时，当他们没有注意会议内容时，构建了一个完整的**企业差旅助理**，它可以查看你的日历，航班延误信息，并处理改签事宜，简直就像在开会时做的。

<details>
<summary>Original English</summary>

**Marco Argenti**: So, I've seen people doing, like cloud migrations of, of, of legacy applications that were on premise, you know, once they have been enabled with, with those tools, a little tiny matter of hours, I've seen someone, build, a complete like, travel assistant, for corporate travel assistant to that, that looks at your calendar, it looks at the flight delays and look at the rebooking stuff, literally, like in a doing a meeting where they were not paying attention. So.
</details>

**乔·魏森塔尔**: 这就是我现在正在做的事情，在录这个播客的时候。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So those are some of the things that's. What I'm doing right now. And while we're doing this podcast.
</details>

**特蕾西·阿洛韦**: 实际上，这正把我带到我接下来想问的问题。我很好奇，大型公司是否有像过去那样的**代币预算**，就像他们有美元预算一样？所以，我希望能无限访问编码模型等等，并真正玩转它并尝试使用它。这是我最喜欢的问题之一。但我很好奇，您如何看待公司内部的**代币分配**，以及是否存在内部的计算资源竞争？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Actually, that brings me to exactly where I wanted to go next, which is I'm curious, like, do a large corporations have a token budget the way they would have a dollar budget in the past? So, like, I would love to have unlimited access to coding models and whatever and actually just play around and try to work on it. It's one of my favorite questions. But I'm curious, like how you think about token allocation within the firm and whether there is intra firm competition for compute?
</details>

**乔·魏森塔尔**: 对于计算资源？是的，代币分配可以像包含在您的绩效中一样，对吧？如果您做得好，您会得到更多。不同的团队等等。这是否是您规划时会考虑的一部分？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: For compute? Yeah, it token allocation could be like included in your performance. Right? If you do well you get more. Different teams and stuff like that. Whether that's part of what you think about for planning.
</details>

### 代币经济学与AI成本管理

**马可·阿根蒂**: 绝对如此。几个月前，我做了一个预测，并在2026年谈到了我的预测。我说的一点是，**个人助理**将会诞生。这在**Open Claw**等产品早期就已经发生了。然后另一点是，首席财务官将面临**代币冲击**，他们将突然看到他们绝对没有预料到的账单。黄仁勋最近在一次采访中提到，如果我支付一名工程师50万美元，我希望你至少在代币上花费25万美元。现在，很多人指出，这就像理发师说你真的需要每周理发一样。尽管如此，我们谈论的是一些相当大的数字。比**Claude Max**计划的200美元要多得多。所以现在谈谈这个。首先，第一课是，你需要**集中管理**模型的访问权限，这样你才能监控它并对其进行优化。所以每个人都去调用API并开始消耗代币的“狂野西部”是一个大问题，你会发现这是个大问题。这就是我们构建 **GSI 平台**的原因，它有一个名为**模型网关（model gateway）**的东西。模型网关智能地将请求路由到**质量和成本的帕累托前沿（Pareto frontier）**的组合。所以你必须集中管理。它不是一刀切的，因为在很多情况下，如果你问“天气怎么样”，你不需要调用**Claude 4.6**，你可以让任何你在本地廉价运行的模型来回答。所以有办法优化。在你开始谈论“你消耗太多工具”之前。我们刚刚——这对我来说很有趣——你试图解决的问题很大一部分是，我们知道，像**ChatGPT**一样，他们会智能地路由，你知道，他们会做一些。你访问SI.com，他们会尝试将其路由到最好的模型，甚至可能存在一些利益冲突，因为他们可能想将其路由到最便宜的模型。用户想要性能最好的模型。但是你们高级工程师的工作中有多少是本质上解决了正确查询路由到帕累托最优模型的问题？这是AI中心团队花费时间的一大部分。平台团队非常担心，例如，我从哪里获取这个问题的正确数据，以及我应该围绕它编写哪个模型？所以这是一个大问题，因为我提到了**帕累托前沿**，意味着在**质量**（我们不想妥协）和**实际成本**之间的优化。你知道，你可以获得相同质量但价格点非常不同的结果，因为并非所有问题都要求最昂贵的文档。所以这是第一点。所以我想说的是，我的理念是尝试让开发人员或用户**摆脱代币焦虑**。这有点像电动汽车。好的。在某个时候，如果你有80英里的续航里程，你总是会优化路线。也许我不会去那里。我今天不需要冰淇淋。或者后来，你以一种你没有使用的方式限制了自己。真的没有有用的最优微优化。我们不希望人们现在就去那样做。这是一个人们需要真正找到如何利用人工智能做更多事情并做到最好的时期。让我们——我的意思是在内部，在一个中心团队中——以一种我们会使其经济实用的方式进行优化。我认为，**减少代币焦虑**是一个巨大的挑战。但我认为它确实释放了创造力，以及你可以用人工智能做什么。这也有点像，你知道，有些问题你不希望过早优化。好的，好的。例如，是的。你现在想优化多少时间？我记得我们曾经优化网页的加载方式，因为它们加载太慢了。然后有一次，编辑或其他人说：“为什么我不能再放一张图片？”然后人们开始说：“好吧，为什么你不这样做？然后我会在后端优化你的图片，而不是要求你最多只能在主页上放三张图片。”对。所以这就是我想要的方法。现在，我宁愿让他们在使用的这一边，让我担心优化问题。另一点是，人类的工作时间总是最昂贵的成本。好的。所以只要你的**代币成本**每小时低于你的**工资成本**每小时，那就是一种积极的**投资回报率**。所以在那一点上，没问题。

<details>
<summary>Original English</summary>

**Marco Argenti**: Absolutely. So, you know, a few months ago I did, and I, I spoke about predictions for 26. And one thing that I said was, you know, there's going to be the birth of the personal assistant. And that kind of happened with Open Claw and all that stuff kind of early on. And then the one was, there's going to be a token sticker shock for CFOs, right? And all of the sudden they're going to start seeing bills that they absolutely did not expect. Jensen Wong is it an interview today or. Sorry, not today. In recent weeks, something about like, oh, if I'm paying an engineer $500,000, I hope that you're spending at least $250,000 on tokens. Now, again, as many people pointed out, that's like the barber saying, oh, you really need to get haircuts every week. Nonetheless, we're talking about some pretty big numbers. A lot more than just like a Claude Max plan for 200. Right. Now. So talk about that right now. Okay, so first of all. Lesson number one is, You need to centralize the access to models, okay? So that you can monitor monitor it and then optimize it. Okay. So the wild West of everybody goes and calls an API and starts consuming tokens. And then you find out later on is a big problem. And so that's why we built, this GSI platform, which has, you know, what's called the model gateway. And the model gateway intelligently routes requests, to, you know, the combination, the Pareto frontier of, quality and, and cost. Okay. So you got to centralize that. It's not the one size fits all because many cases, if you're asking, you know, what's the weather, you don't need to call on a cloud or 4.6, you can ask it to leave any local model that you ran very cheaply on premise. So there is there are ways to optimize that way. Before you start even having the conversation. You're consuming too much, too many tools. We just this is very interesting to me is a big part of the problem that you're trying to solve is and we know, like, you know, ChatGPT they intelligently root, you know, they do some on there. You go to SI.com and they'll try to route it to the best model, and there might even be some conflict of interest because they probably want to rooted to the cheapest model. The user wants the most performant model. But how much of the work of your senior engineers is essentially solving this problem of the right query? Going to the Pareto optimal. Model, it is, a big a big part of the time of the spent by the AI central group. Okay. Platform group, the platform group work worry a lot about, where do I where do I get the right data, for example, for this question, and which model do I write around it? So that's a big, you know, because again, I spoke about potato frontier, meaning the optimization between a quality which we don't want to compromise and the and the actual cost, you know, and you can be ISO quality, very different, you know, price points because not not all questions are require the most expensive doc. Right. So that's point number one. So what I'm trying to say is my philosophy is to try to isolate, the developer or the user from the token. Anxiety is a little bit like with electric cars. Okay. At one point, if you have 80 miles of range, you're always optimizing routes. And maybe I'm not going to go there. I don't need this, ice cream today or later. You're self-limiting in ways that are kind of, you know, unused. Really no useful optimal micro optimizations. We don't want people to go there yet, at least right now. It's a time where people need to really find the the best way to kind of, you know, do more and do the best possible work with AI. And let us meaning internally in the sort of a central team to optimize it in a way that, you know, we're going to make it economical. And I think, reducing the talking anxiety is a big challenge. But I think it really frees up, you know, creativity and what you can do with AI. It's also like, a little bit like, you know, there are certain problems that you don't want to optimize too early. Okay. Okay. So for example, yeah. How much time do you want to optimize now for? I remember we used to kind of optimize the way to web pages because they were too slow to load. And then at one point, the editors or whatever say, why can't I put yet another image? And then people are starting to say, okay, why don't you do it? And then on the back, I'm going to work in optimizing your images rather than asking you at the most, you can put three images on the on the homepage. Right. So that's the approach I want. People right now, I would rather, have them, on the side of usage and let me worry about optimization. And the other point is really at the end, human hours always tend to be the most expensive cost. Okay. And so as long as, your token cost is, your token cost per hour is less than your wage per hour, that is a kind of a positive ROI. And so at that point, it's fine.
</details>

**乔·魏森塔尔**: 好的。关于这一点，您对未来**代币成本**的看法是什么？它们是会上涨还是下跌？因为您听到不同的说法，其中一种说法是，回到对话的开头，人工智能在几个月甚至几周内发展得如此之快，这些成本注定会下降。但另一方面，我们知道像您在高盛这样的**超级用户**，**超大规模提供商（hyperscalers）**仍然在亏损。那么您认为这些成本长期来看会如何发展？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Well, just on this. No. What's your what's your feeling about future costs of tokens and whether they're going up or down because you hear different things on this, one of the things you hear is that, again, going back to the beginning of this conversation, AI has improved so quickly in the course of, you know, months, if not weeks that those costs are destined to come down. But on the other hand, we know that the hyperscalers are still losing money hand over fist for, you know, power users such as yourself at Goldman. So where do you think those are going over time?
</details>

**马可·阿根蒂**: 我的个人观点是，**代币成本**将会大大下降，但**代币使用量**将会上升。是的，可能甚至更多。所以**总代币成本**实际上将会——我们必须接受它将成为任何组织的主要成本项。它应该与人力成本相比较，而不是与IT成本、TCP/IP数据包成本或计算机成本等相比较。如果你只看所使用的代币数量，对于相同的用例，如果你走推理路线或不走推理路线，如果你走智能体路线或不走智能体路线，如果你走Open Claw路线，它会检查每个，你知道，开始有这些一个接一个触发的任务，然后你必须开始设置验证器等等。所以我认为这种趋势将继续，会有越来越多的这种用例。但代币的单位成本，我相当确定它会下降，也因为你知道，**GPU**变得更强大。它们，你知道，**每瓦成本**有望下降。而且说实话，这些**超大规模提供商**正在做大量的优化，试图在自己的硬件上运行这些堆栈，这也有可能产生一些**规模经济**。

<details>
<summary>Original English</summary>

**Marco Argenti**: I my my personal view is, token cost is going to go down quite a bit, but token numbers are going to go up. Yeah, probably even more. And so total token cost is going to actually we're going to have to accept that is going to be a major item of cost in any organization. And it's to be compared to the cost of people and not to be compared to the cost of, you know, it or tcpip packets or computer or any of that. If you look at just the number of tokens being used, for the same, use case, if you go the reasoning route or you don't go the reasoning route if you go the agent route or not, the agent route if you go the open law route, where, you know, it checks every, every, you know, starts having these tasks that are firing one after the other, and then you have to start to have verifiers, etc., etc.. So I think the trend will continue with regards to more and more of those. But the cost the the the per unit cost of token, I pretty I'm pretty sure that is going to go down also because as you know, GPUs are becoming more powerful. They you know, the cost per watt hopefully is going to go down. And then also like, to be fair, I mean, you know, these hyperscalers are doing a lot of optimizations to try to ram those stacks on their own hard right, which will potentially kind of also generate some economies of scale.
</details>

### 安全、监管与Open Claw的启发

**特蕾西·阿洛韦**: 高盛的员工可以在他们的工作电脑上运行**Open Claw**吗？我很好奇您如何看待人们想要安装这个或那个，因为它们看起来很酷，以及您如何处理安全方面的强制性要求。不是代币焦虑，而是这种“我想安装这个，这太棒了”的感觉。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Can Goldman employees like, run open claw on their work computers? And I'm curious like about the degree to which you have people who like want to I want to install this or this seems really cool. And then think about the security imperative and how you handle that aspect. Not the token anxiety, but the sort of I want to install this, this is awesome.
</details>

**马可·阿根蒂**: 我希望是这样。你知道，作为一家银行，我们在可以安装什么方面非常受限。你不能安装不在公司应用商店中的东西。所以没有办法。

<details>
<summary>Original English</summary>

**Marco Argenti**: I hope it is. You know, like as a bank, we're pretty locked down in terms of what you can install. You cannot install stuff that is not, in the, you know, in the corporate, in the corporate App Store in a way. And so there's no way.
</details>

**乔·魏森塔尔**: 但你觉得你们应该这样做吗？当然没有，但你不能只问克劳德如何安装自己吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: But do you feel like you should? Definitely. No way, though, because can't you just ask Claude how to install itself?
</details>

**马可·阿根蒂**: 但它无法执行。它无法创建实际的**可执行文件**。它确实可以，即使是今天的 **GSA 系统**也能吐出大量代码，但它吐出的是**源代码**。好的，现在我们的源代码无法作为可执行文件运行，所以它需要被构建并转换为可执行文件。它需要被签名。否则，操作系统将拒绝运行它。所以除非你拥有这些，否则它根本不会运行。

<details>
<summary>Original English</summary>

**Marco Argenti**: But he's not gonna be able to execute. It's not going to be able to create the actual executable. He can actually, even GSA system today can spit out a lot of code, but it spits out source code. Okay, now our source code doesn't run executable, so it needs to be built and it needs to be turned into an executable. It needs to be signed. Otherwise the operating system is going to refuse to run it. And so it just doesn't run unless you have that.
</details>

**乔·魏森塔尔**: 但你是否感到焦虑，你知道，初创公司可能存在？而且，你知道，没有大量的初创投资银行，但有各种金融科技公司和其他公司想要侵蚀你们的部分业务，他们可能运行得更快，他们可能对员工允许做的事情更自由等等。你是否觉得你必须保持一定的速度来扩展那些能够运行的可执行文件列表？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: But do you feel an anxiety where you know, startups there? Probably. And you know, there's not a ton of startup investment banks, but there are various fintechs and other things I want to chip away at parts of your business, and they can run perhaps faster, and they can be a little bit more liberal about what their employees are allowed to do, etc. do you feel like you have to keep a certain cadence of expanding the list of those executables that are, able to be run?
</details>

**马可·阿根蒂**: 所以，我认为，我会给你两个答案。首先，我想确保我回答了你的第一个问题，那就是我们没有使用 **Open Claw**。好的？好的。但 Open Claw 的一些特性实际上启发了我们构建**智能体平台**的方式。好的，今天的智能体因为 Open Claw 而实际上发生了变化。如果你分解 Open Claw，有三个非常重要的新特性，这是我自己的解释。我从来没有谈论过这个。有三个特点使 Open Claw 成为它。一个是它是一个**恒定的循环**。所以它基本上是你在信息理论中可以称为**观察者模式**的东西，它持续运行并观察。所以它是一个恒定的观察者，它持续运行。另一个是它可以**安排事件**，比如每天早上7点做这个，或者我，你知道，在个人生活中我们都有类似的东西，早上给我发送新闻等等。所以任务具有**调度能力**。第三个是你可以指示它**改变自己的行为**，因为它有这些文件 dot MD5 soul.md，所以你可以说：“嘿，我希望你永远不要使用这个词，或者请改变那个，或者改变你过滤新闻的方式”，所以它会自己编写软件来为你做事情，而你甚至看不到幕后发生了什么。所以我们没有让人们在他们的电脑上安装Open Claw，我们所做的是将其中一些特性融入到我们的**通用智能体平台**中，这样它做的事情就更类似于 Open Claw。所以这就是方法。你有点——你的第二个问题很有趣，因为如果你看问题背后的意思，你是在问我们是否在与其他人相比存在**速度劣势**？好的。我认为，我经常说，速度和**加速度**之间存在差异。速度几乎就像你有一个短跑。好的。但到某个时候你会撞墙，一堵安全墙，一堵可扩展性墙。会出现一个错误。你不知道你在做什么，迟早你会遇到这个问题。你会像，你知道，大多数飞机都是自动驾驶的。我有一个可以做一切的自动驾驶系统。所以理论上，你和我可以进入驾驶舱，在飞行的很长一段时间里，我们会感觉很好。对吗？我们会喝一些软饮料或茶。我们可能会看一些视频。我们会非常高兴。听起来很棒。激情是一个点。在飞行的某个时刻，会有一场风暴，自动驾驶会断开连接。你和我将会面面相觑，然后说：“哦，对了，那是飞行员。”

<details>
<summary>Original English</summary>

**Marco Argenti**: So, I think, so I'll give you two answers. So first, I want to make sure that I answer your first question, which is, we're not using open claw. Okay? Okay. But some of the properties of open core has actually having informed the the way we are building our agent platform. Okay, agents today because of Open Claw have actually changed. There are three very important new if you if you break down warp enclosures that are it is my own interpretation. I never I actually never even spoke about this. There are three characteristics that make open claw what it is. One is it's a constant loop. So it's basically what, you know, in information theory you can call an observer pattern is something that continues to run and observe. So there is that it's a constant observer. So it runs constantly. The other one is it can schedule events every 7 a.m. do this or I, you know, like in personal life we all have some something like that that sends me the news in the morning and all that. So there is a schedule, ability of tasks. The third one is you can instructed to kind of change its own behavior because it has this files dot MD5 soul.md, the way you so you can say things like hey, I would like you to never use this term or please change that or change the way you filter news because and so it kind of writes its own software to do things for you without you even, you know, seeing what's behind the scenes. And so instead of letting people, install open claw on their computers, what we do is we incorporate some of those characteristics into our genetic platform so that it does things that are more similar to open cloud. So that's that's the approach. You're kind of made that the your second question was interesting because basically if I read behind the questions, are you asking whether there is a sort of a velocity disadvantage with regards to, you know, us versus others? Okay. And I think at, you know, I often say, you know, that there is a difference between speed and velocity. Speed is almost like, you have a certain sprint. Okay. But then at some point you're going to hit the wall a security wall, a scalability wall. There's going to be a bug. You don't know what you're doing and there's going to first, sooner or later you're going to be hit by that. You will be like, you know, most airplanes are in auto. I have autopilot that can do everything. So theoretically, you and I could go in the cockpit and for a long time during the flight. We will feel pretty good about this. Right? We will drink, you know, some some soft drinks or your tea. We might maybe watch some videos. We will be very happy. It sounds great. The passion is one point. At one point. In time in the flight, there's going to be some storm, and there's going to be an autopilot disconnect. And you and I are gonna look at each other, are going to say, oh, right, it was the pilot.
</details>

**特蕾西·阿洛韦**: 我最近在一次飞行中，我告诉你，我要去**纽瓦克**。是的。我们盘旋了三次。我们试图降落。当时正在下暴风雨，他们一直没有降落。每个人都开始变得非常恼火，因为我们在空中呆了很长时间。然后空乘人员走过来，顺便说一句，没有提示，说我们有充足的燃油，所有人都卡住了。我们没有，这就像，这是一个问题。这是一个没有人有的答案。不，你需要什么？对不起。我就是不喜欢那样做。然后所有人都变得非常紧张。好的。顺便说一句，我们有充足的燃油。但你知道吗？我几乎担心你会说：那是一个飞行员吗？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Can I just say recently I was on a flight, I tell you this, and I was going to Newark. Oh, yeah. We circled three times. We tried to land. It was during a storm and they kept not landing. Everyone was like, starting to get pretty annoyed because we were up there for a while. And then the flight attendant comes on and says, unprompted, by the way, we have plenty of gas and everyone's stuck. We got no, it's like, this is a question. This is an answer that no one had. No. What do you need? I'm sorry. I just don't like to do that. Then everyone got really nervous. Okay. By the way, we have plenty of gas. But you know what? I was almost fearing that you would say. Is that a pilot?
</details>

**乔·魏森塔尔**: 不，不，我没有。然后我们确实降落在了**华盛顿特区**。好的。哦，你做到了？是的。从纽瓦克。是的。不，不，那不好。但这说得通。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: No, no, I wasn't. And then we did land in Washington, DC. Okay. Oh you did? Yeah. From Newark. Yeah. No, no, that's not good. But that makes sense.
</details>

**马可·阿根蒂**: 是的，是的。所以这就是我所说的**加速度**，它就像马拉松一样，是长时间保持一个方向的持续速度。是的。我认为随机化并不能真正获得加速度，你获得的是某种即时速度。所以我正在优化加速度。

<details>
<summary>Original English</summary>

**Marco Argenti**: Yeah, yeah. So so that's why I mean by velocity is really like, is like the marathon is, you know, sustain the speed for a long time in a certain direction. Yeah. I don't think by randomizing that you actually gain velocity, you gain an instant speed of some sort. And so I'm kind of optimizing for velocity.
</details>

**特蕾西·阿洛韦**: 但关于乔的观点，您是一家**受监管的银行**，对吧？所以在技术方面，您能做什么受到限制。我非常非常好奇您现在与**监管机构**的讨论是什么，因为很多监管机构对这个仍然很陌生。很多模型基本上都是**黑箱**。您如何说服他们，它们运行正常，它们输出了正确的结果，您理解它们实际是如何运作的？

<details>
<summary>Original English</summary>

**Tracy Alloway**: But related to Joe's point, though, you are a regulated bank. Right. And so there are restrictions on what you can do in terms of technology. I am very, very curious what your discussions with regulators are right now, because a lot of regulators, this is still pretty new to them. A lot of the models basically are black boxes. How do you convince them that, like they're running as they should, that they're spitting out the correct output, that you understand how they're actually functioning?
</details>

### AI与监管合规性

**马可·阿根蒂**: 所以这不是银行第一次使用**神经网络**。好的。这些只是更大规模的神经网络。但我们使用神经网络已经超过十年了。所以每家银行都经历过解释神经网络没有完美的**可解释性**的过程。因此，你需要改变围绕它们的**控制系统**。你需要审视它们实际能做什么操作。然后你限制这些操作。好的。然后有一个叫做**模型风险管理**的功能，这是一个非常标准化的功能，在每家银行中，对于每个神经网络，你都需要有一个**清单**，你需要有一个**风险分层**，并且你需要围绕它设置控制。所以这并不是什么新鲜事物，更像是一种演变，现在你有更快速、更强大的东西。但基本的模式和与监管机构的基本讨论是相同的，那就是你是否对应用程序的**风险分层**进行了分类？对。然后你设置了哪些控制措施？你是否设置了**人工监督**和**人机协作（human in the loop）**？所以例如，对于代码。我们不允许人工智能自动批准错误的代码。好的。它们能做的就是发布所谓的**拉取请求（pull request）**或**合并请求（merge request）**，就像开发人员会做的那样。我们有点像有一个**零信任模型**，因为我们不认为一个初级开发人员会比人工智能更少出错，对吧？所以我们有几个控制措施。例如，必须有一个比你更高级的人类来实际查看代码。然后进行认证和批准，然后在那之后，在它投入生产之前，它会进入一个叫做**CI/CD**或**持续集成，持续部署管道**的东西。当它通过构建阶段等等时，会注入大量的检查。有**安全检查**，有**技术风险检查**。所以我认为最终你不会损失太多速度，或者根本不会。你只需要在这些事情上投入更多。这就是事实。而且我认为监管机构，如果你把他们带回一个熟悉的领域，并且你在你知道的事情上和你不知道的事情上都保持诚实，对于你不知道的事情，你就会设置更高的保护措施。我认为这样的对话通常是非常积极的。

<details>
<summary>Original English</summary>

**Marco Argenti**: So this is not the first time that banks use neural networks, okay. These are just much larger neural networks. But we've been using neural networks for like a decade plus. And so every bank has already gone through, the motions of explaining that the neural networks don't have perfect explainability. Therefore, you need to change the control system around them. You need to look at what actions can they actually do. And then you limit the actions, okay. And then you there is a function called the like model risk management, which is a very standardized, you know, function within every bank that for each of those neural networks, you need to have, an inventory, you need to have a risk tiering, and you need to put controls around that. So it is, not really that much of a new thing is more of an evolution, where now you have things that are much faster and much more powerful. But the basic pattern and the basic discussion with the regulators is kind of the same, which is are you classifying the risk tiering of the application? Right. And then which controls are you putting and are you putting human supervision and human in the loop. So for example, for code. We don't allow AI to auto approve the wrong code. Okay. They all they can do is publish what's called a pull request or merge request the same way as, a developer would do. And we kind of have a sort of a zero trust model there because we don't assume that, maybe a junior developer is going to be less, more bug free that than an AI, right? And so we have several controls in place. For example, there isn't to be there needs to be a human that's more senior than you that actually looks at the code. And then certifies and approves, and then after that, before it goes to production, it goes into something that is called Cicd or, you know, continuous integration, continuous deployment pipeline, where when it goes through the build phase, etc., there is a lot of checks that are injected into that. There are security checks, there are tech risk checks. So I don't think at the end of the day you really lose too much velocity or at all. You just need to invest more in those kind of things. And that's really what. And the regulators, I think if you bring them back into sort of a familiar territory and you're also honest on things that, you know and things that you don't know, and for the things that you don't know, you kind of put to higher protections. I think the conversation is generally very positive.
</details>

**乔·魏森塔尔**: 您知道，我们几周前录制了一集，但还没有发布。我不知道那一集或这一集确切的发布时间。我们采访了**格林希尔（Greenhill）**的前首席执行官**斯科特·博格（Scott Borg）**，这是一家精品投资银行。我们进行那次对话的部分原因是，我们想知道，如果人工智能有一天会颠覆我们所知的银行业，那么我们所知的银行业是什么样的。所以我们谈论了**投资银行**的历史。但他谈到的一点是，银行的一个巨大优势是这种**信息不对称**，他们对自己的行业等等比客户了解得更多。这在当时是有利可图的。现在，回到您对第一个问题的回答，您说：“好的，客户可能会打电话给高盛。”他们说：“**霍尔木兹海峡**的封锁对这个投资组合有什么影响？”我正要问这个问题。是的，我想我能做到。我的意思是，恕我直言，我敢肯定您的平台比我更好一点，但我想我能达到90%的程度。我敢打赌，只要有一点数据，我就能构建一个篮子，说：“我想要一个**氦短缺篮子**，如果我认为氦短缺会变得更糟，我会做空哪些公司？”我可以用交易台的方式重新构建一个篮子。您认为从长远来看，人工智能会侵蚀银行的某种结构性盈利来源吗？您担心这个问题吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: You know, we have an episode that we recorded several weeks ago that we still haven't released. I don't know exactly the timing of that one or this one. We interviewed, Scott Borg, the former CEO of Greenhill, the boutique investment bank. And part of the reason we had that conversation was because we want to know, like, if I is going to someday disrupt banking as we know, like what was banking as we know it. So we talked about the history of investment banking. But one of the things that he talked about was that a big advantage that the banks had was this sort of information asymmetry that they would know a lot more about their industries and so forth than their clients. And this was profitable. Now, going back to your answer, the very first question, you're like, okay, a client might call, Goldman. And they said, what is the Strait of Hormuz closure mean for this portfolio shock, etc.. I was going to ask this exact question. Yeah, I. Kind of think I could do that. I think I could you I mean, no offense, I'm sure your platform is a little bit better than like, but I think I could like get 90% of the way there. And I bet I could, like with a little bit of data, build a basket that says, I want, you know, helium shortage basket, which, which companies would I short if I think the helium shortage is going to get worse, I could rebuild a basket the way a trading desk would. Do you think long term, like the air erodes a certain structural source of profitability for banks? And you worry about that?
</details>

### 银行的“额外10%”与信息优势

**马可·阿根蒂**: 我认为你可以达到90%。但我认为客户真正为我们支付的是那**额外的10%**。好的。所以我想这就是答案。

<details>
<summary>Original English</summary>

**Marco Argenti**: I think you can get to the 90%. But I think clients are really paying us for that extra 10%. Okay. So I think that's the answer.
</details>

**特蕾西·阿洛韦**: 在这种情况下，额外的10%是什么？是您的模型稍微更好一些，还是我们能访问到？

<details>
<summary>Original English</summary>

**Tracy Alloway**: So what is the extra 10% in that context? Is it you model for slightly better or is it also the do we. Have access to you know,
</details>

**马可·阿根蒂**: 我们购买了大量数据，这些数据非常昂贵，数量庞大，并且非常实时。所以我们有一些**数据优势**。我们在多种资产类别中运作。所以我们看到了**交易方面**。我们看到了**资产管理方面**。所以我们有一种资产之间的**相关性优势**，因为我们看到了这些，因为通常利率会变动，你知道，利率会影响收益率。你知道，所有这些指标之间都存在相关性。所以还有另一个优势。我们拥有**全球优势**。我们在100多个国家和地区都有人员。这些人拥有人脉，信息通过这些渠道传播。而且，你知道，我们通常处理非常复杂的**投资组合**。所以这不像你我可能只持有三四五只股票。这是一个非常复杂的、涉及多年的资产，拥有复杂的**产品**，如**掉期（swaps）**或**掉期通道（swap channels）**或**奇异产品（exotic products）**等等。所以这才是那10%，你知道，我们的客户真正看重的那10%，也是我们真正需要达到的。就像，归根结底，特蕾西，如果你看看**一级方程式赛车**。好的，每一圈的时间差，你知道，梅赛德斯和，随便你最喜欢的最后一名车队之间的，有时是两分钟中的一秒。这就是，你知道，获得一亿美元的年度赞助还是获得一万美元赞助的区别。所以对于**高端客户**来说，这10%才是真正的价值所在。这才是人们为我们支付费用的原因。

<details>
<summary>Original English</summary>

**Marco Argenti**: We buy a lot of data that, you know, it's very expensive and it's a massive quantities and it's very up to date and very real time. So we have a little bit of a data advantage. We operate across multiple asset classes. So we see the trading side. We see the asset management side. So we have a sort of a correlation between assets advantage that we see those because generally rates move you know interest rates can move yields that can move. You know there is a correlation between all those indicators. So there is another advantage. We have a global advantage. We have people on the ground in, you know, 100 plus countries. And these people have relationships and information travels through those channels. And also, you know, like we generally deal with very complex portfolios. So this is not you and I may be having three stocks or 4 or 5. This is a like very complex, multi-year assets up with complex products like swaps or swap channels or exotic products, etc., etc.. And so that's really the 10%, that, you know, the clients that we have, you know, really value and where we really need to get, it's like at the end of the day, Lisa, if you look at, look at formula one, okay, the difference per time, a particular pair of per lap, between, you know, the, the, Mercedes, and, take, you know, your favorite last team. You know, it's sometimes one second out of the two me out of two minutes. And that is the difference between, you know, getting a $100 million a year sponsorship or a $10,000 sponsorship. So for for sophisticated clients, that 10% is really what the money is. And that's really what people are paying us for.
</details>

**特蕾西·阿洛韦**: 所以实际上您提到了高盛所有不同的业务。有很多，比如**资产管理**、**银行**、**交易**。其中很多业务在某些方面是不应该相互交流的。那么当涉及到数据时，是否存在**数据泄露**问题？例如，您可能有一个内部模型，像 GSI 这样，它正在从公司不同方面提取数据，而这可能不应该发生。鉴于模型的复杂性，可能很难判断。这是您必须关注的问题吗？

<details>
<summary>Original English</summary>

**Tracy Alloway**: So actually you mentioned all the different businesses at Goldman. And there are a bunch of them like asset management there's banking, there's trading. A lot of those businesses aren't supposed to talk to each other in various ways. And so when it comes to the data, is there like a data leakage issue where you might have a model that's, you know, in-house, like GSI, that's pulling data from different sides of the company in ways that, you know, maybe it shouldn't be. Maybe it's really hard to tell given the complexity of the model. Is that something you have to pay attention to?
</details>

**马可·阿根蒂**: 绝对如此。所以，我们有**信息隔离墙（info barriers）**的概念。好的。信息隔离墙在整个系统中强制执行。好的。而且它们与您的ID或帐户关联。好的。所以如果我在私有方，我只能看到某些信息。如果我在公共方，我只能看到某些信息。我甚至不能知道另一方的信息，我无法访问文件、C盘、文件夹。什么都没有。每个AI或每个智能体或每个应用程序。这就是**去中心化平台**的优点。它需要获得一个ID或一个徽章，这个徽章与任何应用程序或任何计算机的信息隔离墙完全相同。所以这些是在源头强制执行的。所以即使是相同类型的模型，但该模型的特定用途，该模型的特定会话，它需要获得一张票或一个徽章，那个徽章或那些密钥只会带他们到特定的地方。所以这是我们花了将近两年时间才构建GSI平台的原因之一。这些都是你不能对这些事情掉以轻心的原因。这个东西不是由一些随意编写代码的人构建的，因为你需要担心网络安全。你需要担心信息隔离墙。所以你需要担心所有这些。所以当我说，你知道，有些地方你可以利用并进行关联，但有些地方你绝对不能。这种规范是基础性的，因为，你知道，你需要做好准备，你不能对这些事情掉以轻心。

<details>
<summary>Original English</summary>

**Marco Argenti**: Absolutely. So, we have the concept of info barriers, okay. And the info barriers are, are enforced, throughout the entire system. Okay. And, they're linked, to your ID or your account. Okay. So if I'm on the private side, I can only see certain information. If I am on a public side, I can only see certain information. And I cannot even know about the information on the other side, I can I don't have access to the files, to the C, to the folders. Nothing. Each I or each agent or each application. That's the beauty of decentralized platform. Needs to get an ID or a badge, and that badge is attached to the exact same info barrier says any application or any computers. And so these are enforced basically at the source. So even if it is the same, type of model, but that particular use of the model, that particular session or the model that needs to get a ticket or a badge and that badge or those keys, just take them to a certain place. And so this is one of this been, you know, it took us almost two years to build the, GSI platform. These are this back to the reason why you can't be casual about these things. This thing is not being built by some random vibe coders because you need to worry about cyber. You need to worry about the info barrier. So you need to worry about all that. And so when I talk about, you know, there are places where you can leverage and do correlations, but there are others where you absolutely cannot. And this scandal that is foundational to the fact that, you know, you need to have, you need to be ready for a, you can't be casual about that.
</details>

**特蕾西·阿洛韦**: 所以我理解您的观点，您在职业生涯中从未见过哪种技术真正减少了对软件工程师的需求，而且软件工程师的工作性质正在发生变化，也许变得更高级。撇开纯粹的**人员编制**问题不谈，人工智能现在是否正在改变您所寻找的人才类型，或者改变了任何软件、技术或其他方面的人才性质？

<details>
<summary>Original English</summary>

**Tracy Alloway**: So I take your point that there's never been a technology that you've seen in your career that has actually reduce the need for software engineers, and that the nature of the job of software engineers is changing, maybe gets more high level. And whatever. Setting aside the pure head level of headcount question is AI changing right now across anything software, technology or otherwise, the types of person you're looking for or changing something about the nature of the type of talent, your person?
</details>

### AI时代下开发者所需的新技能

**马可·阿根蒂**: 是的，绝对如此。好问题。所以，我认为在当今时代，几乎没有人是真正的**个人贡献者**了。因为当你与**智能体**一起工作时，你至少需要具备三个基本特征。第一，你需要能够**解释**你想要完成什么。好的。第二，你需要能够**委派工作**。你猜怎么着？因为你会有多个智能体。一个专门负责，例如，DCF计算。另一个专门负责研究。所以你需要能够将工作分解成可以某种方式并行执行的块。然后第三，你需要具备**监督**的能力。你需要实际查看输出并说：“好的，我对这个没问题”，或者“回去修改”。事实证明，这三件事——解释、委派和监督——是经理的根本职责之一。经理必须具备这三点，否则他们就无法管理团队。所以人工智能正在让每个人都或多或少地成为一名经理。这些就是我们实际正在寻找的技能，寻找那些知道他们将拥有对工具的代理权的人，这些工具在某个时候会比他们自己更熟练、更专业。所以最重要的是**构思**、解释、委派的能力，然后真正知道什么才是好的。我认为这是一个巨大的变化。我认为并不是每个人都会真正快速地经历这个过程。我认为我们正在结合培训。还有结合让他们接触其他人。例如，拥有**前沿部署工程师**的优势之一还在于，餐桌旁会发生一些文化冲突。所以人们的思维方式真的非常不同。这会把人们推出他们的舒适区。这就是为什么我说，你知道，正在发生一点**蜕变（metamorphosis）**。这不仅仅是关于效率，更是关于思考我的工作是否会保持不变，现在它确实改变了很多。

<details>
<summary>Original English</summary>

**Marco Argenti**: Yeah, absolutely. Great question. So, I think, in this day and age, almost nobody is an individual contributor really. Because when you're working with agents, you need to have, at least three fundamental characteristics. One is you need to be able to explain what you want to get done. Okay. The second one is, you need to be able to delegate work. Guess what? Because you're going to have multiple agents. One is specialized, for example, in doing DCF calculations. And one is specialized in doing research. So you need to be able to break down the work into chunks that can be, executed in parallel in some way. And then three, you need to have the ability to supervise. You need to actually look at the output and say, okay, I'm good with this or go back. It turns out that those three things I explain, delegate and supervise are kind of the 1 or 1 of managers. Managers need to have those three, otherwise they can't manage a team. And so I is kind of turning everybody a little bit into a manager. And those are kind of the skills that we are actually looking for, for people that, they know that they're going to have agency on, tools that at some point are going to be even more proficient and specialized than they are. And so the most important thing is really the ability to ideate, to explain, to delegate, and then to really know what good looks like. And I think that is a big change. And I don't think everybody is going to actually rapidly go through that. And I think we're doing a combination of, training. There is a combination of, exposing them to, you know, other people. Like one of the advantages of having forward deployment engineers is also that there is a little bit of clash of culture that is happening around the table. And so people think really, really differently. And that pushes people outside their comfort zone. That's why I'm saying that, you know, there is a little bit of a metamorphosis happening. There is not just about efficiency is really thinking about is my job going to stay the same now is actually changing quite a bit.
</details>

**乔·魏森塔尔**: 我在思考如何提出这个问题。但现在高盛开发人员的**工作与生活平衡**是怎样的？因为您对工作可能发生的变化存在这种**生存焦虑**。同时，您拥有能够提高生产力的人工智能工具，而且现在还发生了一件事，我觉得乔，您可能比我更了解，我觉得很多**凭感觉写代码（vibe coders）**的人，就像上瘾一样。是的，对吧？这就像您在按老虎机的按钮，您在与**Claude**互动，并且一次又一次地看到它吐出什么，直到您获得大奖。所以，我听说有开发人员因为现在用这些工具做得太多而感到**倦怠**，他们只是不停地按那个按钮。最近在**Odd Lot**的Discord上，就此进行了很好的讨论。一些**半导体工程师**觉得这份工作变得不那么令人满意了，因为它只是，我想这有点像您所说的**老虎机**。是的。就像：“哦，您要点击提示。好的。这是很棒的输出。”然后他们觉得工作不那么令人满意了，而不是真正地编写代码。所以，是的。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So I'm thinking how to frame this question. But what's work life balance like now for a developer at Goldman? Because you have this existential existential angst about jobs potentially changing. At the same time, you have AI tools that enable more productivity, and you also have this thing happening where I feel like, Joe, maybe you know more about this than I do, but I feel like a lot of vibe coders, like like it's addictive. Yeah, right. It's like you're you're pressing the button of a slot machine, you're interacting with Claude and you're seeing what it spits back out over and over and over again until you get that big win. And so I've heard people talk about burnout among developers who are just doing so much with this right now that they're just hitting that button over and over. And it was a good discussion in the odd lot discord recently about exactly this. Some engineers and semiconductors feeling that the job has become less satisfying because it just all and I think is sort of what you're getting at the sort of slot machine. Yeah. Where it's like, oh, you're going to like hit the prompt. Okay. This is the great output. And then it's like they field of work as like less satisfying and stuff like that than actually like writing code. So yeah.
</details>

### AI与开发者倦怠、创新与未来

**马可·阿根蒂**: 我的意思是，听着，我喜欢我比大多数工程师稍微年长一点这个事实。其次，我第一次看到人们使用**Excel**，我第一次看到人们使用**Python**。哦，天哪，我不需要知道Java了。然后孩子们开始编码，整个编码运动兴起。然后你开始创建你的应用程序。我第一次看到人们使用移动设备，你知道，移动应用程序。所以我认为这有点是因为它是新事物，说实话。你知道，我认为这其中有一点点，但也有很多新奇之处。然后我看到人们使用这些工具几年后，他们对待它们更像：“好吧，这是一个专业工具。”我将用它来完成我真正需要的事情，而不是仅仅尝试发现。我看到的一件事是，也许是因为这个，但也因为你能从中获得什么，所以存在一种奖励循环，它相当快。是的。人们非常兴奋，实际上。有一种职业的乐趣正在迸发出来，仿佛工程师们觉得这份工作又焕然一新了，因为很多工程师有时在两三年内看到了相同的模式。是的。所以这是一种我观察到的现象。也存在很多**同侪压力**。存在很多**错失恐惧症（FOMO）**。所以人们不是，你知道，不再是我努力推着车上坡，而是人们在看他们的同伴，他们在看：“哦，天哪，你是怎么做到的？”所以它正在相当横向地传播，这真的很好看。所以到目前为止，我不得不说这是一个积极的，积极的变化。另外一件事是，你知道，你谈到倦怠。我看到很多人感到**疲劳**。我不想谈论倦怠，但当有很多重复性任务时，他们会感到疲劳，特别是对于开发人员。举个例子。假设你从某个版本的 **Java 库**或 **Spring Boot** 升级到另一个版本。然后突然你编译，然后你重建，然后你得到所有这些错误，说你需要升级。说实话，升级库并不是最有趣的工作。如果你需要做100次，或者有人说：“顺便说一句，伙计们，我们有了新的设计，新的标志，新的颜色，把它应用到200个网站上。”前十个可能很有趣，然后就变成了苦差事。所以我认为摆脱这些，让他们更多地关注计划，例如。所以现在，让我们为复杂的应用程序制定一个云迁移计划。他们可能会花费70%的时间与一组非常强大的人工智能反复讨论，以真正把计划做好。他们感觉自己更高了一点。而机械部分，你知道，留给了机器。这就像，我的意思是，听着，我开始开发的时候，我真的在翻动开关。好的。然后按下一个按钮，它会把寄存器向上移动一个。然后出现了像C语言这样的语言。哦，天哪，现在我不需要再翻动开关了，但你猜怎么着？我需要做**内存管理**。我需要使用**指针**。我的意思是，有很多繁重的工作。哦，我有一个**内存泄漏**。我将花费一周时间才能最终识别出来。然后，你知道，出现了**Java**或**垃圾回收**。我不再需要担心内存泄漏了。太棒了。然后出现了**Python**，它摆脱了所有这些限制。更容易，你知道，实现**类型自由**等等。所以每次你都在不断提高标准，很多机械部分都消失了。我认为这就像在两年内实现了十年的飞跃。但我认为总体而言，没有人真正喜欢那种辛苦和机械的工作。我实际上很高兴人们会花更多时间，也许最初是因为兴奋，但我认为我正在享受而不是那些他们害怕的事情。

<details>
<summary>Original English</summary>

**Marco Argenti**: I mean listen again I this work, I love the fact that I'm a little bit, older than most to hear an engineer. Second, I've seen that the first time people had the Excel and I've sat for the, you know, the first time people had, Python. Oh, my God, I don't need to know Java. And then the kids start to code and there is this whole coding movement. And then you get the you start creating your applications. I've seen the first time people have mobile stuff and, you know, mobile apps. And so I think a little bit of that is because it's new, to be perfectly honest, you know, and I think there's there is a little bit of that, but there is a little a lot of novelty to that. And then I've seen that people have been using those tools, for a couple of years. They're taking them a little bit more like, okay, it's professionals tool. And I'm going to use it for what I actually need rather than just trying to discover. One thing that I've seen is that because maybe of that, but also because of, what you can get there is a sort of a in a way, reward cycle that is pretty quick. Yeah. People are very excited, actually. There's, there's some sort of a joy of the profession that is actually coming out as if engineers were feeling like this job is new again, because a lot of engineers have seen the same pattern, sometimes for 2 or 3 decades. Yeah. So that has been, something that I observed. There is also a lot of peer pressure. There is a lot of fear of missing out. And so people are rather than, you know, is no longer like, me trying to push the car uphill is more people are actually looking at their peers and they're looking at, oh my God, how could you do that? And so it's kind of spreading horizontally quite a bit, which is which is really nice to, to see. And so, so far I have to say that has been positive, positive change. And also one other thing that, you know, you're talking about burnout. I see that a lot of people get fatigue. I wouldn't want to talk about burnout, but they get fatigue when, you know, there are a lot of repetitive tasks, especially for a developer. Here's an example. Let's say you go from, you know, a version of, a Java library or spring boot. To another version. And then all of a sudden you compile and you get to rebuild and you get all these errors that says you need to upgrade. Honestly, upgrading libraries is not the most fun job. And if you need to do it 100 times, or is like someone says, by the way, guys, we have this new design, design, a new logo, new colors, implement it on like 200 websites. It might be fun. The first ten and then it becomes a drag. And so I think taking that away kind of in making them, they focus more and more on the plan, for example. And so right now let's do a migration plan to the cloud of a complex application. They spend maybe 70% of their time going back and forth with a very powerful set of eyes to really get the plan right. They feel a little bit more elevated. And the mechanical part, it's kind of, you know, left to, to, to to the machine the same way. I mean, listen, I started developing when I was literally flipping switches, okay. And then pressing a button, which would move the register up one and then came, you know, some languages, like, see, oh, my God, now, I don't have to flip switches anymore, but the guess what? I need to do? Memory management. I need to do pointers. I mean, there's a lot of heavy lifting. Oh, I have a memory leak. I'm going to spend a week before I actually finally identify that. And then, you know, it comes to Java or garbage collection. I don't have to worry about memory leaks anymore. Fantastic. And then comes Python, which is all all that rigidity. So much easier to you know, be type, free and so forth. And so every time you kind of keep raising the bar and a lot of the candle mechanics kind of goes away. I think this has been like a ten year jump, in, you know, in, in a matter of two years. But I think overall, nobody really likes to, to have that toil and that mechanical work. And I'm actually quite happy that people are going to spend that maybe initially more time because they're excited. But I don't think that I'm enjoying rather than things that they just, they dread.
</details>

**特蕾西·阿洛韦**: 好的。马可，我想我们一年半后得再请您上播客了，我想是这样。在讨论中。是的。三个月。没错。在缩短的时间线上。非常感谢您。非常感谢您的回归。

<details>
<summary>Original English</summary>

**Tracy Alloway**: All right. Well, market will have to have you back on the podcast in another year and a half, I guess in discussions. Yeah. Three months. That's right. To go on the reduced air timeline. Thank you so much. Thank you so much for coming back.
</details>

**马可·阿根蒂**: 谢谢你们两位。谢谢。

<details>
<summary>Original English</summary>

**Marco Argenti**: Thank you both of you. Thank you.
</details>

**乔·魏森塔尔**: 谢谢邀请我。非常感谢。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Thanks for having me. Thank you so much.
</details>

### 总结与展望

**特蕾西·阿洛韦**: 谢谢，谢谢，乔，很高兴能追上。是的。我认为非常有趣的一点是他关于与**监管机构**讨论的观点，以及将其描述为与之前的技术进步非常相似，您不一定需要精确解释模型如何得出某些结论。是的，但您更关注实际限制风险并确保它们处于正确的风险评估类别中。现在，我认为这非常有趣，只是其中一些技术，你知道的，**黑箱**。是的，大型语言模型不是第一个黑箱。我的意思是，我们之前在金融领域已经谈论了多年的**黑箱交易**。所以这种想法，就像，“好的，这些事情正在发生，我们可以清楚地表达它们等等。”就像金融业这不是第一次经历类似的事情，这真的很有趣。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Thank thank so Joe, that was great to catch up. Yeah. One thing I thought was really interesting was his point about the discussions with the regulators and framing it like very similar to previous technological advances, where you're not necessarily explaining exactly how the models are coming to certain conclusions. Yeah, but you're more focused on actually limiting the risks and making sure that they're in the right bucket for risk assessment. Now, I thought that was really interesting, just that some of these technologies, the, you know, the black box. Yeah, the limbs are not the first black box. I mean, we've actually been talking about black box trading for years and finance before. So the idea of like, okay, there are these things that are happening, we can articulate them and whatever. Like it's not the first rodeo for finance is really interesting.
</details>

**乔·魏森塔尔**: 我还认为关于**代币预算**和**分配**的整个对话很有趣。这种想法是：“好的，这里有一堆不同的模型，理论上每个人都想要性能最好的模型。但你如何找到这种优化，在价格上获得最佳性能？”这听起来像一个非常有趣的工程问题。是的，我实际上很想在这个问题上做更多。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: I'm also, you know, I thought the whole conversation about, token budgets and allocations are interesting. The idea of like, okay, part of the job here is you have a bunch of different models. Everyone, in theory wants the most performant model. But how do you find that optimization where you get the best performance relative to price? It sounds like a pretty interesting like engineering problem. Yeah, I would actually love to do more on that question.
</details>

**特蕾西·阿洛韦**: 我也是，因为它是一个如此有趣的问题，关于**激励**，对吧？以及如何实际优先考虑每个项目，如何构成一个好的产出，以及何时为了比如**十倍少的代币预算**而牺牲一点质量，或者随便什么，就像你说的，这将是非常有趣的，谈论这个问题具体是如何在公司内部解决的。

<details>
<summary>Original English</summary>

**Tracy Alloway**: I would too, because it's such an interesting like a question of incentives. Right? And like how does how how do you actually like prioritize how each. Project, like what constitutes a good output and how when do you sacrifice a little bit of quality for like ten x less, token budget or whatever, like you said this would be, it would be very interesting to talk about how that problem specifically gets solved inside of.
</details>

**乔·魏森塔尔**: 一个订单的**代币经济学**。是的。**效率优化**。是的。我们很快会再请马可回来谈论人工智能正在做的所有新事情。但现在，我们就到此为止吧？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: An order token economics. Yeah. Efficiency optimization. Yeah. Well, we'll have Marco back on very soon to talk about all the new things that AI is doing. But for now, shall we leave it there?
</details>

**特蕾西·阿洛韦**: 就到这儿吧。这是**奇思妙想播客**的又一集。我是**特蕾西·阿洛韦**。您可以在@tracyalloway关注我。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Let's leave it there. This has been another episode of the Odd Lots podcast. I'm Tracy Alloway. You can follow me @tracyalloway
</details>

**乔·魏森塔尔**: 我是**乔·魏森塔尔**。您可以在@thestalwart关注我。关注我们的制作人**卡门·罗德里格斯（Carmen Rodriguez）**@carmenarmen，**达希尔·贝内特（Dashiel Bennett）**@dashbot和**凯尔·布鲁克斯（Cale Brooks）**@calebrooks。如果您想要更多**Odd Lots**内容，您绝对应该查看我们的每日时事通讯。您可以在bloomberg.com/oddlots找到。您可以在我们的Discord频道discord.gg/oddlots全天候24小时讨论所有这些话题。如果您喜欢这次对话，请留下评论或点赞视频。或者更好的是，订阅！感谢观看。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And I’m Joe Weisenthal You can follow me @thestalwart Follow our producers Carmen Rodriguez @carmenarmen, Dashiel Bennett @dashbot and Cale Brooks @calebrooks And if you want more Odd Lots content, you should definitely check out our daily newsletter. You can find that@bloomberg.com/oddlots And you can chat about all of these topics 24-7 in our discord, discord.gg/oddlots And if you enjoyed this conversation, then please leave a comment or like the video. Or better yet, subscribe! Thanks for watching.
</details>