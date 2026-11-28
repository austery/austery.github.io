---
author: AI Engineer
date: '2026-07-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1P1hJ36rxM0
speaker: AI Engineer
tags:
  - code-generation
  - self-play
  - multimodal-model
  - scientific-discovery
title: 从代码生成到自我博弈：Google DeepMind 副总裁 Benoit Schillings 谈 AI 编程与未来科学
summary: Google DeepMind 研究副总裁 Benoit Schillings 探讨了软件工程从手工编写代码向 AI 驱动的转变，指出未来代码编写将变得几乎免费，开发重点将转向系统架构、安全漏洞预防及自我博弈技术，并展望了 AI 在化学、生物等科学领域的应用潜力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google DeepMind
  - Google X
products_models:
  - Gemini
  - AlphaZero
  - Waymo
  - Google Glass
media_books: []
status: evergreen
---
### 跨越边界：从谷歌 X 实验室到 DeepMind

大家好，早上好。非常高兴来到这里并有机会与大家交流。我是 **Benoit Schillings**。在机器学习领域，我其实算是一个“新手”。直到一年半以前，我还在 **Google X**（X 实验室，即现在的 Alphabet X）工作。我们研发过像 **Waymo**（自动驾驶汽车项目，如今在街头巷尾随处可见）这样的项目，也做过像 **Google Glass**（谷歌眼镜）这样的产品。我们经历过成功，也遭遇过失败，但对我而言，这在许多方面都是一次非常有趣的、形成性的经历，它教会了我如何在像 **Google DeepMind** 这样的机构里带领一个研究团队。

我现在带领着一支优秀的团队。我们在 Google DeepMind 的基本目标，就是开发出任何能让 **Gemini** 在未来一个月到一年内变得更出色的技术。之所以说“一个月”，是因为如果你开始着手下周就需要的东西，那完全是另外一种不同性质的工作；而说“一年”，是因为我认为没有人能真正预测那么远的事情。

在这一角色下，我们做了很多事情。其中很大一部分工作与**代码**相关，这也是我今天演讲的主题。但我们也会针对模型的**推理能力演进**开展大量研究，或者进行**网络拓扑结构**（Topology Research: 研究神经网络不同连接方式和结构对模型性能影响的领域）研究，探索哪些新型网络能够带来更好的性能。此外，我们还在**强化学习**（Reinforcement Learning: 通过与环境交互并根据奖励/惩罚进行学习的机器学习方法）的科学原理方面开展基础性工作，这对于我们今天用机器学习所做的一切都是至关重要的。

<details>
<summary>Original English</summary>

All right, good morning. Uh this is really quite exciting to be here and have a chance to to speak with all of you. Uh my name is Benoit Schillings. I'm actually a bit of a noob when it comes to to machine learning. Till a year and a half ago, I was working for Google X which some of you may know. We've done things like Waymo, which seems to be at every street corner now. Uh we also do things like Glass. So, you know, we we had a mix of hit and success. But in many ways this was for me an interesting formative experience on how to run a research team in a place like deep mind.
I do have an incredible team. Uh my team goal in deep mind is basically to develop whatever technology will be needed to make Gemini incredible between one months and one year from now. So one month because if you start to work on what is needed in one week that's a very different type of job and one year because I don't think anybody can really predict anything that far. So that's already pretty ambitious in my opinion to think about things that would happen one year in the future.
We do many things under that role. Uh a lot of it is related to code which will be the main subject of my talk today. uh but we also do a lot of research on what is the evolution of reasoning for models for instance or we do topology research what are new type of network that might bring better performance uh we do fundamental work in the science of reinforcement learning which is so fundamental to what we're doing today with ML

</details>

### 软件开发的三大历史演进时代

让我们先来聊聊软件开发的起源故事。我们在 2018 年在 X 实验室启动了一个名为 **Pitchfork** 的项目，旨在探索机器学习如何切实改善代码编写的方式。这在当时非常有趣，因为在 2018 年我们在谷歌展示这个项目时，老实说根本没人理会我们。那时候大家的态度普遍是：“为什么会需要机器学习来写代码？”同时，我认为我们自己也完全低估了这一技术的发展速度。

在项目启动之初，我们的想法是研究如何加速代码的演进，研究如何消除那些拖慢代码开发速度的微小变化。例如，一个微小的修改如果需要经过长达三天的代码审查，这就会严重拉长周期。当时有些人谈论起**“氛围写代码”**（Vibe Coding: 指用自然语言直接描述需求，让 AI 生成代码的开发模式），老实说，我当时对此完全是不屑一顾的。我觉得：“这正是我们需要编程语言的原因，英语可不是什么编程语言。”好吧，我承认在这点上我确实想错了。但当时我们感受到的阻力，让我想起了我自己的职业生涯在面对变革时是多么保守。

我已经写了 45 年的代码。我的起点是为 **Apple II** 和 **Commodore 64** 编写电子游戏。所以，我的专业底子是编写**汇编语言**（Assembly Language: 与机器指令一一对应的低级编程语言）。当你花了很长时间编写汇编语言后，你会带着极大的怀疑去审视**编译器**，对吧？你会怀疑这些东西真的能正常工作吗？后来，当你转向 **C++** 并使用编译器时，你又会把**垃圾回收语言**（Garbage-collected Language: 具有自动内存管理功能的编程语言）看作是：“哼，那根本不是真正的编程，你必须自己管理内存。”而今天，我却在使用 **Python** 和 AI 辅助编程。

我认为软件行业经历了几个不同的时代：
* **机器限制时代**：也就是我开始写代码的那个时代，物理机器是根本性的限制因素。我们当时需要做大量的工作，只为了从这些机器中榨取出最后一丝性能。在那个写汇编语言的时代，你编写代码时必须极其精准。
* **模块化云时代**：随着计算变得越来越便宜，我们转向了现代的云时代。在这个时代，获取极致的性能不再是最关键的方面，你可以用暴力破解的方式解决许多问题。但真正的限制因素变成了我们的**模块化设计**能力。在这个时代，核心在于你将如何构建库、如何编写函数、如何将问题分解为长期可维护的模块。
* **AI 前沿时代**：以往限制软件过程的核心瓶颈在于**人类大脑**。一个普通人类在短时记忆中通常只能同时处理 7 到 9 个**标记**（Token: 认知或计算中的基本信息单元）。尽管人类处理的标记信息非常丰富，但与现代机器学习相比，这根本无法同日而语，因为 AI 的上下文窗口很快就会变得无穷大。这种人类的根本限制决定了过去软件的编写方式。而现在，这个时代已经结束，我们正在转向全新的 AI 前沿。

<details>
<summary>Original English</summary>

let's do a bit of an origin story Um, we started the project at X named Pitchfork uh in 2018 which was aimed at looking at how ML could really improve the way code is being written. And this was very interesting because in 2018 when we presented that at Google honestly nobody would give us the time of day. uh there was that point like why would you ever need ML to to write code. Um at the same time I think that we totally underestimated how fast this could go.
When we did that project originally the idea was to look at how we could speed up the evolution of a piece of code. How could we make many of those small changes which slows down code speed development? you know the small edit which requires a review that takes three days and how we could compress that cycle. Some people were talking about vibe coding writing code in English and at the time honestly I totally dismissed that. I was that's why we have programming language. English is not a programming language. Well I I guess I was pretty wrong on that front. But the resistance we felt at the time reminded me of how my own career was pretty resistive to to change. Um I've been writing code for 45 years. Uh I started by writing video game for Apple 2 and Commodore 64. So uh my formation was to write assembly language. And when you spend a long time writing assembly language, you look at compilers with a lot of suspicion, right? are those things really working correctly? And then when you switch to C++ and use compiler, you lose you look at garbage collected languages as this h that's not real programming. You need to manage your memory. Well, today I use Python and V coding. So even old dogs can learn new tricks. So uh but I I I do understand what happened there.
I think that we have a number of eras in what happened with software and and the first one was you know the one where I started writing code where the fundamental limit was really the machine and there was a lot of work to go and extract the last ounce of power out of those machine and that was the days of assembly language where you really needed to be incredibly accurate in the way you were writing code computing became much cheaper and we switched to the modern cloud era where getting the best performance is not the most critical aspect. You can actually brute force many problems but really what became the limiting factor was the ability for us to design in a modular way. You know this was the era where software was write it only once and this was this whole idea of how are you going to build libraries? How are you going to write functions? How are you going to break down that problem into something that is long-term manageable?
The limitation there and that determine a lot of how our software process are working where actually the human brain. Uh a traditional human typical human is able to get the context between seven and nine tokens. I mean we have very rich tokens but you compare that to modern ML where the context is basically going to be infinite pretty soon. uh that fundamental limitation of human determined a lot of how software was being written. This is over and we're switching now to that AI frontier where really writing the code is not the challenge anymore. Uh I'll speak some more about it. But the bottlenecks are really how do you ensure that that code is what you really wanted because writing the code is easy but getting what is needed for a specific problem can be much harder to to specify.
So humans at least in the near future will be that role of architecture or thinking of what are really the implication of that piece of code. I'm getting the ML to to design. Inductive thinking is another category where I think humans still have a very clear edge which is to look at a system in a much wider context and to be able to detect patterns and from those pattern take some decision.

</details>

### 数据枯竭与自我博弈的全新纪元

我们目前处于什么阶段？答案是：**超人的语法生成能力**（Superhuman Syntax Generation: 超越人类水平的代码语法和结构自动生成能力）。上一次我让 Gemini 帮我写一个函数，然后我看着那个函数说“我能写得比它更好”是什么时候？这种时代已经彻底结束了。编写代码的具体细节和琐碎工作，虽然你仍可以去争论、去反驳、去寻找反例，但那个手工编码的时代确实已经一去不复返了。

然而，我们在**多步骤代码库管理**上仍有大量工作要做。软件工程不仅仅是编写代码。当你第一次加入一家公司，发现代码库里有 3500 万行 PHP 代码，而你需要对其进行修改时，你才会真正明白什么是**软件工程**。这是我们目前的 Frontier 模型正在不断取得进展的地方。如何管理这种极度的复杂性，并将其拆解为可管理的部分，这正是前沿技术仍在努力突破的难关。这甚至一路延伸到了系统架构层面。以谷歌的系统架构为例，谢天谢地我们有像 **Jeff Dean** 这样的传奇人物作为核心架构师。这种高维度的思考涵盖了如何进行硬件优化、如何管理安全性，以及如何构建一个让系统在 10 年后不会让你充满懊悔的架构。

代码是一个非常独特的问题，这也是我们最初针对它开展 Pitchfork 项目的原因。首先，代码拥有海量的数据，你可以直接去爬取整个 GitHub；其次，代码是一个**可验证性强**的领域。你可以运行一段代码，编译它，并运行单元测试。因此，判断模型生成的代码是否正确是相对容易实现的。

然而，我们今天面临的现实是：**训练数据已经枯竭**。我认为如今添加到 GitHub 的新代码中，有 80% 都是机器生成的。因此，依靠挖掘人类编写的代码来训练模型的模式正在走向终结。但好消息是，我们可以开展**自我博弈**（Self-play: 模型通过自己与自己对抗、自己生成问题并验证解答来提升能力的技术），这也是我们 DeepMind 一直非常热衷的方向。大家都知道 **AlphaZero**，它在没有任何人类知识输入的情况下，仅通过自我博弈就成为了超越人类的围棋和国际象棋大师。现在的 AI 编程 Frontier 模型也已经到了这个阶段，它们能够自己创建挑战，判断答案的有效性，甚至在一定程度上评估架构。这种进行数亿小时自我博弈来编写代码的能力，将带我们进入下一个层级。

<details>
<summary>Original English</summary>

So where are we today? Um, superhuman syntax generation.
When is the last time I got Gemini to write a function for me? And I looked at the function and I was like, I can do that better. It's over. Uh, I think that the minutia of code writing, I mean, you can fight, you can argue, you can find counter example, but that time is is gone. Where we still have a lot of work to do is multi-step code base. Uh software engineering is not about writing code. Software engineering is the first time you join a company and you realize that there are 35 million lines of PHP in the codebase and that you need to make some changes. That that's the day you understand what software engineering is and that's a place where our models today or frontier models are progressing. But this ability to manage that extreme complexity and break it down into man manageable pieces is a place where the frontier is still moving. Um it goes all the way to architecture. You look at I don't know the Google architecture. Thanks God we have Jeff Dean which was you know the the key architect there. But that's the level of thinking which has many implication which can go from how do you do hardware optimization? How do you manage security? How do you build a system so that 10 years later you're not full of regrets? And I think this is really the the range of progress we are working on today. So code is over but there's plenty to do. There's plenty of progress to be made.
Now code is a very unique problem and in some way that's the reason we we did pitchfork on this. Um, first of all, code is a lot of data. There are other domains where you can find a lot of data to train your model, but code was so incredible. You could go and go on GitHub and start to to scrape GitHub. So, this was one of those problem where the amount of training data was a very unique situation. It is also a domain where doing verification is reasonable. You can run a piece of code, you can compile it, you can have unit test. So the ability to figure out is the model generating something correct was something that was pretty reasonable to do. That brought us where we are today. But today what happened is that we run out of training data. I think that 80% of the new code added to GitHub today is machine generated. So the notion of human bringing some knowledge that can be used for mining and to train model is reaching an end. But the good news is that we can do selfplay and selfplay is something we always liked a lot at deep mind. I suppose all know Alpha Zero. Alpha Zero became a superhuman go and chess player without any human knowledge just by playing against itself. We are now at that stage where Frontier model for code are able to do the same where they can create their own challenge. They can judge the validity of the answer. they can even to some extent judge the architecture. So that ability to do those hundreds of millions of hours of selfplay writing code is the thing that will bring us to the to the next layer.

</details>

### 免费代码时代的经济学与主动防御

试想这样一个实验：把一个极其聪明的软件工程师关在房间里两年，只提供披萨，并给他一个任务——成为更优秀的软件工程师。作为一个人，你会怎么做？你会给自己设定一些可以验证的挑战，然后不断地针对这些挑战进行编码和开发。这正是我们对 AI 所做的。这本质上成了一个我们需要投入多少算力、能有多少自我博弈时间的问题。

因此，**编程的经济学规律**正在发生剧变。我们过去的整个软件工程文化、基础设施和公司生态，都是基于“编写代码是其中最难、最昂贵的部分”这一假设建立起来的。而现在，我们进入了一个编写代码几乎是免费的世界。这意味着，我们将看到所产生的代码量迎来**爆炸式增长**。

这带来了一些严峻的影响：
* **系统设计的微观合理性**：面对堆积如山、甚至是由系统动态生成的代码，我们如何确保系统在微观层面依然运行工作且安全可靠？这是人类未来非常重要的角色。
* **无人类阅读的代码库**：我们虽然在编写代码，但已经不再去阅读它们了。虽然我们现在还有代码审查，但我预测，在一年内，我们将完全让 Gemini 或其他模型来生成代码，且**没有任何人会去真正阅读它**。这就像编译器一样——现在还有谁会去检查编译器输出的汇编代码呢？代码的命运也是如此。

这引出了一个新的问题：我们需要建立什么样的新流程来保持系统的可维护性？这就需要引入**主动护栏**（Active Guardrails）。大家一定都看过有关 Google DeepMind 的 AI 系统在一段代码中检测出大量安全漏洞的新闻。虽然大家都在争先恐后地去修补这些漏洞，但我认为这将是一个无休止的过程。模型会发现一层漏洞，我们去修复它，然后模型变得更聪明，走得更深，发现更隐蔽的漏洞。因此，我的团队正在积极开展工作：与其在检测到漏洞后再去建议修复，不如**从一开始就教会模型编写正确的代码**。这非常困难，因为这高度依赖于上下文。

<details>
<summary>Original English</summary>

You know, it's interesting. Um do the experiment. Take a a brilliant software engineer, lock him in a room, lock him or her in a room for two years and feed pizza and give the mission you need to become a better software engineer. What do you do as a person? you you give yourself some challenges, challenges that you can verify and you keep working and coding on those challenges. We can do the same here. So this is an issue of how much compute, how much selfplay time we can have. But that will bring the horizon of how far we go in superhuman coding.
So the economics of code are changing dramatically. You know, as I say, we developed a whole software engineering culture and infrastructure and set of companies based on the assumption that writing code was the hard part. That this was the expensive part. We're now in a world where writing code is free or nearly free. That's why I've got the tilda there. That means that the amount of code that we're going to see produced is going to explode. And there are some hard implications to that. First is the question of design and adequacy. How in front of that mountain of code which will be written or written dynamically, how do we keep systems which works and are reliable at the microscopic level? Great role for human.
It is also the issue that you know we're writing code and we're not reading it very much anymore. I mean I know we still have code review but I would predict that in one year we'll let Gemini or other model generate the code and nobody will actually look at it. You know it's similar to compilers who still check the assembly output of their compiler and maybe someone there but that's probably the end of it. So the same thing is going to happen to code and that brings some question of what are the new process that we need to put in place to keep that manageable and that's where I've got a [clears throat] a bit of a list active guard rails. I mean you've all seen the news of mythos looking at a piece of code and detecting an unreasonable number of vulnerability in that code. there is a rush to go and patch those vulnerability but I think that's going to be a neverending process you know we're going to get a certain layer of vulnerability discovered by models we're going to fix those models will get smarter they will go a bit deeper and find even more subtle vulnerability so I think that the first aspect is that we need to think at least as much about code security and the implication of a piece of code than on the code writing itself and the grail and you know something my team is working actively on is instead of detecting the vulnerability and then suggesting some fix how about teaching model to write correct things from the start and that is very very hard to do because it is very context dependent

</details>

### 归纳式架构、代码链推理与面向模型的新型语言

另一个维度是**归纳式架构**（Inductive Architecture）。我认为目前的模型在知识迁移、将一个领域的知识应用到另一个领域、或者寻找两个概念的交集以进行演绎推理方面，表现得依然不够好。如果我们真的想用机器学习编写极其复杂的软件系统，这就必须是我们需要教会 AI 的一项技能。其中一个关键方面是真正教会模型如何在面对复杂问题时进行**正确规划**。你如何审视一个极其复杂的问题，并决定采取何种正确的分解方式，从而为问题的解决带来最清晰的逻辑或最高的正确性？

我们同样需要改变评估的方式。在我看来，**SWE-bench**（SWE-bench: 评估 AI 智能体解决真实软件工程问题能力的基准测试，转写中语音误识为 threebench）虽然非常出名，但它在我的标准里只能评估一小部分能力。它仅仅验证了一段代码是否能够运行并产生正确的输出，但这只是软件工程中微不足道的一部分。

我们需要在评估基准中加入更多**开放式问题**。我非常喜欢**文本压缩**（Text Compression）这个问题：每个字符需要多少个比特？你能把压缩做到多极限？这其实是一个非常容易编写的评估。你只需给模型一段 10MB 的代码，告诉它：“写出你能做到的最好的无损压缩器。”在这种情况下，损失函数就是：压缩后文件的大小加上源代码本身的体积。这类问题是永无止境的，它们会迫使模型去做一些新颖的尝试，例如创造出完全全新的算法。

我们目前正在跨入这个阶段。编写代码或开展软件工程，不再是简单地把思考当成一条**标记链**（Chain of Tokens）。在今天，思考和推理本质上是一条**代码链**（Chain of Code: 将思考步骤转化为可执行代码并运行，从而提升推理能力的技术），这在提升模型能力方面已经取得了巨大成功。然而，人类在思考问题时要复杂得多。我一直认为，编写代码是一项非常**具象化/视觉化**的活动，这可以是你正在做的事情的框图，也可以是数据在代码中的流动过程。但如果说代码仅仅是模型吐出来的一组标记，那么我认为这种认知只能带我们走到特定的阶段。

在 Google Gemini，我们从一开始就做出了一个明确的选择：它必须是一个**多模态模型**（Multimodal Model）。文本只是 Gemini 能够处理的模态之一。我们开始探索模型如何通过空间或动态表征来思考并解决问题，这将成为未来的核心必备能力。

另一个有趣的问题是：**现在是不是该为模型创造一种全新的语言了？** 现有的 Python 等语言都是为人类发明的，它们在编写安全或可靠的代码方面表现得并不算好。它们用来写写代码还行，但绝对不是最佳选择。既然编写代码的痛苦对模型来说已经不复存在，我们为什么不通过采用**强类型语言**（Strongly Typed Language）或者从 **Lean**（Lean: 一种用于定理证明和交互式定理证明的函数式编程语言）中汲取灵感，让编写代码变得更难呢？通过这种设计，我们从根本上将保证正确性的重担交给了模型。未来的语言不需要是人类可读的，我认为这以后已经无关紧要了。

<details>
<summary>Original English</summary>

the other aspect is that you know that's what I call inductive architecture uh I think that models today are still not very good at transferring knowledge of taking knowledge from one domain and applying it to another one or taking two concepts and finding the intersection of those context to be those context to be able to do deductive thinking. If we really want to write those very complex software system using ML that is a skill that we need to teach and you know one aspect of that is to really teach models how to do correct planning in front of a problem. How do you look at a very complex problem and decide what is the right decomposition of that problem that will bring the best clarity or correctness to the to the problem.
We also need to change the way we do evaluation. I mean u threebench is infamous in in my book because threebench verifies if a piece of code runs and produce the right output. That's only a small part of as I mentioned earlier of code engineering. So for instance, I think that we need some problems much more in those benchmarks that we use which are open-ended problem. I I'll give an example. Uh I love the question of text compression. How many bits per character do you need and how far can you go? So that's a very simple eval to to write. You just take a piece of 10 megabyte of code and you tell the model write the best compressor you can that is lossless and the loss function in that case will be you know the size of the compressed file plus the size of the source code that's never ending I mean those problems are I think what's going to force those model to do novel things like creating totally new algorithmic for instance and I I think we're now getting to that stage
Writing code or doing software engineering is not thinking as a chain of tokens. Thinking and reasoning today is chain of code which has been you know very successful and improve models a lot. But humans of course are much more complex in the way they think about problems. I always think that code writing is a very visual activity and that can be I don't know the block diagram of what you're doing or the flow of data through your code. uh but saying that code will be just a set of token that you emit that are going to be the code I think goes only up to a certain point that's a very interesting aspect to what we do at Google Gemini we made that choice from the onset that this would be a multimodal model that you know text was only one of the modality that Gemini would be able to apply and we're starting to see you know how can a model start to think in term of spatial or dynamic representation to to solve problem and I think that's going to become a must have
another interesting question is is this time to create a new language for models Python you name it have been invented for humans and those language are not very good to write safe or reliable code I mean they're great to write code but they're certainly not the the best thing I think We're getting to the point where since the pain of writing the code does not exist anymore. How about we make writing the code much harder by having you know very strongly typed languages or you know some inspiration from lean on how to write code that by design it's not going to be perfect. I mean program proof is something which has some limits but at least putting the burden of correctness on the model. So I don't know if we have some language designers here, but I I I think there's something really to be done there and it doesn't need to be human readable. I I don't think that that will matter anymore.

</details>

### 科学发现的新前沿：从代码到原子的跨越

超越代码之后，**代码是一门用于解决问题的通用语言**。我们正在看到，在代码中快速进行实验的能力正在迅速冲击其他领域，因为做实验的成本基本变为了零。我认为，**代码编写与原子或科学的交汇**是我们正在开拓的另一个巨大前沿，这也是真正能够涌现全新事物的领域。

其中有两个领域让我感到格外兴奋：
* **化学科学的复杂性突破**：作为人类，我们并不真正理解化学，或者说我们只理解化学中极小的一部分。一旦你的分子中包含超过 20 个原子，我们就会对它的行为一无所知。在这个领域，我们将见证令人难以置信的新事物涌现。一旦你能够将 10,000 个原子组合在一起，那看起来就像是生命了。那么，利用这 10,000 个原子，你还能做些什么别的事情？
* **生物学的无文档工程逆向**：你可能已经听过很多关于它的讨论。但在我看来，生物学是这样一个案例：**大自然做了一次极其出色的工程设计，但却做了一份糟糕透顶的文档记录**。但我们现在能够突破这一点，模型正在找出对我们来说难以琢磨的复杂关系，这将开启不可思议的大门。

最后，是所谓的**“我们看不见的黄金”**（The Gold We Cannot See: 指由于人类自身认知局限和进化偏见而忽略的潜在最优解或新科学规律）。人类在看待“正确解决方案”时有着极强的偏见。我们是演化训练的结果，这种训练的核心是为了帮助我们在丛林中生存，而不是为了做量子计算。因此，即使我们非常聪明且富有创新精神，但也存在着大量我们根本无法看到或感知到的进步和突破。机器学习提供了一个审视这些问题的全新视角，我们将迎来“天啊，原来真相一直就在我们眼前，我们却视而不见”的顿悟时刻。令人兴奋的时代就在前方。非常感谢大家。

<details>
<summary>Original English</summary>

So beyond code, um code is a universal language to solve problems. I think that what we're starting to see is this ability to experiment very quickly in code is impacting other domain very quickly because doing experiment becomes basically free. So I think that looking at that intersection of code writing and atoms or science is another big front that we are opening that is the place where true novelty is going to appear.
two which are especially exciting for me is chemistry. Um you know as humans we do not understand chemistry or we understand a very very small sliver of chemistry. Once you have more than 20 atoms in your molecule it's like wow we don't know what that thing is going to do. I think we're going to see incredible things emerging out of that. I mean once you are able to put 10,000 atom together that starts to look like life. So what are all the other things you can do with 10,000 atoms?
Biology. You probably heard plenty about it, but you know, biology is the case of nature did an incredible engineering job and terrible job at documentation. Um, but we can crack through that now. Models are able to find those relationship that might be elusive for us. So I think that that is something that will open incredible door.
And then there is what I call the gold we cannot see. Humans are incredibly biased in what we feel is the correct solution. I mean, we're the result of an evolutionary training that help us survive in the jungle, right? Not doing quantum computing. So, I think that even though we can be brilliant and innovative, there are whole bunch of progress and breakthrough that can be done which we just cannot see or perceive. If I had more time, I would give some examples. I think that's one of the thing where ML is such a different viewpoint on many of those problems that we're going to get the oh my god this was in front of us the whole time and we could not see it. So exciting times ahead. Thank you very much.

</details>