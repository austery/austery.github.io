---
author: The MAD Podcast with Matt Turck
date: '2026-04-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Bo19sXssYXI
speaker: The MAD Podcast with Matt Turck
tags:
  - self-improvement
  - continual-learning
  - transformer-architecture
  - image-generation
  - model-evaluation
title: AI正在构建AI：Google DeepMind的Mostafa Dehghani访谈
summary: 本期访谈深入探讨了AI前沿研究的多个热点，包括AI模型如何通过递归式自我改进实现自动化构建下一代AI，以及持续学习如何彻底改变企业数据管道和RAG系统。Mostafa Dani还分享了他在Transformer、Vision Transformer和多模态模型（如Gemini系列）方面的重要贡献，并对AI领域的未来发展和挑战提出了独到见解。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google DeepMind
  - OpenAI
products_models:
  - Gemini
  - Transformer
  - Universal Transformer
  - Vision Transformer
  - Nano Banana
media_books: []
status: evergreen
---
### AI的自我构建与循环思维

**Matt Turk**: 很多人没有意识到，这已经是正在发生的事情，尤其是在过去的几个月里。几乎在每一个实验室中，新一代的**模型**都大量使用前一代的模型来构建。目前缺少的是**长周期**和**完全自动化**，我们正在超高速地朝着这个方向前进。一旦我们实现了完全自动化，我们就可以闭合**自我改进**的循环。我们已经摆脱了改进这些模型的人工瓶颈，我预计这种发展将再次带来巨大的飞跃。我是Matt Turk，欢迎收听Matt播客。今天我的嘉宾是**Mustafa Dani**，**Google DeepMind**的顶级AI研究员，也是过去十年中一些最具影响力的**架构突破**的核心贡献者，包括**Universal Transformers**、**Vision Transformer**和原生**多模态**的**Gemini**系列。在本期节目中，我们将深入探讨当前前沿AI的热点，包括AI在循环中思考的实际含义，以及**递归式自我改进**的即时时间表——AI自主构建下一代AI。我们还将深入探讨**Nano Banana 2**的图像生成技术演进，以及**持续学习**如何彻底颠覆目前企业数据管道和**RAG系统**的构建方式。请享受与Mustafa Dani的精彩深度对话。

现在AI研究中最热门的概念之一似乎是“循环”的概念。所以我想这是一个有趣的开始。模型将不再通过变得更大，而是通过递归思考来改进。这到底意味着什么？

<details>
<summary>Original English</summary>

**Matt Turk**: Most of the people don't realize that this is like already happening, especially over the past few months. In almost every lab, the new generation of the models are built heavily using the previous generation of the models. What is missing right now is long horizon and full automation and we're moving to that direction super super fast. The moment that we have this full automation, we can close the loop of self-improvement. We just got rid of the human bottleneck for improving these models which I expect to see a huge jump again from such development. Hi, I'm Matt Turk. Welcome to the Matt podcast. Today my guest is Mustafa Dani, a top AI researcher at Google DeepMind and a core contributor to some of the most influential architectural breakthroughs of the last decade, including universal transformers, the vision transformer, and the natively multimodal Gemini family. In this episode, we unpack what's hot in Frontier AI right now, including what it actually means for AI to think in loops and the immediate timeline for recursive self-improvement, where AI autonomously builds the next generation of AI. We also dive into the technical evolution of image generation with Nano Banana 2 and why continual learning could completely disrupt how enterprise data pipelines and rag systems are built today. Please enjoy this fantastic deep dive with Mustafa Dani.

One of the hottest concepts in AI research right now seems to be the concept of loops. So I thought it'd be a fun place to start. This idea that models are going to improve not by being bigger but by thinking recursively. What does that mean exactly?

</details>

**Mustafa Dani**: 循环无疑是几乎所有实验室都在投入的最热门的活跃领域之一，它在不同层面都有操作。在微观层面，我们基本上是在**推理**时使用循环来进行测试和计算等。而在更高层面，它基本上是我们在这些模型开发过程中所拥有的循环，我们称之为**自我改进**。如果我非常简单地来解释它，这实际上只是我们几十年来一直在延续的趋势的延续。想想经典的**机器学习**，人类必须坐下来手动设计**特征**，你必须决定模型实际关注什么，然后**深度学习**和**神经网络**出现了，它们说“好吧，让我们去掉那些，让模型自己找出**表示**”。那确实是一个大问题，我们以某种方式消除了一个巨大的人工瓶颈和人为偏见，然后，我们不再只是设计架构，我们开始**学习**它们。我们不再像过去那样精心策划每一个**训练信号**，而是转向了数据驱动的方法，让数据说话。而自我改进以及这种融入开发中的循环，只是朝着同一个方向迈出的下一步。它的核心思想和重点在于，你正在消除改进这些模型的人工瓶颈和偏见。现在，就像你说的，人类不再需要手动设计特征，我们也不希望人类每次模型需要改进时都参与到循环中。我认为这基本上是开发方面的问题。所以，它不是根本性的新事物，它只是同一个故事的新篇章。我认为每次我们消除人类在这个过程中的判断时，我们都克服了一个瓶颈。我想说，这种自我改进和开发循环是在最高层面实现这一点的，即改进这些模型。如果你想深入了解循环的更详细层面，我们可以讨论增加这些模型的测试和计算量的方法，以及我们如何让这些模型在特定问题中循环处理它们的过程，以完善它、思考它。我认为最熟悉的形式就是**思维链**，让模型用额外的**token**思考，这超出了这些。你可以想到不同的想法，就是让模型增加针对任何特定问题的计算量，比如，如果我有一些**虚拟token**，它们可以用来作为读写磁带，以便你了解，重新验证我所做的事情，并回顾我正在不同步骤中进行的工作或过程，并了解，你知道，已经完成了什么，接下来要做什么，甚至像**负稀疏性**，它基本上是多次重复使用模型的一部分。这种新的循环方式也被证明非常非常有帮助，主要是因为你只是让模型在困难的问题上投入更多的计算。

<details>
<summary>Original English</summary>

**Mustafa Dani**: Definitely one of the topest active areas for almost every lab to invest in looping and and it has like operation at different levels. The one that is on on the uh on the micro level is basically the the the the looping that we use like architecture or at inference time for test and compute and stuff like that. And then at a higher level is basically the loop the the loop that we have over the development of these models which is basically we refer to to it as uh self-improvement. If I want to put it like like very like like let's talk about self-improvement as as like this general concept, right? If I want to u put it like very simply, it is really just the continuation of the trend that we've been like writing for decades, right? And uh and uh think about it in classical machine learning. humans had to sit down and manually engineer the features and uh you had to decide like what the model actually uh paid attention to and and deep learning and neural network came along and and they said okay let's just remove that let the model figure out the representation itself and um that was actually a huge deal and and we somehow removed a massive human bottleneck and inhuman bias and then like further uh and instead of just like designing architecture we started learning them too. uh instead of curating like you know every piece of training signal uh we scale to kind of basically datadriven approaches and let the data speak and uh the self-improvement and and this like loop into development is just the next step in in in the same direction and the whole idea and the whole point of it is you're removing the human bottleneck and bias from improving these models right and now uh like you say that okay not not just human doesn't have to handcraft features anymore for but also we don't want the human to sit in the loop every time that the model has to to get better and and I think that's basically on on the um on the development side. So it's not radically new it's the same story just a new chapter of the same story and I think every time that we removed human from uh like human judgment from this process we kind of got over a bottleneck I would say like this self-improvement and looping over the development is kind of like doing that at the highest level which is basically improving these models. If you want to go to more detailed uh level of looping, we can we can talk about ways of increasing test and compute for these models and how we let these models to loop over their process within a specific problem to to refine it to to think about it and uh like I think the the most familiar form is just like chain of thought and and letting the model to think with extra tokens that's beyond that and and you can think about different ideas is that you let the model to increase the compute for for any specific problems like what if I have uh like dummy tokens that that they can use as like read and rot tape to kind of like you know reverify what I've done and and go through the the the solutions or the process that I'm like doing over over different steps uh and and understand you know like what what what has been done growing uh what has to be done next or even like you know negative sparity which is basically re reusing part of the model multiple times And um this sort of new pink is also like been shown to be super super helpful uh mostly because you just let the model to to throw more compute on on a a difficult problem.

</details>

### 递归式自我改进 (RSI) 的现状

**Matt Turk**: 所以这是推理时的自我改进。我想你之前提到过，还有一个更大的概念，也许更像**科幻**，但它似乎正在迅速成为现实，那就是**递归式自我改进**（RSI）的概念。这似乎是很多人都在谈论的，我想几周后就会出现一堆关于它的论文。那么，递归式自我改进到底是什么概念？

<details>
<summary>Original English</summary>

**Matt Turk**: So that's self-improvement at inference time. I think you alluded to earlier there is um also a bigger concept that's maybe u I guess more science fiction except it seems to be becoming a reality very quickly which is this concept of um recursive self-improvement or or RSI that seems to be um what a lot of people are talking about I think is coming up in a in a few weeks and there's a bunch of papers focused on that. So what what is that what is recursive self-improvement as a concept?

</details>

**Mustafa Dani**: 这很有趣，因为你把它说成有点像科幻场景，即这些模型实际上正在改进自身，这确实如此。因为几年前，当你想谈论这个问题时，你只需在会议上写一篇**展望论文**，然后在非常高的层面讨论它。但是如果我们现在去看看正在发生的事情，它已经在很大程度上发生了。很多人没有意识到，这已经发生，特别是在过去的几个月里，几乎在每个实验室中，新一代的模型都大量使用前一代的模型来构建。我想这基本上是各地的情况。它还没有完全自动化，但方向非常明确，很容易想象，我们会达到完全自动化的境地。这些模型将自我改进，并不断从世界中学习，它也与**持续学习**以及我们尚未达到最先进水平的其他概念有关。但如果有人来说，“哦，你知道，我有一个想法，让一个模型能够实时计算梯度并更新其权重”，这听起来就非常正常，你知道，这不再是“哇，这是一个多么惊人的想法”。我认为现在缺少的是长周期和完全自动化，我们正在超高速地朝着这个方向前进。一旦我们实现了完全自动化，我想说，我们就可以闭合自我改进的循环。然后，你知道，问题就变成了，主要是为这些模型提供计算资源，让它们做自己想做的事情。正如我之前所说，我们已经摆脱了改进这些模型的人工瓶颈，我预计这种发展将再次带来巨大的飞跃。

<details>
<summary>Original English</summary>

**Mustafa Dani**: It's actually interesting because you you referred to that as something that like looked like a bit of a sci-fi situation where these models are actually improving themselves and and that's true because a few years ago when you were you wanted to talk about this you could just write a perspective paper at a at a conference and and like you know talk about it at super high level but if we go uh and and check out what is happening right now like to a really good extent happening like most of the the the like and and and it's somehow like Most of the people don't realize that this is like already uh happening especially over the past few months in almost every lab u the new generation of the models are built heavily using the previous generation of the models. I think that's basically like like the case again everywhere. Uh and uh it's not fully automatic yet. Uh but the direction is like super clear and it's like easy to imagine that you know like we're going to get to a situation with full automation. These models are going to improve themselves and keep learning from the word and again it has like relation with other concept like continual learning and other other concepts that we are um still not yet to to the to the most advanced uh like point of it. But if someone comes and say that oh you know uh like uh I I have an idea to get a model to calculate the gradient and updates it weights uh like on the fly um it it just feels like very normal you know it's not something that wow this is like such an amazing idea. I think what is missing right now is uh like long horizon and full automation and and we're like moving to that direction like super super fast. the moment that we have this full automation I would say uh we we can close the loop of self-improvement and then um it becomes the like you know the problems become like you know mostly providing compute for these models to actually do what they want to do and as I said like earlier comment we just got rid of the the the human bottleneck for for improving these models which I I expect to to see a huge jump again um from from such development.

</details>

**Matt Turk**: 所以人们可能几周前看过或听说过**Karpathy**的**自动研究项目**。这是一个例子吗？大概是一个相对狭窄的范围使其奏效？这是一个自我递归循环的例子吗？

<details>
<summary>Original English</summary>

**Matt Turk**: So people may have seen or heard about kapathies auto research project a few weeks ago. Is that an example presumably reasonably narrow to make it work? Is that an example of a self recursive loop?

</details>

**Mustafa Dani**: 绝对是，我认为那是我们看到这些模型在研究方面实际做了一些非常明智事情的早期例子之一。所以我们一直在看到它们在改进开发循环的工程部分做了很多很好的工作。但在研究方面，你知道，你可能会觉得“好吧，也许需要某种直觉或悟性，一个有着长期玩弄这些模型的经验的研究员才能做到这一点”，但不一定是一个模型。我想我们已经看到了迹象，表明这种成功的秘诀中，那些主要来自优秀研究人员直觉的“黄金部分”，正在通过这些模型进入开发循环。很难去思考，“这是否意味着我们很快就能用这些模型取代每一个天才研究员？”也许吧，我不知道会多快，但这绝对是一个迹象，表明有些事情我们几年前曾怀疑过，我们不相信它会这么早发生，这非常令人兴奋。

<details>
<summary>Original English</summary>

**Mustafa Dani**: That is definitely and uh I think that was one of the early examples of uh like seeing these models actually doing something super sensible on the research side. So we've been seeing them like doing a lot of good work on improving the engineering part of the development loop. uh but on the research side which like you know you think about okay know maybe some sort of you know gut feeling or intuition is needed and like a researcher with a like a long time of like you know playing with these models and experience can do this but but not necessarily you know like a model uh I think we've seen the sign that okay you know maybe that basically that kind of like golden um part of the recipe a successful recipe that mostly coming from um like um intuition of a good researcher is coming to to kind of these development loops by by these models and it's a bit hard to think about okay you know does it mean that we can replace like every genius researcher with these bottles like like very soon uh maybe and I don't know like how how soon but this this is definitely a sign of u something that we we kind of doubted like you know a few years ago you know we couldn't believe that wow this is going to happen that early uh which is very exciting.

</details>

**Matt Turk**: 我想再强调一下，确保听众明白我们正在谈论的是**AI构建AI**。我想几个月前，如果你和研究人员谈论这个问题，人们会说“哦，是的，我们已经在使用AI构建AI了”，但这实际上意味着我们使用AI工具和推理模型来产生关于构建模型的想法。但我们现在谈论的是AI自动更新自身，以递归的方式更新其权重，这可能导致进展的**戏剧性加速**。而你所说的是，这在很大程度上已经来临，只是一个更长周期和更多计算的问题。这公平吗？

<details>
<summary>Original English</summary>

**Matt Turk**: I want to play it back just to make sure that people listening to this understand we're talking about AI building AI and I think a few months ago if you talk to researchers people would say oh yeah we already use AI to build AI but that really meant that we use AI tools and and and reasoning models to come up with ideas and and thoughts about building models but here what we're talking about is is AI automatically updating itself updating its weights in a recursive manner leading to potentially a dramatic acceleration in progress and But what you're saying is that uh this is largely upon us and a question of longer horizon and basically more more compute. Is that fair?

</details>

**Mustafa Dani**: 我认为是这样。这是其中一点，另一点是，我不会说“哦，你知道，很快我们就会拥有这些完全自动化的模型”，实际上我们还有很多问题需要解决。但是从方向上看，我能看到这会如何发生。你知道，这不是我认为会超级困难的事情。它很难，但非常可能。

<details>
<summary>Original English</summary>

**Mustafa Dani**: I think so. Like this is one and the other one is also I'm not going to say that oh you know um soon we're going to have these models like fully automated and there are actually many problems that we have to solve. Uh but directionally I can see how this can happen. You know like uh like it's not something that I would look at it as like super hard. It's like hard but but very possible.

</details>

### RSI的挑战：评估与模型崩溃

**Matt Turk**: 好的。那么障碍是什么？你提到了计算。**评估**是其中之一吗？因为模型大概需要理解什么是对的，什么是错的，以衡量答案的质量。这是问题之一吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. So what what are the roadblocks? So so you talked about compute is evaluation one of them because presumably the model needs to understand what is right and what is wrong in terms of the quality of the of the answer. Is that one of the issues?

</details>

**Mustafa Dani**: 百分之百是。归根结底，你只能改进你可以衡量的东西，而获得评估是很难的，到头来这几乎变成了一个哲学问题，而不仅仅是一个技术问题。这实际上是一个非常有趣的观察。如果有一个由非常能干的人组成的团队，如果有一些具体的评估标准可以遵循，他们大多数时候可以在一个问题上取得巨大进展。但如果没有评估，就很难取得进展。事实上，我们没有能够衡量“我们距离能够实现自我改进循环还有多近”的评估标准，或者甚至没有定义这样的评估标准，这使得衡量这个方向的进展变得更加困难。当然，有一些**代理指标**和评估，你知道，比如我们可以评估模型朝着这个方向迈出的每一步，或者我们可以评估模型在特定框架和设置中帮助自身改进的程度。而机器学习的这一部分需要迭代。它也相当有趣，因为构建评估的难度在于，你需要可靠运行的基础设施非常复杂，这也很滑稽。但有时，要弄清楚“我如何为在一个像Google内部安全运行的模型创建一个环境，并且它能完成NRE（网络可靠性工程师）和研究工程师或研究科学家在安全设置中能做的所有工作”，你知道，因为现在我们当然不相信它们总能做正确的事情，衡量它们能推进多少以及能推进任务多久是非常困难的。将所有这些点连接到一个模型运行的环境中，然后让它们高效运行，并为EVA带来多样性，这绝对是朝着这个方向取得进展的瓶颈之一。

<details>
<summary>Original English</summary>

**Mustafa Dani**: 100%. At the end of the day you can only improve what you can measure right and then u getting evaluation is uh like just hard and um and at the end of the day it becomes almost a philosophical problem not just a technical one. Like this is actually a very interesting observation. So if you have a a a like a team of super competent people, most of the time they can do like massive progress on a problem if there is some concrete eval to heal climate. But if there's no evout, it's just like really hard to to make progress. and uh and the fact that we don't have uh evouts that like or or like even defining evouts that that can maybe measure oh you know how close we are to the point that we can actually get get a self-improvement look. It's just like we don't we don't have that and and it's just making it like much harder to uh to to measure the the progress in that direction. Well, there are proxies and there are definitely some evals that you know like we're going from uh oh maybe we can evaluate like every a step of the model toward this direction and maybe maybe we can evaluate up to this many turns of the model or maybe we can evaluate the model helping itself to improve in a specific framework and in this specific setup and and this part of the the like the machine learning that needs uh like iteration. It's also quite interesting because the difficulty of building eval is um um like the infrastructure that you need to reliably runs that are super complicated is also like super it's quite funny but sometimes um figuring out that okay how can I uh create an environment for a model that operates safely in in like within Google right uh and and does all the jobs that NRE and and and and and like RA like research engineer or or research scientist can do like in a safe setup you know where they can like because right now we definitely we don't we're not confident about you know them doing the right things all the time and measuring like how much they can push and and how long they can push a task is very difficult and um like connecting all these points into an environment that these models are operating and then get them run efficiently and and like bringing diversity to EVA is definitely one of the bottlenecks of of like making progress in this direction.

</details>

**Matt Turk**: 几周前，我们和**Axium Math**的**Karina Hong**进行了一次有趣的对话，我们谈到了**形式化验证**。从你的角度来看，这是一个有前景的领域吗？像形式化验证这样的东西能否让你确保改进循环持续进行？

<details>
<summary>Original English</summary>

**Matt Turk**: A couple of weeks ago, we had a fun conversation with Karina Hong of Axium Math and we talked about formal verification. Is that a promising area from your perspective? Is something like formal verification what would enable you to make sure that the you know the improvement loop keeps continuing?

</details>

**Mustafa Dani**: 在我看来，**形式化验证**是实现自我改进的最强大关键之一，但它并非唯一的关键。如果你想想大规模**代码逻辑**，它很棒。你可以运行一个证明，它要么通过，要么不通过。但如果你进入其他有点混乱的领域，比如，你无法编写一个形式化证明来证明医生的建议是好的，对吧？所以，将这种形式化验证扩展到现实世界中的所有领域并不容易。但有一个实际上非常有趣的问题，与形式化验证非常相关，那就是我们如何看待这些方法和形式化验证，并为世界中混乱的部分构建那种**紧密而诚实的反馈循环**。我认为这非常鼓舞人心，可以以此为基础，将这些形式化验证方法扩展到那些不容易验证的领域。但你需要某种清晰而紧密的反馈循环，才能取得进展。

<details>
<summary>Original English</summary>

**Mustafa Dani**: In my opinion, formal verification is uh one of the most powerful uh like keys to to to enable like self-improvement, but it's not B key. And if you think about it like for mass code logics, um it's great. You can you can run a proof either it checks out or not. If you go to other domains that are a little bit messier, uh like for example, you cannot write a formal proof that if the doctor's recommendation is good, right? Like so so it's not hard. It's not easy to to have like to extend this formal verification to all the domains uh in real world. But one question that is actually an interesting question which is uh like uh very relevant to formal verification is how can we uh look at these methods and and like formal verification and build that kind of tight and honest feedback loop for the messy part of the world. I think that that's like very inspiring to to build like like on top of these like formal verification methods to to extend to domains that like not easy to verify easily. Uh uh but uh but but you need some sort of clean and tight feedback loop to be able to make progress.

</details>

**Matt Turk**: 这和**强化学习**的问题一样，对吧？一旦你开始偏离数学和代码，你就会进入非常混乱的领域。**模型崩溃**是需要考虑的问题之一，还是说这与此无关？

<details>
<summary>Original English</summary>

**Matt Turk**: So the same problem as reinforcement learning right like the second you start veering away from math and code uh you start getting into like very messy territory. Is model collapse uh one of the issues to think about or is that orthogonal?

</details>

**Mustafa Dani**: 模型崩溃当然是一种风险。我想说，模型崩溃主要发生在你的循环完全封闭时，如果你没有任何外部信号，只是模型自言自语，或者在一个非常受限的环境中运行，那么你的模型很有可能崩溃。但是如果你有一个强大的**验证器**，或者某种真实的**奖励信号**来锚定这些信号，例如来自AI生成的数据，那它可以变得非常强大。我认为这里的关键是保持**接地气**，扎根于真实的东西，然后你就可以很大概率避免模型崩溃之类的事情。但是的，这仍然是一种风险，但绝不是一个主要的障碍。

<details>
<summary>Original English</summary>

**Mustafa Dani**: model collapse is definitely a risk right and um I would say model collapse mainly happens when you have a loop that is completely closed right and um if you don't have any outside signal and just the model for example talking to itself or or operating in a in a in a very uh like a like a restricted environment u there's a good chance that your mobile call access but uh but if you have a strong verifier or some sort of like a real reward signal that anchor this this kind of like um like signals that is coming from like AI generated data for example it can be quite powerful. I think like the key here is to stay in grounded uh uh to to something real and then you can most likely avoid like you know things like model collapse and um I but yeah I mean again it's it's a risk but it's not definitely like a major rocket.

</details>

**Matt Turk**: 也许为了让所有人都能理解，你能先定义一下什么是模型崩溃吗？

<details>
<summary>Original English</summary>

**Matt Turk**: and perhaps to make this accessible to to everyone can you define what model collapse is in the first place?

</details>

**Mustafa Dani**: 基本上，当你有某种数据和环境，这些模型正在与它们互动，但这些环境和数据是由另一个模型设计的，例如，这只是其中一个例子。然后你在这个特定部分变得非常非常擅长，但突然之间，你失去了对任何超越这个范围的**泛化能力**。这是模型崩溃可能导致的一种定义或情况。

<details>
<summary>Original English</summary>

**Mustafa Dani**: So basically when you have some sort of like data and environment that these models are interacting with but those environments and and data are are designed for example by another model like like this is just an example of that right and then you become really really good at this specific part and then suddenly you lose generalization to anything beyond that and this is like one of the kind of like definition or one of the cases that that like like a model collapsing uh would result to.

</details>

**Matt Turk**: 所以你提到了失去泛化能力。这在**RSI**的概念中，是否特别令人担忧？也就是说，你既有那些自我强化的循环，但它们需要相当狭窄，或者你有更通用的模型，但你又有了这些循环。

<details>
<summary>Original English</summary>

**Matt Turk**: So you mentioned losing generalization. Is that is that particularly in the concept of RSI a uh worry that either you have those self-reinforcing loops but they need to be fairly narrow or you have more general models but then you kind of have the loops.

</details>

**Mustafa Dani**: 这又是一个有趣的问题，关于**泛化**与**专业化**。让我退几步。我们已经多次讨论过这个问题：在开发这些模型时，我们应该如何在泛化和专业化之间进行权衡？我认为从长远来看，你想要一个无所不知，并且知道何时深入何时广阔的模型。想象一下你有一个**Agentic**角色，对吧？如果你是一个Agentic程序员，如果你的Agent在操作的每一步都非常强大，就像一个非常好的程序。这很棒，你知道，它超级专业化。但对于许多问题，比如**编码问题**，你需要某种规划和理解正在发生什么，收集信息，然后根据上下文决定做什么。然后，在你定义了步骤之后，你强大的专业化能力就会发挥作用，但在那之前，成为一个**通才**是非常有用的。当然，泛化是达到AGI（通用人工智能）最终目标所需的东西之一。但从短期来看，我想说，构建一个**专业模型**可能是了解实际可能性最快的方法，在许多情况下，这些专业模型正在成为通向**通用模型**的垫脚石，这非常有价值。所以你可以想象，如果我正在考虑自我改进，也许我需要确保在某个非常特定的领域，我可以构建它，也许我专注于编码，如果它奏效，那么我就去研究如何拓宽它，以及如何将更多内容纳入这个专业化设置中。我总是喜欢说的一件事是，人们不关心他们的问题属于哪个类别，对吧？如果人类把某事称为问题，那么AI就应该能够解决它。我认为这从根本上来说是通才的需求，对吧？所以归根结底，你需要泛化，而玩弄这个泛化和专业化的光谱，更多的是关于长期和短期，以及如何在这个过程中利用每一方面。

<details>
<summary>Original English</summary>

**Mustafa Dani**: This is an interesting question again like you know generalization versus uh specialization. Let me go a few steps back. We had this discussion like like many many times. How should we do a trade-off between generalization and specialization when we are developing these models? I think long term you want a model that knows everything and knows when to go deep versus wide, right? Imagine like you have an agentic actor, right? Like if if you an agentic coder, if your agent is like super strong at every step of operation, like a really really good program. It's amazing, you know, like it's like super specialized. But for many of the problems like coding problems you need some sort of planning and understanding what's going on and collecting information and and like you know based on the context deciding what you do and then after you define the steps then your like super strong joint specialization just kicks in and and before that like being a generalist is is like super useful. Definitely generalization is is like one of the things that u like you need to get to the ultimate side of AGI. Uh but short term um I would say like building a specialist model is like probably the fastest way to learn like what is actually possible and um in in many cases these like specialized model are becoming a stepping stone toward a generalist model which which is like super valuable right so so you can imagine that oh you know if I'm actually thinking about self-improvement uh maybe I I need to make sure that you know in a very specific area I can I can build that maybe you know like I I focus encoding and then if it works out then I I go through like you know how to widen that and how to bring more into into this specialized setup. One thing that I always like say is that people don't care what category their problem falls into, right? And and if a human calls like something a problem, then AI should be able to solve it. And I think that's like fundamentally a generalist need, right? So at the end of the day you need generalization and um like uh like playing this like like going through this spectrum of you know like super generalized model and super specialized model is more about you know like a long-term short term and how to take advantage of each side uh uh during this process.

</details>

**Matt Turk**: 今天一个**专业模型**是什么？它是一个独立的模型，还是一个经过特定训练的通用模型，包括通过**强化学习**？

<details>
<summary>Original English</summary>

**Matt Turk**: What's a specialized model today? Is that a separate model or is that a broad general model that's trained in a specific way including in particular through through RL?

</details>

**Mustafa Dani**: 好的，重点来了。我们过去受到**计算**的限制，如果你想推动一个模型，我们会选择特定的维度，然后说“好吧，我们想把我们拥有的计算资源分配给它，然后让这个模型在这个方面变得非常出色，成为一个极其专业的模型。”所以，这是我们在有限的计算预算下试图做出的权衡。随着我们经历了计算变得越来越便宜的阶段，然后，你知道，我们可能会受到数据等其他方面的限制。出现的另一个权衡，尤其是在**后训练**中，你知道，这个评估的游戏有时很难让你的模型在各个方面都表现出色。所以你试图让它在某个方面表现出色，比如多模态，但你可能会看到它在**编码**方面有所退步。然后你让它在编码和多模态方面表现出色，它会比你在数学和推理方面拥有的模型稍差一点。所以，很难找到一个平衡点，部分原因是因为后训练有点像**过拟合**。你知道，归根结底，当你对模型进行后训练时，你试图让它过拟合到你所拥有的最佳局部最优解。当秘诀变成“我如何找到最佳局部最优解”时，问题就变成了“没有一个局部最优解适用于所有情况，所以我需要做出选择”。然后，你知道，看到这一点，你最终会做出一些决定，说“好吧，你知道，也许对我来说，在这个阶段，由于我的组织内部的需求，考虑到正在进行的竞争，我需要选择这个特定的方向”。例如，有些公司非常注重编码，这很好。你知道，我让我的工作变得超级简单，或者说比那些想要构建一个在各个方面都表现出色的模型的竞争对手容易得多。我认为短期来看，这非常非常有效，因为首先，在开发过程中，你不太关心所有维度，所以它可能更快地进行交易。你让研究人员和工程师的大脑 освободиться，让他们不用考虑这个问题，只需将其推向极致。另一个原因是，你不会立即遇到权衡问题。而专业模型，比如“好吧，我要选择这个特定的轴线，然后让模型在这个方面表现得非常好”，有时，这 again，是基于你所处位置的决定，你知道，再次，比如组织方面，竞争对手等等。

<details>
<summary>Original English</summary>

**Mustafa Dani**: Okay, so here's here's the point. We used to have constraint like compute uh and then if you wanted to push a model um to be like so we would choose specific dimensions and then we say that okay you know we we want to kind of like allocate the compute that we have to that and then make this model really good at this like you know something that is like extremely expert at this. So that was like basically the trade-off that we were we were um like trying to to make given the compute budget that we have as we as we go through this like like the the phase of compute becoming like you know more available like cheaper and then you know like maybe we're constraint with other stuff like data and stuff. One of the other trade-offs that pops up is especially in post training like you know this game of evacuable that sometimes it's like really hard to get your model to be good uh across the boards. So you try to kind of like make it good at like something like you know multimodality somehow you see some regression on you know the coding and and you make it like good at like coding and multimodality it becomes a little slightly worse than than a model that you had like you know at like math and reason. So, so it's hard to to kind of find a balance and and part of it is because post- training does a little bit of a like a overfitting you know like like at the end of the day when you post train the model you are trying to overfeit it to the best local optima you have when recipe becomes um like how can I find the best local optima it becomes the problem of okay there's no local optima that is good for everything so I need to kind of choose right and then uh like seeing this you end up with like making some decisions along the way and saying that okay you know maybe for me at this stage because of the meat that I have in in my organization like with respect to the competition that is going on u I need to choose you know this specific access like you know for example some companies have like a very strong focus on coding which is okay you know I I make my job like super easy you know like or or not super easy but like much easier than than the competitors that they want to basically shoot a model that is good across the board I think short term it's like very very effective because uh first of all during development you care less about you know like all the dimensions so maybe it's just faster to be trade like you you kind of free up some space from the mind of your researchers and engineers that okay you know like forget about this just let's push this to the max and then the other one is also like you don't hit the the trade-off like immediately and specialist model is that like okay you know I'm going to pick this specific axis and then make the model look really really good at this sometimes again like this this is the decision based on um the place that you are at you know again like organizationally like competitors like and stuff like that.

</details>

### AI研究员的未来

**Matt Turk**: 太棒了。你几分钟前说了一些话，我觉得非常有趣，那就是像世界上像**Karpathy**这样的人和像你这样的人都可以被自动化。如果世界上最聪明的人被自动化，AI创造了自己，那会发生什么？在某个时候，是不是就没有人知道AI是如何工作的了？这是一种实际可能发生的未来吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. You said something um a few minutes ago that I thought was so intriguing which is this idea that the carpathies of the world and and and and you of the world could be automated. What happens if like the brightest minds in the world get automated and the and the AI creates itself? Like at at some point is there just no one knows how the AI works. Is that is that an actual possible future?

</details>

**Mustafa Dani**: 这一部分非常**哲学**。我不知道。让我给你讲一件我几天前想到的事情。我有一个女儿，一岁半。在过去的几年里，我一直很受启发。非常有趣的是，我多次被证明我心中的时间线是错误的。例如，有时我说“哦，这将在六个月内发生。”从没发生过。有时，像“哦，这太难了，在未来十年内绝对没有机会解决它”，然后“砰”的一声，在两三个月内，有人想出了一个绝妙的主意，他们解决了它。所以，预测未来真的很难。我当时在想，“好吧，你知道，你正在谈论像Karpathy这样的研究员，以及其他研究人员，但我正在想，下一代呢？如果我的女儿在某个时候来问我，‘好吧，我应该做什么？你推荐我学习什么专业？什么科学分支或研究领域是我应该深入钻研并成为专家的？’我真的没有一个好的答案，你知道，它几乎不存在，预测未来真的很难。我知道的是，有一些技能可能对于在这个世界上产生影响以及保持相关性至关重要。其中之一是**战略性思维**，以及在做决策时将所有参数摆在桌面上。而成为某个非常特定主题的绝对专家，很可能在不久的将来不再有用。我想，你知道，**Karpathy**的才华，我认为他并不是一个好的程序员，或者他当然是一个好的老师，但我想说，这些并不是他最令人印象深刻的地方。对我来说，最令人印象深刻的地方是，他对正在发生的事情有一个非常好的**整体视角**。通过将自己置身于信息流中，他可以决定下一步最具影响力的行动是什么。现在，他所做的事情，与五年前他所做的事情，以产生影响，非常不同。我认为他能够继续这样做，你知道，他五年后会做什么？我不知道。我所知道的是，他足够聪明，能够弄清楚，并且仍然在董事会中产生影响。

<details>
<summary>Original English</summary>

**Mustafa Dani**: This patch is very philosophical. I don't know. Let me let me give you one uh quick things that I I thought about it a few a few days ago. I have a daughter. She's like one and a half years old. I've been impressed over the past few years. Like very interestingly like I've been proven wrong multiple times about like the the the timeline that I had in mind. For example, sometimes I say like oh this is going to happen in 6 months. Never happened. sometimes like oh this is just like so hard like within the next 10 years there's absolutely no chance to solve it and then boom like in two months 3 months someone had a brilliant idea and they solved it so so it's like really hard to predict the future and I was thinking like okay you know like so you're talking about like like kipathy and and like you know again like other researchers but I'm thinking about okay like what about the next generation you know if if like my daughter at some point comes to me and asks like okay like what should I do you know like what do you recommend to study like what major and like you know what branch of the the science or or or research should I kind of like, you know, dig in and and like be the expert on? I I really don't have a good answer, you know, like almost it doesn't exist and and it's just like really hard to predict the future. What I know is there are a few skills that are probably key to be able to uh to make impact in this world and also be relevant staying relevant. Like one of them is like a strategic and and having all the parameters on your table when you're making a decision and and becoming absolute expert about a a very specific subject most likely is not going to be useful in in in like like the near future. I think like you know the brilliance of gap I think is not like you know he's a good programmer or he's a good definitely he's a good teacher you know but but I'm I'm saying like you know these are not like the most impressive part of it like the most impressive part for me is that he has a really good overall view of like what is happening like by putting himself in in the in the in the um like the the stream of information he can make a decision about okay what is the next most impactful thing to do and now like you know the things that he does to make impact is very different from like you know the things that he used to do like 5 years ago and I think he can be able to do that like continue doing that you know like what is that the things that he's going to do he's going to be doing like in like in 5 years I don't know what I know is like he's smart enough to figure it out and and still keep making impact on on the board.

</details>

**Matt Turk**: 所以AI研究人员还没有在研究中失去工作。

<details>
<summary>Original English</summary>

**Matt Turk**: so AI researchers are not researching their way out of a job just yet.

</details>

**Mustafa Dani**: 嗯，希望我们足够聪明能做到。

<details>
<summary>Original English</summary>

**Mustafa Dani**: uh hopefully we are smart enough to to do that.

</details>

### 数据与计算的未来

**Matt Turk**: 好的。这也许是一个宏观问题，当我在思考这个生态系统中的**价值**在哪里时，如果AI只是不断地自我创造，那么数据是否仍然是这个等式中的必要部分，或者说一切都变成了计算？

<details>
<summary>Original English</summary>

**Matt Turk**: uh all right Maybe that's more of a macro question as I think about um you know where where the value lands in this ecosystem but if AI just keeps creating itself then does is is data still needed in that equation or is that all compute.

</details>

**Mustafa Dani**: 数据的概念比仅仅是**token**要宽泛一些。如果你将数据视为模型可以从中获取信号的任何东西，无论是预测文本中的下一个token（我们通常在**预训练**中使用它），还是模型与之交互并获取信号的**超级复杂环境**。这是我们可以将其称为数据的东西。数据或拥有好数据或处理数据的价值并不会消失，计算也不会在最终成为唯一的东西。我认为我们在数据方面所做的工作很可能会转向构建环境，或者确保这些模型可以与**物理板**交互，然后它就变成了“我如何为这些模型提供更多的**基础**”的问题。它们擅长自我改进，但只要我将它们暴露在**真实世界数据**中，以及真实世界的环境中，那么提供数据就更多地变成了“我如何让这个特定的模型访问我们以前从未有过的东西”的问题。例如，一个再次有点科幻的想法是，“我如何让这些模型能够接触到**气味**？”你知道，现在没有好的方法，但数据就变成了信息，或者任何对我们来说，因为我们所有的感官都很容易得到的东西。你知道，现在我坐在这里，我知道我的椅子有多硬，这个房间的温度是多少。所有这些**传感器信息**都是我接收到的东西，然后我所看到的下一个场景是基于所有这些输入，对吧？然后，为进行自我改进的模型提供这些信息，本身就是一个非常困难的问题。所以我想说，数据方面的工作将转向使这些传感器信息更容易被这些模型获取，从而使它们能够更有效地利用所有这些信息进行自我改进。

<details>
<summary>Original English</summary>

**Mustafa Dani**: concept of data is a little bit like broader than just like you know tokens right like and and if you think about data as um whatever that the model can get signal from either it is like predicting the next token in rock hex which we kind of like you know use in print training or super complex environment that the model interacts with and then get signal. Um this is something that basically like we can we can like refer to it as like data right and it's not like data or or uh like the value of like having good data or working on data is going to disappear and compute is going to become like the only things at the end of the day. I think like the work that we're doing on the data side most likely is going to shift uh toward building environments or or making sure that these models can interact with with physical boards and then it becomes more of a problem of okay how can I like provide more grounding for these models they are good at like improving themselves but as long as like you know I I have I expose them to real world data right like and and like you know real world environment so so providing data becomes more about okay how can I give uh access to this specific um like model to something that you know we never had for example like again like something came to my mind which is like again like a little bit sci-fi but how can I make like smell accessible to these models you know like like right now it doesn't like there's no good way but then data becomes like okay you know like information or or anything that is for us because of all the sensory that we have is like really easy you know like right now I'm sitting here I know how hard is my chair what is the temperature of this room all this sensor information is something that is coming to me and then I'm like the next board that I'm seeing is based on all this input right and then providing this or a model that does self-improvement is already a really hard problem so I would say that the the work on the data would shift toward making these sensory information more available to these models in a way that that it enables them to really improve themselves given all this information in a more effective way.

</details>

**Matt Turk**: 是的，有趣。是的，似乎有一种**传感器即服务**的巨大趋势。我们看到这个领域正在出现新的创业公司。好的。超级超级有趣。让我们从自我改进中跳出来几秒钟。去年最大的主题是**后训练**的加速，除了**预训练**之外。所以整个**强化学习**方面的事情。你预计未来几个月或一年会有哪些方面的进展？是更多地来自后训练？还是更多地来自预训练？两者都有？还是其他什么？

<details>
<summary>Original English</summary>

**Matt Turk**: yeah interesting yeah there seems to be a big trend towards sensors as a service. We're seeing the startups emerge in that field. Okay. Super super interesting. Zooming out from self-improvement for for uh seconds. The big theme of the last year has been uh the um acceleration of post training in addition to pre-training. So the the whole um you know reinforcement learning aspect um of of things. Where do you expect gains to come from in the next few months or or year? Is that more post training? Is that more pretending? Is that both? Is that something else?

</details>

**Mustafa Dani**: 这个问题的答案取决于你何时提出这个问题。很明显，预训练和后训练之间会有一些来回摆动。归根结底，我想说的是，预训练仍然是基础，你永远无法通过后训练来摆脱一个基于网络的模型。但现在，后训练的回报非常强劲。我几个月前开始从事后训练工作，比如**Gemini**的后训练，主要是**编码**和**Agentic**方面。我可以看到，一个绝妙的小想法如何能让一个模型在行为方面提高10倍，例如，而且成本只是预训练的一小部分。这再次表明，后训练是产生巨大影响和改进这些模型的地方。但另一方面，我知道在不同的公司也是如此，但在GDM（**Google DeepMind**），很多令人兴奋的重置工作都投入到了预训练方面，比如新的配方、新的想法。我想说，我们在预训练方面所做的工作将开启许多下游的可能性。后训练只是一种不同的操作模式。对我来说也超级有趣，因为我 again，对这方面的操作有点新手。但归根结底，我总是期望看到预训练和后训练之间不断地进行。你对预训练的评论与几个月前出现的“预训练已死”的说法相悖。那根本不是你的看法，对吧？

<details>
<summary>Original English</summary>

**Mustafa Dani**: The answer to this question really depends on when you actually ask this question. And like it's obvious that like you know we're going to be having a bit of a swing back and forth between pre-training and post- training. At the end of the day, I I I want to say that, you know, pre-training is still the foundation and like you can never post- train your way out of a veb based model, but right now the current like the return on post training is really strong and I started working on post- training myself like like a few months ago like Gemini post training uh like mostly coding and agentic. I can see how a brilliant small idea can make a model like 10x better for example in terms of behavior at a fraction of the cost of the pre-training right this is again I can like you know we can we can see how post- training is like like the place to make a lot of impact and improve these models but on the other hand um like I I know at different companies it's also the case but at GDM a lot of exciting reset work is going into the pre-training side and like new new recipe new ideas and Um uh and and I would say like you know the work that we're doing on the pre-training is uh going to unlart a lot of downstream possibilities. Post training is just like a different mode of operation. It's like also super interesting for me because I'm again like a little bit like new to to this to this side of the the the operation. Uh but but at the end of the day I always expect to see like like going on like you know between post training and pre-chain. your comments on on pre-training are uh sort of against like that narrative that that appeared a few months ago that pre-training was dead. That's not your take at all.

</details>

**Mustafa Dani**: 对。我认为每个人在预训练方面都有自己的想法。归根结底，追求这个想法是**复杂性**和**预期收益**的函数。有时你会觉得“好吧，有一些低垂的果实，而不是把这个复杂的配方带到预训练中，我有一个简单、优雅、可扩展的配方，我将推动它，然后将精力转移到后期处理”。然后，在某个时候，基础模型变成了瓶颈，然后你乐于接受复杂的配方并将其带到预训练中，然后继续推动它。我认为预训练已死，我想说，也许旧的，谈论新旧也有点像典型的说法，因为时间框架非常依赖于。所以当我说旧时，我可能指的是两周前或更早。但是我们过去进行预训练的方式，也许是一年前或两年前，**收益递减**是显而易见的。但我可以看到，新的想法正在为预训练注入新鲜的能量，并突然打开一扇门，通向一些可能从根本上改变基础模型能力的**奇特事物**。

<details>
<summary>Original English</summary>

**Mustafa Dani**: Right. I think everyone has ideas on pre-training side at the end of the day like going for that idea is a function of complexity and the expected gain right and sometimes you feel that okay you know there are low hanging fruits and and it like you know instead of bringing this complex like you know recipe to the pre-training the one that I have like which is simple elegant super scalable I'm going to push this and then move the the effort to the poster and then at some point like the the base model becomes the bottle like and then you're happy to take the complex recipe and bring it to the pre-chaining and then like hit pushing it. I think pre-training is dead. I I would say like maybe like you know the old it's also like a little bit like typical to talk about old and new because like the the time frame is like very depend so when I say old maybe I'm referring to like you know two weeks ago or something but uh but but the way that we used to do pre-shing maybe like you know like two a year ago or two years ago uh maybe like you know diminishing return is like obvious but I can see how new ideas are are bringing like you know fresh fresh um uh energy into the pre-training and suddenly just open a door toward like like something exotic that might actually drastically change um the base model capability over time.

</details>

### 持续学习与知识更新

**Matt Turk**: 所以**Gemini 4**出来的时候会有令人兴奋的东西。你之前提到了**持续学习**，那是另一个人们一直在谈论的热门话题。你能为我们定义一下持续学习吗，以便这次对话对更广泛的人群具有教育意义？也许可以将其与自我改进循环进行比较和对比。它们是两回事，但请帮助我们理解它们之间的区别。

<details>
<summary>Original English</summary>

**Matt Turk**: So exciting stuff for Gemini 4 whenever it comes out. You mentioned continual learning earlier and that's another one of those hot topics that people have been talking about. Can can you define continual learning for us so that uh this conversation is educational to for broad group of people? Uh maybe compare and contrast that with the self-improvement loop. Like those are two different things but um help us understand the the difference.

</details>

**Mustafa Dani**: 它们确实相关，但又截然不同，对吧？所以**自我改进**是指模型随着时间的推移变得更聪明，并提高自身能力，由模型本身来完成。**持续学习**则主要是关于模型保持**最新状态**。就像一个医生不断阅读新的研究，他们更新自己的知识，并确保这些知识不会过时。自我改进和持续学习的共同敌人是权重冻结的模型，而世界却在不断发展。如果你有一个模型只是冻结在那里，而世界却在变化，那么你既不会获得自我改进，也不会获得持续学习。但持续学习主要关注的是，如果世界中有新的知识，那么模型的**知识截止日期**就不会停留在过去。所以它不断地更新，例如，一夜之间，所有新闻，世界中发生的一切，都会被更新。所以如果今天你问模型一个问题，那些超新的知识就已经在模型的权重中了。所以它不需要依赖外部来源来获取这些信息。这很难，真的很难。最大的问题，不，不是最大的，但其中一个大问题是**灾难性遗忘**，当你训练完模型后，让它学习新信息，然后你突然看到你在主要训练阶段已经学到的知识出现退步，这是目前非常活跃的研究领域。

<details>
<summary>Original English</summary>

**Mustafa Dani**: Definitely they're related but like they're distinct, right? So self-improvement is about a model getting smarter over time and improving its capability like the model itself doing it. Continual learning is mostly about a model staying current, right? like and and and think about a doctor that like keeps reading new research and they like refresh their their knowledge about um uh stuff and and like you know they're trying to make sure that you know the knowledge doesn't go stale. The shared enemy between like um self-improvement and and continual learning is a model with frozen weights uh over time while the the board is just like going right like you know if if you have if you have a model that is just frozen and the board is moving then like you neither get like self-improvement nor continue learning but continue learning is mostly focused on um making sure that you know if there's like fresh knowledge in the board uh uh like the my the model knowledge cutoff is not um like uh in the past. So it's constantly you know like for example overnight all the news everything that is happening in the board everything is just like you know updated. So if today you asked a problem if you ask a question from the model those knowledge which is like super fresh is already in the weight of the model. So it's it doesn't have to kind of like you know depend on external source to to to bring it in. And it's hard. It's like really really hard. And the biggest problem um uh like not the biggest but like one of the big problem is like catastrophic forgetting where you get your model to to uh learn about new information um after you're done training that model like you know and then and and suddenly you see regression in in in the knowledge that you learn already in in the in the main training uh phase and it's a very active u area of of research right now.

</details>

**Matt Turk**: 那么，**持续学习**的现状如何？它是否已经内置到现有系统中，还是完全没有？

<details>
<summary>Original English</summary>

**Matt Turk**: and uh what's the reality of continual learning as of now is that is that's built into existing systems not at all about to?

</details>

**Mustafa Dani**: 这有两个方面。一方面，我认为研究还没有达到一个非常成熟的程度，让你觉得“哦，你知道，这就是秘诀，我只需要利用它并推动**生产化**”。但基本上，你知道，每次你遇到一个关键的新问题时，你都会有一个**探索阶段**，人们会尝试不同的想法，你知道，从一个想法跳到另一个想法，这可能非常不同。然后，当你对这种方法在一定程度上奏效有信心时，你就会进入**利用阶段**，说“哦，你知道，让我尽善尽美，你知道，这就是推动它的方式，让我们扩大规模，让我们开发基础设施，让它变得超快，你知道，生产化它，看看会发生什么”。我认为这还没有实现。另一点是，正如我所说，因为我们从未有过非常自信的持续学习秘诀，所以构建基础设施和投资于快速的东西是困难的。考虑到我已经看到了在GDM内部这方面的惊人进展，这很有趣，因为你知道，它可能非常理论化。我见过一些人，他们一直在做很多理论工作，然后他们进入这个问题，玩得很开心，也产生了很大的影响。这方面的进展令人印象深刻，但我认为我们还没有任何一个想法让每个人都说“哦，你知道，就是它了，让我们就这么做，你知道，让我们推动它”。

<details>
<summary>Original English</summary>

**Mustafa Dani**: there there are two sides of it like one side is I think like the research is not like yet to a a very like uh to a to a point that you you think that oh you know this is this is the recipe you know I just need to kind of like you know exploit it and push productionization right but basically you know like every time that you have uh a new problem that is like key you have this phase of exploration where people like try to kind of like you know try different ideas and you know like uh go jump over this like idea to another idea which could be like so different and then when you're confident about this kind of working to some extent you go to the exploitation mode and say that oh you know let me just make it as good as it can be and you know this is the way to to kind of push it and and let's scale it let's just like you know develop infra for it make it like super fast like you know productionize it and see what happens I think like that that is not yet there the other point is also again like as I said because we we never had like like super confident um uh recipe for continual learning like building infra and investing in in something that is like fast is hard given that I like I've I've seen like very impressive progress on this of this within GDM it's it's kind of interesting because it is one of the things that you know it can be heavily theoretical I' I've seen people who are like you know like uh doing a lot of theory work and they got into this like problem and they're having a lot of fun and they're also like making a lot of impact and uh it's impressive how much progress be made on on this but I don't think that you know we have yet like uh like any any idea that like like everyone says that oh you know this is it you know like let's just do it you know like let's push this.

</details>

### Mustafa Dani的AI旅程：从LSTM到Transformer

**Matt Turk**: 太棒了。我很想听听你和你的背景。你能用几分钟讲讲你的故事吗？你是如何开始这份工作的？你的AI之路，以及你如何来到**Google DeepMind**的？

<details>
<summary>Original English</summary>

**Matt Turk**: great I'd love to talk about you and and your background um tell us your your story in a few minutes like how did you come to do this work and what was your journey to AI and then your journey to to Google deep mind.

</details>

**Mustafa Dani**: 我在**阿姆斯特丹大学**攻读博士学位，研究机器学习，主要涉及**语言模型**、文本、搜索和**检索**。然后，我想是促使我真正走向主流并成为这个努力取得巨大进展的团队一员的原因。我在2016年和2017年做了几次实习，有趣的是，我在2017年初在**Google Brain**实习。那次经历很棒。你知道，我去了这个团队，他们正在研究用于**摘要**的**LSTM**。摘要在当时是一个非常有趣的问题。我当时很惊讶。我想，“这太棒了。我真的想一辈子都做这个。你知道，就是它了。”然后我得到了一个回聘，在同年年底再做一次实习。招聘人员告诉我，“哦，你知道，有一个团队刚刚发表了一篇论文，你可能听说过，叫做**Transformer**，他们在找实习生。”我记得我和**Lucash Tit**聊过，Lucash当时告诉我，“是的，我们有一个想法，要基于Transformer构建一个**aogorph机器**。”他对这个想法非常兴奋。然后，你知道，我们结束了谈话，我开始给招聘人员发信息。我说，“我不知道我是否想加入这个团队。他们只是在做一些随意的事情，你知道，每个人都在做**LSD**。我为什么要加入一个研究这种随意架构（Transformer）的团队？它会消亡的。”然后他尝试了，但他找不到其他团队让我加入，所以我作为实习生加入了这个团队。那改变了我的人生。你知道，能和这些非常聪明、才华横溢的人在一起，他们相信某个愿景和方向，而当时几乎所有人都对其他事情感到兴奋，这非常鼓舞人心。然后我们再次研究了**colograph机器**，这个想法最终演变成了**Universal Transformer**这篇论文。你知道，其中的**递归深度**和**参数重用**就是从中产生的。直到现在，十年后，它仍然产生了很大的影响。

<details>
<summary>Original English</summary>

**Mustafa Dani**: so I I did my PhD at University of Amsterdam on machine learning and and mostly on the on the like the language model side and text and and search and retrieval. And then uh I think what kind of like pushed me toward trying really to be on the uh like on the on the mainstream and be part of this group that are like you know hustling to to make like really good progress. I did a few internship like back in 2016 and 2017 and and the funny story is um I did an internship in at Google brain in 20 like early 2017 and then it was amazing. It was just like you know I went to to to this team they were working on like LSTMs for you know like summarization summarization was actually one of the most like interesting problems at that time. I was like amazed. I was like, "So, this is so good. I I really I just want to keep doing this for the rest of my life. You know, this is it." And then I got uh I got a return offer to go back and then do another internship at the end of the the the same year. The recruiter told me that, oh, you know, there's this team that they just published a paper, maybe you've heard about it, like Transformer, and then they're looking for an intern. And I have a had a chat with I remembered I had a I had a chat with Lucash Tit and then Lucash was talking to me and was saying like yeah like we have this idea of building like aogorph machine based on transformer and he was so excited about this and then like you know we like we finished that the conversation and I started sending a message to recruiter. I was like I don't know if I want to go with this team. It's just like they're doing something random like who like like everyone's doing LSD. I'm like why should I go and and work with a like a a group of people who were working on this like random architecture like transformer it's just like it's going to die you know I and then he tried and he couldn't find any other team for me to to join so I joined this team as an intern and that changed my life you know like uh like being among these like super brilliant like super smart people that they believed in in some vision and direction where almost everyone was excited about something else was like very inspiring and then we work on on like again like this colograph machine like idea of like turned into like you know universal transformer prepare which you know like recursion in depths and reusing parameters was was coming out of it and still this is like making a lot of impacts after almost like 10 years.

</details>

**Matt Turk**: 很快给我们讲讲这个。那是在2019年，我相信你也是那篇论文的合著者。那正是我们从对话一开始就谈论的关于循环和递归的想法。那么，**Universal Transformer**是？

<details>
<summary>Original English</summary>

**Matt Turk**: Tell us about that quickly. So that was in 2019 I believe and you you so you were a co-author of that paper and that was very much that idea that we started with right at the beginning of this conversation of like loops and recursive stuff. So universal transformer like we wrote that paper in 2018 and I think it.

</details>

**Mustafa Dani**: 我们在2018年写了那篇论文，我想它曾经被一个会议拒绝过一次，然后在2019年被接受了。我记不清具体了，但我想它在**NeurIPS**或其他什么地方被拒绝了。整个直觉是，**参数重用**和模型再次遍历其输出有一些特别之处，你知道，你生成一些东西，然后你把它再次输入到模型中，模型就有机会这样做。我们从一个叫做**算法数据集**开始，我记得Lucash曾称之为**算法任务**，它是基于**TensorFlow**的**Tensor2Tensor**代码库的一部分，那个代码现在还在那里。我记得我甚至能找到我为提交**Universal Transformer**代码而发起的**pull request**。我们看到，基本上，有些问题，比如将输入复制到输出，或者用非常长的输入在输出端进行一些算法操作，这非常容易，但像**普通Transformer**这样的普通模型却在这方面表现糟糕。我们看到，你知道，循环做得非常完美。然后在那个时候，我记得我们有了一个来自**Meta**的类似**baddy**数据集，它在那上面表现出色。然后，**测试时计算**（test-time compute）的想法出现在我们脑海中，这基本上是你用固定的计算量进行训练，但在测试时，你让模型进行更多的计算，在输入上投入更多的**浮点运算**。我们对此非常兴奋。然后我们最终实际上将这种**自适应计算机制**引入其中，这再次受到Alex的论文的某种启发，你知道，来自**LSTM**。这是一段非常有趣的旅程，因为我们当时正在推动一些在当时听起来令人兴奋的东西。我猜，也许在那个时候，整个领域过于专注于利用自适应计算来降低简单问题的成本。但现在我们知道，也许我们实际上可以利用自适应计算来增加困难问题的成本，你知道，这实际上是同一枚硬币的另一面，对吧？因为在那个时候，我们，你知道，也许资源受限等等，所以我们真的在思考，为什么我们要花费如此多的浮点运算，你知道，遍历所有层，你知道，所有的东西都为了点，如果那个token是点，我们真的需要24层吗？所以我们如何减少它，但现在我们对此有了不同的看法，那就是，你知道，我们如何增加一个我们想要运行两个星期的物理问题。所以，与这些优秀的人一起工作真的很有趣，我想，这种**深度递归**和**参数重用**，或者我后来看到一些人将其称为**负稀疏性**，这是一种很好的方式，你知道，将其与**专家混合模型**（Mixture of Experts）联系起来，你知道，在专家混合模型中，你有**无浮点运算参数**。所以，你没有实际带来任何浮点运算的参数。而在循环中，你有**无参数浮点运算**，你没有额外的参数来处理你投入的额外浮点运算。所以，它朝着稀疏性的另一个方向发展，它非常有效，而且我认为人们正在接受它，你知道，所以我们看到了这个方向的很多兴奋。

<details>
<summary>Original English</summary>

**Mustafa Dani**: we wrote that paper in 2018 and I think it was also rejected one time from one conference uh and it was accepted in 2019 um I don't remember exactly but yeah I think it was accepted I clear but it was rejected from new rips or something the whole intuition was um there is something about reusing parameters and a model going through um its output another time you know like and and so so basically you generate something and then you kind of like you know pass it into the model again and then the model has the chance of doing this. So we started with like I I remember Lucash had this like algorithmic data set which I remember he he used to call it like algorithmic tasks uh and and it was part of this codebase based on TensorFlow like tensor to tensor was the name of the code that is still there and and I remember I I can even find my put request into that for for pushing the universal transformer code and we saw that basically there are some problems like copying an input to the output or you know like doing something algorithmic with like super long input uh on on the output side which is super easy but the normal models like the normal transformer was like failing awfully at this and we saw that you know like looping is like do it perfectly and then at that point I remember we had this baddy like data set from from meta um and uh it was like doing great on that and then the idea of test time compute which basically you train with fixed amount of compute but at test time you unleash your model to do more computation throwing more flops on the input was coming to our mind like super excited about this and then we ended up with actually kind of like introducing this adaptive computation mechanism into this which was again like like some sort of inspiration from Alex uh um like Alex's paper like you know from from LSDM and then like a very interesting interesting ride because we we were pushing for something that like at that time uh it it sounded exciting but and I have a guess like maybe at that time like the whole field was a bit too focused on using adaptive computation for decreasing the cost on simple problem but now we know that maybe we can actually use adaptive computation to increasing to increase the cost for hard problem you know it's actually like the other side of the same coin right so because at that time we were like you know like maybe you know uh like resource constraint and everything so we were really thinking about why we were spending so much fops like you know going through all the layers and like you know everything's for dot like at the end of the sentence if that that token is like do we really need like 24 layers. So how we can decrease that but now we we had a different perspective to that which is like you know how can we increase this for a physics problem that we want to run the the the inprints for maybe like you know for two weeks. So that was that would be really fun to work on that with with these like brilliant people and um and I think like you know this recursion in depth and reusing the parameters or I've seen later like some some people actually framing it as negative sparity which is a great way of you know like connecting it to mixture of experts that you know in mixture of experts you have flops free parameters. So, so parameters that you they're not actually bringing any flops and in in like looping you have um parameter free flops where you don't have extra parameters for the extra flops that you are throwing on this. So, it goes the other direction of the sparity and it's quite effective and and I think people are picking it up you know so the we're seeing a lot of you know like excitement in this direction.

</details>

**Matt Turk**: 太引人入胜了。你对这个领域做出的另一个极其重要的贡献是2022年的**Vision Transformer**论文。这篇论文叫做《**图像是16x16个词：用于大规模图像识别的Transformer**》。你能给我们介绍一下那是什么吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Fascinating. Another fundamentally important contribution to the to the field that uh you did was the visual transformer paper in 2022. So the paper is called an an image is worse 16 by 16 words transformers for image recognition at scale. Do you want to walk us through what that was?

</details>

**Mustafa Dani**: 那也有一段有趣的故事。我就是通过那篇论文进入**视觉**和**多模态**领域的。所以我从未做过任何视觉问题。这主要是因为我坐在那些研究视觉的人旁边。所以我的办公桌旁边是研究视觉的人，这就是我对此感兴趣的原因，因为我只是和他们交谈，然后我想“哦，这实际上很有趣”。然后我记得在那个时候，我正在研究**Palm**论文，你知道，和**Acha**以及其他同事一起。我当时想，为什么我们有4000亿参数的语言模型，但我们在视觉方面最大的模型只有1亿参数？像**ResNet**一样。为什么？为什么没有**规模效益**？我开始和同事们一起研究这个问题，“好吧，也许Transformer中有些东西可以使其**可扩展**，然后也许我们可以摆脱**卷积**来尝试这个。”归根结底，我不想说那是唯一扩展的方式，也许如果一个团队在卷积上投入足够的时间，他们也可以使其可扩展和同样出色。但这样做也有好处，因为机器学习领域的其他研究人员都在研究语言，他们正在使用这种架构。所以他们正在为它构建基础设施，使其更快，你知道，有时硬件也是根据这种架构设计的，至少在短期内是这样。所以我们开始推动，然后我记得我们有很多想法，“好吧，如果每个**像素**都是一个token怎么办？”然后，成本飙升，上下文变得超级长。然后我们进行了大量的来回讨论，这也很滑稽，因为我们开始从一个非常复杂的角度思考这个问题，所以我们试图模仿卷积来使其奏效。结果是，你知道，我在**苏黎世**也有一群同事，他们开始尝试一个简单的想法：如果只是将图像分成16x16的像素块，然后将每个块作为一个像素，而不考虑重叠块或窗口等等，只是将图像裁剪下来，然后将其输入到**Transformer**中，然后进行扩展，你知道，用大量数据进行训练，然后从一些具有辨别力的东西开始训练这个模型。它奏效了，这也有点出乎我们的意料，“哦，你知道，我们都在思考一些花哨而非常复杂的东西，也许是在整合卷积等方面。”但奏效的基本上是一个简单的想法，你知道，就是**分块**，将其输入到Transformer中，扩展它，然后“砰”的一声，你就得到了一个非常好的**表征学习模型**。

<details>
<summary>Original English</summary>

**Mustafa Dani**: That's also a funny story for that. I got into vision and multimodality with that paper. So I've I've never worked on on on like any vision problem. It was mostly because I was sitting next to people who were working on vision. So like my desk was like next to people who were working on vision and that was the reason that I got interested because I was just talking to I was like oh this is actually interesting and uh and then and then I remember that at that time I was like working on um uh on uh like externally we call it palm paper with like you know acha and other folks and I was like why we have uh 400 billion parameter language models but the biggest model that we have on the vision side is just maybe 100 million like arrest that like why like like why there's no benefit of a scale started looking into this with with folks on like okay like maybe you know like there's something in in transformer that actually kind of like you know make it a scalable and then maybe you know like we we can move away from convolution to try this and and at the end of the day I don't want to say that you know like that's the only way of a scaling maybe you know if a group actually spend like enough time on convolution they can also make it as scalable and as good but there was also benefit of doing That's simply because the rest of the that the machine learning field which was working on on language they were using this a like a like architecture. So they were building infra for it making it faster and and you know like like the sometimes the hardware is kind of like designed based on this architecture at least for short term. So we started pushing and then I remember that you know we had um we had a bunch of ideas that okay what if each pixel is a token and then um like the cost was going high the context was just like getting super long and then we had a lot of back and forth and it's also quite funny because we started thinking about this problem like from like very complicated point of view so we were trying to mimic convolutions to be able to get this working and it ended up like you know like I I had a bunch of colleagues also in Zurich and they started with trying the simple idea of what if just like divide the image into patches of pixel you know 16 by 16 and then get each patch as a pixel and forget about you know like overlapping patches or you know like windows and stuff like that's it you know like you know like chop the image and then fit it to a transformer and then scale you know like like go with a lot of data and then like let's start with like you know something discriminating to train this model and it worked and it was also a little bit like of a surprise for us that oh you know like we were all thinking about something like you know fancy and and very very complicated maybe in the integration of having like you know um like convolutions and stuff but something that worked was basically the simple idea of you know like um patchify fit it to transformer scale it up and then boom you had a really really good model for representation learning.

</details>

**Matt Turk**: 是的。简单来说，这意味着你可以将**Transformer架构**应用于图像，而过去你有两个不同的家族。你有**CNN**世界和文本的Transformer世界。你的突破证明Transformer可以同样好地扩展到图像，这基本上为今天的**Gemini 3**铺平了道路，它是一个原生多模态模型。这公平吗？好的。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. And to play it back at a at the highest level, that basically meant that you could apply transformer architecture to image when in the past you had two different families. You had the CNN world and the transformer world for text. And your breakthrough was to prove that transformer could scale equally well to images which basically paved the way to a Gemini 3 today which is like a natively multimodal model. Is that is that fair? Okay.

</details>

**Mustafa Dani**: 是的，没错。基本上，通过那次工作，我们朝着让视频也采用Transformer，音频也采用Transformer迈进了一步。所以基本上，我们，再次，即使这不是唯一的架构，但它使得原生训练这些模型变得非常简单，因为你有一个单一的架构，并且可以在训练期间拥有所有**模态**。

<details>
<summary>Original English</summary>

**Mustafa Dani**: Yeah, that is true. Yeah. Like so basically we we like with that we kind of took a step toward having also videos like adopting transformers and and audio like you know adopting transformers. So basically we like again like even even if this is not like the only architecture that would be like you know multimodal but it made it really simple to train these models like natively because you have like a single architecture and can have all the modalities in during training.

</details>

### Nano Banana与图像生成

**Matt Turk**: 太棒了。这是一个完美的过渡，可以谈谈你在**Nano Banana**和图像AI未来方面的工作。所以你曾是Nano Banana团队的一员，当它问世并完全病毒式传播时，一定非常有趣，它是一个多么不可思议的产品。所以从那时起，已经发布了几个版本。在2025年11月发布了**Nano Banana Pro**，然后就在几周前发布了**Nano Banana 2**，也就是**Gemini 3.1 Flash Image**。是的，在2月底。所以很多人认为图像生成的工作方式是翻译器，意思是AI读取提示的文本，然后将其翻译成图片指令，然后绘制出来。但正如我们所说，**Gemini**是原生多模态的。那么它是如何工作的呢？模型如何同时处理文本和像素来构建图像？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. So that's a perfect transition into your work into nano banana and the the future of image AI. So, so you were part of the Nano Banana team and which must have been so much fun when this came out and uh went just completely viral and what an incredible product. So, since then there's been a couple releases. So, there's been a Nano Banana Pro in November of 2025 and then just a few weeks ago Nanobanana 2 uh aka Gemini 3.1 flash image. Yeah. At the end end of February. So a lot of people assume that um image generation works as a translator, meaning that the AI reads the the text of the prompt and then translates it into picture instructions and then draws it. But as we were saying, Gemini is natively multimodal. So how does how does that work? How does a model actually uh process the text and the pixels at the same time to build the image?

</details>

**Mustafa Dani**: 我想我之所以进入生成领域，嗯，顺便说一下，还有一件事，就是我不是图像生成方面的专家。我记得当我开始从事这项工作时，我曾与人开会，他们谈论**计算机图形学**以及所有这些旧的理念或直觉，而我对此一无所知。我当时想，我知道如何训练和转换它并扩展它，你知道，如果这有帮助，我就可以为此做出贡献。但再次，你知道，这很有趣，因为我与一群非常聪明、才华横溢的人一起工作，他们有着非常好的直觉。我想我对此感到兴奋的原因，这也许与**Nano Banana**本身不太相关，但我想提一下，我对我说的**跨模态正向迁移**的想法感到兴奋。所以当你思考原生多模态时，其中一部分是“哦，我的模型增加了能力，你知道，所以我的模型可以理解图像，理解视频，理解音频，还可以生成所有这些模态，你知道，所以我的模型实际上将所有这些结合在一起”。这无疑令人兴奋，从产品的角度来看，你知道，你有一个模型，它是一个很棒的模型，可以生成所有这些不同的输出，用户会觉得它非常有用和有趣。但对我来说，最令人兴奋的部分是，我能否看到这些模态之间发生迁移？你知道，例如，如果我训练一个模型使其擅长图像生成，它是否也能更好地生成文本？关于为什么会发生这种情况，有不同的直觉。我认为这在语言学文献中是一个很古老的概念，他们称之为**报告偏差**。所以，例如，你知道，你拜访你朋友的家，对吧？然后你去了他们家，你看到他们有一个香蕉形状的沙发。当你回家时，谈论那个沙发的几率比谈论一个普通沙发要高得多。所以你实际上可以在稍后和你的朋友或伴侣谈论，“哦，你知道，我去了那里，他们的沙发是香蕉形状的，那真的很有趣。”但如果它很普通，你几乎会觉得奇怪，如果你去某个地方，然后说，“哦，顺便说一下，我去了我朋友家，他们有一个沙发，非常普通。”所以，这就是**语言报告偏差**。所以，语言不谈论处于分布中间的事物，对吧？但如果你有一个图像，或者如果你有世界中任何东西的视觉输入，你就会拥有这些信息，不需要报告它。它就在那里，对吧？所以，因为这个原因，通过语言获取大量世界知识效率不高。我不想说不可能，但效率不高，你知道，比如学习**重力**。如果你让你的模型在视频上训练，它更容易让模型学习重力，因为它在视频中发生，而不是训练你的模型在所有教科书上学习重力这个概念，你知道，或者重力到底是什么。

<details>
<summary>Original English</summary>

**Mustafa Dani**: I think the reason that maybe I got to the generation. Okay, by the way, there's also one one uh one thing that uh I'm not an expert in image generation like like when I started working on this, I I remember I had like meetings with people and then they were talking about like you know computer graphic and all the like you know like old like ideas about or or like intuitions and I had like zero idea what's going on. I was like I I know how to train and transform and scale it and and you know if it helps I I can I can basically um contribute to this. But again like you know it was fun because I I worked with like a group of like super smart like brilliant people with like really really good intuition and I think like the reason that I was excited about this was like like this is maybe not super relevant to like nonabanana itself but to just mention this I was excited about the idea of uh like positive transfer across modalities. So when you when you think about multimodel uh like natively one part of it is that oh you know I'm adding capability to my model you know so my model can understand images and understand videos and understand audio but also like gener like and text but also can generate all these modalities you know like so so I have a model that actually does all these together right this is for sure exciting like from the product point of view you know like you have a model that is like you know great model for for generating all these different like outputs and and and like users are like finding it like very useful and interesting. But the the the most exciting part for me was can I see a a glimpse of transfer from these modalities like you know like for example if I train a model to become good at image generating images does it become also good at like better at like generating text there are different like different intuition of that you know like what why this should happen I think this is like something like again like very old in the literature on on the linguistic site that they call it reporting biases right so like you for for example you know like visit your 's place, right? And then you go to their place and then you see that they have a banana shaped like uh like sofa. And when you go home, the chance of talking about that sofa compared to a a normal sofa is like much higher. So you can actually talk to your friends or partner later. Oh, you know, I went there and then their sofa was like in the shape of a banana, which was really fun. But if it's like normal, like you almost like it's weird if you go somewhere. It's like, oh, by the way, I went to my friend's place and they had a sofa, which was like super normal. So, so this is this is the language reporting bias. So, so, so language doesn't talk about things that are like at the middle of the distribution, right? But if you have an image or or if you have like vision input from from anything in the board, you have that information like there's no need for reporting it. It's just like there, right? So, so because of that, like picking up a lot of knowledge about the world through language is just not really efficient. I I don't want to say that it's impossible, but it's not efficient, you know, like to learn about gravity. If you kind of like, you know, have your model train on videos, it's much easier to to get the model to learn about gravity because it just happens in a video than training your model on on all the textbook to kind of like learn about the concept of gravity, you know, or or what is actually gravity.

</details>

**Matt Turk**: 这就是**世界模型**的概念，内置到图像表示中？

<details>
<summary>Original English</summary>

**Matt Turk**: Is that a concept of world model that's built into the image representation?

</details>

**Mustafa Dani**: 完全正确。完全正确。所以，你想要一个视觉模型，这些模型也能成为一个世界模型。你希望这些模型了解这个世界。你很有可能可以通过向你的模型呈现文本来教会它关于这个世界的知识。但这并不高效，一个好的捷径是将**多模态**引入其中。而学习一种模态的最佳方式是学习如何生成它。所以我们到了这个地步，“好吧，我们一直在让**Gemini**从**Gemini 1**开始生成图像。”所以我们基本上，Gemini从第一天起就是多模态的。而我们最初发布图像生成功能是在**Gemini 2.5**，而不是**Gemini 1**、**Gemini 1.5**、**Gemini 2**的原因是，它不够好，然后它确实需要一个推动。然后我们想出了如何推动它，而不影响模型拥有的其他能力，你知道，并将所有这些原生集成到这个模型中。

这对我来说是一个超级有趣的方面。虽然不能说令人悲伤，但要看到正向迁移确实很难。所以它变成了一个非常好的战场，但要看到“哇，我在图像上训练，然后文本的困惑度下降了”确实很难。你知道，你训练一个原生模型，它在所有能力方面都表现出色，这已经令人印象深刻了。但我希望多模态和世界模型能够真正推动多模态训练，以实现**跨模态的正向迁移**。我与这方面的专家一起工作。你知道，例如，我记得一开始他们谈论**视觉质量**时，我当时就想，“哦，这个模型是一个很棒的模型。”我把它们发给他们，他们说，“不，这不是一个好模型。”我当时想，“你是什么意思？”他们开始给我看两张在我看来一模一样的图片，但他们说，“不，这张好多了。”我当时说，“不，它们是一样的。”所以，他们对图像的视觉质量有很好的品味。所以和他们一起工作，去理解“好吧，存在一些维度”真的很有趣。顺便说一下，他们的直觉是真正让**Nano Banana**在成为一个好产品方面取得成功的原因。但我想，“如果我们把这个推向超越传统图像生成的东西会怎么样？”所以它不是像你说的**翻译器**，一个文本到图像的翻译器，而是一个关于图像的**思考机器**。你知道，例如，你启用了**交错的文本图像生成**，模型不仅可以在文本**token**中思考，还可以在**像素空间**中思考。对。所以，它生成文本，然后生成图像，然后生成另一个文本，另一个图像，你可以利用它来解决不同的问题。其中一个问题是，“哦，如果你有一个故事，你知道，故事的文本，与该文本相关的图像，故事的文本，你知道，就像儿童故事书一样。”另一个让我非常兴奋的是这种**增量生成**。让我给你举个例子，如果你使用**DALL-E**或**Imagen**，或独立的图像模型，对吧？如果你要求这些模型生成一个包含50个细节的场景图像，它们可能会失败，对吧？然后有人会说，“哦，你知道，我可以生成一个更好的模型，可以处理多达55个细节。”然后你说，“好吧，那60个呢？”然后我说，“好吧，不，让我回去训练它，然后回来为你提供测试。”但归根结底，这些模型在一定程度上遵循指令的阈值是有限的，关于它们从文本中捕捉多少细节。但如果你有增量生成，所以如果你有文本，然后是图像，然后是文本，然后是图像，你可以让你的模型逐个生成这些细节。所以你从不期望你的模型在第一次尝试时就生成一个完美的图像，对吧？所以，你期望你的模型规划这个生成过程。所以它会说，“哦，你知道，让我从大物体开始，因为，你知道，如果我放置小物体而大物体不合适，以后我就会遇到麻烦。”对。所以，让我先做那个。然后，在下一个回合，我处理中等物体，然后是更小的物体。这种方式非常聪明，你永远不会受到单次图像生成能力的限制，因为你进行了规划，然后你调整了每个步骤的难度，以匹配你的模型生成单次图像的能力。所以这也是**Nano Banana**和原生生成、交错生成带来图像生成工作全新视角的原因之一，它有点偏离了仅仅将文本翻译成图像。

<details>
<summary>Original English</summary>

**Mustafa Dani**: I think the reason that maybe I got to the generation. Okay, by the way, there's also one one uh one thing that uh I'm not an expert in image generation like like when I started working on this, I I remember I had like meetings with people and then they were talking about like you know computer graphic and all the like you know like old like ideas about or or like intuitions and I had like zero idea what's going on. I was like I I know how to train and transform and scale it and and you know if it helps I I can I can basically um contribute to this. But again like you know it was fun because I I worked with like a group of like super smart like brilliant people with like really really good intuition and I think like the reason that I was excited about this was like like this is maybe not super relevant to like nonabanana itself but to just mention this I was excited about the idea of uh like positive transfer across modalities. So when you when you think about multimodel uh like natively one part of it is that oh you know I'm adding capability to my model you know so my model can understand images and understand videos and understand audio but also like gener like and text but also can generate all these modalities you know like so so I have a model that actually does all these together right this is for sure exciting like from the product point of view you know like you have a model that is like you know great model for for generating all these different like outputs and and and like users are like finding it like very useful and interesting. But the the the most exciting part for me was can I see a a glimpse of transfer from these modalities like you know like for example if I train a model to become good at image generating images does it become also good at like better at like generating text there are different like different intuition of that you know like what why this should happen I think this is like something like again like very old in the literature on on the linguistic site that they call it reporting biases right so like you for for example you know like visit your 's place, right? And then you go to their place and then you see that they have a banana shaped like uh like sofa. And when you go home, the chance of talking about that sofa compared to a a normal sofa is like much higher. So you can actually talk to your friends or partner later. Oh, you know, I went there and then their sofa was like in the shape of a banana, which was really fun. But if it's like normal, like you almost like it's weird if you go somewhere. It's like, oh, by the way, I went to my friend's place and they had a sofa, which was like super normal. So, so this is this is the language reporting bias. So, so, so language doesn't talk about things that are like at the middle of the distribution, right? But if you have an image or or if you have like vision input from from anything in the board, you have that information like there's no need for reporting it. It's just like there, right? So, so because of that, like picking up a lot of knowledge about the world through language is just not really efficient. I I don't want to say that it's impossible, but it's not efficient, you know, like to learn about gravity. If you kind of like, you know, have your model train on videos, it's much easier to to get the model to learn about gravity because it just happens in a video than training your model on on all the textbook to kind of like learn about the concept of gravity, you know, or or what is actually gravity. Is that a concept of world model that's built into the image representation? Exactly. Exactly. So, so basically you you want a v model basically you know like these models to be also like a vote model. So you you want these models to know about the war. There's a good chance that that you can actually teach your model about the war just by presenting text to it. But it's just not efficient and and and a good shortcut would be to bring multiodality into this. And the best way of learning about uh a modality is learning how to generate that right like so we we got to this point that okay you know u uh we've been we've been having Gemini generating like images uh from Gemini one. So we like like basically like Gemini was multimodal from day one and and the reason that we kind of first like released the image generation at like 2.5 instead of you know like Gemini 1, Gemini 1.5, Gemini 2 uh was that it was not great and then like it really needed a push and then we figured out that okay you know how to push this without like you know introducing any regression to other capabilities that the model has and you know like bring all of these natively into the into like this this And that was like one site that was like super interesting for me. Like not sad news, but but but it's really hard to see positive transfer. So it it turned out to be a really really good battle, but it was like really hard to see that wow, you know, I train on images and then like text perplexity goes down. That that was hard to see, you know, like the fact that you know, you you train in native model and it's good at at like across all the capabilities is already impressive. But my hope is that you know multimodality and what model is the way to really push multimodel training to to enable like positive transfer across modalities. I work with people that they were like expert on this you know for example one of the one of the things that I remember that you know at the beginning they were talking about this like visual quality and then I remember that you know it's like oh this model is a great model I send them them and there's like no this is not a good model. I was like, "What do you mean?" And they they started showing me two images that to my eyes they were like looking the same, but they were saying like, "No, this is like way better." I was like, "No, they're the same." So, so they had they had a good taste on on grasping the the visual quality of images. So, working with them was like really interesting to kind of understand that, okay, there are dimensions. And by the way, like their intuition was the was the the things that actually made like not a banana like a success in terms of, you know, being a good product. But I was like okay what if we push this towards something beyond like traditional image generation. So instead of like a translator that as you as you said like a a text to image it becomes a a a thinking machine about images. You know for example you know you you enable interled text image generation where the model can think in not only text token but also in pixel space. Right. So, so it generates uh text and then generates an image and it generates another text another image and you can leverage that for different problems like one of them is that oh if you have you know like some sort of a story right like you know like text of the story image related to that text of a story like you know like children's story book right another one which I I was actually really excited about was like this incremental generation like let me just give you an example so if you take like dolly or imagine or or standalone an image model, right? If you ask these models to generate an image of like, you know, a scene with 50 details, they might fade, right? And then someone can say that, oh, you know, okay, I I can like generate a better model that like does up to 55 details and then say, okay, what about 60? And then I say, okay, no, let me just go back and train it and then come back to you to cover your test. But at the end of the day there's a threshold that these models can kind of like follow instruction to to like to some extent about you know how many details that they capture from from the text. But if you have incremental generation so if you have text and then an image and text and image you can't get your model to generate these details one by one. So you you never expect your model to to generate an image a perfect image in the first shot right? So, so you expect model your model to plan about this generation. So, it says that oh, you know, let me start with big objects because, you know, later I'm going to have a hard time if I put like small objects and the big objects don't fit, right? So, let me just do that. And then like in the next turn, I go with like medium objects and and smaller. And this like super smart, you know, and you're never bottlenecked by the capability of a single shot image generation because you you did planning and then you tune every step difficulty to to match the capability of your model to generate a one one shot. So that was also one of the things that like you know Nana a banana and and native generation interle generation uh kind of brought like a completely new perspective to image generation uh work which is like a little bit like far from like you know just translating text into an image.

</details>

**Matt Turk**: 太引人入胜了。这其中一部分是否也提高了**效率**？特别是**Nano Banana 2**，它有**闪电**（Flash）特性。所以你能够非常快速地创建出惊人的图像，而且显然，似乎非常高效。那么这背后的原理是什么？你描述的那些就是它的工作方式吗？你是如何做到的？

<details>
<summary>Original English</summary>

**Matt Turk**: Fascinating. Does part of this contribute to efficiency? So especially nanobana too you have the the flash aspect of this. So you're able to create amazing images very fast and apparently I mean seemingly very efficiently. So what's what's behind the scenes that is that what you describe is that how are you able to do that?

</details>

**Mustafa Dani**: 首先，我参与了最初的**Nano Banana**、**Nano Banana Pro**，然后最后一个版本，你知道，因为我跳到了后训练和编码以及Agent方面，我觉得这很令人兴奋，所以这个版本是由团队发布的。但如果我想从一个非常高的层面来说，你知道，究竟是什么让模型更快、更高效，其中一部分就是**模型大小**。所以像**Nano Banana Pro**就是**pro**尺寸，而这个版本就是**flash**。所以模型参数大小和配置肯定有关系。另一点是，人们实际上花了很多时间来弄清楚**蒸馏**的配方，无论是在知识方面，还是在其他你需要蒸馏的东西方面，以使其成为一个比完整过程更轻的过程。令人惊讶的是，有很多**基础设施**工作用于**服务**。所以我们有很多非常非常出色的人，他们是服务工程师，令人印象深刻的是，你知道，你坐在办公桌前，然后他们走过来，漫不经心地说，“哦，顺便说一下，我让模型快了10倍。”我当时就觉得，你知道，他们只是漫不经心地说出来，“哇，这太棒了。”我们在优化服务方面也做了很多工作，如何服务这些模型，你知道，因为这些模型与普通的**nbridge模型**运行方式不同，它们不一定与预测下一个token相同。这绝对是一个好的服务工程师可以想到的，他们会觉得“好吧，我可以想出一种不同的方法来做这件事”，而且通过他们的工作，我们在效率方面也有了很大的提升。好的。所以，当我们要结束这次对话时，我想用一些**热门观点**来结束，如果你准备好了的话。

<details>
<summary>Original English</summary>

**Mustafa Dani**: First of all I was I was involved in the original Nano Banana Nano Banana Pro and then the last version I g like you know because I I jumped on the post training and coding and agent and I find it exciting this one like this the team actually shipped it. But if I want to say like like super high level that you know what is exactly the things that makes the model like uh like faster and more efficient part of it is just the size of the model. So like non banana was pro size and this one is just like flash. So definitely the the the parameter size like you know configuration of the and stuff. The other one was uh people actually spent quite a lot of time on figuring out like you know uh um like nailing down like distillation recipe uh both on the side of like knowledge and like you know other like things that basically you you kind of like need to distill to something like a process that is like you know lighter than the full process. Surprisingly a lot of infra work for serving. So we have like really really really brilliant people that they're like you know serving engineers and it's kind of impressive that like you sit on your desk and then like they they come and they say oh by the way but casually I made the model 10x faster. I was like you know like it's just like and they just kind of saying it like you know in a very like you know casual like wow this is like impressive. We had also a lot of work on the on on optimizing the serving uh how to serve these models and and you know like because these models are operating differently from like just like normal nbridge model like they're not necessarily you know like um the same as you know next to prediction this is definitely something that you know a good serving engineer can figure out that okay you know I can think about a different way of doing that and we had also a lot of improvement on the efficiency side by by their work. All right. So, as we get towards the uh end of this conversation, I thought it'd be fun to end with a few hot takes if you if you're ready for them.

</details>

**Matt Turk**: 是的，当然。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah, absolutely.

</details>

### AI领域的热门观点

**Matt Turk**: 好的。你认为AI领域目前有什么地方做得不对？

<details>
<summary>Original English</summary>

**Matt Turk**: All right. What is one thing the AI field is getting wrong right now?

</details>

**Mustafa Dani**: 很难 pinpoint 具体的事情，但再次，这只是我的个人意见，也许我的同事和其他人也与我分享了这一点，但我想我们低估了**锯齿状智能**（jagged intelligence）的修复难度。我们遗漏了，或者说低估了它的重要性。我们谈论的时候，人们几乎会笑，你知道，如果一个模型能够进行非常困难的数学证明，但在计算一个单词中的字母时却很困难。正如我所说，人们只是笑笑就过去了，但我想它实际上指向了这些系统中一些深刻而未解决的问题，这些系统如何表示和处理知识，这不是一个可以打补丁的**bug**。所以，我们看到这种情况正在发生，人们有时会说“哦，我们遇到了问题，有些事情非常糟糕”，然后你可以说“哦，让我通过为系统指令或开放者指令添加一些东西来修补它。”这有点像这些模型实际学习方式的**结构性属性**。所以我想说，这可能是我们目前做得不太对的一点。

<details>
<summary>Original English</summary>

**Mustafa Dani**: not easy to pinpoint like a specific things but again like you know this is just like my personal opinion and and maybe I have colleagues and and like other people like sharing this with me but uh I think we're underestimating how hard uh uh like jagged intelligence is to fix we're missing how like like understand like we're underestimating how much it matters and uh we talk about almost like people laugh and and and go you know like if if you have a model that does like a like a very difficult like math proof but has difficult time like counting like letters in a in a war. Uh as I said just people just laugh and and move on but but I think it actually like pointing at something like deep and unresolved about these system like the way that these systems kind of like you know represent unprocess knowledge and it's not a bug that you can patch. So definitely you know like like we we like we we see that you know this is happening you know like people sometimes you know oh like or or we have this problems that you know something is like awfully sad and then you can oh you know let me just like you know patch by adding something for the system instruction or the opener instruction a bit of a structural property of how these models actually learn. So I I would say this is probably one of the things that we're we're not getting it like super right at this point.

</details>

**Matt Turk**: 太棒了。目前AI研究中有什么被低估的想法？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. What is one idea in AI research right now that is underrated?

</details>

**Mustafa Dani**: 就像你提到的**持续学习**，它被低估了。我认为这绝对被低估了。正如我所说，你知道，有时问题会停留在探索模式，直到我们对某事有信心，然后它才会进入利用模式。我认为我们已经过了需要真正将其推向利用模式的时候。所以，也许**基础模型**现在本质上就像时间冻结一样，当训练结束时，一切都建立在这个冻结的模型之上，比如**RAG管道**、**微调工作流**和**检索系统**，以及所有这些复杂的**基础设施**都基于这些模型是冻结的假设。这是一个有点过于强烈的假设，我认为我们将会达到需要改变这些假设的地步，也许我们需要更积极地思考它，并推动它走向生产化。也许现在持续学习有点被低估了。

<details>
<summary>Original English</summary>

**Mustafa Dani**: Something that is underrated like you mentioned continue learning. I I think this is this is definitely underrated. As I said, you know, like sometimes the problem stays in the exploration mode uh until we are confident about something and then it goes to the exploitation mode. I I think we're past the time that we really had to push this to the exploitation. So maybe like foundation models are are essentially right now like frozen in time and like when the like the training ends, right? And then everything is like built on top of this frozen model like you know rag pipeline and and fine-tuning workflows and retrieval system and all these like elaborate like infrastructure is like um all based on this assumption that these models are frozen and uh it's a bit of a like a too much of a strong problem there assumption to make and and and I think like we are going to like get to the point that we need to change these assumptions and like maybe like we need to think about it a little bit more actively and have um pushing it toward like you know something that we actually push it to productionization and maybe it's a little bit like underrated right now like the continual learning.

</details>

**Matt Turk**: 所以你认为RAG会随着时间消失吗？

<details>
<summary>Original English</summary>

**Matt Turk**: So you think rag goes away over time?

</details>

**Mustafa Dani**: 它不会像今天这样，它会变得不同，但说它会完全消失，我不太确定。我说这话的一个原因是，RAG不仅仅是为模型带来新鲜信息，当它想解决关于事物当前状态的问题时，它还有**上下文学习**的功能。上下文中的信息与模型权重中的信息之间存在差异。**持续学习**和**RAG**在带来新鲜信息方面做着不同的事情。也许它会以某种方式改变，你知道，它不需要为所有事情都触发RAG，但我非常确定，仍将有一部分分布我们仍然会使用RAG。你知道，时间。

<details>
<summary>Original English</summary>

**Mustafa Dani**: It's not going to look like as is today and it's going to be different but like saying that it's going to go away completely. I'm I'm not sure about that. And and one of the reason that I say that is rag is not just about bringing like fresh information to the model when when it wants to kind of like solve a problem about like the current state of things, but it also has this kind of like in context learning and and there is a difference between in context learning like the information that you have in in the context of the model compared to the to the information that you have in the weight of the model. like continuous learning and and rag are are doing different things uh for bringing this fresh information. Maybe it changes in a way that you know like it doesn't need to trigger rag for like everything but I'm pretty sure that there going to be some tail of the distribution that we're going to do rag still for it you know like what's the time.

</details>

**Matt Turk**: 好的，最后几个热门观点，你认为人们对什么过于自信？

<details>
<summary>Original English</summary>

**Matt Turk**: all right last couple of hot takes what do you think people are too confident about.

</details>

**Mustafa Dani**: 人们认为推动技术方面就足够了，如果我们只是得到一个更聪明的模型，一切都会随之而来。在我看来，一个在技术问题上非常出色，但在其他所有方面都有**盲点**的AI版本，将无法在世界上创造有意义的进展。人们对此过于自信，认为一切都会随之而来，或者说其他一切都只是小事。我认为这是错误的。我们有**治理**，有**监管**，有**社会信任**，有例如**获取和利益分配**，以及即使是**机构能力**来吸收和适应这项技术。这些问题可能我们没有给予足够的关注，而这些问题如果不是比技术部分更难解决的话，也同样难以解决。它们真的很难，技术进步的速度肯定比世界发展这种机制的能力要快。这个差距正在变得越来越大，但我想说的是，这个领域需要同时处理这两件事。所以也许这就是其中之一。

<details>
<summary>Original English</summary>

**Mustafa Dani**: so people think that you know the pushing the technical side is uh is sufficient that if we just like get a model that is smarter uh everything is going to follow and and in my opinion like a version of AI that is like you really really brilliant at um like technical problems, but it has a like a blind spot about you know everything else. And that version is not going to be able to actually create meaningful prog like progress in in the war. And the fact that you know people kind of assume and and confident about like like they're confident about this that that kind of like you know everything is going to everything else is going to follow or uh uh or or just everything else is just like a small list. Um I think it's wrong like you know we have governance we have like you know regulation we have social trust we have like for example distribution of access and the benefit like in the world for for this technology and even the like you know the institutional capacity to to kind of like absorb and adapt this technology is is just like this is something that maybe we don't have enough um like attention to and uh and and these are not really solved problems if not harder than the technical part. They're they're really hard and like the pace of technical progress is definitely like like um currently running ahead of the world's capacity to to develop this kind of like you know mechanism uh and this gap is getting like you know bigger and bigger but what I'm saying is basically like you know the field needs to hold both things at once. So maybe that's uh yeah that's one of the things.

</details>

**Matt Turk**: 好的，最后一个，我不知道这算不算一个热门观点，或者只是给今天进入这个领域的人的建议。如果你今天从头开始，你会做什么？

<details>
<summary>Original English</summary>

**Matt Turk**: All right, and last one and I don't know if that's a hot take or maybe just advice for anybody entering the field today. If you were going to start from scratch today, what would you work on?

</details>

**Mustafa Dani**: 我不想从头开始。开始很难。我可以告诉你，有两件事，我认为花更多时间去做会很好，还有一件事我非常兴奋。我从我非常兴奋的事情开始说起，我想说短期内推动它会非常令人兴奋。我实际上正在努力甚至能够为这个方向做出贡献，那就是**超长周期任务**的完全自动化。例如，你有一台机器可以工作两周或一个月，今天的**Agent**非常令人印象深刻，演示也非常有市场。但存在一个**复合可靠性问题**，没有得到足够的讨论。例如，想象一下一个Agent需要执行100个顺序步骤才能完成一项任务，假设每个步骤有95%的成功率，这已经很棒了，你知道，鉴于我们今天拥有的模型，95%已经很不错了。那么，在没有单一故障的情况下完成整个任务的概率是0.95的100次方，这不到1%。这种数学计算非常残酷，对吧？而我所说的每一步95%的成功率，已经非常乐观了。长周期自动化并非不可能，但它需要每一步的**可靠性**、**错误恢复**以及当前系统可能不具备的水平。如果我们想要**社会信任**，并且让人们真正使用它，你知道，归根结底，人们不会体验到这些模型的平均性能，他们会体验到失败。如果你的模型犯了一个愚蠢的错误，它对信任造成的损害比100件正确的事情带来的好处更大，对吧？所以，这种长周期任务的可靠性是我们绝对需要的。正如我所说的，有两个更具哲学性的高层次问题，我肯定会致力于**接地问题**，以及我们如何构建健壮并与物理世界连接的AI系统。正如我所说，你知道，很快，数据的概念，你知道，如何使这些模型在自我改进方面非常出色，就变成了“我如何让这些模型在真实世界中接地”的问题。所以这绝对是，你知道，如果我们不积极思考它，就会成为自我改进的瓶颈。我们应该肯定地摆脱文本和像素中的这种统计模式。另一个可能有点相关的问题是，甚至思考智能本身的更好定义。这有点哲学，但它绝对是一个实际的问题。而且整个领域和我们，我们正在构建越来越多的我们没有真正定义的东西，你知道，我们正在努力使这些模型更智能，更聪明，但智能的定义是如此方便和模糊，以至于很难真正衡量有意义的进展，这与你关于评估的问题有关。这很好，你知道，我们有**代理**、**基准**、**分数**、**能力**，甚至还有**视频**，你知道，我觉得这超级有用。但归根结底，我们确实需要一种系统的方法来定义智能，这很难。再次，基于我们现在拥有的东西取得进展是好的，但在某个时候，真正明确目标和目标，然后以最快的速度朝着它前进变得更加重要。

<details>
<summary>Original English</summary>

**Mustafa Dani**: I don't want to start from scratch. It's hard to start. Um I can tell you like you know there there are two things that I I think like you know would be nice to spend more time on it and there's one thing that I'm like very excited about it. I start from the the things that I'm like really excited about it and and I would say like you know short term it's like really exciting to push it. I am actually trying to even like you know be able to contribute to to this direction and and that's like full automation of like super long horizon task things that you know like you have a machine working for maybe like two weeks one months like the agents today are are very impressive right and and and the demos are like very like very marketable but like there's this compounding reliability problem that doesn't get talked about like you know enough and um and for example like imagine if an agent has to take 100 sequential steps to complete complete a task and imagine if each step has 95% of like success rate which is like great you know like I like given the the the the the models that we have today 95% is like really good the probability of um completing the whole task without a single failure is like 0.95 to the power of 100 which which is like less than 1%. and and and this math is like brutal, right? Like you know and and this like 95 per step 95% per step as I said is like very very optimistic. long horizon automation is like u like definitely isn't impossible but it requires a level of like you know per step reliability and and like you know error recovery and and and the current system maybe don't have it and uh if if we want like you know social trust and and you know basically having like people like really using it you know at the end of the day like like people don't experience average performance of these models then they experience like the failures if you have your model doing a dumb mistake the the damage in the trust that it makes is like bigger than than like you know the benefit of getting 100 things right right like 100 imperfect uh things right so this like reliability in this like long horizon task is something that we definitely need the kind of like side of as I said you know two two kind of like more philosophical high level things I would definitely like work on grounding problem and how we can build AI system that are robust and connected to physical world as I said you know like like soon like the the concept of data like you know how to kind of like you know enable these models to kind of like you know be very good at like self-improvement becomes how can I ground these models in in real war so this is definitely like something that you know would be the bottleneck of self-improvement if we don't actively think about it we should definitely move away from like this statistical pattern in text and pixels and the other things that is uh maybe kind of like you know related is um even thinking about you know a better definition of like intelligence itself right a little bit like philosophical but um but it's a definitely a practical practical question. Uh and uh like the whole field and and us you're we're building uh like more and more like something that we haven't like really defined you know like like we're we're trying to kind of make these models smarter and more intelligent but like the definition of intelligent is just so handy and fuzzy that it's hard to actually kind of like you know measure the meaningful progress like which is related to your question that about you know like how about like evaluations. It's good, you know, we have proxies, benchmarks, scores, capabilities and and and even vides, you know, which is I I find like super useful, but at the end of the day, uh we really need a a systematic way of uh maybe defining intelligence that that is hard. And uh again, like making progress based on what we have right now is good, but at some point that becomes a little bit more important to really pinpoint that, you know, what is the target and what is the goal and then uh push toward that like like uh with maximum speed.

</details>

**Matt Turk**: 好的，Mustafa，这是一次非常棒的对话。非常感谢你抽出时间陪伴我们。非常享受。非常感谢。

<details>
<summary>Original English</summary>

**Matt Turk**: All right, Mustafa, it's been a absolutely fantastic conversation. Thank you so much for spending time with us. Really enjoyed it. Really appreciate it. Thank you.

</details>

**Mustafa Dani**: 是的，非常感谢你的邀请。聊天很愉快，谢谢。

<details>
<summary>Original English</summary>

**Mustafa Dani**: Yeah, thank you so much for having me. It was like fun to to chat and uh thanks for for the invite.

</details>

**Matt Turk**: 大家好，我是Matt Turk。感谢收听这期**Matt播客**。如果你喜欢这期节目，如果你还没有订阅，我们将非常感激你考虑订阅，或者在你观看或收听这期节目的任何平台上留下积极的评论。这确实有助于我们建立播客并邀请到优秀的嘉宾。谢谢，下期节目再见。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks and see you at the next episode.

</details>