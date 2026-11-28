---
author: AI Engineer
date: '2026-05-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=BKWpYIWvAo4
speaker: AI Engineer
tags:
  - edge-ai
  - model-quantization
  - on-device-inference
  - agentic-workflow
  - fine-tuning
title: 边缘侧的微型大模型：从 Tiny LLMs 到智能体技能的演进
summary: Google 边缘 AI 技术负责人 Cormac Brick 深入解析了在移动设备和 IoT 终端部署大模型的最新进展。演讲涵盖了微型 LLM（小于 1B 参数）的微调工作流、LiteRT-LM 推理引擎的跨平台架构，以及基于 Gemma 4 模型的智能体技能（Agent Skills）系统，展示了如何通过离线、低延迟的方式在边缘端实现复杂的 AI 交互。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Cormac Brick
companies_orgs:
  - Google
  - Intel
  - Qualcomm
  - Apple
products_models:
  - Gemma-4
  - LiteRT-LM
  - MediaPipe
  - TensorFlow-Lite
media_books: []
status: evergreen
---
### 边缘计算的十年征程与核心优势

Cormac Brick 分享了他在边缘 AI 领域十年的从业经历，从 2016 年在 Raspberry Pi 上运行 GoogleNet，到领导 Intel NPU 的架构设计，再到目前担任 Google Edge AI 的技术负责人。**边缘 AI**（Edge AI: 在终端设备而非云端运行 AI 模型）的核心优势在于四个维度：**低延迟**（Latency: 满足实时翻译等交互需求）、**隐私保护**（Privacy: 数据不出本地，实现端到端加密）、**离线可用性**（Offline Use）以及**成本节约**（Cost Savings: 减少云端推理代币的消耗）。

<details>
<summary>Original English Source</summary>

Hey, my name is uh Cormbrick. I work um on Google AI edge, which is a way of kind of bringing models to the edge. This is something we use internally for our own products. It's also something we make available as open source products. As part of this, we also work really, really close with the Gemma team because they publish a lot of models that are targeted to edge devices as well. Um, yeah, quick bit of background on me. Um, yeah, I've been focusing on Edgi for the last like, wow, like maybe 10 years at this point. Um, so started off in 2016 with like running a uh Google Net on a USB key hardware accelerator plugged into a Raspberry Pi at like Nurips's 2016. So yeah, it's been a lot of fun over the years. I then joined Intel, worked on led the architecture for the NPU that goes into all of their laptops these days. Three years ago, I moved to Google to work as tech lead on Edge AI here. Uh yeah, and that's been great fun like been a crazy few years as you can imagine. Um but yeah, happy to share like both where we're up to and also give a kind of overview of like as part of that we can also kind of cover the story of like where is um where is mobile mobile AI up to today right like what's the state of the art what are the different patterns we see for model deployment... yeah like there's a lot of benefits to running on the edge. There's um like latency or UX improvements for some really sensitive in the loop um things like live voice translation for example. Uh that's something our team shipped on Pixel last year where you can do a live voice translation. Very challenging to do that with the required latency using a cloud service. So being able to do that offline and on the edge is key to be able to meet latency or user experience requirements. Um privacy that's um uh that's definitely a thing as well... offline use yeah that's kind of obvious and then savings um yeah like we see this being increasingly relevant for laptop users... some folks are interested in exporting savings as well.

</details>

### 终端生成式 AI 的双轨并行：系统级与应用内

目前的终端 AI 呈现出两大趋势：一是**系统级生成式 AI**（System-level GenAI: 由操作系统内置 2B-5B 参数的大型模型，如 Android 的 AI Core 或 Apple Intelligence），开发者通过 API 调用摘要或提示词功能；二是**应用内生成式 AI**（In-app GenAI: 使用小于 1B 参数的**微型大模型**（Tiny LLMs: 针对特定任务微调的超轻量化模型））。这类模型不仅能覆盖非旗舰机型，且在经过特定任务（如转录、摘要、语音转动作）微调后，100M-500M 参数量的模型即可达到生产级的可靠性。

<details>
<summary>Original English Source</summary>

Oh yeah. So this is kind of important uh concept is we see two trends happening today. Uh one is we see kind of system level genai. So for very very large models, the way these tends to turn up on mobile phones isn't that you know when you launch a single app it will download a four billion parameter model uh just to uh you know just to help you find a good restaurant in you know uh in whatever app you're looking up looking in right instead the trend is to build larger models into the OS. So we call this like system level gen AAI. These models tend to be in the kind of two to five billion parameter range, right? Like it depends on the OS and um whatever. But like this is one choice that we see both the Android team who we work closely with and the um Apple intelligence team. we see kind of similar choices being made by both mobile OS vendors where there's a central model built in... so then the other trend we see is like inapp genai which is where the kind of tiny LLMs or um TLMs as we're calling them in this presentation are more uh are more relevant right... inapp genai generally these are custom to tasks they're loaded with the app or with the web page. We also deploy some of these uh on the web and generally they're targeted at kind of like wider reach... we can get really reliable performance from models in the um uh really reliable performance from models in the like 100 to 500 million parameter range depending on the complexity of the task, right? ...for the really really tiny models uh certainly less than 500 in our experience you need to fine-tune to get kind of production level reliability.

</details>

### 智能体技能：在边缘端构建动态扩展能力

随着 **Gemma 4** 系列模型的发布，Google 引入了**智能体技能**（Agent Skills: 允许模型调用外部工具或脚本完成特定任务的能力）架构。为了解决边缘端上下文窗口和算力的限制，该系统采用了“按需加载”模式：模型先根据一行的技能描述判断是否需要该功能，再动态加载完整的技能定义（skill.md）和 JavaScript 脚本。这种模式大大提高了代币效率（Token Efficiency）和推理速度，使得在手机端实现地图查询、日历同步、甚至音乐合成等复杂交互成为可能。

<details>
<summary>Original English Source</summary>

The thing we're the thing that's newest from my perspective is kind of agent skills on device... what's actually happening is um the way we've built the skills is they're efficient. Uh so the instructions can be kind of loaded on demand. So this kind of uses a principle... of um kind of uh wow um like kind of progressive disclosure of conditional or conditional depth. So instead of like in an MCP workflow where you need to describe everything about all of the functions that you need, the way we've structured the skills is there's a kind of oneline description, the oneline descriptions of the skills is what the agent sees and then if it thinks that sounds interesting, then it asks for more. It asks to load the skill... and then it goes in and loads the skill and it finds out all of the the details about how to use it, what function calls it can use to to do that skill. So this is like that pattern is particularly important for kind of token efficiency and frankly like reliability on edge models... if you can have a more condensed context window that'll kind of uh up your batting average in terms of kind of quality metrics you're looking at... within our structure of skills we have skill.md and then there's optionally kind of scripts or assets... within scripts, we do also support um uh people kind of writing custom JavaScripts that can then be rendered within the app... [Examples mentioned: Mood tracker, Map skill, Wikipedia skill, Mood music scale, Flashcards, Piano playing].

</details>

### LiteRT-LM：跨平台的边缘端推理引擎

Google 提供了统一的推理框架 **LiteRT-LM**（其前身为 TensorFlow Lite），支持在 Android、iOS、Windows、Linux 以及 IoT 设备上跨平台运行。该引擎通过 **XNNPACK** (CPU 优化库) 和 **ML Drift** (GPU 优化库) 确保了极致的性能。对于 NPU 的部署，则需要通过供应商编译器进行**提前编译**（Ahead-of-Time Compile: 针对特定硬件生成的二进制制品）。目前，2B 参数模型在高端 Android 手机上可实现每秒数千个代币的解码速度，即使在 Raspberry Pi 上也能运行基础的图像分析任务。

<details>
<summary>Original English Source</summary>

Okay. So this is like what we do as like our team we do enable people to build apps. uh we do uh media pipe uh lighter TLM which is a LLM runtime that works on mobile and edge and then lighter t which is just a standard inference framework this was a long time ago known as tensorflow light... it's also you can take the same TF light file and ship that to iOS, Mac OS, Linux, Windows, web or IoT devices just from that same file... One caveat there, that same file deploys on CPU and GPU. For NPU, we need to do some special compilation and you end up with a special NPU file... under the hood we actually invest an awful lot of work in um optimization libraries. So we've X and which is a CPU optimization library and ML drift which is an optimization libraries for GPUs... For NPU we need something a little more specialized. For npu, we need to call a vendor compiler plug-in upfront and that uses an ahead of time compile workflow. So you need to produce an artifact that's particular to a particular npu. ...for the two billion parameter model we can get really compelling performance on a like a high-end Android phone can do thousands of tokens per second on a GPU... on a Raspberry Pi we can get um about 133 tokens per second.

</details>

### 实战案例：AI Edge Eloquent 智能转录与润色

在应用层面，Google 展示了名为 **Eloquent** 的离线转录应用。它不仅能进行语音识别，还内置了一个专用的文本润色引擎。通过**偏差字典**（Biasing Dictionary: 用于强制模型识别特定术语、人名或技术词汇的列表），该应用能精准识别领域术语（如 "LoRA" 而非 "Laura"）。其开发流程极具参考价值：先利用云端强大模型生成海量**合成数据**（Synthetic Data），再对 300M 左右的微型模型进行**指令微调**（Instruction Fine-tuning），从而在极低功耗下实现媲美云端的服务。

<details>
<summary>Original English Source</summary>

What I'm going to show next is an example of a app that we've built using uh tiny LLMs... called AI edge eloquent. Um what this is is a kind of transcription um model but instead... it can kind of remove all of the kind of interjection and and words... one of the other things it has as well is a uh a biasing uh list... any standard transcription service would when you say Laura, it would translate that to the name Lau or A... Whereas you can give it a list of kind of keywords or technical terms as well. And then the model will kind of um uh bias to those words... the microphone input goes into a speech recognition engine that delivers a unfiltered transcription... both of these go into a text polishing engine which is then a um dedicated L mini LLM just for text polishing... generally what that workflow looks like to give you a bit more insight is we'll use a workflow of using a much stronger LLM in the cloud to generate lots and lots of synthetic data that corresponds to the type of thing we want. And then once you have a few, you know, lowdigit millions or tens of millions... you kind of put that into a fine-tuning workflow and you fine-tune the base tiny model you're working with to get a derived model. ...for tiny models uh certainly less than 500 in our experience you need to fine-tune to get kind of production level reliability.

</details>

### 边缘端 AI 的未来：安全性与硬件协同

在问答环节，Cormac 强调了边缘端模型的安全性需要模型厂商和系统厂商的多层防护。针对显存瓶颈，Gemma 团队对 **KV 缓存**（KV Cache: 存储注意力机制中间状态的内存缓冲区）进行了深度优化，使 2B/4B 模型能支持高达 32K 的上下文。此外，LiteRT-LM 运行时还支持**热交换 LoRA 适配器**（Hot-swapping LoRA Adapters），这意味着机器人或 IoT 平台可以在不重新加载基座模型的情况下，快速切换不同的任务技能，极大地提升了系统的灵活性。

<details>
<summary>Original English Source</summary>

Questions about safety on edge models. So firstly the Gemma team spend an awful lot of time on this... the system vendor will typically have some sort of input and output safety checker on the model, right? Uh, as a kind of aftermarket addition... the mediumsiz models have a context window of 128K and the smaller models [E2B/E4B]... 32K. ...the amount of kind of KV cache that's required for each input token that was something that was optimized. So the models behave pretty well on that front. ...if somebody asked me about deploying the 2B on an uh on a robotics platform I would be like absolutely you should fine-tune Lauras for each of your things for each of your tasks and then like our runtime supports loading the model and like hot swapping Loras so you don't even need to kind of load and unload the model to load and unload Laura adapters uh that it's built for that particular use case for like robotics or IoT platforms.

</details>