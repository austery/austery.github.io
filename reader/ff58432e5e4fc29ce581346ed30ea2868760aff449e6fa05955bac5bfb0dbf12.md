---
author: The MAD Podcast with Matt Turck
date: '2026-05-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DhD1zZ8w8Mw
speaker: The MAD Podcast with Matt Turck
tags:
  - reinforcement-learning
  - post-training
  - ai-reliability
  - test-time-scaling
  - continual-learning
title: OpenAI 训练专家访谈：GPT 5.5 进化论、强化学习与 AI 进化的阶跃函数
summary: OpenAI 后训练前沿团队负责人 Yann Dubois 深入解析 GPT 5.5 的核心改进。访谈探讨了 AI 进步为何呈现阶跃式感知、强化学习如何从单纯的竞赛模型转向处理现实世界的复杂数据、效率优化路径，以及为何持续学习仍是尚未解决的重大挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Yann Dubois
  - Matt Turk
companies_orgs:
  - OpenAI
  - Stanford University
products_models:
  - GPT 5.5
  - GPT-5
  - O3
  - Alpaca
  - Claude Mythos
media_books: []
status: evergreen
---
### 可靠性阈值的跨越

**Yann Dubois**: 你需要达到这种水平的**可靠性**，才能让这些 AI 工具真正变得非常有用。我认为我们可能在去年 12 月刚刚跨过了那个门槛，至少在 **OpenAI** 是这样。现在我们可以信任这些模型来完成我们正在做的很多工作。过去的几个月进展非常顺利，我们从关注竞赛表现转变为对用户的实用性，这就是我们现在的感受。我认为大多数时候，瓶颈在于**最后的一公里**。在不同的垂直领域，这最后一公里总会有很大的空间，我会高度鼓励人们继续在这方面努力。

<details>
<summary>Original English</summary>

**Yann Dubois**: You need to reach this level of reliability to really make any of these AI tools very useful and I think we just crossed that probably December last year at least at OpenAI now we can trust these models to do a lot of the work that we are doing the last few months have been pretty well we moved from like competitions to uh usefulness to users and that's what we are feeling right now I think most of the time the BIC is the the last mile there will always be a lot of space left for this last mile in different verticals and I would highly encourage people to continue working on that.

</details>

**Matt Turk**: 大家好，我是 **Matt Turk**。欢迎来到 Mad Podcast。我今天的嘉宾是 **Yann Dubois**，他在 OpenAI 共同领导**后训练前沿团队**（post-training frontiers team）。最近发布的 **GPT 5.5** 是 AI 领域的又一个重大里程碑，Yann 的团队协助构建了它，此外还参与了 OpenAI 之前的顶级推理模型，包括 **O3** 和 **GPT-5 Thinking**。在加入 OpenAI 之前，Yann 曾在**斯坦福大学**（Stanford）参与共同创作了 **Stanford Alpaca**，这是一个启动了现代后训练研究社区的里程碑式项目。在这次对话中，我们将深入探讨 GPT 5.5 究竟有哪些新变化，为什么**强化学习**（RL）正在从数学和编程竞赛转向复杂的现实世界工作，为什么 AI 的进步感觉像是一个突然的阶跃函数，以及为什么在 **ChatGPT** 问世三年后，**持续学习**（continual learning）仍然是 AI 领域尚未解决的大问题之一。请欣赏与 Yann Dubois 的精彩对话。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome to the Mad Podcast. My guest today is Yan Dubois who co-leads the post-training frontiers team at OpenAI. The recent release of GBT 5.5 was yet another major milestone in AI and Jan's team helped build it alongside OpenAI's prior top reasoning models including 03 and GBD5 thinking. Before OpenAI, Yan was at Stanford where he co-authored Stanford Alpaca, the landmark project that kicked off much of the modern post-raining research community. In this conversation, we go deep on what's actually new in GBD 5.5, why reinforcement learning is moving from math and coding competitions into messy real world work, why AI progress can feel like a sudden step function, and why continual learning remains one of the big unsolved problems in AI 3 years after Jet GPT. Please enjoy this fantastic conversation with Yan Dubois.

</details>

### GPT 5.5：从实验室到现实世界的跃迁

**Matt Turk**: 嘿 Yann，欢迎。

<details>
<summary>Original English</summary>

**Matt Turk**: Hey Yan, welcome.

</details>

**Yann Dubois**: 嗨 Matt，谢谢邀请我。

<details>
<summary>Original English</summary>

**Yann Dubois**: Hi Matt, thanks for having me.

</details>

**Matt Turk**: 在 **Frontier AI** 的世界里，随着 GPT 5.5 和 **Claude Mythos** 预览版的发布，过去几周又是一段疯狂的时光。感觉我们似乎又解锁了一个进步的**阶跃函数**，特别是在网络安全和**智能体编程**（agent coding）方面。从你的角度来看，思考这一点的最佳方式是什么？事情是在加速吗？到底发生了什么？

<details>
<summary>Original English</summary>

**Matt Turk**: It's been another wild uh last few weeks in the world of Frontier AI with the release of GPD 5.5 of Claude Mythos preview. So it feels like uh we have unlocked yet another step function in progress particularly in cyber security agent coding. What's the best way to think about this from your perspective? Are things accelerating? What is happening?

</details>

**Yann Dubois**: 是的，过去几个月确实非常疯狂。在公司内部，我们也确实感受到了这一点。我认为任何从事编程工作的人现在都能真切地感受到。我认为这主要归结为三个原因。第一点是，尽管在我看来进步实际上是相当连续的，但你需要达到某种**可靠性**水平，才能让这些 AI 工具真正变得非常有用。我认为我们可能在去年 12 月刚刚在 OpenAI 跨过了那个阈值——现在我们可以信任这些模型来完成很多我们正在做的工作。所以它给人的感觉像是一个阶跃函数，尽管从能力上看，它实际上是相当连续的。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yeah. Uh the last few months have been pretty wild. Um internally we also really feel it. Uh and I think anyone who's working with uh anyone who's work who's coding basically is really feeling it right now. Um I think that's really because of three reasons. Uh the first one is even though the in my mind everything the progress is actually pretty continuous you need to reach this level of reliability to really uh make any of these AI tools very useful and I think we just crossed that probably December last year at least at openi that's why I thought we really crossed that threshold uh where now we can trust these models to do a lot of the work that we are doing so it feels like a stem function even though I actually in terms of capability it's like it's pretty continuous.

</details>

**Yann Dubois**: 第二个原因是，一旦你开始拥有真正优秀的模型，你就会自我加速。特别是在编程方面，因为我们在内部都写代码，你会通过让这些模型来训练其他模型，以及构建我们作为研究人员工作所需的工具来加速自己。我认为所有这些加速意味着我们看到过去几个月的进展越来越快。第三件事是，去年我们真的在这些**推理模型**的基础上做了很多工作，在大力推进**强化学习**。最初当我们有 **O1**、**O1 Preview** 甚至是 O3 时，这些模型仍然是针对所谓的**可验证奖励**（verifiable rewards）进行优化的——这些任务中我们能够获得标准答案（ground truth），并且很容易测试你是否正确，比如数学问题或编程竞赛。我们现在意识到的是，我们能够利用为这些可验证奖励案例构建的许多工具，并将它们更广泛地应用于现实生活中的强化学习案例。我认为这就是为什么我们现在能真切地感受到这一点，特别是在现实世界的编程中，而不是仅限于竞赛。我们从竞赛转向了对用户的实用性，这就是我们现在的感受。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um so that's the first thing. The second the second reason is um once you start having models that are really good you accelerate yourself. Um especially in terms of coding given that we all code internally uh you you accelerate yourself both for having these models like train the other models but also like build like the tooling that we need as researchers to like do our job and and all this acceleration I think means that we saw these last few months going faster and faster. The third thing that I I think we are uh feeling is all of last year uh we really built on um like these reasoning models and we really like sawing pushing a lot on on reinforcement learning and initially when we had like 01 um 01 preview even 03 um these models were still like optimized for uh what we call verifiable rewards things where we actually have access to ground truth and like it's easy to test whether you're correct or not uh That is for example the case in like math questions or like comp like like coding competitions. And what I think we are realizing now is that we were able to take many of the tools that we built for these like verifiable reward cases and we were able to use them more generally in uh on for reinforce learning on like real use cases. And I think that's like really why we're feeling that right now in like um uh just real world coding rather than like competition. So we move from like competitions to uh usefulness to users and that's what we are feeling right now.

</details>

### 效率与推理：缩放曲线的左移

**Matt Turk**: 太棒了，引人入胜。我们将深入探讨其中很多内容，特别是 RL 方面。关于你提到的第一点“可靠性”，这是一种工程上的提升，还是模型层面的提升？是什么让一个模型在你所说的意义上变得“可靠”？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. Fascinating. So we're going to unpack a lot of this particularly on the on the RL side. For the first thing that you mentioned reliability is that a engineering is that models like what makes a model reliable in in in the way you meant it.

</details>

**Yann Dubois**: 这是一切的结合。但总的来说，考虑到这些是**智能体模型**（agentic models），如果你把它们看作每隔两分钟就有一定的出错概率，那么它们运行的时间越长，最终答案出错的概率就越高。这是智能体模型固有的特性。我们一直在大力推进的是降低这种每两分钟出错的概率。当然，从模型的角度来看，有很多可靠性工作也在应用层面发生，OpenAI 的团队在那方面做得非常出色，但我指的甚至是模型本身的可靠性，即确保我们降低了出错的概率。

<details>
<summary>Original English</summary>

**Yann Dubois**: It's a little bit of everything. But in general, given that these are agentic models, h the longer, if you just think about it as like every two minutes, there's like a certain probability that they're wrong. Uh the longer that they run, the the higher the probability that like the final answer is going to be wrong. Um so it's just something inherent in like agentic models. And what we've been pushing a lot on is like making sure that the model like we decrease this probability of being wrong every like two minutes. So purely from a model point of view of course there's a lot of reliability that is also happening on the applied side and the team at open air has been doing an an amazing job um on that um but I'm I'm even talking only about reliability of our models and like making sure that like basically we decrease the probability of being wrong.

</details>

**Matt Turk**: 太好了。GPT 5.5（以前被称为 **Spud**）正如刚才所说，是一件大事。我很想从内部人员的角度知道，你们最引以为豪的是什么？觉得最有挑战性的是什么？能不能给我们描述一下你们在发布这个模型时的感受？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. So 5.5 formerly known as spud was uh as mentioned a big deal uh is a big deal and I'm just a curious from the inside what was what are you guys the most proud of? What did you find the most challenging? Give us some some some color on like how you all uh felt uh you know releasing this.

</details>

**Yann Dubois**: 老实说，我们都对 5.5 感到非常兴奋。这是那种全公司都深度参与构建的模型之一。我认为我们现在确实能感受到它的影响力——因为 5.5，我们得到了很多关注，似乎所有的星星都连成一线了。这种情况并不总是发生。它真的是一个伟大的模型。这很有趣，因为总的来说，对于每一个早期看起来非常好的模型，我们都会感到非常兴奋，然后会产生大量的怀疑，因为大家会想：“噢，内部都在大肆宣传这东西，但实际上它在其他所有事情上都很糟糕。”然后会出现另一波浪潮，人们开始“低估宣传”它。它会经历不同的波动，取决于我们实际发布时内部人员的感受。但这在大多数模型中都是常态。GPT 5.5 在这方面没什么不同，但它的波动幅度可能更高。所以人们经历了非常兴奋，到没那么兴奋，然后我们发布了它，外部的人都很开心。

<details>
<summary>Original English</summary>

**Yann Dubois**: We're all really excited by 5.5 to be honest. It is one of these models where everyone in the company was extremely involved uh in building um and I think that we really feel it now that's like we got a lot of attention because of 5.5 and it's uh it seemed like all the stars were aligned. That doesn't always happen. Um and I was just like a great model for the for this. Um so we we did feel it. It's kind of funny because in general with every model that is looking really good early on, we have a model, we all get really excited about it and then there's like tons of doubt that start uh coming up because it's like oh like everyone is so hyp is like hyping this thing internally but actually it's like bad at all these other things and then there's another wave where like people start uh um underhyping it and it kind of goes through through waves and it depends like when we actually ship it how like people feel about it internally. But that's true with like most models that we have. Um, so 5.5 was not that different in this case, but it definitely maybe had like a a higher amplitude of the wave. So people were very excited then very not as excited and and we shipped it and and people are happy externally.

</details>

**Matt Turk**: 那个过程需要多长时间？包括那些兴奋感起伏的波动。我猜这取决于发布的版本和每个版本的重要性，那是几周还是几个月？

<details>
<summary>Original English</summary>

**Matt Turk**: How long does that process take? Like you know you including the waves of going up and down and of of excitement. I guess it depends on the on the on the release and the importance of each release, but like is that a is that a few weeks? Is that a few months?

</details>

**Yann Dubois**: 这真的不一定。我不能详细透露 GPT 5.5 投入了什么，但它确实取决于流水线的哪个部分在训练模型的哪些部分。我们确实有不同的子团队，包括**预训练**（pre-training）、中等训练阶段（mid-training stage）和后训练（post-training）。通常你越接近产品，比如后训练作为最后一环，迭代周期就越快。如果你处于更上游，迭代周期就越慢。所以时间跨度可能从几个月到几天不等。

<details>
<summary>Original English</summary>

**Yann Dubois**: It really depends. I so I cannot talk exactly about what what went into uh 5.5 but it kind it kind of depends um which part of the pipeline is training parts of the model. So we really have like different sub teams uh including pre-training and you have like the mid-training stage and like you have some post- trainining and usually the closer you get to to products like postraining being the last one the faster the iteration cycle is. Um and if you're more upstream, the slower the iteration cycle is. Uh so it could go from let's say from months to to days.

</details>

**Matt Turk**: 基本上 GPT 5.5 在智能体编程、计算机使用、知识性工作和早期科学研究方面表现得特别出色。这在内部是如何运作的？是有不同的人专注于这些不同的部分吗？你们是如何得到那个结果的？

<details>
<summary>Original English</summary>

**Matt Turk**: Uh basically 5.5 was particularly good um on a gentic coding, computer use, knowledge work and early scientific research. How does that work internally? Do do different people focus on those different parts? How do you get to that result?

</details>

**Yann Dubois**: 是的，我们肯定有不同的团队专注于特定的用例并推进这些用例。我的团队具体负责的是提取所有这些垂直领域的改进，并尝试将它们整合到最终模型中。你可以把这个团队看作是在执行一种“平滑函数”的工作。你有了所有的改进，但你需要确保模型不会感觉过于突兀，不会在不同的垂直领域表现得截然不同。此外，你还需要一些团队专注于横向改进，这基本上就是我的团队所做的。有很多事情，比如**指令遵循**（instruction following）、**函数调用**（function calling），或者思考模型在不同问题上应该思考多久，这些都是非常横向的，会影响到所有的用例。所以我们既有更垂直的团队，也有更横向的团队，两者对于改进模型都非常重要。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yeah, we definitely have different teams that are working on specific use cases and are pushing on these use cases. Uh my team specifically is actually the one that is kind of taking all these vertical improvements and try to put them together in the final model. You could see it as a team that is doing both kind of the smoothing function. So you have all these improvements, but you need to make sure that the model is doesn't feel too spiky, doesn't feel the differently in different on on different verticals. And also you you need to have some teams that are working and that's basically what my team is doing on all the horizontal improvements. So there are many things like instruction following function calling or like thinking about how much should a model think for on different uh problems those are very horizontal and that kind of impacts all these use cases. So we have both these more vertical teams and these more horizontal ones. Um and both are very important uh to to to improve the to improve on the model.

</details>

**Yann Dubois**: 好的方面是，这些事情可以正交地进行改进。你可能有多个不同的团队在特定的垂直领域工作，也许对于一个模型，只有一半的团队在最后一次运行中进行了集成并提高了模型在这些能力上的表现，而对于下一个模型，可能是另一半团队。这是高层运作的方式。另外一件事我想说，因为你也问到了我们对这个模型感到自豪的地方，我会说两点：第一是模型的**效率**。我们极大地提高了模型的效率，在大多数任务中，我们现在的表现基本上比以前快了两倍。这很棒。另一个我已经提到过了，就是公司的协调一致，确保每个人都在朝着同一个目标努力。这真的需要整个公司朝着构建一个好模型的北极星目标在特定的时间表内共同努力。我为这种协作方式感到非常自豪。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um, and the good thing is that these things can kind of be improved orthogonally. So you might have like multiple different teams that are working on certain verticals and maybe for one model there's only half of these teams that made integrations basically in the last run and like improved the model on on these capabilities and maybe for the next model it'll be the other half. So that's kind of at a high level how it works. uh one thing which I will say because you asked also about uh what are the things that we are really proud about for this model I would say two things number one is the efficiency of the model u we really really improved uh the efficiency of the model and like we most of the tasks and we basically performed I would say like 2x faster now with this model um so that's great uh and the other one that I already mentioned before but it's kind of this alignment of the company and making sure that like everyone is working towards the same goal. Uh and that really takes the entire the entire company working towards like this northstar of building one good model uh uh in in like specific timelines. So very very proud of how that happened.

</details>

**Matt Turk**: 太棒了。既然谈到效率，你们是如何优化的？我们谈论的是每个 **token** 的效率吗？我们是否也在谈论模型服务的延迟？AI 研究和工程各占多少比例？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. And then speaking of efficiency, how do you optimize for that? We're talking about efficiency per per token. Are we also talking about latency in serving the model? What what what part is AI research versus engineering?

</details>

**Yann Dubois**: 这就是为什么我说是整个公司的功劳，因为它真的来自各处。它必须来自**推理优化**（inference optimizations），也必须来自模型在思考时间上更高效。基本上，你思考的每一个 token 都是有成本的。通常你应该看的图表是：x 轴是思考的 token 数量，y 轴是性能。这就是我们观察的**测试时缩放曲线**（test-time scaling curves）。研究工作基本上是尝试将这条曲线向左移动——即思考更少就能达到相同的水平甚至更正确。然后推理部门也处理这个 x 轴，但将其从 token 数量转换为实际的延迟。最后人们关心的是 x 轴上的延迟与 y 轴上的性能。这就是所有事情交汇的地方，也是 GPT 5.5 真正实现的目标。所以，这就是为什么我总是说我为公司感到自豪。

<details>
<summary>Original English</summary>

**Yann Dubois**: So that's what that's what I I mean when I say it's the entire company is that it really comes from everywhere. It has to come from like inference optimizations. Um it has to come from the model being more efficient in its thinking time. So you have basically every token that you think for uh basically the the usual plot that you should be looking at is x-axis the number of tokens that you think for and y-axis um the the performance. So this is the these test time scaling curves that we look at. Um and research basically tries to move this curve to the left. So think less uh to be the same level or more correct. Um and then inference also deals with with this x-axis but switches switches it from number of tokens to actual latency. Um and the final thing that people care about is latency on x-axis performance on y-axis. And this is where everything comes together. And this is really what happened with 5.5. Um, so yeah, that's why I always say I'm really proud of the company for this one.

</details>

### 后训练前沿团队的职责

**Matt Turk**: 好的，太棒了。让我们聊聊你个人。你在“后训练前沿”团队（post trading frontiers team）。你描述过这个团队是横向的。那么，这个团队通常做些什么？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay, great. Let's talk about you for for for a minute. So you are in the post trading frontiers team. What? So that that team you described as horizontal. So what does the the team do in general?

</details>

**Yann Dubois**: 是的，我会说我们做三件事。从广义上讲，我们属于后训练部门。我的团队是后训练前沿团队。第一件事是，我们决定什么内容可以进入最终的运行。正如之前讨论的，有很多垂直领域，需要有人来决定什么可以进去，什么不能，并且为人们提供科学实验，让他们能在代表最终运行的环境中进行迭代。这是我团队做的第一件事。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yeah, I would say there's three things that we do. So in a broad broad sense, we are on the porching org. Uh, and my team is the porching uh frontiers one. Um so there are three things that my team does. Number one is we kind of decide what goes into the final run. Um so as we talked before there's like money verticals and someone needs to decide like what can go in what cannot and also provide the the science experiments for people to to iterate on something that's going to be representative of the final run. So this is the first thing that that my team does.

</details>

**Yann Dubois**: 第二件事是将所有东西整合在一起，并实际执行大规模运行。正如你可能想象的，我们训练时使用了大量的 **GPU**，所以需要大量的**基础设施**（infra）工作，同时也需要大量的**机器学习**（ML）工作，通过将所有内容放在一起来确保各部分能够良好协同。第三件事是模型的横向改进。基本上，有一些事情是那些垂直领域的团队通常不会太关注的，例如我之前提到的**思考时间**。对于某些答案，模型应该思考多久？或者像指令遵循、函数调用、内存类功能以及贯穿整个技术栈的通用模型改进。这就是后训练前沿团队的工作，我目前领导着这个团队。

<details>
<summary>Original English</summary>

**Yann Dubois**: The second thing that my team does is bringing everything together and actually doing the big run. So this has as you might imagine like we train on a good amount of GPUs. So there's a lot of infra work that is needed but also there's a lot of ML work that is needed by putting everything together and making sure things work well together. And then the third thing that my team does is uh horizontal improvements to the models. Basically there are some things that like these vertical schemes will not usually look too much at. For example the thinking time as I said before. So how much should the model think for on certain answers? um or like instruction following, function calling, uh things like memory and like general improvements to the model that are really across the stack. Um so that's what the pushing frontiers team does and uh and I'm leading that team.

</details>

### 个人背景：从 Word2Vec 到 Alpaca

**Matt Turk**: 好的，太棒了。你加入 OpenAI 的历程是怎样的？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay, great. And uh what was your journey to open AAI?

</details>

**Yann Dubois**: 噢，说来话长，但我尽量精简。基本上，我在瑞士完成了**生物医学工程**（biomedical engineering）的本科学习。我是瑞士人。然后我去加拿大参加了一个交换项目，在那里我了解了 **Word2Vec**。我不知道你有没有听说过这个算法，但它基本上是将单词这种离散的东西放入一个**向量空间**。你可以把它想象成一个平面，相似的词会靠得更近。它把这些离散的词带入一个在语义上有意义的连续空间，我被那个算法彻底震撼了。就在那时，我决定想要从事**自然语言处理**（NLP）的工作，去理解语言。

<details>
<summary>Original English</summary>

**Yann Dubois**: Oh, it's a long story, but I'll try to keep it really short. Uh basically, I did my undergrad in biomedical engineering um in Switzerland. Um, I'm from Switzerland and then I went on an exchange in Canada and I learned about word tove vec. So I don't know if you heard about this algorithm but it basically takes words which is like something discrete uh and puts it in a in a vector space. So puts it basically in a way to think about it as a plane where if words that are more similar to one another will be closer to one another. So it it brings these like discrete words into like some continuous space that is semantically meaningful and I was absolutely blown away by that algorithm and that's when I decided that I I wanted to work on natural language processing and just like understanding language.

</details>

**Yann Dubois**: 那个时候我大错特错，我以为英语 NLP 基本上已经解决或接近解决了，那是 2017 年。那正是 **Transformer** 架构刚刚开始的时候，其实是在那之前一点。所以我错得很离谱，但我决定想要研究低资源语言（under-research languages），基本上，我想要改进那些数据没那么丰富的语言的 NLP。所以我去了新加坡的 **Grab** 工作，为他们构建自然语言处理流水线，处理高棉语、印尼语、泰语、越南语等所有这些不同的语言。然后跳过一些环节，我在不同的国家做了一些学术性的工作，最后到了斯坦福大学读博士。在那里完成学业后，我经历了一段简短的创业阶段，然后去了 OpenAI。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um at that time I was very wrong but I thought that uh English uh NLP was basically solved or like close to being solved that was in 2017. So that was uh uh right when transformers started. I was actually right before transformers. So I was very wrong but I decided I wanted to work on under research languages and basically um I wanted to improve um NLP on languages where we don't have that much data. Uh so I went to uh work uh for Grab in Singapore and I was basically building the natural language processing uh pipeline for them. Uh working with Kum with Bahasa with Thai Vietnamese and all these different languages. And then I'm skipping a little bit. I had I did more academic type of work in different countries and I ended up at Stanford did my PhD there. Um and after this um had a small stint into startups and then went to open air.

</details>

**Matt Turk**: 是的，我记得在你的博客或网页上看到过一条给量化交易公司的备注，让他们不要联系你，因为你对对冲基金的工作不感兴趣。

<details>
<summary>Original English</summary>

**Matt Turk**: Yes. And I I remember seeing on uh I think your blog or your page uh a note to for for quant firms to not reach out to you because you were not interested in hedge fun work.

</details>

**Yann Dubois**: 是的，对我来说，思考我对世界产生的积极影响，或者至少是我尝试产生的积极影响，是非常重要的。所以这就是为什么会有那条备注。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yeah. by I always think it's very important for me to think about the positive impact that I'm having in the world or at least that I'm trying to have. Um so so that's that's why this note is there.

</details>

**Matt Turk**: 正如我们在开始录制前聊到的，人们可能在 GPT-5 的发布视频中见过你，你做了一个非常有趣的演示，现场构建了一个应用来教你的伴侣说法语。人们应该去看看那个。

<details>
<summary>Original English</summary>

**Matt Turk**: Yes. And as we were saying just before we started uh recording uh people uh may have seen you in the GBT 5 video announcement and you did this uh very funny uh demonstration of um an app that was built on the fly to teach your partner how to speak French. So like people should go check that out.

</details>

**Yann Dubois**: 没错。那很有趣，当时 **GPT-5** 还没那么可靠。所以我当时有点压力，担心它行不通，但最后还是成功了。

<details>
<summary>Original English</summary>

**Yann Dubois**: Exactly. Um that was that was a fun one. That was a fun one. It was TPT5 was not that reliable. So, I was a little bit stressed that it wouldn't work, but uh but it ended up working.

</details>

**Matt Turk**: 所以那是真正的直播，可能经过了非常非常多次的排练，但确实是直播。

<details>
<summary>Original English</summary>

**Matt Turk**: So, this was truly live and and presumably very very rehearsed, but but truly live.

</details>

**Yann Dubois**: 实际上，就在我们做那个演示之前的最后一次彩排，它没成功。所以我当时有点紧张。但不管怎样，最后的直播效果很好。

<details>
<summary>Original English</summary>

**Yann Dubois**: Actually, the um right before we did that, like the last rehearsal, it did not work. So, I got slightly stressed about that. But, uh but yeah, seems like live life ended up working well.

</details>

### 推理能力的进化：从竞赛到现实

**Matt Turk**: 是的，没有压力，但确实表现得很完美。好的，让我们来剖析一下我们在简介中提到的内容。我们实际上是从讨论**推理**开始的，我很想知道 2026 年的推理与我们之前讨论 O1 或 O3 时的对话有什么不同？特别是 GPT 5.5 的一个说法，以及我作为用户的体验，是它在处理**杂乱数据**（messy data）方面表现得特别好，这似乎意味着它需要推理更多的模糊性。发生了什么变化？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah, no pressure, but yeah, that that uh that landed perfectly. Okay. Uh, very cool. All right. So, let let's uh unpack uh some of the things we alluded to in the intro. So, we started effectively talking about reasoning, and I'm I'm curious what reasoning means in 2026 that's any different from, you know, a conversation we could have had about 01 or or or three. Um, in particular, one of the claims uh of 5.5 and and also my experience as a user is that it's particularly good with with messy data, which seems to imply that um it needs to reason through ambiguity more. Um, what has changed?

</details>

**Yann Dubois**: 我想说的是，O1 和 O1 Preview 确实是研究社区的突破，模型能够思考，而且思考的时间越长，正确的可能性就越高。那确实是一个突破，但最初如果你看旧的博客文章，你会看到大多是数学评估，或者是编程竞赛，这些都是非常容易测试你是否正确的东西。这其实也暗示了我们是如何训练其中一些模型的。

<details>
<summary>Original English</summary>

**Yann Dubois**: What I would say is that 01 and 01 preview uh were really really breakthroughs um in in the research community about having model that can think and the longer they thought for the more like the higher likelihood they would be of being correct. Um so that was really a breakthrough but initially and if you look at like old blog posts you would mostly see like math uh math evals and also like maybe coding competitions but things that are really easy to test whether you're correct or whether you're not. Um and it also gives you like some suggestion about like how we were training some of these models.

</details>

**Yann Dubois**: 而我看到的去年整年，特别是去年年底和今年年初，是我们能够将这些适用于可验证奖励（即我们可以说你是否正确的领域）的算法带到杂乱的现实世界中，并真正针对我们为用户提供的效用进行优化，让他们更有生产力。我认为这才是真正改变的地方。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um, and how I see maybe all of last year and especially the end of last year and the beginning of this year is that we were able to take these algorithms that work with uh verified rewards like things where we can say you're correct or you're not uh to the messy real world um and really optimize for the utility that we provide to users and like making them more productive. Uh so I think that's what really changed.

</details>

**Matt Turk**: 好的，所以很大程度上是后训练强化学习部分。

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. So it's the post-training reinforcement learning part largely.

</details>

**Yann Dubois**: 是的，我想说那是很大一部分。当然还有另一个重要部分。首先，当你开发一种新方法时，这种方法往往是脆弱的，没那么可靠，很难产品化。所以这一部分也改进了很多。但随后，基本上我们有了一个可以开始针对不同事物进行优化的工具，最初当我们开发这个工具时，我们对现实世界做出了很多简化的假设，现在我们正在移除这些简化假设。至少在后训练中，我们能够优化用户的效用，确保这些模型有用，并且我们正在查看的任务是有用的。这就是为什么现在的评估看起来更真实。如果你想到 **GPT Eval**，或者如果你看 **ThreeBench Pro**，这些看起来比我们在 O1 时看到的那些 Codeforces 或编程竞赛要真实得多。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yeah, I would say that's a I mean there's also there's also another big part of it. Uh number one basically the first thing is that of course when you develop a new method uh the method is kind of fragile um and is not that reliable and like it's hard to to basically productionize. So this bot also improved a lot. Um but then it's also really basically we had a tool that we could start optimizing for for different things and initially when we were developing this tool uh we were optimi we were making a lot of simplifying assumptions of in the real world basically and and now we are removing these simplifying assumptions and and at least in posting we are able to optimize really like user utility and make sure that these models are useful and the tasks that we're looking at are useful and that's why also now current evals look much more realistic Um I mean if you think about GDP val or even if you look at like threebench pro or threebench these look way more uh realistic than let's say some code force or like coding competitions that we were looking at with 01.

</details>

### 推理深度：Thinking 与 Pro 的区别

**Matt Turk**: 还是关于推理的话题，**GPT 5.5 Thinking** 与 **GPT 5.5 Pro** 之间最终的区别是什么？仅仅是更多的测试时计算（test-time compute）、更多的 token 以及投入更多时间来解决问题吗？

<details>
<summary>Original English</summary>

**Matt Turk**: And still on the topic of of reasoning um what's ultimately the difference between 5.5 thinking versus 5.5 pro? Is that is that just more test time compute, more tokens and more time invested in solving a a problem?

</details>

**Yann Dubois**: 是的，基本上这只是我们向模型或整个系统投入多少测试时计算的问题。我们一次又一次地看到，模型思考得越久，得到的答案就越好。问题在于，我们讨论的这些曲线绝对不是线性的，存在一种平台效应，某种意义上它们看起来是呈对数增长的，取决于具体的评估。所以你可能投入两倍的计算量，却只能获得很小的性能增益。我个人不怎么用 Pro，因为我不喜欢等待。我比较没有耐心。我知道正确的概率肯定会提高，但对我来说提高得还不够。但确实有一些人使用 Pro 并非常喜欢它，特别是对于学术研究，我认识很多数学家在使用它。这是因为他们可以把它放在后台运行一个小时、两个小时，他们不需要和模型进行快速迭代，Pro 非常适合这种场景。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yes, basically it's just a question of of uh how much test time compute we pour into the model uh or we pour into this entire uh system that we're shipping. Um so we we've seen again and again the longer the model thing for uh the better answers we will get. The problem is that this these curves that we're talking about um are not are definitely not linear and like they there's some plateauing effect and they kind of look um lo logarithmic on some in some sense um or depending on which evals. So you can pour like two times more compute and actually only get like small performance gains. Um I personally don't use pro that much because I really don't like weight. I'm pretty impatient, so I don't like waiting for that long. And uh and I know that the probability of being correct definitely improves, but it doesn't improve like enough for for me to use it. Um but there are some people who use pro and who really love it especially actually for academic research and uh I know especially a lot of mathematicians who are using it and that's because they're kind of just have this in the background that is running for maybe one hour uh two hours and they don't really need to like iterate really quickly with the model um and pro is really good for that.

</details>

**Matt Turk**: 我很想把这一点和你之前提到的每个 token 的效率联系起来。那么，这个想法是你可以思考得更久，但同时也更高效，从而更好地解决任务吗？时间维度和效率维度是如何相互作用的？

<details>
<summary>Original English</summary>

**Matt Turk**: I'd love to reconcile this with uh what you were mentioning about efficiency earlier per token. So is the idea that um you would be able to think longer but also be more efficient therefore solve the task better like how do those the the the time aspect and the efficiency uh aspect sort of interact?

</details>

**Yann Dubois**: 是的。如果你回到我讨论的那张图，x 轴是延迟，y 轴是性能。当我们说提高效率时，我们基本上是在将这条曲线不断向左移动。也就是说，我们变得更高效了，或者说我们花费更少的时间就能达到相同的性能。而 Pro 做的是延伸这条曲线。它说，我要思考更久，但我会有更高的正确概率。但 Pro 模型的每一次迭代也都在向左移动，它也变得越来越高效。重要的是，总会有一些任务你只想最大化正确的概率，而并不真正关心延迟。例如，如果我在睡觉前启动一个任务，模型有八个小时的时间，它就应该尽可能地思考。这就是 Pro 模型能给你的。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yes. Uh so if you go back to like the plot that I was talking about I was thinking about uh where on the x axis we have latency and y axis we have performance. We're basically moving this curve when we say that we improve efficiency more and more to the left. So we're becoming more efficient uh or like we spend less time to achieve the same performance. Um but what pro does is that it extends this curve. So it says like um I'm going to think for much longer but I will have a higher likelihood of being correct. But every iteration of the pro model also moves to the left. So it also becomes more and more efficient. The important part is um there will always be tasks where uh you just want to maximize the probability of correctness and you don't really care about latency. Uh for example, if I if I start a job before going to sleep um I mean the model has like eight hours like it should just think for as long as it as it can. Um and this is what kind of promo gives you

</details>

**Matt Turk**: 用通俗的话来说，这在实践中意味着什么或者说如何运作？如果模型走错了方向，它会提前中断自己吗？这是其中的一个维度吗？

<details>
<summary>Original English</summary>

**Matt Turk**: and uh in layman's term like what what what does that mean practically or how does that work practically? If the model goes in a wrong direction uh then it would interrupt itself earlier is that is that one of the axis

</details>

**Yann Dubois**: 关于效率意味着什么？让我给你举一个关于人类的类比。如果你有一个某个领域的专家，你把他和刚入门的大二学生比较，那个大二学生做同样的任务可能需要一天或两天，他必须思考很多可能性并进行调查，因为他从未处理过某个特定问题。而该领域的专家通常一眼就知道该走哪个方向，他不会把时间花在调查 10 个不同的方向上，因为他知道其中一个更有可能正确。这就是我们谈论的那种效率。

<details>
<summary>Original English</summary>

**Yann Dubois**: so for the effic Okay so there's two things are you asking for the efficiency what does it mean? Um let me give you um maybe a metaphor from like humans. Uh if if you have a someone who know like someone who's an expert in certain domain uh and you compare them to like some undergrad that is like starting in that domain, uh the undergrad doing that task will probably take might take like one day, two days and we'll have to think through a lot of like the um the possibilities and like investigate because it never did a certain problem. while someone who's an expert in that in in that field will usually just like know what direction to take and it will it will not spend the time on like investigating 10 different directions because it knows that there's like one that is more likely to be correct. So this is the type of efficiency that we're talking about.

</details>

**Yann Dubois**: 基本上这些模型在现实世界问题上进行了更多的优化。结果是，它被训练成能以更高的概率弄清楚哪些推理路径更有可能正确。这就是效率的一部分。还有你建议的一点，即模型知道自己什么时候走错了路。这也是可以通过强化学习训练模型的能力，比如意识到“这看起来不像一条好的路径，让我回溯一下去测试别的”。如果你对模型的训练不够，它意识到自己走错路的时间可能会晚得多。

<details>
<summary>Original English</summary>

**Yann Dubois**: It's basically models that we where we optimized more on like real world problems. Um and as a result it was kind of trained to uh to figure out with a higher likelihood which paths of reasoning are are more likely to be correct. Um so this is this is a part on on efficiency. There's also what what you suggested is that um part of it is the model knowing when it's going down the wrong path. Uh but this is also something that we can um that the the model can be trained for with reinforcement learning is like knowing okay like that seems like not a great path. let me backtrack and let me go and and test something else. Um, and if you train the model less, it might realize it's in the wrong path much later.

</details>

### 训练流程：预训练与中等训练

**Matt Turk**: 好的。看来很多内容都回到了强化学习和后训练。让我们谈谈现代 AI 系统的不同组成部分。我们来谈谈预训练、**中等训练**（mid-training）和后训练，并在后训练上多花点时间，因为它非常重要。首先从预训练开始，考虑到你可能无法详细谈论 GPT 5.5 具体是如何做的。去年的一大叙事是预训练正在撞墙，不会产生太多进展，但在 2026 年看来似乎并非如此。你能带我们了解一些关于预训练正在发生什么的看法吗？为什么它现在的进展超出了人们去年的预期？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. All right. So, it seems like um a lot of this uh goes back to uh reinforcement learning and post- training. So, let's uh talk about uh how the different components of modern AI systems work. Uh so let's talk about pre-training, mid-training and and post- trainining and spend more time on post-training since it's so important. Uh starting with pre-training uh first at at a high level and and realizing that you may or may not be able to talk about how the things are are done or what happened in the context of 5.5 specifically. You know, big narrative of last year was that pre-training was hitting a wall uh and was not going to yield much progress. that seems to not be the case at all uh in 2026. Uh can you walk us through some some ideas for what is happening in pre-training and why it's progressing now in a way that people hadn't predicted uh last year

</details>

**Yann Dubois**: 对于预训练，我不能谈论内部发生的很多细节。除了团队确实做了很多出色的工作，我们的模型确实变得越来越好。我想强调的一点是，当我们谈论效率时，如果你拥有更大的模型，思考的时间（即它需要思考的 token 数量）通常会减少。你可以隐喻地理解为，模型在生成某个 token 时已经通过其**权重**进行了思考。所以你可以通过增加训练的模型规模来减少它需要生成的思考 token 数量。所以通常如果你增加模型规模，如果你预训练更大的模型，你会获得更好的效率。

<details>
<summary>Original English</summary>

**Yann Dubois**: for pre-training I I can't talk in a lot of details about what is happening internally. Uh besides that um the team has been really doing a lot of good work um and our models are really getting better and better. Um one one thing that I do want to um highlight when we're talking for example with efficiency um if you have larger models uh the amount of thinking time so the amount of tokens that will think for um will usually decrease. And the way that you can think about it is that um metaphorically the model already thinks through its weights when it generates a certain token. Um so you can you can decrease the number of like tokens that it needs to generate for thinking by kind of like increasing the size of the model uh that you're training. Um so so oftentimes if you just increase the the model size if you basically train uh pre-train larger models uh you will get better efficiency.

</details>

**Yann Dubois**: 更大模型的优点是它们在推理时可以更好地**并行化**。所以尽管你可能认为，你实际上生成了更少的 token，但是是由更大的模型生成的，所以你实际上可能会降低整个系统的整体效率。事实并非如此，因为模型越大，你就越有机会针对 GPU 上的推理进行优化。所以你能够使整个系统更加高效。这是关于大模型能带给你很高效率的一点。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um and the good thing with larger models is that they can be paralyzed better on on at inference time. So the even though you might think okay you actually generated fewer tokens but by a larger model uh so you actually might decrease the uh the overall efficiency of the system. This is not true because the larger the model is the the more chances you have to actually uh optimize for optimize basically for inference on on on GPUs. So you will be able to uh um to make them the overall system like more efficient. So that's that's one thing I wanted to say with like larger models that are actually giving you a lot of efficiency.

</details>

**Yann Dubois**: 否则，就预训练而言，我觉得非常有趣。我两年前也认为预训练可能正面临瓶颈。当我们看 **Anthropic** 的模型时，比如 Mythos，从成本上看，它显然是一个大得多的模型。通常如果你想知道它是不是一个更大的模型，你只需看每个 token 的成本，显然他们仅仅通过增加模型规模就获得了非常好的性能。所以我认为业界，至少是一部分人对此感到惊讶。之前有很多关于撞上“数据墙”的讨论，看来我们还没有完全撞上。模型越大，训练它就需要摄取更多的数据。看来不同的公司找到了不同的方法来克服互联网数据不足的问题。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um otherwise in terms of pre-training I think it's very interesting. I actually also thought maybe two years ago that pre-training was kind of hitting a wall. Um and when we see for example if we talk just about entropic I mean myth is seems like clearly just a much bigger model when you look at the cost um uh the cost of the model. Usually that's how you know by the way if it's a if it's a bigger model you just look at the cost um per token and and clearly they're getting very good performance uh just by increasing the size of the model. Um so I think the field was a very at least part of the field was surprised uh about that. There were a lot of conversation about hitting uh data walls and it seems like we did not quite hit it. So the larger the model is the more data it needs to ingest to be trained. Um and it seems like different companies kind of found different ways um to overcome the fact that that we don't have that much data on the internet.

</details>

**Matt Turk**: 下一个前沿或者是当前的数据前沿是**多模态**数据吗？还是**合成数据**？

<details>
<summary>Original English</summary>

**Matt Turk**: Is the next frontier or the current frontier uh for for data multimodel data? Is it synthetic data?

</details>

**Yann Dubois**: 我认为合成数据在数据受限的情况下可能效果很好。多模态也是一个有趣的方向。我肯定不能谈论我们在内部做的事情，但我以前研究过多模态**表示学习**，我一直认为如果你有大量的多模态数据，真的会帮助你的推理能力。我仍然这么认为，但例如看 Anthropic 的模型，它们在多模态方面似乎没那么好，但仍然非常聪明。所以看起来多模态并不是像我以前认为的那样必不可少。我仍然相信，一旦我们进入**具身智能**（embodied AI），你会学到很多关于世界的知识。通过学习世界如何自我互动，你会提高通用智能和对用户的实用性。但至少从 Anthropic 的模型来看，似乎他们不需要那么多多模态数据就能拥有强大的模型。

<details>
<summary>Original English</summary>

**Yann Dubois**: I think synthetic data can probably work well in a in a data um data limited regime. Um I think multimodal is an interesting one. Uh I I definitely cannot talk about what we do internally but like I used to work on multimodal uh representation learning back in the days and I always thought that it would really help uh kind of your reasoning abilities if you have a lot of multimodal data. Um and I still think this but but for example like if you look at entropic models they tend to not be that good on multimodal and they are still really smart. Um, so it seems that uh it's not as necessary as at least I would have thought in the past. Um, I still believe that once we go to embodied agents, embodied AI, you will learn a lot about the world. Um, and you will kind of improve general intelligence and usefulness to users um by learning how how the world interacts with itself. uh but at least looking for example entropic models it seems like they they don't need that much multimodal data to have strong models

</details>

**Matt Turk**: 具身智能是指机器人吗？所以如果你使用一段显示重力如何运作以及机器人在空间中如何演进的视频，那么想必那会更有用，是这样想的吗？

<details>
<summary>Original English</summary>

**Matt Turk**: and by embodied intelligence so you mean so potentially robotics and so if you use a video uh that shows how gravity works and how a robot evolves in space then presumably that would be more useful is that is that the thought

</details>

**Yann Dubois**: 是的。我想很多人都有这种直觉，我也一直有这种感觉，那就是仅仅通过文本很难理解物理学。如果不亲眼看到物体下落，你就很难理解重力。看我们的模型，它们在没见过实物的情况下也某种程度上理解重力，但效果并不直观，它们似乎仍然缺乏一些**常识**。所以我确实觉得，通过让它们在现实世界中互动，我们会提高模型的常识。但我想我们离那还相当远。我指的是学术界和 AI 社区总体上离那还很远。

<details>
<summary>Original English</summary>

**Yann Dubois**: yes the the idea the the intuition that I think many people had and I I definitely felt for a long time is that it's hard to understand the uh only through text and and they will be um it's hard to understand what like what physics is without really seeing what like for example you can't understand gravity without really seeing things falling um and when you look at our models I mean it's they kind of understand gravity without having seen that but it still seems not obvious like it seems still seems like they would get it more and like they are still kind of missing some common sense aspects. Um, so I do feel like we will improve the common sense of our model by having them interact in the real world. Um, but we are we're still pretty far from that I think. And by we, I mean just generally the academic community and and the AI community seems pretty far from that.

</details>

**Matt Turk**: 好的，回到预训练、中等训练和后训练。让我们谈谈中等训练。这可能是人们听说得比较少的一个词。它是什么？为什么它很重要？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay, great. All right, so going back to pre-training, mid training, post- training. Let's talk about mid-training. It's might be something that people have heard about a bit less. The term comes up a bit less. What is it and why is it important? Mid-training

</details>

**Yann Dubois**: 正如你从名字中可以意识到的，这只是处于预训练和后训练之间的一个想法。核心想法是，如果你有高质量的数据，能更真实地代表你最终模型想要的东西，你应该在这些数据上进行**过训练**（overtrain）。退一步说，预训练是什么？它基本上是尝试通过学习互联网上的一切来学习世界上的一切。问题是，互联网上的大多数东西其实并没什么用。如果你想到维基百科或者像 **GitHub** 这样的编程数据，其中的信息量似乎比某些随机论坛要多得多。互联网上也有很多广告，你可能不想在那些上面训练太多。所以在预训练中，我们在所有东西上进行训练，而在中等训练中，我们基本上会给这些我们认为对训练最终模型更有用的高质量数据赋予更高的权重。我不能谈论每个人的具体做法，但目前在学术界和所有的开源模型中，肯定都有这个中等训练阶段。

<details>
<summary>Original English</summary>

**Yann Dubois**: um is just this this idea of something that's between pre-training and as you might realize from the name and kind of the post-training um part of this part of the pipeline. Uh and really the idea is if you have high quality data um that is more representative of what you really want in your final model um you should overtrain on that data. Um so taking a step back here pre-training what is it pre-training it's basically trying to learn everything from the world by learning everything from internet at a high level. Um the problem is that most things on internet are not really useful. Uh if you think for example about Wikipedia or like GitHub which is like coding data um it just seems like there's way more information in there than some random forums. Uh um yeah, some some random farms that may maybe not like have that much information like for example ads there's also lots of ads on the internet like you probably don't want to train too much on that. Um but in pre-training we train on everything and in mid-training we basically overweight this type of high quality data that we think is more useful uh for for training the final model and this is something I I can't talk about what's happening everybody but this is like something that that is happening definitely in all the academic community right now and in all the open source uh models have this stage of mid training

</details>

### 后训练的深度剖析：从克隆行为到优化奖励

**Matt Turk**: 太棒了。后训练，让我们从高层定义开始。后训练包括强化学习，但那不是唯一的部分。还有什么？

<details>
<summary>Original English</summary>

**Matt Turk**: great post training let's start uh at a high level by by defining what that is so there's reinforcement learning but that's not the only part of post training. What What else is there?

</details>

**Yann Dubois**: 这取决于你如何定义这个术语，以及你如何划分界限。在我看来，从广义上讲，后训练包括了所有的强化学习以及推理模型的训练。它的核心想法是，将一个了解世界一切知识的东西，转变为对人们有用的东西。关于预训练，我喜欢用的一个比喻是：你走进图书馆，那里有关于一切的书，理论上你可以在图书馆找到你想要的所有信息。但直接与学习过这些书的专家交谈会更有用，你可以向他们提问，他们能够理解你到底在寻找什么。所以后训练的目标是让模型对用户有用，更容易互动。

<details>
<summary>Original English</summary>

**Yann Dubois**: It kind of depends how you define the term uh and where you put the boundaries. In my mind, post training um including let's I'll take it from a very broad sense which includes all the reinforcement learning and like the training for our reasoning models. Um is just the idea of having something that knows everything about the world to making something that is useful to people. Um so pre-training I think about it or the metaphor that I like giving is uh you go in the library and you have a lot of books about everything and in theory you can find all the information that you want in the library but it's much more useful to talk to an expert who has learned these books and that you can ask questions to and they can answer they can answer and like they can understand like what you're actually looking for. Um so this is kind of the goal of of pushing at a at a very high level is like making something that is useful um uh to users and is like easier to interact with.

</details>

**Yann Dubois**: 这通常有多个阶段。我只谈论 OpenAI 之外以及通常的阶段。通常会有一些 **SFT**，也就是**监督微调**（Supervised Fine-tuning）。在早期，大多数正在进行后训练的模型只做监督微调。这个想法是，如果你有能够提供理想最终答案的人类。如果人类能给你标准答案，你基本上可以克隆人类的行为。这就是我们所说的**行为克隆**（behavior cloning）。问题是，你永远不会做得比你的标准答案更好。人类在很多方面实际上是相当受限的。所以你永远无法超越你合作的人类标注员。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um so there are multiple uh stages I I'll talk mostly well I'll talk only about things that are happening outside of OpenAI and kind of the the usual stages. Um there's usually some SFT that is happening which is supervised finetuning. Supervised finetuning. Yes. uh supervised fine tuning and that's um that's actually what early on most of the uh models that were portraying were only doing supervised fine tuning. This is the idea is that if you have humans that can give you uh the desired final answer. Um so if you have if yeah if you have humans that give you the gold answer you can basically clone the behavior of the human. H so this is what we call behavior cloning. Um the problem with this is that you will never get better than what your ground truth gives you. Uh and humans are actually pretty limited in many in many sense. So you will never like overcome uh the the the the human labelers that you you're working with.

</details>

**Yann Dubois**: 强化学习阶段则是从行为克隆转向真正地优化奖励。这个想法是：我不知道标准答案是什么，我不知道完美的答案是什么，但我知道如何判断答案是否正确。我知道我想要在答案中看到什么。然后你开始优化。你开始让模型尝试获得更多的**奖励**（reward），优化这个所谓的**奖励函数**（reward function）。它会超越你目前拥有的、人类能做到的或者说你合作的标注员能做到的水平。这是两个大的阶段。在强化学习中，取决于训练的是哪些模型。至少在开源社区中，强化学习有不同的方式。首先是具有可验证奖励的强化学习，即非常容易判断对错，你可以有一个二元奖励，这回到了我们之前讨论的 O1 模型。

<details>
<summary>Original English</summary>

**Yann Dubois**: Uh the reinforcement learning or reinforcement learning stage goes from behavior cloning to really like optimizing rewards. So the idea is I don't know what the ground truth is. I don't know what the perfect answer is, but here here's how I would say whether the answer is correct or not. And here are the things that I I want in the answer. And what you do is you start optimizing. You start having a model that tries to to get more reward basically optimize more um uh this this reward function that that's how we call it. Um and it goes beyond what you currently have what what like humans can do or at least the humans that you're working with can do. Um so this this I would say is the two big stages. Then in reinforcement learning uh that depends in like which models are being trained. At least in the open source community it seems that there are there are different ways of doing that. Reinforcement learning when you have verifiable rewards. So, uh, reinforcement learning where it's really easy to say whether something is correct or not and you can really kind of have a binary reward for this and that goes back to how we talked about 01 uh and 01 preview in the past.

</details>

**Yann Dubois**: 然后是针对没有可验证奖励的任务进行强化学习，在那里我可能会做**两两比较**（pair-wise comparisons）。我可以说明这个答案比另一个好，但我并不真正知道完美的答案是什么。当然，这是一个连续的光谱。但我会说这是思考后训练时的三个高层阶段。在开源世界中，人们通常的做法是：先通过 SFT 克隆人类行为，当模型达到相当不错的水平后，再通过强化学习超越目前的水平。因为如果你直接从强化学习开始，效率会非常低。因为强化学习的问题是你必须“撞见”正确答案。强化学习的工作原理是，你从正在训练的模型中进行大量采样，然后判断哪些正确，哪些不正确，并告诉它“多做正确的那种”。所以你必须碰巧产生正确的解决方案。因此，你最好先尽可能地接近你能达到的最佳水平（行为克隆），然后再进行强化学习。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um, and then you have reinforcement learning without verifiable rewards where maybe I could do pair wise comparisons. I can say this this answer is better than this this other one, but I don't really know. I cannot quite say this is the perfect answer. Um so of course like it's a continuum and there's everything in between but I would say these are like the three uh high level uh things to think about when you think about post training in general um and how people are usually doing it in the open source world is that they take SFT uh they clone the behavior that you you can collect online or from humans and then once it's already at a pretty good level they just do this reinforcement to go beyond what we currently have because if you just started from reinforcement learning it would be very inefficient. Uh because the problem with reinforcement learning is that you have to stumble across the right answer basically because how how reinforcement learning works is you sample many times essentially from uh from the model that you're training and you say this one is correct this one is not and you say do more of the one that is correct. So you have to stumble across the right solution. So you're much better off first getting as much as closer as possible to the best you can do. Um and this is this behavior cloning and then doing reinforcement.

</details>

### 强化学习的挑战：从“顶部的樱桃”到核心引擎

**Matt Turk**: 强化学习是创造了新的能力，还是让模型在现有能力上表现得更好？

<details>
<summary>Original English</summary>

**Matt Turk**: Does reinforcement learning uh create new capabilities uh or does it make the model better at existing capabilities?

</details>

**Yann Dubois**: 这很难说。可以说当预训练在整个互联网上进行训练时，它已经拥有了所有的能力。所以要在科学上回答这个问题甚至很难。我想说的是，如果你看两年前我们在开源世界中推送的模型，例如我参与过的 Alpaca，我们使用了 50,000 个例子进行 SFT。而现在你看像 **Kimi** 或 **DeepSeek** 模型的强化学习，它们似乎接近 100 万个数据点。所以人们极大地扩展了强化学习阶段的规模。从这一点来看，它们确实学会了新的能力，比如这种**推理能力**，即你可以检查你的答案并尝试改进它。你可以思考更久以获得更正确的答案。所以我想说的是，虽然理论上预训练中已经包含了一切，但在过去的一年半里，即使在开源世界，我们在强化学习后确实拥有了比以前更多的能力。

<details>
<summary>Original English</summary>

**Yann Dubois**: It's really hard to say because retraining when it's trained on all of the internet arguably already has all capabilities in it. Um so it's it would be even hard to answer this question scientifically. Um because arguably everything is is already there. What I would say is that if you look uh at models that we were training or that we're pushing like two years ago in the open source world uh for example I worked on one of them alpaca where we used 50,000 examples for SFT and like now when you look at reinforcement learning from from models like Kimmy or or or from deepseek models it seems that they are closer to 1 million data points. So definitely people scaled up a lot the reinforcement learning stage. Um and from this it seems that they've learned like new capability like this reasoning aspect this fact that you can check your answer and and uh and try to improve it. Um so you can you can really think for longer to get to get a more correct answer. So all this to say that arguably everything is already in pre-training but we were definitely able in the last one year and a half even even in the open source world um to have more capabilities after reinforcement learning that we used to uh before

</details>

**Matt Turk**: 我听说过好几次，强化学习非常棘手且难以扩展。作为行业，我们没有将强化学习作为初始 LLM 进展曲线的一部分，正是因为它难以奏效。扩展 RL 的难点在哪里？是数据集的问题，还是知道奖励在哪里？还是别的什么？

<details>
<summary>Original English</summary>

**Matt Turk**: I heard several times that reinforcement learning is pretty finicky and and hard to scale and part of the reason why we as an industry didn't do uh reinforcement learning as part of the initial kind of LLM sort of progress curve was was precisely that that it was hard to to make work. What is hard about scaling RL? Is that a question of uh data sets knowing where the rewards are? Is there is that or something else?

</details>

**Yann Dubois**: 我想说两年前学术和研究界大多数没写过强化学习代码的人可能都认为它行不通，而且太棘手了。我以前也是那样的人。实际上当我看到 ChatGPT 发布时，看到他们使用强化学习的博客，当时我还没在 OpenAI。我的第一个念头是：我可以在不使用强化学习的情况下做同样的事情，因为这只是一种过度复杂的方法。这实际上就是我们开始研究 Alpaca 时想要解决的问题——尝试仅使用 SFT，仅通过这种行为克隆来重现效果。

<details>
<summary>Original English</summary>

**Yann Dubois**: I would say most people who did not work in reinforcement learning in the academic and like in research community up to two years ago probably thought reinforcement learning would like just doesn't work and is like too finicky to to work with. Uh I used to be that type of person and actually when I saw Chad GPT come out they had the this blog I was not at openi at the time. Uh I saw this blog that says that they use reinforcement learning and my first thought was I can do the same without reinforcement learning because this is just an over complicated method and this is actually the problem that we started working on with alpaca was exactly let's try to reproduce that only using SFT just by doing this behavior cloning.

</details>

**Yann Dubois**: 例如，**Yann LeCun** 有个著名的比喻：强化学习就像是“**顶部的樱桃**”。我认为那是当时大多数人的直觉。但在跨越了某个规模的模型，拥有了所谓对世界的良好先验知识之后，强化学习似乎就开始奏效了。这不仅仅发生在 LLM 领域，机器人领域似乎也进入了同样的阶段。他们意识到虽然以前很棘手，但现在使用这些已经了解世界一切知识的模型，学习效果非常好。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yeah. And like for example, Yanuk famously like gives like this metaphor of like oh the reinforcement is like the cherry on the top. So I think that was really like the intuition that most people had. Um it seems that after crossing a certain scale of um models that know basically everything about the world and what we call like good priors about the world. It seems that reinforcement learning just started to work and this is not only with LMS. robotics seems to have or get seems to be entering the same stage uh where they're realizing that actually it used to be very finicky but now that we use models that like know already everything about the world it actually learns pretty well um

</details>

**Yann Dubois**: 现在来回答你关于强化学习目前复杂之处的问题：一是基础设施方面。强化学习中，你需要进行大量的采样并判断正误，这种采样非常昂贵，而且必须大规模进行。开源世界目前看到的另一个问题是，当你训练更具**智能体特性**（agentic）的系统时，你只有在漫长的执行过程（roll out）结束时才知道自己是否正确。这意味着你从每个 token 中获得的关于你是否正确的信息非常少。很难进行**归因**（attribution）。很难说你的整个答案中哪一部分是导致你正确的关键。这更多是机器学习方面的问题。机器学习的理想情况是：我可以明确说这部分做得好，以后多做。而智能体系统和 RL 的问题是你直到最后才知道哪部分是好的。这是强化学习的另一个重大挑战。

<details>
<summary>Original English</summary>

**Yann Dubois**: now to answer your question about what is still complicated with reinforcement learning one is an infra aspect um so just like systems in general uh reinforcement learning you have at a very high level basically to sample as I said for many answers and say like what is correct um and what what is not and um and like this sampling is just very expensive and you have you have to do it at scale. Um the other issue that that also in the open source world we uh people are seeing right now is that when we are training more agentic uh systems you only know whether you're correct at the end of your very long roll out. Um so you get very little information per token of whether you were correct or not. And it's hard to say uh it's it's hard to basically do attribution. It's hard to say what part of your entire answer was the one that led you to being correct. So that's more of a of an issue on the machine learning side. It's uh the the the ideal world in machine learning is when I can say exactly like this thing was good do more of that. And the problem again with with uh with these agentic systems and and reinforcement learning aentic system is that you don't really know which part was good or not until you arrive at the end. That's another big issue from from from re reinforcement learning.

</details>

**Matt Turk**: 目前强化学习的前沿是什么？似乎有一堆缩写词，比如 **GRPO** 之类的技术。你们在使用什么？你对什么感到兴奋？你认为什么是有前途的？

<details>
<summary>Original English</summary>

**Matt Turk**: What's the current uh frontier of reinforcement learning? It it seems like there's a jungle of acronyms like GRPO and uh other techniques. What uh what are you using? What are you excited about? What do you think is promising?

</details>

**Yann Dubois**: 我不能谈论我们在用什么，但例如在开源世界，GRPO 似乎效果很好。人们以前使用像 **PPO** 和 **DPO** 不同的方法，现在似乎都向这一种收敛了。它与其他方法的一大区别在于，你采用了我告诉过你的这种简单方法：尽可能多地采样答案，并说哪一个正确。所以从某种程度上说，GRPO 是一种非常简单的方法。总的来说，我们在机器学习中一次又一次地看到，可以扩展计算规模的最简单方法，通常就是最终效果最好的方法。这就是开源世界目前正在发生的事情。

<details>
<summary>Original English</summary>

**Yann Dubois**: So, I can't talk about what we're using, but like for example uh in the open source world, GRPO seems to be working very well. Um and people used to have different methods like PO and and DPO and like people seem to have really converged to this one. Uh the big the big difference with others other methods is that um you again you do this like simple method that I told you about like sampling as many answers as possible and you say which one is correct. Uh so in some way GPO is a very simplistic method. uh and in general we saw over and over again in machine learning that the the simplest method that where you can scale up in terms of compute usually is the one that ends up working the best and that is kind of what is happening here um at least in the open source world

</details>

### 科学、手艺与评估的困境

**Matt Turk**: 你在日常工作中，如何界定科学与“手艺”的界限？或者说是通过多次尝试保留最有效的部分？

<details>
<summary>Original English</summary>

**Matt Turk**: as you described some of the challenges question crossed my mind uh you know you often hear that AI systems are not built they grown how you'd characterize it as well what part is science versus a craft or trying multiple things and then just keeping what works best in your day-to-day life.

</details>

**Yann Dubois**: 这是一个很好的问题。我想它通常是从“手艺”开始的。人们只是尝试很多东西，并开始建立关于什么有效、什么无效的心理模型。随着时间的推移，我们从这个“手艺之地”转向更多的**科学**方法。科学方法很少是第一个起效的。很少有情况是你采取真正科学的方法并说“这是最佳的做法”，做完后它就直接奏效了。这其中有一种“**炼金术**”的感觉。人们只是对某事有很好的嗅觉，让它运转起来，然后才开始通过非常科学的方法来改进。我想这在机器学习中不断发生——先是手艺，然后是科学，两者都非常重要，只是处于流水线的不同阶段。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yeah, that's that's a great question. I think how it usually works is that it starts being craft. Uh people just try out many things and and they start building a mental model of what works and what doesn't. And over time we move to like from this like craft land uh to more science. science uh is or like more scientific approach is are rarely the ones that like first end up working. It's hard. It's very rare that uh you you take a really scientific approach and and you say um uh like this is the optimal the optimal thing to do and you do it and it just works. Like people just there's some sense of alchemy. people just have like a good flare for something and they make it work and then other people or that person uh starts trying to improve what we are doing by being very scientific. Um and I would say this this happens over and over um in uh in machine learning. Uh so first craft then science and both are really important uh but it's different stages of the pipeline.

</details>

**Matt Turk**: 说到评估（evals），这是一个巨大的话题。为什么评估一个模型最初就这么难？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. Let's talk about evals for a minute. Uh that's uh a hugely important topic. Maybe to start, why is it so hard to evaluate a model in the first place?

</details>

**Yann Dubois**: 随着模型变得越来越好，评估变得越来越难。这是因为我们要求模型完成的任务变得越来越通用，越来越**开放**（open-ended）。比如现在我说“给我建一个实现 X 功能的网站”。而在过去，我可能只会问“这个实现中是否有特定的 bug”，这很容易判断，因为我可以找一个人类指出所有的 bug，然后自动应用。而网站的任务很难知道什么是最佳答案，因为有很多好答案。这种开放性特征确实让评估变难了。

<details>
<summary>Original English</summary>

**Yann Dubois**: Evaluation has been harder and harder as models become better. Um and that's because the tasks that we ask to the model become uh more and more general um and more and more open-ended. So like now I maybe just say like build me a website that does X. Well before in the in the past I would just be like hey like is there a specific bug in this in in this like implementation that you have and it's like much easier to say whether there's a bug because I can I can extract I can know a I can have a human that says here are all the bugs that you have and then you can apply that automatically. um while the the website one is very hard to know uh what is like the optimal answer because there are many good answers. There are many good ways of of building a certain website. This open-ended nature of models really makes evals harder.

</details>

**Yann Dubois**: 另一个问题是，模型在特定维度上正变得比大多数人类更强，所以我们能在那方面评估模型的人越来越少了。此外还有一个文化上的问题，大多数人都想改进模型，认为训练模型是最好的方式，但实际上发现问题并确保我们能**量化改进**同样重要，如果不是更重要的话。但在学术界一直存在这种文化鸿沟，以前人们认为评估就是固定的基准测试。现在大家开始意识到数据是关键，而我认为大家还没完全意识到评估有多么大的影响力。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um there's also another issue is that models in specific axes are becoming better than the majority of humans and so we have fewer and fewer humans that can actually evaluate these models in particular axis. Uh so that's definitely a constraint. Another one to be honest is kind of cultural. Um most people want to improve the model and they they think that the best way to do that is kind of training the model when in reality finding issues and like making sure that we can quantify improvements is just as important if not more important. But there's always this like cultural gap. Um that was especially true I would say in the academic world up to like two years ago when evals were always fixed benchmarks were always fixed uh and even data sets were kind of always fixed maybe let's say four years ago um and there was like a mentality shift of like okay data is actually critical and now there's a lot of people working on data and I think eval was still not quite there people don't really fully everyone knows that it's important but like people don't really understand like how impactful it could be to work on evals

</details>

**Yann Dubois**: 实际上我在 OpenAI 的第一个项目，我进来时就说我想研究数据和评估，因为我知道没人研究这个，因此我知道研究这个会有超强的影响力。现在风向正在转变，但还不够快。评估很难的另一个原因是，你每次构建一个评估，实际上都是在构建一种构建训练数据集的方法。由于能力的泛化，你会变得非常擅长那个评估，而评估很快就会过时。但我认为“**模型作为评委**”（model as a judge）非常重要，因为随着模型变好，我们有了这种自我强化的循环，更好的模型成了其他模型的更好老师。

<details>
<summary>Original English</summary>

**Yann Dubois**: Um, so actually my first first product at opening I just came in and I was like I want to work on data and evals because I know that this is the thing that no one is is working on and as a result I know that's like super impactful to work on that. Um, and yeah the tide is shifting but like not fast enough. And is the pace of progress in model as a judge and AI evaluating AI is that is that moving as fast is that a distinct part of research or is that fundamentally the same idea or the same techniques? It's really fundamentally the same method. It's like nothing also most of the things that we do in in eval especially now that we have reinforcement learning could just be applied nearly exactly as is during training. So that's another reason actually why eval are so complicated is that every time you build an eval you actually build a way to build training data sets. Um so now you're going to optimize that training data set. Well not even if it's not that eval it's going to be the same type of data and now you're going to do super well because we have this generalization of of uh of capabilities that I was telling you about. You will learn that on that other data set and now you'll become really good at that eval and that eval will become u obsolete really quickly. Um so so that's also an issue with ULS. But yeah to come back to your question um the model as a judge it's really important and I think it's one one probably of the most important things because as we get like better models uh we have this self-reinforcing loop and we have this this like capability flywheel where better models become better teachers for other models. Um and this is really important for training but then you can also do the same thing for evaluation. So I a lot of my team works on that and I think it's really critical is to work on this uh module model as a as a judge kind of um uh framework.

</details>

### 未来展望：持续学习与“最后一公里”

**Matt Turk**: 当我们接近这次谈话的尾声，我想跳出来看。未来 12 到 24 个月，你认为事物会继续平稳进步，还是会发生某种不连续性？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. Fantastic. Um all right so as we get towards the end of this conversation I'd love to to zoom out a bit and get your sense for where things uh might be heading. Obviously, it's incredibly hard to make predictions on on AI uh you know, years out, but let's call it the next 12, 18, maybe 24 months. Is your sense that things are going to continue progressing or are we heading towards something that could feel more like a discontinuity?

</details>

**Yann Dubois**: 关于进步，我认为它总是在连续发生的。然而，**不连续感**是会发生的。三个月前在编程领域发生过，或者四个月前。我想现在这种感觉会渗透到每一个其他垂直领域——大多数人现在还没感受到像软件工程那样深刻的模型能力和实用性。所以这肯定会扩散到许多其他垂直领域。至于我预测下一次重大的不连续性是什么时候，我确实无法预测。

<details>
<summary>Original English</summary>

**Yann Dubois**: In terms of progress, as I was said before, it's I think it's always continuous. Now, the feeling of discontinuity will happen. It did happen three months ago with coding or four months ago with coding and I think that will happen now in every other domains like most people are not feeling uh the same way like the like kind of the capability of our model and the usefulness of our models the same way as like coding um and like software engineering is feeling right now. Uh so this will definitely permeate I think through many other verticals. Um now in terms of like capability bump in terms of let's say the the verticals that we're already looking at uh I think it will be more continuous um and they will not be there will never be uh big discontinuities like most of them are always local discontinuities but you zoom out and it always just feels pretty smooth. Um it's not always like this but like that has been the case most of the time and I can definitely not predict when is the next big discontinuity.

</details>

**Yann Dubois**: 我对**持续学习**（continual learning）非常兴奋。我认为我们还没真正破解它。我们有智能体内存类功能，但这肯定不是最终状态。如果你画一张图，x 轴是时间，y 轴是提供给用户的效用。现在，大多数模型在第零天投入公司时，可能比大多数新员工更有用，它们起步很高。但随着时间推移，它们基本上保持恒定，因为它们不会学习公司的特有知识。而人类学习得很快，随着时间推移会变得越来越高效。所以我们需要的是让模型在某个环境中工作得越久，就变得越有用。我对还没实现这一点感到惊讶，三年前 ChatGPT 发布时，我以为 OpenAI 在六个月内就能搞定，结果三年后我们还没做到。

<details>
<summary>Original English</summary>

**Yann Dubois**: I'm extremely excited about continual learning. I think we haven't quite cracked it. I mean, we have uh we have like Codex memories and that that is helpful, but it's definitely not like the the end state. Um I have a friend who always like tells me about uh kind again another type of plot that we should be looking at which is x-axis time y-axis utility that you provide to users and right now or like or or like usefulness basically of the models and right now actually most models at day zero if you just drop them in a company um arguably they are more useful than most new employees so they start higher at t0 Um but then across time they are mostly constant because they don't really learn kind of company knowledge. Uh they don't really learn like to be more efficient uh over time on on doing the things that they are doing. uh while humans learn really quickly and what is important is kind of this integral uh or like kind of the area under the curve um uh of these curves and as a result that I think like humans are still more useful uh in many cases um and that's why what we will need is to make like continual learning is to make the the this curve um now monotonically increasing over time uh and basically make models more and more useful the longer they work in a certain environment. So, I'm extremely excited about it. I'm actually surprised that we're not quite there yet. Uh, three years ago when Chip PT came out, I remember I was doing a startup with friends. Uh, and we were thinking about working on on continual learning and like personalization and and like memories in general. And we're like, ah, OpenAI is going to do that in in the next six months. Like they have all the data. They're going to figure it out and they have all the users and the models are going to learn super quickly from users. And uh, three years later, I don't think we're there yet.

</details>

**Yann Dubois**: 至于企业内部，关于模型是否会“吃掉”现有的外挂工具（harness），我认为垂直领域的工具在短期内非常重要。但从长远来看，每个人都应该在针对特定问题时做更多这方面的工作，因为没有好的工具，我们漏掉了太多可能性。如果我们将目前的模型固定下来，并配上优秀的工具，我想人们在每个领域都能感受到 **AGI**。但既然我们不会固定模型，会继续训练更好的模型，那么工具的形式也会不断改变。在垂直领域，“**最后的一公里**”总是有很大的空间，我会高度鼓励人们继续在那方面努力。

<details>
<summary>Original English</summary>

**Yann Dubois**: Yeah. Um I think harnesses can really improve the capability of a model right now. Um I think given that we seeing this this really fast progress in terms of capability uh I personally wouldn't push that much on the harness that unless it's like the harness is um is something for like very concrete goal that you're trying to achieve right now. Um so certain companies like if they are focused on like a specific vertical they want to go from this like 80% uh maybe reliability to maybe the like 85% and like harnesses will give them that and I think that's like very important but like they will they will they need to do it while knowing that they will have to retune that harness in the future and I think that's that's totally fine. Um if you try to have like a general harness to that will like sustain over time uh I don't think that will work the harnesses for specific uh domains as a short-term thing that you need to do. I think it's there will always be so much you can do in harnesses and if anything I think everyone should do more of that if they have a specific problem in mind because we're leaving so much on the table without a good harness. Uh, arguably if we just I think if we froze the models that we have right now and you really worked on the harness and like maybe like we also spend more time like training with like a great harness. Um, I think people would really feel the AGI in every single domain or could already feel that in every single domain. Um, but given that we're not freezing it and we're going to continue training better and better models, uh, I think the harness we don't really understand what the final harness will be and it's not and like it will always change. ... There's so much space left for this last mile in different uh in different verticals and uh I would highly encourage people to continue working on that and maybe one day when we stop making horizontal progress which I don't think is anytime soon maybe we will start focusing on that but yeah that's not what we're doing now.

</details>

**Matt Turk**: 好的，这听起来是一个非常乐观的结尾。非常感谢你，Yann。

<details>
<summary>Original English</summary>

**Matt Turk**: Okay, well that feels like a very uh optimistic note at least for the startup ecosystem to uh end up on. Thank you so much, Yan.

</details>

**Yann Dubois**: 太棒了，谢谢 Matt。

<details>
<summary>Original English</summary>

**Yann Dubois**: Great. Thanks, Matt.

</details>

**Matt Turk**: 大家好，我是 Matt Turk。感谢收听本期 Mad Podcast。如果你喜欢这一集，请考虑订阅、留下评价或评论，这能帮助我们邀请到更好的嘉宾。谢谢，我们下期再见。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks and see you at the next episode.

</details>