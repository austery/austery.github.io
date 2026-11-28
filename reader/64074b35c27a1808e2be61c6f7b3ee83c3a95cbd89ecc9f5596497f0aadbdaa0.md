---
author: All-In Podcast
date: '2026-03-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=gwW8GKwHB3I
speaker: All-In Podcast
tags:
  - ai-factory
  - disaggregated-inference
  - agentic-systems
  - digital-biology
  - ai-governance
title: 黄仁勋：英伟达的未来、物理AI、Agent的崛起、推理爆发及AI公关危机
summary: 本次访谈深入探讨了英伟达（Nvidia）在AI时代的战略布局，包括其从GPU公司向AI工厂的转型，以及在物理AI、数字生物学、边缘计算等新兴领域的巨大潜力。黄仁勋强调AI推理的爆炸性增长和Agent系统对计算模式的彻底变革，并讨论了AI立法、开放模型与专有模型共存的必要性，以及AI如何重塑产业格局和劳动力市场。他还强调了AI技术领导者在公共认知塑造上的责任，并分析了AI供应链的全球竞争态势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Jensen Huang
  - LeBron James
companies_orgs:
  - Nvidia
  - Anthropic
  - OpenAI
  - Google
  - Amazon
  - AMD
  - Tesla
  - Waymo
  - BYD
  - Uber
  - Bit Tensor
  - Intel
products_models:
  - Grock
  - Dynamo
  - Omniverse
  - Blue Field
  - Vera Rubin
  - ChatGPT
  - Claude
  - Gemini
  - Blackwell
  - OpenClaw
  - Synopsys
  - Cadence
  - Blender
  - Autodesk
  - Photoshop
media_books: []
status: evergreen
---
### 访谈开场与英伟达策略

**采访者**: 我们提前了一周的节目，因为只有三个人值得我们这么做：特朗普总统、耶稣和黄仁勋。至于顺序，就让你来选吧。你取得了如此惊人的成就，这次活动也非常棒。每个行业都在这里，每个科技公司都在这里，每个AI公司都在这里。真是不可思议，不可思议。我将全力以赴。

**Advert**: 如果你今天想从零开始构建一个全球金融系统，你不会把它建立在50年前的传统基础设施上，你会选择构建**Airwall**，一个为全球账户、卡和支付设计的AI原生平台。它旨在让整个世界感觉像一个本地市场。其他公司还在将AI嫁接到破旧的基础设施上，但AirWall从一开始就是为智能时代而生。停止支付传统税，立即访问 awallix.comallin 开始构建未来。Arowallix，构建未来。

**采访者**: 过去一年中，一项重大发布就是**Grock**。当你收购Grock时，你有没有意识到Chamath会变得多么令人难以忍受？

<details>
<summary>Original English</summary>

**采访者**: We've preempted the weekly show and there's only three people we preempt the show for. President Trump, Jesus, and Jensen. And I'll let you pick which order we do that. But what an amazing run you've had and a great event. Every industry is here. Every tech company is here. Every AI company is here. Incredible. Incredible. I'm going all in.

**Advert**: If you were building a global financial system from first principles today, you wouldn't build it on 50-year-old legacy rails, you'd build **Airwall**, one AI native platform for global accounts, cards, and payments. It's designed to make the entire world feel like a local market. Others are bolting AI onto broken infrastructure, but AirWall was built for the intelligent era from day one. Stop paying the legacy tax and start building the future at awallix.comallin. Arowallix. Build the future.

**采访者**: And one of the great announcements of the past year has been Grock. When you made the purchase of Grock, did you realize how insufferable Cha Chimath would become?

</details>

**黄仁勋**: 我有点预感。

<details>
<summary>Original English</summary>

**Jensen**: I had an inkling that...

</details>

**采访者**: 我们是他的朋友，我们每周都要应付他。

<details>
<summary>Original English</summary>

**采访者**: We're his friends. We have to deal with him every week.

</details>

**黄仁勋**: 我知道。

<details>
<summary>Original English</summary>

**Jensen**: I know it.

</details>

**采访者**: 你还得应付他六周的成交期。

<details>
<summary>Original English</summary>

**采访者**: You had to deal with him for the six-week close.

</details>

**黄仁勋**: 我知道。就像两周，两周。

<details>
<summary>Original English</summary>

**Jensen**: I know. It's like two weeks. Two weeks.

</details>

**黄仁勋**: 这一切现在都回来了，让我有点不舒服。事情是这样的，我们的许多策略早在几年前的**GTC**上就已公之于众。两年半前，我推出了AI工厂的操作系统，它叫做**Dynamo**。Dynamo，你可能知道，是由西门子创造的一种仪器，一台能将水转化为电力的机器。Dynamo驱动了上一次工业革命中的工厂。所以我认为它是下一场工业革命，即AI工厂的操作系统最完美的名字。在Dynamo内部，核心技术是**解耦推理**。Jason，我知道你技术非常精通。

<details>
<summary>Original English</summary>

**Jensen**: It's all coming back to me now. It's making me rather uncomfortable. The thing is, many of our strategies are presented in broad daylight at GTC years in advance of when we do it. Two and a half years ago, I introduced the operating system of the AI factory, and it's called **Dynamo**. Dynamo, as you know, is a piece of instrument, a machine that was created by Siemens to turn essentially water into electricity. And Dynamo powered the factory of the last industrial revolution. So I thought it was the perfect name for the operating system of the next industrial revolution, the factory of that. And so inside Dynamo, the fundamental technology is disaggregated inference. Jason, I know you're super technical.

</details>

**Jason**: 绝对是，我了解它。

<details>
<summary>Original English</summary>

**Jason**: Absolutely. I know it.

</details>

**黄仁勋**: 我把这个问题交给你了。请为观众定义一下，我不想抢你的风头。

<details>
<summary>Original English</summary>

**Jensen**: I'll let you take this one. Go ahead and define it for the audience. I don't want to step on you.

</details>

**Jason**: 好的，谢谢。我知道你刚才想插话，但这就是**解耦推理**，这意味着推理的流水线，即处理流水线，极其复杂。事实上，它是当今最复杂的计算问题。它有令人难以置信的规模，涉及大量不同形状和大小的数学运算。我们提出了这样的想法：你可以解耦处理的各个部分，使得其中一部分可以在某些GPU上运行，其余部分可以在不同的GPU上运行。这让我们意识到，即使是解耦计算也可能是有意义的，我们可以拥有不同异构性质的计算。同样的理念也引导我们收购了**Mellanox**。

<details>
<summary>Original English</summary>

**Jason**: Yeah. Thank you. I knew you wanted to jump in there for a second, but it's disaggregating inference, which means the pipeline, the processing pipeline of inference is extremely complicated. In fact, it is the most complicated computing problem today. Incredible scale, lots of mathematics of different shapes and sizes. And we came up with the idea that you would disaggregate parts of the processing such that some of it can run on some GPUs, rest of it can run on different GPUs. And that led to us realizing that maybe even disaggregated computing could make sense that we could have different heterogeneous nature of computing. That same sensibility led us to **Mellanox**.

</details>

**黄仁勋**: 你知道，如今**英伟达**的计算分布在GPU、CPU、交换机、纵向扩展交换机、横向扩展交换机、网络处理器上，现在我们还要加入Grock。我们将把正确的工作负载放到正确的芯片上。我们真的从一家GPU公司演变为一家**AI工厂**公司。

<details>
<summary>Original English</summary>

**Jensen**: Today, Nvidia's computing is spread across GPUs, CPUs, switches, scale-up switches, scale-out switches, networking processors, and now we're going to add Grock to that. And we're going to put the right workload on the right chips. We just really evolved from a GPU company to an AI factory company.

</details>

**采访者**: 我的意思是，我认为那可能是最大的收获。你正在看到这种根本性的解耦，我们已经从GPU发展到拥有所有这些不同选项的复杂组合，它们最终都会存在。你或你们在台上说过的话是：“我希望那些高价值的推理人员能听一听这个。”你说，你数据中心25%的空间应该分配给Grock LPU GPU。

<details>
<summary>Original English</summary>

**采访者**: I mean, I think that was probably the biggest takeaway that I had. You're seeing this fundamental disaggregation where we've gone from a GPU and now you have this complexion of all these different options that will eventually exist. The thing that you guys said on stage or you said on stage was, "I would like the high-value inference people to take a listen to this." And 25% of your data center space, you said, should be allocated to this Grock LPU GPU.

</details>

**黄仁勋**: 大约25%的**Vera Rubin**在数据中心里将是Grock。那么你能告诉我们行业如何看待这种现在基本上正在创建的下一代解耦预填充解码DSAG的想法，以及你认为人们将如何对此做出反应？

<details>
<summary>Original English</summary>

**Jensen**: Grock to about 25% of the **Vera Rubin**s in the data center. So can you tell us about how the industry looks at this idea of now basically creating this next generation form of disaggregated pre-filled decode DSAG, and how people do you think will react to it?

</details>

**黄仁勋**: 好的。回溯一下，当时我们增加这个功能时，我们从大型语言模型处理转向了**Agentic处理**。现在，当你运行一个Agent时，你访问工作内存，你访问长期内存。你使用工具。你非常努力地使用存储。你有Agent与其他Agent协同工作。有些Agent是非常大的模型，有些是较小的模型，有些是扩散模型，有些是自回归模型。因此，这个数据中心内有各种不同类型的模型。我们创建Vera Rubin就是为了运行这种极其多样化的工作负载。我的感觉是，我们增加了一个曾经只有单个机架的公司。我们现在又增加了四个机架。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. And take a step back, at the time that we added this, we went from large language model processing to agentic processing. Now, when you're running an agent, you're accessing working memory, you're accessing long-term memory. You're using tools. You're really beating up on storage really hard. You have agents working with other agents. Some of the agents are very large models. Some of them are smaller models. Some of them are diffusion models. Some of them are auto-regressive models. And so there are all kinds of different types of models inside this data center. We created Vera Rubin to be able to run this extraordinarily diverse workload. My sense is, and so we added what used to be a one-rack company. We now added four more racks.

</details>

**采访者**: 对吧？

<details>
<summary>Original English</summary>

**采访者**: Right?

</details>

**黄仁勋**: 所以，如果你愿意，英伟达的总潜在市场（TAM）从原来的数字增加到可能高出33%到50%。现在，这33%或50%中的很大一部分将是存储处理器，它被称为**Blue Field**。其中一部分，我希望，将是Grock处理器，还有一部分是CPU。所有这些，以及很大一部分将是网络处理器。所以所有这一切都将运行AI革命的核心计算，也就是Agent。

<details>
<summary>Original English</summary>

**Jensen**: So, Nvidia's TAM, if you will, increased from whatever it was to probably something, call it, you know, 33%, 50% higher. Now, part of that 33% or 50%, a lot of it's going to be storage processors. It's called **Blue Field**. Some of it will be, a lot of it, I'm hoping, will be Grock processors, and some of it will be CPUs. And they're all, and a lot of it's going to be networking processors. And so all of this is going to be running basically the computer of the AI revolution, called agents.

</details>

**采访者**: 现代工业的操作系统。

<details>
<summary>Original English</summary>

**采访者**: The operating system of modern industry.

</details>

**黄仁勋**: 嵌入式应用怎么样？比如我女儿家里的泰迪熊想和她说话。里面会放什么？是定制的ASIC，还是最终会有一个更广泛的TAM，通过开发在边缘和嵌入式应用中针对不同用例的工具？我们认为，从最大的规模来看，这个问题中有三台计算机。一台计算机是真正用于训练AI模型、开发和创建AI的，另一台计算机用于评估它。根据你遇到的问题类型，例如，环顾四周，有各种各样的机器人和汽车等。你必须在模拟物理世界的虚拟健身房中评估这些机器人。所以它必须是遵循物理定律的软件。

<details>
<summary>Original English</summary>

**Jensen**: What about embedded applications? My daughter's teddy bear at home wants to talk to her. What goes in there? Is it a custom ASIC or does there end up becoming much more kind of a broader set of TAM with developing tools that are maybe different for different use cases at the edge and an embedded application? We think that there's three computers in the problem at the largest scale when you take a step back. There's one computer that's really about training the AI model, developing, creating the AI, another computer for evaluating it. Depending on the type of problem you're having, like, for example, you look around, there's all kinds of robots and cars and things like that. You have to evaluate these robots inside a virtual gym that represents the physical world. So it has to be software that obeys the laws of physics.

</details>

**采访者**: 那是第二台计算机。我们称之为**Omniverse**。第三台计算机是边缘计算机，即**机器人计算机**。

<details>
<summary>Original English</summary>

**采访者**: And that's a second computer. We call that **Omniverse**. The third computer is the computer at the edge, the robotics computer.

</details>

**黄仁勋**: 那个机器人计算机，其中一个可能是自动驾驶汽车，另一个是机器人，还有一个可能是泰迪熊。

<details>
<summary>Original English</summary>

**Jensen**: That robotics computer, one of them could be a self-driving car. Another one's a robot. Another one could be a teddy bear.

</details>

**采访者**: 给泰迪熊的小小一个。

<details>
<summary>Original English</summary>

**采访者**: Little tiny one for a teddy bear.

</details>

**黄仁勋**: 其中一个最重要的是我们正在开发的一个项目，它基本上将电信基站转变为AI基础设施的一部分。所以现在，整个2万亿美元的产业，最终都将转化为AI基础设施的延伸。因此，无线电将成为边缘设备。工厂、仓库，你想得到的都可以。所以，这三台基本的计算机都将是必需的。

<details>
<summary>Original English</summary>

**Jensen**: One of the most important ones is one that we're working on that basically turns the telecommunications base stations into part of the AI infrastructure. So now all of the, it's a $2 trillion industry, all of that in time will be transformed into an extension of the AI infrastructure. And so radios, radios will become edge devices. Factories, warehouses, you name it. And so there are these three basic computers, all of them are going to be necessary.

</details>

### 推理的爆炸性增长与成本效率

**采访者**: 黄仁勋，去年，我认为你在全球都领先一步，指出推理不会像一年前那样增长一千倍。

<details>
<summary>Original English</summary>

**采访者**: Jensen, last year, I think you were ahead of the rest of the world in saying inference isn't going to a thousand last year.

</details>

**黄仁勋**: 是的，它会伤害我的感情吗？它会增长一百万倍吗？它会增长十亿倍吗？是的。

<details>
<summary>Original English</summary>

**Jensen**: Yes. Is it going to hurt my feelings? Is it going to 1 millionx? Is it going to 1 billionx? Yeah.

</details>

**采访者**: 对。我认为当时人们觉得这很夸张，因为世界仍然专注于预扩展和训练。而现在，推理已经爆发式增长。我们受到了推理的限制。你宣布了一个推理工厂，我认为它是领先的，它的吞吐量将比下一个工厂好十倍。但是，如果我听听外界的传言，那就是你的推理工厂将耗资400亿或500亿美元，而替代方案，定制ASIC、**AMD**等，将耗资250亿到300亿美元，你会失去市场份额。那么，你为什么不和我们谈谈呢？你看到了什么？你如何看待市场份额？对于所有这些人来说，支付比其他人营销的价格高两倍的溢价是否合理？最重要的结论是，你不应该把工厂的价格和令牌的价格，也就是令牌的成本等同起来。很可能，500亿美元的工厂，事实上我可以证明，500亿美元的工厂将为你产生最低成本的令牌。原因是我们以非凡的效率生产这些令牌，是10倍的效率。

<details>
<summary>Original English</summary>

**采访者**: Right. And I think people at the time thought it was pretty hyperbolic because the world was still focused on pre-scaling, on training. Here we are now. Inference has exploded. We're inference constrained. You announced an inference factory that I think is leading edge, that's going to be 10x better in terms of throughput to the next factory. But yet, if I listen to what the chatter is out there, it's that your inference factory is going to cost 40 or 50 billion, and the alternatives, the custom ASICs, AMD, others, are going to cost 25 to 30 billion, and you're going to lose share. So why don't you talk to us? What are you seeing? How do you think about share and does it make sense for all these folks to pay something that's a 2x premium to what others are marketing? The big takeaway, the big idea is that you should not equate the price of the factory and the price of the tokens, the cost of the tokens. It is very likely that the $50 billion factory, and in fact, I can prove it, that the $50 billion factory will generate for you the lowest cost tokens. And the reason for that is because we produce these tokens at extraordinary efficiency, 10 times.

</details>

**黄仁勋**: 你知道，500亿和200亿的差价，现在看来只是土地、电力和外壳的成本。

<details>
<summary>Original English</summary>

**Jensen**: You know, the difference between 50 billion, now it turns out 20 billion is just land, power and shell.

</details>

**采访者**: 除此之外，你还需要存储、网络、CPU、服务器和散热，所有这些都是必需的。GPU的价格是1倍还是0.5倍的差异……

<details>
<summary>Original English</summary>

**采访者**: And then on top of that, you have storage anyways, networking anyways, you got CPUs anyways, you got servers anyways, you got cooling anyways. The difference between that GPU being 1x price or halfx price...

</details>

**黄仁勋**: 并非在500亿和300亿之间。选择你喜欢的数字，但假设在500亿到400亿之间。

<details>
<summary>Original English</summary>

**Jensen**: Is not between 50 billion and 30 billion. Pick your favorite number, but let's say between 50 billion and 40 billion.

</details>

**采访者**: 当500亿美元的数据中心实际上拥有10倍的吞吐量时，这并不是一个很大的百分比。

<details>
<summary>Original English</summary>

**采访者**: That is not a large percentage when the $50 billion data center is actually 10 times the throughput.

</details>

**黄仁勋**: 对吧，Jess？这就是为什么我说，即使是大多数芯片，如果你跟不上技术的发展速度和我们前进的步伐，即使芯片是免费的，那也不够便宜。

<details>
<summary>Original English</summary>

**Jensen**: Right, Jess? That's the reason why I said that even for most chips, if you can't keep up with the state of the technology and the pace that we're running, even when the chips are free, it's not cheap enough.

</details>

**采访者**: 是的。我能问一个总体的战略问题吗？是的。我的意思是，你正在运营世界上最有价值的公司。明年这家公司将实现3500多亿美元的收入，2000亿美元的自由现金流。它正以惊人的速度增长。你如何决定该做什么？你如何获取信息？现在，那些人们应该发给你的电子邮件已经很有名了，但你如何真正决定，获得塑造市场、重点投入、适时撤退、以及进入新领域的直觉？这些信息如何传递给你？你如何做出这些决定？

<details>
<summary>Original English</summary>

**采访者**: Yeah. Can I just ask a general strategy question? Yeah. I mean, you're running the most valuable company in the world. This thing is going to do 350 plus billion of revenue next year. 200 billion of free cash flow. It's compounding at these crazy rates. How do you decide what to do? How do you actually get the information? It's famous now these sort of emails that are people are meant to send you, but how do you really decide to get an intuition of how to shape the market, where to really double down, where to maybe pull back, where to actually go into a green field? How does that information get to you? How do you decide these things?

</details>

**黄仁勋**: 归根结底，那是CEO的工作。我们的工作是定义战略，定义愿景，定义战略。当然，我们从杰出的计算机科学家、杰出的技术专家、公司里所有优秀的人那里获取信息，但我们必须塑造那个未来。其中一部分涉及到，这件事情是否难得令人发指？如果它不难做，我们就应该放弃它。原因在于，如果它很容易做，显然会有很多竞争者，很多竞争者。这是否是一件从未做过、难得令人发指、并且以某种方式利用了我们公司独特超能力的事情？所以我必须找到这种符合标准的事物组合。最终，我们也知道这将伴随着大量的痛苦和磨难。

<details>
<summary>Original English</summary>

**Jensen**: In a final analysis, that's the job of the CEO. And our job is to define the strategy, define the vision, define the strategy. We're informed, of course, by amazing computer scientists, amazing technologists, great people all over the company, but we have to shape that future. Part of it has to do with, is this something that's insanely hard to do? If it's not hard to do, we should back away from it. And the reason for that is if it's easy to do, obviously, lots of competitors, a lot of competitors. Is this something that has never been done before, that's insanely hard to do, and that somehow taps into the special superpowers of our company? And so I have to find this confluence of things that meets the standard. And in the end, we also know that a lot of pain and suffering is going to go into it.

</details>

**采访者**: 没有什么是通过轻松的第一次尝试就能发明出来的伟大事物。

<details>
<summary>Original English</summary>

**采访者**: There are no great things that are invented because it was just easy to do and just like first try, here we are.

</details>

**黄仁勋**: 所以如果这件事非常难做，以前没人做过，那很可能你会经历很多痛苦和磨难，所以你最好享受它。

<details>
<summary>Original English</summary>

**Jensen**: And so if it's super hard to do, nobody's ever done it before, it's very likely that you're going to have a lot of pain and suffering, and so you better enjoy it.

</details>

**采访者**: 那么你能谈谈你宣布的几项更长远的项目吗？比如太空数据中心，或者你在汽车**ADAS**领域，或者在生物学领域所做的努力。简单介绍一下你如何看待这些长尾业务的曲线正在向上拐点。

<details>
<summary>Original English</summary>

**采访者**: So can you just look at maybe three or four of the more long-tail things you announced and just talk about the long-term viability of whether it's the data centers in space or whether it's what you're trying to do with ADAS in autos or what you're trying to do on the biology side. Just give us a sense of how you see some of these curves inflecting upwards in some of these longer tail businesses.

</details>

**黄仁勋**: 非常好。**物理AI**是一个大类。我们相信，我刚才也提到了，我们有三个计算系统，以及其上所有的软件平台。物理AI是一个大类。它是科技行业第一次有机会解决一个50万亿美元的产业，这个产业在此之前基本上还没有被技术触及。所以，我们需要发明所有必要的技术来实现这一点。我觉得那是一段10年的旅程。我们10年前开始了，现在我们看到它正在发生拐点。这对我们来说是一个数十亿美元的业务。现在每年接近100亿美元。所以这是一个大业务，并且正在指数级增长。这是第一点。我认为在**数字生物学**方面，我们确实正处于数字生物学的“**ChatGPT**时刻”。我们即将了解如何表示基因、蛋白质、细胞。我们已经知道如何理解化学物质。因此，我们能够表示和理解生物学基本构建单元的动态，这大约是两三年后、五年后的事情。在五年内，我完全相信医疗保健行业，也就是数字生物学，将发生拐点。所以这些都是一些非常棒的领域，你可以看到它们就在我们身边。

<details>
<summary>Original English</summary>

**Jensen**: Excellent. **Physical AI** as a large category. We believe, and I just mentioned, we have three computing systems, all the software platforms on top of it. Physical AI as a large category. It's technology industry's first opportunity to address a $50 trillion industry that has largely been void of technology until now. And so, we need to invent all of the technology necessary to do that. I felt that that was a 10-year journey. We started 10 years ago. We're seeing it inflecting now. It is a multi-billion dollar business for us. It's close to $10 billion a year now. And so it's a big business and it's growing exponentially. And so that's number one. I think in the case of **digital biology**, I think we are literally near the **ChatGPT** moment of digital biology. We're about to understand how to represent genes, proteins, cells. We already know how to understand chemicals. And so the ability for us to represent and understand the dynamics of the building blocks of biology, that's a couple of two, three, five years from now. In five years' time, I completely believe that the healthcare industry where digital biology is going to inflect. And so these are a couple of the really great ones and you could see they're all around us.

</details>

**采访者**: 农业，现在正在反映。毫无疑问。

<details>
<summary>Original English</summary>

**采访者**: Agriculture, agriculture, reflecting now. No question.

</details>

### AI Agent的崛起与计算模式变革

**采访者**: 黄仁勋，我想把你从数据中心带到桌面。英伟达公司最初很大程度上是建立在业余爱好者、视频游戏玩家和那些图形卡的基础上的。你在这里，在大概一万人面前提到，我们只是在思考“开放AI代码”，而Agent已经带来了一场革命。具体来说，那些业余爱好者，他们是很多能量和创新的源泉，他们想要桌面电脑。你在这里宣布了一款，我相信是**戴尔6800**。这是一个非常强大的工作站，可以运行本地模型，拥有750GB的RAM。我的公司里所有地方的Mac Studio都卖光了。我们正在转向**OpenClaw**的一切。Freeberg刚被“Clawdelled”了。我听说你也“Clawpeld”了。你对这些非常着迷。这种从街头兴起的开源Agent和在桌面上使用开源的运动对你意味着什么？它将走向何方？

<details>
<summary>Original English</summary>

**采访者**: Jensen, I want to take you from the data center to the desktop. The company was built in large part on hobbyists, video gamers, and all those graphic cards in the beginning. And you mentioned in front of, I think, 10,000 people here, just clawed open, claw, clawed code, and what a revolution agents have become. And specifically, the hobbyists who are really where a lot of energy, we see a lot of the innovation breaks, want desktops. You announced one here. I believe it's the **Dell 6800**. This is a very powerful workstation to run local models, 750 gigs of RAM. The Mac Studio sold out everywhere in my company. We're moving to **OpenClaw** everything. Freeberg just got Clawdelled. You got Clawpeld, I understand. And you're obsessed with these. What is this from the streets movement of creating open-source agents and using open source on the desktop mean to you? Where is that going?

</details>

**黄仁勋**: 好的。首先，我们回顾一下。在过去两年里，我们基本上看到了三个拐点。第一个是生成式AI，**ChatGPT**将AI带入了大众的视野。但事实是，这项技术早在GPT出现前几个月就已存在。直到ChatGPT为其加上了用户界面，让它变得易于使用，生成式AI才真正腾飞。现在，你知道，生成式AI生成令牌供内部和外部消费。内部消费是思考，这导致了推理。01和03延续了ChatGPT的浪潮，提供了有根据的信息，使AI不仅能回答问题，还能以更具根据的方式回答问题，变得有用。我们开始看到**OpenAI**的收入和经济模型开始发生拐点。然后第三个，只有在行业内部我们才看到了**Claude Code**，第一个Agentic系统，它非常有用，是真正革命性的东西。但Claude Code只对企业开放。大多数外部人士从未听说过Claude Code，直到**OpenClaw**的出现。OpenClaw基本上将AI Agent能做什么带入了大众意识。这就是为什么OpenClaw从文化角度来看如此重要。现在，它之所以重要的第二个原因是，OpenClaw是开放的，但它构建了一种计算模型，这种模型基本上正在彻底重塑计算。它有一个内存系统。它有一个作为短期内存的文件系统。它有技能。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. So great. First of all, let's take a step back. In the last two years, we saw basically three inflection points. The first one was generative, ChatGPT, brought AI to common awareness. But the fact of the matter is the technology sat in plain sight months before GPT. It wasn't until ChatGPT put a user interface around it, made it easy for us to use, that generative AI took off. Now generative AI, as you know, generates tokens for internal consumption as well as external consumption. Internal consumption is thinking, which led to reasoning. 01 and 03 continue that wave of ChatGPT grounded information, made AI not only answer questions but answer questions in a more grounded way, useful. We started seeing the revenues and the economic model of **OpenAI** start to inflect. Then the third one was only inside the industry that we saw **Claude Code**, the first agentic system that was very useful, really revolutionary stuff. But Claude Code was only available for enterprises. Most people outside never saw anything about Claude Code until **OpenClaw**. OpenClaw basically put into the popular consciousness what an AI agent can do. That's the reason why OpenClaw is so important from a cultural perspective. Now, the second reason why it's so important is that OpenClaw is open, but it formulates, it structures a type of computing model that is basically reinventing computing altogether. It has a memory system. It scratch is a short-term memory file system. It has skills.

</details>

**采访者**: 你说的是技能还是规模？

<details>
<summary>Original English</summary>

**采访者**: Did you say skills or scales?

</details>

**黄仁勋**: 技能。

<details>
<summary>Original English</summary>

**Jensen**: Skills.

</details>

**采访者**: 哦，技能。理论上它们确实有规模。是的，是的，技能。

<details>
<summary>Original English</summary>

**采访者**: Oh, skills. They do have scales theoretically. Yeah. Yeah. Skills.

</details>

**黄仁勋**: 所以，第一件事是它拥有资源。它管理资源。它进行调度。

<details>
<summary>Original English</summary>

**Jensen**: So, the first thing, it has resources. It manages resources. It does scheduling.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yep.

</details>

**黄仁勋**: 对。它有Cron任务。它可以生成Agent。它可以分解任务，并导致和解决问题，就像调度一样。它有IO子系统。它可以输入。它可以输出。它可以连接到**WhatsApp**。它还有一个API，允许它运行多种类型的应用程序，称为技能。这四个元素从根本上定义了一台计算机。因此，我们拥有了什么？我们第一次拥有了一台个人人工智能计算机。

<details>
<summary>Original English</summary>

**Jensen**: And it cron jobs. It could spawn off agents. It could decompose a task and cause and solve problems. It does scheduling. It has IO subsystems. It could input. It has output. It connects to **WhatsApp**. And also it has an API that allows it to run multiple types of applications, called skills. These four elements fundamentally define a computer. And therefore, what do we have? We have a personal artificial intelligence computer for the very first time.

</details>

**采访者**: 开源的。

<details>
<summary>Original English</summary>

**采访者**: Open source.

</details>

**黄仁勋**: 它是开源的。它确实无处不在。所以，现在这是现代计算的蓝图，操作系统。而且它确实会无处不在。当然，我们必须帮助它做的一件事是，每当你有Agentic软件时，你必须确保Agentic软件可以访问敏感信息。它可以执行代码。它可以进行外部通信。我们必须确保所有这些都必须受到治理。所有这些都必须是安全的，并且我们有政策可以赋予这些Agent三件事中的两件，但不能同时拥有全部三件。因此，关于治理部分，我们为此做出了贡献，**Peter Steinberger**就在这里。我们有一大批优秀的工程师与他合作，帮助保护和维护这些，以保护我们的隐私，保护我们的安全。

<details>
<summary>Original English</summary>

**Jensen**: It's open source. It runs literally everywhere. And so this is now the blueprint, the operating system of modern computing. And it's going to run literally everywhere. Now, of course, one of the things that we had to help it do is whenever you have agentic software, you have to make sure that agentic software has access to sensitive information. It could execute code. It could communicate externally. We have to make sure that all of it has to be governed. All of it has to be secure and that we have policies that gives these agents two of the three things, but not all three things at the same time. And so the governance part of it, we contributed to **Peter Steinberger** was here. And so we've got a mountain of great engineers working with him to help secure and keep that thing so that it could protect our privacy, protect our security.

</details>

### AI立法与公共认知

**采访者**: 黄仁勋，这种范式转变使得一些已经在全国范围内通过的AI立法，以及许多拟议的法规，变得形同虚设，不是吗？你能不能就这种范式转变如何迅速地规避了许多AI监管模式，而AI监管正成为当前政治领域的一个热门话题，简单评论一下？

<details>
<summary>Original English</summary>

**采访者**: Jensen, that paradigm shift makes some of the AI legislation that has passed around the country to regulate AI and a lot of the proposed legislation effectively moot, doesn't it? Can you just comment for a second on how quickly the paradigm shift kind of obviates a lot of the models for regulatory oversight of AI, which is becoming a very hot topic in politics.

</details>

**黄仁勋**: 好的，这就是我们与政策制定者合作的部分，我们需要始终走在他们前面。布拉德，你在这方面做得很好。我们必须走在他们前面，向他们介绍这项技术的现状，它是什么，它不是什么。它不是生物。它不是外星生物。它没有意识。它就是计算机软件。

<details>
<summary>Original English</summary>

**Jensen**: Well, this is the part that we just with policymakers, we need to always get in front of them. And Brad, you do a great job doing this. We had to get in front of them and inform them about the state of the technology, what it is, what it is not. It is not a biological being. It is not alien. It is not conscious. It is computer software.

</details>

**采访者**: 是的。没错。

<details>
<summary>Original English</summary>

**采访者**: Yeah. Exactly.

</details>

**黄仁勋**: 而且它也不是我们说“我们根本不理解它”的东西。这不是真的。我们并非完全不理解。我们对这项技术有很多了解。所以，我认为首先，我们必须确保继续向政策制定者提供信息，不让悲观主义和极端主义影响政策制定者对这项技术的思考和理解。然而，然而，我们仍然必须认识到技术发展非常快，不要让政策过于超前于技术。我们作为一个国家所面临的风险。我们国家在AI方面的最大国家安全担忧是，当其他国家采纳这项技术时，我们却对它如此愤怒、如此恐惧，或以某种方式对它偏执，以至于我们的行业和社会不利用AI。所以我最担心的是AI在**美国**的传播。

<details>
<summary>Original English</summary>

**Jensen**: And it is not something that we say things like, "we don't understand it at all." It is not true. We don't understand at all. We understand a lot of things about this technology. And so I think one, we have to make sure that we continue to inform the policymakers and not allow doomerism and extremism to affect how policymakers think and understand about this technology. However, however, we still have to recognize the technology is moving really fast and don't get policy ahead of the technology too quickly. And the risk that we run as a nation. Our greatest source of national security concern with respect to AI is that other countries adopt this technology while we are so angry at it or afraid of it or somehow paranoid of it that our industries, our society don't take advantage of AI. And so I'm just mostly worried about the diffusion of AI here in the **United States**.

</details>

**采访者**: 你能再详细说说吗？如果你当时在**Anthropic**的董事会里，面对与国防部的争吵，它似乎建立在人们不知道该如何思考这一理念上。这似乎又增加了人们有时对AI软件层面产生的不满、恐惧或普遍的不信任感。你认为你会告诉**Daario**和他的团队做什么不同的事情，以试图改变一些结果和一些看法？

<details>
<summary>Original English</summary>

**采访者**: Can you just double-click if you were in the seat in the boardroom of **Anthropic** over that whole scuttlebutt with the department of war? It sort of builds on this idea of people didn't know what to think. It's sort of added to this layer of either resentment or fear or just general mistrust that people have sometimes at the software levels of AI. What do you think you would have told **Daario** and that team to do maybe differently to try to change some of this outcome and some of this perception?

</details>

**黄仁勋**: 关于Anthropic，首先我要说的是，他们的技术令人难以置信。我们是Anthropic技术的大用户。我们非常钦佩他们对安全的关注，非常钦佩他们对安全的重视。他们采取这种方式的文化，以及他们所展现的技术卓越，都非常出色。我想说的是，他们希望 предупредить人们了解这项技术的能力，这也很棒。我们只是必须确保我们理解世界是多样的，警告是好的，恐吓则不太好。因为这项技术对我们来说太重要了。我认为预测未来是没问题的，但我们需要更加谨慎。我们需要更谦逊一些，事实上我们无法完全预测未来，而且说一些相当极端、灾难性的事情，但却没有证据表明它会发生，可能会造成比人们想象的更大的损害。当然，我们是技术领导者。曾经有一段时间没有人听我们的。但现在，因为技术在社会结构中如此重要，如此重要的行业，对国家安全如此重要，我们的话语确实很重要，我认为我们必须更加谨慎。我们必须更加温和。我们必须更加平衡。我们必须更加深思熟虑。

<details>
<summary>Original English</summary>

**Jensen**: The first thing that I would say about Anthropic is, first of all, the technology is incredible. We are a large consumer of Anthropic technology. Really admire their focus on security, really admires their focus on safety. The culture by which they went about it, the technology excellence by which they went about it, really fantastic. I would say that the desire to warn people about the capability, the technology, is also really terrific. We just have to make sure that we understand that the world has a spectrum and that warning is good, scaring is less good. And because this technology is too important to us. And I think that it is fine to predict the future, but we need to be a little bit more circumspect. We need to have a little bit more humility that in fact we can't completely predict the future and to say things that are quite extreme, quite catastrophic that there's no evidence of it happening, could be more damaging than people think. And of course, we are technology leaders. There was a time when nobody listened to us. But now because technology is so important in the social fabric, such an important industry, so important to national security, our words do matter and I think we have to be much more circumspect. We have to be more moderate. We have to be more balanced. We have to be more thoughtful.

</details>

**采访者**: 嗯，你知道，我会提名你。我认为这个行业必须团结起来。AI在美国的受欢迎程度只有17%。我的意思是，我们看到了核能的遭遇，对吧？我们基本上关闭了整个核工业，现在中国正在建造100座裂变反应堆，而美国是零。我们听说有关于数据中心的禁令。所以我认为我们必须在这方面更加积极主动。但是，我想回到你在公司内部看到的这种Agentic爆炸，公司内部的效率和生产力提升。关于我们是否看到投资回报率（ROI），有很多争论。你和我在今年年初的时候，最大的问题是收入是否会出现？收入是否会像智能一样扩展？然后我们经历了一场**奥本海默时刻**，二月份Anthropic实现了50亿到60亿美元的月收入。你认为展望未来，你宣布了**Blackwell**和Vera Rubin未来几年将带来万亿美元的收入？当你看到Anthropic和OpenAI发生这种情况时，你认为我们现在正处于这个曲线上，收入将像智能一样扩展吗？

<details>
<summary>Original English</summary>

**采访者**: Well, I, you know, I would nominate you. I think the industry's got to get together. 17% popularity of AI in the United States. I mean, we see what happened to nuclear, right? We basically shut down the entire nuclear industry. And now we have 100 fission reactors being built in China and zero in the United States. We hear about moratoriums on data centers. So I think we have to be a lot more proactive about that. But I want to go back to this agentic explosion that you're seeing inside your company, the efficiencies, the productivity gains inside your company. There's a lot of debate whether or not we're seeing ROI. And you and I entering into this year, the big question was, are the revenues going to show up? Are the revenues going to scale like intelligence? And then we had this kind of Oppenheimer moment, a five-six billion month by Anthropic in February. Do you think as you look ahead, you announced a trillion dollar visibility into a trillion dollars of just **Blackwell** and Vera Rubin over the course of the next couple years? When you see this happening at Anthropic and OpenAI, do you think we're on that curve now where we're going to see revenues scale in the way that intelligence is scaling?

</details>

**黄仁勋**: 当你环顾这个听众时，你会看到Anthropic和OpenAI都出现在这里，但实际上，这里99%的所有事物都是AI，而不是Anthropic和OpenAI。原因在于AI非常多样化。我想说，第二受欢迎的模型类别是**开放模型**。第一位的是开源。OpenAI是第一位。开源是第二位。Anthropic则远远排在第三位。这说明了这里所有AI公司的规模。所以，认识到这一点很重要。让我回顾一下，说几件事。第一，当我们从生成式AI转向推理时，我们需要的计算量大约是100倍。当我们从推理转向Agentic时，计算量可能又是100倍。现在我们看到，仅仅两年时间，计算量就增加了10,000倍。同时，人们为信息付费，但人们主要为工作付费。

<details>
<summary>Original English</summary>

**Jensen**: When you look around this audience, you will see that Anthropic and OpenAI is represented here, but in fact, everybody, 99% of everything that is here is all AI and it's not Anthropic and OpenAI. And the reason for that is because AI is very diverse. I would say that the second most popular model as a category is open models. Number one is open source. OpenAI is number one. Open source is number two. Very distant third is Anthropic. And that tells you something about the scale of all of the AI companies that are here. And so it's important to recognize that. Let me come back and say a couple things. One, when we went from generative to reasoning, the amount of computation we needed was about a hundred times. When we went from reasoning to agentic, the computation is probably another 100 times. Now we're looking at, in just two years, computation went up by a factor of 10,000x. Meanwhile, people pay for information, but people mostly pay for work.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yes,

</details>

**黄仁勋**: 和聊天机器人对话并得到答案非常棒。

<details>
<summary>Original English</summary>

**Jensen**: talking to a chatbot and getting an answer is super great.

</details>

**采访者**: 帮助我做一些研究，令人难以置信。但是完成工作，我愿意为此付费。

<details>
<summary>Original English</summary>

**采访者**: Helping me do some research, unbelievable. But getting work done, I'll pay for it.

</details>

**黄仁勋**: 所以我们现在就处于这个阶段。Agentic系统能完成工作。它们正在帮助我们的软件工程师完成工作。所以，你有10,000倍的计算能力，你现在可能得到100倍的消耗。

<details>
<summary>Original English</summary>

**Jensen**: And so that's where we are. Agentic systems get work done. They're helping our software engineers get work done. And so then you take that, you got 10,000x more compute, you get probably at this point 100x more consumption now.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yes.

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah.

</details>

**黄仁勋**: 我们甚至还没有开始扩展。

<details>
<summary>Original English</summary>

**Jensen**: And we haven't even started scaling yet.

</details>

**采访者**: 我们绝对达到了百万倍的增长。我认为这很适合谈谈公司2万到3万名员工的数量。

<details>
<summary>Original English</summary>

**采访者**: We are absolutely at a millionx which is I think a great place to talk about the number of people have 20, 30,000 at the company something.

</details>

**黄仁勋**: 我们有43,000名员工。我想说38,000名是工程师。我们播客上多次讨论的话题是：“天哪，看看我们公司的令牌使用量，它正在大幅增长。”有些人会问：“嘿，当我加入一家公司时，我能得到多少令牌，因为我想成为一名高效的员工？”我相信你在两个半小时的精彩主题演讲中曾提出，你当时正在花费……

<details>
<summary>Original English</summary>

**Jensen**: We have 43,000 employees. I would say 38,000 are engineers. The conversation we've had on the pod a number of times is, "Oh my god, look at the token usage in our companies. It is growing massively." And some people are asking, "Hey, when I join a company, how many tokens do I get because I want to be an effective employee?" And you postulated, I believe, during your two and a half hour keynote, pretty long keynote, well done, that you were spending...

</details>

**采访者**: 如果做得好，会更短。他没有时间写一个小时的演讲稿。所以你们知道，这没有排练。所以这是一场引人入胜、激情四射的演讲。

<details>
<summary>Original English</summary>

**采访者**: If it was well done, it would be shorter. He didn't have time to write an hour. So you guys know, there is no practice. And so it's a gripping and ripping. Rip and rip. Yeah. So I just want to let you know I was writing the speech while I was giving the speech. So you never know.

</details>

**黄仁勋**: 我只是想告诉你，我是在演讲的时候写的演讲稿。好的，所以你永远不知道。

<details>
<summary>Original English</summary>

**Jensen**: I just want to let you know I was writing the speech while I was giving the speech. So you never know.

</details>

**采访者**: 但这是否意味着，如果我们做个粗略的计算，每个工程师大约75,000个令牌？那么，**英伟达**现在每年在工程团队的令牌上花费了10亿到20亿美元吗？

<details>
<summary>Original English</summary>

**采访者**: But does that mean if we do back-of-the-envelope math, 75,000 in tokens for each engineer or something like that? So, are you spending in **Nvidia** a billion, two billion dollars on tokens for your engineering team right now?

</details>

**黄仁勋**: 我们正在努力。让我给你一个思想实验。假设你有一名软件工程师或AI研究员，你每年付给他们50万美元。我们一直都这样做。好的，这种情况一直都在发生。那个年薪50万美元的工程师，在年底的时候，我会问他们，你们花了多少令牌？如果那个人说5000美元，我就会暴跳如雷。如果那个年薪50万美元的工程师没有消费至少25万美元的令牌，我就会深感不安。这和我们的一位芯片设计师说：“猜猜看？我只用纸笔。我想我不需要任何CAD工具。”没什么两样。

<details>
<summary>Original English</summary>

**Jensen**: We're trying to. Let me give you a thought experiment. Let's say you have a software engineer or AI researcher and you pay them $500,000 a year. We do that all the time. Okay, this is happening all over the time. That $500,000 engineer at the end of the year, I'm going to ask them how much did you spend in tokens? If that person said $5,000, I will go ape something else. If that $500,000 engineer did not consume at least $250,000 worth of tokens, I am going to be deeply alarmed. And this is no different than one of our chip designers who says, "Guess what? I'm just going to use paper and pencil. I don't think I'm going to need any CAD tools."

</details>

**采访者**: 这是一个真正的范式转变，开始思考这些全明星员工。这几乎让我想起了我们在**NBA**学到的东西，当时**勒布朗·詹姆斯**每年花费100万美元来维护他的身体健康。现在他41岁了还在打球。这真的是，如果这些是不可思议的知识工作者，我们为什么不赋予他们超人能力呢？没错。那会走向何方？如果我们推断未来两三年，英伟达的全明星员工的效率会是怎样的？他们能完成什么？他们会变成什么样子？嗯，首先，那些“哇，这太难了”的想法已经消失了。“这会花很长时间”的想法也消失了。“我们需要很多人”的想法也消失了。这与上次工业革命没什么不同。有人说：“天哪，那栋建筑看起来真重。”没人这么说。没人说：“哇，那座山看起来太大了。”没人这么说。

<details>
<summary>Original English</summary>

**采访者**: This is a real paradigm shift to start thinking about these all-star employees. It almost reminds me of what we learned in the NBA when **LeBron James** started spending a million dollars a year just on his health of his body and maintaining it. Here he is at age 41 still playing. It really is, if these are incredible knowledge workers, why wouldn't we give them superhuman abilities? That's exactly right. Where does that go? If we extrapolate out two or three years from now, what is the efficiency of that all-star at an Nvidia and what they're able to accomplish? What do they look like? Well, first of all, things that, "wow, this is too hard," that thought is gone. "This is going to take a long time," that thought is gone. "We're going to need a lot of people," that thought is gone. This is no different than in the last industrial revolution. Somebody goes, "Boy, that building really looks heavy." Nobody says that. Nobody, "wow, that mountain looks too big." Nobody says that.

</details>

**黄仁勋**: 对。所有那些“太大了”、“太重了”、“花太长时间”的想法，都已经消失了。

<details>
<summary>Original English</summary>

**Jensen**: Right. Everything that's too big, too heavy, takes too long, those thoughts, those ideas are all gone.

</details>

**采访者**: 你只剩下创造力了。没错。你能想出什么？

<details>
<summary>Original English</summary>

**采访者**: You're reduced to creativity. That's right. What can you come up with?

</details>

**黄仁勋**: 没错。这意味着现在的问题是如何与这些Agent合作？嗯，这只是一种新的计算机编程方式。过去我们编写代码。未来，我们将编写想法、架构、规范。我们将组织团队。我们将帮助他们定义如何评估好与坏。一个好的结果会是什么样子，如何与你迭代，如何进行头脑风暴。这才是你真正想要寻找的。我认为每个工程师都将拥有数百个Agent。

<details>
<summary>Original English</summary>

**Jensen**: Exactly. Which means now the question is how do you work with these agents? Well, it's just a new way of doing computer programming. In the past, we code. In the future, we're going to write ideas, architectures, specifications. We're going to organize teams. We're going to give him, we're going to help them define how to evaluate the definition of good versus bad. What does it look like when something is a great outcome, how to iterate with you, how to brainstorm. That's really what you're looking for. And I think that every engineer is going to have hundred hundred agents.

</details>

**采访者**: 回到行业现在面临的公关问题。你有一些高管，比如Oho的**David Freeberg**，他正在通过使用你的技术和AI，来计算产生的卡路里数量并生产高质量的卡路里。你认为你能将成本降低多少？这种愿景对你正在做的事情有什么影响？零样本基因组建模，而且它有效。然后你就有那样的时刻，你就像“天哪”……老实说，就像人们在一个晚上替换了整个企业软件堆栈之后。我用90分钟做了一件事。我告诉他们，用90分钟在Claude上替换了整个软件堆栈和一大堆工作负载，运行了这个Agentic系统，构建了整个东西，并部署了它，我们是在一个周日晚上完成的。周日晚上10点，我在11点半完成了，然后去睡觉了。

<details>
<summary>Original English</summary>

**采访者**: Back to the PR problem the industry has right now. You have executives like **David Freeberg** with Oho who's looking at literally taking through the use of technology, your technology and AI, the number of calories produced and making high quality calories. What is the factor you think you can bring the cost down Freeberg and what impact does this vision have for what you're doing? Zero shot genomic modeling, and it works. And then you have that moment and you're like, holy... Honestly, like, and that's after people are replacing entire enterprise software stacks in a night. I did something in 90 minutes. I was telling the guys about, replaced the whole software stack and a whole bunch of workload. 90 minutes on Claude, ran this agentic system, built the whole thing, deployed it, and we got, we were on a Sunday night. On a Sunday night, 10 p.m. I was done at 11:30. I went to bed.

</details>

**黄仁勋**: 作为CEO，你替换了……

<details>
<summary>Original English</summary>

**Jensen**: As the CEO, you replaced...

</details>

**采访者**: 是的。我管理团队的每个人都必须在周末做类似的练习。周一我们看到的情况，我当时想，结束了。但技术方面，科学方面，我们用**自动研究**在30分钟内完成了一些事情。我很想听听你对自动研究的看法，以及它告诉我们，在效率方面我们还有多远的路要走。但是，使用自动研究和一块数据，我们内部发表了一些东西，我们说：“天哪。”那通常会是一篇需要七年才能完成的博士论文。它将成为我们在该领域见过的最著名的博士论文之一，并将发表在《科学》杂志上。而它只用了30分钟，在一台台式电脑上运行自动研究，所有数据我们刚刚摄取。我们周五拿到它。我们想：“嘿，试试看。”启动了它，去了GitHub，下载了自动研究并运行了它，你看到每个人的脸上都露出了这样的表情。然后，这为我们解锁的潜力，就像那种需要七年才能完成的事情，它在30分钟内就发生了，我们正在基因组学中体验它，我们就像，这简直难以置信。所以我认为，这种加速正在以前所未有的方式拓宽每个人的视野，几年前你根本无法想象。但回到自动研究这一点，你能不能评论一下，这项东西在周末用600行代码就发表了，它能够在本地运行并利用这些多样化的数据集实现其目标的能力，以及这告诉我们，在算法和硬件优化方面，我们仍处于早期阶段。

<details>
<summary>Original English</summary>

**采访者**: Yeah. And everyone on my management team had to do a similar exercise over the weekend. What we saw on Monday, I was like, it's over. But the technical stuff, the science stuff, we did something in 30 minutes using auto research. And I'd love your view on auto research and what that tells us about how far we still have to go in terms of efficiency. But using auto research and a chunk of data, something was published internally that we said, "Oh my god." And that would normally be a PhD thesis that would take seven years. It would be one of the most celebrated PhD thesis we've ever seen in this field and it would be in the journal Science. And it was done in 30 minutes on a desktop computer running on auto research with all the data we just ingested. We got it on Friday. We're like, "Hey, let's try it." booted up, went to GitHub, downloaded auto research and ran it and you see everyone's face just go like. And then the potential of what this is unlocking for us is like the kind of thing that would take seven years and it happened in 30 minutes and we're experiencing it in genomics and we're like, this is unbelievable. So I think the acceleration is widening the aperture for everyone in a way that you didn't imagine a few years ago. But just going back to the auto research point, can you just comment on what you think about the fact that this thing got published with 600 lines of code in a weekend and the capacity that it has to run locally and achieve what it can achieve with all of these diverse data sets and what that tells us about the early stages we are in terms of optimization on algorithms and hardware.

</details>

**黄仁勋**: **OpenClaw**如此令人难以置信的根本原因，第一点，是它与大型语言模型突破的时机和结合。它的时机是完美的，无可挑剔。在很多方面，如果不是Claude和GPT以及ChatGPT已经达到了非常好的水平，Peter可能就不会想到它。它也是一种新的能力，允许这些模型使用我们长期以来创造的工具，比如网页浏览器和**Excel电子表格**，以及在芯片设计领域中的**Synopsys**和**Cadence**，还有Omniverse、**Blender**和**Autodesk**。所有这些工具都将继续被使用。有些人说企业IT软件行业将会被摧毁。让我给你一个不同的观点。企业软件行业受限于座位数量。它即将拥有多一百倍的Agent来使用这些工具。它们将是使用**SQL**的Agent，使用向量数据库的Agent，使用Blender的Agent，使用**Photoshop**的Agent。原因在于，这些工具首先做得非常好。其次，这些工具是最终分析中我们之间的纽带。当工作完成时，它必须以我能控制的方式呈现给我。而且我知道如何控制这些工具。所以我需要一切都回到Synopsys中。我希望一切都回到Cadence中，因为这就是我控制它的方式。这就是我的事实依据。

<details>
<summary>Original English</summary>

**Jensen**: The fundamental reason why **OpenClaw** is so incredible, number one, is its confluence, its timing with the breakthroughs in large language model. Its timing was perfect. It was impeccable. In a lot of ways Peter wouldn't have come up with it probably if not for the fact that Claude and GPT and ChatGPT have reached a level that is really very good. It is also a new capability that allows these models to tool use the tools that we've created over time, web browsers and **Excel spreadsheets** and in the case of chip design, **Synopsys** and **Cadence** and Omniverse and **Blender** and **Autodesk**. And all of these tools are going to continue to be used. Some people say that the enterprise IT software industry is going to get destroyed. Let me give you the alternative view. The enterprise software industry is limited by butts and seats. It's about to get a hundred times more agents banging on those tools. They're going to be agents banging on **SQL**. They're going to be agents banging on vector databases, agents banging on Blender, agents banging on **Photoshop**. And the reason for that is because those tools are first of all, do a very good job. Second, those tools are the conduit between us in the final analysis. When the work is done, it has to be represented back to me in a way that I can control. And I know how to control those tools. And so I need everything to be put back in the Synopsys. I want everything to put back in the Cadence because that's how I control it. That's how I've ground truth.

</details>

### 开源与AI的未来格局

**采访者**: 我想问你一个关于开源的问题。我们有这些闭源模型，它们非常出色。我们有这些**开源权重模型**。许多中国模型都令人难以置信。绝对令人难以置信。两天前，你可能没看到，因为你当时在台上忙着，但在一个名为**Bit Tensor Subnet 3**的加密项目中发生了一次训练运行。他们成功地训练了一个40亿参数的Llama模型，完全分布式，有很多人贡献了多余的算力，但他们能够有状态地完成并管理一次训练运行，我认为这是一个相当疯狂的技术成就。

<details>
<summary>Original English</summary>

**采访者**: Let me ask you a question about open source. So we have these closed source models. They're excellent. We have these openweight models. Many of the Chinese models are incredible. Absolutely incredible. Two days ago, you may not have seen this because you were busy on stage, but there was a training run that happened in this crypto project called **Bit Tensor Subnet 3**. They managed to train a 4 billion parameter llama model, totally distributed with a bunch of people contributing excess compute, but they were able to do it statefully and manage a training run, which I thought was like a pretty crazy technical accomplishment.

</details>

**黄仁勋**: 是的，因为它就像随机的人，每个人都分到一小份。

<details>
<summary>Original English</summary>

**Jensen**: Yeah, because it's like random people and each person gets a little share.

</details>

**采访者**: 我们的“在家折叠”的现代版本。

<details>
<summary>Original English</summary>

**采访者**: Our modern version of folding at home.

</details>

**黄仁勋**: 没错。那么你认为开源的最终状态会是怎样的？你是否也看到了架构的去中心化以及计算的去中心化，以支持开源权重模型，并采取完全开源的方法来确保AI能广泛普及给所有人？我相信我们从根本上需要将模型作为一流产品、专有产品，以及作为开源模型。这两者不是A或B的关系，而是A和B。毫无疑问。原因在于模型是一种技术，而不是产品。模型是一种技术，而不是服务。对于绝大多数消费者来说，横向层面的通用智能，我真的非常希望不用去微调自己的模型，对吧？我真的非常希望继续使用ChatGPT。我喜欢使用Claude，我喜欢使用**Gemini**，我喜欢使用X。它们都有自己的个性，你知道，这取决于我的心情，也取决于我试图解决什么问题。你知道，我可能会在X上做，或者在ChatGPT上做。所以，行业的这一部分正在蓬勃发展，它将非常棒。然而，所有这些行业的领域专业知识和专业化必须以他们能够控制的方式被引导和捕捉，而这只能来自**开放模型**。我们正在为开放模型行业做出巨大的贡献，它接近前沿。坦率地说，即使它达到了前沿，我认为“产品即服务”的世界，“模型即产品”的世界仍将继续蓬勃发展。

<details>
<summary>Original English</summary>

**Jensen**: Exactly. So what do you think about the end state of open source? Do you see this decentralization of architecture as well and decentralization of compute to support open weights and a totally open-source approach to making sure AI is broadly available to everyone? I believe we fundamentally need models as a first class product, proprietary product as well as models as open source. These two things are not A or B. It's A and B. There's no question about it. And the reason for that is because models is a technology, not a product. Model is a technology, not a service. For the vast majority of consumers, the horizontal layer, the general intelligence, I would really really love not to go fine-tune my own, right? I would really love to keep using ChatGPT. I'd love to use Claude. I love to use Gemini. I love to you use X. And they all have their own personalities as you know, which is kind of depends on my mood and depends on what problem I'm trying to solve. You know, I might, you know, do it on X or I might do it on on ChatGPT. And so that that segment of the of the industry is thriving. is going to be great. However, there all these industries their domain expertise their specialization has to be channeled has to be captured in a way that they can control and that it can only come from open models. The open model industry we're contributing tremendously to it is near the frontier and quite frankly even if it reaches the frontier I think that products as a service worldass products as a models as a product is going to continue to thrive.

</details>

**采访者**: 我们现在投资的每家初创公司都是先开源，然后再转向专有模型。

<details>
<summary>Original English</summary>

**采访者**: Every startup we're investing in now is open source first and then going to the proprietary models.

</details>

**黄仁勋**: 是的。美好的事情是，因为你有一个很棒的路由器，你把它连接起来，从第一天开始，你每天都将能够访问世界上最好的模型。然后它给你时间来降低成本，进行微调和专业化。所以你每次都将拥有世界级的性能。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. The beautiful thing is because you have a great router you connect it to by on on first day every single day you're going to have access to the world's best model and and then it gives you time to cost reduce and fine-tune and specialize and so you're going to have worldass capabilities out to shoot every single time.

</details>

**采访者**: 我能问个问题吗？

<details>
<summary>Original English</summary>

**采访者**: Let J can I ask a question?

</details>

### AI与地缘政治

**采访者**: 没人比你更希望美国赢得全球AI竞赛，对吧？但是一年前，拜登时代的扩散规则实际上是反美国AI全球扩散的。所以，现在新一届政府上任一年了。给我们打个分吧。我们在全球扩散以及美国AI技术向全球传播的速度方面处于什么位置？我们是A、B还是C？我们看到了什么有效，什么无效？

<details>
<summary>Original English</summary>

**采访者**: Nobody wants the US to win the global AI race more than you, right? But a year ago, the Biden era diffusion rule really was an anti-American diffusion of AI around the world. So here we are a year into the new administration. Give us a grade. Where is where are we in terms of global diffusion and the rate at which we're spreading US AI technology around the world? Are we an A? Are we a B? or we see what what's working, what's not working.

</details>

**黄仁勋**: 嗯，首先，特朗普总统希望美国工业领先。他希望美国科技工业领先。他希望美国科技工业获胜。他希望我们能将美国技术传播到世界各地。他希望美国成为世界上最富裕的国家。他想要所有这些。目前，就在我们说话的时候，英伟达在世界第二大市场失去了95%的市场份额，我们现在是0%。

<details>
<summary>Original English</summary>

**Jensen**: Well, first of all, President Trump wants American industry to lead. He wants American technology industry to lead. He wants American technology industry to win. He wants us to spread American technology around the world. He wants United States to be the wealthiest country in the world. He wants all of that. At the current moment, as we speak, Nvidia gave up a 95% market share in the second largest market in the world, and we're at 0%.

</details>

**采访者**: 特朗普总统，没错。特朗普总统希望我们能回到那里。第一件事是获得向我们能够销售的公司发放许可证。我们有很多公司已经申请了许可证。我们已经为他们申请了许可证，并获得了秘书长卢特尼克的批准。现在，我们已经通知了中国公司，其中许多公司已经向我们下了采购订单。所以我们将在恢复我们的供应链以进行运输。我认为在最高层面上，布拉德，我认为我们应该承认一件事：当我们在微型马达、稀土矿物方面无法获得供应时，我们的国家安全就会受损。当我们无法控制我们的电信网络时，国家安全就会受损。当我们无法为国家提供可持续能源时，国家安全就会受损。它从根本上受到了损害。这些行业中的每一个都是我不想让AI行业成为的例子。

<details>
<summary>Original English</summary>

**采访者**: President Trump, That's right. President Trump wants us to get back in there. And the first thing is to get licensed for the companies that we're going to be able to sell to. We've got many companies who have requested for licenses. We've applied for licenses for them and we've got approved licenses from sec secretary lutnik. Uh now we've we informed the Chinese companies and many of them have given us purchase orders and so we're going to we're going to we're in the process of cranking up our supply chain again to go ship. I think at the highest level Brad um I think one of the things that we should acknowledge is this. Our national security is diminished when we don't have access to miniature motors, rare earth minerals. It's diminished when we don't control our telecommunications networks. It's diminished when we can't provide for sustainable energy for our country. It is fundamentally diminished. Every single one of these industries is an example of what I don't want the AI industry to be.

</details>

**黄仁勋**: 对吧？当我们展望未来，我们想要什么？当美国科技行业、美国AI行业引领世界时，它会是什么样子？我们都可以承认，AI模型不可能普遍存在。我们可以承认，这样的结果毫无意义。然而，我们都可以想象，从芯片到计算系统再到平台的美国技术堆栈被世界广泛使用，他们在那里构建自己的AI，他们使用公共AI，他们使用私人AI等等，他们可以在他们的社会中构建他们的应用程序。我非常希望美国的技术堆栈能占世界90%。是的，我非常希望那样。另一种选择，如果它看起来像太阳能、稀土、磁铁、电机、电信，我认为那对国家安全来说是一个非常糟糕的结果。

<details>
<summary>Original English</summary>

**Jensen**: Right? When we look forward in time and we say what do we want? What is the what does it look like when American technology industry American AI industry leads the world? We can all acknowledge that there is no way that AI models is one universally. It is we can all acknowledge that that is an outcome that makes no sense. However, we can all imagine that the American tech stack from chips to computing systems to the platforms are used broadly by the world where they build their own AI, they use public AI, they use private AI whatever and they can build their applications in their society. I would love that the American tech stack is 90% of the world. Yes, I would love that. The alternative if it looks like solar, rare earth, magnets, motors, telecommunications, I consider that a very bad outcome for national security.

</details>

**采访者**: 同意。

<details>
<summary>Original English</summary>

**采访者**: Agreed.

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah.

</details>

**采访者**: 黄仁勋，你对目前世界各地的冲突情况监控得如何？这些情况让你有多担心？比如中国和台湾，以及从中东氦气供应的可获得性，我了解到这可能对半导体制造业构成供应链风险。这些情况让你有多担心？你为此投入了多少精力？

<details>
<summary>Original English</summary>

**采访者**: How much are you monitoring the situation with the conflicts around the world right now? And how much does it worry you Jensen? So, China and Taiwan and then helium availability coming out of the Middle East, I understand, can be a supply chain risk to semiconductor manufacturing. How much do these situations worry you? How much are you spending on them?

</details>

**黄仁勋**: 首先，我认为在中东，我们有6000个家庭在那里。

<details>
<summary>Original English</summary>

**Jensen**: Well, first of all, I think the in Middle East, I have we have 6,000 families there.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah,

</details>

**黄仁勋**: 我们在**英伟达**有很多伊朗人，他们的家人仍然在伊朗。所以我们有很多家庭在那里。首先，他们非常焦虑，非常担忧，非常害怕。我们一直在想着他们。我们一直在关注和留意他们。他们得到了我们100%的支持。我曾多次被问到，我们是否还在考虑留在以色列？我们100%留在以色列。我们100%支持那里的家庭。我们100%在中东。我也被问到，鉴于中东正在发生的事情，那是否是我们认为可以扩展人工智能的领域？我相信我们发动战争是有原因的，我相信战争结束后，中东将比以前更加稳定。所以如果我们以前在那里，如果我们以前考虑过，我们现在绝对应该考虑。所以我100%支持这一点。关于台湾，

<details>
<summary>Original English</summary>

**Jensen**: We have a lot of Iranians at NVIDIA and their families are still in Iran. And so so we have we have a lot of families there. The first thing is is they're quite anxious. They're quite concerned, quite scared. Um we're thinking about them all the time. Uh we're monitor and keeping an eye on them all the time. They have 100% of our support. Uh I've been asked several times, are we still considering uh being in Israel? We are 100% in Israel. We are 100% behind the families there. We are 100% in the Middle East. I was also asked, you know, given what's happening in the Middle East, uh is that an area where we believe that we can expand artificial intelligence to? Um I believe that there's a reason we went to war and I believe at the end of the war, Middle East will be more stable than before. And so if we were there, if we're considering it before, we should absolutely be considering it after. And so I'm 100% in on that. With respect to with with with respect to to Taiwan,

</details>

**黄仁勋**: 我们必须做三件事。第一，我们必须确保我们尽快将**美国**重新工业化。

<details>
<summary>Original English</summary>

**Jensen**: We have to do three things. One, we have to make sure that we re-industrialize the United States as fast as we can.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah.

</details>

**黄仁勋**: 无论是芯片制造厂、计算机制造厂，还是AI工厂。

<details>
<summary>Original English</summary>

**Jensen**: And whether it's the chip manufacturing plants, the the computer manufacturing plants, or the AI factors.

</details>

**采访者**: 我们在这方面做得怎么样？我们通过获得**台湾**供应链的战略支持和友谊，做得非常出色。通过获得他们的友谊，通过获得他们的支持，我们才能够以惊人的速度在亚利桑那州、德克萨斯州、加利福尼亚州进行建设。他们是真正的战略伙伴。我们，我们真的，他们值得我们的支持。他们值得我们的友谊。他们值得我们的慷慨，他们正在尽一切努力加速我们的制造过程。所以，所以我认为这是第一点。第二点，我们应该实现制造业供应链的多样化。无论是韩国、日本还是欧洲，我们都必须实现供应链的多样化，使其更具弹性。第三点，让我们保持克制。当我们减少……增加我们的多样性和弹性时，不要强行推动……

<details>
<summary>Original English</summary>

**采访者**: How are we doing on that? We're doing excellent with by by gaining the strategic support by gaining the friendship of the supply chain of Taiwan. By gaining their friendship, by gaining their support, we were able to build Arizona and Texas, California at incredible rates. They're they are genuinely a strategic partner. Um we we we really they deserve our support. They deserve our friendship. They deserve our uh generosity and they're doing everything they can to accelerate the manufacturing process for us. And so, so I think that's number one. Number two, we ought to diversify the manufacturing supply chain. And whether it's South Korea, whether it's it's Japan, it's Europe, we got to we got to diversify the supply chain, make it more resilient. And number three, let's be let's let's demonstrate restraint. And while we're reducing uh increasing our diversity and resilience, let's not press push um you know

</details>

**黄仁勋**: 不必要的，我们需要有耐心。

<details>
<summary>Original English</summary>

**Jensen**: unnecessary we need to be patient.

</details>

**采访者**: 氦气是个问题吗？

<details>
<summary>Original English</summary>

**采访者**: Is helium a problem?

</details>

**黄仁勋**: 很多报道，你知道，我认为氦气可能是一个问题，但供应链中也可能有很多缓冲。

<details>
<summary>Original English</summary>

**Jensen**: A lot of reports, you know, I think helium could be a problem, but it's also the case that the supply chain probably has a lot of buffer in it.

</details>

**采访者**: 这类事情往往有很多缓冲。但，嗯，你知道。

<details>
<summary>Original English</summary>

**采访者**: These kind of things tend to have a lot of buffer. Uh but but um you know

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah,

</details>

### 自动驾驶与机器人

**黄仁勋**: 你在自动驾驶方面取得了巨大进展。你发布了一个重大声明。你增加了许多合作伙伴，包括**比亚迪**。你驾驶一辆**梅赛德斯**的视频刚刚发布。还有一个与**优步**的重大声明，你将让许多来自不同制造商的汽车上路。我相信你的赌注是，将有一个Android式的开源平台，你将在其中扮演重要角色，拥有数十家汽车供应商。而另一方面，可能有一个**iOS**，与**特斯拉**或**Waymo**合作。你的战略思维是什么？这个棋局将如何演变？因为感觉你有一个相当深的堆栈，在某些方面你在竞争，在另一些方面你在合作。是的。嗯，退一步讲。我们相信，一切移动的物体总有一天会完全或部分实现自主。第一。第二，我们不想制造自动驾驶汽车，但我们想让世界上每一家汽车公司都能制造自动驾驶汽车。所以，我们构建了所有三台计算机：训练计算机、模拟计算机、评估计算机，以及汽车计算机。我们开发了世界上最安全的驾驶操作系统。我们还创建了世界上第一个**推理自动驾驶汽车**，这样它就能将复杂的场景分解成更简单的场景，并知道如何像我们人类推理系统一样导航。因此，那个名为**Al Pomayo**的推理系统使我们能够取得令人难以置信的成果。我们进行垂直优化。我们进行水平创新，我们让每个人自己决定。你想从我们这里购买一台计算机吗？就**埃隆**和特斯拉而言，他们购买我们的训练计算机。嗯，他们想购买我们的训练计算机和我们的模拟计算机吗？或者你希望我们与你合作，完成所有三项，甚至将汽车计算机放入你的汽车中。所以，你知道，我们的态度是我们想解决问题。我们不是解决方案提供商。我们很高兴无论你如何与我们合作。让我基于这个问题进行阐述，因为它太引人入胜了。你确实创建了这个平台。千花齐放。

<details>
<summary>Original English</summary>

**Jensen**: You've made massive progress in self-driving. You made a big announcement. You've added many more partners including **BYD**. There was just a video of you driving around in a **Mercedes** and huge announcement with **Uber** that you're going to have a number of cars on the road from many different manufacturers. Your bet is I believe that there's going to be an Android type open-source platform that you're going to play a major part in with dozens of car providers and then maybe on the other side there could be an iOS with **Tesla** or **Waymo**. What's your strategy thinking there and how that chessboard emerges because it feels like you have a a pretty deep stack and in some ways you're competing and in other places you're collaborative. Yeah. Um, it's taking a step back. We believe that everything that moves will be autonomous completely or partly someday. Number one. Number two, we don't want to build self-driving cars, but we want to enable every car company in the world to build self-driving cars. And so, we built all three computers, the training computer, the simulation computer, the valuation evaluation computer, as well as the car computer. We develop the world's safest driving operating system. Uh we also created the world's first **reasoning autonomous vehicle** so that it could decompose complicated scenarios into simpler scenarios that it knows how to navigate through just like us reasoning systems. And so that reasoning system called **Al Pomayo** has enabled us to achieve incredible results. We open this we ver we vertical optimization. We horizontally innovate and we let everybody decide. Do you want to buy one computer from us? In the case of **Elon** and Tesla, they buy our training computers. Um, do they want to buy our training computer and our simulation computers or do you want to let us uh work with us to do all three and even put the car computer in your car. So, we, you know, our attitude is we want to solve the problem. We're not the solution provider. And we're delighted however you work with us. Let me build on this question because I think it's like it's so fascinating. You actually do create this platform. A thousand flowers are blooming.

</details>

**采访者**: 但也有一些花现在想回到堆栈的更底层，试图与你竞争。**谷歌**有**TPU**，**亚马逊**有**Inferentia**和**Tranium**。你知道，每个人都在推出自己的版本，认为自己可以超越英伟达。尽管他们也往往是你的大客户。你如何应对这种情况？你认为随着时间的推移会发生什么？这些东西在这种愿景的复杂组合中扮演什么角色？

<details>
<summary>Original English</summary>

**采访者**: But it's also true that some of those flowers want to now go back down in the stack and try to compete with you a little bit. **Google** has **TPU**, **Amazon** has **Inferentia** and **Tranium**. You know, everybody's sort of spinning up their own version of I think I can out Nvidia Nvidia even though they also tend to be huge customers. How do you navigate that? And what do you think happens over time and where do those things play in the complexion of this kind of vision?

</details>

**黄仁勋**: 是的，非常棒。首先，我们是唯一的AI公司，我们是一家AI公司。我们构建基础模型。我们在许多不同的领域都处于前沿。我们构建每一个层面，每一个堆栈。嗯，我们是世界上唯一一家与世界上所有AI公司合作的AI公司。他们从不给我看他们在构建什么，而我总是向他们展示我正在构建什么。

<details>
<summary>Original English</summary>

**Jensen**: Yeah, really great. You know, first of all, um, we're the only AI company, we're an AI company. We build foundation models. We're at the frontier in many different domains. We build every single every single layer, every single stack. Um, we're the only AI company in the world that works with every AI company in the world. They never show me what they're building and I always show them exactly what I'm building.

</details>

**采访者**: 对。

<details>
<summary>Original English</summary>

**采访者**: Right.

</details>

**黄仁勋**: 是的。所以这种信心来自于这一点。嗯，我们乐于在最佳技术上竞争，并且只要我们能继续快速发展，我相信购买**英伟达**的产品仍然是他们能做的最经济的事情，这给了我们巨大的信心。第一点。第二点，我们是唯一一种可以在所有云中使用的架构，这给了我们一些根本性的优势。我们是唯一一种可以从云端取出并放入本地、汽车和任何地区的架构。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. And so so the confidence comes from this one. Uh we are delighted to compete on what is the best technology and to the extent that to the extent that we can continue to run fast I believe that buying from Nvidia still is one of the most economic things they could do and that's just incredible confidence there. Number one. Number two, we're the only architecture that could be in every cloud and that gives us some fundamental advantages. We're the only architecture you could take from a cloud and put into onrem in the car in any region

</details>

**采访者**: 在太空中。

<details>
<summary>Original English</summary>

**采访者**: in space.

</details>

**黄仁勋**: 没错。在太空中。所以我们市场中有很大一部分，大约40%的业务，大多数人没有意识到，除非你有**CUDA**堆栈，除非你能建立一个完整的AI工厂，否则客户不知道该怎么做。他们不是想造芯片。他们不是想买芯片。他们想建立AI基础设施。所以他们希望你带着完整的堆栈来。我们拥有完整的堆栈。所以令人惊讶的是，**英伟达**正在获得市场份额。如果你看看我们今天所处的位置，我们正在获得份额。

<details>
<summary>Original English</summary>

**Jensen**: That's right. In space. And so there's a whole whole part of our market about 40% of our of our business most people don't realize this 40% of our business unless you have the **CUDA** stack unless you can build an entire AI factory you have the customers don't know what to do with you. They're not trying to build chips. They're not trying to buy chips. They're trying to build AI infrastructure. And so they want you to come in with the full stack. And we've got the whole stack. And so surprisingly, Nvidia is gaining market share. If you look at where we are today, we're gaining share.

</details>

**采访者**: 你认为会发生什么？这些人尝试了之后，意识到“天哪，这太多了”，然后他们又回来了。这就是份额增长的原因吗？

<details>
<summary>Original English</summary>

**采访者**: Do you think what happens is these guys try and they realize, oh my god, it's too much. And then they come back. Is that why the share grows?

</details>

**黄仁勋**: 嗯，我们获得份额有几个原因。第一，我们的速度提升了。我们帮助人们意识到，重要的不是制造芯片，而是构建系统。而那个系统真的很难构建。所以他们与我们的业务正在增加。就**AWS**而言，我认为他们昨天宣布，他们将在未来几年购买一百万枚芯片。我的意思是，这对于AWS来说是大量的芯片。这还不包括他们已经购买的所有芯片。所以，我们很高兴能这样做。但首先，过去几年我们获得了份额，因为现在**Anthropic**正在与**英伟达**合作。**Meta SL**也正在与英伟达合作。开放模型的增长令人难以置信。所有这些都在英伟达上。所以我们正在因为模型的数量而获得份额。我们也在获得份额，因为所有这些公司都在云之外，它们正在区域性地在企业和边缘行业中增长，而这整个增长领域，如果你只是构建一个ASIC，就很难实现。

<details>
<summary>Original English</summary>

**Jensen**: Well, we're gaining share for several reasons. One, um, our velocity has gone, we help people realize it's not about building the chip, it's about building the system. And that system is really hard to build. Uh and and so their their their business with us is increasing. In the case of **AWS**, I think they just announced, I think it was yesterday, that they're going to buy a a million chips uh in the next couple years. I mean, that's a lot of chips from from AWS. And that's on top of all the chips they've already bought. And so, we're delighted to do that. But number one, we're gaining share this last couple years because we now have Anthropic coming to Nvidia. **Meta SL** is coming to Nvidia. And the growth of open models is incredible. And that's all on Nvidia. And so we're growing in share because of the number of models. We're also growing in share because out all of these companies are outside of the cloud and they're growing regionally in enterprise in industries at the edge and that entire segment of growth is you know really hard to do if it's just building an as

</details>

**采访者**: 布拉德，关于这个，嗯，不深入数字细节，但分析师似乎不相信，对吧？所以如果你看看共识预测，你说计算可以增长一百万倍，对吧？然而他们预测你明年增长30%，后年增长20%。到了2029年，一个本该是巨大的一年，却只有7%。对吧？所以如果你拿你的总潜在市场（TAM），然后套用他们的增长数字，那意味着你的份额将暴跌。在你的未来订单簿中，你看到了什么会证实这一点吗？

<details>
<summary>Original English</summary>

**采访者**: Brad related to that um and not to get in the weeds on the numbers but analysts don't seem to believe right so if you look at the consensus forecast you said compute could 1 millionx right and Yet they have you growing next year at 30%, the year after that at 20%. And in 2029, which is supposed to be a monster year at 7%. Right? So if you just if you take your TAM and you apply their growth numbers, it suggests that your share will plummet. Do you see anything in your future order book that would make that correct?

</details>

**黄仁勋**: 是的。首先，他们只是不理解AI的规模和广度。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. First of all, they just don't understand the scale and the breadth of AI.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yes.

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah.

</details>

**采访者**: 我认为这是真的。大多数人认为AI只存在于前五大超大规模企业中，对吧？没错。还有一种关于**大数定律**的传统观念。

<details>
<summary>Original English</summary>

**采访者**: I think that's true. Most people think that AI is in the top five hyperscalers, right? That's right. There's also an orthodoxy around these law of large numbers where,

</details>

**黄仁勋**: 你知道，他们必须回到他们的投资银行风险委员会，展示一些模型。

<details>
<summary>Original English</summary>

**Jensen**: you know, they have to go back to their investment banking risk committee and show some model.

</details>

**采访者**: 他们不会相信，在他们看来，5万亿会变成15万亿。他们会认为它只能变成7万亿，或者他们可以拥有一个10万亿的公司。

<details>
<summary>Original English</summary>

**采访者**: They're not going to believe in their minds that 5 trillion goes to 15 trillion. They're like go to it can go to seven or they can have a 10 trillion company.

</details>

**黄仁勋**: 这只是些中情局的东西，我认为从未发生过。所以你不能说它会发生。

<details>
<summary>Original English</summary>

**Jensen**: It's all just CIA stuff that I think it's never happened before. So you can't say it will

</details>

**采访者**: 而且因为你必须重新定义你所做的事情。最近有人评论说，**英伟达**，黄仁勋，你怎么能比**英特尔**在服务器领域更大？原因在于，整个数据中心的CPU市场大约每年250亿美元。

<details>
<summary>Original English</summary>

**采访者**: and and because because you have to redefine what it is that you do. There was somebody who made an observation recently that Nvidia Jensen how can you be larger than Intel in servers and the reason for that is because the CPU market of the entire data center was about $25 billion a year,

</details>

**黄仁勋**: 对吧？

<details>
<summary>Original English</summary>

**Jensen**: right?

</details>

**采访者**: 我们每年做250亿美元，就像你们知道的，在我们坐在这里的这段时间里。

<details>
<summary>Original English</summary>

**采访者**: We do $25 billion a year as you guys know in a very in the time that we were sitting here.

</details>

**黄仁勋**: 所以很明显，很明显。

<details>
<summary>Original English</summary>

**Jensen**: And so obviously obviously

</details>

**采访者**: 那是个笑话。不，但它是**All-In播客**。别担心。这个节目上的一切都差不多。别担心。一切都在这里。总之，那不是指导。但无论如何，无论如何，重点是你能有多大。

<details>
<summary>Original English</summary>

**采访者**: That was a joke. No, it's but it's All-In podcast. Don't worry. Everything on this show is roughly. Don't worry about it. It's all in here. Anyway, that was not guidance. But anyhow, anyhow, it the the point is how big you can be

</details>

**黄仁勋**: 取决于你制造什么。

<details>
<summary>Original English</summary>

**Jensen**: depends on what is it that you make,

</details>

**采访者**: 对吧？英伟达不是在制造芯片。第一，制造芯片不再能帮助你解决AI基础设施问题了。它太复杂了。第三，大多数人认为AI只局限于他们谈论、听到和看到的东西。

<details>
<summary>Original English</summary>

**采访者**: right? Nvidia is not making chips. Number one, making chips does not help you solve the AI infrastructure problem anymore. It's too complicated. Number three, most people think that AI is narrowly in the things that they talk about and hear and see.

</details>

**黄仁勋**: Open AI令人难以置信。它们将变得非常庞大。**Anthropic**令人难以置信。它们也将变得非常庞大。但AI将比这大得多。

<details>
<summary>Original English</summary>

**Jensen**: It's AI is much open AI is incredible. They're going to be enormous. Anthropic is incredible. They're going to be enormous. But AI is going to be much much bigger than that.

</details>

**采访者**: 我们解决了那个细分市场。

<details>
<summary>Original English</summary>

**采访者**: And we addressed that segment.

</details>

**采访者**: 简单说一下太空中的数据中心。

<details>
<summary>Original English</summary>

**采访者**: Tell us about data centers in space for a second.

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah.

</details>

**采访者**: 嗯。

<details>
<summary>Original English</summary>

**采访者**: Um

</details>

**黄仁勋**: 我们已经在太空中了。普通人应该如何看待这项业务，与你在地面上听到的那些大型数据中心建设有什么不同？

<details>
<summary>Original English</summary>

**Jensen**: We're already in space. How should the layman think about what that business is versus when you hear about these big data center buildouts that's happening in in on the ground?

</details>

**黄仁勋**: 嗯，我们当然应该先在地面上努力，因为我们已经在这里了，这是第一。第二，我们应该准备好进入太空，显然太空中有很多能量。嗯，当然，挑战在于散热，你无法利用传导和对流，所以你只能使用辐射，而辐射需要非常大的表面积。所以现在，这不是一个无法解决的问题，而且太空中有很多空间。嗯，但无论如何，费用仍然相当高。我们会去探索它。我们已经在那里了。我们已经**抗辐射强化**。我们在世界各地的卫星中都有**CUDA**。它们正在进行成像、图像处理、AI成像。而且这种工作应该在太空中完成，而不是把所有数据都传回地球来做成像。我们应该直接在太空中进行成像。所以有很多事情我们应该在太空中完成。同时，我们将探索太空中的数据中心架构会是什么样子。这需要很多年。没关系。我们有充足的时间。我想深入探讨医疗保健。我知道你在那方面投入了大量精力。我们都到了一个年龄，开始思考寿命和健康寿命。我的意思是，我们看起来都很好。

<details>
<summary>Original English</summary>

**Jensen**: Well, we should definitely work on the ground first because we're already here and number one. Number two, we should prepare to be out in space and obviously there's a lot of energy in space. Um the challenge of course is that cooling you can't take advantage of conduction and convection and so you can only use radiation and radiation requires very large surfaces and so now that's not an impossible thing to solve and there's a lot of lot of space in space. Um but nonetheless the expense is still quite there is is there uh we're going to go explore it. We're already there. We're already radiation hardened. Uh we have we have uh uh uh **CUDA** in satellites around the world. Um they're doing imaging, image processing, AI imaging and um and that kind of stuff ought to be done in space instead of sending all the data back here and do imaging down here. We ought to just do imaging out in space. And so there's a lot of things that we ought to done do do in space. And in the meantime, uh we're going to explore what is the architecture of data centers look like uh in space. And it'll take it'll take years. It's okay. We got I got plenty of time. I wanted to um double click on healthcare. I know you've got a big effort there. We're all of a certain age where we're thinking about lifespan, health span. I mean, we all look great.

</details>

**采访者**: 有些比其他人好。

<details>
<summary>Original English</summary>

**采访者**: some better than others.

</details>

**黄仁勋**: 我认为有些比其他人好。我不知道你的秘密是什么，黄仁勋。

<details>
<summary>Original English</summary>

**Jensen**: I think some better than others. I don't know what your secret is, Jensen.

</details>

**采访者**: 相当不错。我的意思是，你吃了什么？你有什么禁忌？我们在后台的时候你得告诉我。我想知道你在休息室里有什么秘诀。

<details>
<summary>Original English</summary>

**采访者**: Pretty good these these I mean, what's what are you taking? What's off the menu? You got to talk to me when we're backstage. I want to know in the green room what you got going on.

</details>

**黄仁勋**: 深蹲、俯卧撑和仰卧起坐。

<details>
<summary>Original English</summary>

**Jensen**: Squats and push-ups and sit-ups.

</details>

**采访者**: 完美。好的。嗯，但这有效。你知道在医疗保健建设方面，它将走向何方？我们正在取得怎样的进展？我刚刚还在用Claude做一些分析，说这些账单代码都在哪里？我们在美国花了双倍的钱，似乎只得到了减半的效果。看起来，15%到25%的支出都花在了初次全科医生就诊上。我认为我们都知道，ChatGPT和大型语言模型在初次就诊时做得更好，而且更稳定。那么，要突破所有这些监管，让AI对医疗保健系统产生真正的影响，需要发生什么？

<details>
<summary>Original English</summary>

**采访者**: Perfect. Okay. Um but that works. what you know in terms of the buildout in healthcare where is that going and what kind of progress are we making? I was just using Claude to do some analysis and saying like where are all these billing codes? We spend twice as much money in the US. We get seem to get half as much. It seemed like uh 15 to 25% of the dollar spent were on these first GP visits. And I think we all know like ChatGPT and a large language model does a better job more consistently today at a first visit. So what has to happen there to kind of break through all that regulation and have AI have a true impact on the health care system?

</details>

**黄仁勋**: 我们在医疗保健领域涉及几个方面。一个是AI物理学，也就是AI生物学，利用AI来理解、表示和预测生物行为。所以这是一个在药物发现中非常重要的方面。第二个是**AI Agent**，这就是协助和帮助诊断之类的应用。**Open Evidence**就是一个很好的例子。**Hypocratic**也是一个很好的例子。我喜欢与这些公司合作。我真的认为这是一个Agentic技术将彻底改变我们与医生互动以及我们寻求医疗保健方式的领域。我们涉及的第三个方面是**物理AI**。第一个是AI物理学，利用AI预测物理学。第二个是物理AI。AI理解物理定律的特性，这用于机器人手术，有大量的活动。未来医院里我们互动的每一种仪器，无论是超声波还是CT，或者任何仪器，都将是Agentic的。

<details>
<summary>Original English</summary>

**Jensen**: There's several way several areas that we're involved in in um in healthcare. One is uh AI uh physics uh and and that's or AI biology using AI to understand represent predict biology behavior biological behavior and so that's one that's very important in drug discovery. There's second which is **AI agents** and that's where the assistance and helping diagnosis and things like that. **Open Evidence** is a really good example. **Hypocratic** is a really good example. Love working with those companies. Um I really think that this is an area uh where agentic technology is going to revolutionize how we interact with doctors and how do we interact for healthcare. The third part that we're in involved in is **physical AI**. The first one is AI physics using AI to predict physics. The second one is physical AI. AI that understand the properties of the laws of physics and that's used for a uh robotic surgery huge amounts of activities there. Every single instrument whether it's ultrasound or you know CT or whatever instrument we interact with in a hospital in the future will be agentic.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah.

</details>

**黄仁勋**: 你知道，安全的OpenClaw版本将存在于每一种仪器中。所以在很多方面，那种仪器将以一种非常独特的方式与患者、护士和医生互动。对AI武器进行了如此多的投资。如果能看到对AI急救人员和护理人员进行一些投资，从而挽救生命，而不仅仅是夺走生命，那将是极好的。我认为这是一个很好的过渡到机器人学的话题。你有很多合作伙伴。我们有一个非常奇怪的……

<details>
<summary>Original English</summary>

**Jensen**: You know, open claw in a safe version will be inside every single instrument. And so in a lot of ways that instrument is going to be interacting with patients and nurses and doctors in a very unique way. so much investment in AI weapons. It would be wonderful to see some investment in AI EMTs and paramedics and saving lives, not just taking them, which I think is a great segue into robotics. You've got dozens of partners. We have this very weird

</details>

**采访者**: 我不知道，我想称之为波士顿动力公司迷失的十年或二十年。**谷歌**收购了一堆公司。然后他们又把它们卖掉并剥离了出去，人们普遍认为机器人技术还没有准备好黄金时代。而现在我们有了世界上最伟大的企业家，埃隆·马斯克，做得很好，希望我挽救得及时。**Optimus**，相当令人印象深刻。还有中国的其他公司。它离真正进入我们的生活还有多远？我们可能会看到机器人厨师、机器人护士、机器人管家，你知道，这种人形因素真正在现实世界中发挥作用，了解你与那些合作伙伴的合作情况，特别是中国，他们在机器人方面似乎做得和我们一样好，甚至更好。

<details>
<summary>Original English</summary>

**采访者**: I don't know I want to call a lost decade or 20 years of **Boston Dynamics**. **Google** bought a bunch of companies. They then wound up selling them and spinning them out where people just thought robotics is just not ready for prime time. And now here we have the world's greatest entrepreneur at this time. Uh tied with you, uh **Elon Musk** doing well, that was a good save, I hope. **Optimus**, uh pretty impressive. And then other companies in China. How how close is that to actually being in our lives where we might see a chef, a robotic chef, a robotic nurse, a robotic housekeeper, you know, this humanoid factor actually working in the real world, knowing what you know with those partners and the fidelity, especially in China where they seem to be doing as good a job as we're doing here or maybe better.

</details>

**黄仁勋**: 嗯，我们主要发明了这个行业。美国发明了。你可以说我们介入得太早了。

<details>
<summary>Original English</summary>

**Jensen**: Um, we invented the industry largely. America invented. We c you could argue we got into it too soon.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah.

</details>

**黄仁勋**: 我们变得疲惫不堪。我们累了。在大约五年之后，使能技术才出现。

<details>
<summary>Original English</summary>

**Jensen**: And and we got exhausted. We got tired um about five years before the enabling technology appeared.

</details>

**采访者**: 大脑。

<details>
<summary>Original English</summary>

**采访者**: The brain.

</details>

**黄仁勋**: 是的，是的。我们只是过早地感到疲倦了。好的。这是第一点。但现在它来了。现在的问题是还要多久？从高功能的存在证明，到合理的产品，技术从来不会超过两三个周期。所以两三个周期基本上就是三年到五年。就这么简单。三年到五年，我们将到处都是机器人。我认为，嗯，中国很强大，原因在于他们的微电子、电机、稀土、磁铁，这些都是机器人技术的基础。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. Yeah. And we we just got tired of it just a little too soon. Okay. That's number one. But it's here now. Now the question is how much longer? From the point of high functioning existence proof, high functioning exist existence proof to reasonable products technology never takes more than a couple two three cycles. And so a couple two three cycles basically be somewhere around 3 years to 5 years. That's it. 3 years to 5 years we're going to have robots all over the place. Uh I think I think um uh China is is uh formidable and the reason for that is because their micro electronics, their uh motors, their rare earth, their magnets, which is foundational to robotics,

</details>

**黄仁勋**: 他们是世界上最棒的。所以在很多方面，我们的机器人行业深深依赖于他们的生态系统和供应链。而且，嗯，他们显然发展非常快。嗯，我们的机器人行业将不得不大量依赖它。世界的机器人行业将不得不大量依赖它。所以，所以我认为，你会在这里看到一些快速的进展。

<details>
<summary>Original English</summary>

**Jensen**: they are the world's best. And so in a lot of ways, our robotics industry relies deeply on their ecosystem and their supply chain. Um and uh and and they're, you know, obviously moving very quickly. Uh we're going to, you know, our robotics industry will have to rely a lot on it. the world's robotics industry will have to rely on a lot on it. And so so I think um you're gonna see some fast fast movements here.

</details>

**采访者**: 最终，一对一。埃隆似乎认为我们将拥有一个机器人对应一个人。70亿对70亿，80亿对80亿。

<details>
<summary>Original English</summary>

**采访者**: Ultimately, one for one. Elon seems to think we're going to have one robot for every human. 7 billion for 7 billion, 8 billion for 8 billion.

</details>

**黄仁勋**: 嗯，我希望更多。是的，我希望更多。是的。嗯，首先，将会有很多机器人在工厂里全天候工作。将会有很多工厂……它们不动。它们移动一点点。几乎所有东西都将是机器人。世界会变成什么样子？

<details>
<summary>Original English</summary>

**Jensen**: Well, I'm hoping more. Yeah, I'm hoping more. Yeah. Uh well, first of all, there's a whole bunch of robots that are going to be in factories working around the clock. There's going to be a whole bunch of fac that that don't move. They move a little bit. Uh almost everything will be robotic. What does the world look like?

</details>

**采访者**: 抱歉，让我……我认为对我来说，机器人是能够解锁每个人的经济流动性机会的其中一个环节。现在每个人，就像每个人都有一辆车时，他们就能去做很多不同的工作。当每个人都拥有一个机器人时，他们的机器人可以为他们做很多工作。他们可以建立一个**Etsy**商店，一个**Shopify**商店。他们可以用他们的机器人创造任何他们想要的东西。他们可以做一些他们独立无法做到的事情。我认为机器人最终将成为地球上更多人实现繁荣的最大解锁，这是我们以前从未在任何技术中见过的。

<details>
<summary>Original English</summary>

**采访者**: Sorry, let me I think like this is one of the robotics for me is one of the pieces that I think unlocks uh economic mobility opportunities for every individual. Everyone now like when everyone got a car, they could now go and do a lot of different jobs. When everyone gets a robot, their robot can do a lot of work for them. They can stand up an **Etsy** store, a **Shopify** store. They can create anything they want with their robot. They could do things that they independently cannot do. I think the robot is going to end up being the greatest unlock for prosperity for more people on Earth than we've ever seen with any technology before.

</details>

**黄仁勋**: 是的，毫无疑问。我的意思是，目前简单的数学事实是，我们今天的劳动力短缺数百万。对。是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah, no doubt. I mean, just a simp the simple math at the moment is we're millions of people short in labor today. Right. Yeah.

</details>

**采访者**: 对。我们，我们实际上非常需要机器人，这样所有这些公司才能获得更多的劳动力。我的意思是，我们，我们首先。你提到的一些事情非常有趣。我的意思是，因为有了机器人，我们将拥有虚拟存在。你知道，我将能够进入我家的机器人，并虚拟地操作它。我正在出差。

<details>
<summary>Original English</summary>

**采访者**: Right. We're we're we're actually really desperate in need of robotics and so that all of these companies could grow more if they had more labor. I mean, we're we're number one. Some of the things that you mentioned are super fun. I mean, because of robots, we'll have virtual presence. Uh, you know, I'll be able to go into the robot of my house and virtually operate it. I'm on a business trip,

</details>

**黄仁勋**: 对吗？

<details>
<summary>Original English</summary>

**Jensen**: right?

</details>

**采访者**: 绕着房子走，遛狗。

<details>
<summary>Original English</summary>

**采访者**: Walk around the house and walk the dog.

</details>

**黄仁勋**: 是的，遛狗。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. Walk the dog.

</details>

**采访者**: 扫落叶。

<details>
<summary>Original English</summary>

**采访者**: Break the leaves.

</details>

**黄仁勋**: 是的。没错。吓到狗。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. Exactly. Freak out the dog.

</details>

**采访者**: 可能没那么夸张，但就是，你知道，只是在家里到处走走，看看发生了什么。你知道，和狗聊天，和孩子们聊天。

<details>
<summary>Original English</summary>

**采访者**: Maybe not quite that, but just, you know, just, you know, wander around and just see what's going on in the house. You know, chat with the dog, chat with the kids.

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah.

</details>

**黄仁勋**: 是的。时间旅行也是。我们将能够以光速旅行。所以，你知道，很明显，我们将会把我们的机器人派出去。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. And that's time travel is also we're going to be able to travel at the speed of light, you know, and so, you know, clearly we're going to send our robots ahead of us.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah.

</details>

**黄仁勋**: 我不会亲自去。我会派一个机器人去。你知道。

<details>
<summary>Original English</summary>

**Jensen**: Not going to send myself. I'm going to send a robot, you know.

</details>

**采访者**: 看看吧。

<details>
<summary>Original English</summary>

**采访者**: Check it out.

</details>

**黄仁勋**: 是的。是的。然后我将上传我的AI。是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. Yeah. And then I'm going to upload my AI. Yeah.

</details>

**采访者**: 嗯，这是不可避免的。它解锁了月球和火星作为殖民目标，这为我们提供了无限的资源。从月球返回基本上是零能量成本，因为你可以使用太阳能并加速。所以你可以在月球上建立工厂，生产世界上所需的一切，而机器人将是实现这一目标的解锁。

<details>
<summary>Original English</summary>

**采访者**: Well, it's inevitable. It unlocks the moon and it unlocks Mars as um targets for for colonization, which gives us infinite resources. Getting back from the moon is effectively zero energy cost to move material back because you can use solar and accelerate. So you could have factories that make everything the world needs on the moon and the robots are going to be the unlock for enabling that.

</details>

**黄仁勋**: 没错。距离不再重要。

<details>
<summary>Original English</summary>

**Jensen**: That's right. Distance no longer matters.

</details>

**采访者**: 距离不重要。是的。

<details>
<summary>Original English</summary>

**采访者**: Distance doesn't matter. Yeah.

</details>

**黄仁勋**: 我们从模型和Agent中获得的收入越多，我们就能投入越多的资金来建设基础设施，这反过来又解锁了模型和Agent更多的能力。**Daario**最近在**Dwaresh**的播客上说，到2027-2028年，我们将从模型公司和Agent公司获得数百亿美元的收入。他预测到2030年将达到万亿美元。对吧？这是非基础设施的AI收入。

<details>
<summary>Original English</summary>

**Jensen**: The more the more revenue we get out of models and agents, the more we can invest in building the infrastructure which then unlocks more capabilities on models and agents. **Daario** on **Dwaresh**'s podcast recently said by 2728 we'll have hundreds of billions of dollars of revenue out of the model companies and the agent companies. and he forecasts a trillion dollars by 2030. Right? This is non-infrastructure AI revenue.

</details>

**黄仁勋**: 我认为他太保守了。我相信Daario和Anthropic会做得比那好得多。

<details>
<summary>Original English</summary>

**Jensen**: I think he I think he's he's being very conservative. I believe Dario and Anthropic is going to do way better than that.

</details>

**采访者**: 哇。

<details>
<summary>Original English</summary>

**采访者**: Wow.

</details>

**黄仁勋**: 比那好得多。

<details>
<summary>Original English</summary>

**Jensen**: Way better than that.

</details>

**采访者**: 哇。所以从300亿到1万亿。

<details>
<summary>Original English</summary>

**采访者**: Wow. So from 30 billion to a trillion.

</details>

**黄仁勋**: 是的。原因是他没有考虑到的一个部分是，我相信每一家企业软件公司也将成为Anthropic代码、Anthropic令牌、OpenAI的增值经销商。没错，他们将会，他们那一部分将会得到对数级的扩展。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. and not and and the reason for that is the one part that he hasn't considered is that I believe every single enterprise software company will also be a reseller value added reseller of anthropic code anthropics tokens value added reseller open AAI that's right and they're going to that that that part of their get this logarithmic expansion

</details>

**采访者**: 这种对数级的扩展。

<details>
<summary>Original English</summary>

**采访者**: get this logarithmic expansion

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: yes

</details>

**采访者**: 他们的市场推广将在今年大幅扩展。

<details>
<summary>Original English</summary>

**采访者**: their go to market is going to expand tremendously this year

</details>

### AI时代的护城河与专业化

**采访者**: 在那个世界里，你认为护城河是什么？还剩下什么？我的意思是，你有一些护城河，坦率地说，我认为随着规模的扩大，几乎是不可逾越的。没有人谈论的最好的护城河可能是**CUDA**，它只是一个令人难以置信的战略优势。但未来，如果一个模型可以用来创造一些不可思议的东西，那么下一个模型的迭代可能会被用来颠覆它。在你看来，对于那些正在应用层构建的这些公司，他们的护城河是什么？他们如何实现差异化？

<details>
<summary>Original English</summary>

**采访者**: what do you think in that world is the moat what's left over. I mean you have some modes that are frankly I think as this scales almost insurmountable. The best one that nobody talks about is probably **CUDA** which is just like an incredible strategic advantage. But in the future if a model can be used to create something incredible then the next spin of a model can be used to maybe disrupt it. Sort of in your mind what do you think for these companies that are building at that application layer? What's their moat? like how do they differentiate themselves?

</details>

**黄仁勋**: 深度专业化。深度专业化。我相信这些模型将拥有通用模型，这些通用模型将连接到软件公司的Agentic系统。

<details>
<summary>Original English</summary>

**Jensen**: Deep specialization. Deep specialization. I believe that um these models they're going to have general general models that are connected into the software company's agentic system,

</details>

**采访者**: 对吗？

<details>
<summary>Original English</summary>

**采访者**: right?

</details>

**黄仁勋**: 这些模型中的许多是云模型和专有模型，但其中许多是他们自己训练的专业化子Agent。

<details>
<summary>Original English</summary>

**Jensen**: Many of those models are cloud models and proprietary models, but many of those models are specialized sub aents that they've trained on their own.

</details>

**采访者**: 对。所以你给企业家的号召是：

<details>
<summary>Original English</summary>

**采访者**: Right. So the call to arms for you for entrepreneurs is look

</details>

**黄仁勋**: 了解你的垂直领域。

<details>
<summary>Original English</summary>

**Jensen**: know your vertical.

</details>

**采访者**: 没错。比任何人都更深入、更好地了解它。

<details>
<summary>Original English</summary>

**采访者**: That's right. Know it as deep and as better than everybody else.

</details>

**黄仁勋**: 没错。

<details>
<summary>Original English</summary>

**Jensen**: That's right.

</details>

**采访者**: 然后等待这些工具，因为它们正在追赶你，现在你可以将你的知识融入其中。

<details>
<summary>Original English</summary>

**采访者**: And then wait for these tools because they're catching up to you and now you can imbue it with your knowledge.

</details>

**黄仁勋**: 没错。你越早连接你的Agent。

<details>
<summary>Original English</summary>

**Jensen**: That's right. The sooner you connect your agent,

</details>

**采访者**: 你越早将你的Agent与客户连接。

<details>
<summary>Original English</summary>

**采访者**: the sooner you connect your agent with customers,

</details>

**黄仁勋**: 那个飞轮将使你的Agent获得。

<details>
<summary>Original English</summary>

**Jensen**: that flywheel is going to cause your agent to get

</details>

**采访者**: 这非常像是我们今天所做事情的颠倒，因为今天我们构建一个软件，然后我们说它有什么通用性。

<details>
<summary>Original English</summary>

**采访者**: it very much is an inversion of what we do today because today we build a piece of software and we say what generalizes

</details>

**黄仁勋**: 然后我们试图尽可能广泛地销售它，然后销售围绕它的定制化。

<details>
<summary>Original English</summary>

**Jensen**: and then let's try to sell it as broadly as possible and then sell the customization around it

</details>

**采访者**: 事实上，我们确实如此，没错。我们创造了一个横向平台，但请注意，所有这些集成商（GSI）和顾问都是专家，他们将你的横向平台进行专业化。

<details>
<summary>Original English</summary>

**采访者**: and we in fact in fact exactly right we we create a horizontal but notice there are all these gsis and all of these consultants who are specialists who then take your horizontal platform and specializes it into

</details>

**黄仁勋**: 而且可以说，定制化是一个大五倍或六倍的行业。

<details>
<summary>Original English</summary>

**Jensen**: and that's arguably a five or six time bigger industry is the customization.

</details>

**采访者**: 它绝对是全部。非常重要的是。

<details>
<summary>Original English</summary>

**采访者**: It is absolutely the whole very much is

</details>

**黄仁勋**: 没错。所以我认为这些平台公司有机会成为那个专家，成为那个垂直领域。

<details>
<summary>Original English</summary>

**Jensen**: that's right. So I think that these platform companies have an opportunity to become that specialist to become that vertical.

</details>

**采访者**: 是的。领域专家。

<details>
<summary>Original English</summary>

**采访者**: Yeah. Domain expert.

</details>

### AI对工作的影响与青年建议

**采访者**: 你知道，我只想向你致敬。我认为三年前你说过，你不会因为AI而失去工作，你会因为使用AI的人而失去工作。现在我们在这里。整个对话都围绕着Agent使人变得超人，商业机会扩展，创业精神扩展这个概念。你确实看得很清楚。

<details>
<summary>Original English</summary>

**采访者**: You know, I just want to give you your flowers. I think it was 3 years ago you said you're not going to lose your job to AI. You're going to lose your job to somebody using AI. And here we are. The entire conversation has revolved around this concept of agents making people superhuman and the business opportunity expanding and entrepreneurship expanding. You actually saw it pretty clearly. Yeah.

</details>

**黄仁勋**: 你改变了你的看法。

<details>
<summary>Original English</summary>

**Jensen**: You changed your view.

</details>

**黄仁勋**: 这是悲观主义者。不，我不是悲观主义者。我确实有悲观主义。不，我认为你可以同时支持两种观点。一种是，将会有很多。

<details>
<summary>Original English</summary>

**Jensen**: This is Doom Dmer. No, I'm not Doomer. I do I do have Dmer. No, I you can hold space for I think two ideas. One is there are going to be a lot

</details>

**采访者**: 那是病毒式的杰克。

<details>
<summary>Original English</summary>

**采访者**: that's viral Jake.

</details>

**黄仁勋**: 哦，不。你可以的。

<details>
<summary>Original English</summary>

**Jensen**: Oh, no. There you can.

</details>

**采访者**: 但那只是因为他不够常和我出去玩。

<details>
<summary>Original English</summary>

**采访者**: But that's just because he doesn't hang out with me enough.

</details>

**黄仁勋**: 嗯，我们，我的意思是，我们有一点。我们不谈论它。他会展示桌子。他会跟着你。

<details>
<summary>Original English</summary>

**Jensen**: Well, we I mean we a little bit. We don't talk about it. He will show THE TABLE. HE'LL FOLLOW YOU AROUND.

</details>

**采访者**: 我没要求。我只是。

<details>
<summary>Original English</summary>

**采访者**: I'm not asking for it. I'm just

</details>

**黄仁勋**: 跟着你。我没要求。

<details>
<summary>Original English</summary>

**Jensen**: follow you around. I'm not asking for it.

</details>

**采访者**: 你可以和我以及塔克一起。我们每年一月都会在日本滑雪。喜欢。然后塔克去公路旅行。将会出现工作岗位流失，然后问题就变成了，那些人是否有毅力、有决心去拥抱这些技术。我们将看到100%的人类驾驶被取代。这只是，这是一种美好的事情，挽救了生命，但我们必须认识到，这在美国有1500万人，1000万到1500万人从事这种工作。所以这将会发生。

<details>
<summary>Original English</summary>

**采访者**: You can come with me and Tucker. We ski in Japan every January. Love it. and Tucker go road trip. There is going to be job displacement and then the question becomes, you know, do those people have the fortitude, the resolve to then go embrace these, you know, technologies. We're we're going to see 100% of driving go away by humans. That's just it's that's a beautiful thing and the lives saved, but we have to recognize that's 15 million people in the United States, 10 to 15 million who are employed in that way. And and so that is going to happen.

</details>

**黄仁勋**: 是的，我认为工作会改变。例如，今天有很多司机驾驶汽车。我相信，尽管许多司机实际上会坐在汽车里，坐在方向盘后面，而汽车正在自动驾驶。原因在于，最终请记住司机是做什么的。这些司机，他们正在帮助你，他们是你的助手。他们正在帮助你搬运行李。他们正在帮助你。我的意思是，他们正在帮助你处理很多事情，所以我不会感到惊讶，如果未来的司机成为你的出行助手，他们正在帮助你处理很多其他事情。

<details>
<summary>Original English</summary>

**Jensen**: Yes, I I think I think that jobs will change. For example, um there are many chauffeers today uh who drives the car. I believe that though many of those chauffeers will actually be in the car sitting behind the drive the steering wheel while the car is driving by itself. And the reason for that is because remember what a chauffeur does in the end. These chauffeers, they're helping you they're your assistants. They're helping you with your luggage. They're helping you. I mean, they're helping you with a lot of things and and so I wouldn't be surprised actually if the chauffeers of the future becomes your mobility assistant and they are helping you do on a whole bunch of other stuff

</details>

**采访者**: 到酒店。

<details>
<summary>Original English</summary>

**采访者**: to the hotel.

</details>

**黄仁勋**: 是的。汽车正在自动驾驶。

<details>
<summary>Original English</summary>

**Jensen**: Yeah. And the car is driving by itself.

</details>

**采访者**: 飞机上的自动驾驶仪创造了更多的飞行员，并没有把任何飞行员从驾驶舱里赶出去，尽管自动驾驶仪90%的时间都在驾驶飞机。顺便说一句，当那辆汽车自动驾驶时，那个司机将会在手机上做很多其他工作，他将会。

<details>
<summary>Original English</summary>

**采访者**: The autopilot in planes created a lot more pilots and didn't take any of the pilots out of the cockpit even though the autopilot is flying the plane 90% of the time. By the way, while that car is driving itself, that chauffeur is going to be doing a bunch of other work on his phone and he's going to be

</details>

**黄仁勋**: 例如，安排、协调很多事情，获得，你知道，这块蛋糕以某种方式不断增长。

<details>
<summary>Original English</summary>

**Jensen**: arranging, for example, coordinating a bunch of things for you, getting, you know, it's all the pie just grows in a way that

</details>

**采访者**: 其中一件事是，是的，每份工作都将发生转变。嗯，有些工作会被淘汰。然而，我们也知道很多很多工作将会被重新创造。我想对那些刚毕业的年轻人说，那些担心AI、焦虑AI的年轻人，要成为使用AI的专家。

<details>
<summary>Original English</summary>

**采访者**: one of the things that that that yes, every job will be will be transformed. Um, some jobs will be eliminated. However, we also know that many many jobs will be recre will be created. The one thing that I will say to young people who are coming out of school who are concerned who are anxious about AI be the expert of using AI

</details>

**黄仁勋**: 看看，我们都希望我们的员工能够熟练使用AI，这并不容易。

<details>
<summary>Original English</summary>

**Jensen**: how much look we all want our employees to be expert at using AI and it's not not

</details>

**采访者**: 不容易，不容易。所以知道如何指定，而不是过度规定，为AI留下足够的创新和创造空间，同时我们引导它达到我们想要的结果。所有这些都需要艺术性。

<details>
<summary>Original English</summary>

**采访者**: not trivial not trivial and so knowing how to specify not to overprescribe leaving enough room for the AI to innovate and create while we guide it to the outcome we want. it. All of that requires artistry.

</details>

**采访者**: 你在斯坦福大学的时候曾给过一个很棒的建议，我想是：“我祝你痛苦和磨难。”你还记得吗？

<details>
<summary>Original English</summary>

**采访者**: You had you had this great advice to when you were at Stanford, I think it was, which is I wish to you pain and suffering. Do you remember that?

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah.

</details>

**采访者**: 太棒了。

<details>
<summary>Original English</summary>

**采访者**: Fantastic.

</details>

**采访者**: 你对那些即将离校的年轻人有什么建议？他们应该学习什么？因为现在这些孩子正处于这个非常原生、还没有决定上大学、学什么专业、甚至是否上大学的阶段。你如何引导这些孩子？你会告诉他们什么？我仍然相信深入的科学、深入的数学、语言技能。你知道，语言是AI的编程语言。

<details>
<summary>Original English</summary>

**采访者**: What's your advice to young people around what they should be studying? So, if they're sort of about to leave high school because now those are the kids that are at this like really native, they haven't made a decision about college, what to study, if at all go to college. How do you guide those kids? What would you tell them? I I still believe that deep science, deep math, um language skills, you know, as you know, language is the programming language of AI,

</details>

**黄仁勋**: 终极编程语言。

<details>
<summary>Original English</summary>

**Jensen**: the ultimate programming language.

</details>

**采访者**: 所以，事实证明，英语专业的人可能是最成功的。是的。

<details>
<summary>Original English</summary>

**采访者**: So, as it turns out, it it could be that the English major could be the most successful. Yeah.

</details>

**黄仁勋**: 所以，所以我认为，嗯，我只是建议，无论你接受什么教育，都要确保你非常非常精通使用AI。我想说的一件事，关于工作，我想让每个人都听到的是，事实上，在**深度学习革命**的初期，一位世界上最杰出的计算机科学家，我对他深感尊敬，他曾预测计算机视觉将完全取代放射科医生，而他建议大家不要进入的唯一领域就是放射科。十年后，他的预测百分之百准确。计算机视觉已经百分之百地整合到世界上所有的放射技术和放射平台中。令人惊讶的结果是，放射科医生的数量实际上增加了，对放射科医生的需求飙升。原因在于，每个人的工作都有其目的和任务。你所做的任务是研究扫描，

<details>
<summary>Original English</summary>

**Jensen**: And and so so I think I think um I I would just advise whatever whatever education you get, just make sure that you're deeply deeply expert in using AIS. One of the things that I wanted to say with respect to jobs and I want everybody to hear it that in fact at the beginning of the deep learning revolution, one of the the finest computer scientists in the world deeply deeply I deeply uh deeply uh um respect uh predicted that computer vision will completely eliminate radiologists and and that the one the one field he advises everybody to not go into is radiology. 10 years later, his prediction was at 100% right. Computer vision has been integrated into all of the radiology technologies and radiology platforms in the world 100%. The surprising outcome is the number of radiologists actually went up and the demand for radiologists is skyrocketed. The reason for that is because everybody's job has a purpose and its task. The task that you do is studying the scans,

</details>

**采访者**: 但你的目的是帮助医生，帮助患者诊断疾病。

<details>
<summary>Original English</summary>

**采访者**: but your purpose is to diag helping the doctors, helping the patient diagnose disease.

</details>

**黄仁勋**: 所以令人惊讶的是，因为现在扫描做得如此之快。

<details>
<summary>Original English</summary>

**Jensen**: And so what's surprising is because the scans are now being done so quickly,

</details>

**采访者**: 他们可以做更多的扫描，改善医疗保健。

<details>
<summary>Original English</summary>

**采访者**: they could do more scans, improving healthcare.

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yes.

</details>

**采访者**: 但是做得更快，可以更快地接诊患者，更快地治疗。结果呢，因为医院也喜欢赚钱。

<details>
<summary>Original English</summary>

**采访者**: But doing more scans more quickly allows patients to be onboarded a lot more quick, treated a lot more quickly. And as it turns out, because hospitals enjoy making money, too.

</details>

**黄仁勋**: 是的。

<details>
<summary>Original English</summary>

**Jensen**: Yeah.

</details>

**采访者**: 对。

<details>
<summary>Original English</summary>

**采访者**: Right.

</details>

**黄仁勋**: 他们做了更多的扫描。

<details>
<summary>Original English</summary>

**Jensen**: They're doing more scans,

</details>

**采访者**: 他们治疗了更多的客户和患者，收入增加了。猜猜看？

<details>
<summary>Original English</summary>

**采访者**: they're treating more customers and patients, the revenues go up. Guess what?

</details>

**黄仁勋**: 一个增长更快的国家，生产力会提高。一个更富裕的国家可以把更多的老师放到教室里，而不是更少的老师。没错。你只需要为教室里的每个学生提供个性化的课程，让他们都变得更强，从而带来更多。每个学生都将得到AI的帮助，但每个学生都将需要优秀的老师。

<details>
<summary>Original English</summary>

**Jensen**: And and a country that grows faster, productivity increases. A wealthier country can put more teachers in the classroom, not less teachers in the classroom. That's right. You just give every one of those teachers a personalized curriculum for every student in the room. It makes them all bionic and leads to a lot more. Every single student will be assisted by AI, but every single student will need great teachers.

</details>

**采访者**: 是的。太棒了。黄仁勋，祝贺你。我知道你的成功，这确实是一次极其积极、令人振奋的讨论。我们非常感谢你抽出时间与我们交流。他是我们需要的掌舵人。

<details>
<summary>Original English</summary>

**采访者**: Yeah. Amazing. Uh Jensen, congratulations. I know your success and really this is an incredibly positive, uplifting discussion. We really appreciate you taking the time for us. He is the steward we need.

</details>

**黄仁勋**: 你是，你是一个更健谈的人。我非常积极地谈论它积极的一面。我认为悲观主义太多了。

<details>
<summary>Original English</summary>

**Jensen**: You are you are the more vocal. I'm being very vocal about the positive side of it. I think there's too much dumerism is

</details>

**采访者**: 但我也认为，要取得如此大的成功并保持谦逊，需要谦逊。我们只是在开发软件。是的。

<details>
<summary>Original English</summary>

**采访者**: but I also think it takes the humility to have this level of success and be humble about we're making software guys. Yeah.

</details>

**黄仁勋**: 我认为这实际上对人们来说非常有益。我们以前也做过这种事。我们以前也发明过类别和行业。

<details>
<summary>Original English</summary>

**Jensen**: And I think that that's actually really healthy for people to hear. We have done this before. We have invented categories and industries before.

</details>

**采访者**: 我们不需要陷入这种。

<details>
<summary>Original English</summary>

**采访者**: We don't need to go to this

</details>

**黄仁勋**: 散布恐慌的地方。那毫无意义。

<details>
<summary>Original English</summary>

**Jensen**: scaremongering place. It does nothing.

</details>

**采访者**: 而且我们可以选择，对吧？我们有自主权和决策权。我们可以选择如何。

<details>
<summary>Original English</summary>

**采访者**: And we get to choose, right? We have autonomy and and agency. We get to pick how to

</details>

**黄仁勋**: 我们当然可以。

<details>
<summary>Original English</summary>

**Jensen**: we sure do

</details>

**采访者**: 使用这个。好的，各位。我们下次在“All-In访谈”再见。好的。

<details>
<summary>Original English</summary>

**采访者**: employ this. Okay, everybody. We'll see you next time on the All-In interview. Okay.

</details>

**黄仁勋**: 做得好，兄弟。

<details>
<summary>Original English</summary>

**Jensen**: Well done, brother.

</details>

**采访者**: 谢谢，伙计。

<details>
<summary>Original English</summary>

**采访者**: Thanks, man.

</details>

**黄仁勋**: 干得好。

<details>
<summary>Original English</summary>

**Jensen**: Good job.

</details>

**采访者**: 谢谢您，先生。那太棒了。

<details>
<summary>Original English</summary>

**采访者**: Thank you, sir. That was awesome.

</details>

**黄仁勋**: 好的，好的。感谢你。

<details>
<summary>Original English</summary>

**Jensen**: Good. Good. Appreciate you.

</details>

**采访者**: 你们太棒了。

<details>
<summary>Original English</summary>

**采访者**: You guys are awesome.

</details>

**黄仁勋**: 看看这个。看看你们身后这群庞大的人群。

<details>
<summary>Original English</summary>

**Jensen**: Look at this. Look at this big crowd behind you guys,

</details>

**采访者**: 老兄。我想他们是为你而来。

<details>
<summary>Original English</summary>

**采访者**: man. I think they're here for you.

</details>

**黄仁勋**: 我将全力以赴。
<details>
<summary>Original English</summary>

**Jensen**: I'm going all in.

</details>