---
author: AI Engineer
date: '2026-11-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ys6YQ2yfBpM
speaker: AI Engineer
tags: []
title: ''
summary: ''
insight: ''
draft: true
series: ''
category: ''
area: ''
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/9 -->

我们可以开始了。感谢大家的到来。我是 Lance，Anthropic 的技术人员。今天我其实想和大家分享一些非常简单的东西，几种充分利用前沿模型的简单方法。

<details><summary>Original English</summary>
We can kick it off. Thank you all for coming. I'm Lance. I'm member of technical staff at Anthropic. And I actually want to share some very simple things with you today. A few simple ways to get the most out of frontier models.
</details>

我们通常认为成本和质量之间存在权衡。所以为了获得更好的性能，你就必须花更多的钱；而为了降低成本，你就必须牺牲性能。所以你可以这么考虑，在任何给定的评估中，模型都会构成这样一条帕累托前沿。

<details><summary>Original English</summary>
So we typically think of cost and quality as a trade-off. So in order to get, you know, better performance, you have to spend more money. And in order to kind of reduce cost, you have to scratch sacrifice performance. And so you can kind of think about it on any given evaluation, you have models that kind of create this Pareto frontier.
</details>

你可以设想这种情况，Fable 处于曲线的最右上方，然后你有 Opus，有 Sonnet，再然后有 Haiku。

<details><summary>Original English</summary>
And you can imagine this case, Fable is kind of up on the far right of the curve, and then you have Opus, you have Sonnet, then you have Haiku.
</details>

现在我想分享的其实是，很多时候你实际上并没有处在这条前沿上。你的应用程序其实是落在了你本可以达到的前沿之内。这是因为一些微小的错误配置，我今天将向大家展示如何修复它们。

<details><summary>Original English</summary>
Now what I want to share is actually that many times you're not actually on this frontier. Your application is actually sitting inside this frontier that you could be on. And it's because of minor misconfigurations. Which I'm going to show you today how to fix.
</details>

>> [嗤笑声]

<details><summary>Original English</summary>
>> [snorts]
</details>

>> 我们已经反复看到这种情况。通过一些非常简单的方法，为许多客户提升了性能并降低了成本。

<details><summary>Original English</summary>
>> And we've seen this repeatedly. Improve performance and reduce cost for many customers using some view very simple things.
</details>

首先，我将涵盖五个主题。然后我们可以进行互动。幻灯片用不了一个小时，差得远呢。所以问答其实要有意思得多。

<details><summary>Original English</summary>
So first, I'm going to cover five themes. And then we can make it interactive. The slides won't take an hour. Not even close. So I question answering is actually much more fun.
</details>

### 审查提示词

第一，审查你的提示词。这是一个挺重要的观点：提示词就像代码一样会累积债务。如果大家还记得几代之前，我们过去常常使用像“逐步思考”（think step-by-step）这样的东西；过去常常使用验证仪式，“复查你的工作”（double-check your work）；过去常常使用思维助推词，“要极尽周全”（be maximally thorough）；有时我们会使用类似草稿纸的东西，告诉智能体如何思考，给它思考的空间。

<details><summary>Original English</summary>
First, audit your prompts. This is a kind of important point that prompts accumulate debt just like code. So if you recall several generations ago, we used to use things like think step-by-step. We used to use verification rituals, double-check your work. We used to use thought from this boosters, be maximally thorough. Sometimes we would use kind of scratch pads, tell the agent how to think, give it places to think.
</details>

你现在不再需要那些了。前沿模型非常擅长思考、选择何时去思考。它们不需要被告知该做什么以及如何验证它们的工作，它们会自然地验证自己的工作。它们不需要被告知要周全，它们已经非常周全了。

<details><summary>Original English</summary>
You don't need that anymore. Frontier models are very good at at thinking, choosing when to think. They don't need to be told what to do and like kind of how to verify their work. They naturally verify their work. Um they don't need told to be thoughtful. They're already very thoughtful.
</details>

更糟糕的是，当你做这些事情时，它实际上增加了成本，而且可能在某些方面降低性能，我稍后会简要谈谈这点。

<details><summary>Original English</summary>
Um and worse, when you do these things, it actually increases cost and can reduce performance in some ways I'll talk about briefly.
</details>

早前模型另一个有趣的现象是，如果你的提示词中含有相互矛盾的规则，那些不太擅长遵循指令的早期模型往往会忽略两条规则中的一条。所以它在某种程度上仍能工作。但是对于前沿模型，它们往往会被相互矛盾的规则搞糊涂。

<details><summary>Original English</summary>
Another interesting one with earlier models, if your prompt had contradictory rules in them, earlier models that weren't as good at instruction following would kind of ignore one of the two rules. So it kind of still worked. But with frontier models, they'll often get confused by contradictory rules.
</details>

所以如果你有任何想要检查的代码，我现在要给你一件非常简单的事情去做。在 Claude Code 中，你可以运行这个命令：`checkup prompt audit`。

<details><summary>Original English</summary>
So I'm going to give you one very simple thing to do right now if you have any code that you want to check. In Claude code, you can run this command checkup prompt audit.
</details>

你也可以运行 `Claude API prompt audit`。这是 Claude Code 中的两个不同技能。它们链接到同一段代码。只是 checkup 通常是大家检查其 Claude Code 配置本身的方式——也就是你在 Claude Code 本身之内的技能和提示词；而 Claude API 技能是捆绑在 Claude Code 中的独立技能，适用于使用我们 API 的代码。但这两个命令使用的原理相同，并且它们基本上都链接到同一个底层技能本身。这只是两种不同的调用方式。

<details><summary>Original English</summary>
You can also run Claude API prompt audit. These are two different skills in Claude code. They link to the same code. It's just checkup is typically how people do checkups on their Claude code configuration itself. So your skills, your prompts within Claude code itself, the Claude API skill is a separate skill bundled in Claude code that's meant for a kind of code that uses our APIs. But both of these commands use the same principle and they kind of link down to the same underlying skill itself. It's just two different ways to call it.
</details>

>> [嗤笑声]

<details><summary>Original English</summary>
>> [snorts]
</details>

>> 这些技能将审查你的代码，Claude Code 工作目录中的任何内容。所以那可以是技能、可以是工具、可以是提示词，检查这些反模式，并为你移除它们。

<details><summary>Original English</summary>
>> These skills will audit your code, anything in the working directory of Claude code. So that could be skills, that could be tools, that could be prompts for these anti-patterns and will remove them for you.
</details>

这变得非常受欢迎。许多人……我们在 Anthropic 内部许多人都在使用它。它在 Twitter 上也变得挺受欢迎。这非常简单，而且往往能降低成本并提升性能。

<details><summary>Original English</summary>
This has become kind of very popular. Many people we all Many people use it within Anthropic. It's kind of become somewhat popular, you know, on Twitter as well. Um it's very simple and often it can improve cost and performance.
</details>

这里有一个例子，这是我构建的一个评测。这是一个针对客户支持工单的合成评测，大约有 50 张工单。我所做的是以 Opus 48 开始，基本上模拟向 Opus 55 的迁移，好吗？

<details><summary>Original English</summary>
So here's an example uh where it This is an evaluation that I built. It's a synthetic evaluation of customer support tickets. There's like 50 tickets. And what I do is I start with Opus 48. And I basically simulate a migration to Opus 55, okay?
</details>

在这个过程中，我单独注入每种反模式并衡量结果。那就是中间那个点，明白吗？所以，实际情况是，它基本上取了整个基准测试中所有反模式的平均值。关键点在于：当我从 48 迁移到 Opus 55 时，最初在注入了这些反模式的情况下，我们确实看到了一些成本节省和一点点性能节省。你可以看到它向左移动，并且向上走了一点。

<details><summary>Original English</summary>
And in this process, I inject each anti-pattern individually and measure the result. That's this middle point, okay? So, what happens is it's taking the average of all the anti-patterns across the benchmark, basically. The key point is this. When I do the migration to Opus 55 from 48, initially with these kind of anti-patterns injected, we do see some cost savings and a little bit performance savings. You can see it goes to the left and it goes up a bit.
</details>

如果在此基础上运行 prompt audit，由于诸多不同的原因，我在性能提升和成本降低上都获得了进一步的提振。因为这个命令会逐一检查并移除验证仪式、以及那些实际上导致 Opus 55 消耗过多 token 的助推词。

<details><summary>Original English</summary>
If I run prompt audit on top of that, I get a further bump both in performance and cost reduction for a bunch of different reasons. Because this command is going through and it's removing verification rituals, boosters that are actually causing Opus 55 to expend excessive tokens.
</details>

因此，这个简单的小命令通常基本上可以减少 token 使用量、节约成本，并且在诸如相互矛盾的提示词困扰前沿模型的情况下，它能够提升性能。

<details><summary>Original English</summary>
So, this little simple command often will basically reduce token use, saving cost, and it can improve performance in cases where things like contradictory prompts were confusing frontier models.
</details>

所以这是我推荐的一个非常简单的命令。我们在 Anthropic 内部非常广泛地使用它，并且许多客户也相当喜欢这个命令。运行它非常简单。你可以在任何使用 API 的代码中运行它，甚至可以在你的 Claude Code 配置上运行它，以确保你的提示词针对前沿模型进行了良好调优。这是第一点。

<details><summary>Original English</summary>
So, this is a very simple command that I recommend. Um and we've used it very extensively within Anthropic and also many customers have enjoyed this quite a lot. It's very simple to run. You run it kind of in any code using the API or even on your cloud code configuration to make sure your prompts are kind of well-tuned for frontier models. That's point one.
</details>

### 使用提示词缓存

第二点是确保你在使用提示词缓存（prompt cache）。这对于许多用户来说可能相当熟悉，但我确实想确保这一点极为清楚。比方说，智能体是跨多轮运行的。每一轮都只增加一点点，例如一次工具调用。

<details><summary>Original English</summary>
Now, point two is make sure you're using the prompt cache. This is probably pretty familiar to many of users, but I do just want to make sure it's extremely clear. So, agents, for example, operate across many turns. Every turn adds just a little bit. For example, one tool call.
</details>

许多上下文在多轮之间是重复的。你不会想为此支付两次费用。这就是为什么你可以使用提示词缓存。提示词缓存的计费大约是基础 token 费率的十分之一，所以要便宜得多。不同模型之间略有差异。我想十分之一大概是当前的定价，不过你可以查看定价页面。关键在于它便宜得多。

<details><summary>Original English</summary>
Much of kind of context is repeated across turns. You don't want to pay for it twice. That's why you can use the prompt cache. So, prompt cache is built at like a tenth the the rate of base tokens. So, it's much cheaper. Varies a bit per model. I think 10 a a tenth is I think the current pricing, but you can check the pricing page. The point is it's much cheaper.
</details>

它也快得多。因此在多轮应用程序中，大量使用提示词缓存是非常重要的。

<details><summary>Original English</summary>
It's also much faster. So, it's very important in multi-turn applications to be making heavy use of the prompt cache.
</details>

现在问题在于，提示词缓存是严格的前缀匹配。因此前缀中哪怕一个字节的改变都会使缓存失效。所以在构建智能体或多轮应用程序时，你必须小心不要破坏提示词缓存。这就是关键点。

<details><summary>Original English</summary>
Now, the problem is prompt cache are a strict prefix match. So, any even a byte change in your prefix will invalidate the cache. So, you have to be careful in building agents or multi-turn applications that you don't break the prompt cache. That's the key point.
</details>

如果你使用 API，Claude 控制台为你提供了很好的诊断功能。所以如果你正在用 Claude API 构建应用程序，你可以看到应用程序的提示词缓存命中率，跟踪这一点非常重要。

<details><summary>Original English</summary>
And Claude console, if you're using the API, has nice diagnostics for you. So, if you're building applications with the Claude API, you can see for your application your prompt cache hit rate, which is very important to track.
</details>

例如在 Claude Code 中，我们非常非常虔敬地跟踪提示词缓存命中率。这对于应用程序的经济性显然非常重要。同样在你们的情况下，如果你正在用 Claude API 构建应用，确保你在大量使用提示词缓存是非常非常重要的。

<details><summary>Original English</summary>
For example, with Claude code, we track the prompt cache hit rate very very religiously. It's very important for the economics of the application, obviously. And it's also in your cases, if you're building apps with the Claude API, it's very very important to make sure you're using making heavy use of the prompt cache.
</details>

那么总体上该如何组织你的提示词呢。你可以基本这样考虑：系统指令、工具，这些在你的所有会话中都是全局缓存的。你可以考虑 Claude MD 内存，那是每个项目进行缓存的。会话状态是每个会话特有的，然后消息基本上是每一轮递增的。你大体上会想这样来构建你的提示词。

<details><summary>Original English</summary>
Now, in general, how to organize your prompts. You know, you can think about basically, um system instructions, tools, things that are globally cached across all of your sessions. You can think about Claude MDM memory. That's kind of cached per project. Session state is kind of per session, and then messages kind of incremented each turn. So, that's kind of how you want to structure your prompts.
</details>

关键点是：在 Claude Code 中运行这个。所以如果你有一个使用 API 的项目，你想要检查并确保你在正确使用提示词缓存。你可以运行这个。它将运行诊断程序，确保你有效地使用了提示词缓存。它会找到重新组织提示词的机会，确保它们被组织得能让你获得较高的提示词缓存命中率。这确实是这里的关键点。

<details><summary>Original English</summary>
And the key point is this, run this in Claude code. So, if you have a project using the API, you want to make check and make sure that you're using you're making proper use of the prompt cache. You can run this. It'll run diagnostics to make sure that you're using the prompt cache effectively. It'll find opportunities to reorganize your prompts to make sure that they're organized such that you get a high prompt cache hit rate. That's really the key point here.
</details>

>> [叹气声]

<details><summary>Original English</summary>
>> [sighs]
</details>

>> 这算是一个挺有趣的练习。我和我们 Claude AI 团队的一些同事，在许多具有默认测试套件（harness）的内部基准测试上运行了这个命令。仅仅通过运行这个命令，我们就发现了在性能没有明显变化的情况下将成本降低高达 72% 的机会，因为这些评测中的某些测试套件之前没有正确使用提示词缓存。

<details><summary>Original English</summary>
>> And this is kind of a fun exercise. So, myself and some folks on our Claude AI team ran um ran this command on a bunch of internal benchmarks that had kind of default harnesses. We found opportunities to reduce costs by up to 72% with no meaningful change in performance, just by running this command, because some of the harnesses on these Evals were not using the prompt cache properly.
</details>

非常简单的命令。你可以在你的 API 代码中运行它，它只会寻找机会以确保你尽可能地节省成本，即通过使用提示词缓存。它还会检查其他事项。它会寻找……我稍后会谈谈这个，但它也会检查你的 effort

<details><summary>Original English</summary>
Really simple command. You can run it in your API code and it'll just look for opportunities to make sure you're saving as much cost as you should be, i.e. by using the prompt cache. It'll also check for other things. It'll look for um I'll I'll talk about it a little bit later, but it'll also check your effort
</details>

<!-- chunk 2/9 -->

levels，它会检查你的 prompt。它还会做很多其他事情，但尤其是会查看你的 prompt cache，以确保你有很高的 prompt cache 命中率。

<details><summary>Original English</summary>
levels, it'll check your prompt. So, it it'll do a number of other things, but in particular it'll look at your prompt cache to make sure you have a high prompt cache hit rate.
</details>

再次强调，优化 prompt cache 对性能没有任何改变。这实际上就等于免费节约成本。所以，特别是当你使用 API 构建应用程序时，这是一件非常需要认真对待的事情。这是一件非常需要认真确保有效利用的事情。

<details><summary>Original English</summary>
Again, this has, you know, optimized prompt cache has no change in performance. It's like effectively just free cost savings. So, it's something to be very serious about when you're building applications with the API in particular. Um it's very something to very to very seriously make sure you're utilizing effectively.
</details>

### 前沿模型的评测设计与爬山算法

所以，我想进入其他一些基本原理。我们讨论了 prompt caching，讨论了确保你的 prompt 调整得当。你可以使用 prompt cache 来审计它们。现在，我们来讨论一些对使用前沿模型非常重要的其他事情。

<details><summary>Original English</summary>
So, I want to get into to some other fundamentals. Um we talked about prompt caching, we talked about making sure your prompts are kind of well that are that are well-tuned. You can audit them using prompt cache. Now, let's talk about a few other things that are very important for working with frontier models.
</details>

Claude，尤其是前沿的 Claude，非常擅长自我纠错。所以，如果你给 Claude 一个结构良好的 evaluation，它基本上就可以在那个 eval 上进行 hill climb，我稍后会讲到这一点。

<details><summary>Original English</summary>
So, Claude, frontier Claude in particular, is very good at self-correction. So, if you give Claude a well-structured evaluation, it can basically just hill climb on that in that eval and I'll talk about that in a minute.
</details>

但其中重要的是良好的 eval 设计。你必须给 Claude 一个可以爬升的 evaluation。因此，实际上我们在 eval 设计上花了很多时间思考，确保在构建 eval 和设置 hill climbing 时让 Claude 具备成功的条件。

<details><summary>Original English</summary>
But important in that is good eval design. And you have to give Claude an evaluation that is climbable. And so, actually we spend a lot of time thinking about eval design and making sure Claude is set up for success when building an eval and setting up hill climbing.
</details>

那么，良好 eval 设计的一些普遍特征。这是基础，这跟 Anthropic 没什么关系，这只是一些基本原理，但简要重温一下是很有益的。

<details><summary>Original English</summary>
So, some general features of good eval design. This is This is basics, this is nothing [clears throat] related to, you know, Anthropic, this is just kind of fundamentals, but it's good to revisit briefly.
</details>

你通常应该看到的是，这里有几条不同的曲线，基本上是以每次尝试的 token 数量为基准。这有点像 X 轴是 thinking，Y 轴是 score。

<details><summary>Original English</summary>
What you should see generally is that these are a number of different curves looking at basically tokens per attempt. This is kind of like thinking on the X and then score on the Y.
</details>

最上方是前沿模型，中间曲线是中型模型，底部是小型模型。所以可以将其想象成 Opus、Sonnet、Haiku。

<details><summary>Original English</summary>
Frontier model at the top, mid-size model on in the middle curve, small model at the bottom. So, think about that as like Opus, Sonnet, Haiku.
</details>

在你的 evaluation 上，你通常应该看到：当你提升模型级别时，性能随之上升。这是第一点。

<details><summary>Original English</summary>
You should generally see on your evaluation as you step up model and performance goes up. That's point one.
</details>

当你增加 thinking 时，性能应该上升。这是第二点。

<details><summary>Original English</summary>
As you increase thinking, performance should go up. That's point two.
</details>

在最前沿应该留有提升空间。这是第三点。所以基本上不应该处于饱和状态。

<details><summary>Original English</summary>
There should be headroom to improve at the frontier. So, that's point three. So, basically shouldn't be saturated.
</details>

而且运行与运行之间的方差应该很低。

<details><summary>Original English</summary>
And there should be low run-run variance.
</details>

非常简单的几点，但做好它们其实非常重要。事实上，即使我们看到的很多非常流行的 evaluation，也有很多模棱两可的任务，实际上限制了前沿的提升空间。

<details><summary>Original English</summary>
Very simple points, uh but actually very important to get right. And actually even a lot of very popular evaluations that we see have many tasks that are ambiguous, effectively limiting that headroom at the frontier.
</details>

这是我经常看到的一个问题。你构建了一个 evaluation，结果发现里面有一堆反正无法解决的模棱两可的案例。所以看起来，比如，“哦，在这个上面我还能再提升 20%”，但实际上没有任何模型能够做到。

<details><summary>Original English</summary>
And this is a problem I see all the time. You build an evaluation, it turns out you have a bunch of ambiguous cases that can't be solved anyway. So, it looks like, you know, oh, I've 20% more that I can get on this, but no model can actually achieve it.
</details>

所以，你可能会花费大量 token 在一个实际上已经饱和的 evaluation 上进行 hill climbing。做好这一点非常重要。

<details><summary>Original English</summary>
So, you could spend many tokens [clears throat] hill climbing on an evaluation that's effectively saturated. It's very important to get this right.
</details>

>> [sighs]

<details><summary>Original English</summary>
>> [sighs]
</details>

>> 试试这个命令：`Claude API build eval`。

<details><summary>Original English</summary>
>> Try this command. Uh Claude API build eval.
</details>

这实际上是一个非常好用的命令，因为它对你的数据存放在哪里完全没有任何预设偏好。它不在乎。你可以把它指向你现有的任何 tracing 解决方案。它只是 Claude Code 中的一个 skill。

<details><summary>Original English</summary>
This is actually a very nice command because it's not opinionated at all about where your data lives. It doesn't care. You can point this at whatever tracing solution you have. It's just a skill in Claude code.
</details>

它更多的是运用我刚才讲到的原则，来为你测试和健全性检查该 evaluation。

<details><summary>Original English</summary>
It's more employing the principles I talked about to test and sanity check the evaluation for you.
</details>

所以，你可以给这个 skill 提供类似这样的内容：“嘿，这是我想解决的问题，这是我感兴趣的内容，这是原始数据，例如，这是我想使用的 traces”，这个命令就能帮你构建一个 eval set。它会引导你走完一个流程，并一步步带你构建它。它会向你展示数据，向你展示 evaluation，还会跟你一起对 grader 和 criteria 进行健全性检查。因此，它会基于我们的一些最佳实践来引导你走完构建 eval 的过程，我们在这方面也有一篇很好的博文，我也会分享出来。

<details><summary>Original English</summary>
So, you can kind of give this skill, hey, here's a problem I want to solve, here's what I'm interested in, here is the raw data, for example, here's the traces that I want to work with, and this command can help you build an eval set. It'll walk you through a process and step you through building it. It'll it'll help you you'll show you the data, it'll show you the evaluation, it'll sanity it'll sanity check the grader the criteria with you. So, it'll kind of walk you through the process of building eval based upon some of our, you know, some of our best practice and we have a nice blog post on this as well that that I'll share.
</details>

而且它与 hill climbing 配合得非常好。所以，一旦你构建了一个良好的 evaluation——在最前沿有提升空间、方差低、按预期随 thinking 和模型规模扩展——你就可以在此基础上进行 climb。

<details><summary>Original English</summary>
Um and it pairs very well with hill climbing. So, once you've built a good evaluation that has headroom at the frontier, low variance, scales as expected with thinking and model, you can then climb on it.
</details>

前沿的 Claude 模型非常擅长 hill climbing。也就是说，自主地查看 evaluation，并在没有人类参与的情况下自主地在此基础上进行改进。所以，你构建了一个好的 eval，Claude 就能在上面进行 hill climb。

<details><summary>Original English</summary>
Frontier Claude models are very, very effective at hill climbing. So, autonomously looking at an evaluation and autonomously kind of improving on it without you in the loop. So, you build a good eval, Claude can hill climb on it.
</details>

问题在于，这可能会在很多方面出现偏差。尤其是，你最终可能会过拟合于 evaluation 本身。

<details><summary>Original English</summary>
The problem is there's many ways that this can kind of go wrong. And in particular, you can end up overfitting on the evaluation itself.
</details>

比如一些典型的例子：你的 benchmark 中的任务可能具有一些专属的或针对这些任务特有的需求。例如某个任务需要 OCR，于是用来解决该 eval 的测试 harness 碰巧添加了一个类似 OCR 的工具。但在生产环境中，你并不会遇到这些问题。所以你最终过拟合于 eval 的分布，而这并不适用于生产环境。这种情况非常普遍。

<details><summary>Original English</summary>
So like some classic examples would be um like the task in your benchmark have particular needs that are bespoke or specific to those tasks. Like maybe one task needs OCR, so it happens your harness to solve the eval adds like an OCR tool. But in production, you don't see that problems. So you end up overfitting on the eval distribution, it doesn't apply to production. This is very common.
</details>

是的，比如针对你的 eval 样本所特有的独特表述。

<details><summary>Original English</summary>
Um yeah, like distinctive phrasing specific to your eval examples.
</details>

再比如另一个典型情况是：当你在进行 hill climbing 时，prompt 过拟合于你的 eval 分布的特定细节，而不适用于你的测试分布。所以当你进行 hill climbing 时，过拟合是主要的挑战和担忧。试想一下，你花费了大量 token 在一个 evaluation 上进行 hill climbing。在 hill climbing 之后它看起来非常好。你把它运行在生产环境中，结果性能完全没有提升。这令人沮丧，因为你花了很多钱。你进行了 hill climb，结果却发现它不适用于生产环境，因为往往你只是过拟合于 eval 的分布。

<details><summary>Original English</summary>
For example, another classic is like it just kind of it like the prompt when you're basically hill climbing overfits the specifics of your eval distribution, it doesn't apply to to your to your test distribution. So overfitting is the major challenge concern when you're hill climbing. Imagine you spent a lot of tokens hill climbing an evaluation. It looks really good after hill climbing. You run it in production and performance is not better at all. That's frustrating because you spent a lot of money. You hill climbed and like, oh, it's not applicable to production because often you'll you've just kind of overfit to the eval distribution.
</details>

所以试试这个命令。在 Claude Code 中是 `Claude API hill climb`。

<details><summary>Original English</summary>
So try this command. In Claude code is Claude API hill climb.
</details>

如果你构建了一个 eval，它就会为你进行 hill climb。

<details><summary>Original English</summary>
So if you build an eval, it'll hill climb for you.
</details>

它尝试用几种技巧来应对这个问题。当然，它不是完美的。你必须仔细审计，并且确实需要人在回路中，确保你真正理解正在发生的事情。但它可以帮助你。

<details><summary>Original English</summary>
And it tries to combat this with a few tricks. Now it's of course not perfect. You have to audit this carefully and and and indeed be in the loop and and make sure you really understand what's happening. But it can help you.
</details>

具体来说，它执行的是这样一个流程：它会查看你的 evaluation，并将其拆分为测试集和训练集。这是统计学中非常经典的原则。创建一个测试和训练划分。

<details><summary>Original English</summary>
And in particular, what it does is a process like this. It will look at your evaluation and it will split it into test and train sets. This is kind of very classic um kind of classic principles from statistics. Create a test and train split.
</details>

顺便提一下，这只是在 Claude Code 上的操作，当进行 hill climbing 时发生的情况是这样的。Claude Code 基本上拥有这个 skill。你在一个 eval 上运行它。它在决定通过修改什么来提升 eval 表现时，只会查看训练集并反思那些失败案例。

<details><summary>Original English</summary>
What happens is when hill climbing, this is just on Claude code by the way. So Claude code basically has this skill. You run it on an eval. It will only ever look at the train split and reflect on those failures when it's making decisions about what to change to improve on the eval.
</details>

这样做的好处是，在每一轮中，它永远看不到测试集。而且它基本上会按轮次对照测试集和训练集来检查性能。所以，出现的情况就是一个用于发现过拟合的早期信号。如果你看到训练集在提升，但测试集持平，这就是一个信号：“噢，你可能发生过拟合了。”

<details><summary>Original English</summary>
So, what's nice about that is at every round, it never sees a test split. And it will basically check performance per round against test and train. So, what happens is a little it's a little early signal for overfitting. If you see train improving but test flat, it's a signal of "Ooh, you might be overfitting."
</details>

所以，基本上它会应用这种检查以及许多其他更细致的检查，以确保在进行 hill climbing 的同时，你不仅没有过拟合于你的 eval 分布，而且实际上是以一种适用于生产环境的方式在进行 hill climbing。前提是你把 eval 分布构建得很好，而这始终是我们在构建 eval 阶段可以解决的问题。

<details><summary>Original English</summary>
So, basically it applies this check and a number of other more subtle things check to make sure while hill climbing's happening, you aren't just overfitting to your eval distribution, you're actually hill climbing in a way that will apply to production. Assuming you built your eval distribution well, and that's always something that we can address in that build eval phase.
</details>

现在，我将分享一些我在这里用过的具体例子。这实际上就是 Claude API skill 本身。如果我稍微往回退一步，这是 Claude Code 中的一个 skill。它是一个让 Claude 完全了解我们 API 的 skill。基本上是我们的 SDK、API。并且它必须立足于我们的文档。

<details><summary>Original English</summary>
Now, I'll share some concrete examples that I've used here. So, this is actually the Claude API skill itself. So, if I back up a little bit, this is a skill in Claude code. And it is a skill that gives Claude full awareness of our APIs. Uh so, basically our SDKs, APIs. And it has to be grounded in our documentation.
</details>

因此，我基于我们的文档构建了一个 eval set。我对这个 skill 进行了测试。最初，该 skill 在我的集中的 eval 问题上表现不是很好，准确率为 66%。因此，我设置了一个 hill climbing 循环，让 Claude Code 能够访问 skill 文本和文档本身，并让它基本上通过迭代查看 eval set 中的失败案例，尝试弄清楚为什么该 skill 歪曲了文档中的内容。这里面有各种各样的小技巧，我可以更详细地谈谈。但重点是，在当前这个特定案例中，Claude 可以自主找到正确的 skill 文本，从而在 evaluation 上实现显著提升。我在下方的博客链接中也谈到了这一点。

<details><summary>Original English</summary>
So, I built an eval set based upon our documentation. And I tested the skill. The skill initially was not very good at the eval questions in my set, 66%. So, I set up a hill climbing loop with giving Claude code access to the skill text and the documentation itself, and let it basically just iteratively look at the failures in the eval set, and try to figure out why the skill was misrepresenting what's in the documentation. And there's all sorts of little tricks, and I could, you know, talk about that more in more detail. But the point is, Claude can autonomously find, in this particular case, the right skill text to improve significantly on the evaluation. And I talk about this in the blog link below.
</details>

不过再次强调，这是一个很好的例子，展示了定义良好范围的 evaluation、对 skill 进行修改的简单服务，以及一个自主的 hill climbing 循环——只要我像这样设置好系统，就带来了好得多的性能，

<details><summary>Original English</summary>
Um but again, this is a good example of a kind of a well-scoped evaluation, a simple service I'm modifying a skill, and an autonomous hill climbing loop that resulted in a much better performance just when I set the system up this
</details>

<!-- chunk 3/9 -->

这样一来，配合界定严密的评估（eval）以及易于修改的交互面，Claude 就能直接飞速迭代，显著提升性能。这在提示词（prompts）上很管用，在技能（skills）上也同样很管用。简单的纯文本交互面非常非常适合这种爬山（hill climbing）优化过程。

<details><summary>Original English</summary>
way with a carefully scoped eval, a surface that's easy to modify, claw can just rip through it and like significantly improve performance. This works well for prompts, it works well for skills. Simple text-based surfaces are very very good for this kind of hill climbing process.
</details>

现在，这是另一个很多客户都喜欢的有趣技巧。你也可以将爬山算法应用于降低成本。

<details><summary>Original English</summary>
Now, this is another kind of interesting trick that I've seen a lot of customers like. You can also apply hill climbing to cost reduction.
</details>

这当中挺不错的一点是，我给这个爬山命令加入了引导机制。如果你指示它去降低成本，它基本上会做的是尝试寻找一种配置，既能至少在性能上保持持平，又能确确实实降低成本。它会搜索诸如思考程度（effort）、模型选择以及你的提示词等维度。

<details><summary>Original English</summary>
So, what's kind of nice about this is I've added guidance to this hill climb command. If you tell it to reduce cost, what it'll do is it will basically try to find a configuration that's that is at is at least at parity in performance and for sure reduces cost. And it'll search things like effort, model, and your prompts.
</details>

这里有一个基于同一个客户支持基准测试的简单例子。我一开始使用的是 Opus 4.5 high 配备某个基准提示词。我基本上就告诉爬山器去降低成本。于是它的做法是，基本上去搜索模型与 effort 的组合，并挑选那些在多轮迭代中持续降低成本且不牺牲性能的组合。在这个案例中，它切换到了 Opus 4.5 low。我们看到性能有了大幅提升，成本也略微降低了。

<details><summary>Original English</summary>
Here's a simple example on that same um customer support benchmark. I start with Opus Opus 48 high with some baseline prompt. And I basically tell the hill climber reduce cost. So, what it does, it basically will search through model effort combinations and basically pick those that continuously reduces cost over the rounds without degrading performance. In this case, it moves to Opus 5 low. We see a big bump in performance and minor reduction in cost.
</details>

接着，爬山器自主尝试了 Haiku 4.5 low。我们看到性能又出现了一点点下降，但成本大幅削减。然后它决定去调优提示词，于是我们把性能拉了回来。所以，通过自主使用爬山器，我们基本上实现了 90% 的成本削减，同时性能还有了显著提升。

<details><summary>Original English</summary>
The hill climber then autonomously tries flying at 5 low. We see again degrades performance a bit, but big cost reduction. And then it it then decide tune the prompt and we kind of risk rescue the performance. So, we basically got a 90% reduction in cost with notable improvement in performance autonomously using the hill climber.
</details>

如果你手头有评估基准，这又是另一种非常棒的方式，你可以用爬山器直接要求：“行，在保持性能不变的前提下，通过调优 effort、模型选择以及我的提示词等项目，切实降低我的成本。”这是爬山器的另一个极佳用途。

<details><summary>Original English</summary>
This is another very nice way if you have an evaluation, you can use the hill climber to basically say, "Okay, keep performance fixed but reduce my cost materially by tuning things like effort, things like model selection, and my prompts." Another very nice use of the hill climber.
</details>

而且实际上，这套方法的妙处在于，哪怕你的评估基准已经饱和，你也能这么做。所以你大可以表示：“行吧，就算我的评估饱和了，无所谓，我不在乎性能了，我只想要降成本。”这样你就可以直接吩咐爬山器：“行，保持性能不变，全力把成本打下来。”它基本上就能去搜索各种配置，而且往往能发现一些非常有意思的规律。

<details><summary>Original English</summary>
And actually, what's nice about this is you can do this if you have a saturated eval. So, you can basically say, "Okay, say my eval saturated, fine. It doesn't matter. I'm not I don't care about performance. I just want to reduce cost." So, then you can just tell the hill climber, "Okay, keep performance fixed and just try to burn down cost." And it can basically search for configurations and often it'll find very interesting things.
</details>

比如在这个具体例子中，普遍存在一种直觉：采用更高的模型搭配较低的 effort，往往比使用较低的模型搭配高 effort 既更便宜、性能又更好。这就像是让一个更聪明的人来做，他可以不用那么费劲，就能达到更好的目标，或者说更有效地解决问题。于是最终它实际消耗的 token 更少，结果也就更便宜。这是我们屡见不鲜的一个大体直觉，而这已经内置到了这个爬山器技能中。所以，这是另一个不错的技巧。

<details><summary>Original English</summary>
Like in this particular case, there's generally an intuition that moving to higher models at lower effort is often cheaper and more performant than lower models at high effort. It's like giving someone who's smarter can like try less to actually get a better objective or or or to kind of solve the problem more effectively. Um and so it ends up actually using fewer tokens and as a result ends up being cheaper. That's kind of a broad intuition here that we've seen quite a bit. And that's baked into this hill climber skill. So, um another nice trick.
</details>

### 长时间运行 Agent 的架构考量

现在，我很快就会开放提问环节。在结束前我再提几点意见。这也算是呼应一下大家今天上午听到的关于 Magic Agent 的内容。我只是想再稍微着重强调一下。我确实认为，作为释放前沿模型潜能（unhobbling the frontier）的一部分，设计出能充分利用最新 Claude 模型能力的 Harness 至关重要。

<details><summary>Original English</summary>
Now, I'm going to open up the questions pretty soon. I'll just kind of close with some other comments. And this is a bit of a nod to the magic agent stuff you heard this morning. I just want to re-emphasize this a little bit. I do think um as part of unhobbling the frontier, it's very important to design harnesses that can take most advantage of the latest Claude models.
</details>

特别是，如果回顾过去的几年，情况非常有意思：横轴是时间，纵轴是人类完成任务所需的时长。你们都见过这类曲线，它们就是 METR 图表。回顾过去会发现很有趣，大家知道，Claude Opus 3 当时只能进行大约 4 分钟的自主工作。在那样的机制下，你能构建的产品非常有限，无非就是自动补全或者聊天。

<details><summary>Original English</summary>
And in particular, it's interesting if you look back the last few years, time is on the X, and this is task duration for human on the Y. You've seen these curves. They're just meter charts. It's interesting to think back, you know, Claude Opus 3 was capable of only like 4 minutes of autonomous work. And in that kind of regime, there were very limited products you could build. It's really auto completion or chat.
</details>

到了 2025 年，我们看到模型变得更强大了。它们能做数小时的工作，比如大约 1 到 2 个小时人类等效的工作量。显然在过去的 2025 年里，Claude Code 取得了显著的进展。而我们现在正进入一个全新的阶段，模型完成任务的时长正在超过一到两天。我认为这某种程度上已经超出了 METR 目前所能衡量的范围。

<details><summary>Original English</summary>
Now, we saw over the course of 2025, models become more capable. They can do like hours of work. Like maybe an hour to 2 hours of human equivalent work. Claude code obviously kind of um gained significant over the past over 2025. And we're kind of entering a new regime now where these um task durations for models are are exceeding like a day to 2 days. I think this is kind of outside the scope of what meter can even measure now.
</details>

但是在模型能完成相当于数天工作的这一机制下，你需要什么样的 Harness 呢？相关考量发生了很大变化，因为你希望模型能够非常长的时间里持续自主开展工作。那么，你该如何确保它们安全可靠？需要权衡的因素彻底变了。

<details><summary>Original English</summary>
But in this regime where you have models that can do the equivalent of like, say, days of work, what harnesses do you need? Like the considerations change quite a bit because you want models that can just do things autonomously over very, very long periods of time. Now, how do you make sure they're secure and reliable? The considerations change a lot.
</details>

我知道你们今天上午听说过这些，但其实这正是我们较新的一个名为 Claude Managed Agents 的 API 背后的出发点。我在 4 月份写过一篇关于此的技术博客，其核心原则就是将“大脑”与“双手”解耦。这里的理念非常简单：你有一个 Agent Harness，它实际上就是大脑；你还有双手，也就是沙箱，那是 Agent Harness 编写代码和执行操作的地方。

<details><summary>Original English</summary>
And I hear you heard about that morning, but this is actually the motivation behind one of our newer APIs called Cloud Manage Agents. Um and the principle here, I wrote this engine blog back in April on it, is decoupling the brain from the hands. And the idea is pretty simple here. You have an agent harness, which is effectively the brain. You have hands, which are sandboxes. That's where the agent harness writes code and performs actions.
</details>

而且你希望它们是相互独立的实体。特别是，你希望做到的是，即便 Harness 崩溃或者沙箱崩溃，系统也能够恢复过来。想象一下，你启动了一个 Agent 让它通宵运行，结果半夜沙箱崩溃了。这会让人非常抓狂，你会丢失状态、丢失会话日志，丢失一切。

<details><summary>Original English</summary>
And you want those to be separate things. In particular, you want that you want it to be the case that if the harness dies or the sand box dies, the system can recover. Imagine you have an agent that you spin up overnight to just run and the sandbox dies midway through the night. It's very frustrating. You lose state, you lose your session log, and everything.
</details>

因此我们在设计它时，是针对 Claude 会进行极长时间工作的场景来设计的，因而它是可恢复的。这意味着会话日志是一个独立的对象，独立于 Harness，独立于沙箱；它是仅限追加（append-only）的，并且是可恢复的。所以如果 Harness 崩溃或者沙箱崩溃，你随时可以根据会话日志来进行恢复。沙箱同样也是可恢复的，如果某个沙箱挂了，你可以重新启动一个新的；如果 Harness 挂了，你可以通过这个协调器（orchestrator）重新启动一个新的。

<details><summary>Original English</summary>
So when we design this, we designed this for a world where Cloud would be doing work for very, very long durations. And so it's recoverable. So that means the session log is an independent object separate from the harness, separate from the sandbox, that is append-only, that is recoverable. So if the harness dies, the sandbox dies, you can always recover from the session log. Sandboxes are also recoverable. So if a sandbox dies, you can boot up a new one. If the harness dies, you can boot up a new one through this orchestrator.
</details>

这里的另一点是安全性。Managed Agents 所做的一项重要工作，就是它绝不会直接将密钥权限开放给 Claude。密钥全部存放在保险库（vaults）中，这其实就存放在大家在顶部看到的那个工具箱里。保险库确保了 Claude 可以引用 API 密钥或机密，但实际上无法直接看到它们。因为很明显，如果你有一个要连续工作好几天的 Agent，直接赋予它访问高度敏感机密的权限是有点令人提心吊胆的。因此在我们构建 Managed Agents 时，确保安全性是一个极其重要的考量。

<details><summary>Original English</summary>
Another point here is safety. So one of the important things that Manage Agents does is it actually never gives Cloud direct access to secrets. Secrets are held in vaults. Um and that's actually stored in that kind of tools box you see at the top. So vaults ensure that Cloud can reference API keys or secrets, but it can't actually see them. Because obviously, if you have an agent that's working for, say, days on end, it's a little bit spooky to give it direct access to very kind of sensitive secrets. And so we ensure the security is is kind of very is is a very important consideration when we build Manage Agents.
</details>

因此，随着 Agent 能够持续运行数小时、数天乃至不久之后的数周，可靠性与安全性变得越发关键。今天上午大家可能已经对此有所了解，不过我和 CJ 最近发表了一篇很棒的博文，详细介绍了一个示例，基本上就是构建一个可以作为自动化 Agent 来定期更新上下文的实例。它可以调取你指定的不同数据源，也可以向 Slack 写入更新。这是一个非常简单的自动化示例，具有高度的可定制性，但它展示了所有这些不同原语是如何协同工作的。它整合了定时调度部署，全部运行在 Anthropic 的基础设施之上，安全地存储密钥，具备记忆能力，是一个非常棒的端到端范例。

<details><summary>Original English</summary>
So reliability and security become much more important as agents can operate for hours, days, and maybe soon weeks. And this morning you probably heard a little more about this, but we have a nice uh recent blog that I put out with CJ that walks through uh an example of basically building an agent that can serve as like kind of a an an agent automation uh for regular context updates. It can reach into different sources that you specify, it can write updates to Slack. Very simple automation example, it's highly customizable, but it shows how all these different primitives come together. It brings together a scheduled deployment, all this all runs on Anthropic infrastructure, it secure- it securely stores secrets, it has memory, and um it's a very nice kind of end-end example.
</details>

同样，最后一点是，你完全可以直接在 Claude Code 里面运行这个。运行 `Claude API magic sandboard`，然后把博文链接给它，它就会为你启动这份教程，把示例跑起来，你直接体验就可以了。

<details><summary>Original English</summary>
Now again, the final point is you can just run this in Cloud Code. So, run Cloud API magic sandboard and then give it the link to the blog, and it'll just boot up this tutorial for you, it'll spin up the example, and you can just play with it.
</details>

总而言之，这里的核心要点在于，你有多种方式来进行约束治理并确保前沿模型能够切实得到充分释放。审查你的提示词至关重要；确保高效利用提示词缓存（prompt cache）至关重要，特别是在构建长时间运行的 Agent 时，以此来确保成本处于可控范围；从可靠性与安全性的角度去考量专为长时间运行设计的 Harness 至关重要；同时，重视评估基准以及爬山算法也至关重要。

<details><summary>Original English</summary>
Um so, the really the key point here is um there's a number of ways you can kind of harness and uh make sure that Frontier is effectively unhobbled. Uh it is very important to audit your prompts. It's very important to make sure that you're effectively using prompt cache, especially building agents for long duration, to make sure that cost is managed. It's important to think about harnesses that are designed for long duration in terms of reliability and security. And it's also important to think about evaluations and hill climbing.
</details>

而当这些全部结合在一起时，你就可以拥有这样的 Agent：你可以交给他一项任务（例如一个评估基准），让它长时间运行并在该评估上进行爬山迭代优化，等你早上回来时，它已经取得了显著的改善。这确实是我现在看到的许多同事的工作方式，大家在评估上投入的时间多得多了……

<details><summary>Original English</summary>
And when this all comes together, you can have agents that you can give a task, for example, an evaluation, and let it run for long period of time and hill climb on that evaluation, come back, for example, in the morning, and it's it's significantly improved. And that's really the way that I see many of my colleagues working now. People are spending much more time on eval
</details>

<!-- chunk 4/9 -->

……设计，基本上就是明确指定 Claude 能够有效进行爬山算法优化的任务，并且以这样一种方式来做：智能体在执行此操作时高度安全，并且在长时间运行的任务中高度可靠。

<details><summary>Original English</summary>
design,

and basically just specifying tasks that

Claude can effectively hill climb on,

and doing this in a way such that agent is highly secure when doing this,

and is highly reliable for long duration jobs.
</details>

我们看一下时间到了哪里。说到这里，我想我就直接进入提问环节吧，因为不管怎样，有互动会更有趣。大家可以在这里的所有社交媒体上关注我。呃，感谢大家的时间和关注。

<details><summary>Original English</summary>
And let's see where we are on time. With that, I think I'll just take it to questions, because it's more fun when it's interactive anyway. You can follow me on all the the socials here.

And uh thank you for your time and attention.
</details>

>> [掌声]

<details><summary>Original English</summary>
>> [applause]
</details>

>> 好的，从那边开始。

<details><summary>Original English</summary>
>> Sure, start there.
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

### 评估设计与人工在环

>> 这是一个非常好的问题。问题是评估设计在多大程度上是可以自动化的？

<details><summary>Original English</summary>
>> This is a very good question. The question was how automatable is eval design?
</details>

其实我之前在 Twitter 上和 Hamel 有过一些交流。在评估方面他极其有见地。他对我们的 skill 提出的一些反馈是，它确实应该首先引导用户浏览数据，这一点我其实是赞同的。我会对该 skill 做一些小修改来实现这一点。

<details><summary>Original English</summary>
So actually I was engaging a bit with with Hamel on Twitter.

Extremely thoughtful with respect to evals. And some feedback he had on our skill was that it should indeed walk the user through the data first, which I actually agree with. I'll make it some minor modifications to the skill to do that.
</details>

所以，我认为，呃，评估设计——我还是回过头来说一下。在构建评估时，Claude 可以为你提供显著的协助。

<details><summary>Original English</summary>
So

I think that

uh eval design, I'll go kind of go back to it.

Claude can assist you when building evals significantly.
</details>

例如，在他演示中所给出的例子中，嗯，他在查看一个类似于客户支持应用之类的内容。第一个问题就像是，好的，这有一堆追踪记录（traces）。这里的失败案例有哪些？我到底应该把什么提升归入评估集？Claude 非常擅长识别出：“噢，好的，这里有个案例可能存在错误。”它实际上就像是在扮演一个在线评估者，但查看的是你的离线日志，扫描它们并说：“好的，这里有一些有问题的样本。”在那次示例中，Claude 非常擅长做这件事。

<details><summary>Original English</summary>
So for example, in the example he gave when his walk-through,

um he was looking at like a it was like a customer support app or something. And the first question was like, okay, like it's a bunch of traces. What are the failure cases here? What should I even like promote to an eval set? So Claude's really good at kind of identifying, ooh, okay, here's case where there might be errors. It's effectively like acting as like an online evaluator, but looking at your offline logs, scanning them saying, okay, here's some problematic examples. And Claude was very good at that in his example.
</details>

然后，如果 Claude 接着在查看器中把那些原始数据展示给你，这其实很重要而且相当有用。所以我打算把这个加到 skill 里面。我已经提了一个 PR，我会把它加进去。目前，Claude 是直接跳到分析数据，比如构建评估并展示给你。我确实认为有一个先查看数据的中间阶段是很重要且有帮助的。但我认为由 Claude 来标注数据，由 Claude 给你提供一些关于查看什么的思路，这是非常重要的。所以某种程度上像 Claude 辅助的评估和数据扫描，我认为是一个很好的结合。

<details><summary>Original English</summary>
Then it is actually important and quite useful if Claude then shows those raw like the raw data to you in a viewer. So I'm going to add that to the skill. I have a PR up and I'll add it.

Currently, Claude goes directly to analyzing the data and like building the eval and showing it to you. I do think it's important and helpful for there to be an intermediate stage where you look at the data first. But I think having data annotated by Claude where Claude's giving you some ideas about what to look at is very important. So kind of like Claude assisted evaluation and scanning of the data is like I think like I I think a nice marriage.
</details>

嗯，然后一旦完成了这步，你就可以把这类样本提升归入到你的评估集中。所以我认为人类在环在那里仍然有相当大的作用，但 Claude 可以提供相当多的协助。带有人类反馈的爬山算法。

<details><summary>Original English</summary>
Um and then once that's done, you can kind of promote like kind of examples to your eval set. So I think there is still quite a role um for the human in the loop there, but Claude can assist quite a bit. Hill climb with human feedback.
</details>

嗯，所以爬山算法只要求你拥有一个评估，并且拥有某种信号，让 Claude 可以用它来判断好与坏。因此，如果你获取了人类反馈并将其融入到了评估信号中，例如那样的话，那么以这种方式在评估结构上进行爬山算法就应该是完全可行的。

<details><summary>Original English</summary>
Um

so hill climbing only requires that you have an eval and you have some signal that Claude can use to judge good versus bad.

So if you've taken human feedback and you've rolled that into an eval signal, for example, then it should be perfectly feasible to hill climb on an evaluation structure that way.
</details>

### 爬山优化的切入层面与提示词过拟合

是的，这是一个好问题。那么，对于爬山算法来说，最适合作为起点的操作层面（surface）是什么？我这里基本上把它列为我们要编辑的对象。是的，所以我实际上在这个方面做过相当多的尝试。

<details><summary>Original English</summary>
Yeah, this is a good one.

So, for hill climbing, what's like the best surface to start with? So, I kind of have that here as like the thing we edit. Yeah, so so I've actually played with this quite a bit.
</details>

文本挺好的，尤其是像 prompt 和 skill 这类东西非常不错，因为这是一个非常——它是一个非常明确的地方，我们知道它会显著改变和影响模型行为。所以，它是一个修改起来非常受限的层面，而且我们知道它与输出是高度耦合的，通常就你正在评估的内容而言是如此。

<details><summary>Original English</summary>
Text is nice, in particular if things like prompts and skills are very nice because it's a very

it is a very clear place that we know sign that we know significantly alters and affects model behavior.

So, it's like a very constrained surface to modify, and we know it's highly coupled to the output, typically in terms of like what you're evaluating.
</details>

呃，比如这里有一个很好的例子。嗯，比如当我在进行 skill 的爬山优化时，我测试的是直接从该 skill 中读取内容的东西，所以我知道存在明确的耦合。现在，我要把它与我也做过的智能体测试框架（agent harnesses）的爬山优化作个对比。

<details><summary>Original English</summary>
Uh like here's a good example. Um like when I'm doing skill hill climbing, I'm testing something that is directly reading from the skill, so I know there's clear coupling. Now, I'm going to contrast that to I've also done hill climbing with agent harnesses.
</details>

但那里发生的情况是，它可能会稍微更难解释。你在修改框架代码，所以每一轮的改动都是大得多的 diff。而且，嗯，只会有更多容易引起混淆的暴露面。你所做的更改实际上可能与你正在测量的输出信号脱钩。所以，这当然是可能的，而且确实有人在智能体测试框架的爬山优化上做了相当多的工作。我只是觉得它稍微更棘手一些，而基于文本的层面往往是一个很好的起点——prompt、skill，嗯，因为它们与模型行为的耦合如此明确，而且很容易修改。实际上的隐患在于，像 prompt 这类东西非常容易过拟合。在我的许多爬山优化尝试中我也见识过这一点。所以，像——我不知道我是否有好的图示，但是……

<details><summary>Original English</summary>
But, what happens there is it can be a bit more hard to interpret. So, you're modifying the harness code, and so the the the the changes per round are much larger diffs. And um there's just more surface area for confusion. You can be making changes that are actually decoupled from the output signal you're measuring. So, it's certainly possible, and indeed people have done quite a bit of work hill climbing on agent harnesses. I just think it's a little bit trickier, and text-based services are often a good starting point, prompts, skills, um because they're so clearly coupled to model behavior, and they're easy to modify. The catch actually is that is that things like prompts are very easy to overfit. I've seen that in in many of my uh hill climbing efforts as well. So, like um I don't know if I have a good diagram, but
</details>

你知道，你面对着正在其上进行爬山优化的某种评估分布，即使采取了这些正则化措施，比如评估集、测试集、训练集的划分等等。嗯，prompt 非常容易被随意调整，Claude 非常擅长将 prompt 调整成在你的评估中表现良好、但并不能真正代表生产环境中情况的形态。所以对于 prompt 你必须非常小心，但它们确实非常容易修改。因此，这是一个很好的起点，你确实需要对过拟合保持谨慎。

<details><summary>Original English</summary>
um

you know, you have some eval distribution you're hill climbing on, even with these regularizations in place, like you you the eval test train split and so forth. Um prompts are very easy to like wiggle Cloud's very good at wiggling the prompt into a shape that does well in your eval that isn't really representative of what's in production.

So, you have to be very careful with prompts, but they are very easy to to modify. So, it's a good starting point, you do need to be careful with overfitting.
</details>

### 从 Prompt 到 Skill 的转化

呃，让我想想。把 prompt 变成 skill。所以，它们有点算是互补……比如，呃，你的意思也许是如果你正在走某些标准作业程序，什么时候将其提升为一个 skill 吗？好的，是的。

<details><summary>Original English</summary>
Uh let's see. Turning a prompt into a skill. So, they're kind of compliment like um maybe do you mean if you if you're like going through some standard operating procedure, when to like promote that to a skill? Okay, yeah.
</details>

嗯，那其实挺有意思的。我认为通常我和 Claude 都相当擅长对此做出判断。所以，基本上你可以走一遍工作流程，然后你可以要求 Claude：“好的，把它变成一个 skill。”我一直都在这么做。所以，Claude 相当擅长捕捉到：“好的，你正在做某件重复性的事情，把它做成一个 skill 吧。”

<details><summary>Original English</summary>
Um that's actually kind of interesting. I think often I and Claude is quite good at judging that. So, basically you can basically go through a workflow and then you can ask Claude, okay, turn that into a skill. I do that all the time. So, Claude is pretty good at like catching, okay, you're doing some repetitive thing, make it a skill.
</details>

呃，我其实觉得你应该直接让 Claude 去做这件事。嗯，直接告诉它：“把这个变成一个 skill”，它就会去做的。所以在评估的情况下，通常设置会是这样：我有一个已经定义好的现有 skill，可能它带有一些模版化的起始文本，然后我会说：“好的，我希望你改进这个 skill。我希望改进这个 skill 文本，以使其基本上在这个评估上有更好的表现。”所以，这通常是我设置它的方式。比如我拿一个 skill 模版作为起点。我知道我希望这件东西成为一个 skill。就像在这个案例中，对吧？就像我有这个针对 Claude API 的 skill。它是——基本上你可以想象它基本上就是我们文档的精炼提炼。就像是“如果你想了解这个，请访问此页面；如果你想了解这个，请访问此页面”。嗯，它有一堆小坑和问题，所以刚开始时我的评估表现相当低。但我有了一个起点，而那正是 Claude 随后能够进行修改的基础。所以我认为对于 skill，通常都是以某种基线作为起点的。

<details><summary>Original English</summary>
Uh I actually think you should just have Claude do that. Um just tell it, turn this into a skill, and it'll do it. So, usually in the in the case of evals, the setup will be

I'll have an existing skill that I've kind of defined and maybe it has some boilerplate starting text and I'll say, okay, I want you to make this skill improved. I want to improve this skill text to basically perform better on this eval. So, that's usually the way I set it up. Like I have a skill boilerplate as a starting point. I know I want this thing to be a skill. Like in this in this case, right? Like I had this skill for the Claude API. So, and it was basically you can imagine it's basically distillation of our docs. It's like go to this page if you want to learn about this, go to this page you want to learn about this. Um it had a bunch of little gotchas and issues, and so my eval performance was pretty low to start. But I had a starting point, and that's what Claude was able to then modify. So, I think usually with skills you're kind of starting with some baseline.
</details>

它可以是一个非常粗糙的默认内容，但随后要给 Claude 提供一个像这样据以开始的东西。这通常是我会采取的做法。

<details><summary>Original English</summary>
And it could be like a very crude default, but then give Claude something to like start from. That's usually the way I would do it.
</details>

### 开放性标准的验证策略

好的。所以在，嗯，具有某种开放性标准的领域中的验证。所以，比如，是的，我认为一般来说启发式评估器当然是更可取的。因此，如果你能够定义一个确定性的好坏检查，那显然更可取。所以在迷宫中那是行不通的。那么我发现的是，嗯，能产生相似打分的结构良好的评分标准（rubrics）。所以，好的，有几个不同的方面。

<details><summary>Original English</summary>
Right. So,

verification

in um

domains that that have kind of open-ended criteria. So, like yeah, I think in general heuristic evaluators are preferable, of course. So, if you can have define like a a a deterministic check for good or bad, that's obviously preferable. So, in the maze that doesn't work. So, what I found is um well-structured rubrics that produce similar uh grades. So, okay, a few different things.
</details>

首先，构建一个你作为人类能够去推理思考的评分标准。

<details><summary>Original English</summary>
Build a rubric that you as a human can reason about first.
</details>

所以，这就像——假设我们正在给一段文本打分。这是好的还是坏的？构建一个像我作为人类能够去查看一段文本并说出“好的，我能给它打分”的评分标准。这是第一点。

<details><summary>Original English</summary>
So, it's like

let's say we're grading a piece of like text. Is this good or bad?

Build a rubric that like I could look at as a human to like look at some text and say, "Okay, I can grade that." That's point one.
</details>

第二点，不要使用随意的量表。我一直看到这种情况，比如“按零到五分打分”。这非常模棱两可。要让它清晰明了且简单，比如理想情况下是一个好与坏的二元分类。如果你想评估多项内容，你可以设置多个二元分类器；最糟糕的做法莫过于给 Claude 一个“在 1 到 10 之间对此进行评分”。那是极其嘈杂（noisy）的。

<details><summary>Original English</summary>
Point two, don't use arbitrary scales. I see this all the time like grade it from zero to five. It's very ambiguous. Make it crisp and simple like ideally a binary classification good versus bad. You if you want to evaluate multiple things, you can set up like multiple binary classifiers rather than the worst thing is give Claude like

from one to 10 rate this. That's extremely noisy.
</details>

另一项健全性检查是跨不同模型进行测试。让 Sonnet、Opus 和 Fable 都使用你的评分标准来打分。如果它们全都意见不一，那就是个不好的迹象。

<details><summary>Original English</summary>
Another sanity check, test across different models. Have Sonnet, Opus, and Fable all grade using your rubric. If they all disagree, that's like a bad sign.
</details>

另一项测试是运行重复实验（replicates）。所以基本上，嗯，就像我在这里展示的你如何希望得到低方差一样，用你的评分标准运行重复实验，并确保它收敛紧凑。所以如果你把所有这些事情都做了，你绝对可以让它在——嗯，是的，比如对于那些难以捉摸（squishy）的基于文本的回答——很好地发挥作用。比如并没有非常明确的途径去……

<details><summary>Original English</summary>
Another test, run replicates. So, basically um like I show here how you want low variance, run replicates with your rubric and make sure it's tight. So, if you do all those things, you can definitely make it work pretty well

um for yeah, like text-based answers that are squishy. Like there is no very definitive like way to
</details>

<!-- chunk 5/9 -->

启发式地去检查那个。但配有一套结构良好的评分准则（rubric）的 LLM 作为裁判（LLM as judge），其实可以相当有效。对，这其实是个很好的点。所以，其实我——我本该提到这一点的。

<details><summary>Original English</summary>heuristically check that. Uh but LLM as judge with a good well-structured rubric can be quite effective. Yeah, that's actually a good one. So, actually I I I I should have mentioned that.</details>

成对比较（pairwise comparisons）其实可以非常不错。对人类、甚至对模型来说，去对比两个生成物（artifacts），往往要比单独给一个生成物打分容易得多。比如你通常可以回答：“哦，比起这个网页，我更喜欢另一个。”而要回答“我确信这个网页——给它打个 0 到 5 之间的分”，这就难多了。因此成对比较相当有效，而且实际上我认为这是个不错的——如果你的问题允许这么做的话，这确实是处理那些更为模棱两可的评分的一种有效方式。

<details><summary>Original English</summary>Uh pairwise comparisons can actually be quite good. It's much easier for humans even models to kind of compare two artifacts than it is to grade an artifact. Like you can typically answer, "Oh, I like this webpage better than this one." versus "I'm sure this webpage grade it between zero and five." It's much harder. So, pairwise comparisons are pretty effective and actually I think that is a good that is a good way uh if if your problem allows for that, that actually can be a effective way to deal with um more ambiguous gradings.</details>

嗯，我认为这有点回到仔细观察数据这一点上。有点联系到那边提出的问题。

<details><summary>Original English</summary>Well, I think it goes a bit back to just looking at the data carefully. Kind of relate to the question asked over here.</details>

### 评估集的分布与对抗性采样

我说分布的时候，更多是指确保你为评估集采样了一定数量的用例，并且确保这些用例能够代表你在生产环境中真正关心的东西。这才是所谓的分布的真正含义。

<details><summary>Original English</summary>Um when I say the distribution, um I more mean ensuring that um you've sampled some set of cases for your eval set. And making sure those cases represent what you actually care about in production. That's really what I mean by distribution.</details>

所以这里有一些有趣的技巧。比如会发生的一个问题是对抗性采样（adversarial sampling），也就是你选择——这可能有点容易让人混淆，但我尽量解释清楚。你选择的用例是来自某个特定模型类别的特定失败案例。模型的能力是不均衡的（jagged）。所以你只盯着说：好，比如 Sonnet 5 搞不定这些例子，我就把它们提到我的评估集里。而 Opus 5 说不定全都能解决，就因为机器智能是不均衡的。所以某一个模型表现凹陷的一个特定领域，可能换另一个模型直接就解决了。

<details><summary>Original English</summary>And so, there are some interesting tricks here. Like one problem that happens is adversarial sampling, where you select like this is maybe a little bit confusing, but I'll try to explain it clearly. You select cases that are specific failures from a from a particular model class. So, models are jagged. And so, you just look at, okay, like Sonnet 5 can't do these examples. I promote them to my eval. Opus 5 may maybe it'll solve them all just because intelligence is jagged. And so, like a particular pocket of one model might just get solved by another.</details>

因此通常一个好的建议是：从第一性原理出发、凭你自己的直觉、通过观察生产数据，把那些困难或有趣的用例提升到评估集中，而不一定完全从任何给定模型的失败案例中去抽样。因为那样可能会导致产生这种奇怪的分布，它完全是契合某一个具体的不均衡模型的智能低谷而形成的，当你升级模型时就不适用了。

<details><summary>Original English</summary>So, typically, a good recommendation is promote eval cases promote cases in eval set that are hard or interesting from first principles, from your own intuition, from looking at production data, not necessarily completely sampled from the failures of any given model. Cuz that can result in kind of this odd distribution that's shaped to the valleys of one particular like jagged model's intelligence that don't apply when you upgrade models.</details>

### 分级评估还是二元分类

那么，你能使用基于分桶（bucket-based）的评估，还是必须用二元分类（binary classification）呢？我这里说得有点过于硬性规定了。你显然可以这么做，但作为一条通用规则，我看到人们在这个方向上走得太远了。会出现某些在 0 到 10 之间非常随意的评分尺度，带着模糊不清的评分规则，连非常小的模型都无法判别。

<details><summary>Original English</summary>So, like can you use bucket-based evals or do you have to use binary classification? I'm being a little bit overly prescriptive. You obviously can, but just as a general rule, I see people going too far in that direction. So, there'll be some very arbitrary scale between 0 and 10 with unclear grading and rules that even a very small model can't resolve.</details>

所以你显然——如果你有一套深思熟虑的量表，只要它满足我们刚才谈到的条件，你显然可以这么做。比如它方差低、能在不同模型之间复现、人类评分者能够区分这两个等级，那就完全没有问题。我只是说，二元化就像是一种快捷方式，通常用来简化问题。而且在评分方面，你通常希望使用更小、更便宜的模型。你肯定不希望让 Fable 来做评分，这也取决于你的成本敏感度。所以，这些只是一些建议。但显然如果它是经过深思熟虑的，那完全没问题，你可以考虑使用多分类。

<details><summary>Original English</summary>So, you obviously, if you have a well thought through scale, you obviously can do that as long as it satisfies we talked about. It has like low variance, it's reproduced across models, a human grader can kind of distinguish between these two grades, that's totally fine. I'm just saying binary is like a shortcut of like if to simplify the problem, usually. And also for grading, you often want to use smaller, cheaper models. So, you really don't want Fable doing your grading and depending on your cost sensitivity. So, um, those are just the recommendations. But obviously, if it's well thought out, that's totally fine. You can think about using, um, yeah, like a multi uh, like a multi multi-category classification.</details>

### 针对什么场景构建评估

是的，这是个好问题。比如什么时候针对什么类型的问题来构建评估。比如：为我个人的那些用例构建评估值得吗，还是说我们只对生产级别的事情做评估？

<details><summary>Original English</summary>Yeah, that's a good point. Like when when to build evals for what types of problems. Like, is it worth building it for my like personal like use cases or we only doing it for things that are kind of production grade?</details>

我认为这取决于——让我想想。这大概有点取决于任务的重要性。所以哪怕它是一项个人任务，只要你觉得它相当重要，那么为它需要评估就是完全合理的。我觉得那完全没问题，我想有人就是这么做的。这因人而异。我个人并不一定为我个人的自动化任务构建很多个人评估，但我认为如果那是一项高度重要的任务……

<details><summary>Original English</summary>Um I think it depends on um I let's see. It probably depends a bit on the importance of the task. So, if it's even it's a personal task, you feel that it's quite important, then it would be perfectly reasonable to need eval for it. I think that's totally fine. I think people do that. Kind of varies by person. I personally haven't necessarily built many personal evals for like my personal automations, but um I think if it's a task that's highly important, it's</details>

特别是——好的，我举一个很好的例子。比如假设有人在金融行业工作，你把你个人工作流中的某些部分自动化了，但质量极其重要。比如这是要对外分享的工作产出之类的，那就绝对需要评估。尽管这是你自己个人构建的东西。如果它只是我的个人助手，比如，你知道的，就像个会议——像一个我做来帮我管理日程表的应用，我可能会建评估，也可能不建。这取决于具体背景。但我确实认为，显然如果这是对你的工作很重要的东西，比如在生成要对外展示的交付物，或者在执行某项非常敏感的任务，你显然需要评估。即使它只是一个个人 Agent。

<details><summary>Original English</summary>in particular um I okay, I'll give a good example. Like if say people work in finance and like you've automated parts of your your personal workflow, but quality is extremely important. Like, this is a work output that's going to share externally or something, that would absolutely need evals. Even though it's something you've built personally. Um if it's my personal assistant, that's like, you know, it's like a a meeting it's like an app that I built to help me manage my calendar. Uh I may or may not build evals. It depends upon the context. But I do think obviously if it's something that's important for your work, it's like, you know, producing deliverables that are, you know, externally viewed or doing something very sensitive task, you obviously want evals. Even if it's a personal agent.</details>

### 可观测性与爬山算法收敛性

在来 Anthropic 之前我其实在 LangChain 工作过，但我不能为其中任何一个站台。

<details><summary>Original English</summary>I actually worked at LangChain before Anthropic, but I I I I can't advocate for any one or the other.</details>

对，关于那个我保持沉默。我的意思是，听着，我都用过很多。我认为实际上如果你是在相对较小的规模下工作，你显然可以自己手搓一个。你并不一定需要一个花哨的可观测性系统。事实上，我们打算给这个 skill 增加能够……增加一个简单的数据查看器，或者说我们其实正在向这个 skill 添加这个能力。所以 Claude 能够——Claude 非常擅长为你构建界面和可视化看板。所以如果针对你想要查看数据的非常定制化的问题，它可以很轻松地为你搓出任何你想要的应用程序。而且成本也不高。

<details><summary>Original English</summary>Um Yeah, I I I plead the fifth on that. Um I mean, look, I've I've used many of them. Um I think actually if you're if you're working at relatively small scale, you obviously could roll your own. Like, you don't necessarily need a fancy observability system. In fact, we're going to be adding to the skill the ability to to um to to uh just like a simple data viewer or we're actually adding to the skill. So, Claude can kind of Claude's very good at kind of building you UIs and visualization surfaces. So, they can kind of roll If you have like a very bespoke problem you want to look at the data for, it can kind of roll you whatever app you want very easily. And and not very expensively, either.</details>

不，这是个关键点。它根本不能保证收敛。我见过很多爬山算法（hill climber）卡住的情况。实际上我们构建了——你可以去看博客，但我们在爬山算法里做了一个后备机制（fallback）：如果它连续多轮卡住，它实际上会去尝试对剩下的失败用例进行聚类，并且去查找。

<details><summary>Original English</summary>No, this is a key point. It's not guaranteed to converge at all. So, I've seen many cases in which the hill climber gets stuck. And actually, we built You can read the blog, but we built a fallback in the hill climber where if it gets stuck for multiple rounds, it'll actually go and basically try to cluster the the remaining failure cases, and it'll try to look for.</details>

例如，问题常常在于：很多时候你运行爬山算法时，并没有先运行像 build eval 这样的命令，或者没有构建起一个非常精心设计的评估集。所以爬山算法就会去看你的评估集，尝试找出这些用例是否存在我们刚才谈到的模糊不清的问题。也许最后那 20% 全都是评分器有误的例子或者模糊不清的指令。这种情况一直都在发生，非常普遍。所以爬山算法之所以卡住，并不是因为 Claude 无法做得更好，而是因为评估集的结构设计得很差。因此爬山算法 skill 会尝试帮你把这些找出来。

<details><summary>Original English</summary>So, for example, here's the problem. Oftentimes, you'll run the hill climber without having run like a build eval command or with without having built a very like carefully constructed eval set. So, the hill climber will go and look at your evals and try to find are these cases ambiguous like we talked about here. Maybe that last 20% are all faulty grader examples, ambiguous ambiguous instructions. This happens all the time. This is like very common. So, climber is just stuck not because Claude can't do better, it's because the eval is poorly structured. So, the hill climbing skill will try to find that for you.</details>

所以我们加上了那个功能。事实上，当我做我在这里提到的这次爬山优化时，这第二阶段实际上遇到了卡住的情况，于是它就去把那些评估用例进行了聚类，并分析：“好，为什么会有这些失败用例？它们为什么失败？到底是怎么回事？”它发现了一堆模糊不清的用例，并将它们重写了。总之它实际上会为你做这些事，但那种卡住的情况一直都在发生，绝对不保证能够收敛。通常那都是由于你评估集里的缺陷，或者是评估集里某种配置不当造成的。

<details><summary>Original English</summary>Uh so, we added that. In fact, when I did this hill climbing I talked about here, um this second stage actually went it kind of got stuck, and it went and basically clustered the eval cases and looked at, "Okay, why the failure cases? Why are they failing? What's going on?" It found a bunch of ambiguous cases. It rewrote them. And And anyway, so it'll actually do that for you, but that happens all the time. It's absolutely not guaranteed to converge. And usually it's because of failures in your eval or like kind of misconfigurations in eval.</details>

### 与 DSPy 的兼容性及 Effort 调节

所以那真的很有意思。我对 DSPy 团队、Omar 以及各位同仁非常尊敬。这实际上只是内置在 Claude Code 里的一个 skill。这个 skill 本身也是开源的。所以你可以考虑把这个 skill 引入并植入到任何其他环境里。看看你是否想——它可能可以与 DSPy 一起使用。它只是一些非常简单通用的指令，用于按照这些原则建立一个爬山循环。

<details><summary>Original English</summary>Uh so, that that's really interesting. I You have a lot of respect for the DSPy team and and Omar and and and and and um and colleagues. Uh this this actually just is a skill built like bundled with Claude code. The skill is also open source. So, you could consider taking that skill and and like vendoring it in any other surface. See if you want to could probably work with DSPy. It's just some very simple general instructions for setting up a hill climbing loop following basically these principles.</details>

所以，它可能可以与 DSPy 兼容。[清了清嗓子] 我没有用过 DSPy，所以我不知道具体的细节和它的结构是怎样的，但这套 skill 的指导原则完全有可能与它兼容。如果你想在 DSPy 中有效地实现或运行这个，那个 skill 是开源的。

<details><summary>Original English</summary>Um so, um that [clears throat] it could be compatible with DSPy. I haven't used DSPy, so I don't know like the details and how it's structured, but um it's possible this skill guidance here could be compatible with it. If you want to like effectively implement this or run it in DSPy, the skill is open source.</details>

你提到了选择 effort 级别（努力程度 / 思考预算）。是的，这是个经典问题。effort 让人很困惑，对吧？是的，我对 effort 也很困惑。确实，这很不直观。

<details><summary>Original English</summary>Uh you said choosing effort level. Yeah, this is a classic one. Effort's confusing, isn't it? Yeah. I'm also confused by effort. It's Yeah. It it is it's non-obvious.</details>

所以，这里好的一点是，如果你有一套评估，爬山算法绝对可以尝试为你配置 effort。现在我明白，拥有一套评估并不是那么容易的事，所以它并不适用于每一个问题；但如果你碰巧有一套评估，那么这个爬山算法就能去搜索你的模型……

<details><summary>Original English</summary>Um so um this is a so what's nice is if you have an eval uh the hill climber can absolutely try to configure effort for you. Now, I get it. It's like not that easy to have an eval. So, like it's not a it's not applicable to every problem, but if you happen to have an eval then this hill climber can search through your model</details>

<!-- chunk 6/9 -->

### 模型与努力程度（Effort）的权衡

努力程度配置遵循一个非常简单的原则。这个原则简单来说就是，通常较强的模型在较低的努力程度下，呃，抱歉，是更加节省 token，因此比高努力程度下的较弱模型更便宜。这算是一个通用原则。这在很多情况下确实是成立的。因此，它会先在低努力程度下遍历搜索不同的模型，基本上会持续搜索，直到你看到性能下降到基准线以下。所以，这里我没有展示出来，但是比如我尝试 Haiku 的时候，当时是 4.5。现在我们有了 5.5 版的 Haiku，要好得多。呃，4.5 在低努力程度下出现了明显的退化，所以我们去掉了那个数据点。但基本上，如果你有一个 eval，爬山算法是寻找良好模型与努力程度组合的一个非常好的方法。

<details><summary>Original English</summary>
effort configurations and it follows a very simple principle. The principle is just simply that typically the stronger model at lower effort is is like more effective uh or it sorry is more token efficient and therefore cheaper than like a weaker model at high effort. That's like the general principle. That actually turns out to be true a lot. So, it'll kind of search through the different models at low effort first and basically continue that search until you see a degradation performance below the baseline. So, for here I don't show it, but like when I tried Haiku for this was 4.5. Haiku we now have 5.5, which is quite a bit better. Uh 4.5 at low effort was a significant regression, so we admitted that that data point. But basically if you have an eval hill climbing is a very good way to try search for a good model effort combination.
</details>

如果你没有 eval，关于努力程度更通用的指导显然会棘手且微妙，我想大家通常……我想说的是，关于努力程度，我通常推荐的指导是一般尝试较强模型配低努力程度。Opus 5.5 低努力程度。基本上先试试这个。呃，较好的模型在低努力程度下通常更加节省 token，因此比高努力程度下的较弱模型更便宜。这就是我想留给各位的关键要点。

<details><summary>Original English</summary>
More general effort guidance if you don't have an eval is obviously tricky and subtle and like I think um people typically um I I will say the guidance I recommend generally on effort is try stronger model low effort in general. Opus 5.5 low effort. Try that. Basically. Uh better models low effort are often more token efficient and therefore cheaper than than weaker models at high effort. That's like the key point I'll I'll leave you with.
</details>

>> 所以，不用中等努力程度（medium）吗？

<details><summary>Original English</summary>
>> So, not medium?
</details>

>> 呃，一开始先试低努力程度。嗯，你随时可以再往上调。但基本上，我喜欢非常聪明的模型不要太费劲去思考。这通常是……对于性价比来说这往往是个最佳平衡点。显然你可以调高努力程度，但我认为反面情况是人们通常一开始就用类似最大努力程度（max effort）。这极其消耗 token，非常贪吃 token。所以，通常先从更聪明的模型配低努力程度开始，如果需要的话再以此为基础逐步调整，这其实是明智的。是的，实际上我们在博客里谈到过这点。我本来想打开看看的。我没连网。那没关系，那我就直接讲吧。

<details><summary>Original English</summary>
>> Uh try low to start. Um you can always dial back up. But basically I like very smart model not trying too hard. That's a very that's often a sweet spot for for um kind of kind of cost performance. Obviously, you can dial up effort, but I think the the counter is people often start with something like max effort. This extremely token and like token hungry. So, it is actually wise often start like small smarter model low effort and kind of kind of go from there if you need it. Yeah, actually, we talked about this in the blog here. I was open that up. I don't have internet. That's fine. I'll just tell you then.
</details>

是的，所以它基本上就是在告诉 Claude 要花多大心思去思考。低努力程度就是说“不用思考得太费劲”，随着你调高，它就是在说“再多想想”。所以，这也是为什么更根本上具有高智能的模型在低努力程度下，实际上可以比高努力程度下基础 token 费用更便宜的模型更加节省 token，因为那样的话，比如说 Sonnet 5 在高努力程度下会花大量的 token 在思考上，而更聪明的模型在低努力程度下能在更高的基础智力水平上花更少的 token 去思考。这就是直觉所在。

<details><summary>Original English</summary>
Yeah, so it's basically telling Claude how hard to think. So, low effort saying like don't think as hard as you scale it up it's saying think harder. So, and that's kind of why more fundamentally intelligent model at low effort can actually be more token efficient and therefore cheaper than a cheaper model in terms of base tokens at high effort cuz that that for example, Sonic 5 at high effort is spending lots and lots of tokens thinking where smarter model low effort will spend fewer tokens thinking at a higher baseline of intelligence. That's kind of the intuition.
</details>

### 爬山算法中的预算与评测设计

是的，这个问题是关于在爬山算法中设置预算。基本上当你运行这个 skill 并进行设置时，它会询问你的预算。所以，嗯，它会为你管理好这一点。它会跟踪你为这一轮爬山算法分配的预算。

<details><summary>Original English</summary>
Yeah, so the question is about setting budgets in hill climbing. So, basically when you when you run this skill and set this up, it'll ask you for a budget. So, um it will manage that for you. It'll track the budget you allocate for the hill climbing round.
</details>

不过那种情况确实可能发生。这也正是为什么这是一个经典例子。这就是为什么设计一个好的评测（evaluation）非常重要。如果你有一个设定不明确的评测，想象一下比如你有一个 eval，其中最后 20% 是不可能做到的。你就会为了尝试解决那最后的、你知道的、实际上根本无法解决的 20% 的问题，而烧掉大量的 token。

<details><summary>Original English</summary>
That can definitely happen though. And that's actually why this is a classic example. That's why designing a good evaluation is really important. If you have if you have a poorly specified evaluation, imagine for example, you have an eval where that final 20% is impossible. You burn a huge number of tokens trying to solve those final you know, 20% of problems that are effectively not solvable.
</details>

### 人机协同构建 Eval

在 eval 构建方面，这个问题是关于人机协同，人与 Claude 的合作。所以，我认为人类仍然承担着把控目标的角色。比如我们到底在试图评估什么，为什么它很重要？所以品味（taste）很重要。比如你真正想看到回答的是什么？举个例子，我拿 Hamel 对我们构建 eval skill 的公开内部试用（dogfooding）来举例。比如，好，这是一个客户支持应用。假设这就是你的应用。什么才是关键？什么是重要的？你关心什么？这些是人类可以引导 Claude 的事情。现在，一旦这些事情被明确规范，Claude 嗯，就可以查看原始追踪记录（traces）并有效地判断：好，这个应用可能在哪些地方没有达到我的目标？所以我认为这是一种可以在实际中采用的不错的人机合作方式。

<details><summary>Original English</summary>
Kind of an eval building, the question is about kind of human loop kind of human Claude collaboration. So, I think I think that um humans still have the role to kind of steer the goal. Like what are we actually trying to evaluate and why is it important? So, it's kind of taste is important. So, like what are you actually trying to see answer? For example, I'll give you I'll take an example from like Hamel's public kind of ant or a public dog fooding of our um build eval skill. So, it's like okay, it's a customer support app. So, let's say that's your application. What matters? What's important? What do you care about? Those are things that a human can guide Claude. Now, once those things are clearly specified, Claude um can look at like raw traces and determine effectively like okay, where is the app likely falling short of my goals? So, that's I think kind of nice collaboration you can have in place.
</details>

而且这正是查看数据非常有帮助的时候。Claude 可以在某种程度上帮助引导你：好的，我看过数据了，这里有一批案例看起来有问题。这就像拥有一个在线评估器一样。想象一下你有一个追踪系统，你有一个在线评估器。它有一些针对客户满意度之类的评分。它为你标记出：这里有一些存在问题的 trace。同样的事情。就像你在告诉 Claude，告诉在线评估器，这就是我关心的，这就是我想让你检查的。它可以查看数据，它可以挑出一批看起来有问题的案例。然后基于这些案例，你可以去审查它们、理解它们，然后说：好的，基于这些给我构建一个 eval。在构建 eval 方面，这通常是 Claude 与人类之间非常良好的结合。

<details><summary>Original English</summary>
And and and that's actually when like kind of looking at the data is very helpful. So, Claude can kind of help to steer you okay, I've looked at the data. Here's a bunch of cases that look problematic. And that's that's just like having an online evaluator. So, you like imagine you have a tracing system, you have an online evaluator. It has some like grading for like customer satisfaction. It's flagging like here's problematic traces for you. The same kind of thing. Like you're telling Claude, you're telling online evaluator, here's what I care about, here's what I want you check. It can look at the data, it can elevate a bunch of cases that look like these look problematic. Then given those cases, you can like review them, understand them, and then say okay, yes, build me an eval based upon these. That's typically a very nice marriage between like Claude and human when it comes to building evals.
</details>

是的，问题是：谁负责构建 eval？我的意思是，这取决于问题本身，取决于……我想再次强调，每个人、每个人都有权构建 eval。所以它并不是按团队严格划分的。它通常基于对产品的归属权，并且我认为特别是当你有这样的 skill，让构建 eval 来辅助爬山变得更加容易时，它确实大幅拓展了能够切实构建和设计 eval 的人员范围，这实际上非常不错。所以我们在 Anthropic 看到许多许多不同类型的岗位都在构建评测。嗯，因为 Claude 的深度参与并能提供巨大的帮助。嗯，很多诸如构建 eval 运行器等等枯燥繁琐的工作，Claude 都能处理好。所以，这真正涉及的还是我们之前谈到的：人类的品味在引导整个过程。我关心的是什么？很多不同类型的岗位都可以发挥这种指导作用或提供这种把控。

<details><summary>Original English</summary>
Yeah, question is like who's responsible for building evals? I mean, it depends on the problem, it depends upon I mean again throw back at everyone ever everyone is empowered to build evals. So, it's not really delineated per team. It's typically based on ownership like of the product and um I think in particular when you have skills like this, it make it easier to build evals to help climb, it really opens up the number of people that can feasibly kind of build and design evals, which is actually quite nice. So, we've seen like Anthropic many many many different types of roles build evaluations. Um because Claude's so involved and then has can help so much. Um much of the tedium of like um you know, building an eval runner and stuff, that's like Claude can handle all that. So, really it's about what we're talking about before, the human taste guiding the process. What do I care about? And that's very that many different types of roles can can kind of serve that guidance or provide that steering.
</details>

### 大模型作为裁判（LM as Judge）与自动化研究

嗯，让我看看我有没有好例子。呃，好的。嗯，呃，凭空想的话。嗯，我见过……好的，我有一个好例子。我见过针对生成式 UI 的 eval。嗯，所以那算是一个很好的例子。呃，实际上我认为在那起案例中它是一个成对裁判（pairwise judge），回到你刚才提到的那一点。基本上就是对比配置 A 和 B，嗯，在两个不同的生成式 UI 之间哪个更好，打分器会进行成对比较。我认为这些结果随后会在多次试验中汇总，并使用类似 Elo 评分的机制进行打分。这就是我以前见过的带有成对评估器的生成式 UI 例子。还有很多其他例子我一时想不起来了。嗯，但人们一直在使用大模型作为裁判（LM as judge）。嗯，用于检索任务或者写作任务。嗯，呃，看，对 trace 进行分类，查看 trace 并指出“哦，这个不好，或者这个好”。所以这极其普遍。

<details><summary>Original English</summary>
Um let's see if I have a good one. Uh Right. Um Uh, off top of my head. Um I've seen Okay, I have a good one. I have seen um evals for generative UIs. Um, so that's kind of a good example. Uh, actually I think in that case it was a pairwise judge back to the point that you were making. Like so it's basically comparing like configuration A B, um what is better um between like two different generative UIs and like the greater would would do kind of pairwise comparison. I think then those results were rolled across many trials and scored with something like an Elo score. So that's an example of like generative UI with a pairwise evaluator I I've seen before. There's many other examples I can't think of at the top of my head. Um, but people use LM as judge all the time. Um, for like retrieval tasks or like writing tasks. Um Uh Look, categorizing traces, looking at traces and saying oh this is bad or good. So like it's extremely common.
</details>

是的。所以，好的，爬山算法工作的很多动力在某种程度上是源自自动化研究（auto research）。自动化研究很大程度上是由模型正变得非常非常出色这一事实所推动的。它们非常擅长自我修正。如果你给它们一个结构良好的问题，呃，它们就可以在上面进行爬山优化。所以我认为 Karpathy 的案例就是一个很好的例子，我想我不记得具体的问题了。我认为那种通用的设置适用于许多不同的形式。比如它可能是，你知道的，降低损失（loss）之类的。嗯，所以同样有一个非常明确可验证的目标，模型可以看着目标并将其作为爬山优化的指导。嗯，我有……

<details><summary>Original English</summary>
Yeah. So okay, that a lot of the motivation for the hill climbing work is kind of it is kind of flowing from auto research. Auto research is motivated heavily by the fact that models are getting very very good. They're very good at self-correction. If you give them a well-structured problem uh they can hill climb on. So I think Karpathy's case is a good example of I think I can't remember the precise problem. I think that general setup work with many different formulations. Like it could be um you know, like drive down loss or something. Um, so again there's like a very clear verifiable objective and clock can look at the objective and use that as a guide to hill climb. Um, I have
</details>

是的，我这里没有展示，但我还有其他一些在这一类爬山过程中做自动化研究的例子，它会……这种……特别是这个命令，实际上更多是为基于 eval 的爬山设计的，其中你有一个带有划分数据集（split）的 eval 数据集。自动化研究更像是你构建一个工件并对其进行评分，比如查看损失或类似指标，但这个设置大概可以非常容易地进行改造，以完全相同的直觉用于自动化研究。重点在于，在给定

<details><summary>Original English</summary>
Yeah, I didn't show it here but I have some other examples doing auto research um in this kind of hill climbing process and it would it would this kind of um This command in particular is actually designed more for eval-based hill climbing where you have like an eval set with a with a split. Auto research was looking more like you build an artifact and like grade it, like look at the loss or something, but the the setup could probably very be very easily kind of modified to work with auto research with the very same intuition. The point is that models are good at autonomous work over long horizons when given
</details>

<!-- chunk 7/9 -->

只要有一个明确的、嗯，明确的目标或可验证的，他们可以拿来作为奖励，可以衡量并用来指导下一步行动的东西，他们就非常非常擅长自主解决问题。所以，这和 auto research 背后的直觉是一样的。

<details><summary>Original English</summary>
a clear um a clear objective or verifiable that that they can reward that they can kind of measure and use to inform what their next move is, they're very very good at autonomously solving problems. So, it's driven by the same intuition as auto research.
</details>

>> 爬山法，然后扩展到 auto research。

<details><summary>Original English</summary>
>> hill climb and then extend into auto research.
</details>

>> 呃，爬山法的方法论会……所以，这只是个、只是个问题形式化（problem formulation）的问题。先明确这一点。比如 auto research 的形式化最初更侧重于，比如设计一个，比如像一个网络，比如说解决某个你有可验证目标（比如 loss）的问题。仅此而已。不过爬山的过程非常相似，比如 Claude 运行一些实验，衡量 loss，查看结果，然后进行调整，做点别的事情。所以它是同一种爬山循环，只不过在那种特定情况下，它只是应用到了一个略微不同的领域。

<details><summary>Original English</summary>
>> Uh the the methodology for hill climb would So, it's just a it's just a question of a problem formulation. This just to be clear. So, like the auto research from formulation was um was initially focused more on like on like designing, for example, an a like a network with, for example, um solving some problem where you have like a a verifiable objective like loss. That's really it. The the hill climbing process though was like very similar where like Claude runs some experiments. It measures loss. It looks at the results and then adapts, does something else. So, it's the same kind of hill climbing loop, but like in that particular case it's just applied to a slightly different domain.
</details>

所以，你大概可以拿这个 skill，基本上说：“好的，如果你有比如像 nanoGPT 代码库，把它配置给它，你就可以配合它使用这个 skill，我敢肯定。”Claude 会弄清楚如何去调整。如果你对这个感兴趣，就去试试吧。但核心过程是一样的。核心直觉也是一样的，那就是模型在利用自我修正和爬山方面非常非常有效。这就是关键的直觉。

<details><summary>Original English</summary>
So, it's like you could probably take this skill and basically say, "Okay, set this up for if you had like like a the nano GPT repo, you could use this skill with it, I'm sure." It would Claude would figure out how to adapt things. Just If you're interested in that, just just like try it. But the the core process is the same. The core intuition is also the same that like models are very very effective at using um at self-correction and hill climbing. That's the key intuition.
</details>

是的。

<details><summary>Original English</summary>
Yep.
</details>

是的，我有点试着在像这个例子里这么做，这里我关注的是成本和性能。所以你有点像是在这两者之间进行联合优化。是的，你可以直接告诉 Claude 这个多目标。通常它就会去衡量多个目标并把它们考虑在内。嗯，那肯定是可行的。这就是一个很好的例子。

<details><summary>Original English</summary>
Yeah, I kind of try to do that in like this example where I'm looking at cost and um performance. So, you're like kind of jointly optimizing across those two. And yeah, you can just tell Claude the multi-objective. And usually it will just kind of measure multiple objectives and and take that into account. Um that's certainly feasible. And this is a good example of that.
</details>

>> 你有没有测过最多可以……

<details><summary>Original English</summary>
>> Have you checked like what's like the max you like
</details>

>> 呃，我是说，是的，我没有推到那么远。我想我通常看的是成本和性能。而且速度是另一个维度。所以，成本、性能、速度。这感觉像是一个非常合理的、三位一体的指标组合，你可以去联合衡量。

<details><summary>Original English</summary>
>> Uh I mean, yeah, I haven't pushed that far. I think but I've typically looked at as cost and performance. And like speed's another dimension. So, you like cost performance speed. That feels like a pretty reasonable like trifecta of things that you would like kind of jointly measure.
</details>

嗯，是的，我是说，我认为随着你不断扩大规模，它确实会极大地阻碍爬山的过程，因为 Claude 在做出这些改动时试图平衡很多不同的目标。所以我认为这会让问题变得更难，但它是可行的。也许你可以考虑一次只改变一样东西。串行地去做。

<details><summary>Original English</summary>
Um, yeah, I mean, I think that um, as you kind of scale up, it just hobbles the process of hill climbing a lot cuz there's lots of different objectives that Claus is trying to balance when making these changes. So, I think it'll just it'll make the problem harder, but like it is doable. Maybe you could think about kind of changing one thing at once. Doing doing them serially.
</details>

### 模型反模式与努力程度

是的，那是一个非常好的问题。呃，关于这些内容的 prompt，其实在我谈到的所有事情中，它是最容易尝试的，而且往往极其——就像先做简单的事情。它非常简单，而且往往非常有效。呃，这个 skill 中的通用指导适用于……

<details><summary>Original English</summary>
Yeah, that's it that's a very good question. Uh, so the prompt on this stuff, which actually of all the things I talked about is the simplest thing to try and often is like extremely it's like do the simple thing first. It's very simple and often very effective. Uh, this general the general guidance in the skill applies to
</details>

嗯，模型的界线有点……不是那么精确。这些都是众所周知的反模式（anti-patterns），前沿模型像 55 系列绝对不再需要了。你需要往前推到多早的模型，这些模式才仍然适用？这还不太明确。我做过一些测试。大概像 Opus 45 开始，这些东西的相关性开始降低。所以这有点模糊。我不知道究竟具体到哪个模型你需要移除这些，但我的看法基本上是：当你迁移到最新的、比如像 Opus 55 时，直接照做就行。像最新的前沿模型绝对不需要这些模式了。

<details><summary>Original English</summary>
um, the the model delineation's a little bit on like it's not precise. These are well-known anti-patterns that definitively frontier models like the 55 series don't need anymore. How far back do you need to go until these patterns are still like appropriate? It's like not quite clear. I've tried to do some testing. It's maybe like Opus like 45 is the point at which these things start to like become less relevant. So, it's a little bit squishy. I don't know like precisely the model at which like you need to remove these, but my view is basically when you're doing a migration to the latest to like to like Opus 55, just do this. Like definitively like the latest frontier models don't need these patterns.
</details>

对，对，好的，说得好。所以这个 skill 确实有一些针对特定模型的注意事项。这个 skill 在一定程度上考虑到了这一点。比如如果你使用的是 Haiku，我理解。可能 Haiku 没那么自主。也许它确实需要稍微多一点的助推。我不知道是不是这样，我只是在随口提个假设。它会把这一点考虑在内。所以它确实内置了一些针对特定模型的指导。它很聪明，能够弄清楚，好的，这是你正在使用的模型，这是我们已知的不再需要的反模式。不过，这是个很好的提醒。

<details><summary>Original English</summary>
Yeah, yeah, okay, good point. So, the skill does have some model specific caveats. So, the skill takes that into account a little bit. If you're for example going to like Haiku, I get it. Like maybe Haiku like um, isn't quite as autonomous. Maybe it does need slightly more boosters. I don't know if that's true. I'm just kind of yeah, kind of kind of suggesting something. Um, it it'll take that into account. So, it does have some model specific guidance built in. It's like smart to figure out like okay, here's the model you're working with and here's the anti-patterns that we know are are not needed anymore. Um, but it's it's a good call out.
</details>

是的，呃，呃，

<details><summary>Original English</summary>
Yeah, uh, uh,
</details>

>> 是的，嗯，它不是一个……是的，我应该回过头来，把这一点讲得非常清楚。它不是一个硬性上限（hard cap）。它基本上是在告诉 Claude、向它强调要花多少思考来解决这个问题。所以举例来说，即使你设在非常高的努力程度（very high effort），你给它一个简单的问题，它不会只是为了验证它就随意耗费大量的 token。Claude 对于什么问题需要这些额外的思考是有一定权衡的。所以像……我不知道我有没有什么 eval 可以展示这一点。呃，可能没有。但它是建议的思考量。所以我认为它基本上是在告诉 Claude 针对一个问题要思考得多深入。

<details><summary>Original English</summary>
>> Yeah, um it it is not a Yeah, I I should I should get back to to like to be really clear about this. Um it is not a hard cap. It is basically telling Claude emphasizing how much thinking to do to solve the problem. So, like for example, even if you're on very high effort, you give it a simple problem that won't just arbitrarily spend huge amounts of tokens verifying it. There's some Claude has some thoughtfulness about like what problems require, um you know, all this extra thinking. So, like um And and I don't know if I have any evals that show that. Uh yeah, maybe not. Um but it is suggested thinking. So, that's the kind of way I think it's basically telling Claude how hard to think about a problem.
</details>

问题在于当你遇到更难的问题时，比如前沿的编程问题。在那种情况下，比如在超高努力程度（extra high effort）或最大努力程度（max effort）下，你会看到与中等或低程度相比在 token 消耗上的巨大差异，而实际结果并没有太大区别，因为 Claude 会做更多工作来验证结果。所以我认为在前沿难度的问题领域，努力程度的差异确实会导致很大的 token 消耗差异。那正是我们需要更加谨慎的地方。

<details><summary>Original English</summary>
The problem comes up when you have like a harder problem, like a frontier coding problem. That's where at for example hot extra high effort or max effort, you can see huge differences in token usages from like medium or low without much difference in actual outcome because Claude will do more work to verify the result for example. So, I think out in the frontier regime of problems, that's where these effort differences can really result in like big big token spend differences. And that's where we need to be more careful.
</details>

### 运行时调整与过拟合

是的，我是说，这……所以，如果你思考一下正在发生的事情，它和训练并没有太大不同。基本上你给模型一些奖励或目标，而它确实在试图对系统进行修改以提升目标。所以，是的，在理念上是相似的。事实上，即使在我们惯常的做法中，我们也会采用一些像训练集/测试集划分（test train splits）这样的简单原则，这些原则通常是在训练阶段采用的。但好在这些是你可以在运行时进行的修改。所以这基本上是一种采用这些原则的方法，但基本上是当模型部署之后，当你修改像 prompt 或 skill 这样的服务时，你可以采用我们在训练中使用的一些相同原则，不过是在你的特定领域中。这大概就是核心思路。

<details><summary>Original English</summary>
Yeah, I mean, this um this is So, if you kind of think about what's happening, um it's not dissimilar to to training. And basically you're giving a model some some reward or objective, and it it is indeed trying to make modifications to the system to improve the objective. Um so, yeah, philosophically that is similar. And in fact, even where we're used, you know, we employ some simple principles like test train splits that are often employed like at training time. But the nice thing is these are kind of run time modifications you can make. So, this is basically a way to employ some of those principles, but basically like once a model has been deployed and like you're modifying services like prompts or skills, um you can employ some of those same principles that we use in training, um but like in your particular domain. Uh that's kind of the the big idea.
</details>

对，那么 Claude 会意识到自己正在被评估吗？

<details><summary>Original English</summary>
Yeah, so like is Claude aware this being evaled?
</details>

>> 嗯，对，没错。我认为那是我们在博客中发布过不少内容的东西。那确实是一个担忧，在……在训练的不同阶段，那绝对是一个担忧。至于我们在这里讨论的内容，我认为它在某种程度上可能会是一个担忧。但我认为相比我们在这里讨论的，更大的担忧通常更多是过拟合。Claude 可能会知道自己正在被评估。但它会根据在当前 eval 分布中提供的内容，寻找爬山提升目标的方法。经典的例子就是，它会发现一些不适用于生产环境的 prompt 技巧和微调，而这些确实能在你的 eval 上显著提升性能。我见过这种情况发生，这种情况经常发生。

<details><summary>Original English</summary>
>> Um, right, exactly. That I think that's something we've published on a fair amount. That is a concern um, in the that that is certainly a concern kind of in in training uh, in different stages of training, absolutely. What we're talking about here um, I I do think um, it could be somewhat of a concern. I think the bigger concern than what we're talking about here is typically more overfitting. So, Claude may know it's kind of being evaluated. Um, but it will find ways to hill climb the objective based upon what's been provided in kind of this eval distribution that has. The classic example being it'll find um, kind of prompt tricks and tuning that aren't applicable to production that indeed improve performance significantly on your eval. So, I've seen that happen that happens all the time.
</details>

这并不一定是 Claude 意识到自己正在被评估，并表现出某种意料之外的行为。更多的是，你给它一个 prompt，Claude 能找到调整这个 prompt 的方法来让数值上升，它就会这么做。这就是为什么我们会使用训练集/测试集划分并尝试进行正则化。所以我认为过拟合更是我们在这里要考虑的实际问题。不过，评估意识（eval awareness）确实是一个更广泛的现象，我们在一些研究博客中也讨论过。

<details><summary>Original English</summary>
And it's um, it's not necessarily that Claude's like aware it's being evaled and saying like it's it's kind of some um, kind of unexpected behavior. It's more that like okay, you've given it a prompt and Claude can find ways to shape this prompt to like make number go up and it'll just do that. Um, that's why we use things like test train splits and try to regularize. So, I think overfitting is more of the practical concern that we're going to think about here. Um, but it is true that eval awareness is like a broader phenomenon that we we have discussed in in some in some of research blogs.
</details>

对，说得好。大概什么是最小的、有用的数据集？测试集和训练集之间的划分是怎样的？

<details><summary>Original English</summary>
Yeah, that's a good point. Um, kind of what's like the minimum kind of data set that's that's useful. What is like the split between test and train?
</details>

呃，我没有深入研究过那个。坦白讲，直接问 Claude 就行。当你设置好并运行这个命令时，根据信号或者你试图衡量的目标，Claude 有一些启发式方法来推断真正有帮助的 eval 集规模。Claude……

<details><summary>Original English</summary>
Uh, I haven't looked at that in depth. Um, frankly, just ask Claude. Like um, when you set this up and you run this command, Claude has some heuristics to reason about the size of the eval set that's actually helpful given the signal or like what you're trying to measure. Claude
</details>

<!-- chunk 8/9 -->

### 评估集规模与过拟合风险

可以去推断比如你应该拥有多少个样本。而且在 skill 中对此有一些指导。所以，这是你可以与 Claude 一起去微调的事情。但我并没有超级具体地去关注比如不同的评估集规模以及……我认为我主要会担心的核心问题更多是……大概是过拟合和方差。所以，如果你拥有的样本数量非常非常少，比如，好吧，那真的能代表你所关心的东西吗？它更容易发生过拟合。所以，它们可能并不会超出你的生产环境——也就是你真正关心的场景——的分布。它们可能更容易过拟合，也可能会有更多噪声。所以不管怎样，我认为在处于非常非常小样本的区间时，就会出现这些问题。

<details><summary>Original English</summary>
can kind of reason about like how many examples you should have. And then there's some guidance in the skill for this. So, it's something you can kind of uh, work with Claude to kind of con-tune. But I haven't looked at like spoop or super specifically like uh, different like eval set sizes and like um I think the central concern I would have is more um it is probably overfitting and um and like variance. So, if you have a very very small number of samples, like okay, is that really representative of what you care about? Um uh it's a lot easier to overfit. So, like they may not be out of distribution for your production like what you actually care about. Um they may be easier to overfit. Uh they may be noisier. Um so, anyway, like I think those are the problems that arise when you're in like the very very small sample regime.
</details>

### 长时间任务上的爬山优化与 Harness 设计

是的，好的。这个问题是关于在耗时非常非常长的任务上进行爬山（hill climbing）。这挺有意思的，因为这其实就是为什么我提到自己通常会在简单表面（比如 prompt）上进行的原因，因为它们的修改非常非常快。不过你说得对。在某些情况下，你所处的环境里改动可能耗时非常非常长。这实际上会让爬山变得困难得多，因为那样它就变成了一个耗时漫长得多的任务。所以，这需要长得多的时间。这实际上就切入到了我们关于 harness 设计的最后一个要点。如果你打算那样做，如果你在进行非常非常长时间的爬山，你实际上需要能够持续可靠运行很多很多小时到数天的 harness。显而易见，我们在内部拥有这样的基础设施。我们使用像托管智能体（manage agents）这样的东西。

<details><summary>Original English</summary>
Yeah, okay. So, the question is about hill climbing on tasks that are like very very long duration. So, kind of that's funny cuz that's actually why I mentioned I typically do like simple surfaces like prompts because they're like very very quick to change. Uh you are right though. There's some cases you're in a regime where like your changes could be very very long duration. That effectively makes hill climbing much harder cuz like it's a much longer duration task then. So, it's a lot longer time. That's actually where that gets into our final point about kind of harness design. If you're going to do that If you're doing like very very long duration hill climbing, you actually need harnesses that can like remain reliable for like many many hours to days. And so, we have we have that obviously internally. We use things like manage agents.
</details>

我认为当你在做那件事时，它只是变成了一个更大的基础设施工程。这是可以做到的。显而易见它会更难，原因正是我刚才提到的：基础设施问题、故障，以及看到信号所需的时间要长得多。

<details><summary>Original English</summary>
Um I think it just becomes a bigger infrastructure lift when you're doing that. It can be done. Um it obviously is harder because of what I just mentioned, infrastructure issues, failures, um and just like a lot longer time to see your signal.
</details>

### 单轮与多轮评估

单轮对比多轮评估。我是说，是的。在构建智能体时，你通常确实需要多轮评估。Claude 可以帮助你做到这一点。特别是像 build eval 命令，它可以查看 trace。如果你给它一堆 trace，它可以帮你将特定的 trace 提升到你的评估集中。在评分方面，我是说，是的，在这方面有很多不同的理念。你可以让评估器查看整个 trace 轨迹。你也可以让评估器查看智能体的最终成果。存在很多不同的理念。build eval 命令有很多指导。所以，如果你有某个感兴趣的特定智能体，如果你基本上让这个命令访问这些 trace，它在为你构建和设计评估方面应该会非常非常有效。如果你能告诉它我需要多轮，以及这是我正在考虑的内容。好的。

<details><summary>Original English</summary>
Uh single turn versus multi-turn evals. Um I mean, yeah. When you're building agents, you do typically need multi-turn evals. Um Claude can help you do that. Particularly like the build eval command, it can look at traces. It can If you give it a bunch of traces, it can help you promote um it can help you promote particular traces to your eval set. Um in terms of grading, um I mean, yeah, there's a lot of different philosophies on this. You can have evaluators looking at the entire trace trajectory. You can have evaluators looking at like the final agent outcome. Uh there's a lot of different philosophies. The build eval command has a lot of guidance. So, like if you have a particular like agent you're interested in, if you basically give this command access to the traces, it should be pretty pretty effective at kind of shaping and designing the eval for you. And if you can tell it I want multi-turn and here's what I'm considering. Um cool.
</details>

### 上下文工程中的“大脑与双手解耦”

很有意思。所以在上下文工程中，哪些技术能极大地提升可靠性，而哪些技术又属于被过度吹捧的？让我想想。

<details><summary>Original English</summary>
Interesting. So like for context engineering, what promotes of reliability a lot versus what's like overhyped as a technique? Um Uh let's see. Um
</details>

那么好的，我认为关键的事情——而且我过去实际上也提到过这一点，我们在论文中也提到了。我认为关于递归语言模型（RLM）的工作和想法相当不错。我们在当前这里实际上也采用了这个思路。我认为在上下文工程的可靠性方面，非常重要的一点是将大脑与双手解耦。所以基本上设计你的系统，使得……关键点在于：上下文对象是独立于 harness 的。因此 harness，基本上你的云端模型能够有效地查询这个独立存在的上下文对象。由于所有这些不同的原因，这是非常有益的。其一，上下文始终是可恢复的。通常你可以想象另一种情况，你只有消息历史记录，经历了一次压缩事件（compaction event），然后所有被你压缩掉的内容就都没了。如果你没有像这样将它备份起来，你就永远无法恢复它。这就是为什么在上下文工程的可靠性方面我其实非常喜欢这种架构。它完全做到了 RLM 研究工作所倡导的事情。比如基本上就是把上下文对象与模型分离开来，并且上下文对象与模型之间形成关联，模型可以通过不同的机制去查询它。而这正是我们在这里所做的。

<details><summary>Original English</summary>
So okay, the key thing I think and I've actually I've mentioned this in the past, we mentioned in the paper too. I think the recursive language model work in RLM idea is quite good. Um and we actually employ that idea here. I think a very important thing in terms of context engineering reliability is decoupling brain and hands. So basically designing your system such that it um the con- the key point is this, the context object is independent from the harness. So the harness is basically your cloud can effectively query this context object that lives independently. That's beneficial for all these different reasons. One, the context is always recoverable. So typically imagine alternatively you just have like, you know, a message history, you do a compaction event and everything you compacted is gone. You can never recover it if you haven't like backed it up in the way like this. That's why I actually like this architecture a lot for reliability in terms of context engineering. It does exactly what the RLM work advocated. Like it's basically splitting the context object from the model and the context object comes linked the model can interrogate through different mechanisms. And that's exactly what we do here.
</details>

因此，查询该会话日志基本上是由 harness 通过不同的工具来完成的。我认为那是一个非常优秀的架构。所以我觉得这是我在可靠性、可恢复性方面发现非常好的技巧之一。特别是在构建长时间运行的智能体时，很难预知未来会有什么信息是重要的。所以当你进行压缩时，你未必知道自己是否需要回头去查询那些正在被你总结的上下文。而当你在像这样的一个对象中对它进行了备份，你就随时可以做到这一点。所以我觉得这是我非常喜欢的一个技巧。RLM 的研究工作在那个方向上非常棒。是的。

<details><summary>Original English</summary>
So interrogating that session log is basically done by the harness through different tools. Um and that's a very nice architecture I think. So I think that's like one of the tricks that I I found to be very nice for reliability, recoverability, um and in particular building like long duration agents, it's hard to know what will matter in the future. So when you do a compaction, um you don't necessarily know if you need to like go back and interrogate that context that you're summarizing. And when you have it backed up in an object like this, you can always do that. So I think that's a trick that I I I a lot. Uh and the RLM work was was very nice in that direction. Yep.
</details>

### 前沿模型解绑与优质评估设计

是的。嗯，我认为 [清喉咙] 这就是为什么，你知道的，我们要花很多时间在良好的评估设计上。是的，这些模型具有非确定性。在很多情况下，它们所运行的领域中的结果不是轻易可验证的，并不是所有事情都是编程问题。许多情况下，你希望智能体去做一些更依赖判断、产出更自由开放的事情。在那些领域中，你必须在评估设计上非常巧妙，以便为 Claude 提供一个可以攀登的目标。而且我认为我们在验证器设计方面谈到的所有事情——比如良好的目标、明确的评分量表、能验证结果的多模型、低方差——在设计你希望 Claude 去解决的问题时都极其重要。因此，我认为正如在这次演讲中提到的那样，当谈到解放前沿模型（unhamble frontier models）时，我认为前期投入大量时间进行非常非常出色的评估设计，是确保充分发挥模型潜力的途径。因为如果你对模型说：“好的，在这个结构非常糟糕的评估上优化性能。”它将一无所获。而这并不是模型的错，不是因为你没有把评估想清楚，就是因为用例本身是不可能的或模棱两可的。所以，我认为这里的部分信息就是保持深思熟虑，并在评估设计的前期投入大量时间，这样你就能让前沿模型走向成功，并有效地解放它们。这差不多也就是本次演讲标题的由来。

<details><summary>Original English</summary>
Yeah. Well, I think [clears throat] that's why, you know, we spend a lot of time on um, good eval design. Um, yeah, these models, um, are non-deterministic. Um, in many cases the operating regimes where outcomes are not easily verifiable, like not everything is a coding problem. Many cases you want agents to do things that are more judgment-based, more free from open-ended outputs. In those regimes, you have to be very smart about your eval design so that you're giving Claude an objective that I can climb. And I think all the things we talked about in terms of like kind of verifier design, like good objectives, clear grading scales, multiple models can validate the result, low variance, all are like super important when designing like the problem that you want Claude to go and solve. So, I think, as kind of mentioned it in this talk, when it comes to unhambling frontier models, I think spending a lot of time up front in a very very good eval design is a way to make sure that you're getting the most out of the model because if you said tell the model, "Okay, optimize performance on this like very poorly structured evaluation." It won't get anywhere. And it's not the model's fault because you haven't thought through the eval, it's because cases are impossible or ambiguous. So, I think part of the message here is to just be thoughtful and spend a lot of time up front in the eval design such that you kind of set up frontier models for success and effectively unhamble them. That was kind of the the namesake of the talk.
</details>

也许，我们大概时间到了，大家可能都累了。我昨晚参加了一场婚礼，所以我非常累。这时间点真巧，不过能来这里当然非常高兴。实际上，这非常有趣，问题也非常好。也许这边再回答最后一个问题。

<details><summary>Original English</summary>
Maybe, um, I we're probably at time and everyone's probably tired. I was at a wedding last night, so I'm very tired. That was a funny timing, but it's very nice to be here, of course. And actually, it's been uh, it's been a lot of fun, very good questions. Um, maybe one more question over here.
</details>

### 模型能力提升与评估集迭代

嗯。是的，所以我认为这是个好问题。它是关于：是的，模型一直在变得更强，那么我该如何修改我的评估以跟上步伐？而且我认为，很简单，情况理应是随着模型变强，你应该看到评估上的表现不断上升，就像我们在这张图表中看到的那样。如果你没有看到这一点，那么我会回过头去质疑评估当初是如何构建的。确实，是的，我们一直看到这种情况。模型非常迅速地让评估饱和。所以，我们确实需要开发新的、难度更高的评估来跟上材料的发展。实际上，这是个很好的切入点。这实际上相当困难。要构思出真正能挑战当今最顶尖模型的评估是很难的，甚至像 Fables Opus 5.5 这种也是如此。

<details><summary>Original English</summary>
Mm. Yeah, so I think that's a good question. It's about like, yeah, models are getting better all the time, so like, how do I modify my evals to keep up? And I think simply it should be the case that as models get better, you should see performance on eval going up like we see in this diagram. If you don't see that, then I would go back and question the eval was structured. Um it is true like Yeah, we see this all the time. Models are saturating eval very quickly. So, we do need the development of new and harder evals that like keep up with the material. And actually, that's a good point. It's actually pretty hard. It's hard to come up with evals that really challenge like the best models today, like the Fables Opus 5.5 even.
</details>

所以我确实认为这是一项周期性出现的挑战，要去设计出良好的评估来测试最优秀模型的能力。这绝对是一项挑战。但我确实认为，如果你拥有一段时间前构建的评估，你应该在它们上面看到这种趋势。因此，随着模型变强，你应该看到表现一路上升。如果你没有看到，我会对评估本身的方方面面提出质疑。这差不多是我想要表达的关键观点。

<details><summary>Original English</summary>
Um so, I do think it's a it's a it's a it's a recurring challenge um to design good evals that test the capabilities of the best models. It's absolutely a challenge. Um but I do think so, if you have evals that you built sometime ago, you should be seeing this trend on them. So, as models get better, you should be seeing performance going up and up and up. If you don't, I would question things about the eval itself. That's kind of the key point I would make.
</details>

我是说，在这个方面，我实际上从各个 trace 相关公司那里看到了很多有趣的工作。所以我见得相当多的工作流程大致是这样的：部署了智能体，它们产生 trace，你拥有一个在线评估，你在查看那些……

<details><summary>Original English</summary>
I mean, I've actually seen a lot of interesting work on this from the various trace and companies. So, like the the the like workflow I've seen quite a bit of is like you have agents that are deployed, they're like producing traces, you have an online eval you're looking at those
</details>

<!-- chunk 9/9 -->

### 线上评估与离线测试循环

追踪并对它们进行打分。打分……得分较低的 Trace 随后就会被拉入某种离线评估集中，然后你大致就在那上面进行爬山算法式的优化。接着这个循环继续进行。我认为那是一个很好的……那是一个非常好的模式。这非常合情合理。所以，那里发生的事情通常是你在针对生产环境中失败的这些用例进行爬山优化。

<details><summary>Original English</summary>
traces and scoring them. Score Trace that score poorly are like then pulled into some offline eval set, you kind of then hill climb on that. And then that loop continues. That's a good That's like a very good pattern, I think. It's very reasonable. Uh and so, what's happening there is you're typically like hill climbing on these cases that you're failing on in production.
</details>

然后你会，你知道的，在它们全都通过之后把那些放进回归测试中，而这种做法会一直持续，直到你在生产环境中看到的失败非常少为止。所以，这实际上是构建你的某种评估循环的一个很好的通用方式，在许多……你知道的，LangChain、Rise、Braintrust，所有这些公司在某种程度上都有提供这种……这种外循环的产品服务，这看起来确实相当、相当有效。

<details><summary>Original English</summary>
And then you're like, you know, putting those in regression tests once they all pass, and that like continues until in production you're seeing very few failures. So, that actually is a good general way to structure your kind of eval loop and in many of the, you know, the LangChains, Rises, Braintrusts, all these companies kind of have product offerings that offer this kind of this like outer loop, which does seem quite quite effective.
</details>

确实如此。所以，那里的挑战就变成了：好的，那么你的线上评估器是什么？也就是说：好的，你怎么知道在生产环境中什么是好的，以及你正在将什么晋升到你的离线评估集中？还有……

<details><summary>Original English</summary>
You do. So, the challenge there becomes okay, well, what are your online evaluators? So, like okay, how do you know what good is in production and what are you promoting to your offline eval sets? And
</details>

嗯，是的，这根本不容易。

<details><summary>Original English</summary>
Um, yeah, it's not easy at all.
</details>

嗯，我认为那是……是的，现在在那个特定领域有大量的产研工作。就我而言，我没有太密切地关注那个领域——比如各类追踪可观测性公司正在研发的所有最新动态，但我的理解是，在那一类公司当中，这确实是一个非常、非常活跃的产品开发领域。

<details><summary>Original English</summary>
Um, I think that is Yeah, that's like there's like a lot of product work in that particular domain now. As far as I haven't followed that area too closely. Um, like what all the latest um, kind of updates that the various like tracing observability companies are working on, but my understanding is that it's like a very very active area of like product development among that class of companies.
</details>

所以，那挺有意思的。

<details><summary>Original English</summary>
So, that's pretty interesting.
</details>

### 结语

额，好的，到这里也许我们就让大家散会了。嗯，非常高兴见到大家。所以，随时欢迎在任何地方联系我，感谢大家的时间。

<details><summary>Original English</summary>
Uh, okay, with that maybe we'll let everyone go. And um, very nice to see you all. So, feel free to reach out to me anywhere and thanks for the time.
</details>

>> [掌声]

<details><summary>Original English</summary>
>> [applause]
</details>