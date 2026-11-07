---
author: The MAD Podcast with Matt Turck
date: '2026-07-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UEOSUSz--Ig
speaker: The MAD Podcast with Matt Turck
tags:
  - chip-architecture
  - inference-speed
  - supply-chain
  - model-deployment
title: 芯片与人工智能速度的崛起：从大芯片到推理效率的革命
summary: 文章探讨了在AI领域，超大规模芯片对提升信息处理速度的重要性。核心观点包括：随着AI从新奇事物转变为生产力工具，推理速度（以每秒处理Token数衡量）成为关键指标；以及芯片设计理念从“一颗芯片包揽一切”向针对特定工作负载的专业化演变趋势，并分析了在快速增长背景下供应链多元化的挑战与应对策略。
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

### 芯片与AI速度的崛起

**Andrew Feldman**: 这是计算机工业史上制造的最大的芯片。它比GPU大58倍。对于AI而言，更大的芯片处理信息的速度更快，因此你可以用更少的时间得到答案。在AI领域，大芯片无疑是最好的选择。在推理领域没有护城河。在云端从GPU迁移到我们这里只需要八次按键。我们解决了一个计算机史上前所未有且无人能解的问题。我们在2020年就交付了，但当时无人问津。没人在乎。没人买它，也没人在乎。大家都说我们疯了。说这根本行不通。于是我们接着制造了下一代。

<details>
<summary>Original English</summary>

**Andrew Feldman**: This is the largest chip built in the history of the computer industry. It's 58 times larger than a GPU. And for AI, bigger chips process information more quickly and therefore you get answers in less time. For AI world, big chips are undoubtedly the best way to go. There's no mode in inference. It takes you eight keystrokes to move from a GPU to us in the cloud. We solved a problem that nobody in the history of computed solved. And we delivered it in 2020 and nobody cared. Nobody cared. Nobody bought it and nobody cared. Everybody said we were crazy. It would never work. So then we built the next one.
</details>

**Matt**: 大家好，我是Matt。欢迎来到Matt播客。我今天的嘉宾是Andrew Feldman，他是Cerebras公司的联合创始人兼CEO。这家公司制造了计算史上最大的芯片，并且刚刚完成了有史以来规模最大的半导体IPO。Andrew频繁出现在各大新闻头条中：与OpenAI价值超过200亿美元的交易、以及IPO。但这次对话有些不同。我们将从“什么是晶圆”开始，一步步深入探讨。为什么GPU在快速推理方面会遇到瓶颈？三个鲜为人知的短缺问题是什么？那段无人问津其芯片的“荒野十年”经历了什么？以及为什么Andrew认为CUDA不再是Nvidia的护城河。如果你想真正了解当前的芯片行业格局，以及AI推理在芯片底层是如何运作的，这一期节目就是为你准备的。请尽情享受这场与Andrew Feldman的精彩对话吧。

<details>
<summary>Original English</summary>

**Matt**: Hi, I'm Matt. Welcome to the Matt podcast. My guest today is Andrew Feldman, co-founder and CEO of Cereubbras, the company that built the largest chip in the history of computing and just pulled off the biggest semiconductor IPO of all time. Andrew has been everywhere talking about the headlines. the $20 billion plus OpenAI deal, the IPO. But this conversation is a bit different. We started from what is a wafer and built up step by step. Why GPUs struggle with fast inference, the three shortages nobody talks about, the decade in the desert when nobody wanted his chip, and why Andrew believes that CUDA is no longer a mode for Nvidia. If you want to actually understand the current chip landscape and how AI inference works at the silicon level, this episode is for you. Please enjoy this fantastic conversation with Andrew Feldman.
</details>

**Matt**: 我觉得一个有趣的切入点是谈谈“速度”。那么，速度是否已经成为当今AI领域最核心的话题？

<details>
<summary>Original English</summary>

**Matt**: I thought a fun place to start uh would be to talk about speed. So has speed become the dominant conversation for AI today.
</details>

**Andrew Feldman**: 是的。我认为发生的事情是，很长一段时间以来，AI都算是一种新奇事物，对吧？它就像一个客厅戏法。很酷，但不实用。而到了2025年年中左右，AI变得足够聪明了，以至于人们开始使用它。我们要记住，我们通过训练来创造AI，但我们通过推理来使用它。突然之间人们想要使用它，而一旦你想使用它，一旦它开始产生生产力，速度就很关键了，对吧？快速生成的token更具生产力，所以人们讨论的焦点从其他所有事情转移到了：我们如何让推理变得更快？我们如何更快速地交付token，因为这些是更具生产力的token？我们在更短的时间内完成了更多的事情，因此它的价值更高。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah. What happened I think was uh for a long time AI was sort of a novelty, right? It was like a parlor trick. It was cool but not useful. And what happened somewhere around the middle of 2025 was the AI got smart enough such that people began to use it and we remember we we we make AI with training but we use it with inference and suddenly people wanted to use it and the minute you want to use it the minute it's productive right speed matters right fast tokens are more productive and so the conversation moved from everything else to How do we make our inference faster? H how do we deliver tokens more quickly because those are more productive tokens? We get more done in less time and therefore it's more valuable.
</details>

**Matt**: 很好。那速度究竟意味着什么？是衡量token速度的等式吗？是完成任务的时间吗？正确的衡量指标是什么？

<details>
<summary>Original English</summary>

**Matt**: Great. And what does speed mean? Is that uh is that an equation of token speed? Is that completion of the task? What's the right metric?
</details>

**Andrew Feldman**: 正确的指标是每个用户每秒处理的token数。这就是你从回复中的第一个token一直到最后一个token的速度。这对于聊天查询是如此，对于代理工作负载也是如此，对吧？如果它们是多轮循环的，等待时间会被放大。所以你想要的是快如闪电的响应速度，这样AI让人感觉是实时的，你才能与它进行互动。

<details>
<summary>Original English</summary>

**Andrew Feldman**: So the right metric is tokens per second per user. that that's how fast you get the first token all the way through the last token in in your uh in your response. And it's true for queries from from the chat, but it's also true for for agentics loads, right? Uh if they're sort of multicycle turns, waiting is amplified. And so what you want is blisteringly fast responses so that the the AI feels like it's in real time. You can engage with this.
</details>

**Matt**: 所以这是AI的“宽带时刻”。

<details>
<summary>Original English</summary>

**Matt**: So it's the brain moment for AI.
</details>

**Andrew Feldman**: 我想是的。我认为这是一个非常好的比喻。你可以想想Netflix，对吧，当互联网速度很慢的时候，Netflix通过信封寄送DVD。你会在信封里收到一张DVD。而当互联网变快时，他们并没有变得在寄送信封和DVD上更高效，而是成为了一家电影制片厂，对吧？速度使他们能够转变成完全不同的事物。这就是速度在总体上所能做到的，尤其是在AI领域。它打开了一个全新的领域。它允许你以不同的方式使用AI。你会停留更长的时间。你会更频繁地使用，并处理更难的问题。

<details>
<summary>Original English</summary>

**Andrew Feldman**: I think I think that's right. And I I think that's a very good analogy. I I think if you think of something like like Netflix, right, when the internet was slow, right, Netflix delivered DVDs and envelopes. you would get a a DVD in an envelope and and when the internet became fast, they didn't get more efficient at delivering DVDs and envelopes. They became a movie studio, right? The speed enabled them to become something completely different. And that's what speed does uh in general and in particular for for AI. It it opens up a whole new domain. It allows you to use the AI differently. You will stay longer. you you will come more often and you work on harder problems.
</details>

**Matt**: 是的。所以这实际上是一个关于用户体验（UX）的问题，对吧？就是没人愿意等上几秒钟。

<details>
<summary>Original English</summary>

**Matt**: Yep. So it's literally a question of of the UX, right? That's just nobody wants to wait a few seconds.
</details>

**Andrew Feldman**: 说得好。我的意思是，慢速搜索的市场有多大？拨号上网的市场有多大？零。对于一个网站加载，你愿意等多久？你会等8秒吗？没有人会等。对吧？所以对于AI来说情况完全一样。

<details>
<summary>Original English</summary>

**Andrew Feldman**: That's great. I mean, how big is the market for slow search? How big is the market for dialup is zero. How big is how long will you wait for a website to resolve? Will you wait 8 seconds? Nobody waits. See? And so it's the exact same with AI.
</details>

**Matt**: 是的。所以不会再有人开着笔记本电脑在一旁干等着代理去——

<details>
<summary>Original English</summary>

**Matt**: Yep. So no more people waiting with their laptops open uh while the agent
</details>

**Andrew Feldman**: 没错。如果它一直在运行、运行、运行。我认为这不是人们想要的。

<details>
<summary>Original English</summary>

**Andrew Feldman**: That's right. Well, it's running and running and running. I I I think that is not what what people want.
</details>

### AI芯片行业的现状与演变

**Matt**: 好的，太棒了。那么，我很想谈谈目前芯片行业的格局，帮助大家形象地了解你们公司现在所处的位置以及正在进行的艰巨工作。过去，基本上有一种“一颗芯片包揽一切”的概念，但很明显，这种情况正在发生急剧的变化。你们有Grock，还有GPU，人们听说过Trainium，也听说过TPU。所以请帮助我们比较和对比一下，谁主要是为了解决什么问题？

<details>
<summary>Original English</summary>

**Matt**: Okay. Great. Uh wonderful. So, uh I'd love to talk about uh the landscape of the chip industry right now to help people visualize and hard work where where you guys um are. So, um there used to be basically this concept of like one chip to do it all. uh and uh obviously this is evolving dramatically. Um this you guys uh this this Grock uh this there are GPUs there are people have heard of tranium people have heard of TPU so help us compare and contrast like who does what for what
</details>

**Andrew Feldman**: 好的，我认为过去包揽一切的那个芯片叫做CPU。后来出现了一种协处理器来处理独立图形任务。而随着AI工作负载变得越来越有意思，我们越来越把芯片的重心放在那种特定的工作负载上。今天有多家公司制造传统GPU。所以Nvidia和AMD制造非常标准的GPU。也有一群公司，主要是那些超级计算提供商，他们自己制造一些芯片，比如TPU。

<details>
<summary>Original English</summary>

**Andrew Feldman**: well I I I think there used to be one chip to do it all was called the CPU right and uh there emerged a co-processor to do discrete graphics and uh as the AI workload became interesting. We focus chips more and more on that particular workload and today several companies make traditional GPUs. So Nvidia and AMD make very standard GPUs. Um there are a group of companies who uh the hyperscalers make make some of their own parts. So the TPU
</details>

**Matt**: 所以TPU是谷歌的。

<details>
<summary>Original English</summary>

**Matt**: so TPU is Google
</details>

**Andrew Feldman**: TPU是谷歌的，而Trainium是AWS的。是的。此外还有像Cerebras这样的群体，我们是那些从零开始、专门为AI设计且只为AI优化芯片的先驱之一。我们并不隶属于某个超级计算提供商内部。我们没有针对某个超级计算提供商或某个特定实验室的问题进行优化。我们是为一个广泛的AI问题集合构建芯片，我们所有的思考都围绕着如何加速AI展开。

<details>
<summary>Original English</summary>

**Andrew Feldman**: TPU is Google and Tranium is is uh AWS. Yep. Um and then there were group uh like Sburus um and we were among the pioneers to to to build a part from scratch uh optimized for AI and nothing else and that we weren't inside of a hyperscaler. We weren't optimized for a hyperscaler's problem or for one lab's problem. We we were building a a a chip for a collection of of AI problems and all our thinking was around how to accelerate AI.
</details>

**Matt**: 这就是目前的格局。

<details>
<summary>Original English</summary>

**Matt**: And that's sort of the landscape to this day.
</details>

**Andrew Feldman**: 是的。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah.
</details>

**Matt**: 还有更专用的芯片，对吧？比如专门为Transformer模型开发的边缘设备。那些也被称为ASIC。你能否解释一下这个术语的含义？

<details>
<summary>Original English</summary>

**Matt**: There's even more specialized ones, right? Like edged developed specifically for transformers. Then those are called AS6 as well. Could can you maybe define what that term means?
</details>

**Andrew Feldman**: ASIC代表专用集成电路（Application Specific Integrated Circuit）。现在这个词的含义非常广泛。它意味着你在设计时做出了一系列选择，从通用目的转向更窄的一类问题解决领域，并且你在架构上做出了一些决定，使其在某些方面表现得好得多，而在其他方面则差得多，对吧？这是在整个范围内做出的取舍。所以TPU就做了一些这方面的选择。它不能做图形处理。但它非常擅长矩阵乘法。它并不擅长我们在数学中做的一系列其他事情。GPU也是同理。我们都在做不同的选择。就目前正在生产的产品而言，有谷歌的TPU和Trainium。即将推出的还有来自微软的Maia，以及Cerebras的产品，另外还有一个被Nvidia收购的Grock。

<details>
<summary>Original English</summary>

**Andrew Feldman**: And as is an application specific integrated circuit and and it's um uh it's a word that that now has a a wide range of of meaning. It it means that you have made a series of choices away from general towards a narrower class of uh problem solving and that you've made some decisions in your architecture that make it much better at some things and much much worse at others. Right? And and that's uh choices that are made across the spectrum. So the TPU has made some choices like that. It can't do graphics. It's very good at matrix multiply. It's not very good at a collection of other things that we do in in mathematics. Um uh uh same for the GPU. We we've all made different choices. I was right now in production there are uh and there are a collection there's the TPU for Google tradiums. uh just coming up is a Maya part is a part from uh uh uh Microsoft uh Cerebrus and there was one other uh grow up that got acquired by by Nvidia.
</details>

**Matt**: 是的。关于通用芯片与专用芯片的话题，其实很有意思。当Grock被收购时，你和你的首席技术官庆祝了一番。那次收购意味着什么？是不是Nvidia承认了你们的愿景一直都是正确的？

<details>
<summary>Original English</summary>

**Matt**: Yeah. And to the general chip versus pis chip it was actually interesting because you guys and your CTO celebrated when Grock was acquired. Was that what was that? Was it a recognition by Nvidia that your vision was right all along?
</details>

**Andrew Feldman**: 是的。我认为Nvidia最持久的护城河之一，就是人们普遍认为GPU可以做所有事情，并且它是AI所需的全部。而以200亿美元收购Grock，以及他们选择进行收购的结构和速度，向所有人清楚地表明这并不是事实。GPU架构无法做到快速推理，而这个市场巨大且增长迅速，我们在这个领域是速度最快且规模最大的，你知道，我们的销售额是Grock的10倍以上，而他们竟然花200亿买下了市场老二。所以那是美好的一天。

<details>
<summary>Original English</summary>

**Andrew Feldman**: Yeah, I I think uh one of the things India's sort of most durable modes was the perception that the GPU could do everything and it was all you needed for AI. And the acquisition of Grock for $20 million and the structure and the speed with which they chose to do it made clear to everyone that that wasn't true. that uh the GP architecture couldn't do could not do fast entrance and that this market was large and growing quickly and we were the fastest at it and the largest and you know our sales were more than 10 times the Gro and they paid 20 billion for the number two player. So that was a good day.
</details>

**Matt**: 那确实是美好的一天。对。那么，最近有关OpenAI（这也是你们的一个大客户）和博通之间关于Halapeno芯片的声明呢？这在整个格局中处于什么位置？这也是那些用于推理的高度专业化的ASIC之一吗？

<details>
<summary>Original English</summary>

**Matt**: That was a good day. Right. And um the recent announcement uh of Halino between Open which is a very large customer of yours and Broadcom. Uh where does it fit in that picture? Is that one of those highly specialized aix right Gro for inference?
</details>

**Andrew Feldman**: 没错。Jalapeno是一款酝酿已久的芯片。它是在OpenAI与我们达成交易之前与博通一起宣布的。记住，我们达成了一笔庞大的交易。这可能是硅谷历史上最大的交易之一，价值超过200亿美元。我认为他们对硅片有巨大的需求，而OpenAI正在做的一件事情就是——

<details>
<summary>Original English</summary>

**Andrew Feldman**: That's right. Jalapeno is a is a part uh that has been a long time coming. Um it was uh announced with Broadcom before uh OpenAI did the deal with us. Remember we did a huge deal. This is probably the largest deals in Silicon Valley history north of 20 billion dollars. Um uh I I think they have a a yawning need for silicon and the uh one of the things that open AI has
</details>

<!-- chunk 2/7 -->

### AI行业增长与需求

**Speaker A**: ……我认为业内最擅长的是着眼于指数级的采用增长率，并且不畏惧它所传达的信息。对吧？其他一些公司不得不四处奔走，去达成非常糟糕的交易以获取算力，而OpenAI则预见到了这一切。他们为了存储、为了算力，与我们以及其他公司达成了大笔交易。嗯，他们在理解从指数曲线外推的意义上确实很有远见，而这条曲线就是AI的使用量，对吧？它增长得令人难以置信地快。整个行业都在追赶需求。信仰，对吗？通常我们——嗯，往往情况是相反的。通常人们是“先建好，希望需求会来”，而在我们这个案例中，我们所有人都在追赶人们现在就想做的事情，更不用说他们未来可能想做的事情了。

<details>
<summary>Original English</summary>

**Speaker A**: ... been I think the best uh in the industry at is looking at an exponential curve adoption rate of growth and not being afraid of what it says. Right? Others have had to go out and strike really bad deals to get capacity where OpenAI saw this coming. They struck big deals for memory, for compute, with us, with others. Um, they've really been sort of visionary in understanding the what it means to extrapolate from an exponential curve and that curve is AI usage, right? It is growing so unbelievably fast. The whole industry is chasing demand. Faith, right? We usually uh well often it's the other way. Often people are building it hoping it will come and in our case all of us are chasing what people already want to do, let alone what they might do in the future.

</details>

### 多元芯片生态

**Speaker B**: 稍微停一下，因为这是一个非常有趣的话题。为了结束关于GPU（GPS的口误）、推理和ASIC（A6的口误）的讨论，从你的角度来看，这是一个永久的局面吗，我们将永远处于这种多硅（multi-silicon）的环境中吗？

<details>
<summary>Original English</summary>

**Speaker B**: Put a bit um because that's such an interesting topic. um to to finish on GPS versus inference versus A6. Uh is that the permanent situation from your perspective that we're going to be in this uh forever multi-silicon kind of environment?

</details>

**Speaker A**: 是的，多硅环境是一个健康的生态系统，对吧？我不认为有人会说x86环境曾经是一个健康的地方。在长达20年的时间里，那里只有两个玩家。而且如果你注意到了，当新的工作负载出现时——手机工作负载——它非常相似，但需要低功耗和电池，然后他们两个都输了，对吧？英特尔获得了零份额，AMD也获得了零份额，一家以前没人听说过的公司成为了世界上计算能力最大的销售商，那就是Arm（我们的A的口误）。并且，健康的生态系统有很多不同的方式来解决问题。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, multi silicon environment is a healthy ecosystem, right? I don't think anybody would say that the x86 environment was a healthy place. There were for 20 years there were two players and if you notice when a new workload came around cell phone workload... it was very similar but required uh low power and battery and both lost right Intel got zero share AMD got zero share and a company nobody previously heard of became the largest seller of compute in the world and that's our A and that uh healthy ecosystems have lots of different ways to solve problems.

</details>

### 中美AI生态的差异

**Speaker B**: 在所有这些情况中，中国处于什么位置？目前有用于深度学习的华为昇腾（Ascent）芯片，而且出现了一个全栈的中国AI“工厂”——姑且这么称呼吧。这种分化正在发生吗，还是说被夸大了？

<details>
<summary>Original English</summary>

**Speaker B**: Where where does uh China fall in all of this? So there's the Huawei Ascent chips for deep sea and this emergence of a full stack Chinese um AI factory for lack of a better term. Is that divide happening or is that overstated?

</details>

**Speaker A**: 不，不，这种分化是真实存在的。我认为他们是一个工业竞争对手，我觉得他们做了一些非常有趣的投资，在电网的电力方面进行了投资，这在美国是一个真正的弱点。如果你在法国，你有核能，结果证明那是相当便宜且干净的能源。但在中国，他们在电网上进行了巨大的投资。他们在芯片方面落后，但他们的下一层次的做法是作为开源模型，他们正在生产一些非凡的模型，虽然不如GPT、Anthropic或谷歌的Gemini好，但非常优秀。我认为，他们没有美国那样的芯片冲击力，但他们在其他领域拥有领先地位——

<details>
<summary>Original English</summary>

**Speaker A**: No, no, that divide is real. I think they are an industrial adversary that I think um they have made really interesting investments that made investments in power in their grid which is a real weakness in the US. Um if you're in France you have nuclear which sort of turns out to be pretty cheap power and pretty clean. Um but uh in China they made huge investments in their grid. uh they are behind in chips um but their approach was at the next level as open-source models where they producing some extraordinary models not as good as GPT or anthropic or Google's Gemini but very good and I think uh they don't have the same chip strikes that the US does but they've got leadership in other debates

</details>

**Speaker B**: 也许在电力方面，这正是日常销售商所需要的。

<details>
<summary>Original English</summary>

**Speaker B**: potentially in power which is what we need for daily sellers.

</details>

**Speaker A**: 好的。那么中国在第三场竞赛战略中处于什么位置？（注：结合语境可能为此方询问或反问）

<details>
<summary>Original English</summary>

**Speaker A**: Okay. Where does China fall in third race strategy?

</details>

**Speaker B**: 我们不卖问题（We don't sell questions）——

<details>
<summary>Original English</summary>

**Speaker B**: We don't sell questions

</details>

**Speaker A**: 呃，出于地缘政治的原因，出于商业的原因，因为——

<details>
<summary>Original English</summary>

**Speaker A**: uh for geopolitical reasons, for business reasons, for

</details>

**Speaker B**: 监管的原因，

<details>
<summary>Original English</summary>

**Speaker B**: regulatory reasons,

</details>

**Speaker A**: 出于监管的原因，以及一些地缘政治的原因。

<details>
<summary>Original English</summary>

**Speaker A**: for regulatory reasons and and for some uh geopolitical reasons.

</details>

### 本地AI与数据中心

**Speaker B**: 好的。那么本地AI和本地芯片有发挥作用的空间吗？英伟达发布了一些关于专门为Windows电脑制造芯片的公告。那是为了推理吗？你们认为那应该是多生态系统的一部分吗？

<details>
<summary>Original English</summary>

**Speaker B**: Okay. Um is there a role for uh local AI and local chips? Nvidia had some announcement around just building chips for Windows computers. Is that for inference? Is that something that you guys uh think should be part of the multi ecosystem?

</details>

**Speaker A**: 是的，我认为，如果你看看应用和云生态系统是如何出现的，你能在手机或笔记本上做的一切，你就应该在手机或笔记本上做。但是，将真正的处理能力放到手机或笔记本上是受限的，因为它们通常依靠电池工作。所以你想尽可能多地在靠近数据的地方进行计算。但事实是，在大多数情况下，需要真正的计算能力，这就是AI未来的发展方向。我们将在手机上、在笔记本上做大量工作，但对于大型任务，你会去数据中心，而这正是我们的关注点。我们的关注点在数据中心的计算上。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think uh if you look at the way the ecosystem for uh apps and cloud emerged uh everything you can do you should do on your phone or your laptop. But the ability to get real processing power to a phone or to a laptop is constrained because they're generally working off a battery. And so you want to do as much as you can as close to the data as you can. But the truth is is in most situations for real comput. And that's exactly the way it's going to be with AI. We're going to do a lot of work uh on the cell phones uh on the laptop but for the big work you're going to go to the data center and that's where our focus is. Our focus is data center compute free.

</details>

### 市场泡沫的担忧

**Speaker B**: 很好。嗯，你提到了需求是多么强劲，需求超出了产能。那么只是问一个不可避免的问题，关于市场是否处于均衡，是不是泡沫。比如，最近我们都看到的一件事是，6月初发生了一次“闪电崩盘”，损失了1.5万亿的市场价值，英伟达在那一天就损失了3000亿。当然，这在48小时内就被修正了。所以市场似乎围绕着那个普遍概念非常神经质。根据你刚才所说的话，听起来你似乎在这一担忧的另一面保留了筹码？

<details>
<summary>Original English</summary>

**Speaker B**: Great. Um so you mentioned the uh how powerful the demand was and demand out of you know of production. So u just to ask the inevitable question around um market equilibrium bubble or not. So like the most recent um thing we all saw is that there was a bit of a flash crash earlier in June where 1.5 trillion in market value was lost and Nvidia had lost 300 billion that day. Now that was corrected within you know 48 hours. So the market seems uh very jittery uh around that general concept just uh would put the words just based on what you said sounds like you your reserve a play on the other side of that concern

</details>

**Speaker A**: 呃，我认为，如果你花很多时间盯着公开市场，并且每天看它们的起起落落，你就在关注错误的东西了。我认为，从公开市场投资的伟大思想家那里获得的智慧是，在短期内，公开市场是投票机制，看谁最受欢迎；但在长期内，它们是称重机制，看谁创造了最多的价值，最重的重量。所以，作为一家新上市的公司，我们可以做的是不去看日常的波动，我们可以专注于构建非凡的技术，赢得新客户，让我们现有的客户开心，确保他们买得更多，每周变得更好。所以我认为日常的波动是我们无法控制的。嗯，那是关于投票的。

<details>
<summary>Original English</summary>

**Speaker A**: uh I think that if you spend a lot of time staring at the public markets um and watching their ups and downs every day you're watching the wrong thing. I think that right the wisdom uh received from uh the great thinkers of public market investing is that in the short term the public markets are voting mechanisms who's most popular but in the long term they're weighing mechanisms who's created the most value the most weight and so what we can do as a newly public company is we can not look at the day-to-day fluctuations and we can focus on just building extraordinary technology, winning new customers, making our existing customers happy, ensuring they buy more, um being better every week, and so I think the day-to-day fluctuations are out of our hands. Um and that's about the voting.

</details>

**Speaker B**: 是的。我的意思是，仅仅是为了对需求扮演“魔鬼代言人”的角色，看起来很多需求来自于大型实验室，而它们自己是由风险投资、私募股权、对冲基金资助的，不管你怎么称呼它，还有主权投资者。你有没有担心，对芯片的需求来自这些也许是被人工注资的实验室，如果你在这里那里加上几圈交易，你会感觉到任何脆弱性吗？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And I mean, just to play a devil's advocate on the demand, um it seems like a lot of the demand comes from the big labs which you know themselves are financed by uh venture capital, private equity, hedge funds, whatever you call it in you know sovereign investors. Um is there any concern that you know demand for chips comes from the labs which are maybe artificially financed and that the you know if you add a few circle of deals here and there you sense any fragility.

</details>

**Speaker A**: 嗯，那不完全是我们的经验。我的意思是，显然我们有来自Inflection（原文可能是inopan的误听）的巨大需求，但我们也有庞大的、你知道的、几十个其他正在尝试下非常大订单的客户，而且从历史上看，泡沫是指供应跑到了需求前面，对吧？当我们在90年代建立电信基础设施时，对吧，我们超前几年铺设了光纤，虽然它花了六到八年才全被用上，但这是一种“建好了，他们就会来”的心态。而现在AI的不同之处在于，我们都在努力追赶，我们在努力以更快的速度建设数据中心，我们在努力增加针对现在已经存在的需求的供应链。而且世界上只有极小一部分人在接近AI潜力的程度去使用它，而我们已经被计算能力压得喘不过气来了。我们被对存储的需求所压倒，这是一个真正的弱点；而GPU不是我们面临的问题，在这个生态系统中左左右右都是限制因素。那感觉不像是一个泡沫。

<details>
<summary>Original English</summary>

**Speaker A**: Um I that's not exactly our experience. I mean obviously we have uh enormous demand from inopan but we have huge you know dozens of other customers who are trying to place in very big orders ops and uh historically bubbles were when supply got out ahead of demand right when uh in the 90s we built out telco infrastructure right we built out fiber years before it was going to be used and it took six or eight years and it all got used but it was a sort of if you build it they will come mentality whereas what's different about AI right now is we're all trying to catch up um we're trying to build data centers faster we're trying to increase our supply chains for demand that's already here today and only a very small portion of the world are using AI anywhere close to its potential and we're already sort of overwhelmed with compute. We're um overwhelmed with uh the demand for memory which is a real weakness and the GPUs is not a problem we face and the ecosystem they're constraints left and right and that doesn't feel like a bubble.

</details>

### 当前供应链的三大瓶颈

**Speaker B**: 你想在这个问题上再详细谈谈吗？因为那太有趣了，对吧？似乎瓶颈在不断转移。那么大家可能听说过的当前关于内存短缺的问题到底是什么呢？

<details>
<summary>Original English</summary>

**Speaker B**: Do you want to actually double take on that? because that's uh so interesting, right? It seems like the bottleneck keeps moving because uh so what's the current problem of a memory shortage that people may have heard of?

</details>

**Speaker A**: 那么，目前有三大瓶颈。首先是所有GPU和所有ASIC（原文误作AS6）——除了我们——都在使用一种名为DRAM（原文误作DRM）的存储。

<details>
<summary>Original English</summary>

**Speaker A**: So uh there are three major bottlenecks right now. The first is all GPUs and all AS6 except us um use a type of memory called DRM

</details>

**Speaker B**: 以及该存储的一个特殊变种称为HBM（原文误作HBO）？

<details>
<summary>Original English</summary>

**Speaker B**: and a particular flavor of that memory called HBO

</details>

**Speaker A**: 而且这种存储是由世界上三家公司制造的，三星和美光（原文此处缺失海力士）。

<details>
<summary>Original English</summary>

**Speaker A**: and uh that memory is made by three companies in the world, Samsung and Microsoft. (Note: Intended Micron/SK Hynix)

</details>

**Speaker B**: 三家公司，而且都卖光了。那是第一大问题。你们不使用它。

<details>
<summary>Original English</summary>

**Speaker B**: Three companies and they're sold out. That's the number one problem. We don't use it

</details>

**Speaker A**: 而且它卖光了意味着，就像所有的硬件一样，增加供应的唯一方法就是建造新工厂。

<details>
<summary>Original English</summary>

**Speaker A**: and it's sold out as in like the only way to as all things hardware the only way to increase supply would be to build new factories.

</details>

**Speaker B**: 建造更多工厂。

<details>
<summary>Original English</summary>

**Speaker B**: Build more factories

</details>

**Speaker A**: 所以你面临着GPU甚至现在CPU的这个巨大问题，你们拿不到这种存储。由于我们的架构选择，我们不使用它。
第二个限制因素是台积电的一项工艺，叫CoWoS（原文误作co-ass），这使用了硅作为主板，这就是英伟达、AMD和其他公司用作主板的技术。因此，他们将芯片和存储芯片放在上面，它比传统主板更高效。这项工艺也卖光了，受到了高度限制。我们不使用它。
这个领域的第三个限制因素是台积电3纳米工厂的产能。所以，这是最激进的——

<details>
<summary>Original English</summary>

**Speaker A**: and so uh you have this huge problem for GPUs and uh even now for CPUs and you can't get this memory because of our architectural choices. We don't use it.
The second constraint was a process at TSMC process was called co-ass and this used silicon as a motherboard and this is what Invidia and AMD uh and others use as a motherboard. So they put their chips and the memory chips on it and it's more efficient than a traditional motherboard. ahead that process is sold out is highly constrained. We don't use it. Third limitation in the space is 3 nanometer factory space at TSMC. So this is the most aggressive

</details>

<!-- chunk 3/7 -->

### 芯片制程与流片工厂

**Speaker A**: 晶圆厂。所以，凭借最先进的技术，我们的芯片采用的是5纳米制程。因此，我们并没有使用3纳米技术。所以……

<details>
<summary>Original English</summary>

**Speaker A**: factory. So with the most advanced technology, our chips are at 5 nanmter. So we don't use the three nanmator technology. And so

</details>

**Speaker B**: 这太令人着迷了。所以，问个外行的问题。这到底是什么意思呢，流片工厂（stream factory）？是说有一个专门致力于此的工厂吗？

<details>
<summary>Original English</summary>

**Speaker B**: and and that's so fascinating. So uh to ask the layman's question. So this this this what does that mean stream factory? There's a factory that's solely dedicated.

</details>

**Speaker A**: 没错。他们建立工厂，然后在工厂里蚀刻晶体管。

<details>
<summary>Original English</summary>

**Speaker A**: That's right. They they build factories and the factory etches transistors

</details>

**Speaker B**: 这些晶体管之间有一定的间距。而且间距越小，每平方毫米的晶体管数量就越多。每平方毫米能做的事情也就越多。

<details>
<summary>Original English</summary>

**Speaker B**: that are a certain distance apart. And the smaller the distance apart, the more transistors per square millimeter. And the more you can do per square millimeter.

</details>

**Speaker A**: 是的，所以整个计算机行业制造芯片的历史，就是我们在把晶体管放得越来越近这方面变得越来越出色的历史。

<details>
<summary>Original English</summary>

**Speaker A**: And so the history of the computer industry making chips has been we've gotten better and better at putting transistors closer and closer.

</details>

**Speaker B**: 没错。

<details>
<summary>Original English</summary>

**Speaker B**: Yep.

</details>

**Speaker A**: 所以我们过去的间距是16纳米，然后我们进步到了10纳米，再到7纳米，再到5纳米，现在到了3纳米，并且他们正在研发2纳米和1.8纳米。所以现在，GPU世界的大部分芯片都在使用3纳米，而工厂里出现了巨大的拥堵。

<details>
<summary>Original English</summary>

**Speaker A**: And so we used to be at 16 nmters apart and then we went to 10 at to seven and to five at three and they're working on two 1.8. And so right now the bulk of the the the GPU world is all three and there's tremendous congestion at the factory

</details>

**Speaker B**: 而且这在工厂里确实需要完全不同的模具。

<details>
<summary>Original English</summary>

**Speaker B**: and that's literally different tooling at the factory

</details>

**Speaker A**: 工厂里的模具。

<details>
<summary>Original English</summary>

**Speaker A**: tooling at the factory

</details>

**Speaker A**: 我们使用的是5纳米工厂，这是我们的芯片。

<details>
<summary>Original English</summary>

**Speaker A**: and we use uh the 5m factory and this is our ship here.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

**Speaker A**: 这是计算机行业历史上制造的最大的芯片。它比普通 GPU 大 58 倍。你知道的，它的内存带宽是普通 GPU 的两千五百或三千倍。而且对于 AI 来说，更大的芯片能更快地处理信息，因此你能在更短的时间内获得答案。显然，你不会想要为笔记本电脑、手机或许多其他设备配备更大的芯片，但对于 AI 世界来说，大芯片毫无疑问是最好的发展方向。

<details>
<summary>Original English</summary>

**Speaker A**: This is the largest chip built in the history of the computer industry. is 58 times larger than a GPU. It has, you know, two and a half or three thousand times more memory bandwidth. Um, and for AI, bigger chips process information more quickly and therefore you get answers in less time. And obviously you don't want a bigger chip for a laptop or a cell phone or for lots of other things, but for AI world, big chips are undoubtedly the best way to go.

</details>

### AI与CPU需求

**Speaker B**: 好的，这没问题。所以我想稍后对芯片本身进行一些深入探讨。但在结束这个话题之前，你说到了三个瓶颈。你在几分钟前的谈话中也提到了 CPU，似乎出现了一个关于 CPU 短缺的主题。那这是真的吗？是什么导致了这种情况？

<details>
<summary>Original English</summary>

**Speaker B**: Okay, that's all right. So let's So I want to do a bit of a deep dive on that on the chip itself in a in a second. Um uh but to close on this, so three bottlenecks. Um you also mentioned CPUs a couple minutes in this conversation and there seems to be a theme around the emergence of like a CPU uh shortage as well. Is that so one is that true to what causes it? So

</details>

**Speaker A**: 智能体 AI（Agentic AI）是一个 AI 不仅仅提供答案，还会主动发起行动的世界。这个行动可能是访问一个网站。也可能是去学习、从网站收集一些数据，把它们带回来，然后采取另一个行动。这些行动都是由 CPU（转录为 CPDs）来完成的。因此，随着 AI 在执行任务、发出指令、调用服务来完成事情方面变得越来越出色，我们正在使用越来越多的 CPU，对吧？这就推高了 CPU 的消耗量，进而增加了对 CPU 的需求。所以，这种对更多 CPU 的巨大推动力，正是由我们这样的机器以及 GPU 上的 AI 执行智能体工作并要求 CPU 采取行动所驱动的——无论是去网站点墨西哥卷饼，去寻找一条信息，还是从存储中提取它，所有这些工作都由 CPU 来完成。是的。

<details>
<summary>Original English</summary>

**Speaker A**: a gentic AI is a world in which AI doesn't just provide answers it initiates action. So that action might be go to a website. It might be learn, gather some data from a website, bring it back, take another action. Those actions are done by CPDs. And so as AI gets better and better at doing things, at making instructions, calls for things to get done, we're using more and more CPUs, right? And that is driving up the consumption of CPUs and therefore the demand for CPUs. And so this sort of huge push for more CPUs is being driven by AI on machines like ours and GPUs doing agentic work and asking the the the CPUs to take an action to go to a website to order burrito to find a piece of information to pull it from storage to all that work is being done by the CPU. Yes.

</details>

**Speaker B**: 包括在像你们这样的系统中。

<details>
<summary>Original English</summary>

**Speaker B**: Including in a system like yours

</details>

**Speaker A**: 在像我们这样的系统中。

<details>
<summary>Original English</summary>

**Speaker A**: in a system like ours.

</details>

**Speaker B**: 哦，这很有意思。那么，那意味着什么呢？所以你有一侧是你们的芯片，另一侧是 CPU，它们将组成一个系统。

<details>
<summary>Original English</summary>

**Speaker B**: Oh, it's interesting. So, so um what does that mean? So you you have your your chip and CPUs on the side and and those will be a system.

</details>

**Speaker A**: 这意味着，当我们做智能体 AI 时，AI 处理器就像是大脑，而 CPU 就像是身体。它们在采取行动。它们在数字世界中做事，受运行在服务器系统加速器上的 AI 指挥。所以，随着我们做越来越多的 AI 工作和越来越多的智能体工作，我们对 CPU 的调用也越来越多，因此对 CPU 的需求简直要冲破屋顶。

<details>
<summary>Original English</summary>

**Speaker A**: It means that um AI when we do AI the gentic they uh the AI processor is like the brains and the CPUs are like the body. They're taking action. They're doing things in the digital world. under the direction of the AI which is running on the accelerator on the the server system. And so as we do more and more AI work and more and more agentic work, we're making more and more calls to CPUs and therefore the demand for CPU is just through the roof

</details>

**Speaker B**: 并且 CPU 也经历了同样的内存短缺，它们使用的数字是完全相同的。

<details>
<summary>Original English</summary>

**Speaker B**: and CPUs experience the same memory short memory shortage they use the exact same number.

</details>

**Speaker A**: 没错。

<details>
<summary>Original English</summary>

**Speaker A**: That's right.

</details>

### 创业历程与市场时机

**Speaker B**: 好的。是的。我们稍后会回到产品的话题上，但让我们稍微谈谈你和你的创业旅程，好让大家了解一下背景。所以，显然，你把握住了绝佳的时机，完成了一次令人难以置信的 IPO。而且我知道……我知道这有一点……

<details>
<summary>Original English</summary>

**Speaker B**: Okay. Yeah. Let's go back to the product in in a second, but um uh let's talk about you and your journey a little bit for for people to have context. So, you know, obviously you pulled and hold of an incredible um IPO with perfect timing. Um and I know I know it was a little bit

</details>

**Speaker A**: 他们觉得，拥有完美时机的方法，就是在此之前的 10 年里经历糟糕透顶的时机。这就是你获得完美时机的方式。

<details>
<summary>Original English</summary>

**Speaker A**: they make the way you have perfect timing is to have horrible timing for 10 years. That's the way you have perfect and

</details>

**Speaker B**: 非常切中要害。所以你们在十多年前就开始研发这款专注于推理的更大芯片了。

<details>
<summary>Original English</summary>

**Speaker B**: very much to this point. So like you you guys uh started building this uh you know bigger chip focused on inference in uh you know over a decade ago

</details>

**Speaker A**: 2016年。

<details>
<summary>Original English</summary>

**Speaker A**: 2016

</details>

**Speaker B**: 2016年。事后看来，考虑到构建这样一项技术需要花费多长时间，这完全合情合理。但当时的愿景是什么呢？那是2016年，我猜那是 ImageNet 深度学习成为热门话题之后的第四年吧。

<details>
<summary>Original English</summary>

**Speaker B**: 2016 uh which u you know makes perfect sense in in retrospect given how long it takes to build a technology like this but like what what was the the vision right 2016 I guess it was like four years after image net deep learning was a thing

</details>

**Speaker A**: 当时全是计算机视觉。

<details>
<summary>Original English</summary>

**Speaker A**: it was all it was all vision

</details>

**Speaker B**: 当时全都是这些革命，这就是为什么……

<details>
<summary>Original English</summary>

**Speaker B**: it was all revolutions and and that's why

</details>

**Speaker A**: 我们不认为正确的做法是把你最新的、最酷的模型硬编码到电路中。那是个错误。你知道，我们是世界上运行 Transformer 最快的，而我们的架构在 Transformer 出现之前就已经确定了，对吧？我们是世界上运行 Diffusion 最快的，而我们的架构在 Diffusion（转录为 confusion）出现之前就已经确定了。你要做的是掌握这些模型的底层基础，这样当市场发生变化时，你也能同样擅长新的方向，否则……

<details>
<summary>Original English</summary>

**Speaker A**: We we don't believe the right thing to do is to embed the the latest and coolest uh model into your circuitry. That's a mistake. You know, we're the fastest in the world of transformers and our architecture was set before transformers existed, right? We're the fastest in the world of diffusion before and our architecture was set before confusion. What you want to do is get the underpinnings of those so that when the market moves you can be good at that as well otherwise

</details>

**Speaker B**: 因为生命周期很短。

<details>
<summary>Original English</summary>

**Speaker B**: because short life

</details>

**Speaker B**: 回到之前关于 ASX 的问题，所以其他人的做法就是把模型的架构直接构建到……

<details>
<summary>Original English</summary>

**Speaker B**: to the ASX question earlier so that's what others do they build the architecture of the model into the

</details>

**Speaker A**: 有些人是这么做的，有些人确实这么做了，而历史上这被证明是一个结构性的错误。

<details>
<summary>Original English</summary>

**Speaker A**: some have some have and historically that's been a structural mistake

</details>

**Speaker B**: 这是一个结构性的错误。所以你们在做的是一个适用于任何类型模型的全新横向平台。

<details>
<summary>Original English</summary>

**Speaker B**: it's been a structural mistake so you're doing the brand new horizontal platform on any kind of model

</details>

**Speaker A**: 你需要思考的是底层的计算逻辑是什么。所有这些工作的底层计算都是稀疏线性代数。

<details>
<summary>Original English</summary>

**Speaker A**: you want to think about what is the underlying calcul calcation the underly calculation at all this work is sparse linear algebra.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 如果你能加速这个计算，那么无论模型制造商发明出什么，你都能让它运行得更快。好的。这就是我们的方法。

<details>
<summary>Original English</summary>

**Speaker A**: And if you can accelerate that whatever the bottle makers invent you can make faster. Okay. And that was our approach.

</details>

### 从SeaMicro到新征程的经验教训

**Speaker B**: 是的。所以你们从2016年起步。你之前有一家公司卖给了 AMD。你在那里学到了哪些重要的经验教训，并将其带到了现在的公司中？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So you started in 2016. Um you had a prior company that you sold to AMD. What were some of the lessons you run there that you took into serious?

</details>

**Speaker A**: 我认为这些经验教训既宏大又兼具中等规模。我想其中之一就是，经验不过是犯错并从中学习的代名词，对吧。我认为，你知道，我们作为一个团队在过去25年里构建了几十款芯片，而在芯片制造领域，经验的回报是巨大的。我们在 SeaMicro 构建了一种不同类型的计算机，一种专为低功耗和不同于 AI 的工作负载（比如网页浏览）而优化的计算机。但是，作为一名计算机架构师，你所问的根本问题始终是一样的：我能做些什么让这项工作跑得更快，对吧？并且这种需求是否足够大，以至于值得我们去做？这就是我们所问的两个问题：我们应该为此构建一种架构吗？我们能做些什么来构建一个专门为 AI 优化的芯片？以及未来会有足够的 AI 需求，让你能围绕它建立起一门生意吗？这些就是我们在2016年提出的问题。而在硬币的另一面，我的意思是，如果 GPU——这个被优化用于图形处理了 20 年、一直在往显示器上推像素的组件——突然在一个全新的世界里大放异彩，那难道不是一件令人惊讶的事吗？那得是多大的偶然？而我们逐渐相信，GPU 并不是适合 AI 的正确架构。它只是比 CPU 好用而已。而且我们相信我们可以构建出一种速度快得多、功耗更低，并且能降低成本的架构。

<details>
<summary>Original English</summary>

**Speaker A**: I think the lessons are large and medish. I think what one what are the things you know I guess experience is is another name for having made mistakes and learning from them right I I think you know we we have as a team built dozens of chips over the past 25 years and the returns to experience and chipm is enormous and we built a different type of computer at at C Micro a type of computer optimized for low power and optim optimized for a workload that was very different than AI for something like web browsing and uh but the the fundamental underpinnings the questions you ask as a computer architect are always the same what what can I do to to to make this work faster right and is there enough of it to make it worthwhile these are the two questions we ask um should we build a art for it. Should we what could we do to build a chip optimized for AI and will there be enough AI so that you can build business around it? Those were the questions we asked in 2016. And you know the the the flip side of that was I mean wouldn't it be a surprise if the GPU which had been optimized for graphics for 20 years and been pushing pixels to a monitor was suddenly good at a new world. it'll that be serendipitous and we came to believe that that it wasn't the right architecture for it. It was just better than the CPU and that we could build an architecture that would be vastly faster. It would use less power and could drive down the cost of of it

</details>

**Speaker B**: 那是一段漫长的旅程。所以服务在很早就推出了，但是……

<details>
<summary>Original English</summary>

**Speaker B**: and that was the journey. So service was very early but uh

</details>

**Speaker A**: 然后我们在沙漠中度过了一段时光。在沙漠中。然后我们在沙漠中漫游。

<details>
<summary>Original English</summary>

**Speaker A**: then we spent time in the desert. in the desert. Then we want then we wander in the desert.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker B**: 是的。也许你能稍微带我们回顾一下那几年的时光，特别是给那些听这个播客的创始人，尤其是深度科技领域的创始人们。那么，首先市场时机的问题到底出在哪里？是当时的技术行不通吗？然后你们作为一个团队是如何应对的？你是如何让团队成员和投资者加入，并完成更多轮融资的？毕竟，你当时很可能并没有别人需要的那些成功证明。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Maybe maybe walk us a little bit through those years for any you know founders especially NDP tech founders listening to this. So um what was so first of all what was the issue with the market timing? Was it the technology was not working? Uh and then how did you go about it as as a team? You getting your you on board and your investors and raising more rounds. So as as you presumably didn't have the proof points that one would need.

</details>

**Speaker A**: 对我们来说，一开始我们就对风险投资人坦诚相待，告诉他们我们将要攻克一个非常艰难的难题。我们不打算做一款只比 GPU 稍微好一点的产品。我们的想法、我们的战略是，你永远无法通过做一些只比英伟达好一点点的东西来打败这家伟大的公司，那种认为他们会为了更低的价格而购买一切的想法是虚假的。他们会面临定价压力，他们能够进行产品捆绑。因此正确的策略，是在工程上做一件极其困难的事情，其难度要远远……

<details>
<summary>Original English</summary>

**Speaker A**: So for us we uh at the beginning we were honest with our VCs and told them we're going to attack a really hard problem. We we weren't going to build something that was a little bit better than a GPU. And that our idea, our our strategy was that you will never beat a great company like Nvidia by doing something a little bit better than fake that they're going to buy everything for less. They're going to have pricing pressure. They're going to be able to bundle. And the right strategy would be to do something incredibly hard in engineering that was way

</details>

<!-- chunk 4/7 -->

### 芯片内存与架构策略

**Speaker A**: （性能可以提高）10倍、15倍、20倍、30倍甚至50倍。但要做到这一点，那些寻常且显而易见的路径都行不通了。其他人已经把门槛抬得很高。因此，我们观察到的是，推理速度将取决于内存，而且内存分为两种。一种是 HBM 的显存（VRAM），它们能存储很多数据，但是距离较远。还有一种叫做 SRAM 的内存，速度快得令人难以置信，但单位面积下存不了多少数据。在图形处理领域，大家一直使用的是 DRAM 或 HBM，因为 AI 的工作负载与图形处理有着根本的不同。在图形处理中，你把数据转移到 GPU，然后进行长时间的计算，最后再输出结果。因此，在数据移动和计算的总时间里，计算占据了主导地位。但在 AI 和推理中，情况恰恰相反。你需要将海量的数据，也就是所有的权重，从内存移动到计算单元，然后做一次计算来生成下一个词，接着又得重复这个过程。所以，绝大部分时间都花在了数据的移动上。这就是为什么 GPU 很难做到快速处理的原因。因此我们发现，如果选择使用 SRAM 的策略，速度可以更快。但随之而来的是，我们必须克服 SRAM 存储量小的短板。这就引出了我们的解决方案。如果我们能制造出一块比历史上任何芯片都要大得多的芯片——大概有餐盘那么大，我们就可以把 SRAM 填满整个芯片，从而既享受到 SRAM 极速的优势，又克服了它存储量不足的弱点。这让我们走向了一种叫做“晶圆级（wafer scale）”的策略。这种芯片是由台积电生产的一整块晶圆制成的。

<details>
<summary>Original English</summary>

**Speaker A**: 10, 15, 20, 30, 50 times better. But to do that, the ordinary and obvious paths are all close. Everybody else has taken the bar. And so what we observed was that speed in inference was going to be a function of memory and that there were two types of memory. There's this VRAM of HBM and they can store a lot but there's four. There's another type of memory called Eser that is unbelievably fast but per unit area can't store very much and that for graphics everybody had always used DM they used HP and that the AI workload was fundamentally different in graphics you move data to the GPU and then you work on it for a long and then you send the result. So the time spent in total of movement plus work is dominated by work. In inference and AI, it's the exact opposite. You move a huge amount of data, all the weights from memory to compute and you do one calculation to generate the next word and then you have to do it again. So all the time is dominated by the movement of data. So that's why GPUs have so much trouble being fast. Okay. So we observed that if we chose a strategy using SRAMM, we could be faster. But then we have to overcome the tradeoff with SRAM. It can't store very much. That led us to the solution. If we could build a part vastly larger than any part in history, right? at the size of a dinner plate. We could stuff it to the gills with SRAM and it and thereby get the benefit of SRAMM that it was fast and overcome the weakness that it can't store very much. And that led us to a strategy called wafer scale. This chip is made from a single wafer that comes out of TSMC.

</details>

**Speaker B**: 你想解释一下什么是晶圆（wafer）吗？

<details>
<summary>Original English</summary>

**Speaker B**: Do you want to define what a wafer is?

</details>

**Speaker A**: 晶圆，所有的芯片都是从晶圆上切割下来的。晶圆是一块圆形的硅片，直径为 300 毫米。制造芯片的过程就像你妈妈用饼干模具切饼干一样，把芯片一块块“切”出来。在我们之前，人类制造过的最大的芯片是 800 平方毫米，确切地说是 840 平方毫米。而我们的芯片是 46,000 平方毫米。因此，我们必须发明各种各样的新技术来制造这么大的芯片。一旦你把它造出来，你还得发明如何为它供电、如何为它散热的方法。没有任何现成的供应商在等着你。

<details>
<summary>Original English</summary>

**Speaker A**: A wafer, all chips are cut from a wafer. A wafer is a circular piece of silicon that's 300 mm across and the process of chip making stamps out like your mother does with a cookie cutter. Uh stamps out chips. The biggest chip that had ever been built before us was 800 square millm. 840 to be exact. And this is 46,000. So we had to invent all sorts of new technology to build a chip this big. And once you build it, you have to invent ways to power it, to cool it. There are no vendors waiting for you.

</details>

**Speaker B**: 是的，没错。因为你们的产品看起来跟以前制造的任何东西都不一样。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Right. Because you look like nothing else ever made.

</details>

### 深科技创业的挑战与失败分析

**Speaker A**: 这花了我们好几年的时间。而且，这是一个极其艰深的深科技（deep tech）问题，以前从未有人解决过。我们曾经历过一段长达 18 个月的时期，每个月烧掉 800 万美元，却造不出这东西。所以对于深科技的创始人来说，你们必须得有心理准备——

<details>
<summary>Original English</summary>

**Speaker A**: And that took years. And uh it it was a deep tip problem. It had never been solved before. And we had a an 18-month period where we were spending 8 million a month and we couldn't build them. So for your deep tech founders, you have

</details>

**Speaker B**: 每个月 800 万美元。

<details>
<summary>Original English</summary>

**Speaker B**: 8 million a month.

</details>

**Speaker A**: 对。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 为什么？为什么会这么多？光是为了弄懂这些东西怎么运作，成本就有多高？

<details>
<summary>Original English</summary>

**Speaker B**: And why why so much? What was the cost just to understand how these businesses?

</details>

**Speaker A**: 因为那些大家都认为很难的问题，我们很快就解决掉了。而那些别人不知道的东西——因为他们从来没有真正做过——结果却极其困难。你知道，我常跟别人打比方：想象第一支要去攀登珠穆朗玛峰的队伍，他们在珠峰大本营，正跟一支刚失败下来的队伍一起喝茶。刚失败的队伍说，“在半山腰有个地方，极其难爬，我们过不去。” 好，你们的队伍继续向上爬，一路登顶，然后下来又在喝茶。这次成功登顶的队伍转过身去，对那支没成功的队伍说：“你们说中间那个地方难？那根本不是最难的部分。” 因为（在他们之前）根本没有人越过那个难关，没有人跨过特定的障碍，所以他们甚至连该害怕什么都不知道。我们现在知道了。那个难关叫做封装（packaging）步骤。就是如何将整块晶圆固定到主板上，如何给它供电，如何给它散热。之前根本没人做过这种事。在那个 18 个月的周期里，我们在这个领域从近乎零基础变成了世界顶尖水平，对吧？我们是怎么做到的？就是一次又一次地失败，利用优秀的工程方法论，对每一次失败进行详尽的故障分析。所以我们不断犯下不同的错误。我们每六个星期跟董事会开一次会，我们会对董事会说，“没错，这就是我们的策略。以前没人做过。这就是我们要干的事。” 我们必须发明新材料，发明新技术。最终我们不得不亲自去造那些别人本来可以找合作伙伴来代工的东西。但在 2019 年 8 月，我们宣布我们解决这个问题了。我和我的联合创始人们，当这个东西第一次成功运行的时候，是在一个小小的实验室里，我们简直不敢相信。我们是前几个努力尝试让它运行的人，我们只能死死盯着它看。你知道的，看着服务器运行，基本跟盯着油漆变干一样无聊。但当时我们五个人，就死盯着那台机器，不敢相信它可能真的跑起来了。我们真的做到了。

<details>
<summary>Original English</summary>

**Speaker A**: Because what everybody thought was hard, we solved quickly. And and what nobody else knew about because they'd never actually done it turned out to be really hard. You know, imagine I tell people, imagine the first group that was going to climb Everest and they're at base camp and they're having tea with a group that just failed. And the group that just failed says, "Halfway up, there's this part. It's unbelievably hard. We couldn't do it." Okay. Your team climbs up, makes it all the way to the top, comes back, they're having tea again, and the team that made it leans over the team that hadn't made it. Said that part in the middle, that wasn't the hard part because nobody had gotten past it. Nobody had gotten past certain things. So, they didn't even know what to be afraid of. We we now know. And it was something a step called packaging. And that's how you fix a wafer to a motherboard, how you deliver power to it, and how you cool it. And uh nobody had done it before. And over that 18-month period, we became the best in the world at it from approximately zero, right? And we did that by sailing again and again and using good engineering methodology and doing a failure analysis every single failure. So we failed differently again and again and again. And we told our board, you know, we met with our board every six weeks and yeah, this is the strategy. Nobody's ever done this before. Uh this is what we're going to do. And we had to invent new materials. We had to invent new techniques. We uh ended up building things that that everybody else had partners who could do. But in August of 2019, we announced we had solved it. And it'll my co-founders and I the first time it worked it was sitting in a tiny little lab and we couldn't believe it. We were the first few things that treated me to make one work. And we just stared at, you know, watching a server run is about as exciting as watching paint dry. And there we were, the five of us just staring at this machine, not believing might have worked. We made it work.

</details>

### IPO 的情感意义与新的起点

**Speaker B**: 哇。那……这个时刻，跟敲钟上市的那一刻比起来，哪个意义更大？还是说这两种情感完全不同？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Um was it was it a bigger moment that actually ranging the bell or that just completely different like emotionally?

</details>

**Speaker A**: 从情感上来说，这是完全不同的两码事。前者是因为我们将自己的想法变为了现实，我认为特别是对于深科技的创始人来说，你脑海深处总会有个声音在嘀咕，也许这……对吧？也许我们真的是疯了。

<details>
<summary>Original English</summary>

**Speaker A**: Emotionally it it was a completely different thing. Um it it was that we had made our idea work and I think for deep tech founders in particular um there's always this little thing in the back of your mind that says maybe it's right? Maybe we're actually crazy.

</details>

**Speaker B**: 没错。也许它肯定会失败，也许它根本行不通。可能我会没时间了，也许我们的钱要烧光了。也许，也许，也许。

<details>
<summary>Original English</summary>

**Speaker B**: That's right. Maybe it's no fail and maybe it's not going to work. And uh maybe I don't have time. Maybe we're going to run out of money. Maybe maybe maybe.

</details>

**Speaker A**: 而与这种焦虑相对的另一面，就是无与伦比的喜悦。因为这些是我的联合创始人们的想法，我是说，这是他们的想法在这个世界上的具象化，这是非常不可思议的——当某个人的想法具有了物理形态。接下来的阶段是，当你看到其他人的工作建立在你的想法之上，那你就知道你是真的热爱构建基础设施。所以当我们今年 5 月 14 日敲钟上市，完成半导体历史上最大规模的 IPO 时……我们做了一件不寻常的事。我们邀请了从一开始就陪伴我们的所有工程师，邀请了所有在我们这里工作超过 9 年的员工，以及他们的家人，我们所有人一起敲响了上市的钟声。我们全都登上了舞台。我是说，那是一种不同类型的骄傲，一种“我们共同完成了这件事”的骄傲，而且，真希望我没在某个时候挂掉，因为创业这事儿——大家是很诚实的，只是他们不会告诉你这些——但我们避免了一些致命的失误。我们犯了很多错，但避开了那些足以致命的错误。我们成功存活下来，达到了一定程度的成功，这让我们有机会去追求一个更高层次的成功。这就是 IPO 的意义。它不是终点，而是你到达了一个新的平台期，在这里你可以在公开市场上追逐更高层次的成功。我必须承认，那感觉相当棒。

<details>
<summary>Original English</summary>

**Speaker A**: And the flip side of that is the joy that that this was my co-founder's ideas. I mean these are their ideas manifest in the world and that is an extraordinary thing is when someone's ideas take physical shape and then the next step is when you watch other people's work sit on top of your idea then you know you love making infrastructure and so when we rang the bell and we went public on May 14th uh this year in the largest semiconductor IPO about history. Um what and we did something unusual. We invited all our engineers who'd been with us since the start. Everybody who'd been with us more than nine years and their families and we all rang the bell together. We all got up on stage. I mean that was sort of a moment of of a different pride that that that we had done this together and that uh wish I'd managed not to die at some time but it started up you know people are donest they don't tell you that but we we'd avoided some we'd made plenty of mistakes but we've been avoided the fandle ones and we we made it crew to a level of success that gave us the opportunity to to pursue a new level of success. That's what an IPO is. It's not the end. It's you've gotten to a plateau that you can chase a new level of success in the public market and and that felt pretty good, I'll admit.

</details>

### 构建大芯片的技术权衡与故障模式管理

**Speaker B**: 太了不起了。非常棒。谢谢你的分享。那么我们再深入探讨一些关于产品和技术方面的东西。制造一个更大的芯片，需要做哪些权衡呢？首先跃入脑海的一个问题就是——故障模式（failure mode）。

<details>
<summary>Original English</summary>

**Speaker B**: Amazing. Amazing. Thanks for sharing. Um so just and then go a little deeper on some of the product and and technical stuff. Um so uh what are the tradeoffs uh of building a bigger chip? One that may come to mind is uh failure mode.

</details>

**Speaker A**: 当然。

<details>
<summary>Original English</summary>

**Speaker A**: Sure.

</details>

**Speaker B**: 如果你在一个大晶圆上分布着很多小芯片，你可以隔离出有问题的地方。但如果你把它做成一个整体的大芯片，那么所有东西岂不是会同时失效？

<details>
<summary>Original English</summary>

**Speaker B**: Uh if you have a lot of little chips on a big wave for prison where you can isolate the problems. Yeah, if you have a big one, then everything won't fail in the same time.

</details>

**Speaker A**: 是的，所以你必须极其谨慎地考虑故障模式。为此，我们发明了一种技术，芯片上包含大约一百万个相同的模块（tiles）。如果其中一个坏了，我们可以把它关闭，然后启用备用模块继续运行。所以如果你要把芯片做大，就必须在计算机最底层的架构中考虑如何管理故障。我的意思是，GPU 的故障率其实是极高的。我相信你们肯定讨论过这个。早期失效（infant mortality）比例非常大，而且它们总是会出故障。有很好的数据支持这一点。Facebook 就发表过一篇论文，统计了他们在大型集群中遇到的故障数量。现在，我们能够采取一些其他手段，因为我们把所有的算力都集中在了一个点上，所以我们可以投入更多的资源来为其散热。于是我们在 AI 系统中首创了水冷技术，我们让这些芯片运行在比 GPU 低得多的温度下。而在电子产品中，最主要的故障诱因就是温度。因此，通过在更低的温度下运行，我们的芯片更加可靠，这成了一个优势。但话又说回来，我们不得不推进技术边界，才能解决怎么给这么大一块芯片散热的问题。

<details>
<summary>Original English</summary>

**Speaker A**: So, you have to think very carefully about failure mode and and we invented a technique that had about a million identical tiles and if one fails, we can shut it down and we can use a redundant one and keep going. And so if you're going to go big, you have to think about in the very architecture of the computer how you're going to manage failure. I mean the JPEGs have a huge failure rate. So I'm sure you guys have spoken about this. Infant mortality is enormous and they fail all the time. There's good data. Facebook put out a paper on the number of failures they get in a big cluster. Now we can do some other things be because we have all this compute in one spot uh we can uh invest more to cool it. So we pioneered water cooling uh in AI systems and we run these much colder than GPMs and the failure mode in electronics is temperature and so by running them colder we are more reliable and so that was from an advantage but again we had to advance the technique to to to cool off a chip this big.

</details>

**Speaker B**: 是的。所以我认为我们有一种系统性的思维方式，对吧？如果你打算做一件大事，你就必须做出权衡，并且你必须要考虑一种能够容纳冗余和修复的架构。你必须去思考——

<details>
<summary>Original English</summary>

**Speaker B**: Yes. And so I I think we we have a a systemal mentality, right? If you're going to do something big, you've made tradeoffs and you have to think about an architecture that allows for redundancy and repair. You have to think

</details>

<!-- chunk 5/7 -->

### 架构与速度的本质

**Speaker A**: ……关于架构各个方面的优缺点，呃，这就是你如何做出与众不同的新东西的途径。

<details>
<summary>Original English</summary>

about the pros and cons of every aspect uh of the architecture and and that's how you do something different and new.

</details>

**Speaker B**: 好的。再次强调一下这个重点，呃，为了确保观众能从这次对话中，我猜，获得清晰的结论。所以，请向我解释一下，就像我不是五岁，而是十五岁那样。呃，为什么这比 GPU 更快？从根本上说，是什么让它更快？（注：原文字幕存在口误或听写错误，“what country is super fast with a GPA”）。

<details>
<summary>Original English</summary>

Okay. and and again just to drive the the point home um to make sure there's I guess clear takeaway you know for people from from this conversation. So explain it to me like I'm maybe not five but 15. Uh why is this faster than a GPU? Like what fundamentally makes it faster and what country is super fast with a GPA?

</details>

**Speaker A**: 在推理中生成 token（标记）的方式就是它在推理中生成一个词更快的原因，而我们的回答是一整串词。它可能是代码，也可能是像素，但我们统称它们为词。具体来说，模型的权重从内存转移到计算单元，进行一次计算，这就生成了这个词。

<details>
<summary>Original English</summary>

How tokens are generated in inference is why it's faster in a in an inference to generate a word and our answers are a whole stream of words. It can be code. It can be pixels but call them words. Talk the weights of the model are moved from memory to compute a calculation occurs and that generates the word.

</details>

**Speaker B**: 这是预填充（prefill）还是解码（decode）阶段？

<details>
<summary>Original English</summary>

Is a prefill versus decode.

</details>

**Speaker A**: 这两个步骤都是。

<details>
<summary>Original English</summary>

That is both steps.

</details>

**Speaker B**: 好的。也许您可以解释一下什么是预填充和解码。

<details>
<summary>Original English</summary>

Okay. And you want to maybe explain what prefill and decode are.

</details>

**Speaker A**: 好的。进行推理所需的计算有两个步骤。当你在 ChatGPT 中输入，呃，向我解释这个村庄在二战前的历史，然后它把答案呈现给你。此时发生了两件事。第一件事是你的提示词（prompt）已被处理。这是第一步。第二步，生成了你的回答。生成回答的过程称为解码（decode），懂了吗？解码是顺序进行的。处理你的提示词，我们称之为预填充（pre-fill），是可以并行化的。因此你可以同时处理许多提示词。但是，你获得回答的速度取决于解码，它必须一步一步、按顺序进行，这一点无法改变。而你执行这一步的方式，就是将代表模型智能的权重，转移到计算单元来生成一个词。你进行一次计算，得到一个词，然后这个词被用于生成下一个词，此时权重会再次转移到计算单元。因此，这是一个将权重从内存不断移动到计算单元的过程。那么，在一个小型模型——比如一个拥有 700 亿参数的模型——中，权重有多大呢？这些权重的大小大约相当于 100 部高清电影。所以，为了生成一个词，你必须将 100 部高清电影级别的数据从内存移动到计算单元，然后为了生成下一个词，你必须再移动它们一次。

<details>
<summary>Original English</summary>

Okay. There are two steps in uh the computation necessary to do inference. When you type in the chat GPT uh explain to me the history of this village prior to World War II and it came to you. Two things have happened. The first thing is your prompt has been processed. That's step one. And step two, your answer has been generated. And the way your answer is generated is called decode. Okay? And decode is sequential. Processing your prompt, which we call pre-fill, can be paralyzed. So you can process many of them simultaneously. But the speed with which you get an answer is a function of the decode and it is step by step by step in sequence and that can't be changed. And how you do that step is you move weights which are the intelligence from the model to compute to generate a word. You do a calculation and you get a word and then that word is used to generate the next word where weights are moved from compute. So the process is one of moving weights from memory to compute. So well how big are the weights in a little model like a 70 billion parameter model. The weights are about the size of 100 HD movements. So to generate a single word, you move a 100 HD boogies from memory to compute and then you have to move them again for the next word.

</details>

**Speaker B**: 而且你要把这个过程重复一千次，才能得到一个好的回答。一个一千个词的回答。

<details>
<summary>Original English</summary>

And you want to do this a thousand times to get a good answer. A thousand word answer.

</details>

**Speaker A**: 这就是 HBM（高带宽内存）慢的地方。正是这个特定步骤，HBM 显得很慢。而在这个步骤中，由于我们把所有的 SRAM 都放在这里，我们的速度快得惊人。因此，将权重移动到计算单元的速度在这里大约比在 GPU 上快了两千五百倍。这就是我们在这里所能做到的本质，也是为什么它会快这么多的原因。

<details>
<summary>Original English</summary>

This is where HBM is slow. This exact step is where HBM is slow. And that exact step, it is where by having all the SRAMM here, we're blisteringly fast. And so the speed of moving weights to compute is about two and a half thousand times faster here than on a wen GP. And so that's the essence of what we've been able to do here and why it's so much faster.

</details>

**Speaker B**: 是的。太吸引人了。你认为模型需要、将会需要，或者也会在那个快速的 AI 世界中演进吗？还是说那只是个问题？

<details>
<summary>Original English</summary>

Yeah. Fascinating. Do you think that models need will need need or will evolve as well in that fast AI world or is that just a problem?

</details>

**Speaker A**: 不。完全正确。因为请记住，正在发生两件事。第一，我们希望模型变得更聪明；第二，模型变聪明的方法之一是使用强化学习（RL），而 RL 在训练内部使用推理，对吧？所以，你在训练内部进行推理的速度越快，你的训练速度就越快。

<details>
<summary>Original English</summary>

No. Exactly. Because remember two things are happening. One we want the models to be smarter and two one of the ways models are getting smarter is with RL and RL uses inference inside of training, right? And so the faster you can do the inference inside of training, the faster you're training.

</details>

**Speaker B**: 我很感兴趣。这对你们来说是个市场吗？

<details>
<summary>Original English</summary>

I'm interesting. Is that is that a market for you guys in

</details>

**Speaker A**: 对我们来说，那也是一个市场。

<details>
<summary>Original English</summary>

that's a market for us as well.

</details>

**Speaker B**: 所以你们不只是涉足——我们做强化学习，我们也做传统的模型训练（注：字幕误作 trading）。不是为最大的实验室的最大型模型服务，而是为下一个梯队服务。

<details>
<summary>Original English</summary>

So you're not just in we do RL and we do traditional trading too. Not for the largest models for the largest uh labs but for the next tier.

</details>

**Speaker A**: 嗯哼。对于预训练（注：字幕作 pre-trading），对于纯粹的预训练。

<details>
<summary>Original English</summary>

Uhhuh. for pre-trading for pure pre-training

</details>

**Speaker B**: 粗糙的训练，呃，微调，全套的。所以如果你做，呃，预训练，我是说使用强化学习的后训练，为其他实验室做一些预训练，嗯，我的意思是，GPU 在哪些工作上仍然比你们更好？

<details>
<summary>Original English</summary>

crude trading uh fine-tuning full set. So if you do uh pre-training I mean post training with RL some pre-training for the other labs um what I mean GPUs are still better than you for what job that

</details>

### 分布式计算与推理优化

**Speaker A**: 那么，GPU 在训练中面临一些挑战，这些挑战目前已经被社区中极少数的一部分人解决了。GPU 是一个非常小的芯片，而我们在训练中需要做的计算量非常大。训练中最复杂的部分之一就是把计算拆解，并将它们分散到多个 GPU 上，这被称为分布式计算。在历史上，这一直是超级计算领域的专属，而且这非常困难，不仅仅是因为破解一个问题并让很多人一起解决它很难，还因为它们必须不断地共享信息。正是为了这种信息共享，他们才需要收购 Mellanox，对吧？他们需要控制一个架构，通过它来进行所有的信息共享，从而得出一个答案。那种拆分，呃，一个大型矩阵乘法，一个大型计算的过程被称为运行张量模型并行（tensor model parallel）。你把张量拆解，然后把它分散开来。世界上最顶尖的实验室擅长这个，但其他人都做不到。当我们在进行训练时，我们不需要以那种方式运行。我们运行的是所谓的数据并行（data parallel）。数据并行非常简单。所以，它允许那些本身很优秀、非常优秀的团队能够快速在训练中测试各种想法。因此我们更容易使用，速度也更快，呃，因为我们允许他们使用一种简单得多的技术。

<details>
<summary>Original English</summary>

so GPUs in trainings have some challenges that have been solved by a very narrow selections of the community GPU is a very small chip and the calculations that we need to do in trading are very large and one of the most complicated parts of training is the breaking up the calculations and spreading them apart on multiple GPUs and that's called distributed compute that has historically been the domain of the supercomput world and is very difficult ult not just because cracking a problem and having lots of others work on it is hard but they have to constantly share information and that sharing information is why they needed to buy Melanox right is they needed to control a fabric over which all this sharing in order to get an answer would happen that breaking up the a big matrix multiply a big calculation is called running tensor model parallel You are breaking up the tensor and spreading it apart. And the best labs in the world are good at that, but nobody else is. They when we run training, we don't have to run that way. We run what's called model par data parallel. And data parallel is very simple. And so it allows teams who were good and very good to quickly test ideas in training. And so we are easier to use and faster um because we allow them to use a technique which is much simple.

</details>

**Speaker B**: 让我们谈谈代理（agentic）的世界，也许从推理（reasoning）开始谈起。嗯，我想我看到过一篇博客文章，文章里嗯，你们指出推理并不总是所有问题的正确解决方案。你们是如何看待这个问题的，以及它在服务世界中扮演什么角色？

<details>
<summary>Original English</summary>

Let's talk about the enentic world maybe starting with with um with reasoning. Um I think I saw a blog post where um you guys have given stated that reasoning was was uh not always the the right solution for all problems. Like how do you how do you think about this and where does that fit in service world?

</details>

**Speaker A**: 我们把推理作为一种技术，嗯，有点像，呃，当你在上八年级的时候，你写论文会打几遍草稿。呃，在单次推理（single shot inference）中，你输入一个查询，就会得到一个答案。理解推理最简单的方式就是把它想象成你要写几遍草稿。它会把问题拆解开来。它会按步骤来解决问题。它会把结果综合起来。它会评估结果。它会改进结果。然后它才会给你一个答案。所以这将花费更多的计算资源。如果你的计算机很慢，那就不只是让人恼火而已了。那将会是致命的慢速。因此，由于目前最好的模型——所有的模型，无论是国内的还是中国的（注：原文指不同国家或厂商的模型），无论是 OpenAI 还是 Anthropic 或者 Gemini，无论你是任何一种中国模型——它们都转向了推理路径。但这也就意味着在推理期间会使用更多的计算资源。这对我们来说是一个巨大的优势，因为我们的速度更快，它让 GPU 的迟钝愈发凸显，也让我们的速度优势变得更加显著。所以这对我们来说是天大的好事。我们认为这，呃，将会作为目前运行这些模型方式的一个核心本质保留下来。

<details>
<summary>Original English</summary>

We're using as a technique um a little bit like uh when you were in 8th grade and you wrote different drafts of the paper. um single shot inference. You you get an you you write a query, you get an answer. It the easiest way to think about reasoning is you're going to do several drafts. It's going to break the problem up. It's going to solve it in parts. It's going to bring them together. It's going to review the results. It's going to improve the results. And then it's going to give you an answer. And so that is going to take more compute. And if your computer is slow, that's going to be a more than an irritant. That could be crippling speed. And so as the best models, all of them, whether they're domestic or Chinese, whether you're uh uh open AI or anthropic or Gemini, whether you're any of the Chinese mod, they all move to a reasoning approach. But that meant more compute was being used during inference. That was a huge advantage for us because we were faster and it made the GPU slowness stack up and it made our speed have an even bigger advantage. And so this was a huge bone for us. We think this is uh going to stay as a fundamental essence of the way these models are are are run right now.

</details>

**Speaker B**: 你还写过关于，嗯，验证（verification）的文章，呃，以及是否，嗯，代理中的瓶颈究竟是推理能力不够好、不够聪明，还是存在验证方面的问题。

<details>
<summary>Original English</summary>

And you also wrote about um verification uh and whether um what was uh the bolt bottleneck in uh agents was whether the reasoning was good enough, whether they were smart enough or whether there was a verification problem.

</details>

**Speaker A**: 当然。我，我认为验证问题，呃，有点像护栏（guardrail）问题。嗯，呃，你想做的是在你写了两到三遍回答的草稿之后，你会想要确保它没有错。这就是你的验证步骤。你或许可以用一个不同的模型来做这件事。你可以通过用另一种方式向现有模型询问类似的问题来做到这一点。对吧？所有这些都是你对结果进行压力测试的方法。嗯，护栏呃，可以以同样的方式工作，对吧？你想要检查，呃，无论是用一个模型还是用其他技术，通过一种评分机制，来确保这个问题没有越界。确保这个回答不是关于如何制造生物武器，或者调用了某些信息，那些，那些你应该直接向 FBI 报告的信息，对吧？嗯，所有这些都需要计算时间。所以，不管你是在试图通过推理来提升效果，还是在通过追求速度来运行护栏机制，好吧，你都可以在更短的时间内得到结果。

<details>
<summary>Original English</summary>

Sure. I I think the the verification problem uh is a little bit like the guardrail problems. Um and uh what you'd like to do is after you have written two or three uh drafts of your answer, you would like to be sure that it wasn't wrong. And that's your verification step. And you can do that maybe with a different model. You can do that by asking your existing model a similar question in a different way. Right? All of these are ways you you can pressure test your result. Um, guard rails uh can work the same way, right? You want to review uh either with a model or with another technique through a scoring mechanism that this question isn't out of line. that this answer isn't about how to make biological weapons or calling upon information that that that you are direct to the FBI, right? Um, and all of that takes compute time. And so whether you're trying to improve uh through reasoning or whether you're running guard rails by being faster, all right, you can get results in less time.

</details>

**Speaker B**: 嘿，那么你认为目前为代理服务的世界正在向什么方向发展呢？是一堆小型模型以更快的速度运行以进行更多验证，还是依靠一个大型模型？

<details>
<summary>Original English</summary>

Hey, so what do you think the world is evolving for agents? Is it a bunch of smaller models running faster doing more verification versus a large model?

</details>

**Speaker A**: 好吧，我认为两者是协同工作的。我认为大型模型产出一个答案，然后你想加倍，你只是想检查你的数据。我的意思是，在新闻行业，人们写文章会有事实核查员，对吧？会有人去确认，追溯以往，记者会检查数据，或者有一个专门的数据核查员，对吧？那是一项专门的工作。每一项声明都会被独立核查。嗯，这是一种不同的模式，对吧？主导模型负责撰写——

<details>
<summary>Original English</summary>

Well, I think those work together. I think your big model produces an answer. And then you want to double you just want to check your data. I mean in in the journalism industry people would write papers that have data checkers, right? Somebody would go and make sure back in the world journalist check data be a data checker, right? That was a job. Each claim was checked independently. Um that's a different model, right? The made model wrote

</details>

<!-- chunk 6/7 -->

### 多模态模型与计算资源

**Speaker A**: ……这部分，然后用一个小模型检查了一些答案。而且呃，我认为这是一个非常、非常好的处理方法。

<details>
<summary>Original English</summary>

**Speaker A**: the piece and then a little model checked some of the answers. And uh I think that's a very a very good way to go about it.

</details>

**Speaker B**: 对于更大的模型来说，多模态（multimodality）在你们的世界里处于什么位置？

<details>
<summary>Original English</summary>

**Speaker B**: Where does a multimodality uh for the larger models uh falling in your world?

</details>

**Speaker A**: 嗯，我们刚刚算是宣布了，在谷歌的一款多模态模型上，我们是全球速度最快的。我认为事实是，很少有文本是不包含图表和图形的，对吧？你必须在理解文本的同时，能够理解插图、图形和图表，所以那算是最开始也是最简单的部分，然后你应该能够生成这两者，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: Well, we just announced uh uh sort of that we were fastest in the world on on one of Google's multimodal models. I I think the truth is is that there's very little text that doesn't have charts and graphs, right? you you you must to understand text uh be able to understand uh illustrations, graphs, uh charts and so that that's sort of the the first and easiest part and then you ought to be able to create both right

</details>

**Speaker B**: 并且接下来你还得能理解图像，而且，我认为新模型在这方面显然已经非常非常优秀了。在那之后顺理成章的就是视频，因为视频不过就是图像的集合。嗯，但是这在当下需要耗费庞大惊人的计算量，这也是它被头部实验室暂时搁置的原因之一，因为它的计算密集程度高得令人难以置信。

<details>
<summary>Original English</summary>

**Speaker B**: >> and then you ought to understand images and uh I I think the the new models are very very good at that obviously What follows that is video because uh a video is just a collection of images. Um but that takes an enormous amount of compute right now and that's one of the reasons it's been sort of set aside by the leading labs being so unbelievably mutation intensely.

</details>

### 服务器、数据中心与云业务

**Speaker B**: 太棒了。让我们稍微聊一下服务器业务，因为你们显然是芯片提供商，正如我们所讨论的，你们也是云服务提供商、数据中心提供商。那么不同的业务部分到底有哪些？

<details>
<summary>Original English</summary>

**Speaker B**: >> Great. Um let's talk about the server business a little bit u because so you guys obviously uh chipmaker provider as we discussed you're also uh a cloud provider data center provider what's uh so what are the different parts

</details>

**Speaker A**: 我们制造计算设备，并且这种为 AI 优化的计算设备是全球做 AI 计算最快的。如果你有数据中心，我们会把硬件卖给你，部署在你的数据中心里；如果你没有数据中心，并且你想按月或按年租用，我们也有数据中心。所以你可以通过我们的数据中心以及我们的云服务来租用我们的设备。

<details>
<summary>Original English</summary>

**Speaker A**: we we make compute and that computes optimized for AI is the fastest at AI in the world if you have a data center we will sell you hardware for deployment in your data center if If you don't have a data center and you'd like to rent it by the month for the year, we have data centers. They have so you can rent our uh our equipment through our data centers and through our cloud.

</details>

**Speaker B**: 这样一来，你们既能吸引 AI 原生企业，也能吸引大型跨国企业和政府客户。那么目前的销售比例是怎样的？

<details>
<summary>Original English</summary>

**Speaker B**: >> And so that allows us to get uh AI natives as well as large enterprises and and governments. And what's the

</details>

**Speaker A**: 去年是一半对一半（50:50）。呃，我认为上个季度可能是，或者是 75:25，偏向于硬件销售。我认为今年可能会是 50/50，而随着我们 OpenAI 的合作持续，到 2026 年（注：录音转录疑似口误 2012，此处保留语义连贯），可能将会变成 30:70，其中 30% 是在本地部署硬件，70% 在云端。

<details>
<summary>Original English</summary>

**Speaker A**: >> it was 5050 last year. Uh and I I think this last quarter it was or maybe maybe 7525 in favor of of hardware sales. I I think this year it might be 50/50 and as our open AI deal continues 2012 it will probably be 3070 with 30 on premise deployments of hardware at the 7D cloud.

</details>

### 重大合作与电力容量约束

**Speaker B**: 很好。让我们来谈谈那项激动人心的合作，因为它简直是一个创造历史纪录的重大里程碑。嗯，所以，它提供高达 750 兆瓦的规模——顺便说一下，用兆瓦（megawatt）作为一个衡量指标很有意思，因为作为一家芯片供应商，这实际上衡量的是电力。所以，这是某种缩写吗？

<details>
<summary>Original English</summary>

**Speaker B**: Great. Let's talk about that operating ideal since it's such like a major historical milestone record making. Um, so it's it's providing up to 750 megawatt >> megawatt which is which is interesting by the way as a as a metric because a chip provider but this is power. So is that short of hand for

</details>

**Speaker A**: 它是某种缩写。我的意思是，事实证明现在情况就是如此，而且我们之前没有讨论过这个问题，因为在相邻的供应链中，我们经历了内存短缺，经历了名为 CoWoS 3纳米产能的短缺，而现在我们行业的另一个限制因素是数据中心的可用性。我的意思是，这对所有人来说都是一个限制因素，这就是为什么 Anthropic 为了获取数据中心容量，与埃隆（Elon）达成了一项非常昂贵的巨额交易。我们与 OpenAI 的交易，就是因为数据中心容量是一个制约性限制，而数据中心就是用兆瓦（megawatts）来衡量的。这项交易是 760 兆瓦：在 2026 年的多年期租赁中提供 250 兆瓦，2027 年的多年期租赁中再增加 250 兆瓦，以及 2028 年的多年期租赁中提供额外的容量。

<details>
<summary>Original English</summary>

**Speaker A**: it's a shortand I mean it turns out right now and we didn't talk about this because there's sort of in the adjacent supply chain we we went through the shortage of of memory we went through the shortage of a process called co-ass 3 nanometer capacity the the other limitation in our industry right now is data center availability and I mean uh that is a limiting factor for everybody and that's why anthropic did a huge which is in sort of very expensive deal with Elon um for data center capacity. Um uh our deal with them with uh with open AAI was because data center capacity is a limiting constraint measured the way data centers are measured in in megawatts. The the deal is 760 megawatt, 250 megawws in 26 uh on a multi-year lease, an additional 250 megawatts in 27 on a multi-year lease and an additional in 28 and multi-year lease.

</details>

**Speaker B**: 那么，是你们为他们建设数据中心，还是你们只提供放在数据中心里的芯片？

<details>
<summary>Original English</summary>

**Speaker B**: >> And you're doing the data center for them or you providing the chips that go in the data center?

</details>

**Speaker A**: 是为他们提供数据中心。我们将交付一个完整的云解决方案。所以他们基本上只需要通过 API 连接到我们这里。

<details>
<summary>Original English</summary>

**Speaker A**: >> Data center for them. We're delivering a full cloud solution. So they connect to us via an API >> basically.

</details>

**Speaker B**: 想象一下 2026 年，我立刻觉得，那就是——

<details>
<summary>Original English</summary>

**Speaker B**: Imagine 2026 do I immediately that's >>

</details>

**Speaker A**: 我正在寻找数据中心，我的下一个会议就是和一家数据中心提供商开，我们现在在欧洲有很多动作。

<details>
<summary>Original English</summary>

**Speaker A**: I I am looking for data centers my next meeting he's in with a data center provider we're doing a lot in Europe right now

</details>

**Speaker B**: 哦，有意思。

<details>
<summary>Original English</summary>

**Speaker B**: >> oh interesting >>

</details>

**Speaker A**: 在北欧地区（Nordics）有很多。

<details>
<summary>Original English</summary>

**Speaker A**: a lot in the in the Nordics >>

</details>

**Speaker B**: 那是因为那里更靠近能源吗？

<details>
<summary>Original English</summary>

**Speaker B**: is that uh because it's closer to power sources >>

</details>

**Speaker A**: 是的，因为那里有低成本的电力，清洁且低成本的电力。

<details>
<summary>Original English</summary>

**Speaker A**: yes it's because uh there is low cost power on that clean lowcost power. >>

</details>

**Speaker B**: 是的。低成本。呃，就像在他们时间敏感的业务中一样，数据中心所处的位置，就花销而言重要吗？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Low cost. >> Does it matter uh just like in their time business where the data center is is uh is located in terms of >> um spend. >>

</details>

**Speaker A**: 是的。还有一种额外的延迟叫作传输延迟（transport latency），也就是光在光纤中从赫尔辛基传输到纽约的速度，如果你的客户在纽约而你的数据中心在赫尔辛基，你必须把这一点考虑进去。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. There is an additional latency called transport latency and that's the speed of light through fiber to get from Helseni to New York and you have to account for that if your customers in New York and your data center is in Helsinki.

</details>

**Speaker B**: 好的。

<details>
<summary>Original English</summary>

**Speaker B**: Okay.

</details>

**Speaker A**: 我的意思是，这速度大约是光速的三分之二，人们总是很好奇这需要多长时间。嗯，你会希望数据中心都在相同的平台上。

<details>
<summary>Original English</summary>

**Speaker A**: I mean it's usually about 2/3 the speed of light being curious how long it takes. Um uh you would like data centers on the same kind of platforms. >>

</details>

### AWS合作与解耦架构

**Speaker B**: 那是与 OpenAI 的合作。与 AWS 也有一个非常激动人心的合作，你们提供了一个混合芯片解决方案。

<details>
<summary>Original English</summary>

**Speaker B**: That's the open ideal. Uh there was an exciting deal with AWS as well where you uh it's a it's a code chip solution. >>

</details>

**Speaker A**: 没错。这就是你之前提到的解耦解决方案（disaggregated solution），他们的芯片组件负责预填充（prefill），也就是处理可并行化的步骤。那是 Trainium 芯片负责预填充步骤，而我们的芯片负责解码（decode），这样你就能以极快的速度获得多得多的 token。

<details>
<summary>Original English</summary>

**Speaker A**: That's right. It's the disagregated solution you mentioned before where their panium part is doing the prefill and is doing the paralyzable step. So that's tranium that's trium is doing the the prefill step and our chip is doing the decode and so you get a lot more bullet streamly fast tokens. >>

</details>

**Speaker B**: 这对我们来说是一笔很好的交易。它使用的是他们的数据中心。所以这些都是在 AWS 数据中心内部署的。这非常吸引人，对吧？谈论这个行业的时候，似乎灵活性是如此重要。就像交付解决方案一样：你需要芯片，你就得到芯片；你需要数据中心，大家就从不同的供应商那里购买以减少依赖。

<details>
<summary>Original English</summary>

**Speaker B**: It's a good deal for us. It uses their data centers. So these are deployments in the AWS data center. Yeah, it's fascinating, right? Like talking about this industry is how it seems that uh flexibility is so important. This just like delivering the solution like you need chips, you get chips, you need data centers, everybody's buying from different suppliers to reduce dependency.

</details>

**Speaker A**: 我认为，我们之所以从传统的芯片系统提供商转变为同时提供数据中心，原因之一就是：这正是我们的客户想要的，或者是为了极速生成 token，我们能做的任何让交付极速 token 变得更容易的事情，我们都会去做。对一些客户来说，这发生在他们的数据中心里；对另一些客户来说，这是通过 API 提供服务。只需将你的流量指向我们，我们就会在后端用快速生成的 token 像消防水龙一样喷涌回应。

<details>
<summary>Original English</summary>

**Speaker A**: I I think that's one of the reasons why we we went from being a traditional chipping system provider to also offering data centers is that what what our customers want or fast tokens and anything we can do to make the delivery of fast tokens easier. For some of them that's in their data center. For some of them it's with an API. just point your traffic to us and we'll point the fire hose with a fast token in the back. >>

</details>

### 云服务产品矩阵

**Speaker B**: 是的。只是为了了解一下在云版本上，你们从哪里开始，到哪里停止，或者提供什么、不提供什么，至少目前的情况是怎样的。如果我想运行 Kimi，就像我知道你们在速度方面对 Kimi 和 Gemma 有令人难以置信的统计数据，必须得提一下。但是你们不把这些作为服务来运行，还是你们有在做？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And just to get a sense for where where where you start and where you stop on you or do not or at least currently provide the the the cloud version. So if I want to run Kimmy like I know you have like incredible stats for Kiwi and Gemma in the speed feel to mention them. Um but you don't run those as a service or do you do? >>

</details>

**Speaker A**: 我们有提供。

<details>
<summary>Original English</summary>

**Speaker A**: You do.

</details>

**Speaker B**: 好的。所以你们有一项服务在与 BaseTen 和 Fireworks 竞争。

<details>
<summary>Original English</summary>

**Speaker B**: Okay. So you have a service competing with the base stands and fireworks. >>

</details>

**Speaker A**: 是的。我认为，嗯，我们有一个按需服务，你可以来到我们的网站然后预订一个月。我想你甚至可以为 Kimi 或 GLM 或者这些模型中的一些购买 token 额度包。我们的很多客户来到那里，对此感到兴奋，然后就转向了专属的供应方案，在证明了这能给他们的工作带来切实利益之后，他们会租用数百台机器一年、两年、三年或四年。他们经常进行 A/B 测试。不出所料，人们都更喜欢速度快的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I I think um we have a an on demand service um where you can come to our site and and book a month. I think you can even buy buckets of tokens for for Kimmy or GLM or some of these models. Um uh many of our customers come there, get excited about it and then move to a dedicated offering >> where they take hundreds of machines for a year or two or three or four um once they've proven out the um the benefit for them in their work. Often they do AB tests. Not surprising. People like faster. >>

</details>

**Speaker B**: 好的。所以那里只是更像一个测试环节。

<details>
<summary>Original English</summary>

**Speaker B**: Okay. So So we're just more like a testing. >>

</details>

**Speaker A**: 这是一个完整的环境。

<details>
<summary>Original English</summary>

**Speaker A**: It's a full environment.

</details>

**Speaker B**: 好的。

<details>
<summary>Original English</summary>

**Speaker B**: Okay.

</details>

**Speaker A**: 嗯，你可以去使用它。网址是 three.ai。去玩玩看。

<details>
<summary>Original English</summary>

**Speaker A**: Um you can you can go and use it. It's at three.ai. Play around. >>

</details>

**Speaker B**: 这很吸引人。但这可能会演变成另一个庞大的云业务。好吧，所以你们有芯片，你们有数据中心，并且你们在前端还运行着一个云业务，这非常引人瞩目。

<details>
<summary>Original English</summary>

**Speaker B**: But fascinating. But that could become like yet another big cloud business. Okay. So you have chips, you have data centers, and you have a cloud business running in front on its fascinating. >>

</details>

### AI时代的护城河之争

**Speaker B**: 考虑一下商业护城河，众所周知，英伟达拥有 CUDA 这一被广泛讨论的护城河。你们对应的护城河是什么？

<details>
<summary>Original English</summary>

**Speaker B**: Um thinking about modes, so you know famously um Nvidia has cuda as well discussed mode. What's your equivalent? Yeah. >>

</details>

**Speaker A**: 好了，我不认为我们非得拥有 CUDA。我们应该谈谈这个。

<details>
<summary>Original English</summary>

**Speaker A**: Well, I don't think we must >> Korea. We we should talk about that. >>

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yep. >>

</details>

**Speaker A**: 我认为两年前，每一个最先进的模型都是在 CUDA 工作流中训练的。而现在，Gemini 的训练没有使用 CUDA；Anthropic 的 Claude 训练没有使用 CUDA；OpenAI 的训练使用了 CUDA。所以在一两年的时间里，他们失去了 70% 的模型训练份额，或者说最先进模型的份额，因为 Gemini 是在 TPU 上训练的，它极其先进。Anthropic 是在 Trainiums 上训练的，所以我认为关于那条护城河的说法依然存在，但数据表明这条护城河显然正在缩小。而在推理（inference）领域并没有护城河。在云端，把你从 GPU 转移到我们这里只需要敲击八次键盘。

<details>
<summary>Original English</summary>

**Speaker A**: I think two years ago uh every uh state-of-the-art model was trained in a CUDA flow and right now Gemini is trained without CUDA. Enthropic cloud is trained without CUDA. Open AI is trained with CUDA. So in a one or two year period they lost 70% share >> of training models or is the state-of-the-art um because uh Gemini is trained on TPUs it's very out of uh anthropic is trained on craniums and so the I think the the storage of the boat is still present where the data show the mode is clearly shrinking. Um there's no mode in inference. >> Uh it takes you eight keystrokes to move from a GPU to us in the cloud. >>

</details>

**Speaker B**: 只有八次按键吗？

<details>
<summary>Original English</summary>

**Speaker B**: It is eight. >>

</details>

**Speaker A**: 哦，就是这样。为了将你的流量从 GPU API 转移到我们这里。所以，显然，CUDA 在我们行业的创立过程中，以及在使图形处理变得比仅仅处理图形更加通用方面，具有极其重要的意义。但从 2023、2024 年开始，我认为它作为一道持久护城河的能力已经受到了实质性削弱。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, that's it to move your traffic from uh GPU API to us. And so uh obviously Cuda was sort of enormously important in the creation of our industry and in allowing the the graphics processing here to be more general than graphics processing but since 23 24 live I think it's ability to serve as a durable mo substantion >>

</details>

**Speaker B**: 当你们思考你们的护城河时，你们是否拥有一个完整的生态系统战略？就任何护城河可以存在于这个行业的程度而言，就像你们建立了一个完整的生态系统。那是——

<details>
<summary>Original English</summary>

**Speaker B**: and you have a whole ecosystem strategy as you think about your mode to the extent that any moat can be present in this industry like you built a whole ecosystem. Is that is that >>

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. >>

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 我们建立了一个生态系统。我认为，我们的护城河来自于这样一个事实：凭借我们架构的优势，我们……（片段结束）

<details>
<summary>Original English</summary>

**Speaker A**: We've built an ecosystem. I I think um our moat comes from the fact that uh by virtue of our architecture we

</details>

<!-- chunk 7/7 -->

### 供应链与台积电的破局合作

**Andrew**: 我们在做其他人做不到的事情。而且，这不是他们能花更多钱的问题，或者他们不能为 GPU 付出更多代价的问题。如果你想要速度，你就是得不到。我是说，这根本行不通。所以这就是我们建立优势的地方，这也是我们向客户交付价值的方式。

<details>
<summary>Original English</summary>

**Andrew**: ...are doing things no one else can do. And uh it's not uh that they can spend more money or or or they can't uh pay more for for this with GPUs. If you want fast, you can't have it. Well, I mean JP, it it doesn't work. And so that's where we're building sort of our strength and that's how we're we're sort of delivering value to customers.

</details>

**Matt Turk**: 你对供应链怎么看？我们提到了其他人面临的供应链限制，但你们的供应链限制是什么？你们全都在用台积电（TSMC）吗？

<details>
<summary>Original English</summary>

**Matt Turk**: What do you think about supply chain? We mentioned supply chain constraints for others, but what are your uh supply chain constraints? Are you all TSMC?

</details>

**Andrew**: 我们用的就是台积电。嗯，我们有着非常紧密的合作。他们是我们的投资者，一直是非常出色的合作伙伴。我给你讲一个不同寻常的故事。2017年，我们来到了那里，当时我们总共大概只有30个人。而且我们是八月份去的。在台湾那是个可怕的季节。千万别在八月份去台湾。你知道，那天气简直太残酷了。

<details>
<summary>Original English</summary>

**Andrew**: We are TSMC. Um, we had very close collaboration. They were investors of us. They've been exceptional partners. I'll tell you an unusual story. In 2017, we showed up and we were about 30 guys total. And we showed up in August. Horrible trend in Taiwan. Don't go to Taiwan in August. You know, it is brut.

</details>

**Matt Turk**: 搞得好像今天这里的天气有多好似的。

<details>
<summary>Original English</summary>

**Matt Turk**: Not that it's so nice here today.

</details>

**Andrew**: 这里才90度（华氏度）而已。

<details>
<summary>Original English</summary>

**Andrew**: It's only 90 here.

</details>

**Matt Turk**: 真是尴尬。

<details>
<summary>Original English</summary>

**Matt Turk**: Embarrassed.

</details>

**Andrew**: 是啊。但是那里所有的湿气……总之，我们和台积电的领导层见了面。我们说，我们代表我们这家不起眼的小公司，我们相信我们能解决一个历史上无人能解的问题，而为了让这成为可能，我们需要这样修改你们制造芯片的方式。他们思考了一下，然后说：“我们同意，我们干吧。”

<details>
<summary>Original English</summary>

**Andrew**: Yeah. But all the humidity and Yeah. You got put on a and we met with the leadership of TSMC. We said we we would like your little pipsqueak company. We believe we can solve a problem that nobody solved in history and here's how we would modify the way you make chips to make this possible. They thought about it and they said we agree let's do it

</details>

**Matt Turk**: 当场在会议上就决定了？

<details>
<summary>Original English</summary>

**Matt Turk**: in the meeting.

</details>

**Andrew**: 对，就在会议上。

<details>
<summary>Original English</summary>

**Andrew**: In the meeting.

</details>

**Matt Turk**: 在会议上直接拍板，而不是说“你们先回去，我们考虑一个月”？

<details>
<summary>Original English</summary>

**Matt Turk**: in the meeting it it wasn't go away for a month in the meeting.

</details>

**Andrew**: 是因为他们已经有了心理准备，还是他们真的就是反应极其迅速？嗯，首先是销售人员把决策者们都召集到了一起。其次，我们的提案非常出色，能够让他们发挥自己擅长的优势。这不需要他们做出巨大的改变，但确实需要他们做出实质性的改变。而且我认为，他们觉得这个想法足够大胆，他们可以在做的过程中不断学习。他们也知道人工智能在大型芯片上运行得更好。所以，这是一种公平的心态、承担一定风险的意愿，以及来自一家超大型公司的大胆思维的结合。

<details>
<summary>Original English</summary>

**Andrew**: Was that they had a prepared mind or they were just exceptionally fast on their feet? Um first the salesperson had gathered the decision makers. Second uh we got our our proposal was sort of really good at allowing them to use what they were good at. And it didn't require them to change a huge amount, but it it did require them to make real changes. And I think they saw this as sufficiently bold that they would learn as they did it. And they also knew that AI was better on big chips. thing and so a combination of fair mind, a willingness to take some risk, bold thinking from a very large company.

</details>

**Matt Turk**: 真是令人着迷。

<details>
<summary>Original English</summary>

**Matt Turk**: Fascinating.

</details>

**Andrew**: 确实令人着迷。我的意思是，这就是大公司获胜的方式，对吧？嗯，而且这种情况是多么罕见，那简直是非凡的。

<details>
<summary>Original English</summary>

**Andrew**: It is fascinating. I mean that's how big companies win, right? Um and how rare is that was extraordinary.

</details>

### 芯片开发的漫长周期与市场接受度

**Matt Turk**: 那接下来发生了什么？像那种在会议上异常迅速做出的决策，到实际落地需要多长时间？

<details>
<summary>Original English</summary>

**Matt Turk**: And what happened next? Like how long does it take between a decision in a meeting like that which senses exceptionally fast to

</details>

**Andrew**: 两年。

<details>
<summary>Original English</summary>

**Andrew**: two years?

</details>

**Matt Turk**: 两年。芯片制造是一个漫长且艰难的过程。

<details>
<summary>Original English</summary>

**Matt Turk**: Two years. Chipm is a long hard process

</details>

**Andrew**: 而且大多数时候，你的第一款芯片并不会成为赢家。现在有很多初创公司，其中一些拥有非常聪明的人才，但他们的第一款芯片绝不会一上来就成功。谷歌的 TPU 团队拥有业内最顶尖的一批人才，他们的第一款芯片不是赢家，第二款也不是，第三款、第四款才真正变得优秀，现在他们已经做到了第八代，那是一款非常棒的芯片。好吧，比如 AWS 的 Annapurna 团队，他们的第一款芯片并不好，到了第二款、第三款芯片才变得非常出色。

<details>
<summary>Original English</summary>

**Andrew**: and most of the time your first chip isn't a winner and there are lots of of startups now some of them with really smart guys but their first chip will not be order the TPU Google had some of the best guys in the industry first chip wasn't a winner nor the second nor the third fourth was really good now they're on their eighth and it's really good chip okay um the anapa team at uh at AWS. First chip wasn't great. Second, third chip really good.

</details>

**Matt Turk**: 这确实需要时间。

<details>
<summary>Original English</summary>

**Matt Turk**: It it takes time.

</details>

**Andrew**: 所以我们制造了一款芯片，并将其交付。这就回到了你之前问的一个问题。你知道，我们解决了一个在计算历史上从未有人解决过的问题。我们在 2020 年交付了它，但根本没人关心。根本没人关心。没有人买，也没人在乎。大家当时的反应就像是，“哦天哪，所有人都说我们疯了，这绝不可能行得通，而现在它行得通了，却好像没有人想要它。” 嗯，所以后来我们又制造了下一款。

<details>
<summary>Original English</summary>

**Andrew**: And so we built a chip, we delivered it. And this gets to an earlier question you asked. You know, we solved a problem that that nobody in the history of computed solved. And we delivered it in 2020 and nobody cared. Nobody cared. Nobody bought any and nobody cared. She were like, "Oh god, nobody everybody said we were crazy. It would never work and now it works and like nobody want it." Um, so then we built the next one.

</details>

**Matt Turk**: 我的意思是，第一款你们大概卖了一整年？

<details>
<summary>Original English</summary>

**Matt Turk**: I mean, the first one we probably sold quite a year

</details>

**Andrew**: 而且没人想要它。是因为市场还没准备好，还是因为产品不够好？

<details>
<summary>Original English</summary>

**Andrew**: and nobody wanted it because the market was not ready or because the product was not good enough.

</details>

**Matt Turk**: 嗯，没人想要它是因为当时人工智能还只是个业余爱好。那是对的。谁会在乎你的业余爱好是不是运行得特别快呢？

<details>
<summary>Original English</summary>

**Matt Turk**: Um, nobody wanted it because AI was a hobby. It was right. And who cares if your hobby is really fast.

</details>

**Andrew**: 嗯，只有当它投入生产环境时，你才会关心速度。只有当你每天都在使用它时，你才会关心速度。

<details>
<summary>Original English</summary>

**Andrew**: Um, you care about fast when it's in production. You care about fast when you use it every day.

</details>

**Matt Turk**: 所以我们又制造了另一款，你知道，那一款我们卖出了 300 或 500 台。

<details>
<summary>Original English</summary>

**Matt Turk**: And so we built another one and you know that one we sold three or 500.

</details>

**Andrew**: 是的。

<details>
<summary>Original English</summary>

**Andrew**: Yeah.

</details>

**Matt Turk**: 然后我们制造了第三款，我们卖出了几万台。

<details>
<summary>Original English</summary>

**Matt Turk**: And we built the third one and we sold tens of thousands.

</details>

**Andrew**: 太惊人了。

<details>
<summary>Original English</summary>

**Andrew**: Amazing.

</details>

### 供应链多元化的挑战与现状

**Matt Turk**: 是的。这难道不有趣吗？嗯，所以回到供应链的问题，你是否需要考虑多元化？很难从台积电进行多元化分散，芯片制造太难了。实际上，当你设计一款芯片时，设计的一部分就是为了符合那家工厂的规则，对吧？所以你不能把台积电的设计直接拿给其他人做，因为有大量的工作是为了确保你的设计符合他们的规则而进行的。所以即使在整个历史上，我想只有一两个例外。每一代芯片都只交给一家晶圆厂。所以，这就是为什么我们下一代产品也会继续与台积电合作。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. Isn't that interesting? Um and um so going back to supply chain uh do you need to think about u onouring diversification? So it's very hard to diversify away from TS chips are so hard and you actually when you design a chip part of the design is for the rules of that factory right so you can't take your design from TSMC and go to somebody else because a huge amount of the work was bid to be sure your design is within their rules and so even in I think only with one or two exceptions in history. Uh each chip generation goes to one fat. So that that's we're going to be with TSMC for our next generation as well.

</details>

**Andrew**: 我认为有些……

<details>
<summary>Original English</summary>

**Andrew**: I think some

</details>

**Matt Turk**: 嗯，我们的供应链由很多部分组成，但我们从台积电将芯片运回美国。我们在美国进行封装，并在美国进行组装。我们在美国进行制造，然后从美国发货。我认为，当你像我们这样快速增长时，你会面临各种常见的供应链挑战，你知道，比如某个供应商把一批货搞砸了，或者货物卡在海关了。供应链中可能出错的环节数量简直令人难以置信。但我们每天都在应对这些问题，并且我们的制造产能正在呈指数级增长，所以那部分业务其实运转得非常好。

<details>
<summary>Original English</summary>

**Matt Turk**: uh we have uh a supply chain that is built in many parts but we bring the chips back from TSMC to the US. We package in the US and we assemble in the US. We do our manufacturing in the US and then we ship from the US. I think when you're growing this fast as we are right there range of garden variety supply chain challenges you know a vendor screws up a batch it gets stuck in customs. The number of of ways that that things can go wrong the supply chain is unbelievable. But we manage these every day and we're increasing our manufacturing throughput exponentially and so it's really uh that part of the business really well.

</details>

### AI 的未来预测与影响

**Matt Turk**: 太不可思议了。那么，也许把视角拉远，作为最后一个问题，你对这一切的未来走向有什么最好的猜测？显然，谁知道未来几年人工智能会怎样，但就拿未来一两年来说吧。

<details>
<summary>Original English</summary>

**Matt Turk**: Incredible. So maybe to zoom out as the last question um what what's your best guess about how where all of this is going uh you know obviously who knows in AI in the next like few years but like in the next year or two.

</details>

**Andrew**: 好了，我们知道一些事情。我们知道，我们现在使用的模型，也就是你今天正在使用的模型，不管是哪种模型或者是 GPT-5、GPT-6，将会是你用过的最糟糕的模型。你现在觉得它有多酷，在六个月后你就会觉得它有多无聊和落后。这简直太令人兴奋了，而且我认为我观察我们年轻工程师使用它的方式，这和我使用它的方式非常不同。在这个有趣的时代，你可以从年轻的团队成员那里学到东西，他们使用 AI 的方式截然不同。我认为那种做仪表盘的业务，以及那些软件即服务（SaaS）受到的冲击，我认为是无法修复的。你知道，你可以让你的 AI “给我建一个像 Salesforce 一样的工具”，30 秒后你就有了一个可以运行的工具，这简直令人难以置信。而且所有那些以前因为跨越了组织内部孤岛而变得困难的事情，对吧？但是其中一件非常困难的事情是，如果你想知道你表现最好的员工，他们上一次获得期权更新是什么时候？他们还剩下多少持有权？所以，按照今天的价格，他们还剩下多少未行权的股票？

<details>
<summary>Original English</summary>

**Andrew**: Well we know some things. We we know that the model we use it you're using it today. Fable or GPT56 or will be the worst model you ever use. And whatever you think is cool about it right now is going to be boring and backwards in six plus and that is so exciting and I I think I watch the way our young engineers use it and it's very different than the way I'm using it and it's sort of a fun time where you can learn from your young team members that they're using AI very differently. I think the business of dashboarding and the business the um the damage is doing the SAS is I think unrepairable you know we you could ask your AI build me a tool like Salesforce 30 seconds later you have a working tool that that he's just unbelievable and all the things that that were difficult because they cut across you're inside organizational silos, right? But one of the things that's really hard is if you want to know for your top performing people, when was the last time they got a stock option refresh and how much uh holding power is left. So, how much uninvested stock they have left at today's price?

</details>

**Matt Turk**: 以前大概有五个系统。你在 Workday 里查，你还要在你的股票系统里查。

<details>
<summary>Original English</summary>

**Matt Turk**: There's like five systems. You're you're in work days, you you're in your uh stock.

</details>

**Andrew**: 是的。

<details>
<summary>Original English</summary>

**Andrew**: Yeah.

</details>

**Matt Turk**: 你在你的汽车系统里查，你在 Carta 里查。它们没法联动，而这恰恰是一位 CEO 想要的。

<details>
<summary>Original English</summary>

**Matt Turk**: You're in your your car, you're in Card. None of them can and that's what a CEO wants.

</details>

**Andrew**: “我的高管们还有多少持有权？”

<details>
<summary>Original English</summary>

**Andrew**: How much holding powers for my top guys?

</details>

**Matt Turk**: 对。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah.

</details>

**Andrew**: 我以前经常为这个写些小工具。现在砰的一声，我就有了一个深入且能瞬间激发灵感的小应用。

<details>
<summary>Original English</summary>

**Andrew**: And I used to have little tools I wrote for this. And boom, I've got a a little app that that I had deep and spark right.

</details>

**Matt Turk**: 就是这样。

<details>
<summary>Original English</summary>

**Matt Turk**: You go.

</details>

**Matt Turk**: 哇，这真是一个精彩的故事。能听你讲述这一切真是太不可思议了。多么奇妙的旅程，多么令人兴奋的未来。所以，非常感谢你。我学到了很多，这次交流太棒了。谢谢你，Andrew。

<details>
<summary>Original English</summary>

**Matt Turk**: Well, what what a story. Uh it's just incredible to um hear all of this from you. What a journey um and what an exciting future. So, uh, thank you very much. I learned a lot and this was terrific. Thank you, Andrew.

</details>

**Andrew**: 谢谢你邀请我上你的节目。我非常感激。

<details>
<summary>Original English</summary>

**Andrew**: Thank you for for having me on your show. I really appreciate it.

</details>

**Matt Turk**: 大家好，我是 Matt Turk。感谢收听这期 Mad 播客。如果你喜欢这期节目，如果你还没有订阅的话，希望你能考虑订阅，或者在您观看或收听本期节目的任何平台上留下好评或评论，我们将不胜感激。这对我们建设播客并邀请到出色的嘉宾非常有帮助。谢谢，我们下期节目再见。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks, and see you at the next episode.

</details>