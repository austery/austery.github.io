---
author: AI Engineer
date: '2026-04-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=c5-kx2bwoCk
speaker: AI Engineer
tags:
  - llm-performance
  - local-ai
  - jetson-spark
  - model-quantization
  - time-to-first-token
title: 本地运行大语言模型：Jetson Spark 上的 LLM 性能实践
summary: 本文深入探讨了在 NVIDIA Jetson Spark 上本地运行大型语言模型（LLMs）的实际性能。通过数据驱动的实验，分析了内存容量、内存带宽、模型量化（如 NVFB4）对吞吐量和首个 token 生成时间（TTFT）的影响。结果表明，Jetson Spark 能够高效运行高达 2000 亿参数的模型，并提供了关键的本地开发和原型设计优势，是处理隐私数据和加速迭代的理想平台。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Nvidia
products_models:
  - Jetson Spark
  - Grace Blackwell
  - vLLM
  - NVFB4
media_books: []
status: evergreen
---
### AI 开发的挑战与本地化解决方案的兴起

大家好。我是 Moska Gabricima，Nvidia 的开发者关系经理，我在这里与构建和部署 AI 系统的开发者们紧密合作。今天，我们将探讨在 Jetson Spark 上本地运行大型语言模型（LLMs）的实际性能。这并非一次理论性的探讨，而是一次基于数据的实践之旅，深入剖析现代 AI 基础设施的权衡取舍。我们的研究结果基于实践实验，目标是理解在单个系统上实际可行的能力。

AI 的快速发展给开发者系统带来了更大的需求，形成了两大主要挑战：要么是内存不足，要么是缺乏合适的软件堆栈。这最终导致一切都推向云端或数据中心。当模型从实验阶段走向生产阶段时，成本可预测性、数据驻留以及确定性延迟等问题变得至关重要。迭代速度也常常依赖于对共享基础设施的访问。由于您的工作将与其他竞争性工作负载进行调度，这也会导致开发工作延迟。因此，问题来了：我们能否将部分工作流程迁移到更接近实际开发发生的地方？为了最大化开发者生产力，需要对这些挑战提供本地化解决方案。

<details>
<summary>Original English</summary>

Hello everyone. I'm Moska Gabricima, developer relations manager at Nvidia, where I work closely with developers building and deploying AI systems. Today, we're looking at running LLMs locally, practical LLM performance on the Jetson Spark. This isn't a theoretical talk. It's a data-backed journey through the trade-offs of modern AI infrastructure. Findings are based on hands-on experiments with the goal of understanding what's actually practical on a single system.

The evolution in AI puts greater demand on developer systems, creating two main challenges. You either run out of memory or you do not have access to the right software stack. Then you end up and pushing everything to the cloud or data center. As models move from experiments to production, concerns like cost predictability, data residency, and deterministic latency take center stage. And iteration speed often depends often depends on access to shared infrastructure. And since your work will be scheduled against other competing workloads, it causes delays in development work as well. So, the question becomes, can we bring some of that workflow closer to where development actually happens? To maximize developer productivity, local solutions to these challenges are required.

</details>

### Jetson Spark：专为 AI 构建的本地平台

Jetson Spark 从头开始设计，用于构建和运行 AI，并且可以作为一个独立的系统使用。它由 GB10 Grace Blackwell 超级芯片驱动，结合了 CPU 和 GPU 以及统一内存架构。拥有 128 GB 的统一内存和 NV4 支持，它使开发者能够在本地系统上处理多达约 2000 亿参数的模型，而这个系统可以放置在办公桌下方或桌面之上。它运行着与生产环境相同的 Nvidia AI 软件堆栈，这意味着工作流程可以以最小的改动从桌面迁移到数据中心或云端。这里的关键理念不是取代云，而是将强大的 AI 开发能力带到更接近开发者的位置。

<details>
<summary>Original English</summary>

The Jetson Spark is designed from the ground up to build and run AI and can be used as a standalone system. It's powered by the GB10 Grace Blackwell superchip, combining CPU and GPU with a unified memory architecture. With 128 GB of unified memory and NV4 support, it enables developers to work with models of up to around 200 billion parameters locally on a system that fits under the under a desk or on top of your desk. It runs the same Nvidia AI software stack used in production environments, meaning workflows can move from desktop to data center or cloud with minimal changes. The key idea here is not replacing the cloud, but bringing powerful AI development closer to the developer.

</details>

### 本地 LLM 部署与基准测试方法论

这是我的配置。一切都在本地运行并且是可复现的。为了服务模型，我使用了 vLLM，并搭配了一系列不同大小和精度格式的量化模型。我在一个 Nvidia 优化的容器内运行此配置。这将确保我们的环境与您在数据中心部署的环境完全一致。并且，我不想仅仅展示原始结果，而是要向您展示“如何”实现。我构建了一个自动化的基准测试工具。从 15 亿到 140 亿参数的每个模型运行都遵循相同的严格协议：通过 Docker 进行环境隔离，三次强制性预热运行，以及以 1 秒为间隔的后台 GPU 指标记录。

左侧是协调器脚本。对于每次执行，脚本都会自动生成一个使用精确时间戳和已清理模型 ID 的唯一目录。对于每个模型运行，它都会捕获完整模型的端点响应和必要的指标。右侧是结果，一个干净、版本化的运行产物。它包含了验证结果、元数据以及来自基准测试的文本结果所需的一切。右下角是启动任务的一个示例命令。现在，让我们看看实际的测量逻辑。

在 AI 应用中，端到端延迟很重要，但首个 Token 的生成时间（Time to First Token）才是定义用户感知性能的关键指标。如果首个 Token 瞬间到达，应用程序就会感觉响应迅速。这里的脚本展示了我们如何为流式响应的第一个数据块打时间戳。在这个脚本中，我们不仅仅是调用 API 并等待结果，而是显式地处理来自 vLLM 服务器的流式响应。如果您查看 `stream_once` 函数中高亮的部分，您将看到时间戳逻辑。

为了在实践中探索这一点，我在 Jetson Spark 上运行了一系列实验，使用了 vLLM。我测试了不同的模型，从较小的指令模型到较大的优化变体，所有这些都在相同的设置下进行。一切都实现了本地服务。这里的目标不是 pushing 理论极限，而是理解在开发者工作流程中的实际行为。让我们深入了解我捕获的原始性能数据。

<details>
<summary>Original English</summary>

This is my setup. Everything runs locally and is reproducible. To serve the models, I used vLLM with a set of quant models across different sizes and precision formats. I run this inside an Nvidia optimized container. This would ensure that our environment is identical to what you would deploy in a data center. And, [snorts] instead of just showing raw results, I want to show you the how. I built an automated benchmarking harness. Every model run from 1.5 billion to 14 billion follows the same strict protocol. Environment isolation via Docker, three mandatory warm-up runs, and background GPU metrics logging at 1-second intervals. On the left, you're looking at the orchestrator script. For every execution, the script automatically generates a unique directory using a precise timestamp and a sanitized model ID. For every model run, it captures the full model's endpoint response and necessary metrics. On the right, you see the result, a clean, versioned artifact of the run. It contains everything to verify the findings, the metadata, and the text results from the benchmarks. On the lower right, you can see an example command for getting things started. Now, let's look at the actual measurement logic. In an AI application, end-to-end latency is important, but time to first token is the metric that defines the user's perceived performance. If the first token arrives instantly, the application feels responsive. And this script here shows how we timestamp the very first chunk of a streaming response. In this script, we're not just calling an API and waiting for a result. We're explicitly handling the streaming response from the vLLM server. If you look at the highlighted block in the stream_once function, you'll see the timestamping logic. To explore this in practice, I ran a series of experiments using vLLM on the Jetson Spark. I tested different models, from a smaller instruction model to larger optimized variants, all under the same setup. Everything was served locally. The goal here wasn't to push theoretical limits, but to understand realistic behavior in a developer workflow. Let's dive into the raw performance data I captured.

</details>

### 性能洞察：模型吞吐量分析

这张条形图代表了测试集中每秒完成的 Token 数量。在最左侧，您可以看到 15 亿参数的指令模型，其吞吐量高达 61.73 个 Token/秒。但对我们而言，最有趣的数据点是 140 亿参数的 NVFB4 模型。尽管其尺寸几乎是 15 亿模型 的 10 倍，它仍然实现了 20.19 个 Token/秒 的吞吐量。我认为这是一个关键的工程最佳点。通过利用 Nvidia 的 NVFB4 4 位浮点量化，我们能够以比普通人阅读速度更快的吞吐量，维持一个复杂的、高智能的模型。

这里非常明显的是，随着模型的扩展，吞吐量是如何急剧下降的。以及量化技术是如何提供巨大帮助的。看看 140 亿参数的基础模型。其吞吐量下降到仅为 8.40 个 Token/秒。这证明了在 Blackwell 硬件上，量化格式的选择与硬件本身同等重要。正是它使得 Jetson Spark 能够弥合研究工作与生产原型引擎之间的差距。Spark 让我能够进行本地不同精度格式的实验，并实时理解其中的权衡。

<details>
<summary>Original English</summary>

This bar chart represents the completion token per second across the test set. At the far left, you see the 1.5 billion instruct model delivering a massive 61.73 tokens per second. But the most interesting data point for us is the 14 billion NVFB4 model. Despite being nearly 10 times larger than the 1.5 billion model, it still achieves 20.19 tokens per second. I would say this is a critical engineering sweet spot. By leveraging Nvidia's NVFB4 4-bit floating-point quantization, we were we are able to maintain a sophisticated, high-intelligent model at a throughput that is still faster than the average human reading speed. What becomes very clear here is how aggressively throughput drops as model is scaled as models scale. And how much quantization helps. Have a look at the 14 billion base model. It drops to just 8.40 tokens per second. This proves that on Blackwell archi- on Blackwell hardware, the choice of quantization format is just as important as the hardware itself. It's what allows the Jetson Spark to bridge the gap between research work and production prototyping engine. The Spark allowed me to experiment with different precision formats locally and understand the trade-offs in the real time.

</details>

### 性能洞察：首个 Token 生成时间 (TTFT)

虽然吞吐量衡量的是原始算力，但首个 Token 的生成时间（TTFT）是定义用户体验的指标。它决定了一个应用程序是感觉即时还是损坏。换句话说，它反映了模型开始响应的速度有多快。正如我们在结果中看到的，Jetson Spark 提供了卓越的响应能力。对于更大的模型，其 TTFT 的增加是符合预期的，因为更多的参数意味着在生成首个 Token 之前需要更多的计算。

在这张图表中，有趣的是比较两个 140 亿参数模型：基础模型和 NVFB4 模型。正如我们所见，140 亿 NVFB4 模型比未经优化的 140 亿基础模型在首个 Token 生成速度上快 3.4 倍。这里一个关键的启示是，内存容量并不等同于内存带宽。虽然 Jetson Spark 的 128 GB 统一内存允许我们容纳高达 2000 亿参数的庞大模型，但我们的吞吐量仍然受限于数据移动的效率，即内存带宽。这就是 NVFB4 成为英雄的原因。它有效地提高了每字节的智能，使得一个 140 亿参数的模型能够像一个更小的模型一样响应迅速。

<details>
<summary>Original English</summary>

While throughput is a measure of raw power, time to first token is the metric that defines user experience. It determines whether an application feels instant or broken. In other words, it reflects how quickly the model is starts responding. As we see in the results, the Jetson Spark delivers exceptional responsiveness. The increase for larger models is expected. More parameters mean more computation before the first token is generated. Out of all from this chart, the interesting ones are the comparison between the 14 billion parameter models, the base model and the NVFB4 model. As we can see, as we can see, the 14 billion NVFB4 is 3.4 times faster to first token than the unoptimized 14 base model. A key takeaway here from this data is that memory capacity is not the same as the memory bandwidth. While the Jetson Spark's 128 GB of unified memory allows us to fit massive models up to 200 billion parameters, our throughput is still governed by how efficiently we can move data. This is why NVFB4 is the hero here. It effectively increases our intelligence per byte, allowing a 14 billion model to feel as responsive as much smaller one.

</details>

### 核心发现与 Jetson Spark 的应用场景

在运行完所有这些测试后，有两点给我留下了深刻印象。关于何时使用 Jetson Spark：适用于稳态工作负载、隐私敏感数据以及快速原型开发。它允许您使用与 Jetson Cloud 相同的软件堆栈在本地进行构建和微调。访问 build.nvidia.com/spark，以获取我用于这些基准测试的剧本和软件堆栈。

<details>
<summary>Original English</summary>

After running all of these, two things stood out to me. On when to use the Jetson Spark. For steady-state workloads, privacy-sensitive data, and rapid prototyping. It allows you to build and fine-tune locally with the exact same software stack used in Jetson cloud. Visit build.nvidia.com/spark to access the playbooks and software stack I used for these benchmarks.

</details>

### 实践指引与工作流展望

并进行一次本地运行，快速迭代，准备就绪后，即可扩展到数据中心或云端。这就是 Jetson Spark 所赋能的工作流程。

<details>
<summary>Original English</summary>

And in one run locally, iterate quickly, and when ready, scale to data center or cloud. That's the workflow that J uses Spark enables.

</details>