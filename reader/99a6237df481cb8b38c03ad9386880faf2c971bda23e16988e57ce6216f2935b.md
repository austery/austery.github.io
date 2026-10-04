---
author: AI Engineer
date: '2026-05-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=qdh_x-uRs9g
speaker: AI Engineer
tags:
  - model-inference
  - small-language-model
  - gpu-utilization
  - context-management
  - agentic-workflow
title: 小模型推理架构的缺失与重构：Superlinked 的开源实践
summary: Filip Makraduli 探讨了当前 AI 市场在小模型推理架构上的空白。他指出，尽管大模型备受关注，但在 AI 搜索、文档处理和 Agent 工作流中，小模型在上下文管理和预处理方面具有不可替代的价值。本文深入分析了 Superlinked 开源推理引擎 Sie 的设计理念，涵盖了 GPU 资源热切换、模型前向传播的标准化重构以及自动化集群扩展等核心技术栈。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Filip Makraduli
  - Andrej Karpathy
companies_orgs:
  - Superlinked
  - Chroma
  - Hugging Face
products_models:
  - Sie
  - Gemma
  - BERT
  - Qwen
  - ColBERT
media_books: []
status: evergreen
---
### 第一性原理下的推理盲区：从小模型到生产环境

在 AI 领域深耕多年后，作者意识到尽管在模型训练和微调（Fine-tuning）方面积累了丰富经验，但在**模型生产化运行**（Production inference）——即 GPU 调度、路由和自动化领域——仍存在明显的知识盲区。通过在 Substack 发表关于 Flash Attention 和计算限制的深度文章，作者发现业界普遍忽略了现实世界中如何让模型真正“跑得快”的关键：**推理优化**。

为了填补这一空白，作者加入 **Superlinked** 团队，共同构建并开源了 **Sie**（Superlinked Inference Engine）。这是一个专为 AI 搜索和文档处理设计的小模型推理引擎。目前的 AI 生态中，虽然针对大语言模型（LLM）的方案层出不穷，但在处理向量数据库（如 Chroma, Qdrant, Weaviate, LanceDB）所需的嵌入（Embedding）和重排序（Reranking）等小模型时，依然缺乏成熟的、端到端的开源基础设施。

<details>
<summary>Original English Source</summary>

Hello everyone. Um, welcome to this talk. I'll be speaking about small model inference and a gap that we've recognized in the market. And what we did about it and why we kind of made this approach. ... The story starts with me posting an article a few months ago on Substack that got a little bit of traction, explained flash attention, how models worked, memory-bound, compute-bound... But then some people pointed out that actually I had overlooked one key aspect around what makes these models fast in the real world. And that aspect that I overlooked was inference. ... This part around kind of how models run in production, scheduling GPUs, routing, and automation, I guess was a bit of a blind spot for me. ... I decided to join a team at Superlinked, comprised of very good infrastructure engineers, and actually work with them and build something around inference. And that something is this repo, the Superlinked inference engine that we have open-sourced, and this is kind of like the soft launch that I'm doing today. Basically it's inference for small models around AI search and document processing. And we've tested this out with some of our partners, Chroma, Qdrant, Weaviate, as well as LanceDB.

</details>

### 解决 Agent 的核心痛点：上下文腐败与预处理

为什么小模型的推理架构对 **Agent 工作流**（Agentic Workflow）至关重要？核心原因在于**上下文腐败**（Context Rot: 随着上下文长度增加，模型输出质量显著下降的现象）。研究表明，无论模型能力多强，海量信息的堆砌都会导致性能退化。

**上下文管理**（Context Management）是解决此问题的关键。通过使用小模型对数据进行预处理（如命名实体识别 NER、分类或过滤），开发者可以构建更精准的知识库或文件系统。这种方法不仅被 Andrej Karpathy 等社区大咖推崇（如构建基于图的知识库），也被 Chroma 等向量数据库厂商采用。此外，在**工具调用**（Tool Calling）场景中，将小模型作为专门的工具进行分类或检索（例如电商平台的类目分类），能有效降低 Agent 的总 Token 消耗，提高整体链路的稳定性和响应速度。

<details>
<summary>Original English Source</summary>

The three key points I want you to go away with: first, why this matters for AI search and document processing when you're building agents... Well, what you have encountered for sure is context rot. ... Quality degrades as context increases. So, being able to manage this context and do some context management is very important. Using small models that can preprocess your data so that then you can actually use your agents and build your workflows is a very powerful technique. You can also use the small models for tool calling to again do similar things and tackle this problem of context management. ... Andrej Karpathy is building knowledge bases graph-based. So, for example, you can use named entity recognition models to generate ontologies and then build knowledge graphs. ... We have a use case where this repo Superlinked inference engine, we've used it as a tool calling solution where it was around taxonomy classification for an e-commerce store.

</details>

### 推理架构的误区：GPU 堆砌与利用率瓶颈

传统的推理观往往是“堆硬件”：堆更多的 GPU，堆更多的算力。但在小模型场景下，这种做法极其低效。例如 **Stella**（嵌入模型）或 **Glyner**（NER 模型）通常仅占用几 GB 显存。如果为每个模型单独配置一个 GPU，会导致大量的**计算资源闲置**。

真正的推理挑战在于：
1. **热切换**（Hot-swap）能力：Sie 允许在单个 GPU 上动态切换多个模型，通过内置的 **LRU（Least Recently Used）驱逐策略**，显著提高了单块 GPU 的利用率，大幅降低成本。
2. **端到端工程化**：目前市场缺乏从模型推理到生产缩放（Scaling）的完整开源路径。Sie 整合了路由（Routing）、**自动缩放**（Auto-scaling）、队列机制以及基于 Prometheus 和 Grafana 的监控指标。开发者不需要自己手写 API 包装层或繁琐的调度代码，通过简单的配置文件和 Terraform 即可实现大规模生产部署。

<details>
<summary>Original English Source</summary>

The traditional perspective is, "Okay, I will just chuck in more GPUs, get more compute, all good, I've solved inference." However, with small models where actually each model takes up only a small space in memory... you're wasting a lot of idle space. So, it's very important to be able to hot-swap models. ... We've built the ability for you to swap all of these models in one GPU so that per GPU, you get much higher utilization. ... We have this least recently used eviction policy built in. And also what inference is not about is only the server. ... There is no open-source solution that leads you from creating the model inference to actually productionizing this at a scale of this size. So we've included routing, auto scaling, queuing mechanisms, and provisioning GPUs.

</details>

### 推理的阴阳哲学：模型支持与基座设施

作者将推理架构比作“阴阳”的结合：**阴（模型支持）**与**阳（基础设施）**。

在**模型支持**（Yin）层面，尽管 Hugging Face 上有数百万个模型，但它们的底层实现各异。例如 BERT 和 Qwen 在 **Flash Attention** 的实现、**位置编码**（Positional Embeddings，如绝对查找 vs. 旋转位置编码 RoPE）以及归一化方式上完全不同。没有一个通用的引擎能高效处理所有架构。Sie 通过**重构前向传播**（Re-implementing forward pass）来适配这些差异，支持包括 ColBERT（多向量输出模型）、交叉编码器（Cross-encoders）和重排序器在内的多种模型。同时，通过**变长 Flash Attention** 消除 Padding 带来的无效计算，进一步榨取性能。

在**基础设施**（Yang）层面，Sie 构建了三个核心原语：**编码（Encode）**、**评分（Score）**和**提取（Extract）**。底层的集群管理则采用 **KEDA 自动缩放**和 Prometheus 监控，支持在竞价实例（Spot Instances）和高性能 GPU 之间灵活分配负载。这种端到端的整合，让开发者能专注于业务逻辑，而无需在底层硬件调度上“掉链子”。

<details>
<summary>Original English Source</summary>

I call this the yin and yang of inference because I feel like this is a holistic approach. First, the yin is model support. ... Open source models are very relevant, and you need an infra to support them. ... All of these models have different run times. BERT and Qwen have different implementation of flash attention, different positional embeddings... There is no universal engine that can handle BERT, Qwen, and modern BERT as well because their architectures are different. What we've done is set up a way of re-implementing this forward pass in order to adapt attention, do padding where needed, so have variable length attention as well. ... The other part, the yang, is around infrastructure. ... The three primitives of our API: encode, score, and extract. ... We're doing KEDA auto scaling with Prometheus metrics in order to be able to switch models around, not keep GPUs idle. ... The models are basically just a config that you can switch around and then do Terraform apply, and that's it.

</details>