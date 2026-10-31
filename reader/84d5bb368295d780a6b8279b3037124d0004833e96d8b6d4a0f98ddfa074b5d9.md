---
author: AI Engineer
date: '2026-05-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3jGAU2sbAyY
speaker: AI Engineer
tags:
  - text-to-speech
  - generative-ai
  - audio-codec
  - diffusion-model
  - latency-optimization
title: TTS 架构演进：为什么现代语音合成越来越像大语言模型？
summary: 来自 Mistral AI 的科学家 Samuel Humeau 深入解析了语音生成（TTS）的最新技术趋势。文章探讨了如何借鉴 LLM 的 Token 化思路处理音频，详细介绍了 Mistral 开源的 40 亿参数 TTS 模型架构，包括自回归解码、音频编解码器（Codec）以及利用扩散模型生成音频块的技术细节，并展望了实时语音交互中延迟优化的关键策略。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Samuel Humeau
companies_orgs:
  - Mistral AI
  - Meta
products_models:
  - Mistral TTS
  - GPT-4o
media_books: []
status: evergreen
---
### 语音合成的新纪元：从离线阅读到实时交互代理

在语音生成技术领域，我们正见证着一场深刻的范式转移。过去，**文本转语音**（Text-to-Speech: TTS）的主要场景是离线的，比如朗读博客或长篇文章。然而，现在“王者级”的应用场景已转向**智能代理**（Agents），特别是作为对话式 AI 的交互界面。在这种架构中，中央聊天代理负责处理高质量的文本交互，而 STT（语音转文本）和 TTS 则分别作为其“耳朵”和“嘴巴”。

在这种交互模式下，**延迟**（Latency）是成败的关键。为了降低用户感知的延迟，系统必须实现实时处理：当 STT 检测到说话结束时，转录文本应已准备就绪；同理，TTS 必须在生成首批音频包后立即开始播放，而不是等待整段音频计算完成。理想的状态是，随着大语言模型流式输出首个 Token，机器就能同步开始发声。

<details>
<summary>Original English Source</summary>
Nowadays the the king use case for text to speech is uh its usage within agents and in particular it's used to interface uh with a chat agent. typically in a pipe like this uh where you have a central chat agent that does text to text but does it extremely well and you want to talk to it so you add a speech to text and you want it to speak to you so you add a text to speech. As everybody in this conf will tell you the latency is key here. It's also very important that as soon as you have the first audio packets, you you you start to um to voice them out. This way, the perceived latency is lower. If you're going to interface a chat assistant uh which is a real time text input text to speech where uh as soon as you have the first token of the LLM uh the the machine starts to speak.
</details>

### 声音克隆与数字身份的品牌化

Mistral 最近发布的开源 TTS 模型展现了极强的**声音克隆**（Voice Cloning）能力，仅需几秒钟的原始音频样本即可模拟特定人类的声音。这种技术不仅能完美复刻音色，还能跨语言推理，例如让一个带有浓重法国口音的人说流利的英语。这种能力的普及正在改变企业对**语言身份**（Vocal Identity）的认知。

过去，大公司只在广告中关注品牌声音；但在未来，就像每家公司都会精心设计网页视觉形象一样，声音身份将成为品牌识别的核心组成部分。用户可以通过开源工具配置特定的声音，甚至在解决复杂问题时通过克隆自己的声音来进行自我对话。目前，虽然 Mistral 开源了模型权重，但在声音克隆的编码器部分仍保持闭源，以防止该技术被滥用于恶意伪造他人声音。

<details>
<summary>Original English Source</summary>
I mentioned the the voice cloning here. Uh this model can like only need a few second to clone the voice of someone. It's also very good at inferring how a person would speak in in another language. So for example, this is a French voice and we can clearly recognize a very strong French accent. Currently actually a lot of large company they do have a concept of vocal identity and they do care in their branding about how they sound uh in their branding identity, it would be the same for the voice identity. We didn't release this part like the the encoder part. Uh, which means it's the only thing that is missing for you to clone your own voice. we just didn't want to give everybody the ability to clone any voice.
</details>

### 音频 Token 化：借鉴 LLM 的序列建模思路

从底层物理角度看，音频是随时间变化的压力波信号，每秒包含数万个采样点。历史上的 TTS 经历过单词拼接、逐采样生成等阶段，而现代实验室正趋向于一种共同的模式：**语言建模化**（Language Modeling Problem）。既然人类已经极其擅长处理 Token 序列，那么将音频转化为 Token 序列并使用**自回归解码器**（Auto-regressive Decoder）生成，就成为了当前的主流选择。

然而，音频的 Token 化比文本难得多。一个文本 Token 包含的信息量较小，而高质量音频（如 200kbps 的 MP3）每秒需要巨大的比特率。如果直接将文本简化为字幕轨道，信息量会骤降至每秒约 15 bit，丢失所有声学特征。因此，我们需要一种**音频编解码器**（Audio Codec），在保留音色、情感等特征的同时，将音频压缩到每秒几千 bit。在 Mistral 的系统中，我们将每 80 毫秒的音频帧转化为 37 个 Token，从而将复杂的音频生成问题简化为每秒处理约 500 个 Token 的预测任务。

<details>
<summary>Original English Source</summary>
Physically it's the pressure of the microphone that we measure several thousand of times per second. So it seems that most labs have converged to some common patterns and obviously the the first one is inspired by large language model. We're trying to uh transform the problem as a language modeling problem because humanity is extremely good at modeling sequences of token. For audio it's much harder because one token of a vocabulary of a thousand, it's 10 bits of information and the audio requires much much more uh like a much larger bit rates. The codec that are used uh typically reduce the audio to about a few thousand bits uh per second. In our case for instance uh we treat the problem with we cut the audio as uh with pieces of 80 milliseconds and we transform each frame into several tokens like 37 in our case.
</details>

### 扩散模型与流匹配：突破传统的生成架构

虽然大多数系统采用逐帧预测的自回归骨干网络，但 Mistral 在具体实现上进行了创新。对于拥有 40 亿参数的核心 Transformer 模型，如果完全按照传统的自回归方式逐个处理 500 个 Token，计算开销将非常巨大。主流做法是骨干网络每帧执行一步，再配合一个小型的深度 Transformer。

Mistral 的独特之处在于，我们利用了**扩散模型**（Diffusion Model）——确切地说是**流匹配**（Flow Matching）技术，在每一个时间步同时生成一帧中的全部 37 个 Token。这种方式既保持了生成的高质量，又显著提升了效率。在单 GPU 环境下，从输入文本到产出首个可播放音频包的延迟仅为 17 毫秒。目前关于如何处理流式文本输入（作为模型调节条件）仍有多种流派，包括交织音频/文本流（Interleaved）或双流架构。Mistral 目前的模型属于先提供完整上下文再生成音频的第一类，但实现更低延迟的流式输入支持将是接下来的研究重点。

<details>
<summary>Original English Source</summary>
What most people do then uh is uh having one step of the backbone per frame and a smaller model here uh typically a dev transformer that um recomputes all the the tokens of one frame. In our case, each frame which is represented by 37 tokens in our case, we do generate these 37 tokens at once using a diffusion model. It's a pretty cool uh use case of flow matching uh models which is similar to diffusion model. Regarding the latency, so it it's pretty fast. Uh if you remove the network and with a single GPU, you have 17 milliseconds between the moment where you input your text and the moment where you have the first audio you can play.
</details>