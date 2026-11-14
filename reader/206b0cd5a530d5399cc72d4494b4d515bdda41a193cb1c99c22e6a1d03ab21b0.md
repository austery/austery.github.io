---
author: Latent Space
date: '2026-08-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=79mIutht1f4
speaker: Latent Space
tags:
  - neural-operators
  - physics-modeling
  - extreme-event-prediction
  - ai-for-science
title: 人工智能在科学建模中的突破：神经算子与物理世界模拟
summary: 文章探讨了人工智能，特别是神经算子在气象预测和物理系统建模中的应用。研究表明，AI 模型不仅能达到传统物理模型的准确度，而且速度快了成千上万倍，并能有效捕捉物理世界的潜在结构，尤其在预测极端事件方面表现出优越性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/7 -->

### AI 气象预测的突破

**Anima**: 因此，我们开始寻找有趣的例子，其中之一就是气象建模，因为气象数据是开源的，既然有现成的数据，我们就想，好吧，那就去试试吧，对吧。这就是它的美妙之处，只要有可用的数据，那就是个好消息。但很多气象科学家在当时（大概是 21 年）提醒我们，他们说，不，不，这太困难了，你知道，传统天气预报已经有几十年的发展历史了，那是基于物理的、非常严谨的自下而上的建模。所以前提是，哦，这就是流体动力学，你能去预测第二天的天气吗，等等。所以，很多人的想法是 AI 根本无法击败气象建模领域几十年的研究。但令我们惊讶的是，我们就直接去做了，我们训练了它们，我们使用神经算子（neural operators）来有效地捕捉现象，然后令我们惊讶的是，我们发现它不仅，你知道，准确，它几乎和传统气象模型的准确度一样高，而且速度快了成千上万倍。所以以前需要大型超级计算机来运行的东西，现在只要消费级 GPU 就可以运行了，像，你知道的，这是一个小模型，非常契合，速度快而且准确。我认为这彻底改变了每个人的想法。

<details>
<summary>Original English</summary>

**Anima**: So we set out looking for interesting examples and one of them was like weather modeling because the weather data is open source and so given that the data was there we were like okay let's just go try it right and that's the beauty of it whenever data is available it's really good news but a lot of weather scientists did caution us back then this was back in 21 and they said no no this is so difficult you know there have been like decades of like development in traditional weather forecasting and that's very careful bottom-up physics-based modeling right so assuming oh this is the fluid dynamics can you go predict the weather the next day and so on and so that's how a lot of the thinking was that AI is just not going to be able to beat the decades of work in weather modeling but to our surprise we just went ahead we trained them we used neural operators to be able to effectively capture the phenomena and then to our surprise we found that it's not only you know accurate it's almost as close to what the traditional weather models can do accurately but also tens of thousands of times faster so what would take a big supercomputer to run can now be run and we only needed a consumer grade like GPU like you know it was a small model it fit very well it's very fast and it's accurate and I think that just changed everybody's thinking
</details>

### 欢迎来到 Latent Space

**Brandon**: 欢迎来到 Latent Space，这是 Latent Space 的 AI for Science 板块。我是 Brandon，在 Atomic AI 使用 AI 研发 RNA 疗法。和我一起的还有我的联合主持人 RJ Honakee，他从事空间转录组学研究，也是 Miraomics 的首席技术官和创始人。今天，我们很高兴邀请到加州理工学院数学与计算机科学的布伦（Brin）教授 Anima Anandkumar。Anima 做过各种非常酷的工作，基本上是将 AI 与物理世界的模型结合起来，并且她有着非常多元的背景，我觉得我甚至无法涵盖其中的皮毛。不过不管怎样，我会让 Anima 自己来介绍，感谢您做客我们的节目。

<details>
<summary>Original English</summary>

**Brandon**: welcome to lane space this is the AI for science section of lane space I'm Brandon I work on RNA therapeutics using AI at atomic AI I'm joined by my co-host RJ Honakee who develops spatial transcriptomics and is the CTO and founder of Miraomics today we're excited to be joined by Anima Anankumar the Brin professor of mathematics and computer science at Caltech Anima has done all sorts of really cool work combining AI with basically models of the physical world and has a really diverse background I don't think I could even remotely cover it but anyway I'll let Anima introduce ourselves thank you for coming on the show
</details>

**Anima**: 是的，谢谢 Brandon 和 RJ，很高兴来到这里。我真的很喜欢“潜在空间”（Latent Space）这个词，因为它在我的很多工作中都扮演着重要角色，因为说真的，你知道，世界就是潜在的（latent）。简单介绍一下，我已经从事 AI 研究二十多年了，在深度学习出现之前，当我们需要为概率模型建立很多理论基础时，我就在研究它们了。然后随着深度学习开始腾飞，直到最近我也一直涉足其中。所以我之前在英伟达（NVIDIA）领导 AI 研究，在那之前在亚马逊云科技（AWS）帮助创立了云 AI 团队，并在大约十年前构建了首个云端 AI 产品。所以，你知道的，这种一只脚在工业界、一只脚在学术界的经历，我认为给了我很多有趣的视角，去思考如何将理论与实践结合起来，去思考大规模的 AI，同时也去思考有原则的 AI。

<details>
<summary>Original English</summary>

**Anima**: yeah yeah thank you Brandon and RJ it's a pleasure to be there and I really like the term latent space because very much figures in a lot of my work because it's really you know the world is latent but yeah just as a brief introduction you know I've been working in AI for more than two decades in a way you know before even deep learning when a lot of the theoretical foundations had to be built for probabilistic models I worked on them and then as deep learning started taking off I also had a foot until recently so I was at NVDI led AI research there and before that at Amazon Web Services helped found the cloud AI team and built the first cloud for AI products back almost a decade ago so you know like kind of having this one foot in industry in academia I think has given me a lot of interesting perspective of how to bring theory and practice together and think of AI at large scale but also AI that is principled
</details>

### TorchLean 与物理系统建模

**Host**: 您的很多工作都与……你知道的，使用某些类型的物理系统来对物理系统进行建模有关，您使用微分方程来建模，并利用机器学习来辅助建模。所以，也许我们先从高层次谈谈这个，稍后我们再讨论关于单一算子（single role operators / neural operators）的一些细节以及像气象预报这样的应用。但首先，我其实非常想听听关于 TorchLean 的情况，以及您最近一直在做的这项工作是如何与那个更大的研究项目联系起来的。

<details>
<summary>Original English</summary>

**Host**: a lot of your work has been related to you know the modeling of physical systems using certain types of physical systems which you model with differential equations and you help model them with using machine learning so maybe first let's go in and talk a little bit about that as a high level but we'll get to kind of the details about the single role operators and some of the applications like weather later but first I'm actually really curious to hear about TorchLean and how this recent work you've been doing connects with that larger research program.
</details>

**Anima**: 对我来说，广义地讲，我的主题是 AI 与科学，也就是我们如何将这两者结合起来，对吧。所以，你知道的，当我大约十年前开始在加州理工学院工作时，那时我的热情一直是在科学方面，也就是物理，但是，你知道，我当时在做 AI，所以如何将这两者结合起来，就是，你知道，最初奠定一些基础的地方。对我来说，这涉及到几个方面。一个是人们一直在思考如何将语言模型用于科学，是的，你可以做很多假设生成，你可以有很多想法，但仅仅有想法是不够的，对吧。所以你可以有很多想法，但瓶颈在于去测试和验证它们是否在现实世界中有效。所以这方面一直是我最近很多关注的焦点，我们如何确保我们构建的 AI 有保证它能在物理世界或科学领域的任何方面发挥作用。一种思考方式是，你知道，我们能否建模并保持物理学上的正确性，这就是神经算子（neural operators）发挥作用的地方。另一方面是，我们能否用符号来验证某些方面。例如，你知道，如果我们声称一个定理是正确的，我们必须去验证它，你知道，这就是 Lean 作为一种形式语言可以用于验证的地方。所以我们如何将这一点与语言模型结合起来，这就是许多数学推理一直处于前沿的地方。因此 TorchLean 在某种程度上就属于这个范畴，我们在那里说，你知道，你不只是想验证数学陈述，你可能还想验证神经网络本身声称要提供的内容。你知道，例如，如果你现在正在使用一个神经网络，你想问它是否会具有鲁棒性，比如你想在控制回路中使用神经网络，你想控制，你知道，无论是一架无人机，还是一个核反应堆。所以最终所有这些，当我们构建带有深度学习的 AI 系统并将其放入控制回路时，我们需要鲁棒性。所以现在 TorchLean 可以帮助我们无缝地进行这些验证，这样我们现在就可以让神经网络成为验证循环的一部分，并有信心我们可以恰当地使用它们。

<details>
<summary>Original English</summary>

**Anima**: To me broadly like you know my thesis is AI and science how we bring that together right so you know when I started at Caltech almost a decade ago that's when you know my passion was always science was physics and but you know I was doing AI so how to bring that together was where you know the first kind of foundations got laid there and to me like you know there are several aspects to that one is people have been thinking how to use language models for science yes you can do a lot of hypothesis generation you can have ideas but ideas are not enough right so you can have a lot of ideas the bottleneck is going testing and verifying that they work in the real world and so this aspect is where a lot of my recent focus has been on how do we ensure that we can build AI that has guarantees that it will work in the physical world or any aspects in scientific domains and one way to think about it is you know can we model and keep the physics correct and that's where neural operators come in the other aspect is can we verify symbolically certain aspects for instance you know if we claim that the theorem is correct we have to go verify that you know that's where lean as a formal language can be useful for verification so how do we bring that together with language models is where a lot of mathematical reasoning has been at the forefront and so torch lean kind of is in that realm where we say you know not only that you want to verify mathematical statements you may want to verify what neural networks themselves claim to deliver you know for instance if you are now using a neural network and you want to ask whether it's going to be robust say you want to use a neural network in a control loop you want to control you know whether it's a drone whether it's a nuclear reactor so all of this ultimately when we build AI systems with deep learning into control loops we want robustness and so now torch lean can help us do those verifications seamlessly so we can now have neural networks be part of the verification loop and have confidence that we can use them appropriately
</details>

**Host**: 我们已经在播客中讨论过 Lean 了，而且大家可能都对神经网络很熟悉了。但是神经网络看起来非常不受约束，你所说的证明是指什么类型的证明？你是在说对输出和输入的界限进行约束吗？你能用 TorchLean 证明什么？

<details>
<summary>Original English</summary>

**Host**: we have already discussed on the podcast lean and and everyone should probably be familiar with neural networks how but neural networks seem very unconstrained what kinds of proofs are you talking about are you talking about bounds on the outputs inputs what what can you prove with torch thing
</details>

**Anima**: 是的，TorchLean 是一个很新颖（noble / novel）的框架，对吧。所以它真正实现的是，你现在基本上可以在 Lean 中编写神经网络。所以与其像在 PyTorch 中那样编写——它就像一个类似 PyTorch 的抽象——但你可以，你知道的，用 Lean 来写。所以它可以在 Lean 中完全形式化。然后有几种实现方式，你知道，我们有用于可验证鲁棒性（certified robustness）的算法，比如 CROWN，你知道，它们就是在这个框架下实现的。对不起，你说它像什么？像 CROWN。CROWN 是其中之一……我们能稍微解释一下吗？所以有不同的方法来界定，你知道，对于可验证鲁棒性，你知道这些界限能有多紧，这取决于松弛技术。不深入讨论那些，有很多这样的算法，但你知道，我们有点像是在 Lean 中实现它们并启用它们，这样我们就可以无缝地运行。你知道，我们首先像写类似 Torch 的框架那样非常简单地写下神经网络，对吧，然后我们也可以对它们进行形式化的陈述并进行验证。所以所有这些都可以汇集在一个框架中。

<details>
<summary>Original English</summary>

**Anima**: yeah so torch lean is a noble framework right so what it really enables is that you can now write neural networks essentially in lean so instead of writing in like pytorch it's like a pytorch like abstraction but you can like kind of you know write it in lean and so it can be fully formalized in lean and then there are several implementations you know we have algorithms for certified robustness like crown you know those are implemented under this framework so sorry was it like what like crown crown crown is one of the can we explain it a little bit so there are different ways to bound you know for certified robustness you know how tight those bounds can be it depends on the relaxation techniques and sort of without going into those there's many such algorithms but you know we are kind of like implementing them and enabling them in lean so we can seamlessly run both you know we both first kind of write down not torch like framework neural networks very simply right and then we can also make statements about them formally and verify them so all of that can be brought together in one framework
</details>

### 控制回路与安全性

**Host**: 那么你能声称的一个界限的例子是什么？比如我们正在操作一个核反应堆，我们不希望它熔毁。你能为输入和输出提供什么样的保证来帮助避免那种情况发生呢？

<details>
<summary>Original English</summary>

**Host**: so what's an example of a a bound that you could claim like so we're operating a nuclear reactor we don't want it to melt down what are the sort of guarantees that you could provide to the out inputs and outputs that would help that not know yeah
</details>

**Anima**: 是的，我的意思是自然的一个就是我刚才提到的这种可验证鲁棒性。也就是说明如果你的输入，你知道，向上波动了某个特定的量，输出会向上波动多少，对吧。这种敏感性分析是另一个术语。所以拥有针对不同架构的这类界限，所以你自然而然地得到了这些界限，然后就能帮助我们，你知道，不仅是训练神经网络在控制回路中表现良好，还能考虑到人们所关心的控制系统中的安全性、鲁棒性和稳定性。所以这是应用的一个例子。因此，它实际上更广泛的理念是，在许多涉及神经网络的场景中你需要进行验证。所以控制回路是一个例子。另一个例子是，你知道，我们使用物理信息神经网络（physics-informed neural networks）来求解，比如说，偏微分方程，或者想出那些保证满足某些物理定律的系统。但我们同时也想要验证，例如，我们的神经网络只在有限精度下进行了训练，对吧，那么我们能否克服这些要求？以及当我们……因为我们使用了这种有限精度，缺点是什么？我们也能界定这些吗？好了，所以这些是 TorchLean 中起作用的其他类型的界限。因此，像，你知道的，精度的影响，扰动的影响，所有这些方面，你知道的，我们都可以通过在 Lean 中实现的算法，让它们现在无缝地成为验证循环的一部分。

<details>
<summary>Original English</summary>

**Anima**: I mean the natural one is this certified robustness that I mentioned so saying that if you are inputs are you know put up by a certain amount how much is the output going to be put up right this sensitivity analysis is another term and so having those kinds of bounds for different architectures so you kind of automatically get those bounds can then help us you know not only train neural networks to do well in a control loop but also worry about safety and robustness stability these are all part of control systems that people worry about so that's one example of an application so it's really more broadly the idea is you need verification uh in lots of scenarios that involve neural networks so control loops are one another example is you know we used physics inform neural networks to say solve partial differential equations or come up with systems that that are guaranteed to satisfy certain physical laws but we also want to verify for instance that our neural network is only trained in finite precision right so can we overcome those requirements and what happens when we are what are the shortcomings because we are using this finite precision can we also bound those all right so those are other kinds of bounds that work in torch lean so all aspects of like you know the effect of precision the effect of perturbation all of these we can you know we can have algorithms that are implemented in lean that can be seamlessly now part of the verification loop
</details>

**Host**: 那么，TorchLean 的描述能力是否足以描述基本上任何的神经网络呢？还是说在这方面有一些限制？

<details>
<summary>Original English</summary>

**Host**: so and is the descriptive power of the torch lean is that sufficient to describe basically any neural network or is there are there constraints on that
</details>

**Anima**: 是的，所以它本质上是一个，你知道，类似 PyTorch 的框架，对吧。所以你可以非常完美地以相同的方式定义神经层，但通过将其后端设为类似 Lean，现在就帮助我们去形式化并证明它。

<details>
<summary>Original English</summary>

**Anima**: yeah so it's essentially a you know pytorch like in a framework right so you can just kind of nicely define neural layers in the same way but the back end having like lean now helps us formalize and prove it
</details>

**Host**: 那么对于例如 Transformer 架构，在一个非常大的神经网络上证明这种界限是合理的吗？所以……

<details>
<summary>Original English</summary>

**Host**: and for like transformer architecture for example is it reasonable to prove these kinds of bounds on a very large neural network so
</details>

**Anima**: 这个，你知道，这里有一个方面是，一方面是有框架，对吧；另一方面是可扩展性。不过 Lean 在这方面仍然存在很多缺点。它是基于 CPU 的，而且你知道，这不是说把它弄到 GPU 上那么简单，这里面有很多细微的区别，所以，你知道，还有大量的工作要做。因此我们现在是从一个框架开始的，你知道，要让它变得更加高效，尤其是在非常大的规模上，依然需要做很多工作，是的，但这在广义上也适用于 Lean 自身。

<details>
<summary>Original English</summary>

**Anima**: the you know there is the aspect of one is like kind of having the framework right the other is scalability low so lead still has a lot of shortcomings there it's cpu based and you know it's not like getting that onto the gpu has a lot of nuances there so you know a lot of work needs to be done so what we've started with is a framework you know making that more efficient especially at a very large scale requires still a lot of work to be done yeah but that's true broadly for lean as well
</details>

### 偏微分方程的优化挑战

**Host**: 所以我只是想弄清楚我该如何去想象这个。如果我去上数值分析课，你知道的，研究生水平的数值分析课，你有一个微分……你有一些离散化误差或类似的东西，然后你设定一个界限，比如，给定这些属性，我可以界定这个解，对吧。所以，关于解这些基于物理的或者基于 AI 的微分方程的方法，我想从历史上看这一直都是……虽然现在可能不那么严重了，我觉得你提到了物理启发（通知）神经网络。这是一个非常酷的想法，能稍微谈谈这个会很有趣。但我知道有时它们很挑剔，并不是总是有效，而且我认为人们并不总是知道它们什么时候有效，什么时候无效。我的意思是，我不是专家，但我只是好奇那是否也是你的经验。我真正想知道的是，这是否帮助你理解了 PINNs（物理信息神经网络）的适用范围？并且，这是否在某种程度上是目标？就是你可以严谨地说“这个解会收敛”，还是说对于神经网络而言，在可控的意义上并不一定有这种相同的收敛概念？

<details>
<summary>Original English</summary>

**Host**: so i'm just trying to understand like how i imagine this so if i were to take a numerical analysis classes you know on graduate level numerical analysis class you have a differential you have some discretization error or something and you bound like given these properties i can bound the solution right so solving some of these physics based or ai-based solutions to differential equations i think historically has been kind of the while less so i think you mentioned physics inspired neural networks um really cool idea it'd be fun to talk about that a little bit but i know that sometimes they they are particular and that people don't they don't always work and i think people don't always know when they will or won't work um i mean i'm not an expert but i'm just wondering if that's i've been your experience um and what i'm wondering is like has this helped you understand like the domain of applicability for pins or and is that sort of like the goal is like you can rigorously say like this solution will converge or is there not necessarily the same concepts of convergence in the controlled way for neural networks
</details>

**Anima**: 是的，所以你知道，像物理信息神经网络（physics-informed neural nets）就在说，你知道，我写下一个偏微分方程（PDE），希望优化能够成功，然后我得到答案，对吧。当然，如果优化根本不是问题，那这将是通用的，你解出了所有东西，你知道，我们都很高兴。但事实并非如此。因此，优化通常会变得非常困难。尤其是对于随时间变化的问题，意味着它不仅是平稳的，你还有时间维度。在很多情况下，时间分量可能是湍流式的，比如流体力学中，你知道，你那种……如果运行足够长的时间，它可以变得混乱（混沌的）。所以你确实，你知道的，有着非常精细微小的尺度效应在起作用。因此在那些情况下，指望在所有时间尺度上直接去求解一个偏微分方程就是无望的。像，你知道，这不是一个我们能够，你知道的，有任何办法去应对的优化环境。而这就是……

<details>
<summary>Original English</summary>

**Anima**: yeah so you know like physics form neural nets are about like saying that you know i write down like a pde uh partial differential equations and hopefully the optimization succeeds and i get the answer right and of course if like optimization was not at all an issue this would be universal you solve everything you know we're all happy but that's not the case and so optimization ends up being usually very difficult especially for problems that are time dependent meaning it's not just stationary you also have time and the time component in many cases could be turbulent like in the case of fluid dynamics you know you kind of like if you run it long enough it can become chaotic so you really you know have like very small fine scale effects matter and so in those cases just trying to solve a partial differential equation at all times is just hopeless like you know this is not an optimization landscape that you know i think we'll you know we can have any handle on and this is where
</details>

<!-- chunk 2/7 -->

### 神经算子与数据驱动的方法

**Speaker A**: 从头开始使用神经网络求解这些方程的想法是不可能的，因此物理信息神经网络（PINNs）并不是在所有情况下都有效。而我们提出的神经算子（neural operators）就是为了克服这个问题。也就是说，我们不能仅仅依靠物理约束来获得答案。我们有大量可用的数据。我会谈到天气的例子，在这个例子中我们甚至会去收集数据，所以我们不仅仅是求解方程并获得合成数据，我们还有通过观察天气获得真实数据的例子。那么，为什么不利用所有可用的数据呢？这样我们就不必完全依赖从头开始尝试求解偏微分方程和其他物理问题，因为真正使得快速获得答案成为可能的是数据驱动的方法。因此，借助神经算子，我们可以将两者结合起来，我们可以利用所有可用的数据，并在此基础上加入物理约束，从而克服 PINNs 的局限性。

<details>
<summary>Original English</summary>

**Speaker A**: the idea that from scratch we would be able to solve these equations using a neural net is not possible so pins don't work everywhere and our idea of neural operators came as a way to overcome this right so saying you know we can't rely just on physics constraints alone to come up with answers we have lots of data available you know i'll talk about the weather example where we even collect data right so we don't just solve equations and have synthetic data but we also have real data by observing the weather as one example so why not make use of all of the data available so we don't just rely on trying to solve partial differential equations and other physical problems from scratch because it's really the data-driven approach that makes it possible to get quick answers and so with neural operators we can bring both of them together we can have all the data that's available we can utilize it we can add physical constraints and then that overcomes pins face

</details>

**Speaker B**: 你能不能多谈谈这其中的区别，以及为什么这是可能的？我听到你提到，在使用 PINNs 时，你基本上只是将物理约束融入到神经网络中，但这随着时间推移或其他变量的变化会变得不稳定。然而，如果你加入一点数据，我大概能凭直觉理解为什么那可能会有帮助，但你能更直观地解释一下这到底是发生什么了吗？这里的区别是什么？

<details>
<summary>Original English</summary>

**Speaker B**: can you give a little bit more intuition on the difference there and why that is possible so i heard you mentioned you know in with pins you're basically just baking the physics constraints into the neural network but that this becomes unstable over time or other other variables whereas if you add a little bit of data like i can kind of intuitively understand why that might help but can you give a little intuition for what's going on what's the difference here

</details>

**Speaker A**: 所以像 PINN，你知道的，你要求解的每一个方程实例都是从头开始的，至少在经典意义上是这样的。所以一开始，你设定好你想要解的方程规范，然后你希望优化过程能够成功，但在很多情况下它并不能成功。相比之下，使用神经算子时，我们的做法是，因为我们有大量的数据，所以我们会有一个训练阶段。我们训练它如何为不同的方程实例得出解，因此就像在其他的监督学习中一样，在测试阶段你现在可以问它：“你能给出一个答案吗？”而且你仍然可以加入物理约束来引导它，这样一来，它可以将数据驱动和物理信息结合在一起。这样做的好处在于，因为我们有数据，你就像是不会陷入优化困境中，对吧？所以在训练期间你就知道了答案是什么，因此现在即便在测试阶段，你也有更大的机会得出正确的答案。

<details>
<summary>Original English</summary>

**Speaker A**: so the pin like you know every instance of an equation you solve from scratch right at least in the classical sense so you start you take the specification of what equation you want to solve when you hope that the optimization landscape succeeds which many cases it doesn't whereas with the neural operators what we do is we you know have lots of data so we have a training phase we teach it how to come up with solution for different instances of equation and so just as in other supervised learning at test time you can now ask you know can you come up with an answer and you can still have physics constraints as a way to guide that so you know it can be both data driven and physics informed together but the benefit is because we have data you know it's like you're not stuck in an optimization landscape right so you know what the answers are during so you're now at a better chance to come up with the right answers even at this time

</details>

**Speaker B**: 我的理解是，神经算子是一个拟合数据的函数，或者说是一个学习将函数拟合到数据的神经网络，这种直觉理解对吗？

<details>
<summary>Original English</summary>

**Speaker B**: my understanding is it a neural operator is is a function fit to to uh like to data or a neural network you know learns to fit functions to data is that a good intuition here

</details>

**Speaker A**: 是的，所以你知道，从这个意义上说，神经算子类似于……它和神经网络是一样的，对吧？你都是在数据上进行学习。但不同之处在于，你可以把神经算子看作是神经网络的泛化。标准的神经网络，其输入和输出都是固定大小的。比如在语言中，我们有固定的词汇表，我们固定了输入和输出是什么；在计算机视觉中的图像和视频也是一样，我们假设一个固定的分辨率，而且你知道，我们的输入和输出始终处于那个固定的分辨率，我们不能在事后改变它。然而，对于许多物理数据而言，其核心思想是我们的世界本质上是多尺度的。所以你不应该事先就决定分辨率是多少，你知道，也许你只有粗分辨率的天气数据，但实际上物理现象是在更精细的尺度上发生的，对吧？也许之后你想加入更精细分辨率的额外数据，或者在更精细的分辨率上加入物理约束。所以我们应该具备这种灵活性，我们真的不应该在这些固定的分辨率下来看待世界，而是要看到这个真实世界是在无限分辨率下运行的。而这正是神经算子所能实现的，因为它们将输入和输出建模为连续的函数，可以被无限解析，可以有无限的离散化。现在在推理阶段，你可以给它输入，并要求它输出任意分辨率的结果。所以你不再仅仅局限于我们在标准神经网络中看到的训练时的分辨率，这就是神经算子所能带来的功能。神经算子让我们能够随心所欲地放大和缩小。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so you know neural operators are in that sense similar to you know it's the same as neural networks right you're learning on data but the difference is neural operators are you can think of it as a generalization of neural networks so with standard neural networks the inputs and outputs are of fixed sized so in language we have fixed vocabulary we fix what the input and output are and same with images in computer vision in videos we assume a fixed resolution and we always you know our inputs and outputs always at that fixed resolution we can't change it post-hoc whereas with a lot of this physical data the idea is our world is inherently multi-scale so you should not be like deciding beforehand what the resolution is you know maybe you have like weather data available only at coarse resolution but really the actual phenomena is happening at a finer scale right and maybe you want to after that incorporate either additional data at finer resolution or add in physical constraints at finer resolution so we should be having that flexibility and we should really think of the world not at these fixed resolution but one that's happening uh infinitely you know that one the real world happens at that infinite resolution and that's what neural operators enable because they model inputs and outputs as continuous functions that can be infinitely resolved that can have infinite discretization and now we can have you know at inference time you can give it now inputs and ask for outputs at any resolution so you're not just limited to the resolution of training that we see in standard neural networks and that's what neural operators enable so neural operators enable us to zoom in and out as we like

</details>

**Speaker B**: 那么显然，正如你所说，对于任何受约束的函数，对吧，你可能会有很多很多拟合这些数据的函数，这很容易导致过拟合。那么你是如何进行正则化的呢？

<details>
<summary>Original English</summary>

**Speaker B**: so obviously that as stated that any function that that's under constraint right you could have many many functions that fit this fit the data it'll be easy to overfit so how do you regularize that

</details>

**Speaker A**: 是的，所以当然，如果你问的是在比所见过的更高分辨率上进行预测，也就是我们所说的零样本超分辨率（zero-shot super resolution），你多少是在做一些猜测，对吧？这也正是这些模型正在做的事情，它们试图进行正则化，并某种程度上平滑地扩展到更高的分辨率。但是，当然，如果你现在给模型提供额外的信息，比如一个物理损失函数，你可以给它偏微分方程约束、守恒定律，现在你可以在比你拥有的数据更精细的分辨率上强制执行这些约束，那么在某种程度上就会有更多的引导。这样一来，它现在即使在更高的分辨率下也能得出正确的答案，因为你是在更高的分辨率下给它提供约束的。因此，这就是我们如何确保这些物理信息神经算子（physics-informed neural operators）能够在比可用训练数据更高的保真度和更高分辨率下工作的原因。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so certainly like you know you know if you're asking about making predictions at a higher than what's seen like what we call zero short super resolution you're kind of making some guesses right and and that's what these models are doing they're trying to regularize and kind of smoothly extend to higher resolution but of course if you now give it the model additional information in terms of let's say a physical loss so you could give it partial differential equation constraints conservation laws and you can now enforce them at a finer resolution than the data you have then there's more guidance in a way so that way it can now come up with the the right answers even at higher resolution because you're you know giving it constraints at higher resolution and so that's how we can ensure that these physics-informed neural operators can work at higher fidelity and higher resolution than even the training data that was available

</details>

### 傅里叶神经算子 (Fourier Neural Operator)

**Speaker B**: 我的理解是，你们的很多工作都使用了一种特定类型的神经算子，也就是傅里叶神经算子（Fourier neural operator）。傅里叶是一个对偶域，它扩展了输入的整个域。这涉及很多专业术语，也许你能直观地解释一下，为什么这很重要？它是如何起作用的？

<details>
<summary>Original English</summary>

**Speaker B**: my understanding a lot of your work uses a particular kind of a neural operator a Fourier neural operator so Fourier is a dual domain it is extended across the entire domain of the inputs that's a lot of jargon maybe can you give some intuition for why why is that important how does that help

</details>

**Speaker A**: 我刚才提到神经算子作为一类模型，它允许我们拥有任意分辨率的输入和任意分辨率的输出，对吧，并学习它们之间的映射。所以这实际上被称为算子，也就是函数空间之间的映射。这就是“神经算子”这个名字背后的原因。傅里叶神经算子是我们早期提出的一种架构设置，它之所以如此成功，是因为它在效率和表达能力之间取得了很好的平衡，对吧。那么，为什么傅里叶空间是个好空间呢？傅里叶空间允许我们……你知道，它像你提到的那样是一个对偶空间，但它真正让我们能够捕捉到非局部（non-local）现象，对吧？也就是说，在傅里叶域中非局部的东西甚至可以被高效地捕捉。正如我们在自然界中看到的许多现象，无论是流体动力学、材料变形还是量子化学，它们很多都是非局部的。你知道，微分方程中导数是局部的，但它的逆运算，你实际上是在做积分，它是非局部的，对吧？所以解是非局部的，而这些模型能够捕捉到这一点。但同时，做傅里叶变换是高效的，而且它很好地捕捉到了我们在许多自然现象中看到的归纳偏置（inductive bias）。但这并不意味着我们完全在傅里叶基下捕捉这个世界，对吧？它不是傅里叶基下的线性表示，那是经典数值方法所做的。我们在傅里叶层之间加入了非线性，就像 Transformer 和其他神经网络一样，我们还加入了残差连接。所以，所有这些受到在其他神经网络中表现良好的架构方面启发的元素，将它们结合在一起，真的帮助我们获得了两全其美的结果。你可以这样想：如果我们使用 Transformer，并且我们需要非常高的分辨率，这将会因为二次复杂度和全对全的连接而变得不可行。另一方面，如果你用傅里叶变换来做，我们拥有准线性复杂度，但仍然具有某种形式的全局连接，使得我们能够对这些非局部现象进行建模。这就是为什么它是一个很好的折中方案。

<details>
<summary>Original English</summary>

**Speaker A**: what i mentioned neural operators as a class of models that allow us to have any resolution input and any resolution output right and learns the mapping between them so that's really called an operator so the mapping between function spaces so that's the reasoning behind the name neural operator and in a Fourier neural operator was one of the early setups we or architectures we came up with and the reason why that's been so successful is because it kind of strikes a nice trade-off between efficiency and expressivity right so why is the Fourier space a good one the Fourier space allows us to you know it's a dual space like you mentioned but it really allows us to capture non-local phenomena right so meaning something that's like uh non-local in the Fourier domain could be even efficiently captured and the lot of phenomena like we see in nature whether it's fluid dynamics material deformation quantum chemistry it's all you know there's a lot of them are non-local you know the differential equation like the derivative is local but the inverse of it is you're kind of doing essentially integration it's non-local right so the solutions are non-local and these models are able to capture that but at the same time doing Fourier transform is efficient and it kind of like nicely captures a lot of inductive bias we see in many of these natural phenomena but this doesn't mean that we are capturing the world entirely in the Fourier basis right it's not a linear representation in the Fourier basis which is what classical numerical methods do we add non-linearity just as a transformer and other neural nets in between Fourier layers and we also add residual collections so all of these architectural aspects that are inspired by other neural nets that work well in other neural nets bringing that together really kind of helps us get best of both the world so you can think of like if we were to use transformers and we require a very high resolution it would become untenable because of the quadratic complexity and all to all connections on the other hand if you did that with Fourier transforms we have like quasi-linear complexity and still we have global connections in a way we can model these non-local phenomena and so that's why it's a nice middle ground

</details>

**Speaker B**: 所以这让你能够从其他地方发生的事情中学习，就像在讨论芝加哥发生的事情是否可能会对旧金山发生的事情产生影响。嗯，也许不会，但核心思想就是这样。

<details>
<summary>Original English</summary>

**Speaker B**: so that allows you to learn from what is happening on the other like it is talking whether what's happening in Chicago may have some impact on what's happening in San Francisco well maybe not but that's the idea

</details>

**Speaker A**: 是的，这在时间上也是同样的思想。就像，是的，你知道，我认为在某个时刻也许是局部的，但最终它们会对其他地方产生影响。是的，所以在空间和时间上，我们都想要捕捉那种依赖关系。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so that's the idea in time like kind of yes there is you know like and I think like yes you know at this point maybe local but eventually they have an impact in the other locations and yeah so both in space and time we want to capture that dependence

</details>

**Speaker B**: 是的，所以今天在芝加哥发生的事情，会在一个月后对旧金山产生影响，大概是这样。

<details>
<summary>Original English</summary>

**Speaker B**: yeah so what happens today in Chicago will happen will have an impact in a month in San Francisco or something like that

</details>

**Speaker A**: 是的，所以你知道，存在短期和长期的影响。在短期内，我们会考虑可预测的天气；但从长远来看，我们讨论的是气候，对吧？所以发生的事情，你可能无法准确地说出，你知道芝加哥发生的事情会导致旧金山发生什么，那就像是蝴蝶效应。但另一方面，我们可以给出某种平均情况，你知道，如果整个区域出现热浪，我们大概会知道那里的温度将高于平均水平。所以这些就是我们可以共同捕捉的方面。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so you know so there is like both the short term and the long term effects so in a short term like we think about predictable weather but longer term we're talking about climate right so what happens you may not be able to say precisely you know what happens in Chicago what will happen in San Francisco that's like the butterfly effect on the other hand we can kind of give averages you know if there's heat wave in this kind of overall region you know we kind of have an idea that it's going to be higher than average temperatures so those are the aspects we can capture together

</details>

**Speaker B**: 从架构的角度来看，对于在座的所有人工智能工程师，我们仅仅是在谈论将所有的工作都在傅里叶域中进行吗？也就是说它本质上是同一个神经网络，只是我在傅里叶域中操作，还是说为了正确地做到这一点，还需要其他方面的内容？

<details>
<summary>Original English</summary>

**Speaker B**: from an architectural standpoint for all the AI engineers here are we just talking about doing all the work in the Fourier domain but it's basically the same neural network but I'm just operating in the Fourier domain or is there other other aspects that are that are required in order to do this properly

</details>

**Speaker A**: 所以我想想，也许最简单的理解方式是，你知道，如果你把 Transformer 架构想象一下，现在你不再使用注意力图（attention map），而是使用了傅里叶变换。但你仍然拥有其他的非线性部分，你拥有残差连接，架构中许多其他的赋予它表达能力的部分依然存在。我们可以将其提升到更高的维度，比如你的通道空间（channel space），赋予它更多的表达能力。所以所有那些最佳的原则仍然是可用的，但傅里叶变换帮助我们捕捉了那种全对全的依赖关系，而不需要我在 Transformer 中看到的那么巨大的计算复杂度，这是有道理的。

<details>
<summary>Original English</summary>

**Speaker A**: so think of it I guess maybe the easiest way to think about it is you know you can if you think of a transformer architecture instead of like the you know attention map you now have the Fourier but you still have other non-linearities you have like you know the residual you have you know many other parts of the architecture still there that give it like expressivity you can we have lifting to higher dimension like you know your channel space to give it more expressivity so all of those kind of best principles are are still available but the Fourier helps us capture that all to all the you know for dependence without requiring very huge complexity that I see transformers that makes sense

</details>

**Speaker B**: 另一个优势是它赋予了你天然的多尺度能力。这里有一种隐含的截断，你知道，如果你有信号处理或物理学背景，你可能会问：在线性系统中，如果你线性地处理所有事情，就会有一个最大频率，你知道的，超过那个频率你就无法表示任何东西。但是，在非线性域中加入这些其他的架构改变，实际上是如何影响你对频率边界的选择的呢？

<details>
<summary>Original English</summary>

**Speaker B**: the other advantage is that it gives you the natural multi-scale what's sort of a implicit cutoff is you know the sort of if you have a signals background or physics background you might ask you know in linear if you're doing everything linearly there's a maximum frequency and you know pull you know above that you can't represent anything but how does that how does adding these other architectural changes in a non-linear domain actually affect you know your choices of frequency bounds yeah

</details>

**Speaker A**: 是的，那是一个非常好的问题。这也正是表达能力的用武之地，对吧？否则，如果你仅仅是对一个信号进行傅里叶变换并试图表示它，你知道，那正是数值方法也曾尝试去做的事情，而这需要非常精细的离散化。这就是为什么用经典方法进行模拟成本非常高的原因。相反，如果我们想摆脱这种做法，想要去学习特征（这正是深度学习的核心），那么我们就不能强迫它仅仅处于傅里叶域。我们必须赋予它非线性能力，让它去弄清楚表示信号的最佳基底到底是什么。所以这就是我们拥有的一种很好的结合方式：所有这些非线性都将帮助它找到正确的空间。而且，如果你在那个隐空间（latent space）中做傅里叶变换，那可能是一种更高效的表示方式。所以这就是一种思考方式，因为首先我们正将信号提升到更多的维度，即使信号本身只有两维或三维。

<details>
<summary>Original English</summary>

**Speaker A**: yeah no that that's a great question and that's where the expressivity comes in right otherwise if you're just taking a Fourier transform of a signal and trying to represent it you know that's what numerical methods have also attempted to do and that requires very fine discretization and that's why it's very expensive to do the simulations in a classical way and instead if you want to move away from that and say we want to learn the features which is what deep learning is all about then we cannot force it to be only in the Fourier domain we have to give it non-linearity to figure out what the right basis for you know the best basis to represent the signals are and so that's the kind of like nice kind of combination we have that it's like all these non-linearities will help it kind of you know find the right space no fun in tendence this is the right and so you know the and if you do Fourier in that latent space you know that may be a more efficient way to represent so that's one way of thinking because you know first of all we're lifting the signal to more dimensions even if the signal is two or three

</details>

<!-- chunk 3/7 -->

### 高维空间与非线性变换

**Speaker A**: 维度方面，我们现在把它提升到了更高的维度，所以在那个空间里，我们的想法是去学习，并且我们是在做一个非线性的提升，对吧？因此那里已经存在一个潜在空间，然后我们在傅里叶变换之间做进一步的非线性变换。这意味着我们在说，是的，你知道，也许只有这些有限数量的频率模式它的表达能力是不够的，但是当我加入非线性时，我就能，你知道，我就能稍微更好地捕捉它们。

<details>
<summary>Original English</summary>

**Speaker A**: dimensions we are now lifting it to much higher dimension so in that space the idea is to learn and we're doing it as a non-linear lifting right so there's already a latent space there and then we are doing further non-linear transformations in between our Fourier transforms so that means we are saying yes you know maybe with these limited number of frequency modes it's not expressive enough but when I add non-linearities I can you know I can kind of more nicely capture them.

</details>

**Speaker B**: 所以你的职业生涯早在神经网络真正，我猜，起飞之前就开始了，对吧？所以我想那时候人们确实非常关注，你知道，合适的基集（basis sets），以及你知道的，函数展开、正交多项式或者其他什么。从你研究的立场来看，这种演变是怎样的？就像整个社区已经从那种方法演变到了“哦，不管了，把所有的东西都扔进去（throw it all in）”，但看起来你仍然相信至少其中的一些概念可以作为指导原则。你是否认为，实际上确实可以从，你知道，经典的数学，比如严格的数学技术中汲取经验教训？即使你现在仍然只是“把所有能用的东西都砸向问题（throwing the kitchen sink at things）”，你仍然可以利用这些技术来帮助改善对现实世界的建模？

<details>
<summary>Original English</summary>

**Speaker B**: So you started your career back before neural networks were I guess taken off right so I think back then people really did think a lot about you know appropriate basis sets and you know function expansions and orthogonal polynomials or whatever how does that evolution from you know your research standpoint how like as the community has evolved from that to oh just crew it throw it all in it seems like you still believe in at least some of those concepts as being guiding principles do you think that that that there is actually so lessons to be taken from you know classical mathematical like rigorous mathematical techniques that you can use those techniques actually to help improve modeling of the real world even if you still are just throwing the kitchen sink at things.

</details>

### 结合物理约束与计算复杂度

**Speaker A**: 不，我认为这是一个很好的权衡。我的意思是，很有趣，我现在大概二十多年前的本科论文就是关于分数阶傅里叶变换的，对吧？所以，是的，我的意思是，单靠它们自己，你知道，那是不足以做计算机视觉的。但我很好奇，好吧，这些技术是什么，它们的效果如何？所以，你知道，我完全同意你的看法，我们不能强迫自己只使用石器时代的技术或经典技术，对吧？我的意思是，我们必须要有特征学习（feature learning），我们必须要有灵活性、表达能力，你知道，它们必须容易优化。所以所有这些方面在深度学习中都非常重要。但是，当涉及到物理世界和物理数据时，它永远不可能像我们在语言模型中看到的那样丰富。因为，你知道，我们的天气模型大概有5万个样本，对吧？5万个分辨率相当高的样本，比如全球天气图，但这完全不能和我们在语言领域看到的相比。而在其他领域，数据甚至更少，因为模拟的成本太高了，而且真实数据可能根本无法获得。所以在这里，我们必须更多地考虑归纳偏置（inductive biases），我们必须加入物理约束，不能仅仅依赖数据。这就是我认为在架构设计上需要更多思考的地方。

另一个方面是计算复杂度。你想想语言，它只是一个维度。即使在那里，上下文长度，你知道，我们现在达到了数百万级别，我们就已经很挣扎了，对吧？我的意思是，另一方面，我们现在考虑的不仅仅是二维、三维，甚至是四维（4D），你知道的，三维加上时间。如果每个维度哪怕只有几百个网格点——你知道，工业规模的起点大概是每个维度一千个网格点——我们谈论的将是几千亿甚至一万亿的上下文长度，对吧？所以，对于这种规模的任何东西，别指望能有一个 Transformer。全世界所有的计算能力加起来都不够。而且首先，它们都必须被安置在同一个地方（co-located）才有可能做到这一点。这就是为什么我们需要其他架构。

<details>
<summary>Original English</summary>

**Speaker A**: No I think it's a it's a nice I think there's a trade-off I mean it's funny my undergraduate thesis more than two decades ago now was on fractional four-year transform right and so yes I mean by themselves like you know that wasn't enough to do computer vision but I was curious okay what are these techniques and how well do they work and so you know I'm completely with you that we cannot just force ourselves to use stone age techniques or classical techniques right I mean so we have to have feature learning we have to have flexibility expressivity you know they have to be easily optimized so all of these aspects are very important with deep learning but when it comes to the physical world and physical data it's never going to be as plentiful as we see with language models because we are you know our weather model like had about like 50 000 samples right 50 000 samples of fairly high resolution like work global weather maps but it's nothing like what we see with language and in other domains it's even less because it's so expensive to simulate and the real data may just not be available and so here we have to think about the inductive biases more we have to add the physics constraints cannot be just reliant on data and that's where I think a little bit more thinking of the architectural design comes up the other aspect is computational complexity so think about language it's just one dimension and even there the context length you know we are getting to millions and we are struggling right I mean on the other hand now we are thinking about the not just 2d 3d even 40 you know 3d and time and if each of the dimension is even a few hundred grid points which is where you know industrial scale starts at like like a thousand grid points in each dimension we're talking like hundreds of billions to even a trillion context length right so forget ever having a transformer for anything of this scale all of the world's compute will not be enough and first of all they all have to be co-located to be able to ever do this so that's why we need other architectures

</details>

**Speaker B**: 但是我想稍微反驳一下，对吧？我们有视觉和视频语言模型，对吧？它们使用的是，它们基本上是学习一种映射。

<details>
<summary>Original English</summary>

**Speaker B**: but I would push back a little bit right we have the vision and video language models right and they use they basically learn a mapping

</details>

**Speaker A**: 但是分辨率非常低，这是关键。比如对于物理世界，我需要什么样的分辨率？我提到了，比如一千乘一千乘一千乘一千。所以，你知道，如果你计算一下，那已经达到了几亿、几十亿的级别。是的，所以，你知道，当我们目前思考图像和视频时，我们并没有做到那么高的分辨率。我有一个朋友，并且那个视频也是类似自回归（autoregressive）的，所以它本质上只是像，你只需要做下一个（预测）。

<details>
<summary>Original English</summary>

**Speaker A**: but the resolution is very low that's the key like for the physical world the resolution what do I require I mentioned like thousand by thousand by thousand by thousand so there you know the if you count that that's like already in hundreds of millions billions yeah so so you know we are not doing that high resolution when we think about images and videos currently I have a friend and the video is also like autoregressive so it's essentially only like you only need to do the next

</details>

**Speaker B**: 对，是的，但你是在学习，我的意思是，像通常来说你是在学习一个码本（code book），对吧？所以你拥有，你有点像是在学习潜在空间的偏差（bias），或者说现实世界到潜在空间的偏差。所以，如果你能从物理世界做一种压缩到潜在空间，那么，那么……你知道，这些自回归技术已经取得了成功。

<details>
<summary>Original English</summary>

**Speaker B**: right yeah but you're learning I mean like generally you're learning a code book right so you have you're kind of learning the bias of the latent space or the the real world to the latent space and and and so that if there is a like a compression that you can do from the physical world into the latent space then then um you know these autoregressive techniques have been successful

</details>

### 高保真度与物理现象模拟

**Speaker A**: 是的，但问题是，你知道，许多用于视觉和视频模型的自回归和，你知道的这些技术，主要是为了像，你知道，看起来不错，对吧？所以它们不是用于非常精确的模拟的。在精确模拟中，你知道的，拥有更高的分辨率和细节是非常重要的。所以我们至少需要摄入那种高分辨率的数据，对吧？所以我们需要处理它并对其进行推理。这就是很大一部分瓶颈所在，因为我们，你知道，承担不起直接丢掉所有东西然后说，“哦，让我们就在每个维度上有100个网格点，或者50个网格点吧。”因为那样的话，根本没有足够的细节来正确模拟像流体动力学、等离子体、材料如何变形这样的现象。所以所有这些都需要高保真度，而为了实现这一点，我们需要高分辨率。

<details>
<summary>Original English</summary>

**Speaker A**: yeah but the idea is you know a lot of these autoregressive and you know techniques for vision and video models are for mostly like you know looking good right so they are like not for very precise simulations and they're you know having that higher resolution and details is really important and so we need to at least take in the data of that high resolution right so we need to process that and reason over them and so this is where a lot of the bottleneck is because we you know cannot afford to just throw away everything and say oh let's just like have 100 grid points in each dimension or 50 grid points because there just isn't enough detail to correctly model phenomena like fluid dynamics plasma how materials deform so all of this requires high fidelity and for that we need high resolution

</details>

**Speaker B**: 我的理解是，你有一个论点，即人工智能需要，你知道，将物理世界融入其中，以便在未来能够扩展并保持准确性。很多人都有这个论点。你在某种程度上比较独特，因为你有几个以这种方式将我们的算子（operators）应用于物理世界的例子。然后看来你正在围绕你在这方面的经验形成一个论点。那么，你能和我们分享一些你使用神经算子（neural operators）和其他技术所做的真正有趣和令人兴奋的事情吗？

<details>
<summary>Original English</summary>

**Speaker B**: my understanding you have a thesis that AI needs you know to incorporate the physical world into it in order to scale and be accurate going forward many people have this thesis you are somewhat unique in that you have several examples of applying our operators to the physical world in this way and then it seems like you're getting a thesis around your experience here so can you share with us some of the really interesting and exciting looking things that you've done using neural operators and other techniques?

</details>

### 神经算子在天气预报中的突破

**Speaker A**: 是的，我的意思是，你知道，对我们来说，当我们开始研究例如偏微分方程的神经算子时，但更广泛地说，你甚至不需要假设它们是偏微分方程，对吧？可以是任何时空的或者是多尺度的数据。所以我们，你知道，开始寻找有趣的例子。其中一个就是像天气建模，因为天气数据是开源的，它是可以获取的，也就是来自ECMWF（欧洲中期天气预报中心），即负责全球天气建模的欧洲机构的ERA5。所以既然数据在那里，我们就想，“好吧，我们去试一试吧”，对吧？这就是它的美妙之处，每当数据可用时，这真的是个好消息。

但是当时，这回到了2021年，许多天气科学家确实警告过我们，他们说：“不不不，这太困难了，你知道，传统的天气预报有着像几十年的发展。而那是非常谨慎的、自下而上的基于物理的建模，对吧？所以假设哦，这是流体动力学，你去预测明天的天气等等。”所以很多想法都是这样的：人工智能根本不可能击败，你知道的，天气建模中几十年的工作。但令我们惊讶的是，我们就是继续前进了。我们训练了它们，我们使用了神经算子来能够有效地捕捉这些现象。然后现在我们，令我们惊讶的是，我们发现它不仅，你知道，准确，它几乎与传统天气模型所能达到的准确度一样好，而且速度快了几万倍。所以过去需要大型超级计算机才能运行的东西，现在可以运行了，而且我们只需要一块消费级的，比如GPU，就像，你知道的，它是一个很小的模型。它非常适合，速度非常快，而且非常准确。

我认为那直接改变了每个人的想法。在那之后，DeepMind、华为以及许多其他机构跟随我们的脚步，一年后发布了他们自己的模型。我们是第一个实际开源我们的天气模型 FourCastNet 的团队，并且是以宽松许可的方式进行的。正是这一点使得各家公司、气象机构以及所有人都能在我们的基础上进行构建。所以，你知道，看到天气模型现在被广泛应用，气象机构正在采用它们，这真的是一场非常有趣的革命。而且它使我们现在能够让例如全球南方的那些小型气象机构，拥有过去只有非常大型的机构才能做到的同等水平的保真度，对吧？所以这是在使天气建模民主化。所以这只是一个关于在哪里取得了非常快速进展的例子，并且在说“哦，现在我们可以将人工智能作为一种可靠的天气建模方式”方面实现了范式转变。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah I mean you know for us when we started with like neural operators for partial differential equations but also more broadly you don't even need to assume their partial differential equations right could be any spatiotemporal or data at multiple scales so we you know set out looking for interesting examples and one of them was like weather modeling because the weather data is open source it's available called the EDO5 from the ECMWF the European Agency for Global Weather Modeling and so given that the data was there we were like okay let's just go try it right and that's the beauty of it whenever data is available it's really good news but a lot of weather scientists did caution us back then this was back in 21 and they said no no no this is so difficult you know there have been like decades of like development in traditional weather forecasting and that's very careful bottom-up physics-based modeling right so assuming oh this is the fluid dynamics can you go predict the weather the next day and so on and so that's how a lot of the thinking was that AI is just not going to be able to beat the you know decades of work in weather modeling but to our surprise we just went ahead we trained them we used neural operators to be able to effectively capture the phenomena and then now we to our surprise we found that it's not only you know accurate it's almost as close to the what the traditional weather models can do accurately but also tens of thousands of times faster so what would take a big supercomputer to run can now be run and we only needed a consumer grade like GPU like you know it was a small model it fit very well it's very fast and it's accurate and I think that just changed everybody's thinking after that DeepMind Huawei many others followed us a year later released their own models we were the first to actually open source our weather model forecast net and do it permissively so that's what allowed companies weather agencies everybody to build on us and so you know it's been a really interesting revolution to see that the weather models are now out there weather agencies are adopting them and it allows us to now have small weather agencies in the global south for instance have the same kind of fidelity that very big agencies were in the past only able to do right so it's democratizing weather modeling and so that's just one example of where there's been very quick rapid progress and a paradigm shift in terms of saying that oh now we can have AI as a reliable way to do weather modeling

</details>

**Speaker B**: 我看到了，你知道，你提到的那些模型，你获得了一个别人没有的洞见。并且人们能够设计出其他机制来紧随你之后，但这里发生了一些类型的思维转变。那么这是因为，仅仅是因为“我们相信这些数据中有足够的结构供我们学习，而人们只是做错了”，并且人们找到了其他学习这种结构的方法，但你的方法非常，嗯……

<details>
<summary>Original English</summary>

**Speaker B**: I saw that you know the the models that you mentioned you made an insight that nobody else had and that people were able to devise other mechanisms to kind of follow behind you but there was some sort of shift in thinking that was required here and was it it was it simply we believe that there's enough structure in this data to learn and that people are just doing it wrong and people found other ways to learn the structure but that your method was very um

</details>

### 从短期天气到长期气候建模的融合

**Speaker A**: 所以让我，让我澄清一下，对吧？所以这里，你知道，首先第一项工作仅仅是说，你知道，看，传统上这是通过试图求解偏微分方程来完成的，每次都是一遍又一遍地做。而人工智能从数据中学习模式，并且可以同样准确但速度很快，对。然后接下来的几次迭代是说，你知道，我们如何使它更准确？这涉及到这样一个方面，你知道，存在短期天气，比如未来两周内可以预测的内容。然后有长期预测，你知道，进入次季节，最终到气候建模。传统上人们所做的是为这些不同的场景使用不同的模型。有一种系统适用于短期，另一种系统适用于长期。但对我来说，只有一个地球。你知道，如果你想要一个基础模型，如果声称它应该能够同时做非常短期的和非常长期的预测。而这就是在 FourCastNet 3，即该模型的最新迭代中，我们能够同时做到这两点。那是因为你也，你知道，纳入了地球的球面几何形状。

因此，有很多架构在短期天气预测中获得了相当不错的准确率。但是当你将它们运行更长时期时，当你运行它们比如几个月甚至一年，甚至在那之前，它很快就崩溃了，对吧？因为它假设世界是一个矩形，而它并不是。所以将所有的几何结构和信息整合到神经算子中，意味着我们可以忠实地在长期运行同一个模型，并将其变成一个气候模型。这就是艾伦人工智能研究所现在已经基于我们的神经算子架构建立了气候模型的原因。这也是唯一一个作为人工智能模拟器起作用的模型，对吧？没有其他任何架构适用于气候，因为气候要求我们假设世界是一个球体。并且如果你反复推演，你要一直保持那个信息。而如果它只是一个狭义的替代模型，那这就是我认为的天气模型，你只狭隘地看几个指标，许多不同的架构应该都能胜任，对吧？但是如果你要求一个架构完成一系列不同的任务，像一个基础模型一样，那就是为什么纳入地球是一个球体的几何结构，并使用神经算子这一种有效的方式来做到这一点，使我们能够实现这一目标的原因。

<details>
<summary>Original English</summary>

**Speaker A**: so let me let me clarify right so there is you know first of all the very first work was to just say that you know look traditionally this has been done with trying to solve partial differential equations each time doing it again and again whereas AI from data learns patterns and can be just as accurate but fast yeah and then the next iterations was to say you know how do we make it even more accurate and there's the aspect that you know there is the short term weather like what is predictable for the next two weeks and then there's the long term you know going to sub-seasonal to ultimately climate modeling and traditionally what people did was to have different models for these different scenarios there's a different kind of system that works for short term another system works for long term but to me there's only one earth you know if you want a foundation model if the claim is that it should be able to do both very short term as well as very long term together and that's where in forecast net three the latest iteration of the model we're able to do both and that's because you also you know incorporate the spherical geometry of the earth and so with a lot of the architectures that have been getting fairly good accuracies for the short term weather when you run them for longer term when you run them for like several months to even year even before that it just very quickly blows up right because it assumes the world is a rectangle which it isn't and so incorporating all of the geometry and that information into neural operators means that we can faithfully run the same model also longer term and make this into a climate model this is where the Allen AI Institute has now built climate models based on our neural operator architecture and that's the only one that works as an AI emulator right none of the other architectures work for climate because climate requires us to assume the world is a globe and that if you are repeatedly rolling out you kind of keep that information whereas if it's like a narrow surrogate that's what I consider a weather model you just narrowly look at a few metrics many different architectures should do the job right but if you are asking one architecture do a range of different tasks like a foundation model that's where incorporating the geometry of the earth which is that it's a sphere and using neural operators an efficient way to do that enables us to accomplish that

</details>

**Speaker B**: 是的，所以关于 FourCastNet，你说是在58000个数据点上训练的。我们能不能谈谈，比如这是什么样子的？就像，数据输入是什么样子的？你实际上试图从这里预测什么？然后，类似大规模的，你知道，你说你正从天气走向气候，做这件事看起来是什么样的？因为我可以想象，如果你有5万个数据点，这些是，你知道，比如北美的一些高分辨率数据，那么，你知道，它们可能甚至依赖于当地的地理环境。比如，如果你总是在模拟，你知道的，堪萨斯州，这能迁移到，嗯，你知道，比如说瑞士阿尔卑斯山或者其他地方吗？然后这又能迁移到，呃，你知道，迁移到……

<details>
<summary>Original English</summary>

**Speaker B**: yeah so forecast net you said trained on 58,000 data points can we just talk about like what does this look like like what does the data input look like what are you actually trying to predict from here and then what is where the like the large scale you know you said you you're going from weather to climate what does it look like to do that because I could imagine if you have 50,000 data points these are you know some high resolution in North America then you know they might even depend on the local geography like like if you are always modeling you know Kansas does this kind of transfer to um you know let's say the swiss Alps or something and then does that transfer to uh you know to

</details>

<!-- chunk 4/7 -->

### 天气模型与气候模型

**Speaker A**: 首先澄清一下，我们在全球天气模型上训练它，对吧？所以我们掌握了地球周围的所有信息。我们要求它进行预测，比如给定当前的天气情况——比如风况、湿度等等，接着会发生什么。你知道，以一种自回归的方式，每六个小时一次，预测接下来的六个小时会发生什么，依此类推。你不断展开（roll out），训练模型进行预测。所以，你懂的，你有可能让同一个模型永远预测下去，对吧？但可预测的窗口期就像天气一样。如果你想超越这个窗口期，去做我们所谓的系综（ensembles），也就是说，你要对几个月到几年内发生的事情进行概率估计，这就是你获得气候模型的方式。

<details>
<summary>Original English</summary>

**Speaker A**: him so first of all to clarify training it on the global weather model right so we have all the information around the earth and that we are you know asking it to predict like given the current weather uh like say wind conditions humidity and so on what happens uh you know in an auto regressive way and it's every six hours so what happens in the next six hours and so on and you roll out and you train the model to predict and and so you know you can have potentially the same model predict forever right so but the predictability window is like the weather and if you want to go beyond if to do what we call ensembles meaning you have like a probabilistic estimate of what happens uh in several months to years and that's how you get a climate model

</details>

**Speaker B**: 好的，所以你实际上拥有这些局部预测器的系综，然后你对这些系综使用某种统计方法，从而得出一个气候模型。

<details>
<summary>Original English</summary>

**Speaker B**: okay so you have you actually have an ensemble of these local predictors and then you use the some sort of statistics on the ensemble to get a climate

</details>

**Speaker A**: 是的，所以你有点像进行了几次展开（rollouts）。本质上，你拥有多条展开轨迹，然后你得出结果。所以实际上，这非常关键。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so you kind of like have several rollouts essentially you have several trajectories of rollouts and then you get and so you can actually pretty key here

</details>

**Speaker A**: 是的，这就是为什么那是传统气候建模面临的最大瓶颈，因为甚至哪怕只进行一次单一的运行都太昂贵了。你必须进行长轨迹、极高分辨率的计算。你知道，这就是为什么我们在进行例如气候变化预测时，往往缺乏很多极高分辨率的能力。

<details>
<summary>Original English</summary>

**Speaker A**: yes and that's why that's the biggest bottleneck with traditional climate modeling that it's so expensive to do even one single run you have to do long trajectories very very high resolution and uh you know that's why we don't have a lot of very high resolution ability to do climate change predictions for instance

</details>

**Speaker B**: 那么，你们如何验证气候模型呢？你们做了大量的展开（rollouts），然后看事物在某种聚集状态下是如何演变的。我的意思是，“蝴蝶效应”这个词说得很好，在局部范围内，我认为我们可以相信，即使是一个完美的气候模型或完美的天气模型，也只能给你大约两周的准确预测，在那之后，它就会变得无法计算。所以，嗯，你们做了大量的展开，嗯，存在一些混沌现象，你们把所有这些东西平均起来。你们实际上是如何验证这在足够长的时间内是有效的呢？而且还需要技巧。

<details>
<summary>Original English</summary>

**Speaker B**: so how do you validate climate so you do lots of rollouts and you look at sort of how things evolve kind of an aggregate i mean nicely said butterfly effect locally i think we can believe even a perfect climate model or perfect weather model would only give you maybe two weeks before it sort of it becomes non-computable so um you do lots of rollouts um there's some chaos you you average all these things how do you actually validate that this works over long enough times yeah and skills

</details>

**Speaker A**: 是的，你知道，这是一个很棘手的问题，对吧？例如，你必须确保你满足了所有的物理约束，如果你只是进行标准的展开，那是很可能无法实现的。所以，我们正在进行的一些研究是，当你们在进行展开时，你们如何强制执行正确的物理约束？比如，你不想完全抹去那些细节，因为那样就不准确了；但另一方面，如果你保留它们，它们在物理上可能是无效的。所以这仍然是一个悬而未决的问题。这就是困难所在：你希望人工智能速度快，希望能够进行这些长期的气候模拟，同时又要对它们充满信心。但这些正是我们现在正在努力解决的问题。

<details>
<summary>Original English</summary>

**Speaker A**: yeah and and you know it's a tricky question right so for instance you have to kind of ensure that you satisfy all of the physical constraints and if you just do a standard rollout that is you know likely not going to happen and so some of the ongoing research we're how do you kind of enforce the right physical constraints as you do the rollouts like you don't want to you know completely wash out the fine details because then it's not accurate uh but on the other hand if you keep them you may be physically they're invalid so this is still an open problem and that's what makes it difficult that you want ai to be fast and you want to be able to do these long climate simulations and at the same time be able to have full confidence in them but these are things we are working on now

</details>

### 极端天气与物理约束的结构

**Speaker B**: 我不知道这属于天气还是气候，但我们最近刚刚经历了现代气候数据历史上最极端的热浪之一，对吧？嗯，就在美国西南部这里。我想知道你们是不是……我不知道你是否参与了这件事，或者经常关注，但你知道你或其他人是否真的正确地模拟或预测了那次事件吗？

<details>
<summary>Original English</summary>

**Speaker B**: i don't know if this falls into weather or climate but we recently just had one of the most extreme heat waves in the history of modern climate data right um in the just right here in the uh kind of southwest united states i'm wondering where you did you i don't know if you were involved in this and regularly but do you know if you or anyone actually modeled that or predicted that correctly

</details>

**Speaker A**: 是的，是的，所以我们有。我知道我并没有这次具体事件的信息，但我们已经在我们最新的 FourCastNet 3 模型中测试了各种极端的灾害性天气事件，对吧？而这就是关键所在，在这些地方你需要的是概率性的答案。当我们研究极端事件时，仅仅给出一个确定性的输出然后说这就是天气是不够的。所以我们需要仔细的概率校准，而我们证明了我们能够很好地捕捉到这些。我认为，即使在我们的第一次尝试中，我们可视化了一些特定的飓风和风暴，它也能做得很好，这令人非常惊讶。因为你会认为罕见事件并不是人工智能能做好的事情，对吧？你会觉得它在典型事件上能做得很好。但我认为，更广泛的教训在于：物理世界可能更加宽容。因为你知道，在像飓风这样的极端事件发生的地方，它们具有非常具体的物理特征。对吧？所以它虽然极端，但是以一种非常具体的方式表现出来。所以，也许你不需要那么多的样本，因为物理世界有大量的结构。这是我们一次又一次看到的东西：在许多其他例子中，存在着大量的结构。你知道，谈论等离子体和聚变反应堆，你知道，我们仅仅只有几千个样本，但我们能够非常准确地预测像破裂（disruption）这样的事件。而且，我们能够比传统模拟快一百万倍地完成它。对我来说，是的，所有这些听起来都非常令人惊讶，但这是因为我认为大自然帮了我们很大的忙，它有着大量的潜在空间结构，嗯，我认为传统的数值方法是无法揭示这些的。因为它们更关注正确性，认为在任何场景下你都应该能够解开这些方程。另一方面，对于人工智能，它是从数据中学习的，它在揭示这种结构，它在揭示这些问题是多么容易或多么可解。这就是我们在许多情况下看到的情景。

<details>
<summary>Original English</summary>

**Speaker A**: yeah yeah so we have i know i don't have information on this specific one but we've tested in our latest uh forecast net three model extreme weather events of all kinds right and that's the key like you know that's where you need probabilistic answers so having just one deterministic output and saying that this is the weather is not enough when we are looking at extreme events so we need careful probabilistic calibration and we show that we are able to capture those well and i think that was the surprise even in our very first attempt that we visualize certain hurricanes and storms and it was able to do well which is very surprising because you would think that rare events are not something ai would do well right would do well on typical events but i think this is where more broadly the lesson is the physical world may be more forgiving because you know where there are extreme events like hurricanes that have very specific physical signature yeah right so it's like extreme but in a very specific way so maybe you don't need as many samples because the physical world has a lot of structure and that's something we see this again and again that there is a lot of structure in so many other examples you know talk about plasma and fusion reactor you know we barely have a few thousand samples but we are able to accurately predict events like disruption very well and we are able to do that a million times faster than what traditional simulations were able to do to me yes all these sound very surprising but it's because i think the nature helps us a lot and it has a lot of latent space structure that's uh that i don't think traditional numerical methods are able to uncover because they are focusing more on correctness that in any scenario you should be able to solve these equations on the other hand with ai it's learning from data it's uncovering this structure it's uncovering how easy or kind of tractable these problems are and that's what we see in many cases

</details>

**Speaker B**: 是的，我有一个类似的类比，所以从，你知道，我自己的领域大概更接近于计算生物学，但你知道 AlphaFold 显然是，嗯，是社区中一个非常令人兴奋的发展。所以，解决了蛋白质结构预测问题，当然，实际上解决了什么还有各种需要注意的地方。嗯，我想我们在上一期与 Bolts 团队的播客中讨论过这个，如果听众想了解更多，鼓励他们去听那期节目。但我认为关于蛋白质结构的一个重要观点是，它确实受到了物理学的约束。从某种意义上说，这也是为什么它是生物学领域中为数不多的巨大胜利之一，生物学在其他方面是非常复杂的。一般来说，我们遇到了麻烦，机器学习取得了很多成功。而且似乎那些通过微分方程解决的问题，或者我应该说能够通过微分方程很好地建模的问题，拥有更大的空间，也能够作为一种通用形式来整合这些技术。我想这是毫无疑问的，是的，所以……

<details>
<summary>Original English</summary>

**Speaker B**: yeah i've had a similar analogy so from you know my own domain is probably closer to computational biology but you know alpha fold is the obvious uh like really exciting development in the community so the solving protein structure prediction and of course all the caveats of what was actually solved well i think we discussed this in a in a previous episode with the bolts team encourage listeners to listen to that if they want more but one of the i think points about protein structure is that it really is constrained by physics and that's why it was in some sense one of the few big wins in the field of biology which is otherwise very complex and we've had trouble generally speaking machine a lot of success and it seems like problems which are solved by differential equations or i say modeled well by differential equations have a lot more room for also integrating these techniques um as a general form don't think there's a question yeah so

</details>

### 多尺度世界与神经算子

**Speaker B**: 所以，所以回到我的问题，嗯，我们有气候或者说天气和气候，我们有等离子体，我们有，嗯，生物学。我知道你为我们准备了一些可视化图像，你能，你能跟我们分享一下吗？嗯，那看起来是什么样的？你知道，所以，那些可视化，然后贯穿其中的主线是什么？我想也许听众们已经对此有所猜测了，但我真的很兴奋能看到那个。

<details>
<summary>Original English</summary>

**Speaker B**: so so getting back to my question um we have climate or weather and climate we have plasma we have um uh biology and i know that you you prepared for us a few visualizations can you can you just share with us um what does that look like you know what so the visualizations and then what is the thread that runs through here and i think maybe the listeners will already have a hint about that but i'd be really excited to see that

</details>

**Speaker A**: 是的，我当然可以分享其中的一些。我的意思是，这个只是一种展示，你知道，我们的世界有不同的尺度，对吧？这些都是在不同尺度下发生的现象的例子，从原子到蛋白质，甚至到像我们谈论的天气这样的行星尺度。你知道，我们需要捕捉所有这些东西。这正是神经算子（neural operators）被设计出来要做的，你可以，你知道，输入这些不同尺度的数据。而这恰好就是使许多物理世界问题变得困难的一个方面——对于精细尺度的需求。你知道，我们谈到过许多传统的计算机视觉视频模型，它们仅仅是被设计来让事物在视觉上看起来很好。那只需要足够低的分辨率，它是可处理的，是自回归的，这就足够了，你知道，它是能起作用的，它处理的是足够短的视频。但这并不是许多物理模拟的运作方式。对于，你知道，工业规模、高保真度的工作，你真的需要高分辨率。你知道，大气就是一个例子，比如，取决于分辨率，你所观察到的不同现象才能被捕捉到。所以，如果你没有那种分辨率，你就会错过它。现在的问题是，利用人工智能，我们做这件事能比使用传统模拟快得多吗？这个关于神经算子的图展示出，你知道，如果你使用标准的神经网络，并且你有一个固定数量的像素，就像你在这边看到的那样，当你放大时，它会变得模糊，对吧？那就是终点了，超出那些固定分辨率你就无法捕捉到任何东西。但是神经算子的理念在于，因为它是一种函数空间表示（function space representation），这意味着你可以不断放大。你可以添加相关的细节，要么通过给它提供更高分辨率的数据，要么通过提供更高分辨率的物理约束。你可以把那种多尺度的现象结合起来。

<details>
<summary>Original English</summary>

**Speaker A**: yeah i can certainly share some of them i mean this one is just kind of showing that you know we have world at different scales right and these are examples of phenomena happening at different scales from atomic to protein to even planetary scales like the weather we talked about and you know we need to capture all of that that's what neural operators are designed to do and you can you know feed in data these different scales and that's really like the aspect that makes a lot of the physical world problems hard that need for fine scale you know we talked about how a lot of traditional computer vision video models are just designed to make things look visually good and that requires low enough resolution it's tractable regressive it's enough that you know it works out it's short enough videos but that's not how a lot of the physical simulation for you know industrial scale high fidelity work you really need high resolution the you know the atmosphere is one example like you depending on the resolution you observe different phenomena can be captured so you just miss that out if you don't have that resolution and now the question is with ai can we do this much faster than what we could with traditional simulation and this one with neural operators is kind of showing that you know if you use the standard neural network and you had a fixed number of pixels like you're seeing on this side and you zoom in it gets blurry right that's the end of it there's nothing beyond those fixed resolution that you can capture but the idea is with neural operators because it's a function space representation meaning you can keep zooming in you can add it the relevant details either by giving it data at higher resolution or physical constraints at higher resolution you can kind of bring that multi-scale phenomena together

</details>

**Speaker B**: 那么物理约束在哪里呢？我的意思是，我假设这里的物理约束就像是在局部模拟，嗯，你知道，流体方程或者某种，是的，动力学。

<details>
<summary>Original English</summary>

**Speaker B**: so where are the physical constraints i mean i assume physical constraints here are like local simulating um you know fluid equations or some sort of yeah so dynamic

</details>

**Speaker A**: 都有可能，对吧？所以它可以是任何性质的。其理念是，现在你可以加入诸如守恒定律。例如，在一个不可压缩的流体中，你可以加入物质变形，比如事物是如何拉伸的；或者它可以是一个完整的偏微分方程。所以这也是一个我们一直在研究的有趣问题：各种不同物理的课程（curriculum）是怎样的？就像你提到的，你知道，某些物理可能很难强加或者作为损失函数加入，而其他的可能会容易一些。所以你也需要稍微思考一下，你知道，要强加什么。

<details>
<summary>Original English</summary>

**Speaker A**: could be right so it could be of any nature the idea is now you can add like conservation laws for instance in an incompressible fluid you can add like material deformation like how things stretch so or it can be a full partial differential equation so that's also an interesting question we've been researching how is the curriculum of different physics like you meant you know some physics may be very hard to impose or add as a loss function others may be easier so you also need to kind of you know think about what what to impose you

</details>

**Speaker B**: 懂了，而这里的直觉是，当我添加一个物理约束时，我实际上是在将它添加到损失函数中。大致上是这么回事吗？

<details>
<summary>Original English</summary>

**Speaker B**: know and the intuition is here is that when i'm adding a physical constraint i'm adding it to the loss function is that more or less what's happening

</details>

**Speaker A**: 是的，因为那样做在计算上是可处理的。你知道，如果让它成为一个硬性约束是不可处理的。然而，把它作为一个损失函数加进去是可以的，当然，我们仍然需要平衡这个损失函数与我们拥有的数据。所以我们必须，你知道，嗯，以适当的方式来做，对吧？是的。所以正如我提到的，这个就是天气模型的例子，在这里我们展示了我们如何能够捕捉像大气河这样的现象，这是我们在加州这里能看到的现象，你知道，导致真实生活的风暴。我想我们预计这周晚些时候就会有一场，所以我们会让你对这个说法负责的。

<details>
<summary>Original English</summary>

**Speaker A**: yeah because that's what is tractable you know making it a hard constraint is not tractable whereas adding it as a loss function and of course there's still the balancing of that loss with the data we have so we have to you know uh do that in the appropriate way right yeah so as i mentioned the this is the example of the weather model where here we are showing how we are able to capture like atmospheric rivers which is the phenomena we see here in california you know resultarian life storms i think we are we have one expected later this week so we'll hold you to that

</details>

**Speaker A**: 所以这个理念，你知道，我为什么展示这个，就是这种全球性现象，对吧？它们就像有几千英里那么宽，所以你真的需要非局部的模型来捕捉这些跨度极大的现象，并准确地做到这一点。而这正是我们的神经算子能够做到的。

<details>
<summary>Original English</summary>

**Speaker A**: so the idea of like you know why i show this is this kind of global phenomena right these are like thousands of miles wide so you really need non-local models that capture these very large span phenomena and do that accurately and that's what our neural operators are able to do

</details>

### 数据整合与模型可用性

**Speaker B**: 那么，所以这个的训练数据是——你之前稍微提到过这个，但我还是想知道——这是来自气象卫星的，还是说有基于地面的数据？或者它是两者的某种混合体？

<details>
<summary>Original English</summary>

**Speaker B**: so so the training data for this is you were talking about this a bit before but i'm still like wondering what is this this is weather satellites or is there ground-based data is it some hybrid of the two

</details>

**Speaker A**: 它其实是不同数据源的一种组合。所以这就是我们所谓的再分析（re-analysis）数据。这是一种历史天气数据，在某种意义上它被重新分析了。这意味着诸如卫星数据，本质上被与物理求解器告诉你的信息结合在一起，把它们同化（assimilate）到一起。然后这些数据由气象机构提供出来，我们就可以在上面进行训练。

<details>
<summary>Original English</summary>

**Speaker A**: it's it's kind of a combination of different sources so it's what we call re-analysis data so this is historical weather data that is in a way re-analyzed meaning that the sad rock satellite data is combined with essentially what the physics solvers tell you together assimilate it and so this is made available by the weather agencies and we can train on them

</details>

**Speaker B**: 所以你的意思是，他们采用一个低分辨率的数据集，也就是编译了世界上所有的数据集，你知道，就是我们在世界各地拥有的所有生物数据，然后他们使用基于物理的，你知道的经典技术进行短时间的模拟，来填补那些细节。你可以做到针对短时间跨度这样操作，但当你走得更远时，它很快就崩溃了。

<details>
<summary>Original English</summary>

**Speaker B**: so you're saying that they take a low resolution data set which is compiling all of the world's data set you know all of our biological data we have across the world and then they do short time simulations using physics-based you know classical techniques to to fill in the details and you can do that over short time spans but as you go farther it breaks down very quickly

</details>

**Speaker B**: 所以你们把这些成本摊销到所有人身上，本来每个人都必须那样做。所以有人做好了这件事，然后你们就能接手去用它。

<details>
<summary>Original English</summary>

**Speaker B**: so you're amortizing that across all the everyone would have to do that and so somebody does it and then you are able to take

</details>

**Speaker A**: 是的，我的意思是这就是数据，对吧？它已经是准备好的了。但理念在于，这种与物理学结合的数据同化方式，已经立即让我们的模型具备了物理先验信息。所以它能够，你知道，保留那些信息。也许这也是它甚至在极端天气事件上表现良好的一个原因。是的。所以这里只是想展示，我们的模型在 ECMWF（欧洲中期天气预报中心）上是可用的，那是一个气象机构，就像，你知道，欧洲气象机构。而且，所以这个大概是两年多前启动的。但是，你知道，我想是 2023 年秋天。所以你知道，我认为 ECMWF 将这些基于人工智能的天气模型提供给公众使用，对我来说是非常重大的一步。因为在那里，你知道，每个人都可以看到发生了什么。比如有几个飓风……

<details>
<summary>Original English</summary>

**Speaker A**: yeah i mean this is data right that's already prepared but the idea is already this data simulation with physics kind of makes our model physics informed immediately so it's able to kind of you know keep that information and that's why maybe that's one reason maybe it does well on even extreme weather events yeah so this is just showing that we our model is available in the cmwf which is the weather agency like you know the european weather agency uh and so this was launched like more than two years ago but you know i think fall 2023 so you know i think ecmwf making these ai-based weather models available to the public to me was a very big step because that's where you know everybody could see what's happening there were several hurricanes like for

</details>

<!-- chunk 5/7 -->

### 飓风预测与集合预报 (Hurricane Prediction and Ensemble Forecasting)

**Speaker A**: 以飓风“李”（Hurricane Lee）为例，公众由此看到了这些气象模型的作用。例如，我们的 ForecastNet 模型能够比标准的天气预报模型提前几天准确预测飓风的登陆。因此，这些模型非常适合预测极端天气并进行早期预警的理念——你知道，这无论对挽救生命还是减少经济损失来说，都具有非常重大的意义。我认为，正是由于它在这些事件中的出色表现，公众和气象科学家才更加认可它。这就是我之前提到的，在极端天气或气候的集合预报（ensemble prediction）中，不仅仅是观察单一的轨迹，对吧？因为你知道，除非有人拿着马克笔（Sharpie）硬说飓风会往哪走（这里无意冒犯），但你真正想要的是概率预测（probabilistic prediction）。这意味着，我要尝试在初始条件中加入不同程度的噪音。当飓风在加勒比海形成时，我会加入一些噪音，因为那里本来就充满噪音，我不知道那里真实的测量数据到底是什么。然后，我会观察那些可能的飓风路径会发生什么变化。这样我就可以得出飓风在不同地区登陆的概率，这也是我进行风险评估的方式。而对于传统的气象模型来说，这就变得更加昂贵了，因为你必须运行所有的这些集合。现在，人工智能气象模型由于速度极快——快了数万倍——意味着我们现在可以运行非常庞大的集合，这对于我们能做的风险评估来说是一个非常巨大的进步。

<details>
<summary>Original English</summary>

**Speaker A**: instance there was hurricane lee and that's where the public could see what are these weather models doing for instance our forecast net was able to correctly predict that the hurricane making the landfall several days earlier compared to the standard uh weather forecasting models and so the idea that these models could be very good for extreme weather and do early prediction you know both for human lives for economic costs is a very big deal and so that's when the public kind of got a lot more i think buy-in and from weather scientists because of how well it was doing in these events and this is what i was talking about in an ensemble prediction both for extreme weather or if you're thinking about climate it's not just about looking at one trajectory right because you know unless you're somebody with a sharpie somehow saying okay the hurricane is gonna go no fun intended but you know what you really want is the probabilistic prediction meaning you know i'm gonna try different adding noise levels to my initial condition what the when the weather when the hurricane is forming in the caribbean i'm gonna add some noise because anyway it's noisy i don't know truly what the measurement there is and then i'm gonna look at what happens to the possible hurricane tracks and then i can come up with the probability of landfall in different regions and that's how i can do risk assessment and so this is where it gets even more expensive for traditional weather models because you have to run all of these ensembles and now ai weather models being so fast tens of thousands of times faster means we can now very large ensembles and this is a very big improvement in terms of what we can do for risk assessment

</details>

**Speaker B**: 你有没有回顾历史飓风地图，然后尝试进行集合预测，并校准你的预测频率，就像……是的。

<details>
<summary>Original English</summary>

**Speaker B**: have you gone through and done let's say looked over the historical hurricane maps and then tried to do ensemble predictions and calibrated how often your predictions are like a yeah

</details>

**Speaker A**: 是的，所以在 ForecastNet 3 的论文中，你知道，我们有诸如极端天气事件和集合预测的指标。事实上，我们已经训练了模型来进行优秀的集合预测。这就是为什么对于这类事件，校准是非常重要的。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so in forecast net three paper that are you know we have metrics of like extreme weather events and ensemble prediction and in fact we've trained the model to do good ensemble prediction and so this is where the calibration matters for for these kind of events

</details>

### ForecastNet 3 的关键进展与球面几何 (Key Developments in ForecastNet 3 and Spherical Geometry)

**Speaker B**: ForecastNet 第三个版本与第二个版本或最初的版本相比，关键的见解或进展是什么？

<details>
<summary>Original English</summary>

**Speaker B**: what was the sort of key insights or developments in forecast net three in versus two versus the first version

</details>

**Speaker A**: 是的，第一个版本使用的是类似傅里叶神经算子（Fourier neural operators）的技术，但我们没有纳入球面几何（spherical geometry），对吧？在接下来的这个版本中，我们说，我认为世界是一个球体这一点很重要，因为首先，否则它就会变形，所以你有点无法预测……

<details>
<summary>Original English</summary>

**Speaker A**: yeah so the first version was kind of the you know the using like the Fourier neural operators but we didn't incorporate the spherical geometry right in this next version we said i think you know it's important that the world is a sphere because first of all otherwise distorted so you kind of are not predicting uh it

</details>

**Speaker B**: 这是一个问题，但如果它不是球形的，你会怎么做？比如使用墨卡托投影（Mercator projection）或者类似的？是的，标准的……

<details>
<summary>Original English</summary>

**Speaker B**: in our question but if it wasn't spherical what did you do like a mercator projection or something yeah the standard like kind of the you

</details>

**Speaker A**: 你知道，所有其他的天气模型也是这么做的，对吧？所以它们只是使用了标准投影，然后预测天气。这对于短期预测还可以，但当我们的目标是让同一个模型也进行长期预测时，融入球面几何就增加了这种额外的稳定性，我们可以进行更长期的展开（rollouts）。然后在 ForecastNet 3 中，我们的理念是，这不仅仅是关于确定性预测，我们想要得到集合预测，对吧？所以我们必须基于“我们要获得正确的概率预测”这个目标来训练它们。

<details>
<summary>Original English</summary>

**Speaker A**: know like and all the other weather models do the same right so they just kind of have the standard projection and then uh it's predict the weather and which is okay for short term prediction but when we in our goal was to have the same model also do longer term and that's when incorporating spherical geometry added this additional stability we could do longer rollouts and then in forecast net three the idea was it's not just about deterministic prediction we want to get ensemble predictions right so we have to train them based on this objective that we get the probabilistic predictions correct as well

</details>

**Speaker B**: 你能预测多远的未来？你要进行多少次展开（rollouts）？

<details>
<summary>Original English</summary>

**Speaker B**: how long are you predicting out and how many rollouts are you doing

</details>

**Speaker A**: 是的，你知道，展开（rollout）就是你预测多长时间，对吧？所以每一步是 6 个小时，然后你想预测多长就预测多长，你知道，你只需要不断向外展开预测。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so the you know rollout is how long you predict right so each step is six hours and then you predict for how long you want you know you just have to roll out

</details>

**Speaker B**: 抱歉，你们的集合中有多少个实例（examples）？

<details>
<summary>Original English</summary>

**Speaker B**: sorry how many how many examples in the ensemble df

</details>

**Speaker A**: 这也是我们的选择。我们可以有不同级别的集合，所以我想大概是几十个（tens）之类的，这是我们目前展示的，但你也可以做大得多的集合。

<details>
<summary>Original English</summary>

**Speaker A**: so and again that's our choice we can have like ensembles of different levels so we i think it's like a few tens or something like is what we are currently you know shown but you can do much larger too

</details>

**Speaker B**: 预测那么远，这就足够了吗？我的直觉是，你想预测得越久，需要的实例就越多……

<details>
<summary>Original English</summary>

**Speaker B**: and that's adequate to get out how far my intuition is the longer you want to predict the more

</details>

**Speaker A**: 不一定。这实际上又回到了校准集合的问题，确保它们有正确的分布范围（spread），而不是……

<details>
<summary>Original English</summary>

**Speaker A**: so not necessarily it's really like about again calibrating the ensembles and ensuring that they have the right spread rather than

</details>

**Speaker B**: 你知道，好吧，所以也许你的集合中有几十个模型或实例，即使进行非常非常长期的展开，那也足够了。

<details>
<summary>Original English</summary>

**Speaker B**: you know okay so maybe so you have tens of these um models or examples in your ensemble and that even with a very very long roll out that's adequate

</details>

**Speaker A**: 再次说明，你知道，正如我所说，要做非常非常长期的展开预测，仍然有许多悬而未决的问题，对吧？因为你确实需要以某种方式引入物理约束，以确保……那是我们现在正在积极研究的。但是我们拥有的这些模型，能够进行最长的展开预测，相比于任何其他完全忽略球体假设和其他一系列因素的气象模型而言。

<details>
<summary>Original English</summary>

**Speaker A**: so again like you know there's as i said a lot of still outstanding questions to do very very long rollouts right because you do need to incorporate like the physical constraints in a way to ensure that that's something that we are actively researching now but these models that we have are able to do the longest rollouts compared to any of the other weather models that completely ignore spherical assumption and the range of other things

</details>

### 将物理定律融入集合预测 (Incorporating Physical Laws into Ensemble Predictions)

**Speaker B**: 所以当你提到为长期的气候预测引入物理定律时，我是说，那具体是什么样的？因为有许多局部的守恒定律（local conservation），如果你取一个集合平均值，这些定律可能就会被破坏，即便任何给定的单次快照（snapshot）是遵守这些定律的。

<details>
<summary>Original English</summary>

**Speaker B**: so when you say incorporate physical laws for climate over long times i mean what does that look like because there's a lot of the local conservation which may be just broken if you take an ensemble average even though any given snapshot is respects that

</details>

**Speaker A**: 不，我们的想法是确保你观察每个集合成员，并且它遵守物理规律。

<details>
<summary>Original English</summary>

**Speaker A**: no the idea is to make sure you look at each ensemble member and it respecting the physics

</details>

**Speaker B**: 好的，好的，你不是假设整个集合……你不是在推导一个类似于粗粒化（coarse grained）的概率等价物或者类似的东西，因为那样的话你会失去那种分辨率和拟合度。好的，这让我有点困惑，等等，所以它不是一个平均值……那你是如何组合这个集合的？

<details>
<summary>Original English</summary>

**Speaker B**: okay okay you're not assuming the ensemble how you're not deriving a like coarse grained like equivalent of a probability or something because then you would lose that you know resolution and the fit okay that's a little confusing to me wait so you're so it's not an average well how are you combining the ensemble

</details>

**Speaker A**: 你是在做平均，但你是分别预测每一个成员。

<details>
<summary>Original English</summary>

**Speaker A**: you are doing the average but you're predicting each one

</details>

**Speaker B**: 哦，你是分别预测每一个成员的，好的。所以每一个成员都独立地满足这些物理约束，但集合本身并不满足。是的……所以这就是你确保符合物理规律的方式。

<details>
<summary>Original English</summary>

**Speaker B**: oh you're predicting each one separately okay so each one is independently satisfies these constraints but the ensemble it does not yeah which and so that's how you ensure physical biology

</details>

**Speaker A**: 是的。所以当你在球面上进行运算时，你使用的是球谐函数（harmonics）或某种……是的，你有一个……是的。这实际上对于傅里叶（Fourier）来说非常自然。如果你做其他……是的。确切地说，这就是傅里叶拯救我们的地方。它可以很好地融合这些几何形状，所以我觉得它能非常忠实地反映地球真实的模样。是的。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so when you go on a sphere you operate in do use basically harmonics or some sort of yeah you have a yeah yeah which is actually very natural with for enough for is probably much harsher if you're doing yeah um other exactly so that's where the you know like the 40 years saves us can incorporate these geometries well and and so i think be very faithful to you know what the globe is yeah

</details>

**Speaker B**: 可以说这比墨卡托投影或其他什么投影要自然得多。

<details>
<summary>Original English</summary>

**Speaker B**: arguably it's much more natural than uh didn't like a marketer projection or whatever other

</details>

**Speaker A**: 是的，否则的话就像格陵兰岛变得非常巨大一样，那是另一回事了。但是，是的，我认为这就是，你知道，更广泛地融入更多几何形状和领域信息，在物理世界中变得更为重要的地方，对吧？所以这又是我在强调，我们需要融入更多的结构信息，因为一方面数据是有限的，另一方面我们要求的很多都是外推（extrapolation）——你知道，要超越训练数据去预测。你知道，我们只是训练它去预测未来 6 个小时，也许再做一点自回归（auto regressive）展开的多步微调，对吧？所以我们并没有训练它去做诸如气候一样的超长期预测，因为那太昂贵了。但我们奇迹般地希望它能运作良好，而如果你只是说“我只需在那里放一个标准的 Transformer 或其他什么东西”，它是无法做到的，那是行不通的。所以我们添加了更多的领域约束，比如球面几何，我们可能以某些方式加入了更多的物理规律，这就是它在算法上也变得更有趣的地方，你知道，这里有更复杂的设计。

<details>
<summary>Original English</summary>

**Speaker A**: yeah which is like green land becomes huge different story but uh but yeah but i think that this is where i think the aspect of you know more broadly incorporating more of geometry and information about the domain becomes a lot more important in for the physical world right so this is me again emphasizing that we need to incorporate more of the structures because one is the data is limited and the other is a lot of what we are asking is extrapolation you know to go beyond than what the strain on you know we're just training it to predict the next six hours and maybe do a little bit of multi-step fine tuning for auto regressive rollouts right so we are not training it to do very long like a climate because that's just too expensive but we hope magically it works well and it cannot if you just say i'm just gonna put a standard transformer or whatever else there and it won't work out so we added more of the domain constraints like spherical geometry we add in maybe more of the physics in certain ways and that's where it becomes more interesting algorithmically as well you know there's more involved design here

</details>

### 时间尺度与空间分辨率 (Time Scales and Spatial Resolution)

**Speaker B**: 那么你们训练的时间尺度是多长？

<details>
<summary>Original English</summary>

**Speaker B**: so the time scale that you train on how long is that

</details>

**Speaker A**: 预测接下来的 6 个小时。

<details>
<summary>Original English</summary>

**Speaker A**: to predict for the next six hours

</details>

**Speaker B**: 哦，所以只有 6 个小时？

<details>
<summary>Original English</summary>

**Speaker B**: oh so only six hours

</details>

**Speaker A**: 是的，就像我说的，再加一点多步微调。是的。

<details>
<summary>Original English</summary>

**Speaker A**: yeah and a little bit of multi-step fine tuning like i said yeah i said

</details>

**Speaker B**: 好的，明白了。所以这非常令人惊讶。是的，那非常令人惊讶，我本来以为会是几周或几个月。

<details>
<summary>Original English</summary>

**Speaker B**: okay understood so which is very surprising yeah that is very surprising i would have expected it was weeks or months

</details>

**Speaker A**: 是的，不，然后它基本上运作得很好，甚至就像现在，我们展示了在几个月的时间跨度内它都能做到这一点。

<details>
<summary>Original English</summary>

**Speaker A**: yeah no i've then it kind of just works well even for like now we are showing for several months that it's able to do that

</details>

**Speaker B**: 步数是在几百步左右或者……是的，而且你的傅里叶基，它是……它是基础谐波（base harmonic）的很多倍。我的意思是，那是在空间上的，对吧？所以我们说的展开（rollout）是随时间自回归的，没有人说是在时间上的……我可能有点误解了，因为这是在傅里叶域（Fourier domain）中。

<details>
<summary>Original English</summary>

**Speaker B**: the number of steps is on hundreds or yeah and that your your foyer basis your it's it's many times the the the sort of base harmonic i mean this is like that's in space right so we're talking rollout is auto regressive with time nobody like in in time i'm maybe i'm misunderstanding here because it's a in foyer domain

</details>

**Speaker A**: 不，不，在时间上它不是（傅里叶域）。这就是我所说的，它是自回归的（auto regressive）。哦。

<details>
<summary>Original English</summary>

**Speaker A**: no no in time it's not that's what i'm saying it's auto regressive oh oh

</details>

**Speaker B**: 我明白了，好的，所以是在空间上（使用傅里叶域），是的。是的，很有趣。是的，你们使用的角分辨率（angular resolution）是多少？

<details>
<summary>Original English</summary>

**Speaker B**: i understand okay so it's space it is yeah yeah interesting yeah what's the uh angular resolution

</details>

**Speaker A**: 至少在这个场景下是这样。在其他情况下，我们在时间上也同样在傅里叶域中表示，这同样是个悬念：我们能做到吗？但在这个例子中，是的，它是自回归的，明白了。

<details>
<summary>Original English</summary>

**Speaker A**: at least in in this scenario in other cases we also have in time is also represented in the foyer domain and that's a question as well can we do that but in this example yes auto regressive got it

</details>

**Speaker B**: 嗯，在这个……你知道的，在这个球面版本中，你们使用的角分辨率是多少？

<details>
<summary>Original English</summary>

**Speaker B**: um what's the angular resolution that you use for for this um in you know in the spherical version

</details>

**Speaker A**: 是的，所以所有可用的数据大概是……我想是四分之一度，就像 0.25 度。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so it's so all of the data that's available is like i think a quarter like 0.25 degrees

</details>

**Speaker B**: 所以在球面谐波阶数 L 方面，或者我的意思是，比如在球谐频率方面……以及……

<details>
<summary>Original English</summary>

**Speaker B**: so in terms of l maybe or i mean in terms of like a spherical harmonic frequency or and

</details>

**Speaker A**: 所以这就像……哦，你是说我们利用了多少个模式（modes）？对于那个分辨率，我们实际上只利用了……我想大部分都被省略了，只留下了少数几个，我忘了具体细节了，但是……

<details>
<summary>Original English</summary>

**Speaker A**: so this is like uh oh you mean like how many modes we utilize i think we so for that resolution and we essentially utilize i think most of only a few of them will live out i forget the details but

</details>

**Speaker B**: 我只是很好奇，你们在地球仪上解析到的实际角分辨率是多少？或者仅仅是物理分辨率？

<details>
<summary>Original English</summary>

**Speaker B**: i'm just curious like what is the actual angular resolution on the globe that you are resolving to or maybe just the the physical resolution

</details>

**Speaker A**: 我的意思是，这就是我们获得的数据，对吧？所以现在我们获得的数据类似于四分之一度，就像 0.25 度。完全正确。大概是 0.25 立体角（solid angle）。所以我想结果类似于……你知道，700 乘以几千这样的分辨率。但这已经是标准的、经过处理的数据了。

<details>
<summary>Original English</summary>

**Speaker A**: i mean and that's what that because that's the data we get right so right now the data we get is like a quarter like uh 0.25 degrees totally okay like a 0.25 solid angle so i think it's the yeah it's like i think kind of comes out to like uh you know 700 by few thousand like resolution so but this is already standard like kind of processed

</details>

**Speaker B**: 是的，是的。我只是想弄清楚，要表示这些数据你需要多大的基（basis）？

<details>
<summary>Original English</summary>

**Speaker B**: yeah yeah and just uh trying to understand like how large is the basis do you need to represent this

</details>

**Speaker A**: 我的意思是，这真的取决于分辨率。现在的思路是，你知道，我们的气象数据只是受限于这个分辨率，但如果你能够……你知道，你可以进行更高分辨率的合成气候模拟（synthetic climate simulations），对吧？这就是接下来如何将这些结合起来的问题。

<details>
<summary>Original English</summary>

**Speaker A**: i mean that's really depends on the resolution and the idea is you know right now or whether data is just limited by this resolution but if you could you know you could like kind of do synthetic climate simulations of even higher resolution right and that's kind of the next thing on how combine these together

</details>

**Speaker B**: 你觉得你能用超分辨率（super resolution）进行预测吗？基本上就是在低于提供数据的分辨率下进行预测？

<details>
<summary>Original English</summary>

**Speaker B**: do you think you can predict with super resolution be basically resolution lower than the data provided

</details>

**Speaker A**: 再次强调，是的，我们总是可以用神经算子（neural operators）来预测它们，但是你知道，你确实想要融入更多的物理约束来确保它们是有效的。

<details>
<summary>Original English</summary>

**Speaker A**: again like yes we can always predict them with the neural operators uh but you know you do want to incorporate more of the physical constraints to ensure that they are valid

</details>

### 聚变反应堆与等离子体控制 (Fusion Reactors and Plasma Control)

**Speaker B**: 好的，所以……我们能谈谈其他的一些……

<details>
<summary>Original English</summary>

**Speaker B**: okay so at um can we talk about some of the other

</details>

**Speaker A**: 是的，是的，我知道这有很多内容。所以这仅仅是在展示，就像我描述的，在左边，当世界被假定为一个矩形时，它非常快地就崩溃了（blows up）。而在右边，因为我们假设世界是一个球体，它持续展开，并且保持稳定，所以……

<details>
<summary>Original English</summary>

**Speaker A**: yes yes i know it's a lot uh so this is just showing like how you know the what i described that the on the left where the world is being assumed it's a rectangle it blows up very quickly and on the right because we assume the world was a sphere it kept rolling it out and it kept being stable so

</details>

**Speaker B**: 我还是能看到那里有一点奇点（singularity），好吧。它仍然像是……你知道的，所以……

<details>
<summary>Original English</summary>

**Speaker B**: i still see a little bit of a singularity there is all right and it's still like you know so

</details>

**Speaker A**: 思路是，是的，因为这是一个非常长的展开预测，而且我们没有任何物理护栏（guardrails of physics），我们并没有，你知道，把它投射到正确的物理规律上，对吧？这是完全的外推。但关键在于，球体假设在很大程度上稳定了它，与左图相比，这是一个好得多的结果。是的。

<details>
<summary>Original English</summary>

**Speaker A**: the idea is yes because it's a very long rollout and we have no guardrails of physics we are not you know kind of projecting it to the right physics right this is full extrapolation but the idea is the sphere assumption stabilize it to a much greater extent compared to the left it's a much better yeah

</details>

**Speaker B**: 但是如果你在南极的话，你仍然无法精确获得结果，因为两极才是最困难的部分，所以……

<details>
<summary>Original English</summary>

**Speaker B**: but if you're you're in the south pole you're still not going to get exactly since the poles are the hard parts so

</details>

**Speaker A**: 所以这是一个聚变反应堆（fusion reactor）的例子。这是一个托卡马克（tokamak）装置，我们能够对复杂的等离子体演化进行建模，而且执行速度比传统模拟方法快一百万倍。从某种意义上说，这就像是我们正在创建一个等离子体的数字孪生（digital twin），对吧？然后我们可以，你知道，做进一步的事情，比如现在作为下一步，我们正在研究类似于控制（control）的东西，但要包含完整有效的物理规律，理想情况下能够防止等离子体破裂（disruptions），并使核聚变具有可持续性。

<details>
<summary>Original English</summary>

**Speaker A**: so this is the example of the fusion reactor so this is a tokamak and we are able to model the complex plasma evolution and do this a million times faster than what we could do with traditional simulations and this was in a way we're creating a digital twin of the plasma right and then we can you know do further things like right now we are as a next step looking at like control but with the full valid physics like being able to prevent disruptions ideally and make fusion sustainable

</details>

**Speaker B**: 所以你们在这里模拟的是 MHD 方程，或者抱歉，是磁流体力学方程（magnetohydrodynamics equations）吗？是的。好的。然后，作为背景补充，在这种情况下，破裂（disruption）是指一种困扰等离子体物理学家的现象：在某个时刻，你所有的等离子体会聚集在一束微小的电子束中，然后发射出一股强烈的……你知道，直接射向你的安全壳容器，并且……

<details>
<summary>Original English</summary>

**Speaker B**: so are you simulating mhd equations here or sorry mignito hydro dyne n-mass equations yes okay yeah and then so for context disruption in this case is this phenomenon which plagues which plagues plasma physicists where at some point your entire plasma collects in a little tiny beam and then shoots a strong you know right to your containment vessel and

</details>

**Speaker A**: 是的，它会损坏反应堆。这是一个很大的瓶颈，因为在破裂发生之前你必须以某种方式将它关闭。

<details>
<summary>Original English</summary>

**Speaker A**: so and it can damage the reactor and that's the that's a big bottleneck because then you have to kind of shut it down before

</details>

<!-- chunk 6/7 -->

### 聚变反应堆与数字孪生

**Speaker A**: 这种情况发生了，而且，拥有一个可持续的未来也不再可能了，所以这里存在许多悬而未决的挑战。但核心理念是，你知道的，进行物理实验是非常昂贵的，你能在数字孪生（digital twin）中捕捉到的信息越多，同时确保物理上的有效性，你就能在数字领域进行越多的设计和其他考量。你知道，我们希望能取得进展，而这些就是朝着那个方向迈出的第一步。

<details>
<summary>Original English</summary>

**Speaker A**: that happens and then plus it's no longer possible to have a sustainable future so there's a lot of open challenges here but the idea is you know it's very expensive to go to physical experiments the more you can capture that in the digital twin but ensure physical validity the more you can even do design and other considerations in the digital realm you know we can hopefully make advances and these are the first steps towards that

</details>

**Speaker B**: 目标是，如果你遇到这种事件之一，你可以以某种方式调整……嗯……调整磁场，从而将其控制住并使其稳定下来，对吧。

<details>
<summary>Original English</summary>

**Speaker B**: the goal is that if you have one of these events that you can somehow adjust the the um the magnetic field so that it contains that and and stabilizes yes

</details>

**Speaker A**: 是的，这就是我们现在正在做的下一步，我们正在考虑将控制和模拟结合起来一起设计。

<details>
<summary>Original English</summary>

**Speaker A**: and that's the next step we are doing now we are looking at like designing both the control and the simulation together

</details>

**Speaker B**: 我只是很好奇，你是和这个特定的实验室合作吗？

<details>
<summary>Original English</summary>

**Speaker B**: are you working with this specific lab i'm just curious

</details>

**Speaker A**: 所以这个项目是和英国原子能管理局（UK Atomic Energy Agency）合作的。现在我们也在和美国这里的其他几个机构合作。所以我们在从聚变本身的许多不同途径中获取信息。所以这个是托卡马克（tokamak）装置，我们也在研究仿星器（stellarators），我们正在研究不同的设备。

<details>
<summary>Original English</summary>

**Speaker A**: so this one was with the UK atomic energy agency okay and now we're also working with a few others here in the us as well so we are you know kind of getting the information from many different approaches of fusion itself so this is the tokamak we're also working with stellarators we are working with different

</details>

**Speaker B**: 仿星器非常棘手，是的。

<details>
<summary>Original English</summary>

**Speaker B**: stellarities are are tricky yes

</details>

**Speaker A**: 是的，但理想的想法是，你知道，我们的目标是能够在数字孪生中设计它们。所以我们能否想出好的设计，使其可能变得更实用。所以，作为一名 AI 从业者，我认为这也是一件好事，它更加……你知道，不可知论（agnostic），并且不会预先挑选一个赢家，对吧。就像我喜欢研究不同的方法，你知道，看看 AI 是否能加速所有这些方法，然后我们可以……你知道，不至于过早地排斥某一种方法而选择另一种。这就是 AI 让我们能够去承担更多风险并探索不同方法的原因。相比之下，在物理世界中，如果试图建造其中任何一个，你基本上必须砍掉很多有风险的项目，然后说，“我只打算做这个，因为这就是我要做的，我不打算做那个，因为情况非常困难，所以它不太可能成功。”

<details>
<summary>Original English</summary>

**Speaker A**: yeah but the idea is ideally you know like our goal is to be able to design them in the digital twin so can we come up with good designs that would make it maybe more practical and so that's i think also good thing as an ai person and much more like you know agnostic and not picking a winner beforehand right like i like to work with different approaches you know and see whether ai can accelerate all of them and then we can kind of you know not prematurely rule out one approach over the other so that's what ai enables us to be more kind of taking risks and exploring different approaches as opposed to in the physical world trying to build any of these you kind of have to cut a lot of the risky ones and say i'm only going to do this because this is what i would do and i'm not going to do it because it's a very difficult situation and so it's not really likely to work

</details>

### 从理论到应用的研究转变

**Speaker B**: 我注意到在你的职业生涯中，你一开始花了很多时间在……你知道，机器学习非常理论化的基础和数学上。也许在，我不知道，大约六到八年前，你开始真的花很多时间在应用上，并扩展到各种各样的问题领域。是什么促使了你研究方向的这种转变？我的意思是，你也还在研究非常难的数学问题，比如，举例来说，Torch 方面的精简工作。但是，嗯，应用方面确实已经大幅增长了，我想知道是什么促使了这一点？以及，嗯，从那时起你学到了哪些经验教训？

<details>
<summary>Original English</summary>

**Speaker B**: i noticed over your career you started out spending a lot of time on you know really theoretical foundations and mathematics of machine learning and maybe i don't know something like six eight years ago you started working really working a lot on applications and branching out in a diverse set of problems what sort of prompted that shift in your your looking at i mean so you're still working on very hard math problems as well like for example the torch lean work but um the the applications have really grown and i'm wondering what what prompted that and like um what were some of the lessons you've learned since then

</details>

**Speaker A**: 当然，我的意思是，对我来说，这就像是，你知道，我觉得我是随着 AI 一起成长的，对吧。所以当 AI 还在……你知道，在那个神经网络因为没有足够的数据以及其他各种原因而无法工作的阶段时，你知道，那时你就必须去建立理论基础，并试图希望那能把你引向一个……你知道，能让算法跑起来的地方，对吧。而且……你知道，在那个时候，张量方法（tensor methods）就是基于这样一种想法：在深度学习出现之前，我们仍然需要结构，我们有像用于主题建模的隐含狄利克雷分布（Latent Dirichlet Allocation）这样的概率模型，而求解它们是很困难的。但是现在，张量方法为我们提供了一种非常实用的方式，它可以并行化，并且可以大规模完成，但仍然有很好的理论基础。所以那正是，你知道的，我们起步的地方。然后，随着深度学习开始腾飞，我们可以看到它在实践中效果很好；是的，也许有一些理论上的理解，但因为它的复杂性，理论理解并不是很多。对我而言，理论不应该成为一种约束，对吧，它应该是一个补充。所以这就是很多探索的意义所在，去让它在实践中良好运行。后来到了亚马逊 AWS 服务，然后是英伟达（NVIDIA），所以真的是在像在大规模下让系统跑起来，并且真的可以说是亲自动手去弄脏双手，对吧，这就是很多发展发生的地方。现在，我看到它完成了一个完整的循环。因为许多纯数据驱动的方法，在某种程度上正看到其饱和点，对吧。我们想问，好吧，要么让它们在硬件上更高效，对吧——现在有很大的空间去问，我们现在能否，你知道，让它们更加节能或更加硬件高效。所以这是一个方面。但是另一个方面是像现在这样的领域，在物理世界中我们没有足够的数据，我们要求进行高难度的外推（extrapolation）。你知道，我们想要思考去进行发现。从本质上讲，发现就是关于外推的。所以，关于一个新的发现，我们永远不会有数据，对吧，这是我的定义。所以在那里，我们需要再次回到用原则性的方式去思考。并且，无论是架构设计、算法设计，还是正确的损失函数，我们都需要更加深思熟虑。所以我看到这正在形成一个闭环，因为我们要把所有在深度学习中有效的东西都拿过来，但要让它们更具原则性。

<details>
<summary>Original English</summary>

**Speaker A**: sure i mean to me it's like you know i feel like i've grown along with ai right so when ai was you know in this where neural nets were not working because there wasn't enough data and all kinds of other reasons you know then you kind of have to build the theoretical foundations and try to hope that that leads you to a place where you know you get algorithms to work right and and and and you know back then ektensor methods was with that idea that uh you know pre-deep learning we still wanted structure we have probabilistic models like late and Dirichlet allocation for topic modeling and solving those were hard but now tensor methods gave us a way to be very practical it's parallel and can be done at large scale but still has nice theoretical basis so that was where you know we're starting off and then as deep learning started taking off and we could see that it works well in practice and yes there is a little bit of maybe theoretical understanding but not a whole lot because of the way how complex it is to me theory should not be a constraint right it should be an and so that's where a lot of like the exploration was to make this work well in practice and over into amazon web services then nvidia so really like making things work at scale and really kind of getting hands dirty right was kind of like where a lot of the development is and now i see a full circle because a lot of day purely data driven approaches in a way seeing saturation right we want to ask okay either make them more hardware efficient right there's a lot of now room to kind of say can we now you know make them much more energy efficient or hardware efficient so that's one aspect but the other is areas like this where in the physical world we don't have enough data we are asking for hard extrapolation you know we want to think of doing discovery by nature it's about extrapolation so we will never have data about a new discovery right that's my definition and so there we need to again go back to thinking in principled ways and whether it's architecture design algorithm design the right loss functions so we need to be much more mindful so i see that coming a full circle because all of the things that work with deep learning let's take them but make them a bit more principled

</details>

### AI 在物理学和基础模型中的广阔应用

**Speaker B**: 还有其他几个似乎非常自然的应用，我想知道你是否从事过这些领域，或者我是否只是错过了一些论文，如果错过了，我很抱歉。嗯，一些例子比如电磁电路的设计，嗯，我认为这是一个很大的领域，或者可能现在还不是很大，但我认为在不久的将来会出现的。比如材料设计，嗯，比如散热和散热器的设计，或者……或者任何种类的，比如流体流动。当我在脑海里过这些微分方程时，我知道电磁学，我知道扩散方程……嗯，你知道，嗯嗯。

<details>
<summary>Original English</summary>

**Speaker B**: there are several other applications which seem very natural i'm wondering if you've worked on these or did i just miss some papers if i did i'm sorry um so some examples are design of like electromagnetic circuits um i think is a big one uh or maybe not a big one but i think we'll be coming up in the near future design of let's say materials um design of let's say dissipation and heat sinks or um or any sort of like fluid flow as i'm going through what differential equations i know electromagnetism i know diffusion equations um you know it mhm mhm yeah

</details>

**Speaker A**: 我想知道其他一些领域是……

<details>
<summary>Original English</summary>

**Speaker A**: i'm wondering some of the other domains that are

</details>

**Speaker B**: 是的，我的意思是，对我来说，这其中有着无尽的可能性，对吧。所以那里，你知道的，就像你可以让它处理任何数据一样，我们有其他几个例子。所以这就像，你知道，能够提出问题：我们能否将二氧化碳封存在地下，并对二氧化碳如何扩散进行建模；或者你知道，在这些储层中的压力积累是多少；以及，嗯，你知道，我们能否对它们在几十年内的迁移方式进行建模。所以在这方面，我们能够比传统的模拟做得快得多。我的意思是，另一个方面是能够处理各种几何形状，比如，你知道，能够对汽车、飞机等进行空气动力学建模。所以，这又是一个关于潜在空间（latent space）的很好例子，因为你可以将汽车或任何其他形状转换成一个甜甜圈（donut），然后在甜甜圈上进行建模，然后再将甜甜圈转换回汽车。

<details>
<summary>Original English</summary>

**Speaker B**: yeah i mean to me there is just endless possibility right so there you know as like you can just have this work on any data and we have several other examples so this was like you know being able to ask can we sequester carbon dioxide underground and model uh how carbon dioxide uh expands or you know what is the pressure build up in these reservoirs and uh you know can we kind of model how they migrate over several decades and so this one we were able to do much faster than what traditional simulations could do i mean the other aspect is being able to do all kinds of geometric shapes like you know being able to model aerodynamics in cars planes and so on and so again this is a nice example of a latent space because you can transform a car or any other shape to a donut and then model on the donut and then transform the donut back to the car

</details>

**Speaker A**: 你没有把它变成一个咖啡杯，这是那个经典的笑话吗？你在捐赠任何咖啡……

<details>
<summary>Original English</summary>

**Speaker A**: you didn't turn it into a coffee cup is that the classic joke you're donating any coffee

</details>

**Speaker B**: 东西……实际上，利用潜在空间来处理各种不同的几何形状，并能够捕获潜在空间中的物理原理，这意味着我们现在可以拥有一个能够跨越许多不同几何形状进行泛化（generalizes）的模型。

<details>
<summary>Original English</summary>

**Speaker B**: things actually so the idea of like a latent space to handle all kinds of different geometries and be able to capture the physics there in the latent space well means we can now have a model that generalizes across a lot of different geometries

</details>

**Speaker A**: 我的理解是否正确，或许这里更大的愿景是，呃，你可以训练一个基础模型（foundation model），在这个意义上，就是能够用同一个模型来模拟许多不同的物理现象。因此你可以进行微调（fine tune），或者可能会有一种提示（prompt）提供给它，让它理解特定的几何结构；但是，你知道，就像是在所有这些不同的物理问题上你进行了训练，然后，当你面对特定的某个问题时，你能够非常有效地对其进行建模。

<details>
<summary>Original English</summary>

**Speaker A**: am i understanding that the maybe the larger vision here is that uh you can train a foundation model in the sense of being able to model many different physical phenomena with the same model and so you may fine tune or there may be some kind of prompt that you give it to have it understand the particular geometry but that you you know sort of on all these different physical problems you train and then and then you have your particular one and you're able to model that very effectively

</details>

**Speaker B**: 是的，我的意思是，这真的是未来，对吧。因为我们有用于语言的基础模型，也许还有视觉的基础模型，但还没有用于物理学的基础模型。所以，你知道，我们的想法是，不像现在这样，我们看到的是狭义的替代模型，我们在试图越来越大地拓宽它们的范围；但理想情况下，我们应该有更宽泛的模型，可以处理一系列现象，同时也能处理多物理场（multi-physics）。所以不仅仅是只有一个单一的物理场，而是耦合的物理场（coupled physics）。真实世界里所有的物理场都是以耦合的方式汇聚在一起的。所以我们能把所有这些结合起来吗？所以这是一个方面，就像，你知道的，拥有可以进行设计、可以进行模拟的基础模型。但另一个非常有趣的方面是逆问题（inverse problem），对吧。所以我现在能否不只是模拟，而是去问：什么是最好的设计？然后这类的模型能够，就像做模拟一样，但你甚至可以隐式地做这件事，得出最好的设计。而在更早的时代，那是人类试图想出一个设计，然后你去尝试模拟，或者去风洞进行任何物理测试，然后验证它。但现在你让 AI 想出优化过的设计，并且你有物理学的护栏，所以你有在物理上准确的模型，你有信心它们能良好运作。所以你在同一个模型中，差不多也能够做到这一点。

<details>
<summary>Original English</summary>

**Speaker B**: yeah i mean that's really the future right because we have foundation models for language maybe vision but not for physics so you know the idea is instead of like right now what we've seen are narrow surrogates and we're trying to broaden their scope more and more but ideally we have much broader models that can work on a range of phenomena but also multi-physics so not just have like one single physics but coupled physics the real world has all of the physics kind of coming together in coupled ways so can we bring all that together so that's one aspect like you know have foundation models that can do design that can do simulation but the other aspect that's really interesting is the inverse problem right so can i now not just simulate but ask what is the best design and then these kinds of like models can like do simulation but you can even do that implicitly and come up with the best design rather than in the earlier era it was humans trying to come up with design then you go and try to simulate or go to the wind tunnel whatever physical testing and validate that but now you have ai come up with optimized designs but you have the guardrails of physics so you have models that are accurate in physics you have the confidence they work well so you're kind of able to do that as well in the same model

</details>

**Speaker A**: 有没有原因……你有没有看到任何证据表明，你所讨论的这种多物理场能够迁移，或者，或者你也许能够泛化到那些某种未见过的物理现象上？

<details>
<summary>Original English</summary>

**Speaker A**: is there reason have you seen any evidence that you talked about these like sort of multi-physics being able to transfer or that that you may be able to generalize to sort of unseen physics

</details>

**Speaker B**: 那么，我的意思是，你知道，就像物理学本质上如果它是完全未见过的，那是无法迁移的，对吧。我的意思是，当然，有多少人会说我们要超越标准模型，这是绝对没有数据的，那是不可能的。但如果你问的是，比如说，你知道的，有这样的情况，比如我……你知道，给它展示过仅仅是热量如何传播的例子，还有其他材料如何拉伸的例子，而现在产生了耦合，比如因为受热，所以也产生了拉伸，或者是这种联合现象。你现在就可以期望用少得多的样本进行微调，因为某种程度上它单独了解这种现象，然后再把它们结合在一起。也许它不能从零开始做这件事，因为那要求太高了，它是高度非线性和耦合的；但它可以只用少量的例子来做到。我们已经看在我们的很多论文中看到了这方面的证据，你基本上能够构建一个课程（curriculum）。这正是我们在许多这些例子中一次又一次看到的，那就是，你知道，对于现实世界，我们可以某种程度上控制大量的课程，然后说，你知道，让我们把它们构建成一个个模块然后把它们拼凑起来，这就是它现在允许我们系统地进行的工作。在这里，我想在设计方面，我不知道我们是否想非常快速地展示一下。所以这个就像，你知道的，正在考虑如何为逆向光刻（inverse lithography）设计掩模，这意味着现在这里有一个逆向设计问题，我们也能够为设计量子点中的门（gates）做同样的事情。这就是非线性光子学之类的。所有这些中共同的一点是，你知道存在一个正向模型在模拟物理过程；但现在我们想要的是逆向设计，就像那个我们可以优化出最好设计的问题。而人类在这方面通常并不擅长，对吧，我们不擅长观察高度非线性的现象，然后说，“哦，也许这所有门组合在一起不知怎么就能在量子门中帮助把电子聚集起来。”所以我们的合作者过去常常手动艰难地做这件事，而有了 AI，我们现在能够得出非常高效的设计；而且那些设计我们也知道确实可行，因为我们已经把模拟作为循环的一部分了，它表明它们运作良好。所以我认为这些例子让我们看到，这不仅仅是关于模拟，这是关于真正新颖的设计和新颖的发现，它们能使我们在创新本身的进程上更进一步。

<details>
<summary>Original English</summary>

**Speaker B**: so i mean you know like the physics by nature if it's completely unseen it's not possible to transfer right i mean sure how many of you are saying that we're going beyond the standard model there's absolutely no data that's not possible but if you're asking about like you know for instance like you know there is the like say i've like you know shown it examples of like just how the heat propagates and the other examples of how the material like stretches and now there's coupling like because of heat there's also stretching or kind of the joint phenomena you could like now hope to fine tune with much fewer samples because it kind of individually knows this phenomena then combining them together maybe it can't do it from scratch because that's still too much to ask it's highly non-linear and coupled but it can do it with fewer examples and we've seen evidence of that in a lot of our papers that you're able to kind of essentially build up a curriculum and that's what we see again and again in many of these examples that you know the real world we can kind of control a lot of curriculum and say you know let's kind of build in like modules and put them together and that's what it now allows us to do in a systematic way here i guess the design aspect i don't know if we wanted to show very quickly so this one was like you know looking at like designing the mask for inverse lithography meaning now there's an inverse design problem and we are also able to do that for designing gates and quantum dots this is like non-linear photonics and all of this what is common is the idea that you know there's a forward model that is simulating the physics but now what we want is the inverse design like the problem that of we can optimize the best design and humans are usually not good at this right we are not good at like looking at highly non-linear phenomena and say oh somehow maybe this combination of all these gates coming together helps pull the electrons together in a quantum gate and so our collaborators were struggling to do that manually and with ai we are now able to come up with very efficient designs but also those we know actually work because we have already the simulation as part of the loop saying that they work well so i think these are examples where we see that it's not just about simulation it's about really novel designs and novel discoveries that enable us to move the needle of innovation itself

</details>

**Speaker A**: 每一个这样的例子都需要大量的领域知识，如果有人是一个领域专家，他们该如何吸收你的基础研究成果，并快速开始将神经算子（neural operators）以及你开发的其他框架应用到他们的问题上？是啊……

<details>
<summary>Original English</summary>

**Speaker A**: each one of these examples takes a lot of domain knowledge how could somebody take your basic research if a domain expert and quickly get started applying neural operators and the other frameworks that you've developed to their problem yeah

</details>

**Speaker B**: 你知道的，神经算子是一个开源库，它已经被广泛采用，它是 PyTorch 生态系统的一部分。你知道的，它不仅被大量研究人员使用，而且也被许多公司使用。我们在那里有很多文档，所以我鼓励人们去那里看看。我们有，你知道的，许多不同的架构、示例、配方。所以我认为那是一个开始的好地方。

<details>
<summary>Original English</summary>

**Speaker B**: you know neural operators are an open source library it's extensively already adopted it's part of the pytorch ecosystem it's you know used by a number of not only researchers but also in companies we have a lot of documentation there so i encourage people to go there we have like you know many different architectures examples recipes so i think that's a great place to get started

</details>

<!-- chunk 7/7 -->

### 加入联合国科学咨询委员会与对人工智能的展望

**Host**: 我知道我们的时间快到了，但你最近加入了联合国科学咨询委员会（UN Scientific Advisory Board）。也许你可以简单分享一下这背后的故事，以及你希望在那里实现什么目标？

<details>
<summary>Original English</summary>

**Host**: you recently joined the un scientific advisory board i know we're running out of time but maybe just can you quickly give a bit of the story behind this and what you hope to accomplish

</details>

**Anima**: 是的，我非常荣幸能成为联合国科学咨询委员会的一员。在当今这个充满地缘政治挑战的复杂时期，虽然我不是这方面的专家，但当涉及到尤其是与人工智能相关的议题时，让科学家参与到讨论中，我认为是非常重要的。我希望我能秉持客观公正的视角，尝试为任何相关方面提供科学依据。我们想要思考人工智能在全球范围内产生的影响，比如，我们如何确保人工智能带来的红利能够惠及每一个人？我们如何实现人工智能访问权限的民主化？我们又该如何确保那些意料之外的后果和有害影响能够得到有效控制？我认为这些只是初步的考量。当然，另一方面，当谈到气象模型时，我已经感到非常兴奋了。比如，目前正有一种推动力，促使我们探索如何能拥有更好的天气和气候模型，进而影响我们的粮食问题，比如利用更精准的天气预测来改善农业生产。所以在所有这些领域，联合国也在世界各地拥有众多专门的机构和实地工作人员。因此，我非常期待能为此做出贡献，并成为这一进程的一部分。

<details>
<summary>Original English</summary>

**Anima**: yeah no i'm really honored to be part of that advisory board for the un and in these tricky times with a lot of geopolitics there you know which again i'm not the expert on that but when it comes to you know aspects especially related to ai having scientists in the room is something that you know i think is very important i hope i could have an unbiased view and try to provide scientific evidence for any aspect right we want to think about how ai impacts globally like you know how do we ensure the benefits of ai reach everybody how do we democratize access to ai how do we ensure the unintended consequences and harmful impacts can be controlled i think these are just the beginning aspects of course the other side when it comes to weather models i'm already excited like you know there are there is a push to seeing how we can have better weather climate modeling so then our food you know like using weather for better agriculture so all these aspects are also where un has a lot of dedicated agencies and people on the ground across the world so i'm looking forward to contributing and being part of this

</details>

**Host**: 你知道，回顾你的职业生涯，以及听你讲述你所从事的工作，看起来你非常像是一个喜欢解决具体问题的人。你不喜欢对事物进行空洞的哲学思考。这也许让你比人工智能领域的很多人看起来更加乐观。你对世界抱有一种充满希望的看法，我认为这并不总是常见的。所以我想，相比于其他人，你能够通过哪些独特的方式将这种观点带入委员会呢？

<details>
<summary>Original English</summary>

**Host**: you know looking you know looking at your career and how you you know talking what you work on it seems like you very much are a person who likes to solve concrete problems you don't like to philosophize about things which then you're also seeing i think maybe more optimistic than a lot of people in the ai space um you have a very hopeful view of the world um i think not that's not always true um yeah so i guess what are the ways that you can uniquely bring that viewpoint to the board versus maybe some you know

</details>

**Anima**: 谢谢。对我来说，正如我所说，我努力保持客观公正。作为一名科学家，站在科学家的角度，我认为人工智能有很多有益的方面，而当我们仅仅盯着它可能产生的有害影响时，这些益处有时往往被忽略了。尤其是关于人工智能在科学领域的应用（AI for science），这一点尤为突出。因为许多监管框架常常将人工智能直接等同于语言模型。是的，语言模型确实可以操纵人们，可以产生各种各样我们应该了解并加以控制的有害影响。但是，用于科学研究的人工智能是截然不同的。所以我认为，这种“一刀切”的思维方式正是许多问题产生的根源。我们需要认识到，人工智能能够通过新发现改变世界，我们应该让世界各地的人们不仅能从中受益，而且还能有能力进行研究，让他们能够接触和使用人工智能，并以各种有趣的方式对其进行应用。

<details>
<summary>Original English</summary>

**Anima**: yeah thank you i you know to me i think as i said i tried to be unbiased and as a scientist and as a scientist i think that there's a lot of beneficial aspects of ai that are sometimes missed when we think of only the harmful impacts right and and especially that is with respect to ai for science because a lot of regulatory frameworks equate ai with language models and yes language models can you know have manipulate people can have all these kinds of harmful impacts that we should know about controlling but ai for science is different so i think this one size fits all is where a lot of problems come up so we have to be mindful that there is you know ai that can change the world with new discoveries and we should enable people around the world to not only benefit from them but also be able to do research you know have access to ai that they can go in a and use them in interesting ways

</details>

**Host**: 我们试图问每一位嘉宾的一个问题是：如果你可以挑选你所在领域中的一个瓶颈，并且能够施展魔法将其消除，你会选择什么？为什么？

<details>
<summary>Original English</summary>

**Host**: one question that we have been trying to ask every guest is if you could pick a bottleneck in your domain that you could magically remove what would that be and why

</details>

**Anima**: 更多的计算资源。你知道这可能是一个显而易见的、或者有点偷懒的答案。因为毫无疑问，相比起几年前，我们现在拥有的计算能力已经实现了巨大的增长，这要归功于英伟达（NVIDIA），也要归功于其他公司。对此我别无二话。但我之所以这么说，是因为对于研究而言，促成越来越多计算资源的使用是非常重要的。我知道有些国家实验室正在建造更多超级计算机，希望我们能拥有更多的计算资源。但我认为，如果没有算力，我们就无法进行实验，更无法进行创新。我认为这是我极力推动的一个方面，我怎么强调它的关键性都不为过。

<details>
<summary>Original English</summary>

**Anima**: more compute you know that's i know that's an easy one maybe a lazy one right because you know and you know of course our compute that we have is growing so much more than even a few years ago thanks to nvidia thanks to others again thanks so no no comments on that but what i mean by that is also like for research enabling more and more compute you know it's very important i know there are national labs building more supercomputers you know hoping that we can have more compute for but i think you know without that we cannot experiment we cannot innovate i think this is a part that i push a lot and you know i think i cannot emphasize that it's so critical

</details>

**Host**: 如果你有一个行动呼吁，或者有什么你希望人们去采取行动、去思考或者去学习的事情，那会是什么？

<details>
<summary>Original English</summary>

**Host**: if you had a call to action or something that you would like people to do or think about or learn about what would that be

</details>

**Anima**: 是的。所以你可以去尝试使用神经算子（neural operator）相关的代码库，这样你就可以亲自动手探索不同的架构和配方，研究各种应用案例。但同时也要思考，比如把“用于科学的人工智能（AI for science）”看作不仅仅是语言模型和智能体。是的，那固然是一个方面，但归根结底，它们在某种程度上仍然只是外部的包装。直到我们拥有了能真正理解物理世界的人工智能——不仅仅是将其视为符号，而是能够基于此进行模拟、设计和控制——在那之前，我们依然缺失了很大的一块拼图。所以我认为，人们真的应该去思考的另一个方面，就是以这种方式将人工智能应用于物理世界。

<details>
<summary>Original English</summary>

**Anima**: yeah so you know you can go to neural operator libraries so you kind of hands-on play with different architectures recipes you know look at use cases but also think about like you know ai for science as not just language models and agents yes that's one aspect of it but ultimately you know those are still like external rappers in a way right until we have ai that fully understands the physical world not just as symbols but as one that can simulate and design and control based on that you know there's a big piece missing so that's the other aspect that i think the people should really think about ai for the physical world in this way

</details>

**Host**: Anima，这次对话真的太吸引人了。我也很兴奋能亲自去看看神经算子，我的脑海里已经产生了一些想法。我非常感谢你抽出时间坐下来和我们交流。

<details>
<summary>Original English</summary>

**Host**: Anima this has been so fascinating um i i'm excited to check out neural operators myself i have some ideas in my head already i really appreciate you taking the time to sit down with

</details>

**Anima**: 谢谢你 Arjes，谢谢你 Brandon。我真的很享受这次对话，我们确实深入探讨了很多问题，所以我很感谢你们的安排。

<details>
<summary>Original English</summary>

**Anima**: thank you Arjes thank you Brandon i really enjoyed it it was really dug deep into a number of things so i appreciate you doing that

</details>

**Host**: 谢谢，谢谢。

<details>
<summary>Original English</summary>

**Host**: thank you thank you

</details>