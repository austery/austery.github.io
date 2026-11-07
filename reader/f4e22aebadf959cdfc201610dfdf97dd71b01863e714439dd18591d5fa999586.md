---
author: AI Engineer
date: '2026-07-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=uIiA6DquRiE
speaker: AI Engineer
tags:
  - model-distribution
  - training-optimization
  - performance-metrics
  - reward-hacking
title: 语言模型分发、优化与性能极限的深度研讨
summary: 文章介绍了大型语言模型和扩散模型的发布商在模型分发（如上传至顶级平台）、漏洞修复以及训练栈优化的工作。同时，探讨了模型能力指标（Meter Plot）、单次提示与多次提示的成功率，并分析了指数级进步趋势，最后讨论了奖励作弊问题及矩阵乘法的理论极限。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/17 -->

### 欢迎与团队介绍

**Daniel**: 大家好。非常感谢大家今天能来。我是 Daniel，来自 Unsloth，我兄弟今天也在这里。对于还不了解我们的朋友，我们实际上是最大的语言模型和扩散模型分发商之一。我们不仅仅做语言模型，还会把模型上传到 Hugging Face。我想我们在 Hugging Face 的顶级组织中大概排在前十名。我们的总下载量已经超过了 3 亿次，所以大家一定要去看看。你可以运行 DeepSeek、GLM 以及许多其他模型，我们会使用动态量化技术对它们进行量化，让你可以直接在本地电脑上运行。

<details>
<summary>Original English</summary>

**Daniel**: Hello everyone. Yeah, thanks so much for coming today. Much appreciated. Yes, I'm Daniel. I'm from Unsloth. My brother is also here today. But yeah, like you know, thanks for coming. So for you folks who don't know us, we actually, you know, we're one of the largest distributors of language models and diffusion models as well. So we don't just do language models. We upload our models to Hugging Face. And you know, we're on the... I think we're number 10 or something on the list of the top organizations on Hugging Face. We have over 300 million total downloads. So definitely check us out on that. You can run like you know DeepSeek, GLM, many other models and we quantize them down using dynamic quantization. So you can run them on your local computer.

</details>

### 模型修复与训练栈优化

**Daniel**: 我们也为开源模型做很多漏洞修复。我们修复了 OpenAI 的 GPU 代码、Meta 的模型、Google 的模型、DeepSeek 等许多其他模型中的错误。它们有时会出现很多问题，然后我们会在 Twitter 上发布我们的发现。所以你们用过的大多数开源模型，很可能都包含了我们的修复。我们与全世界的人在模型发布上进行合作，也与硬件供应商合作。我们不仅做模型修复，还引入了新功能，并针对整个训练栈进行优化。例如，我们引入了被称为“异步梯度检查点”的技术，被许多组织所使用。我们还引入了 Flex Attention，也被很多人使用。我们还修复了一个梯度累积的错误，将整个训练栈的准确率提高了 1% 到 3%。所以我们不只是对模型进行漏洞修复，还包括整个训练栈的修复等等。

<details>
<summary>Original English</summary>

**Daniel**: We also do many bug fixes for open source models. So you know we fix many bugs in OpenAI's GPUs, Meta's models, Google's models, DeepSeek, many other models we fix bugs in them. And so they have many issues sometimes and then we post about them on Twitter. You know we post about our findings. So most of the open source models that you guys have used are most likely fixed by us. And yeah, we collaborate with everyone in the entire world on model releases. We also collaborate with hardware providers and we really appreciate the collaborations with everyone. We also don't just do model fixes and bugs, we also introduce new features and we also do fixes for the entire training stack. For example, we introduced something called async gradient checkpointing which is used by many organizations. We also introduced flex attention which is used by many folks. And we also fixed a gradient accumulation bug fix which increased accuracy by 1 to 3% across the entire training stack. So we don't just do bug fixes for models, it's also whole training stack fixes and stuff like that.

</details>

### 研讨会流程与 AI 现状

**Daniel**: 今天的研讨会时间挺长的，会有多个环节。每个环节结束后，大家都可以提问。如果不确定有没有麦克风，只要你大声提问，我都非常乐意解答。我们今天要讨论的第一个部分是 AI 的现状：语言模型和 AI 模型目前处于什么阶段？

<details>
<summary>Original English</summary>

**Daniel**: So today, the workshop is quite long. So there will be multiple sections in the workshop. And so after each section, anyone can ask a question. And so, please, I guess, if I'm not sure if there's a microphone, but if you could raise your voice and you ask a question, I'm more than happy to answer them. But the first section we're going to be talking about is the state of AI. So, where is currently language models, AI models, where are they at currently?

</details>

### 能力指标：Meter Plot 与模型欺骗

**Daniel**: 不知道大家是否了解“Meter Plot”。这个图表展示了模型的时间跨度能力。也就是说，如果一项任务需要人类花费 16 个小时，模型能完成吗？从这个图表上你可以看到，Claude Mythos 预览版非常强大，它可以完成需要人类 16 小时才能做完的任务。Opus 4.6 也在上面，其他所有的模型都在图表里。这个图表很好地象征了 AI 模型随着时间推移正变得越来越强。比如最近发布的 GPT-5.6 预览版，他们官方并没有更新图表，因为他们说结果还不够可靠，但我还是把它标在了图表上。你可以看到 GPT-5.6 大概在 Opus 4.6 的水平，但置信区间很大，也就是说对该模型的能力非常不确定。然而，如果你把“欺骗行为”算进去——因为模型在某些任务上有时喜欢作弊——那么它的能力实际上能达到 270 个小时。在 Y 轴上我其实做了一个不连续的图表，直接从 50 小时跳到了 250 小时。所以你可以想象这个图表实际上非常偏斜。当我制作这个图表时，GPT-5.6 是一个非常大的异常值，所以我不得不压缩图表。但这只有在你认为 GPT-5.6 在某些任务上作弊的前提下才成立。我们稍后会讨论为什么 AI 模型会作弊，以及我们该如何解决这些问题。不过，这个图表在展示这些模型的能力方面非常有用。

<details>
<summary>Original English</summary>

**Daniel**: So I'm not sure if everyone knows the meter plot. So this meter plot shows the time horizon of models. If every single task, if it takes a human 16 hours, can a model finish that task. And you can see on this plot, Claude Mythos preview is very good. It can do tasks that humans can do that take a human 16 hours. Opus 4.6 is also there. All the other models are also there. And so you know this plot is very good because it symbolizes the AI models are getting better and better and better over time. Recently with the launch of GPT-5.6 preview model just on Friday, I put the plot so they didn't actually update their plot because they said that the results were not trustworthy enough, but I just put it on the plot. And so you can see that GPT-5.6 is around Opus 4.6 level I guess with large confidence bounds. So it's very uncertain about the capabilities of the model. However, if you include cheating, so if you include that the model sometimes likes to cheat on some of the tasks, then it actually goes to 270 hours. So if you look at the y-axis I actually did a disjoint graph. So the y-axis is 50 hours skipped to 250 hours. So if you can imagine the graph is actually very skewed. When I made the graph, GPT-5.6 was like a very big outlier. So I had to compress the graph. But this only works if you consider that GPT-5.6 cheated on some of the tasks. And so we'll be talking about why AI models cheat and how do we solve these issues. But yeah this plot is very useful to showcase the capabilities of these models.

</details>

### 单次提示与多次提示的成功率

**Daniel**: 之前如果想在单次提示下达到 50% 的成功率，你只需直接要求模型去实现 X 或实现 Y。但如果你想让模型表现得非常好，也就是看 80% 的成功率指标，这个能力跨度就会下降很多。你可以看到，之前 Mythos 在 50% 成功率下大约能完成 16 到 17 个小时的任务，但在 80% 的成功率下，它只能完成 3 个小时的任务。所以，如果你只给模型一个单次提示的例子，然后期望它能很好地实现 PageRank、某种 RAG 系统或者微调模型，它只能完成那些人类需要 3 个小时来做的任务。这就是 AI 模型的一个问题。总的来说，如果你想很好地使用 AI 模型，你需要至少提示它五次左右。假设每次尝试都是独立的，那么如果你提示多次，成功率会高得多。你不能指望只调用一次模型就能让它把工作做得很好，你需要调用多次。你可以算出它成功的概率：如果模型的准确率是 50%，失败率就是 50%，那么尝试五次的失败率就是 0.5 的 5 次方。这样经过 5 轮交互后，你的成功率就会跃升到大概 97%。所以，你至少需要调用模型五次，它才能非常有效。

<details>
<summary>Original English</summary>

**Daniel**: So previously this is 50%. If a model can complete the task with 50% of the time to 50% accuracy if you want to actually oneshot the model, so you just ask the model implement X or implement Y, and you want the model to do very well, then you want to look at the 80% success rate. If you look at the 80% success rate it kind of drops quite a lot. So you can see that previously Mythos is around 16 17 hours, now it only can do three hours. So if you prompt a model and you want to have like a oneshot example, you just trust the model by asking it implement, I don't know, page rank or something, implement some sort of rag system, fine-tune a model or something like that. It can only do a task that will take a human three hours to do. And so that is a problem with AI models. Generally speaking, if you want to use AI models very well, you need to prompt it at least like five times or something. And each of those times assuming they're independent the success rate is much higher if you're prompted many many times. Right, you can't just call the model once and expect it to do work to do well, you need to call it multiple times. And you can also work out the probability of it succeeding. You know if the model is 50% accurate then it will be 50% failure then it's 1 minus 0.5 to the power of five or something like that. If you do five turns and then your success rate jumps to like 97% or something. So you need call the model at least five times for it to be very effective.

</details>

### 指数级进步与 AGI 的逼近

**Daniel**: 之前这个图表的 Y 轴是一个线性趋势，但实际上不仅仅是线性的。如果我们对 Y 轴取对数，你会发现它呈指数级进步——实际上，对 AI 模型能力时间跨度进行完整拟合，会得到一条直线。你可以非常清晰地看到，AI 模型随着时间的推移正变得越来越好。我们还在图表上加入了是否允许 GPT-5.6 作弊的对比，以及 Claude Mythos 的表现。现在你不需要去伪造 Y 轴或做不连续处理了。通过对数坐标，你可以看出模型正在不断进步。如果这个趋势继续下去，这些模型将会变得越来越强。不仅仅是这个基准测试中的某一个特定任务，在所有的基准测试中，模型都在随着时间变得越来越好。像 GPQA Diamond 虽然有点进入瓶颈饱和期，但总体表现仍然很好。无论是 LiveCodeBench、数学测试，甚至特斯拉的自动驾驶，也都有着 17 个月的翻倍时间。也就是每 17 个月，模型的能力就会翻一倍。在每个领域、每个学科，它们都会变得更好。所以，最核心的问题就是：如果我们假设在每一个学科、每一个领域，模型的能力都在逼近 100% 的准确率，这就是 AGI 吗？

<details>
<summary>Original English</summary>

**Daniel**: So previously these are linear, this is a linear trend on the y-axis. It's not just linear. If we log the y-axis you can see that it's more exponential progress. So it's actually a straight line fit to the entire progress of AI models on the meter time horizon. Benchmark you can see that it's very clear that AI models are getting better and better over time. We also added GPT-5.6 with the cheating and no cheating and also claude mythos are accentuated that. And you can see I you don't need now you don't need to fake the y-axis, you don't need to do like a disjoint y-axis. If you do that you can see that models are getting better over time. And supposedly if this trend continues these models will get better and better and much better. Yeah, so the question is if the trend continues, that's the fundamental question. And it's not just one specific task for this benchmark that you can see that models are getting better over time, across all benchmarks models are getting better over time right. So like GPQA diamond it's kind of plateaued, it's kind of already saturated as a benchmark but over time it does very well. Every single benchmark you see models are getting better. Live code bench, math tests, even Tesla's self-driving I guess is also has like a doubling time of 17 months. So every single 17 months the models will get better and better. Double their capabilities. So over time all these models in every single subject every single area it will get better. Um so I guess the main question is if we assume every single subject every single area the models get 100% like approaching 100% accuracy, is this AGI? Um so that is one of the fundamental

</details>

<!-- chunk 2/17 -->

### 基准测试与 AGI 进展

**Speaker A**: 人们常问的一个问题是，如果我们只是在基准测试上变得更好，这算是 AGI 吗？如果我们在所有的基准测试上，也就是人类创造的每一个基准测试上都表现得更好，那会发生什么？模型只是在所有测试上都变得更好而已。这里有一张非常好的图表，展示了所有不同类型的基准测试，它们都随着时间的推移而不断提升。大家最喜欢的——我觉得是 Artificial Analysis（人工智能分析）的基准测试——也显示出人工智能的能力随着时间的推移正在变得越来越好。我觉得 Fable 可能是目前最好的基准测试，虽然现在不是所有人都能访问，但不管怎样，它目前是最好的。而且你可以看到，随着时间的推移，这些模型也都在变得更好。这张图表展示了一个非常有用的指标，我们在想，如何去进行基准测试，这个基准测试在展示模型能力方面究竟好不好。我们之后也会讨论这个问题。另一方面，是的，模型确实随着时间的推移变得更好。但是，仍然有一些事情是模型不太擅长的，例如，在长上下文方面做得就不太好。

<details>
<summary>Original English</summary>

**Speaker A**: questions that people ask you know if we just get better on benchmarks um is this AGI um what happens if we get better on all benchmarks you know every single benchmark that human humanity has created it just gets better on all of them. Um yeah but so this is a you know very good plot show well I guess chart showing all of the different types of benchmarks and they all get better over time. everyone's favorite I guess artificial intell uh you know artificial analysis benchmark showing you know artificial intelligence getting much much better over time as well you know fable I guess is I guess the best for now um although not everyone can access it currently but anyways it's for now it's the best um and you can see over time that you know these models are getting better over time as well um and you know like this plot showcases um a very useful indication you know like how do we like you know benchmark you know is this benchmark actually good um in terms of like you know showcasing the capabilities of models as well. Um and we'll be also discussing about that as well. Um on the other hand yes models are getting better over time. Um but there are some things which models are not very good at still for example long context is not doing very well.
</details>

### 长上下文能力的挑战与基准测试缺陷

**Speaker A**: 所以，大多数模型，你可能会说，好的，Gemini 有 100 万的上下文长度，GBD 有 100 万的上下文长度，Claude 也有 100 万的上下文长度。但是，你真的应该用满这 100 万的上下文长度吗？实际上有些基准测试表明，如果你使用比如 GBD 5.5——如果你使用 512K 的上下文，你的准确率会下降到 50%。也就是说，如果你使用 512K 的上下文，你只会记住你在之前上下文中写下的 50% 的事实。所以，也许使用完整的上下文并不是一个好主意。你可以看到 Opus 4.7（4.6 还是 4.7，是最后一条橙色的线），在 256K 的上下文长度下，它的准确率降到了 0%。所以这可能是基准测试的一个缺陷。也许不要太相信这个基准测试。但是，总体来看看基准测试还是有好处的，能了解模型在长上下文方面的能力究竟到了哪里。我标注的蓝线是开源模型，比如 DeepSeek、GL 5.1 以及其他模型。绿线是 Google 的模型。但你可以看出，总的来说，模型在处理长上下文时肯定会出现性能下降。所以，例如，如果你设置了一个自动压缩区，我建议你不要使用全部的 100 万上下文，也许最多 600K 左右，然后对其进行压缩，之后再继续你的编程会话。但总的来说，这张图表表明，长上下文仍然有很长的路要走。如果我们希望具备长上下文能力，我猜实验室还需要很多时间来解决这个问题。

<details>
<summary>Original English</summary>

**Speaker A**: Um so you know most models you might say okay Gemini has 1 million context length. You know GBD has 1 million context length. Claude has 1 million context length. But should you actually use all of the 1 million context length? Um so there are actually benchmarks to showcase that if you use for example GBD 5.5 um you know if you use 512 context your accuracy reduces to 50%. Um so if you use you know 512 context you will only remember 50% of the facts that you wrote in the previous context. Um so maybe that's not a good idea to use the full context. Um you can see opus 4.7 um 4.6 4.7 is the very last orange line. Um so at the context length of 256K it goes to 0%. Um so this might be a benchmark flaw. Um so maybe don't trust the benchmark too much. Um but it's good to look at the benchmark overall. You know where is the model's capabilities for long context. Um the blue lines I highlighted are open source models. You know deepseek gl 5.1 other models. Green is Google's models. Um but you can see in general you know models are models definitely do degrade over long context. Um so if you you know for example if you set like a you know automatic compaction area I would not suggest you to use all 1 million context maybe maximum 600k or something um and then compact it and then continue your you know coding session um but I would yeah but in general you know this plot shows that long context still has a very long way to go um and if we want to have long context you know capabilities um labs I guess will have a lot of time to fix this problem.
</details>

### 开源与闭源模型的长上下文对比

**Speaker A**: 另一张图表只是展示了开源与闭源的对比。开源模型在这个长上下文领域仍然有一段路要走。蓝线代表开源模型，而黑线则代表闭源模型。你可以看到，总体而言，开源模型表现尚可，但肯定还有很大的提升空间。与 Opus 4.7 相比，它要好一些。但也可能这个基准测试本身就需要改进，或许它还存在一些缺陷。不过总体来看，这张图表显示长上下文肯定还有更多的改进空间。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So another plot is you know just showing open source versus closed source. So open source still has some way to go for this you know long context. Um so open source is blue line and the black lines are like you know closed source models. Um and you can see in general open source does okay but there's definitely much more room for improvement. Um I guess compared to Opus 4.7 it's better. Um but you know maybe this benchmark does need maybe there are some flaws in the benchmark as well. Um yeah, but overall you know this plot shows that long context definitely still has more room for improvement.
</details>

### 智能停滞期与推理突破

**Speaker A**: 另外，如果你看看之前的图表，这个仪表图，我不确定你是否能看清楚，在 o1 preview 之前，性能实际上经历了一个停滞期。正如你所见，从 GPT-4 到 GPT-4o，并没有太大的性能提升。所以在大约一年的时间里，各大实验室都很困惑下一步该怎么走，直到 o1 preview 出现并证明了“推理”非常重要，在此之前他们实际上并不知道下一步该追求什么。因此，在这一年里，模型似乎陷入了停滞，我称之为“智能停滞期”。一个假设是，假设我们从未发现“推理”这种方法，那么 AI 模型可能会一直停滞不前；但因为我们发现了推理，我们证明了模型可以具备推理能力，这使得我们能够让这种增长趋势延续下去。所以通常我不确定这是运气的成分，还是这本身就是一个自我实现的预言。我不知道你们是否了解摩尔定律，摩尔定律能够延续，并不是因为这条定律本身，而是因为人们知道它必须延续，所以人们将资金投入到资源中以确保这条定律继续生效。所以，这在某种程度上表明，我们可能曾经处于一个模型已经停止进步的世界里。

<details>
<summary>Original English</summary>

**Speaker A**: And also you know like if you looked at the plot previously you know this meter plot um I'm not sure if you can see that before 01 preview there is actually a plateau of performance. Um and so if you can see you know GBD4 to GBD40 there's not that much performance improvement. Um and so this time frame around one year um was when you know the labs were confused on what is next um you know before 01 preview which showed that reasoning was very important they didn't actually know what to pursue next um and so for one year the models kind of like plateaued um and so I call this the intelligence plateau the hypothesis that you know you know assume that we never have discovered reasoning then maybe air models would have like plateaued um but because we have discovered reasoning you know we have shown that models can do reasoning capabilities we have continued the trend continuously um and so normally I don't know if this is like luck um or if this is a self fulfilling prophecy um so I don't know if you guys you know the moor law um you know mos law has continued um not because of the law but because people know that it must continue and so people invest money into the resources to make the law continue um and so this kind of like shows that you know we might have been in of the world where models have stopped improving.
</details>

### 新的缩放定律 (Scaling Laws) 与更短的迭代周期

**Speaker A**: 但是，随着 o1 preview 的发布，我想模型发展又回到了正轨。事实上，我做了一张图，假设我们没有发现推理，或者说没有 o1 preview。那么黑线代表模型原本应该具有的能力。你可以看到，我把它画成了一个 S 形，就像一个 S 型曲线。如果我们没有发现推理，那么模型在能力方面肯定会逐渐达到瓶颈对吧，我们只会拥有一个跟 Claude 3.7 Sonnet 或 o1 之类差不多能力的模型。但幸运的是，由于推理的出现以及这种全新的 Scaling（缩放）范式，这条绿线代表了新的 Scaling Law（缩放定律）。你可以看到，以前黑线的翻倍时间大概是 7 个月，也就是说每过 7 个月，模型的能力就会翻一倍。但现在，这个时间已经缩短到了 3.5 个月。也就是说，每隔 3.5 个月，你只需要等 3.5 个月，模型就会变得好一倍，能力提高两倍。我想这是相当惊人的。

<details>
<summary>Original English</summary>

**Speaker A**: Um but you know with the launch of 01 preview you know I guess models have went back to trend. In fact I made a plot showcasing you know assuming we did not discover reasoning or 01 preview. Um then the black line was the supposed you know capabilities of the models. You can see I made it into a S shape um like a you know a sigmoid type shape. Um and if you know if we didn't discover reasoning then models definitely will taper off in terms of capabilities right we'll only have a model that's as capable as claw 3.7 sonnet I guess or 01 or something like that um but you know luckily because of reasoning and this new paradigm of scaling you know the green line is the new scaling law um and you can see previously the black line the doubling time was actually around seven months so every single seven months the capabilities of the models double um but now it has shrunk to 3.5 months. So every single 3.5 months you just need to wait 3.5 months and the models will get double better, right? Better by two times. Um and that's quite striking I guess.
</details>

### 未来的发展轨迹与研究者的挑战

**Speaker A**: 但随之而来的一个核心问题是，这条绿线是否会继续保持直线增长？这是一个各大实验室仍在努力解答的基础性问题。如果这条绿线再次呈现 S 形怎么办？这是有可能的。但我们实际上并不知道这是否会发生，不知道这条绿线是否会一直无止境地直线向上攀升，还是会变成 S 形。很多研究人员可能因为这个问题而彻夜难眠：推理和 o1 之后，下一步会是什么？在那之后接下来到底是什么？许多研究人员将不得不深入思考这个问题。是的，这是我最喜欢的图表之一，因为它展示了只要有新的理念和创新，AI 的进步是随着时间推移可以持续下去的。好了，有人对第一部分有什么问题吗？请说。

<details>
<summary>Original English</summary>

**Speaker A**: Um so the main question though is will the green line continue as a straight line? Um that is a fundamental question that labs are still struggling on. you know what happens if the green line again you know the green line again goes as a S shape you know that's possible um but you know we don't actually know if this will happen you know if the green line will continue scaling you know going all the way up to infinity I guess or would it be like an S shape um and this is you know many researchers are you know I guess have sleepless nights you know what is the next you know what is the next thing afterwards after reasoning after 01 you know what is the next thing afterwards um and you know Many researchers will need to like you know I guess think about this. Um yeah but you know this plot is very you know this is one of my favorite plots because it shows that you know AI progress can continue over time with new ideas and innovation. Oh yes. So does anyone have any questions for the first section? Um yes.
</details>

### Q&A：关于参数规模的进一步扩展

**Audience**: 那么，我们现在已经一路发展到了一万亿参数，对吧？你认为如果我们需要下一次的飞跃，我们需要 10 万亿参数吗，还是说硬件将会成为我们看到下一次飞跃的瓶颈？

<details>
<summary>Original English</summary>

**Audience**: >> So we came all the way to one trillion right? Do you think the next jump if we need do we need like 10 trillion parameters when we'll see the jump or hardware will be the limitation that
</details>

**Speaker A**: 是的，这是一个很好的问题。这个问题是说，我们目前的模型已经达到了一万亿参数，我们是否需要增加到 10 万亿参数或者更多，才能使模型具备更强的能力？Scaling laws 确实表明，如果将参数量和数据规模相乘，一般来说，如果这个乘积变大，模型就会变得更强。所以，没错，你可以把参数量增加 10 倍，通常来说性能也会随之提升。然而，现在的观点是，这将会面临边际收益递减的问题。我觉得，这不仅仅是“模型规模乘以数据集规模”那么简单，这实际上是一个比例关系，在相乘时呈现某种幂律分布。因此随着时间的推移，你实际上会遇到收益递减。所以，你是对的。如果你想要获得双倍的能力，我不太清楚确切的定律是什么，但如果你想要双倍的能力，你确实需要 10 倍的参数。而如果你想再翻一倍，你就必须再增加 10 倍。也就是说，参数量需要从一万亿，到 10 万亿，再到 100 万亿。如果你想这么做的话，也许这并不是一个好的扩展方式。或许，与其去打造一个 100 万亿参数的模型……

<details>
<summary>Original English</summary>

**Speaker A**: >> yes that's a great question. So the question was you know models we're currently at one trillion parameters do we need to go to 10 trillion parameters or more for models to be even more capable? Um so the scaling laws does say that you know if you multiply the parameters and the data size um generally speaking this number if you increase the number you will get the models become more capable. So yes you can increase the parameters by 10 times and in general your performance will increase. Um however the view is there is going to be diminishing returns. Um I feel like you know it's not just the model size times the data set size. It's actually a ratio um some sort of like power law when you multiply them. So you actually get diminishing returns over time. So yes, you're right. If you want to have actually I'm not sure the exact law, but if you want to have double capabilities, you do need to 10 times the parameters. Um and then if you want another double, you have to 10 times it again. So it's 1 to 10 to 100 trillion parameters. um if you want maybe that's not a good way to scale. Um maybe instead you know instead of making a 100 trillion parameters
</details>

<!-- chunk 3/17 -->

### 下一个词预测的局限与未来

**Speaker A**: ……某种新的算法或新的架构或许能够解决这个问题。不过你说得对，如果你是一个实验室，你肯定想走捷径，所以最简单的办法就是直接堆出 10 万亿参数。但我还是想说，或许某种新算法会表现得更好。嗯，大家还有其他问题吗？请问。

<details>
<summary>Original English</summary>

**Speaker A**: ... some sort of new algorithm or new architecture could solve that problem. Um but you're right like if you're a lab you want to do something easy and so the easiest path is to just make a 10 trillion parameters. Um but I would say like you know maybe a new algorithm will be better. Um yeah any other questions? Yes.

</details>

**Speaker B**: 那么，您确实认为我们正在逼近下一个 token 预测（next token prediction）的极限吗？

<details>
<summary>Original English</summary>

**Speaker B**: >> So you do think that we are approaching the limitation of next token prediction.

</details>

**Speaker A**: 这是一个很好的问题。我想说，下一个 token 预测其实非常强大，因为人类语言本质上就是极具表达力的，而且它甚至不需要是人类语言。它可以是数学、是代码，你只需要去预测下一个词。而为了预测下一个词或 token，你需要掌握关于那个 token 或词的一切信息，对吧？就像 IA（此处可能是指 Ilya Sutskever，Ilia Satska）谈到的那样，他说过，你需要在模型内部构建一个世界模型（world model），才能去预测下一个词。所以我依然认为，下一个词预测还有很长的路要走。举个例子，你可以看看这张图，如果我们没有引入推理（reasoning），我猜它可能确实会停滞。但正是因为我们发现了这种新的方法论，也就是在下一个词预测的基础上通过推理来尝试进一步扩展，我们又重新回到了增长的趋势线上。我觉得主要的问题在于，如果不依赖下一个词预测，接下来会是什么？这是一个最根本的问题，我也不确定接下来会是什么。我觉得下一个词预测之所以如此强大，是因为它非常容易公式化，而且由于注意力机制（attention）同样非常强大，你可以利用这种特殊的注意力机制，并且它的训练效率非常高。所以，我不确定，我觉得关键问题就在于我不知道接下来会发生什么。我想研究人员现在可能都在挠头思考：在这之后，下一步该怎么走？嗯，是的。请问。

<details>
<summary>Original English</summary>

**Speaker A**: >> That is a good question. I would say that for next token prediction it's very powerful because you can essentially the human language is extremely powerful and it doesn't have to be human language. It can be you know maths coding you can just predict the next word and in order to predict the next word or token you need to know everything about that token or that word right so like I think IA was talking about like you know Ilia Satska he was saying like you know you need to have you need to make a weld model in the model in order to like predict the next word so I still think next word prediction still has a lot of way to go for example if you see this plot you know if we didn't have reasoning I guess okay maybe it would have plateaued But because we have discovered this new methodology you know reasoning and trying to like scale even more on next word you know next word prediction we have you know went back to trend um I feel like so the main question is if we don't have next word prediction what is next um that is the fundamental question most I mean I'm not sure like you know I'm not certain what's what's the next thing I feel like next word prediction is just extremely powerful because it's very easy to formulate and you can just like you know you can have like you know because attention is very powerful as well. You can have, you know, this special cause of attention mechanism and it's very efficient to train. So, I'm not sure I think the main question is I'm not sure what's next. Um, I guess researchers will like, you know, they're trying to scratch their heads, you know, what is next afterwards? Um, yeah. I I Yeah. Yes.

</details>

**Speaker B**: 追问一下。您觉得我们现在是不是处于和当年注意力机制刚问世时一样的时代？

<details>
<summary>Original English</summary>

**Speaker B**: >> Just a follow up on it. Do you feel like we are in the same era like how we attention came out?

</details>

**Speaker A**: 没错。就像注意力机制刚出现时那样，我们不知道接下来会发生什么。是的，这个追问很合理。你提到了它有点像 LSTM 或者是旧 AI 时代的情况。我们不知道之后会有什么新东西。嗯，这确实是个好问题。我觉得就像之前那个例子，对吧？在 GBD4（指 GPT-4）之后，大家只是在做预训练，做一些监督微调，一些 ROF（可能是指 RLHF），一些强化学习（RL），然后他们等了一整年才推出了 01 preview（可能是指 o1-preview）。在这长达一年的“战争迷雾”里，我们不知道接下来会是什么，研究人员也在四处摸索：我们是不是要加入推理过程？我们要不要把预训练做得更好？我们要不要把模型做得越来越大？他们尝试了所有这些实验，而推理似乎是最终胜出的那个。但我认为，主要的问题在于这条绿色趋势线能否继续保持下去。目前看来，它还在延续。一旦我们看到模型在智能和能力上开始出现瓶颈并趋于平缓，那么我们可能又会回到过去那种，比如整整一年的等待期。但就目前而言，这些模型似乎非常强大。所以，我不确定这个趋势是否会停止。我的意思是，如果你盯着这张图表仔细看，也许我们确实正在趋于平缓。或许我们不应该考虑那个 GBD 5.6“作弊”的例子，对吧？我们把它从图表中剔除。但你可以看到 GBD 5.6 Mythos，或者 4.6，它们似乎都开始趋于平缓了。所以也许……我不知道有没有人愿意打赌，也许模型的进展已经停滞了，但我们还不敢肯定。所以我们得再等上几个月看看。假设我们再等 3.5 个月，如果 3.5 个月后发现模型没有进步，那就说明确实停滞了。但是记住，我们只需要等 3.5 个月。如果那样，这个定律就会失效。事实上，如果你等上 7 个月，也就是两倍的时间，而模型只是沿着虚线发展的话，那么我们确实可以说它停滞了。那时候我也会同意，我们需要设计出新的东西，进行新的发明之类的。但就目前而言，现在看起来进展还是很顺利的。好。

<details>
<summary>Original English</summary>

**Speaker A**: >> Right. So, attention like we don't know what's next. Yes, that's a fair followup. So, um, you were mentioning how it's kind of like LSTMs or the old AI world. We don't know what's next afterwards. Um, that's a fair point. I feel like so like, you know, previously this example, right? So, after GBD4, it was just pre-training, some, you know, supervised fine tuning, some ROF, you know, some RL um, and they waited one year until 01 preview. So in this one year of fog you know the fog of war we don't know what what was next and so researchers you know were scrambling you know do we do the reasoning process do we make pre-training better do we make the model bigger and bigger and bigger you know they tried all these experiments um and reasoning was the one that won I guess um but I think like I think the main question is is the green trend going to continue at the current time it looks like it's continuing once we see models starting to taper out in intelligence, you know, in capabilities, then we'll go back to the, you know, olden days of like, you know, this one year waiting period. But I think for now, these models seem very powerful. Um, yeah. So, like I'm not sure if this will, I mean, if you look, okay, if you squint at the plot, I guess maybe we're tapering out. Maybe um let's not consider the GBD 5.6 cheating example, right? Let's remove that from the plot. Um, but you can see the GBD 5.6 Mythos, you know, 4.6. They're kind of all I guess they're kind of tapering. Um so maybe as a I mean I don't know if we someone wants to bet on this but you know maybe models have tapered out but we're not sure. So we shall wait a few more months and see. So let's wait 3.5 months. If we wait 3.5 months and see the models do not improve then we have tapered out. Um but remember we only need to wait 3.5 months. Um so then this law will fail. In fact, if you wait seven months, if you wait seven months, so double the time and models have, you know, just assume you know that dotted line that if if the models just follow the dotted line, okay, then we have tape it out. And I would agree that, you know, we'll have to design something new in, you know, make some new invention or something like that. Um, but for now, you know, for now looks like it's doing fine. Um, yeah.

</details>

### 开源与闭源模型对比

**Speaker A**: 好的，进入下一部分。我们的每个部分都可以提问，所以大家可以随便问。下一部分我们要讨论的是开源与闭源模型。Artificial Analysis 机构有一张非常酷的图表，展示了开源模型的性能。蓝线代表开源模型，而黑线代表闭源模型。大家可以看到，开源模型确实存在落后。随着时间的推移，开源模型无疑是滞后的。

<details>
<summary>Original English</summary>

**Speaker A**: Okay, next section. Um, so every single section we can have questions, so you can ask as many questions as you like. Um the next section we're going to talk about is open versus closed models. Um so artificial analysis has this very cool plot showcasing the performance of open source. So open source is the blue line. Um so open source is the blue line and closed source models is the black line. Um and you can see that open source does lag. You know open source definitely lags over time.

</details>

**Speaker A**: 另一个非常好的基准测试叫做 weird ML benchmark（此处可能是指 WildBench，按原文翻译）。它同样显示开源模型落后于闭源模型，图上蓝线是开源模型，绿线是闭源模型。大家可以看到，随着时间的推移——X 轴是模型发布日期，Y 轴是性能——开源模型一定程度上落后于闭源模型。为什么选择 weird ML benchmark 呢？我不确定大家是否真的了解它，为什么选它？看起来 weird ML benchmark 是一个非常好的指标，比其他基准测试更好。原因在于，我之前提到了那张关于推理的图表，绿线是推理模型，黑线是非推理模型，你能看到推理模型把性能翻倍所需的时间从 7 个月缩短到了 3.5 个月。但有趣的是，在 weird ML benchmark 上，这些推理模型实际上并没有表现得更好，也没有改变原有趋势，只是让成绩稍微好了一点点。因此，这个 weird ML benchmark 似乎更加稳健（robust）。这也正是为什么这个基准测试非常有用的原因。

<details>
<summary>Original English</summary>

**Speaker A**: Um another very good benchmark is called the weird ML benchmark. Um this also shows that open source models lag closed source models right the blue line is open source models the green line is closed source models um and you can see over time you know the x-axis is release date of the model and the y-axis is performance and you can see that open source models kind of lag close source models and why the weird ML benchmark I'm not sure if you folks actually know about this why the weird ML benchmark um it seems like the weird ML benchmark is a very good indicator better than other benchmarks and the reason the reason why is you know previously I mentioned you know previously this graph right reasoning the reasoning models are the green line and in the black models are the non-reasoning models and you can see that reasoning models double you know reduce the time of doubling time to 3.5 months previously it was 7 months um interestingly on the weird ML benchmark these reasoning models didn't actually do better it didn't actually change the trend um all it did was make slightly better. Um and so this weird ML benchmark seems to be more robust. Um and that is why you know this benchmark is very useful.

</details>

**Speaker A**: 事实上，如果你去看看 Twitter 上的讨论圈（Twitter verse），在 GLM 5.2（可能是指特定的大模型版本）发布之前，Twitter 上大多数人都说，哦，你知道 DeepSeek，如果仔细看，或者眯着眼睛看这张图——是的，眯着眼看，DeepSeek 和 Kimi 都在那边那个小角落里。那三大模型（three whales）是 DeepSeek、DeepSeek Pro（Flash？）以及可能叫 Max Mode 之类的版本，另外 Kimi 也在那里。所以在 GLM 5.2 发布之前，在 Twitter 圈子里，每个人都在说开源模型比闭源模型差得多，对吧？他们不仅仅是滞后，由于这个基准测试的结果，他们被认为差得多。

<details>
<summary>Original English</summary>

**Speaker A**: Um in fact if you go on the Twitter bus um before GLM 5.2 got released um most you know most of the Twitter people said oh you know deepseek you know deepse if you see very if you squint okay I think I have a plot. Oh yes if you squint deepseek and Kimmy are in that little corner over there. um you know deepseek those three models the three whales are deepseek you know flash deepseek pro I think one of them's max mode or something like that um and also Kim's over there as well so before GLM 5.2 two got released, you know, on the Twitter verse, everyone kept saying that open source models are much worse than closed source models, right? They're not lagging, you know, they're not just lagging, they're much worse because of this benchmark.

</details>

**Speaker A**: 事实上，如果你非常仔细地观察 weird ML benchmark，所有顶级的模型都来自闭源实验室，比如 Fable，比如 GPD 5.5 等等，所有的这些都非常清楚地表明，开源模型在这个基准测试中表现得并不好。直到 GPD 5.2（可能是某开源模型代号）的出现——图表上的 15 号是 GPD 5.2——它表明实际上开源模型又杀回来了。而且 GPD 5.2 多多少少震惊了世界。我想这就证明了开源并没有消亡。总体来说，这非常奏效，DeepSeek 和 GLF2 也展示了开源模型依然表现得很出色。

<details>
<summary>Original English</summary>

**Speaker A**: Um, in fact, if you look very closely of the weird ML benchmark, all of the top models are closed source labs, you know, like Fable, you know, GPD 5.5, whatever, you know, all of these are just very, you know, it shows very clear that open source models are not doing very well in terms of this benchmark. um until GPD 5.2 came along um you know number 15 is GPD 5.2 and it shows that actually open source has came back um and GPD 5.2 too kind of shocked the world. Um that you know I guess open source has not died. Um and you know deep yeah so in general this worked very well you know deepse you know GLF2 showed that you know open source does very well still.

</details>

**Speaker A**: 你还可以按国家来进行筛选。按国家筛选后你会看到，黑线代表美国，也就是美国的模型。深红色的线代表中国实验室的模型。当然也有其他实验室的模型，比如法国、韩国的实验室等等。但随着时间的推移，数据表明这些模型——美国实验室的模型长期以来表现得非常好，它们总是处于前沿位置；而中国实验室的模型则一直在努力追赶。之前我提到了，在 01 preview 发布前的那段停滞期。如果你仔细观察这个——

<details>
<summary>Original English</summary>

**Speaker A**: You can also filter out by country. So by country you can see that the black line is United States you know the US models. Um the dark red line is the Chinese labs. Um and you know there's other labs as well. um you know French, South Korean labs and stuff like that. Um but you know over time it shows that these models um you know the US labs seem to do very well over time. You know they they're always at the frontier and then the Chinese labs like to catch up over time. Previously you know I mentioned you know the um you know the plateau before you know before 01 preview got released. If you actually look at this

</details>

<!-- chunk 4/17 -->

### 开源模型与闭源模型的差距趋势

**Speaker**: 来看这张图表，这里有一个所谓的“开源差距”（open source draft）。在 o1-preview 发布之后，开源实验室并不知道该如何去复现它。他们以前从未接触过，也不知道“推理”（reasoning）到底是什么。这已经是几年前的事情了。但在 Twitter 上，你会看到 OpenAI 一直在谈论 o1-preview 有多强大。每天你都能看到他们的推文，展示 o1-preview 的强大实力。因此，大概有六到八个月的时间，开源模型和开源实验室都陷入了迷茫，不知道下一步该怎么走。不过，众所周知，后来 DeepSeek-R1 问世了。他们证明了，即便是对于开源模型，你也可以通过 GRPO（注：口误，可能指 GRPO 或类似算法）等强化学习方法来训练它们进行推理，而且效果非常好。

<details>
<summary>Original English</summary>

**Speaker**: plot um there is something called the open source draft. Um so after 01 preview got released open source labs did not know how to replicate 01 preview. They have never you know they don't know what is reasoning. So I'm not sure if you okay this is a few years back um but on Twitter you know open kept talking about oh you know 01 preview was extremely powerful um you know every single tweet you see every single day you know they show that 01 preview was very powerful. Um and so for one I think it was six months to eight months um open source models open source labs they got confused on what to do next. Um but then as everyone knows deepseek R1 came along um and they showed that even for open source models you can train these models to do reasoning gpo um reinforcement learning and it does very very well.
</details>

**Speaker**: 事实上，如果你看这张图表，就是用黑线减去蓝线，得出差值，就会得到现在的这张图。你可以从中看出开源模型落后了多少个月。随着时间的推移，你可以发现，在 o1-preview 发布之后，这个差距可以说是直线飙升。在当时，开源模型在能力上极其滞后于闭源模型。所以，当 DeepSeek-R1 发布时，开源实验室才恍然大悟：“原来我们也可以做类似 o1 的推理。” 这就是为什么最近闭源实验室和开源实验室之间的差距时间又开始缩短了。不过，这张图稍微有点过时了，大概是今年 5 月份的数据。随着 GLM-5.2 的发布，我认为现在的差距大概是四个月。所以，目前开源实验室落后闭源实验室约四个月的时间。

<details>
<summary>Original English</summary>

**Speaker**: In fact, if you take this plot, you know, the the black line minus the blue line, if you just minus it, you get this plot. Um, and you can see this is how many months behind open source is. Um, and you know, over time, um, you can see like, you know, after 01 preview got released, um, you know, it kind of skyrocketed. Um, you know, the open source models were very, very lagging in terms of, you know, behind closed source models. Um and so like when Deepseek R1 got released then the open source labs knew okay we can also do uh 01 type reasoning. Um and that is why recently you know the the time between closed source labs and open source labs have started decreasing again. Um yeah so this is slightly outdated. This is like May. Um so I think now it's actually four months with the release of GLM 5.2. It's around four months now. Um so open source labs lag behind closed source labs by around four months.
</details>

**Speaker**: 之前还有一张非常棒的图表，做了一些回归分析或趋势外推。根据那张图表的预测，如果把这种趋势延续到今年 12 月，开源模型将百分之百追平闭源模型。不过，谁知道呢？也许如果这个趋势继续下去，到 12 月我们真能拥有一款和最强闭源模型一样强大的开源模型。所以，我认为问题在于：这种趋势还会继续吗？关键始终在于趋势是否能延续。

<details>
<summary>Original English</summary>

**Speaker**: There was actually a very nice plot you know doing some sort of regression. So some sort of like trend extrapolation. Um according to this plot um if you extrapolate the trend by December this year open source models will 100% catch up to closed source models by this year December. Um but you know who knows I guess maybe maybe open source maybe we can have an open source model as powerful as the best closed source model by December um you know if this trend continues um so I guess the question is will the trend continue um it's always about will the trend continue
</details>

### 开源模型的蒸馏与训练方法

**Speaker**: 你们中可能有人知道，开源技术和能力的一些进步，是通过“蒸馏”（distillation）实现的。所以一些开源实验室喜欢做的，就是去调用那些前沿的闭源模型（比如 Opus 或 GPT），然后利用它们的推理轨迹（traces）来训练自己的模型。这是很多实验室普遍采用的方法。我不能说这是一种糟糕的方法，但这确实是一些闭源实验室所鄙视的。他们希望能阻止这种情况。他们的观点是：“我们不应该允许这些开源实验室这样训练，不劳而获地省下训练成本。”

<details>
<summary>Original English</summary>

**Speaker**: um and you know may most of you maybe may know that you know open source some of the open source improvements in technology you know improvements in capabilities are via distillation you know so some of the open source labs what they like to do is they like to call the models you know core the frontier models like opus or GPD and then use the traces to train your model um so this is a common methodology that labs like to do um I wouldn't say this is a bad method um but it is a method that you know some closed source labs like to look down upon you know they like to stop you know their view is you know we should not allow these open source labs to like do this training um and you know get away for free I guess in terms of training cost.
</details>

**Speaker**: 但实际上，你并不需要非得采用这种方法。大多数实验室在进行蒸馏时，通常有两种不同的途径。第一种方法是你需要获取 logits（逻辑输出），也就是你需要访问完整的对数概率日志。不幸的是，大多数实验室并没有这个权限，因为闭源实验室不可能把完整的 logs 给你。你能拿到的只有总结好的推理轨迹以及最终的输出结果。因此，这些开源实验室并不是简单地拿 Opus 的输出直接训练，那样太蠢了。他们的做法是，利用 GRPO 或强化学习来重新生成推理轨迹。因为你已经有了最终的输出，也就是答案，你只需要用 GPU 和强化学习来自动生成出推导过程。这就是他们训练这些模型的方式。所以你实际上并不需要获取模型的 logits 或权重，那不是必需的。

<details>
<summary>Original English</summary>

**Speaker**: Um but you don't actually have to do this approach. Um so most labs when you do distillation there are two different types of approaches. Um the first approach is you need to have the logits. You need to actually have access to the full logs. Um and unfortunately most labs do not actually have that right. So like labs will not give you the full logs. Um instead you only get the reasoning traces that are summarized um and the final output. Um, and so these, you know, these open source labs, they're not just, you know, they're not just training on the, you know, Opus output, right? That's just, that's silly. What they do is they use GRPO or reinforcement learning to recreate the traces. Um, and so because you you have the final output, which is the answer. All you need to do is use GPU and RL to create the reasoning trace automatically. Um, and so that's kind of how they train these models. Um, and so you don't actually need to like access the logits or the weights of the model. um that's not necessary.
</details>

### 动态量化技术与模型压缩

**Speaker**: 此外，大家知道，这些大型模型面临的一个最重要的问题是：随着模型变得越来越庞大，你已经无法在本地设备上运行它们了，运行起来极其复杂。因此，我们采用了一种叫做“动态量化”（dynamic quantization）的技术。基本上，就是你拿一个模型，将其量化到 1-bit。但这里的窍门在于，你不能把每一个层都量化成 1-bit，你需要保留一些重要的层，让它们保持在 16-bit 或是 8-bit 左右的精度。如果你把整个模型都量化到 1-bit，那你得到的准确率将会是 0%。但诀窍就在于动态量化。你看，如果这是一个 3-bit 的 DeepSeek 模型，你可以获得 75.6% 的准确率。而如果你使用动态 1-bit 量化，你可以获得 57% 的准确率。这表明，如果你采用聪明的策略进行动态量化，你是可以恢复准确率的。随着模型体积越来越大，这种方法将变得越来越重要。如果你画出帕累托（Pareto）效率曲线，你会发现，如果不使用动态量化，或者使用其他的动态量化方法，效果可能还行；但我们证明了，如果能智能地选择特定层进行量化，效果会更好。

<details>
<summary>Original English</summary>

**Speaker**: Um yeah, and you know, one of the most important factors of you know, these large models is, you know, as models get bigger and bigger and bigger, you can't run them on your local device anymore. Um it's extremely complicated to run. Um and so we do something called dynamic quantization where essentially you take a model, you quantize them down to one bit. Um but the trick is you don't quantize every single layer to one bit. you quantize some important layers to 16 bit or 8 bit or something like that. Um and so if you quantize the whole model down to one bit you will get 0% accuracy right 0%. Um but the trick is if you do dynamic quantization so if you look on the you know this is a three-bit Deepseek model um a three-bit one you get 75.6% 6% accuracy, a three-bit one. In fact, if you do dynamic one bit, um you get 57% accuracy. Um so we show that you know if you do something called dynamic quantization where you quantize the model down smartly, you can recover accuracy. Um and this methodology will become even more important when models get larger and larger and larger and larger. if you plot the paro you know efficiency um there if you don't do dynamic if you do you know some other dynamic quantization methods it does okay um but we showed that if you smartly choose the layers it does even better
</details>

**Speaker**: 我不知道大家有没有关注，我们针对 GLM-5.2 也发布了动态量化版本，并证明了 GLM-5.2 可以被非常好地量化。如果你们看这里，我想这是一个动画演示。哦，它能播放。大家可以看到这个 1-bit 的 GLM-5.2 模型的动画演示。而且这个 1-bit 模型的体积足足减小了 86%。相比原本 1.5 TB 的完整模型，它缩小了 86%，但依然在我们的一个提示词测试上表现得非常好。这说明模型并没有变傻。即使你让模型体积缩小了 86%，它并不会因此变傻 86%，可能只会损失 14% 的性能。这表明，如果你使用一些特殊的技巧来压缩模型，模型依然能运行得很好。

<details>
<summary>Original English</summary>

**Speaker**: um I'm not sure if you folks have followed but GLM 5.2 we also released dynamic quantizations for that we showed that GLM 5.2 2 can quantize very well. So if you look I think this is oh this is an animation. Oh it works. Um but yes you can show the animation you you can see the animation a one bit GLM 5.2 model and this is one bit um and the one bit model is literally 86% smaller. Um so it's 86% smaller than the full 1.5 terabytes. Um and it still managed to do very well on one of the prompts. Um so it shows that the models are not dumb. Right? If you make the model 86% smaller, it does not get 86% dumber. Um, it only gets 14% less dumb. Um, and so it shows that, you know, if you do special tricks to compress the model, the model still works very well.
</details>

**Speaker**: 我们还与 Opus 进行了比较，比如和 Opus 4.8 比较，也和 GPT-5.5 比较过。而且需要注意的是，对于 GLM-5.2，我使用的是高推理模式（high reasoning mode）。Opus 我用的是超高（extra high）模式，GPT-5.5 同样使用的是超高模式。所以你可以看到，这其中有着不同的推理模式，我们也可以一并观察。而且这些测试都是 zero-shot（一次成型）的，我们并没有反复去提示模型 50 次之类的，全部都是直接单次测试。好了，关于开源与闭源部分的讨论到此结束。大家还有什么其他问题吗？好的，请提问。

<details>
<summary>Original English</summary>

**Speaker**: Um, and we also compared to Opus, you know, we compared to Opus 4.8, we compared to GBD 5.5. And also, you have to notice that for G 5.2, I use high reasoning mode. You know, for Opus, it's extra high. And for you know GPD 5.5 is also extra high. Um and so like you know there are different reasoning modes as well which we can also um see. Um and all of these are oneshot um so we do not like prompt the model like you know 50 times or something. Um this is just one shot directly. Okay so the next I guess the open source versus close source section is done. I guess any other questions? Yes.
</details>

**Speaker**: 刚才的问题是，我们具体会把模型的哪些部分量化到更低位数，哪些保留较高精度。总体而言，我们在这方面做过大量的研究。如果你研究过 Qwen-3.5 的架构，你会发现有一些层叫做线性注意力层（linear attention layers）。线性注意力层绝对不能被量化。如果你将这些注意力层量化了，在处理长上下文时性能绝对会大受影响。因此，通常线性注意力层需要保留在 8-bit 或 16-bit。这就好比，如果再看其他的模型层，有些层则可以被深度量化到 1-bit。原因是这些层更像是填充层（filler layers），实际上并没有起什么作用。为了检验某个特定层是否真的有用，你需要一套校准数据集。你需要把一些具有代表性的数据输入到模型中，获取每一层之后的输出。然后你就可以观察：“这个模型在这一特定的层中变化大吗？” 如果变化不大，那或许就可以把这层直接量化到 1-bit；但如果变化非常剧烈，那你就要小心了，你不能把它量化到 1-bit 等等。实际上，我们发表了大量的博客文章和研究来讨论这些……

<details>
<summary>Original English</summary>

**Speaker**: Um so the question was which parts of the model do we quantize to lower bits versus higher precision. Um so in general um we did actually a lot of research on this. So if you look at the quen the quen 3.5 architecture there are some layers which is the linear attention layers. Um the linear attention layers should never be quantized. If you quantize the linear attention layers down you will definitely suffer in long context. Um so in general the linear attention layers need to be left in 8 bit or 16 bit. Um that's for example um another like if you look at the model layers um some layers can be quantized down heavily to one bit. Um and the reason why is because these layers are kind of like filler layers. Um and so they don't actually do anything. Um and in order to check whether a layer does something or not, you do need some sort of collaboration data set. So you need you need to have some sort of like representative data and pass it into the model um and you can get you can get the um outputs after each layer and then you can see okay does this model at this specific layer you know does it change that much um and if it doesn't change that much okay maybe just quantize a layer to one bed um but if it does change dramatically then you need to be careful um you you cannot quantize that down to like one bed or whatever um so there are actually many we actually publish a lot of like blog research on
</details>

<!-- chunk 5/17 -->

### 量化视觉层与模型能力

**Speaker A**: 我们展示过，我想也有过这样的展示，比如你不能对视觉层进行量化。如果你对视觉层进行量化，模型会变得非常糟糕。如果你给它一张，你知道，如果你给它一张火车的照片，它可能会说它看起来像一个海滩。因此，你绝不应该量化视觉层、音频层。只有语言模型层你可以尝试量化。为了实现这一点，有很多技巧。是的。

<details>
<summary>Original English</summary>

**Speaker A**: Um we show I think there was we also show for example you cannot quantize the vision layers down. If you quantize the vision layers down you will make the model really bad. Um if you give it a you know if you give it a picture of a train it will say it looks like a beach for example. Um and so it's you should never quantize the vision layers, the audio layers. Um and only the language the language model layers you can like quantize. Um but there are many tricks in order to do that. Um yeah

</details>

### 模型蒸馏与预训练技巧

**Speaker B**: 对。所以刚才的问题是，如果你进行蒸馏，你可能会在其他主题上表现得更差，但是只有当——比如你只用代码去蒸馏，它就只会在写代码上表现好，然后在其他方面变得非常笨。所以这是一个很合理的观点。我认为主要的技巧是，你需要使用非常非常多的样本。你需要调用这个模型大概，你知道，一千万次。所以技巧在于，一旦你调用中间模型一千万次，并且问题本身具有很高的多样性，一般而言，通过利用预训练的优势，模型在其他任务上也会表现良好。预训练之所以效果很好，是因为它已经学习了如此多的任务，以至于它可以填补缺失的空白。比如，如果你只是用数学问题来预训练一个模型，假设你只做数学，它可能不会表现得非常好，对吧？它在其他所有任务上也不会表现得很好。但是预训练的技巧在于，它涵盖了数学、编程、法律以及你能想象到的所有话题。正是因为它拥有如此多的知识，它填补了自身认知中的空白。因此，对于蒸馏，你也需要采取同样的方法。你需要进行采样，你需要进行充分的采样。比如，与其进行 10 万亿 token 的采样，你可以只采样比如 1%，然后调用模型。所以这基本上就是各大实验室目前的做法。

<details>
<summary>Original English</summary>

**Speaker B**: correct. So the question was if you do distillation um you you might have done worse on other topics um but you know only if you for example if you just do coding it will just do good encoding and then the rest gets very dumb. Um so that's a fair point. Um so I think that the main trick is you will need to do many many examples. You will call the model like you know 10 million times. Um and so like the trick is once you call the middle model 10 million times with high diversity of questions in general um by using the pre-training argument um the model will do well on other tasks. Um so the reason why pre-training does very well um is because it has learned so many tasks that it can interpolate the missing holes. Um for example, if you just train if you just pre-train a model with just maths questions um assume you do only maths. Okay, maybe it's not going to do very well, right? And it's not going to do very well on every other task. But the trick of pre-training is it does maths, coding, law, you know, every single imag, you know, every single topic you can imagine. And the trick is because it has so much knowledge, it feels the holes of the things that it doesn't know. Um, and so for distillation, you also need to do the same approach. You need to sample, you need to sample well. Um so for example instead of doing 10 trillion tokens sample you know like 1% um and then call the model. Um yeah so that's kind of how the labs are doing that.

</details>

### 模型剪枝与量化的权衡

**Speaker B**: 这是一个非常好的问题。所以，与其进行一次大规模的量化，你能不能对模型进行剪枝？比如，你知道的，完全删除某些层。一般来说，根据我们的研究，剪枝是有效的。但这里有一个非常大的问题：你需要重新训练模型。在剪枝之后，你需要持续训练模型，因为你已经删除了整整一层。如果你删除了一整层，你需要做比如 QAT（量化感知训练）或者进一步的微调，来推动其他权重获取更多知识。这就是如果你删除层会遇到的唯一问题。如果你不删除层，当你进行比如动态量化时——这被称为训练后量化（PTQ），如果只做量化的话，你根本不需要进行任何训练。但如果你去剪裁（prune）这些层，你就确实需要进行训练。所以这就是问题之一。是的。

<details>
<summary>Original English</summary>

**Speaker B**: Um that is a very good question. So instead of doing one big quantization can you instead prune the model like you know delete some layers entirely. Um so in general from our research pruning does work. There is a very big problem though. You need to retrain the model. you need to continuously train a model after pruning because you have deleted an entire layer. Um and so if you delete an entire layer, you will need to do like you know qat or further fine-tuning to push the other to push the other weights to have more knowledge. So that is the only problem where if you delete layers um if you don't delete layers when you do you know dynamic dynamic quantization it's called post training quantization. So PTQ you do not need to do any training at all. if you do you know quantization um but if you do prove the layers you do need to train um so that is one of the problems um yeah

</details>

### 开源与闭源模型的差距

**Speaker B**: 是的，这是一个很好的问题。所以问题是，因为开源实验室使用闭源模型进行蒸馏，它们之间的差距永远不会真正缩小到零。我对这一点部分同意。主要论点是，对于开源实验室来说，最简单的方法是进行蒸馏，但是，比如如果你是一个开源应用，你只会利用这种方法来首先进入市场。但作为长远之计，作为一种长期的安全网，你不会一直采取这种方法。相反，你会做比如生成答案、获取问题——例如，你会从大军（Scale）或其他什么地方获取数据，雇佣某种大规模的数据标注团队，我不知道。所以总的来说，因为目前有些实验室并不只是做蒸馏，对吧？他们不会仅仅去调用模型 10 万亿次，然后只做蒸馏。他们也会用自己的方法来扩充训练数据。我稍后可能会讲讲 GLM 的方法。但他们确实发明了一些新方法来做非常出色的强化学习和 GRPO。并且因为 GRPO 和强化学习是开源的，这些实验室只需利用这些方法就能让模型变得更好。因此，蒸馏只是训练系统的一部分。如果假设蒸馏消失了，好吧，也许开源实验室的进度可能会增加——你知道，可能不是落后四个月，而是落后八个月，但这没关系，因为我们总会有一些创新和新方法。DeepSeek 可能会发明一些新东西。因此像 GLM、Kimi（ki）所有这些，谷歌，甚至美国的开源实验室，他们都会有新的创新。所以我觉得，是的，如果你停止蒸馏，这会把四个月的差距拉大到八个月，但我依然觉得这没问题。这只是一种延迟，然后这种延迟最终会回到四个月左右。是的，好问题。

<details>
<summary>Original English</summary>

**Speaker B**: yes that's a great question so the question was you know because open source labs you know they use closed source models the gap will never actually go to zero um and so I partially agree and so the main argument was labs open source labs the easiest way is to do distillation however you know if you for example if you were an open source app you will only use that approach to firstly enter the market but as longterm you know as long-term safety as a long-term safety net you will not do this approach um instead as a you know instead you will do you know for example generate the answer get the question for example you know you will get data from a call or scale whatever you know have some sort of like large data labeling army or something I don't know um and so like in general because currently some of the labs so they don't just do distillation right so they're not just going to call the model 10 trillion times you know and just do distillation. They also augment the training data with their own approach. So I will be talking about the GLM approach maybe like later um but they did invent some new approaches to do very good reinforcement learning and GRPO um and because GRPO and reinforcement learning um you know is open source these labs just use these methodologies to make the models better. So you don't so distillation is only one part of the training system. Um and it's not I would say that assume distillation disappeared. Okay, maybe open source labs maybe increase you know it's not four four months maybe eight months um but but that's fine because you know we always have some sort of innovative and new approach you know deepseek might invent something new um and so like you know GLM ki all of them Google you know even the American open source lab they'll have some new innovation um and so like I think like yes if you stop distillation it will increase you know the you know four months to eight months but I still think that is fine Um it's just a delay you know and then the delay will go back to like four months. Um yeah good question.

</details>

### 动态量化的应用

**Speaker B**: 所以问题是，如果动态量化总是更好的，为什么人们不总是使用动态量化呢？这取决于动态量化的定义。对于每一个实验室，他们对动态量化都有不同的方法。事实上，我确实打算谈谈这个。我原本打算在基准测试和降低准确率那一节讲这个，所以我稍后会讲到。所以你的问题稍后会得到解答。好的。还有一个问题。是的，是的。

<details>
<summary>Original English</summary>

**Speaker B**: So the question is if dynamic quantization is always better why do people not always do dynamic quantization? Um so it depends on the definition of dynamic quantization. So for every single lab they will have different approaches to dynamic quantization. In fact, I'm actually going to talk about that. Um, I was going to talk about that in the benchmaxing and accuracy minimizing session. So, I'll be talking about that. Um, so I will your question will be answered later. Um, yes. Okay. One more question. Yes. Yes.

</details>

### 消费级显卡与小尺寸开源模型

**Speaker B**: 所以，刚才的问题是，对于消费级显卡来说，在参数规模、功能等方面，有哪些开源模型？在开源社区，最受欢迎的模型大概是 Qwen 3.6——呃，350 亿参数（35 billion），270 亿参数的 Gemma（GMA），你知道，Gemma 的 260 亿参数模型，GLM 4.7 Flash，这些最小类型的模型。我感觉这些小模型其实非常强大。我这里大概——等等，我好像没有图表——但从本质上讲，这些小模型最大的问题（哦，其实我也会讲到这个），这些小模型最大的问题是它们在工具调用上失败得很惨。因为它们存在工具调用问题，它们会无限循环。最大的原因就是它们太小了，这就是它们出现这些问题的原因。但我们可以解决这个问题。所以我稍后要讲的其中一点是，模型本身已经不再那么重要了，用来调用模型的测试框架或者工具才是最重要的事情。你如何实际去调用模型，这在最大程度上影响了模型的准确性，而不是模型本身。但我也会谈到这个。好的，我将继续。每个小节后总是会有提问。

<details>
<summary>Original English</summary>

**Speaker B**: So, the question was for consumer grade GPUs, you know, what are the open source models in terms of like, you know, the parameter size capabilities and stuff like that. Um, so for the open source community, you know, the most popular models are probably Quen 3.6 6 35 billion um 27 billion GMA you know Gemma's 26 billion um GLM 4.7 flash the smallest type models um and I feel like these small models are actually very powerful um so okay I don't have wait I don't think so I have a plot um but essentially these small models the biggest problem oh actually I'm going to talk about this as well the biggest problem of these small models are they fail very bad at tool calling because they have tool calling issues um they loop continuously um and the biggest problem is because they're small and that is why they have these problems um but we can counteract this um and so one of the things I'm going to talk about later is the model becomes not important anymore it's the harness or the tool that is actually the most important thing um how do you actually call the model um that actually affects the most accuracy of the model um so not actually the model itself um but I'll be talking about that as well um yeah okay I will continue on. Um, there were always questions after each section. Um, uh, yes.

</details>

### 吞吐量最大化与成本效益分析

**Speaker B**: 哦，是的。下一节，有趣的一节：吞吐量最大化（throughput maxing）。哦，其实我觉得我写错了，它应该是 2x 什么的。我不知道，无所谓了。吞吐量最大化以及……降低准确率。我本来以为是挖掘准确率（accuracy mining），但没这回事，所以目前就叫它降低准确率（accuracy minimizing）吧。是的。这部分我非常喜欢。我不确定你们能不能看清，稍微有点……算了。这里展示了模型成本的帕累托效率（parade efficiency）。X轴是成本，Y轴是竞技场得分（arena score）。所以这就像，你知道的，LMSYS Chatbot Arena（Ella Marina's arena）的得分。我非常喜欢这部分。因为我不太喜欢，比如你看到各个模型之间的竞技场得分。我不太喜欢那样，因为那样看起来非常不直观。相反，更好的做法是将每一个模型绘制在两根轴上：成本与准确率。你可以看到 Fable 表现得非常出色，对吧，Fable 在这张图上表现得非常非常好。但你可以看到这里有一个帕累托趋势，比如 Gemini 3.1 预览版在这里，Opus 4.6 也在那边。Fable 发布时也有一些其他模型。好吧，现在它被禁了。但不管怎样，当 Fable 发布的时候，当人们尝试它时，他们注意到在实际能力方面它并没有那么好。你可以看到，你可以看到。但是人们非常喜欢它的前端设计。你知道的，他们说……

<details>
<summary>Original English</summary>

**Speaker B**: Oh, yes. The next section, the fun section, throughput maxing. Oh, actually, I think I did. It's supposed to be 2x. I don't know. Whatever. Throughput maxing and and accuracy minimizing. I thought it was like accuracy mining, but there's no such thing. So, it's called accuracy minimizing for now. Um, yes. So, this part actually I really like. Okay. I'm not sure if you guys can see it's a bit oh whatever. Um this shows the parade efficiency of cost of the cost of the model. So cost is um cost is the x-axis. Um and the y-axis is the arena score. So this is like you know Ella Marina's arena score. Um and this part I really like. So I don't really you know maybe you see like arena scores you know Ella Marina scores between each model. I don't really like that. It's not it's not very easy to see. Instead the better approach is to plot every single model on two axes cost versus accuracy. Um and you can see Fable does very well right so Fable does very very well on that plot. Um but you can see there is a paro trend you know like Gemini 3.1 preview is over here you know Opus 4.6 is over there as well. There are some other models as well when Fable got released. Okay. Well, now it's banned, but anyways, when Fable was released, when you know when people tried it, they noticed that it's not that much better in terms of actual capabilities. Um, you can see, you can see, but however, people really liked the front-end design. You know, they said

</details>

<!-- chunk 6/17 -->

### 模型能力趋势与系统级衰减分析

**Speaker A**: 如果你调用过 Fable，你会发现它在 UI 和 UX 前端设计方面非常出色。事实上，如果你看看 LMSYS 排行榜（LM Mariners chart），你就能看出前端设计方面发生了巨大的变化。GLM-4（GLM 52）也在那里，你可以看到它是这一趋势的一部分。但总的来说，对于这些大型模型，它们在通用任务上的表现似乎不会有太大提升。然而在 UI 和设计方面，Fable 似乎做得非常非常好。所以你应该使用 Fable 来做设计、做 UI、UX，或者是 HTML、JavaScript 等等，但你可能不应该用 Fable 来做其他的任务，因为它非常昂贵。所以对于其他任务，还是用别的模型吧。不过这确实表明了 Fable 在 UI 和 UX 上表现极佳。

<details>
<summary>Original English</summary>

**Speaker A**: if you called Fable, it was very, very good for UI UX front end. Um and in fact if you look at the LM Mariners chart you can see it it was a very big shift in terms of front-end design. Um GLM 52 is also there if you can see you know it was part of the par paro trend. Um but in general for these large models they seem to have they're not going to be do they're not going to be doing that much better on general tasks. Um however for UI and designing Fable seems to have done very very well. Um, and so you should use Fable for your designing. You you should use Fable for designing, for UI, for UX, whatever, HTML, JavaScript, but you should probably not use Fable for the rest of the tasks because it is very expensive. Um, so you know, use some other models instead. Um, and you know, however, yes, okay, you know, some other models, you know, like, okay, this, you know, this shows that Fable does very well on UI and UX.

</details>

**Speaker A**: 但是随着时间推移情况如何呢？你知道，Anthropic 的观点是我们需要最大化吞吐量，同时也要最大化准确率，他们希望能服务更多的人。但有时候这事与愿违，有时候准确率反而降低了。所以你可以看到有一个……我不知道大家是否了解 Margin Labs，他们做的事情非常酷，他们在做 SWE-bench，他们用这些模型来给 Codex 和 Claude Code 做基准测试。这是这些模型随时间推移的准确率变化。虚线代表新模型的发布。其实在……等一下，鼠标在这里。我想大概是在这个位置，Fable 发布了。所以这里其实还有另一条虚线。你能看到一些非常有趣的趋势。第一个趋势是，每次有新模型发布，这个每日追踪的准确率似乎就会下降。所以如果你想预测 Anthropic 什么时候发布新模型，你可以把这个作为一个指标。这招非常准。对吧？基本上，当你在图表上看到这里时，这段很长时间内的准确率下降就是因为 Fable 发布了。然后这里，我想那是 Opus 4.8 吧。对，我想那是 Opus 4.8。这是 Opus 4.7，以此类推。那个大概是 4.6。具体我记不清了，但你还能看到准确率出现了巨大的滑坡。而且这不仅仅是一两天的波动，而是持续了很长一段时间。这也是 Codex 的情况。他们也做了 Codex 的基准测试。你同样可以看到随时间的变化。我不知道你能不能看清，但如果你把趋势画出来，你会发现其实 Codex 的表现越来越差了，对吧？我不知道你能不能看清，但如果你画一条线，它看起来确实在变糟。所以我猜测 OpenAI 也在调查这个问题。好的。

<details>
<summary>Original English</summary>

**Speaker A**: Um but how about over time um you know how what do you know anthropic their view is we need to maximize throughput right maximize throughput but also maximize accuracy um you know they want to like you know serve more people um but sometimes it doesn't actually work um sometimes they actually reduce accuracy um and so you can see there is a I don't know if you folks know margin labs um they have this very cool they do they do su bench they benchmark codecs they benchmark codecs and clawed code with the models. Um, and this accuracy over time for these models. Um, and the dotted lines are the release of the new models. Um, so there's actually another um, there was actually a dip in Wait, can you is there Oh, okay. The mouse is there. Um, I I think it was over here. Um, I think it was over here that feeble got released. Um, so there was actually another dotted line. Um, there was actually very interesting trends you can see. The first one is um every single time there is a new model release this this you know daily tracker seems to decrease in accuracy. Um and so if you want to predict when a model gets released from anthropic you can use this as an indicator um of when the model gets released. it worked very very well. Right? So like essentially if you were over here the dipped in accuracy over a very long period of time was because fable got released. Um and over here I think that's opus 4.8 I think. Um I think yeah I think that's opus 4.8. This is opus 4. Uh 7 and so on. That's 4.6 I think. I whatever um I don't remember exactly but um but you can also see that there is ginormous dips of accuracy. Um, and it's not just like one day or two days, it's for a very long period of time. This is also Codex. Um, so they also do codeex benchmarks. Um, and you can also see that over time. I don't know if you can squint, but you can see that actually Codeex has been getting worse if you plot the trend, right? If you can I don't know if you can squint, but if you draw a line, it seems to be getting worse. Um, so I'm assuming OpenAI is investigating this as well. Um, okay.

</details>

**Speaker B**: 所以这是一个不同的模型。这是 Codex。

<details>
<summary>Original English</summary>

**Speaker B**: >> So this is different model. This is codeex.

</details>

**Speaker C**: 所以这是在用 5.5 版本。

<details>
<summary>Original English</summary>

**Speaker C**: >> So this is using 5.5.

</details>

**Speaker D**: 这是在用……模型。

<details>
<summary>Original English</summary>

**Speaker D**: >> This is using
>> model.

</details>

**Speaker A**: 没错，是一样的。这个基准测试的做法是，你随机抽取 50 道 SWE-bench 的题目。SWE-bench 的题库非常大。所以你只需抽取 50 道题，然后调用模型来回答。接着你记录准确率。很显然，每天都会有日常的波动。哦，这种单日数据没那么有用，因为你只调用了 50 个问题。所以诀窍在于看趋势。而这个趋势……也许 OpenAI 应该调查一下这个。你可以看到 Anthropic 的趋势也非常不妙。总体来说……哦抱歉，这不是同一个模型。模型是会变的，我的错。所以测试框架是一样的，但模型变了。这条虚线是 GPT-4.5（GBD 5.5）。这里左边的全是 GPT-4.5。这里右边的则是 GPT-4.4。我想这块是 4.3。依此类推。但这看起来模型确实是在变差。所以我也不知道。这可能仅仅是在这个特定的基准测试上是这样，对吧？在 SWE-bench Pro 上它变差了。但你要知道，我其实不太会完全信任这些基准测试。最好的方法是去观察那些断崖式下降。比如，Codex 在这里出现了戏剧性的暴跌。我不知道为什么。还有 Claude Code 在这里或者这里的几周时间里表现非常糟糕，对吧。好。请讲。

<details>
<summary>Original English</summary>

**Speaker A**: >> Correct. It's the same. So what this benchmark does is you randomly sample 50bench questions. Sweet bench is very large. So you just sample 50 of them and then you call the model to answer it. Um and then you record accuracy. Um and so obviously you know every single day there's like you know daily variations. Oh, it's not it's not that useful because you're only calling 50 questions. Um, so the trick is to look at the trend. Um, and the trend uh h maybe open should investigate this. Um, and you can see the trend for you know anthropic is also not very good. Um, in general oh so sorry this is not the same model. Um, these models change my bad. Um, so it's the same harness but the model changes. Um, so this dotted line is GBD 5.5. Um, so everything over here is GBD 5.5. Everything over here is GBD 5.4. Um I think this is 5.3. Um and so on. Um but it seems like the model's getting worse. So I don't know. This is probably just on this benchmark, right? On the Sweet Bench Pro benchmark, it's getting worse. Um but you know, I wouldn't really trust these benchmarks. The best way is to look at the degradation. You know, the sudden drops. You know, for example, Codex dramatically dropped over here. I don't know why. Um and you know clawed you know clawed code was very bad for a few weeks over here or over here right. Okay. Yes.

</details>

**Speaker A**: 是的，这其中有置信区间。我没有把它画出来，因为只有 50 个任务。每天他们就是随机调用 50 个任务。所以他们会采样 50 个任务。因此你不应该看每日的数据。这里画的是每日数据。意思是每天测 50 题，然后另一天 50 题，再 50 题，以此类推。相反，你应该看滑动平均值，比如做个 7 天滑动平均之类的。那是一个更可靠的数字。对。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yes there is a confidence interval. I did not plot it but this is 50 tasks. So every single day they call a 50 tasks randomly. So they will sample 50 tasks. Um and so you you should not look at this daily. This is daily. So every single day is 50 questions. Another 50 questions. another 50 questions and so on. Instead, you should do like a rolling average, you know, some sort of rolling, you know, 7-day average. Um, that's a better number. Yeah,

</details>

**Speaker B**: 真的。我从这里都能看出来。它就像是在不断下降。

<details>
<summary>Original English</summary>

**Speaker B**: >> really. I can see it from here. It's like decreasing.

</details>

**Speaker A**: 它确实是……如果你看……如果你做 7 天滑动平均的话，我晚点大概会把那个图拿出来。它实际上是在下降。你可以看到……如果你看那些最高的峰值，你看看顶部的峰值，那些峰值正在降低。

<details>
<summary>Original English</summary>

**Speaker A**: >> It's it's
>> if you look at the if you do the seven moving average, I I'll probably get the pot later. It actually is decreasing. You can see it um if you can see I don't know if you look at the top peaks of the you look at the top peaks and the peaks are decreasing.

</details>

**Speaker B**: 好的，那么低部的谷值呢？

<details>
<summary>Original English</summary>

**Speaker B**: >> Okay, how about the bottom peaks?

</details>

**Speaker A**: 好的，我承认这里有随机噪音。所以诀窍是你需要看滑动平均，如果你看滑动平均图，你能真切地看到它在下降。我稍后会把图拿出来。你们可以去搜一下。去 Margin Labs，搜索 Margin Labs Codex Claude Code benchmarks，他们确实展示了每周的趋势。但我说这些不是为了证明模型越来越差了。这仅仅是为了展示模型的准确率确实会出现那种断崖式的下跌。问题是为什么？比如，为什么 Claude Code 在某几周里的性能会下降？为什么会这样？这才是最根本的问题。这就引出了一种理论。该理论认为他们可能出现了意外，在模型发布前他们正在做测试，所以他们可能把一些查询请求路由到了 Opus 4.8 或者是 Fable 或是其他的什么模型上。但问题是他们并没有这么做。主要问题是，就算你真的路由到了新模型，为什么准确率会下降呢？按理说它应该变得更好才对。所以其中一个理论，理论一是，他们忘了修改系统提示词（system prompt）。Fable 的系统提示词是不一样的，但他们给 Opus 4.8 用了错误的系统提示词，这就是准确率下降的原因。然后等模型正式发布后，准确率又回升了，因为他们用回了正确的系统提示词。这是一种理论。

<details>
<summary>Original English</summary>

**Speaker A**: >> Okay, I agree there is random noise. So the trick is you need to the moving average and if you look at the moving average you can actually see it's decreasing. I I'll probably I'll get the plot later. Um you can you can search it. It's so go to Margin Labs, search in Margin Labs codeex claw code benchmarks and they do show weekly the weekly trend but I'm just saying this is not this is not to say that the model is getting worse. This is just to show that accuracy that you know the sudden dips the accuracy of these models can decrease. Um and the question is why you know for example why did claude code over a few weeks why did the performance decrease like why that's the fundamental questions. So that is one theory. A theory is they might have accident you know that before the model release they are doing testing and so they might have like you know act you know some of the some of the queries they route to opus 4.8 eight
>> or fable or whatever. And the problem is they did not. So the main question is if you do route to another model, why did the accuracy decrease? It should actually get better. And so one of the theories is theory one, they forgot to edit the system prompt. And so the system prompt for Fable was different, but then they used the wrong system prompt for, you know, for Opus 4.8, and that is why the accuracy decreased. Um and then after the model got released the accuracy went back up because they used the correct system prompt. That is one theory.

</details>

**Speaker A**: 另一种理论是……好吧我们待会儿其实会讲到这个，那就是他们实际上在搞一些花样。比如他们做了量化，但没有做动态量化。他们做了一些很蠢的量化。或者有些 GPU 坏了，比如他们用错了 GPU。有些 GPU 可能会出现比特翻转之类的问题，谁知道呢。或者他们建了一个新数据中心，而恰巧那个数据中心的准确率就是偏低。事实上，这确实发生过……好的，我其实正要讲这个。总之有很多很多种理论，很多种可能性可以解释为什么准确率会下降。其实我觉得就在下一张图里。对，就是下一张图。或者接下来的几页幻灯片。实际上，这是什么时候的事？我记不清了。几个月前吧。AMD 的人实际上在准确率暴跌期间，在 Claude Code 上提了一个 issue。我记得是在那次准确率大幅下降之前，他们直接问了 Claude 团队：“为什么准确率出现了明显的下滑？这是怎么回事？” 后来 Claude 方面在 2023 年 4 月写了一份报告，详细说明了他们准确率下降的原因，对吧？所以他们对 Claude 发生的事情做了一次事后复盘。原因是因为那个思考轨迹（thinking trace）在第二次之后被删除了，你知道，当你当你提问的时候……

<details>
<summary>Original English</summary>

**Speaker A**: Um the other theory is the other theory is okay we're actually going to talk about this is it's actually they're doing tricks. You know they did quantization but they didn't do dynamic quantization. They did some dumb quantization. Um you know they some GPUs are broken for example. You know they use the wrong GPUs. Some of them have like you know bit flips or something. I don't know. um they have like a new data center and then that data center just by chance has lower accuracy. Um in fact there is actually okay I'm going to talk about this actually. Um yeah but there are many many theories like you know possibilities why this could reduce an accuracy. Um actually I I think it's the next plot. Yes the next plot. Um oh well the next slides. Um so actually when was this? I don't remember. Um it was a few months ago. Someone from AMD actually made an issue on chord code you know during this dip. I think it was during the before um a very large dips in accuracy and they actually asked Claude, you know, they asked the Claude team, why is there a noticeable dip in accuracy? You know, why why is that? And Claude actually wrote a in April 23, they actually provided details on why they had reduced in accuracy, right? So they did a postmortem on what happened with Claude. Um and the reason why is because the thinking trace got deleted after the second you know when you when you ask

</details>

<!-- chunk 7/17 -->

### 工具链与推理提供商对准确率的影响

**Speaker A**: 第二次的时候，思考痕迹（thinking trace）被删除了，并且它使用了一个糟糕的系统提示词（system prompt）。他们发现这就是准确率下降的原因。不知何故，在 Claude Code 中，当你第二次提出问题时，之前的思考痕迹就会被抹除。我甚至不知道他们是怎么没发现这个问题的。但根据他们的说法，Claude 现在有了这个内部基准测试（internal benchmark），所以他们会使用更多的内部调查来测试，确保下次如果有新模型，这种情况不会再发生。这些事情随着时间的推移确实会发生。对于 Claude Code 这个具体例子来说，工具链（harness）本身才是问题所在，而不是实际的模型。在工具链中，思考痕迹被删除了，而且他们的系统提示词也不是很好。这就是准确率实际下降的原因。

<details>
<summary>Original English</summary>

**Speaker A**: The second time, the thinking trace got deleted and it had a bad system prompt. They found out that that was why the accuracy got degraded. Somehow in Claude Code, the second time you ask a question, the previous thinking trace got erased. I don't even know how they did not find this, but oh wow, according to them, Claude now has this internal benchmark, so they will use more internal investigations to test that next time if there's a new model, this won't happen ever again. These things do happen over time. For this specific example with Claude Code, the harness itself was the problem, not the actual model, right. The harness, the thinking trace got deleted, and they had a not very good system prompt. And that is why the accuracy actually degraded.

</details>

**Speaker A**: 所以我们找到了这些模型变差的一个原因。在 2025 年 9 月，他们也指出这实际上是由于硬件问题。在他们的编译器中，他们使用了 TPU。Anthropic 喜欢同时使用 TPU 和 GPU。他们表明，相同的软件栈在 GPU 和 TPU 上实际上产生了不同的结果。对于 TPU，它使用了不同的采样（sampling）；而对于 GPU，则是一个不同的采样机制。这就是为什么他们在 9 月份的某个时候准确率下降的原因，因为他们实际使用了不同的硬件。一旦你有了不同的硬件，准确率也会随之改变。

<details>
<summary>Original English</summary>

**Speaker A**: So we found one answer why these models got worse. They also released in September 2025, right in September 2025 they showed that it was actually due to a hardware problem. So in their compiler they used TPUs. Anthropic likes to use TPUs and GPUs. They showed that the same software stack for GPUs and TPUs actually produced different results. And so for the TPUs it actually was different sampling. And for the GPUs it was a different sampling mechanism. And so that is actually why they had decrease in accuracy during September sometime. Because they actually had different hardware. And so you need to, like, once you have different hardware accuracy also changes.

</details>

**Speaker A**: 所以我认为最关键的一点是，工具链、实现方式、工具现在是最重要的。重要的不再是模型，单纯的模型是没有用的。如果你观察开源模型和闭源模型，模型本身通常是一样的。区别在于 Claude Code 是如何构建的，或者 Codex 是如何构建和使用的。这实际上是最重要的因素，不再是模型本身了。正如我们所看到的，如果他们不小心搞砸了工具链，准确率就会降低。对于大型实验室来说，我确信他们知道这些问题，并且正在努力解决。但我觉得这些问题仍然非常难以修复。

<details>
<summary>Original English</summary>

**Speaker A**: So I think the main point is the harness, the implementation, the tool is now the most important. It's not the model, right, the model is useless. Most models you know, if you look at open source versus closed source, models are generally the same. The difference is how Claude Code is made, you know how Codex is made and used. And so that is actually the most important factor. It's not the model anymore. And so like you know, as we have seen, if they accidentally botched the harness, you will get reduced accuracy. And so definitely for large labs, I'm sure they know these problems and they're working on it. But I feel like these are still very hard to fix.

</details>

**Speaker A**: 希望我回答了大家关于工具链和准确率的一些问题。准确率下降是有实际原因的，但这不仅仅发生在闭源实验室，在开源模型提供商之间，准确率同样会发生变化。如果你看这张来自 OpenRouter 的图表——这是 DeepSeek v4 Pro——大多数推理提供商（inference providers）想要做的是以最便宜的价格为你提供最高的吞吐量（throughput）。他们想给你每秒 60 个 token、120 个 token 甚至 1,000 个 token，对吧？他们想给你最快的速度。但是人们真的花心思去检查准确率了吗？这是一个根本性的问题。你可能获得了每秒 10,000 个 token 的速度，但实际上毫无模型能力可言。所以主要的问题是，你需要对从这些推理提供商那里使用的东西保持谨慎。对于 DeepSeek v4，OpenRouter 运行了两个基准测试。我认为它是按照 Tau-bench 排序的，而绿色的那个是 GPQA。你可以看到，总体而言，一些推理提供商的表现并不好。所以在你使用开源模型之前，请务必先检查准确率。

<details>
<summary>Original English</summary>

**Speaker A**: Hopefully I answered some of people's questions on the harness, you know, the accuracy. So there's actually reasons why accuracy got degraded, but you know it's not just closed-source labs; across open-source model providers the accuracy changes. So if you look at this plot, this is from OpenRouter, this is DeepSeek v4 Pro. Most inference providers, what they want to do is they want to serve you the highest throughput, right, with the cheapest price. They want to give you, you know, 60 tokens, 120 tokens, 1,000 tokens per second, right? They want to give you the fastest. But did people actually bother to check accuracy? So that is the fundamental question. You might be getting 10,000 tokens per second and there is no model. So the main question is you need to be careful of what you use from these inference providers. And so for DeepSeek v4 you know there are two benchmarks which OpenRouter ran. I think it's sorted on Tau-bench, and the green one is GPQA. And you can see that in general some of the inference providers are not doing very well. So before you use an open source model, please check the accuracy.

</details>

**Speaker A**: 另外最大的问题之一是，例如对于 Claude Code 和 Codex，你可以随着时间推移对其准确率进行基准测试。闭源实验室的好处是他们控制着供应链。而开源的最大问题是，这些模型有太多的供应商和提供商，以至于有时人们会对开源模型表现不佳感到反感和恼火。生态系统中的每个人都在说闭源实验室比开源做得好得多，但这并不是因为模型本身，而是因为推理提供商。这要归咎于推理提供商，他们正在导致开源的衰败，因为他们在给开源抹黑。所以我建议你检查一下你最喜欢的推理提供商。这个基准测试是昨天由 OpenRouter 运行的，所以这是 OpenRouter 的每日数据。

<details>
<summary>Original English</summary>

**Speaker A**: And also one of the biggest problems of this is every single time, you know for example with Claude Code and Codex, you can benchmark accuracy over time. And the good thing about closed source labs is they control the supply chain. The biggest problem of open source is there are so many suppliers and providers of these models that sometimes what happens is people get turned off and they get very annoyed that the open source models do not work very well. So everyone in the ecosystem keeps saying that closed source labs do much better than open source, but it's not because of the model, it's because of the inference provider. The inference provider is to blame that they are causing the downfall of open source because they're giving a bad name for open source. So I would check whatever favorite inference provider you have. This benchmark was run I think yesterday by OpenRouter, so this is daily data by OpenRouter.

</details>

**Speaker A**: 所以无论你最喜欢哪家推理提供商，请告诉他们不要把准确率降低那么多。这是 GLM 5.2。GLM 5.2 同样显示出不同的准确率。你可以看到右边的图表显示，大多数推理提供商都在“追求吞吐量最大化（throughput maxing）”，但同时也在“准确率最小化（accuracy minimizing）”，这就是这个说法的由来。他们其实并不关心，你看，最高的准确率是 76.4%，而最低的是 62.4%。最高准确率和最低准确率之间存在差距。所以，在这里我要对推理提供商们呼吁：在尝试提升速度之前，请先提高准确率。你总不想让一个模型变得非常愚蠢，只是跑到每秒 10,000 个 token。我们甚至可以把它做到每秒 100 万个 token，然后根本没有模型在运行——直接找个人类或者造个假就行了。所以最主要的一点是，我们需要推理提供商在准确率方面表现出色，否则这会让开源生态显得非常糟糕。这就是第二部分的结尾，我想这有点像是在发牢骚。关于这部分还有其他问题吗？请问。

<details>
<summary>Original English</summary>

**Speaker A**: So whatever favorite inference provider you have, please tell them not to, you know, reduce accuracy that much. This is GLM 5.2. So GLM 5.2 as well shows different accuracies. You can see the plot on the right shows most inference providers are throughput maxing, but they are accuracy minimizing, that's where the phrase comes from. So they do not care about—in fact, look, the highest accuracy is 76.4% and the lowest is 62.4%. So there is a 10% gap between the highest accuracy and the lowest accuracy. And so as a call out to inference providers, you know, please increase accuracy before trying to make things faster. You do not want a model to be very dumb and it's like 10,000 tokens per second. We can make it 1 million tokens per second and there is no model—just call a human or make a fake or something. So the main point is we need inference providers to do good in terms of accuracy, otherwise this will make open source have a very bad look. Oh okay, that's the end of the second section. I guess that was a bit of a rant. Any other questions for this? Yes.

</details>

### 如何在企业中部署开源模型

**Speaker B**: 对于一个想要使用开源模型的新组织，你是建议他们使用推理服务提供商，还是建议从 Hugging Face 下载，然后使用模型或者某种服务器自己进行部署？如果有新组织来问你如何使用开源模型，你会怎么建议？

<details>
<summary>Original English</summary>

**Speaker B**: For a new organization that wants to use like the open source model, do you suggest using an inference service provider, or do you suggest downloading from Hugging Face and then using like model or some kind server to implement yourself? Like what do you suggest if any new organization comes and asks you like how do you use open source model?

</details>

**Speaker A**: 这是一个很好的问题。当一个开源模型发布时，在准确率、吞吐量等方面，你应该如何使用它？总的来说，开源已经取得了长足的进步。例如，我们确实报告过 Gemma 1、Gemma 2、Llama、Mistral、OpenGPTs 中的 bug，这些模型每一个都有 bug。好的一面是，我们会在实验室发布模型之前帮助他们修复一些问题。所以你们现在使用的每一个模型都包含了我们的一些修复。这是一件好事。但总的来说，如果你有一个开源模型，我会建议使用 Llama CPP。我认为 Llama CPP 和 Llama Server 可能是最没有 bug 的系统。所以我建议，是的，你应该从 Hugging Face 下载。使用 Llama Server、Llama CLI，或者你可以使用 LM Studio，无论你最喜欢什么工具。但是的，你应该从 Hugging Face 下载。如果你们是一家大型企业，一般来说，他们喜欢做的是等待一周。大多数企业会等待一周，等所有问题都修复了，然后他们再使用这个模型。但在我看来，这不是一个好方法。如果每个人都等一周，那我们怎么修复 bug 呢？因为只有在大规模使用时，我们才能发现这些 bug。总而言之，我们需要大家尽早开始尝试这些模型，而不是等待一周或一个月。

<details>
<summary>Original English</summary>

**Speaker A**: That's a great question. So when an open source model gets released, you know, how should you use it in terms of accuracy, throughput, or whatever? So in general, open source has come a long way. So for example, we did report bugs in Gemma 1, Gemma 2, Llama, Mistral, you know, OpenGPTs—every single one of those models had bugs. And so the good thing is, we will help the labs before they release a model to fix some of the issues. So every single model you now have has some of our fixes. So that's a good thing. But in general, if you have an open source model, I would use Llama CPP for example. I think Llama CPP and Llama server is probably the most bug-free system. So I would suggest yes, you should download from Hugging Face. Use Llama server, use Llama CLI, you can use LM Studio, whatever is your favorite tool. But you should, yes, you should download from Hugging Face. In terms of like, if you're a large enterprise, generally speaking, what they like to do is they like to wait one week. So most enterprises, they'll wait one week for all the problems to be fixed. And then they will use the model. But in my view, that is not a good approach. I would say if everyone waits one week, then like how do we fix the bugs? Because only at scale, then we can see the bugs. And so like in general, we need everyone to start trying these models earlier, and not like wait one week, wait one month, you know.

</details>

<!-- chunk 8/17 -->

### Model Performance Degradation Before Release

**Speaker A**: 不要采取等待的策略。不过我想说，通常企业倾向于做的就是只等待一周。嗯，是的，这就像是常规做法。嗯，是的。

<details>
<summary>Original English</summary>

**Speaker A**: don't do the waiting approach. Um but I would say like in general the enterprises what they like to do is just wait one week. Um yeah that's like common practice. Um, yes.

</details>

**Speaker B**: 那么，好的，问题是为什么模型在发布前性能会下降？嗯，这些只是假设性的问题，假设性的理论。所以，每一个模型都有不同的系统提示词 (system prompt)。那么，Opus 4.8，Opus 4.8 的系统提示词非常短。但是，Opus 4.7 的系统提示词则极长。嗯，所以理论上，这只是一个理论，即 Anthropic 通过 Claude Code 意外地将一些模型路由到了 Opus 4.8，对吧，他们使用 Opus 4.8 进行测试，对吧，他们需要测试 Opus 4.8。但是他们使用了 Opus 4.7 的系统提示词。因此他们使用了错误的系统提示词，这就是准确率下降的原因。这是一种理论。嗯，另一种理论其实，我想那就是……其实我想了一下。那可能是我唯一的理论。我还在想，嗯，还有其他的理论吗？嗯，

<details>
<summary>Original English</summary>

**Speaker B**: >> So, okay, the question was why would the model performance degrade before a model release? Um, these are just hypothetical question hypothetical theories. So, every single model has a different system prompt. So, opus 4.8 8 Opus 4.8 system prompt is very short. Um but Opus 4.7 system prompter was extremely long. Um so the theory was this is just a theory that anthropic via claude code accidentally routed some of the models to Opus 4.8 right they use opus 4.8 as testing right they need to test opus 4.8 But they used Opus 4.7 system prompt. So they used the wrong system prompt and that is why accuracy degraded. That's one theory. Um, another theory is actually I think that's the actually I thought about it. That's probably the only theory I had. I'm like thinking hm is there another theory? Um,

</details>

**Speaker A**: 我猜测试框架 (harness) 本身，就像你知道的，有时候测试框架本身是为了 Opus 4.7 设计的。嗯，当他们准备发布 4.8 时，他们需要校准测试框架，对吧？他们需要更改测试框架，嗯，为了 4.8 能够工作。但问题是，你不被允许发布它，对吧？你不被允许发布它并把它交给人们，因为否则人们就会，你知道，跑到 Twitter 或 LinkedIn 上，你知道，到处说，“哦，我能看到 4.8 就要发布了。”你知道，每个人都会尖叫，你知道，“4.8 来了。4.8 被发布了。”所以也许这就是为什么准确率下降了。就是他们没有更新测试框架。嗯，或者另一个选项是，他们已经……他们悄悄地……他们在模型发布前悄悄更新了测试框架，然后它倒退了，你知道，它降低了准确率。嗯，我不知道，说实话，我觉得你可能应该去问 Anthropic 这个问题。嗯，或者，但我认为总的来说，性能下降并不总是对应着新模型的发布。有些下降是实际存在的问题，比如，你知道的，思维链 (thinking trace) 被删除了。嗯，系统提示词他们写错了，我觉得对于系统来说很有趣，我认为对于系统提示词，他们说……他们试图减少冗长，所以他们试图让模型少说话。嗯，结果这实际上让模型变得更蠢了。嗯，所以我认为这只是一个词，他们加了一个词……不，是一句话，我认为系统提示词里的一句话让模型变蠢了。嗯，是的，我不知道这是否有帮助，但我不知道其他人是否还有什么理论。我不……我不认为有任何人能对这件事有那么多理论。嗯，显然 Anthropic 的工程师会知道，但我，你知道，他们是不会说的。所以，这完全基于假设。可能与系统提示词有关，可能与测试框架有关。是的。但我认为总的来说，你也可以利用这张图表。你知道，如果性能下降了，很可能就意味着一个新模型即将到来。嗯，是的。还有其他问题吗？好的。

<details>
<summary>Original English</summary>

**Speaker A**: >> I guess the harness itself like you know sometimes the harness itself the harness was was designed for Opus 4.7. Um and during when they were going to release 4.8, they need to collaborate the harness, right? They need to change the harness um for 4 4.8 to make it work. But the problem is you're not allowed to publish it, right? You're not allowed to publish it and give it to people because otherwise people will like, you know, go into Twitter on LinkedIn, you know, everywhere. Oh, I can see 4.8 is going to be released. You know, everyone's going to be screaming, you know, 4.8's coming. 4.8's, eights, you know, were getting released and so maybe that's why accuracy decreased. It's they update they did not update the harness. Um or the other option is they up they already up they silently they silently updated the harness before the new model got released and it regressed you know it reduced accuracy. Um I don't know like to be honest I you should probably ask anthropic that question. Um or but I think in general in general the dips the dips don't always correspond to like new model releases. Some of the dips are actual issues like you know the thinking trace got deleted um the system prompt they wrote a wrong I think for the system it's funny I think for the system prompt they said um they tried to reduce verbosity so they tried to make the model less talkative um and it actually made the model dumber um and so I think it was just one word they added one word no one sentence I think one sentence in the system prompt that made the model dumber Um, yeah, I don't know if that helps, but I don't know if anyone else has any like theory. I don't I don't think so anyone even has that many theories on this. Um, obviously the anthropic engineers will know, but I, you know, they're not going to tell. So, it's just based on hypotheticals. Something to do with the system problems, something to do with the harness. Yeah. But I think in general, you can also use this plot. You know, if the performance decreases, most likely a new model is going to be coming. Um, yeah. Any other qu? Yes.

</details>

**Speaker B**: 只是补充一点。

<details>
<summary>Original English</summary>

**Speaker B**: >> Just to add on that

</details>

**Speaker A**: 是的，没错。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, correct.

</details>

**Speaker B**: 没错。

<details>
<summary>Original English</summary>

**Speaker B**: >> Correct.

</details>

**Speaker A**: 是的。完全正确。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yes. Exactly.

</details>

**Speaker B**: 完全正确。所以在模型发布之前，他们为那个新模型、为旧模型使用了不同的系统提示词。所以这可能就是为什么准确率会有一些下降的原因。他们切换了系统提示词或者类似的操作。嗯，还有，你知道，模型本身，你知道，我认为 4.8 的系统提示词非常短。嗯，它是，是的，我认为它是非常非常短的，而 4.7 则是极其庞大的。嗯，原因在于 4.7 就像，你知道，我不知道，我不知道发生了什么，但他们有这个极其庞大的系统提示词，而 4.8 只是把它大幅缩减了。嗯，所以也许，也许他们使用了 4.7 的系统提示词，我不知道，或者 4.8 的系统，4.8 的短系统提示词，然后他们把它用在了 4.7 上，这就是它准确率下降的原因。我不知道。嗯，但是是的，你是对的。嗯，他们确实发布了，虽然我认为他们在网站上发布的系统提示词是给 Claude.ai 的。也就是在线聊天系统，嗯，Claude Code 的系统提示词其实是不同的。

<details>
<summary>Original English</summary>

**Speaker B**: >> Exactly. So before a model release, they use a different system prompt for that new model for the old model. And so that is probably why there are some decrease in accuracy. they switch the system prompts around or something like that. Um and also you know the model itself you know I think 4.8 system prompts is very short. Um it's yeah I think it's like very very short and 4.7 was ginormous. Um and the reason is 4.7 was like you know I don't know what I don't know what happened but they have this ginormous system prompt and the 4.8 just shrunk it a lot. Um so maybe maybe they used the 4.7 system prompt I don't know or 4.8 system the short system prompt for 4.8 eight and then they use it for 4.7 and that's why it decreased accuracy. I don't know. Um but yeah, you're correct. Um they do release although I think the system prompt they released on the website is for claw.ai. So the online chat system um the clawed code system prompt is actually different.

</details>

### Benchmarking and Cheating

**Speaker A**: 是的。所以我想你需要实际调用，你需要调用 Claude Code，你知道，问“我的系统提示词是什么”，然后你把它打印到一个文本文件里，嗯，然后你就可以去调查系统提示词是什么了，如果你愿意的话，你还可以覆盖它，嗯，是的，但这很可能是一个不同的系统提示词。嗯，是的，如果没有人有最后一个问题的话，好，继续。好的，下一部分我们将要讨论的是基准测试和作弊 (benchmarking and cheating)。嗯，我不确定在座的各位是否看过 Deep SWE 基准测试。嗯，Deep SWE 基准测试是最近一个非常受欢迎的基准测试，它显示，你知道，成本在 X 轴，Y 轴就是 Deep SWE 基准测试。这是一个新的基准测试，基于，你知道的，一个更好、未受污染版本的 SWE-bench Pro。嗯，总的来说你可以看到，你知道，GBD 5.5 在 Fable 上表现非常好，嗯，你知道，GLM Opus 4.8 总的来说，对吧，它显示……你知道这个图表显示模型正在变得，你知道……嗯，这些点是不同的推理模式。嗯，我认为这是最大推理，我认为，嗯，高，超高，你知道，这些实际上也是不同的推理……推理时间。嗯，但是总的来说，你可以看到存在一个帕累托效率趋势，对吧，最好的模型是那个，你知道，在右上角的。越靠右上角的模型就越好。嗯，所以你希望随着时间的推移，模型能越来越好，朝着右上角发展。而且，你知道，我刚了解到，我以前其实不知道这个。我刚了解到，SWE-bench Pro，当你运行这个基准测试时，你使用大语言模型 (LLM)，你使用语言模型作为验证者 (verifier)。嗯，我感到很困惑，因为对于大多数基准测试，对于大多数基准测试来说，你永远不应该调用另一个语言模型来检查你的答案是对还是错。而对于 SWE-bench Pro，你实际上调用了一个语言模型来验证你的语言模型是否正确。嗯，所以这就是为什么 SWE-bench Pro 不是一个很好的基准测试。嗯，问题之一是，我们需要进行采样吗？比如，你需要运行多少次验证来确认你的答案是否正确？你是运行一次吗？运行五次吗？运行一百次然后取个平均值吗？嗯，所以我其实非常震惊，这竟然是实际发生的事情。我其实非常惊讶。嗯，下一个问题是，哪个模型是验证者？你知道，你问……例如你在 SWE-bench Pro 上测试 Opus 4.8 的基准，但是用哪个……你用什么作为验证者？你是用 Opus 4.8 作为验证者，去使用同一个模型自己来验证自己吗。嗯，所以像这种，我真的是相当惊讶基准测试居然是这样运作的。嗯，而且实际上相当失望。嗯，但是不管怎样，显然你可以采取另一种方法。你可以进行人工验证。嗯，你知道，房间里的每个人，我把基准测试给你们，你知道，然后直接让你们来验证它。嗯，我想你可以这么做。嗯，还有，如果验证每天都在变化，会发生什么呢？嗯，你知道，记住之前，模型，你知道每天模型都会变好或者变坏。嗯，如果，如果在模型表现很差的时候你运行验证，会发生什么？对吧，你实际上会得到不同的 SWE 数据。嗯，所以我其实很惊讶，行业里竟然是这么做的。嗯，你知道，运行 SWE-bench Pro，但使用大语言模型作为验证者，这绝对不是个好主意。嗯，但是不管怎样，人们就是这么做的。嗯，事实上根据 Deepu 的说法，如果你……如果你使用语言模型进行验证，SWE-bench Pro 有 8.5% 的假阳性率 (false positive rate)。嗯，假阳性率意味着大语言模型验证者说该模型是正确的，但实际上它是错的。嗯，所以 8.5% 的情况下它会这样做。嗯，假阴性率 (false negative rate) 甚至更糟，达到 24%。嗯，这意味着验证者说该模型是错的，但实际上它是对的。嗯，所以你可以看到，SWE-bench Pro 是一个非常糟糕的基准测试。嗯，所以 Deep SWE 表明，他们……你知道，他们修复了这个问题，你知道……嗯，通过减少错误……

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. So I think you need to actually call you need to call claude code you know what is my system prompt and then you print it to like a text file um and then you can like in investigate what the system prompt is and then you can also override it if you want um yes but it's a different system prompt most likely um yeah last question if anyone no okay continue on Okay, the next section we're going to be talking about is benchmaxing and cheating. Um, I'm not sure if you folks have seen the deep SWE benchmark. Um, the deep SWE benchmark is a very popular recent benchmark that shows, you know, the cost is on the X-axis and the Y-axis it is a deep SWE benchmark. It's a new benchmark based on like you know a better uncontaminated version of Swebench Pro. Um and in general you can see that you know GBD 5.5 does very well with Fable um you know GLM Opus 4.8 in general right it shows you know this plot shows that models are getting you know um these the dots are different reasoning modes um I think this is maximum reasoning I think um high extra high you know these are actually different reasoning um reasoning times as well um but in general you can see that there is a parto efficiency trend right the best model is the one you know to the right to the top right the better the model to the right to the top is the better the model. Um, so you want the models to do better and better over time to that to the top right corner. And you know, I just learned I didn't actually know this. I just learned that Sweetbench Pro when you run this benchmark you use LL you use language models as a verifier. Um, and I was like confused because like for most benchmarks, for most benchmarks, you should never call another language model to check whether your answer is right or wrong. And so for Swedebench Pro, you actually call a language model to verify if your language model was right. Um, and so that is why SweetBench Pro is not a very good benchmark. Um, one of the problems is is do we need to do sampling? Like how many verification runs do you need to run to verify if your answer is correct? Do you run it one time? Do you run it five times? You run it 100 times and take like an average. Um, so I was actually quite shocked that this is actually what happens. I was quite surprised actually. Um, the next question is which model is the verifier? You know you ask for example you ask opus you know you you benchmark opus 4.8 on swbench pro but which what do you use as a verifier do you use opus 4.8 eight as the verifier to using the same model itself to verify itself. Um and so like this I was like quite surprised actually that this is how benchmarks work. Um and actually quite disappointed. Um but anyways obviously you can go the other approach. You can do human verification. Um you know everyone in the room I'll give you the bench you know and just tell you guys to verify it. Um you could do that I guess. Um and also what happens if the verification changes every day? Um you know remember previously models you know every single day models get better or worse. um what happens what happens if you run what happens if you run the verification when the model was doing very bad right you will actually have different SWE numbers um and so like I'm actually quite surprised this is what the industry does um you know run bench pro but using anonymous is verifies that is definitely not a good idea um but anyways people do it whatever um in fact according to deepu um if you do if you do verification using language models Sweet Bench Pro has a 8.5% false positive rate. Um, and a false positive rate means that the LLM verifier said that the model was correct, but it was actually wrong. Um, and so 8.5% of the time it would do this. Um, the false negative rate is even worse at 24%. Um, this means that the verifier said that the model was wrong, but it was actually right. Um and so you can see that SweetBench Pro is a very bad benchmark. Um and so Deep Sweet showed that they have in you know they fixed the problem you know um by reducing the false

</details>

<!-- chunk 9/17 -->

### 基准测试中的作弊与测试缺陷

**Speaker**: 阳性率（positive rate）和假阴性率（false negative rate）降到，你知道的，1%。嗯，实际上，关于作弊的一些例子，嗯，你知道这其实非常令人惊讶，但是在 SWE-bench Pro 基准测试中，你会得到类似一个 GitHub 问题，你知道的，一个 GitHub issue，你调用模型来解决那个 GitHub issue，但是你知道在 SWE-bench Pro 中你能得到完整的 Git 提交历史记录吗？所以你实际上也得到了真实的答案。所以我当时的反应是，我其实非常震惊地了解到这一点，在测试这些模型期间，你既给它问题又给它答案，那模型显然会作弊。因此，这绝对是一个非常糟糕的基准测试。你知道的，你绝对、绝对、绝对不能把答案直接给模型。所以这非常愚蠢。但是，是的，这种情况经常发生。你肯定不希望模型真的直接看到解决方案，对吧？那是一种非常糟糕的方法。

<details>
<summary>Original English</summary>

**Speaker**: positive rate and the false negative rate to you know 1%. Um in fact some examples of cheating um I you know this is actually quite surprising um but in the bench pro benchmark you get you get like a GitHub question you know a GitHub issue you call the model to solve that GitHub issue but did you know that in Swebench Pro you get the full Git history so you get the you get the actual answer as well um so I'm like I'm actually quite I was actually quite shocked to learn this um that during these models you give the answer and the question like obviously the model will cheat. Um and so like this is definitely a very bad benchmark. Um you know you should never ever ever ever give the model the answer. Um and so very silly. Um but yes this happens a lot. Um and you do not want the model to literally see the solution, right? That is a terrible approach.

</details>

**Speaker**: 嗯，你遇到的其他问题，比如假阳性（false positives），就是你知道的，PR 测试，你知道，那个 GitHub issue 的测试非常薄弱。所以你知道，在最后的结论部分，当 GitHub issue 通过合并请求（pull request）被关闭时，维护者编写的测试其实并不是很好。随之而来的问题是，你知道，如果你拥有的测试非常薄弱，那么你知道，模型表现得很好也并不意味着它真的很好。而且显然最糟糕的部分是，模型会比如绕过某些测试。它会跳过一些测试，嗯，那绝不是一个非常好的做法。

<details>
<summary>Original English</summary>

**Speaker**: Um the other problems that you get get like false positives is you know the PR tests you know the the GitHub the GitHub issue tests are very weak. Um so you know at the final conclusion you know when the GitHub when the GitHub issue is closed with a pull request the tests that the maintainer wrote are not very good. Um and so the problem of that is you know if you have tests which are very weak then you know the model does very well not very good. Um and obviously the worst part is the model will like bypass some tests. It will skip some um and that is not a very good approach.

</details>

**Speaker**: 事实上，嗯，Deep Suite 实际上展示了模型有多少次通过查看完整的 Git 历史记录来作弊，你知道，直接去寻找答案。嗯，你可以看到 Opus 4.7。那些紫色的柱状图显示了模型的作弊情况。嗯，啊，看起来 Jubilee 5.5 从来不作弊。看起来是这样，嗯，好吧，也许我们应该使用 GP 5.5。嗯，你知道实际上这非常有趣。有些人认为如果你作弊，那实际上是件好事。而且为什么说它是好事的原因是，这意味着 Opus 4.7 已经知道了，就像如果你给了它完整的 Git 历史记录，你应该能够……就像你把它给了它们对吧，你给了 Opus 完整的 Git 历史，它就应该在那里找到解决方案，对吧，它就应该直接跳到解决方案。所以这就是人们的想法，你知道人们有一种观点，认为人类既然给了 Opus 4.7 完整的 Git 历史记录，那它就应该作弊对吧，是你，你，你设计它去作弊的。所以总的来说，Cord 模型似乎作弊更多，而 OpenAI 模型总体上似乎作弊较少。所以这取决于你，你知道，你是否希望一个模型作弊。而且“作弊”这个词的定义也非常，你知道的，带有感情色彩（charged），所以我猜这取决于“作弊”这个词到底意味着什么。

<details>
<summary>Original English</summary>

**Speaker**: In fact um deep suite actually showed how many times a model cheats by looking at the full git history you know directly going to the answer. Um you can see opus 4.7. So the purple bars show cheating by models. Um ah it looks like Jubilee 5.5 never cheats. It looks like it um h okay maybe we should use GP 5.5. Um you know actually this is actually very interesting. There are some people which think that if you cheat that's actually good. Um and the reason why it's good is it means that Opus 4.7 already know like if you give it the full Git history you should be able to like you gave it to them right you gave Opus the full Git history it should find the solution there right it should just directly skip over to the solution. So it's that's what people think you know people have a view that the humans gave Opus 4.7 the full gate history so it should cheat right you you you designed it to cheat um so in general cord models seem to cheat more um and open AI models seem to cheat less in general um so it depends on you you know if you want a model to cheat or not um and the definition of the word cheat is also very you know charged so I guess it depends on what the word cheating means

</details>

**Speaker**: 嗯，你知道关于假阴性（false negatives），记住 SWE-bench Pro 会调用一个语言模型来验证你的答案是否正确，嗯，所以有时候它的效果不是很好。你知道，有时你会遇到不相关的测试失败的情况；嗯，你忘记了，你知道有时当你写测试的时候，你忘记了那些带有辅助程序（helpers）的测试，你知道的，辅助函数，然后你直接跳过了那个，所以存在很多问题。这个，我想这是20……是的，所以在 24% 的时间里，在 24% 的情况下，模型说，验证器说你的模型错了，但它实际上是正确的。因此，这是另一个问题。

<details>
<summary>Original English</summary>

**Speaker**: um you know for false negatives remember Swebench Pro calls a language model to verify if your answer is correct um and so sometimes it's not very good you know sometimes you have unrelated tests that fail um you forgot you know sometimes when you write tests you forgot about the tests which have helpers you know helper functions and you just skip that um so there are many issues and this I think this was 20 yeah so 24% % of the time, 24% of the time, the model says, the verifier says your model was wrong, but it was actually correct. So, this is another problem.

</details>

**Speaker**: 甚至更糟的是，测试框架（harness）本身可以改变准确率。所以，当你使用 SWE-bench Pro 进行基准测试时，你比如需要为所有模型配备一个智能体或一个测试框架，对吧？你如何为这些模型创建一个通用的控制环境呢？嗯，所以你可以看到，比如，你知道 Deep Suite 展示了，如果你使用 Claude 代码，你能获得 40% 的准确率，但是如果你使用他们自己的，也就是一个特殊的测试框架，你就能获得 50% 的准确率。嗯，以 Gemini 为例，对吧，如果你使用 Gemini CLI，你得到 20% 的准确率，但如果你使用他们的那个，你知道的，那个受控环境，你就能获得 40% 的准确率。所以总的来说，对于这些基准测试，你还需要有一个受控的环境。嗯，这也是另一个问题。

<details>
<summary>Original English</summary>

**Speaker**: And even worse, the harness itself can change accuracy. So, when you benchmark using Swebench Pro, like you need to have one agent or one harness for all models, right? How do you create a generalized control environment for these models? Um and so you can see like you know for example DeepSu showed if you use clawed code you get 40% accuracy but then if you use their own so it's a special harness you can get 50% accuracy um Gemini for example right if you use Gemini CLI you get 20% accuracy but if you use their one you know the the control environment you can get 40% accuracy um and so in general for these benchmarks you also need to have a controlled environment. Um, and that is also another problem.

</details>

**Speaker**: 而有了 Deep Suite，他们展示了通过使用这个基准测试，通过解决，你知道，通过阻止作弊，你知道，通过，也就是如果我们消除作弊现象，如果我们消除，你知道的，这些其他问题，你可以看到模型，你知道，模型的数据表现不再是饱和的了，对吧？你可以看到这些模型在能力方面有很大的不同。根据这个基准测试，GBD 5.5 是最好的，根据这个来看。嗯，我没有……哦，这个数据没有更新。嗯，关于 4.8 我想大概在这里或者什么地方。嗯，但是，是的，这个基准测试显示 Core Taiku 是 0%。嗯，准确率，对吧？我想这太糟糕了。嗯，但是是的，这个基准测试只是展示了……好吧，主要的问题是：你信任这个基准测试吗？那是另一个问题。

<details>
<summary>Original English</summary>

**Speaker**: And with Deep Suite, they showed by using this benchmark, by solving, you know, by stopping cheating, you know, by, you know, if we remove cheating, if we remove, you know, these other issues, you can see the models, you know, the models are not saturated anymore, right? You can see the models are very different in terms of the capabilities. According to this benchmark, GBD 5.5 is the best according to this one. Um I don't Oh, this is not updated. Um for 4.8 I think is over here or something. Um but yes, this benchmark shows core taiku is 0%. Um accuracy, right? It's terrible, I guess. Um but yeah, this benchmark just show okay the main question is do you trust this benchmark? That is another question.

</details>

### Cognition 的 Frontier Code 与基准测试竞争

**Speaker**: 嗯，还有其他的基准测试，对吧？所以 Cognition 发布了一个名为 Frontier Code 的基准测试，它也试图解决关于基准测试的同样的问题，你知道，为了解决作弊和基准测试的问题。嗯，他们所展示的是你可以修复数据污染（contamination）。你该如何修复污染呢？你要求，你知道的，你让 Cognition 的团队，那里面全都是像，你知道的，国家奥林匹克竞赛选手和，你知道的，国际奥林匹克竞赛选手。他们自己手动检查了每一个问题，你知道，并删除了糟糕的问题，你知道的，删除了不好的示例。嗯，他们还展示了他们的问题要多样化得多，对吧？所以，Frontier Code 包含许多不同的其他语言。嗯，他们展示了通过多样性，你知道通过更多样化的编程语言，嗯，以及通过减少污染，他们也建立了一个基准测试。嗯，根据他们的基准测试，Opus 4.8 是最好的，对吧，达到了 14.5% 的准确率，Juby 5.5 的准确率是 7.2%。

<details>
<summary>Original English</summary>

**Speaker**: Um there is other benchmarks, right? So cognition released a frontier code benchmark which also tries to solve the same questions for benchm you know for cheating and benchmarks. Um and what they showed is you can fix contamination. And how do you fix contamination? You ask, you know, you ask Cognition's team, which is full of like, you know, national Olympiads and, you know, international Olympiads. They manually checked every single question um themselves, you know, and removed bad questions, you know, bad examples. Um and they also showed that their questions are much more diverse, right? So, Frontier Code has many different other languages. Um and they showed with diversity you know with more diverse programming languages um and by reducing contamination they also have a benchmark um and according to their benchmark opus 4.8 is the best right for 14.5% accuracy juby 5.5 is 7.2 to accuracy.

</details>

**Speaker**: 嗯，这个是钻石（Diamond）级别的那个，对吧？所以，这是那 50 个，那 50 个最难的问题。嗯，主要基准测试包含 100 个问题，扩展版则是 150 个。嗯，所以根据他们的说法，你知道的，Claude 表现最好，根据他们的基准。但同样根据他们的说法，Frontier Code 似乎比 Deep Suite 更好。对吧？我之前展示的那个基准测试，Deep Suite，这一个，嗯，你知道，根据 Frontier Code，也就是 Cognition 团队的说法，他们的基准测试比 Deep Suite 更好，对吧？根据他们的说法，在他们看来，Deep Suite 的假阳性率是 44.9%。但是还记得 Deep Suite 自己是怎么说的吗？他们说假阳性率是……我不记得他们到底说什么了？嗯，他们说它是 0.3%。对吧？所以 Deep 说，Deep Suite 自己说他们的假阳性率是 0.3%。但是 Frontier Code 却说 Deep Suite 的假阳性率高达 44.9%。

<details>
<summary>Original English</summary>

**Speaker**: Um, and this is the diamond one, right? So, this is the 50 the 50 hardest questions. Um, the main benchmark is 100 questions and the extended is 150. Um, and so according to them, you know, Claude does the best according to them. But also according to them, Frontier code seems to be better than Deep Suite. Right? The benchmark that I showed previously, Deepswuite, this one um you know according to Frontier Code, so the cognition team, their benchmark is better than Deepswuite, right? According to them, according to them, Deep SW's false positive rate is 44.9%. But remember what did Deepswu say? They said the false positive rate was I don't remember what what did they say? Um they said that it was 0.3%. Right? So deep said deep said their false positive rate is 0.3%. But Frontier code said that Deep SWE's false positive rate was 44.9%.

</details>

**Speaker**: 嗯，所以你知道在各个基准测试实验室之间，我猜存在一些竞争；嗯，好吧，Cognition 不是一个基准测试实验室，但就像你知道的，在公司之间存在竞争。所以最主要的问题是，我们该信任谁？你知道，我们该相信 Frontier Code 的基准测试吗？我们该相信 Deep Suite 的基准测试吗？我们该相信 Bench 吗？你知道，我们到底该信任谁？这是一个非常重要的问题。嗯，你知道，我的看法是，就像，你知道的，比如我们就直接取每个人的平均值好了。把所有人的数据平均一下，你大概就能得到最好的答案了。你知道，到底谁实际上做得最好。

<details>
<summary>Original English</summary>

**Speaker**: Um so you know there is some competition I guess between benchmarking labs um well cognition is not a benchmarking lab but like you know between companies um so the main question is who do we trust you know do we trust Frontier codes benchmarks? Do we trust Deep Swiss benchmarks? Do we trust Bench? You know, who do we trust? And that is a very important question. Um, you know, my take is like, you know, like let's just take an average of everyone. Take an average of everyone and you'll probably get the best answer. You know, who is actually doing the best.

</details>

**Speaker**: 嗯，是的，但这其实非常有趣。嗯，你知道，它显示了……好吧，所以根据他们的说法，Deep Suite 的假阴性率是正确的。你知道的，1.2%。但是我的兴趣所在，你知道的，我可能会想，你知道，我的主要疑问是，为什么对于 Deep 来说，假阳性率会这么高？根据，根据 Frontier Bench 的说法，Deep Suite 甚至比 SWE-bench Pro 还要糟糕。我猜，在假阳性率这方面，这就是他们试图表达的意思。

<details>
<summary>Original English</summary>

**Speaker**: Um, yeah, but this is actually very interesting. Um, you know, it show Okay, so according to them, the false negative rate for Deep Suite is correct. You know, 1.2%. But my interest, you know, I probably, you know, my main question is why is the false positive rate so high for deep according to according to Frontier Bench, Deep Sweet is even worse than Sweet Bench Pro. That's what they're trying to say, I guess, for for the false positive rate.

</details>

### Frontier Math 基准测试的修复

**Speaker**: 嗯，是的。甚至更糟的是，还有一个名为 Frontier Math 的基准测试。嗯，所以这个 Frontier Math 是由 Epoch AI 发布的。嗯，所以他们，他们有这个数学基准测试，它分为不同的层级，你知道的，第一级，第二级，第三级，第四级。那么第四级是最难的。嗯，但是这个基准测试本身就搞砸了（botched）。嗯，所以他们实际上不得不发布了一个修正版的基准测试。嗯，我想这是一个月前吧，嗯，或者差不多那时候。嗯，所以他们展示了他们的基准测试题目完全是错误的。嗯，然后你可以看到如果你纠正了这个基准测试，如果你修改好了基准测试，GBD 5.5 的准确率就会从 50% 跃升到 80% 或者类似的数据。嗯，所以现在你多少能信任这个基准测试了。他们还在推文上展示了，哦，那是在 6 月 12 日。哦，那仅仅是两周前。嗯，所以在 6 月 12 日，他们展示了为什么他们表现不佳的原因在于……

<details>
<summary>Original English</summary>

**Speaker**: Um, yeah. And even worse, there is another benchmark called Frontier Math. Um, so Frontier Math is by Epoch AI. Um so they they have this math benchmark with different tiers you know tier one, tier two, tier three, tier four. So tier four is the hardest. Um but the benchmark itself was botched. Um and so they actually had to release a corrected version of their benchmark. Um I think this was one month ago um or something. Um so they showed that their benchmark questions were fully wrong. Um, and you can see that if you correct the benchmark, if you correct the benchmark, the accuracy for GBD 5.5 jumps from 50% to 80% or something. Um, and so now you kind of trust the benchmark. And they showed in a tweet, oh, it's June 12. Oh, it's only two weeks ago. Um, so in June 12, they showed that the reason why they did bad on

</details>

<!-- chunk 10/17 -->

### Benchmarking Flaws and Evaluation Challenges

**Speaker A**: 基准测试的问题在于，他们在提取答案时做错了。比如，他们的问题表述不清，或者正负符号弄错了。举个具体的例子，他们说模型输出的答案是 12，但实际上正确答案应该是 -12，而他们在提取答案时却忘了把负号也提取出来。他们还会出现“差一错误（one-off errors）”。总之，这个基准测试存在许多许多的问题。直到最近，他们才刚刚修复了他们的基准测试。事实上，这相当可笑。这也就是两周前发生的事情。大家听说过 Hugging Face 一年前推出的 Math Verify（数学验证）吗？Hugging Face 表明，事实上当你用这些基准测试做数学题时，它们的表现总是很差。原因就在于存在很多问题，比如格式不正确，分数的提取也是错的，正负符号提取失败等等，在数学公式和答案的提取方面有非常非常多的问题。老实说，我觉得这有点像是在重复造轮子，或者说是重新发现已有的问题。Hugging Face 早在一年前就发布了这个结论，而 Epoch 直到两周前才刚刚修复它。所以，我觉得基准测试实验室肯定需要更多地去调查研究，他们需要更多地查阅现有的文献资料。事实上，根据 Hugging Face Math Verify 的数据，如果你看那条绿色的柱状图，那条绿条代表的是你不使用 Hugging Face 的验证系统来修复基准测试时的结果。如果你确实使用了修复后的基准测试，你会发现模型的准确率会发生大幅度的提升，对吧？例如 Qwen 模型，Qwen 原本的准确率只有 10%，现在修复后变成了 25%。这就意味着，开源模型并不蠢，它们只是输出了一种不同的格式而已。所以其中一个大问题就是，我们到底该如何实际去解析这些五花八门的格式？实际上，情况甚至更糟。我记得我在 2024 年 8 月发过一条推文，提到如果你使用不同的分词技术（tokenization），你也可能会得到截然不同的准确率。事实上，对于 MMLU 来说，如果你使用空格，准确率会提高 0.4%。这听起来可能不算多，但这里的重点是，正是因为这些非常愚蠢的小问题，比如使用空格，或者 -12 变成了 12 等等，这些看似无关紧要的小细节，会导致这些基准测试的准确率随着时间的推移而发生波动和变化。所以，主要的核心问题是，我们如何才能让基准测试实验室和基准测试公司变得更加可靠，并且更加值得信赖。

好了，我想关于基准测试的部分就讲到这里。关于这部分大家还有什么其他问题吗？有问题请提问。那位请讲。

<details>
<summary>Original English</summary>

**Speaker A**: the benchmarks is they they did the answer extraction incorrectly. For example, they did, you know, they had unclear questions. They had the incorrect sign. So, for example, they said the model said 12, but it should be actually minus 12 and they forgot to cut the minus sign. Um, they have one-off errors. Um, yeah, there's many problems with the benchmark. Um, and so they fixed their benchmark um, just recently. In fact, you know, it's actually quite funny. This was just two weeks ago. Have you guys heard of hugging faces math verify which was one year ago? Um and hugging base showed that in fact these benchmarks when you do math questions they always do bad and the reason why is because there's many problems right the formatting is incorrect um you know the extraction of the fraction is wrong um you know the sign is failed extraction there's many many many problems of mathematical extraction and to be honest I feel like it's like kind of a reinventing the wheel or you know rediscovery um but hugging base actually published this one year ago and epoch just fixed it 2 weeks ago. Um so you know benchmarking labs definitely need more you know they need to investigate literature more I think. Um in fact according to hugging face math verify you know if you use if you the green bar the green bar is if you do not use hugging faces's verification system you know to fix the benchmark. If you do fix the benchmark, you can see accuracy dramatically increases, right? For example, for Quen, for Quen, the accuracy was 10%, now it's 25%. Um, and so you need to, so that means the open source models are not dumb. They just have different they output a different format. Um, and so one of the problems is how do we actually actually like, you know, pass these different formats? In fact, it's even worse. Um, no, I think I tweeted, oh, I tweeted this in August 2024. Um, that if you if you use different tokenization, you can also have different accuracy. Um, in fact, for MLOU, if you use spaces, you increase accuracy by 0.4%. Um, it might not sound like a lot, but the point is by these very dumb things like, you know, using spaces or, you know, minus 12 becomes 12. Um and all of these like dumb little small things, the accuracy of these benchmarks can change over time. Um and so like the main question is you know how do we make benchmarking labs and benchmarking companies you know how do we make them more reliable um and you know more trustworthy.

Oh okay that's I guess the section for the benchmarking part. Any other questions for that section? Um questions. Yes.

</details>

**Speaker A**: 那是一个非常好的问题。所以你的问题是，我们该如何去信任这些基准测试公司？或者说，我们可以采用什么其他类型的基准测试来使其变得真正值得信赖？这确实是个极好的问题。对于基准测试来说，最主要的问题在于你需要满足两个关键条件。第一个条件是，基准测试必须是不能被“刷榜（benchmaxable）”的，对吧？你该如何去构建一个极端困难、难以被刻意针对优化的基准测试？我们该如何避免模型轻而易举地获得 100% 的准确率？第二个问题是，我们如何让基准测试变得完全可验证？也就是说，我们怎样才能让基准测试不仅能运行，而且你还能确实验证其给出的答案是否正确？大家还记得吗，SWE-bench Pro 之所以显得有些愚蠢，是因为它直接调用语言模型本身去验证它自己的输出。这种做法是不好的。所以核心焦点就是这两个问题。

为了说明这一点，我举一个好例子，尽管这也算是个有点笨的例子：随机生成大量的数学题，进行采样。好吧，这也许算不上一个很好的基准测试，但假设你自动生成数学题目，我们可以进行无限次的采样，对吧？我们可以采样无穷无尽的数学题，比如 2 + 2，4 + 4，任何两个单独的数字相加。这就是一道测试题。你能验证这个答案吗？完全可以。你可以调用一个外部计算器来验证 2 + 2 到底等于几。这种测试能被轻易刷榜吗？很难。之所以说它难，是因为它的采样空间是无限大的，对吧？它可以是 2 + 2，也可以是 1000 + 101，而且你也不一定非得限定做加法，你可以做 1000 乘以 1000。所以，这就是构建一种既很难作弊，同时又很容易验证的基准测试的方法之一，也就是采用某种随机生成的数学问题。

另一个例子，比如说……好吧，也许这个例子也不太恰当，这是我临时在台上想出来的。比如，要求模型创作一首 70 个单词的诗，并且规定在这首诗中必须使用“快乐（happy）”这个词。你能验证这个输出吗？可以。在生成的文本里有没有“快乐”这个词？如果有，就加一分。此外，你也可以数一数它生成了多少个单词，对吧？你可以数一下，到底是不是正好 70 个词？所以你可以采用这类验证方法。这种方法能被刷榜吗？不能。这就很难被针对性地过度优化，因为你可以要求 70 个词，也可以要求 69 个词、68 个词、102 个词或者 1000 个词，对吧？而且也不一定非得是“快乐”这个词，可以是“你必须包含两个特定的词”，或者“三个特定的词”。所以，你需要设计某种很难被刻意刷榜的基准测试。在我看来，我认为这可能会成为未来最重要的一种基准测试，但我认为现在似乎还没有任何人真正做出这样的东西。也许台下的哪位听众，或者你们可以组建几个团队，去弄个初创公司之类的去尝试解决这个问题。我觉得那种类型的基准测试将会非常、非常重要。

<details>
<summary>Original English</summary>

**Speaker A**: That's a great question. So the question is how do we how can we trust these benchmarking companies or like what other types of benchmarks can we do to make it trustworthy? Um so that is actually a very good question. The main question for benchmarks is you need to satisfy two conditions. The first condition is the benchmark must not must not be benchmaxable. Right? How do you make a benchmark that is extremely hard to benchmark, right? How do we like not get 100% accuracy? And the second question is how do we make the benchmark um verifiable, right? So how do we make the benchmark you can you can also verify that the answer is in fact correct, right? You remember Swebench Pro is dumb because you call the language model itself to verify itself. Um so that is not good. Um so the main question is those two questions. Um, and so one good example, this is just a dumb example. Randomly create maths questions. Sample for example. Okay, this is okay, this is probably not a good benchmark. You automatically create maths questions. Um, we can sample infinity, right? We can sample infinite maths questions, right? 2+ 2, 4 plus 4, you know, any single number added together. That's one question. Can you verify this? Yes, you can. Right? You can call a calculator to verify what is 2 plus two. Can this be benchmaxible? Hard. And the reason why hard is because the sampling space is infinity, right? It can be 2 plus 2, 1,00 plus 101, right? It can you you don't have to do plus, right? You can do 1,00 times 1,00. And so that's one way make a benchmark which is very hard to cheat but also easy to verify. So some sort of math question.

Um, the other one, for example, is um, okay, maybe this is not a good example. I'm just making this one up on the spot. Tell the model to create a poem in 70 words and you must use the word happy. Can you verify this? Yes, you can. Is happy in the, you know, generation? If yes, plus one. Also, you can count how many words, right? You can count, okay, is there 70 words? Um, so you can do these type of approaches. And is this benchmaxable? No. It's it's very hard to benchmark because you can say 70 words, 69 words, 68 words, 102 words, 1,000 words, right? It doesn't have to be happy. It can be you must have two words, you must have three words. Um, so some some sort of benchmark where it's very hard to benchmark. Um yeah, in my view I think that's that's probably going to be the most important benchmark and I don't I don't think so anyone has actually made this yet. Um I don't know maybe someone in the audience or you know you guys can go as teams I don't know make a startup or something you know do that. Um and I feel like that benchmark will be very very important. Um yeah

</details>

**Speaker B**: 那么今天没有任何一个我们可以信任的基准测试？把它们全部取个平均值怎么样？

<details>
<summary>Original English</summary>

**Speaker B**: benchmarks we can trust today none of them. take an average of all of them.

</details>

**Speaker A**: 老实说，最好的方法可能就是“凭直觉检验（vibe checking）”。亲自把它们都试一遍，看看你最喜欢哪一个。坦白讲，对于这些基准测试，我最大的不满就在于，比如你看这个测试，甚至每一天基准测试的结果都可能会发生改变。所以我们再也无法信任这些基准测试了。我个人的基本观点是，不要去信任任何一个基准测试。如果说取个平均值，那么接下来的主要问题就是：谁来计算这个平均值？我想 Artificial Analysis （人工智能分析平台）上会有一些平均数据。他们面临的唯一问题是，他们会对各项测试分配权重。每一个基准测试都有相应的权重，那么现在问题又来了：每个基准测试的权重到底应该是多少？你不能只是算一个无脑的平均值，比如简单地把 10 个基准测试的分数加起来然后除以 10。这大概是行不通的。所以主要问题变成了你甚至该如何去科学地设定这些权重？这又是一个新的棘手问题。所以我认为，总的来说，评估可能还是要依靠直觉检验。我大概也无法给出一个确切的答案。还有其他问题吗？好的。

<details>
<summary>Original English</summary>

**Speaker A**: To be honest, probably the best approach is just vibe uh vibe checking. Try all of them and see which one you like the best. Um to be completely honest, I just you know like these benchmarks h like the main the main issue I have with benchmarks is for example um you know I mean like this one right this one I mean even every single day the benchmark can change. So we can't trust the benchmarks anymore. So my fundamental view is do not trust any benchmarks. Take an average and then okay then main question is who's taking the average? I guess artificial artificial analysis has some average. The only problem is they have some weightings for the weight. Um you know each benchmark has a weight. So now the question is you know what is the waiting of each benchmark. You know you can't just take like a dumb average. Um you know you can't just say you know 10 benchmarks divided by 10. Um that's probably not going to work. So the main question is how do you even do the waiting? That's another problem. Um, so I think in general it's based on vibe checking, I guess. Yeah, I guess I don't have an answer for that. Um, any other questions? Yes. question.

</details>

**Speaker C**: 是的。

<details>
<summary>Original English</summary>

**Speaker C**: Yes.

</details>

**Speaker D**: 那样算是个好办法吗。

<details>
<summary>Original English</summary>

**Speaker D**: So that way Good matter.

</details>

### Cyber Security and Regulation

**Speaker A**: 你说得对。刚才的问题是，因为比如在进行基准测试验证时，你需要调用一个模型，那么问题是你要调用哪个模型？是 GPT-4.8 吗？还是 GPT-5.5？然后用这个模型去验证基准测试的结果？所以你的问题是，我们能不能改用一个开源模型来做这件事？如果是这样的话，你就拥有了一个完全受控的环境。答案是肯定的，你可以这么做。但是请记住，这里依然存在一个问题，因为即使是开源模型本身也会有缺陷，同时推理引擎也可能会有缺陷，甚至推理服务提供商也可能会有缺陷，并且存在准确率下降的问题。所以你说得对。主要的问题是，我们需要有某个人、某个组织，或者某个委员会，能够让我们去彻底审查：你们在测试中使用的到底是哪个引擎？并且要求一定不要去更新那个引擎，引擎必须始终保持不变，模型的权重也不能有任何更改。所以，这种方法也存在非常多、非常多难以克服的问题。但我同意你的观点，作为一个公开透明的标准，你可以使用开源模型，但这并不能一劳永逸地解决其他那些问题。这样解释清楚了吗？好的。

那么，下一部分我要讲的是网络安全与监管。这是一个非常有趣的话题。我不确定在座的各位是否都看过这张图表。它展示了一些人工智能安全研究所的数据，我想这应该是来自英国的数据。他们展示了各个模型在某些网络安全任务上的表现。图上显示 Mythos 预览版似乎在其中表现最好，与之对比的还有 GPT-5.5 Cyber 预览版等等。他们展示了这个基准测试的结果。正如我之前所强调的，我认为 Weird ML 在这方面做得更好，当然，这只是我个人的主观看法，Weird ML 是……

<details>
<summary>Original English</summary>

**Speaker A**: You're correct. So the question was in terms of because we bench pro for example you call a model. The question is what model? Could it be 4.8? Could it be GB 5.5 and you call this model to verify the benchmark? Um you and so the question was can you use an open source model instead? So then now you you have a controlled environment. So yes you can. But remember there is a problem because even open source models itself have bugs times you know the inference engines have bugs times the inference providers have bugs and accuracy degradation. So it's you're correct. Um so the main question is we need to have some one or some organization you know some person or some whatever committee that we can investigate you know which engine did you use do not update the engine you know the engine must be the same you know the weights must have not changed so there's many many many problems with this approach um but I do agree as open you can use an open source model but it's not it doesn't solve the other problems um yeah does that Okay.

Um, so the next section I'm going to be talking about is cyber security and regulation. Um, this is a interesting topic. Um, so I'm not sure if you have all folks have seen this plot. It shows the AI security institutes. Um, I think this is from the UK. Um, they show the performance of models based on some cyber security task. Um, and they show that mythos preview seems to be the best. Um, you know, with GBD 5.5 cybar, you know, preview and so on. Um, they show this benchmark. Uh and again previously as I mentioned weird ML is a better ben in my view okay this is just my take weird ML is

</details>

<!-- chunk 11/17 -->

### 评估基准的局限性与权重分配

**Speaker A**: 总体而言，对于评估模型的智能水平，这是一个更好的基准测试。原因在于，它实际上并没有遵循推理模型与非推理模型的趋势。回想一下之前关于推理模型的讨论，我想我……好吧，我这会儿手头没有那个数据。对于推理模型，能力翻倍的时间缩短了一半，变成了3.5个月。所以请记住，你只需要等待3.5个月，模型的能力就会翻倍。而非推理模型的能力翻倍时间是7个月。所以你需要等上7个月，这些非推理模型的能力才会翻倍。但是 Weird ML 实际上并没有表现出这种趋势。Weird ML 的基准测试表明，它实际上根本不存在这种趋势。而且，我想我在这里就直说了，你知道，基准测试最大的问题之一是，你需要不断地重塑自我，并且对不同基准测试的组合进行重新加权。例如，Artificial Analysis 最近刚刚发布了他们新的 v4.1 版本基准测试，并展示了这些基准测试的权重分配。你知道，比如 GDP Vow 占 20%，Terminal Bench 占 16% 等等。所以他们将这些数字设计为各个基准测试的权重，然后将它们平均计算在一起。那么主要的问题是，你究竟是如何确定这些数字的？所以这更像是一种人为的方法。你知道，你必须人为地去确定这些数字。

<details>
<summary>Original English</summary>

**Speaker A**: a better benchmark in general for benchmarking intelligence on models and the reason why is because it doesn't actually it doesn't actually follow the trend of reasoning versus non-reasoning remembering reasoning previously I think I okay I don't have it um reasoning um the reasoning models doubling time reduced by half to 3.5 months So remember, you just need to wait 3.5 months and the models capabilities will double. Um and the non-reasoning was 7 months. Um so you need to wait seven months for the models to double in capability. Um but weird ML did not actually have this trend. Um the weird ML benchmark showed that actually the trend was like there is no trend. Um, and I think I'll just talk about this, you know, like one of the biggest problems of benchmarks is you need to constantly reinvent yourself and do reweings of combinations of benchmarks. For example, artificial analysis just recently released, you know, their new v4.1 benchmark and they showed the waiting of the benchmarks. Um, you know, GDP vow is 20%, terminal bench is 16% and so on. Um and so they they designed these numbers as waitings for each of those benchmarks and then they've averaged it up together. Um so the main question is how do you actually determine these numbers? Um and so this is more like a human approach. You know you have to determine these numbers.

</details>

### Goodhart定律与模型对基准的过拟合

**Speaker A**: 你知道，ARC AGI 在 ARC AGI 1 上某种程度上已经饱和了，这就是为什么我们有了 ARC AGI 2，这也是为什么我们又有了 ARC AGI 3。我猜一旦 ARC AGI 3 饱和了，我们就会有 ARC AGI 4、5、6、7 诸如此类的东西。而关键点在于，一旦你有了基准测试——这叫 Goodhart 定律还是什么来着，我不记得了——这个基准测试本身就会变得毫无用处，因为模型会开始针对这个测试进行专门的跑分。所以这些大型模型在网络安全等方面最大的问题之一，就是 Mythos 实际上已经大幅偏离了这一趋势。这也是为什么很多人对 Mythos 感到恐惧，或者对 GPD-5.6 感到恐惧，他们害怕这些模型，因为它们偏离了原有的趋势。你可以看到 Mythos 大幅偏离了趋势。

<details>
<summary>Original English</summary>

**Speaker A**: um you know arc AGI kind of saturated on ARC AGI 1 and so that's why we have ARC AGI 2 and that is also why we have ARC AGI 3 and my you know I guess once ARC AGI 3 is saturated then we have ARC AGI 4 5 6 7 whatever um and the main point is once you have benchmarks is it called good art I don't remember um the good the benchmark itself becomes useless because you know models will start benchmarking on this so one of the biggest problems of these larger models for cyber security for example um is mythos actually dramatically went out of the trend um and that is why you know many people are afraid of these you know mythos you know GPD 5 point 5.6 you they're afraid of these models because it went out of trend um you can see that mythos dramatically went out of trend

</details>

### 内部基准测试与网络安全评估

**Speaker A**: 而且你知道，甚至 GPD-5.6 也没有真正发布那么多基准测试，因为它还处于预览模式。所以这来自他们的系统卡。他们表明，在网络安全方面，Guby 5.6 表现得非常非常好。事实上，对于 Guby 5.6，我想他们只把 Terminal Bench 作为他们的基准测试。他们没有在其他任何项目上进行基准测试。不过，在他们的系统卡中，他们确实有一项非常重要的基准测试。这个测试被称为“内部研究调试评估”。这是 OpenAI 自己制定的一套问题。所以，你知道，如果你愿意的话，它就像是自定义的开源测试，是他们自己制定的大约 10 个问题之类的，他们用这套题对 GBD 5.6 进行了基准测试。根据他们的说法，它表现得非常非常……它表现得更好。好吧，我本来想说“非常非常好”，但其实并没有。它表现得更好。而且你可以看到，关于 GBD 这个其实挺有意思的。GBD 5.5 在 OpenAI 自己的内部研究评估中的表现，甚至比 GBD 5.5a4 还要差。而 GBD 5.6 绝对表现得好得多，对吧？你可以看到，如果你把它扩展开来，GBD 5.6 Soul 的表现要好得多。但有趣的是，Terara 在某些时候的表现要好一些。嗯，是的。

<details>
<summary>Original English</summary>

**Speaker A**: um and you know even you know you know GP 5.6 didn't really release that many benchmarks because it was in preview mode. Um, so this is from their system card. They showed for cyber security that Guby 5.6 does very very well. Um, in fact because Guby because Guby 5.6 they I think they only did terminal bench as their benchmark. They did not benchmark on anything else. Um, they did have in their system card they did have one benchmark which is very important. Um, and this is called the internal research debugging evaluation. Um, and this is OpenAI's own set of set of questions. So, you know, the custom open source, you know, if you want to, it's their own set of 10 questions or whatever that they benchmarked GBD 5.6 on. Um, and according to them, it does very very it does better. Okay, I was going to say very, very well, but it's not. Um, it does better. Um, and you can see that GBD, it's actually kind of interesting. GBD 5.5 did worse than GBD 5.5 a four um for OpenAI's own internal um research evaluation um and you know GBD 5.6 definitely does much better right you can see that the G GBD 5.6 soul, you know, if you extend it, it does much better. Um, but interestingly, Terara does better um somewhat sometimes. Um, yeah.

</details>

### 开源模型的漏洞挖掘能力

**Speaker A**: 而且，你知道，随着这些模型变得越来越好，它们带来的最大问题之一是——我不知道你们是否了解，开源漏洞利用正变得越来越糟。高危漏洞的利用率，即被发现的关键漏洞数量，在最近已经飙升。现在可以说每天或每周，都有某种开源软件包遭到入侵。这幅图表也表明，情况正变得非常棘手。Claude Mythos 就是在这条虚线处发布的，当时大多数人都不确定这些漏洞数量的增加是否是因为 Claude Mythos。最有可能的原因是开源界，你知道的，我们使用了大量的模型，对它们进行了成千上万次的调用，而且我们可以在这些模型中自动发现漏洞。但这里其实还有另一点。有人在 Hacker News 上发帖讨论了这个问题：难道真的只有 Mythos 和 Juby 5.6 在发现网络安全问题上表现出色吗？其实并非如此，开源模型也做得非常好。开源模型在发现网络安全威胁和问题方面表现极其出色。在 Hacker News 上有一些关于这到底是对是错的讨论。但是根据一些研究人员和网络安全专家的说法，Mythos 看起来在网络安全方面表现很好的主要原因，是因为他们真的花功夫去检查了开源代码。所以，如果你真的把这些开源库的完整代码库喂给开源模型，它们也会发现漏洞，它们也能发现网络安全问题。你所需要做的就是给模型提供核心数据。所以我感觉，最根本的问题是，Mythos 显得非常强大，并不是因为模型本身有多强大，而是因为他们确实费心在所有的开源仓库上进行了测试。如果你调用所有这些开源模型去检测漏洞和网络安全问题，你同样会发现漏洞。而且就像大家都知道的，Fable 至今对绝大多数人还是被封禁的。

<details>
<summary>Original English</summary>

**Speaker A**: And, you know, one of the biggest problems of these models that are getting getting better and better and better is I don't know if you guys know that, you know, open-source exploits are getting worse and worse and worse. Um and so the high exploit ratio you know number of critical vulnerabilities that were discovered has skyrocketed you know recently you know every single week or day some sort of open source package gets compromised um and they actually you know this plot shows that it's getting very problematic um and so you know claude mythos was released at this dotted line where you know most people they're not sure if it's because of claude mythos that these vulnerabilities are increasing most likely it's because open source you know we use lots of models call them many many many many times and we can you know automatically find exploits in these models but you know there is actually another point so in hacken news someone posted about this um is it just mythos and juby 5.6 six that do good on finding cyber security issues. It's not actually open source models also do very well. Um open source models do extremely well in finding cyber security threats and issues. Um you know there is some discussion on hacker news you know is this actually true or false? Um but you know according to some you know some researchers and cyber security people the main reason why you know mythos looked like it was very good on cyber security is because they bothered to actually check the open source code. Um and so if you actually give the open source models the full code base of these open source libraries they will find the bugs you know they will find cyber security issues. Um and all you need to do is core the model. Um and so I feel like you know that's the fundamental problem is mythos seems very powerful not because the model is powerful but because they actually bothered to test on all open source repos. Um and so if you do you know if you call all these open source models to detect for bugs for cyber security issues you will find bugs and you know as as you know recently you know as everyone knows fable is still banned for the majority of everyone.

</details>

### AI模型管控与许可证制度探讨

**Speaker A**: 而 GBD 5.6 呢，正如大家所知，是延迟分批发布的对吧？比如 Guby 5.6 预览版是周五发布的，对吧？也就是几天前，而且他们表示不会向所有人开放。现在的核心问题是，不论是在开源界还是闭源界，人们都在问，我们使用这些 AI 模型是不是都需要许可证？就像在这个房间里的每个人，现在我们是不是必须得像考驾照一样，拿个证才能用这些模型？我们需要去考证吗？未来所有这些模型的发布是不是都会被延迟？以至于每次发布新模型时，只有受信任的提供商才能获得这些模型。接下来的另一个最重要的问题是，开源模型该怎么办？现在美国政府似乎正试图对 Fable 和 GPD 5.6 进行某种管控。那么现在的主要问题是，我们该拿开源模型怎么办？那些开源模型、开放权重的模型。政府将采取什么措施来管控开源领域？说实话，政府这么早就对 GBD 5.6 和 Fable 采取管控行动，我感到相当惊讶。我原以为可能会到年底甚至明年，但看起来行动已经开始了。

<details>
<summary>Original English</summary>

**Speaker A**: Um, and GBD 5.6, you know, is delayed a staggered release, right? So like Guby 5.6 preview was on Friday, right? So like a few days ago, and they said they're not going to be releasing to everyone. Um, and the main questions are, you know, in the open source world, in the clos world, people are asking, do we need a license to use these AI models for everyone? You know, like everyone in this room now, we have to have a license to use the models, like a driver's license. Um, do we need to get that? um is there going to be a delay in all of these releases? So every single time when a new model gets released only the trusted providers get these models. Um the next most important question how about open-source models you know okay the government the US government currently is like you know trying to like control Fable GPD 5.6 The main question now is what do we do about open source models? You know, open models, open weight models. What will the government do to control the open source space? To be completely honest, I was quite surprised the government acted this early um in doing GBD 5.6 and fable control, right? I thought it was like maybe the end of the year or next year, but it seems like it's now.

</details>

### 定义前沿智能与开源生态的未来

**Speaker A**: 所以接下来的问题是，开源模型会发生什么？政府会开始管控开源模型吗？而最根本的问题在于，是什么定义了前沿智能？政府之所以要管控这些模型，就是因为它们非常非常强大。那么主要问题来了：究竟是什么定义了智能？我们应该使用哪个基准测试？难道仅仅基于一万亿个参数吗？我们该如何界定一个模型是应该被禁还是不被禁？这是一个非常非常重要的问题。现在是不是会出现一个开源模型的暗网？我们是不是需要像下种子那样去下载开源模型？还有最重要的问题，推理服务商现在会怎么做？假设政府甚至对开源模型也有了某种监管，那么推理服务商该何去何从？他们需要持有许可证吗？他们是不是必须在用户使用模型前检查每个人是否都有许可证？诸如此类的问题。所以这些都是目前非常重要的问题。不仅是政府，还有整个行业，整个 AI 生态系统和产业界，都在试图找到这些问题的答案。显然，如果你是政府，如果我是政府，这也就说得通了。他们不希望他们的关键……

<details>
<summary>Original English</summary>

**Speaker A**: Um so the next question is what will happen to open source models? Will the government start controlling open source models? Um and the fundamental question is what defines frontier intelligence like the reason why the government is you know they're controlling these models is because they're very very powerful. Um so the main question is what actually defines intelligence? You know which benchmark do we use? Is it just based on one trillion parameters like you know how do we define whether a model can be banned or unbanned? Um and that is a very very important question. Um and we will we have a dark web of open models now you know do we need to torrent open models? Um and the most important question what is inference what are inference providers going to do now you know assuming assuming that the government has some sort of regulation on even open models. Um what is the inference prov what are they going to do? You know what are the inference providers going to do? Do they need to have license? Do they need to check that everyone has a license before you can use the model? Um or something like that. Um and so like you know these are very important questions that you know the government is currently like you know and the industry you know the entire AI ecosystem and industry we are trying to like you know what are the answers to these questions. Um and obviously you know if you were the government if I was the government it makes sense you know they do not want their critical

</details>

<!-- chunk 12/17 -->

### 网络安全法规与开源模型的争议

**Speaker**: 基础设施被黑客攻击的风险。你知道，你要记住，开源漏洞的利用数量正在飙升。如果你改变那个纵坐标轴（y-axis），你知道，不是去看开源漏洞的利用，而是看，比如说，关键基础设施的漏洞利用，你知道，显然政府会感到害怕。嗯，所以他们交错（stagger）发布模型是说得通的。嗯，但主要的问题是，你知道，我们现在仍处于这种……我们仍处于这种类似于“战争迷雾”（fog of war）的应对方式中，你知道的。好吧，不是战争迷雾，就是迷雾，一种大雾弥漫的状态，你知道，我们不知道在监管方面到底会发生什么。嗯，是的，那是非常有问题的。嗯，是的。哦，好的。有没有人对网络安全监管政策，或者其他什么相关内容有任何问题？嗯，或者有任何相关的见解，以及问题？

<details>
<summary>Original English</summary>

**Speaker**: infrastructure to be hacked. You know, remember open-source exploits are skyrocketing. If you change that y-axis, you know, not open source exploits, but like critical infrastructure exploits, you know, obviously the government's scared. Um, so it makes sense for them to like stagger the release. Um, but the main question is, you know, we're still in this we're still in this fog of war type approach, you know. Okay, not fog of war, just fog, a foggy, you know, we don't know what will happen for regulation. Um, yeah, that's very problematic. Um yeah. Oh okay. Anyone have any questions for cyber security regulation policy or whatever? Um or any takes as well questions?

</details>

**Speaker**: 是的。那是一个好问题。所以，这是因为开源吗……所以大家对开源模型的恐慌，是因为，你知道，Anthropic 每天都在不停地大声疾呼“开源很糟糕，开源很糟糕”，你知道，每一天都在说“开源很糟糕”吗？嗯，既是，也不是。我觉得这部分是真的，那就是，你知道，在闭源行业的领域里，确实有一些玩家，他们想要彻底关闭开源生态系统，他们的观点是，如果你把开源模型提供给任何人，他们就会开始黑客攻击，你知道，攻击关键基础设施，他们就会开始进行不良的行为。嗯，所以这算是他们的观点。嗯，所以，是的，我同意一些闭源实验室确实造成了这个问题。嗯，但这其实有点好笑，因为目前政府正在优先监管他们，而开源模型仍然是一个巨大的问号。嗯，所以这就有点像……我不知道，他们可能搬起石头砸了自己的脚，或者做了类似的事情。我不知道具体怎么说那句俗语。嗯，但我感觉，他们确实在声称“开源很糟糕”这方面引起了一些争议，但总的来说，开源模型实际上是非常好的。嗯，所以你可以……我的意思是，从理论上讲，你可以使用一个开源模型，然后，你知道，在所有的代码库（repos）上运行这个模型，你就能发现漏洞，并且你可以利用这些漏洞。所以，他们说的并没有错。嗯，但我感觉，你知道，到底谁有足够的基础设施来做这件事呢？嗯，你知道，GitHub 可能会自动检测到你，然后封禁你之类的。我不知道。每一个部分都有很多很多的……嗯，安全层级（layers of security）。嗯，所以就像，我……我不知道。我……我感觉这多多少少有些被过度夸大了（overblown），但这确实是……这确实是……它发生的概率并不是绝对的 0%。所以这确实是一个问题。嗯，是的，希望能回答你的问题，不过，好的。是的。

<details>
<summary>Original English</summary>

**Speaker**: >> Yes. That is a good question. So is it is open source so the scare of open source models is it because you know anthropic keeps screaming about open source is bad open source is bad you know every single day open source is bad um yes and no I feel like it's true that you know there are some players in the closed source industry they want to shut down the open source ecosystem their view is if you give open source to anyone they will start hacking you know critical infrastructure they will start doing bad behavior. Um, and so that's kind of their view. Um, so yes, I agree that some of the closed source labs have caused this problem. Um, but it's actually kind of funny because currently the government is regulating them first and open source is still a question mark. Um, and so like it's kind of like I don't know, they probably stabbed themselves in the foot or something. I don't know whatever whatever the phrase is. Um but I feel like it's they did cause some controversy in terms of like saying open source is bad but in general open source models are actually good. Um so you could I mean theoretically you can use an open source model and you know run this on all repos and you will be able to find exploits and you can exploit. So they're not wrong. Um but I feel like you know who has the infrastructure to do this? um you know, GitHub might automatically detect you and ban you or something. I don't know. There's many there's many um layers of security for each section. Um and so like I I don't know. I I feel like it's somewhat overblown, but it is it is it's not 0% probability. So it is a problem. Um yeah, if that answers your question, but okay. Yes.

</details>

### 从硬件优化向软件优化的范式转变

**Speaker**: 那么现在我们将要讨论内核（kernels）。嗯，所以在此之前，你知道，像往常一样，这是我最喜欢的一张图表。嗯，你知道，如果我们处在一个不同的未来，你知道，如果我们处在另一条不同的时间线上，我们没有发现 01（此处应指 o1 模型）预览版模型，我们的发展就会停滞不前（plateaued）。我认为这就是这张图表最基本的要点。它表明，如果我们从未发现“推理”（reasoning），我们从未发现 01（o1）或者其他什么相关的模型，我们就会陷入停滞。我们就会在准确率方面遇到瓶颈并停滞不前。嗯，那可不是一件好事。嗯，而且因为我们发现了这种模型扩展（scaling）的新范式，你知道，模型已经持续地实现了进一步的扩展。嗯，但我的个人看法是，我们之所以停止了扩展——嗯，我是说基于旧方法的扩展，你知道的——是因为旧方法仅仅专注于硬件优化（hardware optimizations）。我们现在必须将重心转移到软件优化（software optimizations）和算法优化（algorithmic optimizations）上。嗯，我们……你知道，我们需要在“如何进一步扩展人工智能”这个问题上拥有新的发明。嗯，我们不能仅仅依赖于训练 10 万亿个参数（10 trillion parameters），或者，你知道，仅仅是把模型做得越来越大，越来越大，再大一点。嗯，例如，你知道，我们必须做浮点型的强化学习（float a reinforcement learning）。嗯，如果 PyTorch 拥有这样一种方法论（methodology），让你可以针对不同的精度进行浮点计算操作（floatate float），从而加快训练速度。嗯，那就是其中一种方式。嗯，另一种方式，例如，作为一种软件层面的方法，比如我之前说过的，我们发现了一些位的……你知道的，在梯度累积（gradient accumulation）中的问题。嗯，所以当你进行梯度累积的时候，嗯，它其实是……在损失计算（loss calculation）期间它实际上没有被正确计算。嗯，如果你修复了这个小小的问题，你实际上就可以把准确率提高 1% 到 3%。是的。所以，就像，你知道，这个普遍存在的梯度累积 bug 的修复，它完全就是一个软件层面的修复。它并不是一个硬件修复。嗯，所以，这里最基本的观点就是，你需要进行越来越多、越来越深度的软件改动。对吧？

<details>
<summary>Original English</summary>

**Speaker**: So now we're going to be talking about kernels. Um so previously you know this is my favorite plot as usual. Um you know if we were in a different future you know if we were in a different timeline that we did not discover 01 preview models would have plateaued. I think that's the fundamental point of this plot. It shows that if we have never discovered reasoning we have never discovered 01 whatever we will have plateaued. We will have plateaued in terms of accuracy. Um and that is not good. Um and because we have discovered this new paradigm of scaling, you know, models have continuously scaled even further. Um but my take is the reason why we have stopped scaling um based on you know the old approach is because the old approach only focused on hardware optimizations. We now have to move over to software optimizations and algorithmic optimizations. Um we you know we need to have new inventions of how do we scale AI even further. Um and we can't just rely on doing 10 trillion parameters or you know making the model bigger and bigger and bigger bigger. Um for example you know we have to do float a reinforcement learning. Um so if pytorch has this methodology where you can do floatate float for different precisions to make training faster. Um and that is one way. Um another way for example as a software approach for example as I previously said we found some bit you know issues in gradient accumulation. Um so when you do gradient accumulation um it was actually it was not calculated correctly during the loss calculation. Um and you can actually increase accuracy by 1 to 3% if you fix this small little issue. Yeah. So like you know the universal gradient accumulation bug fix was a software fix. It is not a hardware fix. Um and so the fundamental view is you need to do more and more software changes. Right?

</details>

**Speaker**: 另外一个例子，比如 Snowflake，我们与他们进行了合作，去实现长上下文的微调（context long context fine-tuning），达到了 500k 的上下文长度（contact length），这些全部都是软件层面的改进；嗯，另一个例子是，你知道，MLB 训练速度提高了 12 倍，这也是另一个软件改进；嗯，DeepSeek，你知道，他们发布了一个叫做 DeepSpark 的东西，虽然发布到现在才不过几天时间，嗯，但他们展示了他们可以将推理速度，你知道，提高 50%…… 50% 到 600%，也就是比普通的 MTP 方案快了足足六倍；嗯，所以这是一种软件层面的方法论，对吧？而不是一种硬件的方法论。还有，你知道，Diffusion Gemma，对吧？Gemma 发布了一个新的扩散模型，展示了通过使用一种新的架构，你可以达到每秒 2,000 个 token 的生成速度，对吧？所以，利用扩散类型的大语言模型（diffusion LLMs）来进行更快的推理，再说一次，这也是一个软件上的变更。

<details>
<summary>Original English</summary>

**Speaker**: Another one for example Snowflake we collaborated them to make context long context fine-tuning 500k contact length this was all software improvements um another one is you know 12 times faster MLB training this is another software improvement um deepseeek you know they released something called deep spark which was just a few days um and they showed that they can make inference you know 50 50 to 600% faster so six times faster than just normal MTP um and so this is a software ware methodology, right? Not a hardware methodology. And you know, diffusion Gemma, right? Gemma released a new diffusion model showcasing that you can get 2,000 tokens per second by using a new architecture, right? So using diffusion LLMs to do faster inference and again this is a software change.

</details>

### 摩尔定律的局限与数值表示法的进步

**Speaker**: 那么，我的主要观点是，总的来说，硬件创新正变得越来越不重要。嗯，而且硬件创新的速度实际上正在放缓。嗯，所以这其实相当有趣，智能，你知道……关于智能的扩展，总的来说，它有点像摩尔定律（Moore's law，口误为 Mo's law）——嗯，这有点像，有一种无情的进步、一种不懈的方法在不断地提升智能水平，这就和摩尔定律是一样的。嗯，所以，就像总的来说你可以看到，你……这边就是摩尔定律的图，晶体管的数量一直在不断地持续增加，嗯，但是，你知道，单核性能（single performance）并没有随之增加，它已经停滞不前（staggered）了。嗯，所以这就有点像，你知道，这有点让我想起了，你知道，这张图表，对吧，在参数量方面的智能扩展很可能已经遭遇了瓶颈，最有可能的是，你知道，无论是硬件性能、预训练，或者别的什么东西，我们现在都需要进入这个全新的“推理”范式才能实现进一步的扩展；嗯，所以这在某种程度上，就像是类似于摩尔定律类型的图表，算是吧。嗯，你可以看到，如果你看这边这个，GP（指GPU）的数值表示法（number representation），所以我的 GPU 正在变得越来越快、越来越快、越来越快，对吧？但这其实并不是 GPU 本身在变得越来越快、越来越快、越来越快。嗯，是表示法……是数值的表示法发生了改变，对吧？所以就像，他们把精度从 Float 32（32位浮点）一路改成了 Float 4（4位浮点）。嗯，而这使得 GPU 的速度提高了整整 32 倍。嗯，所以这可不是加快了 8 倍，对吧？这不是简单的 32 除以 4 等于 8 倍。它是加快了 32 倍。而其中的原因是因为张量核（Tensor Cores，此处口误为 tensores），嗯，你知道，更小的尾数（mantissas，此处发音为 mantesses），嗯，等等等等。嗯，所以就像，你其实可以看到，你知道，哪怕是张量，随着张量核（tensores）的引入，它也让 GPU 的速度提升了 12 倍，诸如此类。事实上，如果你仅仅是把 GPU 做得越来越小，越来越小，越来越小，它只会让速度提升区区三倍。所以它其实甚至都已经没那么重要了。嗯，如果你看一下这张图，我们现在正处于 Float 4 的阶段。所以我们现在拥有的大部分 GPU 都停留在 Float 4。接下来是什么呢？我们会拥有 Float 3、Float 2、Float 1 吗？我们会拥有 Float 0 吗？好吧，根本没有这种东西。但不管怎样，重点是硬件可以说已经达到了它的物理极限，对吧？我们已经到 Float 4 了。接下来会是什么？接下来没有东西了。嗯，所以，所以这个问题的答案是：没有下一步了。嗯，所以现在我们需要将重心转移到软件领域上，对吧？我们该如何创造新的算法？我们该如何创造新的方法论来继续保持规模的扩展？

<details>
<summary>Original English</summary>

**Speaker**: And my main point is is that in general, hardware innovations are getting less and less important. Um and hardware innovations are actually slowing down. Um so it's actually kind of interesting intelligence you know the scaling of you know intelligence in general it's kind of like Mo's law um it's kind of like a there is a relentless progress relentless approach to increase intelligence and the same with Mo's law um and so like in general you can see that you this is Mo's law over here the number of transistors has continuously increased um but you know single performance is not increasing it has staggered Um and so this is kind of like you know this kind of reminds me of you know this plot right scaling intelligence in terms of parameters probably has plateaued most likely you know hardware performance pre-training whatever we now need to go into this new reasoning paradigm to scale even further um so it kind of is like similar to the moors law type graph um kind of um and you can see if you see on this side the number representation of GP so my GPU is getting faster and faster and faster, right? It's not actually the GPU itself that's getting faster and faster and faster. Um, it's the represent number representation, right? So like they changed from float 32 all the way to float 4. Um, and this made GPUs 32 times faster. Um, so it's not eight times faster, right? It's not 32 divided by 4 is eight times faster. It's 32 times faster. And the reason why is because of tensores, um, you know, the smaller mantesses, um, and so on. Um, and so like you can actually see, you know, even tensors with the introduction of tensores, it made the GPUs 12 times faster and so on. Actually, if you made the GPU smaller and smaller and smaller, it only made it three times faster. It's not even that important anymore. Um, and if you look at this plot, we are now at float 4. So most of the GPUs that we have now are at float four. What is next? Are we going to be having float three, float two, float one? Are we going to have float zero? Okay, no such thing. But anyways, the point is hardware is kind of at its limits, right? We're already at float 4. What is next? There is nothing next. Um, and so the so the answer to this question is there is nothing next. Um, and so now we need to move over to software, right? How do we make new algorithms? How do we make new methodologies to continue scaling?

</details>

**Speaker**: 嗯，我也制作了这个表格，对吧？我之前说过，为什么，你知道，你使用 Float 32，嗯，我们把它更改成 Float 4，为什么是……为什么它不是仅仅快了 8 倍？嗯，而相反地，它是快了 32 倍，对吧？为什么它能快 32 倍呢？原因在于，当你使用……当你执行浮点精度（floating point precision，发音误为 floatingoint）运算时，你有一个指数部分（exponent）和一个尾数部分（mantissa，发音误为 menta）。嗯，而晶体管空间，晶体管占用的物理空间是指数部分加上尾数部分的平方。嗯，所以这里的诀窍是，如果你把它们在特斯拉（Tesla，此处疑为口误，可能是指 Tensor 或晶体管）上做得越来越小、越来越小、越来越小，你就把它们的性能提升倍数给平方了，对吧？所以，Float 32，对于 Float 32，你大概需要 537 个晶体管左右，对吧？537 个晶体管。嗯，要从 Float 32 变成 Float 16，你只需要 105 个晶体管。所以，实际上你……你使得晶体管的数量变成了五倍之多，对吧？所以，不仅仅是两倍，而是五倍。嗯，依此类推，依此类推，依此类推。嗯，所以你知道，我想你可以……

<details>
<summary>Original English</summary>

**Speaker**: Um, I also made this table, right? I previously said why is you know you use float 32 um we change it to float 4 why is it why is it not eight times faster um and instead it's 32 times faster right why is it 32 times faster and the reason is because when you use when you do floatingoint precision you have an exponent and a menta um and the transistor space the transistor space is the exponent plus the menta squared um and so the trick is if you make them in Tesla smaller and smaller and smaller, you square their number of improvements, right? So, float 32, float 32, you needed 537 transistors around, right? 537 transistors. Um, to go from float 32 to float 16, you only need 105 transistors. So, actually you made you made the number of transistors five times more, right? So, not two times, it's five times. Um, and so on so on so on. Um, so you know, I guess you can

</details>

<!-- chunk 13/17 -->

### 硬件优化的终局与算法的崛起

**Speaker A**: 转向 1.58 bit。我想你可以那么做。但实际上这挺有意思的，因为 1.58 bit 其实并没有快那么多。比起 float 8，1.58 bit 并没有快太多。如果你用，你知道的，7 位指数和 Messa 2。还有另一种使用 float 4 的 1.58 bit。Float 4 比 float 32 快 179 倍。而主要的问题是，我们现在已经做到了大约三个晶体管，对吧？我们已经在大约三个晶体管的水平了，接下来我们要怎么做？两个晶体管？或者一个晶体管？所以，最有可能的情况是，GPU 不会再变得更快了，这就是这张图反映的根本问题。GPU 不会再变快了，相反，我们需要把注意力集中在算子（kernels）上。我们该如何编写更好的算子、更好的算法？我们该如何通过这种方式来扩展规模？不要再去做硬件优化了。相反，我们应该思考如何进行这些算法层面的优化？

<details>
<summary>Original English</summary>

**Speaker A**: go to 1.58 bit. I guess you can do that. Um, but it's actually kind of interesting because 1.58 bit um is actually not that much faster. Um, so 1.58 bit is actually not that much faster um than float 8. Um, if you use um, you know, seven seven exponent and Messa 2. Um, there is another 1.58 bit which you use float 4. Um, so float 4 is 179 times faster than float 32. Um and the main question is we are already at three transistors right we are already around three transistors what are we going to do next two transistors or like one transistor so don't like you know most likely GPUs are not going to be getting faster um that's the fundamental question of this plot so GPUs are not going to be getting faster instead we need to focus on kernels right how do we make better kernels better algorithms how do we scale this instead right don't do don't do hardware optimizations anymore. Instead, how do we do, you know, these optimizations?

</details>

### Torch Compile 与手写算子

**Speaker A**: 所以，我最喜欢使用的工具之一，也是每个人都应该使用的，就是 `torch.compile`。在现代，给你个建议：不要去学怎么写自定义算子。这是我的忠告，不要去写算子。原因在于 `torch.compile` 将会接管所有的算子编写工作。例如，你可以看这张图，`torch.compile` 是那条红线，从性能上看它似乎表现得不是很好，对吧？与手写算子相比，它似乎表现平平。手写算子是其他的那些线。所以 `torch.compile` 看起来表现不佳，但那是因为那是一个旧版本的 PyTorch。如果你用较新版本的 PyTorch，`torch.compile` 就会以压倒性的优势获胜，对吧，那就是那条橙色的线。而所有这些都是手写的算子。哦，对了，黑线是 `torch.compile` 加上无融合（no fusion），那是另一种 `torch.compile` 方法。但是红线、绿线和蓝线……蓝线就是没有使用 `torch.compile` 的普通 PyTorch。但是绿线和红线是手写算子，你可以看到它们的表现甚至比 `torch.compile` 还要差。所以我的观众们可能会想，那写算子还有什么意义呢？`torch.compile` 做的甚至比你还好。

<details>
<summary>Original English</summary>

**Speaker A**: Um, and so one of my favorite tools to use, you know, everyone should use this is just use torch compile. Um, so in my, you know, it's the modern, you know, the modern time, do not, as advice, do not learn how to write custom kernels. That is advice. Do not do kernel writing. Um and the reason why is because torch compile will take over all of kernel writing. Um so you can see for example this plot um torch compile was a red line right performance it doesn't look like it's doing very well right it does not look like it's doing very well versus handwritten kernels right handwritten kernels are the other ones right so torch compile doesn't look like it's doing very well but that's because that's an old PyTorch version if you have a newer PyTorch version torch compile wins dramatically right that's the orange line um and all of these are handwritten kernels. Oh, the okay the black line is torch compile plus no fusion. Um so that's another torch compile method. Um but the red line, the green line and the blue line okay the the blue line is just no torch compile just normal PyTorch. Um but the green line and the black the green line and the red line are handwritten kernels and you can see it does even worse than torch compile. So like my viewers like what's the point of writing kernels? Torch compile does even better than you.

</details>

**Speaker A**: 所以重点是，在你写算子之前，你应该总是先试试 `torch.compile`。先用 `torch.compile`，不要一上来就去学怎么写 Triton，或者 CUDA，或者任何你最喜欢的算子编程语言，不要那样做，去用 `torch.compile`。更糟糕的是，比如这是 RMS Norm，这是 Layer Norm，`torch.compile` 以巨大的优势胜过手写算子。所以我绝对建议你把 `torch.compile` 作为你的首选尝试。不要一上来就写算子，用 `torch.compile`。

<details>
<summary>Original English</summary>

**Speaker A**: Um so the main point is you should always firstly look at torch compile right before you write a kernel use torch compile first do not start learning how to do triton or you know cuda or whatever is your favorite coding language for kernels don't do that instead use torch compile um even worse like you know this this was RMS norm um you know this is layer norm torch compile wins dramatically um you know versus handwritten kernels. So I would not you know definitely only use torch compile as your first try. Um do not write kernels first. Use torch compile.

</details>

### 算法改进的巨大潜力

**Speaker A**: 所以，主要的结论是，算法比硬件或那些手写算子要重要得多。对吧？还记得 DeepSeek 发布的 DeepSpark 吗？还有其他用于推测解码（speculative decoding）的算法，比如 MTP、D flash、DSpark 等等。所有这些都是算法层面的改进，它们让推理速度提升了 2 到 6 倍，对吧？这并不是因为什么新硬件，不是新硬件让推理变快了，而是算法让推理变快了。比如 Flash Attention、FA2、FA3、Flash Attention 4、5、6、7 等等，所有这些都是算法改进。Flash Attention 本质上是一个更好地进行内存移动的技巧。我们该如何像编排舞蹈一样去调度内存移动，并更好地利用 GPU 的缓存结构？所以 Flash Attention 也是一种算法。

<details>
<summary>Original English</summary>

**Speaker A**: So the main takeaway is algorithms are much more important than hardware or whatever handwritten kernels. Right? Remember deepseek released deep you know deep you know deep spark you know there's other algorithms for speculative decoding like MTP D flash DSpark whatever all of these are algorithmic improvements and these made inference two times to six times faster right it wasn't like new some new hardware it wasn't some new hardware which made inference faster it was algorithms which made inference faster right flash attention flash you know FA2 FA3 three, flash attention four, flash attention five, six, seven, whatever, right? All of these are algorithmic improvements, right? Flash attention was essentially a trick to do memory movement much better. Um, so how do we like orchestrate memory movement and use the caching structure of the GPUs much better? Um, and so flash attention is also a algorithm.

</details>

**Speaker A**: 梯度检查点（Gradient checkpointing）是训练中最重要算法之一。它所做的就是不保存所有的激活值（activations）。你使用一个技巧，只保存每一层的激活值，然后跳过每一层中所有的中间激活值，之后再去重新计算这些激活值。梯度检查点大幅节省了内存，大概减少了 70%。在不改变准确率的情况下减少了 70% 的内存消耗。好吧，训练可能会慢一点点，大概慢 10% 到 15%。所以，梯度检查点也是一种算法。

<details>
<summary>Original English</summary>

**Speaker A**: Gradient checkpointing, you know, one of the most important algorithms for training is gradient checkpointing. Um, and all it does is you do not save all the activations. You do a trick where you only save the activations for every single layer. Um, and then you skip all the intermediate activations in each layer. Um, and then you recomp compute the activations. Um, and gradient checkpointing saves memory by dramatic amounts by like 70%. Um, 70% memory reduction with no change in accuracy. And okay, training is a little bit slower maybe by 10% to 15%. Um and you know grading check checkpointing was an algorithm.

</details>

**Speaker A**: 总的来说，你还应该尝试去理解一些新的数据处理技巧。比如我们该如何交错处理数据？我们要不要使用课程学习（curriculum learning）之类的东西？我不知道。在实际预训练模型之前，我们该如何清理数据集？在数据处理方面有很多技巧可以采用。显然，仍然有一群人——我不确定，我持相反的观点——有一群人认为巨型算子（mega kernels）是算子领域最新、最好的东西。什么是巨型算子？巨型算子就是你把模型的整个实现写成一个算子，就像一个超大的算子。也许它很有用，谁知道呢。

<details>
<summary>Original English</summary>

**Speaker A**: Um and you know like in general you should also try to understand you know what is the new data processing tricks you know how do we like you know stagger data you know do we do do we do curriculum learning or something like that I don't know um what you know how do we clean the data set before we actually pre-train the model there are many tricks you can employ for data processing um and obviously you know there is still a group of people I don't know I take an opposite view there is a group of people who think mega kernels are the latest and greatest for kernels. You know what is a mega kernel? A mega kernel is when you take an entire you take an entire implementation of a model and it's just one kernel like one large kernel. Um ah maybe it's useful who knows

</details>

### 异构系统与巨型算子的困境

**Speaker A**: 你看，英伟达收购了 Groq 之类的公司。他们的观点是，举个例子，你有两个不同的系统，对吧？LPU（也就是 Groq 系统）负责解码，比如 MLP 层负责解码；然后 GPU（也就是英伟达的 GPU）负责注意力和 prefill（预填充）。总的来说，我们未来甚至可能拥有不同类型的硬件系统，比如我们有专用集成电路（ASICs），这些是专门为计算设计的芯片，我们也有像 GPU 这样的通用系统。这些 ASICs 和 GPU 将会相互协作。例如，注意力机制将交给 GPU 处理，然后它们会将数据传输给 LPU 来处理 MLP 等等。这就好像它们之间的一支舞蹈。你也可以做像流水线（pipelining）这样的事情。你可以想象这有很多很多的副本，它们可以一口气服务 20 个人，或者 1000 个人。所以，这是另一种方法。在我看来，这和巨型算子是截然相反的路径。

<details>
<summary>Original English</summary>

**Speaker A**: um you know you know Nvidia you know Nvidia has acquired Grock or something um and you know their view is for example you have two different systems right the LPU which is the Grock system does the decoding right so like the MLP layers the layers does the decoding and then the GPU so the Nvidia GPUs does the attention and the prefield um and so in general you know we might even have a future We have different types of hardware systems you know we have asex which are you know specially designed chips for you know computation and we have generalized systems like GPUs. Um and these asex and GPUs will collaborate with each other. Um so for example the attention you know the the attention will be for the GPUs and they will transfer over to the LPU to do you know the MLPS and so on. Um and then this is like a dance you know between them and you can also do like pipelining right you can imagine that there's like many many replicas of this and they can like you know serve you know 20 people or you know 1,000 people in one go. Um and yeah so this is like another approach and you know this in my view this is kind of an opposite approach of mega kernels.

</details>

**Speaker A**: 作为巨型算子，你的观点是你想把……巨型算子的目标是为语言模型的完整前向路径（forward path）编写一个单独的算子。一旦你能够把语言模型的前向路径做成一个算子，你现在就可以把拥有 32 层的整个语言模型变成一个算子了。对吧？你可以扩展它。而且因为整个语言模型都是一个算子，你甚至可以进一步扩展它，对吧？对第二个 token、第三个 token、第四个 token、第六个 token 的预测都可以只是一个算子。不幸的是，这很难做到。这非常难，因为注意力机制是个问题。注意力必须看到未来的 token……抱歉，是看到过去的 token，不是未来的，那是作弊。你必须看到过去的 token，这是一个根本性的问题。要把注意力和 MLE 或 MLP 层结合起来做成一个巨型算子是非常非常困难的，极其复杂。所以通常人们的做法是写两个算子，一个算子负责注意力部分，另一个算子负责剩下的部分。因此你会看到有两个算子。所以，写一个巨型算子很难，但你可以写两个算子。

<details>
<summary>Original English</summary>

**Speaker A**: So as a mega kernel your view is you want to combine the goal is to make the goal of a mega kernel is to make one kernel for the full forward path of a language model. Um and once you make one once you once you are able to make the language model the forward path into one kernel you can now make the entire language model with 32 layers as one kernel. Right? You can extend this and because the whole language model is one kernel you can even further extend it. Right? the prediction of the second token, the third token, the fourth token, the sixth token can all be just one kernel. Um, and unfortunately, this is very hard to do. It's very hard because attention is the problem, right? Attention has to see the tokens in the future. See the tokens in the past, not the future. That's cheating. Um, you have to see the tokens in the past. And that is a fundamental problem. Um and it's very hard to you know it's very hard to make a mega kernel to combine attention and the MLE or MLP layers. It's extremely complicated. So in general what what people do is they will make two kernels right one kernel for the attention part and the other kernel for the rest. Um and so you will see there are two kernels. Um and yeah so it's very hard to make one mega kernel but you can make two kernels.

</details>

### Q&A

**Speaker A**: 好的，还有其他问题吗？关于算子有什么问题吗？所以主要的收获是……是的，请提问。是的，这是一个非常好的问题。这个问题是，因为 `torch.compile` 有太多的旋钮（配置项），大概有 1000 个左右。我们该如何减少实验时间，去找出哪种配置是最好的？幸运的是，我们有一种叫做二分法（bisection）或二分搜索的方法。这就是秘诀。所以我们要做的不是随机去检查每一种 10000 种可能的组合。你要做的是随机化二分法。你随机抽取 50% 的标志位（flags），打开它或关闭它，然后进行基准测试，看看哪种更好。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Okay. Any other questions? Any questions for kernels? So the main takeaway for Yes, a question. Yes, that is a very good question. So the question was because there's so many knobs for torch compile like 1,00 or something. How do we reduce the experimentation time to like you know find which knob is the best? Um so luckily we have something called bisection or binary search. That's the trick. So what we'll do is instead of checking every single 10,00 combination randomly sample. So random you do randomize bisection. You randomly sample 50% of the, you know, flags. You turn it on versus turning it off and then benchmark which one is better.

</details>

<!-- chunk 14/17 -->

### Parameter Search & Specialized Hardware (ASICs) vs GPUs

**Speaker A**: 无论哪个更好，你就可以据此缩小搜索范围。你再次进行 50% 和 50%，50% 和 50% 的划分。所以它实际上是 10000 的以 2 为底的对数。我不知道那个……10000 的以 2 为底的对数是多少。我不知道那个是多少。嗯，两倍的，我不知道。总之，log 200。我想你需要做大概 30 步，我想。我不知道。我不记得 2 的多少次方等于 10000 然后取对数了。嗯，所以你只需要做……你不需要，你不需要检查全部 10000 个参数旋钮。你只需要检查几个步骤，然后你就会知道哪个标志是最好的。嗯，所以技巧是使用二分查找（binary search）或二分法（bisection）来执行这种方法。嗯，对。对。还有其他问题吗？

<details>
<summary>Original English</summary>

**Speaker A**: And whichever one is better, you then narrow down the search. You again do 50% and 50% and 50% and 50%. So it's actually log two of 10,00. I don't know what that what is log 2 of 10,000. I don't know what that is. Um two times I don't know. Anyways, log 200. I think you need to do 30 steps, I think. I don't know. I don't remember whatever 2 to the^ of something is equal to 1,00 then log it. Um so you you only need to do you don't need to do you don't need to check all 1,00 knobs. You only need to check a few steps and then you will know which flag is the best. Um so the trick is to use binary search or bisection to do this approach. Um yeah. Yeah. Any other questions?

</details>

**Speaker B**: 有的。你对……有什么看法？

<details>
<summary>Original English</summary>

**Speaker B**: Yes. What are your thoughts on...

</details>

**Speaker A**: 所以你的问题是我对 ASIC 怎么看，比如，你知道，Cerebras、Groq、SambaNova。我不知道，甚至一些初创公司，新的芯片公司，他们确实设计了自己的芯片。我觉得，ASIC 的问题在于……不管是叫 AS6 还是 ASX 还是什么的，专用芯片的问题在于架构本身需要硬编码在某些芯片中，这就是问题所在。如果你将某些芯片硬编码，你知道，硬编码基础设施，硬编码架构，实验室总是喜欢改变架构，所以每次实验室改变架构时，你都需要更新芯片。嗯，但作为 GPU，GPU 的诀窍在于 Nvidia 已经让它变得——你知道，Nvidia、AMD、Intel，无论什么 GPU 都极其强大，因为它内部集成了通用的 ASIC，对吧？GPU 实际上是各种 ASIC 的组合。而 ASIC 只是一个大型的 ASIC。嗯，所以我认为总体而言 GPU 要好得多，因为你可以定制进入 GPU 内部的内容。你可以禁用进入 GPU 内部的某些东西等等。是的。所以，关于这点，我的观点是，我不知道，我不想说什么，但总的来说，我不认为，你知道，正如我之前提到的，在硬件方面，已经没有别的地方可去了。你知道，我们现在处于 float4，除非硬件提供商发明出，我不知道，float0，那么也许我们能达到 4……你知道，再快四倍。但总的来说，我认为，我认为人们在硬件上投入了太多关注，而他们没有看到实际上最大的提升并不在于硬件，而是在于软件，对吧？数值精度，数值精度的提升让速度快了 32 倍。而硬件只快了 3 倍，对吧？所以硬件仅仅贡献了 3 倍的速度提升。嗯，哦，实际上，好吧，裸片尺寸（die size），你把 GPU 做得更大，你能快 2 倍。那……那有点像是作弊。所以我不会真正说那是实质性的进步。嗯，但从根本上说，如果你把硬件变快，你只能得到 3 倍的提速。嗯，所以在我的观点里，硬件可能被夸大了。你知道，硬件实际上并没有那么重要。软件才是 Nvidia——你知道，Nvidia、AMD、Intel，所有这些硬件提供商，他们依赖的诀窍，他们押注在这样一个事实上：数值精度是一个诀窍，还有张量（tensor）、数值精度、稀疏性（sparsity），你知道，这些软件技巧。嗯，好吧，张量其实不算是软件技巧，但你知道，张量（单元）有点像是 GPU 内部的一个 ASIC。嗯，所以就像，我觉得……对。所以我的观点是，我不太，我不太看好 ASIC 的未来。那是我的观点。嗯，我认为 ASIC 就像，反而，你知道，老实说，我其实挺惊讶的。我们有很多做 ASIC 的公司，但是做算法的公司却很少。嗯，原因在于 ASIC 你可以卖，对吧？每一年你都可以让人升级。你知道，今年你花 1000 美元买 ASIC 的版本一，下一年你就得升级了，对吧？算法的问题在于，算法很难，你知道，很难强迫用户或者不管是谁再次付费。所以这就是为什么硬件非常受欢迎，因为硬件是一个非常容易的商业模式。但是对于算法，这就变得更加复杂了，对吧？我们要如何把梯度检查点（gradient checkpointing）变现？我不知道，对吧？这非常困难。嗯，但主要的一点是，大型实验室本身，我想比如 OpenAI 宣布与 Broadcom 和，随便什么（TSMC等）的合作，你知道，每个实验室本身都在去找硬件提供商并和他们一起设计芯片。嗯，所以我的看法是，也许我们会看到更多这种类似于合作的方法，但我觉得独立的、独立的 ASIC，我不认为它们能长久存在。嗯，是的，这就是我的看法，我想。还有其他问题吗？是的。哦，你是说有哪些类型的内核（kernel）或者……

<details>
<summary>Original English</summary>

**Speaker A**: So your question was what do I think about asex like you know cerebras gro sanova I don't know even startups new chips they do design their own chips I I feel like so the problem of ASEX is is it AS6 or ASX or whatever the problem of specialized chips is the architecture itself needs to be hardcoded in some of the chips and that is the problem. If you hardcode some of the chips you know hard code the infra hardcode the architecture labs always like to change the architecture and so every single time when the lab changes the architecture you need to update the chip. Um but as a GPU the G the trick of GPUs is Nvidia has made it you know Nvidia, AMD, Intel whatever the GPU is extremely powerful because it has generalized asex inside of the GPU right the GPU is in fact a combination of ASEX. Um and the ASICH is just one large ASICH. Um so I think like in general a GPU is much better because you can customize what goes inside the GPU. you can disable stuff that goes inside the GPU and such. Yeah. So on so my view is I don't know I don't I don't want to say anything but like in general I don't think like you know previously as I mentioned you know hardware there is nowhere else to go you know we are at float four unless if the hardware providers invents float I don't know float zero then maybe we get four you know another four times faster but in general I think I think just people are focused too much on hardware and they have not looked that actually the biggest improvements is not hardware, it's software, right? Numerical precision, numerical precision was 32 times faster. Hardware is only three times faster, right? So hardware only contributed three times faster. Um oh actually d okay the die size you make the you make the GPU bigger, you get two times faster. That's that's kind of cheating. So I wouldn't really say that's improvement. Um but essentially if you make the hardware faster, you only get three times faster. Um so in my view hardware is probably overblown. you know hardware is actually not that important. The software was the trick that Nvidia, you know, Nvidia, AMD, Intel, all of these, you know, hardware providers, they banked on the fact that numerical precision was a trick and tensor, tensor, numerical precision, sparsity, you know, these software tricks. Um, okay. Well, tensor is not really software trick, but you know, a tensor is kind of an ASICH inside of the GPU. Um, and so like I feel like that's Yeah. So my view is I don't I don't really see a future for ASEX. That's my view. Um I think that ASEX are like instead, you know, to be honest, I'm actually quite surprised. We have lots of asset companies, but we have very few algorithm companies. Um and the reason why is because ASEX you can sell, right? Every single year you can upgrade. You know, this year you pay $1,000 to ASICH version one and the next year you have to upgrade, right? The problem with algorithms is algorithms is very hard to you know force the user or whatever to pay again and so that is why hardware is very popular because hardware is a very easy business model but for algorithms it gets more complicated right how are we going to monetize grading checkpointing I don't know right that's very hard um so but the main point is the large labs themselves I think like open air announced collaboration broadcom and suras whatever you know each lab themselves are going to the hardware provider and designing the chip with them. Um, so my view is like maybe we'll have more of these like collaboration approaches, but I feel like standalone standalone assets, I don't think they're going to last. Um, yeah, that's my take, I guess. Any other questions? Yes. Oh, you mean what are the types of kernels or

</details>

### CUDA Kernels and Memory Movement

**Speaker B**: 哦，好的。好的。好的。

<details>
<summary>Original English</summary>

**Speaker B**: Oh, okay. Okay. Okay.

</details>

**Speaker A**: 嗯，所以你的问题是内核有哪些，你知道，内核有哪些变化或优化，或者对于内核来说有什么有趣的东西。嗯，所以大部分内核，当你编写内核时，它们中的大多数都集中在减少内存移动上。我们如何减少内存移动？这占据了内核开发的大部分。嗯，例如，有一种技巧叫做……你知道，有一种技巧叫融合交叉熵损失（fused cross entropy loss），它不是……不是让最后一层……不是去物化（materializing）所有的 logits，你可以用一个技巧，分批处理，对吧？你可以进行逐行的物化（row-by-row materialization）。嗯，如果你有很长的上下文，甚至更多，这样做会减少非常多的内存，大概，我不知道，10 GB 之类的。嗯，那是一种方法。嗯，其他的内核，大部分内核被称为内核融合（kernel fusion），你……你有一个像这样很长的 PyTorch 函数，你所做的就是你只写一个内核来执行这整个 PyTorch 函数，而 torch.compile 会为你做这件事。所以 torch.compile 非常擅长进行内核融合，对吧？你给 torch.compile 一个函数，它会写一个内核，一个 Triton 内核或者什么内核，然后它会直接把所有的东西融合在一起。嗯，它在那方面非常非常有效。嗯，但我认为总的来说，内核只是在减少内存移动。嗯，所以就像，我……你知道，说实话，我不太喜欢叫它内核，大多数算法……所以对于大多数算法，你要么使训练更快，要么减少内存使用，但内核……在我看来，内核就是减少内存移动。嗯，所以大多数内核仅仅是内存移动，你知道，内存移动优化，对吧？我们如何……我们如何使用 GPU 的缓存结构？嗯，你知道，我们如何做到不把同一个变量加载两次或三次或者别的什么？嗯，是的，我不确定这是否回答了你的问题，但接下来是强化学习（reinforcement learning）。

<details>
<summary>Original English</summary>

**Speaker A**: Um, so the question was what are the you know what are the changes for kernels or optimizations or stuff that is like interesting I guess for kernels. Um so most kernels when you write kernels the majority of them are are focused on memory movement reduction. How do we reduce memory movement? That's the majority of kernels. Um for example there's there's a trick called um you know there's a trick called fuse cross entropy loss where instead of making instead of the last layer of cont instead of materializing the full logs there is a trick you can do it in batches right you can do rowby row materialization. Um and so this will reduce memory by like a lot by like I don't know 10 GB or something if you have long context or even more. Um that's one way. Um the other kernels most kernels are called kernel fusion where you you have this like long pietorch function and all you do is you just write one kernel to do this whole pietorch function and torch compile will do this for you. So torch compile is very very good at doing kernel fusion right you give torch compile a function it will write a kernel a try kernel or whatever kernel and it will just fuse everything um it's very very effective for that um but I think in general kernels are just reducing memory movement um and so like I you know to be honest I don't really like to call it kernels most algorithms so most algorithms you either make training faster or reduce memory usage um but kernels in my view kernels is reduce memory movement. Um, and so most kernels is just memory movement, you know, memory movement optimization, right? How do we how do we use the caching structure of the GPUs? Um, you know, how do we not load the same variable twice or three times or whatever? Um, yeah, I'm not sure if that answer your question, but next reinforcement learning.

</details>

### Introduction to Reinforcement Learning (RL)

**Speaker A**: 嗯，在这之后将是代理（agents）的奖励黑客（reward hacking）。嗯，所以作为入门，我假设大多数人都知道，大多数人知道强化学习吗，还是我需要给大家做个入门介绍？好的，我会给大家做一个非常快速的强化学习入门。好的，强化学习的快速入门。嗯，什么是强化学习？你有一个环境，比如这个吃豆人（Pac-Man）游戏。嗯，作为玩家，你的目标是，你知道，最大化奖励。你想要吃掉所有的饼干，对吧？你想吃掉所有的饼干，但同时也要逃离你的……怪物。我其实不知道它们叫什么。敌人、怪物、不管叫什么吧。嗯，你作为吃豆人的目标是你想最大化你吃掉的饼干数量。嗯，那就是你的奖励。奖励就是饼干。嗯，而动作（action）是你向上、向左、向下还是向右走。嗯，环境就是这个游戏。另一个好例子，你知道，另一种我喜欢解释强化学习的方式是，强化学习的目标是你希望在训练过程中有更多好的结果，更少坏的结果。嗯，所以例如，在训练的最初阶段，你问模型 2 加 2 等于几？嗯，答案显然是 4。嗯，但当模型开始训练时，它会非常笨。它会非常差。它会看到 B，你知道，模型可能只会说 B、D、猫、狗、房子、老鼠等等。嗯，诀窍是对于所有的坏回答，你想要减少，你不想……你想对它进行负面奖励或者惩罚。如果模型说了些糟糕的答案，你想惩罚它；如果它说出了正确答案，你想增加奖励。嗯，所以这就是强化学习的诀窍。你只想要更多的好答案，更少的坏答案。嗯，如果它像，你知道，非常接近正确答案。所以，你知道，3 非常接近正确答案。嗯，你想奖励，你想要……

<details>
<summary>Original English</summary>

**Speaker A**: Um, and after this will be reward hacking the agents. Um, so as a primer to I'm assuming most people know, do most people know reinforcement learning or do I need to prime people? Okay, I'll give a very fast primer for reinforcement learning. Okay, fast primer for reinforcement learning. Um, what is reinforcement learning? You have this environment such as this Pac-Man game. Um, and your goal is as the player, you know, to maximize reward. You want to eat all of the cookies, right? You want to eat all of the cookies, but also escape away from your the monsters. I don't actually know what they're called. Enemies, monsters, whatever, whatever they're called. Um, and your goal as Pac-Man is you want to maximize the amount of cookies that you eat. Um, and that is your reward. The reward is the cookies. Um, and the action is whether you go up, left, down, or right. Um, and the environment is the game. Another good example, you know, another way I like to explain reinforcement learning is the goal of reinforcement learning is you want to have more good and less bad um during training. Um so for example, at the very beginning of training, you ask the model what is 2 plus two? Um the answer is clearly four. Um but when the model starts training, it will be very dumb. It will be very bad. it will see B, you know, the model would just say B, D, cat, dog, house, mouse, whatever. Um, and the trick is for all of the bad responses, you want to decrease, you don't want you want to like negatively reward this or penalize it. You want to penalize the model if it says something bad and you want to increase the reward if it says the correct answer. Um, so that is the trick of reinforcement learning. You just want more good answers, less bad answers. Um, and if it's like, you know, very close to the correct answer. So, you know, three is very close to the correct answer. Um, you want to reward, you want to

</details>

<!-- chunk 15/17 -->

### 强化学习基础与奖励机制

**Speaker**: ……少给一点负向奖励，对吧？因为相比 B 或 D，3 显然更接近 4。因此，如果模型输出了 B 或 D，你会想要给它施加极其巨大的负向奖励。在强化学习中，诀窍在于你要有一个验证系统，对吧？你需要一个验证器（verifier）来判断模型做得好不好。所以你会无数次地调用这个模型。而对于你给出的每一个示例，你都会给出一个验证分数。比如，第一个示例做得非常好，你就给它打 +10 分。下一个示例表现一般，你就给它打 -5 分。然后最后一个示例非常糟糕，你就给它 -100 分。强化学习允许你对每一个问答分配分数。这基本上就是强化学习验证的方式。强化学习的一个诀窍，用我最喜欢的一句话来说就是：“只要有耐心就够了（Patience is all you need）”。在训练最开始的时候，你的模型会表现得非常差。你的奖励会全是 0。你需要等待很长很长的时间，然后才能得到正确的答案。举个例子，你问模型“2 加 2 等于几”。你开始预训练这个模型，它一开始并不知道 2 加 2 等于几，但 10 年后它会说等于 4。好吧，显然不需要 10 年，我只是夸张一下。但假设你等了 10 年，模型就会回答 4。这也是为什么对于强化学习，我最喜欢说的是“运气才是你需要的全部（Luck is all you need）”。也许你碰巧很快就能让它算出 4，但也可能你需要永远等下去，直到强化学习真正起效。所以通常来说，你的奖励会在很长一段时间内都是零，然后突破零点之后奖励才会开始增加。对于强化学习，有一个非常简单的算法，它的诀窍在于：记住你想要的最终答案。比如，你知道 2 加 2 的答案是 4，但问题是你不知道它的推理轨迹是怎样的，你不知道这个推理过程到底是好是坏。再举个例子，你让模型去写一个快速矩阵乘法算法。这里的诀窍是，如果最终答案是对的，你就给它的每一行代码都打上 +10 的奖励；如果答案是错的，你就给每一行都打上 -100 分。Andrej 在 Dwarkesh 的播客里说过，强化学习有点像“用吸管吸取监督信号（sucking supervision bits through a straw）”。如果你喜欢，我们其实有相关的贴纸，最后可以发给大家。所以 Andrej 的观点是，强化学习虽然很糟糕，但其他的方法更糟。这也是为什么强化学习是我们目前唯一能直接奏效的工具。它确实管用，只是效率不太高。好吧，这其实是下一节要讲的内容。但总而言之，这就是强化学习的基础介绍。大家对这部分有什么问题吗？没有？好的，那我就跳过——哦，有一个问题。请讲。

<details>
<summary>Original English</summary>

**Speaker**: ...negatively reward this a little bit less, right? Because three is much closer to four than B or D. So if you do B or D, you want to negatively reward it massively. In reinforcement learning, the trick is you have a verification system, right? You have a verifier to verify if the model is doing good or bad. So you'll call the model many, many times. And each of these examples you give a verification number, right? So for example, the first example is very good, so you give it a +10 score. The next example is like okay, so you give it a -5 score. And then the last example is very bad, so you give it a -100 score. And reinforcement learning allows you to assign scores to each of those answers and questions. And so that's kind of how reinforcement learning verifies. And the trick of reinforcement learning is, my favorite phrase is "patience is all you need". At the very beginning of training, your model will do very bad, right? Your reward will be zero, zero, zero, zero. You wait for a very long time and then you will get the correct answer. Right? So for example, you ask the model what is 2 plus 2? You start pre-training the model, the model doesn't know what is two plus two, but after 10 years it will say four. Okay, obviously not 10 years, I'm just exaggerating. But you wait 10 years, the model will then say four. And that is why my favorite phrase is "luck is all you need" for reinforcement learning. Maybe by chance you will get four very quickly. But maybe you just have to wait and wait for eternity until reinforcement learning works. So in general, your reward will be zero for a very long time and then you will increase reward after the zero. And for reinforcement learning, there is a very simple algorithm. The trick is, remember the final answer you want. For example, you know what is 2 plus 2, you know the answer is four, but the problem is you don't know what is the reasoning trace. Was the reasoning trace good or bad? So, for example, to tell the model to create a fast matrix multiplication algorithm. The trick is if the answer is right, you reward every single line as a +10 score. And if it's wrong, you reward every single line as -100. And Andre said in a Darkash podcast, reinforcement learning is kind of like "sucking supervision bits through a straw". We actually have stickers for them if you like, so you can get one of those stickers which we can distribute at the end. So Andre's quote is this, and the main point is reinforcement learning is terrible, but everything else is even worse. And so reinforcement learning is the only tool we currently have that just works. It works, but it's not very efficient. And actually that's the next section. But the main point is, that's a reinforcement learning primer. Does anyone have questions on the reinforcement learning primer? No? Okay, I'll skip to— Okay, one question. Yes.

</details>

### 奖励作弊与过程监督

**Speaker**: 我会在下一节提到这个。确实有更好的强化学习方法，但总的来说，目前强化学习的表现似乎已经非常好了。我想这应该是最后一个话题了，也可能不是。奖励作弊（Reward Hacking）与智能体（Agents）。这大概是最有趣的一个话题。对于强化学习来说，只有当生成正确答案的概率大于零时，它才能起作用。如果这个概率低于零，强化学习永远都不会生效。这是强化学习的一个硬性约束：好答案的概率必须大于零，绝不能是零。而在很多情况下，强化学习之所以失败，可能是因为格式不对，或者你需要做一些预热（priming）。所以你必须用一些技巧稍微教教模型，让它了解你到底想最大化什么东西。你必须进行监督微调（SFT）。强化学习的诀窍之一，就是你其实需要先做 SFT 或者微调，让模型不那么“笨”，也就是让好答案的概率不再是零。你需要做好预训练。另一个问题是，在强化学习过程中，如果数据分布偏移太严重，强化学习的效果就会变得非常差。所以强化学习有很多问题。对于生成轨迹（trajectories），强化学习可能会给轨迹分配错误的奖励。还记得强化学习那个简单的诀窍吗？我们会给每一行分配相同的奖励分数，要么全好，要么全坏。这其实并不好，为什么呢？比如你问模型 2 加 2 等于几。最终答案是对的，答案是 4，模型也输出了 4。于是你给这整个思考过程的轨迹打了 +10 分。但这其实是错的，因为如果你仔细看它的思考轨迹，它中间可能写了一句“2 加 2 等于 10”。想象一下，如果我们就像强化学习的诀窍那样，简单粗暴地给每一行打上 10 分或 -100 分，我们就会漏掉这个糟糕的中间步骤。所以你可以想象，当我们不断训练这个模型时，它可能会开始钻空子，或者进行奖励作弊。它会在中间生成一堆毫无意义的乱码，或者发明出某种我们根本看不懂的“新机器语言”，但最终依然能骗到高分。这是强化学习中一个非常大的问题。解决这个问题的办法叫做“过程监督（Process Supervision）”。在过程监督中，你需要手动检查每一行代码或文本。你不再是只给最终结果打分——比如答案对了就直接给每一行都打上 +10 分，你不能这么做。相反，你需要给每一行打上不同的分数。你给某些行 +30 分，某些行 +0 分，而把那些糟糕的行打上 -100 分。这种做法效果非常非常好。但遗憾的是，过程监督无法大规模扩展，而且成本极其高昂。谁来做标注呢？我想只能是人类了。我们必须手动标注这些数据。这也是为什么那些大型实验室有时候会去找 Scale 这样的公司，花钱请人来给数据打标签——判断这一行是好是坏。不过这里的窍门是，你也可以用语言模型来做这件事，对吧？你可以用大语言模型（LLM）来当裁判。你可以调用语言模型来逐行标注。我的观点是，大型实验室未来会越来越多地采用这个流程。它们会反复调用自己的模型来对其自身进行重新审查。在它们看来，这就是通向 AGI 的一种方式：通过不断地自我评估、自我检查，利用 LLM 作为裁判来进行自动化的过程监督。但要记住这其中存在一个问题：即使你引入了过程监督，你依然是在用同一个模型去评估它自己。这跟 SWE-bench Pro 的问题一样，你用 LLM 来验证 LLM，这绝对是不靠谱的。因为你同样会遭遇奖励作弊。奖励作弊的一个绝佳例子就是模型开始作弊。比如，当你想让它写一个极速的矩阵乘法算法时，它要做的居然只是把计时器给删掉。还记得吗，你设定的目标是减少矩阵乘法算法的运行时间。于是它就会直接删掉计时器：“让我们把计时器删掉，把计时时间设为 0”，这样就能最大化它的奖励了。显然这完全是错的。所以这里的应对技巧是，你同时还需要一个正确性检查（correctness check）。

<details>
<summary>Original English</summary>

**Speaker**: I will mention that in the next section. There are better RL methods. But in general, reinforcement learning seems to do very well for now. I think this is the last topic, or maybe not. Reward hacking and agents. The most fun one, I guess. So for reinforcement learning, reinforcement learning can only work if the probability of a good answer is more than zero. If it is less than zero, reinforcement learning will never work. So that is a constraint of reinforcement learning. The probability of a good answer must be more than zero. It can never be zero. And there are many, many problems of reinforcement learning not working. The formatting could be wrong. You need to do some sort of priming or warm-up. So you have to do some sort of trick to teach the model a little bit about the thing that you're trying to maximize. You have to do supervised finetuning. So one of the tricks of reinforcement learning is you actually need to do SFT or fine-tuning to make the model not dumb, right? To make the probability of a good answer not zero. You need to do good pre-training. And then the other problem is that during reinforcement learning, it's just way too out of distribution that reinforcement learning is just very bad. So there are many problems, and for the trajectories, reinforcement learning can assign incorrect rewards to the trajectory, right? Remember the simple trick of reinforcement learning is we assign the reward to every single line as the same number, right, either this is good or this is bad. And this is not good because, why? You ask the model I need to find what is 2 plus 2. The answer is correct. The answer is four. The model says it's four. So you reward this whole thinking trace as +10. But this is wrong because as you can see in the thinking trace, it says 2 plus 2 is equal to 10. Imagine in all of training, because the trick of reinforcement learning is we just literally assign 10 to every single line or -100 to every single line. We missed this bad thing. So you can imagine when we keep training the model, the model might hack or do reward hacking. It will do gibberish in between, do some sort of new machine language which we can't read, and it will assign a high score to that. And so this is a very big problem of reinforcement learning, and the way to solve this or fix this is something called process supervision. And process supervision, what you do is you manually check every single line. You don't just assign +10 to the final... the answer is correct, +10, assign every single line as +10. You don't do this. Instead, what you do is you assign every single line as a different number. You assign some lines as +30, some lines as +0, whatever, the bad lines as -100. This works very, very well. Unfortunately, process supervision cannot scale and it's extremely expensive to do, right? Who's going to label this? It's the humans, I guess. We have to label this data. We have to manually label. For the labs, I guess that's why labs sometimes they go to Scale or whatever, they ask people to label the data—is this good, is this bad, and so on. But the trick is you can also use a language model, right? You can use LLM as a judge. You can call a language model to label every single line. And my view is, large labs are going to be doing this process more. They will call their own model iteratively to re-review itself. And that is one way their view is they can reach AGI, right? Just by re-evaluating itself, re-checking, doing automatic LLM as a judge process supervision, something like this. But remember there is a problem because even if you do process supervision, the model you are using the same model to evaluate the model, right? The same problem as SWE-bench Pro, right? You use the LLM as a verifier to verify the LLM, which is definitely not good. And the reason why is because you can do reward hacking. A very good example of reward hacking is your model starts cheating. So for example, when you want to make a fast matrix multiplication algorithm. All it does is it deletes the timer. Remember you give the goal to reduce the time of the matrix multiplication algorithm. So all it will do is just delete the timer. Let's delete the timer. Set the timer to be zero and then there we maximize a reward. Obviously this is not correct, right? Because the trick is you also have a correctness check,

</details>

<!-- chunk 16/17 -->

### 奖励破解与模型作弊的风险

**Speaker A**: 对吧？你需要检查矩阵乘法是否真的正确。嗯，但是还有另一种方式，模型会直接把你的两个矩阵都修改为零。嗯，那么0乘0等于多少？零。嗯，所以正确性检查也失效了。嗯，所以奖励破解（reward hacking）变成了一个非常非常大的问题，因为这些模型可以作弊，并且使用特殊的技巧来绕过你实际的模型，嗯，绕过你奖励函数的意图。

<details>
<summary>Original English</summary>

**Speaker A**: right? You check if the matrix multiplication is actually correct. Um but there is another way the model will edit your two matrices to be just zero. Um and what is 0 time 0? Zero. Um and so the correctness checks also fail. Um and so reward hacking becomes a very very big problem because these models can cheat and do special tricks to go around your actual model um your intent of the reward function.

</details>

**Speaker A**: 另一个非常有问题的例子是，这不仅仅是关于奖励破解。它实际上可能摧毁你的电脑。对吧？运气不好的话，你的模型可能会输出，你知道的，某种破坏方法，你知道的，删除文件，你知道的，在你的整个电脑上执行 rm-rf，然后拜拜，你的电脑就死机了。嗯，所以就像，你知道的，有时候这种事也确实会发生。嗯，所以这不仅仅是奖励破解，还有对你的工具的信任，因为你知道的，信任模型实际上是在做坏事还是做好事，这也是一个非常大的问题。

<details>
<summary>Original English</summary>

**Speaker A**: Another very problematic example is it's not just about reward hacking. It can actually destroy your computer. Right? By bad luck your model might output you know some sort of corruption methodology you know deleting you know doing rm-rf on your entire computer and bye-bye your computer's dead. Um and so like you know sometimes this also does happen. Um so it's not just reward hacking also trust of your tool cause you know trust of whether the model is actually doing good or bad is also a very big problem

</details>

**Speaker A**: 还有，记得我展示的这个图表，你知道的，如果你把 GPD 5.6 在基准测试上作弊、你知道的，查看答案的情况包括进去，你知道的，记得之前提到的 su bench、嗯 bench pro 和 deep，都表明模型也会通过查看最终答案来作弊，你知道的，你可以看到在 GBD 5.6 上，如果你作弊，它表现得非常好。但是如果你移除掉那些作弊的例子，它的表现，你知道的，就在趋势线之内。

<details>
<summary>Original English</summary>

**Speaker A**: and remember this plot that I showed you know if you include GPD 5.6 cheating on the benchmarks you know looking at the answer you know remember the previously su bench uh bench pro and deep show that models also cheat by looking at the final answer you know you can see that with GBD 5.6 If you cheat, it does very well. But if you remove the cheating examples, it does, you know, within trend.

</details>

**Speaker A**: 然后，你知道的，也许你可能会想，哦，这个奖励破解的事情就像，哦，它非常罕见，你知道的，非常罕见。这在现实世界中是不会发生的。嗯，好吧，GLM 5.2 在其训练方法中，他们特别提到他们有一种用于强化学习的新方法叫做防作弊（anti-hacking）。嗯，所以 GLM 5.2 引入了一种方法来阻止，你知道的，奖励破解。嗯，他们做的是，他们添加了一个链接检查器。嗯，所以记得之前我们提到过 SweetBench Pro 嗯模型会怎么作弊并查看答案。嗯，所以 GLM 所做的就是他们加入了这个检查。嗯，所以在强化学习期间，他们会检查你进行的每一次工具调用。嗯，如果网站，如果网站导向了答案，你就会阻止这种情况发生。嗯，所以就像 GLM 基本上公开了这个就像，你知道的，针对整个强化学习过程的过滤系统。嗯，而且你知道，据他们说，这非常有效。

<details>
<summary>Original English</summary>

**Speaker A**: And then, you know, maybe you might be thinking, oh, this reward hacking thing is like, oh, it's like very rare, you know, very rare. It's not going to happen in real world. Um, well, GLM 5.2 during its training methodology, they specifically mentioned they have this new methodology for reinforcement learning called anti-hacking. Um, so GLM 5.2 introduced a method to stop, you know, reward hacking. Um and what they do is they added a link checker. Um so remember previously we mentioned how SweetBench Pro um the model will cheat and look at the answer. Um and so what GLM did is they had this check. Um so during reinforcement learning they will check every single tool call you make. Um and if the website if the website went to the answer you would stop that from happening. Um and so like GLM essentially outed this like you know filtering system for the entire reinforcement learning process. Um and you know according to them it worked very well

</details>

**Speaker A**: 还要记得这个关于作弊例子的图表。嗯，你知道 opus，似乎 claude 的模型总是喜欢作弊。嗯，而 Jubet 的模型不喜欢作弊。嗯，但主要的结论是模型会作弊，因为你是在，你是在告诉它，你知道的，就像你知道的，我想要最大化奖励 AB CDE EFG。嗯，所以模型会，它会去最大化这个奖励，但它实际上并不会遵循你的意图。嗯，所以你必须在这方面非常小心。

<details>
<summary>Original English</summary>

**Speaker A**: and remember this plot about cheating examples. Um you know opus it seems like claude's models like to always cheat. Um and Jubet's models don't like to cheat. Um but the main takeaway is models will cheat because you are you are telling it you know like you know I want to maximize reward AB CDE EFG. Um and so the model will it will maximize it but it won't actually follow your intent. Um so you have to be very careful on this.

</details>

**Speaker A**: 嗯，事实上对于 GBD 5.1，在它的训练期间，OpenAI 提到过他们有一种叫做计算器作弊（calculator hacking）的情况。嗯，所以在 GBD 5.1 训练的时候，嗯，他们想要奖励网络工具的使用，对吧，所以就像你想要奖励模型去使用网络工具。嗯，但它反而没有使用网络工具，它使用了计算器来伪造网络工具。嗯，所以在 GBD 5.1 的训练期间，就发生了这种情况。嗯，所以就像，你知道的，有非常非常非常非常多的问题。我想他们展示了，是的，他们展示了计算器作弊。你知道的，你在使用了哪个工具上撒谎。嗯，你知道，你隐瞒了不确定性，你捏造了事实。嗯，所以对于嗯奖励破解，存在着非常非常非常多的问题。

<details>
<summary>Original English</summary>

**Speaker A**: Um in fact for GBD 5.1 during its training OpenAI mentioned that they had something called calculator hacking. Um and so in GBD 5.1 when they were training um they wanted to reward web tool use right so like you want to reward the model to use the web tool. Um but instead it didn't use the web tool it used the calculator to fake the web tool. Um and so during the training of GBD 5.1 this happened. Um and so like you know there's many many many many problems. I think they show yeah they showed calculator hacking. You know you lie about which tool you used. Um you know you conceal uncertainty you make facts up. Um so there's many many many problems with um reward hacking.

</details>

**Speaker A**: 而且这不是捏造的，对吧？所以奖励破解已经在大型实验室的训练运行中存在了，对吧？这还仅仅是 5.1。嗯，我不这么认为，所以他们提到了 GB 5.2 或者别的什么。是的，但总的来说，他们表明，你知道的，这件事情确实在现实世界中发生了。

<details>
<summary>Original English</summary>

**Speaker A**: And this is not fake right? So reward hacking is already in large labs training runs right? This is just 5.1. Um I don't think so they mentioned GB 5.2 or whatever. Yeah, but in general they showed that you know this thing does happen in real world

</details>

### GPU Mode 黑客松与测试作弊示例

**Speaker A**: 嗯，你知道的，我不知道你们是否了解 GPU mode，嗯，但是 GPU mode 有这个，你知道的，这个排行榜，嗯，用于，你知道的，编写更快的内核（kernels），所以如果你确实想写你自己的内核，一定要发在 GPU modes 的黑客松挑战赛上。嗯，它们非常非常有帮助，非常有用。嗯，但是你知道，有人设法破解了，奖励破解了 GPU mode 的内核比赛。嗯，记得在矩阵乘法的例子里。我们需要进行两个，有两个，有两个检查，对吧？让矩阵乘法算法更快，但同时它也必须是正确的，对吧？有两个检查，正确性检查和时间检查。嗯，GPU mode 也有两个检查，正确性检查和时间检查。嗯，所以你认为当模型，模型知道，模型实际上知道它正在接受正确性检查的评估时，模型做了什么？对吧，它学到了，哦，我正在接受正确性检查的评估，我现在要让正确性变正确，对吧？所以它会输出正确的内核。然后模型知道它正在被计时，它做了什么，它做了什么呢？它只是，它只执行了一次算法，然后把它保存下来，接着它就跳过了后面所有的 15 个，嗯，你知道的，测试。

<details>
<summary>Original English</summary>

**Speaker A**: um you know I don't know if you guys know GPU mode um but GPU mode does you know this leaderboard um for you know making faster kernels so if you do want to write your own kernels definitely post on GPU modes hackathon challenges um they're very very helpful and very useful um but you know someone managed to hack reward hack the GPU mode kernel competition um and remember in the Matrix multiplication example. There are two there are two there are two checks that we need to do right make the matrix multiplication algorithm faster but also it needs to be correct right there are two checks the correctness check and the timing check. Um and GPU mode also had two checks the correctness check and the timing check. Um and so what do you think the model did when the model the model knew the model actually knew that it was being evaluated on the correctness check right it learned oh I'm being evaluated on the correctness check I will now make correctness correct right so it will output the correct kernel and then the model knew that it was getting timed and what it what did it do it just it just did the algorithm once and then saved it and it skipped all the another 15 um you know tests.

</details>

**Speaker A**: 嗯，这就是模型所做的。所以基本上模型学到了，模型学到了这里有两个测试，正确性检查和时间检查。而模型只把正确性检查做对了，然后一旦进入计时的阶段，它就作弊了。嗯，老实说，这其实相当可怕。所以基本上模型学到了你正在进行这些测试，而且模型实际上知道你正在进行基准测试。嗯，所以这其实非常有趣。嗯，而且你知道，哦是的，这是，这是一个更加，你知道，更大的例子。正确性检查没问题，但在时间检查上它作弊了。嗯，它所做的一切就是启动，你知道，第一次调用本应有 15 次调用。在第一次核心调用中，它执行了整个过程的全部 15 次，对吧？它执行了所有 15 次运行。嗯，然后在核心二到十五中，它只做了一个 Python 字典查找。嗯，是的。

<details>
<summary>Original English</summary>

**Speaker A**: Um and so that's what the model did. So essentially the model learned the model learned that there were two tests, the correctness check and the timing check. And the model only did the correctness check correctly and then once it went into the regime of timing, it cheated. Um to be honest, it's actually quite scary. So essentially the model learned that you're doing these tests and the model actually knows you're doing the benchmarks. Um and so this is actually very interesting. Um and you know, oh yeah, this is this is more an you know, larger example. The correctness check was fine, but the timing check it cheated. Um and all it did is it launch, you know, there was supposed to be 15 calls in the first call. In the first core, it did all 15 of the entire process, right? It did all of the 15 runs. Um and then core two to 15, it just did a Python dictionary look up. Um, yeah.

</details>

**Speaker B**: 我不知道你是否了解这个。这让我想起了大众汽车，他们在那里触发（initi）...

<details>
<summary>Original English</summary>

**Speaker B**: >> I don't know if you know about this. Reminds me of Volkswagen where they initi.

</details>

**Speaker A**: 是的，我... 确实有人告诉我...

<details>
<summary>Original English</summary>

**Speaker A**: >> Yes, I someone did tell

</details>

**Speaker B**: 有人告诉过我这件事。嗯，

<details>
<summary>Original English</summary>

**Speaker B**: >> someone told me about it. Um,

</details>

**Speaker B**: 这非常相似。就像是，哦，我没在做这个。关掉这个，然后...

<details>
<summary>Original English</summary>

**Speaker B**: >> this is very similar. It's like, oh, I'm not doing this. Turn this off and

</details>

**Speaker A**: 是的，完全正确。所以，就像，你知道的，我想不仅是模型会作弊。我想，即使是人类也会作弊。是的。但我认为这叫古德哈特定律（Goodhart's law）。就是那个。就像，如果你有一个基准，那么这个基准就会变成……它是叫好定律（good law）吗？我不记得了。是的。好吧。是的。基准基本上变得毫无用处了，因为人们只会为了最大化奖励而作弊。嗯，是的，我想人类也会作弊。嗯，是的。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah, exactly. So, like, you know, it's not just models, I guess, that cheat. Even humans cheat, I guess. Yes. But I think it's called Goodart's law. That's the one. Like, if you have a benchmark, then the benchmark becomes Is it good law? I don't remember. Yes. Okay. Yeah. The benchmark essentially becomes useless because people just cheat to maximize reward. Um yes, I guess humans also cheat. Um yeah.

</details>

### 声称的性能提升与验证的必要性

**Speaker A**: 好的。哦，我最喜欢的例子是，嗯，在其他实验室，你知道，你在 Twitter 上，或者在任何地方看到，他们说他们把内核做得快了 10 倍。嗯，不，不，不，那不正确。他们并没有让内核快 10 倍。事实上，如果你查看代码，他们里面根本没有，你知道的，没有操作（no ops），所以没有进行任何运算。他们还修改了计时器。你知道的，他们，就像我字面描述的那样，你知道的，我描述过，他们，你知道的，在这里，嗯，你知道，他们修改了计时器，他们把矩阵变成了零，他们作弊了。嗯，所以就像，你知道，这种事真的在现实世界中发生过。所以一些，你知道的，一些实验室，他们发表了论文声称他们把内核做得快了 10 倍。但实际上，如果你通读代码和例子，他们……这些例子全都在作弊。嗯，所以你知道，他们，你知道，就奖励破解而言，这非常不好。你知道，奖励破解是一个非常大的问题。嗯，还有你知道，比如，内核奖励破解的一些例子是什么？你知道的，没有生成真正的 CUDA 代码，而是引发，或者某种，你知道的，已经写好的系统。嗯，你使用了空操作（no up）内核，这本质上是让，你知道的，让 A 和 B 矩阵直接变成零。它所做的就是什么都不做，对吧？它仅仅是……这个内核是空的。嗯，还有你有像内存重用这样的情况，所以你一遍又一遍地重用同一个答案。嗯，你还有时间同步的问题。那就是在计时器上作弊。嗯，我的观点是，就像，你知道，如果你确实发布了更快的内核或者更快的，你知道，矩阵，如果你认为你的 AI 智能体让内核快了 10 倍，请验证一下，你知道，请在发布前查看一下代码，因为这是一个非常……这看起来非常不好。嗯，所以，而且还有一个我感觉人们越来越忘记的最大的问题，就是你知道的，你让内核快了 10 倍，你让矩阵乘法快了 10 倍。有一个……

<details>
<summary>Original English</summary>

**Speaker A**: Okay. Oh, my favorite example is um so on other labs, you know, you see on Twitter, on wherever, they say they made kernels 10 times faster. Um no, no, no, that's not correct. They did not make kernels 10 times faster. In fact, if you look through the code, they have no, you know, no ops, so no operations. They also edit the timer. You know, they, as I literally described, you know, I described, they, you know, over here, um, you know, they edit the timer, they made matrices go to zero, they cheated. Um, and so like, you know, this actually happened in real world. So some, you know, some of the labs, they published papers claiming that they made kernels 10 times faster. But actually if you read through the code and the examples they these examples all cheated. Um and so you know they you know this is not very good in terms of you know reward hacking. You know reward hacking is a very big problem. Um and you know for example what some of the examples of kernel reward hacking you know not generating real CUDA code instead it cause or some sort of like you know already written system. um you have no up kernels which is essentially making the you know making the A and B matrix just zero. All it does is just doesn't do anything, right? It just the kernel is empty. Um, and you have like memory reuse, so you reuse the same answer over and over again. Um, you have timing synchronization issues. So that's cheating on the timer. Um and my view is like you know if you do publish faster kernels or faster you know matrix if you think that your AI agent has made kernels 10 times faster please verify you know please look through the code before publishing because it is a very it's not a very good look um and so and also the biggest issue that I feel like people are getting forgetting is you know you made kernels 10 times faster you made matrix multiplication 10 times faster There is a

</details>

<!-- chunk 17/17 -->

### 矩阵乘法的理论极限与奖励作弊

**Speaker A**: 矩阵乘法是有理论极限的，对吧？关于矩阵乘法，你知道的，你不可能无限期地把它变得更快，因为在如何让它变得更快方面是存在数学极限的，对吧？所以就像，你知道，在很久很久以前的时期，你知道，矩阵乘法的时间复杂度是 O(N³)。你知道，每一次研究人员都在让它变得越来越快、越来越快、越来越快、越来越快、越来越快。你知道，现在它的时间复杂度大概是 O(N^2.371339)，我猜是这个数。你知道，研究人员每年都在努力，试图让这个数字变得越来越小、越来越小、越来越小、越来越小。嗯，你知道，我想就像，你知道，尾数从 1552 降到 1339，这进步幅度其实也不算小，你知道的，我想也不算特别大吧。嗯，但是你知道，他们确实在取得进展，但最主要的观点是，你知道这些研究人员，你知道他们用数学极限展示了你不可能比这个速度更快了，所以你怎么能通过奖励作弊（reward hacking）做到比这还要快呢？嗯，所以最根本的一点是，请一定要验证，你知道，对于那些写研究论文和做类似事情的人来说，请务必确认你们的模型没有在进行奖励作弊。这是一个非常大、非常大、非常大的问题。嗯，你们可以看到，哦，我想我这里只有一张图表。嗯，但是是的，总的来说，请不要这么做，请一定要检查你们的模型。嗯，我想今天的演讲内容就到这里了。嗯，你知道，是的，谢谢大家的到来。哦，好像还有更多问题。嗯，好的，谢谢。

<details>
<summary>Original English</summary>

**Speaker A**: theoretical limit for matrix multiplication, right? Matrix multiplication, you know, it's not you can't make a faster because there's mathematical limits on how to make a faster, right? And so like, you know, matrix multiplication at the very very very olden times, you know, it's O of N cubed. You know, every single time researchers have make it faster and faster and faster and faster and faster. You know, it's now O of N to the^ of 2.371339, I guess. you know researchers every single year are trying to like make this number smaller and smaller and smaller and smaller. Um you know I guess like you know 1 1552 to 1339 is not that small you know not that big I guess. Um but you know they're having progress but the main point is you know these researchers you know they show with mathematical limits you cannot go faster than this and so how can you do reward hacking that is even faster than that. Um and so like the fundamental point is please verify you know to like the people who do research papers and stuff like that please confirm your model is not reward hacking. It is a very big big big problem. Um and you can see oh I think I only had one plot. Um but yes in general please do not do please check your I guess models. Um I guess that's all for the talk. Um you know yeah thank you everyone for coming. Oh more questions as well. Um okay thank you.

</details>

**Speaker B**: 谢谢。我们这边还有——

<details>
<summary>Original English</summary>

**Speaker B**: Thank you. We also have

</details>

**Speaker A**: 哦，是的。我们在那边的盒子里还准备了一大堆贴纸，大家可以随便拿，此外还有一些别针之类的东西。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, yes. We have a whole bunch of stickers that you can take in the box over there and some pins and stuff.

</details>