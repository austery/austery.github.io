---
author: AI Engineer
date: '2026-05-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UsB70Tf5zcE
speaker: AI Engineer
tags:
  - llm-training
  - transformer-architecture
  - pytorch-implementation
  - tokenizer-design
  - inference-optimization
title: 从零开始本地训练大模型：ElevenLabs 专家的深度实战指南
summary: 本讲稿由 ElevenLabs 语音转文本团队负责人 Angelos 主讲，系统性地演示了如何不依赖预训练权重，纯手工利用 PyTorch 训练一个类 GPT-2 架构的小型语言模型。内容深度解析了分词器选择、Transformer 核心组件（注意力机制、MLP、残差连接）、训练超参数优化以及推理采样策略，并探讨了多模态编码与推理增强模型的底层逻辑。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Angelos Perivolaropoulos
  - Andrej Karpathy
companies_orgs:
  - ElevenLabs
  - OpenAI
  - Google
products_models:
  - GPT-2
  - Scribe V2
  - NanoGPT
  - Gemini 1.5
media_books: []
status: evergreen
---
### 开启 LLM 的底层探秘：从零构建与分词策略

本次工作坊的核心目标是引领参与者跨越“黑盒”调用的局限，从零开始（From Scratch）构建一个**大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）。**Angelos**（ElevenLabs 语音转文本团队负责人）强调，我们不使用任何预训练权重，也不依赖 `transformers` 等高级库，而是纯粹基于 **PyTorch** 及其基础库进行开发。这种方法能让开发者像顶级实验室的训练工程师一样，深度掌握模型设计的权衡点。

在训练模型之前，首要任务是理解**分词器**（Tokenizer: 将文本转换为数字序列的组件）。对于算力受限的本地训练场景，**字符级分词**（Character-level Tokenization）是最佳选择，因为它仅需 65 个嵌入向量，极大地降低了模型收敛所需的计算量。相比之下，虽然工业界主流使用 **字节对编码**（Byte Pair Encoding / BPE: 一种根据频率合并字符的子词分词技术），但其巨大的词表（如 GPT-2 的 50,000 个词素）会导致参数量剧增。Angelos 指出，在数据量有限的情况下，如果盲目追求复杂的 BPE 分词器，模型将难以训练出有效的**二元语法**（Bi-gram: 两个相邻词素的组合概率）关系，最终导致无法收敛。

<details>
<summary>Original English Source</summary>

Today we're going to be training an LLM from scratch. So, no pre-trained weights, no nothing that you can just grab online from like a transformers library. We're going to work purely on torch and some like very basic libraries. This will be like a good indication of how like actual like research engineers like in big labs like design their models.

As I mentioned like this is generally the first thing you think about when you create a new any new transformer model is what tokenizer you're using. I come from the voice world. So this is where that's the one of the most important things. LLMs don't see text they they work with embeddings or like vectors. What we're going to be using here is a character level tokenization just because it has the lowest number of possible tokens. In our case it's going to be only 65 embeddings essentially because it's 65 different characters that will appear in our training data.

The concept of biogram is very is a very important concept when when you're training transformers because you want your model to see as many possible biograms as possible. In our case, 4,000 biograms is like very doable. If we did try to train using a full tokenizer, this will never converge. The problem with character level tokenizers is that they don't really scale very well because the models need to understand correlation between different tokens. But that's our trade-off that we're willing to take because of course we're running a small model.

</details>

### Transformer 架构解构：四大核心组件的协同

Transformer 已经成为一种“商品化”的技术，尽管不同实验室有各种优化手段，但其底层架构已非常成熟。Angelos 将其拆解为四个关键模块。首先是**多头自注意力机制**（Multi-head Self-attention: 允许模型在处理当前词时，关注上下文中其他相关词的机制）。它是 Transformer 区别于传统神经网络的核心，负责捕捉序列中不同位置的依赖关系。其次是 **MLP**（Multi-layer Perceptron / 多层感知机，亦称 Feed-forward Network），它负责对注意力机制提取的特征进行非线性映射和重组，为生成 **Logits**（未归一化的概率得分）做准备。

为了确保深层网络的训练稳定性，架构中引入了**残差连接**（Residual Connections: 将层输入直接加到层输出上的设计）。这意味着每一层并不需要从头开始学习特征，而是在前一层输出的基础上学习“残差”或增量变化，这极大缓解了梯度消失问题。最后是**层归一化**（Layer Normalization），它的作用是防止 **激活值**（Activations）在层间传递时发生数值爆炸。如果没有归一化，经过几十层的乘法累加，中间结果可能会从 0.5 飙升至数千万，导致模型无法训练。即使开发者不完全理解这些数学细节，通过组合这些模块也能构建出性能强大的模型。

<details>
<summary>Original English Source</summary>

Transformers are using like these four different building blocks. One is multi head self attention. Attention is what the difference between that makes the transformers different than other neural networks is that they can actually attend to previous tokens and understand the relationship between tokens. Next one is the MLP or like the feed forward network which essentially takes this different relationships between those tokens and it combines them together to to be able to generate the logits.

Then you have the residual connections which are basically there for the model to not have to reinvent itself after every layer. Residual basically means that every layer that passes through, it just takes the previous input and adds a small difference. This way the model doesn't make a huge change on the inputs themselves and the model can be more stable during training. And lastly, the layer normalization is allowing you to scale down those activations in ways that allows those activation to not be exploding into very big values. So if one layer like multiplies your activation by 10x, the layer norm is going to push it back back to like normal values.

</details>

### 训练循环与超参数：让模型从混沌走向秩序

在实际训练中，我们不仅要初始化 GPT 模型，还要配置精细的**训练循环**（Training Loop）。Angelos 建议使用 **AdamW 优化器**，并配合**学习率预热**（Learning Rate Warm-up）和**余弦衰减**（Cosine Decay）策略。在训练初始阶段，模型权重随机分布，**交叉熵损失**（Cross Entropy Loss: 衡量模型预测分布与真实分布差异的指标）通常处于高位（如 4.17，即 65 个字符的自然对数）。随着训练进行，模型会依次经历三个阶段：先是学会字符频率，然后掌握常见的双字母组合（如 'th'），最后在损失降至 1.5 左右时开始生成连贯的单词。

监控**验证损失**（Validation Loss: 在模型从未见过的数据集上计算的损失）对于防止**过拟合**（Overfitting: 模型死记硬背训练数据而非学习通用规律）至关重要。Angelos 展示了一个有趣的现象：当训练损失持续下降但验证损失开始回升时，说明模型已进入过拟合状态，此时应停止训练或调整策略。在本地实验中，一个 180 万参数的小型模型在几分钟内就能学会莎士比亚风格的遣词造句。此外，为了让生成的结果不那么“枯燥”，推理时通常引入 **温度系数**（Temperature: 控制生成随机性的超参数）和 **Top-K 采样**，避免模型总是选择概率最高的词。

<details>
<summary>Original English Source</summary>

The objective of this training is going to be to create a Shakespeareian like LLM. As we mentioned before these models like are learning as next prediction. The way this cross entropy works is that you take your sequence and you just offset it by one as what the model needs to learn.

The way the models work is that you first start generally with as high of a learning rate as as you can afford without making the model become unstable. Usually you have this concept of a warm-up where you start with a very small learning rate. Then you start reducing the learning rate. That's what we call weight decay. You want the learning rate to be less when the model is like close to being perfect.

TQDM helps with like tracking like the losses. Another important part is evaluations to make sure that your model actually works well. It's very easy for models to like overfit especially like this small models. That's why we have this val loss which is a part of the data the model has never seen. When the loss starts going below 1.0 for this specific data set, that's where we're going to start seeing overfitting.

Greedy decoding doesn't work very well for LM. You would want to use temperature. Generally like a 0.7 temperature is like the best middle ground to make inference work well. And then you have top k sampling which prevents the model from predicting very unlikely tokens even though the temperature might get unlucky.

</details>

### 深度问答：多模态编码与推理模型的进阶思考

在问答环节中，Angelos 深入讨论了当前 AI 的前沿话题。关于 **推理增强模型**（Reasoning Models），他解释道，这类模型（如 OpenAI 的 o1）并非在基础架构上发生了质变，而是高度依赖于**思维链数据**（Chain of Thought Data）。通过在后训练阶段加入高质量的逻辑推导过程，模型学会了在生成最终答案前先进行内部“思考”，并回过头来关注这些推理 **Token**，从而提高复杂问题的准确率。这种数据的获取极其昂贵，往往需要各领域的博士生手工编写解题思路。

针对**多模态模型**（Multimodal Models: 能够处理文本、图像、语音等多种模态的模型）的原理，Angelos 揭示了一个简洁的统一框架：模型并不在乎输入的向量是来自文本、音频还是视频。通过使用特定的 **编码器**（Encoder: 负责将特定模态转换为向量特征的模块），我们可以将视频帧或音频谱图转换为与文本嵌入维度一致的向量。随后，这些向量被作为“前缀”输入给 Transformer。在 ElevenLabs 的实践中，音频分词通常基于 **梅尔频谱图**（Mel Spectrograms）进行训练。这种将不同感官信号映射到同一向量空间的技术，正是现代大模型能够实现“跨模态理解”的底层奥秘。

<details>
<summary>Original English Source</summary>

Question: Are reasoning models quite a bit different in training?
Answer: The building blocks are very similar. This is very data driven. So you need very high quality data. The complication of reasoning models is finding this good chain of thought data. Reasoning is essentially just adding to the context of the model this logic that then the model can when it generates the response it can go back and attend to those reasoning tokens and get a better response out.

Question: How different is this versus like doing this with audio?
Answer: It's surprisingly very similar. These vectors they don't have to correspond to specific token you can take these vectors from other places too. Instead of having a tokenizer for like video, what they do is they have another transformer that they call a video encoder. It will take those frames and then put them through this encoder transformer. You take those vectors out of this encoder and you're going to input them in the embedding layer of the transformer model. The model just cares about these embeddings. It don't care if it's text or if it's audio or if it's video.

</details>