---
author: Dwarkesh Patel
date: '2026-06-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4pG3SJQPAwk
speaker: Dwarkesh Patel
tags:
  - sample-efficiency
  - data-scaling
  - reinforcement-learning
  - artificial-general-intelligence
title: AI 中心的巨大数据黑洞：揭秘样本效率的百万倍差距
summary: 本文深入探讨了 AI 训练中面临的样本效率瓶颈，对比了人类与模型在数据量、机器人操控及自动驾驶方面的巨大差距，并指出仅仅扩展模型尺寸无法弥补样本效率赤字，最后讨论了如何通过自动化白领工作与 AI 研究来应对这一挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Mercor
  - Surge
  - Waymo
  - Tesla
  - Epoch
products_models:
  - Unitree G1
media_books: []
status: evergreen
---
### 样本效率与合成数据

**德瓦凯什**: 因此，**智能**的一种定义就是**样本效率（Sample Efficiency）**。也就是说，在给定的领域中，你需要多少数据才能流畅且胜任地运行？事实上，在过去几年里，我们在提高训练样本效率方面是否取得了实质性的进展还很不清楚。看起来更像是我们只是急剧地扩大并改善了**数据分布**。AI 变得更好的主要方式是添加更多、更好的数据，并扩大最初开发这些数据所需的计算规模。显而易见，**强化学习（RL）**是实现这一目标的主要方式。你可以把强化学习基本上看作是一种**合成数据生成（Synthetic Data Generation）**，即你将大量的计算资源投入到一个验证器（如果你把大语言模型作为裁判，就是评分标准）上，以便首先找出什么是优质数据。然后，你训练你的模型去预测这些正确的运行轨迹（Rollouts），这与你训练该模型去预测互联网文本中的下一个单词的方式非常相似。

<details>
<summary>Original English</summary>

**Dwarkesh**: So one definition of intelligence is sample efficiency. That is to say, how much data do you need in a given domain to operate fluently and competently? And it's actually not clear that we've made that much progress in training sample efficiency over the last few years. It seems more like we've just dramatically widened and improved the data distribution. The main way that AIs have been getting better is from adding more and better data, and scaling the compute required to develop that data in the first place. Obviously, RL is the main way that this has happened. You can think of RL as basically a kind of synthetic data generation, where you dump a ton of compute against a verifier — or a rubric, if you have an LLM as a judge — in order to find out what the good data is in the first place. And then you train your model to predict these correct rollouts, much in the same way that you might train that model to predict the next word in internet text.

</details>

### 人类专家数据需求

**德瓦凯什**: 为了让这一过程行之有效，模型在最开始必须至少有某种先验概率能够预测出正确的解决方案，这就是为什么在你想让模型最终能够胜任的每一个领域和技能中，你都需要极其庞大的**人类专家轨迹（Human Expert Trajectories）**。这些人类专家数据是多么针对特定任务和定制化，怎么强调都不为过。如果你想获得一些直观的感受，我建议你去看看 **Mercor** 或 **Surge** 网站上的职位描述。里面有招聘 Word 专家的帖子，要求将遗留文档转换为精美的 Word 文件；还有招聘法律专家的帖子，要求撰写真实的并购（M&A）尽职调查报告或证券申报文件；以及招聘管理咨询顾问的帖子，要求撰写模板化的市场研究报告。

<details>
<summary>Original English</summary>

**Dwarkesh**: For this process to work, the model must have at least some prior probability of anticipating the correct solution in the first place, which is why you need mind-stretching amounts of human expert trajectories in every single field and skill that you want the model to eventually be competent in. It's hard to overstate how task-specific and bespoke this human expert data is. If you want some intuition, I recommend checking out the job descriptions on Mercor or Surge's websites. There are listings for Word specialists who will convert legacy documents into polished Word files, and legal experts who will write realistic M&A diligence reports or securities filings, and management consultants who will write up template market research.

</details>

**德瓦凯什**: 而且这不仅在于数据必须如此特定于领域，还在于数据的量必须极其庞大。每一项技能都对应着至少数百名人类专家，他们负责生成示例补全、编写评分标准并解释他们的**思维链（Chain of Thought）**。这就是为什么生产这些专家标签的数据行业，以及这些被精细分类的技能得以凝结的强化学习环境，每年能赚取数十亿美元的收入，并且很快就会达到数百亿美元的原因。

<details>
<summary>Original English</summary>

**Dwarkesh**: And it is not only that the data have to be so domain-specific, but there has to be so much of it. Each skill corresponds to at least hundreds of human experts who are generating example completions, writing rubrics, and explaining their chain of thought. There's a reason that the data industry producing these expert labels, and the RL environments in which these meticulously cataloged skills can congeal, is earning billions a year in revenue, soon to be deca-billions.

</details>

### 模型训练与弗兰肯斯坦怪物

**德瓦凯什**: 现在想象一下，如果你需要上几十年课，由数百名教授同时授课，并完成数百万个练习任务，才能学会如何美化一个 Word 文件。即使是这里的任务数量差异也低估了其中的差距，因为模型必须碾压式地完成数量多得多且难度大得多的任务。一个人类学生可能只会练习一两次教科书上的问题，但在使用 **GRPO（Group Relative Policy Optimization，群体相对策略优化）** 时，这些模型针对每个任务会生成数百到数千个运行轨迹，它们需要这样做来解决**信度分配问题（Credit Assignment Problem）**。看待这些模型的正确方式，并不像是一个学会了你所看到的模型展示的所有不同技能的人类。它更像是一个**弗兰肯斯坦的怪物**，由十亿个精心构建的示例碎片拼接缝合而成。

<details>
<summary>Original English</summary>

**Dwarkesh**: Now imagine if it took a couple decades' worth of courses with hundreds of concurrent professors and millions of practice tasks for you to learn how to polish a Word file. Even the task-count difference here understates the gap, because the models have to grind through their far more numerous tasks, each far harder. Whereas a human student might practice a textbook problem once or twice, with GRPO, these models are generating hundreds to thousands of rollouts per task, and they need to do this to solve the credit assignment problem. The correct way to think about these models is not like a human who has learned all these different skills that you see the models displaying. It's more like a Frankenstein's monster that has been built out of a billion grafts of carefully constructed examples, all sewn together.

</details>

**德瓦凯什**: **Epoch** 最近报告称，开源模型落后于最先进的前沿模型大约四个月。我认为，开源和之前的落后者之所以能够相对容易地追赶到距离前沿仅几个月的水平，原因在于**数据**才是进步的真正驱动力。数据可以很容易地从公开的 API 中提炼出来，而超参数、训练技巧和架构优化则不能。如果是后者驱动了大部分的进步，那么追赶的难度将远远超过我们现在所观察到的情况。

<details>
<summary>Original English</summary>

**Dwarkesh**: Epoch recently reported that open models lag state-of-the-art frontier models by four months. I think the reason it is relatively easy for open source and previous laggards to catch up to within months of the frontier is that data is the real driver of progress. And data can be easily distilled from public APIs, whereas hyperparameters, training tricks, and architectural optimizations cannot. If the latter were driving most of the progress, then catching up would be far harder than we are observing it to be.

</details>

### 庞大的数据黑洞

**德瓦凯什**: 人们很容易忘记这些模型是在多么庞大的数据上进行训练的，以及这些数据比我们人类一生中所看到的要多得多。我们把这些 AI 看作是闪烁着各种能力能力的璀璨星系。但在它们的中心，肉眼看不见却把所有星座紧紧凝聚在一起的，是一个超乎想象的巨大**数据黑洞**。我只想做几个对比来阐明样本效率差距到底有多大。这里有一个对比：如果一个人平均每小时看和听（慷慨地估计）2000个单词，那么从出生到成年，他们会看到大约 2 亿个 Token。而相比之下，这些前沿模型是在大约几十万亿到上百万亿个 Token 上进行训练的。这接近**百万倍的差距**。

<details>
<summary>Original English</summary>

**Dwarkesh**: It is easy to forget how much data these models are trained on, and how much more it is than what we humans see in our lifetimes. We see these AIs as a galaxy glittering with capabilities. But at their center, invisible to the naked eye, holding all the constellations together, is an unimaginably massive black hole of data. I just want to make a couple points of comparison to illustrate just how big the sample-efficiency gap is. Here's one. If a person sees and hears on average, let's say generously, 2,000 words an hour, then between the time they're born and the time they're an adult, they'll see about 200 million tokens. Now, by contrast, these frontier models are trained on somewhere between tens to hundreds of trillions of tokens. That is close to a millionfold difference.

</details>

**德瓦凯什**: 这是另一个对比：如果你愿意，你可以在几个小时内学会遥控操作任何一个类人机器人或机械臂。如果我们能让 AI 学习得同样快，**机器人技术（Robotics）**将会是一个数十万亿美元的产业，你将拥有无穷无尽的 **Unitree G1** 大军在世界上做各种有用的工作。但我们做不到这一点的原因是，我们的 AI 学习效率远远低于我们，即使我们收集了数百万小时的演示数据，这仍然不足以让它们执行复杂的、开放式的任务。最后一个对比：一个青少年只需要大约 20 小时的练习就能学会开车。即使把他们 16 年的成长、理解世界运转方式以及建立物理直觉的经历都算进去，这仍然比 **Waymo** 和 **Tesla** 用来训练其自动驾驶模型的数据量少了三到四个数量级。

<details>
<summary>Original English</summary>

**Dwarkesh**: Here's another point of comparison. If you wanted to, you could learn to teleoperate any random humanoid or robot arm within hours. And if we could get AIs to learn just as fast, robotics would be a deca-trillion-dollar industry, and you'd have an endless army of Unitree G1s doing all kinds of useful work in the world. But the reason we can't do this is that our AIs learn much less efficiently than we do, and even with the millions of hours of demonstrations that we've collected, this is not enough to allow them to perform complex, open-ended tasks. And a final point of comparison: a teenager can learn to drive a car with about 20 hours of practice. And even if we include their 16 years of growing up and understanding how the world works and building physical intuition, that is still three to four orders of magnitude less data than Waymo and Tesla are using to train their self-driving car models.

</details>

### 反对意见解析之一：进化预训练假说

**德瓦凯什**: 现在我想应对人们对这类对比提出的几个常见回应和反对意见。人们会说的一件事是（我想 **Karpathy** 在参加我的播客时也说过），对人类而言，数十亿年的进化基本上相当于对我们进行了**预训练**。因此，当我们把我们一生中看到的如此少的数据，与这些从完全随机初始化开始冷启动的 LLM 必须学习的数据进行比较时，我们是不公平的。我认为这不是思考这个问题的正确方式。我们的**基因组（Genome）**只有 3GB，而且其中只有 1% 到 2% 是编码蛋白质的。根本没有足够的空间来存储进化假定已经预训练好的这个网络的参数。我认为更贴切的类比是，进化找到了正确的**超参数（Hyperparameters）**和正确的**损失函数（Loss Functions）**，而在我们的一生中，我们仍然在从头开始构建大脑中的**大脑连接组（Connectome）**。也就是说，这类似于神经网络本身的权重和参数。

<details>
<summary>Original English</summary>

**Dwarkesh**: Now I want to deal with a couple of common responses and objections that people have to these kinds of comparisons. One thing people will say, and I think Karpathy said this when he came on my podcast, is that for humans, many billions of years of evolution had to go into basically pretraining us. And so we're being unfair when we're comparing how little data we see within our lifetimes to what these cold-started LLMs, which are just starting off with a totally random initialization, have to learn from. I think this is not the right way to think about it. Our genome is only three gigabytes, and only one to two percent of it is protein coding. There is simply not enough space to store the parameters of this network that evolution supposedly pretrained. I think the closer analogy is that evolution found the right hyperparameters and the right loss functions, and that within our lifetime, we are still building up the connectome in our brain from scratch. That is to say, the thing analogous to the weights and parameters of the neural net itself.

</details>

**德瓦凯什**: 即使你同意这种对比，并说：“是的，这些模型为进行预训练而看到的数百亿个 Token 类似于在追赶进化的步伐”，这仍然无法解释为什么你想赋予这些模型的任何新的**边际能力（Marginal Capability）**都需要如此多的数据。一旦你接受了教育，你同样不需要一百个不同的教授来教你如何学习一门新的编程语言。但是这些 AI 即使在预训练之后，仍然需要海量的数据来学习下一个边际技能，以及在此之后的下一个边际技能。

<details>
<summary>Original English</summary>

**Dwarkesh**: And even if you granted this comparison and said, "Yes, the hundreds of trillions of tokens these models see to get pretrained is similar to just catching up to evolution," that still doesn't explain why any new marginal capability that you want to give these models takes so much data. Once you have been educated, again, you don't need a hundred different professors to teach you how to learn a new programming language. But these AIs, even once they're pretrained, still require enormous amounts of data to learn the next marginal skill, and the next marginal skill after that.

</details>

### 反对意见解析之二：多模态与规模扩展限制

**德瓦凯什**: 对这种对比的另一个反对意见是，我们没有把我们一生中看到的**多模态数据（Multimodal Data）**计算在内。如果我们将从出生到成年所看到的所有感官信息都包括在内，那可能是数百亿到数千亿个 Token 的数据。而我对这个反对意见的回应很简单：即使是失明或失聪的人，尽管他们与这部分感官流隔绝，但他们仍然拥有**通用智能（General Intelligence）**。这向我表明，所有这些数十亿的感官 Token 并不真正是让人类变得聪明的关键。事实上，通过手语和阅读进行交流而不是通过听力交流的聋人，他们摄入的语言 Token 可能远远少于我们之前估算的 2 亿个，这表明我们之前计算的百万倍差距甚至可能被低估了。

<details>
<summary>Original English</summary>

**Dwarkesh**: Another objection to this kind of comparison is that we're not including the multimodal data that we're seeing in our lifetimes. So if we include all this sensory information that we see from birth to adulthood, that's probably tens to hundreds of billions of tokens of data. And my response to this objection is simply that blind or deaf people, who are cut off from parts of this sensory stream, still have general intelligence. That suggests to me that all these billions of sensory tokens are not really the thing that is making humans smart. In fact, deaf people who communicate through sign language and reading, and not through hearing, are probably ingesting far less than the 200 million language tokens that we ballparked earlier, which suggests that even the millionfold difference that we calculated earlier might be an understatement.

</details>

**德瓦凯什**: 好的，人们提出的第三个常见反对意见是，我们只是还没有进行足够的**规模扩展（Scaling）**。我们有这些**扩展定律（Scaling Laws）**。它们告诉我们，更大的模型具有更高的样本效率。我们知道，人脑大约有 100 万亿个**突触（Synapses）**，而我们目前的前沿模型大约有 5 万亿个参数。因此，如果我们把这些模型扩大一到两个数量级，也许就能达到人类水平的样本效率。这个反对意见偏离目标的原因其实非常有趣。如果你看一下扩展定律方程的运作方式，它们会告诉你，参数和数据项是独立加到损失函数中的。假设你有一个模型，并且你以计算最优的方式训练了它，然后你说：“我想提高样本效率。我想使用尽可能少的数据，为此我将投入尽可能多的参数。” 拿 **Chinchilla** 扩展定律论文中的常数来看，即使你将参数数量增加到无穷大，也只能将为了保持相同损失所需的数据量减少到原来的十分之一。而人类的样本效率是这些模型的数千到数百万倍。因此，仅仅扩展当前模型的尺寸根本无法弥补这一差距，这确实表明人类完全处于另一条不同的**扩展曲线（Scaling Curve）**上。

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, the third common objection people make is that we just haven't scaled enough. We have these scaling laws. They tell us that bigger models are more sample efficient. The human brain, we know, is about 100 trillion synapses, and we have frontier models that are currently around five trillion parameters. So maybe we could just achieve human-level sample efficiency if we made these models one to two orders of magnitude bigger. The reason this objection is off-mark is actually quite interesting. If you look at the way the scaling-law equations work, they tell you that the parameter and data terms are added to the loss independently. Suppose you have a model, and you've trained it compute-optimally, and you say, "I want to be sample efficient. I want to use as little data as possible, and I'll throw in as many parameters as necessary to make that happen." Take the constants from the Chinchilla scaling-law paper. Even if you increased the number of parameters by infinity, that would only decrease by a factor of ten the amount of data that you need in order to keep the same loss. Humans are somewhere between thousands to millions of times more sample efficient than these models. So scaling the size of current models simply can't make up for that discrepancy, and this really does suggest that humans are on a different scaling curve altogether.

</details>

### 白领工作的自动化转型

**德瓦凯什**: 好，撇开所有这些学术性的对比不谈，你可能会问：我们为什么要在意样本效率？对于各大实验室实现其两个首要目标来说，这真的是必要的吗？这两个目标分别是：第一，**白领工作自动化（Automate White-Collar Work）**；第二，**AI 研究自动化（Automate AI Research）**。实验室在白领工作上所下的赌注是，软件工程师、分析师或会计师需要做的常见任务是普遍存在的，因此，你可以很容易地将它们纳入训练分布中。如果你看一下这些实验室过去几个月的收入曲线，就会发现，即使我们无法复制让人类学习如此特殊的机制，将这些常见任务纳入分布中仍然能带来巨大的价值。而且，训练 AI 来做这些任务可能比训练人类更低效，但那又怎样呢？人类的寿命根本不允许体验这些模型所经历的训练数量和广度。

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, all these nerdy comparisons aside, you might ask: why do we even care about sample efficiency? Is this actually necessary for the labs to achieve the two overarching objectives they have, which are, one, to automate white-collar work, and two, to automate AI research itself? The bet that the labs are making with white-collar work is that the common tasks that a software engineer or analyst or accountant needs to do are common, and as a result, you can bring them into the training distribution quite easily. If you look at the revenue curves of these labs over the last few months, it does suggest that there's an enormous amount of value from bringing into distribution these kinds of common tasks, even if we can't replicate whatever is making human learning so special. And it might be more inefficient to train AIs to do these kinds of tasks than it is to train humans, but so what? Human lifespan simply does not allow for the quantity and the breadth of training that these models experience.

</details>

**德瓦凯什**: 如果你作为一个人，患有某种奇特的学习障碍，必须阅读 GitHub 上的每一个公开仓库才能成为一名合格的软件工程师，那么培养你就完全没有任何意义了。你在教育的早期阶段就得靠领取社会保障金度日了，而且一旦训练完成，你一次也只能在一个项目上工作。但是 AI 可以通过一次性灌注吉瓦级的训练来学习这些技能，并且它们学到的东西可以同时在数十亿个会话中摊销。因此，我们可以在训练它们时表现得极其低效，但仍然能获得极其丰厚的收益。

<details>
<summary>Original English</summary>

**Dwarkesh**: If you, as a human, had some weird learning disability where you needed to read through every public repository on GitHub before you could be a competent software engineer, then it would simply not make sense to train you up. You'd be on Social Security by the early stages of your education, and even once you were trained, you would only be able to work on one project at a time. But AIs can learn these skills by firehosing gigawatts of training at a time, and what they learn can be amortized across billions of sessions at once. So we can be ludicrously inefficient in training them up and still be wildly in the green.

</details>

### 分布外思考与智能爆炸

**德瓦凯什**: 然后是一个问题，即白领员工需要进行多少无法提前训练的**分布外思考（Out-of-Distribution Thinking）**。这更多是关于不同工作本质的问题，而不是关于 AI 研究的问题，而且这也取决于你讨论的是哪种工作。有些工作是如此机械和可预测，以至于我们在现代 AI 时代到来之前很久就能够将它们自动化，例如银行柜员或旅行社代理人。但还有其他一些工作，每天都需要处理与数据分布相去甚远的复杂问题。我认为**软件工程（Software Engineering）**大概就是这样的一项工作。这是 AI 本应首先接管的工作，但我愿意打赌，在 2028 年，对人类软件工程师的整体需求将比现在更大，这在很大程度上要归因于 AI 的互补性输入。

<details>
<summary>Original English</summary>

**Dwarkesh**: And then there's a question of how much out-of-distribution thinking white-collar employees need to do that you simply can't train for in advance. This is more a question about the nature of different jobs than it is a question about AI research, and it also depends on which job you're talking about. Some jobs are so mechanical and predictable that we were able to automate them long before the modern era of AI, for example, bank tellers or travel agents. But there are other jobs that require dealing on a daily basis with problems that are quite distant from the data distribution. I think software engineering is probably one such job. This is the job that AIs are supposed to take first, but I would be willing to bet that there's overall more demand for human software engineers in 2028 than there is right now, largely due to the complementary input of AI.

</details>

**德瓦凯什**: 实验室针对后一类工作的计划是，首先将 AI 研究自动化，然后让自动化的 AI 研究人员来解决样本效率问题。那么问题来了：不具备人类级别样本效率的 AI，是否能够解决阻碍人类般智能和学习的其余研究问题？这是一个非常复杂的问题，我必须在未来一篇更长的博客文章中来探讨。但先稍微透漏一点，我认为目前人们思考**智能爆炸（Intelligence Explosion）**的方式非常笨拙，因为人们要么完全否定 AI 加速 AI 进展的可能性，要么假设在另一端会蹦出某种神明。他们没有仔细推敲，如果经历一段 AI 进展比平时快得多的时期会是什么样子，以及这种情况发生在 LLM 之上、发生在 LLM 所特有的智能类型之上时会是怎样的一番景象。不过我把这个留到下一次。与此同时，如果你想阅读这篇博客文章，或者我写的其他所有博客文章，或者在我撰写未来博客文章时收到提醒，请前往我的网站 **dwarkesh.com** 订阅我的通讯。好了，回头见。

<details>
<summary>Original English</summary>

**Dwarkesh**: The labs' plan for this latter category of jobs is first to automate AI research and then have the automated AI researchers solve the sample-efficiency problem. So then the question is: can AIs, which do not have human-level sample efficiency, nonetheless solve the remaining research problems that stand in the way of human-like intelligence and learning? This is a very complicated question, and I'll have to address it in a much longer future blog post. But just to tease it a bit, I think that the way people currently think about an intelligence explosion is very clumsy, because either people dismiss the possibility of AIs speeding up AI progress altogether, or they assume that some kind of God pops out the other end. They don't reason carefully about what it looks like to have a period where AI progress is much faster than usual, but to have that happen on top of LLMs and the particular kind of intelligence that LLMs are. But I'll save that for next time. In the meantime, if you want to read this blog post, or all the other blog posts I write, or be alerted when I write a future blog post, go sign up for my newsletter at my website, dwarkesh.com. All right, I'll see you later.

</details>