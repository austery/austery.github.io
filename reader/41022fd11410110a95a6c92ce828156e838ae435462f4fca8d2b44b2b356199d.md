---
author: Latent Space
date: '2026-03-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=64D6tcsPH1U
speaker: Latent Space
tags:
  - inference-optimization
  - disaggregation
  - ai-agent
  - kv-cache
  - hardware-software-co-design
title: NVIDIA 的推理炼金术：从创业魂到数据中心级的 Dynamo 推理引擎
summary: 本次访谈深入探讨了 NVIDIA 内部如何保持“4万人的创业公司”活力。重点解析了数据中心级推理引擎 Dynamo 的架构设计，详细讨论了推理优化的核心三轴（成本、质量、延迟）、预填充与解码解耦技术、长上下文的硬件协同设计，以及 AI Agent 在生产环境中的安全边界与 CLI 交互的复兴。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Jensen Huang
companies_orgs:
  - NVIDIA
  - Brev
  - OpenAI
  - Anthropic
products_models:
  - Dynamo
  - DGX-Spark
  - Claude-Code
  - DeepSeek
  - Kimi
media_books: []
status: evergreen
---
### Agent 的三大安全边界

**[Netter]**: **Agent** 基本上能做三件事：访问你的文件、连接互联网，以及现在它们可以编写并执行**自定义代码**。你实际上应该只允许 Agent 同时做这三件事中的两件。

如果你允许它访问文件并编写自定义代码，你就不会想要它连接互联网，因为那是一个安全漏洞。如果你同时开启了互联网访问和文件系统访问，你就必须非常清楚这个 Agent 行为的全部范围。否则，可能会被注入恶意软件。这一直是我们思考的核心：既要赋能这种显然是未来的技术，又要找到能保护系统的**执行点**（Enforcement Points）。

<details>
<summary>Original English</summary>

**[Netter]**: Agents can do three things. They can access your files. They can access the internet. And then now they can write custom code and execute it. You should really only let an agent do two of those three things. If you can access your files and you can write custom code, you don't want internet access because that's one vulnerability, right? If you have access to internet and your file system, you should know the full scope of what that agent's capable of doing. Otherwise, malware can get injected or something that can happen. And so that's a lot of what we've been thinking about is like, you know, how do we both enable this because it's clearly the future, but then also, you know, what are these enforcement points that we can start to like protect?

</details>

### 从 Brev 冲浪板到 NVIDIA 收购

**[主持人]**: 欢迎来到 Chroma Studio 的 Lean Space 播客。我们请到了客座主持人 **Vivu**，以及来自 **NVIDIA** 的朋友们：**Netter** 和 **Kyle**。

<details>
<summary>Original English</summary>

**[Host]**: All right, welcome to the Lean Space podcast in the Chroma Studio. Welcome um to all the guests here. Uh we're back with our guest host Vivu. Welcome. Good to have you back. Uh and our friends uh Netter and uh Kyle from Nvidia. Welcome.

</details>

**[Netter]**: 大家好，我是 **Dynamo** 的工程负责人和架构师之一。

**[Kyle]**: 我是开发工具部门的负责人，主要关注开源、Agent 营销、**Brev** 以及开发者工具。

<details>
<summary>Original English</summary>

**[Netter]**: Yeah, thanks for having us. I'm one of the engineering leaders and AR architects of Dynamo.

**[Kyle]**: Yeah, you're the developers, developers, developers guy at NVIDIA, open source, agent marketing, brev, and like dev tools and stuff in the focus.

</details>

**[主持人]**: 我对 Netter 最深刻的记忆是你在 **GTC** 大会上的“营销噱头”。当时你的初创公司 **Brev** 还没被收购，你带着一块**冲浪板**去参展，结果 NVIDIA 竟然非常喜欢，直接把你们买了。

**[Netter]**: 是的，我们的 Logo 是一个 **Shaka**（夏威夷招呼手势）。很多初创公司都喜欢假装成大公司，但 **SF Compute** 的 Evan Conrad 告诉我们：“你们就是两个人在房间里搞开发，为什么要装呢？”于是我们把冲浪板和棕榈树带进了展位。虽然我们的展位在最偏僻的角落，但因为棕榈树很高，大家隔着老远都能看到 Brev。

我妻子当时还在医学院，她来帮忙贴冲浪板上的乙烯基贴纸。凌晨一点，在去 GTC 的前一天，她看着我说：“你这混蛋，要是这招真能成，你就是个天才。”后来被收购的消息公布后，我把这段视频发到了家庭群聊里。

<details>
<summary>Original English</summary>

**[Host]**: One of my favorite memories uh for NAD, like you always do like marketing stunts and like while you were brev you like had this surfboard that you like went down to GTC with and like Nvidia apparently liked it so much that they bought you like what was that like?

**[Netter]**: Yeah. Um, yeah, we we um our logo was a shaka. We we uh we were always just kind of like trying to keep true to who we were. I think you know so much stuff startups you're like trying to pretend that you're a bigger more mature company than you are and it was actually Evan Conrad uh from SF Compute who was just like you guys are guest amazing yeah um he was just like guys you're two dudes in a room why are you pretending that you're not U and so then we were like okay let's make the logo of Shaka we brought surfboards to our booth to GTC and the energy was great some palm trees too. They actually poked out over the walls so you could see the bread booth and no one else just from very far way. 

My wife was uh at the time fiance she was in medical school and she came to help us cuz it was like a big moment for us. And so we we bought this Cricut. It's like a vine like a vinyl uh printer cuz like how else are we going to label the surfboard? So um we got a surfboard. We got a cricket and it was just like fine-tuning for enterprises or something like that that we put on the surfboard and it's 1:00 a.m. the day before we go to GTC. She's helping me put these like vinyl stickers on and she goes, "You son of a... If you pull this off, you son of a bitch." And so, uh, pretty much after the acquisition, I stitched that within the news of the acquisition. I sent it to our family group chat.

</details>

### NVIDIA 的“物理极限”文化：SOL 原则

**[主持人]**: 我听说 NVIDIA 内部有一个非常有名的 **SOL**（Speed of Light，光速）原则，或者简称为 **SO**。这是什么意思？

**[Netter]**: 这是我学到的最重要的一课。在初创公司，一切都是关乎生死的；但在大组织里，层级会掩盖现实。**SO** 的本质是问：**物理规律**是什么？

如果光速是某个值，而现在速度慢了，那一定有东西挡路了。在讨论交付日期之前，先理解理论极限。不要告诉我为什么做不到，先告诉我理论上最快能多快，然后再告诉我差距在哪。这能帮助领导者创造**紧迫感**，打破噪音。

<details>
<summary>Original English</summary>

**[Host]**: One more thing before we move on to Kyle. Just have so many Jensen stories and I just love mining Jensen stories. Uh, my favorite so far is so. Uh, what is what is so?

**[Netter]**: So is actually I I think of all the lessons I've learned, that one's definitely my favorite. As you start to become a much larger organization, so is is essentially like what is the physics, right? The speed of light moves at a certain speed. So if flight's moving some slower, then you know something's in the way. So before trying to layer reality back in of like why can't this be delivered at some date? Let's just understand the physics. what is the theoretical limit to like uh how fast this can go and then start to tell me why cuz otherwise people will start telling you why something can't be done but actually I think any great leader's goal is just to create urgency.

</details>

**[Vivu]**: 只有**黄仁勋**能用“SO”卡来挑战别人吗？

**[Netter]**: 并不是为了赶人走，而是为了获得**第一性原理**（First Principles）的理解。比如你说买台电脑要5天，那 SOL 是什么？SOL 是我直接走进百思买（Best Buy）当场拿走。超出这个时间的部分就是“现实阻力”，我们需要拆解这些阻力是否合理。

<details>
<summary>Original English</summary>

**[Vivu]**: One thing I'm unclear about is can only Jensen use the so card...

**[Netter]**: Yeah. I think it's not so much about like get the [ __ ] out. It's like give me the root understanding, right? Like if you tell me something takes 3 weeks... The first principles. It's like what's the like why is it 3 weeks? What is the actual limit? If let's say you wanted to buy a new computer and someone told you it's going to be here in 5 days, what's the SOL? Well, like the SOL is like I could walk into a Best Buy and pick it up for you, right? So then anything that's like beyond that... we can kind of piece the reality back.

</details>

### 推理引擎 Dynamo：数据中心级的炼金术

**[Kyle]**: 现在“**推理**”（Inference）已经从一个小众话题变成了 101 公路边的广告牌。随着 **Agent** 消耗越来越多的 Token，**测试时扩缩容**（Test-time Scaling）变得极其重要。

**Dynamo** 的诞生是因为我们发现，现有的引擎如 vLLM 或 TensorRT-LLM 通常只关注单个副本的优化。但在数据中心级别大规模部署时，你不能只是垂直扩容（Scale up），因为会有硬件边界（比如 **NVLink** 只能跨 8 颗 GPU，超出后必须走稍慢的 **Infiniband**）。

Dynamo 是一个坐落在推理框架之上的**数据中心级推理引擎**。它利用规模经济来最大化 **KV Cache** 的命中率，并引入了“**解耦**”（Disaggregation）技术。

<details>
<summary>Original English</summary>

**[Kyle]**: I think at this point a lot of people are familiar with the term of inference. Inference at scale is becoming a lot more important. Uh we have these moments like you know open claw where you have these agents that take lots and lots of tokens but produce you know incredible results. Dynino sort of came about at NVIDIA because myself and a couple others were sort of talking about the these concepts that like, you know, you have inference engines like VLM, SLA, Tensor TLM. Um, and they have like one single copy. But when you're actually serving things at scale, you can't just scale up that replica because you end up with like performance problems. Dynamo is this data center scale inference engine that sits on top of the frameworks like VLM sang and tensor HLM and just makes things go faster because you can leverage the economy of scale. maximizing your cache hits or you want to employ new techniques in inference like disagregation.

</details>

### 预填充与解码的“解耦”艺术

**[主持人]**: 这种优化具体是怎么实现的？

**[Kyle]**: 我们通过调整三个轴来寻找最优解：**成本、质量、延迟**。一个核心技术是**解耦**。

传统推理引擎会在两个阶段之间“跳跃”：**预填充**（Pre-fill，读取序列并生成 KV Cache）和**解码**（Decode，生成新 Token）。预填充通常是**计算受限**（Compute-bound）的，而解码则是**内存带宽受限**（Memory-bound）。

通过将这两个阶段分开，你可以分别扩容。比如，你可以在高性能的 **DGX-Spark** 上做预填充，然后在 Mac 上做解码，这样速度反而更快。Dynamo 内部有一个名为 **Grove** 的 Kubernetes 组件，它会根据工作负载动态调整预填充和解码节点的比例。

<details>
<summary>Original English</summary>

**[Kyle]**: There are three things that determine whether or not something can be done with inference: cost, quality, latency. Historically models would be hosted with a single inference engine and that inference engine would sort of ping pong between two phases. There's pre-fill and then using that KV cache to generate new tokens which is called decode. Prefill is right now computebound most of the time. Decode is usually memory bound. Someone uh ExoLabs did a really cool demo where for the DGX Spark, which has a lot more compute, you can do the compute hungry prefill on a DGX Spark and then do the decode on a Mac and so that's faster. Dynamo actually has like a a Kubernetes uh component in it called Grove that allows you to do do this like crazy scaling specialization. 

</details>

### 长上下文与硬件协同设计

**[Vivu]**: 我们在长上下文（Long Context）方面是否已经达到了极限？比如目前大多模型都卡在 100 万长度。

**[Kyle]**: 这涉及到了“**硬件-模型-上下文协同设计**”。比如 **Moonshot** 的 **Kimi 2** 或 **DeepSeek**。Kimi 2 增加了很多专家（Experts），但减少了**注意头**（Attention Heads）。虽然计算依然是平方级增长，但通过减少头数，工作量减半了。

DeepSeek 的 **MLA**（Multi-head Latent Attention）更是激进。原本 12.8 万长度的 Llama 405B 上下文可能需要 40-80GB 的显存，而 DeepSeek 只需要 8GB。这些被 Leopold Aschenbrenner 称为“**Unhoblers**”（去阻碍者）的技术突破，将带领我们突破千万甚至亿级的上下文。

<details>
<summary>Original English</summary>

**[Kyle]**: We see models like Kimmy or GPTOSS. Kimmy 2 comes out, right? Kimi has more experts but fewer attention heads. Attention scales with the number of heads. If you have 64 heads versus 32 heads you do half the work. Deepseek's MLA (multi headlen attention) decrease the burden that KV has on the model which allows you to grow like longer in context. For context, the total context length of Deepseek is 128,000 tokens... fits into 8 GB and previously context like the llama 405b context of a similar size was like 40 or 80 gigabytes. I wouldn't be surprised if we do see the ability to like break through to like 10 million, 20 million, 100 million context through an unhobler showing up.

</details>

### 命令行（CLI）：Agent 的通用语言

**[Netter]**: NVIDIA 内部已经大规模部署了 **Claude Code** 和 **Cursor**，几万人都在用。我发现一个有趣的现象：**编码 Agent** 比通用 Agent 成功得多，很大程度上是因为它们能访问**终端**（Terminal）。

终端意味着它们可以访问你安装的所有工具。比如我们有个同事 Carlos 写了一个 **Outlook CLI**，我让 Agent 扫描我所有的邮件，总结重点，把需要回复的放进文件夹，其余全部归档。这简直是魔法。

**[Kyle]**: 没错。计算始于 Shell，后来我们觉得它对人类不友好，于是造了 GUI。讽刺的是，现在我们要让 LLM 去操作 GUI。其实最直接的办法就是把 Shell 的访问权限给 LLM。命令行数据在预训练语料中极其丰富，模型天然理解 CLI。

<details>
<summary>Original English</summary>

**[Netter]**: Coding agents have been so much more effective than general purpose agents. And I think a large part of that is it just has access to the terminal. It can write code and then it can compile the code and if there are errors it can fix it. I found this person uh his name is Carlos at the company. He wrote an Outlook CLI. I asked it to go through all of my emails... give me a summary, highlight any escalations... It was magic.

**[Kyle]**: Yeah, it's kind of funny, right? Like we like computing began with a terminal with a shell, but we said that it's not empathetic to humans. So we built these nice user interfaces and then now we have LLMs navigating our user interfaces. And ironically, we're not empathetic to the machine anymore. Just give the LLM access to the shell.

</details>

### 2026：系统即模型（System as Model）

**[Kyle]**: 如果说去年是编码 Agent 的元年，今年就是 **Sub-agent**（子代理）的一年。

我们要实现“**系统即模型**”（System as Model）。当你调用一个 API 时，后台可能是一个包含数十个子 Agent、各种路由和优化组件的复杂系统，但对用户来说，它依然表现为一个黑盒模型。Dynamo 就在帮助管理这种复杂性。

例如在 CES 上发布的模型路由器，它会自动决定某个查询是发给本地的 **DGX-Spark** 还是云端的基座模型，用户不再需要在“本地”和“云端”之间做二选一。

<details>
<summary>Original English</summary>

**[Kyle]**: This is the year system as model, right? Where instead of having like a single model be a thing, you have a system of models and components that are working together to like emulate the blackbox model. Under the hood, it's like a billion different models. And that's a lot of complexity, right? With Dynamo and with other libraries on media, we're looking to help manage that comp. We actually for CES, we just released the model router... the model router decides when to send queries to which one. It's no longer this like either or. It's use the best of everything that's available to you.

</details>