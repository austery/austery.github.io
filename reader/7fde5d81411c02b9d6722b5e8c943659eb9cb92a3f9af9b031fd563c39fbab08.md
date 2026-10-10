---
author: AI Engineer
date: '2026-06-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mFLlVpnGpds
speaker: AI Engineer
tags:
  - speaker-diarization
  - speech-to-text
  - audio-processing
title: 超越单纯转写：构建真正理解“对话”的语音 AI
summary: pyannote.ai 联合创始人 Hervé Bredin 深入解析了“说话人日记化”的核心挑战，并探讨了如何通过解决语音重叠和对齐难题，提取情绪、反向交流等深层声学信息，从而让下游大语言模型实现对对话的真正理解。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - pyannote.ai
  - OpenAI
  - Nvidia
  - Hugging Face
products_models:
  - Whisper
  - Parakeet
  - pyannote
media_books: []
status: evergreen
---
### 语音转录的局限与对话理解的深层维度

语音技术的发展已经取得了长足的进步，特别是自 OpenAI 开源 **Whisper**（Speech-to-Text: 将音频转换为词汇序列的技术）以来，高质量的免费语音转录变得触手可及。然而，仅仅回答“说了什么”是远远不够的。在会议记录、播客分析（如跨剧集追踪特定嘉宾）以及视频自动配音等场景中，“谁说了什么”同样至关重要。如果我们希望构建一个真正理解对话的 AI，系统必须向更底层的声学信息进行探索。

在真实的交流中，“何时说”以及“如何说”往往承载着与字面意思同等重要的信息。例如，精确的时间戳可以揭示对话中的打断行为，或是捕捉到细微的**反向交流**（Backchannels: 听者在对方讲话时发出的简短回应，如点头、说“嗯”或“对”）。如果系统遗漏了这些短促的附和声，下游的**大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）就会误判说话者的心理状态，甚至无法理解某方是在赞同还是在提出异议。此外，两次发言之间的停顿长短、咳嗽、笑声，以及讲话时的重音位置（例如，当孩子说“狗吃了蛋糕”时，重音的不同位置会彻底改变句子的侧重点和含义），都提供了至关重要的语境信息。将这些细粒度的声学特征结合真实的声学背景（如安静的房间或嘈杂的街道）输入给下游工具，才能使机器从单纯的“文字转录”走向真正的“对话理解”。

<details>
<summary>Original English Source</summary>

Good morning everyone. Thanks for being here to the voice and vision session. I'm Hervé Bredin, chief science officer and co-founder at pyannote.ai. I'm going to talk to you today about understanding conversations and what you can do on top of transcription.

I've been an academic researcher all my life until two years ago when I started this company. I worked on this topic called speaker diarization, which I'll introduce a bit later. Over the years I built an open source toolkit called pyannote which focuses on speaker diarization, and that became quite popular in particular since OpenAI released Whisper speech-to-text open source models. Whisper was some kind of revolution in terms of STT—the fact that it was free, that it was very good—but it didn't provide the actual names and tags of the speaker. So people naturally turned to pyannote to combine the two. (By the way, I happen to turn 45 in just one week, and we are almost at 10k stars on GitHub, so please give me a birthday gift by adding your star!)

Let's go to the core of the presentation. You all know what transcription or speech-to-text is. Basically, that's answering the question: "what was said" from the recording of a conversation. You get a sequence of words as output. That's what Whisper does, but without the actual names of the speaker, the transcripts are not really understandable. The next step is to attribute a speaker tag to each of the words. That answers the question: "who said what."

For some applications, that's enough—like for meeting note takers to make a summary and assign action points. But there are many cases where knowing who said what is as important as what was said. For instance, automatic video dubbing: you want the voices to be consistent across languages. Same for podcast intelligence, like tracking a speaker or finding the same guest across different episodes.

But knowing who said what is sometimes not enough to really understand how the conversation goes. Knowing "when" they said it brings even more information. Without precise timestamps, you can't detect that a speaker interrupted another. You can't really detect the small backchannels a speaker makes during the speech of another. If you miss it, you don't really understand that the listener is actually agreeing or nodding. Knowing exactly when this small word was pronounced is very important. Same goes for pauses in between two speech turns, which might convey additional information about my state of mind or the point I'm trying to make.

We can go a step further: knowing who said what, when, and "how" they said it. Are you laughing because I said something stupid, or was I actually funny? Maybe I'm coughing because something makes me uncomfortable and I'm hiding behind that. Stress, disfluency, prosody—stressing particular words in a sentence might completely change its meaning. If a child tells you "the dog ate the cake" versus "the *dog* ate the cake", the meaning is slightly different. Being able to have a voice AI actually understand this stress and these low-level details brings much more information to any downstream LLM or tools you use after transcription. 

Having a higher-level view of the conversation also opens up a new bunch of applications. All of this happens in an acoustic environment that gives you context—whether it's in a quiet room or if I'm in the street. This brings more context to the game so you can take a better decision about what's going on and why a person is saying what they're saying.

</details>

### 日记化系统的工程挑战与现实瓶颈

要实现精确的说话人归属，我们需要引入**说话人日记化**（Speaker Diarization: 回答“谁在什么时间说话”的技术）。在建立这种底层声学感知后，具体的系统处理流程主要分为几个阶段。首先是进行**语音活动检测**（Voice Activity Detection: 判断当前时间点是否有人说话），接着将这些连续的语音区域切分为更小的语音片段，寻找说话人切换点，并处理复杂的重叠语音和极短的发言。最终，系统需要为每个片段分配一个说话人标签。

然而，日记化是一个极具挑战性的技术难题，它不同于传统的机器学习分类任务。核心困难在于：系统无法预先知道对话中实际存在的说话人数量，也无法提前获得这些人的真实身份（即使拥有会议邀请名单，也无法预判是否有未邀请的人加入或两人共用一个麦克风）。模型输出的只是相对的“说话人1”、“说话人2”，这些标签具备排列不变性。此外，现实场景中充斥着复杂的变量，如两人同时开口的重叠语音、极短的附和声、不同说话人发言时长严重不均（Imbalance），以及多变的声学背景噪声。

业界通常使用**日记化错误率**（Diarization Error Rate / DER: 衡量系统在说话人混淆、漏报和误报方面综合误差的指标）来评估系统性能。在理想的电话语音测试集中，目前最好的系统能够达到 8% 的极低错误率；但是，如果场景切换到背景嘈杂的餐厅聚会，并使用远场麦克风进行收音，即便是最先进的系统，其错误率也会飙升至 41%。这意味着，距离完全解决复杂环境下的多说话人分离，我们仍有很长的路要走。这也正是开源社区（例如 **pyannote** 刚刚在其作者 45 岁生日之际突破了 GitHub 的 1 万颗星）和顶级 AI 模型提供商（如 **Hugging Face** 平台上最受欢迎的音频模型中，有多个专门针对该任务）持续投入该领域的根本原因。

<details>
<summary>Original English Source</summary>

This is basically what we are trying to work on at pyannote. But we started with a smaller problem called speaker diarization, and that's really what I want to talk about today. 

Speaker diarization is usually just as important as what was said. You can tell by going to the Hugging Face model repository and filtering the audio models by number of downloads. Among the top seven models, the first three are actually related to speaker identity and speaker diarization, and the others are STT. That shows speaker diarization is actually quite important in the community.

Going into a bit more detail, speaker diarization answers the question: "who speaks when." Starting from the recording of a conversation, the first step people usually do is Voice Activity Detection (VAD)—telling whether anyone is speaking at one time or not. Then you can segment those speech regions into smaller speech turns. This segmentation includes finding speaker change points and finding regions where people are actually interrupting each other or making some kind of backchannel (saying "hm" or "okay"). You don't want to miss these small speech turns because sometimes they convey the most important information of the conversation. If you miss a small "yes," you have no idea what the state of mind of the speaker is.

But that's not yet speaker diarization. Diarization goes all the way to assigning a speaker identity to each speech turn. We usually don't have any prior knowledge on the actual number of speakers in the conversation. If you are a meeting note taker, you might have the list of attendees, but that doesn't mean two people didn't join from the same channel, or an uninvited attendee joined. That makes the problem difficult because we don't know in advance the number of classes we're supposed to detect, contrary to classical machine learning problems. Also, we don't know the identity of the speaker. It outputs "speaker one," "speaker two," and they can be permutated and still be correct from the point of view of the evaluation metrics.

Even though the community has been working on this topic for a long time, it's still not solved. There are other reasons: we have to handle overlapping speech, take into account very short speech turns, handle imbalance between the speech time of multiple speakers, and deal with acoustic condition problems that any speech processing task has to deal with.

To show you how diarization systems are evaluated, you'll often stumble into the acronym DER, which stands for Diarization Error Rate. In my demo, comparing a community diarization pipeline to a manual reference, we see three kinds of mistakes: confusion (it got the speaker wrong), false alarms (it detects speech when there's actually no speech), and missed detections (often happening during overlapping speech when we only detect one of the two speakers). The DER is basically the sum of confusion, false alarms, and missed detections divided by the total duration of speech. 

I'm often asked how well state-of-the-art speaker diarization works today. It's a difficult question because it really depends on the use case. For conversation telephone speech, the best system goes down to an 8% Diarization Error Rate. But if you are in a restaurant with many friends and lots of background noise, even the best system reaches a 41% Diarization Error Rate. So it's far from being a solved problem, but we are working on that.

</details>

### 转写与日记化的对齐：突破重叠语音瓶颈

在分别获得了最佳的日记化输出和文本转写结果后，最直观的想法似乎是简单地将它们合并，把对应时间戳的词汇分配给相应的说话人。然而，这种简单的“对齐”（Reconciliation）在工程实践中往往会遇到巨大的阻碍。

核心瓶颈在于：绝大多数的语音识别模型都是基于单人清晰语音训练的。当它们被应用于充满重叠、打断和背景噪音的多人对话场景时，性能会呈现断崖式下跌。以目前表现优异的 **Nvidia Parakeet** 模型为例，在纯净的单人测试中它可以取得极低的 11.4% 词错误率，但一旦将其应用于使用远场麦克风录制的多人会议数据集（如 AMI 数据集），其错误率会立刻飙升至 26%。这种性能鸿沟导致 STT 模型在面对重叠语音时，往往只能捕捉到其中一个人的声音，或者干脆生成混乱的文本；与此同时，STT 生成的时间戳经常与日记化模型产生分歧，有些词被转写了却没有被检测为语音，有些被检测为语音的片段却没有被转写。

为了解决这一对齐难题，工程层面需要引入一种名为**排他性日记化**（Exclusive Diarization: 在重叠语音片段中，系统主动预判并优先选择最可能被 STT 模型转写的那个主要说话人）的启发式策略。通过在日记化阶段就预测 STT 模型的转写偏好，系统能够极大地简化后续的词汇分配过程。结合专门的编排引擎（Orchestration），即使在两个人激烈交谈、声音高度重叠的片段中，系统也能精准地将交叉的词汇拆解并分别归属给正确的发言者。最重要的是，这种架构设计具有极强的通用性，它不需要对底层的 STT 模型进行任何重新训练，可以直接适配企业内部微调过的各种专有转写引擎，从而为终端应用提供可靠的“带说话人标签”的转写文本。

<details>
<summary>Original English Source</summary>

Once you have speaker diarization and transcription, it shouldn't be that hard to actually find a speaker-attributed transcription, right? It's just a matter of assigning a word to a speaker. But actually, that's not that easy.

The first reason is that most speech-to-text models are actually trained on single-speaker data. As soon as you apply them on multi-speaker data with overlap, speaker change, and all kinds of mess, they fail miserably. For instance, if you look at the Open ASR leaderboard on Hugging Face, the Nvidia Parakeet model reports an 11.4% word error rate. But when we apply the very same model on the AMI dataset (meetings between 4-5 people using a distant microphone in the middle of the table), we get 26%. The difference is because on one side you have single-speaker speech, and on the other side you have multi-speaker and distant microphone speech. That's why it degrades a lot.

So when doing speaker-attributed transcription, it might go wrong because STT doesn't work great and doesn't generalize well to multi-speaker recordings, distant microphones, cross-talk, interruptions, or code-switching. But it also might be because of the actual reconciliation between diarization and STT timestamps. STT does not transcribe overlapping speech well, the timestamps often disagree between STT and diarization, and sometimes diarization will detect speech that the transcription will not transcribe (and the other way around).

In our demo with Nvidia's Parakeet model and our precision diarization model, the question is how to assign a speaker to each word. Sometimes the timestamps are a bit shifted. Or there's a word in between two speech turns, and which one do you assign it to? According to diarization there are two speakers speaking, but only one word from the transcription. 

That's why at pyannote we came up with a new STT orchestration system that takes care of the reconciliation between the two. The trick to actually solve this problem of reconciliation is partly available in our open source community model, which we call exclusive diarization. Basically, what we do is we find a way when there is overlap to actually select the most likely of the two speakers that will be transcribed by the STT model. That simplifies the reconciliation between the two. This is not part of the model training—we really plan to support any kind of STT without having to change or retrain the STT model itself. It's supposed to work with any STT, even fine-tuned ones you might have internally for your particular use case. It correctly manages to interleave the overlapping words from the speakers. 

This demo and tools are available in the pyannote tutorials GitHub repo, where you can play with the pyannote open source toolkit, pyannote.metrics for evaluation, and our interactive visualization widgets. Thank you very much!

</details>