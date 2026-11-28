---
author: AI Engineer
date: '2026-04-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_A367W_qvc8
speaker: AI Engineer
tags:
  - gemma-4
  - mixture-of-experts
  - on-device-ai
  - multimodal-llm
  - attention-mechanism
title: Gemma 4 技术全解：Google DeepMind 如何重塑高效模型与原生多模态架构
summary: Google DeepMind 研究员 Cassidy Hardin 深度解析了最新发布的 Gemma 4 系列模型。本文涵盖了 2B/4B 端侧模型、26B MoE 以及 31B 稠密模型的架构创新，重点探讨了局部与全局注意力交替机制、层级嵌入（PLE）存储优化，以及支持可变分辨率的原生多模态处理逻辑。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google DeepMind
products_models:
  - Gemma 4
  - Gemma 3
media_books: []
status: evergreen
---
### Gemma 4 模型矩阵：开源生态的性能新基准

Google DeepMind 正式发布了 **Gemma 4** 系列，这是开源模型家族的最新成员。Gemma 4 在模型规模与性能的平衡上实现了质的飞跃，为小型开源模型的能力设定了新的先例。该系列包含四种规格：两款专为端侧应用优化的 **小型高效模型**（Effective Models），能够在手机、平板和笔记本电脑上本地流畅运行；以及两款大型模型。其中，**26B 混合专家模型**（Mixture of Experts: 一种仅激活部分参数进行推理的架构）是 Gemma 家族的首个 MoE 成员，在仅需 3.9B 激活参数的情况下实现了卓越性能；而旗舰级的 **31B 稠密模型**（Dense Model）则在各项基准测试中表现惊人，甚至在 LMSYS Arena 排行榜中位列开源模型前六，超越了其体量 20 倍以上的模型。

为了进一步赋能开发者，Gemma 4 转向了 **Apache 2.0** 开源协议。这一决策旨在降低集成门槛，使开发者能够轻松地将 Gemma 引入从初始测试到大规模部署的完整开发生命周期。特别是 31B 模型，作为一款先进的 **多模态模型**（Multimodal Model: 支持多种输入形式的 AI 系统），它专门为 **高级推理**（Advanced Reasoning）设计，原生支持 256k 上下文长度、思维链推理（Thinking）、函数调用（Function Calling）以及结构化 JSON 输出，是构建自主工作流的理想选择。

<details>
<summary>Original English Source</summary>

Hi everyone, my name is Cassidy and I'm a researcher at Google DeepMind. Today I'm really excited to share with you some of the technical improvements and architecture that we have with Gemma 4. Last week we launched Gemma 4 which is the latest addition to our family of open source models. Gemma 4 brought incredible improvements at a scale that has not been seen before. We have a family of very small models with incredible performance setting a new precedent for what's possible with small open source models.

Gemma 4 comes in four sizes. We have two smaller effective models which are geared towards ondevice applications. These models have been adapted and improved in order to provide incredible performance at a small scale which are able to run locally on phones, iPads and laptops. We have two larger models starting with a 26B mixture of experts model which is the first ever Gemma. This model has been adapted to have incredible performance while only requiring 3.9 billion active parameters. And our largest model is our 31B dense. This has insane performance, a huge improvement upon what existed within Gemma 3 at a new precedent that hasn't been seen before.

Taking a look at our larger models, our 31B and our 26B, these models have both ranked in the top six of all open-source models on the LM, the LM arena. One of the most exciting improvements and things that we've launched alongside Demo 4 is the move to an Apache 2.0 license. This was deliberately done in order to make our models more accessible for the everyday developer. You should easily be able to integrate Gemma into your life cycle of development through initial testing all the way to deployment and building within the Gemma universe.

Now, let's take a little look at what each of these models are and some of the use cases that we've adapted this for. Starting with our 31D dense model. This is a state-of-the-art multimodal model which has been purposely built for advanced reasoning. This model ranked number three on the global arena for the AI leaderboard. This is outperforming models over 20 times its size. This is a huge improvement. The 31B has a 256k context length which has been purpose-built for autonomous workflows with native support for thinking, function calling, and structured JSON outputs.

</details>

### 架构创新：局部注意力与混合专家系统的协同

在底层架构上，Gemma 4 对 **注意力机制**（Attention Mechanism）进行了显著改良。模型引入了 **交替层架构**：在 31B 及端侧模型中，局部层与全局层的比例为 5:1（2B 模型为 4:1）。**局部层** 采用滑动窗口机制，仅关注当前位置之前的特定数量标记（大型模型为 1024 tokens，小型模型为 512 tokens），极大地提升了推理效率；而 **全局层** 则确保模型能够访问完整的上下文信息。此外，为了平衡内存消耗与性能，全局层采用了 **分组成组查询注意力**（Grouped Query Attention: 多个查询共享同一组 Key 和 Value 头的技术），将 8 个查询头对应 1 个 KV 头，并通将 KV 头长度从 256 增加到 512 来弥补性能损失。

26B MoE 模型的引入则是另一项突破。它采用了包含 128 个专家的架构，每次前向传播仅激活 8 个专家。与传统的 MoE 不同，它设计了一个 **共享路由专家**（Shared Router Expert），其大小是普通专家的三倍，并在每次前向传播中保持激活。这种结构不仅保证了模型的小巧高效（每次推理仅需 3.8B 参数），还维持了与 31B 稠密模型相当的卓越性能，完美契合了对计算效率有严格要求的应用场景。

<details>
<summary>Original English Source</summary>

We also have a slightly smaller 26B. This 26B is the first addition of a mixture of experts model into the Gemma family, only requiring 3.8 billion parameters during any forward pass. This model is small and efficient, utilizing a total of 128 experts while only requiring eight experts during any inference. This is efficient for running while still maintaining some of the incredible performance that we saw with our 31B.

Now, let's take a look at what's actually new in Gemma 4 and what have we done and how have we actually been able to achieve this incredible performance. Starting on the architecture side, we have our standard dense model. This is our 31B as well as our smaller effective 2B and 4B models. We have our standard decoder block. What we've done with Gemma 4 is we've made several improvements within attention. We've introduced a 5:1 ratio of interle to global layers with our smaller effective 2B having a 4:1 ratio. This means that within our local layers, we have a sliding window of how many tokens we're attending to. And lastly, with our global layers, we've now ensured that the last layer is always a global layer, meaning that our last layer is attending to all preceding tokens.

In practice, what this looks like is our global layers are attending to every token that is preceded within this, whereas our local models are only attending to a specific number of preceding tokens. In our smaller models, we have a sliding window of 512 tokens, while in our larger models, we have a sliding window of 1,024 tokens. This sliding window has provided significant improvements in the efficiency and optimizations of our local layers while still maintaining passing through information to the preceding layers.

However, our global layers remain to be quite expensive. Despite this interleing of local and global layers, all of our global layers are still required to attend to all preceding tokens, which makes it quite memory intensive and expensive to run. And this is where we've looked into introducing grouped query attention. Within our local layers, we group together two queries to share the same key and value heads. However, in our global layers, we're grouping together eight queries sharing the same key and value heads. Since reducing the number of key and value heads can have a big impact on performance, we've doubled the length of the key value heads within our global layers to have a length of 512 as opposed to 256 as used within the local layers.

These attention changes were present across all of our models. But we also introduced a new architecture with Gemma 4 and this is our MoE. Our MoE has one shared router expert with a total of 128 total experts with eight activated experts on each forward pass. All of these experts are small fed forward neural networks. In practice, what this looks like is having our constant shared expert which is activated on every pass of the model. This shared expert is three times the size of our regular experts. We then have 128 experts each of which eight of which are selected by the router during any pass of the model.

</details>

### 端侧性能巅峰：层级嵌入（PLE）与存储革新

针对 2B 和 4B 这两款被称为“高效型”（Effective）的模型，Google DeepMind 引入了 **层级嵌入**（Per Layer Embeddings: 为模型的每一层分配独立嵌入表的技术）这一革命性设计。虽然 2B 模型的推理参数约为 2.3B，但其 **表征深度**（Representational Depth）达到了 5.1B，这使其在处理复杂任务时具备了超越体量的表达能力。PLE 技术的关键创新在于 **存储介质的迁移**：模型将这些庞大的层级嵌入表存储在手机或电脑的 **闪存**（Flash Memory）中，而非极其有限的 **显存**（VRAM）中。

在运行过程中，模型会在每个 **解码块**（Decoder Block）的末尾从闪存中读取 256 维的层级嵌入，并将其投影至模型全尺寸的嵌入空间。由于闪存的容量远大于显存，这种方法在不显著增加硬件成本的前提下，极大地增强了模型的表征能力，使得 E2B 和 E4B 模型在性能上大幅领先于前代 Gemma 小模型。这种优化确保了高性能 AI 能够脱离昂贵的云端 API，在个人终端设备上实现真正的本地化运行。

<details>
<summary>Original English Source</summary>

And lastly on an architecture side we get into our dense effective models. So what does it mean when we're saying our model is effectively 2B, effectively 4B? This is where we're looking at the difference in the number of parameters which are required to operate the model as opposed to the total number of representational parameters present. Our 2B is effectively 2.3 billion parameters while having a representational depth of 5.1 billion parameters. These models have been specifically designated and optimized in order to have the best ondevice performance. These are designed to run on phones, run on laptops without requiring expensive API calls to models served somewhere else in the world.

These advancements were made possible through PLE. This is our per layer embeddings where within each of our layers, we now have a dedicated embedding table. Before digging into exactly how our per layer layer embedding table looks, let's take a look at how the entire token embedding layer works. This hasn't been replaced within our effective models. We still have your standard embedding table where you're looking at the mapping of an ID for a token in toward towards its embedding vector. In our E2B, we have an embedding vector size of 1536. And in our larger E4B, we have an embedding vector size of 2560.

Now we also have a per layer embedding table. This is where similarly we have our entire vocabulary size and have an embedding representation for each of these tokens. But now we also have one of these for each of the layers. The big advancement that comes here is the fact that we store our per layer embedding table in flash memory as opposed to VRAM. VRAM is one of the largest constraints on ondevice. where you quickly run out of memory in phones and laptops. So by requiring that we no longer need to store this additional embedding table in VRAM and we can can store it in flash memory, we're able to get incredible improvements on the inference side without having an expensive cost of this additional storage and memory.

The big difference in our PLE embedding table as opposed to the standard embedding table is our embedding dimension now is only 256. So this is significantly reduced from the size of the full model. For each token, we now have an embedding for this token at each separate layer within the model. And as you progress through the layers of the models (35 for the 2B and 42 for our larger model), you'll see the progression and improvements in the embedding representation for each of these tokens at the next subsequential layer. Ultimately, these improvements allow for our E2B and our E4B to be significantly outperforming prior generations of Gemma small models.

</details>

### 原生多模态：跨分辨率视觉与音频感知

Gemma 4 在多模态领域确立了新的边界。与 Gemma 3 采用的“平移扫描”（Pan and Scan: 将大图切分成多个正方形小块的折中方案）不同，Gemma 4 引入了 **可变长宽比**（Variable Aspect Ratios）和 **可变分辨率**（Variable Resolutions）。开发者可以根据任务需求自由选择分辨率和 **软标记预算**（Soft Token Budget）。例如，在执行 **光学字符识别**（OCR: 从图像中识别文本）或空间对象识别等高精度任务时，可以分配更高的 token 预算以确保清晰度；而在纯文本任务中，则可以降低预算以节省资源。

在处理逻辑上，图像被切分为 16x16 的 **图像块**（Patches），经过线性投影形成嵌入。为了让模型理解图像的物理结构，系统引入了 **空间位置编码**（Spatial Positional Encoding），确保模型能准确区分不同位置的图像块。此外，端侧模型（E2B/E4B）还集成了 **原生音频支持**，通过 35M 参数的 **Conformer** 编码器和梅尔频谱（Mel Spectrogram）处理逻辑，将原始音频转化为软标记。这一改进使得端侧模型在实时翻译和语音识别方面表现优异，真正实现了视觉、音频与文本的三位一体原生交互。

<details>
<summary>Original English Source</summary>

In addition to everything that we've done on an architecture side, we've also really set a new frontier for what's possible with multimodality. In Gemma 3, we introduced vision for the first time. In the Gemma 3N model, we launched open-sourced audio vision and text model for the first time. This really paved the way for Gemma 4 being natively multimodal models. Starting on the vision side, our 31B and 26B model both use a 550 million parameter vision encoder. Our effective 2B and effective 4B have a smaller, compact, more designed encoder of 150 million parameters.

We've made big strides from Gemma 3 by the introduction of variable aspect ratios and variable resolutions. What this means in practice is you now have a choice to select the resolution and the soft token budget that you want to allocate for images. This is available in five different resolutions. What's important to understand here is this is a huge improvement from Gemma 3. In Gemma 3, we had to introduce pan and scan. And this is where you would give an image and we split it into a sequence of squares and padded whatever else was necessary. Now, we're now able to process images with varying number of patches depending upon the actual image which was provided by the user.

For the audio side, audio has been added into the E2B and the E4B with the goal of being able to support translation and speech recognition. This is made possible through the combination of an audio tokenizer and a conformer. This is a 35 million parameter conformer which processes as an audio encoder processing embeddings rather than tokens. On the audio tokenizer side, we start with raw audio. This raw audio is run through a MEL spectrogram which is able to process features out of the raw audio files. This MEL spectrogram is then split into NMEL chunks which are downsampled. This ultimately outputs soft tokens. These audio embeddings are what's passed forward into the conformer.

</details>