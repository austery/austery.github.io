---
author: Dwarkesh Patel
date: '2026-02-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=n1E9IZfvGMA
speaker: Dwarkesh Patel
tags:
  - ai-scaling
  - agi-timelines
  - economic-diffusion
  - ai-governance
  - model-generalization
title: AI进步的指数级终点与治理挑战：Anthropic CEO Dario Amodei的洞察
summary: Anthropic CEO Dario Amodei深入探讨了AI技术在过去三年中的指数级发展，预测通用人工智能（AGI）将在1-3年内实现，并将其学习过程比作人类进化与学习的混合体。他强调了经济扩散的复杂性、Anthropic负责任的计算扩展策略，以及AI治理在生物恐怖主义、地缘政治和价值观对齐方面的紧迫挑战。Amodei还分享了Anthropic通过内部文化和原则驱动模型对齐的独特方法。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - DeepMind
  - JPMorgan
  - Moderna
  - Gates Foundation
products_models:
  - GPT-1
  - GPT-2
  - GPT-3
  - GPT-4 Turbo
  - Claude Code
  - AlphaGo
  - Dota
  - AlphaStar
  - Gemini
media_books:
  - The Big Blob of Compute Hypothesis
  - The Bitter Lesson
  - The Adolescence of Technology
  - Machines of Loving Grace
status: evergreen
---
### AI 指数级增长

**Dwarkesh**: 我们三年前交谈过。在你看来，过去三年里最大的更新是什么？当时的感觉和现在相比，最大的区别是什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: We talked three years ago. In your view, what has been the biggest update over the last three years? What has been the biggest difference between what it felt like then versus now?

</details>

**Dario**: 广义上讲，底层技术的指数级增长基本符合我的预期。前后可能有一两年的误差。我不知道我是否能准确预测代码能力的具体发展方向。但当我审视这个指数级增长时，它大致符合我的预期：模型从聪明的高中生，进步到聪明的大学生，再到开始胜任博士和专业级别的工作，而在代码领域甚至超越了这一点。前沿领域的发展有些不均衡，但大致符合我的预期。

<details>
<summary>Original English</summary>

**Dario**: Broadly speaking, the exponential of the underlying technology has gone about as I expected it to go. There's plus or minus a year or two here and there. I don't know that I would've predicted the specific direction of code. But when I look at the exponential, it is roughly what I expected in terms of the march of the models from smart high school student to smart college student to beginning to do PhD and professional stuff, and in the case of code reaching beyond that. The frontier is a little bit uneven, but it's roughly what I expected.

</details>

**Dario**: 最令人惊讶的是，公众缺乏对我们离指数级增长终点有多近的认知。对我来说，这绝对是不可思议的——无论是在圈内还是圈外，当人们还在谈论那些陈词滥调、老生常谈的政治热点问题时，我们已经接近指数级增长的终点了。

<details>
<summary>Original English</summary>

**Dario**: What has been the most surprising thing is the lack of public recognition of how close we are to the end of the exponential. To me, it is absolutely wild that you have people — within the bubble and outside the bubble — talking about the same tired, old hot-button political issues, when we are near the end of the exponential.

</details>

### 强化学习与扩展

**Dwarkesh**: 我想了解一下目前的指数级增长是什么样的。三年前我们录制节目时，我问你的第一个问题是：“扩展法则（Scaling Laws）是怎么回事，为什么它会起作用？”我现在也有一个类似的问题，但感觉更复杂了。至少从公众的角度来看，三年前在多个数量级的算力上存在着众所周知的公开趋势，你可以看到损失函数是如何改善的。现在我们有了强化学习（RL）的扩展，但并没有公开的扩展法则。甚至连背后的原理都不清楚。这到底是为了教模型技能？还是为了教元学习？目前的扩展假说是什么？

<details>
<summary>Original English</summary>

**Dwarkesh**: I want to understand what that exponential looks like right now. The first question I asked you when we recorded three years ago was, "what’s up with scaling and why does it work?" I have a similar question now, but it feels more complicated. At least from the public's point of view, three years ago there were well-known public trends across many orders of magnitude of compute where you could see how the loss improves. Now we have RL scaling and there's no publicly known scaling law for it. It's not even clear what the story is. Is this supposed to be teaching the model skills? Is it supposed to be teaching meta-learning? What is the scaling hypothesis at this point?

</details>

**Dario**: 实际上，我的假说和早在 2017 年时一样。我想上次我提到过，但我写过一份名为**《大计算团块假说》**（The Big Blob of Compute Hypothesis）的文档。它并不专门针对语言模型的扩展。我写那篇文章时，**GPT-1** 刚刚发布。那只是众多事物中的一个。在那个年代，还有机器人技术。人们试图将推理作为独立于语言模型的东西来研究，并且在 **OpenAI** 的 **AlphaGo** 和 Dota 中也出现了那种强化学习的扩展。人们还记得 **DeepMind** 的《星际争霸》（StarCraft）AI **AlphaStar**。那是一份更通用的文档。**Rich Sutton** 几年后发表了**《苦涩的教训》**（The Bitter Lesson）。这两个假说基本上是一样的。

<details>
<summary>Original English</summary>

**Dario**: I actually have the same hypothesis I had even all the way back in 2017. I think I talked about it last time, but I wrote a doc called "The Big Blob of Compute Hypothesis". It wasn't about the scaling of language models in particular. When I wrote it GPT-1 had just come out. That was one among many things. Back in those days there was robotics. People tried to work on reasoning as a separate thing from language models, and there was scaling of the kind of RL that happened in AlphaGo and in Dota at OpenAI. People remember StarCraft at DeepMind, AlphaStar. It was written as a more general document. Rich Sutton put out "The Bitter Lesson" a couple years later. The hypothesis is basically the same.

</details>

**Dario**: 它的核心观点是，所有的聪明才智、所有的技术、所有“我们需要一种新方法来做某事”的想法，其实都没那么重要。只有少数几件事是重要的。我想我列出了七件。第一是你拥有多少原始算力。第二是数据的数量。第三是数据的质量和分布。它需要是一个广泛的分布。第四是你训练了多长时间。第五是你需要一个可以无限扩展的目标函数。预训练目标函数就是这样一个目标函数。另一个是强化学习目标函数，它设定一个目标，然后你去实现这个目标。在这其中，有你在数学和编程中看到的客观奖励，也有你在 **RLHF**（基于人类反馈的强化学习）或其高阶版本中看到的更主观的奖励。然后第六和第七点是关于归一化或条件化的，就是获得数值稳定性，以便这个巨大的计算团块能够以层流的方式流动，而不是遇到问题。

<details>
<summary>Original English</summary>

**Dario**: What it says is that all the cleverness, all the techniques, all the "we need a new method to do something", that doesn't matter very much. There are only a few things that matter. I think I listed seven of them. One is how much raw compute you have. The second is the quantity of data. The third is the quality and distribution of data. It needs to be a broad distribution. The fourth is how long you train for. The fifth is that you need an objective function that can scale to the moon. The pre-training objective function is one such objective function. Another is the RL objective function that says you have a goal, you're going to go out and reach the goal. Within that, there's objective rewards like you see in math and coding, and there's more subjective rewards like you see in RLHF or higher-order versions of that. Then the sixth and seventh were things around normalization or conditioning, just getting the numerical stability so that the big blob of compute flows in this laminar way instead of running into problems.

</details>

**Dario**: 这就是那个假说，而且我至今仍然坚持这个假说。我不认为我看到了太多与此不符的情况。预训练的扩展法则是我们在那里看到的一个例子。这些法则一直在延续。现在这已经被广泛报道了，我们对预训练感觉很好。它继续为我们带来收益。发生改变的是，现在我们在强化学习上也看到了同样的情况。我们看到了一个预训练阶段，然后是在此基础上的强化学习阶段。对于强化学习，情况实际上是一样的。甚至其他公司也在他们的一些发布中表示：“我们在数学竞赛（如 **AIME** 等）上训练模型，模型表现的好坏与我们训练它的时间呈对数线性关系。”我们也看到了这一点，而且不仅仅是数学竞赛。这是在各种各样的强化学习任务中。我们在强化学习中看到了与预训练相同的扩展规律。

<details>
<summary>Original English</summary>

**Dario**: That was the hypothesis, and it's a hypothesis I still hold. I don't think I've seen very much that is not in line with it. The pre-training scaling laws were one example of what we see there. Those have continued going. Now it's been widely reported, we feel good about pre-training. It’s continuing to give us gains. What has changed is that now we're also seeing the same thing for RL. We're seeing a pre-training phase and then an RL phase on top of that. With RL, it’s actually just the same. Even other companies have published things in some of their releases that say, "We train the model on math contests — AIME or other things — and how well the model does is log-linear in how long we've trained it." We see that as well, and it's not just math contests. It's a wide variety of RL tasks. We're seeing the same scaling in RL that we saw for pre-training.

</details>

### 学习机制的差异

**Dwarkesh**: 你提到了 Rich Sutton 和《苦涩的教训》。我去年采访了他，他实际上对 LLM（大型语言模型）并不太感冒。我不知道这是否是他的观点，但可以这样转述他的反对意见：真正具备人类学习核心能力的东西，不需要耗费数十亿美元的数据和算力，也不需要这些定制的环境，去学习如何使用 Excel、如何使用 PowerPoint、如何浏览网页。我们必须使用这些强化学习环境来内置这些技能，这一事实暗示我们实际上缺乏一个核心的人类学习算法。所以我们扩展错了东西。这就引出了一个问题。如果我们认为存在某种能够像人类一样即时学习的东西，为什么我们还要做所有这些强化学习的扩展呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: You mentioned Rich Sutton and "The Bitter Lesson". I interviewed him last year, and he's actually very non-LLM-pilled. I don’t know if this is his perspective, but one way to paraphrase his objection is: Something which possesses the true core of human learning would not require all these billions of dollars of data and compute and these bespoke environments, to learn how to use Excel, how to use PowerPoint, how to navigate a web browser. The fact that we have to build in these skills using these RL environments hints that we are actually lacking a core human learning algorithm. So we're scaling the wrong thing. That does raise the question. Why are we doing all this RL scaling if we think there's something that's going to be human-like in its ability to learn on the fly?

</details>

**Dario**: 我认为这把几件应该区别对待的事情混为一谈了。这里确实存在一个真正的谜题，但这可能并不重要。事实上，我猜这可能并不重要。有一件有趣的事情。让我暂时把强化学习放在一边，因为我实际上认为，说强化学习在这个问题上与预训练有任何不同，是一个转移注意力的烟雾弹。如果我们回顾预训练的扩展，在 2017 年 **Alec Radford** 开发 GPT-1 时，情况非常有趣。在 GPT-1 之前的模型是在不能代表广泛文本分布的数据集上训练的。你只有非常标准的语言建模基准测试。GPT-1 本身是在一堆同人小说上训练的，我想应该是这样。那是文学文本，只占你能获取的文本的一小部分。在那个年代，大概是十亿个词左右，所以小数据集代表了你在世界上能看到的相当狭窄的分布。它的泛化能力并不好。如果你在某个同人小说语料库上表现得更好，它并不能很好地泛化到其他任务上。我们有所有这些衡量标准。我们有所有这些衡量它在预测所有其他类型文本方面表现如何的标准。

<details>
<summary>Original English</summary>

**Dario**: I think this puts together several things that should be thought of differently. There is a genuine puzzle here, but it may not matter. In fact, I would guess it probably doesn't matter. There is an interesting thing. Let me take the RL out of it for a second, because I actually think it's a red herring to say that RL is any different from pre-training in this matter. If we look at pre-training scaling, it was very interesting back in 2017 when Alec Radford was doing GPT-1. The models before GPT-1 were trained on datasets that didn't represent a wide distribution of text. You had very standard language modeling benchmarks. GPT-1 itself was trained on a bunch of fanfiction, I think actually. It was literary text, which is a very small fraction of the text you can get. In those days it was like a billion words or something, so small datasets representing a pretty narrow distribution of what you can see in the world. It didn't generalize well. If you did better on some fanfiction corpus, it wouldn't generalize that well to other tasks. We had all these measures. We had all these measures of how well it did at predicting all these other kinds of texts.

</details>

**Dario**: 只有当你在互联网上的所有任务上进行训练时——当你从 **Common Crawl** 这样的地方进行全面的互联网抓取，或者抓取 **Reddit** 中的链接（这就是我们为 **GPT-2** 所做的）时——你才开始获得泛化能力。我认为我们在强化学习上看到了同样的情况。我们首先从简单的强化学习任务开始，比如在数学竞赛上训练，然后转向涉及代码等更广泛的训练。现在我们正在转向许多其他任务。我认为接下来我们将越来越多地获得泛化能力。所以这在某种程度上消除了强化学习与预训练之间的对立。

<details>
<summary>Original English</summary>

**Dario**: It was only when you trained over all the tasks on the internet — when you did a general internet scrape from something like Common Crawl or scraping links in Reddit, which is what we did for GPT-2 — that you started to get generalization. I think we're seeing the same thing on RL. We're starting first with simple RL tasks like training on math competitions, then moving to broader training that involves things like code. Now we're moving to many other tasks. I think then we're going to increasingly get generalization. So that kind of takes out the RL vs. pre-training side of it.

</details>

**Dario**: 但无论哪种方式，都存在一个谜题，那就是在预训练中我们使用了数万亿个 token。人类并没有看过数万亿个词。所以这里确实存在样本效率的差异。这里确实有一些不同的东西。模型从零开始，它们需要更多的训练。但我们也看到，一旦它们被训练好，如果我们给它们一百万的超长上下文——唯一阻碍长上下文的是推理成本——它们在那个上下文中学习和适应的能力非常强。所以我不知道这个问题的完整答案。我认为这里发生了一些事情，预训练不像人类学习的过程，但它介于人类学习的过程和人类进化的过程之间。

<details>
<summary>Original English</summary>

**Dario**: But there is a puzzle either way, which is that in pre-training we use trillions of tokens. Humans don't see trillions of words. So there is an actual sample efficiency difference here. There is actually something different here. The models start from scratch and they need much more training. But we also see that once they're trained, if we give them a long context length of a million — the only thing blocking long context is inference — they're very good at learning and adapting within that context. So I don don't know the full answer to this. I think there's something going on where pre-training is not like the process of humans learning, but it's somewhere between the process of humans learning and the process of human evolution.

</details>

**Dario**: 我们的许多先验知识来自于进化。我们的大脑不仅仅是一块白板。关于这一点已经有整本书的论述。语言模型更像是一块白板。它们实际上是从随机权重开始的，而人类的大脑一开始就有所有这些连接到各种输入和输出的区域。也许我们应该把预训练——以及强化学习——看作是存在于人类进化和人类即时学习之间中间地带的东西。我们应该把模型所做的上下文学习看作是介于人类长期学习和人类短期学习之间的东西。所以存在这样一个层级结构。有进化，有长期学习，有短期学习，还有人类的本能反应。LLM 的各个阶段存在于这个光谱中，但不一定完全在相同的点上。LLM 并没有完全对应人类的某些学习模式，它们落在了这些点之间。这说得通吗？

<details>
<summary>Original English</summary>

**Dario**: We get many of our priors from evolution. Our brain isn't just a blank slate. Whole books have been written about this. The language models are much more like blank slates. They literally start as random weights, whereas the human brain starts with all these regions connected to all these inputs and outputs. Maybe we should think of pre-training — and for that matter, RL as well — as something that exists in the middle space between human evolution and human on-the-spot learning. And we should think of the in-context learning that the models do as something between long-term human learning and short-term human learning. So there's this hierarchy. There’s evolution, there's long-term learning, there's short-term learning, and there's just human reaction. The LLM phases exist along this spectrum, but not necessarily at exactly the same points. There’s no analog to some of the human modes of learning the LLMs are falling in between the points. Does that make sense?

</details>

**Dwarkesh**: 是的，尽管有些事情仍然有点令人困惑。例如，如果类比是这就像进化，所以样本效率不高也没关系，那么如果我们能从上下文学习中获得超级样本高效的智能体，为什么我们还要费力去构建所有这些强化学习环境呢？有些公司的工作似乎是教模型如何使用这个 API，如何使用 Slack，如何使用各种工具。让我困惑的是，如果那种能够即时学习的智能体正在出现或已经出现，为什么还要在这些方面投入这么多精力？

<details>
<summary>Original English</summary>

**Dwarkesh**: Yes, although some things are still a bit confusing. For example, if the analogy is that this is like evolution so it's fine that it's not sample efficient, then if we're going to get super sample-efficient agent from in-context learning, why are we bothering to build all these RL environments? There are companies whose work seems to be teaching models how to use this API, how to use Slack, how to use whatever. It's confusing to me why there's so much emphasis on that if the kind of agent that can just learn on the fly is emerging or has already emerged.

</details>

**Dario**: 我无法代表其他人的侧重点发言。我只能谈谈我们是如何看待这个问题的。目标并不是在强化学习中教给模型所有可能的技能，就像我们在预训练中不这样做一样。在预训练中，我们并不是试图让模型接触到单词组合的所有可能方式。相反，模型在大量数据上进行训练，然后在预训练过程中达到泛化。那是我近距离观察到的从 GPT-1 到 GPT-2 的转变。模型达到了一个临界点。我经历过这样的时刻，我当时想：“哦，是的，你只要给模型一列数字——这是房子的成本，这是房子的平方英尺——模型就能补全模式并进行线性回归。”虽然做得不是很好，但它做到了，而且它以前从未见过完全一样的东西。所以，就我们构建这些强化学习环境而言，目标与五到十年前预训练所做的非常相似。我们试图获取大量数据，不是因为我们想要覆盖特定的文档或特定的技能，而是因为我们想要实现泛化。

<details>
<summary>Original English</summary>

**Dario**: I can't speak for the emphasis of anyone else. I can only talk about how we think about it. The goal is not to teach the model every possible skill within RL, just as we don't do that within pre-training. Within pre-training, we're not trying to expose the model to every possible way that words could be put together. Rather, the model trains on a lot of things and then reaches generalization across pre-training. That was the transition from GPT-1 to GPT-2 that I saw up close. The model reaches a point. I had these moments where I was like, "Oh yeah, you just give the model a list of numbers — this is the cost of the house, this is the square feet of the house — and the model completes the pattern and does linear regression." Not great, but it does it, and it's never seen that exact thing before. So to the extent that we are building these RL environments, the goal is very similar to what was done five or ten years ago with pre-training. We're trying to get a whole bunch of data, not because we want to cover a specific document or a specific skill, but because we want to generalize.

</details>

### AGI 时间表预测

**Dwarkesh**: 我认为你提出的框架显然是有道理的。我们正在朝着 AGI 迈进。目前没有人不同意我们将在本世纪实现 AGI。关键在于你说我们正在接近指数级增长的终点。其他人看到这个会说：“我们从 2012 年开始取得进展，到 2035 年我们将拥有一个类人的智能体。”显然，我们在这些模型中看到了进化所做的事情，或者是人类一生中学习所做的事情。我想了解你看到了什么，让你认为这距离我们只有一年，而不是十年。

<details>
<summary>Original English</summary>

**Dwarkesh**: I think the framework you're laying down obviously makes sense. We're making progress toward AGI. Nobody at this point disagrees we're going to achieve AGI this century. The crux is you say we're hitting the end of the exponential. Somebody else looks at this and says, "We've been making progress since 2012, and by 2035 we'll have a human-like agent." Obviously we’re seeing in these models the kinds of things that evolution did, or that learning within a human lifetime does. I want to understand what you’re seeing that makes you think it's one year away and not ten years away.

</details>

**Dario**: 这里你可以提出两个主张，一个较强，一个较弱。从较弱的主张开始，当我在 2019 年第一次看到这种扩展时，我并不确定。这是一半一半的概率。我觉得我看到了一些东西。我的主张是，这比任何人想象的都要可能得多。也许这有 50% 的几率发生。基于这个基本假设，正如你所说，在十年内我们将达到我所说的“**数据中心里的天才国度**”（country of geniuses in a data center），我对此有 90% 的把握。很难比 90% 更高了，因为世界是如此不可预测。也许不可消除的不确定性让我们停留在 95%，比如你会遇到多家公司内部动荡、台湾遭到入侵、所有晶圆厂被导弹炸毁等情况。

<details>
<summary>Original English</summary>

**Dario**: There are two claims you could make here, one stronger and one weaker. Starting with the weaker claim, when I first saw the scaling back in 2019, I wasn’t sure. This was a 50/50 thing. I thought I saw something. My claim was that this was much more likely than anyone thinks. Maybe there's a 50% chance this happens. On the basic hypothesis of, as you put it, within ten years we'll get to what I call a "country of geniuses in a data center", I'm at 90% on that. It's hard to go much higher than 90% because the world is so unpredictable. Maybe the irreducible uncertainty puts us at 95%, where you get to things like multiple companies having internal turmoil, Taiwan gets invaded, all the fabs get blown up by missiles.

</details>

**Dwarkesh**: 现在你把我们给咒了，Dario。

<details>
<summary>Original English</summary>

**Dwarkesh**: Now you've jinxed us, Dario.

</details>

**Dario**: 你可以构建一个有 5% 概率发生的世界，在那里事情被推迟了十年。还有另外 5% 的情况是，我对可以验证的任务非常有信心。在编程方面，除了那种不可消除的不确定性之外，我认为我们在一两年内就能达到目标。在能够进行端到端编程方面，我们不可能在十年内还达不到。我唯一一点根本性的不确定性，即使在很长的时间尺度上，也是关于那些无法验证的任务：规划火星任务；进行像 CRISPR 这样的基础科学发现；写一部小说。这些任务很难验证。我几乎可以肯定我们有一条可靠的路径可以到达那里，但如果有一点点不确定性，那就是在这里。在十年的时间表上，我有 90% 的把握，这几乎是你所能达到的最高确定性了。我认为说这在 2035 年之前不会发生是疯狂的。在一个理智的世界里，这应该是非主流的观点。

<details>
<summary>Original English</summary>

**Dario**: You could construct a 5% world where things get delayed for ten years. There's another 5% which is that I'm very confident on tasks that can be verified. With coding, except for that irreducible uncertainty, I think we'll be there in one or two years. There's no way we will not be there in ten years in terms of being able to do end-to-end coding. My one little bit of fundamental uncertainty, even on long timescales, is about tasks that aren't verifiable: planning a mission to Mars; doing some fundamental scientific discovery like CRISPR; writing a novel. It’s hard to verify those tasks. I am almost certain we have a reliable path to get there, but if there's a little bit of uncertainty it's there. On the ten-year timeline I'm at 90%, which is about as certain as you can be. I think it's crazy to say that this won't happen by 2035. In some sane world, it would be outside the mainstream.

</details>

**Dwarkesh**: 但对验证的强调向我暗示了，你缺乏对这些模型具备泛化能力的信念。如果你想想人类，我们既擅长那些能获得可验证奖励的事情，也擅长那些无法验证的事情。

<details>
<summary>Original English</summary>

**Dwarkesh**: But the emphasis on verification hints to me a lack of belief that these models are generalized. If you think about humans, we're both good at things for which we get verifiable reward and things for which we don't.

</details>

**Dario**: 不，这就是为什么我几乎可以肯定的原因。我们已经看到了从可验证的事物到不可验证的事物的实质性泛化。我们已经看到了这一点。

<details>
<summary>Original English</summary>

**Dario**: No, this is why I’m almost sure. We already see substantial generalization from things that verify to things that don't. We're already seeing that.

</details>

**Dwarkesh**: 但似乎你强调这是一个光谱，它将区分我们在哪些领域看到了更多进展。这似乎不是人类进步的方式。

<details>
<summary>Original English</summary>

**Dwarkesh**: But it seems like you were emphasizing this as a spectrum which will split apart which domains in which we see more progress. That doesn't seem like how humans get better.

</details>

**Dario**: 我们无法到达那里的世界，是我们只做所有可验证事情的世界。其中许多能力会泛化，但我们并没有完全到达那里。我们并没有完全填满盒子的另一边。这不是一个非黑即白的事情。

<details>
<summary>Original English</summary>

**Dario**: The world in which we don't get there is the world in which we do all the verifiable things. Many of them generalize, but we don't fully get there. We don’t fully color in the other side of the box. It's not a binary thing.

</details>

### 软件工程自动化

**Dwarkesh**: 即使泛化能力很弱，你只能做可验证的领域，我也不清楚在这样一个世界里你是否能自动化软件工程。在某种意义上，你也是“一名软件工程师”，但对你来说，作为一名软件工程师的一部分工作包括撰写关于你宏大愿景的长篇备忘录。我不认为那是软件工程师（SWE）工作的一部分。

<details>
<summary>Original English</summary>

**Dwarkesh**: Even if generalization is weak and you can only do verifiable domains, it's not clear to me you could automate software engineering in such a world. You are "a software engineer" in some sense, but part of being a software engineer for you involves writing long memos about your grand vision. I don’t think that’s part of the job of SWE.

</details>

**Dario**: 那是公司的工作，不是专门针对 SWE 的。

<details>
<summary>Original English</summary>

**Dario**: That's part of the job of the company, not SWE specifically.

</details>

**Dwarkesh**: 但 SWE 确实涉及设计文档和其他类似的事情。

<details>
<summary>Original English</summary>

**Dwarkesh**: But SWE does involve design documents and other things like that.

</details>

**Dario**: 模型已经非常擅长写注释了。再次强调，为了区分两件事，我在这里提出的主张比我实际相信的要弱得多。我们在软件工程方面已经快要到达终点了。

<details>
<summary>Original English</summary>

**Dario**: The models are already pretty good at writing comments. Again, I’m making much weaker claims here than I believe, to distinguish between two things. We're already almost there for software engineering.

</details>

**Dwarkesh**: 用什么标准来衡量？有一个标准是 AI 写了多少行代码。如果你考虑软件工程历史上的其他生产力提升，编译器编写了所有的软件代码。写了多少行代码和生产力提升有多大之间是有区别的。“我们快要到达终点了”意味着……生产力提升有多大，而不仅仅是 AI 写了多少行代码？

<details>
<summary>Original English</summary>

**Dwarkesh**: By what metric? There's one metric which is how many lines of code are written by AI. If you consider other productivity improvements in the history of software engineering, compilers write all the lines of software. There's a difference between how many lines are written and how big the productivity improvement is. "We’re almost there" meaning… How big is the productivity improvement, not just how many lines are written by AI?

</details>

**Dario**: 我实际上在这一点上同意你的看法。我对代码和软件工程做了一系列预测。我认为人们屡次误解了它们。让我展示一下这个光谱。大约八九个月前，我说 AI 模型将在三到六个月内编写 90% 的代码行。这已经发生了，至少在某些地方是这样。它在 **Anthropic** 发生了，在下游使用我们模型的许多人身上也发生了。但这实际上是一个非常弱的标准。人们以为我在说我们将不再需要 90% 的软件工程师。这两者有天壤之别。这个光谱是：90% 的代码由模型编写，100% 的代码由模型编写。这在生产力上是一个巨大的差异。90% 的端到端 SWE 任务——包括编译、设置集群和环境、测试功能、编写备忘录等——由模型完成。今天 100% 的 SWE 任务由模型完成。即使发生这种情况，也不意味着软件工程师会失业。他们可以做新的、更高层次的事情，他们可以进行管理。然后在这个光谱的更远端，对 SWE 的需求减少 90%，我认为这将会发生，但这是一个渐进的光谱。我在**《技术的青春期》**（The Adolescence of Technology）中写过这个问题，在那里我用农业的例子梳理了这种光谱。

<details>
<summary>Original English</summary>

**Dario**: I actually agree with you on this. I've made a series of predictions on code and software engineering. I think people have repeatedly misunderstood them. Let me lay out the spectrum. About eight or nine months ago, I said the AI model will be writing 90% of the lines of code in three to six months. That happened, at least at some places. It happened at Anthropic, happened with many people downstream using our models. But that's actually a very weak criterion. People thought I was saying that we won't need 90% of the software engineers. Those things are worlds apart. The spectrum is: 90% of code is written by the model, 100% of code is written by the model. That's a big difference in productivity. 90% of the end-to-end SWE tasks — including things like compiling, setting up clusters and environments, testing features, writing memos — are done by the models. 100% of today's SWE tasks are done by the models. Even when that happens, it doesn't mean software engineers are out of a job. There are new higher-level things they can do, where they can manage. Then further down the spectrum, there's 90% less demand for SWEs, which I think will happen but this is a spectrum. I wrote about it in "The Adolescence of Technology" where I went through this kind of spectrum with farming.

</details>

### 经济扩散的速度

**Dwarkesh**: 我实际上完全同意你这一点。这些基准测试彼此之间非常不同，但我们正在以极快的速度跨越它们。你愿景的一部分是，从 90 到 100 的转变将会发生得很快，并且它会带来巨大的生产力提升。但我注意到，即使在全新项目中，人们开始使用 **Claude Code** 或类似工具，人们报告说启动了很多项目……我们在现实世界中看到软件的复兴了吗？看到所有这些原本不会存在的新功能了吗？至少到目前为止，我们似乎还没有看到。所以这确实让我感到疑惑。即使我永远不需要干预 Claude Code，世界也是复杂的。工作是复杂的。在自包含系统上形成闭环，无论是仅仅编写软件还是其他什么，仅仅从中我们能看到多大的更广泛的收益？也许这应该会降低我们对“天才国度”的估计。

<details>
<summary>Original English</summary>

**Dwarkesh**: I actually totally agree with you on that. These are very different benchmarks from each other, but we're proceeding through them super fast. Part of your vision is that going from 90 to 100 is going to happen fast, and that it leads to huge productivity improvements. But what I notice is that even in greenfield projects people start with Claude Code or something, people report starting a lot of projects… Do we see in the world out there a renaissance of software, all these new features that wouldn't exist otherwise? At least so far, it doesn't seem like we see that. So that does make me wonder. Even if I never had to intervene with Claude Code, the world is complicated. Jobs are complicated. Closing the loop on self-contained systems, whether it’s just writing software or something, how much broader gains would we see just from that? Maybe that should dilute our estimation of the "country of geniuses".

</details>

**Dario**: 我一方面同意你的观点，这是这些事情不会瞬间发生的原因，但同时，我认为效果会非常快。你可能会有这两个极端。一个是 AI 不会取得进展。它很慢。它需要永远的时间才能在经济中扩散。经济扩散已经成为这些流行语之一，用来解释为什么我们不会取得 AI 进展，或者为什么 AI 进展并不重要。另一个极端是我们将获得递归自我改进，以及随之而来的一切。难道你不能在曲线上画一条指数线吗？在获得递归能力后的多少纳秒内，我们将会在太阳周围建起戴森球。我在这里完全是在夸张地描述这种观点，但确实存在这两个极端。但我们从一开始就看到的，至少如果你看看 Anthropic 内部，我们看到了这种不可思议的收入每年增长 10 倍的情况。所以在 2023 年，是从零到 1 亿美元。在 2024 年，是从 1 亿美元到 10 亿美元。在 2025 年，是从 10 亿美元到 90-100 亿美元。

<details>
<summary>Original English</summary>

**Dario**: I simultaneously agree with you that it's a reason why these things don't happen instantly, but at the same time, I think the effect is gonna be very fast. You could have these two poles. One is that AI is not going to make progress. It's slow. It's going to take forever to diffuse within the economy. Economic diffusion has become one of these buzzwords that's a reason why we're not going to make AI progress, or why AI progress doesn't matter. The other axis is that we'll get recursive self-improvement, the whole thing. Can't you just draw an exponential line on the curve? We're going to have Dyson spheres around the sun so many nanoseconds after we get recursive. I'm completely caricaturing the view here, but there are these two extremes. But what we've seen from the beginning, at least if you look within Anthropic, there's this bizarre 10x per year growth in revenue that we've seen. So in 2023, it was zero to $100 million. In 2024, it was $100 million to $1 billion. In 2025, it was $1 billion to $ 9-10 billion.

</details>

**Dwarkesh**: 你们其实应该自己买十亿美元自己的产品，这样你们就可以……

<details>
<summary>Original English</summary>

**Dwarkesh**: You guys should have just bought a billion dollars of your own products so you could just…

</details>

**Dario**: 而在今年的第一个月，那个指数曲线是……你可能会认为它会放缓，但我们在 1 月份又增加了几十亿的收入。显然，这条曲线不可能永远持续下去。GDP 只有那么大。我甚至猜测它今年会有所弯曲，但那是一条非常陡峭的曲线。那真的是一条非常陡峭的曲线。我敢打赌，即使规模扩大到整个经济，它也会保持相当快的速度。所以我认为我们应该考虑这个中间世界，在这个世界里，事情发展得非常快，但不是瞬间的，它们需要时间，因为经济扩散，因为需要形成闭环。因为它很繁琐：“我必须在我的企业内部进行变更管理……我设置了这个，但我必须更改它的安全权限才能让它真正运作……我有一个旧的软件，在模型编译和发布之前检查它，我必须重写它。是的，模型可以做到这一点，但我必须告诉模型去做。这需要时间。”所以我认为到目前为止我们看到的一切都符合这样一种观点：有一个快速的指数级增长是模型的能力。然后还有另一个快速的指数级增长是其下游，即模型在经济中的扩散。不是瞬间的，也不慢，比任何以前的技术都要快得多，但它有其局限性。当我审视 Anthropic 内部，当我审视我们的客户时：采用速度很快，但不是无限快。

<details>
<summary>Original English</summary>

**Dario**: And the first month of this year, that exponential is... You would think it would slow down, but we added another few billion to revenue in January. Obviously that curve can't go on forever. The GDP is only so large. I would even guess that it bends somewhat this year, but that is a fast curve. That's a really fast curve. I would bet it stays pretty fast even as the scale goes to the entire economy. So I think we should be thinking about this middle world where things are extremely fast, but not instant, where they take time because of economic diffusion, because of the need to close the loop. Because it's fiddly: "I have to do change management within my enterprise… I set this up, but I have to change the security permissions on this in order to make it actually work… I had this old piece of software that checks the model before it's compiled and released and I have to rewrite it. Yes, the model can do that, but I have to tell the model to do that. It has to take time to do that." So I think everything we've seen so far is compatible with the idea that there's one fast exponential that's the capability of the model. Then there's another fast exponential that's downstream of that, which is the diffusion of the model into the economy. Not instant, not slow, much faster than any previous technology, but it has its limits. When I look inside Anthropic, when I look at our customers: fast adoption, but not infinitely fast.

</details>

**Dwarkesh**: 我能对你抛个犀利的观点吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Can I try a hot take on you?

</details>

**Dario**: 说吧。

<details>
<summary>Original English</summary>

**Dario**: Yeah.

</details>

**Dwarkesh**: 我觉得“扩散”是人们找的一个借口。当模型无法做某事时，他们就会说，“哦，但这是一个扩散问题。”但你应该用人类来做比较。你会认为，AI 固有的优势会使得新 AI 的入职扩散比新人类的入职要容易得多。AI 可以在几分钟内阅读你整个 Slack 和云盘的内容。它们可以分享同一个实例的其他副本所拥有的所有知识。你在雇佣 AI 时没有这种逆向选择问题，所以你只需雇佣经过验证的 AI 模型的副本。雇佣人类要麻烦得多。人们一直在雇佣人类。我们支付给人类高达 50 万亿美元的工资，因为他们有用，尽管原则上将 AI 整合到经济中比雇佣人类要容易得多。扩散并不能真正解释这个问题。

<details>
<summary>Original English</summary>

**Dwarkesh**: I feel like diffusion is cope that people say. When the model isn't able to do something, they're like, "oh, but it's a diffusion issue." But then you should use the comparison to humans. You would think that the inherent advantages that AIs have would make diffusion a much easier problem for new AIs getting onboarded than new humans getting onboarded. An AI can read your entire Slack and your drive in minutes. They can share all the knowledge that the other copies of the same instance have. You don't have this adverse selection problem when you're hiring AI, so you can just hire copies of a vetted AI model. Hiring a human is so much more of a hassle. People hire humans all the time. We pay humans upwards of $50 trillion in wages because they're useful, even though in principle it would be much easier to integrate AIs into the economy than it is to hire humans. The diffusion doesn't really explain.

</details>

**Dario**: 我认为扩散是非常真实的，并且不完全与 AI 模型的局限性有关。同样，有些人把扩散当作一个流行语来用，以此来说明这没什么大不了的。我说的不是那个。我不是在说 AI 会以以前技术的速度扩散。我认为 AI 的扩散速度将比以前的技术快得多，但不是无限快。我只举一个例子。有 Claude Code。Claude Code 非常容易设置。如果你是一名开发者，你可以直接开始使用 Claude Code。大型企业的开发者没有理由不以与独立开发者或初创公司开发者一样快的速度采用 Claude Code。我们尽一切努力去推广它。我们向企业销售 Claude Code。大型企业、大型金融公司、大型制药公司，它们采用 Claude Code 的速度都比企业通常采用新技术的速度快得多。但同样，这需要时间。任何特定的功能或任何特定的产品，比如 Claude Code 或 **Cowork**，被那些整天泡在 Twitter 上的独立开发者、被 A 轮初创公司采用的速度，会比被一家从事食品销售的大型企业采用的速度快好几个月。这有很多因素。你必须通过法务审核，你必须为每个人配置它。它必须通过安全和合规检查。离 AI 革命较远的公司领导者是有前瞻性的，但他们必须说：“哦，我们花 5000 万是有道理的。这就是 Claude Code 这个东西。这就是为什么它能帮助我们的公司。这就是为什么它能让我们更具生产力。”然后他们必须向下两级的人解释。他们必须说：“好吧，我们有 3000 名开发者。这是我们将如何向我们的开发者推广它的方案。”我们每天都有这样的对话。我们正在尽一切努力使 Anthropic 的收入每年增长 20 或 30 倍，而不是 10 倍。同样，许多企业只是在说：“这太有生产力了。我们要在通常的采购流程中走捷径。”他们现在的行动速度比我们试图向他们推销普通 API（他们中很多人都在使用）时要快得多。Claude Code 是一个更具吸引力的产品，但它不是一个具有无限吸引力的产品。我不认为即使是 AGI 或强大的 AI，或者是“数据中心里的天才国度”，会是一个具有无限吸引力的产品。它将是一个足够有吸引力的产品，也许能带来每年 3-5 倍，或 10 倍的增长，即使你处于数千亿美元的规模，这极其困难，在历史上也从未有过，但它不是无限快的。

<details>
<summary>Original English</summary>

**Dario**: I think diffusion is very real and doesn't exclusively have to do with limitations on the AI models. Again, there are people who use diffusion as kind of a buzzword to say this isn't a big deal. I'm not talking about that. I'm not talking about how AI will diffuse at the speed of previous technologies. I think AI will diffuse much faster than previous technologies have, but not infinitely fast. I'll just give an example of this. There's Claude Code. Claude Code is extremely easy to set up. If you're a developer, you can just start using Claude Code. There is no reason why a developer at a large enterprise should not be adopting Claude Code as quickly as an individual developer or developer at a startup. We do everything we can to promote it. We sell Claude Code to enterprises. Big enterprises, big financial companies, big pharmaceutical companies, all of them are adopting Claude Code much faster than enterprises typically adopt new technology. But again, it takes time. Any given feature or any given product, like Claude Code or Cowork, will get adopted by the individual developers who are on Twitter all the time, by the Series A startups, many months faster than they will get adopted by a large enterprise that does food sales. There are just a number of factors. You have to go through legal, you have to provision it for everyone. It has to pass security and compliance. The leaders of the company who are further away from the AI revolution are forward-looking, but they have to say, "Oh, it makes sense for us to spend 50 million. This is what this Claude Code thing is. This is why it helps our company. This is why it makes us more productive." Then they have to explain to the people two levels below. They have to say, "Okay, we have 3,000 developers. Here's how we're going to roll it out to our developers." We have conversations like this every day. We are doing everything we can to make Anthropic's revenue grow 20 or 30x a year instead of 10x a year. Again, many enterprises are just saying, "This is so productive. We're going to take shortcuts in our usual procurement process." They're moving much faster than when we tried to sell them just the ordinary API, which many of them use. Claude Code is a more compelling product, but it's not an infinitely compelling product. I don't think even AGI or powerful AI or "country of geniuses in a data center" will be an infinitely compelling product. It will be a compelling product enough maybe to get 3-5x, or 10x, a year of growth, even when you're in the hundreds of billions of dollars, which is extremely hard to do and has never been done in history before, but not infinitely fast.

</details>

### 持续学习与适应

**Dwarkesh**: 我同意这会带来轻微的放缓。也许这不是你的主张，但有时人们谈论这个问题时会说，“哦，能力已经具备了，但由于扩散的原因……否则我们基本上已经达到 AGI 了”。

<details>
<summary>Original English</summary>

**Dwarkesh**: I buy that it would be a slight slowdown. Maybe this is not your claim, but sometimes people talk about this like, "Oh, the capabilities are there, but because of diffusion... otherwise we're basically at AGI".

</details>

**Dario**: 我不认为我们基本上已经达到 AGI 了。我认为如果你拥有了“数据中心里的天才国度”……如果我们拥有了“数据中心里的天才国度”，我们会知道的。如果你拥有了“数据中心里的天才国度”，我们会知道的。这个房间里的每个人都会知道。华盛顿的每个人都会知道。偏远地区的人可能不知道，但我们会知道的。我们现在还没有达到那个程度。这是非常清楚的。

<details>
<summary>Original English</summary>

**Dario**: I don't believe we're basically at AGI. I think if you had the "country of geniuses in a data center"... If we had the "country of geniuses in a data center", we would know it. We would know it if you had the "country of geniuses in a data center". Everyone in this room would know it. Everyone in Washington would know it. People in rural parts might not know it, but we would know it. We don't have that now. That is very clear.

</details>

**Dwarkesh**: 回到具体的预测……因为有太多不同的事情需要澄清，当我们谈论能力时，很容易各说各话。例如，三年前我采访你时，我问你对三年后我们应该期待什么的预测。你是对的。你说：“我们应该期待这样的系统，如果你和它们交谈一个小时，你很难将它们与受过良好教育的人类区分开来。”我认为你在这一点上是对的。我觉得在精神上我感到不满足，因为我内心的期望是这样的系统可以自动化大部分白领工作。所以，讨论你希望从这样一个系统中获得的实际最终能力可能会更有成效。

<details>
<summary>Original English</summary>

**Dwarkesh**: Coming back to concrete prediction… Because there are so many different things to disambiguate, it can be easy to talk past each other when we're talking about capabilities. For example, when I interviewed you three years ago, I asked you a prediction about what we should expect three years from now. You were right. You said, "We should expect systems which, if you talk to them for the course of an hour, it's hard to tell them apart from a generally well-educated human." I think you were right about that. I think spiritually I feel unsatisfied because my internal expectation was that such a system could automate large parts of white-collar work. So it might be more productive to talk about the actual end capabilities you want from such a system.

</details>

**Dario**: 我基本上会告诉你我认为我们目前处于什么阶段。

<details>
<summary>Original English</summary>

**Dario**: I will basically tell you where I think we are.

</details>

**Dwarkesh**: 让我问一个非常具体的问题，以便我们能确切地弄清楚我们很快应该期待什么样的能力。也许我会以一个我非常了解的工作为背景来问这个问题，不是因为它最相关，而是因为我可以评估关于它的主张。以视频剪辑师为例。我有视频剪辑师。他们工作的一部分涉及了解我们观众的偏好，了解我的偏好和品味，以及我们所做的不同权衡。在几个月的时间里，他们逐渐建立起对背景的理解。他们在工作六个月后拥有的技能和能力，一个能够在工作中即时掌握这种技能的模型，我们应该在什么时候期待这样的 AI 系统出现？

<details>
<summary>Original English</summary>

**Dwarkesh**: Let me ask a very specific question so that we can figure out exactly what kinds of capabilities we should think about soon. Maybe I'll ask about it in the context of a job I understand well, not because it's the most relevant job, but just because I can evaluate the claims about it. Take video editors. I have video editors. Part of their job involves learning about our audience's preferences, learning about my preferences and tastes, and the different trade-offs we have. They’re, over the course of many months, building up this understanding of context. The skill and ability they have six months into the job, a model that can pick up that skill on the job on the fly, when should we expect such an AI system?

</details>

**Dario**: 我想你谈论的是，我们进行这三个小时的采访。有人会进来，有人会剪辑它。他们会说，“哦，我不知道，Dario 挠了挠头，我们可以把那段剪掉。”“放大那个画面。”“这里有一段很长的讨论，人们不太感兴趣。还有另一件事人们更感兴趣，所以让我们做这个剪辑。”我认为“数据中心里的天才国度”将能够做到这一点。它能做到这一点的方式是，它将拥有对电脑屏幕的全面控制权。你将能够把这些输入进去。它还能使用电脑屏幕上网，查看你以前所有的采访，查看人们在 Twitter 上对你采访的反应，和你交谈，问你问题，和你的员工交谈，查看你过去的剪辑历史，然后据此完成工作。我认为这取决于几件事。我认为这是实际上阻碍部署的事情之一：在计算机使用方面达到模型真正精通使用计算机的程度。我们已经看到这在基准测试中不断攀升，而基准测试总是不完美的衡量标准。但我认为，当我们一年零三个月前首次发布计算机使用功能时，**OSWorld** 的成绩可能在 15% 左右。我不记得确切数字了，但我们已经从那个水平攀升到了 65-70%。可能还有更严格的衡量标准，但我认为计算机使用必须通过一个可靠性的临界点。

<details>
<summary>Original English</summary>

**Dario**: I guess what you're talking about is that we're doing this interview for three hours. Someone's going to come in, someone's going to edit it. They're going to be like, "Oh, I don't know, Dario scratched his head and we could edit that out." "Magnify that." "There was this long discussion that is less interesting to people. There's another thing that's more interesting to people, so let's make this edit." I think the "country of geniuses in a data center" will be able to do that. The way it will be able to do that is it will have general control of a computer screen. You'll be able to feed this in. It'll be able to also use the computer screen to go on the web, look at all your previous interviews, look at what people are saying on Twitter in response to your interviews, talk to you, ask you questions, talk to your staff, look at the history of edits that you did, and from that, do the job. I think that's dependent on several things. I think this is one of the things that's actually blocking deployment: getting to the point on computer use where the models are really masters at using the computer. We've seen this climb in benchmarks, and benchmarks are always imperfect measures. But I think when we first released computer use a year and a quarter ago, OSWorld was at maybe 15%. I don't remember exactly, but we've climbed from that to 65-70%. There may be harder measures as well, but I think computer use has to pass a point of reliability.

</details>

**Dwarkesh**: 在你进入下一点之前，我能就此追问一下吗？多年来，我一直试图为自己构建不同的内部 LLM 工具。通常我有一些文本输入、文本输出的任务，这应该是这些模型能力库中的核心。然而我仍然雇佣人类来做这些事。如果是像“找出这份文字记录中最好的片段”这样的任务，也许 LLM 能做到十分之七的水平。但我没有一种持续的方式可以与它们互动，帮助它们在工作上变得更好，就像我对待人类员工那样。这种缺失的能力，即使你解决了计算机使用问题，仍然会阻碍我将实际工作交给它们的能力。

<details>
<summary>Original English</summary>

**Dwarkesh**: Can I just follow up on that before you move on to the next point? For years, I've been trying to build different internal LLM tools for myself. Often I have these text-in, text-out tasks, which should be dead center in the repertoire of these models. Yet I still hire humans to do them. If it's something like, "identify what the best clips would be in this transcript", maybe the LLMs do a seven-out-of-ten job on them. But there's not this ongoing way I can engage with them to help them get better at the job the way I could with a human employee. That missing ability, even if you solve computer use, would still block my ability to offload an actual job to them.

</details>

**Dario**: 这又回到了我们之前谈论的在职学习。这非常有趣。我认为对于编程智能体，人们不会说在职学习是阻止编程智能体端到端完成所有事情的障碍。它们在不断变得更好。在 Anthropic，我们有不写任何代码的工程师。当我审视生产力时，回到你之前的问题，我们有同事说：“这个 GPU 内核，这个芯片，我以前都是自己写的。现在我直接让 **Claude** 来做。”生产力有了这种巨大的提升。当我看到 Claude Code 时，对代码库的熟悉程度，或者感觉模型没有在公司工作过一年，这些并不是我看到的抱怨列表中的首要问题。我想我是在说，我们正在走一条不同的路。

<details>
<summary>Original English</summary>

**Dario**: This gets back to what we were talking about before with learning on the job. It's very interesting. I think with the coding agents, I don't think people would say that learning on the job is what is preventing the coding agents from doing everything end to end. They keep getting better. We have engineers at Anthropic who don't write any code. When I look at the productivity, to your previous question, we have folks who say, "This GPU kernel, this chip, I used to write it myself. I just have Claude do it." There's this enormous improvement in productivity. When I see Claude Code, familiarity with the codebase or a feeling that the model hasn't worked at the company for a year, that's not high up on the list of complaints I see. I think what I'm saying is that we're kind of taking a different path.

</details>

**Dwarkesh**: 你不认为在编程方面，这是因为存在一个实例化的代码库作为外部记忆支架吗？我不知道还有多少其他工作有这个。编程之所以进展迅速，正是因为它具有其他经济活动所没有的这种独特优势。

<details>
<summary>Original English</summary>

**Dwarkesh**: Don't you think with coding that's because there is an external scaffold of memory which exists instantiated in the codebase? I don't know how many other jobs have that. Coding made fast progress precisely because it has this unique advantage that other economic activity doesn't.

</details>

**Dario**: 但当你说这话时，你的言下之意是，通过将代码库读入上下文，我就拥有了人类在工作中需要学习的一切。所以这将是一个例子——无论它是否被写下来，无论它是否可用——在这个例子中，你需要知道的一切都是从上下文窗口中获得的。我们所认为的学习——“我开始了这份工作，我需要六个月的时间来理解代码库”——模型只是在上下文中完成了它。

<details>
<summary>Original English</summary>

**Dario**: But when you say that, what you're implying is that by reading the codebase into the context, I have everything that the human needed to learn on the job. So that would be an example of—whether it's written or not, whether it's available or not—a case where everything you needed to know you got from the context window. What we think of as learning—"I started this job, it's going to take me six months to understand the code base"—the model just did it in the context.

</details>

### 生产力与竞争

**Dwarkesh**: 我真的不知道该怎么看待这个问题，因为有人定性地报告了你所说的情况。我确信你看到了去年的一个主要研究，他们让经验丰富的开发者尝试在他们熟悉的代码库中关闭拉取请求（pull requests）。这些开发者报告了生产力的提升。他们报告说，使用这些模型让他们感觉更有生产力。但事实上，如果你看看他们的产出以及实际合并回代码库的数量，生产力下降了 20%。使用这些模型导致他们的生产力降低了。所以我试图将人们对这些模型的定性感觉与以下两点统一起来：1) 在宏观层面上，软件的复兴在哪里？2) 当人们进行这些独立评估时，为什么我们没有看到预期的生产力收益？

<details>
<summary>Original English</summary>

**Dwarkesh**: I honestly don't know how to think about this because there are people who qualitatively report what you're saying. I'm sure you saw last year, there was a major study where they had experienced developers try to close pull requests in repositories that they were familiar with. Those developers reported an uplift. They reported that they felt more productive with the use of these models. But in fact, if you look at their output and how much was actually merged back in, there was a 20% downlift. They were less productive as a result of using these models. So I'm trying to square the qualitative feeling that people feel with these models versus, 1) in a macro level, where is this renaissance of software? And then 2) when people do these independent evaluations, why are we not seeing the productivity benefits we would expect?

</details>

**Dario**: 在 Anthropic 内部，这是非常明确的。我们承受着难以置信的商业压力，而且我们还让自己变得更难，因为我们做了所有这些安全方面的工作，我认为我们比其他公司做得更多。在保持我们价值观的同时还要在经济上生存下来的压力简直难以置信。我们正试图保持这种 10 倍收入曲线的增长。我们根本没有时间搞虚的。我们根本没有时间去感觉自己有生产力而实际上却没有。这些工具让我们变得更有生产力。你认为我们为什么担心竞争对手使用这些工具？因为我们认为我们领先于竞争对手。如果这在暗中降低了我们的生产力，我们才不会费这么大劲。我们每隔几个月就会以模型发布的形式看到最终的生产力。在这件事上骗不了自己。这些模型让你更有生产力。

<details>
<summary>Original English</summary>

**Dario**: Within Anthropic, this is just really unambiguous. We're under an incredible amount of commercial pressure and make it even harder for ourselves because we have all this safety stuff we do that I think we do more than other companies. The pressure to survive economically while also keeping our values is just incredible. We're trying to keep this 10x revenue curve going. There is zero time for bullshit. There is zero time for feeling like we're productive when we're not. These tools make us a lot more productive. Why do you think we're concerned about competitors using the tools? Because we think we're ahead of the competitors. We wouldn't be going through all this trouble if this were secretly reducing our productivity. We see the end productivity every few months in the form of model launches. There's no kidding yourself about this. The models make you more productive.

</details>

**Dwarkesh**: 1) 人们感觉自己有生产力，这在定性上是被这类研究所预测的。但是 2) 如果我只看最终产出，显然你们正在取得快速进展。但原本的想法应该是，随着递归自我改进，你制造出一个更好的 AI，这个 AI 帮助你构建下一个更好的 AI，等等。但我看到的却是——如果我看看你们、OpenAI、DeepMind——人们只是每隔几个月在领奖台上换个位置。也许你认为这会停止，因为你们已经赢了或者怎样。但如果上一个编程模型确实带来了巨大的生产力收益，为什么我们没有看到拥有最好编程模型的人获得这种持久的优势呢？

<details>
<summary>Original English</summary>

**Dwarkesh**: 1) People feeling like they're productive is qualitatively predicted by studies like this. But 2) if I just look at the end output, obviously you guys are making fast progress. But the idea was supposed to be that with recursive self-improvement, you make a better AI, the AI helps you build a better next AI, et cetera, et cetera. What I see instead—if I look at you, OpenAI, DeepMind—is that people are just shifting around the podium every few months. Maybe you think that stops because you've won or whatever. But why are we not seeing the person with the best coding model have this lasting advantage if in fact there are these enormous productivity gains from the last coding model.

</details>

**Dario**: 我认为我对这种情况的模型是，存在一种正在逐渐增长的优势。我会说现在编程模型可能带来了，我不知道，15-20% 的全要素加速。这是我的观点。六个月前，可能只有 5%。所以这无关紧要。5% 是感觉不到的。现在它刚刚达到成为几个重要因素之一的程度。这将会继续加速。我认为六个月前，有几家公司大致处于同一起跑线，因为这不是一个显著的因素，但我认为它开始越来越快地加速。我还要说，有多家公司编写用于代码的模型，我们在阻止其他一些公司在内部使用我们的模型方面做得并不完美。所以我认为我们看到的一切都符合这种滚雪球模型。再次强调，我在所有这些事情上的主题是，所有这些都是软起飞，平滑的指数级增长，尽管指数曲线相对陡峭。所以我们看到这个雪球聚集了动力，比如 10%、20%、25%、40%。随着你的推进，根据**阿姆达尔定律**（Amdahl's law），你必须消除所有阻碍你形成闭环的障碍。但这是 Anthropic 内部最大的优先事项之一。

<details>
<summary>Original English</summary>

**Dario**: I think my model of the situation is that there's an advantage that's gradually growing. I would say right now the coding models give maybe, I don't know, a 15-20% total factor speed up. That's my view. Six months ago, it was maybe 5%. So it didn't matter. 5% doesn't register. It's now just getting to the point where it's one of several factors that kind of matters. That's going to keep speeding up. I think six months ago, there were several companies that were at roughly the same point because this wasn't a notable factor, but I think it's starting to speed up more and more. I would also say there are multiple companies that write models that are used for code and we're not perfectly good at preventing some of these other companies from using our models internally. So I think everything we're seeing is consistent with this kind of snowball model. Again, my theme in all of this is all of this is soft takeoff, soft, smooth exponentials, although the exponentials are relatively steep. So we're seeing this snowball gather momentum where it's like 10%, 20%, 25%, 40%. As you go, Amdahl's law, you have to get all the things that are preventing you from closing the loop out of the way. But this is one of the biggest priorities within Anthropic.

</details>

### 算力投资与商业

**Dwarkesh**: 退一步讲，之前在技术栈中我们讨论过什么时候能实现这种在职学习？似乎你在编程问题上表达的观点是，我们实际上不需要在职学习。你可以拥有巨大的生产力提升，你可以为 AI 公司带来数万亿美元的潜在收入，而不需要这种基本的人类在职学习能力。也许这不是你的主张，你应该澄清一下。但在大多数经济活动领域，人们会说，“我雇了个人，他们前几个月没那么大用处，然后随着时间的推移，他们建立起了背景和理解。”实际上很难定义我们在这里谈论的是什么。但他们掌握了一些东西，现在他们成了主力，对我们非常有价值。如果 AI 没有发展出这种即时学习的能力，我有点怀疑如果没有这种能力，我们是否会看到世界发生巨大的变化。

<details>
<summary>Original English</summary>

**Dwarkesh**: Stepping back, before in the stack we were talking about when do we get this on-the-job learning? It seems like the point you were making on the coding thing is that we actually don't need on-the-job learning. You can have tremendous productivity improvements, you can have potentially trillions of dollars of revenue for AI companies, without this basic human ability to learn on the job. Maybe that's not your claim, you should clarify. But in most domains of economic activity, people say, "I hired somebody, they weren't that useful for the first few months, and then over time they built up the context, understanding." It's actually hard to define what we're talking about here. But they got something and then now they're a powerhorse and they're so valuable to us. If AI doesn't develop this ability to learn on the fly, I'm a bit skeptical that we're going to see huge changes to the world without that ability.

</details>

**Dario**: 我认为这里有两点。一是目前的技术状态。同样，我们有这两个阶段。我们有预训练和强化学习阶段，你把大量的数据和任务扔给模型，然后它们进行泛化。所以这就像学习，但它像是从更多的数据中学习，而不是在一个人类或一个模型的一生中学习。所以再次强调，这介于进化和人类学习之间。但一旦你学到了所有这些技能，你就拥有了它们。就像预训练一样，模型知道得更多，如果我看一个预训练模型，它比我更了解日本武士的历史。它比我更了解棒球。它比我更了解低通滤波器和电子学，所有这些东西。它的知识面比我广得多。所以我认为，即使仅仅是这样，也可能让我们达到模型在一切方面都更好的地步。我们还有，同样，只需扩展现有的设置，即上下文学习。我会把它描述为有点像人类的在职学习，但稍微弱一点，也稍微短期一点。你看看上下文学习，如果你给模型一堆例子，它确实能理解。在上下文中发生了真正的学习。一百万个 token 是很多的。那可能相当于人类几天的学习量。如果你想象模型阅读一百万个词，我读一百万个词需要多长时间？至少几天或几周。所以你有这两样东西。我认为现有范式中的这两样东西可能就足以让你获得“数据中心里的天才国度”。我不能确定，但我认为它们将让你实现很大一部分。可能存在差距，但我当然认为，就目前的情况而言，这足以产生数万亿美元的收入。这是第一点。第二点，是这种持续学习的想法，这种单一模型在职学习的想法。我认为我们也在研究这个问题。很有可能在未来一两年内，我们也能解决这个问题。同样，我认为即使没有它，你也能实现大部分目标。每年数万亿美元的市场，也许我在《技术的青春期》中写到的所有国家安全影响和安全影响，都可以在没有它的情况下发生。但我们，我想其他人也一样，正在研究它。我们很有可能在未来一两年内实现这一目标。有很多想法。我不会详细讨论所有这些想法，但其中一个是让上下文变得更长。没有什么能阻止更长的上下文发挥作用。你只需要在更长的上下文下进行训练，然后学会在推理时提供服务。这两个都是我们正在努力解决的工程问题，我假设其他人也在努力解决。

<details>
<summary>Original English</summary>

**Dario**: I think two things here. There's the state of the technology right now. Again, we have these two stages. We have the pre-training and RL stage where you throw a bunch of data and tasks into the models and then they generalize. So it's like learning, but it's like learning from more data and not learning over one human or one model's lifetime. So again, this is situated between evolution and human learning. But once you learn all those skills, you have them. Just like with pre-training, just how the models know more, if I look at a pre-trained model, it knows more about the history of samurai in Japan than I do. It knows more about baseball than I do. It knows more about low-pass filters and electronics, all of these things. Its knowledge is way broader than mine. So I think even just that may get us to the point where the models are better at everything. We also have, again, just with scaling the kind of existing setup, the in-context learning. I would describe it as kind of like human on-the-job learning, but a little weaker and a little short term. You look at in-context learning and if you give the model a bunch of examples it does get it. There's real learning that happens in context. A million tokens is a lot. That can be days of human learning. If you think about the model reading a million words, how long would it take me to read a million? Days or weeks at least. So you have these two things. I think these two things within the existing paradigm may just be enough to get you the "country of geniuses in a data center". I don't know for sure, but I think they're going to get you a large fraction of it. There may be gaps, but I certainly think that just as things are, this is enough to generate trillions of dollars of revenue. That's one. Two, is this idea of continual learning, this idea of a single model learning on the job. I think we're working on that too. There's a good chance that in the next year or two, we also solve that. Again, I think you get most of the way there without it. The trillions of dollars a year market, maybe all of the national security implications and the safety implications that I wrote about in "Adolescence of Technology" can happen without it. But we, and I imagine others, are working on it. There's a good chance that we will get there within the next year or two. There are a bunch of ideas. I won't go into all of them in detail, but one is just to make the context longer. There's nothing preventing longer contexts from working. You just have to train at longer contexts and then learn to serve them at inference. Both of those are engineering problems that we are working on and I would assume others are working on them as well.

</details>

**Dwarkesh**: 关于上下文长度的增加，似乎在 2020 年到 2023 年期间，从 **GPT-3** 到 **GPT-4 Turbo**，上下文长度从 2000 增加到了 128K。我觉得从那以后的两年左右时间里，我们一直停留在差不多的水平。当上下文长度远长于这个数字时，人们报告说模型考虑完整上下文的能力出现了定性下降。所以我很好奇你们在内部看到了什么，让你认为“1000 万的上下文，1 亿的上下文能获得相当于人类六个月的学习和背景构建”。

<details>
<summary>Original English</summary>

**Dwarkesh**: This context length increase, it seemed like there was a period from 2020 to 2023 where from GPT-3 to GPT-4 Turbo, there was an increase from 2000 context lengths to 128K. I feel like for the two-ish years since then, we've been in the same-ish ballpark. When context lengths get much longer than that, people report qualitative degradation in the ability of the model to consider that full context. So I'm curious what you're internally seeing that makes you think, "10 million contexts, 100 million contexts to get six months of human learning and building context".

</details>

**Dario**: 这不是一个研究问题。这是一个工程和推理问题。如果你想提供长上下文服务，你必须存储整个 KV 缓存。在 GPU 中存储所有内存、调度内存是很困难的。我甚至不知道具体细节。在这一点上，这已经到了我无法再跟进的细节层面，尽管在 GPT-3 时代我是知道的。“这些是权重，这些是你必须存储的激活值……”但现在整个情况都变了，因为我们有了 **MoE**（混合专家）模型以及所有这些东西。关于你谈到的这种能力下降，在不涉及太多细节的情况下，有两件事。有你训练时的上下文长度，也有你提供服务时的上下文长度。如果你在较短的上下文长度下训练，然后试图在较长的上下文长度下提供服务，也许你就会遇到这些能力下降。这总比没有好，你可能仍然会提供它，但你会遇到这些下降。也许在长上下文长度下进行训练更难。

<details>
<summary>Original English</summary>

**Dario**: This isn't a research problem. This is an engineering and inference problem. If you want to serve long context, you have to store your entire KV cache. It's difficult to store all the memory in the GPUs, to juggle the memory around. I don't even know the details. At this point, this is at a level of detail that I'm no longer able to follow, although I knew it in the GPT-3 era. "These are the weights, these are the activations you have to store…" But these days the whole thing is flipped because we have MoE models and all of that. Regarding this degradation you're talking about, without getting too specific, there's two things. There's the context length you train at and there's a context length that you serve at. If you train at a small context length and then try to serve at a long context length, maybe you get these degradations. It's better than nothing, you might still offer it, but you get these degradations. Maybe it's harder to train at a long context length.

</details>

**Dwarkesh**: 我想同时问一些可能比较深入的问题。难道你不会预料到，如果你必须在更长的上下文长度上进行训练，那将意味着在相同的算力下你能输入的样本更少吗？也许这不值得深入探讨。我想得到那个更大图景问题的答案。我并不偏好一个为我工作了六个月的人类剪辑师，而不是一个为我工作了六个月的 AI，你预测哪一年会实现这一点？

<details>
<summary>Original English</summary>

**Dwarkesh**: I want to, at the same time, ask about maybe some rabbit holes. Wouldn't you expect that if you had to train on longer context length, that would mean that you're able to get less samples in for the same amount of compute? Maybe it's not worth diving deep on that. I want to get an answer to the bigger picture question. I don't feel a preference for a human editor that's been working for me for six months versus an AI that's been working with me for six months, what year do you predict that that will be the case?

</details>

**Dario**: 我的猜测是，有很多问题基本上当我们拥有“数据中心里的天才国度”时就能解决。如果让我猜的话，我的预期是一到两年，也许是一到三年。这真的很难说。我有一个强烈的观点——99%，95%——所有这一切都将在 10 年内发生。我认为这是一个非常稳妥的赌注。我有一种预感——这更像是一半一半的概率——它将更像是一到两年，也许更像是一到三年。

<details>
<summary>Original English</summary>

**Dario**: My guess for that is there's a lot of problems where basically we can do this when we have the "country of geniuses in a data center". My picture for that, if you made me guess, is one to two years, maybe one to three years. It's really hard to tell. I have a strong view—99%, 95%—that all this will happen in 10 years. I think that's just a super safe bet. I have a hunch—this is more like a 50/50 thing—that it's going to be more like one to two, maybe more like one to three.

</details>

**Dwarkesh**: 所以是一到三年。天才国度，以及经济价值稍低一些的视频剪辑任务。让我告诉你，这似乎具有相当大的经济价值。只是有很多类似的用例。有很多类似的用例。所以你预测在一到三年内。然后，总的来说，Anthropic 预测到 26 年底或 27 年初，我们将拥有这样的 AI 系统：“能够导航今天从事数字工作的人类可用的界面，智力能力达到或超过诺贝尔奖获得者，并且能够与物理世界互动”。你两个月前接受 **DealBook** 采访时，强调了你们公司与竞争对手相比更负责任的算力扩展。我试图将这两种观点统一起来。如果你真的相信我们将拥有一个天才国度，你会想要一个尽可能大的数据中心。没有理由放慢脚步。一个能做诺贝尔奖获得者能做的一切的诺贝尔奖获得者的总潜在市场（TAM）是数万亿美元。所以我试图将这种保守主义——如果你有更温和的时间表，这似乎是合理的——与你所陈述的关于进展的观点统一起来。

<details>
<summary>Original English</summary>

**Dwarkesh**: So one to three years. Country of geniuses, and the slightly less economically valuable task of editing videos. It seems pretty economically valuable, let me tell you. It's just there are a lot of use cases like that. There are a lot of similar ones. So you're predicting that within one to three years. And then, generally, Anthropic has predicted that by late '26 or early '27 we will have AI systems that "have the ability to navigate interfaces available to humans doing digital work today, intellectual capabilities matching or exceeding that of Nobel Prize winners, and the ability to interface with the physical world". You gave an interview two months ago with DealBook where you were emphasizing your company's more responsible compute scaling as compared to your competitors. I'm trying to square these two views. If you really believe that we're going to have a country of geniuses, you want as big a data center as you can get. There's no reason to slow down. The TAM of a Nobel Prize winner, that can actually do everything a Nobel Prize winner can do, is trillions of dollars. So I'm trying to square this conservatism, which seems rational if you have more moderate timelines, with your stated views about progress.

</details>

**Dario**: 实际上这一切都是吻合的。我们回到这种快速但非无限快的扩散。假设我们正以这个速度取得进展。技术正以这么快的速度进步。我非常确信我们将在几年内达到目标。我有一种预感，我们将在这一两年内达到目标。所以在技术方面有一点不确定性，但相当有信心误差不会太大。我不太确定的是，同样，经济扩散方面。我真的相信我们可能在一到两年内拥有数据中心里天才国度级别的模型。一个问题是：在那之后多少年，数万亿的收入才会滚滚而来？我不认为这保证会立竿见影。可能是一年，可能是两年，我甚至可以把它拉长到五年，尽管我对此表示怀疑。所以我们存在这种不确定性。即使技术发展得像我怀疑的那样快，我们也不知道它究竟能多快地推动收入增长。我们知道它要来了，但以你购买这些数据中心的方式，如果你误差了几年，那可能是毁灭性的。

<details>
<summary>Original English</summary>

**Dario**: It actually all fits together. We go back to this fast, but not infinitely fast, diffusion. Let's say that we're making progress at this rate. The technology is making progress this fast. I have very high conviction that we're going to get there within a few years. I have a hunch that we're going to get there within a year or two. So there’s a little uncertainty on the technical side, but pretty strong confidence that it won't be off by much. What I'm less certain about is, again, the economic diffusion side. I really do believe that we could have models that are a country of geniuses in the data center in one to two years. One question is: How many years after that do the trillions in revenue start rolling in? I don't think it's guaranteed that it's going to be immediate. It could be one year, it could be two years, I could even stretch it to five years although I'm skeptical of that. So we have this uncertainty. Even if the technology goes as fast as I suspect that it will, we don't know exactly how fast it's going to drive revenue. We know it's coming, but with the way you buy these data centers, if you're off by a couple years, that can be ruinous.

</details>

**Dario**: 就像我在**《充满爱的恩典机器》**（Machines of Loving Grace）中写的那样。我说我认为我们可能会在 2026 年，也许是 2027 年获得这种强大的 AI，这种“数据中心里的天才国度”。你给出的那个描述就来自《充满爱的恩典机器》。我说我们将在 2026 年，也许 2027 年获得它。同样，那是我的预感。如果我误差了一两年，我也不会感到惊讶，但那是我的预感。假设那发生了。那是发令枪。治愈所有疾病需要多长时间？这是驱动巨大经济价值的途径之一。你治愈了每一种疾病。这里有一个问题，即其中有多少归制药公司或 AI 公司所有，但存在巨大的消费者剩余，因为——假设我们能让每个人都获得它，这是我非常关心的——我们治愈了所有这些疾病。这需要多长时间？你必须进行生物学发现，你必须制造新药，你必须通过监管流程。我们在疫苗和 COVID 上看到了这一点。我们把疫苗分发给了每个人，但这花了一年半的时间。我的问题是：把治愈一切的药物——理论上 AI 这个天才可以发明出来——分发给每个人需要多长时间？从那个 AI 首次在实验室中存在，到疾病真正为每个人被治愈，需要多长时间？我们拥有脊髓灰质炎疫苗已经 50 年了。我们仍在努力在非洲最偏远的角落根除它。**盖茨基金会**（Gates Foundation）正在尽最大努力。其他人也在尽最大努力。但这很困难。同样，我不指望大多数经济扩散会像那样困难。那是极其困难的案例。但这里存在一个真正的困境。我对此的结论是，它将比我们在世界上看到的任何事情都要快，但它仍然有其局限性。

<details>
<summary>Original English</summary>

**Dario**: It is just like how I wrote in "Machines of Loving Grace". I said I think we might get this powerful AI, this "country of genius in the data center". That description you gave comes from "Machines of Loving Grace". I said we'll get that in 2026, maybe 2027. Again, that is my hunch. I wouldn't be surprised if I'm off by a year or two, but that is my hunch. Let's say that happens. That's the starting gun. How long does it take to cure all the diseases? That's one of the ways that drives a huge amount of economic value. You cure every disease. There's a question of how much of that goes to the pharmaceutical company or the AI company, but there's an enormous consumer surplus because —assuming we can get access for everyone, which I care about greatly—we cure all of these diseases. How long does it take? You have to do the biological discovery, you have to manufacture the new drug, you have to go through the regulatory process. We saw this with vaccines and COVID. We got the vaccine out to everyone, but it took a year and a half. My question is: How long does it take to get the cure for everything—which AI is the genius that can in theory invent—out to everyone? How long from when that AI first exists in the lab to when diseases have actually been cured for everyone? We've had a polio vaccine for 50 years. We're still trying to eradicate it in the most remote corners of Africa. The Gates Foundation is trying as hard as they can. Others are trying as hard as they can. But that's difficult. Again, I don't expect most of the economic diffusion to be as difficult as that. That's the most difficult case. But there's a real dilemma here. Where I've settled on it is that it will be faster than anything we've seen in the world, but it still has its limits.

</details>

**Dario**: 所以当我们去购买数据中心时，同样，我关注的曲线是：我们每年都有 10 倍的增长。在今年年初，我们看到的是 100 亿美元的年化收入。我们必须决定购买多少算力。实际建好数据中心、预留数据中心需要一两年的时间。基本上我是在说，“在 2027 年，我能获得多少算力？”我可以假设收入将继续以每年 10 倍的速度增长，所以到 2026 年底将是 1000 亿美元，到 2027 年底将是 1 万亿美元。实际上那将是 5 万亿美元的算力，因为那将是连续五年每年 1 万亿美元。我可以购买从 2027 年底开始的 1 万亿美元算力。如果我的收入不是 1 万亿美元，即使是 8000 亿美元，如果我买了那么多算力，地球上没有任何力量、没有任何对冲手段能阻止我破产。尽管我大脑的一部分想知道它是否会继续以 10 倍的速度增长，但我不能在 2027 年购买每年 1 万亿美元的算力。如果我在那种增长率上只误差了一年，或者如果增长率是每年 5 倍而不是 10 倍，那么你就会破产。所以你最终处于一个你支撑数千亿美元，而不是数万亿美元的世界。你接受需求太大以至于你无法支撑收入的风险，你也接受你猜错了且增长仍然缓慢的风险。当我谈到负责任地行事时，我的意思实际上不是绝对数量。我认为我们花的钱确实比其他一些玩家少一些。实际上是其他方面，比如我们是否对此深思熟虑，还是我们在随性而为（YOLO），说“我们要在这里投 1000 亿，在那里投 1000 亿”？我的印象是，其他一些公司并没有写下电子表格，他们并不真正了解他们正在承担的风险。他们只是因为听起来很酷就去做。我们对此进行了仔细的思考。我们是一家企业级业务公司。因此，我们可以更多地依赖收入。它不像消费者业务那样变幻莫测。我们有更好的利润率，这是买得太多和买得太少之间的缓冲。我认为我们购买的数量使我们能够抓住相当强劲的上行空间。它不会抓住全部的每年 10 倍增长。事情必须变得非常糟糕，我们才会陷入财务困境。所以我们经过了仔细的思考，并做出了这种平衡。这就是我说我们负责任的意思。

<details>
<summary>Original English</summary>

**Dario**: So when we go to buying data centers, again, the curve I'm looking at is: we've had a 10x a year increase every year. At the beginning of this year, we're looking at $10 billion in annualized revenue. We have to decide how much compute to buy. It takes a year or two to actually build out the data centers, to reserve the data center. Basically I'm saying, "In 2027, how much compute do I get?" I could assume that the revenue will continue growing 10x a year, so it'll be $100 billion at the end of 2026 and $1 trillion at the end of 2027. Actually it would be $5 trillion dollars of compute because it would be $1 trillion a year for five years. I could buy $1 trillion of compute that starts at the end of 2027. If my revenue is not $1 trillion dollars, if it's even $800 billion, there's no force on earth, there's no hedge on earth that could stop me from going bankrupt if I buy that much compute. Even though a part of my brain wonders if it's going to keep growing 10x, I can't buy $1 trillion a year of compute in 2027. If I'm just off by a year in that rate of growth, or if the growth rate is 5x a year instead of 10x a year, then you go bankrupt. So you end up in a world where you're supporting hundreds of billions, not trillions. You accept some risk that there's so much demand that you can't support the revenue, and you accept some risk that you got it wrong and it's still slow. When I talked about behaving responsibly, what I meant actually was not the absolute amount. I think it is true we're spending somewhat less than some of the other players. It's actually the other things, like have we been thoughtful about it or are we YOLOing and saying, "We're going to do $100 billion here or $100 billion there"? I get the impression that some of the other companies have not written down the spreadsheet, that they don't really understand the risks they're taking. They're just doing stuff because it sounds cool. We've thought carefully about it. We're an enterprise business. Therefore, we can rely more on revenue. It's less fickle than consumer. We have better margins, which is the buffer between buying too much and buying too little. I think we bought an amount that allows us to capture pretty strong upside worlds. It won't capture the full 10x a year. Things would have to go pretty badly for us to be in financial trouble. So we've thought carefully and we've made that balance. That's what I mean when I say that we're being responsible.

</details>

### 行业竞争与利润

**Dwarkesh**: 所以看起来我们可能对“数据中心里的天才国度”有不同的定义。因为当我想到真正的人类天才，一个数据中心里真正的人类天才国度时，我会很乐意购买价值 5 万亿美元的算力来运行一个真正的数据中心里的人类天才国度。假设**摩根大通**（JPMorgan）或 **Moderna** 或其他什么公司不想使用它们。我有一个天才国度。他们会创办自己的公司。如果他们不能创办自己的公司，并且被临床试验卡住了脖子……值得说明的是，在临床试验中，大多数临床试验失败是因为药物不起作用。没有疗效。

<details>
<summary>Original English</summary>

**Dwarkesh**: So it seems like it's possible that we actually just have different definitions of the "country of a genius in a data center". Because when I think of actual human geniuses, an actual country of human geniuses in a data center, I would happily buy $5 trillion worth of compute to run an actual country of human geniuses in a data center. Let's say JPMorgan or Moderna or whatever doesn't want to use them. I've got a country of geniuses. They'll start their own company. If they can't start their own company and they're bottlenecked by clinical trials… It is worth stating that with clinical trials, most clinical trials fail because the drug doesn't work. There's not efficacy.

</details>

**Dario**: 我在《充满爱的恩典机器》中正是提出了这一点，我说临床试验将会比我们习惯的快得多，但不是无限快。

<details>
<summary>Original English</summary>

**Dario**: I make exactly that point in "Machines of Loving Grace", I say the clinical trials are going to go much faster than we're used to, but not infinitely fast.

</details>

**Dwarkesh**: 好的，然后假设需要一年的时间临床试验才能成功，这样你就能从中获得收入并可以制造更多的药物。好吧，你有一个天才国度，而且你是一个 AI 实验室。你可以使用更多的 AI 研究人员。你也认为聪明人致力于 AI 技术会带来这些自我强化的收益。你可以让数据中心致力于 AI 的进步。购买每年 1 万亿美元的算力与每年 3000 亿美元的算力相比，会有实质性更多的收益吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, and then suppose it takes a year for the clinical trials to work out so that you're getting revenue from that and can make more drugs. Okay, well, you've got a country of geniuses and you're an AI lab. You could use many more AI researchers. You also think there are these self-reinforcing gains from smart people working on AI tech. You can have the data center working on AI progress. Are there substantially more gains from buying $1 trillion a year of compute versus $300 billion a year of compute?

</details>

**Dario**: 如果你的竞争对手购买了 1 万亿，是的，会有。

<details>
<summary>Original English</summary>

**Dario**: If your competitor is buying a trillion, yes there is.

</details>

**Dwarkesh**: 嗯，不，会有一些收益，但话又说回来，他们有可能在此之前破产。

<details>
<summary>Original English</summary>

**Dwarkesh**: Well, no, there's some gain, but then again, there's this chance that they go bankrupt before.

</details>

**Dario**: 同样，如果你只误差了一年，你就会毁了自己。这就是平衡。我们买了很多。我们买得非常多。我们购买的数量与游戏中最大的玩家购买的数量相当。但如果你问我，“为什么我们没有签署从 2027 年中开始的 10 万亿美元的算力？”……首先，它生产不出来。世界上没有那么多。其次，如果天才国度来了，但它是在 2028 年中而不是 2027 年中来的呢？你会破产的。

<details>
<summary>Original English</summary>

**Dario**: Again, if you're off by only a year, you destroy yourselves. That's the balance. We're buying a lot. We're buying a hell of a lot. We're buying an amount that's comparable to what the biggest players in the game are buying. But if you're asking me, "Why haven't we signed $10 trillion of compute starting in mid-2027?"... First of all, it can't be produced. There isn't that much in the world. But second, what if the country of geniuses comes, but it comes in mid-2028 instead of mid-2027? You go bankrupt.

</details>

**Dwarkesh**: 所以如果你的预测是一到三年，似乎你应该希望最迟在 2029 年拥有 10 万亿美元的算力？即使在你陈述的时间表的最长版本中，你正在增加构建的算力似乎也不相符。是什么让你这么想？人类的工资，比方说，大约是每年 50 万亿美元——

<details>
<summary>Original English</summary>

**Dwarkesh**: So if your projection is one to three years, it seems like you should want $10 trillion of compute by 2029 at the latest? Even in the longest version of the timelines you state, the compute you are ramping up to build doesn't seem in accordance. What makes you think that? Human wages, let's say, are on the order of $50 trillion a year—

</details>

**Dario**: 所以我不会具体谈论 Anthropic，但如果你谈论整个行业，该行业今年构建的算力数量可能，姑且说是 10-15 吉瓦（gigawatts）。它每年大约增长 3 倍。所以明年是 30-40 吉瓦。2028 年可能是 100 吉瓦。2029 年可能是 300 吉瓦。我在脑子里算了一下，每吉瓦成本可能在 100 亿美元左右，大约每年 100-150 亿美元。你把这些加起来，你得到的正是你所描述的。你得到的正是那个数字。到 2028 年或 2029 年，你每年将获得数万亿美元。

<details>
<summary>Original English</summary>

**Dario**: So I won't talk about Anthropic in particular, but if you talk about the industry, the amount of compute the industry is building this year is probably, call it, 10-15 gigawatts. It goes up by roughly 3x a year. So next year's 30-40 gigawatts. 2028 might be 100 gigawatts. 2029 might be like 300 gigawatts. I'm doing the math in my head, but each gigawatt costs maybe $10 billion, on the order of $10-15 billion a year. You put that all together and you're getting about what you described. You’re getting exactly that. You're getting multiple trillions a year by 2028 or 2029.

</details>

**Dwarkesh**: 你得到的正是你预测的。那是整个行业的。

<details>
<summary>Original English</summary>

**Dwarkesh**: You're getting exactly what you predict. That's for the industry.

</details>

**Dario**: 那是整个行业的，没错。

<details>
<summary>Original English</summary>

**Dario**: That's for the industry, that’s right.

</details>

**Dwarkesh**: 假设 Anthropic 的算力保持每年 3 倍的增长，然后到 2027-28 年，你们有 10 吉瓦。乘以，如你所说，100 亿美元。那么每年就是 1000 亿美元。但你又说 2028 年的 TAM 是 2000 亿美元。

<details>
<summary>Original English</summary>

**Dwarkesh**: Suppose Anthropic's compute keeps 3x-ing a year, and then by 2027-28, you have 10 gigawatts. Multiply that by, as you say, $10 billion. So then it's like $100 billion a year. But then you're saying the TAM by 2028 is $200 billion.

</details>

**Dario**: 同样，我不想给出 Anthropic 的确切数字，但这些数字太小了。

<details>
<summary>Original English</summary>

**Dario**: Again, I don't want to give exact numbers for Anthropic, but these numbers are too small.

</details>

**Dwarkesh**: 好的，有意思。你告诉投资者，你们计划从 2028 年开始盈利。这一年我们可能会获得作为数据中心的天才国度。这现在将解锁医学、健康和新技术领域的所有这些进展。这难道不正是你们想要对业务进行再投资并建立更大“国度”以便它们能做出更多发现的时候吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, interesting. You've told investors that you plan to be profitable starting in 2028. This is the year when we're potentially getting the country of geniuses as a data center. This is now going to unlock all this progress in medicine and health and new technologies. Wouldn't this be exactly the time where you'd want to reinvest in the business and build bigger "countries" so they can make more discoveries?

</details>

**Dario**: 盈利能力在这个领域是一种很奇怪的东西。我不认为在这个领域，盈利能力实际上是衡量削减开支与投资业务的标准。让我们建立一个模型。我实际上认为，当你低估了你将获得的需求量时，就会产生利润；当你高估了你将获得的需求量时，就会产生亏损，因为你是提前购买数据中心的。这样想吧。同样，这些都是程式化的事实。这些数字并不准确。我只是想在这里建立一个玩具模型。假设你一半的算力用于训练，一半的算力用于推理。推理的毛利率超过 50%。所以这意味着，如果你处于稳定状态，你建立了一个数据中心，如果你确切地知道你将获得的需求，你将获得一定数量的收入。假设你每年支付 1000 亿美元用于算力。在 500 亿美元的基础上，你支撑了 1500 亿美元的收入。另外 500 亿美元用于训练。基本上你是盈利的，你赚了 500 亿美元的利润。这就是今天该行业的经济学，或者不是今天，而是我们对未来一两年的预测。唯一使情况并非如此的是，如果你获得的需求低于 500 亿美元。那么你就有超过 50% 的数据中心用于研究，你就不盈利了。所以你训练了更强大的模型，但你不盈利。如果你获得的需求比你想象的要多，那么研究就会被挤压，但你能够支撑更多的推理，你就更盈利。也许我解释得不好，但我想说的是，你首先决定算力的数量。然后你对推理与训练有一个目标期望，但这取决于需求。它不是由你决定的。

<details>
<summary>Original English</summary>

**Dario**: Profitability is this kind of weird thing in this field. I don't think in this field profitability is actually a measure of spending down versus investing in the business. Let's just take a model of this. I actually think profitability happens when you underestimated the amount of demand you were going to get and loss happens when you overestimated the amount of demand you were going to get, because you're buying the data centers ahead of time. Think about it this way. Again, these are stylized facts. These numbers are not exact. I'm just trying to make a toy model here. Let's say half of your compute is for training and half of your compute is for inference. The inference has some gross margin that's more than 50%. So what that means is that if you were in steady-state, you build a data center and if you knew exactly the demand you were getting, you would get a certain amount of revenue. Let’s say you pay $100 billion a year for compute. On $50 billion a year you support $150 billion of revenue. The other $50 billion is used for training. Basically you’re profitable and you make $50 billion of profit. Those are the economics of the industry today, or not today but where we’re projecting forward in a year or two. The only thing that makes that not the case is if you get less demand than $50 billion. Then you have more than 50% of your data center for research and you're not profitable. So you train stronger models, but you're not profitable. If you get more demand than you thought, then research gets squeezed, but you're kind of able to support more inference and you're more profitable. Maybe I'm not explaining it well, but the thing I'm trying to say is that you decide the amount of compute first. Then you have some target desire of inference versus training, but that gets determined by demand. It doesn't get determined by you.

</details>

**Dwarkesh**: 我听到的是，你预测盈利的原因是你们在系统性地对算力投资不足？

<details>
<summary>Original English</summary>

**Dwarkesh**: What I'm hearing is the reason you're predicting profit is that you are systematically underinvesting in compute?

</details>

**Dario**: 不，不，不。我是说这很难预测。关于 2028 年以及它何时会发生的这些事情，那是我们尽最大努力向投资者做出的交代。所有这些事情都非常不确定，因为存在不确定性圆锥。如果收入增长足够快，我们可能会在 2026 年盈利。如果我们高估或低估了下一年，情况可能会发生剧烈波动。

<details>
<summary>Original English</summary>

**Dario**: No, no, no. I'm saying it's hard to predict. These things about 2028 and when it will happen, that's our attempt to do the best we can with investors. All of this stuff is really uncertain because of the cone of uncertainty. We could be profitable in 2026 if the revenue grows fast enough. If we overestimate or underestimate the next year, that could swing wildly.

</details>

**Dwarkesh**: 我想表达的是，你脑海中有一个商业模型，即投资、投资、再投资，获得规模，然后变得盈利。有一个单一的转折点。

<details>
<summary>Original English</summary>

**Dwarkesh**: What I'm trying to get at is that you have a model in your head of a business that invests, invests, invests, gets scale and then becomes profitable. There's a single point at which things turn around.

</details>

**Dario**: 我不认为这个行业的经济学是这样运作的。

<details>
<summary>Original English</summary>

**Dario**: I don't think the economics of this industry work that way.

</details>

**Dwarkesh**: 我明白了。所以如果我理解正确的话，你是在说，由于我们应该获得的算力数量和我们实际获得的算力数量之间存在差异，我们在某种程度上被迫实现了盈利。但这并不意味着我们将继续盈利。我们将对这笔钱进行再投资，因为现在 AI 已经取得了如此大的进展，我们想要一个更大的天才国度。所以回到收入很高，但亏损也很高的情况。

<details>
<summary>Original English</summary>

**Dwarkesh**: I see. So if I'm understanding correctly, you're saying that because of the discrepancy between the amount of compute we should have gotten and the amount of compute we got, we were sort of forced to make profit. But that doesn't mean we're going to continue making profit. We're going to reinvest the money because now AI has made so much progress and we want a bigger country of geniuses. So back into revenue is high, but losses are also high.

</details>

**Dario**: 如果我们每年都能准确预测需求，我们每年都会盈利。因为将大约 50% 的算力用于研究，加上高于 50% 的毛利率，以及正确的预测需求，就会带来利润。我认为这就是那种存在的盈利商业模式，但它被这些提前建设和预测错误所掩盖了。

<details>
<summary>Original English</summary>

**Dario**: If every year we predict exactly what the demand is going to be, we'll be profitable every year. Because spending 50% of your compute on research, roughly, plus a gross margin that's higher than 50% and correct demand prediction leads to profit. That's the profitable business model that I think is kind of there, but obscured by these building ahead and prediction errors.

</details>

**Dwarkesh**: 我想你是把 50% 当作一个给定的常数，而事实上，如果 AI 进展很快，你可以通过扩大规模来加快进展，你应该投入超过 50% 并且不追求盈利。

<details>
<summary>Original English</summary>

**Dwarkesh**: I guess you're treating the 50% as a sort of given constant, whereas in fact, if AI progress is fast and you can increase the progress by scaling up more, you should just have more than 50% and not make profit.

</details>

**Dario**: 但我要说的是。你可能想要扩大规模。记住规模的对数收益。如果 70% 会让你通过 1.4 倍的系数得到一个稍微小一点的模型……那额外的 200 亿美元，那里的每一美元对你来说价值都要小得多，因为对数线性的设置。所以你可能会发现，把这 200 亿美元投资于提供推理服务，或者雇佣更擅长他们工作的工程师会更好。所以我说 50% 的原因是……那不完全是我们的目标。它不会完全是 50%。它可能会随着时间的推移而变化。我想说的是对数线性回报，它导致的结果是你花费了业务的某个比例。比如不是 5%，也不是 95%。然后你就会遇到边际收益递减。

<details>
<summary>Original English</summary>

**Dario**: But here's what I'll say. You might want to scale it up more. Remember the log returns to scale. If 70% would get you a very little bit of a smaller model through a factor of 1.4x... That extra $20 billion, each dollar there is worth much less to you because of the log-linear setup. So you might find that it's better to invest that $20 billion in serving inference or in hiring engineers who are kind of better at what they're doing. So the reason I said 50%... That's not exactly our target. It's not exactly going to be 50%. It’ll probably vary over time. What I'm saying is the log-linear return, what it leads to is you spend of order one fraction of the business. Like not 5%, not 95%. Then you get diminishing returns.

</details>

**Dwarkesh**: 我觉得很奇怪，我竟然在说服 Dario 相信 AI 的进步之类的。好吧，你不投资研究是因为它有边际收益递减，但你投资于你提到的其他事情。

<details>
<summary>Original English</summary>

**Dwarkesh**: I feel strange that I'm convincing Dario to believe in AI progress or something. Okay, you don't invest in research because it has diminishing returns, but you invest in the other things you mentioned.

</details>

**Dario**: 我认为宏观层面的利润——同样，我谈论的是边际收益递减，但那是在你每年花费 500 亿美元之后。

<details>
<summary>Original English</summary>

**Dario**: I think profit at a sort of macro level— Again, I'm talking about diminishing returns, but after you're spending $50 billion a year.

</details>

**Dwarkesh**: 我确信你会提出这一点，但对一个天才的边际收益递减可能会非常高。

<details>
<summary>Original English</summary>

**Dwarkesh**: This is a point I'm sure you would make, but diminishing returns on a genius could be quite high.

</details>

**Dario**: 更一般地说，在市场经济中什么是利润？利润基本上是在说，市场上的其他公司能用这笔钱做比我更多的事情。抛开 Anthropic 不谈。我不想提供关于 Anthropic 的信息。这就是我给出这些程式化数字的原因。但让我们推导一下行业的均衡。为什么不是每个人都把 100% 的算力花在训练上而不服务任何客户呢？这是因为如果他们没有获得任何收入，他们就无法筹集资金，他们就无法达成算力交易，他们第二年就无法购买更多的算力。所以会有一个均衡，每家公司在训练上的花费都少于 100%，当然在推理上的花费也少于 100%。应该很清楚为什么你不只是提供当前模型的服务而不再训练另一个模型，因为那样你就没有任何需求，因为你会落后。所以存在某种均衡。它不会是 10%，也不会是 90%。作为一种程式化的事实，我们姑且说是 50%。这就是我想表达的。我认为我们将处于这样一种情况：你在训练上花费多少的均衡点，低于你能够从算力中获得的毛利率。所以底层的经济学是盈利的。问题是，当你在购买下一年的算力时，你面临着这种地狱般的需求预测问题，你可能猜低了，非常盈利但没有算力用于研究。或者你可能猜高了，你不盈利，但你拥有世界上所有的算力用于研究。这说得通吗？仅仅作为该行业的一个动态模型？

<details>
<summary>Original English</summary>

**Dario**: More generally, what is profit in a market economy? Profit is basically saying other companies in the market can do more things with this money than I can. Put aside Anthropic. I don't want to give information about Anthropic. That’s why I'm giving these stylized numbers. But let's just derive the equilibrium of the industry. Why doesn't everyone spend 100% of their compute on training and not serve any customers? It's because if they didn't get any revenue, they couldn't raise money, they couldn't do compute deals, they couldn't buy more compute the next year. So there's going to be an equilibrium where every company spends less than 100% on training and certainly less than 100% on inference. It should be clear why you don't just serve the current models and never train another model, because then you don't have any demand because you'll fall behind. So there's some equilibrium. It's not gonna be 10%, it's not gonna be 90%. Let's just say as a stylized fact, it's 50%. That's what I'm getting at. I think we're gonna be in a position where that equilibrium of how much you spend on training is less than the gross margins that you're able to get on compute. So the underlying economics are profitable. The problem is you have this hellish demand prediction problem when you're buying the next year of compute and you might guess under and be very profitable but have no compute for research. Or you might guess over and you are not profitable and you have all the compute for research in the world. Does that make sense? Just as a dynamic model of the industry?

</details>

**Dwarkesh**: 也许退一步讲，我并不是说我认为“天才国度”会在两年内到来，因此你应该购买这些算力。对我来说，你得出的最终结论非常有道理。但那是因为似乎“天才国度”很难实现，还有很长的路要走。所以退一步讲，我想表达的更多是，你的世界观似乎与那些说“我们距离一个创造数万亿美元价值的世界还有 10 年”的人是兼容的。

<details>
<summary>Original English</summary>

**Dwarkesh**: Maybe stepping back, I'm not saying I think the "country of geniuses" is going to come in two years and therefore you should buy this compute. To me, the end conclusion you're arriving at makes a lot of sense. But that's because it seems like "country of geniuses" is hard and there's a long way to go. So stepping back, the thing I'm trying to get at is more that it seems like your worldview is compatible with somebody who says, "We're like 10 years away from a world in which we're generating trillions of dollars of value."

</details>

**Dario**: 那根本不是我的观点。所以我再做一个预测。我很难想象在 2030 年之前不会有数万亿美元的收入。我可以构建一个看似合理的世界。也许需要三年时间。那将是我认为合理的最晚时间。比如在 2028 年，我们获得了真正的“数据中心里的天才国度”。到 2028 年，收入将达到数千亿美元的低位，然后天才国度将其加速到数万亿。我们基本上处于扩散的缓慢一端。需要两年的时间才能达到数万亿。那将是一个需要到 2030 年的世界。我怀疑即使将技术指数和扩散指数结合起来，我们也会在 2030 年之前达到目标。

<details>
<summary>Original English</summary>

**Dario**: That's just not my view. So I'll make another prediction. It is hard for me to see that there won't be trillions of dollars in revenue before 2030. I can construct a plausible world. It takes maybe three years. That would be the end of what I think it's plausible. Like in 2028, we get the real "country of geniuses in the data center". The revenue's going into the low hundreds of billions by 2028, and then the country of geniuses accelerates it to trillions. We’re basically on the slow end of diffusion. It takes two years to get to the trillions. That would be the world where it takes until 2030. I suspect even composing the technical exponential and diffusion exponential, we’ll get there before 2030.

</details>

**Dwarkesh**: 所以你提出了一个 Anthropic 盈利的模型，因为从根本上说，我们似乎处于一个算力受限的世界。所以最终我们不断增加算力——

<details>
<summary>Original English</summary>

**Dwarkesh**: So you laid out a model where Anthropic makes profit because it seems like fundamentally we're in a compute-constrained world. So eventually we keep growing compute—

</details>

**Dario**: 我认为利润的来源是……同样，让我们把整个行业抽象化。让我们想象我们在经济学教科书里。我们有少数几家公司。每家公司可以投资有限的金额。每家公司可以将一部分投资于研发。他们有提供服务的边际成本。该边际成本的毛利润率非常高，因为推理是高效的。存在一些竞争，但模型也是差异化的。公司将竞相推高他们的研究预算。但因为玩家数量很少，我们有……那叫什么来着？古诺均衡（Cournot equilibrium），我想，就是少数公司均衡。关键是它不会均衡到利润率为零的完全竞争状态。如果经济中有三家公司，并且都独立地理性行事，它不会均衡到零。

<details>
<summary>Original English</summary>

**Dario**: I think the way the profit comes is… Again, let's just abstract the whole industry here. Let's just imagine we're in an economics textbook. We have a small number of firms. Each can invest a limited amount. Each can invest some fraction in R&D. They have some marginal cost to serve. The gross profit margins on that marginal cost are very high because inference is efficient. There's some competition, but the models are also differentiated. Companies will compete to push their research budgets up. But because there's a small number of players, we have the... What is it called? The Cournot equilibrium, I think, is what the small number of firm equilibrium is. The point is it doesn't equilibrate to perfect competition with zero margins. If there's three firms in the economy and all are kind of independently behaving rationally, it doesn't equilibrate to zero.

</details>

**Dwarkesh**: 帮我理解一下，因为现在我们确实有三家领先的公司，而且他们没有盈利。那么什么正在改变？

<details>
<summary>Original English</summary>

**Dwarkesh**: Help me understand that, because right now we do have three leading firms and they're not making profit. So what is changing?

</details>

**Dario**: 同样，现在的毛利率是非常正的。正在发生的是两件事的结合。一是我们仍处于算力的指数级扩展阶段。一个模型被训练出来。假设去年训练一个模型花费了 10 亿美元。然后今年它产生了 40 亿美元的收入，推理成本为 10 亿美元。同样，我在这里使用的是程式化的数字，但这将是 75% 的毛利率和这 25% 的税。所以那个模型作为一个整体赚了 20 亿美元。但同时，我们花费 100 亿美元来训练下一个模型，因为存在指数级的扩展。所以公司亏钱了。每个模型都赚钱，但公司亏钱。我谈论的均衡是一个我们拥有“数据中心里的天才国度”的均衡，但那个模型训练的扩展已经更加平衡了。也许它还在上升。我们仍在试图预测需求，但它已经更加平稳了。

<details>
<summary>Original English</summary>

**Dario**: Again, the gross margins right now are very positive. What's happening is a combination of two things. One is that we're still in the exponential scale-up phase of compute. A model gets trained. Let's say a model got trained that costs $1 billion last year. Then this year it produced $4 billion of revenue and cost $1 billion to inference from. Again, I'm using stylized numbers here, but that would be 75% gross margins and this 25% tax. So that model as a whole makes $2 billion. But at the same time, we're spending $10 billion to train the next model because there's an exponential scale-up. So the company loses money. Each model makes money, but the company loses money. The equilibrium I'm talking about is an equilibrium where we have the "country of geniuses in a data center", but that model training scale-up has equilibrated more. Maybe it's still going up. We're still trying to predict the demand, but it's more leveled out.

</details>

**Dwarkesh**: 我对那里的几件事感到困惑。让我们从当前的世界开始。在当前的世界里，你是对的，正如你之前所说，如果你把每个单独的模型当作一家公司，它是盈利的。但当然，作为一家前沿实验室的生产职能的很大一部分是训练下一个模型，对吧？

<details>
<summary>Original English</summary>

**Dwarkesh**: I'm confused about a couple of things there. Let's start with the current world. In the current world, you're right that, as you said before, if you treat each individual model as a company, it's profitable. But of course, a big part of the production function of being a frontier lab is training the next model, right?

</details>

**Dario**: 是的，没错。

<details>
<summary>Original English</summary>

**Dario**: Yes, that's right.

</details>

**Dwarkesh**: 如果你不这样做，那么你就会盈利两个月，然后你就不会有利润率了，因为你将不再拥有最好的模型。但在某个时刻，它达到了它能达到的最大规模。然后在均衡状态下，我们有算法上的改进，但我们花在训练下一个模型上的钱大致等于我们花在训练当前模型上的钱。在某个时刻，经济中的钱会被耗尽。一个固定的劳动力总量谬误……经济会增长，对吧？那是你的预测之一。我们将在太空中拥有数据中心。

<details>
<summary>Original English</summary>

**Dwarkesh**: If you didn't do that, then you'd make profit for two months and then you wouldn't have margins because you wouldn't have the best model. But at some point that reaches the biggest scale that it can reach. And then in equilibrium, we have algorithmic improvements, but we're spending roughly the same amount to train the next model as we spend to train the current model. At some point you run out of money in the economy. A fixed lump of labor fallacy… The economy is going to grow, right? That's one of your predictions. We're going to have the data centers in space.

</details>

**Dario**: 是的，但这是我谈论的主题的另一个例子。在 AI 的推动下，经济增长的速度将比我认为的以往任何时候都要快得多。现在算力每年增长 3 倍。我不认为经济会每年增长 300%。我在《充满爱的恩典机器》中说过，我认为我们可能会获得每年 10-20% 的经济增长，但我们不会获得 300% 的经济增长。所以我认为最终，如果算力成为经济产出的大部分，它将受限于此。

<details>
<summary>Original English</summary>

**Dario**: Yes, but this is another example of the theme I was talking about. The economy will grow much faster with AI than I think it ever has before. Right now the compute is growing 3x a year. I don't believe the economy is gonna grow 300% a year. I said this in "Machines of Loving Grace", I think we may get 10-20% per year growth in the economy, but we're not gonna get 300% growth in the economy. So I think in the end, if compute becomes the majority of what the economy produces, it's gonna be capped by that.

</details>

**Dwarkesh**: 所以让我们假设一个算力保持上限的模型。前沿实验室赚钱的世界是他们继续取得快速进展的世界。因为从根本上说，你的利润率受限于替代方案有多好。所以你能够赚钱是因为你拥有一个前沿模型。如果你没有前沿模型，你就赚不到钱。所以这个模型要求永远不要有稳定状态。你永远不断地取得更多的算法进展。

<details>
<summary>Original English</summary>

**Dwarkesh**: So let's assume a model where compute stays capped. The world where frontier labs are making money is one where they continue to make fast progress. Because fundamentally your margin is limited by how good the alternative is. So you are able to make money because you have a frontier model. If you didn't have a frontier model you wouldn't be making money. So this model requires there never to be a steady state. Forever and ever you keep making more algorithmic progress.

</details>

**Dario**: 我不认为那是真的。我的意思是，我觉得我们像是在上经济学课。

<details>
<summary>Original English</summary>

**Dario**: I don't think that's true. I mean, I feel like we're in an economics class.

</details>

**Dwarkesh**: 你知道 **Tyler Cowen** 的名言吗？我们永远不会停止谈论经济学。

<details>
<summary>Original English</summary>

**Dwarkesh**: Do you know the Tyler Cowen quote? We never stop talking about economics.

</details>

**Dario**: 我们永远不会停止谈论经济学。所以不，我不认为这个领域会成为垄断。我所有的律师都不希望我说“垄断”这个词。但我不认为这个领域会成为垄断。你确实会看到只有少数几个玩家的行业。不是一个，而是少数几个玩家。通常，你获得像 **Facebook** 或 **Meta**——我总是叫他们 Facebook——这样的垄断的方式是这种网络效应。你获得只有少数几个玩家的行业的方式，是非常高的进入成本。云服务就是这样。我认为云服务是这方面的一个很好的例子。云服务领域有三个，也许四个玩家。我认为 AI 也是一样，三个，也许四个。原因是它太昂贵了。运营一家云公司需要太多的专业知识和太多的资本。你必须投入所有的这些资本。除了投入所有这些资本之外，你还必须搞定所有其他这些需要大量技能才能实现的事情。所以如果你去找某人，你说，“我想颠覆这个行业，这里有 1000 亿美元。”你会说，“好吧，我投入 1000 亿美元，并且还打赌你能做所有这些其他人一直在做的其他事情。”结果只是降低了利润。你进入的影响是利润率下降。所以，我们在经济中一直有这样的均衡，即我们有几个玩家。利润不是天文数字。利润率不是天文数字，但它们也不是零。这就是我们在云服务上看到的。云服务是非常无差异化的。模型比云服务更具差异化。每个人都知道 Claude 擅长的事情与 GPT 擅长的事情不同，与 **Gemini** 擅长的事情也不同。不仅仅是 Claude 擅长编程，GPT 擅长数学和推理。它比那更微妙。模型擅长不同类型的编程。模型有不同的风格。我认为这些东西实际上彼此之间有很大的不同，所以我预计会比你在云服务中看到的有更多的差异化。

<details>
<summary>Original English</summary>

**Dario**: We never stop talking about economics. So no, I don't think this field's going to be a monopoly. All my lawyers never want me to say the word "monopoly". But I don't think this field's going to be a monopoly. You do get industries in which there are a small number of players. Not one, but a small number of players. Ordinarily, the way you get monopolies like Facebook or Meta—I always call them Facebook—is these kinds of network effects. The way you get industries in which there are a small number of players, is very high costs of entry. Cloud is like this. I think cloud is a good example of this. There are three, maybe four, players within cloud. I think that's the same for AI, three, maybe four. The reason is that it's so expensive. It requires so much expertise and so much capital to run a cloud company. You have to put up all this capital. In addition to putting up all this capital, you have to get all of this other stuff that requires a lot of skill to make it happen. So if you go to someone and you're like, "I want to disrupt this industry, here's $100 billion." You're like, "okay, I'm putting in $100 billion and also betting that you can do all these other things that these people have been doing." Only to decrease the profit. The effect of your entering is that profit margins go down. So, we have equilibria like this all the time in the economy where we have a few players. Profits are not astronomical. Margins are not astronomical, but they're not zero. That's what we see on cloud. Cloud is very undifferentiated. Models are more differentiated than cloud. Everyone knows Claude is good at different things than GPT is good at, than Gemini is good at. It's not just that Claude's good at coding, GPT is good at math and reasoning. It's more subtle than that. Models are good at different types of coding. Models have different styles. I think these things are actually quite different from each other, and so I would expect more differentiation than you see in cloud.

</details>

**Dario**: 现在，实际上有一个反驳论点。那个反驳论点是，如果生产模型的过程，如果 AI 模型自己能做到这一点，那么这可能会蔓延到整个经济。但这不是将 AI 模型普遍商品化的论点。这有点像是将整个经济同时商品化的论点。我不知道在那个世界上会发生什么，基本上任何人都可以做任何事，任何人都可以构建任何东西，而且任何东西周围都没有护城河。我不知道，也许我们想要那个世界。也许那是这里的最终状态。也许当 AI 模型能做所有事情时，如果我们已经解决了所有的安全和安保问题，那就是经济再次自我扁平化的机制之一