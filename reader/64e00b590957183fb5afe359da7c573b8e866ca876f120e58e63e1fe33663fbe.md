---
author: Latent Space
date: '2026-03-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KSCCKCz2x04
speaker: Latent Space
tags:
  - materials-discovery
  - active-learning
  - quantum-chemistry
  - chemical-bonding
  - data-driven-methods
title: AI驱动的材料发现：挑战、机遇与学术界的未来
summary: 麻省理工学院Heather Kulic教授探讨AI在材料科学中的应用，包括加速新材料发现、韧性塑料的意外突破以及金属有机框架的多目标优化。她强调了化学基础知识的重要性，指出AI在预测复杂化学反应和处理多样化数据方面的挑战，并展望了高通量实验和自动化实验室的未来。Kulic教授还分享了学术界如何在计算资源有限的情况下，通过独特的问题视角与科技巨头竞争，并推荐了其团队开发的Mole Simplifier开源工具。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - MIT
  - AstraZeneca
  - Microsoft
  - Meta
  - National Science Foundation
products_models:
  - GPT
  - AlphaFold
  - Mole Simplifier
  - Moth Simplify
media_books:
  - Science
status: evergreen
---
### 引言：AI与化学学习的平衡

**主持人**: 有一种观点认为，既然像 **GPT** 这样的AI模型已经对化学、物理等领域有博士级别的理解，那我们为什么还要费力去学习这些知识呢？我的个人经验是，尽管 **ChatGPT** 在维基百科级别的化学知识方面表现出色，但当我要求它设计一个包含22个原子的配体（ligand），并结合到过渡金属络合物中时，它始终无法给出正确答案。一个经验丰富的化学家能在几秒钟内完成这个任务。虽然 **LLM** 可以提供很多你不熟悉领域的见解，帮助你学习化学基础知识，甚至在判断模型对错方面提供帮助，但我认为我们必须从某个基础开始，将AI作为工具，而不是盲目依赖它。

<details>
<summary>Original English</summary>

**Host**: There's a school of thought that why should I bother to learn chemistry or physics or whatever when GPT has PhD level understanding of that. My personal experience is that ChatGPT is super good at Wikipedia level chemistry knowledge. I'm really interested in molecular design. How do you find a new ligand that can go into a transition metal complex? What that means is it's some combination of atoms and it's going to bind to the metal and it's going to change its properties. The thing I constantly do every time an LLM is updated is I just ask it, please design me a ligand that has 22 atoms. I can never get an answer that has 22 atoms. So then you could try a range and see how many times you can get a range. That's a trivial thing, but that's something that an expert chemist could do in a second. There are really good introductions to chemistry that I think you can get through conversations with an **LLM**. You can get a lot of insight into an area you're unfamiliar with. And for sure things have improved a lot. When I first tried typing in, which exchange correlation functional should I use for this type of chemistry? The answers were completely wrong. They looked right, but they were completely wrong. Things have gotten better because that knowledge is out there on the internet. It's in the training data, but I think there's a lot of things that you should learn chemistry well enough to know when these models are right or wrong. If you don't know any chemistry at all, it's hard to know if you're assessing correctly. But I think that there are a lot of things that you don't have time to do a deep dive into that you can now get from an **LLM** that can augment knowledge. But I think you have to start from somewhere and then use it as a tool rather than starting from zero and relying blindly on what an **LLM** will say. But one of my favorite things if someone can get in one shot an **LLM** to generate me a 22 atom ligand I would love to see it.

</details>

**主持人**: 大家好，今天我们非常荣幸邀请到麻省理工学院（**MIT**）化学工程教授 **Heather Kulic**。Heather在材料科学和计算化学领域做出了杰出贡献。她几乎整个职业生涯都在探索数据驱动方法和 **AI** 在改善材料方面的应用。她对哪些方法有效以及如何利用这些方法解决问题有独到的见解。Heather，能否分享一个你认为在 **AI** 工程领域最酷的成就？

<details>
<summary>Original English</summary>

**Host**: All right, we're really excited to have Heather Kulic here. She's a professor of chemical engineering at **MIT**. Heather has done some amazing work in **material science** and **computational chemistry**. But we're particularly excited to have her here today because she has for almost her entire career been working on the intersection of using **data-driven methods AI** and using applying them to improve materials and understanding materials. And she has a lot of really interesting opinions about what works and how do you approach these problems to get the most out of them. So, we're really excited to have you here and maybe to get started, can you just tell us about one of the coolest things you've done in your opinion for an **AI** engineering audience?

</details>

### AI加速材料发现：韧性塑料的突破

**Heather Kulic**: 当然。我的研究团队主要致力于加速新材料的发现。最初，我们只是利用 **AI** 来加速计算模型进行的预测。但我们经常被问到的问题是：“AI带来了什么惊喜？有什么是即使是非常聪明的化学家或材料科学家也无法预知的？” 最近，我们成功展示了一个很好的例子：我们利用人工智能筛选了数万种材料，其中每次实验在实验室中都需要数月甚至数年。通过 **AI**，我们发现了一种意想不到的**量子力学现象**，使得**聚合物网络**（即**塑料**）的韧性提高了四倍。当我们将 **AI** 的设计方案展示给实验人员时，他们非常惊讶，表示自己绝不可能想到这种设计。最终，我们在实验室中成功制备了这种更坚韧的材料。这在应用上意义重大，因为如果能制造出更坚韧的**塑料**，就能延长其使用寿命，从而解决**塑料**整体耐用性方面的一些问题。我认为这是 **AI** 在材料发现领域前景的一个实例。

<details>
<summary>Original English</summary>

**Heather Kulic**: Yeah, so my group works a lot in accelerated discovery of new materials. When I first started out, we were just really using **AI** to make predictions we'd normally make with computational models, just make them faster. But the question I would often get when we were doing that was, okay, but what's surprising? What's something from **AI** that I wouldn't have already known if I were a really smart chemist or a really smart material scientist? And, you know, you make all these computational predictions. Has anyone actually made in the lab something that you predicted? Recently I was able to do a really nice demonstration where the answer to both of those questions was very clear from the work. So we were able to screen with **artificial intelligence** a set of thousands, tens of thousands of materials where each individual experiment, if it were done in the lab, would have taken months to years. And through **AI**, we uncovered this unexpected **chemical phenomenon** that led to an emergent property in what's known as a **polymer network**. So **plastics**, that would make the polymer about four times tougher. And when we showed the design that **AI** had come up with to the experimentalists, they were really surprised. They would have never come on this on their own. And then we were able to convince them to make it in the lab. And in fact, it was this tougher material. And where this has applications is if we can make **plastics** tougher, then we can get more use out of them and it'll ultimately address some of the problems we have with overall durability and use of **plastics**. So I think that's an example of some of the promise of **AI** in materials discovery.

</details>

**主持人**: 能否深入解释一下这个令人惊讶的化学发现？

<details>
<summary>Original English</summary>

**Host**: Cool. So, can you dig into that a little bit? What was the surprising chemical discovery there?

</details>

**Heather Kulic**: 很难在不深入化学细节的情况下解释，但基本上，这些分子在断裂时，能使它们所在的整体结构变得更坚韧。材料的一小部分断裂，有助于耗散力。通常，你会认为通过制造一个“铰链”来让这些小分子更容易断裂，使它们可以“剥开”而不是“滑开”。但我们发现，这是一种纯粹的**量子力学现象**。我们无法基于任何其他方式预测它，因为电子的运动方式不同，使得分子在断裂时变得更加稳定。这些概念类似于催化剂和酶的工作原理，但以前从未在聚合物材料中被证实。

<details>
<summary>Original English</summary>

**Heather Kulic**: It's hard for me to think about how to explain it without getting too deep into the chemistry, but basically these are molecules that have to break apart. And when they break apart, they make the overall structure that they're in tougher. So, a little part of the material breaks and that helps to dissipate the force. Normally, the way you would think about making it easier to break apart these small molecular components might be to create a hinge so they can kind of peel open instead of sliding apart. But what we discovered was that there was a fully **quantum mechanical phenomenon**. There was really no way for us to predict this, based on anything else, where the electrons just move around in a different way so that at this moment where the molecule is going to break apart, it's a lot more stabilized. These types of concepts, they're similar to what's known about how **catalysts** and **enzymes** work, but it had never before been shown in these **polymer materials**.

</details>

**主持人**: 这有点像**贝桥**（Bay Bridge）中的保险丝，通过受控断裂来保持桥梁在地震中的结构完整性？

<details>
<summary>Original English</summary>

**Host**: So, this is sort of like the fuse in the **Bay Bridge** that sort of allows the bridge to keep its structural integrity during an earthquake by having a controlled break. Is that kind of?

</details>

**Heather Kulic**: 是的。我们并不是第一个发现这种现象的人。这种通过在网络中设置小的可断裂点来增强整体强度的一般现象，几年前已发表在 **Science** 杂志上。但我们提出设计这种材料的具体方法，这是我们的新贡献。

<details>
<summary>Original English</summary>

**Heather Kulic**: Yeah. Yeah. So, we weren't the first ones to discover that phenomenon on its own. The general phenomenon that putting little places that could break to make the network stronger that was published in **Science** magazine a couple years ago, but the specific way we came up with to design the material to do this, that was our new contribution.

</details>

### 从化学计量学到机器学习

**主持人**: 你提到最初是利用增强计算加速现有方法。是什么促使你转向基于**机器学习**的方法？

<details>
<summary>Original English</summary>

**Host**: How did you, you mentioned that you started off in accelerating kind of existing methods using enhanced computation. What caused you to take that leap to more **machine learning based methods**?

</details>

**Heather Kulic**: 我很早就被**数据驱动发现**所吸引，甚至在知道“**机器学习**”这个词之前。我当时非常兴奋于从数据模式中学习的可能性。那时我们称之为**化学计量学**（chemiformatics），试图思考如何从数据中发掘趋势。因为我职业生涯的开始是每次研究一个分子或一种材料，而我当时很没耐心。我希望能理解更广泛的趋势，而不仅仅是为每个分子写一篇论文。大约在2015-2016年，我意识到把我的工作称为**化学计量学**是个坏主意，而将其称为**机器学习**是个好主意。我有一个非常出色的学生，**John Paul Jana**，他现在是 **AstraZeneca** 瑞典分公司的助理总监，负责他们的逆向设计项目。他和我最初讨论了各种材料设计方法，他很快将其转化为训练**神经网络**。那时候我认为我们正处于第一波“炒作周期”，但与现在相比，那只是一小波浪潮。

<details>
<summary>Original English</summary>

**Heather Kulic**: So, I was drawn to **data-driven discovery** pretty early on, before I even knew the phrase **machine learning**. And I was just really excited by what you could learn from patterns and data. Back then we were trying to call it **chemiformatics** and just trying to think about in what ways could you unearth trends in data because I started my career actually working kind of one molecule at a time or one material at a time and I was just impatient. I wanted to be able to understand not just one molecule at a time and write one paper about it, which is something people would have been happy to do back when I was starting my career in the mid-200s, but to actually kind of unearth broader trends in how you understand how material is going to behave. Somewhere around 2015, 2016, I realized it was a bad idea to call things **chemiformatics** and it was a good idea to start calling things **machine learning**. And I had a brilliant student, **John Paul Jana**, who's now an assistant director at **AstraZeneca** in Sweden, running their inverse design program. He and I originally talked about all sorts of ways of thinking about materials design and he very quickly adapted that into training **neural networks**. And that's when I thought we were in the first hype cycle, the first wave, but I think compared to what's going on right now, it was a tiny baby wave.

</details>

**主持人**: 我在你的论文中读到，那实际上是一个课堂项目。

<details>
<summary>Original English</summary>

**Host**: I read in your paper that that was actually a class project or something.

</details>

**Heather Kulic**: 是的，没错。他就说：“我必须做些作业。”然后我们就这样开始了。

<details>
<summary>Original English</summary>

**Heather Kulic**: Yeah. Yeah, that's right. He just said, "I have to do something for my homework." And that's how we got into it.

</details>

### 多目标优化与活性学习

**主持人**: 我也读过你的论文，你最近在**活性学习**方面做了很多工作。能谈谈这方面吗？

<details>
<summary>Original English</summary>

**Host**: I've also read in your paper that you've done a lot of work more recently on **active learning**. Can you talk a little bit about that?

</details>

**Heather Kulic**: 是的，是的。我刚才举的那个聚合物例子原则上也是**活性学习**，但我们只进行了一代就停止了，因为我们已经探索完了整个空间。我认为**机器学习**在化学科学中最有前景的领域之一是解决**多维度挑战**。例如，我们目前正在进行一个关于**金属有机框架**（**MOFs**）的项目，试图解决与直接从空气中捕获 **CO2** 相关的权衡问题。为了找到一种适合的材料，我们需要考虑它的成本、在潮湿环境中的稳定性、对 **CO2** 的选择性吸附能力、机械稳定性以及热稳定性。这只是其中几个目标，但在当前的**活性学习**项目中，我们正在优化七个不同的目标。即使对于一个不太精确的**机器学习**模型，每增加一个优化维度，通常也能实现100到1000倍的速度提升。所以，真正的潜力在于通过七个目标来“大海捞针”，并且在模型尚未完全精确之前就开始优化，这就是**活性学习**的真正潜力。这让我想到了制药行业，那里有很多计算工作用于药物发现，但真正的瓶颈往往是将药物送到人们手中。

<details>
<summary>Original English</summary>

**Heather Kulic**: Yeah. Yeah. So even that polymer example I was giving that would have been **active learning** in principle, but we stopped after one generation because we had exhausted the space. But I think one of the areas where **machine learning** kind of just with what's out there right now has the most promise in chemical sciences is in solving **multi-dimensional challenges**. So right now we're working on a project in **metal organic frameworks** where we're trying to solve tradeoffs relevant for direct capture of **CO2** from the air. And so in order to find a material that's good for that, we would worry about its cost, its stability in say aqueous humid environments. Its ability to take in **CO2** over other molecules, its mechanical stability, is it going to hold up under force? Is it thermally stable? Can you heat it up and will it be okay? I'm just naming a few but in total right now in an **active learning** campaign we're working on seven different objectives. And usually just even for a not so accurate **machine learning** model you get at least 100 to a thousandfold speed up for every dimension you're optimizing over. So the real promise is going to be in searching for that needle in a hay stack with say seven objectives and doing something where you're not waiting for the models to be accurate before you start doing that optimization. That's really the promise of **active learning**. That has an interesting parallel in my mind to the **pharma** world where you have a lot of computational work in the discovery process, but that actually getting the drug out to in people's hands is often the bottleneck for a drug.

</details>

**主持人**: 是的，还有药物在货架上存放三个月后会发生什么变化等问题。

<details>
<summary>Original English</summary>

**Host**: And also, what happens to the drug when it sits on the shelf for three months? That kind of thing. Yeah.

</details>

**主持人**: 这些**金属有机框架**主要用于哪些方面？

<details>
<summary>Original English</summary>

**Host**: Are these medical organic frameworks? What are the kind of things that they're used for?

</details>

**Heather Kulic**: 它们主要用于**气体存储**、**传感**和**分离**。它们与聚合物复合材料结合使用。在 **CO2 捕获**方面，它们有非常大的前景，但人们也研究过它们在**催化**方面的应用。催化的限制因素一直是它们的稳定性。所以，我们投入大量时间来预测它们的稳定性。但它们用于各种用途，甚至**药物递送**。它们有机会做的，是在特定方向上精确放置化学基团，最终实现**主客体相互作用**。这基本上是创造一个“手套”，与**金属有机框架**中的“客体”分子进行靶向相互作用。

<details>
<summary>Original English</summary>

**Heather Kulic**: They're used most in **gas storage**, **sensing** and **separations**. They're used in combination with polymer composites. They have really strong promise for **CO2 capture** especially, but people have looked at them for **catalysis**. The limitation on **catalysis** has been, you know, how stable are they? So, one of the things we've spent a lot of time on is trying to be able to predict their stability. But they're used for all sorts of things, even **drug delivery**. What they have the opportunity to do is really place precise chemical groups in specific orientations that can ultimately allow for what's known as **host guest interaction**. So basically kind of create a glove to have a targeted interaction with a guest molecule in the **metal organic framework**.

</details>

**主持人**: 我明白了。对于非化学家来说，**金属有机框架**就像化学界的**乐高**（Legos）吗？

<details>
<summary>Original English</summary>

**Host**: I see. And just for the non-chemist, **metal organic framework Legos** for chemistry, is that?

</details>

**Heather Kulic**: 是的，是的。我认为**金属有机框架**在一些工程师中会变得更家喻户晓，因为今年这些材料的发现者刚刚获得了**诺贝尔奖**。当然，这也能让化学界的一些事物变得家喻户晓。但它们基本上就像**乐高**积木一样，有不同的构建块，可以以几乎无限的方式组合，创造出非常精确的化学结构。

<details>
<summary>Original English</summary>

**Heather Kulic**: Yeah. Yeah. **Metal organic frameworks** I think are going to be a little bit more of a household name among some engineers because they the discoverers of those materials just won the **Nobel Prize** in chemistry this year. So as much as that can make something in chemistry a household name, but they're basically like tinker toys or **Legos**. And they have different building blocks that can be combined in basically infinite ways to create very precise chemistry.

</details>

### AI如何赋能量子力学计算

**主持人**: 能否回顾一下，在开始使用**机器学习**之前，或者与**机器学习**并行时，你使用了哪些技术？**机器学习**如何帮助你推进这些技术？两者的作用是什么？

<details>
<summary>Original English</summary>

**Host**: Maybe for context, could we step back and like what are the techniques you were using before you started or maybe in parallel with **machine learning** and how does **machine learning** help you advance those? Like what are the roles of the two?

</details>

**Heather Kulic**: 我职业生涯的开始是研究**过渡金属催化**。如果你看**元素周期表**，中间部分包含大量金属，例如**铁**（iron）。这些位于**元素周期表**中间的元素都有所谓的“开壳层”，这意味着这些材料中的电子不是成对的，因此更具反应性。通常，理解它们的行为方式，例如不同金属组合如何形成用于大量转化的**催化剂**，包括哈伯-博施法合成氨等维持世界大部分人口生存的工艺，都可以追溯到20、30、50年前，人们通过**量子力学建模**来理解和理性设计这些材料。**量子力学建模**通过使用薛定谔方程的近似值，可以非常精确，但也非常耗费计算资源。因此，单个**量子力学预测**，根据所使用的保真度级别，可能需要数小时到数天甚至数周。这正是我在接触 **AI** 之前通常会做的工作。现在，我们的一些工作是加速这些**量子力学预测**，并且我特别感兴趣的一个领域是，并非所有的**量子力学近似**都是等效的，你可以实际使用**机器学习**模型来预测根据所研究的材料应使用哪种最佳近似方法。

<details>
<summary>Original English</summary>

**Heather Kulic**: So, I started my career studying what's known as **transition metal catalysis**. If you look at the **periodic table**, the middle of it contains a bunch of metals. A good example would be **iron**. And all of those things sitting in the middle of the **periodic table**, they have what's referred to as an open shell. So the electrons in those materials are not paired and they're as a result more reactive. Normally the way that you understand how they're going to behave. So that for instance, they give rise to different combinations of these metals give rise to the **catalysts** that are used in a large number of transformations including the things that say feed and sustain most of the world's population such as the habberos process for ammonia synthesis. And the way going back 20, 30, 50 years that people understood these materials and could enable their rational design is through **quantum mechanical modeling**. **Quantum mechanical modeling** by using approximations to the **Schrodinger equation** can be very accurate, but is very computationally costly and so a single **quantum mechanical prediction** depending on the level of fidelity used could take hours to days to weeks and that's what I would have normally been doing before I got started in **AI**. Some of what we do these days is accelerating those **quantum mechanical predictions** as well as looking at an area that I'm particularly excited about is that not all **quantum mechanical approximations** are equal and you can actually use **ML models** to kind of predict what the best approximation to use is depending on the material studied.

</details>

**主持人**: 这和距离有关吗？

<details>
<summary>Original English</summary>

**Host**: Is that like closer is better or is it some is it it's not really distance related.

</details>

**Heather Kulic**: 就使用哪种方法而言，它实际上相当复杂，不能仅仅根据启发式方法来确定。所以，我们实际上在一个领域中使用**量子力学波函数**作为**神经网络**的输入，来实际预测应该使用哪种正确的方法并学习这种映射。

<details>
<summary>Original English</summary>

**Heather Kulic**: In terms of which method is the right method to use? So, it actually turns out to be quite complex. Can't just determine it from heuristics. So we actually in one area use the **quantum mechanical wave function** as inputs to **neural networks** to actually predict what is the right method to use and learn that mapping.

</details>

### 材料科学领域的AlphaFold：挑战与机遇

**主持人**: 你认为**机器学习**目前最大的差距是什么？如果一个有抱负的**机器学习**工程师想从**机器学习**角度解决一个新问题，你认为他们可以做些什么来真正帮助化学领域？

<details>
<summary>Original English</summary>

**Host**: What do you think the biggest gaps that **machine learning** has from your experience that if you were an aspiring **ML engineer** looking to take on a new problem from the **machine learning** side? What do you think someone could work on which would really help the chemistry side?

</details>

**Heather Kulic**: 很多挑战在于数据集不够大或不够多样化，所以它们吸引的兴趣较少。对我来说，最关心的是**反应性预测**，也就是预测哪些反应会发生以及为什么会发生，尤其是在复杂现象中，例如多种元素以及预测它们的转化。另一个问题是，缺少关于更多样化的**化学键合**和更多样化化学的数据。对我而言，这包括**过渡金属**，但也涉及到热密材料、奇异现象等问题。对于非常“无聊”的化学，我们有很好的数据集。例如，即使你不是化学家，也可能熟悉有机分子数据集和有机分子与蛋白质结合的数据集。这些是常见的数据集。但在更复杂的物理问题中，例如物质在光照下被激发到激发态时会如何表现，这类问题受到的关注相对较少，因为可能还没有相关的基准或排行榜。所以，也许我们化学家有责任生成更多数据集，让这些排行榜出现。但化学领域确实有很多值得关注但尚未得到足够关注的兴趣点。

<details>
<summary>Original English</summary>

**Heather Kulic**: There are a lot of challenges out there where the data sets aren't large enough or diverse enough, and so I think they've attracted less interest. So the ones closest to my heart are **reactivity prediction**, so predicting which reactions will occur and why, especially in complex phenomena, like in multiple elements and predicting those transformations. Another thing that I think there's not enough data on is just more diverse **chemical bonding** and more diverse chemistry. For me, that's **transition metals**, but there's also questions of warm dense materials, exotic phenomenon. We have really good data sets out there for really boring chemistry. So we have, you know, probably even if you're not a chemist, you're familiar with organic molecule data sets and organic molecules binding to proteins. Those are the common data sets out there. There's lots of challenges out there where the physics is much more complex and the things like how does matter behave when you shine light on it and you excite it into excited states. All sorts of things like that receive relatively little attention because you know, there may not be a benchmark or a leaderboard yet for that. And so maybe it's on us chemists to generate more data sets so those leaderboards are out there, but there's definitely a lot of interest in chemistry for which there has been less attention.

</details>

**主持人**: 在蛋白质领域有 **CASP**，人们在这方面努力了很久，并促成了 **AlphaFold** 的诞生。材料科学领域有类似 **CASP** 的东西吗？

<details>
<summary>Original English</summary>

**Host**: So in the protein world there's **CASP**, right? And people have been working on that for a while and this led to **AlphaFold**. Like kind of without **CASP**, **AlphaFold** probably wouldn't exist. Is there like an equivalent to **CASP** in the material science world?

</details>

**Heather Kulic**: 有各种各样的**材料项目**（Materials Project）和**开放催化剂项目**（Open Catalyst Project）等，它们存储了相当低保真度的**DFT**数据。这些项目确实提供了不错的排行榜，但其局限性在于数据来自保真度不高的**密度泛函理论**（DFT）。所以，我想说第二个挑战是，现在所有最聪明的**机器学习**工程师都在基于不反映实验结果的数据进行学习。没有大型的实验数据集。例如，**CASP** 的优势之一是它来自实验的真实数据。但在材料领域，这方面的数据并没有那么多。我们讨论了 **CASP** 及其在 **AlphaFold** 中的作用。你认为我们能否找到一种方式来大规模收集数据，从而发起一项社区挑战，解决你心目中的开放问题？或者说，如果材料领域有一个类似 **AlphaFold** 的工具，你希望它能做什么？

<details>
<summary>Original English</summary>

**Heather Kulic**: So there are all sorts of repositories of fairly low fidelity **DFT** data on crystalline materials. So **Materials Project**, **Open Catalyst Project**, these do provide good leaderboards, but some of the limitations of that are the data comes from not very high fidelity **density functional theory**. So, I'd say that's a second challenge is that we're all the smartest **ML engineers** right now are learning on data that is not going to be reflective of experiment. There aren't big experimental data sets. For example, one of the advantages of things like **CASP** is that it comes from an experimental ground truth. Whereas that aspect, it just isn't available in materials as much. We talked about **CASP** and the role of **CASP** and **AlphaFold**. Do you think that there is a problem, a way of phrasing this that we could start collecting data at scale that we could really have a community challenge which breaks open some open problem in your mind and maybe even stepping back beyond that. What would you want to have if there was an **AlphaFold** for materials? What would you want it to do?

</details>

**Heather Kulic**: 有一个模糊的领域，我可能无法直接回答这个问题。对我们来说，**电子结构计算**非常昂贵，但原则上它们应该能给出正确的答案，从第一性原理上预测材料的行为。很多人现在正在用**机器学习**训练的**原子间势能**来扩展这些计算。每次有人发布一个基于新数据集训练的所谓**基础模型**，它看起来都非常棒。但当你把它带到实验室，想用它来解决你非常兴奋的问题时，它就会开始做一些奇怪的事情，比如分子会散开。我不点名，但今年夏天有一个引起轰动的模型，人们开始宣称：“这种方法已经死了，那种方法也死了，我们都将只使用这些**神经网络**模型。”然而，在我看来，我没有点名的那个模型，只比我用 **GPU** 进行的最快 **DFT** 计算快五倍，而且它也不是每次都有效。

所以，我认为我们需要一种更透明的方式来判断这些模型是否真的能取代传统的基于物理的建模。如果它们能够做到，如果我能放弃所有 **DFT** 计算，只依赖**机器学习势能**，并且如果它们比传统方法快两个数量级，那将彻底改变我们的科学研究方式。但我们需要对我们所说的“拟合数据”有更严格的要求，特别是当这些数据可能缺乏质量时；或者说，我们需要对“这个模型真的可以取代基于物理的建模”这一说法有更严格的要求。

<details>
<summary>Original English</summary>

**Heather Kulic**: One kind of murky area, so maybe I'm not going to directly answer this question. One murky area for us is **electronic structure calculations** are expensive and they should in principle give you the right answer. They should from first principles give you the right answer of how a material is going to behave. And a lot of people are scaling these up right now with **machine learned interatomic potentials** on training data. And every time someone comes out with kind of a new data set trained on a and they call it a **foundation potential**, **foundation model**, it looks really good. And then you get it into your lab and you say, "Okay, I want to use it for this problem I'm really excited about." And it starts doing kind of wacky things like molecules fall apart. I won't name names, but there was one that made a huge splash this summer and people started declaring, "Oh, this method is dead. This method is dead. We're all going to just use these **neural network models**." Now, it's only in my hands, the one I'm still not naming is only about five times faster than my fastest **DFT calculation** on a **GPU**. And it also doesn't work all the time. So I would say we need a more transparent way of trying to figure out if these models can really replace conventional physics-based modeling. If they could if I could just give up ever doing a **DFT calculation** again and just rely on **machine learn potentials** and if they were two orders of magnitude faster than the traditional approach that would change that would change how we're doing science. But there needs to be a little more rigor on what we consider, you know, just fitting data when that data maybe lacks quality or there needs to be a little bit tougher requirement for how we say this model can really replace the physics based modeling.

</details>

**主持人**: 是的，我们认为比特与原子之间的接口是真正的瓶颈，即在实验室中尝试实验的实际活动是瓶颈，你通过**活性学习**在一定程度上解决了这个问题。但我也认为，纯粹的流程和自动化、良好的操作实践都很重要，因为虽然你可以推动自动化，但另一方面，这也会带来脆弱性。那么，你如何思考弥合与实验化学之间的差距，并将它作为一种“自然计算机”来解决设计过程中的问题？

<details>
<summary>Original English</summary>

**Host**: Yeah. So I one of our thesis is that the interface between bits and atoms is really the bottleneck, right? Where you have to the actually activity of trying things in the lab is the bottleneck and you've addressed that to some extent in **active learning**. But I think that there's also an extent to which that just pure process and automation good operational practice those are important things so that if you you can push to automation on the one side but on the other side that creates brittleness. So, how do you think about kind of bridging that gap to experimental chemistry and using that sort of as a nature's computer to figure out things for your design process?

</details>

**Heather Kulic**: 是的。有很多非常聪明的人正在从事**高通量合成**、实验和**自动化实验室**的工作。我认为在这个领域中，对我来说有趣的一点是，某些类型的实验，至少在我参加的上次相关会议上，对于自动化**高通量实验**来说非常困难，但对于人类来说却非常容易，反之亦然。然后还有人类在实验室中可能遇到的偶然性，有些人试图思考如何将这种“噪音”引入**高通量实验**中。所以，我认为这是一个挑战。你的问题也让我想到了另一点，我绝不是这方面的专家，但大多数真正致力于将材料应用于设备尺度的人，例如电视机中的材料，都会告诉你，这不仅仅是材料本身，更是过程。我认为在如何通过**机器学习**来学习结构和性质，以及加工过程所扮演的角色方面，我们还处于起步阶段，一无所知。

<details>
<summary>Original English</summary>

**Heather Kulic**: Yeah. So, so there are a lot of really smart people working in **high throughput synthesis** and experimentation and **autonomous labs**. I think the thing that that's interesting to me in that space at least is that there are some types of experiments that at least as of the last conference I went to on this are really hard for autonomous **high throughput experimentation** but are really easy for a human and vice versa. And then there's, you know, the serendipity that a human might experience in the lab that a couple of people have tried to think about like, well, how do you how do you introduce that noise into **high throughput experimentation**? So, I think that's a challenge. Your question also brought to mind another point that I am by no means an expert on, but most people who actually work on getting materials to the device scale say something that would be in your television or something like that is they will tell you that it's not just the material, it's the process. And I think we're at ground zero, we're nowhere when it comes to like, well, how do we machine learn not just the structure and the properties but also the role that processing plays. I don't think we know anything about how to do that.

</details>

**主持人**: 对于非专家来说，蛋白质结构很容易想象，我们可以看到蛋白质，进行模拟，看它们扭动，结构看起来非常漂亮。那么材料科学的数据是什么样的呢？计算，比如 **DFT**，我认为能给出类似晶体结构的东西，你可以想象。但有没有实验数据可以观察到晶体结构？或者这主要是通过探针测量个体性质，这些性质是集体性的，而不是细粒度的？

<details>
<summary>Original English</summary>

**Host**: Maybe for non-experts like with protein structure it's really easy to imagine like oh you can see these proteins like and we can run some simulations and see them wiggling around and the structures looked really pretty. What does the data look like for material science? Is there's the computations like **DFT** I think gives you something which looks like a crystal structure you can imagine but then there's also like is there experimental data where you can observe that crystal structure or is this mostly sort of like kind of probes where you're measuring individual properties which are kind of collective and with not fine grained?

</details>

**Heather Kulic**: 实验结构是可用的，我刚才举的例子就是我们知道它是稳定的，并且之前见过它的结构。但使用某些模型时，它会散开。这里的挑战是，**AlphaFold** 在预测球状蛋白质结构方面做得很好，主要基于20种天然氨基酸。我其实可以指出很多 **AlphaFold** 在更有趣的化学领域也会失败的例子。挑战在于，涉及到材料时，你拥有的构建块远不止20种。因此，关于**化学键合**有很多不同的思考方式。而目前，没有任何势能模型能够真正稳健地编码所有这些键合，尤其是在**金属有机键合**方面。

<details>
<summary>Original English</summary>

**Heather Kulic**: So experimental structures are available, and the example I was giving is something we know is stable and we've seen a structure of it before, and it will fall apart with some of these models. The challenge here is that **AlphaFold** has done really well is predict structures of globular proteins primarily with 20 natural amino acids. I could actually point to lots of cases where **AlphaFold** fails too for more interesting chemistry. The challenge is that you have a lot more than 20 building blocks when it comes to materials. And so there's lots of different ways to think about **chemical bonding**. And right now, no potentials are really robustly encoding all of that bonding, especially with respect to **metal organic bonding**.

</details>

**主持人**: 换句话说，**AlphaFold** 解决的是基态结构问题，它不考虑动力学。这与你关于**催化酶**需要**量子力学**的说法是一致的。但你是否认为，即使在基态性质方面，参数也太多了，而且没有一个明确的相互作用集合被限制在少数构建块中？

<details>
<summary>Original English</summary>

**Host**: You know, maybe a different way of saying it is like with **AlphaFold**, I mean, **AlphaFold** is solving ground state structures. It's not looking at dynamics. Which is I think consistent with like some of your statements about needing **quantum mechanics** for **catalytic enzymes**. But even you're saying even at just kind of ground state properties you're saying that just there are too many parameters and there's not like a clear set of interactions which is limited to a small number of building blocks.

</details>

**Heather Kulic**: 在整个材料空间中，键合是高度可变的。当然，也有简单的材料区域。你可以选择**铝**（aluminum）。**铝**非常无聊，早在上世纪60年代，人们就能在纸上写出如何对**铝**进行建模，这很容易用**神经网络势能**来拟合。但如果你想转向**氧化铁**（iron oxide），再转向**高熵合金**（high entropy alloys），肯定有案例使用这些方法。但我认为一个巨大的挑战是，当你转向更大的尺度和时间尺度时，没有真正的方法知道你是对是错。实验数据不存在。即使是解释实验图像，例如你想要做的表面图像，也需要一定程度的图像解释。所以，很难从实验或其他计算中判断这些模型是否正确。它们肯定在整个化学空间中不总是正确的。而且我认为它们的失败可能比 **AlphaFold** 更具灾难性，尽管 **AlphaFold** 也有失败的时候。

<details>
<summary>Original English</summary>

**Heather Kulic**: The **bonding** is highly variable across all of material space. Now there's simple regions of material space. You can pick **aluminum**. **Aluminum** is very boring, and you can write down people in the 60s could write down on paper, how you need to model **aluminum**, that's something that is pretty easy to fit a **neural network potential** to. But then if you want to get over to **iron oxide** and then if you want to get over to **high entropy alloys**, there are definitely cases where people are using these methods. But I'd say a big challenge is that there's no real way to know if when you go to bigger lane scales and time scales, there's no real way to know if you're right or wrong. The experimental data is not there. Experiment even interpreting say looking at an image of an experiment surface which you would want to do. It requires some degree of interpretation of that image. So, it's just hard to know from experiment or from other computations if these types of models are correct. And they're certainly not correct across all of chemical space. And I'd say they could fail more catastrophically than **AlphaFold** obviously fails, though they're definitely failures of **AlphaFold**, too.

</details>

### 文本信息与AI模型集成

**主持人**: 换个话题，我在你的论文中还读到你曾尝试将论文中的文本信息整合到你的 **AI** 模型中。你能谈谈这种整合给模型带来了什么提升，以及你是如何实现的吗？

<details>
<summary>Original English</summary>

**Host**: Switching gears a little bit, I read in your paper also that you had done some work with integrating textual information from papers and into your AI that we all know and love right now. Can you talk about what kind of lift that that gives the models and how did how did you actually do that integration?

</details>

**Heather Kulic**: 是的，我们大概在五年前开始这项工作。最初，我们只是进行标准的**自然语言处理**和**图数字化**。现在我们使用 **LLM** 来尝试从文献中提取属性数据集，特别是那些被广泛报告的属性。我们注意到，这些模型能学到很多东西。即使只有几千个数据点，你也可以做一些事情，比如根据实验报告预测材料分解的温度。但我们发现最有趣的事情之一是，你可以通过两种方式获得材料分解的温度。一种是从图表中获取，另一种是从作者对图表的解释中获取。而这两个结果并不一致。所以，我认为从论文中提取文献信息的挑战之一是人们会犯明显的错误，没有人是完美的，但另一个挑战是人们对结果的解释方式不同。因此，如果我们基于这些解释来构建模型，就会面临挑战。就 **LLM** 而言，它们在**文献提取**方面取得了长足进步，但它们仍然对**假阳性**非常敏感。我认为我们花在检查 **LLM** 以确保我们摄取的数据准确性上的时间，无疑增加了这些工作流程的开销。

<details>
<summary>Original English</summary>

**Heather Kulic**: Yeah, so we started I guess about five years ago. So when we first started doing it, we were just doing sort of standard **natural language processing** and **graph digitization**. These days we use **LLMs**. But just to try to extract from the literature data sets of properties wherever people are widely reporting properties. And what we noticed is that there's a lot you can learn from these models. So you can even on the scale of a few thousand data points, you can then do things like predict the temperature at which a moth will break apart based on experimental reports. But one of the funniest things I think we noticed is that you can get the temperature at which a material will break down two ways. One, you can get it from the graph and two you can get it from what the authors say about how they interpret the graph. And those two things do not line up. So people, you know, one of the challenges I think with **literature extraction** from papers is one would be the obvious mistakes people make. You know, no one's perfect, but the other would be just, you know, people interpret their results in different ways. And so if we're building models based on those interpretations, that's a challenge. In terms of **LLMs**, they've come a long way in terms of **literature extraction**, but they're still definitely sensitive to **false positives**. And I think the amount of time we spend checking on **LLMs** to make sure that the data we're ingesting is accurate definitely is an overhead on those types of workflows.

</details>

**主持人**: 我明白了。那么这会如何影响发现过程呢？因为你有已知的文献，作为化学家，你的工作是发现新东西。但如果你的计算方法侧重于文献，那是否会偏向于之前报道的结果，而不是全新的发现？

<details>
<summary>Original English</summary>

**Host**: I see. And what about the way that it might bias the discovery process, right? Because you have this known literature, your job as a chemist kind of is to find new stuff. But if so, if you're emphasizing if your computational method is pulling in literature then maybe it's biasing you towards the previously reported results instead of something new, you know?

</details>

**Heather Kulic**: 我们试图解决这个问题的一种方法是，在一个文献数据集上训练模型，然后将其应用于以前从未见过的新结构，并尝试真正观察模型能扩展多远。但我们正在努力解决这个普遍问题。现在有一些实验数据的存储库，你可以了解它们何时发表，结构是什么，以及用途。我们现在正努力在此基础上构建**生成模型**，试图回答：如果我们了解一个领域的前30年，那么在这个基础上训练的模型能否预测接下来的20年？我认为这是一个悬而未决的问题。哪个模型是最好的？也许它不能预测所有新发现，但最近20年里我们认为是新的一些发现，也许对模型来说是微不足道的泛化，而另一些则不然。在理想情况下，当我们拥有可用的文献数据但又不确定时，我们可以使用**不确定性量化**来识别哪些材料是最有趣的，可以加入到我们的数据集中。

<details>
<summary>Original English</summary>

**Heather Kulic**: One of the ways we try to address that is we try to train a model on that literature but then apply it to new structures that have never been seen before and try to really look at how far we can extend the model. But we are trying to answer this in general. There are repositories out there of experimental data where you can have a sense of when it was published, what the structure is, what it was used for, and we're really trying to build **generative models** on top of that now to try to be able to say, well, if I know about the first 30 years of a field, can a model trained on that predict the next 20? I think that's an open question. And what model is best at, you know, and maybe it won't get all of them, but maybe some of those discoveries that we think are new in the most recent 20 years, maybe some of them are trivial for a model to generalize to, whereas others are not. I think in an ideal case where we have the available literature data and we don't know, we could use **uncertainty quantification** to then identify, okay, these would be the most interesting materials to get into our data set.

</details>

**主持人**: 对于那些有兴趣参与的人，有哪些好的数据集可以开始使用呢？

<details>
<summary>Original English</summary>

**Host**: I see in those data sets just for people who are interested in getting involved, what are some of the what's the best ones to get to get started with?

</details>

**Heather Kulic**: 我不知道哪个是最好的。我们整理了几千个关于**金属有机框架**热稳定性、活化稳定性和水稳定性的数据点。其他团队也整理了其他衡量稳定性的数据。它们都在我们的网站上。

<details>
<summary>Original English</summary>

**Heather Kulic**: I don't know about the best. We've curated a few thousand data points of **metal organic framework** thermal stability as well as **metal organic framework** activation stability, water stability. Other groups have curated other measures of stability. They're all out there. They're on our website. That kind of thing.

</details>

### 学术界在AI材料科学中的角色与未来

**主持人**: 你认为是否有必要发起一个多机构的资助项目或倡议，以高通量自动化方式获取数据？如果你能组织一个真正推动该领域发展的项目，你的梦想会是什么？

<details>
<summary>Original English</summary>

**Host**: Awesome. Do you imagine there being useful to like create an initiative or like a multi-institutional like funding source or something which really is trying to get data in a high throughput automated way? What would sort of like your dream be if you could organize something which really will drive the field forward in your mind?

</details>

**Heather Kulic**: 我认为**国家科学基金会**（National Science Foundation）有一个这样的倡议。我也听说过一些基金会以前对建立**云实验室**感兴趣，这样用户可以按需使用**高通量自动化**。我绝对认为拥有这样的用户设施非常棒，计算研究人员如我能设计实验并让其执行。以公开的方式收集所有这些数据会很棒。现在，研究成果发表在论文中，很难再提取出来。我们花费大量精力试图将其提取出来。因此，这方面也需要对报告结果的方式进行系统化，以便它们从发表之日起就符合**机器学习**的要求。一些研究子领域正在尝试这样做，但这在材料科学领域尚未全面发展。但我相信，将来肯定会有更多共享设施，人们可以利用来自更高通真度实验的数据，那将非常棒。我不知道这会来自公司捐赠设备、**国家科学基金会**还是私人基金会。

<details>
<summary>Original English</summary>

**Heather Kulic**: I think the **National Science Foundation** has one initiative. I've also heard about things with foundations before being interested in in putting together **cloud labs**. So things that users can on demand make use of **high throughput automation**. I definitely think having user facilities where a computational researcher like me could design an experiment and have it executed would be awesome. Having all that data collected in sort of a public way would be great. You know, the way that research right now gets published into papers, it's very hard to then extract back out. We spend a lot of energy trying to get it back out. And so, some of this is a need also for, you know, maybe systematization of how results get reported so that they can be **machine learning ready** from day one when they're published. Some research sub fields are trying to do that, but it's not really developed across material science, but for sure, I think there will be more sort of shared facilities where people can make use of data from higher experimentation, and that would be really awesome. I don't know if it'll come from companies donating equipment from **National Science Foundation** or from private foundations.

</details>

**主持人**: 是的，生物技术领域有一个大型的慈善推动。但似乎人们还没有充分意识到这作为一个重要领域的价值，尤其是在气候变化材料等方面。

<details>
<summary>Original English</summary>

**Host**: Yeah, there is a large like philanthropic push in the biotech face. It seems like people haven't quite picked up on this as such an important field like especially with things like materials for climate change. You can imagine a particular.

</details>

**Heather Kulic**: 这是一个非常重要的问题，我们可以投入更多努力。

<details>
<summary>Original English</summary>

**Heather Kulic**: A very important problem that we could use a lot of cush on.

</details>

**主持人**: 是的，这引出了一个问题：最近私人公司和初创企业对材料领域进行了大量投资。你认为这给化学领域的学术研究带来了什么影响？

<details>
<summary>Original English</summary>

**Host**: Yeah, that that kind of brings up the question there's been a ton of very recent materials investment for private companies startups. Where does that leave in your mind the role of the academic in chemistry?

</details>

**Heather Kulic**: 我一直在思考这个问题，尤其是在过去一年里。特别是，公司拥有学术界无法企及的计算资源。所以，我问自己，我们能做些什么更具创造性的工作，而不需要蛮力计算？我认为我们仍然有很多事情可以做。但我们必须提出这些问题。当然，**Microsoft**、**Meta**这些公司拥有几乎无限的资源，而作为一名学者，我没有。但我们对那些尚未进入这些公司雷达的问题感兴趣。我认为只要我们能做到，每当有人向我提出问题时，我都会尽量确保我们不会仅仅试图做一些投入大量计算资源就能解决的问题。

<details>
<summary>Original English</summary>

**Heather Kulic**: I ask myself that all the time or more recently in the past year. So in particular, there's a lot of compute that companies have access to that academics don't. So I ask myself, what can we do that's more creative that doesn't require just brute force compute? And I think there is a lot of stuff that we can still do. But we have to ask those questions. For sure **Microsoft**, **Meta**, those are the companies that have basically infinite resources. And as an academic, I don't have infinite resources, you know, but we have an interest in problems that haven't crossed the radar of those companies yet. And I think as long as we, whenever someone poses a problem to me now versus a few years ago, I try to make sure that we're not just in the process of trying to do something that throwing a lot of compute at it would solve it.

</details>

### 开源工具与社区参与

**主持人**: 我们时间不多了，但我想给你一个机会，呼吁大家行动。你希望听众了解什么？他们应该做些什么来参与其中，或者你对什么充满热情？

<details>
<summary>Original English</summary>

**Host**: Yeah. I think we're kind of running out of time, but would like to give you an opportunity, call to action. What would you like our listeners to know about do what what should they do to get involved or something that you're really passionate about?

</details>

**Heather Kulic**: 我想我会坚持一个比较小众的话题。

<details>
<summary>Original English</summary>

**Heather Kulic**: I think I will stick to something kind of niche.

</details>

**主持人**: 太好了。

<details>
<summary>Original English</summary>

**Host**: Great.

</details>

**Heather Kulic**: 我认为化学仍然有一席之地，我会这样说。我的团队开发了一个用于**过渡金属络合物结构生成**和**金属有机框架筛选**的代码，名为 **Mole Simplifier**。当我们处理 **MOF** 时，我们称之为 **Moth Simplify**。它有网站版本，你可以查阅而无需安装任何东西，但它也在 **GitHub** 上。如果你对**过渡金属络合物**感兴趣，可以尝试一下。它包括**机器学习预测**，但也能创建新颖的结构。我真的非常想知道是否有人正在使用它。我知道很多公司正在使用它，但我们通常是事后才知道。所以，如果你对这个材料领域更感兴趣，我非常乐意听取反馈。

<details>
<summary>Original English</summary>

**Heather Kulic**: So I think there is still a place for chemistry. I will say that. But my group develops a code for **transition metal complex structure generation metal organic framework screening**. It's called **Mole Simplifier**. When we're working on **MOFs**, we call it **Moth Simplify**. There's website versions of it that you can look up and not install anything, but it's also on **GitHub**. And if you do have an interest in **transitional complexes**, just try it out. It includes **machine learning predictions**, but it also makes novel structures. And I'm just really interested to hear if people are using it. I know a lot of companies are using it. But we sort of find out after the fact. So, if you're interested more in this material space, I'm definitely interested and open to feedback.

</details>

**主持人**: 非常感谢。很高兴。请多多参与。谢谢，博士。

<details>
<summary>Original English</summary>

**Host**: Grateful. Awesome. Get involved. Thank you very much. Take care, doctor.

</details>