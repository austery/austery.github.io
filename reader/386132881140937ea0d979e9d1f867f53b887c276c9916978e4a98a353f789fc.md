---
author: AI Engineer
date: '2026-06-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=gHs5ZiY80PM
speaker: AI Engineer
tags:
  - diffusion-models
  - model-quantization
  - model-caching
  - model-distillation
  - real-time-generation
title: Nvidia 专家解析：加速扩散模型的量化、缓存与蒸馏策略
summary: Nvidia 专家 Ziv Ilan 探讨了优化扩散模型以实现实时生成的路径。他详细阐述了量化、缓存和蒸馏三大核心技术，并介绍了开源库 FastGen 在降低算力门槛与提升训练稳定性上的实际应用。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Nvidia
  - Black Forest Labs
  - Google
  - DeepSeek
products_models:
  - Flux 2
  - LTX 2
  - TRT LLM
  - Blackwell
  - Hopper
  - FastGen
media_books: []
status: evergreen
---
### 扩散模型与挑战

**Ziv Ilan**: [音乐] 好的。希望大家午餐后都精神饱满，很高兴见到各位。我是 Ziv。我就职于驻扎在巴黎的 **Nvidia** AI 实验室团队，与各个领域的顶尖模型构建者合作。当然，**扩散模型 (Diffusion Models)** 是其中之一，我们将听到几个我们与他们合作的例子。嗯，我们只有20分钟。所以，这显然是介于深入探讨和高层概述之间的混合体。这里的每一个话题大概都需要一整天或一整场会议来涵盖。所以，我会尽量在有限的时间内涵盖所有我能讲的内容，但之后欢迎大家通过 LinkedIn 联系我，或者演讲结束后我也会在这里逗留几分钟。

<details>
<summary>Original English</summary>

**Ziv Ilan**: [music] Okay. Hope everyone are awake after lunch and nice to meet you all. I'm Ziv. I'm in the AI labs team in Nvidia based out of Paris and working with different frontier model builders across a lot of domains. Of course, diffusion is one of them and we'll hear about a couple of examples of work we do with them. Um, we have only 20 minutes. So, obviously it's kind of a mix between going deep and going very high level. Each of these topics will probably be a full day or full um, conference to cover. So, I'll try to cover everything I can within this time frame, but feel free to reach out afterwards either through LinkedIn or I'll stay here a few minutes afterwards.

</details>

**Ziv Ilan**: 那么，事不宜迟，我们来谈谈扩散模型。我假设在座各位都对此有所了解。有没有人不知道视频生成和图像生成在宏观层面上是如何通过**去噪 (Denoising)** 运作的？非常好。好的。其核心理念是，当然，与**自回归 (Autoregressive)** 架构的 **LLM** 不同，你需要通过大量的迭代来对图像或视频进行去噪。通常是在 20 到 50 步之间。我想在过去一年里，我们看到了大量高质量模型的涌现，无论是图像生成（比如 **Flux 2**），还是视频生成（比如 **LTX 2**），或者是 **Google** 的 Nano Banana 及后续几代模型，我们也确实看到了更多实用的应用场景。而一旦我们有了有趣的用例，主要挑战就变成了如何让它真正可用，对吧？我们知道生成视频或图像很酷，但如果我们谈论的是开发者语境或企业语境，它就必须足够快，好的？我们希望它成熟，希望它可扩展，而这些通常都是很难解决的挑战，因为这个生态系统还远不如自回归的 LLM 和 **VLM** 生态系统那么成熟，好的？

<details>
<summary>Original English</summary>

**Ziv Ilan**: So, without further ado, diffusion models. I assume everyone are here knows about it. Anyone doesn't know what video gen image gen how they work on a high level, denoising? Perfect. Okay. The idea is that, of course, unlike auto regressive um, architectures LLM, the idea is that you have a lot of iterations to denoise the image or the video. Usually between 20 to 50 steps and um, we see, I think the last year, an influx of very good high quality models both for image generation, what with flux two, um, video generation, um, LTX two, one, um, Google with the nano banana and and the later generations and we do see a lot of more practical use cases for that. And the main challenge once we have some interesting use cases is how to make it actually usable, right? We know that it's cool to generate videos or to generate images, but now if we talk about a developer context or a enterprise context, this should be uh, fast, okay? We want it to be mature, we want it to be scalable and these are usually the challenges that are hard to solve as this ecosystem is is not as mature as the auto regressive LLM VLM ecosystem, okay?

</details>

### 三大优化策略

**Ziv Ilan**: 因此，我们试图借鉴许多在 LLM 领域被证明行之有效的概念，并逐步将它们“蒸馏”（如果可以借用这个术语的话）到扩散模型的世界中。我们今天会涵盖其中的几个话题，但话又说回来，我们每天都能在这个领域看到越来越多的新研究，我预计在下一届 AI 工程师大会上，这个生态会更加成熟。从用例和赋能的角度来看，实时图像、实时视频显然是终极圣杯，好的？想象一下这能开启多少全新的用例，比如用于机器人技术的世界模型，或者是电脑游戏、内容生成等。它为公司和开发者开辟了许多新的应用途径。而大家共同面临的巨大挑战，当然是延迟，好的？生成第一张图像需要花费大量时间，要达到高质量的内容（比如 1080p 或 720p 分辨率）就更是如此。为了弥合这一差距，我将讨论三个核心概念。当然，这并不能涵盖优化视频与图像生成模型的所有方法，但我会重点介绍**量化 (Quantization)**、**缓存 (Caching)** 和**蒸馏 (Distillation)**。你在实际部署时，不一定要按照我讲的顺序来，好的？通常你会先从蒸馏开始，然后做一些量化，再加入一些缓存机制。但我今天的讲解是从简单到复杂的顺序。最简单的通常是量化。对于那些在 LLM 中尝试过它的人来说，概念是非常相似的。之后我们再讨论缓存和蒸馏。

<details>
<summary>Original English</summary>

**Ziv Ilan**: So, we try to borrow a lot of the concepts we see work very well for LLM and we gradually kind of distill them, if I'll steal this um, terminology, into the world of diffusion models, okay? We'll cover a few of the topics here, but again, it's every day we see more and more research, um, in this domain and I expect this world to be even more mature in the next AI engineer. Use case and enablement, real-time image, real-time video is obviously the the holy grail, okay? Imagine how many new use cases where it's uh, world models for for robotics, for um, you know, computer games, for content generation. It opens a lot of new avenues for companies and developers to use it. And the big challenge together is, of course, the latency, okay? It takes a lot of time to get a first image and then to obviously get a high quality, okay? If we talk about 1080p or 720p uh, content out there. And to bridge this gap, I'll talk about three concepts. Of course, it's not um, covering all the the ways you can optimize your video gen image gen models, but I'll touch on quantization, caching, and distillation. It's not necessarily the the order you'll deploy it yourself, okay? Usually you'll start with distillation, then do some quantization, then some caching, but I started from the simple to the more complex, okay? Simple is usually quantization, okay? For those of you tried it in LLMs, concepts are quite similar. Okay, then we'll talk about caching and distillation.

</details>

### 量化技术与应用

**Ziv Ilan**: 当我们谈论量化时，我们有两种主要方法，好的？**后训练量化 (PTQ)** 和**量化感知训练 (QAT)**。我想说，在很多情况下，我们当然想使用像 PTQ 这样更简单的方法，但我们知道，要想保持图像或视频的质量，它在扩散模型上会稍微复杂一些。我们还知道，这类模型更加依赖注意力机制，这意味着做量化的影响并不像在 LLM 或 VLM 中那么显著。但是，当我们谈论利用 **Blackwell** 和更现代计算设施的先进特性时，它仍然是一个非常容易实现的目标。举个例子，这是我们与 **Black Forest Labs** 合作在 Flux 2 上所做的一项工作，你可以看到通常使用动态量化能带来的效果。你可以使用静态量化，这意味着我们会预先计算所有不同参数的范围，进行部署，然后使用这个静态范围来进行量化。但在本例中，我们使用了动态方法，好的？这意味着一些范围会动态实时计算。再次强调，这是为了确保数据分布与你运行这些模型时可能想要使用的各种数据分布保持一致。

<details>
<summary>Original English</summary>

**Ziv Ilan**: When we talk about quantization, we have two approaches, okay? Post-training quantization and quantization-aware training. Um, I'd say in many cases, of course, we do want to use the more simple approach like PTQ, but we know that at least for that to maintain the image quality, the video quality, it's a little bit more complex with the diffusion models, okay? Uh, we also know that um, this type of models are more attention heavy, which means that the impact of doing quantization is not as impactful as the LLMs VLMs, but it is still quite a low-hanging fruit when we talk about taking advantage of the more advanced um, features of Blackwall, for example, and and more modern uh, compute. In this example, just a work we did with Black Forest Labs on flux two, you can see that using usually dynamic quantization, okay? You don't want to use we can use static, which means that we'll compute all the range of all the different parameters up front, deploy it and use this static range for the quantization. In this case, we use dynamic approach, okay? Which means that some of the range will be computed on the fly, okay? Again, to make sure that the distribution is in line with the different uh, data distribution that you'll probably want to use when running these models.

</details>

**Ziv Ilan**: 这是你完全可以自己动手来实现的东西，好的？我们最近在开源的 **TRT LLM Visual Gen** 仓库中发布了一个很好的例子。你可以开始使用它，看看效果如何。我们为了帮助社区采用这项技术，也在努力协助我们的合作伙伴发布预量化的权重文件。所以，你只需前往 **Hugging Face**，加载量化后的权重文件并开始使用它，好的？如果你不需要微调或做后续的低秩适配器 (LoRA)，这非常方便，你立刻就能看到成效。当然，当我们谈论量化时，它的影响主要体现在内存上。它会占用更少的显存，这意味着你可以在更低端的 GPU 上运行它，无论是消费级 GPU 还是低端的数据中心 GPU，但同时，它也能帮助提升性能，好的？所以，这是工具箱的一部分。再次强调，它的背后支撑着一个完整的生态系统，以确保其实用且高效。就在今天，我还看到了来自 **How Lab** 的关于 FP4 注意力机制的最新研究。正如我提到的，注意力对于这类模型来说是非常沉重的计算负担。因此，我们一直在努力跟进最新的研究，并确保它们能被社区所使用。

<details>
<summary>Original English</summary>

**Ziv Ilan**: It's something that you can either do it yourself, okay? We recently released a good example in our TRT LLM visual gen repository, open source. You can start using it and see how it goes. What we also try to to do to again help the community to adopt it is also to help our partners to do quant- pre-quantized checkpoints. So, you can just go to Hugging Face, load the the quantized checkpoint and start using it, okay? If you don't need to fine-tune or to do some lower adapters afterwards, it's something again, it's quite handy and you can already see the impact. Of course, when we talk about quantization, the impact is both on the memory, okay? It will require less memory, which means you can run it on lower-end GPUs, whether it's consumer GPUs or lower-end data center GPUs, but um, also something that will help you in the performance, okay? So, this is one part of the toolkit. Again, a whole world sitting behind it to make sure that it's something that is effective. Just today I've seen one of the latest research coming from How Lab um, about attention FP4, which again, as I mentioned, attention is quite heavy for this kind of models. So, we do try to follow up with the latest research and make sure it's accessible for your you as a community.

</details>

### 块级缓存机制

**Ziv Ilan**: 好的，现在我们来谈谈第二阶段：缓存。**KV 缓存 (KV Cache)** 是一个只要你多多少少接触过 LLM 和自回归模型，就非常熟悉的术语——大家都在讨论如何高效地使用它、卸载它等等。这同样是一门艰深的学问。但由于扩散模型的特性，它的运作方式完全不同，对吧？我们并不是在每次迭代中生成一个 token。因此，当我们谈及去噪步骤，或是试图利用先前的计算结果来生成未来的图像或视频时，就很难直接套用这类技术。**T-Cache** 是其中一个例子。再次说明，尽管它可能不是最强悍的例子，但它是一个帮助理解这一概念的好例子，好的？在进行去噪步骤时，我们提到了 20 到 50 步，相邻的去噪步骤之间有些区域的内容几乎是一模一样的，好的？所以，我们不一定需要去重新计算它们。T-Cache 的做法是，如果在两次去噪步骤之间的变化极小，它会通过对比并认识到，“好的，现在我不需要为下一个去噪步骤重新计算这部分了”。所以它是一种更全局的方法，针对整个像素空间或潜在空间进行操作，好的？

<details>
<summary>Original English</summary>

**Ziv Ilan**: Okay, when we are talking about the second stage, caching, okay? KV cache is something that, you know, anyone that worked a little bit about in with LLMs, with auto regressive models, it's it's something that everyone talk about how to um, to use it efficiently, how to offload it, etc., etc. Again, it's a whole world. With the characteristics of diffusion models, it's not the same way, right? We don't we don't generate a token every time. So, it's harder to use this kind of techniques when we talk about denoising steps or, you know, getting again, making sure that we use the computation we had before in the way we'll generate future images or future videos. There are some T-cache is one example. Again, it's not um, a very strong example, but it's a good example to understand the concept, okay? While we are doing denoising steps, right? We talked about 20 to 50 steps. There are areas between the denoising steps that are pretty much the same, okay? So, we don't necessarily need to recompute them. What T-cache is doing is, okay, if if there's there was a minimal change or very small change between the denoising steps, it compares it and it understands, okay, now I don't need to um, to recompute for the next denoising step, okay? So, it's more general, okay? It does it for the entire pixel space or latent space, okay?

</details>

**Ziv Ilan**: 而更现代的缓存技术会采用基于分块 (Chunk-based) 的方法。想象一下，不知道你们怎么看，现在我们在这样一个教室里。你们大多数听众都坐着，盯着屏幕，所以画面里并没有太大的变化。但我试图表现得动感一些，所以我走来走去，你们为了跟上我也需要调整视线。这意味着，视频中属于你们这部分的画面不一定需要重新计算。但我这一部分的画面是需要的，好的？所以，我们会将画面隔离开，只对变化的部分重新计算。当然，你可以自定义这个变化阈值，而这实际上能带来巨大的性能影响。我们在这里提供了一些好例子，展示了使用这种方法能够带来的预期性能提升。但是请一定亲自去尝试一下，并且要确保能维持图像的质量，好的？如果你在缓存上处理不当，可能会对图像质量产生非常显著的负面影响。作为内容创作者，在追求世界模型等目标时，在获得性能提升的同时，保持图像质量是你绝对需要确保的事情，好的？这就是缓存机制。我鼓励大家去阅读更多关于不同技术的资料。这已经是刚才我提到的 TRT LLM Visual Gen 中可用的功能。你只需启用一个标志并设置阈值就能进行实验。此外，这类功能也在 **VLLM Omni** (作为 GLN diffusion) 和其他模型服务库中得到了支持。

<details>
<summary>Original English</summary>

**Ziv Ilan**: More modern techniques of caching will do it in a more chunk-based, okay? Imagine that, I don't know, now we are in the classroom here. Most of you audience are sitting, staring at the the screen, so nothing much changes, but I try to be a little bit dynamic, so I'm uh, you know, you still wake up and follow me and which means that this chunk of the video doesn't necessarily need to you guys don't need to recompute. I do need to, okay? So, we'll isolate just this chunk and recalculate that, okay? Of course, you can define the threshold and and this is something that actually makes a lot of impact. We provided here some good examples of the expected boost you can get from using this. Um, but make sure that you try it, of course, and you maintain the quality, okay? Caching is something that if you don't do the right way, can have quite a significant impact on the quality of the image, okay? And as content creators, again, world models, etc., it's something you want to make sure that you maintain while you get the boost, okay? Um, so that's caching. Again, I encourage you to read more about different techniques. This is something that is already available in the TRT LLM visual gen I mentioned. Just a flag you enable and you set up the threshold. Uh, you can experiment with it, but also it's available, you know, in VLLM Omni as GLN diffusion and other serving libraries.

</details>

### 步骤蒸馏与压缩

**Ziv Ilan**: 接下来是蒸馏。这回到了“你不一定需要 50 步”的问题。我们已经看到过很多蒸馏的成功案例，我想说，最震撼的时刻应该是在 **DeepSeek** 首次发布时，他们成功地将一个超大模型蒸馏成多个更小的模型，并在模型尺寸大大减小的情况下获得了可接受的生成质量。但在扩散模型中，我们的目标并不是获得一个更小的模型，好的？你依然会保留相同数量的参数。这里的重点是步骤蒸馏。我们要训练一个学生模型来生成同样高质量的图像或视频，但使用的步骤却少得多。不是 50 步，而是降到 4 步、8 步，在某些情况下甚至是单步生成。同时还要保持质量，这是极大的挑战。想象一下，如果你能大幅削减步骤且不损失质量，就能带来 10倍、甚至 200倍的性能提升。如果我们把目光放回到实时生成上，在当下，这可能是唯一能让我们在保证高质量前提下实现这一目标的方法，好的？我想下一个例子是我们在几周前圣何塞举行的 GTC 大会上做的一个演示，我们展示了两种不同的蒸馏技术，并成功实现了实时生成。这又是目前所有 AI 实验室以及大型科技公司都在翘首以盼的事情，因为这意味着我们终于能够实现流式传输，从而开启大量全新的应用场景。

<details>
<summary>Original English</summary>

**Ziv Ilan**: Distillation, okay? And this goes to the you don't necessarily need 50 steps. Distillation is something we've seen, again, um, I I'd say probably the big bang for distillation was during the Deep Seek first release, how they managed to distill from a very big model to much smaller models and get, um, you know, I would say acceptable quality, but with a much with a much smaller model. In diffusion, the goal is not to get to a smaller model, okay? You'll still have the same number of parameters. This is more about step distillation, okay? Training the model, the student model, to generate as good quality images or videos, but by using much less steps. Okay? Instead of 50 steps, going to four steps, eight steps, in some cases one one shot. Okay? And maintaining the quality. Okay? And this is the big challenge. And imagine if you are able to reduce this significant number of steps, but maintaining the quality, it's something that can give you 10x, 200x improvement in performance. And if we go back to the real-time generation, this is something today it's probably the only way that can get us there in good quality. Okay? Um there is The next one, I think there's some demo we did in the last GTC conference a couple of weeks ago in in San Jose uh with two different um distillation techniques. Um and we got to a real-time generation. Okay? And this is something again that everyone are looking for, all the AI labs, and I'm sure also the bigger players, because this is um this means that we can actually get to again streaming, something that will open a lot of new use cases. Okay?

</details>

**Ziv Ilan**: 那么，我们该如何实现呢？在谈论蒸馏时，我们总是需要一个教师模型和一个学生模型。目前在蒸馏方面，我们有两种主要方法。第一种是基于轨迹的 (Trajectory-based)，这意味着我们会试图教会学生模型去完全模仿教师模型在去噪步骤中的运行轨迹。第二种是基于分布的 (Distribution-based)，这意味着我们只关注最终的输出分布。我们希望学生模型在最后能达到与教师模型相同的终点，但我们会让它自己去摸索该怎么到达，而不是死板地照抄整个轨迹。现在更为常见、生成质量也更好的技术，主要是基于分布的方法。同时我们也看到了许多融合这两种方法的尝试。在最近发布的 **FastGen** 视频中，他们实际上设法采用了一种混合方法，既保持了高质量，又获得了更稳定的训练过程。我把蒸馏留到最后讲的原因，在于它通常是一项后训练阶段的技术，好的？这意味着，如果你想让它跑在你自己的数据上，你需要准备特定数据供该技术使用，而且你希望它能良好地收敛，对吧？否则就会变成“垃圾进，垃圾出”。因此，它需要更庞大的算力，花费更多的时间，并且对熟练度要求也更高。这也是一个仍处于探索和学术驱动阶段的领域，目前已经有大量不同的技术路线出现，未来也会有更多，但我们开始看到一些更成熟的方案崭露头角。一些优秀的例子已经在最新的开源模型中得到了展示，当然，闭源模型的构建者们也同样在使用这种方法。

<details>
<summary>Original English</summary>

**Ziv Ilan**: So, how do we get it? Okay? We are When we talk about distillation, we always have a teacher model and a student model. Currently, we have two main approaches when we talk about distillation. Okay? One is trajectory based, which means we'll try the student try to teach the student how to follow the trajectory of the denoising steps as the teacher is doing. Okay? And the second is distribution based, which means we'll only look at the output distribution. Okay? We want the student to get to the same point at the end, but we'll let the student understand how to get there. Okay? And not by following the exact trajectory. Okay? The more common, I would say, and better quality technique these days is distribution based. And we also see a lot of ways that can be combined. These techniques can be combined. Um in the last FastGen video release, they actually managed to do kind of an hybrid approach that maintain the quality, but also got to a more stable um um training. The challenge and why I kept it to the last is that distillation is usually it's a post-training technique. Okay? Which means that you let's say if you do want it to work with your data, it's something you'll need to use some data for that technique, and and you want it to converge in a good way, right? Cuz otherwise, it will just um you know, garbage in, garbage out. Okay? So, it will require more compute, it will require more time, also more proficiency. Again, as it's an exploratory, still or research-driven domain, there's a lot of different techniques out there, and we expect more to come, but we are starting to see more mature techniques coming. And some very good examples shown in again in with the latest open-source um models. Of course, um closed-source model builders are also using this approach.

</details>

### 开源库FastGen

**Ziv Ilan**: 所以，**FastGen** 是诞生于我们 NV 研究团队的一个开源项目。你可以去库里看看，里面包含了很多不同的技术。它并不是一个单一的蒸馏技术或方法，核心理念在于，由于我们要处理的大模型实在太复杂了。很多最新的视频扩散模型都有着 200亿、300亿甚至 400亿参数量，而且我们预期它会发展到千亿参数的级别。它们需要进行后训练，需要跨 GPU 的张量分片并行 (Scale Sharding)。所以为了管理这一切，我们推出了 FastGen 来为你梳理这个流程，让你能够专注于模型质量的提升，并去微调你想要使用的具体技术配方。如你所见，这里有一个可选的训练数据选项。如果你不打算使用特定数据，你完全可以使用开源数据，它能起到一定的作用，对吧？而且我们对那里的结果实际上很满意。但如果你的使用场景有着非常特定的数据分布要求，我们建议你使用你自己的数据来进行微调。我们在这里引用了一些结果，这种加速不仅体现在耗时更短上，还体现在它能够用少得多的算力来实现实时生成。就像我刚才提到的，在 GTC 大会上，我们只用了一张 **Blackwell B200** GPU 就能生成接近实时，甚至是完全实时的视频，这取决于输出质量的要求。所以，如果你想实现这一点，我们强烈建议你研究一下这些方案，好的？

<details>
<summary>Original English</summary>

**Ziv Ilan**: So, FastGen is something that came out of our NV research group. Okay? It's an open-source repository. You can go There's a lot of different techniques there. Okay? It's not a distillation technique or method, but the idea is that because it's so complex when we talk about, you know, large models. Okay? A lot of the new video diffusion models are 20, 30, 40 B parameters, and we expect it again to get to hundreds of billions of parameters. It requires post-training, requires scale sharding across different GPUs. So, to manage all of this, we came with FastGen as a way to structure this process for you and enable you to focus only on the quality and, of course, you know, fine-tuning the exact recipe that you want to use. Like you can see, there's an optional training data here. If you're not using um well, you can always use open-source data, and it will work up to a point, right? And and we're actually happy about the results there. Um but if you want it to work for or if your use case have very specific data distribution, then we recommend you to use your own data for the fine-tuning. Um some of the results quoted here, okay? Um you know, the speedup, it's actually something we got not just The speedup doesn't come only in time, it's also in using much smaller uh much um less compute, I would say, to get to real-time. Okay? We got again in in GTC, as I mentioned, we got to one GPU of Blackwell B200 to generate near real-time video or real-time again, depends on the quality of the output. So, it does something that we highly recommend you to look into if you want to get to this point. Okay?

</details>

### 自回归与扩散融合

**Ziv Ilan**: 我们也预期很多其他的自回归技术将会被引入，并逐渐在视频生成和图像生成领域大放异彩。我们也看到许多新的模型构建者正在采用类似 **Transfusion** 或自回归扩散的方法。在这种方法中，你使用扩散模型生成某一帧，然后以自回归的方式一帧一帧地往下生成。所以，我们预计在这个领域会涌现出大量这类技术，但这在很大程度上仍然是由学术研究驱动的。不过这也确实是一个非常值得关注的优秀例子。我认为，这套工具最具价值的地方在于，所有技术都是增量叠加的，好的？你可以同时使用这个、那个和另一个技术。你不必非要做单选题：我只做蒸馏，或者只做量化，或者只做上下文并行。外面有很多不同的技术，它们全都可以叠加使用。你可以从最简单的量化开始尝试。如果量化已经能够满足你的需求，那停留在这一步就好。如果不够，那么让我们引入多卡部署，做一些上下文并行，然后再加入缓存机制。最后，去尝试最具影响力的蒸馏技术。我希望能看到更多的开发者亲身实践，尽早实现你们的实时性能突破。去尝试一下吧。这些都是你们触手可及的开源资源。我们已经增加了对各种开源模型的支持，无论是 Flux 2 系列、LTX 2 系列还是其他正在推进中的模型。希望未来能看到大家为这个生态做出贡献，让视频扩散模型达到我们在 LLM 和 VLM 领域所见到的那种高度。

<details>
<summary>Original English</summary>

**Ziv Ilan**: We do expect again, a lot of the other autoregressive techniques to come and gradually um be relevant for the video video generation and image generation. We also see a lot of new model builders working kind of a transfusion or autoregressive diffusion approach. Okay? So, you use a diffusion to generate a um um a frame, sorry, but then it generates frame after frame in a autoregressive manner. So, again, we expect a lot more of these techniques to get into this domain, but it's still a lot of research-driven. So, make sure again, this is one very good example you can take a look at. And I think the best value about it is all of it is incremental. Okay? You can use this plus this plus this. You don't necessarily need to decide, okay, I'm doing only distillation or only quantization or only context parallelism, or again, there's a lot of different techniques out there, and they're all incremental. Okay? So, you can start with quantization, as I mentioned, which is the easier approach. If it's good enough for you, stay there. If not, okay, let's move to now multi-GPU, maybe do some context parallelism, maybe add some caching techniques. Okay? And then last and the most impactful, that's a distillation. And again, hope to see a lot of you trying it and getting into the real-time performance now. Try it yourself. Okay? All of it are open-source resources that you can use. We have added support for the open-source models as well, whether it's the one family, Flux 2 family, LTX 2 family, and other ongoing. So, hopefully, you'll be able We will be able to see also you guys contributing to this um and making video diffusion as good as we see with LLM VLM.

</details>

### 观众问答互动

**Ziv Ilan**: 我想我的时间差不多到了。如果有一两个问题，我很乐意尝试解答。如果没有，我们可以让大家休息一分钟。
[掌声]

**观众**: 一般来说，微调这样一个模型大约需要什么样的硬件要求？因为现在想要获取 **GB200** 并不容易。另外在数据集方面，你看到在使用这些模型时效果比较好的数据集通常有多大？

<details>
<summary>Original English</summary>

**Ziv Ilan**: Um I think I'm almost at time. So, if there is maybe one, two questions, happy to try and answer. If not, um we can let you 1 minute of breathing.
[applause]

**Audience**: On average, what would you say is like are the requirements for you to fine-tune this model? Because access to GB200s are are not that easy right now. And in terms of data set, how big are the data sets that you've seen work well with some of these models? 

</details>

**Ziv Ilan**: 好的，刚刚的问题是关于微调所需的算力，以及需要的数据集，为了让大家都能听清。关于蒸馏的一大好处在于，你不需要 GB200，对吧？你可以使用 **Hopper** 架构的卡，你可以使用 H200、H100、B200，你知道的，B300。所以，你并不必然需要像预训练阶段那样投入极大规模的算力，但你依然需要算力。这并不是说你随便拿一个实例就能跑起来。当然，这取决于模型的参数规模，对吧？如果你的模型很小，比如现在有只有 20亿、40亿参数的小型视频生成模型。这显然所需的算力就会显著下降。在数据方面，我认为很重要的一点是你要确保自己知道如何进行评估。这样你就能明白，只是使用通用的数据集，与使用你针对特定用例的特定数据，这两者之间有何区别。在这种情况下，我们确实看到了差异。对于比较通用的演示，我们不使用任何特殊的数据集，效果也很好。但如果是蛋白质生成或类似的高要求任务，那显然就需要更专门的数据。我的时间到了，我想，但在他们把我赶下台之前，还有其他问题吗？好的，我想我们可以会后交流。谢谢大家。
[音乐]

<details>
<summary>Original English</summary>

**Ziv Ilan**: Okay, so the question was about the compute needed for that, and then from the data set needed for that, just for everyone to hear.
Um what's good about distillation is that you don't need um GB200, right? You can do it with Hoppers, you can do it with H200, H100, B200, you know, B300. So, it's not necessarily that you need very big compute as you do for pre-training, uh but you still need to compute. Okay? So, it's not something you just, you know, take your um I don't know, just one instance and start doing it. Of course, it depends on on the size of the model, right? If your model is small, you have video generation models that are very small, 2 B, 4 B parameters. So, this will require obviously much less compute. On the data front, I think it's very important to make sure that one, you know how to evaluate. Okay? So, you can understand what's different if I just use just a general-purpose data set versus your specific data requires for your use case. And in such cases, we have seen differences. So, for the more general demos, we don't do use any special data set, and it works well. But again, if it's something that, I don't know, protein generation or something around that, that it will require, you know, something more specific. I'm at time, I think, but yeah, until they kick me out. Anyone other question there? Okay, we can afterwards, I think. Thanks, everyone.
[music]

</details>