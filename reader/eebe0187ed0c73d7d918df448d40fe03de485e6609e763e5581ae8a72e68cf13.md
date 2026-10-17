---
author: Latent Space
date: '2026-06-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=fpAthTtha8c
speaker: Latent Space
tags:
  - scaling-laws
  - reinforcement-learning
  - evaluation-metrics
  - agi-roadmap
  - autonomous-research
title: 对话 OpenAI 首席研究官 Mark Chen：关于 AGI、o1、评估危机与 Scaling Laws 的深度探讨
summary: 在这期特殊的 Latent Space 烹饪访谈中，OpenAI 首席研究官 Mark Chen 与主持人 Alan 边做韩国豆腐汤边畅谈 AI 前沿。对话涵盖了交易员背景对 AI 研究的独特价值、通过复现经典论文培养研究品味、o1 模型背后的强化学习探索过程、面临饱和的评估标准危机，以及大模型如何从“氛围研究”迈向全自动的端到端研究等核心议题。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Mark Chen
companies_orgs:
  - OpenAI
products_models:
  - o1
  - AlphaGo
media_books: []
status: evergreen
---
### 序幕与马克·扎克伯格的“送汤梗”

**Alan**: 欢迎来到 **Latent Space** 烹饪系列节目。在这里，我们邀请创始人、研究人员来到厨房，让他们边做饭边畅聊。今天我们有一位非常特别的嘉宾，**OpenAI** 的首席研究官 **Mark Chen**。欢迎你，Mark！

<details>
<summary>Original English</summary>

**Alan**: Hey guys, welcome to the Latent Space cooking series where we invite founders and researchers and just let them cook. Today, we have a very special guest, the chief research officer of OpenAI, Mark Chen. Welcome, Mark.

</details>

**Mark Chen**: 谢谢邀请，Alan。

<details>
<summary>Original English</summary>

**Mark Chen**: Thanks for inviting me, Alan.

</details>

**Alan**: 谢谢你能来。首先，我们这个节目的灵感来源于一个传闻——据说**马克·扎克伯格 (Mark Zuckerberg)** 曾亲自做汤来试图挖走 OpenAI 的研究员，而作为回应，你也亲自送汤给你们的研究人员。这是真的吗？真的发生过，并且起作用了吗？

<details>
<summary>Original English</summary>

**Alan**: Yeah, thank you for coming. I mean, to begin, this all started from the inspiration after hearing the story that Mark Zuckerberg would make soup to try to poke researchers and in response, you brought soup to researchers. Is this true? Did this happen? Did it work?

</details>

**Mark Chen**: 哈哈，这绝对是一个真实的故事。我确实给我们的研究员送了汤。我觉得这么做之后，大家的情绪确实稍微平复了一些。最终我们成功守住了阵地，但不得不说，这依然是 AI 竞争狂潮中一个非常有趣的插曲。

<details>
<summary>Original English</summary>

**Mark Chen**: Oh, you know, it's absolutely a true story. And I have brought soup to our own researchers. I think that matters calmed down a little bit. I think we came out on top, but yeah, still a very funny story in the craziness of how AI is involved.

</details>

**Alan**: 你平时经常做饭吗？这是你熟悉的事情吗？

<details>
<summary>Original English</summary>

**Alan**: How often do you cook? Is it something you're familiar with?

</details>

**Mark Chen**: 我其实很享受做饭，但平时没有太多时间做。现在我几乎每个工作日晚上都有工作晚餐。不过也许在实现 **AGI (通用人工智能)** 之后，这会成为我的爱好。我一直开玩笑说，一旦这一切尘埃落定，我打算开个面摊。

<details>
<summary>Original English</summary>

**Mark Chen**: Well, you know, I I do enjoy cooking, but I don't have the luxury of doing that so often. So, I uh usually have a work dinner every night of the week and, you know, maybe post AGI, this is going to be my hobby. I've always joked that I'm going to start a noodle stand once once it's it's all over.

</details>

**Alan**: 哈哈，期待 AGI 之后能看到你的面摊。那看着我们眼前的这些食材，你大概知道我们今天要用这些原料做什么菜了吗？

<details>
<summary>Original English</summary>

**Alan**: Yeah, yeah, you know, post AGI, hopefully that'll, you know, still be there, but great. And I guess looking at what we have in front of us, do you have an idea generally of what we're probably making?

</details>

**Mark Chen**: 也许是韩国豆腐汤？

<details>
<summary>Original English</summary>

**Mark Chen**: Uh Korean tofu soup, maybe?

</details>

**Alan**: 没错，正是如此。正是受到你给研究员送汤那个故事的启发，我们今天决定做一道**韩国海鲜豆腐汤**，我这边会烹饪虾。你准备好开始了吗？

<details>
<summary>Original English</summary>

**Alan**: Yeah, yeah, that's that's generally what it is. So, we inspired off of the story of you, you know, bringing soup to researchers. So, we're making a tofu Korean stew and we have prawns that I'll be cooking. Are you ready to go?

</details>

**Mark Chen**: 准备好了，我们开始吧。

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah, let's do it. Let's do it.

</details>

**Alan**: 好的，第一步我们先把蔬菜分类，然后切好。我们要先把有泥沙的脏的部分切掉，然后把它们理出来。

<details>
<summary>Original English</summary>

**Alan**: Great. Okay, so the first thing we should probably do is we'll separate the veggies and then we can cut them. And basically, what we want to do is just um cut the dirty part off with the dirt and then, yeah, separate that across.

</details>

**Mark Chen**: 明白。

<details>
<summary>Original English</summary>

**Mark Chen**: that I know.

</details>

### 从交易员到 AI 研究员：不走寻常路

**Alan**: 好的，把菜放在那。当你在切菜的时候，我想问问关于你的背景。在进入 AI 领域之前，你曾经是一名**交易员 (Trader)**。甚至 **Sam Altman** 在去年四月也发推特说过，如果你是一名高频交易员，你应该考虑加入 OpenAI 来一起构建 AGI。那么你认为，成为一名交易员和成为一名研究员之间，存在什么隐秘的联系吗？还是说，这纯粹只是因为交易是一个极度依赖技术且竞争激烈的领域，因而吸引了大量优秀的潜在人才？

<details>
<summary>Original English</summary>

**Alan**: Yeah, okay. And then just have that there. So, you can do that. And while that's going, I guess I could ask more about your background. So, in a previous life, you were once a trader. And even Sam, I think, last year in April also tweeted about how if you're a high frequency trader, you should consider joining OpenAI because, you know, build AGI. So, do you think there's a relation between, you know, being a trader and being a researcher, or do you think it's just like a very technical and competitive area where a lot of great employees can come from?

</details>

**Mark Chen**: 我觉得最关键的一点是，在 OpenAI 很多优秀的研究员在开始的时候并没有接受过系统的机器学习或 AI 研究训练。我们非常相信可以从头培养人才。我认为真正难得的能力，是**创造性地解决问题**和打破常规思考的能力，而不是你必须拥有一个博士学位——尽管博士学位确实能带来非常宝贵的技能训练。对于交易员这个职业，我不觉得它有什么太特殊的魔力。我们的团队里有极其优秀的数学家，也有极其优秀的物理学家。

但交易这一行有一点很独特，那就是它是“**不可欺骗的 (unhackable)**”。你无法欺骗现实世界，对吧？这是一个非常硬性的、难以操纵的优化指标。而且这个领域非常注重细节，你必须在细节上做到极致。此外，它涉及对系统的极限优化和压榨。这些精细化调整的思维方式和技能可以无缝迁移到深度学习研究中。

<details>
<summary>Original English</summary>

**Mark Chen**: I think really the most important thing is there are a lot of researchers who just started out without a formal training in machine learning or AI research. Um we've very much believed in training people up to do this. I I think the real hard thing is the ability to creatively solve problems and think outside of the box. It's not so much, you know, you have to do a PhD, even though that does bring a valuable skill set. Um with trading in particular, I mean, I I don't know that it's that special of a profession. Like, I kind of think of it as, you know, we've had great mathematicians join, we already had great, you know, physicists join, but trading is something where, you know, it's like it's very unhackable. You're um how you you can't kind of cheat the real world, right? You know, it's it's a hard metric to optimize. And there's also a lot of characteristics like it's it's a field where attention to detail really matters. And um you know, it's kind of the brutal hard optimization and squeezing out the juice of a system. Um and some of those those skills transfer over.

</details>

**Alan**: 明白。那么对于那些想要进入 AI 研究领域但又没有博士学位的人来说，你认为他们应该通过什么样的方式或步骤去培养自己的**“研究品味” (Research Taste)** 呢？因为对于门外汉来说，“研究品味”听起来非常玄乎和陌生。

<details>
<summary>Original English</summary>

**Alan**: Got you. Yeah, and I guess for people who want to get into research, who let's say don't have a PhD, what do you think are the main attributes or things that they can learn to develop research taste? Because I guess that's the main part of getting into this field that may be very foreign to them.

</details>

**Mark Chen**: 我觉得“研究品味”在某种程度上被夸大了。它确实是需要培养的，但我发现最有效的培养机制其实就是**“复现” (Replication)**。你应该挑出那些你发自内心佩服、非常经典的论文，然后尝试去完全复现它们。

在我的学习历程中，有几个标志性的工作让我印象深刻。比如在 2018 年前后，有像 **ResNet** 还有 **PixelCNN** 这样的经典论文。我通过尝试去完全对齐它们的训练曲线，去拿到跟论文里完全一样的训练损失 (Training Loss) 或困惑度 (Perplexity)，学到了极其丰富的东西。在这个过程中，你会接触到很多细节性的微调技术，这些是作者在论文里不会专门讨论，但你必须深入底层去自己摸索才能学到的。

而真正把我带入这个领域的契机，是 **AlphaGo** 对战李世石。我认为那对很多人来说都是一个转折点，它具有强烈的启发性。当时我动手做的第一个大项目，就是尝试去让一个 **DQN (Deep Q-Network)** 跑通并工作起来。

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah, I mean, I think it's a little bit overrated. It is something you have to develop, but um the best mechanism I've found for developing that is really just replication. So, I think you should take papers that you really look up to and just try to fully replicate it. I like I I think a lot of applications stood out in my my mind. Um you know, back in 2018, there is um you know, like ResNet, there were Pixel CNNs, and I I learned so much just um trying to replicate the training curves exactly, get to the exact amount of, you know, like training loss or perplexity that the papers um hinted towards. You just see a lot of techniques, right, that um people don't really kind of talk about, but you know, once once you dive in a couple of layers deeper, um you learn those techniques. And um yeah, I think really the first thing, too, that got me into the field was when AlphaGo played Lee Sedol. And you know, I think that was a turning point for so many people. And yeah, I mean, it it was it was it was inspirational. And it the the first big project that I I really went after was um can I get a DQN working?

</details>

**Alan**: 确实是这样。我还记得当时看比赛时那种震撼的感觉，尤其是那神秘的**“第37手”**。看着技术从那时一步步走到今天，特别是最近这几年的突破，确实让人惊叹。

<details>
<summary>Original English</summary>

**Alan**: Yeah. Yeah. Yeah, that's true. I think it was move 37 or something like one of the games that was pretty uh insane watching it happen and seeing all that development and seeing also where we have gotten to today, especially with the research.

</details>

**Mark Chen**: 难道现在不也是这样吗？你现在几乎在每个领域都能看到类似的“第37手”。在数学领域、在计算机科学和编程领域。感觉今年初很多人一觉醒来，突然意识到：天呐，**AI智能体 (Agents)** 已经可以胜任我日常的专业工作了。他们发现这些模型已经能够开始处理长程的、有实际商业价值的复杂任务了。

<details>
<summary>Original English</summary>

**Mark Chen**: I mean, isn't it crazy that you're seeing move 37s in almost every field now? It's like there's move 37s in in math, there's uh in computer science and coding. Um I think even yeah, just it feels like a lot of people woke up at the start of this year and were like, man, agents are working in my profession. And um you know, they're they're essentially realizing that these models can just do long horizon meaningful work for them.

</details>

### 主观还是客观？强化学习的边界

**Alan**: 是的，这确实非常令人震撼，我自己在日常工作中也在深度使用它。好了，切完蔬菜，接下来我们来切洋葱，把它切成丁。

我想接着这个话题问，你觉得在未来，有什么类型的工作是**强化学习 (RL)** 很难突破或切入的吗？例如，编程可能是相对容易优化的，因为有非常清晰的上下文，代码运行结果可以通过编译器或运行结果直接反馈。但如果是初级管理咨询顾问的工作，所有的背景信息都极度分散、零碎且没有绝对的对错，这种情况会不会难得多？你如何看待这两种不同的场景？有没有一些特定的框架来评估哪种任务更适合强化学习？

<details>
<summary>Original English</summary>

**Alan**: Yeah, no, that's true. It is it is very impressive to see, like I'm even just using it in my own work. But okay, the next thing we could do is just as simple as cutting the onion. So, what we have to do here is just like dicing it. Do you think um there's jobs that RL maybe will have like a much harder time to kind of break into? So, for example, coding maybe easier since a lot of context is accessible either through the code bases or even the work you're trying to do, but let's say if you're trying to do the job that a junior consultant may do, where all the context is a little scattered, maybe it more difficult. How do you view through like those different scenarios? Is there a way that you kind of assess what can be the right approach?

</details>

**Mark Chen**: 是的，传统上，当面对**主观性 (subjective)** 强于**客观性 (objective)** 的领域时，强化学习确实会遇到很大的阻力。比如**创意写作 (creative writing)**，你可以拿两篇创意写作的文章给两个文学专家看，他们很可能会给出截然相反的评价。

所以在这些难以给出明确、统一评分的领域，强化学习目前最难直接应用和施展拳脚。尽管现在很多研究人员正在尝试开发新的 RL 技术去解决这些模糊场景，但就目前而言，强化学习真正大放异彩的依然是那些存在“**冷酷硬真理**” (cold hard truth) 的领域，比如数学和计算机科学。在这些领域，对就是对，错就是错，你可以通过代码运行或者逻辑定理给出无可辩驳的证明。这也是你看到它迅速腾飞的原因。

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah, I mean, I think it's RL's traditionally had um headwinds when it's come to fields that, you know, it's more um kind of subjective than objective. So, if you kind of think of you know, one one kind of you know, uh example of this is creative writing. Where, you know, you could take two pieces of creative writing and two experts can have wildly different opinions. So, it's these fields where things are hard to grade. Um where you know, RL has the least amount of ability to kind of go and um and directly apply there. I know a lot of people are developing techniques to apply RL in these um these settings, but um for now, it's just where there's cold hard truth, things like math and computer science, where you can prove it correctly or wrong. Um that's where you kind of see it really taking off.

</details>

**Alan**: 这让我想到了如何去评估那些前沿领域。当模型的推理能力变得越来越强大，甚至在数学竞赛（如国际奥林匹克数学竞赛 IMO）的真题上都拿到接近满分或饱和的成绩时，我们该如何去评估**超人类智能 (Superhuman Intelligence)**？当模型强到甚至能解决人类最顶尖的 0.01% 的科学家都觉得困难的问题时，我们该如何突破智能的现有边界？

<details>
<summary>Original English</summary>

**Alan**: Yeah. No, that actually brings up a thought on in terms of evaluating those fields. So, um you know, as models get much much more powerful and even saturate, for example, solving like the IMO questions. Um how do you view evaluating like superhuman intelligence? Like it gets to a point where it's so good at things that even the top what, 0.01% of humans can do, that like, you know, how can we push past that frontier of intelligence?

</details>

**Mark Chen**: 这确实是一件让人感到不可思议的事情。我觉得现在的核心重点在于**与现实世界接轨并产生交互**。过去，当我们思考如何超越单纯的“编程竞赛”这类虚拟指标时，我们选择的一个核心方向是将其引向**真实的科学研究** (real-world research)。我们已经看到，模型开始展现出发现新定理、探索硬科学边界的能力。到今天，大家对模型解决这些极高难度的问题已经不再感到惊讶了。我们几乎已经习以为常地认为，模型不仅能解决难题，还能在不同的陌生学科领域之间建立起深刻而新颖的关联。

所以在当前阶段，**代码协同开发** (coding co-working) 是一个关键试验场，它能够全方位测试模型在**极长上下文** (high-context) 和**长程任务规划** (long-horizon) 场景下的真实表现。

<details>
<summary>Original English</summary>

**Mark Chen**: No, it's kind of it's kind of crazy, and I feel like um a lot of it centers in on in on kind of interfacing with the real world. And um when when we've thought about how to evolve past things like programming contests in the past, um I think a lot of the initial direction we took was you should move it to real-world research, right? And we've seen that the models uh they've gotten a lot better at uh just kind of discovering novel theorems and uh pushing the frontiers of of hard sciences. But even today, right? That's no longer a surprise. I think like you we almost take it for granted now that these these models can solve very very difficult problems. They can make contributions and even kind of draw relationships between um fields that, you know, that are that are that are novel and insightful. So, I think you know, we we think of coding co-working as really a domain for that that tests whether our models can learn in high-context settings and in real-world long-horizon settings.

</details>

### OpenAI 的研发路线图与 o1 背后的坚定信念

**Alan**: 明白了，切完洋葱后，接下来我们开始热锅翻炒蔬菜。我们会用到这个高科技的 Impulse 电磁炉，加热速度非常快，我来把它打开。我们在锅里倒入适量的食用油。

<details>
<summary>Original English</summary>

**Alan**: Got you. Okay. Yeah, that makes sense. And since you're done with all the vegetables, we can now do the next step, which is sauteing it. So, yeah, we can use the impulse stove, which we've seen before and very powerful. Let me just turn it on. Um and yeah, so we'll just saute it with some oil. So, yeah, put the pan in the front burner and then

</details>

**Mark Chen**: 这种电磁炉真的很酷。我倒一些油进去，大约这个量，可以了吗？

<details>
<summary>Original English</summary>

**Mark Chen**: These are cool stoves. Yeah, you can use oil to pour some in. And then, you can also Yeah, just a good dollop. Perfect. And yeah, and then we can turn on the stove. So, just press it. And then, yes, spin the knob. Great. Perfect. And then while that heats up, we can just wait and then add the vegetables.

</details>

**Alan**: 完美。在锅子加热的时候，我们稍等一下就可以把蔬菜放下去了。

我想请教一下关于研究路线图的决策。对于那些广为流传的各种行业论调，比如“预训练已经死去了”或者“语言模型永远无法带领我们实现 AGI”，作为在 OpenAI 领导科研路线的主官，你有哪些与行业共识不同或者不认同的观点？

<details>
<summary>Original English</summary>

**Alan**: But yeah, I guess more so on views for research, are there I guess, you know, commonly accepted ideas that are, you know, you disagree with, whether it be like pre-training is dead or language models will never get us to AGI. I think there's a lot of takes out there that are very ambiguous and obviously haven't proven out yet. And I guess from your perspective as like the research like leading things in OpenAI.

</details>

**Mark Chen**: 我**坚定地相信 Scaling Laws (缩放定律)**，相信指数曲线的力量。因此，我强烈不赞同任何形式的“AI 见顶论”或悲观论调。

关于“预训练已死”这种说法，有趣的是，这种言论往往是在过去一两年，当某些阶段性瓶颈显现时才开始广泛传播的。但在大型语言模型（LLM）的发展史上，每隔一段时间就会有人跳出来宣称发展触及了天花板。确实，每一次我们都会遇到阻碍继续向下的技术壁垒，但我们每次都能找到新的通路——不管是通过更极致的工程优化，还是通过关键的科研洞察，来突破原本以为牢不可破的物理边界。

所以在我看来，接下来的路只是同样叙事的延续：更细致的**研究工程** (research engineering)、更精细的**数据工程** (data engineering) 以及更科学的**模型缩放** (scaling)。这些努力总能解锁模型的下一阶段能力。在过去的进程中，这个定律已经在十个数量级的规模跨度上被反复验证了，没有理由认为它会在接下来的探索中失效。

<details>
<summary>Original English</summary>

**Mark Chen**: I mean, I I firmly believe in exponent being on the exponential and in scaling laws. So, I think any of these bear takes, I fairly strongly disagree with. Um you know, when when it comes to pre-training is dead, I I mean, I think the the funny thing is this narrative only started spreading more widely after, let's say, the last one or two years or so. Right? In many times uh in the history of uh developing LLMs, people have been saying this, right? And you know, um there there've always been some some bottlenecks that people will Well, you can't scale past this because of this bottleneck. Um and we've always found some kind of technique, whether it be better engineering or some new research insight that helps you break past the boundary. And so, I think it's just more and more of the same, right? Like more careful research engineering, more careful data engineering, more careful scaling. And it always unlocks that next ability to scale further. So, I I mean, it's held for, you know, almost 10 orders of magnitude, but there's no reason it should not keep keep holding.

</details>

**Alan**: 的确如此。那在过去这些不断推高边界的科学押注中，有没有什么具体的想法在早期阶段是连内部很多人都认为不可能成功的？

<details>
<summary>Original English</summary>

**Alan**: Yeah, that's a very fair point. I guess on research bets that have helped you scale beyond, were there specific ideas that you can even remember in the early days that everyone was was saying that this is not going to work?

</details>

**Mark Chen**: 让我们引以为傲的 **o1** 推理模型就是一个最典型的例子。o1 是我们向世界展示的重大突破，但它的起步极其艰难。因为在我们研发它的那个时期，整个行业都在享受“预训练 + 简单微调”所带来的红利，那是一个被公认为最平坦、最确定的技术范式。

因此，即使在 OpenAI 内部，也免不了有人会产生疑问：既然现有的机器运转得如此完美，我们为什么还要投入巨大精力去赌一个充满未知的强化学习推理方向？在这个关键时刻，必须归功于 **Jakub Pachocki**、**Ilya Sutskever** 以及团队里许多对这一方向有着极强信念和远见的骨干。正是因为这种坚定的科学信仰，我们才开始倾尽全力推动这个项目，并最终成功调动了全公司的资源，将其确立为我们最核心的基石赌注之一。

<details>
<summary>Original English</summary>

**Mark Chen**: Well, yeah, I mean, I think of reasoning as one of the biggest examples of this. Yeah, and um you know, the the first breakthrough that we launched to the world here was O1, but it wasn't easy to get that off the ground cuz one the world we were back living in back then, it was one where pre-training plus post-training, right? That felt like such a promising paradigm. Um and so, even at a company like OpenAI, you would have people ask naturally, why do something when you have a machine that works? And fundamentally, you know, it's to the credit of you know, Yakub, Ilya, many of the people who really had conviction and vision in the space um that we started pushing on this in earnest. And even then, it took a lot of steering to get the whole company behind this as a as a fundamental bet.

</details>

**Alan**: 明白了。在这个过程中，你作为研究主官，是如何去调动和激励研究员的？因为科研押注往往伴随着高失败率，你必须在团队中建立起强大的信任，让他们知道即使很多尝试都会失败，但只要有几个项目踩中了幂律分布的爆发点，所有的付出就是值得的。

<details>
<summary>Original English</summary>

**Alan**: Got you. And how do you kind of develop that ability to motivate researchers? Cuz I assume that's a big part of you know, taking a lot of bets and some won't pan out, but still building the trust in the team to know that eventually some of these will actually have no power law effects.

</details>

**Mark Chen**: OpenAI 最酷的一点在于它拥有非常纯粹的**“能者治之” (meritocracy)** 科研氛围。在很多时候，我们的研究管理者本身就是过去在科研一线做出过杰出工作的人。所以，当这些在专业领域长期积累了崇高声望的管理者站在一线，对大家说“嘿，我确信这就是未来的方向”时，这种自上而下的引导会极具号召力和说服力，研究员们会非常认真地去权衡和跟进。

但与此同时，我们也保留了强大的**自下而上 (bottom-up)** 的探索通道。我们非常乐意被证明“我们高层想错了”，前提是你能够拿出冷酷、坚实的实验数据和逻辑证据。在我们当前的科研路线图中，有很大一部分核心模块，最初并不是来自高层的意志，而是由基层研究员凭借自身极强的Conviction（信念）默默探索出来，并最终用数据说服了所有人。这种双向流动的机制是公司非常珍贵的活力来源。

<details>
<summary>Original English</summary>

**Mark Chen**: You know, what's what's really cool about OpenAI is um research it feels like a meritocracy. So, um often times the research managers are the people who um do the actual have done the best research in the past. And so I think a lot of steering can come top-down, right? Like if your manager says, "Hey, you know, I'm like really convinced this is the path forward." Um, generally people will take that into heavy consideration, right? It's like, you know, this person who you've respected for their research taste and execution for so long is like now very excited by this idea. Um, it's it's definitely something that uh that that um yeah, you you you people take into account. So, I think there there's good top-down steering. At the same time, you know, I think one really cool thing about OpenAI is um there bottom-up elements. Like we like to be convinced that um uh you know, that we're wrong, right? And and someone can just come with cold, hard evidence. And many things like that have turned into core parts of our research roadmap. Just things that no one was really kind of trying to steer, but some researcher on the ground had a heavy conviction in. Um, and and that's also a really good big delight to see.

</details>

### 计算资源分配与顶级人才甄别

**Alan**: 这太棒了。我最近在你的采访中听到，尽管外面竞争对手和新模型层出不穷，但 OpenAI 内部的核心科研路线图其实一直非常稳定，没有因为外界的动荡而发生大幅度的摇摆。那么，你们是在什么时候、以什么样的机制去主动复盘、调整甚至是未雨绸缪地更新这些路线图的呢？尤其是在周围的一切技术都在以惊人的速度迭代的环境下。

<details>
<summary>Original English</summary>

**Alan**: Yeah, no, absolutely. I heard in a recent interview that you gave that your internal research roadmap hasn't really changed um even through all that we've seen, you know, with model development and even other companies. Yeah. I guess how often do you guys assess that, reassess that, even like act proactively? I assume it's not a lot of reactive, you know, decision-making as like other models come out. But how do you like think through that process, especially as everything around you just continues to get better?

</details>

**Mark Chen**: 没错，高维度的科研路线图必须保持高度的战略定力，因为团队需要一个明确的北极星去落地和深耕。我很庆幸我们在面对诱惑时保持了足够的耐心。但底层的**具体执行细节 (implementation details)** 必然是动态变化的，包括项目优先级、资源的倾斜程度以及具体的工程节奏。

在日常运转中，我们有一些刚性的时间节点来逼着我们进行复盘。最典型的一个节点就是**“计算资源 (Compute) 分配机制”**。我们在管理上的一项核心工作，就是决定如何把昂贵的算力集群拆分并倾注到不同的研究项目中去。在这个节点上，我们会用最严苛的眼光审视每一个申请算力的项目：我们真的把这笔宝贵的财富用在最刀刃、最前沿、最具颠覆性的押注上了吗？

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah, so I think the thing is um the high-level research roadmap should be stable, right? I think people need something to ground in. People need to see a path to what we're building. Um, and I've been very happy that we stayed the course for for a while. But the implementation details can change over time, right? And I think um it's important to kind of like the the sequencing will matter, right? The relative resourcing will matter. And the kind of exact steps on the ground will matter. So, what we do is um I think we have kind of points in time that force us to reconsider these things. So, uh one example is when we do compute. Um, one of the parts of the job is just figuring out how to allocate computer projects. And um it's it's a time to kind of question like are we really putting compute to use and people's use at the highest priority bets?

</details>

**Alan**: 明白。你能进一步阐述你所说的“高维度战略路线图”和“具体执行细节”之间的界限吗？高维度是指像“构建 AGI”这样抽象的口号，还是更具体的一些科学命题？

<details>
<summary>Original English</summary>

**Alan**: Yeah. And I guess could you clarify more what you mean by Oh yeah. Yeah, I was like I'm constantly adding oil. But clarify what you mean by higher level versus like the more implementation detail. Like is high level as general as like AGI? That's like our North Star or is it more like granular than that?

</details>

**Mark Chen**: 它比 AGI 要落地得多。在高维度上，我们的研究版图主要由几个大核心部门支撑：**预训练团队 (Pre-training)**，负责给模型灌输世界知识；**强化学习团队 (RL)**，教导模型如何在知识之上进行逻辑推理和长程思考；以及**对齐与后训练团队 (Alignment & Post-training)**。我们所有的科学假设，都是围绕如何推高这几个核心支柱的物理极限展开的。

至于你提到的项目数量，我之前提到过我们可能会同时评估几百个潜在的研究意向。但我们的核心管理原则是**“极致聚焦”**。为了避免陷入微观管理，我们把计算资源打包成大额的预算，直接授权给各大部门负责人，让他们在三大支柱的方向下，把绝大部分筹码聚焦在 3 到 5 个最核心的重仓项目上，同时保留小部分算力池给到自由度极高的前沿探索。

<details>
<summary>Original English</summary>

**Mark Chen**: Um well yeah, I mean at the very highest level, right? We have an org that focuses on pre-training, right? Which is you know giving models a lot of world knowledge. We focus on RL like teaching the models how to reason with that knowledge, how to chain the little insights together. Yeah. And then finally um alignment and post-training, right? And um we're always looking at both like how to scale the mainline in each of these domains and also new bets that fundamentally unlock either like different scaling properties or more aggressive scaling properties. And so even in that I heard that every one to two months you go through what? Like 300 projects like research projects that could be you know followed through on. Is there a way that you kind of hone that decision making I assume as you like decide what to actually double down on and what not to since I assume there's a lot of talented researchers who provide possible ideas to pursue. So I think really in the spirit of uh focus. So one one narrative you might have heard is you know we're we're really focusing our bets at OpenAI and um we're also trying to do a little bit more uh directive computer allocation as well. So um I don't like micromanaging my managers. I think one important thing is to empower them but to just kind of give compute big [clears throat] swaths of compute to the big bets you want to make. Yeah, yeah, yeah. But but then also give them kind of flexible pools of compute which they can you know freely allocate to things that that they believe in or just kind of a fudge with the the allocations that that we prescribe. So, I think yeah, I I think it's just tying would say like a small number of bets, say three to five bets from each org into the main research roadmap and then really letting the the managers and org leads take things from there.

</details>

**Alan**: 明白。对于那些有潜力的新生代科研人员，在面试或者早期的合作中，你有什么独到的眼光或者“特征信号”来判断这个人有成为顶级 AI 研究员的潜力？还是说，你们依然主要依赖看他们过去发表过的学术成果？

<details>
<summary>Original English</summary>

**Alan**: Got you. Okay, that makes sense. And I guess for rising researchers, so let's say in an interview setting, are there specific tells or ways that you can identify, okay, this person has some, you know, potential of becoming a researcher to impact an org in a specific way or is it like just looking at the previous research that they've done and then that is what heavily dictates whether they can actually continue on?

</details>

**Mark Chen**: 在面试阶段，这其实是一个公认的难题。但当你带过足够多的项目，观察过成百上千个研究员在实际高压环境下的产出后，你会慢慢建立起一种强烈的直觉。在交流中，听他们提出的科学假设、看他们面对未知变量时的推演路径，看他们的**科研直觉** (intuition) 能否与我们脑海中最前沿的技术蓝图产生共振。

但即便如此，最靠得住的筛选依然是**实战表现**。一般在加入公司后的 6 个月到 1 年里，谁拥有最陡峭的成长曲线，谁能解决最棘手的工程阻碍并产生真实影响力，结果会变得一目了然。

此外，顶级人才并不是单一维度的。有些研究员是**“极致的执行者”**，他们能够以超乎常人的速度将一个复杂的想法完美实现并落地；而另一些人则是**“疯狂的构想者”**，他们善于推翻现有框架，从看似荒谬的角度开辟出全新的技术路线。我们需要这两种特质的有机结合。

<details>
<summary>Original English</summary>

**Mark Chen**: Um, it's a hard problem before someone comes to OpenAI. I think that's that's genuinely true. Um, I think for a lot of the best research managers, you know, they work with so many researchers over time where you kind of develop an intuition like you know, the things that they say, the ideas that they bring up. Are are those kind of do they hit hit the same mark or like are they the things that you would be thinking about personally too? And so there's this gut check of like, you know, does their intuition match um the same intuition that you have? Um but it is really hard to tell out of the gate. Usually in, you know, let's say six months to a year, it's pretty clear who who's, you know, has the strongest trajectory and who's going to make a lot of impact. Um, so yeah, honestly um I I think it's a hard problem, but just having seen a lot of people, you know, go through research development at OpenAI, you develop an intuition for you know, who's more peppy in different areas. Yeah. And one thing to kind of like just mention there is not every researcher is the same. I think there's a lot of different types of impact. Yeah. There are the people who just take an idea, it's very clear, and they'll just implement it before anyone else. They're also the people who just come up with the kind of like crazy almost too crazy, but yeah, but somehow not that crazy and and they they really convince you in a in a different way of seeing the world or or or another completely different type of project. So, there's a lot of ways to make an impact.

</details>

**Alan**: 非常有启发性的观点。这让我想到了顶级软件工程师和顶级 AI 研究员的异同。在工程界，大家公认优秀的工程师能够把一个模糊的概念一直推到生产环境中去。但在前沿科学研究中，是不是因为前方的道路完全是黑暗且充满不确定性的，所以研究员更需要具备强大的“品味”来作为路标，而不是仅仅闷头写代码？

<details>
<summary>Original English</summary>

**Alan**: Yeah. No, that's helpful. And so, I guess elaborating on that, would you say there are similarities that you would see between, let's say, like top engineers and top researchers? Like I often hear top engineers, even at like small companies and startups, are ones who can take an iota of an idea all the way to production. I assume in research it's like coming up the idea all the way to how it's delivered to the end user through like the product. Or do you think it's more so they're focusing solely on the research and not considering like the end design, how it's used by the customer?

</details>

**Mark Chen**: 没错，科学研究最迷人也最痛苦的地方就在于，前方的路大多时候是没有路标的。这也就是为什么**“科学品味” (taste)** 在这里变得至关重要，它能帮你选择在面对无数分叉路口时走向哪里。

软件工程通常有一套被时间证明行之有效的架构范式，如果你要搭建一个特定功能的产品，背后的工程学路径和模式是相对清晰的。但在科研中，你不仅要找到那条微弱的通道，你还必须有能力去说服其他人，证明你正在探索的方向是真正值得投资的。因此，优秀的 AI 研究员不仅要有极强的编码实现能力，更需要有能力把底层探索逻辑融入整个团队的核心科研路线图中。

<details>
<summary>Original English</summary>

**Mark Chen**: Well, I yeah, I mean, I guess the thing about research is many times the path forward is unclear. And so, what differentiates researchers is how often they're pointed in the right direction and how like like you say taste, right? I think in engineering there are certain patterns that work. Like, you know, if you want to build a product that looks this way, the engineering principles can be pretty similar. Yeah. But for research, I think the thing that's slightly different is just this ability to you know, have good research taste to convince other people that what you're doing is promising. Um and then, yeah, again, to just kind of integrate it into the core research room. Yeah.

</details>

### 多任务烹饪与评估危机

**Alan**: 好的，蔬菜炒得差不多了，接下来我们要开始多任务并进。我们把水倒入锅里，作为豆腐汤的汤底。同时，我们在旁边的煎锅里烹饪海鲜（虾）。

<details>
<summary>Original English</summary>

**Alan**: Got you. Yeah. Great. Okay, it seems like we're done with the vegetables, so now we have to multitask. Okay. So, we're going to pour some water into our pots to get the base of the soup going. So, in the top right, yeah, here. And then just twisting this off. So, I'm going to pour some here. And you can use some as well. And while we have this simmer, and we'll add the veg, we'll cook our prawns here. Okay.

</details>

**Mark Chen**: 没问题，让我先把这里清理一下。我看你的洋葱和蘑菇已经炒出了漂亮的焦糖色。

<details>
<summary>Original English</summary>

**Mark Chen**: Um Yeah, so let me clean this up real quick. Looks like it's going great so far. I feel like saute got some color on the onions and mushrooms. So, yeah, let's turn this on.

</details>

**Alan**: 谢谢！我想顺着这个场景问一下，你展示出了极其优秀的多任务并行能力。其实对于 AI 模型来说也是一样的，我们不仅希望它能多任务并行，还希望它能在跟人类保持实时流畅对话的同时，在后台默默进行复杂的多线程推理。

但这里有一个极其头疼的科研难题：**评估标准 (Evals)**。在模型的生命周期中，有没有出现过某些时候，大家做“直觉测试 (vibe checks)”觉得模型表现极其惊艳，但在严肃的基准测试 (benchmarks) 上数据却非常难看？反之亦然，有没有可能模型通过了某些高难度测试，但实际体验却像是一个纸老虎？

<details>
<summary>Original English</summary>

**Alan**: I guess one aspect or area that seems very interesting are evals. Um and more specifically, have there been instances where you've seen like through just vibe checks that it was a really good, but on the actual benchmark it like performs very poorly? Or do you think it's like heavily correlated that, you know, if your Sweet Bench Pro is, you know, a high number, then it's like your vibe check on it doing coding tasks is also really, really high?

</details>

**Mark Chen**: 这在行业里其实非常普遍。我们内部管它叫**“基准分刷榜” (bench maxing)**。如果你的训练方法不够科学，模型极其容易对某些特定的测试分布产生严重的过拟合。

这导致它虽然在基准测试上拿到了极其耀眼的高分，但它的泛化能力极差，在面对稍微变形的现实世界任务时就会瞬间崩溃。这里面最致命的核心痛点在于：**行业里真正公认的黄金标准基准测试实在是太稀缺了**。

毫不夸张地说，整个学术界和工业界目前正处于一场深刻的**“评估危机” (evals crisis)** 中。我们从小到大耳熟能详的所有硬核测试，从 SAT、GRE 到高难度的专业资格考试，都已经被前沿大模型刷到接近满分饱和了。我们急需开发全新的、动态的、对抗性的评估体系来测试模型的真正智能极限。

像我们之前开发的 Codex 项目，之所以能够迭代得如此迅速，就是因为我们构建了一套高效的评估工程体系，能够让一位研究员在极短的时间内快速跑完一轮完整的、高质量的逻辑评估。

此外，**大规模部署模型**也是一个极其关键的评估来源。只有当千百万真实用户开始在极度多元、高度具体的真实场景下使用模型时，你才能最清晰地看到它会在什么难度的逻辑节点“掉链子”，它处理复杂任务的真实思维红线究竟在哪里。

<details>
<summary>Original English</summary>

**Mark Chen**: No, no. I mean, I think there is this phenomenon. Um you know, I think internally, I'm not sure if this is a externally used word, but yeah, just like bench maxing, you know? Um yeah, I think I think you can kind of overfit onto certain distributions. Um and it won't be reflective how you how well you generalize, right? Because um I mean, easy ways to do this are, you know, you take a benchmark and you just find like very, very, very similar types of instances to the benchmark and you overtrain on these instances. Um So, I think um beyond that, the the other scary thing in the field is the the number of canonical gold standard benchmarks is low. Yeah. And we really are kind of in an evals crisis, right? Where all the really great uh evals that we we all know like growing up like taking the SAT or those those are all fully saturated. And um we really need to find good new ways to benchmark the models. I think one great thing about tools like Codex is they really enabled the fast iteration of of evals. Like we're able to just kind of have one person just very quickly put together a very high-quality eval. Um another kind of interesting thing of just being able to deploy your models is you can just see them eval as people are doing things with them, right? Um, one of the great things is, you know, in math and coding and software, like you get a sense for like where where they fall over, what the task horizon they can do from from this like general very broad-based deployment. So.

</details>

**Alan**: 非常赞同。现在，我们把虾放入油锅中煎出漂亮的颜色。

我想追问的是，在这个大背景下，你们是如何平衡这两者的？因为如果你们老老实实做泛化，而不去针对基准测试进行特化优化，那么在外界甚至消费者的眼中，你们模型的测试跑分可能会低于那些为了刷榜而过度拟合的竞品，从而得出“你们的模型落后了”的荒谬结论。你如何平衡这种微妙的公关与科学的冲突？

<details>
<summary>Original English</summary>

**Alan**: Yeah, no, that's that's helpful. Now, we'll just add the prawns to the oil and get some color on it. Um. Yeah, and so I guess double-clicking onto that um how do you balance both doing well on these benchmarks but also not, you know, like benchmark maxing as you said. Cuz I assume you want to be most honest and like not kind of cheat the system. But if you have like lower scores, let's say, than a competitor or from other models, to the consumer maybe like, "Wait, your score isn't that great, so the model just probably isn't that good." Like how do you balance both of those dichotomies?

</details>

**Mark Chen**: 我们解决这个问题的方法，是在组织架构上建立明确的**“防线”**。

首先，我们必须在测试集上坚持极其严苛的混合度，并且不断投入专门的团队去从零构建未公开的隐藏测试集。这里面的核心哲学是：**一旦一个评估基准被公开发布到世界上，它作为科学评估的价值就已经开始衰退了。**

其次，我们有意识地将**“评估团队” (Evals Team)** 与**“优化与训练团队” (Training Team)** 进行彻底的物理隔离。评估团队的唯一使命和 KPI，就是去绞尽脑汁构建那些能够把当前最强模型“考倒”的高难度题目。这种内部天然的**对抗性博弈**，能从机制上有效防止训练团队为了指标好看而无意识地去“作弊”刷榜。

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah, I mean, I think the thing is, you just really have to operate over representative mixtures of evals and always investing in creating new evals. And yeah, really just like there's this philosophy of once an eval is out in the world, then it's it's just already not a good eval. And I think one one thing is, also just kind of partnering with external organizations to create evals. So, you know, in in many of the kind of hard math and science evals, we've partnered with external organizations and they've been able to kind of craft gold standards there for us. So, yeah, I think um there's a kind of interesting philosophy of separate the teams that are creating the evals from the teams that are optimizing building, okay. the models themselves. Because that way you don't like coincentivize them, right? Like the the way the evals team can work is they're trying to build evals that are hard for the models. So, there's this inherently adversarial process where you're you're not kind of cheating yourself.

</details>

**Alan**: 这套对抗机制确实设计得非常精妙。那么你和 Jakub 在日常管理中，会亲自参与到评估基准的设计和第三方权威测试机构的挑选过程中吗？

<details>
<summary>Original English</summary>

**Alan**: Yeah. The the incentives are somewhat aligned in the right way between the two teams. Yeah. Yeah. do kind of also contribute and help in the ideation process or even deciding what Evals, you know, you should work with a third party on to develop.

</details>

**Mark Chen**: 我们会深度参与。因为每一项新评估的立项，本质上都对应着我们想要在模型中挖掘和引导的**某种特定新能力 (capability)**。

我们如果发现模型在某些复杂逻辑处理上存在明显的黑盒或者短板，我们就会立刻要求立项一套全新的、精细化的评估集来量化这个短板。把所有人对好考题的认知对齐到同一个标准，本身就是一项非常艰巨且关键的工作。

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah. Yeah. So, I mean, I think a lot of the work that Yacoub and I do also involves just kind of uh steering the direction that Evals go. Yeah. I think we'll notice certain gaps, right? Or certain kind of capabilities um that we want. And every capability on the foot side is an Eval, right? You need some kind of Eval that measures if you elicited exactly what you want and you want it well. So, yeah, I think uh yeah, it's um it's takes a lot of steering and just to get everyone on the same page with Evals is also a lot of tough work.

</details>

### 科学家的幽默与超人类智能的“锯齿状边界”

**Alan**: 明白。说到 Jakub，你在以前的采访里提到过他其实是一个非常幽默的人。你能跟我们分享一两个你们在平时极其紧张的研究对抗中，发生的有趣或者好笑的故事吗？因为你们两人配合得极其默契，这种高效率的科学碰撞对于 OpenAI 维持前沿优势至关重要。

<details>
<summary>Original English</summary>

**Alan**: Yeah. No, that's that's fair. I guess on Yacoub, you said in a previous interview that he's a very funny guy. Do you have any fun stories that maybe you haven't shared about working with him? Cuz you also state that you guys align very well. So, your discussions even on research are very efficient and help a lot when like driving towards the frontier. I guess like on the opposite side of being very funny, are there things that you're

</details>

**Mark Chen**: 哈哈，我想起他昨天刚跟我讲的一个冷笑话，我觉得非常能体现他的黑色幽默。

因为我和他共同分管整个 OpenAI 的科研版图。前几天，有一个基层研究员跑来向 Jakub 抱怨说：“Jakub，我觉得我们现在的处境非常不妙，我们手下就像是带着一整支虽然听话、但脑子不太好使的**‘智商平平的纯执行者大军’**。”

Jakub 听完之后，面无表情地看着他说：“**其实这跟我每天管理公司的处境一模一样。**”

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah. You you asked about like a funny story. Well, he told me this joke yesterday, which I thought was very funny. I mean, in many ways we kind of jointly manage the the research efforts. And you know, apparently some researcher came up to him and was like, you know, um it feels like I now just have an army of, you know, really dumb I O I like formalists. Yeah. And Yacoub was like, that feels like already the situation I'm in. You're like, so uh yeah, no, he's he's just like brutally sarcastic and funny. Yeah.

</details>

**Alan**: 哈哈，这确实是典型的 Jakub 式冷幽默。在高压的工作环境下，能有这样的幽默来调剂确实非常重要。

这让我想到了另一个有趣的科学现象：模型可以在国际奥林匹克信息学竞赛 (IOI) 或奥数中拿到极其惊人的高分，但却可能在人类三岁小孩都能轻松完成的一些常识性日常任务上遭遇滑铁卢。你怎么看待大模型这种奇特的智力分布？

<details>
<summary>Original English</summary>

**Alan**: Yeah, that's great. It's great to have humor in the workplace and it's good to bounce out, especially as you're pushing the frontier on very important work. Um but that also brings to mind one kind of weird scenario of how models can perform very well on, let's say, the IMO or even the I O I, but may struggle with some more mundane tasks that a human can easily do. So, I guess how do you feel about

</details>

**Mark Chen**: 这是一个非常经典的概念，也就是人们常说的**“锯齿状边界” (jagged frontier)**。对模型而言自然而然的逻辑路径，对人类来说往往并不直观；反之亦然。

这很大程度上取决于模型在训练阶段所吞噬的数据结构。例如，**视觉和多模态能力**在人类的生物演化史上经过了千万年的硬件级打磨，对我们来说就像呼吸一样自然。但对模型而言，它必须从零开始在硅基芯片里重建这些高维度的感知网络。

另一个核心差异在于**上下文记忆与自主演进**的能力。人类在完成一项复杂工作后，能够自动总结经验教训，并把这些抽象后的智慧无缝应用到完全不同的未来任务中。这种极其高级的自适应学习能力，是目前大模型普遍欠缺、也是整个 AI 行业正在全力攻克的下一个核心阵地。

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah. Yeah. I mean, ultimately, I think what's intuitive for the models is often not um that intuitive for the humans. Like, uh there's there's a lot made of this jagged frontier analogy where um there's some things that the models just inherently, you know, based on maybe the data it sees or um kind of the the things that we we can teach it more easily, yeah, it's just good at. Um I actually think, you know, a lot of a lot of it boils down to also just context, right? Um the models don't have a lot of context that it can Um vision, of course, is something that's more naturally biologically wired for humans. Um and so, yeah, I think there are there's just certain kind of jagged capabilities that models are better at than humans and vice versa. Um but I also think, you know, context, just um being able to take a single task, learn lessons from it, and apply them to future tasks, um that capability is something that, you know, a lot of people are in AI working towards right now. Um but it's, yeah, very natural for humans.

</details>

**Alan**: 说到上下文，一个显而易见的粗暴解决方法就是拼命拉长**上下文窗口 (Context Window)**，直接塞入几百万 Token。但这似乎会带来所谓的“上下文腐烂 (context rot)”和极高的推理延迟。在真实的工程落地中，我们应该如何优雅地解决长程记忆的问题？

<details>
<summary>Original English</summary>

**Alan**: Yeah. Yeah. And on the context point, um a very low-hanging fruit example that many people will say is just to increase the context window to provide more um examples so the model can perform. But do you think I assume there's more complexity on how to actually enable, since even with a large context window and a lot of context, there could be bloat or even just a lot of like context rot, as people have said. So, how do you go through that process of

</details>

**Mark Chen**: 没错。单纯把上下文窗口拉大，在工程上其实相对简单。但如何让模型在超长文本里保持高精度的检索和长程推理（即**大海捞针 Needle-in-a-Haystack** 测试），才是衡量科研功底的地方。

除了在底层网络架构上进行优化，其实有非常多的工程和算法“捷径”可以走。比如现在很多前沿的编程助手工具，都深度集成了**“信息压缩” (compaction/compression)** 技术。你可以通过对历史对话或工作流状态进行实时的语义摘要和状态压缩，避免每次都把庞大冗余的原始文本塞给模型。这种高效率的上下文管理，比单纯依赖物理层面的长上下文要经济且高效得多。

<details>
<summary>Original English</summary>

**Mark Chen**: Yes, so I mean, I think there's kind of the canonical way you would solve for very long horizon learning, which is, you know, you just naively increase your context window, right? And um I mean, that makes sense. I think there's a difference between implementing long context and implementing long context well, like you said. Um and there is a lot of kind of like needle-in-a-haystack style evaluations to measure that. Um but I do think beyond that, um there are also a lot of, in some sense, like engineering and research shortcuts that you could take. Um so, you like, uh many many coding products today have features like compaction, right? Where um, you can compress kind of either insights or working state and stuff like that, you know, it just shortcuts a lot of the the very brutally difficult and expensive um, primitives that you have to build with just native long context.

</details>

### 喷枪焰色与“全自动科学研究”的未来

**Alan**: 明白了。接下来我们要进行烹饪中最有趣的一步了——利用**火焰喷枪 (Flambé)** 来对虾进行高温炙烤，锁住海鲜的鲜甜，并带出独特的焦香。我先在我的煎锅上演示一遍，这叫“单样本学习” (one-shot learning)。

<details>
<summary>Original English</summary>

**Alan**: Got you. Great. Okay, now we're going to do the fun part. So, um, let's lower the heat a little bit and then add a little bit more oil to the pan. Um, and then we'll torch the the shrimp the prawns to get a little more flavor in there. So, I'll first do it on on my pan to show you what it looks like. One shot learning.

</details>

**Mark Chen**: 哈哈，确实是生动的“单样本学习”。等等，我刚才是不是忘了倒波旁威士忌（作为燃料）？

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah. Yeah, indeed. Wait, I I didn't pour any bourbon.

</details>

**Alan**: 哈哈，没关系。我们倒入大约四分之一杯，然后把火关掉，用喷枪点燃它。

<details>
<summary>Original English</summary>

**Alan**: Okay, wait. So, let's pour like a fourth. Okay. And then pour it in. Heat is off. And then torch it.

</details>

**Mark Chen**: 哇，太炫酷了！我应该也学会了。

<details>
<summary>Original English</summary>

**Mark Chen**: Awesome. Great. Okay, I think I got this.

</details>

**Alan**: 好的，那你来试试你的那一份。倒入半个四分之一杯的量，然后用喷枪开火。

<details>
<summary>Original English</summary>

**Alan**: Okay, yeah. So, do you want to do it your Yeah. So, pour it to like half of the fourth cup and then once you have that, I can give this to you. Great. So, it's off. And then once that's off, you can turn it back on.

</details>

**Mark Chen**: 好的，点火……成了！火光稍微有点小，但确实烧起来了。现在我们可以把火重新打开，把多余的酒精蒸发掉。

<details>
<summary>Original English</summary>

**Mark Chen**: Perfect. Great. So, it's off. And then once that's off, you can turn it back on. Perfect. Okay. And then now, do you want to hold on this and just press this button to fire it up. Yeah. Cool. Yeah, perfect. Great. Okay. I'm burning it. It's a little light, but yeah. Great. And then we can turn on the heat again. And then we'll just cook off the alcohol. Okay. Great. Great. Great. Great. How How are you feeling? You know

</details>

**Alan**: 感觉怎么样？虾基本上已经熟透了。

我们在烹饪的同时，也完成了极其优秀的多线程并进。其实我想顺着这个场景问你：在当前大模型研发的最后冲刺阶段，你认为行业里还剩下多少“低垂的果实 (low-hanging fruit)”？我们是不是必须去赌一些完全没有人走过的全新科学路线，才有可能实现智力的下一次大跃迁？

<details>
<summary>Original English</summary>

**Alan**: Great. Basically there cooking everything. So Okay. Awesome. Yeah, and I guess in terms of research ideas and what to work towards, do you think there's still a lot of low-hanging fruit or ideas that can still be improved a lot through just optimizing small parts of already implemented work or do you think right now there has to be a lot of research that are completely new bets that people take?

</details>

**Mark Chen**: 这真是一个非常深刻的问答。

直觉告诉我，行业里确实还剩下一些全新的重大科学押注，但其总量已经不多了。因为大家都预感到 AGI 时代正在以超乎想象的速度逼近，当前的硅基智能网络已经展现出了极其强悍的泛化潜力。

如果你能够深入推演这背后所带来的终极行业图景，你会得出一个非常震撼的结论：**我们正在无限逼近一个“由 AI 自主进行前沿 AI 科学研究”的临界点。**

让大模型能够实现完全端到端、自我闭环、自适应进化的**“自主科研能力 (self-sustaining research)”**，正是我们在 OpenAI 路线图上为未来设定的最核心、最宏伟的终极目标。

<details>
<summary>Original English</summary>

**Mark Chen**: Um yeah, that's a really great question. I feel like there are new bets, but probably not that many. Yeah, um in some sense like uh hopefully you feel like, you know, AGI is coming soon, right? And um I think everyone sees that these models are getting really capable, and I think if you really imagine the implications of that, we're getting closer and closer to a world where the models can come up with more of the innovation funder out. Yeah, if they can kind of do self-sustaining research, this is one of the big or goals that we've set for for our research work.

</details>

**Alan**: 明白了。也就是说，在那个自我进化的临界点到来之前，剩下的时间窗口其实非常狭窄了。

我听到很多外部科学家表示，为了真正跨越到 AGI，我们至少还需要两到三个基础科学维度的突破，比如实现真正的**持续学习 (continual learning)** 或者是底层架构的根本性重构。你认同这种“范式跨越论”吗？还是你觉得这只是一系列连续的、渐进式的工程演进？

<details>
<summary>Original English</summary>

**Alan**: Yeah. I mean, there've been some researchers who have stated that to get to AGI, we still need, let's say like two or three more breakthroughs, if you like continual learning or some other ideas. Um do you follow that same view perspective, or do you think it's kind of more so like not as drastic as coming up with like three completely different paradigms?

</details>

**Mark Chen**: 我在框架层面上并不完全赞同这种“必须发生巨大范式跃迁”的预设。

对于持续学习这类基础特性，它确实是我们必须解锁并交付的**基础原语 (primitives)** 之一。但为了解决这些特性，我们手头其实积攒了非常多不同维度的备选技术路线。我很难去定义哪些算作是“历史性突破”，哪些仅仅是“伟大的工程优化”。

但可以确定的是，我们在每个关键逻辑短板上都准备了充足的“射门机会” (shots on goal)。根据目前的进展，我对这些科学押注最终能够跑通并落地充满信心。

<details>
<summary>Original English</summary>

**Mark Chen**: Um yeah, I mean, I I don't know. I I don't know if I have that same framing. Like continual learning is a a basic primitive that you have to unlock. Yeah. Uh there's so many different techniques. I I don't know um that yeah, I think, you know, we're we're trying a lot of in the limitations of it. I don't know what would consider as a breakthrough versus not, but I think there clearly many shots on goal, and I I I'm pretty sure they'll work.

</details>

### 统一的单体多模态架构与“氛围研究”

**Alan**: 好的，我们的虾已经全部煎好了，香气非常诱人。现在我们把炒好的蔬菜放入汤锅的水中进行炖煮。

在炖煮的时候，我想请教一个架构哲学问题：我们应该把视觉、音频、视频和文本等所有不同维度的信息，全部塞进同一个**统一的超大模型 (Single Unified Model)** 架构里？还是应该通过设计精细的接口，让各个专门的多模态模型去协同工作？

<details>
<summary>Original English</summary>

**Alan**: Great. Okay. Great. Okay, so the shrimp is basically done. Awesome. Okay. So, do you want to do the flambé thing again to get more color? Let's do it. Yeah. Okay. I'll I'll Turn on the heat a little bit, and then let me get some more oil. Great. Yeah, cuz you want to get like some dark color. I think mine has. And here. Great. And then we can hopefully get another shot. Okay. Perfect. minute. Yeah. Do you want Do you want to go first? Um Okay. Same same amount of beer. Yeah. Same amount. We could hopefully get cuz I think the heat wasn't as Yeah. Okay. I think we put it in. Yeah. I think There we go. Let's press the button. Great. There we go. There it is. It's good texture. Yeah. Indeed. And it's like add some good flavor. Here, let me try it. It'll be good. Yep. Yeah, let's see. Great. All right, let's see what it's going to look like. Ooh. There it is. All right. But we're in the final stretch. Okay. shrimp all cooked. Yep. Some fire. So, now we can kind of Yeah. Cook it off a little bit and then um we should add our veg to the water. I'm impressed by your multitasking abilities. You know, I think that's actually one thing um we need our models to get better at. Like it should just be able to do some thread like this and also just have a conversation with you at the same time. Yeah. Yeah. Yeah. No, I I That also reminds me. Do you think images and audio and video and even text like that should all be one under one model or do you think it'll like break through like specific specialized like audio model or

</details>

**Mark Chen**: 从顶尖前沿研究实验室的研发效率角度来看，**统一单体架构 (one architecture) 具有压倒性的优势。**

人们往往严重低估了在公司内部同时维护、调试和迭代多套完全不同的基础设施底层（Infrastructure Stacks）所带来的灾难性工程内耗和算力浪费。

如果我们把所有 modality（模态）全部收拢到同一套核心架构栈中，那么我们在底层工程优化、分布式训练和基础算法改进上取得的每一次突破，都能自动、瞬间惠及所有模态。所以在 OpenAI，我们有极其强烈的架构偏好，即尽可能把整个帝国的基石维持在极少数甚至是单一的单体架构上。

<details>
<summary>Original English</summary>

**Mark Chen**: Well, yeah. I mean, I think for for a research lab, I think there are a lot of advantages for it to be under one. Um you just have to maintain one infrastructure stack for instance. Um I think the cost of like maintaining and scaling many infrastructure stacks at once. Um I think that's something that you shouldn't underestimate. So, I think there are a lot of benefits to just like you know, you do some core research in in your like in your fundamental stack and that just carries over to whatever modality or whatever thing that you want. So, um I I think there's a strong bias for us to keep it in as as few different archi architectures as possible.

</details>

**Alan**: 这在科研战略上确实是极具远见的决定。

我最近还注意到另一个有趣的行业行话叫**“氛围研究员” (Vibe Researcher)**。我们以前经常开玩笑说很多写代码的人是“氛围程序员 (vibe coders)”，那“氛围研究员”在科学探索中扮演着什么样的角色？它最终的终极演进形态会是什么？它的核心价值是来自于提出伟大假设的“品味”，还是来自于将想法落地的工程执行力？

<details>
<summary>Original English</summary>

**Alan**: Got you. Yeah. Great. No, that that makes a lot of sense. I think like the architecture as well is something that isn't often considered. Yeah. It's very important. But one also term that I've been seeing a lot that you've also kind of mentioned is a vibe researcher. You know, we have vibe coders obviously. Yeah, yeah, yeah, yeah. But I guess on vibe researching, what do you think is like the end state? Do you think the main value out of a vibe researcher is just the research taste of coming up with the right idea or do you think it's more so the execution of going through and following through on the actual research?

</details>

**Mark Chen**: 我们正在极速驶向这样一个时代：前沿的 AI 探索工作正在大踏步向**“高维度协同编排” (orchestration-focused)** 转型。

在过去，研究员需要耗费海量的精力在底层繁琐的代码编写、Debug 环境、分布式算力调度等体力活上。但随着模型推理能力（如 o1）的腾飞，未来的大模型自己就能以极高的质量和效率去搞定底层的执行与编码细节。

因此，研究员的精力将会被极大地解放出来，纯粹聚焦于**“提出伟大的科学假说”和“定义高价值的优化目标”**。这就是为什么我们说“科研品味”将拥有无可替代的黄金价值。因为哪怕在未来，如何教导硅基网络拥有像顶尖科学家一样卓越、深邃的科研 Taste（品味），依然是一个极难攻克的终极课题。

当然，即使在当下，通过让 AI 承担起繁重的工程实现，我们内部的科研迭代速度也已经得到了极其显著的成倍增幅。

<details>
<summary>Original English</summary>

**Mark Chen**: Um yeah, so I I I think we're actually moving towards this world very quickly, right? I think both that OpenAI and our other labs, you're starting to see a lot of the work become mostly orchestration-focused, right? Like the researchers coming up with the ideas and the model's great enough to do the implementation execution by itself. So I think you know, when you when it comes down to like you know, is is the value of coming up with ideas versus execution? Um Yeah, both are still important, but I just feel like there's there's this market shift towards just kind of being able to come up with a lot of ideas and then the model can actually do the the execution and orchestration for you. So I think going to be the future of doing research. Um We also said earlier, you know, like the models don't quite have the taste yet. And um that's why you still need the researchers coming up with the ideas. It's going to be hard to teach the models good taste. We noticed that, but in terms of actually accelerating the research, there's clear tangible benefits already.

</details>

**Alan**: 那么在未来三年内，你认为大模型有希望在“科研品味”这一维度上，真正与人类顶尖的科学家平起平坐，实现全自动的端到端自我科研吗？

<details>
<summary>Original English</summary>

**Alan**: Yeah. Do you think they'll ever be parity in terms of research taste with models?

</details>

**Mark Chen**: 我认为这是完全有可能的。

在我们当前三年的核心技术战略蓝图里，我们的终极终点站，就是一个**模型能够独立、端到端地自我进行完整科学探索**的图景。而如何给模型注入真正的科学审美与品味，让它在面对无限广阔的科学荒原时，能敏锐地嗅出最可能产生颠覆性突破的路线，正是我们当下最核心的攻坚战役之一。

<details>
<summary>Original English</summary>

**Mark Chen**: I think so. I mean, when we look at our kind of three-year roadmap, right? The end goal that we want to reach is one where you know, the the models are just doing end-to-end research and um I think a part of that problem is just being able to have the model come up with good taste. You point at some you know, just generic benchmark or something and it finds the right solutions. Yeah.

</details>

### 容忍失败的艺术与完美的汤成品

**Alan**: 明白了。对于那些最终不幸宣告失败的科研押注，你们在 OpenAI 内部通常会如何进行“死后复盘” (postmortem)？因为在前沿探索中，失败绝对是不可避免的。

<details>
<summary>Original English</summary>

**Alan**: Yeah, no, that's helpful. And in terms of research done by humans at OpenAI, how do you guys go about I guess the postmortem process of let's say a research bet that didn't turn out well? Cuz I assume that a lot of it is taking these, you know, vast bets and some don't turn out well.

</details>

**Mark Chen**: 我可以毫不夸张地说，**对高风险科研失败的极度包容，构成了 OpenAI 最核心的护城河 (Alpha)**。

我们与许多保守的研发机构最本质的区别在于，我们愿意主动承担极高的风险，去赌那些一旦成功就能将人类文明推向下一阶段的宏伟命题。而代价就是，我们必须接受大量的尝试最终会化为泡影。

当一个重仓的押注宣告失败时，最关键的铁律是：**绝对不要自欺欺人。**你必须诚实地面对数据，迅速割肉，而不是为了个人的科学面子强行续命。

但即使项目失败了，我们也要求团队产出极高质量的**“失败总结报告” (write-ups)**。因为在前沿领域，明确证明“此路不通”并给出严密的物理解释，其价值丝毫不亚于一次成功的突破。这能帮全行业避免在同一个错误的泥潭里重复踩坑，省下海量的算力和时间。

<details>
<summary>Original English</summary>

**Mark Chen**: Well, I would say that is a big part of OpenAI's alpha because I think one thing that differentiates us from other labs is we take a lot of high-risk bets. And I think that's what's allowed us to stay at the frontier uh so consistently over time. Um but it also means that some of the bets are not going to pan out. And um a hard corollary of that is when a when a bet doesn't pan out um you have to you know, not delude yourself into thinking that, you know, this is something that will work and and kind of uh disconnect from it. So, I think there are certain calls that you have to make, right? Like uh kind of look back and be like, well, um this was a promising idea at the time, but actually it's less important than we thought, you know, it's uh there's some other approach that works better or, you know, um there's some other kind of some something that we discovered. But I I think many of that much of that work is also very fruitful. So, what we realized is like even sometimes when people fail at um proving out a technique, uh their write-ups are very important important because um they'll kind of a lot it it'll often be a natural idea and you can perhaps save a lot of people from going through the same pain.

</details>

**Alan**: 确实。那么对于一个具体的研究员，如果他连续几次极其宏大的科研押注全都颗粒无收，作为管理者的你，会如何去衡量和平衡？因为即使你主观上非常支持他去冒险，但从公司的整体产出和科学回报率来看，你依然需要他在某个时刻拿出真正有用的科学成果。

<details>
<summary>Original English</summary>

**Alan**: Yeah. Well, that's helpful. Yeah. So, I guess when it comes to this positive view on failure, how do you balance that with, you know, a researcher, let's say, takes a lot of bets, consecutive bets, and none of them pan out? Cuz I assume at a certain point you'd want a researcher to eventually have contributions that are actually beneficial compared to only taking bets that maybe pan out to being not good space.

</details>

**Mark Chen**: 在我的职业生涯中，我确实见过有研究员陷入这种连续失败的低谷中。

但我也亲身经历过好几次非常富有戏剧性的案例：某个研究员经历了长达数年的连续失败，就在他本人以及周围所有人都处于极度沮丧和自我怀疑的边缘时，他突然凭借不懈的积累，砸出了一个统治全行业的**“超级爆款” (mega hit)**。

这种神奇的科学突破在 OpenAI 发生过不止一次。所以作为管理层，我们的核心判断标准是：**他的基础科学假设本身是否是合乎逻辑且科学严谨的？**如果他的假设极其宏大、物理逻辑自洽，只是因为身处极其险峻的科学无人区而导致概率性失败，那我们就应该坚定地继续支持他。因为在幂律分布的科学界，你不需要每次都对，你只需要在关键的战役中赢一次，就足以照亮人类文明的未来。

<details>
<summary>Original English</summary>

**Mark Chen**: Just through experience, I I've definitely seen some people fall into this. Um but I've also had several cases where, you know, like it's just like bet after bet, it doesn't pan out, and just when you're like at the brink of frustration, you have something that's like a mega hit. And um this happened enough, so it really just depends on kind of are are the ideas themselves sound? Uh they could be ambitious, but they still have to be sound. And um there's a certain kind of person who will will just take a lot of those ideas, and it's okay because they're somewhat on the riskier frontier. But, they only have to justify it once in a while for it to make sense, right? It may be like a very trading like kind of lens on the world, but yeah, it's it's just on our expectation, right? Like they they need to add value.

</details>

**Alan**: 极具智慧的回答。好了，我们的豆腐汤现在已经完全炖煮入味，海鲜和蔬菜也完美组装完毕。

最后一步，我们可以尝一下汤的咸淡。如果不够咸，可以加一点酱油；如果偏咸，可以适量补充一点水来中和。让我们来看看这道终极杰作！味道怎么样？

<details>
<summary>Original English</summary>

**Alan**: Yeah, no, that's that's great. Okay, so we're basically assembled, now it's the finishing touches, so you can taste your soup, and then we just add soy sauce if it's not salty enough, and if it's too salty, we can add some water to lower this down. But, let's see our final creation. How is it?

</details>

**Mark Chen**: 味道棒极了！味道非常鲜美。

<details>
<summary>Original English</summary>

**Mark Chen**: It's pretty good. I'll take it. Mine is good.

</details>

**Alan**: 哈哈，那就好。我这一份稍微偏浓了，我需要加一点水，你能把水递给我一下吗？

这次边做饭边聊天的体验感觉怎么样？

<details>
<summary>Original English</summary>

**Alan**: Yeah, mine needs a little bit of water. Could you pass me the water? yeah, absolutely. Great. So, how was that? How did that feel?

</details>

**Mark Chen**: 这对我来说是一次非常生动的“知识蒸馏 (distillation)”过程。很显然在做饭这方面，你比我专业得多。

<details>
<summary>Original English</summary>

**Mark Chen**: Um I think this is a student distillation. Um you're clearly better than I am at this.

</details>

**Alan**: 哪里哪里，你太谦虚了。我觉得你做得非常棒，特别是最后用喷枪炙烤海鲜和搭配棕榈心那几步，香气扑鼻。

我想在最后问一个经典的问题：目前对于 AI 科研的各大细分课题，你认为有哪些是当前被严重**高估 (overrated)** 的？又有哪些是被严重**低估 (underrated)** 的？

<details>
<summary>Original English</summary>

**Alan**: No, no, no. [laughter] I feel like you did a very good job, especially with even with the shrimp and palm hearts. Yeah. Smells great. Wow, okay, that sounds good. I guess just more generally, I'm kind of curious, are there any reason research or topics that you think are right now overrated and underrated? Like what would you categorize under?

</details>

**Mark Chen**: 如果目前外界依然有人抱着“预训练已经死去了”的观点，那我必须说，**“预训练” (pre-training) 依然是被严重低估的**。它还远远没有压榨到物理极限。

另一个被严重低估的领域是：**如何将我们在科学研究中建立的各种基础算法原语，与现实世界中真实、高频、复杂的智能体 (agentic) 实用场景深度结合并闭环。**

你绝对不能关起门来，在完全真空的学术实验室里去构建一切，你必须让技术与现实世界的实体 utility（实用性）产生最真实的碰撞。

<details>
<summary>Original English</summary>

**Mark Chen**: Um Well, I think if you still have a pre-training is dead view of the world, um I think I think uh pre-training is definitely uh yeah, yeah, yeah, not not dead. It's it's um it's underrated. Um Yeah, and honestly, um I think products and kind of thinking about end uses and you know how you tie all the primitives you build in research to you know real agentic use cases in the world. That's also underrated. I think um you really can't just kind of build everything in a vacuum and not connect things to utility.

</details>

**Alan**: 太棒了，我们现在可以正式开动了！我们把汤盛出来。

<details>
<summary>Original English</summary>

**Alan**: Yeah. No, that's great. Yeah. Awesome. I think we are ready to taste. So, do we want to give it a go? Let's do it. We can move this and I think there should be some plating. Yeah, do you want to take this plate over here? Okay. Okay. Shrimp looks great. But everything else is here. Great. And then we could just use these pots. So, we have our shrimp. Yep. Do you want to try it? Cheers. Cheers. Let's see. Maybe a little sweet. That's a little too sweet. Cuz we found a way to make it up.

</details>

**Mark Chen**: 味道很赞，不过稍微有一点点偏甜。不过我很喜欢甜食，所以对我来说非常完美。

<details>
<summary>Original English</summary>

**Mark Chen**: for me. I like sweet things. It's good. Okay, great.

</details>

**Alan**: 哈哈，那就好。Sean，你要不要也过来尝尝我们做的汤？你可以假装自己是一个正在努力争取晋升的研究员。

<details>
<summary>Original English</summary>

**Alan**: Um Sean, do you want to come and taste our truffle soup? That was so good by the way. You guys can't smell it, but um We'll pretend you're a um researcher that's trying to get a promotion.

</details>

**Mark Chen**: 而我是马克（扎克伯格），正在用这碗汤来拼命测试和挽留你。你要用这个勺子来尝尝吗？

<details>
<summary>Original English</summary>

**Mark Chen**: And I'm Zach and he's a you know trying to get you so do you want to grab the spoon over here?

</details>

**Alan**: 这碗汤的品质将直接决定你是否能够通过我们今天的评估。

<details>
<summary>Original English</summary>

**Alan**: soup is really going to sway the decision here. The soup quality of soup. Yeah. Great.

</details>

**Sean**: 哈哈，我来试试。你们这次的艺术创作方向是什么？

<details>
<summary>Original English</summary>

**Sean**: I'll do it. All right. What was the artistic direction here?

</details>

**Mark Chen**: 艺术创作方向吗？我想是“极致的模仿” (mimicry)。我认为模仿本身就是一种非常伟大的艺术。

<details>
<summary>Original English</summary>

**Mark Chen**: Um artistic direction. Well, it was mimicry. I think there's great art in mimicry.

</details>

**Alan**: 没错，我们只是在厨房里“让他们静静地煮” (let them cook)。

<details>
<summary>Original English</summary>

**Alan**: Yeah. Just letting them cook.

</details>

**Sean**: 味道真的太棒了！鲜味和辣味完美地融合在了一起，还有非常浓郁的海鲜风味。

<details>
<summary>Original English</summary>

**Sean**: Mhm. Good. Wow. Yeah. Strong. I mean, I think um one thing I I definitely like like savory and spice that goes together, but then also like the sort of sea seafoodness. Mhm. Um Yeah. Kind of really goes into it.

</details>

**Alan**: 谢谢！那么，由你这位外部的权威评估专家来做客观判定，我们两个人的作品，谁才是今天的赢家？

<details>
<summary>Original English</summary>

**Alan**: Great. Okay. Mine's mine's very dominant. winner or what? No, no, no. You're you're supposed to try it and then No, you do pick a winner. [laughter] Okay. This is like evals? Yes. Yeah. So, it's expensive. External evals. Okay, I got to say

</details>

**Sean**: 哈哈，这就像是进行昂贵的外部评估测试。那我必须客观地说，Alan 做的这一份，水可能加得稍微多了一点点，冲淡了原本浓郁的汤底。因为这个锅子实在太大了。

而 Mark 做的这一碗，味道的浓度和层次感把控得更好。所以我投票给 Mark！

<details>
<summary>Original English</summary>

**Sean**: I feel like there's too much water in this. I think like the the I [laughter] I think it's also a pot. Cuz this is a big pot. Yeah. Wait, okay. Um I I would say I I have to go for this. Okay. Okay. Just like you're our respected guest, but I want to be objective. Of course. Of course. Yes. Yes. Yes. Um and like yeah, the density I think really a flavor really I'll do half water? Half the water? Probably. Okay. That sounds good. I mean I think it's very personal, right? Yeah, I think it's also very personal. Taste, you know, you were mentioning

</details>

**Mark Chen**: 哈哈，客观的评价。多加水确实容易影响浓郁度。做菜的味道确实是非常主观和个性化的体验。

不过 Alan，你平时一定经常下厨吧？

<details>
<summary>Original English</summary>

**Mark Chen**: You do a lot of cooking. Taste. No. No. No. [laughter]

</details>

**Alan**: 哈哈，其实并不经常下厨。我只会做几个非常特定的菜谱，并且每次都要极其严格地按照配方比例来，一旦让我做一点点即兴的改动，我就会彻底手忙脚乱。

<details>
<summary>Original English</summary>

**Alan**: Okay. I know a couple recipes. Um I follow them to the T. I can't Like if you tell me, "Oh, cook something slightly different." I have no idea. I'm completely lost. Right. Right. Yeah. There's busy cooking.

</details>

**Mark Chen**: 没关系，下一次你可以让 ChatGPT 现场教你如何调整配方。

<details>
<summary>Original English</summary>

**Mark Chen**: GPT can tell you.

</details>

**Alan**: 哈哈，老实说，我今天在准备食材的时候，确实好几次偷偷查了 ChatGPT。

不管怎么说，今天非常高兴能邀请你来这里。你一直在用卓越的科学直觉和研究品味带领着整个 AI 行业的边界不断向前。非常期待看到你们未来的新成果。今天玩得开心吗？

<details>
<summary>Original English</summary>

**Alan**: Mhm. Yeah. Yeah. Oh, I I'm not going to lie. I kind of looked up in ChatGPT a couple of times. [laughter] So for you, it's like, "Oh, just as prep." But No worries. But yeah. It was It was great having you. I feel like you're always leading the field with a lot of research taste as well, and it's great seeing your work. So hopefully It was fun.

</details>

**Mark Chen**: 玩的非常开心，谢谢你的邀请，Alan！

<details>
<summary>Original English</summary>

**Mark Chen**: Yeah, a lot of fun. Thank you so much.

</details>