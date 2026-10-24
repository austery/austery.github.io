---
author: Dwarkesh Patel
date: '2026-04-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xmkSf5IS-zw
speaker: Dwarkesh Patel
tags:
  - model-architecture
  - ml-inference
  - gpu-cluster
  - memory-bandwidth
  - cost-optimization
  - sparse-attention
  - pipeline-parallelism
  - kv-cache
  - feistel-network
title: GPT-5、Claude和Gemini的训练与服务：Reiner Pope深度解析
summary: Reiner Pope深入探讨了大型语言模型（LLM）的训练和推理架构，包括批处理大小对延迟和成本的影响、稀疏专家混合模型、GPU机架内外的通信模式、流水线并行化以及内存容量与带宽的权衡。他解释了API定价如何反映底层硬件成本，并讨论了神经网络与密码学在架构上的相似与不同。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - MatX
  - Google
  - Claude
  - Codex
  - Cursor
  - Jane Street
  - Nvidia
  - OpenAI
  - DeepSeek
products_models:
  - Blackwell
  - NVL72
  - A100
  - H100
  - B100
  - Hopper
  - Rubin
  - Gemma 4
  - GPT-4
  - GPT-5
  - GPT-3
  - GShard
  - Switch Transformer
  - RevNets
media_books: []
status: evergreen
---
### 引言

**Reiner Pope**: 大家好，今天我将采访 **MatX** 的首席执行官 **Reiner Pope**，**MatX** 是一家新的芯片初创公司。他之前在 **Google** 负责 **TPU** 架构和许多其他项目。

<details>
<summary>Original English</summary>

**Reiner Pope**: Today, I'm interviewing Reiner Pope, who is the CEO of MatX, which is a new chip startup. Previously, he was doing TPU architecture and many other things at Google.

</details>

**Dwarkesh**: 这次采访的形式与我往常的采访非常不同。这将是一场黑板讲座。我们马上就要开始了。事实上，我们专门为此形式建造了这个全新的工作室，所以很高兴能和您一起启用它。我们将讨论**模型架构**、**ML**基础设施以及许多其他事情。我认为这是一个重要的话题，因为一旦你了解了集群中训练和推理的工作原理，很多事情——关于为什么 **AI** 会是现在的样子，为什么 **AI** 架构是现在的样子，为什么 **API** 价格是现在的样子，以及为什么 **AI** 进展是现在的样子——都会变得有意义。你需要了解细节才能理解，而你需要一块黑板才能理解细节。**Reiner**，非常感谢您能来。

<details>
<summary>Original English</summary>

**Dwarkesh**: This is a very different format from my usual interviews. This is going to be a blackboard lecture. We're going to get up in a second. We in fact built this whole new studio with specifically this format in mind, so it's a pleasure to get to inaugurate it with you. We're going to be talking about model architecture, ML infra, and many other things. The reason I think it's an important topic is because once you understand how training and inference work in a cluster, a lot of things—about why AI is the way it is, why AI architectures are the way they are, why API prices are the way they are, and fundamentally why AI progress is the way it is—start making sense. You need to understand the details to get there, and you need a blackboard to understand the details. Reiner, thank you so much for doing this.

</details>

**Reiner Pope**: 很高兴来到这里。

<details>
<summary>Original English</summary>

**Reiner Pope**: Very happy to be here.

</details>

**Dwarkesh**: 完全披露一下，我是 **MatX** 的天使投资人，但这与本次播客无关。**Reiner**，为了启动讨论，我将提出这个问题。我们有像 **Claude**、**Codex** 和 **Cursor** 这样的公司，它们提供类似“**快速模式**”的服务，即以 **6** 倍的价格，以 **2.5** 倍的速度为你传输令牌。从机制上讲，我很好奇这里发生了什么。为什么你可以支付更多以获得更快的延迟？其次，你能否继续下去？你能否支付 **100** 倍的费用，以某种方式获得更快的速度？第三，你能否反其道而行之？你能否拥有像 **Claude Code** “**慢速模式**”这样的东西，如果你愿意等待几分钟，你可以获得更便宜的价格？也许这有助于激发您在讲座中进行的分析。

<details>
<summary>Original English</summary>

**Dwarkesh**: Full disclosure, I am an angel investor in MatX, but that's unrelated to this podcast. Reiner, to kick us off I'll ask this question. We have a couple of companies like Claude and Codex and Cursor offering something like Fast Mode, where for 6x the price, they'll stream you tokens at 2.5x the speed. Mechanically, I'm curious what's going on here. Why is it the case that you can pay more to get faster latency? Two, could you keep going? Could you pay 100x more and somehow get much faster speeds? Three, could you go the other way? Could you have something like Claude Code "Slow Mode", where if you are willing to wait for minutes on end, you could get even cheaper prices? Maybe this will help motivate the analysis that you'll be doing through the lecture.

</details>

**Reiner Pope**: 很好。稍微跳到结论，主要影响是**批处理大小**。我们现在要做的是量化这到底是什么样子，以及它对延迟和成本有什么影响。还有另一种效应，你可以称之为**推测解码**或**多令牌预测**。我们稍后再回来讨论，但我们要讲的第一件事是**批处理大小**。我想介绍一下**分析的两个原则**。首先，我们将对如何在芯片集群上运行**Transformer**模型进行**屋脊线分析**（roofline analysis）。我们将使用一个 **Blackwell NVL72** 集群，也就是一个包含 **72** 个 **GPU** 的机架。**屋脊线分析**意味着我们关注**内存带宽**和**计算性能**。另一方面，我们将只关注模型的两个简单因素：**处理权重的时间**，以及**处理上下文**（即 **KV 缓存**）的时间。我们开始吧。我们将尝试估算运行特定形状推理所需的时间。我们在这里并不完美。我们无法精确预测时间，因此我们将进行近似。我们将说时间必须**大于或等于**某个数量。我们将考虑两个不同的方面：**进行内存获取所需的时间**，以及**进行计算所需的时间**。事实证明，即使使用一个简单的模型，这也能给我们提供非常强大的预测能力。

<details>
<summary>Original English</summary>

**Reiner Pope**: Great. To jump to the conclusion a little bit, the big effect is batch size. What we're going to do now is quantify exactly what that looks like and what its implications are on latency and cost. There's another effect, which you can call speculative decoding or multi-token prediction. We can maybe come back to that later, but the first thing that we'll talk through is batch size. What I'd like to introduce is the two principles of analysis. First, we're going to look at a roofline analysis of how we run a transformer model on a cluster of chips. We'll take a Blackwell NVL72 cluster, so a rack of 72 GPUs. The roofline analysis means we look at memory bandwidth and compute performance. The other side of that is that we're going to look at just two simple factors of the model: the time to operate on the weights, and the time to operate on the context, the KV cache. Let's jump in. We're going to try and estimate the time that it takes to run an inference of a certain shape. We're not perfect here. We can't exactly predict the time, so instead we're going to approximate. We're going to say that the time must be greater than or equal to a certain quantity. We're going to consider two different aspects: the time it takes to do the memory fetches, and the time it takes to do the compute. It will turn out that this gives us very strong predictive power, even with a simple model.

</details>

### 计算时间与内存获取时间

**Reiner Pope**: 逐一来看，**计算所需的时间**是多少？在计算中我真正需要做两件事。我需要乘以所有**激活参数**，然后我需要对**注意力**进行一些工作。乘以所有**激活参数**，我有一定的**批处理大小**正在运行，我的模型中有许多**激活参数**。然后我将把这个除以**计算吞吐量**，即芯片的 **FLOPs**。这是一个硬件问题。这包括所有**权重矩阵乘法**的所有计算时间。这里有一个小小的注意事项。我们忽略了进行任何**注意力计算**的时间，但总的来说，与此相比，这部分时间会非常小。所以我们将忽略它。

<details>
<summary>Original English</summary>

**Reiner Pope**: One by one, what is the time that it takes to do the compute? There are really two things I need to do in the compute. I need to multiply by all of the active parameters, and then I need to do some work on the attention. Multiplying by all the active parameters, I have a certain batch size that I'm running, and I've got a number of active parameters in my model. Then I'm just going to divide this by the compute throughput, which is the FLOPs of the chip. This is a hardware concern. This accounts for all of the compute time for all of the weight matrix multiplies. There's a little caveat here. We've ignored the time to do any of the attention computation, but that in general will be quite small in comparison to this. So we'll ignore this.

</details>

**Dwarkesh**: 我会不时打断，问一些非常初级的问题，或者澄清一些基本观点。对于听众来说，你不是一次服务一个用户。**批处理**是指你同时服务许多不同的用户，这是一个完整的批次。

<details>
<summary>Original English</summary>

**Dwarkesh**: I'll just interrupt from time to time to ask some very naive questions or to clarify some basic points. For the audience, you're not serving one user at a time. The batch refers to the fact that you're serving many different users at the same time, and that's a whole batch.

</details>

**Reiner Pope**: 我至少可以稍微解释一下**批处理**的动机。我们将精确地看到为什么**批处理**是一种如此有利的优化。事实证明，如果你不将许多用户批量处理在一起，你获得的成本和经济效益可能会比你批量处理许多用户时**差一千倍**。我们将能够非常明确地看到这一点。然后，是**激活参数**的数量。例如，如果我查看一个 **DeepSeek** 模型，**DeepSeek V3** 模型大约有 **370 亿**个**激活参数**，**7000 亿**个**总参数**。我们只关注那些对单个 **AI** 令牌活跃的参数。我们正在建模计算性能。我将继续写等号，但在所有这些情况下，你可以认为这个时间至少是这么多，也许会有一些我们忽略的项。

<details>
<summary>Original English</summary>

**Reiner Pope**: I can motivate the batch at least a little bit. We will see exactly why batch is such a favorable optimization. What will turn out to be the case is that if you do not batch together many users, the cost and the economics you get can be a thousand times worse than if you do batch many users together. We'll be able to see that quite explicitly. Then, number of active parameters. If I look at, for example, a DeepSeek model, the DeepSeek V3 model has about 37 billion active parameters, and 700 billion total parameters. We're focusing on just the ones that are active for a single AI token. We're modeling compute performance. I'm going to keep writing equals, but in all of these cases, you can think of this time as being at least this much, and maybe there will be some terms we ignored.

</details>

**Reiner Pope**: 在内存方面，我们需要对内存做些什么？我们需要获取所有**权重**，所以需要一些时间来获取**总参数**数量，而不仅仅是**激活参数**。有**权重获取时间**，此外，还有**KV 缓存获取时间**。这实际上取决于**批处理大小**。对于批处理的每个元素，我们都必须获取整个**上下文长度**的令牌，并且每个令牌有一个大小，即一个令牌的字节数。这是一个**模型参数**。

<details>
<summary>Original English</summary>

**Reiner Pope**: On the memory side, what do we need to do with memory? We need to fetch all of the weights, so there is some time to fetch the total number of parameters, not just the active parameters. There's weight fetch time, and then in addition, there's a KV cache fetch time. This actually depends on batch size. For every element of the batch, we have to fetch an entire context length worth of tokens, and there's a size per token, bytes for one token. This is a model parameter.

</details>

**Dwarkesh**: 也许稍微回顾一下，让我们快速解释一下什么是 **KV 缓存**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Maybe just backing up, let's explain what the KV cache is real quick.

</details>

**Reiner Pope**: 当我进行一次**前向传递**时……让我画一下**自回归推理**是如何工作的。这发生在**解码**期间。如果我有一堆**文本令牌**……我画一个**张量**，因为最终令牌被表示为**嵌入维度**中的一个张量。在这个方向上，我有**序列长度**。运行解码的工作是，我必须通过一堆**矩阵乘法**在许多不同的层上运行每个令牌。一般来说，我必须对所有这些令牌进行这项工作。但解码的一个步骤是只在此处生成一个附加令牌。我将要做的是运行一个完整的**前向传递**，乘以整个模型中的所有**权重矩阵**。但随后我有了**注意力机制**，其中这个令牌正在查看所有过去的令牌，它具体在查看什么？它正在查看模型生成的令牌的一些**内部表示**，我们称之为**KV 缓存**。这个单个令牌关注所有令牌历史的过程就是**注意力**。它主要由**内存获取**主导，而不是**矩阵乘法**。所以我们有这里显示的**内存获取量**，然后这当然只是除以**内存带宽**，即**内存字节每秒**。

<details>
<summary>Original English</summary>

**Reiner Pope**: When I do a forward pass… Let me draw how the autoregressive inference works. This is during decode. If I have a bunch of text tokens… I'm drawing a tensor because ultimately the tokens are represented as a tensor in some embedding dimension. In this direction, I have the sequence length. The work of running a decode is that I have to run each token through a whole bunch of matrix multiplies over a bunch of different layers. In general, I'm going to have to do that work over all of these tokens. But one step of decode is to produce just this one additional token up here. What I'm going to do there is run a full forward pass of multiplying by all of the weight matrices in the entire model. But then I've got this attention mechanism where this token is looking at all of the past tokens, and what is it looking at specifically? It is looking at some internal representation that the model has produced of the tokens, and we call that the KV cache. This process of this single token attending to all of the history of tokens is attention. It is mostly dominated by memory fetches rather than matrix multiplies. So we've got the amount of memory that we're fetching shown over here, and then this is of course just divided by the memory bandwidth, so the memory bytes per second.

</details>

### 批处理大小与延迟和成本的关系

**Reiner Pope**: 事实上，这些方程足以让我们画出一些拟合线。我们想看的是对**批处理**的敏感度，然后是**上下文长度**的敏感度（我们将单独绘制）。我们说过，你能获得的最大影响是**批处理大小**中**延迟与成本**的权衡。让我们画出来。我认为我们真正只想画两张图。我们首先在这里画出**批处理大小与时间**的关系图。当我们看它的形状时，我们有一个总和的最大值，然后是另一个项。让我们逐一看看这些项以及它们如何缩放：**计算时间**和**内存时间**，以及它们如何显示。让我们首先看看**计算时间**。这完全是**批处理大小**的线性关系，没有偏移，所以它是一条这样的曲线。这是 **t 计算**。在内存方面，我们这里有一部分只是这个常数，这里有一些基本偏移，这是**权重获取**。最后，我们这里有这个项，它是 **KV 获取**，它在**批处理大小**方面是相当线性的，所以它看起来是那样的。这个加上这个的最大值……让我们至少先画出总和。这两个**内存时间**结合起来，在这条弯曲的斜坡上看起来像这样。然后整体最大值是——我在这里画粗一点——这两条曲线的最大值。

<details>
<summary>Original English</summary>

**Reiner Pope**: In fact, these equations here are enough for us to now draw some fit lines. The things that we'd like to look at are sensitivity to batch, and then also, which we'll draw separately, to context length. We said that the big effect you can get is some trade-off in latency versus cost in batch size. Let's draw them out. I think there are just really two graphs that we want to draw. We'll first draw batch size versus time here. When we look at the shape of this, we've got a maximum of the sum and then another term. Let's look at these terms one by one and how they scale: the time for compute and memory, and how they show up. Let's first look at this compute time. This is just purely linear in batch size with no offset, so it is some curve like this. This is t compute. On the memory side, we've got some portion here that is just this constant in some base offset here, which is the weight fetch. Finally, we have this term here, which is the KV fetch, which is pretty linear in batch size, and so it looks like that. The sum of this plus this maxed with this… Let's at least first draw the sum. The two memory times in conjunction end up looking on this curved slope like this. Then the overall maximum is—I'll draw a little thicker here—the maximum of these two curves.

</details>

**Reiner Pope**: 这意味着什么？这是一张**延迟图**。如果我增加**批处理大小**，最初我对**批处理大小**的依赖性不是很强，所以这里有一个**延迟的下限**。这已经部分回答了问题。对于给定的**硬件配置**——我们可以讨论改变硬件配置——**延迟有一个下限**。仅仅是我需要将所有**总参数**从内存读入芯片，这需要一定的时间。如果我使用所有**内存带宽**，我就不能做得更好了。

<details>
<summary>Original English</summary>

**Reiner Pope**: What does this mean? This is a latency plot. If I grow my batch size, initially I get some not very strong dependence on batch size, so there is some lower bound on latency here. This already partially answers the question. For a given hardware configuration—and we can talk about varying the hardware configuration—there is a lower bound on latency. It is simply that I need to read all of my total parameters from memory into the chips, and that takes a certain amount of time. If I use all of my memory bandwidth, I can't do any better than that.

</details>

**Dwarkesh**: 看来您绘制的**计算时间**斜率和 **KV** 增长的方式——以及 **KV** 对**内存时间**的影响——如果它高于或低于会怎样？是的，这必然是这样吗？如果这总是真的，那么随着**批处理大小**的增长，**计算**总是主导 **KV**，这意味着如果**批处理大小**足够大，**内存**可能永远不是问题。

<details>
<summary>Original English</summary>

**Dwarkesh**: It seems like the way you've drawn the slopes for compute time and how the KV grows—and what implication the KV has on memory time—What if this were above or below? Yeah, is that necessarily the case? If this is always true, then as batch size grows compute always dominates KV, which suggests that if you have a big enough batch size, maybe memory is never an issue.

</details>

**Reiner Pope**: 这对**上下文长度**非常敏感，所以我想我们应该回来探讨一下。当你改变**上下文长度**时，**KV 获取时间**会越来越长，这将导致从**计算受限**过渡到**内存受限**。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is really sensitive to the context length, so I think we should come back and explore this. As you vary the context length, the KV fetch time will go up and up, and that will cause a transition from compute-limited to memory-limited.

</details>

**Dwarkesh**: 斜率与**计算时间**的斜率完全相同，这有什么特别的意义吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Is there something especially significant about the slope being exactly the slope of the compute time?

</details>

**Reiner Pope**: 每当我们有**平衡点**时，它都表示你做得恰到好处。对于斜率匹配的特定**上下文长度**，这意味着我既受**内存限制**又受**计算限制**，这是一个非常理想的状态。

<details>
<summary>Original English</summary>

**Reiner Pope**: Whenever we have balance points, it says that you're getting it exactly right. For the particular context length where the slopes match, that says I am equally memory-bound and compute-bound, which is a really desirable place to be.

</details>

**Dwarkesh**: 这是一个非常简单的代数问题，但假设最佳**上下文长度**是 **10 万**，你增加到 **20 万**。你的 **MFU** 会下降到 **50%** 吗？对 **MFU** 会有巨大的影响吗，如果它稍微偏离最佳**上下文长度**范围，即“**金发区**”？

<details>
<summary>Original English</summary>

**Dwarkesh**: This is a very simple algebra problem, but suppose the optimal is 100K context length, and you go to 200K context length. Does your MFU go down to 50%? Does it have a humongous impact on MFU to be slightly outside of the optimal context length range, the Goldilocks zone?

</details>

**Reiner Pope**: 没错。正如这里所建模的那样，这是真的。这里有一个关键点，我将**内存获取**建模为**上下文长度**的线性关系。这取决于**模型架构**。对于所有具有**密集注意力**的模型架构都是如此。**稀疏注意力**实际上扩展性要好得多。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's right. That is true as modeled here. There is a key point here that I'm modeling the memory fetch as linear in context length. That depends on model architecture. It is true for all of the model architectures with dense attention. Sparse attention actually scales much better than that.

</details>

**Dwarkesh**: 明白了。**稀疏注意力**是大家在实践中使用的吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Got it. Is sparse attention what everybody uses in practice?

</details>

**Reiner Pope**: 我对**稀疏注意力**非常兴奋。很难知道实验室在用什么。**DeepSeek** 已经发布了**稀疏注意力机制**。我只是想提一下，**DeepSeek** 发布的一些关于**稀疏注意力**的论文最终在这个术语中添加了**平方根**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I'm pretty excited about sparse attention. It's hard to know what the labs are using. DeepSeek has published a sparse attention mechanism. I'll just put a plug in that some of the DeepSeek papers that have published sparse attention end up putting a square root in this term.

</details>

**Reiner Pope**: 到目前为止，我们已经讨论了**延迟**。很难从这里读出**成本**。如果我考虑**成本**意味着什么……为了运行这个推理，我将使用 **GPU** 一定秒数，比如一毫秒或 **20** 毫秒。我必须支付那段时间的租金。所以是每 **GPU** 每小时 **2** 美元或类似的价格。这是这个推理的成本，但在那个推理期间我处理了多少令牌？那是**批处理大小**。我们真正想绘制的是**成本与批处理大小**的关系图，即 **t/B** 与**批处理大小**的关系图。这是**每个令牌的成本**。我们必须想象将这三条曲线中的每一条除以 **B**，所以乘以这个倒数。

<details>
<summary>Original English</summary>

**Reiner Pope**: So far, we've looked at the latency. It's hard to read off cost from this. If I think about what cost means… To run this inference, I'm going to use the GPU for a certain number of seconds, like one millisecond or 20 milliseconds. I have to pay the rental time for that time. So it's $2/hour per GPU or something like that. That's the cost of this inference, but how many tokens have I processed during that inference? That is the batch size. What we actually want to plot is the cost versus batch size, which is t over B versus batch size. This is the cost per token. We have to imagine dividing each of these three curves by B, so multiplying by this reciprocal.

</details>

**Reiner Pope**: 结果是……**计算曲线**是线性的。我们除以 **B**，这使得它在这里变成一个常数。这是 **t 计算**。**KV 获取**是线性的，现在它也变成一个常数。然后**权重获取**是常数，现在我们除以 **B**，所以它变成了一个**抛物线**。我们再次计算总和的最大值。这两个项的总和使**抛物线**向上移动。**KV 获取**和**权重获取**的总和给我们一个更高的**抛物线**，像这样。然后我们将在这里取与**计算**的最大值。我们最终得到的是我们关心的整体形状。

<details>
<summary>Original English</summary>

**Reiner Pope**: What we end up with there is… The compute curve was linear. We divide by B, and that makes it a constant here. This is t compute. The KV fetch was linear, and now it becomes a constant as well. Then the weight fetch was constant, and now we've divided by B, so it becomes this parabola. Again, we're going to compute the max of the sum. The sum of these two terms shifts the parabola up. The sum of the KV fetch and the weight fetch gives us a higher parabola that's like this. Then we're going to take the max with the compute here. We end up with this being the overall shape that we care about.

</details>

**Reiner Pope**: 再次，我们看到一些**限制行为**。**成本**最初在**批处理大小**为 **1** 时非常高。它几乎趋于无限，因为我们有如此多的**权重获取**，以至于无法在大的**批处理大小**上分摊。但随着我们增加**批处理大小**，**权重获取**分摊到许多不同的**批处理元素**上，它们的成本变得非常小，最终**计算时间**最终推动了成本。所以**成本**有一个**限制下限**，就是这里的这条线。

<details>
<summary>Original English</summary>

**Reiner Pope**: Again, we see some limiting behavior. The cost initially starts very high at a batch size of one. It almost goes to infinity because we've got so many weight fetches that are not amortized over a large batch size. But as we increase the batch size, the weight fetches become amortized over so many different batch elements that their cost grows very small, and eventually the compute time ends up driving the cost. So there is a limiting lower bound on cost, which is this line here.

</details>

**Dwarkesh**: 所以 **Claude Code Slow** 或 **Codex Slow** 或其他任何东西都只会在这条线上运行。它不会有太大帮助，因为你无法在更大的批处理中分摊 **KV** 值。它们对于每个批处理都是独一无二的。计算对于每个批处理也是独一无二的。那么，在分摊掉所有其他东西之后，你每个批处理可以做的最小工作是什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: So Claude Code Slow or Codex Slow or whatever would just live on this line. It wouldn't help much because you're not able to amortize the KV values over a much bigger batch. They're unique per batch. The compute is also unique per batch. So what is the minimum work you can do per batch after amortizing everything else away?

</details>

**Dwarkesh**: 在实践中，**前沿模型**的**批处理大小**有多大，以至于你不再受**内存带宽限制**？

<details>
<summary>Original English</summary>

**Dwarkesh**: This point where you are no longer memory bandwidth bound, practically how big a batch do you need? How big are the batches practically for frontier models?

</details>

**Reiner Pope**: 你可以解决这个问题。它甚至对**模型架构**不特别敏感。我们继续吧。我们讨论的是当**内存时间**等于**计算时间**时。这就是那个问题。因为我们关注的是**批处理大小**是多少——以及真正的问题是**权重何时分摊到乘法上**——我将专注于比较**权重获取时间**和**权重乘法时间**。我将忽略 **KV 获取**项，只是为了简化分析，这样我们就可以得到一个清晰的答案。我们将把这部分与这两个时间等同起来。

<details>
<summary>Original English</summary>

**Reiner Pope**: You can just solve for that. It's not even particularly sensitive to model architecture. Let's go ahead and do that. What we're talking about is when the memory time is equal to the compute time. That’s what that question is. Because we're focused on what the batch size is—and really there's a question of when the weights are amortized over the multiplies—I'm going to focus on comparing the weight fetch time to the weight multiply time. I'm going to disregard the KV fetch term just to simplify the analysis so we can get a clean answer out. We're going to equate this portion with these two times.

</details>

**Reiner Pope**: 写出来就是，**总参数** **N** 除以**内存带宽**，等于**批处理大小**乘以**激活参数**数量除以**计算性能**。从这里看，上面都是**模型参数**。下面都是**硬件参数**。事实证明，将它们重新排列成**硬件参数**在一边是很好的。这等价于 **FLOPs** 除以**内存带宽**等于**批处理大小**乘以**激活参数**数量除以**总参数**数量。

<details>
<summary>Original English</summary>

**Reiner Pope**: Writing that out, we get N, number of total parameters, over memory bandwidth, is equal to batch size times number of active parameters divided by the compute performance. Looking over here, everything on the top are model parameters. Everything on the bottom are hardware parameters. It turns out to be nice to rearrange them such that we have the hardware parameters on one side. This is equivalent to FLOPs over memory bandwidth being equal to batch size times number of active parameters, divided by the number of total parameters.

</details>

**Reiner Pope**: 这个**硬件参数**最终是一个**无量纲常数**。如果你从 **FLOPs** 的角度来看……它的维度是什么？这是**每秒乘法次数**。这是**每秒字节数**。所以这不完全是**无量纲**的。但你所做的是，你说，每秒有多少 **FP4** 乘法次数乘以每个 **FP4** 是半字节的事实。我实际上可以让这最终成为**无量纲**的。在大多数 **GPU** 上，这最终约为 **300**。

<details>
<summary>Original English</summary>

**Reiner Pope**: This hardware parameter ends up being a dimensionless constant. If you look in terms of FLOPs… What are the dimensions of this? This is multiplies per second. This is bytes per second. So that's not quite dimensionless. But what you do is you say, how many FP4 multiplies per second times the fact that each FP4 is half a byte. I can actually make this end up being dimensionless. On most GPUs, this ends up being somewhere around 300.

</details>

**Dwarkesh**: 随着我们从**模型代际**到**模型代际**，这个比率是否发生了变化，**FLOPs** 持续增加？

<details>
<summary>Original English</summary>

**Dwarkesh**: Has that ratio changed over time as we've gone from model generation to model generation, where the FLOPs keep increasing?

</details>

**Reiner Pope**: 这是一个**硬件参数**。硬件改变了多少？从 **A100** 到 **H100** 到 **B100**，**FLOPs** 大幅增加，**内存带宽**也大幅增加，并且保持了相当稳定。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is a hardware parameter. To what extent has the hardware changed? From A100 to H100 to B100, the FLOPs have increased substantially, the memory bandwidth has also increased substantially, and it has remained reasonably stable.

</details>

**Reiner Pope**: 我们也可以这样表达。这是一个**稀疏度参数**。我甚至可能会稍微不同地表达这一点。让我们完整地解决**批处理大小**。把它移回另一边，我们最终得到**批处理大小**需要**大约 300 乘以稀疏度**。例如，在 **DeepSeek** 中，我激活了 **256** 个专家中的 **32** 个，所以这将是 **DeepSeek** 的 **8**。这实际上给你一个非常准确的实践**估算值**。一般来说，人们会比这稍微大一点。他们不希望正好处于**平衡点**，因为实际效率不如**屋脊线分析**所说的那么好。但你可以取这个值，然后**乘以两到三倍**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We can express this one as well. This is a sparsity parameter. I might even phrase this slightly differently. Let's solve for batch size in total. Moving this back over to the other side, we end up with batch size needs to be bigger than approximately 300 times sparsity. For example, in DeepSeek I activate 32 out of 256 experts, so this would be 8 for DeepSeek. This actually gives you a ballpark which is remarkably accurate to practice. Generally, people will go a little bit larger than this. They don't really want to be exactly at the balance point because real-world efficiencies aren't as good as a roofline analysis would say. But take this and maybe double or triple it.

</details>

**Dwarkesh**: 好的，所以大概是每批 **2000 到 3000** 个令牌。但是如果包括 **KV 缓存**，这意味着**最佳批处理大小**……

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, so it's two to three thousand tokens per batch. But then if you included the KV cache, the implication would be that the optimal batch size...

</details>

**Reiner Pope**: 应该更大。我们解决了**计算时间**等于**内存时间**的等价关系。如果我添加消耗更多**内存带宽**的东西，那么我用于**权重加载**的可用带宽就减少了。我需要增加更多的**内存带宽**，因此也需要增加更多的**批处理大小**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Should grow larger. We solved for the equivalence between when compute time is equal to memory time. If I add in something that consumes more memory bandwidth, then I have less available for the weight loads. I need to grow the memory bandwidth more, and therefore the batch size more.

</details>

**Dwarkesh**: 这看起来非常小。这会**少于一个序列**，对吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: This seems incredibly small. This would be less than one sequence, right?

</details>

**Reiner Pope**: 请记住，我谈论的是我正在生成**一个额外令牌**的令牌数量。实际上是 **2000** 个唯一的序列。

<details>
<summary>Original English</summary>

**Reiner Pope**: Keep in mind that I'm talking about the number of tokens that I'm generating one more token for. It's actually 2,000 unique sequences.

</details>

**Dwarkesh**: 明白了。

<details>
<summary>Original English</summary>

**Dwarkesh**: Got it.

</details>

**Reiner Pope**: 我们只是在这些序列上进行**一次前向传递**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We're just talking about a single forward pass on these sequences.

</details>

**Dwarkesh**: 你把**批处理**看作是**序列的数量**。

<details>
<summary>Original English</summary>

**Dwarkesh**: You think of the batch as the number of sequences.

</details>

**Reiner Pope**: 没错。

<details>
<summary>Original English</summary>

**Reiner Pope**: That’s right.

</details>

**Dwarkesh**: 当我准备面试时，我经常与该领域的专家交流。所以对于 **Reiner**，我与 **Jane Street** 的两位工程师 **Clark** 和 **Axel** 聊过。**Clark** 负责低延迟交易系统，他向我解释了为什么 **Jane Street** 使用 **FPGA** 来确保他们拥有**可预测的纳秒级延迟**。“你可以很容易地构建这些巨大的计算网格，它们完全符合你的需求，可以触及 **100 兆字节**的 **SRAM**，然后非常容易地在**几十纳秒**内获得响应。这在 **CPU** 上基本上是不可能的。”他接着解释了为什么 **CPU** 根本不适用于这种类型的事情。“所以如果你的时钟每三纳秒跳动一次，你实际上一次有**几字节**的信息来做决定。这与 **CPU** 不同，**CPU** 会收集整个数据包，比如 **1500 字节**的数据包，然后说，好的，这个数据包准备好了。你拿去吧，**CPU**。你现在可以开始考虑它了。”**FPGA** 允许你**在数据包到达的最早部分做出反应**，而不必等待整个数据包。我们还讨论了**液冷**、**网络设计**以及许多其他事情。如果你对这些感兴趣，**Jane Street** 正在招聘。你可以在 **JaneStreet.com/Dwarkesh** 查看他们的空缺职位。如果你想观看完整的准备对话，我们也发布在那里了。

<details>
<summary>Original English</summary>

**Dwarkesh**: When I'm prepping for interviews, I often talk to experts in the field. So for Reiner, I chatted with two of Jane Street's engineers, Clark and Axel. Clark, who works on low latency trading systems, walked me through why Jane Street uses FPGAs to make sure that they have predictable nanosecond latencies. “You can just build these like giant grids of compute very easily that do exactly what you need that touch a hundred megabytes of SRAM and then get your response back in tens of nanoseconds very easily. And that's basically impossible on a CPU.” He then went on to explain why CPUs just wouldn't work for this kind of thing. “And so if you have a clock that's going every three nanoseconds, you actually have several bytes of information at a time to make your decision. That's as opposed to a CPU where you'll just collect up a whole packet, you know, let's say a 1500-byte packet, and then you say, okay, this packet's ready. Here you go, CPU. You can start thinking about it now.” FPGAs allow you to react to the earliest part of the packet as it arrives, rather than having to wait for the full thing. We also talked about liquid cooling, network design, and many other things. If you're interested in this stuff, Jane Street is hiring. You can check out their open roles at JaneStreet.com/Dwarkesh. And if you want to watch the full prep conversation, we posted it there too.

</details>

**Dwarkesh**: 如果你有一个**前沿模型**并且你正在进行推理，他们肯定有超过 **2000** 个并发用户。**批处理**必须填满，这是否会增加额外的延迟？或者如果你有合理数量的用户，不太可能需要 **100 毫秒**才能填满接下来的 **2000** 个插槽？

<details>
<summary>Original English</summary>

**Dwarkesh**: If you've got a frontier model and you are actually doing inference, surely they must have more than 2,000 concurrent users. Is there any added latency from the fact that you need to have the whole batch fill up? Or if you have a reasonable amount of users, is it so unlikely that it would take you 100 milliseconds to fill up the next 2,000 slots?

</details>

**Reiner Pope**: 思考这个问题的方式是：作为模型，**火车何时发车**？假设我选择了一个我将运行的**批处理大小**。顺便说一下，这个交点和这里是同一个交点。我选择这个**批处理大小**，我知道它将花费，例如 **20 毫秒**，这是一个常见的落点。这是 **GPU** 上运行的时间线。它将**每 20 毫秒**启动一个新批次，无论如何。你可以把它看作是**火车时刻表**。**每 20 毫秒**就有一列新火车发车。任何准备好的乘客都会上车。如果火车满员，他们会等到下一班。如果火车不满员，火车也会发车。就这对于**排队延迟**意味着什么而言，最坏的情况是请求在火车发车后立即到达。它必须等待下一班火车，所以最多需要 **20 毫秒**，然后它必须等待那班火车完成。所以最坏情况下的延迟是 **40 毫秒**。

<details>
<summary>Original English</summary>

**Reiner Pope**: The way to think about this is: when does the train depart, as a model? Let's say I've picked a batch size that I'm going to run at. By the way, this intersection point is the same intersection point here. I pick this batch size, and I know that it's going to take, for example, 20 milliseconds, which is a common place this ends up landing. This is a timeline of what is running on the GPU. It's going to start a new batch every 20 milliseconds regardless. You can think of this as a schedule for the train. A new train departs every 20 milliseconds. Any passengers who are ready board the train. If the train is full, they wait until the next train. If the train is not full, the train is going to go anyway. In terms of what that means for queuing latency, the worst case is that a request arrives just after the train departed. It has to wait for the next train, so that's up to 20 milliseconds, and then it has to wait for that train to complete. So the worst-case latency is 40 milliseconds.

</details>

**Dwarkesh**: **20 毫秒**是如何得出的？

<details>
<summary>Original English</summary>

**Dwarkesh**: How is the 20 milliseconds derived?

</details>

**Reiner Pope**: 这是一个经验法则，但它来自哪里尚未完全解释。到目前为止，我们只关注了**内存带宽**和**计算时间**。当我们查看内存时，另一个考虑因素是**我们希望使用我们拥有的所有内存容量**。通常，我们将使用所有这些**内存容量**来**存储权重或 KV**。在进行**前向传递**时，我们希望将所有**内存容量**读入芯片。那就是**容量除以带宽**。在许多不同代的 **HBM** 上，这往往是 **20 毫秒**。

<details>
<summary>Original English</summary>

**Reiner Pope**: It's a rule of thumb, but where it comes from is not fully explained yet. So far we've focused on memory bandwidth and compute time. When we look at memory, the other consideration is that we want to use all of the memory capacity we have. Generally, we're going to use all of that memory capacity to store the weights or the KVs. In the time of doing a forward pass, we want to read all of the memory capacity into the chip. That is capacity divided by bandwidth. That tends to be 20 milliseconds on many different generations of HBM.

</details>

**Dwarkesh**: 单位是合理的。你将拥有**字节除以每秒字节数**。

<details>
<summary>Original English</summary>

**Dwarkesh**: The units make sense. You would have a byte divided by bytes per second.

</details>

**Reiner Pope**: 例如，在 **Rubin** 这一代，它大约是 **288 千兆字节**除以 **20 太兆字节每秒**。这大约是 **15 毫秒**。

<details>
<summary>Original English</summary>

**Reiner Pope**: For example, on the Rubin generation, it is something like 288 gigabytes divided by 20 terabytes per second. This comes out to about 15 milliseconds.

</details>

**Dwarkesh**: 让我确定我理解了这是什么意思。我理解单位分析。它的意思是**我们可以在这段时间内清空并替换 HBM**。所以我们不想处于这样的情况，即 **HBM** 不够大，以至于我们无法真正写入我们想要的一切或从中取出一切。或者我们不想处于这样的情况，即我们读写的能力与……

<details>
<summary>Original English</summary>

**Dwarkesh**: Let me make sure I understand what this is saying. I understand the unit analysis. What it's saying is we can evacuate and replace the HBM in this amount of time. So we don't want to be in a situation where the HBM is not big enough that we're not actually able to write everything we want to it or take everything out of it. Or we don't want to be in a situation where our ability to write back and forth is so small compared...

</details>

**Reiner Pope**: 有两种情况。为什么我们不选择一个**大于 15 毫秒**的延迟？如果我思考这意味着什么，它意味着我实际上有时间**两次读取 HBM**。顺便说一下，大多数 **HBM** 访问都是读取，而不是写入。它几乎都是读取，因为**权重矩阵**是只读的，而且几乎所有的 **KV 缓存**访问都是读取。大约 **30 毫秒**内，我可以**两次读取所有 HBM**，但这有什么意义呢？我不想**两次读取权重矩阵**。我不想**两次读取 KV**。

<details>
<summary>Original English</summary>

**Reiner Pope**: There are sort of two scenarios. Why don't we pick a latency that is bigger than 15 milliseconds? If I think about what that means, it means I actually have time to read the HBM twice. By the way, most HBM accesses are reads, not writes. It's almost all reads because the weight matrices are read-only, and almost all of the KV cache accesses are reads. In around 30 milliseconds, I can read all of HBM twice, but what's the point of that? I don't want to read the weight matrices twice. I don't want to read the KVs twice.

</details>

**Dwarkesh**: 很有道理。几个快速问题。如果**最佳批处理大小**是 **2000** 左右，它完全取决于**稀疏度**，不取决于**模型大小**或其他任何东西。

<details>
<summary>Original English</summary>

**Dwarkesh**: Makes a ton of sense. A couple of quick questions. If it is the case that the optimal batch size is something like 2,000, it's totally dependent on the sparsity, not dependent on the model size or anything.

</details>

**Reiner Pope**: **稀疏度**体现在**模型大小**中，但除此之外，它只取决于**稀疏度**，不取决于**规模**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Sparsity shows up in model size, but beyond that, it only depends on sparsity, not on scale.

</details>

**Dwarkesh**: 这是一个非常有趣的结果。一个问题是，**推理批处理**的**规模经济**会推动**集中化**多少？但这似乎不是什么大问题。**2000** 个用户同时进行算多吗？似乎不多。

<details>
<summary>Original English</summary>

**Dwarkesh**: That's a very interesting result. One question is how much of a push towards centralization is it that you would have these economies of scale from inference for batching? But it seems like it's not that big a deal. Is 2,000 users at the same time a lot? It doesn't seem like a lot.

</details>

**Reiner Pope**: 我们可以对此进行一些分析。你可以从**用户数量**的角度来思考，但更有效的方式是**每秒令牌数**。这个**批处理大小**对于系统的**每秒令牌数**意味着什么？**每秒令牌数**将等于**批处理大小**。我们每隔一段时间间隔运行一个批次的令牌，这个间隔等于 **15 毫秒或 20 毫秒**。这最终是**批处理大小**乘以大约 **60**，所以是 **64 x B**。这最终大约是 **2000 x 64**，即 **128,000 个令牌每秒**。这以更容易理解的单位表示。很难推断并发用户，但一个系统的**全球流量**是多少？当你看到一些公告时，有时 **API 提供商**会吹嘘他们有多少流量。我记得去年 **Gemini** 的一些公告中的数字是**全球每秒数亿个令牌**。这只是其中的**千分之一**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We can do a bit of analysis on this. You can think of it in terms of number of users, but a more productive way to think of it is in terms of tokens per second. What does this batch size mean in terms of tokens per second of the system? Tokens per second is going to be equal to the batch size. We run a batch of tokens, and we do that every time interval, which is equal to the 15-millisecond or 20-millisecond number. This ends up being batch size times about 60, so 64 x B. This ends up being around 2,000 x 64, so 128,000 tokens per second. This is in more digestible units. It's hard to reason about concurrent users, but what is the global traffic for a system? When you look at some of the announcements, sometimes the API providers will brag about how much traffic they have. The numbers I remember from some announcements of Gemini last year were in the hundreds of millions of tokens per second worldwide. This is one-thousandth of that.

</details>

**Dwarkesh**: **Gemini** 很大。**Gemini** 的千分之一也很大。

<details>
<summary>Original English</summary>

**Dwarkesh**: Gemini is big. One-thousandth of Gemini is a lot.

</details>

**Reiner Pope**: 为了真正在规模上具有竞争力，你需要能够服务至少**千分之一的 Gemini**。

<details>
<summary>Original English</summary>

**Reiner Pope**: To actually be competitive at scale, you need to be able to serve at least one-thousandth of Gemini.

</details>

**Dwarkesh**: 这很有趣。**稀疏度**越高，所需的计算就越少。根据这个分析，**批处理大小**越大，**计算**似乎最终会成为瓶颈。那么问题是，**稀疏度**能达到多高？随着**稀疏度**的增加，即**激活参数**相对于**总参数**的比例越小，模型的性能会下降多少？它的下降速度是否比通过增加**稀疏度因子**节省的计算速度更快？

<details>
<summary>Original English</summary>

**Dwarkesh**: That's interesting. The more sparsity you have, the less compute you need. It does seem that as batch sizes get bigger, compute ends up being the bottleneck, according to this analysis. Then the question is, how far can you take sparsity? As the sparsity ratio increases, as you have fewer active parameters relative to total parameters, how much is the performance of the model degrading? Is it degrading faster than you're saving compute by increasing the sparsity factor?

</details>

**Reiner Pope**: 你指的是**模型质量**，而不是**模型速度**。不幸的是，我们无法通过分析来回答这个问题。这是一个关于**模型质量**的经验问题。我能做的最好的就是找一篇论文，然后通过经验来回答。

<details>
<summary>Original English</summary>

**Reiner Pope**: You mean the quality of the model, rather than the speed of the model. Unfortunately, we're not able to answer that analytically. That is an empirical question of model quality. The best I can do is pull up a paper and answer that empirically.

</details>

**Dwarkesh**: 我们现在要找论文吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Should we pull up the paper now?

</details>

**Reiner Pope**: 这篇论文是《**路由语言模型的统一缩放定律**》（Unified Scaling Laws for Routed Language Models）。以现在的标准来看，这是一篇有点老的论文，但他们研究的一个问题是，如果我持续增加**稀疏度**，对**模型质量**有什么影响？这个答案对**专家混合**的实际选择非常敏感。**专家混合**已经存在了很长时间，甚至可能早在 **2017 年**就有了，但技术已经发生了很大变化。**DeepSeek** 的**专家混合**是其工作方式的一个重大改变。还有更早的论文，比如 **GShard** 和 **Switch Transformer**。实际的经验结果将取决于所有这些。

<details>
<summary>Original English</summary>

**Reiner Pope**: This paper is "Unified Scaling Laws for Routed Language Models." It's a somewhat old paper by this stage, but one of the things they looked at is if I keep increasing sparsity, what is the model quality impact? This answer is very sensitive to the actual choice of mixture of experts. Mixture of experts has been around for a really long time, maybe even back in 2017, but the techniques have changed a lot. DeepSeek's mixture of experts was a big change in how it worked. There have been older papers, like GShard and Switch Transformer. The actual empirical results are going to depend on all of that.

</details>

**Reiner Pope**: 在这里显示的一种旧技术上，你可以看到如果我将**激活参数**的数量保持在一个特定大小不变，然后我增加**稀疏度**（他们称之为**专家计数**），**质量会持续增加**。如果你想象从 **1.3B 密集**模型画一条水平线，你会发现在这种情况下，**64** 个专家、**3.7 亿**个**激活参数**的模型与一个**密集型 13 亿**参数模型一样好。所以从某种意义上说，这实际上并不是惊人的回报，你可能需要将**总参数**增加一百倍才能获得相当于**十倍激活参数**的效果。甚至更多。对于效率的适度提升，**参数数量却巨大增加**。

<details>
<summary>Original English</summary>

**Reiner Pope**: On one of the older techniques shown here, you can see if I hold constant the number of active parameters at a certain size, and then I increase the sparsity, which they call expert count, the quality keeps increasing. If you imagine drawing a horizontal line from 1.3B dense across, you end up seeing that, in this case, the 64-expert 370-million activated parameter model is as good as a dense 1.3-billion model. So in some sense, it's actually not amazing returns where you need to increase total parameters a hundredfold to get the equivalent of 10x as many active parameters. Actually even more so. It's a huge increase in parameter count for a modest increase in efficiency.

</details>

**Dwarkesh**: 所以在这种情况下，实际上是 **4** 倍？

<details>
<summary>Original English</summary>

**Dwarkesh**: So in this case, actually it's 4x?

</details>

**Reiner Pope**: **64** 倍换来 **4** 倍。所以虽然通过增加**稀疏度**可以节省计算时间，这似乎是一个值得做的权衡。但如果你每次将**稀疏度**加倍，**计算时间**减少 **2** 倍，然后这部分增加 **8** 倍……这到底是好是坏呢？

<details>
<summary>Original English</summary>

**Reiner Pope**: 64x for 4x. So while it is true that you get this benefit of being able to economize on your compute time if you increase sparsity, naively it would seem like a trade-off worth making. But if you're decreasing this by 2x and then having this go up by 8x every time you double sparsity... Is that good or bad, actually?

</details>

**Reiner Pope**: 即使从**内存**的角度来看……请记住你正在将这部分**内存获取**加倍，这部分获取是通过**批处理**分摊的。所以只需继续运行更大的**批处理大小**。从我们这里所做的分析来看，这是一个**纯粹的胜利**。一直这样做，直到用完可用的用户为止。

<details>
<summary>Original English</summary>

**Reiner Pope**: Even from a memory point of view… Keep in mind you are doubling this portion of the memory fetches, which is amortized by batch. So just keep running a larger batch size. From the point of view of the analysis we've done here, this is a pure win. Keep doing it until you run out of available users, basically.

</details>

**Reiner Pope**: 存在这样的等价关系，如果我有很多用户，我可以使用**稀疏度**更高的模型。从这个角度来看，这是一个合理的权衡。这里出现的另一个权衡是它还会**消耗内存容量**。我们在这里只讨论了**内存带宽**，但它也**消耗内存容量**。

<details>
<summary>Original English</summary>

**Reiner Pope**: There's this equivalence where if I have a lot of users, I can go to a much sparser model. From that point of view, it's a reasonable trade-off. The other trade-off that shows up here is that it also consumes memory capacity. We've only reasoned about memory bandwidth here, but it also consumes memory capacity.

</details>

**Dwarkesh**: 我明白了。

<details>
<summary>Original English</summary>

**Dwarkesh**: I see.

</details>

**Dwarkesh**: 让我确保我理解了。你的意思是**我们想花更少的时间计算**，因此我们做更多**稀疏度**。为了实现这一点，我们需要更大的**批处理大小**。这意味着我们需要更多的**内存容量**才能拥有更多的**稀疏度**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Let me make sure I understood. You're saying we want to spend less time computing, therefore we do more sparsity. To make that work, we need bigger batch sizes. Which means we need more memory capacity to have more sparsity.

</details>

**Reiner Pope**: 也许这会是一个很好的点，讨论一下**专家混合层**通常是如何在 **GPU 机架**上布局的。

<details>
<summary>Original English</summary>

**Reiner Pope**: Maybe this would be a good point to talk about how a mixture of experts layer is typically laid out on a rack of GPUs.

</details>

**Dwarkesh**: 好的。有道理。

<details>
<summary>Original English</summary>

**Dwarkesh**: Cool. Makes sense.

</details>

### 专家混合层与并行策略

**Reiner Pope**: 我们刚才在哪里？**稀疏专家混合**。也许我们如何在 **GPU** 上布局它。让我们首先放大**专家混合层**，画出它的样子。通常，我们会有一个**路由器层**，它决定将令牌路由到哪里。令牌从这里进来，它们通过**路由器层**，然后我们有许多不同的专家。我再画几个来排队。**路由器**将决定路由到哪些专家，并且它将是一小部分，也许是 **32** 个中的 **1** 个。也许它会决定路由到这个，也许是这个，也许是这个。每个**专家**本身都是一个正常的 **MLP**。它有一个**上投影**，然后是一个带有**非线性**的**下投影**。然后最后，我们做**逆向操作**。我们在这里广播东西，我们将它们带回来并求和。像这样带进来。然后最后，我们有**残差连接**。令牌也通过这里，并被添加到 **MoE 层**的结果中。这是一个正常的 **MoE 层**。我想讨论的是它如何映射到 **GPU 机架**以及这对**通信**意味着什么，因为我认为这将开始显示我们**稀疏度**能达到多高的限制。

<details>
<summary>Original English</summary>

**Reiner Pope**: Where were we? Sparse mixture of experts. Maybe how we lay that out on a GPU. Let's zoom in on the mixture of experts layer first and draw what that looks like. Typically, we'll have some kind of a router layer, which is making the decision of where we route the tokens to. We get tokens coming in here, they go through a router layer, and then we have a bunch of different experts. I'll draw a few more to line some up. The router will make a decision of which experts it's going to route to, and it will be a small fraction of them, maybe 1 in 32. Maybe it will make a decision to route to this one, maybe this one, and maybe this one. Each expert itself is a normal MLP. It has an up projection and then a down projection with a nonlinearity in between. Then finally, we do the inverse operation. Where we were broadcasting things out here, we're going to bring them back in and sum them up. Bringing them in like this. Then finally, we have our residual connections. The token is also passed through here, and it gets added to the result of the MoE layer. This is a normal MoE layer. What I want to talk through is how this is mapped to a GPU rack and what this means for communication, because I think this will start to show some of the limits of how sparse we can go.

</details>

**Reiner Pope**: 这里的标准做法，也是最好的解决方案，是使用**专家并行**。这意味着**不同的专家位于不同的 GPU** 上。如果我们以 **DeepSeek** 模型为例，他们有 **256** 个专家。假设我们想在 **Blackwell** 机架上运行它。有 **72** 个 **GPU**。我们有一个**可分割性问题**。这不是 **2** 的幂。我们只是简化一下，说我们只使用其中的 **64** 个。忽略另外八个。这不是什么大问题。所以我们每个 **GPU** 有**四个专家**。非常简单。为了图示方便，实际上我们只说每个 **GPU** 有**两个专家**。我们最终只是放置这些 **GPU 边界**。每对专家都位于自己的 **GPU** 上。然后我们可以查看**通信成本**。我们在这里集中存储了一些令牌。它们被路由到所有这些专家，这里支付了一些**通信成本**。在输出端也支付了相同的**通信成本**。希望这不会成为**通信限制**。

<details>
<summary>Original English</summary>

**Reiner Pope**: The standard practice here, and it is the best solution, is to use expert parallelism. That means different experts go on different GPUs. If we take something like a DeepSeek model, they have 256 experts. Let's say we want to run that on a Blackwell rack. There are 72 GPUs. We have a divisibility problem. This is not a power of two. We'll just simplify and say we're only going to use 64 of them. Just ignore the other eight. It's not a big deal. So we have four experts per GPU. Very simple. For the sake of the diagram, actually let's just say we have two experts per GPU. We end up just putting these GPU boundaries. Every pair of experts is on its own GPU. Then we can look at the communication cost. We had some tokens stored centrally here. They get routed to all of these experts, and there is some communication cost paid here. There's the same communication cost paid on the output. The hope is that this does not become communication limited.

</details>

**Reiner Pope**: 那么这里的**流量模式**是什么？这里的**流量模式**是任何 **GPU** 都将与任何其他 **GPU** 通信，这取决于模型所做的决策。这是一个**全对全的流量模式**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Now what is the traffic pattern here? The traffic pattern here is that any GPU will be talking to any other GPU, depending on the decisions made by the model. This is an all-to-all traffic pattern.

</details>

**Dwarkesh**: 当你提到“**任何 GPU**”时，你是指**路由器**不止一个 **GPU** 吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: When you say any GPU in the pre-tense, the router is more than one GPU?

</details>

**Reiner Pope**: 我把它画成了一个**路由器**。实际上，你会有很多**路由器**的副本，事实上，你会有和 **GPU** 数量一样多的**路由器**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I drew this as one router. In reality, you would actually have many copies of the router, and you would have as many routers as GPUs, in fact.

</details>

**Dwarkesh**: 作为传入流量。

<details>
<summary>Original English</summary>

**Dwarkesh**: As the incoming traffic.

</details>

**Reiner Pope**: 是的。这些是 **64** 个 **GPU**，这些也是 **64** 个 **GPU**。实际上是相同的 **GPU**，我们只是将它们分开绘制，因为它们服务于不同的目的。所以在这个时候，任何 **GPU** 都可以向任何其他 **GPU** 发送数据。这种**全对全的通信模式**，以及 **Blackwell** 机架的配置方式，非常适合 **MoE** 实际希望执行的**通信模式**。然而，如果你认为一个机架太慢，我想用两个机架，那么我就会面临这样的挑战，也许我在这里外面画了一个**机架边界**，在两个机架中，我不再拥有所有 **GPU** 之间的**全对全通信**。**机架间通信**最终成为一个重要的瓶颈。这里的根本问题是**一个机架限制了你可以做的专家层的规模**。这一直是推动**更大互连域**发展的一部分。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah. These are 64 GPUs and these are 64 GPUs. It's actually the same GPUs, we just draw them as separate because they're serving different purposes. So at this point, any GPU can be sending to any other GPU. This all-to-all pattern of communication that shows up and how the Blackwell racks are configured is a perfect fit for the communication pattern that the MoE actually wants to do. However, if you think maybe one rack is too slow and I want to do two racks, then I have this challenge that maybe I've got some sort of rack boundary drawn outside here like this, and I no longer have all-to-all communication between all the GPUs in two racks. The rack-to-rack communication ends up being a substantial bottleneck. The fundamental thing here is that one rack bounds the size of an expert layer you can do. This has been part of what's been driving towards larger and larger interconnect domains.

</details>

**Dwarkesh**: 在我们继续之前，您不妨解释一下**机架**究竟是什么。**机架内**和**机架之间**的**带宽差异**，以及**机架内**与**机架外**通信的**全对全与非全对全**性质。

<details>
<summary>Original English</summary>

**Dwarkesh**: Before we continue, it may be worth you explaining what exactly a rack is. The differences in bandwidth between a rack and within a rack, and the all-to-all versus not all-to-all nature of communication within versus outside.

</details>

**Reiner Pope**: 在这里，**Nvidia** 和 **Google** 以及包括我们在内的其他公司之间，它开始变得非常不同。通常，一个**机架**是一个物理结构。它有几米高，一米或两米宽，具体取决于配置，它存储一些 **GPU** 或 **XPU**，通常大约是 **64** 个。限制它达到一定尺寸的是**供电**、**重量**和**散热能力**。在许多情况下，由于这些物理限制，它最终会达到这个尺寸。当我部署一个**数据中心**时，一个数据中心可能有数千个这样的机架。我有一个这样的高机架，里面有许多 **GPU** 等等。然后我把另一个机架放在它旁边。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is a place where it starts to be very different between Nvidia, for example, and Google, and then others, including us. Generally, a rack is a physical structure. It's a few meters tall, a meter or two wide, depending on configuration, and it stores some number of GPUs or XPUs, which is typically about 64. What constrains it being a certain size is power delivery, weight, and cooling ability. It ends up being about this size in many cases because of these physical constraints. When I deploy a data center, a data center may have thousands of these racks. I've got one of these tall racks, it's got a bunch of GPUs in it, and so on. And then I put another rack next to it.

</details>

**Dwarkesh**: 你说得好像很容易。

<details>
<summary>Original English</summary>

**Dwarkesh**: You make it sound so easy.

</details>

**Reiner Pope**: 没错。我只是把它们放进去。在 **Nvidia** 的情况下，**通信拓扑**……他们实际上把 **GPU** 放在机架的外面，然后把这些**交换机**放在机架的里面。结果是这里有一套**交换机**。这些是 **NV** 交换机。然后他们连接了许多电缆。每个 **GPU** 都有电缆连接到中间的**交换机**。**交换机**与所有 **GPU** 都有连接。所有 **GPU** 都可以通过两次跳跃与其他 **GPU** 通信：到**交换机**，再到另一个 **GPU**。现在，当我想离开机架时，我最终会通过一条不同的路径。**GPU** 也有更慢的连接，通常慢约**八倍**。我在这里用绿色绘制的是 **NVLink**。更广义地说，它被称为**横向扩展网络**。你通常还会有一个**纵向扩展网络**，它允许你连接到某个**数据中心交换机**。所有 **GPU** 都将与某个地方的某个**数据中心交换机**建立连接。这是**纵向扩展**，它的**带宽**通常慢约**八倍**。如果你想在两个机架之间布局**专家混合层**，挑战在于这里一半的 **GPU** 会想要与这里的 **GPU** 通信。平均而言，当我查看这些 **GPU** 上的令牌想要去哪里时，一半的令牌想要留在机架内。这很好。它们可以使用快速的**横向扩展网络**。但一半的令牌会想要离开机架并去到另一个机架，那就不太好了。它们需要使用更慢的网络，因此这成为**全对全模式**的瓶颈。

<details>
<summary>Original English</summary>

**Reiner Pope**: Right. I just drop them in. In Nvidia's case, the communication topology… They actually put the GPUs on the outside of the rack, and then they put these switches on the inside of the rack. What this ends up being is that there's a set of switches in here. These are the NV switches. Then they run a bunch of cables. Every single GPU has cables going to the switches in the middle. The switches have connections to all the GPUs. All of the GPUs can talk to all the other GPUs in just two hops: going to the switch, going to the other GPU. Now, when I want to leave the rack, I end up going via a different path. The GPUs also have a much slower connectivity, which is typically about eight times slower. The green that I drew here in the GPU cases is the NVLink. More generally, it's called the scale-up network. You will typically also have a scale-out network, which allows you to connect to some data center switch. All of the GPUs will have some connectivity up to some data center switch somewhere. This is the scale-out, and it tends to be about 8x slower in bandwidth. The challenge, if you want to lay out a mixture of experts layer across two racks, is that half of the GPUs here are going to be wanting to talk to the GPUs here. On average, when I look at where the tokens on these GPUs want to go, half of the tokens want to go inside the rack. That's great. They can use the fast scale-up network. But half the tokens are going to want to leave the rack and go to the other rack, and that's not as good. They need to use a much slower network, and so that becomes the bottleneck on the all-to-all pattern.

</details>

**Reiner Pope**: 另一种选择是，为什么我不能在这里有一个更大的**交换机**，并将所有东西连接到一个实际将两个机架组合在一起的更大的**交换机**呢？这个方向有很多想法，但总的来说，你拥有这种**交换机层次结构**而不是一个大**交换机**的原因是为了**管理电缆拥塞**。你只需要连接大量的电缆。

<details>
<summary>Original English</summary>

**Reiner Pope**: A different choice would be, why don't I have a big switch here and connect everything to a much bigger switch that actually combines the two racks together? There are many ideas in this direction, but in general, the reason you have this hierarchy of switches rather than one big switch is to manage the cabling congestion. You just need to run a large number of cables.

</details>

**Dwarkesh**: 抱歉，您刚才问的问题基本上是，为什么它不能更大规模地扩展？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, is that question you just asked basically, why isn't it a bigger scale-up?

</details>

**Reiner Pope**: 没错。为什么不能有**一百万个芯片**进行**纵向扩展**或**一千个芯片**？是什么变化使得 **Nvidia** 能够从 **8** 个 **Hopper** 发展到 **72** 个 **Blackwell**，而现在 **Rubin** 将是……是 **500** 多个吗？

<details>
<summary>Original English</summary>

**Reiner Pope**: Exactly. Why not just have a million chips in scale-up or a thousand chips? What has changed that has allowed Nvidia to go from Hopper, which was 8, then Blackwell is 72, and now Rubin will be... is it 500 something?

</details>

**Reiner Pope**: 是的，**500** 多个。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah, 500 and something.

</details>

**Reiner Pope**: 从 **Hopper** 到 **Blackwell** 主要只是从托盘作为**外形尺寸**转换为机架作为**外形尺寸**的决定。这是一个产品决策。那里没有实质性的技术障碍。从 **64** 个切换到 **500** 个左右，其中有一些 **Jensen** 的数学计算，但至少有真正的 **4** 倍增长，这来自于一个更加复杂和困难的机架设计。这实际上是一种新的物理设计，可以连接更多的电缆。

<details>
<summary>Original English</summary>

**Reiner Pope**: From Hopper to Blackwell is mostly just the decision to switch from trays as the form factor to switching to racks as the form factor. That's a product decision. There wasn't a substantial technical barrier there. Switching from 64 to 500 or so, there's a bit of Jensen math there, but there is at least a genuine 4x increase, which is coming from a much more complicated and difficult rack design. That is actually a new physical design to run more cables.

</details>

**Dwarkesh**: 电缆的复杂性仅仅是弄清楚哪根电缆跳到哪根，或者哪个信号从哪个地方到哪个地方的成本吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: The cable complication is just the cost of figuring out which cable hops to which, or which signal goes from what to what?

</details>

**Reiner Pope**: 让我们放大这一点，看看**线密度**。我再画一次这个图，这样我们就可以有一个更清晰、更大的版本来处理。假设我中间有一些**交换机**。最初，我将从每侧只有两个 **GPU** 开始，或者每侧两个 **GPU 托盘**。假设每个托盘都想有**两根电缆**伸出来。我实际连接了像这样垂直的电缆，连接到**交换机**。现在如果我想**将机架中的 GPU 数量加倍**，我需要连接**两倍的电缆密度**。我还需要连接这些。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let's zoom in on this and look at the wire density. I'll draw this diagram just once more so we have a bit of a cleaner and larger version to work with. Let's say I have some switches in the middle. Initially, I'm going to start with just two GPUs on each side or two trays of GPUs on each side. Let's say maybe each tray wants to have two cables coming out of it. I physically run vertical cables that look like this running out to the switches. Now if I want to double the number of GPUs in a rack, I need to run literally twice the density of cables. I need to run these as well.

</details>

**Dwarkesh**: 非常初级的问题。但是如果你看一个物理**数据中心**，机架内似乎有很多空间。我不知道。电缆真的很大而且……

<details>
<summary>Original English</summary>

**Dwarkesh**: Extremely naive question. But if you look at a physical data center, it seems like there's a lot of space within a rack. I don't know. The cables are really big and...

</details>

**Reiner Pope**: 机架外有空间。机架内……随着它们变得更加优化，这些机架非常紧凑。

<details>
<summary>Original English</summary>

**Reiner Pope**: There is space outside the rack. Inside the rack… As they become more optimized, these racks are very tight.

</details>

**Reiner Pope**: 有**连接器密度**，从托盘进入机架，以及机架的背板，背板本身具有非常高的密度。还有其他物理限制，包括**电缆的弯曲半径**。你不想折断它们等等。

<details>
<summary>Original English</summary>

**Reiner Pope**: There's connector density going from the tray into the rack and the rack's backplane, and the backplane itself has a really high density. There are other physical constraints including the bend radius of cables. You don't want to snap them and so on.

</details>

**Dwarkesh**: 好的，所以是**物理空间**来放置电缆，这限制了它。我完全不知道。这很有趣。这似乎令人惊讶。

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, so it's literally the physical space to put a cable that's constraining it. I had no idea. Interesting. That seems surprising.

</details>

**Reiner Pope**: 机架这么大，我们不能只是塞更多的电缆进去。

<details>
<summary>Original English</summary>

**Reiner Pope**: The rack is so big and we can't just stuff more cables in there.

</details>

**Reiner Pope**: **机架设计**不是我的专长，但当我与那些遇到限制的人交流时，这是一个多种因素的组合。您主要优化哪些大的物理因素？**空间**，**机架的重量**。它实际上很重，所以你需要足够的金属才能不塌陷。但随后你添加更多的金属，它就更重了。然后是**电力**和**冷却**。所有这些都在相互竞争。现代机架正在将所有这些推向非常极端的物理极限。

<details>
<summary>Original English</summary>

**Reiner Pope**: Rack design is not my expertise, but when I talk to folks on what constraints they're up against, it's a combination of things. What are the big physical things you're optimizing for? Space, weight of the rack. It's actually really heavy, so you need enough metal to not sag and fall. But then you add more metal, and it's heavier. Then power and cooling. All of those are competing. Modern racks are pushing all of those to very extreme physical limits.

</details>

**Dwarkesh**: 深度工作本质上是相当厌恶的，所以即使像 **Slack** 和电子邮件这样的工作，也可能很容易让你分心。所以我经常希望我能关掉互联网。但是如果我正在准备面试，即使我有论文和书籍在手边，能够与 **LLM** 进行来回交流仍然非常有用，这样我就可以分解概念并研究后续问题。**Google** 新的 **Gemma 4** 是第一个允许我拥有这种**完全脱机焦点机器**的**开源模型**。它足够小，可以在我的笔记本电脑上运行，但又足够好，足以真正有用。因此，为了准备这一集，我下载了 **Reiner** 的缩放书籍并关闭了互联网。**Gemma** 能够帮助我理解材料并回答我的问题。如果你想要一个可以在笔记本电脑甚至手机上本地运行的 **LLM**，你应该查看 **Gemma 4**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Deep work is by its nature quite aversive, so even things which seem like work, like Slack and email, can be easy ways to distract yourself. So I often wish that I could just turn the internet off. But if I'm prepping for an interview, even if I have the papers and books on hand, it's still super useful to be able to do a back and forth with an LLM so I can break down concepts and research follow-ups. Google's new Gemma 4 is the first open model that allows me to have this kind of fully disconnected focus machine. It's small enough to run on my laptop, but good enough to actually be useful. So to prep for this episode, I downloaded Reiner's scaling book and shut off the internet. I was able to have Gemma help me understand the material and answer my questions. If you want an LLM that you can run locally on your laptop or even your phone, you should check out Gemma 4.

</details>

**Dwarkesh**: **GPT-4** 什么时候发布的？是 **2022** 年还是 **2023** 年？

<details>
<summary>Original English</summary>

**Dwarkesh**: When was GPT-4 released again? Was it 2022 or 2023?

</details>

**Reiner Pope**: **2023** 年。

<details>
<summary>Original English</summary>

**Reiner Pope**: 2023.

</details>

**Dwarkesh**: 好的。据说它有**超过一万亿个参数**。似乎直到最近六个月，才有模型发布了比三年前发布的模型**多得多**的参数，而在此期间本应有这种扩展。

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay. And it was rumored to be over one trillion parameters. It seems like only now, within the last six months, have models been getting released that have significantly more parameters than the model released three years ago, when supposedly there should have been this scaling in the meantime.

</details>

**Dwarkesh**: 原因是**我们只是在等待有足够内存的机架**来容纳一个**五万亿参数的模型**，以及它的 **KV 缓存**以供足够多的用户使用，以应对大量序列？或者如果你正在进行强化学习（**RL**），类似地考虑**实际为你要解决的问题批次保存 KV 缓存**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Is the reason that we were just waiting for racks with enough memory to hold a five-trillion parameter model, along with its KV cache for enough users for a lot of sequences? Or if you're doing RL, a similar consideration of actually holding the KV cache for the batch of problems you're trying to solve.

</details>

**Reiner Pope**: 如果你看 **Hopper**，你有**八个 Hopper**，我想那是 **2022** 年的 **640 千兆字节**。随着 **Blackwell** 最终部署在……

<details>
<summary>Original English</summary>

**Reiner Pope**: If you look at Hopper, you had eight Hoppers, and I think that's 640 gigabytes as of 2022. With Blackwell finally, which was deployed in…?

</details>

**Dwarkesh**: 最近。

<details>
<summary>Original English</summary>

**Dwarkesh**: Very recently.

</details>

**Reiner Pope**: 也许去年。

<details>
<summary>Original English</summary>

**Reiner Pope**: Maybe last year.

</details>

**Dwarkesh**: 去年。

<details>
<summary>Original English</summary>

**Dwarkesh**: Last year.

</details>

**Reiner Pope**: 你最终拥有了 **10 到 20 太字节**的**扩展规模**，这足以容纳一个 **5T** 模型加上 **KV 缓存**。在更大的**扩展域**中部署是一个巨大的解锁。我在这里画出了 **Nvidia Blackwell** 的部署。**Google** 的部署实际上长期以来一直拥有非常大的**扩展域**。

<details>
<summary>Original English</summary>

**Reiner Pope**: You finally have a scale-up on the order of 10-20 terabytes, which is enough for a 5T model plus KV cache. Deploying in larger scale-up domains is a huge unlock. I've drawn here the Nvidia Blackwell deployment. The Google deployment has actually had very large scale-up domains for a long time.

</details>

**Dwarkesh**: 这也解释了为什么 **Gemini** 似乎更领先。

<details>
<summary>Original English</summary>

**Dwarkesh**: That also explains why Gemini seemed to be ahead.

</details>

**Reiner Pope**: **Gemini** 似乎比其他一些实验室更早地成功进行了**预训练**。当时我不在场，所以我不确定有多少是来自成功部署更高的**稀疏率**，这可能是一个原因。也可能是一大堆实际的建模事情，特别是你如何进行**专家混合**。我们看到 **DeepSeek** 的**专家混合**激活了更多的专家，但**粒度更细的专家**。那是一个巨大的创新。我相信在**模型架构**以及**训练数据**上还有许多其他创新。很难将它们全部理清，但就你能做的限制而言，**激活参数**（如我们所见）受**计算成本**限制，而**总参数**受**扩展规模**限制。

<details>
<summary>Original English</summary>

**Reiner Pope**: It just seems like Gemini has had successful pre-training for longer than some of the other labs. Not having been there at the time, I'm not sure how much is coming from successfully deploying higher sparsity ratios, which it could be. It could also be a whole bunch of actual modeling things, specifically how you do the mixture of experts. We've seen the DeepSeek mixture of experts activate more experts, but finer-grained experts. That was a big innovation. I'm sure there are many other innovations on the model architecture as well as on the training data. It's hard to disentangle all of them, but what shows up in terms of the limits of what you can do is that the active parameters, as we saw, are limited by the compute cost, and the total parameters are limited by the scale-up size.

</details>

**Dwarkesh**: 当你在一个**单一的纵向扩展域**内操作时，这是否是**前向**或**后向**，或专门针对**预填充**与**解码**的考虑因素？还是说无论你有什么样的工作负载，无论是进行**预训练**、**强化学习生成**还是**用户推理**，都最好始终处于**纵向扩展**之内？

<details>
<summary>Original English</summary>

**Dwarkesh**: When you're operating within a single scale-up domain, is that a consideration specifically for either forward or backward, or specifically for prefill versus decode? Or is it preferred to always be within a scale-up whatever kind of workload you have, whether you're doing a pre-training run, RL generation, or inference for users?

</details>

**Reiner Pope**: 真的很有趣。要回答这个问题，我们需要讨论**通信模式**。我们已经讨论了**专家混合**的**通信模式**。那是**全对全**的。**全对全**非常强烈地倾向于**完全连接**，这就是我们这里所展示的，它倾向于**在一个机架内**。除了我们这里展示的**专家并行**之外，还有其他类型的**并行**。文献中是**张量并行**。随着**更小专家**的趋势，这变得不那么相关了，所以我们可以忽略它。但我们还有另外两个可用的东西是**数据并行**和**流水线并行**。它们可以更好地适应使用**多个机架**。让我们专门关注**流水线并行**。这是一个**MoE 层**。我上面将有一百多个层。在这个时候，我可以决定，例如，移动到另一个机架，更换机架。现在，这会成为**通信瓶颈**吗？我们实际上可以解决这何时成为**通信瓶颈**的问题。在我们进行代数运算之前，让我们将其可视化并勾勒出路径。我们将有另一个 **MoE 层**，这里还有另一个 **MoE 层**，等等。假设我在这里更换机架，然后一些层之后，我在这里也更换机架。我们将用来确定在更换机架时是否存在**通信瓶颈**的方法是，我们将比较**纵向扩展带宽**要求与**横向扩展带宽**要求。让我们写下这个。

<details>
<summary>Original English</summary>

**Reiner Pope**: Really interesting. To answer that question, we're going to need to talk about the communication patterns. We've talked about the mixture of experts communication pattern. That is this all-to-all. All-to-all very strongly favors full connectivity, which is what we've just shown here, and it favors being within one rack. There are other kinds of parallelism besides expert parallelism, which we just showed here. In the literature is tensor parallelism. With the trend towards smaller experts, this has become much less relevant, so we can ignore that. But the other two things we have available are data parallelism and pipeline parallelism. They can be a much better fit for using multiple racks. Let's focus on pipeline parallelism specifically. This is one layer of MoE. I'm going to have a hundred more layers up above. I could decide at this point, for example, to move to a different rack, change rack. Now, is that going to become a communication bottleneck? We can actually solve for when this becomes a communication bottleneck. Before we do that algebraically, let's visualize it out and sketch the path. We're going to have another MoE layer, and another MoE layer here, and so on. Let's say I change rack here, and then some number of layers later, I change rack here as well. The methodology we're going to use to determine whether we have a communication bottleneck at the point where we change rack is we're going to compare the scale-out bandwidth requirements to the scale-up bandwidth requirements. Let's write this.

</details>

**Reiner Pope**: 提示是这里有更多的发送。我们在这里发送很多东西，而我们在这里只发送一个东西，而且我们可能也做了很多次。这就是区别。

<details>
<summary>Original English</summary>

**Reiner Pope**: The hint is going to be that there's a lot more sends here. We're sending many things here, whereas we're only sending one thing here, and we're also maybe doing it many times. That's what makes the difference.

</details>

**Dwarkesh**: 我能猜一下吗？出于好奇，看看我是否真的理解了，你似乎正在将**批处理大小**发送到机架中。

<details>
<summary>Original English</summary>

**Dwarkesh**: Can I try to guess? Just out of curiosity, to see if I'm actually understanding, it seems like you're sending batch size into the rack.

</details>

**Reiner Pope**: 在这里？

<details>
<summary>Original English</summary>

**Reiner Pope**: In here?

</details>

**Dwarkesh**: 是的。但是机架内的通信是**批处理大小**乘以 **GPU** 数量。

<details>
<summary>Original English</summary>

**Dwarkesh**: Yes. But the communication within the rack is batch size times number of GPUs.

</details>

**Reiner Pope**: **激活 GPU** 数量。我根本没有发送到这个 **GPU**。在这个图中，有一个 **1-3** 倍的爆炸式增长。关键是**我甚至不需要发送到这个 GPU**，所以这是一个很大的节省。

<details>
<summary>Original English</summary>

**Reiner Pope**: Number of activated GPUs. I don't send to this GPU at all. There's an explosion from 1-3x larger here in this diagram. The key thing is that I didn't even need to send to this GPU at all, and so that's a big saving.

</details>

**Reiner Pope**: 我们将讨论**纵向扩展**在多大程度上是**横向扩展**的瓶颈。我们将直接跳到**纵向扩展**上花费的时间与**横向扩展**上花费的时间之比。这就是我们正在讨论的数量。第一个考虑因素是**纵向扩展**通常比**横向扩展快 8 倍**。在基线上，如果带宽相同，我们将有 **1/8**，这来自于**带宽**。但随后我们发送的数据量有所扩展。如果一个令牌从这里进来，那么这个令牌就会被路由到，在 **DeepSeek** 的例子中，可能是 **32** 个专家或 **16** 个专家。它被路由到一些专家。所以这是**激活专家**的数量。同样的事情适用于多个不同的层，所以也许我将运行两个层。还有**每阶段多次的层数**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We're going to talk through to what extent scale-up is a bottleneck over scale-out. We will directly jump to the ratio of the time spent on scale-up over the time spent on scale-out. This is the quantity we're talking about. The first consideration is that scale-up is 8x faster than scale-out generally. At a baseline, if the bandwidths were the same, we would have this 1/8, which is coming from bandwidth. But then we have some amount of expansion in how much data we're sending. If one token comes in here, then this one token gets routed to, in the DeepSeek case maybe 32 experts or 16 experts. It gets routed to some number of experts. So this is the number of activated experts. This same thing applies on multiple different layers, so maybe I'm going to run two layers. There's also multiple times the number of layers per stage.

</details>

**Dwarkesh**: 你不需要乘以 **2** 来表示**全对全**吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Don't you need to multiply the whole thing by two for the all-to-all?

</details>

**Reiner Pope**: 对于向上和向下。是的，有一个**两倍的因子**。谢谢。

<details>
<summary>Original English</summary>

**Reiner Pope**: For the up and down. Yes, there's a factor of two. Thank you.

</details>

**Reiner Pope**: 我们希望**纵向扩展时间**大于**横向扩展时间**，因为**纵向扩展时间**是更重要和更宝贵的资源。我们希望这个数字**大于或等于 1**。这看起来真的不难。我们只需要克服 **8** 倍的因子。所以我们需要这三件事的乘积大于 **8**。通常我们有相当大数量的**激活专家**。它本身可能是 **8**。然后我们可以增加**每阶段的层数**很多，直到我们满足这个条件。

<details>
<summary>Original English</summary>

**Reiner Pope**: What we would like is for the scale-up time to be greater than the scale-out time, because the scale-up time is the more important and precious resource. We would like this number to be greater than or equal to one. This really doesn't seem hard. There's just a factor of 8 that we need to overcome. So we need the product of these three things to be bigger than 8. Typically we have a fairly large number of activated experts. It could be 8 by itself. Then we can increase the number of layers per stage a lot until we satisfy this.

</details>

**Reiner Pope**: 这最终看起来像是我可以有一个**机架的完整流水线**，其中一个机架做一层，然后我移动到下一个机架再做一层，然后我移动到下一个机架再做一层。

<details>
<summary>Original English</summary>

**Reiner Pope**: What this ends up looking like is that I can have an entire pipeline of racks where one rack does one layer, and then I move on to the next rack and do another layer, and then I move on to the next rack and do another layer.

</details>

**Dwarkesh**: 有趣的是，实践中最好的**并行策略**最终与实际架构在物理上相似。它不是什么“银河系大脑”的东西。它就像是，“哦，我们有专家，我们将把它们放在不同的 **GPU** 上，或者我们有不同的层，我们将把它们放在不同的机架上。”我觉得这很有趣。

<details>
<summary>Original English</summary>

**Dwarkesh**: It's interesting to me that the best parallelism strategy in practice ends up being one which physically resembles the actual architecture. It's not some galaxy brain thing. It's like, "Oh, we have experts, we're going to put them on different GPUs, or we have different layers, we're just going to put them on different racks." I feel that's interesting.

</details>

**Reiner Pope**: 切割与**模型架构**匹配。

<details>
<summary>Original English</summary>

**Reiner Pope**: The cutting matches the model architecture.

</details>

**Dwarkesh**: 没错。可能是一些更古怪的东西，比如**张量并行**什么的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Exactly. It could have been something wackier with tensor parallelism and whatever.

</details>

**Reiner Pope**: 从“银河系大脑”的角度来看，思考这个问题的方式是，模型在哪些不同的维度上进行**扩展**？它通过**层**进行扩展，它通过**模型维度**进行扩展，它通过 **DFF 维度**进行扩展，它通过**专家数量**进行扩展。这些数字中的每一个你都可以选择进行切割。如果这些数字足够大，最终沿着它们切割就会变得有利可图。我们选择了其中两个。另外两个，以模型通常的大小来看，是无利可图的。

<details>
<summary>Original English</summary>

**Reiner Pope**: The galaxy brain way to think of it is, what are all the different dimensions in which a model is scaled up? It is scaled up by layers, it is scaled up by the model dimension, it is scaled up by the DFF dimension, it is scaled up by the number of experts. Every single one of those numbers you can choose to cut along. If those numbers are big enough, it eventually becomes profitable to cut along there. We have selected two of them. The other two, in the way models are typically sized, are not profitable.

</details>

**Dwarkesh**: 所以 **Ilya** 有一个演讲，他说：“今天我们知道**不要做流水线并行**。”**Horace He** 给我和我的朋友们……我讨厌它听起来像**苏斯博士**的引语。但他给我们讲授了这些不同类型的**并行**。他说**流水线并行**的问题在于，除了**气泡**之外，它还会产生这些**架构约束**。例如，**Kimi** 有**残差**，其中注意力关注前几层，所以以这种方式实现变得很困难。

<details>
<summary>Original English</summary>

**Dwarkesh**: So there's a talk by Ilya where he says, "Today we know not to do pipeline parallelism." And Horace He gave my friends and me… I hate that it sounds like a Dr. Seuss quote. But he gave us a lecture on these different kinds of parallelisms. He said the problem with pipeline parallelism is that, other than the bubbles, it creates these architectural constraints. Kimi, for example, has these residuals where attention attends to layers a few back, so it becomes hard to implement in this way.

</details>

**Reiner Pope**: 我想我们甚至没有完全阐明我们从**流水线**中获得了什么好处。这些复杂性是真实存在的。**流水线**是一个巨大的麻烦，但它确实给你带来了一些好处。然后你可以决定这些好处是否值得付出代价。它在**推理**中有些好处，在**训练**中可能好处更大。在**推理**中，我们节省了什么？我们节省了**内存时间**还是**计算时间**？并非如此。我们只是将**内存时间**从一个芯片移动到另一个芯片，或者从一个机架移动到另一个机架。运行时并没有实际的好处。然而，我们节省的是**内存容量**。如果认为机架中的内存是一个瓶颈，那么**我们能有多快**就有一个限制。**流水线**允许我们**大幅减少这个瓶颈**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I guess we didn't fully articulate even what is the benefit that we're getting from pipelining. These complexities are real. Pipelining is a massive hassle, but it does give you some benefits. You can then decide whether those benefits are worth the costs. It has some benefits in inference, maybe bigger benefits in training. In inference, what are we saving on? Are we saving on memory time or compute time? Not really. We're just moving the memory time from one chip to another chip, or one rack to a different rack. There's no actual benefit in runtime. However, what we are saving on is memory capacity. If we think that the memory in a rack is a bottleneck, then there's a constraint on how fast we can go. Pipelining allows us to massively reduce that bottleneck.

</details>

**Reiner Pope**: 与此相反的含义……在这次采访之前，我与 **Jane Street** 的 **GPU 性能工程师 Axel** 聊过。他解释说，要进行**流水线**，你必须使用**微批次**而不是**全批次**。如果你使用**微批次**，那么你本质上无法将**加载权重**的成本分摊到所有用户或所有序列上。积极的含义是**你不需要使用那么多内存**。消极的含义是**我们无法将加载权重的成本分摊到所有这些用户身上**。

<details>
<summary>Original English</summary>

**Reiner Pope**: The opposite connotation to this… Before this interview, I was chatting with Axel, who's a GPU performance engineer at Jane Street. He was explaining that to do pipelining, you have to do micro-batches rather than full batches. If you do micro-batches, then you're by definition not able to amortize loading the weights across all the users or all the sequences. The positive connotation of that is you don't have to use as much memory. The negative connotation is that we can't amortize loading the weights across all those users.

</details>

**Reiner Pope**: 也许值得解释一下为什么要进行**微批次**。我们应该画出**流水线气泡**图吗？什么是**流水线并行**中出现的**微批次**？

<details>
<summary>Original English</summary>

**Reiner Pope**: Maybe it's worth explaining why you have to do micro-batches. Shall we draw the pipeline bubble? What is this micro-batching that shows up in pipeline parallelism?

</details>

**Reiner Pope**: 我将首先关注**推理**。这是一个稍微简单的问题。我将画出时间，然后是我们在哪个机架上。想法是，也许我会有**四个机架**。我有一个**推理**，它将像这样通过这四个机架进行。这是**推理零号**。它以一定的**批处理大小**运行，并像这样通过所有**流水线阶段**。现在，如果我们要说，“好吧，我们在这里运行**推理一号**”，这显然是巨大的浪费。大约**四分之三**的时间，每个机架都在空闲。我们实际上不会在这里运行**推理一号**，我们会尽快运行它，也就是在**推理零号**完成后立即运行。然后我们继续。如果我们没有填充这个，我们就会称之为**流水线气泡**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I'll focus on inference first. It's a slightly simpler problem. I'm going to draw time, and then which rack we're on. The idea is that maybe I'll have four racks. I've got an inference that is going to step through these four racks in some time like this. This is inference number zero. It runs at a certain batch size and steps through all the pipeline stages like this. Now, if we were to say, "Well, we're going to run inference number one here," this is clearly a massive waste. Like three-quarters of the time each of the racks is doing nothing. We don't actually run inference one here, we run it as soon as we can, which is immediately after inference zero finishes. And then we keep going. If we hadn't filled this in, we would call this the pipeline bubble.

</details>

**Reiner Pope**: 当我以这种**推理上下文**绘制它时，我们只进行**前向传递**，这是显而易见的。你为什么要这样做呢？在**训练上下文**中，它可能不那么明显。但在**推理上下文**中，进行这种改变是非常自然的。

<details>
<summary>Original English</summary>

**Reiner Pope**: When I've drawn it in this inference context where we're only going in a forwards pass, it's obvious. Why would you do this stupid thing? In a training context, it's maybe less obvious. But in the inference context, it's really natural to make this change.

</details>

**Dwarkesh**: 哦，有意思。这有点显而易见，但**微批次**和**批次**之间的区别在**推理**中根本不重要，因为你可以随意称呼它。它只在**训练**中重要，因为有一个**最优批处理大小**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Oh, interesting. This is sort of obvious, but the difference between micro-batch and batch doesn't matter at all in inference because you can just call it whatever you want. It only matters in training because there is an optimal batch size.

</details>

**Reiner Pope**: 是的。在你进行完整的**反向传播**之前，你需要累积该批次中的所有序列。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yes. Before you do a full backward step, you want to have accumulated all the sequences in that batch.

</details>

**Dwarkesh**: 如果你希望在**训练**中进行**流水线**，为了避免**气泡**，你需要……我们应该画出带有那个的**训练图**吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: If you want to do pipelining in training, in order to avoid that bubble, you need to—Should we draw the training diagram with that?

</details>

**Reiner Pope**: 我们这样做吧。这是**推理图**，我称之为**前向**，这样我们就不会弄错。现在让我们为**训练**做同样的事情。我们有一个**前向传递**，但在某个阶段，我们将不得不过渡到**后向传递**。我们将在**前向传递**中进行一些批次，然后我们将一次性过渡到**后向传递**，编号类似。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let’s do that. This is the inference diagram, and I'll call this forward so we don't have the wrong thing showing up there. Let's do the same thing for training now. We've got a forwards pass, but at some stage we're going to have to transition to a backwards pass. We'll do some number of batches in the forwards pass, and then we're going to transition to the backwards pass for everyone all in one go. The inference part is the same here, but then we do a hard stop at this point and transition everyone to the backwards pass, with similar numbering like this.

</details>

**Dwarkesh**: 也许值得澄清的是，那里有一个硬停顿的原因是**你希望一次性完成整个批次的后向步骤**。然后有一个**最优大小**来决定这个批次应该有多大。

<details>
<summary>Original English</summary>

**Dwarkesh**: It may be worth clarifying the reason there is that hard stop is because you want to do a whole batch at once for the backward step. And then there is an optimal size for how big that batch should be.

</details>

**Reiner Pope**: 更小总是更好，实际上，这是一种说法。从 **ML** 收敛率的角度来看，更小总是更好，因为你可以从**梯度下降**中获得最新鲜的信息。

<details>
<summary>Original English</summary>

**Reiner Pope**: Smaller is always better, actually, is a way to put it. From an ML convergence rate perspective, smaller is always better because you're getting the freshest information from the gradient descent.

</details>

**Dwarkesh**: 但从**总训练时间**的角度来看呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: But from a total training time perspective?

</details>

**Reiner Pope**: 从**总训练时间**的角度来看，从系统角度来看，更小更糟。**最优解**是这两者之间的权衡。所以你选择一个**批处理大小**，对于那个**批处理大小**，你进行一定数量的**前向**，然后进行一定数量的**后向**。你问为什么会有一个硬停顿。使用**流水线并行**，因为你这里有**空闲时间**，也就是**气泡**，文献中有很多技术可以改变这种布局并避免它。还有更复杂的方案，称为**零气泡**或**一前一后**，它们以复杂的方式交织**前向**和**后向**。

<details>
<summary>Original English</summary>

**Reiner Pope**: From a total training time perspective, smaller is worse from a systems perspective. The optimum is the trade-off between those two. So you pick a batch size, and for that batch size, you do some amount forwards and then some amount backwards. You asked why there is even a hard stop there. With pipeline parallelism, because you've got this idle time here which is the bubble, there are so many techniques in the literature for how to lay this out differently and avoid that. There are more complicated schemes called zero bubble or one-forward-one-backward, which interweave the forwards and the backwards in complicated ways.

</details>

**Dwarkesh**: 你可以在那个**气泡**里挖**比特币**。

<details>
<summary>Original English</summary>

**Dwarkesh**: You can mine Bitcoin in that bubble.

</details>

**Reiner Pope**: 没错。更实用的是，你可以执行**权重梯度步骤**，但你也可以挖**比特币**。在**推理**中，**流水线**对你关心的任何事情，比如**批处理大小**或**延迟**，都是中性的。它既不改善也不恶化。如果你看这个推理的延迟，如果它是**流水线**的，与它都在一个机架上运行相比……如果它都在一个机架上运行，我们只会将所有盒子滑下来并仍然排成一排，延迟会是相同的。

<details>
<summary>Original English</summary>

**Reiner Pope**: Right. More usefully, you can do the weight gradient step, but you can also mine Bitcoin. In inference, the effect of pipelining on anything you care about, like batch size or latency, is neutral. It doesn't improve it, it doesn't make it worse. If you look at the latency of this inference, running it if it were pipelined versus if it were all on one rack… If it were all on one rack, we would just slide all the boxes down and still put them in a row, and the latency would be the same.

</details>

**Reiner Pope**: **流水线**对于**延迟**既没有更好也没有更差。它确实意味着你每个机架使用的**内存容量**更少。因为现在你不再需要整个模型，你只需要模型的**四分之一**，然后你就可以扩展。

<details>
<summary>Original English</summary>

**Reiner Pope**: Pipelining is neither better nor worse for latency. It does mean that you just use less memory capacity per rack. Because now instead of needing the whole model, you only need a quarter of the model, and you can expand.

</details>

**Dwarkesh**: 很有道理。所以在**推理**中使用**流水线**是显而易见的，但在**训练**中存在更艰难的权衡。

<details>
<summary>Original English</summary>

**Dwarkesh**: Makes a ton of sense. So it's a no-brainer to use pipelining during inference, but there's this harder trade-off during training.

</details>

**Reiner Pope**: 即使在**推理**中，事实上，它也没有被大量使用。它减少了你的**内存容量**要求，但实际上有**巨大的盈余**。我想你刚才说一个 **Blackwell** 机架有几十**太字节**。这比一个**万亿参数模型**大得多。一个**万亿参数模型**只需要一个**太字节**，所以它已经足够了。**流水线**没有巨大的好处，因为你正在减少一个已经很小的数字。但这确实说明理论上，你可能拥有**太多内存**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Even in inference, in fact, it is not used a ton. It reduces your memory capacity requirements, but there's actually a huge surplus. I think you were saying that a rack of Blackwell has many tens of terabytes. That's much bigger than a trillion parameter model. A trillion parameter model only needs one terabyte, so it already fits. There's not a huge benefit from pipelining because you're reducing a number that's already pretty small. But it does say that theoretically, maybe you had too much memory there.

</details>

**Reiner Pope**: 你本可以**构建不同的硬件**，拥有更少的内存。如果你正在设计硬件，你可以说，“我不需要那么多内存，因为我不需要权重适合一个机架。我可以将权重放在八个机架中，那么我本可以构建没有那么多 **HBM** 每个 **GPU** 的硬件。”

<details>
<summary>Original English</summary>

**Reiner Pope**: You could have built different hardware that has less memory. If you were designing your hardware, you could say, "I didn't need that much memory because I don't need the weights to fit in one rack. I can fit the weights in eight racks, then I could have built hardware that didn't have so much HBM per GPU."

</details>

**Dwarkesh**: 上周，**Horace He** 慷慨地给了我和我的朋友们一个关于**大规模预训练系统**的精彩讲座。有一些概念我想为我的博客文章进行动画化，比如**权重如何分片**以及**梯度如何根据你使用的并行方式流动**。所以我把我的讲座笔记和我在讲座中做的草图给了 **Cursor**。我让它**可视化 Horace** 解释的一个**特定的分层集合**。第一个版本已经很好了，然后我能够使用**设计模式**从那里选择和调整任何特定的组件。我做所有这些都没有一个明确的最终状态。**Cursor** 的 **Composer 2 Fast** 模型足够快，我可以**几乎即时地迭代**。我可以尝试一个想法，在内置浏览器中测试结果，并立即进行任何更改。我在不到 **20** 分钟内完成了 **10** 个不同的版本。如果你想查看这个动画，我已将其与讲座笔记一起发布在博客文章中。链接在描述中。如果你想亲自尝试这种**迭代设计流程**，请访问 **cursor.com/dwarkesh** 开始。

<details>
<summary>Original English</summary>

**Dwarkesh**: Last week, Horace He was kind enough to give me and my friends a great lecture on large-scale pre-training systems. And there were some concepts that I wanted to animate for a write-up on my blog, like how weights shard and gradients flow depending on the parallelism that you're using. So I gave Cursor my lecture notes and a sketch that I made during the lecture. And I asked it to visualize a specific hierarchical collective that Horace had explained. The first version was already pretty good, and then I was able to use design mode to select and tweak any specific components from there. I was able to do all of this without a clear end state in mind. Cursor's Composer 2 Fast model was quick enough that I was able to iterate almost instantaneously. I could try an idea, test the results in the built-in browser, and immediately make any changes. I went through 10 different versions in under 20 minutes. If you want to check out this animation, I published it along with the lecture notes in a blog post. The link is in the description. And if you want to try out this kind of iterative design flow for yourself, go to cursor.com/dwarkesh to get started.

</details>

**Dwarkesh**: 现在大家都在谈论**内存墙**。内存变得非常昂贵。内存不足。智能手机销量将下降 **30%**，因为内存不足。这令人震惊，**Dylan** 说**超大规模厂商**今年将 **50%** 的资本支出用于内存。

<details>
<summary>Original English</summary>

**Dwarkesh**: everybody's talking about the memory wall right now. Memory is getting super expensive. There's not enough memory. Smartphone volume will go down 30% because there's not enough memory. This is shocking, Dylan said hyperscalers are spending 50% of their CapEx this year on memory.

</details>

**Reiner Pope**: 这可以相信。

<details>
<summary>Original English</summary>

**Reiner Pope**: That’s believable.

</details>

**Dwarkesh**: **超大规模厂商**的资本支出是多少？那是数千亿美元，也许一万亿美元，他们将其中一半花在内存上？那是一个巨大的约束。这就是为什么我们今年不会有新的笔记本电脑和手机。但与此同时，我们有**太多内存**？

<details>
<summary>Original English</summary>

**Dwarkesh**: What is hyperscaler CapEx? That's high hundreds of billions, maybe a trillion, and they're spending half of that on memory? That is a huge constraint. That's why we're not going to get new laptops and phones this year. But at the same time, we have too much memory?

</details>

**Reiner Pope**: 人们愿意在这些系统中投入**太多内存**。如果不需要，**Jensen** 为什么要把这么多内存塞进这些机架呢？

<details>
<summary>Original English</summary>

**Reiner Pope**: People are willing to put too much memory into these systems. Why is Jensen shoving all this memory into these racks if you don't need it?

</details>

**Reiner Pope**: 在我们擦除之前的方程中，我们计算了**内存时间**、**内存带宽**和**计算带宽**。现在让我们开始关注**内存容量**。我们首先关注**内存容量**，甚至不考虑**并行方案**。对内存的需求是**总参数**的数量。这是我们需要将权重放入我们正在使用的某个系统中的。然后我们还需要放入 **KV**。**KV** 随着**批处理大小**乘以**上下文长度**乘以**每个令牌的字节数**而变化。

<details>
<summary>Original English</summary>

**Reiner Pope**: In the equations we had here before we erased them, we were doing memory time, memory bandwidth and compute bandwidth. Let's now start looking at memory capacity. We'll start off with memory capacity without even thinking about a parallelism scheme. The demand on memory is the number of total parameters. This is what we need to fit the weights in some system that we are using. Then we need to fit the KVs as well. KVs go as batch size times the length of the context times the bytes per token.

</details>

**Reiner Pope**: 在这种情况下，我所争论的，以及我为**流水线**提出的论点是，有一些技术可以让我们解决这个问题。让我们考虑在一些 **GPU** 上运行这个。我们将有一个**扩展范围**，即 **E**，**专家并行**。当我们在许多 **GPU** 之间进行**专家层分片**时，我们这样做到了什么程度？多少个 **GPU**？我们说这是，例如 **64**。然后 **P** 将是**流水线**的程度。这是机架的数量，也许我们选择 **4** 个或类似的东西。这是整个系统的**总内存需求**，但现在我将计算**每个 GPU 的内存需求**。我将使用小写的 **cmem**。显然，我们只是将所有这些数字除以 **E** 和 **P**。非常简单。

<details>
<summary>Original English</summary>

**Reiner Pope**: What I was arguing about in this context, and the case I was making for pipelining, is that there are some techniques that allow us to solve this. Let's consider running this on some number of GPUs. We're going to have one extent, which is E, the expert parallelism. When we had this sharding of an expert layer across many GPUs, to what extent do we do that? How many GPUs? We're going to say that this is, for example 64. Then P is going to be the extent of pipelining. This is the number of racks, maybe we'll pick 4 or something like that. This is the total memory requirement across the system, but now I'm going to calculate a memory requirement per GPU. I'll use a lowercase cmem. Obviously, we just take all of these numbers and divide it by E and P. Really easy.

</details>

**Reiner Pope**: 它是 **Ntotal**，加上**批处理**乘以**上下文长度**乘以**每个令牌的字节数**，全部除以 **E** 乘以 **P**。

<details>
<summary>Original English</summary>

**Reiner Pope**: It's this Ntotal, plus the batch times length of context times bytes per token, all divided by E times P.

</details>

**Dwarkesh**: 为什么这样划分是正确的？

<details>
<summary>Original English</summary>

**Dwarkesh**: Why is this correct as divided this way?

</details>

**Reiner Pope**: 我们知道**参数**在机架中的所有 **GPU** 之间完美划分。**层**在不同的机架之间完美划分。所以这在这里是可行的。我们将在某种程度上——我将大致说明如何——将上下文在机架中的 **GPU** 之间完美分片，然后根据层在机架之间进行分片。

<details>
<summary>Original English</summary>

**Reiner Pope**: We knew that the parameters were perfectly divided amongst all the GPUs in a rack. The layers are perfectly divided amongst the different racks. So that works here. Somehow we're going to arrange—I'll hand-wave exactly how—the same perfect sharding of the contexts across GPUs in a rack, and then based on layer across racks.

</details>

**Dwarkesh**: 抱歉，**4** 是机架的数量吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, 4 is the number of racks?

</details>

**Reiner Pope**: 是的，例如。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah, for example.

</details>

### 流水线并行与内存优化

**Reiner Pope**: 这里是我们需要回到**批处理大小 B** 并分析它的地方。你提到了**微批处理**和**全局批处理**的区别。让我们回到这里的**流水线图**。我们有一个批次在这里向前运行，然后正如我所画的，它有点消失了。这并不完全正确。如果你思考**解码**是如何工作的，我已经生成了一堆令牌。我进行一次**前向传递**，生成一个新令牌，然后我将其写入我的 **KV 缓存**。然后我进行另一次**前向传递**，生成下一个令牌。我实际上将**批次零**在一个循环中运行。事实上，我向前运行。一旦我完成，我就可以在这里开始循环的下一次迭代。我们只需填充它。我们有二、三、二和三，以及二和三。让我们分割这个批次。这个批次将是**全局批处理大小**。**B** 将是**微批次**的数量乘以**每个微批次的批处理大小**。我们需要多少个**微批次**？这个图中的**微批次**数量是 **4**：零、一、二、三。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is the place where we actually need to go back and analyze this batch size B. You were making this comment that there's micro-batching versus global batching. Let's come back to this pipelining diagram here. We've got one batch going forward here, and then as I drew it, it kind of just disappeared. That's not really correct. If you think about how decode is working, I have a bunch of tokens that I have generated already. I do one forwards pass where I generate a new token, and then I write that to my KV cache. Then I do another forwards pass that generates the next token. I'm actually going to be running this batch zero in a loop. In fact, I go forwards. Once I finish, I can start the next iteration of the loop up here. We'll just fill this in. We've got the two, three, two and three, and two and three. Let's split this batch. This batch will be the global batch size. B is going to be the number of micro-batches times the batch size per micro-batch. How many micro-batches do we need? The number of micro-batches in this diagram is 4: zero, one, two, three.

</details>

**Reiner Pope**: 抱歉，不，这是 **300** 乘以**稀疏度**。这就是每 **20 毫秒**发车的火车有多大。

<details>
<summary>Original English</summary>

**Reiner Pope**: Sorry, no, this is the 300 times sparsity. This is how big the train that takes off every 20 milliseconds is.

</details>

**Dwarkesh**: 没错。

<details>
<summary>Original English</summary>

**Dwarkesh**: Right.

</details>

**Reiner Pope**: 这将是 **20 毫秒**的火车。**全局批处理大小**是**微批次**的数量乘以**本地批处理大小**。**本地批处理大小**由这个**硬件参数**设置。**微批次**的数量尽可能小，以便我们可以在不留下任何空闲时间的情况下循环。如果我们少一些，我们就会在循环时出现空闲时间。你可以直观地看到它等于**流水线阶段**的数量。这是一个视觉证明。它是 **4**，这边也是 **4**。你可以看到它沿着这里走，然后循环到**流水线阶段**的数量。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is going to be the 20-millisecond train. The global batch size is the number of micro-batches times the local batch size. Local batch size is set by this hardware parameter. The number of micro-batches is as small as possible, such that we can wrap around and not leave any idle time. If we had fewer, we would have this idle time when we wrap around. You can visually see that it is equal to the number of pipeline stages. It's a proof by visual here. It is 4, and it's 4 this way as well. You can look and see that it goes along here, and then it wraps around to the number of pipeline stages.

</details>

**Dwarkesh**: 抱歉，非常基本的问题。这实际上是这样做的吗？今天的**前沿模型**在**推理**过程中会有**流水线**吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, very basic question. Is this what is actually done? A frontier model today will have pipelining during inference?

</details>

**Reiner Pope**: 毫无疑问，在**大规模训练**中会这样做。它可以在**推理**中完成。我实际上要说明为什么它吸引力较小。它对**权重**有用，但对 **KV** 不那么有用。

<details>
<summary>Original English</summary>

**Reiner Pope**: For sure during massive scale training this is done. It can be done for inference. I'm actually going to make the case for why it is less attractive. It is useful for weights, but not so useful for KVs.

</details>

**Reiner Pope**: 最大的挑战是……让我们填上这个。这里的**微批处理大小**最终等于**流水线阶段**的数量。当我们回到这里并代入所有这些时，我们会得到**流水线阶段**的数量乘以这里出现的小写 **b**。当我们将其分解时，我将把这个加号分成两项。我们得到这里完全除以 **E** 乘以 **P**。我们这里仍然除以 **E** 乘以 **P**，但 **P** 抵消了。我们发现，如果你增加**流水线阶段**的数量，**权重**的内存占用会越来越小，但**激活**的内存占用保持不变。所以它实际上不起作用。你大部分的内存……一旦你进行了足够的**流水线**——而且实际上并不多，即使是两个也常常足够了——这个项就变得非常小。**KV 缓存**成为主导项。

<details>
<summary>Original English</summary>

**Reiner Pope**: The big challenge is... Let's fill this in. The micro-batch size here ends up being equal to the number of pipeline stages. When we go back and substitute all of that into here, we get a number of pipeline stages times this little b showing up in here. When we factor this out, I'm going to split this plus into two terms. We get the full division by E times P over here. We still have division by E times P over here, but the Ps cancel. What we find is that if you increase the number of pipeline stages, the memory footprint for the number of weights keeps going down and down and down, but the memory footprint for the number of activations stays constant. So it doesn't actually work. Most of your memory… Once you do enough pipelining—and it's really not much, even two is often enough—this term becomes very small. The KV cache becomes the dominant term.

</details>

**Dwarkesh**: 我知道这是错的。我只是想弄清楚我的逻辑链为什么是错的。如果你通过许多不同的阶段进行**流水线**，**KV 值**在层之间是不共享的。为什么跨多个层进行**流水线**没有帮助呢？因为那样你就不必存储……你只需要存储一层的 **KV** 而不是两层。

<details>
<summary>Original English</summary>

**Dwarkesh**: I know this is wrong. I'm just trying to think about why my train of logic here is wrong. If you're pipelining through many different stages, the KV values are not shared between layers. Why would it not help to be pipelining across multiple layers? Because then you don't have to store... You only need to store one layer rather than two layers of KVs.

</details>

**Reiner Pope**: 从这个角度来看是有帮助的，你说得对。但与此同时，与此竞争的是，你需要同时保持所有机架有效运行，所以同时在传输中的序列数量增加了。

<details>
<summary>Original English</summary>

**Reiner Pope**: It helps from that perspective, you're right. What's competing with that, though, is that you need to be keeping all of the racks usefully busy at a time, so the number of sequences that are in flight simultaneously has gone up.

</details>

**Dwarkesh**: 啊，有道理。

<details>
<summary>Original English</summary>

**Dwarkesh**: Ah, that makes sense.

</details>

**Reiner Pope**: 它们正好抵消了，最终你每个 **GPU** 没有节省。

<details>
<summary>Original English</summary>

**Reiner Pope**: Those exactly cancel, and you end up not getting a saving per GPU.

</details>

**Dwarkesh**: 没错。

<details>
<summary>Original English</summary>

**Dwarkesh**: Right.

</details>

**Reiner Pope**: 这从根本上回到了**你无法跨越 KV 缓存进行分摊**这一点。首先，我们确定你无法跨越**批处理大小**分摊 **KV 缓存**。现在我们说你也无法在**流水线阶段**之间分片它。从这两个角度来看，这都很糟糕。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is going back fundamentally to the point of how you're not able to amortize across KV caches. First, we established you can’t amortize KV caches across batch size. Now we're saying you also can't shard it across pipeline stages. It sucks from both of those points of view.

</details>

**Dwarkesh**: 有意思。那么**推理**中做了什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. So then what is done during inference?

</details>

**Reiner Pope**: **DeepSeek** 论文报告了他们所做的事情，那就是他们只是进行了大量的**专家并行**。实际上，你应该将你的**专家并行**增加到你的**扩展域**大小，然后进行非常少的**流水线**。也许根本没有，也许只有两个，足以让**权重存储**不是一个大问题。这些是唯一真正有意义的两种**并行**。过去有**张量并行**，它是在一个专家内部进行切割，但现在专家太小了，这不再是一种有利可图的优化。

<details>
<summary>Original English</summary>

**Reiner Pope**: The DeepSeek paper reports what they do, which is that they just do a lot of expert parallelism. In effect, you should increase your expert parallelism up to your scale-up domain size, and then do very little pipelining. Maybe none at all, maybe two, just enough to make the weight storage not too big of an issue. Those are the only two parallelisms that really make sense. In the past, there was tensor parallelism, which was cutting up within an expert, but the experts are so small now that that is not a profitable optimization.

</details>

**Dwarkesh**: 这是否意味着**前沿实验室**在进行**推理**时，只在**单个纵向扩展**中进行？

<details>
<summary>Original English</summary>

**Dwarkesh**: Does that mean that frontier labs, when they're doing inference, are just within a single scale-up?

</details>

**Reiner Pope**: 是的。你可以看看它如何取决于**模型大小**。你可能有一个非常大的模型，一个超过机架内存的模型。在这种情况下，你应该进行一些**流水线**。也许它是极其稀疏的，例如，那将是这样做的原因。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yes. You can look at how it depends on model size. You could have a very large model, one that exceeds the memory of a rack. There you should be doing a bit of pipelining. Maybe it's extremely sparse, for example, and that would be a reason to do it.

</details>

**Reiner Pope**: 这回到了讲座开头所做的承诺，即这将告诉你**AI 进展**。就**模型大小**的缩放最近一直很慢而言……

<details>
<summary>Original English</summary>

**Reiner Pope**: This goes back to the promise at the beginning of the lecture, which was this will actually tell you about AI progress as well. To the extent it is the case that model size scaling has been slow until recently…

</details>

**Dwarkesh**: 让我确保我理解这个主张。主张不会是你可以在更多的机架上训练。只是之前没有意义，我们没有能力轻松地对更大的模型进行推理。

<details>
<summary>Original English</summary>

**Dwarkesh**: Let me make sure I understand the claim. The claim would not be you could have trained across more racks. It was just that it would not have made sense before, we didn't have the ability to do inference for a bigger model easily.

</details>

**Reiner Pope**: 实际上，**流水线**对**上下文长度**没有帮助。它对**模型大小**绝对有帮助。由于**流水线**的能力，机架至少不应该成为你**拟合模型参数**能力的约束。你问的另一个考虑因素是，为什么它没有扩展更多，以及为什么更大的**纵向扩展域**有帮助？我们讨论了其中一个方面，即它不是因为**内存容量**。我们至少在**模型大小**方面解决了**内存容量**问题，而不是在 **KV 缓存大小**方面，但至少在**模型大小**方面。出现的另一个问题是**延迟**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Actually, pipelining doesn't help with context length. It totally helps with model size. Because of the ability to do pipelining, a rack at least should not be a constraint on your ability to fit the model parameters. The other consideration you're asking is, why hasn't it scaled up more, and why did bigger scale-up domains help? We talked through one aspect of that, which is that it's not because of memory capacity. We have a solution to the memory capacity at least with respect to model size, not with respect to KV cache size but at least with respect to model size. The other issue that shows up is latency.

</details>

**Dwarkesh**: 我正要问，从一个机架到另一个机架，**每跳的延迟成本**是多少？

<details>
<summary>Original English</summary>

**Dwarkesh**: I was just about to ask, going from rack to rack, what is the latency cost per hop?

</details>

**Reiner Pope**: 这很大程度上取决于**硬件**。我不能非常权威地说。我认为可能在**几毫秒**的量级，但那里可能会有一个数量级的误差。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is very much dependent on the hardware. I can't say with a lot of authority. I think it's probably on the order of a few milliseconds, but it could be off by an order of magnitude there.

</details>

**Dwarkesh**: **4** 是**流水线阶段**的现实数字吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Is 4 a realistic number of how many pipelining stages you might have?

</details>

**Reiner Pope**: 是的。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yes.

</details>

**Dwarkesh**: 所以那并不多。在少量**流水线阶段**中，这不是一个巨大的**延迟影响**。但我想**每个令牌**是 **10 毫秒**。

<details>
<summary>Original English</summary>

**Dwarkesh**: So that's not that much. On a small number of pipelining stages, this is not a huge latency impact. But I guess it's 10 milliseconds per token.

</details>

**Reiner Pope**: 没错。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's right.

</details>

**Dwarkesh**: **2** 乘以 **4** 左右，或者我不知道您说了多少……**每个令牌 10 毫秒**实际上很多。

<details>
<summary>Original English</summary>

**Dwarkesh**: 2 times 4-ish, or I don't know how many you said… 10 milliseconds per token is actually a lot.

</details>

**Reiner Pope**: 如果它从 **20** 到 **30**，或者类似的情况……

<details>
<summary>Original English</summary>

**Reiner Pope**: If it goes from 20 to 30, or something like that…

</details>

**Reiner Pope**: 只是为了描绘它经过的路径，这里你从你的 **GPU** 或 **TPU** 到**网卡**，然后到**机架顶部交换机**，然后跳到另一个机架并反向执行相同的操作。你必须**将这些不同事物的延迟加起来**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Just to chart the path that it goes through, here you're going from your GPU or TPU to a network card, which then goes to a top-of-rack switch, and then hops over to the other rack and does the same thing in reverse. You have to sum up the latencies of these different things.

</details>

**Dwarkesh**: 抱歉，这和**数据中心交换机**是一回事吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, is this the same thing as the data center switch?

</details>

**Reiner Pope**: 它实际上可能上升到**数据中心交换机**并返回。这取决于**部署配置**。

<details>
<summary>Original English</summary>

**Reiner Pope**: It may in fact go up to a data center switch and back. It depends on deployment configuration.

</details>

**Dwarkesh**: 明白了。由于它是**解码**和**顺序**的，它们会堆叠在各个阶段。你不能同时进行它们。

<details>
<summary>Original English</summary>

**Dwarkesh**: Got it. And because it's decode and sequential, they stack up across the stages. You can't do them at the same time.

</details>

**Reiner Pope**: 没错。

<details>
<summary>Original English</summary>

**Reiner Pope**: That’s right.

</details>

**Reiner Pope**: 这又回到了这个问题，即**纵向扩展**的大小是否与过去几年 **AI 模型大小**的变化有关，无论是通过**训练**还是**推理**？我们讨论了**跳的延迟**。还有**仅 tmem 的延迟**。**内存时间延迟**实际上通过更大的**纵向扩展域**得到了**极大的改善**。我在这里回想一下 **tmem**。**权重**的 **tmem** 等于**总参数**的数量除以**内存带宽**。

<details>
<summary>Original English</summary>

**Reiner Pope**: This brings us back to the question then, is the size of the scale-up at all relevant to why AI model sizes have been what they have been over the last few years, whether through training or through inference? We talked about latency of the hop. There is also just the tmem latency. The memory time latency is actually massively improved by larger scale-up domains. I'll recall tmem down here. tmem for the weights was equal to the number of total parameters divided by the memory bandwidth.

</details>

**Dwarkesh**: 我们这里谈论的是哪个**内存带宽**？它只是一个 **GPU** 吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Which memory bandwidth are we talking about here? Is it just one GPU?

</details>

**Reiner Pope**: 它是**我可以在并行中加载这些权重**的 **GPU** 数量。我不能在并行中使用不同的**流水线阶段**，因为它们不是同时运行的，但我可以在并行中使用我的**纵向扩展域**中的所有 **GPU** 来加载权重。这实际上**非常有效**。基本上，我这里会有一个项，这个**内存带宽**项本身等于**纵向扩展大小**……

<details>
<summary>Original English</summary>

**Reiner Pope**: It is the number of GPUs that I can use in parallel to load these weights. I can't use different pipeline stages in parallel because they're not running at the same time, but I can use all the GPUs in my scale-up domain in parallel to load the weights. This is actually extremely effective. Basically, I end up with a term here, this memory bandwidth term itself is equal to scale-up size...

</details>

**Dwarkesh**: 乘以**每个 GPU 的内存带宽**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Times memory bandwidth per GPU.

</details>

**Reiner Pope**: 是的。乘以 **GPU 带宽**。这个项没有增加很多。它可能每代增加 **1.5** 或 **2** 倍，但这个从 **Hopper** 增加了 **8** 倍。所以**更大规模扩展**之所以重要，不是因为整个**规模扩展**的**内存容量**，而是**内存带宽**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah. Times GPU bandwidth. This term doesn't increase a lot. It maybe increases 1.5 or 2x per generation, but this one increased by a factor of 8 from Hopper. So the reason the bigger scale-up matters, it's not the memory capacity of the whole scale-up, but really the memory bandwidth.

</details>

**Dwarkesh**: 是的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Yeah.

</details>

**Reiner Pope**: **流水线**完全解决了**容量问题**，但**纵向扩展**大小有助于解决**带宽问题**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Pipelining totally solves the capacity problem, but scale-up size helps solve the bandwidth problem.

</details>

**Dwarkesh**: **带宽问题**帮助你实现**更长的上下文长度**，这随着这些模型变得更具**代理性**而变得越来越相关。

<details>
<summary>Original English</summary>

**Dwarkesh**: And the bandwidth problem helps you do longer context lengths, which is more and more relevant as these models get more agentic.

</details>

**Reiner Pope**: 它让你首先能够以**更低的延迟**运行模型。如果我只是做一个**非常稀疏**的模型，并且它在一个小的 **H100** 盒子里，**延迟**会非常高。

<details>
<summary>Original English</summary>

**Reiner Pope**: It lets you just run the model at lower latency as a first thing. If I just do a very sparse model and it's on a little H100 box, the latency will be really high.

</details>

### 模型训练与推理成本

**Dwarkesh**: 一个非常离题的问题。有**Chinchilla 缩放定律**，它告诉你一个模型应该相对于你将要训练的数据量有多大。但现在，显然你不仅仅是试图优化能够通过训练计算获得的最高质量模型。你希望用户能够通过训练和推理计算的混合获得最佳结果。所以有一个问题是，你**应该过度训练一个模型多少**，以便将**训练和推理**分摊的计算**最小化**以获得一定的性能。但现在有了**强化学习（RL）**，还有另一个考虑因素，那就是你将进行一定量的**预训练**。该**预训练**将用于 **RL 生成**和最终用户的**推理**。这里我说的**过度训练**是指，虽然从**训练计算**的角度来看，拥有一个更大的模型，训练时间更短，因为它学习速度更快，效率会更高，但你可能会得到一个更小的模型，花费比你本来会花更多的计算来训练它，但现在将其提供给用户更便宜。

<details>
<summary>Original English</summary>

**Dwarkesh**: A super tangential question. There's Chinchilla scaling, which tells you how big a model should be relative to the amount of data you're going to train it on. But now, obviously, you're not just trying to optimize for the highest quality model you could get with training compute. You want the best results a user can get with a mixture of training and inference compute. So there's a question of how much you should over-train a model such that compute amortized over training and inference is minimized to get a certain performance. But now with RL, there's another consideration which is, you're going to do some amount of pre-training. That pre-training will be used both for RL generation and then for inference for the final user. By over-training here I mean that while it would have been more efficient just from a training compute perspective to have a bigger model that you train for less time because it can learn faster, maybe you get a smaller model, spend more compute training it than you otherwise would have, but now it's cheaper to give it to users.

</details>

**Dwarkesh**: 让我把问题说得更具体。基本上，模型比**Chinchilla 最优**的**过度训练**了多少？以及这是否因为**RL 生成**而改变？

<details>
<summary>Original English</summary>

**Dwarkesh**: Let me make the question more concrete. Basically, how much more than Chinchilla optimal are models over-trained? And has that changed as a result of RL generation?

</details>

**Reiner Pope**: 这是一个我们必须进行**猜测**的地方，因为更新的**缩放定律**和**模型流量**没有报告，所以我们必须猜测。一种看待它的方式……让我首先提出一个**普遍的启发式主张**。如果我有一些成本，并且我有一个**总成本**是**成本 A** 和**成本 B** 的总和，比如这可能是**训练成本**，这是**推理成本**，我想最小化这个总和……

<details>
<summary>Original English</summary>

**Reiner Pope**: This is a place where we have to do a bit of guesswork because the updated scaling laws and the model traffic are not reported, so we have to guess there. One way to look at it… Let me first just make a general heuristic claim. If I have some cost, and I've got a total cost which is a sum of cost A and cost B, like maybe this is the training cost and this is the inference cost, and I want to minimize this sum…

</details>

**Reiner Pope**: 对于许多曲线，最小值往往出现在**成本相等**的地方。这是一种**启发式主张**，但有很多例子证明它是真的。例如，一个是 **1/x**，另一个是 **x**，它们往往在它们相等的地方达到最小值。对于 **ex** 和 **e-x** 以及所有其他类似的情况也是如此。基本上，我有一条曲线下降，另一条曲线上升，它们往往在这个**等价点**达到最小值。

<details>
<summary>Original English</summary>

**Reiner Pope**: For many curves, the minimum tends to be where the costs are equalized. That's something of a heuristic claim, but there are many examples where it's true. Where one is 1/x and the other one is x, for example, they tend to be minimized at the point where they equal each other. It's also true for ex and e-x and all kinds of other things. Basically, I've got some curve that's going down, some other curve that's going up, and they tend to be minimized at this equal point.

</details>

**Reiner Pope**: 启发式地，我将推测**你描述的设置**也是如此。实际上要证明这一点，需要查看**缩放定律**并拟合这些奇怪的**指数**，但遵循**幂律**的事物往往具有这种特性。所以我只是提出这个主张，然后继续。我们要说**我们想平衡训练成本和推理成本**。我们可以全面地做到这一点。

<details>
<summary>Original English</summary>

**Reiner Pope**: Heuristically, I will conjecture that that is true for the setup you described as well. Actually showing that would be true would require looking at the scaling laws and fitting these weird exponents, but things that follow power laws tend to have this property. So I'll just make that claim and move on. We're going to say that we want to equalize the cost of training and the cost of inference. We can do all of it in general.

</details>

**Reiner Pope**: **预训练的成本**，那就是**激活参数**的数量乘以**预训练数据**。这里有一个 **6** 的因子，是 **FLOPs** 的数量。有著名的 **6ND 公式**。

<details>
<summary>Original English</summary>

**Reiner Pope**: The cost of pre-training, that's the number of active params times the data on pre-training. There's a factor of 6 out here, which is the number of FLOPs. There's the famous 6ND formula.

</details>

**Reiner Pope**: 然后在 **RL** 中，我们大约有相同的东西。我们有相同数量的**激活参数**，但现在**数据量**是 **RL 数据**。这里有这个额外的**效率乘数**，或者**低效率**……

<details>
<summary>Original English</summary>

**Reiner Pope**: Then in RL, we have approximately the same thing. We've got the same number of active parameters, but now the amount of data is the RL data. There is this extra efficiency multiplier, or inefficiency...

</details>

**Dwarkesh**: 这就是你没有训练所有**回滚**的事实。

<details>
<summary>Original English</summary>

**Dwarkesh**: Which is the fact that you're not training on all your rollouts.

</details>

**Reiner Pope**: 嗯，有那个，然后另一个，也许更大的**低效率**是这涉及大量的**解码**。通常**解码**的 **MFU** 比**训练**低。

<details>
<summary>Original English</summary>

**Reiner Pope**: Well, there's that, and then the other, perhaps even bigger inefficiency is that this involves a substantial amount of decode. Often decode runs at less MFU than training.

</details>

**Dwarkesh**: 好的。所以如果你在 **RL** 中每生成一个**反向传播**，那将是 **6ND**。所以这可能是一个更小的数字，对吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay. So if you're doing a backward pass on every single generation in RL, it would be 6ND. So this could be a smaller number, right?

</details>

**Reiner Pope**: 它至少是**二**，因为那是下限……在**二到六**之间。

<details>
<summary>Original English</summary>

**Reiner Pope**: It would at least be two, because that's the lower... Somewhere in the range of two to six.

</details>

**Reiner Pope**: 我们说大约在**二到六**之间，就到这里吧。然后我们可以加上**推理成本**。**推理成本**是二，**激活参数**的数量乘以**推理数据**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We'll say somewhere in the range of two to six and leave it at that. Then we can add in the inference cost. The inference cost is two, the number of active parameters times the data in inference.

</details>

**Dwarkesh**: 抱歉，我想我刚才说得很混乱。对于听众来说，**每个参数**的**前向加后向**是 **6**。**仅前向**是 **2**。这就是为什么 **RL**，你肯定会生成所有轨迹，但你可能训练或不训练所有轨迹，是 **2 到 6**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, I think the way I said it was super garbled. Just for the audience, forward plus backwards per parameter is 6. Forward alone is 2. That's why RL, where you're definitely going to generate all the trajectories but you might or might not train all the trajectories, is 2 to 6.

</details>

**Reiner Pope**: 是的。谢谢。然后**推理**只是 **2**。我们将解决这些三项的**基本相等性**。那就是人们的**大致范围**。实验室有更多关于**进行更多 RL**（例如）与**进行更多预训练**的有用信息。我没有这些信息，但我认为一个好的估算值是**三分之一**的分配。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yes. Thank you. And then inference is just 2. We're going to solve for essentially equality of all three of these terms. That is the ballpark of where people are going to be. Labs have more information on what is productive in doing more RL, for example, versus doing more pre-training. I don't have that information, but I think a good ballpark is a 33% split between each of them.

</details>

**Dwarkesh**: 我不确定我理解这种直觉。另一个幼稚的模型可能是 **RL** 加**预训练**是 **50%**，**推理**是 **50%**。

<details>
<summary>Original English</summary>

**Dwarkesh**: I'm not sure I understand the intuition for that. Another naive model could have been that RL plus pre-training would be 50% and inference would be 50%.

</details>

**Reiner Pope**: 这也是一个有效的答案。因为这是**启发式**的，所以我无法真正为其中一个辩护。它们的差异不大。**33%** 与 **25%** 只有很小的差距。让我们选择其中一个。全部相等似乎足够简单，所以我们只要求它们相等。这非常简单。我们可以立即看到**激活参数**的数量完全消失了，所以我们把它分解出来。我们只是说**预训练数据**——我决定用你的方法，它更好一点——加上……

<details>
<summary>Original English</summary>

**Reiner Pope**: That's also a valid answer. Because this is heuristic, I can't really argue for one versus the other. They don't differ by that much. Thirty-three versus twenty-five is only a small factor off. Let's pick one of them. All equal seems simple enough, so we're just going to solve for equality of them. It's pretty straightforward. We can immediately see that the number of activated parameters totally disappears, so let's factor that out. We're going to just say that data in pre-training—I decided to do it your way, it's a little bit nicer—plus...

</details>

**Reiner Pope**: 哦，我这里也没有**低效率**。**预训练数据**加上某个**阿尔法**倍的 **RL 数据**将最终等于某个**贝塔**倍的**推理数据**。让我们大致估算一下**阿尔法**。这个**阿尔法**可能在 **2 到 6** 之间。从这项与这项相比，超过 **6**。然后我们有一个**低效率项**，我想说可能在 **30%** 左右。所以这个**阿尔法**将是**十分之一**左右。而这里的**贝塔**实际上是相同的。它是三分之一。它是**三分之一乘以 30%**。所以它也等于**十分之一**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Oh, I didn't have the inefficiency over here either. Data in pre-training plus some multiple of α times the data in RL is going to end up equal to some β times the data in inference. Let's just roughly size the α. This α is maybe somewhere in the range of 2 to 6. Over 6, from this term compared to this term. And then we've got an inefficiency term, which I would say is maybe in the range of 30%. So this alpha is going to be something like 1/10. And this β here is actually the same. It's a third. It's one third times 30%. So it also equals 1/10.

</details>

**Dwarkesh**: 如果它们都是**十分之一**，那是否意味着 **RL** 永远没有**反向传播**？

<details>
<summary>Original English</summary>

**Dwarkesh**: If both of them are one in ten, that kind of implies that there's never a backward pass on RL?

</details>

**Reiner Pope**: 是的。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah.

</details>

**Reiner Pope**: 好的，我们可以把这个变成**十分之二**。再大一点。再写一次，这是**十分之二**，这是**十分之一**。你拥有的**推理令牌**数量仅仅是**每秒数亿个令牌**乘以我的模型在**部署两个月**后才发布下一个版本。这应该决定 **RL** 和**预训练**中的令牌数量。

<details>
<summary>Original English</summary>

**Reiner Pope**: Okay, we can make this 2/10. Make it a bit bigger. Just write it out once more, this is 2/10, this is 1/10. The number of inference tokens you have is just a function of hundreds of millions of tokens per second times my model is deployed for two months before I ship to the next version. That should determine the number of tokens in RL and pre-training.

</details>

**Reiner Pope**: 我想我们没有在**预训练**和 **RL** 之间进行等价计算，所以我们在这里进行。**预训练数据**应该等于**十分之二的 RL 数据**，以便它们在成本上等价。

<details>
<summary>Original English</summary>

**Reiner Pope**: I guess we didn't do the equivalence between pre-training and RL, so we'll do that here. Data in pre-training should be equal to 2/10 data in RL for them to be cost equivalent.

</details>

**Dwarkesh**: 抱歉，是**十分之一**。我搞反了。

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, 1/10. I got it backwards.

</details>

**Reiner Pope**: 当它**效率低下**时，我们支付更多的成本，所以这需要是**十分之一**。追溯回去……这最终实际上是，如这里所写……这就像 **1.5**，这是 **1**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We pay more cost when it's inefficient, so this needs to be 1/10. Tracing this back… This thing ends up actually being, as written here… This is like 1.5, and this is one.

</details>

**Dwarkesh**: 数十亿美元的计算刚刚流向了另一个方向。

<details>
<summary>Original English</summary>

**Dwarkesh**: Billions of dollars worth of compute just flowed in the other direction.

</details>

**Reiner Pope**: 没错？

<details>
<summary>Original English</summary>

**Reiner Pope**: Right?

</details>

**Reiner Pope**: 我认为如果你用电子表格进行建模，你可能会注意到何时**资金流失**。所有这些最终都接近，正如这里建模的那样。这个 **30%** 可能有点**过于慷慨**了。所以我们说这里大约是 **1.5**，这里是 **1**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think if you do it with a spreadsheet and actually model it out, you might notice when the money’s going down the drain. All of these end up being close in, as modeled here. This 30% may have been a little bit too generous. So let's say something like 1.5 here, and leave this as a one here.

</details>

**Reiner Pope**: 我想在这一点上，你几乎可以直接读出来。**推理令牌**的数量应该与**预训练令牌**的数量大致相同，这应该与 **RL 令牌**的数量大致相同，在我们无法推断的因素范围内。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think at this point, you can almost read it off. The number of inference tokens should be about the same as the number of pre-training tokens, which should be about the same as the number of RL tokens, within factors that we're not able to reason about.

</details>

**Dwarkesh**: 抱歉，我犯了一个基本的代数错误。看起来**RL 令牌**应该比**预训练令牌**少，对吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry for making a basic algebra mistake. It seems like there should be fewer RL tokens than pre-training tokens?

</details>

**Reiner Pope**: 一般来说是正确的。因为 **RL** 在**机器时间**方面效率较低，如果你试图**平衡 RL 和预训练时间**，那么你应该有更少的令牌才能拥有相同的**墙上时间**。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's in general right. Because RL is less efficient in terms of machine time, if you're trying to equalize the RL and pre-training time, then you should have fewer tokens in order to have the same wall time.

</details>

**Dwarkesh**: 这都很有趣。我从未从**平衡数据**的角度考虑过这个问题。

<details>
<summary>Original English</summary>

**Dwarkesh**: This is all quite interesting. I never thought about it in terms of equalizing data.

</details>

**Reiner Pope**: 我认为从**平衡成本**开始是正确的，但根据你**建模成本**的方式，这接近于**平衡数据**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think starting with equalizing in cost is right, but depending on how you model the cost, this comes close to equalizing in data.

</details>

**Dwarkesh**: 所以为了**最优地训练 GPT**，每个使用 **GPT-5** 的用户，他们流式传输的总令牌量应该等于**预训练**中投入的总量。而**预训练**中投入的总令牌量是**所有人类知识的总和**。

<details>
<summary>Original English</summary>

**Dwarkesh**: So for GPT to be trained optimally, every single user who uses GPT-5, the total amount of tokens that they stream should equal the total amount that has gone into pre-training. And the total amount of tokens that have gone into pre-training is the sum of all human knowledge.

</details>

**Reiner Pope**: 每个模型都应该在其输入上生成**人类知识的总和**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Each model should generate the sum of human knowledge on the output that it gets on the input.

</details>

**Dwarkesh**: 是的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Yeah.

</details>

**Reiner Pope**: 人们会犯哪种错误？如果你认为人们的**预测能力**不完美，而且你还有可能制作出一个**不是前沿模型**然后将其丢弃的模型，那么这会改变**成本权衡**，因为**推理**存在一些概率。你应该将**推理令牌**的数量降低一定量。

<details>
<summary>Original English</summary>

**Reiner Pope**: Which way are people going to err? If you think that people's power of prediction is not perfect, and also you run the risk that you make a model that is not a frontier model and then you just throw it away, then that changes the cost trade-off because there's some probability that applies to the inference. And you should derate the inference tokens by some amount.

</details>

**Dwarkesh**: 没错。

<details>
<summary>Original English</summary>

**Dwarkesh**: Right.

</details>

**Dwarkesh**: 我们能倒推出一个给定大小的模型比**Chinchilla 最优**的计算量多多少吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Can we back out how much more compute than Chinchilla optimal for a given sized model?

</details>

**Reiner Pope**: 我想我们在这里必须做一些**实际的假设**。**推理令牌**，我们应该完全能够计算出来，对吗？假设**几亿**。也许现在是**每秒五亿个令牌**，我真的不知道。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think we just have to make some real-world assumptions here in order to do that. The inference tokens, we should totally be able to count, right? Let's say a few hundred million. Maybe it's five hundred million tokens a second now, I don't really know.

</details>

**Dwarkesh**: **每秒五亿个令牌**乘以。一个模型在**两个月**后才过时？

<details>
<summary>Original English</summary>

**Dwarkesh**: Five hundred million tokens a second times. A model is deployed for two months before it becomes obsolete?

</details>

**Reiner Pope**: 我无法在脑子里计算出来。你能输入到电脑里吗？

<details>
<summary>Original English</summary>

**Reiner Pope**: I can't do this in my head. Can you type it into a computer?

</details>

**Dwarkesh**: **2.6 x 10^15**。

<details>
<summary>Original English</summary>

**Dwarkesh**: 2.6 x 1015.

</details>

**Reiner Pope**: 好的。**2.6 x 10^15**。这个数字可能太大了，因为这将会是**一个系列中的多个模型**。让我们把它**缩小 5 倍**或**缩小 10 倍**或类似的情况。所以我们估计**每个特定模型**每秒大约**五千万个令牌**。模型运行**两个月**。这大约是**两百万亿个令牌**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Okay. 2.6 x 1015. This number is probably too large because this is going to be multiple models in a family. Let's make it 5x smaller or 10x smaller or something like that. So we're estimating maybe fifty million tokens per second, per specific model. The model is live for two months. This comes out to around two hundred trillion tokens.

</details>

**Reiner Pope**: 然后我们想将它与**前沿模型**上的**激活参数**进行比较。我实际上不知道最新的谣言。

<details>
<summary>Original English</summary>

**Reiner Pope**: And then we want to compare that to active parameters on a frontier model. I don't actually know the latest rumors.

</details>

**Dwarkesh**: 你知道吗？有人告诉我**一百五十万亿**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Do you know? Somebody told me a hundred and fifty trillion.

</details>

**Reiner Pope**: **激活参数**？

<details>
<summary>Original English</summary>

**Reiner Pope**: Active parameters?

</details>

**Dwarkesh**: 抱歉，我指的是**令牌**。在**一百五十万亿个令牌**上训练。

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, I meant tokens. Trained on a hundred and fifty trillion tokens.

</details>

**Reiner Pope**: 有趣。这实际上很相似。所以**预训练数据**。这没有很好的引用，但没关系。

<details>
<summary>Original English</summary>

**Reiner Pope**: Interesting. Which is similar. That's actually similar. So data on pre-training. This is not well-cited but it’s fine.

</details>

**Reiner Pope**: 我认为通常**激活参数**的数量可能在**千亿**左右。也许更大一点。所以乘以 **20** 得到 **Chinchilla 令牌数**。所以 **Chinchilla**，**DChinchilla**，大约是**两万亿**。我们看到我们大约是它的**一百倍**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think often the number of active parameters could be in the range of a hundred billion, something like that. Maybe a bit larger. So multiply by 20 to get the Chinchilla token count. So Chinchilla, DChinchilla, would be around two trillion. We see we're about a hundred times larger than that.

</details>

**Dwarkesh**: **DChinchilla** 实际上是什么意思？

<details>
<summary>Original English</summary>

**Dwarkesh**: What does DChinchilla actually mean?

</details>

**Reiner Pope**: 我猜是 **Chinchilla 缩放定律**会推荐的**预训练令牌数**。

<details>
<summary>Original English</summary>

**Reiner Pope**: The token count for pre-training that the Chinchilla scaling law would recommend, I guess.

</details>

**Dwarkesh**: 哦，我明白了。所以**过度训练**了多少？

<details>
<summary>Original English</summary>

**Dwarkesh**: Oh, I see. So how much is it over-trained?

</details>

**Reiner Pope**: 明白了。**两百万亿**或**一万亿参数**与**两万亿 Chinchilla 最优**的比率，就是**过度训练**的量。

<details>
<summary>Original English</summary>

**Reiner Pope**: Got it. The ratio of this two hundred trillion or a hundred trillion parameters over the Chinchilla optimal of two trillion, that's the amount it's over-trained.

</details>

**Dwarkesh**: **一百倍的过度训练**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Which is a factor of a hundred over-trained.

</details>

**Reiner Pope**: **一百倍**。所以如果你考虑这一点，在正确的范围内，仅仅通过思考你如何**平衡所有计算**……如果 **OpenAI** 也意识到这一点，并且他们每秒服务一定数量的令牌，这告诉你**预训练 GPT-5 投入了多少数据**。即使有 **50%** 的误差，你也可以从**第一性原理**推导出这些数字，这太疯狂了。

<details>
<summary>Original English</summary>

**Reiner Pope**: A hundred. So if you consider this right here, to the extent this is in the right ballpark, just by thinking about how you want everything to be equal in terms of compute… If OpenAI also realizes that and they're serving a certain amount of tokens per second, that tells you how much data went into the pre-training of GPT-5. Even if it's 50% off or something, it is wild that you can first-principles these kinds of numbers.

</details>

**Reiner Pope**: 这就是为什么你应该到处都使用**近似值**，因为这里有很大的误差范围。但仅仅**设置 A 等于 B** 并找出答案，这有点令人振奋。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is why you should just approximate everywhere, because there are big error bars on this. But it's kind of empowering to just set A equal to B and figure it out.

</details>

**Dwarkesh**: 这太酷了。

<details>
<summary>Original English</summary>

**Dwarkesh**: That's super cool.

</details>

### API定价与内存成本

**Dwarkesh**: 好的，本着推导的精神，我们可以公开查找这些模型的 **API 价格**，也许我们可以从中了解一些信息。首先，对于**更长的上下文**，如果超过 **200k** 令牌，**Gemini 3.1** 将比低于 **200k** 令牌时**贵 50%**。从高层次上讲，我理解为什么会这样，但为什么**偏偏是 50%** 呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, so in the spirit of trying to deduce things, we can publicly look up the API prices of these models, and maybe we can learn something from that. First, with longer context, Gemini 3.1 is 50% more expensive if you go over 200k tokens than if you're below 200k tokens. At a high level, I understand why that might be, but why specifically 50%?

</details>

**Reiner Pope**: 为什么**偏偏是 50%**？从高层次上讲，即使在一开始，**上下文长度**的增加也会导致成本增加。我们可以回顾一下。那是**内存时间**与**计算时间**的关系。我们再次列出了之前相同的方程，**内存获取时间**（包括**权重**和 **KV 缓存**）以及**计算时间**（仅仅是**权重**的**矩阵乘法**）。我还将绘制**成本曲线**，但这次我将其绘制为**上下文长度**的函数，而不是**批处理大小**的函数。

<details>
<summary>Original English</summary>

**Reiner Pope**: Why specifically 50%? The high level, even in the first place, is that there is some amount of increasing cost with context length. We can bring that back up. That was the memory time versus the compute time. We've put up these same equations from before, of the time for memory fetches which is the weights and the KV cache, and then the time for the compute which is just the matrix multiplications for the weights. I will also draw the cost curve, but this time I'll do it as a function of context length instead of batch size.

</details>

**Reiner Pope**: 所以这是**成本曲线**作为**上下文长度**的函数。我们将绘制**计算**。**计算成本**实际上是**上下文长度**的**常数**。这里**不依赖于上下文长度**。实际上，有一些依赖性，但非常轻微，所以我们将忽略它。所以这是**计算时间**。

<details>
<summary>Original English</summary>

**Reiner Pope**: So this is the cost curve as a function of context length. We'll draw the compute. The cost of the compute is actually constant as a function of context length. There's no dependence here on context length. In reality, there is some dependence, but it is very mild, so we'll ignore it. So this is the time for the compute.

</details>

**Reiner Pope**: 然后我们还将绘制**内存获取**对**上下文长度**的依赖性。它从一个大数字开始（对于**权重**），然后随着**上下文长度**的增加而逐渐增长。也许从这里开始，然后随着**上下文长度**的增加而逐渐增长。所以，你取最大值，你会看到这里有一个**拐点**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Then we'll also draw the dependence of the memory fetch on context length. This starts at a large number for the weights and then grows gradually with the context length. Maybe starting here, and then grow gradually with context length. And so, you take the maximum and you see there is this inflection point here.

</details>

**Reiner Pope**: 所以这是 **Gemini** 可能支付的成本。然后你思考，你如何在此之上建立**定价结构**？你希望确保无论**上下文长度**是多少，你仍然有利可图。所以我们有一个**两级定价结构**。也许我们有一些东西看起来像这样，直到某个程度。

<details>
<summary>Original English</summary>

**Reiner Pope**: So this is the cost that Gemini might be paying. And then you think, how might you put a pricing structure on top of that? You would like to ensure that no matter what the context length is, you are still profitable. So we've got a two-tier pricing structure. Maybe we've got something that looks like this up to some extent.

</details>

**Reiner Pope**: 我认为这说明了一些问题，鉴于跳跃点在 **200k**，这可能意味着这在某种程度上与这个**交叉点**对齐。也许不完全对齐。我们实际上可能甚至可以完成那个计算，看看它落在哪里。我们可以通过对**激活参数**的数量做一些假设来解决**每个令牌的字节数**。所以，解决**每个令牌的字节数**，我们假设**内存时间**和**计算时间**相等点在，比如说 **200k** 令牌。所以我们使这两个相等。我们还假设**批处理大小**足够大，以至于**权重上花费的内存时间**可以忽略不计。所以我们将忘记这一点，我们将专注于**KV 缓存**上实际花费的**内存时间**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think it says something about, given that the bump is at 200k, it probably means that this is somewhat aligned with this crossover point. Maybe not exactly aligned with it. We can actually probably even complete that calculation just to see where it lands out. We can solve for the number of bytes per token if we make some assumptions about the number of active parameters. So solving for the number of bytes per token, we're going to assume the point where we equalize the time of memory and the time of compute is at, let's say, 200k tokens. So we equalize these two. We're also going to assume that the batch size is large enough that the memory time spent on weights is negligible. So we'll forget about this, and we'll focus on the actual memory time spent on KV cache.

</details>

**Reiner Pope**: 结果是，复制这一项，**批处理**乘以**上下文长度**乘以**每个令牌的字节数**除以**内存带宽**将等于**激活参数**的数量除以 **FLOPs**。

<details>
<summary>Original English</summary>

**Reiner Pope**: That ends up saying, copying this term over, batch times length of context times bytes per token over memory bandwidth is going to be equal to the number of activated params over FLOPs.

</details>

**Reiner Pope**: 然后我们将解决**每个令牌的字节数**。**批处理大小**在这里缺失了。它出现在这里，然后我们到达这里时它就抵消了。我漏掉了**上下文长度**。所以我们可以代入数字。这是我们之前看到的数字的倒数。这是 **1/300**，这在许多不同的硬件平台上都相当稳定。我们推测性地说，也许**激活参数**的数量是**千亿**。我们说**上下文长度**是 **200k**。

<details>
<summary>Original English</summary>

**Reiner Pope**: And then we're going to solve for bytes per token. Batch size was missing here. It shows up here, and then it cancels out by the time we get to here. And I dropped the length of context. So we can plug in numbers. This is the reciprocal of the number that we saw before. This is 1/300, which is reasonably stable across many different hardware platforms. We conjecturally said that maybe the number of activated parameters is a hundred billion. The length of the context we said was 200k.

</details>

**Reiner Pope**: 这里出了点问题。**上下文长度**应该在分母上，而不是分子上。**1667**。差不多**两千字节**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Something is wrong here, though. Length of the context should be on the denominator, not the numerator. 1667. Almost two kilobytes.

</details>

**Dwarkesh**: 那实际上是合理的。

<details>
<summary>Original English</summary>

**Dwarkesh**: That is plausible, actually.

</details>

**Reiner Pope**: 你说大约**两千字节**。让我们做个**健全性检查**，看看这可能是什么。人们有两种机制可以用**少量字节**处理**注意力**。一种是**密集注意力**，它在层之间大量重用。**Character AI** 有一篇博客文章谈论了这一点，交替使用**长上下文**和**短上下文**。在 **Character AI** 这种模型中（也出现在 **Gemma** 模型中），**全局上下文**——我们这里讨论的实际上就是这个——在所有层之间共享。要将其转换为**千字节**，你可以通过，例如，一个典型的 **dhead 128** 来实现。

<details>
<summary>Original English</summary>

**Reiner Pope**: You said around two kilobytes. Let's just do a sanity check for what this could be. There are two mechanisms that people do attention with a small number of bytes per token. One is dense attention with a lot of reuse across layers. Character AI has a blog post talking about that, alternating long and short context. In the Character AI kind of model, which also showed up in the Gemma models, the global context—which is really what we're talking about here—was shared across all the layers. To get this to kilobytes, you could get that, for example, as a dhead of 128, which is typical.

</details>

**Reiner Pope**: 那么**字节数**通常是**注意力层数**乘以二乘以 **dhead** 乘以 **KV 头数**。这是**每层唯一的上下文数**。你是在**许多层之间共享上下文**，还是只使用一次？在 **Character AI** 这种模型中，这个数字是 **1**。我们说过这是 **128**。这是一个选择，通常范围从 **1**……抱歉，我指的是 **KV 头**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Then the number of bytes is typically the number of attention layers times two times dhead times the number of KV heads. This is the number of unique contexts per layer. Do you share the context across many layers, or do you use it only once? In the Character AI-like models, this number is one. We said this is 128. This is a choice which typically ranges from one... Sorry, this is KV heads, I meant.

</details>

**Dwarkesh**: **头**和 **KV 头**的区别在于……

<details>
<summary>Original English</summary>

**Dwarkesh**: The difference between a head and a KV head is that…?

</details>

**Reiner Pope**: **KV 头**是存储在内存中的头，存储**之前令牌的内容**。**Q 头**是**检索头**。它们只在临时使用，由**注意力令牌**使用。在这个**自回归上下文**中，我所有的上下文都关联着 **KV 头**，然后这个新令牌关联着 **Q 头**。但是这个头，**128**。哦，抱歉。这个 **d-head** 是**向量的维度**。

<details>
<summary>Original English</summary>

**Reiner Pope**: The KV heads are the heads that are stored in memory, store the contents of the previous tokens. The Q heads are the retrieval heads. They're only used temporarily and they’re used by the attending token. In this autoregressive context, I've got KV heads associated with all of the contexts, and then Q heads associated with this new token here. But this head, the 128. Oh, sorry. This d-head is the dimension of the vector.

</details>

**Reiner Pope**: **KV 头**的数量通常在 **1 到 8** 之间。通过，例如，有 **8** 个 **KV 头**和一个 **d-head 128** 来获得这个是完全合理的。这正好给你这个数字。或者你可以有更少的 **KV 头**，但有更多的层。这是通过**密集注意力**实现的方法。还有一种通过**稀疏注意力**实现的方法，你可以增加所有这些数字，但随后你有一个**稀疏度**的倒数项。我认为这个数字是合理的，即使可能有点小。

<details>
<summary>Original English</summary>

**Reiner Pope**: The number of KV heads is typically in the range of 1 to 8. It is totally plausible to get this by, for example, having 8 KV heads and a d-head of 128. That gives you exactly this number. Or you could have fewer KV heads, but more layers. This is one way to get there via dense attention. There's also a way to get there via sparse attention, where you increase all of these numbers, but then you have a 1/sparsity term. I think this number is plausible, if maybe a little bit small.

</details>

**Dwarkesh**: 他们通过 **API 定价**泄露了这么多信息，这很有趣。

<details>
<summary>Original English</summary>

**Dwarkesh**: It's funny that they would leak so much information through their API pricing.

</details>

**Reiner Pope**: 我的意思是，你被激励以接近成本的价格定价，否则会有人抢走你的生意。

<details>
<summary>Original English</summary>

**Reiner Pope**: I mean, you are incentivized to price close to your costs because otherwise someone could scoop you.

</details>

**Reiner Pope**: 也许我们可以了解一下**输入**和**输出价格**的差异，以及这告诉我们这些模型中**解码**和**预填充**的什么信息。我想我上次查看时，它贵 **50%** 左右？我不记得了。

<details>
<summary>Original English</summary>

**Reiner Pope**: Maybe we can learn something about the difference in input versus output prices, and what that tells us about decode versus prefill in these models. I think last I checked it's 50% more expensive or something like that? I don't remember.

</details>

**Dwarkesh**: 我过去见过的是贵 **3-5** 倍。

<details>
<summary>Original English</summary>

**Dwarkesh**: What I've seen in the past is 3-5x more expensive.

</details>

**Reiner Pope**: 好的，那更有道理。所以假设它贵 **5** 倍。这是在**解码**中处理下一个令牌的计算量。

<details>
<summary>Original English</summary>

**Reiner Pope**: Okay, that makes more sense. So let's say it's 5x more expensive. This is the compute to process the next token in decode.

</details>

**Reiner Pope**: 假设你正在进行**预填充**，你不仅仅处理最近的令牌，你还并行处理所有令牌。我想说那将是这个乘以**预填充长度**？或者**通常的传递长度**。如果我们能把**解码**看作是一次传递，然后**预填充**看作是多次传递。

<details>
<summary>Original English</summary>

**Reiner Pope**: Suppose you're doing prefill, where you're not just processing the most recent token, you're processing all the tokens in parallel. I want to say that it would be this times length prefill? Or length of the pass in general. If we can think of decode as being a pass with one, and then prefill being a pass with many.

</details>

**Dwarkesh**: 好的。所以也许是**前缀**？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay. So maybe prefix?

</details>

**Reiner Pope**: 好的，**内存**。你没有为**预填充令牌**存储 **KV 缓存**。如果我们能澄清一下，我实际画一下**预填充**是如何显示的。我们进行一些这样的**解码**。我们可能实际上会回来做更多的**预填充**。如果你认为这是一个聊天会话，用户说了一些话，**AI** 生成一个响应，然后用户再说一些话，我们**预填充**这个。

<details>
<summary>Original English</summary>

**Reiner Pope**: Okay, memory. You're not storing the KV cache for the tokens that are the prefill tokens. Let's actually draw how prefill shows up here, if I may clarify. We do a bit of decode like this. We may actually come back and do more prefill. If you think this is a chat session, the user says something, the AI generates a response, and then the user says something else and we prefill this.

</details>

**Reiner Pope**: 也许这是普遍情况，而不是这个。事实上，这就像你读一个文件什么的。

<details>
<summary>Original English</summary>

**Reiner Pope**: Maybe this is the general case, rather than this. In fact, this is like you read a file or something.

</details>

**Dwarkesh**: 读文件，或者 **AI** 响应用户输入、工具调用，或者任何不是 **AI** 生成的东西。

<details>
<summary>Original English</summary>

**Dwarkesh**: Read a file or the AI is responding to a user input, tool call, or anything that's not AI-generated.

</details>

**Reiner Pope**: 好的，假设我们在这里。你之前已经计算了所有这些。所以只是**之前所有东西的 KV**。但是这个的**内存成本**是多少？

<details>
<summary>Original English</summary>

**Reiner Pope**: Okay, suppose we're here. You will have calculated all of this previously. So just the KV of everything that came before. But what is the memory cost of this?

</details>

**Reiner Pope**: 嗯，这个的**内存带宽成本**。如果你正在进行**闪存注意力**，它会——

<details>
<summary>Original English</summary>

**Reiner Pope**: Well, the memory bandwidth cost of this. If you're doing flash attention, it would—

</details>

**Dwarkesh**: 它基本上是临时的。它甚至不会进入主内存。

<details>
<summary>Original English</summary>

**Dwarkesh**: It's basically temporary. It doesn't even go to main memory.

</details>

**Reiner Pope**: 忽略它。

<details>
<summary>Original English</summary>

**Reiner Pope**: Just ignore that.

</details>

**Dwarkesh**: 没错。所以那它就只是之前所有东西了？

<details>
<summary>Original English</summary>

**Dwarkesh**: Exactly. So then it would just be everything that came before. Is it not just that then?

</details>

**Reiner Pope**: 实际上对**内存时间**没有任何调整。

<details>
<summary>Original English</summary>

**Reiner Pope**: There's actually no adjustment at all to the memory time.

</details>

**Dwarkesh**: 好的。太好了。所以这是一个非常微不足道的更改。

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay. Great. So it's a very trivial change to accommodate.

</details>

**Reiner Pope**: 这一项使其贵 **5** 倍。现在，为什么会这样？那实际上告诉我们什么？什么变量可以帮助我们限制这一点？

<details>
<summary>Original English</summary>

**Reiner Pope**: This term is making it 5x more expensive. Now, why would that be? What does that actually tell us? What variable does this help us clamp?

</details>

**Reiner Pope**: 唯一可能改变的是**计算成本**因此贵了 **5** 倍。这是**一次传递的时间**，但实际上令牌数量多得多。我们实际上想要的是**每个令牌的成本**，或者**每个令牌的时间**。

<details>
<summary>Original English</summary>

**Reiner Pope**: The only thing that could have changed is that the compute is 5x more expensive as a result. This is the time for one pass, but actually the amount of tokens is that much larger. We want the cost per token, in fact, or the time per token.

</details>

**Dwarkesh**: 我不确定我理解。这是用于处理**前缀**中的下一个令牌吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: I'm not sure I understood. This is for processing the next token in prefix?

</details>

**Reiner Pope**: 嗯，实际上是用于处理整个批次。以这个成本，我们处理了这么多令牌，即**预填充的长度**。或者我猜是**传递的长度**。不是这个前缀，而是这个成本。

<details>
<summary>Original English</summary>

**Reiner Pope**: Well, actually for processing the entire batch. At this cost, we have processed this many tokens, the length of prefill. Or I guess the length of the pass. Not this prefix, but it's this cost.

</details>

**Dwarkesh**: 好的。我们只需进行此传递。所以这贵了 **5** 倍。**输入贵 5 倍**。**输出实际上更贵**。**输出贵 5 倍**。我们想要实现的结果是**预填充是计算受限的**，而**解码是内存带宽受限的**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay. Let's just do this pass. So this is 5x more expensive. Input is 5x more expensive. Output is more expensive, in fact. Output is 5x more expensive. The result we want to work towards is that prefill is compute-limited and decode is memory bandwidth-limited.

</details>

**Reiner Pope**: 为什么我们不这样做呢？我们只需将**传递长度**放在 X 轴上，**t** 放在 Y 轴上。我们想要**每个令牌的成本**，所以它将是 **t 除以传递长度**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Why don't we do this? Why don't we just chart it with len-pass on the X-axis and t on the Y-axis. We want the cost per token, so it'll be t over length of the pass.

</details>

**Dwarkesh**: 那将是正确的。

<details>
<summary>Original English</summary>

**Dwarkesh**: That'll be right.

</details>

**Dwarkesh**: 我想我对此感到困惑。**传递长度**是……当你在做**预填充**时，这应该更高。**预填充**有一个更大的**传递长度**。

<details>
<summary>Original English</summary>

**Dwarkesh**: I guess I’m getting confused by this. Len-pass is... It seems like this should be higher when you're doing prefill. Prefill has a bigger length pass.

</details>

**Reiner Pope**: 是的。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah.

</details>

**Dwarkesh**: 但为什么它更便宜呢？为什么成本更高？

<details>
<summary>Original English</summary>

**Dwarkesh**: But then why is it cheaper? Why is the cost higher?

</details>

**Reiner Pope**: 这是除以**传递长度**。这会抵消，但所有这些都将除以**传递长度**，这将使**内存成本**更便宜。

<details>
<summary>Original English</summary>

**Reiner Pope**: It's this division by length pass. This is going to divide out, but then all of this is going to divide by length of pass, and it's going to make the memory costs cheaper.

</details>

**Dwarkesh**: 好的。那让我再想想。基本上我们会有四条不同的线。让我们先做**预填充**……

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay. Let me think about this then. Basically we'll have four different lines. Let's do prefill first...

</details>

**Dwarkesh**: 实际上，让我们先做**解码**。**传递长度**为 **1** 时，那是**解码**。当它更大时，那是**预填充**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Actually, let's do decode first. Length of the pass, when it's one, that is decode. When it is bigger, that is prefill.

</details>

**Reiner Pope**: 哦，好的。我明白了。那有道理。

<details>
<summary>Original English</summary>

**Reiner Pope**: Oh, okay. I see. That makes sense.

</details>

**Reiner Pope**: 回到正题。所以 **t 计算**，如果你基本上只是这个除以**传递长度**，所以只是这个量。这实际上不随 **t** 而变化，所以它将是这样一条**平坦的线**。这是 **t 计算**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Getting back to it. So tcompute, if you have basically just this divided by len-pass, so just this amount. This actually does not vary based on t, so it'll just be some flat value like this. And this is tcompute.

</details>

**Reiner Pope**: 这是——

<details>
<summary>Original English</summary>

**Reiner Pope**: And this is—

</details>

**Dwarkesh**: 那是**解码**。

<details>
<summary>Original English</summary>

**Dwarkesh**: That's decode.

</details>

**Reiner Pope**: **解码**。没错。现在 **t 内存**，我们有整个东西除以**传递长度**。嗯，上面是什么并不重要，它只会是这样一条线。假设这是 **t 内存**。这又是**解码**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Decode. Right. Now tmem, we have this whole thing divided by len-pass. Well, it doesn't really matter what's up there, it'll just be something that looks like this. Let's say this is tmem. This is decode again.

</details>

**Reiner Pope**: 所以随着**前缀**或**传递的长度**增加，你的**内存带宽时间**下降，这意味着就你以前受**内存带宽**瓶颈的程度而言，你可以避免受**内存带宽**瓶颈。他们为**预填充**收取的费用比**解码**少 **5** 倍这一事实表明，他们**在内存带宽上受到了相当大的瓶颈**，以至于对他们来说——因为 **t** 等同于成本，它是租用计算的成本——这将是 **1**，而这将是 **5**。

<details>
<summary>Original English</summary>

**Reiner Pope**: So as the length of the prefix goes up, or pass, your memory bandwidth time declines, and that means that to the extent that you were bottlenecked on memory bandwidth before, you can avoid being bottlenecked on memory bandwidth. The fact that they are charging 5x less for prefill than decode does suggest that they are bottlenecked on memory bandwidth to quite a degree, such that for them at least—because t is equivalent to cost, it's the cost of renting a compute—this would be at 1, and this would be at 5.

</details>

**Dwarkesh**: 没错。

<details>
<summary>Original English</summary>

**Dwarkesh**: That's right.

</details>

**Reiner Pope**: 所以事实上，它受到了极大的**内存带宽瓶颈**。真实的图表看起来像那样。它仍然交叉，但是的。

<details>
<summary>Original English</summary>

**Reiner Pope**: So it is, in fact, tremendously memory bandwidth bottlenecked. The real graph looks something like that. It still crosses, but yeah.

</details>

**Dwarkesh**: 没错。让我这样做。这是**解码**中**内存**和**计算时间**之间的差距。

<details>
<summary>Original English</summary>

**Dwarkesh**: Exactly. Let me do it this way. This is the gap on decode between the memory and the compute time.

</details>

**Dwarkesh**: 好的，有意思。另一个有趣的问题是**缓存命中**为什么便宜这么多。如果我没记错的话，**缓存命中**大约便宜 **10** 倍……根据所有这些模型的定价，**写入缓存更贵**。但如果你确实命中缓存，它就便宜 **10** 倍。

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, interesting. Another interesting one would be why cache hits are so much cheaper. If I remember correctly, cache hits are like 10x… It's more expensive to write to cache according to the pricing on all these models. But if you do hit a cache, it's 10x.

</details>

**Reiner Pope**: 大概，这是将某些东西保留在 **HBM** 中而不是将其清空的成本。但是如果它确实保留在 **HBM** 中，那么再次加载它会更便宜？

<details>
<summary>Original English</summary>

**Reiner Pope**: Presumably, this is the cost of keeping something in HBM rather than just evacuating it. But if you do keep it in HBM, then it's cheaper to load again?

</details>

**Dwarkesh**: 没错。

<details>
<summary>Original English</summary>

**Dwarkesh**: Right.

</details>

**Reiner Pope**: 你可以通过两种方式为令牌生成 **KV 缓存**。你可以通过从头开始计算它来生成它，通过底层的令牌 ID，这些 ID 非常小。或者你可以之前已经生成它并将其存储在某个内存中。**成本比率**实际上是在谈论这两种生成机制之间的比率。**缓存未命中**意味着你已将其从所有内存中删除，并且你必须直接从令牌重新计算它。

<details>
<summary>Original English</summary>

**Reiner Pope**: There are two ways you can produce the KV cache for a token. You can just produce it from scratch by computing it from the underlying token IDs, which are tiny. Or you can previously have produced it and stored it in a memory somewhere. The cost ratio is really talking about the ratio between those two mechanisms of producing it. A cache miss means you've deleted it from all your memories, and you have to recompute it from the tokens directly.

</details>

**Reiner Pope**: 你甚至可以进一步思考，你将其存储在哪个**内存层**。你可以将其存储在 **HBM** 中。除了 **HBM** 之外，还有其他更慢更便宜的内存，比如主机上的 **DDR**，或者**闪存**。你可以做的一件事是计算在每个**内存层**中存储的合理性，这与你将存储多长时间有关。我们想看看**几种不同内存层**的**存储成本**以及**重新物化**的成本。**Remat** 意味着在你删除 **KV 缓存**后从头开始重建它的成本，所以我们**重新物化**它。

<details>
<summary>Original English</summary>

**Reiner Pope**: You can even take that a step further and think about which memory tier you store it in. You could store it in HBM. There are other slower and cheaper memories than HBM, like DDR on your host or flash as well. One of the things you can do is a calculation of where it makes sense to be in each memory tier, and this is related to how long you're going to store it for. We want to look at the cost of storage in a few different memory tiers and also the cost of rematerialization. Remat means the cost to rebuild all of the KV cache from scratch after you deleted it, so we rematerialize it.

</details>

**Reiner Pope**: 基本上，这将花费**上下文的长度**。实际上，我们将查看**每个令牌的成本**，所以我们不需要随身携带这个**上下文长度**。要重新物化一个 **KV 缓存令牌**，我只需要在整个模型上运行一次**前向传递**。这将是**计算时间**。我必须以我的 **GPU** 的速度重新运行计算，然后我将其乘以我的**每个 GPU 每秒美元成本**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Basically, this is going to cost the length of the context. Actually, we'll look at the cost per token, so we don't need to carry around this length of context everywhere. To rematerialize one token of KV cache, I just need to run a forward pass on the whole model. This is going to be the compute time. I have to rerun the compute at whatever speed my GPU does it, and then I multiply it by my GPU dollars per second.

</details>

**Dwarkesh**: 抱歉，一个初级问题。为什么没有**二次项**？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, excuse a naive question. Why is there not a quadratic term?

</details>

**Reiner Pope**: 有一个**二次项**。它出现在**计算**中。作为一种近似，我选择将其删除。我快速向你展示它是什么样子。如果你看**每个令牌的成本**，或者**每个令牌的 FLOPs**，有来自进行**权重矩阵乘法**的 **FLOPs**，作为……的函数。

<details>
<summary>Original English</summary>

**Reiner Pope**: There is a quadratic term. It shows up in the compute. As an approximation, I chose to remove it. I'll just show you quickly what that looks like. If you look at the cost per token, or the number of FLOPs per token, there are the FLOPs that are coming from doing the weight matrix multiplies as a function of—

</details>

**Dwarkesh**: 那是**平坦的**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Which is flat.

</details>

**Reiner Pope**: ……**上下文长度**。然后有来自进行 **KV 缓存**的乘法次数，它随着你关注的东西的数量而线性增长。它的斜率非常低，以至于当你像这样绘制它时，它非常好地被一条**平坦的线**近似。你开始在**数百万令牌**左右注意到**二次项**或**线性项**的影响。所以它不是非常相关。

<details>
<summary>Original English</summary>

**Reiner Pope**: ...context length. And then there is the number of multiplies that comes from doing the KV cache, which goes up linearly with the amount of stuff you attend to. The slope on this is so low that when you draw it like this, it's very well approximated by a flat line. You start to notice the effect of the quadratic or the linear term up in the millions of tokens or so. So it's just not super relevant.

</details>

**Dwarkesh**: 那么，如果这是真的，为什么没有一家公司拥有**超过一百万个令牌的上下文长度**呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: So what is the reason that there's no company which has over a million token context length, if this is true?

</details>

**Reiner Pope**: **长上下文**有两个成本。一个是**内存带宽成本**，我们花了很多时间分析。就是这个东西。另一个是**计算成本**。**计算成本**几乎总是由**基本原理**强制要求，其斜率远小于**内存带宽成本**。限制你使用真正大的上下文的主要因素是**内存带宽**和**内存容量**，这正是这种效应。

<details>
<summary>Original English</summary>

**Reiner Pope**: There are two costs of long context. One is the memory bandwidth cost, which we've spent a lot of time analyzing. That's this thing. The other one is the compute cost. The compute cost is almost always forced by fundamental principles to be a much smaller slope than the memory bandwidth cost. The primary things that limit you to really large contexts are memory bandwidth and memory capacity, which is exactly this effect.

</details>

**Reiner Pope**: **Dario** 在播客中提出了这个想法，其他人也说过，“我们不需要**持续学习**来实现**通用人工智能（AGI）**，**上下文学习**就足够了。”如果你相信这一点，那么你必须认为我们必须达到**一亿令牌的上下文长度**，才能拥有一名相当于与你一起工作一个月的员工。现在，也许有了**稀疏注意力**或其他东西，情况就不再是这样了。但如果你这样认为，那么一些 **ML 基础设施**就必须改变，以允许**一亿**，比如**内存带宽**，以允许**一亿令牌的上下文长度**。

<details>
<summary>Original English</summary>

**Reiner Pope**: There's this idea that Dario said on the podcast, and others have said, which is, "We don't need continual learning for AGI, in-context learning is enough." If you believe that, then you have to think that we have to get to a hundred-million-token context length to have an employee that is the equivalent of working with you for a month. Now, maybe that's no longer true with sparse attention or something. But if you think that, then some ML infra thing would have to change to allow for a hundred million, like the memory bandwidth, to allow for a hundred-million-token context lengths.

</details>

**Reiner Pope**: **稀疏注意力**当然给你一个出路，因为你得到了**平方根**。它给你带来了很大的改进。但如果你看看**模型上下文长度**的历史，从早期的模型如 **GPT-3**，也许到 **GPT-4**——我不记得何时发生转变——它们从大约 **8K** 猛增到 **100-200K**。然后在一两年内，它们都徘徊在那里。我认为这表明这是一个**合理平衡的成本点**，大规模超越它将是**成本高昂的**。不是因为**计算成本**，而是因为**内存带宽**……

<details>
<summary>Original English</summary>

**Reiner Pope**: Sparse attention gives you a get-out for sure, because you get this square root. It gives you a big improvement. But if you look at the history of context lengths of models, from earlier models like GPT-3, maybe to GPT-4—I don't remember when the transition happened exactly—they shot up from about 8K to 100-200K. And then for the last year or two, they've all been hovering around there. I think that indicates that this is the reasonably balanced cost point, and going massively beyond that would be cost-prohibitive. Not because of the compute cost, because of the memory bandwidth...

</details>

**Dwarkesh**: 因为**内存带宽成本**，是的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Because of memory bandwidth cost, yeah.

</details>

**Reiner Pope**: 我实际上看不出有很好的方法来解决这个问题。**HBM** 就在那里。它没有变得好很多。

<details>
<summary>Original English</summary>

**Reiner Pope**: I actually don't see a very good path to solving that. The HBM is where it is. It's not getting hugely better.

</details>

**Dwarkesh**: 为什么**稀疏注意力**不能解决它呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: And why doesn't sparse attention solve it?

</details>

**Reiner Pope**: **稀疏注意力**是一个很大的改进。也许这已经被定价了。这不是无限的改进，因为如果你**太稀疏**，你就会**失去太多质量**。经验结果是**上下文长度**没有增加那么多。我认为那是因为这里没有**内存墙**的解决方案。**太稀疏**只是意味着你只关注令牌的一个非常小的子集，**质量会变差**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Sparse attention is a big improvement. Maybe that is priced in already, perhaps. It's not an infinite improvement because if you go too sparse, you lose too much quality. The empirical result is that the context lengths haven't been increasing that much. I think it's because there is no solution to the memory wall here. Going too sparse just means you're attending to a very small subset of the tokens, and the quality will get worse.

</details>

**Dwarkesh**: 很有道理。

<details>
<summary>Original English</summary>

**Dwarkesh**: Makes sense.

</details>

**Dwarkesh**: **重新合成 KV 缓存**的这些不同方法的成本是多少？

<details>
<summary>Original English</summary>

**Dwarkesh**: What is the cost of these different ways of resynthesizing the KV cache?

</details>

**Reiner Pope**: 从头开始计算它基于我的 **GPU 时间**。我必须做一定量的乘法，即我花费的 **GPU 时间**才能生成它。

<details>
<summary>Original English</summary>

**Reiner Pope**: Computing it from scratch is based on my GPU time. I have to do a certain amount of multiplies, of GPU time that I spend in order to produce it.

</details>

**Reiner Pope**: 存储在 **HBM** 中。这实际上是我的**每个令牌的字节数**。我只需要**每个令牌**拥有一定数量的**字节**，然后我需要将其存储在 **HBM** 中。它会占用我的一部分 **HBM 容量**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Storing in HBM. This really goes as my bytes per token. I need to just have some number of bytes per token, and then I need to store this in the HBM. It's going to use up some of my HBM capacity.

</details>

**Reiner Pope**: 思考这个问题的一种方式是，如果我的 **HBM** 中有太多这些东西，如果我用我没有使用的 **KV 缓存**填满我的 **HBM**，我就无法使用那个 **GPU**。我怎么给它定价？也许我说它的成本与我使用的 **HBM 比例**成正比。还有**乘以 GPU 美元**。

<details>
<summary>Original English</summary>

**Reiner Pope**: A way to think of this is that if I have too many of these things sitting in my HBM, if I fill up my HBM with just KV caches that I'm not using, I can't use that GPU. How do I price that? Maybe I say that the cost of it is proportional to the fraction of the HBM I'm using. There's also times GPU dollars.

</details>

**Reiner Pope**: 让我们再增加一个**内存层**，并说改为存储在 **DDR** 中。同样的情况也适用于**闪存**和 **DDR**。我把它们放在了错误的列中。我本来想做两列。我想区分的是，有**检索成本**，然后有**保留成本**。这是一个**每秒成本**，而这是一个**瞬时成本**。**重新物化**有**检索成本**，但**存储成本为零**，因为我们已经删除了它。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let's just do one more memory tier and say store in DDR instead. The same kind of thing goes up for flash and for DDR. I put these in the wrong columns. I meant to make two columns. The distinction I want to make is that there is the cost to retrieve, and then there's a cost to hold on. This is a cost per second, whereas this is an instantaneous cost. Rematerialization has a cost to retrieve and has zero cost to store it because we've deleted it.

</details>

**Reiner Pope**: 这是我放错位置的那个。这实际上只是**保留成本**，所以我将重写它。如果我们将它存储在 **HBM** 中，它具有这种**成本配置文件**。如果我们将它存储在 **DDR** 中，它实际上会花费一些时间。我们在这里得到同样的结果：**每个令牌的字节数**除以 **DDR 容量**乘以**每个 DDR 每秒的成本**。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is the one that I put in the wrong location. This is actually the cost just to hold on, so I will rewrite it. If we're just storing it in HBM, it has this sort of cost profile. If we store in DDR, it's actually going to take some time. We get the same thing here: bytes per token over DDR capacity times DDR cost per second.

</details>

**Reiner Pope**: 但现在这有一个**检索成本**，它高于 **HBM**，因为我们需要将其复制到 **HBM** 中。所以这是**每个令牌的字节数**除以 **DDR 带宽**。

<details>
<summary>Original English</summary>

**Reiner Pope**: But now this has a cost to retrieve that is higher than the HBM because we need to copy it into the HBM. So this is bytes per token over DDR bandwidth.

</details>

**Reiner Pope**: 然后这也会消耗一些 **DDR**。

<details>
<summary>Original English</summary>

**Reiner Pope**: And then this consumes some amount of the DDR as well.

</details>

**Dwarkesh**: 每次**纵向扩展**都有 **DDR** 和**闪存**吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: And every scale-up has DDR and flash?

</details>

**Reiner Pope**: 这实际上是一个**部署问题**，所以你可以选择。**Nvidia** 以这种形式进行部署。它两者都有。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is really a deployment question, so you can choose that. Nvidia does deploy in this form. It has both.

</details>

**Dwarkesh**: 为什么检索 **HBM** 的成本不是**字节除以内存带宽**呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: Why isn't the cost to retrieve HBM the bytes divided by memory bandwidth?

</details>

**Reiner Pope**: 这取决于你如何定义**检索**。在这里，我将**检索**定义为将其移动到 **HBM** 中，这样你就可以开始对其进行**推理**。

<details>
<summary>Original English</summary>

**Reiner Pope**: It depends what you define a retrieve to be. Here, I'm defining retrieve to be, move it into HBM so that you can start actually doing inference on it.

</details>

**Dwarkesh**: 因为如果它已经在 **HBM** 中，你可以在从 **HBM** 到 **SRAM** 的过程中进行计算？

<details>
<summary>Original English</summary>

**Dwarkesh**: Because if it's already in HBM, you can be doing compute while you're getting it from HBM to SRAM?

</details>

**Reiner Pope**: 有趣。是的，例如。

<details>
<summary>Original English</summary>

**Reiner Pope**: Interesting. Yeah, for example.

</details>

**Reiner Pope**: 这是三件事，我想我排序错了。一般来说，如果你要**平衡两种成本**，并且你有**内存层次结构**中的不同层，你应该预期随着这种**成本的增加**，这种**成本应该下降**。你可以看到零点在哪里。我应该先订购这个，然后是这个，然后是这个。如果你要**保留它很短的时间**，那么所有这些都乘以**保留时间**。这是其中之一，这个也是。

<details>
<summary>Original English</summary>

**Reiner Pope**: These are three things, and I guess I ordered them wrong. In general, if you're balancing two costs and you've got different tiers in the memory hierarchy, you should expect as this cost goes up, this cost should go down. You can kind of see where the zeros are. I should have ordered them this one first, this one second, and this one third. If you're going to hold onto it for a very short amount of time, then all of this is multiplied by the hold time. This one is, and so is this one.

</details>

**Reiner Pope**: 有趣的是，它们的**写入价格不同**。你是否在 **API** 中指定了**五分钟**与**一小时**？这表明**五分钟**是 **HBM**，**一小时**是 **DDR**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Interestingly, they have different prices to write for. Do you specify this in the API for five minutes versus an hour? Which suggests that the five minutes is HBM and the hour is DDR.

</details>

**Dwarkesh**: 我认为这是一个很好的假设。

<details>
<summary>Original English</summary>

**Dwarkesh**: I think that's a pretty good assumption.

</details>

**Reiner Pope**: 如果你看看这些数字，也可能发现它比这低一级，是 **DDR** 与**闪存**。

<details>
<summary>Original English</summary>

**Reiner Pope**: If you look at the numbers, it might also turn out that it's one tier down, and it's DDR versus flash.

</details>

**Dwarkesh**: 有意思。

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting.

</details>

**Reiner Pope**: 我会查找**价格差异**。

<details>
<summary>Original English</summary>

**Reiner Pope**: I'll look up the price difference.

</details>

**Dwarkesh**: **基本输入令牌**是**每百万令牌 5 美元**。**基础**，这意味着**重新物化**。这是 **5 美元**。

<details>
<summary>Original English</summary>

**Dwarkesh**: The base input tokens is $5 per million tokens. Base, which means remat. This is $5.

</details>

**Reiner Pope**: 那是 **5 美元**用于“**检索**”。然后写入，大概是 **HBM**，**五分钟是 6.25 美元**。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's $5 to "retrieve". And then to write, presumably HBM, for five minutes is 6.25.

</details>

**Reiner Pope**: 我们可以通过**持续时间**来确定它属于哪个**内存层**。**五分钟**与**一小时**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We might be able to determine which memory tier it is by the durations. Five minutes versus one hour.

</details>

**Dwarkesh**: 没错。

<details>
<summary>Original English</summary>

**Dwarkesh**: Exactly.

</details>

**Reiner Pope**: 我认为这可能最终是你所处**内存层**的**消耗时间**。这意味着，鉴于我知道我将**保留它五分钟**，我想选择一个**我可以在五分钟内读取的内存**。我可以在大约**每五分钟**读取整个内存一次。这就是**内存的消耗时间**。所以如果我将**存储容量**除以**存储带宽**，我希望它等于**五分钟**。我们对 **HBM** 进行了这个计算。对于 **HBM**，我们知道这个数字是 **20 毫秒**。所以 **HBM** 太小了。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think this will probably end up being the drain time of the memory tier that you're in. What that means is, given that I know I'm going to be holding something for five minutes, I would like to pick a memory that I can read every five minutes. I can read the whole memory once per five minutes, ballpark. That is the drain time of the memory. So if I take the storage capacity over storage bandwidth, I would like this to be equal to five minutes. We did this calculation for HBM. For HBM, we know that this number is 20 milliseconds. So HBM is much too small.

</details>

**Reiner Pope**: **DDR** 可能比这低一到两个数量级，所以这可能在**几秒**的量级，比如 **1 到 10 秒**。我没有记住这些数字，但一般来说，当你进入**较慢的层**时，**闪存**可能在**一分钟**的量级。然后**机械硬盘**，它大大不同，在**一小时**的量级。所以这可能实际上识别出**闪存**和**机械硬盘**的层级。

<details>
<summary>Original English</summary>

**Reiner Pope**: DDR could be about an order of magnitude or two off from this, so this is probably on the order of seconds, like 1 to 10 seconds. I don't have these numbers memorized, but generally, as you go to slower tiers, flash is plausibly on the order of one minute. And then spinning disk, which is massively different, is on the order of one hour. So this might actually identify the tiers of flash and spinning disk.

</details>

**Dwarkesh**: 抱歉，为什么这是计算？这是**存储容量**除以**带宽**吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sorry, why is this the calculation? This is the storage capacity divided by the bandwidth?

</details>

**Reiner Pope**: 你有许多不同的**内存层**，我们列出了其中四个。你选择哪个**内存层**是为了**最小化成本**。你使用了设备的多大比例？你使用了设备的一部分来**保留它**，然后你使用了设备的一部分来**检索它**。假设我使用了设备的 **10%**。我希望**平衡这两个比例**。这表明我找到了正确的东西。

<details>
<summary>Original English</summary>

**Reiner Pope**: You've got a bunch of different memory tiers, we've listed four of them. Your choice of which memory tier is about minimizing the cost. What fraction of the device are you using? You're using some fraction of the device for holding onto it, and then you're using some fraction of the device to retrieve it. Let's say I'm using 10% of the device. And I want to equalize those two fractions. That's a sign that I've hit the right thing.

</details>

**Reiner Pope**: 假设我这里有一些运行时。我将**保留**所有这些时间，所以这是**保留时间**。然后这里将有一些时间，那是**检索时间**。基本上为了**平衡这两个成本**，我希望**检索时间**等于**保留时间**乘以**容量的比例**。因为这是**检索时间**，这是我**可以同时保留多少其他东西**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Let's say I've got some runtime here. I'm going to hold on for all of this time, so this is the time-hold. And then there's going to be some amount of time here, which is time-retrieve. Basically to equalize these two costs, I want the retrieval time to be equal to the hold time times the fraction of capacity. Because this is the retrieval time, this is how many other things I can hold simultaneously.

</details>

**Dwarkesh**: 基本上，你希望将东西存储在里面足够长时间，以至于它在里面的时间是**将所有东西放入和取出的时间**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Basically, you want to store things in there for so long such that the amount of time it's in there is the time to get all your things in there and out.

</details>

**Reiner Pope**: 是的，基本上。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah basically.

</details>

**Reiner Pope**: 我认为这可能表明这两个层是**闪存**和**机械硬盘**。我很震惊地看到**机械硬盘**被使用，因为它是一种如此古老的技术。

<details>
<summary>Original English</summary>

**Reiner Pope**: I think that probably indicates that the two tiers are flash and spinning disk. I'm kind of shocked to see spinning disk being used at all, because it's such an old technology.

</details>

**Dwarkesh**: 有意思。它慢到需要**一小时**才能加载其全部容量，这也很疯狂。

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. It’s also crazy that it’s so slow that it takes an hour to load its full capacity to it in.

</details>

**Reiner Pope**: 这是一种非常没有吸引力的技术，但在某些地方很有用。

<details>
<summary>Original English</summary>

**Reiner Pope**: It’s a really unattractive technology but it’s useful in some places.

</details>

### 神经网络与密码学的架构相似性

**Dwarkesh**: 我们坐下来吧，因为我想问您一些不需要黑板的问题。您有一篇非常有趣的博客文章，其中您谈到，从高层次上讲，**不同加密协议的架构**看起来**很像神经网络**。这是一种**趋同进化**，它们都需要**混淆所有输入信息**。对于**加密协议**，它确保**哈希函数**的每个新输入都会完全**打乱**发生的事情。当然，对于**神经网络**，它们需要考虑这部分信息如何改变您应该如何看待另一部分信息。

<details>
<summary>Original English</summary>

**Dwarkesh**: We're sitting down because I want to ask you some questions that don't need a blackboard. You have this extremely interesting blog post where you talk about how, at a high level, the architecture of different cryptographic protocols looks a lot like neural networks. There's this convergent evolution where they both need to jumble information across all their inputs. For cryptographic protocols, it's to make sure that each new input into a hash function will totally scramble what happens. For neural networks, of course, they need to consider how this piece of information changes what you should make of this other piece of information.

</details>

**Dwarkesh**: 我认为那是一个**非常有趣的观点**。从高层次上讲，在某种意义上它们试图做**相反的事情**。**加密协议**试图**获取具有结构的信息并使其看起来与随机性无法区分**。**神经网络**试图**获取看起来随机的东西**——**蛋白质序列**、**DNA**、**乱码文本**——并**从中提取更高层次的结构**。它们具有相似的高层次机制，但它们实际上试图做**相反的事情**。我想知道您对此有何看法。

<details>
<summary>Original English</summary>

**Dwarkesh**: I thought that was an extremely interesting point. At a high level, in some sense they're trying to do the inverse thing. Cryptographic protocols are trying to take information which has structure and make it look indistinguishable from randomness. Neural networks are trying to take things which look random—protein sequences, DNA, garbled text—and extract higher-level structure from it. They have similar high-level mechanisms, but they're actually trying to do the opposite things. I wonder what you make of that.

</details>

**Reiner Pope**: 我也尝试寻找**混合和打乱**出现在其他地方的例子。几乎有一个物理例子，你正在做一个蛋糕，你想搅拌面糊。字面上来说，先这样搅拌，然后那样搅拌，这不是一个太糟糕的方法。除此之外，回到数字世界，有一些差异，你指出的那个是一个相当大的差异。

<details>
<summary>Original English</summary>

**Reiner Pope**: I try to look for other examples where mixing and scrambling shows up as well. There's almost a physical example where you're making a cake and you want to stir the batter. Literally the idea to first stir it this way and then stir it this way is not too bad of an approach. Beyond that, back to the digital world, there are some differences, and the one you call out is a pretty strong difference.

</details>

**Reiner Pope**: 它的表现方式是，如果你只是**随机初始化一个神经网络**，也许它也是一个合理的**密码**，因为**随机初始化**会以复杂的方式**混淆事物**。它甚至可能做你想做的事情。谁知道呢？使其可解释的是**梯度下降**。你可以**微分一个神经网络**并获得有意义的**导数**。我们做了大量工作来避免过度复杂化**导数**，所以**残差连接**使其保持在可控范围内并简单。我们所做的 **LayerNorm** 也是如此。

<details>
<summary>Original English</summary>

**Reiner Pope**: The way it shows up, if you just randomly initialize a neural network, maybe it's a reasonable cipher as well because the random initialization is going to jumble stuff in a complicated way. It may even do what you want. Who knows? The thing that makes it interpretable is the gradient descent. You can differentiate a neural network and get a meaningful derivative. We do a lot of work to not overcomplicate the derivative, so the residual connection keeps it contained and simple. And so does the LayerNorm stuff that we do.

</details>

**Reiner Pope**: 针对**密码**的最大攻击之一也是**微分密码**。**密码**在不同的数域中运行。它们在**两个元素的域**中运行，所以只是**二进制**，而**神经网络**理论上在**实数域**中运行。你必须对**二进制数**进行**微分**，但你绝对可以**微分一个密码**。这被称为**差分密码分析**。基本上，它说的是如果你对**输入**进行微小差异，很难使**输出的差异**很小。一个设计良好的**密码**的全部工作就是使**输出的差异非常大**。

<details>
<summary>Original English</summary>

**Reiner Pope**: One of the biggest attacks against cryptographic ciphers is also to differentiate the cipher. Ciphers run in a different number field. They run in the field of two elements, so just binary, whereas neural nets run, in theory, in the field of real numbers. You have to differentiate with respect to binary numbers, but you can absolutely differentiate a cipher. This is called differential cryptanalysis. Basically, what it says is that if you take a small difference of the input, it's quite difficult to make the difference of the output be small. The whole job of a well-designed cipher is to make the difference in output very large.

</details>

**Reiner Pope**: 区别在于，那时的**优化目标**是**复杂化**。它们没有相同的**残差连接**，比如 **LayerNorms**。我猜两者融合的地方是**后门**。在 **LLM** 中使用**后门**，你试图隐藏……你会认为它是一个输入吗？它不是**前向传递**的输入，而是**后向传递**的输入。你试图隐藏**后向传递**的输入。

<details>
<summary>Original English</summary>

**Reiner Pope**: The distinction is that the optimization goals at that point are about complexifying. They don't have the same residual connections, like LayerNorms. I guess a place where the two merge is backdoors. With a backdoor in an LLM, you're trying to hide… Would you consider it an input? It’s not an input into the forward pass but it’s an input into the backward pass. You’re trying to hide an input into the backward pass.

</details>

**Dwarkesh**: 这是一个**对抗性上下文**吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: This is an adversarial context?

</details>

**Reiner Pope**: 这实际上是一个你得到**密码**所具有的**雪崩效应**的地方。针对**图像分类模型**的**对抗性攻击**是关于寻找图像的非常小的**扰动**，这些扰动会完全改变**分类**，完全改变**输出**。

<details>
<summary>Original English</summary>

**Reiner Pope**: This is actually a place where you get exactly the avalanche property that ciphers have as well. Adversarial attacks on image classification models are about finding a very small perturbation of the image that totally changes the classification, totally changes the output.

</details>

**Reiner Pope**: 这在**密码**中是常见的情况，而在**神经网络**中则是**不希望出现的情况**。

<details>
<summary>Original English</summary>

**Reiner Pope**: That is the common case in ciphers, whereas that's the undesired case in neural nets.

</details>

**Dwarkesh**: 有意思。使用**神经网络**作为**密码**是否是一个成功的领域？

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. Has it at all been a successful field to actually use neural networks as ciphers?

</details>

**Reiner Pope**: 你在尝试创建**密码**时所做的几乎任何事情，如果它没有经过**十年的审查**，它可能就会**被破解**。所以在这个方向上，它有点危险。在另一个方向上，至少有一种技术被**非常明确地采纳**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Almost anything you do in trying to create a cipher, if it doesn't have 10 years of scrutiny, it's probably broken. So in that direction, it's a little dangerous. In the other direction, there has been at least one very clear adoption of technology.

</details>

**Reiner Pope**: 有一种构造，你取一个**不可逆的函数 f[x]**，并用它来构建一个**可逆的函数**。这始于**密码学**。它被称为**费斯泰尔密码**或**费斯泰尔网络**。你应用函数 **f**——我想在黑板上写，但我不写——记住**输入**，然后**交换两者**。这允许你**构建可逆层**。有一篇 **2018 年或 2019 年**的论文叫做 **Reversible Nets**，**RevNets**，它正是这样构造的。除了你的**残差连接**，你还**记住来自前一层的输入**。这实际上使得**整个层可逆**，并且几乎**完全消除了你训练期间的内存占用**。

<details>
<summary>Original English</summary>

**Reiner Pope**: There is a construction where you take a function, an f[x] function, which is not invertible, and use that to build an invertible function. That started in ciphers. It's called a Feistel cipher or Feistel network. You apply the function f—I want to write on the blackboard but I won’t—remember the input, and then you swap the two. That allows you to construct invertible layers. There is a paper from 2018 or 2019 called Reversible Nets, RevNets, which does exactly this construction. In addition to your residual connection, you also remember the input from the previous layer. That actually makes the entire layer reversible and almost completely eliminates your memory footprint during training.

</details>

**Reiner Pope**: 无需为**反向传播**保存**激活**，你可以**反向运行整个网络**并**重新物化激活**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Instead of needing to save activations for the backwards pass, you can run the entire network backwards and rematerialize the activations.

</details>

**Dwarkesh**: 好的，所以我问你，**神经网络**真的被用于**密码学**了吗？我们意识到这可能最好在黑板上做。

<details>
<summary>Original English</summary>

**Dwarkesh**: Ok, so I was asking you, have neural networks actually been used for cryptography? And we realized it may be better to just do this on the blackboard.

</details>

**Reiner Pope**: 它们真的被用于**密码学**了吗？使用**神经网络**进行**密码学**……一般来说，**创建一个新密码**是一个非常危险的提议。几乎所有密码都会**被破解**。**99%** 的密码都会**被破解**，所以这可能是一个糟糕的起点。但另一个方向，至少在一个非常明确的案例中，**非常有成效**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Are they actually being used for cryptography? Using neural nets for cryptography… In general, creating a new cipher is a very dangerous proposition. Almost all of them are broken. 99% of them are broken, so it’s probably a bad place to start. But the other direction has been, in at least one very clear case, quite productive.

</details>

**Reiner Pope**: 有一种构造存在于**密码学**中，然后被引入**神经网络**，称为**费斯泰尔密码**或**费斯泰尔网络**。这个想法是，你可能有一个**不可逆的函数 f**，但你喜欢这个函数，因为它做了一些有趣的事情，比如它做了一个 **MLP**。或者它以有趣的方式进行混合。你希望用它来构建一个**可逆的函数**。我们将要进行的构造将是一个**双输入函数**，而不是一个**单输入函数**。

<details>
<summary>Original English</summary>

**Reiner Pope**: There's a construction that exists in ciphers and then was imported into neural nets called a Feistel cipher, or Feistel network. The idea is that you may have some function f which is not invertible, but you like the function because it does interesting things, like it does an MLP, for example. Or it mixes it in an interesting way. You'd like to build something out of this that is invertible. The construction we're going to make is going to be a two-input function rather than a one-input function.

</details>

**Reiner Pope**: 我们将应用 **f[x]**。我们需要实际记住 **x** 是什么，所以我们将 **x** 放在这里，以便我们可以反向工作，然后我们也不能丢弃 **y**。我们将记住 **y**，然后我们将它们加在一起形成这个**元组**。反转它的方法是，如果你认为我有这个**输出**并且我想恢复 **x** 和 **y**，我可以轻松恢复 **x**。就在那里，我直接读出来。要恢复 **y**，如果这个东西叫做 **z**，我可以通过 **z 减去 f[x]** 来恢复 **y**，因为我已经恢复了 **x**。这意味着这个**构造是可逆的**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We're going to apply f[x]. We need to actually remember what x was, so we're going to stick x over here so that we can work backwards, and then we also can't drop y. We're going to remember y, and we're going to add them together to form this tuple. The way to invert this, if you think I have this output and I want to recover x and y, I can easily recover x. That's right there, I just read it off. To recover y, if this thing was called z, I can recover y by z minus f[x], because I've already recovered x. That means this construction is invertible.

</details>

**Reiner Pope**: 这在**密码学**中被大量使用，现在仍然在使用。它是构建**密码**的主要机制之一。通常你希望**密码是可逆的**，尤其是**密码的层**，因为这具有更好的**加密特性**。

<details>
<summary>Original English</summary>

**Reiner Pope**: This was used in ciphers a ton and still is used. It's one of the main mechanisms of constructing ciphers. Often you want ciphers to be invertible, especially the layers of ciphers, because that has better cryptographic properties.

</details>

**Reiner Pope**: 这实际上已被**移植**到**神经网络**中。有一篇 **2017 年**的论文叫做 **RevNets**，即**可逆网络**。它使得**整个网络可逆**。你可以将其应用于任何网络，比如**Transformer 网络**。我进行**前向传递**，但随后我也可以**反向运行整个传递**。**整个神经网络**都通过这种构造**可逆**。这篇论文将其应用于某个层，比如**Transformer 层**。

<details>
<summary>Original English</summary>

**Reiner Pope**: This has actually been ported over into neural nets. There's a 2017 paper called RevNets, reversible networks. What it does is make the entire network invertible. You can apply it to any network, like a transformer network. I do a forwards pass, but then I can run the entire pass backwards as well. The whole neural network is invertible with exactly this construction. This paper applied it to some layer, like a transformer layer, for example.

</details>

**Reiner Pope**: 我们有这个函数 **f**，它是我们的**Transformer 层**。通常我们只有一个**输入**，然后有一个**残差连接**出来，并在这里添加。现在，这种变体将是我们有两个输入 **x** 和 **y**。**x** 经过函数，添加到 **y**，然后这成为新的 **x**，输出 **x**。然后这个 **x** 成为输出 **y**。这真正做的是，如果你考虑两层之前，是你之前提到的东西。它正在做**来自两层之前的残差连接**。这个 **y** 来自前一层，是那里的**残差连接**。由于这种构造，**整个东西是可逆的**。

<details>
<summary>Original English</summary>

**Reiner Pope**: We've got this function f, which is our transformer layer. Normally we would have just an input and then a residual connection coming out, and it gets added over here. Now, the variation of this is going to be we've got two inputs, x and y. x goes through the function, gets added to y, and then this becomes the new x, output x. Then this x becomes the output y. Really what this is doing, if you think of two layers back, is the thing you mentioned before. It's doing the residual connection from two layers back. This y came from the previous layer and was the residual connection there. Because of this construction, the whole thing is invertible.

</details>

**Dwarkesh**: 我为什么要关心？**可逆**有什么关系？

<details>
<summary>Original English</summary>

**Dwarkesh**: Why do I care? What does invertible matter for?

</details>

**Reiner Pope**: 它可能有趣的最大一点是**训练**。如果我考虑**训练的前向传递**……假设我有**四个层**，我以零、一、二、三的顺序运行它们。我必须将所有**激活**写入 **HBM**。我在这里的 **HBM 占用**与层数**呈线性关系**。这实际上可能是**训练期间最大的内存占用**。这是正常训练，然后我运行**反向传递**并反向读取。

<details>
<summary>Original English</summary>

**Reiner Pope**: The big thing that it can be interesting for is training. If I think of a forward pass of training… Let's say I have four layers and I run them in zero, one, two, three order. I have to write all of the activations to HBM. I get an HBM footprint here that is kind of linear in the number of layers. This can actually be the largest memory footprint during training. This is normal training, and then I run the backwards pass and read it in reverse.

</details>

**Reiner Pope**: **前向传递**向前运行，**后向传递**向后运行。我必须把它们读回来。这个 **RevNets** 论文的想法是，因为它是**可逆的**，我根本不需要存储这个。我可以完全**重新物化**它。我运行我的**前向传递**，然后当我运行我的**反向传递**时，我同时**同步地撤销**我所做的所有**前向传递步骤**，以便拥有我在这里需要的**激活**。这最终是**内存节省**，这是一个不错的主意。

<details>
<summary>Original English</summary>

**Reiner Pope**: The forward pass goes forward, and the backward pass goes backwards. I have to read them back out. The idea of this RevNets paper is that because it's invertible, I don't need to store this at all. I can completely rematerialize it. I run my forwards pass, and then when I'm running my backwards pass, I'm simultaneously in lockstep undoing all of the forwards pass steps that I did in order to have the activations that I need here. This ends up being memory saving, which is a nice idea.

</details>

**Dwarkesh**: 有意思。从某种意义上说，你**花费更多的计算来节省内存**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. In some sense you're spending more compute to save memory.

</details>

**Reiner Pope**: 没错。

<details>
<summary>Original English</summary>

**Reiner Pope**: That's right.

</details>

**Dwarkesh**: 有意思。这与你对 **KV 缓存**所做的**相反**。

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. It's the opposite of what you're doing with the KV cache.

</details>

**Reiner Pope**: 对于 **KV 缓存**，你**花费更多的内存来节省计算**。

<details>
<summary>Original English</summary>

**Reiner Pope**: With the KV cache, you're spending more memory to save compute.

</details>

**Dwarkesh**: 是的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Yeah.

</details>

**Reiner Pope**: 鉴于硬件的现状，**花费更多的内存来节省计算**通常是**有利可图的**。

<details>
<summary>Original English</summary>

**Reiner Pope**: Spending more memory to save compute is generally profitable given where hardwares are.

</details>

**Dwarkesh**: 有意思。这太有趣了。**Reiner**，非常感谢您能来。我觉得这真正证明了工作室和黑板背后的愿景。

<details>
<summary>Original English</summary>

**Dwarkesh**: Interesting. That was super fun. Reiner, thank you so much for doing it. I feel like it really vindicated the vision behind the studio and the blackboard.

</details>

**Reiner Pope**: 是的。太酷了，非常感谢您能来。

<details>
<summary>Original English</summary>

**Reiner Pope**: Yeah. Cool, thanks so much for doing it.

</details>

**Dwarkesh**: 谢谢。

<details>
<summary>Original English</summary>

**Dwarkesh**: Thanks.

</details>