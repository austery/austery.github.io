---
layout: post.njk
source: https://yage.ai/share/whisper-repetition-hallucination-20260526.html
speaker: yage.ai
title: |-
  Whisper
  的复读机模式：为什么一段沉默能让语音识别开始自言自语
date: '2026-05-26'
summary: 本文分析了OpenAI的Whisper模型在处理长音频停顿时产生复读或幻听现象的原因，指出训练数据中静音段配对的残留字幕是主因。文章对比了新一代模型（如Qwen-ASR和GPT-4o）在架构和训练上的改进，并提供了工程化缓解Whisper复读问题的实用方案。
area: tech-engineering
category: ai-ml
tags:
  - automatic-speech-recognition
  - whisper
  - hallucination
  - repetition-loop
  - voice-activity-detection
people: []
companies_orgs:
  - openai
products_models:
  - whisper
  - qwen-asr
  - gpt-4o
media_books: []
draft: true
status: evergreen
---

你把一段音频扔给
Whisper，前几秒还算正常，接着遇到了一个比较长的停顿。然后事情开始不对劲了——第一遍输出的句子，Whisper
又原样输出了一遍，然后是第三遍、第四遍，像个坏了的光盘机一样原地打转。运气不好的时候还能听到
“Thanks for watching and Electric Unicorn”、“please leave a like and
subscribe to the channel” 这种没有在任何一秒音频里出现过的东西。

我在过去几年里用了大量 Whisper，几乎每个版本都见过这个行为。从 tiny
到 large-v3，从英文到中文，它都会在某些时刻突然开始复读。问题是这到底是
Whisper 独有的坑还是语音识别模型的通病？新一代的 Qwen-ASR 和 GPT-4o
的实时语音好像就没这个问题——虽然 GPT-4o
在完全没人的时候偶尔也会编点东西，但至少不会把”今天天气不错”重复输出四十几遍。

## 出故障的窗口

要理解 Whisper 为什么变成复读机，得先知道它怎么处理长音频。Whisper
的窗口只有 30 秒。如果音频超过了 30 秒，它会把音频切成一个个 30
秒的块，逐块转录，然后用一个巧妙的滑动窗口机制把它们拼起来。拼的时候，上一个窗口的转录结果会作为”上文”喂给下一个窗口（具体来说是一个
<|startofprev|> 特殊 token
后面接上之前转出的文本）。

这个设计本身是对的——前面说了什么话给后面提供上下文，正常的人类语言也有这个性质。但问题出在另一个设计缺陷上：Whisper
没有 VAD（Voice Activity
Detection，语音活动检测）。它不会判断”这一段是沉默，不要转”，它只会对每一帧音频都产生输出。

当沉默来了的时候，编码器给出的音频 embedding
全是接近零的噪声向量。模型只在语音上训练过，它不知道”没有语音”长什么样。但它必须输出东西，因为它没有说”这段是空”的机制。于是解码器落回到自己最熟悉的东西：语言模型的先验，也就是刚刚看过的文本。上一句刚转出来”会议将在三点开始”，decoder
面对零向量时想：“这应该像上一句”，于是再输出一次”会议将在三点开始”。而这句话又变成了下一个
30 秒窗口的”上文”，下一窗口再复制一次——一旦开始，就停不下来了。

Whisper 的原始论文（Radford et al., 2022）第 4.5
节里本身就提到了这个问题，说 greedy decoding
在长音频转录时容易陷入重复循环，建议用 beam search + 5 beams 并且从
temperature 0
开始逐步增加。但很多开源实现和本地部署的默认参数并没有跟上论文的建议。

## 训练数据里住着的字幕组广告

当沉默足够长的时候，复读会演变成另一种更诡异的形态：Whisper
开始吐出完全不存在于音频里的内容。一个真实的例子——在一段完全没有说话的音频上，Whisper
自信地输出：“This is Ritesh Srinivasan and welcome to my channel. In
this video, let’s look at WhisperJAX… I hope you enjoyed the video. If
you did, please leave a like and subscribe to the channel.”
后面还接上了一句 “For more information visit www.FEMA.gov”。另一个来自
Cornell 学术论文的案例更简洁：“Thanks for watching and Electric
Unicorn”——音频里说的是 Cinderella 的童话故事，这句话凭空冒了出来。

这些句子确实有一个共同来源：字幕。OpenAI 在 Whisper
论文里说的是用 68
万小时的”弱监督”音频数据训练，手动标注的只占很小的比例（有几万小时）。弱监督的意思是：音频
+
网上的文本配对，不要求人工校验。那么互联网上音频和文本天然配对的场景是哪里？YouTube
的字幕和自动生成字幕、播客的逐字稿、各种视频平台的 CC（Closed
Caption）。

问题就在这里。很多视频在结尾——没有语音、只有画面和滚动字幕的那段——字幕文件里不是空的。它们会写上”感谢观看”、频道主的订阅呼吁、赞助商信息，或者字幕翻译组的署名。在训练样本里，这些文本对应的音频全是沉默（或者背景音乐）。于是
Whisper
学到了一条规则：当听到长时间没人的音频时，输出你记忆里和这种音频配对过的文本。有
OpenAI 论坛的用户报告：“most of the hallucination text I did get was
things like credits to movies subtitles sites”，直接印证了这个猜测。

一篇 2025 年的学术论文（arXiv:2501.11378）提供了更精确的统计：当
Whisper 在非语音音频上产生幻觉时，出现频率最高的输出依次是 “thank
you”（24.76%）、“thanks for watching”（10.32%）、“thank you for
watching”（2.58%）。这组数字几乎就是 YouTube
视频结尾字幕的按频率排序。

Cornell 的研究团队（Koenecke et al., 2024）在 AphasiaBank
数据集上更系统地验证了这个模式。他们发现在 1%
的转录中出现了完整的幻听句子，并且把内容分成了三类：暴力语言（如没有出现过的谋杀描述）、虚假关联（如虚构的患者药物清单）、虚假权威（如伪造的
YouTube 频道口吻和网站链接）。更有意思的是，在用
Google、Microsoft、Amazon、AssemblyAI、RevAI 的 ASR
服务做对照组时，这些幻听完全没有出现。这意味着它不是语音识别普遍面临的困难，而是
Whisper 训练流程的特有产物。

## 新一代模型交了什么卷？

Qwen-ASR 和 GPT-4o 在这个问题上走了两条不同的路，但都避开了 Whisper
的坑。

Qwen-ASR（基于 Qwen3-Omni
底座）的做法比较直接。第一，训练数据更干净。Qwen3-ASR
的技术报告里写了这是”tens of millions of hours of multimodal speech
data”，训练过程中明确做了 silence 和 non-speech audio 的过滤——不是靠外部
VAD 后处理，而是模型本身就能区分语音和非语音。第二，它的管道内置了 VAD
作为正式环节，不是事后补救。第三，它支持 <|nospeech|>
类型的 token，模型可以直接输出”这段没东西”，不需要强编文本。

GPT-4o
走的是另一条路。它是端到端的音频理解模型，不是”音频到文本”的转写流水线。GPT-4o
的语音模式不是”把音频转成文字再送给语言模型”，而是直接处理音频
token，把它作为原生输入模态。这意味着它没有 Whisper
那种”先转写成文本再用上一个文本做上下文”的脆弱的级联结构。GPT-4o 能区分
silence 和 speech，并且在 Dynamic-SUPERB
基准测试中证明它对”这个音频有没有人声”的判断能力远优于 Whisper
级联的管道。

但这不是说 GPT-4o
完全免疫。我在实验里观察到，当给它一段完全静音的音频并要求它转写时，它有时候会含糊地编一点东西——频率比
Whisper
低得多，并且不会无限循环。原因可能是同一个：任何生成模型，在没有输入信息的时候，都会退回到训练数据的分布。只是
GPT-4o
的对齐训练给它加了一个更强的”不确定就说不知道”的限制，使得它不会像
Whisper 那样纵容自己进入瀑布式的复读循环。

## 你眼前能用上的办法

如果 Whisper
是你跑不掉的依赖——很多场景下确实如此，因为它快、开源且生态成熟——有几个手段可以大幅降低复读出现的频率。

第一层是预处理，也就是 VAD。在音频扔给 Whisper 之前，先用 Silero VAD
或者 webrtcvad
切掉沉默段，只把有语音的部分送进去。这个方法的命中率很高，绝大多数复读都是由长时间沉默触发的，切掉就不触发了。

代价是 VAD 的灵敏度不一定能匹配
Whisper。有些音频段虽然在说话，但环境噪声很大或者人声特别轻，VAD
可能判断成沉默然后扔掉。但这些片段 Whisper
原本是有能力转出来的——只是没人声的信噪比太低的时候，F1
的阈值不好调。所以你需要在”少复读”和”多漏字”之间做一个取舍。它更像是一个工程经验参数，没有一刀切的设定。

第二层是推理参数。从 temperature 0 开始，加上 beam search（5 beams
是比较稳妥的选择），再启压缩率阈值和 logprob
阈值。这两个阈值是检测复读最直接的信号——复读导致的输出长度明显异常，token
的平均概率也通常偏低。一旦触发，就重新提交这个音频段（Whisper
的幻听是非确定性的，同一段音频跑两次大概率不一样）。

第三层是事后清洗。用正则抓连续重复的短语或句子，检测到后删除或标记。这也是目前很多依赖
Whisper 的产品实际在用的方案。

如果你对中文 ASR 的要求比较高，换用 Qwen3-ASR 或者 Fun-ASR
的效果立竿见影。Qwen3-ASR 在中文语音上的 WER 已经明显低于 Whisper
large-v3，且沉默误转的问题基本不存在。

最后，Whisper
的复读问题本身是个很好的教学案例。它本质上是”模型没有给空白预留编码”这个通用陷阱的一个实例——语言模型会在不敢说不知道的时候编答案，Diffusion
模型会在输入噪声过大时回到训练集的平均人脸，都是同一类问题。解法也不是什么神秘的东西：训练的时候让模型见过空白样本并学会输出”空”这个
token，推理的时候也别让它对没意义的输入强行产生输出。只是说到和做到之间，隔着你用于训练的那几十万小时音频、那些在视频结尾残留的字幕广告、以及无数次”谢谢观看”。