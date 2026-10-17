---
author: AI Engineer
date: '2026-08-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YXowceUKYJI
speaker: AI Engineer
tags:
  - kv-cache-routing
  - prefill-decode-disaggregation
  - llm-inference
  - agentic-workloads
title: Kubernetes 上的 KV Cache 感知路由与 P/D 分离架构深演
summary: 本文基于 Red Hat 推理团队专家的分享，深入探讨了 Agent 智能体时代大语言模型（LLM）推理面临的挑战。重点解析了如何通过 LLMD 实现 KV Cache 感知路由和前向填充与解码（P/D）分离架构，并分享了在 H200 芯片集群上部署 GLM 5.2 模型的实战案例与多维性能优化数据。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Red Hat
  - IBM
  - Google
  - Nvidia
  - CoreWeave
products_models:
  - LLMD
  - GLM 5.2
  - vLLM
  - speculators
  - guide-LLM
  - LLM Compressor
media_books: []
status: evergreen
---
### 议程与背景介绍

**[Ashish Kamra]**: 好的。嗯，欢迎大家来到又一场关于推理的分享。我希望大家到目前为止在大会上过得愉快。在本次演讲中，我相信在座的各位想必已经多次听到这些专业术语了。因此，我们将进一步深入探讨针对 **Agent 智能体负载 (Agentic Workloads)** 的 **大语言模型 (LLM)** 部署挑战，本节我们将重点关注 **KV Cache 感知路由 (KV Cache-Aware Routing)** 以及 **前向填充与解码分离 (Prefill-Decode Disaggregation / PD Disaggregation)**。此外，当大家查看公开的推理基准测试结果时，通常看到的都是非常平稳、孤立且高度净化的数据，而这些基准测试实际上无法向您展示多轮交互、海量上下文波动的混乱现实，而这些正是智能体工作负载的典型特征。因此，我们也将尝试揭开这些复杂性的面纱。首先自我介绍一下，我叫 **Ashish Kamra**，是 **Red Hat** 性能工程部的资深经理。而在我身旁的这位是……

<details>
<summary>Original English</summary>

**[Ashish Kamra]**: All right. Um, welcome everyone to yet another inference talk. I hope you have had a good conference so far. And so in this session, I mean I'm sure you people who have been in the room must have heard these terms many times by now. So we're going to do a little bit more deep dive into the challenges of LLM deployments for agentic workloads and in this session we'll focus specifically on KV cache aware routing and PD disaggregation, and also you know when you look at public inference benchmark results you are typically looking at very steady state isolated highly sanitized numbers and what those benchmarks actually don't show you is the chaotic reality of multi-turn interactions, massive context fluctuations which are very typical of agentic workloads. So we'll also try to pull the curtain back on some of those complexities. By way of introduction, my name is Ashish Kamra. I'm a senior manager of performance engineering at Red Hat. And with me...

</details>

**[Yuchen Chen]**: 大家好，我是 **Yuchen Chen**。我是 Red Hat Inference 的产品经理，与 **vLLM** 和 **AMD** 的核心维护者们紧密合作，我自己也是贡献者之一。

<details>
<summary>Original English</summary>

**[Yuchen Chen]**: hi I'm Yuch Chen. I'm the product manager at Red Hat Inference working closely with vLLM and AMD core maintainers. also a contributor myself.

</details>

**[Ashish Kamra]**: 好的，以下是接下来大约 20 分钟的议程。首先，Yuchen 将从分析智能体时代的推理行为以及一些核心特征和挑战开始。接下来，他将带我们了解 KV Cache 的利用和管理策略。然后，我将拆解前向填充（Prefill）与解码（Decode）分离的机制，并向大家展示一些实验结果。接着，Yuchen 会结合我们目前正在针对大家喜爱的开源代码模型 **GLM 5.2** 进行的实战案例研究，将所有这些概念串联起来。

另外，如果大家对学习开源推理更感兴趣，我们这边有两个推荐资源：一个是 **Cedric** 与 **吴恩达 (Andrew Ng)** 合作在 **deeplearning.ai** 上推出的免费课程；另一个是 Red Hat 开发者门户网站上关于分布式推理概念、故障排除和部署模式的一系列博客。

对于那些可能还不了解我们的人来说——虽然 Red Hat 更广为人知的是作为企业级 Linux 的 Linux 公司以及针对 OpenShift 的 **Kubernetes** 公司——但最近，我们也是开源 AI 推理领域的主要参与者。我们是 vLLM、**LLMD** 和 KServe 等项目的核心贡献者，同时还孵化了用于基准测试的 **guide-LLM**、用于模型量化的 **LLM Compressor** 以及用于投机解码模型的 **speculators**。我们还在 **Hugging Face** 的 Red Hat AI 空间下将这些工具整合在一个优化模型库中。不仅如此，我们还在为下一波智能体推理负载构建基础平台。接下来，我将把麦克风递给 Yuchen，由他来带大家深入了解。

<details>
<summary>Original English</summary>

**[Ashish Kamra]**: So here is the agenda for the next 20 minutes or so. Um Euchen will start with an analysis of inference behavior in the agentic era and some of the core characteristics and challenges. Uh next we next you will walk us through the KV cache um utilization and management strategies. I will break down the mechanics of pre-fill decode disagregation and walk you through some some results and then Euchen will again bring it all together with our ongoing case study on our favorite open coding model GLM 5.2. Um and just a couple of sources from our side if you are more interested in learning more about open source inference we have a free course free course on deep learning.ai AI uh by Cedric and with Andrew Ning. Um and the other is a series of blogs on the Red Hat developer portal on distributed inference concepts uh troubleshooting and deployment patterns. Uh and for those who may not be aware since Red Hat is better known as the Linux company for enterprise Linux and uh the Kubernetes company for Open Shift uh but more recently we are also a major player in open source AI inference with uh us being the top contributor in vLLM LLMD and the case of projects and also uh having incubated guide LLM for benchmarking LLM compressor for model quantization and speculators for uh speculative uh decoding models and we also bring it bring all of that together in a optimized model hub on hugging face under the Red Hat AI arc. Um and we are also building the platform for the next wave of agentic inference workloads and with that I will hand over to you to uh walk you through more of it.

</details>

---

### Agent时代的挑战

**[Yuchen Chen]**: 好的。我们目前正处于从传统推理时代向智能体时代过渡的拐点。当我们观察现实世界中的智能体负载（例如 **SWE-bench**，以及来自现实云端代码开发会话的真实调用链路数据）时，它们从根本上打破了我们在经典 LLM 部署服务中所做的许多假设。

正如大家在之前的议程中多次听到的那样，例如，多轮交互已经成为新常态。我们发现，对话从仅仅几次交互一直延伸到多达 3,000 轮交互。此外，由于智能体频繁重复使用相同的系统提示词（System Prompt）和工具定义（Tool Definitions），我们通常会看到极高的缓存命中率，往往远超 90%。

另一个特征是，输入与输出 Token 数量的比例非常悬殊，通常超过 100:1 甚至在许多情况下更高。在这之上，由于这种极高的变异性，上下文管理变得异常复杂。因为我们不能简单地取平均值来规划，往往在进行容量规划（Capacity Planning）时，我们需要看数据的整体分布情况，尤其是 P90 和 P99 的数值。

此外，我们还观察到了非常有趣的模式，比如子智能体面板（Sub-agent Panel），这进一步增加了调度的复杂性。为了帮助社区研究这些模式，我们与 **Google** 合作（非常感谢），同时也与我们的母公司 **IBM** 合作，在 Inference Perf 压力测试工具中添加了一个 Trace 回放工具，正如大家在今天早些时候 Ashok 和 Jason 的分享中所听到的那样。大家可以去关注并体验这个项目，链接就在这里。

<details>
<summary>Original English</summary>

**[Yuchen Chen]**: So we are currently um at this inflection point moving from the era of classic inference to the agentic era. So when we look at the real world agentic work workloads such as uh sweet bench and also watrices from real world cloud code sessions they fundamentally break many assumptions we made with classic LM serving. uh as you heard actually many times in previous sessions for example multi-turns and new standard we found from a few turns all the way to 3,000 turns and also because agent frequently reuse the uh system prompt and the tool definitions we usually see super high cash hit rate um oftentimes well exceeding 90%. Uh another thing is input output ratio is massive oftentimes over a 100 ratio and even higher and in many cases and on top of that the context management is is incredibly complex due to this high variance because we can't just simply take the average and oftentimes we need to look at the distributions and the P90 numbers especially when you do uh capacity planning and also we observe really interesting patterns like sub Asian panel which which further complex uh complicates scheduling. So to help communities study um this patterns we collaborate with Google thank you and also IBM our parent company to add uh a a trace replay tool in the inference perf you heard from earlier sessions uh from Ashoken and Jason. Um so yeah feel free to check it out and the link is here.

</details>

---

### 感知路由与缓存

**[Yuchen Chen]**: 接下来看下一张幻灯片。基于我们刚刚看到的智能体工作负载的特征进行转型，我们不再盲目在稳态下追求单纯的吞吐量。我们通常需要优化比如交互延迟，面对的是极度不稳定且完全由客户端决定的上下文环境，因为用户和客户端定义了整个提示词的结构。这引入了几个关键性挑战。

首先，KV Cache 管理变得极其动荡，因为上下文完全由客户端决定。因此，我们经常需要面对频繁的缓存淘汰和重写。

其次，我们需要协同上层的调度和路由，去调优像 vLLM 这样的底层引擎。这种协调在引入前缀路由时尤为必要，特别是当延迟成为首要的调度度量指标，而不是被当作次要指标或事后才考虑的事情时。

第三点，我们还需要重新审视我们的评估指标。例如，我们需要单独衡量缓存下的吞吐量。为什么？因为正如右图所示，其背后的经济利益差别非常大。这里展示的是 Anthropic API 的定价。正如在之前的演讲中提到的，缓存 Token 和非缓存 Token 之间存在 10 倍的成本差距。对于企业而言，代币资产负债表上 10 倍的差距会对业务利润产生非常严重的影响。

接下来，让我们来看看在 LLMD 中是如何对 KV Cache 进行利用和管理的。LLMD 路由器拥有非常灵活的端点选择器插件（Endpoint Picker Plugins），我们简称为 EP，它可以将请求路由到在 KV Cache 局部性（Locality）和负载指标上都最符合条件的 Pod。EP 会持续探测每个 Pod（例如获取 vLLM 的 Pod 指标），评估每个 Pod 上的运行中请求和等待中请求，以及 KV Cache 利用率和前缀缓存的可用性。这样，我们就能把请求调度到负载最低且最有可能实现缓存命中的最优 Pod 上。

<details>
<summary>Original English</summary>

**[Yuchen Chen]**: Uh next slide. Oh, so transition from the class uh the characteristics um we just saw for agentic workloads. We're no longer chasing this um this this raw throughput in a steady state. We often need to optimize uh for example interactive latency and they're very um highly volatile and client-driven context because user and you know client define the prompt structure. So this introduced several critical challenges. First of all, KV cache management becomes super volatile because the context is client determined as I said. So oftentimes we face this like you know frequent evictions and rewrites and secondly we also need to tune um the engine like VM with upper layer uh scheduling and routing. It needs that coordination such as prefix routing especially when latency becomes a primary uh scheduling matrix rather than like a secondary or afterthought. And thirdly, we also need to rethink our metrics. For example, we need to measure cats throughput separately. Why? Because on the right, it's really clear that economic stakes is very high. So, this is the uh anthropic API pricing. You also heard from earlier sessions. There's 10x cost difference between cash and non-cash tokens. So, 10x difference on your um token balance sheet is is pretty serious impact on your business. So next let's let's look at how the KV cache is um both utilized and managed in LMD. So LMD router has this really flexible um endpoint picker plugins we call the EP that can route the request to the optimal pods and that meet the KV cache locality and also the load criteria. So the EP continue probe each pods like VM pod matrix to score each pod on like the running for example running and waiting request and then the KV cache utilization also prefix uh cache availability and so we can schedule requests to the optimal pod with the lowest load and also highest possibility to um to of a cache hit.

</details>

**[Yuchen Chen]**: 进一步下沉到 KV Cache 的管理层，实际上，在刚刚结束的上一场议程中大家也听到了一些介绍。对于拥有热（Hot）、温（Warm）、冷（Cold）缓存特征的智能体交互会话，我们目前的精力主要集中在拓展更多的卸载介质层（Offloading Tiers）上，比如 NVMe SSD，以及伴随 KV 中心化存储（如 Mooncake）使用的 XFS 文件系统；同时也在实现更智能的、感知会话的淘汰策略，例如引入优先级和会话锁定（Session Pinning），以确保至关重要的上下文能在恰当的时间、恰当的节点上得以保留。

接下来我快速播放一个演示视频。这是一个非常简短的 Demo。

<details>
<summary>Original English</summary>

**[Yuchen Chen]**: So um going down from to the KV cache management layer actually you also heard from earlier session right before this. So for agentic sessions when you have u hot warm and cold cache our current effort focus on for example um more offloading tiers like NVME SSD and also file system XF along with KV ccentric store um like uh moon cake and also implementing smarter and session a wire eviction policies such as priority and also session pinning to uh ensure this uh really important you know the the context persists exactly when and where it's needed. So, I'm gonna play this video really quick. Uh it's a it's a short demo.

</details>

**[Ashish Kamra]**: 你可以站在这里，这样大家都能看清楚。

<details>
<summary>Original English</summary>

**[Ashish Kamra]**: Stand here so you can look at it.

</details>

**[Yuchen Chen]**: 好的。这就是一个关于 KV Cache 感知路由的实例。正如大家所见，当我们发送第一个请求并填充 KV Cache 时，大约需要 3 秒钟的时间。当我们观察此时的缓存命中状态时，因为这是第一轮对话，所以并没有命中 KV Cache。

随后，当我们进入第二轮对话时，请求重用了 KV Cache。大家可以看到，系统提示词是完全一致的，这次只用了大约 1 秒钟。而且，如果你去观察它分配到的 Pod IP 地址，会发现是完全相同的，这是因为我们定义了 KV Cache 的局部性路由。

现在进入第三轮对话，我们发起了一个带有不同系统提示词的新请求。这次处理耗时大约 3 秒钟。正如大家看到的，这里没有找到任何可复用的 KV Cache，并且你可以注意到它路由到了一个不同的 Pod 地址。

紧接着，如果我们仅仅修改用户提示词（User Prompt）而保留相同的系统提示词，在下一轮对话中，我们就可以重新利用 KV Cache。可以看到，这次也只用了大约 1 秒钟。这个演示非常直观。接下来，我将把时间交给 Ashish 来讲解下一张幻灯片。不过在此之前，我们先思考一下，这个方案解决了什么问题？通常，前缀路由或 KV Cache 感知路由帮助我们解决了 **首字延迟 (TTFT / Time to First Token)** 的问题，并在一定程度上提升了吞吐量。但在智能体场景下，指标并不仅局限于 TTFT。我们的吞吐量直接受到 **Token 间延迟 (ITL / Inter-Token Latency)** 的制约，那么该如何解决这个问题呢？这就需要引入前向填充与解码分离架构，这是一种非常强大的技术，但它也有其适用的边界条件。接下来由 Ashish 为大家带来 P/D 分离的深度原理解析。

<details>
<summary>Original English</summary>

**[Yuchen Chen]**: Okay. So, okay. So, this is a example of a KV cache bar routing. As you see, when we send the very first request and it populate the KV cache, it takes roughly 3 seconds. And when we actually look at where the KV cache uh is going there's no KV cache hit because it's the very first turn. And then when we have the second turn the request actually reuse a KV cache because as you see the system prompt is the same and this time takes about one seconds. And then when you actually look at the uh pod address exactly the same because we define the KV cache. Now going to the third turn a new request with different system prompt. Now it takes about three uh seconds and as you see you know right now and we don't find any KV cache here because you can tell it's different pod address and then if you just change the user prompt and keep the same system prompt and the next turn you you reuse the KB cache and in this in this time it takes roughly about uh one second. Yeah. So it's a pretty intuitive demo and um I'll turn it to Ashish to talk about the next side but before that what does problem does it solve? So often times the prefix routing KB cache routing helps you solve the TTFD problem and of course you'll improve your lat uh your your throughput but oftentimes for agentic workload is not just a TTFT your throughput is about your inter token latency how do we solve that so preview decode disagregation is a really uh powerful technique but there are times there work at times it doesn't work so I'll turn it to Ashish to give you a preview of um of the PD uh disregation

</details>

---

### P/D分离架构深演

**[Ashish Kamra]**: 在我们深入探讨 P/D 架构之前，先来看一下 LLMD 的全貌。LLMD 是一个高性能的 Kubernetes 原生（现在也支持非 Kubernetes 环境）的分布式 LLM 推理框架，目前托管在 **CNCF** 基金会伞下。LLMD 提供了一个统一的智能控制平面，专门为智能体时代的推理负载而设计。

正如刚才 Yuchen 在幻灯片顶部所介绍的，它包含路由器和 EP。其他方面还包括工作负载 API，比如用于编排复杂多节点模型执行的 LeaderWorkerSet 和 DisaggregatedSet，以及能够监控系统容量边界和实时流量组合、并根据系统负载独立对 Pod 进行扩缩容的自动伸缩器（Autoscalers）。

现在让我们详细剖析一下前向填充与解码分离架构。首先，为什么会存在 P/D 分离？在传统的聚合服务（Aggregated Serving）中，单个 Pod 必须同时负责优化首字延迟（TTFT）和 Token 间延迟（ITL）。但在 P/D 架构中，前向填充和解码被剥离为可以独立扩展的推理 Pod。

要理解我们为什么需要这样做，必须回归到 LLM 执行的物理特性上。将前向填充和解码任务混合部署在同一张 GPU 上会产生所谓的“相位干扰”（Phase Interference）。

前向填充阶段是为初始提示词创建 KV Cache 的过程。它需要高算力，具有高度突发性，能够让 GPU 运行在极高的 FLOPs（每秒浮点运算次数）上，并高度依赖大 Batch 并行度来快速处理提示词以构建初始缓存。

相反，解码阶段每次只生成一个 Token，这对于内存带宽的吞吐要求极高，对延迟极其敏感，并且需要极高密度的缓存常驻。如果在传统的聚合 Pod 中突然涌入一个超长的填充 prompt，它会完全阻塞正在进行的解码 Token 生成过程，导致严重的响应抖动，极大地破坏了用户的流式体验。

<details>
<summary>Original English</summary>

**[Ashish Kamra]**: So before we dive into PD, let's just uh look at what LLMD is. So LLMD is a high performance Kubernetes native and actually now works on non-cubernetes environments as well. Distributed LM LLM inference framework hosted under the CNCF umbrella. LLMD provides a unified intelligent control plane designed specifically for the agentic era of inference workloads. Well, Euchin already talked about the router and the EP at the top of the slide. Um, the other aspects are workload APIs such as leader worker set and disagregated set that orchestrates complex multi- multi-node model execution and then autoscalers that monitors capacity bounds and real-time traffic mixes to independently scale up and scale down uh your pods depending on the system load. So now look now let's look at uh prefill decode disagregation in detail. Um uh okay so why does PD exist in the first place? So one of the most powerful patterns implemented by LLMD is prefill decode disagregation and you must have heard from some of the previous talks as well. So what happens is in in a nonPD situation in aggregated serving one pod is responsible for optimizing both your time to first token and your inter token latencies. Uh but in PD prefill and decode become independently scalable inference pods. But to understand why we actually need this we have to look at the physics of LLM execution. colloccating uh both prefill and decode tasks on the same GPU creates something called as phase interference. Prefill phase is the phase that creates the KV caches for your initial prompt. It wants high compute. It's highly bursty uh utilizes GPUs at uh high flops and and thrives on large batch parallelism to process the prompts and builds the initial KV cache. The decode phase on the other hand is generating one token at a time and it's more me memory bandwidth hungry. It's highly latency sensitive and requires high heavy cache residency. So in a in a in a traditional aggregated pod if you if there's a sudden influx of a long prefilled prompt, it will completely stall the ongoing decode token generation process causing massive problems and jitter in user streaming latency.

</details>

**[Ashish Kamra]**: 那么在 LLMD 中，P/D 架构在实践中是如何运转的呢？

它的工作步骤如下：第一步，一个进入系统的请求首先到达网关路由器，路由器会通过我们之前提到的端点选择器（EP）动态评估集群的状态，决定该请求是否采用 P/D 分离处理，并选择出最优的前向填充节点和解码节点。

随后，路由器直接与选定的前向填充节点协调处理事务。前向填充节点处理提示词，构建初始的 KV Cache 并输出标准的 KV 传输元数据。

接着，目标解码节点通过网络物理织网（Network Fabric），利用前向填充 Pod 生成的元数据，将计算好的 KV Cache 拉取过来。这就是 LLMD 中 P/D 分离的具体实现方式。

<details>
<summary>Original English</summary>

**[Ashish Kamra]**: So, so how does PD actually work in practice in LMD? So, LNMD uses um uh you know like okay, we'll start with step one. A incoming request hits the gateway router which dynamically evaluates cluster states using something known as the endpoint picker you talked about and schedules the request to use PD disagregation selecting the optimal prefill and decode workers. The router then coordinates the transaction directly with the designated pre-fill worker. The pre-fill worker processes the prompt, construct the initial KV cache of the prompt and outputs the standard KV transfer metadata. Um, and the target decode worker actually pulls the computed KV caches um, uh, across the network fab fabric utilizing uh, the KV transfer metadata that the uh, uh, prefill pod had generated. Um okay so with that yes that's kind of how uh PD is implemented in practice in LMD and...

</details>

---

### 性能数据实测分析

**[Ashish Kamra]**: 接下来我想向大家展示一些我们测试的实验数据，来证明 P/D 架构在哪些场景下大放异彩。

在图表中大家可以看到，在最上方的红色曲线代表的传统聚合部署（Aggregated Deployment）下，P99 的 ITL（Token 间延迟）大约在 900 毫秒左右剧烈波动。而最下方的蓝色曲线代表的是 P/D 部署下的 P99 ITL。可以看到，它的响应不仅平滑得多，而且延迟仅为 100 毫秒左右，性能提升了将近 9 倍！

这是 Red Hat 内部的测试数据：我们使用了一个 GPT-style 的 12B 模型，运行在 16 张 **H100** 卡上。聚合配置下采用 4 副本、张量并行度（Tensor Parallelism）为 4；而分离配置下采用 2 个前向填充实例和 2 个解码实例，张量并行度同样为 4。测试场景为高度多轮交互负载，前缀上下文长度为 10,000 Token，每轮对话输出 128 Token。

这是一张非常棒的对比图：最下方代表的是作为基准线的标准聚合配置，使用的是 Kubernetes 默认的调度策略。中间的蓝色曲线仍然是聚合模式，但是启用了 LLMD 的 KV Cache 感知路由，你可以明显看到仅凭路由算法优化所带来的性能跃升。最上面的红色曲线则是在包含 2 前向填充与 2 解码节点的 P/D 模式下运行的结果。大家可以发现，在极低或极高并发的区间，P/D 的延迟表现和聚合模式很接近，但处于中等并发区间时，P/D 的性能优势便非常显著地展现出来。这正是我们在同时对比 P/D 与聚合方案时看到的经典帕累托曲线。

这组测试结果基于 12B 模型和 64 张 H100 GPU。聚合方案下采用 8 副本、张量并行 8；分离方案下采用 3 个前向填充节点和 5 个解码节点，张量并行也是 8。这是一类重前向填充的负载，平均输入长度为 5,000 Token，输出长度为 500 Token。大家可以清楚地看到，蓝色的 P/D 曲线在整个交互性能区间上完全压制了红色的聚合配置曲线。

<details>
<summary>Original English</summary>

**[Ashish Kamra]**: next I would like to show you some uh experimental results on where PD actually shines. So in this graph you can see that um uh in in in the standard aggregated deployment which is the top red line uh the P99 ITL uh hovers roughly around 900 milliseconds and you can you can see some fluctuations um up and down and but the the bottom blue line is the P99 uh inter token latency on a PD deployment and you can see that it's drastically almost nine times better at 100 millconds and it's also much smoother uh than the aggregated serving and uh this is some of our own internal results at Red Hat. So for a GPOSS 12B model uh 16 H100s uh the aggregated config is four replicas tensor parallelism 4 and the disagregated is two prefilled 2D code all with tensor parallelism 4. It's a highly multi-turn workload with a 10,000 token prefix and 128 tokens for every turn every turn. So, so this is a great chart like you can see at the bottom most line is a standard aggregated config that's uh is doing the default Kubernetes scheduling and uh and it's aggregated. So that's kind of our baseline and then the middle blue line is still aggregated but with the LLMD uh KV cache aware routing and you can almost see the gains just just based on the routing and the red line is actually the PD uh the pre-fill decode config with two pre-fill and two decode workers and you can actually see that like it's very similar to the aggregated config at the lower concurrency regimes and uh even and and very similar at the higher concurrency regimes but it's actually the middle part of the concurrency regime that PD actually shines and and these are some of the the the classic parita curves that we see when you actually do PD and uh aggregated side by side. So these results are again from the GPTOSS 12B model 64 H100s aggregated is eight replicas TP8 and this a is uh three prefilled 5D code again TP8 and a pre-filled heavy workload with like 5,000 average input sequence length and 500 output sequence length and you can actually see the blue line is the the PD curve and the red line is the aggregated curve and the PD curve kind of dominates um uh the aggregate curve across the entire interactivity spectrum.

</details>

---

### 决策矩阵与选型

**[Ashish Kamra]**: 话虽如此，我并不想让大家产生“P/D 架构在任何情况下都是灵丹妙药”的误解。它本质上是一种相位分离的权衡，而不是包治百病的万能钥匙。为此，我们梳理了一个矩阵来帮助大家评估何时应该采用 P/D 架构。

如果你的系统面对的是长上下文，且输入与输出长度比（ISL/OSL Ratio）极高，同时在为大型模型服务，并有能力应用丰富的模型并行度技术，并且处于我们刚才展示的中等并发负载区间，最重要的一点是，你对 Token 间延迟（ITL）流式平滑度有非常苛刻的指标要求，那么你应该优先考虑 P/D 分离。然而，我们也注意到这需要在网络上将 KV Cache 从前向填充节点转移到解码节点。因此，你的硬件设施必须配备先进的高速网络架构，如 **RDMA** 或 **RoCE**，来支撑这种极速的数据同步。

相反，如果你们没有此类需求——例如短上下文、中等上下文、任意模型规格、低并发区间，或者对首字延迟（TTFT）有极其严苛的要求（因为你可以直接在聚合模式下对此进行针对性调优），尤其是当你们的基础设施缺少高速网络环境来支持跨节点 KV Cache 迁移时，我们建议大家继续保留传统的聚合服务。

我的核心结论是：设计和架构这样一个复杂的推理平台，需要在一系列高度多维度的设计空间中权衡各种配置旋钮。而所有这些，都得到了 LLMD 系统的原生支持。正如大家所见，调度器必须时刻对 SLO 目标、QEP、KV Cache 局部性指标、P/D 比例和网络拓扑进行动态计算以实现最优路由；而在 P/D 分离架构中，我们则需要动态的 P/D 速率匹配算法以适应负载变化，因为静态的 P/D 比例往往无法跟上流量结构变化的脚步，我们需要自动伸缩器能够根据需要独立地为前向填充和解码池扩容，并持续调优张量并行、数据并行等模型并行技术来保障 SLO 的达成。

接下来，我把时间交还给 Yuchen，让他结合我们对 GLM 5.2 模型的实际部署案例研究，来具体说明这些概念。这个项目到目前为止依然在活跃推进中。

<details>
<summary>Original English</summary>

**[Ashish Kamra]**: Okay, but I don't want to leave you guys that PD is the answer to everything and it's a magic bullet. But um it's uh it's essentially a separation phase separation trade-off and not a magic bullet. So we created this uh matrix to help you decide when PD might be uh good for you. So if you're managing long context uh with high ISL OSL ratios and you if you have a large model that you're serving that can that you can apply rich model parallelism techniques um you're facing that middle concurrency regime uh that I I showed you in the previous graphs and and the very important part is that if you want uh strict ITL streaming requirements like you want the you want the token generation to be uh much more smooth um then you want to consider PD but we also saw that it requires transfer of KV caches from your pre-filled workers to your decode workers. So you must pro process an advanced uh high-speeded network fabric like uh RDMMA or rocky to support that KV cache transfer. And if you do not have such requirements, short moderate context, any model size, low concurrency regimes or uh if you have strict TTF requirements because you can actually tune them on an aggregate serving um and you the biggest point is like if you don't have the network fabric to support those KV cache transfers. So you might actually just want to stick with aggregated. So here is my key takeaway from all of this. So architecting this complex platform requires balancing a lot of uh knobs and a highly multi-dimensional design space all of which is supported in LLMD. As you saw the scheduler must or constantly evaluate SLO targets uh QEPs KV cache locality metrics PD ratios and network topologies to be able to route the request to the optimal FOD. While in while the PD design space you you need dynamic PD rate matching to adapt to PD ratios because you know you can start with a static PD ratio but it needs to evolve with the autoscaler as the traffic changes um and you need uh yeah autoscaling to scale PD pools independently um and constantly tweaking model parallelism techniques like tensor parallelism data parallelism uh to meet your SLOs's. So um I think with these uh I will hand it over to Euchen to anchor some of the concepts that we showed with the real world case study of serving the GLM 5.2 model uh which is uh still ongoing as we speak.

</details>

---

### GLM 5.2实战案例

**[Yuchen Chen]**: 是的，目前依然在进行中。大家可能已经在 NVIDIA 的 B200 平台上见识到了 GLM 5.2 的惊人性能。但在我们与客户沟通的过程中，很多客户其实并没有 B200 这样奢侈的配置。他们的机房里目前部署的大多是 **H200** 系列 GPU。因此，我们必须探索如何合理调配各项性能旋钮，让 GLM 5.2 在 H200 集群上实现最优的推理效率。

让我们把所有的概念整合在一起。我们刚刚讨论了 KV Cache 路由、P/D 分离。在 LLMD 的内部实践中，我们将这套流转路径统称为“智能体最优路线（Wild Path）”。在此基础上，我们结合了多元化的并行方案，以便能够独立地横向扩展前向填充路径，因为智能体负载中伴随着超长且沉重的前向填充计算。

在这个具体的落地案例中，我们设计的前向填充池最多可配置 3 个工作节点，旨在通过深度的计算并行度实现超高吞吐率；而在解码端，我们只分配了 1 个专注于低延迟表现的专属节点。我们通过 vLLM 来实现前向填充与解码池之间的高效 KV Cache 传输。

针对每个工作节点，我们配置了 LeaderWorkerSet 组，其拓扑为张量并行 1、数据并行 8，并且配合了专家并行度（Expert Parallelism）为 8（即 TP1, DP8, EP8）。这套架构的优势在于其高度的模块化特征，因为如果系统遭遇吞吐压力，我们完全可以仅通过水平添加填充池的节点来线性扩展计算吞吐，而不需要去重新配置解码池的状态。这完美体现了 Red Hat 是如何在工程化实践中管理 P/D 与专家并行在超大规模下的复杂度的。

此外，在几天前我们还得出了一个非常有趣的发现：在处理超长的前向填充任务时，使用 BF16 精度格式的 KV Cache 甚至比使用 FP8 精度格式具有更快的响应速度。这也是我们持续研究的课题之一，今后还会源源不断地发现新的性能范式。

不过现在，我更想让大家看一下我们的第一阶段的成果数据。在典型的智能体应用数据集中，ISL/OSL（输入输出比）极高，达到了 45:1。显而易见，前向填充成为了系统的瓶颈。通过在集群中部署 2 个前向填充实例和 1 个解码实例，我们成功将首字延迟（TTFT）缩短了 4 倍，且每秒能够多吞吐 60% 的请求！这是一套持续在迭代优化的开发方案。接下来，我们计划进一步把上层的 TTFT 压到更低，并在前端增加更多的填充副本。

<details>
<summary>Original English</summary>

**[Yuchen Chen]**: Yeah, still ongoing. You probably have seen tons of uh impressive numbers of GLM 5.2 on B200 when we talk to our customers and they usually don't have you know the luxury of B200. They have a lot of H200. So we have to figure out how to like put all the knobs together and make GM 5.2 work really well for cluster of of H200. So uh we let's anchor all the concept together. Um we went through for example the uh KV cache routing PD disagregation. We kind of call them a wildl path in LMD and also we combine with different parallelism strategies to so we can uh independently scale prefuel paths because for agentic workload is super uh long you know like heavy prefill. So uh in this case we designed the prefuel pool using up to three workers optimized for uh high throughput uh with deep and then for decoup we use uh one dedicated worker and um that's optimized for for low latency. So we use Nixo for efficient KV transfer between the pools and also with the each worker we have the leader worker set group uh with TP1 DP8 and also uh EP8 uh expert parallelism 8. So the architecture is just highly modular because you can uh actually scale the throughput by simply adding uh preview workers without reconfiguring and um the decoup. So uh this highlights how AMD effectly effectively managed the complexity of combining like PB and DB and EPI scale. And also we found some interesting fun fact actually a couple days ago. Um B B B B B B B B B B B B B B B B B B B B B B B B B B B B B B B B B B B B B Bf6 uh BF16 KV cache actually is faster than using like FPA uh KV cache for longer preview. Um this is also like we continue to explore and found like more interesting patterns, but more importantly uh we want to kind of just show the result really quick. So for this uh data set agentic workload data set the ISO OSL ratio is pretty high 45 to1 ratio preview is uh is really the constraint you can tell um with 2P even 1D we have um 4x passer TDFT and also 60 uh % more requests and this is continuous like work in progress so the next step is we need to also put the upper layer lower TTFT and also adding more more preview replicas so um...

</details>

---

### 总结与社区展望

**[Yuchen Chen]**: 我知道我们本场议程所剩的时间已经不多了。针对智能体负载所带来的根本性推理变革，我们将继续向着智能体“北极星”目标推进，未来将在会话图编排（Session Graph Orchestration）、程序感知调度（Program-Aware Scheduling）、状态复用生命周期（State Reuse Lifecycle）管理以及智能体基准测试工具等方面不断深耕。大家可以在 upstream 的 vLLM 与 LLMD 社区中找到这些工作的蛛丝马迹，我们也热忱邀请并欢迎大家加入我们的特殊兴趣小组（SIG）共同讨论和贡献代码。

在最后的幻灯片中，我们想强调：面对如此复杂的分布式推理工程挑战，没有任何一家公司能够单枪匹马完成所有的拼图。我们非常自豪能够在开源的旗帜下，与我们杰出的生态系统合作伙伴——**CoreWeave**、Google、IBM、**NVIDIA**，以及不断增长的发布伙伴和行业早期采纳者们并肩推动未来。如果大家也对开源推理的未来充满热忱，欢迎大家加入我们。我们在楼下也设有专门的展位，欢迎大家前去交流，再次感谢大家的宝贵时间！

<details>
<summary>Original English</summary>

**[Yuchen Chen]**: I know we're running out of time really quick. Uh we um the fundamental shift for agentic workload we're continuing to uh have this um uh agentic north uh northstar uh with session graph orchestration program award scheduling uh state reuse life cycle and also the uh agentic benchmark um we're working on. So you can find them uh in AMD upstream AMD and also you know feel free to join the SIG group and uh and contribute and um this is the very last slide. So distri distributed inference is not challenge uh every single comp a single company can solve along. We're proud to be uh building this uh future in the open alongside our incredible ecosystem collaborators uh core wave Google IBM Nvidia growing list of launch partners and industry adopters. So if you're passionate about the future of opensource inference, we invite you to join us. We do have a booth downstairs. Feel free to stop by, ask us any questions. And uh thank you so much for your time. [applause] >> [music]

</details>