---
author: AI Engineer
date: '2026-08-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=QHBjufYK8TA
speaker: AI Engineer
tags:
  - model-routing
  - multi-agent-collaboration
  - context-compaction
  - kv-caching
  - hybrid-inference
title: 模型路由的现状：英伟达、Cognition 与 OpenRouter 的前沿对话
summary: 本篇访谈记录汇集了来自英伟达、Cognition（Devin 开发商）和 OpenRouter 的行业领袖，深入探讨了在多模型世界中模型路由、智能分发、上下文压缩、KV 缓存优化以及端到端多智能体协作的核心挑战与前沿技术路径。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - NVIDIA
  - Cognition
  - OpenRouter
products_models:
  - Devin
  - GPT-4o
  - Pareto
media_books: []
status: evergreen
---
### 多模型世界的兴起与模型路由的兴起

**主持人**: 大家好，今天非常高兴能把几位行业领袖聚集在一起，讨论我们在尝试在本地运行更多模型时所面临的一些挑战。如果你参加了第一场圆桌论坛，应该记得我们讨论过的一个核心议题就是**模型路由（Model Routing）**。我们坚信，未来的世界将是一个**多模型（Multi-model）**的世界。我想许多与会嘉宾也都表达了类似的观点。任何在生产环境中部署人工智能、尤其是进行本地部署的人，都会看到这种多模型的趋势。这也是为什么我们在 **NVIDIA** 推出了 **NeMo Triton** 模型。我们开源了从数据集到模型权重的所有内容，并提供了定制化配方，因为我们知道，模型定制化将是未来的大趋势。因此，今天的这场圆桌论坛非常令人期待，因为我们将专门探讨模型路由。也就是说，在挑选要使用的模型时，我们所需的工具链究竟是怎样的？首先，请各位嘉宾介绍一下自己吧。

<details>
<summary>Original English</summary>

**Host**: have been really exciting. We've tried to get a bunch of the industry leaders together to talk about some of the problems that are that we're facing as we try to run more on local. If you guys were here for the first panel, one of the things that we talked about was model routing. We firmly believe that we're in a multi-model world. I think you heard this from many of the panelists. Anyone who is deploying AI in production and who is doing so locally is seeing that multi-model world. That's why we released these NeMo Triton models at NVIDIA. Everything is released from the data sets to the weights with recipes so that you can customize them. We do that because we know that people customizing models is going to be huge. And so, this panel is really exciting cuz we're going to talk specifically about model routing. So, as you are picking which model to use, how does that how essentially how does that tooling itself look? Um, do you guys want to introduce yourselves?

</details>

**Walden**: 好的，没问题。我是 **Walden**，**Cognition** 的联合创始人。我们构建了全球首个 AI 软件工程师 **Devin**。除了不断迭代我们的产品，我们还花了大量时间与客户合作，研究他们应该如何部署这些模型和智能体。如今客户经常问我们的一个核心问题是：我该如何衡量我们模型的投资回报率（ROI）？我该如何知道哪些具体的任务应该让工程师使用最昂贵的模型，而哪些任务可以让更具成本效益的模型来处理？正是因为这些实际的需求，我们最近也在深入思考多模型环境下的模型路由机制。

<details>
<summary>Original English</summary>

**Walden**: Yeah, sure. Um, I'm Walden. I'm the co-founder of Cognition. We build Devin, AI software engineer. Uh, in addition to the product, we spend a lot of time partnering with our customers to figure out how they should deploy these models uh and these agents. And one of the things they're constantly asking us nowadays is basically how do I know the ROI of our models and how do I know which tasks I can actually let our engineers spend the most expensive models on versus, you know, letting them use a more cost-efficient model. And so, that's why we're we're also thinking a lot more about multi-model model routing nowadays.

</details>

**主持人**: 确实如此。

<details>
<summary>Original English</summary>

**Host**: Totally.

</details>

**Carter**: 大家好，我是 **Carter**。你们刚才可能已经听过我的发言了，但如果你刚来，我自我介绍一下：我是 **NVIDIA** 的开发者技术工程师。我大部分时间都在思考如何将 AI 智能带入尽可能多的开发者手中。对于许多开发者来说，随着我们使用的 AI 智能度越来越高，前沿模型也变得越来越昂贵，如何不打破预算成了头等大事。有时候，尽管你很想在所有地方都用最好的工具，但成本却高得令人望而却步。因此，我们最近的核心关注点是：我们如何在确保获得期望输出的前提下，让独立开发者、初创公司以及小型企业，能够充分利用这些强大工具而又不至于破产？

<details>
<summary>Original English</summary>

**Carter**: Yeah. I'm Carter. You guys heard from me a little bit earlier, but if you weren't here, I'm a developer tech engineer at NVIDIA. And uh ultimately, I spend a lot of time thinking about how to get intelligence into as many developers' hands as possible. And uh something that is continually becoming a not an issue, but something that is top of mind for a lot of developers is uh as you use more intelligence and the frontier models get more expensive, uh it becomes somewhat cost prohibitive to to use the best uh tools, what feels like the best tools, as much as you would like to use them. And so, this has become a recent uh you know, focus is, how can we, you know, still get the same desired outputs, but actually uh both as an individual developer, but also imagine startups and small companies, how can you leverage this incredible tool without totally breaking the bank?

</details>

**Donne**: 大家好，我是 **Donne**。我此前主要致力于模型评估工作，包括准确性、效率以及对模型成本结构的深度理解。我尝试将这些研究成果付诸实践，并协助构建路由器。所以我的工作基本上就是从底层亲密地理解模型的行为特点，然后利用这些发现来改进模型，并设计一个能让不同模型彼此协同工作的系统。

<details>
<summary>Original English</summary>

**Donne**: Uh I'm Donne. I have worked on model evaluations uh both in terms of its accuracies and efficiency and cost understanding of the model. Uh and then I try and understand those implement those learnings and uh help build a router. So, it's basically my job is to understand the behavior of of the model on an intimate level and then use those learnings to both improve the model and try and design a system of model that can work together with each other.

</details>

**主持人**: 确实是这样。我非常喜欢 NVIDIA 在这方面开展的诸多研究，我们也在见证着这个领域的蓬勃发展。令人兴奋的是，模型路由本身其实还非常新颖。正如我们在第一场圆桌会议上提到的，目前还没有一个非常明确、标准的解决方案。这也意味着初创企业和整个生态系统中的公司有巨大的空间来填补这一空白，因为我们仍在摸索最有效的模式。我想问问 Walden：Cognition 刚刚发布了 **Fusion**，这是你们开发的模型路由器。在发布时的官方博客中，你们提到 Fusion 实际上实现了优于单个前沿模型的性能。这听起来非常令人惊讶，因为通常人们认为，在边缘设备或计算受限的环境中运行更小的本地模型时，能获得“足够接近”或“相当不错”的性能就已经是极限了。但你们却实现了超越。你们能具体解释一下是如何做到的吗？

<details>
<summary>Original English</summary>

**Host**: Totally. Um yeah, I love a lot of the research that you're doing at Nvidia as we kind of see the space through. I think what's really interesting is model routing itself is pretty new still. And so, what you'll notice is there isn't a very clear solution here. That was something that came up on the first panel is that there is a lot of space for startups and for companies in the ecosystem to fill in a solution here cuz we're still figuring out how to best do these patterns. And I think, Walden, I want to kind of ask you. So, um Cognition just released Fusion, your guys's model router. And when you guys released it, you in your blog said that you're actually getting better performance than Fable, um than these frontier models. And I feel like that was a very surprising statement to hear because we were thinking that you're getting as good or close enough usually when we're running on edge, when we're running local in these compute strained, smaller footprint models. But you guys are getting better. Can you explain how?

</details>

### 协同委派与模型能力的互补性

**Walden**: 好的，没问题。在这里我想先澄清一个概念：我们并不是说我们在基础能力上全面超越了像 **Fable** 这样的顶级前沿模型，就如同前沿模型拉开与其他普通模型的差距那样。实际上，这里存在一个非常反直觉的动态：越聪明的模型，其实越擅长委派工作。我们在构建模型路由器时的一个核心哲学是：我们绝对不希望把用户路由到一个较弱的模型后，导致智能体卡在某个它根本无法处理的任务上；结果用户不得不手动切换回聪明的模型，白白承受昂贵的成本开销。我们认为目前市面上现存的很多路由系统，实际上和人们一年前使用的做法别无二致。我们希望推出一种全新的框架，让用户在依然保留前沿模型提供安全保障的同时，享受巨大的成本优势。具体来说，我们将 Fable 级别智能的整体成本降低了 40%。我们实现这一目标的方式是：让前沿大模型继续负责顶层的规划和复杂的决策制定，而将具体的执行和落地工作委派给一个更专精的“执行模型（Implementation Model）”。这个执行模型可以是一个开源模型，也可以是成本极低的 Mini 系列模型。

最有趣的一点在于，即便执行模型的运行成本低得多，但因为你将具体工作委派了出去，你就可以让它以比以往深得多的强度去执行任务。例如，你可以瞬间衍生出三个子智能体去并行探索代码库。这种并行的深度探索，往往比你只让单个前沿大模型自己去阅读代码库要全面得多。这就带来了一个非常漂亮的平衡：它不仅在成本上更高效，而且在解决问题的完整性上表现得更加优异。

<details>
<summary>Original English</summary>

**Walden**: Yeah, absolutely. Um so, I also want to be be clear about something here is like, you know, we're not saying that that we gap above Fable level performance in in the same way that maybe Fable level performance gaps above other models. I think actually there's this really unintuitive dynamic where smarter models actually get better and better at delegating work. And so one of the philosophies we had with building a model router is we don't want to route people to a dumber model and then suddenly you're stuck with a model that doesn't know how to do your task. Next thing you know you're you're switching yourself back to smarter model anyways and now taking that expensive cost. And in general we think a lot of the existing model routing systems out there are probably the same ones people have been using like a year ago. And so we really wanted to put out a new framework that actually lets people still feel like and and still have a frontier model in their system while getting all these like cost benefits. So yeah we we're reducing the cost of Fable level intelligence by 40%. The way we do that is we allow Fable to still do like the planning and the the hard decision making but delegate a lot of the work to an implementation model. And the implementation model can be you know one of these open source models be it a cheaper mini model. Um the unintuitive thing is even though it's cheaper because you're delegating the work to another model you can let that model go at the task with much more depth and intensity than you might otherwise. Like you can spin off like you know three sub agents to go and like explore the code base and maybe that's actually more comprehensive than if you had just let Fable explore the code base itself. So you're actually getting this like nice trade-off where it's both more cost efficient and it's also more comprehensive overall.

</details>

**主持人**: 这非常有趣。也就是说，通过启用多个较小的模型去执行任务（比如去翻阅代码库），你获得的探索效果可能远胜于仅仅依赖一个在上下文或思考路径上受限的单一模型。

<details>
<summary>Original English</summary>

**Host**: Interesting. I see. So you're saying by using a bunch of smaller models you're essentially like for one example scouring the code base you can you you can explore it potentially better than if you were to just have one model I don't know figure out with what it's limited with its limited context with whatever path it's on.

</details>

**Walden**: 没错，完全是这样。

<details>
<summary>Original English</summary>

**Walden**: Yeah, totally.

</details>

**主持人**: 而且，如果我们从代币预算的角度来看，如果前沿大模型的单 Token 成本非常高，而小模型要便宜几个数量级，你就可以在相同的预算范围内，让小模型生成并消耗远多于大模型的 Token，从而进行更深层次的计算。

<details>
<summary>Original English</summary>

**Host**: But also if you think about the budget of if you were to say the frontier model costs this amount per token and the smaller model is this amount per per token and it's significantly cheaper then you can use a lot more tokens from the smaller model with still within the budget that it would have been from the Frontier model.

</details>

**Donne**: 我想补充一点，我强烈建议大家意识到，大多数模型都存在“参差不齐的能力（Jagged Capabilities）”。编程并不是一个单一的领域。在编程内部，比如在数据可视化领域，会涉及到 scikit-learn、matplotlib 等各类不同的库。这在很大程度上取决于每个模型在训练时所接触的数据语料库。这意味着，当你在处理任务 X（例如数据可视化）与任务 Y（例如机器学习模型构建）时，不同模型会表现出完全不同的优势。所以，仅仅因为模型 A 在某项编程基准测试中得分较高，并不代表它在所有细分任务中都绝对优于模型 B。因此，路由的核心任务其实是深入理解不同模型在各种子任务上的行为、强项与弱点，并因地制宜地调用它们。我们应该把模型看作是互补的，而不是寄希望于有一个“至尊模型”能统治一切。

<details>
<summary>Original English</summary>

**Donne**: I would also like to encourage everyone to think there are jagged capabilities in most models, right? So, coding is not one domain. Within, let's say data visualization, there'll be scikit-learn, there'll be matplotlib, there'll be something else. It largely comes down comes down to the training corpora that went into each of the models, so right? So, one model, while you're trying to do X type of work, let's say data visualization, and the other type is Y, that means let's say model building. Let's say you're trying to have a data science work stream, where you're trying to optimize for some kind of prediction, and then visualizing your results. Within that task, different models will have different strengths. So, not it's not necessary that model A if scores higher on a coding benchmark, is just plain better at every task that is. So, routing is a task of intimately intimately understanding of behavior of and strengths and weaknesses of different models, and then applying them thusly, right? I would I would encourage everyone to think, "Hey, models are strong at different things, rather than like there's one model to rule them all."

</details>

**主持人**: 我明白了。另外，我们插播一句，非常感谢 **Alex** 刚赶到并加入我们。

<details>
<summary>Original English</summary>

**Host**: I see. And by the way, real quick, thank you Alex for joining. Yeah.

</details>

**Alex**: 抱歉我迟到了。我是来自 **OpenRouter** 的 Alex，非常感谢你们邀请我。

<details>
<summary>Original English</summary>

**Alex**: Sorry I'm late. I might need yours in. Sorry I'm late. I'm Alex from OpenRouter. Um thanks for having me now.

</details>

**主持人**: 没关系，你刚从机场赶过来，时间刚刚好。我们刚才聊到，模型路由不仅是简单地将任务派发给一个小模型，更是如何让一个智能体集群协同完成任务。而在这之中，如何在不同的智能体之间有效地流转和路由任务，本身就变成了一个非常值得研究的独立课题。

<details>
<summary>Original English</summary>

**Host**: No. Oh, is that so? Yeah, of course. Thank you so much. You came right from the airport, so this is perfect. I think um tonight that's that's super interesting. So, um the way that you're thinking through through model routing, it's not even just uh delegating to necessarily a smaller model, but like and maybe this is kind of what you're saying is can you can you put essentially a swarm of agents to accomplish the same task, and suddenly routing the task between them is is much is a is a problem to solve in and of itself.

</details>

### 上下文管理与压缩的科学

**Donne**: 是的。我们拿科学探索或科研发现来作为一个简单的例子。通常这类任务极其困难，不是一步就能到位的。你需要让模型反复推演整个过程，这里面包含了无数的子领域。如果从模型的微调和训练后处理（Post-training）过程来看，它们是由不同的“教师模型”指导的，并在不同的细分子任务上进行了优化。一旦我们理解了每个模型在不同子任务上的失败模式，就可以在系统中利用这种“套利空间（Arbitrage）”进行精妙的协同。在 LM 路由器基准测试中，如果使用这些协同技术，甚至可以将准确率提高多达 10%。这很大程度上取决于你拥有的模型池以及手头的具体任务。我们应该多思考模型之间的互补性。

<details>
<summary>Original English</summary>

**Donne**: Yeah. So, if you look at like let's say let's take an easy example. Let's take a science or like scientific discovery as an example, right? Usually these are one-shot problems. It's incredibly hard. You have models think through this process, right? So, in that you have tons of sub-domains. Like tons and tons and tons. So, in that aspect, if you think about post-training like the post-training process of a model, they'd be tuned with different teachers. They'd be tuned on different sub-tasks. So, those those um those overlapping strengths will be readily apparent when you're trying to understand failures of each models on different different sub-tasks. Once you understand that, you can orchestrate your system to leverage that arbitrage essentially, and that essentially becomes free. So, I think this is on LM router bench. There was there are tons of benchmarks out there. But, if you use these techniques, you can get like up to 10% higher accuracy even, right? It depends on the model pool. Depends on the task at hand. But, I would encourage to think about the complementary nature of models.

</details>

**主持人**: 我想知道，正如你所描述的将任务拆分给小模型去处理，由于它们的 Token 成本极低，它们在执行过程中会产生极其庞大的 Token 数量。那么在路由设计中，你们是否会特意针对这一点进行优化，从而让它们可以更“健谈（Chattier）”地去试错？

<details>
<summary>Original English</summary>

**Host**: I see. Do you see so in kind of the way that you were describing the way that the task is broken up, do you see that the some of the smaller models because the token cost is cheaper, are they using more tokens? Like is it Are they Are you specifically routing so that they do or that they so that they are chattier?

</details>

**Walden**: 是的，它们确实会产生更多的 Token。我想顺着 Donne 刚才提到的观点深入聊聊。当人们看到在特定基准测试中小模型表现优于大模型时，很容易产生一个天真的想法：“那我们直接把这类任务路由给小模型不就行了？”

但我们在关于 Devin **Fusion** 的博客中特别强调过：这种**基于任务类型的静态路由极其脆弱**，尤其是当你处理高度**智能体化（Agentic）**的复杂任务时。以真实的软件开发为例，当你给智能体派发任务时，它首先需要去理解“这个代码库是如何运作的”；接着，它需要深入去“实现某些具体功能”；再然后，它需要去进行“集成测试并调试深层的 Bug”。随着时间的推移，任务的复杂度在动态改变，任务的类型也在不断转换。如果你在某个时刻把任务卡死在一个能力不足的模型上，整个流程就会崩溃。这也是为什么人们如此青睐前沿大模型的原因——因为它们具备通用智能，能在各种截然不同的领域之间自由切换。

因此，真正的挑战在于：我们如何让一个小模型意识到它已经“超出能力范围”了，并触发机制将其无缝移交给更聪明的模型？我们给出的解决方案是：你必须始终让一个处于统治地位的“前沿代理（Frontier Agent）”在幕后进行全程观察。即便它不直接参与干活，它也必须密切保持跟踪，以便在发现被委派的小智能体陷入困境时，及时把任务接管并分配给其他模型。这种让前沿智能始终在场的设计，极大地降低了复杂智能体系统的脆弱性。

<details>
<summary>Original English</summary>

**Walden**: Uh oh yeah, they absolutely do use more tokens. I I actually I want to kind of like riff on something that Donne was saying, which is like you know, a lot of times when you look at these different benchmarks, you'll see that the small models will perform better than like even the frontier models in certain cases. I think a lot of people they look at this and they immediately jump to, "Oh, how can we just route like, you know, the task where the small models do better just straight to the smaller models?" I I think that one of the things we really want to emphasize with our recent blog post and recent Devin Fusion was that this kind of like naive like initial routing to based on the task type is extremely fragile, especially the more agentic the task you you work on is. So, for example, like a real developer, you might ask your agent first, "Oh, how does this code base work?" And then you you go deeper and you're like, "Okay, actually, can you implement some features for me?" And then you go deeper and you're like, "Oh, can you like now go to like a live test of this feature and debug deep cases?" The complexity changes and the type of task changes over time, and you don't want to be left with some subpar model for the the task that you're now on. I think this is why people like frontier models so much is they're they're just like generally intelligent and they're capable of shifting between various different domains, even if you can eke out better performance in very specific tasks. Um, and and what So, the challenge is, how do you get a small model to know that it's out of its depth and you need to now like go switch to another model or go like, you know, go to a smart smarter model. And and our solution to this is you kind of just always have this like main frontier agent that's watching, even if it's not the one doing the work. It should at least be keeping tabs to figure out, "Okay, we like the the agent I delegated to now is like out of its depth. I need to kind of like move it to to something else." Um, and and overall, just the guarantee of always having frontier intelligence present, I think reduces the the fragility of of these systems quite a lot.

</details>

**主持人**: 当一个小智能体完成了部分工作，并决定：“我可能无法搞定接下来的部分了，我需要把它交还给主模型”时，它们之间的**上下文共享（Context Sharing）**是如何实现的？我们显然不希望把小智能体产生的所有零碎运行轨迹和历史记录原封不动地全部塞回给大模型。那如何在提供必要信息的同时，避免大模型被无关的冗余代币淹没？

<details>
<summary>Original English</summary>

**Host**: How does the sharing of context between one of those smaller agents who has basically completed up to some level of a task and decides, "Actually, I don't think I'm the right person for this. I need to hand it back to the foundational model." Um, of course, you don't want to have the entire trace of that smaller agent be passed back to the larger model. But so, how do you get that level of specificity while basically providing the information it needs, but not more?

</details>

**Walden**: 是的，这是一个非常关键的技术细节。如果你的多模型协作设计得不够好，很容易让运行成本变得更高。比如，如果一个小智能体读取了一个文件，接着另一个模型又去重复读取该文件，这就意味着你为相同的上下文支付了多次费用。

我们花了很多精力优化的一点是：在默认情况下，大部分底层的原始上下文（例如读取具体文件产生的数据）只会流向执行任务的小模型。而我们需要精细调优的是小模型将上下文“汇报”给大模型的能力。比如，它不需要发送具体文件的每一行内容，而只需要汇报它读取了哪些文件，以及它做出了什么高维度的思考和判断。这就是**上下文压缩（Context Compaction）**。在长程智能体（Long-running Agents）的设计中，上下文压缩本就是必须要解决的核心问题。我们把这一领域成熟的压缩与概括技术应用到了多模型路由中，从而实现了高效的信息交接。

<details>
<summary>Original English</summary>

**Walden**: Yeah, absolutely. So, I I think like the the context here is it's actually very easy to actually create a system that's more expensive as soon as you're running like, you know, multiple models together cuz oh, no, like, you know, this one file reading. Now, every every one of these models is now reading this one file reading. So, now you're you're you're being charged like three times as much. Um, the the the the trick that we we spent a lot of our time on is um, most of the context by default will only be going to like one model. So, like most of the context let's say will be going to the small model. But, the thing you need to then tune very well is okay, like maybe you still show like what files it's reading, maybe you show like the high-level thinking of what it's doing back to the main model. Maybe you have the small model um, you tune its ability to present the context back to the main model. Um, and actually a lot of these problems already have been well studied in many domains already like context compaction is something you already have to solve if you want to do like really long-running agents. And so, this problem of taking long context compacting it in a way that is now understandable is the one that you can also apply to this domain and just kind of give the compacted context back to back to the main agent.

</details>

**主持人**: 这非常有趣。虽然我对上下文压缩有所了解，但我之前确实没有将其与多模型路由关联起来。在多模型环境下，如果频繁地在不同模型间流转原始上下文，确实会造成巨大的 Token 浪费和重叠计算开销。

<details>
<summary>Original English</summary>

**Host**: Context compaction is something that you know, I'm familiar with but I hadn't really thought about as you're doing model routing and as you're trying to share context across now potentially many models, you're you're expanding the amount of what could be seen as wasteful tokens or redundant tokens just just because you have to process that across the many models.

</details>

**Walden**: 是的，正是如此。我们目前仍处于模型路由领域的极早期阶段。我希望一年后当我们回头看 Devin Fusion 现在的设计时，会觉得这些做法非常古老，因为届时肯定会出现好得多的路由机制。而且，当未来的大模型在研发之初就将“可路由性”作为协同设计的考量时，整个生态系统会变得更加强大。

<details>
<summary>Original English</summary>

**Walden**: Yeah. Yeah. Um, I I I think there's the way I describe it is I think we are early in in the in the model routing domain. Um, I I I hope that a year from now that even the techniques we kind of use for Devin Fusion you people look back on that and are like, "Oh, these are some like really legacy ideas and and now we have like much better methods at routing between models." Um, and when people actually start co-designing their models with this in mind we're going to be be in a much better world.

</details>

### 智能体协同设计与强化学习

**Donne**: 我非常赞同 Walden 的看法。路由机制一定会随着我们任务形态的演进而演进。当我们处理实际问题时，我们应该更多地从“子任务”和整个“交互会话”的角度去审视它，而不是只关注单个独立的 Prompt 触发。在复杂的业务流中，用户会提出大量问题、探索不同的方向。因此，路由器的设计者必须理解这些复杂度的不同阶段，并引入相应的逻辑来进行协同和任务委派。

<details>
<summary>Original English</summary>

**Donne**: Yeah, I I echo what you said that um, I think routing will evolve as the task evolves when when you start task, right? So, um, it's more useful to see things in terms of subtasks and sessions uh, than individual problems that you're trying to solve because more than likely you're when you're working through a problem you're asking a lot of questions, you're you're you're exploring different things. Um, and it is imperative that you try like people who design routers is imperative that they try and understand these phases of different complexities and then try and apply some logic for essentially side kicking tasks or leveraging expertise from other models that's that's pretty on point.

</details>

**主持人**: 我很想听听 OpenRouter 作为分发平台的看法。

<details>
<summary>Original English</summary>

**Host**: Yeah, I'd love to hear from the the router guy.

</details>

**Alex**: 哈哈。我认为这些都是非常核心的问题。我们内部争论最多的一个议题是：**负责顶层协调的那个外部模型，究竟应该是一个大模型还是一个小模型？** 

根据你的选择，你得到的运行结果和效率会截然不同。甚至在价格上，它的影响也是复杂的。如果负责编排的外部模型是一个前沿大模型，虽然它本身的单价贵，但它能够利用 **上下文缓存（Prompt Caching）** 来加速它做出的大量决策，这在很多时候反而比频繁让小模型加载上下文并重新计算要省钱得多。

从更宏观的视角来看，当你在进行多模型融合时，你希望从所有不同实验室、不同来源所训练的数据中汲取红利，而不是局限于某一家。一个模型本质上是它所接触的数据、计算量以及强化学习（RL）质量的结合体。长期来看，你希望模型能够清晰地知道哪些知识在它的“分布内（In-distribution）”，哪些在“分布外（Out-of-distribution）”。对于分布内的任务，直接用小模型处理可以轻松省钱；但一旦面对分布外的任务，强行使用小模型反而可能增加你的整体成本——因为小模型会因为理解不了而陷入疯狂调用工具和死循环的怪圈。

例如，如果你在 `Terminal Bench` 上运行 Claude 3 Opus 和 Claude 3 Haiku。Opus 的表现可能比 Haiku 好三倍，而其整体最终消耗的成本可能只有 Haiku 的十分之一——即便 Haiku 的单 Token 报价要便宜得多。因为 Haiku 会在错误的道路上生成大量无用的垃圾 Token 并不断重试。所以在面对超出模型训练域的任务时，使用过小的模型会带来灾难性的代价。相反，如果只是做简单的文本分类（例如识别一段文字里哪些是人名、哪些是机构名），这属于强分布内任务，就应该坚决路由给小模型。因此，如何精确识别分布内与分布外，正是我们在 **OpenRouter Fusion** 中花费大量精力在做的工作。同时，我们也在探索如何针对不同任务，最优化地编排内层与外层模型的协同。

目前整个行业还处于非常早期的研究阶段，但我们对此非常乐观。我们是一家非常注重生态协同和合作的企业，正与许多合作伙伴一起，通过提供优秀的底层原语（例如子智能体原语和 Advisor 工具）来改进他们的编排管线。

<details>
<summary>Original English</summary>

**Alex**: Yeah, um I think those are these are like important points and one of the biggest debates I think we have internally is whether that outer model that's doing the orchestration should be the big model or the small model. You get like very different results depending on your choice and in fact and it's not even clear what the pricing impact would be because if your outer model that's doing the orchestration is the big model it can leverage its caching to like make more of its decisions and it's caching is going to be like a dramatic price savings compared to the small models caching a lot of the time especially for like perform for you know issues that are on the bright line like zooming out a little bit I think the what you want from all the models out there when you do model fusion is to benefit from all the data that is being trained on across all the labs and and not just the data from one lab right or one source and a model is just like a combination of like the data and its understanding of the data both its compute and the quality of its RL so long term I think you want you want models where they know that oh this is like in distribution like this is in my data you can use small models pretty easily and get a cost savings but if it's out of distribution small models may actually increase your cost because of how often they'll like call tools and how crazy their loops will be. Like if you run terminal bench on Opus and Haiku, like Opus will do about three times better at 1/10 the cost of Haiku, even though Haiku's significantly cheaper per token. So it really becomes a huge problem if you use a too small of a model, particularly on tasks that are out of domain for the train data. When you're doing something like classifying text, like hey, is this like a person's name or is this an organization's name? That's super in domain. So you would you don't want that kind of task to go to a large model. You want it to go to a a small model. Everyone has that in their domain. Um so deep like being able to understand in domain, out of domain is a lot of work that we're doing for for um open router fusion. And uh and then also figuring out like what like how to orchestrate the outer and inner models um for different types of task. And like um yeah, it's it's an early industry. It's like an early field of research. Uh most research on model fusion has not been very detailed, not been very like, you know, optimistic sometimes. Um it's only like just, you know, recently getting uh more optimistic. And I think um I'm personally very optimistic about it. And uh you know, like we we're very like ecosystem-driven, collaborative company. And a lot of our like we work with a lot of partners to try like help improve their orchestration pipelines with good primitives, like the, you know, sub-agent and like the advisor tool, um which is kind of similar to what you were talking about.

</details>

**主持人**: 这很有道理。如果一个小模型处于“分布内”，它会非常便宜；但如果不是，它就会在挣扎中白白消耗大量 Token。那么，关于主智能体应该部署在本地还是云端，这个决策是否也取决于该任务是否处于本地模型的分布内？

<details>
<summary>Original English</summary>

**Host**: I'm curious. So uh help me understand when uh if a it makes total sense that um a small model, if it's in domain, would be cheaper. But if it's not, then it's going to thrash around uh as it tries to get an answer. When you're describing whether the uh con- like the main agent should be the the the local model or the cloud model? Does that is that a decision that's then dependent on whether the task is something that it that's in domain or not? Does my question kind of make sense?

</details>

**Alex**: 目前阶段还很难给出一个绝对的结论。在我们几周前发布的研究中，我们主要聚焦于深度搜索（Deep Research）而非编程任务。在深度搜索场景下，我们让聪明的模型作为最外层的包裹器（Wrapper Model）和编排器，从而获得了最佳的效果。但在其他任务上，界限依然很模糊。模型路由在编程任务上的优化目前还不够极致，或许未来在编程场景下，小模型在单次成功解决任务的期望花费上能展现出更高的性价比，但这都需要时间的检验。

<details>
<summary>Original English</summary>

**Alex**: I don't know. Um, I basically I don't it's kind of early to um to say. I I think the I wait the results that we published, which are a couple weeks ago, which were focused on deep research, not coding. Um we had the smart model be the wrapper model, be the outer model, and we got the best results from doing that. Um, but it for deep research it works the best. Um, for other tasks, it's like kind of unclear. Like we there it's fusion is not super well optimized for coding. And uh it might be that like a smaller model ends up being like a higher um efficiency per you know, fewer dollars um per like completed successfully successfully completed task, but it's kind of early to say.

</details>

**Walden**: 刚才 Donne 提到，你可以从主智能体那里获得上下文缓存的好处。但实际上，你同样可以从旁侧智能体（Side Agent）上获得缓存红利。这也是我们在发布 Devin Fusion 时特别强调的一个理念：如果你只是简单地采用传统的“主智能体 - 子智能体（Master-Slave）”架构，实际上会漏掉很多优化空间。

在我们的系统中，我们并不倾向于使用临时创建、用完即丢的子智能体。相反，我们使用一种被我们称为 **Sidekick（侧翼副手）** 的常驻机制。这是一个始终保持运行状态的旁路智能体，它拥有持续演进的运行上下文。这意味着主智能体在分发任务时，不需要一遍遍重复提供历史背景，因为它们都已经存在于上下文缓存中了，这让输入 Token 的开销便宜了十倍。

我们目前还在花精力研究：如何通过强化学习（RL）训练出天生具备**协作能力**的模型？目前学术界有大量关于如何让一个模型端到端完成任务的文献。但我们该如何训练一个模型，让它擅长与另一个模型进行分工配合？我们尝试了两种设定：一是训练它作为编排者，决定何时将何种任务委派出去；二是训练它作为执行者（即常驻副手 Sidekick），测试它执行其他模型指令的精准度。我们预期，这种模型与编排系统的协同设计，将是多模型编排领域的下一个重大飞跃。

<details>
<summary>Original English</summary>

**Walden**: One thing you said earlier is like, oh, you get the caching benefit from like the main line agent. Um, you actually can get the caching benefit from the side agent. And um, this is actually one of the key things we talked about with our Devin fusion launch is that um, you kind of are leaving a lot on the table if you do a main agent and sub agents type system. Um, so we don't use sub agents. We use what we call a sidekick, which is um, one sub agent that continually has a running context. So the main agent doesn't need to re-provide uh, context from earlier. Um, it's all still in the KB cache, right? Like it's 10 times cheaper on on all those cache tokens. Um, and then if you want to like switch the smart model to be like the one on the side or the one in charge, um it's actually totally fine, and you can kind of like do do the swapping back and forth. We're also spending a lot of time right now thinking about how do you train models to actually work collaboratively with other models? I actually I think there's a lot of literature out there on how you RL one model to do a task end-to-end. How can you RL model to also be good at collaboration? And when we think about it, we actually try both of these setups where let's RL the model being the orchestrator and the one deciding what gets delegated to other models, see how well that performs. Um and we also orchestrate it in a way where the model we're training is actually the executor, the sidekick, and see how well is it at executing other models' instructions. Um and we expect that to to be a probably a big lift in this next step of like multi-model orchestration is don't just like take models as they are and orchestrate them, but like can you actually co-design your models with the orchestration system?

</details>

**主持人**: 这非常合理。比如英伟达在开发 NeMo-Tron 以及其他基座模型时，我们本质上也是在针对它们最终被使用的框架进行后训练（Post-training）优化。如果未来的开发框架中包含大量的模型路由逻辑，那么把路由和协作能力做进模型的后训练阶段就非常顺理成章。

<details>
<summary>Original English</summary>

**Host**: Yeah, that makes sense. I mean, with Nemo Tron and you know, with all the foundational models where um we're essentially post-training them for the harnesses that they're getting used. If the harness is going to include a lot of routing, then that makes sense that makes its way in to the post-training.

</details>

**Walden**: 没错。不知道英伟达内部是否也在针对这些协作和路由场景开展特定的模型训练研究？

<details>
<summary>Original English</summary>

**Walden**: Yeah. Um are you guys thinking a lot about the kind of like the model training at at Nvidia for this kind of purposes?

</details>

### 弹性运行时与本地/云端混合路由

**Donne**: 是的，我们有一项被称为 **Flex Run（弹性运行时）** 的技术。在我们的设置中，会有一个主模型，然后我们将其蒸馏（Distill）成不同尺寸和计算占用的子模型。在实际推理时，系统可以根据任务的实时复杂度，动态切换由哪一个级别的蒸馏模型来进行解码（Decoding）。利用这种技术，在同一个模型资产内部其实可以玩出很多非常高级的权变机制。也就是说，我们甚至不需要跨越到完全不同的模型架构，而是根据复杂度动态激活模型内部的某一个子权重区间。

对于开源模型或你可以访问训练数据的模型，如果你能掌握它的训练配方（Recipe），你就可以非常精确地在推理时判断出当前输入的问题对于该模型而言是分布内还是分布外。这意味着你可以动态调整模型的尺寸。

关于刚才提到的上下文压缩，我想补充一点：上下文压缩在本质上是有损的（Lossy）。虽然目前像 AST（抽象语法树）等代码表示方法能帮助我们进行相对无损的压缩来传递状态，但大家是如何看待这种信息损失与智能体状态保持之间的平衡的？

<details>
<summary>Original English</summary>

**Donne**: Yeah, so we have a technology called Flex Run. So you have uh we we have a setup where uh there's a the uh there's a main model, then we distill it into smaller uh footprints. And then based on the based on the task at hand, you can switch which model does the decoding. Right? So there's a lot of fancy stuff you can do uh within a model artifact, too. Uh to essentially only activate a class of model or a section of weights, depending on the task at hand or the complexity at hand. Most In most cases, you can essentially understand the novelty of a question to a model if you have access to the recipe with which it was trained. So, this works very well for open models, right? Like or any model you have access to its data for, right? Because you can literally decide if it's in like see if it's in distribution or not. Uh again, if you have studies from when it was trained, you can also see how much essentially how much was your distillation gap across teachers and the artifact that you trained, right? Because sure, you have domain data from all all the different domains you're tuning, but it's not guaranteed that it uh absorbed all the that data evenly across the models, right? So, um it becomes it becomes very interesting uh to start thinking about these flexible weights and flexible model sizes essentially. There's also I wanted to add with the context piece, right? So, how do you think about ASTs and and context compression representations? Uh compaction in its very nature is lossy, right? So, just like headroom is there, RTK is there, right? Uh these these spaces code bases are usually designed to have representations that we carry forward through life and you essentially give models the capability to further expand on them. It's it's more more like loss less-ish compression, which can retain states of a models or states of agents. What do you think about that?

</details>

**Walden**: 我觉得这触及了智能体和上下文设计哲学中非常底层的本质。我经常做的一个思想实验是：作为人类，如果我现在开始随机给你念一串数字，你在开始遗忘之前能记住多少个？其实非常少。这意味着人类大脑的实时上下文窗口其实比现在的 LLM 要短得多。但人类依然可以极其高效地处理极其复杂的软件工程。

为什么？因为我们的大脑记忆是有损的，但我们懂得利用外部的**无损系统**作为支撑。比如我们有文件系统。当智能体去阅读一个文件时，它不需要把整个文件一字不落地背在它的上下文里；它只需要记住文件里最核心的逻辑和位置，当它需要精确细节时，随时去文件系统里重新读取即可。所以，一个优秀的上下文工程系统（Context Engineered Harness），其核心目标是给智能体提供获取所需信息的**寻址能力**，而不是把所有信息第一秒就全部填满它的上下文窗口。

<details>
<summary>Original English</summary>

**Walden**: Yeah, I think this gets to like kind of like a fundamental philosophy of how agents and context should work. One exercise I like to do is like you know, as a human, like how many numbers can you like if I just start spitting out numbers now, right? Like how many can you remember before, you know, like you start losing track of them. I think it's actually very few, right? So, in some ways you could argue that your context window is actually shorter than these language models. And yet, you can actually be very effective at that, right? Your context is is very lossy. Um, I think one of the nice things that people are starting to realize with agents is like you have a lot of non-lossy systems that you can fall back to. So, you have a file system. Like uh if in your memory all your memory is that you read some file earlier, you don't need to remember the whole file. You maybe remember the important parts, but you can still have the full version of the file on your system. And that's kind of my goal when I'm thinking about how do we build a good context engineered harness is the harness should have everything in needs to find what it needs to have even if it doesn't have everything immediately available.

</details>

**主持人**: 在这种模式下，未来的上下文共享问题是否会变得更便宜、更不成为瓶颈？

<details>
<summary>Original English</summary>

**Host**: In that case, uh do you think that the context sharing problem will become cheaper and less of a problem in future?

</details>

**Walden**: 确实如此。我们看到很多案例中，Sidekick 智能体完成了庞大的工作后，它不会把完整的日志丢给大模型，而是通过文件路径进行轻量化引用。而聪明的大模型由于具备更高效的工具使用和阅读能力，它们在读取这些引用文件时，只会有选择地读取最重要的片段，或者运行一行命令来校验结果。

这种在智能水平提升时，系统整体 Token 消耗效率反而呈现出超线性提升的现象，非常令人惊叹。这并不是一个理所当然的结果。谁能想到，部署价格更贵的模型，最后却能帮你实现更便宜的整体系统成本？

<details>
<summary>Original English</summary>

**Walden**: Yeah, it's definitely possible as well. I've seen cases where um you know, the psychic agent does a bunch of work. It tells the main model, "Oh yeah, like here's here's all the things I found." Instead of dumping the full thing, it just references them by file. And then the main model is actually generally you find these larger, smarter models, they're actually more token efficient with how they use tools and how they read. And so, they actually read the files in a way where they only see the important parts, right? Or they decide that, "Oh, actually I only need to look at a subset of this." Or, "Oh, I can run a single command and just know if everything is done properly." Um, it's actually quite amazing um the fact that you know, these multi-model systems they actually seem to scale and get better with intelligence, which is um not something we should just take for granted, right? It's not obvious that actually more expensive models are actually creating an overall cheaper system.

</details>

**主持人**: 这就是大模型的尺度定律（Scaling Laws）在系统层面上的体现：模型越聪明，Token 的利用效率就越高；而小模型虽然单价低，但 Token 利用效率却低得多。

我想问 Alex 一个问题：作为 OpenRouter，你们目前会将注意力更多地放在路由的**基础设施端优化**上吗？例如感知 KV 缓存的路由器（KV-cache Aware Routing），或者是关注人们在生产环境中部署路由器的实际拉动情况？

<details>
<summary>Original English</summary>

**Host**: Yeah, like the scaling laws uh if you have a larger model, it's going to be more efficient with its tokens. Uh smaller models less efficient with its tokens. I guess I had a question for you, Alex. Uh do you guys uh like weigh more importance on uh the actual infrastructure side of routing? So, for instance, KV cache aware routing or uh like this where most of the businesses right now Uh or the are you seeing strong pull of like people actually deploying routers in production?

</details>

**Alex**: OpenRouter 本质上是一个语言模型的市场（Marketplace）。作为一个分发平台，除非我们自己运行模型（这非常罕见），否则我们是无法直接窥探到各个模型底层的 KV 缓存状态的。

不过，我们确实花了大量时间来针对**缓存命中（Cache Hits）**进行路由优化，并将由此产生的成本节省直接传递给终端用户。具体来说，当我们的系统检测到某个请求有极高概率命中缓存时，我们会在缓存有效期内坚决路由到该节点。

在这方面，我们甚至在尝试更高级的玩法：即便你手头的缓存还有两分钟才过期，但如果我们计算出此时切换模型能带来更大的整体系统增益，我们会选择主动废弃这一段缓存并进行路由切换。我们正在小范围内测试让用户自己去微调这种行为的容忍度，不过目前还没有对所有客户公开。

<details>
<summary>Original English</summary>

**Alex**: So open router is a like a marketplace for language models. We we exist at like we can't see into the KV caches of models unless we're running them ourselves, which is pretty rare. Um we we do spend a lot of time optimizing for cash hits and we we like pass through cash hits directly to users. Um but like in terms of KV cash optimizations we we we can't do any of like specific work there. What we do for um model routing is we we try to like find the best model or best combination of models for the prompt and then when we see a cash hit, we will will like use up the duration of the cash and send the downstream customer like the the full savings of the cash hit. Um there's more work that we can do here where we could say, okay, this looks like something where there's significant benefit to switching the model right now, but you haven't used up the full cash. You still have like 2 minutes left. Um and it we think it's probably worth switching the model and losing the rest of your cash um and letting people kind of like tweak their tolerance for that behavior. Um we've we've been doing a little bit of that, but we haven't like exposed it to customers yet.

</details>

**主持人**: 太棒了。那对于 OpenRouter 的路由业务而言，下一步的规划是什么？因为这听起来和你们最初纯粹的模型分发市场有些不一样。

<details>
<summary>Original English</summary>

**Host**: Awesome. What what is next for you guys in terms of your your your model routing? Cuz as you mentioned, you know, it is kind of like a different direction from like the the marketplace business that exists today. So I'd love to hear.

</details>

**Alex**: 实际上，我们推出自动路由器（Auto-router）已经快两年了。但在刚推出时，几乎没人使用，大家都只想明确指定调用某一个特定的模型。当时我们主要把它看作是一个帮助用户“探索和发现”适合自己 prompt 的工具。

然而，今年一月份情况发生了彻底的改变。随着 **OpenClaw** 这类智能体应用的爆发，我们的路由器流量也迎来了爆炸式增长。这里面有一个非常有趣的滑稽历史：OpenClaw 客户端有一个机制，每隔 10 分钟就会向你指定的模型发送一次心跳探测（Heartbeat），以确认客户端是否依然活跃。如果你把默认模型设为极其昂贵的 Claude 3 Opus，你就会在这些毫无意义的心跳上浪费大量代币。

这也是人们第一次切身意识到：同一个应用中，其实存在着两种截然不同的智能需求。心跳和基础维持只需要极低的智能，而核心任务则需要极高的智能。与此同时，开源模型的性能也提升到了可以让市场在不同层级进行合理分流的程度。

现在，OpenRouter 上的大量智能体和应用都在使用我们的各种路由器。我们提供了好几种选择：例如 **Pareto（帕累托编码路由器）**，它能在给定的预算和延迟阈值内，为你推荐处于帕累托最优边界的编程模型；当然还有我们负责编排多模型的 Fusion 路由器。未来我们还会推出更多实验性原语，目标是为开发者提供灵活的“边车（Sidecar）”工具，既能让他们进行复杂的编排调优，又能简单地通过设置一个统一的 Slug 接入所有主流框架。

<details>
<summary>Original English</summary>

**Alex**: So I mean we've been doing like we we've had a an auto router for like 2 years almost. Um but when we launched it, there was like no adoption of it. It was people really wanted to use specific models. Um and the the auto router just had like no real usage. It was we mostly saw it as like a discovery play point. Like, hey, this is how you discover which model might be good for your prompt. And then um at around like January this year with open claw, it exploded. And the reason it exploded is because there's this fundamental um idiosyncrasy in open claw where it sends heartbeats every like 10 minutes to your model of choice just to see like if the you know, if the the the client was still active. And that means that if you set Opus to be your default model, it would be like using a lot of tokens on this like heartbeat process. And so um this was the very beginning of like a very popular app with two completely different intelligence needs, completely different. And the models the open source models have improved to a point where like it makes sense to segment the market and at at least those two areas. And so that's that was how it got started. And then we saw a lot more segmentation blossom afterwards. And so um and now a whole bunch of agents and apps on open router use the the different routers that we have. We have a couple of them. We have Pareto code which gives you the Pareto Pareto optimal model for coding tasks given a certain like threshold that you can tune. Um we have fusion which orchestrates multiple models and gives you a fused result. And um and then we'll have other experiments in the future. What we want to do is basically like create good primitives that developers can use to like get really advanced with how they use model orchestration. Um kind of like sidecar sort of like that. Um but also give people like a really easy thing that they can just like set a slug to that works with all harnesses and just like gets the job done.

</details>

**主持人**: 目前的行业发展确实为模型路由创造了一场“完美风暴”。一方面，即便是忽略智能体，纯粹为了压榨出更好的模型表现，我们也必须打破传统的单步 Prompt 限制，引入任务拆分与策略规划。这必然推导出路由的诉求。另一方面，随着智能体的普及，工作负载的特征发生了质的变化：从最初的“一问一答”，到包含思考过程的“推理流”，再到现在的常驻心跳流。每一类工作负载都有其独特的路由经济学。

<details>
<summary>Original English</summary>

**Host**: I feel like it's super interesting how much of a perfect storm there is for model routing right now because on one hand, you know, ignore agents, ignore open claw for a second, like just to squeeze better performance, it seems like we should be smarter about how we tackle problems. That's obvious, right? If you make a plan, if you make a strategy, that's a that's a better way to to go about your day. So, I'm not surprised that you're going to see, you know, better code get written or more performing code get written and less buggy code get written if you break the problem down. And so, routing specifically for that uh use case makes a ton of sense. But then hearing this, yeah, like the profile of workloads changed with agents, right? They're very they it went from like I ask questions, I get a response, then it went to reasoning where I ask questions, it reasons, and then it comes back, and then it went to uh yeah, this heartbeat, right? Like if um if my agents are running optimally, uh there's a token being generated every second. Um and suddenly that is its own need for model routing, and it feels like um hearing the different solutions uh to kind of tackle each of those is very interesting. Even

</details>

### 本地部署的经济学与幻觉探测器

**主持人**: 是的，我们甚至还没深入探讨的一大路由驱动力——尤其是对在座的各位企业代表而言——就是**本地运行（Run Locally）与云端前沿模型之间的动态平衡**。这里面不仅有成本考量，还有隐私和敏感信息保护。例如，能否在本地通过一个小模型先对 Prompt 进行实时扫描，一旦发现包含敏感隐私信息，就在本地进行脱敏和匿名化，然后再把高难度的推理任务路由到云端的大模型去处理？

另一个例子是硬件资产的利用率。很多企业购买了昂贵的英伟达 DGX 服务器，但他们的日常 GPU 利用率可能只有不到 100%。如果企业能建立起本地与云端混合路由的管线，把日常的心跳维持、简单分类和本地脱敏任务全部路由到自己的 DGX 上运行，而只把超分任务发往云端，这就能把硬件资产的电子红利吃满。本地与云端混合路由必然会崛起成为一个庞大的独立细分板块。

<details>
<summary>Original English</summary>

**Host**: Well, I was just going to say I think that yeah, the the use cases for model routing are are there are many of them. And so, one could be getting a better answer, one could be, you know, saving money and trying to get the same answer. One that we haven't even talked about yet, which is probably the most relevant maybe even to this crowd, is uh when do you want to actually run a model locally versus when do you actually need something like a frontier model to to perform that task. And that might be something to the effect of like uh for privacy protecting information. You know, when I'm running some local, it can you detect that my prompt has sensitive information? And if so, do that on on device, um but then maybe even anonymize some of that information to go do the more advanced workloads up on top of that information in the cloud. Um another example would be again for the cost savings, but it's like, "Hey, I bought this DGX Spark and I'm not I I know I'm not at 100% utilization. How can I make sure that as part of my workloads, whether it's the heartbeat and open claw or what have you, that I'm leveraging that compute um to the fullest of its ability because I'm only paying for the electrons that are coming in for my power bill, um but I'm paying full price for the tokens in the cloud?" And I think that's a whole other area of model routing that I know that we're doing some work with at NVIDIA um that I think will be will be really cool as it starts to uh the hybrid of local and cloud starts to to really emerge as its own sector.

</details>

**主持人**: 我想知道大家对自建数据中心、自托管模型的成本动态怎么看？当我们自托管模型时，随着上下文深度的增加，模型的吞吐量（Throughput）会显著下降。在这种情况下，我们是通过路由到其他小模型更划算，还是在本地通过上下文压缩来挽救吞吐量？

<details>
<summary>Original English</summary>

**Host**: Yeah, I'd be curious to know what you guys take uh take is on. Like if you self-host a model, the cost dynamics change, right? You have a considerably higher cost at a higher context length because your throughput slows down as the context gets deeper. So, rather than switching to a cheaper model, even if you have self-hosted models in data center, you can use compaction uh to bring your throughput back up. Uh have you guys uh thought about this part of it? Like compaction versus uh just routing because one is you have fewer tokens to work with. One is we have cheaper tokens.

</details>

**Walden**: 实际上，单纯靠上下文压缩是无法彻底解决成本和吞吐瓶颈的。因为在实际应用中，前沿模型和小模型之间的智能和价格差距实在太悬殊了。而且，当你进行上下文压缩时，由于内容发生了改变，你会不可避免地在推理端触发一次严重的 **缓存未命中（Cache Miss）**。这意味你必须重新为这一批输入 Token 支付全额计算成本，有时反而得不偿失。

我们进行上下文压缩的核心出发点，其实是为了**保护智能**。现在的很多模型厂商在广告里宣传自己支持 100 万甚至更高的超长上下文。但作为从业者，我绝对不建议你在生产中将上下文用到 20 万 Token 以上，如果可以的话，尽量控制在 10 万以内。因为在上下文极深的地方，模型的实际遵循和推理能力会发生断崖式下跌。

（哈哈，如果 Anthropic 的人在看我们这场直播，我表示抱歉，但事实确实如此。）

因此，如果你注定要承受缓存未命中的代价（比如当你决定路由切换到另一个模型时），这时候使用上下文压缩来最小化新模型的上下文窗口，是极其行之有效的。

<details>
<summary>Original English</summary>

**Walden**: Yeah, I I think in practice um compacting alone doesn't solve the the cost or or throughput problems because a lot of times it's just like the uh the differential in like model intelligence and cost is just so big where also by the way, when you compact, you're taking a cache miss. So, you're actually then now like paying 10 times as much for the for those input tokens if you didn't compact. Um the main reason we compact is actually intelligence. Um all all these like multipliers they advertise some like insane context window, like a million tokens. Uh I would like never recommend using like these models past like 200K tokens, under 100K if you can. Um the the the intelligence uh just kind of like falls off a cliff at some point. Um sorry, Anthropic if you're if you're watching. But I I think that uh you know, compaction is like a very useful tool if you are going to have to take a cache miss anyway um one way or another, like when you're routing to another model and you want to just like minimize the the window there.

</details>

**主持人**: 也就是说，当小智能体疯狂吐出 Token 导致上下文急剧膨胀时，也是一个非常好的时机去主动将任务路由并升级给大模型？

<details>
<summary>Original English</summary>

**Host**: Do you find that, um, in the sidecar, um, when small models are generating lots of tokens, um, is that like an is that like one of the best reasons to switch it to a larger model? Like, basically, when when small models generate lots of tokens, I wonder if that's like a box of root the root cause of of intelligence problems down the road. You want your big model to generate the big token chunks, the small models to generate smaller token chunks, right?

</details>

**主持人**: 换句话说，小模型发出“求救信号”触发路由的那个具体**检测机制**是什么？它是通过什么指标来判断小模型已经搞不定了的？

<details>
<summary>Original English</summary>

**Host**: that question, you mentioned like a small model essentially needing to flag that it needs help from the larger model. What is that mechanism? Cuz that seems like the what's the indicator and then what's the mechanism for it to do so?

</details>

**Walden**: 我们的博客中提到过很多检测触发机制。关于小模型如何感知自我局限，老实说，在非常多的场景下，你无法指望小模型自己能完成这种“元认知”——你必须依靠幕后监视的大模型来进行主动探测。

有一项我们在博客中没有详写的实用工程技巧是：在很多云端推理服务中，由于 KV 缓存存在一个默认的 5 分钟左右的生命周期（过期会被剔除出 GPU 显存）。既然我们在生命周期结束前注定要去重新刷新缓存，我们可以在刷新缓存的节点上，顺便免费附带一次前沿大模型的调用。在这一步，我们会让大模型快速审视一遍小模型在过去几分钟内的运行痕迹：“你看小模型目前是不是在一个死循环的兔子洞里打转？它是不是需要帮助？”

<details>
<summary>Original English</summary>

**Walden**: Yeah, totally. Uh, so there are a lot of mechanisms we we talk about in our blog post about how uh we just detect that we need to like change the model up. Um, to to uh I guess to answer your question first, how does the the small model detect? Um, actually, the the thing that we spend a lot of time on is, um, how do we make sure the small model is like good at detecting it. Unfortunately, there's a lot of cases where you do need the big model to detect it. Um, one thing that we could don't go into the blog post is, um, you have some kind of cadence on which you're refreshing the cache anyways, cuz by default there's some like 5-minute lifetime on these caches. If you're going to go refresh a cache anyways, you basically can get a free like big like frontier model call uh if you kind of like ask the right question. So, it's at that point where you might say, "Hey, just take a look at what the small model is doing. Does it feel like it's kind of like going into some rabbit hole and and need some help now?" Um,

</details>

**主持人**: 为什么会有这个 5 分钟刷新的限制？

<details>
<summary>Original English</summary>

**Host**: What's the need for the 5-minute refresh?

</details>

**Walden**: 这主要是推理服务商在物理硬件上的商业限制。为了腾出 GPU 昂贵的显存，非活跃的 KV 缓存必须被定期清除。

<details>
<summary>Original English</summary>

**Walden**: Uh, it's just like a practical like you you you have to pay some kind of like cost to like keep these like KV cache caches warm. Um, and so most caches just get evicted on some kind of cadence.

</details>

**Donne**: 在推理时间（Inference Time），GPU 显存中能容纳的活动缓存数量是有限的。一旦某个客户端的缓存有一段时间没有被再次调用，它就会被下载（Offloaded）到系统内存或被直接丢弃。这也是为什么云端服务商需要为此向你收费。但如果你是本地自托管，你完全可以根据自己的业务逻辑，把缓存周期设得任意长。

<details>
<summary>Original English</summary>

**Donne**: works is like at inference time you only have so many so many cache you can keep kept loaded in the GPU. So, once if a cache is not being used again and again, it's offloaded. So, it's lost essentially. So, that's why the inference provider asks you for money. Uh but if you self-hosted, you can get around this problem. You can you can make it as long as you want based on your big business logic.

</details>

**主持人**: 未来我们会看到更动态的缓存生命周期吗，比如长达数小时？

<details>
<summary>Original English</summary>

**Host**: But do do you see a world where we'll have like much more dynamic cache durations rather than just the 5-minute, 1-hour?

</details>

**Donne**: 这完全取决于部署的环境。如果在一块显存比例极高的特定 GPU 上，或者在苹果的统一内存（Unified Memory）架构中，或者是基于像英伟达 **Rubin** 的下一代架构，我们可以玩出非常多的软件优化策略。目前主流提供商的 5 分钟限制是一个出于商业运维成本（Operational Determination）的选择，而不是物理定律层面的硬性约束。

另外，如果企业选择自托管，成本结构和计费经济学将发生根本性改变。云端 API 提供商需要对所有客户的计算特征（例如有人是 32K 缓存 + 1K 输入，有人是 64K 缓存）进行平均化摊销来给出一个固定报价。但如果你自托管，你可以根据自己单一且特定的工作负载形状去极致压榨硬件，其最终的运行成本往往会低得多。

<details>
<summary>Original English</summary>

**Donne**: It depends on who's do who's deploying the model where, right? So, if you have a GPU which has like a lot of memory uh which like the ratio of let's say SCMs to memory is memory more heavily skewed or if you're working with unified memory uh and you have systems like where I Rubin, uh you you have a lot of tricks to play here, right? Uh the 5-minute uh window is what a lot of providers right now put, but that's uh that's that's more an operational operational operational determination rather than a like a science-based or like a core physics law determination. So, you can technically see over time maybe some uh some APIs are priced differently, uh but uh if you do self-deploy again, you can you can get past a lot of this. The the cost economics really change when you move from self-hosted models to uh API providers uh because you have a lot more control and uh you don't have to guess the shape of your workload. So, let's say if your workload is 32K uh like on average 32K cache, 1K input, 1K output, uh and someone else's like let's say 64K uh 1K 1K, uh if you use some provider, they are amortizing everyone's use case and then giving you a price, right? And they have optimized, quote and quote, for general use. If you self-host, you can optimize specifically for your use, and you'll likely pay much less.

</details>

**Walden**: 这正是软硬件前沿协同设计最令人着迷的地方。当我们在 2024 年创办 Cognition 开始研发首个 AI 智能体时，整个行业还没人愿意往这个方向走，因为大家觉得智能体的代币成本高得像个笑话。当时甚至连 Prompt 缓存的概念都还没有。如果你让智能体连续走十几步，每前进一步你都要为前面累积的十万 Token 支付全额费用。

我们当时之所以能把 Devin 做出来，是因为我们直接与算力提供商包下了整机算力（Dedicated Compute Capacity），直接在物理卡层面上进行长周期运行，避开了昂贵的单 Token 计费。

而现在，我们正在和大家一起思考：我们能否把模型的 KV 缓存镜像直接转储（Dump）到廉价的云端冷存储（如 S3）中？在需要时再快速将其热加载回 GPU 显存。如果这能实现，缓存的生命周期将拉长到天级别。

<details>
<summary>Original English</summary>

**Walden**: Yeah. This is like kind of like the level of like, you know, hardware-software frontier that we kind of like think about. When we started Cognition, we were working on the first agents, I think one reason why no one else worked on agents is they were just extremely expensive. This was before cash tokens was a thing that API providers paid for. Like if you were sending 100,000 tokens and the same 100,000 tokens, you were paying full price for those tokens back in 2024 when we started. One of the key things that let us build Devin and build these first agents was we actually bought direct compute capacity from these providers, and instead of paying on a per-token basis, we just paid for the underlying compute, knowing that the economics of the compute was that we were actually paying far less for for the cash tokens that we'd send over. Um And then nowadays, you know, that uh you know, there's there's like similar, you know, things I would like about like, you know, having a version of the cache that maybe like you can just back out to like storage in S3 or something and just like hold for much longer.

</details>

**Donne**: 如果你们想要做这样的尝试，可以去研究一下英伟达开源的 **Dynamo**。我们在里面针对预固定缓存（Pre-fixed Cache）进行了大量的系统级工程优化。

<details>
<summary>Original English</summary>

**Donne**: Yeah. Now, this is not extremely relevant to a DGX organization like setup, but if anyone's looking to do what you guys have wanted to try out Dynamo. We have a lot of pre-fixed cache optimizations in there.

</details>

**Walden**: 那非常棒。顺便回应刚才 Alex 的问题：小模型在吐出海量 Token 时是否应该作为退避和升级路由的指标？我们目前确实还没有将这一特征作为核心判定条件。但这是一个非常好的思路。我们注意到不同的小模型在生成 Token 的冗余度上存在巨大差异，不过这很多时候也取决于它们在训练时接触到的上下文轨迹。我们要得出确切结论，必须在开发中保持极其严谨的实证（Empirical）态度。

<details>
<summary>Original English</summary>

**Walden**: Yeah. Um And then going back to your question, Alex, I think you said like, "Oh, like you When a small model is going off and generating a ton of tokens, is that like a interesting time to back off?" Um to be honest, we haven't explored that right yet. So, that that might actually be a very interesting thing to to take a look at. Um It It is weird. I think like some small models do tend to kind of be less like token efficient than others, but um they also seem to be trained on like their own traces, so maybe in a way it ends up like balancing out. A lot of these things I I feel like we have to be like very empirical to actually know.

</details>

**Donne**: 补充一下，目前学术界和工业界在**幻觉探测器（Hallucination Probes）**上有很多进展。这些探测器能够直接对运行中模型的隐藏层激活值（Hidden States）进行轻量级的线性探针分析（Linear Probing）或幅度分析。通过这些探针，我们可以在解码的每一步实时输出当前模型思维的“困惑度（Perplexity）”或它偏离训练分布的程度。这提供了一个非常精准的量化指标，来作为路由系统判定模型是否已经“陷入胡思乱想（Lost in thinking）”的求救信号。

<details>
<summary>Original English</summary>

**Donne**: So, uh just to add on that um um you have a lot of like these days there are a lot of hallucination probes. So, probes that work on either the internal state like internal state of the models directly. So, you can have some form of either magnitude analysis done or linear probes or just uh the end types of probes that you can see and you can essentially rate like how how much you think is is tending towards hallucination. Uh so, that kind of gives you a proxy for how lost it is. Uh like how lost a model is in its thinking. Uh so, you can use like different kinds of probes to understand like the perplexity within a model.

</details>

**主持人**: 这非常神奇。所以路由不再仅仅去统计生成了多少个 Token，而是直接透视模型隐藏层的数学状态，来判定它是否在幻觉。

<details>
<summary>Original English</summary>

**Host**: Well, that's interesting. So, yeah, instead of using the quantity of tokens that are as indicative of a of a model being lost, it's the it's hallucinating more and you're

</details>

**Donne**: 是的，因为模型在推理前推（Prefill）阶段产出的本质上就是一系列向量。我们完全可以通过外挂一个极小的轻量级分类器，来对这些前推向量的状态进行诊断，从而估计模型所处的状态。

<details>
<summary>Original English</summary>

**Donne**: Yeah, so uh so, essentially what is cache, right? It's It's the prefill It's the prefill stage, right? So, you What is a prefill stage? It's just a vector at the end of the day. So, you can do tune all kinds of classifiers to understand uh different aspects of those collections of vectors. So, with those kind of probes, you can guesstimate a lot of uh states of a model.

</details>

### Prompt 不兼容性与智能体的迭代

**主持人**: 另一个核心的工程痛点是：**Prompt 的非兼容性**。由于不同模型的词表、注意力倾向和训练偏好大相径庭，为大模型精心设计的 Prompt 如果直接发给小模型，往往会导致严重的格式崩溃。在多模型路由的设计中，你们是如何处理这种 Prompt 适配和动态转换的？

<details>
<summary>Original English</summary>

**Host**: I see. One One question I have is um you know, different models behave uh differently and um the kind of means that these prompts aren't portable. So, as you're doing model routing, how do you handle essentially if you're if you're going to a different model architecture, um what do you want to do to the prompts and how much is that a factor into either of you guys' model routing solution? Like what like how how is the prompt itself a factor in the in the routing?

</details>

**Walden**: 在构建复杂的 AI 软件工程师（如 Devin）时，你会遇到无数由不同模型的微小格式偏好导致的“千刀万剐般的细节边缘案（Paper cuts and edge cases）”。我们作为一家智能体公司，其核心的核心资产和技术壁垒，其实就在于积累了大量关于智能体在各种复杂环境下如何跌入死循环的观察日志，以及总结出了最稳健的恢复算法。

这些避坑指南和恢复机制，最终都会以一种极其精密的方式沉淀进我们为不同模型定制的 Prompt 系统中。这就要求不管是顶层的 Advisor 模型还是底层的执行模型，都要有量身定制的指令接口。我们在开发 Devin Fusion 时，必须能够让团队里的任何一名工程师，甚至让 Devin 它自己，去调阅任何一次运行的路由轨迹（Traces），手动或自动地对局部 Prompt 进行微调，并在庞大的回归测试集上跑出准确率数据，确保一次修改不会导致其他地方掉链子。我们目前主要依靠这种在实战中淬炼出来的工程管线，而不是去依赖某种低层级的、完全非黑盒的自动梯度下降 Prompt 调优机制。

<details>
<summary>Original English</summary>

**Walden**: Yeah. Yeah, um well, I think with building agents, there are all kinds of paper cuts and edge cases that are domain-specific and like the value of an agent company like the value of Devin is all these like doom loops that you've discovered that are across all industries and the best ways to recover from them and like man here I mean it manifests big time in what the prompts are going to be both for like you know how the the the advisor model gets called um uh you know the smart friend the how the like subtask agents get called and and the best thing is that like anyone can like like any engineer or any like agent can inspect the traces and like adjust the prompt and then see the like live accuracy long time. So I mean basically I just think that that's part the prompt is part of the the startup building process and is also really easy to observe and like and have and have like multiple people and agents collaborating on them.

</details>

**Alex**: 我们目前在 Fusion 产品上虽然还没有上线这个功能，但这确实是我们正在进行技术预览（Preview）的方向：**根据生产环境中的真实调用数据进行路由规则的自动迭代**。

当用户在使用基于 Fusion 的智能体时，如果系统原本将任务分配给小模型，而用户在前端界面因为输出不满意，手动点击了“升级到前沿大模型”，或者我们底层的回归系统检测到小模型的输出被否定了，这就产生了一个极具价值的负反馈数据流。我们可以捕获所有这些真实的生产 Prompt 与路由成败对，在后台不断迭代我们路由器的分类权重，使其能够像液体一样慢慢贴合用户的真实业务边界。

<details>
<summary>Original English</summary>

**Alex**: Yeah. One thing I'd love to do with our fusion product and we don't have this yet and so this is kind of maybe a preview of some some things we work on is you know you can tune it against a data set but the the real thing you want when you're building a real agent someone uses is just like tune it against what actual people use it for and and what actual models they get routed to. And so there's a lot of signals for this like if if someone sends a prompt and then Devin is working and then you see that the user decides themselves like upgrade to a different model or they decide to downgrade or the system detects that we originally sent to the wrong one we now got to replace. Like that's actually a really useful stream of signals and we're actually getting into this world of like auto research where like maybe we can just have like a constant stream of prompts what it should have been what it was instead and build a system internally that's just capturing all of this and then reiterating on our routing system until it eventually kind of like fits the real production data. Um that's kind of like now that we it's it's it's public and and people are using it, this is now something that we're we're thinking about.

</details>

**主持人**: 你们有尝试过利用算法进行底层的自动 Prompt 优化吗？

<details>
<summary>Original English</summary>

**Host**: Have you guys looked into prompt tuning and do you find it useful like say Japa?

</details>

**Alex**: 几年前学术界有一些尝试通过梯度下降来寻找最强 Token 组合的 Prompt 优化框架。我个人对这些底层的机械化调优方案并不太看好。相反，我认为更有效的做法是：把执行失败的完整上下文丢给一个非常聪明的前沿大模型，直接质问它：“请帮我分析，为什么刚才小模型在面对这句 Prompt 时理解错了？是哪里产生了格式歧义？”

利用前沿大模型的通用智能直接生成 Prompt 的修改意见，然后自动部署进系统运行回归测试。我对这种基于高阶智能迭代 Prompt 的系统拥有高得多的信心。

<details>
<summary>Original English</summary>

**Alex**: Yeah, so there are like these prompt tuning frameworks from like a few years ago that tried to do some kind of like gradient descent type thing. I'm like I'm actually personally less bullish on these kind of like low level mechanical prompt tuning harnesses versus just telling like a smart model like here is the decision that was made and the context figure out why it went wrong. Sometimes you can do something as dumb as asking the model why did you do this instead of this and cite the prompts and then just have your agent your dev and just go and update the prompts, rerun the the test as a regression, make sure make sure it changes. Like it's a lot heavier weight of a system, but I kind of trust the intelligence of a system like that a lot more.

</details>

**主持人**: 好的，因为时间有限，我们得准备收尾了。今天的讨论非常精彩，我们清晰地感受到了这个领域的鲜活和新颖。这在很大程度上依然处于科研和产品化的交界处。

随着越来越多的开发者在本地使用 DGX 等算力设备，当本地显存被活动缓存占满，或者内存带宽遭遇瓶颈时，我们可以通过多智能体路由和并发委派，把闲置的 GPU 计算核心（Compute Utilization）彻底吃满。也就是说，多模型路由不仅是云端省钱的妙招，更是压榨本地边缘端硬件性能的必经之路。

最后我想留给大家的一个思考问题是：模型路由在未来究竟会成为一个独立的商业化软件产品，还是会作为“软件水管（Plumbing）”被直接内化进各大基础模型和开发框架的底层？未来是否大模型天生就会自己路由到其他模型？

<details>
<summary>Original English</summary>

**Host**: So we're we're running out of time, so we're going to wrap up real quick, but I think what's really interesting is just from talking to you guys, we can kind of see how new this space is, right? How much of this is actually just research. We're starting to see new products come in. I'm really excited about your guys' solutions as you guys enter the space. The the ways and the needs that you need routing for, you know, even on a DGX Spark when you're doing local inference, you have more compute and if the memory is filled, one or if it's if the memory utilization is high, one thing you need to do is increase the compute utilization. And so one way you can do that is by spawning multiple agents that are working collaboratively. So that collaborative piece is something that not only is optimal for all of these cloud workloads that you guys are doing, but but specifically that is how you extract more performance out of this edge hardware. And I think um you know, a question here is and maybe to to end on is a router going to be something that we see as a product or is that going to be seen as part of the plumbing here? Are models going to get good at routing to other models because they know they need to be collaborative or or harnesses going to know that they are working across multiple models.

</details>

**Walden**: 实际上这正在发生。在 Cognition，我们正在研发的新一代大模型本身就已经在后训练中融入了“协作”和“自我委派”的基因。未来的 GPT-5.5、GPT-5.6 或者是像我们的新模型，天生就非常擅长将大任务肢解并委派给周围的 Sidekick 模型。所以我认为，模型本身的协作化已经是一大确定性趋势。

<details>
<summary>Original English</summary>

**Walden**: I think we already see this. Like you know, at Cognition we're training our models to be able to be good collaborators. I think it's very clear that new frontier models like the Fable models and GPT-5.5 and 5.6 models are like themselves like naturally collaborative and and better at delegation. So I think we're ready there at that point.

</details>

**主持人**: 这非常引人遐想。

<details>
<summary>Original English</summary>

**Host**: Interesting.

</details>

**Carter**: 没错，未来的抽象层级一定会不断走高。最终我们会发现，无论是开发框架、调度边车还是大模型本身，它们都会融合成为一个我们今天还无法清晰定义的“智能体块（Smarter Blob）”。我们不可能割裂地去讨论一个优秀的运行环境和一个优秀的模型，它们是深度绑定的。

<details>
<summary>Original English</summary>

**Carter**: Yeah, I I think that the systems are are kind of becoming not muddied in some sense, but I think that ultimately we're understanding that as we step up the the abstraction ladder and build more more things to create this smarter blob, which obviously we should hopefully and we do understand how we're building it and why we're building it, that it's going to it's going to become a system that you look at kind of both the the different components of the system, but it's not just going to be just models. There's not going to There's not going to be a thing as like a really great harness that is in absence of a really great model and vice versa.

</details>

**Donne**: 在我们这个非确定性（Non-deterministic）系统主导的领域里，我们始终在一个较低信任的生产环境里构建应用。因此，性能的提升一定会同时发生在模型端和框架端。但不管未来模型自己变得多会协作，在应用调度层也必须存在一个全局的协调器（Controller）。因为没有任何单个模型拥有全知全能的视角。就像互联网诞生了流量路由（Traffic Routing），随着 AI 时代的到来，这种路由智能只会向着更加精细和集中的方向发展。

<details>
<summary>Original English</summary>

**Donne**: Yeah. Makes sense. I think applications, especially as built on non-deterministic systems like models, operate in a very low-trust environment. So yes, most of the improvements will likely be distributed across both models and the harnesses, but I think overall it's it's it's mostly it's There There will There will have to be some form of controller trying to have some form of arbitration because even from the model perspective you aren't in a perfectly visible world. You don't know the behavior of every model, so it's going to be at the orchestration level where you have these kind of things. And this has traditionally been shown by other industries like when web when web launched, you know, you had traffic-based routing. So it's different. But all the sort of routing controls have been centralized over time.

</details>

**主持人**: 听起来，这对于整个行业的未来是一个巨大的好消息。

<details>
<summary>Original English</summary>

**Host**: Makes sense.

</details>

**Alex**: 哈哈，没错。在讨论的最后，我想再次强调缓存优化的决定性力量。同时，如果大家去 OpenRouter 的后台看一看我们公布的脱敏消费统计，你们猜在分类（Classification）这一类明显应该交给便宜小模型的任务上，目前美元消费额最高的模型是哪一个？

答案居然依然是极其昂贵的 Claude 3 Opus。

这说明，尽管我们今天勾勒出了如此美丽的多模型协作与模型路由的蓝图，但对于绝大多数普通开发者而言，如何轻松、稳定地用好小模型，依然存在着极其高昂的认知和工程门槛。这也正是我们在座的所有企业正在努力攻克的万亿级市场。

<details>
<summary>Original English</summary>

**Alex**: I I it's most likely going to be good news in the future. Um and and I I think like caching is a big reason for that. Even if you I think like a to take the flip side of of this argument, um the you know, it might be that in the future we have like one big model that's like, "I know I am the like most efficient at everything and I'm like way more efficient than Haiku. I'll solve every task better than Haiku can at like a lower price. Um why should I ever delegate to Haiku?" There's something like that actually could could be a model that we have in the future. Um but you're always going to have these like, you know, for example, caching. It could be that like you tell the model that this other model like does have the right context in cash and uh you know, the the orchestrator model just always has more context and the models have to be aligned. So, I I think like it's I I don't really see a world where like we wouldn't be able to get models to collaborate really well and and I think they're going to get better over time. Um in part because they're you know, they just have limited memory. So, I I think that's kind of one one deciding factor and another is that um there will be like uh there will continue to be like if you just look at like the the the rankings on OpenRouter, if you look at our our public data and you look at like the top model being used by dollar spent on classification tasks, well, guess what it is. It's Opus. I think there are there are there are big opportunities for like using small models for in distribution easy tasks and the and like as time goes on, that's going to be a larger and larger percentage of tasks relative to like the most valuable tasks that um very smart models spend most of their time on.

</details>

**主持人**: 确实如此。非常感谢各位嘉宾的精彩分享。让我们给台上的各位嘉宾一轮热烈的掌声，谢谢大家！

<details>
<summary>Original English</summary>

**Host**: Totally. Well, I want to thank you guys so much. Can we all give everyone a round of applause? Thank you.

</details>

*(台下掌声雷动，论坛圆满结束。)*