---
author: AI Engineer
date: '2026-07-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KhYifX22yhE
speaker: AI Engineer
tags:
  - synthetic-data
  - distributed-training
  - agentic-coding
  - fp8-training
  - mixture-of-experts
title: 大模型规模化的喧嚣与真实：合成数据策略与分布式预训练工程实操
summary: 本文深入探讨了 poolside 在训练 Laguna 系列（包括 Laguna M.1、XS.2 及最新 118B MoE 架构的 Laguna S）模型时的前沿实践。文章详细介绍了 poolside 的合成数据流水线设计（包括多阶段生成、跨域迁移和双角色演进等四种核心模式），以及在大规模分布式预训练中，如何通过模型副本哈希校验（Model Replica Hash Checks）、FP32 精度积累和解决开源 DeepGemm FP8 算子中的竞态条件，来应对静默数据损坏与梯度爆炸等工程挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Marah Abdin
  - Robert McHardy
companies_orgs:
  - poolside
  - DeepSeek
products_models:
  - Laguna-M
  - Laguna-XS
  - Laguna-S
  - DeepGemm
media_books: []
status: evergreen
---
### 走向大众的 Laguna 模型与 poolside 的合成数据观

在人工智能模型不断走向规模化（Scaling）的背景下，AI 创业公司 **poolside** 宣布了一项重大转变：从原先专注于面向企业端（Enterprise）发布模型，转向同时面向大众提供服务。近期，poolside 已经在 Hugging Face 上开源了两个开放权重（Open-weight）模型：**Laguna M**（又称 Laguna M.1）和 **Laguna XS**（又称 Laguna XS.2），并发布了技术报告。在 poolside 的理念中，**合成数据**（Synthetic Data）并非用来彻底取代**有机数据**（Organic Data：即人类真实世界的原生数据），而是作为一种极其关键的互补手段。

人类的原生有机数据中隐藏着大量的隐式逻辑与结构，但它们的呈现方式往往不是模型学习的最佳形式。合成数据则提供了一条独特的通路，可以将这些隐式逻辑提取并投影到新的维度上，从而显式地展现出**隐式推理**（Implicit Rationale）、**隐式规划**（Implicit Planning）以及**隐式结构**。这种方法不仅能够填补真实数据的空白，还能对模型的 Token 呈现方式和训练逻辑进行正则化。在 Laguna XS.2 的训练中，合成数据已占到整个预训练数据混合配比（Data Mix）的 13%。目前，poolside 已经构建了一个包含 6 万亿 Token 且持续增长的预训练语料库。

<details>
<summary>Original English Source</summary>

Hi everybody. Thanks for coming to our talk. My name is Marah Abdin. I'm from poolside. I don't know if you're familiar with our models. Our data team and today my colleague Robert and I will be talking a little bit about some of the challenges that we've seen as we scale our models over here. Particularly if you haven't heard, we've switched recently from releasing our models towards enterprise to also releasing towards everybody. We've actually put out two open weight models. They're on Hugging Face a few weeks ago. We have Laguna M and Laguna XS. We also put out a tech report which has a ton of detail if you're interested. As you can see here by the Laguna M.1 and XS.2, this is actually because we have switched out quite a few things between those two models and so a big flavor of this talk is going to be about kind of how did we transition from one to two. And in fact, we've continued to do so and now we actually have a newer version and Robert will give a sneak peek about soon to be released model.

Okay. So I will be particularly talking about the synthetic data part of things. So there's three things that we did on the data side to kind of resolve some of the issues that we've seen with scale. One is that we implemented auto mixer that basically just gives us a chance to do a cheaper sweep on clusters of our sets before moving on to more expensive experiments. And then we improved, we just rethought our sampling of web data for higher recall. And then the third one is that we relied a lot more on synthetic data in a few forms which I'm going to. Okay, so before we kind of go into what does that mean and what have we done, etc. Why would we kind of, sometimes it's fair at least to ask why synthetic data and the thing is that at least at poolside we don't see it as a way to replace organic data. I don't see it so in the current state of the world at least, but it is a way to kind of complement it. And the thing is that organic data has a lot in it that is basically kind of implicitly hidden. A lot of things that could teach the model are not very presented in the most optimal way sometimes. And so synthetic data gives us a track to extract some of these features and project them on some new planes. And this is how we get to expose implicit rationale, implicit planning, implicit structure, and a way for us to fill gaps and regularize not only how we present the tokens, but also how we are teaching the model. For XS.2 in particular, we settled on 13% of the mix. This is only pre-training stages before post-training. And since then we've just been continuously generating more data in a bunch of directions. Now we have a six trillion token corpus that's continuously growing.

</details>

在确立了合成数据作为核心补充的定位后，如何在大规模训练中解决数据瓶颈成为了 poolside 的下一个攻关重点。

### 模块化合成数据流水线与四种核心变体模式

在大规模训练模型时，如果过于死板地追求数据质量而进行过度过滤，会导致模型在高质量数据上面临严重的**非最优重复**（Non-optimal Repetition），从而过早饱和。为了解决这一 Token 独特性问题，poolside 广泛采用了**合成重构**（Synthetic Rephrasing）技术来消除重复。在具体的系统工程实现上，poolside 将所有的合成数据流水线抽象为**模块化设计**，统一由以下六个核心组件构成：

*   **种子**（Seeds）：初始的提示词或文本种子。
*   **初级输入**（Primary Inputs）：构建生成任务的基础上下文。
*   **元数据**（Metadata）：控制生成的约束与属性。
*   **次级输入**（Secondary Inputs）：辅助模型生成的额外参考资料。
*   **生成器函数**（Generator Function）：可以是配备工具的 Agent，也可以是特定的 Prompt 模版。
*   **辅助功能**（Supplementary Functions）：过滤器（Filters）与验证器（Validators）。

利用这种高度可配置的模块化架构，poolside 在实践中推导出了四种典型的合成数据生成变体模式（Shapes）：
1.  **重构与去重**（Rephrasing）：在保留种子语义的前提下进行多样化表达，是成本最低、最易规模化的手段。
2.  **多阶段工作流**（Multi-stage Workflows）：将复杂的生成任务拆解。例如生成小说时，先分步生成场景设定、人物设定、大纲，最后逐章撰写，其效果远超单次生成。
3.  **跨域迁移**（Cross-domain Porting）：在不同的代码或数据格式间进行转换，例如将**数学问题**翻译并转化为**代码实现**。
4.  **多轮对抗演进**（Multi-turn Iteration）：让不同的 Agent 扮演裁判与进化者（Judge & Evolver）进行多轮对话，通过博弈不断演进数据难度。

为了承载这套复杂的生成逻辑，poolside 开发了名为 **Hive** 的配置化基础设施。它支持构建一个由自定义 Agent 组成的队列，开发者可以灵活配置每个 Agent 的提示词、模型、入队与出队机制、以及它们之间的**编排器**（Orchestrators）和全局**监督器**（Supervisor）。

<details>
<summary>Original English Source</summary>

Okay. So yeah, so what kind of what I just said is that we saw some limitations switching from Laguna M.1 to our XS.2 models. And so one of those things is that we started on data and this is really not a crazy kind of problem. We very intuitively started from a place on a smaller scale where we were basically focusing on quality versus quantity maybe a little too much because eventually when we started scaling our models, we had to scale our training budget and with that came some limitations because we started hitting repetition like non-optimal repetition on some of our high-quality data which saturated the model a little too early. So one of the ways we've particularly for this like a token uniqueness problem we relied on which is a very common form of synthetic data rephrasing which you know you just may heard in like Beyond Web for example. It's become pretty trendy these days. And you can see here that you know, this is an ablation result so take the numbers with a grain of salt but what persists pretty consistently is the diff between using the orange would be just the seeds with repetition and then the green would be replacing some of those repeated tokens with higher like with the multi-mode reverse or at least yeah, all of them or at least reducing the repetition. And so for rephrasing particular we did to the you know, what everyone's doing with the you know, generic kind of multi-mode very scalable pipeline but we also took it a step far and we did two other specialized pipelines, one to go from math to code and text and one to go specifically for STEM data. Just because this is a very cheap scalable pipeline so it kind of you kind of have to rely very heavily on the seed and we push a little further on that for the STEM documents.

Okay. So if you kind of think of everything in a kind of an modular way you can think of every synthetic data pipeline is composed of the same six components and so you have your seeds, your primary inputs, your metadata, your secondary inputs, your generator function which can be an agent with tools or one you know, with some prompt templates and then some supplementary functions like filters and validators and so on. And really you can compose just about all pipelines from like very simple to very expensive pipelines like this. And on that note and kind of we have covered quite a bit of wide scope on the axis complexity and you kind of can think of it if one end you have like the cheap scalable pipelines that have used smaller models and can get with it because they're seed heavy examples of phrasing. And then on the other end you have more complex pipelines with a little more orchestration in the workflows. This is reserved when we're building on something that's worth it. Educational data. But really this is how we're not blocked or limited by whatever teacher model can do. And this is how we can be ambitious in our synthetic data. Because the rule of thumb is if task is too hard for your model, then your model will start to fall on its face. Lose correctness, lose diversity. So break down the task, make it simpler.

And yeah, I will give some examples of kind of shapes rather than just like something more concrete about how do we use this modularity. And one shape is the formula writing is just rephrasing. We already talked about this. Multi-stage pipelines and multi-stage workflows. Basically this is what I also just said. You take a step and you break it down into multiple steps. You can aggregate the processing. Slowly build up the generation. Example of this were if you wanted to generate a novel for example, you could generate one chapter at a time, but you could also, you know, take it a little slowly. First generate, the setting, the character names, the character styles, the plot, you know, some twists. And then from there go into generate the chapters one by one. You will absolutely get a better novel. Third is cross-domain porting which really is just like moving from one mode to another. Example would be translating code. Another example would be something we did which is take our math problems and convert them to code. The last one is multi-turn role. What I mean by that all I mean is that instead of having kind of a very singular or linear or even non-linear kind of view of things you have more of an iteration. This encapsulates pretty much everything. And an example of that would be multi-turn chats when you have two agents talking to each other or a task evolution pipeline where, you know, you have a judge and an evolver going back and forth for some amount of time.

And so lastly, forewarning off to Robert, I do want to kind of just mention that because of the modularity of the way we think about this, we can implement an infrastructure that's pretty configurable. So this is how we present Hive. Hive is basically a way for us to easily construct generations where now you have a queue of agents that you define. Each one has, you know, its prompt, its parameters, its model, etc., inputs, outputs. But it also has when you can configure when enters the queue, when it exits, how many frequency to come in. And then we have orchestration in the middle between agents. And with this orchestrators are really useful because they give you more flexibility and kind of presenting a hierarchy between LLMs that are generating is very, this is how you police them, basically. But also give them some form of creativity and dynamically change instructions for the next agent or choose which agent goes next, which agent skipped, and so on. And lastly, you have the supervisor, which basically someone who polices the orchestrator and has more of a global view. Cool. Okay, that's it for me and Zendaya. I hope you learned something interesting. Handing over to Robert for pre-training stuff.

</details>

在解决了数据层面的生成与去重挑战后，当模型训练规模扩展至数千张 GPU 和千亿参数时，底层的分布式预训练工程又迎来了另一维度的静默损坏与精度陷阱。

### 分布式预训练工程：模型副本哈希校验与 GPU 静默损坏

在超大规模分布式预训练中，poolside 奉行“不信任任何事物”的原则。当训练任务在数千张 GPU 上运行，模型参数扩展到数百亿甚至数千亿时，硬件故障和底层软件缺陷变得不可避免。为了保障训练代码库与硬件环境的正确性，poolside 引入了**模型副本哈希校验**（Model Replica Hash Checks）这一核心保障机制。

在分布式数据并行（DDP）训练中，所有模型副本的权重在每一步更新后理论上必须保持绝对一致。poolside 在训练过程中定期计算所有副本权重的哈希值并进行比对。如果哈希值完全一致，则继续训练；一旦检测到任何哈希不匹配，系统会立即主动中断（Crash）训练，以防止错误的权重继续扩散。

这种机制成功捕捉到了多次**静默数据损坏**（Silent Data Corruption）的案例。例如在一次训练中，poolside 遭遇了坏损 GPU。对比实验表明，在模型配置、训练数据和代码实现完全相同的情况下，受损 GPU 导致了非常严重的隐蔽数据损坏，使得损失函数曲线（Loss Curve）严重抖动变陡，梯度范数（Gradient Norms）急剧膨胀。通过模型副本哈希校验，该故障在早期即被拦截，避免了昂贵算力资源的浪费。

<details>
<summary>Original English Source</summary>

All right, thank you, Mara. Um, cuz I will talk a little bit more on the actual pre-training side rather than just data. I liked in the previous talk, the speaker made a point that we should treat different data mixes holistically, different training stages. I want to make the same point that we should treat data and implementation of your training code base, correctness of it, and so on, also holistically. If you've got data that sucks, you can't train a good model. If you've got a training code base that sucks, you also can't.

Um, so I specifically focus on architecture work and distributed training and so on. Um and the way we look at things in my team is we don't trust anything. There's so many things that can go wrong when you scale models to billions of parameters to hundreds of billions of parameters training on thousands of GPUs and so on. And I want to show you some of the learnings that we got from training Laguna M.1. And yeah, some of the surprising things that happen at scale.

Um so one thing we do is we've got these model replica hashtags. So essentially when we train a model we've got multiple replicas of the same model, right? Distributed data parallel. And we know there's an invariant, the weight should always be the same across all of these replicas. That's something you can verify, right? You can calculate a hash over the weights and you know that should always be the same across all replicas. So we do that in training and periodically compare them. If all of these hashes are identical, then we know we can continue training. If they're not identical, we know something has gone seriously wrong because that should never happen. And we crash the training. And I'll give you some examples now of things that we've not shared before publicly like this. Um so I hope they're interesting.

Um so the first example here of that happens at scale are broken GPUs. On the left-hand side we've got two loss curves and on the right-hand side the corresponding gradient norms that we observed during training. And you can see that these loss curves look quite different, right? Like the purple one has got quite some bumps, looks a bit spiky. The gradient norms are huge for that run. And there's actually no difference in terms of model configuration, training data, training implementation between these runs. They're exactly the same run. Just in one of them we got unlucky and we had a broken GPU included. That broken GPU caused silent data corruption and therefore made the training behave the way it did. And that is one of those cases that you can catch with these hashtags because you know this computation should be the same across all replicas, but it wasn't.

</details>

然而，并不是所有的训练异常都源自硬件故障。在大规模训练中，数值精度与底层高性能算子的并发控制往往更容易引发隐蔽的灾难。

### 精度溢出陷阱与 DeepGemm FP8 算子的竞态条件调试

在大规模预训练的演进中，poolside 团队记录了两个典型的数值与算子层面的深水区 Bug：

1.  **反 unembedding 阶段的精度溢出与梯度爆炸**：
    在训练 Laguna M.1 到约 50,000 步时，模型突然停止收敛，损失函数曲线变平。经排查，由于模型规模增大，最后一层语言模型头（LM Head）前的激活值（Activations）急剧增长。由于 poolside 采用了张量并行（Tensor Parallel）来处理反嵌入（Unembedding）计算，其默认的中间结果累加是在 **BF16** 精度下进行的。在激活值极大的情况下，BF16 的尾数精度不足导致了严重的数值丢失，使得模型无法继续学习。团队通过将累加计算切换为 **FP32**，成功解决了这一数值瓶颈，使模型梯度范数开始稳步下降并恢复收敛。

2.  **FP8 预训练中的算子静默损坏**：
    在开发更庞大的 **Laguna S**（混合专家 MoE 架构，拥有 1180 亿总参数，80 亿激活参数，在 4000 张 GPU 上使用 30 万亿 Token 进行预训练）时，poolside 引入了基于开源 **DeepGemm** 的 FP8 算子进行加速训练。然而在训练过程中，团队频繁遭遇非法内存访问（Illegal Memory Access）以及梯度中出现 NaN 值。
    经过深度调试，他们发现底层算子存在**竞态条件**（Race Condition），导致约 0.5% 的梯度被静默损坏并被随机值替换。这种梯度层面的损坏是“权重副本哈希校验”机制的盲区，因为单次迭代的权重尚未发散，但长此以往会彻底破坏模型收敛。目前，poolside 已经向 DeepGemm 官方提交了修复该 Bug 的 Pull Request（PR）。

<details>
<summary>Original English Source</summary>

Which brings me to the next instance of that happens at scale. In this case exploding gradients. Um again, we're looking at two different loss curves and the corresponding gradient norm curves. The purple run is our initial training run for Laguna M.1. We're a bit further into training here around 50,000 steps or so. And you can see it stops converging, right? Like it just flattens out. And the reason here was that during training the activations grew and grew right before the LM head, the unembedding. And we have to perform some sort of accumulation here because we use tensor parallel for the unembedding. And that accumulation was performed in BF16 by default. And because of the growing scale that we observed in the activations, there wasn't enough numerical precision available anymore to do this accurately. And hence the model just couldn't learn anymore. And this is also very dramatic point for this to happen because from there on it really like back propagates into the full model trunk. The orange curve is essentially just adding a fix on that. So, we took the checkpoint from the purple curve. We moved that accumulation into FP32 and from there on the model started converging again. The gradient norm, as you can see, actually started decreasing. Before then we had an increasing trend. And this is also something you can only observe at scale. And that will break your model if you're not careful about it.

So, as Mara said, we took all of these insights on data, on numerics, and so on, and we turned them from M.1 into XGen-2. That's why we say it's a new generation model. This included increasing diversity, reducing data repetitions, all of these numerical things I just mentioned, and just adding more observability and checks on that side, as well as generally optimizing the training in the architecture. And XGen-2, if you look at it, it's open weights, right? So, you can download and use it for free. It's one of the most competitive models for its size and for coding specifically. That's what we focus on: Agentic coding. Um, so we're pretty happy with it.

However, you can say that the model with 33 billion parameters is pretty small. Like you wouldn't probably observe any issues anyways training it. So, what was important to us was to scale this, right? And this is where Laguna S comes in. This model is not public yet, so this is a preview. As I said, we treated XS as a test bed in a sense, and with Laguna S we scaled this to a model that's 118 billion total parameters and 8B active parameters. Again, we trained it on 30 trillion tokens on 4,000 GPUs. So, the scale was sufficient to not only test whether all the improvements we made on the data and architectural side had hold, but also if any of these numerical issues come up again. And of course, something happened. In this case, it doesn't actually have anything to do with scale, so it was just unfortunate. In this case, we had a race condition because we added FP8 training based on DeepGemm FP8 kernels that are also like open source. We noticed these because we hit illegal memory accesses as well as NaNs in the gradients, which after a while of debugging we traced back to those kernels.

There's also an unobservable effect that you wouldn't know about if you don't know that there's an issue. In our case, we noticed about 0.5% of the gradient gets silently corrupted, essentially replaced by random values. We do have a fix available that's in a PR right now. It's not been merged to DeepGemm yet, but it's public on that QR code if anyone is interested. And it's also an interesting point because it's a blind check and a blind spot in the hash checks. In real training runs, you don't have any redundancy where you have the same model weights and the same data, so you can never check if forward and backward actually behave the same across different model replicas. So, you can also never check if there's a race condition in that. That's something that we're working on right now to essentially have a hash checker that can also do that as a at least as a dry run.

</details>

在跨越了算子和精度的重重难关后，这些底层的工程沉淀最终在模型能力评测中转化为了显著的性能跃升。

### Laguna S 的评测表现与智能体编程愿景

作为对 poolside 预训练工程与合成数据配方的一次大考，**Laguna S** 在多项基准评测中展现了极强的竞争力。需要指出的是，当前结果为预训练基座模型（Base Model）的评测指标，后续的微调（Post-training）过程仍在进行中：

*   **编程基准测试**：在 **MultiPL-E**、**LiveCodeBench** 和 **BigCodeBench** 上，Laguna S 不仅大幅超越了前代较小的 Laguna XS.2，也击败了体量更大的 Laguna M.1。同时，其表现优于 GLM-4-Air、Qwen-2.5（即 we turn 360）以及体量更大的 DeepSeek-V2.5-Flash-Max。
*   **智能体代理能力**：在用于评估预训练阶段 Agent 代理能力的 **SWE-bench**（Agentless 评测）中，Laguna S 的表现显著优于所有参与测试的其他同类模型。
*   **通用知识权衡**：在 **MMLU Pro** 通用知识库评测中，Laguna S 弱于 Llama-3-Nemotron 和 DeepSeek。但这符合 poolside 的战略取向——团队在训练中并没有针对通用知识灌注过多资源，而是将全部重心放在了打造最强大的**智能体编程**（Agentic Coding）模型上。

poolside 表示，随着这套验证过的预训练与数据配方成功扩展，Laguna S 将在不久的将来以开源权重（Open Weights）的形式向公众免费发布，从而进一步践行其将强大编程模型带给全球开发者的愿景。

<details>
<summary>Original English Source</summary>

And I want to end on some early results from this new model and demonstrating how it performs against some open weight models and also against our previous models. So, first I want to caveat this with these are base model evals, right? They are partly indicative of how the final model will look, but also not perfectly, right? There's still post training happening. Not all of these will translate one-to-one to the final model. But if we look at them specifically on the coding part of the evals, so for instance MultiPL-E, LiveCodeBench, BigCodeBench, Laguna S is not only stronger than XS.2, which is our previous smaller model that performed very well, but also than the much larger M.1. And it's also much better than GLM-4-Air, which is admittedly a bit older, and then Qwen 2.5, which is quite recent, and then DeepSeek-V2.5-Flash-Max, which is quite recent and a fair bit larger. We can see it's competitive on Big Bench Hard for instance. It doesn't achieve the top eval results compared to these models, but it's quite close. We also see it's quite close on EvalPlus, and quite importantly for us, it does very well on SWE-bench Agentless, which we use to sort of proxy agentic performance during pre-training. And in that case it performs much better than all the other models we tested here. I also want to point out that of course there are like it's not the strongest model in the world, right? Like for instance MMLU Pro knowledge benchmark is something we don't care about that much compared to coding because we want to build the strongest agentic coding models. So here like compared to Nemotron and DeepSeek we have to say that they perform much better, and this mainly comes down due to data, right? It's a data gap that we could plug if we wanted to. But I think the point is all of the things we found before were included in the recipe. The recipe held, it scaled, and we will continue scaling it from here. So this model will also be available sometime in the future relatively soon. Again open weights, so all of you can download it and use it for free. And with that I want to thank everyone for attending our talk. I added also a link to our careers page and our Twitter page if you want to check it out. And yeah, thank you very much.

>> [music]

>> Hey.

</details>