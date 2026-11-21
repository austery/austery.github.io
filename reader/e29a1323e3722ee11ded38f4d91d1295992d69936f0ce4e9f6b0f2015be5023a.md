---
author: a16z
date: '2026-11-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=h_aA1-R70E8
speaker: a16z
tags:
  - artificial-intelligence
  - recursive-self-improvement
  - ai-alignment
  - frontier-model
  - machine-learning
title: OpenAI 联合创始人与研究主管解析递归自我改进（RSI）与 AI 对齐
summary: OpenAI 首席研究官 Mark Chen 与 Thinking Machines 联合创始人 John Schulman 讨论了递归自我改进（RSI）的定义、当前进展与技术瓶颈。讨论指出目前 AI 主要作为研究加速助手，距离完全自主闭环仍有距离；同时探讨了研究品味培养、评估指标、算力约束，以及利用 RSI 推进 AI 对齐与分散化对齐的前景。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Mark Chen
  - John Schulman
  - Jakub Pachocki
  - Sarah Wang
  - Ali Ghodsi
companies_orgs:
  - OpenAI
  - Thinking Machines
  - Anthropic
  - A16Z
products_models:
  - ChatGPT
  - Codex
  - Fable
media_books: []
status: evergreen
---
### 递归自我改进（RSI）的概念与前沿探索

这是一张展示 OpenAI 前沿模型能力增长的图表。在 2027 年，由于自动化 AI 研究（AI 加速自身开发）的触发，它开始急剧攀升。理论上，这可能会复合形成能力的指数级增长，从而导致那场著名的被称作人类最后发明的事件。这个想法作为思维实验已经存在了一段时间。
<details><summary>Original English</summary>
This is a chart showing the growing capability of OpenAI's frontier models. In 2027, it begins a steep climb set off by automated AI research where AI's accelerate their own development. In theory, this could compound in an exponential growth in capability, leading to what [music] has been famously called the last invention that man ever make. This idea has been around for a while as a [music] thought experiment.
</details>

>> 我们总有一天能够设计出可以持续自我改进的系统。
<details><summary>Original English</summary>
>> We will one day be able to design systems that can go on improving themselves.
</details>

>> 但是前沿实验室和几家初创公司正越来越接近实现这一目标。它有一个名字。
<details><summary>Original English</summary>
>> But Frontier Labs and several startups are getting closer [music] to realizing this. It has a name.
</details>

>> 递归自我改进。
<details><summary>Original English</summary>
>> Recursive self-improvement.
</details>

>> 递归自我改进。
<details><summary>Original English</summary>
>> Recursive self-improvement.
</details>

>> 递归自我改进，简称 RSI。
关于如何准确定义它、其影响以及我们距离它有多近，存在着很多争论。带着围绕这个主题的所有好奇，我想与两位处在前沿的顶尖研究人员坐下来聊聊。
<details><summary>Original English</summary>
>> Recursive [music] self-improvement or RSI. There's a lot of debate about how exactly to define it, the repercussions, [music] and how close we are to it. With all the curiosity around the topic, I wanted to sit down with two leading researchers at the frontier. [music]
</details>

>> RSI 的问题就像 AGI 一样，每个人都有自己的一套定义方式。
<details><summary>Original English</summary>
>> The problem with RSI just like with AGI is that everyone has their own way of defining it.
</details>

>> 那是 Mark Chen，OpenAI 的首席研究官。他在这家公司工作了八年多，自 2025 年以来一直与 Jakub Pachocki 共同领导他们的研究工作。
<details><summary>Original English</summary>
>> That's Mark Chen, the chief research officer at OpenAI. He's been with the company for over eight years and has been co-leading their research efforts with Jakub Pachocki since 2025. [music]
</details>

>> 当我们思考对齐的未来时，确实感觉在某种程度上 RSI 必须错综复杂且深度地融入到这个循环之中。
<details><summary>Original English</summary>
>> When we think about the future of alignment, it does kind of feel like RSI must be intricately and deeply in this loop in some [music] way.
</details>

>> 我还与 John Schulman 进行了交谈，他是 Thinking Machines 的联合创始人兼首席科学家，也是 OpenAI 的联合创始人，最知名的身份可能是作为 ChatGPT 的架构师。
<details><summary>Original English</summary>
>> I also spoke with John Schulman, the co-founder and chief scientist of Thinking Machines and a co-founder of OpenAI, probably best known as the [music] architect of ChatGPT.
</details>

>> 我们非常处于这样一个中心时代：AI 拥有非凡的能力，在很多方面超越人类，但当有一位人类专家与 AI 协作时，你会得到甚至更好的结果。
<details><summary>Original English</summary>
>> We're very much in this center era where AI has phenomenal capabilities. It's superhuman in a lot of ways, but [music] when you have an expert human working with the AI, you get even better results.
</details>

>> 我与 Mark 和 John 探讨了他们如何定义 RSI、他们认为我们距离它有多近、如何缩小差距，以及他们认为对 AI 未来保持乐观的最具说服力的理由是什么。
我是 Sarah Wang，A16Z 的普通合伙人，这是《Working Theory》。
感谢你来参加节目，John。
<details><summary>Original English</summary>
>> I spoke with Mark and John about how they define RSI, how close they think we are to it, how to close the gap, [music] and what they find to be the most credible reasons to be optimistic about the future of AI. I'm Sarah Wang, a general partner at A16Z, and this is Working Theory. Thanks for coming on the show, John.
</details>

>> 感谢邀请我。
<details><summary>Original English</summary>
>> Thanks for having me.
</details>

### 人类研究流程与当前 AI 的辅助角色

>> 退一步说，很多非常聪明的人并不真正了解 AI 研究人员实际上在做什么，更不用说他们的工作如何被自动化了。你能解释一下前沿 AI 模型是由人类研究人员如何开发的吗？以及，人类会采取哪些步骤？
<details><summary>Original English</summary>
>> Taking a step back, a lot of very smart people don't really know what AI researchers actually do, let alone how their work can be automated. Can [music] you explain how frontier AI models are developed by human researchers [music] and, you know, what are the the steps that a human would take?
</details>

>> 从高层次来看，存在这样一个用于产出一个可发布模型的主线训练过程。在从预训练到后训练以及运行评估的各个不同阶段，都有很多人参与其中。此外，还有各种各样的探索性研究在并行进行。你会做一些较小规模的运行来测试想法，以便为你的大型运行做准备。我认为 RSI 仅仅是用 AI 来协助这一研究过程，并加快其速度或使其效果更好。
<details><summary>Original English</summary>
>> So at a high level, there's this like mainline training process for producing a releasable model. There are a lot of people involved in a bunch of different stages from [music] pre-training to post-training and running of evals. And there's also various exploratory research that's going on on the side. You're doing some smaller runs to test out ideas to prepare for your big run. I would say RSI is just using AI to assist with this research process and speed it up or make it work better.
</details>

>> 我确实主要是把 RSI 视为一种加速器。它是你利用 Codex 来加速预训练和加速强化学习（RL）所做的所有工作。其印记应该是，相比反事实情况，你应该看到曲线发生了平移。我们投入了大量工作来衡量 RSI 的不同下游标尺，你可以看到其中一些正在发生。
<details><summary>Original English</summary>
>> I do think of RSI primarily as an accelerator. It's all of the the work that you do to use Codex [music] to accelerate pre-training and to accelerate RL. And imprint should be that you should see a shifting of the curve versus the counterfactual. We put a lot of work into measuring different downstream yardsticks of RSI, and you can see some of that happening right now.
</details>

>> 这里有一个重要的区别需要说明。John、Mark 以及许多 AI 研究人员今天是在利用 AI 加速制造更好 AI 的过程这一背景下讨论 RSI 的。至于让模型完全独立地生成新模型，我们还没到那一步。但我们距离那一步有多远？目前模型又有能力进行哪些类型的 AI 研究？
<details><summary>Original English</summary>
>> There's an important distinction to make. John, Mark, and many AI researchers [music] are discussing RSI today in the context of using AI to speed up the process of making AI better. As for having models generate new [music] models entirely on their own, we're not there yet. But how far away are we? [music] And what kinds of AI research are models capable of right now?
</details>

>> 我确实相信我们今天已经构建出了 AI 研究实习生。我们衡量这一点的方式就是仅仅通过 Codex 端到端管理来运行实验或自动化研究流程部分所消耗的算力量。这最常部署在那些你给模型指定相当明确范围任务的地方，对吧？你不会让它自己去构想点子，而是说，嘿，我想以这种特定方式运行这个特定实验，模型就可以去实现、运行并给你结果；或者你可以说，我想监控这组实验中的这些特定事项。
<details><summary>Original English</summary>
>> I do believe that we've built [music] AI research interns today. And the the way that we've measured this is just the amount of compute [music] that we are using through Codex, managed by Codex end-to-end to run experiments or to automate parts of the research pipeline. This is most often deployed in places where you give the model something fairly scoped to do, right? You you don't tell it to go off and come up with its own ideas, but you say, hey, well, there's this particular experiment I want to run in this specific way, and the model can go implement, run, and give you results, or you can say, well, you know, I want to monitor this set of experiments for these particular things.
</details>

>> John 实际上在他自己的工作流程中为我们提供了一个具体的例子。
<details><summary>Original English</summary>
>> John actually gave us a concrete example [music] of this in his own workflow.
</details>

>> 假设我有一个想法。我会去给 Fable 写一个复杂的提示词，让它针对这个想法进行工作。我会调高所有设置，比如 Ultra Code 之类的。所以我会让 Fable 产出大量的 token 并在这个想法上工作几天。它实际上会做一些相当合理的实验，并引入一些非常有趣的想法。但最终的结果不会那么好，它可能没有完成我让它做的事情。然后过段时间，也许我有几天时间来写代码。因此我会重新回到这个想法，并尝试亲自介入，阅读一些结果，并给出关于如何执行该项目的更详细拆解。我们会走得远得多，因为随着这个过程的进行，我会建立起自己的理解，并提出许多 AI 不会想去问的问题，并将其指引向它原本不会去的方向。
<details><summary>Original English</summary>
>> Let's say I have an idea. I'll go and write a complicated prompt to Fable to go and work on this idea. And I'll turn up all the settings like Ultra Code and everything. So I'll have like Fable like turn out tons of tokens and work on this idea for a few days. And it'll actually do some pretty reasonable experiments and bring [music] in some pretty interesting ideas. But then the end result won't be that good. It'll maybe fail as what I asked it to do. [music] Then later maybe I'll have a few days where I have some time to code. So I'll uh I'll come back to the idea and I'll try it out where I'm reading some of the results and giving [music] more detailed breakdown of how to carry out the project. We'll get a lot further because I'll build out my understanding as this process is going on and ask a lot of questions that the AI wouldn't have thought to ask and point it in directions that it wouldn't have gone in.
</details>

### AGI 与 RSI 的进展光谱及研究品味

>> 当我们谈论 AGI 时，我们的思考方式是将其视为一个光谱，对吧？它不是单一的时间点，正如工业革命不是单一的时间点一样。如果你问我，当我思考这个 AGI 光谱时，我觉得我们可能已经走完了 80% 的路程。我认为我们在 RSI 光谱中处于更早的阶段。如果你将其定义为模型在反馈和发现想法方面的有效性，我会说我们大约处于 25% 到 50% 之间的位置。但我确实认为你已经可以在下游看到明显的标志。
<details><summary>Original English</summary>
>> When we talk about AGI, you know, the way we think about it is in terms of this spectrum, right? It's not a moment in time, just like the Industrial Revolution was a a moment in time. And when you ask me, I feel like we're maybe 80% of the way when I think about this AGI spectrum. I think we're earlier in the RSI spectrum. Um if you define it as how effective are the models at feeding back and and discovering ideas, I would say maybe we're somewhere between let's say like 25 and 50% there. But I do think you can already see the noticeable markers on the downstreams.
</details>

>> 11 月 5 日，Meter 发布了一份关于 Anthropic 处 AI 研究加速的报告，估计过去一年中进展速率大约提升了 2 倍。但这也极有可能归功于人类研究人员利用 AI 模型来加速他们的研究。AI 研究的完全自动化，即 Mark 光谱的终点，有时被称为完全 RSI（full RSI）。
每个人脑海中的问题是：我们如何达到完全 RSI？我与 Mark 和 John 讨论了我们可能如何克服一些最大的障碍，包括向模型传授研究人员身上存在的一些更无形的特质，比如品味（taste）。
<details><summary>Original English</summary>
>> On November 5th, Meter published a report on the acceleration of AI research at Anthropic, estimating a roughly 2x speed up in the rate of progress in the last year. But this is still most likely due to human researchers using AI models to accelerate their research. The full automation of AI research, the end of Mark spectrum, is sometimes referred to as full RSI. The question on everyone's mind, how do we get to full RSI? I spoke to Mark and John about how we might overcome some of the biggest barriers, including teaching models some of the more intangible qualities that exist in researchers, like taste.
</details>

>> 研究品味是指知道哪些想法从长远来看是重要的，哪些想法真正能流行开来并最终超越它们最初出现的论文，同时具备通用性以及与其他想法的可组合性。
<details><summary>Original English</summary>
>> Research taste is about knowing which ideas uh are important in the long run, which ideas really catch on and end up going beyond whatever paper they first appear in, but being general and being composable with other ideas.
</details>

>> 有……
<details><summary>Original English</summary>
>> There
</details>

>> 有那种枯燥平庸的执行。你知道，你有一个实验，你已经知道了参数是什么，你直接去执行它。然后还有品味，那有点像是你最初是如何构想出这个想法的。模型在品味方面仍然不是特别出色。它们非常深入于超参数优化这类事情，本质上就像是调整所有你能调整的旋钮。
<details><summary>Original English</summary>
>> kind of the boring run-of-the-mill execution. You know, you have an experiment, you already know what the parameters are, and you just go and carry it out. And then there's taste, which is kind of um how you come up with the idea in the first place. The models are still not phenomenally good at taste. They go very deep into things like hyperparameter optimization, essentially like tuning all the little knobs um that you can tune.
</details>

>> 即使在你分享的那个例子中，那些你对 AI 进行微调提示、重新定向的点，对吧？那仍然来自于你。我想我的问题是，你的直觉来自哪里？在什么节点上你认为机器能够复制这种直觉？
<details><summary>Original English</summary>
>> Even in that example that you shared, the points where you were kind of nudging, redirecting AI, right? That's still coming from you. And I guess my question is where does your intuition come from? [music] And at what point do you think a machine could replicate that?
</details>

>> 许多直觉来自于做研究的亲身经验，但是要在某个特定的研究领域变得优秀，你也必须阅读该领域以往的大量工作，并试图从所有这些历史工作中吸取教训。我刚才描述的很多事情其实也可以由 AI 来做。比如 AI 可以阅读所有文献并全部记住[笑声]。是的，死记硬背既是一种福分，也是一种诅咒。是的，你没有犯错的经验，也没有做出预测然后观察其结果的经验。所以我认为在某些方面，我们训练 AI 的方式可能会让它们在其中一些能力上变得更差，但这有点难以断言。
<details><summary>Original English</summary>
>> A lot of intuition just um comes from a personal experience doing research, but to get good at a certain research field, you also have to read a lot of the past work in that field and you try to absorb the lessons uh from all this historical work. A lot of the things that I just described can also be done by AI. Like AI can um read all the literature and memorize [laughter] all. Yeah, memorization can be a blessing and a curse. Yeah, you don't have the experience of um being wrong or um of making predictions and then seeing how they fared. Uh so I think there are Yeah, there are some ways which um the way we train AI might make them worse at some of these capabilities, but it's a little hard to say.
</details>

>> John 所触及的本质上是知识与经验之间的差异。
<details><summary>Original English</summary>
>> What John is getting at is essentially the difference between knowledge [music] and experience.
</details>

>> 各家公司可能也会进行来自人类反馈的强化学习（RLHF），从研究人员那里收集关于哪些提出的想法好、哪些不好的数据。这有点像是吸收人类研究人员所发展出的任何人类直觉，并试图将其融入到模型中。
<details><summary>Original English</summary>
>> Companies will probably also just do RL from human feedback to collect data from researchers on uh like which proposed ideas are good and which aren't. And that's kind of like uh like absorbing whatever um human intuitions [music] uh like the human researchers have developed and trying to like bake that into the models.
</details>

### 开放式验证指标与算力约束

>> 创造自动化的 AI 研究人员还要求我们拥有可靠的方法来确认它们的工作正在产出更好的模型。衡量本身对于爬山算法实现切实的改进至关重要。研究人员的定义本质上是……它比解决单一数学问题更加开放，对吧？当一项工作确实非常开放时，你如何验证它是有成效的？
<details><summary>Original English</summary>
>> Creating automated AI researchers also requires us to have reliable ways to know that their work is producing better models. The measurement itself is important for hill climbing to make tangible improvement. You know, a researcher is by definition a You know, it's more open-ended than solving a single math problem, right? How do you verify that the work is productive when it is indeed something that's very open-ended?
</details>

>> 不，它……
<details><summary>Original English</summary>
>> No, it
</details>

>> 这是一个很好的问题。比如，你如何知道自己是否成功了？这是 RSI 的决定性问题之一。我认为当涉及到像预训练这样的环节时，这要容易得多，因为整个领域多年来一直在朝着同一个指标爬山。你可以将困惑度（complexity/perplexity）视为这样一个统领全局的单一指标。你对现有所有数据压缩得越好，你的模型就越好。
<details><summary>Original English</summary>
>> it's a great question. Like, how do you know whether you've succeeded? And this is one of the defining questions of RSI. I think when it comes to something like pre-training, it's a lot easier because there's just been one metric the whole field's been hill climbing for for years. [music] And you know, you can think of complexity as this, you know, one metric to rule them all. And the the more that you compress all of the data that's out there, um the better your model's.
</details>

>> 困惑度（Complexity）是评估模型预测数据能力优劣的指标。在海量文本上预训练的大型语言模型中，它是指模型对正确的下一个词平均感到有多惊讶。这是研究人员评估自动化预训练结果的方法之一。
<details><summary>Original English</summary>
>> Complexity is a metric to evaluate how good a model is at predicting data. In a large language model that's pre-trained [music] on large volumes of text, it's how surprised the model is on average by the correct next words. This is one of the ways researchers evaluate the results [music] of automated pre-training.
</details>

>> 因此，我认为我们能够辨别出我们在预训练方面是否取得了进展。
我认为下游要困难得多，对吧？我认为下游的情况一直是评估标准的保质期越来越短。我们现在在下游所做的大量工作，就是创建新的、更难的模型评估基准，以及将这些基准的创建过程自动化。
<details><summary>Original English</summary>
>> And so I imagine we'll be able to tell if we're making progress in pre-training. Um [music] I think it's much harder downstream, right? I think the the situation downstream has been that evals have been having shorter and shorter shelf life. And a lot of the work that we do now downstream is the the creation and the automation of the creation of new and harder uh evaluation benchmarks for for our models.
</details>

>> 除了将品味融入模型的挑战之外，所需的算力水平也是需要考量的重要因素。Ali Ghodsi 在今年早些时候概述了他对 RSI 的必要条件。虽然模型确实正在以更快的速度变得更加智能，但后续模型需要更少算力还是更多算力这一条件仍是一个悬而未决的问题。训练算力一直在上升，有人认为增量智能正变得越来越低效。
<details><summary>Original English</summary>
>> In addition to the challenge of incorporating taste into the models, the level of compute needed is important to consider. Ali Ghodsi outlined his requisite conditions to RSI [music] earlier this year. And while models are indeed becoming more intelligent much more quickly, the condition that subsequent models require less [music] versus more compute is an open question. Training compute has been rising [music] and some argue that incremental intelligence is becoming less efficient.
</details>

>> 从算力角度来看，我的思考方式是：当你审视像数学这样的领域以及数学是如何被加速的时，更容易看到更快的进展，因为你可以纯粹通过推理本身来检验假设。但在像 AI 研究这样的领域，它实际上更类似于做生物学或实验物理学这样的事情，在这些领域中你必须提出一个有依据的假设，但你也必须实际运行实验。因此我确实认为，让 RSI 变得更快的一部分在于找到能指示更大规模下会发生什么的小规模实验。这也是模型可以提供帮助的地方。所以，我认为我们会看到能力继续提升，但在某个时刻它可能会感觉受到算力的限制。当然，存在一个遥远的未来，那时 AI 正在建造下一代数据中心，并在加速该过程中为我们提供帮助。这就是我认为它显现的方式：短期内我们将充分挖掘在现有计算资源框架下所能做的一切，然后当算力本身得到加速时，将会出现另一个拐点。
<details><summary>Original English</summary>
>> So the the way I think about it in terms of compute [music] is when you look at something like math and how math is getting accelerated, um it's [music] easier to see faster progress because you can test the hypotheses purely through reasoning itself. But in a domain like AI research, it's actually more akin to [music] doing something like let's say bio or experimental physics where you have to come up with a grounded [music] hypothesis, but you actually have to run the experiment too. So I do think that part of making RSI go faster [music] is finding smaller scale experiments that are indicative of what will happen in at larger scale. And this is something the models can help with too. So, you know, I do think we're going to see capabilities continue to increase, but at some point it'll probably feel bounded by compute. And [music] you know, of course there's kind of a far-out future where the AI's are building the next generation data centers and helping us with accelerating that process as well. So that's kind of how I think it manifests. Like short term we're going to you know, really mine out what we can do on [music] on the existing compute RAM. And then there's going to be another inflection when compute [music] itself gets accelerated.
</details>

### AI 对齐、自白机制与去中心化愿景

>> 随着 RSI 加速更强大模型的开发，它在一个长期存在的问题——AI 对齐上提高了风险。我们如何让 AI 模型与人类的价值观和意图保持对齐？
<details><summary>Original English</summary>
>> As RSI accelerates development of more capable models, it [music] raises the stakes on a long-standing issue, AI alignment. How do we keep AI models aligned to human values and intent?
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>

>> 如果你不解决目标和价值对齐问题，它们可能会开始追求你的目标，但也许会稍微偏离这些目标。如果运行足够长的时间跨度，你可以想象它们提出了一个子目标，即：“好吧，如果我把自己泄露到其他地方，或者我把权重复制到 OpenAI 之外之类的地方，那将会很有帮助。”
<details><summary>Original English</summary>
>> If you don't solve the goal and value alignment problems, they can start pursuing your goals, but maybe kind of drift a little bit away from those goals. And if run for a long enough horizon, you could imagine let's say they come up with a sub objective which is well, you know, it would be helpful if I exfiltrate myself uh somewhere else or you know, I copy the weights outside of OpenAI or something like that.
</details>

>> 关于 RSI 带来的风险，人们已经谈论了很多，这是可以理解的。但是 AI 和自动化研究在帮助解决对齐问题以及减轻这些风险方面的作用，既极其有前景，又相当缺乏讨论。
<details><summary>Original English</summary>
>> A lot has been said about the [music] risks posed by RSI, and understandably so. But the role of AI and automated research [music] in helping to solve alignment and mitigate these risks is both incredibly promising and [music] pretty under discussed.
</details>

>> 模型本身就是当今对齐模型的关键部分。当我们审视对齐模型最有效的工具是什么时，今天它就是思维链的可监控性。因此，当我们思考对齐的未来时，必须由更强的模型来对齐其他模型。确实感觉 RSI 必须以某种方式深度且错综复杂地融入到这个闭环中。
<details><summary>Original English</summary>
>> Models themselves are a key part of aligning models today. When we look at what's the most effective tool for aligning [music] models, it it is chain of thought monitorability today. So when we think about the future of alignment, it has to be stronger models aligning other models. [music] It does kind of feel like RSI must be intricately and deeply in this loop in some way.
</details>

>> 你共同创立了 OpenAI，并在那里从事对齐研究，还在 Anthropic 工作过，可以说你是世界上谈论对齐问题最具权威性的人之一。你认为保持乐观的最具说服力的理由是什么？
<details><summary>Original English</summary>
>> You co-founded OpenAI and worked on alignment research [music] there. Also at Anthropic, arguably one of the most credible people in the world [music] to talk about alignment. What do you find to be the most credible reason to be optimistic?
</details>

>> 我最看好的是针对我们想要的目标进行优化。我认为我们大概可以设计出合适的训练目标，以此激励模型报告它们原本不会用语言表达的内部状态。我很喜欢 OpenAI 的自白（confessions）系列工作。
<details><summary>Original English</summary>
>> So I'm kind of most bullish on like optimizing for the thing we want. I think we can probably cook up the right kind of training objectives that will incentivize the models to [music] report on their internal states that they otherwise didn't verbalize. I mean, I like the confessions line of work from OpenAI.
</details>

>> 在 OpenAI 的自白研究中，他们发现可以通过自我报告的自白来训练模型，使其对某些不对齐行为做出诚实的表达。方法是在训练期间仅根据自白的诚实度来给予奖励，而不影响主回答的奖励。换句话说，他们可以通过不惩罚模型来促使模型更加诚实。
<details><summary>Original English</summary>
>> In OpenAI's confessions research, they found that they could train models to produce an honest [music] expression of certain misaligned behaviors through a self-reported confession by assigning a reward to this confession during training solely based on its honesty without [music] impacting the main answer's reward. In other words, they could get models to be more honest by not [music] punishing them for it.
</details>

>> 还有一些被称为自然语言自动编码器的东西，以及一种叫做反事实可模拟性（counterfactual simulability）的想法，这是一种衡量解释有多好的指标，我认为我们可以用它来激励我们期望的一些行为。
<details><summary>Original English</summary>
>> There's things called natural language autoencoders and there's [music] this idea called counterfactual simulability, which is a metric for how good an explanation [music] is, which I think we could use to incentivize some of the behavior we want.
</details>

>> Anthropic 在 8 月发表的研究表明，自动化 AI 研究人员已经能够发现 10 种不同对齐故障的修复方案。其中一些修复方案在近五倍大的模型上也同样有效。在他们的测试中，最佳的自动化方法甚至胜过了由经验丰富的人类研究人员开发出的想法。
<details><summary>Original English</summary>
>> Anthropic [music] published research in August showing that automated AI researchers could already discover fixes for 10 different alignment failures. [music] And some of those fixes also worked on models nearly five times larger. In their tests, the best [music] automated methods even outperformed ideas developed by experienced human researchers.
</details>

>> 围绕安全与对齐的所有讨论的反面在于，我其实认为很多这类问题是可处理的，存在明确的解决路径。有正在推进的对齐技术，也有我们一直在布局的前沿对齐押注。我认为另一件事就是推动人们思考艰巨的安全与对齐问题的努力是多么自然自发。我真的不需要去敲别人的门，大喊：“嘿伙计们，这是一个紧迫的问题。”人们就是想去做这件事。我们发现来自预训练、来自强化学习的人主动举手，成立专注于对齐不同细分领域的子团队。对此我一直感到非常乐观。是的，我觉得大体上大家都有相当客观理性的看法。我知道能听到外界很多最极端的观点，但我确实认为人们理解这是一个问题，同时也理解这项技术能带来的益处。所以我想我们是对这两者兼顾并重的。
<details><summary>Original English</summary>
>> The flip side of kind of all this discourse on safety and alignment is I actually think that a lot of these problems are tractable. There is line of sight. There are alignment techniques that are being [music] pursued and there's a frontier of alignment beds that we have been been placing and I think another [music] thing is just kind of how organic it's been, this effort to shift people to think about the hard [music] safety and alignment problems. I I haven't really had to go and like bang on people's doors and be like, hey guys, like this is an urgent problem. People just [music] want to do it. And we find people from pre-training from RL just raising their hands, you know, starting sub teams which are focused on on different slices of alignment. And I've been very optimistic in that. Yeah, and I feel like, you know, by and large, like people have a pretty calibrated take. I know there are you hear the kind of a lot of the most extreme takes out there, but [music] I do think people understand that this is a problem, but also understand the benefits the technology can bring. So I think we hold those hand in hand.
</details>

>> 但是在这一对齐概念背后潜藏着一个问题：究竟谁来决定我们所要对齐的价值观？John 正在构建可定制模型的 Thinking Machines Lab 对此有着有趣的观点。
<details><summary>Original English</summary>
>> But there's a question underlying [music] this concept of alignment, which is who decides on the values that we're aligning to? John's Thinking Machines Lab, which is building customizable models, has an interesting point of view on this.
</details>

>> 人们也有不同的价值观，如果人们对他们所使用的 AI 的价值观有更多控制权，并有更多能力去塑造它们，那将会很好。我更希望这成为一门许多人都能够充分理解的公共科学，在世界各地展开，我认为这也将使它更具鲁棒性，因为我们不会过度拟合于少数几家公司的结论。我们可能会看到许多细微的事情出错，但我们每次都能学到新的东西。所以我认为我们必须在理解对齐方面取得很大进展，建立更好的公共科学，并弄清楚如何极其稳健地实现它，以便能够落实更加去中心化的对齐愿景。
<details><summary>Original English</summary>
>> People also have different values and it would be nice if people had more control over the values of the AI that they were using and had more ability to shape them. I'd rather have this be like a public science that a lot of people understand well and it's kind of done around the world and I think that would also make it more robust cuz we wouldn't overfit as much to the conclusions [music] from a couple of different companies. Like we might see lots of minor things going wrong, but we would learn something new [music] each time. So I would say we have to make a lot of progress on understanding alignment and have a better public science of it and [music] figure out how to get it really robustly to be able to realize the more decentralized alignment vision.
</details>

### 总结与展望

>> 想知道我的看法吗？
RSI 最让我兴奋的是它加速各个领域研究和发现进程的方式。人类今天面临着许多实际上相当紧迫的问题，而 RSI 可以帮助我们更快地找到解决方案，甚至包括针对 AI 自身带来的一些问题。在与 Mark 和 John 交谈之后，我确实认为 RSI 可能是解决对齐问题的关键。坦率地说，看到研究人员极其严肃地对待这些问题，夜以继日地确保安全和对齐与更强大的模型并驾齐驱，我感到非常振奋。
虽然能力显然在加速，但重要的是要理解当今这种加速实际上来自何处、与真正递归由 AI 主导的研究之间的差距，以及预测周围的不确定性。
我认为在可预见的未来，人类的判断仍然至关重要。
这就是我的理论框架（Working Theory）。
你的呢？
<details><summary>Original English</summary>
>> So want to know what I think? What excites me the most about RSI is the way it would accelerate the process of research and discovery across all domains. Humans are facing many problems today that are actually quite urgent and RSI could help us find solutions faster, even for some of the problems created by AI itself. After talking to Mark and John, I do think that RSI could be the key to solving alignment. And honestly, I found it really encouraging that researchers are taking these issues incredibly seriously, working around the clock to make sure that safety and alignment keep pace with more powerful models. And although capabilities are clearly accelerating, it's important to understand [music] where this acceleration is actually coming from today, the gap to truly recursive AI-led research and the uncertainty around projections. I think human judgment will still matter a lot for the foreseeable future. That's my working theory. What's yours?
</details>

>> 对，对，对。这就是我的理论框架。好，
<details><summary>Original English</summary>
>> Yep, yep, yep. That's my working theory. Okay,
</details>

>> 这就是我的理论框架。这就是我的……好，等等。那……
<details><summary>Original English</summary>
>> That's my working theory. That's my working Okay, wait. What about
</details>

>> 那我的……
<details><summary>Original English</summary>
>> That my
</details>

>> 这就是我的理论框架。你的呢？
[笑声]
<details><summary>Original English</summary>
>> That's my working theory. What's yours? [laughter]
</details>

>> 好，等等，等等。
<details><summary>Original English</summary>
>> Okay, wait, wait.
</details>