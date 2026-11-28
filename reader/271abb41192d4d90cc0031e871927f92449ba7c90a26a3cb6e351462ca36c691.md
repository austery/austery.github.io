---
author: AI Engineer
date: '2026-06-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TUnPNY4E2fw
speaker: AI Engineer
tags:
  - long-context-training
  - context-parallelism
  - memory-optimization
  - transformer-architecture
  - distributed-systems
title: 突破500万上下文限制：长文本大模型训练的内存优化架构全解析
summary: 深入剖析长上下文大模型训练的内存扩展瓶颈，从基础的分片并行、上下文并行到前沿的激活卸载，并详细论述支持500万Token极限训练的U-Pipe内存复用架构技术体系。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Together AI
products_models:
  - Llama
  - DeepSpeed Ulysses
  - Flash Attention
  - PyTorch
media_books: []
status: evergreen
---
### 长上下文模型训练的驱动力与瓶颈

本次关于模型训练与微调的架构研究，由**Together AI**（Together AI: 提供大语言模型从算力集群、强化学习微调到无服务器推理的全生命周期基础设施云服务平台）的主导团队发起。当前全球AI社区对训练**长上下文模型**（Long Context Models: 具备处理并记忆极长输入序列能力的神经网络模型）表现出极其狂热的探索兴趣。这主要由两股核心应用浪潮驱动：首先是**智能体**（Agents: 能够自主推理并利用工具完成任务的AI系统）的爆炸式普及，开发者希望在上下文中加载尽可能多的外部语境，以引导模型进行更深度的推理；其次是**视频生成**技术的演进，维持生成系统的**时间一致性**（Temporal Consistency）需要在上下文中高频追踪多秒乃至数分钟的历史帧，这会以极快的速度消耗极其庞大的Token容量。

然而，在基于**Transformer**（Transformer: 基于自注意力机制的深度学习基础架构）的基础模型上暴力扩展上下文长度时，底层计算资源会遭遇两个维度的严峻瓶颈。首当其冲的是**二次方计算复杂度**（Quadratic Computation），因为长序列中成百上千万的元素都需要进行两两配对交互。第二个则是更加隐蔽且致命的**线性内存增长**，随着输入序列的不断扩大，系统内存分配将随之攀升。如果不采取一系列深度的系统级干预技术，庞大的内存占用将阻断所有的训练尝试。准确掌握并压榨这些计算节点中内存的具体去向，是将节省下的显存重新投入训练管线并加速整体性能的制胜关键。

<details>
<summary>Original English</summary>

Everyone, my name is Max. I am VP of research and development at Together AI. And today, I'm going to tell you about our research project, which is called Road to 5 million sequence length, breaking memory barriers in context parallelism. So, to begin, uh I'll first say a few words about Together AI and who we are. Together AI is an AI native cloud, which provides services and infrastructure for AI developers and builders at all stages of development, starting from uh creating a model, where you just might need a GPU cluster with heavily optimized computes and uh highly reliable uh systems, uh all the way through model shaping, where you can take existing models and customize them for your tasks in terms of performance, in terms of speed, in terms of quality, through services such as the fine-tuning or uh reinforcement learning. Also, we are an inference provider, so if you have an app which is reliant on open-source model inference, uh you can uh work with us and we'll provide you with the fastest way to launch and use AI models with more than 200 models in our portfolio, uh options for deployment, which include serverless and dedicated inference, and a ton of advanced optimizations, which I will not be able to speak about today. Um the purpose of this talk is uh focused on model training, customization, and fine-tuning in particular. And uh I'll start by asking a question. Uh I think in the last few months or like at least a year or so, we're seeing a lot of interest in the community, uh both on the system side and on the research side, in training long context models. Um the primary reasons for that are twofold, I would say. First of all, with the uh like explosion in popularity of agents, you can see a lot of different applications where you might want to put as many tokens as you want in your context, and you want the model to leverage that context effectively. Um second, with the development of applications such as video generation, you might often need to keep track of multiple uh like uh different frames, which or like even uh multiple frames per second, which can um occupy quite a few tokens in your context pretty quickly. And you also need models that have good uh sense of uh temporal consistency, which means that they are able to see what was happening a few seconds or ideally a few minutes ago. Um to do that all effectively, you need to make sure that the models are able to process that context and work with it correctly at the training time. Um but even if you're not at the scales of like millions of uh tokens in the context length, it's still quite important to understand where the memory goes, because who knows, maybe you might be able to reinvest it in some other ways and speed up your training overall. So, the problem here is that if you are taking a standard transformer-based language model and trying to extend its context, you can run into two bottlenecks. Bottleneck number one is that you are faced with quadratic computation, because uh long story short, for transformer-based models, uh you have pairwise interactions across all the elements in a sequence. The second problem is more insidious, one might say. Uh as you continue scaling your context, your memory keeps growing linearly, which is not as bad, but still pretty difficult to deal with, unless you apply a range of specific techniques.

</details>

### 突破内存限制：基础优化策略的深度叠加

为直观呈现突破内存极限的系统工程，我们设定了一个严苛的硬件测试基准：试图在由8块**H100**组成的单GPU节点上，将标准的**Llama 3B**架构模型训练上下文强行撑大至300万Token。在这一暴力扩展下，仅仅是加载庞大的模型基础参数，系统内存就会瞬间全线溢出。

针对这种物理极限，技术栈必须引入一系列复合的降维打击手段。防线的第一步是实施**完全分片数据并行**（Fully Sharded Data Parallelism: 深度切割神经网络参数并分散部署至多个加速卡的分布式训练策略），将参数碎片化分布到8块显卡之中。尽管这种做法大幅削减了模型静态权重的显存负荷，但由反向传播引发的海量**注意力激活值**（Attention Activations）很快会导致第二次内存崩盘。

在此基础上，系统被强制植入了**上下文并行**（Context Parallelism），最为典型的技术代表是由微软引入的**DeepSpeed Ulysses**架构。它通过更为高明的调度通讯算法，不再让每一个GPU独立硬扛全序列的多头注意力计算；取而代之的是，单个GPU在特定时间点仅承担一个注意力头（Attention Head）的运算负担，但其计算感受野却横跨整条300万Token的序列。这种精密的通信切分不仅完美兼容了**Flash Attention**（Flash Attention: 高效压榨底层硬件I/O速度的精准注意力计算实现）的底层加速，还能使内存使用率暴降近8倍。紧随其后，团队再次叠加了**激活检查点**（Activation Checkpointing: 不保存中间态，而在反向传播需要时精准实时重算的显存解脱技术），通过在反向传递（Backward Pass）中动态复现计算轨迹，第三次将激活内存的理论占用量往下压缩了8倍，为挑战更长序列打牢了地基。

<details>
<summary>Original English</summary>

Um and this is an example from Hugging Face's blog post on model training, which shows that the sequence length growth can affect your memory limits pretty considerably. Um yeah, here's the slide. And our goal of that project was to see how far exactly we are able to get with a range of existing techniques that are pretty well known to some in the community, as well as some further optimizations that we wanted to leverage to push this a bit further ahead. So, um let's say you're taking a model which is a standard Llama 3B architecture, you're trying to fit 3 million train tokens into your context, and you're taking uh all of this on an 8 uh x H100 GPU node. Um the first stage you'll see is that even with uh just model parameters, you're not able to fit uh it into the GPU. Uh you run out of memory just by trying to place the model. Of course, the next stage is to apply fully sharded data parallelism, where all the parameters are like basically chunked across the eight GPUs that you have, which is great, but uh still doesn't solve the problem. You see that uh the memory usage for the model drops quite significantly, but you still are running out of memory because of all the attention activations. The next point that uh we've leveraged, and I encourage you to use as well, is uh taking advantage of uh context parallelism. In particular, there is a pretty well-known technique called DeepSpeed Ulysses, first uh introduced by Microsoft. The idea is that instead of computing all of your multi-head attention like on every GPU separately for the whole sequence, you can do something more clever. In particular, you can try to compute the attention for different heads at different points in time, uh or like on different GPUs, uh through communicating these activations as uh they are required, in such a way that one GPU is only responsible for one attention head here, but it's still computing the attention over the whole sequence. Um that technique is quite effective at uh addressing the problem, and it also allows you to utilize the best possible attention implementation, like Flash Attention 1 2 3 4, um to optimize that part of the computation. And then you aggregate the results as uh you would have uh previously. So, if you apply Ulysses context parallelism, the utilization drops quite significantly, like approximately 8x uh here, as uh it should, but we are still quite far from our goal of being able to fit that onto just a single uh H100 node. So, what happens next is that we can try to recompute the activations as they uh are needed to us at the backward pass. That technique is known as activation checkpointing, and uh it's available in pretty much all of the deep learning frameworks these days that you could use. You just need to enable it in a correct way that does not uh impose too much of a computational burden on you. Um with that, with activation checkpointing, you can drop the activation usage by like a further factor of eight, but still something else needs to be done.

</details>

### 激活卸载与精细化的序列切块运算

当常规并行的优化潜力被彻底榨干，对异构硬件内存的深度掠夺便提上了日程。第四道核心工序是**激活卸载**（Activation Offloading: 将低频访问的激活数据从GPU高速显存下放至廉价CPU内存的错峰调度机制）。系统不再将Transformer块的所有输入矩阵全部锁定在显卡中，而是在其闲置期无缝转移给CPU，直到反向传播计算推进至对应网络层时，再实施精准预取（Prefetch）。这项由开源框架**Unsloth**率先实施的激进策略，由于绕过了核心计算节点的性能敏感区，能在几乎不损失整体算力指标的前提下，强行撕扯出高达37GB的超大显存真空。

然而，解决了静态存储后，计算过程中的瞬时高压水流依然存在。在长序列网络中执行损失函数计算或**多层感知机**（MLPs）等大量**逐元素**（Element-wise）的数学运算时，如果按照传统方式执行，会瞬间在内存中开辟出一个维度长达300万的史诗级张量缓冲池。为了彻底截断这种灾难性的内存波峰，工程团队引入了极细粒度的**切块与平铺运算**（Tiling and Chunking: 将长序列维度的连续矩阵运算拆卸成多个互不干涉的碎片运算序列）。通过对Arctic序列维度的切割阵列化处理，这些不可阻挡的瞬时计算峰值被彻底抹平，使得300万Token的极限上下文挑战在物理层面终于具备了可操作性。

<details>
<summary>Original English</summary>

Uh the next optimization is um also connected to the storage of activations. You can try to uh store some of the inputs to each transformer block, not on the GPU, but instead offload them to CPU when they are not required. Uh this is not very impactful for the performance, because you can offload uh it and prefetch when you are trying to backpropagate to that to the corresponding layer. Um this optimization, to the best of our knowledge, was first implemented uh by Unsloth, and uh it allows you to drastically expand the context window. Um the next point is that you're getting uh with offloading next to 37 uh gigabytes of data, but then comes the other part of offload memory usage. Uh what happens next is that you can essentially tile all all of the computations across the sequence length in case they are element-wise. So, all the loss computations, all the MLPs, they can be chunked to avoid creating these huge buffers that would be 3 million along one of the dimensions. Um that's Arctic sequence length training, and even with these optimizations, you are finally getting to a point where 3 million is possible.

</details>

### U-Pipe：基于时间序列的缓冲复用

但若想进一步刺穿500万序列长度的技术天花板，常规的防线拼凑已无济于事，必须对上下文并行的内核发起底层架构革命，这就是我们主导研发的核心变体算法——**U-Pipe（Untitled Ulysses）**。

在传统并行理念中，研究人员发现，哪怕仅仅抽取并计算一组注意力头的数据，也足以在单次迭代的时间窗口内彻底打满显卡的算力负载。U-Pipe巧妙地捕捉到了这一算力饱和的特征，设计出了一套**跨时间步的内存复用循环**（Buffer Reuse）。当单个GPU被调度执行一批不同的注意力头时，系统会将其强制切分为时间轴上的连续运算块（Chunks）。执行引擎首先计算第一组头的数据，生成并存储局部张量结果；随后，革命性的一幕出现——**引擎进入下一计算阶段时，并不会开辟新的显存空间，而是直接覆盖并完全复用上一阶段早已分配好的底层显存缓冲区**。

相较于传统架构那如同无底洞般的内存全量分配，U-Pipe仅仅申请了一块极小的驻留显存池，却在时间维度的多次迭代中循环利用。这种近乎苛刻的内存压榨不仅在极限长文本训练中避免了**查询、键、值**（QKV Matrices）产生恐怖的、在其中一个维度长达500万的全矩阵交叉积，而且在短上下文的测试场景下也展现出了反直觉的高吞吐量。最终结果显示，U-Pipe在8B和32B模型参数规模下，不仅完全追平了当前业内最极致的内存优化实现方案，更为开发者构建出了一个极具弹性的性能杠杆：你可以放大计算块的尺寸换取更快的整体训练速度，也可以堆叠前述所有的极限优化手段并加上U-Pipe引擎，榨干系统的每一滴显存，将这些冗余资源调配至管线更需要的关键阶段。这正如**PyTorch Profiler**等底层性能分析工具所揭示的真理：在大模型长文本的深水区里，致命的瓶颈往往潜伏在系统最不易察觉的盲点深处。

<details>
<summary>Original English</summary>

But, what if you wanted to go further? And here we actually need to do something else, which is the primary optimization we've done in our work dubbed the Untitled Ulysses. And you could describe it as a further deeper analysis and expansion of this context parallelism technique. So, what we found was that even trying to compute one set of heads at a time is already enough to saturate the computational capacity of the GPU with within one iteration. Which means that if you have multiple different heads scheduled to be executed on one GPU, you can divide it in chunks and then essentially iterate through these chunks over time. So, we have one group of heads which are being recomputed, then you compute attention over them, you store the partial result, then you follow up with the next stage, which can reuse all the buffers you've allocated at the previous stage. Um so, the advantage here is that instead of allocating this huge buffer as you would have before like here in this slide, you allocate a buffer which is smaller, but you reuse it across like two or more different iterations. And that allows it to further save on the activation memory for your training without any significant impact to the throughput at small scales. So, here you can see the results that we've measured across different context parallelism techniques. As you can see, both at the 8 billion scale and at the 32 billion scale, we are matching quite closely the most memory optimized implementations of transformer training while being able to scale even further like 5 million tokens and sometimes even being more performant at small at shorter context lengths. Um the relation between the chunk size or the number of heads you compute at the same time and the throughput is quite straightforward. So, if your chunk is larger, your memory utilization is higher, but at the same time you can run the whole model a bit faster. Um so, by stacking all of these techniques together and applying U-Pipe on top, you can, for example, free up a bit of additional memory in your training if you need it and reinvest it somewhere else, for example, among the stages. Or you could say that we're interested in training across not 3 by 5 million context lengths and then you pipe is the technique that will save you by contrast to everything else. So, as a takeaway, I think one of the things that could be quite insightful here is that training models with large context lengths is a very interesting and challenging goal, but the bottlenecks might appear where you least expect. So, tooling like the PyTorch profiler, which we elaborate on on in our paper, or other or other techniques can help you a lot. And also check out our paper for more results. All of that is public at the moment and we have an upcoming thread which will illustrate the method in more depth. Thank you very much for listening and now we are ready for questions. Thank you. Do you guys have any questions cuz we're together and I am employees. So, who did you join it from the middle so we lack some certain context? I'm just curious about the so the QKV that was quantization parameters is that correctly Uh not exactly. It was just the query, key, and value matrices of the transformer layer. So, you multiply them here in the attention part, which creates most of the complexity because all of the queries have to like result in all of these pairwise active interactions with like keys. Uh and the problem is that if you have a a sequence which is like 3 million in length, it means that technically like in the standard most vanilla way, you would have just like allocated that whole big tensor which has 3 million in which is 3 million in size along one of the axis. And like that's pretty significant as you could imagine, which means that you have to resort to like not just one technique, which is U-Pipe, but a range of other approaches to somehow help you like uh leverage like execute these computations without running out of your memory. So, yeah, that's the key idea and the key challenge of working with transformers at the scale. Cool. Um in that case, thank you very much for questions and for listening.

</details>