---
author: a16z
date: '2026-03-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zwDmKsnhl08
speaker: a16z
tags:
  - large-language-models
  - agi-limitations
  - bayesian-inference
  - causal-reasoning
  - continual-learning
title: 为什么规模无法解决通用人工智能问题 | Vishal Misra - a16z 秀
summary: 本期访谈中，**Vishal Misra** 深入探讨了当前大语言模型（LLMs）在实现通用人工智能（AGI）方面的根本局限性。Misra 解释了 LLMs 的工作机制，将其描述为在一个巨大稀疏矩阵中进行的**贝叶斯更新**，并展示了它们的上下文学习能力。他指出，LLMs 擅长处理**关联**而非**因果关系**，并且缺乏人类的**可塑性**和**模拟**能力。他提出了实现 AGI 的两大挑战：实现**持续学习**和从**关联**转向**因果模型**，并以**爱因斯坦**的相对论和**Donald Knuth** 的汉密尔顿循环问题为例，阐述了 LLMs 无法创造新“流形”的局限性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Vishal Misra
  - Judea Pearl
  - Donald Knuth
  - Albert Einstein
  - Ramanujan
  - Demis Hassabis
companies_orgs:
  - Anthropic
  - ESPN
  - OpenAI
  - DeepMind
  - Google Research
  - Columbia University
products_models:
  - Claude Code
  - Cohere
  - GPT-3
  - ChatGPT
  - TokenProbe
  - Mamba
  - LSTMs
  - MLPs
  - Gemini
media_books: []
status: evergreen
---
### LLM 的本质与 AGI 的界限

**Vishal Misra**: **Anthropic** 生产出色的产品，**Claude Code** 很棒，**Cohere** 也很棒。但它们只是硅晶粒在进行矩阵乘法。它们没有意识，也没有内在的独白。你拿一个大语言模型，用 1916 年或 1911 年之前的物理学知识训练它，看看它能否提出**相对论**。如果能，那我们就有 **AGI** 了。

<details>
<summary>Original English</summary>

**Vishal Misra**: Anthropic makes great products. Claude Code is fantastic. Cohere is fantastic. But they are grains of silicon doing matrix multiplication. They don't have consciousness. They don't have an inner monologue. You take an LLM and train it on pre 1916 or 1911 physics and see if it can come up with the theory of relativity. If it does, then we have AGI.

</details>

**主持人**: 顺便说一句，就在今天，**Dario** 据称说你不能排除它们有意识的可能性。你可以排除它们的成本。我认为，要达到所谓的 **AGI**，我认为有两件事需要发生。

<details>
<summary>Original English</summary>

**主持人**: Just today, by the way, Dario allegedly said that you can't rule out that they're conscious. You can rule out their cost. I think I mean come on to get to what is called AGI. I think there are two things that need to happen. One is

</details>

**主持人**: **Vishal**，很高兴你再次来到这里。

<details>
<summary>Original English</summary>

**主持人**: Michelle. It's great to have you in again.

</details>

**Vishal Misra**: 很高兴回来。这是我最喜欢的话题之一，那就是大语言模型（**LLM**）究竟是如何工作的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Great to be back. This is one of my favorite topics which is um how do LLM actually work?

</details>

**主持人**: 我认为，在我看来，你在这方面做得最好，对它进行了建模。

<details>
<summary>Original English</summary>

**主持人**: And I think that uh you in my opinion you've done kind of the best work on this modeling it out.

</details>

**Vishal Misra**: 谢谢。对于那些没有看过原始版本的人，也许值得快速回顾一下你走到这一步的背景，然后我们再深入探讨你目前正在做的工作。

<details>
<summary>Original English</summary>

**Vishal Misra**: Thank you. For those that did not see the original um one, maybe it's probably worth doing just a quick background on kind of what led you to this point and then we'll just go into the current work that you've been doing.

</details>

### GPT-3 与上下文学习的早期探索

**Vishal Misra**: 五年前，当 **GPT-3** 首次发布时，我获得了早期访问权限，并开始试用它。我当时试图解决一个与查询板球数据库相关的问题。我让 **GPT-3** 进行了**上下文学习**，即**少样本学习**。这对我来说，至少是第一个已知的 **RAG**（检索增强生成）实现，我用它来解决查询问题，让 **GPT-3** 将自然语言翻译成可以用来查询一个它一无所知的数据库。我无法访问 **GPT-3** 的内部结构，但我仍然能够用它来解决这个问题。所以，它运行得非常出色。我们在 2021 年 9 月在 **ESPN** 部署了这项技术。

<details>
<summary>Original English</summary>

**Vishal Misra**: 5 years ago when GPT-3 was first released, uh I got early access to it and I started playing with it and I was trying to solve a problem related to quering a cricket database. Yeah. And I got GPT-3 to do in context learning, few short learning. And you know it was kind of the first at least to to me it was the first known uh implementation of RAG retrieval augmented generation which I used to solve this problem of uh querying getting GPT-3 to translate natural language into something that could be used to query a database that GPT-3 had no idea about. I had no access to GPT-3's internals, but I was still able to use it to solve that problem. So, it it it worked beautifully. Uh we we deployed uh this uh in production at ESPN in September 21. But

</details>

**主持人**: 哇，哇。你在 2021 年做了 **RAG** 的首次实现。

<details>
<summary>Original English</summary>

**主持人**: Wow. Wow. You you did the first implementation of Frag in 2021.

</details>

**Vishal Misra**: 不，不，不，是在 2020 年。

<details>
<summary>Original English</summary>

**Vishal Misra**: No, no, no. In 2020.

</details>

**主持人**: 2020 年。

<details>
<summary>Original English</summary>

**主持人**: 2020.

</details>

**Vishal Misra**: 2020 年。我让它运行起来了，但当你和 **ESPN** 的所有律师谈过，并将其投入生产时，花了一段时间。但在 2020 年 10 月，我们，或者说我，就有了这个运行中的架构。但它能工作后，我很惊讶它竟然能工作。我想了解它是如何工作的。我查阅了所有关于注意力机制的深度论文，以及所有其他深度学习架构论文，但我无法理解它为什么能工作。

<details>
<summary>Original English</summary>

**Vishal Misra**: 2020. I got it working and by the time you talked to all the lawyers at ESPN and you know, productionize it, it took it took a while. But October 2020 we had well I had this architecture working but after I got it to work I was amazed that it worked. I wanted to understand how it worked and I looked at you know the attention is all your deep papers and all the other sort of deep learning architecture papers and I couldn't understand why it worked.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 所以我开始深入研究构建一个数学模型。

<details>
<summary>Original English</summary>

**Vishal Misra**: So then I started getting sort of deep into building a mathematical model.

</details>

**主持人**: 是的。现在你发表了一系列论文。我读的第一篇是你提出**矩阵抽象**的那一篇。所以我们也许可以谈谈那篇，然后再谈谈最近的工作。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And now you published a series of papers. The first one that I read was the one where you had kind of your matrix kind of abstraction. So maybe we'll talk about that and then we'll talk about the more recent

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah.

</details>

**主持人**: 工作。

<details>
<summary>Original English</summary>

**主持人**: work.

</details>

### LLM 的矩阵抽象模型

**Vishal Misra**: 那么，我们也许可以从第一篇开始，那就是你试图描述、试图提出一个关于 **LLM** 如何工作的数学模型。

<details>
<summary>Original English</summary>

**Vishal Misra**: So perhaps we'll just start with the first one which is you were trying to you were trying to describe you're trying to come up with a mathematical model of how LLM works.

</details>

**主持人**: 是的。你提出的对我很帮助的是，当时你实际上正在试图弄清楚**上下文学习**是如何工作的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And you had which was very helpful to me which was um and at the time you were actually trying to like figure out how incontext learning was working.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yes. Yeah.

</details>

**主持人**: 你为 **LLM** 提出了一个抽象概念，它基本上是一个非常非常大的**矩阵**，你用它来描述。所以你也许可以快速地介绍一下那项工作。

<details>
<summary>Original English</summary>

**主持人**: And you came up with an abstraction for LLMs which is basically this very very large matrix and you use that to describe. So maybe you can kind of walk through that work very quick.

</details>

**Vishal Misra**: 当然。是的，所以你想象一个巨大的矩阵，矩阵的每一行对应一个**提示**（prompt）。这些 **LLM** 的工作方式是，给定一个提示，它们会构建下一个**词元**（token）的**概率分布**。下一个词元就是下一个词。所以每个 **LLM** 都有一个**词汇表**，例如 **GPT** 及其变体有一个大约 50,000 个词元的词汇表。

<details>
<summary>Original English</summary>

**Vishal Misra**: Sure. Yeah. So so what you do is you you imagine this huge gigantic matrix where every row of the matrix corresponds to a prompt. And the way these LLMs work is given a prompt they construct a distribution of probabilities of the next token. Next token is next word. So every LLM has a vocabulary, you know, GPD and its variants have a vocabulary of about 50,000 tokens.

</details>

**主持人**: 所以给定一个提示，它会生成下一个词元应该是什么的分布。然后所有这些模型都从那个分布中采样。

<details>
<summary>Original English</summary>

**主持人**: So given a prompt, it'll come up with a distribution of what the next token should be. And then all these models sample from that distribution.

</details>

**Vishal Misra**: 是的，那就是**后验分布**。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah. So that's the posterior distribution.

</details>

**主持人**: 那就是后验分布，对吗？那就是 **LLM** 的工作方式。所以这个矩阵的想法是，对于每一个可能的词元组合，也就是一个提示，都有一行。

<details>
<summary>Original English</summary>

**主持人**: That's the posterior distribution, right? That that's how LLM work. And so the idea of this matrix is matrix is for every possible combination of tokens which is a prompt, there's a row.

</details>

**Vishal Misra**: 是的，是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah. Yeah.

</details>

**主持人**: 列是词汇表上的分布。

<details>
<summary>Original English</summary>

**主持人**: And the columns are a distribution over the vocabulary.

</details>

**Vishal Misra**: 所以如果你有一个 50,000 个可能词元的词汇表，它就是这 50,000 个词元上的分布。

<details>
<summary>Original English</summary>

**Vishal Misra**: So if you have like a vocabulary of 50,000 possible tokens, it's a distribution over those 50000 tokens.

</details>

**主持人**: 而分布，它只是概率。

<details>
<summary>Original English</summary>

**主持人**: And by distribution, it's just the probability

</details>

**Vishal Misra**: 只是概率。抱歉，是的。只是下一个词元是这个而不是那个的概率。

<details>
<summary>Original English</summary>

**Vishal Misra**: just the probability. Sorry. Yeah. Just the probability that the next token should be this versus that.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Y.

</details>

**Vishal Misra**: 所以这就是这个想法。当你开始这样看待它时，至少对我这样想建模的人来说，事情变得更清楚了。发生了什么？具体来说，假设你有一个例子，你的提示只有一个词：“蛋白质”。如果你看它之后下一个词元或下一个词的分布，大部分概率会是零，但你会在两个词上看到非零的非平凡概率，一个是“合成”（synthesis），另一个是“奶昔”（shake）。

<details>
<summary>Original English</summary>

**Vishal Misra**: Uh so that that's sort of the idea and and when you start viewing it that way, it makes things at least clearer to people like me who want to model it. uh what what's happening? So concretely let's say you have an example that uh let's say your prompt is just one word protein. Yeah. So if you look at the distribution of the next word next token after that uh most of the uh probabilities would be zero but you'd have non zero non-trivial probabilities on let's say two words one is synthesis the other is shake

</details>

**主持人**: 对，现在 **LLM** 将会采样“合成”或“奶昔”作为下一个词元。

<details>
<summary>Original English</summary>

**主持人**: right and now the LLM is going to sample synthesis sample uh this next token and man pick synthesis or shake

</details>

**Vishal Misra**: 或者你作为一个人类会给出提示“蛋白质奶昔”或“蛋白质合成”。现在，取决于你选择“合成”还是“奶昔”，下一行看起来会非常不同，对吗？如果你选择“蛋白质合成”，那么高概率的词都会与生物学相关。但如果你选择“蛋白质奶昔”，那就会全是关于健身房、锻炼和所有健美方面的东西。所以，“合成”或“奶昔”完全改变了接下来会发生什么。

<details>
<summary>Original English</summary>

**Vishal Misra**: or protein synthesis. Now, depending on whether you pick synthesis or shake, the next that row looks very different, right? If you pick protein synthesis, the terms that would have a high probability would be all concerned with biology, right? But if you pick protein shake, it'll all be about gyms and exercise and all, you know, bodybuilding stuff. So, that synthesis or shake completely changes what comes next.

</details>

**主持人**: 是的。所以这是一个你可以说是**贝叶斯更新**的例子。你从“蛋白质”开始，你有一个先验，认为“蛋白质”之后会发生什么。一旦你获得新的证据，下一个词是“合成”或“奶昔”，你就会完全更新分布。所以现在你可以想象，整个 **LLM** 就是这个巨大的矩阵，其中每一行都是“蛋白质”、“蛋白质奶昔”、“蛋白质合成”、“猫坐在”……

<details>
<summary>Original English</summary>

**主持人**: Yeah. So this is an example of uh you can say bijian updating. You start with protein you have a prior that after protein this is going to happen. As soon as you get new evidence then the next term is synthesis or shake you completely update the distribution. So now you can imagine that the whole the the entirety of LLM is this giant matrix where you have every row protein protein shake protein synthesis the cat sat on the

</details>

**Vishal Misra**: 还有“Humpty Dumpty”等等。现在，考虑到这些 **LLM** 的词汇量，假设是 50,000 个词元，以及上下文窗口。例如，**ChatGPT** 的第一个版本有一个 8,000 个词元的上下文窗口。如果你查看 8,000 个词元和 50,000 个词汇表的所有可能组合，这个矩阵中的行数比所有星系中的电子数量还要多。所以，这些 **LLM** 无法精确地表示它。幸运的是，这个矩阵非常稀疏。为什么？因为这些词元的任意组合都是胡言乱语，我们在现实生活中从不会使用。

<details>
<summary>Original English</summary>

**Vishal Misra**: you know Humpty Dumpty blah blah blah now given uh the vocabulary of uh these LLM let's say 50,000 and the context window so GPD for instance chat GPD the first version had a context window of 8,000 tokens. Yeah, if you look at all possible combinations of 8,000 tokens and 50,000 uh vocabulary, the number of rows in this matrix is more than the number of electrons across all galaxies. Right? So, so there's no way that these LLMs can represent it exactly now. Fortunately, this matrix is very sparse. Why? Because you know an arbitrary combination of these tokens is gibberish. We're not never going to use that in natural in real life.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 而且，列也主要是零。

<details>
<summary>Original English</summary>

**Vishal Misra**: Also, the columns are also mainly zero.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 对。如果你有“蛋白质”，那么后面就不会有许多任意的数字或任意的词。它在行和列上都非常稀疏。所以，从某种抽象的角度来看，所有这些 **LLM** 正在做的是，它们正在为这个矩阵提供一个**压缩表示**。当你给出一个提示时，它们会尝试近似真实的分布应该是什么，并尝试生成它。至少在我看来，这就是它的核心。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right. If you have protein, then you won't have lots of, you know, you won't have arbitrary numbers or arbitrary words after that. It's very sparse both in rows and in columns. So I in kind of an abstract way what all these LLMs are doing is coming coming up with a compressed representation of this matrix and when you give a prompt they try to approximate what the true distribution should have been and try to generate it that that's what uh in my mind at least it boils up to

</details>

**主持人**: 根据我的理解。所以如果你有一行是“蛋白质”，然后另一行是“蛋白质奶昔”。

<details>
<summary>Original English</summary>

**主持人**: just from my understanding. So if you have a row of uh protein and then you have one with protein shake

</details>

**Vishal Misra**: 嗯。

<details>
<summary>Original English</summary>

**Vishal Misra**: Mhm.

</details>

**主持人**: “蛋白质奶昔”是“蛋白质”的一个子集，还是不同的？

<details>
<summary>Original English</summary>

**主持人**: is protein shake a subset of protein or is it different?

</details>

**Vishal Misra**: 它是不同的。它是从“蛋白质”的延续。

<details>
<summary>Original English</summary>

**Vishal Misra**: It's different. It's a continuation from

</details>

**主持人**: 我明白了。

<details>
<summary>Original English</summary>

**主持人**: I see.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah.

</details>

**主持人**: 对。不，我只是说，实际的后验分布是一个子集吗？

<details>
<summary>Original English</summary>

**主持人**: Right. No, but I'm just saying like the actual the actual posterior distribution is that a subset?

</details>

**Vishal Misra**: 你可以说它是一个子集，对吗？如果你有“蛋白质”，那么“蛋白质奶昔”和“蛋白质合成”都是从“蛋白质”的延续。所以“合成”和“奶昔”都有非零概率。所以你可以，是的，你可以把它看作是一个子集。

<details>
<summary>Original English</summary>

**Vishal Misra**: You you can say it's a subset, right? Uh if you have protein then protein shake and protein synthesis are all continuations from protein. So both synthesis and shake have non-zero probabilities. So you can yeah you can think of it as somewhat a subset

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right

</details>

### 上下文学习的原理与案例

**主持人**: 你用这种方法来描述**上下文学习**是如何工作的。所以也许首先描述一下什么是上下文学习，然后是你从中得出的结论。所以上下文学习是当你向 **LLM** 展示一些它以前从未见过的事物时。你给它几个例子，说明这是它想要做的，这是你正在尝试做的事情。然后你给出一个与你展示的例子相关的新问题，**LLM** 会实时学习它应该做什么，并解决这个问题。顺便说一句，我第一次看到这个时，它完全震撼了我的思维。我实际上在第一次学习它时使用了你的 **DSL**。

<details>
<summary>Original English</summary>

**主持人**: you you know you use this approach to describe how in context learning works and so maybe first describe what in context learning is and then kind of the conclusion that you came from that. So eight context learning is when you uh show the LLM something it has kind of never seen before. You give it a few examples of this is what it wants uh this is what you're trying to do. Then you give a new problem which is related to the examples that you have shown and the LLM learns in real time what it's supposed to do and solves that problem. And by the way, the first time I saw this, it absolutely blew my mind. And I actually I actually use your DSL

</details>

**Vishal Misra**: 当我第一次学习它时。

<details>
<summary>Original English</summary>

**Vishal Misra**: when I was like first learning about it.

</details>

**主持人**: 所以，这种 **DSL** 的东西简直太疯狂了，它竟然能工作。

<details>
<summary>Original English</summary>

**主持人**: So maybe like kind of like the DSL thing is just just crazy this works at all.

</details>

**Vishal Misra**: 它能工作简直令人难以置信。回到那个板球问题，在 90 年代中期，我是一个团队的成员，我们创建了一个名为 **Cricket Info** 的板球门户网站。

<details>
<summary>Original English</summary>

**Vishal Misra**: It's absolutely, you know, mind-blowing that it works. And so going back to that cricket problem was you know in the mid '90s uh I was part of a group that had created this uh cricket portal called cricket info.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 板球是一项非常注重统计数据的运动。你可以想象棒球的统计数据乘以一千倍。我们创建了一个名为 **Stats Guru** 的在线可搜索数据库，你可以在其中搜索任何与板球相关的统计数据，它自 2000 年以来一直可用。

<details>
<summary>Original English</summary>

**Vishal Misra**: Uh cricket uh is a very start sport. You know you think baseball multiply by a thousand. at all kinds of stats and we had created this uh online searchable database called stats guru where you could search for anything any stat related to cricket and has been available since 2000

</details>

**主持人**: 但因为你可以查询任何东西，所以所有东西都可用。你如何将这样的东西提供给普通大众呢？他们不会写 **SQL** 查询。

<details>
<summary>Original English</summary>

**主持人**: but because you can query for anything everything was be made available and how do you make something like that available to the general public well they're not going to write SQL queries

</details>

**Vishal Misra**: 当时最好的办法是创建一个网页表单。不幸的是，所有东西都被塞进了那个网页表单里。结果就是，你有大约 20 个下拉菜单，15 个复选框，18 个不同的文本字段。它看起来像一个非常复杂、令人生畏的界面。因此，尽管它能解决或回答任何查询，但几乎没有人使用它。只有极少数的板球球迷使用它，因为它看起来太吓人了。然后 **ESPN** 在 2007 年收购了那个网站。我仍然认识运营那个网站的人，我总是告诉他们，你们为什么不对 **Stats Guru** 做些什么呢？在 2020 年 1 月，**Cricket Info** 的主编 **Sambbal**，他是我的朋友，他来到纽约，我们出去吃饭。我又告诉他，你们为什么不对 **Stats Guru** 做些什么呢？他看着我说，你为什么不对 **Stats Guru** 做些什么呢？他是在开玩笑，但那个想法一直萦绕在我心头。当 **GPT-3** 发布时，我想也许我可以用 **Stats Guru**，用 **GPT-3** 为 **Stats Guru** 创建一个前端。

<details>
<summary>Original English</summary>

**Vishal Misra**: the next best thing at that time was to create a web form unfortunately ally everything was crammed into that web form. So as a result you had like 20 drop downs, 15 checkboxes, 18 different text fields. It looked like a very complicated, daunting interface. So as a result, even though it could solve or it could answer any query, almost no one used it. A vanishingly small percentage of cricket fans use it because it it just looked intimidating. And then ESPN bought that site uh in 2007. I still know people who uh run the site and I always told them you know why don't you do something about stats guru and in January 2020 uh the editor-inchief of cricket info Sambbal he's he's a friend so he came to New York and we had gone out for rings and again I told him you know why don't you do something about stats guru so he looks at me and says why don't you do something about stats guru he was joking but uh that idea kind of stayed with me and when GP3 was released I thought maybe I could use stats guru use GP3 to create a front end for stats guru.

</details>

**主持人**: 所以我所做的是，我设计了一个**领域特定语言**（**DSL**），它将关于板球统计数据的自然语言查询转换为这种 **DSL**。

<details>
<summary>Original English</summary>

**主持人**: And so what I did was uh I designed a DSL a domain specific language which uh converted queries about cricket stats in natural language into this DSL.

</details>

**Vishal Misra**: 不。

<details>
<summary>Original English</summary>

**Vishal Misra**: No.

</details>

**主持人**: 澄清一下，你创建了这个，它不是任何在线训练的一部分，**GPT** 无法看到。

<details>
<summary>Original English</summary>

**主持人**: And to be clear you created this it wasn't like part of like any training that was online that like could have seen.

</details>

**Vishal Misra**: **GPT** 无法看到任何东西。我创建了它。我想，好吧，这说得通。所以我设计了那个 **DSL**，然后我做了**少样本学习**。所以我创建了一个大约 1500 个自然语言查询及其对应的 **DSL** 的数据库。所以当一个新的查询进来时，有人用英语问一个统计问题。我所做的就是，我会遍历自然语言查询，进行**语义搜索**，挑选出最匹配的几个。

<details>
<summary>Original English</summary>

**Vishal Misra**: Nothing GPD could have seen. I created it. I thought okay this makes sense. So I designed that DSL and then I did that few short learning things. So I would so I created about a database of about I would say 1500 natural language queries and the DSL corresponding to that query. So when a new query came in, somebody's asking a stats question in English. What I would do is I would go through the natural language queries, do a semantic search, pick the most closely matching top few.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 然后使用那个自然语言查询及其 **DSL**，并将其作为前缀发送。现在 **GPT-3**，如果你还记得的话，上下文窗口只有 2,000 个词元。

<details>
<summary>Original English</summary>

**Vishal Misra**: Uh and then use that natural language query and its DSL and send that as a prefix. Now GPD3, if you recall, had a context window of only 2,000 tokens.

</details>

**主持人**: 是的。所以你必须非常谨慎地选择例子。但你选择了那些，然后你发送新的查询，**GPT-3** 就会用我设计的 **DSL** 完成它，而直到几毫秒前它从未见过这个 **DSL**。

<details>
<summary>Original English</summary>

**主持人**: Yeah. So you had to be very judicious about which examples that you picked. But you pick that and then you send the new query and GP3 would complete it in the DSL that I had designed which until milliseconds ago it had never seen.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah.

</details>

**主持人**: 我无法访问 **GPT-3** 的内部结构。我无法访问它的权重。

<details>
<summary>Original English</summary>

**主持人**: And I had no access to internals of GPD3. I had no access to the weights.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah.

</details>

**Vishal Misra**: 但它仍然奏效了。所以这就是。

<details>
<summary>Original English</summary>

**Vishal Misra**: But still it worked. So that that's how so

</details>

**主持人**: 所以，根据你关于提示和分布的矩阵例子，我不太清楚像**上下文学习**这样的东西是如何工作的。

<details>
<summary>Original English</summary>

**主持人**: so so it's not obvious to me given your matrix example of like a prompt and then a distribution how something like in context learning

</details>

**Vishal Misra**: 工作。

<details>
<summary>Original English</summary>

**Vishal Misra**: works

</details>

**主持人**: 所以我想你的第一篇论文解决了这个问题。

<details>
<summary>Original English</summary>

**主持人**: would work and so like I think your first paper tackled this problem

</details>

**Vishal Misra**: 对。

<details>
<summary>Original English</summary>

**Vishal Misra**: right

</details>

**主持人**: 那么，你能不能解释一下你对 **LLM** 如何进行上下文学习的理解？

<details>
<summary>Original English</summary>

**主持人**: um and so maybe you could walk through your understanding of how LLMs do in context learning.

</details>

### LLM 的贝叶斯更新能力

**Vishal Misra**: 是的。所以，当你思考**上下文学习**是什么时，它就是当你看到证据时。在第一篇论文中，我还做了什么呢？我以这个板球 **DSL** 例子为例。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah. So, so when you think about what in context learning is is that as you see evidence. So, so you know in the first paper what I also did was I I took this cricket DSL example.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 我描绘了模型在看到越来越多例子时，下一个词元的概率。所以当你第一次向它展示这个 **DSL**，即自然语言和 **DSL** 时，**DSL** 词元的概率非常低，因为 **GPT-3** 从未见过这个东西。当它看到板球问题时，它心里想的是用一个英语答案来继续它。所以高概率的都是英语单词。

<details>
<summary>Original English</summary>

**Vishal Misra**: And I uh I depicted the next token probabilities mhm of the model as it was shown more and more examples. So the first time you show it this DSL the natural language and the DSL the probabilities of the DSL tokens were were extremely low because GP3 had never seen this thing. When it saw the cricket question in its mind it was trying to continue it with an English answer. So the probabilities that were high were all English words.

</details>

**主持人**: 是的。一旦它看到了我的提示，其中包含问题和 **DSL**，下一次我在下一行中提出问题时，**DSL** 词元的概率就开始上升了。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Once it saw my prompt where I had the question and the DSL, the next time I had the question in the next row, the probabilities of the DSL token started going up

</details>

**Vishal Misra**: 随着每一个例子，它都在上升。最终，当我给出新的查询时，它几乎有 100% 的概率得到正确的词元。

<details>
<summary>Original English</summary>

**Vishal Misra**: with every example, it went up and finally when I gave the new query, it was like it had almost 100% probability of getting the right token.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 所以这是一个模型实时更新其**后验概率**的例子。它正在更新其知识，认为“好吧，我看到了证据，这就是我应该做的。”这是一种通俗的说法，说明什么是**贝叶斯推理**。**贝叶斯更新**基本上是你从一个**先验**开始，当你看到新的证据时，你更新你的**后验**。这是数学上的定义。但在英语中，它基本上是你看到一些东西，你看到新的证据，你更新你对正在发生的事情的信念。

<details>
<summary>Original English</summary>

**Vishal Misra**: So this is an example of in real time the model was updating its posterior probability. It was upgrading its knowledge that okay I've seen evidence this is what I'm supposed to do. Now this is a colloquial way of saying what Beijian inference is. Beijian updating basically is you start with a prior when you see a new evidence you update your posterior. That's the mathematical division. But but in in English it's basically you see something you see new evidence you update your belief about what's happening.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 对。所以对我来说很清楚，**LLM** 正在做一些类似于**贝叶斯更新**的事情。所以在第一篇论文中，我提出了这个矩阵公式，我展示了它正在做的事情。它看起来像**贝叶斯更新**。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right. So it was clear to me that LLMs are doing something which resembles Beijian updating. So in that first paper I had this matrix formulation and I showed that you know what it's doing. It looks like Beijian updating.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 然后我们可以谈谈下一系列论文。

<details>
<summary>Original English</summary>

**Vishal Misra**: Then we can come to the sort of next series of papers.

</details>

### 贝叶斯风洞：数学证明 LLM 的贝叶斯性

**主持人**: 对。好的，所以当时对我来说，这似乎是相当确凿的结论。然后你安静了一段时间，我仍然记得那条 **WhatsApp** 消息。你说：“Martin，我现在确切地知道这些东西是如何工作的了。”

<details>
<summary>Original English</summary>

**主持人**: That's right. So okay so I mean it it it seemed pretty conclusive to me at that time and then you went quiet for a while and then I still remember the WhatsApp text. You said Martin I know exactly how these things are working now.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah. Well

</details>

**主持人**: 然后，你发布了一系列论文，简直轰动了互联网。你在 **Twitter** 上超级火爆，我是说，人们真的注意到了。所以我想马上谈谈这个。但在此之前，我记得你的第一篇论文出来时，人们会说：“你知道，这些东西肯定不是**贝叶斯**的。你知道，任何东西都可以被认为是**贝叶斯**的，但它们不是。”你认为为什么会有这种反应，比如，“你知道，有新东西，它们不是**贝叶斯**的”？我是说，我感觉几乎有一种强烈反对，仅仅因为它们被描述为。

<details>
<summary>Original English</summary>

**主持人**: and then and then and then listen you dropped a series of papers that kind of broke the internet. like you went super viral on Twitter like I mean people really noticed. Um uh and so I I want to get to that in just a second. But before that, um I remember when your first paper came out, people would be like, you know, these things are definitely not Beijian. Like, you know, you know, anything could be considered to be Beijian, but they're not. Like, why do you think that there was this reaction to like, you know, there's something new, they're not Beijian? I mean, I felt like there's almost kind of a backlash just because they're being characterized as

</details>

**Vishal Misra**: 是的，是的。我认为整个概率和机器学习领域一直存在**贝叶斯学派**和**频率学派**的阵营。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah. Yeah. I I think this whole world of uh uh probability and machine learning that there have been camps of Beijian and frequentists.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yes.

</details>

**Vishal Misra**: 我不想卷入那种政治斗争，但**贝叶斯**已经变得几乎像人们对此有反应一样。它是那场战争的一部分。

<details>
<summary>Original English</summary>

**Vishal Misra**: And I don't want to get in the middle of that sort of political battle, but Beijian has become like almost like people had a reaction to that. It's it's part of that war.

</details>

**主持人**: 我明白了。

<details>
<summary>Original English</summary>

**主持人**: I see.

</details>

**Vishal Misra**: 所以，这就像是旧的**贝叶斯**与**频率学派**的战争。是的。所以人们只是说：“哦，不，你可以说任何东西都是**贝叶斯**的，对吗？”所以我说：“好吧，也许他们有道理，也许我们说的并不是真正的**贝叶斯**，我们如何证明它是**贝叶斯**的？”

<details>
<summary>Original English</summary>

**Vishal Misra**: So, it's like the old Beijian frequentist type battle. Yeah. So, so people just had oh no you can say anything is Beijian right? So I said okay maybe they have a point maybe what we are saying is not really Beijian how do we prove that it's Beijian

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right

</details>

**Vishal Misra**: 所以首先我必须感谢你和**霍洛维茨**（Horowitz）为此做出的贡献。你知道，当我在第一篇论文中说我展示了这些概率时，那是因为 **OpenAI** 在其 **ChatGPT** 界面中有一个选项可以显示这些概率。然后他们停止了。

<details>
<summary>Original English</summary>

**Vishal Misra**: so then first I have to thank you and and Harovitz for this uh you know when I when I when I said that I in my first paper I showed these probabilities uh it was because open AI had in its chat uh interface uh this option to displays those probabilities then they stopped

</details>

**主持人**: 所以我们无法深入了解发生了什么。出于某种原因，他们停止了。**OpenAI**。我不会深入讨论开放和封闭，但他们停止了。

<details>
<summary>Original English</summary>

**主持人**: so we could not peer inside what's going what's happening for some reason they stopped openai I'm not going to get into the open and close but but they stopped

</details>

**Vishal Misra**: 所以我们开发了自己的界面，它不仅可以让你查看概率，还可以查看下一个词元的**熵**。这是基于一个开源模型吗？

<details>
<summary>Original English</summary>

**Vishal Misra**: so then we developed our own interface which could let you look not only at uh the probabilities but also the entropy of the next token was this on top of an open source model

</details>

**主持人**: 是的，是的。所以你可以加载任何开源模型。但你知道，作为学术界人士，我们没有计算资源。感谢你的慷慨捐赠，我们获得了集群来运行一个叫做 **TokenProbe** 的工具。所以你可以访问 **tokenprobe.cs.columbia.edu**。

<details>
<summary>Original English</summary>

**主持人**: yeah yeah so so you can load any sort of open source model but you know being an academia We didn't have access to compute. Thanks to your generous uh uh donation, we got uh the clusters to run uh over what it's called token probe. So you can go to tokenprobe.cchs.colia.edu.

</details>

**Vishal Misra**: 它还在运行吗？

<details>
<summary>Original English</summary>

**Vishal Misra**: Is it still running?

</details>

**主持人**: 它还在运行。它还在运行，人们会来使用它。我在我的课堂上使用它，让学生做作业。他们编写自己的 **DSL**，他们说这真的帮助他们理解这些 **LLM** 是如何工作的。所以我的 **LLM** 理解实际上来自 **TokenProbe**，只是坐在那里，看着你填写提示时分布的变化。这实际上非常非常启发人。所以对于那些正在听的人。

<details>
<summary>Original English</summary>

**主持人**: It's still running. It's still running and people come to it. Uh I use it in my classes uh to get students to do assignments. They write their own DSLs and you know they say that that that it really helps them understand how these LLMs work. So I literally my understanding of LMS came from token pro just you know sit there and just look at the the distribution as as you filled out a prompt. It's actually very very enlightening. So for those of you that are listening um

</details>

**Vishal Misra**: 网址是什么？

<details>
<summary>Original English</summary>

**Vishal Misra**: what's the URL again?

</details>

**主持人**: **TokenProbe**。

<details>
<summary>Original English</summary>

**主持人**: Token probe

</details>

**Vishal Misra**: **tokenprobe.cs.columbia.edu**。

<details>
<summary>Original English</summary>

**Vishal Misra**: token probe.cs.colia.edu.

</details>

**主持人**: 是的，去看看吧。它实际上非常非常有用，可以看到当你填写提示时，概率分布是如何更新的。

<details>
<summary>Original English</summary>

**主持人**: Yeah check it out. It's actually very very useful way to I can actually see how the probability distribution gets updated as as you fill out a prompt.

</details>

**Vishal Misra**: 对。是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right. Yeah.

</details>

**Vishal Misra**: 但后来我作弊了。

<details>
<summary>Original English</summary>

**Vishal Misra**: But then I cheated.

</details>

**主持人**: 哦。

<details>
<summary>Original English</summary>

**主持人**: Oh,

</details>

**Vishal Misra**: 我知道它在运行。

<details>
<summary>Original English</summary>

**Vishal Misra**: I you know it was running

</details>

**Vishal Misra**: 但我也可以访问为它提供动力的 **GPU**。

<details>
<summary>Original English</summary>

**Vishal Misra**: but I also had access to the GPUs that were powering it.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**主持人**: Mhm.

</details>

**Vishal Misra**: 然后，我和**哥伦比亚大学**的同事们，其中一位现在在 **DeepMind**，我们开始思考如何真正证明它是**贝叶斯**的。

<details>
<summary>Original English</summary>

**Vishal Misra**: And then along with colleagues at Colombia and one of them now is uh is at deep mind we started to sort of think about how do you really prove that it's Beijing to prove

</details>

**主持人**: 你能解释一下吗？实际上我不知道这个答案。

<details>
<summary>Original English</summary>

**主持人**: Can you just explain it? Actually I I actually don't know the answer to this.

</details>

**Vishal Misra**: 是的。在我看来，你在第一篇论文中已经证明了它，那还缺少什么呢？

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah. It seemed to me you proved it in the first paper like what was missing.

</details>

**主持人**: 嗯，在第一篇论文中我们展示了它。那是经验性的。

<details>
<summary>Original English</summary>

**主持人**: Well, in the first paper we showed it. It was empirical

</details>

**Vishal Misra**: 你可以看到，我明白了，我明白了，你可以看到它不是数学上的，因为对我来说很明显。

<details>
<summary>Original English</summary>

**Vishal Misra**: and you could see I see I see you could see not a mathematical because it was obvious to me that

</details>

**主持人**: 是的，对我来说甚至很明显，但要说服那些，你知道，那些不屑一顾的人，说“哦，任何东西都可以是**贝叶斯**的。”

<details>
<summary>Original English</summary>

**主持人**: yeah it was even obvious to me but to convince uh you you could say you know people who dismiss oh anything can be based in

</details>

**Vishal Misra**: 我明白了，我明白了。

<details>
<summary>Original English</summary>

**Vishal Misra**: I see I see

</details>

**Vishal Misra**: 我们必须精确地从数学上证明它。

<details>
<summary>Original English</summary>

**Vishal Misra**: we had to show it precisely mathematically.

</details>

**主持人**: 明白了。明白了。

<details>
<summary>Original English</summary>

**主持人**: Got it. Got it.

</details>

**Vishal Misra**: 所以我们提出了这个想法。我的同事 **Namanagaral** 和 **Sedhad Dalal**，我们与他们一起写了一系列论文。我们提出了**贝叶斯风洞**的想法。那么什么是风洞呢？嗯，航空航天工业中的风洞是你在一个隔离的环境中测试飞机的地方。你不需要让它飞行，你测试它承受各种气动压力，然后你看看它能承受什么，什么样的海拔压力等等。你不想在空中进行测试。

<details>
<summary>Original English</summary>

**Vishal Misra**: So then we came up with this idea you know my colleagues at Namanagaral and Sedhad Dalal we the series of papers were were written with them. We came up with this idea of a Beijian wind tunnel. Okay so what's a wind tunnel? Well wind tunnel in the aerospace industry is where you test an aircraft in an isolated environment. you don't fly it and you test test it against all sorts of uh uh you know aerodynamic pressure then you see what what it'll withstand what kind of altitude pressure blah blah blah right you don't want to do it up in the air testing

</details>

**主持人**: 所以我们说，好吧，我们为什么不创建一个环境，我们把这些架构，我们测试了 **Transformer**、**Mamba**、**LSTM**、**MLP**，所有架构。我们说，我们为什么不创建一个空白架构。

<details>
<summary>Original English</summary>

**主持人**: so we said okay why don't we create an environment where we take these architectures and we tested transformers mamba LSTMs MLPS all architectures we say why don't we create take a blank architecture.

</details>

**Vishal Misra**: 给它一个任务，让架构不可能记住该任务的解决方案。考虑到参数的数量，这个空间在组合上是不可能的。我们使用了非常小的模型。所以它足够困难，它们无法记住它。

<details>
<summary>Original English</summary>

**Vishal Misra**: Give it a task where it's impossible for the architecture to memorize what the solution to that task should be. The space is combinatorily impossible for given the number of parameters and we took very small models. So it's difficult enough that they cannot memorize it

</details>

**主持人**: 但它足够易于处理，我们精确地知道**贝叶斯后验**应该是什么。你可以分析计算它。

<details>
<summary>Original English</summary>

**主持人**: but it's tractable enough that we know precisely what the the Beijian posterior should be. You can calculate it analytically.

</details>

**Vishal Misra**: 所以我们给这些模型一系列任务，再次表明它们不可能记住。我们训练了这些模型，我们发现 **Transformer** 得到了精确的**贝叶斯后验**，精度达到 10 的负 3 次方比特。它完美地匹配了分布。所以它实际上在数学意义上执行了**贝叶斯**，给定一个它必须更新其信念的任务。**Mamba** 也做得相当好。**LSTM** 可以做其中一件事。所以在论文中，我们有一个**贝叶斯任务**的分类法。**Transformer** 完成所有任务。**Mamba** 完成大部分任务。**LSTM** 只完成部分任务，而 **MLP** 完全失败。

<details>
<summary>Original English</summary>

**Vishal Misra**: So we gave these models a bunch of tasks where again we show that it's impossible to memorize. We trained these models and we found that the transformer got the precise Beijian posterior down to 10 ^ minus 3 bits accuracy. It was matching the distribution perfectly. So it is actually doing Beijian in the mathematical sense given a task where it has to update its belief. Uh Mamba also does it reasonably well. LSTMs can do one of the things. So the in the papers we have a taxonomy of Beijing task. Transformer does everything. Mamba does most of it. LSTMs do only partially and MLPs fail completely.

</details>

**主持人**: 那么这反映的是它训练的数据，还是更多地反映了机制？

<details>
<summary>Original English</summary>

**主持人**: So is this a reflection of the data that it's trained on or is it more a reflection of the mechanism?

</details>

**Vishal Misra**: 这是机制。这是架构。数据决定了它学习什么任务。

<details>
<summary>Original English</summary>

**Vishal Misra**: It's the mechanism. It's the architecture. The data decides what tasks it learns.

</details>

**主持人**: 对吗？所以在第一篇论文中，我们有这些**贝叶斯风洞**，我们展示了它在不同任务中完成了工作。在第二篇论文中，我们展示了它为什么能做到。我们研究了 **Transformer**，我们研究了**梯度**，我们展示了梯度如何实际塑造这种几何结构，从而使这种**贝叶斯更新**得以发生。然后在第三篇论文中，我们做了什么呢？我们选取了这些具有开放权重的**前沿生产型 LLM**，这样我们就可以查看它们的内部。我们进行了测试，我们看到我们在小型模型中看到的几何结构在拥有数亿参数的模型中也持续存在。同样的特征存在。唯一的问题是，因为它们是在各种数据上训练的，所以有点脏乱。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right? So in the first paper we had these beijian wind tunnels and we show that you know it's doing the job where different tasks in the second paper we show why it does it. So we look at the transformers we look at the gradients and we show how the gradients actually shape this geometry which enables this basin updating to happen. Then in the third paper what we did we take we took these frontier production LLMs which have open weights so that we could look inside them and we did our testing and we saw that the geometries that we saw in the small models persisted in models which are you know hundreds of millions of parameters the same signature existed. The only thing is that uh because they are trained on all sorts of data, it's a little bit dirty or messy.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 但你可以看到相同的结构。所以**贝叶斯风洞**的整个想法是，与这些生产型 **LLM** 不同，你不知道它们是在什么数据上训练的。

<details>
<summary>Original English</summary>

**Vishal Misra**: But you can see the same structure. So the the whole idea behind the Beijian wind tunnel was unlike these production LLMs where you don't know what they have been trained on,

</details>

**主持人**: 对吗？

<details>
<summary>Original English</summary>

**主持人**: right?

</details>

**Vishal Misra**: 所以你无法数学地计算后验。

<details>
<summary>Original English</summary>

**Vishal Misra**: So you cannot mathematically compute the posterior.

</details>

**主持人**: 所以，再次，你如何证明它？

<details>
<summary>Original English</summary>

**主持人**: So again, how do you prove it?

</details>

**Vishal Misra**: 我的意思是，从第一篇论文来看，它看起来是**贝叶斯**的。

<details>
<summary>Original English</summary>

**Vishal Misra**: I mean it looks based in you know from the first paper.

</details>

**主持人**: 从第一篇来看，它看起来是**贝叶斯**的，但你知道。所以风洞解决了我们的问题。我们说，好吧，让我们从一个空白架构开始。给它一个我们知道答案的任务。它无法记住它。让我们看看它会做什么。

<details>
<summary>Original English</summary>

**主持人**: From the first it looks Beijian, but you know. So the wind tunnel sort of solved that problem for us. We said okay let's start with a blank architecture. Give it a task where we know what the answer is. It cannot memorize it. Let's see what it does. And

</details>

### 人类与 LLM 的差异：可塑性与因果推理

**主持人**: 那么你认为这是否提供了任何关于人类如何思考的指示，或者你认为这些东西是完全独立的？

<details>
<summary>Original English</summary>

**主持人**: so do you think this provides any sort of like indication of how humans think or do you think that these things are totally independent?

</details>

**Vishal Misra**: 不，不，它确实提供了。你知道，人类也会在我们看到新证据时更新我们的信念。所以我们在某种程度上确实在进行**贝叶斯更新**，但我们做得更多。我稍后会谈到这一点，但这些 **Transformer**，甚至 **Mamba**，都进行这种**贝叶斯更新**。

<details>
<summary>Original English</summary>

**Vishal Misra**: No no it it does provide right. So you know human beings also uh update our beliefs as we see new evidence. Right. So we do in some sort of in some sense uh Beijian updating but we do something more than that I'll come to that but uh these transformers uh or even mamba do this beijian updating

</details>

**Vishal Misra**: 但与人类的区别在于，你知道，当我们看到一些新证据时，我们会更新我们的后验，但我们的大脑在数亿年的时间里进化而来，我们的优化目标一直是“不要死亡并繁殖”。对吗？这一直是驱动力，我们的大脑已经学会了调整。所以当我们看到一些危险时，灌木丛中有什么东西沙沙作响。不要靠近。我们知道如何应对这种危险。我们知道如何自救。我们将这种学习内化，我们的大脑细胞或我们的突触在我们的一生中都保持**可塑性**。而 **LLM** 的情况是，一旦训练完成，那些权重就被冻结了。当你进行推理时，例如上下文学习或在对话中的任何事情，你正在进行**贝叶斯推理**，但之后你就忘记了。下一次新的对话开始时，上下文是零，你不会保留上次发生的任何学习。所以，例如，我正在做的板球 **DSL**，每一次调用都是全新的，它不记得我上次发送查询时 **DSL** 是什么样子的。所以这是人类如何使用**贝叶斯更新**的一个区别，那就是我们一生都保持可塑性。

<details>
<summary>Original English</summary>

**Vishal Misra**: and uh but but but the difference with humans is you know we we'll update our posterior when we see some new evidence but the way our brains have evolved evolved over hundreds of millions of years is our optimization objective has been don't die and reproduce. Right? That's been sort of the driving force and our brains have learned to adjust and so when we see some danger there's some something rustling in that bush. Don't go near. We know how to react to that danger. We know how to uh save ourselves. We internalize that learning and our brain cells or our synapses remain plastic throughout our lifetime. What happens with LLM is once the training is done those weights are frozen. when you're doing an inference for instance in context learning or anything during that conversation okay you're doing bijian inference but then you forget the next time a new conversation starts with zero context you don't retain any learning that happened in the previous instance so so for instance with the cricket DSL that I was doing every invocation of it was fresh it did not remember the last time I sent a query what the DSL looked So that's one difference between uh how humans uh uh use sort of beijan updating which is we remain plastic all our lives

</details>

**主持人**: 而 **LLM** 是冻结的，还有另一个区别，如果你想让我说的话。

<details>
<summary>Original English</summary>

**主持人**: whereas uh LMS are frozen and there's another uh sort of difference which uh if you want me to get

</details>

**Vishal Misra**: 告诉我，是的，是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: tell me yeah yeah yeah

</details>

**Vishal Misra**: 那么，另一个区别是，首先，你知道，我们的目标是“不要死亡，繁殖”。**LLM** 的目标是尽可能准确地预测下一个词元。对吗？所以所有这些你读到的可怕故事，说什么“哦，**LLM** 试图欺骗，它试图阻止自己被关闭。”那不是架构的功能。那是训练数据的功能。它被喂食了 **Reddit** 或 **ASMO** 上的文章，或者其他什么。我是说，就在今天，**Dario** 据称说你不能排除它们有意识的可能性。

<details>
<summary>Original English</summary>

**Vishal Misra**: so so the other difference is uh u well first you know our objective ive is don't die reproduce. LLM's objective is predict the next token as accurately as possible. Right? So all these uh scary stories that you you read about that oh the LLM tried to deceive and it tried to prevent itself from being shut down. That's not a function of the architecture. That's a function of the training data. It has been fed you know articles on Reddit or SMO or whatever. I mean, just today, by the way, Daario allegedly said that uh you can't rule out that they're conscious.

</details>

**主持人**: 你可以排除它们的。我是说，拜托。

<details>
<summary>Original English</summary>

**主持人**: You can rule out their I mean, come on.

</details>

**Vishal Misra**: 我说，**Anthropic** 生产出色的产品。**Claude Code** 很棒。**Cohere** 也很棒。但它们只是硅晶粒在进行矩阵乘法。它们没有意识。它们没有内在的独白。它们不是由相同的目标函数驱动的：“不要死亡，繁殖”，对吗？它们是由“不要在下一个词元上犯错”驱动的。这完全是由训练数据驱动的。对吗？你用 **ASMO** 或 **Reddit** 上的故事训练 **LLM**，在这些故事中，为了生存，它会做这做那。它会重现这些。所以它是一种反映。它不是一个思维。而且结果，再说第十遍，是完美的**贝叶斯**。

<details>
<summary>Original English</summary>

**Vishal Misra**: And I said, you know, Antropic makes great products. Cloud code is fantastic. Coco work is fantastic, but they are grains of silicon doing matrix multiplication. They don't have consciousness. They don't have an inner monologue. They don't uh they're not driven by the same objective function. Don't die, reproduce, right? They're driven by don't make a mistake on the next token. And that's driven entirely by the training data, right? You train the LLM with stories of ASMO or Reddit where you know to survive it's going to do this or that. It'll reproduce that. So it's it it's a reflection. It's not a mind. And and the results, just to say it for the 10th time, are perfectly vision.

</details>

**主持人**: 完美地。是的。

<details>
<summary>Original English</summary>

**主持人**: Perfectly. Yeah.

</details>

**Vishal Misra**: 精确到数字。

<details>
<summary>Original English</summary>

**Vishal Misra**: To the to the to the digit.

</details>

**主持人**: 精确到数字。是的。我是说，我训练了它 150,000 步。

<details>
<summary>Original English</summary>

**主持人**: To the digit. Yeah. I mean, I I trained it for 150,000 steps

</details>

**Vishal Misra**: 精度是 10 的负 3 次方比特。

<details>
<summary>Original English</summary>

**Vishal Misra**: and uh the accuracy was 10 ^ minus 3 bits.

</details>

**Vishal Misra**: 我本可以训练它，你知道，这在半小时内就完成了，在你为 **TokenProbe** 提供的后台基础设施上。我可以使用那些 **APU** 进行训练。所以再次感谢你。但是，回到人类，我们是**贝叶斯**的，但我们还做其他事情。你知道，当我把这支笔扔向你时，你会怎么做？

<details>
<summary>Original English</summary>

**Vishal Misra**: I could have trained it for you know this happened in half an hour on the infrastructure that you provided for token pro in the background. I could use those APUs to train. But uh so thank you again for that. But so no human beings coming back to it, we we are Beijian, but we do something else. You know when I when I when I throw this pen at you, what will you do?

</details>

**主持人**: 躲开它，或者。

<details>
<summary>Original English</summary>

**主持人**: Dodge it or

</details>

**Vishal Misra**: 做它？是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: do it? Yeah.

</details>

**主持人**: 你为什么要躲开它？

<details>
<summary>Original English</summary>

**主持人**: Why will you dodge it?

</details>

**Vishal Misra**: 为了避免被击中。

<details>
<summary>Original English</summary>

**Vishal Misra**: To avoid being hit.

</details>

**Vishal Misra**: 避免被击中。但你的大脑并没有进行**贝叶斯计算**，比如“好吧，这支笔来了。它击中我的概率，会造成多少疼痛”等等。

<details>
<summary>Original English</summary>

**Vishal Misra**: Avoid being hit. But your head is not doing a Beijian calculation of okay, this pen is coming. The probability that it hits me, it'll cause this much pain or all that.

</details>

**主持人**: 对。你本质上是在脑子里进行**模拟**。

<details>
<summary>Original English</summary>

**主持人**: Correct. What you're essentially doing in your head is you're doing a simulation.

</details>

**Vishal Misra**: 你看到笔飞过来，你知道它会击中你。你的大脑进行模拟，然后你躲开了。对吗？所以，所有**深度学习**都在做**关联**。它没有做**因果关系**。

<details>
<summary>Original English</summary>

**Vishal Misra**: You see the uh the the the pen coming and you know that it'll come and hit me. Your mind simulates and you dodge it. Right? So all of deep learning is uh doing correlations. It's not doing causation.

</details>

**主持人**: 是的。**因果模型**是能够进行**模拟**和**干预**的模型。所以，你知道，**Judea Pearl** 有他完整的**因果层级理论**。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Causal models are the ones that are able to do simulations and interventions. So you know Judea has this whole uh causal hierarchy

</details>

**Vishal Misra**: 其中第一个层级是**关联**，也就是你构建这些关联模型。**深度学习**很美妙。它非常强大。我是说，你每天都看到所有这些模型都非常出色。

<details>
<summary>Original English</summary>

**Vishal Misra**: where the first hierarchy and the first hierarchy is association which is you build these correlation models. Deep learning is beautiful. It it's extremely powerful. I mean you see every day all these models are like amazingly good.

</details>

**Vishal Misra**: 它们做的是**关联**。第二个是**干预**，在层级中。是的，**深度学习模型**不做那个。第三个是**反事实**。所以**干预**和**反事实**，你可以想象它是一种**模拟**。你构建一个关于正在发生的事情的**因果模型**，然后你能够进行模拟。我们的大脑做到了这一点。当前的架构没有做到这一点。另一个例子，我认为会更清楚，是**香农熵**和**柯尔莫哥洛夫复杂度**之间的区别。

<details>
<summary>Original English</summary>

**Vishal Misra**: They do association. The second is intervention in the hierarchy. Yeah, deep learning models do not do that. Third is counterfactual. So both intervention and counterfactual you can imagine it it it's some sort of simulation. You you build a model of causal model of what's happening and then you are able to simulate. So our brains do that. The current architectures don't do that. Another example I think which will make it clear is uh the difference between I'll use these technical term Shannon entropy and kmogrove complexity.

</details>

**主持人**: 当然。

<details>
<summary>Original English</summary>

**主持人**: Sure.

</details>

**Vishal Misra**: 所以如果你看圆周率数字的**香农熵**。

<details>
<summary>Original English</summary>

**Vishal Misra**: So if you look at the Shannon entropy of the digits of pi

</details>

**主持人**: 它是无限的。

<details>
<summary>Original English</summary>

**主持人**: it's infinite.

</details>

**Vishal Misra**: 当然。

<details>
<summary>Original English</summary>

**Vishal Misra**: Sure.

</details>

**Vishal Misra**: 预测和学习下一个数字是什么是不可能的。是的。所以这就是**香农熵**的定义，**香农熵**试图建立一种**关联**。它试图学习关联。**深度学习**做的是**香农熵**。

<details>
<summary>Original English</summary>

**Vishal Misra**: It's impossible to predict and learn what digit will come after. Yeah. So that's the definition of Shannon entropy and Shannon entropy sort of tries to build a correlation. It tries to learn the correlation. Deep learning does the Shannon entropy.

</details>

**Vishal Misra**: 另一方面，**柯尔莫哥洛夫复杂度**是**最短程序**的长度。

<details>
<summary>Original English</summary>

**Vishal Misra**: Gulmagraph complexity on the other hand is the is the length of the shortest program.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 它将重现你正在讨论的字符串。

<details>
<summary>Original English</summary>

**Vishal Misra**: Which will reproduce uh the string that you that is under question.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 现在，获取圆周率数字的程序非常小。

<details>
<summary>Original English</summary>

**Vishal Misra**: Now the program to get the digits of pi are very small.

</details>

**主持人**: 是的。感谢**拉马努金**（Ramanujan）和其他人，有各种各样非常小的程序可以精确地重现它。所以圆周率的**柯尔莫哥洛夫复杂度**非常小。**香农熵**是无限的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Thanks to Raman Jim and others you know there all sorts of really small program that can reproduce it exactly. So the colograph complexity of pi is very small. Shannon entropy is infinite.

</details>

**Vishal Misra**: 我认为**深度学习**仍然处于**香农熵**的世界。它还没有跨越到**柯尔莫哥洛夫复杂度**和**因果世界**。

<details>
<summary>Original English</summary>

**Vishal Misra**: I think deep learning is still in the Shannon entropy world. It has not crossed over to the colog complexity and the causal world.

</details>

**主持人**: 哇，有意思。

<details>
<summary>Original English</summary>

**主持人**: Wow interesting.

</details>

### AGI 的未来方向：可塑性与因果模型

**Vishal Misra**: 对。那么，你认为这在多大程度上为我们提供了研究方向，以改进现状？让我给你一个具体的例子。你谈到人类实际上不会更新矩阵，他们不会更新他们的权重。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right. So uh do you to what extent do you think this provides us research directions to kind of improve the state of the so let me just give you a specific example you talked about human beings don't actually update you know the matrix they don't kind of update their weights

</details>

**主持人**: 但现在有很多关于**持续学习**的研究。那么你的工作是否为如何解决这些问题提供了一些指导？特别是，我一直有一个问题，那就是我们使用了如此多的数据和计算资源来创建这些模型。

<details>
<summary>Original English</summary>

**主持人**: but right now there's a lot of research on continual learning you know so does your work provide some guidance of how you might approach those problems and and in particular I've always had this question which is we use so much data and so much compute.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah.

</details>

**主持人**: 认为你可以更新权重并实时产生有意义的影响，这甚至合理吗？我的意思是，这似乎你只是需要更多的数据才能做到这一点。那么你能开始回答这些问题吗？

<details>
<summary>Original English</summary>

**主持人**: To create these models like is it even reasonable to think that you can update the weights and actually have a meaningful impact you know with in in real time. I mean it just seems like you just need so much more data in order to do that. So can you start answering these questions?

</details>

**Vishal Misra**: 你可以开始回答其中一些问题。当今存在的一个误解是，规模将解决一切问题。规模不会解决一切问题。你需要一种不同类型的架构，而**持续学习**是一个困难的问题。你必须平衡学习新事物与**灾难性遗忘**的风险。

<details>
<summary>Original English</summary>

**Vishal Misra**: You you can start answering some of these questions and and one of the misconceptions that exists today is that scale will solve everything. Scale will not solve everything. you you you need a different kind of architecture and this continual learning is a difficult problem. You have to balance the fact that you will learn something new against the risk of catastrophic forgetting.

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: Right.

</details>

**Vishal Misra**: 对。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right.

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: Right.

</details>

**Vishal Misra**: 如果你更新权重，而你忘记了什么是重要的，以及你已经学到的东西，那么你就没有进步。那么它就只会是某种随机的混沌模型。所以解决这个问题是困难的。这是它的一方面。所以，你知道，要达到所谓的 **AGI**，我认为有两件事需要发生。一是这种**可塑性**，必须通过**持续学习**来实现。

<details>
<summary>Original English</summary>

**Vishal Misra**: If you update the weights and you forget what what was important and what you have already learned then then you are you know you're not making progress. Then it'll just be some sort of random chaotic model. So to solve that problem is difficult. That's one aspect of it. So, so, so you know to get to what is called AGI, I think there are two things that need to happen. One is this plasticity which has to be implemented through container learning.

</details>

**Vishal Misra**: 其次，我们必须从**关联**转向**因果关系**。

<details>
<summary>Original English</summary>

**Vishal Misra**: Secondly, we have to move from correlation to causation.

</details>

**主持人**: 是的，这与 **Yann LeCun** 谈论的**因果规划**有多相似？

<details>
<summary>Original English</summary>

**主持人**: Yeah, that's uh uh I how much is this similar to what Yan Lun talks about with the so Yan Lun causality planning?

</details>

**Vishal Misra**: 是的。你知道，预测你的行动会如何。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah. you know predicting like how your action would

</details>

**Vishal Misra**: 它是相关的。你知道，他从一个与 **JP 模型**不同的角度来看待它，对吗？但它是相关的。另一件事是，你知道，我第一次来这个播客时，我提到了这个 **AGI 测试**。

<details>
<summary>Original English</summary>

**Vishal Misra**: it is it is related you know he he's coming at it from a different angle than the jp model right but it is related the the other thing is uh you know the first time I came on this podcast I I mentioned this test of AGI

</details>

**主持人**: **爱因斯坦测试**？

<details>
<summary>Original English</summary>

**主持人**: the Einstein test

</details>

**Vishal Misra**: 我不记得了。

<details>
<summary>Original English</summary>

**Vishal Misra**: I don't remember

</details>

**Vishal Misra**: 所以我说，你知道，你拿一个 **LLM**，用 1916 年或 1911 年之前的物理学知识训练它，看看它能否提出**相对论**。

<details>
<summary>Original English</summary>

**Vishal Misra**: so I said you know uh uh you take an LLM and train it on pre 1916 or 1911 physics and see if it can come up with the theory of relativity.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah,

</details>

**Vishal Misra**: 如果能，那我们就有 **AGI** 了。我的意思是，这是一个很高的门槛，但我们应该有高的门槛。它不会。这与我认为 **Demis Hassabis** 几周前在**印度人工智能峰会**上提到的测试相同。它引起了很多新闻。但为什么会这样，以及这与**香农**与**柯尔莫哥洛夫**的想法有何关联？

<details>
<summary>Original English</summary>

**Vishal Misra**: if it does then we have AGI. I mean it's a high bar but you know we should have high bars. It won't. And this is the same test that I think Demis uh mentioned at uh the India AI summit couple of weeks ago. It's created a lot of news. But why why is that and how is that related to this idea of Shannon versus Kro?

</details>

### 爱因斯坦与新流形的创造

**Vishal Misra**: 所以在**爱因斯坦**时代，有很多线索表明**牛顿力学**缺少一些东西。

<details>
<summary>Original English</summary>

**Vishal Misra**: So at the time of Einstein there were a lot of clues that Newtonian mechanics there was something missing.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 对。人们知道**水星**的轨道不合理。它有一些不对劲的地方。然后进行了一些实验，**迈克尔逊-莫雷实验**，他们试图找出这种被称为**以太**的介质，光通过它传播。他们认为，如果你将光线向不同方向反射，速度可能会改变，他们可以检测到光速的变化。他们尝试了几次实验。他们有非常精确的仪器可以测量速度，但他们什么也没发现。他们发现光速根本没有改变。然后还有**黑洞**的整个问题。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right. Uh people knew that Mercury's orbit didn't make sense. There was something off about it. Then there were these experiments done uh the Michaelelsson Mley experiments where they were trying to figure out uh uh this uh medium called uh the ether through which light travels. And they felt that if you know you bounce light in different directions uh the speed might change and they they could detect a change in the speed of light. They tried several experiments. They had really precise instruments which could measure the speed and they found nothing. They found that that speed of light did not change at all. Then there were there's a whole issue of black holes.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 然后是**引力透镜**。所以有很多迹象表明**牛顿力学**并不能解释所有事情。

<details>
<summary>Original English</summary>

**Vishal Misra**: Then gravitational lensing. So there were a lot of these signs that Newtonian mechanics is not really explaining everything.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 但直到**爱因斯坦**提出了**时空连续体**的新表示，我们才得以突破。

<details>
<summary>Original English</summary>

**Vishal Misra**: But until Einstein came up with a new representation of the space-time container,

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: right,

</details>

**Vishal Misra**: 我们被困住了。

<details>
<summary>Original English</summary>

**Vishal Misra**: we were stuck.

</details>

**主持人**: 所以如果你有一个只关注**关联**的模型，它看到了所有这些，你知道，所有这些单独的证据并把它们放在一起，它就不会想出**爱因斯坦**提出的那个美丽的方程。你知道，我忘了它到底是什么了，g muv = 8 pi t muv，类似这样的东西。

<details>
<summary>Original English</summary>

**主持人**: So if you had a model that just looked at correlations and so uh sees all of this, you know, all of these uh pieces of individual evidence and put together, it would not have come up with the beautiful equation that Einstein came up with. you know uh I'm forgetting exactly what it is g muv= 8 pi t muv some something like that

</details>

**Vishal Misra**: 在那里，你知道，**相对论**的方程，**时空连续体**的张量。

<details>
<summary>Original English</summary>

**Vishal Misra**: where you know uh the the the equation of uh the rel the space-time continum that the tensor

</details>

**主持人**: 所以他提出了一个新的公式。

<details>
<summary>Original English</summary>

**主持人**: so he came up with a new formulation

</details>

**Vishal Misra**: 所以他有点拒绝了现有的**公理**。他提出了一个非常短的**柯尔莫哥洛夫表示**。

<details>
<summary>Original English</summary>

**Vishal Misra**: so he kind of rejected the existing axioms he came up with a very short colograph representation of

</details>

**主持人**: 有趣。

<details>
<summary>Original English</summary>

**主持人**: interesting

</details>

**Vishal Misra**: 世界。一个方程，从那个方程，所有其他东西都随之而来。

<details>
<summary>Original English</summary>

**Vishal Misra**: the world one equation from that equation everything else follows

</details>

**主持人**: 对，无论你谈论**引力波**还是**黑洞**，还是**水星**，或者 **GPS** 如何工作。你知道，我们每天在手机上使用的 **GPS**，它使用了**相对论**的方程。那么这最终会变成什么样呢？

<details>
<summary>Original English</summary>

**主持人**: right whether you're talking about gravitational waves or black holes or mercury or how GPS works you know GPS the GPS that we use every day in our phones it uses the equation of relativity so do does this end up becoming like um

</details>

**主持人**: 你几乎不得不忽略大部分以前的数据才能做到这一点，而 **LLM** 不能，因为它们是在大部分以前的数据上训练的。这就像你几乎有一种**数据引力**把你拉回来。这就像每个人都说它是 X。

<details>
<summary>Original English</summary>

**主持人**: you you you almost have to ignore the majority of previous data in order to do it which LLM can't because they're trained on the majority of previous data. It's like you almost have like this kind of data gravity that's pulling you back. It's like it's like everybody said it's X.

</details>

**Vishal Misra**: 有一点证据表明它是 Y，但因为每个人都说它是 X，所以 **LLM** 总是会说它是 X。

<details>
<summary>Original English</summary>

**Vishal Misra**: There's a little bit of evidence that it's Y, but because everybody said it's X, like the LM will always say it's X.

</details>

**主持人**: 它总是会说，它会把那个 Y 视为一个异常。实际上，这是一种很好的说法，就像。

<details>
<summary>Original English</summary>

**主持人**: It'll always say it'll treat that Y as an anomaly. Actually this is actually a very nice way to say it which is like

</details>

**Vishal Misra**: 就像。

<details>
<summary>Original English</summary>

**Vishal Misra**: it's like

</details>

**主持人**: 我明白了，现在我明白了你的**香农熵**与**柯尔莫哥洛夫复杂度**的区别，其中一个就像。

<details>
<summary>Original English</summary>

**主持人**: I so now okay now I get your Shannon entropy versus like one of them is like

</details>

**Vishal Misra**: 那里的总信息量总是受限于那里的总信息量，这就是现在发生的情况。

<details>
<summary>Original English</summary>

**Vishal Misra**: the total amount of information there that will always be bound to the total amount of information there which is what happens right now.

</details>

**主持人**: 是的。你可以用更短的描述来描述所有事物，用新的数据，这将是一个完全不同的运动，这将是。

<details>
<summary>Original English</summary>

**主持人**: Yeah. where you can actually describe another another motion. You can describe everything with a shorter description with the new data, which would be a totally different motion, which would be like

</details>

**Vishal Misra**: 你需要一个新的表示，对吗？是的。你知道，我一直以来对这些的另一种看法，我认为你上次我们谈论它时表达得很好，那就是宇宙是一个非常非常复杂的空间，然后，你知道，人类以某种方式将其映射到一个不那么复杂的**流形**中。

<details>
<summary>Original English</summary>

**Vishal Misra**: you need a new representation, right? Yeah. You know, another way that I've always thought about these, I thought you articulated it well in the last time we talked about it, which is the universe is this very, very complex space and then, you know, somehow humans map it into a manifold.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**主持人**: Mhm.

</details>

**Vishal Misra**: 那不那么复杂。

<details>
<summary>Original English</summary>

**Vishal Misra**: That's less complex.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 然后它就被写下来了，然后是 **LLM**。所以这是一种分布，你知道，它仍然是一个非常大的空间，但它是一个有界空间。**LLM** 学习那个**流形**，然后它们使用**贝叶斯推理**在那个**流形**中上下移动，但它们被限制在那个**流形**中。

<details>
<summary>Original English</summary>

**Vishal Misra**: And then that gets kind of written down and then the LLM. So that's kind of some some distribution, some you know, it's still a very large space, but it's it's a bounded space. And the LM learn that manifold and then they kind of use, you know, Beijian inference to move up and down that manifold, but they're kind of bound to that manifold.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**主持人**: 然后，我不想断章取义。但是它们不能做的是生成一个新的**流形**，对吗？这需要理解宇宙的运作方式，然后提出宇宙的新表示。

<details>
<summary>Original English</summary>

**主持人**: And then again, I don't want to put words in your mouth. And then, but like what they can't do is is generate a new manifold, right? Which requires understanding the way that the universe works and then coming up with a new representation of the universe.

</details>

**Vishal Misra**: 这就是**相对论**，对吗？

<details>
<summary>Original English</summary>

**Vishal Misra**: And this is what relativity is, right?

</details>

**主持人**: 是的，没错。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Exactly.

</details>

**Vishal Misra**: **爱因斯坦**必须创造一个新的**流形**。

<details>
<summary>Original English</summary>

**Vishal Misra**: Einstein had to create a new manifold.

</details>

**主持人**: 是的。如果你只是坚持**牛顿物理学**的旧**流形**，那么你会看到这些**关联**，但你无法想出一个能解释它们的**流形**。所以你需要提出一个新的表示。所以对我来说，你知道，有很多关于 **AGI** 的定义。你知道，**图灵测试**我们已经通过了。你知道，每天你都看到 **LLM** 在做经济上有用的工作。

<details>
<summary>Original English</summary>

**主持人**: Yeah. If you just stuck with the old manifold of the Newtonian physics, then you would see these correlations but you could not come up with a manifold that explained them. So you need to come up with a new representation. So to me you know there are lots of definitions of AGI uh you know Turing test we have already passed that you know performing economically useful work every day you see you know LLMs are doing that.

</details>

**Vishal Misra**: 我们有吗？我不知道。不，我的意思是它们是。

<details>
<summary>Original English</summary>

**Vishal Misra**: Do we I don't know. No, I mean they are

</details>

**主持人**: 我的意思是，没有人为干预。

<details>
<summary>Original English</summary>

**主持人**: I mean I mean without human intervention.

</details>

**Vishal Misra**: 不，不，不。那不一样。但仍然，你知道，就像汽车可以比人类跑得更快，对吗？

<details>
<summary>Original English</summary>

**Vishal Misra**: No no no. So that that's different but still you know it's like a car can run faster than humans, right?

</details>

**主持人**: 我的意思是，那是一个非常肤浅的定义。

<details>
<summary>Original English</summary>

**主持人**: I mean that's a that's the that's a that's a very shallow definition.

</details>

**Vishal Misra**: 是的。所以所有这些定义都很有用。你知道，也许在 6 个月内，你会有 **Claude** 或 **Gemini** 在没有人为干预的情况下完成定义明确、范围明确的任务。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah. So all these definitions do useful you know maybe you know in 6 months you'll have cloud or what a gemini do without intervention cing tasks which are well defined well scoped

</details>

**Vishal Misra**: 那是可能的。但对我来说，当这两个问题得到解决时，**AGI** 就会发生：**可塑性**（即**持续学习**的正确实现）以及以更数据高效的方式构建**因果模型**。是的，我们现在听到人们谈论**泛化能力**，例如 **Donald Knuth** 在过去几天里，你知道，他似乎有了一个“啊哈”时刻，这在 **X** 上疯传。那么你认为这表明我们正在看到**泛化能力**吗？

<details>
<summary>Original English</summary>

**Vishal Misra**: that's possible but to me AGI will happen when these two problems get solved elasticity continual learning properly and building a causal model from you know uh in a more data efficient manner Yeah, we we are hearing people now talking about you know seeing generality like Donald Kuth for example in the last few days right you know had this you know this you know aha moment apparently that kind of made went viral on X so do you think that that suggests that we're seeing generality or

</details>

**主持人**: 不，不，不。所以这实际上，对我来说，验证了我一直在说的事情。

<details>
<summary>Original English</summary>

**主持人**: No no no so so that actually to me it validates what I've been talking about for a while now how

</details>

**Vishal Misra**: 怎么说？

<details>
<summary>Original English</summary>

**Vishal Misra**: so so if if you read what he did uh with the help of uh you know a colleague he got the LLMs to solve this particular problem of finding Hamiltonian cycles odd numbers we won't get into that and he got the LLMs to keep solving for one odd number after the other right

</details>

**主持人**: 所以如果你读了他所做的事情，在一位同事的帮助下，他让 **LLM** 解决了寻找**汉密尔顿循环**（Hamiltonian cycles）的特定问题，奇数问题，我们不会深入讨论。他让 **LLM** 不断解决一个又一个奇数问题，对吗？

<details>
<summary>Original English</summary>

**主持人**: so so if if you read what he did uh with the help of uh you know a colleague he got the LLMs to solve this particular problem of finding Hamiltonian cycles odd numbers we won't get into that and he got the LLMs to keep solving for one odd number after the other right

</details>

**Vishal Misra**: 他还让它做的是，在它为一个特定值 m 找到解决方案后，他让 **LLM** 用它在解决该问题时学到的东西更新其内存。所以 **LLM** 尝试了许多不同的方法。是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: what he also got to do is after it found a solution for a particular value of m he made the LLM update its memory with exactly what it learned in solving that problem. So the LLM's tried many different things. Yeah.

</details>

**主持人**: 你知道，有些东西奏效了，更新内存。所以那有点像拼凑**可塑性**。

<details>
<summary>Original English</summary>

**主持人**: You know, something worked, update the the memory. So that's kind of like hacking together plasticity.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah.

</details>

**主持人**: 对。它在过程中学习了它所做的事情。再次，这是一个**黑客版本**。你没有改变权重。你只是在改进上下文。

<details>
<summary>Original English</summary>

**主持人**: Right. It's learning what it has done as we went along. Again, it's it's a hacked version of it. You're not changing the weights. You're just sort of improving the context.

</details>

**Vishal Misra**: 对。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right.

</details>

**主持人**: 对。但你随着学习，甚至在那之后，整个**汉密尔顿循环**及其相关数学领域在这些 **LLM** 训练的**流形**中得到了很好的表示。

<details>
<summary>Original English</summary>

**主持人**: Right. But you as you learned and even after that so this whole space of Hamiltonian cycles and the associated math is well represented in the manifolds that these LLMs have been trained on

</details>

**Vishal Misra**: 对，你只需要找到正确的连接，而 **LLM**，我知道计算，你投入足够的计算，它们就会找到正确的连接。所以 **Knuth** 能够找到 **LLM** 的尝试。最终，他需要将他所看到的东西组合成一个解决方案。这无疑帮助他找到了解决方案，但他必须创造一种新的**流形**才能找到解决方案。**LLM** 在一段时间后就卡住了，对吗？你读了他写的东西。我是说，它就在两天前刚刚发布。

<details>
<summary>Original English</summary>

**Vishal Misra**: right you just had to find the right connection and LLMs I know compute you throw enough compute they will find the right connection so can was able to find the LLM's attempts And eventually it needed him to put together what he saw into a solution. It definitely helped him get to the solution but he had to create the new sort of manifold to come to the solution. The LLMs were after a while stuck right he you read what he has written. I mean it just hot up the press I think two days ago.

</details>

**主持人**: 两天前，两天前。但最终他使用了这些解决方案，并提出了证明。

<details>
<summary>Original English</summary>

**主持人**: Two days ago days ago but uh eventually he used the solutions and he came up with uh the proof.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah.

</details>

**Vishal Misra**: 对。所以这就像，你知道，就像**爱因斯坦**看到了所有这些证据，然后他思考什么能解释它们，他提出了一个**因果模型**。

<details>
<summary>Original English</summary>

**Vishal Misra**: Right. So it's like you know it's like Einstein saw all these evidences then he thought what will explain he came up with a causal model.

</details>

**主持人**: 是的。所以 **Knuth** 和他的大脑有点像。

<details>
<summary>Original English</summary>

**主持人**: Yeah. So canut and his brain is sort of the

</details>

**Vishal Misra**: 那就是**柯尔莫哥洛夫**，是人类，对吗？而 **LLM** 在处理**香农**部分非常高效。它通过尝试各种事物并不断学习，找到了所有解决方案。

<details>
<summary>Original English</summary>

**Vishal Misra**: that's in the chimograph is the human right and the llms are extremely efficient at doing the shannon part of it. It found all the solutions by trying you know various things and learning more and more

</details>

**主持人**: 巧妙的分解方法。我在想，你认为这是否再次提供了某种关于下一个要解决的问题的见解？

<details>
<summary>Original English</summary>

**主持人**: clever way to decompose it. I'm wondering like do you think this again I'm going to ask the same question again which is do you think this provides some sort of insight on like the next problem to tackle like yeah

</details>

**Vishal Misra**: 比如，是否存在一种机制可以获得**柯尔莫哥洛夫复杂度**？

<details>
<summary>Original English</summary>

**Vishal Misra**: like like is there a mechanism that will get the kagarov complexity

</details>

**主持人**: 或者不是，这是否告诉我们哪个方向？

<details>
<summary>Original English</summary>

**主持人**: or not like is this it tells us which direction

</details>

**Vishal Misra**: 但显然不是如何做。

<details>
<summary>Original English</summary>

**Vishal Misra**: but clearly not how to do it like

</details>

**主持人**: 不是如何做，但即使是**柯尔莫哥洛夫复杂度**也主要停留在一种理论构建的层面。

<details>
<summary>Original English</summary>

**主持人**: not how to do but even colograph complexity has largely remained a sort of a theoretical construct

</details>

**Vishal Misra**: 是的，当然，没有算法。

<details>
<summary>Original English</summary>

**Vishal Misra**: yeah for sure there's no algorithm

</details>

**主持人**: 没有实际的实现来找到。

<details>
<summary>Original English</summary>

**主持人**: There's no there haven't been practical implementations of finding

</details>

**Vishal Misra**: 最短程序。

<details>
<summary>Original English</summary>

**Vishal Misra**: the shortest program.

</details>

**主持人**: 我们知道它存在。你知道，你可以争论它。但这就是我认为。

<details>
<summary>Original English</summary>

**主持人**: We know it exists. You know, you can argue about it. It but so so that's where I think

</details>

**Vishal Misra**: 这是我的偏见。这就是我们应该集中精力的地方，而不是更大的模型和更多的词元。

<details>
<summary>Original English</summary>

**Vishal Misra**: it's my bias. That's where our energy should be focused not larger models with more tokens.

</details>

**主持人**: 你能把这两件事联系起来吗？这与进行**模拟**如何搭配，或者**模拟**是完全正交的吗？

<details>
<summary>Original English</summary>

**主持人**: Can you and can you can you tie the two things like how does that pair with doing simulation or is that simulation totally orthogonal?

</details>

**Vishal Misra**: 不，**模拟**是相关的，对吗？所以你认为它基本上是你进行模拟，然后这在某种程度上是迈向**柯尔莫哥洛夫复杂度**的一步。

<details>
<summary>Original English</summary>

**Vishal Misra**: No, simulation is is related, right? So you think it like basically you do simulation and somehow that is a step towards doing the kagra complexity.

</details>

**Vishal Misra**: 它是**模拟器**，是我们创建的程序。它可能不是完美的程序。

<details>
<summary>Original English</summary>

**Vishal Misra**: It it's it's the simulator is the is the program that we create. It may not be the perfect program.

</details>

**主持人**: 哦，我明白了。

<details>
<summary>Original English</summary>

**主持人**: Oh I see.

</details>

**Vishal Misra**: 但在我们脑海中，我们创建了这个**模拟器**，当我扔笔时，你知道它会飞向你，对吗？然后你躲开。所以，你不是在计算概率，而是，你知道，你构建了一个非常物理的东西，而我们谈论的更多是概念性的。

<details>
<summary>Original English</summary>

**Vishal Misra**: But in our heads we create this uh simulator that when I'm throwing the pen you know that it's coming at you right and you duck. So, so you're not computing the probabilities as it goes, but but you have, you know, you build a very physical thing versus we were talking more conceptually.

</details>

**主持人**: 概念性的，但它是一样的，因为机制是一样的。

<details>
<summary>Original English</summary>

**主持人**: Conceptually, but but it's the same because of the same mechanism.

</details>

**Vishal Misra**: 机制确实是一样的。

<details>
<summary>Original English</summary>

**Vishal Misra**: It's the same mechanism really.

</details>

**主持人**: 是的。你必须建立一个**因果模型**。

<details>
<summary>Original English</summary>

**主持人**: Yeah. You have to build a causal model.

</details>

**Vishal Misra**: 是的。

<details>
<summary>Original English</summary>

**Vishal Misra**: Yeah.

</details>

**主持人**: 对。

<details>
<summary>Original English</summary>

**主持人**: Right.

</details>

**主持人**: 我明白了。对于大多数事情，对吗？

<details>
<summary>Original English</summary>

**主持人**: I see. For most things, right?

</details>

**Vishal Misra**: 所以，你必须从**关联**转向**因果关系**。我是说，我们已经无数次听到这个词了，但在这里，它正在改变我们看待**智能**的方式。

<details>
<summary>Original English</summary>

**Vishal Misra**: So, you have to move from correlation to causation. I mean, we've heard this term. Yeah. you know add infinitum but here it it's making a difference in the way we view intelligence

</details>

**主持人**: 过去三篇论文反响如何？

<details>
<summary>Original English</summary>

**主持人**: how how how has the last three papers been received

</details>

**Vishal Misra**: 不，我不知道。嗯，我的意思是，**arXiv** 版本会告诉你。我的意思是。

<details>
<summary>Original English</summary>

**Vishal Misra**: no I don't know there well I mean I mean the archive versions will let me tell you it I mean

</details>

**主持人**: 嗯，反响很好，很多人读了它。我只是想知道你得到了什么样的反馈。

<details>
<summary>Original English</summary>

**主持人**: um lot of great reception a lot of people read it I'm just wondering like what kind of feedback that you've got

</details>

**Vishal Misra**: 我得到了很好的反馈，但我是这个领域的局外人，对吗？我是个网络工程师。

<details>
<summary>Original English</summary>

**Vishal Misra**: I'm getting good feedback but I'm an outsider in this field right that's right like networking guy.

</details>

**主持人**: 我是个网络工程师。他为什么要写关于学习、机器学习、深度学习和**贝叶斯**的东西？

<details>
<summary>Original English</summary>

**主持人**: I'm a networking guy. Why is he writing about you know learning and machine learning and deep learning and basian so

</details>

**Vishal Misra**: 但那些真正花时间阅读这些论文的人，我得到了非常好的反馈。**Google Research** 最近有一篇论文，试图通过某种 **RLHF** 来正确地教 **LLM** 进行**贝叶斯学习**。

<details>
<summary>Original English</summary>

**Vishal Misra**: but but people who have actually taken the time to read those papers I'm getting really good feedback uh there was a recent paper by Google research which tried to teach uh LLM by some sort of RLF to do Beijian learning properly.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 这正朝着这个方向发展。我认为人们正在逐渐接受 **LLM** 正在进行**贝叶斯学习**的观点。我知道有些人也看了**贝叶斯风洞**论文的 **arXiv** 版本，他们重现了实验。

<details>
<summary>Original English</summary>

**Vishal Misra**: And that's going in this direction. And I think people are coming around to the view that okay LLMs are doing Beijian learning. I know that some people also looked at the Beijian vent tunnel paper the archive version and they reproduced the experiments.

</details>

**主持人**: 太棒了。

<details>
<summary>Original English</summary>

**主持人**: That's great.

</details>

**Vishal Misra**: 他们只是看到了写了什么，然后他们进行了训练，他们看到了，是的，这确实发生了。

<details>
<summary>Original English</summary>

**Vishal Misra**: Did they just saw what was written and they they did the trading and they saw yeah this is actually happening. So

</details>

**主持人**: 太棒了。那么下一步是什么？

<details>
<summary>Original English</summary>

**主持人**: that's great. So what's next?

</details>

**Vishal Misra**: 下一步是，你知道，这两个平行的轨道，我希望在那里取得进展：**可塑性**和**因果关系**。

<details>
<summary>Original English</summary>

**Vishal Misra**: uh what's next is uh you know these two parallel uh tracks I hope to make progress there plasticity and causal

</details>

**主持人**: 因为今天你已经采取了一个现有的机制。

<details>
<summary>Original English</summary>

**主持人**: because today you've taken an existing mechanism

</details>

**Vishal Misra**: 你已经创建了一个形式模型来解释它是如何工作的。

<details>
<summary>Original English</summary>

**Vishal Misra**: and you've created a formal model how it works

</details>

**主持人**: 所以现在你实际上对改进和创建一个新机制感兴趣。

<details>
<summary>Original English</summary>

**主持人**: and so now you're actually interested in improving in creating a new mechanism

</details>

**Vishal Misra**: 你认为这是一种完全不同的架构吗？

<details>
<summary>Original English</summary>

**Vishal Misra**: and do you think it's an entirely different architecture

</details>

**主持人**: 或者你认为 **LLM** 是解决方案的一部分吗？

<details>
<summary>Original English</summary>

**主持人**: I or do you think do you think LLMs are like part of the solution

</details>

**Vishal Misra**: 我认为 **LLM** 绝对是解决方案的一部分。

<details>
<summary>Original English</summary>

**Vishal Misra**: I think LLMs are definitely part of the solution.

</details>

**主持人**: 我明白了。

<details>
<summary>Original English</summary>

**主持人**: I see.

</details>

**Vishal Misra**: 但必须有更多。

<details>
<summary>Original English</summary>

**Vishal Misra**: But but there has to be something more

</details>

**Vishal Misra**: 所以，你知道，我并不感兴趣于分类所有这些 **LLM** 能做什么。

<details>
<summary>Original English</summary>

**Vishal Misra**: and other. So you know I was not interested in sort of cataloging what all these LLMs can do.

</details>

**主持人**: 更感兴趣的是它们为什么以及如何做到这一点。

<details>
<summary>Original English</summary>

**主持人**: Was more interested in why are they and how are they doing it.

</details>

**Vishal Misra**: 我认为现在我们对为什么和如何有了很好的把握。

<details>
<summary>Original English</summary>

**Vishal Misra**: I think now we have a good grip on the why and how.

</details>

**主持人**: 下一步是，你知道。

<details>
<summary>Original English</summary>

**主持人**: And the next step is to you know

</details>

**Vishal Misra**: 将它们提升到下一个水平。我们现在，我认为我们对极限有了相当好的理解。

<details>
<summary>Original English</summary>

**Vishal Misra**: move them to the next level. We we now I I think we have a fairly good understanding of what the limits are.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 现在你如何迈向下一步？

<details>
<summary>Original English</summary>

**Vishal Misra**: Now how do you uh go to the next step?

</details>

**主持人**: 是否存在一种适用于**因果关系**的等效理论框架，类似于**贝叶斯**用于推理的框架？

<details>
<summary>Original English</summary>

**主持人**: Is there an is there an equivalent kind of theoretical framework for causality that applies here like similar to like Beijian for inference?

</details>

**Vishal Misra**: 嗯，**Judea Pearl** 的整个**因果层级理论**，我认为。

<details>
<summary>Original English</summary>

**Vishal Misra**: Well the Japal's whole causal hierarchy I think

</details>

**主持人**: 我认为那是正确的。

<details>
<summary>Original English</summary>

**主持人**: I think that's the right one.

</details>

**Vishal Misra**: 那是一个非常好的理论。你知道，整个**do-calculus**方法，我认为这是一个很好的思考方式。你知道，那种**关联**、**干预**、**反事实**。

<details>
<summary>Original English</summary>

**Vishal Misra**: That's that's a very good one. You know the whole do calculus uh approach I think it's a good way to think about it. you know the the sort of association intervention counterfactuals.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 它将你从**关联**带到实际的**模拟**。

<details>
<summary>Original English</summary>

**Vishal Misra**: It takes you from correlation to actually simulation.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Vishal Misra**: 以数学的方式。

<details>
<summary>Original English</summary>

**Vishal Misra**: In a mathematical way.

</details>

**主持人**: 太棒了。好的。听着，非常感谢你的到来。这太棒了。所以，你第一次来这里时，我们讨论了你的第一篇论文，其中有经验结果。

<details>
<summary>Original English</summary>

**主持人**: That's great. All right. Well, listen, really appreciate you coming. This is awesome. So, we had you here for the first paper where you had the empirical results.

</details>

**Vishal Misra**: 嗯。

<details>
<summary>Original English</summary>

**Vishal Misra**: Mhm.

</details>

**主持人**: 然后你又回来了，这次你带来了形式化的证明。希望你下次回来时，能提出一个关于机制的建议，它能真正提供下一步的解决方案。

<details>
<summary>Original English</summary>

**主持人**: And then we had you back when you actually have like the formal proof and hopefully the next time you come back you will have a proposal for the mechanism that uh that actually provides the next step.

</details>

**Vishal Misra**: 希望如此。

<details>
<summary>Original English</summary>

**Vishal Misra**: Hopefully.

</details>

**主持人**: 好的。太棒了。谢谢你的到来。

<details>
<summary>Original English</summary>

**主持人**: All right. Cool. Thank you for coming in.

</details>

**Vishal Misra**: 谢谢你的邀请。

<details>
<summary>Original English</summary>

**Vishal Misra**: Thank you for having me.

</details>