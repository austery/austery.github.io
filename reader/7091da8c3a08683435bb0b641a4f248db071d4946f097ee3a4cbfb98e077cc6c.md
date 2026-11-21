---
author: AI Engineer
date: '2026-05-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Lm8BLHkxiAo
speaker: AI Engineer
tags:
  - edge-ai
  - on-device-inference
  - agentic-workflow
  - model-quantization
  - cross-platform-deployment
title: Gemma 4 与 Light RT：重构边缘侧 AI 智能体部署生态
summary: 本文深入探讨了 Google DeepMind 最新推出的 Gemma 4 系列边缘模型及其配套的 Light RT 部署框架。文章重点介绍了从传统聊天机器人向具备推理、函数调用和结构化输出能力的自主智能体（Autonomous Agents）的演进，并展示了在隐私保护、低延迟和低成本背景下的多样化端侧应用场景，以及 NPU 加速带来的性能飞跃。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - Google DeepMind
products_models:
  - Gemma 4
  - Gemma 3
  - Light RT
  - TensorFlow Lite
  - Gemma 4 E2B
  - Gemma 4 E4B
media_books: []
status: evergreen
---
### 边缘 AI 的范式转移：从聊天机器人到自主智能体

Google DeepMind 近期发布的 **Gemma 4** 系列模型标志着端侧 AI 的重大进化。不同于以往仅局限于文本对话的轻量级模型，Gemma 4 的核心演进在于从简单的**聊天机器人**（Chatbot）能力转向支持**自主智能体**（Autonomous Agents）。这意味着模型现在原生支持推理能力、**函数调用**（Function Calling: 允许模型与本地 API 交互）以及**结构化 JSON 输出**（Structured JSON Output: 无需复杂的提示工程即可生成标准格式数据）。在模型规格上，2B（约占用 1-2GB RAM）和 4B 版本的发布，使得从智能手机到高性能笔记本及 IoT 设备都能实现高效的本地部署。

运行在边缘侧（Edge）具备显著的战略优势：**实时性**（Latency）对于视频滤镜或语音交互至关重要；**隐私保护**（Privacy）确保了敏感的摘要和文档处理无需上传云端；此外，端侧部署能有效对冲云端推理昂贵的**令牌成本**（Tokens Cost）。这种混合架构让开发者能够在云端强大算力与本地高效响应之间找到最佳平衡。

<details><summary>Original English Source</summary>
Google DeepMind recently launched Gemma 4 and uh this talk is going to be focusing a little bit more on like the 2B and the 4B edge models that are are focused on uh deploying on device. Uh Google certainly has a big suite of models and even the Gemma 3 family which are also in the smaller size like all the way down to 270 million parameters. So if you're looking for extremely small models that you're able to fine-tune, uh we certainly have a hugging face page which I'll go over which has more of these models. Um, so yeah, so the big evolution with Jamma 4 is going to be really moving from like chatbot type capabilities to more autonomous agents that also support reasoning capabilities and more sophisticated features and uh a lot of it is also uh it's going to be great how you can deploy these on different devices.

So running on edge has many benefits. I think my colleague went over some of these uh yesterday and I'll just you know run through this uh really quick also. So certainly like latency is important for those who are keen. Um any of these like real-time camera use cases like filters where you're looking to replace backgrounds or like video calls like real-time latency is king over there. So that's you know on device can help with that. Privacy is also critical for any use cases where you know you have sensitive details, you're doing some kind of summarizing uh documentation which is sensitive offline use cases where you have poor connectivity and costs like you know I've seen so many presentations uh this uh uh AI engineer event where uh people are complaining about the number of tokens that are getting used and this and that but I think uh ondevice always offers this hybrid approach where if you're looking for like how do i really offset you know uh running things on the edge versus on cloud and where can i get the best balance? I think there's a there is something here.
</details>

### 端侧应用生态：Gallery App 与多模态推理实践

为了展示 Gemma 4 的强大性能，Google 推出了开源的 **Gallery App**，作为一个实验场供开发者探索智能体技能。该应用不仅支持基础的**端侧摘要**（Summarization）和图像问答，还引入了**思维链**（Chain of Thought）的显示模式，让用户直观地看到模型的思考过程。在具体的应用场景中，Gemma 4 展示了其在**知识增强**（Augmenting Knowledge: 如本地调用维基百科 API）和复杂工作流管理方面的潜力。

通过具体的演示案例，我们可以看到模型在图像理解与音频生成方面的深度融合。例如，用户上传一张早餐照片，模型能够识别照片的“氛围”（Vibe）并完全在本地生成匹配的音乐。此外，针对健康管理的**情绪追踪智能体**（Mood Tracker Agent）能够分析过去七天的情绪趋势并给出建议。这些技能的实现得益于模型在硬件原生的优化，使其能够跨 CPU、GPU 甚至是即将全面支持的 **NPU**（Neural Processing Unit: 专用 AI 加速芯片）无缝运行。

<details><summary>Original English Source</summary>
In the next couple of slides um at present you know what's new is the de the the gallery app allows you to demonstrate the agent skill capabilities um and also it has the audiocribe capabilities or ask image and also other features that were uh related to uh chat experiences. Um all of this is happening on device. The purpose of this app that is created by Google is to help you get a playground to get a feel for what these models are capable of. Uh each of these capabilities has sample code as well that anyone can go and grab and then you are able to also fork this app to build your own experiences.

So here's one use case where you're augmenting knowledge and you know for example you can build a skill to query Wikipedia allowing the agent to query uh and respond to any encyclopedia question. So this is a this is a skill that's already available in our app that's uh that's there. So you can kind of see that it's able to create this all on device. It's taking your input, it's feeding it, it's able to understand. So the reasoning and the thinking capability are new in the new model and that the the ondevice capabilities have gotten a lot more powerful. Another similar ex example is going to be on expanding like the core capabilities. So for instance, you can also pair photos and it's going to read the photo and have image understanding and generate music also all on device.
</details>

### Light RT：跨平台部署框架与硬件加速性能

在技术底层，Google 将其端侧 AI 框架更名为 **Light RT**（原 TensorFlow Lite 的演进版），旨在提供一个统一且跨平台的架构。Light RT 不仅支持原有的 **TensorFlow Lite** 格式，还通过 **Light RT Torch** 路径实现了对 **PyTorch** 和 **JAX** 模型的兼容。这一转变解决了开发者“自带模型”（Bring Your Own Model）的痛点，确保同一模型文件可以在 Android、iOS、Linux、Windows 以及 Raspberry Pi 等各类 IoT 设备上保持一致的行为。

性能优化是 Light RT 的核心竞争力。通过 **AI Edge Portal** 云端基准测试工具，开发者可以针对大规模设备群进行**混合精度训练**（Mixed Precision）或量化策略的验证。特别是在硬件加速方面，Light RT 已完成与高通（Qualcomm）和联发科（MediaTek）的深度集成，利用 NPU 加速可以实现 **3 到 10 倍** 的性能提升，这对于实时 **ASR/TTS**（语音识别/合成）以及 AR/VR 应用来说是革命性的。性能对比数据显示，在移动端，Light RT 的运行速度在某些场景下可达到 Llama 模型的 35 倍，为边缘侧复杂智能体的落地提供了坚实的工程基础。

<details><summary>Original English Source</summary>
Google has an offering with light RT for bring your own models essentially. So light RT essentially is Google's ondevice framework. It's built and built on the TensorFlow framework. TensorFlow light if you guys are familiar with that. Uh it's really meant to also be built on using the same TensorFlow light model format and that's what we are focusing on at this point. So the rebranding was to also demonstrate that it's not just TensorFlow light models that we accept but also PyTorch models and JAX models.

The AI edge portal is a benchmarking tool which could be of interest for those who are looking to deploy broadly on Android. So this is a cloud-based benchmarking service called AI edge portal. Um yeah sorry one more thing on this slide is uh the next part is acceleration. So CPU and GPU are pretty universal right now. Uh NPU acceleration is also another focus. So we have completed uh integration with Qualcomm MediaTek and we are also focusing on additional integrations with other uh partners. I think the NPU is going to give you at least like 3 to 10x improvement in performance and it's going to be a gamecher in terms of the amount of energy you're going to use uh and the amount of performance you're looking for to unlock those use cases. Our runtime is also very performant versus llama. At least on like mobile, we've seen up to like 35 times faster performance.
</details>