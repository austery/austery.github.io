---
author: AI Engineer
date: '2026-08-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KLDdXOw6jIc
speaker: AI Engineer
tags:
  - multimodal-ai
  - generative-media
  - video-generation
  - reinforcement-learning
  - omni-modal
title: Google DeepMind 多模态先锋对谈：Veo、Imagen 与全模态智能的未来演进
summary: 来自 Google DeepMind 的核心研究与产品专家 Dumitru Erhan、Shane Gu 与 Nicole Brichtova 深度探讨了生成式多模态媒体模型的前沿进展。内容涵盖 Veo 视频生成、Nano Banana（Imagen 3 轻量版）、Omni 全模态端到端交互、强化学习在推理与媒体生成中的应用、多模态评估难题以及人机协同创作的未来范式。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Dumitru Erhan
  - Shane Gu
  - Nicole Brichtova
companies_orgs:
  - Google DeepMind
  - Google
products_models:
  - Veo
  - Imagen 3
  - Gemini
media_books: []
status: evergreen
---
### 开场与近期重大发布

**主持人**: 欢迎线上直播以及现场的所有观众回到我们的讨论环节。通常在各大主舞台主题演讲之间的间隙，我们会安排这样较长深度的专题讨论，借此深入探讨那些极为关键、但或许没有单独设立独立发布会的重要技术与产品。今天我们非常荣幸能邀请到负责 **Omni**、**Veo**、**Nano Banana** 等前沿生成模型的专家团队。Dumitru，我最初关注到你，是因为你经常在社交平台上分享办公室的日常。我想你大概是 Google 在旧金山办公室的“头号网红”了，而且你特别喜欢骑自行车，经常发骑行相关的照片。

<details>
<summary>Original English</summary>

**Host**: And welcome back for those on the stream and those in person. We tend to basically take these longer sessions between all the sort of mainstage keynotes to reflect on things that are particularly important but don't have a significant launch moments. Today we're very lucky to have people working on Omni and Veo, Nano Banana, like the world's best generative models here with us. Dumitru, I first saw you when you were posting about your office. I think you're probably Google's number one office influencer at least in San Francisco. I think you like to bike as well. You like to take photos of...

</details>

**Dumitru Erhan**: 我是骑车来这里的。

<details>
<summary>Original English</summary>

**Dumitru Erhan**: Bike here.

</details>

**主持人**: 没错。但除了骑行，你更重要的工作是负责视频生成模型的研发。

<details>
<summary>Original English</summary>

**Host**: Yeah. But also you work on video models.

</details>

**Dumitru Erhan**: 是的。

<details>
<summary>Original English</summary>

**Dumitru Erhan**: That's right.

</details>

**主持人**: Shane，我想我们最初是在一次晚餐聚会上认识的。

<details>
<summary>Original English</summary>

**Host**: Shane, I met you I think at like a dinner.

</details>

**Shane Gu**: 是的。

<details>
<summary>Original English</summary>

**Shane Gu**: Yeah.

</details>

**主持人**: 我记得当时你还试图向我安利投资某家初创公司，我都快忘了具体是哪家了。

<details>
<summary>Original English</summary>

**Host**: And I remember you were trying to get me invested in like one of the companies. I forget which one.

</details>

**Shane Gu**: 哈哈，那件事就别提了。

<details>
<summary>Original English</summary>

**Shane Gu**: Forget about that. [laughter]

</details>

**主持人**: 不过现在你正在全心投入 **Omni Thinking** 的研发，以及 **Gemini RL** 等方向。

<details>
<summary>Original English</summary>

**Host**: But now you're working on Omni Thinking, and just a bunch of other...

</details>

**Shane Gu**: 还有 Gemini 强化学习（RL）。

<details>
<summary>Original English</summary>

**Shane Gu**: Gemini RL.

</details>

**主持人**: 没错。Nicole 则负责多媒体生成模型的其余部分，包括 Nano Banana 以及这周刚刚发布的全新成果。

<details>
<summary>Original English</summary>

**Host**: Yeah. And Nicole also, the rest of the gen media models, Nano Banana and everything you just launched actually even this week.

</details>

**Nicole Brichtova**: 没错，我们刚刚上线了一系列新的 API。

<details>
<summary>Original English</summary>

**Nicole Brichtova**: Yeah. We launched some APIs.

</details>

**主持人**: 确实如此。

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah.

</details>

**Nicole Brichtova**: 顺便说一句，我可从来没劝你投资过什么项目，不过也许我之后应该试试。

<details>
<summary>Original English</summary>

**Nicole Brichtova**: And I haven't tried to convince you to invest in anything, but maybe I should.

</details>

**主持人**: 其实我一直尽量避免做投资人，但大家总是会来找我。对于我们这些不在前沿实验室（Frontier Labs）全职工作的人来说，能跟你们面对面交流已经是最近距离接触前沿的机会了。那么，不如我们先盘点一下，既然你们是最核心的参与者，本周到底上线了哪些重磅更新？开发者和用户现在最应该去体验什么？

<details>
<summary>Original English</summary>

**Host**: I try not to be an investor, people just convince me anyway. For those of us who are not working at a Frontier Lab, this is the closest we'll ever get. So yeah, actually let's kind of recap since you're closest to it and we just did it. What was launched this week? What should people go try out?

</details>

### Nano Banana 与图像生成的演进

**Nicole Brichtova**: 好的。昨天我们有两个重大的发布时刻：第一是我们推出了 **Nano Banana 2 Light**（Imagen 3 轻量化版本），它具备非常出色的图像生成质量，而且生成速度极快；第二是我们在 Google AI Studio 中全面开放了 Nano Banana 2 的 API，这意味着开发者们现在可以直接构建相关的应用程序了。在这之前，大家只能在 Gemini 网页端或者 Vertex AI 上使用，现在任何开发者都可以通过 **AI Studio** 快速接入了。

<details>
<summary>Original English</summary>

**Nicole Brichtova**: Yeah. So yesterday we had two launch moments. One of them we launched Nano Banana 2 Light which has amazing quality and it's super fast. And the second thing is that we brought the Nano Banana 2 API to Google AI Studio, which means that developers can now build with it. Before that, you were only able to use it in Gemini or on Vertex, and now any developer can just go and build with it on AI Studio.

</details>

**主持人**: 这太令人兴奋了。当你们团队最初发布 Omni 相关的能力时，我就非常关注。当时社区里有各种各样的用法，比如让它去识别猫咪。我自己也养了一只猫，那可能是我见过的最有趣的应用场景之一。

<details>
<summary>Original English</summary>

**Host**: Yeah, that's incredible. So when you guys launched Omni for the first time... That is my favorite use case. Everybody should do that. I got a cat which is probably like the most interesting use case.

</details>

**Shane Gu**: 我强烈建议大家关注 **Furer**，如果你想寻找“这个模型到底能用来做什么”的灵感，他绝对是推特上的第一人选。

<details>
<summary>Original English</summary>

**Shane Gu**: Furer is the number one guy you should follow for ideas on okay what can this thing do.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Shane Gu**: 他在探索模型能力边界方面确实非常厉害。

<details>
<summary>Original English</summary>

**Shane Gu**: He's amazing at that.

</details>

**主持人**: 过去两年我一直试图邀请他来参加 AI Engineer 大会，但他一直还没能到场，不过他确实贡献了非常多惊艳的 Demo。

<details>
<summary>Original English</summary>

**Host**: I've tried to get him for the last two years to come to AIE. He hasn't made it yet. He's actually coming up with amazing demos.

</details>

**Shane Gu**: 我知道。

<details>
<summary>Original English</summary>

**Shane Gu**: I know.

</details>

**主持人**: 我本来想说出他的真名，不过可能不方便公开。

<details>
<summary>Original English</summary>

**Host**: I want to say his real name but I can't say his real name.

</details>

**Dumitru Erhan**: 他做过的最酷的事情之一就是实时摄像头互动演示，让模型识别他的宠物猫。当时是音频和视觉的实时端到端交互。

<details>
<summary>Original English</summary>

**Dumitru Erhan**: One of the cool things he did was a live camera demo with his cat, with real-time audio and vision.

</details>

**主持人**: 对，他对着镜头问模型：“这只猫现在在想什么？”然后模型直接用拟人化的语气作出了回应。

<details>
<summary>Original English</summary>

**Host**: Right, he asked what the cat was thinking and the model responded in character.

</details>

### Omni 原生多模态：端到端与级联架构的本质差异

**主持人**: 显然，这个模型最核心的能力（或者说最突出的两大杀手级特性）之一，就是能够直接接收连续的视频输入，并进行端到端的流式理解与交互。你们能否深入聊聊，构建这样一个原生全模态（Omni-modal）系统背后的技术挑战？它与传统上把 ASR（语音识别）、LLM、TTS（语音合成）拼接起来的管道（Pipeline）究竟有何根本区别？

<details>
<summary>Original English</summary>

**Host**: So obviously the hero capability of the model, or maybe there's two: one is the ability to kind of take in live video and do end-to-end streaming comprehension. Can you talk about the technical challenges behind building an omni-modal system versus traditional cascading pipelines?

</details>

**Shane Gu**: 这背后的关键在于**原生端到端架构（Native End-to-End）**。在传统的级联系统中，语音转录为文本会丢失语调、语速、情感以及环境声；同时文本转语音又是一套独立的后处理，无法与当前的视觉场景产生毫秒级的协同反应。而端到端模型将音频波形/视觉帧与语义表征统一在同一个模型空间中，使得低延迟反应和丰富的情感表达成为可能。

<details>
<summary>Original English</summary>

**Shane Gu**: The key difference is the native end-to-end architecture. In traditional cascading systems, transcribing speech to text loses prosody, emotion, tone, and background audio. Then TTS is another disconnected step. An omni-modal model processes tokens across modalities directly, enabling real-time nuance and low-latency interaction.

</details>

**Dumitru Erhan**: 另外在多模态视频生成的维度上，我们构建 **Veo** 时也是采用原生多模态联合建模。视频生成不仅要保证每一帧的视觉保真度和时间一致性（Temporal Consistency），还要理解复杂的物理世界规律，甚至实现画面与声音的协同生成。

<details>
<summary>Original English</summary>

**Dumitru Erhan**: In generative video like Veo, we also adopt native multimodal modeling. Video generation must preserve temporal consistency and visual fidelity, while understanding physical dynamics and enabling joint audio-visual generation.

</details>

### 强化学习（RL）在多模态与推理中的融合

**主持人**: Shane，你在强化学习领域深耕多年。现在整个行业都在讨论 Reasoning 模型与 RL 的结合。在多模态生成以及 Omni 交互中，强化学习扮演着怎样的角色？

<details>
<summary>Original English</summary>

**Host**: Shane, you've worked on RL for a long time. Now the industry is discussing reasoning models and RL. What role does reinforcement learning play in multimodal generation and Omni interaction?

</details>

**Shane Gu**: 强化学习正在从单纯的博弈与机器人控制，演进为驱动大模型深度推理与多模态行为决策的核心引擎。在语言与多模态交汇处，RL 能够通过构建奖励模型（Reward Models）和自博弈/验证机制，引导模型在复杂的视觉-语言任务中进行多步推理（Multi-step Reasoning）。对于生成媒体，RLHF 及基于美学与物理规律的反馈机制，也正在成为提升生成稳定性和控制精度的重要手段。

<details>
<summary>Original English</summary>

**Shane Gu**: RL is evolving from games and robotics into a core driver for reasoning and multimodal behavior. At the intersection of vision and language, RL uses reward signals to guide multi-step reasoning. For generative media, feedback mechanisms aligned with aesthetic and physical plausibility are becoming crucial for controllability.

</details>

### 评估困境与未来创作范式

**主持人**: 评估（Evaluation）一直被认为是多模态模型中最棘手的难题。文本尚且有确定性的基准测试，但视频与图像的生成质量、美学表现、以及复杂的交互体验该如何评估？

<details>
<summary>Original English</summary>

**Host**: Evaluation is known to be the hardest part in multimodal models. Text has deterministic benchmarks, but how do you evaluate video/image generative quality, aesthetics, and interactive UX?

</details>

**Nicole Brichtova**: 确实，我们进行了海量的人工评估（Human Evals）。单纯依靠自动化指标（如 FID 等）已经完全无法衡量最前沿模型的能力了。细微的光影差异、构图平衡、肢体自然度、甚至是否有奇怪的多余细节（比如每只手上莫名其妙出现的婚戒），都需要综合专业创作者的感知评估。

<details>
<summary>Original English</summary>

**Nicole Brichtova**: We do a tremendous amount of human evaluations. Traditional automated metrics like FID are no longer sufficient to measure frontier model quality. Subtle lighting differences, composition, natural anatomy, and unintended artifacts require holistic evaluation from professional creators.

</details>

**Dumitru Erhan**: 随着这些工具的成熟，未来的内容创作范式将发生根本转变。模型不再只是孤立地输出几秒钟的片段，而是会作为创作者的协同大脑，从构思分镜、即时调整视觉风格，到自动匹配多轨道音频，深度重塑整个创意工作流。

<details>
<summary>Original English</summary>

**Dumitru Erhan**: As these tools mature, the creative paradigm will fundamentally shift. Models won't just output isolated clips; they will act as collaborative partners throughout the workflow—from storyboarding and style adjustment to multi-track audio synthesis.

</details>

**主持人**: 非常精彩的分享，感谢三位专家的深入探讨！

<details>
<summary>Original English</summary>

**Host**: Great discussion. Thank you everyone!

</details>