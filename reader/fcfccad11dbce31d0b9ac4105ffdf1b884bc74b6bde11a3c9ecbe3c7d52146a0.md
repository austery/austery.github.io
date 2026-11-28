---
author: Bloomberg Podcasts
date: '2026-05-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=7bWqp3oZyXg
speaker: Bloomberg Podcasts
tags:
  - wafer-scale-computing
  - ai-inference
  - semiconductor-manufacturing
  - compute-economics
  - hardware-acceleration
title: 巨型芯片的豪赌：Cerebras CEO 揭秘为何要制造“餐盘大小”的晶圆级处理器
summary: 本期访谈对话 Cerebras 创始人 Andrew Feldman，深入探讨了其独特的“晶圆级引擎”（WSE）架构如何通过物理规模解决 AI 推理中的存储瓶颈。Andrew 详细解释了巨型芯片在速度、能效及成本上的代际优势，并分析了推理市场的爆发、CUDA 护城河的消解、以及 AI 硬件行业在供应链和政治环境下的长期挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Andrew Feldman
companies_orgs:
  - Cerebras
  - Nvidia
  - TSMC
  - OpenAI
  - G42
  - AWS
products_models:
  - WSE-3
  - CS-3
  - CUDA
media_books:
  - Odd Lots
status: evergreen
---
### AI 心理症与芯片狂热

**Joe Weisenthal**: 欢迎收看新一期的 **OddLots** 播客。我是 **Joe Weisenthal**。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Hello and welcome to another episode of the OddLots podcast. I'm Joe Weisenthal.

</details>

**Tracy Alloway**: 我是 **Tracy Alloway**。Joe，我得说，不幸的是，我并没有所谓的“**AI 心理症**（AI psychosis）”。我很确定这一点。

<details>
<summary>Original English</summary>

**Tracy Alloway**: And I'm Tracy Alloway. Joe, I have to say unfortunately I don't have AI psychosis. I'm certain of that.

</details>

**Joe Weisenthal**: 这点还有待商榷。我很确定我没有 AI 心理症。但我不得不说，现在我有太多的时间都在思考 AI 相关的问题，感觉它们正在吞噬我脑海中的其他想法。无论是关于哪个模型最好、为什么最好，还是关于**推理**（inference）的经济学，或者是每个模型的**预训练**（pre-training）与**后训练**（post-training）比例是多少。这一切就像一个不断增长的肿块，占据了我越来越多的思绪。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Debatable. I'm pretty sure I don't have AI psychosis. I do have to say unfortunately like the amount of time now where it's like it feels like AI related questions and many of them are sort of like swallowing up the other thoughts that I have in my head. Whether it's questions about which model is best and why and what are the economics of inference and how much training is pre-training versus post-training for each model. All like it's just sort of like this blob that's growing that's taking up more and more of my thoughts.

</details>

**Tracy Alloway**: 你对 AI 心理症的定义是什么？因为有人可能会认为，字面意义上整天思考 AI 可能就是一种心理症的表现。

<details>
<summary>Original English</summary>

**Tracy Alloway**: What is your definition of AI psychosis? Cuz one would argue that maybe thinking about AI literally all the time would be a form of psychosis.

</details>

**Joe Weisenthal**: 这么说吧，我不是那种会把 AI 当成朋友的人。我没有爱上 AI 模型，也不认为通过与 **ChatGPT** 的协作，我能偶然发现物理学的统一理论之类。但是，你确实花了很多时间输入指令，按下按钮，然后观察结果。我只是想说，我很清楚我是在和机器对话，我们并没有建立什么伟大的突破，也不是什么合作者、伙伴或朋友。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Well, let's just say like I'm not the type who thinks that like I don't like think that the AI is a friend for one thing. [laughter] I'm not in love with the AI models. I don't think that in collaboration with chat GPT that I'm stumbling on a unified theory of physics and things like that. But you do spend a lot of time inputting instructions, pressing the button and seeing what comes out. I'm just saying I think I'm aware that I'm talking to a machine and that we're not establishing any great breakthroughs of which we are collaborators and partners and friends.

</details>

**Tracy Alloway**: 意识到自己有问题是康复的第一步。Joe，认真地说，有充分的理由去越来越多地思考 AI，因为不仅是市场，现实经济的一大块现在都在围绕 AI 运转。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Recognizing you have a problem is the first step towards healing. Joe, seriously though, there's a good reason to think about AI more and more, which is that a huge chunk of not just the market but the real economy is now revolving around AI. Right.

</details>

### Cerebras 的“餐盘”芯片

**Joe Weisenthal**: 没错。总之，在 AI 的讨论中有很多子类别。其中一个正是 **OddLots** 最喜欢的话题——**芯片**。当然，芯片以多种不同的方式被使用，它们处于 AI 供应链的不同环节，不同类型的芯片扮演着不同的角色。所以，我们需要了解更多。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Totally. So anyway, again, within the AI conversation, there are a lot of subcategories. One of the subcategories happens to be another OddLot's favorite topic which is chips. Of course, chips are used in multiple different ways. Chips are used in different parts of the AI supply chain. Different types of chips have different roles. And so, we have to learn more.

</details>

**Tracy Alloway**: 我们必须了解更多。我不得不说，我对我们即将访谈的这家公司特别感兴趣。部分原因是我对他们的两个了解：第一，他们刚刚完成了一次巨大的 **IPO**，筹集了大约 55 亿美元，估值倍数相当惊人。我甚至没法算市盈率，因为他们还没盈利。但仅从营收角度看，市销率大约是 67 倍，这非常火热。第二，他们制造**巨大的晶圆级芯片**。这是一个很有趣的画面。

<details>
<summary>Original English</summary>

**Tracy Alloway**: We have to learn more. And I have to say I'm particularly interested in the company we're about to speak to. Partly because the two things I know about them are number one, they just had a huge IPO, right? raising something like $5.5 billion at kind of insane multiple. I can't even do a price to earnings multiple because they're not profitable yet. But I think just on a sales basis, it was like 67 times forward earnings, which is pretty juicy, pretty hot. And the second thing I know about the company is they make giant wafers. Yes. Which is just a fun image to have [laughter] in your head.

</details>

**Joe Weisenthal**: 没错。如果你在想这个领域有一个热门的新入局者，他们的差异化竞争优势是什么？那么，关于他们的一点事实就是：他们的芯片非常巨大，大约有**餐盘那么大**。你可能会觉得自己是在读《洋葱新闻》的文章，但事实上这是真的，而且显然它确实具有一些实质性的技术优势。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: That's right. So if you were thinking it's like okay there is a hot entrant in this space what is their differentiator well one fact about them is their chips are just enormous about the size of the dinner plate one might think you're reading an onion article but in fact it's real and apparently it actually has some real technical advantages so

</details>

**Tracy Alloway**: 它的做法和大家都不一样。其他所有人都在做某种**模块化网络**，把一堆芯片组合在一起，连接起来。这就是你获得更多算力、内存和动力的方式。但这家公司做了一些不同的事情，采取了巨型晶圆的形式。

<details>
<summary>Original English</summary>

**Tracy Alloway**: And it's different to what everyone else is doing so everyone else is I guess doing this sort of like modular networking thing where you get together a bunch of chips and you connect them together and That's how you get more compute, more memory, more power basically. But this company has done something different in the form of the giant wafer.

</details>

**Joe Weisenthal**: 巨型晶圆。如果你想获得最大性能，你就想缩短组件之间的距离，那就把它们全部放在一个晶圆上。总之，我们将了解到更多信息。我非常激动地宣布，本期节目的嘉宾是 **Cerebras** 的创始人兼 CEO **Andrew Feldman**。Andrew，非常感谢你在 IPO 周来到我们的节目。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: The giant wafer. And if you figure that to get maximum performance, you sort of want to lessen the distance between things, then put it all on one wafer. Anyway, we're going to learn a lot more. I'm very excited to say about giant wafers and more. I'm very excited to say we do have the founder and CEO of Cerebras on the podcast, Andrew Feldman. Truly the perfect guest. So, Andrew, thank you so much for coming on the podcast on the week of your IPO.

</details>

**Andrew Feldman**: 非常感谢你们邀请我，深感荣幸。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Well, thank you so much for having me. What a pleasure.

</details>

### 为什么大芯片处理更快？

**Joe Weisenthal**: 咱们直接开始吧。那个巨大的芯片，它们显然是真的，像餐盘一样大。从技术角度看，为什么这种架构在 AI 的某些方面是更优越的形式？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Absolutely. Why don't you just start us off? The big giant chip, they're apparently real. They're as big as a dinner plate. What is the technical reason why this actually makes sense as a superior form of architecture for at least some aspect of AI?

</details>

**Andrew Feldman**: 我认为更大的芯片能在更短的时间内处理更多的信息。这会产生更快的反馈结果。事实上，所有人都在向更大的芯片迈进。**英伟达**（Nvidia）在过去五六年里，正是出于这个原因，将芯片面积从 400 平方毫米增加到了 800 平方毫米。而在计算行业，**晶圆级**（wafer scale）就是指建造这么大的芯片——（Andrew 举起了一块芯片）顺便跟听众说明一下，Andrew 现在正举着那块芯片。老实说，它看起来比餐盘还要大。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Well, I think larger chips process more information in less time. Okay. And that produces faster results. And everybody had gone to bigger chips. Nvidia had moved from 400 square millimeters to 800 square millimeters over the course of five or six years for this exact reason. And in the compute industry, wafer scale, which is building a chip, this big. For those who are, by the way, for those who are just listening, Andrew is now holding up the chip. And yes, it looks it actually looks bigger than a dinner plate to be honest.

</details>

**Andrew Feldman**: 这确实是一块大芯片。它的面积是此前任何芯片的 **58 倍**。这使我们能够使用一种不同类型的内存。内存主要有两种：一种是可以存储很多数据但速度很慢，另一种是每平方毫米存储不了多少数据但速度快得惊人。

<details>
<summary>Original English</summary>

**Andrew Feldman**: That's a big chip. Beautiful. I think it's 58 times larger than any other chip that had ever been. And what it did was it allowed us to use a different type of memory. Okay. A type of memory that there at the beginning there are two types of memory. There's memory that can store a lot but it's really slow. Okay. And there's memory that can't store very much per square millimeter but is blisteringly fast.

</details>

**Andrew Feldman**: 历史上，所有的 **GPU** 使用的都是那种存储量大但速度慢的内存。这就是它们推理速度如此之慢的原因。如果你现在使用 **Claude** 或者除 **ChatGPT** 以外的任何模型，你经常会感觉到，输入提示词后必须等待答案。这是因为内存速度慢，它们必须将海量信息从内存移动到计算核心。

<details>
<summary>Original English</summary>

**Andrew Feldman**: And historically all graphics processing units used this memory that could store a lot but was really slow. And that's the reason they do inference so slowly. So if you're using Claude right now or you're using anything but chat GPT, what you'll frequently feel is you'll enter your prompt and you'll wait for an answer. Right? And that's because the memory is slow and they have to move a ton of information from memory to compute.

</details>

**Andrew Feldman**: 通过晶圆级架构，我们可以使用这种**高速内存**（SRAM）。虽然我们无法增加它每平方毫米的存储容量，但我们可以增加平方毫米的数量。通过制造这种巨大的芯片，我们可以把它塞满高速内存。这就是为什么我们比最快的 GPU 快 15 倍的原因。这也是为什么在某些问题上，我们比 GPU 快 50 倍、100 倍甚至 1000 倍。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Now by going to wafer scale we could use this fast memory. Now we couldn't make that memory store more information per square millimeter but we could add square millimeters. And so by building this big chip we were able to stuff it to the gills with this fast memory. And that's why we're 15 times faster than the fastest GPU. That that's why on some problems we're 50, 100, even a thousand times faster than graphics processing units.

</details>

### 解决 75 年来的行业难题

**Tracy Alloway**: 等等，你能解释一下你们到底是怎么做到的吗？因为我知道此前有过尝试晶圆级芯片的努力，我记得甚至在 1980 年代就有过早期尝试。你们是怎么成功的？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Wait, can you explain how you actually manage to do this? Because I know there have been previous attempts to do wafer scale and I I seem to remember there was even like an early attempt in the 1980s or something to do it. How were you able to pull this off?

</details>

**Andrew Feldman**: 这是一个雄心勃勃的工程。在行业 75 年的历史中，每一次之前的尝试都失败了。包括位列行业“总统山”级别的 **Gene Amdahl**，他在 80 年代中期创办的一家叫 **Trilogy** 的公司就遭遇了惨败。不仅如此，在我们成功之后，一些参观过我们实验室的人试图模仿我们，也都失败了。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah, it was an ambitious undertaking, that's for sure. Every previous effort in the 75 year history of our industry had failed, including Gene Amdall, who who's sort of on the Mount Rushmore of compute in our industry. He failed sort of spectacularly in the mid 80s at a company called Trilogy. Not only that, but after we succeeded, people who had visited us, who'd been in our labs, tried to copy us, and they also failed.

</details>

**Andrew Feldman**: 我们所做的是解决了一系列根本性的问题。这些问题跨越了广泛的技术领域。首先是**光刻**（lithography），我们必须与 **TSMC**（台积电）紧密合作，事实证明他们是非常棒的伙伴。我们必须在**材料和封装**上进行发明，解决如何将处理器和硅片放置在主板上并交付电力和 IO 的问题。我们必须发明**供电**方式。当你建造一个巨型芯片时，你交付的电力要比邮票大小的芯片多得多。我们还必须发明**冷却**方法，编写运行在上面的新型软件。所有这些此前都没人做过。

<details>
<summary>Original English</summary>

**Andrew Feldman**: And so what we were able to do is solve a set of really fundamental problems. And those problems cut across a wide swath of technology. They cut across lithography. So we had to collaborate closely with TSMC. And they turned out to be a great partner. We had to make inventions in material and packaging. That's how you put a processor, how you put a piece of silicon on a motherboard, deliver power and IO to it. We had to make inventions in power delivery, right? When you build a giant chip, you're going to deliver way more power to it than if you do a chip the size of a postage stamp. We had to invent ways to cool it. We had to write new types of software that ran on it. All of these had never been done before. And it was a decade long process.

</details>

**Andrew Feldman**: 我们花了 5 年时间和大约 5 亿美元才交付了第一块芯片。从那以后，发展非常迅猛。去年 12 月，我们与 **OpenAI** 签下了一份超过 **200 亿美元**的合同，这是硅谷历史上最大的合同之一。今年 3 月，我们与 **AWS** 签署了协议，他们将在其数据中心部署我们的系统。这是一个非凡的历程，但耗时很久，需要极高的工程水平。在很长一段时间里，我们都不确定是否能做成。

<details>
<summary>Original English</summary>

**Andrew Feldman**: It took us five years and about $500 million to deliver the first one. And it's been an extraordinary run since. In December, we signed a deal with OpenAI north of $20 billion, one of the largest contracts ever signed in Silicon Valley. And then in March, we signed a deal with with AWS where they would deploy our systems in their data centers, in their AWS data centers. And so, it's just been an extraordinary run, but it took a long time. Yeah, it took extraordinary engineering and there were certainly long periods of time when it wasn't clear we were going to make this work.

</details>

### 推理 vs 训练：AI 的下半场

**Joe Weisenthal**: 显然你们已经达到了这个显著的里程碑，完成了 IPO，市场对你们公司的估值约为 640 亿美元。为了让听众理解，这些芯片是专门用于**推理**，还是也用于**训练**？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Obviously, you've hit this remarkable milestone. You have in fact IPOed and so forth and right now markets valuing your company at 64 billion dollar early days of the IPO. Just for the listener to understand the chips are are they solely an inference as opposed to you know in training. When we think about AI, I think about okay, there's training, training the model, and then answer giving. That's the inference. Are the chips for just for inference?

</details>

**Andrew Feldman**: 你的框架非常准确。**训练**（Training）是我们如何“制造” AI，而**推理**（Inference）是我们如何“使用” AI。在 2025 年上半年，我们制造的模型已经足够聪明到变得有用，于是使用量出现了爆炸式增长。我们通过推理来使用 AI，所以出现了一股巨大的推理需求浪潮，这种趋势在 2026 年仍在继续，并将持续多年。

<details>
<summary>Original English</summary>

**Andrew Feldman**: So, a couple things I think you framed it exactly right. Training is how we make AI, and inference is how we use AI. And so, what happened was that in sort of 2025, in the first part of 2025, the models we made were smart enough to be useful. Yeah. And there was an explosion of use. and we use AI by doing inference. So there was this sort of tidal wave of demand on inference and that has continued in 2026 and we think it will continue for for years and years to come.

</details>

**Andrew Feldman**: 当我们在 2015 年开始构思这家公司时，我们预见到 AI 就在地平线上，它将吞噬海量的计算资源。我们当时做了两个基本赌注：第一，它需要**专用硅片**。正如图形处理需要专用芯片产生了 GPU，移动计算需要专用芯片产生了 ARM 处理器。第二，我们打赌修改 GPU 架构是不对的，你需要从一张白纸开始。

<details>
<summary>Original English</summary>

**Andrew Feldman**: And so that that's the what had happened in 2015 when we began thinking about the company. We knew that AI was on the horizon and it would eat a huge amount of compute, right? And we we made sort of two fundamental bets. We bet that it would need dedicated silicon and right graphics had needed dedicated silicon. That's how you got the graphics processing unit. Mobile compute had needed dedicated compute. That's where you got ARM processors. We made that bet. And we made a bet that modifying the GPU architecture wouldn't be right. You needed to start with a clean sheet of paper.

</details>

**Andrew Feldman**: 所以我们从一个新的愿景开始。这个愿景既能做训练，也能做推理，而且速度都快了几个数量级。但目前我们看到推理需求的爆发非常猛烈，以至于虽然我们在训练上同样比 GPU 快得多，但大量的业务目前都体现在了推理上。

<details>
<summary>Original English</summary>

**Andrew Feldman**: And so what we started with was a new vision. And that vision could do training and it could do inference. And it was orders of magnitude faster at both. But right now what we're seeing is such an explosion in demand for inference that a lot of the business has met as inference even though we're just as fast at, you know, the same amount faster than than GPUs on training.

</details>

### 速度在 Agent 时代的重要性

**Joe Weisenthal**: 很有趣。稍后我们再谈训练市场。先说推理。科技博主 **Ben Thompson** 在文章中区分了“**解答型推理**（answer inference）”和“**Agent 型推理**（agentic inference）”。前者是格式化简历或写论文，后者是 AI 作为一个 Agent 去执行任务。你是否认同这种划分？你的芯片能两者兼顾吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: That's interesting. Maybe we'll get more to the theoretical training market a little later. Just real quick on inference. Ben Thompson who writes a newsletter about tech he wrote a piece in which he distinguishes between answer inference and agentic inference. So answer inference is like you know format my resume or whatever or write me an essay on X or Y or answer some questions and then aentic inference is like okay here's this thing that's going to go around. Do you distinguish and do services for you? Not producing visual answers. Do you distinguish between those two? Is that a real divide in your view? And can your chips do both?

</details>

**Andrew Feldman**: 我们的芯片能兼顾两者。我认为这种划分是存在的，但**速度在两者中同样重要**。如果你正在与 AI 交互，比如写代码，这就属于 Agent 型，没有人愿意等待。试问，“慢速搜索”的市场有多大？零。“拨号上网”的市场有多大？零。为什么？因为没人想等待。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Our chips can do both. I think it is a divide. Okay. I think speed matters equally in both. Okay. I think if you are engaged with the AI, if you're writing code, which is agentic, if you're writing code or you're doing work, nobody wants to wait. I mean, we could just turn the question around and say, well, how big is the market for slow search? Zero. How big is the market for dialup internet? Zero. Why is that? Because nobody wants to wait, right?

</details>

**Andrew Feldman**: 所以，如果你是在与 AI 互动，速度是本质要求。如果 AI 在做 Agent 工作，而你的竞争对手在 20 分钟内完成的工作量是你的 3 倍、5 倍甚至 10 倍，你就会被彻底击败。Ben Thompson 认为速度在 Agent 流程中不重要的观点是完全错误的。**速度在生产性工作的所有方面都至关重要。**在更短的时间内完成更多工作的能力是一种随时间积累的基础优势。当你的对手完成一份工作时，你能完成三份，下一次你能完成六份，长期来看你会在任何领域击败他们。

<details>
<summary>Original English</summary>

**Andrew Feldman**: So, if you're engaged with the AI, speed is of the essence. But if the AI is doing agentic work and your competitor gets three times, five times, 10 times as much work done in 20 minutes than you do, you're going to get smoked. And so this notion somehow that Ben proposed that speed isn't very important in agentic flows is dead wrong. That speed is important in all aspects of productive work. And that your ability to get more done in less time is a fundamental advantage that that acrru over time. Right? If while your competitor is doing one unit of work, you can do three and in the next time they do one unit of work, you do six. Right? This adds up over time and you beat them in any line of work. And so speed, which is sort of our specialty, is is important across the board.

</details>

### Token 经济学：速度的溢价

**Tracy Alloway**: 巨型晶圆和速度对于 **Token** 的经济学意味着什么？我脑海中有一个画面：我去超市买牙膏，我可以零买一支，也可以去 Costco 批发一大盒，单价更便宜。我就是这么看巨型晶圆的。速度对 Token 成本意味着什么？

<details>
<summary>Original English</summary>

**Tracy Alloway**: What do giant wafers and speed in general actually mean for I guess the economics of tokens? Because one way I think about it, I have this sort of vision in my head like, okay, if I'm out shopping for toothpaste, I know I need toothpaste every once in a while and I go into like a CVS, a store, I get one thing of toothpaste and then maybe a week later I get some more toothpaste. Or I could go to Costco and buy a giant thing of toothpaste and take it home probably at a cheaper cost. And that's sort of how I think of the giant wafers. Maybe it's a bad analogy, but what does speed actually mean for the cost of tokens?

</details>

**Andrew Feldman**: 我有几点观察。目前人们选择为速度支付一定的**溢价**。例如，**Anthropic** 提供了一种高级服务，Token 生成速度快两倍，但收费高六倍，即便如此也供不应求。而我们的速度比他们快 15 倍。人们看重速度是因为它能提高生产力。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Well, I I think there are a couple observations. I I think people have chosen so far to price speed a little higher. For example, Anthropic offered a premium service in which they offered tokens twice as fast and charged six times as much and they sold it out and they couldn't meet the demand. Now, just to give you an idea, we're 15 times faster than they're twice as fast. And so, people value speed because it allows them to do more work and they value their time. And when you can do more work in less time, you are making people more productive. That's why people have chosen to price them at a premium.

</details>

**Andrew Feldman**: 实际上，快速 Token 的制造成本并不更高。英伟达的 GPU 架构非常出色，在生成“慢速 Token”时极其高效且成本极低。但 GPU 有一个特性：当你试图让它跑得更快时，每个 Token 的成本和功耗会大幅增加。这就像你开车，速度越快，油耗越高。

<details>
<summary>Original English</summary>

**Andrew Feldman**: They don't cost more to make. In fact, in the GPU architecture is an extremely good architecture and extremely efficient at building very slow tokens. And if you don't mind slow, the cost per token on a GPU is extremely low. But the GPU has a characteristic that as you try and go faster, the cost and the power used per token increase. Sort of like as you go faster in your car, your miles per gallon decrease, right?

</details>

**Andrew Feldman**: 所以，当你试图达到“有用”的速度，快到足以让用户的注意力集中在产品上时，GPU 会变得极其昂贵和耗能。而我们可以让快速 Token 的成本远低于 GPU，且功耗极低。

<details>
<summary>Original English</summary>

**Andrew Feldman**: So what happens is as you try and get fast enough to be useful, fast enough to be interesting, fast enough to keep users intelligence focused on this product, they become extremely expensive and extremely power- hungry. And so the question is is not just what people are paying for a token, what people are choosing to price them at, but what they actually cost to make. And GPUs make very slow tokens very cheaply. And they're unbelievably expensive at fast tokens. We make fast tokens vastly less expensive than than GPUs. And we use a tiny fraction of the power.

</details>

### 供应链与数据中心的瓶颈

**Joe Weisenthal**: 假设这一套说辞大家都信了。那么在接下来几年里，你们的推理市场份额在多大程度上取决于能否获得 **TSMC** 的产能？这是否是增长的限制机制？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Let's say we stipulate that this is all true and everyone wants the fastest and everyone's like you know what this is the solution that the Sarah bras technology one big chip this is really where it's at. How much of like your market share for the inference market when you look out next year, the year after etc. How much is your market share going to be dictated by your ability to get capacity at TSMC fabs? How much is that a gating mechanism for growth?

</details>

**Andrew Feldman**: TSMC 是供应链中极其重要的一部分。但我们有一些真正的优势。目前限制厂商建造 AI 算力的领域主要有三个：第一是 **HBM 内存**，由于只有三星、海力士和美光三家生产，供应压力极大，成本极高。我们**不需要使用它**。第二是 TSMC 内部一种叫 **CoWoS** 的封装工艺，英伟达和其他 GPU 必须使用它。我们**不需要使用它**。第三是 TSMC 压力最大的 **3 纳米**工厂，我们使用的是 **5 纳米**工艺。

<details>
<summary>Original English</summary>

**Andrew Feldman**: You know, TSMC is is a huge part of the supply chain. Yeah. But we have some real advantages. There are three areas right now that are limiting vendors in building AI compute. Number one is HBM memory is this memory we described earlier that can store a lot but it's really slow that's made by three companies approximately Samsung high nix and micron and it's under unbelievable supply pressure it's extremely difficult to get there are very long lead times it's unbelievably expensive right now we don't use it the second part that's limiting is a process inside of TSMC called co-ass And this is the process that that Nvidia and other GPUs use. We don't use it. The third thing is that at TSMC the factory that is under most pressure is their 3 nanometer factory. We don't use it. We use 5 nanometer.

</details>

**Andrew Feldman**: 我们成功绕过了一些最紧迫的供应限制。目前整个行业的限制因素其实是**数据中心**，或者说是通电的建筑物。这真是巨大的讽刺：你发明了 75 年来没人能造出的技术，写出了卓越的软件，造出了远快于对手的产品，结果大家都被房地产和电力给困住了。这种局面在未来 15 到 18 个月内不会改变。

<details>
<summary>Original English</summary>

**Andrew Feldman**: So we have managed to avoid some of the the most binding supply constraints. Now TSMC still has to give us a meaningful allocation and they've been an extraordinary partner from the get-go and they are the greatest manufacturing company on earth by far. But I I think today TSMC has given us as many wafers as we've needed. Business today is constrained by data centers. And that's the grand irony, right? You invent technology that has been unbuildable, never been invented for 75 years in the history of compute. You write software that is extraordinary. You built a product that is vastly faster than the incumbent. And what are we all constrained by? Buildings, right? Data centers right now are are everybody's constraint in the entire industry. Powered buildings. So, real estate, it is an amazing thing right now. And that that is true sort of across the board.

</details>

### 开源模型与“智商成本”

**Joe Weisenthal**: 除了制造芯片，你们还有自己的云服务，用户可以访问各种**开源模型**。在传统软件中，开源意味着免费。但在 AI 领域，没有所谓的免费，因为即便软件免费，你还得支付芯片折旧和电力。作为云供应商，开源模型在“单位智力成本”上是否更便宜？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So in addition to manufacturing these chips, you actually I I didn't realize this, you have your own cloud. We do and or you have your own cloud services which I have a bunch of questions about that. You have your own cloud services through which a user can actually get access to various open source models and so forth. What I am something I'm curious about and maybe you can speak to this you know in traditional software opensource one nice thing about open source is you don't have to pay for it. So it's free. It's a little bit different when we're talking about there's no really such thing as like free AI software because even if it's like free, you still have to like pay for the depreciation of the chips and you have to pay for the electricity to run them. So there's no real such thing as like free open- source AI software. But what I am curious about in your experience as a cloud vendor are the open-source models cheaper on a per unit of intelligence basis if we had some way of saying levelized cost of intelligence which I don't know if the industry has yet. Are open source models cheaper per IQ point whatever we want however we want to measure intelligence.

</details>

**Andrew Feldman**: 是的，便宜得多。在闭源世界，你为那最后一点点额外的智力支付了高昂的代价。目前的开源模型虽然还不如最顶尖的闭源模型，差距大约在 3% 到 5% 左右，但使用成本极低。你不需要支付训练成本。目前市场上正在进行一场开源与闭源的决战。闭源确实稍微强一点，但也贵得多。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yes by a lot. Really? Yeah. I I think in the closed source world, you're paying a lot for that extra little bit of intelligence, right? The open source models, there are no open source models that are as good as the closed source models. Okay? Think of it as 3 4% 5% different. Okay? Something in that range. And it could be a little more, could be a little less, but the cost to you using them. Yeah. Right. What you're not paying for was the cost to train it, right? And that's a battle that is underway in the market. What is clear is that the closed source is is strictly better by a little bit. By how much varies and it's more expensive.

</details>

### CUDA 还是护城河吗？

**Tracy Alloway**: 谈到英伟达，人们常说他们真正的护城河是 **CUDA** 软件栈。作为挑战者，你如何看待这种软件生态的捆绑？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Um, since we're on the topic of software, one of the things you often hear when talking about, you know, new chip entrance going up against Nvidia is this idea that, well, you know, like Nvidia chips, they're great and all, but the real moat of Nvidia's business is CUDA, right? The software stack that goes with it. What's your take on that?

</details>

**Andrew Feldman**: 英伟达可能是本世纪前 25 年最伟大的公司。CUDA 在创造 AI 版图的过程中非常重要。**但现在它不再重要了，在推理领域它根本没有地位。**如果你想把模型从 GPU 迁移到我们的芯片，只需 10 次按键，指向我们的 API 即可。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Nvidia is probably the greatest company in the first part of the this century, right? You know, Jensen's one of the great CEOs of of our era. Just extraordinary and CUDA was really important in the creating of the AI landscape. But it's not important now and it has no role whatsoever in inference. If you want to move from running a model on GPUs today to running it on us, we can move it in 10 keystrokes. Just move point to our API.

</details>

**Andrew Feldman**: 此外，一年前几乎所有的前沿实验室模型都建立在 CUDA 基础上，而今天，三大前沿模型中的两个已经不是了。**Google 的 Gemini** 是在 TPU 上训练和服务的；**Anthropic 的模型**是在 Trainium 和 TPU 上训练服务的。只有 **GPT** 还在使用 GPU/CUDA 环境。CUDA 的统治地位正在大幅缩减，在推理领域已无关紧要。

<details>
<summary>Original English</summary>

**Andrew Feldman**: So that's the first part. The second part is that a year ago, every major Frontier Lab model had been built on a CUDA foundation and today two of three haven't. So they lost 70% market share. There are three leading frontier models, Gemini, Claude and GPT. Gemini built by Google on TPUs, trained on TPUs, served on TPUs. No CUDA. anthropics models trained on tranium, no CUDA, served on TPUs, on trainium and on GPUs and OpenAI's GPT trained on GPUs in the CUDA environment. So two of the three leading models today use no CUDA. That's a hemorrhaging a share.

</details>

### 政治、出口管制与 IPO

**Tracy Alloway**: 你们本周 IPO 了。我注意到你们的很大一部分收入来自阿布扎比的 **G42**，他们既是最大客户也是主要投资者。此外，你们去年的融资轮中出现了 **1789 Capital**，这是一家与小唐纳德·特朗普有关的投资公司。作为一个愤世嫉俗的人，我好奇这是否让你们更容易通过关于 G42 的国家安全审查？

<details>
<summary>Original English</summary>

**Tracy Alloway**: So, you IPOed this week. I was looking through the IPO filing and looking at some of the actual numbers in there and I know you have the Open AI deal now, but a huge chunk of your revenue comes from this company called G42 in Abu Dhabi and I think they're both like your biggest customer and also a major investor. And then but also last September you got an uh one of the your I looks like G round participants in the G round investor was 1789 Capital which is of course the firm assoc that's associated with Donald Trump Jr. I wonder if the participation if uh Donald Trump Jr.'s investment in your company made it easier to get the green light from these national security concerns to do an IPO.

</details>

**Andrew Feldman**: 我希望事情有那么简单，但事实并非如此。我们在 2025 年 3 月就解决了所有的 **CFIUS** 问题，那是在接受 1789 的投资之前。我们接受他们的资金是因为他们是一家周到的风投公司。我们不认为政治观点只有一种。我们从不寻求，也不会寻求政治准入或这类事情。

<details>
<summary>Original English</summary>

**Andrew Feldman**: I wish it were that easy. No, it had no no role at all. We resolved all CPHAS issues in March of 2025. I believe that was before we took money from from 1789. Moreover, I I I wouldn't ask that. That's not who I am and that's not the way we roll. So, we took money because they are a a thoughtful venture firm. And we we don't believe that that there's only one point of political view. We have never asked nor will we ever ask for political access or anything of the kind.

</details>

**Joe Weisenthal**: 一天之内变成亿万富翁是什么感觉？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: What's it like to become a billionaire in a single day?

</details>

**Andrew Feldman**: 老实说，对我来说没什么特别的。担任科技公司的 CEO 是一条非常辛苦的致富之路。你必须热爱这项工作，热爱团队。相比我个人财富的变化，更让我自豪的是，**我们造就了 800 多位百万富翁**。在我的上一家公司，我们造就了 100 位百万富翁。这才是让你每天醒来都觉得自己很有价值的事情。

<details>
<summary>Original English</summary>

**Andrew Feldman**: No, I I I think the honest truth is it was a big nothing for me. I was had some wealth before and have some wealth after. I I think this is a very difficult way to make money, right? Being a tech CEO. I think what you have to do is you have to love the work, you have to love the people, and you have to think every day about how to make your team rich. And far more important than than sort of some change in my wealth was we made more than 800 millionaires. And that's something I'm proud of every minute of every day.

</details>

### 尾声：给硅片注入生命

**Tracy Alloway**: 你提到了“**为一块硅片注入生命**”。我父亲是一名物理学家，他总是喜欢指出，碳和硅在周期表上是相邻的。这也许暗示了什么。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yeah. You mentioned breathing life into a chunk of silicon. My dad, who's a physicist, always likes to point out how um carbon and silicon are right next to each other on the periodic table. Maybe there's something deep in that.

</details>

**Andrew Feldman**: 你父亲说得非常有深度。虽然我们盯着周期表看了很久，但没人跟我提过这点。我们要创造人工生命，就需要硅。**碳是所有生物生命的基石，而人工生命——至少是智能部分——将建立在硅之上。**

<details>
<summary>Original English</summary>

**Andrew Feldman**: I I think that's a really thoughtful thing your father said. And I I I I think that's really cool. And uh nobody pointed that out to me though we've stared at periodic tables for a long time. But I I think to the extent we can make artificial life, we need silicon. Yeah. And they're right next to each other, right? Carbon carbon's the heart of all other life and artificial life will be founded at least the intelligent part will be founded on silicon.

</details>

**Joe Weisenthal**: 硅的下面是锗，也许那是下一个。Andrew，非常感谢你来到 OddLots。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Right below silicon is Germanmanium. Maybe the next I don't know. Well, let's ask your dad. Andrew, thank you so much for coming on OddLots.

</details>