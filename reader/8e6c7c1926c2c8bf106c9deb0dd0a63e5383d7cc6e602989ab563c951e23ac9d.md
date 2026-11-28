---
author: Latent Space
date: '2026-03-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=SUjA25ijcNs
speaker: Latent Space
tags:
  - text-to-speech
  - flow-matching
  - end-to-end-audio
  - open-source-ai
  - formal-verification
title: Mistral AI 访谈：Voxtral TTS 发布、端到端语音架构与开源愿景
summary: Mistral AI 团队深入解析了新发布的 Voxtral TTS 模型，详细介绍了其自研的“自回归流匹配”架构及神经音频编解码器。访谈探讨了端到端语音交互的实时性挑战、企业私有数据的微调价值，以及 AI 在形式化数学证明和科学研究领域的广阔前景。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Mistral AI
  - OpenAI
  - Google
  - Meta
products_models:
  - Voxtral TTS
  - Mistral Small
  - Leanstral
  - Whisper
  - GPT-4o
media_books: []
status: evergreen
---
### 私有数据的价值

**Guillaume**: 当客户使用这些现有的**闭源模型**时，令人遗憾的是，他们没有利用好自己收集多年的数据。这些数据量巨大，有时在特定领域内拥有数万亿个 Token，这些都是在公开互联网上找不到的。由于闭源模型无法接触到这些私有数据，客户基本上无法从他们多年积累的见解中受益。

<details>
<summary>Original English</summary>

**Guillaume**: When customers use this offtheshelf close model, what's very sad is that they are not leveraging, you know, these data that they have been collecting for for years or sometime for decades. So much data, sometimes it's trillions of tokens of data in a very specific domain, their domain, which is data that you will not find in the in the public on the public internet. So data on which like the closed model we actually have access. So if they're using like closed source models are basically not benefiting from all this insights, all these data they have collected through years.

</details>

### Voxtral TTS 发布

**Host**: 欢迎来到 Lin Space。我们现在在演播室里，还有我们可靠的联合主持人 **Bibu**，欢迎。

**Bibu**: 很高兴参加这一集。

**Host**: 还有来自 **Mistral AI** 的 **Guillaume** 和 **Pavan**。欢迎。

**Guillaume**: 很高兴来到这里。

**Pavan**: 谢谢。

**Host**: Pavan，你负责 Mistral 的**音频研究**；Guillaume，你是首席科学家。我们今天要宣布什么？我们正在配合你们发布一些东西。

**Pavan**: 是的。我们要发布 **Voxtral TTS**。这是我们的首个**文本转语音**（Speech Generation）模型。这并不是我们的第一个音频模型，之前我们发布过几个。去年夏天我们发布了一个音频模型，但那是用于**语音识别**（ASR/Transcription）的。几个月后，我们在此基础上发布了一些更新，支持了更多语言，并为客户提供了一系列功能，如上下文偏置、分角色转录（Diarization）和时间戳。我们还发布了一个实时模型，可以实时进行转录，不需要等待整个音频文件结束。而这次发布是音频领域的自然延伸，即**语音生成**。我们支持 9 种语言，这是一个只有 **30 亿参数（3B）**的小模型，所以速度非常快。在性能上，它与我们的基础模型处于同一水平，但在成本和效率上要高得多，其成本仅为竞争对手的一小部分。

<details>
<summary>Original English</summary>

**Host**: Okay, welcome to Lin Space. We're here in the studio with our trusty co-host uh Bibu. Welcome.
**Bibu**: Excited for this one.
**Host**: As well as Guiam and Pavan from Mistral. Welcome.
**Guiam**: Glad to be here.
**Pavan**: Thank you for uh Pavan, you are leading audio research at uh Mistral and uh Guiam, your chief scientist. Uh what are we announcing today where we're sort of coordinating this this release uh with you guys?
**Pavan**: Yeah. So we are releasing uh Voxal TTS. So it's our first uh audio model that generates speech. Uh it's not our first audio model. We had a couple of releases before. We had one uh in the summer that was a box our first audio model. But it's it was like a transcription mod ASR like a few months later we released some update on top of this supporting more languages also a lot of table ST features for customers like context biasing theization time stamping and the transcription. We also had some real time model that can transcribe not just at the end of the you don't need to fill your entire audio file but can also come in real time and here this is kind of the natural extension uh in the audio. basically speech generation. So, so yeah, so we support nine languages uh and this is pretty small model 3D model. So very fast very fast and also state of the eco performance at the same level at the at the base model but it's uh much more efficient in terms of cost and also uh much in terms of cost much to go only a fraction of the cost of our competitors and we are also releasing the way that this model is yeah

</details>

### 自研流匹配架构

**Host**: 没错，你们有什么研究心得可以补充吗？

**Pavan**: 我们可以稍后深入讨论，但这是一个我们内部开发的**全新架构**。我们迭代了多个内部架构，最终采用了**自回归流匹配（Auto-regressive Flow Matching）**架构。此外，我们还拥有全新的自研**神经音频编解码器（Neural Audio Codec）**，它能将音频转换为包含语义和声学信息的潜变量 Token（Latent Tokens）。我们对这个模型的质量感到非常兴奋。正如 Guillaume 提到的，这是一个基于我们几个月前发布的 **Ministral** 模型开发的 3B 模型，主要针对 TTS 任务，但它依然保留了文本处理能力。

<details>
<summary>Original English</summary>

**Host**: yeah what's the decision factor
**Pavan**: it's a good question there'll be more yeah provide any other sort of research notes to add on what? No, we uh maybe we'll dive into it later in the forecast too, but it's a novel architecture that we developed in house. Uh we iterated uh on several internal architectures and ended up with a auto reggressive flow matching architecture uh and also have a uh new uh in-house uh neural audio codec uh which uh converts this uh audio into all point by herz uh latent tokens, semantic and acoustic tokens. And yeah, that's uh that's the new part about this model and we're pretty excited that it's uh uh it came out uh with such good quality and like G was mentioning yeah it's a 3B model. Uh it's based off of the ministral model that we actually released just a few months back and instruct trunk and mainly meant for like the TTS stuff but they need text capabilities are also there uh in

</details>

### 音频理解与生成

**Host**: 这里有很多内容要覆盖。我喜欢任何关于**新型编码**的东西，因为这能带来极大的效率提升。Pavan，你之前在 **Gemini** 团队工作，负责语言模型的后期训练，可能很多人在音频模型方面的经验会比纯语言模型少。当你加入 Mistral 并开始做这个项目时，有哪些东西是需要从头开始审视的？

**Pavan**: 我认为音频领域可以分为两个部分：**音频理解**（Audio Understanding）和**音频生成**（Audio Generation）。音频理解模型就像我们去年 7 月发布的 **Pixtral** 系列。虽然我们可以将它们视为统一的模型集，但目前这两类方法略有不同。关于音频如何输入模型，理解模型与我们发布的**像素模型**非常相似。我们将音频通过一个**音频编码器**输入，就像图像通过视觉编码器一样，它产生连续的嵌入（Embeddings），作为 Token 输入到主要的 **Transformer 解码器**中。模型输出只是文本，所以输出端不需要特殊处理。有趣的部分在于生成步骤。输出端现在必须产生音频。我们的方法是使用神经音频编解码器，将音频转换为潜变量 Token。虽然已有许多基于此方法的文献和模型，但我们在设计决策上有所不同。最终，该编解码器将音频转换为 12.5 Hz 的潜变量集。每个潜变量包含一个语义 Token 和一组声学 Token。我们在输入端融合这些离散 Token，虽然有多种融合方式，但我们只是简单地将嵌入相加。

<details>
<summary>Original English</summary>

**Host**: so there's a lot to cover. I always I I love any anything to do with novel encodings and all all those things uh because I think that's obviously it creates a lot of efficiency but also maybe bugs uh that sometimes happen. You were previously at Gemini and you worked on post training for language models and maybe like a lot of people will have less experience with audio models just in general uh compared to uh pure language. uh what did you find that you have to sort of revisit from scratch as you joined MRA and started doing this
**Pavan**: at least when it comes to for I think the there are two buckets I guess the audio understanding and audio generation the audio understanding like the walk through models that was mentioning that we released earlier the the walkrough chat that we released uh I think July last year and the follow-up transcription only uh models family that we released in January that would be one bucket I guess on generation is another bucket. I think uh you can also treat them as a unified uh set of models but currently uh the approaches are a little different between these two to your question on um how audio is like fed to the model in the understanding model it's very similar to actually pixel models that we also released I guess yeah it was pretty I that was the first project I worked on after joined mist it was pretty pretty nice and voxil was uh very similar in spirit I guess so we feed uh audio through an audio encoder similar to uh images through a vision encoder and it produces continuous uh embeddings uh and which are fed as tokens to the main transformer decoder transformer model. Yeah. And the model output is just texted. So on the output side there is nothing uh that needs to be done in these kinds of models. I guess the interesting part about the generation step is the output now has to produce audio and the approach that we have is this uh neural audio codec which uh converts audio into these uh latent tokens. there is uh a lot of uh existing literature and a lot of models uh which uh are based off of this kind of approach and we took a slightly uh different I guess design decisions around this but at the end of the day the neural audio product converts audio into a 12.5 Hz uh set of latent and each latent is has a semantic token and uh a set of acoustic tokens and the idea is that you take these discrete tokens and and feed it on the input side. There's several ways to fuse this at each frame, but we just sum the embeddings. So, it's it's kind of like having k different vocabularies and kind of combine all of them because they all correspond to one audio frame on the input side.

</details>

### 流匹配 vs. 深度 Transformer

**Pavan**: 输出端更有意思。一种流行技术是使用**深度 Transformer**（Depth Transformer），因为每个时间步有 K 个 Token，而文本只有一个。人们通常会用一个小型的 Transformer 或 LSTM/RNN 来以自回归方式预测这 K 个 Token。我们做得不同的是，我们没有采用这种自回归的 K 步预测，而是使用了**流匹配模型**（Flow Matching Model）。我们训练编解码器同时具备离散和连续特性。我们也尝试过离散方式，效果不错，但连续潜变量的效果更好。流匹配磁头（Flow Matching Head）接收来自主 Transformer 的潜变量，类似于扩散模型中的去噪过程，但在流匹配中，它是一个**速度估计**（Velocity Estimate）。你从噪声潜变量一直演化到音频潜变量，对应 80 毫秒的音频，然后通过声码器（Vocoder）转换回音频帧。

<details>
<summary>Original English</summary>

**Pavan**: The output side is the interesting part on the output side. The it's not the I don't know if it's the most popular, but one popular technique is to have a depth transformer because you have k tokens at each time step like with uh text you just have one token at each time step. So you just do like uh predict the token from the vocabulary with yeah with just you get probabilities. This a very straightforward tip. Very straightforward. Yeah. But if you have K tokens, then the main thing would be to predict all of them in parallel. But that doesn't work. Uh at least that doesn't work that well because audio has more entropy. And the one of the techniques people use is this depth transformer where you uh you almost have a small transformer or it can be LSTMRN as well but people use transformers and you predict the K tokens in auto reggressive fashion in that. So you have two auto reggressive things going on. So the thing we did differently is instead of having this auto reggressive kstep prediction we have a flow matching model instead of modeling this as a discrete token set we we train the codec to be both discrete and continuous to have this flexibility. So we did try the discrete stuff too and it works well but the continuous stuff works just better. So yeah we took this flow matching. So the it's a flow matching head which takes the latent from the main transformer and kind of like in diffusion it's dino noising but in this flow matching it's a velocity estimate. So you kind of uh uh go from this noised uh latent all the way to the audio latent which corresponds to 80 mcond audio and then which is sent uh through the voder to get back the 80 mcond audio frame.

</details>

### 音频领域的“未竟之地”

**Host**: 这是流匹配在音频领域的首次应用吗？因为我通常只在图像领域见到它。

**Pavan**: 实际上音频领域也有一些流匹配模型，但我认为这种特定的组合是比较新颖的。视觉社区大得多，他们开拓了很多扩散和流匹配的工作，将这些想法引入音频很有趣。更宏观的一点是，音频领域还没有一个公认的“胜出模型”。大家都还在迭代，探索最佳方案。音频空间非常令人兴奋。如果你想要**实时生成**，这是我们选择这种方法的一个重要原因。

<details>
<summary>Original English</summary>

**Host**: Yeah. Is this the first application of flow matching in audio? Because uh usually I come I come across this in the image.
**Pavan**: Yeah, actually in some sense there are models uh flow matching models in audio but I think this this specific combination I I I could be wrong. There could be some work. I haven't seen I haven't seen much work in this. So I I think it's it's novel and a lot of u it's just a way bigger community right. So they I think they pioneer a lot of these diffusion flow matching work and it's interesting to adopt some of the ideas there into audio and yeah and personally that's the the part which is trying trying out one of and more meta point is unlike text even in vision I think this is true but in audio is that there is no uh winner model yet there is no okay this is the way you do things it's uh it's still evolving I think people are still iterating and figuring out like what's the uh best overall recipe I guess the the idea I mean pretty sure uh there are models which are also completely end to end like NATO audio and native audio but it's still not like uh come to a convergence point where this this right way to think that also makes the space pretty exciting to explore what are some of the ways to look at it like there are ways where you can do diffusion for audio generation but if you want like real time generation that's a big thing with the approach I'm assuming that you took Yeah.

</details>

### 面向语音智能体的优化

**Host**: 你们是如何在关心的不同维度上进行权衡和评估的？

**Pavan**: 好问题。你可以对整个音频进行流匹配或扩散，但我们没有走那条路，因为我们主要的应用场景之一是**语音智能体**（Voice Agents），我们需要**实时流式传输**。所以我们选择了自回归方法。在自回归空间内，你可以分块处理。我们更倾向于最简单的方法，所以我们尝试将音频作为另一个 Head 添加到常规的 Transformer 解码器模型中，这使得未来音频与文本的**原生端到端建模**变得更容易。效果非常好。我们也尝试过离散扩散方法，效果也不错，但流匹配的表现更出色。

<details>
<summary>Original English</summary>

**Host**: And also like how do you go about evaluating different axes of what you care about, right? So yeah,
**Pavan**: good point. I think we uh so you can do just flow matching diffusion for the whole audio. We didn't even go down that path because one of the main applications is uh voice agents and we want realtime streaming and that's the use case. That's not the only use case but that's one of the primary use cases we want to get to. So we picked the auto reggressive uh approach for that and within the auto reggressive space again you can do chunk by chunk or you can do uh so we pick the I think at least personally prefer the approaches which are the simplest I guess and so we try to see can we just add audio as just another head to our regular uh transformer decoder model because that kind of makes it easier for eventual end to end modeling of audio text native modeling. Yeah. And it works pretty well. So I guess we kind of uh went with that and we tried it a little bit with the flow matching head itself. Like we had a discrete diffusion kind of approach which also works well but the flow matching worked quite

</details>

### 通向“全双工”模型

**Host**: 我很好奇你们团队之间是如何协作研究方向的？

**Guillaume**: 我们共同确定特性的优先级。音频领域能做的事情太多了，我们必须决定如何开展。例如，我们最终想要构建的是**全双工（Full Duplex）**模型。

**Host**: 确认一下，“全双工”意味着它可以边听边说？

**Guillaume**: 是的。我们最终会达到那里，但我们决定一步步来。首先从客户最需要的特性开始，比如转录是最流行的用例，然后是语音生成，实时性紧随其后。我们希望在把所有功能合并成一个“超级全能模型”（Super Omni Model）之前，先优化每一项能力。

<details>
<summary>Original English</summary>

**Host**: I was just curious about how you also think about uh this overall directional research like do you basically when you work with the audio team do you set uh some highle parameters and then let them explore whatever or how does it work between you guys?
**Guillaume**: No, I think the the way it works is that we are we are prioritizing together I think what are the most important features. There are many many things we can do in audio. I think we try to decide like how we should do things. For instance, ultimately what we want to do is to build this full duplex model. But we are not going to start this start there directly. I think it's some project people are doing but
**Host**: just to confirm full duplex means it can speak while I'm speaking or okay audio.
**Guillaume**: Yeah. Yeah. So ultimately we're going to get there but for us it was I mean we decided to take it like a step by step. So we start with whatever is the most important I think also for customers which is the transcription is the most popular use case then the speech generation the real time just a bit before that and then actually to be like more try combine everything all together but uh but yeah we thought it was also important to like separate things and like optimize each capability one by one before we all of that together. then the the the super omni model

</details>

### 捕捉语言的微妙之处

**Pavan**: 即使在同一个时间步，也有很多待预测的信息分布。在文本空间，为了简单起见，一个词可能只对应一个 Token。但在音频中，即使是同一个词，用你自己的声音也可能有无数种不同的**语调**（Inflection）。流匹配能很好地模拟这种分布。你的直觉可能是，它存在几个不同的聚类，每个对应一种特定的语调或发音方式。你不能只预测它的平均值，因为那会产生模糊的语音，你必须选中其中一种，然后使其清晰。

**Host**: 条件推理（Conditional Inference）。

**Pavan**: 没错。

**Host**: 这一切都包含在**非流利性**（Disfluencies）中吗？这是音频领域的术语，包括停顿、语调等。顺便说一下，我要感谢 Sophia 整理了这些很好的笔记，因为我对音频不太熟悉。

**Pavan**: 没错，非流利性是其中一种现象，比如“嗯”、“啊”。

**Guillaume**: 还有重复，比如当你思考时，你会重复某个词。

**Host**: 而语调则是升调之类的？

**Pavan**: 是的。这里存在很大的熵。**深度 Transformer** 在条件建模方面做得很好，即使它只是个微型 Transformer。但主要考虑的是延迟：如果你有 K 个 Token，就需要做 K 步自回归。流匹配能显著降低延迟，我们能以 16 步甚至更少步数完成推理。

<details>
<summary>Original English</summary>

**Pavan**: No, I think the main main thing is like uh even at a particular time step there is a distribution of things uh to be predicted like the way you in so you already know the word that you're speaking and yeah the in text space let's say the word maps to just a single token for simplicity in most cases it does so there is uh not a lot of like so you just pick the word but with within audio even the same word could even with your own voice be inflicted in so many different ways and I think uh uh any approach which like models this distribution and well and flow matching is one one of the it's not the only one at all but it's it's a one which works pretty reasonably well I think does better so you have to pick across several different like uh the the intuition I have is it's it's there are some several different clusters each corresponding to some specific way you would inflect pronounce that thing and you can't predict the mean of it because that corresponds some blurred out speech or something like that, but you have to uh pick one and then like sharp
**Host**: conditional inference.
**Pavan**: Yeah, exactly.
**Host**: Is that all covered under disluencies, which is I think the the normal term of art and discuencies, pauses, intonations. By the way, I have to thank Sophia for setting all this up, including like some of these really good notes because
**Pavan**: yeah, I'm less familiar with the audio. No, no, I think discies are definitely one such phenomen which is arms. Yeah, also repeat like if you're like like uh you do this filler words, you're thinking so you repeat the word.
**Host**: Okay. Whereas inonation is like a is up uh up speak and all this. Okay.
**Pavan**: Yeah. So I think there is a lot of like entropy and modeling it as a distribution and uh any technique which helps with it and the depth transformer is a conditional way of modeling this and transformers actually good at it even though that's a mini transformer. So I think that worked pretty well too for us too. It's just that the main consideration is when you have a depth transformer, if you have K tokens, you need to do K autogressive steps. So even though it's a small thing, it's like K steps, which is very latency heavy. With flow matching, we were able to cut it down significantly. So we are able to do the inference in quad steps or 16 steps and it works pretty well.

</details>

### 高效模型的策略

**Host**: 你们选择 3.6B 或 4B 作为骨干网络，是为了适应特定的硬件或延迟约束吗？

**Guillaume**: 不一定。我们非常在意效率。我们有很多独立的专用模型，比如我们有一个非常小巧高效的 OCR 模型。有些公司选择做一个能做所有事情的通用模型，但那很昂贵。我们想说的是，如果你关心特定的用例，这个专用模型会极其出色且高效，其性价比远高于包含冗余能力的通用模型。

**Host**: 相比其他 TTS 模型，它的表现如何？

**Guillaume**: 非常好，绝对是目前顶尖水平之一，很可能是最好的**开源模型**。

<details>
<summary>Original English</summary>

**Host**: efficiency wise like I I imagine like the reason it's open weights uh the reason you pick 3.6b backbone uh it 3.4b 4B uh you are trying to fit to some kind of hardware constraints. You're kind of to fit some kind of latency constraints. What what are they?
**Guillaume**: Not necessarily. I think uh something we care about in our model that they are efficient. So we have like a lot of separate model for instance um so we have this red is very small very efficient. We also have like a small OCR model that is really very good really efficient as well. And uh I think an approach that maybe other I think companies are going to take is to have like a very general model that will do a bit of everything. But that is also going to be expensive. And here what you want to say is if you care about this specific use case you can actually use this model. It just does that. It's extremely good at it but so very efficient. That's why we can actually models a but like OCR that are like really really good at that and that will be much more cost effective than than the general models that will contain a lot of capabilities. You don't really need the test. So so yeah. So, we're doing like general model, but also like more customized model like this.
**Host**: How does it compare to other TTS models? It's, you know, we're going full open wave. We're just dropping it like
**Guillaume**: Oh, I think it's pretty good. I think it's pretty good. Like, it it's definitely one of the best for sure. It's probably I I would say it's the best open source model, right?

</details>

### 为何深耕音频？

**Host**: 为什么是现在？这如何融入 Mistral 的愿景？你们如何看待**语音智能体**的未来？

**Guillaume**: 我们有很多客户在寻求语音功能。虽然转录看起来像简单的模式识别或分类，但当你真正与模型交谈时，你会发现它还不够自然。在英语中表现尚可，但在法语等其他语言中，人们说话时往往会变得非常缓慢和生硬。目前还没有达到那种自然的程度。我认为 progress 还在继续，路径很清晰。

**Pavan**: 我在几年前曾在 **Google Assistant** 团队工作过。回过头看，短短四五年间，我们已经实现了完全的语音输入、语音输出、函数调用，且整个过程完全端到端，这非常迷人。但正如 Guillaume 所说，差距依然存在，还没到像和真人说话那样的程度。

<details>
<summary>Original English</summary>

**Host**: Yeah. Why now? How does it fit into broader mist vision? How do you see voice agents? How do you see voice? Like I I think every year I've heard okay you're a voice you're a voice there's a lot of architectural stuff there's a lot of ant latency that you're solving but where do you see voice heading we had so many customers asking for for voice that's also why we wanted to to build it uh what's kind of interesting in this domain is that in a sense if you take something simple like transcription it doesn't seem like something that should be very hard to do for a model it's essentially it's pattern recognition it's classification this are very good at classifying right nonetheless when you talk to them. I mean it's it's not there yet, right? It's not you don't talk to them the same way you talk to a person on something maybe people don't realize it in English it's still much better than in any other language even compared to French for instance if you talk to this in French I mean when you see people talking to this they will talk very slow they will articulate as much as they can so it's not natural right we are not yet to this uh I think yeah maybe the next generation will not know this but yeah I think people that are maybe our age will actually always keep this bias speaking very slowly when they talk to this model even if maybe probably in a couple of years there may be an So it would not be necessary anymore. But yeah, but what's interesting is to see that um even for like languages like French and Spanish, German that are not no resource on release, you have a lot of audio with this there and still it's it's not as good. So and I think a consequ I mean reason for this I suppose there is not as much energy as much effort that has been put in some other modities like that for some vision or like coding but but there's still a lot of progress to be done. I think it's just a question of doing the work and it's a you like a clear path I think to to get there.
**Pavan**: It's a little fascinating because I worked on Google Assistant. I I think while back at this point, but it's I think um it's it's kind of like when you take a step back, it's fascinating. It's not that long ago. It was like 4 years ago or 5 years ago and it's like now it's a completely audio in audio out and the function calling and the whole thing happens completely end to end and in a very natural natural way and still ways to go like you was telling even despite all the previous it's not like you're speaking to a person uh when you talk to any of these uh uh uh agents bots or voice mode kind of situation it's still still like a gap I take that's the great part and I I feel like with even the existing stack we should be able to get to this uh uh very natural uh speech uh conversational abilities uh soon enough I guess and uh we'll also hope hope to get there and it's kind of the next step right because when you talk to these agents like usually people are just writing to them and sometimes they have like this very clear for instance you you want to write code but you you have like a very clear idea of how you want the model to implement what you have in mind but uh so here you are having to spend like a lot of time writing so it's not really efficient on like audio is really like a natural interface that is just not there yet but I think it's just going to be the right place.

</details>

### Mistral Forge 与私有云部署

**Host**: 服务和推理的情况如何？我们看到很多现成的 LLM 很容易部署，但在音频模型分发渠道上是否存在滞后？

**Guillaume**: 这正是我们与客户合作的重点。他们通常有严密的隐私顾虑，不希望敏感数据离开公司。所以我们帮助他们在内部部署模型，无论是本地（On-premise）还是**私有云**。许多公司对不同敏感度的数据有不同处理流程（如 CH1, CH2, CH3 等），有些数据绝对不能传到云端。通过本地部署，他们不再担心泄露。另一个价值点是，很多客户拥有积累了几十年的私有领域数据，有时多达数万亿 Token，这些数据不在互联网上，闭源模型无法触及。虽然可以在推理时提供上下文，但永远不如用这些数据训练模型来得好。

**Host**: 这就是 **Mistral Forge** 平台的作用。

**Guillaume**: 是的，我们在 GTC 上宣布了。这是一个包含多种工具的平台，帮助客户处理数据并进行训练。这些工具正是我们科学团队内部使用的，非常成熟且经过实战测试，涵盖持续预训练、微调、SFT、RLHF 等。客户往往没意识到，用自己的数据微调后，模型会变得多么强大。相比于给模型喂 10k 的上下文，让模型吸收整个公司的知识库要高效得多。

<details>
<summary>Original English</summary>

**Host**: How's it like building, serving, inferencing? Like we see a lot about it's very easy to take LLMs off the shelf, serve them. Uh fine-tuning, deploying uh I know you guys have a whole like you have forge, you have a whole stack of customizing, deploying. Is there a lag in getting that like distribution channel? Are you are you helping there?
**Guillaume**: Yeah, I mean I think this is a lot of what we're doing with our own customers. I mean very often they come to us. So it's for different reasons. I think one reason is sometimes they have this lot of privacy concerns. They have this data that it is very sensitive. They don't want the data to leave the company. They want it to stay inside the company. So we help them deploy model inhouse. So either on either on premise or on private cloud. So they are not worried that it's given to a third party and that there's some leakage. Sometimes they have this kind of uh many many companies have this different you know sensitivity of data they have like sometimes ch one ch two ch three you can send it to the cloud ch it has to stay there so then it creates some kind of heterogeneous workflows where it's kind of annoying I mean you cannot send some data to the cloud this one you can so so here when we actually deploy the model for them they don't have this consideration they are like not worried that you know this is going to leak everything is much easier so we help them basically do this on the so it's one of the value proposition but Um but the other is very often I mean when customers use this offtheshelf close model what's very sad is that they are not leveraging you know this data that they have been collecting for for years or sometime for decades so much data sometime it's trillions of tokens of data in a very specific domain their domain which is data that you will not find in the in the public on the public internet so data on which like the closed model we actually not have access to one which is not going to be really good. So if they're using like closed source models are basically not benefiting from all these insights all these data they have collected three years they can always give it into context that inference but is it's never as good as if you actually train the model this so so yes that's basically what we help them to do we actually provide them some some mal approach is basically what we announced at GTC this week so we provide them with this it's basically like a platform with a lot of tools uh to actually help them process data train on that yeah it's actually the same thing that we are using in the science team so it's actually very battle tested infrastructure like a lot of efficient training codebase for like a continu pre-training like a fine tuning even doing SFT IRL uh so we help them do this using the same tools as what our team is building is using so since it's tools that we've been using for like two years now it's really pated it's really like sophisticated so it's the same thing we are giving to them we're giving the company the same thing that what our still using internally to actually build their own AI and it makes a really big difference I think sometime customers and many people in general don't realize how much better the model becomes when you fine it on your own data. You can have like a your model is here and you start from there. You have like a close source model which is sort of here. But if you actually fine tune you can actually really really go much further than this and then you have like a very big advantage. The model is trained on your entire company knowledge. So it knows everything. You don't have to feed like 10k tokens of context at every query. So it's it's much easier. It's a bit I think using a closed source model it's really sad because it basically puts you are not leveraging all this data and you are going to be using the same model as all your old competitors when you using I mean everything you've been collected for years which is really valuable so so yeah so we help basically customers do this we we have a lot of solution um I mean deployed for engineers that go in the company that basically look at the problem customers are facing look at what they're struggling to do what we should do to solve it so we help them solve them together.

</details>

### 定制化与边缘计算

**Guillaume**: 我们的方法与竞争对手不同。我们不只是提供一个 API 终端或一个模型权重。我们与客户紧密合作，解决他们的具体问题，提供定制化方案。比如，有些客户需要模型在某些**亚洲语言**上表现极其出色。对于通用的 Off-the-shelf 模型，这些语言在训练数据中可能只占 0.1%，表现并不理想。我们会为他们训练一个新模型，将该语言的占比提高到 50%，使其精通各种方言。还有一个例子是汽车行业的客户，他们需要一个能做音频交互且具备函数调用能力的 3B 模型，并且必须是**离线运行**的，因为车里不一定总有网络。我们在网上找不到这种现成的模型。

**Host**: 这就是 Mistral 的杀手锏。

**Guillaume**: 很多客户先用闭源模型做原型，效果不错，但想投入生产时发现太贵了。他们回来找我们，我们可以通过微调提供一个便宜 10 倍且在本地服务器上表现更好的方案。

<details>
<summary>Original English</summary>

**Guillaume**: So it's a I think our approach is a bit different here than some other companies and competitors. It's we don't just release an end point and say some stuff on top of that or we don't just give a checkpoint. We we really look very closely with customers. We look at the issues they have. We had them solve them. We really make some tailor solution for for the problem they're facing. some example are also going to be sometime where some customers they really wanted to have a really good model really performant on some like Asian languages on the if you take some of the shift model they can speak it they can write in this language but it's it's not amazing this language will be like maybe 01% of the mixture so it it has it has been included during training but very very little so what we did here is that we train a new model for them but this language was 50% of the mix so it's much much stronger it knows of the dialects it knows the long. So it's a Yeah. So it's some example of things we can do and it's it's really arbitrarily custom. I think some of their customers for instance they wanted some they wanted some 3D model that can do audio with like very good at functioning. So something you wanted to put in the car in particular they wanted this to be offline because in a car you don't necessarily have access to internet. So so yeah so here we can actually build the solutions. There is no like model out of the box on this in the internet. You have this very you have this very general model generalist like reasoning on strong model but for things like this they always want like specific solutions and yeah on some of the reasons sometimes they come to us is because um you know like they they experiment with some closed source model they get some prototype they are happy with what they build it works well they're happy with the performance and then they want to go to production and then they but it's extremely expensive you cannot push this it's a so then they come back to us and they say can you add help us build the same thing as this but using something much cheaper on here. On here we can sometime build something 10x cheaper by just fine tuning a model and it will be better on prem on their own server and also much cheaper as well.

</details>

### 音频微调：术语与个性化

**Host**: 是否也存在语音层面的微调？

**Pavan**: 在 Forge 框架中，我们支持音频微调。我们的 **Voxal** 系列比 **Whisper** 更强大，社区中有很多人在微调 Whisper，他们也会想微调 Voxal。用例包括：支持一些模型原生未覆盖的长尾语言；或者在特定领域（如医疗、法律）中使用专业的术语和术语表；还有在特定的**声学条件**下（如高噪音环境）提升表现。

**Guillaume**: 文本转语音（TTS）的微调则不同，它更多涉及**声音个性化**（Voice Personalization）和企业适配。企业需要特定音调、特定个性的声音来代表品牌，并满足安全考量。

**Host**: 我们从来没聊过**声音克隆**。它有多重要？

**Pavan**: 主要用例是企业个性化。你肯定不希望拨打两家不同公司的客服电话，听到的声音完全一模一样，那很奇怪。此外，像医疗保健领域的移情助手（Empathetic Assistant）所需的语气，与客服机器人或纯对话式应用完全不同。这些都是企业需要的定制化方向。

<details>
<summary>Original English</summary>

**Host**: I'm curious is is there also uh voice finetuning that people do?
**Pavan**: So in this in this forge we we also have it's a unified uh framework uh and the the hope is like the walkers uh speech to text uh that we released earlier this year and uh even the walker chat that we released last year and I think uh a big people I think there's a big uh uh rich ecosystem of uh people finding whisper and people want the same thing with walker it's much stronger than than whisper and yeah the uh the platform offers that kind of fine-tuning. Uh yeah, which could be any kind of finetuning like for instance even sometimes people want to support new languages to this which are uh tail languages which we hope to cover um our natively but if there is a language where you have data and you want to fine-tune I think this is a good use case or the other use case is you it's the same language like even English uh but it's in a very domain specific way terminology jargon medical stuff exactly and also the specific uh acoustic conditions like uh there's a lot of noise or the and the model will do uh decently in most conditions but you can always make it better and that those are some of the use cases where you can uh improve it even further and u that's one good use case for this and for u uh text to speech we're just releasing it so we'll we'll have support for that soon too I think it's similar use case it's little different the kind of things that you want to extend a text to speech model to which could be like voice personal ization, voice adaptation for enterprises and many enterprises need like very specific kind of tone, very specific kind of like personality for this kind of voice and all of those are like good good use cases for finding.
**Host**: That's what I was going to ask you. You know, we never talked about cloning, voice cloning here. How how important is it? Right? Like I can clone a famous person's voice. Okay. But
**Pavan**: the main use case would be like for enterprise personalization. Like enterprises need like lot of customization. You don't want the same voice for like all the enterprises. Each enterprise uh want a customized specialized uh something which is representative of both their brand and also their uh I guess safety considerations and the use case like I think the kind of thing that you would deploy as a empathetic assistant in the context of a healthcare domain would be very different from the kind of thing that would be in a customer support bot uh and would be different from uh like more conversational aspects. So I think those are the customizations you would expect from an enterprise and that's the main use case at least from from us right

</details>

### 长文本建模：从 Whisper 到 Voxal

**Host**: Whisper 以处理 30 秒片段著称，而你们将其扩展到了 40 分钟，论文中有很多关于填充（Padding）和合成数据生成的细节。你们如何生成长篇且连贯的语音？

**Pavan**: 会有技术报告详细说明。简而言之，我们现在有了自研的实时模型编码器，采用了**双流架构**（Dual Stream Architecture），这是一个具有因果性的（Causal）多语言编码器，社区目前还缺乏这种强力编码器。在 TTS 方面，它依赖于自回归解码器骨干。长上下文的逻辑与文本非常相似：模型以 12.5 Hz 处理音频，1 秒对应 12.5 个 Token，1 分钟大约 750 个 Token。在 8K 上下文窗口中可以处理 10 分钟，32K 窗口则可以处理半小时。我们非常擅长 32K 甚至 128K 的长上下文训练，所以理论上可以扩展到长达数小时的生成。

<details>
<summary>Original English</summary>

**Host**: yeah I've hyped up this paper enough we covered it somewhere but uh a big thing so Whisper is known for 30 secondond generation uh 30 secondond processing you extended this to 40 minutes there was a lot of good detail in the paper about how this was done even little niches of how the padding is so like it it's very much needed you need to have that padding in there the synthetic data generation around this I'm wondering if you can share the same about the new speech to text right uh text to speech so how do you how do you generate long form coherent how do you generate you know how do you do that and and any gems. Is there going to be a paper?
**Pavan**: Yeah. Yeah, there would be a technical report. Yeah, I think it will have a lot of details. Uh but uh I think the summary of it actually some of the considerations in this paper were because we started with the whisper encoder as the starting point and now we have in-house encoders like the real time model for instance which we released in January. We also released a technical report uh for that real-time model as well which is this dual stream architecture. It's an interesting architecture. Uh you should check it out. And there we have a causal encoder and I don't think there's any strong multilingual causal encoder uh out in the community. So we thought it's a good contribution. So that's that's one nice encoder. If other people want to adapt that's that's a good encoder and we train it from scratch. I think our pull stack is now mature enough that we're able to train super strong encoders and some of these considerations like sparing and stuff is a function of the whisper encoder. And now that we uh train uh encoders in house, the design concentrations are different. And for the question on like uh text to speech, I think that's also like leans on to the original auto reggressive decoder uh backbone. I think uh it's almost identical considerations. I think the long context in uh it's not even long. So the model processes audio at 12.5 hertz. So 1 second maps to like pulp point by tokens. So I think 1 minute is like 720 tokens. So you can get like up to 10 minutes in like 8K context window and get half an hour in 30k context window. So that's uh
**Host**: and 32k context is something that's we are very comfortable training on. We can extend it to even much longer 128k. So you can naturally see how it can extend to even hourong generations. Yeah we need the like data recipe and the whole algorithm to uh work coherently enough through such long long context but the techniques are some some way uh very um similar to the text long context modeling uh and the key difference is it's just doing flow matching autogressively instead of like uh uh text open prediction

</details>

### Mistral Small 与能力合并

**Host**: 我有个关于 **Mistral Small** 的大问题。什么是“Small”？如何定义它？我记得以前 7B 模型在我笔记本上都跑不动。

**Guillaume**: 这只是个术语问题。我们本可以叫它 Medium。这是一个**专家混合模型**（MoE）。以前我们是以独立团队开发独立模型：一个团队做指令遵循，一个团队做代码（Codestral），一个团队做数学推理。现在我们将所有这些能力合并到了一个模型中。Pixtral 是我们第一个视觉模型，现在我们也将其合并进来。未来我们会把更多能力，如函数调用、更强的推理，集成到这些模型中。我们还在开发一个更大版本。它的特点是非常**稀疏**（Sparse），只有 6B 激活参数，服务效率很高，并支持 256K 上下文。

<details>
<summary>Original English</summary>

**Host**: okay I think that was most most of the the the sort of voice questions that we had but um I have a I have a big question on Mr. M small. Let's go. Um, so what is small? How do we define small? What is this? What is this? I remember the days of ML 7B on my laptop. It's not fitting on my laptop. I could I could run it on a big laptop, but
**Guillaume**: it's just a different question of terminology. I suppose give it another name. But uh yeah, we could have called it medium but then I think this I suppose but yeah it's a model that we released minister of experts uh it's a model that combines different uh model before the way we were doing is that we had one model general model for doing instruction following where like a separate model that was deflated coding specified specific to code we had another model for reasoning magistral So this were separate artifacts built by different team at what we are doing is basically merging all of this it was pal the first vision model we had was like a separate model on the way we would kind of do things internally that we have like one team focus on one capability build one model and then when it's mature enough we decide to merge this into the main texture so so here was the first time we basically merge all of this into into one there are some other things we didn't have time to merge in time for instance more capabilities or like function coding I think we are it's going to much much better in small proper phone but uh but so it's a test model we're working on a larger version of this and yeah I mean key things is it's very sparse 6B active so you know pretty efficient to serve uh 256k context um yeah

</details>

### 开源使命与科学 AI

**Host**: 这种“单独开发、随后合并”的策略非常有趣。开源对你们来说仍然是核心吗？

**Guillaume**: 开源属于公司的灵魂。我和 Arthur 曾在 Meta 负责 **LLaMA** 的发布。在那之前，大学的研究人员几乎无法研究语言模型。LLaMA 开源后，很多技术如 DPO 都是由能够接触到这些模型的社区开发的。我们希望为这个生态做出贡献。我们不希望看到最智能的模型被锁在少数几家大公司门后，由他们决定谁可以使用智能。我们希望 intelligence 对所有人都是可用的。

**Host**: 你们最近还发布了 **Leanstral**？

**Guillaume**: 是的。我们内部有一个小团队专门研究**形式化数学证明**（Formal Math Proofs）。虽然 Lean 社区很小，但其数据是极其宝贵的，因为它们是**可验证的**。在数学推理中，很多问题没有简单的验证方法，你不能只靠比较答案。但在 Lean 这样的系统中，只要代码能编译，证明就是正确的。这在软件验证领域非常有潜力，比如航空航天和机器人领域，代码的正确性关乎生命。

**Host**: 我的理论是，形式化证明可以作为**长程推理**（Long-horizon Reasoning）和规划能力的代理指标。

**Guillaume**: 绝对如此。我们已经在数学推理模型上看到了这种能力的迁移。模型可以主动提出：“我要证明这三个引理”，并并行地去证明它们。这比简单的 0 或 1 奖励要有趣得多。

<details>
<summary>Original English</summary>

**Host**: No, I mean you got to check that. But then I mean I just want to hear more broadly on open source for you guys. And when you had asked earlier about what's next, what are the other, you know, side tubes working on, you you put out lean straw. Um, this one is a surprise. I was like, I don't this doesn't fit my mental model. M.
**Guillaume**: Yeah. I mean, um, I mean, first for open source in general, I think it's really something which belongs to the journey of the company. I think we started it around this. We uh, so we have been open sourcing with us since the beginning and even before this. So before this. So me and Tim were at meta we released LMR and I think what was really nice to see that before this for most researchers like universities it was impossible to to work on lens there was no outside and if you look at many of the techniques that were developed after for instance TAM was open source like all these post training approaches like even DPOD like preference optimization all of these were done by people that had access to this pel and it would have been impossible to do without this so it's really making sense move faster so we really want contribute to this open ecosystem. ... We really don't want to be living in a world where the the the smartest model the best models are only behind you know like closed doors only accessible to like a few companies that we you know have the power to decide who can use them or not. I think it's kind of a scary feature we don't want to live in. We really want this model to be accessible to to anyone but you want intelligence to be used and accessible by anyone that can use it. ... yeah lin trial I think is also one step into this direction ... we were working on reasoning ... what's nice with lin and with formal probing is that you don't have to worry about this whatsoever. We just they're all function as long as it compiles in lean is functionally the same. Right. Exactly. It's like a program if it compiles it's correct.

</details>

### 下一个前沿：RL 与科学研究

**Host**: 下一个研究前沿在哪里？很多人在讨论强化学习（RL）和计算资源的倾斜。

**Guillaume**: 我们仍在深耕预训练。我认为 **Mistral 4** 的预训练将是飞跃性的一步。在 RL 方面，我们正在开发支持超长轨迹（Long Trajectories）的算法和基础设施。有些问题的奖励可能需要 6 个小时才能获得。

**Host**: 你们在招聘什么样的人才？

**Guillaume**: 科学团队和前向部署（Forward Deploy）团队都在招人。我们在巴黎、伦敦、帕罗奥图、苏黎世、华沙和纽约都有办公室，很快也会在旧金山开设办公室。我们倾向于保持精简敏捷的小团队。我们对 **AI for Science** 特别兴奋，正在探索 AI 在物理、材料科学等领域的应用，这些领域 AI 尚未被充分利用，但潜力巨大。

<details>
<summary>Original English</summary>

**Host**: where are you guys seeing the frontier of research in that
**Guillaume**: Yeah, I think for us uh we are still working a lot on the pre-training side. We are very very far from this sort of situation on the pre-training. I think ML4 preing will be like big step compared to everything we have done before. So we are pretty excited about this and I think on the side I think now we have more and more to think about this algorithm that will actually support this very long trajectories. I think uh when it was for instance GRPO for doesn't really work with this tiny bit of policy which was okay initially because you are solving math problem that can be solved like a few thousand tokens so the model can actually generate them pretty quickly so when you do your update the model is never too far off it's never too far off but now when you are moving towards this kind of problems where sometime takes hours like six hours to get the reward then your model is p so you have to be new infrastructure that supports this but also new algorithm so now everything we're doing internally we're way to build some infra that we actually anticipate is what we have in like a 6 month which is this extreme you know scenarios on the P game.
**Host**: what are you hiring for?
**Guillaume**: Yeah so we are having a lot of people in our sense team we are hiring uh in all our offices. So we have like our HQ is in France in Paris we have like a a small team in London like a team in PaloA as well. Recently we opened some offices uh in uh in Verso in Poland so one in Zurich um we serve some presence in New York as well and soon one in San Francisco. ... AI for science is one big thing.

</details>

### 前向部署工程师的角色

**Host**: 什么是好的前向部署工程师？

**Guillaume**: 这种人需要对技术非常熟悉。不一定需要深厚的研究背景，但必须擅长使用模型：知道如何进行微调，如何建立 RL 流程。大多数公司无法独立完成这些。我们需要喜欢解决复杂、具体问题的“应用科学家”。这需要耐心和创意，去创建合成数据，寻找边缘案例。这是一个良性循环：应用科学家在实际场景中发现模型的短板，反馈给科学团队，我们在下一代基础模型中将其修复。

<details>
<summary>Original English</summary>

**Host**: what makes a good for deployed engineer what do they need where do people fail
**Guillaume**: I think it's um um usually you need people that are very familiar with the tech not necessary uh with lot of research expertise but that are actually pretty good at using this model that can actually like you know that know how to do finetuning that know how to like start some aerial pipeline uh and it's u it's not easy it's something that most majority of companies would not be able to do this on their own so here I think we need people that that are you know that like to solve problems that I set about actually some complex very concrete problem. It's applied science basically and uh yeah so I think it's not too different I think from the skills you need in your research because essentially you are trying to find solutions to problems that in customers have not yet solved ... we incorporate it into the uh base model itself. So it's uh it it's just better out of the box.

</details>