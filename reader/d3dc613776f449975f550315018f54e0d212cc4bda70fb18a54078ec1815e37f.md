---
author: The MAD Podcast with Matt Turck
date: '2026-07-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wEZBlmvxx4o
speaker: The MAD Podcast with Matt Turck
tags:
  - compute-infrastructure
  - custom-silicon
  - liquid-cooling
  - power-grid-nuclear
  - network-protocols
title: 专访 OpenAI 算力负责人 Sachin Katti：智能工厂时代的算力重构、定制芯片与电力挑战
summary: 本期访谈深度对话 OpenAI 工业算力负责人 Sachin Katti（前 Intel CTO 及斯坦福教授）。探讨了全球范围内空前规模的 AI 数据中心建设，涵盖液冷超算、电网与核能转型、OpenAI 联合 Broadcom 开发的定制芯片 Jalapeno、MRC 容错网络协议、算力即服务的商业化未来，以及 AI 自主迭代设计硬件的递归前景。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Sachin Katti
  - Matt Turk
companies_orgs:
  - OpenAI
  - Intel
  - Broadcom
  - Oracle
  - Microsoft
  - SoftBank
  - Google
  - Amazon
  - CoreWeave
  - VMware
products_models:
  - Jalapeno
  - MRC
  - GB200
media_books: []
status: evergreen
---
### 算力基建的空前规模

**麦特·特克**: 算力数据中心领域正在发生的事情，被一些人描述为人类历史上最大规模的基础设施建设，其规模甚至超过了当年的州际高速公路和铁路建设。我想知道，第一，你是否同意这个说法？第二，身处风暴中心的你，在 OpenAI 内部对你们目前正在构建的事情有什么真实的感受？

<details>
<summary>Original English</summary>

**Matt Turk**: To start, some people describe what's currently happening in the world of compute data centers as the largest infrastructure build out in history, bigger than the highway, bigger than the railroads. And I'm curious one, if you agree, and two, what it feels like on from the inside. Like what's How do you view what you're currently building at OpenAI?

</details>

**萨钦·卡蒂**: 是的，这绝对让人感觉是人类有史以来建造的最大规模的工程之一。它确实比我所听说过的许多历史项目都要庞大。虽然我的年纪还没大到能亲自经历当年的高速公路建设大潮，但它给人的感觉确实如传闻中一样，用通俗的话说，我就在“巨兽的腹中”。每天我们都在做出决策。由于这些决策的影响极其深远，如果是在我以前的职位上（例如在 **Intel** 担任 CTO 时），可能需要花上几个月的时间来评估和决定。但是现在的需求是如此饥渴，增长是如此迅猛，以至于我们必须极其迅速地采取行动。所以，这确实是一个非常紧张的时期，但对于工程师来说，这大概是他们所能参与的最令人兴奋的事情了。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yeah, it definitely feels like one of the largest things humanity has ever built, effectively. Definitely bigger than many of the things that I've heard of. I'm not old enough to have experienced the highway buildout. But no, it's feels exactly like what it sounds I'm in the in the belly of the beast, so to speak. Every day is we are making we are making decisions. We are compute that historically from my previous role, for example, at Intel, we'd probably take months to make given the magnitude of the those decisions. But the demand is so insatiable that and it is growing so rapidly that we have to move very quickly. So it's an it's an intense time, but it's probably the most exciting thing an engineer would want to be part of.

</details>

**麦特·特克**: 是的，我曾在某处读到，**OpenAI** 今年计划在算力上投入大约 500 亿美元。这个数字在方向上大致准确吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah, and I read somewhere that OpenAI was planning on spending about 50 billion compute this year. Is that Is that still the rough number directionally?

</details>

**萨钦·卡蒂**: 这个数字听起来确实差不多。是的，而且整个行业的算力支出今年预计将达到 7000 亿美元。所以说，这些都是令人难以置信的、疯狂的数字。

<details>
<summary>Original English</summary>

**Sachin Katti**: It actually that sounds about right. Yeah, and the whole industry itself was going to be 700 billion in compute spend this year as well. So like insane insane numbers. It seems.

</details>

**麦特·特克**: 是的，而且这种增长可能还会在未来几年继续，对吧？大量的建设正在展开。对于像我们这样的人来说，很多建设投入会在一两年内转化为我们所使用的算力。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah, and it's probably continuing to grow, right? And a lot of build happening. So a lot of that is also going to translate to compute usage from people like us in a year or two.

</details>

**萨钦·卡蒂**: 是的，未来的算力供给会更加充足。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yes.

</details>

### 从模型研究到物理基建

**麦特·特克**: 对 OpenAI 来说，这在某种程度上是一个全新的世界，对吧？显然，所有的 AI 研究都在全速前进，但在公司内部构建一个全新的业务则是另一回事。这样理解公平吗？大家是这么看待这件事的吗？因为构建模型是一码事，而构建数据中心完全是另一个不同的世界。

<details>
<summary>Original English</summary>

**Matt Turk**: Is the right way to think about this that for OpenAI it's it's a bit of a new world, right? There's obviously not quite a a because obviously the all AI research is going you know full speed ahead but like building a whole new business within the the the company. Is that Is that fair? Is that how people think about it? Because obviously building models is one thing, building data centers is a whole different world.

</details>

**萨钦·卡蒂**: 是的，我认为 OpenAI 始终秉持一个根本性的信念：**计算是万物的基石**，计算是智能的基石。我们要不断扩大智能的规模，推广和分发智能，其途径就是拥有足够的算力。因此，这一核心信念从未改变。我认为现在变得越来越明确的是，为了构建我们所需要的计算能力，并且达到这样的庞大规模，我们不能仅仅依赖于从合作伙伴那里获取算力。我们必须越来越多地采取更主动的姿态，亲自去构建并获取我们所需的计算资源。所以，这绝对像是我们在公司内部正在锻炼和培养的一块“新肌肉”。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yeah, I mean I think OpenAI has always has had a fundamental belief that computers are the foundation of everything, right? Computers are the foundation for intelligence. And the way we keep continuing to scale intelligence and distribute intelligence is by having compute. And so that has never been different. That has never always been the belief. I think what's becoming clear is to build the kind of compute we need and and at the scale we have to not just rely on getting compute from our partners. We increasingly have to take a much more active role in building and getting that compute that we need. So it does absolutely feel like a new muscle that we're building in the company.

</details>

### 什么是现代 AI 数据中心

**麦特·特克**: 为了让我们的对话建立在清晰的事实基础之上，首先讨论一下现实中数据中心究竟是什么，或许会非常有帮助。我想每个人都知道行业正在建设数据中心，但我不太确定大家是否真正清楚具体在建些什么，毕竟我们在云时代已经建设了几十年的数据中心。那么，我们今天为 AI 建设的数据中心，与以往有什么本质上的不同和创新？

<details>
<summary>Original English</summary>

**Matt Turk**: And maybe to anchor the the conversation from from from the beginning, it would actually be very helpful to talk about what a data center is in reality. So I think like everybody knows that data centers are being built but you know going to one's head like I'm not sure that everybody could say well what is actually being built because we've been building data centers over the industry for cloud for for decades at this point. So what is fundamentally different and new about the data centers that we're building for AI today?

</details>

**萨钦·卡蒂**: 我想最大的不同可能就在于**规模**。当我们思考人工智能时，我们实质上是在构建超大型的超级计算机。随着我们不断构建智能，交付智能，并且模型的能力变得越来越强，我们需要用它们来执行更加复杂的任务。我们实际上需要越来越多、规模越来越大的计算机。

因此，我把现在的数据中心形象地比作**巨型工厂**——它们实际上是将**电子（电力）转化为 Token** 的工厂。这是如今非常流行的一个词。但这其中确实蕴含着非常深刻的真实性。我们如何获取电力？如何将这些电子引导并实际用于驱动芯片，从而高效地交付智能？

我脑海中的物理图像是：这些数据中心像好几个足球场那么大。由于这些芯片运行时发热量极大，它们必须全部采用**液冷技术**。这些芯片的运行温度非常非常高，你无法再用空气来冷却它们，必须用液体。因此，建筑旁整齐地排列着大量由液冷技术支撑的冷水机组和制冷设备。

<details>
<summary>Original English</summary>

**Sachin Katti**: I think the biggest probably is is a scale, right? So we are essentially building large supercomputers as we think about AI. And as we build intelligence and deliver intelligence and models become more capable, we use it for more more and more complex tasks. We need more and more bigger computers effectively. And so I think the way we visualize data centers is giant factories, right? That are turning uh electrons into tokens. Uh that's a popular phrase nowadays. But that it's it actually has a lot of a ring of truth to it. So, how do we take power? How do we take those electrons and actually use it to power chips that effectively are delivering intelligence? Uh but the way I visualize it is large football fields, uh liquid cooled because these chips run really hot. Uh the temperatures on these chips are very very high. And so you have to cool them with liquids. You can't cool them with air. So, a lot of liquid cooled uh basically refrigerators effectively uh that are sitting in the alongside the building.

</details>

**麦特·特克**: 那么关于冷却，这种大面积的冷却是发生在数据中心整体层面，还是发生在芯片层面？或者两者皆有？

<details>
<summary>Original English</summary>

**Matt Turk**: And you know, on that a big wall where it's uh the the the cooling happens at the data center level or does it happen at the chip level? Or both?

</details>

**萨钦·卡蒂**: 两者皆有。你需要对整个数据大厅进行降温，但你也必须对每个芯片进行针对性的单独冷却，因为仅做其中一项是远远不够的。

此外，你还必须冷却连接芯片的那些物理链路和部件。这就是为什么现在的系统几乎无处不需要冷却。甚至连分配电力的变压器和电缆都会变得极热，因此它们也需要被冷却。可以说，任何处理能量的设备都会产生热量。

<details>
<summary>Original English</summary>

**Sachin Katti**: Both. Right. So, you need to cool the data halls, but you also need to need to cool the chips individually because it's not going to be enough to do one or the other. And uh you also have to cool the things that connect chips, right? And so that's why you need cooling pretty much everywhere uh nowadays. Even the cables that are the transformers that distribute the power become too hot. So, they also need to be cooled. So, everything that processes energy produces heat.

</details>

**麦特·特克**: 那么我们目前所使用的冷却技术，是已经非常成熟并直接进行规模化部署的技术，还是说现在在冷却领域正在发生一些根本性的新技术变革？

<details>
<summary>Original English</summary>

**Matt Turk**: And is cooling technology uh that's being used uh something that's uh well understood and is just getting deployed or is there like fundamental new things happening in cooling right now?

</details>

**萨钦·卡蒂**: 液冷技术其实已经存在了一段时间，但它从未像今天这样以如此庞大的规模被部署。因此，目前的创新更多是围绕**如何提高其可靠性、如何降低成本以及如何实现更高的可扩展性**展开的。在这方面有非常多的工程创新。

同时，也有许多针对新型冷却液、新型吸热材料的研发和创新，以实现更好的热传导效率。因为任何能够提高热量传递效率的创新，对数据中心而言都至关重要。

<details>
<summary>Original English</summary>

**Sachin Katti**: I think liquid cooling has been around for some time uh but has never been deployed at this scale. And so, the innovation is more around how to make it reliable, how to make it uh cheaper, uh more scalable, right? So, there's a lot of innovation around that. There's also a lot of new innovation, new kinds of liquids, new kinds of materials that can absorb heat better. Uh because anything that can improve the efficiency of heat transfer uh is very important for data centers.

</details>

**麦特·特克**: 这意味着你们可以让芯片运行在更高的温度下。

<details>
<summary>Original English</summary>

**Matt Turk**: Mhm. So, we can then run the chips hotter. Mhm.

</details>

**萨钦·卡蒂**: 没错。在芯片的运行温度和计算机的算力性能之间存在着直接的正相关关系。芯片运行温度的上限越高，你就能获得越高的内存带宽，以及越高的浮点运算能力（Flops）。因此，这其中存在着非常强大的回报机制：**如果你能做好冷却，就意味着你可以生产出更多的智能**。

<details>
<summary>Original English</summary>

**Sachin Katti**: Right? And there is a direct correlation between running a chip hotter and how powerful the computer is. So, the hotter the chip, the more memory bandwidth you get, the more flops you get. And so, there's more there's a strong payoff. If you can cool well, that also means you can produce more intelligence.

</details>

### 电网制约与核能转型

**麦特·特克**: 明白了，巨大的工厂，密集的冷却系统。另一个对所有讨论都至关重要的部分是电力和能源。那么，这套系统在宏观上是如何运转的？你们是直接连接公共电网，还是拥有自己的发电设施？

<details>
<summary>Original English</summary>

**Matt Turk**: All right. So, gigantic factories, lots of cooling. Um the other part that uh seems to me very critical to any discussion is uh power and energy. Uh so, how do how does that work starting at a a high level? Uh you do you connect to the grid? Do you have your own power generation?

</details>

**萨钦·卡蒂**: 在早期，我们都是直接连接到公共电网。时至今日，我们依然希望能够接入电网。但是在目前这个节点上，我们已经开始在电网的发电基础设施和输电基础设施上进行直接投资。这意味着，无论我们在哪里建造数据中心，我们都会做出硬性承诺：**我们不会从已有的电网中强行分走现有的电力**。事实上，我们是在投资电网以产生新的增量电力，从而专门供数据中心消费。

<details>
<summary>Original English</summary>

**Sachin Katti**: It I think the early days we all connected to the grid. Uh and we still all would want to connect to the grid. Uh at this point we are beginning to hit uh and we are investing in generation infrastructure for the grid, transmission infrastructure for the grid. So, whenever we build a data center anywhere, we make it a hard commitment that we are not taking power away from the grid. In fact, we are investing in the grid to generate new power uh so that we can consume it uh for data centers.

</details>

**麦特·特克**: 在实际操作中这具体意味着什么？

<details>
<summary>Original English</summary>

**Matt Turk**: You know, what does that mean practically?

</details>

**萨钦·卡蒂**: 比如某个地区有电网，它具有特定的发电和配电能力，即特定的兆瓦数（Megawatts）。显然，一旦数据中心建成，如果有闲置的电力容量，数据中心当然可以直接使用。但如果没有闲置容量，我们就必须**为电网投资建设全新的天然气发电、太阳能发电或水力发电等基础设施**。

<details>
<summary>Original English</summary>

**Sachin Katti**: You have a grid somewhere. Uh it produce it has a certain generation and distribution capability, certain number of megawatts. Uh obviously, a data center shows up. If there are spare capacity, then of course the data center can use it. But if there isn't spare capacity, then we have to add new gas or solar or hydro generation infrastructure.

</details>

**麦特·特克**: 也就是说，把这些发电设备并入到电网中。

<details>
<summary>Original English</summary>

**Matt Turk**: To the grid.

</details>

**萨钦·卡蒂**: 没错，我们是在为这些基础设施的扩建提供资金和投资。然后你还必须建设输电线路，投资变压器、变电站以分配和传输这些电力。所以，无论我们在哪里建立数据中心，我们都在资助所有这些配套基础设施的开发。

这也是我们想要强调的一点：**如果没有这些数据中心的建设需求，这些庞大的基础设施资金在其他情况下是根本不会被拨出和落实的**。由于这一轮大规模的数据中心建设，美国乃至全世界的电网基础设施都在得到极其迅速的升级和改造。

这就是关于电力的部分。所以，只要有可能，我们就会这样做。我们从电网中消耗电能，但同时我们也是电网建设的“好公民”，因为我们实际上在为所有人改善和升级电力基础设施，这不仅惠及数据中心，也惠及千家万户。

但在某些地区，我们已经开始触及通过电网扩建和消费电力的极限。因此，大家都在关注“表后发电”（Behind the meter）。我们也在尝试进行一些表后发电的探索，即在数据中心现场拥有独立的发电和配电能力。这些电力不来自公共电网，从而让数据中心在能源层面上实现事实上的**自给自足**。

<details>
<summary>Original English</summary>

**Sachin Katti**: So, we are investing and funding that build-out. And then you have to build transmission lines, invest in transformers, substations to distribute that power. So, wherever we're are data centers, we are funding uh the development of all of that infrastructure. And so, that's one of the things that uh that we do want to emphasize, which is this is infrastructure that would otherwise not have been funded if not for these data centers. And one of the side benefits of this big data center build-out is the grid infrastructure of America and the whole world, for that matter, is getting upgraded very quickly. And so, that's the power piece. So, whenever we can do that, we do that, and we consume power from the grid, but it's also being good citizens of the grid because we are improving the infrastructure for everyone. Not just for data centers, but also for households. Uh in some places, we are beginning to hit the limits of how much grid power we can build and consume. And so, there everyone's looking at behind the meter. We are also doing some behind the meter generation, where we would have on-site uh power generation and distribution capability that did not come from the grid, but in fact, the data center becomes effectively self-sufficient in terms of power.

</details>

**麦特·特克**: 这是指安装燃气轮机吗？

<details>
<summary>Original English</summary>

**Matt Turk**: It does gas turbines?

</details>

**萨钦·卡蒂**: 在今天，尤其是在美国，最主要的形式确实是**天然气轮机**。因为天然气是目前能量密度最高、最易于运输的能源形式，而且在美国本土的供应非常广泛。

<details>
<summary>Original English</summary>

**Sachin Katti**: Well, what what is it? Today, it's gas turbines, especially in the US. Uh because that's the most dense, transportable form of energy, and also the one uh that is uh quite uh you know, widely available in the US.

</details>

**麦特·特克**: 你认为关于核能的讨论有吸引力吗？我们目前正在法国录制这期节目，法国拥有非常丰厚的核能发电底蕴。核能系统似乎也重新回到了美国政策与产业讨论的中心。这是你们在思考的事情吗？你觉得它有前景吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Do you think that the nuclear conversation is uh interesting? Maybe we're recording this in France, which has a bunch of uh you know, nuclear nuclear uh power generation. Nuclear systems have come back to the discussion in the US, as well. Is that something that you think about? Do you think it's interesting?

</details>

**萨钦·卡蒂**: 毫无疑问。**核能来得越快越好**。我认为核能是我们所能生产和消费的能量密度最高的能源形式，而且它非常清洁。因此，对于数据中心而言，核能绝对会成为大规模、高可扩展性清洁能源的一个非常重要的来源。显然，除了法国之外，世界上其他国家在建设这种基础设施方面还有很多追赶工作要做，但我认为它将在未来的数据中心世界里扮演极其关键的角色。

<details>
<summary>Original English</summary>

**Sachin Katti**: Absolutely. It can't come soon enough. Uh I think it is the densest form of energy we can all produce and consume. Uh and it's also clean. So, I think definitely uh would be a good source of massive scalable energy for data centers. Obviously, outside of France uh the rest of the world has a lot of catching up to do and building this infrastructure, but I think it's going to be a very important role in the data center world.

</details>

### 自研芯片 Jalapeno 的战略意图

**麦特·特克**: 这是一个非常好的关于数据中心的介绍。另一个非常引人注目的新闻是你们最近公布的自研芯片项目 **Jalapeno**。现在的 OpenAI 似乎不仅拥有面向消费者和企业的应用业务、前沿的 AI 模型研究业务、算力与数据中心业务，而且还正式涉足了芯片业务。可以说是完全实现了全栈化。我很想知道，从整体战略的角度来看，自研芯片在你们的蓝图里处于什么位置？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay, so that's a great introduction on on on data centers. The other The other interesting bits of news that you guys recently had is jalapeno. Um so now in for OpenAI in addition to being the application business, consumer and enterprise, and then being in the model AI research business, and then the computing data center business, it seems that OpenAI is in the uh chip business, if that's fair. So like completely full stack, but I'm I'm I'm curious and we'll we'll go into some details about jalapeno later later, but I just want to like overall strategy, where where does that fit?

</details>

**萨钦·卡蒂**: 随着全球人口中 AI 的使用率呈爆炸式增长，推理（Inference）显然在我们的整体工作负载中占据了极大的比例，并消耗了大量的计算资源。我们意识到的另一个关键点是：因为我们非常精准地知道终局的工作负载是什么，知道我们想要运行的究竟是什么模型，所以我们能够共同设计（Co-design）硬件，使其在运行这些特定模型时表现出超高的效率。

因此，**Jalapeno 背后的战略核心就是：我们如何利用对终局工作负载和模型架构的精确知晓，去设计出在服务这些模型时具有极高效率的定制芯片**。

这让我们可以极大地提升效率优势，驱动**每瓦特电力产生更多的 Token**。Jalapeno 正在优化的最关键指标，就是最大化每瓦特功率能够产生的 Token 数量。在当今世界电力受到严重制约的背景下，如果你能在消耗同等电力的情况下产生更多的 Token，这对所有人都是一件大好事。因此，我们将其视为我们向世界交付并规模化智能的一个非常关键的战略拼图。

<details>
<summary>Original English</summary>

**Sachin Katti**: As we begin to as so uh pretty big fraction of the world's population, AI usage is exploding. Uh inference is obviously becoming a big fraction of our workload, and it's consuming a lot of compute. And one of the other realizations is because we know what is the workload exactly, what is the model we want to run. Uh we can co-design the hardware to be super efficient and that are in those models, right? And so the the strategic thesis behind jalapeno is how do we take advantage of knowing what the end workload is, what the model itself is, and design chips uh that are very efficient in serving those models. So it really allows us to drive the efficiency advantage, drive more tokens per watt. So the key metric that jalapeno is optimizing is maximizing the number of tokens you can produce per watt. And because the world is constrained by power today, so the more tokens you can produce for the same number of amount of power, it's better for everyone. So we look at it as a very critical ingredient in scaling how we deliver intelligence to the world.

</details>

### 推理与训练的界限模糊

**麦特·特克**: 我们稍后会继续聊 OpenAI。你刚才提到了推理。在现在的计算机资源分配和使用上，推理的总体消耗是不是已经远远超过了模型训练？我们是否已经从重度的预训练（Pre-training）占主导的阶段，转型到了推理占大头的阶段？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. So we'll come back to OpenAI in in in a second, but you mentioned you just mentioned inference and uh you know, there's such an interesting evolution as well. Without commenting on necessarily what's going on at OpenAI specifically, is inference equally being much bigger than training these days in terms of like usage of computers as as as are we shifted from you know, being those very heavy pre-training runs as the major use case for compute to now just inference being the majority?

</details>

**萨钦·卡蒂**: 不，虽然推理的规模非常庞大，甚至可能是算力消耗的多数派。但在我们内部，**我们现在其实并不太倾向于把训练和推理做非常割裂的区分，因为现在的训练过程中包含了大量的推理**。

例如，当我们训练一个新模型时，我们需要生成大量的合成数据（Synthetic data），这本质上是推理。我们在做训练后的对齐和强化学习（Post-training）时，这也包含大量的推理。当你在模型运行期间进行测试时计算（Test-time compute），这全部都是推理。

因此，当我们提到“训练”时，这个阶段中所消耗的很大一部分计算资源实际上都是由推理构成的。所以，推理是一个贯穿始终的、最根本的构建块。

<details>
<summary>Original English</summary>

**Sachin Katti**: No, inference is big, perhaps even the majority on compute. And and I think one of the I we don't like to make a distinction between training and inference because a lot of training is now inference. So when we train a new model, we are generating synthetic data for example. That's inference. When we train a new model, we are doing post-training and that's inference. When you train a model, you're doing test time compute. That's all inference. So when we say training, a lot of the compute actually is inference even in that phase of the the work. So inference is a fundamental building block.

</details>

### 数据中心会“过载扩建”吗？

**麦特·特克**: 面对如此庞大的投资，我不得不问一个无法回避的问题，那就是是否存在“过度建设”（Overbuilding）的潜在风险？毕竟从规划到建成一个数据中心需要极其漫长的周期，而在需求与实际算力上线之间存在着明显的时间滞后。我记得你曾在某个地方提到过，你对未来三年可能遇到的问题和意外保持着一种“清醒的偏执”（Paranoid），这似乎是一种非常健康的工程态度。你是怎么看待这一点的？有没有什么方法可以缓解这种风险，还是说大家都深信这条路代表着未来的方向，因此只能“踩死油门”一路向前？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. Obviously I cannot resist asking the inevitable question around the potential risk of overbuilding given the lag between demand and usage and how long it takes to build a data center. And you mentioned somewhere that you were deliberately very paranoid about the problems ahead in the next three years. We're planning on that the surprises ahead, which seems like a very healthy approach. So, how do you how do you think about that? Is there any way to mitigate that or is just like I'm going to be playing do you have any belief that this is the future and you know, we're just all just going to go go go?

</details>

**萨钦·卡蒂**: **我们对扩展定律（Scaling Laws）抱有极其坚定的信仰**。历史也一再证明了我们的信念。

从业务层面上看，我们算力规模的增长与我们的营收轨迹有着高度的契合。当我们把计算资源翻三倍时，我们的收入也会相应地翻三倍。我们相信这一规律在未来依然成立。目前，市场对算力的需求远远超出了算力的实际供给。可以说，任何我们能够上线的算力资源，都会被瞬间消耗殆尽。因此，至少对我们而言，没有任何一点算力是被浪费掉的。

这种坚定的信心没有任何动摇。如果说有什么改变的话，那就是我们看到前沿研究和训练中的扩展定律依然非常有效，并且因为 AI 技术的辅助，我们进行科学研究的步伐正在进一步加快。**现在，AI 正在协助进行大量的 AI 研究本身**。

这背后其实隐藏着一个微妙的行业影响：在过去，我们的研究人员为了运行实验需要消耗大量的算力。但他们能够运行的实验数量，最终受限于人类研究员的数量——而在世界上，顶尖的 AI 研究员是非常稀缺的资源。并没有多少人真正懂得如何做前沿的 AI 研究。

然而现在，当 AI 自身能够开始做 AI 研究时，我们所能开展的实验数量就会呈指数级增加。随之而来的是，我们研究所需要的算力需求也会呈现爆炸式增长。

所以，在可预见的未来里，我们并不认为会面临算力过剩的问题。当我之前提到“清醒的偏执和意外”时，**我的担忧恰恰相反——我担心的是我们可能根本无法及时建造出我们所需要的全部算力**。

这对我们来说是一个真正的制约因素。因为在很多次决策中，每当我们因为觉得算力差不多够了而产生哪怕一丝想要放慢脚步的想法时，现实总会无情地给我们一个耳光：不，我们绝对不应该慢下来。

所以，我们最大的担忧依然是算力供不应求。在我们计划获取和构建算力的这个庞大规模上，**物理世界运行的速度实在是太慢了**。物理世界的供应链、工厂的建设，它们根本无法以我们需要的那种速度去运转或扩充产能。所以对我们而言，意外和挑战主要集中在这个方向，而不是相反的方向。

<details>
<summary>Original English</summary>

**Sachin Katti**: We have deep conviction in scaling, right? And history has borne us out. So, effectively our revenue, for example, has tracked it. We triple compute and we triple revenue. And we believe that I mean, that continues to be true. Demand far outstrips compute supply today. So, anything we can bring online we consume immediately. So, there's no compute that is going waste as for us at least. So, I think that conviction has not changed whatsoever. And if anything, we are seeing that scaling laws on research and training continue to hold and potentially the pace at which we are doing research is accelerating, right? Because of AI itself. So, AI is doing a lot of AI research now. And so, one of the subtle implications of that is is previously our researchers used to run experiments and they needed compute to run experiments. But the number of experiments they could run was limited by the number of human researchers they have, which is a scarce resource in the world. Right? There's not a lot of people who can do AI research. Now is AI itself can do AI research, the number of experiments we can draw next tools. And therefore, the amount of compute you need for research also explodes. So, we don't see a world where we will have unlimited compute for the foreseeable future, right? When I was referring to surprises, my worry is more on the downside of we are not able to actually build all the compute that you want. And and this is where is the other if the other way for us. Right? And because that is consistently in the case we anytime we have thought we have having less compute, we can slow down. Always negatively surprises like, oh we should not have slowed down. Right? And and so our biggest worry is that still. And at the scale at which we are planning to get compute and build compute, uh the physical world does not move that fast. Right? Physical supply chains, factories don't move that fast or cannot add capacity that fast. So for us the surprise is more on that direction than the other direction.

</details>

### 数据中心与地方社区的利益共生

**麦特·特克**: 这非常引人深思。你刚才提到了地方社区。显然，这是一个非常关键的辩论焦点。我想听听你的看法。在这个问题的光谱上，一端的人认为 AI 行业和计算机行业正面临着公关（PR）危机，但其实并没有什么实质性问题，只是我们没有向公众解释清楚；而另一端的人则认为，地方社区的担忧是非常合理的。你认为现实情况是怎样的？

<details>
<summary>Original English</summary>

**Matt Turk**: That's fascinating. You alluded to communities a minute ago and obviously that's a that's a key debate. So curious about your perspective on a on a on a spectrum where um you know, on the one hand one extreme you'd say, well, uh the AI industry and computer industry has a PR problem and there's no problem it's just that the the problem is that we cannot explain it well enough to at the other extreme actually those communities have a point. Uh what do you think the reality is?

</details>

**萨钦·卡蒂**: 我认为，每当出现像这项技术一样具有颠覆性、革命性的新技术时，社会中总会发生一些震荡和变革。但纵观历史，我们深知这些变革最终都会为社会带来更好的福祉。因此，我们的职责在于将我们今天所处的位置与未来的美好图景连接起来，向世界解释为什么这是我们所有人都需要共同前行的轨道。

在地方社区的层面，这其中存在着“局部利益”与“全局利益”之间的平衡问题。但即便在今天，我相信数据中心对每一个落户的社区而言都是一种绝对的**净正面效益**。

例如，我们很多数据中心是建在美国非常偏远的农村地区，在那些地方，原本几乎没有任何大型项目的建设。我们落户在德克萨斯的乡村，建立起数据中心，为当地社区带去大量新的房产税收入。这些税收直接资助了当地的学校、医院和公共服务。同时，我们投资了全新的电网基础设施，如果不是因为数据中心的建设需求，由于当地缺乏电力需求，这些升级在以往是根本不可能发生的。这意味着当地居民也能享受到现代化升级后的电网。此外，我们还创造了大量的就业岗位。

因此，我们目前在做的一件非常核心的投入，就是向大家阐明每一次我们落户某地时，能为当地带来的切实利益。我们需要确保大家理解其中的巨大红利。而且，数据中心一旦建成并开始运行，本质上是非常干净的社区成员。它们不排放任何废气，不产生有害的化学物质，一切都是完全物理封闭和自包含的，它们唯一产出的东西就是智能。

<details>
<summary>Original English</summary>

**Sachin Katti**: I think anytime there's new technology which is as ex- as revolutionary as this technology is, uh there is always disruption that's going to happen. Uh but you know, that we have we have learned this over history that uh this always leads to better outcomes for society, right? And so how do we draw a line from where we are today to that outcome, right? And uh explain to the world why this is the trajectory we all need to be on. I mean, it's our responsibility to do that. Uh on the communities front there's a little bit of a local versus global issue, right? Uh the communities, I think data centers are even today a net positive to every community. It is we are building these data centers in rural areas of America for example, right? Where there's nothing else that is being built. I'm just kidding. So we show up in rural Texas. We build a data center that produces new property taxes into the community. That funds schools, that funds hospitals. We show up and we invest in new grid infrastructure. Which otherwise would never have happened. Because there's no demand. So there's a modernized grid that that area can enjoy. Basically we produce jobs. Nice. And and and so I think one of the things we are investing a lot in is explaining the local benefits every time we build a data center somewhere. And making sure that it is well understood the kind of upside that this has. And data centers, once they are built, are essentially very clean citizens. Right? They don't produce any gases or toxic chemicals or anything. Right? They're self-contained. They just produce intelligence.

</details>

### 关于水资源的误解

**麦特·特克**: 另一个经常被提及的典型问题是水资源消耗。虽然很多研究已经澄清和反驳了这一说法，但也许你可以从你的角度为我们补充一些关于水资源问题的细节。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. Typical question that comes up is water. Um and I think that's been debunked quite a bit by by research, but well it's maybe give us just color on um my outlook on the the water question.

</details>

**萨钦·卡蒂**: 我们使用的是闭式液冷系统，这意味着冷却液是在系统内部进行**完全循环使用**的。所以，一个数据中心的实际净水资源消耗量小得令人吃惊，甚至比许多普通家庭的日常用水量还要少。

正如你所说，这在科学界已经被澄清了。外界认为数据中心会消耗巨量水的说法其实是一个很大的误解。事实上，相较于它们所承载的庞大计算任务，它们的耗水量微乎其微。并且所有使用的水在进入特定节点后，都是以封闭回路的形式在液冷系统中循环往复地利用。

<details>
<summary>Original English</summary>

**Sachin Katti**: We use liquid cooled and the liquid is recycled. So we do actually the water consumption of a data center is shockingly small relative to household water consumption. Uh so I think as you put it, it's been debunked. It's uh it's a misperception that data centers consume a lot of water. Uh if anything, they consume so little water for what they do. Uh and all of that water is recycled. So we don't net consume new water once we get to a particular point. The water just gets recycled as it is liquid cooled.

</details>

**麦特·特克**: 明白。所以那些关于数据中心排放污水或消耗当地地下水的传闻在逻辑上是站不住脚的，因为数据中心的整个水循环是一个完全密闭的环路。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. So all those stories about like brown water is that just don't make sense because the water um at the data center up it's in like a contained circuit.

</details>

**萨钦·卡蒂**: 没错，它是一个闭环系统（Closed loop），完全封闭。

<details>
<summary>Original English</summary>

**Sachin Katti**: It's a closed loop. Yes, it's a closed loop. It's a closed loop.

</details>

**麦特·特克**: 你刚才提到了德克萨斯州和偏远农村地区。既然我们在对话开始时就讨论了数据中心，那为什么 OpenAI 和其他科技巨头会如此偏爱农村地区？你们是如何为一个新的数据中心选址的？

<details>
<summary>Original English</summary>

**Matt Turk**: And by the way, you mentioned Texas in rural areas. Since we talked about data centers at the beginning of this conversation, why do OpenAI and other companies pick rural areas? Like how do you select a site for a data center?

</details>

**萨钦·卡蒂**: 选址考量涉及非常多的因素。

首先当然是土地，我们需要极其充裕且开阔的土地。

第二是许可和规划审批（Permitting），即我们能否在当地顺利开展建设。同时，我们希望这些设施的建设不会对任何现有的居民社区和邻里生活产生干扰，因此与居民区保持一定物理距离的开阔土地是最理想的选择。

第三是电力的可获取性（Access to power）。这需要当地具备强大的电网接入能力或丰富的天然气供应。

第四则是劳动力（Labor）。这关系到我们能以多快的速度将数据中心建造起来。建设大军的保障、合格的电工、管工等专业技工的充足供应至关重要。

因此，所有这些复杂的物理和政策因素共同决定了每一次的选址决策。德克萨斯州之所以成为热门选择，正是因为它在很多指标上都非常完美地契合了这些条件，但它绝不是唯一的选择。我们在全美许多其他州，包括洛杉矶以及更多地区都部署有数据中心。

<details>
<summary>Original English</summary>

**Sachin Katti**: Uh so many factors. So one is of course land, like plentiful land. Uh number two would be uh permitting, like can we build these things? And we want to build these things such that they are uh not affecting any neighborhoods, right? So land that is somewhat removed is the ideal candidate. Of course, access to power, right? So a strong grid, strong gas availability. All of those are important factors. And then four is labor, right? So how quickly can you build these things? So availability of labor, construction labor, qualified electricians, plumbers, all this stuff comes into play. So all of those factors go into every single site selection decision. Um and I know we obviously Texas is a popular because it fits a lot of these criteria, but it's not the only state. I mean, we have data centers all around the country in LA plus.

</details>

### 从学术界到 OpenAI：Sachin 的个人轨迹

**麦特·特克**: 接下来聊聊你个人的经历和职业生涯。你是 OpenAI 的工业算力负责人。如我们刚才所说，在当下这个极具历史意义的关头，“工业算力”真是一个再贴切不过的职位名称了。这个职位的具体工作内涵是什么？在 OpenAI 内部，这项工作是如何组织和开展的？

<details>
<summary>Original English</summary>

**Matt Turk**: Mhm. Okay, great. We're going to go into all of this in in in more detail, but um let's talk about you a little bit and and and your journey. So you're the the the head of industrial compute at OpenAI, uh which by the way to the beginning of this conversation to the title industrial compute is is so, I mean, such a perfect title, right? For the moment we're in. Um but uh what what does that mean? What what what is the role um and how is this all effort organized within OpenAI to the extent you can talk about it?

</details>

**萨钦·卡蒂**: 可以把我的角色以及我们团队的角色理解为：**如何以工业级的规模将算力带到线上**。这就是我们实质上在做的事情，它涵盖了整个生命周期。

比如，我们如何寻找构成算力的所有基础要素？这包括土地、电力、机架、芯片和散热系统。我们如何为它们筹措资金？因为这涉及极其庞大的资金体量。我们如何确保为电网基础设施提供资金？如何资助物理基建的建设？如何为采购芯片提供资金保障？

其次是关于运营和执行。我们如何确保所有这些极为复杂的物理基础设施能够按时完工并顺利上线？如何确保它们上线后保持极高的可用性而不宕机？

然后，是关于我们如何分配和使用这些算力。我工作中非常核心的一部分是**在 OpenAI 内部进行算力的容量分配（Capacity allocation）**。因为计算资源在任何时候都是极其稀缺的。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yeah, I think think of it as uh my role and our team's role rather Uh how do we bring compute online at industrial scale. Right? That's effectively what we're doing. Uh that's the entire life cycle. So, how do we find the ingredients that are going to compute, land, power, shelves, chips, heat. How do we finance them? Right? So, because these are massive dollars. And so, how do we make sure that we finance the uh grid infrastructure? How do you finance the construction of the infrastructure? How do you finance the chips? Uh then it's about how do you operationalize all of this? So, how do you actually make sure these things happen on time? They stay up. How do you operationalize all of this infrastructure? So, it's that entire life cycle. And then, of course, uh how do you actually use the compute? So, big part of my role is uh capacity allocation inside of an ear.

</details>

**麦特·特克**: 听起来你绝对是公司里最受欢迎的人之一。

<details>
<summary>Original English</summary>

**Matt Turk**: Mhm. So, it is always a scarce resource. You sound very You're a very popular guy.

</details>

**萨钦·卡蒂**: 事实上，我可能是最不受欢迎的人。因为无论你做出什么样的分配决定，总会有人感到不满意。

不过，我们团队确实负责提供做出算力分配决策所需的核心数据和决策依据。我们理清并呈现不同的抉择方案，以及不同分配选择背后的“如果……会怎样”的量化分析。这包括容量规划以及利用这些数据去预测我们在何时、何地需要多少容量。因为这不仅仅是获取更多算力的问题，还关乎算力应该部署在什么地方、采用什么配置、使用什么芯片，以及你究竟想在上面运行什么类型的工作负载。我们团队理清了所有的预测和规划，形成闭环，并以此来指导我们下一步应该去哪里获取新的土地、电力和芯片来填充这些容量。

<details>
<summary>Original English</summary>

**Sachin Katti**: not very popular. Uh there is always someone who is unhappy with whatever decisions you make. Uh but, yeah, we actually our team provides the input to make the capacity allocation decisions. Mhm. So, we surface what are the different choice points and what are the what if questions on different allocation choices that we have. So, capacity planning and then, of course, using that to forecast how much capacity we need where. Because it's not just more compute, it's also where, what kind, what shape, what chip, uh what workload you want to run there. So, all of those are this team figures out kind of what should be the forecasting and planning. And that informs that closes the loop. And so, that informs of where do I go find the next chunk of land and power and chips to put in there.

</details>

**麦特·特克**: 了解。在规模上，你们的团队现在是已经达到数千人的规模了吗？还是说它由许多不同的子团队构成？或者你们是主要依赖外部承包商来开展很多物理建设？

<details>
<summary>Original English</summary>

**Matt Turk**: And uh again, without going into it, I think uh confidential although I guess when you guys go public, all of this will you soon will all of this will be public, but like is that thousands of people at this stage? And like is that a is is that a like multiple different teams? Or do you guys got to like ask yours, a bunch of things in works, or is a bunch of contractors?

</details>

**萨钦·卡蒂**: 我们采用的是**组合拳的策略**（Portfolio approach）。我们绝不会陷入一个把所有事情都外包出去的境地，也不会尝试把所有事情都揽在自己身上。因为在这样的规模下，最合理的做法就是采用混合模式。你绝对不能把所有鸡蛋都放在同一个篮子里。

因此，**超大型云服务商（Hyperscalers）**会继续为我们提供非常大的一部分、甚至是大部分的算力支持。

同时，一些**新兴的云服务商（New clouds）**也会成为我们算力组合中的重要组成部分。此外，我们与专业的**设计-建造厂商（Design-build firms）**建立紧密的合作关系，由他们按照我们的需求去具体承建算力系统。最后，我们自己也会亲自动手构建一部分数据中心。

在我们需要获取的庞大算力规模下，我们必须打通所有可能的算力获取通道，而不能仅仅依赖于某一种特定的物理或商业机制。

<details>
<summary>Original English</summary>

**Sachin Katti**: Uh it's a portfolio approach, right? So, we are never going to be in a world where we outsource everything or we let everything outsource, right? It's always going to be a mix because that's the that's the reason that's the reasonable thing to do, right? So, you don't want to put your eggs in all all in one basket. So, we will have hyperscalers providing probably providing a big chunk of a compute, a majority of a compute. Uh we will have new clouds uh parts of our portfolio. Uh we will be partnering with design build firms that can build the compute that we need. And of course, we may build some of it ourselves. And and so, we're always going to have a portfolio approach because at the scale which we need uh we will need to tap into all sources of compute. We can't just rely on one particular mechanism.

</details>

**麦特·特克**: 聊聊你个人的背景。在加入 OpenAI 之前，你既是斯坦福大学的教授，也是多次创业的创始人。请带我们回顾一下你的个人职业轨迹。

<details>
<summary>Original English</summary>

**Matt Turk**: And uh your background before all of this uh so, you're both a uh professor at Stanford and an entrepreneur or founder or mostly an academic like just walk us through your journey.

</details>

**萨钦·卡蒂**: 确实是这几种角色的结合体。但从内心里讲，我首先是一个学术人。自 2010 年起，我就一直在斯坦福大学担任教授。

<details>
<summary>Original English</summary>

**Sachin Katti**: A bit of all of the above. Uh so, but yes, uh I'm at my heart, I'm an academic. So, I've been a I'm professor at Stanford since 2010.

</details>

**麦特·特克**: 你当时在斯坦福的研究方向是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: What do you focus on there?

</details>

**萨钦·卡蒂**: 我是计算机科学系和电子工程系的教员。我的研究领域主要集中在**网络与光纤网络**，涵盖移动无线网络和光通信网络。其实一直以来，我关注的核心都是网络技术。

在大约三四年前，在斯坦福任教期间，我创办了几家初创公司。其中最后一家初创公司被 **VMware** 收购了。正是因为那次收购，我结识了帕特·基辛格（Pat Gelsinger）。当帕特出任 Intel 的 CEO 时，他邀请我加入了 Intel。在来到 OpenAI 之前，我担任的职务是 Intel 的 CTO。

因此，我非常幸运地体验了不同的世界：学术界、初创公司、以及像 Intel 这样的行业巨头。而 OpenAI 恰恰是所有这些世界的交汇点，因为它同时融合了前沿的研究实验室、极速奔跑的初创公司文化以及一个体量巨大且在飞速成长的商业实体。

<details>
<summary>Original English</summary>

**Sachin Katti**: Uh I was a faculty in computer science and electrical engineering. Uh yeah, my area of research was networking and optical fiber networks both mobile wireless networks and the like. So, there's only networks actually. Uh but three, four years ago, I while I was at Stanford, I did a couple of startups. Uh the last startup got acquired by VMware. Uh and that's how got to know Pat. Uh, Pat became Intel's CEO and he That's how I ended up at Intel. Uh, most recently before coming to Open AI, I was Intel's CTO. And uh, and so I've kind of seen all the different things, academia, startups, corporate uh, in Intel. And then of course, a mix of all of the above in Open AI because they have a research lab, uh, startup, and a fast-growing company all mixed into one by Open AI.

</details>

**麦特·特克**: 当时这个工作机会找到你时，让你决定接受它的最核心动力是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: Yes. Is that what you Why you said What did you say yes to the job when the job came uh, come up?

</details>

**萨钦·卡蒂**: 正是我刚才提到的那种独特性。这种独特的组织形态在其他地方是极其罕见的。在很多时候你必须做出非此即彼的妥协，但在这里，你能够在一个世界级的前沿科学研究环境里，去解决物理和工程上最困难的硬核技术问题。

我们在构建世界上规模最大的计算机。在这个过程中有无数全新的工程障碍等待我们去跨越。同时，这也是一个呈指数级增长的商业体。我非常喜欢那些处于**商业、硬核技术与公司战略三者交汇处**的复杂问题。在我们所处的这个独特的历史时刻，这无疑是一个极具吸引力和独特性的岗位。

<details>
<summary>Original English</summary>

**Sachin Katti**: Uh, it's actually what I just said. That makes this so unique. Uh, and it's hard to find anywhere, right? Because you always have to choose, but having a world-class research environment coupled with the hardest technical problems. So, I mean, we're building the largest computer in the world. And so, there are a lot of new problems that we would need to solve. But also a fast-growing business. So, this makes us I I like problems that sit at the intersection of business, technology, and strategies. And so, this is like very unique time in history and a unique role. Uh, so which is very attractive, obviously.

</details>

### OpenAI 的算力版图与 Stargate

**麦特·特克**: 让我们切入更多关于 OpenAI 算力战略的具体细节。首先能为我们梳理一下你们目前所拥有的算力版图吗？例如你们与**微软（Microsoft）**的深度合作，以及之前达成的与 **Cerebras** 的 200 亿美元合作协议，还有外界传闻的 **Stargate** 项目。能否为我们勾勒一下目前的算力来源分布，然后我们再聊聊你们下一步的建设计划？

<details>
<summary>Original English</summary>

**Matt Turk**: Uh, very cool. All right. So, going into a bit more specifics about um, Open AI's compute strategy. Uh, so maybe let's summarize what you guys currently have. So, I think there's some Microsoft uh, you did this this big uh, $20 deal with uh, Cerebras. There's a bunch of things going on. There's Stargate. Maybe just give us the lay of the land of what you currently have and then we'll talk about what you what you're building next.

</details>

**萨钦·卡蒂**: 我们的计算资源实际上来自于非常多元化的渠道。

**微软**显然是我们最重要、最庞大的核心战略合作伙伴。同时，我们也从**亚马逊（AWS）**、**谷歌（Google）**等超大型云服务商处获取并部署了相当规模的计算资源。可以说，我们事实上与所有的主流 hyperscalers 都有着深浅不等的算力合作。

此外，在新型云服务商方面，我们与 **CoreWeave** 展开了深入的算力合作。同时在芯片合作伙伴层面，我们也直接使用像 Cerebras 这样的厂商提供的特定算力产品来满足我们的研究需求。

这就是我们目前整体的算力组合构成。展望未来，我们显然会继续巩固和扩大现有的所有合作伙伴关系，但同时也会积极寻求更多的新选项。例如由我们亲自设计算力系统与数据中心架构，甚至在未来直接投资承建数据中心。所以，这依然是那句老话：我们必须全方位并举。

<details>
<summary>Original English</summary>

**Sachin Katti**: Uh, we have compute from effectively many sources. So, Microsoft obviously is a big partner, important partner. Uh, we also have compute at the amounts from AWS, ION, and Google. So, we have compute from all of the hyperscalers, effectively. Um we also have compute from CoreWeave, for example, so a new cloud. And then, of course, compute uh that chip partners are supplying now, like Cerebras, in the top directly for any 26 compute for us. So, I think that's the mix roughly today. Um oh, as we go forward, uh obviously, we'll be building on all of these relationships. Uh but, also looking at more options where we design the compute, the data center itself ourselves, or potentially even build a data center ourselves. So, all of those uh are ways of scaling the amount of compute that we have. Um so, I think coming back to my earlier answer, it's the answer always will probably be try, but it's all of the above. I'm with you.

</details>

**麦特·特克**: 是的，考虑到目前算力资源的极度稀缺，多元化的配置方案在逻辑上是完全正确的。那么关于 Stargate 项目，它的定义似乎发生了演变。它最初被报道为你们与甲骨文（Oracle）和软银（SoftBank）的一个联合体，而现在它更像是你们整个算力战略的一个“总伞形项目”（Umbrella term）。这样描述准确吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. Yeah. Uh no, no, that that's that's that's helpful. Uh and uh you know, obviously, diversification makes all the sense in the world, given the uh scarcity. Um and then, uh it seems that Stargate has evolved. So, from uh the what was going to be a joint venture with Oracle and uh SoftBank, um to what now seems like it seems like it's more like an umbrella term for the compute strategy these days. Is that Is that a fair way to describe it, or

</details>

**萨钦·卡蒂**: 没错。我们将 **Stargate** 视为我们整体算力战略的代名词。在这把“大伞”之下，包含着我们自己参与设计、参与建设的各种不同深度的算力项目。

例如，我们与 **Oracle** 保持着极度紧密的合作关系。我们会协助他们设计和运行针对 AI 算力的系统架构，因为这对整个行业来说都是一种全新的计算范式。同时，我们与**软银能源（SoftBank Energy）**的合作也是公开的。我们与他们共同设计了数据中心的“暖壳”（Warm shell），由他们负责具体的物理施工，而我们则负责研究未来如何在这些数据中心里运营我们自己的自研芯片。

所以，对我们而言，Stargate 代表着横跨所有这些不同合作模式的整体战略。这是一个不断演进的过程。并不是说我们明天早上醒来，就会突然把所有事情都转成单一的自主建设模式。Stargate 是我们不断学习如何规模化构建和运营算力，并持续叠加新能力的制度性路径。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yeah. Yeah, I think uh we look at Stargate as our compute strategy. And it uh is varying degrees of uh us designing or building the compute ourselves. Uh for example, with uh with Oracle close partnership, uh we help them uh design, we help them uh with how we do operate AI compute, which is effectively new kind of compute uh for us. Uh we work with SoftBank Energy, which is public. Uh we basically have co-designed the warm shell with them and they're executing on that warm shells and we will be kind of figuring out how to operate our chips in these data centers, ourselves, using our new chips. So, Stargate to us is that umbrella strategy for across all of these different things. And think of it as an evolution that we continuously be on because it's never going to be tomorrow we wake up wake up and do only one kind of we are building it. Uh, I've been Stargate to us is a continuous way of learning how to scale compute and we adding on more and more capability.

</details>

### Abilene 与前沿模型的炼成

**麦特·特克**: 作为这个战略的一部分，现在德克萨斯州的阿比林（Abilene）似乎正在兴建一个非常庞大的数据中心。你能为我们梳理一下这方面的情况吗？目前在建的物理实体是什么样的？

<details>
<summary>Original English</summary>

**Matt Turk**: And as part of that there there are data centers being built right now in like Abilene, Texas and so maybe walk us through that. What what is currently being built for for people to have a so situational awareness?

</details>

**萨钦·卡蒂**: 我们与 Oracle 在德州的阿比林有着非常庞大的项目合作。那就是阿比林数据中心。

我们在阿比林部署了非常庞大的 **GB200** 芯片集群来满足我们的算力需求。事实上，我们目前最新一代的前沿模型，正是放在这个集群里进行训练的。我们对此感到非常兴奋。

<details>
<summary>Original English</summary>

**Sachin Katti**: Uh, we obviously have a big partnership with Oracle. That's the Abilene data center. Uh, that's where for example we are training our newest models. So, very excited about that. That's a very big uh, GB black belt cluster for for our needs.

</details>

**麦特·特克**: 也就是说，这个集群目前已经全部上线并开始运转了。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. So, that's that's up and running.

</details>

**萨钦·卡蒂**: 是的，它正在全速运转，承担着我们最近两代前沿模型的核心训练任务。外界能够如此迅速地感受到我们的模型能力在不断变强，其背后的物理功臣正是阿比林这样的算力基建。

<details>
<summary>Original English</summary>

**Sachin Katti**: It's up and running. It's being used for training the last two models more at your Um, so it's super trip. A lot and you're seeing the results. Like you're seeing how quickly the models are becoming more capable. It's because of these kinds of compute.

</details>

**麦特·特克**: 那么在阿比林之外，目前还有其他正在建设中的数据中心吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. Are there data centers that are currently being built that are Yes. That That are the right Yeah.

</details>

**萨钦·卡蒂**: 是的。Oracle 目前正在多地建设一系列新的数据中心，其中很多项目都是公开的，分布在密歇根州、德克萨斯州以及其他地方。这些超大型算力集群将在未来几年陆续完工上线。届时，我们会在阿比林等地的基础上，进一步扩充我们的物理算力版图。这些大体量集群既会被用于前沿模型的训练，也将承载大规模的商业推理工作负载。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yes. So, Oracle is building a number of data centers all of which are public so across Michigan and Texas and other places. So, these are coming online in the next couple of years as they get built and being put whatever chips on that time training rather than but these are really meant to be uh very big clusters uh that Amel is new both uh training, but also product inference kind of compute.

</details>

**麦特·特克**: 在商业合作模式上，是由 Oracle 作为物理建设和云服务的提供主体，而你们则是唯一的承租方（Core Tenant），对吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Right. With the way those deals are structured, the Oracle is the prime building those uh and

</details>

**萨钦·卡蒂**: 没错，Oracle 提供物理的云基础设施，我们则是承诺消费这些算力的核心租户。

<details>
<summary>Original English</summary>

**Sachin Katti**: Oracle of the cloud. And we're consuming company so you're the core tenant from both the

</details>

**麦特·特克**: 这非常有趣。那么对于你们自己投资和设计的那部分项目，融资战略是如何运作的？显然，你们最近完成了一笔惊人的 122 亿美元融资，因此账面上并不缺现金。但对于建设周期极长、资产极重的算力而言，科技巨头通常会非常巧妙和战略性地利用债务工具。这是你们融资战略的一部分吗？你们在公司内部是如何思考算力资本运作的？

<details>
<summary>Original English</summary>

**Matt Turk**: Interesting. How does the for the stuff that you're building, how does the financing strategy work? You know, obviously you you you all raised what was it? The 122 billion was it the number um recently, so there's no uh shortage of cash, although, you know, um given all those expenses, I don't know, but um uh you know, the core resource of the world are famous for uh being very strategic users of debts. Um is that part of the financing strategy as well? How do you How do you all think about it?

</details>

**萨钦·卡蒂**: 对于我们目前所拥有的庞大算力，非常关键的一点是，我们有非常优秀的 hyperscalers 合作伙伴在为我们分担和引导这些资本支出。

微软、谷歌、亚马逊和甲骨文，它们在前端承载了沉重的物理基础设施建设资本。而我们则是“下家”（Off-take），即承诺去租赁和消费这些上线的算力资源。因此，我们在商业链条中扮演的是租户的角色，我们向合作伙伴承诺我们会消费这些算力，从而帮助他们完成资本的闭环。

<details>
<summary>Original English</summary>

**Sachin Katti**: I mean, uh with all of these compute uh that we have today, uh we have amazing partners who actually are channeling that for us. So, Microsoft, Google, Amazon, Oracle are we are off the off-take. So, we are the tenants, as you put it. So, we commit to consuming that compute, to buying that compute, whether it's online

</details>

**麦特·特克**: 也就是说，即便在你们参与设计和参与决策的 Stargate 框架下，你们也是作为租户去消费，而不是物理资产的拥有者？

<details>
<summary>Original English</summary>

**Matt Turk**: Also, across the board, like everything um you're um cuz you you you're building stuff as well. So, you're building you the partners are building Partners somebody. And you're always the across the board the the tenants, not the owner at the

</details>

**萨钦·卡蒂**: 没错。这是目前最符合逻辑和效率的商业划分。

<details>
<summary>Original English</summary>

**Sachin Katti**: Correct.

</details>

**麦特·特克**: 这样一来，极重资产的直接融资压力实际上被合理地“外包”给了你们的云巨头合作伙伴。

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. So, therefore, uh financing is outsourced to your partners. Okay.

</details>

### Jalapeno 项目的 9 个月“速度与激情”

**麦特·特克**: 让我们回到 Jalapeno 芯片上。我很想知道更多关于它在开发速度上的细节。我曾在某处读到，它从最初的设计到最终的芯片流片（Tape-out），仅仅花费了惊人的 9 个月时间。请带我们回顾一下，究竟是什么样的工程和战略因素，让你们能够以如此快的速度完成流片？

<details>
<summary>Original English</summary>

**Matt Turk**: We talked about the jalapeno, let this let this let's go into a bit more detail there um cuz in particular, it seems that you guys went incredibly quickly. And is that anything that I I read somewhere in 9 months from design to tape out? So, maybe maybe walk us through that and what was the reason it went so quick?

</details>

**萨钦·卡蒂**: 是的，9 个月的周期的确是非常惊人的速度，这几乎是我整个工程生涯中见过的最快流片速度。我认为这背后有几个非常关键的原因：

第一，我们有一支极其强悍且经验丰富的核心芯片团队。团队中的很多骨干成员在加入 OpenAI 之前，曾在谷歌主导并设计了多代 **TPU** 芯片。这是一群非常清楚如何在极高并发压力下把事情一次性做对的顶尖芯片专家。

第二，我们有一个非常强大的合作伙伴——**博通（Broadcom）**。博通在交付超大规模定制 ASIC 芯片方面，拥有行业内首屈一指的信誉和无可匹敌的工程技术积累。我们与博通的强强联合，为 Jalapeno 项目的极速推进提供了最坚实的保障。

第三，也是 OpenAI 独一无二的优势所在。在传统的芯片设计公司或商业芯片厂商中，当你设计一颗芯片时，你其实并不知道它最终会被用来运行什么工作负载。因为你是把芯片卖给不同的客户，每个客户运行的模型和应用都大不相同。这导致你在设计芯片时必须做大量的冗余和折中，以求得通用性。

而在 OpenAI，我们有着极其独特的“后向知晓”优势。**我们非常精准地知道我们未来想要运行什么模型，这些未来模型的数学结构是怎样的**。这让我们可以在芯片设计的早期阶段，直接砍掉一切不必要的通用冗余，在无数个芯片设计的分叉路口以最短的路径做出决策。这种“算法与芯片的共同设计”极大地缩短了芯片研发周期。

第四，也是最具有未来启示意义的一点：**AI 自身在 Jalapeno 的设计和物理优化中发挥了巨大的辅助作用**。在传统的芯片研发中，物理版图规划、布线优化等环节往往需要耗费数月的时间，因为这受限于人类工程师进行物理仿真和反复试错的时间。而通过引入 AI 算法来跑这些版图设计迭代，我们能够以极高的速度寻找到最优的物理设计解，从而把研发耗时压缩到了极致。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yes, it was incredibly quick. 9 months is very very fast, probably the fastest I've seen in my career. I think several reasons. One is uh it it's a team, it's a strong team. Uh they have many many of many of the team have designed TPU chips at Google in the past. So, very well experienced team. We have a great partner in Broadcom. That have a very strong track record of delivering get skills ASICs. So, I think a strong partnership with Broadcom and and making this happen. Three, I think perhaps Open AI unique fund. Uh in most chip companies or when you design chips, you don't know what you're designing it for. Because you are a vendor, the customer who you eventually runs the workload is someone different. Uh there's a unique advantage here of us knowing what the future models might look like and therefore being able to short circuit a lot of the decisions you need to make design decisions you need to make on the chip side. So, that that's super helpful. And finally, increasingly AI itself helping design and optimize the chip. That is usually the one that takes the longest time because human you're basically limited by how many human human human much human time is there to process all this data and run the experiments and we can do a lot of those iterations much faster.

</details>

**麦特·特克**: 是依靠 AI 来设计芯片？

<details>
<summary>Original English</summary>

**Matt Turk**: With AI?

</details>

**萨钦·卡蒂**: 是的，利用 AI。

<details>
<summary>Original English</summary>

**Sachin Katti**: Using AI.

</details>

**麦特·特克**: 也就是说，AI 现在已经在帮助自己设计未来的硬件载体了。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. So, AI is building its own chips now.

</details>

**萨钦·卡蒂**: 是的，那个时代已经并不遥远。在今天，AI 正在深度参与并辅助芯片的物理设计与优化。而在未来，我们相信**“递归设计”**（Recursion）的闭环迟早会完全合拢。在那个阶段，AI 会自己设计出它为了训练和运行下一代更强 AI 所需要的全部物理系统，当然也包括芯片本身。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yes. I think that world is not very far. I mean, AI right now is assisting in chip design. But we do believe that the world of recursion is not that far where AI will design the systems it needs to train and run the next generation of AI.

</details>

**麦特·特克**: 也包括芯片。

<details>
<summary>Original English</summary>

**Matt Turk**: And including chips.

</details>

**萨钦·卡蒂**: 没错，包含芯片。

<details>
<summary>Original English</summary>

**Sachin Katti**: Including chips.

</details>

### MRC 容错网络协议的技术革新

**麦特·特克**: 几周前你们还开源并发布了 **MRC**（Multi-Path Spraying Routing Protocol），这是一种全新的网络传输协议。请为我们深入讲解一下 MRC 究竟是什么，以及它在超级计算机和大规模计算集群中为什么扮演如此关键的角色？

<details>
<summary>Original English</summary>

**Matt Turk**: Including chips. You also released a a weeks ago uh MRC, which is a networking protocol. Uh walk us through through that. What is it and why is it a big deal?

</details>

**萨钦·卡蒂**: MRC 是一种全新的**网络路由与传输协议技术**，它主要是为了解决如何让拥有十几万张 GPU 的超大型计算集群网络稳定工作的问题。

试想一下，当你有 10 万张 GPU 连接在一起运行一个极其庞大的前沿模型训练任务时，由于模型本身的体量超出了单张卡甚至单个机架的物理极限，模型的权重和计算过程事实上被拆分并分摊到了整个 10 万张卡的庞大网络中。因此，在训练过程中，这些芯片之间在进行着永不停歇的超大规模数据同步与通信。

在 10 万张卡的物理规模下，各种网络链路、网卡、交换机的故障（Failures）不是偶尔发生，而是**每时每刻都在发生**。它的故障率是非常高的，你根本无法预知或枚举系统可能会以什么奇奇怪怪的方式出现硬件损坏或丢包。

而 MRC 的核心价值，就是**利用算法和协议在底层优雅地屏蔽掉所有这些密集的物理故障，从而让顶层的模型训练任务完全感知不到底层的网络波动**。对顶层的训练任务而言，它看到的是一个高可用的抽象网络系统，不需要担心任何因网卡坏了或光纤断了而导致的训练中断。网络总会稳定存在，总能自动找到数据的传输路径。

这就是关于**可用性**与**可靠性**的故事。

在物理实现上，MRC 采用的是**“多路径喷洒”**（Multi-path spraying）的机制。在任意两个 GPU 芯片之间，物理上都存在着无数条可以通过的路由路径，就像在一座大城市里，从 A 点到 B 点有成百上千条道路可以走一样。

传统的网络协议通常是为一次通信选定一条固定的道路。如果这条路在半途发生了拥堵或坍塌，通信就会中断。而 MRC 则不同，它会将数据包像雨水一样“喷洒”分摊到所有可用的物理路径上。数据包走不同的路前往终点，只要有路径能够走通，数据就能安全抵达。

这种设计让局部的物理故障不再成为阻碍整个训练任务的“致命要素”（Showstopper）。在如此庞大的数据中心规模和吞吐速度下，能把这套多路径喷洒机制做到极致的低延迟和高吞吐，在工程上面是非常困难的。这也是为什么 MRC 的发布在行业内引起了如此大的关注。

<details>
<summary>Original English</summary>

**Sachin Katti**: It's a new uh networking uh protocol routing technology, if you will. Uh uh uh to scale these really large cluster fabrics. So, imagine you have uh 100,000 GPUs. Uh They need to be connected together. And uh when you're doing large training runs, uh they're constantly communicating with each other because these models are so large that the processing of the models is happening over the entire 100,000 GPU cluster, for example. And you can imagine imagine the number of links and switches and NIC cards that need to be there to connect all of these chips together. At this scale, failures are common. Right? Happens all the time. Uh you can't really even enumerate all the ways things could fail. So, the strategy behind MRC is how do you design algorithms and protocols that can gracefully um mask all these failures and make sure that the training workload does not get impacted. Right? It just The network is an abstracted system that the training job does not ever worry. It's always going to be there. It's always going to find a path even if a link fails. So, it is all about reliability. It is all about availability. So, how do we design protocols that can tame the complexity of such a such a big cluster and make sure that we don't get stopped because of failures, which are very common in the system. So, MRC is like a multi-path spraying protocol where you can spray packets over multiple paths. So, between any two chips, there are many many routes to get there, kind of like between any two points in the city there are many routes. So, instead of picking just one route, we will we will send traffic across all of them, and whichever one succeeds, you take that. Right? And so, that way even if any one of them fails, it's not a showstopper. So, that's kind of the basic intuition behind it. It's obviously a lot more sophisticated than that. But, doing this at scale and that speed is hard, and so that's why it's quite innovative.

</details>

### 无处不在的物理供应链瓶颈

**麦特·特克**: 在你当前的工作中，最主要的瓶颈是什么？毕竟在计算机行业中，瓶颈的性质随着技术演进而一直在发生变化。例如现在很多人在讨论 HBM 内存的稀缺。这是否也是制约你们的瓶颈之一，还是说有其他更核心的障碍？

<details>
<summary>Original English</summary>

**Matt Turk**: What are the bottlenecks that you experience these days? So, since like the nature of the bottleneck keeps changing in the computer industry, um uh obviously people talk a lot about memory these days. Is that Is that one of them? Or what what else?

</details>

**萨钦·卡蒂**: 老实说，目前在物理供应链上，**瓶颈几乎无处不在**。并没有哪一个单一的瓶颈在起决定性作用。

我们在建设数据中心的每一个物理环节都遭遇着不同程度的制约：这包括前期的规划与环评许可审批的漫长周期、大型重型天然气轮机的产能制约、以及高压大功率变压器的漫长交期。

在过去的十几年中，电力变压器和重型燃气轮机这些传统重工业，市场需求一直非常平稳，因此厂商并没有动力去盲目扩张产能。然而，这一轮算力大潮带来了一个极其剧烈的**需求震荡**。这些重工业厂商不可能在短短几个月内就拔地而起一座新的工厂来交付更多的变压器，这需要数年的资本开支周期。所以我们目前正在竭尽全力去填补这个供应链的巨大鸿沟。

<details>
<summary>Original English</summary>

**Sachin Katti**: I think they're bottlenecks everywhere, to be honest, to the supply chain. Uh so, I don't think there's any one, right? Uh we have bottlenecks in the data center building itself, around permitting, around availability of gas turbines, transformers. Those industries capped historically have not added much capacity over the last decade or so ago, and they've suddenly experienced a demand shock. Yeah. And it takes years before you have capacity to produce more turbines and transformers. So, we're trying to play catch-up.

</details>

**麦特·特克**: 那么在人力资源层面呢？比如具备专业资质能够处理这些超高压电的数据中心专业电工、管道技工等蓝领技术工人是否也面临短缺？

<details>
<summary>Original English</summary>

**Matt Turk**: And to the job thing that you that you mentioned earlier, is there like a shortage of like electricians and and and my technical people trade people that know how to build those things as well? Is there a human

</details>

**萨钦·卡蒂**: 确实面临极其严重的人力短缺。

<details>
<summary>Original English</summary>

**Sachin Katti**: Absolutely. Yeah. Absolutely. So,

</details>

**麦特·特克**: 这就是为什么有人调侃：随着 AI 开始逐步替代一部分办公室里的白领脑力劳动者，年轻人或许应该去学习成为一名电工。

<details>
<summary>Original English</summary>

**Matt Turk**: That's why we should all do uh as AI replaces uh knowledge workers become electricians.

</details>

**萨钦·卡蒂**: 的确如此。目前在电工、管工等各种专业技术工种上，整个行业都面临着巨大的缺口。这些岗位在今天的待遇是非常丰厚的，所有的超大型云厂商、AI 实验室都在疯狂抢夺这些专业技工。如果年轻人具备相关的物理与电气技能，他们根本不需要担心未来的生计。随着我们尝试建造越来越多、规模越来越大的算力工厂，这一人力瓶颈正在变得愈发凸显。

<details>
<summary>Original English</summary>

**Sachin Katti**: No, I think there is a definitely a shortage of electricians, plumbers, all kinds of trades, you name it. So, anything we can do to train more folks to be able to do those They're a very well-paying jobs uh that a lot of us all of the hyperscalers, all of the labs would actively hiring for if you had the like qualifications, so I think that is definitely a bottleneck. I think they're becoming an increasingly bottleneck because we're all trying to build more and more and we have unlimited number of things these capabilities.

</details>

### “算力即服务”与保证代币额度

**麦特·特克**: 聊聊商业侧的事情。你们最近推出了一项非常新颖的商业模式：面向企业客户提供**保证容量（Guaranteed capacity）**以锁定算力。这非常耐人寻味，它让 OpenAI 听起来越来越像是一家提供计算资源的公用事业公司（Utility company）。这背后的商业逻辑和战略考虑是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: Right. Let's talk for a minute about the the business side of things. Another thing you launched recently is guaranteeing capacity for customers to lock in compute. Um That which is interesting, right? It almost feels like OpenAI is also becoming a utility company providing computing to others. Uh uh what's the story behind that and the the the strategy?

</details>

**萨钦·卡蒂**: 所谓保证算力容量，在我们的商业定义里，本质上指的是**保证 Token 的额度**。

我们实际上是在向企业客户做出承诺：我们会为你保证特定额度、由智能生成的 Token 供给。在今天算力处于极度制约、Token 供给极其宝贵的世界里，这套逻辑是非常自然且合理的。

对于今天乃至未来的数字化企业而言，**“智能”已经成为像电力、石油一样的核心生产要素**。为了确保其业务的正常运转，企业需要源源不断的智能 Token 输入。如果算力供给存在波动，企业就不得不承担业务中断的巨大风险。

因此，我们推出的保证容量模式，正是为了向企业客户提供一种“供应链安全感”，确保他们业务所需的智能额度不会在关键时刻断供。我认为这是一种非常健康的商业卫生习惯（Business hygiene）。当你把智能视为最重要的生产原料时，在商业合同上提前锁定这部分的稳定供应是极具战略眼光的。这就是我们正在努力去满足的企业侧需求。

我知道这可能是一个相对崭新的商业概念——去锁定智能的算力额度。但这就是我们正在见证的历史：智能正在成为每一个数字化企业最核心的公用事业输入。

<details>
<summary>Original English</summary>

**Sachin Katti**: Yeah, so guaranteed capacity is guaranteed tokens. Right? So, we are effectively saying we will guarantee you a certain dollars worth of tokens of intelligence. I I mean, it makes sense, right? So, in a world where compute is a shortage, therefore tokens are always going to be at a premium. And there's a shortage of tokens that we can produce even the limited compute that we have. And as this becomes a fundamental input to the enterprise, right? So, enterprises are going to need intelligence, more and more of it to run. Right? And so, this is a way of enterprises gaining assurance that the tokens of intelligence that they need will be there for them. And so, they they don't have to take business risk. Right? And so, I I I think it's uh it's good business hygiene. If you have a critical supply resource and every enterprise, intelligence is kind of the most important supply item, issue it. Uh it makes little sense to make sure you secure that supply. And so, that's that's the demand we're trying to fulfill. Yeah. I know it's a new concept, like what does it mean to have guaranteed capacity for the intelligence? But I think that's what intelligence is becoming. It is becoming a supply unit for every digital enterprise.

</details>

### 太空数据中心的科幻与现实

**麦特·特克**: 在访谈的最后，让我们聊一个轻松有趣的话题。你可以选择脱掉 OpenAI 的官方身份来回答。那就是——太空数据中心（Data centers in space）。你觉得这是一个令人兴奋的蓝图，还是纯粹的科幻小说？或者它在未来确实是某种必要的算力载体？还是说大家仅仅因为好玩和酷炫才去讨论它？你在这个问题上持什么态度？

<details>
<summary>Original English</summary>

**Matt Turk**: Right. So, maybe to end on a fun one, uh, and you can answer either with your open eye hat on or not, uh, data centers in space. Is that Is that, uh, is that exciting? Is that science fiction? Is that, uh, needed? Is it something that people like to talk about just because it's cool? Or where where where do you land?

</details>

**萨钦·卡蒂**: 从一个工程师和科技极客的直觉出发，这无疑是非常令人兴奋的。去想象一个漂浮在轨道上的卫星星座在太空里源源不断地生成和分发算力，这画面确实非常酷。

而且我个人认为，在技术层面上，这在未来是完全可行的。随着时间的推移和资金的持续注入，那些轨道动力学、太空散热等工程难题都是可以被逐步解决的。

至于它是否是未来所必须的，我相信在未来的算力图谱里，必然有属于“轨道计算”（Orbital compute）的一席之地。虽然它无法彻底取代地面上的主力算力网络，但它一定会成为我们算力军火库中一个非常好的补充手段。

目前我们正在等待的关键临界点在于：**什么时候太空发射的商业性价比能够发生根本性的改变？以及什么时候太空抗辐射硬件的经济性能够发生改变？**

因为要让太空算力真正商业化落地，我们必须能够以极度廉价的门槛将硬件送入轨道。并且，由于在太空中你无法派个工程师上去换配件，所以当某个太空计算节点发生硬件故障时，它的成本必须低到可以直接被抛弃和替换掉而不至于让人肉疼。当太空产业跨过这个性价比临界点时，太空数据中心就会真正走向现实。

<details>
<summary>Original English</summary>

**Sachin Katti**: For for the geek in me and the engineer in me, it's definitely exciting. It's, uh, one of those things that can be super cool to see a constellation of satellites producing compute. Uh, I actually think it is, uh, it will become feasible, right? As engineering problems we solve. Uh, but they can be solved, uh, with enough time and investment. Uh, whether it is needed, uh, I think there is room for orbital compute. Uh, I don't think it's going to solve all the compute needs, but it's uh, definitely going to be a complement in the arsenal. I think what we are waiting for is when does the economics of the launching satellite change? And when does the economics of the hardware change? Because we need to get to a point where it's cheap to launch the hardware. And if something fails, it's cheap to throw it away. You I mean, you can't go up and fix it. Uh, unlike on the ground. Uh, and so I think that inflection point hopefully happens soon and at that point time it becomes viable.

</details>

**麦特·特克**: 好的。萨钦，这是一次非常美妙的对话。非常感谢你今天抽出时间来与我们交流。我们深表感谢。

<details>
<summary>Original English</summary>

**Matt Turk**: Correct. So, Chirag has been a wonderful. Thank you so much for spending time with us. We appreciate it.

</details>

**萨钦·卡蒂**: 非常感谢。这是一次非常愉快的聊天。

<details>
<summary>Original English</summary>

**Sachin Katti**: Thank you. It's been great to have have this chat.

</details>

**麦特·特克**: 好的，我是特克。感谢大家收听本期 Mad Podcast。如果你喜欢这期节目，且还没有订阅的话，请考虑订阅或在我们播出的平台上为我们留下好评与留言。这能极大地帮助我们把播客办得更好，并邀请到更多优秀的嘉宾。谢谢大家，我们下期节目再见。

<details>
<summary>Original English</summary>

**Matt Turk**: Cool. Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks and see you on the next episode.

</details>