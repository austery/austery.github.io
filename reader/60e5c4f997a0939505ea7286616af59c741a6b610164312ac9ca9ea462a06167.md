---
author: AI Engineer
date: '2026-08-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=maRzp4kImJ4
speaker: AI Engineer
tags:
  - reinforcement-learning
  - distributed-training
  - pgrpo
  - system-optimization
  - model-quantization
title: 跨数据中心强化学习：解耦训练与弹性 Rollout Fleet 的系统实践
summary: 来自 Modal 的 Nan Jiang 介绍了如何打破传统 RL 强化学习训练中 Trainer 和 Rollout 节点的强耦合限制。通过利用 Adam 优化器在低精度（BF16/FP8/FP4）表示下的“更新吸收”效应，将每步权重更新同步量从数百 GB 的全量 Checkpoint 压缩至数百 MB 的稀疏 Delta 补丁。这使得 Rollout 节点可以脱离昂贵的 RDMA 局域集群，以高弹性、全球分布式、多云供应商的方式在廉价闲置 GPU 上低延迟运行，极大提升了强化学习后训练（Post-Training）的算力利用率与规模瓶颈。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Nan Jiang
companies_orgs:
  - Modal
products_models:
  - Stitch
media_books: []
status: evergreen
---
### 强化学习后训练的算力供需失配：紧耦合集群 vs. 全球分布式算力

在当前大语言模型的**后训练**（Post-Training: 模型预训练完成后的对齐与强化学习阶段）讨论中，绝大多数研究都集中于算法设计（如 **GRPO**：Group Relative Policy Optimization，一种无价值网络的策略优化算法）或确定性算子内核的优化上。然而，一旦在真实物理世界中以工业级规模运行这些实验，问题就会迅速从算法理论演变为物理现实：GPU 到底部署在哪里？它们是否在同一个区域？是否有极速的网络互连（如 **RDMA**：Remote Direct Memory Access，允许节点间直接进行内存访问而无需 CPU 介入）？我们能否立即获取这些算力？

传统的强化学习（RL）后训练架构面临着极大的物理限制。标准的 RL 循环包含一个 **Trainer**（训练器）和一组 **Rollout Workers**（采样器/生成节点）。Trainer 负责更新策略（Policy）权重，而 Rollout 节点则利用当前版本的策略模型生成动作轨迹（Trajectories），并通过环境或奖励模型获取观测值与奖励，最后将数据传回 Trainer 进行下一步迭代。在默认设置下，Trainer 和 Rollout 节点紧密耦合在同一个高带宽集群中，彼此通过极速的 RDMA 网络进行权重同步和数据交换。

然而，这种紧耦合架构将 Rollout 节点的算力规模限制在 Trainer 集群的固定尺寸内。如果采样阶段需要更多的计算算力，我们根本无法在运行中动态扩展集群。这造成了严重的**算力失配**：可用的物理算力往往零散分布在不同云服务商、不同地区、不同价格区间，但默认的 RL 架构却强行要求一个单一、紧密互连的巨型集群，而这种兼具“足够 GPU、同一地区、极速互连、即时可用”的集群正是市场上最稀缺、最昂贵的黄金资源。

<details>
<summary>Original English</summary>

All right, cool. Hi everyone. Uh, hope you all have a good time at the conference. Uh, I'm N from Moto. Uh, at Moto, we spend a lot of time thinking about GPU capacity, like where it exists, how do we make it elastic, and what kind of workload can we actually use it. Today I want to talk about one place where everything became like gets really interesting the IO post training. A lot of IO discussion right now is about algorithm and the environments sandbox PO GRPO like to call maybe low precision training maybe deterministic kernels. Um but when you run those experiments at a scale the problem became more physical. Where are the GPUs? Are they in the same region? Uh do they have fast fabric? Uh can we get them right now? Maybe the default shape of IO comput is too restrictive. Maybe some of the work we usually force them one cluster uh like can actually run on scattered autoscaled capacity. So can we do our cross globe? So this is my talk about many about. So to make this more concrete let's start with the IO loop itself. So in the second uh our post training loop we can see there's a one trainer and the trainer updates the policy rollout worker or maybe people call it sampler use those policy to generate trajectories. The environment will be returning the reward and observations. Those trajectory will go back to trainer for the next updates. The important error here is the way sync in the default setup trainer and the rollout will be living in the same cluster and the the way sync will be super fast with RDMA. But that also couple the rollout fleet to the to the trainer cluster. If the rollout needs to more to have more capacity maybe no more nodes during runs um you are normally limited by the fixed size during your trainer maybe your trainer cluster. So the ne next question is what kind of compute shape did we actually force everything into? On the left side is the cathedral uh one region one faster interconnect uh many GPUs wild together. This is the right shape for the trainer. On the right it is bro. This is where a lot of like usable useful usable compute actually lives. Different providers different regions different price and different availability. There's still a lot of capacity out there, but it's not one perfect RDM in the island. This is the mismatch. Available computer is distributed, but the default IO loop ask one tightly coupled cluster. And that cluster is exactly the hot part hard to get. IO wants all four of these at the same time. Enough GPU, same region, fast fabric, and available now. Any of these like is manageable, but all four of them that are pretty hard to get at the same time. ADMIC capacity is not elastic in the way the inference capacity is elastic. You cannot assume you can grow the trainer cluster uh halfway through a run just because roll out wants more nodes for a trainer. So if the whole out loop has no live like has to live inside the the one cluster rollout inherits the hottest part capacity constraint in here. So that leads to the key question does the whole out loop actually need that like this kind of shape.

</details>

### 解耦训练与采样：将可移动的 Rollout 岛屿推向全球分布式算力

为了打破这种算力局限，我们需要审视 RL 后训练的两种截然不同的计算负载性质：
* **训练（Training）**：这是一个高度紧耦合的同步计算任务。在每一次参数更新步骤中，都需要进行全局的 `All-Reduce` 等集体通信以及模型并行化传输，这必须运行在拥有极速互连网络（如 RDMA）的单一高带宽集群上。
* **采样（Rollout/Serving）**：这本质上是一组服务/推理任务。它们独立运行当前策略模型的实例，为不同的 Prompts 生成生成轨迹并调用环境或工具获取奖励，再将数据传回。各个 Rollout 任务之间没有全局的 `All-Reduce` 通信需求，相互之间完全独立。

因此，**反向传播（Back-Propagation）** 应该被牢牢锁定在高性能本地集群中，而 **Rollout 节点舰队**（Rollout Fleet）则完全可以离开这个高昂的中心集群。更具体地说，我们将可独立移动的计算单元定义为 **Rollout 采样岛屿**（Rollout Serving Island）—— 这是一个在内部服务单一特定策略版本、可能有本地并行化限制（如张量并行 Tensor Parallelism）的局部推理服务组。

一旦明确了这种解耦定义，整体架构设计就会变得非常自然：Trainer 依然运行在专用的 RDMA 高带宽集群上，专注于梯度计算和参数更新；而 Rollout 岛屿则呈扇形散布在外部的分布式算力网络中。两者的核心通信接口极简：Trainer 仅需向外广播策略模型的权重版本，而各地自治的 Rollout 岛屿在本地生成轨迹数据与元数据后，异步将其发回 Trainer。

<details>
<summary>Original English</summary>

So let's dive into this training is one tightly coupled job. Every step has collectives all reduced and the model parallel communication that part actually wants one fast fabric a RDM connected rollout is a fleet of serving jobs. It generates trajectories call environments or maybe tools and they will be sending back data back to the trainer. So cross rollout jobs there's no global or reduce. So the thing I want to move here is not back propagation. Back propagation should stay in the cluster. The run the rollout fleet is the one that can leave. More precisely, the movable unit is the rollout serving island a coherent endpoint or maybe a local group of endpoint or that they can be serving one policy version inside island. A large model may still be having like local parallelism. They can do PD segregation. They can have like local serving constraints. So across islands the dependency is much lighter right now. policy version in and the trajectory and the metadata out. So once we define the unit that way the architecture is much much more natural. Once we define the movable unit the architecture is very straightforward. In this case we just have trainer standing audic cluster and that's where the back proper and the collective go the rollout side will be fing out across the SPR. Each rollout island will be can be single engine will be a local serving group depending on the model and the serving topology there. across island there is no global or reduce that's the most important thing there the global interface is very simple the trainer send policy weight version out and the rollout sending trajectory and the metadata back. At this point the architecture depends on one remaining link the weight update so if you want to if you want to send the full parameter like full checkpoint from disk or maybe through the network then everything is like minimless and like it will be breaking immediately so uh after this aggregation The things we will be discussing about like the size of like go the size of the full parameters go through the disk. Naively that means shipping all full checkpoints every time rollout needs a new way version. At this scale the checkpoint is very huge. So a Kim scale NVIP for checkpoint you have like 500 gigabytes normally take a minute or maybe normally take multiple minutes to hours to just do the way. So moving that over commodity link is might not be the smartest choice because like uh when you're doing async maybe even even fully async training you still want way updates latency to be as low as possible like within seconds. So the problem here is not whether rollout can leave the cluster the problem is like the full checkpoint is a wrong unit of synchronization.

</details>

### 更新吸收效应：利用低精度 rounding 边界实现极致稀疏的权重 Delta 补丁

在这个完全解耦的架构中，仅剩下一个致命的技术瓶颈：**权重更新的传输带宽与延迟**。如果每次策略更新，都需要将一个包含完整参数的巨型 Checkpoint（例如一个 500 GB 的模型）通过普通公网链路传输给全球各地的 Rollout 节点，那么网络延迟将彻底摧毁整个 RL 训练流。在异步强化学习训练中，为了保证策略不严重过时，我们要求权重同步的延迟控制在数秒之内。因此，传统的全量物理 Checkpoint 并不是一个正确的同步单位。

我们在此提出一个关键假设：在相邻的两个策略版本之间，Rollout 节点所能感知到的权重变化，是否**少于 1%**？

需要注意的是，这里的“Rollout 感知权重”指的是推理引擎实际载入的低精度权重（如 **BF16** 或 **FP8** 格式），而非 Trainer 内部保存的高精度（FP32）**优化器状态**（Optimizer States: 包含一阶、二阶动量等高精度中间变量）。如果这个假设成立，我们只需在网络上传输权重的稀疏差异补丁（Delta Patches）。

这一假设由以下两个物理机制共同支持：
1. **精度 Floor（最低变化门槛）**：以 BF16 格式为例，其尾数只有 7 位，这意味着在数值大小为 $\theta$ 的邻域内，其最小可表示间隔约为 $\theta / 128$。只有当优化器对 Master 权重的微调量跨越了相邻表示值之间的舍入边界（Rounding Boundary，约 $\theta / 256$）时，低精度的 Rollout 模型中才会有实际的值发生翻转。对于幅值接近 1 的权重，这个翻转门槛大约是 $0.0039$。如果优化器的单步调整量小于这个值，低精度的表示将完全保持不变。
2. **优化器 Push（步长控制）**：对于常用的 Adam 优化器，在忽略权重衰减项时，每个参数的更新步长大约等于**学习率**（Learning Rate）乘以归一化的梯度方向。在强化学习后训练中，学习率通常极小（通常在 $10^{-6}$ 到 $10^{-5}$ 量级）。因此，单步更新对权重的微调量非常微弱（例如单步调整量约为 $3 \times 10^{-6}$），这比 BF16 的舍入边界（$3.9 \times 10^{-3}$）小了近千倍。

这种微小的优化器步长与低精度的舍入边界相结合，产生了一种天然的**更新吸收效应**（Update Absorption）：虽然优化器在 FP32 高精度 Master 权重上的更新是 100% 稠密发生的，但当它们被投影（Cast）到 Rollout 引擎所使用的低精度空间时，绝大多数极其微小的变化都会被舍入机制抹平，最终在推理端呈现出极度的**稀疏性**（Sparsity）。

通过对比 $t-1$ 版本和 $t$ 版本的低精度表示，我们可以直接计算出一个极小的**比特等价二进制补丁**（Bit-equivalent Patch），仅包含变化的位置索引与替换的数值比特。这不是浮点数加法的增量更新，而是严格的比特级位替换，因此可以彻底避免由于浮点数累加导致的数值漂移（Additive Delta Drift）。对于大模型后训练，这种稀疏补丁的尺寸直接从数百 GB 缩减至数百 MB 甚至更低，使得通过公网链路进行秒级权重同步成为现实。

```
              Update Magnitude
                     ^
                     |          / BF16 Rounding Boundary (Floor: θ/256)
                     |         /
                     |        /   <-- [Absorption Region]
                     |       /    (Updates exist in Master Weights,
                     |      /     but are absorbed by Rounding)
                     |     /
  Adam Push (LR) ----+----+-------------------->
                     |   /
                     |  /         Unabsorbed (Weights change in BF16)
                     | /
                     +----------------------------> Weight Magnitude (θ)
```

不仅在 BF16 下如此，在业界推理引擎正迅速采纳的更低精度（如 **FP8**、**FP4** 或带有层次化缩放因子的 **NF4**）格式中，这种更新吸收效应更加显著，单步发生变化的比特比率往往进一步降低到 0.05% 到 0.15% 之间。这并非因为梯度本身是稀疏的（事实上，实测表明 99% 的参数在每一步都会产生非零梯度，梯度是稠密的），而是完全由低精度舍入的数学特性决定的。

<details>
<summary>Original English</summary>

So the next question is can we keep the exact same serve version there but send a much smaller object. So this is the bet. What if less than 1% of rollout visible weights got changed from one version to another one by rollout visible weights I mean the weights in the served rollout checkpoint uh not the FP32 optimizer states not the atom like moments like the weights are the rollouts engine which will actually use to serve maybe let's say the FBA or maybe MVP4 format if that's true we do not need to shift the entire full parameter over the network we just need to shift the change the server view the precision data got different. The important part here is like still a bit wise reconstruction. The rollout engine gets the same served served version. You would have gotten to as sync to the full checkpoint there. So if this works then the link shrinks from hundreds of gigabytes to maybe hundreds of megabytes and this is something smaller enough we can just send it across like the network. So right now we need to justify the less than 1% like claim. Why would this roll of visible like weights barely change? Uh now we get we will get into this mechanism. So it's kind of small atom like step meets finite precision. We need we need a two uh prerequisite. The first one two two uh ingredients. The ingredient one is the precision. The optimizer may keep very high precision master weights but the next four will pass really a BF6 visible view. That view has final resolution around a value of magnitude theta. uh BF16 spacing is roughly theta over 128. Uh that spacing is people call it oop basically the unit in the last piece. Basically it's the distance between the adjacent representable BF systeming value. But the update only needs to cross the near surrounding boundary to be viable to be visible. That boundary is about half of the oop. So roughly like the over 256 for weight around one. The BF systeming loop is around uh 0.78 and the near surrounding boundary is about 00039. If the optimizer notched the master weight by something like smaller than that uh the BFC visible value will run back so you will not see any change from the weight perspective rollout weight perspective. So that's the floor. The second primitive there is we call push. So for Adam maybe add here we just like we ignore the weight decay turn the per per sorry the the per parameter updates is the learning rate times a normalized direction the raw gradient can be dense and can have very different magnitudes across parameters and add like device by running uh gradients statistics. So the per wise push is usually on the order of learning rates. The paper passed I sight there they prove a bound. The addon step is at most B times the learning rates. So you do not need to actually remember the exact like bound there. Like the important notes is the adden makes the push small and very controlled. So at our post training learning rates the push is very very tiny. So that's the push. Combining these two primitives now we have to we have a whole like better picture assert the value changed only if the push clear the floor the push is the addent step roughly the learning rate the floor is the nearest the BF16 rounding boundary roughly theta over 256 take theta equal one the BF6 boundary is about 039 a typical added step here is around 3 millions so the update is more than a thousand smaller than the boundary so the BF visible value will not change. This is not saying the master weights uh in is frozen forever. It is saying the value that rollout engine would serve does not change on this part. So the whole magnet is pushing is is pushed versus four. Let's visualize this to have better understanding. The x-axis is the weight magnitude and the y-axis is the update magnitude. First we look at the red line. The red diagonal is the bxis invisible boundary. It's like theta over 256. And now we look at the green bound. This is the atom push. Is this roughly around the learning rate and with a conservative upper bound? So now we ask like where the most point fits for most of the weights. The red floor is above the green push. Those updates exists in the master weights but they are not visible in the served BI6 view. This step small weights on the left can move. Large weight on the right. They will just stay the same. They will be absorbed it. This is the addon absorption. This is why the serve update become very sparse. In this case, the object will be shipped is just a diff uh is just a diff not the entire FP32 automated state. We first look at the rollout view. The weight cast or projected to the dype that the rollout engine will be serving. Then we will be comparing the version t minus one and the version t. Uh in this view the patch is the patch is the change the position plus like uh replacement bits and also like some metadata. There are multiple lossless encoding. People can do selective overrides. They can people can also do xor. The important part is like there are bit equivalent bit level equivalent. So it's not a floating point addition. So there's no additive uh delta drift. If a roller engine applied the patch correctly, it reconstruct the sync server version bitwise. So everything so far we explained is about the full parameter which is hot power. So in full parameter reinforcement learning the automizer update the whole model but the roll of view patch is sparse as the thing we just explained lower is a small for a different purpose for for a different reason. The base model is frozen and the adapter is small enough by construction. So you do not need to pu So you do not need to have the push versus flow arguments here. So full parameter delta is small by absorption and the lower updates are small by construction. Let's dive into deeper about the paper itself. So the paper they mentioned more stats I will be showing here. The measurement is not great in sposity. It's not optimized state sposity. They cast weights to BF16 compare consecutive version stness and they compare the the version bitwise and they count what did not change over time across model family the result around 99% of the time is bit identical per step is also it also survives stillness even when the roller lax the changes set remain very small the important part is not only the number it is the patch is lossless change index plus imprint value reconstruct the exact same version. So a common misconception there is like the work it works because all our gradients are sparse. They are not. The paper reports the gradients are dense. About 99% of the parameter gets non-zero gradients. The FP32 master update is also dense. It's just small. The main thing is like the rollout weight change is just 1% from the perspective of rollout engine. So far we mostly talk about BF16 but the rollout of open serving even lower precision such as like MFP4 FA and NVF4 and we can see many many model providers doing this in the roll out. Uh this is not a training precision the training is just like in the normal BFC although people can do QA on that. So for fixed stale flow format the visibility for is roughly theta over two to the mantisa plus one. So as you can see the F4 will be higher and FA also will be between BF60 and F4 which means in even lower precision there will be less weight changed. So plane flows are easy to reason about. So each element has its own rounding sling one value cross the floor one value they just flip and changed group scale such in4 they are they're a bit different. This is the regime where many low precision serving system are moving towards right now. For in four each ways is quantized against a shared group scale and we can apply the same rationale and also we can observe similar thing for NBF4 is hierarchical scales and uh we can see there are different encoding and the displaying mechanism for MPV4. So this is the from one internal run. So here's the model we serve like GM 4.7 air in FP8 and we can see in the beginning there are only like 0.15% of weights got changed in the first step where the learning is high and after we have more training step like when the adden is going relatively stable and you can see the entire curve goes stable when you got only one 05% uh weight change during each step. So we can see this pattern showing more generally. We have a different research uh we saw different research sync have a similar conclusion and we saw a different model providers such as cursor composer 2 mi they all using add in the post training at at this point assume we can produce exact rollout weights version cheaply. The next question is how do we do this in practice?

</details>

### 系统实现与生态集成：Stitch 架构设计与 Sidecar 版本控制机制

在这一套将“稀疏 Delta 补丁”应用于“全球分布式算力”的系统设计中，**Stitch** 是 Modal 提供的一个高度解耦且框架无关（Framework-agnostic）的生产级实现方案。

在 Stitch 的拓扑设计中，主要包含以下核心组件：
* **Trainer 端**：在完成优化器计算步骤后，它直接提取低精度的 rollout 视图，并通过一个共享的**电子公告板**（Bulletin Board）广播最新的不可变权重版本标识。
* **Rollout 节点端**：运行在外部的 GPU 实例上，它们只从公告板上异步拉取最新的版本控制描述，并在本地重构出与 Trainer 端位级完全一致（Bitwise-identical）的推理 Checkpoint 文件（如 HuggingFace 的 `safetensors` 格式），随后直接交由主流的高性能推理引擎（如 **vLLM** 或 **SGLang**）运行。

为了使标准的开源推理引擎（如 vLLM）能够具备无侵入式的版本感知能力，Stitch 设计了一个轻量级的 **Sidecar（边车）** 进程，作为流量代理与本地权重的自治调控器。

```
                       [ Trainer Cluster (RDMA) ]
                                   │
              (Broadcast Weight Version / Delta Patches)
                                   ▼
                       [ Shared Bulletin Board ]
                                   │
                                   ▼
                      [ Rollout Island (Remote) ]
           ┌──────────────────────────────────────────────┐
           │                                              │
           │  Request ──> [ Stitch Sidecar ] ── Proxy ──> │
           │                    │ (Apply Patch)           │
           │                    ▼                         │
           │             [ Local Weights ]                │
           │                    │ (Load)                  │
           │                    ▼                         │
           │            [ vLLM/SGLang Engine ] ─────────> │
           └──────────────────────────────────────────────┘
```

当 RL 工作流向 Rollout 发送采样请求时，请求中会明确携带该轨迹生成所期望的模型版本 $V_{expected}$ 以及可接受的版本范围。Sidecar 的判断机制如下：
1. **完全匹配**：若本地模型引擎当前载入的版本正是 $V_{expected}$，Sidecar 直接将推理请求透传给推理后端。
2. **版本落后但可追赶**：若本地模型版本落后，但所需的 Delta 差分补丁在可用的过渡队列中，Sidecar 会迅速就地拦截并应用这些稀疏 Delta 补丁，完成本地模型的版本更新，随后恢复请求。
3. **无法追赶**：若网络出现较大延迟或版本脱节，Sidecar 会立即向任务调度系统返回 `Not Ready` 状态，触发弹性路由将请求分发给其他已就绪的节点。

通过这种方式，全球各云服务商的任何闲置、零散 GPU 都可以被实时组织成一个高度弹性的全球采样舰队（Elastic Rollout Fleet）。传统的 RL 算力紧缺被彻底打破，空闲的廉价推理算力可以直接无缝转化为强大的强化学习对齐动力。

虽然当前该系统主要在 Adam 优化器及后训练阶段取得了显著成效，但业界在更广泛领域的探索仍在继续，例如在预训练、SFT 阶段的泛化表现，以及在采用全新优化器（如 **Muon**，一种近期在 DeepSeek 等后训练中广受关注的正交优化算法，其在稀疏性边界上的表现与传统 Adam 存在本质差异）下的更新吸收效应，都将是下一阶段系统优化的前沿方向。

<details>
<summary>Original English</summary>

So from sparse delta to to our cross globe. How do we do this with elastic rollout engines and also explicit stness this is the whole shape the trainer saying a cluster after it got updated it publish immutable rollout based version to a shared bulletboard rollout engine leave outside of the training cluster which means they don't need to be RDM connected with the trainer they can be in different region or different providers. This is also request lane. You can see a request does not just say give me the completion. You will also say which version you will be sending request to and which version you will be accepting and the response will come back with the version and also like exact same information as if as if they are in the same cluster as the trainer. They will be returning tokens log prop like router replay information and many more metadata. The trainer writes immutable version to the broad after optimizer state uh after optimizer step engine pool version and the materialize it locally in the checkpoint layout. So they can just like serve directly the artifact defined version the engine choose how to how to load and shot it. It does not change it does not choose a different server version since it will be displaying in a hugging HF will be saved tensor format which is accepted widely by many rollout engines such as sjet and VLM. So we can support any compatible back end attention back end back end different parallelism compatible serving these type and any compatible GPUs there. We can talk more about the scar itself. The scikar is basically what makes a normal roller engine version aware. If the version is already at acceptable commit version, the psychar just proxy the request. If the engine is behind but can they can catch up the psychar just simply apply the missing transition. If they cannot get there the the psychar just simply return not ready. So this will be supporting elasticity rollout and any idle GPU can just be used with design with this design to support this aggregated roll out. So this is more like a system latency analyst incluster way syncing is fast because they have RDMA. Uh a full checkpoint across regions through network is pretty slow and but if we use the delta if we use exactly what we described previously we can decrease the number of like transfer transfer size from like 500 gigabytes to 5 500 megabytes. So it will be like extremely fast in seconds. So everything above was very general protocol. Stitch is one of very concrete implementation from model that we imple implementing everything above. So on the trainer side stitch publish uh what defines a rollout weights version and on the contract side you will be pulling out and record everything on the bulletboard and the only rollout side you will be pulling the latest weights and it start doing way sync across different region and different providers. So stitch itself is a very framework agnostic about trainer and engine and also transport. It's very async first and also agent first agentic first. By doing this we can have rollouts uh engines like autoscale globally. Each one self-s sync it weights serve accept version and return rollout metadata. That means scattered inference cap capacity became one elastic rollout fleet. Instead of being limited by the trainer cluster rollout can be the global pool. So inference capacity can now become our capacity. Last section we have some uh ongoing explorations. So we can see a lot of model providers such as moonshot and also deepc4 they have like they're adopting muan in their post training. Um does the spicy still hold for muan because a lot of thing we discussed previously only for Adam. Second question is async RL at the scale right now we can use the compute across the globe then how like how scalable is the fully async RL this is a very open-ended question there and uh third question is like does it generalize pass because like we have pre-training mid training and SFT like do we have can we apply same paradigm there last but not least we are working on some very hot problem and come work with us you can check the link there model Thank you.

</details>