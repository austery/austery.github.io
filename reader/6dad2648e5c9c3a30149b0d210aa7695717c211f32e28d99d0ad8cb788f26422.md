---
author: AI Engineer
date: '2026-10-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=bU5gDVyu_28
speaker: AI Engineer
tags:
  - code-quality
  - disposable-software
  - software-architecture
  - engineering-rigor
  - technical-debt
title: 代码质量还重要吗？取决于这四大维度——从一次性软件到持久软件
summary: 探讨AI时代代码质量的本质与必要性。软件的成功归结于理解与执行，而代码质量的核心在于系统结构与降低变更风险。演讲者提出软件正划分为'一次性软件'与'持久软件'两大范畴，并给出了基于失败后果、替换成本、依赖度与维护成本的判定框架，同时分享了如何通过标准化与自动化工具降低工程严谨性的成本。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Capital One
products_models:
  - Chromium
media_books: []
status: evergreen
---
### 代码质量真的还重要吗？

>> 今天我觉得不如挑一个完全没有争议、谁都没有意见的温和话题，对吧？社交媒体上根本没人讨论这个，大家也知道，社交媒体上针对这个话题的观点往往都极具深度和细致入微的洞察，大家都很有深度，思考很宏大。也许这件事除了一句简单的“是”或“否”之外，还有更多可以探讨的内涵。当然，如果你问一位资深工程师任何问题，我们对所有问题的回答永远都是同一个，那是每位资深工程师最喜欢的答案——“看情况”（it depends）。

<details>
<summary>Original English</summary>

>> So, today I figured I'd just pick a nice uncontroversial topic that nobody has any opinions about. Right? Nobody nobody said anything on about on this about social media, you know, and of course every take about this on social media is like really deeply nuanced, you know, like people have lots of like depth and like, you know, really big thoughts. You know, maybe there's a little bit more to it than like yes or no. And you know, of course if you ever ask a senior engineer a question, we always have the same answer to every question, every senior engineer's favorite answer to every question, which is it depends.
</details>

不过坦率地说，这并不是一个很有用的回答，因为到底取决于什么呢？

<details>
<summary>Original English</summary>

Now, that's not a very helpful answer though, frankly, because what does it depend on?
</details>

### 为什么要关注代码质量：理解与执行

所以，我们先从这个问题开始：代码质量最初究竟为什么重要？我看到很多人会说，“因为它让我感觉良好。”但这并不是一个充分的理由。因此，让我们看看能否在这个讨论中注入一些细致的权衡，帮助大家在讨论时至少拥有一个推理的基础。让我们尝试在这里建立一个分析框架，这就是本场演讲要尝试做的事情。

<details>
<summary>Original English</summary>

So, let's start with this. Why did code quality ever matter in the first place? Like I see a lot of people be like, well, it made me feel good. That's not really a sufficient justification. So, let's see if we can inject some nuance into this conversation and help everybody at least be able to have a basis for reasoning about it while we're discussing it. So, let's see if we can make a framework here and that's what we're going to try to do with this talk.
</details>

好。我们首先要明确的是：你想通过软件达成的所有目标，都仅仅取决于两个因素，且仅取决于这两个因素——那就是**理解**，以及**基于这种理解去执行**。无论是模型对齐、系统扩缩容，还是推动用户采纳，任何事情都不例外。所有软件的成功都由这两个因素决定。这也是为什么我们会有调试器、可观测性、评估工具甚至测试这类东西。所有这些东西的存在，实际上都是为了提高你的理解能力，或是提高基于该理解去执行的能力。人们以为它们是为了其他原因存在的，但根本上它们就是为了这个原因。

<details>
<summary>Original English</summary>

Okay. So, we're going to start off with everything you want to ever accomplish with a piece of software depends on two factors and two factors alone. And that is understanding and executing on that understanding, whether that's aligning a model, scaling a system, driving adoption, anything. All software success is determined by these two factors. This is why we have things like debuggers and observability and evals and even tests. All those things actually are there to improve your understanding or ability to execute on that understanding. People think that they're there for other reasons, but fundamentally they're there for that reason.
</details>

我们在代码质量领域所做的一切，完全且仅仅是为了这两件事。它不为别的，并非关乎某种抽象的正确性或其他东西，它只与这两件事有关。

<details>
<summary>Original English</summary>

Everything we have ever done in the field of code quality is exclusively and only for these two things. It's not for anything else. Not doesn't have something to do with correctness or something else. It has to do only with these two things.
</details>

现在，如果你想成为一名软件工程师，最重要的两项理解是必须具备的。如果你从事产品或销售，可能需要对软件有其他的理解，但如果你是软件工程师，这两点是最为关键的。第一点是：**系统的行为是什么？** 这里的具体是指实际行为，而不是某份文档上描述的行为，是系统的真实行为究竟是什么？第二点是：**我该如何正确且安全地修改这种行为？** 对吧？

<details>
<summary>Original English</summary>

Now, there's two understandings that are the most important to have if you're going to be a software engineer. There are other understandings to have about software if you're going to be a product, if you're going to be in sales, but if you're a software engineer, there's the two that are the most important. And the first is what is the behavior of the system? Like con- the concretely, not what does a doc say the behavior of the system is, but what is the actual behavior of the system? And the second one is how do I correctly and safely modify that behavior, okay?
</details>

### 代码与结构的本质

在一个极小的系统上，如果你想理解系统做了什么，我直接告诉你它做什么就行了。它打印出“Hello World”。你说：“我想让它输出 Hi World。”我说：“好，我现在就让它输出 Hi World。”除了纯粹了解它做了什么之外，几乎没有什么需要去理解的，这就是你所需要的全部理解。然而，任何真实的软件系统都极其复杂。这是一张 Chromium 代码库的真实结构图，也就是 Chrome 背后的开源项目。如果你想一想这些组件之间相互交互的所有不同方式，它们的潜在可能行为基本上是无限的。

<details>
<summary>Original English</summary>

On a very small system, if you want to understand what the system does, I just tell you what it does. It prints hello world. You say, "I want it to say hi world." I say, "Okay, I will make it say hi world now." There's very little to understand about it other than purely what it does. That's all of the understanding that you need. However, any real software system is enormously complex. This is a real map of the code base of Chromium, which is the open-source project behind Chrome. And if you think about all of the different ways that these components can interact, they have essentially infinite possible behaviors.
</details>

比如，我不可能用语言向你完整描述 Chromium 作为一个系统整体的行为。

<details>
<summary>Original English</summary>

Like, I could not describe to you in words the behavior of Chromium as a whole as a system.
</details>

然而，我能够向你描述的——正如我们所知，大家做软件工程师都有一段时间了——是我可以向你描述系统的组件。我能够成功地向你描述系统中某个组件的行为方式。比如这里是 URL 解析器，Chromium URL 解析器的实际函数等等。它解析出 URL 的所有不同部分。

<details>
<summary>Original English</summary>

However, what I can describe to you, and as we all know, everybody's been a software engineer for a while, I can describe to you components of the system. I can successfully describe to you how a component of the system behaves. So, this is the URL parser, the actual functions and stuff for the URL parser of Chromium. It figures out all the different parts of the URL.
</details>

这就是代码存在的全部原因。我们最初之所以拥有代码，完全是为了**结构**。因为……这是什么意思呢？

<details>
<summary>Original English</summary>

And this is the whole reason that code exists. The whole reason that we have code at all in the first place is for structure. It Because it What do I mean by that?
</details>

好。如果在 Linux 机器上运行，左边和右边这两段都会打印出“Hello World”。然而，在左边，你可以看出它是“Hello World”，它具备“Hello World”的标识与结构。而在右边，你看到的只是一连串没有特定、可识别或可理解标识的指令。它不是一个组件，只是一堆指令。虽然在这里它尚且可以被理解，但如果是数百万或数十亿行这样的东西，理解起来就会困难得多。

<details>
<summary>Original English</summary>

Okay. So, both of these two things on the left and on the right will print Hello World if run on a Linux machine. However, on the left, you can see that it is Hello World. It has the identity and structure of Hello World. On the right, you just see a series of instructions with no particular identity, recognizable or understandable identity. It's not a component, it's just a bunch of instructions. While that's understandable there, if that was millions or billions of lines of that, it would be much harder to grok.
</details>

过去我们谈论过可读性、可测试性等看似针对代码的人性化概念，但真正最关键的始终是系统具备某种可理解的结构。所以，真正重要的是结构。

<details>
<summary>Original English</summary>

In the past, we've talked about things like readability or testability or things that seemed like human concepts about code, but what actually mattered the most always was that the system had some sort of understandable structure. So, it's the structure that actually matters.
</details>

### 修改系统的两大风险与复利危机

这种重要性在你想修改系统时体现得最为明显，也就是我们谈到的第二种理解。对系统的所有修改都会带来两类风险。第一类是你引入某种问题。所谓问题不仅仅指 bug，而是指任何可能发生的坏事。比如你的项目耗时远超预期；或者它的表现不符合你用户的需求；又或者项目因为预算超支而失败。仅仅因为你试图去完成这项变更的过程，就可能发生各种各样的问题。第二类是你可能会让未来的变更变得更加困难。具体而言，这意味着你增加了未来发生问题的可能性，增加了系统未来的风险。

<details>
<summary>Original English</summary>

And when this modifies when this matters the most is when you want to modify the system, the second uh understanding that we talked about. All modifications to a system carry two categories of risk. The first is that you will introduce some sort of problem. And a problem isn't just a bug, it's anything bad that could happen. Like your project could take much longer than you expect. Uh it could not behave in the way that you wanted it to for your users. The project could fail because you have budget overruns. Any kind of problem could happen from just you trying to go through the process of making this change. And the second is you could make it harder to make future changes. In particular, what that means is you can make it more likely to have future problems. You could increase future risk of the system.
</details>

这两件事都是由理解上的问题造成的。第一点与最初理解系统的难度有关，第二点是你让系统变得更难理解了。我可以把我看过的每一次事故复盘（postmortem）都以某种方式归结为这两个因素：生产环境配置太难理解、有人把某些东西写得无法理解、系统出现了无法理解的涌现特性等等。

<details>
<summary>Original English</summary>

These two things are caused by under problems with understanding. So, the first has to do with the difficulty of understanding the system in the first place, and the second is you make the system harder to understand. I can reduce every postmortem I have ever read for any incident to these two factors in one way or The the production configuration was too hard to understand, somebody made something impossible to understand, there were emergent properties of the system that were impossible to understand, whatever.
</details>

第二点会反哺第一点，形成恶性循环，以非线性的方式复合累积。因此，理解的难度并不是线性增长的，它是随时间推移复合增长的。你最终会达到一个临界点——而且所有系统最终往往都会到达这个临界点——在那时每一次修改都会带来某种问题。

<details>
<summary>Original English</summary>

Point two feeds into point one in a vicious cycle that compounds in a non-linear fashion. So, the difficulty of understanding does not grow linearly, it compounds over time. You will eventually reach a point, and all systems eventually tend to reach this point, where every modification involves some sort of problem.
</details>

有些系统甚至会到达完全无法修改的地步。比如想想那些拥有1亿行、5亿行的大型主机（mainframe）代码库，在那种系统里，任何变更都会带来某种问题。你会发现它体现在组织架构问题上，体现在各个方面，体现在交付周期上等等。

<details>
<summary>Original English</summary>

Uh and you know, some some systems get to the point where like you can't modify them at like if you think of like, you know, some of like your giant 100 million 500 million line mainframe code bases and that everything, every change is some sort of problem. You know, you'll see it in organizational issues, you'll see it all over the place, you'll see it in timelines, whatever.
</details>

### 新范式：一次性软件（Disposable Software）的崛起

看，现在有很多争论说未来的大模型或许能解决这个问题。也许确实能，也许未来的模型以某种方式拥有处理复杂度的无限能力。但我们今天不必讨论这一点，因为我认为现在的模型正在做另一件非常有趣的事情：它们正在创造一种全新形态的软件、一个全新的软件类别。这个类别一直都存在，但它即将变得比任何其他软件形态常见十万倍。那就是——**一次性软件（disposable software）**。

<details>
<summary>Original English</summary>

And look, there's a lot of arguments about maybe future models will fix this. Look, maybe they will. Maybe future models will have infinite ability to deal with complexity somehow. Uh but we don't have to discuss that today because I think models are doing something else really interesting right now. They are creating a new kind of software, a new category of software. This category has always existed, but it's about to become a hundred thousand times more common than any other form of software. And that is disposable software.
</details>

那到底什么是“一次性软件”？想象一下这样一个世界：在这个世界里，你系统的失败后果非常微小甚至根本不存在；想象一下只有极少数人依赖它，或者几乎没有其他系统依赖这个软件；变更管理要求极低甚至没有；想象一下它的替换成本降到了近乎为零，你可以在几小时或几天内替换掉整个系统；而且它基本上没有维护成本。在那个世界里，代码质量根本无关紧要。因为我们之前试图防止的所有随时间复合累积的风险，在那里统统不存在。

<details>
<summary>Original English</summary>

So, what is that? Okay. So, imagine a world in which the consequences of failure for your system are very minimal or non-existent. Imagine that there's very few people that depend on it or and almost no other systems depend on that piece of software. Change management, very minimal, non-existent. Imagine the cost of replacement went to near zero. You could replace the whole thing in hours or days. And it had basically no cost of maintenance. In that world, code quality does not matter. Because it all of those things we were trying to prevent about the compounding risks over time don't exist.
</details>

传统上，我们一直构建的是**持久软件（durable software）**。你知道，它会存活多年，被数千或数百万人所依赖。它失败的后果极其严重，可能是业务毁灭性的灾难后果，而且它需要大量的维护。世界上绝大多数软件工程师的大部分时间，都花在维护这些庞大的持久系统上。我认为这种情况将继续存在。所以在这一点上，我认为社交媒体上的讨论有时走偏了。

<details>
<summary>Original English</summary>

Traditionally, we've always built durable software. You know, it lives for years. It's depended on by millions or thousands of people. There's huge consequences of failure, potentially business catastrophic consequences of failure. And it requires enormous maintenance. Most of the software engineers in the world spend most of their time maintaining these giant durable systems. I expect this to continue to exist. So, this is one of the areas where I think sometimes the conversation goes a little astray, okay?
</details>

持久系统在未来大概率仍将是世界上最重要的系统，而且它们的数量可能还会更多。但是数量最庞大的系统，将是一次性软件。它们可以在几小时内被替换，依赖者极少，或者变更管理根本无所谓。如果它跑不通，大家都有智能体（agents），用户自己就能做出一个版本来。维护根本不重要或者近乎免费。不喜欢操作系统自带的计算器？自己做一个。想为孩子筹办一场派对？专门为那一场派对写一个派对策划软件。用完就扔掉。代码质量根本无所谓，没人在乎。

<details>
<summary>Original English</summary>

Durable systems will continue to probably be the most important systems in the world. And there will be probably more of them. But the most numerous systems will be disposable software. They will be replaceable in hours. They will be depended on by a few or change management just won't matter. And look, if it doesn't work, you will give everybody agents. They'll make a version of it themselves. You know, maintenance will be unimportant or nearly free. Don't like the calculator on your OS? Make your own. Want to plan a party for your kids? Write a party planner software just for that one party. Throw it away. Code quality doesn't matter. Nobody cares.
</details>

### 衡量光谱：决定工程严谨度的四大要素

在未来，我们将根据软件的“可抛弃程度”来施加相应的工程严谨性（engineering rigor）。在光谱的最左端，什么都不需要，我们所有的工程严谨性实践根本毫无意义。在光谱的最右端，我们在过去几十年里建立起来的所有工程实践都至关重要。

<details>
<summary>Original English</summary>

In the future, we will apply engineering rigor to the degree of disposability of the software. On the left, nothing. None of our practices of engineering rigor matter at all. On the right, all the practices of engineering that we have built up over the last many decades matter greatly.
</details>

我们可以通过我一直在讲的这四个要素，来判断你处于这个尺度的哪个位置：**后果（Consequences）**、**替换成本（Cost of Replacement）**、**依赖关系（Dependencies）** 和 **维护成本（Cost of Maintenance）**。如果它们都很低，那就是一次性软件；如果它们都很高，那就是持久软件。而且，任何写过很久代码的人都知道，你应当倾向于将软件视为持久软件，你应该假定这些因素都比你预期的要高。

<details>
<summary>Original English</summary>

We can determine where you are on this scale by those four factors that I have been talking about. Consequences, cost of replacement, dependencies, and cost of maintenance. If they're all low, it's disposable software. If they're all high, it's durable software. And look, any person who's written software for a long time knows you should err on the side of it being durable. You should err on these all being higher than you expect them to be.
</details>

### 让软件更具“一次性”：软件工程的新学科

但世界上现在还有一件你可以做的新事情：你可以**主动让软件变得更具一次性**。那具体涉及什么呢？比如设计出隔离度更好的环境。也就是说，“嘿，你只能部署到这个环境，这个环境只能访问你自己的数据，没有客户数据，没有个人身份信息（PII）等等。”

<details>
<summary>Original English</summary>

But, there's also a new thing you can do in the world. You can make software more disposable. So, like, what do What does that involve? Well, come up with better isolated environments, right? So, hey, you can only deploy to this environment that has access to only your data. No customer data, no personally identifiable information, whatever.
</details>

你可以强制执行独立性。你可以规定：“好，在这个环境里，不允许来自其他生产系统的入站 API 调用接入这个系统，对吧？”这样一来，部署到该环境中的所有内容就都是一次性的了。

<details>
<summary>Original English</summary>

You can enforce independence. You can say, "Okay, no inbound API calls from other production systems are allowed to this system in this environment, right?" And so, everything deployed to that environment is disposable.
</details>

还有冗余性。你可以保留一个虽然老旧笨重、难以使用但稳固的后备系统。然后，如果人们想去“氛围编码”（vibe code）自己更高效的前端，那就让他们去 vibe code 出他们更高效的前端吧。因为有一个老旧、持久、笨重的后备系统存在，一旦他们那个粗糙的 vibe coded 小玩意挂了，他们还可以退回去用老系统。它确实会挂掉，对吧？没关系，即便挂了也无关紧要。

<details>
<summary>Original English</summary>

Redundancy. You can have an old clunky backup system that is like hard to use. And then, like, look, if people want to vibe code their own like more efficient front ends, you let them vibe code their more own more efficient front ends because there is an old durable clunky backup system that they can use if their, you know, crappy little vibe coded thing fails. Which Which it will fail, right? That's fine. But, it doesn't matter if it fails.
</details>

你还可以限制范围，就像我刚才说的，它只是给这一个人用的计算器，或者它仅仅用来筹划这一次派对。我们在这里还可以做很多事情，探讨很多增加一次性特征的方法。事实上，我认为这是一门**全新的软件工程学科**：不再去思考如何提高持久系统的严谨性，而是如何审视我们的系统，去鼓励或允许更高的一次性，让人们可以放心地扔掉这些东西。这真是一个有趣的思路。

<details>
<summary>Original English</summary>

Uh and you can limit scope, just like I talked about, right? It's just a calculator for this one person. It just plans this one party. There's so much more we could do here and talk about ways of increasing disposability. In fact, I think this is a whole new discipline of software engineering, not to think about how we improve the rigor of durable systems, but how do we take our systems and how do we encourage disposability or allow more disposability, allow people to throw these things away. Interesting thought.
</details>

### 降低严谨性的成本

现在，我想再次强调，持久软件工程绝不会消失，因为这是我目前在社交媒体上看到的最大困惑。事实上，我相信世界上持久软件的绝对总量还会增加，因为 AI 编码工具使得构建持久软件变得越来越容易。

<details>
<summary>Original English</summary>

Now, I want to re-emphasize that durable software engineering is not going away because this is the biggest confusion that I see on social media today. In fact, I believe the absolute amount of durable software in the world will increase because AI coding tools make it easier and easier to make more durable software.
</details>

另一个需要理解的要点是，一次性与持久并不是非黑即白的。正如我之前展示的，它是一个光谱。而在该光谱上变化的，是你将为工程严谨性投入多少精力。这包括即时投入的精力，也包括随时间推移持续投入的精力，正如我们过去一直针对软件所探讨的那样。

<details>
<summary>Original English</summary>

And another important thing to understand is that disposable and durable are not black and white. There's a spectrum, like I showed before, but that spectrum what changes across the spectrum is how much effort you're going to put into engineering rigor. Okay? And that's both immediate effort and effort over time, just like we've always talked about for software.
</details>

然而，你真正应该做的、我认为你最应该关心的，是**降低付诸精力的成本，降低工程严谨性的成本**。如果严谨性的成本更低，如果让软件具备严谨性变得越来越轻而易举，你就越来越不必纠结自己在光谱上的具体位置。这是你可以采取的另一种方法。如果你改变了主意，比如你原本以为它是一次性的，现在发现它需要变成持久的，如果你当初让它变得持久的成本足够低，那么改变主意或犯错的代价就小得多。因为在那种预估上，你永远不可能做到百分之百全对。

<details>
<summary>Original English</summary>

However, what you want to do, and I think what you want to care about the most, is reducing the cost of effort, reducing the cost of rigor. Like, if rigor is cheaper, if it's the the easier and easier you make it to be rigor, the less you have to worry about where you are on the scale. So, this is another approach you can take. If you change your mind, it's much easier to go like you're like, "Oh, I thought this was going to be disposable and now it needs to be durable." The cheaper you make it to make it durable, the easier it is to change your mind or to be wrong because you're never going to be 100% right all the time on that estimate.
</details>

这就涉及了一套不同的实践，它们本身不是工程严谨性本身，而是关于如何降低工程严谨性的成本。对此我可以滔滔不绝讲上好几个小时，我的职业生涯有很大一部分时间都花在了这件事上。我没有10个小时，计时器上大概还剩5分钟，所以我就捡能讲的讲，好吗？

<details>
<summary>Original English</summary>

So, that involves a different set of practices that are not engineering rigor themselves, but that are about how to decrease the cost of engineering rigor. Now, I could talk about this for hours. I have spent a tremendous amount of my career doing this. Uh I don't have 10 hours. I have about 5 minutes left on that timer. So, I'll tell I'll talk about what I can, okay?
</details>

### 降低严谨性成本的四大实践

我们先来谈谈**标准化（Standardization）**。我们为什么要做标准化？人们会说：“呃，我不知道，因为老板这么要求的。”不，我们做标准化是因为它排除了可能性。如果你的系统中没有任何 PHP，你就不必去搞清楚 PHP 的所有 linter 是什么、最佳实践是什么、有哪些必须修复的安全漏洞。你仅仅通过标准化就排除了这些可能性，它直接降低了严谨性的成本。

<details>
<summary>Original English</summary>

Let's talk about standardization. Why do we do standardization? People are like, "Well, I don't know because the boss said so." Well, now, we do standardization because it removes possibilities. If you don't have any PHP in your system, you don't have to figure out what are all the linters for PHP, what are all the practices, what are all the security holes I have to fix. You just eliminate possibilities through standardization and it just reduces the cost of rigor.
</details>

框架也是同样的道理。为什么你不想把世上存在的每一种前端框架或后端框架都引入进来？因为这会让严谨性的成本大幅攀升。是的，严谨性依然是可能的；是的，你依然可以让智能体帮你编写所有工具代码，但你每一次都必须重新做一遍。协议也是如此。为什么要采用标准化的 RPC 协议？完全是同一个道理。所有的标准都是为了这个目的。

<details>
<summary>Original English</summary>

Uh same thing with like frameworks. Like why don't you want to have every front-end framework or every back-end framework in the in existence? Because it makes rigor more expensive. Like yes, rigor is still possible. Yes, you could still have the agent code up all your tools, but you have to do it every single time. Uh you know, proto- uh protocols. Why do you want to have standardized RPC protocols? All the same thing. Standards are all for this reason. Okay?
</details>

其次是我所说的**内流式工具（inward flow tooling）**。所谓内流式工具，就是自然发生、无感运行的工具。程序员不需要特意选择去运行它，他们不需要理解它是怎么跑起来的，它自然而然就会执行。如果它在那里，感觉和看起来就像是免费的，而且它非常可靠。可靠性极其极其重要。比如它不会产生大量的误报，它速度极快，悄无声息地完成。这一点越成立，你就越可以把它同样应用到你的一次性软件中。如果它又免费又快，谁在乎呢？

<details>
<summary>Original English</summary>

Uh what I call inward flow tooling. So, inward flow tooling is tooling that just occurs. The programmer doesn't have to choose to run it. They don't have to understand how it runs. It just happens. If it's there, it it's feels and seems free and it is reliable. Reliability is very, very important. Like it doesn't have a ton of false positives. It's fast. It just happens. And the more that's true, like you can apply it to your disposable software, too. If it's free and fast, who cares?
</details>

第三是**让测试变得更容易**。这不仅仅关乎“嘿，我们如何把测试做得更好？”想想看，你如何做到让任何人都无需去思考“该如何做好测试”？你如何让每一次测试都又快又确定（deterministic），而无需任何人成为深度的测试专家？要实现这一点，你必须在测试基础设施上投入大量的工作。举个例子，作为测试负责人，我一直以来的一个宏大梦想，就是每个人都能为他们的服务提供内存中的仿真实现（in-memory fake versions），这样我就能直接运行这些内存仿真服务。猜猜怎么着？编码智能体现在就能做到这一点。所以你现在就可以去实现它，对吧？但你必须主动选择去做，并把它开放给所有人使用。

<details>
<summary>Original English</summary>

Uh making testing easier. So, this is not just about like, "Hey, how do we do better testing?" Look, how do you make it so that nobody has to think about how to do better testing? How do you make it so that every test is fast and deterministic without anybody having to be a deep expert in testing? There's a ton of work that you have to put into test infrastructure to make that possible. For example, you know, one of the great dreams that I've always had as a as a test owner is that everybody would provide in-memory fake versions of their services and I could just run those in-memory fake versions of their services. Guess what? The coding agent can do that. So, you can just do that now, right? But you have to choose to do it and make it available to everybody.
</details>

还有一点，那就是**追求极致的严格（maximum strictness）**。你只需把各处的严格度拉满。把所有的静态检查规则（lint rules）调到最高级别，在任何事情上都不妥协，这会消除很多分歧——它与标准化非常相似，能省掉大量的无谓争论。有时候 linter 可能会报错，但只要误报率相对较低且不会造成灾难性后果，那就无所谓，因为突然之间一大堆未来的 lint 错误或未来隐患就被你提前扼杀了，免去了后续处理的麻烦。不妨去问问那些突然想在百万行代码库中开启 linter 的人，他们往往会惊呼：“天啊，现在我得提一个十万行的修改，对吧？”提前把它做好并对所有人默认开启，显然要容易得多。

<details>
<summary>Original English</summary>

And another thing is, look, maximum strictness. You just turn the strictness up everywhere. You turn You set all your lint rules to maximum. You You never compromise on anything and it just eliminates It's very similar to standardization. It eliminates a ton of conversations. Sometimes the lint is wrong. Like as long as the false positive rate is relatively low and it doesn't have catastrophic consequences, it doesn't matter because all of a sudden there's a bunch of future lint errors or future issues that you don't have to deal with. Like, ask anybody who's been like, "Oh, I suddenly want to turn on my linter in this million-line code base." And they're like, "Oh, wow. Now here's my 100,000-line change that I need to make, right?" Much easier to just do that up front and have it on for everybody. Now, look.
</details>

### 总结与结论

正如我所说的，我完全可以在这里站着连续跟你们聊上10个小时。在这里你能做的事情还有很多很多，这仅仅是几个方面，但它也是你可以应用在另一条轴线上的整个软件工程学科体系。

<details>
<summary>Original English</summary>

Like I said, I could literally stand here and talk to you about this straight for 10 hours. There is much, much more you can do here. This is just a few areas, but also a whole area of software engineering discipline that you can apply on the other axis. So, this lets us now answer our question, not just it depends, but yes or no.
</details>

因此，现在我们终于可以回答最初的问题了，不再只是一句“看情况”，而是明确的“是”或“否”：

代码质量到底还重要吗？

对于一次性软件：**不重要。**

对于持久软件：**重要。**

而且我们还能顺带回答第三个、甚至是更有趣的问题：

工程严谨性必须昂贵且高成本吗？

**不必。**

非常感谢大家。

>> [掌声]

<details>
<summary>Original English</summary>

So, does code quality even matter? For disposable software, no. For durable software, yes. And we get to answer a third and even more interesting question, which is does it have to be expensive? No. Thank you very much.

>> [applause]
</details>