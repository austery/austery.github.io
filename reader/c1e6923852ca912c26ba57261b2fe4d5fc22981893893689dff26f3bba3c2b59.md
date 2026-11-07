---
author: Latent Space
date: '2026-11-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KgqWyVVH4Oc
speaker: Latent Space
tags:
  - document-parsing
  - agentic-workflow
  - continuous-evaluation
  - model-routing
  - multimodal-ai
title: Reducto CEO Adit Abraham 谈文档解析为何依然困扰 AI、自研端到端模型与初创团队打造
summary: Reducto 联合创始人兼 CEO Adit Abraham 在边做牛排三明治的对谈中，深入分析了 PDF 等非结构化文档处理的核心难点，介绍了自研端到端模型 R1 如何提升精度并降低成本，阐述了对持续评测体系的重视，并分享了团队对专业技能极致追求的工程师文化与白领工作自动化前景。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Adit Abraham
companies_orgs:
  - Reducto
products_models:
  - R1
media_books: []
status: evergreen
---
### 片头高能片段

我以前从来没用叉子煎过牛排。如果 Arth 看到这个，我很抱歉让你当众被点名了。嘿，我们能回应一下那些批评者吗？
<details><summary>Original English</summary>
I've never cooked a steak with a fork before. If Arthur's watching this, I'm sorry for putting you on the spot. Yo, can we address the critics?
</details>

### 开场与牛排推文渊源

>> 大家好，欢迎来到 Latent Space 烹饪秀，在这里我们会邀请创始人和研究人员，让他们自由发挥施展厨艺。今天我们有一位非常特别的嘉宾，Reducto 的联合创始人兼 CEO Adit。欢迎你，Adit。
<details><summary>Original English</summary>
>> Hey guys, welcome to the late space cooking show where we invite founders and researchers and just let them cook. Today we have a very special guest, co-founder and CEO of Reducto, Adit. Welcome Adit.
</details>

>> 嘿，感谢你们邀请我。
<details><summary>Original English</summary>
>> Hey, thanks for having me.
</details>

>> 好的，没问题。其实我们是通过 Adele 牵线的，起因是一条发了牛排照片的推文火了，对吧？你在推文里煎了一块看起来很不错的牛排。
<details><summary>Original English</summary>
>> Yes, of course. And we actually got connected through Adele after a tweet went viral, right? Where you could I thought a really good looking piece of steak.
</details>

>> 我当时觉得那块牛排棒极了。
<details><summary>Original English</summary>
>> I thought it was incredible,
</details>

>> 但大家都在评论区抨击你。事情是这样的吧？
<details><summary>Original English</summary>
>> but people were ratioing you. Is that correct happened?
</details>

>> 没错。当时有人提出了一些指控，我们今天会一一回应。
<details><summary>Original English</summary>
>> Yes. There were some allegations made um that we'll address today.
</details>

>> 好的。行，今天我们就来正名并开始动手。今天我们要煎牛排，还会做奇米秋里酱（chimichurri），所以我们可以直接开始了。能麻烦把欧芹递给我吗，我们先把欧芹切了？
<details><summary>Original English</summary>
>> Okay. Yeah, we'll redeem today and we get started. So today we have steak and we also have chim cherry that we'll make and so yeah, we can get started. Do you want to hand me the parsley and we can start cutting it?
</details>

### 从 Remember All 到 Reducto：创业方向的转型

>> 好。在开始之前，我其实挺好奇的。你们最初加入 YC 时创办的公司叫 Remember All，对吧？甚至到了今天，你们的公司叫 Reducto。所以我在想，这和《哈利·波特》有什么渊源吗？你们是不是……
<details><summary>Original English</summary>
>> Yeah. Um, and before we start as well, I was kind of curious. You initially joined YC with this company called Remember All. That correct? And even today, your company's called Reduct. And so I was wondering, are there any ties with Harry Potter? Are you
</details>

>> 经常有人这么问。
<details><summary>Original English</summary>
>> We get that a lot.
</details>

>> 好吧。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 嗯，对。具体的故事是这样的：进 YC 的那天，我们就知道自己会从 Remember All 转型。我们当时就告诉了 Diana：“嘿，我们觉得我们不会继续做这个方向了。”我们当时并不知道具体要转型去做什么。大体上的想法是，我们要为开发者打造神奇的工具。然后我们在群聊里发起了一个投票，列出了一堆名字以及各自可用的域名……
<details><summary>Original English</summary>
>> Um, yeah. So the story here is uh we knew we were going to pivot from remember all. The day we got into YC, we told Diana like, "Hey, we don't think this is what we're going to pursue." Um, and we we didn't know what we would pivot into specifically. Um, there was this like general idea of we'll make magical tools for developers and we made like a a poll in a group chat saying here are the names and the domain names available for each
</details>

>> 然后这个名字胜出了？
<details><summary>Original English</summary>
>> and this one the name
</details>

>> 里面有些名字其实挺糟糕的。但是……
<details><summary>Original English</summary>
>> got some horrible names in there. But
</details>

>> 是的，但我想你也知道，发生了很多变化。当时做的还是……
<details><summary>Original English</summary>
>> yeah, but I guess you know a lot has changed uh going from at that time it was
</details>

>> 长周期记忆，或者单纯是给……
<details><summary>Original English</summary>
>> long horizon memory or just memory for
</details>

>> 给智能体（Agent）用的记忆，而如今你们在做的是文档解析或处理。
<details><summary>Original English</summary>
>> memory for agents agents and then today you're working on document parsing or processing.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yep.
</details>

### PDF 解析的本质：从打印机驱动到自动驾驶般的视觉难题

>> 为了给观众补充一些背景，你能不能进一步拆解一下这个问题的核心难点，甚至讲一讲从传统的 OCR 到 IDP（智能文档处理），再到如今结合视觉语言模型（VLM）和智能体的演变历史？
<details><summary>Original English</summary>
>> Um and I guess to contextualize for the audience do you want to u provide some more like breakdown of the core crux of the problem and even maybe some history going from OCR to IDP and now today with VLNs and agents.
</details>

>> 好。其实几十年来一直都有公司在做 PDF 处理。比如我遇到过一个人，他从事 PDF 处理的时间比我的年龄还长。毫不夸张地说，他当年做的是打印机打印 PDF 所需的原始驱动程序。
<details><summary>Original English</summary>
>> Yeah. So, I mean there's um a few decades worth of companies that have worked on PDF processing. Like I I met this guy that had worked on PDF processing longer than I've been alive. Like quite literally he worked on the original drivers for printers to print PDFs.
</details>

>> 不过，人们现在处理文档的语境显然大不相同了。这些格式是通用的横向格式，很多人都会用它们来编目整理信息，是各家企业都会使用的一套统一数据载体。所以，如果你想让模型来承担大量原本由人类完成的工作，在读取文档时具备达到人类级别的保真度就变得极其重要。
<details><summary>Original English</summary>
>> Um the context in which people process documents is obviously very different though in that like these are just horizontal formats that a lot of people will use for you know cataloging information. and it's a a unified set of data that people will use across enterprises. And so if you're going to have models do a lot of human work, it becomes really important that you have human level of fidelity when you're reading it.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mh.
</details>

>> 棘手的地方在于——正如我刚才提到那位做打印机驱动的前辈——PDF 作为一种文件格式，其最初的设计语境是为了让打印机能够忠实还原原件，对吧？所以它在设计之初根本没有考虑到“由智能体来阅读”这类问题。于是我们就深深陷进了这个兔子洞：你究竟怎样才能像人类那样去阅读这些文档？
<details><summary>Original English</summary>
>> And the tricky thing is I I hinted at this with the guy that's um worked on printer drivers. Like the original context for PDF as a file format was for printers to be faithful to the original, right? And so it wasn't really designed around this sort of problem of agents are going to read it. And so we just got really really deep in this rabbit hole of how can you read these documents the way that a human would.
</details>

>> 这实际上是一个极其困难的计算机视觉问题。
<details><summary>Original English</summary>
>> Um which is a really hard vision problem.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我们经常把它比作自动驾驶汽车的研究。汽车里的车道保持辅助系统已经存在很长时间了，但这和说你的 Waymo 能够完全端到端自动驾驶是截然不同的两码事。这就是我们在 Reducto 想要达到的标准。
<details><summary>Original English</summary>
>> We liken it a lot to self-driving car research. Uh and that there's been, you know, lane assist in cars for a long time and it's a very different thing to say that your Whimo will drive fully end to end autonomously. That's the sort of bar that we want to get to with Reductto.
</details>

### 从单纯解析到横向智能体平台与底层模型架构

>> 明白了，懂了。那这么说来，你们也是一个面向智能体的平台。
<details><summary>Original English</summary>
>> Gotcha. Okay, that makes sense. And I guess you guys are also an agentic platform. Mhm.
</details>

>> 除了能和很多智能体交互之外，这通常还包含什么？在你的设想中，它是否也会成为一个横向平台，覆盖范围不仅限于处理和解析，甚至还包括编辑、提供一个供客户使用的无代码 Studio？
<details><summary>Original English</summary>
>> Um, and I guess what does that generally entail beyond just being interactable with a lot of agents? Like do you see it also being like a horizontal platform where you cover beyond processing and parsing to even editing and having a noode studio that clients can use?
</details>

>> 是的，可以这样去理解：只要是模型与文档、或者更广泛地说与非结构化文件发生的任何交互，我们都希望 Reducto 能够成为实现这种交互的最佳途径。明白了。这意味着读取文档（比如解析它）、对信息进行分类、对其进行编辑。人类工作中有很大一部分就是从文档中读取信息，然后再写入文档。
<details><summary>Original English</summary>
>> Yeah, the way to think about it is any sort of interaction that a model has with a document or unstructured files in general, we want reductive to be the best way for that interaction to happen. Gotcha. That means reading the document like parsing it, classifying that information, editing it. So much of human work is people reading from documents and writing into documents. Yeah,
</details>

>> 它将负责处理从提取数据、与其他文档进行比对调和，直到生成客户所需最终输出的全流程。
<details><summary>Original English</summary>
>> that will take care of everything from extracting that data, reconciling it against other documents and then getting the end output that they needed.
</details>

>> 明白了。那你们会考虑模型路由（Routing）吗？因为我在官网上看到，Reducto 底层使用了 12 个以上的模型。针对不同的任务和文件，你们在选择更便宜的模型还是更贵的模型之间，决策框架是怎样的？
<details><summary>Original English</summary>
>> Gotcha. And do you guys consider routing because I read on the website Redu under the hood has 12 plus models and so what's the decision framework between choosing a cheaper model, let's say, versus a more expensive one for different tasks and files. So the tricky thing here is that a lot of it is ultimately a longtail problem,
</details>

>> 这里的难点在于，很多时候这归根结底是一个长尾问题，对吧？你可能会遇到很多页面看起来就只是纯文本，但冷不丁某处就会出现一张极其复杂的表格，而你事先根本无法确切知道究竟是哪一页会有这些内容。
<details><summary>Original English</summary>
>> right? And so you'll have a lot of pages that look like they're just text and then every once in a while you'll have this really complex table and you're not going to know exactly which page had that or anything like that.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以我们最初的想法是：好吧，我们用许多较小的传统计算机视觉模型来做基线处理，然后把大模型用在非常困难的任务上。不过随着时间的推移，我们在模型架构本身上摸索出了一种非常有趣的路径。我们打算在周一正式宣布这个消息……也就是我们新的自研模型，我们称之为 R1。它将能够端到端地完成这一工作。既包括识别页面布局等环节，也包含了确保尽可能接近 100% 精度所必需的最后一公里校正。
<details><summary>Original English</summary>
>> And so we started with this idea of okay, we'll use a lot of smaller traditional CV models for the baseline and then we'll use larger models for the really hard tasks. Um over time though we've been able to have this like pretty interesting approach to just the model architecture. We're going to announce this on Monday uh which is our new like in-house model. We're calling it R1 which is going to be able to do this end to end. So that components of you know capturing the layout and all that but also the last mile corrections that you'd want to make sure that you're at as close to 100% as possible.
</details>

### 自研模型 vs 调用外部模型：帕累托前沿的权衡

>> 明白了，好的。那太棒了。我们现在应该可以把欧芹放进去了。感觉粗略切碎一下，然后加入其他配料就行。回到你刚才提到的新模型，在决定是“拥有智能”还是“租用智能”之间，你的决策框架或者心智模型是什么？因为去年你们为了测试推出过基于 Qwen VLM 构建的 ROM OCR。而随着新模型的推出，似乎你们正在专注于自研，不再依赖第三方提供商。
<details><summary>Original English</summary>
>> Gotcha. Okay. That's pretty great. Are you We could probably add the parsley now. feel like just have it relatively chopped and then add the other elements. But yeah, I guess going on to what you mentioned with this new model, what is your framework or even mental models behind determining whether to own your intelligence versus rent it? Um because last year, even though it was for a test, you had ROM OCR, which is built on top of the Quen VLM. Um and with this new one coming out, it seems like you're maybe focusing on that and not depending on providers.
</details>

>> 是的。我们团队的理念或核心准则是：无论如何，我们都要成为市面上最好的服务提供商。我们的客户在思考时并不会去纠结“Reducto 到底是用自研模型还是别家的模型”。他们只想要无懈可击的结果。
<details><summary>Original English</summary>
>> Yeah. So our thesis or like mandate for us as a team is we want to be the best possible provider no matter what like our customers don't think in terms of is reductive using in-house models or something else. Um they just want incredible results.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以我们不想单纯从“是不是自研”的角度来看待这个问题。随着时间推移，自然发生的一件事是：我们极其看重准确率、成本和延迟之间的帕累托前沿（Pareto frontier）。我们不断发现，如果针对某一特定类型的任务，专门针对该任务进行后训练（post-trained）的模型在上述这三个维度上的表现都更胜一筹。
<details><summary>Original English</summary>
>> And so we don't want to look at it as is it in-house or not. The thing that's happened naturally over time is we care a lot about that sort of perto frontier of accuracy, cost and latency. Yeah. And we keep finding that if you are looking at a specific type of task, a post-trained model on that task outperforms on all three dimensions.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 因此，随着时间的推移，我们的技术栈越来越向自研倾斜。目前仍然存在一些非常通用的横向任务，使用前沿的基础模型会很合理，但如今这类任务在适用范围上已经比较有限了。
<details><summary>Original English</summary>
>> And so our stack has shifted more and more towards in-house over time. There are still like really horizontal tasks where uh Frontier just foundation model makes sense, but that's limited in scope today.
</details>

### 精确率与召回率的陷阱：为何基础模型会静默漏掉数据

>> 很好。好的。下一步，你要切一下桃子吗？这样我们可以烤一些。你想用这个新的砧板吗？
<details><summary>Original English</summary>
>> Great. Okay. And so for the next thing, do you want to cut the peaches so we can maybe get some grilled and I can Do you want to take this new cutting board?
</details>

>> 好的，谢谢。那我就拿这个来切。另外，你之前真没开玩笑，边做饭边聊天确实很容易分心。
<details><summary>Original English</summary>
>> Yes. Thank you. And then I'll just take this so that I can. Also, you weren't joking about uh it being distracting to talk while you cook.
</details>

>> 是啊。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。你们最近推出了 Deep Extract，并且公布了基准测试，表明评测外壳（Harness）的性能超过了许多基础模型。对此，如果有人来问你：“我为什么不能直接等这些基础模型的性能提上来，这样就不需要这个 Harness、直接用基础模型就行，何必来找你们？”你对这种观点怎么看？
<details><summary>Original English</summary>
>> Yeah. And you guys recently launched the deep extract um and had the benchmark showing that the harness outperforms a lot of the base models. Yep. Um, and I guess how do you view the people come to you and say, "Why can't I just wait for these base models to get to the performance level and not need this harness and just use that compared to going to you guys?"
</details>

>> 我觉得这次新发布中最有意思的事情之一是……不知道你有没有读过那篇博客，我们发现精确率（Precision）和召回率（Recall）之间存在一种非常奇怪的权衡。当你将推理时间设为无上限时，很多这类专门的文档处理平台的表现其实比前沿模型更差。
<details><summary>Original English</summary>
>> I think one of the most interesting things with the new launch was uh I I don't know if you had a chance to read the blog, like we found this really weird trade-off between precision and recall. And so a lot of these specialized document processing platforms were worse than frontier models uh when you set uncap reasoning time.
</details>

>> 但前沿模型的失效模式却出在召回率上。它们会静默地丢掉几行数据，漏掉某些上下文片段，诸如此类。
<details><summary>Original English</summary>
>> But the failure mode for the frontier models was on recall. So they were silently dropping rows um missing bits of context like those sorts of things.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 如果考虑到你的数据提取层直接把信息彻底漏掉了，这种形式的数据损失你在生产环境中根本查不出来，对吧？因为你一开始就不知道自己漏提取了什么。这就凸显了围绕模型搭建 Harness、确保并审查审计提取结果是何等的重要。
<details><summary>Original English</summary>
>> And if you're thinking about your extraction layer just missing information altogether, that's the sort of loss pattern that you're just not going to find in production, right? like you don't know what you failed to extract in the first place. Um and those are the sorts of things where having a harness around making sure and auditing the results becomes really really important.
</details>

>> 明白。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我并不觉得这是非此即彼的对立关系。确实存在某些任务，前沿模型处理起来非常棒。但如果你是在寻找针对某项任务最高效的工具，你可能应该根据正在处理的具体任务进行专业化定制。
<details><summary>Original English</summary>
>> Um where I don't see it as either or like there are certainly tasks where a frontier model is great. But if you're looking for the most efficient tool for the task, you should probably specialize in terms of the task you're doing.
</details>

### 基准测试的营销乱象与独立评测

>> 确实，有道理。而且针对这次发布，你们是和 Micro1 合作构建了基准测试。
<details><summary>Original English</summary>
>> Yeah. No, that makes sense. And I guess even for the announcement, you work with micro one to create benchmark.
</details>

>> 没错，是的。
<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

>> 你怎么看待与性能绑定的评测基准，以及大家对在不同基准任务上疯狂刷榜（Benchmaxing）而导致性能参差不齐（Jagged performance），反而脱离真实世界任务的担忧？
<details><summary>Original English</summary>
>> And I guess how do you think about um eval benchmarking tied with performance and even the concern of jagged performance for like benchmark benchmaxing y um across like the different tasks compared to like real world tasks.
</details>

>> 我们内部显然做了大量的基准测试。让我感到沮丧的一点是，如今基准测试基本上已经变成了营销物料。每个人在自己的基准测试里都是第一名，所以整个环境很快就变得极其嘈杂。
<details><summary>Original English</summary>
>> So we obviously do a lot of benchmarking internally and something that's frustrating for me is benchmarks largely have become marketing material. M um everybody's number one on their own benchmark and so there's just this it becomes really really noisy really quickly.
</details>

>> 我们之所以选择与 Micro1 合作，就是想划清一条界线：不是由 Reducto 来挑选测试文档，不是由 Reducto 来设定标准答案（Ground truth），Reducto 也没有通过任何手段去操纵结果。就是为了确立一个基准：这是一个独立的第三方基准评测。
<details><summary>Original English</summary>
>> Um and so the reason why we worked with micro one was we just wanted this like clear line drawn of reducto is not choosing the documents. Redduck is not setting the ground truth. Product is not you know manipulating the results in any which way. Um just so there's this baseline of it's an independent benchmark. Um
</details>

>> 当然，即便是这样也称不上完美。我认为归根结底最关键的，还是大家亲自拿自己的文档去测试。但至少它给出了一个大致的方向，让大家可以开始思考这些问题，而这正是我们所关心的。
<details><summary>Original English</summary>
>> even that obviously is not perfect. I think at the end of the day, the thing that matters most is for people to try things on their own documents. Yeah. Um but at least it gives like a directional sense for people to start thinking about these sorts of things which is all we care about.
</details>

### R1 模型发布与百万级文档处理的规模化

>> 明白。结合你们近期发布的 R1，这是否意味着你们做事方式的转变？在研发它的过程中，有没有什么有趣的发现？
<details><summary>Original English</summary>
>> Gotcha. And I guess tying in your recent launch R1 um does this indicate a change in how you guys will um do things? Is there anything interesting that you guys discovered while working on it?
</details>

>> 我认为 R1 对我们来说是迈出的一大步。因为在过去的一段时间里，我们的锚点一直在于“Reducto 会是你尝试过的产品中准确率最高的”，对吧？特别是随着我们开始承接体量更大的业务——如今 Reducto 每月处理的页面数量略超过 10 亿页。而且这个数字还在迅速增长。
<details><summary>Original English</summary>
>> Uh I think R1 is a really big step forward for us because for a while we had the sort of anchor points of reductive is going to be the most accurate thing that you've tried, right? Um and especially as we start doing larger volume work like today reducto processes a little over a billion pages every single month. Um and that number keeps changing really quickly.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 在这种情况下，推动帕累托前沿的平衡、让它能够适用于各种不同的使用场景就变得至关重要。我之所以这么喜欢 R1，不仅因为它在准确率维度上有所提升，还在于它将极大地简化我们的定价结构以及客户在生产环境中接入产品的方式。
<details><summary>Original English</summary>
>> it becomes really important to have that sort of perto frontier conversation of making this available for all sorts of different use cases. Um, the reason why I like R1 so much is it's not just an improvement from the lens of accuracy. It's also going to really simplify our pricing and the way that our customers get to adopt the product in production.
</details>

>> 之前如果开启智能体（Agentic）特性或类似功能，我们会按倍数加价。是的，这些现在统统取消了。R1 的计费方式变成了：你直接把文档发给我们，其单页成本甚至低于我们基础模型原先的单页价格，却能获得比我们此前最高精度模型更好的准确率。
<details><summary>Original English</summary>
>> So for a while we would have these multipliers if you were turning on aic features and things like that. Yeah, that's all going away. Um, our one is just you send us the documents, it it'll be less than the per page cost of our base models for better accuracy than our most accurate models.
</details>

>> 哇，好的。这么说价格确实优惠了非常多。
<details><summary>Original English</summary>
>> Oh wow. Okay. Yeah. So like the pricing is definitely a lot better um
</details>

>> 毫无疑问，绝对如此。比我们过去的收费便宜了好几倍。
<details><summary>Original English</summary>
>> by far and away. Like it's multiples cheaper than where we used to be.
</details>

>> 明白了。天呐，如果是按照你们很多客户目前的使用体量来用 Reducto，这确实非常令人兴奋。
<details><summary>Original English</summary>
>> Gotcha. Dang. That is pretty exciting if you use Redducto at the scale that a lot of your customers do.
</details>

>> 确实是这样。
<details><summary>Original English</summary>
>> Exactly. Yeah.
</details>

### 低容错行业、置信度机制与可追溯性

>> 这让我想起你提过的一点：你们很多客户所处的行业容错率极低。我很好奇，面对比如 99% 的准确率依然不够用的系统或性能指标，你们是如何去思考评测或者设定的？比如在医疗保健这类低容错行业中，如果在企业真正需要的极少数用例上出现失误，或者面对非对称用例时，你们会如何考量和评估？
<details><summary>Original English</summary>
>> Yeah. Which reminds me, you mentioned that a lot of your clients are in industries that have very low margin of error. Mhm. And I was kind of curious how you maybe think through um evaluating or even setting metrics for systems or even performance where let's say 99% accuracy may still not be enough if it fails on like the few use cases that um an enterprise really needs in let's say healthcare or a very low margin error industry. Yeah. Like asymmetrical um use cases. How do you like think through evaluating that and considering that? So
</details>

>> 首先，第一层问题是：在理想状态下，初次解析就应该尽可能做到最准。显然，我们的大量精力都投入在这上面。但第二点在于，永远不存在真正意义上的绝对完美。即使你已经极其擅长识别页面上的内容，仍然可能存在歧义等情况。
<details><summary>Original English</summary>
>> the first order problem is ideally our first pass should be as accurate as possible. Um and obviously that's where a lot of our head space is. But the second thing is there's never going to be a line for truly perfect. Like even if you get really really good at reading what's on the page, maybe you have ambiguity or things like that. Um
</details>

>> 因此，可追溯性（Traceability）变得极其重要。比如能够清楚知道某个信息是从哪里提取出来的；在人工复核时，能够准确指明人类应该查看哪一部分。此外，还需要具备精准的置信度评分（Confidence Scoring），让他们知道什么时候该对某项内容进行复查。如果你要做医疗文档工作流这类事情，这些环节就变得非常非常关键。
<details><summary>Original English</summary>
>> and so traceability becomes really important. like being able to know where something was extracted from, being able to say uh exactly what a human should look at if they're reviewing it. Um and also having things like accurate confidence scoring so they know when to look at a certain thing. Um that becomes really really important if you're going to do something like healthcare document workflows.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以在内部做基准评测时，我们不仅仅衡量提取准确率。我们还会评估：在那些不够完美的情况中，我们能以多高的可靠性上报给人工、告知其结果并不完美？所有这些细节都极其重要。
<details><summary>Original English</summary>
>> Um and so internally when we do benchmarks, we don't only measure ourselves on extraction accuracy. We say like of the things that weren't perfect, how reliably could we escalate to a human that this is not perfect? All of that kind of stuff really matters too.
</details>

>> 明白了。所以你们是不是会把所有最难的失败案例记录下来，汇编成数据集，以便在运行测试时确保 Harness 没有出现性能退化（Regression）？
<details><summary>Original English</summary>
>> Okay. And so do you I guess keep track of all the hardest failure instances and then put that in like a data set that you could run to make sure that there are no regressions with like your harnesses.
</details>

>> 我们确实在这方面做了大量工作，是的。
<details><summary>Original English</summary>
>> We do a lot along those lines. Yeah.
</details>

>> 好的。能展开讲讲吗？比如你们有没有使用什么具体的基础设施工具，或者什么框架……
<details><summary>Original English</summary>
>> Okay. Can you double click into that like are there specific infrastructure tools that you use or frameworks that
</details>

### 烹饪间隙：切桃与持续评测机制

>> 我应该先问一下的：你想让我怎么切这些桃子？
<details><summary>Original English</summary>
>> I should have asked before. How do you want me to choose features?
</details>

>> 完全随你。如果你想切成那样的小块也可以，或者切薄一点。我本应该竖着切成薄片的。没关系，我们还有很多桃子，可以吃这些……
<details><summary>Original English</summary>
>> So this is completely up to you. So if you want to do it slices like that that's fine. You want to do it thinner. I should have done thin vertical slice. Okay, we also have a lot of peaches, so we can eat those and then
</details>

>> 用较薄的来烤，然后夹进你的三明治里。
<details><summary>Original English</summary>
>> use the thinner ones to grill and put on your sandwich.
</details>

>> 好的。不过，回到你刚才聊的框架、工具，以及你们如何捕捉这些失效案例并针对它们做基准测试。
<details><summary>Original English</summary>
>> Um, but yeah, again, back to like your framework or tools or how you think about um catching these failure cases and then benchmarking against them.
</details>

>> 好。我们在公开场合不太常聊的一点是，我们的 ML 团队在持续评测（Continuous Evaluations）上投入了大量时间。也就是能够在生产环境中捕捉到那些即便没有出错、但也存在缺陷的问题，这使我们有能力开始理解在真实业务场景中，什么是超出分布范围（Out of Distribution）的情况。
<details><summary>Original English</summary>
>> Yeah, something we don't talk about as much publicly is our ML team puts a lot of time into continuous evaluations. So being able to spot things that are maybe not incorrect but even just imperfect in production um which gives us the ability to start understanding what is out of distribution for real world use cases.
</details>

>> 嗯。这关键不在于单个数据点本身，更多是在于失效模式的整体规律。比如在医疗行业，我们非常重视了解具体痛点。
<details><summary>Original English</summary>
>> Mhm. to Yeah. Um and it's not about the individual data point itself. It's more so about patterns of failure modes. Like we care a lot about being able to know in healthcare.
</details>

>> 没错，你可以声称自己关注手写文字识别，也可以对手写表现进行基准测试。但你可能手里并没有足够多的倾斜页面手写数据样本，比如某人胡乱写到了表格网格线外面去。哪怕仅仅是掌握自己的短板在哪里，也是迈出的第一步，这样你才能捕捉到下一轮模型训练时想要囊括的内容。
<details><summary>Original English</summary>
>> Yes, you can say that you care about handwriting and maybe you benchmark your handwriting performance. Um, but you might not have a lot of data points that are handwriting on a tilted page where you know somebody scribbled outside the grid lines. Um, and those just knowing where you're falling short is the first step for you to be able to catch the sorts of things that you want to include in your next training run too. Mhm.
</details>

### 通用基元与跨行业视觉直觉的复用

>> 你们有特定行业的评测标准吗？因为我想医疗公司和律师事务所的需求大概率是不同的，但律所之间、医疗公司之间内部会有更高的相似性，尽管这两类行业彼此差异很大。
<details><summary>Original English</summary>
>> And do you have industry specific um I guess criteria cuz I assume the needs at a healthcare company may want versus a law firm will probably differ. Um but like the law firms may have closer similarities and the healthcare companies may have closer similarities as well. Even though the industries are different.
</details>

>> 是的，尤其在创业早期，我们内部经常就此争论。因为做垂直领域的专用文档处理平台要容易得多。
<details><summary>Original English</summary>
>> Yeah. Um this was a debate we had a lot in the early days especially because uh it's a lot easier to build a vertical specific document processing platform.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但这里需要做的权衡是：我认为绝大部分文档归根结底都能解构为极其相似的基本图元（Primitives）。人们往往把这一点视为理所当然。作为人类，你看向页面时会做出一系列瞬间的基本判断，对吧？
<details><summary>Original English</summary>
>> Um, the trade-off that you make there is I think a lot of documents ultimately boil down to very similar primitives. Like people take this for granted. You as a human when you look at a page make a lot of fundamental judgments that are just snap judgments, right? Like
</details>

>> 每次两个段落之间出现间距时，你就会明白：好吧，这是一个新的语义信息块。你甚至不会有意识地去感知这一点，但它就是一种直觉。
<details><summary>Original English</summary>
>> every time there's a gap between two paragraphs, you know, okay, this is a new semantic block of information. You don't like consciously perceive that, but it's intuitive.
</details>

>> 是的。其他所有的东西基本也都可以归结为类似的原理。比如你天然就能理解表格结构是如何将两个维度上的信息关联起来的，诸如此类。我们在确保系统能够抗住医疗领域传真件里那些杂乱表格所做的研发，意味着我们在面向金融行业客户提供可靠方案时，天然就会表现得更好。
<details><summary>Original English</summary>
>> Yeah. And everything else kind of boils down to a similar thing like you naturally understand you know how a table structure is associating two dimensions of information all that kind of stuff. Yeah. Um and the work that we do on making sure that we are resilience to you know messy tables and healthcare that were faxed means that we are naturally better at offering a reliable solution for our customers in finance as well.
</details>

>> 总体而言这是一项难度更大的工程，但我认为最终结果是，这让我们能够跨不同行业客户去解决最棘手的案例。
<details><summary>Original English</summary>
>> Um and so it's like a a harder undertaking overall. Yeah, I think in nets it just means that we can serve the most challenging cases across these customers.
</details>

>> 明白了。所以你们从不同行业积累的认知其实是重合相通的，因为你们聚焦的是相同的基元，并且……
<details><summary>Original English</summary>
>> Gotcha. So all the learnings that you have from different industries kind of have that overlap since you're focused on the same primitives and like
</details>

>> 是的。基本上就是把人类审阅文档时的直觉灌输进模型里。
<details><summary>Original English</summary>
>> Yeah. Um basically building the intuition that a human has when they look at a document into like your models.
</details>

>> 这就是目标。当然各行各业也会有细微差异，比如在法律领域，你可能会非常关注删除线和下划线，这在医疗领域可能没那么重要；但拥有这种底层的基本直觉对我们来说至关重要。
<details><summary>Original English</summary>
>> That's the goal. Yeah. And obviously there are going to be nuances like if you're in legal you probably care a lot about something like strikethroughs and underlines um matters a bit less in healthcare but just having that baseline intuition is really really important for us.
</details>

>> 有道理。这也是 Reducto 未来的愿景吗？永远不会变成单纯做垂直业务的公司，而是彻底做横向，让任何行业、任何企业都能获得一套表现优异的高专业化又高通用性的解决方案。
<details><summary>Original English</summary>
>> Yeah that makes sense. And is that kind of the future vision as well of reducto where which won't ever become verticalized will be horizontal through and through um so that any industry any company will have a very specialized or very general solution that performs well.
</details>

>> 没错。我们不想在面对像解析这类客观任务时陷于被动。在给定的页面上，你可以非常明确地指出页面上究竟写了什么，对吧？我们希望这部分是横向通用的，是零样本（Zero-shot）即开即用的。而对于涉及主观判断的事情——比如金融团队可能对某个指标有独特的定义——那些内容应该支持 Prompt 引导和灵活调整，并随时间迭代完善。
<details><summary>Original English</summary>
>> Yeah. We don't want to be in a situation where for objective tasks like parsing you can very clearly say on a given page like hey this is exactly what was on the page right um we want that to be horizontal we want that to be zero shot for things where it's a matter of opinion like maybe a finance team has a different definition of a certain metric yeah those things should be promptable and steerable and improve over time
</details>

### AI 智能体浪潮下的工程师文化与全天面试

>> 确实，有道理。从整体来看，针对 Reducto，你是如何看待这场 Agent 和大语言模型的爆发浪潮的？你们在文化上是否做了很多调整来拥抱它？比如强制工程师使用编程 Agent，或者在内部搭建很多自动化工具？还是说你们主要是在将所有精力集中在客户要用的产品上，亦或是二者兼有？
<details><summary>Original English</summary>
>> true okay that makes sense and I guess Just overall with respect to reductto um how have you kind of perceived this whole boom of agents and LNS? Um is it something that you've kind of made a lot of cultural changes to to I guess adopt and like force your engineers to use coding agents um or even like internally have a lot of tooling or is it mainly like you're trying to focus all of these efforts towards a product that your customers will use or even a mix of both?
</details>

>> 我的联合创始人非常年轻。这是他大学毕业后的第一份工作，所以我觉得他恰好是你所能见到的最具大模型原生思维（LLM-native）的人之一。比如你发消息给他，回复可能直接就是通过 ChatGPT 发回来的。因此在这种氛围下，我们并不需要强制工程师要求“大家必须使用 Claude Code”或类似规定。大家看到他以及团队其他人做的事情，自然而然就会想去效仿。
<details><summary>Original English</summary>
>> Yeah, my co-founder um is very young. Um this is his first job out of college and so I think he he happens to be one of the most LM native people you'll meet. Um like you'll send him a message and it'll be like sent by a chat GPT back. Um and so given that I I think he just naturally it's not that we're mandating our engineers and saying like you must use cloud code or anything like that. Um it is very natural for people to see the sorts of things that he and others on the team are doing and like want to do it.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 让我觉得特别有意思的一件事是，我们的销售团队现在会大量使用 Devin。大家会为潜在客户定制网站之类的东西。这并不是自上而下强推的结果。大家只是开始意识到：“哎呀，我在 Google Slides 上花了大把时间，结果发现用 Claude 做出的方案设计，比你费尽心思做的还要好。”于是大家就直接用起来了。这更多的是在于展示其潜在价值，胜过一切说教。
<details><summary>Original English</summary>
>> One of the most interesting things for me is like our sales team now uses Devon a ton. Um Wow. Like people will make custom websites for prospects and things like that. Yeah. Um and it wasn't really a top down push. I think people just started seeing like, hey, I'm spending a ton of time in Google Slides and it turns out that cloud design can just make a proposal better than you know what you put effort into. Yeah. Um, and so they'll just do that like it's more about showing what the value could be more so than anything else.
</details>

>> 明白了。所以这是一种以身作则的带动——你的联合创始人频繁使用，然后员工就会觉得：“哇，也许我也应该试试，让自己变得更高效？”
<details><summary>Original English</summary>
>> Gotcha. So, was it like a lead by example like your co-founder was using it a lot and then your employees were like, "Oh, wow. Like I should maybe try it out as well and become more efficient?"
</details>

>> 是的，不仅如此，我们在现场面试以及常规面试中从第一天起就允许使用大模型。我们的现场面试是整整一整天的 Onsite，你要和团队一起度过 8 个小时。如果你不用好大语言模型，那些问题基本上是非常难以解出来的。我觉得从本质上讲，最终能通过这种现场面试的人，通常都是非常擅长高效使用编程工具的人。
<details><summary>Original English</summary>
>> Yeah, it was that plus um we've allowed LLM and on-sites since day one or just interviews in general and our on-sightes are actually like a full day onsite. So, you spend 8 hours uh with the team. Oh, wow. Yeah. And the problems end up being really difficult to actually solve for unless you use LMS properly. Like I I think just by nature, the people that end up making it through the on-site Typically are people that know how to use coding tools effectively.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我们还会遇到一些极端案例。比如我们团队里有个叫 Arth 的小伙子——如果 Arth 在看这期节目，很抱歉当众cue你——Arth 还在伯克利上学时就加入了我们，来现场面试时才大概 20 岁。GPT-3 最早出来的时候他才大一。如果你看他写代码，就感觉像看一个精神极度亢奋的人一样，同一时间手头上同时进行着无数件事情。
<details><summary>Original English</summary>
>> And we'll see some extreme cases where there's this guy on our team named Arth. Uh if Arth is watching this, I'm sorry for putting you on the spot. Um Arth joined us while he was still a student at Berkeley. Um he was like 20 years old when he came on site. Wow. And so he was a freshman when GPT3 first came out. Yeah. Um, and if you watch him coding, it's kind of like watching a crackhead just like in terms of the number of things that he has going on at one point. Um,
</details>

>> 在他身上发生的最疯狂的一件事是：我记得当时给了他我们标准的软件工程现场面试题，他差不多 2 个小时就全搞定了。Ronic 在 Slack 上非常焦虑地私信我说：“糟了，他会觉得极度无聊的，我们该怎么办……”于是我们把整套机器学习工程的现场面试题也都扔给他做了。这就是我们极力想要招进团队的那种人才。
<details><summary>Original English</summary>
>> and the craziest thing with him in particular was I remember we gave him our standard software engineering onsite. Mhm. And he did all of it in like 2 hours. Oh wow. Um, and so Ronic was DMing me on Slack, really stressed, saying like, "Shoot, he's going to be really bored. Like what do we And so we gave him our entire ML engineering onsite, too. Um, and that's the kind of person that we want to make sure we include on the team.
</details>

### 人才招聘理念：对自身技艺的极端痴迷

>> 哇，这绝对是极其理想的招聘对象。非常适应前沿工具，而且行动极其迅速。好的。你想尝尝奇米秋里酱吗？想。我觉得桃子切成这样差不多可以了。那边有勺子可以用。我们把喷枪准备好炙烤。
<details><summary>Original English</summary>
>> Wow. Yeah, that's a that's a perfect hire. I feel like someone who's very very native with the tools and also moves very fast. Yep. Um, great. Okay. Do you want to try some of the chim chur? Yes. And then I think a peaches that should be good enough. Um, there's also a spoon over there if you want to use. And yeah, we got it set up for blowtorrching.
</details>

>> 酷。
<details><summary>Original English</summary>
>> Cool.
</details>

>> 在做这个的同时，我想顺着招聘这个话题深入聊聊。你们团队以招人极其审慎、保持极其精炼的团队架构而闻名。你们最早招募的核心成员之一——好像是第一个正式员工——就是 Ephie，他基本上是该领域业内顶尖的高手；其他增长业务人员也都在特定领域极其专业、甚至曾创办过自己的业务，包括 Adele 等人。从最初只有你和 Ronic 两个人，到如今团队规模不断扩大，在最优秀的员工身上，你有没有发现哪些共同的特质，是你在如今招聘时依然格外看重的？
<details><summary>Original English</summary>
>> But I guess while we're doing that, I want to double click on this with hiring. So you guys are notorious for hiring very slow and moving with a very lean team. initially your one of your earliest hires. I think your first hire was Ephe who's basically one of the best in the industry um for this specific topic um and even your other like growth hires um very specialized have their own business even Adele others and so I guess now going from just you and Ronic to now being a scaled up team are there traits that you see recurring among like your top hires that you even today when you're recruiting try to look for
</details>

>> 我们排名第一的文化价值观是对自身专业技艺的极致痴迷（Obsession for your craft）。你可以把“痴迷”单纯看作一种渴望，但我真正寻找的是：如果你与任何一个极度渴望精通某项技艺的人交流——不管是厨师、运动员还是任何人——你总会发现，他们在对待日常工作的方式上都带着一种严谨性。
<details><summary>Original English</summary>
>> our number one cultural value um our number one cultural value is having obsession for your craft M um and I think that like you can think of obsession as just desire, but like the the real thing that I look out for is if you talk to anybody that is really really obsessed with this idea of being great at something. Yeah. Um cooks, athletes, whoever, you always find that they have this like rigor to the way that they approach the day-to-day. M
</details>

>> 比如 Yee 是一位了不起的机器学习研究员，这不仅仅是因为他的博士研究方向与我们的业务吻合。他可能是在审视数据方面最痴迷的人之一。他对数据集的检查极其仔细，可能脑子里都记住了每一页单独的 PDF 长什么样。
<details><summary>Original English</summary>
>> um like Yee is an incredible ML researcher, not just because he did a PhD in what we do. Um he is probably one of the most obsessive people about inspecting the data. Like people look through the data set really really closely. Um probably has like individual PDF pages memorized like
</details>

>> 哇。
<details><summary>Original English</summary>
>> Oh wow.
</details>

>> 我没见过谁花在在 PDF 上画标注框的时间比他还多的。
<details><summary>Original English</summary>
>> I don't know anybody that has spent more time drawing boxes on PDFs.
</details>

>> 厉害。
<details><summary>Original English</summary>
>> Wow.
</details>

>> 这很重要。做无法规模化的事（Do things that don't scale）。
<details><summary>Original English</summary>
>> Um and that matters. Don't scale.
</details>

>> 没错。即使在我们某些时期数据标注员数量比全职员工还多的阶段，他依然会亲自去审查数据并深陷其中。我认为工程师也必须对客户支持这类事情保持痴迷。不仅仅是为了发布耀眼的新功能，更要确保在生产环境中覆盖长尾案例等等。我认为这种特质很难强加给别人。如果一个人把工作看作是一件渴望做到极致的事情，他们自然就会有一种在细节上不断改进的驱动力。所以我们在招聘中会极力筛选这种特质。
<details><summary>Original English</summary>
>> Exactly. Yeah. like it it's really really important even when we had at some point we had more data labelers than we had full-time employees. Oh wow. Um but he would still be the type to look at the data himself and like really obsess over it. I think engineers need to be obsessed about things like customer support. Like it's not just about the flashy feature launch. It's about making sure that in production the longtail cases are addressed like all that kind of stuff. Yeah. Um and I think that's a really hard thing to force somebody to want to do. Like if they look at their work as this thing that they want to be incredible at. Yeah. Um they naturally have this tendency to want to improve in that way. Got so we try to select for that.
</details>

### 如何在面试中识别“对技艺的痴迷”

>> 明白了。那你如何去评估候选人，或者在面试中挖掘出这种特质？你只是看他们过往的经历，还是说在面试中有特定的提问流程来判断他们对自己的技艺有多痴迷？
<details><summary>Original English</summary>
>> Okay. And I guess how do you assess that or get that out from a prospective employee? Do you just look at their experience? What they've done in the past or are there questions processes in the interview that you kind of are able to determine how obsessive they are with their craft or even in the past?
</details>

>> 我觉得痴迷的人往往会在工作的方方面面都展现出这种特质。有时候会体现在全职工作中，有时候则表现在个人爱好上。我非常喜欢问候选人：有什么事情是他们自认做到了世界顶级水准的？当他们谈论起那件事时，你能看到他们的眼睛是在放光的。那件事甚至可以是一款电子游戏。只要将这群人引导至正确的方向和正确的问题上，这种痴迷往往是能自然迁移过去的。
<details><summary>Original English</summary>
>> I think obsessive people tend to be obsessive in many different ways throughout their work. Um, and maybe sometimes it shows up in their full-time job. Maybe sometimes it shows up in like hobbies. Yeah. I really like asking people about something that they are just world class at. And you see the way that their eyes kind of light up um when they talk about that thing. Um, could be a video game even like people that are obsessive in that way as long as you orient them towards the right things like the right problems. Yeah. Naturally transfer over.
</details>

>> 明白了。顺便说一下，桃子片切了很多。
<details><summary>Original English</summary>
>> Gotcha. Plenty of peach slices by the way.
</details>

>> 好的。我拿几片，我们也可以用喷枪炙烤一下。没错，痴迷确实是相通的，我们继续烤。
<details><summary>Original English</summary>
>> Yeah. I'll grab a couple and we could also blow torch them. No, that makes sense. I think obsession does carry over and then we'll talk. Yeah.
</details>

>> 你想烤到多焦？随你喜欢，直接拿喷枪对着烤都行。
<details><summary>Original English</summary>
>> How charred do you want it to be? as as much as you prefer. Honestly, you could put a torch in there.
</details>

>> 老实说，我以为这就算数了。
<details><summary>Original English</summary>
>> Honestly, I thought it would count.
</details>

>> 哈哈。你想直接扔平底锅里吗？
<details><summary>Original English</summary>
>> Yeah. You want me to just toss it on a pan?
</details>

>> 行，我们直接丢锅里烤。我这边用喷枪有点笨手笨脚。我们用这个 Impulse 灶台。你想试试吗？直接打开就行。
<details><summary>Original English</summary>
>> Yeah, we should just toss I'm struggling a bit here. And we'll use the impulse stove. Um, you want to try? So, you just turn it on.
</details>

>> 太期待了。
<details><summary>Original English</summary>
>> I'm so excited for this.
</details>

>> 对，直接拧旋钮调节温度就行。
<details><summary>Original English</summary>
>> Yes. So, you can just twist it.
</details>

>> 好的，我看过这家公司创始人煎牛排的视频。虽然我现在是租房子住，但如果不是租房，我肯定会买一台。
<details><summary>Original English</summary>
>> Oh. any temp. Um um yeah, I've seen the videos of the founder cooking a steak and I rent my apartment, but if I didn't, I would be purchasing one.
</details>

>> 是的，这个炉灶非常棒。升温极快，甚至连烧开水都非常轻松。
<details><summary>Original English</summary>
>> Yeah, I think this stove is very very nice. It heats up super fast. Even boiling water, it's it's very easy.
</details>

### 从早期初创到 B 轮：创始人的认知刷新与放权

>> 从极早期一路走到现在的 B 轮融资，再次向你表示祝贺。在从原本极小的团队走向如今的成长期过程中，有没有什么东西是你必须去主动摒弃（Unlearn）甚至做出改变的？
<details><summary>Original English</summary>
>> Yeah. Okay. Going from very early stage now, series B, congratulations again. Thank you. Um, have there been any things you've had to unlearn or even change going from such a small team now to I guess growth stage?
</details>

>> 有的。首先，我认为在公司发展顺利的前提下，公司面临的问题在体量上从来不会变小，你只是随着时间推移去解决不同类别的问题而已。在创业第一天，我的工作大多是处理当下迫在眉睫的具体杂务，比如跟进某一个具体客户订单，或者解决某一张具体的支持工单。随着人员增加，这显然发生了改变。
<details><summary>Original English</summary>
>> Yeah. Um, one I I think the number of problems at a company assuming things are going well never actually decrease in size. Um, you just get to work on different problems over time. And so like day one a lot of my job was just whatever in the weeds thing I needed at that moment. Um and so it's like an individual deal or like an individual support ticket. Obviously that changes as you have more people. Yeah.
</details>

>> 学会放手会让人觉得很不适应。作为创始人，有很长一段时间，如果我没有随时盯着 Slack，就会产生严重的焦虑感。因为心里总觉得只要我不盯着，某些地方就会出问题。
<details><summary>Original English</summary>
>> Um and it's weird to let go of that. I think as a founder like for a long time I would have this anxiety if I wasn't constantly available on Slack. Mh. Um because it just felt like if I'm not looking like something could go wrong. Yeah.
</details>

>> 随着时间推移，这种担忧逐渐减轻了。你开始意识到，公司在某种程度上有了它自己独立的生命力。不过你仍然要花大量时间陪伴核心客户，同时也会处理越来越多与团队组织相关的事情。我以前从没想过自己会成为那种坐下来写企业文化文档的创始人，但稀奇的是，你的很多工作开始变成这一类事情。但这都挺有意思的。我经常发现自己对当前阶段的工作做得一塌糊涂，花三个月摸清门道后，又开始迎接全新的工作职责。
<details><summary>Original English</summary>
>> Um that's been less true over time. Like you start to realize that the company has a life of its own on some level. Um but you always still spend a lot of your time with your top customers. Um you start having more like people related things over time. Like I never thought I would be the type of founder to write culture documents, but weirdly a lot of your job starts being things along those lines. Yeah. Um, but it's all fun. Like I constantly find that I suck at the current phase of my job and then you get good at three months and then you start doing a new job.
</details>

>> 是的，随着公司的成长和扩张，角色一直在动态演进。在流程机制上整体还是一样吗？我记得你提过，早期阶段你每周会给每位工程师设定一个首要任务，那通常与你们想要达成的核心目标直接挂钩。如今团队规模扩大了，你依然在贯彻这种“一周完成一个优先级目标”的节奏，还是说变得更像大厂那样的组织架构了？
<details><summary>Original English</summary>
>> Yeah. It constantly evolves as as you grow and scale. Yep. Is the process generally the same? Cuz I recall hearing you say in the early stage you would give one priority to an engineer for a week. That would kind of be maybe the direct directly related to the goal you want to achieve. Yeah. And now that the team has scaled up, do you still try to enforce that um one priority get it done in a week or is it a little more like an organization like a big tech company?
</details>

>> 我们现在每周依然会召开全员会。工程团队需要对核心大单有清晰的了解，反之亦然，所有这些都没变。不过我确实认为，我们的一些重要项目很难直接拆解塞进一周的时间里，所以某些事情的时间跨度发生了一些变化。而且有些事情属于“当天首要任务”，甚至都算不上“周任务”。但我们确实极力确保团队对我们当下真正看重的事情有清晰的认知。我的思维方式也稍微发生了一些转变，从按周规划更多转向了按月和按季度的优先级。
<details><summary>Original English</summary>
>> Yeah. Um we still meet as a full team every single week. Um so like engineering should have good context on our top deals and vice versa. Like all of that has not changed. Um, I do think some of our important projects are hard to dismiss into like one week and so maybe time horizons for some things have changed and there are still things that are on the order of you know like it's a priority of the day not even priority of the week. Um, but we do try to make sure that there's clarity on like what are the set of things we really care about. Yeah. Uh and my thinking has shifted a bit more from weekly to more so like monthly priorities and quarterly priorities as well.
</details>

>> 明白。
<details><summary>Original English</summary>
>> Gotcha. Okay.
</details>

>> 但它绝不像大型科技公司的体制。我们不会去制定一套年度 OKR 之类的条条框框去死板对标。我们依然在努力像初创企业一样保持敏捷精简。因为在这个时代，尤其在 AI 和编程领域，瞬息万变，你无时无刻不在接收新的信息。如果不能根据当前的市场变化快速调整，你就会落后。
<details><summary>Original English</summary>
>> But it's not quite like big tech organization like like we don't have a annual set of things like OKRs that we're going up against or anything. Yeah. We're still trying to operate it lean like a startup and great cuz you're constantly learning new information, right? like the market changes so quickly today that if you don't adjust as a function of whatever the current thing is like you're behind no s there especially in this age of AI and coding it's moves very fast
</details>

### 行业竞争、防御壁垒与飞轮效应

>> 转向商业层面，你们身处一个相当拥挤的赛道，存在不少竞争对手，大家都在拼尽全力提升性能。如果不能使用所有客户的数据来进行训练，在数据量上升但模型未必能借此扩展性能的情况下，你如何看待护城河与防御壁垒？你们如何形成差异化并保持领先？
<details><summary>Original English</summary>
>> um but kind of then to pivot more to the business aspect um I know that you guys um are in a space that is somewhat crowded you have other competitors and everyone is going as fast as possible to improve the performance Yeah. So how do you kind of think about defensibility um in the case where you may not be able to train out all the data of your customers um and so maybe the performance can't scale as the volume scales um and how you differentiate and kind of stay ahead of pack.
</details>

>> 我前面提到的持续评测能力，正是我们考量如何围绕每月 10 亿页的处理量构建飞轮的核心支柱。我们的很多工作并不仅仅局限于某一种特定的页面排版，而是在于横向通用性。一个很好的良性循环是：我们的客户群越广，我们对各种长尾问题的商业直觉就会变得越敏锐。
<details><summary>Original English</summary>
>> Yeah. So I mean things like what I mentioned earlier of being really good at continuous evaluations um ends up being a key part of how we think about your processing a billion pages per month like how do you have a flywheel around that. Mhm. Um I think a lot of our work is not just on you know an individual type of layout or anything like that. It's this like horizontal nature and a really nice thing is the more the broader our customer base gets the better our intuition around the range of problems becomes too. Got it.
</details>

>> 归根结底，我认为竞争激烈的市场其实非常好，因为这是一个完全凭实力说话（Meritocratic）的环境。为 Harvey 这样的头部 AI 原生独角兽提供服务意味着：如果我们不能持续保持行业最强，他们自己就会去另寻高就。我们的态度一贯是：我们只需全力迎战，接下挑战。
<details><summary>Original English</summary>
>> Um I ultimately think that competitive markets are really nice because like it's very meritocratic. Um and so serving you know some of the leading AI native startups uh like a Harvey just means if we don't continue being the best like they will look for the best themselves. Yeah. Um and our stance has always been like we just need to rise to that challenge.
</details>

>> 有道理。可以说你们是竞争导向的，渴望赢下比赛，并在公平环境下角逐。
<details><summary>Original English</summary>
>> Yeah, that makes sense. So you would say you're probably competitive first. You want to win and and yeah have a level playing field.
</details>

>> 确实是。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 是的，尤其现在很多市场都会极度拥挤，关键在于你能不能跑得最快并去竞争。相比以往，现在更重要的不是去建所谓体制化的护城河，而在于极致的执行力。
<details><summary>Original English</summary>
>> Great. Yeah, that makes sense. I think yeah especially these days too um with how the landscape is yeah a lot of markets will be very crowded and it's just a matter of can you be the one to move that fast and u compete so yeah it's good to hear I think more so than ever before it's less about like systemic modes and more so on execution
</details>

>> 绝对如此，执行力就是一切。好的，我觉得桃子可以出锅装盘了，然后我们开始煎牛排。回到前面探讨的 Reducto 的未来发展。
<details><summary>Original English</summary>
>> yeah constantly for sure for sure great okay I think the peaches look good to transfer them to the plate and then you see get started on this steak so yeah kind of going back on what we touched before about the future of reductto.
</details>

>> 哎呀，能再给我加点油吗？
<details><summary>Original English</summary>
>> Damn, can I get some more oil?
</details>

>> 好的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 谢谢。
<details><summary>Original English</summary>
>> Hey.
</details>

### 产品边界：专注文档操作而非存储

>> 谈到 Reducto 的未来，你是否设想过团队会扮演像 Rippling 那样的角色——打造一系列不同的横向产品，成为一家提供多元服务的复合型初创企业（Compound Startup），甚至接管文件存储，或者满足客户在提取、解析和编辑之外的其他需求？
<details><summary>Original English</summary>
>> Yeah. on the future of Reducto, do you kind of yourself maybe taking the role like a rippling where you have a lot of different products that are horizontal um and kind of having this like compound startup that provides a lot of services and maybe even taking over like file storage or um yeah other needs that your clients may have beyond just extraction, parsing, editing.
</details>

>> 我们最关心的核心是围绕文档本身所采取的具体行动。我们对这个问题的思考更少聚焦在文件存储这类的方向上。对我们而言，衡量的准则永远是：我们能否在那项任务上做到全球第一？当你思考文档分类、解析和编辑时，答案是肯定的。至少在今天，单纯做数据存储对我们来说吸引力不大。只有在存储能显著为客户带来更优秀使用体验的前提下，我们才会真正去探索这个方向。
<details><summary>Original English</summary>
>> Yeah, we care the most about the actual actions with the document itself. Okay. Um, so the the way that we think about it is less so focused on file storage and things like that like the question for us is always can we be the best in the world at that task. Um, and as you think about things like classification on documents and parsing and editing like the answer is yes. Um, at least as of today things like you know just storing the data is less interesting for us. Yeah. Um, we would only really push on those sorts of directions if it in that leads to a better experience for our customers.
</details>

>> 明白了。我还听说，很多客户找上门时，通常都带着一批在此前所有竞品测试中都失败了的文档，但在 Reducto 上却成功运行了。你有没有什么有趣的案例或者神奇时刻可以分享？
<details><summary>Original English</summary>
>> Got it. And so whenever you get your customers, I also heard that um they usually come with a set of documents that have failed all the previous tests y before and somehow it works with reductto. Do you have any fun stories to share I guess about instances or like whatever you can um of like moments where something was just very magical that happened for?
</details>

>> 我最喜欢的客户演示闭环，就是客户发现了一个以往完全无法跑通的业务用例，最后通过我们彻底解决了；他们甚至开始引入那些原先被认定为根本无法实现的复杂需求。
<details><summary>Original English</summary>
>> Yeah. Um, my favorite type of just like customer demo loop is when they find a use case that previously could not work. Mhm. Um, and they end up just like being able to solve for that thing. Like they start introducing things that they just seen as out of scope. Mhm.
</details>

>> 另外我们还发现，解析准确率的提升会产生很多意想不到的下游正面效应。例如我们的一家法律科技客户发现，当底层文档改由 Reducto 解析后，终端客户与文档的交互量直接翻了一倍。他们提了更多问题。这显然不是我们在宣传中单独售卖的功能点，但他们发现回答质量和引文精准度明显提高，导致整体用户黏性更强。这非常关键，这是我们终极追求的成果，尽管它未必能直接体现在前期的销售邮件里。
<details><summary>Original English</summary>
>> Um, there's also a few things where we find that like parsing accuracy ends up translating into downstream effects that people don't consider. Like one of our legal tech customers ended up finding that customers interact with documents twice as much when it's parsed by reducto. Oh wow. Um like they ask more questions. Um and it was something that like it's obviously not a feature that we sell. Um but they just found that like answer quality improved and citations precision improved such that overall customers were more likely to engage. Yeah. And that's huge. Like that's the kind of thing that we ultimately want to drive, but maybe it doesn't show up immediately in an email process.
</details>

### 联合创始人的默契：从未吵过架的搭档关系

>> 明白。关于你和 Ronic 的搭档关系，你们俩都是 MIT 毕业的对吧？是在他当助教（TA）的一门课上认识的，当时他大一。你以前说过，他的才华和能力让你印象极为深刻，随后便一起共事。如今走过了差不多两三年——快三年了——在这三年时间里，有没有哪些时刻让你觉得彼此真正志同道合？有没有哪些特质是你认为联合创始人不可或缺的，或者有哪些反直觉的经验是违背传统创业建议的？
<details><summary>Original English</summary>
>> Gotcha. Okay. Yeah. And I guess even now on the team with you, Ronic, you guys both went to MIT, right? And then you met through a class that he was RA for or like being a TA. Um, and yeah, when he was a freshman. Yeah. Yeah. And you have said in the past that you're very impressed by just his ability and his talent and then work together. And I guess over the course of now it's been like two two years. Two we're coming up on three. Three years. Yeah. Yeah. Like during those entire three years, have there been moments where you realized like you guys really clicked and these traits are very important for co-founders to have or is the moments where you know seem non-intuitive that the conventional startup advice they give that you guys kind of go against?
</details>

>> 截至目前，我们联合创始人关系中最让我引以为傲的一点是：我们从未发生过任何一次真正意义上的争吵。我们针对业务会有很多探讨，面对不同意见也会深入沟通，但我们有一种非常棒的默契——对事不对人，就事论事地化解分歧。
<details><summary>Original English</summary>
>> Yeah. Um, I think one of my favorite things about our founding relationship to date is, uh, we still have never had what I would truly classify as like an argument. Okay. Um, like we've had plenty of discussions about things and talk through deferring opinions. Um, but we have a really really good dynamic of talking through things on their own merits uh, and like resolving disputes. Well,
</details>

>> 在彼此尊重、技能互补这些基础之上，我认为这是最重要的一点。创业极其艰难，你必须确信自己能与合伙人休戚与共、历经起伏而不心生怨怼。这一点非常珍贵，在刚认识一个人时是很难强求或预测出来的。
<details><summary>Original English</summary>
>> okay. And to me, that's honestly the most important thing outside of there needs to be this baseline if you really respect the other person. You think that they bring a complimentary skill set and all that. Um, but startups are really hard and it's really important that you feel like you can go through the ups and downs with your co-founder without being resentful. Um, and that's special. Like I I think that's hard to force or forecast when you're first meeting somebody.
</details>

>> 你和 Ronic 的技能树是互补的吗？
<details><summary>Original English</summary>
>> Yeah. And do you and Ronic have complimentary skill sets?
</details>

>> 我觉得是的。虽然我本科在 MIT 读的也是计算机，但相比之下，我几乎算是个非技术人员。通常我们在产品定义上会有交集，他全盘负责工程落地，在那方面有着极强的主见；而我则主要负责市场拓展（Go-to-market）。两人都有足够的技术底子来对话，但我绝不会去和 Ronic 在 Hackathon 上同台打擂台。实际上我觉得他这辈子打黑客松就没输过。
<details><summary>Original English</summary>
>> I'd say so. Like I I did my entire undergrad in CS at MIT, but um in comparison, I might as well be non-technical. Um yeah, like typically we will overlap on product. Um he just leads a lot of our engineering work across the board. Um and like is a type to have a lot of strong opinions there. And then vice versa for go to market on my side. Gotcha. Okay. But both technical enough where he can u conversations but I'm not going to I would never enter a hackathon against Ronic. Um I don't think he's lost a hackathon in his life actually.
</details>

>> 厉害。你们当年也一起打过黑客松对吧？在 Anthropic 推出早期 Claude 开放测试资格的那场黑客松上。
<details><summary>Original English</summary>
>> Dang. You guys also did a hackathon together right? We did. The anthropic one when quad the early quad model came out.
</details>

>> 没错，当时他们给出了早期内测资格，而那正是我们创业征程的起点。当时我们萌生了对 Reducto 最初构想：模型本身已经令人惊艳，但上下文窗口却小得可怜，于是由此发散构思出了长期记忆的想法，最终演变出了 Reducto 后来的一切。
<details><summary>Original English</summary>
>> They were uh giving early access to Quad. Um that's actually sort of how our founding journey started. Um yeah, so back then that's where the whole like framing for Redto came in where models were already really impressive. Yeah. Um but they had horrible context window limits and so that spiraled into this like long-term memory idea. Yeah. And everything else that reductive became after. Gotcha.
</details>

### 从 RAG 到信息检索：本质都是搜索问题

>> 时代确实变了。那时 RAG（检索增强生成）非常火爆，你们早期也在处理器中做了大量分块（Chunking）工作，现在随着上下文窗口增大，可能大家对此关注变少了。
<details><summary>Original English</summary>
>> Yeah. Times have definitely changed because for sure like then rag was a very big thing and you guys still do a lot of chunking right with your processors it less so now with less windows are okay yeah like I think chunking is less of maybe what piques somebody's interest
</details>

>> 分块技术现在可能不太容易引起公众的兴趣了，但绝大多数问题归根结底仍然是搜索问题。不管你称之为 RAG 还是别的叫法，很多产品本质上都是某种形式的搜索，再加上在搜索结果之上的某种推理推断。从定义上来看，这其实就是检索增强生成。
<details><summary>Original English</summary>
>> um but a lot of problems ultimately are search problems okay and whether you call it rag or you call it something else like plenty of products are still some form of search and then some form of inference on top of the search results Gotcha. Which I personally see as like definitionally it's kind of retrieval augmented generation.
</details>

>> 能就“所有问题最终都可以归结为搜索问题”这一点展开说说吗？在文档解析处理领域，底层的逻辑是一样的吗？
<details><summary>Original English</summary>
>> Yeah. Right. That's true. Can you double click on that with the notion of every problem kind of being still down to a search problem. Um because I know like even with coding like ref and file search kind of became next thing after rags and I guess for document parsing for processing is the framework the same do you differently? Are there like insights that you can share? Of course.
</details>

>> 通常人们提到 RAG，想到的都是传统方案：将内容分块、向量化（Embed），然后用余弦相似度搜索找出应该塞进模型上下文的内容。很多人对 RAG 有排斥心理，觉得“我做的又不是聊天机器人”。但我们的很多客户实际上是在为 Agent 搭建文件系统，Agent 在文件系统中检索，定位相关上下文，进行逻辑推理，并把多份文档的信息拼凑在一起。无论是由 Agent 在后台自主执行，还是在搜索产品界面中直观呈现，本质都是：检索信息、拼装上下文、综合分析，并最终做出某种操作决策。
<details><summary>Original English</summary>
>> Yeah. So um I mean a lot of times when people think of rag they think of like the more traditional you chunk things um you embed them and then you use cosign similarity search to figure out what to pass into your models context. Yeah. Um and people have an aversion to rag on the basis of like oh I'm not building a chatbot. Mhm. Um, a lot of our customers will still have, you know, like a file system for an agent and the agents is crawling through the file system to figure out where the relevance contextes context is and like it's reasoning on that context and piecing together information for multiple documents. Yeah. Um, what I mean is just like that process, whether it's the agent doing it or whether it's, you know, clearly visible in your search product, is you're searching for information, piecing together that context, synthesizing it, and making some sort of action at the end of it all.
</details>

>> 原来如此，非常直观通顺。牛排看起来煎好了。聊到团队现状，你们目前应该正在全面招人吧？目前开放了哪些岗位？
<details><summary>Original English</summary>
>> I see. Okay. Yeah, that makes sense. It's like a pretty intuitive process. Um, let's see if Great. Okay. I think my stake is done. I feel like you can probably start looking at but yeah and I guess now going towards more how people can find you and what you're looking for. I assume you're hiring across different roles. Are there
</details>

>> 我们目前大概有 40 个空缺岗位。
<details><summary>Original English</summary>
>> I think we have like 40 roles open at this point.
</details>

>> 目前团队的产能瓶颈主要在哪里？主要是销售团队，还是仍在寻找大量研究人员？
<details><summary>Original English</summary>
>> Okay. What what are you bottlenecked by right now? Is it mainly sales or is it you still trying to find a lot of researchers?
</details>

>> 各个方向都非常需要。工程方面在大量招聘，特别是随着规模扩大，底层基础设施问题极其关键。我想在洗手之后再切肉。我们在招聘产品工程、机器学习（ML）岗位以及平台工程方向。销售团队年初只有一名 AE，现在已经扩大到了 30 人。整体招聘力度很大。在短期内招人步伐绝不会放缓，团队仍然感到产能吃紧。
<details><summary>Original English</summary>
>> It's across the board. Um so we're hiring a lot on engineering like infrastructure problems really matter to us especially as we start to scale. Um also I do want to wash my hands after. Yeah. Um mistakes in the washing hand. Yeah. So we're hiring for our product engineering team, ML roles, um platform as well. On the sales team, we started the year with one AE and seats. Wow. And we now have 30 people on the sales or Wow. Um so a lot of hiring overall. Yeah. Um I expect that's not going to slow down in the near term. Like we still feel capacity constrained as a team. Gotcha. Yeah.
</details>

>> 这是个好兆头。面对成长的烦恼，远比陷入痛苦的转型地狱要好得多。好的，你把牛排放这里，然后我们去洗手。
<details><summary>Original English</summary>
>> Well, that's a good place to be in. I feel like challenge of growing rather than the challenge of being in pivot hell as you mentioned in the past of um not being able to sit down and solve a problem. Yeah. Uh is a lot harder than being at the moment where you just kind of grow. So yeah, it should be good, I think. Yeah. So you can transfer here and then we could wash.
</details>

>> 我以前从来没用叉子煎过牛排。凡事都有第一次，太棒了。
<details><summary>Original English</summary>
>> I've never cooked a steak with a fork before. first for everything. Amazing.
</details>

### 白领工作的“Claude Code时刻”与文档智能编辑

>> 好，我们回来了。牛排已经醒好了，我们可以开始切了。你切面包我切牛排？回到 Reducto 的业务上：你们正从一家帮助企业提取和解析文档的平台，逐步扩展到支持文档编辑处理。从“读取”拓展到实际的“修改编辑与知识型工作”，这里面存在广阔的空间。
<details><summary>Original English</summary>
>> Great. And we're back. So, our steaks are ready and we can start cutting. Do you want to cut the bread and I'll cut the steaks? But yeah, I guess more so again on reducto uh you guys have made this transition from being the place where companies can come to extract and parse documents to even now handle editing, right? And so do you see a lot of opportunities or transitioning to taking on this whole use case because I assume going from reading to now like actually analying the editing and the knowledge work is can cover a lot of use cases.
</details>

>> 我大体上的判断是：白领工作目前尚未迎来类似 Claude Code 的颠覆性时刻。很多白领工作不仅是信息整合，不仅是从文档中提取数据——三明治要做多大？按你喜欢的尺寸来就行，直接切开就好——它不仅是从文档提取数据，往往在这些流程的末端，你还要把结果写入电子表格或 Word 文档中，对吧？
<details><summary>Original English</summary>
>> Yeah. My general view here is I don't think white collar work has quite had the equivalence of like um a quad code moment. Um, and I think if you think of a lot of white collar work, it's not just information synthesis, like people pulling from documents, but also how big are we making these sandwiches? Um, as big as you want. We could just cut it. Yeah. Okay. Um, it it's not just people pulling from documents, but also like at the end of a lot of these processes, you write into a spreadsheet or you write into a word doc, whatever it is, right? Um, and so
</details>

>> 所以我们极力确保视野不仅局限在最前端的解析与提取层。我们希望让模型能够以极高可靠性去完成合同修改审阅（Redline contracts），去填写贷款申请表，做任何人类原本需要做的事情。这背后衍生出一整套极具挑战的技术问题。这块牛排真不错。
<details><summary>Original English</summary>
>> we really wanted to make sure that we are not just thinking about that initial layer of parsing and extraction. Like we want to make it possible for models to redline contracts as reliably as possible. Um, we want them to be able to fill out loan applications, do whatever a human would have had to do, right? Yeah. Um, and there's a range of problems that comes up there that is just really hard to do. That's a great stake.
</details>

>> 我们前面聊到过，人类每年在文档本地化（Localization）上要花费数十亿美元。如果你是一家美国企业，想与中东的公司做生意，你大概率需要将内容翻译成阿拉伯语。在今天，这极其依赖人工。模型虽然非常擅长翻译，但把修改重新应用回文档却非常困难。因为你需要把一份按英文排版生成的文档进行版面重构。换成从右向左书写的语言后，文本可能直接溢出到了下一页。排版格式完全变了。
<details><summary>Original English</summary>
>> Yeah. Um, like one of the things we were talking about earlier is humans spend billions of dollars per year on document localization. Uh, and so if you're a business in the US and you want to do business with a a company in the Middle East, um, you probably are going to want to translate your content into Arabic, right? And if you think about that today, it's very manual. Models are great at the translation. Yeah. But applying that edit to a document is really hard because you're going to need to take a document that was generated in English and change the layout. Like when you change it to a right to left language, now you need to consider like maybe the text flows over onto the next page. Formatting is different.
</details>

>> 没错。这背后包含了一整套复杂难题，我们希望能够在底层将其为客户抽象化解决。我们在这方面仍处于早期阶段，大约半年前推出了表单编辑端点（Form editing endpoint），我们马上还会发布很多新功能，这将会带来阶跃性的改变。
<details><summary>Original English</summary>
>> Exactly. Um and so there's a whole set of problems here that ideally we can abstract away for our customers. Yeah. Um we're still early in that phase. We launched a form editing endpoint not too long ago. um close to like 6 months at this point. Um but we have a lot that we're about to release soon that I think will be a sub function change here.
</details>

>> 听上去这像是一个完全不同的技术范畴，有点类似于计算机操作（Computer Use）的领域了。
<details><summary>Original English</summary>
>> Gotcha. This kind of sounds like a pretty different problem though. It sounds very like computer usees like if you're filling out
</details>

>> 确实有相通之处，很多底层逻辑也更接近于代码生成（Codegen）。但从根本上讲，正因为我们极其擅长理解视觉结构，才让我们能够在诸如落地编辑修改等环节上同样保持极高水准。
<details><summary>Original English</summary>
>> there's some parallels for sure. Um there's definitely a lot of work that's closer to codegen here as well. Um, but I think fundamentally being really really good at understanding things like visual structure makes it possible for us to also be really good at things like the edit application.
</details>

>> 明白。你们是设立了独立的团队来攻克这些不同问题，还是都在同一个团队下？
<details><summary>Original English</summary>
>> Gotcha. Okay. So, do you kind of treat the problem or do you have like separate teams for these different problems or is it all under one umbrella?
</details>

>> 我们并不会把团队划分得那么刻板。我们有一个 ML 团队，团队内部成员会分头解决各种不同类型的问题。当然也会有专精特定领域的成员。比如我们刚刚招进了一位非常优秀的成员 Liang，他之前在 Twitter 上因为开发开源 Office 智能体而引起了巨大轰动。那次招聘难度极高，他刚从新加坡搬过来。他对文档编辑这类问题极度兴奋，目前正在主导相关研发。让对的人遇上让他充满热忱的问题，这种人岗匹配非常重要。
<details><summary>Original English</summary>
>> Uh, we don't really separate teams that meaningfully. Maybe this touches on what we were talking about earlier with, you know, how do we structure prioritization for the engineering team and all that. Um, we have an ML team, but within that ML team, people work on all sorts of different problems. They're definitely people that specialize in certain types of things. We just made a a really awesome hire. Um, his name is Leang. You might have seen he went super viral on Twitter for open source office agents. Oh, I think I saw this. Yeah. Yes. um really hard hire to make. He just moved over from Singapore, but like he's really excited about this sort of editing problem and so he's taking the lead on a lot of that. Like those sorts of just person problem enthusiasm alignments is really important.
</details>

### 数据孤岛与企业隐性知识的挑战

>> 你怎么物色那些对你们使命怀有同样雄心壮志的人才？主要是主动出击还是靠自发申请？
<details><summary>Original English</summary>
>> And how do you find the right people who are um as ambitious, let's say, for the mission? Is a lot of outbound or inbound? Um do you kind of like filter out folks like a specific way? Yeah. Um so that they're very like mission driven. I assume that's like a very big thing you consider in hiring.
</details>

>> 我们有常规的招聘渠道：内部招聘人员、外部猎头等等。但每隔一段时间，你总会在 Twitter 上发现某些人以异于常人的高频频率痴迷地研究 PDF。每当我们看到这种人，就说明这个人很特别——因为他们居然愿意把大把时间毫无功利心地投入到文档处理上。遇到这种人，我们必定会主动去建立联系。
<details><summary>Original English</summary>
>> Yeah, we have steady state hiring. Like we have recruiters in house, we work with agencies, all of that. But every once in a while you find somebody on Twitter that is weirdly obsessed with PDFs um at a more frequent cadence than you would expect. Yeah. And so like anytime we see something like that, like it says a lot about the person that they're spending time thinking about document processing just willy-nilly. Yeah. We'll always try to get in touch.
</details>

>> 回到你刚才提到的“白领工作尚未迎来 Claude Code 时刻”，你认为引发这种大爆发的催化剂会是什么？是让大家意识到应用价值有多高，还是行业扩散及编辑用例的普及问题？
<details><summary>Original English</summary>
>> Yeah, that makes sense. Yeah. And I guess when you're talking about you haven't had a cloud code moment. Yeah. Um what do you think would be a catalyst for that like Cambrian explosion? Is it just a matter of seeing how valuable the use case could be or is it like more so diffusion problem of like specific industries and maybe just more adoption for like the editing use case?
</details>

>> 首先，我认为模型本身的智能水平已经基本到位了。很多前沿实验室此前显然在代码生成上倾注了过多心力，然后才开始思考要让模型去解决的其他问题。代码在很多维度上是一个具有清晰可验证性的问题，而且工程师群体也最愿意拥抱这些新工具。相比之下，企业端的数据散落在各个角落，而且充满了各种奇奇怪怪的经验规则。比如你去和一家大型金融机构聊聊某种纸质流程是怎么跑的，他们会存在诸如此类的企业隐性认知：“噢，如果我在屏幕左下角看到这个标志，我就知道这来自肯塔基州，因此我该执行 X 动作。”
<details><summary>Original English</summary>
>> Yeah. Um one I think model intelligence is right around there. Um and a lot of the frontier labs clearly hill climbed on codegen before they were thinking about some of the other problems for models to solve. Yeah. Um I think whereas code is in many cases like a verifiable problem um and engineers are the most likely to adopt there's definitely like a large component of enterprises have their data in all sorts of different places and there are like weird heruristics of you talk to a large financial institution about how like some paper process is done and they'll just have institutional knowledge of like oh if I see this in the bottom left of the screen I know it's from Kentucky and therefore or I do X. Yeah.
</details>

>> 这些规矩极少会被清晰明确地书写沉淀下来。因此，做工具生态的人还有海量的工作要做：汇聚这些上下文、协助他们构建匹配的知识库、为模型提供充足的上下文以便对数据进行有效推理。但我觉得，距离这一设想在大规模范围内落地已经不远了。
<details><summary>Original English</summary>
>> Um it's rarely the case that that is clearly written down. Um and so I think there's a ton of work for people in the tooling space to do to like aggregate that context, help them build the appropriate knowledge bases, give models the sufficient context for them to be able to reason on that data. Yeah. Um but I don't think that we are far from a point where that happens. Okay. At scale.
</details>

>> 听起来瓶颈更多在于数据的碎片化和上下文的割裂，而不是模型推理能力的不足。
<details><summary>Original English</summary>
>> Gotcha. So it sounds more so like a fragmentation of the data um and context that seems to be the issue more so than performance that
</details>

>> 模型在长周期长流程推理上的能力已经变得如此强悍，以至于纯粹的智力水平看起来越来越不太可能是最大的瓶颈了。
<details><summary>Original English</summary>
>> models have gotten so good at long horizon reasoning that it feels less and less likely that intelligence is the biggest bottleneck.
</details>

>> 既然如此，要梳理俄亥俄州某些旧文件系统里堆积如山的纸质档案，这似乎不是纯靠通用软件就能轻松搞定的。通过文档处理来切入这件事，是不是需要更多垂直深耕？
<details><summary>Original English</summary>
>> Yeah. And so in that case, is that something that we need like a more concentrated effort because I feel like um you know, wrangling all these different sources of data from like this paper in like Ohio where they have all these like older file systems um isn't something that software necessarily can solve. Yeah. Um so like maybe this is not something that's trivial by approaching it through like a document processing or have you thought about it differently?
</details>

>> 这正是很酷的一点：我们能够与各个垂直赛道的领先团队保持极其紧密的合作。比如我们与负责端到端报税自动化的 Basis 团队紧密合作；与法律科技领域的 Harvey 和 Legora 深度协同。正是因为他们在特定场景的极度专注，让他们开始摸索出在具体业务语境下，端到端交付真实价值到底需要什么。
<details><summary>Original English</summary>
>> Yeah. I mean the cool thing is we get to work really really closely with a lot of the leading teams in all sorts of different verticals. Um and so we've been working with you know the basis team um who's trying to automate N10 tax filing. Um we work super closely with companies like Harvey and Lora who are doing incredible work in the legal space. And part of the great thing about them specializing is that they start to figure out in a certain context what it takes to deliver that value end to end. Um, which is great.
</details>

### 组装牛排三明治与成本削减

>> 懂了，有道理。这片牛排冒着热气呢。我们可以开始组装三明治了，组装完尝尝就可以收尾了。除了这次发布之外，今年剩下的时间里你还有哪些期待的里程碑？再次恭喜你们。
<details><summary>Original English</summary>
>> Gotcha. Okay, that makes sense. It's steam a piece. Oh, okay. Good. Mhm. Okay, we could assemble one and then eat it and then call it. Okay. Yeah. And I guess are there any other milestones or things that you're looking forward to outside of this launch? Congratulations again for the rest of the year.
</details>

>> 全面来看，我们的模型性能都在大幅提升。你要加墨西哥辣椒（Jalapeño）吗？想一起放上去吗？当然。我们对结构化数据提取模型进行了大幅升级。不仅是准确率，我们在引用性能（Citations performance）和结构合规性（Schema adherence）上也做得更好了。而且综合成本大幅下降。以往每提取一页结构化数据的总成本在 4.5 美分以上，而现在我们在提升性能的同时，将费用直接砍半。
<details><summary>Original English</summary>
>> Yeah. Um, across the board, our models are getting much much better. You want the Halo? Yeah. You want to put this on with them? Sure. Yeah. Um, so we have a a massive improvement to our structured extraction models as well. There, this isn't just accuracy again. Like we're getting better at things like citations performance and schema adherence. Um, and are doing that at a much more effective cost. We announced this today. Um, historically a page of structured extraction would have cost you all in like over 4.5 cents. And now we're able to do that at half the rate while also improving performance.
</details>

>> 哇。你没事吧？
<details><summary>Original English</summary>
>> Oh wow. Um you okay?
</details>

>> 呛了一下。降价幅度确实非常大。
<details><summary>Original English</summary>
>> I choked up. Yeah. Wow. That is a big cut.
</details>

>> 是的，这些都是我们想要去推动突破的事情。在全线业务上全面推进帕累托前沿。
<details><summary>Original English</summary>
>> Yeah. And so those are the sorts of things that we want to push on. Um Gotcha. Like really driving that Purto frontier across the board.
</details>

>> 你们主要是聚焦在降低成本上，还是在维持原有性能基线的前提下降本？
<details><summary>Original English</summary>
>> Gotcha. And you were talking before about cost and performance. So, is this mainly a cost focus or just like bring it down while keeping performance at the level that was before?
</details>

>> 幸运的是，这甚至不是我们为了降成本而刻意降成本的结果。我们只是发现，在专注攻克性能本身的同时，单位成本所能获得的智能水准自然而然变得更高了。我们最核心的北极星指标，永远是成为市面上最精准的文档处理平台。并且正如你所说的，保持对底层模型的兼容中立。
<details><summary>Original English</summary>
>> Actually, fortunately, this is not even from us trying to drive cost in and of itself. Um, we're just finding that we can get to better intelligence per dollar while happening to just focus on the performance itself. Like our main Nordstar is always going to be the most accurate document processing platform out there. Mhm. and being model agnostic as well like you said.
</details>

>> 好的，完美。你想放多少？再放一点吗？我们铺两层吧。你可以挪到这边来，也可以再加一些。
<details><summary>Original English</summary>
>> Okay, perfect. Okay, great. Okay, how much do you want to put on? You want to put some more? We should do like two layers. Okay, here we can do you want to I could move on this side. Can also add some. Great.
</details>

>> 感觉如何？很棒。我一直在想那个用户的推特名字是什么……我想确保摆盘方式足够讲究……免得又被人吐槽。不，不是因为那个。这些肉切得挺细的，所以应该很好咬断。
<details><summary>Original English</summary>
>> Great. All right. How are you feeling? Good. I'm thinking about the I'm forgetting his username. Um, but I want to make sure I layer this in a way that's Yeah, you don't get ratio again. No, not that. These are also very small cuts. So, yeah. Should pull apart well.
</details>

>> 看起来棒极了。把布拉塔芝士（Burrata）放上去吧。你来放布拉塔芝士，我来铺桃子？太棒了。是铺在牛排上还是面包上？放在牛排上吧，然后抹开。看起来太诱人了。
<details><summary>Original English</summary>
>> Great. Great. They look great. Yeah. Put the bar on. Yeah. Do you want to put the bara and I'll put on the teacher? Okay. Oh, wow. That is good. You put it on top of the steak or on top of the bread? Um, probably the steak. Okay. Yeah. And then we just top it off. Yeah. Spread it. Yeah. Oh, great. That looks so good. So good.
</details>

>> 好的，放桃子。你想淋奇米秋里酱吗？当然，搅拌一下淋在最上面。天呐，这些特写镜头拍出来绝对绝了。
<details><summary>Original English</summary>
>> Yeah. That's PGs. Okay. Then do you want to do Chimmy Cherry? Sure. Yeah. Mix it and then just put it on top. Oh my goodness. These action shots are going to be crazy.
</details>

>> 看起来真棒。把顶层面包盖上吧，漂亮。切开它。
<details><summary>Original English</summary>
>> Yeah, looks really cold. Do you also want to do it on top? You could put the bread on top action. Let's get the Yeah, nice. Okay, perfect. Let's cut it.
</details>

### 回应网络质疑与品尝收尾

>> 嘿，我们能回应一下那些批评者了吗？
<details><summary>Original English</summary>
>> Yo, can we address the critics?
</details>

>> 可以。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我们可以数数你咬下去的时候会掉出来几片牛排。有人断言会掉出来三片。咬吧。一片，轻松过关。味道怎么样？
<details><summary>Original English</summary>
>> Yes. Um, I think we should count the number of steak slices that come out as you bite. It's alleged that it's going to be three. Mhm. Go for it. One. Yeah. Easy. Okay. How's it taste?
</details>

>> 太好吃了。
<details><summary>Original English</summary>
>> Amazing.
</details>

>> 好的，干杯。而且还有点辣味，太好吃了。牛排三明治永远不会让人失望。桃子很提味。做得太棒了。感谢你们的邀请。
<details><summary>Original English</summary>
>> Good. Okay. Let's cheers. M. Oh, spicy, too. Mhm. That's so good. Oh my goodness. Wow. You can never go wrong with a steak sandwich. Yeah, the peaches. Mhm. Man, this is great. We did a great job. Thanks for having us over.
</details>

>> 那么，在这个三明治里，Reducto 的隐喻是什么？
<details><summary>Original English</summary>
>> So, how does this So, what's the metaphor for reducto in this sandwich?
</details>

>> 你想让我发表一个和文档相关的点评吗……
<details><summary>Original English</summary>
>> You want me to make a document related comment on
</details>