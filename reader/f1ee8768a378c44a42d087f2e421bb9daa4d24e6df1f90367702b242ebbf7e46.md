---
author: AI Engineer
date: '2026-10-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=htod7Nv1cBc
speaker: AI Engineer
tags:
  - sparse-attention
  - multimodal-learning
  - vision-transformer
  - long-context
  - transformer-architecture
title: MiniMax M3 架构解密：稀疏注意力机制与原生多模态端到端训练
summary: MiniMax 强化学习研究员 Olive 深入剖析了开源前沿模型 MiniMax M3 的技术实现。重点详解了软硬件协同设计的稀疏注意力机制 MSA 如何在 GQA 下实现 100 万超长上下文的高效扩展，并分享了从零开始原生预训练多模态模型以避免文本能力受损的探索历程与 3D ViT 设计实践。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - MiniMax
products_models:
  - MiniMax M3
media_books: []
status: evergreen
---
### 三位一体前沿基座：MiniMax M3 与开源架构全景

MiniMax 作为全球少数全面深耕多模态全技术栈的 AI 实验室之一，此前已在**大语言模型**（Large Language Model）、语音模型、视频生成模型以及代码智能体（Coding Agent）领域建立起完整矩阵。最新发布的开源模型 **MiniMax M3**（MiniMax M3: 开源前沿多模态大语言模型）首次在开源权重模型中实现了三大核心前沿能力的有机融合：
* **顶尖代码与智能体能力**：能够胜任高复杂度的智能体调度任务，涵盖自动化长文本创作，并可直接作为编程智能体无缝承接 90% 的日常研发编码工作。
* **百万级超长上下文**（1M Context Window）：具备处理完整代码库与长程交互的能力。通过自主研发的 **MSA**（MiniMax Sparse Attention: 稀疏注意力机制），在保持百万上下文容量的同时，Prefill 吞吐速度提升 9 倍，Decode 推理速度提升 15 倍。
* **从零原生的多模态融合**（Native Multimodal from Step Zero）：彻底打破传统的后期嫁接模式，在预训练伊始便同步融合视觉感知与语言生成，为计算机使用智能体（Computer-Use Agent）等跨模态交互提供了坚实底层支撑。

<details>
<summary>Original English Source</summary>

um all right, um so hi everyone. i'm my name is olive. i work at minimax on a reinforcement learning research. and today, i'm gona talk k little bit it about our new model minimax m three and how we trarended nativemulti model from step zero and how we trarended with MSA, which is called ininimax spar attension. um a little bit introduction of our team and how one of the few labs over the world that uh works on multime modealities, which means that we have published our um of course, LM dedels. before we worwork on our speech models, we have our own video generation models, and we have our coding agenca models. and lately we just release our minimax m three, which is open weight with frontier performance. so it is actually the first open weight model to combine the following three uh, from chair capabilities. the first one is what we call. so the uh coding and ergentic capabilities, the model is able to do a lot of the agentic task that you imagine. um it can do automatic a text composition. it can work in your coding agents. it can drop in for ninety percent of the coding works that you are currently doing. and the second pillar is that the model has one million context window. um so which is very long that enabled like unlocks pretty much basic all basic user long user interactions um of like it handles four coo bases, and we trained ded with MSA minimum sparse attention. so it is nine times faster prefiil and fifteen times faster decode versus four tension. and the third one is that the the model was trained native mutor model from step zero, which means that from from scratch, we combined visionary standing with language generation. so the model would understand both capabiliis very well from the start and uh h. so that we can build many more applications on that, say, computer use agents, right?

</details>

### 双分支协同设计：解构轻量索引与稀疏注意力机制

在超长上下文架构的探索中，核心设计哲学在于**更简洁的架构必然带来更优越的 Scaling 规律**（Simpler architecture leads to better scaling properties）。为了摆脱传统全注意力机制的计算爆炸困境，MiniMax 构建的稀疏注意力由两个精简分支协同运作：
* **索引分支**（Index Branch）：负责执行轻量化的全注意力计算。该分支采用 4 个 Query Head 和 1 个 Key Head 的紧凑配置，并通过 KL 散度损失函数（KL Divergence Loss）进行训练，以精准拟合主分支的注意力分布概率。其核心职责是以微小的算力开销筛选出注意力权重最高的代表性 Token。
* **稀疏主分支**（Sparse Main Branch）：并不直接对全量上下文进行稠密计算，而是根据索引分支挑选出的高优先级 Token 块（Blocks），仅针对性调取对应键值对（Keys & Values）执行真正的深度注意力运算。

这种双分支解耦设计，使得主计算流在维持极高信息捕捉精度的同时，将算力与内存带宽需求大幅压缩。

<details>
<summary>Original English Source</summary>

so first, all briefly explain what sparse attention does. our court design principal is that a simpler architecture can always lead to better scaling properties. this is a principle we have followed throughout the entire design. so our goal is to always pursue a cleaner and simpler architecture. disparse attention consists of two branches. the first one is what we call the index branch, which performs a lightwid full attention computation. it uses four quarheads and one key head, and it is trained with a care loss to match the the attention scores of the main branch. the index branch is used to identify the tokens with the highest attention scores. these selected tokens are then attended by by the main branch. in other words, the sparse branch does not attend to all of the tokens, but only to a subset of them. this subset is selected through the lightwway computation of the index branch. then the sparse branch would use the blocks selected by the index branch to determine which keys and values are needed for attention complication. all right.

</details>

### 破除硬件瓶颈：算法与底层系统的软硬件协同重构

这项架构演进并非单纯停留在算法层面的推演，而是**算法与底层硬件基础设施的协同设计**（Algorithm and Infrastructure Co-design）。以业内知名的 **DSA**（DeepSeek Sparse Attention: 深度求索稀疏注意力）为例，该方案高度适配结合了 **MQA**（Multi-Query Attention: 多查询注意力）与大头维度（Large Head Dimension）的特定架构；然而，当迁移至主流工业界广泛使用的 **GQA**（Grouped-Query Attention: 分组查询注意力）时，直接沿用现有稀疏方案会遭遇算法与系统的双重掣肘：
1. **注意力多样性湮灭**：GQA 本身依靠多个 KV 组来提供异构特征的多样性。若所有 KV 头强行共享同一套 Token 筛选集合，就会迫使各头关注完全一致的目标，直接抵消了 GQA 带来的表征多样性优势。
2. **GPU 连续内存访存受阻**：在 MQA 设定下，KV 布局表现为单一连续大维度（例如 $1 \times 512$），GPU 能以连续读取实现极高的吞吐率。然而在 GQA 中，相同维度被拆解为多个离散 KV 头（例如 $4 \times 128$），导致 GPU 必须跨通道执行多次独立的非连续读取，显著推高了访存开销并劣化了算存比（Compute-to-Memory Access Ratio）。
3. **Top-K 串行排序依赖**：在全量候选 Token 空间上直接进行细粒度 Top-K 排序存在严苛的数据依赖性，极难在 GPU 硬件上实现高效高度并行化，进而产生不可忽视的计算与聚合开销。

针对上述系统瓶颈，MSA 实施了针对性的工程突破：在算法侧，**废除索引分支输出的跨头粗暴聚合**，允许不同 KV 头在稀疏注意线下索引并关注不同的 Token 集合，完整保全 GQA 的多视角表征能力；在硬件架构侧，**由 Token 级细粒度筛选全面转向 Block 块级检索**（Block-level Retrieval），大幅缩减候选集规模，消除昂贵的 Top-K 排序瓶颈，最大化契合 GPU 块连续访存模式。结合专为预训练与推理端量身打造的高性能 CUDA 算子（Custom Kernels），在保障性能无损的前提下平稳支撑起百万 Token 上下文的高效预训练。

<details>
<summary>Original English Source</summary>

and what i want to emphasize today that our design is not purely algorithm like algorithm driven and said, we took an algorithm algorithm and infrastructure code design approach. um a good good example to start with this dsa. d. sa was a very strong design, but it is also high to optimize for deep six oones architecture, especially the comonination of MQA and the large headdeam. however, what we move to a more commonly used GQA architecture directly applying the same design, becomes a lustury forward. it introduces several practical issues is especially from the infrastructure and implementation perspective. so this motivate our design choice, instead of simply borrowing and existence, spar se attion design, we rethink the architecture under the constraints of GQA and real al system efficiency. so what are the issues? um if we directly apply the existing sparse? attenararchitecture first from algorithm perspective, GKVA has multiple KV has which should ideproviprovide diverversity across different KV groups. however, if we directly reuse the same token selection strategy, multiple KV has will end up attending to exactly the same selected tokens. they essentially cancils out the diversity that jicuates is supposed to provide second from the infrastructure perspective. this design is not very friendly to GPU memory access GPU are much more efficient when reading continuous data in the MQA setting. we can syanthy KV eight layouts as one KV had with a large head dimension, for example, one by five hundred. and pulth, this is relatively continuuous and efficient to read. however, in g ua, the same total dimension may be sput acpross multiple KV hats, for example, is four by one twenty eight. these are no longer one single continuguous read. instead, the GPU needs to perform multiple independent readacross different KVVVS. this increases memory access overhead and reduces the computer memory access stratio. and another issue here is the top key computition to south to select the most important tokens. the indexture needs to compute. talk k. sorts over a large number of token webl candidates. however, talk k has inherent data dependencies, so it is difficult to fully be parallel on gpu. as a result, total level selection introduces nontribual competition emerging overhead. so how that we address these issues in m sa from the from the algorithm side, we remove the aggregation of the index branch outputs in the original design. the results from all index branch in index branch has emerged into a single set of selected tokens. but as we discuss earlier, this would remove the diversity brought by jecua. instead, we keep the selection different. the different across KV has under our sparse attention design when using GQA different KV has can attend to do different sets of tokens. this helps preserve the diversity of GQA rather than forcing all hets to share the same sports tension for the infrastructure side. we move from token level selection to block level retrival. compared with token level selection, brock block level retrieval significantly reduces the number of candidates and lower sea overhead of top key computation and result merging at the same time, block level retrival is more hardtware friendly. it improves memory access efficiency and increases the compute to memory accestrry shell. importantly, we also show that the design does not introduce a significant performance drap finally would design efficient kernels for both training and influence. i won't going to the kernel details here today, but this is the system level component that makes the sparse attention design, practical and efficient. so with this design, we were able to extend the training of our m free model to one million context very ficiently.

</details>

### 原生多模态范式：从 Step-0 消除模态割裂与语言能力衰退

在确立了高吞吐的长上下文基座后，团队面临的核心战略抉择在于如何引入多模态能力。独立的纯视觉语言（VL）模型应用场景受限，但直接在预训练中融合视觉与文本又极易引发严重的负向干扰。行业内最通用的两类过渡方案均存在根本缺陷：
* **CPT 后期持续预训练策略**（Continual Pre-training）：在主干文本模型预训练收敛（Decay 阶段）之后再加入多模态图文数据。此时模型的文本语义空间结构已高度固化，强行插入多模态分布会造成严重的灾难性遗忘与语言表征损伤。
* **衰减期前插入策略**：在模型预训练中途、文本参数定型前介入多模态数据。实验表明该路径对动态超参数（如 Learning Rate）极其敏感，虽然微调特定学习率可能短暂缓解回退，但结论完全无法跨训练轮次泛化，在大规模分布式预训练中无法保持工程稳定性。

这促使 MiniMax 坚定采用 **Step-0 原生端到端多模态预训练**（Native Multimodal Training from Scratch）。在相同文本 Token 预算下，模型自第一步起即同时摄入文本与图像，使得两类模态在网络早期生长中自然同构。注意力热力图（Attention Map）的对比揭示了两种范式的本质差异：在 CPT 模式下，文本 Token 几乎完全不关注视觉 Token，视觉区域在热力图上呈现大面积暗区，表现为严重的**模态解耦割裂**；而在 Step-0 原生训练下，视觉与文本 Token 呈现出高度交融的激活状态，形成了真正意义上的跨模态有机理解，同时完好保留了最顶尖的语言核心能力。

<details>
<summary>Original English Source</summary>

and as we talked about earlier, the third pillars is the native multimobality. our model minimax m three was trained from scratch with multimodel data. what does that mean? our model was string with both text and vision understand standing from steps zero is very different approach from current open weight models. our starting point is very clear as a current stage, a standalone VL model has relatively limited application scenaris. but combining it was with, you know, text understanding during the training can be challenging. so the key question and challenged there was, how can we introduce multimodel capability without hurting the cortex performance? to answer this, we actually explore several training strategies as scale. the first and most common approach is to add mottimodel training after the pretrain in decay stage, which is essentially ACPT stall approach. however, at that point, the model has already largely conversed, adding more time model data at this stage tends to interfere with a learch tax capability and causous degregation. another approach is to insure multimodel training before pretraining decaded ge, for example, after the model has already seen a number of amount of tex tokens. we also tried this direction but found that the results were highly sensitive to the dynamisure in training hypoper proramners, such as learning rate, for example, in one setting, a smaller learning rate might reduce the performance drop, but this conclusion does not necessarily generalize to another run. more importantly, during a large scale, pray training. these parameters can not be ararbitarily changed just for mulormodel training, and this leled us to our final strategy. native mulormodel training from scratch in this setting. multi model capability is introduced from the very beginning rather than being added after the text model has already formed its structure under the same text token budget. we find that the disaproproach almost does not heard tax capability. we actually did many fundd. analyyis is aring this experiments. one of them missed this interesting observation from the attention maps. you can see from this picture that for CPT style multime model models, the text tokens often pay very little attention to visual tokens. the visual token regions are mostly dark in the attention map. this suggest that the multi modelities are not fully integrated, while in contrast, with native multimodel training, the attention map looks much more integrated. we do not see here a clear separation between tax tokens and visual tokens. they suggest that the model learns to fuse visual and textual information more naturally from the beginning. so overall, our training strategy is not just about adding vision capability. it is about integrating multimodelity into model while preserving its strongest text capabilities.

</details>

### 时空表征升维：3D 视觉注意力在 ViT 中的工程权衡

在多模态的模型物理架构层面，MiniMax 采用了标准化且鲁棒的接入管线：图像或视频流输入至 **ViT**（Vision Transformer: 视觉 Transformer 编码器）提取视觉 Token，随后将视觉 Token 替换掉文本序列中的图像占位符（Image Placeholders），将视觉嵌入与文本嵌入联合输入给大语言模型进行联合建模。

在此基础上，一项关键的架构发现是**在 ViT 内部引入 3D 空间-时间注意力机制**（3D Attention inside ViT）。在传统的标准 ViT 设定中，注意力计算被严格限制在单张图像或单个离散视频帧内，各帧之间的 Patch 在 ViT 阶段相互孤立；而引入 3D 注意力后，不同帧之间的 Patch 能够跨越时间维度直接相互交互。这赋予了模型显著增强的跨帧时序与三维几何建模能力。不仅直接拉升了视频理解水准，相关增益更跨域迁移至静态图像基准评测中，证明其系统性强化了底层视觉表征的综合质量。在落地实践中，考虑到全量多帧展开会带来指数级的系统通信与负载均衡开销（Load Balancing Challenges），团队通过大量实验验证，将时序注意力窗口严格界定在 **4 帧跨度**，达成了算法感知上限与硬件工程吞吐的最佳平衡。

<details>
<summary>Original English Source</summary>

and of course, uh, we did many experiments on multimodeararchiteture ture choices. our all arartetetures relatively standard, the image or video is being processed by a viit, which produces visual tokens. these visual tokens are then inserted into the language model input by replacing the original image placeholders in the take sequence. after that, the visual embeddings and text ebeddings are fed together into the language model. one important finding is that applying three, the attention inside the vip is very helpful for vision understanding, and the standard viit setting attention is is applied within each individual image or frame for video inputs. this means that visual patches from different frames do not directly interacts ts at the IT stage, but with three d attention patches across different frames can attend to each other directly. this gives the model stronger temporal and cross from visual model and capability, and we found that this improves visual understanding and the benefit also transfers to some image benchmarks, suggesting that it's strength the overall visual representation, rather than only improving video specific text. and one practical detail is that we cannot simply extend three d attention to an unlimited number of frames because that would introduce additional system and low balancing chengenges in explplation using sing four frames, give us the best trade off between performance and efficiency. so overall, with our architecture design with our training strategies that would export uh throughout the stages. and with our analysis and VIT explorations, we were able to train the model from scratch uh, with more timodality understanding, and that will be the end of the presentation today. thank you. the.

</details>