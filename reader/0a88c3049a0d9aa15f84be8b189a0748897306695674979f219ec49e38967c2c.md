---
author: AI Engineer
date: '2026-04-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xOP1PM8fwnk
speaker: AI Engineer
tags:
  - diffusion-models
  - latent-representation
  - generative-media
  - model-scaling
  - prompt-engineering
title: 规模化构建生成式音视频模型：Google DeepMind 的幕后技术洞察
summary: 本文由 Google DeepMind 研究科学家 Sander Dieleman 分享，深入探讨了训练大规模扩散模型的核心环节。内容涵盖了数据清洗的重要性、潜空间表示（Latent Representation）的原理、扩散过程的频域分析、Transformer 架构的演进、采样引导（Guidance）的威力以及模型蒸馏与控制信号的最新进展，揭示了 Veo 等前沿模型背后的技术细节。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google DeepMind
  - OpenAI
products_models:
  - Veo
  - Nano Banana
  - Stable Diffusion
  - Jax
  - Glide
media_books: []
status: evergreen
---
### 核心范式：数据清洗与生成的底层逻辑

在构建如 **Veo** 或 **Nano Banana** 这样的大规模生成式媒体模型时，**数据清洗**（Data Curation）是往往被低估但最具决定性的环。在学术研究背景下，由于竞争需要，研究者倾向于在固定数据集上通过微调优化器或模型架构来刷分；但在工业界的大规模模型训练中，改善数据质量的投资回报率通常远高于微调模型细节。数据清洗不仅是确保高保真结果的关键，也是各大实验室秘而不宣的“核心配方”。

目前的音视频生成主要采用 **扩散模型**（Diffusion Models）范式，这与大语言模型（LLM）主要依赖的**自回归**（Auto-regression）有所不同。扩散模型通过一个逐步迭代的精细化过程，而非一次性生成序列，这使其在处理高维音视频数据时展现出独特的优势。

<details>
<summary>Original English Source</summary>
I'm a research scientist at Google DeepMind. I'm on the generative media team. So we work on models like VO and nano banana and I want to this talk is kind of a bit of a behind the scenes perspective on like everything that goes into training these models at scale. It's going to be focused on diffusion models because that's sort of the modeling paradigm that at least nowadays people tend to use for generating audiovisisual data... I think it's really important to emphasize just how important data curation is in training these these large scale models. It's really really essential for high quality results. And like for me coming from a research background, it's actually something like when I was doing my PhD, it's not something that's incentivized... time spent on improving the data is sometimes a better investment of that time than actually sort of trying to tweak the model.
</details>

### 潜空间表示：攻克内存屏障的压缩艺术

处理高分辨率视频（如 1080p，30秒，30fps）时，原始像素张量的大小可达数 GB，单条训练数据就足以挤爆内存。因此，现代模型普遍放弃直接在像素空间训练，转而采用 **潜空间表示**（Latent Representation: 数据的压缩低维表示）。

核心步骤是首先训练一个由编码器和解码器组成的 **自动编码器**（Autoencoder）。编码器将原始像素压缩进一个极小的“瓶颈”层（Bottleneck），虽然空间分辨率大幅下降（例如从 256x256 降至 32x32），但通过增加额外的通道数，模型能够保留关键的高频信息。这种 **有损压缩**（Lossy Compression）保留了数据的拓扑结构，确保了生成模型（如 **Stable Diffusion**）能够高效地捕捉语义内容而非冗余纹理。通过这种方式，数据量可以减少两个数量级，使大规模训练成为可能。

<details>
<summary>Original English Source</summary>
The typical digital representation of visual data is pixels. Once you sort of start scaling up the size of the objects that you're modeling... these pixel tensors in memory get very very large. We're talking many several gigabytes of data to store that in memory... So what we end up doing is we actually use compressed representations. We actually learn our own compressor. We and and we do that based on autoenccoders. That bottleneck is going to learn what what's typically called a latent representation. It's like a more compact representation of the data and that is then the representation that we're actually going to use as a basis for training our diffusion model... especially for video also where you have this extra time dimension, you have even more redundancy, right? You you're often able to reduce the size of these tensors that you have to work with by by two orders of magnitude.
</details>

### 扩散机制：频域分析下的“光谱自回归”

扩散过程的本质是预定义一个损坏过程（逐渐添加高斯噪声直至信息全无）并学习一个 **去噪器**（Denoiser）来反转该过程。直观来看，如果只要求去噪器进行单步预测，由于信息丢失，它只能预测所有可能图像的平均值，导致结果模糊。因此，采样必须采取小步迭代，每一步都重新预测更新方向，甚至在每步后加回少量新噪声以避免误差累积。

从 **傅里叶分析**（Fourier Analysis）的角度看，图像和视频遵循能量随频率下降的幂律关系。扩散过程实际上是一种“光谱自回归”：随着噪声增加，高频信号（细节）首先被遮盖，最后才是低频信号（全局结构）。在采样生成时，模型首先构建低频语义框架，再逐渐填充高频细节。这种由粗到精的生成方式符合人类视觉逻辑，也让模型能在感知上更重要的尺度上投入更多权重。

<details>
<summary>Original English Source</summary>
Diffusion does that by first defining a corruption process destroying information in the image or in the video by adding noise gradually. And then you learn a deninoiser model that tries to remove that noise. If you just ask a diffusion model to do a onestep prediction, you're going to get a very blurry image... The optimizer gives you an update direction. You don't want to take a step that's too large because actually this update direction is only valid locally. After we've done this small denoising step, in many diffusion sampling algorithms, you actually add a little bit of the noise back... it sort of obscures the mistakes that the noiser is making. I've sort of summarized that myself as diffusion is basically spectral auto reggression. You start with the low frequencies and then you gradually add higher and higher frequencies and that corresponds to coarse grain features and fine grain features.
</details>

### 架构演进与采样引导：扩散模型的“越级挑战”

在网络架构方面，虽然早期模型依赖于 **U-Net**（一种最初用于图像分割的卷积神经网络），但现在的趋势是全面转向 **Transformer**。得益于大语言模型领域深厚的工程积淀，Transformer 在规模化训练中的优势显而易见。在视频生成中，现代模型倾向于对整个 3D 像素体积（高x宽x时间）进行联合去噪，或者采用自回归与扩散的混合模式。

扩散模型的一项杀手锏是 **采样引导**（Guidance）。通过对比“有文本提示”和“无文本提示”的预测方向，并人为放大两者之间的差异（即 Delta），引导技术能大幅提升生成的质量与符合度，代价是降低样本的多样性。正是这种机制让扩散模型在参数规模较小时，依然能产出远超其“体重”量级的高质量图像。

<details>
<summary>Original English Source</summary>
People initially started using units for this... but then people figured out actually can we use a transformer for this? The answer is yes of course you can... because we've learned so much about how to scale transformers from the LLM side, it just makes practical sense to also use this for diffusion models. The main thing I want to talk about in the context of sampling is this idea of guidance. What guidance enables you to do is to trade off sample quality for diversity. The quality is going to massively improve to the point where these models are punching well above their weight. If you use a prompt, that corresponds to a difference between two predictions... and we basically amplify this. Guidance is sort of a no-brainer these days. I think a lot of people would be surprised at how bad today's models are if you take guidance away.
</details>

### 效率与控制：模型蒸馏与多维调控信号

为了解决采样步骤过多的效率问题，**一致性模型**（Consistency Models）等蒸馏技术应运而生。其核心思想是学习直接从噪声路径上的任一点预测最终的数据点，将原本需要 50 次迭代的路径压缩到 1-3 步。虽然单步生成在复杂任务中仍具挑战，但在质量与速度的权衡上提供了极大空间。

在控制层面，单一的文本提示已不足以满足用户。现代模型正引入更丰富的 **调控信号**（Conditioning Signals），如基于参考图像的生成（将用户放入视频）、显式的相机运动控制或精准的时间节奏控制。这些信号往往在 **后训练阶段**（Post-training）引入，结合人类偏好优化（如 RLHF 或 DPO），使模型从单纯的数据分布模拟者转变为更具“主见”的内容创作工具。

<details>
<summary>Original English Source</summary>
To speed up the sampling procedure, what we're actually going to try and do is reduce the number of steps that we require. Why can't we just predict where we're going to end up? This is exactly what consistency models do. These models only are as useful as our ability to actually influence what they actually produce. The canonical way is a text prompt. But people want reference based generation... put yourself in it. In video generation specifically, we might want to sort of explicitly control camera motion, the speed of events... It can be quite useful to do that in post-training. Pre-train a model with just a text prompt and then maybe add some of these extra conditioning signals in a post-training phase.
</details>