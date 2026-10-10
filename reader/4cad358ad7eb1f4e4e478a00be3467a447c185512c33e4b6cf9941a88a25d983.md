---
author: Latent Space
date: '2026-05-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Hxlayqs-IAs
speaker: Latent Space
tags:
  - gemma-models
  - on-device-ai
  - multimodal-learning
  - text-diffusion
  - model-fine-tuning
title: Google DeepMind 的开源 AI 战略与 Gemma 模型解析
summary: 本访谈由 Omar Sanseviero 深入解析了 Google DeepMind 的开源模型 Gemma 4 系列，重点介绍了其在高效参数利用、端侧部署能力、多模态性能以及研发背后的工程协作与开源社区生态，并探讨了文本扩散模型的前景及模型微调趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Omar Sanseviero
companies_orgs:
  - Google DeepMind
  - Google Cloud
  - Android
  - Hugging Face
  - Nvidia
  - AMD
  - Kaggle
products_models:
  - Gemma 4
  - Gemini Nano
  - Gemma 3N
  - Android Studio
  - Med Gemma
media_books: []
status: evergreen
---
### Gemma 4 与模型高效化

**主持人**: Gemma 4、Gemma 3、Gemma Scope、Med Gemma，给我们讲讲重点吧。

<details>
<summary>Original English</summary>

**Host**: We got so much Gemma 4, Gemma 3, Gemma scope, Med Gemma. Give us the TLDR.

</details>

**Omar Sanseviero**: **Gemma 4** 刚刚发布。这是我们迄今为止发布的最强大的开源模型，我们确实致力于在每个参数中压缩尽可能多的智能，并带来了所有这些多模态功能。这就是 Gemma 4。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: Yeah, so yeah, Gemma 4 is just out. This is the most capable open model we've released so far. We really tried to compact as much intelligence per parameter as we could. Bring all of these multimodal capabilities. So yeah, that's Gemma 4.

</details>

**主持人**: 有个有趣的事情，你提到了“有效参数”（effective parameters），而不是“活跃参数”（active parameters）。能解释一下吗？

<details>
<summary>Original English</summary>

**Host**: So one interesting thing, you have this thing with effective parameters, not active parameters. Can you explain what it is?

</details>

**Omar Sanseviero**: 在传统的 **Transformer** 架构中，有一个巨大的嵌入层（embedding layer）。而这种新架构只是 Transformer 架构中 Transformer 块的一点小改动。我们增加了每层的嵌入，这意味着你在每一层都添加了一个嵌入表。令人兴奋的是，你不需要进行完整的矩阵乘法，这更像是一个查找表。Gemma 4 模型是 E2B 的，意味着它有效地在 GPU 中加载了 20 亿参数。实际上它有近 50 亿参数，但其中 30 亿参数可以存在 CPU 或磁盘上，这意味着你可以极快地进行推理。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: Yeah, so pretty much in the traditional transformer architecture you have like this big embedding layer, right? And this new architecture is is more of a small change in the transformer architecture, in the transformer block. Pretty much we add a per layer embedding. So at every layer we add an embedding table. What is exciting is that you don't need to do like the full matrix multiplication. This is pretty much a lookup table. So the Gemma 4 model is a E2B. That means that it effectively has 2 billion parameters loaded into the GPU. It actually has almost 5 billion parameters, but those 3 billion parameters can be in the CPU, they can be in the disk, which means that you can do inference extremely quickly. This is just a lookup table.

</details>

### 端侧部署与应用

**主持人**: 为什么不一直这样做？它能扩展吗？这是开放研究吗？如果我能直接把一半参数卸载到 CPU 上，这看起来非常棒。

<details>
<summary>Original English</summary>

**Host**: And what's the con? Why don't we Why don't we always do this? Can it scale? Is it open research? Like you know, it seems very Okay, if I can just offload half the parameters to CPUs.

</details>

**Omar Sanseviero**: 我们做了很多质量实验，这是真正为端侧（on-device）优化的。我说端侧，指的是在手机、Android、树莓派等设备上运行。当你做得更大时，你通常想压缩更多，或者使用密集架构（dense architectures）或 **MOE**（混合专家模型）。所以这些研究决策对于这些小型用例非常有帮助。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: Yeah, so pretty much here we did lots of quality experimentation and this is really optimized and designed for like on device. And when I say on device I mean like running in a phone, Android, Raspberry Pi, and so on, right? When you go larger you usually want to compact more. You want to have more like dense architectures or MOEs. So this this research This research decisions were very helpful for these small small use cases.

</details>

**主持人**: 听说在中国，超级应用（super apps）正将模型直接打包在应用中进行推理。这是你们的目标用例吗？

<details>
<summary>Original English</summary>

**Host**: I met Cormac and he was telling me that I apparently in China the super apps are shipping models in the app bundle. For inference and just like use among all their super app. Assistants. Yeah. And I don't know is is is that like a target use case for you guys?

</details>

**Omar Sanseviero**: 如果你购买 Pixel 手机或高端 **Samsung** 手机，它们自带 **Gemini Nano**，Gemini Nano 内置于操作系统中，并且是构建在 Gemma 之上的。去年我们发布了 **Gemma 3N**，这是一种真正为手机用例设计的架构，他们使用 Gemma 3N 并进行了一些额外的训练和调整，使模型适用于传统的端侧用例。所以当你购买这些高端手机时，你已经可以直接使用 Gemini 了。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: Yeah, so actually if you install like if you buy a pixel phone or a high end Samsung, they come from with a Gemini Nano and Gemini Nano is baked into the operating system and Gemini Nano is really built on top of Gemma. So last year we released Gemma 3N which was this architecture really designed for phone use cases and they use a Gemma 3N with some additional training, some additional adaptations to make the model good for like traditional on device use cases, right? So pretty much when you buy like these high end phones, you can already use a Gemini out of the box.

</details>

### 模型开发与工程协作

**主持人**: 打造这样一个主流模型幕后需要什么？

<details>
<summary>Original English</summary>

**Host**: What goes into shipping a mean line model like this? Like Yeah. What what's the behind the scenes?

</details>

**Omar Sanseviero**: 这很复杂。Gemma 团队实际上相对较小。我们有两到三名产品经理（PM），一名营销人员，然后是致力于发布模型的工程师和研究人员。当然，还有完整的训练部分，我们如何进行训练后处理、蒸馏、训练后技术等。令人兴奋的是，一旦模型完成，我们就会与许多开源合作伙伴合作，例如 **Llama.cpp**、**Olama**、**MLX**、Hugging Face、**vLLM**、Nvidia 和 AMD。对于 Gemma 4 发布，我们有近 50 个外部合作伙伴。在内部，我们也与许多不同团队合作，比如 Google Cloud、Vertex 模型即服务、ADK 以及 Android 团队。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: It's complex. The Gemma team is actually relatively small. We have like two or three PMs, we have one marketing person and then there is our like engineers and researchers working on shipping this. Of course there's like the full training part, we how do we do the post training, distillation, post training techniques and so on. What is quite exciting is that once we have the model, then we collaborate with a bunch of open source partners, right? So for example, we work with a Lama CPP, Olama, MLX, Hugging Face, vLLM, Nvidia, AMD. So we have almost 50 external partners for every well for the Gemma for lunch, which has been the most complex launch. And also internally, we collaborate with a bunch of different teams. So, think of Google Cloud, Vertex, Vertex models models as a service, ADK, uh and then Android as well, right?

</details>

**主持人**: 人们为什么要使用本地 Gemma 而不是直接使用 Gemini？除了离线或隐私需求之外。

<details>
<summary>Original English</summary>

**Host**: What's the difference? When would someone want to do that versus just using Gemini? Outside of course Outside of the obvious, you're offline or you want the privacy.

</details>

**Omar Sanseviero**: 主要是离线用例。或者如果你想让所有的开发环境都在本地设置，并且不想将任何代码发送到任何 API，你就会使用它。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: Yeah, yeah, it's mostly offline use cases. Right or if you Yeah. Offline or privacy, like if you want to have all of your development set up locally and you don't want to send any code to to any API, you would use that.

</details>

### 多模态与多语言能力

**主持人**: 能谈谈多模态方面吗？

<details>
<summary>Original English</summary>

**Host**: Can we talk about the multi-modality side? Any advances there that you want to highlight or you've been getting good feedback on?

</details>

**Omar Sanseviero**: Gemma 4 是建立在与 Gemini 3 相同的研究基础上的。在多模态方面，小型模型可以理解音频、图像和短视频（30 到 60 秒的视频和音频）。即便是 2B、4B 这样的端侧模型，也能表现出很好的多模态能力。在音频方面，我们有语音识别、语音转翻译文本以及一些语音理解功能。在视觉方面，我们支持对象检测、指向、标注。目前还不支持图像分割，也不支持视频与音频同时处理，这只是还需要做些改进的问题。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: Yeah, so Gemma 4 was built on the same research as Gemini 3, which pretty much means that we benefited from all the improvements that happened with Gemini 3. Multimodal wise, the smaller models can understand audio, images, and short videos. So, 30- to 60-second videos and and audios. For us actually quite long. And even the on-device, like the 2B, 4B, 2B can do very good multimodal. Yeah, for audio we have a speech recognition, we have a speech-to-translated text, and then a bit of a speech understanding. So, you can do like a ask questions about an audio file and so on. So, use cases that are very optimized for like on-device phone use cases. And then on the vision side, we also improved things quite a bit. So, we have object detection, pointing, captioning. We do not have image segmentation, which we know is like one thing that many people have been asking us. But otherwise, like for many things, we do support that. The other thing we do not support yet is video with audio. So, we can understand like video input or audio input separately, but if you want to pass like in the same prompt both a visual part and the audio part, we still need to do some improvements around that.

</details>

**主持人**: 你们在多语言方面也做了很多工作，特别是分词器（tokenizer）。

<details>
<summary>Original English</summary>

**Host**: Gemma is quite important for the multilingual aspect as well. So Gemma supports these 140 languages. Uh You did a lot of work on the multilingual order the tokenizer.

</details>

**Omar Sanseviero**: 分词器基本上是基于 Gemini 的分词器。它非常棒。无论 Gemma 的能力如何，如果你只选择基础 Gemma 模型并针对一种额外语言进行微调，它实际上工作得非常好。它非常擅长捕获不同语言的正确标记，是一个非常好的多语言分词器。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: So the tokenizer has been pretty much based on the Gemini tokenizer. It's extremely good. So independently of the Gemma capabilities, if you just pick base Gemma model and you fine-tune for an additional language, it actually works extremely well.

</details>

### 研究、工程与未来趋势

**主持人**: 你觉得研究和工程现在更紧密了吗？

<details>
<summary>Original English</summary>

**Host**: I do think that research and engineering are closer than people think.

</details>

**Omar Sanseviero**: 是的。现在每个人都有自己的个人研究工程师。很酷的是，研究人员开始采用一些很酷的智能体（agentic）工具了。例如，在团队内部，我们正在构建一些技能来做实验、消融（ablations）和评估，研究团队如何将这些智能体工具作为其研究过程的一部分也非常有趣。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: Yep. Uh there's I mean there's research engineers. Yep. And Mechatronics is probably the easiest single easiest way that engineers can get into research if they want to. Yeah, I think I mean in in big part like so many researchers are doing ablations, right? Like they are just moving the pieces around and seeing what works and what doesn't work. Of course there's like a branch within research that is more much more like architecture design and like a much deeper. But there's lots of very like empirical experimentation and seeing what works, what doesn't work, moving things around, which for me is much more engineering rather than for like research unless we are like writing new activation functions maybe, but Yeah, and something that is cool that is happening is also how researchers begin to adopt some of the cool agentic tools now. So for example, within the team we are building a skills to do experiments and ablations and evaluations and how the research team can use all of these agentic tools as part of their research process is also quite interesting.

</details>

**主持人**: 你对自动研究（auto-research）有什么看法？

<details>
<summary>Original English</summary>

**Host**: Do you have a take on auto research?

</details>

**Omar Sanseviero**: 每个 AI 浪潮都有一个 AutoML 浪潮。这基本上是我们在更高参数空间中的参数搜索。我不认为这可以完全自动化。如果通过智能体代理来自动化你本来就会做的事情，那只是加速实验而已。真正令人兴奋的是做出别人没想到的、具有影响力的发现。我认为下一代微调者将不是那些完全不编码的人。如果是为了特定领域改进能力或添加新行为，他们不需要编写微调代码。但如果你想在架构上进行更深入的研究，我的预感是，至少在未来一两年内，这还无法自动化。

<details>
<summary>Original English</summary>

**Omar Sanseviero**: Every AI wave has an auto ML wave and this is the auto ML wave of this wave. I don't know like with Karpathy experiments it's been quite interesting to see like how things are evolving. I will I don't know what's your take on this. Things are just cooler when he does it. I do think some some part of this is you're just speed running experiments agentically right? The agent The coding agent is more autonomous you can actually go to sleep and it will do the things that you would have done anyway. So you're just kind of automating things that you would have done. I see it differently. I think okay it will be a very exciting time if we have a move 37 from an auto research. If you make an impactful discovery that someone wouldn't have thought of right? So there's a side of okay I have these ideas go run them in the background that's fine. But the the The side is actually when you're shooting off not just paths that you wouldn't have thought about, but you know, trajectories that people wouldn't think about and they work and you make new discoveries. That's the very exciting thing. I think when you have more approach to just token spend and send off, you know, hopefully that becomes possible. Yeah, I do think the next generation of fine-tuners will not be like I mean will be people that are not coding at all, right? Like 1 year ago we had to write like our own code that with transformers or on slots or or whichever library of your choice. I do think as we like keep evolving like most people will be fine-tuning with a couple skills, right? Like Hugging Face has a skills, like all of these libraries have skills. They will just uh prompt the agent to kick off like some experiments and see what works, what doesn't work. And honestly, it's a it's a good middle ground right now. Like all the tools you've mentioned, they let you fine-tune in minutes. You don't need to know what's happening in the order. Yeah, so I think that's where like the direction will be like people that just want to do fine-tunes to improve their capabilities for certain domain or like add some like new behavior. They will not be coding the fine-tuning code, but of course if you want to do like deeper research in the architecture, my hunch is that most likely uh this will not be like automatable at least in the next 1 or 2 years.

</details>