---
author: AI Engineer
date: '2026-06-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TNwJ1LMiENk
speaker: AI Engineer
tags:
  - reinforcement-learning
  - model-fine-tuning
  - tool-use
  - financial-analysis
  - data-quality
title: 停止盲目扩大模型：用强化学习与优质数据让4B模型超越235B模型
summary: Snorkel 开发者倡导者 Kobe Crawford 分享了一项研究成果：在金融分析的工具使用任务中，通过基于高质量领域数据的强化学习（RL），一个 40 亿参数的小模型成功超越了 2350 亿参数的大模型。文章强调了工具使用纪律对模型性能的决定性作用，并展示了低成本（不到500美元）微调的巨大潜力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Snorkel
  - UC Berkeley
products_models: []
media_books: []
status: evergreen
---
### 会议开场与互动

**Kobe Crawford**: 这是我在这场会议上要做的最后一场演讲了。所以，我已经感觉到了那种“啊，终于都结束了”的兴奋感。嗯，我知道我们现在也接近整个系列活动的尾声了。我是说，无论我走到哪里，我一直觉得这些会议能给我带来一些最强烈的高质量信息（highest signal）。所以，大家总体上觉得在这里得到了你们想要的吗？我只是很好奇，因为你知道，我们是 **Snorkel**，当我们提供赞助时，我们想知道大家是否从中得到了他们想要的，他们知道自己还会再来，因为我们希望下次还能继续赞助。我们想知道大家对此是否满意。那么，你们看到你们想看的东西了吗？是吗？

<details>
<summary>Original English</summary>

**Kobe Crawford**: This is the the last presentation I have to give this uh conference. So, I'm feeling already a little bit of the euphoria of like, "Ah, it's all done." Um I know we're we're at a uh at a uh also closer to the end of the whole sequence uh is hasn't been I mean I I keep finding these conferences to be like some of the highest signal that I get like wherever I'm wherever I go. So, how how generally is it people feel like like they're getting what they came for here? I'm just curious because like I you know we're we're Snorkel um when we we put in a sponsorship and we want to know that like people are getting what they want out of they know they're going to come back because we want to sponsor next time. We want to know people are happy about it. So, did did did you did you guys see what you wanted to see? Yeah?

</details>

**观众**: 是的。是的，非常棒。精彩。

<details>
<summary>Original English</summary>

**Audience**: Yeah. Yeah, really good. Brilliant.

</details>

### Snorkel 介绍与数据质量

**Kobe Crawford**: 精彩。嗯，那么，既然现在是3点45分，我就开始正式的演讲了。所以，我的名字是 **Kobe Crawford**。我是 Snorkel 的一名开发者倡导者（developer advocate）。我们称自己为前沿 AI 数据实验室（Frontier AI Data Lab）。我们现在正在做的主要事情，是从 Snorkel 成立以来一直在做的基于研究的工作开始的。我们一直致力于各种关于数据质量的工作，然后现在，我们关注的重点实际上是提供我们能够保证一定质量水平的数据集。我们非常注重、非常非常积极地确保数据是高质量的。而我们获得高质量数据的方法之一是，我们始终确保在整个过程中有某种专家参与（expert in the loop）。所以，我们有合作的专家贡献者，我们引入专业人士来提供他们的专业知识，以确保我们生成的数据是最高质量的。对于那些想要使用我们的数据来改进他们的模型，并以正确的方式完成这种“爬山”过程（hill climbing）的顶尖实验室来说，这就是我们在 Snorkel 所做的。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Brilliant. Um so, now that it is 3:45, I'm going to go ahead and start the the official thing. Uh so, uh my name is Kobe Crawford. Uh I'm a developer advocate at Snorkel. Uh we call ourselves the Frontier Data Frontier AI Data Lab. And the what we're doing right now our main thing is starting from the research-backed work that Snorkel's been doing since its inception. Uh we've been working on a variety of things about data quality and then then at this point now where where we're focused is actually providing data sets where we assure a certain level of quality. We're very attentive to being very very very motivated about making sure the data is high quality. And part of how we get to high quality is we always make sure to have sort of an expert in the loop as part of the process. So, we have uh expert contributors that we work with and we bring people in uh to provide their expertise to make sure that the data that we generate uh is of top quality. And then for the for the top labs that want to use our data to uh improve their models and get them get the hill climbing done uh in the right way, uh that's what we that's what we do at Snorkel.

</details>

**Kobe Crawford**: 正因为如此，正在进行的很多工作仍然是偏向研究的。这是一场讨论我们所做的一些工作的演讲，是我们研究团队完成的工作。这项研究的关键之一是，我们在研究如何将最优质的数据得到最佳应用，以及我们需要去哪里寻找完成这项工作的机会。所以，在今天这个特定的案例中，我们要讨论的是“停止让模型变得更大”。我的意思是，这是一个很好听、很吸引人的标题。当然，我们并不是真的说模型本质上不应该很大，但从广义上讲，关键在于有时我们会发现，将合适的数据应用于合适的问题陈述，可以获得巨大的收益。所以，这是我们要讨论的一个特定用例，是我们的研究团队发现的，并且是与 **RLLM** 团队合作完成的，那是加州大学伯克利分校（**UC Berkeley**）的一个研究小组。加州大学伯克利分校的团队，RLLM，Agentic 项目，他们的实验室在这个特定的工作上与我们进行了合作。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Um because of that, um you know, uh a lot of what goes on is uh still more research. And uh this is a a talk that's talking about some of the work that we did that our research team did. And um one of the keys in this research is uh that we're looking at uh how the best quality data can be best applied and like where it is that we need to be looking for where there are opportunities uh to get that done. So, in this particular case, talking about stop making models bigger. I mean, it's a nice punchy title. Of course, we don't really mean like models shouldn't be large intrinsically, but uh the point broadly speaking is that sometimes we find great wins to be had with the right data applied to the right uh to the right problem statement. So, this is something we're going to talk about a specific use case that we that our research team discovered and uh and in partnership with the RLLM team, uh which is a research group uh with a part of UC Berkeley. Uh and so, the UC Berkeley team over there, RLLM, the Agentic Project, their their lab partnered with us on this particular work.

</details>

### 研究目标：小模型超越大模型

**Kobe Crawford**: 那么，正如我所说，这个目标是让一个 **40亿参数**（4 billion parameter）的模型，在一个用于金融分析的工具使用任务上，表现超越一个 **2350亿参数**（235 billion parameter）的模型。所以，我们将从研究目标开始。然后我们将逐步探讨这个特定过程所使用的方法，接着讨论结果，我很高兴地报告我们得到了我们想要的结果。所以，这是好事。那么，有几个关于我们在这里讨论内容的快速背景设定。首先，当我们看到企业用例呈现出更大的复杂性时，显然，我们在人们做个人助手方面看到了爆炸式的增长。而当人们在企业环境中工作时，很多时候你仍然需要对如何实现某个东西做出更加受限的选择，并确保它是可靠的。当你寻找那些要在企业生产用例中完成的事情时，你几乎必须确保完成了很多安全和安保方面的工作。

<details>
<summary>Original English</summary>

**Kobe Crawford**: So, the goal this is the the as I said is making a 4 billion parameter model outperform outperform a 235 billion parameter model on a tool use task for financial analysis. So, we'll start with the research objective. And then we'll iterate in through talking about the approach that we that was used for this particular process and then talk about the results and um happy to report that we got what we were looking for. So, uh so so, good things to be had. So, couple of quick level setting backgrounds of the what we're talking about here. First is that as we see enterprise use cases uh take on some greater complexity, we have obviously we've got the massive explosion with people are doing in terms of personal assistance. And as people are working in the context of enterprise, a lot of times you still need a several more constrained uh choice about how to implement something and make sure that it's reliable. And like when you're looking for things that are going to be done uh for uh you know, enterprise production use cases, you kind of almost have to make sure there's a lot of safety and security things done.

</details>

**Kobe Crawford**: 所以，这些其他类型的优先级会融入人们通常想要做的事情中，我们看着这些事情说：“好吧，这些是人们拥有的企业用例。” 当人们试图解决让模型达到可以接受、作为生产服务实际部署的性能水平的问题时，我们经常看到人们会这样选择：“你知道，好吧，我们现在用这个没有得到我们想要的性能。我们干脆就直接换一个更大的模型。它会更聪明。它有更强的推理能力。我们就自然而然地期望重要的性能会提升，以匹配模型规模的增加和随之而来的更高推理成本。” 但在某些情况下，这可能并不总是正确的做法。所以，我们看到人们会说，“你知道，我们就直接弄个更大的模型。那就能解决问题。” 有时候，这也许并不完全是答案。在这个案例中，我们试图做的是提出：“我们难道不能使用一个较小的模型，然后通过适当的数据使用强化学习（**RL**），来产生我们所寻找的那种性能提升，并提供我们想要的应用程序功能吗？” 这就是这里的目标。

<details>
<summary>Original English</summary>

**Kobe Crawford**: So, these other kind of priorities and that that fold into what people typically want to do, we're looking at these things and saying, "Okay, well, these are the enterprise use cases that people have." And as people try to solve the problems of making the models perform at the level that makes it like acceptable for actually being deployed as a production service, um we see very often that people choose like, "Well, okay, we didn't get the performance that we wanted with this right now. We'll just drop in a larger model. It'll be smarter. It has greater reasoning skills. And we'll just sort of expect that the important performance will improve uh commensurate with the additional load of the size of the model and the the the greater inference cost that goes along with that." And in some cases that might not always be the right thing. So, we see people saying, "You know, we'll just get a bigger model. That'll solve the problem." And uh sometimes maybe that isn't quite the answer. In this case, what we're trying to do is to say, "Can't we take a smaller model and then use RL with the right data to yield the kind of performance gains that we're looking for and to deliver the kind of application functionality that we want?" And so, that's the target here.

</details>

### 企业部署与 Terence Tao 效应

**Kobe Crawford**: 同样，出于各种原因，成本、速度、安全性，以及这样一个概念：通常情况下，你从一个非常大的模型开始，制作你的概念验证（POC），让它运转起来，每个人都很高兴它能工作。然后就像是，“好吧，现在我们要做些什么来将它投入生产？” 你想推向生产，你想思考如何部署它。你需要把所有东西都保留在本地（on-premise）吗？你是否有能力自行部署和运行你的服务，这样你就不必依赖外部资源，也不用担心数据导出方面和数据控制的问题。特别是在金融数据和医疗保健以及其他类似领域的背景下，人们也不得不关注这些方面。因此，为了让较小的模型能够表现得和较大的模型一样好，我们觉得，在讨论金融分析的工具使用这个特定用例中，强化学习（**RL**）是进行这类训练的正确时机。你谈论的是改变行为。所以，这更像是一种行为上的事情。对于改变行为来说，RL 往往比，比方说你要改变模型内部的核心数据和知识要更好。这是一种关于我们如何处理它的直觉，这也是这里正在进行的一部分。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Uh and again, for these various reasons, cost, speed, security, and then the the idea that in general, you know, you start with a really big model and make your POC and make it work and everybody's happy that it works. It's like, "Okay, now what do we do to productionize it?" You want to roll to production, you want to think about how you're able to deploy that. Do you need to keep everything on premise? You do do you have the ability to deploy and run your service yourself so that you don't have to have external dependencies and worry about the data export aspects and data control. Especially in the context of financial data and health care and other domains like that, people have to be concerned about those aspects as well. So, for getting a smaller model to be able to perform as well as larger models, uh we feel like in the particular case of talking about tool use for financial analysis that RL is the right time to to be uh making the kind of training. You're talking about like changing the behavior. And so, that's kind of more of a behavior thing. The RL's kind of better for behavior than say you're talking about like changing the core data and knowledge that's inside of that. So, that's that's an intuition about like how we've approached it and that's part of what's going on here.

</details>

**Kobe Crawford**: 所以，一个更大的模型，有时它更像是在用大锤砸核桃（taking a sledgehammer to crack a walnut）。它就像仅仅添加所有这些能力就是这样的。我们合作的 RLLM 团队，他们谈到了这个，他们对它的描述是 **Terence Tao 效应**。陶哲轩（Terence Tao），著名的数学家，我忘了得过什么奖项之类的，但他以在各个领域的数学方面都非常聪明而闻名。因此，他可以应对和处理任何类型的数学问题。但那么多的聪明才智，可能未必是一个金融分析师实际需要的。他们不需要知道所有类型的数学。他们不需要做潜在狄利克雷分布（Latent Dirichlet Allocation）算法之类的东西来讨论，你知道，做个 SQL 查询，获取一些数据，然后做些加法和减法，对吧？所以，那种认为你必须总是用一个更聪明的模型来做某事，或者进行更深层次的推理才能把事情做好的想法，正是我们在这里要挑战的。

<details>
<summary>Original English</summary>

**Kobe Crawford**: So, a larger model, sometimes it's more like uh taking a sledgehammer to crack a walnut. It's like just adding all of this capability is like this. And the RLLM team uh that we worked with, they talked about this and their description of it was the Terence Tao effect. Uh uh Terence Tao, the famous mathematician who's uh uh I forget what awards he's won and whatnot, but well known for being, you know, generally brilliant about mathematics across the board. And therefore, like could approach and manage any kind of mathematical problem. But that much brilliance might not necessarily be what a financial analyst actually has to have. They don't have to know all the kinds of math. They don't have to do latent Dirichlet algorithm stuff uh to talk about, you know, doing a SQL query and getting some math getting some some data's back and then, you know, doing some addition and subtraction, right? So, the the idea that you must always get to a much smarter model to do something or deeper reasoning to get something done well uh is the thing we're challenging here.

</details>

### 大模型的失败与幻觉

**Kobe Crawford**: 那么，这里有那个 **2350亿** 参数的 quant 3 模型对我们在构建的这个环境中的问题的回答。我稍后会详细谈谈这个环境。但我指出这一点，是为了展示这里有一个推理模型，一个更聪明的模型，以及它在需要实际使用工具的背景下的反应。所以，对于“YouTube 广告收入从 23 年到 24 年的同比增长率是多少？”这个问题，它生成的回答，是从发起一个查询以寻找一些现有值开始的，但它选择的查询是指向一个不存在的表。这个表不存在。它并没有实际检查环境，也没有检查工具来找出它可以查询哪些表。它只是在没有这样做的情况下抛出了一个查询。嗯，所以，那个表不在那里，也没有得到任何返回结果。它又猜了一次。还是没有得到任何返回。然后，在这两次尝试都没有得到任何结果之后，它退回到直接**幻觉出一个答案**。所以，就得出了这个幻觉出的答案。它完全是，你知道的，不知道是权重让它这么说的，但这就是输出的结果。而且，你知道，它不是很有用。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Um so, here is that 235 billion quant three model responding to the question in this environment that we built. I'm going to talk about the environment a little bit more in detail later. But I point this out to sort of show here's a reasoning model, a smarter model, and its response in the context of needing to actually use tools. So, the response that it got that it generated to the question, "What is the year-over-year growth rate of YouTube ads revenue from '23 to '24?" began with uh making a query to find an existing uh some values, but they the query it chose was to a non-existent table. The table didn't exist. It didn't actually inspect the environment and inspect the tools to find out what tables it could query. It just threw a query out uh without doing that. Um so, the table it wasn't there and didn't get anything back. It guesses again. Still doesn't get anything back. And then having not gotten anything back in either of those two uh attempts, it falls back to just hallucinating an answer. And so, out comes this hallucinated answer. It's completely, you know, don't know what the weights told it to say, but that what came out. And, you know, it's it's not very useful.

</details>

**Kobe Crawford**: 因此，尽管这个模型在推理方面非常不可思议，比如比一个更小模型在推理上要好得多，但这种更强的推理能力在它需要使用工具时并没有帮到它。我们还会带着同一个问题，回到我们微调过的那个只有 **40亿参数** 的模型上。你们会看到区别的。稍后我们再多谈谈这些区别。所以，先把这事放一边。我们还会回来的。我们会再次看到那个同比增长的问题。所以，这就是我们正在谈论的。再次总结一下，尽管它拥有它所具备的推理能力，但在工具使用上缺乏纪律（no discipline in tool use）。

<details>
<summary>Original English</summary>

**Kobe Crawford**: So, even though the model is incredible in terms of like much better at reasoning than a much smaller model would be, uh that greater reasoning did not help it when it needed to use the tools. We're going to come back to the same question again against the model that we fine-tuned that's only 4 billion parameters. And you're going to see the difference. We'll talk a little bit more about those differences later. So, put a pin in that. Come back. We'll see that that year-over-year question from come back. So, here, this is what we're talking about. Summarizing it again, no discipline in tool use even though it has all the the abilities to reason that it has.

</details>

### 高质量数据生成与强化学习微调

**Kobe Crawford**: 接下来谈谈我们针对这次尝试做了什么，为了使用 RL 让更小的模型表现出色。嗯，第一件事是生成一个高质量的数据集。在 Snorkel，我们通常的做法同样是让专家参与其中（experts in the loop）。我不知道我刚才有没有说过，我现在再说一遍，但我认为我没说过。对于我们处理的数据，我们有专家参与。我们生成数据和处理它的方式是，我们有一个内部使用的平台，用于处理各种事务。我们寻求专家在各种任务和主题上的工作和支持。所以，如果我们需要一个已经在金融分析领域的人，那么我们就找到他们，把他们拉进来。对于他们专业领域的专业知识，我们会与具有博士水平的人合作。当然，还有那些在行业中深耕多年，非常了解该领域的人。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Moving forward to then what we did for this uh attempt to use RL to make the smaller model work well. Uh the first thing is to generate a high-quality data set. Um at Snorkel, our general approach is again to have experts in the loop. I don't know if I said I say again now, but I don't think I said it. We have experts in the loop for the data that we do. Um the way we generate data and the way we work on it is we have a platform that we've used internally for interacting with things we we solicit the work and support of experts on various tasks and various topics. So, if we need somebody who is in the financial analysis space already, then we get them and pull them in. We'll work with people at the PhD level for the their domains of expertise. Uh and also, of course, people who are deep in the industry and have been working for some time and then know the space well.

</details>

**Kobe Crawford**: 做这件事的过程，正是我们放在首位强调的事情之一，这就是我们在 Snorkel 进行数据生成的工作方式。一般来说，这自然可以与其他类型的东西结合起来。但这就是我们真正关键的地方，就我们希望在强调数据质量作为核心要素方面所做的事情而言。所以我们有了数据集。然后我们继续，确保完成了一个验证步骤，以确保从该数据集中定义的任务实际上是适合该任务的，并且实际上是好任务，就是说，就能够被查询而言。你知道，你确信你能从中得到你想要的结果。并且我们应该能够得到我们正在寻找的、可验证的答案。所以我们执行了所有的验证步骤，确保在这方面一切都是正确的。这也是你要拼凑数据集，并让它准备好供使用的一部分。我再说一遍，数据质量对我们来说是一个非常重要的点。所以我们真的确保这是关键。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Um The process of doing that that's like one of the things that we put an emphasis on is how we work at Snorkel for our data generation. And then broadly speaking, naturally that can be augmented with other kinds of things. But that's what we're really key about like what we want to do in terms of emphasizing quality as a core element. So we have the data set. And then we go through and make sure there's a verification step done to make sure that the tasks that are defined from that data set are actually appropriately fit fit it to the task and are actually like good tasks that they do in terms of like the it can be queried. You know, you you know that you're going to get the results that you need from it. And that that we should be able to have a verifiable answer that we're looking for. So we do all the verification steps to make sure that everything is correct on that front. And that's another part of what means to you know, put together the data set and have it ready for use. Data quality again is a big emphasis for us. So we really make sure that's a the key.

</details>

**Kobe Crawford**: 然后，就是时候用它做 RL（强化学习）了。我们做这件事的方式……其实就技术现状而言，没有什么出人意料的东西。**GRPO**。同样，我们从一个 40 亿参数的模型开始。然后我们使用的环境是 RLLM 框架，还是通过与加州大学伯克利分校的合作，通过该框架的开发者。我们有我们构建的 **FinQA 环境**。我待会再详细讨论这个环境的细节。但这件事情能够在一个 21 小时的任务中完成，运行该任务的总成本是每次运行不到 **500 美元**。所以，嗯，RL 并不一定是一件非常昂贵的事情，同样能够获得不可忽视的性能提升。如果你已经在处理想要自己托管的模型，如果你已经在思考你希望如何能够做这些基于本地（on-prem）解决方案的事情，或者你在用更小的模型做事，而你还没有认为自己可以按照你想要的方式改进模型，那么这就是一个行动号召，你实际上是可以的。使用 RL 将你想使用的模型提升到你需要的性能水平，这实际上是一件非常容易处理的事情。即使 Andrej Karpathy 不喜欢它。

<details>
<summary>Original English</summary>

**Kobe Crawford**: And then it was time to do our RL with it. And the way we did our the way that this was done we're talking about very few surprises in terms of like you've seen the state of the art in this in this space. GRPO Again, we started with a 4 billion parameter model. And then the environment that we used the RLLM framework again through the UC Berkeley partnership through the the developers of that framework. And we have our a FinQA environment that we built. And we're going to talk a little bit more about the details about that environment in just a moment. But then this is something that was able to be done like in a 24 21-hour job and the total cost of running that job was under $500 per run. So um RL is not have to be a very expensive thing to be able to get non-trivial performance gains. And if you're already working about working on working with models that you want to host yourself, if you're already thinking about like what you'd like to do to be able to do things we have on prem kind of solutions or things where you're doing it with a smaller models. And you aren't already thinking that you can improve the models the way you that you want, then this is like a call to action that you actually can. That it's actually a very tractable thing to get a model that you want to work with actually up to the performance levels that you need using RL. Even if Karpathy doesn't like it.

</details>

### FinQA 环境与评估

**Kobe Crawford**: 那么，我们的 FinQA 环境是我们构建的。它被设置用来承载我们在这里提问的各种问题。它提供了一组特定的工具。它的设置将所有东西都内置在环境中。所以没有任何外部依赖可能会……你知道的，在某个你无法访问的远程数据中心里。所以当你部署这个环境时，它是完全自包含的（fully self-contained）。可以推广开来，如果你以前用过 Harbor，或者你用过 OpenEnv，你就会熟悉使用这种环境的套路。这是我们实际构建和发布的一个环境。它可以在 **PrimeIntellect** 的基础设施上使用。所以有人可以直接在 PrimeIntellect 那里加载它。也在 **OpenEnv** 上，并且实际保存在了 GitHub 的 OpenEnv 仓库中。然后 OpenEnv、PyTorch 团队和 Hugging Face 团队联手，将这些托管在 Hugging Face spaces 中。所以如果你想看看它们，看看如何把它们应用到你的需求中，这些东西是很容易获取和找到的。并且，再次强调，像开始使用 RL 如今实际上已经越来越容易了。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Um So our FinQA environment is something that we built. It's set up for being able to host the kinds of questions that are being done here. It provides a specific set of tools. It's set up where like everything is built into the environment. So there's no external dependencies that are that might be you know, in some remote data center that you don't have access to. So when you deploy the environment it's fully self-contained. Kind of roll out that if you worked with something like Harbor before or if you worked with like OpenEnv, you're familiar with the same thing about using an environment like this. And this is an environment that we've actually built and published. It's available on PrimeIntellect's infrastructure as well. You can so somebody can load up right there at PrimeIntellect. Also on OpenEnv and and and actually saved into the OpenEnv repo on GitHub. And then the OpenEnv the PyTorch folks and and Hugging Face folks team up and host these in Hugging Face spaces. So these kinds of things are accessible and easy to find if you want to take a look at them and see how you might take take them apply them to your needs. And then again like getting getting started with RL is actually easier and easier these days.

</details>

**Kobe Crawford**: 我们设置了 FinQA，其中有 **290个样本**。我们还有更高级的 **79个样本**，称为 FinQA Reasoning（FinQA 推理），它需要多表查询（multi-table queries）。因为需要跨表进行推理才能完成，所以我们已经确定这些是更难的任务。所以我们在那个环境中实质上构建了两个基准测试（benchmarks）。这就是我们如何完成这项工作的设置。接下来，我们将探讨基于我们刚才在这个 40 亿参数模型上做的 RL，我们所得到的评估（evals）和结果。

<details>
<summary>Original English</summary>

**Kobe Crawford**: We have the FinQA set up where we have 290 samples that way and we have our more advanced 79 samples called FinQA reasoning that requires multi-table queries. And so there's enough enough of the reasoning that has to be done across that to make that we've we've identified that these are harder tasks. And so we have like essentially two benchmarks that are built inside of this environment. So that's the set up of like how we get this done. We're going to go about talking about the evals and the results that we got working with this now given the RL that we just did on this 4 billion parameter model.

</details>

### 模型性能对比与意外发现

**Kobe Crawford**: 所以，我们做到了。在经过那个 RL 训练循环之后，它的表现比那个 2350 亿参数的模型还要好。在 Pass@1（一次通过率）方面的表现，从解决问题的百分比来看，基本上是以前的两倍。所以，这个 500 美元的循环带来了一个非常显著的提升（significant uplift）。同样，合适的数据集是真正的关键。你希望问题和答案实际上是那些能够真正帮助模型学习的东西。但有趣的是，对于模型需要学习的东西来说，到底什么是重要的。

<details>
<summary>Original English</summary>

**Kobe Crawford**: So we did it. It's performs better than the 235 billion parameter model with that RL training loop. And the performance in terms of pass at one was essentially double of what it had been percentage-wise in terms of like solving problems. So it's a very significant uplift that was done with this $500 loop. And again, the right data set and and is really a key. You want to get the questions and answers to be actually things that are really going to help the model learn. But what is also interesting is what was important about what the model needed to learn.

</details>

**Kobe Crawford**: 所以，给你们一点体验，看看那个微调过的 40 亿参数模型在行为方面是怎样的。如果你还记得我们之前提到的，那个 2350 亿参数的模型在不知道表是什么的情况下尝试了一些查询。什么也没找到，然后幻觉出了一个答案。这个在数据集上进行过微调的 40 亿参数模型尝试查询一个表，但它实际上首先通过使用 `get_table_names` 工具发现了这些表。这个工具同样存在于另一个模型的环境中，但它只是选择不去尝试。所以它做的第一件事实际上是通过查询来弄清楚它有哪些表可用。这已经是一次胜利了。好了，第二件事是，从那开始，它继续实际检查模式（schema）。“让我找出那张表里有什么，这样我就知道如何构建正确的 SQL 查询了。” 所以它使用了 `get_table_info` 工具来获取信息，从而知道该查询什么。

<details>
<summary>Original English</summary>

**Kobe Crawford**: So just to give you a little flavor of like what that 4 billion parameter model looks like in terms of like how it behaves. And if you recall what we talked about earlier, the 235 billion parameter model tried some queries without knowing what the tables were. Didn't find anything and then hallucinated an answer. This 4 billion parameter model having been fine-tuned on this data set tries a table and actually first discovers the tables by using the tool get table names. The tool existed for the other model as well and it just didn't choose to try it. So the first thing it did was actually query to find out what tables it had available to it. So that's already like win. All right. The the second thing is then from there it went on to actually inspect the schema. Let me find out what's in that table so I know how to make the right SQL query. And so it's like does get table info to get the information back to know what to query it.

</details>

**Kobe Crawford**: 随后，它运行了一个查询。实际上遇到了一个错误。它实际上请求了 revenue（收入）列。但那个列实际上并不是表中数据的一部分。遇到那个错误后，它实际上修正了。它进行了自我修正（self-corrected）。它观察到了错误，通过实际修正并找到它需要的确切列来对那个错误做出了反应。所以你看到了它学会了如何进行错误修正，以及在最开始使用工具来发现正确信息的能力。所以在两者之间，这些行为是它在这些问题上取得成功的真正关键。而这其实是关于模型在哪方面失败的一些不太直观的事情。现实是，它需要做的是，而在这里它获得了正确答案。现实是它需要做的是学习如何使用工具。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Following that it runs a query. Actually ran into an error. It actually asked for the revenue column. But that column was not actually a part of the the data in the table. Given that error it actually corrected. It self-corrected. It observed the error, responded to that error by actually correcting to find the actual column that it needed. And so you're seeing both the error correction that it had learned how to do as well as the use of the tools to discover the right information in the first place. So between those two, those behaviors are the real keys to succeeding at these questions. And this is actually something like maybe not quite intuitive about like where it is that the model was failing. The reality is that what it needed to do and here it is getting the correct answer. The reality is what it needed to do was to learn how to use tools.

</details>

**Kobe Crawford**: 与此相关的还有两件有趣的事情，这比较有趣，而且在我们的情况下也非常有用且好。我们在开头谈到的训练数据，整体数据集中包含了单表问题和多表问题。作为评估研究的一部分，他们说的一件事是，“让我们来看看，如果我们只用单表问题训练，或者在其中混合多表问题，所以这两种类型的完整数据集，又或者尝试做一些课程学习（curriculum learning），实际上从单表开始，让模型稍微攀升一点，然后再逐渐添加多表问题。” 结果发现，**只用单表数据训练（single-table only training）**，实际上是为这类问题带来了最大的提升。所以这是一个非常好的、令人愉快的意外发现。

<details>
<summary>Original English</summary>

**Kobe Crawford**: Couple interesting things that go along with it that are more more fun and also really useful and good for our situation here. The training data that we talked about at the beginning, there were single-table questions, multi-table questions included in the overall data set. And for as part of the evaluation study, one of the things that they said was like let's take a look and see if we train with single table only, train with multi-table mixed in so the full data set across both types, or try to do some curriculum learning and actually start with single table, let the model kind of climb a bit and then progressively add multi-table. And it turned out the single-table only training was actually the one that yielded the greatest uplift for these kinds of questions. So that was a nice pleasant surprise.

</details>

### 工具使用纪律与量规（Rubrics）

**Kobe Crawford**: 另一件令人惊讶的事情是，即使只用单表进行的训练机制是最好的训练机制，我们在那些包含多表问题的更难的基准测试上看到的模型性能提升，在百分比改善上也是一个类似的翻倍。因此，在 FinQA Reasoning 问题集中的难度更高的多问、多表问答，在此次训练后也看到了从 **13.9% 到 26.6%** 的百分比跃升。因此，同样非常有趣的是，工具的纪律性（tool discipline），仅仅知道如何使用环境中的工具，结果在让这些模型能够更好地执行它们需要在该领域完成的任务方面，这成了比其他任何东西都更重要的事情。所以，结果是问题不在于推理，而是在于工具的使用。我们只关注单步（single step）来获得最佳性能。我们成功修复了那个核心失败模式。并且鉴于修复了那个核心失败模式，结果模型在性能提升泛化到其他问题集方面也变得更好了。

<details>
<summary>Original English</summary>

**Kobe Crawford**: And the other surprising thing was that even though the single-table only training regime was the best training regime the uplift that we see in terms of the model's performance on that harder benchmark that is a that has multi-table questions was a similar doubling in in in percentage improvement. So the harder multi-question multi-table Q&A in the FinQA reasoning question set also saw 13.9 to 26.6 percentage jump after this training. So interestingly enough again, the tool discipline, just knowing how to use the tools that are in the environment turned out to be a bigger deal than anything else in terms of how to make these models actually get better at what they need to do in this space. So turned out it wasn't the reasoning that was the issue. It was the tool use. We focused only on single step for the best performance. And we're able to fix that core failure mode. And given that core failure mode being fixed, it turned out that that then made the model better in terms of like the improvement generalizing to other question sets.

</details>

**Kobe Crawford**: 所以这意味着，从这之中得出的关键启示是，有时这个想法是要找到真正存在问题的具体行为。我要回到我们在 Snorkel 所做的事情，我们研究团队最近谈论的很多事情之一就是，将**构建量规（rubrics）**作为我们评估（evals）的一部分。通过将模型响应的正确或错误细分为一整套不同的可以回答的问题，然后观察那些个别的问题，你就可以开始利用量规来发现并直观地找到实际的问题在各种可能的地方出在哪里。所以，你不仅能在最后知道“是”或“否”（这对于 RL 部分来说是很好的，你可以利用那个进行实际的 RL 循环），你还能使用量规帮你分析，看看哪些是你真正想生成数据集来帮你培养的行为。因此，你可以根据量规提供的更丰富反馈，来决定你需要哪些数据集，或者你想要使用哪些数据。然后对于 RL 循环，GRPO 通常只与一个简单的单值输入交互，这是它工作方式的一部分。

<details>
<summary>Original English</summary>

**Kobe Crawford**: And so that means like that's the key to talk to take away from this is that sometimes the the idea is to find the specific behavior that's really the problem. And one of the things that I would go back to what we do at Snorkel, one of the one of the things that our research team has been talking about a lot lately is building rubrics as part of our evals. And then those rubrics by breaking down the rightness or wrongness of a model's response into a full list of different questions that can be answered. And looking at each of those individual questions, you can then start to use the rubric as as a way to find and intuit like and find where the actual problem is among all the multiple possible arenas. So instead of simply knowing yes or no at the final, which is good for the RL part you can use the rubric to help you do an analysis of what are the behaviors that you want to actually generate data sets to help you with. So you make decisions about what which data sets you need or which data you want to work with based on what you see coming out of the richer feedback that the rubric gives you. And then the RL still gets a single value or so GRPO just usually works with a single value. That's it. That's part of how it works. So you use that for the actual RL cycle.

</details>

**Kobe Crawford**: 所以这就是我们用它所做工作的总结。我们认为这是一个非常有趣的结果，需要被知道。而且，你知道的，同样地，针对恰当的问题或寻找正确的疑问来寻找解决方案的机会真的很有帮助。这里的这个链接是指向我们关于此发布的一篇博文。所以如果你对这项特定研究的细节有疑问，并且你想了解更多关于它的信息，你可以深入查看。它还链接到了加州大学伯克利分校 Agentyca 团队的一篇合作博文。所以他们的帖子也有额外的信息，你可以从他们那里看到，这，你知道的，是我们想谈论的重要事情。感谢大家的时间，我不知道我们还剩多少时间提问，或者到底有没有。我们进度怎么样？我们是不是已经到时间了？看来是的。好吧，抱歉。好的，所以我很抱歉我们没有提问时间了。我……

<details>
<summary>Original English</summary>

**Kobe Crawford**: So that's the that's the summary of what we we did with that. We think it's a really interesting result to know. And you know, again the opportunity of what you can do with the solving the right questions or the right problems really helps. This link here is to a blog post that we have about this. So if you have questions about the details of this particular study and you want to see more about it, you can drill down within that. It also links to a partner post from the Agentyca team over UC Berkeley. So their post also has additional information you can see from them and and this is you know, the significant thing we wanted to talk about. So thank you for your time and I I don't know how much time we have left for questions or not. How are we doing? Are we already at time? Looks like it. Yeah, sorry. Okay, so I'm sorry we don't have questions. I'll

</details>