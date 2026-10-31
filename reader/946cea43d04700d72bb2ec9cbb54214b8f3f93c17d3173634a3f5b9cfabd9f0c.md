---
author: Latent Space
date: '2026-06-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jPtQlILfkhA
speaker: Latent Space
tags:
  - video-generation
  - world-model
  - video-agent
  - generative-ui
  - diffusion-model
title: xAI 访谈录：Ethan He 揭秘 Grok Imagine 研发内幕、世界模型与视频智能的未来
summary: 前 xAI 工程师 Ethan He 分享了在 3 个月内从零构建 Grok Imagine 的历程。他提出“视觉智能本质上源于语言智能”的核心主张，探讨了视频生成与世界模型的本质区别，并预言视频智能体 (Video Agents) 和生成式 UI 将重构人机交互的未来。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Ethan He
  - Elon Musk
companies_orgs:
  - xAI
  - Nvidia
  - OpenAI
  - Google
products_models:
  - Grok Imagine
  - Cosmos
  - Grok
  - Llama
  - Sora
media_books: []
status: evergreen
---
### 硅谷速度：在 xAI 的三个月“从无到有”

**Ethan He** 分享了他在 2025 年中期加入 **xAI** 后的传奇经历。当时团队几乎处于“三无”状态：没有基础设施、没有数据、没有模型。在 **Elon Musk** 极具挑战性的目标驱动下，一支精干的工程师团队在短短三个月内就发布了 **Grok Imagine 0.9**。这种极速研发的核心在于**第一性原理思维**（First Principles Thinking）：团队不断推演数据获取、模型训练迭代和硬件加速的物理极限。xAI 的文化被总结为三句话：**快速移动、实干构建、目标不设限**。

这种效率的背后是极低的沟通带宽成本。团队规模虽小，但每个成员都是顶级人才，每天仅需一次同步会议，其余时间全部投入到构建中。更重要的是，研发的重心并非发明全新的算法，而是通过强大的基础设施支持，每天进行数次端到端迭代，从数据管道和模型训练中揪出微小的 **Bug**。Ethan 指出，模型质量的巨大飞跃往往源于这些细节的打磨，而非架构的剧变。随着 **AI 编程模型** 的进化，计算资源（Compute）再次成为迭代速度的瓶颈，因为工程师实现想法的速度已经从几周缩短到了几小时。

<details>
<summary>Original English Source</summary>

I moved to XAI. At that time I I joined by the time when XI was about to build video models and in multimodel models. There were no no infra no data and no model. And just as just a few engineers we we built it in three months and released the first model Gro imagine 0.9.

I say the most important thing is is a talent. Everyone everyone were very strong and clever very close with each other towards a common goal. So that speed up things a lot. So you reduce the communication bandwidth among people and everyone can can work toward the same goal. It's it's like every day there's not that much meetings on the calendar like maybe like a like a a sync a day and after that it's it's just all building.

A lot of the improvements does not come from new algorithms. It comes from finding small bugs here and there in the data pipeline in the in the model training pipeline. Zoske Z those gave the biggest boost to the model quality.

Compute might become a bottleneck again because previously like if you want to train a new model say you want to generate new synthetic data and then or write a new algorithm it might take a few weeks and during that period of time you don't you might not have experiments to run but now you you can build that thing within a few hours then you can immediately train a model now you have to have enough compute to to try all of the ideas.

</details>

### 技术路径：从合成数据到视频标记化

构建顶级视频生成模型的第一步是先构建图像模型。由于互联网上的视频往往缺乏高质量的文本描述（例如 YouTube 标题可能与画面毫无关联），**合成数据**（Synthetic Data）成为了胜负手。技术流程通常是：从互联网获取原始视频，利用 **多模态大模型**（VLM: Vision Language Model）生成极其详尽的描述。在 **Nvidia Cosmos** 的研发协议中，描述的要求必须达到“能让盲人通过这段文字在脑中重建画面”的精细度。

在架构层面，**标记化**（Tokenization）是解决计算效率的关键。直接在原始像素上训练 Transformer 是不可能的（百万级像素等于百万级 Token），因此必须通过 **变分自编码器**（VAE: Variational Autoencoder）将图像或视频压缩进**隐空间**（Latent Space）。这种压缩不仅包括空间维度（基于 16x16 的 Patch），还包括时间维度。**时间冗余**（Temporal Redundancy）的利用可以显著提高压缩率，但也带来了交互延迟的挑战：高倍率的时间压缩会导致模型响应变慢。此外，**流匹配**（Flow Matching）和**步长蒸馏**（Step Distillation）技术让推理过程从数百步缩减至几步，从而实现了生产级的响应速度。

<details>
<summary>Original English Source</summary>

The data you need is a 100% syntheatic pair of language and image or language to video because on the on the internet actually the the videos don't naturally associate with text. The first step is to you have to generate synthetic pair of language with the videos. So you get the videos from the internet and you you use a VLM to caption the videos. 

In the protocol of cosmos labeling, we require the the objective we gave to the labelers was that you have to describe the video as detailed as possible such that a blind person shares a blob of text can reconstruct what the video is like from from their head.

You need to train a tokenizer which can go from image to latent space and latent space back to image. If you compress temporal dimension you you get a much higher compression rate is because there there's temporal redundancy between frames.

The biggest gain is from the dissolation of these models. So you you can it's called step dissolation. Typically for flow matching models you need like 100 steps. A step distillation is try to learn to generate few step from the model itself. In cosmos I believe we have we have like four step and eight steps.

</details>

### 核心洞察：视觉智能的本质是语言智能

Ethan 提出了一个引发行业热议的核心观点：目前的视觉智能（Visual Intelligence）大部分实际上源于**语言能力**。在 **Grok Imagine** 或 **Cosmos** 这样的系统中，模型通常由两部分组成：一个巨大的**提示词重写器**（Prompt Rewriter，如 Llama 或 Mixtral）和一个相对较小的视频扩散头。扩散模型本身在某种程度上是“迟钝”的，它们只会机械地执行极其详细的指令。如果用户只输入“一只猫”，扩散模型可能会生成一个背景苍白、静态的画面。

真正的智能出现在**提示词扩展**阶段。大型语言模型（LLM）负责理解用户的模糊意图，将其转化为包含光影、动态、场景细节的长文本描述，甚至通过**智能体模式**（Agentic Mode）去检索实时新闻、构思布局。这意味着，视频生成质量的每一次飞跃，本质上都是因为背后的语言模型变得更聪明、更具逻辑性。Ethan 认为，未来的突破点不在于扩散技术本身，而在于如何通过语言模型来管理工具链——包括调用 **Photoshop**、**ffmpeg** 或特定视频编辑工具，进行迭代式的重构和精修。

<details>
<summary>Original English Source</summary>

I have a pretty big claim the visual intelligence are actually mostly coming from language like these video models. Mostly the the gain comes from language model not not coming from the the video model itself like the the video description models themselves.

The prompt writer's task is to take take a user instruction and convert it to extremely detailed description of the video. Because the the video diffusion models I would describe they're kind of dumb because they they take the input instruction literally.

The thinking process you mentioned is from there. If you look at like GPD image like you generate a image in 3 minutes, 3 minute it's it's not all like a pixel generation a lot of time is spending in thinking.

The video models capability increase actually come from language model being more intelligent. I think video agent like it it can unlock more stuff that might you might imagine. The generated UI will be user intention to to the pixels directly.

</details>

### 终局展望：从视频生成到世界模型与生成式 UI

Ethan 严谨地定义了**世界模型**（World Model）与普通视频生成模型的区别。真正的世界模型必须具备三个要素：**实时性**（Real-timeness）、**交互性**（Interactivity）和**长程视野**（Long Horizon）。目前的模型多为几秒钟的片段，而世界模型需要能支持分钟甚至小时级的连贯生成，并能以毫秒级的延迟响应用户的键盘、鼠标或语音指令。他展示了 **Flipbook** 和 **NeuroOS** 的案例，证明了模型可以通过学习屏幕录制，在没有源代码的情况下，仅凭像素想象出一套完整的操作系统界面。

这预示着一个革命性的未来：**生成式 UI**（Generative UI）。在计算成本持续下降的背景下，互联网的呈现形式可能不再是预定义的代码，而是模型根据用户意图直接生成的像素。你可以要求你的邮箱界面看起来像 **TikTok** 风格，通过左右滑动来处理邮件。扩散模型将成为计算机的“前端”，而大语言模型则作为“后端”进行逻辑编排。这种高带宽的人机交互模式，将在 **Neuralink** 脑机接口成熟之前，成为人类与 AI 协作的终极形态。

<details>
<summary>Original English Source</summary>

Word model is like real time interactive long horizon videos. Interaction: allow you to interact with them through keyboard mouse and maybe also voice. Real time: if say the the world model generate the game like how how fast can that game respond? Third part is is long horizon because we are not going to just play with video games just like a few seconds.

The generated UI will be user intention to to the pixels directly. In the future we might have much more powerful OM and coding models running behind the scene and in the in the front end the diffusion model will actually be the front end to show stuff to you.

Humans naturally have the maximum bandwidth when we are looking at things look at videos and and we also have maximum output bandwidth when we are talking. So in the future it might be something like we we talk to AI models and the AI model responds back with the generative UI.

</details>

### 职业转型：为何离开 xAI 转向语言模型

尽管在视频领域取得了巨大成功，Ethan 却选择在此时离开 xAI，并将精力转向大语言模型。这在旁人看来似乎是职业风险，但他的逻辑一脉相承：既然视频智能的瓶颈在于语言，那么解决语言模型的**上下文自我管理**（Context Awareness & Management）和**无限长文本**问题，才是通往通用人工智能（AGI）最紧迫的任务。

他回顾了从 **ResNet** 时代的图像识别，到 **Facebook** 的自监督学习，再到 **Nvidia** 的大规模缩放（Scaling），每一次转型都在追随技术红利的转移。他预测，未来的语言模型将不再被动地接受 **Token** 窗口的限制，而是能像人类一样主动管理记忆，自主决定何时精简、何时调用工具。他相信，即便是在视频和机器人领域，最终的胜负也将由那个能“自我编程”并深度理解物理世界的语言内核决定。

<details>
<summary>Original English Source</summary>

There's a lot of research you want to do that you cannot do at as a company. I realized the fact that the the video models even like in the beginning the game might come from improvement on diffusion technology but this is a point where actually most of the gain come from the language models themselves.

What are you looking for in the next one year? I think one thing pretty pretty interesting I I think might be happening soon is the the language models will be like context aware and manage its own context.

I'm imagining what if the model have access to the whole the code of the agent harness itself and be able to modify it whatever you want. The model can like a program the model can program itself online in test time.

A lot of the core principles how who train large models are are largely the same. Right now the the bottleneck uh for for video models is actually the language part the the agent which which is why I want to go to work more on all.

</details>