---
author: All-In Podcast
date: '2026-09-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=yAsrMA_ADPc
speaker: All-In Podcast
tags:
  - dynamical-systems
  - energy-efficiency
  - hardware-architecture
  - semiconductor-physics
title: Unconventional AI 探索基于动力系统与半导体物理的新型能效计算架构
summary: Naveen Ralph 介绍了初创公司 Unconventional AI 的技术构想。公司旨在摆脱传统数字抽象，利用动力系统理论及半导体物理特性来构建新型硬件与整机柜系统，计划在数年内大幅提升能效并运行模型。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Naveen Ralph
companies_orgs:
  - Unconventional AI
  - Nirvana Systems
  - Databricks
  - Intel
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/4 -->

### 讲者介绍与开场

Naveen Ralph，Unconventional AI 的联合创始人兼 CEO，这是一家 AI 芯片初创公司。

<details><summary>Original English</summary>
Naveen Ralph, co-founder and CEO of Unconventional AI, which is an AI chip startup.
</details>

>> 最为人所知的是创立并出售了两家深科技公司。[音乐] Naveen 在定义上算是一位特立独行的创始人。我刚去那里时，我们大概有 2000 万美元的业务规模，而当我离开时，你们知道，已经达到了 7 亿或 8 亿美元。[音乐]

<details><summary>Original English</summary>
>> Best known for building and [music] selling two deep tech companies. Naveen is kind of definitionally outlier founder. When I came there, we had about a $20 million business and it was, you know, 7 or 800 [music] million when I left.
</details>

>> 我认为除非你能亲手把它造出来，否则你并不是真正理解某件事物。

<details><summary>Original English</summary>
>> I don't think you really understand something until you can build it.
</details>

>> 仅仅因为某件事物被尝试过，并不意味着它是错的。[音乐]

<details><summary>Original English</summary>
>> Just because something is tried does not mean it's [music] wrong.
</details>

>> 我与 AI 毁灭论者恰恰相反。我认为 AI 是人类的下一次演化。我们需要在硬件基底上进行创新，以真正构建起真正的智能。

<details><summary>Original English</summary>
>> I'm the opposite of an AI goomer. I think AI is the next evolution of humanity. We need innovation on the hardware substrate to actually build true intelligence.
</details>

>> 掌声欢迎 Naveen Ralph。[音乐]

<details><summary>Original English</summary>
>> Please welcome Naveen Ralph. [music]
</details>

大家好，很高兴来到这里。嗯，你们知道，现在稍微把话题切换到 AI 上，关于 AI 你们可能已经有所耳闻了。嗯，能来参加这次大会特别令人兴奋，因为正如刚才介绍中所说，我与毁灭论者完全相反。我认为 AI 是人类创造的最具变革性的技术之一，并且将使我们能够达到下一次演化的水平，这就是我为此而来的原因。嗯，这也是一次反毁灭论者的大会。那么，让我们开始吧。[笑声]

<details><summary>Original English</summary>
Hey everyone, great to be here. Um, you know, switching gears a little bit to AI now, which you may have heard a little bit about. Um, it's super exciting to be at this conference specifically because as was said in the uh intro, I'm the opposite of a doomer. I think AI is one of the most transformational technologies that humanity's ever created and will enable us to get to that next level of evolution which I'm here for and uh this is sort of the anti-doomer conference. So, let's go. [laughter]
</details>

### 个人背景与创业历程

嗯，所以在我们深入之前，我先介绍一下我自己。嗯，你们知道，我这挺不可思议的。我真正处在我一生都想身处的位置。呃，这是我大概五六岁时的样子，差不多那样。我们很早就拥有一台电脑，所以这会暴露我的年龄，不过呃那是在 1978 年。我们有了一台电脑。这大概是在 80 年代初。呃，在我还是个小孩时就学会了编程。我当时只觉得它就像个谜题。嗯，你们知道，后来学会了我成了一名电气工程师。嗯，其实是因为我喜欢科幻小说，而且总是想思考我如何能造出一台智能机器。呃，你们知道，在经历了制造计算机的职业生涯后，我又回到学校并拿到了神经科学的博士学位，当时的想法就是，让我们回到那个问题：我们如何让计算机具有智能？幸运的是，整个世界在某种程度上都朝着这个方向发展了。所以你们知道，作为一名技术人员，现在这有点像梦想成真。

<details><summary>Original English</summary>
Um, so before we get going, I'll tell you a little bit about myself. Um, you know, I'm it's kind of weird. I'm really right where I wanted to be my whole life. Uh this was me at about five or six years old, something like that. We had a computer very early on, so I'll date myself, but uh this was in 1978. We got a computer. This is probably in the early 80s. Uh learned to program when I was a little kid. I just thought it was like a puzzle. Um you know, learned to I became an electrical engineer. Um really because I enjoyed sci-fi and always wanted to think about how I could make a intelligent machine. And uh you know then after a career in uh building computers I went back to school and got a PhD in neuroscience and the idea was like let's go back to that thing how do we make computers intelligent and fortunately the whole world kind of moved in this direction. So you know as a technologist it's sort of the dream right now.
</details>

嗯，关于我从技术呃公司创业的角度来看的一点背景，比如我实际上创立了第一家名为 Nirvana Systems 的 AI 芯片公司。嗯，这是在 2014 年，如果有人还记得那时的话，当时还没有 AI，或者至少在普遍的话语体系中没有，呃，当时确实很难让人们相信这很重要，更不用说围绕它构建硬件了。现在你们从台上的 Jensen 那里听到了，比如全球最大的公司是一家硬件公司，全因 AI。所以我们很早就入局了。嗯，我认为我把公司卖给英特尔卖得太早了，呃，但我呃我运营我创立并运营了英特尔的 AI 部门。

<details><summary>Original English</summary>
Um a little bit about me tech uh from a company entrepreneurship standpoint like I actually founded the first AI chip company called Nirvana Systems. So um this was in 2014 if anyone remembers back then there was no AI or at least not in the common vernacular and uh it was really hard to actually convince people that this is important much less to build hardware around it. Now you heard from Jensen up here like the largest company in the world a hardware company because of AI. So we were early on um I think I sold the company way too early uh to Intel but I uh I ran I started and ran the AI group at Intel.
</details>

嗯，在 2020 年完成了那段经历后，我其实开始思考下一个问题，那就是我们如何构建更大的模型，就像我们今天谈论的大语言模型一样。当时的问题是，我该如何构建基础设施来打造这些模型？于是我们开始将 GPU 平台化，使其能够扩展，并让其他人能够轻松使用。在 2022 年 ChatGPT 出现之后，对于人们开始构建自己的模型来说，我们可以说是当时最好的选择。所以业务起飞得非常快。我们决定与 Databricks 联手。嗯，那是在 2023 年，而且呃实际上那占到了如今 Databricks 总营收的四分之一。所以嗯，与 Databricks 的 Ali 及其团队一起完成那整件事非常有趣。

<details><summary>Original English</summary>
Um, after I was done with that in 2020, I actually started thinking about the next problem, which was how do we build bigger models like the large language models we talk about today. And it was about how do I build the infrastructure to build those models? And so we started platformizing GPUs and enabling it to scale and making that easy to use for other people. And after chat GBT happened in 20 2022, we were kind of the best game in town for people to start building their own models. So took off really fast. We decided to actually join forces with data bricks. um that was in 2023 and and uh actually that's a quarter of the total revenue of of data bricks today. So um a lot of fun doing that whole thing with uh Alli and team at data bricks.
</details>

### Unconventional AI 的使命与组织架构

现在我想向大家介绍 Unconventional AI，它正在重新思考计算机运作的基础。所以这里我们正在回归第一性原理，真正试图构建一台全新的机器。长久以来，计算机一直以某种特定的方式运行。我们希望重新思考这一点，完全是为了实现极其节能的单一目的，而目标一直是——最初是在 5 年内达到 1000 倍的能效提升。我实际上已经把这个目标调整为三年半，因为进展比我们预期的要快。有趣的是，由于 AI 的帮助，我们实际上更快地解决了一些非常深奥的科学难题。

<details><summary>Original English</summary>
And now I want to tell you about unconventional AI which is rethinking the foundations of how a computer works. So there we're going back to first principles here to really trying to build a new machine. Computers have worked a certain way for a long time. We want to rethink that for the singular purpose of making something very power efficient and the goal has been within it was initially within 5 years to get to a 1000x power efficiency. I've actually revised this to three and a half years because things have gone faster than we anticipated. We've actually solved very deep scientific problems quicker because of AI interestingly enough.
</details>

那么简单介绍一下我们是如何组织的？比如我们是一家真正的自顶向下贯通的公司。我们从理论家开始。这些人拥有数学博士学位，以及嗯你们知道的理论神经科学等背景。他们提出你们所知道的各种概念，从减少信息搬移的角度来看，我们认为这些概念能够有效地为我们带来更高的能效，然后我们将其转化为模型，这些模型在真实数据上进行训练，并依据真实标准进行评估，从而完成实际任务。所以这算是这些概念落实到了实处。然后最终我们必须真正制造出物理实体。因此这些人负责构建物理电路的架构，嗯实际设计那些电路，呃对它们进行建模，并观察其是否能真正起效，我们努力将整个技术栈连接在一起。嗯，然后最终我们必须构建一个系统、一块板卡以及所有那类东西，并打造出一款产品。

<details><summary>Original English</summary>
So just a little bit how are we organized? Like we're truly a toptobottom company. We start with theorists. These are people with like math PhDs and um you know theoretical neuroscience that kind of thing. They come up with you know concepts that we think would effectively give us more power efficiency from the perspective of moving less information around and we then translate that into models and that do real things trained on real data and evaluated against real criteria. So it's kind of the rubber hitting the road of these concepts. Then eventually we have to actually build something physical. So these are people who architect a physical circuit um actually design those circuits uh model them and see if it actually works and we try to connect this whole stack together. Um then eventually we have to build a system and and a board and all that kind of stuff and build a product.
</details>

### AI 的能源挑战与算力瓶颈

那么能源真的构成问题吗？呃我不确定在座的各位对这个问题思考了多少，但有趣的是，我会在这里给你们提供一些数据点。这是一家公司，仅仅是 Google。我用 Google 为例是因为 Google 实际上公开谈论过这个。嗯，他们每个月处理的 token 数量突破了 3.2 拍（3.2 千万亿）。这是一个疯狂的数字。我甚至从来——我从来都不以拍（千万亿）为单位来思考，但这就是我们今天所处的世界。而如果我按每个 token 消耗 10 焦耳能量来计算——就模型而言，这实际上处于能耗区间的偏低水平。但我们就取这个数值进行乘法计算。这是 12 吉瓦。美国目前为数据中心投入的大约是 40 吉瓦能源。而我们大约占了全球数据中心容量的一半。所以，你们知道，今天全球数据中心的能源规模在 100 吉瓦以下。仅一家公司在 AI 服务上就要消耗 12 吉瓦。所以，你们可以想象，如果模型变得更大，能耗就会上升；如果需求增长——而且事实确是如此——能耗也会上升。因此，根据我的估计，我们大概在 3 年左右的时间里就会非常快地耗尽能源。

<details><summary>Original English</summary>
So is energy really a problem? Uh I'm not sure how much everyone in this audience has thought about this but interestingly enough I'll give you some some data points here. This is one company. This is just Google. I'm using Google because Google has actually talked about this publicly. um per month they cross 3.2 quadrillion tokens. It's a crazy number. I never even I never think in quadrillions but that's the world we're in today. And if I just take 10 jewels per token of energy. This is a actually on the lower end of uh of the energy spectrum for models. But let's just take that number and multiply it out. This is 12 gawatt. The US puts about 40 gawatts of energy into data centers today. And we're about half of the data center capacity of the world. And so, you know, we're under a 100red gawatts of of data center energy in the world today. 12 gigawatts is going into one company just for AI services. So, you can imagine if models get bigger that that energy goes up and if demand grows, which it is, that energy goes up. So, we're going to run out of energy pretty fast in like 3 years or so is my estimate.
</details>

所以，直观地用图表来表达，这就是我们面对的现状。你们知道，我们拥有这个正在呈指数级增长的庞大市场，姑且称其为 2030 年的万亿美元市场，也许比这还要大。然后我们在底部只有这种近似线性增长的能源。所以关于这一点你们今天已经听到了很多。呃但是这个缺口就是问题所在。而我们希望用技术来解决这个缺口。

<details><summary>Original English</summary>
So, really just putting it graphically, this is what we have. You know, we have this huge market that's growing exponentially. call it a trillion dollar market in 2030. Maybe it's bigger than that. And then we have this kind of linearized energy at the bottom. And so you've heard a lot about this today. Uh but this gap is the problem. And we want to solve that gap with technology.
</details>

嗯，我不知道大家是否意识到这一点，但在过去的几年中，我们对数据中心的考量方式已经发生了转变。过去关注的是占地面积。我能拿到机房空间吗？我能拿到机架空间吗？然后变成了网络设备。接着变成了 GPU。今天关注的则是能源。首先你要考虑能源。我拿到用电合同，然后我必须想办法去填满它，并且基本上是用 GPU 以及类似设备来构建基础设施。提供一个 token 服务的成本中大约有 50%——所以每当你在 ChatGPT 上尝试一些东西时，其中 50% 的成本是能源。其余部分是硬件资本支出以及占地面积等等所有那类开销。所以今天我们有点认为——哎呀，我们有点认为它相当于：我拿到一份电力合同，我需要将每一瓦特货币化变现；简单来说，我们的商业逻辑非常直接，我们要比现有硬件高出 1000 倍地去将它货币化变现。

<details><summary>Original English</summary>
So um I don't know if people are aware of this, but the way we think about data centers has shifted over the last several years. It used to be about floor space. Can I get the floor space? Can I get the rack space? Then it was about networking equipment. Then it became about GPUs. Today it's about energy. First you think about energy. I get the energy contract and then I have to figure out how to fill it and and basically create u u um uh infrastructure out of out of GPUs and things like this about 50% of the cost of serving a token. So every time you try something on chat GBT 50% of that cost is energy. The rest of it is the capex of the hardware and the floor space and all that kind of stuff. So today we sort of think about oops we kind of think about it as I get I get a a power contract I need to monetize every watt and simply put our business case is pretty easy we're going to monetize that a thousandx better than existing hardware.
</details>

### 从生物大脑中汲取启发

那么接下来的问题就变成了：好的，很好，这一切都讲得通，但我们真能做到吗？我们如何制造一台更好、更高效的计算机？在这方面，生物学实际上为我们提供了一些证据。大家可能听说过，人类大脑运转的能耗大约是 20 瓦。而更让我惊叹的其实是动物大脑。那个红色的数字代表大脑中神经元的数量。如果将其线性向下缩放到比如猴子的大脑，它的运转功率只有 1 瓦。为了便于理解，你口袋里的手机运行功率大约就是 1 瓦。而其他动物，比如你们知道的老鼠、蝙蝠等类似动物，它们运转的能耗只有毫瓦级。所以拿一个大家都能产生共鸣的动物来说，那就是松鼠。你可能观察过

<details><summary>Original English</summary>
So then the question becomes, okay, great, that all makes sense, but can we actually do it? How do we build a better, more efficient computer? Well, biology actually provides some proof for us here. So the human brain, you may have heard this, runs on about 20 watts of energy. And what's even more remarkable to me is actually animal brain. So that red number is how many neurons are in the brain. And if you kind of scale it linearly down to like a a monkeykey's brain, it runs on one watt. To put that in perspective, the cell phone in your pocket runs on about one watt. And other animals like you know um rats and bats and things like this. They run on millowatts of energy. So just something that's pretty relatable to everyone is a squirrel. You probably watched
</details>

<!-- chunk 2/4 -->

能有多精准。它们在树枝间跳跃，连续一千次都能做到分毫不差。它们的大脑仅靠 8 毫焦（mill）的能量运行。你可以在手机上运行 100 多个松鼠大脑，而且它具有非常精确、到位的行为表现。

<details><summary>Original English</summary>
how accurate they can be. They jump between branches and they do it perfectly a thousand times out of a thousand. Their brain runs on 8 mill of energy. You could run over a 100 squirrel brains on your phone and it it has very precise and accurate behavior.
</details>

所以，大自然创造了非常不可思议的东西。事实上，它是承载智能的恰当物理基质。

<details><summary>Original English</summary>
So biology created something quite incredible. In fact, it's the right kind of physical substrate for intelligence.
</details>

这是我很喜欢的一句话：“如果我们无法创造一样东西，我就觉得我们并未真正理解它。”我们在创造智能系统方面已经取得了很大进步。

<details><summary>Original English</summary>
So, this is a quote I love. I don't feel like we truly understand something until we can create it. We've gotten a lot better creating intelligence systems.
</details>

然而，这些系统的运作方式在某种程度上是低效的。存在怎样的低效呢？正如我一开始所暗示的，计算系统中的大部分能量都消耗在信息的搬运上。拿具体数字来说，人类大脑皮层——也就是大脑表面那些褶皱的部分——每秒仅移动大约 160 亿个比特。仔细想想，这其实是个很小的数字，因为皮层中大约有 130 亿或 140 亿个神经元。

<details><summary>Original English</summary>
However, they do it in a kind of inefficient way. What kind of inefficiency is there? Well, as I kind of hinted at the beginning, most of the energy in a computing system goes into moving information around. Just to put some numbers on it, the human cortex, the squiggly part of your brain, the outside of it, um, only moves about 16 billion bits per second. That's actually kind of a small number if you think about it because there's, you know, some 13 or 14 billion neurons in that cortex.
</details>

而一个 GPU，或者说高端计算系统，每秒进出内存的数据量接近 30 万亿比特。这还只是在芯片外部。在芯片内部，这个数字可能还要高出 10 到 100 倍。因此，我们在这些人造系统中搬运的比特数远远超过大脑。而这正是推动能源需求的原因。

<details><summary>Original English</summary>
Um, a GPU or, you know, a high-end computing system moves nearly 30 trillion bits in and out of memory per second. That's outside the chip. Inside the chip, it's probably, you know, 10 100x more than that. So we're moving a lot more bits in these synthetic systems than the brain does. And that's actually what drives the energy demand.
</details>

### 计算范式的演进与局限

我们是怎么走到这一步的呢？计算机其实以某种形式存在数百年了。它们最初是机械的，到了世纪之交变成了模拟计算机，而在 20 世纪 30、40 年代变成了数字计算机。

<details><summary>Original English</summary>
And you know how do we get here? You know computers have been around for hundreds of years actually in some form. They were mechanical. They became analog around the turn of the century and they became digital back in the 1930s 1940s.
</details>

所以，1940 年、1945 年计算机的运行机制实际上和今天的计算机非常相似。并没有发生巨大的范式转变。实际上就是将内存置于外部，有一套计算单元，然后在二者之间来回搬运比特。这种运作方式造就了一台需要大量数据搬运的机器，但它的速度非常快。我们制造计算机就是为了追求速度，它们始终比替代方案更快。

<details><summary>Original English</summary>
So this the operation of that computer in 1940 1945 is actually very similar to how they operate today. There's not a huge paradigm shift. actually have this memory on the outside. You have some kind of computing and you move bits back and forth. That operation creates a machine that just requires a lot of movement but it's very fast. We built computers to be fast. They were always faster than the alternative.
</details>

顺便提一句，1945 年建造的那台名为 ENIAC 的计算机，其设计初衷是用于计算火炮弹道轨迹，它的制造就是为了比替代方案更快。当时的替代方案是人工计算。而现在的替代方案通常是另一台计算机——比如这台计算机的速度是那台的两倍。我们就是这样销售计算机的，但它并未考虑能效问题。而这正是我们正在改变的地方。

<details><summary>Original English</summary>
Uh incidentally that computer in 1945 that was built called Eniac was built to do artillery trajectory calculation and it was built to do it faster than the alternative. The alternative were humans who actually did the calculations. Now the alternative typically is some other computer. this this computer is twice the speed of that computer. That's how we sell computers, but it's doesn't contemplate energy efficiency. And that's what we're changing.
</details>

大家知道，这些趋势已经持续了很长时间：晶体管数量不断增加，但我们无法继续提升运行频率，也无法继续提升单线程性能。而现在，我们在能效方面也无法继续扩展了。如果你听说过摩尔定律的话，它所代表的将晶体管做小这一路径基本已经走到尽头。因此，单纯依靠缩小晶体管尺寸已经无法获得能效提升了。所以我们需要重新思考这个问题。

<details><summary>Original English</summary>
And you know, these have been trends going on for a long time where the number of transistors kept going up, but we couldn't keep scaling the frequency. We could couldn't keep scaling uh single thread performance. And now we're actually not scaling efficiency any longer. Moore's law, if you may have heard of this, it's like making transistors smaller has largely ended. So we're not seeing efficiency gains just from making transistors smaller. So we need to rethink the problem a bit.
</details>

### 打破抽象层与物理计算

那么我们该怎么做呢？一个很好的直觉思路是省去中间环节。计算机是建立在这些抽象层之上的。正如我提到的“数字”，“数字”意味着 1 和 0。这本身就是对物理世界的一种抽象。事实上并没有天然表现为 1 和 0 的物理系统。晶体管实际上存在中间状态，但我们通过工程手段让它表现出那种特性。这就是一种抽象。我们不断叠加这些抽象层，最终开始在上面构建神经网络和学习机器。

<details><summary>Original English</summary>
So how do we do it? Well, a good intuition is that we cut out the middleman. So computers have been built up with these abstractions. So I mentioned digital. Digital means one and zero. That itself is an abstraction of the physical world. Like we don't actually have systems that behave as one and zero. A transistor actually has states in the middle. But we engineer it to behave that way. And that that's an abstraction. So we kept building these abstractions up and eventually we started creating neural networks and learning machines on top of it.
</details>

这里的每一个抽象层实际上都是有损的，意味着它是低效的。它并未顾及底层所有的复杂性，这正是抽象的本质。所以我们正在做的事情从某种意义上来说是对其进行简化。我们找到半导体物理特性的某种抽象，并将其与神经网络连接起来。如果你想想自己的大脑，它包含大量神经元，但里面并没有线性代数，也没有浮点数运算。实际上是神经元的物理特性催生了智能。我们希望通过半导体来模仿其中的一部分。

<details><summary>Original English</summary>
Each one of these abstractions actually is lossy. It means it's inefficient. It it it doesn't contemplate all the complexity underneath it. That's why it's an abstraction. So what we're doing is kind of simplifying this in some sense. We find an abstraction of the physics of the semiconductor and connect that to the neural network. If you think about your brain for a moment has a bunch of neurons in it, but there's no linear algebra. There's no uh floatingoint math. It's actually the physics of the neurons give rise to intelligence. We want to kind of mimic some of that uh with a semiconductor.
</details>

这也并非新概念。大自然中处处存在计算。比如鸟群。大家可能见过类似的情形：一只鸟做出简单的行为——看看左边，看看右边，弄清楚旁边的同伴要去哪里。当它们这样做时，实际上产生了这些有趣的群体飞行行为，即涌现行为。我们在蚁群中也能看到这一点。蚁群仅凭极其简单的规则就能完成智能行为。

<details><summary>Original English</summary>
And this is also not a new concept. There's actually computation all throughout nature. Uh birds in a flock. You may have seen things like this where you know a bird does a simple behavior. It looks left, looks right, and figures out where the next guy's going. And when they do that, they actually create these interesting flocking behaviors, this emergent behavior. And we see that with ant colonies. Ant colonies actually do intelligent things just by very simple rules.
</details>

这门研究被称为动力系统理论。它基本上研究的是如何从各个组成部分的极其简单的行为中获得这些涌现特性。我们的大脑实际上也是这样工作的。因此我们正在吸收这些想法，并实际开始利用它们来构建电路。

<details><summary>Original English</summary>
And uh this study is called dynamical systems theory. It's basically how I get these emergent properties from very simple behaviors of individual components. Our brain actually works this way as well. So we're taking these ideas and actually starting to build circuits out of them.
</details>

### 振荡器与动力系统模型

让我举一个这种系统的例子。在场的各位大概都知道什么是节拍器。就是学弹钢琴时用到的那种“嘀嗒、嘀嗒”来回摆动的物理装置。有趣的是，如果把多个节拍器放在一块刚性平板上，且这块平板可以来回滚动，你会发现它们开始同步。这纯粹是由系统的物理特性决定的。它们各自对平板施加微弱的作用力，即便彼此之间有些许偏差，最终都会同步到完全相同的相位。

<details><summary>Original English</summary>
So let me give you an example of such a such a system. So everyone here probably knows what a metronome is. just, you know, when you're learning to play the piano or something like that, it's just tick tock tick- tock physical thing moving back and forth. So, this is kind of cool. If you put multiple ones of them on a rigid plank and that plank can just roll back and forth, you'll actually see them start to synchronize. And that's just due to the physics of the system. They each push against the plank just a little bit. And even if they're off by a little bit from each other, they'll all synchronize to exactly the same phase.
</details>

在物理系统上你甚至可以扩展到数百个节拍器，它们全部都会同步。所以这实际上是一种动力系统形式：无论从各种不同相位的哪个起点出发，它总是能够达到同步。你可以设想一个稍复杂的版本，其中节拍器也许并非全部同步，可能有一半相互同步，另一半以相反模式或类似方式同步。但核心思想在于，这是一个纯粹凭借系统自身的固有内在连接，就能表现出特定行为的物理系统。

<details><summary>Original English</summary>
You can actually scale this up to hundreds of of metronomes on a physical system and they'll all synchronize. So this is actually a form of a dynamical system that goes through you know some starting point of all these different phases and always synchronizes. You can imagine a slightly more complicated version of this where maybe they don't all synchronize. Maybe half of them are synchronized with each other and other half are synchronized uh in an opposite pattern or something like this. But the idea is that this is a physical system that that kind of uh behaves the way it does just by by the the inherent interconnection of the system itself.
</details>

于是我们提出了一个问题：我们能否利用像节拍器系统这样的系统来进行计算？我们希望将其与生成式 AI 结合起来，这是我们真正关心的方向。为此我们发布了一个名为 UNO 的模型，实际论证了这一点。这是一个建立在一组类似振荡器之上的图像生成模型。我们对其进行了仿真并进行了开源，以便大家探索体验。这是首次证明我们确实可以扩展这类系统、对其进行训练，并实际获得像图像生成这样有用的输出。

<details><summary>Original English</summary>
Uh so we asked the question can we actually use such a system like like that metronome system to do computation. We want to connect that to generative AI that's what we really care about. So we released a model we called UNO which actually demonstrated this. It's an image generation model that's built on a set of oscillators like that. And uh we simulated it and made it open source so people can play with it. But this was a f the first demonstration that I can actually scale something up, train it and actually get useful output like image generation.
</details>

这是我们在那篇技术报告中提供的一部分分析。大家在这里看到的是我们所谓的“状态空间轨迹”，它基本上描述了系统随时间演化的情况。可以设想一下，如果将系统的状态表征为所有这些振荡器的全部相位，然后观察它随时间的变化过程，基本上就可以基于输出对其进行条件约束。你说我想要生成一架飞机、一辆汽车或一只鸟，它实际上就会经历不同的状态空间轨迹。所以我们在这里看到的正是对此的分析。这些则是它实际生成的图像。

<details><summary>Original English</summary>
And uh you know this is kind of some of the analysis that we uh we we provided in that uh in that write up. What you're seeing here is um we call this state space trajectory. It's basically how the system evolves in time. You can imagine if you characterize the state of the system as all the phases of those oscillators um and then look at how it evolves through time and you basically condition that on the output. You say I want to generate an airplane or a car or a bird. It'll actually go through different state space trajectories. And so that's what we're seeing here is just an analysis of this. And these are actual images that were generated by it.
</details>

### 稀疏性与规模扩展

事实证明，在过去的几个月里，我们实际上已经开始建立起许多基础科学层面的认知。我们还发现了让其运行得更好的其他机制。这就是我们所说的“稀疏性”概念。

<details><summary>Original English</summary>
Now it turns out we actually started to build a lot of that fundamental science up over the last couple of months. And we found other things that enable this to work even better. So this is a concept of what we call sparsity.
</details>

稀疏性的含义在于，比方说，如果我有一组元件，它们全都相互连接，就像左边展示的那样。如果有 10 个元件需要彼此全部相连，即 10 × 10 个元件，就会有 100 条连接。这还可以接受。但如果有一千个元件，那就是 1,000 × 1,000，变成了 100 万条连接。这种方式扩展性很差。我们称之为 n 的平方级（n squared）扩展。添加的元件越多，扩展的难度就会大幅增加，对吧？

<details><summary>Original English</summary>
Sparsity means that you know if I have uh let's say I have a bunch of elements all connect to each other like we have on the left hand side there. So you know if I have uh 10 elements I want to connect them all to each other. I have 10 * 10 elements. So I have a 100 connections. That's okay. But if I have a thousand now I have thousand* 1,000 which becomes a million. So this doesn't scale very well. We call this n squared scaling. So the more I add, it actually becomes way more hard to scale, right?
</details>

所以这种方式并不理想。而稀疏性使我们能够探讨：我是否可以丢弃其中的部分连接？如果我现在丢弃它们，是否还能挽救整个系统的行为表现？事实证明，你不仅能够

<details><summary>Original English</summary>
So that's not great. So sparsity allows us to actually say, well, can I throw away some of those connections? If I throw them away now, can I actually rescue the behavior of the whole system? And it turns out you can actually not only
</details>

<!-- chunk 3/4 -->

舍弃一部分连接，整个系统反而能获得更好的表现。它实际上变得更易于训练了。这背后有许多理论原因，但我们不仅在模拟系统中，而且在真实的物理系统中切实做到了这一点。因此，这属于那种极为罕见的情况：你得到了某种更高效、实际上更具可扩展性，甚至还能提供更高性能的东西。所以，这算得上是一个终极目标（holy grail）。这一直是个长期存在的难题，但我们必须以正确的方式界定问题，才能真正找到这个解决方案。因此，这其实是我第一次公开谈论这件事。我之所以想在这个场合讲，是因为我认为这确实是一件大事。

<details><summary>Original English</summary>
throw away some of the connections, but you can actually get better behavior out of the whole system. It actually becomes more trainable. Uh there's a lot of theoretical reasons for this, but we actually are able to do this in um in not only simulated systems, but actually real physical systems. So, it's one of these rare things where you get something that's more efficient, uh, that's actually more scalable and even gives you more performance. So, this is kind of a holy grail. It's been it's been a problem for a long time, but we had to frame the problem the right way to actually find this solution. And so, this is actually the first time I'm talking about this publicly. This is uh I wanted to do it at this venue because I think uh um it's a really big deal.
</details>

这是有史以来制造出的第一台物理动力学计算机（dynamical computer）。我们在5个月内完成了这项工作。这家公司——［掌声］

<details><summary>Original English</summary>
This is actually the first physical dynamical computer ever built. Uh, we did this in 5 months. This company started [applause]
</details>

谢谢。

<details><summary>Original English</summary>
Thank you.
</details>

在1月份正式启动。当时我们甚至连团队都没有，但我们说要制造出首个物理原型，并且要在今年完成。实际上，我们在6月——也就是6月1日——完成了设计流片（taped out the design），意思是送往晶圆厂制造。现在芯片已经回到了我们的实验室，并且我们确实拿到了测试结果。这就是由这类计算机有史以来生成的第一批图像。

<details><summary>Original English</summary>
started in earnest in January. We didn't even have a team, but we said we're going to build this first physical prototype and do it, you know, this year. And actually, we taped out the design, meaning we sent it to the fab uh in June on June 1st. The chip is back in our lab, and we actually have results from it. So, these are the first ever images generated from such a computer.
</details>

现在，这很好，很酷。但在图像之外，它还能做任何有用的事情吗？你实际上可以用它来执行任何类型的任务，比如序列建模或语言模型。但这里令人瞩目的是，生成每张图像只需大约500纳焦耳（nano [joules]）。为了直观对比，像GPU这样的普通计算机是在毫焦耳的量级。纳焦耳是10的负9次方。它非常非常小。所以它比标准计算机高效了许多个数量级，原因在于它根本不需要在各处搬运信息。这是证实其行之有效确凿证据。所以，这确实是我们第一次公开谈论它。所以，好的，谢谢大家。［掌声］

<details><summary>Original English</summary>
Now, great, cool. But does it do anything useful uh beyond just um uh images? you can actually do any kind of a task like sequence modeling or or language models. But the interesting thing here is it's only five 500 or so nano per image. So to put that in perspective a a normal computer like a GPU is on the order of millig. So nanog is 10 theus 9th. It's really really small. So it's many orders of magnitude more efficient than a standard computer and it's because it just doesn't move information around. This is proof positive this works. So this is literally the first time we're talking about it publicly. So um yeah, thank you. [applause]
</details>

### 物理动力学与4D计算

这里最酷的地方在于，这确实代表着某种新事物的诞生。计算机的发展历程是从CPU走向GPU，在计算和存储方面变得越来越并行，并且更加并行和细粒度。但所有这些都属于我们所说的冯·诺依曼架构。它们包含存储器和计算单元，信息在两者之间来回搬运。而我们构建的是所谓的动力学计算机，它实际上将计算和存储融为一体。我们没有存储接口。每一个单独的计算元件本身就是一个存储单元。因此，这是一种审视该问题的截然不同的方式。

<details><summary>Original English</summary>
So what's cool here is this is really the emergence of something new. So computers have gone from CPUs to GPUs going more and more parallel to compute and memory which is even more parallel and fine grain. Um but all of these are what we call vonoyman architecture. They have a memory and compute and we move information back and forth. What we built is what's called a dynamical computer which actually has compute and memory in one thing. We don't have a memory interface. Each individual computing element is a memory. So it's a completely different way to look at the problem.
</details>

因此我们称之为4D计算：在动力学过程中利用时间维度，并且实际利用裸片堆叠（die stacking）的物理三维空间，既将元件进行垂直放置，也以平面形式布局。我们在物理上拥有三个维度，同时在时间上拥有一个维度。所以这实际上是一种思考计算机的新方式，并且从效率的角度来看，它确实被证明是行之有效的。那么，如果我们制造出能效高出1000倍的东西，会带来什么影响？我认为这实际上非常酷。每瓦特所带来的智能（intelligence per watt）才是我们关心的核心。随着时间的推移，我们能否对此进行优化并使其变得更好？实际上存在一个绝无法超越的热力学极限。而哺乳动物的大脑——动物大脑——距离该极限大约在一到两个数量级以内。今天我们处于这张图表的最左端，距离那个热力学极限大约有100亿倍的差距——也就是1后面跟着10个0。我们认为在三年半的时间内，我们可以达到2D光刻技术的极限。而这家公司的终极目标是超越生物学。我们希望做出更好的东西，并在未来十年左右让算力无处不在，包括赋予新的机器人形态等事物以计算能力。

<details><summary>Original English</summary>
And so we call this 4D computing where we use the time dimension in the dynamics and we actually use the physical three dimensions of die stacking putting things vertically as well as in a in a planer form. So we have three dimensions from from the physical and we have one dimension in time. So this is actually kind of a new way of thinking about a computer and it it really is proving to work uh for efficiency sake. So now what are the implications if we build something that's a thousand times more power efficient? I think this is actually pretty cool. So intelligence per watt is what we care about. Can we optimize this and make it better over time? There is actually a thermodynamic limit which you can never exceed. And uh the mamillian brains though animal brains are somewhere within one or two orders of magnitude of that. Today we're on the far left of this graph and we're about 10 billion times away. That's 10 one with 10 zeros after it uh from that thermodynamic limit. We think in that three and a half years we can hit the the limits of 2D lithography. And the the overarching goal of this company is to beat biology. We want to make something better and enable you know compute everywhere including compute in new robotic um forms uh and things like this in the next uh decade or so.
</details>

我认为有趣的是，我们将看到计算形态发生转变，从拥有吉瓦级功耗的超大型数据中心，转向分布在各处的大量小型数据中心。我认为这是一件好事。它实际上让事物更加环保、更加本地化、更具适应性。

<details><summary>Original English</summary>
I think what'll be interesting is that we'll see the shift going from like big big data centers with gigawatts to many small data centers all over the place. I think this is a good thing. It actually makes things that are more environmentally friendly, more local, more adaptive.
</details>

正如我所说，我认为赋能构建数十亿个机器人，让它们以动态组合的方式来解决我们世界中的问题，是一件非常酷的事情。这将使我们能够思考更大的难题，并做出更多事情。

<details><summary>Original English</summary>
And as I said, I think enabling the ability to build billions of robots that kind of dynamically assemble to solve problems in our world is something that's I think is actually really cool. This is something that will enable us to think about bigger problems and do even more.
</details>

你们知道，我之前谈到过AI是一个万亿美元级的市场。那么，如果我们将其颠覆1000倍——存在一个被称为杰文斯悖论（Jevons paradox）的概念，即当你降低某种资产的基础成本时，你的实际消耗量会超过该资产成本下降的幅度。因此，如果你将某种东西的价格降低一半，你的消耗量会超过2倍。如果你将某种东西的价格降至千分之一，你的消耗量会远超其千分之一的幅度。我认为这将创造出人类有史以来见过的最大市场。

<details><summary>Original English</summary>
And you know, I talked about AI being a trillion dollar market. Well, if we disrupt it by a thousandx, it's there's a there's a concept called Jieven's paradox where when you drop the underlying um cost of an asset, you actually consume more more than the drop of that asset. So, if you make something half the price, you'll consume more than 2x. If you cons you make something 1,000th the price, you'll consume more than 1/ 1,000th of it. And uh I think this will create the largest market that humanity's ever seen.
</details>

### 现场对谈与技术落地

>> 我想说这极其出人意料。不得不说，这太令人惊叹了。

<details><summary>Original English</summary>
>> I mean that was extremely unexpected. I got to say that was pretty amazing.
</details>

>> 让我以每个人脑海中可能都在想的问题开始，那就是——

<details><summary>Original English</summary>
>> Let me let me start with actually probably the thing that's on everybody's mind which is
</details>

>> 鉴于这项技术确实有效，Nav，你之前大概也看到黄仁勋（Jensen）了。

<details><summary>Original English</summary>
>> to the extent that this works Nav and you probably saw Jensen earlier.
</details>

>> 围绕着你、在你的身旁，必须存在一个完整的人才与产业生态系统，不论是晶圆代工厂、封装厂等等。

<details><summary>Original English</summary>
>> There just needs to be an entire ecosystem of people that are beside you and around you whether it's the fabs packagers etc etc.
</details>

从这个早期版本——

<details><summary>Original English</summary>
What does it take to get from this early version
</details>

>> 走向某个能拿在人们手中、或者人们能用上的东西，需要付出什么？在时间和复杂度方面，你如何看待这条路径？它会是什么样的过程？

<details><summary>Original English</summary>
>> to something that sits in somebody's hand or that people use and how do you see that path in terms of time and complexity? What does that look like?
</details>

>> 是的，时间上我们在两年之内就能将其做成完整的产品。我是说——

<details><summary>Original English</summary>
>> Yeah, timewise we're within two years of of getting it to a full product. I mean
</details>

>> 那么这个产品是什么？

<details><summary>Original English</summary>
>> and what is the product?
</details>

>> 好的，

<details><summary>Original English</summary>
>> Yeah,
</details>

>> 它是一个运行在某处、由你们管理的虚拟机，然后——

<details><summary>Original English</summary>
>> it's a VM that sits somewhere that you guys manage and
</details>

>> 实际上我们正在打造一款面向数据中心的新产品，因此它是一个整机柜系统，对吧？

<details><summary>Original English</summary>
>> effectively we're we're building a new data center product for so it's a whole rack. as a system, right?
</details>

>> 它的核心构想基本上就是在上面运行那些模型。因此是通过网线输入Token、输出Token，但内部结构与现有的计算机截然不同。

<details><summary>Original English</summary>
>> And the idea is that basically we'll run those um uh models on it. And so tokens in, tokens out through a network cable, but the inner guts are completely different than an existing computer.
</details>

>> 那么你是否预期必须去支持现有的模型家族和现有架构？在这样一个世界里它能行得通吗——正如你所知，我们花了这么长时间，像“好吧，KV缓存”，大家都在做诸如此类的事情，这一切基于我们所依赖的这些抽象概念来看是如此机械化地还原，对吧？那么你预期我们其他人将如何转向这种架构？因为我的意思是，我认为大家都能看到那条能效曲线。我们都想要它。那么我们该如何利用它呢？

<details><summary>Original English</summary>
>> And do you expect that you'll have to move to support the existing model families and existing architectures? And will this work in a world where, you know, we've spent all of this time like, okay, KV cache and let's all like this all just so mechanically reductive based on, as you said, these abstractions that we've lived on, right? So how do you expect the rest of us to kind of move towards this? Because I mean I think you see that efficiency curve. We'd all want it. So how do we take advantage of it?
</details>

>> 是的。所以我认为，在某样东西有多好与为了转向它你愿意承受多少痛苦之间，存在一个权衡滑动标尺。你知道，我基本采取的策略是，让转向它的理由变得非常非常令人无法抗拒。要将内容移植过来确实需要做一些工作。实际上我们不是在算子层（operations layer）进行移植，你移植的是模型层。所以是的，现有的模型能够运行，但要实现这一转换需要相当数量的计算资源——

<details><summary>Original English</summary>
>> Yeah. So I think there's a there's a sliding scale between you know how much better something is and how much pain you'll you'll take to move to it. And you know I I basically took the the tack of like let's make it really really compelling to move. There is going to be some work to port things over. We actually don't port at the operations layer, you port the model layer. So yes, the existing models will work, but there's a fair bit of compute required to make that transition happen
</details>

>> 那么像矩阵乘法（matmul）这样非常基础的元件，它是否存在于你们的——它并不存在。它是——

<details><summary>Original English</summary>
>> and very basic elements like mapm does it is that exist in your it doesn't exist. It's
</details>

>> 我的意思是，你可以将其表征为矩阵乘法，但它并不是以矩阵乘法的方式去实现的。好的，

<details><summary>Original English</summary>
>> I mean you can you can characterize it as map but it doesn't implement it as maple. Okay,
</details>

>> 它是将其实现为一种随时间变化的行为。但对于其中的每一个时间步，你基本上都可以将其分析为当前状态矩阵乘以一个转移矩阵。

<details><summary>Original English</summary>
>> it implements it as a sort of time varying behavior. But each one of those time steps you can analyze as basically a matrix of the current state times a transition matrix.
</details>

>> 当你在组建这样一个团队时，这些人都是谁？他们是生物学家加上物理学家，再加上什么样的人？

<details><summary>Original English</summary>
>> And when you're building a team like this like who are these people? These are biologists plus physicists plus what are these people?
</details>

>> 是的。可以说是提出这些理论的理论家——动力系统理论（dynamical systems theory）已经存在100年了。是的。

<details><summary>Original English</summary>
>> Yes. Um like it's sort of like theorists that that come up with these uh uh like dynamical systems theory has been around for 100 years. Yeah.
</details>

>> 所以我们从那个领域招揽了人才，然后我们又招揽了真正造芯片的人，而他们彼此是不对话的。

<details><summary>Original English</summary>
>> So we got people from that world and then we got people who actually build chips and they don't talk to each other.
</details>

>> 他们彼此不对话。

<details><summary>Original English</summary>
>> They don't talk to each other.
</details>

>> 所以我们必须居中促成沟通。这实际上是关于这家公司最具挑战性的事情之一：我们拥有的跨领域人才跨度如此之大，以至于让他们协同一致并造出同一个东西，实际上相当困难。

<details><summary>Original English</summary>
>> So we had to facilitate that. That's actually one of the most challenging things about this company is the span of talents that we have is so big that getting them to kind of all coordinate and build one thing is actually pretty hard.
</details>

>> 那么，有什么类似于CUDA的对应物——如果可以打一个不太恰当的比方的话——能够让上面这些人和下面这些人进行交流？

<details><summary>Original English</summary>
Well, and what is this like CUDA like equivalent, if you will, just to use a bad analogy, that allows these people up here to talk to these people down there.
</details>

>> 是的。所以我们实际上构建了一套Python库。在Python中，

<details><summary>Original English</summary>
>> Yeah. So, we actually have built a set of libraries in Python. In Python,
</details>

>> 它是——它是Python。它不是——

<details><summary>Original English</summary>
>> it's it's Python. It's not
</details>

<!-- chunk 4/4 -->

CUDA，但呃，你知道，它在某种程度上是一种语言，允许你去表达那些具有随机行为的随时间变化的元素。

<details><summary>Original English</summary>
CUDA,
but
it's
uh
you
know,
it's
it's
a
language
of
sorts
that
allows
you
to
kind
of
express
time
varying
elements
that
have
stoastic
behavior.
</details>

>> 我是说，这令人难以置信地印象深刻。它太有雄心了。非常感谢你。很高兴见到你。很高兴见到你。太棒了。[音乐]

<details><summary>Original English</summary>
>> I
mean,
it's
incredibly
impressive.
It's
so
ambitious.
Thank
you
very
much.
It's
great
to
see
you.
Great
to
see you.
Amazing.
[music]
</details>