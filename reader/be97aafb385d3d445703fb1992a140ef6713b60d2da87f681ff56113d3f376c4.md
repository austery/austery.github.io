---
author: Latent Space
date: '2026-09-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3uSI8q_RN-o
speaker: Latent Space
tags:
  - wafer-scale-engine
  - low-latency-inference
  - sram-architecture
  - interconnect-bandwidth
  - agentic-reasoning
title: 推理前沿：从每秒 100 到 10,000 Token —— 专访 Cerebras 联合创始人兼 CTO Sean Lie
summary: Cerebras 联合创始人兼 CTO Sean Lie 深入剖析了晶圆级芯片架构（WSE）在低延迟超高速推理中的技术突破。从 CS4 到 CS5 的系统级演变、SRAM 与互连带宽的技术红利、与 OpenAI 的深度合作，到超快推理如何颠覆性地重塑智能体（Agent）循环与实时交互体验，全方位展现了芯片黄金时代的创新浪潮。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cerebras
  - OpenAI
  - Nvidia
products_models:
  - CS4
  - CS5
  - Jalapeno
media_books: []
status: evergreen
---
### 推理速度的代际跃迁与智能体变革

**Sean Lie**: 过去大家认为每秒 100 或 200 个 token 就已经很快了，但现在这种速度正迅速变成新的“批处理模式”（Batch Mode）。我认为那种速度依然有其用武之地，它非常适合做 **Prompt 预处理**（Prompt Processing），也极其适合处理那些高度并行的批处理工作负载。

<details>
<summary>Original English</summary>

**Sean Lie**: what used to be considered fast at like 1,000 uh 100 or or 200 tokens per second is quickly becoming the new batch mode. And so I think that you know there's a place for that. It's great for prompt processing. It's great for very very parallel workloads. Um

</details>

**主持人**: 比如我跑一次模型评估（Evals）原本需要 20 个小时，现在按下一个按钮，两个小时就能跑完。

<details>
<summary>Original English</summary>

**Host**: but my emails take 20 hours. I can hit a button and run it in two hours.

</details>

**Sean Lie**: 没错，完全正确。但很快大家就会发现，仅仅具备快速处理 Prompt 的能力是远远不够的。诚然，那是市场中很大的一部分需求，但绝对无法覆盖全部场景。

<details>
<summary>Original English</summary>

**Sean Lie**: Exactly. Exactly. Right. But but quickly, you know, being able to do prompt processing isn't isn't quite enough. Right. That's a big part of the market, but that's not quite enough.

</details>

### 开场与 Hot Chips 盛会观察

**主持人**: 在进入今天的正题之前，我想对各位听众说一小段心里话。非常感谢大家！如果没有你们每周点击收看和收听我们的内容，我们根本不可能持续为大家带来关于 **AI 工程**、前沿科学与深度探讨的优质内容。几乎每天都有赞助商找上门来，但非常幸运的是，有足够多的听众选择订阅支持我们，使得我们能够完全在无广告的情况下维持频道的良性运转，我们也希望能够一直保持这种纯粹的形式。

我在这里只有一个小小的请求：如果你愿意支持我们，最有力且完全免费的举动，就是点击那个**订阅**按钮。这是我唯一向大家恳求的事。对于我和每周辛勤制作 **Inspace** 节目的整个团队来说，这意义非凡。只要大家持续支持，我保证我们会竭尽全力把节目越做越好。现在，让我们正式进入正题！

今天我们来到了 **Cerebras** 总部，对话联合创始人兼 CTO **Sean Lie**。非常欢迎你！

<details>
<summary>Original English</summary>

**Host**: Before we get into today's episode, I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis, but fortunately, enough of you actually subscribe to us to keep all this sustainable without ads, and we want to keep it that way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you. And it means absolutely everything to me and my team that works so hard to bring the Inspace to you each and every week. If you do it, I promise you we'll never stop working to make this show even better. Now, let's get into it. Okay, we're here at Crisis HQ with CTO Sha Lee. Welcome. Uh

</details>

**Sean Lie**: 谢谢你，非常感谢你们邀请我。

<details>
<summary>Original English</summary>

**Sean Lie**: thank you. Thank you for having us.

</details>

**主持人**: 感谢你抽出宝贵时间接受采访。

<details>
<summary>Original English</summary>

**Host**: Yeah. No, thank you for having me.

</details>

**主持人**: 今天正好是 **Hot Chips** 大会刚结束的第二天。今年大会上发布了海量重磅新品，甚至连 **Apple** 都发布了 **M6** 相关的架构细节。当然，你们在之前的 **Supernova** 活动上也公布了重磅消息。你在大会上深入讲解了 **CS4**，等会儿我们还会聊聊接下来的 **CS5**。此外，**OpenAI** 也公布了其代号为 **Jalapeno** 的项目。Hot Chips 上真是干货满满、热度非凡。作为在芯片行业深耕多年的资深专家，你对今年的大会有什么总体看法？

<details>
<summary>Original English</summary>

**Host**: Uh and it is the day after hot chips. Lots of things launching. Even like Apple launched the M6 stuff. Uh but you guys obviously had we were at Supernova. You uh talked about CS4. We're going to talk a little bit about CS5. OpenI talked about Jalapeno. All the all the hot stuff in hot chips. What's your take this year having been in this industry?

</details>

**Sean Lie**: 首先，再次感谢你们的邀请。你说的完全没错，眼下是一个令人无比兴奋的时代。Hot Chips 是整个芯片与系统工程社区齐聚一堂的绝佳盛会。我依然清晰地记得 10 年、20 年前去参加 Hot Chips 时的情景，那时候基本上就是一群计算机架构极客聚在一起，钻研各种主频、带宽参数和技术指标；而如今，这里已经成为了颠覆整个行业的硬核技术与硬件首发的舞台。可以说，整个行业走过了漫长而波澜壮阔的历程，这个技术社区充满了活力。

在昨天离开 Hot Chips 会场时，我最深刻的感触就是：对于芯片设计和硬件行业而言，这真是一个令人心潮澎湃的时代，我们正身处**硬件的黄金时代**。正如你所言，我在这个行业已经打拼了很长时间。当前这个时期之所以极其特殊，不仅是因为人工智能正在迎来爆发式增长、各大厂商都在全力研发自己的硬件，更在于我们在芯片产业链的多个维度上看到了前所未有的创新浪潮。在半导体工业的历史上，我们从未见过在所有层级上同时爆发如此密集的突破——从芯片内核、互连架构、系统级工程、软件栈，到光互连、设计方法论以及 EDA 工具链，全行业都在齐头并进地推高极限。因此，作为一名技术人员和骨子里的计算机体系结构极客，能够见证这个行业迈入这一阶段，感觉真的非常痛快。在 Hot Chips 现场，每一位与我交谈的人都真切地感受到了这种技术激荡与澎湃的能量，这太不可思议了。

<details>
<summary>Original English</summary>

**Sean Lie**: I think I think uh well, first of all, thank you for having me. Um and uh and and you're absolutely right. It's a super exciting time right now. Um hot chips is a is is a is really good, you know, time when the whole community comes together. Um, and you know what what used to be, you know, I still remember going hot chips 10, 20 years ago when it's a bunch of like, you know, computer architect, you know, geeks, you know, geeking out on, you know, speeds and feeds and and now it's like this is where, you know, industry changing hardware is is being revealed. And so, um, you know, it's come a long way. It's really exciting, you know, community. And I think one of the main takeaways that that that I had after, you know, after leaving Hot Chips yesterday is like what an exciting time it is for the the chip design and the hardware industry. It's uh you know, this is really the golden age of uh of hardware right now. Um and you know, like you said, I've been in this industry for some time. Um this is a very very unique time not just because you know AI is taking off and you know and there's uh you know obviously a lot of uh people doing their own hardware but the amount of innovation that's happening now across multiple fronts we've never seen in the history of uh of the semiconductor industry this level of innovation across all the levels right in the chip uh the interconnect the system design the software the optics the you know the methodology the tooling people are pushing across the board and so like you know as a technologist and and you know a computer architecture geek at heart it's like really really fun to see this community and this industry at this stage right now and when we and we felt that like at at hot chips and everybody I talked to it's like that that buzz is there it's amazing

</details>

### CS4 架构突破：晶圆级芯片走向超大规模

**主持人**: 我们想把这次发布的各种芯片挨个盘点一遍，不过还是先从你们自家的芯片聊起。大家最关心的莫过于 **CS4** 的推出，它展示了一些堪称疯狂的性能数据——比传统 GPU 快了 **30 倍**！能为我们系统拆解一下全新 CS4 带来了哪些技术突破吗？

<details>
<summary>Original English</summary>

**Host**: we want to go through the chips let's you know talk about your chip first what's what's most exciting uh CS4 came out some crazy numbers here 30x faster the GPUs but uh you know walk us through what's new with the new CS4.

</details>

**Sean Lie**: 没问题。在设计下一代 **CS4** 架构时，我们打造了一套全新的系统平台。其核心目标非常明确：那就是要让**晶圆级计算（Wafer-scale Engine）**真正走向主流应用，全面推向超大规模（Hyperscale）数据中心，并从根本上解决现代高密度数据中心每天都面临的工程难题。

我们设计了一个全新的模块化系统平台，它向单个晶圆提供的供电功率达到了上一代产品的整整**两倍**，互连带宽同样提升至**两倍**，同时将通信延迟缩短了一半。所有这些突破都是在系统级体系结构层面实现的。大家看到的结果就是：通过向晶圆输送大幅增加的电能，并在机架中实现更高密度的集成，我们能够把性能推向全新的高度。

我们经常说，凭借现有的产品线，Cerebras 已经是超高速推理领域公认的领军者；而令人振奋的是，CS4 产品将把这一性能前沿进一步推高，让整体推理速度在现有极致基础上再翻**一倍**。在 Hot Chips 现场的演示就是一个极佳的例证：我们展示了 **GPT-OSS** 在 CS4 架构上以超过 **4,400 TPS（Tokens Per Second）** 的惊人速度飞速运行。这个数字简直令人瞠目结舌，快到让人感觉甚至有些不真实。

我们坚信这必将彻底颠覆整个 AI 产业。因为这不仅意味着我们能够持续推高这些大语言模型的运行极限，更重要的是它将解锁一系列前所未有的全新应用场景。用户的交互体验将发生质的飞跃：过去只能以离线批处理模式运行的复杂任务，现在将瞬间转变为端到端的实时交互体验。

此外，随着各种新兴**智能体工作流（Agentic Flows）**和智能体框架的蓬勃发展，用户再也不需要坐在屏幕前漫长地等待智能体在其推理闭环（Agentic Loop）中一轮又一轮地反复计算。当底层大模型的推理速度突破每秒 4,000 个 token 时，系统就能在极短时间内执行更深层次的智能体循环，进行多步链式思考和更充分的逻辑推理，从而打造出能力与智能水平显著跃升的真正智能体。这才是最令我们兴奋的核心所在——不仅在于我们展示了那些极其震撼的性能指标（虽然这确实很酷），更在于它赋予了开发者实现此前根本无法企及的全新能力。这就是我们在昨天发布会上感到无比自豪的原因。

<details>
<summary>Original English</summary>

**Sean Lie**: Sure. So, you know, we we we we designed uh our next generation CS4 architecture um with a new brand new system platform with the goal really um to make wafer scale uh mainstream to make it uh uh to bring it to hypers scale and to solve uh a lot of the the the high density um data center problems that you know we're facing every single day. So we've designed this uh modular platform uh that provides twice the amount of power to the wafer than we have in our previous generation. Um twice the amount of uh interconnect bandwidth, half the latency. Um and all of it is done at the system uh architecture level. And what you see here is the result is that by being able to provide significantly more power to the to the wafers by you know packing more density into the rack we're able to drive up the performance even further. Um you know we like to say that Cerebrris is uh with our current product already the undisputed leader in you know ultraast inference. Um and and what's amazing is this CS4 product will actually push that frontier even further by taking it another two times faster. Um and this is a a perfect example right we here in this in this demo that we gave uh at hot chips. Um we're showing uh GPTOSS uh running at over 4,400 TPS which is just mind-blowing. It's like it's it it it almost feels like it's fake, right? Um and uh and and we think that this is going to really revolutionize the entire you know industry because you know not only are we able to you know continue to push the frontier on how fast these models can run um it will enable all sorts of new applications um you know uh uh user experiences start to become extremely different right what used to be batch and offline applications start to become real time um And you know all of this you know growth in new agentic flows and agentic uh frameworks now also mean that you know you're you're sitting there waiting for these agents to go over and over and over uh uh in their agent agentic loop and all of a sudden if you're running uh your model at over 4,000 tokens per second. Now the you can do you know more agentic uh uh loops you can do more reasoning ultimately you get significantly more capable more intelligent agents. And so this is what really excites us about this. Not just the fact that you we show these really really big numbers which is also really cool. Um but but the fact that you can you know really start to do things that you can't really do uh otherwise and and and start to enable brand new capabilities. Um that that's that's what makes me so excited about this this reveal that we had yesterday.

</details>

**主持人**: 确实如此。回顾你们踏上“大芯片与晶圆级计算”这一探索征程的初心，一路走来真的收获斐然。曾经人们对晶圆级技术持怀疑态度，直到现实需求迫使大家不得不重视，而现在整个业界都在以极其严肃认真的态度对待这一方向。

<details>
<summary>Original English</summary>

**Host**: Yeah. I think it's also very rewarding that you guys started on this journey the big chip journey. uh you know wafer scale everything everything that you've always said it just like people didn't take it that seriously until they had to and then now they're they're really really taking it super seriously right

</details>

**主持人**: 作为联合创始人、CTO 以及整套架构的总设计师，在经历了这波 AI 爆发式繁荣之后，你们是如何规划和定义新一代芯片产品的？我猜在研发 CS1、CS2 和 CS3 的时代，外部环境可能相对更加平静一些。

<details>
<summary>Original English</summary>

**Host**: um I I I do feel like as you know co-founder CTL the the architect of this whole thing how are you guys approaching the new generations post like AI boom like I imagine CS123 was a bit more uh sort of uh calm

</details>

### 从训练引擎到超高速推理中枢

**主持人**: 如今，OpenAI 正式推出了与你们合作的超高速推理模式（Ultra Fast Mode）。这已经不再是理论探讨，而是实实在在落地的产业现实。

<details>
<summary>Original English</summary>

**Host**: now like literally open AI is launching soup the the ultra fast mode with you guys and like it it is a matter of like I mean

</details>

**Sean Lie**: 没错，确实如此。在我看来，过去几年发生在我们身上的核心战略转变在于：过去，我们主要将这套庞大的芯片架构定位为超大规模的**AI 训练加速引擎**；而现在，整个团队清晰地意识到，这套架构在**低延迟超高速推理（Ultra-fast Low-latency Inference）**领域展现出了无与伦比的天然优势。

正如我前面所讲，由于我们在单颗晶圆上集成了海量的片上 SRAM 内存，并且在整个晶圆面积内构建了超高带宽、微秒级延迟的片上网络互连，使得我们能够以突破物理常识的极限速度读取模型权重并吐出 token。这种架构特性与当下大模型对实时推理的极致渴求完美契合。

<details>
<summary>Original English</summary>

**Sean Lie**: No, absolutely. I I feel like the main shift that has happened over the last few years um for us is that you know the the the major pivot that we made was from you know historically thinking about this as a giant training machine to now really realizing that this architecture has a huge fundamental advantage for you know low latency ultra fast inference.

</details>

**主持人**: 那么我们或许可以接着聊聊昨天的具体发布。

<details>
<summary>Original English</summary>

**Host**: And so maybe we'll talk about yesterday.

</details>

**Sean Lie**: 好的。

<details>
<summary>Original English</summary>

**Sean Lie**: Yeah.

</details>

### 展望 CS5 与产品交付节奏

**主持人**: 关于大会上预告的 **CS5**，你能为那些还没完全跟上最新进展的观众们简单梳理一下吗？

<details>
<summary>Original English</summary>

**Host**: Uh previewing CS5. Uh can you recap for people who are maybe not not yet caught up on that?

</details>

**Sean Lie**: 没问题。刚才我提到了我们刚刚发布的 **CS4** 系统平台。而对于 **CS5**，我们将在其上搭载全新制程工艺打造的下一代芯片架构。它将带来两倍于现有水准的片上内存容量、两倍的计算算力以及成倍扩展的互连带宽。这意味着在 CS4 将推理速度推向每秒 4,000+ token 之后，CS5 将继续引领行业，向每秒接近 **10,000 Token** 的终极推理极限发起冲击。

<details>
<summary>Original English</summary>

**Sean Lie**: Yeah. No, no problem. So I mentioned that our CS4 system that we just uh launched has this brand new platform and CS5 is basically taking that exact platform and putting our next generation wafer scale engine on that platform. And what that means is that you get another 2x performance increase over CS4. So, you know, we're already running at 4,000 tokens per second. Now you're talking about running closer to 10,000 tokens per second with CS5.

</details>

**主持人**: 目前整体的交付和落地节奏是怎样的？你们在接下来的几年里与 OpenAI 达成了重要合作，但普通开发者和大众究竟什么时候才能真正使用上？大家现在对 Ultra Fast 模式可谓望眼欲穿。

<details>
<summary>Original English</summary>

**Host**: What's the rollout process like? So, you have a deal with OpenAI over the next few years, but when do we get access, you know? So, everyone wants ultra fast right now. Sure. When do we get it?

</details>

**Sean Lie**: 这是一个非常好的问题。目前来看，我们所有的算力产能基本处于完全售罄的状态。来自各方的需求极其旺盛。为了应对这一局面，我们正在与台积电（TSMC）及各核心供应链伙伴紧密协同，全速拉升产能与制造规模。

关于具体的时间表：我们目前正向首批核心战略客户全面交付并部署现有的硬件系统。随着年底的临近以及明年初步入量产爬坡期，大家将会看到 CS4 系统陆续进驻数据中心；而随后的 CS5 则会在该系统架构上实现无缝升级与迭代。我们正在以最快速度将这种超高速推理能力普惠给更广泛的开发者群体。

<details>
<summary>Original English</summary>

**Sean Lie**: that's a great question. So right now uh we are basically you know sold out of everything that we can make. The demand is super high. And so we are working as hard as we can with our manufacturing partners like TSMC to really scale up the production. In terms of timelines, you know, CS3 is obviously shipping today and powering a lot of this ultra fast mode. CS4 is sampling now and will be ramping into high volume production next year, followed closely by CS5 on that same modular platform.

</details>

### OpenAI 合作逻辑与 Jalapeno 架构对比

**主持人**: 顺便提一句，从你刚才梳理的脉络中我意识到，OpenAI 此前在底层硬件上其实并没有完全自研的专用芯片落地。这在商业决策上是一个非常耐人寻味的信号。

<details>
<summary>Original English</summary>

**Host**: by the way you know the way that you framed it I realized that they didn't have a hardware play of their own that was public until now and so people didn't know what they were doing.

</details>

**主持人**: 大家都很好奇背后的商业考量。

<details>
<summary>Original English</summary>

**Host**: nobody knew that that's an interesting like business decision almost I don't know

</details>

**Sean Lie**: 我想说的是，显然我无法代表 OpenAI 去公开发表过多评论。但我认为对于任何处于他们那种规模的领军企业来说，在超高速推理领域必须平衡多维度的战略诉求。他们近期也公布了自己在定制化硬件上的探索，比如在 Hot Chips 上介绍的 Jalapeno 项目。

<details>
<summary>Original English</summary>

**Sean Lie**: I would say I would say that um you know obviously I can't uh you know explicitly comment about their business strategy. But what I can say is that when you look at companies of that scale, they have to look at multiple ways to solve the problem, right? They need massive scale for general workloads, and they also need extreme performance for ultra fast experiences.

</details>

**Sean Lie**: 在超高速低延迟这一赛道上，他们需要综合权衡性能、研发周期、软件生态以及供应链的成熟度。

<details>
<summary>Original English</summary>

**Sean Lie**: um, you know, in in the ultra fast space as well. I mean they're balancing a lot you know most recently with what they presented at Hot Chips with Jalapeno.

</details>

**主持人**: 我们必须深入探讨一下这个话题！关于 **Prefill（Prompt 预填充）** 与 **Decode（自回归生成解码）** 的分工，针对 OpenAI 的 **Jalapeno** 芯片，你的专业看法是什么？

<details>
<summary>Original English</summary>

**Host**: we got to talk about this as well we got to we got to go into them so what are we thinking prefill jalapeno vs decode?

</details>

**主持人**: 你对他们的架构设计怎么看？

<details>
<summary>Original English</summary>

**Host**: what are your takes

</details>

**Sean Lie**: 我认为他们的结论非常理性且符合工程逻辑。当你在构建像他们那样吞吐量极为庞大的超大规模数据中心服务时，将 Prefill 阶段与 Decode 阶段进行物理层面的架构解耦，是一个极其自然的设计选择。

<details>
<summary>Original English</summary>

**Sean Lie**: I think that's I think that's uh that's a very you know rational um you know conclusion I I think of their work, right? When you're operating at their scale, separating prefill and decode makes absolute architectural sense.

</details>

**主持人**: 我想就这一点进一步深挖。你是芯片领域的顶级专家。普通人看到 Token/s 这一数字，可能以为所有芯片都在跑同样的任务，但其实背后的计算瓶颈截然不同。Jalapeno 并没有针对极致低延迟的 Decode 去做专属特化，对吧？

<details>
<summary>Original English</summary>

**Host**: I guess to to double click on that, you're the expert in chips, right? There's people see token per second and they think everything is uniform. But prefill is compute-bound, matrix multiplication heavy, whereas decode is memory-bandwidth bound. So for Jalapeno, they didn't actually specialize jalapeno for low-latency single-stream decode, right?

</details>

**主持人**: 他们并没有把 Jalapeno 特化在低延迟生成上。

<details>
<summary>Original English</summary>

**Host**: for they didn't actually specialize jalapeno for right

</details>

**Sean Lie**: 没错。他们并没有将 Jalapeno 专门特化在极限低延迟的单流（Single-stream）生成解码上，而是将其重点优化为高并发、高吞吐量的计算引擎。在 Prefill 阶段，模型需要一次性摄入成千上万个 token 的上下文，这是一个典型的**算力密集型（Compute-bound）**负载，非常适合利用高密度的矩阵乘法单元在大 Batch 模式下高速吞吐。

而到了 Decode 生成阶段，系统每生成一个 token，都必须完整读取一次数十甚至数百 GB 的模型权重矩阵。此时每个 token 的计算强度极低，性能完全受限于**内存带宽（Memory Bandwidth Bound）**和**通信互连延迟（Interconnect Latency）**。

因此，当你尝试用传统由高带宽内存（HBM）加 GPU 构建的集群去跑 Decode 时，受制于片外通信延迟和 HBM 带宽上限，单流生成速度很难突破物理天花板。而 Cerebras 的晶圆级架构将 44GB 甚至上百 GB 的超高带宽 SRAM 直接集成在晶圆内部，拥有高达数十 PB/s 的片上内存带宽，因此能够天然在 Decode 阶段实现数千 TPS 的极致低延迟。两者在体系结构上的侧重点是完全不同的。

<details>
<summary>Original English</summary>

**Sean Lie**: they did not specialize jalapeno for that but they specialized it for throughput right and so they get high throughput prefill. Prefill is very compute dense—you're doing massive GEMMs on large prompt contexts. But decode is fundamentally memory bandwidth and latency bound. When you generate token by token, you have to stream the entire model weights through memory for every single token. On traditional architectures with HBM and multi-chip interconnects, you hit a memory wall and a communication wall. Because we have wafer-scale SRAM with petabytes per second of memory bandwidth and uniform on-wafer latency, we excel at single-stream ultra-low latency decode. So they're addressing different parts of the pipeline.

</details>

### SRAM 与 HBM：架构哲学之争与 Groq 整合

**主持人**: 业界当前热烈探讨的另一个焦点，就是关于内存架构的路线分歧。大家都在讨论片上 SRAM 与片外 HBM 的权衡。你们从一开始就坚守全晶圆 SRAM 的道路，并一直走到今天。

<details>
<summary>Original English</summary>

**Host**: I think one thing that people are talking about like you know I'm trying to get to the disagreements in the industry. The SRAM versus HBM debate. You guys have been here the whole time championing SRAM on wafer.

</details>

**Sean Lie**: 我们始终在这里，从未动摇。

<details>
<summary>Original English</summary>

**Sean Lie**: been here the whole time. We

</details>

**Sean Lie**: 我们倡导这一架构路线已经很多年了。看到如今整个半导体产业越来越深刻地认识到 SRAM 在超低延迟推理中的核心价值，这种感觉非常美妙。

<details>
<summary>Original English</summary>

**Sean Lie**: we we've been talking about it for a long time. And it's amazing to see, you know, the the industry really converge on recognizing how critical on-chip SRAM bandwidth is for fast inference.

</details>

**主持人**: 提到 SRAM 架构的芯片公司，比如 **Groq**，在被收购之后你感觉他们有什么变化吗？毕竟你们同台竞技也有一段时间了。

<details>
<summary>Original English</summary>

**Host**: do they feel different post acquisition? I mean, you've been competing with them for

</details>

**主持人**: 竞争了相当长一段时间。

<details>
<summary>Original English</summary>

**Host**: a while.

</details>

**Sean Lie**: 从根本层面来看，并没有本质不同。我认为看到市场上出现多种基于 SRAM 的架构探索是一件极好的事情，这有力地验证了片上高速缓存对于消除内存墙的重要性。

但两者的系统集成方式有着根本差异：Groq 采用的是多颗小芯片（Small Chips）拼接方案，单颗芯片上的 SRAM 容量较小（大约只有两百多兆字节），要运行一个完整的大模型，必须将数百张板卡通过复杂的外部机架铜缆或光纤互连网络拼接在一起。此时，芯片间的外部通信延迟和网络拥塞就成了新的瓶颈。

而 Cerebras 的独特之处在于**晶圆级规模（Wafer-Scale）**——我们在单颗巨大的完整晶圆上集成了数十万个核心和数十吉字节的 SRAM，所有核间通信都走微米级的晶圆内部金属走线，延迟低至纳秒级，带宽是板间互连的数千倍。这是两种截然不同的物理实现维度。

<details>
<summary>Original English</summary>

**Sean Lie**: Uh, to first order, no. I think it's really awesome to see that, you know, SRAM architectures are being recognized. But the fundamental difference is scaling. If you build a small chip with 200-300MB of SRAM, to fit a 70B parameter model you need hundreds of chips connected across circuit boards, cables, and racks. The moment you go off-chip across copper or optical networks, your latency shoots up and network topology dominates. What Cerebras did with wafer-scale is keep all that SRAM and hundreds of thousands of cores on a single continuous piece of silicon, communicating via on-wafer wires at speed-of-light latencies. That architectural difference is night and day.

</details>

### Nvidia Rubin 平台与混合异构趋势

**主持人**: 还有 Nvidia 的 **Rubin** 架构演进路线。

<details>
<summary>Original English</summary>

**Host**: I mean, there's a separate Reuben, you know, strategy.

</details>

**Sean Lie**: 没错，虽然有 Rubin，但还有他们提出的 **LPX** 等扩展架构方案。

<details>
<summary>Original English</summary>

**Sean Lie**: Well, so there's there's there's Reuben, but you know, the LPX itself

</details>

**主持人**: 那原本是他们计划重点发力的方向。

<details>
<summary>Original English</summary>

**Host**: that that was supposed to be where it was.

</details>

**Sean Lie**: 他们原本的设想是将 Rubin 与 LPX 紧密协同。如果大家回想一下，Jensen 在之前的 GTC 大会上……

<details>
<summary>Original English</summary>

**Sean Lie**: It was supposed to be Reuben LPX together, right? Um, if if you guys recall, I mean, the Jensen spent

</details>

**主持人**: 在 GTC 上……

<details>
<summary>Original English</summary>

**Host**: GTC

</details>

**Sean Lie**: 没错，Jensen 在 GTC 上花了将近半个小时来阐述整个计算拓扑：Attention 机制在哪些单元上运行、KV Cache 存放在哪里、视频与多模态生成又在哪些部分处理。当行业巨头开始将系统拆分为如此复杂的专用异构模块时，说明传统单一 GPU 架构在应对极端复杂的全模态实时负载时，已经遭遇了严峻的体系结构瓶颈。

<details>
<summary>Original English</summary>

**Sean Lie**: GTC like half an hour explaining attention runs here and and you know and and the movies run here and KV cache runs there. When you have to partition an architecture into so many disparate pieces, it's an admission that a monolithic general GPU is struggling with the diverse requirements of modern frontier models.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Sean Lie**: 当你从这个角度审视时，就会发现他们试图在现有的多芯片分立封装体系下去拼接这种异构流。

<details>
<summary>Original English</summary>

**Sean Lie**: Right. And so when you start to think about it that way, it's like, well, is it surprising that they have to stitch these complex hierarchies together?

</details>

**主持人**: 所以他们试图通过梯度化的层级设计来弥补这一鸿沟。

<details>
<summary>Original English</summary>

**Host**: so they're going to gradient this into this.

</details>

**Sean Lie**: 我认为实际情况恰恰相反。最终的工程现实是：如果你的底层硬件受限于物理分立芯片的引脚数量（Pin-out）和封装边界，那么在面对超大规模低延迟交互时，层级越多，通信协议转换和数据搬运的开销就越大。

<details>
<summary>Original English</summary>

**Sean Lie**: Well, I I think I think it's I think it's the other way, right? I think what's what's going to end up happening is that as long as you are constrained by standard reticle limits and package boundaries, adding more specialized chips just adds latency hops and interconnect bottlenecks.

</details>

**Sean Lie**: 如果底层架构存在这种物理边界限制，系统复杂度就会呈指数级上升。这也是为什么晶圆级集成能够提供一种优雅得多的解决方案——在一个统一的晶圆平面内解决所有的计算与互连需求。

<details>
<summary>Original English</summary>

**Sean Lie**: All right. Um, you know, if you if you have that limitation in your architecture, then I I think that you're constantly fighting physics at the package boundary. With wafer-scale, the entire fabric is uniform, eliminating those artificial inter-chip boundaries.

</details>

**主持人**: 确实。而且市场规模极其庞大，你们与他们面向的细分市场和工作负载有着明确的差异。

<details>
<summary>Original English</summary>

**Host**: Yeah. And look, the market's large, right? You have a different market than them. And you know that there's room for multiple winners.

</details>

**Sean Lie**: 完全赞同。市场规模极其广阔，不同形态的应用场景催生了多样化的硬件需求。对于大规模批量离线训练和海量吞吐的常规批处理，传统方案有其优势；但对于前沿的实时交互、超高速多轮对话和智能体自主推理，超高速低延迟则是绝对的胜负手。

<details>
<summary>Original English</summary>

**Sean Lie**: No, absolutely. I mean the the the market's large there's a lot of different opportunities for you know different architectures. Batch processing and massive parallel throughput will always have a place, but for real-time interactivity, conversational voice, and autonomous agent loops, ultra-fast low latency is the key differentiator.

</details>

**主持人**: 没错，前沿的极速推理（Frontier Ultra Fast）。

<details>
<summary>Original English</summary>

**Host**: yeah. Frontier ultra fast.

</details>

**Sean Lie**: 极其精准。

<details>
<summary>Original English</summary>

**Sean Lie**: Exactly. Exactly.

</details>

### 芯片架构与模型协同设计（Co-Design）

**主持人**: 我本来还想聊聊今年大会上其他几家备受关注的初创公司，但这正好给了我一个机会，想就一个关键问题向你请教：作为顶尖的芯片架构师，你在设计硬件时，究竟是如何看待底层硬件与上层 AI 模型演进之间的协同设计（Co-design）关系的？

<details>
<summary>Original English</summary>

**Host**: Um, I we was going to go into some of the other companies that were, you know, top of town this year, but it gives me this gives me opportunity. I want to follow up on one thing which is how do you think about the relationship between hardware design and model architecture co-design?

</details>

**Sean Lie**: 关于这个问题，我认为存在两个不同维度的视角。一个是具体的产品落地视角，另一个则是长期的体系结构演进视角。

在芯片工程中，模块化与通用性的平衡至关重要。我们在做芯片架构决策的每一天，都在反复权衡：这里究竟应该放一个硬核的专用加速逻辑，还是保留通用的可编程计算核心？如果把架构做得过于特化（Over-specialized），一旦顶层算法从 Transformer 演进到 SSM（状态空间模型）、RNN 或全新的注意力变体，专有加速器就会立刻沦为废铁。因此，我们在晶圆级芯片上构建的是高度灵活、通用的张量处理单元阵列，并通过软件编译器来调度模型。

<details>
<summary>Original English</summary>

**Sean Lie**: Well, so I I think there's probably two different views here. Um you know, one is the the product view and the other is the long-term architectural view. When we design a chip every single day we're deciding like am I going to hardcode a specific mathematical primitive, or do I make it flexible and software-programmable? If you over-specialize for today's Transformer architecture, what happens when researchers invent new architectures like Mamba, RWKV, or hybrid attention? So our philosophy is to provide massive general-purpose compute, ultra-wide memory bandwidth, and flexible routing, allowing the software compiler to adapt to any model evolution.

</details>

**Sean Lie**: 保持架构的通用性与模块化，使得我们无需担心模型算法的快速迭代。无论是 Dense 稠密模型、MoE 专家混合模型，还是各种新型的注意力机制，晶圆级架构都能凭借庞大的片上带宽和灵活的可编程互连网格提供最优支持。

<details>
<summary>Original English</summary>

**Sean Lie**: modular it's modular and when we design a chip every single day we're deciding like am I going to use this silicon area for fixed functions or programmable cores? By keeping the cores programmable and connecting them over a fine-grained mesh, we can support Dense models, Mixture of Experts (MoE), and future architectures without redesigning the silicon every time the AI algorithms pivot.

</details>

**主持人**: 这种协同设计在多大程度上影响了前沿模型的算法设计？比如在与 OpenAI 的深度合作中，你们是否会共同探讨模型结构的优化，以充分发挥超高速推理的潜力？

<details>
<summary>Original English</summary>

**Host**: How much of that plays into model design, model architecture? So working with OpenAI, you get to co-optimize how the model is structured to take maximum advantage of the hardware?

</details>

**主持人**: 仅仅靠文本生成可能还不够，未来还有端到端语音大模型、Diffusion 扩散模型等。如果涌现出更多交互模态，硬件将如何演进？

<details>
<summary>Original English</summary>

**Host**: It's not enough. There's also voice diffusion. Uh what what if what if there's more interactive modalities coming down the pipe?

</details>

**Sean Lie**: 毫无疑问！随着我们借助硬件能力解锁越来越多的实时交互场景，语音端到端交互、实时视觉反馈以及基于扩散模型的连续流式生成都将变得切实可行。

以语音为例，人类对语音对话的延迟感知极其敏锐——只要交互延迟超过 300 毫秒，对话就会显得极不自然、充满卡顿；而如果要在 300 毫秒内完成语音识别、多步逻辑思考和语音合成，留给大模型推理的时间只有短短数十毫秒。这就要求推理引擎必须以每秒数千 token 的极限速度输出。极速推理不仅让文字交互变得如闪电般迅速，它更是打通真正自然流畅的多模态交互、端到端实时具身智能（Embodied AI）以及复杂多步智能体系统的终极基石。

<details>
<summary>Original English</summary>

**Sean Lie**: Absolutely. And I think as as we start to get into more interactive use cases that we enable through ultra fast inference, voice, real-time video, and diffusion models become practical. In human conversation, latency over 300ms feels disjointed. To achieve sub-300ms total conversational loop including audio transcription, reasoning, and speech synthesis, the core LLM must generate text in tens of milliseconds. That requires thousands of tokens per second. Ultra-fast inference is not just about reading text faster; it is the foundational enabler for natural multi-modal interaction and continuous agentic thinking loops.

</details>

**主持人**: 确实如此。虽然时间有限我们需要继续下一个话题，但业内真正理解这一深远意义的人都对此感到无比振奋。

<details>
<summary>Original English</summary>

**Host**: Yeah. And we we don't have time for this because we want to move on, but uh the people who understand this are really excited about what this unlocks.

</details>

**Sean Lie**: 没错，我对此深信不疑。在深入讨论其他公司之前，这确实是理解整个行业演进脉络的关键抓手。

<details>
<summary>Original English</summary>

**Sean Lie**: Yeah. No, absolutely. I'm I'm a huge believer in that for sure. I think before getting into other hardware architectures, this paradigm shift in latency is the single most important concept to grasp.

</details>

### 行业热点解析：Nvidia 策略与 Etched 争议

**主持人**: 我认为 Nvidia 正在按部就班地执行大家预期中他们该做的一切事情。

<details>
<summary>Original English</summary>

**Host**: I think that uh Nvidia is doing exactly what we all expected Nvidia to be doing, right?

</details>

**Sean Lie**: 就像我前面说的，Nvidia 是一家极其出色的工程公司，他们在自身成熟的 GPU 与 NVLink 生态下持续推高吞吐量。但在面对极致低延迟的单流推理需求时，传统架构受到片间互连与 HBM 带宽物理定律的客观制约。

<details>
<summary>Original English</summary>

**Sean Lie**: Nvidia is executing very well on their roadmap, doing what they've always done best—scaling massive parallel throughput across GPUs. But when it comes to single-stream low latency, they are fundamentally bound by the physics of HBM and board-to-board interconnects.

</details>

**主持人**: 回到最初的比喻：如果我的模型评估任务原本需要 20 个小时，现在按下一个按钮两个小时就能搞定，这种生产力的跃迁是显而易见的。

<details>
<summary>Original English</summary>

**Host**: but my evals take 20 hours. I can hit a button and run it in two hours.

</details>

**Sean Lie**: 没错！但如果能进一步把 2 小时压缩到 2 分钟，它就不再是一个“批处理任务”，而是变成了开发者即时调试、智能体自主自我进化的实时反馈闭环。这就是每秒数千 token 推理速度带来的质变。

<details>
<summary>Original English</summary>

**Sean Lie**: Exactly. Exactly right. But when you take that from 2 hours down to 2 minutes, it stops being batch processing entirely and becomes an interactive development loop. That completely changes how software and models are built.

</details>

**主持人**: 好的，接下来聊聊一些颇具争议的“热辣”芯片。你们官网上有一张对比展示页面，清晰罗列了实测性能数据；然而备受瞩目的初创公司 **Etched** 却始终没有公开具体的基准测试（Benchmarks）和实测数据。你对这家公司有什么看法？

<details>
<summary>Original English</summary>

**Host**: Okay. Um, spicy spicy chips. There's this page that you have on your website that uh this company Etched just doesn't have. No, no numbers, no benchmarks, any takes? That's the talk of the town.

</details>

**Sean Lie**: 关于他们正在做的事情，他们对外透露的技术细节其实非常有限。而且他们对外宣称的架构方案随着时间推移也发生过不少变化。

<details>
<summary>Original English</summary>

**Sean Lie**: Well, so they have said very little about what they're doing. Um uh but what they have said has changed over time.

</details>

**主持人**: 这一点他们自己也是承认的。

<details>
<summary>Original English</summary>

**Host**: which they acknowledge

</details>

**Sean Lie**: 外部的 AI 模型与技术环境一直在剧烈演变，因此调整路线在情理之中。但关键在于，硬件行业是一门极其严谨的硬科技。要想证明一款芯片的真正价值，必须把芯片实际流片出来、点亮系统、在真实数据中心中运行完整的端到端模型，并公开透明可复现的基准测试数据。在没有拿出实际硬件与跑分之前，一切宣称都只能停留在纸面阶段。

<details>
<summary>Original English</summary>

**Sean Lie**: which they acknowledge and and you know the the environment is changing a lot and so that makes sense. But in hardware, talk is cheap. You actually have to tape out the silicon, bring up the boards, build the systems, run the full models end-to-end, and publish verifiable benchmarks. Until you have real silicon running in real data centers, it's all theoretical.

</details>

**主持人**: 但与此同时，他们如今顶着数十亿美元的估值，在资本市场上也绝非无名之辈。

<details>
<summary>Original English</summary>

**Host**: Yeah. But at the same time, like massive valuations now, it's like, you know, not a pushover.

</details>

**Sean Lie**: 在最好的情况下，我非常乐意看到他们或者其他团队能够真正推动系统级创新的边界。因为要真正解决 AI 算力瓶颈，绝对不是单靠在单颗芯片上固化某个注意力算子就能实现的，它需要跨越从芯片、封装、系统到数据中心的全面革新。

<details>
<summary>Original English</summary>

**Sean Lie**: in the best case I would love to see them or others frankly push the boundaries of more innovative system-level architecture, because real AI scaling requires full-stack innovation across silicon, packaging, networking, and software.

</details>

### 数据中心物理极限：供电、散热与背板互连

**主持人**: 包括机架、节点……

<details>
<summary>Original English</summary>

**Host**: the rack node,

</details>

**Sean Lie**: 涵盖机架设计、计算节点、先进封装……

<details>
<summary>Original English</summary>

**Sean Lie**: the rack, the node, the package, the

</details>

**主持人**: 互连通信架构……

<details>
<summary>Original English</summary>

**Host**: the the interconnect,

</details>

**主持人**: 甚至整个晶圆厂和制造系统……

<details>
<summary>Original English</summary>

**Host**: the factory,

</details>

**Sean Lie**: 没错，直至整个生产制造体系。他们或许正在尝试类似的探索，但目前外界很难看清。而在我们看来，真正的系统级挑战在于如何把全套复杂的软硬件基础设施完整地工程化落地。

<details>
<summary>Original English</summary>

**Sean Lie**: the the the factory. Um, they may be doing something like that. It's hard to tell, right? But the real moat is the full-stack engineering execution required to make massive systems work reliably in production.

</details>

**主持人**: 还有复杂的调度算法、流水线并行机制等。

<details>
<summary>Original English</summary>

**Host**: scheduling, pipelining, all those algorithms,

</details>

**Sean Lie**: 所有的这些核心要素缺一不可。在昨天的发布中，我们不仅展示了芯片本身，更展示了支撑这颗庞大晶圆运行的整套供电、液冷、分布式编译与调度系统。

<details>
<summary>Original English</summary>

**Sean Lie**: all of those things, right? And and so, you know, of the reveals yesterday, it's the entire infrastructure—power delivery, liquid cooling, compilers, and collective communication algorithms—that makes wafer-scale practical.

</details>

**主持人**: 顺便说一句，你们的背板供电和集成设计（Backpack），让我联想到了存储巨头们正在进行的技术探索。这是同一类思路吗？

<details>
<summary>Original English</summary>

**Host**: I was going to say like your backpack stuff reminds me of what the memory people are doing. Is that a similar convergence?

</details>

**Sean Lie**: 两者确实存在一定的技术共通性。我们在 CS4 系统中所做的，是通过创新的背板设计将超高密度的电力传输模块直接贴近晶圆背面，从而大幅降低阻抗损耗，实现前所未有的超高功率密度供给。

<details>
<summary>Original English</summary>

**Sean Lie**: there there's a there's a little bit of of that, right? Because you know what we're doing with our power delivery and backpack integration is bringing power conversion and regulation as physically close to the silicon as possible, minimizing resistive loss and maximizing power density delivered directly into the wafer.

</details>

**主持人**: 让我们为观众也盘点一下其他厂商。在内存领域，一些其他名字也格外亮眼。

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh let's leave some hints for people. A couple other names that stood out in memory...

</details>

**Sean Lie**: 顺着这个脉络，**Samsung** 在大会上也分享了关于其 **ZHBM** 等前沿定制高带宽内存的构想。

<details>
<summary>Original English</summary>

**Sean Lie**: along these lines. I I think you know Samsung has some discussions around their ZHBM right um

</details>

**主持人**: 全是存储巨头的手笔。

<details>
<summary>Original English</summary>

**Host**: all memory guys

</details>

**Sean Lie**: 归根结底，构建现代 AI 芯片系统本质上由三大支柱决定：第一是**算力逻辑单元（Compute）**，第二是**互连网络（Interconnect）**，第三则是**内存体系（Memory）**。

<details>
<summary>Original English</summary>

**Sean Lie**: all I mean look in the end there's only three main things to to building a you know a an AI chip right: compute, interconnect, and memory.

</details>

**主持人**: 紧随其后的就是存储架构。

<details>
<summary>Original English</summary>

**Host**: and then there's memory

</details>

**Sean Lie**: 没错。而在超低延迟推理领域，内存带宽与访存延迟的权重变得比以往任何时候都更加关键。

<details>
<summary>Original English</summary>

**Sean Lie**: right and so um and and more and more importantly as we all know for at least in the low latency space, memory bandwidth and latency are the absolute dictating constraints.

</details>

**主持人**: 此外供电和散热同样是不可逾越的物理限制，对吧？

<details>
<summary>Original English</summary>

**Host**: and power and cooling not as major still.

</details>

**Sean Lie**: 不，供电与散热绝对是核心瓶颈！你们刚刚看到我们在 CS4 上进行了大规模的系统重构。

<details>
<summary>Original English</summary>

**Sean Lie**: No, absolutely. I mean, you just did a big redesign. Power and cooling are massive physical constraints.

</details>

**主持人**: 正是这些基础设施支撑着上层的一切算力运转。

<details>
<summary>Original English</summary>

**Host**: Those are those are what's powering all of this, right?

</details>

**主持人**: 我们面对的是实打实的物理极限。

<details>
<summary>Original English</summary>

**Host**: Yeah. I'm just saying, you know, like physical limits,

</details>

**Sean Lie**: 这是一个切中要害的深刻洞察。当我们最初创立 Cerebras 启动晶圆级芯片研发时，很多人质疑说：“你们根本不可能为一整片晶圆提供充足的电力，也绝不可能把数百千瓦的热量散发出去。”

为了攻克这一挑战，我们不得不从第一性原理出发，从零重新发明了一整套定制化的水冷微通道散热系统和直接垂直供电网络。在芯片制造、封装、电力电子和流体力学等多个学科的交叉边界上进行极致创新，才最终打破了物理极限，让晶圆级计算在商业数据中心中成为现实。

<details>
<summary>Original English</summary>

**Sean Lie**: but that's actually a really really good point, right? I think that um when we when we originally started Cerebras, people told us it was physically impossible—they said you can't deliver thousands of amps to a single continuous wafer, and you can't cool a 20kW piece of silicon. We had to reinvent liquid cooling from scratch with micro-fluidic manifold cold plates and design vertical power delivery architectures. Scaling AI hardware today is fundamentally an applied physics and mechanical engineering challenge just as much as a semiconductor challenge.

</details>

### 开源模型与全球生态竞争

**主持人**: 另外像 **华为** 以及国际上其他芯片厂商的最新进展……

<details>
<summary>Original English</summary>

**Host**: Huawei and what what have you

</details>

**主持人**: 许多模型在未经公布运行硬件的情况下就引发了巨大热议。

<details>
<summary>Original English</summary>

**Host**: hyped outside of knowing what it was on

</details>

**主持人**: 很多开源模型在 OpenRouter 等评测榜单上表现优异，甚至完全没有运行在美国传统的主流芯片上。

<details>
<summary>Original English</summary>

**Host**: just model is good doing good in you know open router came out not even running on US chips

</details>

**主持人**: 关于这一点大家私下有讨论吗？行业对此的实际看法是怎样的？

<details>
<summary>Original English</summary>

**Host**: so the TDR is are people talking about it uh what's what what we doing

</details>

**Sean Lie**: 业内当然在密切关注并热烈讨论。因为如今几乎绝大多数前沿的开源大模型……

<details>
<summary>Original English</summary>

**Sean Lie**: I mean I think that absolutely I mean of course people are talking about it right because like the top open models are flourishing globally.

</details>

**主持人**: 虽说不敢说 100%，但……

<details>
<summary>Original English</summary>

**Host**: not 100% but

</details>

**Sean Lie**: 至少 95% 以上的最顶尖开源模型正在全球各地百花齐放。无论是在中国还是其他地区，开源社区的算法创新正在以极快的节奏迭代演进。这充分证明了 AI 算法创新的普惠性。而这也进一步突显出提供高效率、极致吞吐与低延迟的全球化算力基础设施是多么至关重要。

<details>
<summary>Original English</summary>

**Sean Lie**: almost okay 95% right most of the most of the big models most of the big open models that are out there are demonstrating tremendous architectural ingenuity. It shows that algorithmic breakthroughs are happening everywhere globally, and that hardware platforms must remain agile to run whatever weights and architectures emerge from the global AI research community.

</details>

**主持人**: 我猜在 Hot Chips 的私下交流环节，各大厂商的技术骨干们肯定在密室里针对这些前沿动态进行了深入交流。

<details>
<summary>Original English</summary>

**Host**: so I I imagine that should take place as at Hot Chips. It's like the secret room of all you guys. You guys are pushing the envelope.

</details>

**主持人**: 你们正是推动这一切前沿极限的核心力量。

<details>
<summary>Original English</summary>

**Host**: right? that you would be the guys to

</details>

**Sean Lie**: 我们一直在全力以赴推高硬件算力与推理效率的边界，并且对全球开源模型生态的发展保持着极为坚定和积极的支持态度。

<details>
<summary>Original English</summary>

**Sean Lie**: I mean we we have absolutely been been pushing for this and we've been very supportive of of you know the entire open source ecosystem and running any frontier model at maximum possible speed.

</details>

### 结语与未来展望

**主持人**: 太棒了！我知道你日程非常紧凑马上要去赶下一个行程，非常感谢你今天极其慷慨地分享了这么多真知灼见！祝贺你们取得的所有辉煌成就。

<details>
<summary>Original English</summary>

**Host**: Okay. Uh you got to go but you've been very generous with your time. Congrats on all your success. It's been an incredible journey.

</details>

**Sean Lie**: 非常感谢！有时候我甚至还需要掐一下自己，来确认我们一路走来达成这些里程碑是真实的。但对于整个 AI 与芯片产业而言，我们依然处于非常早期的起步阶段。

<details>
<summary>Original English</summary>

**Sean Lie**: Yeah. Yeah. Yeah. Sometimes I still have to pinch myself to remind me that we accomplished all this from an ambitious idea, but we're still in the very early innings of what AI hardware will become.

</details>

**主持人**: 确实仍处于早期阶段。

<details>
<summary>Original English</summary>

**Host**: still early.

</details>

**Sean Lie**: 这一路走来真的很不错，非常精彩。

<details>
<summary>Original English</summary>

**Sean Lie**: That was not bad. That was not bad.

</details>

**主持人**: 再次向你们致以热烈祝贺！期待未来几年与你再次相聚，继续交流。

<details>
<summary>Original English</summary>

**Host**: Uh no congrats uh and uh look forward to meeting up with you in the future year.

</details>

**主持人**: 我们最后必须提个要求：请一定要带给我们更快的 Ultra Fast 速度，更大的算力规模，以及更多革命性的芯片！

<details>
<summary>Original English</summary>

**Host**: We got to ask you know give us ultra fast. Give us bigger give us more.

</details>

**主持人**: 也要把这股超高速的算力浪潮带给所有普通开发者和大众！

<details>
<summary>Original English</summary>

**Host**: No no I mean give give the people ultra fast too. Like

</details>

**Sean Lie**: 哈哈，我们或许可以帮你在 OpenAI 的排队通道里往前挪挪位置。

<details>
<summary>Original English</summary>

**Sean Lie**: we but we but we can probably get you in line at at OpenAI.

</details>

**主持人**: 哈哈，我希望你们没有给 OpenAI 吹太多风让他们把这项超快推理能力仅限内部使用。大家真的需要它，整个生态都需要更强大的模型与更极致的推理速度！

<details>
<summary>Original English</summary>

**Host**: I hope you didn't bias OpenAI too much to, you know, just keep it internally. No, people need it. We need better models and faster access.

</details>

**Sean Lie**: 那是 OpenAI 的产品决策，我们只负责提供最底层、最极致的硬核算力基础设施！

<details>
<summary>Original English</summary>

**Sean Lie**: It's OpenAI's decisions. We're we're just providing the infrastructure.

</details>

**主持人**: 哪怕先给我们开放 **GLM** 或者 **DeepSeek** 的超高速版本也行啊！

<details>
<summary>Original English</summary>

**Host**: Hey, but give us give us GLM. Give us Dec.

</details>

**主持人**: 直接给我们拉来一整个 Cerebras 机架，我们自己来跑！好的，再次非常感谢你今天的做客，真的非常非常感谢！

<details>
<summary>Original English</summary>

**Host**: Just give us our own rack and then we'll run it. Uh, okay. Thank you again for coming. Really really appreciate it.

</details>

**Sean Lie**: 谢谢！

<details>
<summary>Original English</summary>

**Sean Lie**: Yeah.

</details>