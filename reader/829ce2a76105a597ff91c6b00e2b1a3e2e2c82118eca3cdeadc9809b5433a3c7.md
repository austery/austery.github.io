---
author: Dwarkesh Patel
date: '2024-03-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UeI29-AdhQI
speaker: Dwarkesh Patel
tags:
  - ai-research-acceleration
  - compute-bottleneck
  - research-cycle
  - prioritization
title: AI 加速 AI 研究：计算瓶颈、研究周期与迭代效率
summary: 本次讨论深入探讨了AI如何加速AI研究进程，重点关注算力作为瓶颈的作用，以及增加计算资源的影响。内容详细阐述了包含想法构思、实验验证和结果解读的研究迭代周期，并强调了不完美信息下的严格优先级排序的重要性。发言者区分了算法进展与AI生成内容，并指出研究员需要快速适应和迭代，这与进化优化过程有相似之处。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models:
  - GPT-4
media_books: []
status: evergreen
---
### 智能爆炸与AI研究员的崛起

**Unknown Speaker**: 在智能爆炸的模型中，会发生的是你取代了AI研究员，然后有一大批自动化的AI研究员，它们能加速进展，制造更多的AI研究员，取得更进一步的进展。我们应该直接问AI研究员，他们是否认为这是可行的。

<details>
<summary>Original English</summary>

**Unknown Speaker**: In the model of the intelligence explosion, what happens is you replace the AI researchers, and then there are a bunch of automated AI researchers who can speed up progress, make more AI researchers, make further progress. We should just ask the AI researchers about whether they think this is plausible.

</details>

**Unknown Speaker**: 那么，我能问你一个问题吗？比如，如果我有一千个AI研究员（或者AI研究单位），你认为这会引发智能爆炸吗？

<details>
<summary>Original English</summary>

**Unknown Speaker**: So, let me just ask you: like, if I have a thousand AI researchers (or AI research units), do you think that you get an intelligence explosion?

</details>

### 算力与判断力的瓶颈

**Unknown Speaker**: 我认为目前我们受到的限制，更多是来自于运行和获取信号的算力，以及在不完美的信息上做出正确判断的‘判断力’（taste），而不是制造这些东西本身的工程工作。所以，算力和判断力，这倒是挺有意思的。

<details>
<summary>Original English</summary>

**Unknown Speaker**: I think we are less, at the moment, bound by the sheer engineering work of making these things, than we are by compute to run and get signal, and, uh, and taste, in terms of what the actual right thing to do is. And that, like, making those difficult inferences on imperfect information. So, compute and taste—that's interesting to think about.

</details>

### 计算弹性的衡量

**Unknown Speaker**: 因为至少算力方面，它并不是受限于更多的智能（以至于无法进一步提升），它只是受限于‘7万亿参数’（Stam 7 trillion）或者别的什么（算力规模）的瓶颈，对吧？所以，如果我给你10倍的H100（GPU）来运行你的实验，你作为一个研究员会提高多少效率？请说，你作为一个研究员会提高多少效率？嗯，我想‘Gemini’项目可能会因为10倍的算力而快上大约五倍，或者诸如此类。所以这就是 pretty good elasticity（不错的弹性）？像0.5倍？等等，这太疯狂了。是的，我认为更多的算力会直接转化为进展。

<details>
<summary>Original English</summary>

**Unknown Speaker**: Because at least the compute part is not a bottleneck on more intelligence, it just bottlenecks on, say, 7 trillion parameters or whatever, right? So if I gave you 10x the H100s to run your experiments, how much more effective a researcher are you? Please, how much more effective a researcher are you? Uh, I think the Gemini program would probably be like, maybe five times faster with 10 times more compute or something like that. So that's pretty good elasticity? Like 0.5? Wait, that's insane. Yeah, I think like more compute would just like directly convert into progress.

</details>

### 算力分配的战略决策

**Unknown Speaker**: 所以你有一部分，嗯，一部分固定的算力，其中一部分用于推理（inference），一部分用于运行完整模型的实验。是的，没错。考虑到瓶颈是研究，而研究又受制于算力，那么用于实验的比例不应该更高吗？

<details>
<summary>Original English</summary>

**Unknown Speaker**: So you have some, um, some fixed size of compute, and some of it goes to inference, some of it goes to running the experiments for the full model. Yeah, that's right. Shouldn't then the fraction that goes to experiments be higher, given that you would just be like, like, the bottleneck is research, and research is bottlenecked by compute?

</details>

### 预训练团队的算力分配考量

**Unknown Speaker**: 每一个预训练团队都必须做出的战略决策之一是：到底分配多少算力到你的不同训练运行中？嗯，比如分配到你的研究项目，还是用于扩展你最终找到的那个最佳模型。你之所以还需要持续训练大模型，原因之一是你能在那里获得其他方式得不到的信息。所以，规模（scale）带来了所有这些涌现属性（emergent properties），你想要更好地理解它们。而如果你总是做研究，你不确定什么东西会‘偏离曲线’（fall off the curve），对吧？嗯，如果你一直在这个模式下做研究，并且不断提高计算效率，你可能会偏离最终能够扩展的道路。所以你需要不断地投入进行大型运行（big runs），去探索你认为会奏效的前沿领域。

<details>
<summary>Original English</summary>

**Unknown Speaker**: One of the strategic decisions that every pre-training team has to make is like, exactly what amount of compute do you allocate to your different training runs? Uh, like, to your research program versus like scaling the last best, I like, you know, thing that you landed on. One of the reasons why you need to still keep training big models is that you get information there that you don't get otherwise. Um, so scale has all these emergent properties, uh, which you want to understand better. And if you, like, are always doing research, you're not sure what's going to like fall off the curve, right? Yeah. Um, if you like, keep doing research in this regime, yeah, uh, and like, keep on getting more and more computer efficient, you may never, you, you may have actually like gone off the path that actually eventually scales. So you need to constantly be investing in doing big runs too, at the frontier of what you sort of expect to work.

</details>

### AI加速研究的世界

**Unknown Speaker**: 好的，那么请告诉我，在一个AI显著加速了AI研究的世界里，那是什么样的景象？因为从你刚才的描述来看，听起来并不像是AI们会独立地从零开始写代码，从而带来更快的产出。听起来更像是它们在某种程度上在增强顶尖研究员的能力。比如，是的，请具体告诉我：它们是在做实验吗？它们是在构思想法吗？它们只是在评估实验的输出结果吗？到底发生了什么？

<details>
<summary>Original English</summary>

**Unknown Speaker**: Okay, so then tell me, what does it look like to be in the world where AI has significantly sped up AI research? Because from this, it doesn't really sound like the AIs are going off and writing the code from scratch and that's leading to faster output. It sounds like they're really augmenting the top researchers in some way. Like, yeah, tell me concretely: are they doing the experiments? Are they coming up with the ideas? Are they just like evaluating the outputs of the experiments? What's happening?

</details>

### AI研究的两个主要加速方向

**Unknown Speaker**: 所以，我认为这里有两个‘门槛’（walls）需要考虑。一个是AI有意义地加速了我们进行算法进展的能力，对吧？另一个是AI本身的输出成为了实现模型能力进展的关键要素。而我在这里具体指的就是合成数据（synthetic data）。嗯，在第一个‘AI加速算法进展’的世界里，我认为一个必要的组成部分就是更多的算力。

<details>
<summary>Original English</summary>

**Unknown Speaker**: So I think there are like two walls you need to consider here. One is where AI has meaningfully sped up our ability to make algorithmic progress, right? And one is where the output of the AI itself is the thing that's like the crucial ingredient towards, uh, like model capability progress. And like, specifically what I mean there is synthetic data, right? Um, and in the first world where it's meaningfully speeding up algorithmic progress, I think a necessary component of that is more compute.

</details>

### AI作为高效副驾驶

**Unknown Speaker**: 而且，你可能会达到这个‘弹性’点。比如，AI在某些时候可能比你自己、比其他人更容易被加速和理解。嗯，所以AI能够有意义地加速你的工作，因为它们就像一个很棒的‘副驾驶’（co-pilot），基本上能帮助你写代码的速度提高数倍。嗯，这听起来确实相当合理。嗯，拥有超长上下文、超级智能的模型，它能立即被‘接入’，你可以让它去完成子任务和子目标。

<details>
<summary>Original English</summary>

**Unknown Speaker**: And, and you probably like reach this elasticity point. Like, AI maybe at some point, are easier to speed up and get on context than yourself, than other people. Um, and so AI meaningfully speeds up your work because they're like a fantastic co-pilot, basically, that helps you code like multiple times faster. Um, and that seems like actually quite reasonable. Um, super long context, super smart model. Um, it's onboarded immediately, and you can like send them off, uh, to like, complete subtasks and sub goals for you.

</details>

### 研究的日常：从想法到验证

**Unknown Speaker**: 请带我走一遍，比如，你一天的工作是怎样的？展示一下，你正在进行一个实验或项目，旨在让模型‘引述’（quote unquote）变得更好，对吧？比如，从观察到实验到理论再到写代码，整个过程是怎样的？发生了什么？

<details>
<summary>Original English</summary>

**Unknown Speaker**: Walk me through, like, a day in the life of, show, like, you're working on an experiment or project that's going to make the model, quote unquote, better, right? Like, what is happening from observation to experiment to theory to like writing the code? What is happening?

</details>

### 想法、验证与结果解读的循环

**Unknown Speaker**: 我认为最重要的一点，需要阐述的是这个过程：构思一个想法，并在不同规模下进行验证。嗯，以及，理解和弄清楚哪里出了问题。我想大多数人会惊讶于，要理解和弄清楚哪里出了问题，需要付出多少努力。因为人们脑子里有很多想法，他们想尝试。但并非每一个你认为应该奏效的想法都会奏效，而试图理解其中的原因非常困难。以及弄清楚你到底需要做什么来‘审问’（interrogate）它。所以，其中很大一部分是内省（introspection），关于正在发生什么。它不是在写成千上万行代码，也不是… 构思想法的难度，即使我认为很多人都有很长的想法列表想去尝试，从中筛选并根据非常不完美的信息做出‘定夺’（shot calling），去探索哪些才是正确的想法，这真的很难。

<details>
<summary>Original English</summary>

**Unknown Speaker**: I think the most important, like, part to illustrate is this cycle of coming up with an idea, proving it out at different points in scale. Um, and, uh, the, and like, interpreting, understanding what goes wrong. And I think most people would be surprised to learn just how much, much goes into interpret- like, interpreting and understanding what goes, what goes wrong. Because the ideas people have, long lists of ideas that they want to try. Not every idea that you think should work, will work. And trying to understand why that is, is quite difficult. And like, working out what exactly you need to do to interrogate it. Um, so, so much of it is like introspection about what's going on. It's not pumping out thousands and thousands and thousands of lines of code. It's not, um, like, the difficulty in coming up with ideas. Even, I think many people have a long list of ideas that they want to try. Pairing that down and shot calling under very imperfect information, what the right ideas to explore further is really hard.

</details>

### 不完美信息下的决策

**Unknown Speaker**: 请详细说说‘不完美的信息’是什么意思？是指早期实验吗？还是指，你在小范围内进行‘低增量’（low increments）的扩展时所获得的信息？你可以看到，比如在‘GPT-4’论文中，他们有很多点（dots），对吧？他们说我们可以估计最终模型的性能，比如，使用所有这些点，而且还有一条漂亮的曲线穿过它们。具体来说，为什么那是‘不完美的信息’？

<details>
<summary>Original English</summary>

**Unknown Speaker**: Tell me more about what do you mean by imperfect information. Are these early experiments? Are these like, what is the information that you're, like, scaling in low increments? You can see like in the GPT-4 paper, they have like a bunch of like dots, right? Where they say we can estimate the performance of our final model, like, using all of these dots, and there's a nice curve that like flows through them. Concretely, why do, why is that imperfect information?

</details>

### 趋势的不确定性与规模效应

**Unknown Speaker**: 是因为你永远不知道趋势是否会适用于某些架构。趋势一直都很好，某些改变也一直都很好。但情况并非总是如此。在小规模上有帮助的东西，在大规模上反而可能有害。嗯，所以基于趋势线看起来的样子，以及你凭直觉感觉‘好吧，这件事确实很重要’来做猜测。值得思考的是，在发布论文中你看到的每一张图表，背后都有一个‘第一轮运行’的‘坟场’（graveyard），然后还有所有那些走向不同方向的‘其他曲线’。

<details>
<summary>Original English</summary>

**Unknown Speaker**: is you never know if the trend will hold for certain architectures. The trend has held really well, and for certain changes, it's held really well. But that isn't always the case. And things which can help at smaller scales can actually hurt at larger scales. Um, so making guesses based on what the trend lines look like and based on like your intuitive feeling of, okay, this, this is actually something that's going to matter. That's interesting to consider that for every chart you see in a release paper, there's a graveyard of like first runs, and then like, there's all these other lines that go in like different directions.

</details>

### 理解模型的复杂性与猜想

**Unknown Speaker**: 是的，这太疯狂了。无论是作为一名研究生，还是在这里，你需要运行大量的实验，然后‘凭直觉推断’（intuiting）哪里出了问题，这确实非常困难。比如，弄清楚‘ Trenton’（研究团队）正在试图更好地理解的问题：‘这些模型内部到底发生了什么？’我们有一些推断、理解，甚至是一些关于为什么某些东西会起作用的‘脑补’（headcanon），但它不是一门精确的科学。嗯，所以你必须不断地猜测为什么会发生某事，什么实验可能揭示真相，而那很可能就是最复杂的部分。

<details>
<summary>Original English</summary>

**Unknown Speaker**: Yeah, it's crazy. Both like as a grad student, and then also here, like, the number of experiments that you have to run, and then intuiting what went wrong is actually really hard. Like, working out what, like, this is, in many respects, the problem that the team, the Trenton is on, is trying to better understand: is like, what is going on inside these models? We have inferences and understanding, and like, headcanon for why certain things work, but it's not an exact science. Um, and so you have to constantly be making guesses about why something might have happened, what experiment might reveal whether that is or isn't true. And that's probably the most complex part.

</details>

### 解释性团队与优先级排序

**Unknown Speaker**: 是的，我同意很多观点。但即使在‘解释性’（interpretability）团队，我是说，尤其是在Chris Ola的领导下，我们有很多想法想要测试。这真的就是‘工程’（Engineering）能力的问题，但我会给‘工程’打上引号，因为其中很大一部分是研究，需要非常快速地迭代一个实验，查看结果，解读它，尝试下一个，沟通。嗯，然后就是无情地对最高优先级的任务进行排序。这非常重要，‘无情地排序’是我认为区分‘优质研究’和‘不那么成功的研究’的关键之一。

<details>
<summary>Original English</summary>

**Unknown Speaker**: Yeah, I I agree with a lot of that. But even on the interpretability team, I mean, especially with Chris Ola leading it, there are just so many ideas that we want to test. And it's really just having the engineering skill, but I'll put Engineering in quotes because a lot of it is research to like very quickly iterate on an experiment, look at the results, interpret it, try the next thing, communicate them. Um, and then just ruthlessly prioritizing what the highest priority things to do are. And this is really important, like the ruthless prioritization is something which I think separates, uh, a lot of like quality research from, um, research that doesn't necessarily succeed as much.

</details>

### 理论的局限与简约偏见

**Unknown Speaker**: 我们正处在一个有趣（funny）的领域，我们的理论理解基本上已经被‘打破’（broken down）了。所以，你需要有一种‘简约偏见’（Simplicity bias），以及‘无情地排序’，来处理到底哪里出了问题。我认为，这正是区分最有效率的人的一个特点：他们不一定过于执着于使用他们熟悉的某种解决方案，而是直接解决问题。你经常看到，也许有人带着特定的学术背景进来，尝试用那个工具箱解决问题。而最棒的人是那些极大地扩展了工具箱的人。

<details>
<summary>Original English</summary>

**Unknown Speaker**: We're in this funny field where, uh, so many of our theoretical, initial theoretical understanding is like, broken down, basically. Um, and so you need to have this Simplicity bias, and like, ruthless prioritization over what's actually going wrong. And I think that's one of the things that separates the most effective people: is they don't necessarily get, like, too attached to solving using a given, like, a solution that they're necessarily familiar with. Um, but rather, they attack the problem directly. Um, you see this a lot, uh, in, like, maybe people come in with, like, specific academic background, they try and solve problems with that toolbox. Um, and the best people are people who expand the toolbox dramatically.

</details>

### 跨学科的工具箱与快速迭代

**Unknown Speaker**: 你知道，他们在里面跑来跑去，从强化学习（reinforcement learning）中汲取灵感，也从优化理论（optimization Theory）中汲取灵感，而且他们对系统有深刻的理解，所以他们知道是什么限制了问题的范围，而且他们是优秀的工程师，能够快速迭代并尝试想法。就像，毫无疑问，我见过的最优秀的研究员，他们都具备快速尝试实验的能力。这种‘周期时间’（cycle time），在小规模上，周期时间区分了人们。我是说，机器学习研究就是如此的经验主义。

<details>
<summary>Original English</summary>

**Unknown Speaker**: they're you know they're running around in there and taking ideas from reinforcement learning but also from optimization Theory and also they have a great understanding of systems and so they know what the sort of constraints that bound the problem are and they're good Engineers they can iterate and try ideas fast like by far the best researchers I've seen uh they all have the ability to try experiments really really really really really fast um and that is that cycle time and at smaller scales cycle time separates people I mean machine learning research is just so empirical.

</details>

### 贪婪优化与大脑类比

**Unknown Speaker**: 是的，而且说实话，这也是为什么我认为我们的解决方案可能最终看起来更‘大脑化’（brain-like）而不是其他什么的原因之一。就像，即使我们不想承认，整个社区都在对‘可能的人工智能架构’以及其他一切的‘景观’（landscape）进行一种‘贪婪的进化优化’（greedy evolutionary optimization）。就像，这不比进化好多少。

<details>
<summary>Original English</summary>

**Unknown Speaker**: yeah and and this is honestly one reason why I think uh our solutions might end up looking more brain-like than otherwise uh it's like even though we wouldn't want to admit it the whole Community is kind of doing like a greedy evolutionary optimization over the landscape of like possible Ai architectures and everything else uh it's like no better than evolution.

</details>