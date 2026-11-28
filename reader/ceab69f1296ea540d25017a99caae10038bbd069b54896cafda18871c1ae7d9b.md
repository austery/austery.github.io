---
layout: post.njk
source: https://yage.ai/share/sglang-omni-llm-inference-20260530.html
speaker: yage.ai
title: |-
  LLM 推理是怎么跑的：跟着 SGLang Omni
  团队的设计思路走一遍
date: '2026-05-30'
summary: SGLang Omni展示了顶级推理系统团队在设计时的完整决策链路。文章通过对语音大模型（Omni模型）的计算特性分析，揭示了多阶段推理（Multi-stage decode）中各环节计算瓶颈和依赖关系的差异。作者强调计算特性是系统设计的核心，主张通过调度解耦、分层通信和动态显存管理等架构选择，解决异构stage间的资源竞争与同步开销，为理解推理系统架构设计提供了范本。
area: tech-engineering
category: ai-ml
tags:
  - llm-inference
  - sglang-omni
  - multi-stage-decode
  - compute-bound
  - memory-bound
people:
  - zhao-chenyang
companies_orgs:
  - sglang-community
products_models:
  - sglang-omni
  - qwen3-omni
  - fishaudio-s2-pro
  - ming-omni
media_books: []
draft: true
status: evergreen
---

SGLang 社区最近发布的 SGLang Omni 技术文章（知乎，GitHub），是一个很少见的东西——它把一个顶级推理系统团队的完整决策链路摊在了明面上：从问题定义、到计算特性分析、到系统设计，每一步的前提条件、被否决的替代路径、选择它的理由，原文都写了。

大多数系统团队的公开输出是架构文档和 benchmark
数字，很少把决策过程公开。这篇文章的作者赵晨阳是 SGLang 社区的 RL
Lead，今年 2 月底从 RL 组转到 Omni
组。他自己坦言不来自系统背景——大学时被动态规划和计算机系统导论折磨到差点放弃
CS。恰好是这种背景让他的文章对非系统背景的读者友好：他也在学，所以每一个判断都被仔细解释了原因。

这篇文章像一个团队内部 design doc
公开了。如果你对推理系统感兴趣，它是一个很好的学习入口——不是因为里面有多少高深的技术，而是因为它展示了一个优秀团队分析问题、做设计选择的完整过程。

下面是沿着原文脉络梳理的内容，按读者兴趣分了三个层次。如果你只是对
LLM 推理的基本运行方式感到好奇，看完第一部分就够了——解释了自回归
decode、prefill 和 decode 的区别、compute-bound 和 memory-bound
是什么意思、调度器和 KV cache
在做什么。这些概念是理解任何推理系统的基础。如果你对多模态模型（尤其是语音输入输出）的工程挑战感兴趣，第二部分讲了语音为什么不能像文字那样直接喂给
LLM、codec token 是怎么压缩出来的、以及 Thinker-Talker
架构为什么天然是两条 decode loop。如果你更关心底层 infra
的系统设计，第三部分和第四部分是重点——从 multi-stage
带来的三个计算特性问题（异构调度、依赖分化、显存竞争）出发，看 SGLang
Omni 团队是怎么一步步做架构选择的。

## 先理解一件事：标准 LLM
推理是怎么跑的

SGLang Omni 要解决的问题，本质上是对标准 LLM
推理系统的一次重新设计。所以要理解它做了什么，得先知道原来的方案长什么样。

### 模型生成文字，是一次一个 token
的

一个大语言模型收到用户输入，不是一次性输出整段文字。它是一个 token
一个 token 地生成——每生成一个
token（一个词、一个标点、或者一个字的一部分），就把它拼回输入里，作为下一步的上下文，再生成下一个。直到某个特殊的”结束”token
被生成出来，整个过程才停止。这个过程叫自回归 decode。

工程上，这个过程被拆成两个阶段。

第一个阶段叫 prefill。用户输入的 prompt 里所有的 token
被一次性喂给模型。模型逐层做 attention——每个 token 去”看”它之前的每一个
token，计算它们在语义上怎么互相关联——然后把这些计算结果存成 KV
cache（Key-Value cache）。KV cache 是中间结果缓存：prefill
阶段算出来的注意力信息全保存在里面，这样后面 decode
时每一步不用把整个历史重新算一遍，只需要用新生成的 token 去和这个 cache
做一次查询就行。Prefill
是一次性的计算，输入有多长就算多大一块矩阵乘法，GPU
的计算单元基本被填满——这个阶段是 compute-bound，瓶颈在 GPU 的算力。

第二个阶段叫 decode。prefill 跑完之后，模型已经有了 prompt 的 KV
cache，开始一个 token 一个 token 地生成。每生成一个新
token，就把它和已存的 KV cache 做一次 attention 计算，得出下一个
token。重点是：每一步只处理一个新 token，矩阵乘法非常小，GPU
的算力大量闲置。真正的瓶颈不在计算上，在读取上——那坨 KV cache
越来越长，每一步都要从显存的各个位置把它读进计算单元。这个阶段是
memory-bound，瓶颈在显存的带宽。

为什么这个区分重要？因为优化方向完全不同。Compute-bound 的 prefill
阶段要把 batch size 做大、prompt 切块并行——让 GPU
一直有事做。Memory-bound 的 decode 阶段要把 KV cache
存得更紧凑、读得更快——压缩访存模式，而不是压缩计算量。

### 一台 GPU 要同时服务很多用户

一个推理服务不是一次只处理一个人的请求的。几十上百个用户同时发过来，GPU
怎么分算力？

解决方案叫 continuous batching。传统 batching
是等一批请求全部处理完再接下一批——但不同请求的输出长度不一样，有的三句话就完了有的要写三千字，先完的得等后完的。Continuous
batching 是每步 decode 都把正在跑的所有请求混在一起——谁的 token
生成了就加入这轮的 forward，谁生成了结束 token 就退出。这样 GPU 每轮
forward 处理的 token 总数变多，算力利用率上去了。

但 KV cache 的管理就变复杂了。每个请求有自己的 KV cache，且随着
decode
推进不断增长。如果一开始就给每个请求按最长可能长度预留一大块连续显存，绝大部分空间会空着但被占住了。解决办法叫
paged KV cache——把显存切成固定大小的
page，哪个请求需要新空间就分配一个新
page，结束了的回收。谁来决定哪个请求分配多少 page、哪些 page
留在显存里、哪些暂时换出去？这就是调度器（Scheduler）的职责。

### SGLang 主仓库已经有的能力

SGLang 的主仓库（SGLang main）为 LLM
推理积累了一系列被验证过的优化技术。Prefill/decode disaggregation 是把
prefill 和 decode 分到不同的 GPU 上跑，各自调度不互相阻塞。Chunked
prefill 是把超长 prompt 的 prefill 切成小块和 decode
交替执行——防止一个超长输入把其他人的 decode 全卡住。RadixAttention
是识别不同请求之间共享的 prompt 前缀，共享 KV cache。CUDA Graph 是把
decode 循环中重复的 kernel 调用序列录制成图，后续回放，消除每次启动
kernel 的额外开销。

所有这些优化都建立在一个共同的假设上：每个请求的计算过程是同构的——都是
prefill 然后逐 token decode，仅此而已。这个假设在 LLM 时代成立，因为 LLM
只处理文本。但到了 Omni 模型，事情变了。

## speech 输出把这件事搞复杂了

### 语音不是文字——它是一段波形

文本是人类发明的最经济的信息编码方式。一段话写成文字，1 秒讲 3-5
个字，以 token 计可能就 3-10 个离散符号。每个 token
来自一个固定词表——第几号 token 对应哪个字，界限清清楚楚。

语音是另一回事。它是连续波形，1 秒就有 16,000 到 48,000
个采样点——每个采样点是一个浮点数，代表那个瞬间声波的振幅。1 秒语音 =
至少 16,000 个数字。如果让 Transformer 直接处理原始波形，10 秒对话接近
50 万个标量步，远超大多数 LLM 的上下文窗口。

所以语音处理的第一步永远是压缩。

### 语音怎么被压成 token

压缩分两步。

第一步，把高频波形变成低频帧序列。原始波形每秒几万个采样点，经过
encoder 后变成每秒十几帧（比如 12.5 帧/秒），每帧是一个 128
维的连续向量。这一步在时间轴上压缩了上千倍，但输出的仍然是连续值——不能在一个固定词表里查到”第几号”。

文本 token 之所以能走”有限词表 + 交叉熵 + 采样”这条标准 LLM
管线，是因为每个 token
是离散的，对应词表里恰好一个条目。所以还需要第二步——把连续向量”离散化”。

这个离散化的过程叫残差向量量化。简单说，把每个连续帧向量和一个离散码本里的向量做匹配，找到最接近的编号。一帧匹配一次不够精确，就匹配多层——第一层找一个近似值，剩下的误差给第二层补，第二层的误差给第三层补。比如每帧量化成
8 层，每层一个编号。于是 1 秒语音 = 12.5 帧 × 8 层 = 100 个离散
token。这些 token 叫 codec token——“codec”就是”编码-解码”的缩写。

压缩前后的对比：1 秒语音，从 48,000 个采样点变成了 100 个离散
token。将近 500 倍的压缩。

这个”波形→连续帧→离散 token”的过程叫 audio encoding。反过来，把 codec
token
变回波形——vocoder——也有一套对应的流程。这两步在不同模型之间差异不大，主要是
codec 选型的区别（有的 codec 用 8 层，有的用 4 层；有的每帧 token
多，有的少）。

### 从听懂到说出——四步流水线

有了压缩和离散化的基础，一个”能听懂语音、能用语音回复”的 Omni
模型，整个过程天然可以拆成四步。

第一步，Audio Encoding：把用户说的语音波形压缩成离散 codec
token。这一步之后，语音信息变成了能喂给 Transformer 的 token
序列——和文本 token 混在一起，模型就可以同时处理了。

第二步，Understanding（Thinker）：一个 LLM 或多模态 LLM 读取这些
token（可能还有图片、视频），理解用户意图，生成文本回复。这和标准 chat
模型做 prefill + decode 没有本质区别——输入序列里混入了 audio
token，但计算模式不变。

第三步，Speech
Synthesis（Talker）：把文本回复和声学特征（语气、音色、韵律——这些不是文字里能编码的信息）转成输出语音的
codec token。Thinker
只生成了文字——“今天天气不错”——但这句话以什么样的音高、语速、情感说出来，需要
Talker 根据 Thinker 在处理音频输入时提取的 hidden states 来决定。

第四步，Audio Decoding（Vocoder）：把 codec token
解码回可播放的波形。

Encoding 和 Vocoder 在不同模型之间相对稳定。真正让不同 Omni
模型产生架构分叉的，是中间两步——Thinker 和 Talker 怎么耦合。

### 回到决策：为什么
Thinker 和 Talker 是两条 decode loop

现在可以把最关键的那个概念跳转讲清楚了。

前面四步流水线里，Thinker 和 Talker 都在”生成
token”，但那只是表面相似——它们生成的 token
完全不同种类，计算模式也完全不同。

Thinker 生成的是文本 token。文本 token 是稀疏的、低频的——1 秒大概 3-5
个 token，一个完整短句可能就 20-50 个 token。每个 token
从几万级别的词表里选一个编号。计算模式和标准 LLM 一模一样：prefill 时
compute-bound，decode 时 memory-bound，瓶颈在 KV cache 的读写。

Talker 生成的是 codec token。codec token 是密集的、高频的——1 秒要生成
12.5 帧 × 8 层 = 100 个 token。你可以把它想成音频的”像素”：每个 codec
token
不直接对应一个”字”或”词”的概念，而是对应声音在某个瞬间的声学状态。说出”今天天气不错”这句话，文本端
Thinker 只需要 6-8 个 token，语音端 Talker 可能要生成 200-300 个
token。

而且 Talker 不是独立工作的。Talker 每生成一个时间步的第 0 个 codec
token 后，一个叫 MTP 的模块会立刻介入——以这个第 0 个 token
为条件，并行补全当前时间步的剩余 codec token（第 1 层到第 7
层），再把补全结果写回 Talker，作为下一步的输入。Talker
的下一步严格依赖这次写回——这是一个步间紧反馈回路。

所以 Thinker 和 Talker
虽然在概念上是同一条流水线的两个环节，但在计算上它们是两个不同模型、跑着两条独立的
decode loop、各自有自己的权重和 KV
cache、各自有自己的生成节奏。把它们塞进同一个调度循环是行不通的——这个问题引出了后面全部的设计。

### 这个问题的实质：分类轴的选择

了解了 Thinker-Talker 的计算差异之后，再回头看 SGLang Omni
团队做的第一个核心决策就很自然了。

Omni 模型的定义本来就不统一。有些团队认为只要支持语音输入的 VLM 就算
Omni，有些要求同时支持语音输出，有些甚至做到了全模态输出（文本+语音+图片）。如果按输入输出模态来分类，边界模糊。

原文团队的判断是：不用模态分类，用 decode 是否 multi-stage
分类。这个判断的质量，正是我们一开始说的”顶级团队怎么做决策”的一个具体案例——好的分类轴不是跟着表面特征走，而是找到那个能揭示计算本质的维度。

按这个轴一切，模型很自然分成两边。一边是 single-stage decode——MiMo
Omni、Nemotron Omni 等，decode 过程就是一遍 prefill 然后逐 token
decode，和标准 LLM 一样。SGLang main 已经为这些模型做到极致了。

另一边是 multi-stage decode——Qwen3-Omni、FishAudio S2 Pro（纯 TTS 的
Dual-AR）、Ming Omni（全模态输出）等。它们的共同点是：decode
被拆成了多个异构 stage，各自有不同的计算特性。这些是 SGLang Omni
的目标。

这个分类轴的 engineering taste 在哪？第一，它让系统边界可预测——stage
数量直接决定计算拓扑，而计算拓扑是系统设计的直接输入。第二，它避免重复建设——single-stage
交给 SGLang main，SGLang Omni 只做
multi-stage。第三，它有概念上的简洁性——一个判断把整个模型版图分得清清楚楚。好的工程分类往往是二分法，边界上只有一个维度在变。

## multi-stage
带来了三个系统级问题

标准 LLM 推理是一个 Scheduler、一套 KV cache 池、一个同构的 decode
循环——所有请求的计算模式一样。Multi-stage decode 是两个甚至多个异构
decode loop 并行运行——各自权重、各自 KV
cache、彼此之间有实时数据依赖。

### 问题一：不同 stage
的计算瓶颈完全不同

要理解这个问题，需要先回顾一下前面讲的 compute-bound 和 memory-bound
的区别。这里用一个比方来帮助记忆。

把 GPU
想象成一条流水线。工位上有一个工人，他面前有两件事：一是操作机器做计算（矩阵乘法、attention），二是从仓库里取原材料（读
KV cache）。Prefill
阶段的工作是”计算量大、取料少”——工人大部分时间在操作机器，机器满负荷运转，这就是
compute-bound。Decode
阶段的工作是”计算量小、取料多”——工人大部分时间在往仓库跑、取东西、回来，机器经常空转，这就是
memory-bound。

一个优秀的调度器就像工头，它根据活的类型来分配机器时间——大计算量的活（prefill）批处理打满机器，取料多的活（decode）优化仓库布局减少跑路时间。标准
LLM
下这套管理方式运转得很好，因为所有的活要么是”计算量大型”要么是”取料频繁型”——两种类型，但规律清晰。

现在来看 multi-stage 场景下，每个 stage 是什么类型的活。

Thinker 不用多说，和前面完全一样——prefill
是”计算量大型”（compute-bound），decode
是”取料频繁型”（memory-bound）。SGLang main
已有的所有优化都可以直接复用。

Talker + MTP 是一种标准 LLM 里没见过的类型。Talker
虽然也在做自回归，但每一步不读长序列 KV cache——它的输入只是当前步
Thinker 给的”这一秒应该生成什么文字”和 MTP
上一步反馈回来的”刚才产出的语音特征”。attention
极轻，往仓库跑的次数和取料量都很少——它不是 memory-bound。MTP
做的事像一个小 prefill，但每次只处理几个 codec
token，计算量太小——机器远远没跑满，它不是 compute-bound。

那它瓶颈在哪？原文给了一个非常精确的定性：“kernel launch
overhead 和同步开销反而成了主导因素。”

这个现象在 LLM 推理里几乎不存在。为什么？因为 LLM 每步 decode
的矩阵乘法足够大——比如一个 7B 模型每步 decode 算一次 attention，GEMM
的计算时间可能是几百微秒，而启动一次 GPU kernel 的 overhead
大概十几到几十微秒，占比很小。但 Talker 每步的计算本身就很小——整个
forward 可能才几十微秒——这时 kernel launch
本身就成了大头。就好比一个工人在做一个只需要 5
秒的小零件，但每次去开机器、关机器、检查流程就要花 3 秒——工序的 overhead
比干活本身还长。

这个洞察并不孤立。GLM-5.1
的高速版 API（400 tokens/s）背后，智谱的 TileRT
推理引擎发现了完全相同的瓶颈。TileRT 面对的场景是实时交互中 batch size=1
的 LLM decode——每次只生成一个 token，每步计算量骤降，kernel launch
overhead 的占比同样激增。表面上两个团队做的是完全不同的事：SGLang Omni
在多模态语音场景，TileRT 在文本 LLM
场景。但推到根上，结论是同一个——当单步计算轻到一定程度，瓶颈从”算力不够”或”带宽不够”变成”kernel
之间在空转”。
两个团队各自独立地走到了这个认识，而各自选择的解法也异曲同工：TileRT
在编译期把整个模型编排成一条连续流水线消除工位隔离，SGLang Omni 把
Talker 和 MTP 圈在同一个 forward 里用分段 CUDA Graph 抹平间隙。

还有 Vocoder。它不是 Transformer，没有 KV cache。它是
ConvNet，是”计算量大型”（compute-bound）——但幸运的是，它和 LLM
decode（“取料频繁型”）的瓶颈资源不同，一个要算力一个要带宽，可以在同一张
GPU 上通过 CUDA MPS 并行跑、互不干扰。

这三种类型（compute-bound、memory-bound、kernel-launch-bound）如果硬塞进同一个
Scheduler 管，会互相伤害。Thinker 的吞吐——一次处理多少个请求——会被
Talker 频繁的细粒度操作打断。Talker
的延迟——用户听到第一个音节要等多久——会被 Thinker 大 batch prefill 时占满
GPU
导致排队。就像一个工厂里把造航母的、拧螺丝的、给零件抛光的全放在一条流水线上，快的人等慢的，慢的被快的打断。

原文的结论很简单：调度解耦不是可选项，是必然。
Thinker 和 Talker 只能由两个独立的调度器异步运行。

这个问题背后，也恰好体现了这个团队的分析风格。他们没有笼统地说”multi-stage
更复杂”，而是把每一个 stage
单独拿出来，分析它的计算类型是什么、瓶颈在哪个资源、和其他 stage
的差异在哪。局部分析做透了，系统级问题就自己出来了。

### 问题二：两个
decode loop 之间的连接方式完全不同

这个问题的分析也延续了同样的”局部分析”方式——先看每一对 stage
之间的依赖长什么样，再看这种依赖对通信提了什么要求。

第一种依赖：Thinker 和 Talker 之间是异步解耦的。Thinker 提前生成文本
token 和声学 hidden state，放进一个共享 buffer，Talker
按自己的节奏从这个 buffer 里取。两个模型维护独立的 decode
loop，不需要每一步都同步——Thinker 比 Talker
快几拍也没关系。这种模式下，通信的核心需求是低开销的流式缓冲，允许
slack。

第二种依赖：Talker 和 MTP 之间是同步紧耦合的。Talker 每产出一个第 0
个 codec token，MTP 必须立刻补全并写回——Talker
的下一步严格依赖这次写回。这种模式下，每一步延迟都至关重要。如果 Talker
生成 token 后还要等一个跨进程信号触发 MTP、MTP
算完再发信号回来，额外开销会累积到不可接受。

同一个系统里同时存在两种通信需求，一个允许
slack，一个要求极限低延迟。这是第二个问题。

### 问题三：多个模型同时抢一块
GPU 的显存

标准 LLM
推理的显存分配直观得像个两段式：模型权重占固定的一块，剩下的全部给 KV
cache。想调比例就改一个参数（SGLang 里叫 mem_fraction_static）。

Multi-stage 场景下这个简单逻辑直接失效了。Thinker
的权重在显存里（Qwen3-Omni 的 Thinker 是 30B-A3B MoE），Talker
的权重也在显存里。Thinker 要自己的 KV cache pool，Talker
也要自己的。Vision encoder 和 audio encoder
处理长视频时有巨大的临时激活峰值——原文指出一分钟视频轻松超过 30GB，而
encoder 权重本身只有约 2.5GB。Talker 和 MTP 之间还需要 feedback
buffer。

问题不只是”多个人分一张饼”——如果只是总量不够，加显存就行。更深层的问题是这些
consumer 的加载顺序不同（有的先初始化有的后初始化），offload
策略不同（有的权重可以暂时换出有的不行），“剩余可用显存”这个数字每一步都在变。原来一维的显存分配逻辑直接失效了——它假设只有一个主
consumer。

## SGLang Omni
的回应：每一个设计选择都在回答一个问题

三个问题就是三份需求说明。下面看原文团队针对每个问题做了什么选择，以及选择的理由是什么。

### 调度解耦：统一接口，独立实现

所有 stage 对外遵循同一个 inbox/outbox 协议，但内部实现各自不同。

Thinker 跑在 OmniScheduler 上，直接复用 SGLang main
的全部调度能力——continuous batching、混合 prefill/decode 调度、KV cache
管理、tree cache、overlap scheduling——同时去掉 tokenizer、grammar 等
Omni 场景暂时不需要的模块。Talker 也跑在 OmniScheduler 上，和 Thinker
各自维护独立的调度循环，通过 relay
异步解耦。不需要调度的阶段（预处理、encoder）用
SimpleScheduler——几行代码的 get → forward → put。Vocoder 用
Code2WavScheduler。

这里体现了团队判断力的一个关键选择：Talker 和 MTP
被合在同一个 Stage 里。

为什么？因为 Talker 和 MTP 之间的依赖是同步且每步极轻的。拆成两个
Stage，中间走 relay 和 ZMQ
信号，“每一步的延迟会膨胀到不可接受”——这是原文的原话。

所以 MTP 的补全和 feedback 写回全部封装在 FeedbackARModelRunner
的一个 forward 调用里。对上层 Coordinator 来说，Talker + MTP
的一个时间步只是轻量的一步 decode——Coordinator 完全不知道 MTP 存在。

原文特意说明这种合并改变了什么、没改变什么。改变的只是 kernel
的编排顺序和 CUDA Graph 的边界。没改变的是 Talker 的 paged KV cache、MTP
的权重和多头补全逻辑——它们仍然是两个完整模型，只是共享同一个 forward
调用，紧反馈回路被圈在 Stage 内部，没有跨 scheduler 的开销。

这个选择背后的原则可以用一句话概括：Stage
边界不由模型模块的物理边界决定，而由依赖关系的松紧程度决定。
紧的地方合在一起省掉跨 stage
的通信延迟，松的地方拆开各自优化吞吐。这不是在按”什么看起来像一个模块”来划边界，而是在按”什么通信代价会伤害性能”来划边界——又是这个团队分析方式的一个体现。

### 分层通信：按需求类型分，不搞一刀切

问题二发现了两种依赖模式——一个异步、一个同步。SGLang Omni
的回应是不搞统一的通信层，而是分控制面和数据面。

控制面走 ZMQ，承载事件通知（“上游 chunk
写完了”“新请求到了”）。数据面走 relay，承载实际大 Tensor 传输——同机 GPU
用 shared memory 或 CUDA IPC 零拷贝，跨节点走 NCCL。

Thinker 和 Talker 的异步依赖同时用控制面和数据面：Thinker 写数据到
relay，发 DataReady 信号，Talker 收到后按自己的节奏从 relay
里消费。Talker 和 MTP 的同步依赖不走任何跨 stage 通信——全在同一个
ModelRunner 的一个 forward 调用里完成。

这个设计的品味在于不预设结构——通信分几层不由教条决定，而由需求本身决定。有多少种依赖模式，就匹配多少种通信路径。

### 跨 stage
显存预算：从单个全局比例到多方声明制

单 Scheduler 下的显存管理可以用一个全局参数表达。Multi-stage
下这个参数失效了。

SGLang Omni 的方案是改成多方预算制。每个 stage 在自己的配置里声明
total_gpu_memory_fraction——“我要占这张卡总显存的多少比例”。启动时按 GPU
汇总所有声明，总和超过 100% 直接拒绝；通过后每个 AR stage
在自己预算内尽可能多地分配 KV cache。

Encoder 的显存风险被原文单独拿出来讨论。权重只有约
2.5GB，但激活峰值轻松超过 30GB。SGLang Omni
对它的处理体现了一种一致性的追求：encoder 和其他 stage 一样，在
StageConfig 里声明 tp_size 和 GPU placement。TP 切分激活峰值不是为
encoder 单独做的——它是所有 stage
共享的机制。好东西不在”为特殊情况开了特殊路径”，而在”一个机制能解决一大类问题”。

### Coordinator：只管拓扑，不管实现

Coordinator 在最上层做三件事：新请求路由到 entry Stage、从 terminal
Stage 收集输出并合并、需要 abort 时广播到所有相关 stage。

它的设计原则也很简单——stage-implementation agnostic。不管每个 Stage
里跑什么模型、用什么调度器，它只知道 pipeline
的拓扑关系。这个”只管拓扑不管实现”的设计让 Coordinator
不会随着支持的模型类型增多而膨胀。

## 回头看：一个统一的视角

原文开头有一句话，放在这里重读有不一样的感受：“ML
系统研究者只有一个目标——研究给定计算过程的计算特性，为它设计高效、鲁棒的系统。”

这不仅仅是作者的个人信念，也是整篇文章的组织逻辑。计算特性是第一性的：它决定了覆盖范围（什么模型归
SGLang Omni、什么归 SGLang main）、决定了系统需求（从 stage
级别计算特性推出三个问题）、决定了设计选择（调度解耦、分层通信、显存预算），也决定了可扩展性——因为
Stage 抽象统一、Scheduler
接口统一、通信和显存是框架层的，新模型接入只需要声明计算特性、依赖关系和显存预算。

回到我们最初想从这篇文章里学到的东西：一个顶级推理系统团队怎么做决策。原文提供了四个层面的答案。问题定义——不跟风用模态分类，自己定义一个能揭示计算本质的轴。计算特性分析——把系统拆到
stage 层面，逐个分析每个 stage
的瓶颈和依赖特征，从局部分析推到系统级约束。设计选择——每一项选择都有明确的前提条件、有被否决的替代方案、有选择它的工程理由。系统性视角——所有选择指向同一个起点：计算特性是第一性的。

这些事说起来都不复杂，但每一步都在做选择、每一步都有判断。我们分析这篇文章，不是因为它介绍了什么高级技术，而是因为这些选择的来龙去脉被写在了明面上——对做工程的人来说，这就是最好的教材。