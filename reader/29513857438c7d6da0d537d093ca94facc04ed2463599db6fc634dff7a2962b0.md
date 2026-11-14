---
author: AI Engineer
date: '2026-05-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=P_RI1kCkRbo
speaker: AI Engineer
tags:
  - voice-ai
  - full-duplex
  - latency-optimization
  - on-device-ai
  - paralinguistics
title: 语音 AI 的 “Her” 时刻：从级联架构到全双工本地化的路径演进
summary: Gradium AI 创始人 Neil Zeghidour 深入探讨了语音 AI 实现电影《她》中自然交互的核心障碍。文章分析了级联系统的延迟瓶颈、全双工交互（Full-Duplex）在社交反馈中的重要性，以及副语言理解（Paralinguistics）的缺失。最后，他提出了通过本地 CPU 运行的轻量级模型来解决成本与隐私问题，助力语音应用走向规模化。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Neil Zeghidour
  - Eric Schmidt
  - Xavier Niel
companies_orgs:
  - Gradium AI
  - 11 Labs
  - OpenAI
  - Nvidia
products_models:
  - Moshi
  - Phonon
  - GPT-4o
  - Kokoro
media_books:
  - Her
status: evergreen
---
### 语音 AI 的基石：从开源实验室到 Gradium 的使命

**Gradium AI** 的核心使命是解锁语音 AI 尚未实现的巨大潜力。我们不仅训练语音模型，更致力于成为语音代理（Voice Agents）和解决方案的核心组件供应商。我们专注于提供 **语音转文本**（Speech-to-Text: STT）、**文本转语音**（Text-to-Speech: TTS）以及 **语音转语音**（Speech-to-Speech: STS）等底层构建模块，而不涉及具体的垂直业务编排。

我们的团队起源于两年前成立的一个非营利实验室，获得了包括 **Eric Schmidt**、Rodolphe Saadé 和 Xavier Niel 在内的慈善家资助。该实验室专注于开放研究，并开发了全球首个用于实时对话的语音转语音模型 **Moshi**，以及近期推出的可在 CPU 上运行的 **Pocket TTS**。为了让这些技术超越开源阶段并进入生产环境，我们成立了 Gradium 这家营利性机构。

<details>
<summary>Original English Source</summary>

Our mission is to unlock the unrealized potential of voice AI. So basically we train voice models, speech-to-text, text-to-speech, speech-to-speech, whether it's transformation, translation, speech-to-speech dialogue, and so on and so forth. We want to be main model provider for voice for everyone building voice agents and voice solutions. So we are not working on orchestration, we are not working on specific verticals. We just make building blocks for people who want to build voice AI.

This is a spin-off from a non-profit lab we created 2 years ago with the funding from philanthropists including Eric Schmidt, Rodolphe Saadé and Xavier Niel. The main idea was to create a lab that has open research and we focus mostly on speech. So we developed Moshi which was the first speech-to-speech model for conversation, speech-to-speech translation, Pocket TTS most recently a CPU model. And we decided to also create this for-profit structure to make a product that can be used in production beyond open source.

</details>

### 级联系统的瓶颈：延迟与工具调用的阻碍

目前市场上绝大多数语音交互仍采用经典的 **级联系统**（Cascaded Systems: 由 STT、LLM 和 TTS 三个独立环节串联构成的架构）。虽然目前的 TTS 速度已经非常快，但整套系统的端到端延迟仍然难以跨越人类对话的门槛。人类对话通常要求从理解、生成答案到发音的完整链路在 **200 毫秒**（200ms）左右完成，而目前的流式 TTS 本身就需要超过 200 毫秒，这导致交互感依然显得不够自然。

更严峻的挑战在于 **工具调用**（Tool Call: 模型调用外部 API 或执行任务的过程）。当我们追求减少几十毫秒的 TTS 延迟时，一次复杂的工具调用或路由切换可能带来 500 毫秒到 4 秒的延迟，这成为了语音代理最难以预测的瓶颈。为了缓解这一问题，一种解决方案是引入 **填充词**（Fillers: 在等待结果时生成的口语化衔接，如“好的，让我查一下...”），让 LLM 在等待工具返回结果的同时保持对话的自然流转，随后再将结果无缝织回对话中。

<details>
<summary>Original English Source</summary>

Speech-to-text, LLM, text-to-speech, that's the classic Cascade. In our case, we do streaming speech-to-text, streaming text-to-speech with voice cloning, semantic VAD, the classic stuff. In a human conversation, you need the entire stack of understanding, producing an answer, and pronouncing it to be around 200 milliseconds. None of this will allow to have a conversation that sounds human. 

Today, if you have a voice agent that is supposed to use a tool, you're going to wait. The tool call, we are fighting for latency of the TTS, trying to grab 10 milliseconds, 20 milliseconds, and then you have a tool call or open router that is going to have a latency between 500 milliseconds and 4 seconds. I think now the main bottleneck is becoming the tool call, which is very unpredictable. One solution to do that is to have fillers. So basically, your LLM it splits into two things. It sends a tool call. And while it waits for getting the result back, it can keep the conversation going in a natural way, and then it retrieves the result, and it tries to insert it back naturally in the conversation.

</details>

### 全双工交互：电影《她》的核心技术门槛

实现电影《她》中萨曼莎（Samantha）式交互的关键在于 **全双工**（Full-Duplex: 允许系统在说话的同时进行监听，支持双向同时传输数据）。目前包括 OpenAI 的高级语音模式在内的大多数 STS 模型仍是 **半双工**（Half-Duplex: 只能交替进行监听或说话）的。在真实的人类交互中，重叠谈话、咳嗽、以及 **回声辅助**（Back-channeling: 如“嗯”、“对”等表示正在倾听的反馈信号）非常普遍。在日语等文化中，这种反馈甚至占到对话时长的 20%。如果系统无法处理这种重叠，交互就会变得非常生硬且容易中断。

此外，**副语言理解**（Paralinguistic Understanding: 通过语调、语速、情感等非文字信号理解对方意图的能力）也是目前纯文本模型的短板。虽然 STS 模型在理论上保留了音频信息，但如果训练数据仅限于事实性问答，模型就无法学会利用这些情绪线索。我们的 **Moshi** 模型目前仍是少数能实现真正全双工交互的系统之一，它能够处理背景噪音和多人重叠说话，使交互更接近人类直觉。

<details>
<summary>Original English Source</summary>

Speech to speech is the idea that now instead of having the three blocks, you only have one that does everything together. That reduces latency a lot, but that's still not a human conversation. In particular, because every single speech to speech model except Moshi is half duplex. What it means is that the model is either listening or it's speaking. And it cannot handle the ambiguity of human conversation where you can have overlap between people speaking on one another. 

Full duplex—that's a human conversation. In Japanese it's a sign of politeness to do a lot of back channeling. You will say mhm, uh-huh constantly when the other person is speaking and you get up to 20% of the time that is overlapped. Paralinguistic understanding is understanding all the cues that come from the way people speak. Technically, that is in Moshi, that is in any speech-to-speech model because this information is not lost. However, if you don't exploit this information to make your model say relevant things, it's never going to exploit it.

</details>

### 本地化与规模化：解决成本与隐私的 Phonon 模型

语音 AI 走向大规模商业化的另一大障碍是 **成本与隐私**。语音模型的运行极其昂贵，许多科技巨头目前是在亏损运营其语音模式。对于开发者而言，TTS 的 API 费用往往会迅速耗尽融资额，导致用户群增长受限。同时，随着用户向 AI 敞开更多私人数据，对 **本地处理**（Local Processing: 数据在用户设备端进行运算，不上传云端）的需求也日益迫切。

为了应对这些挑战，我们推出了 **Gradion Phonon**。这是一款 **端侧 TTS**（On-device TTS）模型，参数量小于 1 亿（<100M parameters），能够直接在智能手机的 **CPU** 上运行。这意味着开发者无需支付任何 API 费用即可实现高质量、低延迟且具备语音克隆能力的语音应用。相比之下，现有的 Kokoro 等模型虽然优秀，但缺乏语音克隆功能。本地运行不仅保障了绝对隐私，还彻底解决了服务器排队和宕机的问题，是语音 AI 规模化生产的未来方向。

<details>
<summary>Original English Source</summary>

Voice is very expensive. The voice mode of most hyperscalers is run at a loss. It's a gigantic multimodal model, and they lose money every time you use it. LLM now is almost nothing in terms of cost. TTS is really what is going to consume most of the money. I saw people burning their fundraising in TTS bills. Another aspect is privacy. You will be more comfortable if all your private data is local.

To solve that, our first step is Gradion Phonon. It's an on-device TTS. For us, on-device means it runs on a smartphone CPU. It's a very small model, less than 100 million parameter, and for its size, it works quite well. It's better than all the existing on-device models. Kokoro is a good one, but it doesn't have voice cloning. This runs on the smartphone CPU, which means that you can use that to power any kind of voice application without paying a single cent of API fee.

</details>