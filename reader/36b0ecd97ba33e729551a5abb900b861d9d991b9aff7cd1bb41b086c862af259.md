---
author: AI Engineer
date: '2026-09-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=oVsEddfhdxc
speaker: AI Engineer
tags:
  - automated-ai-research
  - recursive-self-improvement
  - llm-benchmarking
  - optimizer-speedrun
  - autonomous-agents
title: 让AI与人类研究员竞速：自动化AI科研的极限与真实瓶颈
summary: Prime Intellect的研究员分享了在nanoGPT和优化器竞速环境（Speedrun）中，让Claude Code、Codex与人类开发者同台竞争的实验结果。研究显示，尽管AI在工程迭代与调参速度上表现出色并能刷新人类记录，但目前仍缺乏真正的科学发现与机制创新能力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Prime Intellect
products_models:
  - Claude Code
  - Codex
media_books: []
status: evergreen
---
### 递归自我改进迷思：为何需要开源独立的AI科研基准？

大家好，感谢各位的到来。今天我非常兴奋能与大家探讨**自动化AI研究**（Automated AI Research: 利用AI自主进行模型架构设计、训练与调优的过程），特别是当前最先进的基座模型在执行自动化AI科研任务时的真实表现。我是Amy，在**Prime Intellect**担任研究工程师，今天将分享我们在该领域的实践与探索。

首先，我想解释我们为何要开展这项工作，以及为何坚持以开源、公开的方式推进。顶级闭源实验室一直向公众描绘一个即将到来的愿景——**递归自我改进**（Recursive Self-Improvement: 模型在无需人类干预的情况下自主训练并迭代生成更强模型的能力），并将其视作某种潜在的生存风险。然而现实是，整个社区缺乏任何定量基准来检验这一论断是否属实；更重要的是，独立研究机构与小型实验室无法通过公开基准来评估这种能力究竟何时会真正落地。此外，我们坚信未来绝大部分科学研究都将深度依赖AI工具，因此深入理解AI如何开展科研——不仅限于AI算法本身，更关乎通用的科研探索能力——已成为极其紧迫的课题。我们需要构建一个标准化的真实环境来评测模型。

<details>
<summary>Original English Source</summary>

Hello, uh, greetings to everyone. Thank you for being here. Yes, I'm really excited to talk about automated AI research today and, in particular, how all these advanced models are performing automated AI research tasks. So, I'm Amy. I work at Prime Intellect as a research engineer, and yes, I will talk about our work in this area.

So first I want to explain a little bit why we're doing this and why we think it's so important to do it openly. So, first of all, I think we all agree that we've heard from big labs about this dangerous thing called "recursive self-improvement," which is coming very soon. So, recursive self-improvement is when models train other models without human intervention, essentially. But we don't have any benchmark to quantify whether that's true or not, right? And even more so, we don't have an independent benchmark from small laboratories to understand whether to expect this in the near future.

The other part is that we think it's extremely important to understand how these models conduct research, because we believe that a significant portion of scientific research in the coming years will also be based on AI tools. So it's very important to understand how these models do research, not just AI research. So we're trying to create an environment to test the models' ability to do that.
</details>

### 从极速nanoGPT到优化器竞速：构建闭环评测与强化反馈环境

这一探索的起点源自**Andrej Karpathy**。他此前制作了一个趣味视频，在约90分钟内从零开始完整训练了**GPT-2**。要知道，在两年前训练GPT-2通常需要数周时间，而压缩到90分钟已是不可思议的飞跃。这里的“复现GPT-2”有着明确的量化定义：在最短时间内使模型达到与原始GPT-2相同的目标验证集损失值（Validation Loss）。只要达到该损失收敛线，即可视为模型具备同等性能。

随后，开源社区基于此GitHub仓库演化出了由Kyler Jordan主导的**modded-nanogpt**项目。社区研究者通过极致的代码与算法优化，先将训练时间压缩到45分钟，经过两年协同攻坚，最终实现将达到GPT-2验证损失的训练时间缩减至2分钟以内。这是一个由无数顶尖研究者合力打造的极强基准，也因此成为我们**竞速评测**（Speedrun）的理想实验场。

整个机制犹如一场明确的游戏：唯一目标是以最短时间达成目标损失率。在初代**nanoGPT Speedrun**中，除了必须严格统一训练集与验证集之外，几乎没有任何限制，参赛者可以自由修改模型架构、引入Mixture of Experts（MoE: 混合专家系统）、调整注意力机制等。而数月前发布的**Optimizer Speedrun**（优化器极速赛）则收紧了规则，参赛者只能修改与优化器相关的参数或算法（例如将Adam替换为New Shampoo等任意自研优化器）。这种设定让任务更具学术研究属性，不再过度偏向系统底层工程提速，而是专注于在固定算力开销下寻找最优算法。

我们选择Speedrun作为自动化AI科研测试环境的核心考量在于：
* **强化学习奖励闭环**：任务具有极高的确定性，打破历史记录则给予正向奖励（Positive Reward），失败则记零或负向反馈；
* **高频低延迟迭代**：单次优化器运行仅需15至20分钟，验证周期短；
* **清晰可验证的假设检验**：规则透明，任何新算法的优劣都可以被严谨证伪，具备支撑科学突破的实验土壤。

<details>
<summary>Original English Source</summary>

It all started with Andrej Karpathy, who essentially had fun creating this video where he trained GPT-2 from scratch in about 90 minutes. Training GPT-2 takes weeks, and two years ago it seemed to only take 90 minutes. So what does it mean to recreate GPT-2 in 90 minutes? This means that in 90 minutes you have reached the target loss function, and yes, at this point, when you have the same loss rate as GPT-2, you consider your model to have roughly the same performance.

Then what happened was that the community took this repository, this GitHub repository, and created another one called "modded nano GPT," and this work was led by someone named Kyler Jordan. And it turns out that they cut that 90 minutes down to 45, and then — no, we can train a model with the GPT-2 validation loss rate in less than 2 minutes, which is, frankly, crazy. And it took about 2 years.

So, this is a very strong benchmark that many talented researchers have worked on. Um, yeah, that's why we decided to choose this environment for the speedrun. So, what do you see? It's a kind of game. So, the goal of the game is to reach this loss rate in the shortest amount of time. So, this is nano GPT-1. And you have almost no restrictions. The only limitation is that you have to use the same data for validation and training, right?

Um, there's a new speedrun called "optimizer speedrun" released a few months ago. And here the situation is a bit different, as you can only change the parameters related to the optimizer. So, for example, in NanoGPT you can change the architecture, do MOE, change the focus, etc. In the optimizer speedrun, you can just change, for example, Adam to new shampoo or any other of your favorite optimizers. Um, yeah, and it's a bit more like research, because it's not so much about optimizing the program for maximum speed, but about finding the best method, regardless of the time spent on the computer, right?

So, yes. Why choose Speedrun as an environment for automated artificial intelligence research? First, we think this is a good estimate, then we'll see why, and that's the main focus of this conversation. But we also think it's probably a good learning environment because it's a way to provide a reward to the model. So, the reward is positive if the model completed the speedrun and broke the previous record, sorry. And the reward is zero or negative if she fails. So, this is a good environment for training the model. It's also pretty fast, as you can see, the previous record for the optimizer was around 2 minutes. Each run takes approximately 15–20 minutes. And yes, there are, in fact, clear rules there. And we also think it's a good environment for making discoveries. That is, a kind of breakthrough in 2D research, because there are these clear rules that can be tested or refuted. Um, yes.
</details>

### 自主科研智能体实战：架构调度与工作模式分异

在两月前的优化器竞速赛中，我们正式部署了两组AI智能体与人类社区竞争：一组是基于高级推理架构的**Codex**，另一组是**Claude Code**。我们直接将智能体接入计算集群并实施全自主迭代，经历了V1、V2至V3多个版本。在最终冲刺阶段（V3），当我们发现智能体的成绩落后于人类最新进展时，便将人类社区近几周沉淀的全部记录与代码注入智能体，让其尝试全面超越人类战绩。同时，我们还设立了专门考察**新颖性**（Novelty）的独立赛道，要求智能体必须通过原创设计而非微调已知方案来刷新纪录。

整套系统的交互架构保持了极简设计：
* **目标与规则约束文件**：我们创建了类似 `goal.md` 与 `agents.md` 的规范配置文件，规定研究边界与可探索范围；
* **集群资源调度**：智能体通过**Slurm**作业调度系统使用 `sbatch` 提交计算任务。为了兼顾资源效率，智能体被配置为使用**可抢占权限**（Preemptible Permission: 当其他人类研究员需要占用计算节点时，系统会自动中止并取消智能体的排队或执行任务）；
* **统计显著性验证**：智能体负责实时解析训练日志，评估当前迭代是否打破纪录。所有声称打破纪录的成果都必须通过严格的统计显著性阈值，防止由于随机数种子或训练波动导致的偶然收敛。

在长期自主运行中，不同模型展现出了截然不同的行为特征与工作模式：
* **坚韧度与停机行为**：Claude Code暴露出明显的心理防御倾向，每运行9至10小时就会主动放弃并报告“该记录已达物理极限，我无法打破”，必须通过人工外部干预强制指令其开辟新方向，导致近三分之一的算力时间处于闲置状态；相反，Codex表现出极致的机械化韧性，从不提问或抱怨，保持持续不间断的高强度实验探索。
* **工作记忆与思考习惯**：在提供给智能体记录思考过程的草稿笔记本（Draft Notebook / Active Memory）中，Codex的读写频次大幅超越其他模型（在经动作总数标准化处理后依然显著更高），呈现出极强的行为特异性；同时两者的行文风格迥异，Claude在刷新纪录时表现出使用大量Emoji的情绪化兴奋，而Codex则始终保持冷静克制的结构化陈述（“这是我的决策”、“下一步方案如下”）。
* **资源消耗与压缩机制**：Codex衍生出的子智能体（Subagents）数量与Token总消耗量远超Claude（累计达到数十亿Token级别，涵盖输入缓存）。由于Codex仅有250k上下文窗口，其每小时执行约20次上下文压缩（Compression），而Claude在整个生命周期内极少触发深度压缩。

<details>
<summary>Original English Source</summary>

So, yes. Um, so what we did was: the release was about 2 months ago, and there was this "optimizer speedrun," so we decided to compete with the community by running two AI agents. So, Codex and Cloud Code. Codex was like GPT-5.5 with XAI, and Cloud Code was like Opus 4.8 with XAI. Um, and yeah, we decided to actually release an agent onto our cluster, uh, and, uh, just iterate over it. So we have versions V1, V2, V3—this is essentially us stopping the agent and then restarting it.

V3, uh, was about a day or two before the release, because we saw that our agents were no longer having the best results. So we're like, okay, take all the human, uh, records from the last few weeks and just try to beat them, in any task. Yes. And we also have a direction of novelty, where the goal is, uh, to break the record only thanks to new ideas. Um, and we see that it was more difficult for the models.

So our structure is very simple. Honestly, we could have just replaced it with /goal, but at that time, there was no /goal. So we created our own goal.md. It's funny that we chose the same name. And we had a goal.md and, like, agents.md that defines the rules, and we let the agent propose ideas, and then it can submit tasks via Sbatch to our Slurm cluster. And, actually, this is how it works: it can send tasks to available nodes, but only with a certain permission, which means if someone wants to use that node, uh, the model just cancels the task. This is called preemptible permission. So, yes.

Then he measured, essentially, the training logs and then decided whether it was a record or not. To confirm a record, you essentially have to pass a statistical threshold to make sure it's not just random number optimization and coincidence, right?

So, yes, some results from these experiments. The first thing that was honestly really painful to work with was that code-code-code-code kept stopping every 9 or 10 hours and basically saying, “Yeah, I can’t beat the record. It's too hard for me. There is no way to go beyond it." And then I just said, "Okay, keep exploring a new direction." And he worked for 10 hours again, and then he said, "Yeah, I can't break the record," and so on. So, essentially, a third of the time the code-code agent was on standby because I had no way to control it. And Codex is the complete opposite, it just worked all the time. And, yes, he almost never, ever asked questions, and, and, and was very impressive in that regard.

Um, we also give the model the ability to write down a bunch of things in a so-called "draft notebook", which is actually the model's active memory. We noticed that Codex mostly writes a lot to this notebook. So all the graphs I'll show are normalized by the number of active actions. This means that Codex doesn't just work harder, it's truly a different behavior model. So, yes, you see that he writes a lot more in the sketchbook, in this memory. And the tone of each file was also very different. For example, Claude was excited about setting new records, using a bunch of emojis and such. And Claude X behaved with restraint: "That's what I do." "Here is the decision I make." "What will I do next?" Very robotic.

Uh, yes. We also have this graph where we see that Claude X created significantly more subagents than Claude. We saw that Claude X spent significantly more tokens than Claude. I think overall it was somewhere around billions of tokens. But of course there is caching of input tokens, so it's not exactly 1 billion output tokens. So, yes. We also see that Claude X was doing a lot of compression because he only had a context window of 250k. And Claude only did it once an hour. And Claude X more often. No, even less than once an hour, I mean, once during the entire launch for Claude, and for Claude X it was about 20 times an hour. So, yes.
</details>

### 实验评测与学术复现：AI打败人类记录背后的真相与局限

在持续5至6天的全周期优化器竞速评测中，各主流前沿智能体与人类顶尖水平的对比曲线呈现出极具启示性的特征：
* **人类基准的超越**：当时人类社区的最佳训练步数纪录约为2,990步。Claude在启动初期凭借精准的搜索策略迅速建立优势，最终将人类纪录缩减了50至60步；Codex则进一步扩大了领先优势，比人类纪录少走约80步（比Claude领先20步）。
* **模型间的性能轨迹**：Claude在优化路径上呈现平滑、稳步提升的线性特征；而**Kimi**（基于Kimi K2.7 Code）则呈现典型的**阶跃函数**（Step Function: 长时间处于平台期后突然出现单点爆发式突破），在第4天成功实现跳跃并超越Codex创造新高。
* **Token能效比对比**：在时间维度上各模型难分伯仲，但若将坐标轴切换为生成Token量，Kimi表现出极其惊人的能效比，消耗极低的Token便完成了高质量调优；而Claude在最大化推理模式下消耗了海量Token。
* **文献检索驱动的红利**：不同模型对前沿学术文献的利用策略截然不同。Claude频繁通过外部检索挖掘论文，甚至成功检索到一篇其他模型均未发现的冷门学术论文，并直接将其中的技巧移植到了优化器代码中，从而打破了记录。

然而，这一连串打破纪录的繁荣景象背后隐藏着AI科研能力的根本性缺陷：**所有模型均未能产生任何颠覆性的原创发现**。在运行智能体之前，我们原本期望它们能突破人类思维定势，构想出前所未见的新型优化器机制。但真实情况是，智能体几乎全部依靠**文献拼接工程**（Paper Stitched Tricks）——将论文A的Trick与论文B的超参数组合，或者在既有算法上做微小的“加一”增量修补。对于即便人类全职研究者几周内就能摸索出的全新机制或底层数学洞察，当前的AI大模型仍完全不具备发现能力。

<details>
<summary>Original English Source</summary>

And here are the main results. This graph shows the progress of human results—that's the white line. And in red you see Claude. Although it should be orange, it doesn't matter. And in blue you see Claude X, right? You see that almost always Claude and Claude X are better than the human record, and Claude is very accurate at the start, achieving high results very quickly.

And something else very important: the model has the ability to get human results at any time, and that's exactly what Codex did... sorry, Claude, because when I restarted it, it got a new human record and improved it. Um, so here's the result: I think the best record at that time was about 2,990 steps, and we beat it by 50 or 60 steps for Claude, and Codex was 20 steps ahead. So I think that's both impressive and, well, yeah.

Um, so we...it's not released yet. This is what we are working on now. And basically the idea is that it's a cool experiment, but it lacks structure, you know? If you want to do a real benchmark, you need to use multiple initialization options, do everything properly, where you put all the models in the same conditions, right? So that's what we're working on right now, and the idea is to do three different directions. One without any access to really measure the models' ability to conduct AI research based only on knowledge of the model's weights, one with only access to articles from the archive, and one with full access. So, he also has access to the latest developments of people. And for this, we plan to conduct both a nano GPT track, which is original, and an optimizer speedrun, where we limit the optimizer to only the novelty, essentially.

Um, yeah, so I'll present some results on the optimizer speedrun. This is, in fact, what we got. We let the agent iterate for almost 6 days, let's say 5 days, and we see that Codex, Kimi, and Claude are very efficient. So, it's not a complete launch for GLM, right? The model is actually still continuing to iterate on our cluster. But we see that Claude is showing a very good result again. And we see that, surprisingly, Kimi is also very competitive. He kind of made a breakthrough around day four when he surpassed Codex with a new record, right?

It's also interesting to see that Claude is more progressive in how he improves the record, and Kimi has a real step function where he makes a breakthrough and so on. So, this is an interesting timeline, because 6 days is quite a long time to evaluate. But you can change this axis to the number of output tokens, and then the story will be different, because Claude consumes much more tokens in max mode than Codex and Kimi. And you also see that Kimi is actually very efficient in terms of the number of tokens she uses. So, this is Kimi K 2.7 code.

Hmm, well, yes. We also see that they have different approaches to using literature and scientific articles. For example, Claude performs a lot of article searches, and in fact, Claude found an article that no other model found, and this resulted in the best result. So it's pretty funny.

And, uh, yes. One of the main problems with all of this is that when I ran these agents—and I think it's important for you to remember this for this talk—when I ran these different agents, I expected them to come up with some crazy ideas for the optimizer that no one had discovered before. But, to be honest, that wasn't the case. They used some clever tricks, where they basically combined different articles. They made a kind of "plus one" improvement to many methods, but no new optimizer or mechanism came from these models. And I think it's quite telling that even for something that's not simple, but, I would say, accessible to people, right? For human researchers who spend days and weeks, the model cannot find new optimizers and mechanisms.
</details>

### 下一代科学发现范式：多智能体进化演算法与云端沙盒基建

为了打破上述“仅会调参整合、无法实现底层发现”的僵局，我们正在将评价体系向真正的**科学发现引擎**升级。该方案深度汲取了Google **AlphaEvolve**及演化算法研究的思想，致力于构建一个具备高维筛选与自我拓展能力的多智能体协作系统：
1. **异构生成与经济性协作**：引入生成器网络（Generators），混合调用闭源顶尖模型与高性价比开源小模型提出假设，由小模型以极低推理成本快速提出大量候选思想；
2. **快速沙盒试验与客观奖励**：候选方案被分配至轻量化算力单元进行极速试跑，提取客观损失指标作为初步过滤条件；
3. **独立裁判机制**（Judge with Scientific Taste）：引入具备独立科研审美的裁判智能体。该裁判游离于主循环之外，结合前沿科研方法论对新颖性、数学简洁性及理论深度进行非标量定性评价，打破单纯追求单机局部提速的死胡同；
4. **跨尺度验证与可扩展性校验**（Scaling Validation）：针对社区常出现的“小参数下有效、大模型尺度上失效”问题，将高分候选算法逐步扩展至更大参数规模与海量Token上复测，验证其真实扩展法则（Scaling Laws）。

在基础设施落地层面，我们正在推进一系列配套工具的研发：
* **GPU沙盒运行环境**（GPU Sandbox）：专为智能体自主运行、代码编译与训练设计的安全容器隔离区；
* **LLM基础设施专用智能体**：对具备文件读写、指令下发与代码测试能力的开源模型进行指令微调与领域强化；
* **全生命周期训练评估套件**：推出并开源如 **verify-primary** 与状态训练框架，支持对各类复杂训练环境进行快速接入，目前已在超大规模开源模型上进行了高并发测试与工程打磨。

我们坚定地推进这一切，是因为真正的递归自我改进绝不应被禁锢在少数闭源巨头的黑盒中。通过打造透明、严谨且人人皆可参与的开源评测与发现环境，我们才能真正揭示机器智能的边界，让自动化科学研究真正赋能每一个普通研究者。

<details>
<summary>Original English Source</summary>

So we think there's a way to make this better for discovery, not just for evaluation. And it's very inspired by Google's Alpha Evolve work, as well as a bunch of articles that have been published since then. It's a kind of multi-agent system that interacts together—a bunch of generators. You have closed-source models, but you also have open-source models that are extremely cost-effective, right? They can suggest ideas, then you run a quick run, get a reward, and then you have a judge who provides quality feedback. It could also be that the judge has a certain taste. You can make it so that the judge has his own vision of whether this method is good or not if it is outside the main loop.

And then you can decide which method you want to scale to more parameters and tokens. So, this is kind of the scalable part of the rapid run, because a lot of people in the development community often say that their methods don't work at scale. So, I think it's very important to also add scaling elements to this cycle. Uh, and I think the people here are also extremely helpful in evaluating agents' ideas, steering them in the right direction, etc.

Um, yeah, we haven't tried that yet. That is, we are trying to do this now, and we hope that it will at least lead to new discoveries in artificial intelligence research. And there is also a way to define multiple speedruns. So this is the next slide. Uh, if you want, it's from the SoftBank slides, but if you don't know that link, that's okay. This means that you don't spend too much time online. But the idea is that by changing the goals and constraints of the speedrun, you can create a lot of variety and make the model move in a certain direction. And, uh, yes, making these discoveries.

So, at Hummingbird, we're doing a lot in that direction. There's a lot of stuff here that we, well, most of it we haven't released yet, but we're working on a GPU sandbox to allow models to iterate in the sandbox, because that's what you need a GPU sandbox for. We are working on our own agents that are very efficient for the LLM infrastructure. This means you have a file system, you can write and read information, and you can run software coding tools. We train the model to be good at this based on open source models.

What we have already released is a set of libraries and a product called "verify primary" or "state training" where you can train and evaluate any environments and the model that can be trained can be, for example, GNM 5.2, which is very large, and yes, we are working hard to make these libraries very efficient to provide the best quality to our customers.

Yes? I mean, yes, I'm very passionate about this field. Again, I think it's extremely important that some of this recursive self-improvement happens openly, because in reality, a lot of people don't work in big labs. So, we need to make it easy for people to understand how all these models work, to conduct research, etc. So that's our goal, and thank you very much.
</details>