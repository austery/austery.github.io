---
author: Latent Space
date: '2026-07-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2wIxPWK6nCs
speaker: Latent Space
tags:
  - scale-lesson
  - data-bottleneck
  - sim-to-real-gap
  - model-efficiency
title: 科学研究中的规模效应与数据瓶颈：从模拟到现实的挑战
summary: 文章探讨了在人工智能和科学领域，如何克服“规模的苦涩教训”，即现有数据集的局限性。核心议题包括如何为模型提供新的扩展轴（如数据），以及将实验室概念转化为类似数据中心的未来模式。同时，文章分析了科研范式转变，例如利用计算资源进行快速验证和商业合作，以及解决“模拟到现实”的差距等关键技术瓶颈。
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
<!-- chunk 1/9 -->

### Cold Open

**Speaker A**: 但不仅限于科技生物 (techbio)，你们在科学方面具体做什么？

<details>
<summary>Original English</summary>

But not just techbio, what do you do in terms of science?

</details>

**Andy Beam**: 我们完全相信规模的苦涩教训 (bitter lesson)。我们认为，能够扩展且通用的方法会击败那些不能扩展的方法。正如 Ilya 去年在 NeurIPS 上所说，我们只有一个互联网。它是化石燃料。我们进行了水力压裂式的开采。我们尽可能地从互联网中榨取了每一盎司的数据，但它已经消耗殆尽了。因此，人工智能领域的问题是，下一个互联网规模的数据集将从何而来？

<details>
<summary>Original English</summary>

We are all in on the bitter lesson in scale. We think that methods that scale and that are general beat those that are not. As Ilya said at NeurIPS last year, we have but one internet. It's the fossil fuel. We fracked. We got every ounce of data that we could out of the internet, but it's gone. And so the question in AI is, where is the next internet scale data set coming from?

</details>

**RJ**: 你知道，人们通常会谈论不同的扩展维度。你有计算能力。你有数据。而对于科学来说，数据不一定是无限的资源。你们的观点是，我们现在想要为数据增加一个新的扩展轴。

<details>
<summary>Original English</summary>

You know, people normally talk about different scaling X's. You have compute. You have data. And for science, data is not necessarily an infinite resource. And your point is that we now want to add a new scaling axis for data.

</details>

**Speaker B**: 我们认为未来的实验室应该感觉像一个数据中心。一排排的服务器机架，尽可能密集地排列，同时也尽可能地提高能源效率，诸如此类。

<details>
<summary>Original English</summary>

We think that the lab of the future should feel like a data center. Rows of server racks, as densely packed as possible, and also as energy efficient as possible, and things like that.

</details>

### Introductions

**Brandon**: 欢迎来到 Latent Space Science。我是 Brandon。我和我的联合主持人 RJ 在这里。今天我们邀请到了来自 Lila Sciences 的 Rafa Gómez-Bombarelli 和 Andy Beam。我们就直接开始，让你们先自我介绍一下。

<details>
<summary>Original English</summary>

Welcome to Latent Space Science. I'm Brandon. I'm here with my co-host RJ. Today we have Rafa Gómez-Bombarelli and Andy Beam from Lila Sciences. We'll just start off and let you introduce yourself.

</details>

**Andy Beam**: 是的，感谢邀请我们上播客。我是长期的听众，第一次作为嘉宾参与，很高兴来到这里。我是 Andy。我是 Lila 的首席技术官。从事人工智能研究已经大概 20 年了，可以追溯到深度学习出现之前的日子，比如支持向量机 (SVM)、随机森林等。我大约在 2010 年到 2014 年期间攻读了神经网络的博士学位，当时深度学习正处于起步阶段。很明显，神经网络是值得押注的方向，但自动求导 (autograd) 库当时还没有开发出来。所以在那个年代，我是手工进行反向传播的，那种感觉就像是每天必须走很远的上坡路一样。我当时对医疗保健和生命科学领域的人工智能产生了浓厚的兴趣。我的妻子是一名医生，所以我看着她在各种问题中挣扎，我认为人工智能显然是解决其中许多问题的自然方案。之后我在哈佛大学医学院做博士后，从事医疗人工智能的早期工作。我主要是为了人工智能本身而身在其中。我真的很感兴趣人工智能可以解决什么问题。但我也一直对初创公司充满好奇。所以我暂停了一年学术界的工作，帮助创立了一家名为 Generate Biomedicines 的公司，这是一家早期的生成生物学公司。我是那里负责机器学习的创始主管。在接下来的五六年里，我体验了那种既是教授又是初创公司创始人的有趣混合身份。我在哈佛大学又建立了一个实验室，介于公共卫生学院和医学院之间，从事方法研究，但也有很多应用工作。那很有趣。这是一系列很棒的工作。但我感觉到人工智能的时刻正在以非常显著的方式发生改变。我希望成为其中的一部分。所以我开始思考，我可以在哪里从事人工智能最前沿、最令人兴奋的问题。学术界有很多优势。但获得规模化计算资源并不是它的优势之一，或者说规模化的资源。所以我曾是 Lila 的早期顾问，当公司的理念具体化后，我变得非常兴奋。但基本上，就是将科学作为一个无限的 token 生成器，来大规模地训练模型。除了创建一个能够解决科学问题的新前沿模型之外，我还有什么理由想从事其他工作呢？所以我半开玩笑地说，两年前我脱下了花呢外套，离开了我在学术界的职位，全职加入了 Lila，担任首任首席技术官。

<details>
<summary>Original English</summary>

Yeah, thanks for having us on the podcast. You're a long time listener, first time caller, excited to be here. I'm Andy. I'm the chief technology officer at Lila. I've been an AI researcher now for something like 20 years, going back to the pre-deep learning days, SVMs, random forests, things like that. I did a neural net PhD around 2010 to 2014, as deep learning was taking off. Clearly, neural nets were the thing to back, but autograd libraries really hadn't been developed yet. So I did the backprop by hand back in my day, walking uphill both ways kind of thing. Got very interested in AI for healthcare and life sciences. My wife's a physician, so I watched her struggle through different things and thought that AI was obviously a natural solution for a lot of those problems. Did a postdoc at Harvard in the medical school, doing early work on medical AI. And was really-- I'm in it for the AI. I was really interested in what problems could AI solve. But I've also always been like startup curious. So I took a break from academia for a year and helped start a company called Generate Biomedicines, which was an early generative biology company. I was the founding head of machine learning there. And got to do the fun kind of hybrid professor, startup founder thing for the next five or six years. So I had a lab at Harvard, again, sort of between the School of Public Health and the medical school, doing methods research, but also a lot of applied work. That was fun. There was a great set of jobs. But I got a sense that the AI moment was changing in a very significant way. And I wanted to be a part of it. So I started to think about where could I work at the frontier of AI on really, really exciting problems. And academia has a lot going for it. Access to scaled compute is not one of the things that it has going for it, or scaled resources. So I'd been an early advisor for Lila and got very excited once the thesis crystallized. But basically, science as an infinite token generator to train models at scale. Why would I want to work on anything other than creating a new frontier model that can solve scientific problems? So I kind of joked that I hung up the tweed jacket two years ago, left my position at academia, in academia and joined Lila full time as the inaugural CTO.

</details>

**Rafa Gómez-Bombarelli**: 是的，大家叫我 Rafa，我是 Lila 的物理科学首席科学官兼联合创始人。我以前是一名计算化学家。我们使用一种商品化资源，那就是计算。很明显，我们可以扩大计算规模来进行分子模拟。这产生了一定的数据量，以至于在 2010 年代初，我们意识到我们面临着数据问题。所以就在那时，我的研究方向发生了转变。我与 David Duvenaud 和 Ryan Adams 合作，融合了当时感觉像是科学深度学习的最初实例。我是第一批在标记化的分子上使用自编码器进行化学生成人工智能研究的人之一。从那时起，我就深深迷恋上了潜在空间 (latent spaces)。实际上，我们有一个非常类似于你们的标志，但是针对分子的，那个图形已经有了自己的生命。

<details>
<summary>Original English</summary>

Yeah, I go by Rafa, I'm the chief scientific officer for physical sciences at Lila and a co-founder. I was a computational chemist back in the day. We used a commodity resource that is compute. So it was clear that we could scale up compute to do molecular simulations. And that's sort of something that produced enough data that in the early 2010s, we realized we had a data problem. And so things switched gears for me right around then. I was, I worked with David Duvenaud and Ryan Adams in sort of blending what I think felt like the first instances of deep learning for science. I was one of the first people to do generative AI for chemistry with an autoencoder on tokenized molecules. And so then deeply in love with latent spaces. We actually have a very similar to your guys' logo, but for molecules, and that has taken its own life, that figure.

</details>

**Speaker C**: 这个标志肯定会刻在你的墓碑上。

<details>
<summary>Original English</summary>

This is the one that will be on your tombstone.

</details>

**Rafa Gómez-Bombarelli**: 完全正确。我的学生们甚至建立了一个 Slack 频道，专门用来发布在其他地方看到这个标志的照片。我的经历不如 Andy 的丰富，但也差不多。我在 2015 到 2016 年期间转变了方向，并在哈佛大学做博士后期间分拆出了一家公司，一家计算材料平台公司。然后去了麻省理工学院 (MIT)，在那里我建立了我的材料科学与工程团队。那里的团队主要在分子模拟和人工智能的交叉领域工作，比如材料结构的生成模型、自动求导工具，为了我们在分子模拟中想要看到的那些非常酷的梯度。到了 2022 到 2023 年，事情开始发生 Andy 刚才提到的转变，对吧？我们已经看到规模的苦涩教训应验在了计算生成的数据上。这就是为什么 Meta、DeepMind 和微软，他们都有专门的团队在做计算材料科学的人工智能。但很明显，我们需要更进一步，将这个东西完全推向现实，为实际的材料科学制造人工智能，而不仅仅是计算版本。这与在 22 年、23 年再次开始分拆出一家公司的机会相吻合，就像我说的，我们开始思考这个想法。我现在非常兴奋，能够推动这种科学推理的综合愿景，跨越我们可以在实验室中验证的所有科学模式。

<details>
<summary>Original English</summary>

Exactly. My students have a Slack channel just to post it when it shows up in the wild. Not as much of a story as Andy, but same. I converted in the 2015–2016 era and spun out a company from my postdoc at Harvard, a computational materials platform company. And then went to MIT, where I started my group in materials science and engineering. And the group there was sort of working at the interface of molecular simulations and AI with things like generative models for materials structure, autograd, for sort of really cool gradients that we want to see in the molecular simulations. And by 2022–2023, sort of things were taking sort of the turn that Andy just mentioned, right? We had seen the bitter lesson come to computationally generated data. And that's the reason why, you know, meta and DeepMind and Microsoft, they have teams doing AI for computational materials science. But it was clear that we needed to reach out and get this thing all the way out and make AI for actual materials science and not just the computational version. And that sort of lined up with this opportunity to start spinning out something again in, like I said, ’22, ’23, started sort of thinking about the idea. I'm very excited now to sort of be pushing this integrated vision of scientific reasoning across all the modalities of science we can validate in the lab.

</details>

### Lila's Thesis and Scale

**Brandon**: 这让我想问，Lila 的核心理念是什么？看起来你们在这里有一个非常雄心勃勃的目标。

<details>
<summary>Original English</summary>

That brings me to what is Lila's thesis? It seems like you have a very ambitious goal here.

</details>

**Andy Beam**: 是的，这是一个很好的问题。我尽量给你一个简短的总结 (TLDR)，然后我们可以再深入探讨几个层次。正如 Rafa 所说，我们完全相信规模的苦涩教训。我们认为，能够扩展且通用的方法会击败那些不能扩展的方法。这听起来似乎是显而易见的真理，但实际上它是反直觉的，并且与人工智能研究 70 年的历史中很大一部分是相悖的。但我们的认识是，在过去四五六年中促成大型语言模型崛起的原因，是结合了规模化计算和规模化数据的途径。那些数据来自互联网。它们是由人类生成的，而我们已经用光了它。正如 Ilya 去年在 NeurIPS 上所说，我们只有一个互联网。它是化石燃料。我们进行了水力压裂式的开采，我们尽可能地从互联网中榨取了每一盎司的数据，但它已经消耗殆尽了。因此，人工智能领域的问题是，下一个互联网规模的数据集将从何而来？在预训练时代之后，我们进入了具有可验证奖励的强化学习 (RL) 阶段。所以人们经常谈论强化学习，但强化学习本质上是模型自行生成数据的一种方式，奖励信号强化好的数据并惩罚坏的数据。对于数学和编程问题来说，这已经是一个非常有成效的框架。但在 Lila，我们认为实际上科学、运行科学方法并利用自然和实验作为验证器，是该框架的终极版本。所以我们正在建立的，我们将谈论这些我们称之为“人工智能科学工厂”的东西。它们是用于科学的规模化验证器，这样我们就可以大规模地进行后训练，并拓展推理模型的能力边界。这就是我们理念的简要概述。

<details>
<summary>Original English</summary>

Yeah, it's a great question. I'll try and like give you the TLDR and then we can go a couple of levels deeper. So like Rafa said, we are all in on the bitter lesson and scale. We think that methods that scale and that are general beat those that are not. That's actually sounds straightforwardly true, but is actually counterintuitive and contrary to much of the 70 year history of AI research. But the realization that we had is that what gave rise to large language models over the last four, five, six years is access to the combination of scaled compute and scaled data. That data came from the internet. It was human generated and we have used it all. As Ilya said at NeurIPS last year, we have but one internet. It's the fossil fuel. We fracked, we got every ounce of data that we could out of the internet, but it's gone. And so the question in AI is, where is the next internet scale data set coming from? Post the pre-training era, we moved into reinforcement learning with verifiable rewards. So people talk about RL a lot, but really what RL is is a way for a model to generate its own data and the reward signal reinforces good data and penalizes bad data. So that has been a very productive framework for problems in math and coding. But what at Lila we believe is that actually science, running the scientific method and using nature and experiments as verifier is like the ultimate version of that. And so what we're building, we'll talk about these things that we call the AI Science Factories. They are scaled verifiers for science so that we can do post-training at scale and push out the frontier of what reasoning models are capable of. So that's like the thesis in a nutshell.

</details>

**RJ**: 你的提议基本上是，人们通常会谈论不同的扩展维度 (scaling Xs)，你有计算，你有数据，你有参数。而对于科学来说，数据不一定是无限的资源。你们的观点是，我们现在想要为数据增加一个新的扩展轴。所以我引用我在 Escalante Bio 的一些朋友的话，他们有一篇博客文章，一篇非常好的博客文章，我推荐你们去读一下。文章里说，“你的实验是有运行时间 (runtime) 的。” 那么你们数据收集的运行时间是多久呢？

<details>
<summary>Original English</summary>

Your proposal is basically, people normally talk about different scaling Xs, that you have compute, you have data, you have parameters. And for science, data is not necessarily an infinite resource. And your point is that we now want to add a new scaling axis for data. So I want to quote some of my friends at the Escalante Bio, have a blog post, really good blog post, I recommend you read it. It says, "Your experiment has a runtime." So what is the runtime of your data collection?

</details>

**Andy Beam**: 我觉得，这是一个非常棒的问题。这显然会因实验而异。比如，你不能让核糖体运转得更快，至少据我所知是这样的。生物学设定了你运行速度的极限。在材料科学和化学中，有更短的时间尺度，也有更大的长度尺度。但你实际在问的是一个技术问题。那么你如何针对在反馈方面相差几个数量级的反馈机制来训练模型呢？所以我们认为 Lila 的整体能够生成不同时间尺度上的不同种类数据。然后，一旦这些数据生成，我们就可以同步我们训练模型的方式。同样，对于我们做的一些实验，时间尺度是在几天或几周的数量级。问题是，我们能多路复用吗？我们能在单位时间内获得更多数据吗？但是无限的 token 生成器依然存在。我们只需要解决另一端的技术问题，将所有这些部分对齐，并将其输入模型进行训练。

<details>
<summary>Original English</summary>

I mean, so that is an awesome question. It's so in, it will obviously vary by experiment. So like you can't make the ribosome go faster, at least to my knowledge. Biology sets a limit for how fast you can go. In materials sciences and chemistry, there are smaller time scales, there are larger length scales. What you're actually kind of asking is a technical question though. So how do you train a model against feedback mechanisms that vary by orders of magnitude in terms of feedback? So we think about all of Lila as being able to generate different kinds of data on different timescales. We can then synchronize how we train the model once that data has been generated. Again, for some of the experiments we do, the timescales are on the order of days or weeks. And the question is, can we multiplex? Can we get more data per unit time? But the infinite token generator is still there. We just have to solve the technical problem on the other side of that to be able to line all these pieces up and train it into the model.

</details>

**RJ**: 所以当你说无限的 token 生成器依然存在时，你是什么意思？因为你可以想象有许多不同的科学 token，有些 token 提供的信息比其他的多得多。有些东西你也许可以大规模收集，比如喜欢下一代测序 (NGS) 的人，你基本上可以收集无限量的 NGS 数据。然而，在某些情况下，另一个人类基因组可能只会是增量更新，相比于——

<details>
<summary>Original English</summary>

So when you say the infinite token generator is still there, what do you mean by that? Because there are many different scientific tokens you can imagine and some tokens provide much more information than others. And certain things you can collect maybe at scale, like people who love NGS, you can basically collect an infinite amount of NGS data. And yet there are certain cases where another human genome is probably going to be an incremental update versus--

</details>

**Andy Beam**: 是的，就像我的基因组相对于参考基因组一样，大概只有几千字节的信息量。那里的信息并不多。所以你完全正确。我们不想一遍又一遍地生成相同种类的数据。所以我们正在构建的平台与传统的自动化框架有着本质的不同。实际上，我们正在构建的实验平台，相比于原始吞吐量，优先考虑的是通用性和灵活性。我们希望模型能够设计一个新的实验方案，运行该方案，并接收反馈，即使那不是我们自己曾经想过要做的实验。所以下一个增量 token 必须是对模型有价值的东西，而不是又一个 NGS 样本来告诉我们它已经达到收益递减阶段的东西。

<details>
<summary>Original English</summary>

Yeah, like my genome relative to a reference genome is like a couple kilobytes worth of information. There's not a lot of information there. So you're exactly right. We don't want to generate the same kind of data over and over again. And so the platform that we're building is qualitatively different than traditional automation framework. So actually the experimental platform that we're building prioritizes generalizability and flexibility over raw throughput. We want the model to be able to design a new experimental protocol, run the protocol, and receive the feedback, even if that's not an experiment we have thought about doing ourselves. So the next incremental token has to be something that is valuable to the model versus yet another NGS sample to teach us something where it's already hit diminishing returns.

</details>

### Lab Automation as a Graph

**RJ**: 所以当你说下一个实验时，我想到的是，传统上你会走进实验室，以任何方式重新配置实验室，然后手动运行一些实验，可能需要几周的时间等等。在 Lila，实验室是如何为新的实验进行重新配置的？

<details>
<summary>Original English</summary>

So when you say next experiment, what I think of is traditionally you would go into the lab and reconfigure the lab in whatever way, and then run some experiments by hand, maybe over the course of weeks or whatever. How does the lab get reconfigured for the new experiment at Lila?

</details>

**Andy Beam**: 理解这个实验室的方式是，它几乎就像一个图 (graph)。每台仪器都是这个图中的一个节点。节点之间的边表示这两台仪器之间有一层物理传输层。所以我们稍后可能会展示一段视频。但我们有一层物理传输层，将我们在 Lila 购买的几乎所有仪器相互连接起来。这些目前是平面电机系统，上面有一个 96 孔板悬浮在轨道上方。你可以对该孔板移动的位置进行毫米级控制。所以你可以，我几乎把它看作是实验室的 PCI 总线，通过它每台仪器连接到系统的其余部分。

<details>
<summary>Original English</summary>

The way to think about the lab is it's almost like a graph. And so each instrument is a node in this graph. And an edge between a node indicates that there's a physical transport layer between those two instruments. And so we'll probably have a video that we'll show in a bit. But we have a physical transport layer that connects almost every instrument we've bought at Lila to each other. These are currently planar motor systems where there's a 96-well plate that magnetically levitates over a track. You have sort of millimeter-level control over where that plate goes. And so you can, I think of it almost as like a PCI bus for the lab, where each instrument connects to the rest of the system.

</details>

**RJ**: 这个比喻不错。我觉得一半的听众可能不知道什么是 PCI 总线。

<details>
<summary>Original English</summary>

That's a good one. I think half of the audience might not know what a PCI bus is.

</details>

**Andy Beam**: 所以它是一种通用串行总线，在你的主板上允许你连接新设备。如果你插入一块新显卡，如果你插入一块新硬盘，有一条总线允许该设备与你电脑的其余部分进行通信。

<details>
<summary>Original English</summary>

So it's a universal serial bus that on your motherboard allows you to connect a new device. If you plug a new graphics card, if you plug a new hard drive in, there's a bus that allows that device to speak to the rest of your computer.

</details>

**RJ**: 这适用于生物系统和材料系统等领域吗？

<details>
<summary>Original English</summary>

And this works for like bio systems and material systems and et cetera?

</details>

**Andy Beam**: 越来越适用，但目前还不完全。所以另一件需要记住的事情是——

<details>
<summary>Original English</summary>

Increasingly, but not totally yet. So the other thing to keep in mind about

</details>

<!-- chunk 2/9 -->

### 自动化的局限与“API边界”

**Andy**: 自动化其实存在一个非常长的“长尾”问题，你需要解决无数琐碎的细节才能真正实现自动化。而到目前为止，人们还没有以这种灵活的方式来思考端到端的自动化。因此，现在很多仪器并没有连接到这个系统中来。例如，在材料科学领域，并没有太多高通量的自动化设备，为此我们一直在专门建造定制的仪器，然后再把它们整合进来。但这里存在一个类似于“二八定律”的规则：那些容易整合和自动化的设备，会直接接入 PCI 总线；而那些难以自动化的部分，人们依然会进行人工干预。人们仍然需要把样品手动搬过去。或者，你会发现，仅仅是从试管上取下盖子，就是一个极难自动化的动作。实验室里的很多操作，都默认你拥有一双对生拇指，并且能灵活地使用它们。我们看到一些关于 Lyla 的讨论将我们定义为一家自动化公司，这实际上是对我们正在做的事情的一种误解。我们并不是“自动化至上主义者”，实际上我们更像是“Token 生成至上主义者”和“灵活性至上主义者”。所以，随着时间的推移，我们会把那些适合自动化的东西自动化，但同时，也会在现阶段合理的地方继续使用现成的（甚至是人工的）解决方案。所以，系统会设计实验，并给出指令。有时候会发现，“哦，这件事需要人去实际操作”，那你就去召集一些员工去完成那项任务。一切都是 API 调用。所以，有时候当你调用一个 API 时，执行它的是一个机械臂；而有时候，执行某个动作的则是一条人类的手臂。所以，人类其实就真真切切地存在于这个 API 界线之下。

<details>
<summary>Original English</summary>

**Andy**: automation is there's a very long tail of things that you have to solve to be able to automate. And to date, people have not been thinking about end-to-end automation in this like flexible kind of way. And so there are instruments that are not connected to this now. There's not a lot of high throughput automation and materials sciences, for example, and we've been building custom instruments for that that then are brought on board. But there's like an 80/20 rule at play here where things that are easy to onboard and automate are plugged directly into the PCI bus. And then things that are not, people still move. People will still move a sample to that. Or it turns out that removing a cap from a test tube is a very hard thing to automate. A lot of the lab assumes that you have opposable thumbs and you're good with them. And some of the things that we've seen discussed about Lila frames us as an automation company, and that's kind of the wrong perspective to think about what we're doing. We're not automation maximalists. We are actually sort of like token generation maximalists and flexibility maximalists. So we will over time automate things that make sense to automate, and then again, use solutions now where they make sense. So the system designs the experiments. It gives instructions. There's like, oh, people need to actually do this thing. So you recruit some of the staff to go and do that thing. Everything's an API call. And so sometimes when you call an API, there's a robot arm. Sometimes there's a human arm that does something. So people are literally below the API line.

</details>

**Interviewer**: 是啊，这太疯狂了。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, well, crazy.

</details>

**Andy**: 我认为，同样地，我们希望把资源花在值得花费的地方，做出理性的决策。有时候，当一个人能在十分之一秒内完成一个步骤时，再去尝试把它自动化就没有意义了。但真正重要的是，模型有能力给出指令来测试假设，并且所有这些数据都是可见的、透明的且被存储下来的，这样这些 Token 就能流回到模型中。

<details>
<summary>Original English</summary>

**Andy**: I think that like, again, we want to spend resources where it makes to spend resources and make rational decisions. And sometimes it just doesn't make sense to try and automate a step when a person can do it in a tenth of a second. But what matters is that the model has the ability to give instructions to test the hypothesis and that all of that data is visible, transparent, stored, so that those tokens flow back into the model.

</details>

**Interviewer**: 那么，你们是否让 AI 模型进行完整的实验设计呢？也就是超越现有的、只需微调比例或来源等参数的固定协议，那些参数你们都知道最终会进入管道或移液器之类的地方，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: Do you have your AI models doing entire like experimental designs, which are beyond just a pre-existing protocol where you tweak like relative ratios or sources from, or like what you know, all of those go into a pipe or pipette or something?

</details>

**Andy**: 我的意思是，这取决于你对“新颖性”的门槛有多高。毫无疑问，在表达协议（expression protocols）方面，比如我们做过的一些基因编辑工作，我们已经测试了平台执行这些任务的能力与人类的对比。模型在零样本（zero shot）情况下能达到大约 80% 的水平，而人类在零样本情况下的成功率是 0%。那么，我们现在在做完全开放式、自由形式的实验吗？其实还没有。那是我们的目标。我们正在朝着这个方向努力建设。那也是我们希望达到的状态。但我们已经见证了它能够在极短的时间内，完成相当于人类巨大心智劳动的工作能力。

<details>
<summary>Original English</summary>

**Andy**: I mean, it depends on like your threshold for novelty here. Certainly for expression protocols, for some gene editing work that we've done, we have tested like the platform's ability to do that versus humans. Model gets like 80% of that zero shot, humans get zero percent of that zero shot. Are we doing like fully open-ended free-form experimentation now? I mean, no, not yet. That is the goal. But we're building towards that. That's what we want to be in. But we have seen the ability to do what would be an enormous amount of human intellectual labor over a very, very short time horizon.

</details>

### AI 实验设计中的安全与浪费问题

**Interviewer**: 所以，当你们赋予 AI 模型一种自由设计的权力去开始构思新实验时，你们是如何确保这些实验是值得被测量的数据，或者你们如何验证这是一个好策略，而不是单纯在浪费大量资金呢？

<details>
<summary>Original English</summary>

**Interviewer**: So when you're giving these, you know, giving your AI models kind of free reign to start designing new experiments, like how do you make sure that these are things that should be measured or that you validate that this is, you know, a good strategy or that you didn't just waste so much money?

</details>

**Rafa**: 第一个问题是，我认为这里面可能涉及到一个潜在的安全问题。而且我认为我们从一开始就非常重视这一点，对吧？这包括安全和保障两方面：数据的安全（security），以及模型建议的安全性（safety）。我们拥有一支非常强大的团队，队伍在不断壮大，并且有非常强有力的领导。这是第一层保障。就像我们有强大的 AI 安全协议一样，这类似于人们在大型语言模型中一直研究的那种“能力提升（uplift）”的考量。只是我们的工作绝对是玩真的。我们有非常严格的 AI 安全协议，类似于人们在大型语言模型中所探究的能力跃升问题。不同的是，我们这里绝对是来真的。

<details>
<summary>Original English</summary>

**Rafa**: The first one is, there is I think maybe an underlying safety question there. And I think that we've been taking very seriously from the beginning, right? Both security and safety, security of the data and the safety of the model suggestions. We have a very strong team, it's growing and there's sort of very strong leadership. And that's the first layer, right? Like we have strong safety, AI safety protocols that look similar to the sort of uplift considerations that people have been looking into large language models. Only it's absolutely, we have strong AI safety protocols that look similar to the sort of uplift considerations that people have been looking into large language models. Only it's absolutely for real.

</details>

**Interviewer**: 在实验室自动化的环境中，当你正在处理一些生物物理材料科学类型的问题时，你实际需要担心的危险是什么？我通常会想到恶意行为者，或者是系统过于复杂导致它真的输出了某种危险物品的情况。从我对 Lila 目前范围的理解来看（虽然我们还没详细谈到，也许稍后会提及），目前在现阶段，安全性似乎并不会成为一个主要的担忧点？

<details>
<summary>Original English</summary>

**Interviewer**: In a lab automation setting where you're working on some, you know, biophysical materials science type problem, what are actually the dangers you have to worry about? There's like, I generally think of malicious actors and or, you know, situations where you have a sufficiently complicated system that it could genuinely output something dangerous. It seems like from the scope of Lila, as I understand it, which we haven't talked about yet, maybe it'll come in a minute, but it doesn't seem like safety is actually going to be a major concern at this point.

</details>

**Rafa**: 我觉得，这是我们从一开始就必须严肃对待的事情，对吧？这是一件我们绝对承担不起失误后果的事情。我同意你的看法，现在平台掌握在 Lila 的员工手中，他们是在对平台有深入理解和对齐的基础上去推动研究的，这与我们的使命是一致的。所以我同意，我们暂时不必担心恶意行为者。但我们在一定程度上仍然需要担心模型给出的建议本身。我认为更多的是一些触及实验室日常安全的事情，而不是恶意破坏。我不认为会出现涌现行为导致模型直接建议某种极端剧毒的化学物质。它更多地是指给仪器施加不当指令，比如导致化学品溢出，或者混合了你本来就不拥有的化学物质。因此，我认为自打一开始就必须设立一个化学 EHS（环境、健康与安全）保护层，因为我们在做的是某种开放式的、容易引发溢出风险的实验。

<details>
<summary>Original English</summary>

**Rafa**: I mean, it's something we need to take seriously from the beginning, right? Something where we cannot afford to not get it right. I agree with you. Right now it's in the hands of Lila employees that are sort of pushing interest on a line understanding of the platform. It's aligned with our mission. So I agree, we don't have to worry about malicious actors. We still need to worry to some degree about the model giving a suggestion. I think it's more some things that start touching into lab safety more than malicious. I don't think we're going to have emerging behavior where the model suggests an extremely toxic chemical. It's more about sort of pushing an instrument such that maybe it sort of overflows, it combines chemicals that you don't have. So I think there's like a chemical EHS safety layer that needs to be there since the beginning because we're doing sort of open ended overflows.

</details>

**Andy**: 我想说，我确实认为 Rafa 说得对，安全性不是你可以拖延处理的问题，因为能力增长曲线往往呈 S 型，它可能看起来一切正常，然后突然之间就会出现一些你完全没预料到模型竟然能做到的事情。所以在这方面我们绝对是积极主动的。正如 Rafa 所说，我们有一个 AI 安全团队，但我也认为你说的有道理，那就是我们可以在有意义的层面上约束这个问题，这种方式是那些与普通公众互动的通用 AI 系统所做不到的。同时，我们也可以依靠生物安全等级之类的标准，运用那些传统而可靠的实验室安全规范来在过渡期提供帮助。当然，暴露给特定科学问题的节点也是有限制的，我们没必要把所有的实验能力都暴露给所有的科学问题，对吧？对于一个抗体设计的问题，我们可能根本不需要向模型透露我们有装满气体的气罐，对吧？因为它根本用不到。所以我们可以巧妙地处理，而不是把范围局限在单一的科学领域。另外，关于你的问题，我觉得这很有意思：你很难去判断某件事情是否危险，或者很难去断定这是否是在浪费资源。比如我们在电催化剂方面做的一些工作，Lila 内部有一位专家在这个课题上发表了 40 篇论文。起初模型提出的一些建议让他觉得很无聊，但后来，建议从“无聊”变成了他眼中的“愚蠢”。这些建议是用于将水分解为氢气和氧气的非铂系电催化剂。然而结果证明，那成为了我们制造出来的最好的非铂系电催化剂。所以，“明显错误”、“类似 AlphaGo 惊天第37手”，以及“甚至让人类专家都感到惊讶”之间的界限是非常难以界定的。因此，我们确实会去做一些看似浪费资源的事情，因为我们想找出这二者之间的区别。

<details>
<summary>Original English</summary>

**Andy**: I mean, I do think Rafa's right in that safety is not something you can procrastinate on because capability curves tend to be sigmoid shaped and it can look like everything's fine, everything and then all of a sudden there's something that you didn't anticipate the model being able to do. So we are definitely proactive on that side. We have an AI safety team like Rafa said, but I think you're also right in that like, we can constrain the problem in meaningful ways in the way that like a broad based AI system that interacts with the general public cannot. We can also lean on biosafety levels and things like that, good old fashioned lab safety to help in the meantime. And of course the nodes that are exposed to a particular, we don't necessarily need to expose all the experimental capabilities to all the scientific questions, right? For an antibody design question, we probably don't even need to expose the model to the fact that we have gas canisters that contain gases, right? Because it's not gonna need them. So we can still be creative with instead of questions that relate to one particular area of science. Yeah, so your question though is, sorry, is interesting. Like how do you know if something is dangerous is like actually kind of hard to do or actually how do you know if it's wasteful? Some of the work that we've been doing in like electric catalysts, we have someone inside of Lila who's like published 40 papers on the topic and some of the suggestions from the model initially were boring, but then transitioned from boring to what he considered to be stupid. These are non-platinum-group electrocatalysts for separation of hydrogen and oxygen from water to make hydrogen. And those turns out to be our best non-platinum-group electrocatalysts that we've made. So the line between like obviously wrong and like quasi-move 37 and surprising even to a human expert is hard to know. And so we will do wasteful things because we kind of want to know the difference between the two.

</details>

### 数据有效性与团队验证

**Interviewer**: 这就引出了一个问题。对于你们现在所描述的这类实验，它是成是败是非常明显的，对吧？但你可以想象，就像之前伯克利实验室围绕那些被误解的测量数据产生的一些争议那样。你们如何确认你们对有效性的测量，或者你们试图优化的任何指标实际上是准确无误的呢？

<details>
<summary>Original English</summary>

**Interviewer**: That brings up the question. So for like an experiment like what you're describing now, it is obvious whether it works or not, right? But you can imagine, and there was some controversy in the Berkeley lab around measurements that were misinterpreted, right? How do you know that your measurements of effectiveness or whatever you're optimizing are actually correct?

</details>

**Rafa**: 是的，我对那个领域的状况非常熟悉。我想说，我们绝不能仅仅因为它是 AI，就放松科学严谨的标准。这不同于五年前，那时当我们开始为 X 和 Y 做生成模型时，大家会觉得：“哇，这挺可爱的。它运作起来就像个小孩子做的一样。”现在我们已经超越了那个阶段。我们需要以要求常规的、由人类主导的科学研究的相同标准来要求 AI 科学。我认为 2023 年的那篇论文是一个社区观念的转折点，从事科学研究的 AI 社区人员，过去看到渐进式的进步总是很兴奋。但我想从那时起，我们开始集体触及到了整个科学界更广泛的意识。他们不再只是说“太棒了”。我们现在要讨论的是如何以最高标准来完成我们的工作。所以我觉得我们有很多实验专家在把关。但我想回到刚刚关于 API 的观点上。我认为我们很幸运，能够从零开始建立一家公司，让人们具备 AI 意识，对 AI 感到兴奋。在我们合作的所有人和网络中，我们成功地建立了一支由实验专家和自动化工程师组成的团队，他们真正相信这个使命，并真的想让它实现。他们非常宽容地对待这一切，对吧？所以，每当 AI 给出一些大错特错的东西时，他们会在那里应对：“好吧”，然后他们按下红色的按钮警报，注意，这简直是个糟糕透顶的主意。但他们也很宽容，比如说，在测试“假阳性”结果时。假阳性对于人类科学家来说是可怕的，对吧？因为你去尝试一些东西，结果发现行不通。但对于模型来说，这太棒了。它极大地减少了不确定性。对操作员来说，这有点扫兴，对吧？因为你本以为会得到一些很酷的东西。并且我认为我们成功做到了，回到 Andy 刚才提出的那一点，我想大约直到三个月前，人们还是在单纯地审查并批准 AI 的决定。但大约三个月前，我们开始发现模型提出的一些疯狂想法开始让人感到惊讶，更令人惊讶的是，人们的反应变成了：“我不知道，我猜我们得试一试。”我们亲眼见证了这种转变。我认为实验专家们挑战 AI 但同时保持开放包容的能力，也就是这种人机接口的互动，在过去的几个月里一直非常有价值。

<details>
<summary>Original English</summary>

**Rafa**: Yeah, I'm very familiar with that part of the landscape. I would say we cannot relax our standards of scientific rigor because it's AI, right? It's not, you know, maybe five years ago when we started doing generative models for X and Y, they were like, "Yeah, it's cute. It kind of works like you would do with a kid. " It's like, but now we're past that. And we need to hold AI science to the same standard we hold, regular human-led science. And I think that 2023 paper was a switchover from the community, a part of, you know, the AI community for science people, we're always excited to see incremental progress. And I think at that point, we started collectively touching upon the rest of the community's awareness. And they were like, "Fantastic. " But, you know, now we're gonna talk about the way we do things to our highest standard. So I think we have lots of experimentalists. But I wanna go back to the API point. I think we've had the fortune by starting from zero to build a company where people are sort of AI aware, AI excited, we have sort of, across all the people and the networks that I collaborated with, we've managed to build a team of experimentalists and automation engineers that really believe in the mission and really want to make it happen. They're really taking this graciously, right? So whenever AI gives something that is sort of very, very wrong and they're there to just, "Okay," they push the red button, watch out, this is a vast idea. But they're also gracious in, for instance, trying false positives. False positives are terrible for human scientists, right? Because you go to try something, it doesn't work. For the model, it's fantastic. It reduces uncertainty a lot. For the operators, it's kind of a bummer, right? Because you thought you were gonna get something cool. And I think we've managed, and going back to the point Andy made, for the, you know, I think about until three months ago, people would be sort of approving AI decisions. And I think about three months ago, we started seeing that the model's crazy ideas started being sort of surprising to people, but surprisingly, it was like, "I don't know. I guess we need to try. " And we seen the switchovers. I think the ability of people, experimentalists, to sort of challenge the AI, but being gracious, like that interface of human and computers has been very rewarding over the last few months.

</details>

**Andy**: 另外我还想说，把实验室的控制权交给模型，会迫使你建立基础设施，以暴露那些你通常不想或不关心的实验数据。你知道，也许没有什么实验本身是错误的，但你需要有能力去解释实验的结果。所以，如果你想一想，如果你做了一个实验并拟合了一个统计模型，你试图做的就是用输入的变量来解释输出变量的变化。我们之所以有能力解释输出的变化，是因为我们测量了非常多的不同变量，因为我们必须把这些数据暴露给模型。所以我们可以说：“好的，实验室里的湿度不对，那也许这恰好解释了那个结果。” 然后我们还可以按下按钮，重新运行实验来进行验证。因此我们不认为，正如 Rafa 所说，在某些事情上我们必须对任何结果持更加怀疑的态度；但我们能够随后迅速回去重新运行那个实验，因为说到底它本质上就是软件在运行。

<details>
<summary>Original English</summary>

**Andy**: And I would also say, like, giving the model control of the lab forces you to build infrastructure to expose pieces of data that you wouldn't normally want to or care about. And, you know, maybe no experiment is wrong, but you want the ability to explain the outcome. So if you think about it, if you have an experiment, you fit a statistical model, what you're trying to do is use variation inputs to explain variations in outputs. And so we have the ability to explain variation in outputs because we measure so many different things because we have to expose that to the model. So we can say, "Okay, the humidity was off in the lab that maybe that explains exactly the thing. " And then we can also push button and rerun the experiment to verify. And so we do not believe, like Rafa said, in some things we have to be more skeptical of any outcome, but we can then quickly go and rerun that experiment because it's all software, effectively.

</details>

**Interviewer**: 那你们觉得团队在这上面花了很多时间进行验证吗，或者说时间的分配比例是怎样的？

<details>
<summary>Original English</summary>

**Interviewer**: And you find that the team spends a lot of time on verification, or like, how's the breakdown?

</details>

**Rafa**: 越来越少了。我想在最开始的时候，这倒不算是负担。我的意思是，这确实有一个执行过程，比如：“好的，我们有一个假设，我们有一组即将发给 API 的指令。”我们为它做担保，然后 API 中的某些部分是需要人去做的。我认为这一部分将会保留下来，对吧？这就是体力劳动的部分。但是我觉得那种反复核对 AI 直觉是否正确的做法在逐渐减少。我认为我们开始在这种超级智能中看到局部的火花闪现——

<details>
<summary>Original English</summary>

**Rafa**: Less and less so. I think at the beginning, it wasn't so much, I mean, there is an execution of, "Okay, we've got a hypothesis, we've got a set of instructions that's gonna go off to the API. " We vouch for it, and then some parts of the API are people doing things. And I think that will stay, right? That's the labor of it. But I think the double checking that the intuitions were right, I think we're starting to see in this super intelligence local spikes of

</details>

<!-- chunk 3/9 -->

### 超越生物技术：科学领域的超级智能与强化学习

**Rafa**: 在这些领域，我们更多地是在支持这种超级智能行为的涌现，而不是在扮演把关人的角色，而且这些想法不仅仅是徒劳的。所以我认为这种情况正在各个领域发生。也许可以进一步阐述一下 Andy 提到的例子，我们非常关心能源和可持续性，对吧？要知道，我们不仅仅是一家生物技术公司，我们真的非常关心能源、可持续性和材料科学，我们正在尝试制造绿氢。为了制造绿氢，也就是利用光来分解水分子，你需要为其中很大一部分能量买单，因为这些能量储存在化学键中，而你是从阳光和电力中获取这些能量的。然后还要付出一些额外的代价，称为过电位，这与现实世界并不完美、存在能量损耗这一事实有关。而这种损耗来源于一种叫做催化剂的东西。目前的催化剂还可以，但是它们既昂贵又稀有。它们是由钌和铱制成的。因此，我们建立了一个模型来探索：我们能做些什么来避免使用这两种元素？人们会发表这些论文，比如，几周前有一篇论文说，用于某某领域的低钌合金。我的意思是，是的，当然，你可以减少它的用量，对吧？你可以把它稀释，但它仍然是同一个根本问题，你只是少用了 50%。因此，我们针对这类问题设定了模型规则，我们有能力制造材料、测量性质、测量催化作用、测量稳定性。然后在第二代、第三代的连续学习中，对吧？也就是在信息和模型已知内容之间的这种交互作用中。我们开始看到一些建议，我的意思是，它使用的词汇都没问题。它使用的是我们常用的概念。只是说，换作是我，我不会把那个想法应用到那个元素上。我不会把它们以那种方式组合在一起。但结果证明，这是我们迄今为止性能最好的化学物质。

<details>
<summary>Original English</summary>

**Rafa**: places where we're kind of, you know, supporting this emergence of super intelligent behavior more than we are sort of gate keeping, and that the ideas are not just wasteful. So I think that that's happening for domains, and maybe to elaborate a little on the example that Andy mentioned, we care a lot about energy and sustainability, right? Something that, and you know, we're not just a biotech, we really care about energy and sustainability and materials, we're trying to make green hydrogen. And you know, in order to make green hydrogen, to use light to split the water molecule, a bunch of that energy you need to pay for because it's the energy that's stored in the chemical bond, and that you get from sunlight and electricity. And then there is some overhead that you pay that's called the overpotential, which has to do with the fact that the world is not perfect and things are lossy. And the loss comes from something called the catalyst. And today the catalysts that are out there are okay, but they're expensive and rare. They're made out of ruthenium and iridium. So we set up a model to explore, what can we do to not use these two elements? And people do these papers and there is, you know, there was something a couple of weeks ago that said ruthenium, you know, low ruthenium alloys for X, Y, Z. I mean, yeah, it's like, sure, you can, you know, dope it down, right? You can water it down, but it's still the same fundamental problem. You're using 50% less. So we set out the model rules on this type of problem and we have the ability to make the material, measure the properties, measure the catalysis, measure the stability. And then in the second, third generation of sequential learning, right? This interplay between sort of information and what the model knows. We started seeing suggestions that were like, I mean, the words were fine. It was using the concepts that we use. It's just that you know, I wouldn't apply that idea to that element. I wouldn't have put them together in that way. And it turns out those have been our best performing chemicals so far.

</details>

**Interviewer**: 我确实想谈谈“Lila 不是一家生物技术公司”这个话题，但在那之前，顺着这个思路问最后一个问题。强化学习（RL）以“奖励作弊（reward hacking）”而闻名。你刚才，我忘了你具体怎么说的了。我不知道你是否说过你们正在使用 RL，或者，学习迭代。我会非常担心，你给出一些奖励，然后模型可能会在物理科学中进行作弊，而这在纯计算领域是做不到的。

<details>
<summary>Original English</summary>

**Interviewer**: I do want to get to the, Lila is not a biotech, but before we do one last question along this train, thought train, RL is famous for reward hacking. You just, I forget what you said. I don't know if you said you were using RL, but or, you know, learning iterations. I would be very concerned that you know, you throw some rewards and that you can really hack the, you know, physical sciences in a way that you can't do with the compute.

</details>

**Andy**: 是的，我不反对这一点。100% 同意。

<details>
<summary>Original English</summary>

**Andy**: Yeah, I'm not going to disagree with that. 100% agree with that.

</details>

**Interviewer**: 最搞笑的例子是什么？

<details>
<summary>Original English</summary>

**Interviewer**: What's the funniest example?

</details>

**Andy**: 我们有很多有趣的类似于 RL 失败的例子，它们并不完全是奖励作弊。嗯，我的意思是，其中一个是当我们训练模型时，我们早期做的一件事是，你能否直接制作一个微孔板布局图（plate map）？就像，你能把实验条件布置在微孔板上吗？当有人提出要求时，模型居然生气了。就是你要求模型做一个微孔板布局图，它会去做。然后人们会说，其实，你能换一下这些试剂吗？然后它就会，比如，开始骂人。我们就会觉得，这只是一个 96 孔板。拜托，伙计。就是在它的思维链中。

<details>
<summary>Original English</summary>

**Andy**: We have lots of funny, like, RL fails that are not explicitly reward hacking. Well, I mean, one is when we train, one of the early things we did was like, can you just like make a plate map? Like, can you like lay the experimental conditions out on a plate? And it got annoyed when the person would ask. So you would ask the model to do a plate map and it would do it. And they'd be like, actually, could you change these reagents? And it would like, swear. We'd be like, it's a 96 well plate. Come on, man. Like, in the chain of thought.

</details>

**Interviewer**: 我不知道那是从哪学来的，但它就是会这样。肯定是从互联网的某个地方学来的。

<details>
<summary>Original English</summary>

**Interviewer**: I don't know where that came from, but it would like. Somewhere on the internet.

</details>

**Andy**: 是的，某个地方。里面包含了互联网的数据。我无法忘记那件事。所以我们看到很多类似这种由 RL 导致的有趣性格怪癖。也有一些明显的 RL 问题，我不会叫它们奖励作弊，而是病态行为，比如重复。就像思维链会崩溃，然后它就会一遍又一遍地重复最终答案。出于某种原因，这有时候确实能可靠地带来更高的奖励。我们不确定为什么病态的思维链或不可读的思维链在某些情况下会导致更高的奖励。

<details>
<summary>Original English</summary>

**Andy**: Yeah, somewhere. The internet's in there. I can't forget that. So we've seen lots of like funny, like personality quirks like that as a function of RL. There's like obvious RL, I wouldn't call them reward hacking, but pathologies like repetition. So like the chain of thought will collapse and it will just like repeat its final answer over and over and over again. For some reason, that reliably sometimes leads to higher rewards. We're not sure exactly why pathological chain of thoughts or non-legible chain of thoughts in some cases lead to higher rewards.

</details>

**Interviewer**: 抱歉，我想打断一下。所以我们正在谈论 RL。听起来就像是针对思维链进行 RL，就像所有人都在做的那样。但你们的 RL 实际上包含了一个实验室步骤。如果你陷入了一个病态循环中，那是否意味着实验室就在一遍又一遍地做同一个实验？

<details>
<summary>Original English</summary>

**Interviewer**: So, sorry, I wanna interrupt. So we're talking about RL. We're talking about the way you're talking about it. Sounds like just RL on chain of thought, just like everybody's doing. But your RL actually has a lab step. If you're in a pathological loop, does that mean the lab is just like doing the same experiment over and over again?

</details>

**Andy**: 思维链，也许我们先退一步来说，是模型用来解决问题的标记（tokens）。如果你在解一道数学题，你会用定理一、定理二、推论、引理，你会把问题分解。在科学领域，思维链也有一些类似的内容。也就是会发生推理过程。我试图为这个靶点制造一种抗体。关于这个靶点我知道什么？抗原表位是什么？我的攻击计划是什么？在思维链中还包含工具调用。比如，我可能会用一个结构预测模型来了解序列在三维空间中是如何折叠的。所以工具调用是思维链的一部分。在 Lila，有趣的是，实验室仪器也是工具调用，或者是工作流中的一系列工具调用，而且它们都是人类可读的。它们都是用英语表达的。因此，我们观察到的一些病态行为是，它直接跳过了所有中间部分，而我们会认为这中间部分对于解决问题是很重要的，然后直接给出了答案。它说，在这种情况下我不需要做实验。我不需要调用工具。在某些情况下，当我们能够进行评判时，可能因为我们之前做过类似的实验，出于某种原因，这种策略在某些情况下实际上并不差。所以这里面有一些神秘的东西。

<details>
<summary>Original English</summary>

**Andy**: So a chain of thought, maybe just to step back, is tokens that the model uses to solve a problem. So if you were solving a math problem, you would do theorem one, theorem two, corollary, lima, you decompose the problem. In science, the chain of thought, there's some of that too. So there's reasoning that happens. I'm trying to make an antibody for this target. What do I know about this target? What are the napotopes? Like what's my plan of attack? In the chain of thought are also tool calls. So maybe I'm gonna use a structured prediction model in case to get some read of how the sequence folds in three dimensional space. So tool calls are part of the chain of thought. At Lila, the fun thing is that the lab instruments are also tool calls, or a series of tool calls for a workflow, but it's all human legible. It's all in English. And so some of the pathologies we've seen is it just skips all the middle part, which we would think is important for solving a problem, and just goes right to the answer. And says, I don't need to do an experiment in this case. I don't need to call a tool. And in some cases where we can judge something, because maybe we've already done the experiment or something like that, for some reason it is actually not a bad strategy in some cases. And so there's some mystery there.

</details>

**Interviewer**: 它是理论家。

<details>
<summary>Original English</summary>

**Interviewer**: It's a theorist.

</details>

**Andy**: 是的，而不是计算。这可能有些偏题了，但它实际上是在潜在空间（latent space）中思考，然后发出标记。因此，关于模型计算到底在做什么，思维链通常是一个不可靠的叙述者。所以我们试图思考的一大问题是，当我们开始解决一个问题时，正如 Rafa 提到的关于电催化剂的问题，我们其实并不知道什么是对的什么是错的。我们应该在多大程度上依赖思维链，而不是仅仅相信实验、相信验证器、相信模拟器作为最终的真理标准。

<details>
<summary>Original English</summary>

**Andy**: Yeah, it's not the calculation. And this is probably too much of a tangent, but it actually thinks in latent space, it emits tokens. So the chain of thought is often an unreliable narrator for what the computation of the model is actually doing. And so one of the big things we're trying to think about is when we're moving into working on a problem, like Rafa said, for electrocatalysts, that we actually don't know what right and wrong looks like. How much should we rely on the chain of thought versus just trusting the experiment, trusting the verifier, trusting the simulator as the ultimate ground truth.

</details>

### 数据生成与模型商业化

**Interviewer**: 那么，Lila 不是一家生物技术公司。

<details>
<summary>Original English</summary>

**Interviewer**: So, Lila is not a biotech company.

</details>

**Andy**: 我认为 Lila 在这方面实际上相当独特。我参与过生物技术公司的事务，帮助创办过生物技术公司。通常它们的目标是冲刺到临床试验阶段。你想开发一种资产，开发平台是为了拥有能够进入哪个领域的选择权。但是，一旦你有了临床资产，你就会把其他所有东西都放在一边进入医学昏迷状态，专注于通过临床试验，如果进展顺利，其他事情才能继续进行。所以，我们排除了那种选择。在 Lila，模型本身才是具有价值的东西。因此，从这个意义上说，我们更像是一个新形态的实验室（neo-lab），试图想出一种新方法，将能力推向一个核心的基于 LLM 的推理模型。

<details>
<summary>Original English</summary>

**Andy**: Lila is actually fairly unique, I think, in this way. I've been involved with biotechs, I've helped start biotechs. Often the goal is to sprint to a clinical trial. So you want to develop an asset, you develop the platform in service of having optionality of what space you move into. But once you have the clinical asset, put everything into a medically induced coma and you get through the clinical trial and if it goes well, then other things get to, so we are taking that option off the table. The model itself is the thing of value at Lila. So in that sense, we're much more of like a neo-lab, trying to think of a new way to push forward capabilities to a core reasoning LLM-based model.

</details>

**Interviewer**: 甚至连实验室平台也不是主要价值？所以实验室平台只是标记生成器（token generator）。

<details>
<summary>Original English</summary>

**Interviewer**: Not even the lab platform? So the lab platform is the token generator.

</details>

**Andy**: 没错。那是数据生成机制，这最终才是 Lila 的护城河。一旦它继续扩张，我们所能生成的数据量，无论是单位时间还是单位面积的数据生成量都会上升，这些数据将反馈给模型，让它变得更聪明，然后由模型建议接下来该做哪个实验。所以，我们真正专注于使这个核心模型的性能和智能化程度尽可能地高。我们可以讨论一下这如何适用于不同的商业策略，但归根结底，我们感兴趣的是创造这种新型的人工智能模型。

<details>
<summary>Original English</summary>

**Andy**: Okay. That is the data generation mechanism that ultimately is the moat for Lila, is that once that continues to scale, the amount of data that we can generate, both per unit time but per unit square foot will go up and that feeds back into the model to make it smarter, that then suggests the next experiment to do. And so we really are focused on making this core model as performant and smart as possible. And we can talk about how that lends itself to different commercial strategies, but ultimately we're interested in creating this new type of AI model.

</details>

**Interviewer**: 我想引用 Octant Bio 公司的 Sri Kossuri 的话，几周前他发了一条我很喜欢的推文，他问：在药物发现领域，机器学习的商业模式是什么？因为如果你需要数据来训练模型，但是如果你已经拥有了数据，你还需要模型做什么？

<details>
<summary>Original English</summary>

**Interviewer**: So I wanna quote Sri Kossuri from Octant Bio, who had a great tweet, I really loved a few weeks ago, it was, what is the business model in ML for drug discovery? Because if you need the data to train the model, but if you have the data, what do you need the model for?

</details>

**Andy**: 当你范围狭窄时，这确实是对的。在科学的某一个特定垂直领域，这是事实。我要用一个类比，比如回到 10 年前，如果你想创建一个代码助手模型，你只会获取代码数据。你不会同时去获取莎士比亚的诗歌或者墨西哥猪肉卷（carnitas）的食谱，但事实证明，随着模型能够在更广泛、更深层次的数据上进行训练，就会出现溢出效应（spillover）。所以再说一遍，我们所押注的核心在于，这对于科学领域同样适用。如果模型在日益广泛的数据集上进行训练，那么你在特定领域所需的数据量将会减少。在某些情况下，如果它与模型以前见过的数据相邻，数据需求甚至会降至零。所以，有一个关于数据效率的论点表明，再次强调，拥有一个能产生广泛科学数据的通用平台是有益的。我还要补充一点，显然，我们正在使用的是一些已经商品化了的东西。我们使用公开的数据集，使用模拟器，而我们的实验平台是对这些现有商品化资源的补充。

<details>
<summary>Original English</summary>

**Andy**: That is true when you are narrowly scoped. So that is true within a given vertical of science. The analogy that I would use is like, if you went back 10 years and you tried to create like a coding assistant model, you would just get coding data. You wouldn't also get Shakespeare poetry, carnitas recipes, it just, it turns out that there is spillover as the model is able to train on a broader swath of data and a deeper cut of data. And so again, the core bet that we're making is that is true for science. That if the model is trained on an increasingly broad set of data, the amount of data that you need in a given domain, that data requirement is reduced. In some cases, will be reduced to zero if it's adjacent to what the model has already seen before. And so there's a data efficiency argument that would suggest that again, having a general platform that can create a broad swath of scientific data, I'll also just mention that like, obviously we are using things that are already commodities. So public data sets we use, simulators we use, and experimental platform is a compliment to these existing commodity resources.

</details>

### 科学领域的领域迁移与通用推理

**Interviewer**: 这在我的脑海中引发了一个关于“适用范围（applicability domain）”概念的问题，在这个概念中，你面对的是不同的尺度、不同的事物，它们导致了完全不同类型的信息和实体之间的关系，对吧？所以你有量子领域，化学领域，还有各种不同的生物领域。我对这种跨领域方法的一个担忧是，这些领域之间是否存在迁移能力？墨西哥猪肉卷食谱和国际象棋问题，它们有一个共同点，那就是都是用语言写成的；而在这些科学领域中，你面对的几乎是完全独立的、甚至不是同一种语言的东西，对吧？在这些领域之间有着完全独立的模型。

<details>
<summary>Original English</summary>

**Interviewer**: This brings up a question in my mind about, there's a concept of applicability domain where you have different scales, different, and they result in different types of completely different types of information and relationships between entities, right? So you have the quantum realm, you have chemical realm, you have sort of different bio realms. One concern I would have with cross-cutting approaches is their domain transfer between these at all. Whereas, carnitas recipes and chess problems, you have the commonality that they're written in language, whereas you almost have a completely separate, not even language, right? It's a completely separate model between these domains.

</details>

**Andy**: 人类科学家可以在所有这些领域中工作。

<details>
<summary>Original English</summary>

**Andy**: Human scientists work on all of those domains.

</details>

**Interviewer**: 没错，并且他们主要通过书面语言和使用工具来相互交流。

<details>
<summary>Original English</summary>

**Interviewer**: Correct, and they mostly communicate with each other in written language using tools.

</details>

**Andy**: 所以我会说，存在一种通用的推理过程，允许人们在每一个领域内解决问题。我认为这种逻辑同样适用于我们正在训练的推理模型，它同样使用工具、能进行数学运算、能写代码，而且它将所有的知识都存储在一个地方。

<details>
<summary>Original English</summary>

**Andy**: So I would say there's a common reasoning process that allows someone to solve problems in each one of those domains. And so I think that that logic carries over to a reasoning model that we're trading, that again, uses tools, can do math, can do code, but it's having all of that knowledge stored in one place.

</details>

**Interviewer**: 对我来说，一个经典的领域迁移的例子是在复杂性理论和量子引力之间，对吧？现在许多量子引力理论基本上已经认识到两者背后的数学结构是相同的，对吧？你有没有这种“天哪，这个领域竟然可以应用到那个领域”的例子？

<details>
<summary>Original English</summary>

**Interviewer**: One classic example for me of domain transfer is between complexity theory and quantum gravity, right? Where now a lot of the quantum gravity theories are basically recognizing the identical math behind the two of them, right? Do you have examples of this kind of sort of, oh man, this domain actually applies to this domain?

</details>

**Andy**: 我们收集了这个包含 10 万亿个科学标记的推理数据集，这些跨越生命科学、化学和材料科学的推理轨迹都经过了实验验证。而且我们已经看到，这个通用模型经常能击败那些特定领域的模型。所以很难指出究竟是模型里的什么东西起了作用，它到底发现了什么联系；但是很明显，看到了科学所有领域内更多的数据后，在样本对比中，它确实击败了特定领域的推理模型。

<details>
<summary>Original English</summary>

**Andy**: So we have assembled this reasoning data set of 10 trillion scientific tokens, reasoning traces that are experimentally verified across life sciences, chemistry, and materials sciences. And we have seen that this general model often beats the domain-specific models. And so it's hard to point to what's in the model that is making it, what connections it has realized, but clearly having seen more data across all of science beats sort of in a sample for sample kind of way domain-specific reasoning models.

</details>

**Interviewer**: 科学的未来是语言，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: The future of science's language, right?

</details>

**Rafa**: 嗯，所以，是的，所以我不——

<details>
<summary>Original English</summary>

**Rafa**: Well, so, yeah, so I don't--

</details>

**Interviewer**: 化学的未来非常广阔。

<details>
<summary>Original English</summary>

**Interviewer**: Future of chemistry is huge.

</details>

**Rafa**: 也许吧。我不认为这是必要的，我不认为这是实现科学超级智能的必要条件。我的意思是，上周 Demis Hassabis 有句引言是怎么说的来着？这可能不值得去蒸馏所有存在于额外 Alpha 形式中的方法，对吧？有些数据模态与语言大不相同。而且你知道，Andy 总是对我说，“那么，Rafa，英语是图灵完备的，所以你可以用英语表达一切。”

<details>
<summary>Original English</summary>

**Rafa**: Maybe. I don't think it's necessary, I don't think that's a necessary condition for a scientific superintelligence. I mean, there was this quote from Demis Hassabis what, last week? That it might not be worth distilling all the ways that live in sort of, you know, both in the extra alpha form, right? There are data modalities that are so different from language. And you know, Andy always tells me, "Well, Rafa, English is Turing-complete, so you could express everything in English."

</details>

**Interviewer**: 有几种图灵完备语言，但是的，是的。

<details>
<summary>Original English</summary>

**Interviewer**: Several Turing-complete languages, but yes, yes.

</details>

**Rafa**: 所以，我同意这一点。由于性质的不同，可能有些地方用别的方式会更高效……我是说，你做过几何深度学习，对吧？我认为对于几何学，也许，你知道，我……

<details>
<summary>Original English</summary>

**Rafa**: So, and I agree with that. There might be places where it's more efficient because of the nature of the, I mean, you've done geometric deep learning, right? I think for geometry, and maybe, you know, I

</details>

<!-- chunk 4/9 -->

### 科学领域的模型与工具结合

**Speaker A**: （我想提一下我的同事 Tess Smidt）几何学是人们认为其问题性质可能更适合其他模型架构的领域之一。因此，如果我们需要调用一个蛋白质折叠模型，或者我们需要调用一个平衡扩散模型来生成晶体结构，这都是可以接受的常规操作。所以我可以说，科学在未来与我们对话的方式，肯定是通过语言来进行的。至于模型是否需要一直用英语来思考化学问题，也许是，也许不是。化学家们在思考化学时用的也不是英语。

<details>
<summary>Original English</summary>

**Speaker A**: call my colleague, Tess Smidt, I think geometry is one of those places where people feel that there might be sort of just the nature of the problem is more amenable to other architectures. So if we need to call a protein folding model, or we need to call an equilibrium diffusion model to make crystal structures, that's fair game. So I would say, the future of the way science talks with us, for sure, is through language. That the model needs to be thinking in English about chemistry all the time, maybe yes, maybe not. Chemists don't think about chemistry in English.

</details>

**Speaker B**: 好的，是的，但他们谈论化学时用的是英语。

<details>
<summary>Original English</summary>

**Speaker B**: Okay, yeah, they talk about it in English.

</details>

**Speaker A**: 是的，没错。而且我同意 Rafa 所说的一切，即基于 token 的推理与工具使用相结合是非常强大的。我认为我们想表达的是，我们在科学领域才仅仅触及了这种潜力的皮毛。我们并不是试图将特定领域的模型精简提取成一个纯粹的推理模型。而是这个模型它可以高效地使用这些工具。因此，仅仅是在英语环境下（有时也包括在 Python 等语言中）的推理与工具使用相结合，就已经是极其强大的了。我们在科学应用中还处于非常早期的阶段，仍在探索我们能把它向前推进到什么程度。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, exactly. And I agree with everything Rafa said, like token-based reasoning with tool use is very powerful. And I think the claim that we're making is we have barely scratched the surface for that in science. We're not trying to distill domain-specific models into a reasoning model. It can use those tools productively. And so it's just the combination of reasoning, often in English, but also in Python and things like that, combined with tool use is very powerful. And we're very early in science and understanding how far we can push that forward.

</details>

**Speaker B**: 那么您能举一些您正在运行的具有代表性的项目或活动的例子吗？实际上，在您回答之前，也许顺便说一下，我意识到我们还没有向听众解释你们不仅仅做生物学研究。你们不只是做科技生物（tech bio）。所以我认为这是一个很好的切入点。那么，除了科技生物之外，你们在更广泛的科学领域还做些什么呢？

<details>
<summary>Original English</summary>

**Speaker B**: So can you give some examples of campaigns that you are running that are representative? And actually, before you do that, maybe just take that, I realize we still haven't explained that you don't just do bio. It's not just your tech bio. So I think this is a great lead into this. So not just tech bio, what do you do in terms of science?

</details>

**Speaker A**: 科学领域？不，也许吧，我们训练模型的方式是跨越生命科学领域的，无论是 DNA 还是任何蛋白质细胞、小分子，各种不同类型的化学反应，以及不同类型的材料。所以这就是我们目前所界定的研究范围，不可否认，这是一个很大的范围——

<details>
<summary>Original English</summary>

**Speaker A**: Science, no. So maybe, yeah, so the way that we train the model is, I mean, it's across life sciences, or DNA or any protein cells, small molecules, different kinds of chemistries and different types of materials. So that is like where we're scoped now, which is admittedly a large--

</details>

**Speaker B**: 材料本身的研究范围也绝不仅仅是一小块，它和生物学里的所有内容一样，范围极为庞大。

<details>
<summary>Original English</summary>

**Speaker B**: The material itself is also not just, that's also as largely scoped as everything that's in the bio.

</details>

### 从量子点到材料科学的扩展

**Speaker A**: 我们可以举几个例子。今天我们能制造薄膜，我们能制造其他东西，我们还能制造量子点。我们有一个非常酷的量子点技术。大家熟悉这个概念吗？量子点是某些电视中的一种发光技术，你需要进行控制，使它们都具有完全相同的纳米级尺寸。你制造出来的纳米尺寸直接决定了它们会呈现什么颜色。你需要最纯正的红色、最纯正的蓝色和最纯正的绿色，这样才能为你的电视打造出非常鲜明和丰富的色彩。而且你需要让它们尽可能均匀。它们必须完全一致，否则颜色就会变得浑浊并且混合在一起。

我们有一个很酷的演示，在我们的自动驾驶实验室里，我们让访客来到办公室时挑选一个波长，即你希望量子点呈现出什么颜色。然后我们启动机器，模型开始进行推理，有时我们甚至会加入模型从未见过的新型化学物质，只是想看看它是如何运作和反应的。机器运转起来，在这个大约一个到一个半小时的参观结束时，机器可能已经制造出了一代或更多代的量子点。而且它们通常能够成功命中目标，否则我们也不会用它来做展示，对吧？[笑声] 它们往往能精确命中人们建议的颜色。

所以我们拥有制造大量材料的能力。我们可以配制液体、聚合物以及软物质。我们非常关注能源和可持续性发展。所以我们在电化学能力方面占据了很大的比重，涉及化学转化与作为可再生能源的电能之间的相互作用。我们关注传统催化技术，也关注材料的力学性能。所有这些能力汇聚到了我们的项目中，我们在那里制造催化剂，制造用于防腐蚀或航空航天领域的高性能涂料，以及高性能的力学应用。而在过去的几周里，我们与一位外部合作伙伴开始进行了多次敏捷研发冲刺，涉及到了我们以前未曾涉足的领域，从粘合剂一直到冷却液都有。所以我们能够越来越多地在开放式的化学和材料科学领域迅速启动并实现激动人心的发现。

<details>
<summary>Original English</summary>

**Speaker A**: We can give some examples. So today we can make thin films, we can make others, we can make quantum dots, we have a cute quantum dot. Are you folks familiar? Quantum dots are the luminescent technology in some TVs, and you need to control to make them of exactly the same nanometer size. And the nanometer size you make them controls what color they're going to be, and you need the purest red and the purest blue and the purest green to make really sharp and rich color palettes for your TV. And you need to make them as homogeneous. They all need to be the same, otherwise the color gets muddied and blended. 

So we have a cute demo where our self-driving lab, we ask our visitors to pick a wavelength, what color you want the quantum dot to be when they come into the office. And then we fire off the machine, the model reasons, sometimes we even throw in new chemicals that the model had never seen, just to see how it moves. The machine is running, and by the end of this sort of hour, hour and a half tour, the machine has made maybe one, maybe more generations of quantum dots that tend to hit, otherwise we wouldn't do it, right? [laughter] They tend to hit the color that people suggested.

So we have the ability to make lots of materials. We can formulate liquids and polymers and soft matter. We care about energy and sustainability a lot. So we have a good chunk of electrochemistry capabilities about the interplay of chemical transformations and electricity as a renewable energy source. We care about traditional catalysis, and we care about mechanical properties of materials. And all this comes together in programs where we make catalysts, we make high performance coatings for corrosion or aerospace, high performance mechanical applications. And over the last few weeks with an external partner, we started multiple sprints of things we weren't doing before that touch from adhesives to cooling fluids. So we've been able to sort of more and more spin up just exciting discoveries in sort of open-ended chemistry and materials science spaces.

</details>

**Speaker B**: 量子点和例如蛋白质设计之间有什么联系吗？

<details>
<summary>Original English</summary>

**Speaker B**: Do you have any connection between quantum dots and let's say protein design?

</details>

**Speaker A**: 它是同一个平台在做这些事情。是同一套能力。所以有一个共享的基础设施，它让我们能够在同一个屋檐下完成所有这些事情。如果这其中没有联系的纽带，那我们就无法做到这些，我们根本就不具备做所有这些事情的能力。

<details>
<summary>Original English</summary>

**Speaker A**: It's the same platform that does that. It's the same set of capabilities. And so there's a shared infrastructure that lets us do all of those things under the same roof. If there were no connected tissue, then our ability to do, we just would not have the ability to do all those things.

</details>

**Speaker B**: 我们有没有做过类似机制可解释性（mech interp）方面的研究，比如深入观察模型内部，看看从电催化剂中获得的洞见是否会有所启发？

<details>
<summary>Original English</summary>

**Speaker B**: Have we done like the mech interp thing where we look inside the model and see, does this insight from electro-catalyst inform,

</details>

**Speaker A**: 我们还没有对机制可解释性进行过深入的专项研究。我们确实看到，随着平台的日益成熟，我们执行这些项目的速度变得更快了。

<details>
<summary>Original English</summary>

**Speaker A**: we haven't done a deep dive on the mech interp thing. We have seen that our ability to do these programs has gotten faster as the platform has become more mature.

</details>

**Speaker B**: 那么语言模型代理（LMP）就像是某种常见的东西，在你的工具包中这是非常普遍的吗？因为这一点，它促成了你刚刚提到的大部分想法得以实现。这在生物方面显然是合理的，但我对生物的了解远远超过对材料的了解。在你们的实验室工具包中，这是一个共同的主题吗？

<details>
<summary>Original English</summary>

**Speaker B**: So is LMP just like a common thing along, like is this something really common in your toolkit that because of this, this enables like a large fraction of these ideas that you've just mentioned. It certainly makes sense on the bio side, but I know bio much more than materials. Is that like a common theme amongst you, like your lab toolkit?

</details>

**Speaker A**: “AI 科学工厂”拥有的能力越多，我们在追求新的目标产品概貌以及寻找激动人心的新机遇时，行动的速度也就越快。因为模型做好了执行更多任务的准备，实验室能做的事情更多，我们的科学家为了吸纳新能力也变得更加灵活和快速。随着我们拥有的仪器数量增多，添加新仪器的速度也变得更快了。

所以这也许呼应了我们究竟是一家什么类型的公司，也就是超大规模扩展的另一方面——在这里，软件层面的扩展是建立在硬件扩展的支持之上的。事实上，我们有数以万计平方英尺的实验室即将投入使用，里面配备有几十到数百台仪器，正是这一点赋予了我们快速行动的广阔天地。

<details>
<summary>Original English</summary>

**Speaker A**: The AI science factory, the more capabilities has, the faster we've been able to go after new target product profiles and about new exciting opportunities, because the model is prepared to do more things, the lab can do more things, our scientists are more flexible and faster in order to incorporate new capabilities. Adding new instruments has become faster, the more instruments we have. So maybe echoes with sort of what type of company we are, the second of hyperscaling here, of this sort of scaling in software is backed by scaling in hardware. And the fact that we have sort of tens of thousands of square feet of lab coming online with sort of dozens to hundreds of instruments is giving us this breadth to move fast.

</details>

### 从生物到材料的跨领域迁移与扩展挑战

**Speaker B**: 在某些领域，你们的团队有过涉及——我的同事 Heather Kuehlich 最近在播客中来过这里，我们看到的一个领域是吸附（sorption）。我想听众会对这些材料很熟悉，不需要我花太多时间去介绍它们。这些材料是通过分子与金属的相互作用形成的。结果发现，我们的模型最初是针对小分子药物发现进行训练的，而它利用在思考药物发现时学到的所有化学知识，转而对这种金属有机框架（MOF）材料进行推理。我们可以利用这些材料将二氧化碳从空气中提取出来，或者用来过滤氨气。

我发现这非常迷人。很多时候，我看到人们从事机器学习工作时，他们在一个庞大的数据集上进行训练，然后他们转移到某个全新的领域，结果你往往发现这种迁移的效果非常微小。那么，你们是否有一组……我不知道该怎么恰当表达，就像是能组合在一起并经常导致你们实验结果的“原色”（primary colors）？

<details>
<summary>Original English</summary>

**Speaker B**: There are places, you folks had, my colleague Heather Kuehlich here in the podcast recently, one of the areas we're seeing, sorption, so I think the audience will be familiar with these materials, I don't need to spend a lot of time introducing them. These materials are made of the interaction of a molecule with a metal, and it turns out our models have been trained on small molecule drug discovery, and all of the chemistry that they have learned thinking about that discovery, got rid of it to start reasoning over this metal-organic framework materials that we can use to take CO2 out of the air or to filter ammonia. Find that fascinating, like when I think, so many times I've seen people work on machine learning where they train some big data set and then they move to some new domain and oftentimes the amount of transfer you see is small. So are there like a group of, I don't know how to say this, primary colors that you have that you combine together that oftentimes result in your experiments?

</details>

**Speaker A**: 在生物学方面，它们是显而易见的候选对象：核酸感受态（nucleic acid competence）、无细胞表达（cell free expression），以及针对我们所关心的事物的下游检测分析。存在一些核心能力，能够由此衍生出数量呈阶乘级增长的各种不同应用，在材料方面也是如此。

我认为配方（formulation）也是其中之一，而且它甚至……我不知道该怎么形容，我不想说它“平庸（mundane）”，但它太普遍了，也太重要了，以至于它并没有成为首批令人觉得“超级智能”的领域。在最开始的时候，我们会想到更多炫酷华丽的东西。但结果发现，工业界和世界上许多其他领域的人们都非常关心配方，也就是把液体和黏稠物质混合起来制造出其他的黏稠物质，这涵盖了润滑剂、脂质纳米颗粒、除臭剂。就像在消费类产品、工业产品和医药领域中的所有这些东西一样，从凝胶到皮肤移植物，所有这些都源自这种混合黏稠材料的过程，而这正是我们在努力建设的一项“肌肉”能力。随着我们与人们的交流越来越多，它作为一个非常普遍的平台不断涌现出来。

<details>
<summary>Original English</summary>

**Speaker A**: So on biology, they'd be the obvious candidates, nucleic acid competence, cell free expression, and then downstream assays for things that we care about. There are core competencies that we can then sort of give rise to a factorial number of different things that you can do, and on the material side. I think formulation, and it wasn't even, it's so, I don't know, I don't want to say mundane, but it's so common, it's so important that it wasn't one of the first sort of super intelligent places. We thought of flashier things back at the beginning, and it turns out a lot of people in industry and in the rest of the world care about formulation, meaning mixing liquids and gooey things to make other gooey things, but that's lubricant, that's lipid nanoparticles, that's deodorant, like there's all these things in consumer products and industrial products and in medicine, you know, gels, to skin grafts, all those things emerge from these sort of mixing gooey materials, and that's a muscle that we're building. That's a very common platform that is showing up all the time the more we talk with people.

</details>

**Speaker B**: 很有意思。在思考扩展（scaling）问题时，我经常使用一个经验法则，那就是在一个系统中每扩展一个数量级，你所面临的问题集合就会发生完全的改变。你们挑选了两个最困难的问题领域，对吧？材料和生物。你们也做其他事情，但众所周知，材料和生物领域的产品很难推向市场。通常有着 10 年、15 年的时间跨度，其原因尤其是在材料领域，很大程度上就在于扩展问题。那么你们是如何考虑这个问题的？你们是觉得“我们仅仅负责研发发现”，还是认为“我们会去解决扩展的问题”？你们的想法是什么？

<details>
<summary>Original English</summary>

**Speaker B**: Interesting. I have a rule of thumb that I often use when I'm thinking about scaling, which is that every time you scale an order of magnitude in a system, that your set of problems completely changes. You guys pick the two hardest problems, right? Materials and bio, you do other stuff, but materials and bio are notoriously difficult to get to market, right? 10-year, 15-year time horizons, and the reasons are, especially for materials scaling. So how are you thinking about that? Are you just saying we're discovery, or are you saying that we'll get to it? How are you thinking about it?

</details>

**Speaker A**: 在我停止做学术讲座之前准备的最后一场学术讲座，名字叫做“材料与化学中关于扩展的苦乐参半的教训”，因为情况正是如此。事实证明，在人工智能（AI）领域，扩展是一件好事，因为它为你规划了你需要做的事情的路线图。而在化学和材料科学中，扩展是一件让人感到可怕的事情，因为最终你会发现，只有那些能够被实际扩展的东西才是有意义的。

所以我们对此极其清楚，对吧？我们的产品团队、我们的实验室团队，大家都心知肚明。例如，在量子点的例子中，我们能够将同样的配方从个位数毫升的规模一直扩展到将近 100 毫升，几乎是一升。所以在一些情况下，我们今天的能力已经把数字化的发现带入了实际的规模扩展和技术成熟度层面。

然后，我们正在打造系统，使得系统能够在目前进行实验的同时，推理出未来在放大规模时什么是至关重要的。这将体现在我们研发无稀土（rare earth free）或无铂族金属（platinum group free）催化剂的过程中，对吧？这个问题的本质正是我们需要能够去扩展这些产品，对吧？所以它是具有供应链意识的。当我们启动并开展第一个实验时，我们已经阅读过了相关的每一篇论文。我们在角落里已经部署了一个技术经济分析（technical economic analysis）智能体，随时准备对我们所做的任何事情进行技术经济学评估。

但归根结底，我们不会去亲自做临床试验。我们也不会为了你们炼油厂里的某一个特定工艺去专门建造中试工厂，对吧？在那个阶段，这些都是我们将与客户合作的地方。或者说，如果我们发现了非常令人惊叹的东西，不需要任何进一步的指示，我们就直接将其商业化出售。但通常我们会进行技术交接，就像我们将为我们的客户提供治疗药物发现的支持一样。我们将针对客户面临的痛点来支持材料创新。而这些往往也与扩展息息相关。

<details>
<summary>Original English</summary>

**Speaker A**: The last academic lecture I prepared before I stopped giving academic lectures is called the bittersweet lesson of scaling in materials and chemistry, because it's this. It turns out, you know, in AI, scaling is a good thing because it gives you a roadmap of what you need to do, and in chemistry and materials, scaling is a spooky thing because it turns out only the things that you can scale matter. So we're extremely cognizant, right? Our product team, our lab team, we all know. For instance, in the Quantum Dot example, we've been able to use the same recipe from a single-digit milliliters to 100, almost a liter. So there are places where, you know, our capability today takes bytes into scaling and into technology readiness level. 

Then we are making the system such that they can reason about what's going to matter later as they're doing the experiments now. And this will be in our rare earth free or sort of a platinum group free catalysts, right? Precisely the nature of the question is that we need to be able to scale these, right? So it's supply chain conscious. As we're firing off the first experiment, we've already read every paper. We've already have a technical economic analysis agent sitting on this in the corner, ready to do the technical economics of anything we do. At the end of the day, we're not gonna do clinical trials. We're not going to make pilot plans for one particular process that you will put in your refinery, right? At that point, these are places where we will work with our customers or, you know, if we find something so amazing that we don't even need any instruction and we just go sell it. But typically we will hand off just like we're going to support therapeutic discoveries for our customers. We're going to support materials innovations at the pain points our customers have. And those also have to do with scaling.

</details>

**Speaker B**: 你们到目前为止进展到了什么程度呢？

<details>
<summary>Original English</summary>

**Speaker B**: How far have you gotten so far?

</details>

### 生命科学平台与 CAR-T 疗法

**Speaker C**: 在生命科学方面，我想我同意 Rafa 刚才在那里所说的一切。关于人们将如何使用这个平台，或者说我们正在构建的究竟是什么，思考这个问题的更准确方式是，它很像是科学领域的 Claude Code 这类的东西。

因此，吸引早期客户来到我们这里的一点是——我们并不是一家专门做体内 CAR-T (In vivo CAR-T) 的公司。现在市面上有很多体内 CAR-T 公司。这个领域目前非常火爆。比如六个月前通过超过 20 亿美元的 Capstan 收购案我们确实看到——如果大家对这方面不熟悉的话，体内 CAR-T 是一种非常新的热门治疗模式，以前主要用于血癌，但现在越来越多地被用于治疗自身免疫性疾病。

我们在内部确实已经具备了进行体内 CAR-T 所需的“三驾马车”能力体系。显然，结合物设计（binder design）是我们能做的，此外还有 LNP 配方设计以及 mRNA 设计。

<details>
<summary>Original English</summary>

**Speaker C**: So on the life sciences, and I think I agree with everything Rafa said there. The way to think about like how people would use the platform is or just kind of like what we're building is much more of like a Claude Code-ish kind of thing for science. So one of the things that has drawn early customers to us is so we're not an In vivo CAR-T company. There's lots of In vivo CAR-T companies. Super hot right now. We did see, you know, six months ago with the Capstan acquisition for like two plus billion dollars, if folks aren't familiar with that, like In vivo CAR-T is this very new hot therapeutic modality previously for blood cancers, but now increasingly for autoimmune disease. We did have in the internal like sort of triumvirate of capabilities that you would need to do In vivo CAR-T. So binder design, obviously we can do that LMP formulation and then mRNA design.

</details>

**Speaker B**: 稍微解释一下，好让大家知道 CAR-T 是什么。

<details>
<summary>Original English</summary>

**Speaker B**: Just so people know what CAR-T is.

</details>

**Speaker C**: 是的。那真的非常酷。

<details>
<summary>Original English</summary>

**Speaker C**: Yes. It's really freaking cool.

</details>

**Speaker B**: 不，我很喜欢这个。这太酷了。

<details>
<summary>Original English</summary>

**Speaker B**: No, I love it. It's so cool.

</details>

**Speaker C**: 我可以讲讲 CAR-T 吗？是的，我可以讲讲 CAR-T。所以，其实从上世纪80年代末或90年代开始，人们就在研究 CAR-T，大约在2010年左右在癌症治疗领域它才真正火了起来。以前它的工作原理是这样的：提取出体内的一些 T 细胞，在这个基础上设计并添加所谓的嵌合抗原受体（chimeric antigen receptor），这个受体就会告诉 T 细胞去寻找并杀死哪种类型的细胞。

<details>
<summary>Original English</summary>

**Speaker C**: Can I talk about CAR-T? Yeah, I can talk about CAR-T. So CAR-T has been worked on since like the late 80s or 90s, really caught fire around 2010 or so for cancers. The way it used to work is you'd extract some of those T cells, you would engineer what's called chimeric antigen receptor that goes on top of that, that tells the T cell to what kind of cell to go and kill.

</details>

<!-- chunk 5/9 -->

### CAR-T 疗法的原理与早期挑战

**Speaker A**: 所以你基本上就是在改造人们的 T 细胞，把它们取出来，然后进行改造，使其表面带有一种奇特的抗原受体。就像一个寻找并摧毁的标记。通常他们使用一种叫做 CD19 的蛋白质，这种蛋白质优先表达在 B 细胞上。当 B 细胞发生恶变时，它们会导致血癌，引发自身免疫性疾病。你要清除某人几乎全部的 B 细胞库，我们可以做到这一点，但这会产生很多附带损伤。但从本质上讲，你是在告诉 T 细胞去寻找并杀死什么。

<details>
<summary>Original English</summary>

**Speaker A**: So you're basically modifying people's T cells, take them out, you modify it so that it has this weird antigen receptor on its surface. To seek and destroy tag. Usually they use a protein called CD19, which is preferentially expressed on B-cells. When B-cells get malignant, they create blood cancers, they create autoimmune diseases, you wipe out someone's, almost their entire B-cell repertoire, we can do this, there's a lot of collateral damage. But essentially you're telling the T cell what to go and kill.

</details>

**Speaker A**: 这项技术真正开始火爆是在 2015 年左右。当时它既昂贵又缓慢，你必须提取某人的 T 细胞，必须对它们进行基因工程改造，每次输注大约需要 40 万美元，但这仍然是治疗许多不同类型癌症的灵丹妙药。这有点扯远了，但有一个名叫 Emily Whitehead 的孩子，她在宾夕法尼亚州儿童医院（CHOP）接受了治疗。她是首批通过 CAR-T 治愈的小儿癌症患者之一。她本来要被转诊到临终关怀中心了，后来接受了 CAR-T 治疗。这又是个扯远的话题，在最初的 CAR-T 治疗中，她差点死于发烧。

<details>
<summary>Original English</summary>

**Speaker A**: So this really started to catch fire around 2015. It was expensive and slow, you have to extract someone's T cells, you have to engineer them, it was like $400,000 per infusion and just like, it's still a miracle cure for lots of different types of cancer, too much of a tangent for this, but there's this child named Emily Whitehead, who was treated at the Children's Hospital of Pennsylvania, CHOP. She was one of the first cures in pediatric cancer by CAR-T. She was gonna be referred to hospice care, got CAR-T. Another was like, "Psychetangent." She almost died of a fever from this initial CAR-T treatment.

</details>

**Speaker B**: 是的，那太难了。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, that's difficult.

</details>

**Speaker A**: 她幸存下来的唯一原因，是因为治疗她的医生有一个患有小儿关节炎的女儿，并且知道这种特定的抗体可以减弱她对 CAR-T 的 IL-6 反应。所以在用于科学的 AI 方面，那里有很多值得剖析的地方，在那个特定的案例中，所有事情都必须顺利进行，这充满了偶然性。也许如果你再掷一千次骰子，你可能也无法在那个时刻刚好遇到那位知道该给她什么抗体、从而让这种治疗成为治愈手段而不是致命手段的医生。所以再说一遍，这些就是我们实际上想要自动化的那种偶然事件。

<details>
<summary>Original English</summary>

**Speaker A**: The only reason she survived, because the doctor who was treating her had a daughter with pediatric arthritis and knew that this specific antibody would blunt her IL-6 response to CAR-T. So like, there's a lot to unpack there in terms of AI for science, all the serendipity that had to happen in that specific case for all of that to go right. And probably if you roll that dice a thousand more times, you probably don't get that doctor at that moment who knew exactly what antibody to give her to make that treatment curative instead of lethal. So again, those are the types of serendipity things that we'd actually like to automate.

</details>

### 从脂质纳米颗粒到“可编程生物学”

**Speaker A**: 总之，现在它变得非常便宜了。人们后来意识到，实际上只需通过一次输注，如果你取一段编码嵌合抗原受体的 mRNA，将其放入被称为脂质纳米颗粒的东西中，在这个脂肪球的外部放上靶向 CD8 的部分，然后你给患者进行输注，它就会去与 T 细胞结合，被吞噬，脂肪球溶解，mRNA 释放出来，嵌合抗原受体得到表达，并呈现在 T 细胞的表面。所以你只是在告诉，或者说重新编程 T 细胞，让它们表达这些奇特的抗原。

<details>
<summary>Original English</summary>

**Speaker A**: So anyway, it's so inexpensive. People then realize that actually through just an infusion, if you take an mRNA that encodes for the chimeric antigen receptor, you put it in a lipid nanoparticle called a lipid nanoparticle, you put a CD8-targeting moiety on the outside of this ball of fat, it will then, you give them the infusion, it will go bind to the T cell, get ingested, ball of fat dissolves, mRNA comes out, chimeric antigen receptor gets expressed and presents on the top of the T cell. So you're just telling, you're reprogramming the T cells to express these weird antigens.

</details>

**Speaker B**: 简直就是在对生物学进行编程。

<details>
<summary>Original English</summary>

**Speaker B**: Literally programming biology.

</details>

**Speaker A**: 然后 T 细胞就去执行它的任务，清除在这个案例中任何带有 CD19 的细胞。因此，恶性 B 细胞可以解释很多血癌的成因。它们也可以解释很多自身免疫性疾病。B 细胞经常会产生针对自身抗原的抗体之类的情况。所以在最近，六个月前，作为大约六年工作的结果，从一位诺贝尔奖得主的实验室分拆出来，并投入了大约 1 亿美元的研发资金，我们看到了——那音乐真不错，老兄——我们看到了一些关于自身免疫性疾病体内 CAR-T 治疗最令人信服的临床前数据。它是由一家名为 Capstan 的公司做出的，他们被艾伯维（AbbVie）以大约 21 亿美元的价格收购了。

<details>
<summary>Original English</summary>

**Speaker A**: And then the T cell goes and does its thing and wipes out whatever has CD19 in this case. So malignant B-cells explain a lot of blood cancer. They also explain a lot of autoimmune diseases. B-cells often make antibodies to auto antigens and things like that. So recently, six months ago, as the result of about six years worth of work, spun out of a Nobel Prize winner's lab and about $100 million worth of R&D, we saw, that's some good music man. We saw some of the most compelling preclinical data for in vivo CAR-T treatment of autoimmune diseases. It was by a company called Capstan, they were bought by AbbVie for like $2.1 billion.

</details>

**Speaker A**: 在 Lila，我们之前一直是在孤立地研究这三件事。所以大约六个月前，Lila 内部一个由两三个人组成的团队尝试看看我们在体内 CAR-T 方面能做些什么。我们之前一直在进行的工作是 mRNA 设计。就像大多数 RNA 药物一样，你能调节的最大旋钮就是表达峰值和表达持久性。也就是说，当你给某人注射疫苗或其他一些 mRNA 药物时，每单位 mRNA 能产生多少蛋白质？因此我们开发了一些超级 UTR（非翻译区），它们位于蛋白质编码区的两侧，决定了这些表达特性。与莫德纳（Moderna）和辉瑞（Pfizer）的参考序列相比，效果大概能达到 10 倍。

<details>
<summary>Original English</summary>

**Speaker A**: So at Lila, we had been working on all three of those things in isolation. So about six months ago, a team of two or three people inside of Lila tried to see what we could do in the in vivo CAR-T. And what we had been working on was mRNA design. Like most RNA medicines, the biggest knob that you can turn is expression peak and expression durability. So how many proteins do you get per unit of mRNA when you give someone a vaccine or some other mRNA medicine? So we have developed some monster UTRs, untranslated regions, which flank the protein coding region, which dictate those expression properties. Something like 10X, the references from Moderna and Pfizer’s reference sequences’s reference sequences’s reference sequences.

</details>

**Speaker A**: 在六个月的时间里，我们获得了非人灵长类动物的体内数据，其中 B 细胞的耗竭效果明显优于 Capstan 数据中展示的效果。而且其持久性，以及我们观察的所有特征都要好得多。拥有更多的 CAR 表达可能是改进 CAR-T 疗法最有效的方法之一。表达的受体数量决定了该 T 细胞在发现不良细胞后与其结合的概率。而且 T 细胞实际上就是连环杀手，它们会杀死一个细胞，然后去寻找下一个、再下一个。所以它们能持续杀戮多久，是由 CAR 表达的持久性决定的。

<details>
<summary>Original English</summary>

**Speaker A**: And over the course of six months, got to in vivo data in nonhuman primates, where B-cell depletion was significantly better than what was shown in the Capstan data. And the sort of like durability of that was also, all of the characteristics that we looked at were significantly better. Having more CAR expression is probably one of the most potent ways to improve a CAR-T therapy. The number of receptors that get expressed dictates how likely that T cell is to bind to the bad cell once it finds it. And T cells are literally serial killers and that they will kill a cell, then they'll go to the next one, the next one. And so how long they can do that is dictated by how durable the expression of the CAR is.

</details>

### 虚拟初创公司与科研范式的转变

**Speaker A**: 再说一次，我们不是一家 CAR-T 公司，我们是一群科学书呆子，我们喜欢做些很酷的事情。所以我们大约用了六个月的时间达到了那个概念验证点，再次强调，一路推进到了你可能会考虑为一项新的临床资产申请 IND 的程度。我们不会那样做，我们不会去开展临床试验，再说一次，那将牵涉到方方面面的事务。但是一些在 Lila 待了很久的人看到这本质上就像是一家两到三个全职员工的初创公司的运作方式。这里有几个拥有领域知识的科学家，模型加上平台的组合能够用总投资的 10%，在六个月的时间内完成原本需要五年的生物技术工作。

<details>
<summary>Original English</summary>

**Speaker A**: Again, we're not a CAR-T company, we're science nerds, we like to do cool stuff. So we got to that proof point in about six months, where again, all the way up to where you might think about filing an IND for a new clinical asset. We're not gonna do that, we're not gonna do a clinical trial, again, that would be all encompassing. But some folks who had been around Lila for a long time saw that as a way to do essentially like a two to three person FTE startup. Where there's a couple scientists who have domain knowledge and a combination of the model plus platform can do five years worth of biotech work over a six month period for 10% of the total investment.

</details>

**Speaker A**: 因此，我们现在考虑的许多商业合作关系本质上就像是这种“零全职员工”的初创公司模式。当有人带着一个想法来，他们说，如果市场上有一种 CAR-T 能够做到某些事情，如果它具有双特异性，或者具有其他这些特性，我知道那个东西能填补市场上的哪个空白。所以我们现在很多商业合作实际上就像是在 Lila 上运行的虚拟初创公司，有人带着一个非常明确的问题来，但他们不知道该如何实现。也许还有一些与靶点识别相关的事情等等，但他们能以极低的成本，在短得多的时间内有效地运行整个项目。

<details>
<summary>Original English</summary>

**Speaker A**: And so a lot of the commercial relationships we're thinking about now are essentially like the zero FTE startup model. Where someone comes with an idea, they say, if there was a CAR-T in the market that could buy and do things, if it was a buy specific, or if it had these other properties, I know the hole in the market that that thing would plug into. And so a lot of our commercial engagements are effectively virtual startups running on Lila now, where someone comes with a very well specified problem, they don't know how to get there. There may be some things related to target identification and things like that too, but they can effectively run that entire program over a much shorter amount of time at a fraction of the cost.

</details>

**Speaker B**: 所以那些就像是合作伙伴来找你，说我有一个想法，我不想建立一个实验室，我不想雇佣一个团队……我只想把事情做成。所以可能是一位大学的学者，他觉得“我有这个想法，我也做了一点点验证，我认为它行得通。我能和你们一起待六个月把这事做成吗？”

<details>
<summary>Original English</summary>

**Speaker B**: And so those are like a partner comes to you, says I have this idea, I don't wanna build a lab, I don't wanna hire a team, I wanna take their class. I just wanna get it done. So it could be some academic at a university that's like I have this idea, I kinda did a little bit of validation, I think it'll work. Can I sit with you guys for six months and make it work?

</details>

**Speaker A**: 是的，我觉得这是一种正确的思路。在合同层面，它的运作方式类似于有一个平台访问费，我们需要支付试剂费用、系统运行费用以及一些间接成本之类的，然后还会有一些上行收益分享，这是一个可扩展的模型。随着平台变得更好，我们的服务范围可以扩大，不再仅仅做几十个这样的项目，我们可以同时开发几百个甚至几千个这类的虚拟初创项目。这样我们在短期内有收入来支付账单，同时，对于那些决定和我们一起建设的人，我们也拥有共享潜在收益的合作伙伴关系。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I mean that's the right way to think about it. The way that like contractually it plays out is there's like a platform access fee, there's like we have to pay for reagents and running the system and then some overhead and stuff like that, and then there's like some upside sharing, that is a scalable model. Where we can service as the platform gets better, instead of doing dozens of those, we can do hundreds and then thousands of simultaneous kind of virtual startups being developed on the platform where we have revenue that helps pay the bills in the near term, but then we also have this upside partnership with folks who decide to build with us.

</details>

**Speaker B**: 这太令人惊叹了，因为我们现在看到的情况就是，人们越来越倾向于摆脱所有多余的基础设施，使用自动化技术，并专注于想法本身。

<details>
<summary>Original English</summary>

**Speaker B**: That's amazing because this is what we're seeing is that people are more and more pushing towards getting rid of all the extraneous infrastructure and using automation and focusing on the idea.

</details>

**Speaker A**: 我的想法是，我们大多数人进入科学领域是因为我们充满好奇心并想寻找答案。我受过计算机科学家的训练，我喜欢通过软件来解答问题。然而，如果我必须用二进制来编程，我的乐趣会大大减少。[笑声] 现在有了高级抽象，而且是越来越高级的抽象。过去只有 Python 和 Java，现在就像是 Cloud Code，它们能帮助我更快地寻找答案。这里的类比是，这就好像科学家们仍然在用二进制编程。他们有一个想要解答的问题，他们必须把它编译成一个实验方案，然后他们不得不去进行体力劳动，因为不断地移液而得关节炎，这等同于科学领域的“用二进制编程”。

<details>
<summary>Original English</summary>

**Speaker A**: I mean the way that I think about it is like most of us got into science because we're curious and wanna answer questions. I'm a computer scientist by training and I like to answer questions through software. However, if I had to program in binary, I would enjoy that significantly less. [laughter] There are high level abstractions, increasingly high level abstractions, used to just be Python and Java, now it's like Cloud Code, they help me answer questions faster. The analogy is that like scientists are still programming in binary, they have a question that they wanna answer, they have to just compile that down to an experimental protocol, then they have to go to manual labor and get arthritis by moving liquids from one, that's the equivalent of scientific programming in binary.

</details>

**Speaker A**: 所以我们在努力帮助科学家们攀登这个“抽象阶梯”。也许你的想法最终行不通，因为大多数临床试验都会失败，但如果你不必为了把所有环节安排妥当而同时进行体力劳动和某些脑力劳动，你至少能够实现“快速失败”。大多数临床试验都会失败，实际上只有 5% 到 8% 的临床试验能从 IND 阶段走向最终获批。因此，发现环节实际上并不是瓶颈所在。

<details>
<summary>Original English</summary>

**Speaker A**: And so we're trying to help scientists move up the abstraction ladder where what's the, maybe your idea isn't gonna work, most clinical trials fail, but you can at least get to failing fast if you don't have to do both the physical labor and also some of the intellectual labor to get all the pieces in the right place. Most clinical trials fail somewhere between 5% and 8% of clinical trials actually get from IND to approval. So the discovery is not actually the constraint.

</details>

### 应对监管与临床试验的挑战

**Speaker B**: 我很感兴趣，你刚才提到了某种类似“经济建模智能体”的东西，我记不清你具体管它叫什么了，但我觉得那似乎就是需要解决的问题。你是怎么看待这个的？关于临床试验的成功率。关于经济模型，或者总体的规模化？无论是在生物领域还是材料领域，通常都会有一个极其漫长的过程。一旦你有了你认为是最终版本的东西，比如 IND，或者是材料领域的开发候选物，在材料科学世界里通常还需要进行 10 年的临床或资格试验才能将其转化为产品。并且通常那里的瓶颈是关于规模化制造、监管、安全性等方面的问题，这些问题通常很难在早期就给出答案。所以每次你做这个的时候，你只能去……碰运气。

<details>
<summary>Original English</summary>

**Speaker B**: I was interested, you were talking about the sort of economic modeling agent, I can't remember what exactly you called it, but I mean that seems like the problem to solve, how do you think about this? The pro, the success rate of clinical trials. Well, the economic model, what scaling in general? For both bio and materials, oftentimes there's this huge process, once you have something which is, you consider final, like a IND, or a development candidate for material, there's still usually 10 years of clinical trials for qualification in the materials science world to just get that into a product. And oftentimes the bottlenecks there are things about scale manufacturing, about regulatory, about safety, things that are oftentimes just very hard to answer upfront. So every time you do this, you just have to three, no, roll a die.

</details>

**Speaker B**: 而人们处理这个问题的典型方法，本质上就是一种投资组合模式。从融资的角度来看，你唯一能赚钱的方法就是在具备一定风险校准水平的基础上扩大规模。听到你们能够具体地做这些事情真的很令人兴奋，但是它如何融入到更大的蓝图中呢？因为即便你立即解决了这些问题，它仍然只占整体问题的 10%。

<details>
<summary>Original English</summary>

**Speaker B**: And there is, the typical way people deal with this is, essentially a portfolio model, financing wise, it's very much a, the only way you can make money is if you scale with some level of risk calibration. It's really exciting to hear that you can do these things specifically, but how does it feed into the larger thing where even if you solve these problems, immediately, it's still only 10% of the problem.

</details>

**Speaker A**: 美国生物技术之所以输给中国生物技术，并不是因为创新的问题。这其中也有监管框架的原因，我们需要一种能够推动快速临床试验的框架。FDA 最近确实在这方面有所行动，这既涉及某些情况下你必须提交的临床前数据，同时也涉及到我们将如何运行和监控试验。因此，如果认为一家公司，甚至任何公司联合起来就能单方面改变这一现状，那简直是异想天开。这必须与监管机构协同完成。

<details>
<summary>Original English</summary>

**Speaker A**: The reason why US biotech is losing to Chinese biotech is not because of an innovation problem. There's a regulatory framework too, that has to go to enabling like fast clinical trials. The FDA has made motions towards that recently, both for the preclinical data that you have to submit in some cases, but also how we will run and monitor trials. So it'd be crazy to think that like one company could come, or even like any company combined could change that on their own. So it has to be done in tandem with the regulators.

</details>

**Speaker A**: 然而，在临床前成功概率上的微小提升却意义重大。从投资组合理论的角度来看，它让投资变得更具吸引力。这意味着，在预期中，药物能更快地送达患者手中，并且失败的案例更少。所以我可以说，这正是我们目前关注的领域：由一个能够从一百万种独特的 mRNA 设计中获益的系统所创造出的药物，能最大化那些已知可以转化为治疗益处的因素，这将有意义地推动临床前数据的表现……这仍然是，你知道，我想说，掷一个做了手脚的骰子总比掷一个公平的骰子好。所以我们只是在努力让这个骰子尽可能地向有利的一面倾斜。

<details>
<summary>Original English</summary>

**Speaker A**: However, the minor moves in preclinical probability of success matter a lot. From a portfolio theory perspective, it makes investment much more attractive. It means, in expectation medicines get to patients faster, a fewer of them fail. And so I would say like, that is the area that we're focusing on now is that a medicine created by a system that has had the benefit of in this case, a million unique mRNA designs to maximize things that are known to translate to therapeutic benefits will meaningfully move those pre, it's still, you know, I guess it would say it's better to throw a loaded die than it is a fair die. And so we're just trying to like make the die as loaded as possible.

</details>

**Speaker B**: 我想我的思路是，这也是我一直在思考的事情，那就是你如何带来……你知道，基本上就是成果转化，对吧？以及在材料领域的同等概念。无论我们怎么称呼它，我真的希望能看到这样一个模型：它能考虑到所有这些因素并进行推理，而且非常擅长说：“我正在将我的设计过滤出那些我认为能够挺过三期临床试验的选项。”

<details>
<summary>Original English</summary>

**Speaker B**: I guess my thinking, this is the thing that I think about constantly is how do you bring, you know, basically translation, right? And whatever the equivalent is in materials. So how we name that, that I really want to see a model that thinks about these are the factors that in reasons about and is very good at saying, I'm filtering my designs to the ones that I think are going to make it through phase three.

</details>

**Speaker A**: 嗯哼。太棒了。我妻子是生物技术领域的转化科学家。所以她经常提醒我，说你们应该去做用于转化科学的 AI。

<details>
<summary>Original English</summary>

**Speaker A**: Mm-hmm. Great. My wife is a translational scientist in biotech. So she reminds me very often, like you guys should be doing AI for translational science.

</details>

**Speaker B**: 是的。在某种意义上，我认为这会产生一些共鸣，特别是在材料和化学领域。你知道，我们的工具可以调用工艺工程模拟器，去计算出你需要什么直径的管道，以及你需要什么样的热交换器……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. In a sense, I think that sort of some of the echo, especially in the materials and chemistry, you know, our tools can call process engineering simulators and go figure out what pipe diameters and what heat exchangers you...

</details>

<!-- chunk 6/9 -->

### AI 在生物与材料科学领域的转化与规模化

**Speaker B**: 应该被使用，以便扩大流程规模，使其在经济上物有所值。因此，可能仍然需要，你知道，我不知道我们是否会启动过滤器，直到我们去测量它。但是，现在能够对下游将要发生的事情进行推理，这有点像转化型 AI 会做的事情，就是现在对将要产生重要影响的事情进行推理。因为，正如你早些时候所说，当你获得 IND（临床研究申请）时，你就会被锁定。在化学方面也是如此，你选择的分子、序列，当然还有你将给哪个群体使用，以及你将如何衡量成功，这些都是你之后要做出的选择，对吧？我不从事临床前研究，但在化学和材料方面，这正是我们现在试图通过验证器和我们可以访问的数据源来灌输的行为。要么因为有人思考过它们，要么因为物理学允许它，或者因为我们现在可以测量足够好的代理指标，从而告诉我们以后会发生什么。

<details>
<summary>Original English</summary>

**Speaker B**: should be using in order to scale up the process for the economics to be worth it. So it's still, maybe there is, you know, I don't know if we're going to crank up a filter until we go measure it. But the ability to reason now about the things that will come downstream, which is sort of a little bit what the translational sort of AI would do, is to reason now about sort of what's going to matter because I, when you said earlier, when you have the IND you're locked in and it's true on the chemistry side, the molecule, the sequence you've chosen, of course, which population you're going to give it to and how you're going to measure success, those choices you make afterwards, right? I don't work on the preclinical stuff, but on the chemistry and materials, that is precisely the type of behaviors we're trying to instill now for the, with the verifiers and the data sources that we can access either because somebody has thought about them, either because the physics allows it, or because we can measure good enough proxies now that tells us what's going to happen later.

</details>

**Speaker A**: 需要明确的是，所有这些事情都是我们在内部经常讨论的。我们已经在病态地扩大范围的边缘了，只想获得更多。但可以肯定的是，我们坚信，随着模型变得越来越聪明，随着它们摄取 ClinicalTrials.gov 的数据，随着我们与制药公司合作并获得访问那个“饼干罐”（宝贵数据）的权限，这些概率将会发生有意义的改变。在生物制造方面，通过获取良好的制造流程和扩大规模的流程，我们认为模型将能够在那里做出贡献。我们只是选择将我们大部分的商业和协作活动集中在我们认为现在可以解决的科学前沿，但我们的目标是超越这一界限。

<details>
<summary>Original English</summary>

**Speaker A**: And to be clear, like all those things are things that we talk about internally a lot. We're already on the verge of being pathologically over scoped. Just give me more. But absolutely, like the belief that we have is that as models get smarter, as they ingest ClinicalTrials.gov, as we partner with pharma companies and get access to that cookie jar, these probabilities will meaningfully change. On the biomanufacturing side, having access to, good manufacturing processes, scale up processes too, we think the models will be able to contribute there. We've just chose to focus a lot of our commercial and collaborative activity on the sort of like frontier of science that we think we can address now, but the goal is to push past that.

</details>

**Interviewer**: 如果我可以总结的话，这有点像是一个工具调用（tool call）。

<details>
<summary>Original English</summary>

**Interviewer**: If I may summarize, it's kind of like it's a tool call.

</details>

**Speaker A**: 是的，全都是 token，全都是工具调用。Token 和工具调用就是你所需要的一切。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, it's all tokens, it's all tool call. Tokens and tool calls are all you need.

</details>

**Speaker B**: 但同样地，推理机制，也许你之前提到过那位治疗了——你知道的，白细胞介素-6（IL-6），IL-6，你提到的那个——那位医生从生活经验和阅读文献的结合中学到了这些。而我们，既然我们相信“广度带来深度”的论点，我们将通过做更多我们未知的事情来更好地掌握这些能力。在许多可能完全不同的现实世界中，在那次病例里治疗 Emily Whitehead 的并不是那位医生，而 CAR-T 疗法看起来可能，它可能只是 Eroom 定律里的又一块墓碑，你知道，就是又一款失败的药物。所以我确实认为，由于那个人碰巧在场，成功的概率从大约 2% 飙升到了 98%。因此，如果我们能将这一点系统地运作起来，那么你将会显著改变很多事情的成功概率。

<details>
<summary>Original English</summary>

**Speaker B**: But also the reasoning mechanisms that maybe you mentioned for that doctor that treated, you know, the aisle, the aisle six, the aisle six, the aisle six, that you mentioned, well that person had learned that from, you know, a combination of lived experience and reading the literature. And we get, since we believe our thesis that the breadth gives us depth, we will get better at those things by doing more of the things we don't know. And in so many counterfactual worlds, that doctor was not the one treating Emily Whitehead in that case, and Carti may have looked like, it may have been yet another gravestone in E-room's law, you know, for, you know, yet another failed drug. So I do think that like, that went from like a 2% success probability to a 98%, just because that person happened to be in the room. And so if we could just operationalize that, again, like the, you're gonna move a lot of probabilities.

</details>

**Speaker A**: 是的，所以那是一个很好的例子，说明只要拥有非常广泛的科学信息知识就能发挥巨大的作用。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, so that's a good example of where just having really broad knowledge of scientific information.

</details>

**Speaker B**: 这简直就像是 Google 一样。因为在那之前，它仅仅被用于治疗小儿关节炎，就像医学中另一个非常利基（小众）的领域。

<details>
<summary>Original English</summary>

**Speaker B**: So that's like, that's almost like Google. Because that was only being used in pediatric arthritis, like another like very niche area of medicine.

</details>

### AI 的开放性与 Lila 的实验室自动化

**Interviewer**: 我明白了。那么，在你们的团队中有 Ken Stanley，他曾出版过著名的《为什么伟大不能被计划》一书，并且在机器学习研究中非常推崇开放性（open-endedness）和意外发现（serendipity）。那么在 Lila，开放性扮演着怎样的角色呢？

<details>
<summary>Original English</summary>

**Interviewer**: I see. So you have Ken Stanley and your team, famously wrote the book, "Why Greatness Cannot Be Planned," and is very big on open-endedness and serendipity in ML research. So what is the role of open-endedness at Lila?

</details>

**Speaker A**: 哦，是的，首先，Ken 非常了不起。对于那些不了解的人来说，Ken 开创了机器学习和 AI 中一个名为“开放性”的领域，我将其视为机器的创造力。我们如何让模型进行开放式的探索，并同时对什么是“有趣”的事情、应该沿着哪些方向深入有品味上的感知。所以，如果你仅仅是一个很会考试的模型，你是不可能拥有科学超级智能的。因此，如果你思考一下强化学习正在做什么，即使在大规模下，它也只是在以一种无情的、像瓦肯人（Vulcan）一样的、类似斯波克（Spock）的方式回答问题。但你可能只在有限的情况下，才会认为这个模型具有极高的创造力。因此，Ken 在 Lila 创建或组建了一个开放性团队，以应对推理挑战的外层循环或元级别问题。也就是说，我们如何让我们的模型不仅能够回答难题，还能在第一时间提出有趣的问题。这就是 Ken 的核心使命。在过去的几个月里，他一直在建立一个世界级的团队，现在他们正在“厨房”里研发。我认为到今年年底，我们将能从 Ken 的团队那里分享一些很酷的东西。所以，我们现在要来看一段实验室的视频。这将展示一些不同的东西。

<details>
<summary>Original English</summary>

**Speaker A**: Oh yeah, one, like Ken is awesome. So for those of you who don't know, Ken pioneered an area of machine learning and AI called open-endedness, which I think of as machine creativity. Like how do we get models to do open-ended exploration and also like have a sense of taste about what's interesting, what things should go down. So you can't have scientific superintelligence if you're just a good test taker. So like, if you think about what reinforcement learning is doing, even at scale, it's answering questions in kind of like a ruthlessly Vulcan-esque, like, you know, Spock kind of way. But you probably only in like limited ways would think of that model as being supremely creative. And so Ken has created or built and open-endedness team at Lila to sort of take the outer loop or the meta part of that reasoning challenge on. So how can we get our models to not only be able to answer tough questions, but ask interesting questions in the first place. And so that's really Ken's mandate. He's been building like a world-class team over the last like several months, and they're in the kitchen cooking now. And I think by the end of this year, we'll have some cool stuff from Ken's group to share. So we're going to hop into a video here of the lab. This is going to show a couple of different things.

</details>

**Interviewer**: 好的，这可能是一台剥膜机（peeler）或封膜机（sealer）。

<details>
<summary>Original English</summary>

**Interviewer**: All right, so that's probably a peeler or a sealer.

</details>

**Speaker A**: 所以当你在仪器之间移动微孔板时，显然里面会有液体，大部分生物实验都涉及到液体。所以你要在上面贴上这些贴纸。这展示的就是微孔板被密封的过程。好的，我们来看这里。它正在拿起一个——

<details>
<summary>Original English</summary>

**Speaker A**: So when you move plates from instrument to instrument, obviously there's liquid in it, most of the biology is wet. So you put these stickers on it. So that was a plate being sealed. All right, so here we go here. It's picking up a-

</details>

**Interviewer**: 是的，所以这是在液体处理器的内部。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, so this is inside of a liquid handler.

</details>

**Speaker A**: 让我继续，我们等镜头切换到更宽的视角，这样你就可以看到 PCI 总线，并看到一些机器人设备。所以，液体处理器在另一个镜头里。这就是这里的平面电机系统，微孔板会在其上磁悬浮。这是 PCI 总线，传输层连接了所有的仪器。你可以看到那些实验台，所有的仪器都放置在那里。机械臂将其拿起，现在要将它转移到另一块微孔板上，以进入下一个步骤。这里你必须做一点流量控制的工作。就像它们实际上会在某个地方停靠一段时间，以等待拥堵消散。

<details>
<summary>Original English</summary>

**Speaker A**: Let me go, we'll wait till it gets to a wider shot here so that you can see the PCI bus and see some of the robotics. So the liquid handlers are on the other shot. So this is the planar motor system here where the plate magnetically levitates. This is the PCI bus where the transport layer connects all the instruments. You can see benches there where all the instruments sit. A robot arm picks it up, is now going to transfer it to a different plate to go on to the next. There's a little bit of a traffic control thing that you have to do here. Like they actually will go and park for a while while congestion clears.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Speaker A**: 这是 PCI 总线的一个长镜头。同样，所有这些都是完全受控的，所有这些都是全自动的。

<details>
<summary>Original English</summary>

**Speaker A**: And here's a long shot of the PCI bus. And again, like all of that's fully controlled, all of that's fully automatic.

</details>

### 从自动化到软硬件堆栈的垂直整合

**Speaker B**: 这是一个材料科学的例子。是的，这是一个物理科学的例子，它带我们回到了关于扩容规模的那一点。在这里，它正在以放大的尺寸规格制造我们的氢催化剂。那是一种含有材料纳米颗粒的墨水。那是一个旋涂机，正如你可以从它旋转托盘的方式中猜到的那样。然后，这个机器人处理器四处移动，测试小块的催化剂。这种看起来很棒的、带有 90 年代紫色霓虹灯氛围的设备。这被称为磁控溅射机，在其中我们让原子从源头飞出，并沉积在腔室的另一侧，形成一层极薄的原子薄膜。通过这三四个源头上有什么，我们可以制造出任意元素的混合物。我们只需将它们汽化，让它们飞越腔室，并制造出这些极其节省材料的漂亮薄膜。我们可以用非常非常少的材料来完成这项工作。它是我们在催化、腐蚀、力学性能等众多应用中快速实现“设计、制造、测试”以及“设计、测试”循环的主力设备之一。有很多东西，你都可以在这种非常方便的形态下进行测试。

<details>
<summary>Original English</summary>

**Speaker B**: And this is a materials science example. This is a physical science example, yeah, where it takes us back to the scaling point. Here it's making our hydrogen catalysts in a scaled up form factor. That's an ink that contains nanoparticles of the material. That's a spin coater, as you can guess from the fact that it spins the plates. And then this robotic handler moving around, little piece of catalyst to test. And this nice looking purple 90s neon vibe. This is called a magnetron sputtering machine where we make atoms fly from a source and deposit on the other side of the chamber in a very thin atomic film where we can make arbitrary mixtures of elements on what's on the three or four sources. We just vaporize them and make them fly over the chamber and make these nice thin films that are very material efficient. We can do this with very, very little material. And it's one of the work horses for us to design, test, design, make, test fast in many applications, in catalysis, in corrosion, in mechanical properties. Many things you can test in this sort of very convenient form factor.

</details>

**Interviewer**: 液体处理器和其中一些机器，大部分是现成产品（off-the-shelf）。然后你们拥有这个，你们设计出了这种可以适配很多这类机器的通用尺寸规格，既适用于材料科学，也适用于生物科学。

<details>
<summary>Original English</summary>

**Interviewer**: The liquid handlers and some of those machines, those are kind of off the shelf mostly. And then you have this, you've come up with this sort of form factor that works for lots of those machines, both for material and for bio.

</details>

**Speaker A**: 量子点（Quantum Dot）是这两者结合的一个好例子。它实际上是一个液体处理器，我们对其进行了重新改造，以用于量子点的合成与设计。我认为这说明了，仅凭 20、30、40、50 台仪器，你就可以走得很远。关键的能力在于，它们必须被放置在模型能够使用它们的平台上。我认为我来到 Lila 之后，一个让我大开眼界的事情是（因为我来 Lila 之前从未真正意义上接触过实验室自动化），它并不是我所期望的那种自动化。许多自动化都是“点式自动化（point automation）”，也就是在液体处理器的侧面连着一个平板电脑，你可以通过它输入一个宏。那些设备在设计之初并没有考虑到，或者有时甚至是刻意被设计成不与其他设备通信的。因此，我们做了大量工作，我甚至开玩笑说，我们收集了世界上数量最庞大的、在生物学领域“保修失效”的设备。因为为了获得对许多此类仪器的底层细粒度控制，并让它们互相通信，我们编写了我们自己定制的驱动程序和定制固件。所以这段视频很酷，因为你可以看到磁悬浮的托盘。但你看不到的是那些像把所有东西缝合在一起的定制软件封装。其中很多问题归根结底都是非常困难的软硬件接口挑战。有些机器甚至现在仍在运行 Windows 95 系统。所以，想象一下你如何实现它的自动化。实际上，我们正在用一个视觉语言模型（vision language model）来控制一台运行 Windows 95 的机器，因为那是使其自动化的唯一方法。

<details>
<summary>Original English</summary>

**Speaker A**: Quantum Dot is a good example of the combination of the two. It's actually a liquid handler that we've repurposed for Quantum Dot synthesis and design. And that, I think that that speaks to like, you can get very far with 20, 30, 40, 50 instruments. The ability, they just have to be on platforms that the model can use them. I think that a big eye opening thing for me coming into Lila, because I wasn't in lab automation like in any meaningful way before coming to Lila, is it's not the automation that I was hoping for. Like a lot of automation is point automation, where there is a tablet attached to the side of a liquid handler where you can enter a macro. That device is not meant and then sometimes purposely designed not to talk to other things. And so a lot of what we have done has been to, I kind of joke that we have the world's largest collection of voided warranties in biology, because we have written our own custom drivers, our own custom firmware, to get sort of low level granular control of a lot of these instruments and make them talk to each other. So the video is cool because you see magnetically levitating plates. What you don't see is like the custom software wrapper that like stitches all that together. And a lot of this comes down to like really hard software, hardware interface challenges. Some of the machines literally still run Windows 95. And so think about how you automate that. Like we actually have a vision language model controlling a Windows 95 machine, because that's the only way to automate it.

</details>

**Interviewer**: 我刚想开个玩笑，说是不是用一根机械手指去按按钮。

<details>
<summary>Original English</summary>

**Interviewer**: I was just gonna joke about a mechanical finger pressing buttons.

</details>

**Speaker A**: 是啊，你在开玩笑，但不，我们真的这么干了。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, you joke, but no, we did that.

</details>

**Speaker B**: 等一下，我们确实使用了一个机器人去按动机器侧面的 iPad。

<details>
<summary>Original English</summary>

**Speaker B**: Wait, we actually did use a robot to push the iPad on the side of the thing.

</details>

**Speaker A**: 我认为这里需要指出的另一点是，这仍然是“为人制造”的自动化设备。比如那些仪器被放置在大约齐胸高的实验台上，因为这预设了有人需要伸手进去维修它，或者添加试剂。因此，这仅仅是 v0 或 v0.5 版本，是我们认为未来实验室自动化的样子。因为我们刚刚决定进行垂直整合并拥有软硬件堆栈，所以 V2 版本看起来会与此大不相同，那时我们将能够整合一切。这在材料科学领域已经发生，因为那些能力根本就不存在。我们通常会从 XY 坐标系的角度来考虑实验室空间。随着我们的整合，我们将引入一个 Z 轴的维度，因为我们将能够把设备堆叠起来。再说一次，“单位体积的 token 数量”将是我们届时思考的指标。但我们认为，未来的实验室不应该是为人能够轻松走进去而建造的。它应该感觉像一个数据中心，在那里你走进去看到的是一排排服务器机架。后面可能会留出空间让应急小推车进去维修节点，但它应该尽可能地密集排列，并且在能源方面尽可能地高效。所以，回答你的问题，我们现在正在使用商用现成产品，因为从它起步是有意义的，但随着时间的推移，这些设备的形态尺寸几乎肯定会发生很大变化。

<details>
<summary>Original English</summary>

**Speaker A**: I think the other thing to like, the other thing to call it here is, this is still automation made for people. Like the instruments sit on benches, which are approximately chest high because there's the assumption that someone needs to reach in there to service it or to fill the reagents. So this is the like v0, v0. 5, what we think lab automation will look like. And because we've just decided to vertically integrate and own the hardware software stack, the V2 will look very different than this, where we'll be able to integrate things. This is happening already on materials sciences because those capabilities just don't exist. And we often think about labs in terms of like their XY coordinates. As we integrate, like we'll have like a Z component too, because we'll be able to stack things. And again, tokens per like unit volume is like what we'll be thinking about then. But we think that like the lab of the future should not be made for people to easily walk into it. It should feel like a data center, where you go and you see the rows of server racks. There's room for like a crash cart behind it to service the nodes, but it should be as densely packed as possible and also as energy efficient as possible and things like that. So yeah, so to answer your question, we're using commodity things now because it makes sense to get started, but over time, almost surely the form factors of those will change quite a bit.

</details>

**Interviewer**: 我明白了。我只是有点惊讶你们能想出这种标准尺寸的托盘，它几乎能在很大比例上满足你们的各种问题需求。

<details>
<summary>Original English</summary>

**Interviewer**: I see, I'm just a little surprised that you can come up with this common size of tray that kind of matches your needs for a good percentage of your problems.

</details>

**Speaker A**: 这其实是逆向推导的结果。96 孔板（96 well plates）是实验室自动化中实验的最小原子单元。因此，我们也针对材料科学开发了 96 孔板规格。并不是所有的东西都适合这种尺寸，但同样地，采用 96 孔或 384 孔板格式所能带来的覆盖率是极高的。

<details>
<summary>Original English</summary>

**Speaker A**: Well, it's just working backwards. 96 well plates are the like atomic unit of experimentation in lab automation. And so we now do 96 well form factors for materials sciences as a result. Not everything fits into that form factor, but again, the coverage that you get from adopting a 96 well or 384 well plate format.

</details>

**Interviewer**: 二八定律（80/20 法则）。

<details>
<summary>Original English</summary>

**Interviewer**: 80 20.

</details>

**Speaker A**: 80 20 法则，完全正确。

<details>
<summary>Original English</summary>

**Speaker A**: 80 20, exactly.

</details>

**Speaker B**: 是的，我的意思是，你能看到一些沉积材料的块头比较大。所以我们仍然使用这种孔板的形状来承载和移动它们，但相应的样本数量，对吧，你所拥有的数量会变少。我想其中一些可能是比如 12 个，或者 4 乘 3 的规格。这也把我带回到你早些时候关注的一点，关于规模化，以及当你扩大规模时，你的项目是如何变得不同的。我认为公司集体正在期待解决的一个问题是，对一个数据中心规模大小的 AI 科学工厂进行编排和调度，对吧？当它进行全面实验时，你可以同时运行。你要如何思考移动所有这些样本的物流与编排，以及将所有这些仪器连接起来，从而为我们的客户创造最大价值，也为我们的模型提供最多的信息。这就是最令人兴奋的部分。它最后看起来很可能会大不相同。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I mean, you can see some of those words, the pieces of deposited material were bigger. So we still use the plate shape to carry them over, but then the number of samples, right? That you have them are smaller. I think some of them are like maybe 12, four times three. This takes me also to a point you focused earlier about scaling and sort of how, when you scale your programs are different and a problem I think we're looking forward to collectively at the company is the orchestration and the scheduling of a data center size AI science factory, right? When it's a full experiments, you could rank concurrently. How are you going to think about the, you know, the logistics and the orchestration of moving all these samples and interfacing all these instruments to create sort of the maximum value for our customers and maximum information for our model. And that's exciting part. That probably is going to look very different

</details>

<!-- chunk 7/9 -->

### 编排与规模扩展 (Orchestration and Scaling)

**Speaker A**: 这与我们现在思考的其他一些问题有关。关于 Rafa 所说的话，我们的想法是，在其之上进行编排，就像一个 slurm 队列或类似的东西，让你能在全局上最大化你现有系统的吞吐量。但同样地，利用相同的抽象概念来思考吞吐量、调度和编排。而且随着系统变得复杂或者规模变大，最大化这种吞吐量的复杂性也会随之增加。所以如果你是一个，你知道的，CSP（约束满足问题 Constraint Satisfaction Problem）的书呆子，我们这里有最酷的问题之一值得你去思考。你现在考虑的规模扩展，是像建立那一个集群，然后用饼干模具那样直接复制粘贴（cookie cutter），还是说更像是我把所有的液体处理仪和所有的任何自旋编码器等等，放置在实验室的不同区域或其他地方？

<details>
<summary>Original English</summary>

**Speaker A**: from some of the other problems we're thinking about now. What we think about Rafa said is like orchestration on top of that is like a slurm queue or something like that, that lets you globally maximize throughput of the system that you have. But again, using those same abstractions to think about throughput scheduling orchestration. And as the system gets complex or it gets larger, the complexity and maximizing that throughput. So if you're like a, you know, a CSP, a constraint satisfaction problem nerd, we have like one of the coolest ones to think about. Are you thinking about scaling as like that one cluster and then you just cookie cutter that, or is it like I have all of my liquid handlers and all of my whatever spin coders and yeah, over in different parts of the lab or something.

</details>

**Speaker B**: 我的意思是，目前我们拥有的本质上是一个巨大的全连接图（fully connected graph）。而这种模式是无法无限扩展的。仅仅是使用的一些材料本身，就会散发出有害的烟雾。出于安全原因，那部分必须被隔离起来。我不清楚未来的科学集群的确切配置布局会是什么样子。但我认为，它上面的仪器数量可能比你猜测所需要的要少。你知道，可能是几百个，或者几千个。但我们在思考它的扩展时，确实采用了与你思考扩展数据中心相同的方式。那就是，它是一栋多层建筑，占据数百万平方英尺的面积。正如他们所说，这就像一个无人工厂（lights out facility）。它就像是 24/7 全天候运行，实时生成数据。而且你会希望它拥有你对数据中心所期望的相同的正常运行时间（uptime）。当然，这是非常难做到的。这是一件极其困难的事情。但这是我们正试图从中逆推出来的终点。在通往那个终点的路上，你需要解决哪些问题？

<details>
<summary>Original English</summary>

**Speaker B**: I mean, currently what we have essentially is one big fully connected graph. And like that won't scale indefinitely. Just some of the material stuff use, throw off hazardous fumes. And that's isolated for safety reasons. I don't know exactly what the exact configuration layout of the scientific cluster of the future looks like. But I think that it will probably have fewer instruments on it than like you might guess you would need. You know, hundreds, maybe thousands. But we do think about scaling it in the same way that you would think about scaling a data center. And that it's a multi-level building, occupies millions of square feet. And it's like a lights out facility as they say. It's like running 24 seven generating data in real time. And you would want the same uptime you would expect of a data center. Now that's very hard to do. That's like an insanely hard thing to do. But that's the end point that we're trying to work backwards from. What problems do you need to solve on the way to that end point?

</details>

**Speaker A**: 不过，这又回到了我之前关于你们实验运行时间的问题。因为“扩展规模”意味着不同的东西。其中之一是实验设计，它在本质上可以扩展，但可能要以信噪比（signal noise ratio）或一些其他理念为代价。但要以一定的成本，快速且高效地获取广泛的数据。或者，“扩展规模”是指降低吞吐量，但仅仅是进行疯狂的并行化。所以总的来说，我会把这些当作两套不同的问题来处理。我不认为相同的策略对它们都能普遍奏效。那么作为一名科学家，哪种类型的规模扩展对你来说更重要呢？

<details>
<summary>Original English</summary>

**Speaker A**: This goes back to my previous question though about the runtime of your experiments too. Because scaling means different things. And one of them is experimental design, which intrinsically scales, but maybe at the cost of signal noise ratio or some other idea. But getting broad data quickly and efficiently at some cost. Or scaling is lower throughput, but just paralyzing wildly. So in general, I would approach those as two different sets of problems. I don't think that the same strategy really works for them in general. So what type of scaling is more important for you as a scientist?

</details>

**Speaker B**: 我会说，一轮接一轮（round over round）的迭代比那种广泛的、高度多路复用的（hugely multiplexed）、含有高噪音的方式更重要。所以迭代时间（iteration time）真的是唯一最简单的指标。

<details>
<summary>Original English</summary>

**Speaker B**: I would say round over round iteration is more important than a broad, hugely multiplexed, highly noisy kind of thing. So iteration time is really the single easiest thing.

</details>

**Speaker A**: 是的。是的。那么这会限制你们想要专注的领域吗？现在你是否认为，如果我们准备尝试解决一个新问题，我们是会问：我们能否仅通过快速迭代来解决这个问题，还是说，也许答案是你通过大规模地多路复用某个东西来进行扩展，尽管其周转时间（turnaround）可能长达一个月？但是，分析和多路复用在某种程度上是不同的，对吧？有时——

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Yeah. So does that limit the domains that you want to focus on? Now do you think if we are going to try to tackle a new problem, do we ask can we just solve this problem with fast iteration versus something where maybe the answer is will you scale up by massively multiplexing something, with like month long turnaround? But analyzing a multiplexing are somewhat different, right? Sometimes--

</details>

**Speaker B**: 是的，那是另一点。我会说，池化（pooled）——我们喜欢池化方法。是的。我们喜欢池化。因为你可以既快速又广泛地获取数据。所以这正是池化方法的设计初衷。池化是指像 DNA 编码文库（DNA encoded libraries）这样的东西，在其中你使用——里面有一堆乱七八糟的东西（crap）。然后你可以在做完实验之后，把那些无用的东西筛选掉。不知何故，这种检测的形式允许你在同一时间里投入一千个、一百万个甚至十亿个实验，并且检测的设置方式让读取结果能够直接挑选出赢家。所以你在一个板子上尝试了一百万种东西，然后你得到了 1,000 个赢家的一千个读取结果。这就是多路复用。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, that's the other point. I would say pulled-- we love pulled. Yeah. Pooled, we love. Because you get fast and broad. So it's what is pulled made for. Pooled are things like DNA encoded libraries, where you use-- G12 has a bunch of crap in it. Then you can sort out the crap after you do the experiment. Somehow the form of the assay allows you to throw 1,000 or a million or a billion experiments in time, and the way the assay is set up, the readout picks the winner. So you try a million things in one plate, and you get one readout of 1,000 readouts of 1,000 winners. Multiplexed.

</details>

### 高通量与新仪器 (High Throughput and New Instruments)

**Speaker A**: 有个小笑话是说，所有那些被称为有价值的技术（value tech），只不过是把你想要的任何读取结果映射到 NGS（下一代测序 Next-Generation Sequencing）测序上罢了。

<details>
<summary>Original English</summary>

**Speaker A**: There's a little joke that all value tech is just mapping whatever readout you want to an NGS sequencing.

</details>

**Speaker B**: 我的意思是，是的。贴上标签进行多路复用。就这么办。你可以获得大量的数据。另一种观点是，如果一个领域的标准时间是一个月，而我们只需要四天，那么四天的学习周期就是惊人的，因为它将真正推动该领域那部分的发展。这正是我们的自动化工程师和团队在思考其他测量事物方式的地方。在冷却剂（coolants）和催化（catalysis）领域，有些地方我们仅仅是制造了不同的仪器来测量不同的属性，这就使我们的响应速度快了一千倍。例如，在吸附作用（sorption）中——我可以给大家稍微介绍一下——在气体吸附中，人们通常会进行测量。对于我提到的那些从空气中吸出二氧化碳的 MOF 和 COF 材料，他们会对一定量的气体进行加压。通过高中的理想气体定律，你知道的，你就知道你在这个小盒子里放了多少气体。然后你等待气体被材料吸收。你检查压力。根据压力的差异，你就知道有多少气体进入了该材料。然后你再次提高压力，看看又多进去了多少。如果这听起来效率很低，那是因为它确实非常慢。这叫做 BET。每个样本大约需要一天的时间。而且它非常难以并行化，因为那需要另一条气体管线和另一个罐子。或者，你可以从其他那些可并行化的仪器那里进行所有类型的代理测量（proxy measurements）。这就是我们现在在实验室里构建的东西。我们不是在测量压力，而是在测量我们关心的另一个属性。这是关于压力实际会告诉我们的东西的某种读数。但我们可以在大约一小时内完成 96 孔板中对 96 个金属有机框架（MOF）的测试。所以这大约快了 2,500 倍。因此，在这里有一些发挥独创性的空间，或者只是——而且现在与其他读取方式相比，我们仍然是慢的，对吧？电化学领域的其他东西也许我们可以在一分钟内完成。但现在我们已经比我们过去做事的方式快了大约 1,000 倍。我认为，针对你问题的答案，在一定程度上也取决于我们认为模型是从零起点（dead start）开始，还是从步行，抑或是从慢跑开始。所以如果某个领域是我们关心的，有某个问题，很明显我们所使用的模型在这方面几乎是零知识基础。那么我们可能更倾向于用一个庞大而缓慢的过程把它引入进去。如果我们认为它在那方面已经相对有能力了，那么我们将非常坚持快速串行、快速迭代的循环。所以我们两者都会做。我们打赌的是，随着模型性能的提高，样本效率也会上升。因此，你从一轮接一轮的实验中获得的“复利”，将超过你从一个庞大的、嘈杂的、广泛的数据集中获得的回报。

<details>
<summary>Original English</summary>

**Speaker B**: I mean, yes. Tag it multiplex. There you go. You can get lots of data. The other argument would be that if the standard for a field is a month and it's going to take us four days, a four-day learning cycle is amazing, because it's really going to move the needle for that part of the field. This is where our automation engineers and our teams are thinking about other ways of measuring things. And in coolants and in catalysis, there are places where we just made different instruments that measure a different property that turns our response a thousand times faster. For instance, in sorption-- I can tell you folks a little bit-- in gas sorption, people typically measure. They pressurize an amount of gas for the MOF and COF materials I was talking about, sucking CO2 out of the air. You know how much from the ideal gas law, if you remember high school, you know how much gas you put in the little box. And then you wait for the gas to be absorbed in the material. You check the pressure. And from the difference in pressure, you know how much went into the thing. Then you up the pressure again, and you see how much extra went. And if this sounds low, it's because it's very slow. It's called BET. This is about a day per sample. And it's very tough to parallelize because there's another gas line, another canister. Or you can take all the types of proxy measurements from other instruments that are parallelizable. And that's something we built in the lab now. Instead of measuring pressure, we're measuring another property we care about. That is a readout for what actually pressure will tell us. But we can do 96 well plates for 96 metal-organic frameworks in like an hour. So it's like maybe 2,500 times faster. So this is a place where there's a little bit of room for ingenuity or just-- and now we're still slow compared to other readouts, right? Other things in electrochemistry maybe we can do in a minute. But now we're sort of 1,000 times faster than the way we were doing it. I think the answer to your question also, too, depends on how much we think the model is starting from a dead start versus a walk versus a jog. So if there's some area that we care about, some question, it's clear there's like zero knowledge in the way to the base-- in the model that we're using. Then we may prefer a big slow thing to move it in. If we think that it's already relatively competent in that, then we would vastly persevere the rapid serial fast-iteration cycle. So we will do both. The bet is that as the model performance improves, the sample efficiency goes up. And therefore, the compound interest that you get from round over round experimentation will outweigh that you would get from a big, noisy, broad data set.

</details>

**Speaker A**: 你有任何担忧吗？这只是——我只是在这里大声思考。但你是否会担心，你很快就会把你能使用这些方法解决的问题给穷尽（saturate）了——

<details>
<summary>Original English</summary>

**Speaker A**: Do you have any concern? This is-- I'm just thinking out loud here. But do you have concern that you're going to quickly sort of saturate the problems that you can solve using--

</details>

**Speaker B**: 是担忧，或者说是希望。[笑声]

<details>
<summary>Original English</summary>

**Speaker B**: Concern or hope. [laughter]

</details>

**Speaker A**: 像担忧又像是希望，也许吧。但也许你们把这些系统都部署到位了。而现在，因为它们是新事物，所以存在大量的绿地（green field，指未开发的新领域）。你们可以去解决所有这些适合高通量实验的问题。你们也许会这样干上几年。然后突然之间，一切都不同了。然后你们不得不完全重组你们那价值无数美元的基础设施。

<details>
<summary>Original English</summary>

**Speaker A**: Like concern and hope, maybe. But maybe you have these systems that you're putting in place. And right now, because they're new, then there's a lot of green field. You can go and tackle all these problems that are amenable to high throughput experimentation. You're going to do that for a couple of years, maybe. And then all of a sudden, now everything is different. And you have to completely retool your gazillion dollar base.

</details>

**Speaker B**: 明确地说，我希望那是真的。所以我希望我们在两年后不需要再去测量结合解离常数（binding KD）。我们不用再去做了。对此我感到非常兴奋。因为模型已经基本掌握了结合动力学（binding kinetics）。所以你可以认为，最终会达到模型知道如何做那件事的程度。让我们再回到 PCI 总线（PCI bus）的例子。所以我们实际想要做的是减少将新仪器接入平台所需的时间。所以你希望那感觉很像插上一个 USB 设备。我不知道你们大家有多大年纪了。在我小时候，如果你拿到一个新设备。你会在软盘里得到它的驱动程序。你必须撞破头才能把驱动程序安装好。而两天后，你的打印机也仅仅是勉强能用而已。所以那就像——

<details>
<summary>Original English</summary>

**Speaker B**: I hope that that is true, to be clear. So I hope that we don't have to measure a binding KD again in two years. We didn't have to do that. I'm very pumped about that. Because the model has essentially mastered binding kinetics. So you would think that eventually you get to the point where the model knows how to do that. Let's go back to the PCI bus again. So what we actually want to do is to reduce the amount of time it takes to bring a new instrument on platform. So you want that to feel a lot like a USB. I don't know how old you guys. When I was a kid, you got a new device. You got the drivers on a floppy disk. You had to beat your head against the wall to get the driver to install. And two days later, your printer only kind of works. So that's kind of what--

</details>

**Speaker A**: 是的，完全正确。如果你是一个核心的 Linux 玩家，你今天依然能体会到那种经历。音频驱动程序还是不工作。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, exactly. And if you're a Linux hardcore person, you're going to still leave that experience today. Audio driver still doesn't work.

</details>

### 统一平台与未来愿景 (Unified Platforms and Future Vision)

**Speaker B**: 这就是现在在生物学和物理科学领域，把一台新仪器接入平台时的感觉，我们依然处在“用软盘里的驱动程序看手册尝试让它工作”的阶段。所以再一次地，我们希望统一的平台能够实现的一件事就是，仪器的上线时间（onboarding time）最终降到零，你只要有制造商提供的规格说明（spec），模型读取它，正确的 API 就会被抽象出来。我们正在与一些仪器供应商合作，以使这个过程变得更容易。但我认为，我们思考如何调节一个系统的很多方式，都受限于我们现在是如何做的。所以我们再次希望，统一的平台能够使两年后接入新仪器的过程，从一项耗时 30 天的任务变成一项只需 30 分钟的任务。这也是一件很难做到的事情。可能最后证明这是错的。我们可能做不到。但那是我们所指引的未来方向。在当前，我们实际上已经可以非常快地替换现有的仪器了。所以如果我们需要把 Hamilton 替换成不同的液体处理仪，这种替换实际上已经能非常快地完成了。因此我们确实有合理的信念认为，随着时间的推移，接入仪器会变得更快、更好、更可靠。再次强调，我们不想在 2036 年还在做 2026 年的科学。所以我们希望其中一些仪器被淘汰，或者说我们测量事物的方式发生改变。否则，我们和其他所有人对未来十年的进步速度所做的许多假设，就会被证明是错误的。它们确实错了。而我们现在已经从仪器供应商那里获益良多了。

<details>
<summary>Original English</summary>

**Speaker B**: So that is what it's like to bring a new instrument on platform in biology and physical sciences now, is that we're in the driver on a floppy disk in the manual to try to get to work. So again, one of the things that we hope a unified platform enables is instrument onboarding time eventually goes to zero, where you have the spec from the manufacturer. The model reads it. The right APIs get abstracted. We're working with some instrument vendors to make this process easier. But I think a lot of the way that we think about modulating a system is conditioned on how we do it now. And so again, we're hoping that a unified platform makes onboarding instrument two years from now, a 30-minute exercise versus a 30-day exercise. Again, it's a hard thing to do. It could be wrong. We might not be able to do it. But that's the future that we're pointing to, where currently, we actually can swap out existing instruments very quickly. So if we need to replace a Hamilton with a different liquid handler, that swap actually happens very quickly already. And so we do have some reasonable belief that onboarding instruments will get faster, better, more reliable over time. And again, we don't want to be doing 2026 science in 2036. And so we hope that some of these instruments get deprecated, or the way that we're measuring things changes. Otherwise, lots of assumptions we and everyone else made about the rate of progress in the next decade will have been wrong. They were wrong. And we're already benefiting from the instrument vendors.

</details>

**Speaker A**: 我真希望我们面临的问题是你所描述的那种，那就是对于我们拥有的仪器，我们已经没有科学可以去做了。我们用尽了所有的科学。那样我们就有了要求仪器供应商加码的筹码。我们现在拥有的仪器，其强大程度堪比 10 年前的光束线（beam line）。我们今天进行的测量，如果放在 10 年前，会要求你向联邦政府申请一个凌晨 2 点的时间段，在偏远的某个地方，浪费几晚睡眠时间，在极其明亮的中子源或 X 射线源中进行。而在今天，供应商制造了像那样的仪器，我们可以把它放在量子点旁边，或者蛋白质表达仪器旁边。所以我希望那是一个可以确定的终态，但这非常非常不可能。而且我确定，我们将会对现有的仪器提出全新的科学问题。我们曾经邀请过同时涉及这两个主题的嘉宾：首先，你买不到任何设备是原生为了做高通量 AI 科学而设置的。其次，每天都有新的科学设备问世，它们开启了在五年、十年前根本不可能做到的事情。比如在线核磁共振（inline NMR）。在表征、微型化、更高分辨率、更亮的光源方面都有大量的发展。这些都是具有变革性的。而且它们可能与我们正在做的自动化高通量科学非常契合。所以我们将搬进位于马萨诸塞州阿莱夫（Alewife）的这个设施。它只是一个 3D 渲染图。这是一个占地 10 万平方英尺的空间。我们将逐步采用 AMR（自主移动机器人 autonomous mobile robots）来承担部分运输工作。所以你可以从图中看到一些。我们会把它放在节目说明里（show notes）。好吧，我们稍微换个话题。所以你刚才在谈论你们那包含 10 万亿个 token 的科学数据堆。当我听到 10 万亿时，我的第一个想法是，天哪，这听起来太庞大了。像这种规模的东西，相当于 30,000 个人类基因组，进行测序大约需要花费 300 万美元。它大约是几个像 Evo 和 Nucleotide Transformer 等大型基础模型规模的 1/2000。所以从某种意义上说，这是大量的数据。但在另一种意义上，这又不算大量的数据。毕竟并非所有的 token 都是一样的。

<details>
<summary>Original English</summary>

**Speaker A**: I wish the problem we have is what you're describing, that we've run out of science to do with the instrument we have. We used all the science. That we have the ante for the instrument vendors. The instruments we have now are as powerful as a beam line would have been 10 years ago. We're taking measurements today that 10 years ago would have requested you to ask the federal government for a time slot at 2 in the morning, somewhere out there, to waste a couple of nights of sleep, taking measurements that are really bright in neutron or X-ray sources. And today, the vendors make instruments like those that we can put next to the quantum dot or next to the protein expression. So I wish that that's an end state that is decidable, but very, very unlikely. And I'm sure there's going to be new science to be asking of the instruments we have. We've had guests who have had both of these themes of, first of all, none of the devices you buy are set up to do high throughput AI science. And also, that there are new scientific devices which come up every day, which just open up something which is impossible, like five, 10 years ago. Like inline NMR. There is lots of characterization, miniaturization, and more resolution, more bright sources. That are just transformational. And they might read really well with a kind of automated high throughput science we're doing. So we're moving into this facility in Alewife, Massachusetts. And it's just a 3D rendering. It's 100,000 square foot space. And we will move towards AMRs, autonomous mobile robots, as some of the transport. And so you can see some of that there. We'll put it in the show notes. OK, so kind of switching topics a little bit. So you were talking about your scientific pile of 10 trillion tokens. When I hear 10 trillion, my first thought is, man, that sounds like a lot. Things like this is 30,000 human genomes, which would cost roughly $3 million to sequence. It is roughly 1, 2000th of several of these large foundation models, like Evo and Nucleotide Transformer and so on. So in some sense, it is a lot of data. In other sense, it's not a lot of data. And not all tokens are the same.

</details>

<!-- chunk 8/9 -->

### Token Generation and Pre-training Data

**Speaker A**: 我很好奇，创建这个的过程是怎样的？你们的思考过程是什么？然后，10 万亿个 token 里到底包含多少真正有用的信息？

<details>
<summary>Original English</summary>

**Speaker A**: I'm curious, what went into creating this? What were your thought processes? And then how much actual useful information is in 10 trillion tokens or 10 trillion tokens?

</details>

**Speaker B**: 这和我们计算从互联网或后训练（post-training）运行中获取的预训练 token 是一个概念。所以，还是那句话，理解强化学习（RL）最好的方式是把它看作一种数据生成机制。它是一种引导模型走向越来越有价值、越来越好的 token 的方式。因此，这些 token 是我们在 MyLa 运行许多不同的科学 RL 环境后得出的结果。在这些环境中，token 是英文工具调用和实验反馈的混合体。正如我们一直讨论的，它们是由分词器（tokenizer）生成的“准英文（quasi-English）” token。这就是它们的来源。

<details>
<summary>Original English</summary>

**Speaker B**: So it's tokens in the same way that we think about counting pre-training tokens from the internet or from post-training runs. So these are, again, the best way to think about RL is a data generation mechanism. It's a way to steer the model towards more and more valuable tokens, like better tokens. And so these are the result of running that process across many different scientific RL environments at MyLa, where the tokens are a mix of English tool calls and experimental feedback. So they're quasi-English tokens, as we've been talking about, tokenized by the tokenizer. So that's where they came from.

</details>

**Speaker A**: 所以你们没有在做 token 化——

<details>
<summary>Original English</summary>

**Speaker A**: So you're not tokenizing--

</details>

**Speaker B**: 总体来说我们并没有专门去对它们进行 token 化。这其实是隐式发生的，因为如果向模型询问一个关于 DNA 的问题，那里自然就包含了 DNA 相关的 token。并不是说我们下载了 dbGaP、PDB 或者 SwissProt 这样的数据库，然后在序列层面对它们进行 token 化。这些是模型生成的、经过实验验证的推理 token。

<details>
<summary>Original English</summary>

**Speaker B**: So we're not tokenizing those in general. Implicitly, because if the model's asked a question about DNA, there are DNA tokens in there. It's not like we downloaded dbGaP or the PDB or Swiss Prote or something like that in tokenized at the sequence level. These are reasoning tokens, model-generated, that are experimentally verified.

</details>

**Speaker A**: 在这之上，你们依然还有 AlphaFold 和核苷酸 Transformer。所有的测序数据都被整合进去了。所以，10 万亿个 token 就是——10 万亿。

<details>
<summary>Original English</summary>

**Speaker A**: On top of this, you also still have your alpha fold, your nucleotide transformer. You have all your sequencing data, which goes into this. So 10 trillion tokens is-- 10 trillion. 10 trillion.

</details>

**Speaker B**: 我喜欢在我的笔记本上看到“10T”这个数字。我认为这种级别的数据量之所以重要，是因为预训练语料库通常在 15 到 30 万亿 token 之间。在这个规模下，你就能看到涌现能力的发生。因此，一旦你进入了万亿级别的 token 领域，我们就确信这足以让模型开始掌握并展现出涌现的能力。

<details>
<summary>Original English</summary>

**Speaker B**: I like looking at 10T on my laptop. The reason why I think that level of data is important-- pre-training corpuses are usually somewhere between 15 and 30 trillion tokens. And so that's the scale at which you see these emergent things happen. And so once you're in the trillion token regime, we feel confident that that's enough for the model to start to master and see emergent capabilities.

</details>

**Speaker A**: 你们的模型是从头开始训练的，还是基于某个开源模型？

<details>
<summary>Original English</summary>

**Speaker A**: Are you starting from scratch with your model, or you have some open source model?

</details>

**Speaker B**: 同样，为了保持雄心勃勃的宏大视野但又不至于病态地好高骛远，我们决定不亲自涉足预训练阶段，纯粹是因为里面要做的“黑魔法”实在是太疯狂了。而我们通过开放权重模型（open-weight models）的形式，相当于获得了价值约 10 亿美元的计算资源。所以我们从一个已经预训练过的开放权重模型起步。我们所作的假设是，该模型已经在互联网数据和大部分科学文献上进行了预训练。因此，它对于已知知识具备很好的科学先验，也是一个很好的建设基础。

<details>
<summary>Original English</summary>

**Speaker B**: Again, in the interest of being ambitiously over scoped, but not pathologically so. We have not decided to take on pre-training as well, just because the black magic that you have to do is insane. And we've been gifted something like a billion dollars worth of compute in the form of open-weight models. So we start with an open-weight model that has been pre-trained. And the assumption that we are making is that the model has been pre-trained on the internet in a large fraction of the scientific literature. Therefore, it's a good scientific prior over what is known, and therefore a good base camp to build upon.

</details>

**Speaker A**: 所以是在原有的万亿基础上又加了 10 万亿——

<details>
<summary>Original English</summary>

**Speaker A**: So it's 10 trillion on top of the trillion--

</details>

**Speaker B**: 把它们也加进去。是的。我们挺多地使用了 Nemotron，因为我们和 NVIDIA 有合作关系。我想那个模型的预训练和后训练大约投入了 30 万亿个 token。

<details>
<summary>Original English</summary>

**Speaker B**: Add it in, too. Yeah. Been-- Yeah. And we use Nemotron quite a bit because we have a partnership with NVIDIA. And I think there's like 30 trillion tokens that go into the pre- and post-training for that model.

</details>

### Open Source Datasets and Benchmarks

**Speaker A**: 所以在生成这些推理 token 的过程中，可以说你们同时也在创造极具价值的数据集。你们有没有考虑过将其中一些数据集独立开源？哪怕在没有推理模型的情况下，这些数据集对社区来说可能依然很有价值，而且根本不会削弱你们的护城河？

<details>
<summary>Original English</summary>

**Speaker A**: So in the process of these reasoning tokens, you are also creating what are arguably probably just rather useful data sets themselves. Have you thought about independently releasing some of those data sets open source and even in the absence of the reasoning model, which may still be quite valuable to the community, but doesn't actually deteriorate, break your mode at all?

</details>

**Speaker B**: 我们在过程中开发的一个成果，就是一个包含大约 1000 个独特的科学 RL 环境的测试套件。在这里，你可以放入一个前沿模型，也可以放入你自己的模型。我们就放入了我们自己的模型。我们几乎肯定会开源其中的一部分。有些是基于我们自己生成的数据，有些则是我们为了社区使用而精心挑选的数据。所以，我们构建的这个基准测试将会有部分开源版本。随之而来的，大概也会有一些训练数据。

<details>
<summary>Original English</summary>

**Speaker B**: So one of the things that we've developed along the way is a test suite of something like 1,000 unique scientific RL environments where you can drop in a frontier model. You can drop in your own model. We drop in our models. So almost surely we're going to open source a subset of that. Some of it based on data that we've generated, some of it that we have curated for the community to use. So there will be some open source version of the benchmark that we've assembled as doing part of that. And there will be probably some data, training data, that goes along with that.

</details>

**Speaker A**: 你们内部有能够实际运作实验室的基准测试吗？本质上就像是测试模型表现多好——换个说法，你们有自动化的实验控制机制吗？

<details>
<summary>Original English</summary>

**Speaker A**: Do you have benchmarks internally that actually operate the lab? Like essentially like a benchmark for how well does-- Maybe another way of saying, do you have automated experimental controls?

</details>

**Speaker B**: 有的。从公司成立之初起，我们就组建了多学科团队来致力于具体的封闭式问题。我们的超级模型运行模式始终是：进行基准测试，从零开始进行一些朴素的训练，然后引入大家都拿来即用的前沿模型，在我们的内部系统上进行比对。所以对于我们所做的每件事，我们确实都有一个内部基准测试。不过目前的领域非常具体，并不像 Andy 刚才描述的那个基准测试那样通用且包罗万象，因为目前测试的都是我们真正关心的事物、想要交付的产品，以及我们想要做出改变的领域。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. I think for every of the-- we've put together from the beginning of the company these multidisciplinary teams to work on specific close-ended problems. And the model super-anil has always been to benchmark, train something naively from zero, call in frontier, the frontier models that everybody would go use right out of the box, on our own internal. So everything we've done, we do have an internal benchmark. Now the domains are very specific. They're not as general and all encompassing as the benchmark that Andy was describing, because they are the things we really care about, and the products that we want to deliver, and sort of the places where we want to make a difference.

</details>

**Speaker C**: 但在所有这些领域中，我们通常会发现 Andy 所描述的那个能够调用工具、经过科学预训练的模型，通常会以压倒性优势击败我们所做的任何其他尝试。我的意思是，有必要思考一下我们正在努力做的事情，以及这与大型语言模型（LLMs）是如何相辅相成的。试想一下经过实验验证的推理路径（reasoning trace），你认为在互联网或预训练语料库中存在多少这样的数据？数量级为零。

<details>
<summary>Original English</summary>

**Speaker C**: But in all those places, we've typically seen that the scientifically pre-trained model that Andy is describing with access to tool calling typically demolishes, of course, anything else that we do. I mean, it's worth thinking about what we're trying to do, how that is additive with LMs. If you think about an experimentally verified reasoning trace, how many of those do you think exist on the internet or in the pre-training corpus? Order of zero.

</details>

**Speaker B**: 我也认为是零量级。相比于下一个数量级，它绝对可以舍入为零。所以，我们通过向模型展示这种数据获得了不可思议的提升，哪怕我们在参数量上相对于前沿模型处于劣势，仅仅向它展示经过实验验证的推理路径，我们就能立即看到提升。

<details>
<summary>Original English</summary>

**Speaker B**: Order of zero, I think. It certainly rounds down to zero versus the next order of magnitude. So we have just seen incredible lift from showing the model that even if we're at a parameter disadvantage relative to the frontier models, just showing it an experimentally verified reasoning trace, you see just immediate lift when we do that.

</details>

### Lila's Role within the Flagship Ecosystem

**Speaker A**: Lila 是 Flagship 旗下的一家公司。Flagship 基本上是世界上顶级的生物技术孵化器之一。你们是不是有过大概 30 次成功的 IPO？或者不是指你们，而是你们的母公司。包括你自己刚刚参与了 Generate Biomedicine 项目，并非常成功地在最近完成了 IPO。所以 Lila 在生物技术方面非常出色。不过从历史上看，它往往是以单一资产（single asset）为核心的，这是传统的 Flagship 模式。

<details>
<summary>Original English</summary>

**Speaker A**: Lila is a flagship company. Flagship is basically one of the biotech incubators in the world. Do you have had something like, what, I think 30 successful IPOs? Or not you, but your parent. Including you yourself were just part of Generate Biomedicine and just had a successful IPO very recently. So Lila is very good at biotech. I would say from history, it's very much single asset. Traditional flagship.

</details>

**Speaker B**: Flagship 在生物技术领域非常强大。但我刚才想表达的不是这个。是 Lila，Lila。Flagship 在生物科技领域非常强大，因为从历史上看，我们一直非常专注于单一资产。我想在过去的几年里，通过 Generate，还有 Expedition、VELO，他们已经开始涉足更多的平台型业务。

<details>
<summary>Original English</summary>

**Speaker B**: Flagship is very good at biotech. Flagship, that's not what I just said. Lila. Lila. Flagship is very good at biotech because historically, we've been very focused on single assets. I guess in the last few years with Generate, with I guess Expedition, VELO, there are some branching out into more platforming things.

</details>

**Speaker A**: 我很好奇，第一，Lila 是如何融入更广泛的 Flagship 生态系统的？有什么特别的原因促成了现在的 Lila 吗？为什么会从单一资产转向科学推理方向？以及这里面有怎样的更广泛的互动？特别要提到的是，你说你们有一种药物，或者说有一种 CAR-T 药物，已经处于新药临床试验申请（IND）阶段了。所以你们显然有将其转化为成品的生态系统。所以我很好奇，这未来的发展方向是什么？

<details>
<summary>Original English</summary>

**Speaker A**: I'm curious about one, how does Lila fit into the broader flagship ecosystem? Was there a specific reason why Lila is now? Why this sort of pivot from single asset into scientific reasoning? And what is the broader interaction? In particular, you mentioned that you had a drug, or you had a CAR-T drug, which was at the level of IND. So you clearly have the ecosystem to make that into something. So I'm curious, where is this going?

</details>

**Speaker B**: 是的，好问题。让我先梳理一下 Flagship 的背景，然后再谈谈——我们都是从同一个多能干细胞起步的，但每个人走向了不同的分化路径。一家 Flagship 公司的传统发展路径是这样的——就拿 Generate 的历史来说吧，我在 2018 年是 Generate 的早期顾问。当时有一种利用机器学习进行蛋白质工程的想法。我和 Flagship 的其他几个人以及一些外部加入的人——包括达特茅斯学院的一位名叫 Gevorg Grigoryan 的教授——从 Flagship 获得了种子资金，然后出去创办了这家公司。我们致力于构建技术，通常的交易模式是，Flagship 是 A 轮融资的唯一投资者。然后，B 轮融资通常是外部资本首次进入的节点。如你所言，它们往往最终成为基于资产的公司。Generate 目前有一种治疗哮喘的单克隆抗体正处于三期临床试验，紧随其后的是一种治疗慢性阻塞性肺病（COPD）的一期项目。我想 Flagship 的一些人，特别是我们的首席执行官 Geoffrey von Maltzahn，已经认识到了这一点，他参与创建了许多这样的公司。他发现自己一次又一次地在雇佣同一支团队：你需要机器学习团队，需要平台团队。所以我想他看到了所有这些公司之间共享的 DNA。于是我们想，不如成立一家能够基本上支持所有这些不同事务的公司吧。Lila 的第一年基本上就碰上了 01 模型的发布。我们已经准备好了所有的部件，当时就很明显，我们可以创建一个平台来支持一种新型的科学模型。在早期阶段，我们不知道如何将其货币化，什么是商业策略？这些年来，我们对此有了很多清晰的认识。但我们在两年前拥有的核心信念是，“惨痛教训（bitter lesson）”是正确的。科学可能成为一个无限的 token 生成器。在运营上，我们不同于传统的 Flagship 公司，外部投资在 A 轮之前就进入了。还有，A 轮的领投方不是 Flagship。所以我们确实有那样的血统，我们确实来自波士顿。我们确实分享了一家创建过 110 家初创公司的企业所积累的大量经验，我想——Generate 当时的编号是 FL5657，那实际上是一次合并。在早期，Lila 的编号是 9697。因此，Flagship 拥有创建公司的悠久历史。所以我们拥有那个网络资源，我们也拥有那些创建了这么多公司的领导者的经验。但我们是一个非常奇特的存在，我们在非常非常早的阶段就走上了一条完全不同的道路。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, great question. Let me do a little flagship framing, and then I'll sort of talk about-- so we all started the same pluripotent stem cell, but there's differentiation that we all take. The traditional path for a flagship company is there's-- so the history of Generate is I was an early advisor to Generate, a consultant over 2018. There was this idea to use machine learning for protein engineering. Me and a couple other folks at Flagship and some other external folks who came in-- Dartmouth professor named Gevorg Grigoryan was part of this-- got seed money from Flagship to then go and spin that out. We worked on building the technology, and then usually the deal is that Flagship is the sole investor during a Series A. And then the Series B is normally the first point at which external capital comes into that. To your point, they often end up being asset-based companies. Generate has a Phase 3 trial for monoclonal antibody to treat asthma, a Phase 1 program behind that to treat COPD. I think the recognition from some folks at Flagship, especially our CEO Geoffrey von Maltzahn, been involved in creating a lot of these companies. And he's like hiring the same team over and over and over again. You need the ML team. You need the platform team. And so I think he saw shared DNA between all these companies. And let's have one company that can essentially support all these different things. Year one of Lila was essentially like when 01 dropped. And so we had all these pieces in place, and it just became clear that we could create a platform to support a new kind of scientific model. In the early days, we didn't know how do you monetize that? What's the commercial strategy? We've gotten a lot of clarity over that over the years. But sort of the core conviction that we had two years ago was the bitter lesson is correct. Science could be an infinite token generator. Operationally, the way that we're different from a normal flagship is outside investment came in before the Series A. Again, the lead of the Series A was not Flagship. So we do have that lineage. We do come from Boston. We do have a lot of the shared learning that a company that has created 110 startups that I think-- So Generate was FL5657. It was actually a merge. In the early days, Lila was 9697. And so the Flagship has this long history of creating companies. So we have that network, and we have the learning of leaders who have created that many companies. But we're such a weird creature that we essentially went down a very different path very, very early.

</details>

**Speaker A**: 那么，当我听说你们有一种非常有前景的 CAR-T 疗法时，你说你们有一个 DC（候选药物），为什么不直接建立合作呢？通过合作把它开发出来？或许这正在计划中，或者其他什么情况？

<details>
<summary>Original English</summary>

**Speaker A**: So why is it that when I hear you have a very promising CAR-T therapy, you said you had a DC. Why not just partner with that out, partner with that out? Or maybe this is on the horizon or something.

</details>

**Speaker B**: 简而言之，我们确实正在围绕 CAR-T 疗法开展商业合作。其中一些合作是为了进一步开发以增加或改变它的一些特性，比如通过双特异性抗体等方式，去探索新的适应症。但我们已经利用那一种 CAR-T 疗法，实质上启动了多个合作项目。

<details>
<summary>Original English</summary>

**Speaker B**: The short answer is that we are engaging in commercial partnerships around CAR-T therapies, for sure. Some of them are further development to increase or change some of the properties, like by specifics and things like that, going after novel indications. But we've used that one CAR-T to essentially launch several partnership programs.

</details>

**Speaker A**: 好的，这有点像是原理证明，但它本身可能还并不完全符合成为一种药物的确切标准之类的。

<details>
<summary>Original English</summary>

**Speaker A**: Okay, so sort of like the proof of principle, but it in itself was not quite exactly what a drug needed to be or something.

</details>

**Speaker B**: 嗯，澄清一下，我们完全可以去尝试授权或合作那一个特定的成果。但我们发现，把它拿来并围绕进一步的开发达成多项合作要好得多。

<details>
<summary>Original English</summary>

**Speaker B**: Well, so just to be clear, we could go and try and license or partner that specific thing. We found that it was better to take that and secure several partnerships around further development.

</details>

**Speaker A**: 我明白了，好的，太酷了。你们实际上是在做某种联合开发的模式。这就是虚拟初创公司的理念：围绕其中一个适应症启动一个虚拟初创公司，然后他们实质上向我们支付收入来进行后续开发。同时，这周围有一系列的里程碑等设定。

<details>
<summary>Original English</summary>

**Speaker A**: I see, okay, cool. You're getting at basically, you're doing some sort of code development thing. This is a virtual startup idea where company starts a virtual startup around one of these indications and they essentially pay us revenue to further development. And again, we have these milestones and things around it.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 那么，从长远来看，鉴于 Flagship 专门专注于生物领域，而且从未真正涉足过材料等分支，这会对 Flagship 或是 Lila 的战略比重产生怎样的影响？它在其中起作用吗？还是说，在这一点上，你们算是已经起航并且某种程度上剥离出来了。这大概也是它为什么能如此迅速地分化成与众不同的事物的原因之一吧？

<details>
<summary>Original English</summary>

**Speaker A**: So like long-term, since flagship is specifically bio and is never really branching the materials, how does that sort of weight flagship or Lila strategy, does that play into it at all? Or is like, at this point you've kind of launched and sort of spun off. It's kind of one of the reasons why it's sort of differentiated into something different so quickly, right?

</details>

**Speaker B**: 我认为从成立第一天起，我们任务广度的一部分就明确地超越了单纯的生物科技范畴。我们需要雇佣的人员来自不同的网络，我们需要采购的仪器来自不同于通常 Flagship 供应商的其他厂商。所以我认为这部分解释了为什么它感觉有些不同。但这也是任务的核心所在，对吧？我们不可能只在狭窄的领域里使其奏效。就定义而言，我们希望能够尽可能地广泛，因为涌现的行为了将从那里诞生。我认为如果你看看目前在 Lila 工作的人员构成，你会发现它跟我们对一家普通生物技术公司的预期是完全不同类型的。我们的招聘对象、竞争对象，甚至有时候我们赢下的人才，都是那些正在考虑前沿实验室（frontier lab）录取通知的人。我们有很重的软件工程和技术背景占比。我们花在 GPU 上的开销对于一家生物技术公司来说是不同寻常的，我会这么说。我想如果我们自称是一家生物制药公司的话，我们可能拥有世界上排名前三的 GPU 集群。

<details>
<summary>Original English</summary>

**Speaker B**: I think part of the breadth of the mission clearly was beyond biotech from day one. And the people we needed to hire came from different networks, the instruments we had to buy came from different vendors than the flagship vendors would have usually been. So I think that was part of sort of the reasons why it feels somewhat different. But it's also core to the mission, right? We cannot get this to work on a narrow field. By definition, we want to be as broad as we can possibly be because that's where the emerging behaviors are going to come from. And I think if you looked at the composition of people who work at Lila now, it would look like categorically different than what you would expect like a median biotech company to look like. So we hire out of, or compete for, and sometimes win against people who are considering frontier lab offers. We have a heavy software engineering and tech presence. The amount that we spend on GPUs would be atypical for a biotech, I will say. I think that if we called ourselves a biopharma, we probably would have a top three GPU cluster in the world.

</details>

<!-- chunk 9/9 -->

### 发展方向与材料科学挑战

**Speaker A**: 确实，那是我们基因的一部分，但我们一直有意地做出决策，使我们走在自认为对生命科学最有前景的轨道上。这不仅仅是孩子们反抗父母之类的行为。我们认为这个论断是正确的，它指向了一家对不仅是生物技术，而且对材料和化学都非常有价值且重要的公司。

<details>
<summary>Original English</summary>

**Speaker A**: It's true that that's part of our DNA, but we've been intentional about trying to make decisions that put us on what we think is the most promising trajectory for life. This isn't just kids rebelling against their parents or something. We think that the thesis is right, and it points towards a very valuable, but also important company for not just biotech, but for materials and chemistry.

</details>

**Speaker B**: 好的，这引出了我想问的最后一个问题。材料和生物学，哪个更难？

<details>
<summary>Original English</summary>

**Speaker B**: OK, that brings me to what I think is my last question. What's harder, materials or bio biology?

</details>

**Speaker C**: 它们其实非常不同。这很有趣，对吧？我觉得我们马上就要上演那个蜘蛛侠互相指责的表情包了——

<details>
<summary>Original English</summary>

**Speaker C**: They're actually very different. It's funny, right? I feel like we're about to do the Spider-Man meme in like--

</details>

**Speaker A**: [声音重叠] 当我经历了小分子药物发现 AI 的第一轮热潮时，比如 Atomwise、Generate 和 insitro。所以我认为最难的是小分子这块。它包含了化学、合成推理的所有难题，然后它还有推理生物学、不良反应的所有难题，以及——

<details>
<summary>Original English</summary>

**Speaker A**: [overlapping voices] When I was around for the first merry-go-round of AI for small molecule drug discovery, the Atomwise, Generate, and insitro. So I think the hardest is the thing that is a small molecule. It has all the difficulties of chemistry, of reasoning about synthesis, and then it has all the difficulties of reasoning about biology and adverse effects and--

</details>

**Speaker C**: 是的，但反过来说，我们的工具箱里有很多技巧可以从生物学中借用，对吧？所以它更难，但你同时也有——

<details>
<summary>Original English</summary>

**Speaker C**: Yeah, but the counterpoint thing, that we have so many tricks in our toolkit, which you can borrow from biology, right? So it's harder, but you also have--

</details>

**Speaker A**: 嗯，我认为材料更难。他们拥有我们在生物学中没有的出色的模拟器的优势。在材料科学中，你没有生物学中那种成熟的高通量自动化。对我来说，材料作为一个学科很有趣，因为没有一个像中心法则那样的统一原则。材料意味着很多不同的东西。我其实到现在都还没完全理解这个统一原则。当我们说材料科学时，它到底意味着什么。而且商业动态也完全不同。再说一次，对于 CAR-T（嵌合抗原受体T细胞疗法），我们知道，如果我们想的话，该如何直接将其商业化。而对于材料，存在供应链，还有设备。你在实验室里做的测试只能部分预测该材料在使用时的寿命，而且计算更难。

<details>
<summary>Original English</summary>

**Speaker A**: Well, I think materials are harder. So they have the benefit of great simulators that we don't have in bio. In materials science, you don't have the mature high-throughput automation that you have in biology. For me, materials as a subject is interesting, because there's not a unifying principle like the central dogma. Materials means lots of different things. I actually still don't quite understand the unifying principle. When we say materials science, what exactly that means. And then the commercial dynamics are completely different. Again, with CAR-T, we know, if we wanted to, how to monetize that directly. With material, there's this supply chain, there are devices. The testing that you do in the lab is only partially predictive of the lifetime of how that material will be used, and the math is harder.

</details>

**Speaker C**: 就供应链而言，对两者仍然都很重要。也许你可以用一些产品验证和确认（也就是所谓的产品资质认证）来代替临床试验。所以存在直接的类比，而且两者都有各自困难的部分。经济学方面是非常不同的。如果你通过了临床试验，你就能赚钱。那东西很有价值。而且制造它的成本很少是阻碍因素。在生物学中为资产承销要比在材料领域容易得多。

<details>
<summary>Original English</summary>

**Speaker C**: In terms of supply chains, still matter for both. Maybe you replace clinical trials with some product validation and verification, qualification as the terms. So there are direct analogies, and there are hard parts for both of them. The economics are very different. If you pass a clinical trial, you make money. That thing is valuable. And how much it costs to make it is very rarely the blocking element. It can be for the most-- Much easier to underwrite an asset in biology than it is in materials.

</details>

**Speaker A**: 你们知道一家制造超导体的公司名字吗？这个总是被提及。你们在做超导体吗？是的，我们关注磁体，关注超导体。那真的是很酷的科学。你们各位知道一家制造超导体的公司名字吗？没人知道。这些东西超级重要。

<details>
<summary>Original English</summary>

**Speaker A**: Do you guys know the name of a company that makes superconductors? This always comes up. Are you guys doing superconductors? Yeah, we care about magnets. We care about superconductors. They're really cool science. Do you folks know the name of a company that makes superconductors? Nobody knows. These things are super important.

</details>

**Speaker B**: 我知道它们被用于核磁共振（MRI）。

<details>
<summary>Original English</summary>

**Speaker B**: I know that they're using MRI.

</details>

**Speaker A**: 没错。那是它唯一的商业应用。但事实证明，这些东西，当你成功时，你有点像——当你发明了一种能做某事的酷炫材料时，你有点像一家不知名的公司，制造着同样的东西，获得了成功，并且有很好的现金流。但你无法一举成名。每个人都知道大型制药公司，你知道有哪几家巨头。而大多数大型材料公司都在闭门造车。大多数商业接触看起来都像是让他们告诉你重要的问题是什么。并且那里的开放创新生态系统更少。在材料领域有一些东西显然被认为是有价值的。但我认为它与生命科学只是非常不同。也许我们没怎么触及的最后一件事——我想指出来，我认为在化学，尤其是材料领域——政府赞助的研究是一个巨大的驱动力。所以，就像政府不觉得他们需要做直接的发现，除了资助美国国立卫生研究院（NIH）进行早期、开放的、假设驱动的科学研究外；政府和国家安全以独特的方式推动着材料创新。你可以在我们与英国政府合作的方式中看到这一点。我们有合作伙伴关系。我们与美国政府合作。我们获得了奖项。我们参与开发材料和技术，这是推动创新的生态系统的一个不同部分。那也是不同的。

<details>
<summary>Original English</summary>

**Speaker A**: Exactly. That's the only commercial application. But it turns out, these things, when you succeed, you kind of are-- when you make up a cool material that does something, you're kind of a nameless company that makes it same and is successful and has good cash flows. But you don't get to break. Everybody knows a big pharma. But you've got your three ends. And most of the big material companies are behind closed doors. Most of commercial engagements look like getting them to tell you what the important problem is. And there's less of an open innovation ecosystem. There's a couple of things and materials that are obviously recognized to be valuable. But it's just, I think, very different than life sciences. And maybe one of the last things that we haven't touched upon a lot-- and I want to flag out, I think, chemistry, and especially materials-- government-sponsored research is a big driver. So in the same way that the government doesn't feel they need to do direct discovery other than funding NIH for early-stage, open science, hypothesis-driven science, the government and national security drive materials innovations in ways that are unique. And you see this in the way we engage with the British government. We have partnerships. We work with the US government. We have awards. We participate in developing materials and technologies, which is a different part of the ecosystem that drives innovation. That's also different.

</details>

**Speaker C**: 是的，绝对的。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah, definitely.

</details>

**Speaker B**: 你们在参与 Genesis 计划（Mission Genesis）吗？

<details>
<summary>Original English</summary>

**Speaker B**: Are you guys working in Mission Genesis?

</details>

**Speaker A**: 我们是被点名的合作伙伴之一。我们与许多国家实验室一直保持着持续的合作关系。所以我们一直在做这方面的工作。我们确实提交了 25 个 Genesys 相关的内部提案，方式很糟糕。所以是的，我们有很多——我在开玩笑。他离开学术界时以为不用再写拨款申请了，结果还是得写。我预定了他。他们预期大约有两万。

<details>
<summary>Original English</summary>

**Speaker A**: We were one of the named partners. We've had an ongoing relationship with a lot of the national labs. And so we have been working on that. We did send 25 Genesys, like house proposals, and a lousy way. So yeah, we have a lot of-- I was joking. He left academia thinking grant writing was behind him, only to have to write. I booked him. They expect about 20,000.

</details>

### AI与材料科学的发展瓶颈

**Speaker B**: 我们喜欢问所有嘉宾的一个问题是，如果你能消除你所在领域的一个瓶颈，并且你可以随意定义“领域”，那个瓶颈会是什么？

<details>
<summary>Original English</summary>

**Speaker B**: The question that we like to ask all of our guests if you could remove a bottleneck in your domain and you can define domain by fiat, what would that bottleneck be?

</details>

**Speaker A**: 对我来说，我会回到 Rafa 以前做基于物理的模拟那段时间。我会说是“从模拟到现实”（sim-to-real）。对于那些来自基于物理学世界的人来说，就是从模拟到现实。我认为就是这个。

<details>
<summary>Original English</summary>

**Speaker A**: To me, I'm going to go to old time in Rafa that was doing physics-based simulation. I would say they sim-to-real. They sim-to-real for the people that come from the physics-based world. I think they sim-to-real.

</details>

**Speaker B**: 你如何解释那是什么意思？

<details>
<summary>Original English</summary>

**Speaker B**: How do you explain what that means?

</details>

**Speaker A**: 我的意思是——这些人通常是在机器人的背景下提到这个词的，你在 3D 空间中的虚拟模拟，允许你训练将在物理空间中移动的机器人。但这之间存在差距。他们称之为“模拟到现实的差距”。对我们进行基于物理的模拟来说，我们对粘稠物质进行分子模拟。我们对坚硬物质进行电子结构模拟。它们还可以，但缺乏足够的预测性。这也是为什么——如果不是因为那个差距，也许我们就不得不建立一个自动驾驶的材料实验室，因为我们本来可以直接进行预测的。所以我认为我们知道存在物理规律，但它就是还没完全达到具有预测性的程度，这意味着我们在物理上训练的模型也不可能弥合这个差距，因为它们仍然缺失了这一部分。它们是基于那些不够好的近似值来训练的。所以我认为过去十年我们在材料 AI 领域一直追求的东西就是——如果我们用计算数据进行训练，我们能回答真实的实验问题吗？这也是那个如果我能回到过去，除了消除瓶颈之外，我最想解决的地方，那就是我们一直用于训练的底层模拟的准确性。

<details>
<summary>Original English</summary>

**Speaker A**: What I mean-- so these people have typically meant it in the context of robotics, your virtual simulations in 3D spaces, allow you to train robots that will move in physical spaces. But there is a gap. And they call it the sim-to-real gap. For us in physics-based simulations is that we do molecular simulations of gooey stuff. We do electronic structure simulations of hard stuff. And they're OK, but they're not predictive enough. And this is the reason why-- if it wasn't for that, maybe we will have to make a self-driving lab for materials, because we would have been able to just predict. So I think we know there's physics, but it doesn't quite go the way to being predictive, meaning that the models that we train on physics cannot possibly close the gap either, because they're still missing this. They're trained on approximations that are just not good enough. So I think the thing we've been chasing for a decade in AI for materials has been sort of-- if we train on computational data, can we answer real world experimental questions? And that would have been the place where if I get to also go back in time, in addition to taking the bottleneck out, it would be the accuracy of the underlying simulation that we've been training on all the time.

</details>

**Speaker B**: 所以这有点像 Heather Kulik 所说的，材料领域没有 AlphaFold（alfalfold）。

<details>
<summary>Original English</summary>

**Speaker B**: So this is sort of like Heather Kulik said, there is no alfalfold for materials.

</details>

**Speaker A**: 呃，有趣的是 AlphaFold 是基于实验训练的。所以这是不同的——我的意思是，这不是什么好笑的事——她和我都是从做基于物理的模拟背景出来的。而她指出的这个东西，里面没有任何模拟的成分，这有点像承认了同样一个潜在的问题，那就是所有的这些——META 产生了数千万、数亿的训练数据点。但它们全都是虚拟模拟，对于我们真正想做的事情来说，根本起不到足够的作用。

<details>
<summary>Original English</summary>

**Speaker A**: Well, the funny thing is alfalfold was trained on experiments. So it's a different-- I mean, that's not a funny-- she and I would both come from doing physics-based simulations. And the fact that she called out something that had no simulations in it whatsoever, it's kind of admitting the same underlying issue, which is like all these-- META has produced tens of millions, hundreds of millions of training data points. But they're all virtual simulations that just don't carry enough water for the thing we actually want to do.

</details>

**Speaker C**: 这个可能听起来有点无聊而且显而易见。但是有一个指标可以用来追踪你的训练运行有多高效。它叫做模型浮点运算利用率（MFU）。GPU 带有一个标称的理论峰值浮点运算吞吐量，那是在最好情况下计算一些你其实不关心的东西时的指标。单位时间内你能做多少次浮点运算？MFU 始终只是理论峰值浮点运算次数的极小一部分。而对于强化学习来说，它总是在 5% 到 6% 左右。换句话说，这意味着我们只获得了我们付费购买的实际 GPU 计算能力的 5% 左右。所以，如果我能用法术挥舞魔杖，让我们的技术栈以 100% 的模型浮点运算利用率执行，我会那么做，因为这样一来，我们可以更快地得到答案，而且可以购买更少的 GPU，并将这些资金重新部署到实验室或类似的地方。

<details>
<summary>Original English</summary>

**Speaker C**: This is going to be like a boring and obvious one. But there's a metric that you use to track how efficient your training runs are. It's called model FLOPs utilization, or MFU. So the GPU comes with an advertised peak FLOPs throughput, which is under the best situation doing a calculation that you don't actually care about. How many floating-point operations can you do per unit time? MFU is always a very small fraction of peak theoretical flops. And for reinforcement learning, it's always somewhere around 5% to 6%. So said differently, that means that we're getting like 5% of the actual GPU computing power that we're paying for. So if I could buy fiat, wave a wand, and make our stack perform at 100% model FLOPs utilization, I would do that because we would, one, get to the answer faster, but then also be able to buy fewer GPUs and redeploy that capital to the lab or something like that.

</details>

**Speaker B**: 不过那很有趣。因为你们的部署推出（rollouts）不正是受限于实验室吗？

<details>
<summary>Original English</summary>

**Speaker B**: That's interesting, though. Because your rollouts, aren't they constrained by the lab?

</details>

**Speaker C**: 确实如此。但是当我们训练一个大模型时，所有那些数据——我们的强化学习训练管道非常复杂。所以，想要实现大规模处理的一种思路是，直接让模型到处进行 rollout（模拟运行），等待足够的轨迹数据堆积起来，然后再反向传播到模型中。另一种不同的方法是将其解耦分解，让一堆并行训练的专家模型进行工作，它们要么是在生成数据，要么是在自我训练，然后你再把这些知识蒸馏回中心大模型。第二种方法是最有效的，是效率更高的方法。因为所有这些事情都在不同的时间尺度上发生。由于模型太大了，当你有 10 万亿个 token 并希望尽可能高效地将它们推送过模型时，你仍然需要在其之上进行一些强化学习。所以如果我们能获得我们所支付的所有算力性能，我会用我的法力宣告实现它。很酷。

<details>
<summary>Original English</summary>

**Speaker C**: They are. But when we train a big model, all of that data-- our RL training pipelines are very complicated. So one way to think about how you would do this at scale is just to have the model doing rollouts left and right, waiting for enough trajectories to pile up and then backpropagating that into the model. A different way to do that would be to factorize that, have a bunch of expert models that are trained in parallel that are either generating data or being trained themselves, and then you distill that back into the central model. And second way is the most efficient, the more efficient way to do it. Because all those things are happening at different timescale. It's that big, when you have the 10 trillion tokens and you want to push them through the model as efficiently as possible, you're still going to be doing some reinforcement learning on top of that. So if we could get all the flops that we're paying for, I would by fiat declare that. Cool.

</details>

**Speaker B**: 好吧，是的，在我们结束之前，有什么想留给观众的话吗？

<details>
<summary>Original English</summary>

**Speaker B**: Well, yeah, before we end, is there anything you want to leave the audience with?

</details>

**Speaker A**: 让我说说为什么我们在这里。我们现在在旧金山有一个办公室。它位于旧金山市中心的弗里蒙特街（Fremont Street） 181 号。目前那里大概有二三十人，但我们正寻求积极扩张。我们正在从技术栈的各个领域招募人才，显然，后训练（post-training）方面我们正在积极招聘。那些曾在领域 AI，比如生命科学和材料科学方向工作过的人。我们也在招聘这方面的人才。这里目前没有湿实验室（wet lab），所以全部是计算类的工作。但如果人们今天听到的任何内容听起来很有趣，如果觉得这很吸引人，请随时发消息给我或者 Rafa。

<details>
<summary>Original English</summary>

**Speaker A**: Let me say why we're here. So we have an office in San Francisco now. It's 181 Fremont Street in downtown San Francisco. There's currently 20, 30-ish people who sit there, but we are looking to expand that aggressively. We're looking to pull from all areas of the stacks, so both post-training, obviously aggressively hiring for that. Folks have been working in domain AI, like life sciences and materials sciences. We're also hiring for that. No wet lab here currently, so it's all computational work. But if any of this stuff that people have heard about today sounds interesting, feel free to shoot either me or Rafa a message if that sounds interesting.

</details>

**Speaker B**: 感谢你们来到这里。这是一次非常引人入胜的对话。非常感谢。

<details>
<summary>Original English</summary>

**Speaker B**: Thank you for being here. It's been a really fascinating conversation. I appreciate it.

</details>

**Speaker A**: 谢谢你的邀请。再见。

<details>
<summary>Original English</summary>

**Speaker A**: Thank you for having us. Yeah.

</details>