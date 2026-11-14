---
layout: post.njk
source: https://blog.qiaomu.ai/what-are-diffusion-models
speaker: 向阳乔木
title: Diffusion 模型到底是什么？ · 乔木博客
date: '2026-05-10'
summary: 本文阐述了 Diffusion 模型（扩散模型）作为一种训练框架的本质，而非模型架构。它借鉴物理扩散现象，并具有在数据稀缺场景下的优势。文章分析了 Diffusion 模型早期发展缓慢的原因，对比了其在图像与文本生成领域的成熟度差异，并与自回归模型（如 GPT）进行比较。最后，文章探讨了算力、数据、工程积累等因素的作用，并引发了对 AI 前沿驱动因素的思考。
area: tech-engineering
category: ai-ml
tags:
  - diffusion-models
  - autoregressive-models
  - generative-ai
  - model-comparison
people:
  - Yann LeCun
companies_orgs:
  - OpenAI
  - Nvidia
products_models:
  - GPT-3
  - ChatGPT
  - Claude
  - Stable Diffusion
  - Transformer
  - GAN
  - DDPM
  - Flow Matching
media_books: []
draft: true
status: evergreen
---

乔木博客

全部

AI工具

AI教程

AI生成

AI资讯

健脑房

播客解读

论文学习

# Diffusion 模型到底是什么？

播客解读

·

2026年5月10日

·

849 次阅读

·

约 5 分钟

GPT 系列模型统治 AI 圈这件事，大家都看在眼里。

但图灵奖得主 Yann LeCun 却公开说，自回归模型是一种劣等方法。

这话听起来很刺耳，却也让人好奇：他在押注什么？

答案很可能是 Diffusion（扩散模型）。

## Diffusion 不是模型架构，是一套框架

很多人以为 Diffusion 和 Transformer 是竞争关系，一个做图像，一个做文本，各占山头。

这个理解是错的。

Transformer 是模型架构，规定了权重怎么连接。

Diffusion 是训练框架，规定了数据怎么生成、模型怎么训练、推理怎么跑。

两者根本不在同一个维度上，所以 Diffusion 模型完全可以用 Transformer 架构来实现。

更准确的说法是：Diffusion 在理论上是自回归模型能力的超集，因为它可以按任意顺序处理数据，包括从左到右，也包括其他顺序。

## 它的灵感来自物理世界

Diffusion 这个名字，直接借用了物理学里的扩散现象。

墨水滴进水里，从高浓度慢慢扩散到低浓度，最终均匀分布。

Diffusion 模型做的事情类似：把一张干净的图片，一步一步加入随机噪声，直到它变成完全的噪声。

然后，模型学习反过来做这件事，从噪声里一步一步还原出图像。

在数学实现上，历史上有两个流派。

一个把时间看成离散的，用马尔可夫链建模；另一个来自斯坦福，把时间看成连续的，用微分方程描述。

后者和物理扩散的映射关系更紧密，也因此能直接继承物理学几百年积累的数学工具。

## 为什么它在数据稀缺时更有优势

Diffusion 有一个很聪明的地方：它能从一张图片里变出大量训练数据。

对一张图加 1000 步噪声，就得到了 1000 个不同程度的样本。

模型的训练目标，就是在每一步猜出加了多少噪声。

这意味着，一张原始图片，可以撑起 1000 个训练样本。

这在数据稀缺的场景下，是巨大的优势。

实验数据也支持这一点：在数据量只有 2500 万到 1 亿 token 的情况下，Diffusion 模型的损失下降比自回归模型更低，也就是学得更好。

但有个前提：这个优势只在数据稀缺、算力充足的条件下成立。

现在主流 LLM 的训练数据动辄超过 10 万亿 token，自回归模型根本不需要在这个维度上和 Diffusion 竞争。

## 它为什么没有更早流行

时间线大概是这样的：

2015 年，第一篇 Diffusion 论文发表，几乎和 GAN（生成对抗网络）同期。

但 Diffusion 起步很慢，原因可能很简单，数学太重了，入门门槛高，做的人少。

2020 年，DDPM 论文出现，是真正的转折点。

它把训练目标从"猜均值和协方差"简化成"猜噪声"，整个框架一下子清晰了很多。

同年，OpenAI 发布了 GPT-3，势头已经很猛。

2022 年，Stable Diffusion 出现，第一次把模型规模放大到能看出效果的程度，图像生成领域从此热闹起来。

之后，Flow Matching 技术出现，把推理步数从几百步压缩到几步，速度大幅提升。

## 文本扩散为什么还没追上 GPT

Diffusion 在图像领域已经很成熟，但在文本领域，Mercury 这类模型和 ChatGPT、Claude 相比还有差距。

原因不只是算法，更多是工程积累的问题。

现有的推理引擎，比如 vLLM、SGLang，底层 kernel 都是为自回归推理优化的。

要让 Diffusion 模型跑得同样快，需要把这些 kernel 重写一遍，工程量巨大。

训练侧也一样，投入 Diffusion 的时间和资源，历史上就是比自回归少得多。

当然，Diffusion 文本模型有一个很吸引人的特性：生成速度极快，有些能达到每秒超过 1000 个 token。

但 Nvidia 的 Blackwell 系列芯片在自回归推理上的吞吐量也在快速提升，这个速度优势正在被压缩。

## 真正的问题还没有答案

算力越来越多，数据越来越多，推理速度越来越快。

在这个背景下，决定 AI 前沿的到底是什么？ 是速度？是知识深度？是泛化能力？还是可扩展性？

Diffusion 和自回归的路线之争，本质上是在回答这个问题的不同方式。

目前没有定论，但这个问题值得持续关注。

© 2026

·

向阳乔木