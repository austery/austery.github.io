---
author: AI Engineer
date: '2026-05-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TeGsFFNqRLA
speaker: AI Engineer
tags:
  - ai-inference
  - developer-experience
  - prompt-engineering
  - context-management
  - technical-debt
title: 快速模型需要“慢”开发者：AI 时代的开发策略重构
summary: 随着编码模型推理速度实现 20 倍的质的飞跃（如 Codex Spark 达到 1200 token/s），开发者必须从追求‘一次生成、大规模并行’的坏习惯转向实时的‘人机协作’。本文通过硬件层、架构层到开发实践的深度拆解，提出了一个实操手册：利用模型速度优势实现代码验证与自动化重构的零成本化，并强调了在模型生成速度超过人类认知速度时，保持代码质量、 steer 能力以及精确的上下文管理的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cerebras
  - OpenAI
products_models:
  - Codex Spark
media_books: []
status: evergreen
---
### 快速模型带来的开发范式转移

随着推理技术的突破，代码生成速度实现了跨越式发展。**Codex Spark** 等新一代模型达到了 **1200 tokens/s** 的生成速度，相比 Sonnet 或 Opus 等传统主流模型（约 40-60 tokens/s）提升了约 20 倍。

这一变化不仅解锁了新的使用场景，更迫使我们必须重新审视开发工作流。过去为了应对缓慢模型而形成的“坏习惯”（如编写海量 prompt 试图一次成功、直接提交大规模代码块、或者在屏幕上同时运行大量未经验证的代理），在如今的极速生成背景下，正演变成产生大规模“技术债”的工厂。如果不及时纠正这些行为模式，我们正在高速生产高质量的“坏代码”。

<details>
<summary>Original English Source</summary>
Over the past few years, we as developers have developed a series of bad habits when it comes to developing as a result of slow AI code generation. We do things like write massive prompts and try to oneshot. We'll make huge commits or we'll have our 10 agents all on the screen at the same time combulating, coitating, thinking.

About a month ago, we at Cerebrus and OpenAI released a new model, state-of-the-art model called Codex Spark. Codex Spark can generate code at 1,200 tokens per second. To put that into perspective, if you look at the Sonnet family or the Opus family, those can generate code at about 40 to 60 tokens per second. In this new era, as we're starting to see much faster coding models, this is 20 times faster. Not only does it unlock new capabilities and use cases, but it also requires us to rethink how we as developers interact with the coding model.

A lot of these bad habits that we had before that were generating maybe 50 tokens per second of bad code, unless we fix them, they're going to start generating 1,200 tokens per second of bad code.
</details>

### AI 推理栈的技术优化之路

当前模型速度的飞跃源于整个 AI 推理栈（Inference Stack）的协同优化，主要体现在以下几个维度：

*   **硬件层（Hardware）**: 克服“内存墙”（Memory Wall）瓶颈是关键。传统架构中，数据在 CPU/GPU 计算单元与外置 HBM 内存间频繁移动，占据了 50-80% 的延迟。新型方案（如 Cerebras 的 wafer-scale 架构）将内存（SRAM）直接分布式嵌入计算核心旁，实现了极高的内存带宽。
*   **计算架构（Disaggregated Inference）**: 商业化分离了推理的两个阶段：**预填充（Prefill）**和**解码（Decode）**。预填充任务高度并行，适用于计算优化型硬件；解码任务串行且受内存带宽限制，适用于内存优化型硬件。
*   **模型架构（Model Architecture）**: 如 **专家混合模型（Mixture of Experts）**，仅在处理 Token 时激活模型的一小部分专家层，以更小的计算成本获得更大规模模型的智能。此外，通过**结构化剪枝（Pruning）**移除不活跃的专家，进一步减小模型体积。
*   **推理优化（Inference Optimizations）**: **KV Cache 复用**技术显著减少了序列 attention 的重新计算。

<details>
<summary>Original English Source</summary>
It's what many of you probably work on on a day-to-day, but there's so many companies that are working on this problem all at the same time. And as a result, the entire AI inference stack is getting optimized all at once.

One of the biggest things that we have to think about with hardware is the memory wall... And so when we are running inference, we have to constantly move our weights and KV cache values between memory and our actual chip.

What a lot of newer companies are doing are thinking about companies like Cerebrus or Groq, they're thinking about how do we move this memory to be as close to the chip as possible. And so here's an example of the Cerebrus wafer where all of the chip... all the memory is distributed across the chip in SRAM.

Disaggregated inference really has become commercialized in the last few months. In traditional inference, there's two steps: prefill and decode. Prefill is where we're taking every token that the user inputs and processing it, embedding it, and adding it to our KV cache. This is a step that can happen in parallel and so it's compute-bound. Decode on the other hand is where we're actually generating the output token by token and this is sequential and is as we mentioned memory-bound.

What we're doing and seeing now commercially is that we're splitting up these two steps so that prefill is done on one type of hardware that is compute-optimized and decode is done on another piece of hardware that is memory-optimized.

There's so many ways that we are training our models and shaping our models to cater to our hardware. A great example is a very standard model architecture: mixture of experts. Instead of activating the entire model all at once for every single token, we're only activating a subset of experts for every time.

Inference optimizations... one of the biggest things that we're thinking about at this level is KV cache reuse. And so by storing and reusing previously computed token representations, we don't have to recalculate attention over the sequence at every step.
</details>

### 重构开发者行为手册 (Practical Playbook)

面对极速生成的代码，开发者必须从“等待者”转变为“实时协作者”和“严谨的验证者”。

#### 1. 策略性协同 (Orchestration Strategy)
不要试图用单一模型解决所有问题。
*   **模型分工**: 使用更大规模的模型（如 GPT-5.4）执行长周期规划（Planning）；使用 Codex Spark 等极速模型作为高效的执行器（Executor）。
*   **技能化工作流**: 将成功且复杂的任务轨迹转化为可复用的“技能”（Skill），通过固定流程实现验证和自动化循环。

#### 2. “零成本”验证与优化
在极速推理环境下，验证变得几乎无成本。
*   **全面验证**: 必须将测试套件、linting、预提交钩子（Pre-commit hooks）、差异化评审（Diff reviews）和浏览器端 QA 自动化整合到每一环节，而非仅仅在最后进行。
*   **自动重构**: Bake 自动重构流程到开发 workflow 中。在任务完成后，自动执行如删除未使用导入、清理冗余代码、标准化函数结构等操作。

#### 3. 诱导模型生成“品味” (Inducing Taste)
模型本身缺乏品味，但可以通过“Cherry-picking”策略诱导高质量输出。
*   **多版本并行**: 要求模型生成 15 个版本，从中挑选最优解。甚至并行启动 5 个代理生成 75 个版本以进行最终选择。这对于视觉设计、架构方向等价值差异化（Variety）的领域极为有效。

#### 4. 精确的上下文管理 (Context Management)
速度提升后，上下文压缩（Compaction）的时间大幅缩短，sloppy（草率）的实践将导致严重的上下文损耗。
*   **系统化持久化 memory**: 为每个新会话设置四个持久化文件：
    *   **agents.md**: 定义子代理能力。
    *   **plan.md**: 生成任务规划清单。
    *   **progress.md**: 记录已完成与未完成任务，供会话间衔接。
    *   **verify.md**: 每一步的自动验证记录。
*   **Bounded Goals**: 将大型任务切分为较小的、有边界的目标，并避免使上下文充满度达到 80%-100% 从而触发压缩。

<details>
<summary>Original English Source</summary>
A good mental model is to use a larger model like GPT-5.4 for your planning or your long-horizon workflows and then using a faster model like Codex Spark as your actual executor.

Another really helpful trick is to actually make skills out of successful sessions and capture trajectories that are working really well.

At 1,200 tokens per second a model like Codex Spark makes validation basically free. There is no excuse and no reason why you should not be doing things like test suites, linting, pre-commit hooks, diff reviews, browser-based QA automations.

So let's say that I want to code a navbar and I want it to be midnight blue. I want four different icons... what I can do with Codex Spark... I can tell it to generate 15 versions... I can cherrypick the version that I like the best.

Now that the models are so fast, it should not be you spawn a session, you go get a hamburger, you scroll Twitter, and then you come back. Now you can actually sit down and it's a real-time collaboration that you're able to have with this model.

As I was mentioning before, it really shouldn't be, you know, you spawn 10 agents, you never verify the code. You don't know what's happening under the scene... You can be super specific... ban the model from deleting files, give it a max diff size, have the model only read and write.

You can just bake this into your automatic workflow so that after every single task on that checklist is complete, you're just asking the model to automatically delete unused imports, clean up unnecessary lines of code, make it so that all of my functions are structured the same way.

A general very high level framework is just always always break up large tasks into smaller bounded goals.

An example of how you can do this and set up an external memory system that is persistent every time you set up a new session is with this four file system. We have agents.md... plan.md... progress.md... verify.md.
</details>