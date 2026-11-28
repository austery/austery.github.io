---
author: Latent Space
date: '2026-02-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=F_1oDPWxpFQ
speaker: Latent Space
tags:
  - model-distillation
  - hardware-software-co-design
  - long-context
  - inference-latency
  - personalized-ai
title: AI 前沿对话：从 Gemini 3、深度推理到 Flash 模型的蒸馏演进 —— 专访 Jeff Dean
summary: Google 首席 AI 科学家 Jeff Dean 深度解析了 Gemini 系列模型的研发策略，重点探讨了模型蒸馏、长上下文处理、软硬件协同设计（TPU）以及 AI 在编码代理方面的未来演进。他强调了低延迟对 AI 交互的重要性，并预测了 10,000 token/秒级别的超高速推理将彻底改变 AI 辅助思考与编程的范式。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Jeff Dean
  - Noam Shazeer
  - Oriol Vinyals
  - Andrew Ng
  - Sergey Brin
companies_orgs:
  - Google
  - DeepMind
  - OpenAI
products_models:
  - Gemini
  - TPU
  - Flash
  - Gemma
  - Waymo
  - Spanner
media_books: []
status: evergreen
---
### 帕累托前沿：能力与效率的平衡

**Alessio**: 欢迎来到 Leading Space 播客。我是来自 Google Kernel Labs 的 Alessio，今天我们非常荣幸能邀请到 Google 首席 AI 科学家 **Jeff Dean**。你的职业生涯堪称传奇，首先要祝贺你们在**帕累托前沿 (Pareto frontier)** 取得的领先地位。

<details>
<summary>Original English</summary>

**Alessio**: Hey everyone, welcome to the Leading Space podcast. This is Alessio from Google Kernel Labs, and I'm joined by Squix, editor of Leading Space. Hello, hello. We're here in the studio with Jeff Dean, chief AI scientist at Google. Welcome. Thank you for having me. It's a bit surreal to have you in the studio. I've watched so many of your talks, and obviously, your career has been super legendary. So, I mean, congrats. I think the first thing must be said: congrats on owning the Pareto frontier.

</details>

**Jeff Dean**: 谢谢。处于帕累托前沿感觉很好。这不仅是单一因素的结果，而是整个技术栈从上到下的结合。我们不仅能制造高性能的大型模型，还能通过软件技术将这些能力**蒸馏 (Distillation)** 到更小、更轻量的模型中，使它们在保持强大能力的同时，具备更高的性价比和更低的延迟。

<details>
<summary>Original English</summary>

**Jeff Dean**: Thank you, thank you. Pareto frontiers are good, and it's good to be out there. Yeah, I mean, I think as you say, it's not just one thing; it's like a whole bunch of things up and down the stack, and you know, all of those really combine to help make you and us able to make highly capable large models, as well as you know, software techniques to get those large model capabilities into much smaller, lighter weight models that are you know much more cost effective and lower latency, but still you know quite capable for their size.

</details>

### 模型蒸馏与 Flash 版本的崛起

**Alessio**: 在 Google 内部，你们是如何权衡追求性能极限与实际大规模部署之间的矛盾的？

<details>
<summary>Original English</summary>

**Alessio**: So, yeah, how how much pressure do you have on like having the lower bound of the Pareto frontier too? ... How do you prioritize frontier versus like we actually need to deploy it if we build it?

</details>

**Jeff Dean**: 我们两者都想要。前沿模型展示了当前技术能达到的最高能力，但我们也需要高效实惠的模型来支持低延迟场景，比如**智能编码 (Agentic coding)**。通过蒸馏技术，我们可以利用前沿模型作为“老师”来训练更精简的模型。现在我们多代 Gemini 的 **Flash** 版本已经能达到甚至超过前几代 Pro 版本的表现。而且，更小的模型可以通过多次训练提升能力，因为它能从大型模型输出的 **Logits**（软标签）中学习，而不仅仅是硬标签。

<details>
<summary>Original English</summary>

**Jeff Dean**: Yeah, I mean, I think we always want to have models that are at the frontier or pushing the frontier because I think that's where you see what capabilities now exist... At the same time, you know, we know those are going to be really useful for a bunch of use cases, but they're going to be a bit slower and a bit more expensive... So I think we like to do both, and also, you know, through distillation, which is a key technique for making the smaller models more capable... for multiple Gemini generations now we've been able to make the sort of flash version of the next generation as good or even substantially better than the previous generations pro.

</details>

### 长上下文与检索的未来

**Alessio**: 现在的基准测试（Benchmark）似乎已经饱和了，比如 **Needle in a Haystack**（大海捞针）。你们内部如何推动团队寻找新目标？

<details>
<summary>Original English</summary>

**Alessio**: Are there any benchmarks or like test sets they use internally because it's almost like the same benchmarks get reported every time... Like, how do you have to keep pushing the team internally to to like this is what we're building towards?

</details>

**Jeff Dean**: 当一个基准测试达到 95% 以上的准确率时，投入的收益就递减了。我们更看重内部的“保留基准测试”，确保训练数据中没有这些内容。关于**长上下文 (Long Context)**，虽然 100 万或 200 万 token 已经很强，但对于“检索”来说，这种单一指标已经饱和。未来的方向是处理更复杂的、多重目标的任务。最终的理想目标是模型能像人类一样“关注整个互联网”，但这无法通过简单的二次方复杂度算法扩展来实现，我们需要算法和系统层面的创新。

<details>
<summary>Original English</summary>

**Jeff Dean**: Yeah, I mean, I think benchmarks... often kind of have a lifespan of utility... Once it hits kind of 95 percent or something, you get very diminishing returns... We have a bunch of held out internal benchmarks that we really look at where we know that wasn't represented in the training data at all... long context is useful, but it's way too short today... I think what you would really want is can I attend to the internet while I answer my question? ... But that's not going to be solved by purely scaling the existing solutions, which are quadratic.

</details>

### 软硬件协同：能耗才是硬道理

**Alessio**: 你曾提出过“每个程序员都该知道的延迟数字”。在 AI 时代，有没有类似的指标？

<details>
<summary>Original English</summary>

**Alessio**: What you know, this you know, mention of latency and and saving things to disk reminds me of one of your classics... latency numbers every programmer should know. ... I've been trying to make numbers every AI programmer should know.

</details>

**Jeff Dean**: 在 AI 模型中，最关键的是**能耗分析**。一次矩阵乘法单元（MMU）的计算成本极低，可能还不到 1 **皮焦耳 (picojoule)**，但在芯片内部搬运数据（从 SRAM 到乘法器）可能需要 1000 皮焦耳。这就是为什么需要 **Batching**（批处理）：如果你花 1000 皮焦耳搬运了一个参数，你最好利用它进行上百次计算，而不是只算一次。这就是为什么我们要在 **TPU** 设计中强调这种规律性的结构和高带宽连接。

<details>
<summary>Original English</summary>

**Jeff Dean**: Yeah, I mean, it's all going to be about energy and how do you make the most energy efficient system? And then moving data from the SRAM on the other side of the chip... can be you know a thousand picojoules. ... So you better make use of that that thing that you moved many many times. So that's where the batch dimension comes in because all of a sudden, you know, if you have a batch of two fifty six or something, that's not so bad, but if you have a batch of one, that's really not good.

</details>

### 统一模型的胜利与“苦涩的教训”

**Alessio**: 以前人们会为特定的几何或数学问题训练专门的模型，但现在 Gemini 似乎通过一个统一的模型就解决了所有问题，包括 **IMO**（国际数学奥林匹克）级别的题目。

<details>
<summary>Original English</summary>

**Alessio**: I'm still not over the fact that a year ago we had AlphaProof and AlphaGeometry... and then this year we were like, \"Screw that, we'll just chuck it into Gemini.\"

</details>

**Jeff Dean**: 这非常符合我的直觉。人类的大脑并没有一个专门的“符号处理区”，而是一种类似神经网络的分布式表征。2013 到 2016 年间，人们还在为每个小问题训练独立模型，但现在**统一模型**的时代已经到来。**通用模型在绝大多数情况下都会击败专用模型**。虽然垂直领域的微调（如医疗或机器人）有其价值，但我认为它们更像是补充特定领域的数据分布，而不是替代基础的推理能力。

<details>
<summary>Original English</summary>

**Jeff Dean**: Yeah, I mean, I think it makes a lot of sense to me because you know humans manipulate symbols, but we probably don't have like a symbolic representation in our heads... I think general models will win out over specialized ones in most cases.

</details>

### Gemini 项目的起源与组织挑战

**Alessio**: 有传闻说 Google 早期因为内部资源碎片化而限制了语言模型的发展，你是如何改变这一点的？

<details>
<summary>Original English</summary>

**Alessio**: We had a previous guest, David Wan... he kind of like blames almost the brain marketplace as like the reason that Google didn't invest enough in language models.

</details>

**Jeff Dean**: 我当时确实写了一份一页纸的备忘录，指出分散资源是非常愚蠢的。当时 Google Research、Brain 和 DeepMind 都在独立研发不同的语言模型和多模态模型。我建议将最优秀的人才和计算资源整合，打造一个从一开始就是多模态的统一模型。这就是 **Gemini** 工作的起源。之所以起这个名字，是因为这两个团队就像“双胞胎 (Twins)”一样走到了一起，同时也致敬了 NASA 的 Gemini 计划——那是通往阿波罗登月计划的关键一步。

<details>
<summary>Original English</summary>

**Jeff Dean**: Yeah, I mean, I think I actually wrote a one page memo saying we were being stupid by fragmenting our resources... I said, this is just stupid. Why don't we combine things and have one effort to train? ... and that was the origin of the Gemini effort. ... I kind of liked that, and then there's also the NASA interpretation...

</details>

### AI 编码代理：50 个“虚拟实习生”

**Alessio**: 作为一名资深程序员，你如何看待现在的 AI 编码工具？

<details>
<summary>Original English</summary>

**Jeff Dean**: Yeah, I mean, first, I think the coding tools are you know getting vastly better... Imagine if you had a team of 50 interns, how would you manage that if they were people? ... I think that is probably within the realm of possibilities that lots of people could have 50 interns.

</details>

**Jeff Dean**: 编码工具正变得越来越强大，你可以把复杂的任务委派给它们。未来的模式可能是每个程序员管理 50 个**虚拟智能体**。这需要你变得非常擅长**清晰地描述规范 (Crisply specifying things)**。以前我们被教育要写清楚规范，但没人当真；现在，如果你不能清晰地描述需求，模型就无法产出高质量代码。好的 Prompt 本质上就是一种高级的行政沟通能力。

<details>
<summary>Original English</summary>

**Jeff Dean**: The better you get at interacting with these models... they will get really good at crisply specifying things rather than leaving things to ambiguity. ... being able to crisply specify what it is you want is going to be really important. Yeah, my my joke is you know good prompting is indistinguishable from sufficiently advanced executive communication.

</details>

### 未来预测：10,000 Token 每秒

**Alessio**: 最后，你对未来有什么大胆的预测吗？

<details>
<summary>Original English</summary>

**Alessio**: Should we ask him for predictions to to go? ... What's something that you're you're not quite happy with yet that you think will get done soon?

</details>

**Jeff Dean**: 我有两点预测：第一，**个性化模型**将变得极其有用。它能合法地访问你所有的邮件、照片和足迹，这种深度定制的能力远超通用模型。第二，硬件的演进将带来**超低延迟**。现在的推理速度大约是每秒 100 token，未来会达到 **10,000 token 每秒**。在那样的速度下，AI 不只是在输出代码，而是在利用大量的 token 进行思维链推理（CoT）。即使它生成了 10,000 token，其中可能只有 1,000 token 是最终代码，另外 9,000 token 都是它深思熟虑的过程。

<details>
<summary>Original English</summary>

**Jeff Dean**: Let me make two predictions... So I think a personalized model that knows you and knows all your state... is going to be incredibly useful. ... When you say much lower latency... we're at let's say 100 now. We can go to the thousands. Is it meaningful to go 10,000s? Yes. ... it may be a thousand tokens of code that with nine thousand tokens of reasoning behind it.

</details>