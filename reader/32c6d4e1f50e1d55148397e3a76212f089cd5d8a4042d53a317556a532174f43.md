---
author: a16z
date: '2026-08-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=78-6dUROziQ
speaker: a16z
tags:
  - open-source-ai
  - inference-optimization
  - vllm
  - ai-infrastructure
  - large-language-models
title: 开源AI的未来与vLLM的崛起：对话Simon Mo与Matt Bornstein
summary: 本期访谈深入探讨了开源AI与开放权重模型的生态演进、推理引擎vLLM的技术定位及其作为AI基础设施的核心角色。Simon Mo与Matt Bornstein分享了模型商业化授权、软硬件协同优化、中外大模型竞争及蒸馏技术的政策影响等前沿议题，并展望了未来开源AI实现自主迭代与生态繁荣的发展路径。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Infact
  - a16z
  - NVIDIA
  - OpenAI
  - Anthropic
  - Meta
  - Moonshot
products_models:
  - vLLM
  - GPT-4o
  - Kimi K3
  - Claude
  - DeepSeek-V2
  - Llama
media_books: []
status: evergreen
---
## 开源AI的未来与vLLM的崛起：对话Simon Mo与Matt Bornstein

### 精彩看点与前言

**西蒙·莫 (Simon Mo)**: 一个有趣的思想实验是，如果 **GPU** 的价格下降 99%，我们是否能重新回到一个真正的开源世界？如果在未来，内容审查与安全过滤（Moderation）问题始终无法得到完美解决，那么人们默认会选择**开放权重（Open-Weights）**的路线，因为只有这样你才能确信可以为可信的使用场景完全控制安全护栏。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: The fun thought experiment is if GPUs dropped in price by 99%. Then do we get back to a real open-source world? If moderation is never solved in the future, people will go to open way by default because that is where you know for sure you can control your guardrail for trusted use cases.

</details>

**肖恩 (Sean)**: 你能谈谈 **vLLM** 在这个技术栈中处于什么位置吗？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Can you talk about where VLM sits in that stack?

</details>

**西蒙·莫 (Simon Mo)**: **vLLM** 是一个推理引擎。它有点像数据库和操作系统，是驱动**通用人工智能（AGI）**发展的其他关键底层软件。**Nvidia**、**AMD**、**Google**等芯片厂商，其最新的芯片都会确保 vLLM 能够在其上运行。在很多情况下，他们甚至将 vLLM 作为基准测试工具。我们正在弥合将近 10 倍的性能差距。对于闭源私有模型，通常只有普通模式和快速模式。但对于开源权重模型，每个服务商都可以提供多达 10 种不同级别的速度选择。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: VLM is a inference engine. It is kind of like databases and operating system other critical software to power AGI. Nvidia, AMD, Google, their newest chip will make sure VM can run on them. And in a lot of cases, they use VM as a benchmark. We're bridging almost a 10x gap. For proprietary model, there is a regular mode and fast mode. But for open weight, every provider can offer potentially even 10 different levels of speed.

</details>

**肖恩 (Sean)**: 5年后，开源 AI 模型是否已经完全缩小了与最前沿闭源模型的差距？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: 5 years from now, open source AI models, have they closed the gap with frontier models?

</details>

**西蒙·莫 (Simon Mo)**: 从能力上看，我真的没有看到太大的差距，甚至今天也是如此，因为……

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Capability wise, I don't really see a big gap. Not even today because

</details>

### 推理服务的本质不同

**肖恩 (Sean)**: 今天，我们的嘉宾是 **Simon Mo (西蒙·莫)**，他是 **Infact** 的联合创始人，也是 vLLM 的主维护者——这是一个目前在任意时刻运行在50万张 GPU 上的开源推理引擎。我们还邀请到了 **a16z** 的合伙人 **Matt Bornstein (马特·伯恩斯坦)**。Simon，Matt，非常感谢你们的加入。我想我们首先应该从开源 AI 谈起，聊聊开源 AI 近期的发展史。vLLM 实际上起源于 2022 年底 ChatGPT 诞生之前，当时你们的团队最初只是想让一个缓慢的开源 Demo 运行得更快，但却发现了一堆未解决的系统性难题。你能谈谈，为什么大语言模型（LLM）的推理服务，与大家此前已经熟知的传统机器学习（ML）工作负载有着如此根本的不同吗？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: today we're here with Simon Mo, co-founder of Infact and a lead maintainer of VLLM, the open-source inference engine now running on half a million GPUs at any moment. We're also joined by Matt Bournestein, an A16Z general partner. Simon, Matt, thank you so much for joining us. I think first we should start uh with open-source AI and kind of the more recent history of open source AI. So VLM actually has its origins kind of back in 2022 pre-CAD GPT and your team set out to make a slow open-source demo faster and instead just found this pile of unsolved problems. So can you talk about what made serving an LLM so fundamentally different from the ML workloads everyone already knew how to run?

</details>

**西蒙·莫 (Simon Mo)**: 是的，很高兴来到这里。提供大语言模型服务是一个有着根本性不同的问题，因为运行它需要依赖像 **GPU** 或 **TPU** 这样的加速器，这是一个计算极其密集的过程，需要大量的工程优化，以确保每个用户的请求都能快速、高效地得到响应。具体来说，我们必须处理输入分布的差异、每个请求的长度、非确定性的输出分布，以及推理引擎核心中最关键的批处理（Batching）和调度（Scheduling）问题。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yep, good to be here. So serving large language model is a fundamentally different problem because serving it requires to run it on accelerators like GPUs or TPUs and it it is a computationally intensive process that will require a lot of engineering and ensuring that for each request user can see the LM's response quickly and efficiently. So this typically means we need to handle uh differences in input distribution how long each request is output distribution which is non-deterministic and batching and scheduling a lot more in the at the core of the inference engine.

</details>

### 开源AI的演进节点

**肖恩 (Sean)**: 是的。这个项目团队已经存在了大约四年的时间。不过公司成立的时间要晚一些。Matt，我想把这个问题抛给你。我知道你很早就认识这个团队并一直关注他们。在哪个节点上，你看到它从一个深受喜爱的开源项目，转变为核心的基础设施，进而发展成一家公司的？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Yeah. Um and I so so the team the project has been around for about four years now. Um but the company is a little bit more recent. So I want to throw this out to either of you Matt. I know you've known the team and observed the team for a very long time. So at what point did you see this sort of transitioning from being, you know, a a muchbeloved open-source project to critical infrastructure and then a company?

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 是的，我觉得我们需要把时间稍微往回拨一点。在早期，开源是 AI 模型的常态。我们甚至有一家字面意思就叫 **OpenAI** 的公司，它最初也是倡导开源的，虽然现在……

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Yeah, I mean I think you have to go back a little bit, right? O open source um was was the norm for AI models early on, right? I mean, we literally have this company called Open AI, which,

</details>

**肖恩 (Sean)**: 哈哈，这已经变成了一个笑话。它现在已经不像以前那么开放了，或者说差得远了。但在早期，所有前沿的 AI 工作都是开源的，或者至少发布了开放权重，这与严格意义上的开源稍微有些不同。而且人们基本上可以在他们现有的硬件或电脑上运行这些模型。Simon，我很好奇，你是否还记得，哪一个是第一个让你必须专门去寻找特定软件和一套特定的计算机硬件才能跑起来的模型？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: you know, it's come a little bit of a joke. It's not as open as it once was, or not nearly as open as it once was, but uh but but early on, all all the frontier AI work was being open source or or at least released into open weights, which is a little bit different than true open source. Um and and people could mostly run these models sort of on hardware or computers that they already had. Um I'm I'm curious son like maybe you remember like what was like the first model that like you actually needed to go out and get special software and like a you know a special set of computers to be able to run

</details>

**西蒙·莫 (Simon Mo)**: 可能是 **BERT**，再往前是用于计算机视觉图像分类的 **ResNet**。ResNet 当时就需要运行在 Nvidia K80 上，那算是最早的加速卡之一了。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: probably BERT and before that it was like ResNet for computation like uh like images computer vision classification. So, ResNet already need to run on uh Nvidia K80 which is kind of one of the first

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 在 AWS 和其他云平台上。不过在那个时候，ResNet 甚至还可以在普通的 CPU 设备上勉强运行，只是非常慢。但是到了 BERT，大家就会觉得，哇，你必须在 GPU 上跑它，才能让翻译或其他任务变得高效和快速。这大概是在 2020 年之前的事了。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: on AWS and other places and and but way over but even at this point ResNet you can still kind of run on a uh commodity even CPU devices it's just very slow but for Birch where running at it is like wow you have to run it on GPU to make it anything faster and efficient for anything translation any task so that was like before 2020 even. Yeah,

</details>

**肖恩 (Sean)**: 回想起来真的很有意思。我的脑海里充满了各种回忆。当时 **Hugging Face** 上有上千个 BERT 的变体。你必须去为你的特定任务寻找最合适的 BERT 变体。你是对的，你必须跑去搞硬件。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: it's so funny thinking about this. You're I'm like all the memories are flooding my head. Like hugging face had like a thousand BERT variants on it. You have to go find like the right BERT variant for your particular task and Yeah. And you're right. You had to

</details>

**西蒙·莫 (Simon Mo)**: 我想有些人有自己的 GPU 可以运行。但确实，大多数人都必须去购买云端算力之类的。这很有趣。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: some people I guess had their own GPUs and could run it. But but yeah, a lot of people had to go, you know, provision cloud and stuff like that. That's really funny. And so yeah, so so look I mean um

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: BERT 是早期的语言模型，而现在的模型要大得多、复杂得多，占用更多的显存和计算资源。所以 vLLM 从早期开始，就是为了帮助大家运行这些更强大的模型，因为你很难只靠自己去搞定所有底层的运行逻辑。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: you know BERT was an early language model um that uh you know newer models are much bigger, much more sophisticated, take up a lot more memory, a lot more compute and and and and um you know so VLLM really from the early days right was about running these you know more powerful models that um you know that that that you couldn't just sort of do it you know figure it out on your own.

</details>

**肖恩 (Sean)**: 是的。为了把话题带到今天，我们应该探讨一下，在哪个节点上，开源模型变得越来越大，而 vLLM 真正成为了运行这些前沿开源模型所不可或缺的「关键基础设施」？我们是什么时候开始看到这些大型开源模型进入人们视野的？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Yeah. Um, and I I think like to get us to to this present day, you know, um, I I I think it would be good to to talk about kind of at what point it really became critical infrastructure for these, you know, even larger open-source models and when did we even start to see these larger open-source models kind of come into the field? What we really see the criticality of

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 是的。从创业公司的角度来看，这非常有趣。比如你提到的 GPT-3 或早期的 ChatGPT，那些闭源解决方案在那个时候开始成为一小部分人不可或缺的工具。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Yeah. It's sort of it's sort of interesting from a startup standpoint. um uh you know like like you mentioned sort of GPT3 or like early chat GPT um those closed source solutions were starting to become critical to like a small group of people around that time

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 当时开源虽然存在，但更多是作为一种新奇的事物，或者技术爱好者的玩具。随着前沿闭源模型的性能上限被不断推高，

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: and open source existed but it was a little bit of a curiosity or sort of an enthusiast thing um a as the frontier has expanded you know particularly with closed source models

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 越来越多的开源力量被拉了进来，在幕后扮演着关键角色。这很好理解，即使是现在，像 OpenAI 和 **Anthropic** 的闭源模型在总体上依然更广泛地被使用。但是，我认为我们在大约一年前跨过了一个关键门槛。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: more and more open source has been dragged in as kind of like critical behind it like if that makes sense like like at any given point in time including Now I think models from open AI and anthropic are are kind of more widely used and more critical kind of in general than than open source models. But I do think we passed a threshold in like

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 我想说，大概一年前，

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: I want to say about a year ago

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 当时很多规模较小的初创公司或者新型应用公司开始思考：我们该如何真正构建 AI 产品，而不是仅仅做一个 OpenAI 的简单套壳（Wrapper）？这个问题的答案最终指向了开源。这就是 **Cursor** 所走的路，也是 **Decagon** 和 **Harvey** 正在做的事情，还有许多其他非常强大的应用层初创公司做出了同样的决定——他们不能仅仅构建在闭源 API 之上。他们需要做自己的中期训练（Mid-training）、后期训练（Post-training），以及自己的推理和部署优化。这一切都意味着他们必须在开源大模型的基础上进行构建，因为閉源厂商不会向你开放这样的底层权限。所以我认为在大约一年前，开源变得极其核心，虽然它有时在产品表面并不明显，但如今一些最具创新性的产品和应用实际上都深深地依赖于它。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: where a bunch of smaller companies or like new application companies as they were trying to figure out how do I really build an AI without just being a wrapper on top of open AI. The answer to that question turned out to be open source. I mean this is what cursor did. This is what sort of Decagon and Harvey are are in the process of doing now and and a bunch of other like really really strong application level startups sort of made the determination we can't build just on closed source. We need to do our own mid-training our own post- training our own sort of inference and deployment tricks and all of that means it must be built on top of open source like you know the the closed source vendors won't won't give you the access to do this. So my read is like kind of a yearish ago. Open source became really central in a way that's not always visible because it's it's deeply embedded in some of these products but you know some of the most innovative products and applications now um you know really depend on this very deeply.

</details>

### vLLM的核心角色

**肖恩 (Sean)**: 是的。当那些大型企业决定使用开源模型时，vLLM 在他们的整个技术栈中扮演着什么角色？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Yeah. Yeah. And can you talk about where VLM sits in that stack where where we do have these larger enterprise companies that are choosing to use open source models like where where does VLM sit in the stack for them?

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 是同，基本上每个人都在使用 vLLM。Simon，你应该向大家描述一下它。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Yeah. I mean you should like just about everybody uses VLM. You should describe it.

</details>

**西蒙·莫 (Simon Mo)**: 确实，现在几乎每个人都在使用 vLLM。vLLM 是一个推理引擎，它的核心工作就是将可用的 GPU 算力转化为可以运行的智能终点（Endpoint）。因此，它非常类似于数据库和操作系统，是支撑当前 AI 经济和 **AGI** 发展的底层关键软件。大家使用它来确保推理的高效、廉价和可靠，并能随时跟进最前沿的技术。截至今天，vLLM 已经支持超过 1000 种模型架构，其中包含很多开放权重的模型。当这些模型架构从研究原型转变为全球可用的开放权重模型时，vLLM 会在第一时间提供支持，也就是我们所说的「**Day 0 模型释放**」。此外，vLLM 与各大芯片厂商紧密合作，无论是 NVIDIA、AMD、谷歌、亚马逊还是英特尔，他们发布最新芯片时，都会确保 vLLM 能完美运行，甚至将其作为首选的性能基准。这种将大模型算法与底层硬件紧密融合的交汇点，正是魔法发生的地方，也是 vLLM 的立足之本。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Just about everybody uses VLM. VLM is a inference engine. That means its job is to turn available GPUs into a running endpoint for intelligence. So that means it is kind of like databases and operating system other critical software to power uh this uh economy or power of the AGI that everybody really uses today to ensure they can have uh cost effectiveness, efficiency, reliability and also always staying on the frontier because for VRM we support more than a thousand model architecture up to today and a lot of those are proprietary But also a lot of those are openweight right and a lot of those model architecture when they're becoming transitioning from a research prototype to world accessible open way model architecture they are live on VM on immediately so that's what a process we call day zero model release and additionally VM also work closely with all the hardware vendors so that means across like Nvidia AMD Google and Amazon Intel and lot more their newest chip will make sure VM can run on them and then a lot of cases they use VM as a benchmark to make sure it runs well on them. So this kind of fusion of where models run and where hardware where it gets gets to meet the hardware is where the magic happen and this is where VM is

</details>

**肖恩 (Sean)**: 你之前跟我聊过一些幕后故事。现在发布一个大模型真的很不容易，除了技术工作外，似乎还有很多有趣的「人际戏剧」。有没有什么可以公开分享的幕后故事？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: you've told me some of the behind the scenes stories like it's actually not easy these days model releases it's like a lot of human drama in addition to like technical work I guess are there any stories there that you think are okay to share?

</details>

**西蒙·莫 (Simon Mo)**: 噢，这实际上是一个非常有趣的「协同设计（Co-design）」过程。从大模型实验室的角度来看，他们的天才研究员开发出了极其出色的模型，但他们最头疼的是：如何让全世界都能无缝地运行它？我们合作过的一些实验室本身就在其研究或生产环境中使用 vLLM，所以当我们的团队去找他们，说「嗨，我们是 vLLM 团队，希望为你们的新模型提供 Day 0 推理优化支持」时，他们会说「太棒了，我们已经在 RL（强化学习）训练中用 vLLM 把跑通了，代码都在这，你们帮我们 review 并合并 PR 吧！」但硬币的另一面是，也有一些实验室在系统工程上没有那么强的积累，不太清楚如何把模型适配到开源生态中。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Oh, it's actually a very fun co-design process because from model labs point of view, right, these are brilliant researchers who have built this model. Now their biggest question becomes how do we get this out of the world and make sure everybody's able to use it and run it well. And we have worked with model labs that are um very just because they just use VM already in production or in their research process. they will just done everything for you because this is a moment when we go to them it's like hi we're the VM team and we would like to support your open source model we would like to offer in a way this kind of open source but why gloss service to get your model running well on architecture and then you return and we get the model lab is like oh we got it working already because we're running it for the RL process here you go just review our code and merge our pull request and then on the other end we really have model lab that just don't know how this can work so

</details>

**肖恩 (Sean)**: 因为系统工程并不是他们的核心强项。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: because systems is not like their core.

</details>

**西蒙·莫 (Simon Mo)**: 是的，系统工程不是他们的强项，他们可能使用内部特定的推理引擎进行训练，不知道如何将其转换并适配到广阔的开源生态中。而且，这其实是一个极其复杂的多方协作过程。发布一个新模型，通常需要模型实验室、芯片厂商（主要和次要的）、我们（推理引擎）、**Hugging Face**（模型托管与格式规范），以及数十家首发伙伴（如推理云服务商、云厂商巨头）的共同参与，只有大家都准备就绪，才能确保用户能成功把模型跑起来。举个例子，最近的 **Kimi K3** 模型发布，背后就有着极其紧密的生态合作网络。你可以回想一下 2023 年底到 2024 年初，当时 **Mistral** 首次发布模型时，他们只是简单在推特上甩出了一个 BT 磁力链接（Torrent link），大家都抢着去下载，却不知道怎么跑。我们当时立刻与 Mistral 团队连夜加班，在 vLLM 中实现了对该模型架构的推理支持。那是一个非常让人兴奋的周末，等到了周一，大家还在研究这个模型的架构时，我们和 Mistral 就联合宣布：你现在可以直接在 vLLM 上完美运行它了。这让整个开发者社区能够立刻在我们的基础之上开展工作。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah, cuz sistain is not their core and they have been training or maybe they have their internal inference engine that just don't know how it will adapt to the open way ecosystem. And by the way, this is also a very much a multi-party kind of involvement process. Every model is typically involves um the the model lab, involves the primary or secondary hardware vendors, involves us, involves hugging face who are the model format and like model hub vendors and then depending on the appetite of the model lab involves 10 or 20 different kinds of release partners. These could be inference clouds, these could be public hyperscalers, whoever is going to run this model and you want to them to ensure success the model are running successfully, right? So, uh even up to today if you look at the K3 model release is a whole partnership and a drive to make sure that the model is once the model is released because it's just a few terabytes of files sitting on the internet that people are actually going to be use it really really well. E even from the beginning of 2023 2024 if you remember when Mist draw dropped their first model they just dropped a torrent link for PTP and then everybody's like struggling and trying to get it up and running and then we're working behind the scene with MRO team trying to get the inference engine support working uh in VR and this one of the most uh probably early on exciting weekend that we are able to spend on this and then and after the weekend when everybody's trying to really analyze what's going on and uh Monday Tuesday we'll m and us just announced here you can run it on VLM successfully here and everybody will able to easily reuse a lot of the work and start building on top of it

</details>

**肖恩 (Sean)**: 那确实是一段很有趣的时光，像我这样的爱好者会急急忙忙地去下载模型，然后试着在某个地方把它跑起来。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: that was sort of a fun time where like enthusiasts like me could just like scramble to like download the model and like get it running somewhere

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 我也很高兴现在有专业团队接手了，因为以前我们自己折腾的时候经常跑不通，但那个时候确实充满乐趣。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: I'm glad the professionals have taken over because it never worked like very well but it was it was like a fun moment in time

</details>

### 开放权重的商业考量

**肖恩 (Sean)**: 让我们把话题拉回到现在。最近，开源模型和「模型蒸馏（Distillation）」频频成为新闻焦点。Infact 签署了由 NVIDIA 发起的《开放权重与美国 AI 领导力公开信》，签名者还包括 a16z、**Meta**、**Amazon** 等数十家知名企业。你们能聊聊当时为什么决定签署这封信？你们是在回应市场和舆论中的什么声音？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: so so to bring things you know forward to the present. Um I think open source models and also you know distillation have have been in the news recently. Um Infact signed the NVIDIA open weights and American AI leadership letter uh that that was signed by also A16Z, Meta, Amazon, dozens of other companies. Can you just talk about um you know your decision to sign that and and sort of what what you were really kind of responding to uh in the market and and kind of in the news.

</details>

**西蒙·莫 (Simon Mo)**: 是的。对我们来说，签署这封公开信是为了明确表达一个态度：**开放权重在整个AI生态中绝对不可或缺**。这个世界不能仅仅被几个闭源 API 厂商所垄断，开源大模型的发展和相关学术研究也不应该被限制或禁止。Infact 致力于培育这个生态。虽然推理引擎通常处于模型生产链路的稍下游——我们不参与预训练，也不参与 RL 训练，但我们是「模型与真实世界相遇的交汇点」。我们看到开发者们正在用无穷的想象力将开放权重模型用得出神入化。我认为这里主要有两点诉求：第一是成本，闭源 API 实在太贵了；第二是控制力，企业和开发者希望对自己的基础设施和模型拥有自主掌控权，无论是为了精细化微调，还是为了设置自己专属的护栏。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah. So for us what really want to stand behind is open way absolutely matters in the ecosystem. The world cannot just be controlled by proprietary APIs and where open way open development and research of these models are blocked or banned right uh the pledge that infra sign up for is we want to help and foster this ecosystem where we are typically in little bit downstream of this ecosystem right inference engine are not part of the pre-training process nor the RL process but we're where the model actually meets the world And from what we're seeing, people are just really using their imagination and ability to materialize this imagination of open way model. They're able to leverage these open way models so much effectively. There's almost two pieces to this, right? There's like the the cost thing where it's like the closed models are too expensive and then there's sort of the control thing where I I I want to sort of be in control of my infrastructure and and and in control the model, right? if I need to extend it or or put on my own guardrails or anything. I I'm just curious, have you heard from

</details>

**肖恩 (Sean)**: 来自客户的反馈是怎样的？这两点对他们来说同样重要吗？还是说只要能拥有自主控制权，他们其实也愿意支付较高的硬件成本？或者这取决于不同的应用场景？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: from customers? Like are both those things important to them or or like are they kind of willing to pay as long as they have the control or or maybe they're different use cases?

</details>

**西蒙·莫 (Simon Mo)**: 我认为这随着时间在不断波动。在前几年，控制力是最关键的；而在最近几个月，成本的重要性开始急剧上升。特别是当很多开发者试图从极为昂贵的闭源平台迁移出来，避免那令人咋舌的 Token 账单时，成本就变得极其敏感。然而，控制力其实是成本控制的基石。此外，控制力还关系到系统性能的确定性。例如，对于做语音助手（Voice Agent）的公司来说，他们必须严格控制响应延迟，以满足服务等级协议（SLA）。如果你把最核心的 AI 基础设施托管给第三方闭源 API，对方随时可能会宕机、限流或者调整服务条款，这在商业上是无法接受的危险行为。而通过开源模型，你能够掌控从硬件到算法的每一个细节。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: I think like it fluctuate over time. So control matters a lot over the last few years and then costs just start to matter over the last few months. So cost really matters starting from people trying to migrate off uh right uh very expensive coding plan and like uh every skyrocketing token maxing spend but control has always been on in the backbone of this is they want to even in a way to control the cost right but also it's about controlling the system performance against what they're paying for. So uh there for example for a voice agent company they want to control their own model so that they can make sure the model actually respond by their required time. So the customer when they're on the phone they can ensure the agent is responding according to a SLA and this sometimes is only you can do with your controlled intelligence um because you know the whole hardware you're running and whole system you're monitoring versus signing up for relying on your critical infrastructure with a proprietary API where they might go down any time or have violation of the contract any time.

</details>

**肖恩 (Sean)**: 是的。Simon，回到成本问题，你最近在关于 **Kimi K3** 模型发布的文章中提到，其实一味地去比拼账面成本在某种程度上偏离了重点。对于那些由极具才华的研究人员设计的最前沿开放权重模型来说，在本地运行它们的综合成本甚至和直接调闭源 API 差不多。如果是这样的话，那运行这些开源模型的意义是什么？我们在运行这些前沿模型的过程中，在架构层面上能学到什么？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Yeah. Simon, you also um to to go back to the cost point, you actually make the point um in an essay you recently wrote about the release of Kimmy K3 that actually the economics is besides the point. And it's actually, you know, in in the case of these, you know, just really really great openweight models that are on the frontier that were designed by really brilliant researchers. like like these models are in some cases just as expensive as you know the closed source models. So in those cases kind of what is the point of running them and kind of what do we learn architecturally in the in the course of running them.

</details>

**西蒙·莫 (Simon Mo)**: 是的。首先，开源模型并不总是和闭源模型一样贵，这要看具体情况。关于成本的讨论，在几个月前 **DeepSeek-V2** 推出时就曾经掀起热潮，因为开源模型在很多场景下的确要便宜得多。但在 Kimi K3 这个级别上，它实现了很大的跨越，性能极其接近前沿的 **Claude 3.5 Sonnet** 或 **GPT-4o**。它的部署成本可能高于普通的小模型，但它将接近行业顶尖的智能水平直接带到了你自己的基础设施上。你可以完全掌控它，对其进行细颗粒度的微调。此外，闭源厂商往往只提供「标准」和「快速」两个档位。但是如果你在本地使用 vLLM 运行 Kimi K3 这样的开源大模型，你可以在低成本的慢速推理到高达每秒 400-500 个 Token 的极速模式之间自由配置，这比市面上的闭源快速 API 还要快 2 到 3 倍。此外，还有更关键的数据合规与隐私保护问题，许多闭源 API 并没有做到「零数据留存（Zero Data Retention）」，这对于金融、医疗等合规要求极高的行业来说是不可逾越的红线。这就是为什么 Kimi K3 令人兴奋——它让大家真正「拥有」了顶级智能。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah. So first on cost it's not necessarily they are as expensive as a proprietary model but rather first the cost cost discourse has been discussed over and over again with even GLM 5.2 too a few months back. So, open wheel model are sometimes definitely a lot cheaper and but for this model there's a big sort of step change where we're bridging almost a 10x gap but strike somewhere in the middle where Kim K3 is not as expensive as plot or GPD soul but it is a lot more expensive than JM 5.2 to why is that and I do believe this is the point of where pricing intelligence with the market correctly and understanding where it is and but then the majority part of the discourse should be focusing on wow this model is bringing a opus 4.8 a level model to our own infrastructure that I can use, I can run, I can fine-tune, I can be able to understand exactly how many tokens do I need, understand the exact performance profile. The reason here for example is for proprietary model there is uh regular mode and fast mode and that's only the two switch here. But for openweight when you're running it, every provider can offer potentially even 10 different levels of speed going from like the slowest mode which can be a lot cheaper to um 400 tokens per second uh almost uh up to 500 in many cases that for some workloads and this is typically 2x or 3x faster than the fast mode out there today. So this kind of level of control even in terms of performance and then let alone control over how customer interacting with the model control over data retention keeping in mind fable doesn't have zero data retention policy and at least the a lot of the data need to be staying there and let it control security and compliance a lot more and yeah this is why I'm particularly excited about K3 not just from the cost perspective but a lot more on bringing this level intelligence to something people can own.

</details>

**肖恩 (Sean)**: 在后端优化上，为了调整速度等性能指标，通常需要做些什么？你看到用户在做哪些尝试？有没有一些让你觉得非常聪明的玩法？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: In terms of, you know, calibrating things like speed, calibrating other things just sort of on the back end, what needs to happen and and kind of what are you seeing your users do and like like who who is being really clever about this?

</details>

**西蒙·莫 (Simon Mo)**: 我们发现，当用户启用极速模式时，他们能将模型的潜力发挥到极致。在 vLLM 的优化下，Kimi K3 可以达到每秒 400 到 500 个 Token 的输出速度。这带来了质的飞跃。当开发者与模型交互时，他们不再需要等待模型缓慢地吐出字符，而是几乎瞬间完成执行。这种高吞吐量对于需要频繁与环境交互的任务（例如智能体、代码生成）是非常巨大的利好。此外，Kimi K3 的开源特性允许开发者对其进行专门的微调（Fine-tuning），使其在某些特定垂直工作流上的表现更上一层楼。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: So, we do see users are able to get the maximum benefit out of this model when they enable fast mode. Like what I'm talking about here of course is V on its own fast mode getting up to 400 and 500 tokens per second because it is really a big step change from like the especially when developer interacting with uh the model they can see oh I can really just get my task done faster here and the model are not no longer stuck in thinking rather it is just executing executing interacting with the environment so for premium developer blocking focus task we're seeing is very benefiting but also K3 are just be able to uh have the ability for people to modify it and fine-tune on top of it allow them to make it better for their own workload and this is definitely happening today as well.

</details>

**肖恩 (Sean)**: 你能解释一下，相比于过去，最近发布的这批开源模型在商业许可条款（Licensing Terms）上有什么变化吗？他们为什么做出这样的调整？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Can can you just explain what the um licensing term is for the most recent open source models compared to the past and and and like why you think they're doing that?

</details>

**西蒙·莫 (Simon Mo)**: 是的。在早期，开源模型大多使用宽松的 **Apache 2.0** 许可证，这意味着任何人都可以免费拿去修改、商用，就像是送给世界的一份礼物。但是，训练一个前沿模型所需要的数据、算力和研究成本非常惊人。因此，各大实验室必须寻找一种商业上可持续的闭环。从 Meta 发布 **Llama** 系列开始，条款里就加入了限制：如果你的日活跃用户（DAU）或年营业收入（ARR）超过一定门槛，就需要向 Meta 申请额外的商业授权。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Oh yeah. So historically the um the open way model are just like Apache 2 like our software which is like take it modify it do it whatever you want with it here is a gift to the world and then recently the model lab are trying to understand a way to economically fund their own model development after all model training and research are and the data are very very expensive. So we have been starting to see uh terms even to the llama days for for when meta was releasing llama they do have a term of if you're daily active user or like annual recurring revenue exceed some threshold please enter into a commercial agreement with meta specifically right

</details>

**肖恩 (Sean)**: 我记得那个限额数字非常微妙，全世界只有两三家超级巨头（比如字节跳动、腾讯等）会刚好触发，Meta 显然是为了防范这些潜在竞争对手。但现在的厂商从中得到了启发，试图寻找更具包容性的商业变现机制。毕竟，一旦你开源了权重，大家就可以自己在本地运行，而不一定非得去调你的 API。最近，我们看到非常健康的生态进化，比如 **MiniMax** 发布其模型时带有特定的使用量授权条款；而 Kimi 早期也有关于衍生作品的许可条款。之前 **Fireworks** 和 **Cursor** 基于 Kimi 衍生模型进行的开发，就在社区里引起了很大的讨论。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: I do remember that the numbers were like specifically chosen at that time that you could go find it was like two companies in the world that like fit the definition that they had excluded from their license. Yeah, exactly. But like people have taken a hint from that especially now the labs are trying to figure out a way to economically fund it. especially when they're open source the model everybody can just take it and run it themselves whereas nobody will use your API anymore in many cases while their API currently still taking up shape right and now we're seeing a very healthy ecosystem development starting from even miniax recently when they're releasing the M2.7 model they have a term specifically focusing on uh usage and ki initially also has like if you have derivative derivative works like this is kind of big news back then was um fireworks and cursor about how they built on top of Kimi model.

</details>

**肖恩 (Sean)**: 是的，很多开发者今天都在用 Kimi K3，正是因为它允许定制工作流。我记得之前发生过一些关于衍生模型二次发布的争议。你认为未来几年这种开放权重许可证会如何演变？是否会形成某种统一的行业标准？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: and so a lot of our developer are using like Kimmy K3 today even just uh making sure because it's similar right a developer can run it and customize it to their custom workflow. I do remember that we've had issues before where one company tried to release a derivative work and there was a bit of controversy. How do you see the license evolving over the next few years and is there going to be a clear standard for open weight licensing?

</details>

**西蒙·莫 (Simon Mo)**: 我认为我们将看到更结构化的条款。这种开放权重许可证虽然并不符合开源促进会（OSI）的传统开源定义，但它实际上开创了一个全新的类别，即「带商业上限的开放权重（Open-Weights with Commercial Caps）」。它平衡了各方利益：小开发者和学术界可以完全免费使用，而赚大钱的大型企业则需要反哺生态。这是支撑前沿研究巨大资本支出（CAPEX）的唯一可行路径。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah, I think we will see more structured terms. The openweight license is not OSI-approved open source, but it has created a new category of 'shared-source' or 'open-weights with commercial caps'. It aligns the incentives: small developers get it for free, while large commercial enterprises pay their share. This is the only way to fund the massive CAPEX required for frontier research.

</details>

**肖恩 (Sean)**: 如果我能稍微展开说明一下……

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: And and it's if I I I could just expand on that a little like

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 根据我的观察，这些大模型实验室的做法并不是出于贪婪。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: I I I don't think it's greed at least what I've seen from open source model labs, right?

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 当们谈论开源模型时，实际上谈论的是「开放权重」。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Open source models really what we're talking about are open weights. Yeah.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 是的。AI 模型从根本上说并不是传统意义上的软件。传统的开源软件开发可以通过开发者贡献业余时间、或者大公司允许员工在工作中贡献开源代码来维持，这是一种时间的自愿捐赠。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Right. And and it's just not software, right? Like an AI model is not software at the end of the day. Um, and so open- source software used to be supported by people donating their time or big companies kind of authorizing their employees to donate their time. So, it was sort of like a bulk inind, you know, donation of people's time.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 但这在 AI 时代行不通。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: That really doesn't work in AI,

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 因为你不可能晚上回家和几个朋友出于好玩，就顺手训练出一个前沿开源大模型。这需要数百万甚至数亿美元的计算资源。因此，模型研发必须要有商业闭环和资金回笼机制来支撑。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: right? Like like I can't just like go home at night and like train a frontier opensource model with friends for fun. Like we need millions or billions of dollars of computing resources in order to do it. So, so I think it does support your point that like like obviously there need to be economic incentives and there need to be funding mechanisms in place.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 坦率地说，对于中国的大模型团队来说，这一点可能比美国本土的研发力量更为突出。如果缺乏健康的市场化商业闭环，

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Frankly, I think even more so with with Chinese models than than with domestically produced models, right? If if if there's no source of economic if there's no source of funding

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 比如对于像 **Moonshot** 这样的团队，如果他们不能通过创新的授权机制获得资金，他们的研发就不得不依赖于其他渠道。所以我觉得这种创新的许可证条款是一个非常重要的经济机制，未来我们会看到越来越多类似的实践。这就引出了「可持续性（Sustainability）」的话题：你如何把耗资巨大的前期训练资本收回来，特别是考虑到训练大模型往往要经历多次失败，然后再重新开始？我最近听到一个非常生动的类比，那就是**制药行业**。新药的研发同样耗资巨大且风险极高，如果没有专利保护和商业化回报的保证，就没有公司愿意冒如此大的风险进行科研。一旦新药上市，获得的利润就可以重新投入下一代新药的研发中。目前的 AI 模型开发也非常类似。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: for for moonshot to continue to train models, like we know where the funding will come from instead and it's not like something we right, you know, it's it's government and and things that like are actually worse for us, I think. So like I I I think I think you raised sort of an interesting point that that this is an important economic structure and like I I I think this means we'll see more of this in the future. Would you agree with that? Yeah, it's really about sustainability in the end. is about how do you make sure that all this initial capex almost to train the model fail again and again and train the model again like how do you really pay it back and how do you make sure that there's enough confidence and funding uh from everybody involved to go to do the next one right and I recently heard someone uh I recently heard someone making analogy to this to the pharmaceutical industry is almost like how do you make sure that the R&D process of new drugs are properly funed there and there's proper sustainable uh method to making sure that people are willing to take big risk big bat to go to do research for new drugs and then later because they know there's a uh economic incentive in the end when the new drug released to the market a portion of those of course like besides the just distribution channels right a portion of those uh revenue will flow back to continue to fund the next R&D effort and this is where we're kind of seeing uh similar to the model development now Yeah,

</details>

**肖恩 (Sean)**: 这确实是一个非常有趣且贴切的类比，因为……

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: that's a really interesting analogy because it's like

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 新药一旦研发出来，厂商会拥有极强的排他性专利保护，这是典型的「闭源模式」。但开源 AI 模型不同，一旦你公开发布了权重，任何人都可以直接拿去运行和修改，所以如果不加任何商业条款限制，确实很难收回成本。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: once a once a drug a molecule is released you have the strongest possible control which is nobody else can manufacture it at all right it's like the clo most closed possible source right like it's like a secret um uh but but yeah like in the case of models especially open source models you know once it's there anybody can take it use it extend it etc so so having yeah so having some economics attached to it probably does make sense

</details>

### 研发血泪与社区维护

**肖恩 (Sean)**: 这恰好带出了我的一个疑问，正如 Matt 刚才提到的，开源 AI 与传统开源软件在「维护（Maintenance）」这一概念的动态机制上有着很大不同。对于开源 AI 来说，到底什么才需要被维护？是围绕模型周边的推理和工程基础设施，还是模型本身也需要维护？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: well Actually that that raises a a question for me too which uh Matt you were alluding to this earlier about how different open source models are from the dynamics of open source software maintenance when it comes to opensource AI what actually needs to be maintained is it the infrastructure around it do the models themselves need maintenance at all just kind of what what are those dynamics because I think even the the developer behavior around it is is pretty Yeah. I mean, Simon sort of said this already, but maybe maybe I'll just expand a bit, which is

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 是的。我们通常只能看到一个成功训练运行的最终产物，比如经历预训练、监督微调（SFT）和强化学习（RL）这一系列复杂的流水线。大家听说「这是一个耗资 1 亿美元的训练运行」，但往往忽略了在成功之前，背后可能有五次由于各种集群故障而中途夭折的失败尝试。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: um you know, you you see the results of of a big training run, you know, where training now means it's pre-training and then and then you know, RL kind of um uh you know, mid-training or sort of post- training on these things or you know, pre-training, SFT, RL, right? Like it's sort of a complicated pipeline. We see only the result of this at the end and the numbers are big. You're like, "Oh, you know, this was a $100 million training run." But what you often forget is like there may have been five failed training run, you know, large scale failed training runs before you even get to

</details>

**肖恩 (Sean)**: 那是真正的血泪史。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: the blood, sweat, and tears.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 确实如此。我最喜欢的开源文献之一，就是 Meta 在发布早期 Llama 模型时分享的细节。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Yeah. Yeah. Exactly. One one of my favorite artifacts, maybe we could even track down the link is one of the early llama models.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 他们公布了负责「看护」训练集群的工程师之间的聊天日志。这太逗了，满屏都是「天呐，全乱套了！」、「集群崩了，快救灾！」，然后下一条就是「好了好了，问题解决了，损失函数（Loss）重新开始往下降了。」在模型成功发布前，幕后有极其繁重和痛苦的运维工作。当然，一旦模型发布了，如何让它高效地运行，就进入了 Simon 你们 vLLM 的专业领域了。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: They published the whole like conversation log between the or between the people who were babysitting the training clusters like while the models were training. And it's it's so funny. It's just like, "Oh no, everything's gone wrong." Like chaos. Like panic. And then like then the next comment is like, "Okay, we solved it. Everything's okay." You know, clusters up, losses going down. So there's there's a lot a lot a lot that goes in behind the scenes before these models get released, you know, once they're out there. I guess it's a little bit more in your in your zone, you know, to to kind of make sure it's like operationalized.

</details>

**西慢·莫 (Simon Mo)**: 的确。模型发布之后，会触发一场浩大的社区协同效应。因为每个开发者的集群拓扑结构、可用硬件和应用场景都千差万别。我们需要将一个实验室里的单一用例，推广到世界上的无数种用例中。有人想把它部署在边缘端，有人想以超大规模集群运行，还有人想专门针对语音或者代码生成任务（这两种任务的推理特征截然不同）进行深度定制。这就需要依靠开源社区的合力来进行长期的优化、特化和维护。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Oh yeah. But but this is also a very interesting point. Once it's out there is a whole community effort trying to opt in this model because the model is trained on a given type of hardware on given type of architecture and but when it's out in the wild everybody has different cluster topology and use cases and it's about how do you turn like a use case of one now to a use case of almost infinity. Now you have people trying to adapt it to the edge devices and people trying to run at largest scale ever adapted making sure it runs for voice agent but also for coding agent which are entirely different kind of use cases. So this is a whole community effort trying to further optimize specialize and making sure the running of it is reliable and continue to be able to optimize against it. So that's a whole village uh later uh throughout the open source still to make sure it's improved. Yeah.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 这非常酷，因为这正是开源软件最迷人的地方：全球的开发者都可以参与贡献，让它变得更好。我想回到开头提到的那个思想实验——如果 GPU 算力成本暴跌 99%，我们是否能看到开源的黄金时代？即一个呆在地下室的极客，或者百来个业余开发者，就能利用廉价算力去尝试大公司排队等待的各种前沿算法路线，从而以去中心化的方式推进整个行业？

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: And that's cool because that really is like open source software. I mean and this is what you do but you know like this is like anybody can contribute and and like make these better. Um my the the fun thought experiment is if GPUs you know dropped in price by 99%. Right? Like like if if if GPU based compute actually became you know kind of cheap and widely available like then do we get back to a kind of a real open source world where you know one person sitting in their basement or a hundred people working in their free time can like come up with something new try many of these sort of model training paths that you know that like are in the queue somewhere at one of the big companies and and you know kind of kind of see you know really expand and advance the field collectively.

</details>

**肖恩 (Sean)**: 是的。在人工智能早期，跟上前沿技术所需的算力微不足道，而如今这门槛已经高到令人咂舌。我们该如何让普通的个人和社区开发者重新拥有这种前沿的开发能力？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Yeah. Yeah. Well, I mean, this relates to what you were talking about at the beginning. It's like, you know, at the beginning, the amount of compute you needed to be at the quote unquote frontier was negligible, and now it's just like it's it's enormous. And how do you how do you get that, you know, back to consumer parody again?

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 我以前在播客里说过，但我还要再说一遍：掀起这一轮深度学习浪潮的 **AlexNet**，当时是在区区两张 GPU 上训练出来的。这个数字没有任何缩水，就是整整两张。而今天，如果你只有两张卡，你几乎什么前沿大模型都训练不了。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: I've said this on the podcast before, but I'll keep saying it. AlexNet, first, you know, kind of like neural network to run on on GPUs that we care about, ran on two GPUs. And that's not that's not like there are no missing decimal points or commas in there. literally two now. That would get you literally nowhere.

</details>

### 规模化运行的挑战

**肖恩 (Sean)**: 是的。这也关系到我们收到的另一个问题：尽管推理成本在快速下降，但由于模型和请求的规模（Scale）发生巨变，开发者与模型的交互方式也改变了。在大规模场景下运行 vLLM，系统架构面临的主要挑战是什么？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Yeah. Yeah. Um so I guess this this relates to to another question that we've had which is which is inference has gotten a lot cheaper but also scale has changed how developers interact with models. Can you talk about how scale has changed the core design of vLLM and what the main challenges are when running vLLM at scale?

</details>

**西蒙·莫 (Simon Mo)**: 是的，规模挑战来自两个维度。第一是物理模型大小的规模。当你在由数千个加速器组成的数据中心集群上部署一个超大模型时，像 **All-Reduce** 这样的跨卡和跨机网络通信开销会成为主要瓶颈。vLLM 必须极高效率地协调张量并行（Tensor Parallelism）和流水线并行（Pipeline Parallelism）。第二是用户请求并发的规模。高并发会导致 **KV Cache** 占据的显存呈指数级增长。这也是我们设计 **PagedAttention** 的初衷——它借鉴了操作系统的虚拟内存管理方式，彻底消除了显存碎片，极大地提升了系统的并发吞吐能力。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah. So scale comes from a few points. It comes from whether or not you can run this gigantic model on a data center scale cluster with thousands of accelerators, where network bottlenecks (like All-Reduce overhead) dominate. vLLM has to coordinate tensor parallelism and pipeline parallelism efficiently. But scale also comes from request throughput. Under high concurrency, KV cache memory footprint grows exponentially. That is why PagedAttention was such a breakthrough: it treated GPU memory like OS virtual memory, eliminating fragmentation.

</details>

**西蒙·莫 (Simon Mo)**: 对于这一点，我们一直有种开源情结。我们团队出身于加州大学伯克利分校（**UC Berkeley**），这里孕育了 Spark、Ray 和 Mesos 等伟大的开源系统项目。我们坚信开源平台终将胜出，因为它能汇聚全球最聪明的大脑来共同攻克系统层面的难关。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: I think uh there's two parts to this. Our team always have open source kind of angle. We're from UC Berkeley a long tradition of building systems like Spark, Ray, and Mesos. So we think the open platform wins because it brings the best minds to solve the systems problems together.

</details>

**西蒙·莫 (Simon Mo)**: 这又回到了我们之前讨论的「自主掌控权」问题。在分析社区动态时，我们能清楚看到开放权重开发者是如何逐步接管局面的。正因为有了底层掌控权，他们才能灵活地在推理引擎之上构建专用的服务层、优化请求路由，并依据自身特定的合规要求制定安全策略，无需依赖闭源厂商的黑盒 API。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah, like this kind of goes back to our previous point about control. So for the huggy face incident, they break it down about how the open way developers are taking over. Because of the control, they can implement specialized serving layers, optimize routing, and enforce safety policies that match their own compliance needs without relying on a third party.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 我觉得你刚才提到的社交媒体类比非常贴切。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: I think your social media analogy is a really apt one.

</details>

**西蒙·莫 (Simon Mo)**: 是的。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 因为在这两种情况下，我们都是把原本极为分散的人类活动，集中到了几个头部的平台里。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Cuz like in both in both cases, what's kind of happened is you've taken like distributed human activity and kind of centralized it into platforms.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 这使得内容安全和合规控制在平台上变得可行，平台可以努力扮演好「守门人」的角色。然而，一旦大模型走向开源或开放权重，这堵围墙就彻底不复存在了。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: And that allowed the moderation problem to be tractable, I think, right? It's like, okay, we're going to do our best to police this garden, right? But the moment it goes open-source, or open-weights, the garden wall is down.

</details>

**西蒙·莫 (Simon Mo)**: 没错。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 因为我们不可能去监管世界上的每一个角落，也不可能成为所有人类交流的「世界警察」。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Like we're just we we we just can't police everything. We can't be the world police of like all human communications.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 当前的 AI 领域也在上演类似的一幕：不仅是人类的对话，甚至连具体的工作流也在被逐步委派给本地部署的智能体（Agents）和系统。我们必须接受一个现实，那就是我们无法强行控制每一个下游终端的输出。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: I think something similar is sort of happening in AI right where a lot of work not just talking but work is kind of being delegated to these local agents and systems, and we have to accept that we can't control every downstream output.

</details>

**西蒙·莫 (Simon Mo)**: 确实如此。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 而且 AI 厂商目前并不享有类似社交媒体那样的免责条款。社交媒体平台曾经有《通信规范法》第 230 条的保护，不需要为用户的言论承担直接法律责任。但当前的 AI 实验室正承受着巨大的监管压力。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: And they don't have that carve out, right? Like they don't have that exemption of of like, hey, we're not responsible for what our users build, unlike the Section 230 protections that social media platforms had. AI labs are facing immense pressure.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 这也导致一些闭源公司（比如 Anthropic）在内容过滤的安全策略上，制定了甚至比法律要求的还要严格的道德红线。这完全取决于他们自身的商业定位和品牌取向。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: And like some of them, especially, you know, anthropic like is is kind of going further than even what would be sort of legally required. And they're sort of taking ethical stances on these things, which may be right or maybe right. That's a decision they have to make.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 这是他们需要自主做出的决定。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: legally required. And they're sort of taking ethical stances on these things, which may be right or maybe right. That's a decision they have to make.

</details>

### 展望开源大模型的未来

**肖恩 (Sean)**: 是的。Simon，我们的对话接近尾声了。我想退一步，从更高的维度来审视整个行业的竞争格局。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Yeah. Um, Simon, we're we're nearing the close of the conversation. Um, and I just wanted to take a step back a bit and look at the bigger picture.

</details>

**肖恩 (Sean)**: 作为收尾，展望未来。你认为 5 年之后，开源模型是否能完全抹平与最前沿闭源模型的差距？还是说闭源大厂永远能领先一步？5 年在 AI 行业简直像 500 年那么漫长。不如我们先看 1 年，或者 2 年？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Just I guess to close this out five years from now uh do you think open weight open source AI models have they closed the gap with frontier models completely? Are frontier models always one step ahead? Kind of how how do you see that shaking out? Five years. That's like 500 years. All right. One year. One year.

</details>

**西蒙·莫 (Simon Mo)**: 是的，5 年之后的事情，谁能说得准呢？

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah. Five years. We're Who knows?

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 到时候我们可能都像《机器人总动员》（Wall-E）里描绘的那样，舒舒服服地躺在太空船的漂浮椅上了。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: We're either, you know, we're all going to be like just floating around in our Wall-E pods on our spaceships.

</details>

**肖恩 (Sean)**: 哈哈，确实。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Exactly.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 这就是技术进步的魅力，对吧？

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Progress, right?

</details>

**西蒙·莫 (Simon Mo)**: 没错。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah. Yeah.

</details>

**西蒙·莫 (Simon Mo)**: 在我看来，我们刚才忽略了非常关键的一点：开源大模型和闭源大模型在本质上并没有不可逾越的鸿沟。它们能力上的差距微乎其微，更多的是**分发策略（Distribution Strategy）**和**转商策略（Go-to-Market）**的不同。因为大模型研发的物理规律是通用的：你需要显卡集群、高质量的训练数据，以及卓越的研究人才。但有一个要素正变得越来越重要，那就是**评测与对齐的物理反馈环境（Feedback Environment）**。比如 Kimi K3 之所以能在前端代码生成（Front-End Coding）任务上表现得如此优异，是因为 Moonshot 专门为它构建了一个代码沙箱和预览环境，让模型能够在运行、渲染、获取报错反馈的闭环中不断自我纠错。因此，竞争的关键已经不是单纯去搜集互联网上的静态语料，而是看谁能设计出最好的强化学习反馈环境。未来的演进方向将是基于物理和环境交互的**递归自我提升（Recursive Self-Improvement）**。从这个趋势看，开源和闭源在能力上不会有实质性差别。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Um for for me really at this point, there's kind of a point we haven't talked too much about is what really differentiate open way model from closed way model, right? In the end there's not much differentiation. is a more about the distribution strategy and go to market strategy and the capability wise I don't really see a big gap not even today because for how these model are coming to being they're really starting from the first principle right you have a computer cluster you have training data and you have brilliant researchers uh that group together and really to build this amazing artifact that is this mo pre-trend model and then later our old uh post trend model and that the world can use. But if you look at the ingredients right the one of the most important part just the data it's about who gets what data and then what are the environment you are building to let the model improve on itself and make better right one of the very useful uh benchmark that we have on arena for uh for for K3 has been front-end coding right that means for moonshot they have built some of the best environment for front-end coding Right. They have published amazing demo on the ability for this model to code and then see what the rendered is and then kind of continue looping and this iterative process. Now this is about their environment to improve the model. It's not about just source data. It's not about where they get the data from. other is who can build the best environment and who can make the most sort of uh optimization and algorithmic choices to leverage out of learning from this environment. So the next year is all going to be about that is about how open way model labs are differentiating and really getting the model to meet the real world and have this kind of what people are popular today like recursive self-improvement almost to really improve the model overall. And so really project out in your ear there's not going to be any difference.

</details>

**肖恩 (Sean)**: 完全同意。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Yeah.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 赞同。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Yeah.

</details>

**肖恩 (Sean)**: 你刚才好几次提到了「天才的研究人员（Brilliant Researchers）」这个词。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: And you've used this term brilliant researchers a few times. Um

</details>

**肖恩 (Sean)**: 显而易见，世界各地都不缺乏顶尖的人才。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: there are brilliant researchers everywhere in the world clearly. Um what why do you think

</details>

**肖恩 (Sean)**: 但为什么在美国，最聪明的一批研究员似乎都聚集在 OpenAI、Anthropic 这样的闭源大厂；而在中国，像 Moonshot 这样极具才华的团队却在大力拥抱开放权重？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: you know in the US all the smart researchers are working on closed models and in and in China all the smart researchers are working on open models.

</details>

**西蒙·莫 (Simon Mo)**: 在我看来，优秀的研究员其实只是被有趣的科学问题所吸引，而不是一开始就选定了「开源」或「闭源」的立场。不过，选择开放权重的路线，能够让他们的研究成果瞬间被全球数百万开发者所使用，这种无可比拟的学术和技术影响力确实是巨大的加分项。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: I mean from my point of view they are attracted to interesting problems not necessarily on the open or closed stance but rather but however open way model does give people a really really good boost on the impact of such models. So that is like a plus

</details>

**西蒙·莫 (Simon Mo)**: 真正的研究人员渴望的是推动模型能力的边界。比如这里有一个非常有趣且具有技术含量的例子：在最新的 Kimi K3 模型的架构中，他们移除了主流 Transformer 架构中几乎标配的**旋转位置编码（RoPE，Rotary Position Embedding）**。而做出这个决定并最终在技术报告中解释为什么不需要 RoPE 的人，恰恰就是 RoPE 的发明者本人——**苏剑林（Jianlin Su）**。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: and I I think all the brain researchers are attracted to how to improve the model overall right like actually one interesting point about this um uh maybe fairly technical uh for for this Kim K3 model is they removed a uh rotary positional embedding. So rope has always been there for a lot of the Transformers model and guess who removed it is the inventor of rope who are

</details>

**西蒙·莫 (Simon Mo)**: 是的，他当年写下了第一篇将 RoPE 引入业界的开创性论文，而在这一次 Kimi K3 的技术报告里，他又亲笔撰文解释了在新的训练动力学下为什么可以抛弃 RoPE。这就像是一个完美的闭环。这些优秀、谦逊且务实的研究人员，通过脚踏实地地去解构训练和预训练的奥秘，并将这些成果向全世界开源，不断推翻和迭代自己过去的成就。这真的非常令人敬佩。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: like yeah like the the Jenning he he wrote the first paper introducing rope as a concept and then he now also wrote the explanation of why you don't need it in as part of the technical report in this case model. So like when we read it is like really come full circle is you have all these brilliant uh humble researchers that are able to really study how this work and really study the secret of training and pre-training and share it across the whole world and recognizing and iterating on their past. Right? So really a miracle I would say for this model to come alive. It's so

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 这太有意思了。目前 AI 领域处于一个非常奇妙的状态：在工程实践上，模型的效果出奇的好；但是如果你去问底层的理论物理学家或数学家，他们也无法从数学上完美解释这背后的工作机理。所以大家都在通过快速的迭代和实验来探索未知。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: It's so interesting like you know AI is in this funny zone where empirically it works incredibly well but then you go ask the theorists and they have like no idea what's going on right and so like you have these kind of iterative things where when you go read you know

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 以前你读每一本 Transformer 的教科书，上面都会长篇大论地解释为什么位置编码（Positional Embeddings）是不可或缺的，因为没有它模型就无法理解句子的语序和语义。结果经过几年的大规模实践，当聪明的头脑们往深处再探寻一步时，却发现「其实并不需要，更简单的架构反而效果更好」。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: primer on transformers you read about positional embeddings and why or positional encodings and why it's so important because otherwise you can't sort of like understand meaning you know and then it turns out once you understand one level deeper because we've been doing this for a few years and you have all these smart people like oh actually you don't like it's actually, you know, simpler actually is better. Um,

</details>

### 蒸馏与自主创新

**肖恩 (Sean)**: 是的，而且我们此前……

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: we we didn't um

</details>

**肖恩 (Sean)**: 我们在前半段没有详细讨论「模型蒸馏（Distillation）」，但我认为它与当前的讨论非常相关。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: we didn't talk about distillation much so far in this conversation, but I think it's very relevant to this. Like

</details>

**肖恩 (Sean)**: 我不想简单地问「蒸馏是否正在发生」，因为大家其实都心照不宣地知道业界普遍存在这种操作。但我的问题是：

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: I I have just one question which is like I'm I'm not going to ask like is distillation happening? I think this is kind of speculation on the part of everybody, you know, in the world, but like

</details>

**肖恩 (Sean)**: 你经常与这些优秀的中国团队合作。你认为「蒸馏」是支撑他们能够快速跟上前沿技术的核心要素，还是说这仅仅是他们扎实研发过程中的一个辅助性手段？

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: you work a lot with these Chinese labs. Do you think distillation like is a critical component of what they they do or or or like are they kind of just doing good work and and you know distillation if if it's done is sort of an incidental part of it.

</details>

**西蒙·莫 (Simon Mo)**: 我非常倾向于后者。正如我前面强调的，强化学习（RL）的物理和逻辑环境在今天的大模型对齐中起着决定性作用。这些高度定制化的 RL 训练环境是无法通过简单地调用 API 接口进行蒸馏复制的。你必须自己去构建沙箱、去理解模型的学习演进过程。你无法蒸馏「模型在特定环境下的学习策略」。虽然你可以利用一些前沿模型来清洗和重写数据集，从而生成更高质量的预训练语料，但这是行业内通用的数据工程手段。所以，我完全不认为蒸馏是支撑他们取得如此飞速进展的基石。决定性因素依然是：极其聪明的人才、创新的演算法设计，以及高质量的环境设计。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: I I would lean to the latter part specifically as I mentioned previously environment matters so much today. So these are RO environments right these cannot be distilled like you don't have other people's environment to really distill a copy from is about constructing it understanding also understanding the learning process you cannot distill how the model learns within environment a lot of these are just not doable today um there are things potentially you can do with rewriting the data sets right making better pre-training data but again you can do it with any models any models that are are going to follow instruction are going to be useful in terms of utility there. So I really don't think from currently what we're seeing uh this is a big cornerstone of what's powering the progress today. In the end what's powering the progress is still just um really smart people with very interesting algorithms, data environment and they will produce of course compute they will produce the models.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 我认为这具有非常重要的政策启示。我非常同意你的看法，世界各地都有聪明的人在做极其有深度的事情，这绝不是单纯靠从某个地方「套用」或「蒸馏」数据就能实现的。这在政策制定层面的影响非常深远。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: I think it has really interesting policy implications. I I tend to agree with you by the way that that you know we have smart people everywhere working on a bunch of smart things and it's not about you know distilling data from any one place. um has really interesting policy implications, right? Because it doesn't,

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 因为如果华盛顿的决策者们误以为「只要切断对中国大模型蒸馏闭源大模型数据的渠道，竞争优势就能保住」，那他们就大错特错了。这种想法简单地低估了竞争对手的自主创新能力。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: you know, it's almost tempting if you're if you're sort of, you know, in the White House to say, "Oh, sure. We'll just we'll just turn off distillation. All our problems will be solved." But like,

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 事实是，世界上有很多顶级的研究团队在独立进行着极富创造性的基础性创新。我们必须正视这一点，并在此基础上思考我们的全球竞争战略。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: you know, I think it's more the case that they're just, you know, smart people doing interesting things. And so it's so it's like how do we how do we kind of like adapt adapt to that? I think it's

</details>

**西蒙·莫 (Simon Mo)**: 是的，正是源源不断的创造性创新。我在文章中写过，开源和开放权重极大地加速了创新的步伐。它提供了一条公开的跑道，每一个玩家都可以清晰地观察对手的位置，学习彼此的工程实践，并在前人的肩膀上更进一步。这种公开竞争让每个人都跑得更快。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: Yeah. And creative innovations, right? Like one part in my essay we kind of mentioned that open source and open way really helps innovation because it's set out this racetrack where everybody can learn from each other and see where each person like every each player is in this racetrack and then you'll be able to improve and stand on shoulder of each other kind of to improve yourself. So uh is that is where everybody can move forward faster.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 非常正确。从投资的角度来看，我们目前非常关注全球范围内（无论是中国、美国还是欧洲）致力于开源大模型训练和系统优化的团队。因为只有在完全开放的生态中，才能产生那种令人惊叹的全球协作魔力。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Yeah. Yeah. And one thing we're looking for a lot from an investment standpoint is um is people doing more open source model training all all over the world. Not just in China, you know, not just in the United States, but all right. Because you know, you get that sort of magic of collaboration when everybody's doing it

</details>

**西蒙·莫 (Simon Mo)**: 并最终以此实现某种技术上的共荣。

<details>
<summary>Original English</summary>

**西蒙·莫 (Simon Mo)**: and achieve global harmony in all.

</details>

**肖恩 (Sean)**: 我想这是一个非常完美的结语。Matt，Simon，非常感谢你们今天做客我们的节目。也感谢各位听众的收听。

<details>
<summary>Original English</summary>

**肖恩 (Sean)**: Well, I think that's a good note to end on. Um Matt, Simon, thank you so much for joining us. Thanks for tuning in.

</details>

**马特·伯恩斯坦 (Matt Bornstein)**: 非常感谢，节目很棒，谢谢你，肖恩。

<details>
<summary>Original English</summary>

**马特·伯恩斯坦 (Matt Bornstein)**: Thanks so much. Cool. Thanks, Sean.

</details>